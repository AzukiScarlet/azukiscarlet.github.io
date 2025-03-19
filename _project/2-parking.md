---
title: "基于数值优化的复杂环境下泊车轨迹规划"
excerpt: "针对复杂的极限环境下的泊车轨迹规划<br/>
  <img src='/images/figures/project/parking/OpenSpace19.png' style='width: 48%; min-width: 250px; height: auto'>
  <img src='/images/figures/project/parking/OpenSpace20.png' style='width: 48%; min-width: 250px; height: auto'>
  <img src='/images/figures/project/parking/Urban_Complex_Space5.png' style='width: 48%; min-width: 250px; height: auto'>
  <img src='/images/figures/project/parking/Urban_Complex_Space8.png' style='width: 48%; min-width: 250px; height: auto'>
"
collection: project
---
## 项目简介

>  "Trajectory Planning for Autonomous Driving through Environmental Assessment: Achieving Flexible Parking in Extreme Scenarios," in  2025 IEEE/RSJ International Conference on Intelligent Robots and Systems(IROS)(Under Review).

我们研究了自动代客泊车（AVP）任务场景的复杂环境下的泊车轨迹规划问题，针对不规则、非凸障碍物场景，提出了一种基于环境评估的两阶段泊车轨迹规划方法。第一阶段计算停车场景的复杂度，并改进 Hybrid A* 算法生成初始轨迹。第二阶段将轨迹优化建模为最优控制问题，根据环境复杂度调整轨迹，生成最终优化的泊车轨迹。相比其他方法，该方法在复杂场景中计算速度快，成功率高。实验在 22 个开放场景、11 个城市场景和 124 个随机泊车场景中验证，并在 CARLA 仿真和真实车辆上测试。

<iframe width="560" height="315" src="https://www.youtube.com/embed/mb3_W8PnnWk?si=komb0BwtIv83fRiv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 轻量级仿真效果

<iframe src="/images/figures/project/parking/OpenSpace_output_20.html" width="820" height="620"></iframe>
<iframe src="/images/figures/project/parking/Urban_Complex_Space_output_5.html" width="820" height="620"></iframe>


## CARLA仿真效果

## Apollo平台效果
