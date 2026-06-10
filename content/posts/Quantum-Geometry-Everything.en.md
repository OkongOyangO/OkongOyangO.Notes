---
title: "🥺 Quantum Geometry Everything? A Complete Guide to the Quantum-Geometric Physical Responses"
date: 2026-06-09T12:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Berry Curvature", "Quantum Metric", "Nonlinear Response", "Condensed Matter"]
categories: ["Physics Notes"]
---

This article explains both *what Quantum Geometry means* and *what it implies*.

The first half leans toward theoretical derivation, the second half toward experimental phenomena; readers may read as needed.

<!--more-->

## Introduction

Recently the concept of Quantum Geometry has become quite hot in the field of condensed matter physics, with a flood of related papers and reviews. I first encountered it during a summer research program, and was later fortunate enough to publish a note, a paper, and a review or two. If you are interested, feel free to take a look:

> 🔗 *【link: note and paper】*

But my own level is limited, I have not read many papers, and my research experience is also limited, so there are many oversights. I hope all of you expert readers will not hesitate to offer your advice in the comments! Finally, thanks to Zhihu internet-famous article author Xiao Wang [https://www.zhihu.com/people/Junkai-Wang] for urging me to update!

## What is Quantum Geometry?

Q: What geometry does quantum geometry refer to?
A: The geometry of the wavefunction.

More specifically, the wavefunction geometry described by quantum geometry is 2-fold: the first is the geometry of the wave packet in real space, and the second is the geometry of the state vector in reciprocal space.

In real space, Quantum Geometry = deformation + self-rotation, which reflects its physical meaning;
In reciprocal space, Quantum Geometry = length + area, which reflects its geometric meaning.

At the same time, quantum geometry can also be understood as the transition dipole-dipole moment, and it can also have higher-order generalizations. It is worth mentioning that all these constructed quantum geometric quantities are gauge invariant, meaning they have actual physical significance and are even observable physical quantities.

In this section, we first introduce the physical meaning of quantum geometry in real space, and present its interpretation as a transition dipole-dipole moment. We then introduce its geometric meaning in reciprocal space, and finally briefly introduce the higher-order terms of quantum geometry and the gauge invariance of quantum geometry.

### Real Space Wave Packet Geometry

Classical mechanics generally treats the electron as a point particle, whose translational motion gives rise to the classical current; quantum mechanics, however, tells us that the electron is not a point particle, but exists in the form of a wavefunction. Its semiclassical description in real space is a wave packet. In addition to the overall translational motion of the center of mass like a point particle, the wave packet also has internal structure & motion. The two most intuitive examples are the self-rotation and deformation of the wave packet; the former corresponds to Berry Curvature, and the latter corresponds to Quantum Metric.

We all know that a magnetic field can lead to the (quantum) Hall effect, because the cyclotron motion of electrons in a magnetic field produces motion in the transverse direction, which in turn contributes to the Hall current.

We are also all familiar with the fact that nontrivial Berry curvature can contribute to the (quantum) anomalous Hall effect, because nontrivial Berry curvature describes the self-rotation of the electronic wavepacket itself, and this self-rotation motion can also produce an anomalous Hall current, analogous to the cyclotron motion in a magnetic field.

![Fig: Magnetic field vs Berry curvature](/posts/quantum-geometry-everything/fig01.png)

Since the self-rotation degree of freedom of the wave packet can be described by the Berry curvature, we naturally think of the other degrees of freedom of the wave packet, such as the deformation of the wave packet—can it also be described by some geometric quantity? The answer is yes, and this is the Quantum Metric.

It is not hard to imagine that, comparing a rigid body that remains unchanged during motion with a wave packet whose interior can deform/rotate during motion, the latter, in addition to its overall translation, also has anomalous motion caused by internal deformation/rotation. This is the physical mechanism by which quantum geometry produces various geometric responses. In addition to the Berry curvature induced intrinsic anomalous Hall effect commonly seen in linear response, there is also the Berry curvature dipole induced nonlinear anomalous Hall effect in nonlinear effects, as well as the quantum metric dipole induced intrinsic nonlinear anomalous Hall effect & intrinsic nonreciprocal magnetoresistance.

![Fig: quantum metric vs deformation](/posts/quantum-geometry-everything/fig02.png)

Taking nonreciprocal magnetoresistance as an example, in a magnetic system, i.e. a system with broken time-reversal symmetry, the distribution of the quantum metric in momentum space is not symmetric, which can in turn lead to a nonzero quantum metric dipole structure. In this way, when we apply an electric field parallel/antiparallel to the direction of this dipolar distributed quantum metric, the quantum metric/deformation experienced as the central momentum of the wave packet moves in the parallel/antiparallel direction is different. This leads to different resistances of the system under parallel/antiparallel electric fields, which in turn leads to nonreciprocal magnetoresistance. This nonreciprocity can be used to construct novel diode devices, and its performance is determined by the material's quantum metric, an intrinsic quantum geometric quantity. This is one of the possible avenues by which quantum geometry helps in the search for novel electronic devices.

Mathematically, we can also package the Berry curvature $\Omega^{\mu\nu}$ and the quantum metric $g^{\mu\nu}$ into a single whole, called the Quantum Geometric Tensor $Q^{\mu\nu}$

$$
Q^{\mu\nu} = g^{\mu\nu} - i \Omega^{\mu\nu}
$$

where $g^{\mu\nu}$ is the Quantum Metric or Fubini-Study metric, which, like the metric in differential geometry, is a symmetric tensor, and $\Omega^{\mu\nu}$ is the Berry Curvature, which is an antisymmetric tensor. In 2D/3D space, we are sometimes more accustomed to expressing the Berry curvature in scalar/vector form using $\Omega^z = \Omega^{xy} - \Omega^{yx}$ or $\Omega^a = \epsilon^{abc} \Omega^{bc}$, in which case the direction of $\Omega^a$ directly indicates the direction of the angular momentum/magnetic moment of the wave packet's rotation.

### Dipole-Dipole Excitation Rate

In more detail, we can write out the explicit form of $Q_{\mu\nu}$:

$$
Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n = g^{\mu\nu}_n - i \Omega^{\mu\nu}_n
$$

where $r^a_{nm} \equiv \langle \psi_m | \hat{r}^a | \psi_n \rangle$ is the matrix element of the position operator $\hat{r}^a$ between the m-th band $|\psi_m\rangle$ and the n-th band $|\psi_n\rangle$, and is also often called the interband Berry connection/interband transition dipole.

The "interband" here means that this matrix element is between two different bands, i.e. $m \neq n$, which is out of consideration for gauge invariance.

Here $\langle ... \rangle_n$ denotes the expectation value in the n-th band, and $\Delta \hat{r}^\mu \equiv \hat{r}^\mu - \langle \hat{r}^\mu \rangle_n$ denotes the deviation of the position operator from the central position by its expectation value in the n-th band. This exactly removes the gauge dependent diagonal part of the dipole matrix element. We will later show that this gauge dependence is related to the artificial choice of coordinates, so removing the diagonal element here is in order to remove the unphysical quantities from the expression and retain the observable physical quantities.

Its symmetric part is the quantum metric $g^{\mu\nu}_n$, and its antisymmetric part is the Berry Curvature $\Omega^{\mu\nu}_n$.

Starting from this definition, on the one hand, we have mathematically refined our previous understanding of the quantum geometric tensor—the quantum metric gives the symmetric part of the dipole dipole moment of the wavefunction in real space (the real space spread, which in fact also corresponds to the spread of the Wannier function; you may refer to my previous note, and we will not elaborate here), and the Berry curvature gives the antisymmetric part (self-rotation). We can also generalize quantum geometry from a property of a single band to a real space property of the entire ground state wavefunction, so that we no longer need the band structure, and can even construct a quantum geometric tensor for an arbitrary quantum many-body system:

$$
Q^{\mu\nu}_{GS} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_{GS} = \operatorname{tr} \left[ \hat{P} \hat{r}^\mu (\mathbb{I} - \hat{P}) \hat{r}^\nu \right]
$$

where $\hat{P}$ is the Ground State projector operator and $\mathbb{I}$ is the identity matrix. In this way, a quantum geometric tensor can be defined for an arbitrary (ground) state, as an intrinsic physical quantity of the (ground) state, and it can also reflect a series of fundamental physical properties of the ground state such as its conductivity:

> 🔗 *【link: Wannier function spread note】*

> 🔗 *【link: insulator or metal】*

![Fig: quantum metric vs real space spread](/posts/quantum-geometry-everything/fig03.png)

On the other hand, we can also have a new understanding—the quantum metric corresponds to the symmetric part of the dipole dipole excitation, and the Berry curvature corresponds to the antisymmetric part of the dipole dipole excitation.

This new understanding is very helpful in our search for quantum geometric responses. Let us first recall where we might encounter dipole dipole excitation; we naturally think of the Fermi Golden Rule in quantum mechanics (regarding the connection between the Fermi Golden Rule and Response Theory, you may also refer to my previous note, and we will not elaborate here).

The Fermi Golden Rule tells us that under the action of a spatially uniform external electric field (with perturbation Hamiltonian $H' = -e \hat{\mathbf{r}} \cdot \mathbf{E}$), the transition rate from the n-th band (eigenstate) to the m-th band (eigenstate) is:

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi}{\hbar^2} | \langle \psi_m | -e \hat{\mathbf{r}} \cdot \mathbf{E}(\omega) | \psi_n \rangle |^2 \delta(\omega - \omega_{mn})
$$

It is not hard to see that this directly contains the interband dipole-dipole transition matrix element we need, $\langle \psi_m | -e \hat{\mathbf{r}} \cdot \mathbf{E} | \psi_n \rangle = - e r^\mu_{mn} E^\mu$, so that:

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2}  r^\mu_{mn} r^\nu_{nm} \delta(\omega - \omega_{mn}) E^\mu(\omega) \bar{E}^\nu(\omega)
$$

![Fig: Fermi Golden Rule](/posts/quantum-geometry-everything/fig04.png)

where $\bar{E}$ denotes the complex conjugate, and we define $\mathbf{E}(t) = \mathbf{E}(\omega) e^{i \omega t} + c.c.$. It is not hard to see that by performing a few operations on the whole expression, we can directly extract the quantum geometric quantity within it.

For example, summing over all states with $m \neq n$, we obtain the total transition rate from the n-th band to other bands $\sum_{m \neq n} \mathcal{I}_{m \leftarrow n}(\omega)$, and then integrating over $\omega$ to cancel the delta function, we obtain that the total transition rate of the n-th band is proportional to the quantum geometric tensor of the n-th band.

$$
\mathcal{I}_{n}^{tot} = \int d\omega \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} \sum_{m \neq n} r^\mu_{mn} r^\nu_{nm}  E^\mu \bar{E}^\nu \propto Q^{\mu\nu}_{n} E^\mu \bar{E}^\nu
$$

This tells us that the total transition rate of the system for a uniformly distributed spectrum is proportional to the quantum geometric tensor. This is also a direct application of the transition dipole-dipole matrix element interpretation of the quantum geometric tensor: in the past, we generally started from the various matrix elements of the response function to assemble the geometric quantity, and then claimed that these responses were geometric. Now, if we have a deeper understanding of the physical interpretation of the geometric quantity, we can do exactly the opposite, and directly construct the geometric response of a physical quantity starting from its physical meaning.

Here we summed over the pure transition rate, but we can also use a similar method to construct more transition rates. For example, multiplying the transition rate by the "energy difference from the m-th band to the n-th band" $\omega_{mn} = E_m - E_n$ gives the energy dissipation rate, which for an electric-field-driven system is in fact the Joule heat. I have a related note before, which you may refer to.

> 🔗 *【link: Joule heat note】*

And the Joule heat further corresponds to the dissipative part of the linear conductivity, which shows that the dissipative linear conductivity is also quantum geometric.

As another example, multiplying the transition rate by the "velocity difference from the m-th band to the n-th band" $v_m - v_n = \nabla_k \omega_{mn}$ gives the velocity shift rate, which is directly related to the injection current in nonlinear optical conductivity; and as yet another example, multiplying the transition rate by the "displacement from the m-th band to the n-th band" $R_{mn} \sim \langle r \rangle_m - \langle r \rangle_n$ gives the positional shift rate, which is directly related to the shift current in nonlinear optical conductivity. Both of these have been shown to be quantum geometric: the former is related to the quantum metric/Berry curvature, while the latter is related to the higher-order quantum connection.

To summarize:

(i) $\mathcal{I}_{m \leftarrow n} \times \text{1}$: Transition Rate 

(ii) $\mathcal{I}_{m \leftarrow n} \times (E_m - E_n)$: Joule Heat (dissipative linear conductivity)

(iii) $\mathcal{I}_{m \leftarrow n} \times (v_m - v_n)$: Velocity Shift (injection current)

(iv) $\mathcal{I}_{m \leftarrow n} \times (r_m - r_n)$: Positional Shift (shift current)

We will give a more detailed explanation later.

### Momentum Space Eigenstate Geometry

Now that we understand that the quantum metric and Berry curvature describe, respectively, the deformation and self-rotation of an electronic wavepacket in real space — mathematically corresponding to the symmetric and antisymmetric parts of the interband dipole-dipole transition matrix element $\langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n$ — we now turn to the geometric meaning of quantum geometry in reciprocal space (momentum space).

Quantum mechanics tells us that the representation of the momentum operator in real space is the derivative with respect to the coordinate $\mathbf{r}$, namely $\hat{\mathbf{k}} = -i \nabla_{\mathbf{r}}$. Correspondingly, the representation of the position operator in reciprocal space is the derivative with respect to the momentum $\mathbf{k}$, namely $\hat{\mathbf{r}} = i \nabla_{\mathbf{k}}$. We also already know that the essence of a quantum geometric quantity is the expectation value of an (interband) dipole-dipole. Combining the two, we obtain that the quantum geometric tensor describes the metric of the wavefunction in reciprocal space:

$$
Q^{\mu\nu}_{n} = \langle \Delta \hat{r}^\mu \Delta \hat{r}^\nu \rangle_n \sim \langle \psi_n | \nabla_{k_\mu} \nabla_{k_\nu} | \psi_n \rangle
$$

![Figure: curved space metric vs Bloch sphere](/posts/quantum-geometry-everything/fig05.png)

More rigorously, the gauge-invariant expression is:

$$
Q^{\mu\nu}_{n} =  \langle \nabla_{k_\mu} \psi_n | \left[ \mathbb{I} - | \psi_n \rangle \langle \psi_n | \right] | \nabla_{k_\nu} \psi_n \rangle
$$

By now we know that the real-space position operator acting on our wavefunction space is equivalent to taking a derivative in reciprocal space — or, in other words, performing an infinitesimal shift $\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$, then multiplying the change of the state vector either symmetrically or antisymmetrically. This is exactly the operation by which we measure "length" and "area" on a differential manifold. From this viewpoint, the quantum metric measures the "length" of the wavefunction space in reciprocal space, $dl^2 = g^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$, while the Berry curvature reflects the "area" of the wavefunction space in reciprocal space, $dS = \Omega^{\mu\nu} \mathrm{d} k_\mu \mathrm{d} k_\nu$.

![Figure: Bloch sphere metric and curvature](/posts/quantum-geometry-everything/fig06.png)

Specifically, let us first consider how to compute the distance of a line element. To obtain the line element, we consider the change of the state vector corresponding to $\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$. In this process, the wavefunction goes from $|\psi_n(\mathbf{k})\rangle$ to $|\psi_n(\mathbf{k} + d\mathbf{k})\rangle$, and the vector corresponding to the change of the wavefunction in Hilbert space is $|\psi_n(\mathbf{k} + d\mathbf{k})\rangle - |\psi_n(\mathbf{k})\rangle$, while the vector corresponding to this change in reciprocal space is $|\Delta \psi_n(\mathbf{k})\rangle = |\partial_{k_\mu} \psi_n(\mathbf{k})\rangle dk_\mu$. To obtain the (square of the) length, we take the inner product of this vector with itself, obtaining

$$
dl^2 = \langle \Delta \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k}) \rangle = \langle \partial_{k_\mu} \psi_n(\mathbf{k}) | \partial_{k_\nu} \psi_n(\mathbf{k})\rangle dk_\mu dk_\nu
$$

However, the line element defined in this way is not gauge invariant, because the truly physical part of the wavefunction is independent of its norm. This means we still need to remove the component of $|\Delta \psi_n(\mathbf{k})\rangle$ along the norm direction — that is, remove the projection of $|\Delta \psi_n(\mathbf{k})\rangle$ along the direction of $|\psi_n(\mathbf{k})\rangle$ — yielding $|\Delta \psi_n(\mathbf{k})\rangle \rightarrow |\Delta \psi_n(\mathbf{k})\rangle_{\text{real}} = |\Delta \psi_n(\mathbf{k})\rangle - \langle \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k})\rangle |\psi_n(\mathbf{k})\rangle$, and thereby obtaining the gauge-invariant line element

$$
dl^2 = {}_{\text{real}}\langle \Delta \psi_n(\mathbf{k}) | \Delta \psi_n(\mathbf{k}) \rangle_{\text{real}} = g^{\mu\nu} dk_\mu dk_\nu
$$

Similarly, the antisymmetric part corresponding to the Berry curvature can be understood as the area of an area element given by a "cross product", so that:

$$
dS = \Omega^{\mu \nu} dk_\mu dk_\nu
$$

This is very useful for understanding the Chern number and Chern insulators: the integral of the Berry curvature is equivalent to the integral of the area on the Bloch sphere. When the wavefunctions mapped over the entire Brillouin zone cover the whole Bloch sphere, the corresponding area integral equals the area of the unit sphere (since the wavefunctions are all normalized, with norm 1), which is quantized.

This is also very useful for understanding the geometric bound between the quantum metric and the Berry curvature. Consider this: among all shapes with a given perimeter, we can always find the one that maximizes the area (the circle!). This means that, from a purely geometric standpoint, there is a natural upper bound on "area" given the "length". This helps us understand the upper bound of the Berry curvature set by the quantum metric, namely the geometric bound in 2D systems that we will mention later: $\operatorname{tr} g  \geq 2 |\Omega^{xy}|$. We leave it at that for now.

### Gauge Invariance and Projector Formalism

We mentioned earlier the issue of gauge invariance. In short, after adding a phase to the wavefunction (a gauge transformation) $|\psi\rangle \rightarrow |\psi'\rangle = e^{i \theta} |\psi\rangle$, the wavefunction still describes the same state, and the physical quantities we observe must not change — for example the probability $P = |\langle \psi | \psi \rangle|^2$, the expectation value $\langle \psi | \hat{\mathcal{O}} | \psi \rangle$ of an observable $\hat{\mathcal{O}}$, the response function $\chi_{A;B} \propto \langle \psi | [ \hat{A}, \hat{B} ] | \psi \rangle$, and so on.

In particular, for lattice systems the gauge is closely tied to the choice of origin of the spatial coordinates, so let us elaborate a bit here.

What is called gauge dependence corresponds to a phase change. For the Bloch wavefunction of a lattice system, $|\psi_{n\mathbf{k}}\rangle = e^{i \mathbf{k} \cdot \mathbf{r}} |u_{n\mathbf{k}}\rangle$, our gauge transformation (adding a phase) $|\psi_{n\mathbf{k}}\rangle \rightarrow |\psi_{n\mathbf{k}}\rangle e^{i \theta_n(\mathbf{k})}$ is equivalent to performing a translation $e^{i \mathbf{k} \cdot \mathbf{r}}  \rightarrow e^{i \mathbf{k} \cdot (\mathbf{r} + \mathbf{R}_n(\mathbf{k}))}$, as long as $\mathbf{k} \cdot \mathbf{R}_n(\mathbf{k}) = \theta_n(\mathbf{k})$. The diagonal element of the dipole matrix element, $\langle \hat{r}^\mu \rangle_n = \langle \psi_n | \hat{r}^\mu | \psi_n \rangle$, physically represents the center position of the n-th band Bloch wavefunction. But in a periodic-boundary (or, equivalently, infinitely large) lattice system, this center position depends on where we place the origin of the lattice, so this diagonal element is not a physical quantity but one tied to the arbitrary choice of coordinates. After removing it, the resulting quantum geometric tensor retains only the physical, gauge-invariant information, which further convinces us that the quantum geometric quantities we package up are physical, intrinsic quantities.

![Figure: gauge dependence vs coordinate choice](/posts/quantum-geometry-everything/fig07.png)

If we write out the diagonal term explicitly here, it can be written as:

$$
\langle \psi_{n\mathbf{k}} | \hat{r}^\mu | \psi_{n\mathbf{k'}} \rangle = \left[ -i \partial_{k_\mu} +  \underbrace{\langle u_n | i \partial_{k_\mu} | u_n \rangle}_{\mathcal{A}^\mu_{n}} \right] \delta(\mathbf{k} - \mathbf{k}')
$$

Here $|u_n\rangle$ is the periodic part of the Bloch wavefunction, related to the Bloch wavefunction by $|\psi_{n\mathbf{k}}\rangle = e^{i \mathbf{k} \cdot \mathbf{r}} | u_{n\mathbf{k}} \rangle$; in the following formulas we may omit $\mathbf{k}$ without further note. It is worth mentioning, however, that none of the various definitions introduced earlier required the system to be a periodic lattice system, so for the most general systems we can also define quantum geometry — for example many-body systems with interaction/disorder, or even some non-periodic systems such as quasicrystals. You may refer to some of my earlier notes.

> 🔗 *【link: how to distinguish insulator from metal with quantum geometry?】*

This once again reflects the universality of quantum geometry: its most fundamental physical picture and geometric meaning do not change just because the system is non-periodic.

This formula contains a highly singular derivative of a delta function, and also a piece that is precisely the Berry connection of the n-th band. In modern polarization theory we know this corresponds to the polarization (that is, the expectation value of the position operator) in a periodic lattice system. Although we just said that this is a quantity tied to the arbitrary choice of coordinates, this does not mean it is entirely useless. In modern polarization theory, we encounter situations where applying an electric field to the lattice shifts the wavefunctions of the entire Brillouin zone simultaneously and contributes to the polarization; after one period, each wavefunction returns to its original position in momentum space, but the overall change of polarization is not necessarily zero — rather, it is given by the integral of the derivative of the Berry connection, $\Delta P = \int dk  \frac{\partial \mathcal{A}_n}{\partial k} $. Since the Berry connection, as the polarization in a periodic lattice, is defined as a quantity invariant up to a translation by a unit lattice vector, the result of the integral can be zero, or a nonzero integer multiple. This is the idea of the Thouless topological pump thought experiment, and also the origin of the topological insulator. In addition, the Berry curvature can be written as the antisymmetric form of the derivative of the Berry connection, $\Omega^{\mu\nu}_n = \partial_{k_\mu} \mathcal{A}^\nu_n - \partial_{k_\nu} \mathcal{A}^\mu_n$, which indirectly shows that although the Berry connection is tied to the arbitrary choice of coordinates, it also carries important physical meaning.

Since we are more concerned with physical quantities, we are naturally more interested in gauge-invariant quantum geometry and its related observables. But in the previous definitions, what we frequently encountered were operations that directly differentiate the wavefunction, $\partial_a |\psi\rangle$, as well as the various matrix elements $A_{nm} \equiv \langle \psi_n | \hat{A} | \psi_m \rangle$ in response functions — none of which are gauge invariant.

Nevertheless, when defining the Berry curvature, quantum metric, quantum connection, and ultimately computing the quantum geometric observables, we tried to ensure the gauge invariance of the formulas (the proof is left as an exercise). There must be a step in between where gauge-dependent quantities are assembled into gauge-invariant ones. To make this step more convenient, some recent papers have begun to introduce the projector formalism or similar methods, ensuring gauge invariance of the formulas from the very level of the derivation. For example, the projection operator $\hat{P}_n$ of the n-th band is defined as:

$$
\hat{P}_n = |\psi_n\rangle \langle \psi_n|
$$

Although the wavefunction (ket and bra) acquires an extra phase under a gauge transformation, the phases of the two cancel within the projector, which gives the projector operator itself its gauge invariance. The projector $\hat{P}_n$ then contains just as much physical information as the wavefunction $|\psi_n\rangle$, but it remains gauge invariant after we perform differentiation/derivative operations on it. This is very advantageous, allowing us to keep only gauge-invariant terms during the derivation, without having to derive a pile of gauge-dependent matrix elements and then figure out how to assemble a gauge-invariant term — let alone a purely geometric term.

This is the charm of the projector formalism. Under this formalism, the quantum metric, Berry curvature, and quantum geometric tensor can be written as:

$$
g^{\mu\nu}_n = \frac{1}{2} \operatorname{tr}[\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]
$$

$$
\Omega^{\mu\nu}_n = i \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n] - (\mu \leftrightarrow \nu)
$$

$$
Q^{\mu\nu}_n = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \hat{P}_n]
$$

Interested readers can prove this themselves or refer to:

> 🔗 *【link: Projector formalism paper】*

The projector formalism has further benefits. For example, for the quantum geometry of a degenerate point/band, we cannot directly copy the single-band quantum geometry formulas, but we can directly generalize the projector to a d-band projector:

$$
\hat{P}_n = \sum_{i = 1}^{d} |\psi_{n,i}\rangle \langle \psi_{n,i}|
$$

where d is the degeneracy.

Going further, we can also regard this projector as the density matrix of a pure state, and even replace the momentum $\mathbf{k}$ with other parameters, thereby constructing quantum geometry based on the density matrix for pure states and even mixed-state/finite-temperature systems. This is fairly common in the formalism of open quantum systems and quantum information; we will explain it in more detail in the next section and leave it at that for now.

### Higher Order Quantum Geometry

Since the quantum geometric tensor defines the dipole-dipole moment of the wavefunction in real space, $\langle \Delta r^\mu \Delta r^\nu \rangle_n$, as well as the geometric tensor defined by the second-order momentum derivative in reciprocal space, $\langle \nabla_{k_\mu} \nabla_{k_\nu}\rangle_n$, we can naturally consider more combinations of dipole/momentum derivatives, thereby obtaining higher-order quantum geometric quantities, e.g. the quantum connection, torsion tensor, Riemann curvature, etc.

Taking the quantum connection as an example, the single-band quantum connection can be written as:

$$
Q^{\mu;\nu\rho}_n = \operatorname{tr} \left[ \hat{P}_n\partial_\mu \hat{P}_n \partial_\nu \partial_\rho \hat{P}_n \right]
$$

Here we write it directly in the projector formalism form, which also guarantees the gauge invariance of the expression.

There is also a class of higher-order geometric quantities that come from directly differentiating lower-order geometric quantities, for example the Berry curvature dipole $\partial_\rho \Omega^{\mu\nu}_n$ and the quantum metric dipole $\partial_\rho g^{\mu\nu}_n$. They may appear in higher-order response functions such as nonlinear response.

The quantum connection is also closely related to the Berry curvature/quantum metric dipole:

$$
\partial_\rho g^{\mu\nu}_n = \operatorname{Re} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right]
$$

$$
\partial_\rho \Omega^{\mu\nu}_n = -2 \operatorname{Im} \left[ Q^{\mu;\rho\nu}_n - Q^{\nu;\rho\mu}_n \right]
$$

We see that the quantum metric/Berry curvature dipole also correspond to the symmetric and antisymmetric parts under $\mu \leftrightarrow \nu$ of the quantum connection $Q^{\mu;\rho\nu}$.

### Multi-band Quantum Geometry

If we look carefully at the quantum geometric tensor of the n-th band, we find that each summed term $r^{\mu}_{nm} r^{\nu}_{mn}$ is, as a whole, also gauge invariant; it corresponds to the 2-band dipole-dipole transition matrix element restricted to the n-th band and the m-th band only. In fact, $r^{\mu}_{nm} r^{\nu}_{mn}$ appears frequently in various response functions, whereas its unweighted summed form over all bands, $\sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn}$, does not appear nearly as often. Since the 2-band dipole-dipole transition matrix element is itself gauge invariant, we often settle for using the quantum geometric tensor defined on two bands

$$
Q^{\mu\nu}_{nm} = r^{\mu}_{nm} r^{\nu}_{mn} = g^{\mu\nu}_{nm} - i \Omega^{\mu\nu}_{nm}
$$

Here $m \neq n$. We find that $r_{mn}^\mu = \langle u_m | i \partial_\mu | u_n \rangle$ also frequently participates, but this off-diagonal dipole matrix element is itself not a gauge-invariant quantity, so we can construct a "tangent vector" operator $\hat{e}^\mu_{mn}$ (for details, see Ahn's paper)

$$
\hat{e}^\mu_{mn} = |u_m \rangle r_{mn} \langle u_n|
$$

Although $r_{mn}$ itself is gauge dependent, the operator $\hat{e}^\mu_{mn}$ is itself gauge invariant, and this operator carries the physical meaning of a "tangent vector": it is the projection, onto the direction of $|u_m\rangle$, of the shift of the state $|u_n\rangle$ as $\mathbf{k} \rightarrow \mathbf{k} + d\mathbf{k}$ (as $d\mathbf{k}$ becomes infinitesimal it approaches the tangent direction, which is why we call it a "tangent vector").

In this way, various 2-band quantum geometric quantities can be written in a trace form similar to that of the projector operator, for example:

$$
Q^{\mu\nu}_{nm} = - \operatorname{tr}[\hat{e}^\mu_{mn}\hat{e}^\nu_{nm}]
$$

Correspondingly, there is also the 2-band quantum connection:

$$
C^{\alpha\beta\gamma}_{nm} = \operatorname{tr} \left[ \hat{e}^\alpha_{mn} \partial_\beta\hat{e}^\gamma_{nm} \right]
$$

Since the "tangent vector" operator is itself gauge invariant, it can also be expressed in the projector operator form:

$$
\hat{e}^\alpha_{mn} = i \hat{P}_m (\partial_\alpha \hat{P}_n) \hat{P}_n
$$

In this way, the 2-band quantum geometric tensor can be written as:

$$
Q^{\mu\nu}_{nm} = \operatorname{tr}[\hat{P}_n\partial_\mu \hat{P}_m \partial_\nu \hat{P}_n]
$$

The 2-band quantum connection can also be written as:

$$
C^{\alpha\beta\gamma}_{nm} = \operatorname{tr} \left[ \hat{P}_n \partial_{\beta} \hat{P}_m \left( \partial_{\alpha} \partial_{\gamma} \hat{P}_n + \partial_{\alpha} \hat{P}_m \partial_{\gamma} \hat{P}_n \right) \right]
$$

For a detailed derivation, refer to:

> 🔗 *【link: Projector formalism paper】*

When the system has only 2 bands (a 2-dimensional Hilbert space), since the eigenstates of the two bands are orthogonal within the 2D space, knowing one means knowing the other; in this case the 2-band quantum geometry contains the same information as the 1-band quantum geometry. Therefore, in responses described by 2-band quantum geometry, when the system has only two bands, the response can reduce to one described by single-band quantum geometry. For example, the quantized injection conductivity holds only in 2-band systems, precisely because the quantized circular injection conductivity is in fact the sum of all 2-band quantum geometric tensors, whereas the Chern number quantization holds only for the single-band Berry curvature. For details, refer to the original paper:

> 🔗 *【link: quantized circular injection conductivity】*

## What Does Quantum Geometry Mean?

Packaging matrix elements into the quantum geometric tensor, and thereby understanding various physical quantities, offers many advantages.

The first is that it lets us more conveniently use physical intuition to understand the physical/geometric meaning of various quantities. For example, the connection between the anomalous Hall effect and the Berry curvature can be understood through the anomalous motion contributed by the self-rotation of the wave packet. At the same time, these geometric quantities are also intrinsic properties of the material/system being studied, which is enormously helpful for understanding and tuning the physical systems we care about. We no longer need to laboriously understand how to tune more granular quantities such as energies/wave functions/observable matrix elements, which may even carry gauge dependence; instead we only need to focus on the neatly packaged, material-intrinsic quantum geometric properties.

The second is that, through the connection to geometry/topology, we can obtain some interesting identities/inequalities for quantum systems. The most important example is that the quantized Hall conductivity of the quantum (anomalous) Hall effect corresponds to the quantized Chern number of the topologically nontrivial bands of the system:

$$
\sigma_{xy} = \frac{e^2}{h} C = \frac{e^2}{h} \int_{BZ} d^dk \Omega^z(k)
$$

Even when we cannot obtain a quantized geometric quantity like the quantized Hall conductivity, we can still obtain some interesting identities/inequalities. For example, the previously mentioned geometric bound $\operatorname{tr} g  \geq 2 |\Omega^{xy}|$ hints that any physical quantity proportional to the quantum metric is "backstopped" by the Berry curvature (Chern number), which gives a lower bound on the geometric response of topologically nontrivial systems.

### Quantum Geometric Response

Let us start from the physics and think about how quantum geometric quantities enter the response function of a physical system.

For a system driven by an electric field, we previously discussed the expression for the transition rate:

$$
\mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2}  r^\mu_{mn} r^\nu_{nm}  \delta(\omega - \omega_{mn}) E^\mu \bar{E}^\nu
$$

