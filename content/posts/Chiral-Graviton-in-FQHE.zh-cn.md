---
title: "🤯南大发现引力子？手征引力子与分数量子霍尔态内禀量子几何"
date: 2024-04-05T12:00:00+08:00
draft: false
math: true
tags: ["FQHE", "Graviton", "Metric", "Quantum Geometry"]
categories: ["Physics Notes"]
---

本文旨在简要介绍分数量子霍尔液体中“手征重力子”激发的相关理论和实验探测方式，为近期相关领域的火热讨论提供吃瓜素材。本人能力有限，有不足之处还望各位大佬不吝赐教。

<!--more-->

## Introduction

近日，南京大学 Lingjie Du 课题组与其德国美国同行合作发表了一篇关于实验探测分数量子霍尔（Fractional Quantum Hall, FQH）液体中“手征引力子”（Chiral Graviton）激发的 Nature，后经各路媒体炒作，引发了凝聚态学界内外关于在论文中使用“graviton”一词以及凝聚态各种准粒子命名规则的系列讨论。

https://www.nature.com/articles/s41586-024-07201-w

本文无意加入相关论战，毕竟科学本身无罪，都是下面的人执行歪了。故我们不妨趁此机会了解一下相关的理论及实验知识，科学吃瓜。

关于分数量子霍尔效应等前置内容，可以参考本人若干年前写的 note：

https://zhuanlan.zhihu.com/p/574597173

关于量子几何（Quantum Geometry），此处的 Quantum Geometry 为 FQH 基态波函数在 anisotropic 的 mass tensor 或者 Coulomb interaction（Dielectric tensor）下，由 Haldane 提出的一种新的内禀自由度，与之前本人写的关于波函数在特定参数空间（例如动量空间）中定义的 Quantum Geometry 并不完全相同。

不过以上两种 Quantum Geometry 均揭示了量子态除近几十年涌现的各种拓扑性质外的一种新的性质——几何性质及其响应的重要性。关于后者，其在分数翻唱量子霍尔效应以及其非线性光学、输运响应中的体现，都是最近凝聚态物理领域比较火热的话题，感兴趣的可以参考本人之前的 note 或者追更我之后的 note：

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

回到 Haldane 提出的作为 FQH 波函数一种新内禀自由度的 Quantum Geometry，后人发现，这种 Quantum Geometry 不仅只是描述了 FQH 基态波函数的一个参数，还可以视为一种动力学参数，对应了 FQH 中最重要的集体中性激发——magnetoroton 激发在长波极限下的动力学，这种长波极限下的 magnetoroton 激发由于极难观测，同时由于其源于内禀 Quantum Geometry Dynamics 的本质，凝聚态理论学家们也把这种激发模式称为“引力子”/“重力子”/Graviton（有些文献也仍称为长波极限下的 magnetoroton，但这样就不够吸引人眼球，要不到经费 bushi）。

这显然是与我们在广义相对论中熟知的时空 metric 的弯曲引发的引力波进行了类比，同时由于该激发自旋为 2 的特性，这也是与我们希望在量子场论中将引力量子化后同样自旋为 2 的引力子进行了类比。这可以说是擦了 High Energy 的边，也可以说是对引力子在凝聚态体系中的推广和内涵的丰富，毕竟包括外子（Weyl Fermion）、马子（Majorana Fermion）等原先高能物理的概念也先后被引入了凝聚态物理领域，圈内人士往往已经司空见惯。

更进一步，这种 graviton 还具有手性（Chirality），例如在 $$\nu = 1/3$$ 填充的 FQH 中，其 Graviton 激发不仅自旋为 2，同时角动量为 -2 的，相反，在其 particle-hole conjugate 的 $$\nu = 1 - 1/3$$ 填充的 FQH 态中，Graviton 激发的自旋角动量变为了 2。这种不同填充的 FQH 态对其 Graviton Angular Momentum 的 Selectivity 更是与我们常说的 Chirality 遥相呼应，我们便进一步把 FQH 中的基于内禀 Quantum Geometry 动力学的长波元激发称为“Chiral Graviton”，这也是我们在南大论文标题中看到的命名方式。

## Anisotropic FQHE and Intrinsic Quantum Geometry

说来说去，Graviton 的出现离不开 Haldane 提出的 Intrinsic Quantum Geometry of Anisotropic FQHE。相关细节参见 Haldane 的原文：

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.116801

### Band and Dielectric Anisotropy: Galilean and Coulomb (Interaction) Metric

具体而言，Haldane 在一般的磁场中的 Hamiltonian 中加入了 band mass tensor 以及 Coulomb potential 的 anisotropy，用 Galiean metric $$g^{ab}$$。
$$
H = H_0 + V 
$$
Non-interacting 部分：
$$
H_0 = \frac{1}{2} (m^{-1})^{ab} \pi_a\pi_b =  \frac{1}{2m} g^{ab} \pi_a\pi_b,
\quad \bm \pi = \bm p - e\bm A,
$$
其中磁场带来的机械动量的 non-commutative algebra 为，
$$
[r_i^a,\pi_{jb}]= i\delta_{ij}\hbar \delta^a_b, \quad 
[\pi_{ia},\pi_{jb}] = i\delta_{ij}\epsilon_{ab}\hbar^2/\ell_B^2.
$$
其中，$$\ell=\sqrt{\hbar/(eB)}$$ 为 magnetic length.

