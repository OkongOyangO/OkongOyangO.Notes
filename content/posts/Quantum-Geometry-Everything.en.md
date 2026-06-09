---
title: "Quantum Geometry Everything? A Complete Guide to Quantum Geometric Physical Responses"
date: 2026-06-09T12:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Berry Curvature", "Quantum Metric", "Nonlinear Response", "Condensed Matter"]
categories: ["Physics Notes"]
---

This article (~15,000 characters) aims to clarify *what* Quantum Geometry *is* and *what it implies*. The first half focuses on definitions; the second half on phenomena. Read as needed.

<!--more-->

## Introduction

Quantum Geometry has recently become a hot topic in condensed matter physics, with a surge of related papers and reviews. The author first encountered it during a summer research program, and has since published a few notes, papers, and reviews:

- [Revealing quantum geometry in nonlinear quantum materials](https://iopscience.iop.org/article/10.1088/1361-6633/pde454)
- [Electrical magnetochiral anisotropy and quantum metric in chiral conductors](https://iopscience.iop.org/article/10.1088/2053-1583/ada0b8/meta)

The author's knowledge is limited and many gaps remain — comments and corrections from expert readers are warmly welcomed! Special thanks to Junkai Wang ([@Austeritas](https://www.zhihu.com/people/Junkai-Wang)) for the encouragement to update.

---

## What is Quantum Geometry?

**Q: What geometry is Quantum Geometry?**

**A: It is the geometry of wave functions.**

More specifically, the geometry described by Quantum Geometry is two-fold: one is the geometry of wave packets in real space, and the other is the geometry of state vectors in reciprocal space.

In real space: Quantum Geometry = **deformation** + **self-rotation** (physical picture).
In reciprocal space: Quantum Geometry = **length** + **area** (geometric picture).

Quantum geometry can also be understood as a transition dipole-dipole moment, and admits higher-order generalizations. Notably, all quantum geometric quantities are **gauge invariant** — they carry genuine physical meaning and are, in principle, experimentally observable.

### Real Space Wave Packet Geometry

Classical mechanics treats electrons as point particles whose translational motion gives rise to classical current. Quantum mechanics tells us that an electron exists as a wave function, described semi-classically as a wave packet in real space. Beyond center-of-mass translation, the wave packet has internal structure and motion — the two most intuitive being **self-rotation** and **deformation**: the former corresponds to Berry Curvature, the latter to Quantum Metric.

A magnetic field induces the (quantum) Hall effect because cyclotron motion produces transverse current. Similarly, a nontrivial Berry curvature contributes to the (quantum) anomalous Hall effect, because Berry curvature describes the self-rotation of the electronic wave packet, which generates an anomalous Hall current.

> **Figure ①** **(a) Quantum Metric ↔ Deformation**: Arc lengths $l_1, l_2$ on the Bloch sphere (quantum metric = length), corresponding to lateral spreading of the wave packet. **(b) Berry Curvature ↔ Rotation**: Area elements $S_1, S_2$ on the Bloch sphere (Berry curvature = area), corresponding to wave packet self-rotation.

Since the self-rotation degree of freedom is described by Berry curvature, it is natural to ask whether deformation can also be described by some geometric quantity. The answer is yes: this is the **Quantum Metric**.

> **Figure ②** $\Omega\sim\langle\mathbf{r}\times\mathbf{v}\rangle$ (Berry curvature = self-rotation); $g\sim\langle r_i r_j\rangle$ (quantum metric = spread). Under electric field $\mathbf{E}$: Berry curvature → transverse anomalous velocity; quantum metric → longitudinal deformation correction.

Beyond the Berry curvature-induced intrinsic anomalous Hall effect in linear response, there are also: the Berry curvature dipole-induced nonlinear anomalous Hall effect, and the quantum metric dipole-induced intrinsic nonlinear anomalous Hall effect and **intrinsic nonreciprocal magnetoresistance**.

Mathematically, we package Berry curvature $\Omega^{\mu\nu}$ and quantum metric $g^{\mu\nu}$ into the **Quantum Geometric Tensor** $Q^{\mu\nu}$:

$$Q^{\mu\nu} = g^{\mu\nu} - i \Omega^{\mu\nu}$$

Here $g^{\mu\nu}$ is the Quantum Metric (Fubini-Study metric) — a symmetric tensor; $\Omega^{\mu\nu}$ is the Berry Curvature — an antisymmetric tensor.

### Dipole-Dipole Excitation Rate

The quantum geometric tensor can be written explicitly as:

$$Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n = g^{\mu\nu}_n - i \Omega^{\mu\nu}_n$$

where $r^a_{nm} \equiv \langle \psi_m | \hat{r}^a | \psi_n \rangle$ is the interband transition dipole. The constraint $m \neq n$ is imposed by gauge invariance. The operator $\Delta\hat{r}^\mu \equiv \hat{r}^\mu - \langle\hat{r}^\mu\rangle_n$ removes the gauge-dependent diagonal part.

> **Figure ③** $Q_n^{\mu\nu} = \langle\Delta\hat{r}^\mu\Delta\hat{r}^\nu\rangle_n$: A Gaussian wave packet (yellow) in real space, with double arrows labeling its second-order moments. The parallelogram shape symbolizes QGT as the geometric measure of the wave packet's internal structure.

We can generalize quantum geometry from a single band to the full ground state:

$$Q^{\mu\nu}_{GS} = \operatorname{tr} \left[ \hat{P} \hat{r}^\mu (\mathbb{I} - \hat{P}) \hat{r}^\nu \right]$$

The Fermi Golden Rule gives the transition rate under a spatially uniform electric field:

$$\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} r^\mu_{mn} r^\nu_{nm} \delta(\omega - \omega_{mn}) E^\mu(\omega) \bar{E}^\nu(\omega)$$

> **Figure ④** Two-band diagram: blue parabola ($m$-band) and red parabola ($n$-band). Thick white arrow ($\mathcal{I}_{m\leftarrow n}$) marks the transition; lightning bolt labels driving frequency $\omega$.

Integrating over $\omega$ and summing over all $m\neq n$:

$$\mathcal{I}_{n}^{tot} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu$$

Weighting the transition rate by other physical quantities gives different geometric responses:

- (i) $\mathcal{I}_{m\leftarrow n} \times 1$: Transition Rate
- (ii) $\mathcal{I}_{m\leftarrow n} \times (E_m - E_n)$: Joule Heat (dissipative linear conductivity)
- (iii) $\mathcal{I}_{m\leftarrow n} \times (v_m - v_n)$: Velocity Shift (injection current)
- (iv) $\mathcal{I}_{m\leftarrow n} \times (r_m - r_n)$: Positional Shift (shift current)

### Momentum Space Eigenstate Geometry

Since $\hat{\mathbf{r}} = i\nabla_{\mathbf{k}}$ in reciprocal space, the quantum geometric tensor describes the metric of the wave function in reciprocal space:

$$Q^{\mu\nu}_{n} \sim \langle \psi_n | \nabla_{k_\mu} \nabla_{k_\nu} | \psi_n \rangle$$

> **Figure ⑤** Bloch sphere: red arcs $l_1, l_2$ label arc lengths (quantum metric $g_\mathbf{k}^{ab}$); orange-shaded patches $S_1, S_2$ label area elements (Berry curvature $\Omega_\mathbf{k}$). QGT encodes both "length" and "area" of the Hilbert-space manifold.

The gauge-invariant expressions:

$$dl^2 = g^{\mu\nu} dk_\mu dk_\nu, \qquad dS = \Omega^{\mu\nu} dk_\mu dk_\nu$$

This leads to the geometric bound $\operatorname{tr}g \geq 2|\Omega^{xy}|$ — by the isoperimetric analogy, "length" naturally bounds "area" from above.

### Gauge Invariance and Projector Formalism

The diagonal element $\langle\hat{r}^\mu\rangle_n$ depends on the arbitrary choice of lattice origin and is not physical. Removing it leaves only gauge-invariant information in the quantum geometric tensor.

> **Figure ⑥** Gauge transformation = shift of lattice origin: original unit cell → new unit cell, with the wave packet center shifting with the origin choice (same physical state). Illustrates that the diagonal part is gauge-dependent; the off-diagonal quantum geometric tensor is gauge invariant.

The **projector formalism** ensures gauge invariance from the start:

$$\hat{P}_n = |\psi_n\rangle\langle\psi_n|$$

$$g^{\mu\nu}_n = \frac{1}{2}\operatorname{tr}[\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n], \quad \Omega^{\mu\nu}_n = i\operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n] - (\mu\leftrightarrow\nu), \quad Q^{\mu\nu}_n = \operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\hat{P}_n]$$

