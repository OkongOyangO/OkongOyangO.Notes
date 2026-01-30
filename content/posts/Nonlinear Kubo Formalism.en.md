---
title: "Nonlinear Response Theory of the Kubo Formula"
date: 2026-01-08T21:54:37-05:00
draft: false
math: true
tags: ["Nonlinear Response", "Kubo Formula"]
categories: ["Physics Notes"]
---

#! https://zhuanlan.zhihu.com/p/611996682
# Nonlinear Response Theory of the Kubo Formula

This article aims to derive the nonlinear response theory of the Kubo Formula.

## Introduction

Both linear and nonlinear response theories of the Kubo Formula are essentially perturbation theories in quantum mechanics.

Linear response is more common; for example, experimentally measured susceptibilities such as conductivity, magnetic susceptibility, and electric polarizability are all linear response functions (Retarded Green Functions).

However, nonlinear response also has its application values, such as second-order current response in semiconductors, including Second Harmonic Generation, Injection and Shift Current, etc.

Second-order response can even be used to explain the two types of responses discussed in the previous section on Fermi Golden Rule: the constant transition rate and the second harmonic transition rate.

https://zhuanlan.zhihu.com/p/611688122

It can be seen that **as long as one is bold enough, nonlinear response is everywhere**.

## Density Matrix in Dirac Picture

The derivation of the Kubo Formula starts from the evolution of the system's density matrix in the interaction (Dirac) picture.

In the section on Fermi Golden Rule, we have already derived the equation of motion for the wave function in the interaction (Dirac) picture.

Simply viewing the density matrix as $\hat{\rho}_D(t) \sim | \psi (t) \rangle_D \langle \psi(t) |_D$ helps us quickly recall the equation of motion for the density matrix in the interaction (Dirac) picture:

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

By integrating and iterating repeatedly, we can obtain the expansion of the density matrix:

$$
\begin{aligned}
\hat{\rho}_D(t) = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]
\end{aligned}
$$

Note that the upper limit of each integral is not always $t$.

## Linear Response

Consider only the linear response:

$$
\begin{aligned}
\hat{\rho}_D(t)  \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right]
\end{aligned}
$$

where $\hat{\rho}_0$ is the equilibrium density matrix:

$$
\begin{aligned}
\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}
\end{aligned}
$$

We wish to investigate the time evolution of an observable $\hat{A}$:

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

where,

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

For the following perturbation form:

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

Using the cyclic property of the Trace, it can be proven that:

$$
\begin{aligned}
\operatorname{Tr}\left\{\left[\hat{B}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \hat{A}_D(t) \right\} = \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

Thus:

$$
\begin{aligned}
\langle\hat{A}\rangle_t = \langle\widehat{A}\rangle_0 +(-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime}) \operatorname{Tr}\left\{\rho_0\left[\hat{A}_D(t), \hat{B}_{D}\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

In this way, physical quantities in the expression can be written in the form of $\operatorname{Tr}\left\{\rho_0(\dots)\right\}$.

This indicates that the near-equilibrium response can be determined by the observables of the equilibrium state.

Generally, we consider the difference of the observable $\hat{A}$ under perturbation from the equilibrium state, so we can also write the linear response in the following form:

$$
\begin{aligned}
\Delta A_t  =\langle\hat{A}\rangle_t-\langle\widehat{A}\rangle_0=-\frac{\mathrm{i}}{\hbar} \int_{-\infty}^t \mathrm{~d} t^{\prime} F(t^{\prime})\left\langle\left[\widehat{A}^{\mathrm{D}}(t), \widehat{B}^{\mathrm{D}}\left(t^{\prime}\right)\right]_{-}\right\rangle_0
\end{aligned}
$$

Or written as:

$$
\begin{aligned}
\Delta A_t =  \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) F(t^{\prime})
\end{aligned}
$$

This is the form of the linear response Kubo Formula in the Time Domain.

It contains the retarded Green Function,

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_D(t), \hat{B}_D\left(t^{\prime}\right)\right]\right\rangle_0 = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)\left\langle\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\rangle_0
\end{aligned}
$$

Here, since we are calculating the properties of the equilibrium state, the subscripts $D, H$ representing the Dirac and Heisenberg Pictures make no difference, which reflects from another aspect that the system's near-equilibrium response is completely determined by the system's equilibrium properties.

