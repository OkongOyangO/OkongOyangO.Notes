---
title: "What did Fermi Golden Rule Miss?"
date: 2026-01-10T02:59:13Z
draft: false
math: true
tags: ["Quantum Mechanics", "Fermi Golden Rule"]
categories: ["Physics Notes"]
---

This article aims to calculate the strict quantum transition rate and points out that the Fermi Golden Rule is the result of its "long-time average". The strict quantum transition rate contains an additional double-frequency oscillation term with non-negligible amplitude compared to the Fermi Golden Rule. The relationship between the two is similar to "instantaneous power" and "average power" in AC circuits.

## Fermi Golden Rule

The Fermi Golden Rule aims to calculate the transition rate of a quantum system from an initial state $|i\rangle$ to a final state $|f\rangle$ (both are eigenstates of $H_0$) under a time-harmonic external field perturbation. Since this is well-covered in quantum mechanics courses, we will quickly go through it in the Dirac picture (interaction picture). The Dirac picture is used to better compare with the Kubo Formula.

Equation of motion for states in the Dirac picture:

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

Operators in the Dirac picture:

$$
\begin{aligned}
\hat{\mathcal{O}}_D(t) = e^{i\hat{H_0}t/\hbar} \hat{\mathcal{O}}_S(t) e^{-i\hat{H_0}t/\hbar}
\end{aligned}
$$

The subscripts $D$ and $S$ represent the Dirac picture and Schrödinger picture, respectively.

