---
title: "基于数值优化的高效行车时空轨迹规划"
excerpt: "针对行车过程的动态时空轨迹规划<br/><img src='/images/figures/project/driving/cover.png'>" 
collection: project
---

## 项目简介

> "One-stage Trajectory Planning With Conflict-based Optimization for Autonomous Driving," in  2025 IEEE/RSJ International Conference on Intelligent Robots and Systems(IROS2025 under review).

轨迹规划是自动驾驶系统的关键组成部分。传统的两阶段轨迹规划方法通常包含前端粗略路径生成和后端优化，但这些方法存在以下局限性：1) 由于需要大量碰撞检测，计算效率较低；2) 由于两阶段结构对解空间的限制，生成的轨迹可能不是最优的。 
为了解决这些问题，我们提出了一种单阶段轨迹规划方法，该方法大幅减少了碰撞检测需求。首先，根据简单的参考路径（如车道中心线）生成初始 B-spline 轨迹；然后，计算控制点的障碍物排斥力；最后，将该问题构建为一个最优控制问题并求解，以获得最终轨迹。通过引入**障碍物碰撞解除机制**，我们减少了对碰撞检测的依赖，从而提升了计算效率。此外，单阶段优化框架具有更大的解空间，能够生成质量更高的轨迹。实验结果表明，与现有最先进的方法相比，该方法不仅规划速度更快，而且生成的轨迹质量更优。  


<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/driving/driving.mp4" type="video/mp4">
    </video>
</div>

## 实验效果

我们首先在[轻量级的仿真平台](/project/1-simulation)中搭建了行车对应的定向场景，主要包括避开静态障碍物，避开低速静态障碍物，加速超车，路中穿行，穿过狭窄道路共5种场景。

并在这些场景种，将我们的算法与**Lattice Planner**，**动态规划(DP)**，**时空A*算法**进行对比，获得了较好的效果，具体效果对比如下。

<img src="/images/figures/project/driving/results.png" alt="Driving Results" style="max-width:100%; height:auto;">

同时我们还将我们的方法何上述主流算法进行量化对比，主要包括规划时间，算法种碰撞检测次数，成功率，规划轨迹长度，平均位移以及安全性做了详细的对比。
<img src="/images/figures/project/driving/comparasion.jpeg" alt="Driving Results" style="max-width:100%; height:auto;">

