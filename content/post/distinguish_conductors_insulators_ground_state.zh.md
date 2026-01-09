+++
date = '2026-01-08T21:54:37-05:00'
draft = false
math = true
ShowToc = true
TocOpen = false
title = '只看基态如何区分导体和绝缘体？🤔'
+++

本note旨在阐述多体系统**导电性**与**基态量子几何性质**的关联，并解释如何仅通过基态波函数的“局域”程度，来区分导体和绝缘体。

## Introduction

“只看基态就能区分导体和绝缘体”，这个argument似乎有些离谱。

1930年代的能带论（一定程度上）解释了导体和绝缘体的区别。在non-interacting层面上，导体与绝缘体可以根据基态能带是否填满来判断。价带若被填满，且和导带有带隙$E_g > 0$，则是绝缘体；反之则为导体。此时可以用带隙$E_g$区分导体和绝缘体，而带隙$E_g$至少需要知道激发态的能量，故不可避免涉及激发态性质。

但1949年提出的Mott Insulator（由强电子-电子关联导致）和1958年提出的Anderson Insulator（由强无序导致）指出了能带论在区分导体和绝缘体上的漏洞，即多体系统的绝缘机制不只有包括价带被填满，还可能与强关联、无序有关。同理，除了无带隙可以是导体的产生机制，一些无序的金属合金也可能是导体。例如，无序的合金体系中，虽然没有带隙，但仍可能为绝缘体，这正是Anderson Localization导致的局域态没法稳定输运电流导致的。

更何况，多体系统可以根本没有晶格，我们急需一种更universal的判断多体系统导电性质的indicator。

唯象而言，导体与绝缘体的区别在于直流电导率$\text{Re}\sigma(\omega\rightarrow 0)$的不同，因为一般的绝缘体通交流电也能导电。或者靠电极化现象区分，绝缘体中电子束缚，只能在原子附近运动，才有明显的电极化现象，而导体中电子趋于自由运动，外加电场会使其自由流动，因而没有良定的电极化现象。

我们总可以通过计算线性响应理论计算电导率或者电极化率，从而区分导体和绝缘体，但这还是需要考虑激发态的性质。

但Kohn在1964年的论文"Theory of the insulating state"提出，多体系统的导电性可以用基态多体波函数在many-body configuration的“局域”程度来判断。

https://journals.aps.org/pr/abstract/10.1103/PhysRev.133.A171

20世纪末，Resta等人注意到这种局域程度可以用多体基态波函数的second cumulant moment$\langle r_\alpha r_\beta \rangle_c$（“c" for "cumulant"）更好的刻画，并揭示了其Quantum Geometry的本质。

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.82.370

那么首先，我们来阐明怎么定义波函数的局域程度。

## Wannierizability & Quantum Geometry

这里需要阐明，所谓“基态多体波函数在many-body configuration的‘局域’程度”，与单体波函数的局域程度不同，但在定义上有相似之处。而且从单体波函数的角度推导更加简单，所以我们先介绍单体波函数的局域程度的定义，讨论其性质，之后再推广到Kohn、Resta等人论文中的多体情形。

以固体能带体系为例，不论是绝缘体还是导体，其单电子本征态都是延展的Bloch波函数。不过我们可以通过Fourier Transfer将这些实空间延展的Bloch本征态变成实空间局域的Wannier Function。

Wannier函数$|\mathbf{R} n\rangle$和Bloch波函数$\left|\psi_{n \mathbf{k}}\right\rangle$之间的转换关系：

$$
\begin{aligned}
\left|\psi_{n \mathbf{k}}\right\rangle=
\sum_{\mathbf{R}} e^{i \mathbf{k} \cdot \mathbf{R}}|\mathbf{R} n\rangle \Leftrightarrow |\mathbf{R} n\rangle=\frac{1}{N} \sum_{\mathbf{k}} e^{-i \mathbf{k} \cdot \mathbf{R}}\left|\psi_{n \mathbf{k}}\right\rangle
\end{aligned}
$$

Wannier波函数的局域程度与能带的规范选取有关。如果我们给Bloch波函数加上一个与$\mathbf{k}$有关的相位（规范），仍然是本征态。

$$
\begin{aligned}
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|\psi_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{\psi}_{n \mathbf{k}}\right\rangle
\end{aligned}
$$

如何通过调节gauge使得Wannier函数达到最大局域化相关内容可以参考Vanderbilt的1997年的PRB，“Maximally localized generalized Wannier functions for composite energy bands”以及2012年的RMP，“Maximally localized Wannier functions: Theory and applications”：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419

Vanderbilt用其实空间分布的标准差定义Wannier函数的局域程度，即所谓的Spread Functional，也称为Quadratic Spread：

$$
\begin{aligned}
\Omega=\left[\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\langle\mathbf{0} n|\mathbf{r}| \mathbf{0} n\rangle^2\right]=\left[\left\langle r^2\right\rangle_n-\overline{\mathbf{r}}_n^2\right]
\end{aligned}
$$

这个Spread Functional和规范选取有关，但可以分为规范不变$\Omega_{\mathrm{I}}$和与规范有关$\tilde{\Omega}$的两个部分：

$$
\begin{aligned}
\Omega=\Omega_{\mathrm{I}}+\tilde{\Omega}
\end{aligned}
$$

其中，规范不变部分$\Omega_{\mathrm{I}}$，也被称为Wannier函数的second cumulant moment：

$$
\begin{aligned}
\Omega_{\mathrm{I}}=\sum_{\alpha}\left\langle 0 n\left|r_\alpha Q r_\alpha\right| 0 n\right\rangle=\sum_\alpha \text{Tr}\left[P r_\alpha Q r_\alpha\right]
\end{aligned}
$$

$P$为投影到所考察能带的投影算符：

$$
\begin{aligned}
P =\frac{1}{N} \sum_{\mathbf{k}}\left|\psi_{n \mathbf{k}}\right\rangle\langle\psi_{n \mathbf{k}}|=\sum_{\mathbf{R}}| \mathbf{R} n\rangle\langle\mathbf{R} n| 
\end{aligned}
$$

这部分与单体能带的Quantum Geometry有关：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle
\end{aligned}
$$

规范有关$\tilde{\Omega}$的部分是一个非负值

$$
\begin{aligned}
\tilde{\Omega}=\sum_{\mathbf{R} m \neq 0 n}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
\end{aligned}
$$

那么总有：

$$
\begin{aligned}
\Omega \geq \Omega_{\mathrm{I}}
\end{aligned}
$$

此部分详细推倒可以参考本人的note：

https://zhuanlan.zhihu.com/p/629079639

可见Wannier函数Quadratic Spread的规范不变部分定义了其局域程度的下限，且与单体能带的Quantum Geometry建立了直接的联系。

换句话说，**Quantum Geometry可以一定程度上反应系统（目前是单体系统）的局域程度。**

受此启发，我们可以定义多体系统的Quantum Geometry，考察其包含的多体波函数“局域”程度信息，并讨论多体基态波函数的“局域”程度这一基态性质如何决定多体系统的导电性。

## Many-Body Quantum Geometry

类似的，我们来定义多体系统的Quantum Geometry，首先写下最general的多体Hamiltonian：

$$
\begin{aligned}
\hat{H}=\frac{1}{2 m_e} \sum_{i=1}^N\left|\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)\right|^2+\hat{V}(\\{\mathbf{r}_i\\})
\end{aligned}
$$

但此时系统不一定有平移对称性，故原先单体能带论的Quantum Geometry构造方法不能直接应用到此处，不能直接把单电子的动量作为参数空间。

为了找到可以构建Quantum Geometry的参数空间，我们对多体Hamiltonain作规范变换：

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa}) \equiv e^{-i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}} \hat{H} e^{i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}}
\end{aligned}
$$

其中$\hat{\mathbf{r}} \equiv \sum_i \hat{\mathbf{r}}_i$

