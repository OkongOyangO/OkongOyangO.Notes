---
title: "🤩量子幾何学（Quantum Geometry）：量子幾何テンソル入門"
date: 2026-06-30T11:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Fubini-Study Metric", "Berry Curvature", "Fractional Chern Insulator", "Condensed Matter"]
categories: ["Physics Notes"]
---

本ノートでは、Quantum Geometryの定義とその計算法を読者に迅速に習得させることを目的とする。Topologyは量子系の重要な性質であり、系の断熱変化における不変量を反映する。一方Geometryは系の詳細に着目する——量子状態間の「距離」を適切に記述する物理量を見つけることが、Quantum Geometryの中心問題である。

<!--more-->

以下では、状態ベクトルが実際に存在する物理空間——射影ヒルベルト空間（Projected Hilbert Space）——を見出し、その上に計量を定義し、単純な模型のQuantum Geometric Tensorを計算することで、読者をQuantum Geometryという魅力的な分野へと導く。

## Hilbert Space is not Physical

量子状態はヒルベルト空間$\mathcal{H}$内のベクトルとみなすことができ、その成分はすべて複素数である。$n$次元ヒルベルト空間を例にとると、量子状態は$\mathbb{C}^n$に属する状態ベクトルであり、次のように書ける：

$$ |\psi\rangle = (\psi_1, \cdots, \psi_n)^T $$

$$ \psi_i \in \mathbb{C},\,i = 1, \cdots, n $$

しかしこれは真の物理空間ではない。状態ベクトルに複素数を乗じても同じ状態であることが知られている。したがって、真の量子状態空間はヒルベルト空間から**非零複素数で割った**空間である。

具体的には、まず状態ベクトルの成分を実数にし、状態が0でないことを要請する。これは次と等価である：

$$ \mathcal{H} \simeq \mathbb{C}^n - \{\mathbf{0}\} \simeq \mathbb{R}^{2n}-\{\mathbf{0}\} $$

ここで非零複素数$\mathbb{C}-\{\mathbf{0}\}$で割る。非零複素数はノルム$\R^+$と位相$U(1)$に分解できる：

$$ \mathbb{C}-\{\mathbf{0}\} \simeq \R^+ \times U(1) $$

これを二段階に分ける。第一段階としてノルムを揃える、すなわち正実数で割る。これにより原点を除いた$2n$次元空間は$2n-1$次元球面になる：

$$ (\mathbb{R}^{2n}-\{\mathbf{0}\})/\R^+ \simeq S^{2n-1} $$

さらに位相で割ると、複素射影空間が得られる：

$$ S^{2n-1}/U(1) \simeq \mathbb{C}P^{n-1} $$

量子状態が実際に存在する空間を射影ヒルベルト空間（Projected Hilbert Space）$\mathcal{P}\mathcal{H} \simeq \mathbb{C}P^{n-1}$と呼ぶ。

## Introduction and Definition

ヒルベルト空間内の状態ベクトルに対して、その距離を次のように定義できる：

$$
\mathrm{d} s^2=\| \psi(\lambda+\mathrm{d} \lambda)-\left.\psi(\lambda)\right|^2=\langle\delta \psi \mid \delta \psi\rangle \\
=\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu \\
=\left(\gamma_{\mu \nu}+i \sigma_{\mu \nu}\right) \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu
$$

**内積のエルミート性**から、次が成り立つ：

$$
\gamma_{\mu \nu}+i \sigma_{\mu \nu}=\gamma_{\nu \mu}-i \sigma_{\nu \mu} \quad \gamma_{\mu \nu}=\gamma_{\nu \mu} \quad \sigma_{\mu \nu}=-\sigma_{\nu \mu}
$$

しかしヒルベルト空間は真の量子状態空間ではない。なぜなら、状態にゲージ変換（位相の変更）を施しても状態自体は不変だからである。このときパラメータ空間上で定義される「距離」および計量は不変であるべきである（パラメータ空間の各点に対応する状態は変わらず、位相が変わるだけである。ここでは規格化された状態のみを考える）。しかし、先に定義した「計量」には問題があることがすぐにわかる。

具体的には、パラメータ空間から状態空間への写像に任意のゲージ変換を施すと：

$$
\left|\psi^{\prime}(\lambda)\right\rangle=\exp ^{i \alpha(\lambda)}|\psi(\lambda)\rangle
$$

対応する計量テンソルは次のように変化する：

$$ \left\langle\partial_\mu \psi^{\prime} \mid \partial_\nu \psi^{\prime}\right\rangle=\gamma_{\mu \nu}^{\prime}+i \sigma_{\mu \nu}^{\prime} $$

