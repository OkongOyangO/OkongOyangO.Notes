---
title: "😬KT Transition: 2D XY Model, Topological Vortices, and Quasi-Long-Range Order"
date: 2026-06-30T15:00:00+08:00
draft: false
math: true
tags: ["KT Transition", "XY Model", "Topological Defect", "Vortex", "Condensed Matter"]
categories: ["Physics Notes"]
---

The KT transition (Kosterlitz-Thouless Transition) is a unique topological phase transition in two-dimensional systems. Unlike conventional phase transitions, it is not driven by spontaneous symmetry breaking, but by the binding-unbinding of topological defects—vortices. Starting from the 2D XY model, this article explains the basic principles of the KT transition.

<!--more-->

## Principles of the KT Transition

### The 2D XY Model

In the 2D XY model, each lattice site is assigned a two-dimensional spin $S_i=(\cos \theta_i,\sin \theta_i)$. The action on a square lattice is:

$$S[\theta]=-J\sum_{\braket{ij}}S_i \cdot S_j=-J\sum_{\braket{ij}}\cos(\theta_i-\theta_j)$$

Below we compute the correlation functions at high and low temperatures, respectively.

**High temperature** ($J\ll 1$): Expand the partition function in $J$:

$$
Z=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)e^{-S[\theta]}=\int_0^{2\pi}\left(\prod_i \frac{\mathrm{d}\theta_i}{2\pi}\right)\prod_{\braket{ij}}\left[1+J\cos(\theta_i-\theta_j)+O(J^2)\right]
$$

The correlation function $\braket{S_0\cdot S_x}=\braket{\cos(\theta_0-\theta_x)}\sim e^{-f(J)|x|}$, i.e., short-range order.

**Low temperature** ($J\gg 1$): $\theta$ varies slowly, so we can take the continuum approximation:

$$S[\theta]\rightarrow \frac{J}{2}\int \mathrm{d}^2 x\left[\nabla\theta(x)\right]^2$$

The correlation function becomes $\braket{S_0\cdot S_x}\sim x^{-g(J)}$, i.e., quasi-long-range order (algebraic order).

Thus the 2D XY model exhibits a finite-temperature phase transition from short-range to quasi-long-range order. This transition cannot be described by conventional Landau theory—it is driven by the condensation of topological vortices.

## Vortex Excitations and Their Condensation

### Topological Defects and Vortices

Consider a continuous field $\vec{u}(r)=\nabla \theta(r)$. Due to the $U(1)$ structure of $\theta$ ($\theta \equiv \theta + 2n\pi$), the loop integral gives:

$$\oint \vec{u}\cdot \vec{\mathrm{d}l}=2n\pi \quad n\in \mathbb{Z}$$

This result is discrete and invariant under continuous deformations of the path. For a trivial state (constant $\theta$), the loop integral is zero. Once a topological defect is introduced, $\nabla\theta$ becomes ill-defined at the defect site:

$$\nabla \times \vec{u}(\vec{r})=2n\pi \delta^2(\vec{r}-\vec{r_0})\hat{e}_z$$

A vortex carries a topological charge $n$, and its velocity field is:

$$\vec{v}(\vec{r};\vec{r}_0,n)= \frac{n}{|\vec{r}-\vec{r}_0|}\left(\hat{e}_z\times \frac{\vec{r}-\vec{r}_0}{|\vec{r}-\vec{r}_0|}\right)$$

### Free Energy of a Vortex

Consider a vortex located at the origin with charge $n=1$:

$$S_{\text{vor}}=S_{\text{core}}+\frac{J}{2}\int_0^{2\pi}\mathrm{d}\psi \int_a^L \rho\mathrm{d}\rho \,\vec{u}^2(\rho,\psi)=S_{\text{core}}+\pi J \ln\left(\frac{L}{a}\right)$$

Partition function:

$$Z_{\text{vor}}/Z_0\approx \left(\frac{L}{a}\right)^2 e^{-S_{\text{core}}-\pi J\ln(L/a)}=\exp(-S_{\text{core}}+(2-\pi J)\ln(L/a))$$

Free energy of a vortex:

$$F_{\text{vor}}\sim S_{\text{core}}+(\pi J-2)\ln(L/a)$$

When $\pi J > 2$, the coefficient of $\ln L$ is positive, the free energy of a single vortex diverges—vortices are confined. When $\pi J < 2$, the vortex free energy is negative—vortices can appear spontaneously. The critical point is at $\pi J = 2$, i.e., $J_c = 2/\pi$.

### Vortex-Vortex Interactions

The interaction energy between two vortices with charges $n_1, n_2$ is:

$$V_{int} = -2\pi J n_1 n_2 \ln\left(\frac{|\vec{r}_1-\vec{r}_2|}{a}\right)$$

Oppositely charged vortices attract (logarithmic potential), while like-charged vortices repel. At low temperatures, positive and negative vortices form bound pairs and the system maintains quasi-long-range order; at high temperatures, vortex pairs unbind into a vortex plasma and the system becomes disordered.

## Experimental Verification of the KT Transition: 2D Superconducting Thin Films

Experiments using homogeneous thin films of $\mathrm{Hg}-\mathrm{Xe}$ alloy with high sheet resistance have validated the KT transition.

The binding-unbinding of vortex-antivortex pairs in 2D superconductors directly corresponds to the KT transition theory in the XY model. Experiments probe the vortex-antivortex interaction indirectly through $I-V$ characteristic measurements. Detailed analysis of $V(I)$ near $T_c$ shows reasonable agreement with the spatial renormalization group theory of vortex interactions.

On a $\log-\log$ plot, the slope $a(T)$ measures the prefactor of the logarithmic interaction. The vortex unbinding temperature $T_c$ is determined by extrapolating $a(T_{c0})=1$ and taking $a(T_c)=3$. The effective dielectric constant $\epsilon_c = n_s^0 / n_s^R = 1.2 \pm 0.1$ is consistent with theoretical predictions.

## Summary

The KT transition is a purely topological phase transition that does not involve spontaneous symmetry breaking. Its essence is the binding-unbinding of vortex-antivortex pairs in two-dimensional systems. The low-temperature phase exhibits quasi-long-range order (algebraic order), while the high-temperature phase is disordered. KT theory applies not only to 2D XY magnetic systems, but also to a wide range of systems including 2D superconducting thin films and 2D liquid crystals.