这种 non-commutative algebra 可以在各种规范选取下给出不同的 LLL（Lowest Landau Level）single-particle wavefunction，例如 isotropic 条件 $$g^{ab} = \delta^{ab}$$ 以及 symmetric gauge 下可以保留系统的旋转对称性，从而 LLL 单体波函数可以是 $$H_0$$ 与角动量 $$L_z$$ 的共同本征态，这样构造出的 LLL 单体波函数以及在此基础上构建的 Laughlin 多体波函数均为旋转对称的。

但 Haldane 考虑了更一般的 anisotropic 的 Galilean metric，即 $$g^{ab}$$ 并非各向同性的。同时，Haldane 进一步考虑了 interaction metric $$\tilde g^{ab}$$ 刻画的 interaction anisotropy：
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
这两种 anisotropy 分别来自 band mass tensor 和 dielectric tensor 的各向异性，可以是相互独立的两个 metric，而之前我们考虑的 FQH 系统往往将这两种 metric 均默认为各向同性，从而获得的波函数也是各向同性的，这便没法体现波函数自身可能出现的 anisotropy 及其内禀的 intrinsic quantum geometry 等信息。

现在，为了讨论 band mass tensor 和 dielectric tensor 的各向异性，我们需要类似 isotropic 的情形构建 anisotropic 的 LLL 波函数。在这一过程中我们将发现系统本身内禀的量子几何自由度。

### Landau Level with Anosotropic Galilean metric

先来考虑 anisotropic 的 LLL 单体波函数的构建，这完全是 isotropic 情形下的推广，细节可以参考：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.115308

具体而言，此时我们仅需考虑 mass tensor 的 anisotropy，我们可以利用一个 unimodular 的 complex vector $$\omega$$ 来 parametrize mass tensor：
$$
m_{ab}=m (\omega_a^*\omega_b + \omega_b^*\omega_a)
$$
$$
(m^{-1})^{ab}=m^{-1}(\omega^{a*}\omega^b + \omega^{b*}\omega^a).
$$
不难发现，isotropic 的特殊情形即为 $$\omega = \frac{1}{\sqrt{2}} (1, i)^T$$，更一般的 $$\omega$$ 则代表一般的 anisotropic 的情形，这便与我们讨论两者的联系与前者到后者的类比和推广。

#### Construction of Landau Level and Guiding Center Ladder Operators

单体 Hamiltonian 可以表示为：
$$
H_0 ={\textstyle \frac{1}{2}}\hbar \omega_c
\left( b^{\dagger}b + bb^{\dagger}\right)
$$
其中 $$\hbar\omega_c = \hbar^2/m\ell^2$$ 为 cyclotron energy，各向异性条件下的 Landau Level ladder operators 可以推广为：
$$
b = \hbar^{-1}\ell \left (\bm \omega \cdot \bm \pi\right ),
\quad b^\dagger = \hbar^{-1}\ell \left (\bm \omega^* \cdot \bm \pi\right )
$$
ladder operator 满足对易关系 $$[b,b^{\dagger}] = 1$$，这一 ladder operator 用于将波函数在不同 Landau Level 之间升降，升降前后相差一个 cyclotron energy。

进一步引入 "guiding center" coordinates $${\bm R}$$：
$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
“guiding center” coordinate operator 满足：
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
"guiding center" coordinates $${\bm R}$$ 用于生成 "guiding center" ladder operators：$$a$$，$$a^{\dagger}$$：
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
这一组产生湮灭算符与 $$b$$ and $$b^{\dagger}$$ 这组 Landau Level ladder operator 对易，从而可以描述同一 Landau Level 内 LLL 单体波函数的 degeneracy，这也是 isotropic LL 推导中的经典操作。

值得注意的是，以上讨论无需引入具体的 gauge 便能得到 Landau Level 及其 degeneracy 等信息，换句话说，LLL 波函数的构造可以无需引入 symmetric gauge 来 preserve rotational symmetry，这说明我们以往默认的 QH 以及 FQH 态 isotropic 的性质本身是 accidental 的，我们完全有选择 anisotropic LLL 波函数来构造 FQH 理论的自由度，这在之前是被忽略的。

更加细节的推导可以参考 UCSD 的 QHE 相关的 note：

https://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf

#### Introduction of Symmetric Gauge

更进一步我们将说明即使在 symmstric gauge 下我们也可以构造 anisotropic 的 LLL 波函数。这是因为 LLL 波函数往往通过哈密顿量 $$H_0$$ 与角动量 $$L_z$$ 的共同本征态来确定，我们将说明我们可以通过构造 anisotropic 的 $$L_z$$ 来获得不同的 LLL 单体波函数作为讨论 FQH 的基础。

