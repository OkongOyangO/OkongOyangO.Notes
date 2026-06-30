---
title: "😮QHE(4)｜量子ホール効果からトポロジカル絶縁体、Chern-Simons理論とトポロジカル分類へ"
date: 2022-06-10T10:00:00+08:00
draft: false
math: true
tags: ["IQHE", "Topological Insulator", "Chern-Simons", "Berry Phase", "Condensed Matter"]
categories: ["Physics Notes"]
---

凝縮系理論におけるトポロジーに触れてからすでに一年が経ち、断片的に多くの文献を読んできた。以下ではそれらを整理し、今後この分野に取り組むかもしれない読者のために、学習過程における主な流れを明確にしたいと思う。

整数量子ホール効果は凝縮系に新たな分野を切り開いた。しかし、これは凝縮系におけるトポロジーの氷山の一角に過ぎない。IQHEは実際には**二次元、ギャップ有り、相互作用無し、フェルミオン系、時間反転対称性（TRS）無し、粒子-正孔対称性（PHS、あるいは電荷共役対称性）無し、カイラル対称性無し**の系におけるトポロジカル効果であることがわかるだろう。

<!--more-->

実際、上記の修飾語【次元】【ギャップの有無】【相互作用の有無】【フェルミ/ボース】【時間反転対称性】【粒子-正孔対称性】【カイラル対称性】を置き換えることで、非常に豊かなトポロジカル効果が得られる可能性があり、そのため一部の系におけるトポロジカル分類の研究は今なお最先端のホットトピックである。

学び始めの頃、我々は様々な量子ホール効果の組み合わせ命名に興味を持つことが多い。例えば（整数）量子ホール効果、量子スピンホール効果、量子異常ホール効果などの現象である。しかし実際には、上記の次元や対称性などの修飾語に基づく分類の方がより普遍的である。

Prof. Zhaihui（翟薈）が講義で言っていたように：「物理学をterminologyとして学んではならない。これらのtermの背後にある物理にもっと注目すべきである。」

## Reference

まず、私が参考にした資料をここに列挙する。私の限られた理解力に基づき、大まかな難易度分類を行った。読者の資料選びの一助となれば幸いである。

全体的に、この部分の学習は段階的に進めると同時に、複数の資料を並行して読み、資料に対するマンネリ化を避けることをお勧めする。

知乎（Zhihu）にも多くの大御所がノートやレビューを提供している。ここでは私の限られた検索能力で見つけた、比較的親しみやすく刺激的な記事をいくつか挙げる。

@Boltzlinn の論文ガイド：

https://zhuanlan.zhihu.com/p/61559924

@拉格朗日（ラグランジュ）の記事：

https://zhuanlan.zhihu.com/p/77270930

まず最初に推薦するのは、SITPにおけるProf. SC Zhangのトポロジカル絶縁体に関する講演である。B站（Bilibili）に字幕があり、YouTubeのSITP公式アカウントにも完全版がある。Prof. SC Zhangはわかりやすい言葉で、様々な専門分野の研究者にトポロジカル絶縁体の物理と応用の展望を説明しており、この分野に初めて触れる読者にとって非常に刺激的である。

https://www.bilibili.com/video/BV1t7411W7Eq?spm_id_from=333.337.search-card.all.click&vd_source=ba9ae3c860748ec9008f01f641bd9bf8

https://www.youtube.com/watch?v=dCQ7CAQ4Npc

https://www.youtube.com/watch?v=sbJSAOngiGI&t=691s

次に推薦するのは、Hasan & Kaneによるトポロジカル絶縁体とトポロジカル超伝導体に関する综述（レビュー）である。数式は少なく、理論と実験の多くの結論が列挙されており、バンド理論を学んだ読者がこの分野への興味をさらに深め、トポロジカルバンド理論（Topological Band Theory）の魅力を感じるのに適している。ただし、細部にこだわりすぎず、1、2回読んで大意を掴めば十分であり、その後さらに学んでから戻って復習すると、より多くの収穫があるはずである。

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.82.3045

@Lord Hart のコラムでは、Hasan & Kaneによるトポロジカル絶縁体とトポロジカル超伝導体の综述の翻訳が公開されているので、ぜひ参照されたい。

https://www.zhihu.com/column/condensematterphysics

その後は、定量的な計算と公式の導出を多めに行うことを提案する。QHEから出発し、まずDavid TongのQHE講義ノートのChap1とChap2を推薦する。Berry Phaseという重要な道具と、線形応答理論から導かれるHall Conductanceの式におけるBerry CurvatureとChern Numberの項を理解できれば十分である。

http://www.damtp.cam.ac.uk/user/tong/qhe.html

QHEに理論的に存在するトポロジカル効果をより厳密に分析したものについては、前の章で私が書いたノートを参照されたい。

https://zhuanlan.zhihu.com/p/486890623

また、トポロジカル絶縁体の初心者に役立つウェブサイトを紹介する。このサイトの内容も初心者に非常に親しみやすい。

https://topocondmat.org/index.html

以降の内容は、おそらく次の数章のノートでまとめたいと考えていること、すなわち相互作用のない絶縁性（ギャップ有り）フェルミオン系のトポロジカル分類をより系統的に分析することである。

まずはトポロジカルバンド理論を体系的に学ぶべきだと考え、そのためにお勧めの本を二冊挙げる。これらにはQHEの分析も含まれているので、さらに系統的に学びたい読者はこの二冊から読み始めるとよい：

+ 一冊目はBernevig & Taylor Hughesの'Topological Insulator and Superconductor'。この本の特徴は導出が厳密なことである。例えば第3章では格子フェルミオン系の線形応答理論を非常に徹底的に分析し、電流演算子の式を導出し、magnetic BZの方法を用いて非常に力押しで量子ホール効果を導出する。しかし、初心者（私のことだ）を怖がらせ、膨大な式の導出の中で本来の物理的イメージを見失わせ、最後にはemoらせてしまう可能性がある（私のことだ）。そのため、最初の数章と後の4D Topological Insulatorの数章は適度に簡略化して読み、その後XL Qi, Taylor Hughes, SC Zhangのトポロジカル場理論（Topological Field Theory）の補足資料として活用すると非常に役立つ。
+ もう一冊はShunQing Shen（沈順清）先生の"Topological Insulators: Dirac Equation in Condensed Matters"。この本の斬新な点は、冒頭でDirac Equationの観点からバンドのgap closingとreopeningが系のバンドトポロジカル性質の転移に与える影響を分析し、エッジ状態や$\mathbb{Z}_2$数など、これまでの综述では定性的だった結論を厳密に導出しているところにある。トポロジカル絶縁体のトポロジカル性質を理論的にさらに理解する上で大いに役立つ。
+ さらに、Prof. Zhaihui（翟薈）の'Ultracold Atomic Physics'の第7章では、簡単な2バンド系のトポロジカルバンド理論が専門的に紹介されている。2バンド系の波動関数はBloch Sphere上の単位ベクトルで記述できるため、そのトポロジカルな本質がより際立つ。私も翟先生の講義でトポロジカルバンド理論の理解に大きな進展があった。

以上の内容を通じて、読者はトポロジカルバンド理論をより体系的に理解できるようになる。そうすれば、これまでの综述で多かれ少なかれ触れられてきたtopological classificationに興味が湧くだろう。ここでは対称性と次元がトポロジカル分類において果たす役割を考える必要がある。この分野ではChing-Kai Chiu, Jeffrey C. Y. Teo, Andreas P. Schnyder, and Shinsei Ryuの综述を推薦する。

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.88.035005

Yau Mathematical Sciences CenterのQingrui Wangによるトポロジカル秩序に関するオンライン講義も参考になる。初心者はまずLec5-Lec7のFermionic SPT Phaseの内容を視聴するとよい。

https://qr-wang.github.io/teaching_2021_TQM.html

