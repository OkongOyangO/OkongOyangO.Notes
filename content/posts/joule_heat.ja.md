---
title: "🔥フェルミの黄金律？ただのジュール熱さ！"
date: 2023-03-07T22:30:00-05:00
draft: false
math: true
tags: ["Quantum Mechanics", "Joule Heat"]
categories: ["Physics Notes"]
---

本文はフェルミの黄金律とジュール熱の整合性を説明することを目的としています。

<!--more-->

## Introduction

フェルミの黄金律は系の電磁場吸収を計算でき、久保公式（Kubo Formula）は電流応答を計算でき、ジュール熱公式も電磁場の吸収を計算できます。

前者は完全に量子遷移の観点から計算しているように見え、後者は完全にジュール熱の観点から計算しているように見えます。しかし、両者は本質的に量子力学における時間依存摂動論の応用であり、この点については以前の2つの記事でも触れましたが、両者の整合性については詳細に説明していませんでした。興味のある読者は以下をご覧ください：

https://zhuanlan.zhihu.com/p/611688122

https://zhuanlan.zhihu.com/p/611996682

フェルミの黄金律は、久保公式におけるハミルトニアン $H_0$ の二次応答の変化率 $\frac{d }{dt}\langle H_0 \rangle^{(2)}$ に対応し、この二次応答の変化率は電流の線形応答と外部電場の内積 $\langle \hat{\mathbf{J}} \rangle^{(1)} \cdot \mathbf{E}$ として表せることが証明できます。

## Fermi Golden Rule

フェルミの黄金律は、時間調和外場摂動下で、量子系が初期状態 $|i\rangle$ から終状態 $|f\rangle$ （いずれも $H_0$ の固有状態）へ遷移する速度を計算することを目的としています。以前のフェルミの黄金律の記事では、久保公式と比較しやすくするために、ディラック描像（Dirac Picture）を用いて再導出しました。

ディラック描像における状態の運動方程式：

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

運動方程式を積分して反復することで、ディラック描像における状態の時間発展の摂動展開形式が得られます。系が $t = t_0$ において初期状態 $|i\rangle$ にあると仮定すると：

$$
\begin{aligned}
| \psi (t) \rangle_D & = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle + (-i/\hbar)^2 \int_{t_0}^{t}dt_1 \int_{t_0}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2)|i\rangle + \dots \\
& = | \psi^{(0)} \rangle + | \psi^{(1)}\rangle + | \psi^{(2)}\rangle + \dots
\end{aligned}
$$

したがって、時刻 $t$ における $|f\rangle$ 状態の確率も摂動展開できます：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & = \left| \langle f| \psi^{(0)} \rangle + \langle f| \psi^{(1)} \rangle + \langle f| \psi^{(2)} \rangle + \dots \right|^2 \\
& = \underbrace{\langle f| \psi^{(0)} \rangle \langle \psi^{(0)} | f\rangle }_{\mathcal{O}(V^0)} \\
& + \underbrace{\langle f| \psi^{(1)} \rangle \langle \psi^{(0)} | f\rangle + \langle f| \psi^{(0)} \rangle \langle \psi^{(1)} | f\rangle }_{\mathcal{O}(V^1)} \\
& + \underbrace{\langle f| \psi^{(2)} \rangle \langle \psi^{(0)} | f\rangle + \langle f| \psi^{(1)} \rangle \langle \psi^{(1)} | f\rangle + \langle f| \psi^{(0)} \rangle \langle \psi^{(2)} | f\rangle }_{\mathcal{O}(V^2)} \\
& + \dots
\end{aligned}
$$

## Kubo Formula

久保公式の導出も相互作用（ディラック）描像で行われますが、波動関数の発展ではなく、系の密度行列の発展を計算します。

相互作用（ディラック）描像における密度行列の運動方程式：

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

積分後に繰り返し反復することで、密度行列の展開式が得られます：

$$
\begin{aligned}
\hat{\rho}_D(t) & = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]\\
& = \hat{\rho}^{(0)} + \sum_{i=1}^{\infty} \hat{\rho}^{(i)}
\end{aligned}
$$

初期状態が $| i \rangle$ である純粋状態の密度行列については、密度行列の摂動展開が波動関数の摂動展開と一致することは容易にわかります。なぜなら、両者とも量子力学の含時摂動論だからです。

$$
\begin{aligned}
\hat{\rho}_D(t) & = | \psi (t) \rangle_D \langle \psi(t) |_D \\
& = (| \psi^{(0)} \rangle + | \psi^{(1)}\rangle + \dots) (\langle \psi^{(0)} | + \langle \psi^{(1)} | + \dots) \\
& = \underbrace{| \psi^{(0)} \rangle \langle \psi^{(0)} | }_{\hat{\rho}^{(0)}} \\
& + \underbrace{| \psi^{(1)} \rangle \langle \psi^{(0)} | + | \psi^{(0)} \rangle \langle \psi^{(1)} | }_{\hat{\rho}^{(1)}} \\
& + \underbrace{| \psi^{(2)} \rangle \langle \psi^{(0)} | + | \psi^{(1)} \rangle \langle \psi^{(1)} | + | \psi^{(0)} \rangle \langle \psi^{(2)} | }_{\hat{\rho}^{(2)}} \\
& + \dots
\end{aligned}
$$

$|f\rangle$ 状態の確率を求めるには、密度行列（久保公式）の言語で記述すると、$|f\rangle$ 状態の射影演算子を観測量として扱います：

$$
\begin{aligned}
\hat{\mathcal{O}} = | f \rangle \langle f |
\end{aligned}
$$

すると、$|f\rangle$ 状態の確率は以下のようになります：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & = \langle f | \psi (t) \rangle_D {}_D\langle \psi(t) | f \rangle \\
& = \operatorname{Tr} \left\{ \hat{\rho}_D(t) \hat{\mathcal{O}} \right\} \\
& = \underbrace{\langle f| \psi^{(0)} \rangle \langle \psi^{(0)} | f\rangle }_{\mathcal{O}(V^0) = \operatorname{Tr} \left\{ \hat{\rho}^{(0)} \hat{\mathcal{O}} \right\}} \\
& + \underbrace{\langle f| \psi^{(1)} \rangle \langle \psi^{(0)} | f\rangle + \langle f| \psi^{(0)} \rangle \langle \psi^{(1)} | f\rangle }_{\mathcal{O}(V^1) = \operatorname{Tr} \left\{ \hat{\rho}^{(1)} \hat{\mathcal{O}} \right\}} \\
& + \underbrace{\langle f| \psi^{(2)} \rangle \langle \psi^{(0)} | f\rangle + \langle f| \psi^{(1)} \rangle \langle \psi^{(1)} | f\rangle + \langle f| \psi^{(0)} \rangle \langle \psi^{(2)} | f\rangle }_{\mathcal{O}(V^2) = \operatorname{Tr} \left\{ \hat{\rho}^{(2)} \hat{\mathcal{O}} \right\}} \\
& + \dots 
\end{aligned}
$$

フェルミの黄金律と久保公式は、終状態の確率を計算する際、同じものであることがわかります。密度行列は混合状態にも拡張できるため、確率分布を持つ初期状態からの終状態の確率を計算できます。

とりあえず純粋状態の密度行列に注目しましょう。波動関数のゼロ次展開項は以下の通りです：

$$
\begin{aligned}
| \psi^{(0)} = | i \rangle
\end{aligned}
$$

したがって、終状態確率のゼロ次および一次展開項はいずれもゼロとなり、終状態確率の最低次応答は二次項から来ることになります。ゆえに、我々はこう言えます：

**フェルミの黄金律は、終状態確率の二次応答と一致する。**

## Absorption Rate

フェルミの黄金律を用いて系のエネルギー吸収率を計算する場合、計算するのは以下の量です：

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 
\end{aligned}
$$

ここで、$E_{i,f}$ は初期状態、終状態 $|i\rangle,\,|f\rangle$ のエネルギーです。エネルギー変化率は、遷移速度にエネルギー変化を掛け、可能なすべての遷移について和をとったものであることは容易に理解できます。

久保公式の言語に拡張すると、エネルギー吸収率は実は摂動を受けていないハミルトニアン $\hat{H}_0$ の期待値の変化率です：

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

これは非常に直感的であり、フェルミの黄金律と同じことを言っていることを証明するのも難しくありません。

$$
\begin{aligned}
P & = (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle|^2 \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}(E_f - E_i) | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}E_f | f \rangle \langle f |\right) | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f} | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \hat{H}_0 | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \mathbb{I} | \psi (t) \rangle \right\} \\
& = \frac{d}{dt}\langle \hat{H}_0 \rangle - 0
\end{aligned}
$$

これは純粋状態での結果ですが、混合状態は確率に応じて各結果を重ね合わせたものに過ぎず、同様に成立することは容易に想像できます。

このようにして、遷移速度やエネルギー吸収速度などの言語を統一し、久保公式へと拡張しました。特筆すべき点として、$|f\rangle$ 状態の確率と同様に、$\langle \hat{H}_0 \rangle$ の最低次非ゼロ応答も二次から始まります。

## Joule Heat = Energy Absorption

次に、久保公式におけるジュール熱とエネルギー吸収率の整合性を証明します。

ジュール熱は、電流応答と外部電場の内積 $\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$ として定義されます。

電場摂動（ここではまず空間的に均一な時変電場を考えます）の場合、摂動ハミルトニアンは以下のようになります：

$$
\begin{aligned}
\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t) = -(-e) \hat{\mathbf{r}} \cdot \mathbf{E}(t)
\end{aligned}
$$

電流応答 $\langle \hat{\mathbf{J}} \rangle (t)$ の n 次摂動：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \propto \mathcal{O}(|\mathbf{E}|^n) \propto \mathcal{O}(V^n)
\end{aligned}
$$

対応するジュール熱 $\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$ の n+1 次摂動：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \cdot \mathbf{E}(t) \propto {O}(|\mathbf{E}|^{n+1}) \propto \mathcal{O}(V^{n+1})
\end{aligned}
$$

したがって、電流の線形（一次）応答のジュール熱とエネルギー変化率の二次応答は、摂動展開の次数のレベルで一致しています。

私たちの目標は、**電流の線形（一次）応答のジュール熱とエネルギー変化率の二次応答**が式の上で厳密に一致することを証明することです。

## Current Response

ここで「電流」を電気分極の変化率、すなわち電流密度の体積積分として定義します：

$$
\begin{aligned}
\hat{\mathbf{J}} \equiv \iiint dV \hat{\mathbf{j}} \equiv \frac{d}{dt} \hat{\mathbf{P}}
\end{aligned}
$$

ディラック描像において、電流演算子と電気分極演算子の関係は以下のようになります：

$$
\begin{aligned}
\hat{\mathbf{J}}_D = \frac{d}{dt} \hat{\mathbf{P}}_D = (- \frac{i}{\hbar}) [ \hat{\mathbf{P}}_D, \hat{H}_0 ]
\end{aligned}
$$

したがって、摂動 $\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t)$ の一次電流応答は：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D, \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} 
\end{aligned}
$$

したがって、一次電流応答に対応する二次ジュール熱は：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) \cdot \mathbf{E} (t) , \hat{V}_D(t_1)] \right\}  \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D \cdot \mathbf{E} (t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

そして $\hat{\mathbf{P}}_D \cdot \mathbf{E} (t)$ はまさに摂動 $-\hat{V}_D(t)$ の式そのものです。具体的には：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ -\hat{V}_D(t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{H}_0, \hat{V}_D(t) ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

2つの $\hat{V}_D$ の交換子を見ると、これが基本的に $\langle \hat{H}_0 \rangle$ の二次応答の変化率であることがわかります。時間について一度微分したため、時間積分が1つ少なくなっています。具体的には：

$$
\begin{aligned}
\langle \hat{H}_0 \rangle^{(2)} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[{\hat{H}_0}_D(t), \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
& = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{H}_0, \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
\end{aligned}
$$

ここで、${\hat{H}_0}$ がディラック描像においてそれ自身であるという性質と、${\hat{H}_0}_D(t)$ が時間を露わに含まないという性質（時間並進対称性）を用いました：

$$
\begin{aligned}
{\hat{H}_0}_D(t) = e^{ \frac{i}{\hbar}\hat{H}_0 t} {\hat{H}_0} e^{- \frac{i}{\hbar}\hat{H}_0 t} = \hat{H}_0
\end{aligned}
$$

このとき、$\langle \hat{H}_0 \rangle$ の二次応答の時間依存性は、最初の時間積分の上限にのみ存在するため、その変化率は時間積分が1つ少なくなり（そして積分変数 $t_1$ を $t$ に変更）、電流の一次応答のジュール熱の式と完全に一致します：

$$
\begin{aligned}
\frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} &= (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\} \\
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\} \\
\Rightarrow P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} & = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t)
\end{aligned}
$$

より高次の電流応答とエネルギー変化率も一対一に対応することは容易に検証できます。

これにより、エネルギー変化率と電流応答のジュール熱公式の整合性が証明されました。

## Summary

以上のことから、量子系の電磁波吸収を計算する際のフェルミの黄金律とジュール熱公式の整合性を証明しました。

まず、フェルミの黄金律で計算されたエネルギー吸収率とエネルギー応答の変化率の整合性を証明しました：

$$
\begin{aligned}
\underbrace{P = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2}_{\text{Fermi Golden Rule}} \ \Leftrightarrow \ P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

その後、電流の応答に電場を掛けたジュール熱公式とエネルギー応答の変化率の整合性を証明しました：

$$
\begin{aligned}
& \underbrace{P = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\}}_{\text{Joule Heat}} \\
\Leftrightarrow \  &P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} = (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\}
\end{aligned}
$$

つまり、電流の応答に電場を掛けたジュール熱公式と、量子遷移速度にエネルギー変化を掛けたフェルミの黄金律は、本質的にどちらもエネルギー応答の変化率なのです。

したがって、一見巨視的な「ジュール熱」と一見微視的な「フェルミの黄金律」は同じものであると言えます。
