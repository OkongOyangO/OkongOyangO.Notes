---
title: "🥸久保同学不放过我｜Kubo Formula的非线性响应理论"
date: 2023-03-07T22:30:00-05:00
draft: false
math: true
tags: ["Nonlinear Response", "Kubo Formula"]
categories: ["Physics Notes"]
---

本文旨在推导Kubo Formula的非线性响应理论。

<!--more-->

## Introduction

Kubo Formula的线性和非线性响应理论本质上都是量子力学的微扰论。

其中线性响应更为常见，例如实验测量的电导率、磁化率、电极化率等susceptibility均为线性响应函数（Retarded Green Function）。

但非线性响应也有其应用价值，例如半导体中的二阶电流响应，包括2nd Harmonic Generation，Injection and Shift Current等等。

二阶响应甚至可以用来解释上一节Fermi Golden Rule中的常跃迁速率和二倍频跃迁速率两种响应。

https://zhuanlan.zhihu.com/p/611688122

可见**只要胆够大，处处皆是非线性响应（bushi**。

## Density Matrix in Dirac Picture

Kubo Formula的推导从相互作用（Dirac）绘景下，系统密度矩阵的演化开始。

在Fermi Golden Rule那节中，我们已经推导了相互作用（Dirac）绘景下波函数的运动方程。

简单将密度矩阵看成$\hat{\rho}_D(t) \sim | \psi (t) \rangle_D \langle \psi(t) |_D$，有利于我们快速回忆起相互作用（Dirac）绘景下密度矩阵的运动方程：

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

积分后重复迭代，我们可以得到密度矩阵的展开式：

$$
\begin{aligned}
\hat{\rho}_D(t) = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]
\end{aligned}
$$

注意每个积分的上界并非均为$t$。

## Linear Response

只考虑线性响应：

$$
\begin{aligned}
\hat{\rho}_D(t)  \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right]
\end{aligned}
$$

其中$\hat{\rho}_0$为平衡态密度矩阵：

$$
\begin{aligned}
\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}
\end{aligned}
$$

我们希望考察可观测量$\hat{A}$随时间的变化：

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

其中，

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

对于下面的微扰形式：

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

利用Trace的轮换不变性，可以证明：

$$
\begin{aligned}
\operatorname{Tr}\left\{\left[\hat{B}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \hat{A}_D(t) \right\} = \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

从而：

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\widehat{A}\rangle_0 +(-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime}) \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

这样可以将表达式中的物理量都写成$\operatorname{Tr}\left\{\rho_0(\dots)\right\}$的形式。

这说明，用平衡态的可观测量就可以确定近平衡态的响应。

一般而言，我们考虑可观测量$\hat{A}$在微扰下与平衡态的区别，从而我们还可以把线性响应写成以下形式：

$$
\begin{aligned}
\Delta A_t  =\langle\hat{A}\rangle_t-\langle\widehat{A}\rangle_0=-\frac{\mathrm{i}}{\hbar} \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime})\left\langle\left[\widehat{A}^{\mathrm{D}}(t), \widehat{B}^{\mathrm{D}}\left(t^{\prime}\right)\right]_{-}\right\rangle_0
\end{aligned}
$$

或者写成：

$$
\begin{aligned}
\Delta A_t =  \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) F(t^{\prime})
\end{aligned}
$$

这便是线性响应的Kubo Formula在Time Domain的形式。

其中包含了retarded Green Function，

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_D(t), \hat{B}_D\left(t^{\prime}\right)\right]\right\rangle_0 = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\rangle_0
\end{aligned}
$$

这里由于是求平衡态的性质，所以下标$D,\,H$代表的Dirac，Heisenberg Picture没有区别，从另一个方面体现了系统的近平衡态响应由系统的平衡态性质完全确定。

目前给出的线性响应公式是general的，没有考虑时间平移对称性等性质（当$\hat{A}_S,\,\hat{B}_S$不显含时间$t$）。若retarded Green Function$G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$具有时间平移对称性：

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = G_{A B}^{\mathrm{ret}}\left(t -  t^{\prime}\right)
\end{aligned}
$$

