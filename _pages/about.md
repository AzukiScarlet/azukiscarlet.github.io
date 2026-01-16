---
permalink: /
title: "个人简介"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
---

**李想**，哈尔滨工业大学（深圳）机器人与先进制造学院在读研究生。2024年获得哈尔滨工业大学（深圳）自动化专业学士学位（导师：[李衍杰教授](https://faculty.hitsz.edu.cn/liyanjie)），2024年至今哈尔滨工业大学（深圳）控制科学与工程专业硕士研究生在读（导师：[李衍杰教授](https://faculty.hitsz.edu.cn/liyanjie)，[楼云江教授](https://faculty.hitsz.edu.cn/louyunjiang)）。研究方向为智能驾驶决策规划与控制，端到端的智能驾驶，模仿学习，强化学习等。机器人领域顶会IROS2025在投论文2篇。

**Xiang Li** is a master's student at the School of Robotics and Advanced Manufacturing, Harbin Institute of Technology, Shenzhen. He obtained his Bachelor's degree in Automation from Harbin Institute of Technology, Shenzhen, in 2024, under the supervision of [Prof. Yanjie Li](https://faculty.hitsz.edu.cn/liyanjie). Since 2024, he has been pursuing a Master's degree in Control Science and Engineering at the same institution, supervised by [Prof. Yanjie Li](https://faculty.hitsz.edu.cn/liyanjie) and [Prof. Yunjiang Lou](https://faculty.hitsz.edu.cn/louyunjiang). His research interests include decision-making, planning, and control for autonomous driving, end-to-end autonomous driving, and imitation learning. He has submitted two papers to IROS 2025, a top-tier conference in the field of robotics.

研究方向
--------

主要研究方向为智能驾驶决策规划与控制：

- **数值优化**：基于数值优化构建最优控制问题(OCP)进行智能驾驶轨迹规划
- **端到端与模仿学习**：基于模仿学习的智能驾驶端到端轨迹规划
- **车辆控制**：依照车辆动力学进行横纵解耦的轨迹跟踪控制

<iframe width="560" height="315" src="https://www.youtube.com/embed/hLDqkyEGJfs?si=KVpLa1_rGvbzfAA0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

技术栈
------

- **编程技能**：Python，C++11，ROS，百度Apollo框架，CARLA仿真框架，PyTorch，Bokeh，MATLAB，CAD，SolidWorks。
- **理论基础**：机器人学，汽车理论，强化学习，矩阵分析，最优化理论，数值分析，数理统计，自动控制，最优控制。
- **硬件水平**：具有百度 Apollo D-Kit Lite真车调试经验。

研究经历
--------

<div style="display: flex; align-items: flex-start; text-decoration: none; margin-bottom: 10px;">
    <img src='/images/figures/project/simulation/post.jpg' alt="Simulation Project" width="250" style="margin-right: 15px; border-radius: 8px;">
    <div style="display: flex; flex-direction: column;">
        <a href="/project/1-simulation" style="font-size: 18px; font-weight: bold; text-decoration: none; color: #0073e6;">
            面向决策与规划的轻量化自动驾驶仿真环境
        </a>
        <p style="margin: 5px 0 0; color: #555; font-size: 14px;">
            该项目基于交通流模型以及换道模型，在已开源的高精地图的基础上开发了一套自动驾驶交互式仿真环境ADPlan。实现了行车场景对交通参与者行为的仿真、交通信号灯的模拟，可有日志回访和交互式场景两大类仿真场景。此外，还包含各类定向行车场景，包括：避让前方低速或静止车辆、窄路行驶等。同时还实现了各类复杂的泊车场景。
        </p>
    </div>
</div>

<div style="display: flex; align-items: flex-start; text-decoration: none; margin-bottom: 10px;">
    <img src='/images/figures/project/parking/post.png' alt="Simulation Project" width="250" style="margin-right: 15px; border-radius: 8px;">
    <div style="display: flex; flex-direction: column;">
        <a href="/project/2-parking" style="font-size: 18px; font-weight: bold; text-decoration: none; color: #0073e6;">
            基于数值优化的复杂环境下泊车轨迹规划
        </a>
        <p style="margin: 5px 0 0; color: #555; font-size: 14px;">
            该项目针对复杂的甚至极限的待客泊车任务场景，基于环境评估的思想，充分将环境复杂度融入两阶段的时空联合的轨迹规划全过程。利用环境评估对混合A*算法进行改进，并构建了高效快速的轨迹优化方法。在城市复杂场景以及开放场景中的各类复杂场景中都能实现快速高效的泊车轨迹规划。该方法在轻量级自动驾驶仿真环境，CARLA仿真环境，apollo实车平台都进行了规划+控制的验证，证明方法的有效性和鲁棒性。
        </p>
    </div>
</div>

<div style="display: flex; align-items: flex-start; text-decoration: none; margin-bottom: 10px;">
    <img src='/images/figures/project/driving/post.png' alt="Simulation Project" width="250" style="margin-right: 15px; border-radius: 8px;">
    <div style="display: flex; flex-direction: column;">
        <a href="/project/3-driving" style="font-size: 18px; font-weight: bold; text-decoration: none; color: #0073e6;">
            基于数值优化的高效行车时空轨迹规划
        </a>
        <p style="margin: 5px 0 0; color: #555; font-size: 14px;">
            该项目基于数值优化并引入障碍物碰撞解除的机制，构建安全行车走廊，减少了对碰撞检测的依赖，从而提升了计算效率。以单次阶段优化的简洁框架在更大的解空间中搜索，得到质量更高的轨迹。在一些定向的行车场景中通过与Lattice-Planner，时空A*，动态规划等先进方法对比，这一方法求解速度更快，轨迹质量更高。
        </p>
    </div>
</div>

<div style="display: flex; align-items: flex-start; text-decoration: none; margin-bottom: 10px;">
    <img src='/images/figures/project/e2e/post.png' alt="Simulation Project" width="250" style="margin-right: 15px; border-radius: 8px;">
    <div style="display: flex; flex-direction: column;">
        <a href="/project/4-e2e" style="font-size: 18px; font-weight: bold; text-decoration: none; color: #0073e6;">
            多模态一站式端到端的泊车轨迹规划与控制
        </a>
        <p style="margin: 5px 0 0; color: #555; font-size: 14px;">
            该项目针对停车场泊车场景中的端到端快速轨迹规划，通过传统的轨迹规划算法和横纵解耦的MPC控制器生成大量的泊车数据。再利用端到端相关模仿学习结合残差强化学习的方式进行端到端的泊车轨迹规划与控制。提升了多模态传感器的融合能力和长时序的泊车任务中的策略鲁棒性。
        </p>
    </div>
</div>

<div style="display: flex; align-items: flex-start; text-decoration: none; margin-bottom: 10px;">
    <img src='/images/figures/project/diffphys/cover.png' alt="Simulation Project" width="250" style="margin-right: 15px; border-radius: 8px;">
    <div style="display: flex; flex-direction: column;">
        <a href="/project/5-diffphys" style="font-size: 18px; font-weight: bold; text-decoration: none; color: #0073e6;">
            端到端的地面全向配送车局部集群规划算法
        </a>
        <p style="margin: 5px 0 0; color: #555; font-size: 14px;">
            该项目基于可微物理仿真的端到端学习框架，进行Zero Shot的部署，实现了多台地面全向配送车的端到端集群局部路径规划算法，由激光雷达提供深度信息引导，自主完成避障抵达上层规划目标终点。完成了从SIL-PIL-REAL的测试闭环以及调度压力测试，动态协同避障测试等场景测试。
        </p>
    </div>
</div>




主要科研成果
------
- Xiang Li, Ke Lin, Xiaoqing Yang et al. “Flexible Trajectory Planning for Autonomous Vehicles via Environmental Assessment in Extreme Scenarios,” in 2026 IEEE International Conference on Robotics and Automation (ICRA2026 under review).
- Xiaoqing Yang, Ke Lin, Xiang Li, et al. “One-stage Trajectory Planning With Conflict-based Optimization for Autonomous Driving,” in 2025 IEEE/RSJ International Conference on Intelligent Robots and Systems.
<!-- - 专利在审 -->



<!-- **Markdown generator**

The repository includes [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the Academic Pages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring Academic Pages can be found in [the guide](https://academicpages.github.io/markdown/), the [growing wiki](https://github.com/academicpages/academicpages.github.io/wiki), and you can always [ask a question on GitHub](https://github.com/academicpages/academicpages.github.io/discussions). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful. -->
