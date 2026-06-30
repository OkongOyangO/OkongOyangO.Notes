---
title: "😌Does This Hamiltonian Have TRS? A Practical Guide to Time-Reversal Symmetry"
date: 2021-11-17T10:00:00+08:00
draft: false
math: true
tags: ["Time-Reversal Symmetry", "Topological Insulator", "Kramers Degeneracy", "Condensed Matter"]
categories: ["Physics Notes"]
---

Time-reversal symmetry is so common in TI studies that the following situation happens all the time: page one, the conclusion feels trivial; page two, you have no idea where that conclusion came from. This article systematically sorts out how time-reversal symmetry (TRS) manifests in quantum mechanics and band theory.

<!--more-->

## TRS for Spinless Particles

The time-reversal operation $\Theta$ acts as complex conjugation in spinless systems:

$$ \Theta = K $$

where $K$ is the complex conjugation operator. For a spinless Hamiltonian, TRS requires:

$$ \Theta H \Theta^{-1} = H \quad \Leftrightarrow \quad H^* = H $$

That is, all Hamiltonian matrix elements must be real. For a Bloch Hamiltonian, this means:

$$ H(-\mathbf{k}) = H^*(\mathbf{k}) $$

## TRS for Spinful Particles

For spin-$1/2$ particles, the time-reversal operator is:

$$ \Theta = -i \sigma_y K $$

where $\sigma_y$ is a Pauli matrix. A key property:

$$ \Theta^2 = -1 $$

This property leads to the famous **Kramers degeneracy**: under TRS, every eigenstate is at least two-fold degenerate.

Proof: If $|\psi\rangle$ is an eigenstate of $H$, then $\Theta|\psi\rangle$ is also an eigenstate of $H$ and is orthogonal to $|\psi\rangle$:

$$ \langle \psi | \Theta \psi \rangle = \langle \Theta^2 \psi | \Theta \psi \rangle^* = -\langle \psi | \Theta \psi \rangle^* = 0 $$

## TRS in Solid-State Band Theory

In Bloch band theory, TRS requires:

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

This gives mirror symmetry of the bands about $k=0$: $E_n(\mathbf{k}) = E_n(-\mathbf{k})$.

### Time-Reversal Invariant Momenta (TRIM)

Points in the BZ satisfying $-\mathbf{k} = \mathbf{k} + \mathbf{G}$ are called TRIM (Time-Reversal Invariant Momentum). There are 4 TRIM in a 2D square lattice and 8 in 3D. At these points:

$$ H(\Gamma_i) = \Theta H(\Gamma_i) \Theta^{-1} $$

which ensures Kramers degeneracy holds.

### Constraints on Berry Curvature in the Brillouin Zone

TRS imposes a constraint on the Berry curvature:

$$ F(-\mathbf{k}) = -F(\mathbf{k}) $$

This means the Berry curvature vanishes at TRIM (since $F(\Gamma_i) = -F(\Gamma_i)$). Consequently, a TRS-preserving system must have zero Chern number—TRS systems cannot be Chern insulators.

## How to Construct a TRS Hamiltonian

To determine whether a Hamiltonian has TRS, follow these steps:

1. **Write down the time-reversal operator**: determine $\Theta$ based on whether the system includes spin.

2. **Apply the TRS condition to the Bloch Hamiltonian**:

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

3. **Expand in terms of Pauli matrices**. For a two-band system:

$$ H(\mathbf{k}) = d_0(\mathbf{k}) \sigma_0 + \mathbf{d}(\mathbf{k}) \cdot \boldsymbol{\sigma} $$

TRS constrains the symmetry of $d_i(\mathbf{k})$. For a spinless system ($\Theta = K$):

$$ \sigma_x \sigma_0 \sigma_x = \sigma_0 = \sigma_0^* $$
$$ \sigma_x \sigma_x \sigma_x = \sigma_x = \sigma_x^* $$
$$ \sigma_x \sigma_y \sigma_x = -\sigma_y = \sigma_y^* $$
$$ \sigma_x \sigma_z \sigma_x = -\sigma_z $$

Thus $d_y(\mathbf{k})$ must be zero, while $d_x, d_z$ must be even functions.

4. **Consider other symmetries**. For example, combined $C_{2z}\mathcal{T}$ symmetry also plays an important role in non-reciprocal transport.

## TRS in Spin-Orbit Coupled Systems

In systems with spin-orbit coupling, TRS manifests as spin degeneracy of bands. Both Dresselhaus and Rashba spin-orbit coupling preserve TRS (they arise from structural inversion asymmetry and do not break TRS).

When TRS and inversion symmetry (IS) coexist, every band at every k-point is two-fold degenerate (spin degeneracy). This is because the combined $\mathcal{P}\Theta$ symmetry ($\mathcal{P}\Theta^2 = -1$) guarantees local Kramers degeneracy.

## Summary

TRS is one of the three fundamental symmetries in topological classification (alongside PHS and CS). Recognizing whether a system has TRS, and understanding the band constraints it imposes (Kramers degeneracy, odd Berry curvature, degeneracy at TRIM), is foundational for studying topological insulators and other SPT phases.
