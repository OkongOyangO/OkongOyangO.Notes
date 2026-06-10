---
title: "🥺 Quantum Geometry Everything？「量子幾何物理大応答」を一から解説する"
date: 2026-06-09T12:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Berry Curvature", "Quantum Metric", "Nonlinear Response", "Condensed Matter"]
categories: ["Physics Notes"]
---

本稿は"量子幾何"（Quantum Geometry）が「何を意味するか」と「何をもたらすか」を解説する。

前半は理論的な導出、後半は実験現象に重点を置く。読者は必要に応じてお読みいただきたい。

<!--more-->

## はじめに (Introduction)

最近、量子幾何 (Quantum Geometry) という概念は凝聚系物理という分野で非常に注目を集めており、関連する論文やレビューが続々と現れている。筆者は夏季研究 (summer research) の期間に初めてこの概念に触れ、その後幸運にもnote、paper、reviewをいくつか発表する機会を得た。興味があれば以下を参照されたい：

> 🔗 *【link: note paper链接】*

ただし筆者の力量には限りがあり、読んだ論文も多くなく、research experienceも限られているため、多くの見落としがあるはずである。読者の諸賢にはコメント欄にて遠慮なくご教示いただきたい！最後に、知乎の人気記事著者である小王[https://www.zhihu.com/people/Junkai-Wang]の更新催促に感謝する！

## 量子幾何とは何か？ (What is Quantum Geometry?)

Q：量子幾何とは何の幾何か？
A：波動関数の幾何である。

より具体的に言えば、Quantum geometryが記述する波動関数のgeometryは2-foldである。その一つは実空間における波束の幾何であり、もう一つは逆空間における状態ベクトルの幾何である。

実空間において、量子幾何 (Quantum Geometry) = 変形 (deformation) + 自転 (self-rotation) であり、その物理的意味を反映する；
逆空間において、量子幾何 (Quantum Geometry) = 長さ (length) + 面積 (area) であり、その幾何的意味を反映する。

同時に、quantum geometryはtransition dipole-dipole momentとして理解することもでき、さらに高次のgeneralizationも可能である。特筆すべきは、これらの構築されたquantum geometric quantitiesはいずれもgauge invariantであるということ、すなわちそれらは実際の物理的意味を持ち、さらには観測可能な物理量であるということである。

本節では、まずquantum geometryのreal spaceにおける物理的意味を紹介し、そのtransition dipole-dipole momentとしての解釈を述べ、その後reciprocal spaceにおける幾何的意味を紹介し、最後に量子幾何の高次項と量子幾何のゲージ不変性について簡潔に紹介する。

### 実空間波束の幾何学 (Real Space Wave Packet Geometry)

古典力学では一般に電子を点粒子とみなし、その並進運動が古典電流を与える；一方で量子力学は、電子は点粒子ではなく波動関数の形で存在することを教えてくれる。その実空間における半古典的記述は一つの波束である。点粒子のような全体としての質量中心の並進運動に加え、波束はinternal structure & motionも持つ。最も直観的な二つは波束の自転 (self-rotation) と変形 (deformation) であり、前者はBerry Curvatureに、後者はQuantum Metricに対応する。

磁場が(量子)ホール効果を引き起こすことは誰もが知っている。なぜなら磁場中の電子のcyclotron motionがtransverse directionの運動を生み出し、それがHall currentに寄与するからである。

我々はまた、nontrivial Berry curvatureが(量子)異常ホール効果に寄与しうることにも馴染みがある。なぜならnontrivial Berry curvatureはelectronic wavepacket自身のself-rotationを記述しており、この自転運動も磁場中のcyclotron motionと同様にanomalous Hall currentを生み出しうるからである。

![図：磁場 vs Berry curvature](/posts/quantum-geometry-everything/fig01.png)

波束のself-rotation自由度がBerry curvatureによって記述されうるのであれば、我々は自然に波束の他の自由度、例えば波束のdeformationもまた何らかの幾何量によって記述されうるのではないかと連想する。その答えは肯定的であり、それがすなわち量子度規 (Quantum Metric) である。

運動中に不変を保つ剛体と、運動中に内部が変形/回転しうる波束とを想像することは難しくない。後者は全体の並進運動に加え、内部の変形/回転によるanomalous motionを持つ。これがすなわち量子幾何が各種のgeometric responseを生み出す物理的機構である。線形応答でよく見られるBerry curvature induced intrinsic anomalous Hall effectに加え、nonlinear effectにおけるBerry curvature dipole induced nonlinear anomalous Hall effect、ならびにquantum metric dipole induced intrinsic nonlinear anomalous Hall & intrinsic nonreciprocal magnetoresistanceなどもある。

![図：quantum metric vs deformation](/posts/quantum-geometry-everything/fig02.png)

nonreciprocal magnetoresistanceを例にとると、磁性体系、すなわち時間反転対称性の破れた系においては、quantum metricの運動量空間における分布は対称ではなく、これがさらにnonzeroのquantum metric dipole structureを引き起こしうる。こうして、このdipolar distributed quantum metricの方向に平行/反平行に電場を加えると、波束の中心運動量が平行/反平行方向へ移動する際のquantum metric/変形/deformationが異なるものとなる。これにより平行/反平行の電場下で系の電気抵抗が異なり、ひいてはnonreciprocal magnetoresistanceが生じる。このようなnonreciprocityは新型のdiode素子の構築に利用でき、その性能は材料のquantum metricというintrinsic quantum geometric quantityによって決定される。これは量子幾何が新型電子素子の探索を助ける可能な道筋の一つである。

Mathematically、我々はさらにBerry curvature $\Omega^{\mu\nu}$ とquantum metric $g^{\mu\nu}$を一つの全体としてまとめることができ、それを量子幾何テンソル (Quantum Geometric Tensor) $Q^{\mu\nu}$と呼ぶ

$$
Q^{\mu\nu} = g^{\mu\nu} - i \Omega^{\mu\nu}
$$

ここで$g^{\mu\nu}$は量子度規 (Quantum Metric) すなわちFubini-Study metricであり、微分幾何におけるmetricに類似したsymmetric tensorである。$\Omega^{\mu\nu}$はBerry Curvatureであり、antisymmetric tensorである。2D/3D空間においては、我々はしばしばスカラー/ベクトル形式のBerry curvatureを$\Omega^z = \Omega^{xy} - \Omega^{yx}$あるいは$\Omega^a = \epsilon^{abc} \Omega^{bc}$で表すことを好む。このとき$\Omega^a$の方向は波束の回転の角運動量/磁気モーメントの方向を直接表す。

### 双極子–双極子遷移率 (Dipole-Dipole Excitation Rate)

More detailed、我々は$Q_{\mu\nu}$の具体的な形を書き出すことができる:

$$
Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n = g^{\mu\nu}_n - i \Omega^{\mu\nu}_n
$$

ここで$r^a_{nm} \equiv \langle \psi_m | \hat{r}^a | \psi_n \rangle$はposition operator $\hat{r}^a$のm-th band $|\psi_m\rangle$とn-th band $|\psi_n\rangle$の間のmatrix elementであり、しばしばinterband Berry connection/interband transition dipoleとも呼ばれる。

ここでの「interband」とは、ここでのmatrix elementが二つの異なるbandの間のもの、すなわち$m \neq n$であることを意味する。これはgauge invarianceを考慮してのことである。

ここで$\langle ... \rangle_n$はn-th bandにおけるexpectation valueを表し、$\Delta \hat{r}^\mu \equiv \hat{r}^\mu - \langle \hat{r}^\mu \rangle_n$はn-th bandにおけるposition operatorの期待値が中心位置から外れる偏差量を表す。これにより、dipole matrix elementの中のgauge dependentな対角要素の部分がちょうど取り除かれる。このgauge dependenceが人為的な座標選択と関係していることは後で示すが、ここで対角要素を取り除くのは、表式の中の物理的でない量を取り除き、観測可能な物理量を残すためである。

そのうち対称部分がquantum metric $g^{\mu\nu}_n$であり、反対称部分がBerry Curvature $\Omega^{\mu\nu}_n$である。

この定義から出発すると、一方では、我々は数学的に先のquantum geometric tensorに対する理解を完成させたことになる——quantum metricはreal spaceにおける波動関数のdipole dipole momentの対称部分（real space spread、これは実はWannier functionのspreadにも対応しており、私の以前のnoteを参照されたい。ここでは詳述しない）を与え、Berry curvatureは反対称部分（self-rotation）を与える。さらに我々はquantum geometryを一つのbandの性質から基底状態波動関数全体の実空間的性質へと拡張することができ、これによりband structureを必要としなくなり、ひいては任意の量子多体系に対してquantum geometric tensorを構築することすら可能となる：

$$
Q^{\mu\nu}_{GS} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_{GS} = \operatorname{tr} \left[ \hat{P} \hat{r}^\mu (\mathbb{I} - \hat{P}) \hat{r}^\nu \right]
$$

ここで$\hat{P}$はGround State projector operatorであり、$\mathbb{I}$は単位行列である。このようにして、任意の（基底）状態に対してquantum geometric tensorを定義することができ、それは（基底）状態の内禀的な物理量として、基底状態の導電性などの一連の基礎的な物理的性質をも反映しうる：

> 🔗 *【link: Wannier function spread note】*

> 🔗 *【link: insulator or metal】*

![図：quantum metric vs real space spread](/posts/quantum-geometry-everything/fig03.png)

他方では、我々はさらに新たな理解を得ることができる——quantum metricはdipole dipole excitationの対称部分に対応し、Berry curvatureはdipole dipole excitationの反対称部分に対応する。

この新たな理解は、我々がquantum geometric responseを探す助けとして非常に有用である。我々はまず、どこでdipole dipole excitationに出会うかをいくつか思い出してみるとよい。量子力学におけるFermi Golden Ruleを連想することは難しくない（Fermi Golden RuleとResponse Theoryの関係についても私の以前のnoteを参照されたい。ここでも詳述しない）。

Fermi Golden Ruleは、空間的に一様な外部電場の作用下（摂動Hamiltonianが$H' = -e \hat{\mathbf{r}} \cdot \mathbf{E}$）において、n-th band (eigenstate)からm-th band (eigenstate)への遷移率が次のようになることを教えてくれる：

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi}{\hbar^2} | \langle \psi_m | -e \hat{\mathbf{r}} \cdot \mathbf{E}(\omega) | \psi_n \rangle |^2 \delta(\omega - \omega_{mn})
$$

その中に、我々が必要とするinterband dipole-dipole transition matrix element $\langle \psi_m | -e \hat{\mathbf{r}} \cdot \mathbf{E} | \psi_n \rangle = - e r^\mu_{mn} E^\mu$が直接含まれていることに気づくのは難しくない。したがって：

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2}  r^\mu_{mn} r^\nu_{nm} \delta(\omega - \omega_{mn}) E^\mu(\omega) \bar{E}^\nu(\omega)
$$

![図：Fermi Golden Rule](/posts/quantum-geometry-everything/fig04.png)

ここで$\bar{E}$は複素共役を表し、我々は$\mathbf{E}(t) = \mathbf{E}(\omega) e^{i \omega t} + c.c.$と定義する。この式全体に少し操作を加えるだけで、その中のquantum geometric quantityを直接抽出できることに気づくのは難しくない。

例えば、我々はすべての$m \neq n$の状態について和をとり、n-th bandから他のbandへのtotal transition rate $\sum_{m \neq n} \mathcal{I}_{m \leftarrow n}(\omega)$を得て、その後$\omega$について積分してdelta functionを相殺すれば、n-th bandのtotal transition rateがn-th bandのquantum geometric tensorに比例することが得られる。

$$
\mathcal{I}_{n}^{tot} = \int d\omega \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} \sum_{m \neq n} r^\mu_{mn} r^\nu_{nm}  E^\mu \bar{E}^\nu \propto Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu
$$

これは、一様に分布したスペクトルに対する系の総遷移率が量子幾何テンソルに比例することを教えてくれる。これもまたquantum geometric tensorのtransition dipole-dipole matrix elementとしての解釈の直接的な応用である：従来我々は一般にresponse functionの各種matrix elementから出発して幾何量を組み立て、その後これらの応答がgeometricであると主張していた。今や我々がgeometric quantityの物理的解釈についてより深い理解を得たのであれば、我々はその逆を行い、物理的意味から直接出発して物理量の幾何的応答を構築することが完全に可能となる。

ここで我々は純粋なtransition rateについて和をとったが、同様の方法でさらに多くのtransition rateを構築することもできる。例えばtransition rateに「m-th bandからn-th bandへのエネルギー差」$\omega_{mn} = E_m - E_n$を掛ければenergy dissipation rateが得られる。電場駆動の系にとって、これは実はジュール熱Joule heatである。本人にも以前関連するnoteがあるので、参照されたい。

> 🔗 *【link: Joule heat note】*

そしてJoule heatはさらにlinear conductivityの中のdissipativeな部分に対応する。これはdissipative linear conductivityもまたquantum geometricであることを示している。

また例えば、transition rateに「m-th bandからn-th bandへの速度差」$v_m - v_n = \nabla_k \omega_{mn}$を掛ければvelocity shift rateが得られ、これはnonlinear optical conductivityの中のinjection currentと直接関連する；また例えば、transition rateに「m-th bandからn-th bandへの変位」$R_{mn} \sim \langle r \rangle_m - \langle r \rangle_n$を掛ければpositional shift rateが得られ、これはnonlinear optical conductivityの中のshift currentと直接関連する。そしてこの両者はいずれもquantum geometricであることが既に証明されており、前者はquantum metric/Berry curvatureと関連し、後者はより高次のquantum connectionと関連する。

まとめると：

(i) $\mathcal{I}_{m \leftarrow n} \times \text{1}$: Transition Rate 

(ii) $\mathcal{I}_{m \leftarrow n} \times (E_m - E_n)$: Joule Heat (dissipative linear conductivity)

(iii) $\mathcal{I}_{m \leftarrow n} \times (v_m - v_n)$: Velocity Shift (injection current)

(iv) $\mathcal{I}_{m \leftarrow n} \times (r_m - r_n)$: Positional Shift (shift current)

我々は後でより詳細な (detailed) 説明を与える。

### 逆格子空間における固有状態の幾何学 (Momentum Space Eigenstate Geometry)

これまでに、quantum metricとBerry curvatureがそれぞれelectronic wavepacketのreal spaceにおけるdeformationとself-rotationを記述しており、数学的にはそれぞれinterband dipole-dipole transition matrix element $\langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n$の対称部分と反対称部分に対応することを理解した。続いて、quantum geometryのreciprocal space（逆空間、運動量空間）における幾何学的意味を紹介する。

量子力学によれば、運動量演算子のreal space表象は座標$\mathbf{r}$に関する微分$\hat{\mathbf{k}} = -i \nabla_{\mathbf{r}}$であり、対応する座標演算子のreciprocal space表象は運動量$\mathbf{k}$に関する微分$\hat{\mathbf{r}} = i \nabla_{\mathbf{k}}$である。さらに、quantum geometric quantityの本質が(interband) dipole-dipoleの期待値であることはすでに知っている。この両者を組み合わせることで、quantum geometric tensorが波動関数のreciprocal space上の計量を記述していることが分かる。

$$
Q^{\mu\nu}_{n} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n \sim \langle \psi_n | \nabla_{k_\mu} \nabla_{k_\nu} | \psi_n \rangle
$$

![図：曲がった空間の計量とBloch sphere](/posts/quantum-geometry-everything/fig05.png)

より厳密に、gauge invarianceを保証する表式は次の通りである。

$$
Q^{\mu\nu}_{n} =  \langle \nabla_{k_\mu} \psi_n | \left[ \mathbb{I} - | \psi_n \rangle \langle \psi_n | \right] | \nabla_{k_\nu} \psi_n \rangle
$$

ここまでで、real spaceのposition operatorを波動関数空間に作用させることは、reciprocal space上で微分を取ること、言い換えれば$\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$という微小な平行移動を行い、その後state vectorの変化を対称あるいは反対称に掛け合わせることに相当すると分かった。これはまさに、differential manifold上で「長さ」と「面積」を求める操作に対応している。この観点から言えば、quantum metricは波動関数空間のreciprocal space上の「長さ」 $dl^2 = g^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$を測り、Berry curvatureは波動関数空間のreciprocal space上の「面積」 $dS = \Omega^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$を反映している。

![図：Bloch sphereの計量と曲率](/posts/quantum-geometry-everything/fig06.png)

具体的には、まずline elementの距離をどのように求めるかを考えよう。line elementを得るために、$\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$に対応するstate vectorの変化を考える。この過程で、波動関数は$|\psi_n(\mathbf{k})\rangle$から$|\psi_n(\mathbf{k} + d\mathbf{k})\rangle$へと変化し、波動関数の変化に対応するベクトルはHilbert Spaceにおいて$|\psi_n(\mathbf{k} + d\mathbf{k})\rangle - |\psi_n(\mathbf{k})\rangle$となる。そしてこのベクトルがreciprocal space上で対応するベクトルは$|\Delta \psi_n(\mathbf{k})\rangle = |\partial_{k_\mu} \psi_n(\mathbf{k})\rangle dk_\mu$である。長さ（の二乗）を得るために、このベクトルと自身との内積を取ると、次が得られる。

$$
dl^2 = \langle \Delta \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k}) \rangle = \langle \partial_{k_\mu} \psi_n(\mathbf{k}) | \partial_{k_\nu} \psi_n(\mathbf{k})\rangle dk_\mu dk_\nu
$$

しかし、このように定義されたline elementはgauge invariantではない。なぜなら、波動関数の真にphysicalな部分はその大きさ（ノルム）には依存しないからである。これは、$|\Delta \psi_n(\mathbf{k})\rangle$のノルム方向の成分、すなわち$|\psi_n(\mathbf{k})\rangle$方向への射影を取り除く必要があることを意味する。これにより$|\Delta \psi_n(\mathbf{k})\rangle \rightarrow |\Delta \psi_n(\mathbf{k})\rangle_{\text{real}} = |\Delta \psi_n(\mathbf{k})\rangle - \langle \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k})\rangle |\psi_n(\mathbf{k})\rangle$となり、gauge invariantなline elementが得られる。

$$
dl^2 = {}_{\text{real}}\langle \Delta \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k}) \rangle_{\text{real}} = g^{\mu\nu} dk_\mu dk_\nu
$$

同様に、Berry curvatureに対応する反対称部分は「外積」に対応する面積要素の面積として理解でき、したがって次が成り立つ。

$$
dS = \Omega^{\mu \nu} dk_\mu dk_\nu
$$

これはChern number及びChern insulatorを理解する上で非常に有用である。Berry curvatureの積分はBloch sphereの面積の積分に相当し、Brillouin zone全体でmapされた波動関数がBloch sphere全体を覆うとき、対応する面積積分は単位球面（波動関数はすべて規格化されておりノルムが1であるため）の面積に対応し、which is quantizedである。

これはquantum metricとBerry curvatureの間のgeometric boundを理解する上でも有用である。周長が与えられた図形のうち、面積を最大化する図形（circle！）を常に見つけられることを想像してみてほしい。これは純粋に幾何学的な観点から、「長さ」に対して「面積」には自然にupper boundが存在することを意味する。これはquantum metricがBerry curvatureに与えるupper boundを理解する助けとなる。すなわち、後で述べるgeometric bound in 2D system: $\operatorname{tr} g  \geq 2 |\Omega^{xy}|$である。ここでは概略にとどめる。

### ゲージ不変性と射影演算子形式 (Gauge Invariance and Projector Formalism)

先ほどgauge invarianceに関する問題に触れた。簡単に言えば、波動関数に位相を加える（規範変換）$|\psi\rangle \rightarrow |\psi'\rangle = e^{i \theta} |\psi\rangle$を行った後でも、波動関数は元の状態のままであり、我々が観測する物理量は変化してはならないということである。例えば確率$P = |\langle \psi | \psi \rangle|^2$、可観測量$\hat{\mathcal{O}}$の期待値$\langle \psi | \hat{\mathcal{O}} | \psi \rangle$、Response function $\chi_{A;B} \propto \langle \psi | [ \hat{A}, \hat{B} ] | \psi \rangle$などである。

特に、格子系においてはgaugeが空間座標の原点の取り方と密接に関係している。ここで少し詳しく論じよう。

いわゆるgauge dependentとは位相変化に対応する。格子系のBloch波動関数$|\psi_{n\mathbf{k}}\rangle = e^{i \mathbf{k} \cdot \mathbf{r}} |u_{n\mathbf{k}}\rangle$に対して、規範変換（位相を加える操作）$|\psi_{n\mathbf{k}}\rangle \rightarrow |\psi_{n\mathbf{k}}\rangle e^{i \theta_n(\mathbf{k})}$は、$\mathbf{k} \cdot \mathbf{R}_n(\mathbf{k}) = \theta_n(\mathbf{k})$である限り、平行移動$e^{i \mathbf{k} \cdot \mathbf{r}}  \rightarrow e^{i \mathbf{k} \cdot (\mathbf{r} + \mathbf{R}_n(\mathbf{k}))}$を行うことに相当する。dipole matrix elementの対角成分$\langle \hat{r}^\mu \rangle_n = \langle \psi_n | \hat{r}^\mu | \psi_n \rangle$の物理的意味はn-th band Bloch波動関数の中心位置であるが、周期境界（あるいは無限大とみなす）格子系では、この中心位置は格子の原点をどこに取るかに依存する。したがってこの対角成分は物理的な量ではなく、人為的な座標の選び方に依存する量である。よってこれを取り除いて得られるquantum geometric tensorには、物理的でgauge-invariantな情報のみが残る。これにより、我々がまとめ上げた量子幾何量が物理的でintrinsicな量であることがさらに確信できる。

![図：ゲージ依存性と座標の選び方](/posts/quantum-geometry-everything/fig07.png)

ここでの対角項を具体的に書き下すと、次のように書ける。

$$
\langle \psi_{n\mathbf{k}} | \hat{r}^\mu | \psi_{n\mathbf{k'}} \rangle = \left[ -i \partial_{k_\mu} +  \underbrace{\langle u_n | i \partial_{k_\mu} | u_n \rangle}_{\mathcal{A}^\mu_{n}} \right] \delta(\mathbf{k} - \mathbf{k}')
$$

ここで$|u_n\rangle$はBloch波動関数のperiodic部分であり、Bloch wavefunctionとの関係は$|\psi_{n\mathbf{k}}\rangle = e^{i \mathbf{k} \cdot \mathbf{r}} | u_{n\mathbf{k}} \rangle$である。以降の式では$\mathbf{k}$を省略することがあるが、その都度説明はしない。ただし特筆すべきは、これまでに現れた各種のdefinitionは系が周期的な格子系であることを要求していないという点である。したがって最も一般的な系に対してもquantum geometryを定義でき、例えばinteraction/disorderを持つ多体系、さらにはquasi crystalなどの非周期系にも適用できる。私の以前のnoteを参照されたい。

> 🔗 *【link: how to distinguish insulator from metal with quantum geometry?】*

これは再びquantum geometryの普遍性を示している。その最も根本的な物理的描像と幾何学的意味は、系がperiodicでないからといって変わることはない。

この式にはhighly singularなdelta functionの微分があり、もう一つの部分は実はn-th bandのBerry connectionである。modern polarization theoryにおいて、これは周期格子系におけるpolarization（すなわちposition operatorの期待値）に対応することが知られている。先ほどこれは人為的な座標の選び方に依存する量だと述べたが、まったく役に立たないというわけではない。modern polarization theoryでは、格子に電場を加えるとBrillouin zone全体の波動関数が同時に平行移動しpolarizationに寄与する状況に遭遇する。一周期の後、各波動関数は運動量空間で元の位置に戻るが、全体のpolarizationの変化は必ずしも0ではなく、Berry connectionの微分の積分$\Delta P = \int dk  \frac{\partial \mathcal{A}_n}{\partial k} $で与えられる。Berry connectionは周期格子におけるpolarizationとして、その定義はup to a unit lattice vectorの平行移動不変量であるため、積分の結果はゼロにもなり得るし、ゼロでない整数倍にもなり得る。これがThouless topological pumpの思考実験であり、topological insulatorの出発点でもある。これに加えて、Berry curvatureもBerry connectionの微分の反対称形$\Omega^{\mu\nu}_n = \partial_{k_\mu} \mathcal{A}^\nu_n - \partial_{k_\nu} \mathcal{A}^\mu_n$として書ける。これも、Berry connectionが人為的な座標の選び方に依存するとはいえ、重要な物理的意味を持つことを間接的に示している。

我々はphysicalな物理量により関心があるので、当然gauge invariantなquantum geometry及びそれに関連するobservablesにより関心がある。しかしこれまでの定義では、波動関数を直接微分する操作$\partial_a |\psi\rangle$、さらにはresponse function中の各種matrix element $A_{nm} \equiv \langle \psi_n | \hat{A} | \psi_m \rangle$といった、gauge invariantでないものによく遭遇した。

しかし、Berry curvature、quantum metric、quantum connection、さらには最終的に計算されるquantum geometric observablesを定義する際には、formulaのgauge invarianceをできる限り保証してきた（証明は演習問題とする）。これらの間には、必ずgauge-dependentな量をgauge invariantな量に統合する一歩がある。このステップをより容易に行うために、最近いくつかの論文ではprojector formalismあるいは類似の方法を導入し、formula導出の最初の段階からformulaのgauge invarianceを保証するようになっている。例えば、n-th bandの投影演算子$\hat{P}_n$は次のように定義される。

$$
\hat{P}_n = |\psi_n\rangle \langle \psi_n|
$$

波動関数（ket & bra）にgauge transformationを行うと位相が一つ余分に現れるが、両者の位相はprojector全体の中で打ち消し合い、これによりprojector operator自身の規範不変性が生まれる。このときprojector$\hat{P}_n$は波動関数$|\psi_n\rangle$と同じだけの物理情報を含んでいるが、projectorを微分しても依然としてgauge invariantである。これは、導出の際にgauge invariantなtermsのみを残すのに非常に有利であり、大量のgauge dependentなmatrix elementを導出した後でどのようにしてgauge invariantなtermをつくり出すかを考える必要がなく、ましてや純粋にgeometricなtermをつくり出す必要もない。

これがProjector formalismの魅力である。この形式の下では、quantum metric、Berry curvature、quantum geometric tensorは次のように書ける。

$$
g^{\mu\nu}_n = \frac{1}{2} \operatorname{tr}[\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]
$$

$$
\Omega^{\mu\nu}_n = i \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n] - (\mu \leftrightarrow \nu)
$$

$$
Q^{\mu\nu}_n = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]
$$

興味のある読者は自分で証明するか、以下を参照されたい。

> 🔗 *【link: Projector formalism paper】*

Projector formalismにはさらに多くの利点がある。例えば、degenerate point/bandのquantum geometryについては、single-bandのquantum geometryの公式を直接コピーすることはできないが、Projectorをd-band projectorへと直接拡張できる。

$$
\hat{P}_n = \sum_{i = 1}^{d} |\psi_{n,i}\rangle \langle \psi_{n,i}|
$$

ここでdはdegeneracyである。

さらに進んで、このprojectorを純粋状態のdensity matrixとみなし、さらにmomentum $\mathbf{k}$を他のパラメータに置き換えることで、density matrixに基づく純粋状態、さらには混合状態/有限温度系のquantum geometryを構築することもできる。これはopen quantum system、quantum informationのformalismでよく用いられる。より詳細は次のsectionで説明し、ここでは概略にとどめる。

### 量子幾何の高次項 (Higher Order Quantum Geometry)

quantum geometric tensorが波動関数のreal spaceにおけるdipole-dipole moment $\langle \Delta r^\mu \Delta r^\nu \rangle_n$及びreciprocal spaceの二階momentum derivativeで定義される幾何テンソル $\langle \nabla_{k_\mu} \nabla_{k_\nu}\rangle_n$を定義しているのだから、当然より多くのdipole/momentum derivativeの組み合わせを考えることができ、それによりより高次のquantum geometric quantities、e.g. quantum connection, torsion tensor, Riemann curvature, etc.を得られる。

quantum connectionを例にとると、single-bandのquantum connectionは次のように書ける。

$$
Q^{\mu;\nu\rho}_n = \operatorname{tr} \left[ \hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \partial_\rho \hat{P}_n \right]
$$

ここでは直接Projector formalismの形式で書き下した。これにより表式のgauge invarianceも保証される。

もう一種類の高次の幾何量は、低次の幾何量を直接微分することから得られる。例えばBerry curvature dipole $\partial_\rho \Omega^{\mu\nu}_n$やquantum metric dipole $\partial_\rho g^{\mu\nu}_n$であり、これらはnonlinear responseなど高次のresponse functionに現れることがある。

quantum connectionはBerry curvature/quantum metric dipoleとも密接な関係を持つ。

$$
\partial_\rho g^{\mu\nu}_n = \operatorname{Re} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right]
$$

$$
\partial_\rho \Omega^{\mu\nu}_n = -2 \operatorname{Im} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right]
$$

このように、quantum metric/Berry curvature dipoleもquantum connection $Q^{\mu;\rho\nu}$における$\mu \leftrightarrow \nu$の対称部分と反対称部分に対応していることが分かる。

### 多バンド量子幾何 (Multi-band Quantum Geometry)

n-th bandのquantum geometric tensorを注意深く観察すると、和を取られている各項$r^{\mu}_{nm} r^{\nu}_{mn}$という全体もまたgauge invariantであり、これはn-th bandとm-th bandの間に限定された2-band dipole-dipole transition matrix elementに対応することが分かる。実際、各種のresponse functionにおいて$r^{\mu}_{nm} r^{\nu}_{mn}$は頻繁に現れる一方、各bandについて重みなしで和を取った形$\sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn}$はそれほど頻繁には現れない。2-band dipole-dipole transition matrix element自体もgauge invariantであるから、我々はしばしば次善の策として2-band上で定義されたquantum geometric tensorを用いる。

$$
Q^{\mu\nu}_{nm} = r^{\mu}_{nm} r^{\nu}_{mn} = g^{\mu\nu}_{nm} - i \Omega^{\mu\nu}_{nm}
$$

ここで$m \neq n$である。$r_{mn}^\mu = \langle u_m | i \partial_\mu | u_n \rangle$もしばしば関わってくることが分かるが、このoff-diagonal dipole matrix element自体はgauge invariantな量ではない。そこで「tangent vector」 operator $\hat{e}^\mu_{mn}$を構築できる（詳細はAhnの論文を参照されたい）。

$$
\hat{e}^\mu_{mn} = |u_m \rangle r_{mn} \langle u_n|
$$

$r_{mn}$自体はgauge dependentであるが、$\hat{e}^\mu_{mn}$というoperator自体はgauge invariantであり、しかもこのoperator自身が「tangent vector」の物理的意味を備えている。すなわち、状態$|u_n\rangle$の$\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$におけるずれの、$|u_m\rangle$方向への射影である（$d\mathbf{k}$が無限小のときtangent方向に近づくため、that's why we call it "tangent vector"）。

このようにして、各種の2-band quantum geometric quantitiesはProjector operatorと同様にtraceを取る形で書ける。例えば次の通りである。

$$
Q^{\mu\nu}_{nm} = - \operatorname{tr}[\hat{e}^\mu_{mn}\hat{e}^\nu_{nm}]
$$

対応して2-band quantum connectionもある。

$$
C^{\alpha\beta\gamma}_{nm} = \operatorname{tr} \left[ \hat{e}^\alpha_{mn} \partial_\beta\hat{e}^\gamma_{nm} \right]
$$

「tangent vector」 operator自体がgauge invariantであるから、これもProjector operatorの形式で表すことができる。

$$
\hat{e}^\alpha_{mn} = i \hat{P}_m (\partial_\alpha \hat{P}_n) \hat{P}_n
$$

こうして、2-band quantum geometric tensorは次のように書ける。

$$
Q^{\mu\nu}_{nm} = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_m \partial_\nu \hat{P}_n]
$$

2-band quantum connectionも次のように書ける。

$$
C^{\alpha\beta\gamma}_{nm} = \operatorname{tr} \left[ \hat{P}_n \partial_{\beta} \hat{P}_m \left( \partial_{\alpha} \partial_{\gamma} \hat{P}_n + \partial_{\alpha} \hat{P}_m \partial_{\gamma} \hat{P}_n \right) \right]
$$

詳細な導出は以下を参照されたい。

> 🔗 *【link: Projector formalism paper】*

2-band quantum geometryは、系が2 band（2次元Hilbert space）しか持たないとき、二つのbandの固有状態が2D空間内で直交しているため、一方を知ればもう一方も分かる。このとき2-band quantum geometryと1-band quantum geometryは同じ情報を含むため、2-band quantum geometryが記述するresponseは、系が二バンドしか持たないときsingle-band quantum geometryが記述するresponseに退化する。例えばquantized injection conductivityが2-band systemでのみ成立するのは、quantized circular injection conductivityが実はすべての2-band quantum geometric tensorの和であるためであり、一方Chern number quantizationはsingle-bandのBerry curvatureに対してのみ成立する。詳細は原文を参照されたい。

> 🔗 *【link: quantized circular injection conductivity】*

## 量子幾何は何を意味するか？ (Quantum Geometry means What?)

行列要素を quantum geometric tensor へとまとめ上げ、さまざまな物理量を理解することには多くの利点がある。

一つは、さまざまな物理量の物理的・幾何学的な意味を、物理的な intuition によってより容易に理解できることである。例えば、異常ホール効果と Berry curvature の関係は、波束の self-rotation が寄与する anomalous motion によって理解できる。同時に、これらの geometric quantity は研究対象の材料・系そのものに固有 (intrinsic) な property でもあり、これは我々が望む物理系を理解・制御するうえで非常に有用である。我々はもはや、エネルギー・波動関数・可観測量の行列要素といった、より枝葉末節でかつ gauge dependence を含みうる量をどう制御するかを苦労して理解する必要はなく、まとめ上げられかつ材料に固有な quantum geometric properties にのみ注目すればよい。

二つ目は、幾何学・トポロジーとの関連を通じて、興味深い量子系の恒等式・不等式を得られることである。最も重要な例として、量子（異常）ホール効果の quantized Hall conductivity は、系における topological に非自明なエネルギーバンドの quantized Chern number に対応する:

$$
\sigma_{xy} = \frac{e^2}{h} C = \frac{e^2}{h} \int_{BZ} d^dk \Omega^z(k)
$$

たとえ quantized Hall conductivity のような quantized な幾何量が得られない場合でも、いくつかの興味深い恒等式・不等式を得ることができる。例えば、先に述べた geometric bound $\operatorname{tr} g  \geq 2 |\Omega^{xy}|$ は、quantum metric に比例する任意の物理量が Berry curvature（Chern number）によって「下支え」されることを示唆しており、これは topological に非自明な系の幾何応答に対する lower bound を与える。

### 量子幾何応答 (Quantum Geometric Response)

まず物理から出発し、量子幾何量がどのように物理系の response function に関与するかを考える。

電場で駆動される系について、我々は先に transition rate の表式を議論した:

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2}  r^\mu_{mn} r^\nu_{nm}  \delta(\omega - \omega_{mn}) E^\mu \bar{E}^\nu
$$

先に述べたように、transition rate を異なる物理量と組み合わせることで、異なる geometric response を生み出すことができる。ここではより detailed な議論を与える:

(i) $\mathcal{I}_{m \leftarrow n} \times \text{1}$: Transition Rate

前節で基本的に明らかにしたように、quantum geometric tensor の表式 $Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn}$ を作り出すために、まず delta function $\delta(\omega - \omega_{mn})$ を積分で消し、次に励起されうるすべての band について和をとる。これにより total transition rate は $Q^{\mu\nu}$ に比例することになる:

$$
\mathcal{I}_{n}^{tot} = \int d\omega \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n}  E^\mu \bar{E}^\nu
$$

さらに進めて、線偏光（linear polarization）の場合、すなわち $\mathcal{I}_{n}^{tot,\updownarrow}$ は、量子幾何 tensor における $\mu \leftrightarrow \nu$ 対称部分、すなわち quantum metric に対応する。一方、円偏光（circular polarization）の場合、左旋光と右旋光の差、すなわち $\mathcal{I}_{n}^{tot,\circlearrowleft} - \mathcal{I}_{n}^{tot,\circlearrowright}$ を考えると、これは量子幾何 tensor における $\mu \leftrightarrow \nu$ 反対称部分、すなわち Berry curvature に対応する。読者は以下の振幅を自分で選んで検証してみるとよい（表式中の複素共役に注意せよ）

$$
\mathbf{E}_{\updownarrow}(\omega) = (1,0,0),\,\mathbf{E}_{\circlearrowleft/\circlearrowright}(\omega) = \frac{1}{\sqrt{2}} (1,\pm i,0)
$$

詳細な導出については、著者の review paper の appendix、あるいは Ahn の paper を参照できる:

> 🔗 *【link: Ahn's paper】*

> 🔗 *【link: My review paper】*

さらに進めると、この積分式は次のことを我々に教えてくれる。すなわち、frequency に対して一様に分布した power $I(\omega) \propto |\mathbf{E}(\omega)|^2$ で系を励起すると、系全体の transition rate は quantum geometric tensor に比例する。

しかも注目すべきは、我々が $\mathbf{k}$ を陽に書いていないことであり、これはこの結果が任意の系に対して有効であることを意味する。バンド系の場合、さらに $\mathbf{k}$ 積分 $\int_{BZ} d^D\mathbf{k}$ を一つ加えればよいだけである。以降は特に断らない限り、結果の普遍性を強調するため $\mathbf{k}$ 積分は省略する。

このように、ある response function を frequency について（重み付きで）積分することで、系に固有の physical property に対応させる手法は、一般に総和則（sum rule）と呼ばれる。これは系のある内禀的な特性、例えば量子幾何量が、response の中に現れたものである。Sum rule の偉大なところは、それが系（基底状態・平衡状態）の内禀的特性に完全に対応し、励起状態とは無関係であることにある。

(ii) $\mathcal{I}_{m \leftarrow n} \times (E_m - E_n)$: Joule Heat

ジュール熱の本質は、電場の作用のもとでのエネルギーの散逸であり、エネルギーが電磁場から quantum system へと移される。これにより quantum system では絶えず粒子が基底状態 n から励起状態 m へと励起され、その後さまざまな relaxation によって基底状態へと戻り、エネルギーは熱エネルギーとして散逸する（フォノンなど他の自由度へと移される）。

