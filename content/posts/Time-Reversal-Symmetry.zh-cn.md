---
title: "😌一个哈密顿量，究竟有没有TRS的？"
date: 2021-11-17T10:00:00+08:00
draft: false
math: true
tags: ["Time-Reversal Symmetry", "Topological Insulator", "Kramers Degeneracy", "Condensed Matter"]
categories: ["Physics Notes"]
---

时间反演对称性在TI学习里太common了以至于经常出现下述情况：第一页觉得结论很trivial，第二页就不知道结论从哪来的。本文系统地梳理了时间反演对称性（TRS）在量子力学和能带论中的具体表现形式。

<!--more-->

## 无自旋粒子的TRS

时间反演操作$\Theta$在无自旋（spinless）系统中的作用即为复共轭：

$$ \Theta = K $$

其中$K$为复共轭算符。对于无自旋粒子的哈密顿量，TRS要求：

$$ \Theta H \Theta^{-1} = H \quad \Leftrightarrow \quad H^* = H $$

即哈密顿量矩阵元全为实数。对于Bloch Hamiltonian，这意味着：

$$ H(-\mathbf{k}) = H^*(\mathbf{k}) $$

## 有自旋粒子的TRS

对于自旋$1/2$粒子，时间反演算符为：

$$ \Theta = -i \sigma_y K $$

其中$\sigma_y$为Pauli矩阵。关键性质：

$$ \Theta^2 = -1 $$

这一性质导致了著名的**Kramers简并**：在TRS下，每个本征态至少二重简并。

证明：若$|\psi\rangle$为$H$的本征态，则$\Theta|\psi\rangle$也是$H$的本征态且与$|\psi\rangle$正交：

$$ \langle \psi | \Theta \psi \rangle = \langle \Theta^2 \psi | \Theta \psi \rangle^* = -\langle \psi | \Theta \psi \rangle^* = 0 $$

## 固体能带中的TRS

在Bloch能带论中，TRS要求：

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

这给出了能带关于$k=0$的镜像对称性：$E_n(\mathbf{k}) = E_n(-\mathbf{k})$。

### 时间反演不变动量（TRIM）

在BZ中，满足$-\mathbf{k} = \mathbf{k} + \mathbf{G}$的动量点称为TRIM（Time-Reversal Invariant Momentum）。在2D正方晶格中有4个TRIM，3D中有8个。这些点上：

$$ H(\Gamma_i) = \Theta H(\Gamma_i) \Theta^{-1} $$

确保Kramers简并成立。

### 布里渊区中的Berry曲率约束

TRS对Berry曲率施加了约束：

$$ F(-\mathbf{k}) = -F(\mathbf{k}) $$

这意味着在TRIM处Berry曲率为0（因为$F(\Gamma_i) = -F(\Gamma_i)$）。因此TRS系统的Chern number必然为0——TRS系统不能是Chern绝缘体。

## TRS哈密顿量的构建方法

判断一个哈密顿量是否具有TRS，可以按以下步骤：

1. **写出时间反演算符的形式**：根据系统是否含自旋确定$\Theta$

2. **对Bloch Hamiltonian施加TRS条件**：

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

3. **展开为Pauli矩阵形式**。以二能带系统为例：

$$ H(\mathbf{k}) = d_0(\mathbf{k}) \sigma_0 + \mathbf{d}(\mathbf{k}) \cdot \boldsymbol{\sigma} $$

TRS要求约束$d_i(\mathbf{k})$的对称性。对于spinless系统（$\Theta = K$）：

$$ \sigma_x \sigma_0 \sigma_x = \sigma_0 = \sigma_0^* $$
$$ \sigma_x \sigma_x \sigma_x = \sigma_x = \sigma_x^* $$
$$ \sigma_x \sigma_y \sigma_x = -\sigma_y = \sigma_y^* $$
$$ \sigma_x \sigma_z \sigma_x = -\sigma_z $$

从而$d_y(\mathbf{k})$必须为0，$d_x, d_z$为偶函数。

4. **结合其它对称性**。例如联合$C_{2z}\mathcal{T}$对称性在非互易输运中也有重要应用。

## 自旋-轨道耦合中的TRS

在有自旋-轨道耦合的系统中，TRS表现为能带的自旋简并。Dresselhaus和Rashba自旋-轨道耦合都是TRS的（它们由结构反演不对称性产生，不破坏TRS）。

TRS和反演对称性（IS）共存时，每个k点每个能带都是二重简并的（自旋简并）。这是因为$\mathcal{P}\Theta$组合对称性（$\mathcal{P}\Theta^2 = -1$）保证local Kramers degeneracy。

## 总结

TRS是拓扑分类的三种基本对称性之一（与PHS、CS并列）。识别一个系统是否具有TRS，以及TRS带来的能带约束（Kramers简并、Berry曲率为奇函数、TRIM处的简并），是学习拓扑绝缘体和其他SPT相的基础。
