---
title: "😊Magnetism in Solids"
date: 2021-09-25T10:00:00+08:00
draft: false
math: true
tags: ["Magnetism", "Solid State Physics", "Paramagnetism", "Ferromagnetism", "Condensed Matter"]
categories: ["Physics Notes"]
---

The magnetism of solids is an important chapter in solid state physics. It studies how a solid (e.g., a crystal) responds to an external magnetic field $B$ through its internal magnetization $\mathcal{M} = \frac{\Sigma \mathbb{m}}{V}$ and magnetic susceptibility $\chi = \frac{\mu_0 \mathcal{M}}{B}$.

<!--more-->

## Classification of Magnetism

### Single-atom (single-ion) magnetic moment effects (small $\chi$)

Considering just one atomic (or ionic) magnetic moment and ignoring interactions between moments, the magnetic behavior splits into paramagnetism and diamagnetism. The ground state with no external field is a random tangle of moments.

+ **Paramagnetism** $\chi > 0$. Electron spin and orbital angular momentum tend to align with the external field $B$, producing paramagnetism.

+ **Diamagnetism** $\chi < 0$. Induced magnetic moments prefer to oppose $B$, giving diamagnetism.

### Multi-atom (multi-ion) effects (large and exotic $\chi$)

More dramatic magnetic behavior, like ferromagnetism, requires us to consider interactions between magnetic moments. Now the ground state is an ordered arrangement of moments — the simplest is all pointing the same way, while more complex ones include spin chirality and so on.

+ **Ferromagnetism**. The interaction between moments makes them want to line up parallel. There is a paramagnetic-ferromagnetic phase transition, described by the Curie-Weiss law:
  $T < T_c$: spontaneous magnetization, $B = 0$, $M \neq 0$, ferromagnetic state;
  $T > T_c$: $\chi = \frac{C}{T - T_c}$, paramagnetic state.

+ **Antiferromagnetism**. The interaction between moments makes them want to line up antiparallel. There is a paramagnetic-antiferromagnetic phase transition, described by the NÃ©el law:
  $T < T_c$: spontaneous antiparallel ordering;
  $T > T_c$: $\chi = \frac{C}{T + T_N}$, paramagnetic state.

+ **Ferrimagnetism**. Antiparallel ordering where the moments don't fully cancel, giving a net magnetization.

## History of Solid Magnetism and Its Quantum-Mechanical Foundation

The study of solid magnetism goes back to before quantum mechanics. Langevin explained paramagnetism using the idea of permanent dipoles, but the very notion of a permanent dipole contradicts classical mechanics; moreover, a classical system in thermal equilibrium cannot exhibit a net magnetic moment.

These contradictions were only resolved with the advent of quantum mechanics. Quantum mechanics lets the permanent-dipole model lean on intrinsic electron spin and stationary orbital angular momentum, and an analysis of ground-state (equilibrium) energies also cleanly explains induced moment effects.

### Origins of the Atomic Magnetic Moment

The atomic magnetic moment comes from three sources:

1. **Electron spin magnetic moment**. The intrinsic spin $s = 1/2$ of an electron produces a moment $\boldsymbol{\mu}_s = -g_s \mu_B \mathbf{s}$, where $g_s \approx 2$ and $\mu_B = e\hbar/2m_e$ is the Bohr magneton.

2. **Electron orbital magnetic moment**. The orbital angular momentum $\mathbf{l}$ of an electron orbiting the nucleus gives $\boldsymbol{\mu}_l = -\mu_B \mathbf{l}$.

3. **Nuclear spin magnetic moment**. The nuclear spin also creates a magnetic moment, but the nuclear magneton $\mu_N \ll \mu_B$, so it's usually negligible.

### Hund's Rules

For multi-electron atoms, the ground-state electron configuration is determined by Hund's rules:

1. **First Hund rule**: the total spin $S$ is maximized (spins are as parallel as possible).
2. **Second Hund rule**: given the first rule, the total orbital angular momentum $L$ is maximized.
3. **Third Hund rule**: once spin-orbit coupling is considered, $J = |L-S|$ when the shell is less than half-filled, and $J = L+S$ when it is more than half-filled.

## Paramagnetism and the Brillouin Function

Consider an atom with total angular momentum $J$ placed in an external magnetic field $B$. Its Hamiltonian is

$$ \hat{H} = - \boldsymbol{\mu} \cdot \mathbf{B} = g_J \mu_B \mathbf{J} \cdot \mathbf{B} $$

where $g_J$ is the LandÃ© g-factor:

$$ g_J = 1 + \frac{J(J+1) + S(S+1) - L(L+1)}{2J(J+1)} $$

The partition function is

$$ Z = \sum_{m_J=-J}^{J} e^{g_J \mu_B m_J B / k_B T} = \frac{\sinh\left[(2J+1)x/2\right]}{\sinh(x/2)} $$

with $x = g_J \mu_B B / k_B T$. From this we obtain the magnetization:

$$ M = n g_J \mu_B J B_J(x) $$

where $B_J(x)$ is the Brillouin function:

$$ B_J(x) = \frac{2J+1}{2J}\coth\left(\frac{2J+1}{2J}x\right) - \frac{1}{2J}\coth\left(\frac{x}{2J}\right) $$

In the high-temperature weak-field limit ($x \ll 1$), expanding $B_J(x) \approx \frac{J+1}{3J}x$ gives the Curie law:

$$ \chi = \frac{n \mu_0 (g_J \mu_B)^2 J(J+1)}{3k_B T} = \frac{C}{T} $$

## Ferromagnetism and Weiss Molecular Field Theory

Weiss proposed that a ferromagnet contains a "molecular field" proportional to the magnetization:

$$ \mathbf{B}_{eff} = \mathbf{B}_{ext} + \lambda \mu_0 \mathbf{M} $$

where $\lambda$ is the molecular field constant. Substituting $B_{eff}$ into the Brillouin function, the self-consistency equation becomes

$$ M = n g_J \mu_B J B_J\left(\frac{g_J \mu_B J (B_{ext} + \lambda \mu_0 M)}{k_B T}\right) $$

When $B_{ext} = 0$, a nonzero solution exists below $T < T_c$, i.e., spontaneous magnetization. The Curie temperature is given by

$$ T_c = \frac{n \lambda \mu_0 (g_J \mu_B)^2 J(J+1)}{3k_B} $$

For $T > T_c$, $\chi$ obeys the Curie-Weiss law:

$$ \chi = \frac{C}{T - T_c} $$

## Antiferromagnetism and Spin Waves

The order parameter of an antiferromagnet is the staggered magnetization $\mathbf{M}_s = \mathbf{M}_A - \mathbf{M}_B$, where $A$ and $B$ are the two sublattices. At $T = 0$, $\mathbf{M}_s$ is maximal; as the temperature rises, thermal fluctuations excite spin waves (magnons) and $\mathbf{M}_s$ decreases.

The spin-wave dispersion relation in the long-wavelength limit is

$$ \omega_k \propto k^2 \quad \text{(ferromagnet)} $$
$$ \omega_k \propto k \quad \text{(antiferromagnet)} $$

At low temperatures, the temperature dependence of the magnetization follows Bloch's $T^{3/2}$ law:

$$ M(T) = M(0) \left[1 - \alpha \left(\frac{T}{T_c}\right)^{3/2}\right] $$

## Summary

Solid magnetism spans single-ion effects (paramagnetism, diamagnetism) and collective effects (ferromagnetism, antiferromagnetism). Its theory has evolved from the classical Langevin model through the Weiss molecular field theory to a quantum-mechanical spin-wave picture. In modern magnetism research, topological spin textures (skyrmions, etc.), frustrated magnetism, and quantum spin liquids are at the frontier.
