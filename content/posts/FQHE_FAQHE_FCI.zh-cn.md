---
title: "🧐分数量子霍尔效应(FQHE)、分数反常量子霍尔效应(FAQHE)与分数陈绝缘体(FCI)"
date: 2022-10-17T22:30:00-05:00
draft: false
math: true
tags: ["Topology", "Quantum Hall Effect", "FCI"]
categories: ["Physics Notes"]
---

本note全文约10000字，旨在帮助读者入门分数量子霍尔效应、分数反常量子霍尔效应以及分数陈绝缘体的相关内容。本文仅为一己之见，有很多疏漏，还望读者不吝赐教。下面是正文～

<!--more-->

## Introduction to FQHE, FAQHE & FCI

量子霍尔效应需要强磁场环境才能实现，而Haldane Model以及陈绝缘体的出现使得量子霍尔效应得以在**无外磁场的晶格系统**中便能实现。这种现象称为“量子反常霍尔效应”，在陈绝缘体中，非平庸的Berry Curvature分布使得晶格体系具有了类似量子霍尔效应的非平庸拓扑性质，或者更进一步，**Berry Curvature取代了磁场**（虽然Berry Curvature定义在在倒空间中，而磁场出现在实空间中）。由它引申出的对陈绝缘体及其他拓扑相的讨论也成为前些年凝聚态理论领域的热点话题。