As mentioned before, combining the transition rate with different physical quantities can produce different geometric responses. Here we give a more detailed discussion:

(i) $\mathcal{I}_{m \leftarrow n} \times \text{1}$: Transition Rate

The previous section essentially made this clear: in order to assemble the expression for the quantum geometric tensor $Q^{\mu\nu}_{n} = \sum_{m \neq n} r^{\mu}_{nm} r^{\nu}_{mn}$, we first integrate out the delta function $\delta(\omega - \omega_{mn})$, and then sum over all bands that can possibly be excited to, so that the total transition rate is proportional to $Q^{\mu\nu}$:

$$
\mathcal{I}_{n}^{tot} = \int d\omega \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}_{n}  E^\mu \bar{E}^\nu
$$

Going further, for linearly polarized light (linear polarization), i.e. $\mathcal{I}_{n}^{tot,\updownarrow}$, it corresponds to the $\mu \leftrightarrow \nu$ symmetric part of the quantum geometric tensor, i.e. the quantum metric; while for circularly polarized light (circular polarization), we consider the difference between left-handed and right-handed light, i.e. $\mathcal{I}_{n}^{tot,\circlearrowleft} - \mathcal{I}_{n}^{tot,\circlearrowright}$, which corresponds to the $\mu \leftrightarrow \nu$ antisymmetric part of the quantum geometric tensor, i.e. the Berry curvature. The reader may choose the following amplitudes to verify this for themselves (note the complex conjugate in the expression):

$$
\mathbf{E}_{\updownarrow}(\omega) = (1,0,0),\,\mathbf{E}_{\circlearrowleft/\circlearrowright}(\omega) = \frac{1}{\sqrt{2}} (1,\pm i,0)
$$

For a detailed derivation, one may refer to the appendix of the author's review paper, or to Ahn's paper:

> 🔗 *【link: Ahn's paper】*

> 🔗 *【link: My review paper】*

Going one step further, this integral expression tells us that if we excite the system with $I(\omega) \propto |\mathbf{E}(\omega)|^2$ distributing power uniformly across frequency, then the total transition rate of the system is proportional to the quantum geometric tensor.

Note also that we did not explicitly write out $\mathbf{k}$, which means this result is valid for any system; for a band system we only need to add a $\mathbf{k}$ integral $\int_{BZ} d^D\mathbf{k}$. From here on, unless otherwise stated, we omit the $\mathbf{k}$ integral to emphasize the universality of our results.

This method—integrating some response function over frequency (with a weighting) to obtain an intrinsic physical property of the system—is generally called a sum rule. It reflects in the response certain intrinsic characteristics of the system, such as quantum geometric quantities. The greatness of the sum rule lies in the fact that it corresponds entirely to the intrinsic properties of the system's (ground state/equilibrium state) and is independent of the excited states.

(ii) $\mathcal{I}_{m \leftarrow n} \times (E_m - E_n)$: Joule Heat

The essence of Joule heat is the dissipation of energy under an electric field, with energy transferred from the electromagnetic field into the quantum system, so that particles in the quantum system are continually excited from the ground state $n$ to the excited state $m$, and then return to the ground state through various relaxation processes, with the energy dissipated as heat (transferred to other degrees of freedom such as phonons).

First, multiplying the transition rate by "the energy difference from the $m$-th band to the $n$-th band" $\omega_{mn} = E_m - E_n$ gives the energy transfer rate from the $n$-th band to the $m$-th band; then summing over all bands that can possibly be excited gives the total energy transfer rate, which in the steady state coincides with the Joule heat:

$$
\begin{aligned}
\mathcal{P}_{Joule}(\omega) & = \sum_{m \neq n} \mathcal{I}_{m \leftarrow n} (\omega) \omega_{mn} \\
& = \frac{2\pi e^2}{\hbar^2} \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \omega_{mn} \delta(\omega - \omega_{mn})E^\mu \bar{E}^\nu \\
& = \frac{2\pi e^2}{\hbar^2} \omega \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \delta(\omega - \omega_{mn}) E^\mu \bar{E}^\nu
\end{aligned}
$$

Here $\mathcal{P}$ denotes power (per unit volume). In the last step, we used the property of the delta function to replace $\omega_{mn}$ by $\omega$. At this point we could already replace $r^\mu_{nm} r^\nu_{mn}$ with the 2-band quantum geometric tensor $Q^{\mu\nu}_{nm}$ to claim that the Joule heat is quantum geometric, but compared to 2-band quantum geometry we prefer to assemble a single-band quantum geometric quantity.

Let us consider the expression for the linear conductivity $\sigma^{\mu\nu}(\omega)$:

$$
j^\mu(\omega) = \sigma^{\mu\nu}(\omega) E^\nu(\omega)
$$

From the Joule heat formula, it is not hard to obtain:

$$
\mathcal{P}_{Joule}(\omega) = \operatorname{Re} \left[ j^\nu(\omega) \bar{E}^\nu(\omega) \right] = \sigma^{\mu\nu}_{\text{dis}} (\omega) E^\mu(\omega) \bar{E}^\nu(\omega)
$$

Here "dis" can be understood as the current response that has no phase difference with the electric field $E$, i.e. the current response is in phase with the electric field. Because a current response that differs by $\pi/2$ gives zero power when dotted with the electric field, it is not hard to prove:

$$
\sigma^{\mu\nu}_{\text{dis}}(\omega) = \frac{1}{2} \left[ \sigma^{\mu\nu}(\omega) + \bar{\sigma}^{\nu\mu}(\omega) \right]
$$

That is, the dissipative linear conductivity includes the real part of the longitudinal component and the imaginary part of the transverse component.

Comparing the two Joule heat formulas, it is not hard to obtain:

$$
\sigma^{\mu\nu}_{\text{dis}}(\omega) = \frac{2\pi e^2}{\hbar^2} \omega \sum_{m \neq n} r^\mu_{nm} r^\nu_{mn} \delta(\omega - \omega_{mn})
$$

Next, we can use the expression for the linear conductivity to assemble the expression for the quantum geometric tensor. Here there is an extra factor of $\omega$; multiplying by an additional $\frac{1}{\omega}$ and then integrating over all $\omega$ yields the expression for the quantum geometric tensor:

$$
\int d\omega \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}
$$

This is another kind of sum rule, which tells us that integrating the dissipative linear conductivity over frequency with a $\frac{1}{\omega}$ weighting is proportional to the system's quantum geometric tensor. Here we have also omitted the step of summing over all occupied bands, $Q^{\mu\nu} \equiv \sum_{n \in \text{occ}} Q^{\mu\nu}_{n}$, which is left for the reader to fill in. It is not hard to see that this is yet another example of a sum rule connecting a "ground-state property" with a "physical response." As an aside, this sum rule is also called the SWM sum rule; it was proposed to distinguish conductors from insulators, and more details can be found in my earlier note:

> 🔗 *【link: insulator or metal】*

It is worth mentioning that for the linear conductivity there is also another, unweighted, optical f-sum rule:

$$
\int d\omega \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}
$$

where $\mathcal{D}$ is called the Drude weight; it is related to the system's carrier density $n$ and electron mass $m$, is an intrinsic quantity of the system, and is determined entirely by fundamental physical quantities. The electron mass here is not exactly the bare electron mass, but the effective mass, which depends on the upper cutoff of the frequency integral in our sum rule, i.e. the range of energy scales we consider. As it tends to infinity, considering all core electron states and free states, it becomes the bare electron mass $m_e$; otherwise it is only the effective mass $m^*$ within the considered range of energy scales. This does not detract from the importance of the sum rule, however, since it is still an intrinsic property of the system. We will return to this when we discuss other sum rules and universal bounds later; here it is only mentioned in passing.

For anisotropic systems, the effective mass can be a tensor, and the corresponding Drude weight can also be a tensor, with the corresponding sum rule being:

$$
\int d\omega \sigma^{\mu\nu}(\omega) = ne^2 \left[\frac{1}{m} \right]^{\mu\nu} \equiv \mathcal{D}^{\mu\nu}
$$

where $m$ is a tensor, and the corresponding $\mathcal{D}$ is also a tensor.

Furthermore, from the conductivity we can obtain more useful properties, such as the capacitivity, dielectric constant, and refractive index. These properties are all related to the system's electric polarization $P$ response to the electric field, and the electric polarization and the current differ only by a time derivative $\frac{d}{dt}$ (in the frequency domain, by a factor of $i\omega$):

$$
j^a(\omega) = \sigma^{ab} (\omega) E^b (\omega) = \left( \frac{d P^a}{d t} \right)(\omega) = i \omega P^a (\omega)
$$

The susceptibility $\chi^{ab}$ is defined as the ratio of the electric polarization $P^a$ to the electric field $E^b$:

$$
P^a = \chi^{ab} E^b
$$

After comparison, it is not hard to see that the susceptibility and the conductivity differ only by a factor of $i\omega$:

$$
\chi^{ab} (\omega) = \sigma^{ab} (\omega) / i \omega
$$

Combining with the previous sum rule, we conjecture an analogous relation

$$
\int d\omega \chi^{ab} \sim Q^{ab}
$$

In fact, the sum rule related to the susceptibility is somewhat more complicated; for details one may refer to the papers from Raquel's group. But we can grasp the relation between conductivity and susceptibility, and thereby get a feel for the influence of quantum geometry on the susceptibility. Going one step further, the relation between the dielectric tensor $\epsilon$ and the susceptibility $\chi$ is:

$$
\epsilon = 1 + \chi
$$

The relation between the refractive index and the dielectric tensor is:

$$
n = \sqrt{\epsilon}
$$

From this, the reader can also readily get a feel for the influence of quantum geometry on the dielectric constant and the refractive index. To put it more bluntly:

The more topologically nontrivial a system is, the larger its refractive index must be.

Why does diamond sparkle so brilliantly? Because diamond is an obstructed atomic insulator: its nontrivial topology/quantum geometry gives it a higher refractive index, so that light reflects more times inside it, making it appear more brilliant.

This is an example Raquel often uses in talks. Although somewhat crude, it nonetheless reflects to some degree the pervasive, all-encompassing influence of quantum geometry on every aspect of physical response. We will revisit this example later when we discuss the geometric bound; here we leave it at that.

(iii) $\mathcal{I}_{m \leftarrow n} \times (v_m - v_n)$: Velocity Shift

Next we consider how Quantum Geometry enters Nonlinear Optical Conductivity, in particular the Injection Current.

The physical picture of the Injection Current is very intuitive: illumination drives an electron from Band $n$ to Band $m$, and if the post-transition group velocity $v_m$ differs from the original group velocity $v_n$, a current that grows linearly in time (or saturates in steady state) is produced, namely the Injection Current. Multiplying the Transition Rate by the velocity difference $\Delta v = v_m - v_n = \nabla_k \omega_{mn}$ gives the Injection Rate.

For Linearly Polarized Light, this response is called the Linear Photogalvanic Effect (LPGE), while for Circularly Polarized Light it is called the Circular Photogalvanic Effect (CPGE).

