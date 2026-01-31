---
title: "Mean Field Approximation and Variational Method | Can Hartree, Fock, and BCS be Mixed 1:1:1?"
date: 2026-01-09T19:05:46+00:00
draft: false
math: true
tags: ["Condensed Matter", "Mean Field"]
categories: ["Physics Notes"]
---

This article aims to introduce the mean field approximation while elucidating its variational nature.

Hartree, Fock, and BCS—these individual mean field approximations appear to be mutually incompatible decoupling methods. However, by leveraging the variational nature of the mean field approximation, we discover that they can indeed be mixed 1:1:1.

<!--more-->

## Preface

The inspiration for this article primarily comes from discussions with classmate [@ykli](https://www.zhihu.com/people/li-yong-kang-9-34). I would like to express my special thanks to [@ykli](https://www.zhihu.com/people/li-yong-kang-9-34) for the significant assistance provided during the derivation process.

This question has also been raised on the Physics Stack Exchange website (referred to as "Multi-channel Mean Field Theory"). I have included the link here for reference:

https://physics.stackexchange.com/questions/742905/multi-channel-mean-field-theory

Additionally, Senior [@AlanNaHang](https://www.zhihu.com/people/deng-wwzz)'s answer regarding "Physics Circle Slang" (物理圈黑话) also gave me considerable inspiration. Interested readers can visit:

https://www.zhihu.com/question/410499049/answer/2442413803

## Introduction

For interacting systems, the complete Hamiltonian of the system is:

$$
\begin{aligned}
\hat{H} = \hat{H}_0 + \hat{V}_{int}
\end{aligned}
$$

Here, $\hat{H}_0 \sim \sum c^\dagger c$ represents the quadratic part of the fermion creation and annihilation operators, which is relatively easy to treat as independent free particles.

On the other hand, $\hat{V}_{int} \sim \sum c^\dagger c^\dagger c c$ represents the interaction part.

Due to the existence of interactions, it is difficult to determine the system's ground state wave function or equilibrium density matrix, making it challenging to calculate various information about the interacting system. Therefore, we often use various approximation methods to handle this.

The mean field approximation is one such method. We take a mean field approximation Hamiltonian that can be strictly solved:

$$
\begin{aligned}
\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}
\end{aligned}
$$

By making $\hat{V}_{mf}$ also quadratic, it becomes easier to solve strictly. We can then use the solution of this mean field approximation Hamiltonian to approximate various properties of the system.

## Mean Field Theory by Decoupling

However, approximations cannot be chosen blindly; they require certain techniques.

Quantum mechanics textbooks teach us that the mean field approximation involves ignoring the quantum fluctuation part of the operators, i.e., the Decoupling Method:

$$
\begin{aligned}
A^\dagger A & = [\langle A \rangle + (A - \langle A \rangle)]^\dagger [\langle A \rangle + (A - \langle A \rangle)] \\
& \equiv [\langle A \rangle + \delta A]^\dagger [\langle A \rangle + \delta A]  \\
& = \underbrace{\langle A^\dagger \rangle \langle A \rangle}_{\mathcal{O}(\delta A^0)} + \underbrace{\langle A^\dagger \rangle \delta A +  \delta A^\dagger \langle A \rangle}_{\mathcal{O}(\delta A^1)} + \underbrace{\delta A^\dagger \delta A}_{\mathcal{O}(\delta A^2)} \\
& = \underbrace{\langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle}_{\text{mean field}\ =\ \mathcal{O}(\delta A^0) + \mathcal{O}(\delta A^1)} \\
& + \underbrace{(A - \langle A \rangle)^\dagger (A - \langle A \rangle)}_{\text{quantum fluctuation}\ =\ \mathcal{O}(\delta A^2)} \\
& \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

The mean field part retains the zero-order and first-order parts of the operator fluctuation $\delta A$, while the quantum fluctuation includes the second-order part of the operator fluctuation $\delta A$.

Thus, it is not difficult to understand that when quantum fluctuations are not large, the mean field approximation is relatively accurate.

For the two-body interaction $\hat{V}_{int}$:

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

We have three methods to decompose it into the form of (a sum of) $\hat{A}^\dagger\hat{A}$:

+ Density Channel (Hartree): $\hat{A}_{i}^{H} = c_i^\dagger c_i$
+ Exchange Channel (Fock): $\hat{A}_{ij}^{F} = c_i^\dagger c_j$
+ Cooper Channel (BCS): $\hat{A}_{ij}^{BCS} = c_i c_j$

Taking the Density Channel as an example, the decoupling process for the Hartree mean field is:

$$
\begin{aligned}
    & \hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i \\
    & = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_i c_j^\dagger c_j \ +\underbrace{\ const}_{\text{ignore it}} \\
    & = \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{i}^{H}}^\dagger \hat{A}_{j}^{H} \\
    & = \frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{i}^{H}}^\dagger\rangle + \delta {\hat{A}_{i}^{H}}^\dagger \right) \left(\langle {\hat{A}_{j}^{H}}\rangle + \delta {\hat{A}_{j}^{H}} \right) \\
    & \approx -\frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{i}^{H}}^\dagger\rangle  {\hat{A}_{j}^{H}} +  {\hat{A}_{i}^{H}}^\dagger \langle {\hat{A}_{j}^{H}}\rangle - \langle {\hat{A}_{i}^{H}}^\dagger\rangle \langle {\hat{A}_{j}^{H}}\rangle \right) \\
    & \equiv \hat{V}_{H}
