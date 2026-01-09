+++
date = '2026-01-08T21:54:37-05:00'
draft = false
math = true
ShowToc = true
TocOpen = false
title = '基底状態だけで導体と絶縁体をどう区別するか？🤔'
+++

本稿は、多体系の**導電性**と**基底状態の量子幾何学（Quantum Geometry）**との関連性を明らかにし、基底状態の波動関数の「局在性（Locality）」だけで導体と絶縁体を区別する方法について解説することを目的としています。

## Introduction

「基底状態を見るだけで導体と絶縁体を区別できる」——この主張は少し常識外れに聞こえるかもしれません。

1930年代のバンド理論は（ある程度）導体と絶縁体の違いを説明しました。相互作用のないレベルでは、導体と絶縁体は基底状態のエネルギーバンドが満たされているかどうかで区別できます。価電子帯が満たされ、伝導帯との間にバンドギャップ$E_g > 0$があれば絶縁体であり、そうでなければ導体です。ここではバンドギャップ$E_g$を使って区別しますが、$E_g$を定義するには励起状態のエネルギーを知る必要があり、必然的に励起状態の性質が関わってきます。

しかし、1949年に提案されたモット絶縁体（Mott Insulator、強い電子間相関に起因）や1958年のアンダーソン絶縁体（Anderson Insulator、強い無秩序に起因）は、導体と絶縁体を区別する上でのバンド理論の穴を指摘しました。つまり、多体系の絶縁メカニズムは価電子帯が満たされていることだけでなく、強い相関や無秩序も関係しているということです。同様に、バンドギャップがないことが導電性のメカニズムであるのと並んで、無秩序な金属合金の一部も導体になり得ます。逆に、無秩序な合金系では、バンドギャップがなくても絶縁体になる可能性があり、これこそがアンダーソン局在（Anderson Localization）であり、局在状態が電流を安定して輸送できないことに起因します。

さらに言えば、多体系には格子が全く存在しない可能性もあります。多体系の導電特性を判断するための、より**普遍的な指標（universal indicator）**が早急に求められています。

現象論的には、導体と絶縁体の違いは直流伝導率$\operatorname{Re}\sigma(\omega\rightarrow 0)$の違いにあります。なぜなら、一般的な絶縁体でも交流電流下では電気を通すことができるからです。あるいは電気分極現象によって区別することもできます。絶縁体では電子が束縛されており、原子の近くでしか動けないため、明らかな電気分極現象が生じます。一方、導体では電子は自由に動く傾向があり、外部電場によって自由に流れるため、明確に定義された電気分極はありません。

線形応答理論（Linear Response Theory）を用いて伝導率や分極率を計算することで、導体と絶縁体を区別することは常に可能ですが、これでもまだ励起状態の性質を考慮する必要があります。

しかし、Kohnは1964年の論文 "Theory of the insulating state" で、多体系の導電性は、多体配置空間（many-body configuration space）における基底状態の多体波動関数の「局在性」によって判断できると提案しました。

https://journals.aps.org/pr/abstract/10.1103/PhysRev.133.A171

20世紀末、Restaらは、この局在性の度合いが多体基底状態波動関数の**2次キュムラントモーメント（second cumulant moment）** $\langle r_\alpha r_\beta \rangle_c$（"c"は"cumulant"の意）によってより良く特徴付けられることに気づき、その本質が**量子幾何学（Quantum Geometry）**であることを明らかにしました。

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.82.370

そこでまず、波動関数の局在性の度合いをどのように定義するかを明確にしましょう。

## Wannierizability & Quantum Geometry

ここで明確にしておく必要がありますが、いわゆる「多体配置における基底状態多体波動関数の『局在性』」は、単一粒子波動関数の局在性とは異なりますが、定義上は類似点があります。さらに、単一粒子波動関数の観点から導出する方が簡単なので、まず単一粒子波動関数の局在性の定義を紹介し、その性質を議論した後、KohnやRestaらの論文にある多体系の場合へと一般化します。