![Image](https://pic4.zhimg.com/80/v2-2449ec0b77d9fbfb23b817aa27e8b73a.png)

另一方面，当磁场强度足够大，使得电子全部简并在最低朗道能级(Lowest Landau Level, LLL)，特别是当一个电子平均占有整数（或分数）个量子磁通时，分数量子霍尔效应便出现了。与量子霍尔效应、量子反常霍尔效应或是一般的拓扑绝缘体不同，分数量子霍尔效应是LLL中简并**电子强相互作用**的结果，而之前的讨论基本限于non-interacting的有能隙费米系统。

分数量子霍尔体系有着拓扑相关的基态简并度(Ground State Degeneracy, GSD)、分数激发与任意子统计，这可能应用于拓扑量子计算等领域，但需要比量子霍尔效应更强的磁场这一条件便能“**劝退**”很多想要应用化该效应的人。

类似英语语法中的各种时态，我们也想用“反常”和“分数”组合出一种新的量子霍尔效应，及“**分数反常量子霍尔效应**”（Fractional Anomalous Quantum Hall Effect, FAQHE），**简称“FAQ”**（“发Q”）。

![Image](https://pic4.zhimg.com/80/v2-6b707548a72e327c6613a30b75d0645b.png)

特别地，我们希望这一现象在格点体系中便能实现。结合量子反常霍尔效应在陈绝缘体中的实现，物理学家们便把目光投向了陈绝缘体中拓扑非平庸的Chern Band，并仿照分数填布的LLL，在Chern Band中进行1/3、1/5、1/7...的电子数填布，并给系统Hamiltonian加上电子-电子关联项（例如Hubbard Model），来观测这种分数填布的陈绝缘体是否能表现出类似FQH体系的现象（之前提到的GSD、分数激发、任意子统计等）。

在对分数填布、拓扑非平庸的Haldane Model、Kagome Lattice等体系的数值模拟中，确实观测到了热力学极限下有限大的many-body gap、非平庸的GSD、分数激发等现象，物理学家们便把这种新奇的拓扑物态命名为“**分数陈绝缘体**”(Fractional Chern Insulator, FCI)。

## Physics in L.L.L.

为了将（近）自由电子气系统中的分数量子霍尔效应“**无缝衔接**”到陈绝缘体的晶格系统中，我们首先回顾最低朗道能级(L.L.L.)中的物理。

磁场中电子的Hamiltonian：

$$
\begin{aligned}
H=\frac{1}{2 m}\left( \hat{\mathbf{p}} + e \mathbf{A}(\hat{\mathbf{r}}) \right)^2 = \frac{\boldsymbol{\pi}^2}{2m}
\end{aligned}
$$

对于恒定外磁场中的自由电子气，可以不选取特定规范计算Landau能级，也可以在Landau Gauge和Symmetric Gauge下严格求解单电子波函数。

### Analysis without Gauge

$$
\begin{aligned}
\boldsymbol{\pi}=\mathbf{p}+e \mathbf{A}=m \dot{\mathbf{x}}
\end{aligned}
$$

$$
\begin{aligned}
{\left[\pi_x, \pi_y\right]=-i e \hbar B}
\end{aligned}
$$

$$
\begin{aligned}
a=\frac{1}{\sqrt{2 e \hbar B}}\left(\pi_x-i \pi_y\right) \text { and } a^{\dagger}=\frac{1}{\sqrt{2 e \hbar B}}\left(\pi_x+i \pi_y\right)
\end{aligned}
$$

$$
\begin{aligned}
{\left[a, a^{\dagger}\right]=1}
\end{aligned}
$$

$$
\begin{aligned}
H=\frac{1}{2 m} \boldsymbol{\pi} \cdot \boldsymbol{\pi}=\hbar \omega_B\left(a^{\dagger} a+\frac{1}{2}\right)
\end{aligned}
$$

$$
\begin{aligned}
E_n=\hbar \omega_B\left(n+\frac{1}{2}\right) \quad n \in \mathbf{N}
\end{aligned}
$$

很快啊，我们便得到了Landau能级的结构，但我们并不知道Landau能级的简并度等信息。


### Landau Gauge

Landau Gauge破坏了x方向的平移对称性，而$k_y$为好量子数，对应的的本征波函数在x方向局域化（x方向谐振子波函数+y方向平面波）。

$$
\begin{aligned}
\nabla \times \mathbf{A}=B \hat{\mathbf{z}} \quad \mathbf{A}=x B \hat{\mathbf{y}}
\end{aligned}
$$

则Hamiltonian为，

$$
\begin{aligned}
H=\frac{1}{2 m}\left(p_x^2+\left(p_y+e B x\right)^2\right)
\end{aligned}
$$

$p_y$为好量子数，则波函数可写为：

$$
\begin{aligned}
\psi_k(x, y)=e^{i k y} f_k(x)
\end{aligned}
$$

$p_y = \hbar k$的Hamiltonian，不难看出为原点平移的谐振子：

$$
\begin{aligned}
H_k=\frac{1}{2 m} p_x^2+\frac{m \omega_B^2}{2}\left(x+k l_B^2\right)^2
\end{aligned}
$$

能谱和波函数：

$$
\begin{aligned}
E_n=\hbar \omega_B\left(n+\frac{1}{2}\right)
\end{aligned}
$$

$$
\begin{aligned}
\psi_{n, k}(x, y) \sim e^{i k y} H_n\left(x+k l_B^2\right) e^{-\left(x+k l_B^2\right)^2 / 2 l_B^2}
\end{aligned}
$$

Landau Level的简并度可以这么考虑，y方向若为周期边条件，则$k\in \frac{2\pi}{L_y}\mathbb{N}$，而局域在$x = -kl_B^2$附近的谐振子波函数还要满足$x \in [0,L_x]$，从而简并度为：

$$
\begin{aligned}
\mathcal{N}=\frac{L_y}{2 \pi} \int_{-L_x / l_B^2}^0 \quad d k=\frac{L_x L_y}{2 \pi l_B^2}=\frac{e B A}{2 \pi \hbar}
\end{aligned}
$$

这等价于系统的量子磁通数：

$$
\begin{aligned}
\mathcal{N}=\frac{A B}{\Phi_0} \quad \text { with } \quad \Phi_0=\frac{2 \pi \hbar}{e}
\end{aligned}
$$

之后我们会看到这可以和$\mathcal{C}=1$的陈绝缘体中的Wannier Function $W(x,k_y)$类比，从而给出FQH state与FCI state的衔接方式。这方面的内容在10年代XL Qi的文章中有详细介绍。

### Symmetric Gauge

Symmetric Gauge：

$$
\begin{aligned}
\mathrm{A}=-\frac{1}{2} \mathrm{r} \times \mathbf{B}=-\frac{y B}{2} \hat{\mathbf{x}}+\frac{x B}{2} \hat{\mathbf{y}}
\end{aligned}
$$

类似分析另一种“动量算符”，并利用其对易关系构造新的“产生”、“湮灭”算符，这将给出landau能级的简并。

$$
\begin{aligned}
\tilde{\boldsymbol{\pi}}=\mathbf{p}-e \mathbf{A} \quad\left[\tilde{\pi}_x, \tilde{\pi}_y\right]=i e \hbar B
\end{aligned}
$$

$$
\begin{aligned}
{\left[\pi_i, \tilde{\pi}_j\right]=0}
\end{aligned}
$$

$$
\begin{aligned}
b=\frac{1}{\sqrt{2 e \hbar B}}\left(\tilde{\pi}_x+i \tilde{\pi}_y\right) \quad \text { and } \quad b^{\dagger}=\frac{1}{\sqrt{2 e \hbar B}}\left(\tilde{\pi}_x-i \tilde{\pi}_y\right)
\end{aligned}
$$

$$
\begin{aligned}
{\left[b, b^{\dagger}\right]=1 \quad|n, m\rangle=\frac{a^{\dagger n} b^{\dagger m}}{\sqrt{n ! m !}}|0,0\rangle}
\end{aligned}
$$

可以将x-y平面的波函数用复空间描述：

$$
\begin{aligned}
z=x-i y \quad \text { and } \quad \bar{z}=x+i y
\end{aligned}
$$

$$
\begin{aligned}
\partial=\frac{1}{2}\left(\frac{\partial}{\partial x}+i \frac{\partial}{\partial y}\right) \quad \text { and } \quad \bar{\partial}=\frac{1}{2}\left(\frac{\partial}{\partial x}-i \frac{\partial}{\partial y}\right)
\end{aligned}
$$

从而：

$$
\begin{aligned}
a=-i \sqrt{2}\left(l_B \bar{\partial}+\frac{z}{4 l_B}\right)
\end{aligned}
$$

$$
\begin{aligned}
a^{\dagger}=-i \sqrt{2}\left(l_B \partial-\frac{\bar{z}}{4 l_B}\right)
\end{aligned}
$$

可证明被$a$湮灭的LLL波函数有如下形式：

$$
\begin{aligned}
\psi_{L L L} \sim f(z) e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

被$b$湮灭的LLL内最低简并量子数$m=0$对应的波函数为：

$$
\begin{aligned}
\psi_{L L L, m=0} \sim  e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

对应的，其他简并量子数$m$对应的LLL波函数为

$$
\begin{aligned}
\psi_{L L L, m} \sim\left(\frac{z}{l_B}\right)^m e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

可以发现，这个函数大约在$\rho = \sqrt{x^2+ y^2} = \sqrt{2ml_B^2}$处达到极大，即波函数局域在半径为$\rho = \sqrt{2ml_B^2}$圈上。

![Image](https://pic4.zhimg.com/80/v2-a641fbd050367403775101747437e57d.png)

也可以计算Landau能级的简并度，对于有限大的圆盘体系，设半径为R，则$\rho_{max} = \sqrt{2m_{max}l_B^2} = \sqrt{2\mathcal{N}l_B^2}$，则

$$
\begin{aligned}
\mathcal{N} = \frac{\pi R^2 B}{\Phi_0}
\end{aligned}
$$

这从另一个角度给出了Landau能级的简并度。

Symmetric Gauge下的本征波函数在某一半径附近局域化，角动量$J$为好量子数，其波函数可以写成自变量为$z = x + i y$及其共轭$\bar{z}$的函数，其中L.L.L.中的波函数可以写成解析函数$f(z)$与指数因子$exp(-\bar{z}z/4l_B^2)$的乘积。

之后我们会看到，L.L.L.中波函数指数因子前的函数的解析性，即$f(z)$与$\bar{z}$无关这一性质，对于之后考虑投影到L.L.L.上的物理（即把考虑的Hilbert空间限制在到L.L.L.上的波函数）十分重要，而考虑投影到L.L.L.上的物理对于分析FQH中的中性激发（magneto-roton excitation）十分重要。这在80年代GMP(Girvin, MacDonald, Platzman)三人关于FQH系统中magneto-roton excitation的文章中有详细介绍。不过GMP三人的分析进给出了FQH系统低能激发的一个ansatz variational wave function，对于变分方法，只能给出激发能量的上限。

之后我们还会看到，FQH系统中投影到L.L.L.上的电子密度算符会满足特殊的GMR Algebra（或者称为$W_\infty$ Algebra），这对于在陈绝缘体中FCI phase的出现及其稳定性分析有着重要作用。为了在Chern Band中实现这一Algebra从而实现可能的FCI phase，Chern Band必须拥有接近恒定的Berry Curvature和接近恒定的Fubiny-Study度规，这又会牵扯到对Chern Band的Quantum Geometry的限制。这在Rahul Roy等人10年代关于FCI, GMR Algebra, Geometric Stability的一系列文章中有详细介绍。

## Laughlin Wave Function

Laughlin天才地提（猜）出了L.L.L.处于1/m占据的many-body wave-function形式。

首先考虑填布数$\nu = 1$的多体波函数，应当为单体波函数的完全反对称化形式，即：

$$
\begin{aligned}
\Psi_m=\prod_{i < j}\left(z_{\imath}-z_{\jmath}\right)^m e^{\frac{1}{4 l_\beta^2} \sum\left|z_2\right|^2}
\end{aligned}
$$

此时i粒子的幂次为$m(N-1)$，从而根据单电子LLL的角动量和半径的关系，可以得到

$$
\begin{aligned}
r_{\max }=\sqrt{2 \times m(N-1)} l_B
\end{aligned}
$$

从而可以推出朗道能级的简并度为

$$
\begin{aligned}
\mathcal{N} = \pi r_{max}^2/\Phi_0 \approx mN
\end{aligned}
$$

从而朗道能级填布数确实为$1/m$

### Normalizaiton & Plasma Analogy

我们经常在FQH系统中听到Plasma analogy，这事实上是计算Laughlin State以及其他准粒子、准空穴激发态的多体波函数的归一化系数时用的一个技巧。

通过类比，波函数的模平方被转化为求解某个有限温度的经典2维电子气的经典配分函数。而归一化系数的计算对于我们分析准空穴激发在FQH系统中移动导致的Berry Phase有重要作用。

未归一化Laughlin State的模平方为：

$$
\begin{aligned}
\left|\Psi_m\left(z_1 \cdots z_N\right)\right|^2=e^{-\beta V\left(z_1 \cdot z_N\right)}
\end{aligned}
$$

这正比于概率分布。

定义“伪温度”和能量为：

$$
\begin{aligned}
\beta=\frac{2}{m} \quad V=-m^2 \sum_{i < j} \ln \left|z_i-z_{j}\right|+\frac{m}{4} \sum_i\left|z_i\right|^2 \frac{1}{l_B^2}
\end{aligned}
$$

可以看出能量$V$为在$-1/l_B^2$密度均匀二维背景电荷上，在$\{z_i\}_{i=1}^N$位置加上电荷量为$m$的二维电子气系统。

### Review of 2D Plasma

密度均匀二维背景电荷及其电势的Laplace方程$-\nabla^2\phi=\rho$（略去一些物理常数）：

$$
\begin{aligned}
-\nabla^2\left(\frac{|z|^2}{4 l_B^2}\right)=-\frac{1}{l_B^2}
\end{aligned}
$$

二维点电荷的电势分布：

$$
\begin{aligned}
-\nabla^2 \phi=2 \pi q \delta^2(\mathbf{r}) \Rightarrow \phi=-q \log \left(\frac{r}{l_B}\right)
\end{aligned}
$$

从而点电荷之间的相互作用电势能为：

$$
\begin{aligned}
V = -m^2 \sum_{i < j} \ln \left|z_i-z_{j}\right|
\end{aligned}
$$

点电荷在均匀背景电荷中的电势能为：

$$
\begin{aligned}
V = \frac{m}{4} \sum_i\left|z_i\right|^2 \frac{1}{l_B^2}
\end{aligned}
$$

再回到归一化系数的计算：

$$
\begin{aligned}
C = \int \prod_i d^2z_i \left|\Psi_m\left(z_1 \cdots z_N\right)\right|^2  = \int \prod_i d^2z_i e^{-\beta V\left(z_1 \cdot z_N\right)}
\end{aligned}
$$

这相当于按照概率$e^{-\beta V\left(z_1 \cdot z_N\right)}$对点电荷所有可能位形进行积分，所以归一化系数$C$的计算被转化为配分函数的计算。

## Anyonic Excitation

关于任意子(Anyon)的介绍，可以参考文小刚老师的多体物理书第七章《量子霍尔态系统》的开头几节。就结论而言，二维系统可以有任意子统计，而三维系统只有波色或费米子统计。这可以从n维全同粒子的位形空间的拓扑性质来考虑。

下面来介绍FQH中的准粒子和准空穴激发。

### Quasi-hole & Quasi-particle

准空穴的波函数为：

$$
\begin{aligned}
\psi_{\text {hole }}(z ; \eta)=\prod_{i=1}^N\left(z_i-\eta\right) \prod_{k < l}\left(z_k-z_l\right)^m e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

这相当于只要有任意一个电子的位置位于$z = \eta$，则振幅为0，此处电子云密度为0，故称为“准空穴激发”。

进一步，若有m个这样的空穴均位于一个位置，则波函数为：

$$
\begin{aligned}
\psi_{\mathrm{m}-\mathrm{hole}}(z ; \eta)=\prod_{i=1}^N\left(z_i-\eta\right)^m \prod_{k < l}\left(z_k-z_l\right)^m e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

这事实上是将一个电子位置的动力学量$z$，替换成了一个参数，相当于去掉一个电子，从这里可以naive的推想一个空穴相当于去掉$1/m$个电子，从而不难猜想其分数电荷和任意子统计。

有了“准空穴”，我们便会想怎么加“准粒子”，naive的想，我们想在系统中将$\prod_{i=1}^N\left(z_i-\eta\right)$给除掉，但这并非一个好的定义。

而我们意识到除掉一个因子一定程度上等价于作偏导，再加上一些常数项修正，我们给出“准粒子”激发的波函数：

$$
\begin{aligned}
\psi_{\text {particle }}(z, \eta)=\left[\prod_{i=1}^N\left(2 \frac{\partial}{\partial z_i}-\bar{\eta}\right) \prod_{k < l}\left(z_k-z_l\right)^m\right] e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

### Again, Normalization & Plasma Analogy

类似的，我们以准空穴激发为例，计算其多体波函数的归一化系数，把各项全部写到指数上，并去掉温度因子$\beta = 2/m$之后，我们得到“伪能量”为：

$$
\begin{aligned}
U\left(z_i;\xi\right)=-m^2 \sum_{i < j} \log \left(\frac{\left|z_i-z_j\right|}{l_B}\right)-m \sum_i \log \left(\frac{\left|z_i-\xi\right|}{l_B}\right)+\frac{m}{4 l_B^2} \sum_{i=1}^N\left|z_i\right|^2
\end{aligned}
$$

其中$-m \sum_i \log \left(\frac{\left|z_i-\eta\right|}{l_B}\right)$代表了“电荷量”为$1$的“准空穴”与“电荷量”为$m$的电荷之间的排斥作用势。但相比真实的系统，我们还差一项“准空穴”与“背景电荷”的相互作用。

因此我们补上这一项，并在指数因子$e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}$前补上一个因子$e^{-\frac{1}{2 m l_B^2}|\xi|^2}$来抵消加上这一项的影响。

现在再来算归一化系数：

$$
\begin{aligned}
C = e^{-\frac{1}{2 m l_B^2}|\xi|^2} \int \prod_i d^2 z_i\left| \prod\left(\xi-z_i\right) \prod\left(z_i-z_j\right)^m e^{-\frac{1}{4 i_B^2}\left|z_i\right|^2}\right|^2 = e^{-\frac{1}{2 m l_B^2}|\xi|^2} \int \prod_i d^2 z_i e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}
\end{aligned}
$$

其中$\int \prod_i d^2 z_i e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}$部分为“位于$\{z_i\}$、m电荷量电荷”+“位于$\xi$、1电荷量准空穴”+“均匀背景电荷”这个2维Plasma系统的经典配分函数。