さらに進んで、読者にある程度の量子場理論あるいは凝縮系場理論の基礎があれば、XL Qi, Taylor Hughes, SC Zhangのトポロジカル場理論（Topological Field Theory）の論文も参考にできる。そこではChern-Simons項を含む有効理論を導入することで、トポロジカル絶縁体を4次元などのより高次元に一般化している。前述のように、Bernevig & Taylor Hughesの'Topological Insulator and Superconductor'はこの論文の補足資料として活用できる。

http://journals.aps.org/prb/abstract/10.1103/PhysRevB.78.195424 

トポロジーと場理論の内容についてはあまり詳しく述べない。ホモトピー論と経路積分の基礎があれば十分である。ここで場理論関連の推薦を簡単に列挙しておく：
+ QFT: Peskin, Weinberg, Schwartz, Coleman, A Zee, David Tong (Lec. Note)
+ CMPFT: Roger Melko (Online Course), Altland, Fradkin, Xiaogang Wen（文小剛）, Nagaosa: QFT in CMP, QFT in Strongly Correlated Electronic System

## From IQHE to Chern Insulator：Time-Reversal Breaking

すべては段階的に進む。歴史的には、IQHEが発見された当初、フェルミエネルギー以下のLandau準位の数がわずか数個になるほどの巨大な磁場が必要であった。その後、強磁場を必要としないIQHEを求める過程で、HaldaneはHoneycomb格子に周期磁場を加えることを提案し、TRSを破るものの全体の磁場はゼロとなる系を実現した。これが外部磁場を必要としないIQHE、あるいはChern Insulatorと呼ばれるものである。Chern Insulatorは外部磁場をかけたIQHEと同様に、**二次元、ギャップ有り、相互作用無し、フェルミオン系、時間反転対称性（TRS）無し、粒子-正孔対称性（PHS、あるいは電荷共役対称性）無し、カイラル対称性無し**の系におけるトポロジカル効果であり、磁場の役割は"Time-Reversal Breaking"という条件に吸収されている。

Chern Insulatorの分析では、外部磁場がないため、前述のMagnetic BZの方法を用いてHall応答を計算する必要はなく、系のBZと全ての占有バンドのBerry Curvatureを積分すればよい。TRSが破れているため、特定のhoppingやchemical potentialの下では、磁場を加えなくても非零のTKNN invariant（Chern number）が得られる。

Hall効果は様々な摂動法で計算できる。前節でこの点について詳しく説明したのでここでは繰り返さない。全体的に、全ての証明方法は何らかの摂動論の下での線形応答の計算であり、最も一般的なLinear Response Theoryによって統一的に扱うことができ、最終的なHall ConductanceはKubo Formulaによって計算できる。

一方、Berry Connection $\mathcal{A}$ とBerry Curvature $\mathcal{B}$ はBZ上で定義される(Abelian) gauge fieldである（Abelianと言うことは、後にはより一般的なNon-Abelian gauge fieldがもたらす4D topological insulatorなどが存在することを示唆している）。BZ（$\mathbf{T}^2$）上での量子化はほぼ完全にトポロジカル効果である。Hall Conductanceの式とChern numberの式の一致に驚嘆すると同時に、逆向きに考えることもできる。すなわち、異なる次元のgauge fieldのトポロジカル性質（Chern-Simons Theory）を用いて、この既知のトポロジカル性質に対応する物理効果を探求するのである。この考え方に従い、理論物理学者は4D TIや3D Half-IQHE、3D 磁電効果など、さらに多くの物理におけるトポロジカル効果を予言することに成功した。

## From 2D TRB to 1D PHS: Topology in Different Dimensions 

Chern Insulatorに続いて、理論物理学者たちはさらに豊かなトポロジカル効果を期待した。本節ではChern Insulatorから出発し、1次元系におけるChern numberのトポロジカル効果を考察する。

前章のLaughlin Argumentでは、Cylinderに磁束を加えることで、ある次元の$k_y$を正準運動量$k_y+A_y$に置き換え、その後この正準運動量をゆっくりと変化させると、系のスペクトルが周期的に変化することを見た。このとき$k_y$は事実上パラメータとなり、系はこのパラメータに関連するx方向の1次元系となる。これがDimensional Reductionの基礎である。

$$ H=\sum_{k_{y}} H_{1 \mathrm{D}}\left(k_{y}+A_{y}\right) $$

磁束を加えることはベクトルポテンシャルを導入することに相当し、これにより空間並進対称性が保たれる。

$$ A_y = -E_y t \quad A_x = 0$$

ここで、2次元TRB Chern Insulatorを次元削減した後の、Chern numberと1次元系の物理効果の対応関係を考える。ここでの物理効果は$\mathbb{Z}_2$Quantized Charge Polarizationである。

2次元Hall効果はHall電流を与える：

$$ j_x = \sigma_H E_y $$

電荷保存則より

$$ \partial_t \rho + \nabla \cdot j = 0 $$

ガウスの定理より

$$ \nabla \cdot D = \nabla \cdot (P + \epsilon_0 E) = \rho$$

したがって、発散項を除いて

$$ j = \partial_t P $$

$$ \Delta P = \int_0^T dt \ j $$

一方、強束縛モデルの電流は正準運動量$k_y + A_y$をパラメータとする1次元モデルの電流の和で与えられる：

$$ J_{x}=\sum_{k_{y}} J_{x}\left(k_{y}\right) $$

このとき、$\Delta t=2 \pi / L_{y} E_{y}$の間にpumpされる電荷量は：

$$ \Delta Q=\int_{0}^{\Delta t} d t \sum_{k_{y}} J_{x}\left(k_{y}\right) \equiv \sum_{k_{y}} \left. \Delta P_{x}\left(k_{y}\right)\right|_{0} ^{\Delta t}$$

$\Delta t$時間後、スペクトルはちょうど一周期を経て、占有状態の量子数は断熱変化し、$k_y \rightarrow k_y - 2\pi/L_y$となる：

$$ \Delta P_{x}\left(k_{y}\right)=P_{x}\left(k_{y}-2 \pi / L_{y}\right)-P_{x}\left(k_{y}\right) $$

熱力学的極限では、

$$ \Delta Q=-\oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}}  \quad J_{x}\left(k_{y}\right)=d P_{x}\left(k_{y}\right) / d t $$

量子Hall効果と組み合わせて：

$$ \Delta Q=\sigma_{H} \Delta t E_{y} L_{y}=2 \pi \sigma_{H} $$

ここから、2次元Chern numberの量子化が1次元charge pump系のsum ruleに対応していることがわかる。すなわち、$k_y$で記述される1次元系$H_{1 \mathrm{D}}\left(k_{y}\right)$は次を満たす：

$$ \Delta P = \oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}} = - 2\pi \sigma_{H} = -C_1$$

これは、2次元Bloch Hamiltonianのある$k$を時間発展する断熱パラメータに置き換えると、一周期後に系のPolarizationの変化がChern numberの量子化された値になることを示している。

しかしこれはほとんど、Chern numberの式においてBZのある次元のk積分をtの変化と解釈したに過ぎず、結果は自明的である。またこれは2次元系の全てのパラメータ間隔$2\pi/L_y$の寄与に対応しており、$k_y$をパラメータとする1次元系のPolarizationのsum ruleを与えているに過ぎない。

Polarizationは以下の式でも定義できる：

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

ここでWannier Functionの定義を利用した：

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

これからわかるように、PolarizationはBerry ConnectionというGauge Fieldによって定義できる。しかし、Gauge FieldのBZ上のトポロジカル効果により、Gauge Transformationを行うと$P$は整数倍だけ変化しうる。すなわち、$\oint dk \cdot A(k)$の経路積分はゲージ変換の下で$2\pi$の整数倍だけ変化しうる。

さらに、$k_y+A_y$を$\theta$に置き換えると、Polarizationは次のように書ける：

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

