---
title: "😮QHE(4)｜从量子霍尔到拓扑绝缘体到Chern-Simons理论与拓扑分类"
date: 2022-06-10T10:00:00+08:00
draft: false
math: true
tags: ["IQHE", "Topological Insulator", "Chern-Simons", "Berry Phase", "Condensed Matter"]
categories: ["Physics Notes"]
---

距离接触凝聚态理论中的拓扑已经过去一年，零零碎碎读了不少文献，下面想做一个梳理，试图为今后可能要接触这一领域的读者，理清一些学习过程中的主线。

整数量子霍尔效应为凝聚态开启了一个新的领域，然而这只是拓扑在凝聚态中的冰山一角，我们将看到，IQHE事实上是**二维的、有能隙的、无相互作用的、费米的、无时间反演对称性（TRS，Time-Reversal Symmetry）、无粒子-空穴对称性（PHS，或Charge Conjugate Symmetry）、无手性对称性（Chiral Symmetry）**的系统的拓扑效应。

<!--more-->

事实上，我们将上述的定语：【维度】【是否有能隙】【是否有相互作用】【费米/波色】【时间反演对称性】【粒子-空穴对称性】【手性对称性】进行替换，将可能得到及其丰富的拓扑效应，以至于一部分体系拓扑分类的研究仍是前沿研究的热点。

初学时，我们往往会对不同的量子霍尔效应的组合命名产生兴趣，比如（整数）量子霍尔效应、量子自旋霍尔效应、量子反常霍尔效应等现象，但事实上，按照上述维度、对称性等定语进行的分类更有普适性。

如Prof. Zhaihui在课上说过的："不要将物理学成terminology，要更关注这些term后面的物理。"

## Reference

我先将我参考的资料在这里列出，我按照我有限的理解水平给它们做了一个粗略的难易程度分类，希望对读者的资料参考提供一定帮助。

总体而言，我认为这个部分的学习需要循序渐进，同时多换着看材料，避免对材料审美疲劳。

知乎上也有很多巨佬提供了笔记和一些review，这里列一下我个人有限搜索能力下看到的一些对我而言比较友好并且比较inspiring的文章。

@Boltzlinn的论文导读：

https://zhuanlan.zhihu.com/p/61559924

@拉格朗日的文章：

https://zhuanlan.zhihu.com/p/77270930

首先推荐的是Prof. SC Zhang在SITP的一个关于Topological Insulator的talk，B站有字幕，油管的SITP官方账号也有完整版。Prof. SC Zhang用通俗的语言向各种专业的学者解释了拓扑绝缘体的物理和应用前景，这对于初涉该领域的读者应该是很inspiring的。

https://www.bilibili.com/video/BV1t7411W7Eq?spm_id_from=333.337.search-card.all.click&vd_source=ba9ae3c860748ec9008f01f641bd9bf8

https://www.youtube.com/watch?v=dCQ7CAQ4Npc

https://www.youtube.com/watch?v=sbJSAOngiGI&t=691s

下一步我推荐的是Hasan & Kane关于拓扑绝缘体和拓扑超导体的综述，其中公式不多，列举了很多理论和实验方面的结论，适合学过能带论的读者进一步激起对这个领域的兴趣，感受拓扑能带论（Topological Band Theory）的魅力。但不建议死磕在某一些细节上，读一两遍能够掌握大意即可，之后学了更多可以回来再巩固，应该更有收获。

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.82.3045

@Lord Hart的专栏对Hasan & Kane关于拓扑绝缘体和拓扑超导体的综述做了翻译，大家可以前去围观。

https://www.zhihu.com/column/condensematterphysics

之后我的建议是多做一些定量的计算和公式推导，从QHE出发，首先推荐David Tong的QHE讲义的Chap1 和 Chap2，能够理解Berry Phase这一重要工具以及线性响应理论给出的Hall Conductance表达式中的Berry Curvature和Chern Number项即可。

http://www.damtp.cam.ac.uk/user/tong/qhe.html

我们更加严谨分析了QHE中理论上存在的拓扑效应，更多种类的推导可以参考上一章我写的note。

https://zhuanlan.zhihu.com/p/486890623

此外给拓扑绝缘体的初学者们提供一个有用的网站，这里面的内容对初学者也十分友好。

https://topocondmat.org/index.html

之后的内容大概就是接下来几章note我想总结的，即更systematic地去分析无相互作用、绝缘（有能隙）费米系统的拓扑分类。

