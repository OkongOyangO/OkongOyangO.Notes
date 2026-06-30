---
title: "🤪 体边对应：Dirac 方程、Wilson Loop 与纠缠谱"
date: 2026-06-29T18:00:00+08:00
draft: false
math: true
tags: ["Topological Insulator", "Bulk-Boundary Correspondence", "Wilson Loop", "Entanglement Spectrum", "Dirac Equation", "Condensed Matter"]
categories: ["Physics Notes"]
---

本note旨在讨论拓扑能带论中的体边对应（Bulk-Boundary Correspondence, BBC），包括其色散关系及其在实空间中的局域行为的数值验证，以及用 Dirac 方程、Wilson Loop、Entanglement Spectrum 等形式体系的严格证明。

<!--more-->

## Bulk-Edge Correspondence (BEC)

初学拓扑能带论时，我们往往被告知一些重要但subtle的结论，其中拓扑态的"体边对应"（Bulk-Edge Correspondence, BEC, or Bulk-Boundary Correspondence, BBC）便是很重要的一例：我们往往被告知，拓扑绝缘体/陈绝缘体有着绝缘（Gapped）的体态，却有着导电（Gapless）的边缘态，这些边缘态很robust，不会被杂质gap掉，且其个数（有时up to modula 2，有时整数）由体态的拓扑不变量决定。相关内容可考古我以前的一些鬼话：

## Numerical Verification

这个结论是如此的广为流传，以至于我们常挂在嘴边但并不知道其严格推导。我们常常做的是退一步，通过紧束缚模型+精确对角化来验证其正确性。这里推荐一篇介绍kwant包的文章：例如，有能隙的体态性质往往用无boundary的周期边界条件（Periodic Boundary Condition, PBC）的紧束缚模型精确对角化后得到的能带图来验证。

![typical 2D band structure](/posts/bulk-boundary-correspondence/fig01_typical_2d_band.png)

*typical 2D band structure*

无能隙的边缘态则是通过人为在某一方向取开边界条件（Open Boundary Condition, OBC），再对垂直于该方向的好量子数（垂直该方向的动量$k_{\perp}$）对应的经过dimensional reduction的能带图来验证。

![edge state spectrum with OBC](/posts/bulk-boundary-correspondence/fig02_edge_state_spectrum_OBC.png)

*edge state spectrum with OBC*

其robustness可以靠在取开边界的方向上加入disorder观察边缘态色散关系的gaplessness验证，边缘态在实空间中运动方向可以靠观察边缘态的群速度$v = \frac{\partial \epsilon(k)}{\hbar \partial k}$来确定。值得一提的是$C=1$的边缘只有1个单向运动的边缘态（Chiral Edge State），但我们数值模拟时不可避免的要取两个边界（半开边界半无界没法数值对角化），此时会有群速度相反的两个边缘态出现，分别对应两个边界的运动，两者没有任何对称性关联因为2D Chern Insulator属于10 fold classification的A类，本身也没有任何对称性。相比之下，拓扑绝缘体的边界会有1对（或奇数对由time reversal相联系的边界态），数值计算时在一个方向开两个边界则会有两对群速度相反的两个边缘态出现，其中由time reversal相联系的边界态色散关系关于$k=0$是对称的。

![Edge state](/posts/bulk-boundary-correspondence/fig03_edge_state.png)

*Edge state*

## Why Strict Derivation？

这些数值结果终究只能是验证而非严格推导，体边对应作为拓扑能带论最重要的结论之一当然容易记忆，但更严格的审视这一结论的理论推导也更有利于我们对体边对应的理解。同时，严格证明体边对应过程中用到的工具，例如Dirac Equation，Wilson Loop等Formalism，在计算HOTI的体边对应、边缘态等进一步衍生出的拓扑性质时也十分有用，理解其physical origin不可谓不重要。

## Dirac Equation

topological phase transition与gap closing同时发生，这个过程可以用mass随参数变化的Dirac Fermion来描述。先来考虑BHZ model：

$$
H(k_x,k_y;u) = \sin k_x \sigma_x + \sin k_y \sigma_y + (u+\cos k_x + \cos k_y) \sigma_z
$$

其中u为缓变参数，在$u<-2$时系统为trivial insulator，$-2<u<0$时为陈数$C=-1$的Chern insulator，在这个过程中发生了topological phase transition，原因是$(k_x,k_y)=(0,0)$处发生了gap closing。

![Topological phase transition with inverted Dirac fermion mass](/posts/bulk-boundary-correspondence/fig04_topo_transition_dirac_mass.png)

*Topological phase transition with inverted Dirac fermion mass*

取$u\approx-2, (k_x,k_y)\approx(0,0)$，在topological transition point附近的Bloch Hamiltonian与(2+1)D Dirac Fermion相同：

$$
H(k_x,k_y;m) \approx k_x \sigma_x + k_y \sigma_y + m \sigma_z \quad m \equiv u + \cos k_x + \cos k_y \approx u+2
$$

例如从trivial insulator到topological/chern insulator的转变便可以用mass的变化来体现band inversion的过程。拓扑绝缘体的边界附近也可以看成发生了这种band inversion的过程，即形如Dirac fermion的低能激发发生了能带反转。考虑$x=0$处的边界，$x<0$为体系内部，$x>0$为外部（真空，可以看成trivial insulator）。将x看成调控系统的缓变参数，m(x)则在边界附近发生了质量反号：

$$
m(x)>0: x<0 \quad m(x)<0: x>0
$$

只要变化足够缓慢，每个x附近总有一段足够大的bulk以形成稳定的Bloch Hamiltonian $H(k_x,k_y;m)$，而不用考虑$\partial_x m(x)$带来的效应。即系统随x的变化是"绝热"的。不难发现，由于我们只关心低能物理（gap closing）上述的讨论对其他任意模型都成立。下面来求解边界态在实空间的分布，将哈密顿量换到实空间$k_x \rightarrow -i \partial_x$，y方向我们假设仍有平移对称性，即$k_y$仍是好量子数，这样得到的partially Fourier Transformed Hamiltonian为：

