---
title: "🫨最局域万尼尔函数与量子几何"
date: 2023-05-13T10:00:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Quantum Geometry", "Wannier Function", "Berry Phase"]
categories: ["Physics Notes"]
---

本note简述最大局域化Wannier函数（Maximally Localized Wannier Function）的规范选取问题，并讨论量子几何（Quantum Geometry）如何限制其局域程度。

<!--more-->

## Gauge Variance of Wannier Function

回顾Bloch定理：

$$
\hat{H}\left|\psi_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\psi_{n \mathbf{k}}\right\rangle
$$

对于Bloch Hamiltonian：

$$
\hat{H}(\mathbf{k}) = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} \hat{H} e^{-i \mathbf{k} \cdot \hat{\mathbf{r}}}
$$

$$
| \psi_{n \mathbf{k}} \rangle = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} | u_{n \mathbf{k}} \rangle
$$

$$
\hat{H}(\mathbf{k}) | u_{n \mathbf{k}} \rangle = \epsilon_n(\mathbf{k}) \left|u_{n \mathbf{k}}\right\rangle
$$

为了计算方便，我们有时会用似乎有局域性质的Wannier波函数来作为基底求解系统的本征态。

Wannier函数$|\mathbf{R} n\rangle$和Bloch波函数$\left|\psi_{n \mathbf{k}}\right\rangle$之间的转换关系：

$$
\left|\psi_{n \mathbf{k}}\right\rangle=\sum_{\mathbf{R}} e^{i \mathbf{k} \cdot \mathbf{R}}|\mathbf{R} n\rangle \Leftrightarrow |\mathbf{R} n\rangle=\frac{1}{N} \sum_{\mathbf{k}} e^{-i \mathbf{k} \cdot \mathbf{R}}\left|\psi_{n \mathbf{k}}\right\rangle
$$

不难想象，Bloch波函数$\left|\psi_{n \mathbf{k}}\right\rangle$在实空间是延展的，而Wannier函数$|\mathbf{R} n\rangle$是局域在$\mathbf{R}$附近的。

这些Wannier波函数并非系统的本征态，只不过是Bloch波函数的某种在实空间局域的线性组合，还与能带的规范选取有关。如果我们给Bloch波函数加上一个与$\mathbf{k}$有关的相位（规范），仍然是本征态。

$$
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|\psi_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{\psi}_{n \mathbf{k}}\right\rangle
$$

$$
\left|\tilde{u}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|u_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle
$$

不难想象，由于规范$e^{i \varphi_n(\mathbf{k})}$选取的任意性，Wannier波函数的局域性也会受影响，为此我们便有了寻找使得Wannier波函数最大局域化的规范的motivation。

## Vanderbilt's Spread Function

一般的固体物理教材会略去如何通过调节gauge使得Wannier函数达到最大局域化的相关内容，这事实上在能带论提出后几十年一直未完全被解决，相关内容可以参考Vanderbilt的1997年的PRB，“Maximally localized generalized Wannier functions for composite energy bands”：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847

以及2012年的RMP，“Maximally localized Wannier functions: Theory and applications”：

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419

值得一提的是，数值上寻找Maximally Localized Wannier Function对于提高第一性原理计算的效率十分重要，相关的理论在`wannier90`等程序中有重要应用。

简要介绍一下Vanderbilt的理论。首先我们需要定义Wannier函数的局域程度，我们不妨用其实空间分布的标准差来定义，即所谓的Spread Functional：

$$
\Omega=\left[\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\langle\mathbf{0} n|\mathbf{r}| \mathbf{0} n\rangle^2\right]=\left[\left\langle r^2\right\rangle_n-\overline{\mathbf{r}}_n^2\right]
$$

这个Spread Functional和规范选取有关，但可以分为规范不变$\Omega_{\mathrm{I}}$和与规范有关$\tilde{\Omega}$的两个部分：

$$
\Omega=\Omega_{\mathrm{I}}+\tilde{\Omega}
$$

其中，

$$
\Omega_{\mathrm{I}}=\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\sum_{\mathbf{R},m}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

$$
\tilde{\Omega}=\sum_{\mathbf{R} m \neq 0 n}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

事实上，与规范有关$\tilde{\Omega}$的部分是一个非负值，那么总有：

$$
\Omega \geq \Omega_{\mathrm{I}}
$$

Naively，我们希望调节规范使得$\tilde{\Omega}$尽量接近0；而Spread Functional规范不变的部分$\Omega_{\mathrm{I}}$则给出了Wannier函数局域程度的下界。