### Higher Order Quantum Geometry

The quantum connection:

$$Q^{\mu;\nu\rho}_n = \operatorname{tr}\left[\hat{P}_n\partial_\mu\hat{P}_n\partial_\nu\partial_\rho\hat{P}_n\right]$$

Relations to Berry curvature and quantum metric dipoles:

$$\partial_\rho g^{\mu\nu}_n = \operatorname{Re}\left[Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n\right], \qquad \partial_\rho\Omega^{\mu\nu}_n = -2\operatorname{Im}\left[Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n\right]$$

### Multi-band Quantum Geometry

The 2-band quantum geometric tensor:

$$Q^{\mu\nu}_{nm} = r^{\mu}_{nm}r^{\nu}_{mn} = \operatorname{tr}[\hat{P}_n\partial_\mu\hat{P}_m\partial_\nu\hat{P}_n]$$

In a 2-band system, 2-band and 1-band quantum geometry contain the same information. Quantized circular injection conductivity holds precisely because it equals the integral of all 2-band quantum geometric tensors.

---

## What Does Quantum Geometry Imply?

Packaging matrix elements into quantum geometric tensors brings two key benefits:

1. Physical/geometric intuition for all observables.
2. Connections to geometry/topology yield interesting identities and inequalities, most importantly:

$$\sigma_{xy} = \frac{e^2}{h} C = \frac{e^2}{h}\int_{BZ} d^dk\,\Omega^z(k)$$