$$
\gamma_{\mu \nu}^{\prime}=\gamma_{\mu \nu}-\beta_\mu \partial_\nu \alpha-\beta_\nu \partial_\mu \alpha+\partial_\mu \alpha \partial_\nu \alpha
$$

$$
\sigma_{\mu \nu}^{\prime}=\sigma_{\mu \nu}
$$

ここで$\beta$はBerry Connectionであり、次のように定義される：

$$ \beta_\mu \equiv i \langle \psi (\lambda) | \partial_\mu \psi (\lambda) \rangle \in \R $$

このように、我々が素朴に定義した計量は物理的なものではない。物理的な計量はゲージ不変でなければならない。

そこで以下の式を考えてみよう：

$$
g_{\mu \nu}(\lambda):=\gamma_{\mu \nu}(\lambda)-\beta_\mu(\lambda) \beta_\nu(\lambda)
$$

計量（実部、すなわちFubini-Study Metric）を上記の式に変更すると、新たに定義された計量がゲージ不変量になることは容易に証明できる。

このときQuantum Geometric Tensorは次のように定義される：

$$
Q_{\mu \nu}(\lambda):=\left\langle\partial_\mu \psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle-\left\langle\partial_\mu \psi(\lambda) \mid \psi(\lambda)\right\rangle\left\langle\psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle
$$

実部は量子状態間の距離を記述し、**Fubini-Study metric**（FS metric）と呼ばれる対称テンソルである：

$$
g_{\mu \nu}=\operatorname{Re} Q_{\mu \nu}
$$

一方、虚部は**Berry Curvature**の部分（真のBerry Curvatureとは係数2の差がある）であり、反対称テンソルである：

$$ \sigma_{\mu \nu}=\operatorname{Im} Q_{\mu \nu} $$

二つの状態間の距離は次のようにも解釈できる。状態の振幅がすべて規格化されていると仮定すると、状態ベクトルは球面上に分布する点となる。球面上の点の距離は次のように表せる：

$$
D^2\left(\mathbf{k}, \mathbf{k}^{\prime}\right) \equiv D^2\left[\mu(\mathbf{k}), \mu\left(\mathbf{k}^{\prime}\right)\right] =2-2\left|\mu^{\dagger}(\mathbf{k}-\mathbf{q}) \mu(\mathbf{k})\right|
$$

内積をとることは二つの状態ベクトルのなす角の余弦$\cos \theta$をとることに相当し、$|...|$をとることで不定な位相の影響を除去し、振幅の影響のみを残す。$2 - 2 \cos \theta = 4 \sin^2\frac{\theta}{2}$より、$D = 2 \sin \frac{\theta}{2}$となり、これは球面上の二点間の直線距離である。二点が非常に近い場合、これは同時に球面上の二点間の「測地線」距離でもある。このことから、この$D(k,k')$の定義が確かに「距離」の意味を持つことがわかる。

上記の$D(k,k')$の定義を非常に近い二点$k$, $k'$に対して展開すると、得られる計量の式が先の定義と一致することも証明できる。もちろんこれは微小量近似の下でのみ成り立つ。

## Alternative Expression

実際の数値計算では、コンピュータの対角化で得られる固有状態ベクトルの位相には固定された関係がない。このとき$|\partial_\mu \phi \rangle$の計算に問題が生じる可能性がある。そこで、以下の等価な式を導入し、計算における状態ベクトルの偏微分をハミルトニアンの偏微分に変換する。$H(k)$の定義は一般に連続関数であるため、解析計算も数値的な差分も可能となり、FS metric、Berry Curvature、そしてQuantum Geometric Tensor全体といった物理量の数値シミュレーション結果の正確性を保証できる。

以下の等式を利用する。ここで状態ベクトルはすべて$H$の固有状態である：

$$
\left\langle\phi_n \mid \partial_\mu \phi_0\right\rangle=\frac{\left\langle\phi_n\left|\partial_\mu H\right| \phi_0\right\rangle}{E_0-E_n} \quad \text { if } n \neq 0
$$

$$
\left\langle\phi_0\left|\partial_\mu H\right| \phi_0\right\rangle=\partial_\mu E_0
$$

したがって：

$$
Q_{\mu \nu}=\left\langle\partial_\mu \phi_0\left|\left(\mathbf{1}-\left|\phi_0\right\rangle\left\langle\phi_0\right|\right)\right| \partial_\nu \phi_0\right\rangle
$$

$$
=\sum_{n \neq 0}\left\langle\partial_\mu \phi_0 \mid \phi_n\right\rangle\left\langle\phi_n \mid \partial_\nu \phi_0\right\rangle
$$

$$
=\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

ここでBerry Curvatureの式は：

$$
F_{\mu \nu}=\partial_{[\mu} \beta_{\nu]}=i\left\langle\partial_{[\mu} \phi_0 \mid \partial_{\nu]} \phi_0\right\rangle=i\left(Q_{\mu \nu}-Q_{\nu \mu}\right)=-2 \operatorname{Im} Q_{\mu \nu}=-2 \sigma_{\mu \nu}
$$

これはBerry CurvatureとQuantum Geometric Tensorの虚部の間に依然として係数2の差があることを示している：

$$
Q_{\mu \nu}=g_{\mu \nu}-\frac{i}{2} F_{\mu \nu}
$$

上記の定義はすべて非縮退の場合に成立する。$n$重縮退の場合、上記のすべてのスカラー量は$n$次元行列になり、FS metric、Berry Curvature、そしてQuantum Geometric Tensor全体といった物理量も非可換（non-Abelian）量となる。

$$
{\left[Q_{\mu \nu}\right]_{i j}=\sum_{n \neq 0, k(n)} \frac{\left\langle\phi_{0 i}\left|\partial_\mu H\right| \phi_{n k}\right\rangle\left\langle\phi_{n k}\left|\partial_\nu H\right| \phi_{0 j}\right\rangle}{\left(E_0-E_n\right)^2}}
$$

![Image](https://pic4.zhimg.com/80/v2-d327ed01b77d2a2414e5ff2cd596f371.png)

## E.g. Spin-1/2 Systems

最も単純な二準位系のQuantum Geometric Tensorを実際に計算してみよう。ここで選ぶ系は磁場中のSpin-1/2系であり、パラメータは磁場の方位角$\theta \in [0,\pi]$, $\phi \in [0,2\pi]$である。ハミルトニアンは：

$$
H=\mu \vec{\sigma} \cdot \vec{B} = \mu |B| \left(\begin{array}{cc}
\cos \theta & \sin\theta e^{-i\phi} \\
\sin\theta e^{i\phi} & - \cos \theta
\end{array}\right) = \mu |B| \vec{\sigma} \cdot \hat{B}
$$

二準位系の固有値、固有状態は容易に得られる：

$$ E_{\pm} = \pm \mu |B| $$

$$
|+\rangle =\left(
e^{-i \phi / 2} \cos \frac{\theta}{2}, e^{i \phi / 2} \sin \frac{\theta}{2}
\right)^T
$$

$$
|-\rangle=\left(-e^{-i \phi / 2} \sin \frac{\theta}{2}, e^{i \phi / 2} \cos \frac{\theta}{2}\right)^T
$$

先に述べた公式を用いる：

$$
Q_{\mu \nu} =\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

これより二準位系に対して：

$$
Q^{(\pm)}_{\mu \nu} =\frac{\left\langle \pm \left|\partial_\mu H\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu H\right| \pm\right\rangle}{\left(E_\pm-E_\mp\right)^2}
$$

分母分子で$\mu |B|$を消去すると：

$$ Q^{(\pm)}_{\mu \nu} = \frac{1}{4} \left\langle \pm \left|\partial_\mu (\vec{\sigma} \cdot \hat{B})\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu(\vec{\sigma} \cdot \hat{B})\right| \pm\right\rangle $$

ここで$\mu,\,\nu = \theta,\,\phi$である。

さらに：

$$ \partial_\theta (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
-\sin \theta & \cos \theta e^{-i\phi} \\
\cos \theta e^{i\phi} &  \sin \theta
\end{array}\right) $$

$$ \partial_\phi (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
0 & -i \sin \theta e^{-i\phi} \\
i \sin \theta e^{i\phi} &  0
\end{array}\right) $$

これらを直接代入してひたすら計算すると、次を得る：

$$
g^{(\pm)}_{\mu \nu} = \frac{1}{4} \left(\begin{array}{cc}
1 & 0 \\
0 & \sin ^2 \theta
\end{array}\right)
$$

$$
F^{(\pm)}_{\mu \nu}=\pm \frac{1}{2}\left(\begin{array}{cc}
0 & - \sin \theta \\
 \sin \theta & 0
\end{array}\right)
$$

**計算の際、左ブラベクトルは複素共役をとることを忘れずに！**

ここで得られた計量は半径$1/2$の球面上の自然計量に他ならない。これは状態間の距離がBloch球上の「測地線」弧長に相当することを示している。

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