$$
H(x,k_y) = -i \sigma_x \partial_x + k_y \sigma_y + m(x) \sigma_z
$$

这正对应了dimensional reduction操作后的Hamiltonian的低能行为，求解其本征态本征能谱便能得到边界态及其能谱。对于$H(x,k_y = 0) = -i \sigma_x \partial_x + m(x) \sigma_z$较好求解，其本征方程为：

$$
-i \sigma_x \partial_x \Psi_{k_y=0} (x) = - m(x) \sigma_z \Psi_{k_y=0} (x)
$$

其中$\Psi_{k_y=0} (x)$为一个二分量函数，因为$\sigma_i$为$2\times 2$矩阵。

$$
\Rightarrow \partial_x \Psi_{k_y=0} (x) = - m(x) \sigma_y \Psi_{k_y=0} (x)
$$

则$\Psi_{k_y=0} (x)$必须得是$\sigma_y$的本征态，可以写成：

$$
\Psi_{k_y=0}^{\sigma_y = \pm 1} (x) = \psi_{k_y=0}^{\sigma_y = \pm 1} (x) \left(\begin{array}{c}1 \\ \pm i\end{array}\right)
$$

其中$\psi_{k_y=0} (x)$为普通函数，满足：

$$
\partial_x \psi_{k_y=0}^{\sigma_y = \pm 1} (x) = \mp m(x) \psi_{k_y=0}^{\sigma_y = \pm 1} (x)
$$

$$
\Rightarrow \psi_{k_y=0}^{\sigma_y = \pm 1} (x) \propto e^{ \mp \int^x m(x) dx }
$$

由于$m(x)>0$: $x<0$，$m(x)<0$: $x>0$，只有$\sigma = -1$是normalizable的，故解为：

$$
\Psi_{k_y=0} (x) = e^{ - \int^x m(x) dx} \left(\begin{array}{c}1 \\ -i\end{array}\right)
$$

本征值为$E(k_y = 0) = 0$。不难发现$k_y \neq 0$时，$\Psi_{k_y=0} (x) = e^{ - \int^x m(x) dx} \left(\begin{array}{c}1 \\ i\end{array}\right)$也是解，此时能量为：

$$
E(k_y) = k_y
$$

这便给出了低能的边缘态的色散关系，与我们描述的gapless的边缘态相同，且群速度朝+y方向，确实是沿着边界走的edge state，符合我们之前关于体边对应的statement。

![Real space localization and boundary spectrum](/posts/bulk-boundary-correspondence/fig05_realspace_localization_boundary_spectrum.png)

*Real space localization and boundary spectrum*