我们现在选取 symmetric gauge：
$$
{\bm A}={\textstyle\frac{1}{2}}{\bm B}\times{\bm r}={\textstyle\frac{1}{2}}B(-y,x),
$$
并利用包含 mass tensor anisotropy 信息的 $$\omega$$ 来构造 complex coordinate：
$$
z = \frac{\bm \omega \cdot \bm r}{\ell}.
$$
在 isotropic mass tensor 的特殊情形下有，
$$z = \frac{x+iy}{\sqrt{2}\ell}$$
我们可以很熟练的构造 complex coordinate 下的 Landau Level 与 guiding center 的 ladder operator 的 representation，不难证明在任意 anisotropic 的 mass tensor 下这也是成立的，这里我们直接给出结论：
$$
b = {\textstyle \frac{1}{2}}z + \partial_{z*} ,\quad  b^{\dagger} =
{\textstyle \frac{1}{2}}z^* - \partial_{z}
$$
$$
a = {\textstyle \frac{1}{2}}z^* + \partial_{z} ,\quad  a^{\dagger} =
{\textstyle \frac{1}{2}}z - \partial_{z^*}
$$
对应的角动量算符可以定义为：
$$L_0 = a^{\dagger}a - b^{\dagger}b, \quad [L_0,H_0] =0$$
同时对角化 $$H_0$$ and $$L_0$$ 便能得到 n-th LL 的单体波函数 $$|\psi_{nm}\rangle$$：
$$
\begin{aligned}
&H_0|\psi_{nm}\rangle = (n+{\textstyle\frac{1}{2}})\hbar
\omega_c|\psi_{nm}\rangle, \\
&L_0|\psi_{nm}\rangle = (m-n)|\psi_{nm}\rangle, \\
&|\psi_{nm}\rangle =
\frac {(a^{\dagger})^m(b^{\dagger})^n}{\sqrt{m!n!}}|\psi_{00}\rangle\\
& a|\psi_{00}\rangle = b|\psi_{00}\rangle = 0.
\end{aligned}
$$
以上过程只是 $$\omega = \frac{1}{\sqrt{2}} (1,i)^T$$ 变为任意 unimodular vector 的推广，说明对于 general 的 Galilean metric，我们仍能构造一个 anisotropic mass tensor adapted angular momentum operator 来生成系统的“旋转对称性”，这类似将椭圆拉伸成圆，这一定程度上还是 isotropic 的，但 up to a anisotropic mass tensor。

### Intrinsic Quantum Geometry of FQH state: Guiding Center Metric

但这说明 Galilean metric 是系统“倾向”选择的 anisoropy 的方向吗？非也。我们还可以 modify $$L_0$$ 的定义（即 modify Guiding center Metric 的自由度）来说明：在未引入 interaction 以及 Coulomb metric 之前，我们的波函数选取仍有一个内禀的 quantum geometry 自由度可以选取。

我们的 Guiding Center $$R$$，及其 ladder operator $$a,\,a^\dagger$$，是为了 specify 统一 LL 内的 degenerate state 来构造的，但我们初学量子力学时便明白，degenerate states 的 complete basis 选取并非唯一的，我们完全可以对这一组基作 unitary transformation 获得一组新的完备基。在我们讨论 Guiding Center 的语境下，回顾我们之前 Guiding Center Ladder Operator 的构造：

$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
“guiding center” coordinate operator 满足：
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
"guiding center" ladder operators：$$a$$，$$a^{\dagger}$$ 的构造：
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
不难发现，我们先入为主的用了 Galilean Metric 定义的 unimodular vector $$\omega$$ 来定义 Guiding center 的 ladder operator，但我们说过：我们完全可以对这一组基作 unitary transformation 获得一组新的完备基，这在 noninteracting 的情形下完全没有问题，我们的系统目前并没有理由 specify Galilean metric 作为其 intrisic 的性质，反言之，这种完备基选取的不确定性给了我们一种构造 LLL 单体波函数的新自由度，即 Guiding Center Metric 的自由度，这在之后将衍生为我们在 FQH 中常讨论的 Intrinsic Quantum Geometric 自由度（metric 与 geometry 往往不分家）。

在 RZ Qiu, FDM Haldane, X Wan, K Yang, S Yi 等人的“Model Anisotropic quantum Hall states”一文中是这么解释的：

我们首先将角动量算符拆分：
$$
L_0 = L + \bar L
$$
$$
L  = {\textstyle\frac{1}{2}}(b^{\dagger}b + bb^{\dagger})
$$
$$
H_0  =  \hbar \omega_c L
$$
$$
\bar L = {\textstyle\frac{1}{2}}(a^{\dagger}a + aa^{\dagger}).
$$
不难发现 $$L_0 = L + \bar L$$ 中的 $$L$$ 已经和 $$H_0$$ 对易，那么 $$L_0$$ 的 nontrivial part 便来自 $$\bar L$$，

那么我们原先定义的 $$H_0$$ and $$\bar L$$ 的共同本征态可以确定 n-th LL 的 m-th degenerate wavefucntion
$$
\bar L |\psi_{nm} \rangle =
(m+{\textstyle\frac{1}{2}})|\psi_{nm}\rangle
$$
为了体现上述讨论中 Galilean metric 是怎么“先入为主”的进入我们构造 Guiding center Degeneracy 自由度的，我们可以将 $$\bar L$$ 写成：
$$
\bar L = \bar L(g^0)
$$
并定义任意 guiding center metric 下的 $$\bar L$$：
$$
\bar L(g) =  \frac{1}{2\ell^2}g_{ab}R^aR^b
$$
此处我们将来自 band mass tensor 的 "Galilean metric" 记为 $$g^0_{ab}$$ 以反映其特殊性。同时我们也以用一个 unimodular vector $$\bar \omega$$ 来定义任意 guiding center metric。

