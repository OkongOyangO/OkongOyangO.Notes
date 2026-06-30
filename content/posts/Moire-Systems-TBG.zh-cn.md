---
title: "🫠转角石墨烯平带与Moire Physics｜魔角条件的连续模型推导"
date: 2024-01-01T10:00:00+08:00
draft: false
math: true
tags: ["Twisted Bilayer Graphene", "Moire Physics", "Magic Angle", "BM Continuum Model", "Flat Band"]
categories: ["Physics Notes"]
---

2018年曹原大神一篇Nature给我们送来了转角石墨烯（Twisted Bilayer Graphene, TBG）。本文回顾转角石墨烯的BM连续模型构建，分析平带形成的物理机理，并理论推导魔角条件$\theta \approx 1.1^\circ$。

<!--more-->

## 为什么是转角学（Twistronics）？

转角体系的可调控性及其衍生出的平带强关联物理使其成为近年来凝聚态物理的热点。Rafi Bistritzer 和 Allan H. MacDonald 2011年发表的"Moiré bands in twisted double-layer graphene"（BM连续模型）对魔角的出现做出了准确的理论预言。

https://www.pnas.org/doi/10.1073/pnas.1108174108

理论方面，Bernevig等人对BM连续模型从准确性、对称性、单体多体性质等方面做了详尽的解析和计算分析，发表了长达200页的"TBG六部曲"。实验上，转角TMD等体系也被一一实现。

### 平带的意义

能带带宽$W$反映电子的单体动能。平带意味着：

$$ U \gg W $$

其中$U \sim e^2/a_M$为电子相互作用能量量级，$a_M$为moire晶格常数。在平带体系中，电子动能几乎为零，相互作用主导——强关联物理由此涌现。

## BM连续模型

### 单层石墨烯的Dirac锥

单层石墨烯的低能有效模型为：

$$ H_{SLG}(\mathbf{k}) = \hbar v_F \mathbf{k} \cdot \boldsymbol{\sigma} $$

在K点附近形成线性色散的Dirac锥。双层石墨烯由两层堆叠，通过层间耦合相互作用。

### 转角引入的moire超晶格

将顶层石墨烯旋转小角度$\theta$后，两层石墨烯的BZ也发生相对旋转：

$$ \mathbf{K}_t = R(\theta/2) \mathbf{K}, \quad \mathbf{K}_b = R(-\theta/2) \mathbf{K} $$

moire超晶格的倒格矢为：

$$ \mathbf{G}_i^M = \mathbf{G}_i^{(t)} - \mathbf{G}_i^{(b)} $$

moire晶格常数：

$$ a_M = \frac{a}{2\sin(\theta/2)} \approx \frac{a}{\theta} $$

$\theta = 1.1^\circ$时，$a_M \approx 13$ nm，比石墨烯原胞大约50倍。

### BM模型的矩阵结构

BM连续模型在动量空间中是一个无穷维矩阵，基底为两层的Dirac锥在moire倒格矢$\mathbf{G}_i^M$处的复制品。对于低能物理，保留最低的几个moire倒格矢即可获得收敛的结果。

单层Hamiltonian的矩阵元：

$$ [H_{SLG}]_{\mathbf{G},\mathbf{G}'} = \hbar v_F (\mathbf{k} + \mathbf{G}) \cdot \boldsymbol{\sigma} \delta_{\mathbf{G},\mathbf{G}'} $$

层间耦合项（tunneling）：

$$ T_{\mathbf{G}} = \begin{pmatrix} w_0 & w_1 e^{-i\psi} \\ w_1 e^{i\psi} & w_0 \end{pmatrix} $$

其中$w_0$为AA堆叠的层间耦合，$w_1$为AB堆叠的层间耦合。

### Tripod模型与魔角

最简单保持收敛性的截断是Tripod模型——保留K_M Dirac锥加上三个最近的moire倒格矢。这给出一个$8\times 8$的有效Hamiltonian。

在chiral极限（$w_0 = 0$）下，BM模型具有粒子-空穴对称性，平带在魔角处精确出现。魔角条件为：

$$ \alpha = \frac{w_1}{\hbar v_F k_\theta} = \alpha_c \approx 0.586 $$

其中$k_\theta = 2K\sin(\theta/2)$。由此可得：

$$ \theta \approx \frac{3w_1}{\hbar v_F K} \approx 1.05^\circ $$

### 重正化费米速度

BM模型的核心预言是：随着转角的减小，Dirac锥的费米速度被层间耦合重正化：

$$ v_F^* = v_F \frac{1 - 3\alpha^2}{1 + 3\alpha^2} $$

当$\alpha = 1/\sqrt{3}$时，$v_F^* = 0$——这标志着魔角的出现。重正化费米速度为0意味着Dirac色散变成平带。

### 拓扑性质

TBG魔角平带具有非平庸的拓扑性质。每个valley中两个平带总Chern数为0，但每个平带可被约化为$C = \pm 1$。平带与最低Landau能级之间存在形式上的对应关系——"vortexability"判据统一了描述理想FCI平带的几何条件。

## 连续模型的对称性

BM模型具有丰富的对称性：
- $C_{3z}$：三重旋转对称性
- $C_{2z}\mathcal{T}$：自旋less时间反演
- 粒子-空穴对称性（chiral极限下）
- $U(1)$谷守恒（小角度下）

在chiral极限外（$w_0 \neq 0$），粒子-空穴对称性被破坏，但平带依然稳定存在，说明拓扑保护机制在起作用。

## 总结

转角石墨烯的BM连续模型成功预言了魔角平带的出现，其物理本质是层间耦合对Dirac费米速度的重正化。moire超晶格将微米尺度的复杂体系约化为有效的低能模型，为理解转角体系中的强关联现象（超导、关联绝缘态等）奠定了基础。
