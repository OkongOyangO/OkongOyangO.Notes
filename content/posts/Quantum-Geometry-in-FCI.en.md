---
title: "🤩Quantum Geometry: A Hands-on Introduction to the Quantum Geometric Tensor"
date: 2026-06-30T11:00:00+08:00
draft: false
math: true
tags: ["Quantum Geometry", "Fubini-Study Metric", "Berry Curvature", "Fractional Chern Insulator", "Condensed Matter"]
categories: ["Physics Notes"]
---

This note aims to quickly get readers up to speed with the definition and computation of Quantum Geometry. Topology is an essential property of quantum systems, capturing invariants under adiabatic changes of parameters, while Geometry focuses on the fine details—finding a proper physical quantity that characterizes the "distance" between quantum states is the central problem of Quantum Geometry.

<!--more-->

Below, we guide readers through a first exploration of the fascinating field of Quantum Geometry by identifying the true physical space where state vectors live—the Projected Hilbert Space—defining a metric on it, and computing the Quantum Geometric Tensor for a simple model.

## Hilbert Space is not Physical

Quantum states can be viewed as vectors in Hilbert space $\mathcal{H}$, with complex components. Taking an $n$-dimensional Hilbert space as an example, a quantum state is a state vector in $\mathbb{C}^n$, which can be written as:

$$ |\psi\rangle = (\psi_1, \cdots, \psi_n)^T $$

$$ \psi_i \in \mathbb{C},\,i = 1, \cdots, n $$

But this is not the true physical space. We know that multiplying a state vector by a nonzero complex number yields the same physical state, so the real quantum state space should be the Hilbert space **modded out** by a nonzero complex number.

Concretely, we first turn the components of the state vector into real numbers, and require the state not to be zero, which gives:

$$ \mathcal{H} \simeq \mathbb{C}^n - \{\mathbf{0}\} \simeq \mathbb{R}^{2n}-\{\mathbf{0}\} $$

Now we mod out by a nonzero complex number $\mathbb{C}-\{\mathbf{0}\}$. Since a nonzero complex number consists of a magnitude $\R^+$ and a phase $U(1)$:

$$ \mathbb{C}-\{\mathbf{0}\} \simeq \R^+ \times U(1) $$

This can be done in two steps. First, fix the magnitude—i.e., mod out by a positive real number. One can imagine this collapses the $2n$-dimensional space without the origin into a $(2n-1)$-dimensional sphere:

$$ (\mathbb{R}^{2n}-\{\mathbf{0}\})/\R^+ \simeq S^{2n-1} $$

Then mod out by a phase, which yields a complex projective space:

$$ S^{2n-1}/U(1) \simeq \mathbb{C}P^{n-1} $$

We call the true space where quantum states live the **Projected Hilbert Space** $\mathcal{P}\mathcal{H} \simeq \mathbb{C}P^{n-1}$.

## Introduction and Definition

For state vectors in Hilbert space, we can define a distance as:

$$
\mathrm{d} s^2=\| \psi(\lambda+\mathrm{d} \lambda)-\left.\psi(\lambda)\right|^2=\langle\delta \psi \mid \delta \psi\rangle \\
=\left\langle\partial_\mu \psi \mid \partial_\nu \psi\right\rangle \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu \\
=\left(\gamma_{\mu \nu}+i \sigma_{\mu \nu}\right) \mathrm{d} \lambda^\mu \mathrm{d} \lambda^\nu
$$

Due to the **Hermitian property of the inner product**, we have:

$$
\gamma_{\mu \nu}+i \sigma_{\mu \nu}=\gamma_{\nu \mu}-i \sigma_{\nu \mu} \quad \gamma_{\mu \nu}=\gamma_{\nu \mu} \quad \sigma_{\mu \nu}=-\sigma_{\nu \mu}
$$

However, Hilbert space is not the true quantum state space, because we can perform a gauge transformation (change the phase) while leaving the physical state unchanged. In this case, the "distance" and metric defined in parameter space should remain the same, since the state at each point in parameter space is unchanged—only a phase has been changed (we consider only normalized states here). But we will immediately find a problem with the "metric" defined earlier.

