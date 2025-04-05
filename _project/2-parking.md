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

>  "Trajectory Planning for Autonomous Driving through Environmental Assessment: Achieving Flexible Parking in Extreme Scenarios," in  2025 IEEE/RSJ International Conference on Intelligent Robots and Systems(IROS2025 under review).

我们研究了自动代客泊车（AVP）任务场景的复杂环境下的泊车轨迹规划问题，针对不规则、非凸障碍物场景，提出了一种基于环境评估的两阶段泊车轨迹规划方法。第一阶段计算停车场景的复杂度，并改进 Hybrid A* 算法生成初始轨迹。第二阶段将轨迹优化建模为最优控制问题，根据环境复杂度调整轨迹，生成最终优化的泊车轨迹。相比其他方法，该方法在复杂场景中计算速度快，成功率高。实验在 22 个开放场景、11 个城市场景和 124 个随机泊车场景中验证，并在 CARLA 仿真和真实车辆上测试。

<iframe width="560" height="315" src="https://www.youtube.com/embed/mb3_W8PnnWk?si=komb0BwtIv83fRiv" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## 轻量级规划平台仿真效果

我们首先在[轻量级的仿真平台](/project/1-simulation)中搭建了复杂的泊车场景用以验证我们的算法，一些场景展示如下，可以拖动滑条查看泊车效果。

<iframe src="/images/figures/project/parking/OpenSpace19_video.html" width="820" height="620"></iframe>
<iframe src="/images/figures/project/parking/OpenSpace20_video.html" width="820" height="620"></iframe>
<iframe src="/images/figures/project/parking/Urban_Complex_Space8_video.html" width="820" height="620"></iframe>
<iframe src="/images/figures/project/parking/Urban_Complex_Space5_video.html" width="820" height="620"></iframe>

## CARLA仿真效果

随后我们在更加真实的CARLA仿真平台验证算法规划轨迹的可控性，在模型不精确的情况下对我们的时空解耦的规划轨迹做横纵解耦的控制，纵向速度和横向控制采用MPC控制。

<!-- <img src="/images/figures/project/parking/video.png" alt="CARLA 仿真效果" style="width: 50%; height: auto; display: block; margin: auto;"> -->

<!-- <div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; justify-items: center;">
    <video src="/images/figures/project/parking/v1.mp4" controls width="320"></video>
    <video src="/images/figures/project/parking/v2.mp4" controls width="320"></video>
    <video src="/images/figures/project/parking/v3.mp4" controls width="320"></video>
</div> -->

<div style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 10px; justify-items: center;">
  <video controls width="320">
    <source src="/images/figures/project/parking/v1.webm" type="video/webm">
  </video>
  <video controls width="320">
    <source src="/images/figures/project/parking/v2.webm" type="video/webm">
  </video>
  <video controls width="320">
    <source src="/images/figures/project/parking/v3.webm" type="video/webm">
  </video>
</div>

## Apollo平台效果

最后我们将我们的规划算法在Apollo平台的apollo-dev-dkit设备进行sim2real的实际无人驾驶车辆的验证。针对感知数据进行滚动规划。同时以100hz的频率对自车进行横纵解耦的控制跟踪规划轨迹。其中纵向控制采用PID控制，横向控制采用LQR控制。

<div style="display: flex; justify-content: center;">
    <video controls style="max-width: 100%; height: auto;">
        <source src="/images/figures/project/parking/apollo.webm" type="video/webm">
    </video>
</div>

