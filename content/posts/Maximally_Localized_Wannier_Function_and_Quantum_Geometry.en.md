---
title: "🫨Maximally Localized Wannier Function & Quantum Geometry"
date: 2023-05-13T10:00:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Quantum Geometry", "Wannier Function", "Berry Phase"]
categories: ["Physics Notes"]
---

This note briefly describes the gauge selection problem of Maximally Localized Wannier Functions and discusses how Quantum Geometry limits their localization.

<!--more-->

## Gauge Variance of Wannier Function

Recall Bloch's theorem:

$$
\hat{H}\left|\psi_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\psi_{n \mathbf{k}}\right\rangle
$$

For the Bloch Hamiltonian:

$$
\hat{H}(\mathbf{k}) = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} \hat{H} e^{-i \mathbf{k} \cdot \hat{\mathbf{r}}}
$$

$$
| \psi_{n \mathbf{k}} \rangle = e^{i \mathbf{k} \cdot \hat{\mathbf{r}}} | u_{n \mathbf{k}} \rangle
$$

$$
\hat{H}(\mathbf{k}) | u_{n \mathbf{k}} \rangle = \epsilon_n(\mathbf{k}) \left|u_{n \mathbf{k}}\right\rangle
$$

For computational convenience, we sometimes use Wannier wave functions, which seem to possess localized properties, as a basis to solve for the system's eigenstates.

The relationship between the Wannier function $|\mathbf{R} n\rangle$ and the Bloch wave function $\left|\psi_{n \mathbf{k}}\right\rangle$ is:

$$
\left|\psi_{n \mathbf{k}}\right\rangle=\sum_{\mathbf{R}} e^{i \mathbf{k} \cdot \mathbf{R}}|\mathbf{R} n\rangle \Leftrightarrow |\mathbf{R} n\rangle=\frac{1}{N} \sum_{\mathbf{k}} e^{-i \mathbf{k} \cdot \mathbf{R}}\left|\psi_{n \mathbf{k}}\right\rangle
$$

It is not hard to imagine that the Bloch wave function $\left|\psi_{n \mathbf{k}}\right\rangle$ is extended in real space, whereas the Wannier function $|\mathbf{R} n\rangle$ is localized around $\mathbf{R}$.

These Wannier wave functions are not eigenstates of the system; they are merely a linear combination of Bloch wave functions that are localized in real space, and they depend on the gauge selection of the energy bands. If we add a $\mathbf{k}$-dependent phase (gauge) to the Bloch wave function, it remains an eigenstate.

$$
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|\psi_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{\psi}_{n \mathbf{k}}\right\rangle
$$