即，

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa})=\frac{1}{2 m_e} \sum_{i=1}^N\left|\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)+\hbar \boldsymbol{\kappa}\right|^2+\hat{V}(\\{(\mathbf{r}_i\\})
\end{aligned}
$$

此时不同参数$\boldsymbol{\kappa}$对应不同的多体能谱和本征波函数

$$
\begin{aligned}
H(\boldsymbol{\kappa})|\Psi(\boldsymbol{\kappa})\rangle=E(\boldsymbol{\kappa})|\Psi(\boldsymbol{\kappa})\rangle
\end{aligned}
$$

这相当于加了一个常数的磁矢势，可以用1D环内的磁通来理解，此时$\kappa \propto$环内磁通$\Phi$。

![Image](https://pic4.zhimg.com/80/v2-bf698d3fa3347511c74f9b760fb057a6.png)

多体系统最重要的是基态，我们考察参数空间$\boldsymbol{\kappa}$到基态波函数$|\Psi_0(\boldsymbol{\kappa})\rangle$的映射，并以此来构建基态波函数空间的Quantum Geometric Tensor：

$$
\begin{aligned}
\eta_{\alpha \beta}(\boldsymbol{\kappa})=\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle
\end{aligned}
$$

其中$\hat{Q}(\boldsymbol{\kappa})=\hat{1}-\hat{P}(\boldsymbol{\kappa})$，$\hat{P}(\boldsymbol{\kappa})$为基态波函数空间投影算符：

$$
\begin{aligned}
\hat{P}(\boldsymbol{\kappa})=\left|\Psi_0(\boldsymbol{\kappa})\right\rangle\left\langle\Psi_0(\boldsymbol{\kappa})\right|
\end{aligned}
$$

类似的band geometry，实部为Symmetric Tensor，称为Fubini-Study metric：

$$
\begin{aligned}
g_{\alpha \beta}(\boldsymbol{\kappa}) & =\text{Re}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa}) \mid \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle \\
& -\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa}) \mid \Psi_0(\boldsymbol{\kappa})\right\rangle\left\langle\Psi_0(\boldsymbol{\kappa}) \mid \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle \\
& =\text{Re}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle 
\end{aligned}
$$

虚部为Anti-symmetric Tensor，为Berry Curvature：

$$
\begin{aligned}
\Omega_{\alpha \beta}(\boldsymbol{\kappa})=-2 \text{Im}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle
\end{aligned}
$$

类似单体，也可以写成sum of state的形式，用一阶微扰论：

$$
\begin{aligned}
\left|\Psi_0(\boldsymbol{\kappa}+\Delta \boldsymbol{\kappa})\right\rangle-\left|\Psi_0(\boldsymbol{\kappa})\right\rangle \simeq \sum_{n \neq 0}^{\prime}\left|\Psi_n(\boldsymbol{\kappa})\right\rangle
\end{aligned}
$$

$$
\begin{aligned}
\times \frac{\left\langle\Psi_n(\boldsymbol{\kappa})|[H(\boldsymbol{\kappa}+\Delta \boldsymbol{\kappa})-H(\boldsymbol{\kappa})]| \Psi_0(\boldsymbol{\kappa})\right\rangle}{E_0(\boldsymbol{\kappa})-E_n(\boldsymbol{\kappa})}
\end{aligned}
$$

$$
\begin{aligned}
\left|\partial_\alpha \Psi_0(\boldsymbol{\kappa})\right\rangle=\sum_{n \neq 0}^{\prime}\left|\Psi_n(\boldsymbol{\kappa})\right\rangle \frac{\left\langle\Psi_n(\boldsymbol{\kappa})\left|\partial_\alpha H(\boldsymbol{\kappa})\right| \Psi_0(\boldsymbol{\kappa})\right\rangle}{E_0(\boldsymbol{\kappa})-E_n(\boldsymbol{\kappa})} .
\end{aligned}
$$

