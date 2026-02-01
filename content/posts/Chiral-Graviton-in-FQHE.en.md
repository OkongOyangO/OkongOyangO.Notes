---
title: "🤯Chiral Graviton in Fractional Quantum Hall Effect (FQHE)"
date: 2024-04-05T12:00:00+08:00
draft: false
math: true
tags: ["FQHE", "Graviton", "Metric", "Quantum Geometry"]
categories: ["Physics Notes"]
---

This article aims to briefly introduce the theoretical and experimental detection methods related to "chiral graviton" excitations in fractional quantum Hall liquids, providing material for the recent heated discussions in related fields. My ability is limited, so I welcome any corrections from experts.

<!--more-->

## Introduction

Recently, Lingjie Du's group at Nanjing University, in collaboration with colleagues from Germany and the United States, published a paper in Nature on the experimental detection of "Chiral Graviton" excitations in Fractional Quantum Hall (FQH) liquids. This was subsequently hyped by various media outlets, sparking a series of discussions within and outside the condensed matter physics community regarding the use of the term "graviton" in the paper and the naming conventions for various quasiparticles in condensed matter physics.

https://www.nature.com/articles/s41586-024-07201-w

This article does not intend to join the debate, as science itself is innocent, and it is often the execution by others that goes awry. Therefore, we might as well take this opportunity to understand the relevant theoretical and experimental knowledge and enjoy the scientific spectacle.

For prerequisite content such as the Fractional Quantum Hall Effect, you can refer to the notes I wrote a few years ago:

https://zhuanlan.zhihu.com/p/574597173

Regarding Quantum Geometry, the Quantum Geometry mentioned here refers to a new intrinsic degree of freedom proposed by Haldane for the FQH ground state wave function under an anisotropic mass tensor or Coulomb interaction (Dielectric tensor). This is not entirely the same as the Quantum Geometry defined in a specific parameter space (such as momentum space) of the wave function that I have written about previously.

However, both types of Quantum Geometry reveal a new property of quantum states in addition to the various topological properties that have emerged in recent decades—the importance of geometric properties and their responses. Regarding the latter, its manifestation in the fractional quantum Hall effect and its nonlinear optical and transport responses are hot topics in the field of condensed matter physics recently. Those interested can refer to my previous notes or follow my future updates:

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

