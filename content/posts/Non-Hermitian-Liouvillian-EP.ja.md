---
title: "😈非エルミート・ハミルトニアン、Liouvillian超演算子スペクトルと例外点入門"
date: 2026-06-30T13:00:00+08:00
draft: false
math: true
tags: ["Non-Hermitian", "Exceptional Points", "Liouvillian", "Lindblad Equation", "Condensed Matter"]
categories: ["Physics Notes"]
---

本ノートでは、非エルミート（Non-Hermitian）量子物理における2つの中核的概念——Lindblad主方程式形式系におけるLiouvillian超演算子、および非エルミート行列に特有の例外点（Exceptional Points, EP）のスペクトル的特徴——について紹介する。

<!--more-->

## Lindblad Master Equation Formalism & Liouvillian Superoperator

### Lindblad Master Equation

開放量子系の密度行列の時間発展は、Lindblad主方程式（Lindblad Master Equation, LME）によって記述される：

$$
    \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L} \hat{\rho}(t)=-i[\hat{H}, \hat{\rho}(t)]+\sum_{\mu} \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)
$$

$$
    \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)=\hat{\Gamma}_{\mu} \hat{\rho}(t) \hat{\Gamma}_{\mu}^{\dagger}-\frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2} \hat{\rho}(t)-\hat{\rho}(t) \frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2}
$$

ここで、$\frac{1}{2}\{L_{k}^{\dagger} L_{k}, \rho\}$は連続的な反ユニタリー部分を記述し、$L_{k} \rho L_{k}^{\dagger}$は不連続な時間発展をもたらすquantum jump項を表す。これら2つの項の結合により、密度行列の時間発展におけるトレース保存性が保証される。

LMEの導出については、H. P. Breuerの『The Theory of Open Quantum Systems』や、知乎（Zhihu）上の関連記事を参考にするとよい。

### 有効非エルミート・ハミルトニアンと量子軌跡解釈

短時間の時間発展は、有効非エルミート・ハミルトニアン$H_{eff}$によって記述できる：

$$
    \hat{H}_{\mathrm{eff}}=\hat{H}-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2, \quad \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L}^{\prime} \hat{\rho}(t)=-i\left(\hat{H}_{\mathrm{eff}} \hat{\rho}(t)-\hat{\rho}(t) \hat{H}_{\mathrm{eff}}^{\dagger}\right)
$$

$H_{eff}$の非エルミート性は、系と環境の結合に起因する——散逸項$-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2$により固有値に虚部が生じ、この虚部は状態の減衰率を表す。

### Liouvillian超演算子のスペクトル

Liouvillian $\mathcal{L}$は、密度行列空間に作用する超演算子（superoperator）である。ベクトル化（vectorization）操作により、$N \times N$の密度行列を$N^2$次元ベクトルに写像すれば、$\mathcal{L}$は$N^2 \times N^2$行列となる。

Liouvillianのスペクトル$\{\lambda_i\}$は一般に複素数である。そのうち少なくとも1つは定常状態（steady state）に対応し、$\lambda = 0$の固有状態となる。複数の定常状態が存在する場合は散逸相転移（dissipative phase transition）に対応し、これはEPの出現や対称性の破れと密接に関連する。

Liouvillian gapは以下のように定義される：

$$ \Delta = -\min(\operatorname{Re}(\lambda_i)) $$

これは最も減衰の遅いモードの緩和時間を表す。$\Delta \to 0$のとき、系は臨界スローダウン（critical slowing down）を示す。

## 例外点（Exceptional Points）

### 例外点とは何か？

エルミート行列の固有値は常に実数であり、固有ベクトルは完全な直交基底をなす。これに対し、非エルミート行列の重要な特徴の1つは、あるパラメータ値において固有値が縮退するだけでなく、固有ベクトルも縮退することである。このような点を**例外点（Exceptional Point, EP）**と呼ぶ。

EPにおいて、行列は対角化不可能となり、代わりにJordan標準形に帰着する。これはエルミート系における縮退点（Diabolic Point）とは本質的に異なる。

簡単な$2 \times 2$非エルミート行列を考えてみよう：

$$
H = \begin{pmatrix}
\epsilon & t \\
t & -\epsilon + i\gamma
\end{pmatrix}
$$

パラメータを調整して固有値を等しくすれば、EPが見つかる。EP近傍では固有値は平方根の形で分裂する：

$$ \Delta E \propto \sqrt{\lambda - \lambda_{EP}} $$

これはエルミート系における線形的な準位反発（$\Delta E \propto |\lambda - \lambda_0|$）とは対照的である。

### EP近傍の過渡的ダイナミクス：LEPをまたぐ減衰振動子アナロジー

Liouvillian Exceptional Point（LEP）をまたぐ過渡的ダイナミクスは、古典的な減衰振動子が過減衰から臨界減衰、さらには不足減衰へと遷移する様子に類似している。

系のパラメータをLEPの一方から他方へと調整すると：
- LEPの一方の側：系が定常状態に近づく過程は振動的減衰を示す（"不足減衰"）
- LEP上：臨界減衰
- LEPのもう一方の側：振動のない指数関数的減衰（"過減衰"）

これはLiouvillian固有値の虚部の振る舞いによって理解できる——EPにおいて固有値が純実数から複素数へと変化するのである。

### EP近傍でのカイラル状態遷移

系のパラメータをEPの周りで断熱的に一周させると、系の最終状態は周回方向（時計回り／反時計回り）に依存し、初期の固有状態には留まらない。この現象は**カイラル状態遷移（Chiral State Transfer）**あるいは**非対称モード変換（Asymmetric Mode Transfer）**と呼ばれる。

これはエルミート系における断熱定理とは対照的である。エルミート系では、時間発展が十分に緩やかであれば、系は常に瞬時固有状態に留まり続ける（Berry位相因子を除く）。一方、非エルミート系ではEPを一周すると、系は必ず別の固有状態に遷移する。

カイラル状態遷移は非エルミートトポロジーにおける活発な研究分野であり、導波路結合や光マイクロ共振器などの実験プラットフォームで観測されている。

## まとめ

非エルミート量子物理は、Lindblad主方程式を通じて開放量子系のダイナミクスを記述し、有効非エルミート・ハミルトニアンは自然な形で複素固有値を導入する。例外点（EP）は非エルミート系に固有のスペクトル的特異点であり、その近傍の物理——減衰振動子の過渡過程からカイラル状態遷移に至るまで——は、古典系・量子系のいずれにおいても豊富な実験的実現がなされている。
