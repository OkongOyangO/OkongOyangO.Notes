---
title: "费米黄金法则（Fermi Golden Rule）漏了什么？"
date: 2026-01-10T02:59:13Z
draft: false
math: true
tags: ["Quantum Mechanics", "Fermi Golden Rule"]
categories: ["Physics Notes"]
---

本文旨在计算严格的量子跃迁速率，并指出费米黄金法则是其的“长时间平均”的结果。严格的量子跃迁速率相比费米黄金法则还多一项振幅不可忽略的二倍频振荡项，前后者关系类似交流电路中的“瞬时功率”与“平均功率”。

## Fermi Golden Rule

费米黄金法则旨在计算时谐外场微扰下，量子系统从初态$|i\rangle$到末态$|f\rangle$（均为$H_0$的本征态）的跃迁速率。由于量子力学课程中已经阐述的很完备，此处我们在Dirac表象（相互作用表象）下速通一遍。使用Dirac表象是为了更好与Kubo Formula进行比较

Dirac表象下态的运动方程：

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

Dirac表象下的算符：

$$
\begin{aligned}
\hat{\mathcal{O}}_D(t) = e^{i\hat{H_0}t/\hbar} \hat{\mathcal{O}}_S(t) e^{-i\hat{H_0}t/\hbar}
\end{aligned}
$$

下标$D,\,S$分别代表Dirac表象和Schrodinger表象。

对运动方程积分后迭代可以得到Dirac表象下态的演化算符$\mathcal{U}(t,t')$：

$$
\mathcal{U}(t,t') = \mathcal{T} e^{-i \int_{t'}^{t}dt'' \hat{V}_D(t'')/\hbar }
$$

$$
= 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) + \frac{1}{2!} (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{t}dt_2 \mathcal{T} \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots
$$

$$
= 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) +  (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots
$$

其中$\mathcal{T}$是time ordering operator，将时间小的算符放在右边，先和态矢作用。上面也给出了不用time ordering的表达式，可以对运动方程积分，迭代获得。

假设系统在$t = t_0$时，初态为$|i\rangle$，取到$\mathcal{O}(V)$阶近似则：

$$
\begin{aligned}
| \psi (t) \rangle_D & = \mathcal{U}(t,t_0) | \psi (t_0) \rangle_D \\
& = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

则$t$时刻$|f\rangle$态的概率幅为：

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D = 0 + (-i/\hbar) \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

对于频率为$\omega > 0$的时谐微扰：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

则：

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D  = (-i/\hbar) & \int_{t_0}^{t}dt_1 \langle f | e^{i\hat{H_0}t_1/\hbar} \hat{V}_S(t_1) e^{-i\hat{H_0}t_1/\hbar}|i\rangle \\
= (-i/\hbar) & \int_{t_0}^{t}dt_1 e^{i \omega_{fi} t_1}[ \langle f | \hat{H'}^\dagger |i\rangle e^{i \omega t_1} + \langle f | \hat{H'} | i \rangle e^{-i \omega t_1} ] \\
= (-i/\hbar)& [ \underbrace{\frac{e^{i (\omega_{fi} + \omega)t} - e^{i (\omega_{fi} + \omega)t_0} }{i(\omega_{fi} + \omega)} \langle f | \hat{H'}^\dagger |i\rangle}_{(1)} \\
& + \underbrace{\frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle}_{(2)} ]
\end{aligned}
$$

其中$\omega_{fi} = (E_f - E_i)/\hbar$对应从初态$|i\rangle$到末态$|f\rangle$的跃迁能量。

### Common Approach in Quantum Mechanics

量子力学课程中的常用做法是考虑$\omega \rightarrow \pm \omega_{fi}$时，(1)会远小于或远大于(2)，从而只考虑其中一项的贡献。

以$\omega \rightarrow + \omega_{fi}$为例，计算$t$时刻系统处于$|f\rangle$态的概率：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & \approx |(-i/\hbar) \frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle |^2 \\
& = \frac{1}{\hbar^2} | (-i e^{i(\omega_{fi} - \omega)(t - t_0)/2}) \frac{2 \sin[(\omega_{fi} - \omega)(t - t_0)/2]}{\omega_{fi} - \omega} \langle f | \hat{H'} |i\rangle|^2 \\
& = \frac{4}{\hbar^2} \frac{\sin^2[(\omega_{fi} - \omega)(t - t_0)/2]}{(\omega_{fi} - \omega)^2} |\langle f | \hat{H'} |i\rangle|^2 \\
& \xrightarrow{t - t_0 \rightarrow + \infty} \frac{2 \pi}{\hbar^2} |\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) \times (t - t_0)
\end{aligned}
$$

这里利用了一个不太常见的极限：

$$
\begin{aligned}
\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)
\end{aligned}
$$

从而跃迁速率为（同时考虑$\omega \rightarrow \pm \omega_{fi}$）：

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} = \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 = \frac{2 \pi}{\hbar^2} [|\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) + \langle i | \hat{H'} | f \rangle|^2 \delta (\omega + \omega_{fi}) ]
\end{aligned}
$$

### Strict Derivation

上述方法给出的结果是正确的，但上述推导取极限的方法似乎不太严谨，特别是那个极其不友好的极限$\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)$。

事实上，我们可以通过更严谨的推导得到$\mathcal{I}_{i\rightarrow f}$。

进一步，我们会发现之前的推导只考虑了$\mathcal{I}_{i\rightarrow f}$中的零频率项，更严格的结果还含有二倍频项。

但二倍频振荡项在长时间平均下为零，所以跃迁速率更严格的定义应该是"长时平均跃迁速率"：

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \equiv \left\langle \frac{d}{dt} |\langle f | \psi  \rangle_D|^2 \right\rangle_t
\end{aligned}
$$

为了更严格地推导，我们从"$\approx$"号之前出发，并尽量使用严格等号和大家熟悉的极限公式推导：

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & = \left|-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right|^2 \\
& = \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right)
\end{aligned}
$$

从而跃迁速率：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{d}{dt} \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \frac{d}{dt} \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& =  \left(-\frac{i}{\hbar}  \langle f |\hat{V}_D(t)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar}  \langle i |\hat{V}_D(t)|f\rangle\right) \\
& = \frac{1}{\hbar^2} \int_{t_0}^{t}dt_1 \left( \langle f |\hat{V}_D(t)|i\rangle\langle i |\hat{V}_D(t_1)|f\rangle + \langle f |\hat{V}_D(t_1)|i\rangle\langle i |\hat{V}_D(t)|f\rangle \right)
\end{aligned}
$$

对于频率为$\omega > 0$的时谐微扰：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

有：

$$
\begin{aligned}
\langle i |\hat{V}_D(t)|f\rangle = e^{-i\omega_{fi}t}(\langle i |\hat{H'}^\dagger|f\rangle e^{i\omega t} + (\langle i |\hat{H'}|f\rangle e^{-i\omega t})
\end{aligned}
$$

为方便标记，不妨将$\hat{H'}$的矩阵元记为：

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

特别要注意一点，此处只有$\hat{V}$是厄米算符，$\hat{H'}$不一定为厄米算符，所以一般有：

$$
\begin{aligned}
H_{if} = (H^\dagger)_{fi}^* \neq H_{fi}^*
\end{aligned}
$$

从而：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} (H_{if}^*e^{i\omega t} + H_{fi} e^{-i\omega t})(H_{fi}^*e^{i\omega t'} + H_{if} e^{-i\omega t'}) \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} (H_{fi}^*e^{i\omega t} + H_{if} e^{-i\omega t})(H_{if}^*e^{i\omega t'} + H_{fi} e^{-i\omega t'}) \\
& = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{-i \omega (t - t')} }_{(1.1)} + \underbrace{|H_{if}|^2 e^{i \omega (t - t')} }_{(1.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(1.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(1.4)} \right] \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{i \omega (t - t')} }_{(2.1)} + \underbrace{|H_{if}|^2 e^{-i \omega (t - t')} }_{(2.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(2.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(2.4)} \right]
\end{aligned}
$$

要讨论长时间演化下的近似，我们不妨取$t_0 \rightarrow - \infty$

关注(1.1)+(2.1)项，变换积分参量后为：

$$
\begin{aligned}
(1.1) + (2.1) & = \frac{|H_{fi}|^2}{\hbar^2} \int_{- \infty}^t dt' \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{0}^{+ \infty} d(t - t') \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{-\infty}^{+ \infty} d\tau e^{i (\omega - \omega_{fi}) \tau} \\
& = \frac{2 \pi}{\hbar^2} |H_{fi}|^2 \delta({\omega - \omega_{fi}})
\end{aligned}
$$

这边得到了费米黄金法则中的一项，另一项不难发现来自(1.2)+(2.2)项，从而：

$$
\begin{aligned}
(1.1) + (2.1) + (1.2) + (2.2) = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$

但是(1.3)+(2.3)以及(1.4)+(2.4)的具体含义尚未探讨，这也是一般量子力学课程中忽略的一项。

进一步讨论会发现它是一个二倍频振荡项，且在$t \rightarrow \infty$时，振荡频率和费米黄金法则中的$\delta({\omega - \omega_{fi}})$大小相当，故在严格讨论中不能忽略。

或者说，费米黄金法则通过取“长时间平均近似”，将这一项振荡项的贡献消除。这好比求交流电路系统中的平均功率。

### Double Frequency Term

下面我们来计算(1.3)+(2.3)项以及(1.4)+(2.4)。

以(1.3)+(2.3)项为例：

$$
\begin{aligned}
(1.3) + (2.3) & = \frac{1}{\hbar^2} H_{fi}^* H_{if}^* \int_{- \infty}^t dt' e^{i \omega (t + t')}   \left[e^{i\omega_{fi} (t-t')} + e^{-i\omega_{fi} (t-t')} \right] \\
& = \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \delta( \omega - \omega_{fi}) + e^{i (\omega - \omega_{fi})t} \delta( \omega + \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right]
\end{aligned}
$$

类似的，

$$
\begin{aligned}
(1.4) + (2.4) \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right]
\end{aligned}
$$


可见严格的跃迁速率$\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2$不仅包含了常数项，还包含了二倍频项，且两者振幅相当，均包含$\delta( \omega \pm \omega_{fi})$。

只有在“长时间平均近似”下定义的跃迁速率$\left\langle\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 \right\rangle_\tau$，即仅保留了常数项才和费米黄金法则相对应。

还要注意到，无论是否取“长时间平均近似”，跃迁速率都必须在演化时间足够长的条件下讨论，否则吸收谱中的$\delta( \omega \pm \omega_{fi})$将有$(t - t_0)^{-1}$量级的展宽。

但一般的系统并非完全无耗散，还有耗散特征时间$\tau$对应的耗散展宽$\sim \tau^{-1}$。只要$t - t_0 \gg \tau, \omega_{fi}^{-1}$，就不会对吸收谱有太大影响。此处略去对于耗散展宽$\sim \tau^{-1}$的讨论。

## Summary

系统在频率为$\omega > 0$的长时间（$t_0 \rightarrow - \infty,\, t \rightarrow + \infty$）的时谐微扰下

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

从初态$| i \rangle$到末态$| f \rangle$严格的跃迁速率表达式为：

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right] \\
& + \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right] \\
& + \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} \left\{ \left[ |H_{fi}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{2i\omega_{fi} t}) \right]  \delta( \omega + \omega_{fi}) + \left[ |H_{if}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{-2i\omega_{fi} t}) \right] \delta( \omega - \omega_{fi})  \right\}
\end{aligned}
$$

其中常数项为费米黄金法则的结果，除此之外还有二倍频项，两者振幅相当。

在“长时间平均近似”下（观测时间远大于系统本征时间$\omega_{fi}^{-1}$），二倍频项可以略去，长时间平均的跃迁速率与费米黄金法则结果一致，这类似求交流电系统的平均功率。

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} & \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \\
& = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$