再观察波函数在实空间的分布，不难发现$\Psi_{k_y=0} (x) \propto e^{ - \int^x m(x) dx}$是局域在$x=0$附近的波包，最简单的验证方法就是代入$m(x) = -\alpha x$，将得到一个局域在$x=0$的高斯波包，而y方向的分布则是延展的平面波；或者取$m(x) = \left\{\begin{array}{l}m_1>0,&\,x<0 \\ -m_2<0,&\,x>0\end{array} \right.$，结果也是局域的波包。

![Localized Edge State](/posts/bulk-boundary-correspondence/fig06_localized_edge_state.png)

*Localized Edge State*

这对于其他拓扑绝缘体仍然成立，因为在边界处总会发生topological phase transition，那么我们用massive Dirac fermion with inversed mass描述的低能行为总是universal的。这比起数值上对体边对应的验证更加严谨。更详细的内容可以在Qingrui Wang老师的网课中找到讲解，这里不再赘述；

### Exact Solution

@人生玄学提供了一篇严格解拓扑边缘态的文章，可以参考：

Edge states and the bulk-boundary correspondence in Dirac Hamiltonians

## Wilson Loop

一方面，Wilson Loop反映拓扑系统的体态性质；另一方面，Wilson Loop Spectrum与边缘态的色散关系拓扑等价。综上，Wilson Loop既与拓扑系统的体态性质有关，又与边缘态性质相关，自然是用于证明拓扑物态体边对应的不二之选。关于Wilson Loop，知乎上也有很多dl写了很多很好的文章/回答，这里列一些链接：下面，我们来引入拓扑能带论中的Wilson Loop Formalism，并讨论其与体态性质、边缘态性质的联系。

### Wilson Loop and Bulk: Wannierization

Wilson Loop反映拓扑系统的体态性质，这是因为Wilson Loop Spectrum本质上计算的是系统（某一方向）Wannier Center随（垂直方向）动量的变化关系。电子占据的Wannier state在实空间的移动反映了系统的极化、输运等性质，这些都是凝聚态物理学家们研究拓扑物态时倍加关注的性质。例如一维的拓扑SSH Chain有quantized polarization，二维的Chern insulator有quantized Hall Conductance，它们都与拓扑系统体态的拓扑不变量相关，例如陈数为C的Chern Band贡献$\sigma_{xy} = C \frac{e^2}{h}$的电导。而y方向的电场对应$k_y$的变化，若x方向的Wannier Center正好移动了一个晶格常数，这相当于在x方向运输了一个电子，这样我们就能通过Wilson Loop Spectrum读出系统的拓扑不变量等体态性质。

### Wilson Loop and charge pump

![Wilson Loop and charge pump](/posts/bulk-boundary-correspondence/fig07_wilson_loop_charge_pump.png)

*Wilson Loop and charge pump*

Wilson Loop Formalism最初的提出是因为Xi Dai等人在寻找一种更方便的数值方法来计算拓扑不变量。Bloch波函数的数值求解不难，但若直接用Bloch波函数求解Berry Connection、Berry Curvature，需要数值上规定gauge，但拓扑不变量作为一个gauge invariant的量，计算过程中人为规定gauge显得繁琐，且数值计算出的波函数相位一般是混乱的，很难得到连续的gauge。于是Xi Dai等人从电子波函数在实空间中的pump过程得到启发，得到了与通过Berry Connection、Berry Curvature积分得到的拓扑不变量等价的表达式，这便是Wilson Loop Formalism的起源。

<https://journals.aps.org/prb/abstract/10.1103/PhysRevB.84.075119>

该文章最初用于计算没有inversion symmetry的time-reversal invariant topological insulator的$\mathbb{Z}_2$ index，但其"描述电子波函数在实空间中的pump过程"的motivation可以应用到Chern Insulator乃至其他拓扑绝缘体中，Wilson Loop Formalism同时也是Modern Polarization Theory的进一步发展的结果。考虑紧束缚模型的Hamiltonian：

$$
H=\sum_{\alpha \beta} \sum_{i j} h_{i j}^{\alpha \beta}|\alpha i\rangle\langle\beta j|+ h.c.
$$

其本征态为Bloch波函数：

$$
\left|\Psi_{n \mathbf{k}}\right\rangle=\sum_\alpha g_{n \alpha}(\mathbf{k})|\alpha \mathbf{k}\rangle
$$

其中，$|\alpha \mathbf{k}\rangle$为atomic orbital的Bloch sum：

$$
|\alpha \mathbf{k}\rangle=\frac{1}{\sqrt{N_{cell}}} \sum_i|\alpha i\rangle e^{i \mathbf{k} \cdot \mathbf{R}_i}
$$

定义$|n, \mathbf{k}\rangle$为Bloch波函数的周期部分：

$$
|n, \mathbf{k}\rangle=e^{-i \mathbf{k} \cdot \mathbf{r}}\left|\Psi_{n \mathbf{k}}\right\rangle
$$

我们一般把它看成k参数调控的波函数，用它来求Berry Connection、Berry Curvature：

$$
[\mathbf{A}(\mathbf{k})]_{mn} = i \langle m, \mathbf{k} | \nabla_{\mathbf{k}} | n, \mathbf{k} \rangle \quad [A_i(\mathbf{k})]_{mn} = i \langle m, \mathbf{k} | \partial_{k_i} | n, \mathbf{k} \rangle \quad [F_{ij}(\mathbf{k})]_{mn} = [\partial_{k_i}A_j(\mathbf{k})]_{mn} - [\partial_{k_j}A_i(\mathbf{k})]_{mn}
$$

此处我们将Berry Connection、Berry Curvature写成了更general的multiband形式，其中i，j index表示分量，m，n为band index。为了计算某一方向的（Maximally Localized）Wannier Function，我们利用以下结论：某一方向的1D Maximally Localized Wannier Function（MLWF）是该方向坐标算符$\hat{x_i}$投影到对应band子空间后的投影算符$P\hat{x_i}P$的本征态，其本征值为Wannier Center的问题，这样Wilson Loop Formalism的motivation中计算Wannier Center Evolution的问题便转化为求解某一考察方向的投影坐标算符$P\hat{x_i}P$的本征值问题。关于这个结论为何成立可以考古我关于最局域万尼尔函数（Maximally Localized Wannier Function）的note：不过这里要考虑OBC和PBC两种边界条件的问题，在开边界条件下，我们很容易定义坐标算符$\hat{x}$：

$$
\hat{x} =\sum_{i \alpha} (R_i + r_{\alpha})|\alpha i\rangle\langle\alpha i|
$$

在边界趋于无穷远时有：

$$
\hat{x}=\sum_{i \alpha} R_i|\alpha i\rangle\langle\alpha i|=i \frac{\partial}{\partial k_x}
$$

其中$R_i$为原胞i距离原点的位置，$r_\alpha$为sublattice/orbital $\alpha$距离原胞中心的距离。为讨论方便，之后若未特别提及，我们令$r_\alpha = 0$。而体态性质一般在PBC下求解，但PBC下的坐标算符$\hat{x}$不好定义，此时我们用下面的算符来定义坐标：

$$
\hat{X}=\sum_{i \alpha} e^{-i \delta k_x \cdot \mathbf{R}_i}|\alpha i\rangle\langle\alpha i|
$$

此时算符的本征值是$N_x$个$U(1)$ phase $e^{-i \delta k_x \cdot \mathbf{R}_i}$，其坐标$\mathbf{R}_i$被encode在本征值的相位中。由于$\delta k_x \equiv \frac{2 \pi}{N_x a_x}$，所以第1个和第$N_x+1$个原胞的相位（坐标）相同（在$\bmod 2\pi$的意义下）。虽然此时"坐标算符"的本征值的相位才有坐标的物理含义，我们姑且还是将$\hat{X}$叫做"坐标算符"，因为此时$\hat{x}$ is ill defined。换句话说，现在坐标变成了一个多值函数，因为在周期边条件下，$R_i$与$R_i+N_x a_x$是同一个坐标。不失一般性地，我们考虑2维系统，且假设我们只在x方向作Fourier变换得到localize在x方向的partial Wannier function，则y方向的$k_y$仍是好量子数，即可以考虑同一个$k_y$下的子空间内的Wannier局域化以及MLWF的求解问题。固定$k_y$，我们考虑要投影的band subspace，即选取几条我们关心的能带，考虑其对应的电子波函数在实空间中x方向上的行为。对每个$k_y$都这么做就可以求出对应的x localized Wannier function随$k_y$的演化行为，若给系统y方向加上电场使得$k_y$移动，则上述求解的演化行为就能告诉我们系统加y方向电场后电子在x方向的运动行为，这正是Topological/Chern Insulators关心的。这种先block diagonalize各个$k_y$的行为与我们求解能带时利用Bloch Theorem是完全相同的（严格来说因为$k_x$方向变成了我们要对角化的矩阵指标，不再像是"好量子数"，这更像求解边edge state spectrum），我们之后会把"x localized Wannier function随$k_y$的演化行为"称为"Wilson Loop Spectrum"。固定$k_y$，投影算符为：

$$
\hat{P}_{k_y}=\sum_{n \in o, k_x}\left|\Psi_{n \mathbf{k}}\right\rangle\left\langle\Psi_{n \mathbf{k}}\right|
$$

n为band index，o为我们要project的band set，不妨假设要投影到M个band上。投影后的坐标算符：

$$
\begin{aligned}
\hat{X}_P\left(k_y\right)&=\hat{P}_{k_y} \hat{X} \hat{P}_{k_y} \\
&=\sum_{n m \in o} \sum_{k_x k_x^{\prime}, i \alpha} e^{-i \delta k_x \cdot \mathbf{R}_i}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{n k_x, k_y}\right| \\
&\times|\alpha i\rangle\left\langle\alpha i \mid \Psi_{m k_x^{\prime}, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&=\sum_{n m \in o} \sum_{k_x k_x^{\prime}, i} \frac{1}{N_{cell}} e^{i\left(k_x+\delta k_x-k_x^{\prime}\right) \cdot \mathbf{R}_i}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&\times\left[\sum_\alpha g_{n \alpha}^*\left(k_x\right) g_{m \alpha}\left(k_x^{\prime}\right)\right] \\
&=\sum_{k_x k_x^{\prime}} \delta\left(k_x+\delta k_x-k_x^{\prime}\right) \sum_{n m \in o}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&\times\left[\sum_\alpha g_{n \alpha}^*\left(k_x\right) g_{m \alpha}\left(k_x^{\prime}\right)\right]
\end{aligned}
$$

由于$\delta\left(k_x+\delta k_x-k_x^{\prime}\right)$函数的存在，投影坐标算符$\hat{X}_P\left(k_y\right)$在$\left|\Psi_{n k_x, k_y}\right\rangle$基底下有如下分块形式：

$$
\hat{X}_P\left(k_y\right)=\left(\begin{array}{cccccc}
0 & F_{0,1} & 0 & 0 & 0 & 0 \\
0 & 0 & F_{1,2} & 0 & 0 & 0 \\
0 & 0 & 0 & F_{2,3} & 0 & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & 0 & F_{N_x-2, N_x-1} \\
F_{N_x-1,0} & 0 & 0 & 0 & 0 & 0
\end{array}\right)
$$

其中：

$$
F_{i, i+1}^{n m}\left(k_y\right)=\sum_\alpha g_{n \alpha}^*\left(k_{x, i}, k_y\right) g_{m \alpha}\left(k_{x, i+1}, k_y\right)
$$

注意此时$F_{i, i+1}$仍为$M\times M$矩阵，且与$k_y$有关：利用以下等式：

$$
\begin{aligned}
\left\langle n, k \mid m, k^{\prime}\right\rangle&=\left\langle\Psi_{n k}\left|e^{i k \cdot r} e^{-i k^{\prime} \cdot r}\right| \Psi_{m, k^{\prime}}\right\rangle \\
&=\sum_{\alpha, \beta} \frac{1}{N_{cell}} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \\
&* \sum_{j_1, j_2}\left\langle\alpha j_1\left|e^{i\left(k-k^{\prime}\right) \cdot r}\right| \beta j_2\right\rangle e^{i\left(k^{\prime} \cdot R_{j_2}-k \cdot R_{j_1}\right)} \\
&=\sum_{\alpha, \beta} \frac{1}{N_{cell}} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \\
&* \sum_{j_1, j_2}\langle\alpha \mid \beta\rangle \delta_{j_1 j_2} e^{i\left(k-k^{\prime}\right) \cdot R_{j_2}} e^{i\left(k^{\prime} \cdot R_{j_2}-k \cdot R_{j_1}\right)} \\
&=\sum_{\alpha, \beta} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \delta_{\alpha \beta} \\
&=\sum_\alpha g_{n \alpha}^*(k) g_{m \alpha}\left(k^{\prime}\right)
\end{aligned}
$$

我们可以用Bloch波函数的周期部分来改写上述projected position operator：

$$
F_{i, i+1}^{m n}\left(k_y\right)=\left\langle m, k_{x, i}, k_y \mid n, k_{x, i+1}, k_y\right\rangle
$$

那么怎么求这个screwed diagonal矩阵的本征值问题呢？其screwed diagonal分块矩阵的结构提示我们用transfer matrix的方法求解。假设本征态（Maximally Localized Wannier State）在此基底下为$|W^i\rangle =(|W^i_0\rangle,\,|W^i_1\rangle,\,\dots,\,|W^i_{N_x-1}\rangle)^T$，每个$|W^i_j\rangle$都有n分量，i用来标记是第几个eigenstate则本征方程为：

$$
\hat{X}_P\left(k_y\right) | W^i \rangle = e^{-i \delta k_x \cdot \mathbf{R}_i} | W^i \rangle
$$

展开写成：

$$
\begin{aligned}
\left(\begin{array}{cccccc}
0 & F_{0,1} & 0 & 0 & 0 & 0 \\
0 & 0 & F_{1,2} & 0 & 0 & 0 \\
0 & 0 & 0 & F_{2,3} & 0 & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & 0 & F_{N_x-2, N_x-1} \\
F_{N_x-1,0} & 0 & 0 & 0 & 0 & 0
\end{array}\right)
& \left(\begin{array}{c}
|W^i_0\rangle \\
|W^i_1\rangle \\
|W^i_2\rangle \\
\vdots \\
|W^i_{N_x-2}\rangle \\
|W^i_{N_x-1}\rangle
\end{array}\right) \\
= e^{-i \delta k_x \cdot \mathbf{R}_i}
& \left(\begin{array}{c}
|W^i_0\rangle \\
|W^i_1\rangle \\
|W^i_2\rangle \\
\vdots \\
|W^i_{N_x-2}\rangle \\
|W^i_{N_x-1}\rangle
\end{array}\right)
\end{aligned}
$$

则有transfer matrix式的递推式：

$$
F_{j,j+1} |W^i_{j+1}\rangle = e^{-i \delta k_x \cdot \mathbf{R}_i} |W^i_{j}\rangle
$$

这个递推也是周期的，所有的递推式相乘可以得到（为方便，我们取晶格常量$a_x = 1$）：

$$
F_{0,1} \dots F_{N_x-2,N_x-1} F_{N_x-1,0} |W^i_{0}\rangle = e^{-i N_x \delta k_x \cdot \mathbf{R}_i}|W^i_{0}\rangle = e^{-i 2\pi \mathbf{R}_i} |W^i_{0}\rangle
$$

定义"Wilson Loop"：

$$
W_{k_x \rightarrow k_x + 2\pi} \left(k_y\right)=F_{k_x,k_x+\delta k_x} F_{k_x+\delta k_x, k_x+2\delta k_x} \cdots F_{k_x+(N_x-2)\delta k_x, k_x}
$$

则投影坐标算符的本征值问题（求解Wannier Center）变成了"Wilson Loop" $W_{k_x\rightarrow k_x + 2\pi} \left(k_y\right)$ 的本征值问题：

$$
\mathbf{R}_i = \frac{i}{2\pi} \ln [W_{k_x \rightarrow k_x + 2\pi}]
$$

注意到Wilson Loop是$M\times M$矩阵，可以有M个本征值和本征态，分别对应M个occupied band在实空间中的Wannier Function（类似atomic orbital，但可能有杂化），而$\hat{X}_P$是$(N_x M) \times (N_x M)$矩阵，有$N_x$倍更多的本征值（Wannier Center），这正好对应移动$n=0,1,2,\dots,N_x-1$个晶格常数。何以见得？此时Wilson Loop的本征值相位变化$2\pi$，对应$\hat{X}_P$本征值相位变化$2\pi/N_x$，故一个Wilson Loop的本征值对应$N_x$个$\hat{X}_P$本征值，即$\mathbf{R}_i + n,\,n=0,1,2,\dots,N_x-1$也是Wannier Center的解。对于$\delta k=\frac{2 \pi}{N_x a_x} \ll 2 \pi$，即无穷长系统（但仍为PBC），有：

$$
\begin{aligned}
F_{i, i+1}^{m n} & =\left\langle m, k_{x, i}, k_y \mid n, k_{x, i+1}, k_y\right\rangle \\
& =\delta_{m n}+\left\langle m, k_{x, i}, k_y\left|\left(\left|n, k_{x, i+1}, k_y\right\rangle-\left|n, k_{x, i}, k_y\right\rangle\right)\right.\right. \\
& =\delta_{m n}-i A_{i, i+1}^{m n} \delta k \\
& \approx e^{-i A_{i, i+1}^{m n} \delta k}
\end{aligned}
$$

其中$A_{i, i+1}^{m n}$即Berry Connection的离散形式：

$$
A_{i, i+1}^{m n} =i \frac{\left\langle m, k_{x, i}, k_y\left|\left(\left|n, k_{x, i+1}, k_y\right\rangle-\left|n, k_{x, i}, k_y\right\rangle\right)\right.\right.}{\delta k}
$$

则"Wilson Loop"还能形式上写成Path Ordered Integral的形式：

$$
\begin{aligned}
W_{k_x \rightarrow k_x + 2\pi}\left(k_y\right) & =\left[\prod_{i=0}^{N_x-1} F_{i, i+1}\right]=\left[\prod_{i=0}^{N_x-1} e^{-i A_{i, i+1} \delta k}\right] \\
& =P e^{\int_{C_{k_y}}-i A(k) d k}
\end{aligned}
$$

其中路径积分即$C_{k_y}:(k_x,k_y) \rightarrow (k_x + 2\pi,k_y)$。这也是该算符被称为Wilson Loop的原因，数值上计算Wilson Loop在对角化也没有gauge的问题，故这是一个非常好的计算拓扑不变量的工具。

![Path Integral Contour of Wilson Loop](/posts/bulk-boundary-correspondence/fig08_path_integral_contour_wilson_loop.png)

*Path Integral Contour of Wilson Loop*

接下来我们来阐释Wilson Loop的物理意义，及其在确定Chern Insulator的$\mathbb{Z}$ index和$\mathbb{Z}_2$ index中的作用。

### Why Wannierization?

有人可能会问为什么要用Wannier基底这种gauge dependent的玩意，一点都不physical，电子凭什么要待在localized且不是本征态的Wannier state中？这个质疑在能带未被填满（partially filled band）时是成立的，但对于fully occupied band则值得深思。fully occupied band对应的多体波函数由该能带上所有Bloch波函数的Slater Determinant决定：

$$
\Psi_{\text{many body}}(x_1,x_2,\dots x_N) = \frac{1}{\sqrt{N!}} \left| \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right|
$$

其中$\{\psi_{k_i}\}_{i=1}^N$为Bloch波函数，其经过一Unitary transformation $\mathcal{U}$换基可以变成实空间localize的Wannier state $\{w_{R_i}\}_{i=1}^N$。Wannier State全占据态可以写成Slater Determinant：

$$
\Psi_{\text{many body}}'(x_1,x_2,\dots x_N) = \frac{1}{\sqrt{N!}} \left| \begin{array}{c}
w_{R_1}(x_1) & \cdots & w_{R_N}(x_1) \\
\vdots & \ddots & \vdots \\
w_{R_1}(x_N) & \cdots & w_{R_N}(x_N)
\end{array}\right|
$$

两个多体态是完全相同的：

$$
\Psi_{\text{many body}}' = \Psi_{\text{many body}}
$$

因为其determinant部分只差了一个Unitary Transformation，即：

$$
\begin{aligned}
& \det \left[ \left( \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right) \right] \\
= & \det \left[ \mathcal{U} \left( \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right) \mathcal{U}^\dagger \right] \\
= & \det \left[ \left( \begin{array}{c}
w_{R_1}(x_1) & \cdots & w_{R_N}(x_1) \\
\vdots & \ddots & \vdots \\
w_{R_1}(x_N) & \cdots & w_{R_N}(x_N)
\end{array}\right) \right]
\end{aligned}
$$

![Equivalence of Bloch and Wannier Picture in Fully Occupied Bands](/posts/bulk-boundary-correspondence/fig09_bloch_wannier_equivalence.png)

*Equivalence of Bloch and Wannier Picture in Fully Occupied Bands*

这样，只要讨论限定在fully occupied bands，即insulators的范围内，我们用实空间localize的Wannier图像分析物理过程也不会有问题，这在分析insulator的polarization，charge pump时十分有用。反之，对于metal（partially filled bands）系统，我们便没法分析polarization等性质。事实上，电极化是insulator才有的现象，金属加电场后由于band里有unoccupied state，能够导电。这从另一方面描述了导体和绝缘体的区别。若对导体和绝缘体的区别还有兴趣，可以移步我之前的note：总之有了电子占据空间localized Wannier state的图像，我们能够更好的分析系统的拓扑性质：我们取自然单位制$e=\hbar=1$对于Chern Insulator，加入y方向电场$E_y$后，原来处在$k_{y0}$的态经过时间t会变成$k_{y0} + E_y t$的态，考察实空间中电子（Wannier Center）在x方向的运动，一个周期后实空间电子整体移动1个晶格常数，对应x方向输运了一个单位电荷。这个Charge Pump过程可以从Wilson Loop Spectrum中直接读出：

![Wilson Loop Spectrum of C=1 Chern Insulator and its Real Space Picture](/posts/bulk-boundary-correspondence/fig10_wilson_spectrum_C1_chern.png)

*Wilson Loop Spectrum of C=1 Chern Insulator and its Real Space Picture*

用时$2\pi/E_y$，则y方向电场$E_y$ induce的x方向电流为

$$
I_x = j_x = \frac{\Delta Q}{\Delta t} = \frac{1}{2\pi/E_y} = \frac{1}{2\pi} E_y
$$

电流与电流密度相同是因为令晶格常数为1的结果。故Hall conductance是量子化的$\sigma_{xy}=\frac{1}{2\pi}=\frac{e^2}{h}$，推广到任意陈数则有$\sigma_{xy} = \frac{C}{2\pi}$。可见Wilson Loop Formalism的物理意义之直观。

![Charge Pump of Chern Insulator](/posts/bulk-boundary-correspondence/fig11_charge_pump_chern.png)

*Charge Pump of Chern Insulator*

类似的对于$\mathbb{Z}_2$-topological insulator，我们考察一对time-reversal counterpart Wannier State的移动，即"time-reversal charge pump"。若一个周期后time-reversal counterpart Wannier State朝相反方向移动了一个晶格常数，则发生了nontrivial的"time-reversal charge pump"，系统为topological insulator，否则就是trivial insulator。系统没有净的charge pump，这是time reversal symmetry保证的。

![Wilson Loop Spectrum of TI and Real Space Picture](/posts/bulk-boundary-correspondence/fig12_wilson_spectrum_TI.png)

*Wilson Loop Spectrum of TI and Real Space Picture*

![Charge Pump of Topological Insulator](/posts/bulk-boundary-correspondence/fig13_charge_pump_TI.png)

*Charge Pump of Topological Insulator*

trivial insulator的Wilson Loop Spectrum如下图所示，即没有net charge pump也没有nontrivial time-reversal charge pump：

![Trivial Wilson Loop Spectra](/posts/bulk-boundary-correspondence/fig14_trivial_wilson_spectrum.png)

*Trivial Wilson Loop Spectra*

![Charge not Pumped in trivial insulator (C=0 Chern Insulator)](/posts/bulk-boundary-correspondence/fig15_charge_not_pumped_trivial.png)

*Charge not Pumped in trivial insulator (C=0 Chern Insulator)*

### Wilson Loop and Edge: Spectrum Equivalence

另一方面，Wilson Loop Spectrum与边缘态的色散关系拓扑等价。Fidkowski, L., Jackson, T. S., & Klich, I.等人证明，通过一定的interpolation，Wilson Loop Spectrum与Edge State Spectrum可以连续变化连接，这样我们通过Wilson Loop Spectrum能够估计边缘态色散关系的形状即群速度等性质（拓扑等价情况下）。

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.036601>

具体而言，我们考虑最简单的flat band projection后的Hamiltonian，因为只要拓扑等价（gap不发生closing），讨论就是universal的。Flat band Hamiltonian为：

$$
\mathscr{H}_{\text{flat}}(\vec{k})=1-2 P(\vec{k})
$$

其中$P(\vec{k})$为M个occupied band（valence band）的projection operator，此时系统拓扑性质储存在波函数的信息中：

$$
P(\vec{k})=\sum_n^M \int_{-\pi}^\pi \frac{\mathrm{d} k_x}{2 \pi}\left|\psi_{k, n}\right\rangle\left\langle\psi_{k, n}\right|,
$$

考虑边界：

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k})=P(\vec{k}) V_0(\hat{x}) P(\vec{k})+1-P(\vec{k}) \quad V_0(x)= \begin{cases}1 ,\,x<0 \\-1 ,\,x>0\end{cases}
$$

