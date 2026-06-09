---
title: "Quantum Geometry Everything？一文讲清「量子几何物理大响应」"
date: 2026-06-09T12:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Berry Curvature", "Quantum Metric", "Nonlinear Response", "Condensed Matter"]
categories: ["Physics Notes"]
---

本文约15000字，旨在阐述"量子几何" (Quantum Geometry)「何意味」&「意味何」的问题。前半偏definition，后半偏phenomena，读者可按需阅读。

<!--more-->

## 引言 (Introduction)

最近量子几何 (Quantum Geometry) 这一概念在凝聚态物理这一领域颇为火热，相关的论文和综述井喷。笔者在暑研期间初次接触，后有幸发表过note、paper、review一二：

- [Revealing quantum geometry in nonlinear quantum materials](https://iopscience.iop.org/article/10.1088/1361-6633/pde454)
- [Electrical magnetochiral anisotropy and quantum metric in chiral conductors](https://iopscience.iop.org/article/10.1088/2053-1583/ada0b8/meta)

但笔者水平有限，看的论文不多，research experience也有限，有很多疏漏，还望各位读者大佬们评论区不吝赐教！最后感谢知乎网红文章作者小王 [@Austeritas](https://www.zhihu.com/people/Junkai-Wang) 的催更！

---

## 量子几何何意味？What is Quantum Geometry?

**Q：量子几何为几何？**

**A：为波函数之几何。**

更具体地说，Quantum geometry描述的波函数之geometry是2-fold的，其一乃实空间波包之几何，其二乃倒空间态矢之几何。

实空间中，量子几何（Quantum Geometry）= 形变（deformation）+ 自转（self-rotation），反应其物理含义；倒空间中，量子几何（Quantum Geometry）= 长度（length）+ 面积（area），反应其几何含义。

同时，quantum geometry也可以理解为transition dipole-dipole moment，还可以有更高阶的generalization，值得一提的是这些构造出来的quantum geometric quantities都是gauge invariant的，也就是说它们是有实际的物理含义甚至是可被观测的物理量。

本节中，我们先介绍quantum geometry在real space中的物理含义，并介绍其transition dipole-dipole moment的诠释，之后再介绍其在reciprocal space中的几何含义，最后简要介绍量子几何高阶项和量子几何的规范不变性。

### 实空间波包几何 (Real Space Wave Packet Geometry)

经典力学一般把电子看成点粒子，其平动给出了经典电流；而量子力学告诉我们，电子并非点粒子，而是以波函数的形式存在。其在实空间半经典的描述为一个波包。除了整体如点粒子一般的质心的平动，波包也有internal structure & motion，最直观之二便是为波包的自转（self-rotation）和形变（deformation），前者对应Berry Curvature，后者对应Quantum Metric。

我们都知道磁场可以导致(量子)霍尔效应，因为电子在磁场中的cyclotron motion会产生transverse direction的运动，进而贡献Hall current。

我们也都熟悉nontrivial Berry curvature可以贡献(量子)反常霍尔效应，因为nontrivial Berry curvature描述了electronic wavepacket本身的self-rotation，这一自转运动也能类似磁场中的cyclotron motion一样产生anomalous Hall current.

> **图①** **(a) Quantum Metric ↔ Deformation**：Bloch球上弦长 $l_1,l_2$（量子度规=长度），对应波包的横向展宽（spreading）。**(b) Berry Curvature ↔ Rotation**：Bloch球上面积元 $S_1,S_2$（Berry曲率=面积），对应波包的自旋/旋转运动。

既然波包的self-rotation自由度可以被Berry curvature描述，我们自然联想波包的其他自由度，例如波包的deformation，是否也可以被某个几何量描述？答案是肯定的，这就是量子度规(Quantum Metric)。

> **图②** $\Omega \sim \langle \mathbf{r} \times \mathbf{v} \rangle$（Berry曲率=自转）；$g \sim \langle r_i r_j \rangle$（量子度规=展宽）。下行：在电场 $\mathbf{E}$ 作用下，Berry曲率导致横向（反常）速度修正，量子度规导致纵向形变修正。

不难想象，运动中保持不变的刚体和运动中内部可以形变/旋转的波包，后者除了整体的平动还会有内部形变/旋转导致的anomalous motion，这便是量子几何产生各种geometric response的物理机理。除了线性响应中常见的Berry curvature induced intrinsic anomalous Hall effect，还有nonlinear effect中的Berry curvature dipole induced nonlinear anomalous Hall effect以及quantum metric dipole induced intrinsic nonlinear anomalous Hall & intrinsic nonreciprocal magnetoresistance。

以nonreciprocal magnetoresistance为例，在磁性体系，即时间反演破缺的体系中，quantum metric在动量空间的分布不是对称的，这可以进而导致nonzero的quantum metric dipole structure。这样一来，我们平行/反平行于此dipolar distributed quantum metric方向加电场时，波包的中心动量往平行/反平行方向移动时的quantum metric/形变/deformation是不一样的，这样便导致平行/反平行的电场下，系统的电阻不同，进而导致nonreciprocal magnetoresistance。这种nonreciprocity可以被用于构造新型的diode器件，而其性能由材料的quantum metric这一intrinsic quantum geometric quantity决定。

Mathematically，我们还能把Berry curvature $\Omega^{\mu\nu}$ 和quantum metric $g^{\mu\nu}$打包成一个整体，称之为量子几何张量(Quantum Geometric Tensor) $Q^{\mu\nu}$

$$Q^{\mu\nu} = g^{\mu\nu} - i \Omega^{\mu\nu}$$

其中$g^{\mu\nu}$为量子度规(Quantum Metric) or Fubini-Study metric，类似微分几何中的metric，是一个symmetric tensor，$\Omega^{\mu\nu}$为Berry Curvature，是一个antisymmetric tensor，在2D/3D空间中我们有时更习惯标量/矢量形式的Berry curvature $\Omega^z = \Omega^{xy} - \Omega^{yx}$ 或者 $\Omega^a = \epsilon^{abc} \Omega^{bc}$。

### 偶极偶极激发率 (Dipole-Dipole Excitation Rate)

More detailed，我们可以将$Q_{\mu\nu}$的具体形式写出:

$$Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n = g^{\mu\nu}_n - i \Omega^{\mu\nu}_n$$

其中$r^a_{nm} \equiv \langle \psi_m | \hat{r}^a | \psi_n \rangle$为position operator $\hat{r}^a$在m-th band和n-th band之间的matrix element，也被经常称为interband Berry connection/interband transition dipole。此处的"interband"意味着$m \neq n$，这是出于gauge invariance的考量。

此处$\langle ... \rangle_n$表示在n-th band的expectation value，而$\Delta \hat{r}^\mu \equiv \hat{r}^\mu - \langle \hat{r}^\mu \rangle_n$表示在n-th band的position operator期望值偏离中心位置的偏离量，这样正好去掉了dipole matrix element中gauge dependent的对角元部分，保留可观测的物理量。

> **图③** $Q_n^{\mu\nu} = \langle \Delta\hat{r}^\mu \Delta\hat{r}^\nu \rangle_n$：波包（黄色高斯型）位于实空间中，双箭头标注其二阶矩（Spread），整个平行四边形象征量子几何张量作为波包内部结构的几何度量。

从这个定义出发，我们可以将quantum geometry从一个band的性质推广到整个基态波函数的实空间性质：

$$Q^{\mu\nu}_{GS} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_{GS} = \operatorname{tr} \left[ \hat{P} \hat{r}^\mu (\mathbb{I} - \hat{P}) \hat{r}^\nu \right]$$

其中$\hat{P}$为Ground State projector operator，$\mathbb{I}$为单位矩阵。这样便可以对任意（基）态定义quantum geometric tensor，作为（基）态的内禀物理量。

Fermi Golden Rule告诉我们在空间均匀的外电场的作用下（微扰Hamiltonian为$H' = -e \hat{\mathbf{r}} \cdot \mathbf{E}$），从n-th band到m-th band的跃迁速率为：

$$\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} r^\mu_{mn} r^\nu_{nm} \delta(\omega - \omega_{mn}) E^\mu(\omega) \bar{E}^\nu(\omega)$$

> **图④** 两带能带图：蓝色抛物线（$m$-band）和红色抛物线（$n$-band）。白色粗箭头（$\mathcal{I}_{m\leftarrow n}$）标注跃迁，旁有闪电符号标注驱动频率 $\omega$。

对$\omega$积分，再对所有$m\neq n$求和，n-th band的total transition rate正比于quantum geometric tensor：

$$\mathcal{I}_{n}^{tot} = \int d\omega \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu$$

将transition rate与不同物理量组合，便得到不同的geometric response：

- (i) $\mathcal{I}_{m \leftarrow n} \times 1$：Transition Rate
- (ii) $\mathcal{I}_{m \leftarrow n} \times (E_m - E_n)$：Joule Heat (dissipative linear conductivity)
- (iii) $\mathcal{I}_{m \leftarrow n} \times (v_m - v_n)$：Velocity Shift (injection current)
- (iv) $\mathcal{I}_{m \leftarrow n} \times (r_m - r_n)$：Positional Shift (shift current)

### 倒空间态矢几何 (Momentum Space Eigenstate Geometry)

量子力学告诉我们坐标算符在reciprocal space的表象是对动量$\mathbf{k}$的导数$\hat{\mathbf{r}} = i \nabla_{\mathbf{k}}$。结合两者，quantum geometric tensor描述了波函数在reciprocal space上的度规:

$$Q^{\mu\nu}_{n} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n \sim \langle \psi_n | \nabla_{k_\mu} \nabla_{k_\nu} | \psi_n \rangle$$

> **图⑤** Bloch球三维示意图：红色曲线 $l_1, l_2$ 标注弧长（量子度规 $g_\mathbf{k}^{ab}$），橙黄色阴影区 $S_1, S_2$ 标注面积元（Berry曲率 $\Omega_\mathbf{k}$）。量子几何张量同时编码了Hilbert空间流形的"长度"与"面积"。

更严格的保证gauge invariance的表述是：

$$Q^{\mu\nu}_{n} = \langle \nabla_{k_\mu} \psi_n | \left[ \mathbb{I} - | \psi_n \rangle \langle \psi_n | \right] | \nabla_{k_\nu} \psi_n \rangle$$

quantum metric measure了波函数空间在reciprocal space上的"长度" $dl^2 = g^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$，而Berry curvature反映了波函数空间在reciprocal space上的"面积" $dS = \Omega^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$。

Gauge invariant的line element和面积元为：

$$dl^2 = g^{\mu\nu} dk_\mu dk_\nu, \qquad dS = \Omega^{\mu \nu} dk_\mu dk_\nu$$

这对于我们理解Chern number很有用——对Berry curvature的积分相当于对Bloch sphere面积的积分，which is quantized。这对于理解geometric bound $\operatorname{tr} g \geq 2 |\Omega^{xy}|$ 也很有用：给定周长的图形中，圆所围面积最大，这意味着"长度"对"面积"天然存在upper bound。

### 规范不变投影法 (Gauge Invariance and Projector Formalism)

给波函数加一个相位（规范变换）$|\psi\rangle \rightarrow e^{i \theta} |\psi\rangle$后，物理量不能有改变。对于晶格系统，dipole matrix element的对角元$\langle \hat{r}^\mu \rangle_n$与晶格原点取法有关，是gauge dependent的量，去掉后得到的quantum geometric tensor便只剩下gauge-invariant的物理信息。

> **图⑥** 规范变换=原胞原点平移示意：original unit cell → new unit cell，波包中心随原点选取平移（物理同一态）。说明对角元 $\langle\hat{r}^\mu\rangle_n$ 依赖于人为坐标选取，而量子几何张量是gauge invariant的。

为了更方便地保证formula的gauge invariance，引入projector formalism：

$$\hat{P}_n = |\psi_n\rangle \langle \psi_n|$$

ket与bra的相位在projector中抵消，projector本身规范不变。在此formalism下：

$$g^{\mu\nu}_n = \frac{1}{2} \operatorname{tr}[\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]$$

$$\Omega^{\mu\nu}_n = i \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n] - (\mu \leftrightarrow \nu)$$

$$Q^{\mu\nu}_n = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]$$

对于degenerate band，推广为d-band projector $\hat{P}_n = \sum_{i=1}^{d} |\psi_{n,i}\rangle \langle \psi_{n,i}|$；还可以把projector看成density matrix，构建混态/有限温度体系的quantum geometry。

### 量子几何高阶项 (Higher Order Quantum Geometry)

以quantum connection为例：

$$Q^{\mu;\nu\rho}_n = \operatorname{tr} \left[ \hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \partial_\rho \hat{P}_n \right]$$

Berry curvature dipole $\partial_\rho \Omega^{\mu\nu}_n$ 和 quantum metric dipole $\partial_\rho g^{\mu\nu}_n$ 与quantum connection的联系：

$$\partial_\rho g^{\mu\nu}_n = \operatorname{Re} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right], \qquad \partial_\rho \Omega^{\mu\nu}_n = -2 \operatorname{Im} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right]$$

### 多带の量子几何 (Multi-band Quantum Geometry)

2-band quantum geometric tensor：

$$Q^{\mu\nu}_{nm} = r^{\mu}_{nm} r^{\nu}_{mn} = g^{\mu\nu}_{nm} - i \Omega^{\mu\nu}_{nm}$$

利用"tangent vector" operator $\hat{e}^\mu_{mn} = i \hat{P}_m (\partial_\mu \hat{P}_n) \hat{P}_n$（gauge invariant），2-band量可以写成：

$$Q^{\mu\nu}_{nm} = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_m \partial_\nu \hat{P}_n]$$

在系统只有2 band时，2-band quantum geometry与1-band quantum geometry包含相同的信息，例如quantized circular injection conductivity只在2-band system中成立。

---

## 量子几何意味何？Quantum Geometry means What?

我们把矩阵元包装成quantum geometric tensor，进而理解各种物理量有诸多好处。

一是更方便我们用物理的intuition理解各种物理量的物理/几何含义；二是通过与几何/拓扑学的联系，我们可以得到一些有趣的量子体系的恒等式/不等式。最重要的例如量子（反常）霍尔效应的quantized Hall conductivity对应着体系里拓扑非平庸的能带quantized Chern number:

$$\sigma_{xy} = \frac{e^2}{h} C = \frac{e^2}{h} \int_{BZ} d^dk \,\Omega^z(k)$$

### 量子几何响应率 (Quantum Geometric Response)

**(i) Transition Rate**

$$\mathcal{I}_{n}^{tot} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu$$

对于线偏振光，对应quantum metric；对于圆偏振光，左旋右旋之差对应Berry curvature。

**(ii) Joule Heat / Dissipative Linear Conductivity**

$$\mathcal{P}_{Joule}(\omega) = \frac{2\pi e^2}{\hbar^2} \omega \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \delta(\omega - \omega_{mn}) E^\mu \bar{E}^\nu$$

由此得到SWM sum rule：

$$\int d\omega \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}$$

还有著名的optical f-sum rule：

$$\int d\omega \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}$$

进而，极化率 $\chi^{ab}(\omega) = \sigma^{ab}(\omega)/i\omega$，介电常数 $\epsilon = 1 + \chi$，折射率 $n = \sqrt{\epsilon}$ 均受quantum geometry影响。

**越是topological nontrivial的体系，折射率一定更大。** 为何钻石如此闪耀，因为diamond是obstructed atomic insulator，它的nontrivial topology/quantum geometry使它有更高的折射率（$n=2.4$），光线在其内反射更多次从而看起来更加闪耀（相比Rock Salt的$n=1.5$）。

**(iii) Injection Current (Velocity Shift)**

所谓Injection Current，光照导致电子从Band $n$ 跃迁到 Band $m$，如果跃迁后的群速度$v_m$与原群速度$v_n$存在差异，就会产生随时间线性增长的电流。

$$\sigma_{\mathrm{inj}}^{ab;c} \propto \int_{S_k=\{k|\omega = \omega_{mn}(k)\}} dS_k^c \, Q^{ab}$$

有趣的是，对于只有两个Band的系统，CPGE（圆偏振光的Injection Current）是Quantized的。

**(iv) Shift Current (Positional Shift)**

在量子力学中，电子从Band $n$ 跃迁到 Band $m$ 的过程中，波包的"电荷中心"会发生一个实空间的位移——Shift Vector $R_{mn}^a = \mathcal{A}_{mm}^a - \mathcal{A}_{nn}^a - \nabla_{k_a} \arg(r_{mn})$（gauge invariant）。

$$\sigma_{\mathrm{shift}}^{ab;c} \propto \int_{\mathbf{k}} C_{bca} \, \delta (\omega - \omega_{mn})$$

不同于Injection Current依赖于弛豫时间$\tau$，Shift Current是纯粹的量子几何效应，理论上不依赖于弛豫时间，在超快光电响应器件中具有巨大的潜力。

**(v) 非线性输运 (Nonlinear Transport)**

在Transport regime ($\omega \to 0$)，通过分析电导对$\tau$的幂次（Scaling Law），把不同几何贡献一层层剥离：

$$j^{(2)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(2)} v_n^{(0)}}_{\text{NLD}\,(\tau^2)} + \underbrace{f_n^{(1)} v_n^{(1)}}_{\text{BCD}\,(\tau^1)} + \underbrace{f_n^{(0)} v_n^{(2)}}_{\text{QMD}\,(\tau^0)} \right)$$

**NLD（$\tau^2$）:**
$$\sigma_{ab;c}^{\text{NLD}} = \frac{e^3 \tau^2}{\hbar^3} \sum_n \int [dk] f_n \frac{\partial^3 \varepsilon_n}{\partial k_a \partial k_b \partial k_c}$$

**BCD（$\tau^1$，Berry Curvature Dipole，Sodemann & Fu）:**
$$\sigma_{ab;c}^{\text{BCD}} = \frac{e^3 \tau}{\hbar^2} \sum_n \int [dk] f_n \left( \frac{\partial \Omega_{n}^{bc}}{\partial k_a} + \frac{\partial \Omega_{n}^{ac}}{\partial k_b} \right)$$

**QMD（$\tau^0$，完全内禀，Quantum Metric Dipole）:**
$$\sigma_{ab;c}^{\text{QMD}} = \frac{e^3}{\hbar} \sum_n \int [dk] f_n \left( 2 \frac{\partial G_{n}^{ab}}{\partial k_c} - \frac{1}{2}\left(\frac{\partial G_{n}^{bc}}{\partial k_a} + \frac{\partial G_{n}^{ac}}{\partial k_b}\right) \right)$$

其中 $G_{n}^{ab} = \sum_{m \neq n} \frac{r^a_{nm} r^b_{mn} + r^b_{nm} r^a_{mn}}{\epsilon_{nm}}$ 是band-normalized quantum metric。

**(vi) Other geometric responses**

> **表①** 量子几何量与对应可观测响应总表（来自Tobias综述，arXiv:2504.07173）——包含Anomalous Hall、Non-reciprocal conductivity、Optical transition rate、Injection current、Shift current、Spectral weight、Chern number等条目，详见原文。

### 几何界限求和律 (Geometric Bounds & Sum Rules)

**(i) Geometric Bound**

等周不等式：给定周长$L$的所有闭合曲线中，圆所围成的面积最大（$L^2 \ge 4\pi A$）。在量子几何中类比：

$$\mathrm{Tr}(g) \ge |\Omega|$$

> **图⑦** 等周不等式→量子几何界限：给定周长的多种形状→最大面积（圆）。**Length ≥ Area**，**Quantum Metric ≥ Berry Curvature**。

对整个布里渊区积分：

$$\int_{BZ} \mathrm{Tr}(g(\mathbf{k})) d^2k \ge 2\pi |C|$$

这意味着拓扑非平庸的能带必然伴随着一个最小的总量子度量。

> **图⑧** 原子绝缘体（Trivial）：Wannier函数高度局域化，相邻间无overlap。陈绝缘体（Topological）：Wannier函数不可避免地在相邻格点间overlap（非零minimum spread $\Omega_I \propto \int\mathrm{Tr}[g]\,dk$）。

当不等式变为等式时，对应了Landau Level的ideal quantum geometry（最小不确定波包），称为迹条件 $\mathrm{Tr}(g(\mathbf{k})) = |\Omega(\mathbf{k})|$，是FCI设计的核心判据。

Geometric bound的物理本质根植于量子力学的基本不确定性原理$[\hat{x}, \hat{p}] = i\hbar$。

**(ii) Sum Rule**

1. Optical f-sum rule: $\displaystyle\int d\omega\, \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}$

2. Geometric sum rule (SWM): $\displaystyle\int d\omega\, \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}$

Sum rule之所以能给出系统的intrinsic property，是因为它反映的是系统对外界微扰作出反应的"weight"，完全对应系统基态的内禀特性，与激发态无关。

**(iii) Universal Bound**

Y. Onishi 和 L. Fu [Phys. Rev. X 14, 011052 (2024)] 将Geometric Bound和Sum Rule结合，得到了拓扑能隙的普适上界：

$$|C| \leq \frac{\pi n e^2}{2m E_g} \implies E_g \leq \frac{\pi n e^2}{2m |C|} \times (\text{const.})$$

这解释了为什么在许多拓扑材料中，能隙的大小最终会受到电子基本参数（$n, m$）的根本限制。

**(iv) Generalized Geometric Bound**

Herzog-Arbeitman, Bernevig等 [PRL 128, 087002 (2022)] 指出，即使Berry Curvature处处为零，实空间不变量(RSI)依然可以强制Quantum Metric具有非零的下界。对于obstructed atomic insulator，symmetry要求occupied band的Wannier center必须处在bond center，这对应了symmetry enforced bound for quantum metric。

Shinada and Nagaosa [arXiv:2507.12836 (2025)] 将QGT推广到任意参数空间$\boldsymbol{\lambda}$：

> **表②** 外场与共轭算符对应关系（来自Shinada & Nagaosa）：vector potential $A$ ↔ electric current $\hat{J}$；electric field $E$ ↔ polarization $\hat{P}_e$；magnetic field $B$ ↔ spin $\hat{S}$；strain $\partial u$ ↔ stress $\hat{\sigma}$。

**(v) Generalized Sum Rule**

广义矩 $W_\eta = \int_0^\infty \omega^\eta \text{Re}[\sigma(\omega)] d\omega$：$\eta=-1$ 对应静态介电常数；$\eta=0$ 对应f-sum rule；$\eta=1$ 对应有效质量；$\eta=2$ 对应shot noise。

Matsyshyn & Sodemann [PRL 123, 246602 (2019)] 发现非线性霍尔效应的Quantum Rectification Sum Rule。

移位电流的sum rule由位置算符的三阶累积量（偏度 Skewness）控制：

$$\int_{0}^{\infty} d\omega\, \sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega) \approx \frac{2\pi e^3}{\hbar^2} \frac{1}{V} \langle \hat{X}_{\alpha}\hat{X}_{\beta}\hat{X}_{\gamma}\rangle_{c}$$

阶梯对应关系（Hierarchy）：
- 线性响应 ($n=1$) ↔ 二阶矩 (Variance) ↔ Quantum Metric
- 移位电流 ($n=2$) ↔ 三阶矩 (Skewness) ↔ Multistate Geometry
- 三阶响应 ($n=3$) ↔ 四阶矩 (Kurtosis)

根据 Verma & Queiroz [PNAS 122, e2405837122 (2025)]，时变几何张量 (tQGT) 是所有几何求和律的生成函数：

$$\mathcal{S}_{\mu\nu}^\eta \equiv \int_0^\infty \frac{\text{Re}[\sigma_{\mu\nu}(\omega)]}{\omega^{1-\eta}} d\omega = \frac{\pi e^2}{\hbar} \left[ (-i\partial_t)^\eta \mathcal{Q}_{\mu\nu}(t) \right]_{t=0}$$

这意味着只需施加一个特定形状脉冲（如"方波"或"三角波"电场），并测量系统随后的电流或极化响应，即可直接"读出"sum rule对应的generalized geometric weight，无需测量完整光谱。

### 量子几何关联相 (Quantum Geometric Correlated Phase)

**(i) Quantum Geometric Spontaneous Symmetry Breaking**

在平带极限下($W \to 0$)，能量因子退化为常数$1/k_BT$，物理完全由几何因子主导：

$$\chi_0(\mathbf{q}) \approx \frac{1}{k_B T} \sum_{\mathbf{k}} \underbrace{\nu(1-\nu)}_{\text{填充因子}} \underbrace{\left| \langle u_{\mathbf{k}} | u_{\mathbf{k}+\mathbf{q}} \rangle \right|^2}_{\text{几何卷积}}$$

如果几何项favor某个$\mathbf{q}$，那么极化率也会favor这个$\mathbf{q}$，从而导致某种order parameter的出现——这就是"量子几何嵌套"（Quantum Geometric Nesting），与之前纯靠分析energy的Fermi Surface Nesting完全不同。

**(ii) Electron-Phonon Coupling**

主要参考Jiabin Yu的paper。

**(iii) Fractional Chern Insulator (FCI)**

究其本质，还是在模仿Landau Level，不仅要在energy层面模仿（平带），还要在wavefunction（quantum geometry/topology）层面模仿：不但要Chern band，还要布里渊区处处的quantum metric/Berry curvature与Landau Level类似（迹条件）。

Quantum geometry serves as the key ingredient to measure our deviation from the ideal Landau Level.

### 量子几何信息熵 (Quantum Geometric Information Theory)

**(i) Quantum Fisher Information (QFI)**

$$F_Q(\lambda) = 2 \sum_{n,m} \frac{(p_n - p_m)^2}{p_n + p_m} |\langle n | \partial_\lambda \rho | m \rangle|^2$$

在纯态极限（$T \to 0$）下，QFI退化为Quantum Metric的4倍：

$$F_Q = 4 g_{\lambda\lambda}$$

QFI是Quantum Metric在混合态（有限温度）下的自然推广。通过测量虚部动态磁化率可以实验探测：

$$F_Q(T) = \frac{4}{\pi} \int_0^\infty d\omega \tanh\left(\frac{\hbar\omega}{2k_B T}\right) \chi''_{\hat{h}}(\omega, T)$$

**(ii) Entanglement Entropy**

对于自由费米子系统，Renyi纠缠熵$S_A^{(\alpha)}$可以直接表示为关联矩阵的函数：

$$S_A^{(\alpha)} = \frac{1}{1-\alpha} \text{Tr} \ln \det [p \mathbf{1} - C_A]$$

由于关联矩阵本质上反映了波函数在实空间的重叠与距离，这暗示了Quantum Metric与纠缠熵之间存在直接的几何对应关系。

---

## 参考文献 (References)

施工中...

---

## 写在最后

感谢各位读到这里，停更近两年，我十分意外的从以色列转移到了美国，并托导师的福得以继续在凝聚态物理方向深造，十分感慨。

留美期间，我的生活 & 学习 & 工作 & 人际关系方面的变化很多，我仍在缓慢适应，同时科研工作也逐渐深入，于是我也没时间写note了。我也看到有读者在等更新，把用来发正经note的平台变成了我情绪宣泄的垃圾场，实在抱歉。

仅以此文纪念这些年我在quantum geometry方面的理解 & 踩坑 & 成果，谢谢大家至今的支持，有缘再会～