Integrating the equation of motion and iterating gives the evolution operator $\mathcal{U}(t,t')$ in the Dirac picture:

$$\begin{aligned}
\mathcal{U}(t,t') & = \mathcal{T} e^{-i \int_{t'}^{t}dt'' \hat{V}_D(t'')/\hbar }  \\
& = 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) + \frac{1}{2!} (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{t}dt_2 \mathcal{T} \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots \\
& = 1 + (-i/\hbar) \int_{t'}^{t}dt_1 \hat{V}_D(t_1) +  (-i/\hbar)^2 \int_{t'}^{t}dt_1 \int_{t'}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2) + \dots 
\end{aligned}$$

where $\mathcal{T}$ is the time ordering operator, placing operators with smaller times on the right to act on the state vector first. The expression without time ordering is also given above, which can be obtained by integrating the equation of motion and iterating.

Assume the system is in the initial state $|i\rangle$ at $t = t_0$. Taking the approximation to order $\mathcal{O}(V)$:

$$
\begin{aligned}
| \psi (t) \rangle_D & = \mathcal{U}(t,t_0) | \psi (t_0) \rangle_D \\
& = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

The probability amplitude of the state $|f\rangle$ at time $t$ is:

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D = 0 + (-i/\hbar) \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle
\end{aligned}
$$

For a time-harmonic perturbation with frequency $\omega > 0$:

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

Then:

$$
\begin{aligned}
\langle f | \psi (t) \rangle_D  = (-i/\hbar) & \int_{t_0}^{t}dt_1 \langle f | e^{i\hat{H_0}t_1/\hbar} \hat{V}_S(t_1) e^{-i\hat{H_0}t_1/\hbar}|i\rangle \\
= (-i/\hbar) & \int_{t_0}^{t}dt_1 e^{i \omega_{fi} t_1}[ \langle f | \hat{H'}^\dagger |i\rangle e^{i \omega t_1} + \langle f | \hat{H'} | i \rangle e^{-i \omega t_1} ] \\
= (-i/\hbar)& [ \underbrace{\frac{e^{i (\omega_{fi} + \omega)t} - e^{i (\omega_{fi} + \omega)t_0} }{i(\omega_{fi} + \omega)} \langle f | \hat{H'}^\dagger |i\rangle}_{(1)} \\
& + \underbrace{\frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle}_{(2)} ]
\end{aligned}
$$

where $\omega_{fi} = (E_f - E_i)/\hbar$ corresponds to the transition energy from the initial state $|i\rangle$ to the final state $|f\rangle$.

### Common Approach in Quantum Mechanics

The common approach in quantum mechanics courses is to consider that when $\omega \rightarrow \pm \omega_{fi}$, (1) will be much smaller or much larger than (2), thus only considering the contribution of one term.

Taking $\omega \rightarrow + \omega_{fi}$ as an example, calculate the probability of the system being in state $|f\rangle$ at time $t$:

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & \approx |(-i/\hbar) \frac{e^{i (\omega_{fi} - \omega)t} - e^{i (\omega_{fi} - \omega)t_0} }{i(\omega_{fi} - \omega)} \langle f | \hat{H'} |i\rangle |^2 \\
& = \frac{1}{\hbar^2} | (-i e^{i(\omega_{fi} - \omega)(t - t_0)/2}) \frac{2 \sin[(\omega_{fi} - \omega)(t - t_0)/2]}{\omega_{fi} - \omega} \langle f | \hat{H'} |i\rangle|^2 \\
& = \frac{4}{\hbar^2} \frac{\sin^2[(\omega_{fi} - \omega)(t - t_0)/2]}{(\omega_{fi} - \omega)^2} |\langle f | \hat{H'} |i\rangle|^2 \\
& \xrightarrow{t - t_0 \rightarrow + \infty} \frac{2 \pi}{\hbar^2} |\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) \times (t - t_0)
\end{aligned}
$$

Here, a less common limit is used:

$$
\begin{aligned}
\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)
\end{aligned}
$$

Thus, the transition rate is (considering both $\omega \rightarrow \pm \omega_{fi}$):

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} = \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 = \frac{2 \pi}{\hbar^2} [|\langle f | \hat{H'} |i\rangle|^2 \delta (\omega - \omega_{fi}) + \langle i | \hat{H'} | f \rangle|^2 \delta (\omega + \omega_{fi}) ]
\end{aligned}
$$

### Strict Derivation

The result given by the above method is correct, but the method of taking limits seems not rigorous enough, especially that extremely unfriendly limit $\lim_{t \rightarrow + \infty} \frac{\sin^2(\omega t)}{\omega^2} = \pi t \delta(\omega)$.

In fact, we can obtain $\mathcal{I}_{i\rightarrow f}$ through a more rigorous derivation.

Furthermore, we will find that the previous derivation only considered the zero-frequency term in $\mathcal{I}_{i\rightarrow f}$, while the stricter result also contains a double-frequency term.

However, the double-frequency oscillation term is zero under long-time average, so a stricter definition of the transition rate should be the "long-time average transition rate":

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \equiv \left\langle \frac{d}{dt} |\langle f | \psi  \rangle_D|^2 \right\rangle_t
\end{aligned}
$$

For a more rigorous derivation, we start from before the "$\approx$" sign and try to use strict equal signs and familiar limit formulas:

$$
\begin{aligned}
|\langle f | \psi (t) \rangle_D|^2 & = \left|-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right|^2 \\
& = \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right)
\end{aligned}
$$

Thus the transition rate:

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{d}{dt} \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \frac{d}{dt} \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& =  \left(-\frac{i}{\hbar}  \langle f |\hat{V}_D(t)|i\rangle\right) \times \left(\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle i |\hat{V}_D(t_1)|f\rangle\right) \\
& + \left(-\frac{i}{\hbar} \int_{t_0}^{t}dt_1 \langle f |\hat{V}_D(t_1)|i\rangle\right) \times \left(\frac{i}{\hbar}  \langle i |\hat{V}_D(t)|f\rangle\right) \\
& = \frac{1}{\hbar^2} \int_{t_0}^{t}dt_1 \left( \langle f |\hat{V}_D(t)|i\rangle\langle i |\hat{V}_D(t_1)|f\rangle + \langle f |\hat{V}_D(t_1)|i\rangle\langle i |\hat{V}_D(t)|f\rangle \right)
\end{aligned}
$$

For a time-harmonic perturbation with frequency $\omega > 0$:

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega t} + \hat{H'}^\dagger e^{i\omega t}
\end{aligned}
$$

We have:

$$
\begin{aligned}
\langle i |\hat{V}_D(t)|f\rangle = e^{-i\omega_{fi}t}(\langle i |\hat{H'}^\dagger|f\rangle e^{i\omega t} + (\langle i |\hat{H'}|f\rangle e^{-i\omega t})
\end{aligned}
$$

For convenience, let's denote the matrix elements of $\hat{H'}$ as:

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

Note specifically that here only $\hat{V}$ is a Hermitian operator, $\hat{H'}$ is not necessarily Hermitian, so generally:

$$
\begin{aligned}
H_{if} = (H^\dagger)_{fi}^* \neq H_{fi}^*
\end{aligned}
$$

Thus:

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} (H_{if}^*e^{i\omega t} + H_{fi} e^{-i\omega t})(H_{fi}^*e^{i\omega t'} + H_{if} e^{-i\omega t'}) \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} (H_{fi}^*e^{i\omega t} + H_{if} e^{-i\omega t})(H_{if}^*e^{i\omega t'} + H_{fi} e^{-i\omega t'}) \\
& = \frac{1}{\hbar^2} \int_{t_0}^t dt'   e^{i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{-i \omega (t - t')} }_{(1.1)} + \underbrace{|H_{if}|^2 e^{i \omega (t - t')} }_{(1.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(1.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(1.4)} \right] \\
& +\frac{1}{\hbar^2} \int_{t_0}^t dt'e^{-i\omega_{fi} (t-t')} \left[ \underbrace{|H_{fi}|^2 e^{i \omega (t - t')} }_{(2.1)} + \underbrace{|H_{if}|^2 e^{-i \omega (t - t')} }_{(2.2)}  + \underbrace{H_{fi}^* H_{if}^* e^{i \omega (t + t')}}_{(2.3)} + \underbrace{H_{if} H_{fi} e^{-i \omega (t + t')}}_{(2.4)} \right]
\end{aligned}
$$

To discuss the approximation under long-time evolution, let's take $t_0 \rightarrow - \infty$.

Focusing on terms (1.1)+(2.1), after transforming the integration variable:
$$
\begin{aligned}
(1.1) + (2.1) & = \frac{|H_{fi}|^2}{\hbar^2} \int_{- \infty}^t dt' \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{0}^{+ \infty} d(t - t') \left[ e^{i (\omega - \omega_{fi}) (t - t')} + e^{-i (\omega - \omega_{fi}) (t - t')}  \right] \\
& = \frac{|H_{fi}|^2}{\hbar^2} \int_{-\infty}^{+ \infty} d\tau e^{i (\omega - \omega_{fi}) \tau} \\
& = \frac{2 \pi}{\hbar^2} |H_{fi}|^2 \delta({\omega - \omega_{fi}})
\end{aligned}
$$

