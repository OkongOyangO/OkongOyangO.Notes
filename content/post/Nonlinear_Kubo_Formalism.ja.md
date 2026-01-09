+++
date = '2026-01-08T20:30:33-05:00'
draft = false
math = true
ShowToc = true
TocOpen = false
title = '非線形久保公式'
+++

# 非線形久保公式 (Nonlinear Kubo Formalism)

久保公式は線形応答理論の核心であり、システムの輸送係数（電気伝導率など）を平衡状態の相関関数と結びつけます。しかし、強レーザー物理学やトポロジカルオプトエレクトロニクスの発展に伴い、**非線形応答**（Nonlinear Response）の記述がますます重要になっています。非線形久保公式は線形理論を高次の摂動へと拡張するものであり、第二次高調波発生（SHG）やバルク起電力効果（BPVE）などの現象を理解するための理論的基礎となります。

## 1. 密度行列の摂動展開

外場によって駆動される量子系を考えます。ハミルトニアンは以下の通りです：
$$
\begin{aligned}
H(t) = H_0 + V(t)
\end{aligned}
$$
ここで、$H_0$ は非摂動ハミルトニアン、$V(t)$ は時間依存する摂動（例：電磁場と電子の相互作用 $V(t) = e \mathbf{r} \cdot \mathbf{E}(t)$）です。

システムのダイナミクスはリウヴィル＝フォン・ノイマン方程式（Liouville-von Neumann equation）によって記述されます：
$$
\begin{aligned}
i\hbar \frac{\partial \rho(t)}{\partial t} = [H(t), \rho(t)]
\end{aligned}
$$
密度行列 $\rho(t)$ を摂動の次数で展開します：
$$
\begin{aligned}
\rho(t) = \rho^{(0)} + \rho^{(1)}(t) + \rho^{(2)}(t) + \dots + \rho^{(n)}(t) + \dots
\end{aligned}
$$
ここで、$\rho^{(0)}$ は平衡状態の密度行列（通常はフェルミ・ディラック分布）です。

## 2. 反復解法と入れ子交換子

相互作用描像において、$\rho^{(n)}(t)$ の漸化式を得ることができます。第 $n$ 次の密度行列の補正は、第 $n-1$ 次によって決定されます：
$$
\begin{aligned}
\rho^{(n)}(t) = -\frac{i}{\hbar} \int_{-\infty}^{t} dt' [V(t'), \rho^{(n-1)}(t')]
\end{aligned}
$$
これは有名な入れ子交換子（Nested Commutator）形式を導きます。$n$ 次の応答に対して、観測演算子 $\hat{O}$ の期待値は以下のようになります：
$$
\begin{aligned}
\langle \hat{O} \rangle^{(n)}(t) = \text{Tr}(\hat{O} \rho^{(n)}(t))
\end{aligned}
$$
明示的に書き下すと、次のようになります：
$$
\begin{aligned}
\langle \hat{O} \rangle^{(n)}(t) = \left(-\frac{i}{\hbar}\right)^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n \text{Tr}\left( \hat{O} [V(t_1), [V(t_2), \dots [V(t_n), \rho^{(0)}] \dots ]] \right)
\end{aligned}
$$
ここで、時間積分は時間順序 $t > t_1 > t_2 > \dots > t_n$ を満たします。

## 3. 二次非線形応答とトポロジカルな性質

凝縮系物理学において、二次応答（$n=2$）は特に重要です。二次光伝導率 $\sigma^{(2)}$ は、光整流（Optical Rectification）や第二次高調波発生などの効果を記述します。

周期的な結晶系では、運動量空間において位置演算子 $\mathbf{r}$ の行列要素はベリー接続（Berry Connection）を含みます。Sipe や Shkrebtii 等は、バンドに基づいた非線形応答理論を発展させました。

二次の直流応答（光電流）は次のように書くことができます：
$$
\begin{aligned}
J_{a}^{(2)} = \sigma_{abc}^{(2)} E_b E_c^*
\end{aligned}
$$
反転対称性が破れた（Inversion Symmetry Breaking）系において、非線形久保公式の導出は**シフト電流（Shift Current）**の幾何学的起源を明らかにします。その式は以下の被積分関数を含みます：
$$
\begin{aligned}
R_{nm}^{a} = \frac{\partial \phi_{nm}}{\partial k_a} + A_{nn}^{a} - A_{mm}^{a}
\end{aligned}
$$
ここで、$R$ は**シフトベクトル（Shift Vector）**と呼ばれ、電子が光子を吸収して遷移する際の波束中心の実空間変位を記述します。これは非線形光学応答を、波動関数の量子幾何学的性質（ベリー接続）に直接結びつけるものです。

## 4. まとめ

非線形久保公式は単なる摂動の拡張にとどまらず、非平衡状態における高次輸送過程を扱うための統一的な枠組みを提供します。
*   **線形次数**：ドルーデ伝導、ベリー曲率（ホール効果）に対応。
*   **非線形次数**：シフト電流、ベリー曲率双極子、非線形ホール効果に対応。

この形式体系を通じて、トポロジカル物質における新しい非線形光応答を予言し、理解することができます。