定性分析，由于配分函数中对所有电荷位形积分，所以作为参量的准空穴位置$\xi$事实上应当不影响配分函数的结果，所以配分函数部分是一个与$\xi$的常数，从而有

$$
\begin{aligned}
C\left(\xi, \xi^*\right) = \text{const} \times e^{\frac{1}{2 l_B^2} \frac{1}{m}|\xi|^2}
\end{aligned}
$$

归一化系数的计算对于我们分析准空穴激发在FQH系统中移动导致的Berry Phase有重要作用。

### Berry Phase from a moving Quasi-hole

准空穴移动前后的相位变化为：

$$
\begin{aligned}
\left\langle\Psi^h\left[\xi(t+\Delta t), \xi^*(t+\Delta t)\right] \mid \Psi^h\left[\xi(t), \xi^*(t)\right]\right\rangle=e^{i \Delta t a \cdot x}
\end{aligned}
$$

这等价于：

$$
\begin{aligned}
\boldsymbol{a} \cdot \dot{x}=i\left\langle\Psi^h\left[\xi(t), \xi^*(t)\right]\left|\frac{d}{d t}\right| \Psi^h\left[\xi(t), \xi^*(t)\right]\right\rangle
\end{aligned}
$$

$$
\begin{aligned}
=\frac{d \xi}{d t} i\left\langle\Psi^h\left(\xi, \xi^*\right)\left|\frac{\partial}{\partial \xi}\right| \Psi^h\left(\xi, \xi^*\right)\right\rangle+\frac{d \xi^*}{d t} i\left\langle\Psi^h\left(\xi, \xi^*\right)\left|\frac{\partial}{\partial \xi^*}\right| \Psi^h\left(\xi, \xi^*\right)\right\rangle
\end{aligned}
$$

可以写成：

$$
\begin{aligned}
\boldsymbol{a} \cdot d \boldsymbol{x}=a_{\xi} d \xi+a_{\xi^*} d \xi^*
\end{aligned}
$$

其中$a_{\xi},\,a_{\xi^*}$为准空穴位置$\xi$的参数空间中的Berry Connection，此处定义在复空间上，为了保证相位是实数，故有上述形式。

**上述的准空穴激发波函数均已归一化。**

未归一的准空穴激发波函数的归一化系数：

$$
\begin{aligned}
\langle\Psi(\xi) \mid \Psi(\xi)\rangle=C\left(\xi, \xi^*\right)
\end{aligned}
$$

从而：

$$
\begin{aligned}
i\left\langle\Psi^h\left(\xi, \xi^*\right)\left|\frac{\partial}{\partial \xi^{\prime}}\right| \Psi^h\left(\xi, \xi^*\right)\right)=i\left\langle\Psi(\xi)\left|\frac{1}{\sqrt{C\left(\xi, \xi^*\right)}} \frac{\partial}{\partial \xi} \frac{1}{\sqrt{C\left(\xi, \xi^*\right)}}\right| \Psi(\xi)\right\rangle
\end{aligned}
$$

$$
\begin{aligned}
=i \int \prod_i d^2 z_i \Psi^*\left(\xi^*\right) \frac{1}{\sqrt{C}} \frac{\partial}{\partial \xi}\left(\frac{1}{\sqrt{C}} \Psi(\xi)\right)
\end{aligned}
$$

$$
\begin{aligned}
=i \frac{\partial}{\partial \xi} \int \prod_i d^2 z_2 \Psi^*\left(\xi^*\right) \frac{1}{C} \Psi(\xi)-i \int \prod_i d^2 z_2 \Psi^*\left(\xi^*\right)\left(\frac{\partial}{\partial \xi} \frac{1}{\sqrt{C}}\right) \frac{1}{\sqrt{C}} \Psi(\xi)
\end{aligned}
$$

$$
\begin{aligned}
=-\mathfrak{\imath} \sqrt{C} \frac{\partial}{\partial \xi} \frac{1}{\sqrt{C}}
\end{aligned}
$$

$$
\begin{aligned}
a_{\xi}=+\frac{i}{2} \frac{\partial}{\partial \xi} \ln C, \quad a_{\xi^*}=-\frac{i}{2} \frac{\partial}{\partial \xi^*} \ln C
\end{aligned}
$$

这时我们之前利用一大串Plasma Analogy推导的归一化系数的形式便有了用武之地。由于常数项并不贡献在$\ln C$的导数中，所以有：

$$
\begin{aligned}
a_{\xi}=i \frac{1}{m} \frac{1}{4 l_B^2} \xi^*, \quad a_{\xi^*}=-i \frac{1}{m} \frac{1}{4 l_B^2} \xi
\end{aligned}
$$

这可以写成：

$$
\begin{aligned}
a_{\xi}=-\frac{1}{m} q_e A^z, \quad a_{\xi^*}=-\frac{1}{m} q_e A^{z^*}
\end{aligned}
$$

其中复平面上的磁矢势为$A^z = \frac{1}{2}(A_x - iA_y)= \frac{1}{2} [( -\frac{By}{2} ) - i (\frac{Bx}{2})]$

虽然Berry Phase来自“准空穴”激发的位置$\xi$的在参数空间中的运动，我们可以将这个效果等价理解为，一个$e^\star$电荷量的粒子在磁场中运动产生的AB相位：

$$
\begin{aligned}
\oint d \boldsymbol{x} \cdot \boldsymbol{a}=\left(-\frac{q_c}{m}\right) \oint d \boldsymbol{x} \cdot \boldsymbol{A}
\end{aligned}
$$

从而“准空穴”相当于带有电荷量：

$$
\begin{aligned}
e^{\star}=\frac{e}{m}
\end{aligned}
$$

类似的，如果我们分析两个准空穴激发，及其互统计（具体而言，就是两个空穴交换位置会导致的相位变化，若为$0$就是波色子，$\pi$则为费米子，其余则为任意子）。

### Anyonic Statistics

为了能用Plasma Analogy来计算归一化系数，从而计算规范势，我们要在之前的“伪配分函数”的指数项中加入“准空穴”之间的相互作用，以及“准空穴”和“背景电荷”的作用。

只要两个“准空穴”激发的位置足够远，我们总可以认为配分函数与两者位置无关，可以得到归一化系数对两个“准空穴”激发的位置$\xi_1,\,\xi_2$的dependence：

$$
\begin{aligned}
C\left(\xi_1, \xi_2\right) \propto e^{\frac{1}{22_B^2} \frac{1}{m}\left(\left|\xi_1\right|^2+\left|\xi_2\right|^2\right)}\left|\xi_1-\xi_2\right|^{-\frac{2}{m}}
\end{aligned}
$$