\end{aligned}
$$

For Fock mean field Decoupling:

$$
\begin{aligned}
    & \hat{V}_{int} = - \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{F} }^\dagger \hat{A}_{ij}^{F} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx -\frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{F}}^\dagger\rangle  \hat{A}_{ij}^{F} +  {\hat{A}_{ij}^{F}}^\dagger \langle \hat{A}_{ij}^{F}\rangle - \langle {\hat{A}_{ij}^{F}}^\dagger\rangle \langle {\hat{A}_{ij}^{F}}\rangle \right)\\
    & \equiv \hat{V}_{F}
\end{aligned}
$$

For BCS mean field Decoupling:

$$
\begin{aligned}
    & \hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{BCS} }^\dagger \hat{A}_{ij}^{BCS} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx \frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle  \hat{A}_{ij}^{BCS} +  {\hat{A}_{ij}^{BCS}}^\dagger \langle \hat{A}_{ij}^{BCS}\rangle - \langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle \langle {\hat{A}_{ij}^{BCS}}\rangle \right)\\
    & \equiv \hat{V}_{BCS}
\end{aligned}
$$

## Problem of Decoupling

However, it seems we can only make one type of approximation for the two-body interaction: either Hartree, or Fock, or BCS.

But in fact, the "Hartree-Fock mean field approximation" we often hear about seems to use two approximations.

$$
\begin{aligned}
\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

Does doing this cause a problem of double counting?

Or should we split $\hat{V}_{int}$ into $\frac{\hat{V}_{int}}{2}$ and $\frac{\hat{V}_{int}}{2}$ for use?

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{2} + \frac{\hat{V}_{int}}{2} \approx \frac{\hat{V}_{H}}{2} + \frac{\hat{V}_{F}}{2}
\end{aligned}
$$

Or split it into $\frac{\hat{V}_{int}}{3}$ and $\frac{2\hat{V}_{int}}{3}$?

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{3} + \frac{2\hat{V}_{int}}{3} \approx \frac{\hat{V}_{H}}{3} + \frac{2\hat{V}_{F}}{3}
\end{aligned}
$$

Since there is a "Hartree-Fock mean field approximation," why not have a "Hartree-Fock-BCS mean field approximation"? How are the aforementioned double counting problem and the so-called splitting problem resolved?

In fact, $\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}$ is the correct approach. However, if we understand the Hartree-Fock mean field approximation using the Decoupling Method, it always gives a feeling of double counting:

$$
\begin{aligned}
\hat{V}_{int} + \hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

This is caused by the imprecise formulation of Decoupling. Next, we will explain that the mean field approximation, as a non-perturbative method, is essentially a variational method of "guess the solution, then optimize."

Afterward, we will start from the variational method to prove that choosing different decoupling methods (Hartree, Fock, BCS) actually does not affect each other; it merely adds new independent parameters to the guessed solution and does not cause the so-called double counting problem.

## Variational Method for Finite Temperature

We are already familiar with the variational method at zero temperature.

