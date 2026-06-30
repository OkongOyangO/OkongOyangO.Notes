---
title: "😈Non-Hermitian Hamiltonians, Liouvillian Superoperator Spectra, and Exceptional Points"
date: 2022-07-20T10:00:00+08:00
draft: false
math: true
tags: ["Non-Hermitian", "Exceptional Points", "Liouvillian", "Lindblad Equation", "Condensed Matter"]
categories: ["Physics Notes"]
---

This note introduces two core concepts in non-Hermitian quantum physics: the Liouvillian superoperator within the Lindblad master equation formalism, and the spectral features of exceptional points (EP) unique to non-Hermitian matrices.

<!--more-->

## Lindblad Master Equation Formalism & Liouvillian Superoperator

### Lindblad Master Equation

The density matrix evolution of an open quantum system can be described by the Lindblad Master Equation (LME):

$$
    \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L} \hat{\rho}(t)=-i[\hat{H}, \hat{\rho}(t)]+\sum_{\mu} \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)
$$

$$
    \mathcal{D}\left[\hat{\Gamma}_{\mu}\right] \hat{\rho}(t)=\hat{\Gamma}_{\mu} \hat{\rho}(t) \hat{\Gamma}_{\mu}^{\dagger}-\frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2} \hat{\rho}(t)-\hat{\rho}(t) \frac{\hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu}}{2}
$$

where $\frac{1}{2}\{L_{k}^{\dagger} L_{k}, \rho\}$ describes the continuous anti-unitary part, while $L_{k} \rho L_{k}^{\dagger}$ accounts for the quantum jump terms that drive discontinuous evolution. Together, these two pieces ensure the trace-preserving property of the density matrix evolution.

The derivation of the LME can be found in H. P. Breuer's *The Theory of Open Quantum Systems* or in relevant introductory articles on Zhihu.

### Effective Non-Hermitian Hamiltonian & Quantum Trajectory Interpretation

Short-time evolution can be captured by an effective non-Hermitian Hamiltonian $H_{eff}$:

$$
    \hat{H}_{\mathrm{eff}}=\hat{H}-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2, \quad \frac{\partial \hat{\rho}(t)}{\partial t}=\mathcal{L}^{\prime} \hat{\rho}(t)=-i\left(\hat{H}_{\mathrm{eff}} \hat{\rho}(t)-\hat{\rho}(t) \hat{H}_{\mathrm{eff}}^{\dagger}\right)
$$

The non-Hermiticity of $H_{eff}$ originates from the system-environment coupling -- the dissipation term $-i \hat{\Gamma}_{\mu}^{\dagger} \hat{\Gamma}_{\mu} / 2$ endows the eigenvalues with imaginary parts, which represent the decay rates of the corresponding states.

### Liouvillian Superoperator Spectrum

The Liouvillian $\mathcal{L}$ is a superoperator that acts on the space of density matrices. Via vectorization, an $N \times N$ density matrix can be mapped to an $N^2$-dimensional vector, turning $\mathcal{L}$ into an $N^2 \times N^2$ matrix.

The Liouvillian spectrum $\{\lambda_i\}$ is generally complex. At least one steady state exists, corresponding to the eigenstate with $\lambda = 0$. Multiple steady states signal a dissipative phase transition, which is closely tied to the emergence of EPs and symmetry breaking.

The Liouvillian gap is defined as:

$$ \Delta = -\min(\operatorname{Re}(\lambda_i)) $$

and characterizes the relaxation time of the slowest decaying mode. When $\Delta \to 0$, the system exhibits critical slowing down.

## Exceptional Points

### What Are Exceptional Points?

Hermitian matrices always have real eigenvalues and their eigenvectors form a complete orthonormal basis. A key feature of non-Hermitian matrices, however, is that at certain parameter values, not only the eigenvalues but also the eigenvectors become degenerate. Such points are called **exceptional points (EPs)**.

At an EP, the matrix is no longer diagonalizable and instead reduces to a Jordan block. This is fundamentally different from the diabolic points found in Hermitian systems.

Consider a simple $2 \times 2$ non-Hermitian matrix:

$$
H = \begin{pmatrix}
\epsilon & t \\
t & -\epsilon + i\gamma
\end{pmatrix}
$$

By tuning the parameters so that the eigenvalues coincide, one arrives at an EP. Near the EP, the eigenvalues split in a square-root fashion:

$$ \Delta E \propto \sqrt{\lambda - \lambda_{EP}} $$

This stands in sharp contrast to the linear level repulsion ($\Delta E \propto |\lambda - \lambda_0|$) seen in Hermitian systems.

### Transient Dynamics Near an EP: The Damped Oscillator Analogy Across a LEP

Transient dynamics across a Liouvillian Exceptional Point (LEP) resembles the classical damped oscillator crossing from overdamped to critically damped to underdamped.

Tuning the system parameter from one side of the LEP to the other:
- On one side of the LEP: the system approaches steady state with oscillatory decay ("underdamped")
- At the LEP: critical damping
- On the other side of the LEP: oscillation-free exponential decay ("overdamped")

This behavior can be understood from the imaginary parts of the Liouvillian eigenvalues -- at the EP, the eigenvalues transition from purely real to complex.

### Chiral State Transfer Near an EP

When system parameters are varied adiabatically along a closed loop encircling an EP, the final state depends on the winding direction (clockwise vs. counterclockwise), rather than staying in the initial eigenstate. This phenomenon is called **chiral state transfer** or **asymmetric mode transfer**.

This starkly contrasts with the adiabatic theorem in Hermitian systems: in Hermitian systems, as long as the evolution is slow enough, the system remains in its instantaneous eigenstate (up to a Berry phase factor). In non-Hermitian systems, however, encircling an EP forces the system to jump to a different eigenstate.

Chiral state transfer is an active research direction in non-Hermitian topology, and has been observed in experimental platforms such as coupled waveguides and optical microcavities.

## Summary

Non-Hermitian quantum physics describes open quantum system dynamics through the Lindblad master equation, where the effective non-Hermitian Hamiltonian naturally introduces complex eigenvalues. Exceptional points (EPs) are spectral singularities unique to non-Hermitian systems, and the physics around them -- from damped oscillator transients to chiral state transfer -- has been richly realized in experiments across both classical and quantum systems.