何以见得$\Omega_{\mathrm{I}}$规范不变？我们改写其形式：

$$
\Omega_{\mathrm{I}} =\sum_{\alpha}\left\langle 0 n\left|r_\alpha Q r_\alpha\right| 0 n\right\rangle=\sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right]
$$

其中，$P$为投影到所考察能带的投影算符：

$$
P =\frac{1}{N} \sum_{\mathbf{k}}\left|\psi_{n \mathbf{k}}\right\rangle\langle\psi_{n \mathbf{k}}|=\sum_{\mathbf{R}}| \mathbf{R} n\rangle\langle\mathbf{R} n|
$$

ket和bra正好抵消了gauge，从而$P$以及$Q=1-P$显然规范不变（能带投影算符不取决于显然规范选取）。

## Special Case in 1D

对于1D系统，我们确实可以使得，

$$
\Omega = \Omega_{\mathrm{I}}
$$

可以证明，Maximally Localized Wannier Function应当是坐标算符投影到该能带后的本征态，即$P\hat{x}P$的本征态。

$$
\langle R n|x| 0 n\rangle=\langle R n|PxP| 0 n\rangle=\bar{x}_{0 n} \delta_{R, 0}
$$

其中$\bar{x}_{0 n} = \langle 0 n|x| 0 n\rangle$为Wannier函数的中心位置，$P$为投影到能带n的投影算符。第一个等式成立的原因是，$| 0 n\rangle$, $| R n\rangle$也是能带n上本征态的叠加，故自然有：

$$
P| R n\rangle = | R n\rangle
$$

相应的结论可以推广到高维情形中，以3D为例，若要求$\Omega = \Omega_{\mathrm{I}}$，则Maximally Localized Wannier Function需要是$P\hat{x}P$，$P\hat{y}P$，$P\hat{z}P$的共同本征态。

然而，这一般不可能，Maximally Localized Wannier Function作为某一能带的完备基，若还要作为$P\hat{x}P$，$P\hat{y}P$，$P\hat{z}P$的共同本征态，则$P\hat{x}P$，$P\hat{y}P$，$P\hat{z}P$这些投影到该能带的坐标算符应当两两相互对易，未投影前这很容易成立，但投影后则不一定。

换句话说，若$P\hat{x}P$，$P\hat{y}P$，$P\hat{z}P$等投影坐标算符不对易，则Spread Functional没法最小化到0，也不可能有$\Omega_{min} = \Omega_{\mathrm{I}}$。但我们总可以把$\Omega_{\mathrm{I}}$这个规范不变量作为Wannier函数局域程度的下界。

由于1D系统的wannier函数很好求解（求$P\hat{x}P$的本征态），故分析电子在一维方向的波包运动十分有效。即使不是1D问题，我们总可以用partial wannier function，即只对一个方向作Fourier Transform的Wanner函数，

$$
|x,k_y, n\rangle=\frac{1}{N_x} \sum_{k_x} e^{-i k_x x}\left|\psi_{n,k_x,k_y}\right\rangle
$$

此时单单在这一个方向上，Maximally Localized (Partial) Wannier Function的延展范围（Spread Funcitional）可以达到最小值$\Omega_{min} = \Omega_{\mathrm{I}}$，这可以用来分析一个方向的电子极化问题。

## OBC v.s. PBC

值得一提的是，上述情况只在开边界条件（Open Boundary Condition, OBC）下成立，周期边界条件（Periodic Boundary Condition, PBC）的坐标算符没有良好的定义，事实上坐标的定义是多值的：

$$
x = x + mL, m \in \mathbb{Z}
$$

在PBC中我们会用Unitary Operator：$z = e^{i \frac{2\pi}{L} \hat{x}}$来定义坐标，现代的电极化理论以及拓扑能带论中的Topological Charge Pump理论才在此基础上建立，当然这都是后话了。

本note中我们先一律认为坐标算符是良定的，以便讨论物理意义。有时间之后再来进行PBC下的严谨讨论。

## Relation to Quantum Geometry

事实上，Wannier Function的局域程度还与系统的量子几何（Quantum Geometry）相关。关于量子几何可以考古我的note：

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

何以言之？我们先考察描述Wannier Function的局域程度的Spread Functional的形式：

$$
\Omega \sim \langle r_\mu r_\nu \rangle
$$

大致是坐标算符的关联函数，而在动量表象下坐标算符可以表示为动量偏导：

