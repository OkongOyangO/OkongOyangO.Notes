---
title: "😅同龄人都沉迷高数量子古埃及，而我却只想地球毁灭怎么办？"
date: 2026-06-30T21:00:00+08:00
draft: false
math: true
tags: ["Planetary Physics", "Centrifugal Force", "Gravitational Binding", "Roche Limit", "Popular Science"]
categories: ["Physics Notes"]
---

旋转坐标系中，离心力有使物体远离旋转轴的趋势。那么能否仅在普物范围内构建一个toy model来算一算地球转多快可以毁灭呢？本文构建了一个可以用物理竞赛知识计算的简易模型——Luoxi极限。

<!--more-->

## 模型描述

真空环境中的一自转星体。假设星体形状由原半径为$R$的均匀球体变为**均匀的短轴旋转椭球体**，短轴方向即自转轴方向。星体为密度不变、总体积不变的匀质流体。

![Image](https://pic4.zhimg.com/80/v2-351e3e048a5d82e96e21957e1073c45b.png)

一般星体由星际尘埃相互碰撞结合形成稳定的引力束缚体，由于整个过程角动量守恒，最终形成的星体必然有一定的自转角速度。引力与自转的作用将使星体在自转轴方向变扁——地球便有赤道半径大、两极半径小的特征。

## 计算离心势能

设星体自转角速度为$\omega$，离心率为$e$，密度为$\rho$。

dV微元的离心势能为$-\frac{1}{2}\rho \cdot dV\omega^{2}(x^{2} + y^{2})$。

利用椭球体积分公式：

$$\int_{\Omega} x^{2} \mathrm{dV} = \frac{4\pi}{15}a^{3}bc$$

积分范围为一般椭球体$\{(x,y,z):\frac{x^{2}}{a^{2}} + \frac{y^{2}}{b^{2}} + \frac{z^{2}}{c^{2}} \leq 1\}$。

可得离心势能：

$$W_{s} = -\frac{4\pi}{15}\rho\omega^{2}a^{4}b$$

体积不变约束：

$$\frac{4\pi}{3}R^{3} = \frac{4\pi}{3}a^{2}b = \frac{4\pi}{3}a^{3}\sqrt{1 - e^{2}}$$

$$\Rightarrow \quad a = R(1 - e^{2})^{-1/6}$$

则：

$$W_{s} = -\frac{4\pi}{15}\rho\omega^{2}R^{5}(1 - e^{2})^{-1/3}$$

## 引力自能的计算

均匀旋转椭球体的引力自能：

$$W_{g} = -\frac{3}{5}\frac{GM^{2}}{R}f(e)$$

其中$f(e)$为椭球形状因子（离心率$e$的函数），$f(0)=1$对应球体。

当$e \ll 1$时（地球离心率约0.0034）：

$$f(e) \approx 1 - \frac{2}{15}e^{2} + \mathcal{O}(e^{4})$$

## Luoxi极限

系统的总机械能：

$$E_{total} = W_{s} + W_{g} + \frac{1}{2}I\omega^{2}$$

其中$\frac{1}{2}I\omega^{2}$为转动动能，$I = \frac{2}{5}MR^{2}$为转动惯量（球近似）。

星体稳定的条件是$E_{total}$作为$e$的函数在$e=0$处有极小值：

$$\left. \frac{\partial^{2} E_{total}}{\partial e^{2}} \right|_{e=0} \geq 0$$

计算得到临界自转角速度：

$$\omega_{c} \approx \sqrt{\frac{4\pi}{5}G\rho}$$

联系到星体表面的逃逸条件，星体表面的物质受到的离心力等于引力时：

$$\omega^{2}R \approx \frac{GM}{R^{2}} = \frac{4\pi}{3}G\rho R$$

$$\Rightarrow \quad \omega_{c} \approx \sqrt{\frac{4\pi}{3}G\rho}$$

比较两者——量级一致！这说明星体在外层物质离心力大于引力时确实会发生解体。

## 地球毁灭时间

带入地球参数：$\rho \approx 5.5 \times 10^{3}$ kg/m³，$G = 6.67 \times 10^{-11}$。

$$\omega_{c} \approx \sqrt{\frac{4\pi}{3} \times 6.67 \times 10^{-11} \times 5.5 \times 10^{3}} \approx 1.24 \times 10^{-3} \text{ rad/s}$$

临界周期：

$$T_{c} = \frac{2\pi}{\omega_{c}} \approx 1.4 \text{ hours}$$

地球当前自转周期为24小时。所以——只要地球自转加速约**17倍**（约1.4小时一圈），地表物质就会被甩出去。

> 结论：短期内地球不会因自转过快而毁灭。同学们可以安心参加小升博资格考了。
