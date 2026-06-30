---
title: "🫠ツイスト二層グラフェンのフラットバンドとモアレ物理：魔法角の導出"
date: 2024-01-01T10:00:00+08:00
draft: false
math: true
tags: ["Twisted Bilayer Graphene", "Moire Physics", "Magic Angle", "BM Continuum Model", "Flat Band"]
categories: ["Physics Notes"]
---

2018年、Cao Yuan神がNatureに一本の論文を送り込んで、ツイスト二層グラフェン（Twisted Bilayer Graphene, TBG）が世界に火をつけた。本稿ではTBGのBM連続モデルの構築を振り返り、フラットバンド形成の物理的メカニズムを分析し、魔角条件$\theta \approx 1.1^\circ$を理論的に導出する。

<!--more-->

## なぜツイストロニクス（Twistronics）なのか？

ツイスト系の可调控性とそこから派生するフラットバンド強相関物理は、近年の凝縮系物理におけるホットトピックである。Rafi BistritzerとAllan H. MacDonaldが2011年に発表した"Moiré bands in twisted double-layer graphene"（BM連続モデル）は、魔角の出現を正確に理論予測した。

https://www.pnas.org/doi/10.1073/pnas.1108174108

理論面では、BernevigらがBM連続モデルの正確性、対称性、一体系・多体性質などを详尽に解析・計算し、200ページに及ぶ「TBG六部作」を発表した。実験的にも、ツイストTMDなどの系が次々と実現されている。

### フラットバンドの意義

バンド幅$W$は電子の一体的運動エネルギーを反映する。フラットバンドとは：

$$ U \gg W $$

ここで$U \sim e^2/a_M$は電子間相互作用のエネルギースケール、$a_M$はモアレ格子定数である。フラットバンド系では電子の運動エネルギーがほぼゼロとなり、相互作用が支配的になる——強相関物理がここに現れる。

## BM連続モデル

### 単層グラフェンのDirac錐

単層グラフェンの低エネルギー有効モデルは：

$$ H_{SLG}(\mathbf{k}) = \hbar v_F \mathbf{k} \cdot \boldsymbol{\sigma} $$

K点付近で線形分散のDirac錐を形成する。二層グラフェンは二層が積層され、層間結合を介して相互作用する。

### ツイストが導入するモアレ超格子

上層グラフェンを微小角度$\theta$だけ回転させると、二層のBZも相対的に回転する：

$$ \mathbf{K}_t = R(\theta/2) \mathbf{K}, \quad \mathbf{K}_b = R(-\theta/2) \mathbf{K} $$

モアレ超格子の逆格子ベクトルは：

$$ \mathbf{G}_i^M = \mathbf{G}_i^{(t)} - \mathbf{G}_i^{(b)} $$

モアレ格子定数：

$$ a_M = \frac{a}{2\sin(\theta/2)} \approx \frac{a}{\theta} $$

$\theta = 1.1^\circ$のとき、$a_M \approx 13$ nmとなり、グラフェン単位胞の約50倍である。

### BMモデルの行列構造

BM連続モデルは運動量空間において無限次元行列であり、基底は二層のDirac錐をモアレ逆格子ベクトル$\mathbf{G}_i^M$だけずらしたレプリカである。低エネルギー物理に対しては、最低次のモアレ逆格子ベクトルのみを残せば収束した結果が得られる。

単層Hamiltonianの行列要素：

$$ [H_{SLG}]_{\mathbf{G},\mathbf{G}'} = \hbar v_F (\mathbf{k} + \mathbf{G}) \cdot \boldsymbol{\sigma} \delta_{\mathbf{G},\mathbf{G}'} $$

層間結合項（トンネリング）：

$$ T_{\mathbf{G}} = \begin{pmatrix} w_0 & w_1 e^{-i\psi} \\ w_1 e^{i\psi} & w_0 \end{pmatrix} $$

ここで$w_0$はAA積層の層間結合、$w_1$はAB積層の層間結合である。

### Tripodモデルと魔角

収束性を保つ最も簡単な切断はTripodモデル——K_M Dirac錐とそれに最も近い三つのモアレ逆格子ベクトルを残す。これにより$8\times 8$の有効Hamiltonianが得られる。

カイラル極限（$w_0 = 0$）では、BMモデルは粒子-正孔対称性を持ち、フラットバンドが魔角において厳密に現れる。魔角条件は：

$$ \alpha = \frac{w_1}{\hbar v_F k_\theta} = \alpha_c \approx 0.586 $$

ただし$k_\theta = 2K\sin(\theta/2)$である。これより：

$$ \theta \approx \frac{3w_1}{\hbar v_F K} \approx 1.05^\circ $$

### 繰り込まれたフェルミ速度

BMモデルの核心的予言は：回転角の減少に伴い、Dirac錐のフェルミ速度が層間結合によって繰り込まれる：

$$ v_F^* = v_F \frac{1 - 3\alpha^2}{1 + 3\alpha^2} $$

$\alpha = 1/\sqrt{3}$のとき、$v_F^* = 0$——これが魔角の出現を表す。繰り込まれたフェルミ速度がゼロになることは、Dirac分散がフラットバンドに変わることを意味する。

### トポロジカル性質

TBG魔角フラットバンドは非自明なトポロジカル性質を持つ。各valley内の二つのフラットバンドの総Chern数は0であるが、各フラットバンドは$C = \pm 1$に還元できる。フラットバンドと最低Landau準位の間には形式的対応関係が存在し——"vortexability"基準は理想的なFCIフラットバンドを記述する幾何学的条件を統一的に与える。

## 連続モデルの対称性

BMモデルは豊かな対称性を持つ：
- $C_{3z}$：三重回転対称性
- $C_{2z}\mathcal{T}$：スピンレス時間反転
- 粒子-正孔対称性（カイラル極限下）
- $U(1)$谷保存（小角度下）

カイラル極限外（$w_0 \neq 0$）では粒子-正孔対称性は破れるが、フラットバンドは安定に存在し続ける——トポロジカルな保護機構が働いていることを示している。

## まとめ

ツイストグラフェンのBM連続モデルは魔角フラットバンドの出現を成功裏に予言した。その物理的本質は、層間結合によるDiracフェルミ速度の繰り込みである。モアレ超格子はミクロンスケールの複雑な系を有効的な低エネルギーモデルに還元し、ツイスト系における強相関現象（超伝導、相関絶縁体状態など）の理解の基盤を提供している。
