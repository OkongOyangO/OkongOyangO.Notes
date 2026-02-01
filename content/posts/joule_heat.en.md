---
title: "🔥Fermi Golden Rule? Just Joule Heat!"
date: 2023-03-07T22:30:00-05:00
draft: false
math: true
tags: ["Quantum Mechanics", "Joule Heat"]
categories: ["Physics Notes"]
---

This article aims to clarify the consistency between Fermi's Golden Rule and Joule Heat.

<!--more-->

## Introduction

Fermi's Golden Rule can calculate the system's absorption of electromagnetic fields, while the Kubo Formula can calculate the current response, and the Joule heat formula can also calculate the absorption of electromagnetic fields.

The former seems to calculate entirely from the perspective of quantum transitions, while the latter seems to calculate entirely from the perspective of Joule heat. However, both are essentially applications of time-dependent perturbation theory in quantum mechanics. We touched upon this in the previous two articles, but did not elaborate on their consistency. Interested readers can visit:

https://zhuanlan.zhihu.com/p/611688122

https://zhuanlan.zhihu.com/p/611996682

It can be proven that Fermi's Golden Rule corresponds to the rate of change of the second-order response of the Hamiltonian $H_0$ in the Kubo Formula, $\frac{d }{dt}\langle H_0 \rangle^{(2)}$, and this second-order response rate can be expressed as the inner product of the linear current response and the external electric field $\langle \hat{\mathbf{J}} \rangle^{(1)} \cdot \mathbf{E}$.

## Fermi Golden Rule

Fermi's Golden Rule aims to calculate the transition rate of a quantum system from an initial state $|i\rangle$ to a final state $|f\rangle$ (both eigenstates of $H_0$) under a time-harmonic external field perturbation. In previous articles on Fermi's Golden Rule, we re-derived it using the Dirac Picture to better facilitate comparison with the Kubo Formula.

The equation of motion for the state in the Dirac picture:

$$
\begin{aligned}
i \hbar \partial_t |\psi(t) \rangle_D = \hat{V}_D(t) |\psi(t) \rangle_D
\end{aligned}
$$

By integrating the equation of motion and iterating, we can obtain the perturbative expansion form of the state evolution in the Dirac picture. Assuming the system is in the initial state $|i\rangle$ at $t = t_0$:

$$
\begin{aligned}
| \psi (t) \rangle_D & = |i\rangle + (-i/\hbar) \int_{t_0}^{t}dt_1 \hat{V}_D(t_1)|i\rangle + (-i/\hbar)^2 \int_{t_0}^{t}dt_1 \int_{t_0}^{\mathbf{t_1}}dt_2  \hat{V}_D(t_1) \hat{V}_D(t_2)|i\rangle + \dots \\
& = | \psi^{(0)} \rangle + | \psi^{(1)}\rangle + | \psi^{(2)}\rangle + \dots
\end{aligned}
$$

The probability of being in state $|f\rangle$ at time $t$ can also be expanded perturbatively:

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

The derivation of the Kubo Formula is also completed in the interaction (Dirac) picture, but it calculates the evolution of the system's density matrix rather than the wave function.

The equation of motion for the density matrix in the interaction (Dirac) picture:

$$
\begin{aligned}
\frac{d}{dt} \hat{\rho}_D(t) = - \frac{i}{\hbar} [ \hat{\rho}_D(t) , \hat{V}_D(t) ]
\end{aligned}
$$

After integration and repeated iteration, we can obtain the expansion of the density matrix:

$$
\begin{aligned}
\hat{\rho}_D(t) & = \hat{\rho}_0 + \sum_{n = 1}^{\infty} (-\frac{\mathrm{i}}{\hbar})^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n [\hat{V}_D(t_1),[\dots[\hat{V}_D(t_n),\hat{\rho}_0]\dots] ]\\
& = \hat{\rho}^{(0)} + \sum_{i=1}^{\infty} \hat{\rho}^{(i)}
\end{aligned}
$$

For a pure state density matrix with initial state $| i \rangle$, it is easy to see that the perturbative expansion of the density matrix is consistent with that of the wave function, as both are time-dependent perturbation theories in quantum mechanics.

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

To find the probability of the state $|f\rangle$, using the language of the density matrix (Kubo Formula), we treat the projection operator of the state $|f\rangle$ as the observable:

$$
\begin{aligned}
\hat{\mathcal{O}} = | f \rangle \langle f |
\end{aligned}
$$

Then the probability of the state $|f\rangle$ is:

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