The linear response formula given so far is general and does not consider properties like time translation symmetry (when $\hat{A}_S, \hat{B}_S$ do not explicitly contain time $t$). If the retarded Green Function $G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$ possesses time translation symmetry:

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) = G_{A B}^{\mathrm{ret}}\left(t -  t^{\prime}\right)
\end{aligned}
$$

we can obtain a more concise linear response theory in the Frequency Domain. We will discuss this further after deriving the general second-order response.

## Nonlinear Response

Now we want to calculate the nonlinear (higher-order) response. We simply expand the perturbed density matrix to higher orders and repeat the derivation above.

Expanding the perturbed density matrix to higher orders (taking the second-order response as an example),

$$
\begin{aligned}
\hat{\rho}_D(t) & \approx \hat{\rho}_0 + (-\frac{\mathrm{i}}{\hbar}) \int_{-\infty}^t \mathrm{~d} t^{\prime} \left[\hat{V}_{D}\left(t^{\prime}\right), \hat{\rho}_0 \right] \\
& + (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \\
& + \dots
\end{aligned}
$$

Thus the response of the observable $\hat{A}$ is:

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

Using the cyclic property of the Trace, we have:

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t^{\prime}\right), \left[\hat{V}_{D}\left(t''\right), \hat{\rho}_0 \right] \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

Thus:

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{V}_{D}\left(t^{\prime}\right)\right] , \hat{V}_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

In fact, there is a more general conclusion:

$$
\begin{aligned}
\operatorname{Tr} \left\{ \left[\hat{V}_{D}\left(t_1\right), \dots ,\left[\hat{V}_{D}\left(t_n\right), \hat{\rho}_0 \right] \dots \right] \hat{A}_D(t) \right\} = \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

We can calculate the response of any order:

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{V}_{D}\left(t_1\right)\right], \dots , \hat{V}_{D}\left(t_n\right)\right]\right\}
\end{aligned}
$$

Repeating the previous operation, if the perturbation can be separated into an external field (not necessarily a scalar field) and an operator part:

$$
\begin{aligned}
\hat{V}_S(t) = \hat{B}^\mu_S(t) F_\mu(t)
\end{aligned}
$$

Then the second-order response can be written as,

$$
\begin{aligned}
\langle\hat{A}\rangle_2 & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t^{\prime} \int_{-\infty}^{t'} \mathrm{~d} t'' \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\} F_\mu(t')F_\nu(t'') \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t^{\prime} \int_{-\infty}^{+\infty} \mathrm{~d} t'' \chi_2^{\mu\nu}(t;t',t'') F_\mu(t')F_\nu(t'')
\end{aligned}
$$

where $\chi_2^{\mu\nu}(t;t',t'')$ is the second-order susceptibility, defined as:

$$
\begin{aligned}
\chi_2^{\mu\nu}(t;t',t'') \equiv (-\frac{\mathrm{i}}{\hbar})^2 \Theta(t - t') \Theta(t' - t'') \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{A}_D(t), \hat{B}^\mu_{D}\left(t^{\prime}\right)\right] , \hat{B}^\nu_{D}\left(t''\right)\right] \right\}
\end{aligned}
$$

This can be generalized to any order of response:

$$
\begin{aligned}
\langle\hat{A}\rangle_n & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2 \dots \int_{-\infty}^{t_{n-1}} \mathrm{~d} t_n \operatorname{Tr} \left\{\rho_0\left[ \dots\left[\hat{A}_D(t), \hat{B}^{\mu_1}_{D}\left(t_1\right)\right], \dots , \hat{B}^{\mu_n}_{D}\left(t_n\right)\right]\right\} F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n) \\
& = \int_{-\infty}^{+ \infty} \mathrm{~d} t_1 \dots \int_{-\infty}^{+\infty} \mathrm{~d} t_n  \chi_n^{\mu_1 \dots \mu_n}(t;t_1,\dots,t_n)  F_{\mu_1}(t_1) \dots F_{\mu_n}(t_n)
\end{aligned}
$$

## Frequency Domain

First, without considering whether the system has time translation symmetry, we switch from Time Domain to Frequency Domain by simply performing a Fourier Transformation on all time parameters.

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) \xLeftrightarrow{F.T.} \chi_n(\omega ;\omega_1,\dots,\omega_n)
\end{aligned}
$$

The advantage of doing this is that general external fields are single-frequency, such as monochromatic electromagnetic waves. The Kubo Formula in the Frequency Domain can directly tell us the frequency and amplitude of the response. However, essentially it is still a Fourier Transformation.

Specifically:

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

Similarly, Fourier Transform the observable and the external field to frequency space,

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

Thus, the Kubo Formula in the Frequency Domain is:

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

Finally, the Kubo Formula in the Frequency Domain is:

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(-\omega_1) \dots F_{\mu_n}(-\omega_n)
\end{aligned}
$$

The negative sign here can also be removed by redefining the Fourier Transformation of the parameters $\{t;t_1,\dots,t_n\}$.

For example, performing different Fourier Transformations on the left and right sides of ";":

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

Then we have:

$$
\begin{aligned}
\langle\hat{A}\rangle_n(\bar{\omega}) & =  \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_1}{2 \pi}  \dots \int_{- \infty}^{+ \infty} \frac{\mathrm{~d} \omega_n}{2\pi}  \chi_n^{\mu_1 \dots \mu_n}(\bar{\omega} ;\omega_1,\dots,\omega_n) F_{\mu_1}(\omega_1) \dots F_{\mu_n}(\omega_n)
\end{aligned}
$$

But in fact, positive and negative frequency perturbations always exist simultaneously, so the above discussion is just a matter of definition.

**To avoid "-" signs in the Kubo Formula as much as possible, we will adopt the latter definition in the subsequent discussions.**

The general case derived here places no restrictions on the relationship between $\{\bar{\omega} ;\omega_1,\dots,\omega_n\}$, meaning a perturbation at any frequency could potentially excite a response at another frequency.

But for a time-translation invariant response function, there will be certain restrictions on the form of the response function in the Frequency Domain.

Taking the most common linear response as an example, the frequency of the response must be the same as the frequency of the external field, i.e.,

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega \pm \omega_1)
\end{aligned}
$$

And for more general nonlinear responses, it can be proven that the frequency of the response is the sum of the external field frequencies, i.e.,

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega \pm \sum_{i=1}^n \omega_i)
\end{aligned}
$$

where the "$\pm$" sign depends on the definition of the response function in the Frequency Domain.

## Time Translation Symmetry

When the response function possesses time translation symmetry, it can be proven that the response function has the following properties:

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

This is because time translation symmetry ensures that the response function remains unchanged when all times are shifted by the same amount, i.e.,

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n(t + \tau;t_1+ \tau,\dots,t_n+ \tau)
\end{aligned}
$$

Thus, among the parameters $\{t;t_1,\dots,t_n\}$, only their relative values are independent. We can define:

$$
\begin{aligned}
& \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n) \\
& = \chi_n(t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ;t_n + \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots,t_n + (t_{n-1} - t_n),t_n) \\
& = \chi_n(\sum_{i=1}^{n-1}(t_{i} - t_{i+1}) + (t - t_1) ; \sum_{i=1}^{n-1}(t_{i} - t_{i+1}),\dots, (t_{n-1} - t_n),0)
\end{aligned}
$$

Now consider the physical meaning of the response function having time translation symmetry. This actually means that the system and the observables $\hat{A}, \hat{B}$ involved in the response are all time-translation invariant, but this has different meanings in different pictures.

Taking the Schrodinger Picture we are most familiar with as an example, operators not explicitly containing time is sufficient:

$$
\begin{aligned}
\hat{A}_S(t) = \hat{A},\,\hat{B}_S(t) = \hat{B}
\end{aligned}
$$

But in the Dirac/Heisenberg Picture, it manifests as:

$$
\begin{aligned}
\hat{A}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{A}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right),\,\hat{B}_H(t) = \exp \left(\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right) \hat{B}  \exp \left(-\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t\right)
\end{aligned}
$$

It can be proven that "the response function has time translation symmetry" and "the system and the observables $\hat{A}, \hat{B}$ involved in the response are all time-translation invariant" refer to the same thing. Taking the first-order response function as an example:

$$
\begin{aligned}
G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right) & = -\frac{\mathrm{i}}{\hbar} \Theta\left(t-t^{\prime}\right)  \operatorname{Tr} \left\{ \hat{\rho}_0\left[\hat{A}_H(t), \hat{B}_H\left(t^{\prime}\right)\right]\right\}
\end{aligned}
$$

Using the cyclic property of the Trace:

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

Thus $\chi_1(t;t') \equiv G_{A B}^{\mathrm{ret}}\left(t; t^{\prime}\right)$ only explicitly contains $(t-t')$.

The derivation utilizes the property that $\hat{\rho}_0 = \frac{\exp \left(-\beta \mathcal{H}_0\right)}{\operatorname{Tr}[\exp \left(-\beta \mathcal{H}_0\right)]}$ commutes with the time evolution operator $\exp \left(\pm\frac{\mathrm{i}}{\hbar} \mathcal{H}_0 t \right)$, because both are functions of $\mathcal{H}_0$.

Similarly, it can be proven that:

When the system and the observables $\hat{A}, \hat{B}$ involved in the response have time translation invariance, the response function of any order possesses time translation symmetry. This is equivalent to the response function being writable in the form $\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_1,t_1-t_2,\dots,t_{n-1} - t_n)$.

### Linear Order Susceptibility

Now let's prove that time translation invariance implies that the frequency of the response must be the same as the frequency of the external field, i.e.,

$$
\begin{aligned}
\chi_1(\omega; \omega_1) \sim \delta(\omega - \omega_1)
\end{aligned}
$$

Time translation symmetry requires:

$$
\begin{aligned}
\chi_1(t;t_1) = \chi_1^{\mathcal{T}}(t - t_1)
\end{aligned}
$$

Thus the linear response function in the Frequency Domain is:

$$
\begin{aligned}
\chi_1(\omega ;\omega_1) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1}  \chi_1(t; t_1) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i(\omega_1 - \omega) t_1} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_1) e^{-i\omega (t - t_1)}   \chi_1^{\mathcal{T}}(t - t_1) \\
& = 2 \pi \delta(\omega - \omega_1) \tilde{\chi}_1^{\mathcal{T}}(\omega) \\
& \sim \delta(\omega - \omega_1)
\end{aligned}
$$

where $\tilde{\chi}_1^{\mathcal{T}}(\omega)$ is the Fourier Transformation of ${\chi}_1^{\mathcal{T}}(t - t_1)$:

$$
\begin{aligned}
\tilde{\chi}_1^{\mathcal{T}}(\omega) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau}   \chi_1^{\mathcal{T}}(\tau)
\end{aligned}
$$

### Nonlinear Order Susceptibility

For more general nonlinear responses, it can be proven that the frequency of the response is the sum of the external field frequencies, i.e.,

$$
\begin{aligned}
\chi_n(\omega; \omega_1,\dots,\omega_n) \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

Time translation symmetry requires (note here everything is written as difference from $t_n$):

$$
\begin{aligned}
\chi_n(t;t_1,\dots,t_n) = \chi_n^{\mathcal{T}}(t-t_n,t_1-t_n,\dots,t_{n-1} - t_n)
\end{aligned}
$$

Thus the response function in Frequency Domain is:

$$
\begin{aligned}
\chi_n(\omega ;\omega_1,\dots,\omega_n) & \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} t e^{-i\omega t} \int_{- \infty}^{+ \infty} \mathrm{~d} t_1 e^{i\omega_1 t_1} ... \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{i\omega_n t_n}  \chi_n(t; t_1,\dots,t_n) \\
& = \int_{- \infty}^{+ \infty} \mathrm{~d} t_n e^{-i(\omega - \sum_{i=1}^n \omega_i) t_n} \int_{- \infty}^{+ \infty} \mathrm{~d} (t - t_n) e^{-i\omega (t - t_n)} \int_{- \infty}^{+ \infty} \mathrm{~d} (t_1 - t_n) e^{i\omega_1 (t_1 - t_n)} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} (t_{n-1} - t_n) e^{i\omega_{n-1} (t_{n-1} - t_n)}  \chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n) \\
& = 2 \pi \delta(\omega - \sum_{i=1}^n \omega_i) \tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \\
& \sim \delta(\omega - \sum_{i=1}^n \omega_i)
\end{aligned}
$$

where $\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1})$ is the Fourier Transformation of $\chi_n^{\mathcal{T}}(t - t_n,\dots,t_{n-1} - t_n)$:

$$
\begin{aligned}
\tilde{\chi}_n^{\mathcal{T}}(\omega,\omega_1,\dots,\omega_{n-1}) \equiv \int_{- \infty}^{+ \infty} \mathrm{~d} \tau e^{-i\omega \tau} \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_1 e^{i\omega_1 \tau_1} \dots \int_{- \infty}^{+ \infty} \mathrm{~d} \tau_{n-1} e^{i\omega_{n-1} \tau_{n-1}}  \chi_n^{\mathcal{T}}(\tau,\dots,\tau_{n-1})
\end{aligned}
$$

In summary, with the general Kubo Formula for second-order response, we can easily (not really) generalize the various linear responses considered before to nonlinear responses, such as calculating nonlinear conductivity, nonlinear magnetic susceptibility, nonlinear electric polarizability, etc.

## Kubo Formula in Momentum Space

For continuous media (continuous space translation symmetry) or crystals (discrete space translation symmetry), textbooks often also give the Kubo Formula in momentum space.

But this is essentially just performing a Fourier Transform on another parameter—coordinates—essentially no different from the Fourier Transform between Time Domain and Frequency Domain. Even without space translation symmetry, one can transform every coordinate parameter to obtain the most general form.

One can imagine that, similar to the response function of a system with time translation symmetry, the response function of a system with space translation symmetry will also satisfy a similar (quasi-) momentum conservation form, i.e.:

$$
\begin{aligned}
\chi_n(k; k_1,\dots,k_n) \sim \delta(k - \sum_{i=1}^n k_i)
\end{aligned}
$$

## Second Harmonic Generation & Zero Frequency Term

Next, consider a common time-dependent perturbation, a harmonic perturbation with frequency $\omega_0 > 0$:

$$
\begin{aligned}
\hat{V}_S (t) = \hat{H'} e^{-i\omega_0 t} + \hat{H'}^\dagger e^{i\omega_0 t}
\end{aligned}
$$

It can be seen that the external field contributes at frequencies $\pm \omega_0$. For a system with time translation invariance, its first-order response should also only have terms with frequencies $\pm \omega_0$.

As for the second-order response:

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \chi_2(\omega; \omega_1, \omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

If the system has time translation symmetry:

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) F(\omega_1) F(\omega_2)
\end{aligned}
$$

And the spectrum of the external field is:

$$
\begin{aligned}
F(\omega) \sim \delta(\omega \pm \omega_0)
\end{aligned}
$$

Thus the second-order response can have a second harmonic response, the so-called "2nd Harmonic Generation":

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \pm \omega_0) \sim \delta(\omega \pm 2\omega_0)
\end{aligned}
$$

It can also have a Zero Frequency Response, i.e.:

$$
\begin{aligned}
\langle \mathcal{O} \rangle_2(\omega) \sim \int d \omega_1 \int d \omega_2 \delta(\omega- \omega_1-\omega_2) \delta(\omega_1 \pm \omega_0) \delta(\omega_2 \mp \omega_0) \sim \delta(\omega)
\end{aligned}
$$

Whether it is Second Harmonic Generation or Zero Frequency Response, they are interesting topics in the nonlinear electro-optical response of semiconductors in condensed matter physics.

## Kubo Formula for Fermi Golden Rule

In fact, the transition rate (probability) of a quantum system under light excitation can also be viewed as a response of the system to external perturbations.

At this time, the observable of the system is the final state projection operator, the unperturbed density matrix is the initial state projection operator, and the external field is the time-harmonic electromagnetic field of the light wave:

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

The transition rate is:

$$
\begin{aligned}
\mathcal{I}_{i \rightarrow f} = \frac{d}{dt} \langle \hat{\mathcal{O}} \rangle
\end{aligned}
$$

We skip the derivation details for now and look directly at the second-order response of the system (it can be proven that the first-order response is 0), which will also have the second harmonic response corresponding to Second Harmonic Generation and the Zero Frequency Response.

The latter corresponds to the constant transition rate calculated by the general Fermi Golden Rule, while the former is the second harmonic response omitted in the Fermi Golden Rule mentioned in our previous section. Under the long-time average approximation, it completely corresponds to the result of the Fermi Golden Rule.

Therefore, the Fermi Golden Rule is essentially a second-order response, which can be calculated using the Nonlinear Order Kubo Formula.