### Quantum Geometric Responses

**(i) Transition Rate**

$$\mathcal{I}_{n}^{tot} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu$$

Linearly polarized light probes quantum metric; the circular dichroism (left minus right circular) probes Berry curvature.

**(ii) Joule Heat / Dissipative Linear Conductivity**

$$\int d\omega\,\frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu} \quad \text{(SWM sum rule)}$$

$$\int d\omega\,\sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D} \quad \text{(optical f-sum rule)}$$

Polarizability $\chi^{ab}=\sigma^{ab}/i\omega$, dielectric constant $\epsilon = 1+\chi$, and refractive index $n=\sqrt{\epsilon}$ are all influenced by quantum geometry.

**The more topologically nontrivial a system, the larger its refractive index.** Why does diamond sparkle so brilliantly? Diamond is an obstructed atomic insulator — its nontrivial topology/quantum geometry gives $n=2.4$, while Rock Salt (atomic insulator) has only $n=1.5$.

**(iii) Injection Current (Velocity Shift)**

$$\sigma_{\mathrm{inj}}^{ab;c} \propto \int_{S_k = \{k|\omega = \omega_{mn}(k)\}} dS_k^c\, Q^{ab}$$

In a 2-band system, the CPGE (circularly polarized light injection current) is quantized.

**(iv) Shift Current (Positional Shift)**

The Shift Vector $R_{mn}^a = \mathcal{A}_{mm}^a - \mathcal{A}_{nn}^a - \nabla_{k_a}\arg(r_{mn})$ is gauge invariant.

$$\sigma_{\mathrm{shift}}^{ab;c} \propto \int_{\mathbf{k}} C_{bca}\,\delta(\omega - \omega_{mn})$$

Unlike injection current, shift current is theoretically independent of the relaxation time $\tau$ — a purely quantum geometric effect with great potential for ultrafast optoelectronics.

**(v) Nonlinear Transport**

In the transport regime ($\omega\to 0$), scaling with $\tau$ peels apart geometric contributions:

$$j^{(2)} = -e\sum_n\int[dk]\left(\underbrace{f_n^{(2)}v_n^{(0)}}_{\text{NLD}\,(\tau^2)} + \underbrace{f_n^{(1)}v_n^{(1)}}_{\text{BCD}\,(\tau^1)} + \underbrace{f_n^{(0)}v_n^{(2)}}_{\text{QMD}\,(\tau^0)}\right)$$