首先我认为应当系统地学习拓扑能带论，为此主推两本书，其中也包含了对于QHE的分析，希望进一步系统学习的读者也可以从这两本书开始读起：

+ 一本是Bernevig & Taylor Hughes的'Topological Insulator and Superconductor'。这本书的特点是推导严谨，例如第三章就会将lattice费米系统的线性响应理论分析的十分透彻，推出电流算符的表达式，并且极其暴力地用magnetic BZ的方法推导量子霍尔效应，但可能会把初学者（指我）吓坏，同时让初学者（指我）在疯狂的公式推导中逐渐偏离原先的物理图像，最后emo（指我），所以建议大家前面几章以及后面4D Topological Insulator的几章可以适当从简阅读，之后把它当成XL Qi, Taylor Hughes, SC Zhang的拓扑场论（Topological Field Theory）的补充材料，将会很有帮助。
+ 另一本是ShunQing Shen老师的"Topological Insulators: Dirac Equation in Condensed Matters"一书。这本书的新奇之处在于，其开篇从Dirac Equation的角度去分析能带中的gap closing & reopening对于系统能带拓扑性质的转变，并且严谨地推导了边缘态、$\mathbb{Z}_2$数等一系列之前综述中比较定性的结论，对于进一步从理论上理解拓扑绝缘体的拓扑性质很有裨益。
+ 此外Prof. Zhaihui的'Ultracold Atomic Physics'一书的第七章也专门介绍了简单的2能带系统的拓扑能带论，由于二能带系统的波函数可以用Bloch Sphere上的单位矢量来描述，所以其拓扑本质将更为突出，我也是在翟老师的课上对拓扑能带论的理解有了较大的突破。

通过上面的内容，读者们会对拓扑能带论有了更系统的认知，这时便会对前面综述中或多或少会提到的topological classification有所兴趣，这里我们要考虑对称性和维度在拓扑分类中的作用，这里推荐Ching-Kai Chiu, Jeffrey C. Y. Teo, Andreas P. Schnyder, and Shinsei Ryu的综述。

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.88.035005

Yau Mathematical Sciences Center的Qingrui Wang在拓扑序方面的网课，初学者可以先看Lec5-Lec7讲的Fermionic SPT Phase的内容。

https://qr-wang.github.io/teaching_2021_TQM.html

再进一步，若读者有一定的量子场论或凝聚态场论基础，也可以参考XL Qi, Taylor Hughes, SC Zhang的拓扑场论（Topological Field Theory）论文，其中引入Chern-Simons term的有效理论将拓扑绝缘体推广到了4维等更高维度，如前所述，Bernevig & Taylor Hughes的'Topological Insulator and Superconductor'可以作为这篇文章的补充内容。

http://journals.aps.org/prb/abstract/10.1103/PhysRevB.78.195424 

拓扑与场论的内容便不过多赘述，只要有一些同伦伦和路径积分的基础即可，这里可以稍微列一下场论相关的推荐：
+ QFT: Peskin，Weinberg，Schwartz，Coleman，A Zee，David Tong (Lec. Note)
+ CMPFT: Roger Melko (Online Course)，Altland，Fradkin，Xiaogang Wen(文小刚)，Nagaosa: QFT in CMP，QFT in Strongly Correlated Electronic System

## From IQHE to Chern Insulator：Time-Reversal Breaking

一切都是循序渐进的，历史上，刚发现IQHE时，需要极大的磁场使得费米能之下Landau能级的数量只有若干个的量级，只后人们在寻找无需强磁场的IQHE的过程中，Haldane提出了在Honeycomb lattice上加周期磁场，使得TRS被破坏但总体磁场为0，这便得到了无需外场的IQHE，或者称为Chern Insulator。Chern Insulator与加外磁场的IQHE一样，是**二维的、有能隙的、无相互作用的、费米的、无时间反演对称性（TRS，Time-Reversal Symmetry）、无粒子-空穴对称性（PHS，或Charge Conjugate Symmetry）、无手性对称性（Chiral Symmetry）**的系统的拓扑效应，磁场的作用被吸收进了"Time-Reversal Breaking"这一条件里。

在Chern Insulator的分析中，没有外磁场，我们不需要用之前提到的Magnetic BZ的方式去计算系统的Hall响应，而是对系统的BZ和所有填满的能带的Berry Curvature进行积分，由于破坏了TRS，故在一定的hopping、chemical potential下我们不加磁场也可以得到非零的TKNN invariant（Chern number）。

