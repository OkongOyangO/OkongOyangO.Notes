---
title: "フェルミの黄金律（Fermi Golden Rule）は何を見落としているのか？"
date: 2026-01-10T02:59:13Z
draft: false
math: true
tags: ["Quantum Mechanics", "Fermi Golden Rule"]
categories: ["Physics Notes"]
---

本文は厳密な量子遷移率を計算し、フェルミの黄金律がその「長時間平均」の結果であることを指摘することを目的としています。厳密な量子遷移率は、フェルミの黄金律と比較して、無視できない振幅を持つ二倍周波数振動項（double-frequency oscillation term）をさらに含んでいます。両者の関係は、交流回路における「瞬時電力」と「平均電力」の関係に似ています。

## Fermi Golden Rule

フェルミの黄金律は、時間調和外場摂動下で、量子系が初期状態$|i\rangle$から終状態$|f\rangle$（いずれも$H_0$の固有状態）へ遷移する遷移率を計算することを目的としています。量子力学の講義ですでに十分に説明されているため、ここではディラック描像（相互作用描像）の下ですばやく確認します。ディラック描像を使用するのは、久保公式（Kubo Formula）との比較を容易にするためです。

ディラック描像における状態の運動方程式：

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

ディラック描像における演算子：

$$
\begin{aligned}
\hat{\mathcal{O}}_D(t) = e^{i\hat{H_0}t/\hbar} \hat{\mathcal{O}}_S(t) e^{-i\hat{H_0}t/\hbar}
\end{aligned}
$$

添字$D,\,S$はそれぞれディラック描像とシュレーディンガー描像を表します。

運動方程式を積分して反復することで、ディラック描像における状態の時間発展演算子$\mathcal{U}(t,t')$が得られます：

$$
\begin{aligned}
\mathcal{U}(t,t') & = \mathcal{T} e^{-i \int_{t'}^{t}dt'' \hat{V}_D(t'')/\hbar }  \\
& = 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) + \frac{1}{2!} (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{t}dt_2 \mathcal{T} \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots \\
& = 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) +  (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots 
\end{aligned}
$$

ここで$\mathcal{T}$は時間順序積演算子（time ordering operator）であり、時間の小さい演算子を右側に配置し、先に状態ベクトルに作用させます。上記には時間順序積を用いない式も示されており、これは運動方程式を積分し、反復することで得られます。

系が$t = t_0$において初期状態$|i\rangle$にあると仮定し、$\mathcal{O}(V)$次の近似をとると：

$$
\begin{aligned}
| \psi (t) \rangle_D & = \mathcal{U}(t,t_0) | \psi (t_0) \rangle_D \\
& = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

時刻$t$における$|f\rangle$状態の確率振幅は以下のようになります：

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D = 0 + (-i/\hbar) \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

周波数$\omega > 0$の時間調和摂動に対して：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

したがって：

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D  = (-i/\hbar) & \int_{t_0}^{t}dt_1 \langle f | e^{i\hat{H_0}t_1/\hbar} \hat{V}_S(t_1) e^{-i\hat{H_0}t_1/\hbar}|i\rangle \\
= (-i/\hbar) & \int_{t_0}^{t}dt_1 e^{i \omega_{fi} t_1}[ \langle f | \hat{H'}^\dagger |i\rangle e^{i \omega t_1} + \langle f | \hat{H'} | i \rangle e^{-i \omega t_1} ] \\
= (-i/\hbar)& [ \underbrace{\frac{e^{i (\omega_{fi} + \omega)t} - e^{i (\omega_{fi} + \omega)t_0} }{i(\omega_{fi} + \omega)} \langle f | \hat{H'}^\dagger |i\rangle}_{(1)} \\
& + \underbrace{\frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle}_{(2)} ]
\end{aligned}
$$

ここで$\omega_{fi} = (E_f - E_i)/\hbar$は初期状態$|i\rangle$から終状態$|f\rangle$への遷移エネルギーに対応します。

### Common Approach in Quantum Mechanics

量子力学の講義における一般的なアプローチは、$\omega \rightarrow \pm \omega_{fi}$のとき、(1)は(2)よりもはるかに小さいか、あるいははるかに大きくなるため、一方の項の寄与のみを考慮するというものです。

$\omega \rightarrow + \omega_{fi}$を例にとり、時刻$t$において系が$|f\rangle$状態にある確率を計算します：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & \approx |(-i/\hbar) \frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle |^2 \\
& = \frac{1}{\hbar^2} | (-i e^{i(\omega_{fi} - \omega)(t - t_0)/2}) \frac{2 \sin[(\omega_{fi} - \omega)(t - t_0)/2]}{\omega_{fi} - \omega} \langle f | \hat{H'} |i\rangle|^2 \\
& = \frac{4}{\hbar^2} \frac{\sin^2[(\omega_{fi} - \omega)(t - t_0)/2]}{(\omega_{fi} - \omega)^2} |\langle f | \hat{H'} |i\rangle|^2 \\
& \xrightarrow{t - t_0 \rightarrow + \infty} \frac{2 \pi}{\hbar^2} |\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) \times (t - t_0)
\end{aligned}
$$

ここでは、あまり一般的ではない極限を利用しています：

$$
\begin{aligned}
\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)
\end{aligned}
$$

したがって、遷移率は以下のようになります（$\omega \rightarrow \pm \omega_{fi}$の両方を考慮）：

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} = \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 = \frac{2 \pi}{\hbar^2} [|\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) + \langle i | \hat{H'} | f \rangle|^2 \delta (\omega + \omega_{fi}) ]
\end{aligned}
$$

### Strict Derivation

上記の方法で得られる結果は正しいですが、上記の極限をとる方法は厳密さを欠いているように見えます。特に、あの極めて扱いにくい極限$\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)$がそうです。

実際、より厳密な導出を通じて$\mathcal{I}_{i\rightarrow f}$を得ることができます。

さらに、以前の導出では$\mathcal{I}_{i\rightarrow f}$のゼロ周波数成分のみを考慮していましたが、より厳密な結果には二倍周波数項も含まれていることがわかります。

しかし、二倍周波数振動項は長時間平均の下ではゼロになるため、遷移率のより厳密な定義は「長時間平均遷移率」であるべきです：

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \equiv \left\langle \frac{d}{dt} |\langle f | \psi  \rangle_D|^2 \right\rangle_t
\end{aligned}
$$

より厳密に導出するために、"$\approx$"記号の前に戻り、厳密な等号とよく知られた極限公式を使用して導出を試みます：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & = \left|-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right|^2 \\
& = \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right)
\end{aligned}
$$

したがって遷移率は：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{d}{dt} \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \frac{d}{dt} \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& =  \left(-\frac{i}{\hbar}  \langle f |\hat{V}_D(t)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar}  \langle i |\hat{V}_D(t)|f\rangle\right) \\
& = \frac{1}{\hbar^2} \int_{t_0}^{t}dt_1 \left( \langle f |\hat{V}_D(t)|i\rangle\langle i |\hat{V}_D(t_1)|f\rangle + \langle f |\hat{V}_D(t_1)|i\rangle\langle i |\hat{V}_D(t)|f\rangle \right)
\end{aligned}
$$

周波数$\omega > 0$の時間調和摂動に対して：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

ここで：

$$
\begin{aligned}
\langle i |\hat{V}_D(t)|f\rangle = e^{-i\omega_{fi}t}(\langle i |\hat{H'}^\dagger|f\rangle e^{i\omega t} + (\langle i |\hat{H'}|f\rangle e^{-i\omega t})
\end{aligned}
$$

表記を簡単にするために、$\hat{H'}$の行列要素を以下のように記します：

$$
\begin{aligned}
\langle f | \hat{H'}| i \rangle \equiv H_{fi}
\end{aligned}
$$

$$
\begin{aligned}
\langle i | \hat{H'}^\dagger | f \rangle \equiv H_{fi}^*
\end{aligned}
$$

特に注意すべき点は、ここでは$\hat{V}$のみがエルミート演算子であり、$\hat{H'}$は必ずしもエルミート演算子ではないため、一般に以下のようになります：

$$
\begin{aligned}
H_{if} = (H^\dagger)_{fi}^* \neq H_{fi}^*
\end{aligned}
$$

したがって：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} (H_{if}^*e^{i\omega t} + H_{fi} e^{-i\omega t})(H_{fi}^*e^{i\omega t'} + H_{if} e^{-i\omega t'}) \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} (H_{fi}^*e^{i\omega t} + H_{if} e^{-i\omega t})(H_{if}^*e^{i\omega t'} + H_{fi} e^{-i\omega t'}) \\
& = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{-i \omega (t - t')} }_{(1.1)} + \underbrace{|H_{if}|^2 e^{i \omega (t - t')} }_{(1.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(1.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(1.4)} \right] \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{i \omega (t - t')} }_{(2.1)} + \underbrace{|H_{if}|^2 e^{-i \omega (t - t')} }_{(2.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(2.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(2.4)} \right]
\end{aligned}
$$

長時間発展における近似を議論するために、$t_0 \rightarrow - \infty$とします。

(1.1)+(2.1)項に注目し、積分変数を変換すると：

$$
\begin{aligned}
(1.1) + (2.1) & = \frac{|H_{fi}|^2}{\hbar^2} \int_{- \infty}^t dt' \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{0}^{+ \infty} d(t - t') \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{-\infty}^{+ \infty} d\tau e^{i (\omega - \omega_{fi}) \tau} \\
& = \frac{2 \pi}{\hbar^2} |H_{fi}|^2 \delta({\omega - \omega_{fi}})
\end{aligned}
$$

ここでフェルミの黄金律の項の一つが得られました。もう一つの項は(1.2)+(2.2)から生じることが容易にわかり、以下のようになります：

$$
\begin{aligned}
(1.1) + (2.1) + (1.2) + (2.2) = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$

しかし、(1.3)+(2.3)および(1.4)+(2.4)の具体的な意味についてはまだ議論されていません。これは一般的な量子力学の講義でも無視される項目です。

さらに議論を進めると、これは二倍周波数振動項であり、$t \rightarrow \infty$において、その振動周波数はフェルミの黄金律における$\delta({\omega - \omega_{fi}})$と同程度であるため、厳密な議論では無視できないことがわかります。

言い換えれば、フェルミの黄金律は「長時間平均近似」をとることによって、この振動項の寄与を除去しています。これは交流回路系における平均電力を求めることに似ています。

### Double Frequency Term

次に、(1.3)+(2.3)項および(1.4)+(2.4)項を計算します。

(1.3)+(2.3)項を例にとると：

$$
\begin{aligned}
(1.3) + (2.3) & = \frac{1}{\hbar^2} H_{fi}^* H_{if}^* \int_{- \infty}^t dt' e^{i \omega (t + t')}   \left[e^{i\omega_{fi} (t-t')} + e^{-i\omega_{fi} (t-t')} \right] \\
& = \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \delta( \omega - \omega_{fi}) + e^{i (\omega - \omega_{fi})t} \delta( \omega + \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right]
\end{aligned}
$$

同様に、

$$
\begin{aligned}
(1.4) + (2.4) \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right]
\end{aligned}
$$


厳密な遷移率$\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2$には定数項だけでなく、二倍周波数項も含まれており、両者の振幅は同程度であり、共に$\delta( \omega \pm \omega_{fi})$を含んでいることがわかります。

「長時間平均近似」の下で定義された遷移率$\left\langle\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 \right\rangle_\tau$、すなわち定数項のみを保持したものだけが、フェルミの黄金律に対応します。

また、「長時間平均近似」をとるかどうかにかかわらず、遷移率は発展時間が十分に長いという条件の下で議論されなければならないことに注意する必要があります。そうでなければ、吸収スペクトルにおける$\delta( \omega \pm \omega_{fi})$は$(t - t_0)^{-1}$のオーダーの広がりを持つことになります。

しかし、一般的な系は完全に無散逸ではなく、散逸特徴時間$\tau$に対応する散逸広がり$\sim \tau^{-1}$が存在します。$t - t_0 \gg \tau, \omega_{fi}^{-1}$である限り、吸収スペクトルに大きな影響を与えることはありません。ここでは散逸広がり$\sim \tau^{-1}$に関する議論は省略します。

## Summary

周波数$\omega > 0$の長時間（$t_0 \rightarrow - \infty,\, t \rightarrow + \infty$）の時間調和摂動下において：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

$$
\begin{aligned}
\langle f | \hat{H'}| i \rangle \equiv H_{fi}
\end{aligned}
$$

$$
\begin{aligned}
\langle i | \hat{H'}^\dagger | f \rangle \equiv H_{fi}^*
\end{aligned}
$$

初期状態$| i \rangle$から終状態$| f \rangle$への厳密な遷移率の式は以下のようになります：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right] \\
& + \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right] \\
& + \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} \left\{ \left[ |H_{fi}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{2i\omega_{fi} t}) \right]  \delta( \omega + \omega_{fi}) + \left[ |H_{if}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{-2i\omega_{fi} t}) \right] \delta( \omega - \omega_{fi})  \right\}
\end{aligned}
$$

ここで、定数項はフェルミの黄金律の結果であり、それ以外に同程度の振幅を持つ二倍周波数項が存在します。

「長時間平均近似」（観測時間が系の固有時間$\omega_{fi}^{-1}$よりもはるかに長い場合）の下では、二倍周波数項は無視することができ、長時間平均の遷移率はフェルミの黄金律の結果と一致します。これは交流電気システムの平均電力を求めることに似ています。

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} & \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \\
& = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$