$$
r_\mu \sim \partial_{k_\mu}
$$

回忆Quantum Geometric Tensor的定义，正好包含了动量的二阶偏导：

$$
Q_{\mu\nu} \sim \langle \partial_{k_\mu} \partial_{k_\nu} \rangle
$$

故我们可以思考两者的关联。

更进一步我们考虑规范不变性问题，电磁场是规范不变性体现在不同规范的选取不影响场强，同理拓扑能带论中我们知道Bloch波函数的规范选取不会影响Berry Curvature（所以我们说Berry Curvature像是动量空间中的“磁场”），而Berry Curvature事实上是量子几何的一个反对称分量，事实上量子几何也是一个系统固有的规范不变的性质。

所以为了更合理的比较量子几何和Wannier Function的局域程度，我们将比较$Q_{\mu\nu}$与Spread Functional中的规范不变部分$\Omega_{\mathrm{I}}$之间的关系。

不难推导：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right] \\
& = \sum_\alpha \sum_k \langle \psi_{nk} | r_\alpha Q r_\alpha | \psi_{nk} \rangle \\
& = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle
\end{aligned}
$$

其中，

$$
\begin{aligned}
\langle \psi_{nk_1} | r_a | \psi_{mk_2} \rangle & \equiv \langle k_1, n | r_\alpha | k_2, m \rangle \\
& = \langle k_1,n |  r_a e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}}) |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle ) + i \langle u_{k_1}^n | e^{- i k_1 \cdot \hat{r}} e^{ i k_2 \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle \\
& = -i \langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) + i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle
\end{aligned}
$$

其中，

$$
\langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) \simeq \langle k_1,n | \left[ |k_2+\delta k_{2a}, m \rangle - |k_2-\delta k_{2a}, m \rangle \right]/2\delta k_{2a}
$$

而$|k_2 \pm \delta k_{2a}, m \rangle$，$|k_1, 1 \rangle$均为total Hamiltonian$\hat{H}$的本征态，故波函数正交。但是周期Bloch波函数则不一定，因为不同k属于不同Bloch Hamiltonian的本征态，不一定正交。

定义$I_{nm}(k_1,k_2) \equiv i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle$，在坐标表象下计算如下，其中用到了周期Bloch波函数$u_{k}^n (r)$的周期性质：

$$
u_{k}^n (r) = u_{k}^n (r + R),\, R = \sum_{i=1}^{d}n_i\vec{a_i}
$$

$$
\begin{aligned}
I_{nm}(k_1,k_2) & = i \int d^2 r \ u_{k_1}^n (r) e^{i(k_2 - k_1) \cdot r} \partial_{k_{2a}} u_{k_2}^m (r) \\
& = i \int d^2 r \ u_{k_1}^n (r + R) e^{i(k_2 - k_1) \cdot (r+R)} \partial_{k_{2a}} u_{k_2}^m (r+R) \\
& = i e^{i(k_2 - k_1) \cdot R} \int d^2 r \ u_{k_1}^n (r) e^{i(k_2 - k_1) \cdot r} \partial_{k_{2a}} u_{k_2}^m (r) \\
& = e^{i(k_2 - k_1) \cdot R} I_{nm}(k_1,k_2)
\end{aligned}
$$

可以将偏导看成差分：

$$\partial_{k_{2a}} u_{k_2}^\alpha (r) \simeq [u_{k_2 + \delta k_{2a}}^\alpha (r) - u_{k_2 - \delta k_{2a}}^\alpha (r)]/\delta k_{2a}$$

由于$u_{k_2 + \delta k_{2a}}^\alpha (r)$和$u_{k_2 - \delta k_{2a}}^\alpha (r)$均是周期函数（移动整数个元胞不变），从而 $\partial_{k_{2a}} u_{k_2}^\alpha (r)$也是周期函数：

$$ \partial_{k_{2a}} u_{k_2}^\alpha (r) = \partial_{k_{2a}} u_{k_2}^\alpha (r + R) $$

由于$I_{nm}(k_1,k_2)= e^{i(k_2 - k_1) \cdot R} I_{nm}(k_1,k_2)$，且$k_1,\,k_2 \in 1BZ$，故当且仅当$k_1 = k_2$时，$I(k_1, k_2)\neq 0$，从而我们只需要计算$k_1 = k_2$，即$k = k'$部分：