For zero-temperature systems, we commonly use the variational method to "guess" the ground state wave function $|\Psi(\lambda)\rangle$ of the Hamiltonian, where $\lambda$ is a parameter adjusting the "guessed ground state wave function." By adjusting the parameter and observing the ground state energy functional:

$$
\begin{aligned}
E[\Psi(\lambda)] = \frac{\langle \Psi(\lambda) | \hat{H} | \Psi(\lambda) \rangle}{\langle \Psi(\lambda) | \Psi(\lambda) \rangle}
\end{aligned}
$$

Making it minimal allows us to say that $|\Psi(\lambda)\rangle$ is very close to the ground state wave function. We then use this guessed solution to calculate various properties of the system's ground state (zero temperature).

Similarly, the variational principle can be applied to finite temperature systems, simply by changing "guessed ground state wave function" to "guessed equilibrium density matrix."

Here we perform the derivation using the canonical ensemble, and for convenience, we set the unit system $k_B = 1$.

For finite temperature, the equilibrium density matrix is:

$$
\begin{aligned}
\hat{\rho}_{eq} = \frac{e^{-\beta \hat{H}}}{\operatorname{Tr} (e^{-\beta \hat{H}})}
\end{aligned}
$$

The "guessed equilibrium density matrix" must have a specific form. We assume the system's density matrix is the equilibrium density matrix of some auxiliary Hamiltonian $\hat{H}_{mf}(\lambda)$:

$$
\begin{aligned}
\hat{\rho}_{mf}(\lambda) \equiv \hat{\rho}_{eq} [\hat{H}_{mf}(\lambda)] \equiv \frac{e^{-\beta \hat{H}_{mf}(\lambda)}}{\operatorname{Tr} (e^{-\beta \hat{H}_{mf}(\lambda)})}
\end{aligned}
$$

where $\lambda$ is the parameter adjusting the Hamiltonian $\hat{H}_0$ (and thus adjusting the "guessed equilibrium density matrix"), such as mean field strength, order parameter, etc.

Here we use the "mf" subscript to imply that the mean field approximation involves taking the "auxiliary Hamiltonian" providing the "guessed equilibrium density function" as the "mean field approximation Hamiltonian." However, for the general variational method, the "auxiliary Hamiltonian" can take any form, and even the density matrix can be chosen arbitrarily; it does not necessarily have to be the equilibrium density matrix of some Hamiltonian.

At this point, the variational extremum condition also generalizes from "minimizing the energy functional" to "minimizing the free energy functional."

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda)] & = \langle \hat{H} \rangle_{\rho_{mf}(\lambda)} - TS \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{H}) + T \operatorname{Tr} (\hat{\rho}_{mf}(\lambda) \ln \hat{\rho}_{mf}(\lambda) )
\end{aligned}
$$

Note that $\hat{H}$ here is the complete Hamiltonian of the system, not our guessed Hamiltonian $\hat{H}_{mf}(\lambda)$.

In fact, in the mean field approximation, we use the equilibrium density matrix corresponding to the Hamiltonian after mean field approximation as the "guessed equilibrium density matrix." For this, we need to verify that directly taking the mean field approximation and ignoring quantum fluctuations coincides with the variational extremum condition of the free energy functional. This proves that the mean field approximation is indeed a variational method.

In the mean field approximation, we replace the interaction part in the complete Hamiltonian $\hat{H} = \hat{H}_0 + \hat{V}_{int}$ with a quadratic operator containing parameters, i.e.,

$$
\begin{aligned}
\hat{H}_{mf}(\lambda) = \hat{H}_0 + \hat{V}_{mf}(\lambda)
\end{aligned}
$$

Replacing the quartic interaction operator with a quadratic mean field operator will break some symmetries of the Hamiltonian, which is ultimately reflected in the symmetry breaking of the guessed wave function or guessed density operator.

This is the case in the mean field: choosing different channels represents choosing to break different symmetries. For example, BCS theory chooses to break charge conservation (U(1) symmetry).

$$
\begin{aligned}
\hat{V}_{mf}(\lambda) \sim \sum \lambda c^\dagger c^\dagger + h.c.
\end{aligned}
$$

In fact, in the BCS superconducting phase transition, Spontaneous Symmetry Breaking indeed occurs, making the strict ground state wave function or strict equilibrium density operator have less symmetry compared to the complete Hamiltonian $\hat{H} = \hat{H}_0 + \hat{V}_{int}$.

