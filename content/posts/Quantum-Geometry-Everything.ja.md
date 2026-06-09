---
title: "Quantum Geometry Everything？「量子幾何物理大応答」を一から解説する"
date: 2026-06-09T12:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Berry Curvature", "Quantum Metric", "Nonlinear Response", "Condensed Matter"]
categories: ["Physics Notes"]
---

本稿は約15,000字で、"量子幾何"（Quantum Geometry）が「何を意味するか」および「何をもたらすか」を解説する。前半は定義、後半は現象に重点を置く。必要に応じてお読みください。

<!--more-->

## はじめに (Introduction)

量子幾何（Quantum Geometry）は最近、凝聚態物理学の分野で非常に注目されており、関連する論文やレビューが急増している。筆者はサマーリサーチ中に初めて接触し、その後いくつかのnote・論文・レビューを発表した：

- [Revealing quantum geometry in nonlinear quantum materials](https://iopscience.iop.org/article/10.1088/1361-6633/pde454)
- [Electrical magnetochiral anisotropy and quantum metric in chiral conductors](https://iopscience.iop.org/article/10.1088/2053-1583/ada0b8/meta)

筆者の知識には限界があり、多くの不備があると思われるため、読者の皆様からのご指摘をぜひお願いしたい。また、更新を促してくださったJunkai Wang（[@Austeritas](https://www.zhihu.com/people/Junkai-Wang)）氏に感謝申し上げる。

---

## 量子幾何とは何か？ (What is Quantum Geometry?)

**Q：量子幾何とはどんな幾何か？**

**A：波動関数の幾何学である。**

より具体的には、量子幾何が記述する波動関数の幾何は二側面を持つ：一つは実空間における波束の幾何学、もう一つは逆格子空間における固有状態ベクトルの幾何学である。

実空間では：量子幾何 = **変形（deformation）** + **自転（self-rotation）**（物理的描像）。
逆格子空間では：量子幾何 = **長さ（length）** + **面積（area）**（幾何学的描像）。

また、量子幾何は遷移双極子–双極子モーメントとして理解することもでき、高次の一般化も可能である。注目すべき点は、構成された量子幾何量がすべて**ゲージ不変**であり、実際の物理的意味を持ち、原理的に実験的に観測可能であることだ。

### 実空間波束の幾何学 (Real Space Wave Packet Geometry)

古典力学では電子を点粒子として扱い、その並進運動が古典電流を生む。しかし量子力学によれば、電子は波動関数として存在する。その半古典的記述は実空間における波束である。重心の並進運動に加えて、波束は内部構造・内部運動を持つ——最も直感的な二つが**自転（self-rotation）**と**変形（deformation）**であり、前者がBerry曲率、後者が量子計量に対応する。

磁場が（量子）ホール効果を引き起こすのは、磁場中の電子のサイクロトロン運動が横方向の運動を生み出すためである。同様に、非自明なBerry曲率が（量子）異常ホール効果に寄与する。Berry曲率は電子波束の自転を記述し、この自転運動が磁場中のサイクロトロン運動と同様に異常ホール電流を生成するからである。

> **図①** **(a) 量子計量 ↔ 変形**：ブロッホ球上の弧長 $l_1, l_2$（量子計量 = 長さ）と、対応する実空間での波束の横方向広がり。**(b) Berry曲率 ↔ 回転**：ブロッホ球上の面積要素 $S_1, S_2$（Berry曲率 = 面積）と対応する波束の自転運動。

波束の自転の自由度がBerry曲率で記述できるなら、波束の他の自由度——例えば変形——も何らかの幾何学的量で記述できるかどうかを問うのは自然なことだ。答えはイエスであり、それが**量子計量（Quantum Metric）**である。

> **図②** $\Omega\sim\langle\mathbf{r}\times\mathbf{v}\rangle$（Berry曲率 = 自転）；$g\sim\langle r_i r_j\rangle$（量子計量 = 広がり）。電場 $\mathbf{E}$ 下：Berry曲率 → 横方向異常速度修正；量子計量 → 縦方向変形修正。

線形応答でよく知られるBerry曲率誘起の内因性異常ホール効果に加え、非線形効果として Berry曲率双極子誘起の非線形異常ホール効果、および量子計量双極子誘起の**内因性非相反磁気抵抗**がある。

数学的には、Berry曲率 $\Omega^{\mu\nu}$ と量子計量 $g^{\mu\nu}$ をまとめて**量子幾何テンソル（Quantum Geometric Tensor）** $Q^{\mu\nu}$ として表せる：

$$Q^{\mu\nu} = g^{\mu\nu} - i\Omega^{\mu\nu}$$

### 双極子–双極子遷移率 (Dipole-Dipole Excitation Rate)

量子幾何テンソルを明示的に書くと：

$$Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n = g^{\mu\nu}_n - i \Omega^{\mu\nu}_n$$

ここで $r^a_{nm} \equiv \langle\psi_m|\hat{r}^a|\psi_n\rangle$ はバンド間遷移双極子。$m\neq n$ はゲージ不変性から必要。$\Delta\hat{r}^\mu \equiv \hat{r}^\mu - \langle\hat{r}^\mu\rangle_n$ によりゲージ依存した対角成分が除去され、ゲージ不変な物理的可観測量のみが残る。

> **図③** $Q_n^{\mu\nu} = \langle\Delta\hat{r}^\mu\Delta\hat{r}^\nu\rangle_n$：ガウス型波束（黄色）の2次モーメントを双方向矢印で示す。平行四辺形の形状はQGTが波束内部構造の幾何学的計量であることを象徴する。

基底状態全体への一般化：

$$Q^{\mu\nu}_{GS} = \operatorname{tr}\left[\hat{P}\hat{r}^\mu(\mathbb{I}-\hat{P})\hat{r}^\nu\right]$$

フェルミの黄金律による遷移率：

$$\mathcal{I}_{m \leftarrow n}(\omega) = \frac{2\pi e^2}{\hbar^2} r^\mu_{mn} r^\nu_{nm} \delta(\omega - \omega_{mn}) E^\mu(\omega)\bar{E}^\nu(\omega)$$

> **図④** 2バンド図：青い放物線（$m$バンド）と赤い放物線（$n$バンド）。白太矢印（$\mathcal{I}_{m\leftarrow n}$）が遷移を示し、稲妻が周波数 $\omega$ を表す。

$\omega$ で積分し、全 $m\neq n$ で和をとると：

$$\mathcal{I}_{n}^{tot} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu$$

遷移率に異なる物理量を掛け合わせることで様々な幾何学的応答が得られる：

- (i) $\mathcal{I}_{m\leftarrow n} \times 1$：遷移率
- (ii) $\mathcal{I}_{m\leftarrow n} \times (E_m - E_n)$：ジュール熱（散逸線形電導率）
- (iii) $\mathcal{I}_{m\leftarrow n} \times (v_m - v_n)$：速度シフト（注入電流）
- (iv) $\mathcal{I}_{m\leftarrow n} \times (r_m - r_n)$：位置シフト（シフト電流）

### 逆格子空間における固有状態の幾何学 (Momentum Space Eigenstate Geometry)

逆格子空間では $\hat{\mathbf{r}} = i\nabla_{\mathbf{k}}$ であるため、量子幾何テンソルは逆格子空間での波動関数の計量を記述する：

$$Q^{\mu\nu}_{n} \sim \langle\psi_n|\nabla_{k_\mu}\nabla_{k_\nu}|\psi_n\rangle$$

> **図⑤** ブロッホ球：赤い弧 $l_1, l_2$ が弧長（量子計量 $g_\mathbf{k}^{ab}$）を、オレンジ陰影領域 $S_1, S_2$ が面積要素（Berry曲率 $\Omega_\mathbf{k}$）を示す。QGTがヒルベルト空間多様体の「長さ」と「面積」を同時にエンコードすることを視覚的に示す。

ゲージ不変な線素と面積素：

$$dl^2 = g^{\mu\nu} dk_\mu dk_\nu, \qquad dS = \Omega^{\mu\nu} dk_\mu dk_\nu$$

これにより幾何学的境界 $\operatorname{tr}g \geq 2|\Omega^{xy}|$ が理解できる——等周不等式の類推で「長さ」が「面積」に対して自然な上界を与える。

### ゲージ不変性と射影演算子形式 (Gauge Invariance and Projector Formalism)

対角要素 $\langle\hat{r}^\mu\rangle_n$ は格子原点の取り方に依存し物理的ではない。これを除去すると量子幾何テンソルにはゲージ不変な物理情報のみが残る。

> **図⑥** ゲージ変換 = 格子原点の平行移動：元の単位胞 → 新単位胞。波束中心が原点選択とともにシフト（同じ物理状態）。対角成分がゲージ依存であり、量子幾何テンソルがゲージ不変であることを示す。

**射影演算子形式（projector formalism）**：

$$\hat{P}_n = |\psi_n\rangle\langle\psi_n|$$

$$g^{\mu\nu}_n = \frac{1}{2}\operatorname{tr}[\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n], \quad \Omega^{\mu\nu}_n = i\operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n] - (\mu\leftrightarrow\nu), \quad Q^{\mu\nu}_n = \operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n]$$

縮退したバンドには $\hat{P}_n = \sum_{i=1}^{d}|\psi_{n,i}\rangle\langle\psi_{n,i}|$ に拡張。密度行列として解釈し混合状態や有限温度系の量子幾何も構築できる。

### 量子幾何の高次項 (Higher Order Quantum Geometry)

量子接続（quantum connection）：

$$Q^{\mu;\nu\rho}_n = \operatorname{tr}\left[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\partial_\rho\hat{P}_n\right]$$

Berry曲率双極子・量子計量双極子との関係：

$$\partial_\rho g^{\mu\nu}_n = \operatorname{Re}\left[Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n\right], \qquad \partial_\rho\Omega^{\mu\nu}_n = -2\operatorname{Im}\left[Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n\right]$$

### 多バンド量子幾何 (Multi-band Quantum Geometry)

2バンド量子幾何テンソル：

$$Q^{\mu\nu}_{nm} = r^{\mu}_{nm}r^{\nu}_{mn} = \operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_m\partial_\nu\hat{P}_n]$$

2バンド系では2バンドと1バンドの量子幾何が同じ情報を含む。量子化された円偏光注入電導率は2バンド系で成立し、全2バンド量子幾何テンソルの積分に等しいからである。

---

## 量子幾何は何をもたらすか？ (What Does Quantum Geometry Imply?)

量子幾何テンソルとしてパッケージ化することの利点：

1. あらゆる観測量に対する物理的・幾何学的直感。
2. 幾何/トポロジーとの接続が興味深い等式・不等式を与える：

$$\sigma_{xy} = \frac{e^2}{h}C = \frac{e^2}{h}\int_{BZ}d^dk\,\Omega^z(k)$$

### 量子幾何応答 (Quantum Geometric Responses)

**(i) 遷移率**

$$\mathcal{I}_{n}^{tot} = \frac{2\pi e^2}{\hbar^2}Q^{\mu\nu}_{n}E^\mu\bar{E}^\nu$$

直線偏光 → 量子計量；円二色性（左旋 − 右旋） → Berry曲率。

**(ii) ジュール熱 / 散逸線形電導率**

$$\int d\omega\,\frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2}Q^{\mu\nu} \quad \text{（SWM和則）}$$

$$\int d\omega\,\sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D} \quad \text{（光学f和則）}$$

感受率 $\chi^{ab}=\sigma^{ab}/i\omega$、誘電率 $\epsilon=1+\chi$、屈折率 $n=\sqrt{\epsilon}$ はすべて量子幾何の影響を受ける。

**位相的に非自明な系ほど屈折率が大きい。** なぜダイヤモンドは輝くのか？ダイヤモンドはobstructed atomic insulatorで、その非自明なトポロジー/量子幾何が $n=2.4$ をもたらす（Rock Saltの $n=1.5$ と比較）。

**(iii) 注入電流 (Injection Current)**

$$\sigma_{\mathrm{inj}}^{ab;c} \propto \int_{S_k = \{k|\omega = \omega_{mn}(k)\}} dS_k^c\, Q^{ab}$$

2バンド系では、円偏光注入電流（CPGE）が量子化される。

**(iv) シフト電流 (Shift Current)**

シフトベクトル $R_{mn}^a = \mathcal{A}_{mm}^a - \mathcal{A}_{nn}^a - \nabla_{k_a}\arg(r_{mn})$（ゲージ不変）。

$$\sigma_{\mathrm{shift}}^{ab;c} \propto \int_{\mathbf{k}} C_{bca}\,\delta(\omega - \omega_{mn})$$

注入電流と異なり、シフト電流は原理的に緩和時間 $\tau$ に依存しない純粋な量子幾何効果——超高速光電子デバイスへの大きな可能性を持つ。

**(v) 非線形輸送 (Nonlinear Transport)**

輸送領域（$\omega\to 0$）での $\tau$ スケーリング：

$$j^{(2)} = -e\sum_n\int[dk]\left(\underbrace{f_n^{(2)}v_n^{(0)}}_{\text{NLD}\,(\tau^2)} + \underbrace{f_n^{(1)}v_n^{(1)}}_{\text{BCD}\,(\tau^1)} + \underbrace{f_n^{(0)}v_n^{(2)}}_{\text{QMD}\,(\tau^0)}\right)$$

**NLD ($\tau^2$):**
$$\sigma_{ab;c}^{\text{NLD}} = \frac{e^3\tau^2}{\hbar^3}\sum_n\int[dk]\,f_n\frac{\partial^3\varepsilon_n}{\partial k_a\partial k_b\partial k_c}$$

**BCD ($\tau^1$、Berry曲率双極子、SodemannとFuによる提唱):**
$$\sigma_{ab;c}^{\text{BCD}} = \frac{e^3\tau}{\hbar^2}\sum_n\int[dk]\,f_n\left(\frac{\partial\Omega_n^{bc}}{\partial k_a} + \frac{\partial\Omega_n^{ac}}{\partial k_b}\right)$$

**QMD ($\tau^0$、完全内因的、量子計量双極子):**
$$\sigma_{ab;c}^{\text{QMD}} = \frac{e^3}{\hbar}\sum_n\int[dk]\,f_n\left(2\frac{\partial G_n^{ab}}{\partial k_c} - \frac{1}{2}\left(\frac{\partial G_n^{bc}}{\partial k_a} + \frac{\partial G_n^{ac}}{\partial k_b}\right)\right)$$

ここで $G_n^{ab} = \sum_{m\neq n}\frac{r^a_{nm}r^b_{mn} + r^b_{nm}r^a_{mn}}{\epsilon_{nm}}$ はバンド規格化量子計量。

**(vi) その他の幾何学的応答**

> **表①** 量子幾何量と対応する観測可能応答の一覧表（Tobiasレビュー、arXiv:2504.07173より）——異常ホール、非相反電導率、光学遷移率、注入電流（直線/円偏光）、シフト電流、スペクトル重み、チャーン数など。

### 幾何学的境界と和則 (Geometric Bounds & Sum Rules)

**(i) 幾何学的境界**

等周不等式：周長 $L$ を持つ全ての閉曲線の中で、円が最大の面積を囲む（$L^2\geq 4\pi A$）。量子幾何における対応する束縛：

$$\mathrm{Tr}(g) \geq |\Omega|$$

> **図⑦** 等周不等式 → 量子幾何学的境界：与えられた周長を持つ様々な形状 → 最大面積（円）。**Length ≥ Area**、**Quantum Metric ≥ Berry Curvature**。

ブリルアンゾーン全体で積分：

$$\int_{BZ}\mathrm{Tr}(g(\mathbf{k}))\,d^2k \geq 2\pi|C|$$

位相的に非自明なバンド（$C\neq 0$）には最小の全量子計量が必要。

> **図⑧** 上段——原子絶縁体（自明）：ワニエ関数が各原子サイトに高度に局在化、隣接サイト間のオーバーラップなし。下段——チャーン絶縁体（トポロジカル）：ワニエ関数が隣接サイト間で不可避的にオーバーラップし、最小限の広がり $\Omega_I\propto\int\mathrm{Tr}[g]\,dk$ を持つ。

等号条件 $\mathrm{Tr}(g(\mathbf{k}))=|\Omega(\mathbf{k})|$ — **トレース条件（Trace Condition）** — がランダウ準位の理想的量子幾何に対応し、FCI設計の核心的判断基準となる。

幾何学的境界の物理的本質は、基本的な不確定性原理 $[\hat{x},\hat{p}]=i\hbar$ に根ざしている。

**(ii) 和則**

和則は外部摂動に対する系の応答「重み」を反映し、励起状態に依存せず基底状態の内因的性質のみに対応する。

**(iii) 普遍的境界 (Universal Bound)**

Y. Onishi と L. Fu [Phys. Rev. X 14, 011052 (2024)]：

$$E_g \leq \frac{\pi ne^2}{2m|C|}\times(\text{const.})$$

トポロジカルギャップは電子の基本パラメータ（$n,m$）によって根本的に制限される。

**(iv) 一般化された幾何学的境界**

Berry曲率がゼロでも、実空間不変量（RSI）が量子計量の非ゼロ下界を強制できる [Herzog-Arbeitman, Bernevig ら, PRL 128, 087002 (2022)]。

Shinada と Nagaosa [arXiv:2507.12836 (2025)] がQGTを任意のパラメータ空間 $\boldsymbol{\lambda}$ へ一般化。

> **表②** 外場と共役演算子の対応（Shinada & Nagaosa）：$A\leftrightarrow\hat{J}$、$E\leftrightarrow\hat{P}_e$、$B\leftrightarrow\hat{S}$、$\partial u\leftrightarrow\hat{\sigma}$。

**(v) 一般化和則**

一般化モーメント $W_\eta = \int_0^\infty\omega^\eta\text{Re}[\sigma(\omega)]\,d\omega$：$\eta=-1$（誘電関数）；$\eta=0$（f和則）；$\eta=1$（有効質量）；$\eta=2$（ショット雑音）。

シフト電流の和則（歪度階層）：

$$\int_0^\infty d\omega\,\sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega) \approx \frac{2\pi e^3}{\hbar^2}\frac{1}{V}\langle\hat{X}_\alpha\hat{X}_\beta\hat{X}_\gamma\rangle_c$$

階層的対応：
- 線形応答 ($n=1$) ↔ 分散（Variance） ↔ 量子計量
- シフト電流 ($n=2$) ↔ 歪度（Skewness） ↔ 多状態幾何
- 3次応答 ($n=3$) ↔ 尖度（Kurtosis）

時間依存QGT（tQGT、Verma & Queiroz）が全ての幾何和則の母函数：

$$\mathcal{S}_{\mu\nu}^\eta = \frac{\pi e^2}{\hbar}\left[(-i\partial_t)^\eta\mathcal{Q}_{\mu\nu}(t)\right]_{t=0}$$

特定のパルス（方波や三角波電場）への時間領域応答を測定するだけで、フルスペクトル測量なしに幾何量を直接「読み出せる」。

### 量子幾何相関相 (Quantum Geometric Correlated Phases)

**(i) 量子幾何自発対称性の破れ**

フラットバンド極限（$W\to 0$）では物理が完全に幾何学的形状因子に支配される：

$$\chi_0(\mathbf{q}) \approx \frac{1}{k_BT}\sum_{\mathbf{k}}\nu(1-\nu)\left|\langle u_{\mathbf{k}}|u_{\mathbf{k}+\mathbf{q}}\rangle\right|^2$$

幾何学的因子が特定の $\mathbf{q}$ を好む場合、秩序変数が生じる——これが**量子幾何ネスティング（Quantum Geometric Nesting）**で、エネルギーに基づくフェルミ面ネスティングとは全く異なる。

**(ii) 電子–フォノン結合** — Jiabin Yuの論文を参照。

**(iii) 分数チャーン絶縁体 (FCI)**

本質的に、FCIはランダウ準位の模倣である——エネルギー面（フラットバンド）だけでなく、波動関数（量子幾何/トポロジー）面でも：チャーンバンドであるだけでなく、ブリルアンゾーン全体でトレース条件を満たす必要がある。

量子幾何はランダウ準位からの乖離を測る鍵となる要素である。

### 量子幾何情報理論 (Quantum Geometric Information Theory)

**(i) 量子フィッシャー情報 (QFI)**

純粋状態極限（$T\to 0$）では：$F_Q = 4g_{\lambda\lambda}$。

**QFI = 4 × 量子計量** ——QFIは量子計量の混合状態（有限温度）への自然な一般化。

$$F_Q(T) = \frac{4}{\pi}\int_0^\infty d\omega\tanh\left(\frac{\hbar\omega}{2k_BT}\right)\chi''_{\hat{h}}(\omega,T)$$

**(ii) 絡み合いエントロピー (Entanglement Entropy)**

自由フェルミ粒子でのレーニー絡み合いエントロピー：

$$S_A^{(\alpha)} = \frac{1}{1-\alpha}\text{Tr}\ln\det[p\mathbf{1} - C_A]$$

相関行列が実空間での波動関数の重なりと距離を本質的に反映するため、量子計量と絡み合いエントロピーの間には直接的な幾何学的対応がある。

---

## 参考文献 (References)

作成中...

---

## おわりに (Closing Remarks)

最後まで読んでいただきありがとうございます。約2年の更新停止の後、思いがけずイスラエルからアメリカに移り、指導教員のお陰で引き続き凝聚態物理学の研究を続けることができています。アメリカでの生活・学業・仕事・人間関係など多くの変化があり、まだゆっくりと適応中です。研究が深まるにつれてnoteを書く時間も減り、更新を待ってくださっていた読者の皆様、そして真面目なnoteを書くべきプラットフォームを感情の吐き出し場にしてしまったことをお詫び申し上げます。

この文章を、これまでの量子幾何学に関する理解・試行錯誤・成果の記念として捧げる。皆さんのご支援に心より感謝し、またいつかお会いしましょう～