固体バンド系を例にとると、絶縁体であれ導体であれ、その単一電子固有状態は広がったブロッホ波動関数です。しかし、フーリエ変換を通じて、これらの実空間で広がったブロッホ固有状態を実空間で局在した**ワニエ関数（Wannier Functions）**に変換することができます。

ワニエ関数$|\mathbf{R} n\rangle$とブロッホ波動関数$\left|\psi_{n \mathbf{k}}\right\rangle$の変換関係は以下の通りです：

$$
\begin{aligned}
\left|\psi_{n \mathbf{k}}\right\rangle=\sum_{\mathbf{R}} e^{i \mathbf{k} \cdot \mathbf{R}}|\mathbf{R} n\rangle \Leftrightarrow |\mathbf{R} n\rangle=\frac{1}{N} \sum_{\mathbf{k}} e^{-i \mathbf{k} \cdot \mathbf{R}}\left|\psi_{n \mathbf{k}}\right\rangle 
\end{aligned}
$$

ワニエ波動関数の局在性の度合いは、エネルギーバンドのゲージ選択に関係しています。もしブロッホ波動関数に$\mathbf{k}$に関連する位相（ゲージ）を加えても、それは固有状態のままです。

$$
\begin{aligned}
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|\psi_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{\psi}_{n \mathbf{k}}\right\rangle
\end{aligned}
$$

ワニエ関数の局在化を最大にするためにゲージをどのように調整するかについては、Vanderbiltの1997年のPRB論文 "Maximally localized generalized Wannier functions for composite energy bands" および2012年のRMP "Maximally localized Wannier functions: Theory and applications" を参照してください：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419

Vanderbiltはワニエ関数の局在性の度合いを、その空間分布の標準偏差、いわゆる**Spread Functional**（**Quadratic Spread**とも呼ばれる）を用いて定義しました：

$$
\begin{aligned}
\Omega=\left[\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\langle\mathbf{0} n|\mathbf{r}| \mathbf{0} n\rangle^2\right]=\left[\left\langle r^2\right\rangle_n-\overline{\mathbf{r}}_n^2\right] 
\end{aligned}
$$

このSpread Functionalはゲージ選択に関係しますが、ゲージ不変な部分$\Omega_{\mathrm{I}}$とゲージ依存部分$\tilde{\Omega}$に分けることができます：

$$
\begin{aligned}
\Omega=\Omega_{\mathrm{I}}+\tilde{\Omega}
\end{aligned}
$$

その中で、ゲージ不変部分$\Omega_{\mathrm{I}}$はワニエ関数の**2次キュムラントモーメント**とも呼ばれます：

$$
\begin{aligned}
\Omega_{\mathrm{I}}=\sum_{\alpha}\left\langle 0 n\left|r_\alpha Q r_\alpha\right| 0 n\right\rangle=\sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right] 
\end{aligned}
$$

$P$は考察対象のバンドへの射影演算子です：

$$
\begin{aligned}
P =\frac{1}{N} \sum_{\mathbf{k}}\left|\psi_{n \mathbf{k}}\right\rangle\langle\psi_{n \mathbf{k}}|=\sum_{\mathbf{R}}| \mathbf{R} n\rangle\langle\mathbf{R} n| 
\end{aligned}
$$

この部分は単一粒子バンドの**量子幾何学（Quantum Geometry）**に関連しています：

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle
\end{aligned}
$$

ゲージ依存部分$\tilde{\Omega}$は非負の値です：

$$
\begin{aligned}
\tilde{\Omega}=\sum_{\mathbf{R} m \neq 0 n}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
\end{aligned}
$$

したがって、常に以下が成り立ちます：

$$
\begin{aligned}
\Omega \geq \Omega_{\mathrm{I}}
\end{aligned}
$$

この部分の詳細な導出は、私のノートで見ることができます：

https://zhuanlan.zhihu.com/p/629079639

ワニエ関数のQuadratic Spreadのゲージ不変部分は、その局在性の下限を定義し、単一粒子バンドの量子幾何学と直接的な関係を確立していることがわかります。

言い換えれば、**量子幾何学は、システム（現在は単一粒子システム）の局在性の度合いをある程度反映することができます。**

これに触発されて、多体系の量子幾何学を定義し、そこに含まれる多体波動関数の「局在性」情報を調べ、この基底状態の性質——多体基底状態波動関数の「局在性」——がどのように多体系の導電性を決定するかを議論することができます。

## Many-Body Quantum Geometry

同様に、多体系の量子幾何学を定義しましょう。まず、最も一般的な多体ハミルトニアンを書き下します：

$$
\begin{aligned}
\hat{H}=\frac{1}{2 m_e} \sum_{i=1}^N\left|\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)\right|^2+\hat{V}(\\{\mathbf{r}_i\\}) 
\end{aligned}
$$

しかし、この時点ではシステムは必ずしも並進対称性を持っているわけではないため、元の単一粒子バンド理論の量子幾何学構築法をここに直接適用することはできず、単一電子の運動量をパラメータ空間として直接使用することはできません。

量子幾何学を構築できるパラメータ空間を見つけるために、多体ハミルトニアンに対してゲージ変換を行います：

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa}) \equiv e^{-i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}} \hat{H} e^{i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}}
\end{aligned}
$$

ここで、$\hat{\mathbf{r}} \equiv \sum_i \hat{\mathbf{r}}_i$ です。

すなわち、

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa})=\frac{1}{2 m_e} \sum_{i=1}^N\left|\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)+\hbar \boldsymbol{\kappa}\right|^2+\hat{V}(\\{(\mathbf{r}_i\\}) 
\end{aligned}
$$

このとき、異なるパラメータ$\boldsymbol{\kappa}$は異なる多体エネルギースペクトルと固有波動関数に対応します：

$$
\begin{aligned}
H(\boldsymbol{\kappa})|\Psi(\boldsymbol{\kappa})\rangle=E(\boldsymbol{\kappa})|\Psi(\boldsymbol{\kappa})\rangle 
\end{aligned}
$$

これは定数の磁気ベクトルポテンシャルを加えることに相当し、1次元リング内の磁束を使って理解することができます。このとき $\kappa \propto$ リング内の磁束 $\Phi$ です。

![Image](https://pic4.zhimg.com/80/v2-bf698d3fa3347511c74f9b760fb057a6.png)

多体系にとって最も重要なのは基底状態です。パラメータ空間$\boldsymbol{\kappa}$から基底状態波動関数$|\Psi_0(\boldsymbol{\kappa})\rangle$への写像を調べ、これを使って基底状態波動関数空間の**量子幾何テンソル（Quantum Geometric Tensor）**を構築します：

$$
\begin{aligned}
\eta_{\alpha \beta}(\boldsymbol{\kappa})=\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle 
\end{aligned}
$$

ここで、$\hat{Q}(\boldsymbol{\kappa})=\hat{1}-\hat{P}(\boldsymbol{\kappa})$であり、$\hat{P}(\boldsymbol{\kappa})$は基底状態波動関数空間の射影演算子です：

$$
\begin{aligned}
\hat{P}(\boldsymbol{\kappa})=\left|\Psi_0(\boldsymbol{\kappa})\right\rangle\left\langle\Psi_0(\boldsymbol{\kappa})\right|
\end{aligned}
$$

バンド幾何学と同様に、実部は対称テンソルであり、**Fubini-Study計量**と呼ばれます：

$$
\begin{aligned}
g_{\alpha \beta}(\boldsymbol{\kappa}) & =\operatorname{Re}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa}) \mid \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle \\
& -\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa}) \mid \Psi_0(\boldsymbol{\kappa})\right\rangle\left\langle\Psi_0(\boldsymbol{\kappa}) \mid \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle \\
& =\operatorname{Re}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle 
\end{aligned}
$$

虚部は反対称テンソルであり、**ベリー曲率（Berry Curvature）**です：

$$
\begin{aligned}
\Omega_{\alpha \beta}(\boldsymbol{\kappa})=-2 \operatorname{Im}\left\langle\partial_\alpha \Psi_0(\boldsymbol{\kappa})|\hat{Q}(\boldsymbol{\kappa})| \partial_\beta \Psi_0(\boldsymbol{\kappa})\right\rangle 
\end{aligned}
$$

単一粒子の場合と同様に、一次摂動論を用いて「状態和（sum of states）」の形で書くこともできます：

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

この状態和の公式は、ギャップがない場合や基底状態が縮退している場合（一次摂動論が破綻する場合）には破綻することに注意が必要ですが、これは量子幾何学の定義が破綻することを意味するわけではありません。多体系も魅力的な基底状態の縮退（Ground State Degeneracy）を示し、そこでは基底状態波動関数とその量子幾何学を高次元の非可換形式（非可換ベリー接続の一般化）に拡張できます。

紙面の都合上、ここでは**非縮退基底状態**の場合のみを議論します。興味のある読者は、分数量子ホール系などのシステムの非可換量子幾何学を一般化して計算してみてください。

## Quantum Geometry & Localization

単一粒子の局在化の度合いを記述する位置演算子の2次キュムラントモーメント、すなわちSpread Functionalのゲージ不変部分$\Omega_I$を多体系の場合に拡張し、多体波動関数の「局在性」を記述しましょう。

以下に注目します：

$$
\begin{aligned}
\hat{H}(\boldsymbol{\kappa}) \equiv e^{-i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}} \hat{H} e^{i \boldsymbol{\kappa} \cdot \hat{\mathbf{r}}}
\end{aligned}
$$

$\left|\Psi_0\right\rangle$が$\hat{H}$の非縮退基底状態であると仮定すると、$\hat{H}(\boldsymbol{\kappa})$の基底状態を簡単に書き下すことができます（ここではひとまず開境界条件を仮定します。周期的境界条件はより複雑になります）：

$$
\begin{aligned}
\left|\Psi_0(\boldsymbol{\kappa})\right\rangle=e^{-i \boldsymbol{\kappa} \cdot(\hat{\mathbf{r}}-\mathbf{d})}\left|\Psi_0\right\rangle 
\end{aligned}
$$

ここで、$\mathbf{d}=\left\langle\Psi_0|\hat{\mathbf{r}}| \Psi_0\right\rangle$です。この項は定数の位相にしか寄与しないため、影響はありません。

量子幾何学を求めるために微分します：

$$
\begin{aligned}
\left|\nabla_{\boldsymbol{\kappa}} \Psi_0\right\rangle=-i(\hat{\mathbf{r}}-\mathbf{d})\left|\Psi_0\right\rangle=-i \hat{Q}(0) \hat{\mathbf{r}}\left|\Psi_0\right\rangle 
\end{aligned}
$$

これより以下が得られます：

$$
\begin{aligned}
\eta_{\alpha \beta}(0) &=\left\langle\Psi_0\left|\hat{r}_\alpha \hat{Q}(0) \hat{r}_\beta\right| \Psi_0\right\rangle \\
&=\left\langle\Psi_0\left|\hat{r}_\alpha \hat{r}_\beta\right| \Psi_0\right\rangle-\left\langle\Psi_0\left|\hat{r}_\alpha\right| \Psi_0\right\rangle\left\langle\Psi_0\left|\hat{r}_\beta\right| \Psi_0\right\rangle
\end{aligned}
$$

ここで、$\hat{\mathbf{r}} \equiv \sum_i \hat{\mathbf{r}}_i$ です。これが基底状態波動関数の座標分布の分散、すなわち**2次キュムラントモーメント**に相当することに気づかないわけにはいきません。これは実空間における基底状態波動関数の電子分布の「局在性」を反映しています。

しかし、この量は示量性変数（体積のようなもの）であり、熱力学的極限$N\rightarrow\infty$では$N$に比例します。この「局在性」を異なるシステム間で比較するために、電子1個あたりで平均し、比較可能な示強性変数（圧力のようなもの）にします。もちろん、これは波動関数の正規化の定義を変更することによっても達成できます：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\eta_{\alpha \beta}(0) / N
\end{aligned}
$$