Returning to the Quantum Geometry proposed by Haldane as a new intrinsic degree of freedom of the FQH wave function, later researchers found that this Quantum Geometry not only describes a parameter of the FQH ground state wave function but can also be regarded as a dynamic parameter. It corresponds to the dynamics of the most important collective neutral excitation in FQH—the magnetoroton excitation—in the long-wavelength limit. Since this long-wavelength magnetoroton excitation is extremely difficult to observe and originates from intrinsic Quantum Geometry Dynamics, condensed matter theorists have also termed this excitation mode "graviton" (some literature still refers to it as the magnetoroton in the long-wavelength limit, but that isn't catchy enough to get funding, just kidding).

This is obviously an analogy with the gravitational waves caused by the curvature of the spacetime metric in general relativity. At the same time, due to the spin-2 characteristic of this excitation, it is also analogous to the spin-2 graviton that we hope to quantize in quantum field theory. This can be said to be brushing against High Energy physics, or it can be said to be an extension and enrichment of the concept of the graviton in condensed matter systems. After all, concepts from high energy physics such as Weyl Fermions and Majorana Fermions have also been introduced into the field of condensed matter physics, which is often commonplace for insiders.

Furthermore, this graviton also possesses chirality. For example, in an FQH state with filling $$\nu = 1/3$$, its Graviton excitation not only has spin 2 but also has an angular momentum of -2. Conversely, in its particle-hole conjugate FQH state with filling $$\nu = 1 - 1/3$$, the spin angular momentum of the Graviton excitation becomes 2. This selectivity of the Graviton Angular Momentum by different FQH states echoes what we commonly call Chirality. We thus further refer to the long-wavelength elementary excitation based on intrinsic Quantum Geometry dynamics in FQH as the "Chiral Graviton," which is also the naming convention we see in the title of the Nanjing University paper.

## Anisotropic FQHE and Intrinsic Quantum Geometry

Ultimately, the appearance of the Graviton is inseparable from the Intrinsic Quantum Geometry of Anisotropic FQHE proposed by Haldane. For relevant details, see Haldane's original paper:

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.116801

### Band and Dielectric Anisotropy: Galilean and Coulomb (Interaction) Metric

Specifically, Haldane added the anisotropy of the band mass tensor and Coulomb potential to the Hamiltonian in a general magnetic field, using the Galiean metric $$g^{ab}$$.
$$
H = H_0 + V 
$$
Non-interacting part:
$$
H_0 = \frac{1}{2} (m^{-1})^{ab} \pi_a\pi_b =  \frac{1}{2m} g^{ab} \pi_a\pi_b,
\quad \bm \pi = \bm p - e\bm A,
$$
where the non-commutative algebra of the mechanical momentum brought by the magnetic field is,
$$
[r_i^a,\pi_{jb}]= i\delta_{ij}\hbar \delta^a_b, \quad 
[\pi_{ia},\pi_{jb}] = i\delta_{ij}\epsilon_{ab}\hbar^2/\ell_B^2.
$$
where $$\ell=\sqrt{\hbar/(eB)}$$ is the magnetic length.

This non-commutative algebra can give different LLL (Lowest Landau Level) single-particle wavefunctions under various gauge selections. For example, under the isotropic condition $$g^{ab} = \delta^{ab}$$ and symmetric gauge, the rotational symmetry of the system can be preserved, so the LLL single-particle wavefunction can be a common eigenstate of $$H_0$$ and the angular momentum $$L_z$$. The LLL single-particle wavefunction constructed in this way and the Laughlin many-body wavefunction constructed on this basis are both rotationally symmetric.

But Haldane considered a more general anisotropic Galilean metric, where $$g^{ab}$$ is not isotropic. At the same time, Haldane further considered the interaction anisotropy characterized by the interaction metric $$\tilde g^{ab}$$:
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
These two types of anisotropy come from the anisotropy of the band mass tensor and the dielectric tensor, respectively, and can be two independent metrics. previously, the FQH systems we considered often assumed both metrics to be isotropic by default, so the obtained wavefunctions were also isotropic. This fails to reflect the anisotropy that may appear in the wavefunction itself and its intrinsic quantum geometry information.

Now, to discuss the anisotropy of the band mass tensor and dielectric tensor, we need to construct anisotropic LLL wavefunctions similar to the isotropic case. In this process, we will discover the intrinsic quantum geometric degrees of freedom of the system itself.

### Landau Level with Anosotropic Galilean metric

First, let's consider the construction of the anisotropic LLL single-particle wavefunction, which is completely a generalization of the isotropic case. Details can be found in:

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.115308

Specifically, at this time we only need to consider the anisotropy of the mass tensor. We can use a unimodular complex vector $$\omega$$ to parametrize the mass tensor:
$$
m_{ab}=m (\omega_a^*\omega_b + \omega_b^*\omega_a)
$$
$$
(m^{-1})^{ab}=m^{-1}(\omega^{a*}\omega^b + \omega^{b*}\omega^a).
$$
It is not difficult to find that the special case of isotropic is $$\omega = \frac{1}{\sqrt{2}} (1, i)^T$$, and a more general $$\omega$$ represents the general anisotropic case, which relates to our discussion of the connection between the two and the analogy and generalization from the former to the latter.

#### Construction of Landau Level and Guiding Center Ladder Operators

The single-particle Hamiltonian can be expressed as:
$$
H_0 ={\textstyle \frac{1}{2}}\hbar \omega_c
\left( b^{\dagger}b + bb^{\dagger}\right)
$$
where $$\hbar\omega_c = \hbar^2/m\ell^2$$ is the cyclotron energy. The Landau Level ladder operators under anisotropic conditions can be generalized to:
$$
b = \hbar^{-1}\ell \left (\bm \omega \cdot \bm \pi\right ),
\quad b^\dagger = \hbar^{-1}\ell \left (\bm \omega^* \cdot \bm \pi\right )
$$
The ladder operators satisfy the commutation relation $$[b,b^{\dagger}] = 1$$. This ladder operator is used to raise and lower the wavefunction between different Landau Levels, with a difference of one cyclotron energy before and after.

Further introduce "guiding center" coordinates $${\bm R}$$:
$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
The "guiding center" coordinate operators satisfy:
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
The "guiding center" coordinates $${\bm R}$$ are used to generate "guiding center" ladder operators: $$a$$, $$a^{\dagger}$$:
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
This set of creation and annihilation operators commutes with the Landau Level ladder operators $$b$$ and $$b^{\dagger}$$, and can thus describe the degeneracy of the LLL single-particle wavefunction within the same Landau Level. This is also a classic operation in isotropic LL derivation.

It is worth noting that the above discussion can obtain information such as Landau Level and its degeneracy without introducing a specific gauge. In other words, the construction of the LLL wavefunction does not require introducing a symmetric gauge to preserve rotational symmetry. This shows that the isotropic nature of QH and FQH states that we assumed by default in the past is itself accidental. We are completely free to choose anisotropic LLL wavefunctions to construct the degrees of freedom of FQH theory, which was ignored before.

For more detailed derivation, please refer to UCSD's QHE related notes:

https://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf

#### Introduction of Symmetric Gauge

Furthermore, we will show that we can construct anisotropic LLL wavefunctions even under the symmetric gauge. This is because LLL wavefunctions are often determined by the common eigenstates of the Hamiltonian $$H_0$$ and angular momentum $$L_z$$. We will show that we can obtain different LLL single-particle wavefunctions as the basis for discussing FQH by constructing an anisotropic $$L_z$$.

We now choose the symmetric gauge:
$$
{\bm A}={\textstyle\frac{1}{2}}{\bm B}\times{\bm r}={\textstyle\frac{1}{2}}B(-y,x),
$$
And use $$\omega$$ containing mass tensor anisotropy information to construct the complex coordinate:
$$
z = \frac{\bm \omega \cdot \bm r}{\ell}.
$$
In the special case of an isotropic mass tensor, we have,
$$z = \frac{x+iy}{\sqrt{2}\ell}$$
We can skillfully construct the representation of the Landau Level and guiding center ladder operators under complex coordinates. It is not difficult to prove that this also holds under any anisotropic mass tensor. Here we directly give the conclusion:
$$
b = {\textstyle \frac{1}{2}}z + \partial_{z*} ,\quad  b^{\dagger} =
{\textstyle \frac{1}{2}}z^* - \partial_{z}
$$
$$
a = {\textstyle \frac{1}{2}}z^* + \partial_{z} ,\quad  a^{\dagger} =
{\textstyle \frac{1}{2}}z - \partial_{z^*}
$$
The corresponding angular momentum operator can be defined as:
$$L_0 = a^{\dagger}a - b^{\dagger}b, \quad [L_0,H_0] =0$$
Simultaneous diagonalization of $$H_0$$ and $$L_0$$ yields the n-th LL single-particle wavefunction $$|\psi_{nm}\rangle$$:
$$
\begin{aligned}
&H_0|\psi_{nm}\rangle = (n+{\textstyle\frac{1}{2}})\hbar
\omega_c|\psi_{nm}\rangle, \\
&L_0|\psi_{nm}\rangle = (m-n)|\psi_{nm}\rangle, \\
&|\psi_{nm}\rangle =
\frac {(a^{\dagger})^m(b^{\dagger})^n}{\sqrt{m!n!}}|\psi_{00}\rangle\\
& a|\psi_{00}\rangle = b|\psi_{00}\rangle = 0.
\end{aligned}
$$
The above process is just a generalization of changing $$\omega = \frac{1}{\sqrt{2}} (1,i)^T$$ to an arbitrary unimodular vector. It shows that for a general Galilean metric, we can still construct an anisotropic mass tensor adapted angular momentum operator to generate the "rotational symmetry" of the system. This is similar to stretching an ellipse into a circle, which is still isotropic to some extent, but up to an anisotropic mass tensor.

### Intrinsic Quantum Geometry of FQH state: Guiding Center Metric

But does this mean that the Galilean metric is the direction of anisotropy that the system "tends" to choose? No. We can also modify the definition of $$L_0$$ (that is, modify the degrees of freedom of the Guiding center Metric) to show that before introducing interaction and Coulomb metric, our wavefunction selection still has an intrinsic quantum geometry degree of freedom to choose from.

Our Guiding Center $$R$$, and its ladder operators $$a,\,a^\dagger$$, were constructed to specify the degenerate state within a unified LL. However, as we learned when first studying quantum mechanics, the selection of a complete basis for degenerate states is not unique. We can completely perform a unitary transformation on this set of bases to obtain a new set of complete bases. In the context of our discussion on the Guiding Center, recall our previous construction of the Guiding Center Ladder Operator:

$$
R^a=r^a+\hbar^{-1}\ell^2\epsilon^{ab}\pi_b,
$$
The "guiding center" coordinate operators satisfy:
$$
[R^a, R^b]=-i\epsilon^{ab}\ell^2,\quad [R^a,\pi_b]=0,
$$
Construction of "guiding center" ladder operators: $$a$$, $$a^{\dagger}$$:
$$
a=\ell^{-1}\left({\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left({\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
It is not difficult to find that we presumptuously used the unimodular vector $$\omega$$ defined by the Galilean Metric to define the ladder operator of the Guiding center. But we said: we can completely perform a unitary transformation on this set of bases to obtain a new set of complete bases. This is completely fine in the non-interacting case. Our system currently has no reason to specify the Galilean metric as its intrinsic property. Conversely, this uncertainty in the selection of the complete basis gives us a new degree of freedom for constructing the LLL single-particle wavefunction, namely the degree of freedom of the Guiding Center Metric. This will later evolve into the Intrinsic Quantum Geometric degree of freedom that we often discuss in FQH (metric and geometry are often inseparable).

In the article "Model Anisotropic quantum Hall states" by RZ Qiu, FDM Haldane, X Wan, K Yang, S Yi et al., it is explained as follows:

We first split the angular momentum operator:
$$
L_0 = L + \bar L
$$
$$
L  = {\textstyle\frac{1}{2}}(b^{\dagger}b + bb^{\dagger})
$$
$$
H_0  =  \hbar \omega_c L
$$
$$
\bar L = {\textstyle\frac{1}{2}}(a^{\dagger}a + aa^{\dagger}).
$$
It is not difficult to find that $$L$$ in $$L_0 = L + \bar L$$ already commutes with $$H_0$$, so the nontrivial part of $$L_0$$ comes from $$\bar L$$.

Then the common eigenstates of $$H_0$$ and $$\bar L$$ that we originally defined can determine the m-th degenerate wavefunction of the n-th LL
$$
\bar L |\psi_{nm} \rangle =
(m+{\textstyle\frac{1}{2}})|\psi_{nm}\rangle
$$
To reflect how the Galilean metric "presumptuously" entered our construction of the Guiding center Degeneracy degree of freedom in the above discussion, we can write $$\bar L$$ as:
$$
\bar L = \bar L(g^0)
$$
And define $$\bar L$$ under an arbitrary guiding center metric:
$$
\bar L(g) =  \frac{1}{2\ell^2}g_{ab}R^aR^b
$$
Here we denote the "Galilean metric" from the band mass tensor as $$g^0_{ab}$$ to reflect its distinctiveness. At the same time, we also use a unimodular vector $$\bar \omega$$ to define an arbitrary guiding center metric.

For $$\bar L$$ under an arbitrary guiding center metric:
$$
m_{ab}=m(\omega^*_a\omega_b+\omega^*_b\omega_a)=mg^0_{ab}.
$$
Similarly, $$\bar \omega$$ can be used to parametrize any guiding center metric:
$$
g_{ab} = \bar \omega^*_a \bar \omega_b+ \bar \omega^*_b \bar \omega_a.
$$
This is equivalent to choosing the following when constructing the "guiding center" ladder operators: $$a$$, $$a^{\dagger}$$:
$$
a=\ell^{-1}\left(\bar {\bm \omega}^*\cdot{\bm R}\right),
\quad a^\dagger=\ell^{-1}\left( \bar {\bm \omega}\cdot{\bm R}\right),
\quad [a,a^\dagger]=1
$$
From $$\omega$$ to an arbitrary $$\bar \omega$$, or equivalently, from $$g_0^{ab}$$ to an arbitrary guiding center metric $$g^{ab}$$, is equivalent to performing a Bogoliubov Transformation on the ladder operator used to distinguish degeneracy within the LL. This shows that the complete basis describing LL degeneracy itself remains complete, it's just that a more natural, more arbitrary basis has been swapped in, one that is not "presumptuously" selected by the Galilean metric.

This is reasonable in the non-interacting context. After we introduce interaction and the Coulomb metric, this arbitrary guiding center metric/Intrinsic Quantum Geometry becomes a variational parameter of the many-body wavefunction. The system will tend to choose the many-body wavefunction, such as the Laughlin state, composed of the guiding center metric with the lowest energy.

In order to distinguish the difference between the guiding center metric $$\bar \omega_a$$ and the original Galilean metric $$\omega$$, RZ Qiu, FDM Haldane, X Wan, K Yang, S Yi et al. further introduced a complex number $$\gamma$$ to parametrize the difference between the two.

This parameter satisfies $$|\gamma| < 1$$. Its physical meaning is similar to eccentricity, used to define anisotropy up to a Galilean metric. We can discover this in the features of the single-particle wavefunction later.

Specifically, the guiding center metric parametrized by $$\gamma$$ can be further expressed as
$$
\bar \omega_a = (1-|\gamma|^2)^{-1/2}(\omega_a + \gamma^* \omega_a^*),
$$
that determines a unimodular metric $$g_{ab}(\gamma)$$，
$$
\begin{aligned}
g_{ab}(\gamma) & = \bar \omega_a^*\bar \omega_b+\bar \omega_a\bar \omega_b^* \\
& = \frac{1}{1-\gamma^*\gamma}\left(\begin{array}{cc}
(1+\gamma)(1+\gamma^*) & i(\gamma-\gamma^*)\\
i(\gamma-\gamma^*) & (1-\gamma)(1-\gamma^*) \\
\end{array}\right)\nonumber
\end{aligned}
$$
A new set of "guiding center" ladder operators defined by it is:
$$
a_\gamma =\frac{{\bar {\bm\omega}^*}\cdot{\bm R}}{\sqrt{2}\ell} ,\quad
 a_\gamma^\dagger =
\frac{{\bar {\bm\omega}}\cdot{\bm R}}{\sqrt{2}\ell}
$$
This is indeed the Bogoliubov transformation we mentioned earlier:
$$
\left(\begin{array}{c}
a_\gamma \\
a_\gamma^\dag \\
\end{array}\right)
=\frac{1}{\sqrt{1-\gamma^*\gamma}}
\left(\begin{array}{cc}
1 & \gamma  \\
\gamma^*  & 1 \\
\end{array}\right)
\left(\begin{array}{c}
a \\
a^\dag \\
\end{array}\right).
$$
This shows that the selection from the Galilean metric to a general guiding center metric is just selecting a new complete basis for the LL degeneracy.

The similarly constructed LL single-particle wavefunction is:
$$
|\psi_{nm}(\gamma)\rangle
=\frac{(b^\dag)^n(a^{\dagger}_{\gamma})^m}{\sqrt{n!m!}}
|\psi_{00}(\gamma)\rangle
$$
Where $$|\psi_{00}(\gamma)\rangle$$ is the basis in the LLL single-particle wavefunction used to generate other LLL degenerate wavefunctions, satisfying:
$$
a_{\gamma}|\psi_{00}(\gamma)\rangle =
b|\psi_{00}(\gamma)\rangle  = 0.
$$
Afterwards, we can similarly define the LLL single-particle wavefunction under an arbitrary guiding center metric, in order to facilitate the construction of many-body wavefunctions such as Laughlin and MR that contain the guiding center metric variational parameter. We will not go into details here; please refer to the original text for specific details.

In summary, in the process of constructing the LL single-particle wavefunction, we discovered a new degree of freedom defined by the system's guiding center metric. In the case where there is only the Galilean metric, i.e., no interaction, its selection is arbitrary. Essentially, this new degree of freedom comes from the freedom of selecting the degenerate complete basis inside the LL. In the process of introducing interaction and constructing many-body wavefunctions such as Laughlin and MR, this Intrinsic Quantum Geometry degree of freedom in the FQH state will become a variational parameter, selecting the guiding center metric/Intrinsic Quantum Geometry that minimizes the energy of the system and state within the more general anisotropic Galilean metric and interaction metric.

This process is also described as "Compromise of Intrinsic Geometry between Galilean and Coulomb Metric". We will discuss the selection of Intrinsic Geometry after introducing interaction in the next subsection.

### Compromise of Intrinsic Geometry between Galilean and Coulomb Metric

As mentioned before, after we introduce interaction, the Hamiltonian is:
$$
H=T+V,
$$
The kinetic energy contains the Galilean metric, which is one of the sources of the anisotropy QH/FQH state, generally written as:
$$
T=\frac{1}{2}(m^{-1})^{\mu\nu}\Pi_{\mu}\Pi_{\nu} = \frac{g^{\mu\nu}\Pi_{\mu}\Pi_{\nu}}{2m},
$$
For simplicity, by redefining basis, we can also write it as;
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
In this way, $$a=1$$ degenerates to the isotropic case, and a general $$a$$ represents the selection of a general anisotropic Galilean metric. This is equivalent to selecting the Galilean metric:
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
Similar definitions of mechanical momentum and guiding center coordinate are:
$$
{\bf \Pi}={\bf p}+{e\over c}{\bf A}({\bf r})
$$
$$
{\bf R}={\bf r}-(\ell^2/\hbar)\hat{z}\times{\bf \Pi}
$$
Consider the two-body interaction, its expression in real space and momentum space is:
$$
V=\sum_{i < j} V({\bf r}_i-{\bf r}_j)=\frac{1}{2}\sum_{\bf q}V_{\bf q}\rho_{\bf q}\rho_{-{\bf q}},
$$
Where the density operator in momentum space is:
$$
\rho_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf r}_i}
$$
Generally we will also have the interaction anisotropy characterized by anisotropic $$\tilde g^{ab}$$:
$$
\lim_{\lambda \rightarrow 0} \lambda V(\lambda \bm q) \rightarrow 
\frac{e^2}{2\varepsilon}(\tilde g^{ab}q_aq_b)^{-1/2} ,
$$
These two anisotropies: the anisotropy of the band mass tensor and the dielectric tensor, can be two mutually independent metrics. For simplicity, we can only consider the case of anisotropic band mass tensor + isotropic Coulomb interaction, because our main purpose is to see how the guiding center metric selects the ground state with lower energy after adding interaction, so that the arbitrary guiding center metric selection in the noninteracting problem becomes an intrinsic property of the FQH many-body state in the interacting problem.

#### Projected Interaction

To simplify the model, we consider the case where the magnetic field is very large, and the splitting $$\hbar \omega_c$$ between LLs is much larger than the interaction scale $$e^2/a$$, so that we can assume that the wavefunction basically does not enter the higher landau level, and thus the entire problem can be projected to the LLL for discussion. This is also a customary operation when discussing fractional Chern insulators. Those interested can refer to:

https://zhuanlan.zhihu.com/p/574597173

https://zhuanlan.zhihu.com/p/580756343

https://zhuanlan.zhihu.com/p/586913698

https://zhuanlan.zhihu.com/p/580954377

https://zhuanlan.zhihu.com/p/581596244

https://www.zhihu.com/question/616351382/answer/3157331169

Specific details can be found in:

https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.241105

Specifically, the interaction under the general LL basis can be expressed as:
$$
\tilde{V}=\sum_{i < j}\sum_{\bf q}v_{\bf q} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}F_n({\bf q}, a),
$$
The coefficient is:
$$
F_n({\bf q}, a)=|\langle n|e^{i{\bf q}\cdot(\hat{z}\times{\bf \Pi})}|n\rangle|^2 = e^{-(aq_x^2+q_y^2/a)\ell^2/2}|L_n[(aq_x^2+q_y^2/a)\ell^2/2]|^2
$$
For LLL projected interaction, the coefficient is:
$$
F_0({\bf q}, a)=e^{-(aq_x^2+q_y^2/a)\ell^2/2}.
$$
LLL projected interaction is
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
Where the LLL projected density operator is:
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
The GMP algebra it satisfies is also an important element in the construction of fractional Chern insulators. But here we focus on the form of LLL projected interaction. We see that although the original Coulomb interaction is isotropic, due to the anisotropy of the Galilean metric when constructing the LLL wavefunction, the anisotropy of the band mass tensor enters the anisotropy of the projected interaction. Since the single-particle energy of the LLL is always the same, we only need to consider the LLL projected interaction and consider which wavefunction minimizes its energy (variational method).

#### Gaussian Interaction

Even with so many simplifications, the general form of interaction is difficult to calculate analytically. We further consider a special case, that is, the case where the Coulomb potential is a Gaussian function, which roughly describes the characteristics of a screened Coulomb interaction.

Isotropic interaction is reflected in the isotropy of the coefficient distribution of $$V_q$$: $$v({\bf r})=v(r)$$, $$v_{\bf q}=v_q$$.

Further consider Gaussian Interaction:
$$
v(r)=v(0)e^{-r^2/(2s^2)}
$$
Thus the interaction in momentum space is also in Gaussian form:
$$
v_q=v_0e^{-q^2s^2/2}
$$
Further written as:
$$
\tilde{V}_g=\sum_{i < j}\sum_{\bf q}v_0 e^{-\tilde{q}^2\tilde{s}^2/2} e^{i{\bf q}\cdot({\bf R}_i-{\bf R}_j)}
$$
Where
$$
\tilde{s}=[(a\ell^2+s^2)(\ell^2/a+s^2)]^{1/4}
$$
$$
\tilde{q}^2=g q_x^2 + q_y^2/g,
$$
$$
g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}.
$$
Although the above steps are simple mathematical derivations, we will later find that $$g$$ defined here is directly related to the anisotropy of the guiding center metric discussed in the previous section. Moreover, under this special Gaussian Interaction, $$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$$ directly gives a guiding center metric selection that minimizes the energy of the many-body ground state wavefunction in the interaction problem.

First, let's look at some properties of g here:

$$g\rightarrow a$$ for $$s\ll \ell$$, $$g\rightarrow 1$$ for $$s\gg \ell$$

At the same time, generally we have:
$$
1 < g < a
$$
In fact, the lower bound 1 reflects the isotropic interaction metric, and the upper bound $$a$$ reflects the anisotropic mass tensor metric. If we accept the previous statement regarding $$g$$ being the intrinsic quantum geometry anisotropy information of the optimal ground state selection, this inequality indeed reflects the discussion at the beginning of this section:

Intrinsic Geometry as a Compromise between Galilean and Coulomb Metric.

#### Many-Body Ground State of Anisotropic FQHE

Below we prove the connection between $$g$$ and the FQH state Intrinsic quantum geometry/guiding center metric through some arguments, and explain why $$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}$$ is the optimal selection for variational parameters of many-body wavefunctions such as Laughlin.

