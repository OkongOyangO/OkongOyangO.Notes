---
title: "🧐分数量子ホール効果 (FQHE)、分数異常量子ホール効果 (FAQHE)、そして分数チャーン絶縁体 (FCI)"
date: 2022-10-17T22:30:00-05:00
draft: false
math: true
tags: ["Topology", "Quantum Hall Effect", "FCI"]
categories: ["Physics Notes"]
---

本ノートは約10,000文字あり、読者が分数量子ホール効果、分数異常量子ホール効果、および分数チャーン絶縁体に関する内容に入門することを目的としています。本文は私見に過ぎず、多くの不備があるかと思いますので、読者の皆様からのご指摘を歓迎いたします。以下、本文です。

<!--more-->

## Introduction to FQHE, FAQHE & FCI

量子ホール効果の実現には強磁場環境が必要ですが、Haldane模型およびチャーン絶縁体（Chern Insulator）の出現により、**外部磁場のない格子系**においても量子ホール効果が実現可能となりました。この現象は「量子異常ホール効果（Quantum Anomalous Hall Effect）」と呼ばれます。チャーン絶縁体においては、自明でないベリー曲率（Berry Curvature）の分布により、格子系が量子ホール効果に類似した非自明なトポロジカルな性質を持つようになります。さらに言えば、**ベリー曲率が磁場に取って代わった**と言えます（もっとも、ベリー曲率は逆空間で定義されるのに対し、磁場は実空間に現れるものですが）。これに端を発するチャーン絶縁体やその他のトポロジカル相に関する議論は、近年の凝縮系理論分野におけるホットトピックとなっています。