単一粒子のワニエ波動関数の局在化の度合いがすべての運動量$k$についての積分$\Omega_I \propto \int_{BZ}d^dk \operatorname{tr}g(k)$を必要とするのとは異なり、ここではパラメータ空間$\boldsymbol{\kappa} = 0$の情報、つまり元のシステムの基底状態の情報だけが必要であることがわかります。

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}= \frac{1}{N} \left(\left\langle\Psi_0\left|\hat{r}_\alpha \hat{r}_\beta\right| \Psi_0\right\rangle-\left\langle\Psi_0\left|\hat{r}_\alpha\right| \Psi_0\right\rangle\left\langle\Psi_0\left|\hat{r}_\beta\right| \Psi_0\right\rangle \right)
\end{aligned}
$$

後の導出の便宜上（伝導率の式とより良く比較するために）、「状態和」の形で書くこともできます：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}= \frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\partial_\alpha \hat{H}(0)\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\partial_\beta \hat{H}(0)\right| \Psi_0\right\rangle}{\left(E_0-E_n\right)^2} 
\end{aligned}
$$

ここで、

$$
\begin{aligned}
\nabla_\kappa \hat{H}(0) =\frac{\hbar}{m_e} \sum_{i=1}^N\left[\mathbf{p}_i+\frac{e}{c} \mathbf{A}\left(\mathbf{r}_i\right)\right] = \hbar \hat{\mathbf{v}}
\end{aligned}
$$

これは実質的に運動量（速度）演算子であるため、さらに次のように書き換えることができます：

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

しかし、心に留めておくべきは、**この2次キュムラントモーメントは純粋に基底状態波動関数の局在性の性質であり、励起状態とは無関係であるということです。**

まとめると、単一粒子の量子幾何学を多体基底状態波動関数空間に一般化し、多体基底状態波動関数空間の量子幾何学（全電子数Nで割ったもの）が実空間における多体基底状態波動関数分布の局在性を特徴付けることができ、これが励起状態とは無関係な基底状態の性質であることを発見しました。

**私たちの最終目標は、この純粋な基底状態の性質を用いて、一見すると区別に励起状態の性質が必要と思われる導体と絶縁体を区別することです。**

## Localization & Conductivity

### Linear Response Theory

線形応答理論を使って多体系の伝導率を素早く得ることができます。興味のある学生は、私の線形応答理論のノートをチェックしてください：

https://zhuanlan.zhihu.com/p/477550302

$$
\begin{aligned}
\sigma_{\alpha \beta}(\omega)=\frac{i e^2}{\hbar L^3} \lim_{\eta \rightarrow 0+} \sum_{n \neq 0}^{\prime} \frac{1}{\omega_{0 n}}& \left(\frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\omega-\omega_{0 n}+i \eta}\right. \\
& \left.+\frac{\left\langle\Psi_0\left|\hat{v}_\beta\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\alpha\right| \Psi_0\right\rangle}{\omega+\omega_{0 n}+i \eta}\right)
\end{aligned}
$$

この伝導率の実部は散逸項であり、虚部は揺らぎ項です。私たちは通常、コンダクタンスの散逸的な性質を調べるので、その実部$\sigma_{\alpha \beta}(\omega)$に注目します。

伝導率の実部$\sigma_{\alpha \beta}(\omega)$は対称部分と反対称部分に分けることができます（$\omega > 0$かつ$\omega_{0n} > 0$に注意）：

$$
\begin{aligned}
\operatorname{Re} \sigma_{\alpha \beta}^{(+)}(\omega)=\frac{\pi e^2}{\hbar L^3} \sum_{n \neq 0}^{\prime} \frac{\mathcal{R}_{n, \alpha \beta}}{\omega_{0 n}} \delta\left(\omega-\omega_{0 n}\right) 
\end{aligned}
$$
$$
\begin{aligned}
\operatorname{Re} \sigma_{\alpha \beta}^{(-)}(\omega)=\frac{2 e^2}{\hbar L^3} \sum_{n \neq 0}^{\prime} \frac{\mathcal{I}_{n, \alpha \beta}}{\omega_{0 n}^2-\omega^2} 
\end{aligned}
$$

ここで、