First, we can establish the connection between general $$g$$ and the special case of $$g=1$$:
$$
\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)],
$$
Where:
$$
O(\lambda)=e^{{i\lambda\over 2\ell^2}\sum_j R^j_x R^j_y},
$$
$$
\lambda(g)=-{1\over 2}\ln g
$$
$$
O^\dagger(\lambda)R_x^i O(\lambda)=e^{\lambda} R_x^i
$$
$$
O^\dagger(\lambda)R_y^i O(\lambda)=e^{-\lambda} R_y^i.
$$
This process of guiding center changing from isotropic to anisotropic is consistent with the operation of selecting different guiding center metrics to construct guiding center operators and thus constructing a set of complete degenerate bases inside the LL. This explains the connection between $$g$$ and the FQH state Intrinsic quantum geometry/guiding center metric.

Furthermore, since we know that $$g=1$$ is the special case of isotropic, at this time we know that the ground state under Interaction LLL is the Laughlin State (strictly speaking, the Laughlin State is the strict ground state under the 2-body Haldane Pseudopotential, but we tentatively assume that the Laughlin state is still close to the FQH ground state under Gaussian interaction), then the ground state of $$\tilde{V}_{g=1}$$ (kinetic energy can be ignored) is $$|\Psi_{GS,g=1}\rangle \approx |\Psi_{Laughlin} \rangle$$,