元の2次元Bloch Hamiltonianは$\theta$をパラメータとする1次元Bloch Hamiltonianと見なせる。以下では対称性を導入し、この1次元トポロジカル効果の「半製品」— sum ruleを考察する：

$$ -\oint_{0}^{2 \pi} d \theta \frac{\partial P_{x}\left(\theta\right)}{\partial \theta} = C_1 $$

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

あるいは以下の形式で書ける：

$$ G(\theta) =-\oint \frac{d k_{x}}{2 \pi} f_{x \theta}\left(k_{x}, \theta\right) =\oint \frac{d k_{x}}{2 \pi}\left(\frac{\partial a_{x}}{\partial \theta}-\frac{\partial a_{\theta}}{\partial k_{x}}\right)
$$
$$
\int G(\theta) d \theta=C_{1} \in \mathbb{Z}
$$

これが1次元系のトポロジカル分類にさらに役立つかどうかを考える。ここで$a$はBerry Connection、$f$はBerry Curvatureである。

+ 対称性の導入

新たなトポロジカル分類を得たい、あるいはPの値が量子化されることを望むなら、1次元系に対称性を導入する必要がある。ここで導入する対称性は粒子-正孔対称性（Particle-Hole Symmetry）、あるいは電荷共役対称性（Charge Conjugate Symmetry）である：

$$ H=\sum_{k} c_{k}^{\dagger} h(k) c_{k}=\sum_{k} c_{-k} C^{\dagger} h(k) C c_{-k}^{\dagger} $$

$$ \Rightarrow C^{\dagger} h(-k) C=-h^{T}(k) $$

二つの1次元Bloch Hamiltonianを考える：

$$ h(k, 0)=h_{1}(k), h(k, \pi)=h_{2}(k) $$

元の2次元Bloch HamiltonianもPHSを満たすことを要請する：

$$ h(k, \theta)=-\left(C^{-1} h(-k, 2 \pi-\theta) C\right)^{T} $$

2次元Bloch Hamiltonianを用いてChern numberを定義できる：

$$ C[h(k, \theta)]=\oint d \theta \frac{\partial P(\theta)}{\partial \theta} $$

ここで1次元系のPolarizationも以下の式で定義できる：

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

ここでWannier Functionの定義、すなわち実空間の波動関数を利用した：

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

これからわかるように、PolarizationはBerry ConnectionというGauge Fieldによって定義できる。しかし、Gauge FieldのBZ上のトポロジカル効果により、Gauge Transformationを行うと$P$は整数倍だけ変化しうる。すなわち、$\oint dk \cdot A(k)$の経路積分はゲージ変換の下で$2\pi$の整数倍だけ変化しうる。

上記のPolarizationの定義を自然単位系に書き換える：

$$ P(\theta)=\oint \frac{d k}{2 \pi} \sum_{E_{\alpha}(k)<0}(-i)\left\langle k, \theta ; \alpha\left|\partial_{k}\right| k, \theta ; \alpha\right\rangle $$

PHSを利用する：

$$ h(-k, 2 \pi-\theta) C|k, \theta ; \alpha\rangle^{*}=-E_{\alpha}(k) C|k, \theta ; \alpha\rangle^{*} $$

以下の式が証明できる【Xiaoliang Qiのトポロジカル場理論の論文を参照。証明は最後に付録として載せる】：

$$ P(\theta)= -P(2 \pi-\theta) $$ 

したがって

$$ \int_{0}^{\pi} d P(\theta)=\int_{\pi}^{2 \pi} d P(\theta) $$

1次元PHS系のこの性質を利用して（PHSは非常に重要である。そうでなければPはmodulo 1で定義される任意の値であり、量子化されない）、さらにRelative Chern Numberを定義できる：

$$ N_{1}\left[h_{1}(k), h_{2}(k)\right]=(-1)^{C[h(k, \theta)]}$$

trivialな1次元バンドとのrelative Chern numberが0のモデルをtopologically trivial insulator、trivialな1次元バンドとのrelative Chern numberが1のモデルをtopological insulatorと呼ぶ。これにより$\mathbb{Z}_2$のトポロジカル分類が得られる。【ここでも結論のみ述べている。詳細な導出もXiaoliang Qiのトポロジカル場理論の論文にあり、参照の便宜のため本ノートの最後にも掲載する。】

## From Chern Insulator to Topological Insulator: Topology with Different Symmetries

これまでの考察から、次元の変更に加えて、Chern Insulatorという一般化は**対称性**とトポロジカル分類の関係が非常に密接であることを示している。他の対称性を持つ系でも同様のトポロジカル効果（おそらく別の種類の量子ホール効果）が期待される。同じ2次元系でありながらTRSを持つ系で見つかったのがTopological Insulatorである。TIはしばしば総称として使われるが、対応する物理効果—量子スピンホール効果—からQSH Insulatorとも呼ばれる。

実際、2次元TRS系のトポロジカル分類も高次元の母系の次元削減（4D$\rightarrow$ 3D $\rightarrow$ 2D）と対称性の導入によって得られる。しかし初心者には複雑すぎるので、前節で述べたPolarization、および次に述べるPfaffianと$\mathbb{Z}_2$-indexを用いて2次元TIのトポロジカル効果の一端を覗くことを個人的に勧める。

TRSはBloch Hamiltonianに対して次を要請する：

$$ \mathcal{T} h(\mathbf{k}) \mathcal{T}^{-1} = h(-\mathbf{k}) $$

TRSを持つ系のエネルギーバンドを観察すると、$\mathbf{k} = - \mathbf{k}\ mod \ \mathbf{\Gamma}_i$（$\mathbf{\Gamma}_i$は逆格子ベクトル）のとき、縮退が生じる。すなわち$|n,\mathbf{k}\rangle$と$\mathcal{T}|n,\mathbf{k}\rangle$はともに$E_n(\mathbf{k})$のエネルギーを持ち、かつ直交する。これにはさらにスピン1/2系における$\mathcal{T}^2 = -1$の条件を満たす必要がある。これが有名なKramers縮退（Kramer Degeneracy）である。

また一般の$|n,\mathbf{k}\rangle$に対して、その時間反転$\mathcal{T}|n,\mathbf{k}\rangle$は$-\mathbf{k}$の同じエネルギーに対応するため、バンドは$k=0$の点に関して鏡像対称性を持つ。

このようにして、2つのバンドが$\infty$の字のような交差を形成する。この対称性のため、Chern numberの計算式をそのまま適用しようとすると、TRS系ではBerry Curvatureが2本のバンドごとに積分が打ち消し合うことになる。

このKramers縮退を持つバンドを2種類に分類しよう。第2n-1番目と第2n番目のバンドをスピンアップ/ダウンに対応するバンドと見なし、それぞれ$n-I,II$バンドと呼ぶ。

まず1次元系を考える。$I,II$バンドのPolarizationを計算できる。TRSのため、元の$P = P^I + P^{II}$から有用な情報を得ることはできない。そこでTime-Reversal Polarizationを考える：

$$ P_s = P^I - P^{II} $$

Shunqing Shenのトポロジカル絶縁体の4.8節の導出により、TRIM（Time-Reversal Invariant Momentum）における$w_{m n}(k)=\left\langle u_{m}(-k)|\Theta| u_{n}(k)\right\rangle$のPfaffianとDeterminantを用いて$\mathbb{Z}_2$数を計算できる。

2次元と3次元に一般化する際には、2次元をx方向の1次元系の連続的な変換と見なし、$k_y=0$と$k_y=\pi$における1次元系の$\mathbb{Z}_2$数の変化を調べることで、新たな$\mathbb{Z}_2$数を定義できる。同様の方法で3次元系の$\mathbb{Z}_2$数も定義できる。