Hall效应可以用各种微扰的方法计算，上一节就这一点进行了详细讲解，这里不再赘述，总体而言，所有的证明方法都是某种微扰论下计算系统的线性响应，所以完全可以用最general的Linear Response Theory将其统一，最终的Hall Conductance也可以用Kubo Formula计算。

另一方面，Berry Connection $\mathcal{A}$ 以及Berry Curvature $\mathcal{B}$ 是定义在BZ上的(Abelian) gauge field（提到Abelian说明之后还有更general的Non-Abelian gauge field带来的4D topological insulator等等..）在BZ（$\mathbf{T}^2$）上的quantization几乎完全是拓扑效应。在惊叹于Hall Conductance的表达式与Chern number公式的一致性时，我们可以反过来思考，用不同维度的gauge field的拓扑性质（Chern-Simons Theory），去寻找与这个已知的拓扑性质对应的物理效应。遵循这种思路，理论学家成功预言了4D TI和3D Half-IQHE和3D 磁电效应等更多物理中的拓扑效应。

## From 2D TRB to 1D PHS: Topology in Different Dimensions 

继Chern Insulator之后，理论学家们期待更丰富的拓扑效应。本小节尝试从Chern Insulator出发，考虑Chern number在1维系统中的拓扑效应。

在上一章的Laughlin Argument中，我们发现可以通过给Cylinder加磁通，从而将一个维度上的$k_y$替换成正则动量$k_y+A_y$，之后缓慢的tune这个正则动量，系统的spectrum发生周期性变化。此时$k_y$事实上已变成一个参数，而系统则是与这个参数相关的x方向上的一维系统，这是Dimensional Reduction的基础。

$$ H=\sum_{k_{y}} H_{1 \mathrm{D}}\left(k_{y}+A_{y}\right) $$

加磁通相当于加入矢势，这样能保持空间平移对称性。

$$ A_y = -E_y t \quad A_x = 0$$

来考虑2D TRB Chern Insulator降维之后，Chern number与一维系统物理效应的对应。此处的物理效应是$\mathbb{Z}_2$Quantized Charge Polarization。

2D Hall 效应给出 Hall电流：

$$ j_x = \sigma_H E_y $$

由电荷守恒

$$ \partial_t \rho + \nabla \cdot j = 0 $$

高斯定理

$$ \nabla \cdot D = \nabla \cdot (P + \epsilon_0 E) = \rho$$

从而在差一个散度项的情形下有

$$ j = \partial_t P $$

$$ \Delta P = \int_0^T dt \ j $$

另一方面，紧束缚模型的电流为用正则动量$k_y + A_y$为参数的1D模型的电流之和

$$ J_{x}=\sum_{k_{y}} J_{x}\left(k_{y}\right) $$

此时经过$\Delta t=2 \pi / L_{y} E_{y}$后被pump的电荷量为：

$$ \Delta Q=\int_{0}^{\Delta t} d t \sum_{k_{y}} J_{x}\left(k_{y}\right) \equiv \sum_{k_{y}} \left. \Delta P_{x}\left(k_{y}\right)\right|_{0} ^{\Delta t}$$

经过$\Delta t$时间，spectrum正好经历一个周期，而占据态的量子数是绝热变化，$k_y \rightarrow k_y - 2\pi/L_y$，

$$ \Delta P_{x}\left(k_{y}\right)=P_{x}\left(k_{y}-2 \pi / L_{y}\right)-P_{x}\left(k_{y}\right) $$

热力学极限下，

$$ \Delta Q=-\oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}}  \quad J_{x}\left(k_{y}\right)=d P_{x}\left(k_{y}\right) / d t $$

结合量子Hall效应：

$$ \Delta Q=\sigma_{H} \Delta t E_{y} L_{y}=2 \pi \sigma_{H} $$

我们发现了2D Chern number的量子化对应一个1D charge pump系统的sum rule，即用$k_y$描述的1D系统$H_{1 \mathrm{D}}\left(k_{y}\right)$满足：

$$ \Delta P = \oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}} = - 2\pi \sigma_{H} = -C_1$$

这说明如果将2D Bloch Hamiltonian的一个$k$改成随时间演化的绝热parameter，则经过一个周期后，系统Polarization的变化是Chern number Quantized。

但这几乎只是把Chern number表达式中BZ一个维度的k积分理解成t的变化，这么看来结果也很显然，而且这对应了一个2D系统所有parameter间隔为$2\pi/L_y$的贡献，只能说这给出了一个用$k_y$作为parameter描述的1D系统Polarization的sum rule。

Polarization也可以用下式来定义：

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

其中利用了Wannier Function的定义：

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

这里可以看出，Polarization可以由Berry Connection这一Gauge Field定义，但由于Gauge Field在BZ伤的拓扑效应，作Gauge Transformation后$P$能够变化整数倍，即$\oint dk \cdot A(k)$的换路积分在规范变化下可以改变$2\pi$的整数倍。

进一步，我们将$k_y+A_y$换成$\theta$，则Polarization可以写成

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

原先的2D Bloch Hamiltonian可以看成$\theta$为parameter的1D Bloch Hamiltonian。下面我们引入对称性，看看这个1D拓扑效应的"半成品"——sum rule：

$$ -\oint_{0}^{2 \pi} d \theta \frac{\partial P_{x}\left(\theta\right)}{\partial \theta} = C_1 $$

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

或写成以下形式：

$$ G(\theta) =-\oint \frac{d k_{x}}{2 \pi} f_{x \theta}\left(k_{x}, \theta\right) =\oint \frac{d k_{x}}{2 \pi}\left(\frac{\partial a_{x}}{\partial \theta}-\frac{\partial a_{\theta}}{\partial k_{x}}\right)
$$
$$
\int G(\theta) d \theta=C_{1} \in \mathbb{Z}
$$

能否进一步帮助我们对1D系统进行拓扑分类，其中$a$为Berry Connection，$f$为Berry Curvature。

+ 引入对称性

我们希望得到新的拓扑分类，或者说，我们希望P的取值是量子化的，那么我们就必须给一维系统引入对称性。此处引入的对称性为粒子-空穴对称性（Particle-Hole Symmetry），或者说是电荷共轭对称性（Charge Conjugate Symmetry）

$$ H=\sum_{k} c_{k}^{\dagger} h(k) c_{k}=\sum_{k} c_{-k} C^{\dagger} h(k) C c_{-k}^{\dagger} $$

$$ \Rightarrow C^{\dagger} h(-k) C=-h^{T}(k) $$

考虑两个1D Bloch Hamiltonian：

$$ h(k, 0)=h_{1}(k), h(k, \pi)=h_{2}(k) $$

并要求原先的2D Bloch Hamiltonian也满足PHS：

$$ h(k, \theta)=-\left(C^{-1} h(-k, 2 \pi-\theta) C\right)^{T} $$

可以用2D Bloch Hamiltonian定义Chern number：

$$ C[h(k, \theta)]=\oint d \theta \frac{\partial P(\theta)}{\partial \theta} $$

这里1D系统的Polarization也可以用下式来定义：

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

其中利用了Wannier Function的定义，即实空间中的波函数：

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

这里可以看出，Polarization可以由Berry Connection这一Gauge Field定义，但由于Gauge Field在BZ上的拓扑效应，作Gauge Transformation后$P$能够变化整数倍，即$\oint dk \cdot A(k)$的换路积分在规范变化下可以改变$2\pi$的整数倍。

改写上述Polarization定义，改成自然单位制：

$$ P(\theta)=\oint \frac{d k}{2 \pi} \sum_{E_{\alpha}(k)<0}(-i)\left\langle k, \theta ; \alpha\left|\partial_{k}\right| k, \theta ; \alpha\right\rangle $$

利用PHS：

$$ h(-k, 2 \pi-\theta) C|k, \theta ; \alpha\rangle^{*}=-E_{\alpha}(k) C|k, \theta ; \alpha\rangle^{*} $$

可以证明【可以参考Xiaoliang Qi的拓扑场论论文，我将证明放在最后】

$$ P(\theta)= -P(2 \pi-\theta) $$ 

从而

$$ \int_{0}^{\pi} d P(\theta)=\int_{\pi}^{2 \pi} d P(\theta) $$

利用1D PHS系统的这个性质（注意PHS十分重要，否则P是modulo 1定义的一个任意值，而非量子化的），进一步可以定义Relative Chern Number：

$$ N_{1}\left[h_{1}(k), h_{2}(k)\right]=(-1)^{C[h(k, \theta)]}$$