$$
\begin{aligned}
\mathcal{R}_{n, \alpha \beta}=\operatorname{Re}\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle 
\end{aligned}
$$
$$
\begin{aligned}
\mathcal{I}_{n, \alpha \beta}=\operatorname{Im}\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle 
\end{aligned}
$$

導出において、以下を使用しました：

$$
\begin{aligned}
\lim_{\eta \rightarrow 0+} \frac{1}{x + i\eta} = \mathcal{P}\frac{1}{x} - i \pi \delta(x)
\end{aligned}
$$

以前に得られた多体基底状態波動関数の局在性を記述する2次キュムラントモーメント$\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}$の状態和形式と比較します：

$$
\begin{aligned}
\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\left\langle\Psi_0\left|\hat{v}_\alpha\right| \Psi_n\right\rangle\left\langle\Psi_n\left|\hat{v}_\beta\right| \Psi_0\right\rangle}{\omega_{0 n}^2}
\end{aligned}
$$

以下を見つけるのは難しくありません：

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}=\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\mathcal{R}_{n, \alpha \beta}}{\omega_{0 n}^2} 
\end{aligned}
$$
$$
\begin{aligned}
\operatorname{Im}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}=\frac{1}{N} \sum_{n \neq 0}^{\prime} \frac{\mathcal{I}_{n, \alpha \beta}}{\omega_{0 n}^2} 
\end{aligned}
$$

さらに、**SWM公式**（I.Souza, T.Wilkens, R.M.Martin, 2000）を証明することができます：

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{\omega} \operatorname{Re} \sigma_{\alpha \beta}^{(+)}(\omega) 
\end{aligned}
$$
$$
\begin{aligned}
\operatorname{Im}\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{2 e^2 N} \operatorname{Re} \sigma_{\alpha \beta}^{(-)}(0) 
\end{aligned}
$$

### SWM Formula

現象論的に導体と絶縁体を定義する場合、**静的縦伝導率（static longitudinal conductivity）**、すなわち $\lim_{\omega \rightarrow 0}\sigma_{\alpha \alpha}(\omega)$ に注目します。

静的場 $\omega \rightarrow 0$ に注目するのは、絶縁体でも交流電流下では電気を通すことができるからです。また、縦伝導率に注目するのは、たとえ横伝導率（例：ホール伝導率）が非ゼロであっても、縦伝導率がゼロであれば、それを絶縁体と呼ぶからです（例：量子ホール絶縁体、チャーン絶縁体）。

$\omega \rightarrow 0$ での情報は $\left\langle r_\alpha r_\beta\right\rangle_{\mathrm{c}}$ に直接結びつけるのは容易ではありませんが、上記のSWM公式を通じて、$\omega \rightarrow 0$ での情報を間接的に調べることができます。

**SWM公式**の縦情報の成分の実部に注目します（指標$\alpha$が同じなので、$\operatorname{Re} \sigma_{\alpha \alpha} = \operatorname{Re} \sigma_{\alpha \alpha}^{(+)}$）：

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{\omega} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) 
\end{aligned}
$$

f-sum則を使って、積分が $\omega \rightarrow \infty$ で収束することを証明できます：

$$
\begin{aligned}
\int_0^{\infty} d \omega \operatorname{Re} \sigma_{\alpha \alpha}(\omega) = \frac{\pi e^2 N}{2 m_e L^3} 
\end{aligned}
$$

したがって、積分の収束（$\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} $が有限かどうか）は、$\omega \rightarrow 0$ での伝導率の情報に依存します。

そして、$\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$が有限であるかどうかは、多体系の局在性と直接関係しています。$\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$が有限であれば、多体基底状態は**「局在化している（Localized）」**と定義でき、発散すれば**「非局在化している（Delocalized）」**と定義できます。

上記の導出を通じて、多体基底状態波動関数の「局在性」を定量的に表現し、それをシステムの静的縦伝導率と結びつけることに成功しました。

**注意：これは基底状態の情報にのみ関係しています！**

## Metal or Insulator?

最後に、この記事の冒頭の質問に答えることができます：**基底状態を見るだけで、どのようにして導体と絶縁体を区別するのか？**