**NLD ($\tau^2$):**
$$\sigma_{ab;c}^{\text{NLD}} = \frac{e^3\tau^2}{\hbar^3}\sum_n\int[dk]\,f_n\frac{\partial^3\varepsilon_n}{\partial k_a\partial k_b\partial k_c}$$

**BCD ($\tau^1$, Berry Curvature Dipole, Sodemann & Fu):**
$$\sigma_{ab;c}^{\text{BCD}} = \frac{e^3\tau}{\hbar^2}\sum_n\int[dk]\,f_n\left(\frac{\partial\Omega_n^{bc}}{\partial k_a} + \frac{\partial\Omega_n^{ac}}{\partial k_b}\right)$$

**QMD ($\tau^0$, fully intrinsic, Quantum Metric Dipole):**
$$\sigma_{ab;c}^{\text{QMD}} = \frac{e^3}{\hbar}\sum_n\int[dk]\,f_n\left(2\frac{\partial G_n^{ab}}{\partial k_c} - \frac{1}{2}\left(\frac{\partial G_n^{bc}}{\partial k_a} + \frac{\partial G_n^{ac}}{\partial k_b}\right)\right)$$

where $G_n^{ab} = \sum_{m\neq n}\frac{r^a_{nm}r^b_{mn} + r^b_{nm}r^a_{mn}}{\epsilon_{nm}}$ is the band-normalized quantum metric.

**(vi) Other Geometric Responses**

> **Table ①** Quantum geometric quantities and observable responses (from Tobias's review, arXiv:2504.07173) — includes Anomalous Hall, Non-reciprocal conductivity, Optical transition rate, Injection current (linear/circular pol.), Shift current, Spectral weight, Chern number, etc.

### Geometric Bounds & Sum Rules

**(i) Geometric Bound**

Isoperimetric inequality: among all closed curves with perimeter $L$, the circle maximizes area ($L^2\geq 4\pi A$). Quantum geometric analogue:

$$\mathrm{Tr}(g) \geq |\Omega|$$

> **Figure ⑦** Isoperimetric inequality → Quantum Geometric Bound: shapes of given perimeter → maximum area (circle). **Length ≥ Area**, **Quantum Metric ≥ Berry Curvature**.

Integrating over the Brillouin zone:

$$\int_{BZ}\mathrm{Tr}(g(\mathbf{k}))\,d^2k \geq 2\pi|C|$$

Topologically nontrivial bands ($C\neq 0$) must have a minimum total quantum metric.

> **Figure ⑧** Top — Atomic Insulator (Trivial): Wannier functions highly localized, no overlap between neighbors. Bottom — Chern Insulator (Topological): Wannier functions inevitably overlap between neighboring sites, with nonzero minimum spread $\Omega_I\propto\int\mathrm{Tr}[g]\,dk$.

The equality $\mathrm{Tr}(g(\mathbf{k})) = |\Omega(\mathbf{k})|$ — the **Trace Condition** — corresponds to Landau Level ideal quantum geometry and is the key criterion for FCI design.

The geometric bound is rooted in the fundamental uncertainty principle $[\hat{x},\hat{p}]=i\hbar$.

**(ii) Sum Rules**

Sum rules reflect the "weight" with which a system responds to external perturbations — intrinsic ground-state properties, independent of excited states.

**(iii) Universal Bound**

Y. Onishi and L. Fu [Phys. Rev. X 14, 011052 (2024)]:

$$E_g \leq \frac{\pi n e^2}{2m|C|}\times(\text{const.})$$

The topological gap is fundamentally bounded by electron parameters ($n, m$).

**(iv) Generalized Geometric Bound**

Even when Berry curvature vanishes everywhere, real-space invariants (RSIs) can enforce a nonzero lower bound on quantum metric [Herzog-Arbeitman, Bernevig et al., PRL 128, 087002 (2022)].

Shinada and Nagaosa [arXiv:2507.12836 (2025)] generalized QGT to arbitrary parameter space $\boldsymbol{\lambda}$.

> **Table ②** External fields and conjugate operators (Shinada & Nagaosa): $A\leftrightarrow\hat{J}$, $E\leftrightarrow\hat{P}_e$, $B\leftrightarrow\hat{S}$, $\partial u\leftrightarrow\hat{\sigma}$.

**(v) Generalized Sum Rule**

Generalized moments $W_\eta = \int_0^\infty\omega^\eta\text{Re}[\sigma(\omega)]\,d\omega$: $\eta=-1$ (dielectric function); $\eta=0$ (f-sum); $\eta=1$ (effective mass); $\eta=2$ (shot noise).

Shift current sum rule (Skewness hierarchy):

$$\int_0^\infty d\omega\,\sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega) \approx \frac{2\pi e^3}{\hbar^2}\frac{1}{V}\langle\hat{X}_\alpha\hat{X}_\beta\hat{X}_\gamma\rangle_c$$

