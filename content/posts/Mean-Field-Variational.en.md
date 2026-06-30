---
title: "😤Mean Field Approximation & Variational Method: Can Hartree, Fock, and BCS Be Mixed 1:1:1?"
date: 2026-06-30T17:00:00+08:00
draft: false
math: true
tags: ["Mean Field Theory", "Hartree-Fock", "BCS", "Variational Method", "Condensed Matter"]
categories: ["Physics Notes"]
---

This article aims to introduce the mean-field approximation while explaining its variational essence. Hartree, Fock, and BCS—these three mean-field approximations may seem like mutually incompatible decoupling schemes, but by recognizing the variational nature of the mean-field approximation, we find that they can indeed be mixed 1:1:1.

<!--more-->

## Core Idea of the Mean-Field Approximation

The mean-field approximation is a fundamental tool for dealing with many-body interaction problems. Its core idea is to replace one operator in a two-body interaction term with its average value, thereby reducing the interaction problem to a single-particle one:

$$ c_1^\dagger c_2^\dagger c_3 c_4 \approx \langle c_1^\dagger c_4 \rangle c_2^\dagger c_3 + \langle c_2^\dagger c_3 \rangle c_1^\dagger c_4 - \langle c_1^\dagger c_4 \rangle \langle c_2^\dagger c_3 \rangle $$

This is essentially approximating second-order quantum fluctuations by products of first-order fluctuations, neglecting fluctuations of second order and above.

## The Variational Perspective

The mean-field approximation can be rigorously understood from a variational standpoint. Consider a trial Hartree-Fock state (a Slater determinant):

$$ |\Phi_{HF}\rangle = \prod_i c_i^\dagger |0\rangle $$

Its energy expectation $\langle \Phi_{HF} | H | \Phi_{HF} \rangle$ provides an upper bound on the true ground state energy. Through variation:

$$ \frac{\delta \langle H \rangle}{\delta |\Phi_{HF}\rangle} = 0 $$

we obtain the Hartree-Fock equations. The key point is: **any approximation based on the variational principle (Hartree, Fock, BCS) can be treated uniformly within the same variational framework**.

## Hartree Term: Direct Interaction

The Hartree term comes from density-density direct interaction (direct term / Hartree term):

$$ \hat{H}_{Hartree} = \sum_{ij} U_{ij} \langle c_i^\dagger c_i \rangle c_j^\dagger c_j $$

where $U_{ij}$ is the Coulomb interaction matrix element. This term captures the classical electrostatic energy and contributes the most to the total energy.

## Fock Term: Exchange Interaction

The Fock term comes from the exchange interaction (exchange term):

$$ \hat{H}_{Fock} = -\sum_{ij} J_{ij} \langle c_i^\dagger c_j \rangle c_j^\dagger c_i $$

where $J_{ij}$ is the exchange integral. The minus sign arises from the anticommutation relations of fermions. The Fock term is a purely quantum effect with no classical analog.

In real space, the exchange interaction tends to keep electrons with parallel spins apart from each other, reducing the Coulomb repulsion energy.

## BCS Term: Pairing Interaction

The BCS mean field introduces an anomalous average:

$$ \Delta_{ij} = \langle c_{i\downarrow} c_{j\uparrow} \rangle \neq 0 $$

The corresponding BCS Hamiltonian is:

$$ \hat{H}_{BCS} = \sum_{ij} \Delta_{ij} c_{i\uparrow}^\dagger c_{j\downarrow}^\dagger + h.c. $$

The BCS ground state is a coherent state that does not conserve particle number (the vacuum after a Bogoliubov transformation), and can be written uniformly as:

$$ |\Phi_{BCS}\rangle = \prod_k (u_k + v_k c_{k\uparrow}^\dagger c_{-k\downarrow}^\dagger) |0\rangle $$

where $|u_k|^2 + |v_k|^2 = 1$.

## The Possibility of Mixing All Three

Starting from the variational principle, we can treat the three decoupling schemes—Hartree, Fock, and BCS—within a single variational wavefunction. Specifically, take the variational wavefunction as:

$$ |\Phi\rangle = \mathcal{U}_{BCS} \mathcal{U}_{HF} |0\rangle $$

where $\mathcal{U}_{HF}$ is the unitary transformation that generates the Hartree-Fock ground state (Slater determinant), and $\mathcal{U}_{BCS}$ is the Bogoliubov transformation.

Key conclusion: **there is no contradiction between the three decouplings**, because the variational principle guarantees that the energy decreases monotonically with additional parameters. Each additional decoupling scheme expands the variational parameter space, yielding a lower (or at least not higher) ground state energy.

In practical numerical calculations, the Hartree-Fock-Bogoliubov (HFB) method is precisely the unified framework combining all three. It is widely used in nuclear physics, ultracold atomic gases, and superconductivity theory.

## Concrete Steps

Take the Fermi-Hubbard model as an example:

$$ H = -t \sum_{\langle ij\rangle, \sigma} c_{i\sigma}^\dagger c_{j\sigma} + U \sum_i n_{i\uparrow} n_{i\downarrow} $$

Perform a full decoupling of the interaction term:

$$
n_{i\uparrow} n_{i\downarrow} \approx 
\langle n_{i\uparrow} \rangle n_{i\downarrow} + n_{i\uparrow} \langle n_{i\downarrow} \rangle - \langle n_{i\uparrow} \rangle \langle n_{i\downarrow} \rangle \quad (\text{Hartree})
$$
$$
- \langle c_{i\uparrow}^\dagger c_{i\downarrow} \rangle c_{i\downarrow}^\dagger c_{i\uparrow} - c_{i\uparrow}^\dagger c_{i\downarrow} \langle c_{i\downarrow}^\dagger c_{i\uparrow} \rangle + \langle c_{i\uparrow}^\dagger c_{i\downarrow} \rangle \langle c_{i\downarrow}^\dagger c_{i\uparrow} \rangle \quad (\text{Fock})
$$
$$
+ \langle c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \rangle c_{i\downarrow} c_{i\uparrow} + c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \langle c_{i\downarrow} c_{i\uparrow} \rangle - \langle c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \rangle \langle c_{i\downarrow} c_{i\uparrow} \rangle \quad (\text{BCS})
$$

These order parameters can be solved self-consistently in numerics.

## Summary

The variational essence of the mean-field approximation reveals the unity of the three decoupling schemes—Hartree, Fock, and BCS. From the variational perspective, they can be freely mixed: each additional decoupling adds a variational parameter, always yielding a more accurate (or at least no worse) estimate of the ground state energy.
