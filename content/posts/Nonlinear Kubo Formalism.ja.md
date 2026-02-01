---
title: "🥸久保公式の非線形応答理論"
date: 2023-03-07T22:30:00-05:00
draft: false
math: true
tags: ["Nonlinear Response", "Kubo Formula"]
categories: ["Physics Notes"]
---

この記事は、久保公式の非線形応答理論を導出することを目的としています。

<!--more-->

## はじめに

久保公式の線形および非線形応答理論は、本質的に量子力学の摂動論です。

線形応答の方が一般的で、例えば実験で測定される電気伝導率、磁化率、電気分極率などの感受率（Susceptibility）はすべて線形応答関数（遅延グリーン関数）です。

しかし、非線形応答にも応用価値があります。例えば、半導体における第二次高調波発生（SHG）、注入電流（Injection Current）、シフト電流（Shift Current）などの二次電流応答です。

二次応答は、前節のフェルミの黄金律（Fermi Golden Rule）で議論した、一定の遷移速度と二倍周波数の遷移速度という2種類の応答を説明するためにも使用できます。

https://zhuanlan.zhihu.com/p/611688122

**度胸さえあれば、至る所に非線形応答がある**ことがわかります（笑）。

## 相互作用描像における密度行列

久保公式の導出は、相互作用（ディラック）描像における系の密度行列の時間発展から始まります。

フェルミの黄金律の節で、すでに相互作用（ディラック）描像における波動関数の運動方程式を導出しました。

密度行列を単に $\hat{\rho}_D(t) \sim | \psi (t) \rangle_D \langle \psi(t) |_D$ と見なすと、相互作用（ディラック）描像における密度行列の運動方程式をすぐに思い出すことができます：

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

積分して繰り返し反復することで、密度行列の展開式が得られます：

$$
\begin{aligned}
\hat{\rho}_D(t) = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]
\end{aligned}
$$

各積分の積分上限が常に $t$ ではないことに注意してください。

## 線形応答

線形応答のみを考えます：

$$
\begin{aligned}
\hat{\rho}_D(t)  \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right]
\end{aligned}
$$

ここで、$\hat{\rho}_0$ は平衡状態の密度行列です：

$$
\begin{aligned}
\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}
\end{aligned}
$$

観測量 $\hat{A}$ の時間変化を考察したいと思います：

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \operatorname{Tr}\{ \hat{\rho}_D(t) \hat{A}_D(t) \}
\end{aligned}
$$

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\hat{A}\rangle_0 +(-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \operatorname{Tr}\left\{\left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \hat{A}_D(t) \right\}
\end{aligned}
$$

ここで、

$$
\begin{aligned}
\langle\dots\rangle_0 = \operatorname{Tr}\{ \hat{\rho}_0 (\dots) \}
\end{aligned}
$$

$$
\begin{aligned}
\hat{A}_D(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}_S(t)  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right)
\end{aligned}
$$

以下の摂動形式に対して：

$$
\begin{aligned}
\hat{V}_S(t) = \hat{B}_S(t) F(t)
\end{aligned}
$$

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\hat{A}\rangle_0 +(-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime}) \operatorname{Tr}\left\{\left[\hat{B}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \hat{A}_D(t) \right\}
\end{aligned}
$$

トレース（Trace）の巡回不変性を利用すると、以下が証明できます：

$$
\begin{aligned}
\operatorname{Tr}\left\{\left[\hat{B}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \hat{A}_D(t) \right\} = \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

したがって：

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\widehat{A}\rangle_0 +(-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime}) \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

このようにして、式中の物理量をすべて $\operatorname{Tr}\left\{\rho_0(\dots)\right\}$ の形式で書くことができます。

これは、平衡状態の観測量を用いて近平衡状態の応答を決定できることを示しています。

一般に、摂動下での観測量 $\hat{A}$ の平衡状態からの差を考えるため、線形応答を以下の形式で書くこともできます：

$$
\begin{aligned}
\Delta A_t  =\langle\hat{A}\rangle_t-\langle\widehat{A}\rangle_0=-\frac{\mathrm{i}}{\hbar} \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime})\left\langle\left[\widehat{A}^{\mathrm{D}}(t), \widehat{B}^{\mathrm{D}}\left(t^{\prime}\right)\right]_{-}\right\rangle_0
\end{aligned}
$$