可以在频率空间（Frequency Domain）中得到更加简洁的线性响应理论。我们将在推导完general的二阶响应后，进一步讨论这一点。

## Nonlinear Response

现在我们想求非线性（高阶响应），我们直接把微扰后的密度矩阵展开到高阶，重复上面的推导即可。

把微扰后的密度矩阵展开到高阶（以二阶响应为例），

$$
\begin{aligned}
\hat{\rho}_D(t) & \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \\
& + (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \\
& + \dots
\end{aligned}
$$

从而可观测量$\hat{A}$的响应为：

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

利用Trace的轮换不变性，有：

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

从而：

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

事实上有更general的结论：

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t_1\right), \dots ,\left[\hat{V}_{D}\left(t_n\right), \hat{\rho}_0 \right] \dots \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

可以计算任意阶响应

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

重复之前的操作，若可以把微扰分成外场（不一定要是标量场）和算符部分：

$$
\begin{aligned}
\hat{V}_S(t) = \hat{B}^\mu_S(t) F_\mu(t)
\end{aligned}
$$

则二阶响应可以写成，

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\} F_\mu(t')F_\nu(t'') \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} \int_{-\infty}^{+\infty} \mathrm{~d} t'' \chi_2^{\mu\nu}(t;t',t'') F_\mu(t')F_\nu(t'')
\end{aligned}
$$

其中$\chi_2^{\mu\nu}(t;t',t'')$为二阶响应率，定义为：

$$
\begin{aligned}
\chi_2^{\mu\nu}(t;t',t'') \equiv (-\frac{\mathrm{i}}{\hbar})^2 \Theta(t - t') \Theta(t' - t'') \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

可以推广到任意阶响应：

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{B}^{\mu_1}_{D}\left(t_1\right)\right], \dots , \hat{B}^{\mu_n}_{D}\left(t_n\right)\right]\right\} F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n) \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 \dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n  \chi_n^{\mu_1 \dots \mu_n}(t;t_1,\dots,t_n)  F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n)
\end{aligned}
$$

## Frequency Domain

先不考虑系统是否有时间平移对称性等性质，从Time Domain换到Frequency Domain，只是将所有时间参量作Fourier Transformation。

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) \xLeftrightarrow{F.T.} \chi_n(\omega ;\omega_1,\dots,\omega_n)
\end{aligned}
$$

这样做的好处是，一般的外场都是单一频率的，例如单色电磁波。而Frequency Domain的Kubo Formula可以直接告诉我们响应的频率和振幅。不过本质还是Fourier Transformation。

具体而言：

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

类似的将可观测量和外场也Fourier Transform到频率空间，

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

从而Frequency Domain中的Kubo Formula为：

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

最终Frequency Domain中的Kubo Formula为：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(-\omega_1) \dots F_{\mu_n}(-\omega_n)
\end{aligned}
$$

此处的负号也可以通过重新定义$\{t;t_1,\dots,t_n\}$这些参量的Fourier Transformation来去掉。

例如对“;”左右侧进行不同的Fourier Transformation：

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

则有：

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(\omega_1) \dots F_{\mu_n}(\omega_n)
\end{aligned}
$$

但事实上，正负频率的微扰总是同时存在的，上述讨论只是一个定义问题。

**为了Kubo Formula尽量不出现“-”号，之后的讨论我们都采用后一种定义**

此处推导的general的情形，对于$\{\bar{\omega} ;\omega_1,\dots,\omega_n\}$之间的关系并没有限制，任意频率的微扰都有可能激发另一个频率的响应。

但对于时间平移不变的响应函数，会对响应函数在Frequency Domain的形式有一定限制。

以最常见的线性响应为例，响应的频率一定和外场的频率相同，即

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega \pm \omega_1)
\end{aligned}
$$

而对于更一般的非线性响应，可以证明响应的频率是外场频率的和，即

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega \pm \sum_{i=1}^n \omega_i)
\end{aligned}
$$