我们把和trivial 1D band之间relative Chern number为0的模型称为 topologically trivial insulator，将和trivial 1D band之间relative Chern number为1的模型称为topological insulator。这就得到了$\mathbb{Z}_2$的拓扑分类。【这里同样只提了结论，详细推导也在Xiaoliang Qi的拓扑场论论文中，为参考方便我也放在本note最后】

## From Chern Insulator to Topological Insulator: Topology with Different Symmetries

根据我们上面的思路，除了维度的改变之外，我们发现Chern Insulator这一generalization说明**对称性**与拓扑分类的关系十分密切，我们期待在其它对称性的系统中找到类似的拓扑效应（也许是另一种量子霍尔效应）。在同属二维系统，但有TRS的系统中找到的便是Topological Insulator。由于TI有时被用作总称，我们也根据其对应的物理效应——量子自旋霍尔效应，将其称为QSH Insulator。

事实上，2D TRS系统的拓扑分类也是通过高维的母系统降维(4D$\rightarrow$ 3D $\rightarrow$ 2D)，并引入对称性得到的，但对初学者而言过于复杂，个人建议借上节提到的Polarization，以及接下来提到的Pfaffian 和 $\mathbb{Z}_2$-index 来一窥2D TI的拓扑效应。

TRS要求Bloch Hamiltonian满足：

$$ \mathcal{T} h(\mathbf{k}) \mathcal{T}^{-1} = h(-\mathbf{k}) $$

观察具有TRS的体系的能带，则当$\mathbf{k} = - \mathbf{k}\ mod \ \mathbf{\Gamma}_i$时，其中$\mathbf{\Gamma}_i$为倒格矢，会发生简并，即$|n,\mathbf{k}\rangle$与$\mathcal{T}|n,\mathbf{k}\rangle$均有$E_n(\mathbf{k})$的能量且正交，这还需要满足spin-1/2系统$\mathcal{T}^2 = -1$的要求。这便是著名的Kramer Degeneracy。

同时对于一般的$|n,\mathbf{k}\rangle$，其时间反演$\mathcal{T}|n,\mathbf{k}\rangle$将对应$-\mathbf{k}$的相同能量，故能带相对与$k=0$点有镜像对称性。

这样每两条带就会有类似$\infty$的交叠，由于这种对称性，当我们尝试将Chern number的计算公式照搬时，就会发现在TRS系统中的Berry Curvature每两条带的积分便会相互抵消。

我们不妨给这种有Kramer Degeneracy的能带分成两类，将第2n-1和第2n条能带理解为spin-up/down对应的能带，称为$n-I,II$带。

先考虑一维系统，我们能够计算$I,II$带的Polarization，由于TRS，我们不能从原先的$P = P^I + P^{II}$中得到有用信息，我们可以考虑Time-Reversal Polarization：

$$ P_s = P^I - P^{II} $$

经过Shunqing Shen拓扑绝缘体4.8节的推导，我们能够用位于TRIM（Time-Reversal Invariant Momentum）的$w_{m n}(k)=\left\langle u_{m}(-k)|\Theta| u_{n}(k)\right\rangle$的Pfaffian和Determinant来计算一个$\mathbb{Z}_2$数。

推广到2D和3D时，我们将2D视为x方向1D系统的一个连续变换，我们考察$k_y=0$与$k_y=\pi$处1D系统的$\mathbb{Z}_2$数的变化，即可定义一个新的$\mathbb{Z}_2$数，同样的做法可以定义3D系统的$\mathbb{Z}_2$数。

+ 由于Pfaffian的计算需要我们给Bloch波函数定义一个再BZ上连续的规范，这非常复杂，若系统有Inversion Symmetry（IS），此时可以根据TRIM点波函数的Parity，给出$\mathbb{Z}_2$数的简易定义。这在Bernevig的拓扑绝缘体一书中的Chap12有详细介绍。
+ 值得注意的是，最简单的non trivial QSH需要两个Haldane Model，一个自选向上，一个自选向下，并且不同Spin的能带（此处的$I,II$带）对应不同的Spin Chern Number，这样$\mathbb{Z}_2$数便是Spin Chern Number的差mod 2。这种情况要求自旋守恒，条件苛刻，但便于理解；而我们上述对于$\mathbb{Z}_2$数的讨论仅涉及Spin引入的自由度导致能带数量增多，不涉及每个能带具体对应何种方向的自旋，从而$\mathbb{Z}_2$数的定义具有普适意义。
+ 事实上，Topological Insulator往往需要引入Spin-Orbit Couping项，它保护了系统的TRS，给系统的不同spin一定的"磁场"效应，同时也可能破坏了Spin Conservation。

## From Lattice Model to Continuum Model: Dirac Equation and Edge Mode

我们发现拓扑相变几乎都来自gap closing和reopening，这个过程与massive Dirac Fermion的质量变化过程很类似，我们可以用不同维度的Dirac Fermion来描述系统能带的局域特征，从而描述系统的拓扑相变。

这是合理的，因为同一个拓扑相是不在意能带细节的，仅当能带出现奇点时拓扑性质会发生不连续的变化，例如拓扑不变量的跳变。

同时也要注意，Dirac Fermion只能描述局部的能带特征，在较远处的色散将发散，这与BZ的周期边界条件不可避免地会产生矛盾，同时也会产生一些物理效应：例如3D TI中的Dirac Fermion不能只有单独一个Dirac Cone等。

Prof. ShunQing Shen的拓扑绝缘体一书的第2章在这方面做了非常详尽的阐述，十分建议读者进一步研究。我们将看到有开边界的非平庸拓扑绝缘体将有robust的拓扑边界态，且其色散近似线性，这也是可以从Dirac方程中推导出的，具体而言，我们将开边界那一侧的$k_i$替换成$-i \partial_i$从而求解long-range范围内的实空间波函数，及其对应的能量（表面态色散关系），一般来说高维的系统只能微扰求解，但我们仍能看到小范围内的线性色散，这说明实空间的波函数是朝一个方向移动的，这样的解析结果对于理解边缘态的存在及其色散关系便足矣，外加各种微扰会极大地distort色散关系的形状，但我们可以相信，没有gap closing，能带的拓扑是不变的，对应的边缘态也是robust的，这便是拓扑绝缘体中很重要的**体边对应**（Bulk-Edge Correspondence）的精髓。

进一步观察2D Chern Insulator和Topological Insulator，我们能得到Chiral和Helical的边界态。

此处的Chiral指旋转方向一致，例如左边的边界态有向下的群速度，右边的边界态有向上的群速度，对应Chern Insulator/IQHE；此处的Helical指的是边界态的旋转方向和自旋方向的锁定，例如自选向上是顺时针的，自选向下是逆时针的，对应Topological Insulator/QSHE。

## Transport Property: Landauer Formalism

由于Edge Mode对于杂质等微扰是robust的，所以可以视作无back scattering的一维通道，从而通过Landauer Formalism可以分析2端、4端、6端系统在实际测量中的物理响应，这对于分析如何实验探测这些非平庸的拓扑边缘态和实验上对材料进行拓扑分类是很有必要的。

具体的可以参见Prof. ShunQing Shen拓扑绝缘体的6.3节。

## From Tight-Binding Models to Effective Field Theory: Chern-Simons Term

Xiaogang Wen在其多体物理教程的最开头便介绍了路径积分formalism，并且强调了有效理论的重要性，这里建议读者们前往阅读Xiaogang Wen的多体物理第二章。

路径积分的大致精神是，给经典相空间中的每一条路径$\phi=\phi(t)$（可以是粒子的路径，也可以是场的路径）都赋予一个"概率" $e^{S[\phi(t)]}$，其中$S[\phi(t)]$对应这条路径的作用量，故只要写出经典系统的Lagrangian，就可以用路径积分得到其量子版本。

场论的应用范围是极广的，我们只要将系统所有自由度的动力学变量都纳入考虑，写成一个大的Lagrangian，在用路径积分将其量子化，之后的一些可观测量便可以用加一个外场$j(x)$与$\phi$场耦合，再用functional derivative等方式求出。

$$ \langle \phi(x) \rangle = \frac{1}{\mathcal{Z[j]}}\left. \frac{\delta \mathcal{Z}[j]}{\delta j(x)}  \right|_{j=0} $$

$$ \mathcal{Z}[j] \equiv \int \mathcal{D}\phi e^{S[\phi]+ \int d^d x \phi(x)j(x)} $$

但这样的理论有点像Theory of Everything，事实上我们只关心部分的自由度对应的可管测量、关联函数。既然如此，不妨将我们不关心的这部分先进行路径积分。

$$\int \mathcal{D}\phi ( \int \mathcal{D}\psi e^{S[\phi,\psi]} ) = \int \mathcal{D}\phi e^{S_{eff}[\phi]}$$

这并不影响各种期望值的计算，因为$\mathcal{Z}$的定义并未因此改变。

再来考虑这么做的物理意义，这说明，我们对不关心部分的积分的贡献，使得系统完全由只含我们所关心的$\phi$场的一个有效作用量，以及对应的等效场论所描述。

这是十分重要的，凝聚态中，我们往往关注系统的低能激发、响应，因此我们可以将高能部分作路径积分，得到低能部分场的有效理论。这也是重整化群理论的精髓：我们不断将高能的部分积分掉，观察$S_{eff}$中描述系统的参数，例如质量、相互作用强度随着我们截断$\Lambda$的变化，由于大量的参数随着$\Lambda \rightarrow 0$会趋于0，说明这些参数基本不影响低能的物理现象，最终我们只要研究那些不趋于0的极少量参数，就可以描述原先被各种各样取值参数所描述的复杂多体系统的低能理论，这是我们研究多体系统中**普适性**的理论基础！

想想为什么水的连续相变和顺磁-铁磁相变有基本相同的临界指数$\beta$，虽然描述他们的模型的参数肯定大相径庭，但在我们不断积掉高能部分的过程中，最终留下的只有极少数重要的参数，从而描述他们低能理论的模型将惊人的相似。如果只剩下场的二次项和四次项，那么landau平均场模型将预言所有这样的低能模型都有相同的临界指数$\beta=1/2$。此处，我们不在意的是高能的场，我们也可以不关注电子对应的费米场，不关注与系统耦合的环境声子场等等，我们做的只是将其在路径积分中先积分掉。

说完了有效理论的重要性后，我们来看IQHE的有效场论。

IQHE的有效场论是怎么来的？首先，描述系统的Hamiltonian中有各种费米子产生湮灭算符，回忆一下量子场论或凝聚态场论，其路径积分量子化是将所有的$c^\dagger,c$替换成Grassmann number$\bar{\psi},\psi$后进行路径积分。同时考虑到系统中有外加的电磁场，做Peierls Substitution将gauge field引入哈密顿量从而引入。

根据有效理论，我们将费米场的自由度作路径积分，与A有关的部分吸收到一个等效的作用量$S_{eff}$中，这便得到了拓扑绝缘系统中规范场A的有效理论。

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

根据这个有效场，我们可以计算系统的响应，根据

$$ e^{i S_{\text {eff}}[A]} = \int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H_0[c,c^\dagger] \right] + \int d^d x \ j\cdot A} $$

我们作functional derivative，便有了系统的线性响应

$$ j = \frac{\delta S_{eff} [A]}{\delta A} $$

现在我们反过来，根据QHE来反推系统的有效作用量，我们发现

$$
j^{\mu}=\frac{C_{1}}{2 \pi} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

从而可以验证下式便是Chern Insulator的有效作用量

$$
S_{\mathrm{eff}}=\frac{C_{1}}{4 \pi} \int d^{2} x \int d t A_{\mu} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

我们发现这一项有规范不变性，我们将其称为Chern-Simons term。我们要注意的是，有效理论已经积掉了之前费米系统的信息，因此有效理论没法给出$C_1$的来源。

+ 研究分数量子霍尔效应时，我们也可以用完全类似的方法构造有效作用量。


## From Chern-Simons Term to 4D TI: 2nd Chern Number

现在我们来考虑一个4维的系统，我们设想相同的Chern-Simons term也可以在4维系统中找到，只要求其对应的运动方程，我们就得到了4维TI的拓扑响应。更多细节可以看XL Qi的综述和Bernevig的拓扑绝缘体一书的第13章。

其中，4D TI的有效作用量为

$$
S_{\mathrm{eff}}=\frac{C_{2}}{24 \pi^{2}} \int d^{4} x d t \epsilon^{\mu \nu \rho \sigma \tau} A_{\mu} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

从线性响应的角度，2nd Chern number为：
$$
C_{2}=-\frac{\pi^{2}}{15} \epsilon^{\epsilon \mu \rho \sigma \tau} \int \frac{d^{4} k d \omega}{(2 \pi)^{5}} \operatorname{Tr}\left[\left(G \frac{\partial G^{-1}}{\partial q^{\mu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\sigma}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\tau}}\right)\right.
$$

而从Berry Phase拓扑的角度，2nd Chern number为：

$$
C_{2}=\frac{1}{32 \pi^{2}} \int d^{4} k \epsilon^{i j k \ell} \operatorname{tr}\left[f_{i j} f_{k \ell}\right]
$$
$$ f_{i j}^{\alpha \beta}=\partial_{i} a_{j}^{\alpha \beta}-\partial_{j} a_{i}^{\alpha \beta}+i\left[a_{i}, a_{j}\right]^{\alpha \beta} $$
$$
a_{i}^{\alpha \beta}(\mathbf{k})=-i\left\langle\alpha, \mathbf{k}\left|\frac{\partial}{\partial k_{i}}\right| \beta, \mathbf{k}\right\rangle
$$
where $i, j, k, \ell=1,2,3,4$.

求运动方程，可以得到此项有效作用量对应的电流密度：
$$
j^{\mu}=\frac{C_{2}}{8 \pi^{2}} \epsilon^{\mu \nu \rho \sigma \tau} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

值得注意的是，由于此时对外场A的一阶functional derivative得到的结果含有A的二阶项，与2D的Chern-Simons term不同，4D的Chern-Simons term对应的拓扑磁电效应等现象为非线性响应。

我们考虑一个具体的例子：
$$
A_{x}=0, A_{y}=B_{z} x, A_{z}=-E_{z} t, A_{w}=A_{t}=0
$$
则$F_{x y}=B_{z}$ and $F_{z t}=-E_{z}$，可以求出4维电流密度的表达式：

$$ j_{w}=\frac{C_{2}}{4 \pi^{2}} B_{z} E_{z} $$

或写成xy平面上的Hall电流，此时需要z方向的磁场和电场：
$$
\int d x d y j_{w}=\frac{C_{2}}{4 \pi^{2}}\left(\int d x d y B_{z}\right) E_{z} \equiv \frac{C_{2} N_{x y}}{2 \pi} E_{z}
$$

## From 4D TRB to 3D TRI: Dimensional Reduction and $\mathbb{Z}\rightarrow\mathbb{Z}_2$ Again

我们通过4D Chern-Simons term得到了TRB TI在4维的推广，及其topological invariant，即2nd Chern Number。

我们对4维系统作Dimensional Reduction，可以得到该母模型对应的3D TRI(Time-Reversal Invariant) TI的子模型，通过引入TRS，我们将一次得到了$\mathbb{Z}_2$的拓扑分类。

而具体分析3D TI的物理模型，能够得到诸如Surface Half QHE和拓扑磁电效应等一系列新奇的拓扑现象。

更多内容可以参见Bernevig书的第14、15章，以及XL Qi的拓扑场论论文之后的部分

## From Specific to Arbitrary: Period Table and SPT Phase

我们已经认识到维度和对称性在拓扑中的重要性，我们可以将"存在保持某一对称性的连续变化将两个模型相连"这一条件作为拓扑分类的依据，事实上这与拓扑中的同伦定义不谋而合，这也是SPT(Symmetry Protected Topological) Phase的来源，即由特定对称性保护的拓扑相。

而通过Dimensional Reduction我们能得到同种拓扑不变量在不同维度之间（做一些对称性改变后）的拓扑效应。

因此，我们考虑一个最General的模型，并分析其对称性。这看似十分复杂，但事实上我们只需研究Anti-Unitary的对称性，因为有Unitary对称性的系统总能作直积分解，从而得到不具有Unitary对称性的对角块。

如果我们进一步考虑local的对称性，则Altland已将其分为10种，这便是Periodic table代表系统对称性那一侧的10种对称性组的来源。这10个对称性组又来自三种最基本的对称性：时间反演对称性（TRS）、粒子-空穴对称性（PHS）和手性对称性（CS）

作Dimensional Reduction时，我们需要加入特定的对称性，例如2D TRB Chern Insulator到1D需要引入PHS才能将Charge Polarization进行$\mathbb{Z}_2$量子化、4D TRB TI到3D TRI TI引入了TRS才获得类似的$\mathbb{Z}_2$量子化。

Yau Mathematical Sciences Center的Qingrui Wang在拓扑序方面的网课，其中Lec5-Lec7讲的Fermionic SPT Phase的内容。里面较系统地介绍了上述的Periodic Table是如何形成的。

https://qr-wang.github.io/teaching_2021_TQM.html

Ching-Kai Chiu, Jeffrey C. Y. Teo, Andreas P. Schnyder, and Shinsei Ryu的综述也有详细的讲述。

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

## 致谢

本note再次告一段落，感谢知乎各位朋友至今为止的支持，希望我这段曲折的学习经历能给你们带来一点帮助，共勉！