あるいは次のように書けます：

$$
\begin{aligned}
\Delta A_t =  \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) F(t^{\prime})
\end{aligned}
$$

これが時間領域（Time Domain）における線形応答の久保公式です。

ここには遅延グリーン関数が含まれています：

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_D(t), \hat{B}_D\left(t^{\prime}\right)\right]\right\rangle_0 = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\rangle_0
\end{aligned}
$$

ここでは平衡状態の性質を求めているため、ディラック描像、ハイゼンベルク描像を表す添字 $D, H$ に違いはありません。これは、系の近平衡応答が系の平衡状態の性質によって完全に決定されることを別の側面から反映しています。

これまで示した線形応答公式は一般的なものであり、時間並進対称性などの性質（$\hat{A}_S, \hat{B}_S$ が時間 $t$ を顕わに含まない場合）を考慮していません。もし遅延グリーン関数 $G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$ が時間並進対称性を持つならば：

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = G_{A B}^{\mathrm{ret}}\left(t -  t^{\prime}\right)
\end{aligned}
$$

周波数領域（Frequency Domain）において、より簡潔な線形応答理論を得ることができます。これについては、一般的な二次応答を導出した後にさらに議論します。

## 非線形応答

さて、非線形（高次応答）を求めたいと思います。摂動後の密度行列を高次まで展開し、上記の導出を繰り返すだけです。

摂動後の密度行列を高次まで展開すると（二次応答を例にとる）：

$$
\begin{aligned}
\hat{\rho}_D(t) & \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \\
& + (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \\
& + \dots
\end{aligned}
$$

したがって、観測量 $\hat{A}$ の応答は以下のようになります：

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\hat{A}\rangle_0 + \langle\hat{A}\rangle_1 + \langle\hat{A}\rangle_2 + \dots
\end{aligned}
$$

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \{ \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \hat{A}_D(t) \}
\end{aligned}
$$

トレースの巡回不変性を利用すると：

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

したがって：

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

実際には、より一般的な結論があります：

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t_1\right), \dots ,\left[\hat{V}_{D}\left(t_n\right), \hat{\rho}_0 \right] \dots \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

任意の次数の応答を計算できます：

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

以前の操作を繰り返し、摂動を外場（スカラー場である必要はありません）と演算子部分に分離できる場合：

$$
\begin{aligned}
\hat{V}_S(t) = \hat{B}^\mu_S(t) F_\mu(t)
\end{aligned}
$$

二次応答は次のように書けます：

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\} F_\mu(t')F_\nu(t'') \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} \int_{-\infty}^{+\infty} \mathrm{~d} t'' \chi_2^{\mu\nu}(t;t',t'') F_\mu(t')F_\nu(t'')
\end{aligned}
$$

ここで、$\chi_2^{\mu\nu}(t;t',t'')$ は二次応答率であり、次のように定義されます：

$$
\begin{aligned}
\chi_2^{\mu\nu}(t;t',t'') \equiv (-\frac{\mathrm{i}}{\hbar})^2 \Theta(t - t') \Theta(t' - t'') \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

任意の次数の応答に一般化できます：

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{B}^{\mu_1}_{D}\left(t_1\right)\right], \dots , \hat{B}^{\mu_n}_{D}\left(t_n\right)\right]\right\} F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n) \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 \dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n  \chi_n^{\mu_1 \dots \mu_n}(t;t_1,\dots,t_n)  F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n)
\end{aligned}
$$

## 周波数領域

まず、系に時間並進対称性などの性質があるかどうかを考慮せず、すべての時間パラメータをフーリエ変換するだけで、時間領域から周波数領域に移行します。

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) \xLeftrightarrow{F.T.} \chi_n(\omega ;\omega_1,\dots,\omega_n)
\end{aligned}
$$

