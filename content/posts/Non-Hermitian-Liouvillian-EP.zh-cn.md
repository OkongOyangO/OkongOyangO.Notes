---
title: "😈非厄米哈密顿量与Liouvillian超算符的能谱特征及例外点简介"
date: 2022-07-20T10:00:00+08:00
draft: false
math: true
tags: ["Non-Hermitian", "Exceptional Points", "Liouvillian", "Lindblad Equation", "Condensed Matter"]
categories: ["Physics Notes"]
---

本note主要介绍非厄米（Non-Hermitian）量子物理中两个核心概念：Lindblad主方程形式体系下的Liouvillian超算符，以及非厄米矩阵中特有的例外点（Exceptional Points, EP）的能谱特征。

<!--more-->

## Lindblad Master Equation Formalism & Liouvillian Superoperator

### Lindblad Master Equation

开放量子系统的密度矩阵演化可以由Lindblad主方程（Lindblad Master Equation, LME）描述：

$$
    \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L} \hat{\rho}(t)=-i[\hat{H}, \hat{\rho}(t)]+\sum_{\mu} \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)
$$

$$
    \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)=\hat{\Gamma}_{\mu} \hat{\rho}(t) \hat{\Gamma}_{\mu}^{\dagger}-\frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2} \hat{\rho}(t)-\hat{\rho}(t) \frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2}
$$

其中$\frac{1}{2}\{L_{k}^{\dagger} L_{k}, \rho\}$描述连续的anti-unitary部分，而$L_{k} \rho L_{k}^{\dagger}$描述导致不连续演化的quantum jump部分。这两项的结合保证了密度矩阵演化的trace-preserving性质。

LME的推导可以参考H. P. Breuer的《The Theory of Open Quantum Systems》或知乎上相关的介绍文章。

### 有效非厄米哈密顿量与量子轨迹诠释

短时演化可以由有效非厄米哈密顿量$H_{eff}$描述：

$$
    \hat{H}_{\mathrm{eff}}=\hat{H}-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2, \quad \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L}^{\prime} \hat{\rho}(t)=-i\left(\hat{H}_{\mathrm{eff}} \hat{\rho}(t)-\hat{\rho}(t) \hat{H}_{\mathrm{eff}}^{\dagger}\right)
$$

$H_{eff}$的非厄米性来源于系统与环境的耦合——耗散项$-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2$使得本征值带上虚部，虚部代表态的衰减速率。

### Liouvillian超算符的能谱

Liouvillian $\mathcal{L}$是一个超算符（superoperator），作用在密度矩阵空间上。通过向量化（vectorization）操作，可以将$N \times N$的密度矩阵映射为$N^2$维向量，$\mathcal{L}$则成为$N^2 \times N^2$矩阵。

Liouvillian的能谱$\{\lambda_i\}$一般是复数。其中至少存在一个稳态（steady state），对应$\lambda = 0$的本征态。多个稳态对应耗散相变（dissipative phase transition），这与EP的出现和对称性破缺密切相关。

Liouvillian gap定义为：

$$ \Delta = -\min(\operatorname{Re}(\lambda_i)) $$

描述了最慢衰减模式的弛豫时间。当$\Delta \to 0$时，系统出现临界慢化。

## 例外点（Exceptional Points）

### 什么是例外点？

厄米矩阵的本征值总是实数，且本征矢构成完备正交基。而非厄米矩阵的一个关键特征是：在某些参数值处，不仅本征值简并，本征矢也发生简并。这种点称为**例外点（Exceptional Point, EP）**。

在EP处，矩阵不再是可对角化的，而是约化为Jordan标准型。这与厄米系统中的简并点（Diabolic Point）有本质区别。

考虑一个简单的$2 \times 2$非厄米矩阵：

$$
H = \begin{pmatrix}
\epsilon & t \\
t & -\epsilon + i\gamma
\end{pmatrix}
$$

调节参数使本征值相等，即可找到EP。在EP附近，本征值以平方根形式劈裂：

$$ \Delta E \propto \sqrt{\lambda - \lambda_{EP}} $$

这与厄米系统中线性的能级排斥（$\Delta E \propto |\lambda - \lambda_0|$）形成鲜明对比。

### EP附近的暂态动力学：跨LEP的阻尼振子类比

跨Liouvillian Exceptional Point（LEP）的暂态动力学类似于经典阻尼振子从过阻尼到临界阻尼再到欠阻尼的转变。

调节系统参数从LEP一侧到另一侧：
- LEP一侧：系统趋于稳态的过程呈现振荡衰减（"欠阻尼"）
- LEP处：临界阻尼
- LEP另一侧：无振荡的指数衰减（"过阻尼"）

这可以通过Liouvillian本征值虚部的行为来理解——EP处本征值从纯实数变为复数。

### EP附近的手性态转移

让系统参数绕EP绝热演化一圈，系统末态取决于绕行方向（顺时针/逆时针），而非保持在初始本征态。这一现象称为**手性态转移（Chiral State Transfer）**或**非对称模式转换（Asymmetric Mode Transfer）**。

这与厄米系统中的绝热定理形成鲜明对比：在厄米系统中，如果演化足够缓慢，系统始终保持在瞬时本征态上（除了Berry phase因子）。而在非厄米系统中，绕EP一圈后，系统必然跳到另一个本征态上。

手性态转移是非厄米拓扑中一个活跃的研究方向，在波导耦合、光学微腔等实验平台中均有观测。

## 总结

非厄米量子物理通过Lindblad主方程描述了开放量子系统的动力学，有效非厄米哈密顿量自然引入了复本征值。例外点（EP）是非厄米系统独有的谱奇点，其附近的物理——从阻尼振子暂态过程到手性态转移——在经典和量子系统中均有丰富的实验实现。