$$
\left|\tilde{u}_{n \mathbf{k}}\right\rangle=e^{i \varphi_n(\mathbf{k})}\left|u_{n \mathbf{k}}\right\rangle \ \Rightarrow\ \hat{H}(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle = \epsilon_n(\mathbf{k}) \left|\tilde{u}_{n \mathbf{k}}\right\rangle
$$

It is easy to imagine that due to the arbitrariness of the gauge selection $e^{i \varphi_n(\mathbf{k})}$, the localization of the Wannier wave function will also be affected. Thus, we have the motivation to find the gauge that makes the Wannier wave function maximally localized.

## Vanderbilt's Spread Function

Standard solid-state physics textbooks often omit how to adjust the gauge to achieve maximal localization of Wannier functions. In fact, this was not fully resolved for decades after the proposal of band theory. Relevant content can be found in Vanderbilt's 1997 PRB paper, "Maximally localized generalized Wannier functions for composite energy bands":

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847

And the 2012 RMP paper, "Maximally localized Wannier functions: Theory and applications":

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419

It is worth mentioning that numerically finding the Maximally Localized Wannier Function is very important for improving the efficiency of first-principles calculations. Relevant theories have important applications in programs like `wannier90`.

Let's briefly introduce Vanderbilt's theory. First, we need to define the degree of localization of the Wannier function. We might as well define it using the standard deviation of its real-space distribution, the so-called Spread Functional:

$$
\Omega=\left[\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\langle\mathbf{0} n|\mathbf{r}| \mathbf{0} n\rangle^2\right]=\left[\left\langle r^2\right\rangle_n-\overline{\mathbf{r}}_n^2\right]
$$

This Spread Functional depends on the gauge selection, but it can be divided into a gauge-invariant part $\Omega_{\mathrm{I}}$ and a gauge-dependent part $\tilde{\Omega}$:

$$
\Omega=\Omega_{\mathrm{I}}+\tilde{\Omega}
$$

Where,

$$
\Omega_{\mathrm{I}}=\left\langle\mathbf{0} n\left|r^2\right| \mathbf{0} n\right\rangle-\sum_{\mathbf{R},m}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

$$
\tilde{\Omega}=\sum_{\mathbf{R} m \neq 0 n}|\langle\mathbf{R} m|\mathbf{r}| \mathbf{0} n\rangle|^2
$$

In fact, the gauge-dependent part $\tilde{\Omega}$ is a non-negative value, so we always have:

$$
\Omega \geq \Omega_{\mathrm{I}}
$$

Naively, we hope to adjust the gauge so that $\tilde{\Omega}$ is as close to 0 as possible; the gauge-invariant part of the Spread Functional, $\Omega_{\mathrm{I}}$, gives the lower bound for the localization degree of the Wannier function.

Why is $\Omega_{\mathrm{I}}$ gauge invariant? Let's rewrite its form:

$$
\Omega_{\mathrm{I}} =\sum_{\alpha}\left\langle 0 n\left|r_\alpha Q r_\alpha\right| 0 n\right\rangle=\sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right]
$$

Where $P$ is the projection operator onto the considered energy band:

$$
P =\frac{1}{N} \sum_{\mathbf{k}}\left|\psi_{n \mathbf{k}}\right\rangle\langle\psi_{n \mathbf{k}}|=\sum_{\mathbf{R}}| \mathbf{R} n\rangle\langle\mathbf{R} n|
$$

The ket and bra cancel the gauge exactly, so $P$ and $Q=1-P$ are obviously gauge invariant (the band projection operator does not depend on the specific gauge selection).

## Special Case in 1D

For 1D systems, we can indeed achieve:

$$
\Omega = \Omega_{\mathrm{I}}
$$

It can be proven that the Maximally Localized Wannier Function should be the eigenstate of the position operator projected onto that band, i.e., the eigenstate of $P\hat{x}P$.

$$
\langle R n|x| 0 n\rangle=\langle R n|PxP| 0 n\rangle=\bar{x}_{0 n} \delta_{R, 0}
$$

Where $\bar{x}_{0 n} = \langle 0 n|x| 0 n\rangle$ is the center position of the Wannier function, and $P$ is the projection operator onto band $n$. The first equality holds because $| 0 n\rangle$ and $| R n\rangle$ are also superpositions of eigenstates on band $n$, so naturally:

$$
P| R n\rangle = | R n\rangle
$$

Corresponding conclusions can be generalized to higher dimensions. Taking 3D as an example, if we require $\Omega = \Omega_{\mathrm{I}}$, then the Maximally Localized Wannier Function needs to be a simultaneous eigenstate of $P\hat{x}P$, $P\hat{y}P$, and $P\hat{z}P$.

However, this is generally impossible. As a complete basis for a certain band, if the Maximally Localized Wannier Function is to be a simultaneous eigenstate of $P\hat{x}P$, $P\hat{y}P$, and $P\hat{z}P$, then these coordinate operators projected onto that band must commute pairwise. Before projection, this holds easily, but after projection, it is not necessarily true.

In other words, if the projected coordinate operators $P\hat{x}P$, $P\hat{y}P$, $P\hat{z}P$, etc., do not commute, the Spread Functional cannot be minimized to 0, nor can we have $\Omega_{min} = \Omega_{\mathrm{I}}$. But we can always take the gauge invariant $\Omega_{\mathrm{I}}$ as the lower bound for the localization degree of the Wannier function.

Since the Wannier function of a 1D system is easy to solve (finding the eigenstate of $P\hat{x}P$), it is very effective to analyze the wave packet motion of electrons in one dimension. Even if it is not a 1D problem, we can always use the partial Wannier function, i.e., the Wannier function with Fourier Transform performed only in one direction:

$$
|x,k_y, n\rangle=\frac{1}{N_x} \sum_{k_x} e^{-i k_x x}\left|\psi_{n,k_x,k_y}\right\rangle
$$

At this time, in this direction alone, the spread range (Spread Functional) of the Maximally Localized (Partial) Wannier Function can reach the minimum value $\Omega_{min} = \Omega_{\mathrm{I}}$, which can be used to analyze the electron polarization problem in one direction.

## OBC v.s. PBC

It is worth mentioning that the above situation only holds under Open Boundary Conditions (OBC). The coordinate operator is not well-defined under Periodic Boundary Conditions (PBC); in fact, the definition of the coordinate is multi-valued:

$$
x = x + mL, m \in \mathbb{Z}
$$

In PBC, we use the Unitary Operator: $z = e^{i \frac{2\pi}{L} \hat{x}}$ to define the coordinate. Modern electric polarization theory and the Topological Charge Pump theory in topological band theory were established on this basis, but that is a story for another time.

In this note, we will assume that the coordinate operator is well-defined to discuss the physical meaning. We will leave the rigorous discussion under PBC for another time.

## Relation to Quantum Geometry

In fact, the degree of localization of the Wannier Function is also related to the Quantum Geometry of the system. Regarding Quantum Geometry, you can dig up my notes:

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

Why is this so? Let's first examine the form of the Spread Functional describing the localization degree of the Wannier Function:

$$
\Omega \sim \langle r_\mu r_\nu \rangle
$$

It is roughly the correlation function of the coordinate operator, and in the momentum representation, the coordinate operator can be expressed as a momentum derivative:

$$
r_\mu \sim \partial_{k_\mu}
$$

Recall the definition of the Quantum Geometric Tensor, which exactly contains the second-order partial derivative of momentum:

$$
Q_{\mu\nu} \sim \langle \partial_{k_\mu} \partial_{k_\nu} \rangle
$$

So we can think about the connection between the two.

Going a step further, we consider the issue of gauge invariance. The gauge invariance of the electromagnetic field is reflected in the fact that the choice of different gauges does not affect the field strength. Similarly, in topological band theory, we know that the gauge selection of the Bloch wave function does not affect the Berry Curvature (so we say Berry Curvature is like a "magnetic field" in momentum space). Berry Curvature is actually an antisymmetric component of Quantum Geometry; in fact, Quantum Geometry is also an intrinsic gauge-invariant property of the system.

So, in order to more reasonably compare Quantum Geometry and the localization degree of the Wannier Function, we will compare the relationship between $Q_{\mu\nu}$ and the gauge-invariant part $\Omega_{\mathrm{I}}$ in the Spread Functional.

It is not difficult to derive:

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \operatorname{Tr}\left[P r_\alpha Q r_\alpha\right] \\
& = \sum_\alpha \sum_k \langle \psi_{nk} | r_\alpha Q r_\alpha | \psi_{nk} \rangle \\
& = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle
\end{aligned}
$$

Where,

$$
\begin{aligned}
\langle \psi_{nk_1} | r_a | \psi_{mk_2} \rangle & \equiv \langle k_1, n | r_\alpha | k_2, m \rangle \\
& = \langle k_1,n |  r_a e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}}) |u_{k_2}^m \rangle \\
& = \langle k_1,n |  -i \partial_{k_{2a}} ( e^{i k_2 \cdot \hat{r}} |u_{k_2}^m \rangle ) + i \langle u_{k_1}^n | e^{- i k_1 \cdot \hat{r}} e^{ i k_2 \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle \\
& = -i \langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) + i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle
\end{aligned}
$$

Here,

$$
\langle k_1,n | \partial_{k_{2a}} (|k_2, m \rangle ) \simeq \langle k_1,n | \left[ |k_2+\delta k_{2a}, m \rangle - |k_2-\delta k_{2a}, m \rangle \right]/2\delta k_{2a}
$$