これを行う利点は、一般的な外場が単色電磁波のように単一の周波数であることです。周波数領域の久保公式は、応答の周波数と振幅を直接教えてくれます。しかし、本質的にはフーリエ変換にすぎません。

具体的には：

$$
\begin{aligned}
\chi_n(\omega ;\omega_1,\dots,\omega_n) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{-i\omega_1 t_1} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{-i\omega_n t_n} \chi_n(t;t_1,\dots,t_n)
\end{aligned}
$$

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} e^{i\omega t} \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi} e^{i\omega_1 t_1} \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi} e^{i\omega_n t_n} \chi_n(\omega ;\omega_1,\dots,\omega_n)
\end{aligned}
$$

同様に、観測量と外場も周波数空間にフーリエ変換します：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\omega) = \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} e^{i\omega t} \langle\hat{A}\rangle_n(t)
\end{aligned}
$$

$$
\begin{aligned}
F(\omega_i) = \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_i}{2 \pi} e^{i\omega_i t_i} F(t_i)
\end{aligned}
$$

したがって、周波数領域における久保公式は次のようになります：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & = \int_{- \infty}^{+ \infty} \mathrm{~d} t  e^{-i \bar{\omega} t} \langle\hat{A}\rangle_n(t) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t  e^{-i \bar{\omega} t}  \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 \dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n  \\
& \times \chi_n^{\mu_1 \dots \mu_n}(t;t_1,\dots,t_n)  F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n)
\end{aligned}
$$

$$
\begin{aligned}
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t  e^{-i \bar{\omega} t}  \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 \dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n \\
& \times \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} e^{i\omega t} \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi} e^{i\omega_1 t_1} \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi} e^{i\omega_n t_n} \\
& \times  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_1}{2 \pi} e^{i\bar{\omega}_1 t_1} \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_n}{2\pi} e^{i\bar{\omega}_n t_n}\\
& \times \chi_n^{\mu_1 \dots \mu_n}(\omega ;\omega_1,\dots,\omega_n) F_{\mu_1}(\bar{\omega}_1) \dots F_{\mu_n}(\bar{\omega}_n)
\end{aligned}
$$

$$
\begin{aligned}
& =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \\
& \times  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}}{2 \pi}  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_n}{2\pi} \\
& \times \int_{- \infty}^{+ \infty} \mathrm{~d} t  e^{i (\omega - \bar{\omega}) t} \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 e^{i (\omega_1 + \bar{\omega}_1) t_1}\dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n e^{i (\omega_n + \bar{\omega}_n) t_n} \\
& \times \chi_n^{\mu_1 \dots \mu_n}(\omega ;\omega_1,\dots,\omega_n) F_{\mu_1}(\bar{\omega}_1) \dots F_{\mu_n}(\bar{\omega}_n)
\end{aligned}
$$

$$
\begin{aligned}
& = \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \\
& \times  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}}{2 \pi}  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \bar{\omega}_n}{2\pi} \\
& \times 2 \pi \delta(\bar{\omega} - \omega) \times 2 \pi \delta (\omega_1 + \bar{\omega}_1) \times \dots \times 2 \pi \delta (\omega_n + \bar{\omega}_n) \\
& \times \chi_n^{\mu_1 \dots \mu_n}(\omega ;\omega_1,\dots,\omega_n) F_{\mu_1}(\bar{\omega}_1) \dots F_{\mu_n}(\bar{\omega}_n)
\end{aligned}
$$

最終的に、周波数領域における久保公式は次のようになります：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(-\omega_1) \dots F_{\mu_n}(-\omega_n)
\end{aligned}
$$

ここでの負号は、パラメータ $\{t;t_1,\dots,t_n\}$ のフーリエ変換を再定義することで取り除くこともできます。

例えば、「;」の左右で異なるフーリエ変換を行います：

