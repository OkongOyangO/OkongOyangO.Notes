---
title: "😬KT相变note｜二维XY模型、拓扑涡旋与准长程序"
date: 2022-07-08T11:00:00+08:00
draft: false
math: true
tags: ["KT Transition", "XY Model", "Topological Defect", "Vortex", "Condensed Matter"]
categories: ["Physics Notes"]
---

KT相变（Kosterlitz-Thouless Transition）是二维系统中一种独特的拓扑相变。与传统相变不同，它不依赖于自发对称破缺，而是由拓扑缺陷——涡旋（vortex）的束缚-解束缚过程驱动。本文从二维XY模型出发，阐述KT相变的基本原理。

<!--more-->

## KT相变的原理

### 二维XY模型

在二维XY模型中，每个格点被赋予一个二维自旋$S_i=(\cos \theta_i,\sin \theta_i)$。正方晶格上的作用量为：

$$S[\theta]=-J\sum_{\braket{ij}}S_i \cdot S_j=-J\sum_{\braket{ij}}\cos(\theta_i-\theta_j)$$

下面分别计算高温和低温下的关联函数。

**高温**（$J\ll 1$）：将配分函数关于$J$展开：

$$
Z=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)e^{-S[\theta]}=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)\prod_{\braket{ij}}\left[1+J\cos(\theta_i-\theta_j)+O(J^2)\right]
$$

关联函数$\braket{S_0\cdot S_x}=\braket{\cos(\theta_0-\theta_x)}\sim e^{-f(J)|x|}$，即短程序。

**低温**（$J\gg 1$）：$\theta$的变化平缓，可取连续近似：

$$S[\theta]\rightarrow \frac{J}{2}\int \mathrm{d}^2 x\left[\nabla\theta(x)\right]^2$$

计算得到关联函数$\braket{S_0\cdot S_x}\sim x^{-g(J)}$，即准长程序（algebraic order）。

因此二维XY模型在有限温度存在一个从短程到准长程序的相变。这一相变无法用传统Landau理论描述——它由拓扑缺陷vortex的凝聚驱动。

## Vortex激发及其凝聚

### 拓扑缺陷与vortex

考虑连续场$\vec{u}(r)=\nabla \theta(r)$。由于$\theta$的$U(1)$结构（$\theta \equiv \theta + 2n\pi$），环路积分：

$$\oint \vec{u}\cdot \vec{\mathrm{d}l}=2n\pi \quad n\in \mathbb{Z}$$

该结果是离散的，在路径连续变化时不变。对于trivial态（$\theta$为常数），环路积分为0。引入拓扑缺陷后，$\nabla\theta$在缺陷处无定义：

$$\nabla \times \vec{u}(\vec{r})=2n\pi \delta^2(\vec{r}-\vec{r_0})\hat{e}_z$$

vortex携带拓扑荷$n$，其速度场为：

$$\vec{v}(\vec{r};\vec{r}_0,n)= \frac{n}{|\vec{r}-\vec{r}_0|}\left(\hat{e}_z\times \frac{\vec{r}-\vec{r}_0}{|\vec{r}-\vec{r}_0|}\right)$$

### Vortex的自由能

考虑一个位于原点、荷为$n=1$的vortex：

$$S_{\text{vor}}=S_{\text{core}}+\frac{J}{2}\int_0^{2\pi}\mathrm{d}\psi \int_a^L \rho\mathrm{d}\rho \,\vec{u}^2(\rho,\psi)=S_{\text{core}}+\pi J \ln\left(\frac{L}{a}\right)$$

配分函数：

$$Z_{\text{vor}}/Z_0\approx \left(\frac{L}{a}\right)^2 e^{-S_{\text{core}}-\pi J\ln(L/a)}=\exp(-S_{\text{core}}+(2-\pi J)\ln(L/a))$$

vortex的自由能：

$$F_{\text{vor}}\sim S_{\text{core}}+(\pi J-2)\ln(L/a)$$

当$\pi J > 2$时，$\ln L$系数为正，单vortex自由能趋于无穷——vortex被禁闭。当$\pi J < 2$时，vortex自由能为负——vortex可以自发产生。临界点出现在$\pi J = 2$，即$J_c = 2/\pi$。

### Vortex之间的相互作用

两个分别带荷$n_1, n_2$的vortex之间的相互作用能为：

$$V_{int} = -2\pi J n_1 n_2 \ln\left(\frac{|\vec{r}_1-\vec{r}_2|}{a}\right)$$

异号vortex相互吸引（对数势），同号vortex相互排斥。在低温下，正负vortex形成束缚对，体系维持准长程序；在高温下，vortex对解束缚形成vortex等离子体，体系变为无序。

## KT相变的实验验证：二维超导薄膜

实验通过$\mathrm{Hg}-\mathrm{Xe}$合金高薄层电阻均质薄膜检验了KT相变。

二维超导中的vortex-反vortex对的束缚-解束缚直接对应XY模型中的KT相变理论。实验通过测量$I-V$特性间接反映涡流-反涡流相互作用。在$T_c$附近的$V(I)$的详细分析与涡旋相互作用的空间重整化理论预测提供了合理的一致性。

$\log-\log$图上斜率$a(T)$是对数相互作用的前因子量度。通过外推$a(T_{c0})=1$和取$a(T_c)=3$来确定vortex解束缚温度$T_c$。有效介电常数$\epsilon_c = n_s^0 / n_s^R = 1.2 \pm 0.1$与理论预期一致。

## 总结

KT相变是一种纯粹的拓扑相变，不伴随对称性自发破缺。其本质是二维系统中vortex-反vortex对的束缚-解束缚过程。低温为准长程序（algebraic order），高温为无序相。KT理论不仅适用于二维XY磁性系统，也适用于二维超导薄膜、二维液晶等广泛体系。
