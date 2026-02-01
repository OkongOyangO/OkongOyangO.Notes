---
title: "🤯分数量子ホール液体におけるカイラル重力子（Chiral Graviton）"
date: 2024-04-05T12:00:00+08:00
draft: false
math: true
tags: ["FQHE", "Graviton", "Metric", "Quantum Geometry"]
categories: ["Physics Notes"]
---

この記事は、分数量子ホール液体における「カイラル重力子（Chiral Graviton）」励起に関する理論と実験的検出方法を簡単に紹介し、最近の関連分野での熱い議論に「野次馬」的な素材を提供することを目的としています。筆者の能力には限りがありますので、専門家の皆様からのご指摘を歓迎します。

<!--more-->

## Introduction

最近、南京大学のLingjie Duの研究グループは、ドイツおよびアメリカの同僚と協力し、分数量子ホール（Fractional Quantum Hall, FQH）液体中の「カイラル重力子（Chiral Graviton）」励起の実験的検出に関する論文をNature誌に発表しました。その後、様々なメディアによって大きく取り上げられ、凝縮系物理学界の内外で、論文における「graviton（重力子）」という用語の使用や、凝縮系における様々な準粒子の命名規則について、一連の議論が巻き起こりました。

https://www.nature.com/articles/s41586-024-07201-w

この記事では、そうした論争に加わるつもりはありません。科学そのものに罪はなく、歪められるのは常に実行する人間だからです。そこで、この機会に関連する理論的および実験的知識を理解し、科学的な「野次馬」を楽しんでみましょう。

分数量子ホール効果などの前提となる内容については、私が数年前に書いたノートを参照してください：

https://zhuanlan.zhihu.com/p/574597173

量子幾何学（Quantum Geometry）についてですが、ここで言うQuantum Geometryは、異方的なmass tensorやCoulomb相互作用（Dielectric tensor）の下でのFQH基底状態波動関数の、Haldaneによって提案された新しい内因性の自由度を指します。これは、以前私が書いた、波動関数の特定のパラメータ空間（例えば運動量空間）で定義されるQuantum Geometryとは完全には同じではありません。

しかし、これら2種類のQuantum Geometryはどちらも、ここ数十年に現れた様々なトポロジカルな性質に加えて、量子状態の新しい性質——幾何学的性質とその応答の重要性を明らかにしています。後者に関しては、分数量子ホール効果やその非線形光学、輸送応答における発現は、最近の凝縮系物理学分野で比較的ホットな話題です。興味のある方は、以前のノートを参照するか、私の今後の更新を追ってください：

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

FQH波動関数の新しい内因性自由度としてHaldaneが提案したQuantum Geometryの話に戻りましょう。後の研究者たちは、このQuantum Geometryが単にFQH基底状態波動関数のパラメータを記述するだけでなく、動的なパラメータとしても見なせることを発見しました。これは、FQHにおける最も重要な集団的中性励起であるmagnetoroton励起の長波長極限でのダイナミクスに対応しています。この長波長極限でのmagnetoroton励起は観測が極めて困難であり、同時に内因性のQuantum Geometry Dynamicsに由来するという本質を持つため、凝縮系理論家たちはこの励起モードを「重力子（Graviton）」と呼ぶようになりました（一部の文献では依然として長波長極限でのmagnetorotonと呼んでいますが、それでは人目を引かず、研究費も取れませんからね（冗談です））。

これは明らかに、一般相対性理論において時空の計量（metric）の歪みが引き起こす重力波との類推であり、同時にこの励起がスピン2の特性を持つことから、場の量子論において重力を量子化した際に同様にスピン2を持つ重力子との類推でもあります。これは高エネルギー物理学の境界に触れているとも言えますし、凝縮系における重力子の概念の拡張と内包の豊かさを示しているとも言えます。結局のところ、ワイルフェルミオン（Weyl Fermion）やマヨラナフェルミオン（Majorana Fermion）など、元々は高エネルギー物理学の概念も相次いで凝縮系物理学の分野に導入されており、業界内ではすでに見慣れた光景となっています。

さらに、この重力子はカイラリティ（Chirality、手性）を持っています。例えば、$\nu = 1/3$ 充填のFQHでは、そのGraviton励起はスピン2を持つだけでなく、角運動量は-2となります。逆に、その粒子-正孔共役（particle-hole conjugate）である $\nu = 1 - 1/3$ 充填のFQH状態では、Graviton励起のスピン角運動量は2に変わります。このように異なる充填率のFQH状態がGravitonの角運動量を選択する性質（Selectivity）は、私たちがよく言うカイラリティと呼応しています。私たちはさらに、FQHにおける内因性Quantum Geometryダイナミクスに基づく長波長素励起を「カイラル重力子（Chiral Graviton）」と呼んでおり、これは南京大学の論文タイトルに見られる命名法でもあります。

## Anisotropic FQHE and Intrinsic Quantum Geometry

結局のところ、Gravitonの出現は、Haldaneが提案したIntrinsic Quantum Geometry of Anisotropic FQHEと切り離すことはできません。関連する詳細はHaldaneの原論文を参照してください：

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.116801

### Band and Dielectric Anisotropy: Galilean and Coulomb (Interaction) Metric

具体的には、Haldaneは一般的な磁場中のハミルトニアンに、band mass tensorおよびCoulomb potentialの異方性（anisotropy）を加え、Galiean metric $g^{ab}$ を用いました。
$$
H = H_0 + V 
$$
相互作用のない部分（Non-interacting）：
$$
H_0 = \frac{1}{2} (m^{-1})^{ab} \pi_a\pi_b =  \frac{1}{2m} g^{ab} \pi_a\pi_b,
\quad \bm \pi = \bm p - e\bm A,
$$
ここで、磁場によってもたらされる機械的運動量の非可換代数（non-commutative algebra）は以下の通りです。
$$
[r_i^a,\pi_{jb}]= i\delta_{ij}\hbar \delta^a_b, \quad 
[\pi_{ia},\pi_{jb}] = i\delta_{ij}\epsilon_{ab}\hbar^2/\ell_B^2.
$$
ここで、$\ell=\sqrt{\hbar/(eB)}$ は磁気長（magnetic length）です。

この非可換代数は、様々なゲージ選択の下で異なるLLL（最下ランダウ準位、Lowest Landau Level）の単一粒子波動関数を与えることができます。例えば、等方的な条件 $g^{ab} = \delta^{ab}$ および対称ゲージ（symmetric gauge）の下では、システムの回転対称性を保持できるため、LLL単一粒子波動関数は $H_0$ と角運動量 $L_z$ の同時固有状態となり得ます。このように構成されたLLL単一粒子波動関数およびそれに基づいて構築されたLaughlin多体波動関数は、いずれも回転対称となります。

しかし、Haldaneはより一般的な異方的なGalilean metric、すなわち $g^{ab}$ が等方的ではない場合を考慮しました。同時に、Haldaneはinteraction metric $\tilde g^{ab}$ によって特徴付けられる相互作用の異方性（interaction anisotropy）も考慮しました：
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
これら2種類の異方性は、それぞれband mass tensorとdielectric tensorの異方性に由来し、互いに独立した2つのmetricとなり得ます。以前私たちが考えていたFQHシステムでは、これら2つのmetricをデフォルトで等方的であると仮定していたため、得られる波動関数も等方的であり、波動関数自体に現れる可能性のある異方性やその内因的なintrinsic quantum geometryなどの情報を反映することができませんでした。

さて、band mass tensorとdielectric tensorの異方性を議論するために、等方的な場合と同様に異方的なLLL波動関数を構築する必要があります。この過程で、システム自体が持つ内因的な量子幾何学的自由度を発見することになります。

### Landau Level with Anosotropic Galilean metric

まず、異方的なLLL単一粒子波動関数の構築を考えましょう。これは完全に等方的な場合の拡張です。詳細は以下を参照してください：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.115308

具体的には、このときmass tensorの異方性のみを考慮すればよく、unimodularな複素ベクトル $\omega$ を用いてmass tensorをパラメータ化（parametrize）できます：
$$
m_{ab}=m (\omega_a^*\omega_b + \omega_b^*\omega_a)
$$
$$
(m^{-1})^{ab}=m^{-1}(\omega^{a*}\omega^b + \omega^{b*}\omega^a).
$$
等方的な特殊なケースは $\omega = \frac{1}{\sqrt{2}} (1, i)^T$ であることが容易にわかります。より一般的な $\omega$ は一般的な異方的なケースを表しており、これは両者の関係や前者から後者への類推と拡張を議論する際に重要です。

#### Construction of Landau Level and Guiding Center Ladder Operators

単一粒子ハミルトニアンは以下のように表せます：
$$
H_0 ={\textstyle \frac{1}{2}}\hbar \omega_c
\left( b^{\dagger}b + bb^{\dagger}\right)
$$
ここで $\hbar\omega_c = \hbar^2/m\ell^2$ はサイクロトロンエネルギーです。異方性条件下でのLandau Level ladder operators（昇降演算子）は以下のように拡張できます：
$$
b = \hbar^{-1}\ell \left (\bm \omega \cdot \bm \pi\right ),
\quad b^\dagger = \hbar^{-1}\ell \left (\bm \omega^* \cdot \bm \pi\right )
$$
ladder operatorは交換関係 $[b,b^{\dagger}] = 1$ を満たします。このladder operatorは、波動関数を異なるLandau Level間で昇降させるために使用され、昇降の前後でサイクロトロンエネルギー1つ分の差が生じます。

さらに、"guiding center"座標 ${\bm R}$ を導入します：
$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
“guiding center”座標演算子は以下を満たします：
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
"guiding center"座標 ${\bm R}$ は、"guiding center" ladder operators：$a$，$a^{\dagger}$ を生成するために使用されます：
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
この生成・消滅演算子の組は、Landau Level ladder operatorである $b$ および $b^{\dagger}$ と可換であり、したがって同一Landau Level内のLLL単一粒子波動関数の縮退（degeneracy）を記述することができます。これは等方的なLLの導出における古典的な操作と同じです。

注目すべきは、以上の議論が具体的なゲージを導入することなくLandau Levelとその縮退などの情報を得られるという点です。言い換えれば、LLL波動関数の構築において、回転対称性を保存するために対称ゲージを導入する必要はありません。これは、私たちがこれまでデフォルトとしていたQHおよびFQH状態の等方的な性質自体が偶発的（accidental）なものであったことを示しています。私たちは、FQH理論の自由度を構築するために異方的なLLL波動関数を選択する自由を完全に持っており、これは以前は無視されていました。

より詳細な導出については、UCSDのQHE関連ノートを参照してください：

https://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf

#### Introduction of Symmetric Gauge

さらに進んで、対称ゲージ（symmetric gauge）の下でも異方的なLLL波動関数を構築できることを示します。LLL波動関数はしばしばハミルトニアン $H_0$ と角運動量 $L_z$ の同時固有状態によって決定されますが、ここでは異方的な $L_z$ を構築することで、FQHを議論する基礎となる異なるLLL単一粒子波動関数を得ることができることを示します。

今、対称ゲージを選択します：
$$
{\bm A}={\textstyle\frac{1}{2}}{\bm B}\times{\bm r}={\textstyle\frac{1}{2}}B(-y,x),
$$
そして、mass tensorの異方性情報を含む $\omega$ を利用して複素座標（complex coordinate）を構築します：
$$
z = \frac{\bm \omega \cdot \bm r}{\ell}.
$$
等方的なmass tensorの特殊な場合では、
$$z = \frac{x+iy}{\sqrt{2}\ell}$$
となります。複素座標の下でのLandau Levelとguiding centerのladder operatorの表現を構築するのはお手の物ですが、任意の異方的なmass tensorの下でもこれが成立することは容易に証明できます。ここでは直接結論を示します：
$$
b = {\textstyle \frac{1}{2}}z + \partial_{z*} ,\quad  b^{\dagger} =
{\textstyle \frac{1}{2}}z^* - \partial_{z}
$$
$$
a = {\textstyle \frac{1}{2}}z^* + \partial_{z} ,\quad  a^{\dagger} =
{\textstyle \frac{1}{2}}z - \partial_{z^*}
$$
対応する角運動量演算子は次のように定義できます：
$$L_0 = a^{\dagger}a - b^{\dagger}b, \quad [L_0,H_0] =0$$
$H_0$ と $L_0$ を同時対角化することで、n番目のLLの単一粒子波動関数 $|\psi_{nm}\rangle$ が得られます：
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
以上のプロセスは、単に $\omega = \frac{1}{\sqrt{2}} (1,i)^T$ を任意のunimodular vectorに拡張しただけであり、一般的なGalilean metricに対しても、システムの「回転対称性」を生成するanisotropic mass tensor adapted angular momentum operatorを構築できることを示しています。これは楕円を引き伸ばして円にするようなもので、ある程度は等方的ですが、それは異方的なmass tensorを除いて（up to a anisotropic mass tensor）の話です。

### Intrinsic Quantum Geometry of FQH state: Guiding Center Metric

しかし、これはGalilean metricがシステムが「好んで」選択する異方性の方向であることを意味するのでしょうか？いいえ。$L_0$ の定義を修正する（つまりGuiding center Metricの自由度を修正する）ことで、相互作用やCoulomb metricを導入する前であっても、波動関数の選択には依然として内因的なquantum geometryの自由度が存在することを示すことができます。

私たちのGuiding Center $R$、およびそのladder operator $a,\,a^\dagger$ は、統一されたLL内の縮退状態（degenerate state）を特定するために構築されました。しかし、量子力学の初歩で学ぶように、縮退状態の完全基底の選び方は一意ではありません。この基底の組に対してユニタリ変換を行い、新しい完全基底の組を得ることは完全に可能です。Guiding Centerの文脈で、以前のGuiding Center Ladder Operatorの構築を思い出してみましょう：

$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
“guiding center”座標演算子は以下を満たします：
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
"guiding center" ladder operators：$a$，$a^{\dagger}$ の構築：
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
ここで、Guiding centerのladder operatorを定義するために、Galilean Metricで定義されたunimodular vector $\omega$ を先入観を持って使用してしまったことに気づくのは難しくありません。しかし、前述のように、この基底の組に対してユニタリ変換を行い、新しい完全基底の組を得ることは完全に可能です。相互作用のない（noninteracting）状況下ではこれは全く問題ありません。現在のシステムには、Galilean metricをその内因的（intrinsic）な性質として特定する理由はありません。逆に言えば、この完全基底選択の不確定性は、LLL単一粒子波動関数を構築するための新しい自由度、すなわちGuiding Center Metricの自由度を私たちに与えてくれます。これは後に、FQHでよく議論されるIntrinsic Quantum Geometric自由度へと発展します（metricとgeometryはしばしば不可分です）。

RZ Qiu, FDM Haldane, X Wan, K Yang, S Yiらによる論文「Model Anisotropic quantum Hall states」では、次のように説明されています：

まず角運動量演算子を分割します：
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
$L_0 = L + \bar L$ の中の $L$ はすでに $H_0$ と可換であるため、$L_0$ の非自明な部分（nontrivial part）は $\bar L$ に由来することがわかります。

すると、元々定義していた $H_0$ と $\bar L$ の同時固有状態によって、n番目のLLのm番目の縮退波動関数を決定できます。
$$
\bar L |\psi_{nm} \rangle =
(m+{\textstyle\frac{1}{2}})|\psi_{nm}\rangle
$$
上記の議論でGalilean metricがどのように「先入観を持って」Guiding center Degeneracy自由度の構築に入り込んだかを表現するために、$\bar L$ を次のように書くことができます：
$$
\bar L = \bar L(g^0)
$$
そして、任意のguiding center metricの下での $\bar L$ を定義します：
$$
\bar L(g) =  \frac{1}{2\ell^2}g_{ab}R^aR^b
$$
ここで、band mass tensorに由来する "Galilean metric" を $g^0_{ab}$ と記し、その特殊性を反映させます。同時に、unimodular vector $\bar \omega$ を用いて任意のguiding center metricを定義します。

任意のguiding center metricの下での $\bar L$ に対して：
$$
m_{ab}=m(\omega^*_a\omega_b+\omega^*_b\omega_a)=mg^0_{ab}.
$$
同様に、$\bar \omega$ を用いて任意のguiding center metricをパラメータ化できます：
$$
g_{ab} = \bar \omega^*_a \bar \omega_b+ \bar \omega^*_b \bar \omega_a.
$$
これは、"guiding center" ladder operators：$a$，$a^{\dagger}$ を構築する際に以下を選択したことに相当します：
$$
a=\ell^{-1}\left(\bar {\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left( \bar {\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
$\omega$ から任意の $\bar \omega$ へ、あるいは等価的に $g_0^{ab}$ から任意のguiding center metric $g^{ab}$ への変更は、LL内の縮退を区別するためのladder operatorに対してBogoliubov変換を行ったことに相当します。これは、LLの縮退を記述する完全基底自体は依然として完全であることを示しており、単に、より自然的で、より任意性があり、Galilean metricによって「先入観を持って」選ばれていない別の基底の組に取り替えただけです。

これはnoninteractingの文脈では合理的です。その後、相互作用とCoulomb metricを導入すると、この任意のguiding center metric/Intrinsic Quantum Geometryは多体波動関数の変分パラメータとなり、システムはエネルギーがより低いguiding center metricで構成されるLaughlin状態などの多体波動関数を選択する傾向があります。

guiding center metric $\bar \omega_a$ と元のGalilean metric $\omega$ の違いを区別するために、RZ Qiu, FDM Haldane, X Wan, K Yang, S Yiらはさらに、両者の違いをパラメータ化するために複素数 $\gamma$ を導入しました。

このパラメータは $|\gamma| < 1$ を満たし、その物理的意味は離心率に似ており、Galilean metricを除いた（up to a Galilean metric）異方性を定義するために使用されます。この点は、後の単一粒子波動関数の特徴に見出すことができます。

具体的には、$\gamma$ によってパラメータ化されたguiding center metricはさらに次のように表すことができます。
$$
\bar \omega_a = (1-|\gamma|^2)^{-1/2}(\omega_a + \gamma^* \omega_a^*),
$$
これはunimodular metric $g_{ab}(\gamma)$ を決定します。
$$
\begin{aligned}
g_{ab}(\gamma) & = \bar \omega_a^*\bar \omega_b+\bar \omega_a\bar \omega_b^* \\
& = \frac{1}{1-\gamma^*\gamma}\left(\begin{array}{cc}
(1+\gamma)(1+\gamma^*) & i(\gamma-\gamma^*)\\
i(\gamma-\gamma^*) & (1-\gamma)(1-\gamma^*) \\
\end{array}\right)\nonumber
\end{aligned}
$$
これによって定義される新しい "guiding center" ladder operatorsの組は：
$$
a_\gamma =\frac{{\bar {\bm\omega}^*}\cdot{\bm R}}{\sqrt{2}\ell} ,\quad
 a_\gamma^\dagger =
\frac{{\bar {\bm\omega}}\cdot{\bm R}}{\sqrt{2}\ell}
$$
これは確かに以前述べたBogoliubov変換です：
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
これは、Galilean metricから一般的なguiding center metricへの選択が、単にLLの縮退に対する新しい完全基底の選択に過ぎないことを示しています。

同様に構成されたLL単一粒子波動関数は以下の通りです：
$$
|\psi_{nm}(\gamma)\rangle
=\frac{(b^\dag)^n(a^{\dagger}_{\gamma})^m}{\sqrt{n!m!}}
|\psi_{00}(\gamma)\rangle
$$
ここで $|\psi_{00}(\gamma)\rangle$ は、他のLLL縮退波動関数を生成するために使用されるLLL単一粒子波動関数の基底であり、以下を満たします：
$$
a_{\gamma}|\psi_{00}(\gamma)\rangle =
b|\psi_{00}(\gamma)\rangle  = 0.
$$
その後、guiding center metricを変分パラメータとして含むLaughlinやMRなどの多体波動関数の構築を容易にするために、任意のguiding center metricの下でのLLL単一粒子波動関数を同様に定義できます。ここでは詳細は省略しますので、具体的には原論文を参照してください。

要するに、LL単一粒子波動関数を構築する過程で、システムのguiding center metricによって定義される新しい自由度を発見しました。Galilean metricのみが存在する場合、すなわち相互作用がない場合、その選択は任意です。本質的に、この新しい自由度はLL内部の縮退した完全基底の選択の自由に由来します。相互作用を導入し、LaughlinやMRなどの多体波動関数を構築する過程で、このFQH状態におけるIntrinsic Quantum Geometryの自由度は変分パラメータとなり、より一般的な異方的なGalilean metricおよびinteraction metricの中で、システムおよび状態のエネルギーを最小にするguiding center metric/Intrinsic Quantum Geometryを選択します。

このプロセスは「Compromise of Intrinsic Geometry between Galilean and Coulomb Metric（Galilean metricとCoulomb metricの間の内因的幾何学の妥協）」とも記述されます。次の節では、相互作用を導入した後のIntrinsic Geometryの選択について議論します。

### Compromise of Intrinsic Geometry between Galilean and Coulomb Metric

前述のように、相互作用を導入した後、ハミルトニアンは以下のようになります：
$$
H=T+V,
$$
運動エネルギーにはGalilean metricが含まれており、これがanisotropy QH/FQH状態の起源の一つです。一般的には次のように書かれます：
$$
T=\frac{1}{2}(m^{-1})^{\mu\nu}\Pi_{\mu}\Pi_{\nu} = \frac{g^{\mu\nu}\Pi_{\mu}\Pi_{\nu}}{2m},
$$
簡単のために、基底を再定義（redefining basis）することで、次のようにも書けます：
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
このようにすると $a=1$ は等方的な場合に退化し、一般的な $a$ は一般的な異方的なGalilean metricの選択を表します。これは以下のGalilean metricを選択したことに相当します：
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
同様に、機械的運動量とguiding center座標の定義は以下の通りです：
$$
{\bf \Pi}={\bf p}+{e\over c}{\bf A}({\bf r})
$$
$$
{\bf R}={\bf r}-(\ell^2/\hbar)\hat{z}\times{\bf \Pi}
$$
二体相互作用を考えると、その実空間および運動量空間での表現は以下の通りです：
$$
V=\sum_{i < j} V({\bf r}_i-{\bf r}_j)=\frac{1}{2}\sum_{\bf q}V_{\bf q}\rho_{\bf q}\rho_{-{\bf q}},
$$
ここで運動量空間の密度演算子は：
$$
\rho_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf r}_i}
$$
一般的には、異方的な $\tilde g^{ab}$ によって特徴付けられるinteraction anisotropyも存在します：
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
これら2種類の異方性（band mass tensorとdielectric tensorの異方性）は、相互に独立した2つのmetricとなり得ます。簡単のために、anisotropic band mass tensor + isotropic Coulomb interactionの場合のみを考えることができます。なぜなら、私たちの主な目的は、相互作用を加えた後にguiding center metricがどのようにしてより低いエネルギーの基底状態を選択するかを見ることだからです。これにより、noninteracting問題におけるarbitraryなguiding center metricの選択が、interacting問題におけるFQH多体状態のintrinsic property（内因的性質）へと変化します。

#### Projected Interaction

モデルを簡略化するために、磁場が非常に大きく、LL間の分裂 $\hbar \omega_c$ がinteraction scale $e^2/a$ よりもはるかに大きい場合を考えます。これにより、波動関数は基本的にhigher landau levelに入らないと見なすことができ、問題全体をLLLに射影（project）して議論することができます。これは分数チャーン絶縁体を議論する際の慣用的な操作でもあります。興味のある方は以下を参照してください：

https://zhuanlan.zhihu.com/p/574597173

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

具体的な詳細は以下を参照してください：

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.241105

具体的には、一般的なLL基底の下での相互作用は次のように表すことができます：
$$
\tilde{V}=\sum_{i < j}\sum_{\bf q}v_{\bf q} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}F_n({\bf q}, a),
$$
ここでの係数は：
$$
F_n({\bf q}, a)=|\langle n|e^{i{\bf q}\cdot(\hat{z}\times{\bf \Pi})}|n\rangle|^2 = e^{-(aq_x^2+q_y^2/a)\ell^2/2}|L_n[(aq_x^2+q_y^2/a)\ell^2/2]|^2
$$
LLL projected interactionの場合、その係数は：
$$
F_0({\bf q}, a)=e^{-(aq_x^2+q_y^2/a)\ell^2/2}.
$$
LLL projected interactionは次のようになります：
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
ここでLLL projected density operatorは：
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
これが満たすGMP代数も、分数チャーン絶縁体の構築における重要な要素です。しかしここではLLL projected interactionの形式に注目します。元のCoulomb相互作用は等方的ですが、LLL波動関数の構築時にGalilean metricの異方性が存在するため、band mass tensorの異方性がprojected interactionの異方性に入り込んでいるのがわかります。LLLの単一粒子エネルギーは常に同じであるため、私たちはLLL projected interactionのみを考慮し、どの波動関数がそのエネルギーを最小にするか（変分法）を考えればよいのです。

#### Gaussian Interaction

これほど多くの簡略化を行っても、一般形式の相互作用を解析的に計算するのは困難です。さらに特殊なケースとして、Coulombポテンシャルがガウス関数（Gaussian function）である場合を考えます。これは、遮蔽されたCoulomb相互作用（screened Coulomb interaction）の特徴を大まかに記述しています。

等方的な相互作用は $V_q$ の係数分布の等方性に反映されます：$v({\bf r})=v(r)$，$v_{\bf q}=v_q$.

さらにGaussian Interactionを考えます：
$$
v(r)=v(0)e^{-r^2/(2s^2)}
$$
したがって、運動量空間での相互作用もGaussian形式になります：
$$
v_q=v_0e^{-q^2s^2/2}
$$
さらに次のように書けます：
$$
\tilde{V}_g=\sum_{i < j}\sum_{\bf q}v_0 e^{-\tilde{q}^2\tilde{s}^2/2} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}
$$
ここで
$$
\tilde{s}=[(a\ell^2+s^2)(\ell^2/a+s^2)]^{1/4}
$$
$$
\tilde{q}^2=g q_x^2 + q_y^2/g,
$$
$$
g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}.
$$
以上のステップは単純な数学的導出ですが、ここで定義された $g$ が前のセクションで議論したguiding center metricの異方性と直接関連していることが後でわかります。さらに、この特殊なGaussian Interactionの下では、$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$ が相互作用問題において多体基底状態波動関数のエネルギーを最小にするguiding center metricの選択を直接与えます。

まず、ここでのgのいくつかの性質を見てみましょう：

$g\rightarrow a$ for $s\ll \ell$, $g\rightarrow 1$ for $s\gg \ell$

同時に、一般的に以下が成り立ちます：
$$
1 < g < a
$$
実際、下限1は等方的なinteraction metricを反映し、上限 $a$ は異方的なmass tensor metricを反映しています。もし、$g$ が最適な基底状態選択のintrinsic quantum geometryの異方性情報であるという以前の主張を認めるなら、この不等式は確かにこのセクションの冒頭の議論を反映しています：

Intrinsic Geometry as a Compromise between Galilean and Coulomb Metric.

#### Many-Body Ground State of Anisotropic FQHE

以下では、いくつかの議論を通じて、$g$ とFQH状態のIntrinsic quantum geometry/guiding center metricとの関連を証明し、なぜ $g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$ がLaughlinなどの多体波動関数の変分パラメータの最適な選択であるのかを説明します。

まず、一般的な $g$ と $g=1$ の特殊なケースの関連を確立できます：
$$
\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)],
$$
ここで：
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
このguiding centerが等方的から異方的へと変化する過程は、以前に異なるguiding center metricを選択してguiding center operatorを構築し、それによってLL内部の完全な縮退基底の組を構築した操作と一致しています。これは $g$ とFQH状態のIntrinsic quantum geometry/guiding center metricとの関連を説明しています。

さらに、$g=1$ が等方的な特殊なケースであることを知っており、このときInteraction LLLの下での基底状態がLaughlin State（厳密にはLaughlin Stateは2体Haldane Pseudopotentialの下でのみ厳密な基底状態ですが、Gaussian interactionの下でもLaughlin stateは依然としてFQH基底状態に近いと仮定します）であることを熟知しています。したがって、$\tilde{V}_{g=1}$ の基底状態（運動エネルギーは無視できる）は $|\Psi_{GS,g=1}\rangle \approx |\Psi_{Laughlin} \rangle$ となります。

したがって、変換後の $\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)]$ の基底状態は、おおよそ次のように考えられます（ハミルトニアンがユニタリ変換一つ分異なるだけで、エネルギースペクトルは変化せず、基底状態を含む対応する波動関数も同じユニタリ変換一つ分異なるだけであるはずです）：
$$
|\Psi_{GS,g}\rangle=O^\dagger[\lambda(g)]|\Psi_{g=1}\rangle \approx O^\dagger[\lambda(g)] |\Psi_{Laughlin} \rangle =|\Psi^{Laughlin}_{g}\rangle
$$
これに加えて、$g$ がシステムのguiding center metric anisotropyの情報を表しているという点を合わせると、$|\Psi^{Laughlin}_{g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}}\rangle$ は、anisotropic mass tensor + isotropic gaussian interactionの下で、guiding center metric anisotropy/Intrinsic quantum geometryを変分パラメータとする、より一般的なLaughlin波動関数の最適な変分基底状態解であると考えることができます。

したがって、$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)} \in (1,a)$ は、異なる相互作用の下でのFQHのIntrinsic Geometryの決定（determination）を完全に反映しています。定性的には、やはりこのセクションの冒頭の議論通りです：

Intrinsic Geometry as a Compromise between Galilean and Coulomb Metric

ここまでで、FQH内部のIntrinsic Quantum Geometry自由度の起源と、そのdetermination from a variational Compromise between Galilean and Coulomb Metricについて説明しました。これは、回転対称性を破るシステムにおいても、異方的なFQH状態が依然として基底状態になり得ることを示しています。さらにIntrinsic Quantum Geometry自由度と結合する摂動を考慮すれば、このIntrinsic Quantum Geometryのダイナミクスに注目することができます。これがまさに南京大学が発見したchiral graviton modeなのです。

## Dynamics of Intrinsic Quantum Geometry as Chiral Graviton

次に、FQH状態におけるIntrinsic Quantum Geometryのダイナミクスと、その準粒子励起であるChiral Gravitonについて考えます。

### Dynamics of Intrinsic Quantum Geometry

最も直接的なアイデアは、Intrinsic Quantum Geometryと直接結合（couple）する摂動を見つけることですが、これは一般に実現が困難です。モデルにおいて比較的容易に直接coupleできる自由度はband mass tensorです。例えば、音響波（acoustic wave）を利用してFQHのバックグラウンド格子系を摂動させることができます。上記で議論したGaussian Interactionの下でのIntrinsic Quantum Geometry determined by band mass tensor anisotropyの描像が、より一般的な状況下でも実行可能（feasible）であると仮定しましょう。すると、band mass tensorをcoupleすることは、間接的にIntrinsic Quantum Geometryをcoupleすることに相当すると考えられます。

簡単のために、引き続き運動エネルギーを採用します：
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
これは以下のGalilean metricを選択したことに相当します：
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
再び一般的なLLL projected interactionを考えます：
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
音響波を通じてband mass anisotropyに対して時間依存の摂動を与えたと仮定します：
$$
a=1+\xi(t)
$$
これは $g = g(a)$ を通じて振動する（oscillating）metricとして現れます。振動するmetricの物理的描像は重力波（gravitational wave）であることを私たちは知っています。したがって、振動するmetricによって励起される準粒子は、高エネルギー物理学で議論されるgravitonと類似の性質を持つ可能性が高いです。

$a=1+\xi(t)$ に基づいて $\tilde{V}$ を摂動展開します：
$$
\delta\tilde{V}(t)=\frac{\xi(t)}{4}\sum_{\bf q}(q^2_y - q^2_x)V_{\bf
q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf q}\overline{\rho}_{-{\bf q}}.
$$
$(q^2_y - q^2_x)$ の部分が確かにd波の対称性を持っていることがわかります。これは、振動するmetricによって励起される準粒子がスピン2の準粒子である可能性が高いことを示しています。これは高エネルギー物理学で広く信じられているgravitonのスピン2の性質と「奇しくも一致」しています（本質的には、両者ともmetric場の振動であり、その量子が類似の性質を持つことは想像に難くありません）。

時間調和摂動（time-harmonic perturbation）の場合、実験的に測定されるスペクトル関数は、よく知られたフェルミの黄金律（Fermi Golden Rule）を通じて容易に得られます：
$$
I(\omega)=\sum_n|\langle n|\hat{O}|0\rangle|^2\delta(\omega-\omega_n),
$$
ここで摂動演算子は：
$$
\hat{O}=\sum_{\bf q}(q^2_y - q^2_x)V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}}
$$
この摂動演算子をさらに $S_z = \pm 2$ の形式に分割できます：
$$
\hat{O}_\mp^{(2)}=\sum_{\bf q}(q_x \mp i q_y)^2 V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
これら2つの演算子はそれぞれスピン $S_z = \pm2$ のgraviton励起を反映しており、対応するスペクトルは以下の通りです：
$$
I_\sigma(\omega)=\sum_n|\langle n|\hat{O} _{\sigma}|0\rangle|^2\delta(\omega-\omega_n),
$$
ここで、$\hat{O}_\mp$ はgravitonの生成・消滅演算子と見なすことができます。ここでは、生成される準粒子励起が $S_z = -2$ のみであると特定（specify）していることに相当するため、このgraviton励起はカイラル重力子（Chiral Graviton）とも呼ばれます。この選択の由来については後で説明します。逆に、粒子-正孔共役（particle-hole conjugate）なFQH状態の場合、graviton励起のスピンは逆になり、これがさらにそのカイラル（Chiral）な特性を反映しています。

そして $\hat{O}=(\hat{O} _{+} + \hat{O} _{-})/2$ は、調和振動子における変位演算子（displacement operator）に相当し、摂動演算子として「重力波」（本質的には音響波によって誘起された振動するmass tensor anisotropy）と結合します。

### Chirality of Graviton

なぜGravitonの励起はカイラルなのでしょうか？ $\nu = 1/3$ のLaughlin stateを例にとって分析してみましょう。$\hat{O}_\mp$ が2粒子波動関数に作用するとき、次のようになることは容易にわかります。
$$
O_{+} \propto \sum\limits_{M} |m+2, M \rangle \langle m, M|
$$
$$
O_{-} \propto \sum\limits_{M} |m, M \rangle \langle m + 2, M|$$
ここで $|m, M \rangle$ の中の $m$ と $M$ はそれぞれ、2粒子波動関数状態の相対角運動量（relative angular momentum）と重心角運動量（center-of-mass angular momentum）を表しています。

$\hat{O}_{+}$ がLaughlin stateを消滅させることは容易にわかります。なぜなら、$\hat{O}_{+}$ は相対角運動量 $m$ の2粒子状態を相対角運動量 $m+2$ に変化させますが、これはLaughlin state内には存在しないため、Laughlin stateを消滅（annihilate）させるからです。

したがって、$I _{+}(\omega)$ スペクトルは常に0です。一方、$I _{-}(\omega)$ はフェルミオンおよびボソンの場合において常に強いgravitonピークを示します。これは、$\nu = 1/3$ のLaughlin stateのgraviton励起が常に $S_z  =-2$ であることを示しています。逆に、そのPH共役である $\nu = 1 - 1/3$ の正孔Laughlin stateのgraviton励起は常に $S_z  = 2$ となり、これがgraviton励起のカイラリティを体現しています。

### Inaccessibility of normal Magnetoroton modes

本質的に、graviton modeは私たちがFQHで議論する中性集団励起：$k\rightarrow 0$ の極限におけるGMP magnetoroton modeです。言い換えれば、長波長極限において、FQHのダイナミクスは上記で議論したIntrinsic Quantum Geometryのダイナミクスによって決定されます。場合によっては、chiral graviton modeは長波長極限におけるGMP magnetoroton modeの特殊なケースとも呼ばれます。しかし、長波長極限では、GMP magnetoroton modeの構造因子（structural factor）が $\langle 0|\rho_{{\bf k}}\rho_{-{\bf k}}|0\rangle\propto (k\ell)^4$ となるため、一般的な電磁場と電子密度を結合させる方法を用いて長波長極限のGMP magnetoroton modeを検出することは困難です。GMP magnetorotonの詳細については、私の以前のノートも参照できます：

https://zhuanlan.zhihu.com/p/574597173

とにかく、上述の理由により、GMP magnetoroton modeは実験ですでに観測されていますが、その長波長極限の検出は困難です。一般的な電磁場摂動は、光子のスピンが1であるため、スピン2のgravitonと結合することが難しく、通常の方法は機能しません。こうして、Intrinsic Quantum Geometry起源および実験的検出におけるgraviton modeの特殊性は、一般的なGMP magnetoroton modeとは一線を画すものとなり、その検出は凝縮系物理学の分野において非常に意義深い出来事となりました。

### Detection of Chiral Graviton in FQHE

上述の音響波による方法以外に、南京大学がgravitonを検出した方法は、円偏光（circular polarized light）に関連する分光法を利用したものです。円偏光は $S_z = \pm1$ のスピンを持つため、もし $S_z = -1$ の円偏光を用いて $S_z = -2$ のchiral gravitonを励起した場合、システムが吸収した後に放出される光は $S_z = 1$ となるはずです。この原理を通じて、南京大学のLingjie Duの研究グループとそのドイツ・アメリカの同僚たちは、FQHEにおけるchiral graviton modeの発見に成功し、Nature誌に発表しました。これが私たちがよく知るストーリーです。

## Relation with Band Geometry from Momentum-Space Duality

上述の過程で議論したFQH状態のIntrinsic Quantum Geometryは、分数チャーン絶縁体、平坦バンド超伝導、非線形応答などでよく議論されるBand Geometryとは定義上異なりますが、両者の計量場（metric field）の本質は一致しています。このようなFQH状態の幾何学的記述（Geometric Description）という考え方は、Band Geometryを議論する分数チャーン絶縁体などの系にも導入されており、格子系におけるFQH状態の安定性やその他の性質に関する洞察（insights）を提供しています。

例えば、Claassen, M., Lee, C. H., Thomale, R., Qi, X. L., & Devereaux, T. P.らによる2015年の「Position-momentum duality and fractional quantum hall effect in chern insulators」と題されたPRL論文では、Band GeometryとFQH状態のIntrinsic Quantum Geometryとの関連が議論されています。

具体的には、Band Systemにおいて、波動関数空間（Projected Hilbert Space $\mathbb{C}P^{N-1}$）のシンプレクティック幾何学があり、その虚部は私たちがよく知るベリー曲率（Berry Curvature）で、運動量空間の磁場に似ています：
$$
\Omega(k) = \epsilon^{\mu\nu} \partial_{k_\mu} \mathbf{A}_\nu(k)
$$
これは運動量空間のベクトルポテンシャル、ベリー接続（Berry Connection）に由来します：
$$
\mathbf{A}_\nu(k) = -i \langle u_k | \partial_{k_\nu} | u_k \rangle
$$
一方、シンプレクティック幾何学の実部は波動関数空間の計量、すなわちFubini-Study計量を定義します
$$
g_{\mu\nu}(k) = \frac{1}{2} \langle \partial_{k_\mu} u_k | \left[1 - |u_k\rangle \langle u_k | \right] | \partial_{k_\nu} u_k \rangle + \left(\mu \leftrightarrow \nu \right)
$$
FQHにおいて角運動量演算子によってLLL内の縮退を区別したのと同様の方法を用いて、ハミルトニアンの固有状態と一致するような閉じ込めポテンシャル（confinement potential）を同様に定義することができ、それによって回転対称性を破った格子系において「擬角運動量演算子」を定義する目的を達成できます：
$$
\hat{V}(r)= \tfrac{1}{2} \lambda~ x_{\mu} \eta^{\mu\nu} x_{\nu}
$$
$\eta^{\mu\nu}$ は、回転対称性を破った格子系において「擬角運動量演算子」を定義するために用いられるmetricを記述することができ、これはLattice SystemにおけるGuiding Center Metricの類似物（analogy）、すなわちIntrinsic Quantum GeometryのLattice versionです。

同様にLLLへの射影を考えると、この単一粒子「擬角運動量演算子」（本質的には人工的な閉じ込めポテンシャル）の射影は以下のようになります：
$$
\bar{V} =  \hat P\hat V(r)\hat P^\top= \frac{\lambda}{2} \Pi_\mu \eta^{\mu\nu} \Pi_\nu + \frac{\lambda}{2} \eta^{\mu\nu} g_{\nu\mu},\,k \in {\rm BZ}
$$
右側の第一項は私たちがよく目にする運動エネルギー演算子ですが、それに加えてBand Geometryと結合する項があります。これは、Lattice SystemにおけるFQH物理が、連続系（continuum system）におけるFQH物理と比較して、Band Geometryの影響も受けていることを示しており、両者の結合（Coupling）がより一般的な系におけるFQHのIntrinsic Quantum Geometryの物理を与えます。関連する詳細は原論文をさらに参照してください：

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.114.236802

ここではこれ以上深入りせず、Intrinsic Quantum GeometryとBand Geometryの関連を示すにとどめます。

## Summary

以上のように、最近話題の「南京大学が（FQH系において）（カイラル）重力子（の準粒子励起）を発見した」というニュースについて議論し、FQH状態におけるIntrinsic Quantum Geometryの由来を示し、そのダイナミクスの準粒子に対応するChiral Graviton modeの由来について議論しました。また、その検出や私たちがよく知るBand Geometryとの関連についても簡単に議論しました。皆様に科学的な「野次馬」素材を提供できたなら幸いです。

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