$$
\begin{aligned}
\chi_n(\omega ;\omega_1,\dots,\omega_n) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{i\omega_n t_n} \chi_n(t;t_1,\dots,t_n)
\end{aligned}
$$

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega}{2 \pi} e^{i\omega t} \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi} e^{-i\omega_1 t_1} \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi} e^{-i\omega_n t_n} \chi_n(\omega ;\omega_1,\dots,\omega_n)
\end{aligned}
$$

すると：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(\omega_1) \dots F_{\mu_n}(\omega_n)
\end{aligned}
$$

しかし実際には、正負の周波数の摂動は常に同時に存在するため、上記の議論は定義の問題にすぎません。

**久保公式に「-」記号がなるべく現れないようにするため、以降の議論では後者の定義を採用します。**

ここで導出した一般的なケースでは、$\{\bar{\omega} ;\omega_1,\dots,\omega_n\}$ の間の関係に制限はなく、任意の周波数の摂動が別の周波数の応答を励起する可能性があります。

しかし、時間並進不変な応答関数の場合、周波数領域における応答関数の形式に一定の制限が生じます。

最も一般的な線形応答を例にとると、応答の周波数は必ず外場の周波数と同じになります。すなわち：

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega \pm \omega_1)
\end{aligned}
$$

より一般的な非線形応答については、応答の周波数は外場の周波数の和であることが証明できます。すなわち：

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega \pm \sum_{i=1}^n \omega_i)
\end{aligned}
$$

ここで "$\pm$" 符号は、周波数領域における応答関数の定義に依存します。

## 時間並進対称性

応答関数が時間並進対称性を持つ場合、応答関数は以下の性質を持つことが証明できます：

$$
\begin{aligned}
\chi_1(t;t') \equiv G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = G_{A B}^{\mathrm{ret}}\left(t -  t^{\prime}\right)
\end{aligned}
$$

$$
\begin{aligned}
\chi_2(t;t',t'') = \chi_2^{\mathcal{T}} (t-t',t'-t'')
\end{aligned}
$$

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n)
\end{aligned}
$$

これは、時間並進対称性により、応答関数内の時間をすべて同じ量だけ変化させても不変であるためです。すなわち：

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n(t + \tau;t_1+ \tau,\dots,t_n+ \tau)
\end{aligned}
$$

したがって、$\{t;t_1,\dots,t_n\}$ これらのパラメータの中で独立なのはそれらの相対値だけであり、次のように定義できます：

$$
\begin{aligned}
& \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n) \\
& = \chi_n(t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ;t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots,t_n + (t_{n-1} - t_n),t_n) \\
& = \chi_n(\sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ; \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots, (t_{n-1} - t_n),0)
\end{aligned}
$$

次に、応答関数が時間並進対称性を持つことの物理的意味を考えます。これは事実上、系および応答に関与する観測量 $\hat{A},\,\hat{B}$ がすべて時間並進不変であることを意味しますが、これは異なる描像下で異なる意味を持ちます。

私たちが最もよく知っているシュレーディンガー描像を例にとると、演算子が時間を顕わに含まなければよいのです：

$$
\begin{aligned}
\hat{A}_S(t) = \hat{A},\,\hat{B}_S(t) = \hat{B}
\end{aligned}
$$

しかし、ディラック/ハイゼンベルク描像では次のように現れます：

$$
\begin{aligned}
\hat{A}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right),\,\hat{B}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{B}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right)
\end{aligned}
$$

「応答関数が時間並進対称性を持つ」ことと「系および応答に関与する観測量 $\hat{A},\,\hat{B}$ がすべて時間並進不変である」ことは同じことを言っていることが証明できます。一次応答関数を例にとると：

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) & = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)  \operatorname{Tr} \left\{ \hat{\rho}_0\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

トレースの巡回不変性を利用して：

$$
\begin{aligned}
& \operatorname{Tr} \left\{ \hat{\rho}_0\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\} \\
& = \operatorname{Tr} \left\{ \hat{\rho}_0\left[ \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) ,  \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t'\right) \hat{B}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t'\right) \right]\right\} \\
& = \operatorname{Tr} \left\{ \hat{\rho}_0\left( \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t - t')\right)  \hat{B}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t'\right) - \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t'\right) \hat{B}  \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t - t')\right)  \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \right) \right\} \\
& = \operatorname{Tr} \left\{ \hat{\rho}_0\left( \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t - t') \right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t - t')\right)  \hat{B}  -  \hat{B}  \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t - t')\right)  \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 (t-t')\right) \right) \right\} \\
& = \operatorname{Tr} \left\{ \hat{\rho}_0\left( \hat{A}_H(t-t')  \hat{B}  -  \hat{B} \hat{A}_H(t-t') \right) \right\} \\
& = \operatorname{Tr} \left\{ \hat{\rho}_0\left[ \hat{A}_H(t-t') , \hat{B} \right] \right\}
\end{aligned}
$$

したがって $\chi_1(t;t') \equiv G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$ は $(t-t')$ のみを顕わに含みます。

導出には、$\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}$ が時間発展演算子 $\exp \left(\pm\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t \right)$ と可換であるという性質を利用しました。これは両者が $\mathcal{H}_0$ の関数であるためです。

同様に、以下が証明できます：

系および応答に関与する観測量 $\hat{A},\,\hat{B}$ がすべて時間並進不変対称性を持つ場合、任意の次数の応答関数も時間並進対称性を持ちます。これは、応答関数が $\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n)$ の形式で書けることと等価です。

### 線形次数感受率

次に、時間並進不変性が応答の周波数を外場の周波数と一致させること、すなわち以下を導くことを証明します：

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega - \omega_1)
\end{aligned}
$$

時間並進対称性の要請により：

$$
\begin{aligned}
\chi_1(t;t_1) = \chi_1^{\mathcal{T}}(t - t_1)
\end{aligned}
$$

したがって、周波数領域の線形応答関数は：

$$
\begin{aligned}
\chi_1(\omega ;\omega_1) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1}  \chi_1(t; t_1) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i(\omega_1 - \omega) t_1} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_1) e^{-i\omega (t - t_1)}   \chi_1^{\mathcal{T}}(t - t_1) \\
& = 2 \pi \delta(\omega - \omega_1) \tilde{\chi}_1^{\mathcal{T}}(\omega) \\
& \sim \delta(\omega - \omega_1)
\end{aligned}
$$

ここで、$\tilde{\chi}_1^{\mathcal{T}}(\omega)$ は ${\chi}_1^{\mathcal{T}}(t - t_1)$ のフーリエ変換です：

$$
\begin{aligned}
\tilde{\chi}_1^{\mathcal{T}}(\omega) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau}   \chi_1^{\mathcal{T}}(\tau)
\end{aligned}
$$

### 非線形次数感受率

より一般的な非線形応答については、応答の周波数が外場の周波数の和になることが証明できます。すなわち：

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

時間並進対称性の要請により（ここではすべて $t_n$ との差として書かれていることに注意）：

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_n,t_1-t_n,\dots,t_{n-1} - t_n)
\end{aligned}
$$

したがって、周波数領域の応答関数は：

$$
\begin{aligned}
\chi_n(\omega ;\omega_1,\dots,\omega_n) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1} ... \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{i\omega_n t_n}  \chi_n(t; t_1,\dots,t_n) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{-i(\omega - \sum_{i=1}^n \omega_i) t_n} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_n) e^{-i\omega (t - t_n)} \int_{- \infty}^{+ \infty} \mathrm{~d} (t_1 - t_n) e^{i\omega_1 (t_1 - t_n)} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} (t_{n-1} - t_n) e^{i\omega_{n-1} (t_{n-1} - t_n)}  \chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n) \\
& = 2 \pi \delta(\omega - \sum_{i=1}^n \omega_i) \tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \\
& \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

ここで、$\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1})$ は $\chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n)$ のフーリエ変換です：