对于任意 guiding center metric 下的 $$\bar L$$：
$$
m_{ab}=m(\omega^*_a\omega_b+\omega^*_b\omega_a)=mg^0_{ab}.
$$
类似的可以用 $$\bar \omega$$ 来 parametrize 任意 guiding center metric：
$$
g_{ab} = \bar \omega^*_a \bar \omega_b+ \bar \omega^*_b \bar \omega_a.
$$
这相当于在构造 "guiding center" ladder operators：$$a$$，$$a^{\dagger}$$ 时选取了：
$$
a=\ell^{-1}\left(\bar {\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left( \bar {\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
从 $$\omega$$ 到任意的 $$\bar \omega$$，或者说等价的，从 $$g_0^{ab}$$ 到任意的 guiding center metric $$g^{ab}$$，相当于 LL 内用于区分 degeneracy 的 ladder operator 做了 Bogoliubov Transformation，说明本身描述 LL degeneracy 的完备基仍是完备的，只不过换了一组更自然，更 arbitrary，更不会被 Galilean metric“先入为主”选择的基底。

这在 noninteracting 的语境下是合理的，之后我们引入 interaction 以及 Coulomb metric 后，此事 arbitrary 的 guiding center metric/Intrinsic Quantum Geometry 便变成了多体波函数的变分 parameter，系统会倾向于选择能量更小的 guiding center metric 构成的诸如 Laughlin state 等的多体波函数。

为了区分 guiding center metric $$\bar \omega_a$$ 与原先 Galilean metric $$\omega$$ 的区别，RZ Qiu, FDM Haldane, X Wan, K Yang, S Yi 等人进一步引入了 complex number $$\gamma$$ 来 parametrize 两者的不同。

这个参数满足 $$|\gamma| < 1$$，其物理意义时类似离心率，用于定义 anisotropy up to a Galilean metric，我们可以在之后的单体波函数的 feature 后发现这一点。

具体而言，由 $$\gamma$$ parametrize 的 guiding center metric 可以进一步表示为
$$
\bar \omega_a = (1-|\gamma|^2)^{-1/2}(\omega_a + \gamma^* \omega_a^*),
$$
that determines a unimodular metric $$g_{ab}(\gamma)$$，
$$
\begin{aligned}
g_{ab}(\gamma) & = \bar \omega_a^*\bar \omega_b+\bar \omega_a\bar \omega_b^* \\
& = \frac{1}{1-\gamma^*\gamma}\left(\begin{array}{cc}
(1+\gamma)(1+\gamma^*) & i(\gamma-\gamma^*)\\
i(\gamma-\gamma^*) & (1-\gamma)(1-\gamma^*) \\
\end{array}\right)\nonumber
\end{aligned}
$$
由其定义的一组新的 "guiding center" ladder operators 为：
$$
a_\gamma =\frac{{\bar {\bm\omega}^*}\cdot{\bm R}}{\sqrt{2}\ell} ,\quad
 a_\gamma^\dagger =
\frac{{\bar {\bm\omega}}\cdot{\bm R}}{\sqrt{2}\ell}
$$
这确实是我们之前说的 Bogoliubov 变换：
$$
\left(\begin{array}{c}
a_\gamma \\
a_\gamma^\dag \\
\end{array}\right)
=\frac{1}{\sqrt{1-\gamma^*\gamma}}
\left(\begin{array}{cc}
1 & \gamma  \\
\gamma^*  & 1 \\
\end{array}\right)
\left(\begin{array}{c}
a \\
a^\dag \\
\end{array}\right).
$$
说明从 Galilean metric 到一般的 guiding center metric 的选取只是对 LL degeneracy 选取了一组新的完备基。

类似构造的 LL 单体波函数为：
$$
|\psi_{nm}(\gamma)\rangle
=\frac{(b^\dag)^n(a^{\dagger}_{\gamma})^m}{\sqrt{n!m!}}
|\psi_{00}(\gamma)\rangle
$$
其中 $$|\psi_{00}(\gamma)\rangle$$ 为 LLL 单体波函数中用于生成其他 LLL degenerate 波函数的基底，满足：
$$
a_{\gamma}|\psi_{00}(\gamma)\rangle =
b|\psi_{00}(\gamma)\rangle  = 0.
$$
之后，我们可以类似定义任意 guiding center metric 下的 LLL 单体波函数，以便之后包含 guiding center metric 变分参数的 Laughlin、MR 等多体波函数的构造，此处便不过多赘述，具体细节可以参考原文。

总而言之，我们在构造 LL 单体波函数的过程中发现了系统的 guiding center metric 定义的新自由度，在只有 Galilean metric 即没有 interaction 的情况下，其选取是任意的。本质上这一新的自由度来自 LL 内部 degenerate 完备基选取的自由度，之后引入 interaction 并构造 Laughlin、MR 等多体波函数的过程中，这一 FQH 态中 Intrinsic Quantum Geometry 的自由度会成为变分参数，在更一般的 anisotropic 的 Galilean metric 以及 interaction metric 中选取让系统及态能量最低的 guiding center metric/Intrinsic Quantum Geometry。

这一过程也被描述为“Compromise of Intrisic Geometry between Galilean and Coulomb Metric”，我们将在下一小节讨论引入 interaction 后 Intrisic Geometry 的选取。

### Compromise of Intrisic Geometry between Galilean and Coulomb Metric

如前所述，我们引入 interaction 后，Hamiltonian 为：
$$
H=T+V,
$$
动能里包含 Galilean metric，这是 anisotropy QH/FQH 态的来源之一，generally 写成：
$$
T=\frac{1}{2}(m^{-1})^{\mu\nu}\Pi_{\mu}\Pi_{\nu} = \frac{g^{\mu\nu}\Pi_{\mu}\Pi_{\nu}}{2m},
$$
为简单起见，通过 redefining basis，我们也可以写成；
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
这样 $$a=1$$ 便退化到 isotropic 的情形，一般的 $$a$$ 代表了一般的 anisotropic Galilean metric 的选取，这相当于选取了 Galilean metric：
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
类似的机械动量和 guiding center coordinate 的定义为：
$$
{\bf \Pi}={\bf p}+{e\over c}{\bf A}({\bf r})
$$
$$
{\bf R}={\bf r}-(\ell^2/\hbar)\hat{z}\times{\bf \Pi}
$$
考虑二体相互作用，其 real space 和 momentum space 的表述为：
$$
V=\sum_{i < j} V({\bf r}_i-{\bf r}_j)=\frac{1}{2}\sum_{\bf q}V_{\bf q}\rho_{\bf q}\rho_{-{\bf q}},
$$
其中 momentum space 的 density operator 为：
$$
\rho_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf r}_i}
$$
Generally 我们也会有 anisotropic 的 $$\tilde g^{ab}$$ 刻画的 interaction anisotropy：
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
这两种 anisotropy：band mass tensor 和 dielectric tensor 的各向异性，可以是相互独立的两个 metric。为简单期间，我们可以只考虑 anisotropic band mass tensor + isotropic Coulomb interaction 的情形，因为我们主要目的是看看加上 interaction 之后 guiding center metric 怎么选择能量更低的基态，从而使 noninteracting 问题中 arbitrary 的 guiding center metric 选取变成 interacting 问题中 FQH 多体态的一种 intrinsic property。

#### Projected Interaction

为了简化模型，我们考虑磁场很大，LL 之间的 splitting $$\hbar \omega_c$$ 远大于 interaction scale $$e^2/a$$ 的情况，这样我们可以认为波函数基本不会进入 higher landau level，从而可以将整个问题 project 到 LLL 中讨论，这也是讨论分数陈绝缘体时的惯用操作，感兴趣的可以参考：

https://zhuanlan.zhihu.com/p/574597173

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

具体细节可以参考：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.241105

具体而言，一般的 LL basis 下的 interaction 可以表示为：
$$
\tilde{V}=\sum_{i < j}\sum_{\bf q}v_{\bf q} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}F_n({\bf q}, a),
$$
其中的系数为：
$$
F_n({\bf q}, a)=|\langle n|e^{i{\bf q}\cdot(\hat{z}\times{\bf \Pi})}|n\rangle|^2 = e^{-(aq_x^2+q_y^2/a)\ell^2/2}|L_n[(aq_x^2+q_y^2/a)\ell^2/2]|^2
$$
对于 LLL projected interaction，其系数为：
$$
F_0({\bf q}, a)=e^{-(aq_x^2+q_y^2/a)\ell^2/2}.
$$
LLL projected interaction 为
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
其中 LLL projected density operator 为：
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
它满足的 GMP algebra 也是分数陈绝缘体构造中的重要元素。但这里我们 focus on LLL projected interaction 的形式，我们看到虽然原先的 Coulomb interaction 是 isotropic 的，但是由于 LLL 波函数构造时 Galilean metric 的 anisotropy，band mass tensor 的 anisotropy 遍进入了 projected interaction 的 anisotropy。由于 LLL 的单体能量总是相同的，故我们只需考虑 LLL projected interaction，并考虑何种波函数能让其能量最小（变分法）

#### Gaussian Interaction

即使做了这么多简化，一般形式的 interaction 也很难进行解析计算，我们进一步考虑一个特例，即 Coulomb potential 为 Gaussian function 的清形，这大致描述了一个 screnned Coulomb interaction 的特征

isotropic interaction 体现在 $$V_q$$ 的系数分布的各向同性中：$$v({\bf r})=v(r)$$，$$v_{\bf q}=v_q$$.

进一步考虑 Gaussian Interaction：
$$
v(r)=v(0)e^{-r^2/(2s^2)}
$$
从而 momentum space 中的 interaciton 也为 Gaussian 形式：
$$
v_q=v_0e^{-q^2s^2/2}
$$
进一步写成：
$$
\tilde{V}_g=\sum_{i < j}\sum_{\bf q}v_0 e^{-\tilde{q}^2\tilde{s}^2/2} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}
$$
其中
$$
\tilde{s}=[(a\ell^2+s^2)(\ell^2/a+s^2)]^{1/4}
$$
$$
\tilde{q}^2=g q_x^2 + q_y^2/g,
$$
$$
g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}.
$$
虽然以上步骤都是简单的数学推导，但我们之后会发现此处定义的 $$g$$ 与上一 section 讨论的 guiding center metric 的 anisotropy 直接相关，而且在这种特殊的 Gaussian Interaction 下，$$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$$ 直接给出了一个 interaction 问题中使得多体基态波函数能量最低的 guiding center metric 选取。