Interestingly, for a system with only two bands, the CPGE is Quantized. The mathematical reason behind this is that its response function can be written directly as an integral of the Quantum Geometric Tensor. As in the formula fragment given above:

$$
\sigma_{\mathrm{inj}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} Q^{ab} (\partial_{k_c} \omega_{mn}) \delta(\omega - \omega_{mn})
$$

Here $Q^{ab}$ usually corresponds to the Quantum Metric part (for Linear Polarization) or the Berry Curvature part (for Circular Polarization). More specifically, for the CPGE, the response function is proportional to $\int d^dk \Omega \cdot \Delta v$. More generally, we can write the integral on the constant-energy surface $S_k$ satisfying the resonance condition $\omega = \omega_{mn}(k)$:

$$
\sigma_{\mathrm{inj}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{S_k=\{k|\omega = \omega_{mn}(k)\}} dS_k^c Q^{ab} 
$$

This means that the Injection Current essentially probes the distribution of Quantum Geometry on the resonance surface. In the 2-band model, since both $\Delta v$ and $\Omega$ are determined by the parameters of the Hamiltonian, this integral is topologically quantized under certain conditions, giving the quantized CPGE in the 2-band system.

(iv) $\mathcal{I}_{m \leftarrow n} \times (r_m - r_n)$: Positional Shift

If the Injection Current arises from a "difference in velocity," then the Shift Current arises from a "jump in position."

In classical physics, an electron transition is an instantaneous process and the position does not change. But in quantum mechanics, the electron exists as a wavefunction, and during the transition from Band $n$ to Band $m$ the "Center of Charge" of the wavepacket undergoes a real-space displacement, which is called the Shift Vector $R_{mn}$.

The Shift Current is one of the main contributions to the Bulk Photovoltaic Effect (BPVE), especially in non-centrosymmetric materials. Its expression involves a higher-order geometric quantity:

$$
\sigma_{\mathrm{shift}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} r_{nm}^a r_{mn}^b R_{mn,a}^c \delta (\omega - \omega_{mn}) + (a,\omega \leftrightarrow b,-\omega)
$$

The core quantity here, the Shift Vector $R_{mn}$, is defined as:

$$
R_{mn}^a = \mathcal{A}_{mm}^a - \mathcal{A}_{nn}^a - \nabla_{k_a} \arg(r_{mn})
$$

It is the difference of the Berry Connections minus the gradient of the phase of the transition dipole moment. Although the Berry Connection itself is Gauge dependent, the Shift Vector as a whole is a Gauge Invariant real-space displacement.

This response is closely related to the Quantum Connection (Christoffel symbols in Hilbert space) we mentioned earlier:

$$
\sigma_{\mathrm{shift}}^{ab;c} (\bar{\omega} ; \omega, -\omega) \propto \int_{\mathbf{k}} C_{bca} \delta (\omega - \omega_{mn})
$$

where the Quantum Connection $C_{abc}$ links different geometric quantities:

$$
C_{abc} = -i \sum_{\substack{n \in \text{occ} \\ m \in \text{unocc}}} R_{mn}^{a,b} r^{c}_{nm} r^{b}_{mn}
$$

Physically, the Shift Current can be understood as a "geometric slip" of electrons in real space induced by optical pumping. Unlike the Injection Current, which depends on the carrier group velocity (and is therefore limited by the relaxation time $\tau$), the Shift Current is a purely quantum-geometric effect that, in theory, does not depend on the relaxation time, giving it enormous potential in ultrafast optoelectronic response devices.

(v) Nonlinear Transport Conductivity

Having discussed the high-frequency optical response, let us turn our attention back to the low-frequency and even DC Transport process.

In the Transport regime ($\omega \to 0$ or $\omega \tau \ll 1$), the physical picture changes: we can no longer simply apply the Fermi Golden Rule, but must take seriously the relaxation time $\tau$ introduced by impurity scattering. Interestingly, here $\tau$ is not merely a constant; Semiclassical theory tells us that by analyzing the power-law dependence of the conductivity on $\tau$ (the Scaling Law), we can peel away the different geometric contributions one layer at a time, like peeling an onion.

According to semiclassical theory, the current density is defined as $j = -e \sum_n \int [dk] f_n v_n$. Under the electric-field perturbation, we expand the distribution function $f_n$ and the velocity $v_n$ in orders of the electric field:

Distribution function: $f_n = f_n^{(0)} + f_n^{(1)} + f_n^{(2)} + \dots$, where $f_n^{(l)} \propto (e\tau E \cdot \nabla_k)^l f_n^{(0)} \propto \tau^l$.

Velocity: $v_n = v_n^{(0)} + v_n^{(1)} + v_n^{(2)} + \dots$. Here $v_n^{(0)}$ is the conventional group velocity; $v_n^{(1)}$ contains the anomalous-velocity correction from the Berry Curvature, with the full expression: $v_n = \frac{1}{\hbar} \frac{\partial \epsilon_n}{\partial \mathbf{k}} - \frac{e}{\hbar} \mathbf{E} \times \mathbf{\Omega}_n$.

This perturbation expansion can decompose the transport conductivity of any order $n$ into different geometric contributions. Moreover, the different terms have different powers of the relaxation time $\tau$, so we can use the scaling law to peel out the contributions of the different quantum-geometry terms.

Before entering the second-order effects, let us quickly review the familiar first-order linear response $j^{(1)}$:

$$
j^{(1)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(1)} v_n^{(0)}}_{\text{Drude}} + \underbrace{f_n^{(0)} v_n^{(1)}}_{\text{Anomalous Hall}} \right)
$$

Drude Conductivity (longitudinal current): the term $f_n^{(1)} v_n^{(0)}$. This is the classical drift of electrons under the balance between electric-field acceleration and impurity scattering. Using the relaxation-time approximation $f_n^{(1)} \approx e \tau (\mathbf{E} \cdot \mathbf{v}_n) (-\partial_\epsilon f_0)$, we obtain the classical Drude conductivity formula:

$$
\sigma_{ab}^{\text{Drude}} = e^2 \tau \sum_n \int [dk] \left(-\frac{\partial f_n^{(0)}}{\partial \epsilon}\right) v_n^a v_n^b
$$

This is entirely determined by the band dispersion (group velocity $v_n$) and the scattering time $\tau$, and is a dissipative transport process.

Intrinsic Anomalous Hall Effect (transverse current): the term $f_n^{(0)} v_n^{(1)}$. Here $f_n^{(0)}$ is the equilibrium Fermi distribution, and $v_n^{(1)} = -\frac{e}{\hbar} \mathbf{E} \times \mathbf{\Omega}_n$ is the anomalous velocity produced by the Berry Curvature (i.e., the imaginary part of the quantum geometry). This term gives the famous intrinsic anomalous Hall conductivity:

$$
\sigma_{xy}^{\text{AHE}} = -\frac{e^2}{\hbar} \sum_n \int [dk] f_n^{(0)} \Omega_n^z
$$

This shows that the Hall current is directly proportional to the integral of the Berry Curvature over the occupied bands. It is an intrinsic effect determined solely by the topological-geometric properties of the bands, independent of the scattering time $\tau$ ($\tau^0$), and is dissipationless.

Similarly, for the second-order nonlinear current $j^{(2)}$ that we care about, it naturally decomposes into three terms, each corresponding to a different physical mechanism:

$$
j^{(2)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(2)} v_n^{(0)}}_{\text{NLD}} + \underbrace{f_n^{(1)} v_n^{(1)}}_{\text{BCD}} + \underbrace{f_n^{(0)} v_n^{(2)}}_{\text{QMD}} \right)
$$

The first term, Nonlinear Drude (NLD) ($\tau^2$), is the most "classical" nonlinear conductivity, corresponding to the coupling of the second-order distribution-function correction with the zeroth-order velocity ($f_n^{(2)} v_n^{(0)}$). It essentially originates from the non-parabolicity of the bands, with conductivity formula:

$$
\sigma_{ab;c}^{\text{NLD}} = \frac{e^3 \tau^2}{\hbar^3} \sum_n \int [dk] f_n \frac{\partial^3 \varepsilon_n}{\partial k_a \partial k_b \partial k_c}
$$

The second term is the Berry Curvature Dipole (BCD) ($\tau^1$), first proposed by Sodemann and Fu. It corresponds to the coupling of the first-order distribution-function correction with the first-order anomalous velocity ($f_n^{(1)} v_n^{(1)}$). The physical picture is: if the system has time-reversal symmetry ($T$-symmetry) but breaks spatial-inversion symmetry ($P$-broken), then although the total Chern number is zero, near the Fermi surface the distribution of the Berry Curvature $\Omega(k)$ can be non-uniform, forming a "dipole." Its conductivity formula also reflects the dipole nature of the Berry Curvature:

$$
\sigma_{ab;c}^{\text{BCD}} = \frac{e^3 \tau}{\hbar^2} \sum_n \int [dk] f_n \left( \frac{\partial \Omega_{n}^{bc}}{\partial k_a} + \frac{\partial \Omega_{n}^{ac}}{\partial k_b} \right)
$$

The third term is the Quantum Metric Dipole (QMD) ($\tau^0$), corresponding to the coupling of the zeroth-order distribution function (equilibrium) with the second-order velocity ($f_n^{(0)} v_n^{(2)}$). When the system breaks time-reversal symmetry ($T$-broken, e.g., a magnetic system), this kind of nonlinear current that is completely independent of $\tau$ ($\tau^0$ order) appears. This means it is an intrinsic effect, in theory extremely insensitive to impurity scattering. Its origin is precisely the dipole distribution of the Quantum Metric in momentum space:

$$
\sigma_{ab;c}^{\text{QMD}} = \frac{e^3}{\hbar} \sum_n \int [dk] f_n \left( 2 \frac{\partial G_{n}^{ab}}{\partial k_c} - \frac{1}{2}\left(\frac{\partial G_{n}^{bc}}{\partial k_a} + \frac{\partial G_{n}^{ac}}{\partial k_b}\right) \right)
$$

Here the quantum metric $G_{n}^{ab}$ is essentially the band-normalized quantum metric: $G_{n}^{ab} = \sum_{m \neq n} \frac{ r^a_{nm} r^b_{mn} + r^b_{nm} r^a_{mn} }{\epsilon_{nm}}$, which can be regarded as the 2-band quantum geometry $g_{nm}^{ab}$ weighted by the inverse energy gap $\epsilon_{nm}^{-1}$.

The formulas in this text are based on Daniel Kaplan's PRL; in fact, deriving them via the density matrix, many-body Feynman diagrams, or semiclassical wavefunctions, or using different gauges (length gauge $\hat{H}' = \hat{\mathbf{r}} \cdot \mathbf{E}$, velocity gauge $\hat{H}' = \hat{\mathbf{p}} \cdot \mathbf{A}$), will yield differences in detail, and many papers have attempted to unify the QMD coefficient. If one considers higher-order disorder corrections and other "extrinsic" effects (such as skew scattering, side-jump, etc.), the results at nonlinear order become even more complicated.

