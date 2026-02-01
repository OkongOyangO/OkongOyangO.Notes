---
title: "🫨最大局在化ワニエ関数と量子幾何"
date: 2023-05-13T10:00:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Quantum Geometry", "Wannier Function", "Berry Phase"]
categories: ["Physics Notes"]
---

本ノートは、最大局在化ワニエ関数（Maximally Localized Wannier Function）のゲージ選択問題について簡単に説明し、量子幾何（Quantum Geometry）がその局在度をどのように制限するかを議論する。

<!--more-->

## Gauge Variance of Wannier Function

Blochの定理を振り返る：

$$
\hat{H}\left|\psi_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\psi_{n \mathbf{k}}\right\rangle
$$

Blochハミルトニアンに対して：

$$
\hat{H}(\mathbf{k}) = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} \hat{H} e^{-i \mathbf{k} \cdot \hat{\mathbf{r}}}
$$

$$
| \psi_{n \mathbf{k}} \rangle = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} | u_{n \mathbf{k}} \rangle
$$

$$
\hat{H}(\mathbf{k}) | u_{n \mathbf{k}} \rangle = \epsilon_n(\mathbf{k}) \left|u_{n \mathbf{k}}\right\rangle
$$

計算の便宜上、局在的な性質を持つと思われるワニエ波動関数を基底として、系の固有状態を解くことがよくある。

ワニエ関数$|\mathbf{R} n\rangle$とBloch波動関数$\left|\psi_{n \mathbf{k}}\right\rangle$の間の変換関係：

$$
\left|\psi_{n \mathbf{k}}\right\rangle=\sum_{\mathbf{R}} e^{i \mathbf{k} \cdot \mathbf{R}}|\mathbf{R} n\rangle \Leftrightarrow |\mathbf{R} n\rangle=\frac{1}{N} \sum_{\mathbf{k}} e^{-i \mathbf{k} \cdot \mathbf{R}}\left|\psi_{n \mathbf{k}}\right\rangle
$$

Bloch波動関数$\left|\psi_{n \mathbf{k}}\right\rangle$が実空間で広がっているのに対し、ワニエ関数$|\mathbf{R} n\rangle$は$\mathbf{R}$付近に局在していることは容易に想像できる。

これらのワニエ波動関数は系の固有状態ではなく、Bloch波動関数の実空間で局在するある種の線形結合に過ぎず、エネルギーバンドのゲージ選択にも関係している。もしBloch波動関数に$\mathbf{k}$に依存する位相（ゲージ）を加えても、依然として固有状態である。

$$
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|\psi_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{\psi}_{n \mathbf{k}}\right\rangle
$$

$$
\left|\tilde{u}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|u_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle
$$

ゲージ$e^{i \varphi_n(\mathbf{k})}$の選択の任意性により、ワニエ波動関数の局在性も影響を受けることは想像に難くない。そのため、ワニエ波動関数を最大局在化させるゲージを見つける動機（motivation）が生まれる。

## Vanderbilt's Spread Function

一般的な固体物理学の教科書では、ゲージを調整してワニエ関数を最大局在化させる方法については省略されることが多い。実際、これはバンド理論が提案されてから数十年もの間、完全には解決されていなかった。関連する内容は、Vanderbiltの1997年のPRB論文「Maximally localized generalized Wannier functions for composite energy bands」：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847

および2012年のRMP論文「Maximally localized Wannier functions: Theory and applications」：

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419

を参照されたい。

注目すべきは、最大局在化ワニエ関数（Maximally Localized Wannier Function）を数値的に求めることは、第一原理計算の効率を向上させるために非常に重要であり、関連する理論は`wannier90`などのプログラムで重要な応用を持っ​​ていることである。

Vanderbiltの理論を簡単に紹介する。まず、ワニエ関数の局在度を定義する必要がある。とりあえず実空間分布の標準偏差、いわゆるSpread Functionalで定義することにする：

$$
\Omega=\left[\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\langle\mathbf{0} n|\mathbf{r}| \mathbf{0} n\rangle^2\right]=\left[\left\langle r^2\right\rangle_n-\overline{\mathbf{r}}_n^2\right]
$$

このSpread Functionalはゲージ選択に関係するが、ゲージ不変な部分$\Omega_{\mathrm{I}}$とゲージに依存する部分$\tilde{\Omega}$の2つの部分に分けることができる：

$$
\Omega=\Omega_{\mathrm{I}}+\tilde{\Omega}
$$

ここで、

$$
\Omega_{\mathrm{I}}=\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\sum_{\mathbf{R},m}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

$$
\tilde{\Omega}=\sum_{\mathbf{R} m \neq 0 n}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

実際、ゲージに依存する部分$\tilde{\Omega}$は非負の値であるため、常に以下が成り立つ：

$$
\Omega \geq \Omega_{\mathrm{I}}
$$

素朴に（Naively）、我々はゲージを調整して$\tilde{\Omega}$をできるだけ0に近づけたいと考える。一方、Spread Functionalのゲージ不変な部分$\Omega_{\mathrm{I}}$は、ワニエ関数の局在度の下限を与える。

なぜ$\Omega_{\mathrm{I}}$がゲージ不変なのか？その形式を書き換えてみる：

$$
\Omega_{\mathrm{I}} =\sum_{\alpha}\left\langle 0 n\left|r_\alpha Q r_\alpha\right| 0 n\right\rangle=\sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right]
$$

ここで、$P$は考察しているエネルギーバンドへの射影演算子である：

$$
P =\frac{1}{N} \sum_{\mathbf{k}}\left|\psi_{n \mathbf{k}}\right\rangle\langle\psi_{n \mathbf{k}}|=\sum_{\mathbf{R}}| \mathbf{R} n\rangle\langle\mathbf{R} n|
$$

ketとbraがちょうどゲージを打ち消すため、$P$および$Q=1-P$は明らかにゲージ不変である（エネルギーバンド射影演算子は明らかにゲージ選択に依存しない）。

## Special Case in 1D

1次元系の場合、確かに以下のようにすることができる：

$$
\Omega = \Omega_{\mathrm{I}}
$$

最大局在化ワニエ関数は、座標演算子をそのバンドに射影した後の固有状態、すなわち$P\hat{x}P$の固有状態であるべきことが証明できる。

$$
\langle R n|x| 0 n\rangle=\langle R n|PxP| 0 n\rangle=\bar{x}_{0 n} \delta_{R, 0}
$$

ここで、$\bar{x}_{0 n} = \langle 0 n|x| 0 n\rangle$はワニエ関数の中心位置であり、$P$はバンド$n$への射影演算子である。最初の等式が成り立つ理由は、$| 0 n\rangle$、$| R n\rangle$もバンド$n$上の固有状態の重ね合わせであるため、自然に以下が成り立つからである：

$$
P| R n\rangle = | R n\rangle
$$

対応する結論は高次元の場合にも拡張できる。3次元を例にとると、$\Omega = \Omega_{\mathrm{I}}$を要求する場合、最大局在化ワニエ関数は$P\hat{x}P$、$P\hat{y}P$、$P\hat{z}P$の同時固有状態である必要がある。

しかし、これは一般には不可能である。あるバンドの完全基底としての最大局在化ワニエ関数が、$P\hat{x}P$、$P\hat{y}P$、$P\hat{z}P$の同時固有状態でもあるためには、そのバンドに射影されたこれらの座標演算子が互いに交換可能（可換）でなければならない。射影前はこれは容易に成り立つが、射影後は必ずしもそうではない。

言い換えれば、もし$P\hat{x}P$、$P\hat{y}P$、$P\hat{z}P$などの射影座標演算子が非可換であれば、Spread Functionalを0まで最小化することはできず、$\Omega_{min} = \Omega_{\mathrm{I}}$となることもあり得ない。しかし、我々は常にゲージ不変量である$\Omega_{\mathrm{I}}$をワニエ関数の局在度の下限とすることができる。

1次元系のワニエ関数は解くのが簡単（$P\hat{x}P$の固有状態を求める）であるため、1次元方向の電子の波束運動を解析するのに非常に有効である。1次元問題でなくとも、常にpartial wannier function、すなわち1つの方向に対してのみフーリエ変換を行ったワニエ関数を用いることができる：

$$
|x,k_y, n\rangle=\frac{1}{N_x} \sum_{k_x} e^{-i k_x x}\left|\psi_{n,k_x,k_y}\right\rangle
$$

この時、この一方向に関してのみ、最大局在化（Partial）ワニエ関数の広がり（Spread Functional）は最小値$\Omega_{min} = \Omega_{\mathrm{I}}$に達することができ、これは一方向の電子分極問題を解析するのに用いることができる。

## OBC v.s. PBC

特筆すべきは、上記の状況は開境界条件（Open Boundary Condition, OBC）の下でのみ成り立つということである。周期境界条件（Periodic Boundary Condition, PBC）では座標演算子は適切に定義されておらず、実際、座標の定義は多価である：

$$
x = x + mL, m \in \mathbb{Z}
$$

PBCでは、ユニタリ演算子：$z = e^{i \frac{2\pi}{L} \hat{x}}$を用いて座標を定義する。現代の電気分極理論やトポロジカルバンド理論におけるTopological Charge Pump理論はこの基礎の上に構築されているが、それはまた別の話である。

本ノートでは、物理的な意味を議論するために、座標演算子は良定義（well-defined）であると一律に見なすことにする。PBCの下での厳密な議論はまたの機会に譲る。

## Relation to Quantum Geometry

実際、ワニエ関数の局在度は系の量子幾何（Quantum Geometry）とも関連している。量子幾何については、私の過去のノートを掘り起こしてほしい：

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

なぜか？まず、ワニエ関数の局在度を記述するSpread Functionalの形式を考察する：

$$
\Omega \sim \langle r_\mu r_\nu \rangle
$$

これはおおよそ座標演算子の相関関数であり、運動量表示では座標演算子は運動量の偏微分として表すことができる：

$$
r_\mu \sim \partial_{k_\mu}
$$

Quantum Geometric Tensorの定義を思い出すと、ちょうど運動量の2階偏微分が含まれている：

$$
Q_{\mu\nu} \sim \langle \partial_{k_\mu} \partial_{k_\nu} \rangle
$$

したがって、両者の関連を考えることができる。

さらに進んで、ゲージ不変性の問題を考える。電磁場のゲージ不変性は、異なるゲージの選択が場の強さに影響を与えないことに現れる。同様に、トポロジカルバンド理論において、Bloch波動関数のゲージ選択はBerry Curvatureに影響を与えないことを我々は知っている（だからBerry Curvatureは運動量空間における「磁場」のようなものであると言う）。Berry Curvatureは実際には量子幾何（Quantum Geometry）の反対称成分であり、実際、量子幾何もまた系に固有のゲージ不変な性質である。

したがって、量子幾何とワニエ関数の局在度をより合理的に比較するために、Spread Functional内のゲージ不変部分$\Omega_{\mathrm{I}}$と$Q_{\mu\nu}$の関係を比較する。

以下を導くことは難しくない：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right] \\
& = \sum_\alpha \sum_k \langle \psi_{nk} | r_\alpha Q r_\alpha | \psi_{nk} \rangle \\
& = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle
\end{aligned}
$$

ここで、

$$
\begin{aligned}
\langle \psi_{nk_1} | r_a | \psi_{mk_2} \rangle & \equiv \langle k_1, n | r_\alpha | k_2, m \rangle \\
& = \langle k_1,n |  r_a e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}}) |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle ) + i \langle u_{k_1}^n | e^{- i k_1 \cdot \hat{r}} e^{ i k_2 \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle \\
& = -i \langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) + i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle
\end{aligned}
$$

ここで、

$$
\langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) \simeq \langle k_1,n | \left[ |k_2+\delta k_{2a}, m \rangle - |k_2-\delta k_{2a}, m \rangle \right]/2\delta k_{2a}
$$

であり、$|k_2 \pm \delta k_{2a}, m \rangle$、$|k_1, 1 \rangle$はすべて全ハミルトニアン$\hat{H}$の固有状態であるため、波動関数は直交する。しかし、周期Bloch波動関数は必ずしもそうではない。なぜなら、異なるkは異なるBlochハミルトニアンの固有状態に属し、必ずしも直交しないからである。

$I_{nm}(k_1,k_2) \equiv i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle$を定義し、座標表示で計算すると以下のようになる。ここで、周期Bloch波動関数$u_{k}^n (r)$の周期性を用いた：

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

偏微分は差分として見ることができる：

$$\partial_{k_{2a}} u_{k_2}^\alpha (r) \simeq [u_{k_2 + \delta k_{2a}}^\alpha (r) - u_{k_2 - \delta k_{2a}}^\alpha (r)]/\delta k_{2a}$$

$u_{k_2 + \delta k_{2a}}^\alpha (r)$と$u_{k_2 - \delta k_{2a}}^\alpha (r)$はどちらも周期関数（整数個の基本単位セルの移動に対して不変）であるため、$\partial_{k_{2a}} u_{k_2}^\alpha (r)$も周期関数である：

$$ \partial_{k_{2a}} u_{k_2}^\alpha (r) = \partial_{k_{2a}} u_{k_2}^\alpha (r + R) $$

$I_{nm}(k_1,k_2)= e^{i(k_2 - k_1) \cdot R} I_{nm}(k_1,k_2)$であり、かつ$k_1,\,k_2 \in 1BZ$であるため、$k_1 = k_2$のとき、かつそのときに限り$I(k_1, k_2)\neq 0$となる。したがって、$k_1 = k_2$、すなわち$k = k'$の部分のみを計算すればよい：

$$
\begin{aligned}
I_{nm}(k_1,k_2) & = \delta_{k_1,k_2} I_{nm}(k_1,k_1) \\
& = \delta_{k_1,k_2} \ i \int d^2 r \ u_{k_1}^n (r)  \partial_{k_{1a}} u_{k_1}^m (r) \\
& = \delta_{k_1,k_2} \ i \langle u_{k_1}^n | \partial_{k_{1a}} u_{k_1}^m \rangle 
\end{aligned}
$$

ゆえに、

$$
\langle \psi_{nk} | r_a | \psi_{mk'} \rangle = \delta_{k,k'} \ i \langle u_{k}^n | \partial_{k_{1a}} u_{k'}^m \rangle
$$

したがって、ワニエ関数のSpread Functionalのゲージ不変部分は次のように書ける：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle\\
& = \sum_\alpha \sum_k \sum_{m \neq n} \langle \partial_{k_{\alpha}} u_{k}^n | u_{k}^m \rangle \langle  u_{k}^m | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle
\end{aligned}
$$

和の部分がまさにバンド$n$上で定義されたQuantum Geometric Tensorの対角部分であることに注意されたい。さらに次のように書くこともできる：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \sum_{\alpha=1}^{d} \eta_{\alpha \alpha} (k) \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \operatorname{tr} g(k)
\end{aligned}
$$

Quantum Geometric Tensorはエルミート行列であるため、実対称のFubini-Study計量部分と、純虚反対称のBerry Curvature部分に分けることができる：

$$
\eta_{\mu\nu}(k) = g_{\mu\nu}(k) + i \frac{\epsilon_{\mu\nu}}{2}\mathcal{B} (k)
$$

明らかに、最後の等式ではエルミート行列の対角成分が実数であるという性質を用いており、Spread Functionalも明らかに実数であるべきである。

ここで$\operatorname{tr}$は次元に対するトレース$\sum_{\alpha=1}^{d}$であり、以前のものは全kで張られるヒルベルト空間に対するトレースであった。

こうしてみると、ブリルアンゾーンにおける量子幾何のトレースの積分は、実際にはワニエ関数の局在化の程度に下限を与えていることになる。

$$
\Omega \geq \Omega_I \propto \int_{BZ} d^dk \operatorname{tr} g(k)
$$

2次元系の場合、さらに不等式がある：

$$ \operatorname{tr}g^\alpha (k) \geq |\mathcal{B} (k)| $$

そして、2次元ブリルアンゾーンにおけるBerry Curvatureの積分はChern Numberであるため、以下のようになる：

$$
\Omega \geq \Omega_I = \frac{V}{(2\pi)^d} \int_{BZ} d^dk \operatorname{tr} g(k) \geq \frac{V}{2\pi} |C|
$$

Chern Insulatorの場合、1つのバンド（ただし2つなら可能であるため、目にするすべてのChern Insulator Tight-Binding Modelは少なくとも2バンドモデルであり、total Chern number = 0である）はWannierizeできず、せいぜい一方向にlocalizeすることしかできないことが知られているが、この不等式は、Chern numberがゼロでないChern Insulatorのワニエ波動関数は、trivial Insulatorよりもdelocalizeしていることを反映している。

同様に、すべての運動量空間の幾何量と実空間座標の期待値に関連する物理量を結びつけることができる。例えば、Berry Connectionは運動量の1階偏微分を含んでおり、これは座標演算子の期待値と関係していることを示しており、これが電子の分極（polarization）に対応している。

実際、現代の電子分極理論はBerry Connectionと同時代の産物であり、運動量空間のゲージ場を解明して初めて、一見単純な「分極」現象を真に理解できたと言える。

## Multiband Wannierization

強束縛モデルでは、シングルバンドに加えてマルチバンドモデルも計算できる。マルチバンドモデルの自由度を考慮することで、より大きなゲージ選択の自由度が得られるからである（ワニエ関数は異なるエネルギーバンドのBloch関数から構成できる）。

最も直感的な理解は、自由電子を考えることである。Bloch波動関数は平面波（運動量固有状態）であるが、無限の平面波（無限のエネルギーバンド）を用いることでデルタ関数（座標固有状態）を重ね合わせることができ、これ以上Localizeした基底はない（対応して、基本単位セル内の自由度も無限大である）。

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
