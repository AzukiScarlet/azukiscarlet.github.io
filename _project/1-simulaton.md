---
title: "面向决策与规划的轻量化自动驾驶仿真环境"
excerpt: "针对行车和泊车的轻量级仿真环境<br/><img src='/images/figures/project/simulation/cover.png'>"
collection: project
---
## 项目简介

现有的很多自动驾驶仿真环境（例如 Carla, Apollo）都很复杂，感知、预测、决策、规划、控制全都有，这对于只做决策、规划和控制的人来说，是没必要的。而且现在车企的上车方案一定是感知与规划解耦的。另外，现有的仿真环境大概分类两派：一派主张采用 learning 的方法，采集了大量的行车数据和地图数据，想通过监督学习得到很好的规划器，这一派建立的仿真环境中道路非常复杂，因为是采集的真实道路信息，但是对其他交通参与者的模拟就很简单，采用的是日志回放的方案；而另一派，则通过研究交通流实现了交通参与者的交互式仿真，但一般用的道路都比较简单。可以认为，前者的优势是复杂的道路，而后者的优势是交互式的仿真。为了结合这两类仿真环境的优点，我们构建了一个新的仿真环境 ADPLAN。

这个环境的特点在于：只专注于自动驾驶中的决策、规划与控制，容易安装、非常轻量化；在复杂的道路中实现了交通参与者的交互式仿真；也支持日志回放的仿真；包含多个行车定向场景以及复杂泊车场景。整体仿真环境以[bokeh](https://bokeh.org.cn/)作为前端基础，后端数据驱动主要采用[nuplan数据集](https://www.nuscenes.org/nuplan)作为数据驱动。同时我们还构建了泊车和行车使用的定向场景。

## 日志回放仿真环境

日志回访环境直接以数据库的数据驱动，在仿真环境中作日志式回放。
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=707467429&bvid=BV17Q4y137HY&cid=1373315478&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=622465645&bvid=BV1jb4y1V7Y5&cid=1373315484&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=324879297&bvid=BV1Cw411x7tG&cid=1373315179&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=707414476&bvid=BV1DQ4y1g7Du&cid=1373315490&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

## 交互式仿真环境

交互式仿真环境要考虑自车与周围智能体进行交互，周围智能体同样以数据库的数据为基础，但额外引入了IDM模型作为交互控制。
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=664952676&bvid=BV1ka4y1r72f&cid=1373315445&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=622487745&bvid=BV1Gb4y1V7NY&cid=1373315451&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=237395688&bvid=BV1Qe411k7zW&cid=1373315454&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=409940622&bvid=BV1JG411Y7yy&cid=1373315171&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

## 行车定向场景

针对泊车，我们设计了五类定向场景包括狭窄道路通行、避让前方障碍物或静止车辆、避让前方低速车辆、普通行驶情况、换道加速超车。
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=452463555&bvid=BV1dj411n7dq&cid=1373315494&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=237412406&bvid=BV1ue411C77U&cid=1373315186&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=324879407&bvid=BV1Cw411x7FP&cid=1373315582&p=1" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>

## 泊车定向场景

针对复杂的泊车场景，主要是静态的场景，我们将其非为开放空间和城市空间两种，并在此基础上加入了随机生成泊车场景的功能。
<div class="grid-container" style="
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
  margin: 20px 0;
">
  <img src="/images/figures/project/simulation/par_1.jpg" loading="lazy">
  <img src="/images/figures/project/simulation/par_2.jpg" loading="lazy">
  <img src="/images/figures/project/simulation/par_3.jpg" loading="lazy">
  <img src="/images/figures/project/simulation/par_4.jpg" loading="lazy">
  <img src="/images/figures/project/simulation/par_5.jpg" loading="lazy">
  <img src="/images/figures/project/simulation/par_6.jpg" loading="lazy">
</div>