This complexity arises because, at higher orders, the lifetime effects in the different virtual processes become more subtle, and using the same $\tau$ in all terms is not entirely equivalent; even swapping the order of $\tau$ and the response order may give different physical predictions. For example, for $\omega \rightarrow \omega + i/\tau$, in linear response the single $\tau$ can be treated uniformly, but at nonlinear order (e.g., $\omega_1 + \omega_2$), whether the compensation should be $\omega_1 + \omega_2 + i/\tau$, $\omega_1 + \omega_2 + 2i/\tau$, or some other form, there is currently no unified conclusion. Of course, one can also abandon the relaxation-time approximation and directly compute all disorder diagrams, but that leads to extremely complicated expressions with many parameters, making it very difficult for realistic material calculations.

Although the specific QMD coefficient varies among different treatments, at least at $\tau^0$ order the main structure is proportional to the quantum metric dipole $\partial_c G_{n}^{ab}$.

This perturbation theory can also be extended to third-order transport ($j^{(3)}$) and even higher orders, with the form still being a decomposition into the coupling of each order's distribution-function correction with the velocity correction:

$$
j^{(3)} = -e \sum_n \int [dk] \left( \underbrace{f_n^{(3)} v_n^{(0)}}_{\text{Drude } (\tau^3)} + \underbrace{f_n^{(2)} v_n^{(1)}}_{\text{BC Quadrupole } (\tau^2)} + \underbrace{f_n^{(1)} v_n^{(2)}}_{\text{Geometric } (\tau^1)} + \underbrace{f_n^{(0)} v_n^{(3)}}_{\text{Intrinsic } (\tau^0)} \right)
$$

Specifically, each term corresponds to a different geometric physical mechanism:

* $\tau^3$ (3rd order Drude): originates from the higher-order non-parabolicity of the bands (Jerk current), mainly the classical background-signal part.

* $\tau^2$ (Berry Curvature Quadrupole): corresponds to $f_n^{(2)} v_n^{(1)}$. Just as the first-order AHE corresponds to the "monopole" (average) of the Berry Curvature and the second-order BCD corresponds to the "dipole," the third-order response further probes the quadrupole distribution of the Berry Curvature.

* $\tau^1$ (Quantum Metric Quadrupole): corresponds to $f_n^{(1)} v_n^{(2)}$. This term represents a higher-order generalization of the geometric effect of the Quantum Metric, involving the quadrupole properties of the metric field.

* $\tau^0$ (Intrinsic Geometry & Connection Dipole): corresponds to $f_n^{(0)} v_n^{(3)}$. This is a completely intrinsic response, unrelated to scattering. It should be especially noted that here "intrinsic" is not merely a simple extension of lower-order geometric quantities, but also contains entirely new higher-order geometric objects, such as the Quantum Connection Dipole. Different treatments and derivation methods may also differ in the coefficient structure of this term.

(vi) Other geometric responses

For more, please refer to other reviews; here we just pick one table at random:

![Figure: table from Tobias review](/posts/quantum-geometry-everything/fig08.png)

### Geometric Bounds & Sum Rules

Let us now turn back from physics to geometry. Since the quantum geometry we have defined is also a geometric quantity, we can think about some interesting geometric conclusions and apply them to the corresponding geometric responses to see what interesting results emerge.

Of course, the one we are most familiar with is still the Berry Curvature and the Quantum Hall Effect (QHE). Its physical essence is very concise: the quantization of the Hall conductivity $\sigma_{xy} = C \frac{e^2}{h}$ can be geometrically understood as the "quantization of the area integral" of the Berry Curvature in parameter space.

However, the implications of Quantum Geometry go far beyond this. We will discuss it along the following five dimensions:

1. Geometric Bound: review the fundamental inequality between the Metric and the Curvature, understanding it from both geometric intuition and physical intuition.
2. Sum Rule: establish the direct connection between optical-response weights and quantum-geometric quantities (especially the Quantum Metric).
3. Universal Bound: combine the above two to derive a universal upper bound in which the topological gap is limited by the fundamental electronic parameters, reflecting that the geometric constraint imposed by quantum geometry on arbitrary systems is universal.
4. Generalized Geometric Bound: generalize the geometric bound to the case of zero Berry Curvature (symmetry-protected) and to arbitrary parameter spaces.
5. Generalized Sum Rule: further discuss sum rules for higher-order frequency moments and nonlinear responses, as well as strategies for experimentally measuring sum rules using pulses.

(i) Geometric Bound

Before delving into quantum geometry, let us first review a classic geometric intuition: the Isoperimetric Inequality. It tells us that among all closed curves with a given perimeter $L$ in the plane, the circle encloses the largest area $A$ ($L^2 \ge 4\pi A$). This reveals a fundamental constraint of the "metric (length)" on the "area (curvature)."

In quantum geometry, the Quantum Metric $g$ defines the distance in Hilbert space, while the Berry Curvature $\Omega$ corresponds to the phase flux (analogous to area). Since they are essentially the length and area of geometry, there is a similar geometric constraint between them:

$$\mathrm{Tr}(g) \ge |\Omega|$$

We gave a fairly detailed derivation in a previous note; here we give a pictorial understanding:

![Figure: geometric bound](/posts/quantum-geometry-everything/fig09.png)

For more physical details about this bound, you can refer to the author's previous note:

> 🔗 Further reading: [Band Geometry & GMP Algebra in flat-band FCI](https://zhuanlan.zhihu.com/p/580954377) · [FQHE, GMP Algebra & Fractional Chern Insulator](https://zhuanlan.zhihu.com/p/574597173)

This is the geometric understanding of the geometric bound, i.e., the constraint of "length" on "area." And as we learned in the previous chapter, beyond its geometric meaning, quantum geometry also has its own physical meaning—for example, the quantum metric describes the second moment of the wavepacket $\langle \Delta \hat{r}^a \Delta \hat{r}^b \rangle$, which essentially gives the size of the wavepacket. This means that a nonzero Berry Curvature (topological nontriviality) necessarily requires the quantum state to have a nonzero "size" in parameter space, which may further affect the electron's response (the previous subsection) and interaction (the next subsection).

![Figure: topological band wavefunction](/posts/quantum-geometry-everything/fig10.png)

If we integrate over the entire Brillouin zone (BZ), the physical meaning of this inequality becomes even more profound:

$$
\int_{BZ} \mathrm{Tr}(g(\mathbf{k})) d^2k \ge \int_{BZ} |\Omega(\mathbf{k})| d^2k \ge \left| \int_{BZ} \Omega(\mathbf{k}) d^2k \right| = 2\pi |C|
$$

where $C$ is the Chern Number.

This means that a topologically nontrivial band ($C \ne 0$) is necessarily accompanied by a minimal total quantum metric (Total Quantum Metric). This can be understood more intuitively from the localization property of Wannier functions. Marzari and Vanderbilt pointed out that the gauge-invariant spread of Wannier functions is determined by the integral of the Quantum Metric over the Brillouin zone:

$$\Omega_I \propto \int_{BZ} Tr[g(\mathbf{k})] d\mathbf{k}$$

This means that the Quantum Metric sets the fundamental limit on how localized an electron can be in real space:

* For a topologically trivial band ($C=0$), we can find a gauge such that $g \to 0$, thereby constructing highly localized Wannier functions (atomic limit).

* However, for a Chern insulator ($C \neq 0$), the geometric bound $\int Tr(g) \ge 2\pi |C|$ means that the Wannier functions always have a nonzero minimum spread. (In fact, a Chern band cannot be Wannierized, i.e., one cannot Fourier transform the Bloch wavefunctions of a Chern band to obtain Wannier functions that decay exponentially in all directions. This is not hard to understand: our Chern band model has at least two bands, and it is impossible to write a 1-band tight-binding model that is also a Chern band.)

It is worth mentioning that when the inequality becomes an equality, it corresponds exactly to the ideal quantum geometry of the Landau Level, i.e., the minimum-uncertainty wavepacket case. For the quantum geometry of the Landau Level, you can refer to my previous note:

> 🔗 *【link: LL QG note】*

This shows from another angle that the physical essence of the geometric bound is rooted in the fundamental uncertainty principle of quantum mechanics
$[\hat{x}, \hat{p}] = i\hbar$

This conclusion is crucial for the study of the lattice analog of the fractional quantum Hall effect—the Fractional Chern Insulator (FCI).

In the design of FCIs, our core strategy is often to "mimic the Landau level": we try to construct a flat band with nontrivial topology in a lattice system, making its wavefunction properties as close as possible to those of the lowest Landau level (LLL) in continuous space.

The geometric bound tells us that the LLL actually represents the "perfect limit" of quantum geometry, i.e., the case where the inequality becomes an equality: $\mathrm{Tr}(g(\mathbf{k})) = |\Omega(\mathbf{k})|$, which is called the Trace Condition.

Therefore, this inequality provides a quantitative criterion for characterizing how "ideal" a topological band really is. The smaller the deviation from equality $\delta = \mathrm{Tr}(g) - |\Omega|$, the closer the band's wavefunction structure in phase space is to a holomorphic function, and thus the more favorable it is for stabilizing strongly correlated topological orders such as fractional quantum Hall states. This is also why, in systems such as magic-angle graphene, even though the Berry Curvature may not be perfectly uniform, as long as this trace condition is approximately satisfied, we can still observe robust FCI states.

In addition, in nonlinear responses there also exist similar geometric bounds. For example, the magnitude of certain coefficients of the nonlinear Hall effect or nonlinear optical responses is also constrained by the Quantum Metric or its higher-order moments.

(ii) Sum Rule

Earlier, by the method of "engineering the integral," we shaped the frequency integral of the conductivity into a quantity related to the intrinsic properties of the system; let us review it here:

1. optical f-sum rule:

$$
\int d\omega \sigma^{\mu\mu}(\omega) = \frac{ne^2}{m} \equiv \mathcal{D}
$$

2. geometric sum rule:

$$
\int d\omega \frac{\sigma^{\mu\nu}_{\text{dis}}(\omega)}{\omega} = \frac{2\pi e^2}{\hbar^2} Q^{\mu\nu}
$$

We want to point out that the reason a sum rule can give the intrinsic property of the system is that the sum rule actually reflects a kind of weight for how the system responds to an external perturbation. For example, the familiar Newton's second law $F = ma$ tells us that for an external force $F$, a system with "weight" (weight) $m$ can produce a "response," i.e., an acceleration $a$ of a certain magnitude.

It is the same here. Consider applying a pulsed electric-field signal $E(t) = E_0 \delta(t)$; the time is so short that the system instantaneously acquires an acceleration $a \propto F/m = e E_0 / m \delta(t)$. Integrating over time $t$ gives the change in velocity, $v = \int dt a = e E_0 / m$. This delta-function pulse is so fast—faster than any other dissipative force—that the electron has no time to "react" and decelerate, so we need not consider any relaxation effects. Thus the corresponding current $j = ne v = \frac{ne^2}{m} E_0$, and the corresponding conductivity is the Drude weight. This is exactly what the optical sum rule tells us: the response of the system to a delta-function pulse confirms a weighted superposition of the conductivity over the delta-function spectrum, and since the spectrum of a delta function is exactly constant, this corresponds to an unweighted (constant-weighted) superposition of all conductivities, and the result is the "weight" of the system's response to the external pulse perturbation, i.e., the "Drude weight."

The great thing about this sum rule is that, no matter what your system's relaxation time is (which ultimately affects the factor $\frac{1}{\omega + i/\tau}$ in the conductivity), the final result after integrating over frequency is independent of this extrinsic relaxation, and is completely an intrinsic property of the system itself (the Drude weight).

Similarly, we can understand the geometric sum rule as a kind of geometric weight, reflecting the system's response rate under a spectral perturbation $E(\omega) \sim \frac{1}{\omega}$. Those who often do Fourier transformations will easily guess that this spectrum corresponds to a "square-wave signal"; that is to say, the system's response to a step-function-shaped perturbation reflects another kind of intrinsic weight of the system, namely the geometric weight. For more detailed content, you can refer to Verma's paper:

> 🔗 *【link: Paper of Verma on instantaneous response】*

(iii) Universal Bound

If we combine the Geometric Bound with the Sum Rule, we arrive at a very profound result in condensed matter physics, usually called the Universal Bound.

Recently, Y. Onishi and L. Fu proposed in [Phys. Rev. X 14, 011052 (2024)](https://journals.aps.org/prx/abstract/10.1103/PhysRevX.14.011052) a universal upper bound on the topological gap (Topological Gap). This bound reveals a deep connection between the topological nature of a band, its quantum geometry, and its optical response.

The derivation is in fact just a clever combination of the geometric bound and the sum rule from the previous two sections:

1. Spectral Gap Constraint: For an insulator with a gap $E_g$, the optical absorption $\sigma(\omega)$ is nonzero only for $\omega \geq E_g$. Therefore, using the inequality $\frac{1}{\omega} \leq \frac{1}{E_g}$, we can relate the "negative first moment" of the optical conductivity (related to the dielectric constant) to its "zeroth moment" (the total spectral weight):

$$
\int_0^\infty d\omega \frac{\sigma(\omega)}{\omega} \leq \frac{1}{E_g} \int d\omega \sigma(\omega)
$$

2. f-sum Rule: According to the classic optical sum rule, the total weight of the optical conductivity is determined by the carrier density $n$ and the electron mass $m$ (independent of interactions):
   
$$
\int d\omega \sigma(\omega) = \frac{\pi n e^2}{2m}
$$

3. Geometric Bound: A nontrivial topological number (Chern number $C$) requires not only a nonzero Berry Curvature but also imposes a minimal "polarizability" or quantum-geometric requirement on the system. Studies show that the magnitude of the Chern number is bounded by the trace of the Quantum Metric (or the associated optical moment):

$$
|C| \leq \int_{BZ} \text{Tr}[g(\mathbf{k})] d\mathbf{k} \sim \int d\omega \frac{\sigma(\omega)}{\omega}
$$

Combining the three points above, we obtain a universal upper bound on the topological gap:

$$
|C| \leq \frac{\pi n e^2}{2m E_g} \implies E_g \leq \frac{\pi n e^2}{2m |C|} \times (\text{const.})
$$

This formula tells us that, for a given electron density and effective mass, the topological gap $E_g$ cannot be enlarged without limit. If we want to maintain a nonzero topological number $C$, the system must retain sufficient optical weight at low energies (i.e., sufficient quantum-geometric fluctuations).

In fact, many topological materials arise from band inversion near a band crossing, and this universal bound tells us that the gap after such an inversion cannot be enlarged indefinitely—it has an upper limit (if it could be enlarged without bound, one could push all other bands off to infinity, leaving effectively a single band, but such a 1-band Chern band model does not exist). This explains why, in many topological materials, although we would like to enlarge the gap by enhancing interactions (in order to obtain a high-temperature topological phase), the gap size is ultimately fundamentally limited by the basic electronic parameters ($n, m$). This is yet another example of how quantum geometry is intimately tied to some of the most intrinsic properties of a system.

(iv) Generalized Geometric Bound

Beyond the standard form $Tr(g) \ge |\Omega|$ discussed above, the Geometric Bound can also be generalized to other situations.

1. Geometric Bound at Zero Berry Curvature (Symmetry-Protected Geometric Bound)

The standard Geometric Bound usually relies on a nonzero Chern number (Berry Curvature). However, in many Time-Reversal Symmetric systems, the total Berry Curvature vanishes, but this does not mean that geometric effects disappear.

Herzog-Arbeitman, Bernevig, et al. [PRL 128, 087002 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.128.087002) pointed out that even when the Berry Curvature vanishes everywhere, Real Space Invariants (RSIs) can still enforce a nonzero lower bound on the Quantum Metric.

This is especially true in flat-band systems in the Obstructed Atomic Limit—that is, where the Wannier centers, although localized, are displaced from the atomic positions—where symmetry requires the wavefunction to have a certain degree of delocalization.

We can understand this with an example: for an obstructed atomic insulator, symmetry requires the Wannier center of the occupied band to sit at the bond center, meaning the Wannier function must "straddle" the atomic sites on both sides of the bond. In this way, the Wannier function of the obstructed atomic insulator acquires a symmetry-enforced spread. Since this spread (the size of the Wannier wavepacket itself corresponds to the quantum metric: $\mathrm{tr}g \sim \langle \Delta r^2 \rangle$) is enforced, this also corresponds to a symmetry-enforced bound on the (trace of the) quantum metric. And in this system, although it is an obstructed atomic insulator, it still has an atomic limit, so the Berry curvature vanishes everywhere (at least topologically trivial); this is precisely an example that goes beyond $\mathrm{tr} g \ge |\Omega|$. In fact, this bound can be defined via another class of topological index, i.e. the real space invariant (RSI). RSIs are used to distinguish special topological phases such as fragile topology, and their application in the generalized quantum geometric bound can be found in the original text of [PRL 128, 087002 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.128.087002).

2. Generalized Parameter Space and Bounds on Observables (Generalized Parameter Space)

Going further, the concept of Quantum Geometry need not be confined to momentum space $\mathbf{k}$.

Shinada and Nagaosa [arXiv:2507.12836 (2025)](https://arxiv.org/abs/2507.12836) proposed a universal framework that generalizes the Quantum Geometric Tensor (QGT) to an arbitrary parameter space $\boldsymbol{\lambda}$. By examining the response of a physical operator $\hat{O}$ to changes in the parameters, we can define a generalized metric $g_{\mu\nu}^{(\lambda)}$ and curvature $\Omega_{\mu\nu}^{(\lambda)}$.

![table: Generalized Geometric Bound](/posts/quantum-geometry-everything/fig11.png)

(v) Generalized Sum Rule

Finally, we can generalize the Sum Rule to more general situations.

1 Generalized Optical Moments

The usual optical sum rule focuses on the "zeroth moment" of the conductivity (direct integration), but we can also define the generalized moments (Generalized Moments) of the conductivity:

$W_\eta = \int_0^\infty \omega^\eta \text{Re}[\sigma(\omega)] d\omega$

Different values of $\eta$ correspond to different physical quantities, and connect to different aspects of Quantum Geometry:

* $\eta = -1$ (Dielectric Function):  corresponds to the static dielectric constant $\epsilon(0)$ or the static structure factor. This is related to the low-energy behavior of the Quantum Metric, reflecting the contribution of virtual transitions to the polarizability ($\chi \sim \ell_g^2 / \omega_g$).

* $\eta = 0$ (f-sum rule): corresponds to the total optical weight, which, as discussed above, is related to the total amount of Quantum Metric ($\int g$).

* $\eta = 1$ (Energy/Mass): corresponds to the average kinetic energy of the electrons or the optical mass renormalization.

* $\eta = 2$ (Shot Noise): related to current fluctuations.

For details one can refer to Verma's paper:

> 🔗 *【link: Verma's paper on Generalized Sum Rule】*

2 Nonlinear Sum Rule

Beyond the traditional linear response, the concept of the sum rule can also be generalized to the nonlinear regime.

Matsyshyn and Sodemann [PRL 123, 246602 (2019)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.123.246602) discovered a sum rule for the nonlinear Hall effect (second-order photocurrent), namely the Quantum Rectification Sum Rule.

Just as the sum rule of the linear optical conductivity is determined by the Quantum Metric (geometry), the frequency integral of the second-order nonlinear response is constrained by the Berry Curvature Derivative (BCD, $\partial_k \Omega$). Physically, this sum rule can be obtained by generalizing the relaxation time to be frequency-dependent: $\tau \to \frac{1}{\omega + i/\tau}$, and then integrating over frequency to obtain a nonlinear sum rule reflecting some weight of the system.

Furthermore, for the Shift Current—the main source of the bulk photovoltaic effect—a corresponding sum rule also exists. According to [Phys. Rev. Lett. 135, 066901 (2025)](https://journals.aps.org/prl/abstract/10.1103/w761-8nf7), the frequency integral of the shift conductivity is not determined solely by the Berry Connection and the Quantum Metric, but rather by a broader Multistate Geometry as well as the Skewness of the occupied states.

The frequency integral of the shift current conductivity $\sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega)$ is approximately equal to the **Third Cumulant (Skewness)** of the position operator:

$$
\int_{0}^{\infty} d\omega \sigma_{\text{shift}}^{\alpha;(\beta\gamma)}(\omega) \approx \frac{2\pi e^3}{\hbar^2} \frac{1}{V} \langle \hat{X}_{\alpha}\hat{X}_{\beta}\hat{X}_{\gamma}\rangle_{c}
$$

where:

* $\langle \hat{X}_{\alpha}\hat{X}_{\beta}\hat{X}_{\gamma}\rangle_{c}$ denotes the third-order correlation function of the position operator $\hat{X}$ on the ground-state occupied manifold (i.e. the **Skewness**).

* This term measures the **Asymmetry**, or non-Gaussianity, of the real-space distribution of the electronic wavefunction.

To understand its physical meaning, we can draw an analogy with the traditional linear optical response sum rule:

* Linear Conductivity ($\sigma^{(1)}$):
  Its sum rule (usually associated with the f-sum rule or the Souza-Wilkens-Martin formula) reflects the Second Cumulant (Variance) of the position operator:
  $\int d\omega \text{Re}\,\sigma^{(1)}(\omega) \sim \langle \hat{X}\hat{X} \rangle_c \sim g_{\alpha\beta} \text{ (Quantum Metric)}$
  This corresponds to the Quantum Metric, which physically describes the Spread/Fuzziness of the wavefunction.

* Shift Current ($\sigma^{(2)}$):
  As shown in the equation above, its sum rule reflects the Third Cumulant (Skewness) of the position operator:
  $\int d\omega \sigma^{(2)}(\omega) \sim \langle \hat{X}\hat{X}\hat{X} \rangle_c$
  This corresponds to the skewness within the Multistate Geometry, which physically describes the direction and degree of skewness of the wavefunction distribution.

Based on the above, one can derive a Hierarchy correspondence between the order of the nonlinear response and the moments of the position operator:

* Linear response ($n=1$) $\longleftrightarrow$ Second moment (Variance): corresponds to the Quantum Metric (wavefunction spread).

* Shift current ($n=2$) $\longleftrightarrow$ Third moment (Skewness): corresponds to the Multistate Geometry (wavefunction asymmetry).

* Third-order response ($n=3$) $\longleftrightarrow$ Fourth moment (Kurtosis): expected to correspond to the kurtosis (sharpness/long tails) of the wavefunction.

This new discovery revises the traditional understanding of the bound on the photovoltaic response, and offers crucial guidance for designing efficient photovoltaic materials by exploiting multistate coupling between bands.

These new sum rules reveal the intrinsic (geometric) properties of the system's ground state contained within its Dynamical Response. Usually, we think that the spectrum contains complicated information about all excited states. However, the sum rule tells us that when we integrate the response over all frequencies, the details of these excited states are "averaged out," and what remains is determined entirely by the intrinsic geometric structure of the ground-state wavefunction.

Therefore, the sum rule is not merely an experimental tool but a profound physical principle: the geometry of the system's ground state (Quantum Geometry) predetermines its overall Capacity to respond dynamically to external perturbations. Whether it is the total intensity of linear absorption or the net effect of nonlinear rectification, both are strictly locked by the geometric shape of the ground state in Hilbert space (the metric, curvature, and their derivatives).

3. Experiments to probe sum rule

Although the generalized sum rule provides rich geometric information, experimentally measuring the complete optical spectrum $\sigma(\omega)$ from zero frequency to infinity is extremely challenging. Fortunately, we can exploit Time-Frequency Duality, designing the waveform of the probe pulse to directly extract these integrated quantities without having to measure the entire spectrum.

The core of this idea is that the frequency-domain weighted integral $\int \omega^\eta \sigma(\omega) d\omega$ actually corresponds to the instantaneous or cumulative response of the system, in the time domain, to a pulse $E(t)$ of a specific waveform.

According to the work of Verma & Queiroz [PNAS 122, e2405837122 (2025)](https://www.pnas.org/doi/10.1073/pnas.2405837122) and [Phys. Rev. Lett. 134, 106403 (2025)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.134.106403), the time-dependent Quantum Geometric Tensor (tQGT) $\mathcal{Q}_{\mu\nu}(t)$ is the generating function for all geometric sum rules:

$\mathcal{S}_{\mu\nu}^\eta \equiv \int_0^\infty \frac{\text{Re}[\sigma_{\mu\nu}(\omega)]}{\omega^{1-\eta}} d\omega = \frac{\pi e^2}{\hbar} \left[ (-i\partial_t)^\eta \mathcal{Q}_{\mu\nu}(t) \right]_{t=0}$

This means we can directly obtain geometric quantities by measuring the system's Time-Domain Response to a specific pulse:

* Step Response $\to$ Quantum Metric:
  Apply a step electric field $E(t) = E_0 \Theta(-t)$ that is suddenly switched off at $t=0$. In the high-temperature (classical) limit, the subsequently measured polarization relaxation $\mathcal{P}(t)$ is directly proportional to the symmetric tQGT:
  $\mathcal{P}_\mu(t) \approx \frac{\hbar}{2 k_B T} E_\nu \mathcal{Q}^s_{\mu\nu}(t)$
  Therefore, by simply measuring the polarization at the initial instant of relaxation ($t \to 0^+$), one directly obtains the Quantum Metric $g_{\mu\nu} = \mathcal{Q}^s_{\mu\nu}(0)$.

This approach converts a complex broadband spectral measurement into a single time-point measurement or a specific waveform-response measurement, greatly simplifying the experimental probing of quantum geometry.

This means we do not need to measure the spectrum point by point; we only need to apply a specifically designed pulse shape (such as a "square wave" or "triangular wave" electric field) and measure the system's subsequent current or polarization response in order to directly "read out" the generalized geometric weight corresponding to the sum rule.

### Quantum Geometric Correlated Phases

So far we have focused on single-particle physics. In reality, quantum geometry also participates in correlated phases — particularly in multiband and flatband systems.

(i) Quantum Geometric Spontaneous Symmetry Breaking

In the flat band limit ($W \to 0$), the energy factor degenerates to the constant $1/k_BT$, and the physics is entirely controlled by the geometric form factor:

$$\chi_0(\mathbf{q}) = \frac{1}{N} \sum_{\mathbf{k}, n,m} \underbrace{\left| \langle u_{n\mathbf{k}} | u_{m\mathbf{k}+\mathbf{q}} \rangle \right|^2}_{\text{Form Factor}} \times \underbrace{\frac{f(\epsilon_{n\mathbf{k}}) - f(\epsilon_{m\mathbf{k}+\mathbf{q}})}{\epsilon_{m\mathbf{k}+\mathbf{q}} - \epsilon_{n\mathbf{k}}}}_{\text{Lindhard Factor}}$$

$$ \xrightarrow{W\to 0} \frac{1}{k_B T} \sum_{\mathbf{k}} \nu(1-\nu) \left| \langle u_{\mathbf{k}} | u_{\mathbf{k}+\mathbf{q}} \rangle \right|^2 $$

If the geometric factor favors a particular $\mathbf{q}$, so does the susceptibility, leading to the emergence of an order parameter — entirely different from the conventional, purely energy-based Fermi Surface Nesting. This is "Quantum Geometric Nesting."

(ii) Electron-Phonon Coupling

See mainly Jiabin Yu's paper.

(iii) Fractional Chern Insulator (FCI)

At its core, FCI is about emulating Landau Levels — not only in energy (flat band), but also in wavefunction (quantum geometry/topology): not just a Chern band, but one where the quantum metric and Berry curvature throughout the Brillouin zone resemble those of a Landau Level (Trace Condition).

Quantum geometry serves as the key ingredient to measure our deviation from the ideal Landau Level.

### Quantum Geometric Information Entropy

Finally, let us broaden our view from condensed matter physics to the field of quantum information. We will find that quantum geometry is also of great help in understanding quantum information, and conversely, it can even help us observe these quantum-information quantities of quantum geometry.

(i) Quantum Fisher information

In quantum information, we more often discuss the density matrix rather than pure states, so we need to generalize the concept of quantum geometry to density matrices. To do this, we similarly define a distance between density matrices, and then perform a parameter expansion of the corresponding distance to obtain the quantum Fisher information (QFI).

* In the eigenbasis of the density matrix $\rho = \sum_n p_n |n\rangle\langle n|$, by solving the above equation, the QFI can be written in the very practical spectral-decomposition form:

$$
F_Q(\lambda) = 2 \sum_{n,m} \frac{(p_n - p_m)^2}{p_n + p_m} |\langle n | \partial_\lambda \rho | m \rangle|^2
$$

Returning to pure states: the correspondence with the Quantum Metric
This formula looks complicated, but if we take the pure-state limit ($T \to 0$), i.e. some state has $p_0=1$ and all the rest have $p_{n \neq 0}=0$, something magical happens:

1. In the sum, terms survive only when $n=0, m\neq 0$ (or vice versa), where the denominator $p_n+p_m = 1 \neq 0$.
2. In this case the coefficient is $\frac{(1-0)^2}{1+0} = 1$.
3. Taking into account $\partial_\lambda \rho = |\partial_\lambda \psi\rangle\langle\psi| + |\psi\rangle\langle\partial_\lambda \psi|$, we can derive:

$$
F_Q = 4 \left( \langle \partial_\lambda \psi | \partial_\lambda \psi \rangle - |\langle \psi | \partial_\lambda \psi \rangle|^2 \right)
$$

This is exactly 4 times the real part of the Quantum Geometric Tensor (the Fubini-Study metric):

$$
F_Q = 4 g_{\lambda\lambda}
$$

This perfectly demonstrates the unity of physical concepts: the QFI is the natural generalization of the Quantum Metric to mixed states (finite temperature); at zero temperature, it reduces back to the familiar geometric distance in wavefunction space.

These abstract geometric quantities can be connected to experimentally measurable physical quantities through **linear response theory**.

* **Hauke Relation (2016)**
  For a thermal equilibrium state $\rho \propto e^{-\beta H}$, we can use the spectral-decomposition formula above to relate the QFI to the system's imaginary part of the dynamical susceptibility $\chi''(\omega)$. According to the conclusion compiled in the latest review, for parameter estimation generated by an operator $\hat{h}$, its QFI is:

  $$
  F_Q(T) = \frac{4}{\pi} \int_0^\infty d\omega \tanh\left(\frac{\hbar\omega}{2k_B T}\right) \chi''_{\hat{h}}(\omega, T)
  $$

  Here $\chi''_{\hat{h}}(\omega)$ is the dynamical response spectrum of the operator $\hat{h}$.

(ii) Entanglement Entropy

Quantum Geometry is not only related to observable response functions but also has a deep connection to the microscopic **Entanglement Entropy**.

* **Correlation Matrix and Renyi Entropy**
  For a free-fermion system, the entanglement properties of a subsystem $A$ are completely determined by the correlation matrix $C_{nm} = \langle c_n^\dagger c_m \rangle$ (or the overlap matrix $O$). The Renyi entanglement entropy $S_A^{(\alpha)}$ can be expressed directly as a function of the correlation matrix:

  $$
  S_A^{(\alpha)} = \frac{1}{1-\alpha} \text{Tr} \ln \det [p \mathbf{1} - C_A]
  $$

  Since the correlation matrix essentially reflects the overlap and distance of wavefunctions in real space, this hints at a direct geometric correspondence between the Quantum Metric and the entanglement entropy.

### Closing Remarks

Thank you all for reading this far. After nearly two years of silence, I unexpectedly moved from Israel to the United States, and thanks to my advisor I have been able to continue my studies in condensed matter physics—I feel deeply moved by it all.

There have been many changes in my life, studies, work, and relationships in the U.S., and I am still slowly adjusting, while my research has gradually deepened, so I have had no time to write notes. I have also seen readers waiting for updates, and I have turned a platform meant for serious notes into a place where I vent my emotions—for that I sincerely apologize.

By now my PhD is nearly halfway through. To my shame, I still often feel lost about the future. The topic of quantum geometry was not something I carefully chose; it was a passing impulse during my summer research, and I never intended to dig into it deeply, yet it has now become the direction I understand best. Much of the time I do not even know whether digging deeper in this direction has any meaning—often, the more I know, the less I feel I know.

I say I have no time to write notes, but sometimes I feel it is because I am no longer as pure as I once was, no longer able to be genuinely interested in a direction from the bottom of my heart and to pursue it at all costs. That was my mindset when I wrote my notes on Zhihu, and in writing this piece I felt as though I had recovered that pure feeling I used to have when writing notes. I hope I can keep it going, but I am not sure.

I hope to try new directions in the future, but I also gradually feel that I am running out of strength. I envy undergraduates and junior graduate students—although their research experience may not be as rich as mine, their eyes are still full of a pure thirst for knowledge. I know this purity is, to a large extent, a privilege of the young, and I often wish I could return to that pure state of a few years ago, thinking about interesting problems with no utilitarian motive. But reality often dictates that, in order to stay in academia, we cannot flexibly switch directions. Of course, an interesting direction can be cultivated—as the saying goes, the more you understand, the more you embrace it—but the inner longing for purity has not diminished, and I do not know how much time I have left to remain pure.

Perhaps just as the cover image shows, I dedicate my prime years to quantum geometry, and the road ahead must be walked one step at a time.

Thank you all for your support thus far. Until we meet again~
