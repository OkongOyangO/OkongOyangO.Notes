---
title: "😆How to Wiggle Like a Quantum Worm in a Twisted Potential on Chinese Valentine's Day?"
date: 2026-06-30T20:00:00+08:00
draft: false
math: true
tags: ["Twisted Potential", "Quantum Mechanics", "Curvilinear Coordinate", "Popular Science"]
categories: ["Physics Notes"]
---

This article analyzes the historical inevitability of "in-your-face couples explode," and from a quantum mechanics perspective, lays out the correct holiday posture for lonely singles (especially physics folks) on Chinese Valentine's Day.

[Note] "In-your-face couples"—a term from otaku culture referring to people with fulfilling real lives, here specifically meaning CPs. [Note on the note] CP, Charge-conjugation Parity symmetry. In 1964, CP violation was first experimentally confirmed in neutral kaon decays, earning a Nobel Prize in Physics. This reflects that "CP violation, in-your-face couples explode" is a world-recognized Nobel-level law of physics.

<!--more-->

## Twisted Coordinate and Conservation of $p_{\bar{z}}$

Consider a quantum particle in a twisted potential. A potential twisted along the z-direction can be expressed in cylindrical coordinates as:

$$V(\rho, \varphi, z) = V(\rho, \varphi - \phi(z))$$

Introduce curvilinear coordinates:

$$\begin{pmatrix} \bar{x} \\ \bar{y} \\ \bar{z} \end{pmatrix} = \begin{pmatrix} \cos\phi & \sin\phi & 0 \\ -\sin\phi & \cos\phi & 0 \\ 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix}, \quad \phi = \phi(z)$$

In these twisted coordinates, the potential becomes $\bar{z}$-independent:

$$\bar{V}(\bar{\rho}, \bar{\varphi}) = V(\bar{\rho}, \bar{\varphi})$$

## Hamiltonian in Curvilinear Coordinate

The kinetic operator in the new coordinates requires a coordinate transformation. After a tedious but straightforward derivation, the Laplacian becomes:

$$ \nabla^2 = \partial_{\bar{z}}^2 + \nabla_{\bar{\perp}}^2 + 2\dot{\phi}(\bar{z})\partial_{\bar{\varphi}}\partial_{\bar{z}} + \ddot{\phi}(\bar{z})\partial_{\bar{\varphi}} $$

The key cross term $2\dot{\phi}\partial_{\bar{\varphi}}\partial_{\bar{z}}$ comes from the off-diagonal metric of the coordinate transformation.

The corresponding Hamiltonian (mass $m=1$, $\hbar=1$):

$$ H = -\frac{1}{2}\nabla^2 + \bar{V}(\bar{\rho}, \bar{\varphi}) $$

## In Search of a Conserved Quantity

Since $\bar{V}$ is independent of $\bar{z}$, we look for a conserved quantity related to translation along $\bar{z}$. But the off-diagonal metric breaks simple conservation of $\bar{z}$-translation.

Consider the generalized momentum:

$$ p_{\bar{z}} = -i(\partial_{\bar{z}} + \dot{\phi}(\bar{z})\partial_{\bar{\varphi}}) $$

One can verify that $[H, p_{\bar{z}}] = 0$ holds when $\dot{\phi}$ is constant. This means **under a uniform twist rate, the generalized momentum $p_{\bar{z}}$ is conserved**.

$$ [H, p_{\bar{z}}] = 0 \quad \Leftrightarrow \quad \dot{\phi} = \text{const} $$

## Physical Meaning: Birth of the Quantum Worm

In twisted coordinates, the particle's "free" motion along $\bar{z}$ corresponds to helical motion in the laboratory frame. The physical meaning of the conserved quantity $p_{\bar{z}}$ is: the generalized translational momentum of the particle along the helical pipe is conserved.

This is the scientific essence of the "quantum worm"—in a twisted potential, quantum particles naturally propagate along helical paths, like a quantum worm wiggling on a quantum bed!

$$
\Psi(\bar{\rho}, \bar{\varphi}, \bar{z}, t) = \psi_n(\bar{\rho}, \bar{\varphi}) e^{i(p_{\bar{z}}\bar{z} - Et)}
$$

The wave function separates in helical coordinates into a transverse mode and a plane wave along the helical direction—this is precisely the quantum mechanical description of particle propagation in a helical waveguide.

## Conclusion

On this Chinese Valentine's Day, physics folks should:
1. Solve the Schrodinger equation in a twisted potential
2. Verify the conservation of the generalized momentum $p_{\bar{z}}$
3. Discover the "quantum worm" state—quantum eigenstates propagating along helices
4. Deeply understand the physical mechanism by which CP violation causes "in-your-face couples explode"

Wishing everyone a fulfilling and meaningful Chinese Valentine's night.