$$
\begin{aligned}
I_{nm}(k_1,k_2) & = \delta_{k_1,k_2} I_{nm}(k_1,k_1) \\
& = \delta_{k_1,k_2} \ i \int d^2 r \ u_{k_1}^n (r)  \partial_{k_{1a}} u_{k_1}^m (r) \\
& = \delta_{k_1,k_2} \ i \langle u_{k_1}^n | \partial_{k_{1a}} u_{k_1}^m \rangle 
\end{aligned}
$$

故，

$$
\langle \psi_{nk} | r_a | \psi_{mk'} \rangle = \delta_{k,k'} \ i \langle u_{k}^n | \partial_{k_{1a}} u_{k'}^m \rangle
$$

从而Wannier Function的Spread Functional的规范不变部分可以写成：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle\\
& = \sum_\alpha \sum_k \sum_{m \neq n} \langle \partial_{k_{\alpha}} u_{k}^n | u_{k}^m \rangle \langle  u_{k}^m | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle
\end{aligned}
$$

注意到求和部分正是定义在能带n上的Quantum Geometric Tensor的对角部分。也可以进一步写成：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \sum_{\alpha=1}^{d} \eta_{\alpha \alpha} (k) \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \operatorname{tr} g(k)
\end{aligned}
$$

由于Quantum Geometric Tensor是Hermitian matrix，可以分成Real Symmetric的Fubini-Study metric部分和Imaginary Anti-symmetric的Berry Curvature部分：

$$
\eta_{\mu\nu}(k) = g_{\mu\nu}(k) + i \frac{\epsilon_{\mu\nu}}{2}\mathcal{B} (k)
$$

显然最后一个等式用到了hermitian Matrix的diagonal为实数的性质，而Spread Functional显然也应该是实数。

此处$\operatorname{tr}$是对维度求trace$\sum_{\alpha=1}^{d}$，之前的则是对所有k展成的Hilbert空间求trace。

这样看来，quantum geometry的trace在布里渊区的积分，事实上给Wannier函数的局域化程度设置了一个下限。

$$
\Omega \geq \Omega_I \propto \int_{BZ} d^dk \operatorname{tr} g(k)
$$

对于2D系统，我们还有不等式：

$$ \operatorname{tr}g^\alpha (k) \geq |\mathcal{B} (k)| $$

而Berry Curvature在2D的布里渊区的积分便是Chern Number，则：

$$
\Omega \geq \Omega_I = \frac{V}{(2\pi)^d} \int_{BZ} d^dk \operatorname{tr} g(k) \geq \frac{V}{2\pi} |C|
$$

我们知道，对于Chern Insulator，一条能带（但是两条可以，所以见到的所有Chern Insulator Tight-Binding Model都是至少2-band model，且total Chern number = 0）是没法Wannierize的，最多在一个方向上localize，但这个不等式还是反映了，Chern number不为零的Chern Insulator的Wannier波函数比trivial Insulator更delocalize。

类似的，我们可以将所有动量空间几何量和实空间坐标期望值相关的物理量联系起来，例如Berry Connection内含动量的一阶偏导，说明它和坐标算符的期望值有关，这就对应了电子的极化（polarization）。

事实上，现代的电子极化理论是和Berry Connection同时期的产物，可以说人们搞清楚了动量空间的规范场才真正理解了看似简单的“极化”现象。

## Multiband Wannierization

紧束缚模型出了单带还能计算多带模型，因为考虑多带模型的自由度给了更大的规范选取自由度（Wannier Function可以由不同能带的Bloch Function组合而成）。

最直观的理解是，考虑自由电子，Bloch波函数是平面波（动量本征态），而用无限多的平面波（无限多的能带）便可以叠加出delta函数（坐标本征态），已经没有比这更Localize的基底了（相应的原胞内自由度也无限多）

$$
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle =\sum_{m=1}^J U_{m n}^{(\mathbf{k})}\left|\psi_{m \mathbf{k}}\right\rangle
$$

$$
|\mathbf{R} n\rangle =\frac{V}{(2 \pi)^3} \int_{\mathrm{BZ}} d \mathbf{k} e^{-i \mathbf{k} \cdot \mathbf{R}} \sum_{m=1}^J U_{m n}^{(\mathbf{k})}\left|\psi_{m \mathbf{k}}\right\rangle
$$

## Reference

- [Maximally localized Wannier functions: Theory and applications](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419)

- [Pseudopotential formalism for fractional Chern insulators](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.035101)

- [Maximally localized generalized Wannier functions for composite energy bands](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847)