其中"$\pm$"号取决于Frequency Domain中响应函数的定义。

## Time Translation Symmetry

当响应函数具有时间平移对称性时，可以证明响应函数有以下性质：

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

这是因为时间平移对称性使得响应函数中的时间全部改变相同量时不变，即：

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n(t + \tau;t_1+ \tau,\dots,t_n+ \tau)
\end{aligned}
$$

从而在$\{t;t_1,\dots,t_n\}$这些参量中，独立的只是他们的相对值，可以定义：

$$
\begin{aligned}
& \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n) \\
& = \chi_n(t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ;t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots,t_n + (t_{n-1} - t_n),t_n) \\
& = \chi_n(\sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ; \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots, (t_{n-1} - t_n),0)
\end{aligned}
$$

下面考虑响应函数具有时间平移对称性的物理含义，这事实上表示系统以及涉及响应的可观测量$\hat{A},\,\hat{B}$均是时间平移不变的，但这在不同的绘景下有不同的含义。

以我们最熟悉的Schrodinger Picture为例，算符不显含时间即可：

$$
\begin{aligned}
\hat{A}_S(t) = \hat{A},\,\hat{B}_S(t) = \hat{B}
\end{aligned}
$$

但在Dirac/Heisenberg Picture下表现为：

$$
\begin{aligned}
\hat{A}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right),\,\hat{B}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{B}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right)
\end{aligned}
$$

可以证明，“响应函数具有时间平移对称性”和“系统以及涉及响应的可观测量$\hat{A},\,\hat{B}$均是时间平移不变的”说的是一回事，以一阶响应函数为例：

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) & = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)  \operatorname{Tr} \left\{ \hat{\rho}_0\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

利用Trace的轮换不变性：

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

从而$\chi_1(t;t') \equiv G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$仅显含$(t-t')$。

推导中利用了$\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}$与时间演化算符$\exp \left(\pm\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t \right)$可对易的性质，因为两者均为$\mathcal{H}_0$的函数。

类似的，可以证明：

系统以及涉及响应的可观测量$\hat{A},\,\hat{B}$均有时间平移不变对称性时，任意阶的响应函数均具有时间平移对称性，这等价于响应函数可以写成$\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n)$的形式。

### Linear Order Susceptibility

下面来证明，时间平移不变性将导致响应的频率一定和外场的频率相同，即

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega - \omega_1)
\end{aligned}
$$

时间平移对称性要求：

$$
\begin{aligned}
\chi_1(t;t_1) = \chi_1^{\mathcal{T}}(t - t_1)
\end{aligned}
$$

从而Frequency Domain的线性响应函数为：

$$
\begin{aligned}
\chi_1(\omega ;\omega_1) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1}  \chi_1(t; t_1) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i(\omega_1 - \omega) t_1} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_1) e^{-i\omega (t - t_1)}   \chi_1^{\mathcal{T}}(t - t_1) \\
& = 2 \pi \delta(\omega - \omega_1) \tilde{\chi}_1^{\mathcal{T}}(\omega) \\
& \sim \delta(\omega - \omega_1)
\end{aligned}
$$

其中$\tilde{\chi}_1^{\mathcal{T}}(\omega)$为${\chi}_1^{\mathcal{T}}(t - t_1)$的Fourier Transformation：

$$
\begin{aligned}
\tilde{\chi}_1^{\mathcal{T}}(\omega) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau}   \chi_1^{\mathcal{T}}(\tau)
\end{aligned}
$$

### Nonlinear Order Susceptibility

对于更一般的非线性响应，可以证明响应的频率是外场频率的和，即

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

时间平移对称性要求（注意此处全部写成和$t_n$的差）：

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_n,t_1-t_n,\dots,t_{n-1} - t_n)
\end{aligned}
$$

从而Frequency Domain的响应函数为：

$$
\begin{aligned}
\chi_n(\omega ;\omega_1,\dots,\omega_n) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1} ... \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{i\omega_n t_n}  \chi_n(t; t_1,\dots,t_n) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{-i(\omega - \sum_{i=1}^n \omega_i) t_n} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_n) e^{-i\omega (t - t_n)} \int_{- \infty}^{+ \infty} \mathrm{~d} (t_1 - t_n) e^{i\omega_1 (t_1 - t_n)} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} (t_{n-1} - t_n) e^{i\omega_{n-1} (t_{n-1} - t_n)}  \chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n) \\
& = 2 \pi \delta(\omega - \sum_{i=1}^n \omega_i) \tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \\
& \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

其中$\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1})$为$\chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n)$的Fourier Transformation：

$$
\begin{aligned}
\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau} \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_1 e^{i\omega_1 \tau_1} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_{n-1} e^{i\omega_{n-1} \tau_{n-1}}  \chi_n^{\mathcal{T}}(\tau,\dots,\tau_{n-1})
\end{aligned}
$$

总之，有了二阶响应的一般Kubo Formula，我们就能轻松（并不）地将之前考虑的各式各样的线性响应推广到非线性响应了，例如计算非线性电导率，非线性磁化率，非线性电极化率，etc.

## Kubo Formula in Momentum Space

对于连续介质（连续空间平移对称性）或者晶体（离散空间平移对称性），教科书中往往也会给出动量空间中的Kubo Formula。

但这本质上只是对另一种参数——坐标——进行了Fourier Transform罢了，本质上Time Domain与Frequency Domain之间的Fourier Transform没有本质区别。甚至没有空间平移对称性时，也可以对每一个坐标参量作变换，得到最最general的形式。

可以想像，与具有时间平移对称性体系的响应函数类似，具有空间平移对称性的系统的响应函数也会满足类似（准）动量守恒的形式，即：

$$
\begin{aligned}
\chi_n(k; k_1,\dots,k_n) \sim \delta(k - \sum_{i=1}^n k_i)
\end{aligned}
$$

## Second Harmonic Generation & Zero Frequency Term

下面考虑一种常见的含时微扰，频率为$\omega_0>0$的时谐微扰：

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega_0 t} + \hat{H'}^\dagger e^{i\omega_0 t}
\end{aligned}
$$

可以看出外场的频率有$\pm \omega_0$的贡献，对于时间平移不变的体系，其一阶响应也应该是只有$\pm \omega_0$频率的项。

而对于二阶响应：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \chi_2(\omega; \omega_1, \omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

若体系有时间平移对称性：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

而外场的频谱为：

$$
\begin{aligned}
F(\omega) \sim \delta(\omega \pm \omega_0)
\end{aligned}
$$

从而二阶响应可以有二倍频响应，即所谓的“2nd Harmonic Generation”：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \pm \omega_0) \sim \delta(\omega \pm 2\omega_0)
\end{aligned}
$$

也可以有Zero Frequency Response，即：

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \mp \omega_0) \sim \delta(\omega)
\end{aligned}
$$

不论是2nd Harmonic Generation还是Zero Frequency Response，在半导体的nonlinear electro-optical response中都是凝聚态物理中有趣的topic。

## Kubo Formula for Fermi Golden Rule

事实上，量子系统在光激发下的跃迁速率（概率）也可以看成是一种系统对外界微扰的响应。

此时，系统的观测量为末态投影算符，未受微扰的密度矩阵则为初态投影算符，外场则为光波的时谐电磁场：

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

跃迁速率则为：

$$
\begin{aligned}
\mathcal{I}_{i \rightarrow f} = \frac{d}{dt} \langle \hat{\mathcal{O}} \rangle
\end{aligned}
$$

我们暂且跳过推导细节，直接看系统的二阶响应（可以证明一阶响应为0），也将会有2nd Harmonic Generation对应的二倍频响应和Zero Frequency Response。

后者对应一般的Fermi Golden Rule计算的常跃迁速率，而前者则是我们上一节提到的，Fermi Golden Rule中略去的二倍频响应。在长时间平均近似下，便完全对应Fermi Golden Rule的结果。

所以Fermi Golden Rule本质上是一种二阶响应，可以用Nonlinear Order Kubo Formula来计算。