It can be seen that Fermi's Golden Rule and the Kubo Formula are the same thing when calculating the final state probability. The density matrix can also be generalized to mixed states, thereby calculating the final state probability starting from an initial state with a probability distribution.

Let's focus on the pure state density matrix first. Notice that the zero-order expansion term of the wave function is:

$$
\begin{aligned}
| \psi^{(0)} = | i \rangle
\end{aligned}
$$

Therefore, the zero-order and first-order expansion terms of the final state probability are both zero. Thus, the lowest-order response of the final state probability comes from the second-order term, so we say:

**Fermi's Golden Rule is consistent with the second-order response of the final state probability.**

## Absorption Rate

When calculating the system's energy absorption rate using Fermi's Golden Rule, we calculate:

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2 
\end{aligned}
$$

Where $E_{i,f}$ are the energies of the initial and final states $|i\rangle,\,|f\rangle$. It is not hard to understand that the rate of energy change is the transition rate multiplied by the change in energy, summed over all possible transitions.

Extending to the language of the Kubo Formula, the energy absorption rate is actually the rate of change of the expectation value of the unperturbed Hamiltonian $\hat{H}_0$:

$$
\begin{aligned}
P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

This looks intuitive, and it is not hard to prove it is the same thing as Fermi Golden Rule.

$$
\begin{aligned}
P & = (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle|^2 \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}(E_f - E_i) | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f}E_f | f \rangle \langle f |\right) | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \left( \sum_{f} | f \rangle \langle f |\right) | \psi (t) \rangle \right\} \\
& = \frac{d}{dt} \left\{ \langle \psi (t) | \hat{H}_0 | \psi (t) \rangle \right\} - E_i \frac{d}{dt} \left\{ \langle \psi (t) | \mathbb{I} | \psi (t) \rangle \right\} \\
& = \frac{d}{dt}\langle \hat{H}_0 \rangle - 0
\end{aligned}
$$

This is the result for pure states. Mixed states are just superpositions of results according to probability, which can be imagined to hold true as well.

In this way, we have unified and extended the language of transition rates and energy absorption rates to the Kubo Formula. It is worth mentioning that, similar to the probability of the $|f\rangle$ state, the lowest-order non-zero response of $\langle \hat{H}_0 \rangle$ also starts from the second order.

## Joule Heat = Energy Absorption

Next, we prove the consistency of Joule heat and energy absorption rate in the Kubo Formula.

Joule heat is defined as the inner product of current response and external electric field $\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$.

For electric field perturbation (we first consider a spatially uniform time-varying electric field), the perturbation Hamiltonian is:

$$
\begin{aligned}
\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t) = -(-e) \hat{\mathbf{r}} \cdot \mathbf{E}(t)
\end{aligned}
$$

The $n$-th order perturbation of the current response $\langle \hat{\mathbf{J}} \rangle (t)$:

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \propto \mathcal{O}(|\mathbf{E}|^n) \propto \mathcal{O}(V^n)
\end{aligned}
$$

The corresponding $n+1$-th order perturbation of Joule heat $\langle \hat{\mathbf{J}} \rangle (t) \cdot \mathbf{E}(t)$:

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(n)} (t) \cdot \mathbf{E}(t) \propto {O}(|\mathbf{E}|^{n+1}) \propto \mathcal{O}(V^{n+1})
\end{aligned}
$$

Thus, the Joule heat of the linear (first-order) current response and the second-order response of the energy change rate are consistent in terms of the order of perturbation expansion.

Our goal is to prove that **the Joule heat of the linear (first-order) current response and the second-order response of the energy change rate** are strictly consistent in expression.

## Current Response

Here we define "current" as the rate of change of electric polarization, i.e., the volume integral of current density:

$$
\begin{aligned}
\hat{\mathbf{J}} \equiv \iiint dV \hat{\mathbf{j}} \equiv \frac{d}{dt} \hat{\mathbf{P}}
\end{aligned}
$$

In the Dirac Picture, the relationship between the current operator and the electric polarization operator is:

$$
\begin{aligned}
\hat{\mathbf{J}}_D = \frac{d}{dt} \hat{\mathbf{P}}_D = (- \frac{i}{\hbar}) [ \hat{\mathbf{P}}_D, \hat{H}_0 ]
\end{aligned}
$$

Thus, the first-order current response of the perturbation $\hat{V}_S(t) = - \hat{\mathbf{P}} \cdot \mathbf{E}(t)$ is:

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D, \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} 
\end{aligned}
$$

Thus, the second-order Joule heat corresponding to the first-order current response is:

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar}) \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [\hat{\mathbf{J}}_D(t) \cdot \mathbf{E} (t) , \hat{V}_D(t_1)] \right\}  \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{\mathbf{P}}_D \cdot \mathbf{E} (t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

And $\hat{\mathbf{P}}_D \cdot \mathbf{E} (t)$ is exactly the expression for the perturbation $-\hat{V}_D(t)$. Specifically:

$$
\begin{aligned}
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ -\hat{V}_D(t) , \hat{H}_0 ] , \hat{V}_D(t_1)] \right\} \\
& = (- \frac{i}{\hbar})^2 \int_{-\infty}^{t} dt_1 \operatorname{Tr} \left\{ \hat{\rho}_0 [ [ \hat{H}_0, \hat{V}_D(t) ] , \hat{V}_D(t_1)] \right\}
\end{aligned}
$$

Seeing the commutator of two $\hat{V}_D$s, it is easy to see that this is basically the rate of change of the second-order response of $\langle \hat{H}_0 \rangle$. One time integral is missing because the derivative with respect to time was taken. Specifically:

$$
\begin{aligned}
\langle \hat{H}_0 \rangle^{(2)} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[{\hat{H}_0}_D(t), \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
& = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^t \mathrm{~d} t_1 \int_{-\infty}^{t_1} \mathrm{~d} t_2  \operatorname{Tr} \left\{\rho_0\left[ \left[\hat{H}_0, \hat{V}_{D}\left(t_1\right)\right],\hat{V}_{D}\left(t_2\right)\right]\right\} \\
\end{aligned}
$$

Here we used the property that ${\hat{H}_0}$ is itself in the Dirac Picture, and the property that ${\hat{H}_0}_D(t)$ does not explicitly contain time (time translation symmetry):

$$
\begin{aligned}
{\hat{H}_0}_D(t) = e^{ \frac{i}{\hbar}\hat{H}_0 t} {\hat{H}_0} e^{- \frac{i}{\hbar}\hat{H}_0 t} = \hat{H}_0
\end{aligned}
$$

At this point, the dependence of the second-order response of $\langle \hat{H}_0 \rangle$ on time is only in the upper limit of the first time integral. Therefore, its rate of change has one less time integral (and changes the integration variable $t_1$ to $t$), and is completely consistent with the Joule heat expression for the first-order current response:

$$
\begin{aligned}
\frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} &= (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\} \\
\langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) & = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\} \\
\Rightarrow P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} & = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t)
\end{aligned}
$$

It is not difficult to verify that higher-order current responses and energy change rates also correspond one-to-one.

Thus, we have proved the consistency of the energy change rate and the current response Joule heat formula.

## Summary

In summary, we have proved the consistency of Fermi's Golden Rule and the Joule heat formula in calculating the absorption of electromagnetic waves by a quantum system.

First, we proved the consistency between the energy absorption rate calculated by Fermi's Golden Rule and the energy response change rate:

$$
\begin{aligned}
\underbrace{P = \sum_{f} (E_f - E_i) \frac{d}{dt} |\langle f | \psi (t) \rangle_D|^2}_{\text{Fermi Golden Rule}} \ \Leftrightarrow \ P = \frac{dE_{system}}{dt} = \frac{d}{dt}\langle \hat{H}_0 \rangle
\end{aligned}
$$

Afterwards, we proved the consistency between the Joule heat formula using current response multiplied by electric field and the energy response change rate:

$$
\begin{aligned}
& \underbrace{P = \langle \hat{\mathbf{J}} \rangle^{(1)} (t) \cdot \mathbf{E} (t) = (-\frac{\mathrm{i}}{\hbar})^2 \int_{-\infty}^{t} \mathrm{~d} t_1 \operatorname{Tr} \left\{ \hat{\rho}_0 \left[ \left[ \hat{H}_0, \hat{V}_D(t) \right] , \hat{V}_D(t_1) \right] \right\}}_{\text{Joule Heat}} \\
\Leftrightarrow \  &P = \frac{d}{dt} \langle \hat{H}_0 \rangle^{(2)} = (-\frac{\mathrm{i}}{\hbar})^2  \int_{-\infty}^{t} \mathrm{~d} t_2  \operatorname{Tr} \left\{\hat{\rho}_0\left[ \left[\hat{H}_0, \hat{V}_{D}(t)\right],\hat{V}_{D}(t_2)\right]\right\}
\end{aligned}
$$

Therefore, the Joule heat formula of current response multiplied by electric field, and Fermi's Golden Rule of quantum transition rate multiplied by energy change, are essentially both energy response rates.

Thus, we can say that the seemingly macroscopic "Joule Heat" and the seemingly microscopic "Fermi Golden Rule" are the same thing.
