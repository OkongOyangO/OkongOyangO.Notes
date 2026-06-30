---
title: "🫠Twisted Bilayer Graphene Flat Bands & Moiré Physics: Deriving the Magic Angle"
date: 2026-06-30T19:00:00+08:00
draft: false
math: true
tags: ["Twisted Bilayer Graphene", "Moire Physics", "Magic Angle", "BM Continuum Model", "Flat Band"]
categories: ["Physics Notes"]
---

In 2018, Cao Yuan dropped a Nature paper on us gifting the world Twisted Bilayer Graphene (TBG). This article reviews the BM continuum model for TBG, analyzes the physics of flat band formation, and theoretically derives the magic angle condition $\theta \approx 1.1^\circ$.

<!--more-->

## Why Twistronics?

The tunability of moiré systems and the strong-correlation physics emerging from their flat bands have made them a hot topic in condensed matter physics in recent years. The 2011 paper "Moiré bands in twisted double-layer graphene" by Rafi Bistritzer and Allan H. MacDonald (the BM continuum model) accurately predicted the existence of the magic angle.

https://www.pnas.org/doi/10.1073/pnas.1108174108

On the theory side, Bernevig et al. performed exhaustive analytical and computational analyses of the BM model—covering accuracy, symmetry, single-particle and many-body properties—resulting in the 200-page "TBG Hexalogy." Experimentally, twisted TMD systems and others have been realized one after another.

### Why Flat Bands Matter

The band width $W$ reflects the single-particle kinetic energy. A flat band means:

$$ U \gg W $$

where $U \sim e^2/a_M$ is the characteristic scale of electron-electron interactions, and $a_M$ is the moiré lattice constant. In flat band systems, the kinetic energy is nearly frozen and interactions dominate—strong correlation physics emerges.

## The BM Continuum Model

### Dirac Cone of Monolayer Graphene

The low-energy effective model for monolayer graphene is:

$$ H_{SLG}(\mathbf{k}) = \hbar v_F \mathbf{k} \cdot \boldsymbol{\sigma} $$

producing a linearly dispersing Dirac cone near the K point. Bilayer graphene consists of two stacked layers coupled by interlayer tunneling.

### Moiré Superlattice from Twisting

Rotating the top layer by a small angle $\theta$ rotates the Brillouin zones of the two layers relative to each other:

$$ \mathbf{K}_t = R(\theta/2) \mathbf{K}, \quad \mathbf{K}_b = R(-\theta/2) \mathbf{K} $$

The moiré superlattice reciprocal vectors are:

$$ \mathbf{G}_i^M = \mathbf{G}_i^{(t)} - \mathbf{G}_i^{(b)} $$

The moiré lattice constant is:

$$ a_M = \frac{a}{2\sin(\theta/2)} \approx \frac{a}{\theta} $$

At $\theta = 1.1^\circ$, $a_M \approx 13$ nm—about 50 times the graphene unit cell.

### Matrix Structure of the BM Model

The BM continuum model is an infinite-dimensional matrix in momentum space, with the basis being copies of each layer's Dirac cone shifted by moiré reciprocal vectors $\mathbf{G}_i^M$. For low-energy physics, keeping only the lowest few moiré reciprocal vectors gives convergent results.

Monolayer Hamiltonian matrix elements:

$$ [H_{SLG}]_{\mathbf{G},\mathbf{G}'} = \hbar v_F (\mathbf{k} + \mathbf{G}) \cdot \boldsymbol{\sigma} \delta_{\mathbf{G},\mathbf{G}'} $$

Interlayer coupling (tunneling):

$$ T_{\mathbf{G}} = \begin{pmatrix} w_0 & w_1 e^{-i\psi} \\ w_1 e^{i\psi} & w_0 \end{pmatrix} $$

where $w_0$ is the AA stacking interlayer coupling and $w_1$ is the AB stacking interlayer coupling.

### The Tripod Model and the Magic Angle

The simplest convergent truncation is the Tripod model—keep the K_M Dirac cone plus the three nearest moiré reciprocal vectors. This yields an $8\times 8$ effective Hamiltonian.

In the chiral limit ($w_0 = 0$), the BM model has particle-hole symmetry, and flat bands appear exactly at the magic angle. The magic angle condition is:

$$ \alpha = \frac{w_1}{\hbar v_F k_\theta} = \alpha_c \approx 0.586 $$

where $k_\theta = 2K\sin(\theta/2)$. This gives:

$$ \theta \approx \frac{3w_1}{\hbar v_F K} \approx 1.05^\circ $$

### Renormalized Fermi Velocity

The central prediction of the BM model is: as the twist angle decreases, the Dirac cone Fermi velocity is renormalized by interlayer coupling:

$$ v_F^* = v_F \frac{1 - 3\alpha^2}{1 + 3\alpha^2} $$

When $\alpha = 1/\sqrt{3}$, $v_F^* = 0$—this signals the magic angle. A vanishing renormalized Fermi velocity means the Dirac dispersion flattens into a flat band.

### Topological Properties

The magic-angle TBG flat bands have nontrivial topology. The total Chern number of the two flat bands in each valley is zero, but each individual flat band can be reduced to $C = \pm 1$. There is a formal correspondence between flat bands and the lowest Landau level—the "vortexability" criterion unifies the geometric conditions for ideal FCI flat bands.

## Symmetries of the Continuum Model

The BM model has a rich symmetry structure:
- $C_{3z}$: threefold rotation symmetry
- $C_{2z}\mathcal{T}$: spinless time reversal
- Particle-hole symmetry (in the chiral limit)
- $U(1)$ valley conservation (at small angles)

Outside the chiral limit ($w_0 \neq 0$), particle-hole symmetry is broken, but the flat bands remain stable, suggesting a topological protection mechanism at work.

## Summary

The BM continuum model of twisted bilayer graphene successfully predicted the emergence of magic-angle flat bands. The physical essence is the renormalization of the Dirac Fermi velocity by interlayer coupling. The moiré superlattice reduces a micron-scale complex system to an effective low-energy model, laying the foundation for understanding strong-correlation phenomena in moiré systems (superconductivity, correlated insulating states, etc.).
