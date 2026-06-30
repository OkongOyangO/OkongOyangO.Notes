---
title: "🥴Anderson Localization"
date: 2022-09-05T10:00:00+08:00
draft: false
math: true
tags: ["Anderson Localization", "Disorder", "Metal-Insulator Transition", "Condensed Matter"]
categories: ["Physics Notes"]
---

In his seminal 1958 paper, P. W. Anderson proposed the phenomenon of localization in disordered systems: sufficiently strong disorder causes electron wavefunctions to transition from extended states to exponentially localized states, driving the system from a conductor to an insulator. This discovery launched over half a century of localization research and is intimately connected to the metal-insulator transition (MIT).

<!--more-->

## Basic Physical Picture of Anderson Localization

In a perfect periodic lattice, Bloch's theorem guarantees that electron wavefunctions are extended plane waves. The introduction of disorder breaks translational symmetry, subjecting electrons to multiple scattering by impurity potentials. The key question Anderson asked was: **do wavefunctions remain extended after multiple scattering?**

The answer: **it depends on the disorder strength and dimensionality**.

+ **Strong disorder**: regardless of dimension $d$, wavefunctions localize—exponential decay.
+ **Weak disorder**: in $d=1,2$, any infinitesimal disorder leads to localization; in $d=3$, disorder must exceed a critical value for localization to occur.

The localized form of the wavefunction is:

$$ |\psi(\mathbf{r})| \sim e^{-|\mathbf{r}-\mathbf{r}_0|/\xi} $$

where $\xi$ is the localization length. At the critical point of the transition, $\xi$ diverges:

$$ \xi \sim |E - E_c|^{-\nu} $$

## Anderson Tight-Binding Model

Anderson considered a tight-binding model with random on-site energies:

$$ H = -t \sum_{\langle ij\rangle} c_i^\dagger c_j + \sum_i \epsilon_i c_i^\dagger c_i $$

where $\epsilon_i$ are random on-site energies, typically taken from a uniform distribution $\epsilon_i \in [-W/2, W/2]$. The dimensionless parameter $W/t$ characterizes the disorder strength.

For three-dimensional systems, when $W/t$ exceeds a critical value $(W/t)_c$, all states at the Fermi level become localized—this is the Anderson transition.

## Scaling Theory

The scaling theory proposed by the "Gang of Four" (Abrahams, Anderson, Licciardello, Ramakrishnan, 1979) is a landmark in describing Anderson localization. The core idea is to use the dimensionless conductance $g$ as the scaling variable:

$$ g = \frac{G}{e^2/h} $$

The behavior of the scaling function $\beta(g) = d\ln g / d\ln L$:

+ **$d=1$**: $\beta(g) < 0$ for all $g$ → all states localized, no true metallic state
+ **$d=2$**: $\beta(g) \leq 0$ → no true metal-insulator transition (though debated), weak localization in the weak-disorder regime
+ **$d=3$**: $\beta(g)$ has an unstable fixed point $g_c$ → $g > g_c$ flows to a metallic state, $g < g_c$ flows to an insulating state

## Weak Localization

In the weakly disordered metallic regime ($g \gg g_c$), quantum interference effects lead to logarithmic corrections to the conductance (in $d=2$):

$$ \Delta \sigma = -\frac{e^2}{2\pi^2\hbar} \ln\left(\frac{\tau_\phi}{\tau}\right) $$

where $\tau_\phi$ is the dephasing time and $\tau$ is the elastic scattering time.

The physical origin of weak localization is that quantum interference between an electron traversing a diffusive path and its time-reversed counterpart enhances the probability of returning to the origin, thereby reducing conductance. Applying an external magnetic field breaks time-reversal symmetry and suppresses weak localization—this is the origin of **weak anti-localization**, a hallmark of spin-orbit coupled systems.

## Dimensionality and Localization

### $d=1$: Complete Localization

Any infinitesimal disorder in one-dimensional systems leads to localization. The localization length $\xi$ is simply related to the mean free path $l$: $\xi \sim l$.

### $d=2$: Predictions of Scaling Theory

Two dimensions is the marginal dimension. Weak localization gives rise to a logarithmic temperature dependence of the resistivity. Whether a true metal-insulator transition exists remains subtle (depending on spin-orbit coupling, electron-electron interactions, etc.).

### $d=3$: The Anderson Transition

Three-dimensional systems exhibit a genuine Anderson transition. A mobility edge $E_c$ separates extended states ($E > E_c$) from localized states ($E < E_c$). When the Fermi level crosses $E_c$, the system undergoes a metal-insulator transition.

## Anderson Localization and Many-Body Localization (MBL)

Anderson localization is a single-particle effect in non-interacting systems. When electron-electron interactions are included, can localization survive? The answer is: yes, under certain conditions—this is called **Many-Body Localization (MBL)**.

Key features of MBL:
+ The system does not thermalize—it violates the eigenstate thermalization hypothesis (ETH)
+ Entanglement entropy grows logarithmically rather than following an area law ($S \sim \ln t$)
+ Emergent integrability and an l-bit description

MBL is a hot topic at the intersection of condensed matter and quantum information.

## Experimental Observations

Experimental evidence for Anderson localization includes:
+ Metal-insulator transitions in doped semiconductors
+ Weak localization in 2D electron gases at low temperatures (negative magnetoresistance)
+ Anderson localization in cold atomic gases (first directly observed in 2008)
+ Classical wave localization in photonic crystals and acoustic metamaterials

## Summary

Anderson localization is a fundamental phenomenon of quantum waves in disordered media, revealing the decisive role of quantum interference effects on transport properties. Scaling theory provides a unified dimensionality-dependent description, while weak localization and many-body localization further expand the scope of this basic physical picture.