Specifically, consider an arbitrary gauge transformation on the mapping from parameter space to state space:

$$
\left|\psi^{\prime}(\lambda)\right\rangle=\exp ^{i \alpha(\lambda)}|\psi(\lambda)\rangle
$$

The corresponding metric tensor becomes:

$$ \left\langle\partial_\mu \psi^{\prime} \mid \partial_\nu \psi^{\prime}\right\rangle=\gamma_{\mu \nu}^{\prime}+i \sigma_{\mu \nu}^{\prime} $$

$$
\gamma_{\mu \nu}^{\prime}=\gamma_{\mu \nu}-\beta_\mu \partial_\nu \alpha-\beta_\nu \partial_\mu \alpha+\partial_\mu \alpha \partial_\nu \alpha
$$

$$
\sigma_{\mu \nu}^{\prime}=\sigma_{\mu \nu}
$$

Here $\beta$ is the Berry Connection, defined as

$$ \beta_\mu \equiv i \langle \psi (\lambda) | \partial_\mu \psi (\lambda) \rangle \in \R $$

Thus, the naively defined metric is not physical; the physical metric should be gauge-invariant.

Let us consider the following expression:

$$
g_{\mu \nu}(\lambda):=\gamma_{\mu \nu}(\lambda)-\beta_\mu(\lambda) \beta_\nu(\lambda)
$$

It is straightforward to show that after replacing the metric (the real part, i.e., the Fubini-Study Metric) with the above expression, the newly defined metric becomes gauge-invariant.

The Quantum Geometric Tensor is then defined as:

$$
Q_{\mu \nu}(\lambda):=\left\langle\partial_\mu \psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle-\left\langle\partial_\mu \psi(\lambda) \mid \psi(\lambda)\right\rangle\left\langle\psi(\lambda) \mid \partial_\nu \psi(\lambda)\right\rangle
$$

Its real part characterizes the distance between quantum states and is called the **Fubini-Study metric** (FS metric), a symmetric tensor:

$$
g_{\mu \nu}=\operatorname{Re} Q_{\mu \nu}
$$

Its imaginary part is the **Berry Curvature** part (off by a factor of 2 from the true Berry Curvature), an antisymmetric tensor:

$$ \sigma_{\mu \nu}=\operatorname{Im} Q_{\mu \nu} $$

We can also view the distance between two states as follows: suppose the state amplitudes are already normalized, so that the state vectors all lie as points on a sphere. The distance between two points on the sphere can be expressed as:

$$
D^2\left(\mathbf{k}, \mathbf{k}^{\prime}\right) \equiv D^2\left[\mu(\mathbf{k}), \mu\left(\mathbf{k}^{\prime}\right)\right] =2-2\left|\mu^{\dagger}(\mathbf{k}-\mathbf{q}) \mu(\mathbf{k})\right|
$$