Thus the ground state of the transformed $$\tilde{V}_g=O^\dagger[\lambda(g)]\tilde{V}_{g=1} O[\lambda(g)]$$ can be roughly considered to be (Hamiltonian differs by a Unitary transformation, the energy spectrum does not change, and the corresponding wavefunction including the ground state should also only differ by the same Unitary transformation):
$$
|\Psi_{GS,g}\rangle=O^\dagger[\lambda(g)]|\Psi_{g=1}\rangle \approx O^\dagger[\lambda(g)] |\Psi_{Laughlin} \rangle =|\Psi^{Laughlin}_{g}\rangle
$$
Coupled with the previous point that $$g$$ represents the information of the system's guiding center metric anisotropy, we can consider that $$|\Psi^{Laughlin}_{g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)}}\rangle$$ is the optimal variational ground state solution for the more general Laughlin wavefunction with guiding center metric anisotropy/Intrinsic quantum geometry as variational parameters under anisotropic mass tensor + isotropic gaussian interaction.

Thus $$g=\sqrt{(a\ell^2+s^2)/(\ell^2/a+s^2)} \in (1,a)$$ completely reflects the determination of the Intrinsic Geometry of FQH under different interactions. Qualitatively, it is still the discussion at the beginning of this section:

Intrinsic Geometry as a Compromise between Galilean and Coulomb Metric

