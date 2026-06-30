---
title: "😵Quantum Theory of Circular Dichroism"
date: 2022-08-31T10:00:00+08:00
draft: false
math: true
tags: ["Circular Dichroism", "Chirality", "Quantum Theory", "Multipole Expansion", "Condensed Matter"]
categories: ["Physics Notes"]
---

Circular Dichroism (CD) is a common experimental technique for studying molecular chirality. CD measures the difference in absorption of left- and right-circularly polarized light by a sample, serving as a probe of its chirality. Circularly polarized light has a helical electric field geometry in space, which is inherently chiral, so it stands to reason that left- and right-circularly polarized light would interact differently with chiral substances.

<!--more-->

A previous note explained the multipole expansion theory of light-matter interactions in quantum systems. Here, we simply take the electromagnetic wave in left- and right-circularly polarized form and subtract to obtain the CD spectrum of the sample. Since the multipole expansion theory in that note is a perturbative expansion, it is valid when the electronic wavefunction scale $r$ is much smaller than the optical wavelength $\lambda$.

## Quantum Theory of CD

The Hamiltonian typically seen in CD quantum theory is written as

$$ \hat{H} = \hat{H}_0 - Q \hat{\mathbf{r}} \cdot \mathbf{E} - \hat{\mathbf{m}}\cdot \mathbf{B} $$

which neglects the spatial dependence of the electromagnetic fields — this is the lowest-order approximation of multipole expansion theory. Strictly speaking, one should start from the vector potential $\mathbf{A}$ and include the electric quadrupole term at the same order as the magnetic dipole. However, it will be shown later that in randomly oriented systems, the electric quadrupole contribution can be neglected.

For a rigorous derivation, we introduce the electromagnetic field via the vector potential (transverse gauge), which gives the correct lowest-order approximation. The Hamiltonian above differs from the one obtained by introducing the electromagnetic field via the vector potential (transverse gauge) by a gauge transformation — see the previous note for details.

The Hamiltonian introducing the electromagnetic field via the transverse-gauge vector potential is

$$ \hat{H} = \frac{1}{2m} (\hat{\mathbf{p}} - Q \mathbf{A}(\hat{\mathbf{r}},t) )^2 + Q \phi(\hat{\mathbf{r}},t) + V(\hat{\mathbf{r}}) -\frac{Q}{m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t) $$

where the electric field is

$$ \mathbf{E}(\mathbf{r},t) = \frac{E_0}{2}e^{-iqz} e^{i \omega t} \mathbf{e}_E + c.c. = E_0(z) e^{i \omega t} \mathbf{e}_E + c.c. = \mathbf{E}(\mathbf{r}) e^{i \omega t} + c.c. $$

For left- and right-circularly polarized light:

$$ \mathbf{e}_E^{\pm} = \frac{1}{\sqrt{2}}(1,\pm i, 0) $$

The magnetic field part:

$$ \mathbf{B}(\mathbf{r},t) = \frac{E_0}{2\omega} (\mathbf{k} \times \mathbf{e}_E) e^{-iqz} e^{i \omega t} + c.c. = \mathbf{B}(\mathbf{r}) e^{i \omega t} + c.c. $$

Note that $\mathbf{k} = q \hat{z}$.

Correspondingly, $\mathbf{e}_B^{\pm}$ can be found:

$$ \mathbf{e}_B^{\pm} = \frac{1}{\sqrt{2}}(\mp i, 1, 0) $$

For incident light under typical experimental conditions, plugging all the above left- and right-circularly polarized light expressions into the equations, applying Fermi's golden rule via time-dependent perturbation theory, and subtracting the left-circular result, one obtains the general CD spectrum (difference spectrum).

We won't go through the full calculation of the general CD spectrum here — instead, we'll lay out the terms that need to be computed for a CD spectrum under the most general multipole expansion framework. Likewise, we won't assume the rotating wave approximation upfront; instead, we'll decide term by term based on what the calculation requires. Also, when summing over frequencies, contributions from both the positive and negative frequency parts of the light field must be considered.

## Multipole Expansion and CD

For the CD spectrum, we compute the absorption spectra for left- and right-circularly polarized light separately and then subtract them. The CD spectrum $\Delta A(\omega)$ is given by

$$ \Delta A(\omega) = A_+(\omega) - A_-(\omega) $$

According to Fermi's golden rule, the single-photon absorption spectrum can be written in the following symmetric form:

$$
A(\omega) = \frac{\pi Q^2}{\hbar^2} \sum_{i,f} P_i |\langle f | \hat{H}_{int} | i \rangle|^2 \delta(\omega_{fi} - \omega)
$$

where $\hat{H}_{int}$ is the light-matter interaction. Plugging in the transverse-gauge vector potential Hamiltonian above, we obtain the lowest-order terms of the light-matter interaction:

$$
\hat{H}_{int} = - \frac{Q}{m} \mathbf{A}(\hat{\mathbf{r}},t) \cdot \hat{\mathbf{p}} - \frac{Q}{2m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t)
$$

This can be rewritten as

$$
\hat{H}_{int} = \frac{iQE_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c.
$$

Under the assumption $r \ll \lambda$, we expand $e^{-iq\hat{z}}$:

$$
e^{-iq\hat{z}} = 1 - iq\hat{z} - \frac{1}{2}(q\hat{z})^2 + \cdots
$$

The zeroth-order term (electric dipole approximation):

$$ \hat{H}_{int}^{(0)} = \frac{iQE_0}{2m\omega} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c. $$

Using the commutation relation

$$ \hat{\mathbf{p}} = \frac{im}{\hbar}[\hat{H}_0, \hat{\mathbf{r}}] $$

we obtain the equivalent electric dipole form:

$$ \langle f | \hat{\mathbf{p}} | i \rangle = \frac{im}{\hbar} (E_f - E_i) \langle f | \hat{\mathbf{r}} | i \rangle $$

Thus the zeroth-order term can be rewritten in the familiar electric dipole form.

For the CD spectrum, the electric dipole contribution is identical for left- and right-circularly polarized light and therefore cancels in the difference spectrum. The first contributing terms are the electric dipole (E1)-magnetic dipole (M1) cross term and the E1-electric quadrupole (E2) cross term. After a rigorous calculation, the final CD spectrum expression under the rotating wave approximation is

$$
\Delta A(\omega) \propto \sum_{i,f} P_i \left[ \langle i | \hat{\mathbf{m}} | f \rangle \cdot \langle f | \hat{\mathbf{r}} | i \rangle \times \mathbf{k} + \frac{i\omega}{c} \langle i | \hat{\mathbf{r}} | f \rangle \cdot \mathbf{Q} \cdot (\hat{\mathbf{k}} \times \langle f | \hat{\mathbf{r}} | i \rangle) \right] \delta(\omega_{fi} - \omega)
$$

In randomly oriented systems, the electric quadrupole term averages to zero, leaving only the magnetic dipole contribution to the CD signal. This is why most textbooks only mention the E1-M1 cross term as the source of CD.

## Summary

This note rigorously derived the quantum theory of circular dichroism (CD) using the multipole expansion framework of light-matter interactions. The CD signal arises from the difference in absorption between left- and right-circularly polarized light, with the dominant contribution coming from the electric dipole-magnetic dipole (E1-M1) cross term. This theory provides a microscopic basis for understanding the spectroscopic characterization of chiral molecules.