$$
\begin{aligned}
\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau} \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_1 e^{i\omega_1 \tau_1} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_{n-1} e^{i\omega_{n-1} \tau_{n-1}}  \chi_n^{\mathcal{T}}(\tau,\dots,\tau_{n-1})
\end{aligned}
$$

とにかく、二次応答の一般的な久保公式があれば、以前に考えた様々な線形応答を非線形応答に簡単に（とは言えませんが）拡張できます。例えば、非線形電気伝導率、非線形磁化率、非線形電気分極率などの計算です。

## 運動量空間における久保公式

連続媒体（連続空間並進対称性）または結晶（離散空間並進対称性）の場合、教科書では運動量空間における久保公式が示されることがよくあります。

しかし、これは本質的には別のパラメータである座標に対してフーリエ変換を行ったに過ぎず、本質的に時間領域と周波数領域の間のフーリエ変換と違いはありません。空間並進対称性がなくても、各座標パラメータに対して変換を行い、最も一般的な形式を得ることができます。

時間並進対称性を持つ系の応答関数と同様に、空間並進対称性を持つ系の応答関数も、類似の（準）運動量保存形式を満たすことが想像できます。すなわち：

$$
\begin{aligned}
\chi_n(k; k_1,\dots,k_n) \sim \delta(k - \sum_{i=1}^n k_i)
\end{aligned}
$$

## 第二次高調波発生とゼロ周波数項

次に、一般的な時間依存摂動、周波数 $\omega_0 > 0$ の調和摂動を考えます：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega_0 t} + \hat{H'}^\dagger e^{i\omega_0 t}
\end{aligned}
$$

外場は $\pm \omega_0$ の周波数の寄与を持つことがわかります。時間並進不変な系の場合、その一次応答も $\pm \omega_0$ の周波数の項のみを持つはずです。

一方、二次応答については：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \chi_2(\omega; \omega_1, \omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

系が時間並進対称性を持つ場合：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

そして外場のスペクトルは：

$$
\begin{aligned}
F(\omega) \sim \delta(\omega \pm \omega_0)
\end{aligned}
$$

したがって、二次応答は、いわゆる「第二次高調波発生（2nd Harmonic Generation）」である二倍周波数応答を持つことができます：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \pm \omega_0) \sim \delta(\omega \pm 2\omega_0)
\end{aligned}
$$

また、ゼロ周波数応答（Zero Frequency Response）を持つこともできます：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \mp \omega_0) \sim \delta(\omega)
\end{aligned}
$$

第二次高調波発生であれゼロ周波数応答であれ、半導体の非線形電気光学応答において、これらは凝縮系物理学の興味深いトピックです。

## フェルミの黄金律のための久保公式

実際、光励起下での量子系の遷移速度（確率）も、外部摂動に対する系の一種の応答と見なすことができます。

このとき、系の観測量は終状態の射影演算子であり、摂動を受けていない密度行列は始状態の射影演算子であり、外場は光波の時間調和電磁場です：

$$
\begin{aligned}
\hat{\mathcal{O}} = | f \rangle \langle f |
\end{aligned}
$$

$$
\begin{aligned}
\hat{\rho}_0 = |i \rangle \langle i |
\end{aligned}
$$

遷移速度は次のようになります：

$$
\begin{aligned}
\mathcal{I}_{i \rightarrow f} = \frac{d}{dt} \langle \hat{\mathcal{O}} \rangle
\end{aligned}
$$

導出の詳細はひとまず飛ばして、系の二次応答を直接見ると（一次応答が0であることは証明できます）、第二次高調波発生に対応する二倍周波数応答とゼロ周波数応答があることがわかります。

後者は一般的なフェルミの黄金律で計算される一定の遷移速度に対応し、前者は前節で述べたフェルミの黄金律で省略された二倍周波数応答です。長時間平均近似の下では、フェルミの黄金律の結果と完全に一致します。

したがって、フェルミの黄金律は本質的に一種の二次応答であり、非線形次数の久保公式を用いて計算することができます。