This indicates that although the mean field approximation is an approximation method, it indeed captures some essence of the phase transition process. Therefore, when quantum fluctuations are not large (far from the quantum critical point), we often use the mean field approximation to make some approximate predictions about quantum systems.

## Variational Method

Let us denote:

$$
\begin{aligned}
\hat{V}_{mf}(\lambda) = \lambda \hat{X}
\end{aligned}
$$

$$
\begin{aligned}
F_{mf} & = \langle \hat{H}_{mf} \rangle_{\rho_{mf}(\lambda)} - T S_{mf}\\ 
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{H}_{mf}) + T \operatorname{Tr} (\hat{\rho}_{mf}(\lambda) \ln \hat{\rho}_{mf}(\lambda) )
\end{aligned}
$$

It is important to note that $F[\hat{\rho}(\lambda) ] \neq F_{mf}$. The difference between the two is:

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda) ] - F_{mf} = \langle \hat{V}_{int} - \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

It is easy to have a misunderstanding: for $F_{mf}$, the equilibrium density matrix of $\hat{H}_{mf}$ itself is the density matrix that minimizes it, so

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} = 0
\end{aligned}
$$

But this is only true when the parameter $\lambda$ is fixed, i.e., when the fixed Hamiltonian $\hat{H}$ is unchanged, satisfying the extremum condition of $F_{mf}$. $\frac{\partial F_{mf}}{\partial \lambda}$ still needs to be strictly calculated:

First, since $F_{mf}$ is the equilibrium free energy of $\hat{H}_{mf}$, we can conveniently obtain:

$$
\begin{aligned}
F_{mf}(\lambda) = - T \ln \mathcal{Z}_{mf}(\lambda)
\end{aligned}
$$

$$
\begin{aligned}
\mathcal{Z}_{mf}(\lambda) = \operatorname{Tr} ( e^{-\beta \hat{H}_{mf}(\lambda)} ) = \operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )
\end{aligned}
$$

Thus,

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} & = -T \frac{1}{\mathcal{Z}_{mf}}\frac{\partial \mathcal{Z}_{mf}}{\partial \lambda} \\
& = - T \frac{\operatorname{Tr} ( -\beta \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \frac{\operatorname{Tr} (  \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{X} ) \\
& =  \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

That is, the expectation value of the order parameter in the mean field interaction $\hat{V}_{mf}$ part. Generally speaking, the order parameter calculated by the mean field approximation is non-zero, indicating that the system (at least under the mean field approximation) has a specific order.

Using the conclusion above, in order for the free energy functional $F[\hat{\rho}(\lambda) ]$ to reach an extremum, we now only need to set:

$$
\begin{aligned}
& \frac{\partial}{\partial \lambda} (F[\hat{\rho}(\lambda) ] - F_{mf}) \\
& = \frac{\partial}{\partial \lambda} \langle \hat{V}_{int}  \rangle_{\rho_{mf}(\lambda)} - \frac{\partial}{\partial \lambda} \langle \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)} \\
& = -\frac{\partial}{\partial \lambda} F_{mf} = - \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

Using the form $\hat{V}_{mf} = \lambda \hat{X}$ again, we can simplify further.

Note that we must take the derivative with respect to $\lambda$ in both $\hat{V}_{mf} = \lambda \hat{X}$ and $\hat{\rho}_{mf}(\lambda)$:

$$
\begin{aligned}
& \frac{\partial}{\partial \lambda} \langle  \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)} \\
& = \frac{\partial}{\partial \lambda} \langle \lambda \hat{X} \rangle_{\rho_{mf}(\lambda)} \\
& = \frac{\partial}{\partial \lambda}  \operatorname{Tr} ( \lambda \hat{\rho}_{mf}(\lambda) \hat{X} ) \\
& =  \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{X} ) +  \operatorname{Tr} ( \lambda \frac{\partial}{\partial \lambda}\{\hat{\rho}_{mf}(\lambda)\} \hat{X} ) \\
& =  \langle  \hat{X} \rangle_{\rho_{mf}(\lambda)} + \lambda \frac{\partial}{\partial \lambda} \left\{ \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{X} ) \right\} \\
& =  \langle  \hat{X} \rangle_{\rho_{mf}(\lambda)} + \lambda \frac{\partial }{\partial \lambda}\langle  \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