为了考虑他们之间的统计，我们令第二个准空穴不动，然后让第一个准空穴绕它走一圈，这相当于交换了两次位置，同时还要考虑等效电荷$e^{\star}=\frac{e}{m}$绕一圈的磁通对应的AB phase。

其实总体的相位变化就是Berry Phase，只不过我们硬要赋予准空穴一个电荷$e^{\star}=\frac{e}{m}$来模拟AB Phase，并赋予他们和总Berry Phase对应的互统计，使得我们对这个Berry Phase的产生有更物理的解释。

![Image](https://pic4.zhimg.com/80/v2-ed0ea7e6cd8f318bbfe6e1b03cd5a7a3.png)

令：

$$
\begin{aligned}
\xi=\xi_1 \text { and } \xi_2=0
\end{aligned}
$$

规范势：

$$
\begin{aligned}
a_{\xi}=i \frac{1}{m} \frac{1}{4 l_B^2} \xi^*-\frac{i}{2 m} \frac{\partial}{\partial \xi} \ln |\xi|^2=i \frac{1}{m} \frac{1}{4 l_B^2} \xi^*-\frac{i}{2 m} \frac{1}{\xi}
\end{aligned}
$$

$$
\begin{aligned}
a_{\xi^*}=-i \frac{1}{m} \frac{1}{4 l_B^2} \xi+\frac{i}{2 m} \frac{1}{\xi^*} \text {. }
\end{aligned}
$$

规范势在第一个空穴绕第二个空穴一圈的轨迹上的线积分给出总Berry Phase，我们用分数电荷的AB Phase以及两个空穴的互统计去描述它：

$$
\begin{aligned}
\text{AB Phase} + 2\theta = \frac{e}{m} B \times \text { 面积 }+\frac{2 \pi}{m}
\end{aligned}
$$

从而交换一次的相位变化为：

$$
\begin{aligned}
\theta=\frac{\pi}{m}
\end{aligned}
$$

可见分数激发确实有任意子形式的互统计。这种任意子统计对于拓扑量子计算意义重大。

## Collective Neutral Excitation & GMP Algebra

Girvin, MacDonald, Platzman三人在80年代分析了FQH体系中的collective neutral excitation，这种集体激发是 destabilize FQH phase的重要因素，其中引申出的GMP Algebra也可能与FCI相的稳定性有重要关联。

因此我们先来分析FQH系统中的collective neutral excitation，再来分析其中的GMP Algebra进入对Many-Body Gap的分析中。

我们并不会具体分析Many-Body Gap怎么计算，只是大概给出思路，具体的计算可以参考Girvin, MacDonald, Platzman在80年代的原始文献，或者参考Gabriele Giuliani, Giovanni Vignale的"Quantum Theory of the Electron Liquid"一书Chapter 10。

### Ansatz Excitation Wave Function

Girvin, MacDonald, Platzman类比了$^4He$体系的集体激发，给出了一个试探性的激发态波函数：

$$
\begin{aligned}
\left|\psi_{\vec{q}}\right\rangle=\hat{\bar{n}}_{\vec{q}}\left|\psi_0\right\rangle
\end{aligned}
$$

其中$\left|\psi_0\right\rangle$为Laughlin波函数，位于L.L.L.中。$\hat{n}_{\vec{q}}$为动量空间的粒子数算符：

$$
\begin{aligned}
\hat{n}_{\vec{q}}=\sum_{n, n^{\prime}, k_y, k_y^{\prime}}\left\langle n^{\prime}, k_y^{\prime}\left|e^{-i \vec{q} \cdot \vec{r}}\right| n, k_y\right\rangle \hat{a}_{n^{\prime}, k_y^{\prime}}^{\dagger} \hat{a}_{n, k_y}
\end{aligned}
$$

而$\hat{\bar{n}}_{\vec{q}}$则为投影到L.L.L.上的算符：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=\sum_{k_y, k_y^{\prime}}\left\langle 0, k_y^{\prime}\left|e^{-i \vec{q} \cdot \vec{r}}\right| 0, k_y\right\rangle \hat{a}_{0, k_y^{\prime}}^{\dagger} \hat{a}_{0, k_y}
\end{aligned}
$$

因为给算符可能将L.L.L.中的成分映射到更高的Landau Level中，这会增加我们试探解的能量，故我们通过投影把这部分去掉。

这样的试探解，又低能，又保留了基态波函数的关联，应该与真实的激发态差别不大，所以我们可以通过变分法，用试探解得到与激发态能量接近的一个的能量上限。

顺带一提，GMP的原始文献中给这种中性的集体激发命名为"Magneto-roton"，这与boson系统中的“roton”元激发也有关。不过boson系统的集体激发是无能隙的，而在我们的FQH系统中则是有gap的。

![Image](https://pic4.zhimg.com/80/v2-4555edb96992cd8697108dde7bbef308.png)

### Projection to L.L.L.

但问题便是，怎么实现到L.L.L.的投用，GMP的论文告诉我们，对坐标表象下的operator作如下变换即可：

$$
\begin{aligned}
z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}
\end{aligned}
$$

Naive地想，坐标表象下的operator应当是$z,\,z^*$的函数（总可以Taylor Expansion），从而只要知道$z,\,z^*$投影到L.L.L.的结果即可。位于L.L.L.上的波函数有如下形式：

$$
\begin{aligned}
\psi(z)=f(z) e^{-\frac{|z|^2}{4 \ell^2}}
\end{aligned}
$$

用$z$作用后，由于$zf(z)$仍为解析函数，所以$z$作用L.L.L.的波函数后，仍在L.L.L.上，不用变换。

而$z^*$不同，因为$z^*f(z)$会使得一部分波函数分量跑到更高的Landau Level上。

回忆Landau Level的升降算符：

$$
\begin{aligned}
a^{\dagger}=-i \sqrt{2}\left(l_B \partial-\frac{\bar{z}}{4 l_B}\right)
\end{aligned}
$$

这等价于：

$$
\begin{aligned}
\bar{z}=4l_B^2 \partial-i \frac{4 l_Ba^{\dagger}}{\sqrt{2}}
\end{aligned}
$$

可以看出$z^*$可以写成一个Landau Level提升算符（映射到更高Landau Level）和一个$\partial/\partial z$的部分，由于$\partial f(z)/\partial z$仍为解析函数，故投影后应当只剩下$\partial/\partial z$部分。注意此处用了前面的定义：

$$
\begin{aligned}
z=x-i y \quad \text { and } \quad \bar{z}=x+i y
\end{aligned}
$$

$$
\begin{aligned}
\partial=\frac{1}{2}\left(\frac{\partial}{\partial x}+i \frac{\partial}{\partial y}\right) \quad \text { and } \quad \bar{\partial}=\frac{1}{2}\left(\frac{\partial}{\partial x}-i \frac{\partial}{\partial y}\right)
\end{aligned}
$$

所以结果上和$z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}$有一些系数差别，但已足够理解为何$z^*$投影到L.L.L.后变成了$\partial_z$。

我们还有更详细的推导：

让L.L.L.上波函数的完全由指数前面的解析函数代替：

$$
\begin{aligned}
|\psi_f\rangle \equiv |f\rangle
\end{aligned}
$$

定义其内积（按照一个指数因子加权的内积）：

$$
\begin{aligned}
\langle g|f\rangle = \int g\left(z^*\right) f(z) e^{-\frac{|z|^2}{2 \ell^2}} d x d y
\end{aligned}
$$

从而在L.L.L.波函数空间（Hilbert子空间）中$z^*$的矩阵元$\langle g|z^*|f\rangle$为：

$$
\begin{aligned}
\int g\left(z^*\right) z^* f(z) e^{-\frac{|z|^2}{2 \ell^2}} d x d y
\end{aligned}
$$

将$z^*$写成对指数因子作$-2l^2 \partial_z$得到的：

$$
\begin{aligned}
\int g\left(z^*\right)\left[ - 2 \ell^2 \frac{\partial}{\partial z} e^{-\frac{|z|^2}{2 \ell^2}}\right] f(z) d x d y
\end{aligned}
$$

作**分部积分**，并利用$\partial_z g(z^*) = 0$，有

$$
\begin{aligned}
\int g\left(z^*\right)\left[2 \ell^2 \frac{\partial}{\partial z} f(z)\right] e^{-\frac{|z|^2}{2 \ell^2}} d x d y = \langle g |2 \ell^2 \frac{\partial}{\partial z}f\rangle
\end{aligned}
$$

注意此处的$2 \ell^2 \frac{\partial}{\partial z}$仅对指数前面的解析函数$f(z)$作用。

还有一个问题，如果同时有$z$和$z^*$，这在积分里可以随便交换次序，但$2 \ell^2 \frac{\partial}{\partial z}$不能和$z$随便交换顺序。

我们来考虑$zz^*$的投影结果：