则体态哈密顿量为：

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k}) \rightarrow \mathscr{H}_{\mathrm{flat}}(\vec{k}) \text { for } x \rightarrow+\infty
$$

真空中哈密顿量为：

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k}) \rightarrow 1 \text { for } x \rightarrow-\infty
$$

考虑下述边缘势的变化：

$$
V_t(x)=\left\{\begin{array}{ll}
-\frac{x}{t} & \text { for }|x|<t /(1-t) \\
-\frac{\operatorname{sgn}(x)}{1-t} & \text { for }|x| \geq t /(1-t)
\end{array}, \quad 0 \leq t \leq 1 .\right.
$$

则$t=0$时，系统能谱为$\mathscr{H}_{\mathrm{bdr}}(\vec{k})$的能谱，$t=1$时为$P\hat{x}P$的能谱，而$P\hat{x}P$能谱正是Wilson Loop Spectrum（+平移整数个晶格常数）这便证明了两者的拓扑等价性。

![Equivalence between Wilson Loop Spectrum & Edge Spectrum](/posts/bulk-boundary-correspondence/fig16_wilson_edge_equivalence.png)

*Equivalence between Wilson Loop Spectrum & Edge Spectrum*

更具体的讲解可以参考西班牙一年一度的Topological Matter School（TMS）网课：

<https://www.youtube.com/watch?v=t3k5DLKreyg&t=2029s>

或者参考TMS17年的lecture note（已出版）：

<https://link.springer.com/content/pdf/10.1007/978-3-319-76388-0.pdf>

## Entanglement Spectrum

Entanglement Spectrum、Entanglement Entropy这些Quantum Information相关的topics也能在拓扑凝聚态物理里掺一脚？"万恶之源"便是Haldane在2008年的一篇用Entanglement Spectrum来identify FQHE的topological order的文章。

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.101.010504>

Lukasz Fidkowski将其推广到了Band Topology中：

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.104.130502>

核心论点是topological non-trivial state有拓扑保护的degeneracy。

![Degeneracy in Entanglement Spectra = topologically non-trivial phase](/posts/bulk-boundary-correspondence/fig17_entanglement_degeneracy.png)

*Degeneracy in Entanglement Spectra = topologically non-trivial phase*

Ashvin等人进一步发现Entanglement Spectrum与Edge state Spectrum也有类似Wilson Loop Spectrum与Edge State Spectrum的拓扑等价性，证明方法也是类似地提出一种entanglement Spectrum到Edge state Spectrum的interpolation（"连续形变"）：

<https://arxiv.org/abs/0909.3119>

Xiaoliang Qi等人也有相关的文章：

General Relationship between the Entanglement Spectrum and the Edge State Spectrum of Topological Quantum States

![Topological Equivalence between Surface Spectrum & Entanglement Spectrum](/posts/bulk-boundary-correspondence/fig18_surface_entanglement_equivalence.png)

*Topological Equivalence between Surface Spectrum & Entanglement Spectrum*

如上图所示，Surface Spectrum与Entanglement Spectrum拓扑等价，这又给我们提供了一种detect拓扑边缘态的工具。

## Beyond Traditional BEC

上面提到的体边对应是在拓扑能带论被拓扑绝缘体/陈绝缘体/拓扑超导体垄断的10年代前是最重要的结论之一，但也只是最简单的版本。值得一提的是"体边对应"还有后续的发展，这与10年代后陆续发现的由晶体对称性保护的拓扑晶体绝缘体（Topological Crystalline Insulator, TCI），以及其中比较神奇的高阶拓扑绝缘体（Higher-Order Topological Insulator, HOTI）、脆拓扑（Fragile Topology）等概念密不可分。

![Family of Topological Band Insulators](/posts/bulk-boundary-correspondence/fig19_family_topo_insulators.png)

*Family of Topological Band Insulators*

在这些体系中有更神奇的体边对应现象。

### Topological Crystalline Insulators

TCI最早起源于Liang Fu的PRL：

Topological Crystalline Insulators

之后发展成为各种晶格对称性保护的Topological Band Insulators，更进一步Ashvin, Bernevig, Cano, Jennifer, Barry Bradlyn等人发展出了Symmetry Indicator, Topological Quantum Chemistry来系统地进行ab initio计算：

<https://www.nature.com/articles/s41467-017-00133-2>

<https://www.annualreviews.org/content/journals/10.1146/annurev-conmatphys-041720-124134>

对于TCI，只有在保持对应晶体对称性的边界上才有拓扑保护的边缘态，例如Mirror Chern Insulator在破坏了镜面对称的边界就没有拓扑保护的边缘态。下图来自Weizmann的Topological quantum matter系列课程中的Topological Crystalline Insulator小节，墙裂推荐 (。・ω・。)。

<https://www.youtube.com/watch?v=ErwkO5H4M4E&t=454s>

![Mirror Chern Insulator (From Weizmann TQM lecture video)](/posts/bulk-boundary-correspondence/fig20_mirror_chern_insulator.png)

*Mirror Chern Insulator (From Weizmann TQM lecture video)*

TCI的确定用到了Wilson Loop等工具，可以参考Xi Dai & Bernevig的文章：

Wilson-loop characterization of inversion-symmetric topological insulators

### Higher Order Topological Insulators

对于HOTI，假设系统维度为d，不同于在d-1维的边界上有拓扑保护的边缘态的一般体边对应，而能在d-2维、d-3维、……的边界上有拓扑保护的边缘态。本质上，d-2维的拓扑保护的边缘态可以看成d-1维的边界是拓扑绝缘体，对于2维体系我们可以有拓扑角态（topological corner state），对于3维体系我们可以有拓扑棱态（topological hinge state），以此类推。高阶拓扑绝缘体的classification便用到了Wilson Loop和Entanglement Spectrum的推广：nested Wilson Loop与nested Entanglement Spectrum。HOTI更详细的介绍可以参考Taylor Hughes的文章：

<https://www.science.org/doi/full/10.1126/science.aah6442>

<https://journals.aps.org/prb/abstract/10.1103/PhysRevB.96.245115>

也可以参考Titus的文章：

<https://www.science.org/doi/full/10.1126/sciadv.aat0346>

![Hinge state of HOTI](/posts/bulk-boundary-correspondence/fig21_hinge_state_hoti.png)

*Hinge state of HOTI*

### Fragile Topology

对于Fragile Topology，传统的体边对应则失效了，因为脆拓扑是加上trivial band能被trivialize的存在，这说明传统的体边对应和拓扑分类并非一一对应，Zhida Song等人在这方面进行了推广，即所谓的twisted boundary condition（TBC）和real space invariant（RSI）。此时的"体边对应"被推广为twisted boundary condition参数经过一周变化过程中必然会有gap closing过程的存在，这样Fragile Topology便可以用推广的"体边对应"来判断，具体可以参考这个回答：关于TBC与RSI可以参考Zhida Song的文章：

<https://www.science.org/doi/full/10.1126/science.aaz7650>

![Spectral flow of fragile topology under TBC](/posts/bulk-boundary-correspondence/fig22_spectral_flow_fragile_TBC.png)

*Spectral flow of fragile topology under TBC*

## Reference

1. Chang, C. Z., Liu, C. X., & MacDonald, A. H. (2023). Colloquium: Quantum anomalous hall effect. *Reviews of Modern Physics*, 95(1), 011002.

2. Hasan, M. Z., & Kane, C. L. (2010). Colloquium: topological insulators. *Reviews of Modern Physics*, 82(4), 3045.

3. Shen, S. Q. (2012). *Topological insulators* (Vol. 174). Berlin: Springer.

4. Yu, R., Qi, X. L., Bernevig, A., Fang, Z., & Dai, X. (2011). Equivalent expression of $\mathbb{Z}_2$ topological invariant for band insulators using the non-Abelian Berry connection. *Physical Review B*, 84(7), 075119.

5. Bercioux, D., Cayssol, J., Vergniory, M. G., & Calvo, M. R. (Eds.). (2018). *Topological matter: lectures from the topological matter school 2017* (Vol. 190). Springer.

6. Marzari, N., Mostofi, A. A., Yates, J. R., Souza, I., & Vanderbilt, D. (2012). Maximally localized Wannier functions: Theory and applications. *Reviews of Modern Physics*, 84(4), 1419.

7. Marzari, N., & Vanderbilt, D. (1997). Maximally localized generalized Wannier functions for composite energy bands. *Physical Review B*, 56(20), 12847.

8. Resta, R. (2002). Why are insulators insulating and metals conducting?. *Journal of Physics: Condensed Matter*, 14(20), R625.

9. Resta, R. (2022). Geometry and topology in electronic structure theory. Università degli Studi di Trieste.

10. Fidkowski, L., Jackson, T. S., & Klich, I. (2011). Model characterization of gapless edge modes of topological insulators using intermediate Brillouin-zone functions. *Physical Review Letters*, 107(3), 036601.

11. Li, H., & Haldane, F. D. M. (2008). Entanglement spectrum as a generalization of entanglement entropy: Identification of topological order in non-abelian fractional quantum hall effect states. *Physical Review Letters*, 101(1), 010504.

12. Fidkowski, L. (2010). Entanglement spectrum of topological insulators and superconductors. *Physical Review Letters*, 104(13), 130502.

13. Turner, A. M., Zhang, Y., & Vishwanath, A. (2009). Band topology of insulators via the entanglement spectrum. arXiv:0909.3119.

14. Qi, X. L., Katsura, H., & Ludwig, A. W. (2012). General relationship between the entanglement spectrum and the edge state spectrum of topological quantum states. *Physical Review Letters*, 108(19), 196402.

15. Fu, L. (2011). Topological crystalline insulators. *Physical Review Letters*, 106(10), 106802.

16. Po, H. C., Vishwanath, A., & Watanabe, H. (2017). Symmetry-based indicators of band topology in the 230 space groups. *Nature Communications*, 8(1), 50.

17. Cano, J., & Bradlyn, B. (2021). Band representations and topological quantum chemistry. *Annual Review of Condensed Matter Physics*, 12, 225-246.

18. Alexandradinata, A., Dai, X., & Bernevig, B. A. (2014). Wilson-loop characterization of inversion-symmetric topological insulators. *Physical Review B*, 89(15), 155114.

19. Benalcazar, W. A., Bernevig, B. A., & Hughes, T. L. (2017). Quantized electric multipole insulators. *Science*, 357(6346), 61-66.

20. Benalcazar, W. A., Bernevig, B. A., & Hughes, T. L. (2017). Electric multipole moments, topological multipole moment pumping, and chiral hinge states in crystalline insulators. *Physical Review B*, 96(24), 245115.

21. Schindler, F., Cook, A. M., Vergniory, M. G., Wang, Z., Parkin, S. S., Bernevig, B. A., & Neupert, T. (2018). Higher-order topological insulators. *Science Advances*, 4(6), eaat0346.

22. Song, Z. D., Elcoro, L., & Bernevig, B. A. (2020). Twisted bulk-boundary correspondence of fragile topology. *Science*, 367(6479), 794-797.

23. Mong, R. S., & Shivamoggi, V. (2011). Edge states and the bulk-boundary correspondence in Dirac Hamiltonians. *Physical Review B*, 83(12), 125109.
