---
title: "🔥费米黄金定则？焦耳热罢了！"
date: 2023-03-07T22:30:00-05:00
draft: false
math: true
tags: ["Quantum Mechanics", "Joule Heat"]
categories: ["Physics Notes"]
---

本文旨在阐述费米黄金法则和焦耳热的一致性。

<!--more-->

## Introduction

费米黄金法则能计算系统对电磁场的吸收，而Kubo Formula能计算电流响应，用焦耳热公式也能计算电磁场的吸收。

前者似乎完全从量子跃迁的角度计算，而后者似乎完全从焦耳热的角度计算。但两者本质上都是量子力学中的含时围绕理论的应用，这一点我们在前两篇文章中便有所涉及，只不过对两者的一致性没有详尽的阐述，有兴趣的读者可以移步浏览：

https://zhuanlan.zhihu.com/p/611688122

https://zhuanlan.zhihu.com/p/611996682

可以证明，费米黄金法则对应Kubo Formula中哈密顿量$H_0$的二阶响应变化率$\frac{d }{dt}\langle H_0 \rangle^{(2)}$，而此二阶响应变化率可以表示成电流线性响应与外加电场的内积$\langle \hat{\mathbf{J}} \rangle^{(1)} \cdot \mathbf{E}$。

## Fermi Golden Rule

费米黄金法则旨在计算时谐外场微扰下，量子系统从初态$|i\rangle$到末态$|f\rangle$（均为$H_0$的本征态）的跃迁速率。在之前的费米黄金法则的文章中，我们用Dirac Picture重新推导了一遍，而使用Dirac Picture是为了更好与Kubo Formula进行比较。

Dirac表象下态的运动方程：

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

对运动方程积分后迭代可以得到Dirac表象下态随时间演化的微扰展开形式。假设系统在$t = t_0$时，初态为$|i\rangle$，则：

$$
\begin{aligned}
| \psi (t) \rangle_D & = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle + (-i/\hbar)^2 \int_{t_0}^{t}dt_1 \int_{t_0}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2)|i\rangle + \dots \\
& = | \psi^{(0)} \rangle + | \psi^{(1)}\rangle + | \psi^{(2)}\rangle + \dots
\end{aligned}
$$

则$t$时刻$|f\rangle$态的概率为也可以微扰展开成：

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

Kubo Formula的推导也在相互作用（Dirac）绘景下完成，只不过计算的是系统密度矩阵的演化，而非波函数的演化。

相互作用（Dirac）绘景下密度矩阵的运动方程：

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

积分后重复迭代，我们可以得到密度矩阵的展开式：

$$
\begin{aligned}
\hat{\rho}_D(t) & = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]\\
& = \hat{\rho}^{(0)} + \sum_{i=1}^{\infty} \hat{\rho}^{(i)}
\end{aligned}
$$

对于纯态的密度矩阵，初态为$| i \rangle$，不难发现，密度矩阵的微扰展开与波函数的微扰展开是一致的，因为两者均是量子力学的含时微扰理论。

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

要求$|f\rangle$态的概率，用密度矩阵（Kubo Formula）的语言描述，便是把$|f\rangle$态的投影算符作为可观测量：

$$
\begin{aligned}
\hat{\mathcal{O}} = | f \rangle \langle f |
\end{aligned}
$$

那么$|f\rangle$态的概率为：

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

可见费米黄金法则和Kubo Formula在计算末态概率时，是一回事。密度矩阵也可以推广到混态，从而计算有概率分布的初态出发的末态概率。

我们还是先关注纯态密度矩阵，注意到波函数的零阶展开项为

$$
\begin{aligned}
| \psi^{(0)} = | i \rangle
\end{aligned}
$$

因此，末态概率的零阶和一阶展开项均为零，从而末态概率的最低阶响应来自二阶项，所以我们说：

**费米黄金法则和末态概率的二阶响应一致。**

## Absorption Rate

用费米黄金法则计算系统的能量吸收率时，我们计算的是：

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 
\end{aligned}
$$

其中$E_{i,f}$为初态、末态$|i\rangle,\,|f\rangle$的能量，不难理解，能量变化率就是跃迁速率乘以能量的改变，并对所有可能的跃迁求和。

推广到Kubo Formula的语言中，能量吸收率其实是未受微扰的哈密顿量$\hat{H}_0$的期望值的变化率：

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

这看着很intuitive，也不难证明它和Fermi Golden Rule说的是一回事。

$$
\begin{aligned}
P & = (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle|^2 \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}(E_f - E_i) | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}E_f | f \rangle \langle f |\right) | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f} | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \hat{H}_0 | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \mathbb{I} | \psi (t) \rangle \right\} \\
& = \frac{d}{dt}\langle \hat{H}_0 \rangle - 0
\end{aligned}
$$

这是纯态下的结果，混态不过是按概率叠加各个结果，不难想象也能成立。

这样，我们便把跃迁速率、能量吸收速率等语言统一并推广到了Kubo Formula中。值得一提，与$|f\rangle$态的概率类似，$\langle \hat{H}_0 \rangle$的最低阶非零响应也从二阶开始算起。

## Joule Heat = Energy Absorption

下面我们来证明焦耳热和能量吸收率在Kubo Formula中的一致性。

焦耳热定义为电流响应与外加电场的内积$\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$。

对于电场微扰（我们先考虑空间分布均匀的时变电场），微扰哈密顿量为：

$$
\begin{aligned}
\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t) = -(-e) \hat{\mathbf{r}} \cdot \mathbf{E}(t)
\end{aligned}
$$

电流响应$\langle \hat{\mathbf{J}} \rangle (t)$的n阶微扰：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \propto \mathcal{O}(|\mathbf{E}|^n) \propto \mathcal{O}(V^n)
\end{aligned}
$$

对应焦耳热$\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$的n+1阶微扰：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \cdot \mathbf{E}(t) \propto {O}(|\mathbf{E}|^{n+1}) \propto \mathcal{O}(V^{n+1})
\end{aligned}
$$

从而电流的线性（一阶）响应的焦耳热和能量变化率的二阶响应，微扰展开阶数的层面上是一致的。

我们的目标是证明**电流的线性（一阶）响应的焦耳热和能量变化率的二阶响应**在表达式上严格一致。

## Current Response

此处我们定义“电流”为电极化的变化率，即电流密度的体积分：

$$
\begin{aligned}
\hat{\mathbf{J}} \equiv \iiint dV \hat{\mathbf{j}} \equiv \frac{d}{dt} \hat{\mathbf{P}}
\end{aligned}
$$

在Dirac Picture下，电流算符与电极化算符的关系为：

$$
\begin{aligned}
\hat{\mathbf{J}}_D = \frac{d}{dt} \hat{\mathbf{P}}_D = (- \frac{i}{\hbar}) [ \hat{\mathbf{P}}_D, \hat{H}_0 ]
\end{aligned}
$$

从而微扰$\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t)$的一阶电流响应为：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D, \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} 
\end{aligned}
$$

从而一阶电流响应对应的二阶焦耳热为：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) \cdot \mathbf{E} (t) , \hat{V}_D(t_1)] \right\}  \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D \cdot \mathbf{E} (t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

而$\hat{\mathbf{P}}_D \cdot \mathbf{E} (t)$正好就是微扰$-\hat{V}_D(t)$的表达式，具体而言：

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ -\hat{V}_D(t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{H}_0, \hat{V}_D(t) ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

看到两个$\hat{V}_D$的对易子，不难看出这基本就是$\langle \hat{H}_0 \rangle$的二阶响应的变化率，少了一个时间积分是因为对时间求了一次导，具体而言：

$$
\begin{aligned}
\langle \hat{H}_0 \rangle^{(2)} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[{\hat{H}_0}_D(t), \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
& = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{H}_0, \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
\end{aligned}
$$

此处运用了${\hat{H}_0}$在Dirac Picture下就是其本身的性质，以及${\hat{H}_0}_D(t)$不显含时间的性质（时间平移对称性）：

$$
\begin{aligned}
{\hat{H}_0}_D(t) = e^{ \frac{i}{\hbar}\hat{H}_0 t} {\hat{H}_0} e^{- \frac{i}{\hbar}\hat{H}_0 t} = \hat{H}_0
\end{aligned}
$$

那么此时，$\langle \hat{H}_0 \rangle$的二阶响应对时间的依赖，仅在第一个时间积分的上界，所以其变化率就少了一个时间积分（并且把积分参量$t_1$改为$t$），并且和电流一阶响应的焦耳热表达式完全一致：

$$
\begin{aligned}
\frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} &= (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\} \\
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\} \\
\Rightarrow P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} & = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t)
\end{aligned}
$$

不难验证，更高阶的电流响应和能量变化率也能够一一对应。

由此我们证明了能量变化率和电流响应焦耳热公式的一致性。

## Summary

综上所述，我们证明了费米黄金法则和焦耳热公式计算量子系统对电磁波吸收的一致性。

首先，我们证明了费米黄金法则计算的能量吸收率与能量响应变化率一致性：

$$
\begin{aligned}
\underbrace{P = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2}_{\text{Fermi Golden Rule}} \ \Leftrightarrow \ P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

之后，我们证明了用电流的响应乘以电场的焦耳热公式与能量响应变化率一致性：

$$
\begin{aligned}
& \underbrace{P = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\}}_{\text{Joule Heat}} \\
\Leftrightarrow \  &P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} = (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\}
\end{aligned}
$$

所以，电流的响应乘以电场的焦耳热公式，与量子跃迁速率乘以能量变化的费米黄金法则，本质上都是能量响应变化率。

由此，我们可以说看似宏观的“焦耳热”和看似微观的“费米黄金法则”是一回事。