+ Pfaffianの計算には、Bloch波動関数にBZ全体で連続なゲージを定義する必要があり、これは非常に複雑である。系が反転対称性（Inversion Symmetry, IS）を持つ場合、TRIM点における波動関数のParityを用いて$\mathbb{Z}_2$数を簡易的に定義できる。これについてはBernevigのトポロジカル絶縁体の書物のChap12で詳しく紹介されている。
+ 注目すべきは、最も単純なnon-trivial QSHには2つのHaldane Model（スピンアップ用とスピンダウン用）が必要であり、異なるスピンのバンド（ここでの$I,II$バンド）が異なるSpin Chern Numberに対応する。このとき$\mathbb{Z}_2$数はSpin Chern Numberの差 mod 2となる。この状況はスピン保存を要請し条件は厳しいが、理解しやすい。一方、上述の$\mathbb{Z}_2$数に関する議論は、スピンによって導入された自由度がバンド数を増やすことのみに関係し、各バンドが具体的にどの方向のスピンに対応するかには関与しない。したがって$\mathbb{Z}_2$数の定義は普遍的意味を持つ。
+ 実際、Topological InsulatorにはしばしばSpin-Orbit Coupling項の導入が必要である。これは系のTRSを保護し、異なるスピンに一定の「磁場」効果をもたらすと同時に、Spin Conservationを破壊する可能性もある。

## From Lattice Model to Continuum Model: Dirac Equation and Edge Mode

トポロジカル相転移はほぼ全てがgap closingとreopeningに起因することがわかる。この過程はmassive Dirac Fermionの質量変化過程と非常に類似しており、異なる次元のDirac Fermionを用いて系のバンドの局所的特徴を記述し、系のトポロジカル相転移を記述することができる。

これは合理的である。同じトポロジカル相はバンドの細部に関心を持たず、バンドに特異点が現れたときのみトポロジカル性質が不連続に変化する（トポロジカル不変量の跳躍など）からである。

同時に、Dirac Fermionは局所的なバンドの特徴しか記述できず、遠方では分散が発散するため、BZの周期境界条件と不可避的に矛盾が生じ、いくつかの物理的効果も生じることに注意すべきである。例えば3次元TIにおけるDirac Fermionは単一のDirac Coneのみを持つことはできないなどである。

Prof. ShunQing Shen（沈順清）のトポロジカル絶縁体の書物の第2章では、この点について非常に詳しく説明されている。読者にはさらなる研究を強く勧める。開境界を持つ非自明なトポロジカル絶縁体はrobustなトポロジカル境界状態を持ち、その分散は近似的に線形であることがわかる。これもDirac方程式から導出できる。具体的には、開境界側の$k_i$を$-i \partial_i$に置き換え、長距離範囲での実空間波動関数とその対応するエネルギー（表面状態の分散関係）を求解する。一般に高次元の系は摂動的にしか解けないが、小範囲での線形分散は依然として確認でき、これは実空間の波動関数が一方向に移動することを示している。この解析結果はエッジ状態の存在とその分散関係を理解する上で十分である。様々な摂動を加えると分散関係の形状は大きく歪むが、gap closingがなければバンドのトポロジーは不変であり、対応するエッジ状態もrobustであると信頼できる。これがトポロジカル絶縁体において非常に重要な**バルク-エッジ対応**（Bulk-Edge Correspondence）の本質である。

さらに2次元Chern InsulatorとTopological Insulatorを観察すると、ChiralおよびHelicalな境界状態が得られる。

ここでのChiralとは回転方向が一致することを指す。例えば左側の境界状態は下向きの群速度を持ち、右側の境界状態は上向きの群速度を持つ。これはChern Insulator/IQHEに対応する。Helicalとは境界状態の回転方向とスピン方向がロックされていることを指す。例えばスピンアップは時計回り、スピンダウンは反時計回りであり、Topological Insulator/QSHEに対応する。

## Transport Property: Landauer Formalism

エッジモードは不純物などの摂動に対してrobustであるため、無反射の1次元チャンネルと見なすことができる。したがってLandauer Formalismを通じて、2端子、4端子、6端子系の実際の測定における物理的応答を分析できる。これは、これらの非自明なトポロジカルエッジ状態を実験的に検出し、実験的に材料のトポロジカル分類を行うために必要不可欠である。

詳細については、Prof. ShunQing Shen（沈順清）のトポロジカル絶縁体の6.3節を参照されたい。

## From Tight-Binding Models to Effective Field Theory: Chern-Simons Term

Xiaogang Wen（文小剛）はその多体物理の教科書の冒頭で経路積分形式を紹介し、有効理論の重要性を強調している。読者にはXiaogang Wenの多体物理の第2章を参照することを勧める。

経路積分の大まかな精神は、古典的相空間の各経路$\phi=\phi(t)$（粒子の経路でも場の経路でもよい）に「確率」$e^{S[\phi(t)]}$を割り当てることである。ここで$S[\phi(t)]$はこの経路の作用量に対応する。したがって、古典系のLagrangianを書き下せば、経路積分を用いてその量子版を得ることができる。

場理論の応用範囲は極めて広い。系の全ての自由度の力学変数を考慮して大きなLagrangianを書き、経路積分で量子化した後、観測可能量は外部場$j(x)$を$\phi$場と結合させ、汎関数微分などを用いて求めることができる。

$$ \langle \phi(x) \rangle = \frac{1}{\mathcal{Z[j]}}\left. \frac{\delta \mathcal{Z}[j]}{\delta j(x)}  \right|_{j=0} $$

$$ \mathcal{Z}[j] \equiv \int \mathcal{D}\phi e^{S[\phi]+ \int d^d x \phi(x)j(x)} $$

しかしこのような理論は万物の理論（Theory of Everything）のようであり、実際には我々は関心のある一部の自由度に対応する測定可能な量や相関関数のみに関心がある。であれば、関心のない部分を先に経路積分してしまえばよい。

$$\int \mathcal{D}\phi ( \int \mathcal{D}\psi e^{S[\phi,\psi]} ) = \int \mathcal{D}\phi e^{S_{eff}[\phi]}$$

これは各種の期待値の計算に影響を与えない。なぜなら$\mathcal{Z}$の定義はこれによって変更されないからである。

この操作の物理的意味を考えてみよう。これは、関心のない部分の積分の寄与により、系が我々の関心のある$\phi$場のみを含む有効作用量とそれに対応する等価な場理論によって完全に記述されることを意味する。

これは非常に重要である。凝縮系物理学では、我々はしばしば系の低エネルギー励起や応答に注目する。したがって、高エネルギー部分を経路積分し、低エネルギー部分の場の有効理論を得ることができる。これは繰り込み群理論の真髄でもある：高エネルギーの部分を次々に積分し、$S_{eff}$の中で系を記述するパラメータ（質量、相互作用の強さなど）が、我々の切断$\Lambda$とともにどのように変化するかを観察する。多くのパラメータは$\Lambda \rightarrow 0$とともにゼロに近づくため、これらのパラメータは低エネルギーの物理現象にほとんど影響を与えないことがわかる。最終的に、ゼロに近づかないごく少数のパラメータのみを研究すれば、もともと様々な値のパラメータで記述されていた複雑な多体系の低エネルギー理論を記述できる。これが多体系における**普遍性**（Universality）を研究するための理論的基盤である！

なぜ水の連続相転移と常磁性-強磁性相転移が基本的に同じ臨界指数$\beta$を持つのか考えてみよう。それらを記述するモデルのパラメータが大きく異なっていても、高エネルギー部分を次々に積分していく過程で、最終的に残るのはごく少数の重要なパラメータだけであり、その結果、それらの低エネルギー理論を記述するモデルは驚くほど類似する。もし場の二次項と四次項だけが残れば、Landau平均場モデルはそのような全ての低エネルギーモデルが同じ臨界指数$\beta=1/2$を持つことを予言する。ここで、我々が関心を持たないのは高エネルギーの場であり、電子に対応するフェルミ場や、系と結合した環境のフォノン場などを無視しても構わない。それらを経路積分で先に積分してしまえばよいのである。

有効理論の重要性を述べたところで、IQHEの有効場理論を見てみよう。

IQHEの有効場理論はどのようにして得られるのか？まず、系を記述するHamiltonianには様々なフェルミオンの生成消滅演算子が含まれる。量子場理論あるいは凝縮系場理論を思い出せば、その経路積分量子化は全ての$c^\dagger,c$をGrassmann数$\bar{\psi},\psi$に置き換えて経路積分を行うものである。同時に系には外部電磁場が存在するため、Peierls Substitutionを行ってgauge fieldをHamiltonianに導入する。

有効理論に従い、フェルミ場の自由度を経路積分し、Aに関係する部分を等価な作用量$S_{eff}$に吸収させる。これによりトポロジカル絶縁体系におけるゲージ場Aの有効理論が得られる。

$$
\begin{aligned}
e^{i S_{\text {eff}}[A]} &=\int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H [A] \right]} \\
&= \int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H_0[c,c^\dagger] \right] + \int d^d x \ j\cdot A} \\
&=\operatorname{Det}\left[\left(i \partial_{t}-A_{0 m}\right) \delta_{m n}^{\alpha \beta}-h_{m n}^{\alpha \beta} e^{i A_{m n}}\right]
\end{aligned}
$$

$$
\begin{aligned}
H[A]=& \sum_{m, n}\left(c_{m \alpha}^{\dagger} h_{m n}^{\alpha \beta} e^{i A_{m n}} c_{n \beta}+\text { h.c. }\right) +\sum_{m} A_{0 m} c_{m \alpha}^{\dagger} c_{m \alpha}
\end{aligned}
$$

この有効場に基づき、系の応答を計算できる。

$$ e^{i S_{\text {eff}}[A]} = \int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H_0[c,c^\dagger] \right] + \int d^d x \ j\cdot A} $$

汎関数微分を行うことで系の線形応答が得られる：

$$ j = \frac{\delta S_{eff} [A]}{\delta A} $$

ここで逆向きに、QHEから系の有効作用量を推測してみよう。以下が成り立つ：

$$
j^{\mu}=\frac{C_{1}}{2 \pi} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

したがって、以下の式がChern Insulatorの有効作用量であることが検証できる：

$$
S_{\mathrm{eff}}=\frac{C_{1}}{4 \pi} \int d^{2} x \int d t A_{\mu} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

この項はゲージ不変性を持つことがわかる。これをChern-Simons項と呼ぶ。注意すべきは、有効理論は既に以前のフェルミオン系の情報を積分してしまっているため、有効理論から$C_1$の起源を知ることはできない。

+ 分数量子ホール効果を研究する際にも、全く同様の方法で有効作用量を構築できる。

## From Chern-Simons Term to 4D TI: 2nd Chern Number

ここで4次元の系を考えよう。同じChern-Simons項が4次元系にも存在し、その運動方程式を求めることで4次元TIのトポロジカル応答が得られると想定する。詳細はXL Qiの综述とBernevigのトポロジカル絶縁体の書物の第13章を参照されたい。

4次元TIの有効作用量は以下の通りである：

$$
S_{\mathrm{eff}}=\frac{C_{2}}{24 \pi^{2}} \int d^{4} x d t \epsilon^{\mu \nu \rho \sigma \tau} A_{\mu} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

線形応答の観点から、2nd Chern numberは：

$$
C_{2}=-\frac{\pi^{2}}{15} \epsilon^{\epsilon \mu \rho \sigma \tau} \int \frac{d^{4} k d \omega}{(2 \pi)^{5}} \operatorname{Tr}\left[\left(G \frac{\partial G^{-1}}{\partial q^{\mu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\sigma}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\tau}}\right)\right.
$$

一方、Berry Phaseのトポロジーの観点から、2nd Chern numberは：

$$
C_{2}=\frac{1}{32 \pi^{2}} \int d^{4} k \epsilon^{i j k \ell} \operatorname{tr}\left[f_{i j} f_{k \ell}\right]
$$
$$ f_{i j}^{\alpha \beta}=\partial_{i} a_{j}^{\alpha \beta}-\partial_{j} a_{i}^{\alpha \beta}+i\left[a_{i}, a_{j}\right]^{\alpha \beta} $$
$$
a_{i}^{\alpha \beta}(\mathbf{k})=-i\left\langle\alpha, \mathbf{k}\left|\frac{\partial}{\partial k_{i}}\right| \beta, \mathbf{k}\right\rangle
$$
where $i, j, k, \ell=1,2,3,4$.

運動方程式を求めると、この有効作用量に対応する電流密度が得られる：
$$
j^{\mu}=\frac{C_{2}}{8 \pi^{2}} \epsilon^{\mu \nu \rho \sigma \tau} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

注目すべきは、外部場Aの1階汎関数微分の結果にAの2階の項が含まれる点である。2次元のChern-Simons項とは異なり、4次元のChern-Simons項に対応するトポロジカル磁電効果などの現象は非線形応答となる。

具体的な例を考えよう：
$$
A_{x}=0, A_{y}=B_{z} x, A_{z}=-E_{z} t, A_{w}=A_{t}=0
$$
このとき$F_{x y}=B_{z}$ and $F_{z t}=-E_{z}$であり、4次元電流密度の式は：

$$ j_{w}=\frac{C_{2}}{4 \pi^{2}} B_{z} E_{z} $$

あるいはxy平面上のHall電流として書ける。このときz方向の磁場と電場が必要である：
$$
\int d x d y j_{w}=\frac{C_{2}}{4 \pi^{2}}\left(\int d x d y B_{z}\right) E_{z} \equiv \frac{C_{2} N_{x y}}{2 \pi} E_{z}
$$

## From 4D TRB to 3D TRI: Dimensional Reduction and $\mathbb{Z}\rightarrow\mathbb{Z}_2$ Again

4次元Chern-Simons項を通じて、TRB TIの4次元への一般化とそのトポロジカル不変量（2nd Chern Number）を得た。

4次元系にDimensional Reductionを施すことで、この母モデルに対応する3次元TRI（Time-Reversal Invariant）TIのサブモデルが得られる。TRSを導入することで、再び$\mathbb{Z}_2$のトポロジカル分類を得る。

具体的に3次元TIの物理モデルを分析すると、Surface Half QHEやトポロジカル磁電効果など、一連の新奇なトポロジカル現象が得られる。

詳細はBernevigの書物の第14、15章、およびXL Qiのトポロジカル場理論の論文の後半部分を参照されたい。

## From Specific to Arbitrary: Period Table and SPT Phase

我々はすでに、次元と対称性がトポロジーにおいて重要であることを認識している。「ある対称性を保つ連続変形によって2つのモデルが結び付けられる」という条件をトポロジカル分類の根拠とすることができる。これは実際、トポロジーにおけるホモトピーの定義と一致する。これがSPT（Symmetry Protected Topological）Phaseの起源であり、特定の対称性によって保護されたトポロジカル相である。

Dimensional Reductionを通じて、同じトポロジカル不変量が異なる次元の間で（いくつかの対称性を変更した後で）示すトポロジカル効果を得ることができる。

したがって、最も一般的なモデルを考え、その対称性を分析する。これは一見非常に複雑に見えるが、実際には反ユニタリ（Anti-Unitary）対称性のみを研究すればよい。なぜなら、ユニタリ対称性を持つ系は常に直積分解することができ、その結果ユニタリ対称性を持たない対角ブロックが得られるからである。

さらに局所的な対称性を考慮すると、Altlandはすでにそれを10種類に分類している。これがPeriodic tableの系の対称性側を代表する10種類の対称性グループの由来である。これら10の対称性グループは、さらに3つの基本的な対称性、すなわち時間反転対称性（TRS）、粒子-正孔対称性（PHS）、カイラル対称性（CS）に由来する。

Dimensional Reductionを行う際には、特定の対称性を追加する必要がある。例えば、2次元TRB Chern Insulatorから1次元への次元削減ではPHSを導入してCharge Polarizationを$\mathbb{Z}_2$量子化する必要があり、4次元TRB TIから3次元TRI TIへの次元削減ではTRSを導入して同様の$\mathbb{Z}_2$量子化を得る。

Yau Mathematical Sciences CenterのQingrui Wangによるトポロジカル秩序に関するオンライン講義のうち、Lec5-Lec7のFermionic SPT Phaseの内容では、上述のPeriodic Tableがどのように形成されるかが体系的に紹介されている。

https://qr-wang.github.io/teaching_2021_TQM.html

Ching-Kai Chiu, Jeffrey C. Y. Teo, Andreas P. Schnyder, and Shinsei Ryuの综述にも詳細な説明がある。

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.88.035005

## Proof

+ Proof of $P(\theta) = -P(2 \pi-\theta)$

$$ P(\theta)= \oint \frac{d k}{2 \pi} \sum_{E_{\alpha}(k)<0}(-i)\left\langle k, \theta ; \alpha\left|\partial_{k}\right| k, \theta ; \alpha\right\rangle $$

$$ = \oint \frac{d k}{2 \pi} \sum_{E_{\bar{\alpha}}(-k)>0}(-i)(\langle-k, 2 \pi-\theta ; \bar{\alpha} \mid)^{*} \partial_{k}|-k, 2 \pi-\theta ; \bar{\alpha}\rangle^{*} $$

$$ = -P(2 \pi-\theta) $$

+ 1D PHS $\mathbb{Z}_2$-classification
	  
Consider two different parameterizations $h(k, \theta)$ and $h^{\prime}(k, \theta)$, satisfying $h(k, 0)=h^{\prime}(k, 0)=h_{1}(k)$, $h(k, \pi)=h^{\prime}(k, \pi)=h_{2}(k)$. Denoting the polarization $P(\theta)$ and $P^{\prime}(\theta)$ corresponding to $h(k, \theta)$ and $h^{\prime}(k, \theta)$, respectively, the Chern number difference between $h$ and
$h^{\prime}$ is given by
$$
C[h]-C\left[h^{\prime}\right]=\int_{0}^{2 \pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right)
$$
Define the new interpolations $g_{1}(k, \theta)$ nnd $g_{2}(k, \theta)$ as
$$
\begin{array}{l}
g_{1}(k, \theta)=\left\{\begin{array}{cc}
h(k, \theta), & \theta \in[0, \pi] \\
h^{\prime}(k, 2 \pi-\theta), & \theta \in[\pi, 2 \pi]
\end{array}\right. \\
g_{2}(k, \theta)=\left\{\begin{array}{cc}
h^{\prime}(k, 2 \pi-\theta), & \theta \in[0, \pi] \\
h(k, \theta), & \theta \in[\pi, 2 \pi]
\end{array}\right.
\end{array}
$$
$g_{1}(k, \theta)$ and $g_{2}(k, \theta)$ are obtained by recombination of the two paths $h(k, \theta)$ and $h^{\prime}(k, \theta)$, as shown in Fig. 4. From the construction of $g_{1}$ and $g_{2}$, it is straightforward to see that
$$
\begin{array}{l}
C\left[g_{1}\right]=\int_{0}^{\pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right) \\
C\left[g_{2}\right]=\int_{\pi}^{2 \pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right)
\end{array}
$$
Thus $C[h]-C\left[h^{\prime}\right]=C\left[g_{1}\right]+C\left[g_{2}\right]$. On the other hand, from Eq. (37) we know $C\left[g_{1}\right]=C\left[g_{2}\right]$, so that $C[h]-C\left[h^{\prime}\right]=2 C\left[g_{1}\right]$. Since $C\left[g_{1}\right] \in \mathbb{Z}$, we obtain that $C[h]-C\left[h^{\prime}\right]$ is even for any two interpolations $h(k, \theta)$ and $h^{\prime}(k, \theta)$ between $h_{1}(k)$ and $h_{2}(k)$. Intuitively, such a conclusion simply comes from the fact that the Chern number $C[h]$ and $C\left[h^{\prime}\right]$ can be different only if there are $\sin -$ gularities between these two paths, while the positions of the singularities in the parameter space are always symmetric under particle-hole symmetry, as shown in Fig. 4.

Based on the discussions above, we can define the "relative Chern parity" as
$$
N_{1}\left[h_{1}(k), h_{2}(k)\right]=(-1)^{C[h(k, \theta)]},
$$
which is independent of the choice of interpolation $h(k, \theta)$, but only determined by the Hamiltonians $h_{1}(k), h_{2}(k)$. Moreover, for any three particle-hole symmetric Hamiltonians $h_{1}(k), h_{2}(k), h_{3}(k)$, it is easy to

prove that the Chern parity satisfies the following associative law:
$$
N_{1}\left[h_{1}(k), h_{2}(k)\right] N_{1}\left[h_{2}(k), h_{3}(k)\right]=N_{1}\left[h_{1}(k), h_{3}(k)\right] .
$$

+ ShunQing Shen Chapter 4 Section 8,9

**4.8 Time Reversal Symmetry and the $\mathbb{Z}_{2}$ Index**

Time reversal symmetry implies that $[\mathcal{H}(\mathbf{r}), \Theta]=0$, where the time reversal operator $\Theta=-i \sigma_{y} K$ and $K$ is the complex conjugation. Note that in the band theory, time reversal symmetry means that
$$
H(-\mathbf{k})=\Theta H(\mathbf{k}) \Theta^{-1}
$$
since the good quantum number $\mathbf{k}$ has already replaced the momentum operator $\mathbf{p}=-i \hbar \nabla$ in the Hamiltonian, and the later changes a minus sign under time reversal $\Theta$. In the Brillouin zone of a square lattice, there are 4 ( 8 for a cubic lattice in three dimensions) time reversal ifarariant points satisfying $-\Gamma_{i}=\Gamma_{i}+n_{i} \mathbf{G}$, where $G$ is a reciprocal lattice vector and $n_{i}=0$ or $1[11,13,17]$. At these points, $\Gamma_{i}=n_{i} \mathrm{G} / 2$
$$
H\left(\Gamma_{i}\right)=\Theta H\left(\Gamma_{i}\right) \Theta^{-1}
$$
always holds; therefore, the eigenstates are always at least doubly degenerate due to the Kramers degeneracy. A pair of such energy bands $E_{2 n-1}(k)$ and $E_{2 n}(k)$ is called a Kramers pair, as illustrated in Fig. 4.3. These two bands (labeled as $(n, I)$ and $(n, I I)$, respectively) are related to each other by time reversal operation accompanying with a phase factor [11]. Their crossings at time reversal invariant points are protected by time reversal symmetry. If a Kramers pair is isolated from other pairs by finite gaps, a topological invariant associated with this pair can be defined.

For simplicity, we consider a one-dimensional system and suppose that there is no additional degeneracy other than those required by time reversal symmetry. Therefore, the $2 N$ eigenstates can be divided into $N$ pairs that satisfy
$$
\left|u_{n}^{I}(-k)\right|=-\mathrm{e}^{i \chi_{k, n}} \Theta\left|u_{n}^{I I}(k)\right|
$$

Then
$$
\Theta\left|u_{n}^{I}(-k)\right\rangle=-\Theta \mathrm{e}^{i \chi k, n} \Theta\left|u_{n}^{I I}(k)\right\rangle=\mathrm{e}^{-i \chi_{k, n}}\left|u_{n}^{I I}(k)\right\rangle
$$
as $\Theta^{2}=-1$ for electrons with spin $\frac{1}{2}$. Thus, one has the relation
$$
\left|u_{n}^{I I}(-k)\right|=\mathrm{e}^{i \chi-k, n} \Theta\left|u_{n}^{I}(k)\right\rangle
$$
The partial polarization associated with one of the categories $s=I$ and $I I$ can be written as
$$
P^{s}=\int_{B Z} \frac{d k}{2 \pi} A_{k}^{s},
$$
with $A_{k}^{s}=i \sum_{n}^{s}\left\langle u_{n}^{s}(k)\left|\nabla_{k}\right| u_{n}^{s}(k)\right\rangle$. It is invariant (up to a lattice translation) under changes in the phases of $\left|u_{n}^{I}(k)\right\rangle$ and $\left|u_{n}^{I I}(k)\right\rangle$. However, they appear to depend on the arbitrary choice of the label $I$ and $I I$ assigned to each band. To make this invariance explicit for $P^{s}$, we separate the integral into two parts:
$$
\begin{aligned}
P^{I} &=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}^{I}+\int_{-\pi}^{0} \frac{d k}{2 \pi} A_{k}^{I} \\
&=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}^{I}+\int_{0}^{\pi} \frac{d k}{2 \pi} A_{-k}^{I}
\end{aligned}
$$
Using the time reversal constraint,
$$
\begin{array}{r}
\left.\left\langle\Theta u_{n}^{I I}(k)\right| \partial_{k}+\Theta+u_{n}^{I I}(k)\right)=-\left\langle u_{n}^{I I}(k)\right| \partial_{k} \\
A_{-k}^{I}=A_{k}^{I I}-\sum_{n} \partial_{k} \chi_{k, n}
\end{array}
$$
It then follows that
$$
P^{I}=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}-\frac{1}{2 \pi} \sum_{n}\left(\chi_{\pi, n}-\chi_{0, n}\right)
$$
where $A_{k}=A_{k}^{I}+A_{k}^{I I}$. Introduce the $U(2 N)$ matrix
$$
w_{m n}(k)=\left\langle u_{m}(-k)|\Theta| u_{n}(k)\right\rangle
$$
Then only nonzero terms are
$$
\begin{array}{l}
\left\langle u_{n}^{I}(-k)|\Theta| u_{n}^{I I}(k)\right\rangle=-\mathrm{e}^{-i \chi_{k, n}} \\
\left\langle u_{n}^{I I}(-k)|\Theta| u_{n}^{I}(k)\right\rangle=\mathrm{e}^{-i \chi_{-k, n}}
\end{array}
$$

The matrix $w$ is a direct product of $2 \times 2$ matrices with $-\mathrm{e}^{-i x i n}$ and $\mathrm{e}^{-i x-t / n}$ on the off-diagonal. At $k=0$ and $\pi, w$ is antisymmetric. An antisymmetric matrix may be characterized by a Pfaffian, whose square is equal to the determinant. Then we have
$$
\frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}=\exp \left[i \sum_{n}\left(\chi_{\pi n}-\chi_{0 n}\right)\right]
$$
Thus,
$$
P^{\prime}=\frac{1}{2 \pi}\left[\int_{0}^{\pi} d k A_{k}+i \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right]
$$
A similar formula can be obtained for $P^{I I}$. It follows from the time reversal symmetry that $P^{I I}=P^{I}$ modulo an integer, reflecting the Kramers pairing of the Wannier states. The charge polarization for one Kramers pair of states is
$$
P_{\rho}=P^{I}+P^{I I}
$$
and the time reversal polarization is defined as
$$
\begin{aligned}
P_{\theta} &=P^{I}-P^{I I} \\
&=\frac{1}{2 \pi}\left[\int_{0}^{\pi} d k A_{k}-\int_{-\pi}^{0} d k A_{k}+2 i \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right]
\end{aligned}
$$
In terms of the matrix $w_{n m}$, the formula can be written in a compact form:
$$
P_{\theta}=\frac{1}{2 \pi i}\left[\int_{0}^{\pi} d k \operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right]-2 \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right] .
$$
In the matrix $w$, only nonzero elements are off-diagonal:
$$
\begin{aligned}
\operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right] &=\operatorname{Tr}\left[\left(\begin{array}{cc}
0 & \mathrm{e}^{-i \chi-k, n} \\
-\mathrm{e}^{i \chi_{k, n}} & 0
\end{array}\right) \nabla_{k}\left(\begin{array}{cc}
0 & -\mathrm{e}^{-i \chi_{k, n}} \\
\mathrm{e}^{i \chi-k, n} & 0
\end{array}\right)\right] \\
&=i \nabla_{k} \chi-k, n-i \nabla_{k} \chi_{k, n} .
\end{aligned}
$$
Using the unitarity of $w$, we have
$$
\operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right]=\operatorname{Tr}\left[\nabla_{k} \ln w(k)\right]=\nabla_{k} \ln \operatorname{det}[w(k)]
$$
Thus, $P_{\theta}$ can be expressed as
$$
P_{\theta}=\frac{1}{2 \pi i}\left[\ln \frac{\operatorname{det}(w(\pi))}{\operatorname{det}(w(0))}-2 \ln \frac{\operatorname{Pf}(w(\pi))}{\operatorname{Pf}(w(0))}\right]
$$

$$
(-1)^{P_{\theta}}=\frac{\sqrt{\operatorname{det}(w(0))}}{\operatorname{Pf}(w(0))} \frac{\sqrt{\operatorname{det}(w(\pi))}}{\operatorname{Pf}(w(\pi))}
$$
In general, for a cyclic process of $H(t+T)=H(t)$, it follows that
$$
\begin{array}{l}
H\left(t_{1}^{*}=0\right)=\Theta H(0) \Theta^{-1} \\
H\left(t_{1}^{*}=T / 2\right)=\Theta H(T / 2) \Theta^{-1}
\end{array}
$$
The change of time reversal polarization is gauge invariant
$$
v=\left[P_{\theta}(T / 2)-P_{\theta}(0)\right] \bmod 2
$$
Consider the mapping between the time reversal invariant momenta $\Gamma_{i}$ and the time invariant point of time $t_{i}^{*}$; we conclude that the topological invariant can be written as
$$
(-1)^{v}=\prod_{i} \frac{\sqrt{\operatorname{det}\left(w\left(\Gamma_{i}\right)\right)}}{\operatorname{Pf}\left(w\left(\Gamma_{i}\right)\right)}
$$
Since
$$
\operatorname{det}\left(w\left(\Gamma_{i}\right)\right)=\left[\operatorname{Pf}\left(w\left(\Gamma_{i}\right)\right)\right]^{2},
$$
the right-hand side of Eq. $(4.115)$ is always $+1$ or $-1$. Correspondingly $v$ is only an integer modulo 2 , that is, 0 or 1 . Thus, the time reversal polarization defines two distinct polarization states, topologically trivial $(v=0)$ and nontrivial $(v=1)$. Fu and Kane proposed thtit the value of $v$ is related to the presence or the absence of a Kramers degenerate states at the end of a finite system [11].

If an insulator has the additional inversion symmetry, there is a simplified algorithm to calculate the $\mathrm{Z}_{2}$ invariant. Suppose that the Hamiltonian $H$ has an inversion symmetry,
$$
H(-\mathbf{k})=P H(\mathbf{k}) P^{-1},
$$
where the parity operator is defined by
$$
P\left|\mathbf{r}, s_{z}\right\rangle=P\left|-\mathbf{r}, s_{z}\right\rangle .
$$
Here $\mathbf{r}$ is the coordinate and $s_{z}$ is the spin which is unchanged by the parity $P$ because it is a pseudovector. An explicit consequence of the combination of time reversal symmetry and inversion symmetry is the fact that the Berry curvature must vanish:
$$
F(\mathbf{k})=\nabla_{\mathbf{k}} \times \mathbf{A}(\mathbf{k})=0
$$
It follows from the definition of the Berry curvature that it is odd under time reversal, $F(-\mathbf{k})=-F(\mathbf{k})$, and even under inversion, $F(-\mathbf{k})=F(\mathbf{k})$. Considering the $m$ th pair of the occupied energy bands at time reversal invariant momentum $\Gamma_{i}$, we define$\left.P\left|u_{2 m,} \Gamma_{i}\right\rangle=\xi_{2 m}\left(\Gamma_{i}\right) \mid u_{2 m,} r_{i}\right)$ where the parity eigenvalues $\xi_{2 m}\left(\Gamma_{i}\right)=+1$ or $-1$. The degenerate Kramers partners share the same eigenvalue $\xi_{2 m}=\xi_{2 m-1}$. In this case, one has a simple formula to calculate 8 [13]:
$$
(-1)^{v}=\prod_{i} \prod_{m=1}^{N} \xi_{2 m}\left(\Gamma_{i}\right) .
$$
In Sect. 3.6, we have already used this result to classify the topological phases in the lattice model.

Note on Pfaffian: In muathematics, a skew-symmetric matrix is a square matrix $A$ whose transpose is its negative, $A=-A^{T}$. The determinant of a skew-symmetric muirix $A$ can always be written as the square of a polynomial in the matrix entries, which is called the Pfaffian of the matrix, denoted by $\operatorname{Pf}(A)$, that is,
$$
\operatorname{det}(A)=\operatorname{Pf}(A)^{2}
$$
The term Pfaffian was introduced by [15] who named it after Johann Friedrich Pfaff. The Pfaffian is nonvanishing only for $2 n \times 2 n$ skew-symmetric matrices, in which case it is a polynomial of degree $n$.
For example,
$\operatorname{Pf}\left(\begin{array}{cc}0 & a \\ -a & 0\end{array}\right)=a$,
$\operatorname{Pf}\left(\begin{array}{cccc}0 & a & b & c \\ -a & 0 & d & e \\ -b & -d & 0 & f \\ -c & -e & -f & 0\end{array}\right)=a f-b e+d c$

**4.9 Generalization to Two and Three Dimensions**

Generalization of the $Z_{2}$ invariant from two to three dimensions is a milestone in the development of topological insulator. The topological invariant characterizing a two-dimensional band structure may be constructed by rolling a two-dimensional system into a cylinder as shown in Fig. 4.4a. Then the magnetic flux threading the cylinder plays the role of the circumferential crystal momentum $k_{x}$, with $\phi=0$ and $\phi=\phi_{0} / 2$ corresponding to two edge time reversal momenta $k_{x}=\Lambda_{1}=0$ and $k_{x}=\Lambda_{2}=\pi / a$. The $Z_{2}$ invariant characterizes the change of the time reversal polarization in the Kramers degeneracy at the ends of the one-dimensional system between $k_{x}=\Lambda_{1}$ and $k_{x}=\Lambda_{2}$. The change is related to the bulk band structure for a two-dimensional system with the periodic boundary condition. For a square lattice, there are four time reversal invariant momenta in the first Brillouin zone:
$$
\Gamma_{n_{x} n_y}=\left(\frac{n_{x}}{2} \mathbf{G}_{x}, \frac{n_{y}}{2} \mathbf{G}_{y}\right)
$$

with $n_{x}, n_{y}=0,1$. For an edge perpendicular to $\mathbf{G}_{y}$, the one-dimensional edge time reversal invariant momenta are $k_{x}=\Lambda_{1}$ and $k_{x}=\Lambda_{2}$, which satisfy $\Gamma_{1, n_{y}}-\Gamma_{0, n_{y}}=$ $\frac{\mathrm{G}_{x}}{2}$. Thus, the time reversal polarization can be expressed as $\pi_{x}=\delta_{x 1} \delta_{x 2}$, where
$$
\delta_{x i}=\frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{i, y}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{i, y}\right)\right]}=\pm 1
$$
However, $\pi_{x}$ is not a gauge invariant. A $k$-dependent gauge transformation can change the sign of any pair of $\delta_{i}$. If we roll the system into a cylinder along another direction, we can calculate the time reversal polarization $\pi_{y}=\delta_{y 1} \delta_{y 2}$. The product $\pi_{x} \pi_{y}$ is gauge invariant:
$$
(-1)^{v}=\prod_{n_{x}, n_{y}=0,1} \frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{n_{x}, n_{y}}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{n_{x}, n_{y}}\right)\right]}
$$
This $v$ can be equal to 0 or 1 and define a single $Z_{2}$ invariant in two dimensions.

The $Z_{2}$ invariant for three-dimensional crystals can be reduced to the problems in two dimensions $[11,14,16]$. The three-dimensional Brillouin zone can be rolled into a donut along the $x$ - and $y$-direction as illustrated in Fig. 4.4c. There are eight time reversal invariant momenta for three-dimensional systems:
$$
\Gamma_{i=\left(n_{1}, n_{2}, n_{3}\right)}=\left(\frac{n_{1}}{2} \mathbf{G}_{1}, \frac{n_{2}}{2} \mathbf{G}_{2}, \frac{n_{3}}{2} \mathbf{G}_{3}\right)
$$
with $n_{j}=0,1$. They can be viewed as vertexes of a parallelepiped. For a fixed $n_{1}$, for example, $n_{1}=1$, the point set
$$
\left(\frac{n_{1}}{2} \mathbf{G}_{1}, \frac{a_{2}}{2} \mathbf{G}_{2}, \frac{a_{3}}{2} \mathbf{G}_{3}\right)
$$
for all $a_{2}, a_{3} \in\left[-\frac{1}{2}, \frac{1}{2}\right.$ ) defines a two-dimensional Brillouin zone of a twodimensional system respecting time reversal symmetry, for which a $Z_{2}$ invariant can be calculated from the method for two-dimensional system, referred as $v_{n 1=1}$. The other five invariants $v_{n_{1}=0}, v_{n_{2}=0,1}$, and $v_{n_{3}=0,1}$ can be defined in a similar way. These six invariants are associated with six planes of the above parallelepiped. Since they belong to the same three-dimensional crystal, only four of them are independent due to the constraints $[11,14]$
$$
v_{n_{1}=0} \cdot v_{n_{1}=1}=v_{n_{2}=0} \cdot v_{n_{2}=1}=v_{n_{3}=0} \cdot v_{n_{3}=1} \bmod 2
$$
The four independent invariants can be chosen as, say, $v_{0}=v_{n_{1}=0} v_{n_{1}=1}, v_{1}=$ $v_{n_{1}=1}, v_{2}=v_{n_{2}=1}$, and $v_{3}=v_{n_{3}=1}$. The indices $v_{0} ;\left(v_{1} v_{2} v_{3}\right)$ reflect the topology of the surface states $[13,17] . v_{0}$ is given by
$$
(-1)^{v_{0}}=\prod_{n_{1}, n_{2}, n_{3}=0,1} \frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{n_{1}, n_{2}, n_{3}}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{n_{1}, n_{2}, n_{3}}\right)\right]} .
$$
If $\nu_{0}=1$, then the system is a strong topological insulator, with an odd number of Dirac cones on all surfaces of the crystal. If $\nu_{0}=0$, then the crystal is a weak topological insulator, with an even number (including 0) of Dirac cones at the surfaces. The latter one is topologically equivalent to a two-dimensional insulator and therefore is not robust against disorder. Let us take $0 ;(001)$ as an example [13]. The surface states corresponding to the two-dimensional Brillouin zone spanned by $G_{2}$ and $G_{3}$ (with index $v_{1}=0$ ) have two Dirac cones, and the same for the surface states in the Brillouin zone spanned by $G_{1}$ and $G_{3}$, with index $\nu_{2}=0$. But there is no surface states in $G_{2}-G_{3}$ plane, with index $v_{3}=1$.

## 謝辞

本ノートはひとまずここで区切りとする。これまで応援してくださった知乎（Zhihu）の皆様に感謝する。この曲折の多い学習経験が皆様の少しでも助けになれば幸いである。共に頑張ろう！
