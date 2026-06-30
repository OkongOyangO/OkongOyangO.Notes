---
title: "🥴安德森局域化（Anderson Localization）"
date: 2026-06-30T18:00:00+08:00
draft: false
math: true
tags: ["Anderson Localization", "Disorder", "Metal-Insulator Transition", "Condensed Matter"]
categories: ["Physics Notes"]
---

1958年P. W. Anderson在其开创性论文中提出了无序系统中的局域化现象：足够强的无序会使电子波函数从延展态变为指数局域态，导致系统从导体转变为绝缘体。这一发现开启了长达半个多世纪的局域化研究，并与金属-绝缘体相变（MIT）紧密相连。

<!--more-->

## Anderson局域化的基本物理图像

在完美的周期晶格中，Bloch定理保证了电子波函数为延展的平面波。无序的引入破坏了平移对称性，电子受到杂质势的多次散射。Anderson提出的关键问题是：**波函数在多次散射后是否仍保持延展？**

答案是：**取决于无序强度和维度**。

+ **强无序**：无论维度$d$为多少，波函数都会局域化——指数衰减。
+ **弱无序**：在$d=1,2$中，任意弱的无序都导致局域化；$d=3$中需要无序超过临界值才发生局域化。

波函数的局域化形式为：

$$ |\psi(\mathbf{r})| \sim e^{-|\mathbf{r}-\mathbf{r}_0|/\xi} $$

其中$\xi$为局域化长度。在相变临界点处，$\xi$发散：

$$ \xi \sim |E - E_c|^{-\nu} $$

## Anderson紧束缚模型

Anderson考虑了一个紧束缚模型，在位能取随机分布：

$$ H = -t \sum_{\langle ij\rangle} c_i^\dagger c_j + \sum_i \epsilon_i c_i^\dagger c_i $$

其中$\epsilon_i$为随机在位能，通常取均匀分布$\epsilon_i \in [-W/2, W/2]$。无量纲参数$W/t$表征无序强度。

对于三维系统，当$W/t$超过临界值$(W/t)_c$时，费米能级处的所有态都变为局域态——发生Anderson相变。

## 标度理论（Scaling Theory）

"Gang of Four"（Abrahams, Anderson, Licciardello, Ramakrishnan, 1979）提出的标度理论是描述Anderson局域化的里程碑。核心思想是用无量纲电导$g$作为标度变量：

$$ g = \frac{G}{e^2/h} $$

标度函数$\beta(g) = d\ln g / d\ln L$的行为：

+ **$d=1$**：$\beta(g) < 0$对所有$g$成立 → 所有态局域化，无真正金属态
+ **$d=2$**：$\beta(g) \leq 0$ → 无真正金属-绝缘体相变（但有争议），弱无序下为弱局域化
+ **$d=3$**：$\beta(g)$存在不稳定的不动点$g_c$ → $g > g_c$流向金属态，$g < g_c$流向绝缘态

## 弱局域化（Weak Localization）

在弱无序金属态中（$g \gg g_c$），量子干涉效应导致电导的对数修正（$d=2$）：

$$ \Delta \sigma = -\frac{e^2}{2\pi^2\hbar} \ln\left(\frac{\tau_\phi}{\tau}\right) $$

其中$\tau_\phi$为退相干时间，$\tau$为弹性散射时间。

弱局域化的物理本质是：电子在扩散路径上与其时间反演路径的量子干涉增强了返回原点的概率，从而降低了电导。外加磁场可破坏时间反演对称性，消除弱局域化——这是**反弱局域化**（weak anti-localization）的来源，也是自旋-轨道耦合系统的特征。

## 维度与局域化

### $d=1$：完全局域化

一维系统中任意弱无序都导致局域化。局域化长度$\xi$与平均自由程$l$有简单关系：$\xi \sim l$。

### $d=2$：标度理论的预言

二维是边际维度（marginal dimension）。弱局域化导致电阻率对数温度依赖性。是否存在真正的金属-绝缘体相变仍有一些微妙之处（与自旋-轨道耦合、电子-电子相互作用等有关）。

### $d=3$：Anderson相变

三维系统存在真正的Anderson相变。迁移率边（mobility edge）$E_c$将延展态（$E > E_c$）与局域态（$E < E_c$）分开。当费米能级穿越$E_c$时，系统发生金属-绝缘体相变。

## Anderson局域化与多体局域化（MBL）

Anderson局域化是无相互作用系统中的单粒子效应。当加入电子-电子相互作用后，局域化能否存活？答案是：在某些条件下可以——这称为**多体局域化**（Many-Body Localization, MBL）。

MBL的关键特征：
+ 系统不热化——破坏本征态热化假说（ETH）
+ 纠缠熵从面积律变为对数增长（$S \sim \ln t$）
+ 存在 emergent integrability 和 l-bits 描述

MBL是当前凝聚态和量子信息交叉领域的研究热点。

## 实验观测

Anderson局域化的实验证据包括：
+ 掺杂半导体中的金属-绝缘体相变
+ 低温下二维电子气的弱局域化（磁阻中的负磁阻）
+ 冷原子气体中的Anderson局域化（2008年首次直接观测）
+ 光子晶体、声学超材料中的经典波局域化

## 总结

Anderson局域化是量子波在无序介质中的基本现象，揭示了量子干涉效应对输运性质的决定性影响。标度理论提供了统一的维度依赖描述，弱局域化和多体局域化则进一步拓展了这一基本物理图像的内涵。