Thus, the extremum condition for the free energy functional can be written as:

$$
\begin{aligned}
\frac{\partial}{\partial \lambda} F[\hat{\rho}(\lambda) ] = 0\  \Leftrightarrow \ 
\frac{\partial}{\partial \lambda} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\lambda)}  = \lambda \frac{\partial }{\partial \lambda}\langle  \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

We can also generalize this variation to the case of multiple parameters $\{\lambda_i\}$, providing higher variational degrees of freedom, thereby making the guessed solution closer to the real situation.

In summary, if we take the equilibrium density matrix $\rho_{mf}(\{\lambda_i\})$ corresponding to some (usually only containing quadratic terms) mean field Hamiltonian $\hat{H}_{mf}(\{\lambda_i\}) = \hat{H}_0 + \sum_i \lambda_i \hat{X}_i$ as the guessed solution to calculate the free energy functional variation, then the values of the parameters $\{\lambda_i\}$ that minimize the free energy functional (closest to the real equilibrium state) satisfy the following condition:

$$
\begin{aligned}
\frac{\partial}{\partial \lambda_i} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}  = \lambda_i \frac{\partial }{\partial \lambda_i}\langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

We can further use the chain rule to write the variational extremum condition as:

$$
\begin{aligned}
\lambda_i  = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}} 
\end{aligned}
$$

In this way, we can directly obtain the parameters corresponding to the variational extremum condition (physically representing the order parameters).

However, this equation is too formal. We can discover through the calculation of specific examples that this is the same thing as the mean field approximation.

For a general two-body interaction:

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

And the general mean field interaction is taken as quadratic, so that it can be strictly solved as mutually independent elementary excitations. Here we take the most general form:

$$
\begin{aligned}
\hat{V}_{mf} & = \underbrace{\sum_{i} \lambda_i^{H} c_i^\dagger c_i}_{\text{Hartree}} \\
& + \underbrace{\sum_{i\neq j} \lambda_{ij}^{F} c_i^\dagger c_j }_{\text{Fock}} \\
& + \underbrace{\sum_{i,j} (\lambda_{ij}^{BCS} c_i^\dagger c_j^\dagger  + \bar{\lambda}_{ij}^{BCS} c_j c_i )}_{\text{BCS}}
\end{aligned}
$$

Here, the first, second, and third lines correspond to the Hartree, Fock, and BCS mean field parts, respectively.

Here we did not directly use the so-called decoupling method mentioned earlier:

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

Instead, we took a Hamiltonian with completely undetermined coefficients. Afterwards, we can prove that when the variational extremum is reached, this Hamiltonian is the "mean field approximation Hamiltonian" obtained by the decoupling method.

At the same time, precisely because the coefficients are completely undetermined, we can arbitrarily add or remove terms in the first, second, and third lines, because this is just adding or reducing variational parameters.

Next, we calculate $\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}$, which is the expectation value of the strict two-body interaction operator under the mean field corresponding equilibrium state.

We need to use Wick's theorem, because the mean field Hamiltonian is quadratic, so the Generating Functional is Gaussian. Therefore, the expectation value of equilibrium Fermi operators can be strictly decomposed into contractions of pairs of Fermi operators.

$$
\begin{aligned}
\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} & = \frac{1}{2} \sum_{ij}V_{ij} \langle c_i^\dagger c_j^\dagger c_j c_i \rangle_{\rho_{mf}(\{\lambda_i\})} \\
& = \frac{1}{2} \sum_{ij}V_{ij} (\langle c_i^\dagger  c_i \rangle \langle c_j^\dagger  c_j \rangle \\
& - \langle c_i^\dagger  c_j \rangle \langle c_j^\dagger  c_i \rangle + \langle c_i^\dagger  c_j^\dagger \rangle \langle c_j  c_i \rangle)
\end{aligned}
$$

Thus, using the variational extremum condition, we have:

$$
\begin{aligned}
    \lambda_i^H & = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  c_i^\dagger c_i \rangle_{\rho_{mf}(\{\lambda_i\})}} \\
    & = \frac{1}{2} \sum_j \left( V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} +  V_{ji} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} \right)\\
    & = \sum_{j} V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