So far, we have explained the origin of the Intrinsic Quantum Geometry degree of freedom inside FQH and its determination from a variational Compromise between Galilean and Coulomb Metric. This shows that even in a system that breaks rotational symmetry, the anisotropic FQH state may still be the ground state. If we further consider the perturbation coupled with the Intrinsic Quantum Geometry degree of freedom, we can focus on the dynamics of this Intrinsic Quantum Geometry, which turns out to be the chiral graviton mode discovered by Nanjing University.

## Dynamics of Intrinsic Quantum Geometry as Chiral Graviton

Below we consider the dynamics of Intrinsic Quantum Geometry in the FQH state and its quasiparticle excitation, the Chiral Graviton.

### Dynamics of Intrinsic Quantum Geometry

The most direct idea is to find a perturbation that directly couples with Intrinsic Quantum Geometry, but this is generally difficult to achieve. In the model, the degree of freedom that is easier to couple directly is the band mass tensor, for example, using acoustic waves to perturb the FQH background lattice system. We tentatively assume that our picture of Intrinsic Quantum Geometry determined by band mass tensor anisotropy under Gaussian Interaction discussed above is also feasible in more general cases. Then we can consider that coupling the band mass tensor is equivalent to indirectly coupling the Intrinsic Quantum Geometry.