![Image](https://pic4.zhimg.com/80/v2-2449ec0b77d9fbfb23b817aa27e8b73a.png)

一方で、磁場強度が十分に大きく、電子がすべて最低ランダウ準位（Lowest Landau Level, LLL）に縮退している場合、特に電子1個が平均して整数個（または分数個）の量子磁束を占有している時に、分数量子ホール効果（FQHE）が現れます。量子ホール効果、量子異常ホール効果、あるいは一般的なトポロジカル絶縁体とは異なり、分数量子ホール効果はLLL内で縮退した**電子間の強い相互作用**の結果であり、それ以前の議論は基本的に相互作用のない（non-interacting）ギャップを持つフェルミ系に限られていました。

分数量子ホール系は、トポロジカルに関連した基底状態縮退度（Ground State Degeneracy, GSD）、分数励起、およびエニオン統計（Anyon statistics）を持ち、これらはトポロジカル量子計算などの分野への応用が期待されています。しかし、量子ホール効果よりもさらに強い磁場が必要であるという条件は、この効果を応用しようとする多くの人々を「**躊躇（または断念）**」させてきました。

英語の文法における様々な時制のように、「異常（Anomalous）」と「分数（Fractional）」を組み合わせて、新しい量子ホール効果、すなわち「**分数異常量子ホール効果**」（Fractional Anomalous Quantum Hall Effect, FAQHE）、**略して「FAQ」**（「ファッQ」）を作り出したいと考えるのは自然なことです。

![Image](https://pic4.zhimg.com/80/v2-6b707548a72e327c6613a30b75d0645b.png)

特に、この現象を格子系で実現したいという期待があります。チャーン絶縁体における量子異常ホール効果の実現と結びつけ、物理学者たちはチャーン絶縁体中のトポロジカルに非自明なチャーンバンド（Chern Band）に注目しました。そして、分数充填されたLLLを模倣し、チャーンバンド内で1/3、1/5、1/7...といった電子数の充填を行い、システムのハミルトニアンに電子-電子相関項（ハバード模型など）を加えることで、この分数充填されたチャーン絶縁体がFQH系に類似した現象（前述のGSD、分数励起、エニオン統計など）を示すかどうかを観測しようとしました。

分数充填、トポロジカルに非自明なHaldane模型、カゴメ格子などのシステムにおける数値シミュレーションにおいて、実際に熱力学的極限での有限の多体ギャップ（many-body gap）、非自明なGSD、分数励起などの現象が観測されました。物理学者たちはこの新奇なトポロジカル物質相を「**分数チャーン絶縁体**」（Fractional Chern Insulator, FCI）と名付けました。

## Physics in L.L.L.

（近）自由電子ガス系における分数量子ホール効果をチャーン絶縁体の格子系に「**シームレスに接続**」するために、まず最低ランダウ準位（L.L.L.）における物理を振り返ります。

磁場中の電子のハミルトニアン：

$$
\begin{aligned}
H=\frac{1}{2 m}\left( \hat{\mathbf{p}} + e \mathbf{A}(\hat{\mathbf{r}}) \right)^2 = \frac{\boldsymbol{\pi}^2}{2m}
\end{aligned}
$$

一定の外部磁場中の自由電子ガスに対しては、特定のゲージを選ばずにランダウ準位を計算することもできますし、ランダウゲージ（Landau Gauge）や対称ゲージ（Symmetric Gauge）の下で単電子波動関数を厳密に解くこともできます。

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

我々は速やかにランダウ準位の構造を得ることができましたが、ランダウ準位の縮退度などの情報はまだわかっていません。

### Landau Gauge

ランダウゲージはx方向の並進対称性を破りますが、$k_y$は良い量子数となり、対応する固有波動関数はx方向に局在します（x方向の調和振動子波動関数 + y方向の平面波）。

$$
\begin{aligned}
\nabla \times \mathbf{A}=B \hat{\mathbf{z}} \quad \mathbf{A}=x B \hat{\mathbf{y}}
\end{aligned}
$$

するとハミルトニアンは以下のようになります。

$$
\begin{aligned}
H=\frac{1}{2 m}\left(p_x^2+\left(p_y+e B x\right)^2\right)
\end{aligned}
$$

$p_y$が良い量子数であるため、波動関数は次のように書けます：

$$
\begin{aligned}
\psi_k(x, y)=e^{i k y} f_k(x)
\end{aligned}
$$

$p_y = \hbar k$としたハミルトニアンは、原点がシフトした調和振動子であることは容易にわかります：

$$
\begin{aligned}
H_k=\frac{1}{2 m} p_x^2+\frac{m \omega_B^2}{2}\left(x+k l_B^2\right)^2
\end{aligned}
$$

エネルギースペクトルと波動関数：

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

ランダウ準位の縮退度は次のように考えることができます。y方向が周期境界条件であれば、$k\in \frac{2\pi}{L_y}\mathbb{N}$となり、$x = -kl_B^2$付近に局在する調和振動子波動関数は$x \in [0,L_x]$を満たす必要があります。したがって、縮退度は以下のようになります：

$$
\begin{aligned}
\mathcal{N}=\frac{L_y}{2 \pi} \int_{-L_x / l_B^2}^0 \quad d k=\frac{L_x L_y}{2 \pi l_B^2}=\frac{e B A}{2 \pi \hbar}
\end{aligned}
$$

これはシステムの量子磁束数と等価です：

$$
\begin{aligned}
\mathcal{N}=\frac{A B}{\Phi_0} \quad \text { with } \quad \Phi_0=\frac{2 \pi \hbar}{e}
\end{aligned}
$$

後ほど、これが$\mathcal{C}=1$のチャーン絶縁体におけるワニエ関数（Wannier Function）$W(x,k_y)$と類推できること、それによってFQH状態とFCI状態の接続方法が与えられることを見ることになります。このあたりの内容は、2010年代のXL Qiの論文で詳しく紹介されています。

### Symmetric Gauge

対称ゲージ（Symmetric Gauge）：

$$
\begin{aligned}
\mathrm{A}=-\frac{1}{2} \mathrm{r} \times \mathbf{B}=-\frac{y B}{2} \hat{\mathbf{x}}+\frac{x B}{2} \hat{\mathbf{y}}
\end{aligned}
$$

同様に別の「運動量演算子」を解析し、その交換関係を利用して新しい「生成」・「消滅」演算子を構成することで、ランダウ準位の縮退が得られます。

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

x-y平面の波動関数を複素空間で記述することができます：

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

したがって：

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

$a$によって消滅させられるLLL波動関数は以下の形式を持つことが証明できます：

$$
\begin{aligned}
\psi_{L L L} \sim f(z) e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

$b$によって消滅させられるLLL内の最低縮退量子数$m=0$に対応する波動関数は：

$$
\begin{aligned}
\psi_{L L L, m=0} \sim  e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

対応して、他の縮退量子数$m$に対応するLLL波動関数は

$$
\begin{aligned}
\psi_{L L L, m} \sim\left(\frac{z}{l_B}\right)^m e^{-|z|^2 / 4 l_B^2}
\end{aligned}
$$

この関数はおよそ$\rho = \sqrt{x^2+ y^2} = \sqrt{2ml_B^2}$で極大になることがわかります。すなわち、波動関数は半径$\rho = \sqrt{2ml_B^2}$のリング上に局在します。

![Image](https://pic4.zhimg.com/80/v2-a641fbd050367403775101747437e57d.png)

ランダウ準位の縮退度も計算できます。半径Rの有限の円盤系の場合、$\rho_{max} = \sqrt{2m_{max}l_B^2} = \sqrt{2\mathcal{N}l_B^2}$となり、

$$
\begin{aligned}
\mathcal{N} = \frac{\pi R^2 B}{\Phi_0}
\end{aligned}
$$

これは別の角度からランダウ準位の縮退度を与えています。

対称ゲージ下の固有波動関数はある半径付近に局在し、角運動量$J$が良い量子数となります。その波動関数は独立変数$z = x + i y$とその共役$\bar{z}$の関数として書くことができ、その中でL.L.L.の波動関数は解析関数$f(z)$と指数因子$exp(-\bar{z}z/4l_B^2)$の積として書けます。

後ほど、L.L.L.中の波動関数の指数因子の前の関数の解析性、すなわち$f(z)$が$\bar{z}$に依存しないという性質が、その後L.L.L.へ射影された物理（つまり、考えるヒルベルト空間をL.L.L.上の波動関数に制限すること）を考える上で非常に重要であることがわかります。そして、L.L.L.への射影を考慮することは、FQHにおける中性励起（magneto-roton excitation）を解析する上で極めて重要です。これについては、80年代のGMP (Girvin, MacDonald, Platzman) の3人によるFQH系におけるmagneto-roton excitationに関する論文で詳しく紹介されています。ただし、GMPの3人の解析はFQH系の低エネルギー励起に対する一つのアンザッツ変分波動関数（ansatz variational wave function）を与えただけであり、変分法においては励起エネルギーの上限しか与えられません。

また後ほど、FQH系においてL.L.L.に射影された電子密度演算子が特殊なGMR代数（あるいは$W_\infty$代数と呼ばれる）を満たすことを見ることになります。これはチャーン絶縁体におけるFCI相（FCI phase）の出現とその安定性解析において重要な役割を果たします。チャーンバンドにおいてこの代数を実現し、それによって可能なFCI相を実現するためには、チャーンバンドがほぼ一定のベリー曲率とほぼ一定のフビニ・スタディ計量（Fubini-Study metric）を持つ必要があります。これはチャーンバンドの量子幾何学（Quantum Geometry）に対する制限に関わってきます。これについては、Rahul Royらによる2010年代のFCI、GMR代数、幾何学的安定性（Geometric Stability）に関する一連の論文で詳しく紹介されています。

## Laughlin Wave Function

Laughlinは天才的にも、L.L.L.が1/m占有状態にある多体波動関数の形式を提案（推測）しました。

まず、充填率（filling factor）$\nu = 1$の多体波動関数を考えると、それは単体波動関数の完全反対称化形式であるはずです。すなわち：

$$
\begin{aligned}
\Psi_m=\prod_{i < j}\left(z_{\imath}-z_{\jmath}\right)^m e^{\frac{1}{4 l_\beta^2} \sum\left|z_2\right|^2}
\end{aligned}
$$

この時、粒子iの次数は$m(N-1)$となり、単電子LLLの角運動量と半径の関係から、以下が得られます。

$$
\begin{aligned}
r_{\max }=\sqrt{2 \times m(N-1)} l_B
\end{aligned}
$$

これにより、ランダウ準位の縮退度は

$$
\begin{aligned}
\mathcal{N} = \pi r_{max}^2/\Phi_0 \approx mN
\end{aligned}
$$

となり、ランダウ準位の充填数は確かに$1/m$となります。

### Normalization & Plasma Analogy

FQH系において、プラズマ・アナロジー（Plasma analogy）という言葉をよく耳にします。これは実際には、Laughlin状態やその他の準粒子・準正孔励起状態の多体波動関数の規格化係数を計算する際に用いられるテクニックです。

類推によって、波動関数の絶対値二乗は、ある有限温度における古典的な2次元電子ガスの古典分配関数を解くことに変換されます。そして規格化係数の計算は、FQH系における準正孔励起の移動によって生じるベリー位相（Berry Phase）を解析する上で重要な役割を果たします。

未規格化のLaughlin状態の絶対値二乗は：

$$
\begin{aligned}
\left|\Psi_m\left(z_1 \cdots z_N\right)\right|^2=e^{-\beta V\left(z_1 \cdot z_N\right)}
\end{aligned}
$$

これは確率分布に比例します。

「擬温度」とエネルギーを次のように定義します：

$$
\begin{aligned}
\beta=\frac{2}{m} \quad V=-m^2 \sum_{i < j} \ln \left|z_i-z_{j}\right|+\frac{m}{4} \sum_i\left|z_i\right|^2 \frac{1}{l_B^2}
\end{aligned}
$$

エネルギー$V$は、密度$-1/l_B^2$の一様な2次元背景電荷上に、位置$\{z_i\}_{i=1}^N$に電荷量$m$の電荷を加えた2次元電子ガス系に対応していることがわかります。

### Review of 2D Plasma

一様な密度の2次元背景電荷とその電位のラプラス方程式$-\nabla^2\phi=\rho$（物理定数は省略）：

$$
\begin{aligned}
-\nabla^2\left(\frac{|z|^2}{4 l_B^2}\right)=-\frac{1}{l_B^2}
\end{aligned}
$$

2次元点電荷の電位分布：

$$
\begin{aligned}
-\nabla^2 \phi=2 \pi q \delta^2(\mathbf{r}) \Rightarrow \phi=-q \log \left(\frac{r}{l_B}\right)
\end{aligned}
$$

したがって、点電荷間の相互作用ポテンシャルエネルギーは：

$$
\begin{aligned}
V = -m^2 \sum_{i < j} \ln \left|z_i-z_{j}\right|
\end{aligned}
$$

一様背景電荷中の点電荷のポテンシャルエネルギーは：

$$
\begin{aligned}
V = \frac{m}{4} \sum_i\left|z_i\right|^2 \frac{1}{l_B^2}
\end{aligned}
$$

規格化係数の計算に戻ります：

$$
\begin{aligned}
C = \int \prod_i d^2z_i \left|\Psi_m\left(z_1 \cdots z_N\right)\right|^2  = \int \prod_i d^2z_i e^{-\beta V\left(z_1 \cdot z_N\right)}
\end{aligned}
$$

これは確率$e^{-\beta V\left(z_1 \cdot z_N\right)}$に従って点電荷のすべての可能な配置について積分することに相当するため、規格化係数$C$の計算は分配関数の計算に変換されます。

## Anyonic Excitation

エニオン（Anyon：任意子）の紹介については、文小剛（Xiao-Gang Wen）先生の多体物理学の教科書の第7章「量子ホール状態システム」の冒頭の節を参考にしてください。結論から言えば、2次元系はエニオン統計を持つことができますが、3次元系はボソンまたはフェルミオン統計しか持ちません。これはn個の同種粒子の配置空間のトポロジー的性質から考えることができます。

以下では、FQHにおける準粒子（quasi-particle）と準正孔（quasi-hole）励起について紹介します。

### Quasi-hole & Quasi-particle

準正孔の波動関数は：

$$
\begin{aligned}
\psi_{\text {hole }}(z ; \eta)=\prod_{i=1}^N\left(z_i-\eta\right) \prod_{k < l}\left(z_k-z_l\right)^m e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

これは、任意の電子の位置が$z = \eta$にある場合、振幅が0になり、ここの電子雲密度が0になることを意味するため、「準正孔励起」と呼ばれます。

さらに、そのような空孔がm個すべて同じ位置にある場合、波動関数は以下のようになります：

$$
\begin{aligned}
\psi_{\mathrm{m}-\mathrm{hole}}(z ; \eta)=\prod_{i=1}^N\left(z_i-\eta\right)^m \prod_{k < l}\left(z_k-z_l\right)^m e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

これは実質的に、電子の位置という力学量$z$をパラメータに置き換えたものであり、電子を1つ取り除くことに相当します。ここから、1つの空孔は$1/m$個の電子を取り除くことに相当するとナイーブに推測でき、その分数電荷とエニオン統計を推測することは難しくありません。

「準正孔」が得られたので、「準粒子」をどう加えるかを考えます。ナイーブには、系の中で$\prod_{i=1}^N\left(z_i-\eta\right)$を割り算して除きたいと考えますが、これは良い定義ではありません。

因子を除くことはある程度偏微分することと等価であると認識し、いくつかの定数項の修正を加えて、「準粒子」励起の波動関数を与えます：

$$
\begin{aligned}
\psi_{\text {particle }}(z, \eta)=\left[\prod_{i=1}^N\left(2 \frac{\partial}{\partial z_i}-\bar{\eta}\right) \prod_{k < l}\left(z_k-z_l\right)^m\right] e^{-\sum_{i=1}^n\left|z_i\right|^2 / 4 l_B^2}
\end{aligned}
$$

### Again, Normalization & Plasma Analogy

同様に、準正孔励起を例にとり、その多体波動関数の規格化係数を計算します。各項をすべて指数上に書き、温度因子$\beta = 2/m$を除いた後、「擬エネルギー」を得ます：

$$
\begin{aligned}
U\left(z_i;\xi\right)=-m^2 \sum_{i < j} \log \left(\frac{\left|z_i-z_j\right|}{l_B}\right)-m \sum_i \log \left(\frac{\left|z_i-\xi\right|}{l_B}\right)+\frac{m}{4 l_B^2} \sum_{i=1}^N\left|z_i\right|^2
\end{aligned}
$$

ここで、$-m \sum_i \log \left(\frac{\left|z_i-\eta\right|}{l_B}\right)$は「電荷量」$1$の「準正孔」と「電荷量」$m$の電荷との間の斥力相互作用ポテンシャルを表しています。しかし実際の系と比較すると、「準正孔」と「背景電荷」の相互作用の項が不足しています。

したがって、この項を補い、指数因子$e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}$の前に因子$e^{-\frac{1}{2 m l_B^2}|\xi|^2}$を補って、この項を加えた影響を相殺します。

再び規格化係数を計算します：

$$
\begin{aligned}
C = e^{-\frac{1}{2 m l_B^2}|\xi|^2} \int \prod_i d^2 z_i\left| \prod\left(\xi-z_i\right) \prod\left(z_i-z_j\right)^m e^{-\frac{1}{4 i_B^2}\left|z_i\right|^2}\right|^2 = e^{-\frac{1}{2 m l_B^2}|\xi|^2} \int \prod_i d^2 z_i e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}
\end{aligned}
$$

ここで、$\int \prod_i d^2 z_i e^{-\beta V\left(z_i,z_i^*;\xi, \xi^*\right)}$の部分は、「$\{z_i\}$にある電荷量$m$の電荷」+「$\xi$にある電荷量1の準正孔」+「一様な背景電荷」からなる2次元プラズマ系の古典分配関数です。

定性的な解析として、分配関数はすべての電荷配置について積分を行うため、パラメータとしての準正孔の位置$\xi$は実際には分配関数の結果に影響を与えないはずです。したがって、分配関数の部分は$\xi$に関して定数となり、以下のようになります。

$$
\begin{aligned}
C\left(\xi, \xi^*\right) = \text{const} \times e^{\frac{1}{2 l_B^2} \frac{1}{m}|\xi|^2}
\end{aligned}
$$

規格化係数の計算は、FQH系における準正孔励起の移動によって生じるベリー位相を解析する上で重要な役割を果たします。

### Berry Phase from a moving Quasi-hole

準正孔が移動する前後の位相変化は：

$$
\begin{aligned}
\left\langle\Psi^h\left[\xi(t+\Delta t), \xi^*(t+\Delta t)\right] \mid \Psi^h\left[\xi(t), \xi^*(t)\right]\right\rangle=e^{i \Delta t a \cdot x}
\end{aligned}
$$

これは以下と等価です：

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

次のように書けます：

$$
\begin{aligned}
\boldsymbol{a} \cdot d \boldsymbol{x}=a_{\xi} d \xi+a_{\xi^*} d \xi^*
\end{aligned}
$$

ここで、$a_{\xi},\,a_{\xi^*}$は準正孔の位置$\xi$のパラメータ空間におけるベリー接続（Berry Connection）であり、ここでは位相が実数であることを保証するために複素空間上で定義されており、上記の形式になります。

**上記の準正孔励起波動関数はすでに規格化されています。**

未規格化の準正孔励起波動関数の規格化係数：

$$
\begin{aligned}
\langle\Psi(\xi) \mid \Psi(\xi)\rangle=C\left(\xi, \xi^*\right)
\end{aligned}
$$

したがって：

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

ここで、先ほど長いプラズマ・アナロジーを用いて導出した規格化係数の形式が役に立ちます。定数項は$\ln C$の微分に寄与しないため、以下のようになります：

$$
\begin{aligned}
a_{\xi}=i \frac{1}{m} \frac{1}{4 l_B^2} \xi^*, \quad a_{\xi^*}=-i \frac{1}{m} \frac{1}{4 l_B^2} \xi
\end{aligned}
$$

これは次のように書けます：

$$
\begin{aligned}
a_{\xi}=-\frac{1}{m} q_e A^z, \quad a_{\xi^*}=-\frac{1}{m} q_e A^{z^*}
\end{aligned}
$$

ここで、複素平面上の磁気ベクトルポテンシャルは$A^z = \frac{1}{2}(A_x - iA_y)= \frac{1}{2} [( -\frac{By}{2} ) - i (\frac{Bx}{2})]$です。

ベリー位相はパラメータ空間における「準正孔」励起の位置$\xi$の運動に由来しますが、この効果を、電荷量$e^\star$の粒子が磁場中を運動する際に生じるAB位相として等価に理解することができます：

$$
\begin{aligned}
\oint d \boldsymbol{x} \cdot \boldsymbol{a}=\left(-\frac{q_c}{m}\right) \oint d \boldsymbol{x} \cdot \boldsymbol{A}
\end{aligned}
$$

したがって、「準正孔」は以下の電荷量を持つことに相当します：

$$
\begin{aligned}
e^{\star}=\frac{e}{m}
\end{aligned}
$$

同様に、2つの準正孔励起とその相互統計（具体的には、2つの正孔の位置を交換することによって生じる位相変化。$0$ならボソン、$\pi$ならフェルミオン、それ以外ならエニオン）を解析する場合も考えます。

### Anyonic Statistics

プラズマ・アナロジーを用いて規格化係数を計算し、それによってゲージポテンシャルを計算するためには、以前の「擬分配関数」の指数項に「準正孔」間の相互作用、および「準正孔」と「背景電荷」の相互作用を加える必要があります。

2つの「準正孔」励起の位置が十分に離れている限り、分配関数は両者の位置に依存しないと見なすことができ、2つの「準正孔」励起の位置$\xi_1,\,\xi_2$に対する規格化係数の依存性を得ることができます：

$$
\begin{aligned}
C\left(\xi_1, \xi_2\right) \propto e^{\frac{1}{22_B^2} \frac{1}{m}\left(\left|\xi_1\right|^2+\left|\xi_2\right|^2\right)}\left|\xi_1-\xi_2\right|^{-\frac{2}{m}}
\end{aligned}
$$

それらの統計を考慮するために、2番目の準正孔を固定し、最初の準正孔にその周りを1周させます。これは位置を2回交換したことに相当します。同時に、等価電荷$e^{\star}=\frac{e}{m}$が磁束の周りを1周することに対応するAB位相も考慮する必要があります。

実際、全体的な位相変化はベリー位相ですが、我々はあえて準正孔に電荷$e^{\star}=\frac{e}{m}$を付与してAB位相をシミュレートし、それらに全ベリー位相に対応する相互統計を付与することで、このベリー位相の生成に対してより物理的な説明を与えています。

![Image](https://pic4.zhimg.com/80/v2-ed0ea7e6cd8f318bbfe6e1b03cd5a7a3.png)

以下のように置きます：

$$
\begin{aligned}
\xi=\xi_1 \text { and } \xi_2=0
\end{aligned}
$$

ゲージポテンシャル：

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

ゲージポテンシャルを最初の空孔が2番目の空孔の周りを1周する軌跡上で線積分すると、全ベリー位相が得られます。我々はこれを分数電荷のAB位相と2つの空孔の相互統計を用いて記述します：

$$
\begin{aligned}
\text{AB Phase} + 2\theta = \frac{e}{m} B \times \text { 面積 }+\frac{2 \pi}{m}
\end{aligned}
$$

したがって、1回の交換による位相変化は：

$$
\begin{aligned}
\theta=\frac{\pi}{m}
\end{aligned}
$$

分数励起は確かにエニオン形式の相互統計を持つことがわかります。このようなエニオン統計はトポロジカル量子計算にとって重大な意義を持ちます。

## Collective Neutral Excitation & GMP Algebra

Girvin, MacDonald, Platzmanの3人は80年代にFQH系における集団中性励起（collective neutral excitation）を解析しました。この集団励起はFQH相を不安定化（destabilize）させる重要な要因であり、そこから導かれるGMP代数もFCI相の安定性と重要な関連がある可能性があります。

したがって、我々はまずFQH系における集団中性励起を解析し、次にその中のGMP代数がどのように多体ギャップ（Many-Body Gap）の解析に入ってくるかを解析します。

多体ギャップが具体的にどのように計算されるかについては詳しくは述べず、大まかな考え方を示すにとどめます。具体的な計算については、80年代のGirvin, MacDonald, Platzmanの原論文、またはGabriele Giuliani, Giovanni Vignaleの著書 "Quantum Theory of the Electron Liquid" のChapter 10を参照してください。

### Ansatz Excitation Wave Function

Girvin, MacDonald, Platzmanは$^4He$系の集団励起を類推し、励起状態に対する試行波動関数を与えました：

$$
\begin{aligned}
\left|\psi_{\vec{q}}\right\rangle=\hat{\bar{n}}_{\vec{q}}\left|\psi_0\right\rangle
\end{aligned}
$$

ここで、$\left|\psi_0\right\rangle$はLaughlin波動関数であり、L.L.L.内にあります。$\hat{n}_{\vec{q}}$は運動量空間の粒子数演算子です：

$$
\begin{aligned}
\hat{n}_{\vec{q}}=\sum_{n, n^{\prime}, k_y, k_y^{\prime}}\left\langle n^{\prime}, k_y^{\prime}\left|e^{-i \vec{q} \cdot \vec{r}}\right| n, k_y\right\rangle \hat{a}_{n^{\prime}, k_y^{\prime}}^{\dagger} \hat{a}_{n, k_y}
\end{aligned}
$$

一方、$\hat{\bar{n}}_{\vec{q}}$はL.L.L.に射影された演算子です：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=\sum_{k_y, k_y^{\prime}}\left\langle 0, k_y^{\prime}\left|e^{-i \vec{q} \cdot \vec{r}}\right| 0, k_y\right\rangle \hat{a}_{0, k_y^{\prime}}^{\dagger} \hat{a}_{0, k_y}
\end{aligned}
$$

演算子を作用させるとL.L.L.内の成分が高次のランダウ準位に写像される可能性があり、これは試行解のエネルギーを増加させるため、射影によってこの部分を取り除きます。

このような試行解は、低エネルギーであり、かつ基底状態波動関数の相関を保持しているため、真の励起状態と大きな違いはないはずです。したがって、変分法を用いて、試行解から励起エネルギーに近いエネルギー上限を得ることができます。

ちなみに、GMPの原論文では、この中性の集団励起に「Magneto-roton（磁気ロトン）」という名前が付けられており、これはボソン系における「roton（ロトン）」素励起とも関連しています。ただし、ボソン系の集団励起はギャップレス（無能隙）ですが、我々のFQH系ではギャップがあります。

![Image](https://pic4.zhimg.com/80/v2-4555edb96992cd8697108dde7bbef308.png)

### Projection to L.L.L.

しかし問題は、どうやってL.L.L.への射影を実現するかです。GMPの論文によれば、座標表示の演算子に対して以下の変換を行えばよいとされています：

$$
\begin{aligned}
z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}
\end{aligned}
$$

ナイーブに考えれば、座標表示の演算子は$z,\,z^*$の関数であるはずなので（常にテイラー展開可能）、$z,\,z^*$のL.L.L.への射影結果さえわかればよいことになります。L.L.L.上の波動関数は以下の形式を持ちます：

$$
\begin{aligned}
\psi(z)=f(z) e^{-\frac{|z|^2}{4 \ell^2}}
\end{aligned}
$$

$z$を作用させた後、$zf(z)$は依然として解析関数であるため、$z$がL.L.L.の波動関数に作用した後もL.L.L.上にとどまり、変換は不要です。

一方、$z^*$は異なります。なぜなら、$z^*f(z)$は波動関数の成分の一部をより高いランダウ準位へ移動させてしまうからです。

ランダウ準位の昇降演算子を思い出してください：

$$
\begin{aligned}
a^{\dagger}=-i \sqrt{2}\left(l_B \partial-\frac{\bar{z}}{4 l_B}\right)
\end{aligned}
$$

これは以下と等価です：

$$
\begin{aligned}
\bar{z}=4l_B^2 \partial-i \frac{4 l_Ba^{\dagger}}{\sqrt{2}}
\end{aligned}
$$

$z^*$はランダウ準位上昇演算子（より高いランダウ準位への写像）と$\partial/\partial z$の部分として書けることがわかります。$\partial f(z)/\partial z$は依然として解析関数であるため、射影後は$\partial/\partial z$の部分だけが残るはずです。ここでは以前の定義を用いました：

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

したがって、結果として$z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}$とは係数にいくつかの違いがありますが、$z^*$がL.L.L.への射影後に$\partial_z$になる理由は十分に理解できます。

さらに詳細な導出もあります：

L.L.L.上の波動関数を、指数因子の前の解析関数だけで完全に表現させます：

$$
\begin{aligned}
|\psi_f\rangle \equiv |f\rangle
\end{aligned}
$$

その内積（指数因子で重み付けされた内積）を定義します：

$$
\begin{aligned}
\langle g|f\rangle = \int g\left(z^*\right) f(z) e^{-\frac{|z|^2}{2 \ell^2}} d x d y
\end{aligned}
$$

これにより、L.L.L.波動関数空間（ヒルベルト部分空間）における$z^*$の行列要素$\langle g|z^*|f\rangle$は：

$$
\begin{aligned}
\int g\left(z^*\right) z^* f(z) e^{-\frac{|z|^2}{2 \ell^2}} d x d y
\end{aligned}
$$

$z^*$を、指数因子に対して$-2l^2 \partial_z$を作用させて得られたものとして書きます：

$$
\begin{aligned}
\int g\left(z^*\right)\left[ - 2 \ell^2 \frac{\partial}{\partial z} e^{-\frac{|z|^2}{2 \ell^2}}\right] f(z) d x d y
\end{aligned}
$$

**部分積分**を行い、$\partial_z g(z^*) = 0$を利用すると、

$$
\begin{aligned}
\int g\left(z^*\right)\left[2 \ell^2 \frac{\partial}{\partial z} f(z)\right] e^{-\frac{|z|^2}{2 \ell^2}} d x d y = \langle g |2 \ell^2 \frac{\partial}{\partial z}f\rangle
\end{aligned}
$$

ここでの$2 \ell^2 \frac{\partial}{\partial z}$は指数因子の前の解析関数$f(z)$にのみ作用することに注意してください。

もう一つ問題があります。もし$z$と$z^*$が同時にある場合、これらは積分内では自由に順序交換できますが、$2 \ell^2 \frac{\partial}{\partial z}$は$z$と自由に順序交換できません。

$zz^*$の射影結果を考えます：

$$
\begin{aligned}
\int g\left(z^*\right) z z^* f(z) e^{-\frac{-4}{2}} d x d y=\int g\left(z^*\right)\left[2 \ell^2 \frac{\partial}{\partial z} z f(z)\right] e^{-\frac{-3 x}{2 z}} d x d y
\end{aligned}
$$

部分積分の際、$\partial_z$は指数因子以外で$z$を含む解析部分をすべて含んでしまうことがわかります。これはすべての$\partial_z$を一番左に置き、すべての$z$演算子に対して「左から作用」させることに相当します。

したがって、射影を行う際は、まず演算子を$z,\,z^*$の関数として書き、その中の$z^*$の部分を左側に移動させ、すなわち正規順序（normal ordering）にし、その後$z_i^* \rightarrow 2 \ell^2 \frac{\partial}{\partial z_i}$という置き換えを行うことで、一般の演算子のL.L.L.への射影が実現されます。

これで射影を行うことができます：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=\sum_{j=1}^N \overline{e^{-i \vec{q}^{\cdot} \cdot \hat{r}_j}} =\sum_{j=1}^N \overline{e^{-i \mathrm{q} z_j^* / 2} e^{-i \mathrm{q}^* z_j / 2}} =\sum_{j=1}^N e^{-i q \ell^2 \frac{\partial}{\partial z_j}} e^{-i q^* z_j / 2}
\end{aligned}
$$

交換子を作ることができ、それによって別の等価な表現が得られます

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}}=e^{-q^2 \ell^2 / 2} \sum_{j=1}^N e^{-i q^* z_j / 2} e^{-i q \ell^2 \frac{\partial}{\partial z_j}}
\end{aligned}
$$

### Variational Method for Excitation Spectrum

演算子をL.L.L.へ射影する方法がわかったので、試行解のエネルギーを計算できます。

$$
\begin{aligned}
E_{\vec{q}}=\frac{\left\langle\psi_{\vec{q}}|\hat{H}| \psi_{\vec{q}}\right\rangle}{\left\langle\psi_{\vec{q}} \mid \psi_{\vec{q}}\right\rangle} = \frac{\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{H} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle}{\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle}
\end{aligned}
$$

交換操作により、分子を次のように変形できます：

$$
\begin{aligned}
E_0\left\langle\psi_0\left|\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}\right| \psi_0\right\rangle+\frac{1}{2}\left\langle\psi_0\left|\left[\hat{\bar{n}}_{\vec{q}}^{\dagger},\left[\hat{H}, \hat{\bar{n}}_{\vec{q}}\right]\right]\right| \psi_0\right\rangle
\end{aligned}
$$

これにより、基底状態エネルギー + ギャップの式として書くことができます。$\bar{f}/\bar{S}$がギャップです：

$$
\begin{aligned}
E_{\vec{q}}=E_0+\frac{\bar{f}(\vec{q})}{\bar{S}(\vec{q})}
\end{aligned}
$$

ここで、

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

以下、$\bar{f}$と$\bar{S}$の計算を行います。

### Entrance of GMP Algebra

まず$\bar{S}$を計算します。以下が証明できます：

$$
\begin{aligned}
\bar{S}(q)=S(q)-S_1(q)
\end{aligned}
$$

ここで、$S$は射影なしの基底状態構造因子です：

$$
\begin{aligned}
S(q) \equiv \frac{1}{N}\left\langle\psi_0\left|\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}\right| \psi_0\right\rangle
\end{aligned}
$$

$\mathcal{P}_{LLL}|\psi_0\rangle=|\psi_0\rangle$であるため、

$$
\begin{aligned}
S(q) = \frac{1}{N}\left\langle\psi_0\left|\mathcal{P}_{LLL}\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}\mathcal{P}_{LLL}\right| \psi_0\right\rangle = \frac{1}{N}\left\langle\psi_0\left|\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}\right| \psi_0\right\rangle
\end{aligned}
$$

一方、$S_1$は定数です：

$$
\begin{aligned}
S_1(\vec{q})=1-e^{-q^2 \ell^2 / 2}
\end{aligned}
$$

導出には$\partial$と$z$の交換関係を用い、それによって$\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}$と$\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}$を関連付けます：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}} \hat{\bar{n}}_{-\vec{q}} =\sum_j e^{-i q \ell^2 \frac{\partial}{\partial z_j}} e^{-i \frac{q^* z_j}{2}} \sum_k e^{+i q \ell^2 \frac{\partial}{\partial z_k}} e^{+i \frac{q^* z_k}{2}} =\sum_{j, k} e^{-i q \ell^2\left[\frac{\partial}{\partial z_j}-\frac{\partial}{\partial z_k}\right]} e^{-i q^*\left[\frac{z_j-z_k}{2}\right]} e^{-\frac{q^2 \ell^2}{2}\left[\frac{\partial}{\partial z_k}, z_j\right]}
\end{aligned}
$$

$j=k$と$j \neq k$の項を解析して、以下を得ます：

$$
\begin{aligned}
\hat{\bar{n}}_{\vec{q}} \hat{\bar{n}}_{-\vec{q}} = \overline{\hat{n}_{\vec{q}} \hat{n}_{-\vec{q}}}+N\left[e^{-\frac{q^2 \ell^2}{2}}-1\right] .
\end{aligned}
$$

これにより$\bar{S}(q)=S(q)-S_1(q)$が証明され、射影後の演算子の計算が射影前の計算に変換されました。

$\mathcal{P}_{LLL}|\psi_0\rangle=|\psi_0\rangle$、$\mathcal{P}_{LLL}^2 = \mathcal{P}_{LLL}$であるため、式中の$\hat{H}$を射影演算子に置き換えても元の式の結果が変わらないことが証明できます。

$$
\begin{aligned}
\bar{f}(q) \equiv \frac{1}{2 N}\left\langle\psi_0\left|\left[\hat{n}_{\vec{q}}^{\dagger},\left[\hat{\bar{H}}, \hat{\bar{n}}_{\vec{q}}\right]\right]\right| \psi_0\right\rangle
\end{aligned}
$$

ハミルトニアンは、単体エネルギーがすべてL.L.L.で縮退しているため、二体相互作用項のみを考慮すればよいです：

$$
\begin{aligned}
\bar{H}=\frac{1}{2 \mathcal{A}} \sum_{\vec{q}} v_q\left(\overline{\hat{n}_{\vec{q}}^{\dagger} \hat{n}_{\vec{q}}}-N\right) =\frac{1}{2 \mathcal{A}} \sum_{\vec{q}} v_q\left(\hat{\bar{n}}_{\vec{q}}^{\dagger} \hat{\bar{n}}_{\vec{q}}-N e^{-q^2 \ell^2 / 2}\right)
\end{aligned}
$$

このようにして、我々は$\bar{f}$の中の交換子の計算を、より基本的な要素、すなわち$\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]$交換子の解法に変換しました。

そして$\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]$交換子の計算は、**射影後の密度演算子の閉じたリー代数形式**を与えます。**これが有名なGMP代数（GMP Algebra）です**。

$$
\begin{aligned}
\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]=\left(e^{\frac{\mathrm{k}^* q^2}{2}}-e^{\frac{\mathrm{kq}^* \ell^2}{2}}\right) \hat{\bar{n}}_{\vec{k}+\vec{q}}
\end{aligned}
$$

これにより$\bar{f}$の計算を簡略化できます：

$$
\begin{aligned}
\bar{f}(q)=2 \frac{e^{-\frac{q^2 \ell^2}{2}}}{\mathcal{A}} \sum_{\vec{k}} \sin ^2\left(\frac{\left(\vec{q} \times \vec{k} \ell^2\right) \cdot \vec{e}_z}{2}\right) \bar{S}(k)\left[v_{|\vec{k}-\vec{q}|} e^{\vec{k} \cdot \vec{q} \ell^2} e^{-\frac{q^2 \ell^2}{2}}-v_k\right]
\end{aligned}
$$

$\bar{f},\,\bar{S}$および多体（many-body）のさらなる計算についてはここではこれ以上述べませんが、重要なのは、GMP代数がどのように多体ギャップの計算に入ってくるかを見たことです。ここでの変分法は上限しか与えませんが、数値計算の結果は、この近似がすでに非常に正確であることを示しています。

ここで、$q\rightarrow0$において、系は有限のギャップを持ち、ギャップの最小値はおよそ$q \sim 1/l_B$付近に現れ、依然として有限の多体ギャップとなります。そしてこの中性集団励起のギャップは、FQHおよび後に研究するFCI相の安定性にとって、重要な影響を与える可能性があります。

![Image](https://pic4.zhimg.com/80/v2-f7c4dba63f3094a6a7a8ed265e8a547b.png)

### GMP Algebra & Geometric Stability Hypothesis

GMP代数のエッセンスを再掲します：

$$
\begin{aligned}
\left[\hat{\bar{n}}_{\vec{k}}, \hat{\bar{n}}_{\vec{q}}\right]=\left(e^{\frac{\mathrm{k}^* q^2}{2}}-e^{\frac{\mathrm{kq}^* \ell^2}{2}}\right) \hat{\bar{n}}_{\vec{k}+\vec{q}}
\end{aligned}
$$

さらに導出を進めると、以下と等価であることがわかります：

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

定義を変えれば：

$$
\begin{aligned}
\mathcal{P} \rho_{\mathbf{q}} \mathcal{P}=e^{-q^2 \ell_B^2 / 4} e^{i \mathbf{q} \cdot \mathbf{R}} \equiv e^{-q^2 \ell_B^2 / 4} \bar{\rho}_{\mathbf{q}}
\end{aligned}
$$

前の指数因子を消去することができ、別の等価なGMP/$W_\infty$代数が得られます：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=2 i \sin \left(\frac{\mathbf{q}_1 \wedge \mathbf{q}_2 \ell_B^2}{2}\right) \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}}
\end{aligned}
$$

FCIの解析において、非常に重要なアプローチの一つは、格子系においてL.L.L.へ射影された運動量空間粒子数演算子$\hat{\bar{\rho}}_q$のGMP代数を再現することです。なぜなら、これはFQH状態を不安定化（destabilize）させる中性集団励起と最も関係があるからです。

格子系においてFQHのこのようなGMP代数構造を再現するには、特殊なバンド幾何学（band geometry）が必要です。そして、バンド幾何学とGMP代数、そしてFCIの安定性（stability）を結びつけるこの予想こそが、**幾何学的安定性仮説（Geometric Stability Hypothesis）**です。これは理論、数値計算、実験においてFCI状態が出現するかどうか、およびその安定性を解析する際に大いに役立ちます。

もちろん、FQHの代数構造を完全に復元することは、FCIが出現するための必要条件であるべきで、FCI状態の出現条件と完全に等価ではありません。この方面の理論はまだ研究が待たれています。

数値計算の面では、**幾何学的安定性仮説**はすでに基底状態縮退度、多体ギャップなど多方面で一定程度の検証が得られています。

## Ground State Degeneracy

FQH系は背景多様体のトポロジー的性質に関連した基底状態縮退度（GSD）を持ち、これは数値計算や実験においてFQHおよびFCI相を区別する重要な判断要素の一つです。

ここでは準粒子-準正孔対の生成消滅を簡単な例として用い、系の基底状態の非縮退性、およびその背景多様体のトポロジー的性質との関係を説明します。

正方形の対辺を貼り合わせて作られたトーラス上のFQH系、すなわちx-y方向ともに周期境界条件のFQH系を考えます。今、準粒子-準正孔対の生成と消滅を考えます。準粒子-準正孔はトーラスの大円（x軸）を一周して、生成されてから消滅することもできますし、トーラスの小円（y軸）を一周して、生成されてから消滅することもできます。

![Image](https://pic4.zhimg.com/80/v2-667efdec16b00f1ca9e4c7080734752e.png)

これら2つの過程の系発展演算子を$\hat{T}_x$と$\hat{T}_y$と記します。トーラスはx-y両方向に周期境界条件を持つため、トーラス上での$\hat{T}_x\hat{T}_y\hat{T}_x^{-1}\hat{T}_y^{-1}$の過程は、準粒子が準正孔を一周することと**トポロジカルに等価**であることを証明できます。準粒子または準正孔の分数統計により、この過程で生じる位相は$e^{2 \pi i/m}$となるため、以下のようになります：

$$
\begin{aligned}
\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x
\end{aligned}
$$


全過程は基底状態から出発し、基底状態上で準粒子-準正孔励起を生成し、その後消滅して基底状態（元の基底状態とは異なる可能性がある）に戻るため、$\hat{T}_x$と$\hat{T}_y$は基底状態間でのみ行列要素を持ちます。

縮退していようがいまいが、$\hat{T}_x$と$\hat{T}_y$は各基底状態$|0_1\rangle,\dots,|0_{GSD}\rangle$を基底とする線形空間上の行列です。そして$\hat{T}_x$と$\hat{T}_y$に対応する行列を求めることは、実際には$\hat{T}_x$と$\hat{T}_y$の基底状態空間における群表現を求めることです。

もし基底状態$|0\rangle$が非縮退であれば、$\hat{T}_x$と$\hat{T}_y$の過程はどちらも最終的に基底状態に戻るため、せいぜい位相が生じるだけです。

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

しかし、これでは直ちに矛盾が生じます。なぜなら以下のようになるからです。

$$
\begin{aligned}
\hat{T}_x \hat{T}_y |0\rangle = e^{i (\gamma_x + \gamma_y)} |0\rangle = \hat{T}_y \hat{T}_x |0\rangle
\end{aligned}
$$

実際、$\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x$という関係が$\hat{T}_x,\,\hat{T}_y$の非アーベル性を教えていることから、それらの基底状態空間における群表現が1次元になるはずがない、すなわち基底状態は決して非縮退ではない（縮退しているはずだ）と気づくべきです！

さらに解析を進めると、$\hat{T}_x\hat{T}_y = e^{2 \pi i/m}\hat{T}_y\hat{T}_x$の関係に対応する群表現は少なくともm次元であることがわかります。

事実、$T^2$空間上で定義された充填率$\nu = 1/m$のFQH系に対して、基底状態縮退度は：

$$
\begin{aligned}
GSD = m
\end{aligned}
$$

これがFQH系の背景多様体のトポロジー的性質と関係していることも理解に難くありません。我々の上述の導出では以下を用いました：

「トーラス上での$\hat{T}_x\hat{T}_y\hat{T}_x^{-1}\hat{T}_y^{-1}$の過程は、準粒子が準正孔を一周することと**トポロジカルに等価**である」

種数の異なる背景多様体に対して、より複雑なトポロジー的性質がより奇妙な基底状態縮退度をもたらすことは容易に想像できます。

## Effective Chern-Simons Theory

FQH系の低エネルギー効果はチャーン・サイモンズ作用量（Chern-Simons action）によって記述できます。これは実際には高エネルギー部分を積分して消去した後の有効場の理論であり、FQHの分数ホール伝導度（線形応答）、分数励起、GSD、およびその他の多層FQHに対応する分数充填数を解析する上で重要な役割を果たします。ここでは紙幅の都合上、詳しくは述べません。

## Flat Band

チャーンバンド（Chern Band）は基本的に自由電子ガスにおけるランダウ準位の役割を果たしますが、相互作用の効果をより顕著にするために、チャーンバンドのバンド幅（Bandwidth）を調節し、その上で部分的に充填された電子のエネルギーが基本的に縮退するようにします。同時に、異なるバンド間の波動関数が混合（mix）しないように、バンドギャップは十分に大きくあるべきです。これがFCI相が出現するための第一の条件、フラットバンド条件です：

チャーンバンドの分散関係がフラットバンドに近づくほど、チャーンバンド上の電子状態の運動エネルギーは小さくなり、電子間相互作用の影響が強まり、FCIなどの新奇な多体強相関状態が出現する可能性が高まります。

近年最もホットなツイストグラフェン（twisted graphene）はまさにそのような材料です。2層のグラフェン間の相対ツイスト角$\theta$、AA副格子ホッピングとAB副格子ホッピング強度の相対比$\kappa$（これは格子緩和現象などによって生じる可能性があります）などのパラメータを調節することで、フェルミ面付近の分散関係を操作し、フラットバンドに近づけることができます。その中で魔法角$\theta_c \approx 1.05^\circ$、カイラル極限$\kappa =0$付近では、ほぼ厳密にフラットなバンドが得られ、かつバンドはトポロジカルな性質（チャーン数が非ゼロ）を持っており、FCI相を研究する重要なプラットフォームとなっています。

後ほど、分散関係以外の他の格子系の性質がFCI相の出現に与える役割、例えばブリルアンゾーン（BZ）内のチャーンバンドのベリー曲率の分布、およびチャーンバンドのフビニ・スタディ計量などの幾何学的（Geometry）要因がFCI相に与える影響についても紹介します。

ナイーブに考えると、特殊な分散関係も特殊なバンド幾何学も必要というのは、FCI出現の条件を非常に厳しくしているように思えます。しかし実際には、ある格子ハミルトニアンの分散関係と波動関数（ベリー曲率、フビニ・スタディ計量などのバンド幾何学要因は実際には波動関数に関係しています）はある程度独立しています。分散関係$\epsilon(k)$のバンドに対して、BZから波動関数空間への写像とその導かれるベリー曲率、バンド幾何学を変えずに、常にそれを2-flat bandの分散関係に変えることができます。

$$
\begin{aligned}
\hat{H} = \sum_k \epsilon(k) |u_k\rangle \langle u_k| \rightarrow \hat{H}_{flat} = \sum_k \epsilon_0 |u_k\rangle \langle u_k|
\end{aligned}
$$

両者は、変換過程でバンド間のギャップが閉じない限り、トポロジカルに等価です。要するに、解析的な分析においては、分散関係$\epsilon(k)$と波動関数$|u_k\rangle$およびそこから導かれるベリー曲率$\mathcal{B}(k)$などのバンド幾何学を区別して研究することができます。

## Introduction to Quantum Geometry

量子状態はヒルベルト空間（Hilbert Space）に生息しています。ヒルベルト空間は良く定義された内積を持つため、それを用いて量子状態間の「距離」や「計量」を定義することができ、これによってヒルベルト空間に量子的な幾何記述、すなわち量子幾何学（Quantum Geometry）が与えられます。

ただし、状態ベクトル$|\psi\rangle$に非ゼロの複素数を掛けても同じ状態であることに注意すべきであり、真の状態は射影ヒルベルト空間（Projective Hilbert Space）に生息しているはずです。これは$\mathbb{C} P^{n-1}$と同型です：

$$
\begin{aligned}
\mathcal{P}_{\mathcal{H}} \simeq \mathbb{C} P^{n-1}
\end{aligned}
$$

状態間の「距離」をナイーブに定義すると：

$$
\begin{aligned}
d s^2=\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle d k^\mu d k^\nu
\end{aligned}
$$

しかしこれはゲージ不変ではありません。正しい定義は以下のようになるはずです：

$$
\begin{aligned}
d s^2=Q_{\mu \nu} d k^\mu d k^\nu
\end{aligned}
$$

ここで：

$$
\begin{aligned}
Q_{\mu \nu} \equiv\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle-\left\langle\partial_\mu \psi \mid \psi\right\rangle\left\langle\psi \mid \partial_\nu \psi\right\rangle
\end{aligned}
$$

その虚部はベリー曲率に比例します：

$$
\begin{aligned}
B_{\mu \nu} \equiv \operatorname{Im}\left[Q_{\mu \nu}\right]
\end{aligned}
$$

その実部はフビニ・スタディ計量（Fubini-Study Metric）です：

$$
\begin{aligned}
g_{\mu \nu} \equiv \operatorname{Re}\left[Q_{\mu \nu}\right]
\end{aligned}
$$

量子計量は一般的な計量と同様に（半）正定値性を持つはずなので、以下が証明できます：

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

ここで、本文の最初に述べた問題、すなわち格子系においてFQH効果に類似したFCI相をどのように実現するかという問題に戻ります。フラットバンドという条件に加え、前述の幾何学的安定性仮説は、FQH系における集団中性励起中の射影密度演算子$\hat{\bar{\rho}}_q$のGMP代数を可能な限り再現できれば、格子系においてFCI相を実現できる可能性が高いとしています。

### Analogy of Interaction

まず、格子系と連続系の相互作用を類推します：

$$
\begin{aligned}
V=\frac{1}{2} \sum_{i, j} U_{i j} \hat{n}_i \hat{n}_j
\end{aligned}
$$

フーリエ変換を行うと：

$$
\begin{aligned}
V=\frac{1}{2} \sum_{\mathbf{q}} U(q) \hat{n}_{\mathbf{q}} \hat{n}_{-\mathbf{q}}
\end{aligned}
$$

相互作用のない部分の固有波動関数：

$$
\begin{aligned}
|\mathbf{k}, \alpha\rangle=\gamma_{\mathbf{k}, \alpha}^{\dagger}|0\rangle \equiv \sum_a u_a^\alpha(\mathbf{k}) c_{\mathbf{k}, a}^{\dagger}|0\rangle
\end{aligned}
$$

興味のある$\alpha$バンドに対して、FQHにおいてL.L.L.へ射影したのと同様に、チャーンバンドへの射影物理を解析します。

射影演算子は：

$$
\begin{aligned}
\mathcal{P}_\alpha=\sum_{\mathbf{k}} |\mathbf{k}, \alpha \rangle \langle\mathbf{k}, \alpha|
\end{aligned}
$$

フラットバンドの場合、単体部分を無視し、射影後の$\overline{\rho_q \rho_{-q}}$と$\bar{\rho_q}\bar{\rho_{-q}}$は定数差しかないため省略できるとすると、チャーンバンドへ射影された相互作用ハミルトニアンは：

$$
\begin{aligned}
H_{\mathrm{CB}, \alpha}^{\mathrm{eff}}=\frac{1}{2} \sum_{\mathbf{q}} U(\mathbf{q}) \bar{\rho}_{\mathbf{q} ; \alpha} \bar{\rho}_{-\mathbf{q} ; \alpha}
\end{aligned}
$$

L.L.L.への射影と比較すると、両者の形式は基本的に一致していることがわかります

$$
\begin{aligned}
H_{\mathrm{LL}}^{\mathrm{eff}}=\frac{1}{2} \sum_{\mathbf{q}} V(\mathbf{q}) \mathrm{e}^{-q^2 \ell_B^2 / 2} \bar{\rho}_{\mathbf{q}} \bar{\rho}_{-\mathbf{q}}
\end{aligned}
$$

ここで$\mathrm{e}^{-q^2 \ell_B^2 / 2}$を提出したのは、ここでの定義によってGMP代数中の指数項を消去できるためです。

### Lowest Order Correspondence

長波長近似をとることで、射影後の演算子を$q$のオーダーに従って一階一階展開できます。射影密度演算子を$\mathcal{O}(q^2)$まで展開した結果は：

$$
\begin{aligned}
\bar{\rho}_{\mathbf{q}}=P_\alpha-i P_\alpha \mathbf{q} \cdot \mathbf{r} P_\alpha-\frac{1}{2} P_\alpha(\mathbf{q} \cdot \mathbf{r})^2 P_\alpha + \mathcal{O}(q^3)
\end{aligned}
$$

それらの交換子を計算すると：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right] \approx \mathrm{i} \mathbf{q}_1 \wedge \mathbf{q}_2 \sum_{\mathbf{k}}\mathcal{B}_\alpha(\mathbf{k}) |\mathbf{k}, \alpha \rangle \langle\mathbf{k}, \alpha|}
\end{aligned}
$$

GMP代数の$\mathcal{O}(q^2)$項と比較すると、以下のようになるべきです：

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=i\left(\mathbf{q}_1 \wedge \mathbf{q}_2\right) \bar{B}_\alpha P_\alpha}
\end{aligned}
$$

後ろの射影演算子$P_\alpha$は実際には$\bar{\rho}_{q_1+q_2}$の0次近似とみなすことができます。

$$
\begin{aligned}
{\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right] \approx \mathrm{i} \mathbf{q}_1 \wedge \mathbf{q}_2 \overline{\mathcal{B}}_\alpha \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}}
\end{aligned}
$$

これは実際、$\mathcal{O}(q^2)$でGMP代数を再現するには、**BZ上でベリー曲率が一様に分布している**必要があることを示しています。これはFCIを実現するために満たすべき第二の条件、すなわちフラットベリー曲率（Flat Berry Curvature）です。

フラットベリー曲率条件からのずれは、BZ上のベリー曲率の標準偏差で測ることができます。標準偏差が大きいほど、チャーンバンドへ射影された密度演算子はGMP代数から遠ざかると予想され、したがってFCI相はもはや安定（stable）ではなくなります。

また、最低次において、$\overline{\mathcal{B}}_\alpha$がFQHにおけるGMP代数式の$l_B^2$の役割を代替していることもわかります。これはある程度以下のことを説明しています：

**ベリー曲率は確かに実空間磁場の代わりとしての役割を果たしている**。

トポロジカルに自明なバンドに対しては、ベリー曲率の平均値は明らかに$\overline{\mathcal{B}}_\alpha=0$となるため、GMP代数を再現することはなく、FCI状態も存在しない可能性が高いです。一方、チャーン数$\mathcal{C}>1$の系におけるFCI相も現在研究のホットトピックです。

### Higher Order Correspondence

この長波長展開の精神に従い、射影密度演算子をさらに高次まで展開し、その交換子の各階におけるGMP代数からのずれを観察します。

$\mathcal{O}(q^3)$については：

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

ここで、

$$
\begin{aligned}
Q_\alpha=I-P_\alpha
\end{aligned}
$$

フビニ・スタディ計量：

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

がBZ全体で不変である時、射影密度演算子は一般化GMP代数（Generalized GMP Algebra）を満たすことが証明できます。

$$
\begin{aligned}
\left[\bar{\rho}_{\mathbf{q}_1}, \bar{\rho}_{\mathbf{q}_2}\right]=2 i \sin \left(\frac{\mathbf{q}_1 \wedge \mathbf{q}_2 \bar{B}_\alpha}{2}\right) e^{q_{1 l} g_{l m}^\alpha q_{2 m}} \bar{\rho}_{\mathbf{q}_1+\mathbf{q}_2}
\end{aligned}
$$

このようにして、なぜ量子幾何学がFCIの安定性解析に入ってくるのかが明らかになりました。これが幾何学的安定性仮説の精神です。

### Trace Condition

最低次の解析において、我々はBZ上のベリー曲率の標準偏差を用いて、強相関格子系のGMP代数からの偏離度合いを特徴付けました。これはFCIを特徴付ける第二の指標（indicator）です。第一の指標はバンドの平坦性（Band Flatness）であり、チャーンバンドの分散関係の標準偏差で特徴付けることができます。

文献においては、第三のFCI指標、すなわちトレース条件（Trace Condition）を見かけることがあります。これは実際には、$\bar{\rho}_q$交換子のより高次の項におけるGMP代数からの偏離を特徴付けています。以下、簡単に説明します。

以前、量子計量の正定性を用いて不等式を証明しました：

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] \geqslant\left|B_\alpha(\mathbf{k})\right|
\end{aligned}
$$

前後のベリー曲率は係数$2$の違いがあるかもしれません。

ここでは別の証明を与えることができます：

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right]=\left\langle\mathbf{k}, \alpha\left|(x+i y)\left(I-P_\alpha\right)(x-i y)\right| \mathbf{k}, \alpha\right\rangle +i\left\langle\mathbf{k}, \alpha\left|\left[x\left(I-P_\alpha\right) y-y\left(I-P_\alpha\right) x\right]\right| \mathbf{k}, \alpha\right\rangle
\end{aligned}
$$

ここで

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

$AA^\dagger$と$CC^\dagger$の（半）正定性により、以下が成り立ちます：

$$
\begin{aligned}
\left\langle\mathbf{k}, \alpha\left|A A^{\dagger}\right| \mathbf{k}, \alpha\right\rangle \geqslant 0, \quad\left\langle\mathbf{k}, \alpha\left|C C^{\dagger}\right| \mathbf{k}, \alpha\right\rangle \geqslant 0 \text {. }
\end{aligned}
$$

したがって

$$
\begin{aligned}
\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] \geqslant\left|B_\alpha(\mathbf{k})\right|
\end{aligned}
$$

なぜこの数学的不等式に関心を持つのでしょうか？**なぜなら、この不等式の等号「=」が成り立つのはFS計量が定数である時、かつその時のみであり、一定のFS計量こそが高次の項がGMP代数を満たすための条件だからです**。

したがって、非負の数$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right|$を定義し、それを用いて高次項のGMP代数からの偏離を特徴付けることができます。我々はこの量を「**トレース条件**」と定義し、これが第三のFCI相の指標となります。

## FCI Indicators

以上をまとめると、分数充填されたチャーンバンドにおけるFCIの安定性を特徴付ける（可能性のある）3つの指標が得られました：

+ バンド平坦性（Band Flatness）：チャーンバンドのエネルギースペクトルの標準偏差によって特徴付けられます。
+ ベリー曲率平坦性（Berry Curvature Flatness）：ベリー曲率の標準偏差によって特徴付けられます。これはチャーンバンドのGMP代数に対する$\mathcal{O}(q^2)$階での偏離を記述します。
+ トレース条件（Trace Condition）：非負の数$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right| \geq 0$によって特徴付けられます。これはチャーンバンドのGMP代数に対する$\mathcal{O}(q^3)$およびそれより高次での偏離を記述します。

### Finite Field FCI

実際には、微弱な（しかし有限の）磁場がFCI相の安定性に与える作用も考えることができます。我々は依然として前述の3つのFCI指標を用いてFCI相の安定性を特徴付けることができます。

ただし、磁場は並進対称性を破るため、単位胞が拡大し、磁気ブリルアンゾーンは元のブリルアンゾーンよりも小さくなり、それによってチャーンバンドは折り畳まれ、複数のバンドに変化します。

ベリー曲率およびFS計量をマルチバンド系に拡張することができ、射影もこれらの磁場によって分裂した複数のバンドへの射影に変わります。この時、ベリー接続は非アーベル的（non-Abelian）になり、ベリー曲率およびFS計量の次元も拡大します。

しかし、これらの拡張は自然なものであり、数から行列への拡張に似ているため、トレース条件$\operatorname{tr}\left[g^\alpha(\mathbf{k})\right] - \left|B_\alpha(\mathbf{k})\right| \geq 0$を含む3つの指標の形式は基本的に変わりません。

ここではこれ以上詳しく述べませんが、詳細はAshvinによる最近のゼロ磁場および有限磁場下でのツイストグラフェン系におけるFCI状態をシミュレーションした論文を参考にしてください。

## Wannier Function & L.L.L Wavefunction

XL Qiは、チャーンバンド中の単体ワニエ関数とランダウゲージ下のQH系の単体波動関数を対応させるスキームを提案しました。Laughlinによって与えられた多体波動関数の形式と組み合わせることで、チャーンバンド中のFCI状態の多体波動関数の性質を合理的に推測することができます。

簡単に言えば、ランダウゲージで求められた単粒子波動関数は、y方向には広がった平面波であり、x方向には局在した調和振動子波動関数です；

一方チャーンバンドでは、バンドトポロジーが非自明であるため、これはトポロジカルに保護されたエッジ状態に対応し、したがって一般的なフーリエ変換ではx、y方向ともに局在（localize）したワニエ波動関数を得ることはできません。しかし、x方向に対してのみ部分フーリエ変換（Partial Fourier Transformation）を行うことは可能であり、それによってx方向に局在し、y方向に広がった部分ワニエ関数（partial Wannier Function）が得られます。

これら2種類の単粒子波動関数を比較すると、それらを関連付けることは難しくありません。さらに電子ガス中の単粒子波動関数からLaughlin波動関数への変換を利用すれば、上述のチャーンバンド中の部分ワニエ関数を多体波動関数として書き下すことができ、それによって格子系におけるFCI状態の波動関数が得られます（図参照）。

![Image](https://pic4.zhimg.com/80/v2-5984629601675cdc8574304e8a1ab981.png)

詳細については、Qi, X. L.の論文 "Generic wave-function description of fractional quantum anomalous Hall states and fractional topological insulators. Physical review letters, 107(12), 126803." を参照してください。

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