$$
\begin{aligned}
\int g\left(z^*\right) z z^* f(z) e^{-\frac{-4}{2}} d x d y=\int g\left(z^*\right)\left[2 \ell^2 \frac{\partial}{\partial z} z f(z)\right] e^{-\frac{-3 x}{2 z}} d x d y
\end{aligned}
$$

可见，在分部积分时，$\partial_z$一定会把除了指数因子以外含有$z$的解析部分都包含进去，这相当于把所有$\partial_z$放到最左边，以便对所有的$z$算符“左作用”。

所以在做投影时，我们首先将算符写成$z,\,z^*$的函数，再把其中$z^*$的部分提到左边，即normal ordering，之后作替换$z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}$，即实现了一般算符到L.L.L.的投影。

接下来我们便可以作投影：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=\sum_{j=1}^N \overline{e^{-i \vec{q}^{\cdot} \cdot \hat{r}_j}} =\sum_{j=1}^N \overline{e^{-i \mathrm{q} z_j^* / 2} e^{-i \mathrm{q}^* z_j / 2}} =\sum_{j=1}^N e^{-i q \ell^2 \frac{\partial}{\partial z_j}} e^{-i q^* z_j / 2}
\end{aligned}
$$

可以作对易子，从而得到另一个等价表达

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=e^{-q^2 \ell^2 / 2} \sum_{j=1}^N e^{-i q^* z_j / 2} e^{-i q \ell^2 \frac{\partial}{\partial z_j}}
\end{aligned}
$$

### Variational Method for Excitation Spectrum

知道了怎么把算符投影到L.L.L.，我们便可以计算我们试探解的能量。

$$
\begin{aligned}
E_{\vec{q}}=\frac{\left\langle\psi_{\vec{q}}|\hat{H}| \psi_{\vec{q}}\right\rangle}{\left\langle\psi_{\vec{q}} \mid \psi_{\vec{q}}\right\rangle} = \frac{\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{H} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle}{\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle}
\end{aligned}
$$

可以通过对易操作，把分子变成：

$$
\begin{aligned}
E_0\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle+\frac{1}{2}\left\langle\psi_0\left|\left[\hat{\bar{n}}_{\vec{q}}^{\dagger},\left[\hat{H}, \hat{\bar{n}}_{\vec{q}}\right]\right]\right| \psi_0\right\rangle
\end{aligned}
$$

从而可以写成基态能+gap的表达式，$\bar{f}/\bar{S}$即gap：

$$
\begin{aligned}
E_{\vec{q}}=E_0+\frac{\bar{f}(\vec{q})}{\bar{S}(\vec{q})}
\end{aligned}
$$

其中，

$$
\begin{aligned}
\bar{f}(q) \equiv \frac{1}{2 N}\left\langle\psi_0\left|\left[\hat{\bar{n}}_{\vec{q}}^{\dagger},\left[\hat{H}, \hat{\bar{n}}_{\vec{q}}\right]\right]\right| \psi_0\right\rangle
\end{aligned}
$$

$$
\begin{aligned}
\bar{S}(q) \equiv \frac{1}{N}\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle
\end{aligned}
$$

下面进行对$\bar{f}$和$\bar{S}$的计算。

### Entrance of GMP Algebra

先来计算$\bar{S}$，可以证明：

$$
\begin{aligned}
\bar{S}(q)=S(q)-S_1(q)
\end{aligned}
$$

其中，$S$为无投影的基态结构因子:

$$
\begin{aligned}
S(q) \equiv \frac{1}{N}\left\langle\psi_0\left|\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}\right| \psi_0\right\rangle
\end{aligned}
$$

由于$\mathcal{P}_{LLL}|\psi_0\rangle=|\psi_0\rangle$，

$$
\begin{aligned}
S(q) = \frac{1}{N}\left\langle\psi_0\left|\mathcal{P}_{LLL}\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}\mathcal{P}_{LLL}\right| \psi_0\right\rangle = \frac{1}{N}\left\langle\psi_0\left|\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}\right| \psi_0\right\rangle
\end{aligned}
$$

而$S_1$为一个常数：

$$
\begin{aligned}
S_1(\vec{q})=1-e^{-q^2 \ell^2 / 2}
\end{aligned}
$$

推导要用到$\partial$和$z$的对易关系，从而将$\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}$和$\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}$联系起来：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}} \hat{\bar{n}}_{-\vec{q}} =\sum_j e^{-i q \ell^2 \frac{\partial}{\partial z_j}} e^{-i \frac{q^* z_j}{2}} \sum_k e^{+i q \ell^2 \frac{\partial}{\partial z_k}} e^{+i \frac{q^* z_k}{2}} =\sum_{j, k} e^{-i q \ell^2\left[\frac{\partial}{\partial z_j}-\frac{\partial}{\partial z_k}\right]} e^{-i q^*\left[\frac{z_j-z_k}{2}\right]} e^{-\frac{q^2 \ell^2}{2}\left[\frac{\partial}{\partial z_k}, z_j\right]}
\end{aligned}
$$

分析$j=k$和$j \neq k$的项，得到：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}} \hat{\bar{n}}_{-\vec{q}} = \overline{\hat{n}_{\vec{q}} \hat{n}_{-\vec{q}}}+N\left[e^{-\frac{q^2 \ell^2}{2}}-1\right] .
\end{aligned}
$$

从而得证$\bar{S}(q)=S(q)-S_1(q)$，这便把投影后算符的计算转化为计影前的计算。

由于$\mathcal{P}_{LLL}|\psi_0\rangle=|\psi_0\rangle$，$\mathcal{P}_{LLL}^2 = \mathcal{P}_{LLL}$，从而可以证明式中的$\hat{H}$换为投影算符原式结果不变。

$$
\begin{aligned}
\bar{f}(q) \equiv \frac{1}{2 N}\left\langle\psi_0\left|\left[\hat{n}_{\vec{q}}^{\dagger},\left[\hat{\bar{H}}, \hat{\bar{n}}_{\vec{q}}\right]\right]\right| \psi_0\right\rangle
\end{aligned}
$$

Hamiltonian可以仅考虑二体相互作用项，因为单体能量均简并在L.L.L.：

$$
\begin{aligned}
\bar{H}=\frac{1}{2 \mathcal{A}} \sum_{\vec{q}} v_q\left(\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}-N\right) =\frac{1}{2 \mathcal{A}} \sum_{\vec{q}} v_q\left(\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}-N e^{-q^2 \ell^2 / 2}\right)
\end{aligned}
$$

这样，我们便将$\bar{f}$中对易子的计算转化为了求解更基本的元素，即$\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]$对易子。

而$\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]$对易子的计算给出了**投影后密度算符的封闭李代数形式**，**这便是著名的GMP Algebra**。

$$
\begin{aligned}
\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]=\left(e^{\frac{\mathrm{k}^* q^2}{2}}-e^{\frac{\mathrm{kq}^* \ell^2}{2}}\right) \hat{\bar{n}}_{\vec{k}+\vec{q}}
\end{aligned}
$$

从而可以化简$\bar{f}$的计算：

$$
\begin{aligned}
\bar{f}(q)=2 \frac{e^{-\frac{q^2 \ell^2}{2}}}{\mathcal{A}} \sum_{\vec{k}} \sin ^2\left(\frac{\left(\vec{q} \times \vec{k} \ell^2\right) \cdot \vec{e}_z}{2}\right) \bar{S}(k)\left[v_{|\vec{k}-\vec{q}|} e^{\vec{k} \cdot \vec{q} \ell^2} e^{-\frac{q^2 \ell^2}{2}}-v_k\right]
\end{aligned}
$$

对于$\bar{f},\,\bar{S}$以及many-body的进一步计算，这里便不再赘述，重要的是，我们看到了GMP Algebra是如何进入many-body gap的计算的，虽然此处的变分法只能给出上限，但数值结果显示，这种近似已经十分精确。

其中在$q\rightarrow0$处，系统有有限gap，而gap的最小值大约在$q \sim 1/l_B$附近出现，仍为有限的many-body gap。而这一中性集体激发的gap对于FQH以及之后要研究的FCI相的稳定性，可能有重要影响。

![Image](https://pic4.zhimg.com/80/v2-f7c4dba63f3094a6a7a8ed265e8a547b.png)

### GMP Algebra & Geometric Stability Hypothesis

我们将GMP Algebra的精髓再提出：

$$
\begin{aligned}
\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]=\left(e^{\frac{\mathrm{k}^* q^2}{2}}-e^{\frac{\mathrm{kq}^* \ell^2}{2}}\right) \hat{\bar{n}}_{\vec{k}+\vec{q}}
\end{aligned}
$$

进一步推导可以发现它等价于：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=2 i \exp \left(\frac{\mathbf{q}_1 \cdot \mathbf{q}_2 \ell_B^2}{2}\right) \sin \left(\frac{\mathbf{q}_1 \wedge \mathbf{q}_2 \ell_B^2}{2}\right) \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}}
\end{aligned}
$$

