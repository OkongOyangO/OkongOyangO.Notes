---
title: "🤪Bulk-Boundary Correspondence: Dirac Equation, Wilson Loop, and Entanglement Spectra"
date: 2026-06-29T18:00:00+08:00
draft: false
math: true
tags: ["Topological Insulator", "Bulk-Boundary Correspondence", "Wilson Loop", "Entanglement Spectrum", "Dirac Equation", "Condensed Matter"]
categories: ["Physics Notes"]
---

This note aims to discuss the Bulk-Boundary Correspondence (BBC) in topological band theory, including its dispersion relations and numerical verification of its real-space localization behavior, as well as rigorous proofs using formalisms such as the Dirac equation, Wilson Loop, and Entanglement Spectrum.

<!--more-->

## Bulk-Edge Correspondence (BEC)

When first learning topological band theory, we are often told some important yet subtle conclusions, among which the "Bulk-Edge Correspondence" (BEC, or Bulk-Boundary Correspondence, BBC) of topological states is a particularly significant example: we are often told that topological insulators/Chern insulators have gapped bulk states but gapless edge states, that these edge states are robust and cannot be gapped by disorder, and that their number (sometimes modulo 2, sometimes an integer) is determined by a bulk topological invariant. For relevant background, one can dig up my previous ramblings:

## Numerical Verification

This conclusion is so widely circulated that we often invoke it casually without knowing its rigorous derivation. What we commonly do is take a step back and verify its correctness via tight-binding models combined with exact diagonalization. Here I recommend an article introducing the kwant package: for example, gapped bulk properties are often verified by obtaining band structures from exact diagonalization of tight-binding models with periodic boundary conditions (PBC), i.e., without boundaries.

![typical 2D band structure](/posts/bulk-boundary-correspondence/fig01_typical_2d_band.png)

*typical 2D band structure*

Gapless edge states, on the other hand, are verified by artificially imposing open boundary conditions (OBC) in one direction, then examining the dimensionally reduced band structure with respect to the good quantum number in the perpendicular direction (momentum $k_{\perp}$).

![edge state spectrum with OBC](/posts/bulk-boundary-correspondence/fig02_edge_state_spectrum_OBC.png)

*edge state spectrum with OBC*

Their robustness can be verified by adding disorder in the open-boundary direction and observing that the edge state dispersion remains gapless. The direction of edge state motion in real space can be determined by examining the group velocity $v = \frac{\partial \epsilon(k)}{\hbar \partial k}$. It is worth noting that a $C=1$ edge has only one chiral edge state moving in a single direction, but when we perform numerical simulations we inevitably have two boundaries (semi-open boundary conditions cannot be diagonalized numerically). In this case, two edge states with opposite group velocities appear, corresponding to the two boundaries. These two states have no symmetry relation between them because the 2D Chern insulator belongs to class A of the tenfold classification and has no symmetry at all. In contrast, the boundary of a topological insulator has one pair (or an odd number of pairs) of edge states related by time-reversal symmetry. When two boundaries are opened in one direction for numerical calculations, two pairs of edge states with opposite group velocities appear, where the dispersion of time-reversal-related edge states is symmetric about $k=0$.

![Edge state](/posts/bulk-boundary-correspondence/fig03_edge_state.png)

*Edge state*

## Why Strict Derivation？

These numerical results can only serve as verification rather than rigorous derivation. As one of the most important conclusions in topological band theory, the bulk-boundary correspondence is certainly easy to remember, but a more careful examination of its theoretical derivation also deepens our understanding of the correspondence. At the same time, the tools used in the rigorous proof of bulk-boundary correspondence, such as the Dirac equation and Wilson Loop formalism, are also extremely useful for computing further derived topological properties such as HOTI bulk-boundary correspondence and edge states. Understanding their physical origin is by no means unimportant.

## Dirac Equation

A topological phase transition coincides with gap closing, and this process can be described by a Dirac fermion whose mass varies with a parameter. Let us first consider the BHZ model:

$$
H(k_x,k_y;u) = \sin k_x \sigma_x + \sin k_y \sigma_y + (u+\cos k_x + \cos k_y) \sigma_z
$$

where $u$ is a slowly varying parameter. The system is a trivial insulator for $u<-2$, and a Chern insulator with Chern number $C=-1$ for $-2<u<0$. During this process, a topological phase transition occurs because gap closing happens at $(k_x,k_y)=(0,0)$.

![Topological phase transition with inverted Dirac fermion mass](/posts/bulk-boundary-correspondence/fig04_topo_transition_dirac_mass.png)

*Topological phase transition with inverted Dirac fermion mass*

Taking $u\approx-2, (k_x,k_y)\approx(0,0)$, the Bloch Hamiltonian near the topological transition point is identical to a (2+1)D Dirac fermion:

$$
H(k_x,k_y;m) \approx k_x \sigma_x + k_y \sigma_y + m \sigma_z \quad m \equiv u + \cos k_x + \cos k_y \approx u+2
$$

For example, the transition from a trivial insulator to a topological/Chern insulator can be described by the change in mass, reflecting the band inversion process. The vicinity of the boundary of a topological insulator can also be viewed as undergoing such a band inversion process, where the low-energy excitations, resembling Dirac fermions, undergo band inversion. Consider a boundary at $x=0$, with $x<0$ being the interior of the system and $x>0$ being the exterior (vacuum, which can be regarded as a trivial insulator). Treating $x$ as a slowly varying parameter that controls the system, $m(x)$ changes sign across the boundary:

$$
m(x)>0: x<0 \quad m(x)<0: x>0
$$

As long as the variation is sufficiently slow, each neighborhood of $x$ has a sufficiently large bulk to form a stable Bloch Hamiltonian $H(k_x,k_y;m)$, without needing to consider the effects of $\partial_x m(x)$. That is, the variation of the system with $x$ is "adiabatic." It is not difficult to see that since we only care about low-energy physics (gap closing), the above discussion holds for any other model. Let us now solve for the real-space distribution of edge states. Transforming the Hamiltonian into real space with $k_x \rightarrow -i \partial_x$, and assuming translational symmetry still holds in the $y$ direction (so $k_y$ remains a good quantum number), we obtain the following partially Fourier transformed Hamiltonian:

$$
H(x,k_y) = -i \sigma_x \partial_x + k_y \sigma_y + m(x) \sigma_z
$$

This corresponds precisely to the low-energy behavior of the Hamiltonian after dimensional reduction. Solving for its eigenstates and eigenenergies yields the edge states and their spectra. The case $H(x,k_y = 0) = -i \sigma_x \partial_x + m(x) \sigma_z$ is easier to solve, with the eigenequation:

$$
-i \sigma_x \partial_x \Psi_{k_y=0} (x) = - m(x) \sigma_z \Psi_{k_y=0} (x)
$$

where $\Psi_{k_y=0} (x)$ is a two-component spinor because $\sigma_i$ are $2\times 2$ matrices.

$$
\Rightarrow \partial_x \Psi_{k_y=0} (x) = - m(x) \sigma_y \Psi_{k_y=0} (x)
$$

Thus $\Psi_{k_y=0} (x)$ must be an eigenstate of $\sigma_y$, and can be written as:

$$
\Psi_{k_y=0}^{\sigma_y = \pm 1} (x) = \psi_{k_y=0}^{\sigma_y = \pm 1} (x) \left(\begin{array}{c}1 \\ \pm i\end{array}\right)
$$

where $\psi_{k_y=0} (x)$ is an ordinary function satisfying:

$$
\partial_x \psi_{k_y=0}^{\sigma_y = \pm 1} (x) = \mp m(x) \psi_{k_y=0}^{\sigma_y = \pm 1} (x)
$$

$$
\Rightarrow \psi_{k_y=0}^{\sigma_y = \pm 1} (x) \propto e^{ \mp \int^x m(x) dx }
$$

Since $m(x)>0$ for $x<0$ and $m(x)<0$ for $x>0$, only $\sigma = -1$ is normalizable, giving the solution:

$$
\Psi_{k_y=0} (x) = e^{ - \int^x m(x) dx} \left(\begin{array}{c}1 \\ -i\end{array}\right)
$$

with eigenvalue $E(k_y = 0) = 0$. It is not hard to see that for $k_y \neq 0$, $\Psi_{k_y=0} (x) = e^{ - \int^x m(x) dx} \left(\begin{array}{c}1 \\ i\end{array}\right)$ is also a solution, with energy:

$$
E(k_y) = k_y
$$

This yields the low-energy dispersion of the edge state, consistent with the gapless edge states we described, and the group velocity is in the $+y$ direction — indeed an edge state propagating along the boundary, matching our earlier statement about bulk-boundary correspondence.

![Real space localization and boundary spectrum](/posts/bulk-boundary-correspondence/fig05_realspace_localization_boundary_spectrum.png)

*Real space localization and boundary spectrum*

Examining the wavefunction's real-space distribution, we see that $\Psi_{k_y=0} (x) \propto e^{ - \int^x m(x) dx}$ is a wave packet localized near $x=0$. The simplest verification is to substitute $m(x) = -\alpha x$, yielding a Gaussian wave packet localized at $x=0$, with the $y$-direction distribution being an extended plane wave. Alternatively, taking $m(x) = \left\{\begin{array}{l}m_1>0,&\,x<0 \\ -m_2<0,&\,x>0\end{array} \right.$ also gives a localized wave packet.

![Localized Edge State](/posts/bulk-boundary-correspondence/fig06_localized_edge_state.png)

*Localized Edge State*

This remains valid for other topological insulators, because a topological phase transition always occurs at the boundary, and the low-energy behavior described by a massive Dirac fermion with inverted mass is always universal. This is more rigorous than the numerical verification of bulk-boundary correspondence. More detailed content can be found in Professor Qingrui Wang's online course; I will not elaborate further here.

### Exact Solution

@renshengxuanxue provided an article on the rigorous solution of topological edge states; see:

Edge states and the bulk-boundary correspondence in Dirac Hamiltonians

## Wilson Loop

On the one hand, the Wilson Loop reflects the bulk properties of a topological system; on the other hand, the Wilson Loop Spectrum is topologically equivalent to the dispersion of edge states. In summary, the Wilson Loop is related to both the bulk properties and the edge state properties of topological systems, making it a natural tool for proving the bulk-boundary correspondence of topological states of matter. On Zhihu, many experts have also written excellent articles and answers on this topic; I will list some links here. Next, let us introduce the Wilson Loop formalism in topological band theory and discuss its connection to bulk properties and edge state properties.

### Wilson Loop and Bulk: Wannierization

The Wilson Loop reflects the bulk properties of a topological system because the Wilson Loop Spectrum essentially computes how the Wannier Center (in a given direction) varies with momentum (in the perpendicular direction). The real-space motion of the Wannier states occupied by electrons reflects the system's polarization, transport, and other properties that condensed matter physicists study with great interest when investigating topological states of matter. For example, the 1D topological SSH chain has quantized polarization, and the 2D Chern insulator has quantized Hall conductance, both related to the topological invariants of the system's bulk states. A Chern band with Chern number $C$ contributes $\sigma_{xy} = C \frac{e^2}{h}$ to the conductance. An electric field in the $y$ direction corresponds to a change in $k_y$; if the Wannier Center in the $x$ direction moves exactly one lattice constant, this corresponds to transporting one electron in the $x$ direction. Thus, through the Wilson Loop Spectrum, we can read off bulk properties such as the system's topological invariants.

### Wilson Loop and charge pump

![Wilson Loop and charge pump](/posts/bulk-boundary-correspondence/fig07_wilson_loop_charge_pump.png)

*Wilson Loop and charge pump*

The Wilson Loop formalism was originally proposed by Xi Dai et al. in search of a more convenient numerical method for computing topological invariants. Solving for Bloch wavefunctions numerically is not difficult, but directly using Bloch wavefunctions to compute the Berry connection and Berry curvature requires fixing a gauge numerically. However, since topological invariants are gauge-invariant quantities, artificially imposing a gauge in calculations is cumbersome, and the phases of numerically computed wavefunctions are generally disordered, making it difficult to obtain a continuous gauge. Inspired by the real-space pump process of electronic wavefunctions, Xi Dai et al. derived an expression equivalent to the topological invariants obtained by integrating the Berry connection and Berry curvature — this is the origin of the Wilson Loop formalism.

<https://journals.aps.org/prb/abstract/10.1103/PhysRevB.84.075119>

This article was originally used to compute the $\mathbb{Z}_2$ index of time-reversal invariant topological insulators without inversion symmetry, but its motivation of "describing the real-space pump process of electronic wavefunctions" can be applied to Chern insulators and other topological insulators. The Wilson Loop formalism is also a further development of modern polarization theory. Consider the tight-binding Hamiltonian:

$$
H=\sum_{\alpha \beta} \sum_{i j} h_{i j}^{\alpha \beta}|\alpha i\rangle\langle\beta j|+ h.c.
$$

Its eigenstates are Bloch wavefunctions:

$$
\left|\Psi_{n \mathbf{k}}\right\rangle=\sum_\alpha g_{n \alpha}(\mathbf{k})|\alpha \mathbf{k}\rangle
$$

where $|\alpha \mathbf{k}\rangle$ is the Bloch sum of atomic orbitals:

$$
|\alpha \mathbf{k}\rangle=\frac{1}{\sqrt{N_{cell}}} \sum_i|\alpha i\rangle e^{i \mathbf{k} \cdot \mathbf{R}_i}
$$

Define $|n, \mathbf{k}\rangle$ as the periodic part of the Bloch wavefunction:

$$
|n, \mathbf{k}\rangle=e^{-i \mathbf{k} \cdot \mathbf{r}}\left|\Psi_{n \mathbf{k}}\right\rangle
$$

We generally treat it as a wavefunction parametrized by $\mathbf{k}$, used to compute the Berry connection and Berry curvature:

$$
[\mathbf{A}(\mathbf{k})]_{mn} = i \langle m, \mathbf{k} | \nabla_{\mathbf{k}} | n, \mathbf{k} \rangle \quad [A_i(\mathbf{k})]_{mn} = i \langle m, \mathbf{k} | \partial_{k_i} | n, \mathbf{k} \rangle \quad [F_{ij}(\mathbf{k})]_{mn} = [\partial_{k_i}A_j(\mathbf{k})]_{mn} - [\partial_{k_j}A_i(\mathbf{k})]_{mn}
$$

Here we have written the Berry connection and Berry curvature in a more general multiband form, where the $i, j$ indices denote components and $m, n$ are band indices. To compute the (Maximally Localized) Wannier Function in a given direction, we use the following result: the 1D Maximally Localized Wannier Function (MLWF) in a given direction is an eigenstate of the projected position operator $P\hat{x_i}P$, where $\hat{x_i}$ is the position operator projected onto the corresponding band subspace, with the eigenvalue being the Wannier Center. Thus, the problem of computing the Wannier Center evolution in the Wilson Loop formalism reduces to solving the eigenvalue problem of the projected position operator $P\hat{x_i}P$ in the direction of interest. For why this result holds, one can dig up my note on Maximally Localized Wannier Functions. However, we must consider the issue of OBC and PBC boundary conditions. Under open boundary conditions, we can easily define the position operator $\hat{x}$:

$$
\hat{x} =\sum_{i \alpha} (R_i + r_{\alpha})|\alpha i\rangle\langle\alpha i|
$$

In the limit where the boundary goes to infinity:

$$
\hat{x}=\sum_{i \alpha} R_i|\alpha i\rangle\langle\alpha i|=i \frac{\partial}{\partial k_x}
$$

where $R_i$ is the position of unit cell $i$ relative to the origin, and $r_\alpha$ is the distance of sublattice/orbital $\alpha$ from the center of the unit cell. For convenience, unless otherwise specified, we set $r_\alpha = 0$ in the following. Bulk properties are generally solved under PBC, but the position operator $\hat{x}$ is not well defined under PBC. In this case, we define the position using the following operator:

$$
\hat{X}=\sum_{i \alpha} e^{-i \delta k_x \cdot \mathbf{R}_i}|\alpha i\rangle\langle\alpha i|
$$

The eigenvalues of this operator are $N_x$ $U(1)$ phases $e^{-i \delta k_x \cdot \mathbf{R}_i}$, with the positions $\mathbf{R}_i$ encoded in the phases of the eigenvalues. Since $\delta k_x \equiv \frac{2 \pi}{N_x a_x}$, the phases (coordinates) of the 1st and $(N_x+1)$-th unit cells are the same (mod $2\pi$). Although only the phases of the eigenvalues of this "position operator" carry the physical meaning of coordinates, we will still call $\hat{X}$ the "position operator" for convenience, since $\hat{x}$ is ill-defined. In other words, the coordinate has become a multivalued function because, under periodic boundary conditions, $R_i$ and $R_i+N_x a_x$ are the same coordinate. Without loss of generality, consider a 2D system and assume we only Fourier transform in the $x$ direction to obtain partial Wannier functions localized in $x$. Then $k_y$ in the $y$ direction remains a good quantum number, meaning we can consider the problem of Wannier localization and MLWF solution within the subspace at a given $k_y$. Fixing $k_y$, we consider the band subspace onto which we project, i.e., select a few bands of interest and examine the real-space behavior of their electronic wavefunctions in the $x$ direction. Doing this for each $k_y$ yields the evolution of the $x$-localized Wannier functions as a function of $k_y$. If we apply an electric field in the $y$ direction, causing $k_y$ to shift, this evolution tells us how electrons move in the $x$ direction under a $y$-direction electric field — precisely what is of interest for topological/Chern insulators. This block diagonalization over $k_y$ is completely analogous to using Bloch's theorem when solving band structures (strictly speaking, since the $k_x$ direction has become a matrix index to be diagonalized rather than a "good quantum number," it is more akin to solving for the edge state spectrum). We will henceforth refer to the "evolution of $x$-localized Wannier functions with $k_y$" as the "Wilson Loop Spectrum." Fixing $k_y$, the projection operator is:

