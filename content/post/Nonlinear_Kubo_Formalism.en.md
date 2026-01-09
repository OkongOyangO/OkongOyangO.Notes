+++
date = '2026-01-09T20:30:33-05:00'
draft = false
math = true
ShowToc = true
TocOpen = false
title = 'Nonlinear Kubo Formalism'
+++

# Nonlinear Kubo Formalism

The Kubo formula is the cornerstone of linear response theory, relating transport coefficients (such as conductivity) to equilibrium correlation functions. However, with the development of strong laser physics and topological optoelectronics, the description of **nonlinear response** has become increasingly important. The nonlinear Kubo formalism generalizes the linear theory to higher-order perturbations and serves as the theoretical basis for understanding phenomena such as Second Harmonic Generation (SHG) and the Bulk Photovoltaic Effect (BPVE).

## 1. Perturbative Expansion of the Density Matrix

Consider a quantum system driven by an external field, with the Hamiltonian:
$$
\begin{aligned}
H(t) = H_0 + V(t)
\end{aligned}
$$
where $H_0$ is the unperturbed Hamiltonian, and $V(t)$ is the time-dependent perturbation (e.g., the interaction between the electromagnetic field and electrons, $V(t) = e \mathbf{r} \cdot \mathbf{E}(t)$).

The dynamics of the system are described by the Liouville-von Neumann equation:
$$
\begin{aligned}
i\hbar \frac{\partial \rho(t)}{\partial t} = [H(t), \rho(t)]
\end{aligned}
$$
We expand the density matrix $\rho(t)$ in powers of the perturbation:
$$
\begin{aligned}
\rho(t) = \rho^{(0)} + \rho^{(1)}(t) + \rho^{(2)}(t) + \dots + \rho^{(n)}(t) + \dots
\end{aligned}
$$
where $\rho^{(0)}$ is the equilibrium density matrix (usually the Fermi-Dirac distribution).

## 2. Iterative Solution and Nested Commutators

In the interaction picture, we can obtain a recurrence relation for $\rho^{(n)}(t)$. The correction to the $n$-th order density matrix is determined by the $(n-1)$-th order:
$$
\begin{aligned}
\rho^{(n)}(t) = -\frac{i}{\hbar} \int_{-\infty}^{t} dt' [V(t'), \rho^{(n-1)}(t')]
\end{aligned}
$$
This leads to the famous Nested Commutator form. For the $n$-th order response, the expectation value of an observable operator $\hat{O}$ is:
$$
\begin{aligned}
\langle \hat{O} \rangle^{(n)}(t) = \text{Tr}(\hat{O} \rho^{(n)}(t))
\end{aligned}
$$
Written explicitly, this becomes:
$$
\begin{aligned}
\langle \hat{O} \rangle^{(n)}(t) = \left(-\frac{i}{\hbar}\right)^n \int_{-\infty}^{t} dt_1 \int_{-\infty}^{t_1} dt_2 \dots \int_{-\infty}^{t_{n-1}} dt_n \text{Tr}\left( \hat{O} [V(t_1), [V(t_2), \dots [V(t_n), \rho^{(0)}] \dots ]] \right)
\end{aligned}
$$
Here, the time integration satisfies the time ordering $t > t_1 > t_2 > \dots > t_n$.

## 3. Second-Order Nonlinear Response and Topological Properties

In condensed matter physics, the second-order response ($n=2$) is particularly important. The second-order optical conductivity $\sigma^{(2)}$ describes effects such as Optical Rectification and Second Harmonic Generation.

For periodic crystal systems, in momentum space, the matrix elements of the position operator $\mathbf{r}$ involve the Berry Connection. Sipe and Shkrebtii, among others, developed the band-based nonlinear response theory.

The second-order DC response (photocurrent) can be written as:
$$
\begin{aligned}
J_{a}^{(2)} = \sigma_{abc}^{(2)} E_b E_c^*
\end{aligned}
$$
In systems with Inversion Symmetry Breaking, the derivation of the nonlinear Kubo formula reveals the geometric origin of the **Shift Current**. Its expression contains the integrand:
$$
\begin{aligned}
R_{nm}^{a} = \frac{\partial \phi_{nm}}{\partial k_a} + A_{nn}^{a} - A_{mm}^{a}
\end{aligned}
$$
Here, $R$ is called the **Shift Vector**, which describes the real-space displacement of the wave packet center during the electron transition upon absorbing a photon. This directly links the nonlinear optical response to the quantum geometric properties (Berry Connection) of the wave function.

## 4. Summary

The nonlinear Kubo formalism is not just a simple perturbative extension; it provides a unified framework for treating higher-order transport processes in non-equilibrium states.
*   **Linear Order**: Corresponds to Drude conductivity, Berry Curvature (Hall Effect).
*   **Nonlinear Order**: Corresponds to Shift Current, Berry Curvature Dipole, Nonlinear Hall Effect.

Through this formalism, we can predict and understand novel nonlinear optoelectronic responses in topological materials.