Taking the inner product is equivalent to taking the cosine of the angle $\cos \theta$ between two state vectors, and taking $|...|$ removes the effect of the uncertain phase, leaving only the amplitude contribution. Then $2 - 2 \cos \theta = 4 \sin^2\frac{\theta}{2}$, so $D = 2 \sin \frac{\theta}{2}$, which is the straight-line distance between two points on the sphere. When the two points are very close, this is also the "geodesic" distance between them. From this we can see that the definition of $D(k,k')$ indeed carries the meaning of "distance."

It can be shown that expanding the above $D(k,k')$ definition for two very close points $k$, $k'$ yields a metric expression identical to our definition above. This holds, of course, only in the small-distance approximation.

## Alternative Expression

In actual numerical calculations, the phases of the eigenstate vectors obtained from diagonalization are not consistently related. In this case, computing $|\partial_\mu \phi \rangle$ can be problematic. Therefore, we introduce the following equivalent expression, which converts partial derivatives of the state vector into partial derivatives of the Hamiltonian. Since the definition of $H(k)$ is generally a continuous function, we can compute it either analytically or via numerical finite differences, ensuring the accuracy of numerical simulations of the FS metric, Berry Curvature, and the entire Quantum Geometric Tensor.

We make use of the following identities, where the state vectors are eigenstates of $H$:

$$
\left\langle\phi_n \mid \partial_\mu \phi_0\right\rangle=\frac{\left\langle\phi_n\left|\partial_\mu H\right| \phi_0\right\rangle}{E_0-E_n} \quad \text { if } n \neq 0
$$

$$
\left\langle\phi_0\left|\partial_\mu H\right| \phi_0\right\rangle=\partial_\mu E_0
$$

Thus:

$$
Q_{\mu \nu}=\left\langle\partial_\mu \phi_0\left|\left(\mathbf{1}-\left|\phi_0\right\rangle\left\langle\phi_0\right|\right)\right| \partial_\nu \phi_0\right\rangle
$$

$$
=\sum_{n \neq 0}\left\langle\partial_\mu \phi_0 \mid \phi_n\right\rangle\left\langle\phi_n \mid \partial_\nu \phi_0\right\rangle
$$

$$
=\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

The expression for the Berry Curvature is:

$$
F_{\mu \nu}=\partial_{[\mu} \beta_{\nu]}=i\left\langle\partial_{[\mu} \phi_0 \mid \partial_{\nu]} \phi_0\right\rangle=i\left(Q_{\mu \nu}-Q_{\nu \mu}\right)=-2 \operatorname{Im} Q_{\mu \nu}=-2 \sigma_{\mu \nu}
$$

This shows that the Berry Curvature and the imaginary part of the Quantum Geometric Tensor still differ by a factor of 2:

$$
Q_{\mu \nu}=g_{\mu \nu}-\frac{i}{2} F_{\mu \nu}
$$

The above definitions all hold in the non-degenerate case. For $n$-fold degeneracy, all of the above scalars become $n$-dimensional matrices, and the FS metric, Berry Curvature, and the entire Quantum Geometric Tensor become non-Abelian quantities:

$$
{\left[Q_{\mu \nu}\right]_{i j}=\sum_{n \neq 0, k(n)} \frac{\left\langle\phi_{0 i}\left|\partial_\mu H\right| \phi_{n k}\right\rangle\left\langle\phi_{n k}\left|\partial_\nu H\right| \phi_{0 j}\right\rangle}{\left(E_0-E_n\right)^2}}
$$

![Image](https://pic4.zhimg.com/80/v2-d327ed01b77d2a2414e5ff2cd596f371.png)

## E.g. Spin-1/2 Systems

Let us work out the Quantum Geometric Tensor for the simplest two-level system. Here we choose a Spin-1/2 system in a magnetic field, with parameters being the azimuthal angles of the magnetic field $\theta \in [0,\pi]$, $\phi \in [0,2\pi]$. The Hamiltonian is:

$$
H=\mu \vec{\sigma} \cdot \vec{B} = \mu |B| \left(\begin{array}{cc}
\cos \theta & \sin\theta e^{-i\phi} \\
\sin\theta e^{i\phi} & - \cos \theta
\end{array}\right) = \mu |B| \vec{\sigma} \cdot \hat{B}
$$

The eigenvalues and eigenstates of a two-level system are straightforward:

$$ E_{\pm} = \pm \mu |B| $$

$$
|+\rangle =\left(
e^{-i \phi / 2} \cos \frac{\theta}{2}, e^{i \phi / 2} \sin \frac{\theta}{2}
\right)^T
$$

$$
|-\rangle=\left(-e^{-i \phi / 2} \sin \frac{\theta}{2}, e^{i \phi / 2} \cos \frac{\theta}{2}\right)^T
$$

Using the formula mentioned above:

$$
Q_{\mu \nu} =\sum_{n \neq 0} \frac{\left\langle\phi_0\left|\partial_\mu H\right| \phi_n\right\rangle\left\langle\phi_n\left|\partial_\nu H\right| \phi_0\right\rangle}{\left(E_0-E_n\right)^2}
$$

For a two-level system, this reduces to:

$$
Q^{(\pm)}_{\mu \nu} =\frac{\left\langle \pm \left|\partial_\mu H\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu H\right| \pm\right\rangle}{\left(E_\pm-E_\mp\right)^2}
$$

Canceling $\mu |B|$ in the numerator and denominator gives:

$$ Q^{(\pm)}_{\mu \nu} = \frac{1}{4} \left\langle \pm \left|\partial_\mu (\vec{\sigma} \cdot \hat{B})\right| \mp \right\rangle\left\langle\mp\left|\partial_\nu(\vec{\sigma} \cdot \hat{B})\right| \pm\right\rangle $$

where $\mu,\,\nu = \theta,\,\phi$.

Further:

$$ \partial_\theta (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
-\sin \theta & \cos \theta e^{-i\phi} \\
\cos \theta e^{i\phi} &  \sin \theta
\end{array}\right) $$

$$ \partial_\phi (\vec{\sigma} \cdot \hat{B}) = \left(\begin{array}{cc}
0 & -i \sin \theta e^{-i\phi} \\
i \sin \theta e^{i\phi} &  0
\end{array}\right) $$

Plugging in and doing a bunch of algebra, we obtain:

$$
g^{(\pm)}_{\mu \nu} = \frac{1}{4} \left(\begin{array}{cc}
1 & 0 \\
0 & \sin ^2 \theta
\end{array}\right)
$$

$$
F^{(\pm)}_{\mu \nu}=\pm \frac{1}{2}\left(\begin{array}{cc}
0 & - \sin \theta \\
 \sin \theta & 0
\end{array}\right)
$$

**Note: remember to take the complex conjugate of the bras during the computation!**

Unsurprisingly, the metric here is exactly the natural metric on a sphere of radius $1/2$. This shows that the distance between states is simply the "geodesic" arc length on the Bloch sphere.

## Reference

[1] Cheng, R. (2010). Quantum geometric tensor (Fubini-Study metric) in simple quantum system: A pedagogical introduction. arXiv:1012.1337.

[2] Abouelkomsan, A., Yang, K., & Bergholtz, E. J. (2022). Quantum Metric Induced Phases in Moiré Materials. arXiv:2202.10467.

[3] Parker, D., Ledwith, P., Khalaf, E., Soejima, T., Hauschild, J., Xie, Y., ... & Vishwanath, A. (2021). Field-tuned and zero-field fractional Chern insulators in magic angle graphene. arXiv:2112.13837.

[4] Ozawa, T., & Mera, B. (2021). Relations between topology and the quantum metric for Chern insulators. *Physical Review B*, 104(4), 045103.

[5] Parameswaran, S. A., Roy, R., & Sondhi, S. L. (2012). Fractional Chern insulators and the $W_\infty$ algebra. *Physical Review B*, 85(24), 241308.

[6] Roy, R. (2014). Band geometry of fractional topological insulators. *Physical Review B*, 90(16), 165139.

[7] Wang, J., Cano, J., Millis, A. J., Liu, Z., & Yang, B. (2021). Exact Landau level description of geometry and interaction in a flatband. *Physical Review Letters*, 127(24), 246403.

[8] Simon, S. H., & Rudner, M. S. (2020). Contrasting lattice geometry dependent versus independent quantities. *Physical Review B*, 102(16), 165148.

[9] Wang, J., Klevtsov, S., & Liu, Z. (2022). Origin of Model Fractional Chern Insulators in All Topological Ideal Flatbands. arXiv:2210.13487.

[10] Ledwith, P. J., Vishwanath, A., & Parker, D. E. (2022). Vortexability: A Unifying Criterion for Ideal Fractional Chern Insulators. arXiv:2209.15023.

[11] Daniel Arovas, 'Lecture Notes on Quantum Hall Effect', http://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf
