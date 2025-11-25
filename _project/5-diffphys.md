---
title: "端到端的地面全向配送车局部集群规划算法"
excerpt: "端到端的地面全向配送车局部集群规划算法<br/><img src='/images/figures/project/diffphys/cover.png'>"
collection: project
---

## 项目简介

该项目在实习期间完成。

对于一个**半自动机场对飞机自动发餐调度系统的应用场景**。无人机由于航线受限等问题，需要到特定的位置进行地面配送车的对接配送，进行换电，配餐等任务。地面全向配送车需要在机场复杂动态环境下进行自主导航避障，完成多车协同的局部路径规划任务:

- 多台无人配送车参与无人机场景执行整备、等待、接机、起飞等任务
- 与无人机、地勤人员、调度系统实时交互
- 由调度模块完成任务切换与路径下发

而现有的**ego swarm的算法依赖于多机之间的网络通信，广播未来轨迹**，本身避障和集群性能也受到传感器以及里程计的严格限制。

为了实现一种能够适应动态场景的local planner，需要减少基于规则的调参需求，快速训练部署，采用基于可微物理仿真的端到端学习的方法。

## 硬件平台

选择一个由舵轮驱动的地面全向配送车作为硬件平台，搭载IMU和mid360激光雷达。

## 方法介绍

### 训练部署架构

策略模型采用全向**小车的状态，目标位置，安全距离以及激光雷达深度图作为输入**，**输出加速度和速度估计**。基于可微物理仿真器进行端到端的训练部署。

<img src="/images/figures/project/diffphys/overrall.png" alt="DiffPhys Pipeline" style="display: block; margin: auto;">

### 可微物理训练

训练参考DiffPhys框架，基于可微物理仿真器进行端到端的训练部署。

<img src="/images/figures/project/diffphys/training.png" alt="DiffPhys Pipeline" style="display: block; margin: auto;">

借由牛顿第二定律，物理引擎通过对系统状态的迭代更新来模拟物理世界的动态行为进行rollout:
- **感知渲染**: 根据当前姿态渲染深度图(**射线计算交点**)(不可微)
- 构建输入状态: 
    - 深度图(16x12)
    - 水平局部坐标系下的目标速度:`target_v @ R`(从当前位置到目标位置)
    - 当前姿态:`env.R[:, 2]`
    - 安全距离
- **决策阶段**:
    - 网络推理: 加速度`a`+速度估计`v_pred`
- **可微物理rollout**
    - 牛顿力学积分更新无人机位置`p`(可微，保留梯度):
    $$ v_{t+1} = v_t + 0.5 \cdot (a_t + a_{t+1}) \cdot \Delta t, p_{t+1} = p_t + v_t \cdot \Delta t + 0.5 \cdot a_t \cdot \Delta t^2 $$

最终根据loss函数进行反向传播，更新网络参数。

### 策略更新

对整个时序trajectory反向传播：
- 梯度沿轨迹反向传播
- 梯度衰减机制：`grad_decay^(t×ctl_dt)`处理长时序
$$
\frac{\partial L_\theta}{\partial \theta} = \frac{1}{N} \sum_{k=0}^{N-1} \left( \sum_{i=0}^{k} \frac{\partial l_k}{\partial x_k} \prod_{j=i+1}^{k} (\frac{\partial x_j}{\partial x_{j-1}} e^{-\alpha \Delta t}) \frac{\partial x_i}{\partial \theta} + \frac{\partial l_k}{\partial u_k} \frac{\partial u_k}{\partial \theta} \right)
$$

正向计算和反向计算图如下:

<div style="display: flex; justify-content: space-around; align-items: center; gap: 20px; margin: 20px 0;">
  <div style="flex: 1; text-align: center;">
    <img src="/images/figures/project/diffphys/计算图正.png" alt="正向计算图" style="max-width: 100%; height: auto;">
    <p style="margin-top: 10px; font-size: 14px; color: #666;">正向计算图</p>
  </div>
  <div style="flex: 1; text-align: center;">
    <img src="/images/figures/project/diffphys/计算图反.png" alt="反向计算图" style="max-width: 100%; height: auto;">
    <p style="margin-top: 10px; font-size: 14px; color: #666;">反向计算图</p>
  </div>
</div>

### 训练渲染

<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/diffphys/训练.mp4" type="video/webm">
    </video>
</div>
<p style="text-align: center; font-size: 14px; color: #666; margin-top: 10px;">训练过程可视化</p>

### 仿真部署

<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/diffphys/ue.mp4" type="video/webm">
    </video>
</div>
<p style="text-align: center; font-size: 14px; color: #666; margin-top: 10px;"> UE+gazebo联合仿真部署</p>

### 实机部署

<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/diffphys/换电.mp4" type="video/webm">
    </video>
</div>
<p style="text-align: center; font-size: 14px; color: #666; margin-top: 10px;">实机部署换电演示</p>

<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/diffphys/case.mp4" type="video/webm">
    </video>
</div>
<p style="text-align: center; font-size: 14px; color: #666; margin-top: 10px;">实机部署集群避障性能演示</p>