Hierarchy:
- Linear ($n=1$) ↔ Variance ↔ Quantum Metric
- Shift current ($n=2$) ↔ Skewness ↔ Multistate Geometry
- Third-order ($n=3$) ↔ Kurtosis

Time-dependent QGT (tQGT, Verma & Queiroz) as generating function of all sum rules:

$$\mathcal{S}_{\mu\nu}^\eta = \frac{\pi e^2}{\hbar}\left[(-i\partial_t)^\eta\mathcal{Q}_{\mu\nu}(t)\right]_{t=0}$$

A step-response measurement directly yields the Quantum Metric without full spectral measurements.

### Quantum Geometric Correlated Phases

**(i) Quantum Geometric Spontaneous Symmetry Breaking**

In the flat band limit ($W\to 0$), physics is entirely controlled by the geometric form factor:

$$\chi_0(\mathbf{q}) \approx \frac{1}{k_BT}\sum_{\mathbf{k}}\nu(1-\nu)\left|\langle u_{\mathbf{k}}|u_{\mathbf{k}+\mathbf{q}}\rangle\right|^2$$

If the geometric factor favors a particular $\mathbf{q}$, an order parameter develops — **Quantum Geometric Nesting**, entirely distinct from energy-based Fermi surface nesting.

**(ii) Electron-Phonon Coupling** — see Jiabin Yu's paper.

**(iii) Fractional Chern Insulator (FCI)**

FCI is fundamentally about emulating Landau Levels — not only in energy (flat band) but also in wave function (quantum geometry/topology): not just a Chern band, but one satisfying the Trace Condition throughout the Brillouin zone.

Quantum geometry serves as the key ingredient to measure our deviation from the ideal Landau Level.

### Quantum Geometric Information Theory

**(i) Quantum Fisher Information (QFI)**

In the pure-state limit ($T\to 0$): $F_Q = 4g_{\lambda\lambda}$.

**QFI = 4 × Quantum Metric** — QFI is the natural generalization of Quantum Metric to mixed states (finite temperature).

$$F_Q(T) = \frac{4}{\pi}\int_0^\infty d\omega\tanh\left(\frac{\hbar\omega}{2k_BT}\right)\chi''_{\hat{h}}(\omega,T)$$

**(ii) Entanglement Entropy**

For free fermions, the Rényi entanglement entropy:

$$S_A^{(\alpha)} = \frac{1}{1-\alpha}\text{Tr}\ln\det[p\mathbf{1} - C_A]$$

Since the correlation matrix reflects real-space overlaps and distances of wave functions, Quantum Metric and entanglement entropy share a direct geometric correspondence.

---

## References

Under construction...

---

## Closing Remarks

Thank you for reading to the end. After nearly two years without updates, I found myself unexpectedly relocated from Israel to the United States, and am fortunate to continue studying condensed matter physics under my advisor's guidance. Life, studies, work, and relationships have all changed considerably during my time in the US, and I am still slowly adapting. As research deepens, note-writing time has diminished. To those readers who have been waiting for updates — and to anyone who has seen this platform become an outlet for my feelings rather than serious notes — I sincerely apologize.

I dedicate this article to the years of understanding, stumbling, and results I've accumulated in quantum geometry. Thank you all for your continued support — until we meet again ～