バンドギャップを持つシステムの場合、すべての励起エネルギーは $\hbar \omega_{0n} \geq E_g$ なので、伝導率の線形応答公式 $\operatorname{Re} \sigma_{\alpha \beta}^{(+)}(\omega) \simeq \sum \delta\left(\omega-\omega_{0 n}\right)$ から、$\omega \rightarrow 0$ のとき伝導率は明らかに0であり、絶縁体です。

したがって、$\operatorname{Re} \sigma_{\alpha \beta}^{(+)}(\omega) \simeq \sum \delta\left(\omega-\omega_{0 n}\right)$ の積分の下限を $E_g/\hbar > 0$ に変更できます：

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} =\frac{\hbar L^3}{\pi e^2 N} \int_{E_{\mathrm{g} /} \hbar}^{\infty} \frac{d \omega}{\omega} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) 
\end{aligned}
$$
$$
\begin{aligned}
<\frac{\hbar L^3}{\pi e^2 N} \int_0^{\infty} \frac{d \omega}{E_{\mathrm{g}}/\hbar} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) =\frac{\hbar^2}{2 m_e E_{\mathrm{g}}}
\end{aligned}
$$

これは、$\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}}$ が上限を持ち有限であることを示しており、これは先ほど定義した**局在化した多体基底状態**に対応します。

このようにして、多体基底状態の局在性によって、システムが絶縁体か導体かを完全に判断することができます：

$$
\begin{aligned}
\text{多体基底状態が「局在化」} \Leftrightarrow \text{システムは絶縁体}(E_g>0)
\end{aligned}
$$

逆に、静的縦伝導率 $\lim_{\omega \rightarrow 0} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) > 0$ を持つ導体（金属）の場合、上記の積分は $\omega \rightarrow 0$ において：

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} \simeq \frac{\hbar L^3 }{\pi e^2 N} \lim_{\omega \rightarrow 0} \operatorname{Re} \sigma_{\alpha \alpha}(\omega)\int_{0}^{\infty} \frac{d \omega}{\omega} 
\end{aligned}
$$

明らかに $\omega \rightarrow 0$ で発散するため、$\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} = \infty$ となります。

したがって、以下のようになります：

$$
\begin{aligned}
\text{多体基底状態が「非局在化」} \Leftrightarrow \text{システムは導体}
\end{aligned}
$$

もちろん、特殊なケースとしてギャップレスの場合 $E_g = 0$ があります。このとき、多体基底状態が「局在化」しているかどうかは、依然として静的縦伝導率 $\lim_{\omega \rightarrow 0} \operatorname{Re} \sigma_{\alpha \alpha}(\omega)$ の振る舞いに依存します。例えば、もし $\lim_{\omega \rightarrow 0} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) \propto \omega^{\alpha \geq 1}$ ならば、多体基底状態は依然として局在化しており絶縁体です。逆に、もし $\lim_{\omega \rightarrow 0} \operatorname{Re} \sigma_{\alpha \alpha}(\omega) \propto \omega^{\alpha < 1}$ ならば、多体基底状態は非局在化しており導体です。

その中で、強い無秩序を持つアンダーソン絶縁体は前者に属します。なぜなら、無秩序系の移動度端（mobility edge）の外側はエネルギースペクトル（システムをギャップレスにすることができる）ですが、移動度端の外側の電子状態はアンダーソン局在を起こしており、伝導に寄与しないため、全体としては依然として絶縁体だからです。一方、バンド金属や弱無秩序、弱相関の導体システムは後者に属します。

このようにして、任意の多体系（対称性、無秩序、強相関などの有無にかかわらず）について、多体基底状態波動関数の電子の局在性を見るだけで、すべての絶縁体と導体を区別することができます。

## Summary

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} < \infty \Leftrightarrow \text{多体基底状態が「局在化」} \Leftrightarrow \text{システムは絶縁体}
\end{aligned}
$$

$$
\begin{aligned}
\operatorname{Re}\left\langle r_\alpha r_\alpha\right\rangle_{\mathrm{c}} = \infty \Leftrightarrow \text{多体基底状態が「非局在化」} \Leftrightarrow \text{システムは導体}
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