Here we obtained one term of the Fermi Golden Rule. It is not difficult to find that the other term comes from (1.2)+(2.2), thus:

$$
\begin{aligned}
(1.1) + (2.1) + (1.2) + (2.2) = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$

However, the specific meanings of (1.3)+(2.3) and (1.4)+(2.4) have not been discussed yet, which is also an item generally ignored in quantum mechanics courses.

Further discussion reveals that it is a double-frequency oscillation term, and as $t \rightarrow \infty$, the oscillation frequency is comparable to $\delta({\omega - \omega_{fi}})$ in the Fermi Golden Rule, so it cannot be ignored in a strict discussion.

In other words, the Fermi Golden Rule eliminates the contribution of this oscillation term by taking the "long-time average approximation". This is like calculating the average power in an AC circuit system.

### Double Frequency Term

Now let's calculate terms (1.3)+(2.3) and (1.4)+(2.4).

Taking (1.3)+(2.3) as an example:

$$
\begin{aligned}
(1.3) + (2.3) & = \frac{1}{\hbar^2} H_{fi}^* H_{if}^* \int_{- \infty}^t dt' e^{i \omega (t + t')}   \left[e^{i\omega_{fi} (t-t')} + e^{-i\omega_{fi} (t-t')} \right] \\
& = \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^t dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{1}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega - \omega_{fi}) t'} + e^{i (\omega - \omega_{fi})t} \int_{- \infty}^{+ \infty} dt'  e^{i(\omega + \omega_{fi}) t'}  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{i (\omega + \omega_{fi})t} \delta( \omega - \omega_{fi}) + e^{i (\omega - \omega_{fi})t} \delta( \omega + \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right]
\end{aligned}
$$

Similarly,

$$
\begin{aligned}
(1.4) + (2.4) \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right]
\end{aligned}
$$


It can be seen that the strict transition rate $\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2$ contains not only the constant term but also the double-frequency term, and both have comparable amplitudes and contain $\delta( \omega \pm \omega_{fi})$.

Only the transition rate defined under the "long-time average approximation" $\left\langle\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 \right\rangle_\tau$, i.e., retaining only the constant term, corresponds to the Fermi Golden Rule.

It should also be noted that whether or not the "long-time average approximation" is taken, the transition rate must be discussed under the condition that the evolution time is long enough, otherwise the $\delta( \omega \pm \omega_{fi})$ in the absorption spectrum will have broadening of the order $(t - t_0)^{-1}$.

However, general systems are not completely dissipation-free, and there is dissipation broadening $\sim \tau^{-1}$ corresponding to the dissipation characteristic time $\tau$. As long as $t - t_0 \gg \tau, \omega_{fi}^{-1}$, it will not have much impact on the absorption spectrum. The discussion on dissipation broadening $\sim \tau^{-1}$ is omitted here.

## Summary

Under a time-harmonic perturbation with frequency $\omega > 0$ for a long time ($t_0 \rightarrow - \infty,\, t \rightarrow + \infty$):

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

The strict transition rate expression from the initial state $| i \rangle$ to the final state $| f \rangle$ is:

$$
\begin{aligned}
\frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 & \xrightarrow[t_0 \rightarrow - \infty]{t \rightarrow + \infty} \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right] \\
& + \frac{2\pi}{\hbar^2} H_{fi}^* H_{if}^*  \left[ e^{2i\omega_{fi} t} \delta( \omega - \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega + \omega_{fi})  \right] \\
& + \frac{2\pi}{\hbar^2}  H_{if} H_{fi} \left[ e^{2i\omega_{fi} t} \delta( \omega + \omega_{fi}) + e^{-2i \omega_{fi} t} \delta( \omega - \omega_{fi})  \right] \\
& = \frac{2\pi}{\hbar^2} \left\{ \left[ |H_{fi}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{2i\omega_{fi} t}) \right]  \delta( \omega + \omega_{fi}) + \left[ |H_{if}|^2 + 2\operatorname{Re}(H_{if} H_{fi} e^{-2i\omega_{fi} t}) \right] \delta( \omega - \omega_{fi})  \right\}
\end{aligned}
$$

where the constant term is the result of the Fermi Golden Rule, and there is also a double-frequency term, with comparable amplitude.

Under the "long-time average approximation" (observation time is much larger than the system eigen-time $\omega_{fi}^{-1}$), the double-frequency term can be omitted, and the long-time average transition rate is consistent with the Fermi Golden Rule result, which is similar to calculating the average power of an AC system.

$$
\begin{aligned}
\mathcal{I}_{i\rightarrow f} & \equiv \lim_{T \rightarrow +\infty} \frac{1}{2T} \int_{-T}^T \left.\left(\frac{d}{dt} |\langle f | \psi  \rangle_D|^2\right)\right|_{t = \tau} d\tau \\
& = \frac{2 \pi}{\hbar^2} \left[ |H_{fi}|^2 \delta({\omega - \omega_{fi}}) + |H_{if}|^2 \delta({\omega + \omega_{fi}}) \right]
\end{aligned}
$$