$$
\begin{aligned}
\mathbf{q}_1 \wedge \mathbf{q}_2 \equiv \hat{\mathbf{z}} \cdot\left(\mathbf{q}_1 \times \mathbf{q}_2\right)
\end{aligned}
$$

如果换一个定义：

$$
\begin{aligned}
\mathcal{P} \rho_{\mathbf{q}} \mathcal{P}=e^{-q^2 \ell_B^2 / 4} e^{i \mathbf{q} \cdot \mathbf{R}} \equiv e^{-q^2 \ell_B^2 / 4} \bar{\rho}_{\mathbf{q}}
\end{aligned}
$$

则可以把前面的指数因子消去，得到另一种等价的GMP/$W_\infty$ Algebra：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=2 i \sin \left(\frac{\mathbf{q}_1 \wedge \mathbf{q}_2 \ell_B^2}{2}\right) \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}}
\end{aligned}
$$

在对FCI的分析中，一种很重要的途径是在lattice系统中再现投影到L.L.L.的动量空间粒子数算符$\hat{\bar{\rho}}_q$的GMP Algebra，因为这和最能destablize FQH state的neutral collective excitation最有关系。

为了在lattice系统中再现FQH的这种GMP代数结构，我们需要特殊的band geometry。而这种将band geometry与GMP Algebra与FCI的stability联系在一起的猜想，便是**Geometric Stability Hypothesis**。它在理论、数值和实验中分析FCI态是否出现及其稳定性时大有作用。

当然，完全复刻FQH的代数结构，这应当是FCI出现的一种必要条件，而不完全等价于FCI态的出现条件，这方面的理论尚待研究。

而数值方面，**Geometric Stability Hypothesis**已在基态兼并度、many-body gap等多种方面得到一定程度的验证。

## Ground State Degeneracy

FQH系统具有所在manifold拓扑性质相关的基态简并度(GSD)，这是数值或实验中分辨FQH及FCI相的一个重要判断因素。

此处我们用准粒子-准空穴对的产生湮灭作为简单的例子，说明系统基态的非简并性，及其与背景manifold拓扑性质的关系。

考虑由正方形对边粘连而成的torus上的FQH系统，即x-y方向均为周期边界条件的FQH系统。现在考虑准粒子-准空穴对的产生和湮灭，准粒子-准空穴可以绕torus的大圆一圈（x轴），先产生后湮灭；也可以绕torus的小圆一圈（y轴），先产生后湮灭。

![Image](https://pic4.zhimg.com/80/v2-667efdec16b00f1ca9e4c7080734752e.png)

将这两个过程的系统演化算符记为$\hat{T}_x$和$\hat{T}_y$，由于torus在x-y两个方向上均为周期边条件，我们可以证明$\hat{T}_x\hat{T}_y\hat{T}_x^{-1}\hat{T}_y^{-1}$的过程在torus上**拓扑等价于**准粒子绕准空穴一周。由于准粒子或准空穴的分数统计，这个过程产生的相位为$e^{2 \pi i/m}$，则有：

$$
\begin{aligned}
\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x
\end{aligned}
$$


由于整个过程从基态出发，在基态上产生准粒子-准空穴激发，之后又湮灭，回到基态（可能与原基态不同），则$\hat{T}_x$和$\hat{T}_y$仅在基态之间有矩阵元。

无论简并还是非简并，则$\hat{T}_x$和$\hat{T}_y$是在各个基态$|0_1\rangle,\dots,|0_{GSD}\rangle$为基底的线性空间上的矩阵。而求解$\hat{T}_x$和$\hat{T}_y$对应的矩阵，其实是$\hat{T}_x$和$\hat{T}_y$在基态空间中的群表示。

如果基态$|0\rangle$是非简并的，由于$\hat{T}_x$和$\hat{T}_y$过程最终均回到了基态，则最多产生一个相位，

$$
\begin{aligned}
\hat{T}_x |0\rangle = e^{i \gamma_x} |0\rangle
\end{aligned}
$$

$$
\begin{aligned}
\hat{T}_y |0\rangle = e^{i \gamma_y} |0\rangle
\end{aligned}
$$

但这样立马会产生矛盾，因为会有

$$
\begin{aligned}
\hat{T}_x \hat{T}_y |0\rangle = e^{i (\gamma_x + \gamma_y)} |0\rangle = \hat{T}_y \hat{T}_x |0\rangle
\end{aligned}
$$

事实上，从$\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x$告诉我们$\hat{T}_x,\,\hat{T}_y$的非Abel性开始，我们就应当意识到它们在基态空间中的群表示必然不会是1维的，即基态一定不简并！

进一步分析会发现，$\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x$关系对应的群表示至少为m维。

事实上，对于填布数$\nu = 1/m$、定义在$T^2$空间上的FQH系统，基态简并度为：

$$
\begin{aligned}
GSD = m
\end{aligned}
$$

这与FQH系统的背景manifold拓扑性质的关系也不难理解，我们上述的推导用到了：

“$\hat{T}_x\hat{T}_y\hat{T}_x^{-1}\hat{T}_y^{-1}$的过程在torus上**拓扑等价于**准粒子绕准空穴一周”

对于亏格不同的背景流形，不难想象更为复杂的拓扑性质会导致更奇异的基态兼并度。

## Effective Chern-Simons Theory

FQH系统的低能效应可以由Chern-Simons作用量来描述，这事实上是积掉高能部分后的一种有效场论，它对于分析FQH的分数Hall电导（线性响应）、分数激发、GSD，以及其他多层FQH对应的分数填充数有着重要作用。此处限于篇幅不再赘述。

## Flat Band

Chern Band基本起到了自由电子气中Landau Level的作用，但为了让interaction效应更加显著，我们调节Chern Band的能带宽度Bandwidth，使得上面部分填充的电子能量基本简并。同时，我们应当带隙足够大使得不同Band之间的波函数不会发生mix。这便给出了FCI相出现的第一个条件，平带条件：

当Chern Band的色散关系越趋近于平带，则Chern Band上的电子态动能越小，电子间相互作用的影响更强，更有可能出现FCI等新奇的多体强关联态。

近年最为火热的转角石墨烯便是这样一种材料，通过调节两层石墨烯之间的相对转角$\theta$、AA sublattice hopping和AB sublattice hopping强度的相对比值$\kappa$（这可能由晶格弛豫等现象造成）等参数，我们能够操控费米面附近的色散关系，使得其趋于平带。其中在魔角$\theta_c \approx 1.05^\circ$、chiral极限$\kappa =0$附近，能够得到几乎严格flat的能带，且能带具有拓扑性质（陈数非零），这成为了研究FCI相的重要平台。

之后我们还会介绍除了色散关系以外的其他晶格系统性质对FCI相出现的作用，例如Chern Band的Berry Curvature在布里渊区（BZ）中的分布、以及Chern Band的Fubini-Study Metric等Geometry因素对FCI相的影响。

Naive的想，既要特殊的色散关系，又要特殊的band geometry，似乎FCI出现的条件很苛刻。但事实上，一个晶格Hamiltonian的色散关系和波函数（Berry Curvature、Fubini-Study Metric等Band Geometry因素事实上与波函数有关）其实一定程度上是独立的，对于一个色散关系为$\epsilon(k)$的能带，我们总可以把它变成2-flat band的色散关系，而保持BZ到波函数空间的映射及其引申出的Berry Curvature、Band Geometry不变。

$$
\begin{aligned}
\hat{H} = \sum_k \epsilon(k) |u_k\rangle \langle u_k| \rightarrow \hat{H}_{flat} = \sum_k \epsilon_0 |u_k\rangle \langle u_k|
\end{aligned}
$$

两者是拓扑等价的，只要变换过程中保持能带间的gap不close即可。综上，在解析分析时，我们可以把色散关系$\epsilon(k)$和波函数$|u_k\rangle$及其引申出的Berry Curvature$\mathcal{B}(k)$等band geometry区分开来研究。

## Introduction to Quantum Geometry

量子态生活在Hilbert Space中，既然Hilbert Space能够有良定的内积，我们便可以用它来定义量子态之间的”距离“以及”度规“，这便给了Hilbert Space一个量子的几何描述，即Quantum Geometry。

不过应当注意态矢量$|\psi\rangle$乘上一个非零的复数仍为相同的态，所以真实的态应当生存在Projective Hilbert Space上，它同构于$\mathbb{C} P^{n-1}$：

$$
\begin{aligned}
\mathcal{P}_{\mathcal{H}} \simeq \mathbb{C} P^{n-1}
\end{aligned}
$$

naive的定义态之间的"距离"：

$$
\begin{aligned}
d s^2=\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle d k^\mu d k^\nu
\end{aligned}
$$

但这并不是规范不变的，正确的定义应当是：

$$
\begin{aligned}
d s^2=Q_{\mu \nu} d k^\mu d k^\nu
\end{aligned}
$$

其中：

$$
\begin{aligned}
Q_{\mu \nu} \equiv\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle-\left\langle\partial_\mu \psi \mid \psi\right\rangle\left\langle\psi \mid \partial_\nu \psi\right\rangle
\end{aligned}
$$

其虚部正比于Berry Curvature：

$$
\begin{aligned}
B_{\mu \nu} \equiv \operatorname{Im}\left[Q_{\mu \nu}\right]
\end{aligned}
$$

其实部则为Fubini-Study Metric：

$$
\begin{aligned}
g_{\mu \nu} \equiv \operatorname{Re}\left[Q_{\mu \nu}\right]
\end{aligned}
$$

由于Quantum metric应当类似一般的度规，有（半）正定性，可以证明：

$$
\begin{aligned}
\operatorname{det}g_{\mu \nu} \geqslant\left|B_{\mu \nu}\right|^2
\end{aligned}
$$

$$
\begin{aligned}
\operatorname{Tr}g_{\mu \nu} \geqslant 2\left|B_{\mu \nu}\right|
\end{aligned}
$$

## FCI & Geometric Stability Hypothesis

下面我们回到本文最初提到的问题，怎么在晶格系统中实现类似FQH效应的FCI相。除了Flat Band这一条件，之前提到的Geometric Stability Hypothesis认为只要我们能尽可能再现FQH系统中collective neutral excitation中投影密度算符$\hat{\bar{\rho}}_q$的GMP Algebra，我们就很有可能在晶格系统中实现FCI相。

### Analogy of Interaction

首先我们类比晶格和连续系统中的相互作用：

$$
\begin{aligned}
V=\frac{1}{2} \sum_{i, j} U_{i j} \hat{n}_i \hat{n}_j
\end{aligned}
$$

作Fourier Transformation得到：

$$
\begin{aligned}
V=\frac{1}{2} \sum_{\mathbf{q}} U(q) \hat{n}_{\mathbf{q}} \hat{n}_{-\mathbf{q}}
\end{aligned}
$$

non-interacting部分的本征波函数：

$$
\begin{aligned}
|\mathbf{k}, \alpha\rangle=\gamma_{\mathbf{k}, \alpha}^{\dagger}|0\rangle \equiv \sum_a u_a^\alpha(\mathbf{k}) c_{\mathbf{k}, a}^{\dagger}|0\rangle
\end{aligned}
$$

对于感兴趣的$\alpha$-band，我们也类比FQH中投影到L.L.L.那样，分析投影到Chern Band上的物理。

投影算符为：

$$
\begin{aligned}
\mathcal{P}_\alpha=\sum_{\mathbf{k}} |\mathbf{k}, \alpha \rangle \langle\mathbf{k}, \alpha|
\end{aligned}
$$

对于平带，忽略单体部分，由于投影后$\overline{\rho_q \rho_{-q}}$与$\bar{\rho_q}\bar{\rho_{-q}}$只相差一个常数，可以略掉，从而投影到Chern band上的相互作用Hamiltonian为：

$$
\begin{aligned}
H_{\mathrm{CB}, \alpha}^{\mathrm{eff}}=\frac{1}{2} \sum_{\mathbf{q}} U(\mathbf{q}) \bar{\rho}_{\mathbf{q} ; \alpha} \bar{\rho}_{-\mathbf{q} ; \alpha}
\end{aligned}
$$

与投影到L.L.L.的比较，发现两者形式基本一致

$$
\begin{aligned}
H_{\mathrm{LL}}^{\mathrm{eff}}=\frac{1}{2} \sum_{\mathbf{q}} V(\mathbf{q}) \mathrm{e}^{-q^2 \ell_B^2 / 2} \bar{\rho}_{\mathbf{q}} \bar{\rho}_{-\mathbf{q}}
\end{aligned}
$$

这里提出$\mathrm{e}^{-q^2 \ell_B^2 / 2}$是因为此处的定义可以消去GMP Algebra中的指数项。

### Lowest Order Correspondence

我们取长波近似，从而可以把投影后的算符按照$q$的order一阶一阶展开，投影密度算符展开到$\mathcal{O}(q^2)$结果为：

$$
\begin{aligned}
\bar{\rho}_{\mathbf{q}}=P_\alpha-i P_\alpha \mathbf{q} \cdot \mathbf{r} P_\alpha-\frac{1}{2} P_\alpha(\mathbf{q} \cdot \mathbf{r})^2 P_\alpha + \mathcal{O}(q^3)
\end{aligned}
$$

计算它们的对易子，有：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right] \approx \mathrm{i} \mathbf{q}_1 \wedge \mathbf{q}_2 \sum_{\mathbf{k}}\mathcal{B}_\alpha(\mathbf{k}) |\mathbf{k}, \alpha \rangle \langle\mathbf{k}, \alpha|}
\end{aligned}
$$

对比GMP Algebra的$\mathcal{O}(q^2)$项，应当有：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=i\left(\mathbf{q}_1 \wedge \mathbf{q}_2\right) \bar{B}_\alpha P_\alpha}
\end{aligned}
$$

后面的投影算符$P_\alpha$事实上可以看做$\bar{\rho}_{q_1+q_2}$的0阶近似，

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right] \approx \mathrm{i} \mathbf{q}_1 \wedge \mathbf{q}_2 \overline{\mathcal{B}}_\alpha \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}}
\end{aligned}
$$

这事实上说明，在$\mathcal{O}(q^2)$复现GMP Algebra，则要求**BZ上的Berry Curvature均匀分布**，这实现FCI可能要满足的第二个条件，即Flat Berry Curvature。

对Flat Berry Curvature条件的偏离，可以用BZ上Berry Curvature的标准差来衡量，标准差越大，可以预计投影到Chern Band上的密度算符与GMP Algebra相距更远，从而FCI相不再stable。

我们也看到，在最低阶，$\overline{\mathcal{B}}_\alpha$代替了FQH中的GMP Algebra表达式的$l_B^2$的作用，这一定程度上说明了：

**Berry Curvature确实起到了代替实空间磁场的作用**。

对于拓扑平庸的能带，Berry Curvature的平均值显然为$\overline{\mathcal{B}}_\alpha=0$，所以不会再现GMP Algebra，很可能也不会有FCI态。而对Chern number$\mathcal{C}>1$系统的FCI相也是目前研究的热点。

### Higher Order Correspondence

根据这种长波展开的精神，我们继续将投影密度算符展开到更高阶，并观察其对易子的每一阶与GMP Algebra的偏离。

对于$\mathcal{O}(q^3)$，有：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]}
\end{aligned}
$$

$$
\begin{aligned}
=i \bar{B}_\alpha\left(\mathbf{q}_1 \wedge \mathbf{q}_2\right)\left[P_\alpha-i P_\alpha\left(\mathbf{q}_1+\mathbf{q}_2\right) \cdot \mathbf{r} P_\alpha\right]
\end{aligned}
$$

$$
\begin{aligned}
\quad-\frac{i}{2} \sum_{a, b, c}\left(\frac{q_{1 a} q_{2 b} q_{2 c}}{2}\left[P_\alpha r_a P_\alpha, P_\alpha\left(r_b Q_\alpha r_c+r_c Q_\alpha r_b\right) P_\alpha\right]\right.
\end{aligned}
$$

$$
\begin{aligned}
\left.\quad+\frac{q_{1 a} q_{1 b} q_{2 c}}{2}\left[P_\alpha\left(r_a Q_\alpha r_b+r_b Q_\alpha r_a\right) P_\alpha, P_\alpha r_c P_\alpha\right]\right),
\end{aligned}
$$

其中，

$$
\begin{aligned}
Q_\alpha=I-P_\alpha
\end{aligned}
$$

可以证明，当Fubini-Study Metric：

$$
\begin{aligned}
g_{a b}^\alpha(\mathbf{k})=\frac{1}{2} \sum_p\left[\left(\frac{\partial u_p^{\alpha *}}{\partial k_a} \frac{\partial u_p^\alpha}{\partial k_b}+\frac{\partial u_p^{\alpha *}}{\partial k_b} \frac{\partial u_p^\alpha}{\partial k_a}\right)\right.
\end{aligned}
$$

$$
\begin{aligned}
\left.\quad-\sum_q\left(\frac{\partial u_p^{\alpha *}}{\partial k_b} u_p^\alpha u_q^{\alpha *} \frac{\partial u_q^\alpha}{\partial k_a}+\frac{\partial u_p^{\alpha *}}{\partial k_a} u_p^\alpha u_q^{\alpha *} \frac{\partial u_q^\alpha}{\partial k_b}\right)\right]
\end{aligned}
$$

在整个BZ上不变时，投影密度算符将满足Generalized GMP Algebra，

$$
\begin{aligned}
\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=2 i \sin \left(\frac{\mathbf{q}_1 \wedge \mathbf{q}_2 \bar{B}_\alpha}{2}\right) e^{q_{1 l} g_{l m}^\alpha q_{2 m}} \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}
\end{aligned}
$$

这样，我们便清楚了为什么Quantum Geometry会进入到对FCI稳定性的分析中，这便是Geometric Stability Hypothesis的精神。

### Trace Condition

在最低阶的分析中，我们用berry Curvature在BZ上的标准差来刻画强关联晶格系统对GMP Algebra的偏离程度，这是刻画FCI的第二个indicator，第一个是Band Flatness，可以用Chern Band色散关系的标准差来刻画。

在文献中，我们会看到还有第三个FCI indicator，即Trace Condition，它事实上刻画了$\bar{\rho}_q$对易子更高阶项中对GMP Algebra的偏离。下面我们来简要说明一下。

之前我们用Quantum Metric的正定性证明了不等式：

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] \geqslant\left|B_\alpha(\mathbf{k})\right|
\end{aligned}
$$

注意前后Berry Curvature可能相差一个$2$的系数。

此处我们可以给出另一种证明：

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right]=\left\langle\mathbf{k}, \alpha\left|(x+i y)\left(I-P_\alpha\right)(x-i y)\right| \mathbf{k}, \alpha\right\rangle +i\left\langle\mathbf{k}, \alpha\left|\left[x\left(I-P_\alpha\right) y-y\left(I-P_\alpha\right) x\right]\right| \mathbf{k}, \alpha\right\rangle
\end{aligned}
$$

其中

$$
\begin{aligned}
A=\left(I-P_\alpha\right)(x+i y) P_\alpha
\end{aligned}
$$

$$
\begin{aligned}
C=\left(I-P_\alpha\right)(x-i y) P_\alpha
\end{aligned}
$$

由$AA^\dagger$和$CC^\dagger$的（半）正定性，有：

$$
\begin{aligned}
\left\langle\mathbf{k}, \alpha\left|A A^{\dagger}\right| \mathbf{k}, \alpha\right\rangle \geqslant 0, \quad\left\langle\mathbf{k}, \alpha\left|C C^{\dagger}\right| \mathbf{k}, \alpha\right\rangle \geqslant 0 \text {. }
\end{aligned}
$$

从而

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] \geqslant\left|B_\alpha(\mathbf{k})\right|
\end{aligned}
$$

为何关心这个数学不等式？**因为这个不等式取等号“=”，当且仅当FS-metric为常数，而恒定的FS-metric就是高阶项满足GMP Algebra的条件**。

所以我们可以定义一个非负数$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right|$，用来刻画高阶项对GMP Algebra的偏离，我们定义这个量为"**Trace Condition**"，这便是第三个FCI相的indicator。

## FCI Indicators

综上所述，我们得到了（可能）刻画分数填布的Chern Band中FCI稳定性的三个indicators：

+ Band Flatness，由Chern Band能谱的标准差来刻画。
+ Berry Curvature Flatness，由Berry Curvature的标准差来刻画，它描述了Chern band对GMP Algebra在$\mathcal{O}(q^2)$阶的偏离。
+ Trace Condition，由非负数$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right| \geq 0$来刻画，它描述了Chern band对GMP Algebra在$\mathcal{O}(q^3)$及更高阶的偏离。

### Finite Field FCI

事实上，我们还可以考虑较微弱（但有限）的磁场对FCI相稳定性的作用。我们仍可以用之前提到的三个FCI indicator来刻画FCI相的稳定性。

不过，由于磁场破坏了平移对称性，使得元胞扩大，磁布里渊区比原先的布里渊区更小，进而使得Chern Band发生折叠，变成多条能带。

可以把Berry Curvature以及FS metric推广到多能带系统，而投影也变成投影到这些因为磁场劈裂的多条能带上，此时的Berry Connection将变成non-Abelian的，Berry Curvature以及FS metric的维度也会扩大。

不过这些推广是自然的，类似由数推广到矩阵，所以包括Trace condition$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right| \geq 0$在内的三个indicatoe形式基本不变。

此处不再赘述，具体细节可以参考Ashvin最近的一篇在转角石墨烯系统中模拟零场和有限磁场下FCI态的文章。

## Wannier Function & L.L.L Wavefunction

XL Qi提出了一种将Chern Band中的单体Wannier Function与Landau Gauge下的QH系统单体波函数对应起来的方案，结合Laughlin给出的多体波函数形式，我们可以合理猜测Chern Band中FCI态多体波函数的性质。

简单的说，Landau gauge求出的单粒子波函数，在y方向是延展的平面波，而在x方向是局域的谐振子波函数；

而在Chern Band中，由于能带拓扑非平庸，这对应了拓扑保护的边缘态，从而一般的Fourier Transformation不能得到在x、y方向都localize的Wannier Wavefunction。但是可以只对x方向作Partial Fourier Transformation，从而得到在x方向局域化，而在y方向延展的partial Wannier Function。

对比这两种单粒子波函数，不难将其进行联系。再利用电子气中单粒子波函数到Laughlin wavefunction的转化，可以将上述Chern Band中的partial Wannier Function写成多体波函数，从而得到晶格系统中FCI态的波函数，如图所示。

![Image](https://pic4.zhimg.com/80/v2-5984629601675cdc8574304e8a1ab981.png)

具体细节请参考Qi, X. L.的文章，Generic wave-function description of fractional quantum anomalous Hall states and fractional topological insulators. Physical review letters, 107(12), 126803.

## Reference

- [Parker, D., Ledwith, P., Khalaf, E., Soejima, T., Hauschild, J., Xie, Y., ... & Vishwanath, A. (2021). Field-tuned and zero-field fractional Chern insulators in magic angle graphene. arXiv preprint arXiv:2112.13837.](https://arxiv.org/abs/2112.13837)

- [Qi, X. L. (2011). Generic wave-function description of fractional quantum anomalous Hall states and fractional topological insulators. Physical review letters, 107(12), 126803.](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.126803)

- [Jackson, T. S., Möller, G., & Roy, R. (2015). Geometric stability of topological lattice phases. Nature communications, 6(1), 1-11.](https://www.nature.com/articles/ncomms9629)

- [Wu, Y. L., Bernevig, B. A., & Regnault, N. (2012). Zoology of fractional Chern insulators. Physical Review B, 85(7), 075116.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.075116)

- [Bauer, D., Talkington, S., Harper, F., Andrews, B., & Roy, R. (2022). Fractional Chern insulators with a non-Landau level continuum limit. Physical Review B, 105(4), 045144.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.105.045144)

- [Parameswaran, S. A., Roy, R., & Sondhi, S. L. (2013). Fractional quantum Hall physics in topological flat bands. Comptes Rendus Physique, 14(9-10), 816-839.](https://doi.org/10.1016/j.crhy.2013.04.003)

- [Chamon, C., & Mudry, C. (2012). Magnetic translation algebra with or without magnetic field in the continuum or on arbitrary Bravais lattices in any dimension. Physical Review B, 86(19), 195125.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.86.195125)

- [Wang, J., Cano, J., Millis, A. J., Liu, Z., & Yang, B. (2021). Exact landau level description of geometry and interaction in a flatband. Physical Review Letters, 127(24), 246403.](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.127.246403)

- [Kolodrubetz, M., Sels, D., Mehta, P., & Polkovnikov, A. (2017). Geometry and non-adiabatic response in quantum and classical systems. Physics Reports, 697, 1-87.](https://doi.org/10.1016/j.physrep.2017.07.001)

- [Rossi, E. (2021). Quantum metric and correlated states in two-dimensional systems. Current Opinion in Solid State and Materials Science, 25(5), 100952.](https://doi.org/10.1016/j.cossms.2021.100952)

- [Girvin, S. M., MacDonald, A. H., & Platzman, P. M. (1986). Magneto-roton theory of collective excitations in the fractional quantum Hall effect. Physical Review B, 33(4), 2481.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.33.2481)

- [Roy, R. (2014). Band geometry of fractional topological insulators. Physical Review B, 90(16), 165139.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.90.165139)

- [Parameswaran, S. A., Roy, R., & Sondhi, S. L. (2012). Fractional Chern insulators and the W∞ algebra. Physical Review B, 85(24), 241308.](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.241308)

- [Page, D. N. (1987). Geometrical description of Berry's phase. Physical Review A, 36(7), 3479.](https://journals.aps.org/pra/abstract/10.1103/PhysRevA.36.3479)

- [Karabali, D. (1994). W∞ algebras in the quantum Hall effect. Nuclear Physics B, 428(3), 531-544.](https://doi.org/10.1016/0550-3213(94)90216-X)

- [Wen, X. G. (2004). Quantum field theory of many-body systems: from the origin of sound to an origin of light and electrons. OUP Oxford.](https://global.oup.com/academic/product/quantum-field-theory-of-many-body-systems-9780199227309)

- [Tong, D. (2016). The quantum hall effect. TIFR infosys lectures. arXiv preprint arXiv:1606.06687.](https://arxiv.org/abs/1606.06687)

- [Giuliani, G., & Vignale, G. (2005). Quantum theory of the electron liquid. Cambridge university press.](https://www.cambridge.org/core/books/quantum-theory-of-the-electron-liquid/B14D8B6E3245464D928B365B6C48B01F)