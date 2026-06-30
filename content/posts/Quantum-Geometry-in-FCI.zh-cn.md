---
title: "🤩量子几何（Quantum Geometry）"
date: 2022-11-05T10:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Fubini-Study Metric", "Berry Curvature", "Fractional Chern Insulator", "Condensed Matter"]
categories: ["Physics Notes"]
---

本note旨在带读者快速上手Quantum Geometry的定义及其计算。Topology是量子系统的重要性质，反映了模型绝热变化过程中的不变量，而Geometry关注系统的细节——找到合适的刻画量子态之间"距离"的物理量便是Quantum Geometry的中心问题。

<!--more-->

下面，我们通过找到态矢量生活的真实物理空间——Projected Hilbert Space，在其上定义度规，并计算简单模型的Quantum Geometric Tensor，带领读者初探Quantum Geometry这一神奇的领域。

## Hilbert Space is not Physical

量子态可以看做希尔伯特空间$\mathcal{H}$中的矢量，分量均为复数，以n维的希尔伯特空间为例，量子态就是属于$\mathbb{C}^n$的态矢，可以写成：

$$ |\psi\rangle = (\psi_1, \cdots, \psi_n)^T $$

$$ \psi_i \in \mathbb{C},\,i = 1, \cdots, n $$

但这并不是真实的物理空间，我们知道，态矢乘上一个复数仍为相同的态，所以真实的量子态空间应当是希尔伯特空间**模掉**一个非零复数。

具体而言，我们先将态矢的分量变成实数，并且要求态不能是0，这相当于：

$$ \mathcal{H} \simeq \mathbb{C}^n - \{\mathbf{0}\} \simeq \mathbb{R}^{2n}-\{\mathbf{0}\} $$

现在模掉一个非零复数$\mathbb{C}-\{\mathbf{0}\}$。由于非零复数是一个模长$\R^+$和一个相位$U(1)$

$$ \mathbb{C}-\{\mathbf{0}\} \simeq \R^+ \times U(1) $$

可以分成两步，第一步先令模长相同，即模掉一个正实数，可以想像这会让去掉原点的2n维空间变成2n-1维的球面：

$$ (\mathbb{R}^{2n}-\{\mathbf{0}\})/\R^+ \simeq S^{2n-1} $$

再模掉一个相位，这会得到一个复投影空间：

$$ S^{2n-1}/U(1) \simeq \mathbb{C}P^{n-1} $$

我们把量子态真实生活的空间称为投影希尔伯特空间(Projected Hilbert Space)$\mathcal{P}\mathcal{H} \simeq \mathbb{C}P^{n-1}$。

## Introduction and Definition

对于Hilbert Space中的态矢，我们可以定义其距离为：

$$
\mathrm{d} s^2=\| \psi(\lambda+\mathrm{d} \lambda)-\left.\psi(\lambda)\right|^2=\langle\delta \psi \mid \delta \psi\rangle \\
=\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu \\
=\left(\gamma_{\mu \nu}+i \sigma_{\mu \nu}\right) \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu
$$

由于**内积的厄米性质**，我们有：

$$
\gamma_{\mu \nu}+i \sigma_{\mu \nu}=\gamma_{\nu \mu}-i \sigma_{\nu \mu} \quad \gamma_{\mu \nu}=\gamma_{\nu \mu} \quad \sigma_{\mu \nu}=-\sigma_{\nu \mu} $$ 

但是Hilbert Space并不是真实的量子态空间，因为我们还可以对做规范变换（改变相位）而保持态不变，此时定义在参数空间中的"距离"以及度规应该仍然相同，因为参数空间每个点对应的态不变，只是改变了一个相位（此处仅考虑归一化的态），但我们立刻会发现之前定义的"度规"有问题。

具体而言，我们对参数空间到态空间的映射做一个任意的规范变换，有：

$$
\left|\psi^{\prime}(\lambda)\right\rangle=\exp ^{i \alpha(\lambda)}|\psi(\lambda)\rangle 
$$

对应的度规张量变为：

$$ \left\langle\partial_\mu \psi^{\prime} \mid \partial_\nu \psi^{\prime}\right\rangle=\gamma_{\mu \nu}^{\prime}+i \sigma_{\mu \nu}^{\prime} $$ 

$$
\gamma_{\mu \nu}^{\prime}=\gamma_{\mu \nu}-\beta_\mu \partial_\nu \alpha-\beta_\nu \partial_\mu \alpha+\partial_\mu \alpha \partial_\nu \alpha $$ 

$$
\sigma_{\mu \nu}^{\prime}=\sigma_{\mu \nu} $$ 

其中的$\beta$为Berry Connection，定义为

$$ \beta_\mu \equiv i \langle \psi (\lambda) | \partial_\mu \psi (\lambda) \rangle \in \R $$

可见，我们naively定义的度规并不是物理的，物理的度规应当是规范不变的。

我们不妨考虑以下表达式：

$$
g_{\mu \nu}(\lambda):=\gamma_{\mu \nu}(\lambda)-\beta_\mu(\lambda) \beta_\nu(\lambda)
$$

不难证明，将度规（实部，即Fubini-Study Metric）改为上述表达式后，新定义的度规将变为规范不变的量。

此时Quantum Geometric Tensor的定义为：

$$
Q_{\mu \nu}(\lambda):=\left\langle\partial_\mu \psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle-\left\langle\partial_\mu \psi(\lambda) \mid \psi(\lambda)\right\rangle\left\langle\psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle $$ 

实部用于刻画量子态之间的距离，称为**Fubini-Study metric** (FS metric)，是对称张量：

$$
g_{\mu \nu}=\operatorname{Re} Q_{\mu \nu}$$ 

而虚部为**Berry Curvature**部分（和真正的Berry Curvature差了系数2），是反对称张量：

$$ \sigma_{\mu \nu}=\operatorname{Im} Q_{\mu \nu} $$ 

我们也可以这么看待两个态之间的距离：假设态的振幅均已归一化，从而态矢均为分布在球面上的点，球面上点的距离可以表示为：

$$
D^2\left(\mathbf{k}, \mathbf{k}^{\prime}\right) \equiv D^2\left[\mu(\mathbf{k}), \mu\left(\mathbf{k}^{\prime}\right)\right] =2-2\left|\mu^{\dagger}(\mathbf{k}-\mathbf{q}) \mu(\mathbf{k})\right| $$

取内积相当于取两个态矢量夹角的余弦值$\cos \theta$，而取$|...|$是为了将不确定的相位影响去掉，从而只留下振幅的影响，而$2 - 2 \cos \theta = 4 \sin^2\frac{\theta}{2}$, 从而$D = 2 \sin \frac{\theta}{2}$，即球面上两点的直线距离。在两点十分接近时，这同时也是球面上两点间"测地线"距离。由此可以看出这个$D(k,k')$定义确实有"距离"的含义。

可以证明，将上述$D(k,k')$定义对很接近的两点$k$, $k'$做展开，得到的度规表达式和我们上述的定义相同。当然这只在小量近似下成立。

## Alternative Expression

在实际数值计算时，我们用计算机对角化得到的本征态矢量的相位是没有固定关系的，这个时候$|\partial_\mu \phi \rangle$的计算很可能出现问题，因此我们引入下面等价的表达式，将计算中对态矢的偏导转变为对哈密顿量的偏导，由于$H(k)$的定义一般是连续函数，我们既可以解析计算，也可以数值上差分，从而保证我们FS metric、Berry Curvature以及整个Quantum Geometric Tensor等物理量数值模拟结果的准确性。

我们利用一下等式，其中态矢均为$H$的本征态：

$$
\left\langle\phi_n \mid \partial_\mu \phi_0\right\rangle=\frac{\left\langle\phi_n\left|\partial_\mu H\right| \phi_0\right\rangle}{E_0-E_n} \quad \text { if } n \neq 0 $$ 

$$
\left\langle\phi_0\left|\partial_\mu H\right| \phi_0\right\rangle=\partial_\mu E_0$$ 

从而：

$$
Q_{\mu \nu}=\left\langle\partial_\mu \phi_0\left|\left(\mathbf{1}-\left|\phi_0\right\rangle\left\langle\phi_0\right|\right)\right| \partial_\nu \phi_0\right\rangle$$ 

$$
=\sum_{n \neq 0}\left\langle\partial_\mu \phi_0 \mid \phi_n\right\rangle\left\langle\phi_n \mid \partial_\nu \phi_0\right\rangle$$ 

$$
=\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

其中Berry Curvature的表达式为：

$$
F_{\mu \nu}=\partial_{[\mu} \beta_{\nu]}=i\left\langle\partial_{[\mu} \phi_0 \mid \partial_{\nu]} \phi_0\right\rangle=i\left(Q_{\mu \nu}-Q_{\nu \mu}\right)=-2 \operatorname{Im} Q_{\mu \nu}=-2 \sigma_{\mu \nu} $$ 

这说明Berry Curvature和Quantum Geometric Tensor的虚部仍然有系数为2的差别：

$$
Q_{\mu \nu}=g_{\mu \nu}-\frac{i}{2} F_{\mu \nu} $$ 

上述定义均在非简并的情况下成立，对于n重简并的情况，我们上述的所有标量都将变成n维矩阵，此时的FS metric、Berry Curvature以及整个Quantum Geometric Tensor等物理量也将变为non-Abelian量。

$$
{\left[Q_{\mu \nu}\right]_{i j}=\sum_{n \neq 0, k(n)} \frac{\left\langle\phi_{0 i}\left|\partial_\mu H\right| \phi_{n k}\right\rangle\left\langle\phi_{n k}\left|\partial_\nu H\right| \phi_{0 j}\right\rangle}{\left(E_0-E_n\right)^2}} $$ 

![Image](https://pic4.zhimg.com/80/v2-d327ed01b77d2a2414e5ff2cd596f371.png)

## E.g. Spin-1/2 Systems

不妨对最简单的二能级系统算一算其Quantum Geometric Tensor，此处选取的系统为磁场中的Spin-1/2系统，参数为磁场的方位角$\theta \in [0,\pi]$, $\phi \in [0,2\pi]$，Hamiltonian为：

$$
H=\mu \vec{\sigma} \cdot \vec{B} = \mu |B| \left(\begin{array}{cc}
\cos \theta & \sin\theta e^{-i\phi} \\
\sin\theta e^{i\phi} & - \cos \theta
\end{array}\right) = \mu |B| \vec{\sigma} \cdot \hat{B}
$$

二能级系统的本征值、本征态十分容易得到，为：

$$ E_{\pm} = \pm \mu |B| $$

$$
|+\rangle =\left(
e^{-i \phi / 2} \cos \frac{\theta}{2}, e^{i \phi / 2} \sin \frac{\theta}{2}
\right)^T
$$

$$
|-\rangle=\left(-e^{-i \phi / 2} \sin \frac{\theta}{2}, e^{i \phi / 2} \cos \frac{\theta}{2}\right)^T $$

利用上面提到的公式：

$$
Q_{\mu \nu} =\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

即可得到对于二能级系统：

$$
Q^{(\pm)}_{\mu \nu} =\frac{\left\langle \pm \left|\partial_\mu H\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu H\right| \pm\right\rangle}{\left(E_\pm-E_\mp\right)^2}
$$

分母分子消去$\mu |B|$得到：

$$ Q^{(\pm)}_{\mu \nu} = \frac{1}{4} \left\langle \pm \left|\partial_\mu (\vec{\sigma} \cdot \hat{B})\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu(\vec{\sigma} \cdot \hat{B})\right| \pm\right\rangle $$

其中，$\mu,\,\nu = \theta,\,\phi$

进一步：

$$ \partial_\theta (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
-\sin \theta & \cos \theta e^{-i\phi} \\
\cos \theta e^{i\phi} &  \sin \theta
\end{array}\right) $$

$$ \partial_\phi (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
0 & -i \sin \theta e^{-i\phi} \\
i \sin \theta e^{i\phi} &  0
\end{array}\right) $$

直接带入一通爆算，得到：

$$
g^{(\pm)}_{\mu \nu} = \frac{1}{4} \left(\begin{array}{cc}
1 & 0 \\
0 & \sin ^2 \theta
\end{array}\right) $$

$$
F^{(\pm)}_{\mu \nu}=\pm \frac{1}{2}\left(\begin{array}{cc}
0 & - \sin \theta \\
 \sin \theta & 0
\end{array}\right) $$

**注意计算过程中左矢要取复共轭！**

不难发现，此处的度规即半径为$1/2$球面上的自然度规。说明态之间的距离其实就是Bloch球上的"测地线"弧长。

## Reference

[1] Cheng, R. (2010). Quantum geometric tensor (Fubini-Study metric) in simple quantum system: A pedagogical introduction. arXiv:1012.1337.

[2] Abouelkomsan, A., Yang, K., & Bergholtz, E. J. (2022). Quantum Metric Induced Phases in Moiré Materials. arXiv:2202.10467.

[3] Parker, D., Ledwith, P., Khalaf, E., Soejima, T., Hauschild, J., Xie, Y., ... & Vishwanath, A. (2021). Field-tuned and zero-field fractional Chern insulators in magic angle graphene. arXiv:2112.13837.

[4] Ozawa, T., & Mera, B. (2021). Relations between topology and the quantum metric for Chern insulators. *Physical Review B*, 104(4), 045103.

[5] Parameswaran, S. A., Roy, R., & Sondhi, S. L. (2012). Fractional Chern insulators and the $W_\infty$ algebra. *Physical Review B*, 85(24), 241308.

[6] Roy, R. (2014). Band geometry of fractional topological insulators. *Physical Review B*, 90(16), 165139.

[7] Wang, J., Cano, J., Millis, A. J., Liu, Z., & Yang, B. (2021). Exact Landau level description of geometry and interaction in a flatband. *Physical Review Letters*, 127(24), 246403.

[8] Simon, S. H., & Rudner, M. S. (2020). Contrasting lattice geometry dependent versus independent quantities. *Physical Review B*, 102(16), 165148.

[9] Wang, J., Klevtsov, S., & Liu, Z. (2022). Origin of Model Fractional Chern Insulators in All Topological Ideal Flatbands. arXiv:2210.13487.

[10] Ledwith, P. J., Vishwanath, A., & Parker, D. E. (2022). Vortexability: A Unifying Criterion for Ideal Fractional Chern Insulators. arXiv:2209.15023.

[11] Daniel Arovas, 'Lecture Notes on Quantum Hall Effect', http://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf
