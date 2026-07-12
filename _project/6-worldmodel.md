---
title: "基于潜在世界模型在线评估的多模态轨迹规划"
excerpt: "融合模仿学习、强化微调与潜在世界模型的多模态轨迹规划<br/><img src='/images/figures/project/worldmodel/cover.png'>"
collection: project
---

## 项目简介

> “REALM: Reinforcement Fine-Tuning with Latent World Model Based Online Evaluation for Multimodal Planning,” submitted to the 2026 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS 2026).

该项目面向复杂交通环境中的多模态轨迹规划问题，提出了 REALM 框架。方法首先利用模仿学习高效生成多条候选轨迹，再通过闭环强化学习微调提升轨迹的安全性、通行效率和舒适性。针对传统评分器难以判断周围车辆如何响应不同候选轨迹的问题，框架引入潜在世界模型，为每条候选轨迹并行推演对应的未来场景状态，并通过多目标评估器选择最终轨迹。

## 方法流程

REALM 主要包含多模态轨迹生成器、策略优化器、潜在世界模型和轨迹评估器四个部分。轨迹生成器输出不同横向意图与纵向进度组合的候选轨迹；策略优化器利用闭环模拟奖励进行组内相对策略优化；潜在世界模型根据每条固定候选轨迹推演未来环境状态；评估器综合无碰撞、可行驶区域、碰撞时间、舒适性和行驶进度完成在线排序。

<div style="text-align: center; margin: 20px 0;">
  <img src="/images/figures/project/worldmodel/pipeline.png" alt="REALM 方法流程" style="max-width: 100%; height: auto; border-radius: 8px;">
</div>

## 实验展示

以下视频展示了 REALM 在提前避障、紧急响应、变道超车和行人交互等场景中的规划效果，以及不同模块配置下的结果对比。

<div style="display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 18px; margin: 20px 0;">
  <figure style="margin: 0;">
    <video controls playsinline preload="metadata" style="width: 100%; height: auto; border-radius: 8px;">
      <source src="/images/figures/project/worldmodel/avoidance_in_time.mp4" type="video/mp4">
    </video>
    <figcaption style="text-align: center; color: #666; font-size: 14px;">提前感知风险并及时避障</figcaption>
  </figure>

  <figure style="margin: 0;">
    <video controls playsinline preload="metadata" style="width: 100%; height: auto; border-radius: 8px;">
      <source src="/images/figures/project/worldmodel/emergency_response.mp4" type="video/mp4">
    </video>
    <figcaption style="text-align: center; color: #666; font-size: 14px;">紧急交通场景响应</figcaption>
  </figure>

  <figure style="margin: 0;">
    <video controls playsinline preload="metadata" style="width: 100%; height: auto; border-radius: 8px;">
      <source src="/images/figures/project/worldmodel/lane_change_overtake.mp4" type="video/mp4">
    </video>
    <figcaption style="text-align: center; color: #666; font-size: 14px;">变道超车轨迹规划</figcaption>
  </figure>

  <figure style="margin: 0;">
    <video controls playsinline preload="metadata" style="width: 100%; height: auto; border-radius: 8px;">
      <source src="/images/figures/project/worldmodel/pass_pedestrian.mp4" type="video/mp4">
    </video>
    <figcaption style="text-align: center; color: #666; font-size: 14px;">行人交互场景通行</figcaption>
  </figure>

  <figure style="margin: 0;">
    <video controls playsinline preload="metadata" style="width: 100%; height: auto; border-radius: 8px;">
      <source src="/images/figures/project/worldmodel/Ablation_result.mp4" type="video/mp4">
    </video>
    <figcaption style="text-align: center; color: #666; font-size: 14px;">不同模块配置的结果对比</figcaption>
  </figure>
</div>