まず transition rate に「m-th band から n-th band へのエネルギー差」$\omega_{mn} = E_m - E_n$ を掛けることで、n-th band から m-th band への energy transfer rate を得ることができる。その後、励起されうるすべての band について和をとると、total energy transfer rate を得ることができ、定常状態ではこれが Joule heat と一致する:

$$
\begin{aligned}
\mathcal{P}_{Joule}(\omega) & = \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) \omega_{mn} \\
& = \frac{2\pi e^2}{\hbar^2} \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \omega_{mn} \delta(\omega - \omega_{mn})E^\mu \bar{E}^\nu \\
& = \frac{2\pi e^2}{\hbar^2} \omega \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \delta(\omega - \omega_{mn}) E^\mu \bar{E}^\nu
\end{aligned}
$$

ここで $\mathcal{P}$ は（単位体積あたりの）power を表す。最後のステップでは、delta function の性質を利用して $\omega_{mn}$ を $\omega$ に置き換えた。ここまで来れば、$r^\mu_{nm} r^\nu_{mn}$ を 2-band quantum geometric tensor $Q^{\mu\nu}_{nm}$ に置き換えて、Joule heat が quantum geometric であると claim することもできる。しかし 2-band quantum geometry よりも、我々は single-band quantum geometric quantity を作り出すことをより好む。

ここで linear conductivity $\sigma^{\mu\nu}(\omega)$ の表式を考える:

$$
j^\mu(\omega) = \sigma^{\mu\nu}(\omega) E^\nu(\omega)
$$

Joule heat の公式に基づけば、次が容易に得られる:

$$
\mathcal{P}_{Joule}(\omega) = \operatorname{Re} \left[ j^\nu(\omega) \bar{E}^\nu(\omega) \right] = \sigma^{\mu\nu}_{\text{dis}} (\omega) E^\mu(\omega) \bar{E}^\nu(\omega)
$$

ここで「dis」は、電場 $E$ と位相差のない電流応答、すなわち電流応答が電場と同位相であるものと理解できる。位相が $\pi/2$ ずれた電流応答は電場と内積をとった後の power が 0 になるためである。次が容易に証明できる:

$$
\sigma^{\mu\nu}_{\text{dis}}(\omega) = \frac{1}{2} \left[ \sigma^{\mu\nu}(\omega) + \bar{\sigma}^{\nu\mu}(\omega) \right]
$$

すなわち dissipative linear conductivity は、longitudinal な real part と transverse な imaginary part を含む。

二つの Joule heat の公式を比較すると、次が容易に得られる:

$$
\sigma^{\mu\nu}_{\text{dis}}(\omega) = \frac{2\pi e^2}{\hbar^2} \omega \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \delta(\omega - \omega_{mn})
$$

そこで次に、linear conductivity の表式を用いて quantum geometric tensor の表式を作り出すこともできる。ここでは $\omega$ の因子が一つ余分にあるため、さらに $\frac{1}{\omega}$ を掛けてからすべての $\omega$ について積分すれば、quantum geometric tensor の表式を得ることができる:

$$
\int d\omega \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}
$$

これはもう一つの sum rule であり、dissipative linear conductivity を frequency について $\frac{1}{\omega}$ の重みで積分したものが、系の quantum geometric tensor に比例することを教えてくれる。ここでは、すべての occupied band について和をとるステップ $Q^{\mu\nu} \equiv \sum_{n \in \text{occ}} Q^{\mu\nu}_{n}$ を省略しており、読者自身で補ってほしい。容易に見てとれるように、これもまた sum rule が「基底状態の property」と「physical response」を結びつける一例である。ついでに言えば、この sum rule は SWM sum rule とも呼ばれ、導体と絶縁体を区別するために提唱されたものである。詳細については、私の以前の note を参照できる:

> 🔗 *【link: insulator or metal】*

特筆すべきは、linear conductivity に対しては、重み付けをしないもう一つの optical f-sum rule も存在することである:

$$
\int d\omega \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}
$$

ここで $\mathcal{D}$ は Drude weight と呼ばれ、系の carrier density $n$ と electron mass $m$ に関係し、系の内禀量の一つであり、完全に基本的な物理量によって決まる。ここでの electron mass は完全な bare electron mass ではなく、effective mass であり、これは sum rule における frequency 積分の上限、すなわち我々が考えるエネルギースケールの範囲に依存する。無限大に向かい、すべての core electron state と自由状態を考慮すれば bare electron mass $m_e$ となり、そうでなければエネルギースケール範囲内での有効質量 $m^*$ にすぎない。ただし、これはこの sum rule の重要性を損なうものではない。なぜなら、これもまた系の内禀的性質だからである。後に他の sum rule や universal bound を議論する際にも触れるので、ここではただ言及するにとどめる。

anisotropic な系の場合、effective mass はテンソルになりうるため、対応する Drude weight もテンソルになりうる。対応する sum rule は次のとおりである:

$$
\int d\omega \sigma^{\mu\nu}(\omega) = ne^2 \left[\frac{1}{m} \right]^{\mu\nu} \equiv \mathcal{D}^{\mu\nu}
$$

ここで $m$ はテンソルであり、対応する $\mathcal{D}$ もテンソルである。

さらに進めると、電気伝導率からより多くの有用な性質、例えば電気容量 capacitivity、誘電率 dielectric constant、屈折率 refractive index を得ることができる。これらの性質はいずれも、系の電場に対する電気分極 $P$ の応答に関係しており、電気分極と電流の間には時間に関する微分 $\frac{d}{dt}$（frequency domain では $i\omega$ の因子）だけの違いしかない:

$$
j^a(\omega) = \sigma^{ab} (\omega) E^b (\omega) = \left( \frac{d P^a}{d t} \right)(\omega) = i \omega P^a (\omega)
$$

分極率 $\chi^{ab}$ は、電気分極 $P^a$ と電場 $E^b$ の比として定義される:

$$
P^a = \chi^{ab} E^b
$$

比較すると、分極率と電気伝導率の間には $i\omega$ の因子だけの違いしかないことが容易にわかる:

$$
\chi^{ab} (\omega) = \sigma^{ab} (\omega) / i \omega
$$

先の sum rule と組み合わせれば、次のような類似の関係を推測できる

$$
\int d\omega \chi^{ab} \sim Q^{ab}
$$

実際には、分極率に関連する sum rule はもう少し複雑であり、具体的には Raquel グループの論文を参照できる。しかし、我々は電気伝導率と分極率の間の関係を get でき、さらに quantum geometry が分極率に及ぼす影響を感じ取ることができる。さらに進めて、誘電テンソル $\epsilon$ と分極率 $\chi$ の間の関係は次のとおりである:

$$
\epsilon = 1 + \chi
$$

屈折率と誘電テンソルの間の関係は次のとおりである:

$$
n = \sqrt{\epsilon}
$$

これにより、読者も quantum geometry が誘電率および屈折率に及ぼす影響を容易に感じ取れるであろう。より大雑把に言えば:

topological に非自明な系であるほど、屈折率は必ず大きくなる。

なぜダイヤモンドはこれほど輝くのか。それは diamond が obstructed atomic insulator であり、その nontrivial topology/quantum geometry によってより高い屈折率を持ち、光が内部でより多く反射されるため、より輝いて見えるのである。

これは Raquel が talk でよく用いる例であり、いささか乱暴ではあるものの、量子幾何が物理応答のあらゆる側面に、いたるところで影響を及ぼしていることをある程度反映している。この例については、後の geometric bound のところでも触れるので、ここでは要点を示すにとどめる。

(iii) $\mathcal{I}_{m \leftarrow n} \times (v_m - v_n)$: Velocity Shift

次に、Quantum Geometry がどのように Nonlinear Optical Conductivity、特に Injection Current（注入電流）に関与するかを考える。

いわゆる Injection Current の物理的描像は極めて直観的である。光照射により電子が Band $n$ から Band $m$ へ遷移し、遷移後の群速度 $v_m$ が元の群速度 $v_n$ と差を持つ場合、時間とともに線形に増大する（あるいは定常状態で飽和する）電流が生じる。これが Injection Current である。Transition Rate に速度差 $\Delta v = v_m - v_n = \nabla_k \omega_{mn}$ を掛けることで、Injection Rate が得られる。

Linearly Polarized Light（直線偏光）の場合、この応答は Linear Photogalvanic Effect (LPGE) と呼ばれ、Circularly Polarized Light（円偏光）の場合、この応答は Circular Photogalvanic Effect (CPGE) と呼ばれる。

興味深いことに、二つの Band のみを持つ系では、CPGE は Quantized である。この背後にある数学的理由は、その応答関数を直接 Quantum Geometric Tensor の積分形式で書けることにある。先に示した公式の断片の通り：

$$
\sigma_{\mathrm{inj}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} Q^{ab} (\partial_{k_c} \omega_{mn}) \delta(\omega - \omega_{mn})
$$

ここでの $Q^{ab}$ は通常、Quantum Metric の部分（Linear Polarization の場合）あるいは Berry Curvature の部分（Circular Polarization の場合）に対応する。より具体的には、CPGE については応答関数は $\int d^dk \Omega \cdot \Delta v$ に比例する。さらに一般的には、共鳴条件 $\omega = \omega_{mn}(k)$ を満たす等エネルギー面 $S_k$ 上に積分を書くことができる：

$$
\sigma_{\mathrm{inj}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{S_k=\{k|\omega = \omega_{mn}(k)\}} dS_k^c Q^{ab} 
$$

これは、Injection Current が本質的に共鳴面上の Quantum Geometry の分布を探っていることを意味する。そして 2-band モデルでは、$\Delta v$ と $\Omega$ がいずれもハミルトニアンのパラメータによって決まるため、この積分は特定の条件下でトポロジカルに量子化され、その結果 2-band system における quantized な CPGE が与えられる。

(iv) $\mathcal{I}_{m \leftarrow n} \times (r_m - r_n)$: Positional Shift

Injection Current が「速度の差」に由来するとすれば、Shift Current は「位置の急激な変化」に由来する。

古典物理では、電子の遷移は瞬間的な過程であり、位置は変化しない。しかし量子力学では、電子は波動関数として存在し、Band $n$ から Band $m$ への遷移の過程で、波束の「電荷中心」（Center of Charge）に実空間での変位が生じる。この変位は Shift Vector $R_{mn}$ と呼ばれる。

Shift Current は Bulk Photovoltaic Effect (BPVE) の主要な寄与源の一つであり、特に非中心対称な材料において顕著である。その表式にはさらに高階の幾何量が関与する：

$$
\sigma_{\mathrm{shift}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} r_{nm}^a r_{mn}^b R_{mn,a}^c \delta (\omega - \omega_{mn}) + (a,\omega \leftrightarrow b,-\omega)
$$

ここでの中心的な量である Shift Vector $R_{mn}$ は次のように定義される：

$$
R_{mn}^a = \mathcal{A}_{mm}^a - \mathcal{A}_{nn}^a - \nabla_{k_a} \arg(r_{mn})
$$

これは Berry Connection の差から遷移双極子モーメントの位相の勾配を引いたものである。Berry Connection 自体は Gauge に依存するが、Shift Vector は全体として Gauge Invariant な実空間の変位量である。

この応答は、先に述べた Quantum Connection（Christoffel symbols in Hilbert space）と密接に関連している：

$$
\sigma_{\mathrm{shift}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} C_{bca} \delta (\omega - \omega_{mn})
$$

ここで Quantum Connection $C_{abc}$ は異なる幾何量を結びつける：

$$
C_{abc} = -i \sum_{\substack{n \in \text{occ} \\ m \in \text{unocc}}} R_{mn}^{a,b} r^{c}_{nm} r^{b}_{mn}
$$

物理的には、Shift Current は光ポンピングによって引き起こされる電子の実空間での「幾何学的滑り」として理解できる。Injection Current が担体の群速度に依存する（したがって緩和時間 $\tau$ による制限を受ける）のとは異なり、Shift Current は純粋な量子幾何効果であり、理論的には緩和時間に依存しない。このため、超高速光電応答デバイスにおいて大きな潜在性を持つ。

(v) 非線形輸送 (Nonlinear Transport Conductivity)

高周波の光学応答について述べたところで、低周波さらには直流の輸送（Transport）過程へと目を向け直す。

Transport regime ($\omega \to 0$ or $\omega \tau \ll 1$) では、物理的描像が変化する。もはや単純に Fermi Golden Rule を適用することはできず、不純物散乱に由来する緩和時間 $\tau$ を真剣に取り扱わなければならない。興味深いことに、ここでの $\tau$ は単なる定数ではない。Semiclassical theory は、電気伝導度の $\tau$ への冪依存性（Scaling Law）を解析することで、まるで玉ねぎの皮をむくように、異なる幾何学的寄与を一層ずつ剥がし取れることを教えてくれる。

半古典理論によれば、電流密度は $j = -e \sum_n \int [dk] f_n v_n$ と定義される。電場摂動の下で、分布関数 $f_n$ と速度 $v_n$ を電場の次数で展開する：

分布関数: $f_n = f_n^{(0)} + f_n^{(1)} + f_n^{(2)} + \dots$、ここで $f_n^{(l)} \propto (e\tau E \cdot \nabla_k)^l f_n^{(0)} \propto \tau^l$。

速度: $v_n = v_n^{(0)} + v_n^{(1)} + v_n^{(2)} + \dots$。ここで $v_n^{(0)}$ は従来の群速度であり、$v_n^{(1)}$ は Berry Curvature がもたらす異常速度補正を含み、その完全な表式は $v_n = \frac{1}{\hbar} \frac{\partial \epsilon_n}{\partial \mathbf{k}} - \frac{e}{\hbar} \mathbf{E} \times \mathbf{\Omega}_n$ である。

この摂動展開により、任意の $n$ 階の輸送電気伝導度を異なる幾何学的寄与へと分解できる。さらに、異なる項では relaxation time $\tau$ の冪が異なるため、scaling law を通じて異なる quantum geometry 項の寄与を剥がし出すことができる。

二階効果に入る前に、まずなじみ深い一階の線形応答 $j^{(1)}$ を手早く振り返ろう：

$$
j^{(1)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(1)} v_n^{(0)}}_{\text{Drude}} + \underbrace{f_n^{(0)} v_n^{(1)}}_{\text{Anomalous Hall}} \right)
$$

Drude Conductivity（縦電流）：対応する項は $f_n^{(1)} v_n^{(0)}$ である。これは電場による加速と不純物散乱が釣り合った下での電子の古典的なドリフトである。緩和時間近似 $f_n^{(1)} \approx e \tau (\mathbf{E} \cdot \mathbf{v}_n) (-\partial_\epsilon f_0)$ を用いると、古典的な Drude 電気伝導度の公式が得られる：

$$
\sigma_{ab}^{\text{Drude}} = e^2 \tau \sum_n \int [dk] \left(-\frac{\partial f_n^{(0)}}{\partial \epsilon}\right) v_n^a v_n^b
$$

これは完全にバンド分散（群速度 $v_n$）と散乱時間 $\tau$ によって決まる、散逸的な輸送過程である。

Intrinsic Anomalous Hall Effect（横電流）：対応する項は $f_n^{(0)} v_n^{(1)}$ である。ここで $f_n^{(0)}$ は平衡状態のフェルミ分布であり、$v_n^{(1)} = -\frac{e}{\hbar} \mathbf{E} \times \mathbf{\Omega}_n$ は Berry Curvature（すなわち量子幾何の虚部）が生み出す異常速度である。この項は有名な内因性異常ホール電気伝導度を与える：

$$
\sigma_{xy}^{\text{AHE}} = -\frac{e^2}{\hbar} \sum_n \int [dk] f_n^{(0)} \Omega_n^z
$$

これは Hall current が占有バンドにおける Berry Curvature の積分に直接比例することを示している。これはバンドのトポロジカルな幾何学的性質のみによって決まる内因性効果であり、散乱時間 $\tau$ に依存せず（$\tau^0$）、無散逸である。

同様に、我々が関心を持つ二階非線形電流 $j^{(2)}$ は、自然に三項へと分解でき、各項は異なる物理機構に対応する：

$$
j^{(2)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(2)} v_n^{(0)}}_{\text{NLD}} + \underbrace{f_n^{(1)} v_n^{(1)}}_{\text{BCD}} + \underbrace{f_n^{(0)} v_n^{(2)}}_{\text{QMD}} \right)
$$

第一項 Nonlinear Drude (NLD)（$\tau^2$）は、最も「古典的」な非線形電気伝導度であり、二階分布関数補正と零階速度の結合（$f_n^{(2)} v_n^{(0)}$）に対応する。本質的にはバンドの非放物線性（Non-parabolicity）に由来し、その電気伝導度の公式は次の通りである：

$$
\sigma_{ab;c}^{\text{NLD}} = \frac{e^3 \tau^2}{\hbar^3} \sum_n \int [dk] f_n \frac{\partial^3 \varepsilon_n}{\partial k_a \partial k_b \partial k_c}
$$

第二項は Berry Curvature Dipole (BCD)（$\tau^1$）であり、Sodemann と Fu によって最初に提案された。これは一階分布関数補正と一階異常速度の結合（$f_n^{(1)} v_n^{(1)}$）に対応する。物理的描像は次の通りである。系が時間反転対称性（$T$-symmetry）を持つが空間反転対称性を破る（$P$-broken）場合、全 Chern 数はゼロであるものの、フェルミ面付近で Berry Curvature $\Omega(k)$ の分布が不均一になり、「双極子モーメント」（Dipole）を形成しうる。その電気伝導度の公式もまた Berry Curvature の双極子的性質を反映している：

$$
\sigma_{ab;c}^{\text{BCD}} = \frac{e^3 \tau}{\hbar^2} \sum_n \int [dk] f_n \left( \frac{\partial \Omega_{n}^{bc}}{\partial k_a} + \frac{\partial \Omega_{n}^{ac}}{\partial k_b} \right)
$$

第三項は Quantum Metric Dipole (QMD)（$\tau^0$）であり、零階分布関数（平衡状態）と二階速度の結合（$f_n^{(0)} v_n^{(2)}$）に対応する。系が時間反転対称性を破る（$T$-broken、例えば磁性系）とき、$\tau$ に全く依存しないこの種の非線形電流（$\tau^0$ 階）が現れる。これはすなわち内因性効果であり、理論的には不純物散乱に極めて鈍感である。その起源はまさに Quantum Metric の運動量空間における双極子分布である：

$$
\sigma_{ab;c}^{\text{QMD}} = \frac{e^3}{\hbar} \sum_n \int [dk] f_n \left( 2 \frac{\partial G_{n}^{ab}}{\partial k_c} - \frac{1}{2}\left(\frac{\partial G_{n}^{bc}}{\partial k_a} + \frac{\partial G_{n}^{ac}}{\partial k_b}\right) \right)
$$

ここでの quantum metric $G_{n}^{ab}$ は本質的にバンド規格化された量子計量（band-normalized quantum metric）であり、$G_{n}^{ab} = \sum_{m \neq n} \frac{ r^a_{nm} r^b_{mn} + r^b_{nm} r^a_{mn} }{\epsilon_{nm}}$ で与えられる。これは 2-band quantum geometry $g_{nm}^{ab}$ をエネルギーギャップの逆数 $\epsilon_{nm}^{-1}$ で重み付け平均したものとみなせる。

本文中の公式は Daniel Kaplan の PRL に基づく。実際には密度行列、多体ファインマン図、半古典波動関数などの方法で導出したり、異なる規範（length gauge $\hat{H}' = \hat{\mathbf{r}} \cdot \mathbf{E}$、velocity gauge $\hat{H}' = \hat{\mathbf{p}} \cdot \mathbf{A}$）を採用したりすると細部が異なり、QMD 係数を統一しようと試みる論文も多い。さらに高階の無秩序補正などの「外因性」効果（skew scattering, side-jump など）を考慮すると、nonlinear order の結果はより複雑になる。

このような複雑さが現れるのは、高階項では異なる仮想過程における寿命効果がより微妙になり、すべての項で同一の $\tau$ を用いることは完全には等価でなく、$\tau$ と応答次数の順序を入れ替えるだけでも異なる物理予測を与えうるからである。例えば $\omega \rightarrow \omega + i/\tau$ について、線形応答では唯一の $\tau$ を統一的に扱えるが、非線形階（例えば $\omega_1 + \omega_2$）では、補償が $\omega_1 + \omega_2 + i/\tau$、$\omega_1 + \omega_2 + 2i/\tau$、あるいは他の形のいずれであるべきか、現時点で統一的な結論はない。もちろん緩和時間近似を放棄し、すべての無秩序図を直接計算することもできるが、それは表式を極めて複雑にし、パラメータも多くなり、実材料計算の難度は非常に高くなる。

QMD の具体的な係数は論者によって異なるが、少なくとも $\tau^0$ 階における主要な構造は quantum metric dipole $\partial_c G_{n}^{ab}$ に比例する。

この摂動論は三階輸送（$j^{(3)}$）さらにはより高階へと拡張でき、形式は依然として各階の分布関数補正と速度補正の結合への分解である：

$$
j^{(3)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(3)} v_n^{(0)}}_{\text{Drude } (\tau^3)} + \underbrace{f_n^{(2)} v_n^{(1)}}_{\text{BC Quadrupole } (\tau^2)} + \underbrace{f_n^{(1)} v_n^{(2)}}_{\text{Geometric } (\tau^1)} + \underbrace{f_n^{(0)} v_n^{(3)}}_{\text{Intrinsic } (\tau^0)} \right)
$$

具体的には、各項は異なる幾何学的物理機構に対応する：

* $\tau^3$ (3rd order Drude)：バンドのより高階の非放物線性（Jerk current）に由来し、主に古典的な背景信号の部分である。

* $\tau^2$ (Berry Curvature Quadrupole)：$f_n^{(2)} v_n^{(1)}$ に対応する。一階の AHE が Berry Curvature の「単極子モーメント」（平均値）に対応し、二階の BCD が「双極子モーメント」に対応するように、三階応答はさらに Berry 曲率の四極子（Quadrupole）分布を探る。

* $\tau^1$ (Quantum Metric Quadrupole)：$f_n^{(1)} v_n^{(2)}$ に対応する。この項は Quantum Metric の幾何学的効果のより高階への拡張を表し、計量場の四極子的性質に関わる。

* $\tau^0$ (Intrinsic Geometry & Connection Dipole)：$f_n^{(0)} v_n^{(3)}$ に対応する。これは完全に内因性の応答であり、散乱に依存しない。特に注意すべきは、ここでの「内因性」は低階の幾何量の単なる延長ではなく、Quantum Connection Dipole のような全く新しい高階の幾何学的対象をも含むことである。異なる記述体系や導出方法では、この項の係数構造もまた異なりうる。

(vi) Other geometric responses

詳しくは他の review を参照されたい。ここでは適当に一つの表を選んで示す：

![図：Tobias の review より引用した表](/posts/quantum-geometry-everything/fig08.png)

### 幾何学的境界と総和則 (Geometric Bounds & Sum Rules)

ここで再び物理から幾何へと立ち返ろう。我々が定義したこれらの quantum geometry は同時に幾何量でもあるのだから、幾何学上の興味深いいくつかの結論を考え、それを対応する geometric response に適用して、どのような面白い結果が得られるかを見てみよう。

もちろん我々に最もなじみ深いのはやはり Berry Curvature と Quantum Hall Effect (QHE) である。その物理的本質は極めて簡潔である。すなわち、ホール電気伝導度の量子化 $\sigma_{xy} = C \frac{e^2}{h}$ は、Berry Curvature のパラメータ空間における「面積分の量子化」として幾何学的に理解できる。

しかしながら、Quantum Geometry の内実はこれにとどまらない。以下の五つの観点から議論を展開する：

1. Geometric Bound: 計量（Metric）と曲率（Curvature）の間の基礎的な不等式を振り返り、幾何学的直観と物理的直観の両面から二重に理解する。
2. Sum Rule: 光学応答の重みと量子幾何量（特に Quantum Metric）との間の直接的な関係を確立する。
3. Universal Bound: 上記の両者を結びつけ、トポロジカルなエネルギーギャップが電子の基本パラメータによって制限されるという普遍的上界を導き、量子幾何が任意の系に課す幾何学的制限が普遍性を持つことを示す。
4. Generalized Geometric Bound: geometric bound をゼロ Berry 曲率（対称性に守られた場合）および任意のパラメータ空間の場合へと拡張する。
5. Generalized Sum Rule: 高階の周波数モーメント、非線形応答の sum rule、さらにはパルスを用いて実験的に sum rule を測定する戦略について、さらに議論する。

(i) Geometric Bound

量子幾何へ深く入る前に、まず古典的な幾何学的直観、すなわち等周不等式 (Isoperimetric Inequality) を振り返ろう。これは、平面上で与えられた周長 $L$ を持つすべての閉曲線の中で、円が囲む面積 $A$ が最大である（$L^2 \ge 4\pi A$）ことを教えてくれる。これは「計量（長さ）」が「面積（曲率）」に対して課す根本的な制限を明らかにしている。

量子幾何において、Quantum Metric $g$ はヒルベルト空間における距離を定義し、Berry Curvature $\Omega$ は位相フラックス（面積に類似）に対応する。それらが本質的に幾何学における長さと面積でもある以上、それらの間にも類似の幾何学的制約が存在する：

$$\mathrm{Tr}(g) \ge |\Omega|$$

これについては以前の note でより詳細な導出を行っているが、ここでは図的な理解を与える：

![図：geometric bound](/posts/quantum-geometry-everything/fig09.png)

この境界についてのさらなる物理的詳細は、著者の以前の note を参照されたい：

> 🔗 *【link: geometric bound / FCI note】*

これが geometric bound の幾何学的理解、すなわち「長さ」が「面積」に対して課す制限である。そして前章で知った通り、quantum geometry には幾何学的意味のほかに、それ自身の物理的意味もある。例えば quantum metric は波束の二次モーメント $\langle \Delta \hat{r}^a \Delta \hat{r}^b \rangle$ を記述し、波束の size を与えるに等しい。これは、非ゼロの Berry Curvature（トポロジカルな非自明性）が必然的に量子状態にパラメータ空間における非ゼロの「大きさ」を要求することを意味し、これがさらに電子の response（前小節の内容）や interaction（次小節の内容）に影響を与えうる。

![図：トポロジカルバンドの波動関数](/posts/quantum-geometry-everything/fig10.png)

ブリルアンゾーン（BZ）全体にわたって積分すると、この不等式の物理的意味はより深遠になる：

$$
\int_{BZ} \mathrm{Tr}(g(\mathbf{k})) d^2k \ge \int_{BZ} |\Omega(\mathbf{k})| d^2k \ge \left| \int_{BZ} \Omega(\mathbf{k}) d^2k \right| = 2\pi |C|
$$

ここで $C$ は陳数（Chern Number）である。

これは、トポロジカルに非自明なバンド（$C \ne 0$）が必然的に最小の総量子計量（Total Quantum Metric）を伴うことを意味する。これは Wannier 関数の局在性から、より直観的に理解できる。Marzari と Vanderbilt は、Wannier 関数の規範不変な広がり（Spread）が、Quantum Metric のブリルアンゾーン上での積分によって決まることを指摘した：

$$\Omega_I \propto \int_{BZ} Tr[g(\mathbf{k})] d\mathbf{k}$$

これは Quantum Metric が、電子が実空間において局在できる根本的な限界を設定することを意味する：

* トポロジカルに自明なバンド（$C=0$）については、$g \to 0$ となる規範を見つけることができ、それによって高度に局在した Wannier 関数（atomic limit）を構成できる。

* しかし、陳絶縁体（$C \neq 0$）については、幾何学的境界 $\int Tr(g) \ge 2\pi |C|$ により、Wannier 関数は常に非ゼロの最小の広がりを持つことになる。（実際、Chern band は Wannierize できない。すなわち、Chern band の Bloch wavefunction を Fourier transform してすべての方向に exponentially decay する wannier function を得ることはできない。これも理解に難くなく、我々の Chern band model は少なくとも二バンドであり、1-band かつ Chern band であるような tight binding model を書き下すことは不可能である。）

特筆すべきは、不等式が等式になるとき、ちょうど Landau Level の ideal quantum geometry、すなわち最小不確定波束の場合に対応することである。Landau Level の quantum geometry については、私の以前の note を参照されたい：

> 🔗 *【link: LL QG note】*

これは別の側面から、geometric bound の物理的本質が量子力学の基本的な不確定性原理
$[\hat{x}, \hat{p}] = i\hbar$
に根ざしていることを示している。

この結論は、分数量子ホール効果の格子版アナロジーである分数陳絶縁体 (Fractional Chern Insulator, FCI) の研究において極めて重要である。

FCI の設計において、我々の中心的な戦略はしばしば「朗道能級の模倣」である。すなわち、格子系の中に非自明なトポロジーを持つ平坦なバンドを構築し、その波動関数の性質を連続空間における最低朗道能級（LLL）にできるだけ近づけようとする。

Geometric bound は、LLL が実際には量子幾何の「完璧な極限」、すなわち不等式が等号をとる場合 $\mathrm{Tr}(g(\mathbf{k})) = |\Omega(\mathbf{k})|$ を表すことを教えてくれる。これは迹条件 (Trace Condition) と呼ばれる。

したがって、この不等式は、あるトポロジカルバンドがどれほど「理想的」であるかを刻画する定量的な判定基準を提供する。等式からの逸脱の度合い $\delta = \mathrm{Tr}(g) - |\Omega|$ が小さいほど、そのバンドの波動関数が位相空間における構造において正則関数（holomorphic）に近いことを意味し、それによって分数量子ホール状態のような強相関トポロジカル秩序の安定化に有利となる。これが、魔角グラフェンなどの系において、Berry Curvature が完全には均一でないとしても、この迹条件を近似的に満たしさえすれば、依然として頑健な FCI 状態を観測できる理由である。

さらに、非線形応答においても類似の幾何学的境界が存在する。例えば、非線形ホール効果や非線形光学応答の一部の係数も、その大きさが Quantum Metric あるいはその高階モーメントによって制約される。

(ii) Sum Rule

我々は以前、「積分を仕立てる」方法によって、conductivity の周波数積分を系の内因的性質に関連する量へと仕立て上げた。ここで復習しておく：

1. optical f-sum rule：

$$
\int d\omega \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}
$$

2. geometric sum rule:

$$
\int d\omega \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}
$$

ここで指摘しておきたいのは、Sum rule が系の intrinsic property を与えられるのは、sum rule が実は系が外界の摂動に対して反応を示す一種の weight を反映しているからである。例えば我々になじみ深いニュートンの第二法則 $F = ma$ は、外界の力 $F$ に対して、「重さ」（weight）が $m$ である系がなしうる「反応」、すなわち加速度 $a$ の大きさを教えてくれる。

ここでも同様である。パルス電場信号 $E(t) = E_0 \delta(t)$ を加えることを考える。時間があまりにも速いため、系は瞬間的に加速度 $a \propto F/m = e E_0 / m \delta(t)$ を獲得し、時間 $t$ について積分すると速度の変化 $v = \int dt a = e E_0 / m$ が得られる。この delta function パルスはあまりにも速く、他の dissipative force よりもさらに速いため、電子は減速する「反応」をする暇がなく、いかなる緩和効果も考慮する必要がない。したがって対応する電流は $j = ne v = \frac{ne^2}{m} E_0$ となり、対応する電気伝導度がまさに Drude weight である。これこそが optical sum rule が我々に教えてくれることであり、系が delta function パルスに対してなす反応、すなわち delta function スペクトルの電気伝導度の重み付き重ね合わせである。delta function のスペクトルはちょうど定数となるため、すべての電気伝導度を重み付けせず（定数で重み付けして）重ね合わせたものに対応し、その結果が系の外界パルス摂動への応答の「weight」、すなわち「Drude weight」となる。

この sum rule の偉大な点は、系の relaxation time がいくつであろうと（最終的には電気伝導度中の $\frac{1}{\omega + i/\tau}$ という因子に影響する）、最終的に周波数で積分した結果はこれら extrinsic な relaxation に依存せず、完全に系そのものの内因的性質（Drude weight）であるということである。

同様に、geometric sum rule は一種の geometric weight として理解でき、系が $E(\omega) \sim \frac{1}{\omega}$ のスペクトル摂動の下で示す応答率を反映する。Fourier transformation をよく行う方なら、このスペクトルが「方形波信号」に対応することは推測に難くないだろう。つまり、系が step function の形をした perturbation に対して示す応答は、系の intrinsic なもう一種の weight、すなわち geometric weight を反映している。より詳しい内容は Verma の文章を参照されたい：

> 🔗 *【link: Paper of Verma on instantaneous response】*

(iii) Universal Bound

Geometric Bound と Sum Rule を組み合わせると、凝縮系物理学における非常に深遠な結論が得られる。これは通常 Universal Bound と呼ばれる。

最近、Y. Onishi と L. Fu は [Phys. Rev. X 14, 011052 (2024)](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.14.011052) において、トポロジカルギャップ（Topological Gap）の普遍的な上界を提案した。この上界は、エネルギーバンドのトポロジカルな性質、量子幾何、そして光学応答の間の深い関係を明らかにしている。

その導出過程は、実のところ前二節の geometric bound と sum rule を巧妙に組み合わせたものである。

1. Spectral Gap Constraint: バンドギャップが $E_g$ である絶縁体に対して、その光学吸収 $\sigma(\omega)$ は $\omega \geq E_g$ のときのみ非零となる。したがって、不等式 $\frac{1}{\omega} \leq \frac{1}{E_g}$ を用いることで、光学伝導率の「マイナス一次モーメント」（誘電率に関連する）を「ゼロ次モーメント」（全スペクトル重み）と関係づけることができる。

$$
\int_0^\infty d\omega \frac{\sigma(\omega)}{\omega} \leq \frac{1}{E_g} \int d\omega \sigma(\omega)
$$

2. f-sum Rule: 古典的な光学和則によれば、光学伝導率の全重みは、キャリア密度 $n$ と電子質量 $m$ によって決まる（相互作用には依存しない）。
   
$$
\int d\omega \sigma(\omega) = \frac{\pi n e^2}{2m}
$$

3. Geometric Bound: 非自明なトポロジカル数（Chern数 $C$）は、非零の Berry Curvature を要求するだけでなく、この系に対して最小の「分極率」あるいは量子幾何的な要求を課す。研究によれば、Chern数の大きさは Quantum Metric の跡（あるいは関連する光学モーメント）によって制約される。

$$
|C| \leq \int_{BZ} \text{Tr}[g(\mathbf{k})] d\mathbf{k} \sim \int d\omega \frac{\sigma(\omega)}{\omega}
$$

以上の三点を組み合わせることで、トポロジカルギャップに関する普遍的な上界が得られる。

$$
|C| \leq \frac{\pi n e^2}{2m E_g} \implies E_g \leq \frac{\pi n e^2}{2m |C|} \times (\text{const.})
$$

この式は、与えられた電子密度と有効質量に対して、トポロジカルギャップ $E_g$ を無限に大きくすることはできないことを教えてくれる。非零のトポロジカル数 $C$ を維持しようとするなら、系は低エネルギー領域に十分な光学重み（すなわち十分な量子幾何的揺らぎ）を残しておかなければならない。

実際、多くのトポロジカル物質はバンド交差付近の band inversion に由来するが、この universal bound は、この inversion 後のギャップを無限に大きくすることはできず、ある上限が存在することを教えてくれる（もし無限に大きくできるなら、他のすべてのバンドを無限遠へ押しやり、effectively 一つのバンドだけにできてしまうが、そのような 1-band Chern band model は存在しない）。これは、多くのトポロジカル物質において、相互作用を強めることでギャップを大きくしたい（高温トポロジカル相を得るために）と望んでも、ギャップの大きさが最終的に電子の基本パラメータ（$n, m$）によって根本的に制限される理由を説明している。これもまた、quantum geometry が系の最も intrinsic な性質と密接に関連していることを示すもう一つの例である。

(iv) Generalized Geometric Bound

上述の $Tr(g) \ge |\Omega|$ という標準形式に加えて、Geometric Bound を他の状況へと一般化することもできる。

1. ゼロ Berry 曲率下の幾何学的境界 (Symmetry-Protected Geometric Bound)

標準的な Geometric Bound はしばしば非零の Chern数（Berry Curvature）に依存する。しかしながら、多くの時間反転対称（Time-Reversal Symmetric）な系では、全 Berry Curvature はゼロとなるが、これは幾何学的効果が消失することを意味しない。

Herzog-Arbeitman、Bernevig らは [PRL 128, 087002 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.128.087002) において、Berry Curvature が至るところゼロであっても、実空間不変量 (Real Space Invariants, RSIs) は依然として Quantum Metric に非零の下界を強制しうることを指摘した。

特に、阻害された原子極限 (Obstructed Atomic Limits) の平坦バンド系——すなわち Wannier 中心が局在しているものの原子位置からずれている場合——においては、対称性が波動関数に一定の非局所性を要求する。

一例を用いて理解することができる。obstructed atomic insulator に対して、symmetry は occupied band の wannier center が bond center に位置することを要求する。すなわち wannier function は bond 両側の atomic site を同時に「またぐ」必要がある。こうして、obstructed atomic insulator の wannier function は symmetry enforced spread を持つことになる。この spread（wannier 波束の大きさそのものが quantum metric に対応する: $\mathrm{tr}g \sim \langle \Delta r^2 \rangle$）があるからには、これは symmetry enforced bound for (trace of) quantum metric にも対応する。そしてこの系では、obstructed atomic insulator であるものの、なお atomic limit が存在するため、Berry curvature は至るところゼロ（at least topologically trivial）である。これは $\mathrm{tr} g \ge |\Omega|$ を超える一例である。実際、この bound は別の種類の topological index、すなわち real space invariant (RSI) を用いて定義することができる。RSI は fragile topology などの特殊な topological phases を区別するために用いられ、generalized quantum geometric bound におけるその応用については [PRL 128, 087002 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.128.087002) の原論文を参照されたい。

2. 広義のパラメータ空間と可観測量の境界 (Generalized Parameter Space)

さらに進んで、Quantum Geometry の概念は運動量空間 $\mathbf{k}$ に限定される必要はない。

Shinada と Nagaosa [arXiv:2507.12836 (2025)](https://arxiv.org/abs/2507.12836) は、Quantum Geometric Tensor (QGT) を任意のパラメータ空間 $\boldsymbol{\lambda}$ へと一般化する普遍的な枠組みを提案した。物理量演算子 $\hat{O}$ のパラメータ変化に対する応答を考察することで、広義の計量 $g_{\mu\nu}^{(\lambda)}$ と曲率 $\Omega_{\mu\nu}^{(\lambda)}$ を定義することができる。

![図：Generalized Geometric Bound](/posts/quantum-geometry-everything/fig11.png)

(v) Generalized Sum Rule

最後に、Sum Rule をより一般的な状況へと一般化することができる。

1 Generalized Optical Moments

通常の光学和則は伝導率の「ゼロ次モーメント」（直接積分）に注目するが、伝導率の広義モーメント（Generalized Moments）を定義することもできる。

$W_\eta = \int_0^\infty \omega^\eta \text{Re}[\sigma(\omega)] d\omega$

異なる $\eta$ は異なる物理量に対応し、Quantum Geometry の異なる側面と結びつく。

* $\eta = -1$ (Dielectric Function):  静的誘電率 $\epsilon(0)$ あるいは静的構造因子に対応する。これは Quantum Metric の低エネルギー振る舞いに関係し、仮想遷移の分極率への寄与 ($\chi \sim \ell_g^2 / \omega_g$) を反映する。

* $\eta = 0$ (f-sum rule): 全光学重みに対応し、前述のとおり Quantum Metric の総量 ($\int g$) と関係する。

* $\eta = 1$ (Energy/Mass): 電子の平均運動エネルギーあるいは光学質量繰り込みに対応する。

* $\eta = 2$ (Shot Noise): 電流揺らぎに関係する。

詳細は Verma の論文を参照されたい。

> 🔗 *【link: Verma's paper on Generalized Sum Rule】*

2 非線形応答和則 (Nonlinear Sum Rule)

従来の線形応答に加えて、和則の概念は非線形領域へも一般化することができる。

Matsyshyn と Sodemann [PRL 123, 246602 (2019)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.123.246602) は、非線形ホール効果（二次光電流）に関する和則、すなわち Quantum Rectification Sum Rule を発見した。

linear optical conductivity's sum rule が Quantum Metric（幾何）によって決まるのと同様に、二次非線形応答の周波数積分は Berry Curvature Derivative (BCD, $\partial_k \Omega$) によって制約される。物理的には、この種の和則は緩和時間の周波数依存性を考慮することで一般化して得られる。$\tau \to \frac{1}{\omega + i/\tau}$ とし、その後周波数について積分することで、系のある種の weight を反映する nonlinear sum rule が得られる。

さらに、体光起電力効果の主要な起源であるシフト電流 (Shift Current) に対しても、対応する和則が存在する。[Phys. Rev. Lett. 135, 066901 (2025)](https://journals.aps.org/prl/abstract/10.1103/w761-8nf7) によれば、シフト伝導率の周波数積分は Berry Connection と Quantum Metric のみによって決まるのではなく、より広範な 多状態幾何 (Multistate Geometry) と占有状態の 歪度 (Skewness) によって支配される。

シフト電流伝導率 $\sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega)$ の周波数積分は、位置演算子の **三次キュムラント (Third Cumulant, Skewness)** に近似的に等しい。

$$
\int_{0}^{\infty} d\omega \sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega) \approx \frac{2\pi e^3}{\hbar^2} \frac{1}{V} \langle \hat{X}_{\alpha}\hat{X}_{\beta}\hat{X}_{\gamma}\rangle_{c}
$$

ここで:

* $\langle \hat{X}_{\alpha}\hat{X}_{\beta}\hat{X}_{\gamma}\rangle_{c}$ は、基底状態占有多様体上における位置演算子 $\hat{X}$ の三次相関関数（すなわち **歪度 Skewness**）を表す。

* この項は、実空間における電子波動関数分布の **非対称性 (Asymmetry)** あるいは非ガウス性を測るものである。

その物理的意味を理解するために、従来の線形光学応答和則と類比することができる。

* 線形伝導率 (Linear Conductivity, $\sigma^{(1)}$):
  その和則（通常 f-sum rule あるいは Souza-Wilkens-Martin 公式に関連する）は、位置演算子の 二次キュムラント (Second Cumulant, Variance) を反映する。
  $\int d\omega \text{Re}\,\sigma^{(1)}(\omega) \sim \langle \hat{X}\hat{X} \rangle_c \sim g_{\alpha\beta} \text{ (Quantum Metric)}$
  これは 量子計量 (Quantum Metric) に対応し、物理的には波動関数の 広がり (Spread/Fuzziness) を記述する。

* シフト電流 (Shift Current, $\sigma^{(2)}$):
  上式に示されるように、その和則は位置演算子の 三次キュムラント (Third Cumulant, Skewness) を反映する。
  $\int d\omega \sigma^{(2)}(\omega) \sim \langle \hat{X}\hat{X}\hat{X} \rangle_c$
  これは 多状態幾何 (Multistate Geometry) における歪度に対応し、物理的には波動関数分布の 歪み (Skewness) の方向と程度を記述する。

上述の規則に基づき、非線形応答の次数と位置演算子のモーメントとの 階層的対応関係 (Hierarchy) を導くことができる。

* 線形応答 ($n=1$) $\longleftrightarrow$ 二次モーメント (Variance): Quantum Metric (波動関数の広がり) に対応する。

* シフト電流 ($n=2$) $\longleftrightarrow$ 三次モーメント (Skewness): Multistate Geometry (波動関数の非対称性) に対応する。

* 三次応答 ($n=3$) $\longleftrightarrow$ 四次モーメント (Kurtosis): 波動関数の 尖度 (鋭さ/長い裾) に対応すると予想される。

この新たな発見は、光起電力応答の境界に関する従来の理解を修正するものであり、バンド間の多状態結合を利用して高効率な光起電力材料を設計する上で重要な指針を与える。

これらの新しい和則は、動力学応答（Dynamical Response）に含まれる系の基底状態の intrinsic な（幾何学的な）性質を明らかにする。通常、スペクトルはすべての励起状態の複雑な情報を含むと考えられる。しかし和則は、すべての周波数の応答を積分すると、これら励起状態の詳細が「平均化」されて消え、残った結果が完全に基底状態波動関数の intrinsic な幾何構造によって決定されることを教えてくれる。

したがって、和則は単なる実験的ツールであるだけでなく、より深遠な物理原理でもある。すなわち、系の基底状態の幾何（Quantum Geometry）が、外界の微擾に対する動力学的応答の全体的な能力（Capacity）をあらかじめ決定しているのである。線形吸収の総強度であれ、非線形整流の正味の効果であれ、それらはすべて基底状態のヒルベルト空間における幾何学的形態（計量、曲率、およびその導関数）によって厳密に固定されている。

3. Experiments to probe sum rule

広義の和則は豊富な幾何学的情報を提供するが、実験的に零周波数から無限大までの完全な光学スペクトル $\sigma(\omega)$ を測定することは極めて困難である。幸いにも、時間-周波数双対性 (Time-Frequency Duality) を利用することで、プローブパルスの波形を設計することにより、スペクトル全体を測定することなくこれらの積分量を直接抽出することができる。

この考え方の核心は次の点にある。周波数領域の重み付き積分 $\int \omega^\eta \sigma(\omega) d\omega$ は、実際には系が時間領域で特定の波形のパルス $E(t)$ に対して示す瞬時的あるいは累積的な応答に対応する。

Verma & Queiroz の研究 [PNAS 122, e2405837122 (2025)](https://www.pnas.org/doi/10.1073/pnas.2405837122) および [Phys. Rev. Lett. 134, 106403 (2025)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.134.106403) によれば、時間依存幾何テンソル (Time-dependent Quantum Geometric Tensor, tQGT) $\mathcal{Q}_{\mu\nu}(t)$ は、すべての幾何学的和則の生成関数である。

$\mathcal{S}_{\mu\nu}^\eta \equiv \int_0^\infty \frac{\text{Re}[\sigma_{\mu\nu}(\omega)]}{\omega^{1-\eta}} d\omega = \frac{\pi e^2}{\hbar} \left[ (-i\partial_t)^\eta \mathcal{Q}_{\mu\nu}(t) \right]_{t=0}$

これは、系が特定のパルスに対して示す時間領域応答 (Time-Domain Response) を測定することで、幾何学量を直接取得できることを意味する。

* 階段応答 (Step Response) $\to$ Quantum Metric:
  $t=0$ の時刻に突然オフになる階段状電場 $E(t) = E_0 \Theta(-t)$ を印加する。高温（古典）極限において、その後測定される分極緩和 $\mathcal{P}(t)$ は、対称な tQGT に直接比例する。
  $\mathcal{P}_\mu(t) \approx \frac{\hbar}{2 k_B T} E_\nu \mathcal{Q}^s_{\mu\nu}(t)$
  したがって、緩和の初期時刻 ($t \to 0^+$) における分極強度を測定するだけで、Quantum Metric $g_{\mu\nu} = \mathcal{Q}^s_{\mu\nu}(0)$ を直接得ることができる。

この方法は、複雑な全周波数帯のスペクトル測定を、単一の時間点での測定あるいは特定波形応答の測定へと変換し、量子幾何の実験的探測を大幅に簡素化する。

これは、スペクトルを一点ずつ測定する必要はなく、設計された特定形状のパルス（「方形波」や「三角波」電場など）を印加し、その後の系の電流あるいは分極応答を測定するだけで、sum rule に対応する generalized geometric weight を直接「読み出す」ことができることを意味する。

### 量子幾何相関相 (Quantum Geometric Correlated Phase)

ここまで、我々が議論してきた範囲はすべて単体問題の内にあった。しかし実際には、quantum geometry はさまざまな関連相にも関与しており、特に multiband や flatband 系において、interaction と quantum geometry の interplay も量子幾何という分野のホットなトピックとなっている。

まず、quantum geometry がどのように interacting physics に入り込むかを考えてみよう。

まず従来の spontaneous symmetry breaking phase を考える。我々がよく知る自発的対称性の破れの相には、強磁性相（Ferromagnetism、FM）、反強磁性相（Antiferromagnetism、AFM）、電荷密度波（Charge Density Wave、CDW）、スピン密度波（Spin Density Wave、SDW）、超伝導相（Superconductivity、SC）がある。実のところ反強磁性相は、$\mathbf{Q}=(\pi,\pi,\pi)$ の一種のスピン密度波と見なすこともできる。

これらの相は従来の固体物理学において、特に単体 & Mean Field Theory に基づく理論によってよく説明される。ここでは統一的に議論しよう。各相はそれぞれ非零の order parameter $\langle \hat{\mathcal{O}} \rangle$ に対応する。

| 秩序 (Order)     | 秩序変数演算子 $\hat{O}$ (Schematic)                         | チャネル (Channel)      | スピノル基底 (Basis)      | 頂点 $\Gamma$ | 運動量移行 $Q$          | 破れた対称性 (Broken Sym.) |
| :-------------- | :-------------------------------------------------- | :---------------- | :--------------- | :---------- | :---------------- | :------------------ |
| **強磁性 (FM)**     | $\sum c^\dagger \sigma c$                           | Particle-Hole     | $c$              | $\sigma$    | $0$               | $SU(2)$ スピン回転        |
| **反強磁性/SDW**     | $\sum c^\dagger \sigma c_{k+Q}$                     | Particle-Hole     | $c$              | $\sigma$    | $Q \neq 0$        | $SU(2)$ + 並進 $T$    |
| **電荷密度波 (CDW)** | $\sum c^\dagger I c_{k+Q}$                          | Particle-Hole     | $c$              | $I$         | $Q \neq 0$        | 並進 $T$              |
| **超伝導 (SC)**     | $\sum c^\dagger_\uparrow c^\dagger_{\downarrow}$    | Particle-Particle | $(c, c^\dagger)$ | -           | $0$ (Pair)        | $U(1)$ ゲージ           |
| **対密度波 (PDW)** | $\sum c^\dagger_\uparrow c^\dagger_{\downarrow, Q}$ | Particle-Particle | $(c, c^\dagger)$ | -           | $Q \neq 0$ (Pair) | $U(1)$ + 並進 $T$     |

しかし従来の固体物理学の理論は非自明な波動関数を考慮しない。例えば超伝導は $\frac{\mathbf{p}^2}{2m}$ のような自由電子分散のみを考え、band system における異なる orbital mixing が非自明な波動関数を引き起こし、ひいては非自明な quantum geometry の影響をもたらしうることを考慮していない。こうなると、従来の単一バンド BCS の理論は、系の単体運動エネルギー（band width）を抑制した後（flat band limit）にはもはや適用できなくなる。

同様に CDW についても、従来派は主に単体レベルでの Fermi Surface Nesting を探すが、flat band limit に入った後はエネルギーがすべて等しい（少なくとも band width が interaction よりはるかに小さい）状況において、Fermi Surface を論じることはもはや合理的でなくなる。このとき有効な唯一の情報は、平坦バンド上の波動関数の「形」、すなわち quantum geometry なのである。

任意の秩序変数演算子 $\hat{\mathcal{O}}$（頂点行列 $\hat{\Gamma}$ によって定義される）に対して、その完全な静的分極率はエネルギー (Lindhard) と 幾何 (Form Factor) の二つの部分を含む。

$\chi_{\Gamma}(\mathbf{q}) = \frac{1}{N} \sum_{\mathbf{k}} \sum_{n, m} \underbrace{ \left| \langle u_{n\mathbf{k}} | \hat{\Gamma} | u_{m\mathbf{k}+\mathbf{q}} \rangle \right|^2 }_{\text{幾何因子 (Form Factor)} \mathcal{F}_{nm}} \times \underbrace{ \frac{f(\epsilon_{n\mathbf{k}}) - f(\epsilon_{m\mathbf{k}+\mathbf{q}})}{\epsilon_{m\mathbf{k}+\mathbf{q}} - \epsilon_{n\mathbf{k}}} }_{\text{エネルギー因子 (Lindhard)} \mathcal{L}_{nm}}$

* エネルギー因子 $\mathcal{L}_{nm}$：励起のエネルギーコストを決定する。通常の金属では、これがフェルミ面ネスティング (Fermi Surface Nesting) を与える。

* 幾何因子 $\mathcal{F}_{nm}$：遷移の選択則を決定する。エネルギー的に許容されても、波動関数が直交していれば遷移は禁止される。

平坦バンド極限 ($W \to 0$) においては、エネルギー因子は定数 $1/k_B T$ に退化し、物理は完全に幾何因子によって支配される。

分極率 (Lindhard Function) の中心となるエネルギー因子項は次のとおりである。
$L(\mathbf{k}, \mathbf{q}) = \frac{f(\epsilon_{\mathbf{k}}) - f(\epsilon_{\mathbf{k}+\mathbf{q}})}{\epsilon_{\mathbf{k}+\mathbf{q}} - \epsilon_{\mathbf{k}}}$

1. 平坦バンド極限 ($0/0$)：
   エネルギーバンドが平坦になると ($W \to 0$)、$\epsilon_{\mathbf{k}} \approx \epsilon_{\mathbf{k}+\mathbf{q}} \approx \mu$ となる。分母は 0 に近づき、分子も 0 に近づく。ロピタルの定理あるいはテイラー展開を用いると：
   $\lim_{\Delta E \to 0} \frac{f(E) - f(E+\Delta E)}{\Delta E} = - \frac{\partial f}{\partial E}$

2. フェルミ分布微分恒等式 (詳細な導出)：
   $x = \beta(E-\mu)$ とおくと、$f(E) = \frac{1}{e^x + 1}$ となる。

   * 微分：連鎖律を用いて
     $\frac{\partial f}{\partial E} = \frac{d f}{d x} \frac{\partial x}{\partial E} = \left( - \frac{e^x}{(e^x+1)^2} \right) \cdot \beta$

   * 項の整理：$f(1-f)$ を観察すると
     $1-f = 1 - \frac{1}{e^x+1} = \frac{e^x}{e^x+1}$
     $f(1-f) = \frac{1}{e^x+1} \cdot \frac{e^x}{e^x+1} = \frac{e^x}{(e^x+1)^2}$

   * 結論：上記二式を比較すると、ただちに次が得られる
     $- \frac{\partial f}{\partial E} = \beta f(1-f) = \frac{1}{k_B T} f(1-f)$

3. 最終結果：
   元の式に代入すると、平坦バンド極限における分極率が得られる。
   $\chi_0(\mathbf{q}) \approx \frac{1}{k_B T} \sum_{\mathbf{k}} \underbrace{ \nu(1-\nu) }_{\text{占有因子}} \underbrace{ \left| \langle u_{\mathbf{k}} | u_{\mathbf{k}+\mathbf{q}} \rangle \right|^2 }_{\text{幾何的畳み込み}}$

$\chi_{\Gamma}^{flat}(\mathbf{q}) \approx \underbrace{ \frac{1}{k_B T} }_{\text{Energy Part}} \times \underbrace{ \frac{1}{N} \sum_{\mathbf{k}} \text{Tr} \left[ \mathcal{F}_{\Gamma}(\mathbf{k}, \mathbf{q}) \right] }_{\text{Geometric Part}}$

ここで 幾何形状因子 は、平坦バンドへ射影した遷移行列要素の絶対値の二乗として定義される。

$\mathcal{F}_{\Gamma}(\mathbf{k}, \mathbf{q}) = \left| \langle u_{\mathbf{k}} | \hat{\Gamma} | u_{\mathbf{k}+\mathbf{q}} \rangle \right|^2$

* $|u_{\mathbf{k}}\rangle$: 軌道/副格子情報を含む周期的ブロッホ波動関数（スピノル）。

* $\hat{\Gamma}$: 秩序の種類を定義する頂点行列。

(i) Superfluidity Weight/Flatband Superconductivity

これは quantum geometric correlated phase の中では比較的初期の work であり、以下の paper を参照されたい。

> 🔗 *【link: Superfluidity Weight note】*

(ii) Quantum Geometric Magnetism

(iii) Electron-Phonon Coupling

主に Jiabin Yu の paper を参照されたい。

(iv) Fractional Chern Insulator/ Fractional Quantum Anomalous Hall

これは著者が最も早く触れた分野であり、本人の他の note を参照されたい。

> 🔗 *【link: Fractional Chern Insulator note】*

その本質を突き詰めれば、やはり Landau Level を模倣することにある。energy の層面で模倣する（平坦バンド）だけでなく、wavefunction（あるいは同等に、quantum geometry/topology）の層面でも模倣する必要がある。Chern band であるだけでなく、ブリルアンゾーンの至るところで quantum metric/Berry curvature が Landau Level に類似していなければならない。

Here、quantum geometry serves as the key ingredient to measure our deviation from the ideal Landau Level。そしてこれにより、Fractional state に関する多くの議論が発展してきたが、ここでは詳述しない。note や他の文献を参照されたい。

### 量子幾何情報エントロピー (Quantum Geometric Information Entropy)

最後に、視野を凝縮系の分野から量子情報の分野へと広げよう。我々は、quantum geometry が人々の quantum information への理解にとっても重要な助けとなることを見出すだろう。逆に、これらの量子幾何的な quantum information quantities を観測する助けにすらなりうる。

(i) Quantum Fisher information

quantum information においては、我々は純粋状態よりも density matrix を議論することが多い。したがって、量子幾何の概念を密度行列へと一般化する必要がある。そのために、密度行列の間の距離を同様に定義し、対応する距離をパラメータ展開すれば、quantum Fisher information (QFI) を得ることができる。

* 密度行列の固有基底 $\rho = \sum_n p_n |n\rangle\langle n|$ の下で、上記の方程式を解くことにより、QFI は非常に実用的なスペクトル分解の形で書くことができる。

$$
F_Q(\lambda) = 2 \sum_{n,m} \frac{(p_n - p_m)^2}{p_n + p_m} |\langle n | \partial_\lambda \rho | m \rangle|^2
$$

純粋状態への回帰：Quantum Metric との対応
この式は一見複雑に見えるが、純粋状態極限 ($T \to 0$)、すなわちある状態 $p_0=1$、その他 $p_{n \neq 0}=0$ を取ると、不思議なことが起こる。

1. 和の中で、$n=0, m\neq 0$ （あるいはその逆）のときのみ、分母 $p_n+p_m = 1 \neq 0$ となり、項が残る。
2. このとき係数は $\frac{(1-0)^2}{1+0} = 1$ となる。
3. $\partial_\lambda \rho = |\partial_\lambda \psi\rangle\langle\psi| + |\psi\rangle\langle\partial_\lambda \psi|$ を考慮すると、次を導くことができる。

$$
F_Q = 4 \left( \langle \partial_\lambda \psi | \partial_\lambda \psi \rangle - |\langle \psi | \partial_\lambda \psi \rangle|^2 \right)
$$

これはまさに Quantum Geometric Tensor の実部（Fubini-Study 計量）の 4 倍である。

$$
F_Q = 4 g_{\lambda\lambda}
$$

これは物理概念の統一性を完璧に示している。QFI は Quantum Metric の混合状態（有限温度）における自然な一般化であり、零温では我々のよく知る波動関数空間の幾何学的距離へと退化する。

これらの抽象的な幾何量は、**線形応答理論** を通じて実験的に測定可能な物理量と関係づけることができる。

* **Hauke 関係式 (2016)**
  熱平衡状態 $\rho \propto e^{-\beta H}$ に対して、上記のスペクトル分解公式を用いることで、QFI を系の虚部動的磁化率 $\chi''(\omega)$ と関係づけることができる。最新のレビューに整理された結論によれば、演算子 $\hat{h}$ によって生成されるパラメータ推定に対して、その QFI は次のとおりである。

  $$
  F_Q(T) = \frac{4}{\pi} \int_0^\infty d\omega \tanh\left(\frac{\hbar\omega}{2k_B T}\right) \chi''_{\hat{h}}(\omega, T)
  $$

  ここで $\chi''_{\hat{h}}(\omega)$ は演算子 $\hat{h}$ の動的応答スペクトルである。

(ii) Entanglement Entropy

Quantum Geometry は可観測な応答関数と関連するだけでなく、微視的な **エンタングルメントエントロピー (Entanglement Entropy)** とも深い関係を持つ。

* **相関行列と Renyi エントロピー**
  自由フェルミオン系に対して、部分系 $A$ のエンタングルメント特性は、相関行列 $C_{nm} = \langle c_n^\dagger c_m \rangle$ （あるいは重なり行列 $O$）によって完全に決定される。Renyi エンタングルメントエントロピー $S_A^{(\alpha)}$ は、相関行列の関数として直接表すことができる。

  $$
  S_A^{(\alpha)} = \frac{1}{1-\alpha} \text{Tr} \ln \det [p \mathbf{1} - C_A]
  $$

  相関行列は本質的に実空間における波動関数の重なりと距離を反映するため、これは Quantum Metric とエンタングルメントエントロピーの間に直接的な幾何学的対応関係が存在することを示唆している。

### おわりに

ここまで読んでくださった皆様に感謝する。更新が止まって二年近く、私は思いがけずイスラホールからアメリカへと移り、指導教員のおかげで凝縮系物理の方向で研鑽を続けることができ、感慨深い。

アメリカでの生活 & 学習 & 仕事 & 人間関係の面では多くの変化があり、私は今もゆっくりと適応しているところである。同時に研究も次第に深まり、それで note を書く時間もなくなってしまった。更新を待っている読者がいることも目にしていたのに、まじめな note を発表する場を自分の感情の発電場にしてしまい、本当に申し訳なく思う。

ここに至り、私の PhD 生涯もまもなく折り返し点を過ぎようとしている。お恥ずかしながら、私は今でもしばしば未来に対して迷いを感じる。quantum geometry に関する内容も、私が綿密に選んだものではなく、夏のインターン期間の気まぐれであり、もともと深く探究するつもりもなかったのに、今では私が最も深く理解する方向の一つになってしまった。多くの場合、私はこの方向を深く探究することに本当に意味があるのかどうかも分からない。多くの場合、知れば知るほど、かえって知らないことが増えていくのだ。

時間がなくて note を書けないと言ったが、時にはそれは、以前のようには純粋でなくなったからだと感じることもある。心の底からある方向に興味を持ち、そのためにすべてを顧みず探求できる――これが以前に知乎で note を書いていたときの心境であり、この一篇を書いているとき、私はまるで以前 note を書いていたときのあの純粋な感覚を取り戻したかのようだった。私はそれを続けていきたいと願うが、確信は持てない。

これからも新しい方向に挑戦したいと願う一方で、次第に力が及ばないとも感じている。私は学部生や低学年の大学院生たちをとても羨ましく思う。彼らは私ほど研究経験は豊富でないかもしれないが、その目にはまだ純粋な知識への渇望が満ちている。そして私は、その純粋さが大部分において若者の特権であることを知っている。私もしばしば数年前のあの純粋な状態に戻り、何の功利心もなく興味のある問題を考えたいと願う。しかし現実は往々にして、academia に残るために、我々は柔軟に方向を変えることができないのだ。もちろん、興味のある方向は育てることができる。いわゆる、知れば知るほど、擁護するようになる、というものだ。しかし純粋さへの内なる渇望は減ってはいない。あとどれだけの時間、純粋さを保っていられるのか、私には分からない。

おおよそ表紙の図に示されるとおり、芳しき青春を量子幾何に捧げ、これから先の道は一歩ずつ進んでいくほかない。

これまでの皆様のご支援に感謝する。縁があればまたお会いしましょう～
