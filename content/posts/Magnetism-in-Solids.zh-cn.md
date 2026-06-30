---
title: "😊固体磁性"
date: 2026-06-30T14:00:00+08:00
draft: false
math: true
tags: ["Magnetism", "Solid State Physics", "Paramagnetism", "Ferromagnetism", "Condensed Matter"]
categories: ["Physics Notes"]
---

固体磁性是固体物理中一个重要的部分，主要研究晶体等固体在外磁场$B$作用下，内部的磁化强度$\mathcal{M} = \frac{\Sigma \mathbb{m}}{V}$，以及磁化率$\chi = \frac{\mu_0 \mathcal{M}}{B}$等性质。

<!--more-->

## 磁性的分类

### 单原子（离子）磁矩效应（$\chi$较小）

仅考虑一个原子（离子）磁矩，忽略磁矩之间的作用，其磁性质可分为顺磁性和抗磁性。无磁场的基态是磁矩杂乱排布。

+ **顺磁性** $\chi > 0$。电子自旋、轨道角动量等在外场下倾向于朝着$B$方向排列，产生顺磁性。

+ **抗磁性** $\chi < 0$。感生磁矩则倾向于与$B$反向，产生抗磁性。

### 多原子（离子）效应（$\chi$较大且奇异）

铁磁性等更显著的磁性质需要考虑磁矩相互作用。此时基态为磁矩有序的排布，简单的有同向排布，复杂的有spin chiral等。

+ **铁磁性**。磁矩相互作用使得磁矩趋于平行排布，有顺磁-铁磁相变，可用居里-外斯定律描述：
  $T < T_c$，有自发磁化，$B = 0$，$M \neq 0$，铁磁态；
  $T > T_c$，$\chi = \frac{C}{T - T_c}$，顺磁态。

+ **反铁磁性**。磁矩相互作用使得磁矩趋于反平行排布，有顺磁-反铁磁相变，可用奈耳定律描述：
  $T < T_c$，有自发反平行排布；
  $T > T_c$，$\chi = \frac{C}{T + T_N}$，顺磁态。

+ **亚铁磁性**。反平行但磁矩未完全抵消的磁有序。

## 固体磁性的历史与量子力学基础

固体磁性的研究可以追溯到量子力学问世以前。Langevin通过永久dipole假设给出了顺磁性的解释，但永久dipole这一假设本身与经典力学相矛盾；而且，经典的热平衡态不允许系统整体显示磁性。

这些矛盾直到量子力学问世才被解决。量子力学使得永久磁矩模型可以依靠粒子内禀自旋、定态的轨道角动量等得以存在，对基态（平衡态）能量的分析也能很好地解释感生磁矩的效应。

### 原子磁矩的来源

原子磁矩主要来自三个方面：

1. **电子自旋磁矩**。电子的内禀自旋$s = 1/2$产生磁矩$\boldsymbol{\mu}_s = -g_s \mu_B \mathbf{s}$，其中$g_s \approx 2$，$\mu_B = e\hbar/2m_e$为Bohr磁子。

2. **电子轨道磁矩**。电子绕核的轨道角动量$\mathbf{l}$产生磁矩$\boldsymbol{\mu}_l = -\mu_B \mathbf{l}$。

3. **核自旋磁矩**。核自旋也产生磁矩，但核磁子$\mu_N \ll \mu_B$，通常可以忽略。

### Hund规则

对于多电子原子，基态的电子排布由Hund规则决定：

1. **第一Hund规则**：总自旋$S$取最大值（自旋尽可能平行）。
2. **第二Hund规则**：在满足第一规则的前提下，总轨道角动量$L$取最大值。
3. **第三Hund规则**：考虑自旋-轨道耦合后，壳层不到半满时$J = |L-S|$，超过半满时$J = L+S$。

## 顺磁性与Brillouin函数

考虑一个总角动量为$J$的原子在外磁场$B$中，其Hamiltonian为：

$$ \hat{H} = - \boldsymbol{\mu} \cdot \mathbf{B} = g_J \mu_B \mathbf{J} \cdot \mathbf{B} $$

其中$g_J$为Landé g因子：

$$ g_J = 1 + \frac{J(J+1) + S(S+1) - L(L+1)}{2J(J+1)} $$

配分函数为：

$$ Z = \sum_{m_J=-J}^{J} e^{g_J \mu_B m_J B / k_B T} = \frac{\sinh\left[(2J+1)x/2\right]}{\sinh(x/2)} $$

其中$x = g_J \mu_B B / k_B T$。由此可得磁化强度：

$$ M = n g_J \mu_B J B_J(x) $$

其中$B_J(x)$为Brillouin函数：

$$ B_J(x) = \frac{2J+1}{2J}\coth\left(\frac{2J+1}{2J}x\right) - \frac{1}{2J}\coth\left(\frac{x}{2J}\right) $$

在高温弱场极限下（$x \ll 1$），展开$B_J(x) \approx \frac{J+1}{3J}x$，得到居里定律：

$$ \chi = \frac{n \mu_0 (g_J \mu_B)^2 J(J+1)}{3k_B T} = \frac{C}{T} $$

## 铁磁性与Weiss分子场理论

Weiss提出铁磁体中存在一个"分子场"（molecular field），正比于磁化强度：

$$ \mathbf{B}_{eff} = \mathbf{B}_{ext} + \lambda \mu_0 \mathbf{M} $$

其中$\lambda$为分子场常数。将$B_{eff}$代入Brillouin函数，自洽方程变为：

$$ M = n g_J \mu_B J B_J\left(\frac{g_J \mu_B J (B_{ext} + \lambda \mu_0 M)}{k_B T}\right) $$

当$B_{ext} = 0$时，在$T < T_c$下存在非零解，即自发磁化。居里温度由下式给出：

$$ T_c = \frac{n \lambda \mu_0 (g_J \mu_B)^2 J(J+1)}{3k_B} $$

在$T > T_c$时，$\chi$满足居里-外斯定律：

$$ \chi = \frac{C}{T - T_c} $$

## 反铁磁性与自旋波

反铁磁体的序参量是staggered magnetization $\mathbf{M}_s = \mathbf{M}_A - \mathbf{M}_B$，其中$A$和$B$是两套子晶格。在$T = 0$时，$\mathbf{M}_s$取最大值；随温度升高，热涨落激发自旋波（magnon），$\mathbf{M}_s$减小。

自旋波的色散关系在长波极限下为：

$$ \omega_k \propto k^2 \quad \text{（铁磁体）} $$
$$ \omega_k \propto k \quad \text{（反铁磁体）} $$

低温下磁化强度与温度的关系为Bloch $T^{3/2}$定律：

$$ M(T) = M(0) \left[1 - \alpha \left(\frac{T}{T_c}\right)^{3/2}\right] $$

## 总结

固体磁性从单离子效应（顺磁性、抗磁性）到集体效应（铁磁性、反铁磁性），其理论经历了从经典Langevin模型到Weiss分子场理论，再到量子力学基础上的自旋波理论的发展过程。现代磁性研究中，拓扑自旋结构（skyrmion等）、frustrated magnetism、量子自旋液体等是前沿热点。