$$
\hat{P}_{k_y}=\sum_{n \in o, k_x}\left|\Psi_{n \mathbf{k}}\right\rangle\left\langle\Psi_{n \mathbf{k}}\right|
$$

where $n$ is the band index and $o$ is the band set we wish to project onto. Suppose we project onto $M$ bands. The projected position operator is:

$$
\begin{aligned}
\hat{X}_P\left(k_y\right)&=\hat{P}_{k_y} \hat{X} \hat{P}_{k_y} \\
&=\sum_{n m \in o} \sum_{k_x k_x^{\prime}, i \alpha} e^{-i \delta k_x \cdot \mathbf{R}_i}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{n k_x, k_y}\right| \\
&\times|\alpha i\rangle\left\langle\alpha i \mid \Psi_{m k_x^{\prime}, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&=\sum_{n m \in o} \sum_{k_x k_x^{\prime}, i} \frac{1}{N_{cell}} e^{i\left(k_x+\delta k_x-k_x^{\prime}\right) \cdot \mathbf{R}_i}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&\times\left[\sum_\alpha g_{n \alpha}^*\left(k_x\right) g_{m \alpha}\left(k_x^{\prime}\right)\right] \\
&=\sum_{k_x k_x^{\prime}} \delta\left(k_x+\delta k_x-k_x^{\prime}\right) \sum_{n m \in o}\left|\Psi_{n k_x, k_y}\right\rangle\left\langle\Psi_{m k_x^{\prime}, k_y}\right| \\
&\times\left[\sum_\alpha g_{n \alpha}^*\left(k_x\right) g_{m \alpha}\left(k_x^{\prime}\right)\right]
\end{aligned}
$$

Due to the $\delta\left(k_x+\delta k_x-k_x^{\prime}\right)$ function, the projected position operator $\hat{X}_P\left(k_y\right)$ takes the following block form in the $\left|\Psi_{n k_x, k_y}\right\rangle$ basis:

$$
\hat{X}_P\left(k_y\right)=\left(\begin{array}{cccccc}
0 & F_{0,1} & 0 & 0 & 0 & 0 \\
0 & 0 & F_{1,2} & 0 & 0 & 0 \\
0 & 0 & 0 & F_{2,3} & 0 & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & 0 & F_{N_x-2, N_x-1} \\
F_{N_x-1,0} & 0 & 0 & 0 & 0 & 0
\end{array}\right)
$$

where:

$$
F_{i, i+1}^{n m}\left(k_y\right)=\sum_\alpha g_{n \alpha}^*\left(k_{x, i}, k_y\right) g_{m \alpha}\left(k_{x, i+1}, k_y\right)
$$

Note that $F_{i, i+1}$ is still an $M\times M$ matrix and depends on $k_y$. Using the following identity:

$$
\begin{aligned}
\left\langle n, k \mid m, k^{\prime}\right\rangle&=\left\langle\Psi_{n k}\left|e^{i k \cdot r} e^{-i k^{\prime} \cdot r}\right| \Psi_{m, k^{\prime}}\right\rangle \\
&=\sum_{\alpha, \beta} \frac{1}{N_{cell}} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \\
&* \sum_{j_1, j_2}\left\langle\alpha j_1\left|e^{i\left(k-k^{\prime}\right) \cdot r}\right| \beta j_2\right\rangle e^{i\left(k^{\prime} \cdot R_{j_2}-k \cdot R_{j_1}\right)} \\
&=\sum_{\alpha, \beta} \frac{1}{N_{cell}} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \\
&* \sum_{j_1, j_2}\langle\alpha \mid \beta\rangle \delta_{j_1 j_2} e^{i\left(k-k^{\prime}\right) \cdot R_{j_2}} e^{i\left(k^{\prime} \cdot R_{j_2}-k \cdot R_{j_1}\right)} \\
&=\sum_{\alpha, \beta} g_{n \alpha}^*(k) g_{m \beta}\left(k^{\prime}\right) \delta_{\alpha \beta} \\
&=\sum_\alpha g_{n \alpha}^*(k) g_{m \alpha}\left(k^{\prime}\right)
\end{aligned}
$$

We can rewrite the above projected position operator in terms of the periodic part of the Bloch wavefunctions:

$$
F_{i, i+1}^{m n}\left(k_y\right)=\left\langle m, k_{x, i}, k_y \mid n, k_{x, i+1}, k_y\right\rangle
$$

Now, how do we solve the eigenvalue problem of this screwed-diagonal matrix? The structure of the screwed-diagonal block matrix suggests using the transfer matrix method. Suppose the eigenstate (Maximally Localized Wannier State) in this basis is $|W^i\rangle =(|W^i_0\rangle,\,|W^i_1\rangle,\,\dots,\,|W^i_{N_x-1}\rangle)^T$, where each $|W^i_j\rangle$ has $n$ components, and $i$ labels which eigenstate it is. The eigenvalue equation is:

$$
\hat{X}_P\left(k_y\right) | W^i \rangle = e^{-i \delta k_x \cdot \mathbf{R}_i} | W^i \rangle
$$

Expanding this gives:

$$
\begin{aligned}
\left(\begin{array}{cccccc}
0 & F_{0,1} & 0 & 0 & 0 & 0 \\
0 & 0 & F_{1,2} & 0 & 0 & 0 \\
0 & 0 & 0 & F_{2,3} & 0 & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & 0 & F_{N_x-2, N_x-1} \\
F_{N_x-1,0} & 0 & 0 & 0 & 0 & 0
\end{array}\right)
& \left(\begin{array}{c}
|W^i_0\rangle \\
|W^i_1\rangle \\
|W^i_2\rangle \\
\vdots \\
|W^i_{N_x-2}\rangle \\
|W^i_{N_x-1}\rangle
\end{array}\right) \\
= e^{-i \delta k_x \cdot \mathbf{R}_i}
& \left(\begin{array}{c}
|W^i_0\rangle \\
|W^i_1\rangle \\
|W^i_2\rangle \\
\vdots \\
|W^i_{N_x-2}\rangle \\
|W^i_{N_x-1}\rangle
\end{array}\right)
\end{aligned}
$$

This yields a transfer-matrix-like recurrence relation:

$$
F_{j,j+1} |W^i_{j+1}\rangle = e^{-i \delta k_x \cdot \mathbf{R}_i} |W^i_{j}\rangle
$$

This recurrence is also periodic. Multiplying all recurrence relations together gives (for convenience, we set the lattice constant $a_x = 1$):

$$
F_{0,1} \dots F_{N_x-2,N_x-1} F_{N_x-1,0} |W^i_{0}\rangle = e^{-i N_x \delta k_x \cdot \mathbf{R}_i}|W^i_{0}\rangle = e^{-i 2\pi \mathbf{R}_i} |W^i_{0}\rangle
$$

Define the "Wilson Loop":

$$
W_{k_x \rightarrow k_x + 2\pi} \left(k_y\right)=F_{k_x,k_x+\delta k_x} F_{k_x+\delta k_x, k_x+2\delta k_x} \cdots F_{k_x+(N_x-2)\delta k_x, k_x}
$$

Then the eigenvalue problem of the projected position operator (solving for the Wannier Center) becomes the eigenvalue problem of the "Wilson Loop" $W_{k_x\rightarrow k_x + 2\pi} \left(k_y\right)$:

$$
\mathbf{R}_i = \frac{i}{2\pi} \ln [W_{k_x \rightarrow k_x + 2\pi}]
$$

Note that the Wilson Loop is an $M\times M$ matrix and can have $M$ eigenvalues and eigenstates, corresponding to the Wannier Functions (resembling atomic orbitals, but possibly hybridized) of the $M$ occupied bands in real space. Meanwhile, $\hat{X}_P$ is an $(N_x M) \times (N_x M)$ matrix with $N_x$ times more eigenvalues (Wannier Centers). These correspond precisely to translations by $n=0,1,2,\dots,N_x-1$ lattice constants. Why is this the case? At this point, a phase change of $2\pi$ in the Wilson Loop eigenvalues corresponds to a phase change of $2\pi/N_x$ in $\hat{X}_P$ eigenvalues. Hence, one Wilson Loop eigenvalue corresponds to $N_x$ $\hat{X}_P$ eigenvalues, namely $\mathbf{R}_i + n,\,n=0,1,2,\dots,N_x-1$ are also solutions for the Wannier Center. For $\delta k=\frac{2 \pi}{N_x a_x} \ll 2 \pi$, i.e., an infinitely long system (still under PBC), we have:

$$
\begin{aligned}
F_{i, i+1}^{m n} & =\left\langle m, k_{x, i}, k_y \mid n, k_{x, i+1}, k_y\right\rangle \\
& =\delta_{m n}+\left\langle m, k_{x, i}, k_y\left|\left(\left|n, k_{x, i+1}, k_y\right\rangle-\left|n, k_{x, i}, k_y\right\rangle\right)\right.\right. \\
& =\delta_{m n}-i A_{i, i+1}^{m n} \delta k \\
& \approx e^{-i A_{i, i+1}^{m n} \delta k}
\end{aligned}
$$

where $A_{i, i+1}^{m n}$ is the discrete form of the Berry connection:

$$
A_{i, i+1}^{m n} =i \frac{\left\langle m, k_{x, i}, k_y\left|\left(\left|n, k_{x, i+1}, k_y\right\rangle-\left|n, k_{x, i}, k_y\right\rangle\right)\right.\right.}{\delta k}
$$

Then the "Wilson Loop" can also be formally written as a path-ordered integral:

$$
\begin{aligned}
W_{k_x \rightarrow k_x + 2\pi}\left(k_y\right) & =\left[\prod_{i=0}^{N_x-1} F_{i, i+1}\right]=\left[\prod_{i=0}^{N_x-1} e^{-i A_{i, i+1} \delta k}\right] \\
& =P e^{\int_{C_{k_y}}-i A(k) d k}
\end{aligned}
$$

where the path integral is along $C_{k_y}:(k_x,k_y) \rightarrow (k_x + 2\pi,k_y)$. This is also why this operator is called the Wilson Loop. Numerically, computing the Wilson Loop involves no gauge issues in the diagonalization, making it an excellent tool for computing topological invariants.

![Path Integral Contour of Wilson Loop](/posts/bulk-boundary-correspondence/fig08_path_integral_contour_wilson_loop.png)

*Path Integral Contour of Wilson Loop*

Next, let us elucidate the physical meaning of the Wilson Loop and its role in determining the $\mathbb{Z}$ index and $\mathbb{Z}_2$ index of Chern insulators.

### Why Wannierization?

One might ask: why use the Wannier basis, which is gauge-dependent — it doesn't seem very physical. Why would electrons reside in localized Wannier states that are not eigenstates? This objection is valid when bands are partially filled, but it merits deeper consideration for fully occupied bands. The many-body wavefunction of a fully occupied band is determined by the Slater determinant of all Bloch wavefunctions on that band:

$$
\Psi_{\text{many body}}(x_1,x_2,\dots x_N) = \frac{1}{\sqrt{N!}} \left| \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right|
$$

where $\{\psi_{k_i}\}_{i=1}^N$ are Bloch wavefunctions. Under a unitary transformation $\mathcal{U}$, these can be transformed into real-space localized Wannier states $\{w_{R_i}\}_{i=1}^N$. The fully occupied Wannier states can be written as a Slater determinant:

$$
\Psi_{\text{many body}}'(x_1,x_2,\dots x_N) = \frac{1}{\sqrt{N!}} \left| \begin{array}{c}
w_{R_1}(x_1) & \cdots & w_{R_N}(x_1) \\
\vdots & \ddots & \vdots \\
w_{R_1}(x_N) & \cdots & w_{R_N}(x_N)
\end{array}\right|
$$

The two many-body states are identical:

$$
\Psi_{\text{many body}}' = \Psi_{\text{many body}}
$$

because their determinants differ only by a unitary transformation:

$$
\begin{aligned}
& \det \left[ \left( \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right) \right] \\
= & \det \left[ \mathcal{U} \left( \begin{array}{c}
\psi_{k_1}(x_1) & \cdots & \psi_{k_N}(x_1) \\
\vdots & \ddots & \vdots \\
\psi_{k_1}(x_N) & \cdots & \psi_{k_N}(x_N)
\end{array}\right) \mathcal{U}^\dagger \right] \\
= & \det \left[ \left( \begin{array}{c}
w_{R_1}(x_1) & \cdots & w_{R_N}(x_1) \\
\vdots & \ddots & \vdots \\
w_{R_1}(x_N) & \cdots & w_{R_N}(x_N)
\end{array}\right) \right]
\end{aligned}
$$

![Equivalence of Bloch and Wannier Picture in Fully Occupied Bands](/posts/bulk-boundary-correspondence/fig09_bloch_wannier_equivalence.png)

*Equivalence of Bloch and Wannier Picture in Fully Occupied Bands*

Thus, as long as the discussion is confined to fully occupied bands, i.e., insulators, using real-space localized Wannier states to analyze physical processes is perfectly valid, and is particularly useful for analyzing polarization and charge pumping in insulators. Conversely, for metals (partially filled bands), we cannot analyze properties like polarization. In fact, electric polarization is a phenomenon unique to insulators; when an electric field is applied to a metal, the presence of unoccupied states in the band allows conduction. This describes another aspect of the distinction between conductors and insulators. If you are interested in the difference between conductors and insulators, you can refer to my previous note. In any case, with the picture of electrons occupying real-space localized Wannier states, we can better analyze the topological properties of the system. Using natural units $e=\hbar=1$, for a Chern insulator with an applied $y$-direction electric field $E_y$, a state initially at $k_{y0}$ evolves to $k_{y0} + E_y t$ after time $t$. Examining the real-space motion of electrons (Wannier Centers) in the $x$ direction, after one period the entire ensemble of electrons in real space shifts by one lattice constant, corresponding to the transport of one unit charge in the $x$ direction. This charge pump process can be read directly from the Wilson Loop Spectrum:

![Wilson Loop Spectrum of C=1 Chern Insulator and its Real Space Picture](/posts/bulk-boundary-correspondence/fig10_wilson_spectrum_C1_chern.png)

*Wilson Loop Spectrum of C=1 Chern Insulator and its Real Space Picture*

Taking time $2\pi/E_y$, the $x$-direction current induced by the $y$-direction electric field $E_y$ is:

$$
I_x = j_x = \frac{\Delta Q}{\Delta t} = \frac{1}{2\pi/E_y} = \frac{1}{2\pi} E_y
$$

The current equals the current density because we have set the lattice constant to 1. Therefore, the Hall conductance is quantized: $\sigma_{xy}=\frac{1}{2\pi}=\frac{e^2}{h}$. Generalizing to arbitrary Chern number gives $\sigma_{xy} = \frac{C}{2\pi}$. This demonstrates the intuitive physical meaning of the Wilson Loop formalism.

![Charge Pump of Chern Insulator](/posts/bulk-boundary-correspondence/fig11_charge_pump_chern.png)

*Charge Pump of Chern Insulator*

Similarly, for $\mathbb{Z}_2$ topological insulators, we examine the motion of a pair of time-reversal counterpart Wannier states, i.e., a "time-reversal charge pump." If after one period the time-reversal counterpart Wannier states move by one lattice constant in opposite directions, a nontrivial "time-reversal charge pump" has occurred and the system is a topological insulator; otherwise, it is a trivial insulator. There is no net charge pump, as guaranteed by time-reversal symmetry.

![Wilson Loop Spectrum of TI and Real Space Picture](/posts/bulk-boundary-correspondence/fig12_wilson_spectrum_TI.png)

*Wilson Loop Spectrum of TI and Real Space Picture*

![Charge Pump of Topological Insulator](/posts/bulk-boundary-correspondence/fig13_charge_pump_TI.png)

*Charge Pump of Topological Insulator*

The Wilson Loop Spectrum of a trivial insulator is shown in the figure below, i.e., neither a net charge pump nor a nontrivial time-reversal charge pump:

![Trivial Wilson Loop Spectra](/posts/bulk-boundary-correspondence/fig14_trivial_wilson_spectrum.png)

*Trivial Wilson Loop Spectra*

![Charge not Pumped in trivial insulator (C=0 Chern Insulator)](/posts/bulk-boundary-correspondence/fig15_charge_not_pumped_trivial.png)

*Charge not Pumped in trivial insulator (C=0 Chern Insulator)*

### Wilson Loop and Edge: Spectrum Equivalence

On the other hand, the Wilson Loop Spectrum is topologically equivalent to the dispersion relation of edge states. Fidkowski, L., Jackson, T. S., & Klich, I. et al. proved that, through an appropriate interpolation, the Wilson Loop Spectrum and the Edge State Spectrum can be continuously connected. Thus, via the Wilson Loop Spectrum, we can estimate the shape of the edge state dispersion and its group velocity (under topological equivalence).

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.036601>

Specifically, we consider the simplest flat-band projected Hamiltonian, since the discussion is universal as long as topological equivalence holds (no gap closing). The flat-band Hamiltonian is:

$$
\mathscr{H}_{\text{flat}}(\vec{k})=1-2 P(\vec{k})
$$

where $P(\vec{k})$ is the projection operator onto $M$ occupied bands (valence bands). The topological properties are stored in the wavefunction information:

$$
P(\vec{k})=\sum_n^M \int_{-\pi}^\pi \frac{\mathrm{d} k_x}{2 \pi}\left|\psi_{k, n}\right\rangle\left\langle\psi_{k, n}\right|,
$$

Consider the boundary:

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k})=P(\vec{k}) V_0(\hat{x}) P(\vec{k})+1-P(\vec{k}) \quad V_0(x)= \begin{cases}1 ,\,x<0 \\-1 ,\,x>0\end{cases}
$$

The bulk Hamiltonian is:

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k}) \rightarrow \mathscr{H}_{\mathrm{flat}}(\vec{k}) \text { for } x \rightarrow+\infty
$$

The vacuum Hamiltonian is:

$$
\mathscr{H}_{\mathrm{bdr}}(\vec{k}) \rightarrow 1 \text { for } x \rightarrow-\infty
$$

Consider the following variation of the boundary potential:

$$
V_t(x)=\left\{\begin{array}{ll}
-\frac{x}{t} & \text { for }|x|<t /(1-t) \\
-\frac{\operatorname{sgn}(x)}{1-t} & \text { for }|x| \geq t /(1-t)
\end{array}, \quad 0 \leq t \leq 1 .\right.
$$

At $t=0$, the system's spectrum is that of $\mathscr{H}_{\mathrm{bdr}}(\vec{k})$, while at $t=1$, it becomes the spectrum of $P\hat{x}P$, which is precisely the Wilson Loop Spectrum (up to translation by integer lattice constants). This proves their topological equivalence.

![Equivalence between Wilson Loop Spectrum & Edge Spectrum](/posts/bulk-boundary-correspondence/fig16_wilson_edge_equivalence.png)

*Equivalence between Wilson Loop Spectrum & Edge Spectrum*

For a more detailed explanation, refer to the annual Topological Matter School (TMS) online course from Spain:

<https://www.youtube.com/watch?v=t3k5DLKreyg&t=2029s>

Or consult the published TMS 2017 lecture notes:

<https://link.springer.com/content/pdf/10.1007/978-3-319-76388-0.pdf>

## Entanglement Spectrum

Can topics from quantum information, such as the Entanglement Spectrum and Entanglement Entropy, also get a foot in the door of topological condensed matter physics? The "root of all evil" traces back to Haldane's 2008 paper using the Entanglement Spectrum to identify topological order in FQHE.

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.101.010504>

Lukasz Fidkowski generalized this to band topology:

<https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.104.130502>

The central claim is that topologically nontrivial states have topologically protected degeneracy.

![Degeneracy in Entanglement Spectra = topologically non-trivial phase](/posts/bulk-boundary-correspondence/fig17_entanglement_degeneracy.png)

*Degeneracy in Entanglement Spectra = topologically non-trivial phase*

Ashvin et al. further discovered that the Entanglement Spectrum and the Edge State Spectrum also exhibit a topological equivalence similar to that between the Wilson Loop Spectrum and the Edge State Spectrum. The proof proceeds via a similar interpolation ("continuous deformation") from the entanglement spectrum to the edge state spectrum:

<https://arxiv.org/abs/0909.3119>

Xiaoliang Qi et al. also have related work:

General Relationship between the Entanglement Spectrum and the Edge State Spectrum of Topological Quantum States

![Topological Equivalence between Surface Spectrum & Entanglement Spectrum](/posts/bulk-boundary-correspondence/fig18_surface_entanglement_equivalence.png)

*Topological Equivalence between Surface Spectrum & Entanglement Spectrum*

As shown in the figure above, the Surface Spectrum and Entanglement Spectrum are topologically equivalent, providing us with yet another tool for detecting topological edge states.

## Beyond Traditional BEC

The bulk-boundary correspondence discussed above was one of the most important conclusions in topological band theory during the 2010s, when topological insulators/Chern insulators/topological superconductors dominated the field. However, this is only the simplest version. It is worth noting that "bulk-boundary correspondence" has seen further developments, closely tied to the subsequent discovery of topological crystalline insulators (TCIs) protected by crystal symmetries, as well as the more exotic higher-order topological insulators (HOTIs), fragile topology, and related concepts.

![Family of Topological Band Insulators](/posts/bulk-boundary-correspondence/fig19_family_topo_insulators.png)

*Family of Topological Band Insulators*

These systems exhibit even more remarkable bulk-boundary correspondence phenomena.

### Topological Crystalline Insulators

TCI originated from Liang Fu's PRL:

Topological Crystalline Insulators

It later developed into various lattice-symmetry-protected topological band insulators. Further work by Ashvin, Bernevig, Cano, Jennifer, Barry Bradlyn, and others led to the development of Symmetry Indicators and Topological Quantum Chemistry for systematic ab initio computations:

<https://www.nature.com/articles/s41467-017-00133-2>

<https://www.annualreviews.org/content/journals/10.1146/annurev-conmatphys-041720-124134>

For TCIs, topologically protected edge states exist only on boundaries that preserve the corresponding crystal symmetry. For example, a mirror Chern insulator does not have topologically protected edge states on boundaries that break mirror symmetry. The following figure is from the Topological Crystalline Insulator section of the Weizmann Topological Quantum Matter lecture series — highly recommended.

<https://www.youtube.com/watch?v=ErwkO5H4M4E&t=454s>

![Mirror Chern Insulator (From Weizmann TQM lecture video)](/posts/bulk-boundary-correspondence/fig20_mirror_chern_insulator.png)

*Mirror Chern Insulator (From Weizmann TQM lecture video)*

The identification of TCIs uses tools such as the Wilson Loop; see the article by Xi Dai & Bernevig:

Wilson-loop characterization of inversion-symmetric topological insulators

### Higher Order Topological Insulators

For HOTIs, if the system dimension is $d$, unlike the usual bulk-boundary correspondence where topologically protected edge states exist on the $d-1$ dimensional boundary, HOTIs can have topologically protected edge states on $d-2$, $d-3$, ... dimensional boundaries. Essentially, topologically protected $d-2$ dimensional edge states can be viewed as the $d-1$ dimensional boundary being a topological insulator itself. For 2D systems, we can have topological corner states; for 3D systems, we can have topological hinge states, and so on. The classification of higher-order topological insulators uses generalizations of the Wilson Loop and Entanglement Spectrum: nested Wilson Loops and nested Entanglement Spectrum. A more detailed introduction to HOTIs can be found in articles by Taylor Hughes:

<https://www.science.org/doi/full/10.1126/science.aah6442>

<https://journals.aps.org/prb/abstract/10.1103/PhysRevB.96.245115>

Also refer to articles by Titus:

<https://www.science.org/doi/full/10.1126/sciadv.aat0346>

![Hinge state of HOTI](/posts/bulk-boundary-correspondence/fig21_hinge_state_hoti.png)

*Hinge state of HOTI*

### Fragile Topology

For fragile topology, the traditional bulk-boundary correspondence breaks down, because fragile topology can be trivialized by adding trivial bands. This indicates that the traditional bulk-boundary correspondence and topological classification are not one-to-one. Zhida Song et al. generalized the concept to twisted boundary conditions (TBC) and real space invariants (RSI). In this case, the "bulk-boundary correspondence" is generalized to the necessity of gap closing as twisted boundary condition parameters go through one cycle. Thus, fragile topology can be diagnosed using this generalized "bulk-boundary correspondence." For more details, see this answer. Regarding TBC and RSI, refer to the article by Zhida Song:

<https://www.science.org/doi/full/10.1126/science.aaz7650>

![Spectral flow of fragile topology under TBC](/posts/bulk-boundary-correspondence/fig22_spectral_flow_fragile_TBC.png)

*Spectral flow of fragile topology under TBC*

## Reference

1. Chang, C. Z., Liu, C. X., & MacDonald, A. H. (2023). Colloquium: Quantum anomalous Hall effect. *Reviews of Modern Physics*, 95(1), 011002.

2. Hasan, M. Z., & Kane, C. L. (2010). Colloquium: Topological insulators. *Reviews of Modern Physics*, 82(4), 3045.

3. Shen, S. Q. (2012). *Topological insulators* (Vol. 174). Berlin: Springer.

4. Yu, R., Qi, X. L., Bernevig, A., Fang, Z., & Dai, X. (2011). Equivalent expression of $\mathbb{Z}_2$ topological invariant for band insulators using the non-Abelian Berry connection. *Physical Review B*, 84(7), 075119.

5. Bercioux, D., Cayssol, J., Vergniory, M. G., & Calvo, M. R. (Eds.). (2018). *Topological matter: lectures from the topological matter school 2017* (Vol. 190). Springer.

6. Marzari, N., Mostofi, A. A., Yates, J. R., Souza, I., & Vanderbilt, D. (2012). Maximally localized Wannier functions: Theory and applications. *Reviews of Modern Physics*, 84(4), 1419.

7. Marzari, N., & Vanderbilt, D. (1997). Maximally localized generalized Wannier functions for composite energy bands. *Physical Review B*, 56(20), 12847.

8. Resta, R. (2002). Why are insulators insulating and metals conducting?. *Journal of Physics: Condensed Matter*, 14(20), R625.

9. Resta, R. (2022). Geometry and topology in electronic structure theory. Università degli Studi di Trieste.

10. Fidkowski, L., Jackson, T. S., & Klich, I. (2011). Model characterization of gapless edge modes of topological insulators using intermediate Brillouin-zone functions. *Physical Review Letters*, 107(3), 036601.

11. Li, H., & Haldane, F. D. M. (2008). Entanglement spectrum as a generalization of entanglement entropy: Identification of topological order in non-Abelian fractional quantum Hall effect states. *Physical Review Letters*, 101(1), 010504.

12. Fidkowski, L. (2010). Entanglement spectrum of topological insulators and superconductors. *Physical Review Letters*, 104(13), 130502.

13. Turner, A. M., Zhang, Y., & Vishwanath, A. (2009). Band topology of insulators via the entanglement spectrum. arXiv:0909.3119.

14. Qi, X. L., Katsura, H., & Ludwig, A. W. (2012). General relationship between the entanglement spectrum and the edge state spectrum of topological quantum states. *Physical Review Letters*, 108(19), 196402.

15. Fu, L. (2011). Topological crystalline insulators. *Physical Review Letters*, 106(10), 106802.

16. Po, H. C., Vishwanath, A., & Watanabe, H. (2017). Symmetry-based indicators of band topology in the 230 space groups. *Nature Communications*, 8(1), 50.

17. Cano, J., & Bradlyn, B. (2021). Band representations and topological quantum chemistry. *Annual Review of Condensed Matter Physics*, 12, 225-246.

18. Alexandradinata, A., Dai, X., & Bernevig, B. A. (2014). Wilson-loop characterization of inversion-symmetric topological insulators. *Physical Review B*, 89(15), 155114.

19. Benalcazar, W. A., Bernevig, B. A., & Hughes, T. L. (2017). Quantized electric multipole insulators. *Science*, 357(6346), 61-66.

20. Benalcazar, W. A., Bernevig, B. A., & Hughes, T. L. (2017). Electric multipole moments, topological multipole moment pumping, and chiral hinge states in crystalline insulators. *Physical Review B*, 96(24), 245115.

21. Schindler, F., Cook, A. M., Vergniory, M. G., Wang, Z., Parkin, S. S., Bernevig, B. A., & Neupert, T. (2018). Higher-order topological insulators. *Science Advances*, 4(6), eaat0346.

22. Song, Z. D., Elcoro, L., & Bernevig, B. A. (2020). Twisted bulk-boundary correspondence of fragile topology. *Science*, 367(6479), 794-797.

23. Mong, R. S., & Shivamoggi, V. (2011). Edge states and the bulk-boundary correspondence in Dirac Hamiltonians. *Physical Review B*, 83(12), 125109.