首先来看此处 g 的一些性质：

$$g\rightarrow a$$ for $$s\ll \ell$$, $$g\rightarrow 1$$ for $$s\gg \ell$$

同时 generally 我们有：
$$
1 < g < a
$$
事实上，下界 1 反映了 isotropic 的 interaction metric，上界 $$a$$ 则反映了 anisotropic 的 mass tensor metric，如果我们认可了之前关于 $$g$$ 便是最佳基态选取的 intrinsic quantum geometry 的 anisotropu 信息，这个不等式确实反映了本 section 开头的论述：

Intrisic Geometry as a Compromise between Galilean and Coulomb Metric.

#### Many-Body Gruond State of Anisotropic FQHE

下面我们通过一些 argument 来证明 $$g$$ 与 FQH 态 Intrinsic quantum geometry/guiding center metric 的联系，同时说明为何 $$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$$ 为 Laughlin 等多题波函数变分参数的最佳选取。

首先，我们可以建立一般 $$g$$ 和 $$g=1$$ 特殊情形的联系：
$$
\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)],
$$
其中：
$$
O(\lambda)=e^{{i\lambda\over 2\ell^2}\sum_j R^j_x R^j_y},
$$
$$
\lambda(g)=-{1\over 2}\ln g
$$
$$
O^\dagger(\lambda)R_x^i O(\lambda)=e^{\lambda} R_x^i
$$
$$
O^\dagger(\lambda)R_y^i O(\lambda)=e^{-\lambda} R_y^i.
$$
这个 guiding center 从 isotropic 变为 anisotropic 的过程，与之前选取不同 guiding center metric 来构造 guiding center operator 从而构造 LL 内部一组完备 degenerate 基底的操作是一致的，这便说明了 $$g$$ 与 FQH 态 Intrinsic quantum geometry/guiding center metric 的联系。