Here we used $V_{ij} = V_{ji}$. Through observation, it is not difficult to find that this is the Hartree mean field approximation term obtained by "decoupling" earlier, differing by at most a constant.

Previously, we selected $\hat{A}_{i}^{H} = c_i^\dagger c_i$ and omitted the second-order term of its quantum fluctuation; here, we purely used the variational extremum condition to determine the guessed Hamiltonian parameter that minimizes the free energy functional.

Similarly, for other undetermined parameters corresponding to Fock and BCS mean field approximations, we have:

$$
\begin{aligned}
\lambda_{ij}^{F} & = - \frac{1}{2} ( V_{ij} \langle  c_j^\dagger c_i \rangle_{\rho_{mf}(\{\lambda_i\})} + V_{ji} \langle  c_i^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} )\\
& =  - V_{ij} \langle  c_j^\dagger c_i \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

$$
\begin{aligned}
\lambda_{ij}^{BCS} & = \frac{1}{2}  V_{ij} \langle  c_j c_i \rangle_{\rho_{mf}(\{\lambda_i\})} \\
\bar{\lambda}_{ij}^{BCS}& =  \frac{1}{2} V_{ji} \langle  c_i^\dagger c_j^\dagger \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

Substituting them into $\hat{V}_{mf}(\{\lambda_i\})$, it is not difficult to discover that they also correspond to Fock and BCS mean field approximations, respectively.

But from the perspective of the variational method, these undetermined coefficients and terms of the guessed Hamiltonian are independent and do not affect each other. Adding or subtracting terms to the guessed Hamiltonian merely changes the form of the guessed solution, increasing or decreasing the variational parameters. Therefore, Hartree, Fock, and BCS mean field approximations can indeed be mixed 1:1:1, or mixed in pairs, all satisfying the variational extremum condition for the given parameters.

However, in specific problems, we care about specific order parameters, so we minimize the variational parameters (using only BCS or Hartree-Fock) to obtain the most concise and effective conclusions possible.

## Summary

In summary, we have proven through the strict derivation of the variational method that Hartree, Fock, and BCS mean field theories can indeed be mixed 1:1:1.

First, we utilized the decoupling method frequently appearing in quantum mechanics textbooks, obtaining the mean field Hamiltonian under a certain mean field approximation by "brute force" omitting the second-order fluctuation terms of the operators.

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

However, this decoupling method can easily create the illusion of double counting when using two or more mean field approximations.

Afterwards, we re-described the variational nature of the mean field approximation using the language of the variational method, considering that the equilibrium state of the system $\hat{H} = \hat{H}_0 + \hat{V}_{int}$ is very close to the equilibrium state of a certain mean field Hamiltonian $\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i\})$ (guessed Hamiltonian, containing various undetermined coefficients $\{\lambda_i\}$).

Selecting the undetermined coefficients $\{\lambda_i^{mf}\}$ that minimize the system's free energy variation, and thus using the mean field Hamiltonian $\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i^{mf}\})$ under this coefficient selection to approximate the original (interacting) system Hamiltonian $\hat{H} = \hat{H}_0 + \hat{V}_{int}$ is the mean field approximation.

Through the variational method and Wick's theorem, we proved that the optimal undetermined coefficients $\{\lambda_i^{mf}\}$ coincide exactly with the results of selecting first-order fluctuation terms in the decoupling method, meaning the optimal undetermined coefficients $\{\lambda_i^{mf}\}$ are the system's mean field (order parameters).

Returning to the original question "Can Hartree, Fock, and BCS mean field theories be mixed 1:1:1?", when using the variational method, there is no stipulation on the number of undetermined coefficients, or rather, the variational extremum conditions for each undetermined coefficient are mutually independent.

Therefore, the Density, Exchange, and Cooper Channels corresponding to Hartree, Fock, and BCS mean field theories in the decoupling method are in fact independent and do not double count. Thus, we have proven:

**Hartree, Fock, and BCS mean field theories can indeed be mixed 1:1:1.**

## Reference

- [1] Bruus, H., & Flensberg, K. (2004). Many-body quantum theory in condensed matter physics: an introduction. Oxford university press.
- [2] Coleman, P. (2015). Introduction to many-body physics. Cambridge University Press.
- [3] Altland, A., & Simons, B. D. (2010). Condensed matter field theory. Cambridge university press.