$$
\begin{aligned}
\eta_{\alpha \beta}(\kappa)= \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0(\boldsymbol{\kappa})\left|\partial_\alpha H(\boldsymbol{\kappa})\right| \Psi_n(\boldsymbol{\kappa})\right\rangle\left\langle\Psi_n(\boldsymbol{\kappa})\left|\partial_\beta H(\boldsymbol{\kappa})\right| \Psi_0(\boldsymbol{\kappa})\right\rangle}{\left[E_0(\boldsymbol{\kappa})-E_n(\boldsymbol{\kappa})\right]^2}
\end{aligned}
$$

应当注意，此sum of state公式在无能隙或者基态简并时会失效（此时一阶微扰论失效），但这不意味着Quantum Geometry的定义失效。多体系统也存在fascinating的Ground State Degeneracy，此时可以将基态波函数及其Quantum Gemetry拓展到更高维的non-Abelian形式（non-Abelian Berry Connection的推广）。

限于篇幅，我们只讨论nondegenerate Ground State的情形，感兴趣的读者可以自行推广并计算一些Fractional Quantum Hall system等系统的non-Abelian Quantum Geometry。

## Quantum Geometry & Localization

我们再将描述单体Localization程度的second cumulant moment of position operator，即Spread Functional的规范不变部分$\Omega_I$拓展到多体情形，来描述多体波函数的“局域”程度。

我们注意到：

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa}) \equiv e^{-i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}} \hat{H} e^{i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}}
\end{aligned}
$$

假设$\left|\Psi_0\right\rangle$为$\hat{H}$的non-degenerate基态，我们很容易写出$\hat{H}(\boldsymbol{\kappa})$的基态（暂且假设是开边界条件，考虑周期边界条件会更复杂）：

$$
\begin{aligned}
\left|\Psi_0(\boldsymbol{\kappa})\right\rangle=e^{-i \boldsymbol{\kappa} \cdot(\hat{\mathbf{r}}-\mathbf{d})}\left|\Psi_0\right\rangle
\end{aligned}
$$

其中，$\mathbf{d}=\left\langle\Psi_0|\hat{\mathbf{r}}| \Psi_0\right\rangle$。这一项只贡献一个常数相位，故没有影响。

为了求Quantum Geometry，我们作微分：

$$
\begin{aligned}
\left|\nabla_{\boldsymbol{\kappa}} \Psi_0\right\rangle=-i(\hat{\mathbf{r}}-\mathbf{d})\left|\Psi_0\right\rangle=-i \hat{Q}(0) \hat{\mathbf{r}}\left|\Psi_0\right\rangle
\end{aligned}
$$

从而得到

$$
\begin{aligned}
\eta_{\alpha \beta}(0) &=\left\langle\Psi_0\left|\hat{r}_\alpha \hat{Q}(0) \hat{r}_\beta\right| \Psi_0\right\rangle \\
&=\left\langle\Psi_0\left|\hat{r}_\alpha \hat{r}_\beta\right| \Psi_0\right\rangle-\left\langle\Psi_0\left|\hat{r}_\alpha\right| \Psi_0\right\rangle\left\langle\Psi_0\left|\hat{r}_\beta\right| \Psi_0\right\rangle
\end{aligned}
$$

其中$\hat{\mathbf{r}} \equiv \sum_i \hat{\mathbf{r}}_i$。很难不发现，这相当于基态波函数coordinate分布的variance，亦即second cumulant moment。它反映了基态波函数电子在实空间分布的“局域”程度。

但这个量是个广延量（类似体积），考虑热力学极限$N\rightarrow\infty$
时会scale with $N$。为了能在不同系统之间比较这种“局域”程度，我们将其对每个电子做平均，使其成为可以比较的强度量（类似压强），当然这也可以通过改变波函数的归一化定义实现：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\eta_{\alpha \beta}(0) / N
\end{aligned}
$$

不难发现，和单体Wannier波函数的局域化程度需要对所有动量$k$积分$\Omega_I \propto \int_{BZ}d^dk \text{tr}g(k)$不同，这里我们只需要参数空间$\boldsymbol{\kappa} = 0$的信息，也就是原系统的基态信息。

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}= \frac{1}{N} \left(\left\langle\Psi_0\left|\hat{r}_\alpha \hat{r}_\beta\right| \Psi_0\right\rangle-\left\langle\Psi_0\left|\hat{r}_\alpha\right| \Psi_0\right\rangle\left\langle\Psi_0\left|\hat{r}_\beta\right| \Psi_0\right\rangle \right)
\end{aligned}
$$

为了之后推导方便（更好地和电导率公式对比），也可以写成sum of state的形式：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}= \frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\partial_\alpha \hat{H}(0)\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\partial_\beta \hat{H}(0)\right| \Psi_0\right\rangle}{\left(E_0-E_n\right)^2}
\end{aligned}
$$

其中，

$$
\begin{aligned}
\nabla_\kappa \hat{H}(0) =\frac{\hbar}{m_e} \sum_{i=1}^N\left[\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)\right] = \hbar \hat{\mathbf{v}}
\end{aligned}
$$

这事实上就是动量（速度）算符，从而可以进一步改写成：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\left(E_0-E_n\right)^2/\hbar^2}
\end{aligned}
$$

$$
\begin{aligned}
=\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\omega_{0 n}^2}
\end{aligned}
$$

$$
\begin{aligned}
\omega_{0 n}= \left(E_n-E_0\right) / \hbar
\end{aligned}
$$

但我们要牢记，**这里的second cumulant moment完全是基态波函数的局域性质，与激发态无关。**

整理一下，我们将单体的Quantum Geometry推广到了多体基态波函数空间，并发现多体基态波函数空间的Quantum Geometry（除以电子总数N）可以刻画多体基态波函数在实空间分布的局域程度，而且这是基态性质，与激发态无关。

**我们的最终目的是利用这个纯纯的基态性质，来区分看似需要用激发态性质才能区分的导体和绝缘体。**

## Localization & Conductivity

### Linear Response Theory

我们用线性响应理论可以速通多体系统的conductivity，感兴趣的同学可以考古本人的Linear Response Theory note：

https://zhuanlan.zhihu.com/p/477550302

$$
\begin{aligned}
\sigma_{\alpha \beta}(\omega)=\frac{i e^2}{\hbar L^3} \lim_{\eta \rightarrow 0+} \sum_{n \neq 0}^{\prime} \frac{1}{\omega_{0 n}}& \left(\frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\omega-\omega_{0 n}+i \eta}\right. \\
& \left.+\frac{\left\langle\Psi_0\left|\hat{v}_\beta\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\alpha\right| \Psi_0\right\rangle}{\omega+\omega_{0 n}+i \eta}\right)
\end{aligned}
$$

其中，此电导率的实部是耗散项，虚部是涨落项。我们通常意义上的考察电导的耗散性质，故我们关注其实部$\sigma_{\alpha \beta}(\omega)$。

电导率实部$\sigma_{\alpha \beta}(\omega)$可以分成symmetric的部分和anti-symmetric的部分（注意$\omega > 0$且$\omega_{0n} > 0$）：

$$
\begin{aligned}
\text{Re} \sigma_{\alpha \beta}^{(+)}(\omega)=\frac{\pi e^2}{\hbar L^3} \sum_{n \neq 0}^{\prime} \frac{\mathcal{R}_{n, \alpha \beta}}{\omega_{0 n}} \delta\left(\omega-\omega_{0 n}\right)
\end{aligned}
$$

$$
\begin{aligned}
\text{Re} \sigma_{\alpha \beta}^{(-)}(\omega)=\frac{2 e^2}{\hbar L^3} \sum_{n \neq 0}^{\prime} \frac{\mathcal{I}_{n, \alpha \beta}}{\omega_{0 n}^2-\omega^2}
\end{aligned}
$$

其中，

$$
\begin{aligned}
\mathcal{R}_{n, \alpha \beta}=\text{Re}\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle
\end{aligned}
$$

$$
\begin{aligned}
\mathcal{I}_{n, \alpha \beta}=\text{Im}\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle
\end{aligned}
$$

推导中我们用到了，

$$
\begin{aligned}
\lim_{\eta \rightarrow 0+} \frac{1}{x + i\eta} = \mathcal{P}\frac{1}{x} - i \pi \delta(x)
\end{aligned}
$$

对比之前得到的描述多体基态波函数局域程度的second cumulant moment$\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}$的sum of state形式：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\omega_{0 n}^2}
\end{aligned}
$$

不难发现，

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}=\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\mathcal{R}_{n, \alpha \beta}}{\omega_{0 n}^2}
\end{aligned}
$$

$$
\begin{aligned}
\text{Im}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}=\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\mathcal{I}_{n, \alpha \beta}}{\omega_{0 n}^2}
\end{aligned}
$$

进一步可以证明**SWM公式**（I.Souza, T.Wilkens, R.M.Martin, 2000）：

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{\omega} \text{Re} \sigma_{\alpha \beta}^{(+)}(\omega)
\end{aligned}
$$

$$
\begin{aligned}
\text{Im}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{2 e^2 N} \text{Re} \sigma_{\alpha \beta}^{(-)}(0)
\end{aligned}
$$

### SWM Formula

在唯象意义上定义导体和绝缘体时，我们会关注其 static longitudinal conductivity，即$\lim_{\omega \rightarrow 0}\sigma_{\alpha \alpha}(\omega)$。

关注static field$\omega \rightarrow 0$是因为绝缘体在交流电下也能导电；而关注longitudinal conductivity是因为即使transverse conductivity（例如Hall conductivity）非零，但longitudinal conductivity为零时，我们还是称其为绝缘体（例如Quantum Hall Insulator，Chern Insulator）。

我们可以发现，$\omega \rightarrow 0$的信息不好直接和$\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}$联系，但可以通过上面的SWM公式，间接考察$\omega \rightarrow 0$的信息。

关注**SWM公式**的longitudinal信息的实部（由于指标$\alpha$相同，故$\text{Re} \sigma_{\alpha \alpha} = \text{Re} \sigma_{\alpha \alpha}^{(+)}$）：

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{\omega} \text{Re} \sigma_{\alpha \alpha}(\omega)
\end{aligned}
$$

可以用f-sum rule证明$\omega \rightarrow \infty$的积分收敛：

$$
\begin{aligned}
\int_0^{\infty} d \omega \text{Re} \sigma_{\alpha \alpha}(\omega) = \frac{\pi e^2 N}{2 m_e L^3}
\end{aligned}
$$

那么，积分的收敛与否（$\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} $有限与否）就需要看电导率在$\omega \rightarrow 0$的信息。

而$\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$有限与否，与多体系统的局域程度直接关联，我们可以定义$\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$有限，则多体基态波函数是“局域”的（Localized），而发散则为"非局域"的（Delocalized）。

通过上面的推导，我们便成功的将多体基态波函数的“局域”程度定量的表示，并与系统的static longitudinal conductivity联系了起来。

**注意，这只和基态信息有关！**

## Metal or Insulator？

下面我们终于可以回答本文最初的问题：**只看基态如何区分导体和绝缘体？**

对于有能隙的系统，由于所有的激发能$\hbar \omega_{0n} \geq E_g$，从电导率的线性响应公式$\text{Re} \sigma_{\alpha \beta}^{(+)}(\omega) \simeq \sum \delta\left(\omega-\omega_{0 n}\right)$，显然$\omega \rightarrow 0$时电导为0，是绝缘体。

从而$\text{Re} \sigma_{\alpha \beta}^{(+)}(\omega) \simeq \sum \delta\left(\omega-\omega_{0 n}\right)$的积分下限可以改为$E_g/\hbar > 0$

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_{E_{\mathrm{g} /} \hbar}^{\infty} \frac{d \omega}{\omega} \text{Re} \sigma_{\alpha \alpha}(\omega)
\end{aligned}
$$

$$
\begin{aligned}
<\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{E_{\mathrm{g}}/\hbar} \text{Re} \sigma_{\alpha \alpha}(\omega) =\frac{\hbar^2}{2 m_e E_{\mathrm{g}}}
\end{aligned}
$$

这说明$\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$有上界，是有限的，即我们之前定义的**局域的多体基态**。