And $|k_2 \pm \delta k_{2a}, m \rangle$ and $|k_1, 1 \rangle$ are both eigenstates of the total Hamiltonian $\hat{H}$, so the wave functions are orthogonal. However, periodic Bloch wave functions are not necessarily so, because different $k$ belong to eigenstates of different Bloch Hamiltonians and are not necessarily orthogonal.

Define $I_{nm}(k_1,k_2) \equiv i \langle u_{k_1}^n | e^{ i (k_2 - k_1) \cdot \hat{r} }| \partial_{k_{2a}} u_{k_2}^m \rangle$, calculated in the coordinate representation as follows, using the periodic property of the periodic Bloch wave function $u_{k}^n (r)$:

$$
u_{k}^n (r) = u_{k}^n (r + R),\, R = \sum_{i=1}^{d}n_i\vec{a_i}
$$

$$
\begin{aligned}
I_{nm}(k_1,k_2) & = i \int d^2 r \ u_{k_1}^n (r) e^{i(k_2 - k_1) \cdot r} \partial_{k_{2a}} u_{k_2}^m (r) \\
& = i \int d^2 r \ u_{k_1}^n (r + R) e^{i(k_2 - k_1) \cdot (r+R)} \partial_{k_{2a}} u_{k_2}^m (r+R) \\
& = i e^{i(k_2 - k_1) \cdot R} \int d^2 r \ u_{k_1}^n (r) e^{i(k_2 - k_1) \cdot r} \partial_{k_{2a}} u_{k_2}^m (r) \\
& = e^{i(k_2 - k_1) \cdot R} I_{nm}(k_1,k_2)
\end{aligned}
$$

The partial derivative can be seen as a difference:

$$\partial_{k_{2a}} u_{k_2}^\alpha (r) \simeq [u_{k_2 + \delta k_{2a}}^\alpha (r) - u_{k_2 - \delta k_{2a}}^\alpha (r)]/\delta k_{2a}$$

Since $u_{k_2 + \delta k_{2a}}^\alpha (r)$ and $u_{k_2 - \delta k_{2a}}^\alpha (r)$ are both periodic functions (invariant under translation by an integer number of primitive cells), $\partial_{k_{2a}} u_{k_2}^\alpha (r)$ is also a periodic function:

$$ \partial_{k_{2a}} u_{k_2}^\alpha (r) = \partial_{k_{2a}} u_{k_2}^\alpha (r + R) $$

Since $I_{nm}(k_1,k_2)= e^{i(k_2 - k_1) \cdot R} I_{nm}(k_1,k_2)$, and $k_1,\,k_2 \in 1BZ$, $I(k_1, k_2)\neq 0$ if and only if $k_1 = k_2$. Therefore, we only need to calculate the $k_1 = k_2$, i.e., $k = k'$ part:

$$
\begin{aligned}
I_{nm}(k_1,k_2) & = \delta_{k_1,k_2} I_{nm}(k_1,k_1) \\
& = \delta_{k_1,k_2} \ i \int d^2 r \ u_{k_1}^n (r)  \partial_{k_{1a}} u_{k_1}^m (r) \\
& = \delta_{k_1,k_2} \ i \langle u_{k_1}^n | \partial_{k_{1a}} u_{k_1}^m \rangle 
\end{aligned}
$$

Thus,

$$
\langle \psi_{nk} | r_a | \psi_{mk'} \rangle = \delta_{k,k'} \ i \langle u_{k}^n | \partial_{k_{1a}} u_{k'}^m \rangle
$$

Therefore, the gauge-invariant part of the Wannier Function's Spread Functional can be written as:

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \sum_{m \neq n, k'} \langle \psi_{nk} | r_\alpha | \psi_{mk'} \rangle \langle \psi_{mk'} |r_\alpha | \psi_{nk} \rangle\\
& = \sum_\alpha \sum_k \sum_{m \neq n} \langle \partial_{k_{\alpha}} u_{k}^n | u_{k}^m \rangle \langle  u_{k}^m | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle
\end{aligned}
$$

Note that the summation part corresponds exactly to the diagonal part of the Quantum Geometric Tensor defined on band $n$. It can also be further written as:

$$
\begin{aligned}
\Omega_{\mathrm{I}} & = \sum_\alpha \sum_k \langle \partial_{k_{\alpha}} u_{k}^n | \left( \mathbb{I} - |u_k^n \rangle \langle u_k^n | \right) | \partial_{k_{\alpha}} u_{k}^n \rangle \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \sum_{\alpha=1}^{d} \eta_{\alpha \alpha} (k) \\
& = V \int_{BZ} \frac{d^dk}{(2\pi)^d} \operatorname{tr} g(k)
\end{aligned}
$$

Since the Quantum Geometric Tensor is a Hermitian matrix, it can be divided into the Real Symmetric Fubini-Study metric part and the Imaginary Anti-symmetric Berry Curvature part:

$$
\eta_{\mu\nu}(k) = g_{\mu\nu}(k) + i \frac{\epsilon_{\mu\nu}}{2}\mathcal{B} (k)
$$

Obviously, the last equality uses the property that the diagonal of a Hermitian Matrix is real, and the Spread Functional should obviously also be a real number.

Here $\operatorname{tr}$ is the trace over dimensions $\sum_{\alpha=1}^{d}$, whereas the previous ones were traces over the Hilbert space spanned by all $k$.

From this perspective, the integral of the trace of quantum geometry over the Brillouin zone actually sets a lower limit for the localization degree of the Wannier function.

$$
\Omega \geq \Omega_I \propto \int_{BZ} d^dk \operatorname{tr} g(k)
$$

For 2D systems, we also have the inequality:

$$ \operatorname{tr}g^\alpha (k) \geq |\mathcal{B} (k)| $$

And the integral of the Berry Curvature in the 2D Brillouin zone is the Chern Number, so:

$$
\Omega \geq \Omega_I = \frac{V}{(2\pi)^d} \int_{BZ} d^dk \operatorname{tr} g(k) \geq \frac{V}{2\pi} |C|
$$

We know that for a Chern Insulator, a single band (but two are possible, so all Chern Insulator Tight-Binding Models we see are at least 2-band models, and total Chern number = 0) cannot be Wannierized, at most localized in one direction, but this inequality still reflects that the Wannier wave function of a Chern Insulator with a non-zero Chern number is more delocalized than that of a trivial Insulator.

Similarly, we can relate all momentum space geometric quantities to physical quantities related to the expectation value of real space coordinates. For example, the Berry Connection contains the first-order partial derivative of momentum, indicating that it is related to the expectation value of the coordinate operator, which corresponds to the electron polarization.

In fact, modern electron polarization theory is a product of the same period as the Berry Connection. It can be said that people only truly understood the seemingly simple phenomenon of "polarization" after figuring out the gauge field in momentum space.

## Multiband Wannierization

Tight-binding models can calculate multi-band models in addition to single bands, because considering the degrees of freedom of multi-band models gives greater gauge selection freedom (Wannier Functions can be composed of Bloch Functions from different energy bands).

The most intuitive understanding is to consider free electrons. The Bloch wave function is a plane wave (momentum eigenstate), and using infinitely many plane waves (infinitely many energy bands) can superimpose a delta function (coordinate eigenstate). There is no basis more localized than this (correspondingly, the degrees of freedom within the primitive cell are also infinite).

$$
\left|\tilde{\psi}_{n \mathbf{k}}\right\rangle =\sum_{m=1}^J U_{m n}^{(\mathbf{k})}\left|\psi_{m \mathbf{k}}\right\rangle
$$

$$
|\mathbf{R} n\rangle =\frac{V}{(2 \pi)^3} \int_{\mathrm{BZ}} d \mathbf{k} e^{-i \mathbf{k} \cdot \mathbf{R}} \sum_{m=1}^J U_{m n}^{(\mathbf{k})}\left|\psi_{m \mathbf{k}}\right\rangle
$$

## Reference

- [Maximally localized Wannier functions: Theory and applications](https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.84.1419)

- [Pseudopotential formalism for fractional Chern insulators](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.035101)

- [Maximally localized generalized Wannier functions for composite energy bands](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.56.12847)