For simplicity, still use the kinetic energy:
$$
T=\sum_j{1\over 2m}\left[a(\Pi^j_x)^2+(\Pi^j_y)^2/a\right].
$$
This is equivalent to selecting the Galilean metric:
$$
g_{ab} = \begin{pmatrix}
a & 0 \\
0 & a^{-1}
\end{pmatrix}
$$
Consider the general LLL projected interaction again:
$$
\tilde{V}=\frac{1}{2}\sum_{\bf q}V_{\bf q}e^{-\frac{1}{2}(aq_x^2+q_y^2/a)\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
$$
\overline{\rho}_{\bf q}=\sum_{i}e^{i{\bf q}\cdot{\bf R}_i}
$$
Assume we perform a time-dependent perturbation on the band mass anisotropy through acoustic wave:
$$
a=1+\xi(t)
$$
This will be reflected in the oscillating metric through $$g = g(a)$$. We know that the physical image of the oscillating metric is the gravitational wave. Then the quasiparticles excited by the oscillating metric are very likely to have similar properties to the graviton discussed in high energy physics.

Expand $$\tilde{V}$$ according to $$a=1+\xi(t)$$:
$$
\delta\tilde{V}(t)=\frac{\xi(t)}{4}\sum_{\bf q}(q^2_y - q^2_x)V_{\bf
q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf q}\overline{\rho}_{-{\bf q}}.
$$
We find that the part of $$(q^2_y - q^2_x)$$ indeed has d-wave symmetry. This shows that the quasiparticles excited by the oscillating metric are likely to be quasiparticles with spin 2. This "coincides" with the spin-2 nature of the graviton widely believed in high energy physics (essentially because both are oscillations of the metric field, it is not difficult to guess that their quantum have similar properties).

For harmonic perturbation, the experimentally measured spectral function is not difficult to obtain through the well-known Fermi Golden Rule:
$$
I(\omega)=\sum_n|\langle n|\hat{O}|0\rangle|^2\delta(\omega-\omega_n),
$$
Where the perturbation operator is:
$$
\hat{O}=\sum_{\bf q}(q^2_y - q^2_x)V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}}
$$
We can further split this perturbation operator into the form of $$S_z = \pm 2$$:
$$
\hat{O}_\mp^{(2)}=\sum_{\bf q}(q_x \mp i q_y)^2 V_{\bf q}e^{-\frac{1}{2}q^2\ell^2}\overline{\rho}_{\bf
q}\overline{\rho}_{-{\bf q}},
$$
These two operators reflect the graviton excitation with spin $$S_z = \pm2$$ respectively. The corresponding spectrum is:
$$
I_\sigma(\omega)=\sum_n|\langle n|\hat{O} _{\sigma}|0\rangle|^2\delta(\omega-\omega_n),
$$
Where $$\hat{O}_\mp$$ can be regarded as the creation and annihilation operator of the graviton. Here it is equivalent to us specifying that the generated quasiparticle excitation can only be $$S_z = -2$$, so this graviton excitation is also called Chiral Graviton. We will explain the source of this choice later. Conversely, for the particle-hole conjugate FQH state, the spin of the graviton excitation is opposite, which further reflects its Chiral nature.

And $$\hat{O}=(\hat{O} _{+} + \hat{O} _{-})/2$$ is equivalent to the displacement operator in a harmonic oscillator, coupled with the "gravitational wave" (essentially acoustic wave induced oscillating mass tensor anisotropy) as a perturbation operator.

### Chirality of Graviton

Why is the Graviton excitation chiral? We analyze it using the Laughlin state of $$\nu = 1/3$$ as an example. It is not difficult to find that when $$\hat{O}_\mp$$ acts on the 2 particle wave function, we have
$$
O_{+} \propto \sum\limits_{M} |m+2, M \rangle \langle m, M|
$$
$$
O_{-} \propto \sum\limits_{M} |m, M \rangle \langle m + 2, M|$$
Where $$m$$ and $$M$$ in $$|m, M \rangle$$ represent the relative angular momentum and center-of-mass angular momentum of the two-body wavefunction state, respectively.

It is not difficult to find that $$\hat{O}_{+}$$ will annihilate the Laughlin state: because $$\hat{O}_{+}$$ will change a two-particle state with relative angular momentum $$m$$ to relative angular momentum $$m+2$$, which is not within the Laughlin state, thereby annihilating the Laughlin state.

Thus, the $$I _{+}(\omega)$$ spectrum is always 0. While $$I _{-}(\omega)$$ always shows strong graviton peaks in fermionic and bosonic cases. This shows that the graviton excitation of the Laughlin state of $$\nu = 1/3$$ is always $$S_z  =-2$$; conversely, the graviton excitation of the hole Laughlin state of its PH conjugate $$\nu = 1 - 1/3$$ is always $$S_z  = 2$$. This reflects the chirality of the graviton excitation.

### Inaccessibility of normal Magnetoroton modes

Essentially, the graviton mode is the neutral collective excitation we discuss in FQH: the limit of the GMP magnetoroton mode at $$k\rightarrow 0$$; in other words, in the long-wavelength limit, the dynamics of FQH can be determined by the Intrinsic Quantum Geometry dynamics we discussed above. In some cases, the chiral graviton mode is also referred to as a special case of the GMP magnetoroton mode in the long-wavelength limit. However, due to the structural factor of the GMP magnetoroton mode $$\langle 0|\rho_{{\bf k}}\rho_{-{\bf k}}|0\rangle\propto (k\ell)^4$$ in the long-wavelength limit, it is difficult to detect the GMP magnetoroton mode in the long-wavelength limit using general methods of coupling electromagnetic fields with electron density. For details on the GMP magnetoroton, you can also refer to my previous notes:

https://zhuanlan.zhihu.com/p/574597173

In short, due to the above reasons, although the GMP magnetoroton mode has been observed experimentally, its detection in the long-wavelength limit is difficult. General electromagnetic field perturbations fail because the photon spin is 1, making it difficult to couple with the graviton with spin 2. Thus, the uniqueness of the graviton mode in Intrinsic Quantum Geometry's origin and experimental detection distinguishes it from the general GMP magnetoroton mode, and its detection has become a very meaningful event in the field of condensed matter physics.

### Detection of Chiral Graviton in FQHE