这样，我们就可以完全用多体基态的局域程度判断系统是绝缘体还是导体：

$$
\begin{aligned}
\text{多体基态“局域”化} \Leftrightarrow \text{系统是绝缘体}(E_g>0)
\end{aligned}
$$

反之，对于static longitudinal conductivty $\lim_{\omega \rightarrow 0} \text{Re} \sigma_{\alpha \alpha}(\omega) > 0$的导体（metal），我们发现上述积分在$\omega \rightarrow 0$处：

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} \simeq \frac{\hbar L^3 }{\pi e^2 N} \lim_{\omega \rightarrow 0} \text{Re} \sigma_{\alpha \alpha}(\omega)\int_{0}^{\infty} \frac{d \omega}{\omega} 
\end{aligned}
$$

显然在$\omega \rightarrow 0$处发散，从而$\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} = \infty$。

这样我们便有：

$$
\begin{aligned}
\text{多体基态“非局域”化} \Leftrightarrow \text{系统是导体}
\end{aligned}
$$

当然，还有一类特殊情况，即无能隙的情况$E_g = 0$，此时多体基态的“局域”化与否仍然取决于static longitudinal conductivty $\lim_{\omega \rightarrow 0} \text{Re} \sigma_{\alpha \alpha}(\omega)$的行为。例如$\lim_{\omega \rightarrow 0} \text{Re} \sigma_{\alpha \alpha}(\omega) \propto \omega^{\alpha \geq 1}$，则多体基态仍是局域化的，是绝缘体；反之$\lim_{\omega \rightarrow 0} \text{Re} \sigma_{\alpha \alpha}(\omega) \propto \omega^{\alpha < 1}$，则多体基态仍是非局域化的，是导体。

其中强无序的Anderson Insulator属于前者，因为无序系统的迁移率边（mobility edge）外虽然是能谱，可以让系统无能隙，但迁移率边外的电子态发生了Anderson Localization不贡献电导，故整体还是绝缘体；而band metal或者弱无序，弱关联的导体系统属于后者。

这样，我们对任意的多体体系（无论有无对称性，无序，强关联，etc,）我们只看多体基态波函数的电子局域程度，就能区分所有的绝缘体和导体。

## Summary

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} < \infty \Leftrightarrow \text{多体基态“局域”化} \Leftrightarrow \text{系统是绝缘体}
\end{aligned}
$$

$$
\begin{aligned}
\text{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} = \infty \Leftrightarrow \text{多体基态“非局域”化} \Leftrightarrow \text{系统是导体}
\end{aligned}
$$

## Reference

- [1] Kohn W. [Theory of the insulating state](https://journals.aps.org/pr/abstract/10.1103/PhysRev.133.A171). Physical review, 1964, 133(1A): A171.

- [2] Resta, R., & Sorella, S. (1999). [Electron localization in the insulating state](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.82.370). Physical Review Letters, 82(2), 370.

- [3] Souza, I., Wilkens, T., & Martin, R. M. (2000). [Polarization and localization in insulators: Generating function approach](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.62.1666). Physical Review B, 62(3), 1666.

- [4] Marzari, N., Mostofi, A. A., Yates, J. R., Souza, I., & Vanderbilt, D. (2012). [Maximally localized Wannier functions: Theory and applications](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419). Reviews of Modern Physics, 84(4), 1419.

- [5] Lee, C. H., Thomale, R., & Qi, X. L. (2013). [Pseudopotential formalism for fractional Chern insulators](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.035101). Physical Review B, 88(3), 035101.

- [6] Marzari, N., & Vanderbilt, D. (1997). [Maximally localized generalized Wannier functions for composite energy bands](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847). Physical review B, 56(20), 12847.

- [7] Resta, R. (2002). [Why are insulators insulating and metals conducting?](https://iopscience.iop.org/article/10.1088/0953-8984/14/20/201). Journal of Physics: Condensed Matter, 14(20), R625.

- [8] Resta, R. (2022). Geometry and topology in electronic structure theory. Università degli Studi di Trieste.