进一步，由于我们知道 $$g=1$$ 便是 isotropic 的特殊情形，此时我们熟知 Interaction LLL 下的基态便是 Laughlin State（严格来说 Laughlin State 在 2-body Haldane Pseudopotential 下才是严格基态，但我们姑且认为 Gaussian interaction 下 Laughlin state 仍然接近 FQH 基态），那么 $$\tilde{V}_{g=1}$$ 的基态（动能可以忽略）便是 $$|\Psi_{GS,g=1}\rangle \approx |\Psi_{Laughlin} \rangle$$，

从而变换后 $$\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)]$$ 的基态大致可以认为是（Hamiltonian 相差一个 Unitary 变换，能谱不改变，对应的包括基态在内的波函数也应该只差一个同样的 Unitary 变换）：
$$
|\Psi_{GS,g}\rangle=O^\dagger[\lambda(g)]|\Psi_{g=1}\rangle \approx O^\dagger[\lambda(g)] |\Psi_{Laughlin} \rangle =|\Psi^{Laughlin}_{g}\rangle
$$
再加上之前关于 $$g$$ 表示了系统 guiding center metric anisotropy 的信息这一点，我们可以认为 $$|\Psi^{Laughlin}_{g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}}\rangle$$ 便是以 guiding center metric anisotropy/Intrinsic quantum geometry 为变分参数的更 general 的 Laughlin 波函数在 anisotropic mass tensor + isotropic gaussian interaction 下的最佳变分基态解。

从而 $$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)} \in (1,a)$$ 完全反映了 FQH 的 Intrinsic Geometry 在不同 interaction 下的 determination，定性而言还是本 section 开头的论述：

Intrisic Geometry as a Compromise between Galilean and Coulomb Metric

至此，我们说明了 FQH 内部 Intrinsic Quantum Geometry 自由度的来源及其 determination from a variational Compromise between Galilean and Coulomb Metric。这说明即使在破坏旋转对称性的系统中，anisotropic 的 FQH 态仍可能是基态，若进一步考虑与 Intrinsic Quantum Geometry 自由度 couple 的微扰，我们便能关注这一 Intrinsic Quantum Geometry 的 dynamics，which turns out to be 南大发现的 chiral graviton mode。

## Dynamics of Intrinsic Qunatum Geometry as Chiral Graviton

下面我们来考虑 FQH 态中 Intrinsic Quantum Geometry 的 Dynamics 及其 Chiral Graviton 的准粒子激发。

### Dynamics of Intrinsic Quantum Geometry

最直接的想法是找一个和 Intrinsic Quantum Geometry 直接 couple 的微扰，但这一般比较难实现，我们在模型中比较容易直接 couple 的自由度是 band mass tensor，例如利用 acoustic wave 来扰动 FQH 的 background lattice system。我们姑且认为我们上述关于 Gaussian Interaction 下 Intrinsic Quantum Geometry determined by band mass tensor anisotropy 的 picture 在更一般的情形下也是 feasible 的，那么我们可以认为 couple 了 band mass tensor 就相当于间接 couple 了 Intrinsic Quantum Geometry。

为简单起见，仍采用动能：
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
这相当于选取了 Galilean metric：
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
再考虑一般的 LLL projected interaction：
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
假设我们通过 acoustic wave 对 band mass anisoropy 进行了一个含时微扰：
$$
a=1+\xi(t)
$$
这会通过 $$g = g(a)$$ 体现在 oscillating 的 metric，我们知道 oscillating metric 的物理图像便是重力波，"gravitational wave"，那么我们用 oscillating metric 激发出的准粒子很有可能与我们在高能中讨论的 graviton 有类似的性质。