In addition to the above Acoustic wave method, the method used by Nanjing University to detect the graviton utilizes spectroscopy related to circularly polarized light. Because circularly polarized light has a spin of $$S_z = \pm1$$, if circularly polarized light with $$S_z = -1$$ is used to excite a chiral graviton with $$S_z = -2$$, the light emitted after the system absorbs it should be $$S_z = 1$$. Through this principle, Lingjie Du's group at Nanjing University and their colleagues from Germany and the United States successfully discovered the chiral graviton mode in FQHE and published it in Nature. This is the story we are familiar with.

## Relation with Band Geometry from Momentum-Space Duality

The Intrinsic Quantum Geometry of the FQH state we discussed in the above process is different in definition from the Band Geometry we often discuss in fractional Chern insulators, flat band superconductivity, and nonlinear response, but the metric fields of the two are essentially consistent. This idea of Geometric Description of FQH state has also been introduced into systems discussing Band Geometry such as fractional Chern insulators, providing insights into the stability and other properties of FQH states in lattice systems.

For example, a PRL titled "Position-momentum duality and fractional quantum hall effect in chern insulators" by Claassen, M., Lee, C. H., Thomale, R., Qi, X. L., & Devereaux, T. P. et al. in 2015 discussed the connection between Band Geometry and the Intrinsic Quantum Geometry of the FQH state.

Specifically, in the Band System, we have the symplectic geometry of the wave function space (Projected Hilbert Space $$\mathbb{C}P^{N-1}$$), the imaginary part of which is the Berry Curvature we are familiar with, similar to the magnetic field in momentum space:
$$
\Omega(k) = \epsilon^{\mu\nu} \partial_{k_\mu} \mathbf{A}_\nu(k)
$$
Coming from a vector potential similar to momentum space, Berry Connection:
$$
\mathbf{A}_\nu(k) = -i \langle u_k | \partial_{k_\nu} | u_k \rangle
$$
The real part of the symplectic geometry defines the metric of the wave function space, namely the Fubini-Study metric
$$
g_{\mu\nu}(k) = \frac{1}{2} \langle \partial_{k_\mu} u_k | \left[1 - |u_k\rangle \langle u_k | \right] | \partial_{k_\nu} u_k \rangle + \left(\mu \leftrightarrow \nu \right)
$$
Using a method similar to distinguishing degeneracy in LLL through angular momentum operators in FQH, we can similarly define a confinement potential to coincide with the eigenstates of the Hamiltonian, thereby achieving the purpose of defining "pseudo-angular momentum operators" in lattice systems that break rotational symmetry:
$$
\hat{V}(r)= \tfrac{1}{2} \lambda~ x_{\mu} \eta^{\mu\nu} x_{\nu}
$$
$$\eta^{\mu\nu}$$ can be used to describe the metric used to define the "pseudo-angular momentum operator" in the lattice system that breaks rotational symmetry, that is, the analogy of Guiding Center Metric in Lattice System, which is the Lattice version of Intrinsic Quantum Geometry.

Considering the projection on LLL similarly, the projection of this single-particle "pseudo-angular momentum operator" (essentially an artificial confinement potential) is:
$$
\bar{V} =  \hat P\hat V(r)\hat P^\top= \frac{\lambda}{2} \Pi_\mu \eta^{\mu\nu} \Pi_\nu + \frac{\lambda}{2} \eta^{\mu\nu} g_{\nu\mu},\,k \in {\rm BZ}
$$
The first term on the right is the common kinetic energy operator we see. In addition, there is a term coupled with Band Geometry. This shows that the FQH physics in the Lattice System is also affected by Band Geometry compared to the FQH physics in the continuum system. The coupling between the two gives the physics of Intrinsic Quantum Geometry of FQH in a more general system. Relevant details can be further referred to in the original text:

https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.114.236802

We stop here, just explaining the connection between Intrinsic Quantum Geometry and Band Geometry.

## Summary

In summary, we discussed the recent hot news of "Nanjing University discovering (chiral) graviton (quasiparticle excitation) in FQH system", gave the origin of Intrinsic Quantum Geometry in FQH state, and discussed the origin of the Chiral Graviton mode corresponding to the quasiparticle of its dynamics. We also briefly discussed its detection and its connection with the Band Geometry we are familiar with, hoping to provide more material for everyone to enjoy the scientific spectacle.

## Reference

- [Evidence for chiral graviton modes in fractional quantum Hall liquids](https://www.nature.com/articles/s41586-024-07201-w)

- [Geometrical description of the fractional quantum Hall effect](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.107.116801)

- [Magneto-roton theory of collective excitations in the fractional quantum Hall effect](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.33.2481)

- [Chiral gravitons in fractional quantum hall liquids](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.123.146801)

- [Fractional quantum Hall states in two-dimensional electron systems with anisotropic interactions](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.86.035122)

- [Band mass anisotropy and the intrinsic metric of fractional quantum Hall systems](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.165318)

- [Acoustic wave absorption as a probe of dynamical geometrical response of fractional quantum hall liquids](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.93.161302)

- [Geometry of compressible and incompressible quantum Hall states: Application to anisotropic composite-fermion liquids](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.88.241105)

- [Model anisotropic quantum Hall states](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.85.115308)

- [Position-momentum duality and fractional quantum hall effect in chern insulators](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.114.236802)

- [UCSD QHE Lecture note](https://courses.physics.ucsd.edu/2019/Spring/physics230/LECTURES/QHE.pdf)