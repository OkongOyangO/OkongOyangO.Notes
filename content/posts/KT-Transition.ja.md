---
title: "😬KT転移：二次元XY模型、トポロジカル渦と準長距離秩序"
date: 2026-06-30T15:00:00+08:00
draft: false
math: true
tags: ["KT Transition", "XY Model", "Topological Defect", "Vortex", "Condensed Matter"]
categories: ["Physics Notes"]
---

KT転移（Kosterlitz-Thouless Transition）は二次元系における特異なトポロジカル相転移である。通常の相転移と異なり、自発的対称性の破れに依存せず、トポロジカル欠陥——渦（vortex）の束縛-非束縛過程によって駆動される。本稿では二次元XY模型から出発し、KT転移の基本原理を解説する。

<!--more-->

## KT転移の原理

### 二次元XY模型

二次元XY模型では、各格子上に二次元スピン$S_i=(\cos \theta_i,\sin \theta_i)$が割り当てられる。正方格子上の作用は：

$$S[\theta]=-J\sum_{\braket{ij}}S_i \cdot S_j=-J\sum_{\braket{ij}}\cos(\theta_i-\theta_j)$$

以下、高温と低温それぞれの相関関数を計算する。

**高温**（$J\ll 1$）：分配関数を$J$について展開する：

$$
Z=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)e^{-S[\theta]}=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)\prod_{\braket{ij}}\left[1+J\cos(\theta_i-\theta_j)+O(J^2)\right]
$$

相関関数$\braket{S_0\cdot S_x}=\braket{\cos(\theta_0-\theta_x)}\sim e^{-f(J)|x|}$、すなわち短距離秩序。

**低温**（$J\gg 1$）：$\theta$の変化は緩やかであり、連続近似が取れる：

$$S[\theta]\rightarrow \frac{J}{2}\int \mathrm{d}^2 x\left[\nabla\theta(x)\right]^2$$

相関関数を計算すると$\braket{S_0\cdot S_x}\sim x^{-g(J)}$、すなわち準長距離秩序（algebraic order）を得る。

したがって二次元XY模型は有限温度において短距離秩序から準長距離秩序への相転移を示す。この相転移は従来のLandau理論では記述できない——トポロジカル欠陥であるvortexの凝縮によって駆動される。

## Vortex励起とその凝縮

### トポロジカル欠陥とvortex

連続場$\vec{u}(r)=\nabla \theta(r)$を考える。$\theta$の$U(1)$構造（$\theta \equiv \theta + 2n\pi$）により、周回積分：

$$\oint \vec{u}\cdot \vec{\mathrm{d}l}=2n\pi \quad n\in \mathbb{Z}$$

この結果は離散的であり、経路を連続的に変化させても不変である。自明な状態（$\theta$が定数）では周回積分は0である。トポロジカル欠陥を導入すると、$\nabla\theta$は欠陥において定義されなくなる：

$$\nabla \times \vec{u}(\vec{r})=2n\pi \delta^2(\vec{r}-\vec{r_0})\hat{e}_z$$

vortexはトポロジカル荷$n$を担い、その速度場は：

$$\vec{v}(\vec{r};\vec{r}_0,n)= \frac{n}{|\vec{r}-\vec{r}_0|}\left(\hat{e}_z\times \frac{\vec{r}-\vec{r}_0}{|\vec{r}-\vec{r}_0|}\right)$$

### Vortexの自由エネルギー

原点に位置し、荷$n=1$のvortexを考える：

$$S_{\text{vor}}=S_{\text{core}}+\frac{J}{2}\int_0^{2\pi}\mathrm{d}\psi \int_a^L \rho\mathrm{d}\rho \,\vec{u}^2(\rho,\psi)=S_{\text{core}}+\pi J \ln\left(\frac{L}{a}\right)$$

分配関数：

$$Z_{\text{vor}}/Z_0\approx \left(\frac{L}{a}\right)^2 e^{-S_{\text{core}}-\pi J\ln(L/a)}=\exp(-S_{\text{core}}+(2-\pi J)\ln(L/a))$$

vortexの自由エネルギー：

$$F_{\text{vor}}\sim S_{\text{core}}+(\pi J-2)\ln(L/a)$$

$\pi J > 2$のとき、$\ln L$の係数は正であり、単一vortexの自由エネルギーは無限大へ発散する——vortexは閉じ込められる。$\pi J < 2$のとき、vortex自由エネルギーは負となる——vortexが自発的に生成し得る。臨界点は$\pi J = 2$、すなわち$J_c = 2/\pi$に現れる。

### Vortex間の相互作用

それぞれ荷$n_1, n_2$を持つ二つのvortex間の相互作用エネルギーは：

$$V_{int} = -2\pi J n_1 n_2 \ln\left(\frac{|\vec{r}_1-\vec{r}_2|}{a}\right)$$

異符号のvortexは互いに引き合い（対数ポテンシャル）、同符号のvortexは互いに反発する。低温では正負vortexが束縛対を形成し、系は準長距離秩序を維持する。高温ではvortex対が非束縛となりvortexプラズマを形成し、系は無秩序となる。

## KT転移の実験的検証：二次元超伝導薄膜

実験では$\mathrm{Hg}-\mathrm{Xe}$合金の高薄層抵抗均質薄膜を用いてKT転移が検証された。

二次元超伝導におけるvortex-反vortex対の束縛-非束縛は、XY模型のKT転移理論に直接対応する。実験では$I-V$特性の測定を通じて渦-反渦相互作用を間接的に反映する。$T_c$近傍における$V(I)$の詳細な解析は、渦相互作用の空間繰り込み群理論予測と合理的な一致を示した。

$\log-\log$プロット上の傾き$a(T)$は対数相互作用の前因子の尺度である。$a(T_{c0})=1$の外挿と$a(T_c)=3$の設定により、vortex非束縛温度$T_c$が決定される。実効誘電率$\epsilon_c = n_s^0 / n_s^R = 1.2 \pm 0.1$は理論予測と一致する。

## まとめ

KT転移は純粋にトポロジカルな相転移であり、対称性の自発的破れを伴わない。その本質は二次元系におけるvortex-反vortex対の束縛-非束縛過程である。低温では準長距離秩序（algebraic order）、高温では無秩序相となる。KT理論は二次元XY磁性体のみならず、二次元超伝導薄膜、二次元液晶など広範な系に適用される。