对 $$\tilde{V}$$ 根据 $$a=1+\xi(t)$$ 进行微扰展开：
$$
\delta\tilde{V}(t)=\frac{\xi(t)}{4}\sum_{\bf q}(q^2_y - q^2_x)V_{\bf
q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf q}\overline{\rho}_{-{\bf q}}.
$$
我们发现 $$(q^2_y - q^2_x)$$ 的部分确实有 d 波的对称性，这说明 oscillating metric 激发出的准粒子很可能是自旋为 2 的准粒子，这与高能物理中普遍认为的 graviton 的 spin-2 性质“不谋而合”（本质是因为两者都是 metric 场的 oscilation，其 quantum 有类似的性质也不难猜测）。

对于时谐微扰，其实验测得的谱函数为不难通过我们熟知的 Fermi Golden Rule 得到：
$$
I(\omega)=\sum_n|\langle n|\hat{O}|0\rangle|^2\delta(\omega-\omega_n),
$$
其中微扰算符为：
$$
\hat{O}=\sum_{\bf q}(q^2_y - q^2_x)V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}}
$$
我们可以进一步将这个微扰算符拆为 $$S_z = \pm 2$$ 的形式：
$$
\hat{O}_\mp^{(2)}=\sum_{\bf q}(q_x \mp i q_y)^2 V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
这两个算符分别反映了自旋为 $$S_z = \pm2$$ 的 graviton 激发，其对应的 spectrum 为：
$$
I_\sigma(\omega)=\sum_n|\langle n|\hat{O} _{\sigma}|0\rangle|^2\delta(\omega-\omega_n),
$$
其中，$$\hat{O}_\mp$$ 可以视为 graviton 的产生湮灭算符，此处相当于我们 specify 了产生的准粒子激发只能是 $$S_z = -2$$ 的，故这种 graviton 激发也被称为手征引力子，Chiral Graviton。我们之后会说明这种选择的来源，相反的，对于 particle-hole conjugate 的 FQH 态，graviton 激发的自旋是相反的，这进一步反映其 Chiral 的特性。

而 $$\hat{O}=(\hat{O} _{+} + \hat{O} _{-})/2$$ 相当于 displacement operator in a harmonic oscillator，作为微扰算符与“gravitational wave"（本质为 acoustic wave induced oscillating mass tensor anisotropy）相耦合。

### Chirality of Graviton

为何 Graviton 的激发是手征的？我们以 $$\nu = 1/3$$ 的 Laughlin state 为例进行分析，不难发现，$$\hat{O}_\mp$$ 作用在 2 particle wave function 上有
$$
O_{+} \propto \sum\limits_{M} |m+2, M \rangle \langle m, M|
$$
$$
O_{-} \propto \sum\limits_{M} |m, M \rangle \langle m + 2, M|$$
其中 $$|m, M \rangle$$ 中的 $$m$$ 和 $$M$$ 分别代表了二体波函数态的 relative angular momentum 和 center-of-mass angular momentum。

不难发现 $$\hat{O}_{+}$$ 会将 Laughlin state 湮灭：因为 $$\hat{O}_{+}$$ 会将一对 relatively angular momentum $$m$$ 的二粒子态变为 relatively angular momentum $$m+2$$ 而这不在 Laughlin state 内，从而会将 Laughlin state annihilate。

这样，$$I _{+}(\omega)$$ 谱永远是 0. 而 $$I _{-}(\omega)$$ 总是 show strong graviton peaks in fermionic and bosonic cases，这便说明 $$\nu = 1/3$$ 的 Laughlin state 的 graviton 激发总是 $$S_z  =-2$$ 的；反之其 PH conjugate 的 $$\nu = 1 - 1/3$$ 的空穴 Laughlin state 的 graviton 激发总是 $$S_z  = 2$$ 的，这便体现了 graviton 激发的 chirality。

### Inaccessability of normal Magnetoroton modes

本质上，graviton mode 是我们在 FQH 中讨论的中性集体激发：GMP magnetoroton mode 在 $$k\rightarrow 0$$ 的极限；换句话说，在长波极限下，FQH 的动力学可以由我们上面讨论的 Intrinsic Quantum Geometry 的 dynamics 来决定。有些情况下 chiral gravviton mode 也被称为 GMP magnetoroton mode 长波极限下的特殊情形，但由于在长波极限下，GMP magnetoroton mode 的 structural factor $$\langle 0|\rho_{{\bf k}}\rho_{-{\bf k}}|0\rangle\propto (k\ell)^4$$，故此时很难用一般的电磁场与电子密度耦合的方法来 detect 长波极限下的 GMP magnetoroton mode。关于 GMP magnetoroton 的细节也可以参考我之前的 note：

https://zhuanlan.zhihu.com/p/574597173

总之由于上述原因，虽然 GMP magnetoroton mode 已经在实验上被观测到，但是其长波极限的 detection 比较困难。一般的电磁场微扰由于光子自旋是 1，难与自旋为 2 的 graviton 耦合，故常规的方法失效。这样一来，graviton mode 在 Intrinsic Quantum Geometry‘s origin 以及 experimental detection 的特殊性，使其往往与一般的 GMP magnetoroton mode 有所区分，其探测也成了凝聚态物理领域一件非常有意义的事。

### Detection of Chiral Graviton in FQHE

除了上述的 Acoustic wave 的方法，南京大学探测 graciton 的方法则是利用了 circular polarized light 相关的 spectroscopy。因为圆偏振光有 $$S_z = \pm1$$ 的自旋，所以若用 $$S_z = -1$$ 的圆偏振光激发一个 $$S_z = -2$$ 的 chiral graviton，这样系统吸收后再发出的光便应该是 $$S_z = =1$$ 的，通过这种原理，南京大学的 Lingjie Du 课题组与其德国美国同行成功发现了 FQHE 中的 chiral graviton mode 并发表了 nature，这便是我们所熟知的故事了。

## Relation with Band Geometry from Momentum-Space Duality

上述过程中我们讨论的 FQH 态的 Intrinsic Quantum Geometry，与我们在分数陈绝缘体、平带超导、非线性响应中常讨论的 Band Geometry 在定义上是不同的，但两者的度规场本质是一致的，这种 Geometric Discription of FQH state 的想法，也被引入到分数陈绝缘体等讨论 Band Geometry 的体系中，提供关于 FQH 态在 lattice 系统中稳定性及其他性质的 insights。

例如 Claassen, M., Lee, C. H., Thomale, R., Qi, X. L., & Devereaux, T. P. 等人 2015 年的一篇题为“Position-momentum duality and fractional quantum hall effect in chern insulators”的 PRL 便讨论了 Band Geometry 与 FQH 态的 Intrinsic Quantum Geometry 的联系。

具体而言，在 Band System 中，我们有波函数空间（Projected Hilbert Space $$\mathbb{C}P^{N-1}$$）的辛几何，其虚部是我们熟知的 Berry Curvature，类似动量空间的磁场：
$$
\Omega(k) = \epsilon^{\mu\nu} \partial_{k_\mu} \mathbf{A}_\nu(k)
$$
来自一个类似 momentum space 的 vector potential，Berry Connection：
$$
\mathbf{A}_\nu(k) = -i \langle u_k | \partial_{k_\nu} | u_k \rangle
$$
而辛几何的 real part 则定义了波函数空间的度规，即 Fubini-Study metric
$$
g_{\mu\nu}(k) = \frac{1}{2} \langle \partial_{k_\mu} u_k | \left[1 - |u_k\rangle \langle u_k | \right] | \partial_{k_\nu} u_k \rangle + \left(\mu \leftrightarrow \nu \right)
$$
通过与 FQH 中通过角动量算符来区分 LLL 中的 egeneracy 类似的方法，我们可以类似定义一个 confinment potential 使其与哈密顿量的本征态 coincide，从而达到了在破坏了 rotational symmetry 的 lattice 系统中定义“赝角动量算符”的目的：
$$
\hat{V}(r)= \tfrac{1}{2} \lambda~ x_{\mu} \eta^{\mu\nu} x_{\nu}
$$
$$\eta^{\mu\nu}$$ 便可以用来描述破坏了 rotational symmetry 的 lattice 系统中定义“赝角动量算符”所用到的 metric，即 analogy of Guiding Center Metric in Lattice System，即 Intrinsic Quantum Geometry 的 Lattice version。

类似的考虑 LLL 上的 projection，此单体“赝角动量算符”（本质为一个人为的 confinement potential）的投影为：
$$
\bar{V} =  \hat P\hat V(r)\hat P^\top= \frac{\lambda}{2} \Pi_\mu \eta^{\mu\nu} \Pi_\nu + \frac{\lambda}{2} \eta^{\mu\nu} g_{\nu\mu},\,k \in {\rm BZ}
$$
等是右侧的第一项便是我们常见的动能算符，除此之外还有一项与 Band Geometry 耦合的项，这说明 Lattice System 中的 FQH 物理相比 continuum system 中的 FQH 物理，还收到了 Band Geometry 的影响，两者的 Coupling 给出了 FQH 在更 general system 中的 Intrinsic Quantum Geometry 的物理，相关的细节可以进一步参考原文：

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.114.236802

这里我们点到为止，说明 Intrinsic Quantum Geometry 以及 Band Geometry 的联系即可。

## Summary

综上所述，我们讨论了近日热议的“南京大学（在 FQH 系统中）发现（手征）引力子（的准粒子激发）”的新闻，给出了 FQH 态中 Intrinsic Quantum Geometry 的由来，并讨论了其 dynamics 的准粒子所对应的 Chiral Graviton mode 的由来，并简要讨论了其 detection 以及与我们熟悉的 Band Geometry 的联系，希望能给大家提供更多科学吃瓜的素材。

## Reference

- [Evidence for chiral graviton modes in fractional quantum Hall liquids](https://www.nature.com/articles/s41586-024-07201-w)

- [Geometrical description of the fractional quantum Hall effect](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.116801)

- [Magneto-roton theory of collective excitations in the fractional quantum Hall effect](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.33.2481)

- [Chiral gravitons in fractional quantum hall liquids](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.123.146801)

- [Fractional quantum Hall states in two-dimensional electron systems with anisotropic interactions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.86.035122)

- [Band mass anisotropy and the intrinsic metric of fractional quantum Hall systems](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.165318)

- [Acoustic wave absorption as a probe of dynamical geometrical response of fractional quantum hall liquids](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.93.161302)

- [Geometry of compressible and incompressible quantum Hall states: Application to anisotropic composite-fermion liquids](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.241105)

- [Model anisotropic quantum Hall states](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.115308)

- [Position-momentum duality and fractional quantum hall effect in chern insulators](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.114.236802)

- [UCSD QHE Lecture note](https://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf)