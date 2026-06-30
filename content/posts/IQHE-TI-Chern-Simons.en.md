---
title: "😮QHE(4)｜From Quantum Hall to Topological Insulator to Chern-Simons Theory and Topological Classification"
date: 2022-06-10T10:00:00+08:00
draft: false
math: true
tags: ["IQHE", "Topological Insulator", "Chern-Simons", "Berry Phase", "Condensed Matter"]
categories: ["Physics Notes"]
---

It has been a year since I first encountered topology in condensed matter theory. I have read quite a bit of literature here and there, and I would like to organize my thoughts below, hoping to clarify some of the main threads in the learning process for readers who may be entering this field in the future.

The integer quantum Hall effect opened up a new frontier for condensed matter physics. However, this is only the tip of the iceberg when it comes to topology in condensed matter. As we will see, IQHE is in fact a topological effect of a system that is **two-dimensional, gapped, non-interacting, fermionic, without time-reversal symmetry (TRS), without particle-hole symmetry (PHS, or charge conjugate symmetry), and without chiral symmetry**.

<!--more-->

In fact, by varying the attributes above — [dimension], [gapped or gapless], [interacting or non-interacting], [fermionic/bosonic], [time-reversal symmetry], [particle-hole symmetry], [chiral symmetry] — we can obtain an extremely rich variety of topological effects, such that the topological classification of some systems remains a hot topic at the research frontier.

When first learning, one often becomes curious about the various combinations of quantum Hall effects — for instance, the (integer) quantum Hall effect, quantum spin Hall effect, quantum anomalous Hall effect, etc. But in truth, classification based on the aforementioned attributes like dimension and symmetry is far more general.

As Prof. Zhaihui once said in class: "Don't learn physics as just terminology; pay more attention to the physics behind these terms."

## Reference

Let me first list the references I consulted. I have categorized them roughly by difficulty according to my own limited understanding, hoping this will be helpful for readers looking for reference materials.

Overall, I believe this part of the study requires a gradual, step-by-step approach, and it's a good idea to vary reading materials to avoid getting tired of any single source.

There are also many excellent notes and reviews provided by masters on Zhihu. Let me list some articles that I personally found friendly and inspiring within the scope of my limited search ability.

@Boltzlinn's paper guide:

https://zhuanlan.zhihu.com/p/61559924

@Lagrange's article:

https://zhuanlan.zhihu.com/p/77270930

First, I highly recommend Prof. SC Zhang's talk on Topological Insulators at SITP. There are subtitles on Bilibili, and the complete version is also available on the SITP official YouTube channel. Prof. SC Zhang explained the physics and application prospects of topological insulators in accessible language to scholars from various backgrounds, which should be very inspiring for newcomers to this field.

https://www.bilibili.com/video/BV1t7411W7Eq?spm_id_from=333.337.search-card.all.click&vd_source=ba9ae3c860748ec9008f01f641bd9bf8

https://www.youtube.com/watch?v=dCQ7CAQ4Npc

https://www.youtube.com/watch?v=sbJSAOngiGI&t=691s

Next, I recommend the review by Hasan & Kane on topological insulators and topological superconductors. It doesn't contain many formulas but lists plenty of theoretical and experimental results. It is suitable for readers who have studied band theory and want to further spark their interest in this field, experiencing the charm of topological band theory. However, I wouldn't suggest obsessing over every detail; reading through it once or twice to grasp the main ideas is enough. You can come back to reinforce your understanding after learning more — it will be even more rewarding.

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.82.3045

@Lord Hart's column has a translation of the Hasan & Kane review on topological insulators and topological superconductors. Feel free to check it out.

https://www.zhihu.com/column/condensematterphysics

After that, my suggestion is to do more quantitative calculations and formula derivations. Starting from the QHE, I first recommend Chapters 1 and 2 of David Tong's QHE lecture notes. Understanding the Berry Phase as an important tool and the Berry Curvature and Chern Number terms in the Hall Conductance expression derived from linear response theory should suffice.

http://www.damtp.cam.ac.uk/user/tong/qhe.html

For a more rigorous analysis of the theoretically existing topological effects in the QHE and various derivations, please refer to the note I wrote in the previous chapter.

https://zhuanlan.zhihu.com/p/486890623

Additionally, here is a useful website for beginners in topological insulators. The content there is also very beginner-friendly.

https://topocondmat.org/index.html

The content that follows is roughly what I want to summarize in the next few chapters of notes — namely, a more systematic analysis of the topological classification of non-interacting, insulating (gapped) fermionic systems.

First, I believe one should systematically study topological band theory. For this, I primarily recommend two books, which also include analysis of the QHE. Readers who wish to pursue more systematic study can start with these books:

+ One is 'Topological Insulators and Superconductors' by Bernevig & Taylor Hughes. The characteristic of this book is its rigorous derivations. For example, Chapter 3 thoroughly analyzes the linear response theory of lattice fermion systems, derives the expression for the current operator, and uses the extremely brute-force magnetic BZ method to derive the quantum Hall effect. However, it may frighten beginners (me) and cause them (me) to gradually lose sight of the original physical picture amidst the frenzied formula derivations, eventually becoming emo (me). So I suggest readers skim through the first few chapters and the later chapters on 4D Topological Insulators, and then use it as supplementary material for the topological field theory papers by XL Qi, Taylor Hughes, and SC Zhang — it will be very helpful.
+ Another is "Topological Insulators: Dirac Equation in Condensed Matters" by Prof. ShunQing Shen. The novelty of this book lies in its opening analysis of gap closing and reopening in band structures from the perspective of the Dirac Equation, and how this affects the topological properties of the system's band structure. It rigorously derives the edge states, $\mathbb{Z}_2$ index, and other conclusions that were treated more qualitatively in earlier reviews. This is very beneficial for further theoretical understanding of the topological properties of topological insulators.
+ Additionally, Chapter 7 of Prof. Zhaihui's 'Ultracold Atomic Physics' specifically introduces the topological band theory of simple two-band systems. Since the wavefunction of a two-band system can be described by a unit vector on the Bloch sphere, its topological nature is even more pronounced. It was in Prof. Zhai's class that I made a major breakthrough in understanding topological band theory.

Through the content above, readers will gain a more systematic understanding of topological band theory. At this point, they may become interested in the topological classification that is more or less mentioned in earlier reviews. Here we need to consider the role of symmetry and dimensionality in topological classification. I recommend the review by Ching-Kai Chiu, Jeffrey C.Y. Teo, Andreas P. Schnyder, and Shinsei Ryu.

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.88.035005

Qingrui Wang from Yau Mathematical Sciences Center offers an online course on topological order. Beginners can start with Lectures 5-7 on Fermionic SPT Phases.

https://qr-wang.github.io/teaching_2021_TQM.html

Going further, if readers have some background in quantum field theory or condensed matter field theory, they can also refer to the topological field theory papers by XL Qi, Taylor Hughes, and SC Zhang. These works introduce effective theories involving the Chern-Simons term, extending topological insulators to higher dimensions such as 4D. As mentioned earlier, Bernevig & Taylor Hughes' 'Topological Insulators and Superconductors' can serve as supplementary material for these papers.

http://journals.aps.org/prb/abstract/10.1103/PhysRevB.78.195424

I won't go into too much detail on topology and field theory here. As long as you have some foundation in homotopy theory and path integrals, you'll be fine. Let me briefly list some field theory recommendations:
+ QFT: Peskin, Weinberg, Schwartz, Coleman, A Zee, David Tong (Lec. Note)
+ CMPFT: Roger Melko (Online Course), Altland, Fradkin, Xiaogang Wen, Nagaosa: QFT in CMP, QFT in Strongly Correlated Electronic System

## From IQHE to Chern Insulator: Time-Reversal Breaking

Everything is gradual. Historically, when the IQHE was first discovered, enormous magnetic fields were needed to reduce the number of Landau levels below the Fermi energy to just a few. Later, in the search for IQHE without strong magnetic fields, Haldane proposed adding a periodic magnetic field to a honeycomb lattice, breaking TRS while keeping the net magnetic field zero. This yielded the IQHE without an external field, also known as the Chern Insulator. Like the IQHE with an external magnetic field, the Chern Insulator is a topological effect of a **two-dimensional, gapped, non-interacting, fermionic system with broken time-reversal symmetry (TRS), no particle-hole symmetry (PHS, or charge conjugate symmetry), and no chiral symmetry**. The role of the magnetic field is absorbed into the condition of "Time-Reversal Breaking."

In the analysis of the Chern Insulator, since there is no external magnetic field, we don't need to use the previously mentioned magnetic BZ method to calculate the Hall response. Instead, we integrate over the system's BZ and the Berry Curvature of all filled bands. Because TRS is broken, we can obtain a non-zero TKNN invariant (Chern number) without applying a magnetic field, under appropriate hopping and chemical potential conditions.

The Hall effect can be calculated using various perturbative methods. The previous section discussed this in detail, so I won't repeat it here. In general, all proof methods involve calculating the linear response of the system under some form of perturbation theory, so they can be unified under the most general Linear Response Theory, with the final Hall Conductance computed via the Kubo Formula.

On the other hand, the Berry Connection $\mathcal{A}$ and Berry Curvature $\mathcal{B}$ are (Abelian) gauge fields defined on the BZ. (The mention of "Abelian" hints at the more general Non-Abelian gauge fields that lead to things like 4D topological insulators later.) Their quantization on the BZ ($\mathbf{T}^2$) is almost entirely a topological effect. While marveling at the consistency between the Hall Conductance expression and the Chern number formula, we can think in reverse: using the topological properties of gauge fields in different dimensions (Chern-Simons Theory), we can search for physical effects corresponding to these known topological properties. Following this line of thought, theorists have successfully predicted physical effects such as 4D TI, 3D Half-IQHE, and the 3D magnetoelectric effect.

## From 2D TRB to 1D PHS: Topology in Different Dimensions

Following the Chern Insulator, theorists anticipated even richer topological effects. In this subsection, I attempt to start from the Chern Insulator and consider the topological effects of the Chern number in 1D systems.

In the Laughlin Argument from the previous chapter, we saw that by threading magnetic flux through a cylinder, we can replace $k_y$ in one dimension with the canonical momentum $k_y+A_y$, and then slowly tune this canonical momentum, causing the system's spectrum to change periodically. In this case, $k_y$ effectively becomes a parameter, and the system becomes a one-dimensional system in the x-direction associated with this parameter. This is the basis of Dimensional Reduction.

$$ H=\sum_{k_{y}} H_{1 \mathrm{D}}\left(k_{y}+A_{y}\right) $$

Adding magnetic flux introduces a vector potential, which preserves spatial translational symmetry.

$$ A_y = -E_y t \quad A_x = 0$$

Now consider what happens after dimensionality reduction of the 2D TRB Chern Insulator — the correspondence between the Chern number and the physical effects of the 1D system. The physical effect here is $\mathbb{Z}_2$ Quantized Charge Polarization.

The 2D Hall effect gives the Hall current:

$$ j_x = \sigma_H E_y $$

From charge conservation:

$$ \partial_t \rho + \nabla \cdot j = 0 $$

Gauss's law:

$$ \nabla \cdot D = \nabla \cdot (P + \epsilon_0 E) = \rho$$

Thus, up to a divergence term, we have:

$$ j = \partial_t P $$

$$ \Delta P = \int_0^T dt \ j $$

On the other hand, the current in the tight-binding model is the sum of currents from the 1D model parameterized by the canonical momentum $k_y + A_y$:

$$ J_{x}=\sum_{k_{y}} J_{x}\left(k_{y}\right) $$

After $\Delta t=2 \pi / L_{y} E_{y}$, the pumped charge is:

$$ \Delta Q=\int_{0}^{\Delta t} d t \sum_{k_{y}} J_{x}\left(k_{y}\right) \equiv \sum_{k_{y}} \left. \Delta P_{x}\left(k_{y}\right)\right|_{0} ^{\Delta t}$$

After $\Delta t$, the spectrum has gone through exactly one period, and the occupation numbers of the filled states change adiabatically, with $k_y \rightarrow k_y - 2\pi/L_y$:

$$ \Delta P_{x}\left(k_{y}\right)=P_{x}\left(k_{y}-2 \pi / L_{y}\right)-P_{x}\left(k_{y}\right) $$

In the thermodynamic limit:

$$ \Delta Q=-\oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}}  \quad J_{x}\left(k_{y}\right)=d P_{x}\left(k_{y}\right) / d t $$

Combining with the quantum Hall effect:

$$ \Delta Q=\sigma_{H} \Delta t E_{y} L_{y}=2 \pi \sigma_{H} $$

We find that the quantization of the 2D Chern number corresponds to a sum rule for a 1D charge pump system. That is, the 1D system $H_{1 \mathrm{D}}\left(k_{y}\right)$ described by $k_y$ satisfies:

$$ \Delta P = \oint_{0}^{2 \pi} d k_{y} \frac{\partial P_{x}\left(k_{y}\right)}{\partial k_{y}} = - 2\pi \sigma_{H} = -C_1$$

This shows that if we replace one $k$ of the 2D Bloch Hamiltonian with a time-evolving adiabatic parameter, the change in the system's Polarization after one period is given by the Chern number — it is quantized.

But this is almost just reinterpreting the integration over one dimension of k in the BZ as a change in t in the Chern number expression. Seen this way, the result is quite obvious, and it corresponds to contributions from all parameter intervals spaced by $2\pi/L_y$ in the 2D system. It merely gives a sum rule for the Polarization of a 1D system described with $k_y$ as the parameter.

Polarization can also be defined by the following expression:

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

where we have used the definition of the Wannier Function:

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

It can be seen here that Polarization can be defined by the gauge field known as the Berry Connection. However, due to the topological effects of the gauge field on the BZ, $P$ can change by integer multiples under a Gauge Transformation. That is, the path integral $\oint dk \cdot A(k)$ can change by integer multiples of $2\pi$ under a gauge change.

Going further, we replace $k_y+A_y$ with $\theta$, and then Polarization can be written as:

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

The original 2D Bloch Hamiltonian can now be viewed as a 1D Bloch Hamiltonian with $\theta$ as a parameter. Now let us introduce symmetry and examine this "semi-finished" 1D topological effect — the sum rule:

$$ -\oint_{0}^{2 \pi} d \theta \frac{\partial P_{x}\left(\theta\right)}{\partial \theta} = C_1 $$

$$ P(\theta)=\oint d k_{x} a_{x} / 2 \pi $$

Or written in the following form:

$$ G(\theta) =-\oint \frac{d k_{x}}{2 \pi} f_{x \theta}\left(k_{x}, \theta\right) =\oint \frac{d k_{x}}{2 \pi}\left(\frac{\partial a_{x}}{\partial \theta}-\frac{\partial a_{\theta}}{\partial k_{x}}\right)
$$
$$
\int G(\theta) d \theta=C_{1} \in \mathbb{Z}
$$

Can this further help us classify 1D systems topologically? Here $a$ is the Berry Connection, and $f$ is the Berry Curvature.

+ Introducing symmetry

We hope to obtain a new topological classification — that is, we want the value of $P$ to be quantized. To achieve this, we must introduce symmetry into the one-dimensional system. The symmetry introduced here is Particle-Hole Symmetry, or Charge Conjugate Symmetry:

$$ H=\sum_{k} c_{k}^{\dagger} h(k) c_{k}=\sum_{k} c_{-k} C^{\dagger} h(k) C c_{-k}^{\dagger} $$

$$ \Rightarrow C^{\dagger} h(-k) C=-h^{T}(k) $$

Consider two 1D Bloch Hamiltonians:

$$ h(k, 0)=h_{1}(k), h(k, \pi)=h_{2}(k) $$

And require that the original 2D Bloch Hamiltonian also satisfies PHS:

$$ h(k, \theta)=-\left(C^{-1} h(-k, 2 \pi-\theta) C\right)^{T} $$

We can define the Chern number using the 2D Bloch Hamiltonian:

$$ C[h(k, \theta)]=\oint d \theta \frac{\partial P(\theta)}{\partial \theta} $$

Here, the Polarization of the 1D system can also be defined by:

$$ P = -e \sum_{n} \langle n,R=0| \hat{r} | n,R=0\rangle $$

$$= \frac{-e}{2\pi} \oint dk \cdot \langle u_{n,k} | i \nabla_k | u_{n,k} \rangle  = \frac{-e}{2\pi} \oint dk \cdot A(k) $$

where we have used the definition of the Wannier Function, i.e., the wavefunction in real space:

$$ | R, n \rangle = \frac{1}{(2\pi)^d} \int d k e^{-i k \cdot (R-r)} | u_{n,k} \rangle $$

It can be seen here that Polarization can be defined by the gauge field known as the Berry Connection. However, due to the topological effects of the gauge field on the BZ, $P$ can change by integer multiples under a Gauge Transformation. That is, the path integral $\oint dk \cdot A(k)$ can change by integer multiples of $2\pi$ under a gauge change.

Rewrite the above definition of Polarization in natural units:

$$ P(\theta)=\oint \frac{d k}{2 \pi} \sum_{E_{\alpha}(k)<0}(-i)\left\langle k, \theta ; \alpha\left|\partial_{k}\right| k, \theta ; \alpha\right\rangle $$

Using PHS:

$$ h(-k, 2 \pi-\theta) C|k, \theta ; \alpha\rangle^{*}=-E_{\alpha}(k) C|k, \theta ; \alpha\rangle^{*} $$

It can be shown [see Xiaoliang Qi's topological field theory paper; I will include the proof at the end of this note]:

$$ P(\theta)= -P(2 \pi-\theta) $$ 

Thus:

$$ \int_{0}^{\pi} d P(\theta)=\int_{\pi}^{2 \pi} d P(\theta) $$

Using this property of 1D PHS systems (note that PHS is crucial; otherwise, $P$ is an arbitrary value defined modulo 1, not quantized), we can further define the Relative Chern Number:

$$ N_{1}\left[h_{1}(k), h_{2}(k)\right]=(-1)^{C[h(k, \theta)]}$$

A model with a relative Chern number of 0 compared to a trivial 1D band is called a topologically trivial insulator, and one with a relative Chern number of 1 is called a topological insulator. This yields a $\mathbb{Z}_2$ topological classification. [Again, I have only stated the conclusion here; detailed derivations can be found in Xiaoliang Qi's topological field theory paper and, for reference convenience, I will also place them at the end of this note.]

## From Chern Insulator to Topological Insulator: Topology with Different Symmetries

Following the line of thought above, besides varying the dimension, we see that the Chern Insulator generalization shows that **symmetry** is intimately related to topological classification. We expect to find similar topological effects in systems with other symmetries (perhaps another type of quantum Hall effect). What we find in systems that are also 2D but possess TRS is the Topological Insulator. Since TI is sometimes used as a general term, we also call it the QSH Insulator, based on its corresponding physical effect — the quantum spin Hall effect.

In fact, the topological classification of 2D TRS systems is also obtained via dimensional reduction from a higher-dimensional parent system (4D $\rightarrow$ 3D $\rightarrow$ 2D) combined with the introduction of symmetry. However, this is too complicated for beginners. I personally suggest using the Polarization introduced in the previous section, along with the Pfaffian and $\mathbb{Z}_2$ index discussed below, to get a glimpse of the topological effects of 2D TI.

TRS requires that the Bloch Hamiltonian satisfy:

$$ \mathcal{T} h(\mathbf{k}) \mathcal{T}^{-1} = h(-\mathbf{k}) $$

Examining the bands of a system with TRS, when $\mathbf{k} = - \mathbf{k}\ mod \ \mathbf{\Gamma}_i$, where $\mathbf{\Gamma}_i$ are reciprocal lattice vectors, degeneracy occurs. That is, $|n,\mathbf{k}\rangle$ and $\mathcal{T}|n,\mathbf{k}\rangle$ both have energy $E_n(\mathbf{k})$ and are orthogonal. This also requires that for spin-1/2 systems, $\mathcal{T}^2 = -1$. This is the famous Kramers Degeneracy.

At the same time, for a generic $|n,\mathbf{k}\rangle$, its time-reversed partner $\mathcal{T}|n,\mathbf{k}\rangle$ corresponds to the same energy at $-\mathbf{k}$, so the bands exhibit mirror symmetry about the $k=0$ point.

Thus every two bands will overlap in a figure-eight ($\infty$) pattern. Due to this symmetry, when we attempt to directly apply the formula for the Chern number, we find that the Berry Curvature integrates to zero for each pair of bands in a TRS system.

We can divide these bands with Kramers Degeneracy into two categories, understanding the (2n-1)-th and 2n-th bands as corresponding to spin-up and spin-down bands, which we call the $n-I,II$ bands.

First consider a 1D system. We can compute the Polarization of the $I,II$ bands. Due to TRS, we cannot extract useful information from $P = P^I + P^{II}$. Instead, we consider the Time-Reversal Polarization:

$$ P_s = P^I - P^{II} $$

Following the derivation in Section 4.8 of Shunqing Shen's Topological Insulators, we can compute a $\mathbb{Z}_2$ number using the Pfaffian and Determinant of $w_{m n}(k)=\left\langle u_{m}(-k)|\Theta| u_{n}(k)\right\rangle$ at the TRIM (Time-Reversal Invariant Momentum) points.

When generalizing to 2D and 3D, we treat 2D as a continuous transformation of a 1D system in the x-direction. By examining the change in the $\mathbb{Z}_2$ number of the 1D system at $k_y=0$ and $k_y=\pi$, we can define a new $\mathbb{Z}_2$ number. The same approach can be used to define the $\mathbb{Z}_2$ number for 3D systems.

+ Computing the Pfaffian requires us to define a continuous gauge for the Bloch wavefunction on the BZ, which is very complicated. If the system has Inversion Symmetry (IS), we can use the Parity of the wavefunction at TRIM points to give a simple definition of the $\mathbb{Z}_2$ number. This is discussed in detail in Chapter 12 of Bernevig's Topological Insulators book.
+ It is worth noting that the simplest non-trivial QSH requires two Haldane Models, one for spin-up and one for spin-down, and the bands of different spins (the $I,II$ bands here) correspond to different Spin Chern Numbers. The $\mathbb{Z}_2$ number is then the difference of the Spin Chern Numbers mod 2. This case requires spin conservation, a strong condition, but it is easy to understand. In contrast, our discussion of the $\mathbb{Z}_2$ number above only involves the increase in the number of bands due to the spin degree of freedom, without requiring that each band corresponds to a specific spin direction. Thus the definition of the $\mathbb{Z}_2$ number has universal significance.
+ In fact, Topological Insulators generally require the introduction of a Spin-Orbit Coupling term, which protects the system's TRS, provides a certain "magnetic field" effect for different spins, and may also break Spin Conservation.

## From Lattice Model to Continuum Model: Dirac Equation and Edge Mode

We find that topological phase transitions almost always involve gap closing and reopening, a process very similar to the mass change of a massive Dirac Fermion. We can use Dirac Fermions in different dimensions to describe the local features of the system's bands, thereby describing the system's topological phase transitions.

This is reasonable because the same topological phase does not care about the fine details of the bands. Only when singularities appear in the band structure do the topological properties undergo discontinuous changes, such as a jump in the topological invariant.

At the same time, we should note that Dirac Fermions can only describe local band features. At larger distances, the dispersion will diverge, which inevitably conflicts with the periodic boundary conditions of the BZ. This can also produce certain physical effects, such as the fact that a 3D TI cannot have just a single Dirac Cone.

Chapter 2 of Prof. ShunQing Shen's Topological Insulators book provides a very detailed exposition of this topic, and I strongly encourage readers to study it further. We will see that a non-trivial topological insulator with open boundaries has robust topological edge states whose dispersion is approximately linear. This can also be derived from the Dirac equation. Specifically, we replace $k_i$ on the open boundary side with $-i \partial_i$ and solve for the real-space wavefunction over long ranges, along with its corresponding energy (surface state dispersion). In general, higher-dimensional systems can only be solved perturbatively, but we can still see linear dispersion over short ranges. This indicates that the real-space wavefunction moves in one direction. Such analytical results are sufficient for understanding the existence and dispersion of edge states. Adding various perturbations will greatly distort the shape of the dispersion, but we can trust that without gap closing, the band topology remains unchanged, and the corresponding edge states remain robust. This is the essence of the important **Bulk-Edge Correspondence** in topological insulators.

Looking further at 2D Chern Insulators and Topological Insulators, we obtain Chiral and Helical edge states.

Here, Chiral means the direction of rotation is consistent, e.g., the edge state on the left has downward group velocity, and the edge state on the right has upward group velocity — this corresponds to the Chern Insulator/IQHE. Helical refers to the locking between the direction of rotation and the spin direction of the edge states, e.g., spin-up moves clockwise, spin-down moves counterclockwise — this corresponds to the Topological Insulator/QSHE.

## Transport Property: Landauer Formalism

Since Edge Modes are robust against perturbations such as impurities, they can be treated as one-dimensional channels without backscattering. Using the Landauer Formalism, we can analyze the physical response of 2-terminal, 4-terminal, and 6-terminal systems in actual measurements. This is necessary for analyzing how to experimentally detect these non-trivial topological edge states and for experimentally classifying materials topologically.

For details, see Section 6.3 of Prof. ShunQing Shen's Topological Insulators.

## From Tight-Binding Models to Effective Field Theory: Chern-Simons Term

Xiaogang Wen, at the very beginning of his many-body physics textbook, introduces the path integral formalism and emphasizes the importance of effective theory. I recommend that readers go and read Chapter 2 of Xiaogang Wen's Many-Body Physics.

The general idea of the path integral is to assign a "probability" $e^{S[\phi(t)]}$ to every path $\phi=\phi(t)$ in classical phase space (which could be the path of a particle or a field), where $S[\phi(t)]$ is the action corresponding to that path. Therefore, once we write down the Lagrangian of a classical system, we can use the path integral to obtain its quantum version.

Field theory has an extremely wide range of applications. We can include all the dynamical variables of all the system's degrees of freedom, write them into a large Lagrangian, quantize it using the path integral, and then compute various observables by coupling an external field $j(x)$ to the $\phi$ field and using functional derivatives, etc.

$$ \langle \phi(x) \rangle = \frac{1}{\mathcal{Z[j]}}\left. \frac{\delta \mathcal{Z}[j]}{\delta j(x)}  \right|_{j=0} $$

$$ \mathcal{Z}[j] \equiv \int \mathcal{D}\phi e^{S[\phi]+ \int d^d x \phi(x)j(x)} $$

But such a theory is a bit like a Theory of Everything. In reality, we only care about the measurable quantities and correlation functions associated with a subset of degrees of freedom. In that case, we can simply integrate out the degrees of freedom we don't care about first:

$$\int \mathcal{D}\phi ( \int \mathcal{D}\psi e^{S[\phi,\psi]} ) = \int \mathcal{D}\phi e^{S_{eff}[\phi]}$$

This does not affect the computation of expectation values, since the definition of $\mathcal{Z}$ is unchanged.

Now consider the physical meaning of doing this. It means that the contribution from integrating out the degrees of freedom we don't care about results in the system being entirely described by an effective action that contains only the $\phi$ fields we care about, along with the corresponding effective field theory.

This is extremely important. In condensed matter physics, we are often concerned with the low-energy excitations and responses of a system. Therefore, we can path-integrate out the high-energy parts to obtain the effective theory of the low-energy fields. This is also the essence of renormalization group theory: we continuously integrate out high-energy parts and observe how the parameters describing the system in $S_{eff}$ — such as mass and interaction strength — change as we vary the cutoff $\Lambda$. Since many parameters tend to zero as $\Lambda \rightarrow 0$, this indicates that these parameters essentially do not affect low-energy physical phenomena. In the end, we only need to study the very few parameters that do not tend to zero, and we can describe the low-energy theory of a complex many-body system that was originally described by a wide variety of parameters. This is the theoretical foundation for studying **universality** in many-body systems!

Think about why the continuous phase transition of water and the paramagnetic-ferromagnetic phase transition have essentially the same critical exponent $\beta$. Although the parameters describing their models are certainly vastly different, as we continuously integrate out the high-energy parts, only a very small number of important parameters remain. Consequently, the models describing their low-energy theories become strikingly similar. If only the quadratic and quartic terms of the field remain, then the Landau mean-field model will predict that all such low-energy models have the same critical exponent $\beta=1/2$. Here, the things we don't care about are the high-energy fields; we can also choose not to care about the fermionic fields corresponding to electrons, or the environmental phonon fields coupled to the system, etc. We simply integrate them out first in the path integral.

Having discussed the importance of effective theory, let us now examine the effective field theory of the IQHE.

How does the effective field theory of the IQHE arise? First, the Hamiltonian describing the system contains various fermionic creation and annihilation operators. Recall from quantum field theory or condensed matter field theory that path integral quantization involves replacing all $c^\dagger,c$ with Grassmann numbers $\bar{\psi},\psi$ and then performing the path integral. Considering that there are external electromagnetic fields in the system, we do a Peierls Substitution to introduce the gauge field into the Hamiltonian.

According to effective theory, we path-integrate over the degrees of freedom of the fermionic field, absorbing the parts related to $A$ into an effective action $S_{eff}$. This gives us the effective theory of the gauge field $A$ in the topological insulator system:

$$
\begin{aligned}
e^{i S_{\text {eff}}[A]} &=\int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H [A] \right]} \\
&= \int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H_0[c,c^\dagger] \right] + \int d^d x \ j\cdot A} \\
&=\operatorname{Det}\left[\left(i \partial_{t}-A_{0 m}\right) \delta_{m n}^{\alpha \beta}-h_{m n}^{\alpha \beta} e^{i A_{m n}}\right]
\end{aligned}
$$

$$
\begin{aligned}
H[A]=& \sum_{m, n}\left(c_{m \alpha}^{\dagger} h_{m n}^{\alpha \beta} e^{i A_{m n}} c_{n \beta}+\text { h.c. }\right) +\sum_{m} A_{0 m} c_{m \alpha}^{\dagger} c_{m \alpha}
\end{aligned}
$$

From this effective field theory, we can compute the system's response. From:

$$ e^{i S_{\text {eff}}[A]} = \int D[c] D\left[c^{\dagger}\right] e^{i \int d t\left[\sum_{m j} c_{m \alpha}^{\dagger}\left(i \partial_{t}\right) c_{m \alpha}-H_0[c,c^\dagger] \right] + \int d^d x \ j\cdot A} $$

we take the functional derivative to obtain the linear response of the system:

$$ j = \frac{\delta S_{eff} [A]}{\delta A} $$

Now, working backwards from the QHE to infer the effective action of the system, we find:

$$
j^{\mu}=\frac{C_{1}}{2 \pi} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

Thus, it can be verified that the following is the effective action of the Chern Insulator:

$$
S_{\mathrm{eff}}=\frac{C_{1}}{4 \pi} \int d^{2} x \int d t A_{\mu} \epsilon^{\mu \nu \tau} \partial_{\nu} A_{\tau}
$$

We find that this term is gauge-invariant, and we call it the Chern-Simons term. We should note that the effective theory has already integrated out the information of the original fermionic system, so the effective theory cannot provide the origin of $C_1$.

+ When studying the fractional quantum Hall effect, we can construct the effective action in a completely analogous way.

## From Chern-Simons Term to 4D TI: 2nd Chern Number

Now let us consider a 4D system. We imagine that the same Chern-Simons term can also be found in a 4D system. By writing down its corresponding equation of motion, we obtain the topological response of the 4D TI. More details can be found in the review by XL Qi and Chapter 13 of Bernevig's Topological Insulators.

The effective action of the 4D TI is:

$$
S_{\mathrm{eff}}=\frac{C_{2}}{24 \pi^{2}} \int d^{4} x d t \epsilon^{\mu \nu \rho \sigma \tau} A_{\mu} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

From the linear response perspective, the 2nd Chern number is:
$$
C_{2}=-\frac{\pi^{2}}{15} \epsilon^{\epsilon \mu \rho \sigma \tau} \int \frac{d^{4} k d \omega}{(2 \pi)^{5}} \operatorname{Tr}\left[\left(G \frac{\partial G^{-1}}{\partial q^{\mu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\nu}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\sigma}}\right)\left(G \frac{\partial G^{-1}}{\partial q^{\tau}}\right)\right.
$$

From the Berry Phase topological perspective, the 2nd Chern number is:

$$
C_{2}=\frac{1}{32 \pi^{2}} \int d^{4} k \epsilon^{i j k \ell} \operatorname{tr}\left[f_{i j} f_{k \ell}\right]
$$
$$ f_{i j}^{\alpha \beta}=\partial_{i} a_{j}^{\alpha \beta}-\partial_{j} a_{i}^{\alpha \beta}+i\left[a_{i}, a_{j}\right]^{\alpha \beta} $$
$$
a_{i}^{\alpha \beta}(\mathbf{k})=-i\left\langle\alpha, \mathbf{k}\left|\frac{\partial}{\partial k_{i}}\right| \beta, \mathbf{k}\right\rangle
$$
where $i, j, k, \ell=1,2,3,4$.

Solving the equations of motion gives the current density corresponding to this effective action:
$$
j^{\mu}=\frac{C_{2}}{8 \pi^{2}} \epsilon^{\mu \nu \rho \sigma \tau} \partial_{\nu} A_{\rho} \partial_{\sigma} A_{\tau}
$$

It is worth noting that since the first-order functional derivative with respect to the external field $A$ yields a result containing second-order terms in $A$, unlike the 2D Chern-Simons term, the effects corresponding to the 4D Chern-Simons term — such as the topological magnetoelectric effect — are nonlinear responses.

Consider a specific example:
$$
A_{x}=0, A_{y}=B_{z} x, A_{z}=-E_{z} t, A_{w}=A_{t}=0
$$
Then $F_{x y}=B_{z}$ and $F_{z t}=-E_{z}$, and we can derive the expression for the 4D current density:

$$ j_{w}=\frac{C_{2}}{4 \pi^{2}} B_{z} E_{z} $$

Or, written as a Hall current in the xy-plane, which requires magnetic and electric fields in the z-direction:
$$
\int d x d y j_{w}=\frac{C_{2}}{4 \pi^{2}}\left(\int d x d y B_{z}\right) E_{z} \equiv \frac{C_{2} N_{x y}}{2 \pi} E_{z}
$$

## From 4D TRB to 3D TRI: Dimensional Reduction and $\mathbb{Z}\rightarrow\mathbb{Z}_2$ Again

Through the 4D Chern-Simons term, we obtained the generalization of TRB TI to 4D, along with its topological invariant — the 2nd Chern Number.

By performing dimensional reduction on the 4D system, we can obtain the corresponding 3D TRI (Time-Reversal Invariant) TI submodel of the parent model. By introducing TRS, we once again obtain a $\mathbb{Z}_2$ topological classification.

Analyzing the physical models of 3D TI yields a series of novel topological phenomena, such as the Surface Half QHE and the topological magnetoelectric effect.

More content can be found in Chapters 14 and 15 of Bernevig's book, as well as the later sections of XL Qi's topological field theory paper.

## From Specific to Arbitrary: Period Table and SPT Phase

We have already recognized the importance of dimension and symmetry in topology. The condition that "two models can be connected by a continuous transformation that preserves a certain symmetry" can serve as a basis for topological classification. This in fact coincides with the definition of homotopy in topology, and it is also the origin of SPT (Symmetry Protected Topological) Phases — topological phases protected by specific symmetries.

Through dimensional reduction, we can obtain the topological effects of the same topological invariant across different dimensions (after making some symmetry changes).

Therefore, we consider the most general model and analyze its symmetries. This may seem extremely complicated, but in fact we only need to study anti-unitary symmetries. Systems with unitary symmetries can always be decomposed into a direct product, yielding diagonal blocks that no longer possess unitary symmetry.

If we further consider local symmetries, Altland has already classified them into 10 types. This is the origin of the 10 symmetry classes on the symmetry side of the Periodic Table. These 10 symmetry classes come from three fundamental symmetries: Time-Reversal Symmetry (TRS), Particle-Hole Symmetry (PHS), and Chiral Symmetry (CS).

When performing dimensional reduction, we need to introduce specific symmetries. For example, going from the 2D TRB Chern Insulator to 1D requires introducing PHS to achieve $\mathbb{Z}_2$ quantization of the Charge Polarization; going from 4D TRB TI to 3D TRI TI requires introducing TRS to obtain a similar $\mathbb{Z}_2$ quantization.

Qingrui Wang from Yau Mathematical Sciences Center offers an online course on topological order. Lectures 5-7 cover Fermionic SPT Phases, which systematically introduce how the Periodic Table mentioned above is formed.

https://qr-wang.github.io/teaching_2021_TQM.html

The review by Ching-Kai Chiu, Jeffrey C.Y. Teo, Andreas P. Schnyder, and Shinsei Ryu also provides a detailed exposition.

https://journals.aps.org/rmp/abstract/10.1103/RevModPhys.88.035005

## Proof

+ Proof of $P(\theta) = -P(2 \pi-\theta)$

$$ P(\theta)= \oint \frac{d k}{2 \pi} \sum_{E_{\alpha}(k)<0}(-i)\left\langle k, \theta ; \alpha\left|\partial_{k}\right| k, \theta ; \alpha\right\rangle $$

$$ = \oint \frac{d k}{2 \pi} \sum_{E_{\bar{\alpha}}(-k)>0}(-i)(\langle-k, 2 \pi-\theta ; \bar{\alpha} \mid)^{*} \partial_{k}|-k, 2 \pi-\theta ; \bar{\alpha}\rangle^{*} $$

$$ = -P(2 \pi-\theta) $$

+ 1D PHS $\mathbb{Z}_2$-classification
	  
Consider two different parameterizations $h(k, \theta)$ and $h^{\prime}(k, \theta)$, satisfying $h(k, 0)=h^{\prime}(k, 0)=h_{1}(k)$, $h(k, \pi)=h^{\prime}(k, \pi)=h_{2}(k)$. Denoting the polarization $P(\theta)$ and $P^{\prime}(\theta)$ corresponding to $h(k, \theta)$ and $h^{\prime}(k, \theta)$, respectively, the Chern number difference between $h$ and
$h^{\prime}$ is given by
$$
C[h]-C\left[h^{\prime}\right]=\int_{0}^{2 \pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right)
$$
Define the new interpolations $g_{1}(k, \theta)$ nnd $g_{2}(k, \theta)$ as
$$
\begin{array}{l}
g_{1}(k, \theta)=\left\{\begin{array}{cc}
h(k, \theta), & \theta \in[0, \pi] \\
h^{\prime}(k, 2 \pi-\theta), & \theta \in[\pi, 2 \pi]
\end{array}\right. \\
g_{2}(k, \theta)=\left\{\begin{array}{cc}
h^{\prime}(k, 2 \pi-\theta), & \theta \in[0, \pi] \\
h(k, \theta), & \theta \in[\pi, 2 \pi]
\end{array}\right.
\end{array}
$$
$g_{1}(k, \theta)$ and $g_{2}(k, \theta)$ are obtained by recombination of the two paths $h(k, \theta)$ and $h^{\prime}(k, \theta)$, as shown in Fig. 4. From the construction of $g_{1}$ and $g_{2}$, it is straightforward to see that
$$
\begin{array}{l}
C\left[g_{1}\right]=\int_{0}^{\pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right) \\
C\left[g_{2}\right]=\int_{\pi}^{2 \pi} d \theta\left(\frac{\partial P(\theta)}{\partial \theta}-\frac{\partial P^{\prime}(\theta)}{\partial \theta}\right)
\end{array}
$$
Thus $C[h]-C\left[h^{\prime}\right]=C\left[g_{1}\right]+C\left[g_{2}\right]$. On the other hand, from Eq. (37) we know $C\left[g_{1}\right]=C\left[g_{2}\right]$, so that $C[h]-C\left[h^{\prime}\right]=2 C\left[g_{1}\right]$. Since $C\left[g_{1}\right] \in \mathbb{Z}$, we obtain that $C[h]-C\left[h^{\prime}\right]$ is even for any two interpolations $h(k, \theta)$ and $h^{\prime}(k, \theta)$ between $h_{1}(k)$ and $h_{2}(k)$. Intuitively, such a conclusion simply comes from the fact that the Chern number $C[h]$ and $C\left[h^{\prime}\right]$ can be different only if there are singularities between these two paths, while the positions of the singularities in the parameter space are always symmetric under particle-hole symmetry, as shown in Fig. 4.

Based on the discussions above, we can define the "relative Chern parity" as
$$
N_{1}\left[h_{1}(k), h_{2}(k)\right]=(-1)^{C[h(k, \theta)]},
$$
which is independent of the choice of interpolation $h(k, \theta)$, but only determined by the Hamiltonians $h_{1}(k), h_{2}(k)$. Moreover, for any three particle-hole symmetric Hamiltonians $h_{1}(k), h_{2}(k), h_{3}(k)$, it is easy to

prove that the Chern parity satisfies the following associative law:
$$
N_{1}\left[h_{1}(k), h_{2}(k)\right] N_{1}\left[h_{2}(k), h_{3}(k)\right]=N_{1}\left[h_{1}(k), h_{3}(k)\right] .
$$

+ ShunQing Shen Chapter 4 Section 8,9

**4.8 Time Reversal Symmetry and the $\mathbb{Z}_{2}$ Index**

Time reversal symmetry implies that $[\mathcal{H}(\mathbf{r}), \Theta]=0$, where the time reversal operator $\Theta=-i \sigma_{y} K$ and $K$ is the complex conjugation. Note that in the band theory, time reversal symmetry means that
$$
H(-\mathbf{k})=\Theta H(\mathbf{k}) \Theta^{-1}
$$
since the good quantum number $\mathbf{k}$ has already replaced the momentum operator $\mathbf{p}=-i \hbar \nabla$ in the Hamiltonian, and the later changes a minus sign under time reversal $\Theta$. In the Brillouin zone of a square lattice, there are 4 ( 8 for a cubic lattice in three dimensions) time reversal ifarariant points satisfying $-\Gamma_{i}=\Gamma_{i}+n_{i} \mathbf{G}$, where $G$ is a reciprocal lattice vector and $n_{i}=0$ or $1[11,13,17]$. At these points, $\Gamma_{i}=n_{i} \mathrm{G} / 2$
$$
H\left(\Gamma_{i}\right)=\Theta H\left(\Gamma_{i}\right) \Theta^{-1}
$$
always holds; therefore, the eigenstates are always at least doubly degenerate due to the Kramers degeneracy. A pair of such energy bands $E_{2 n-1}(k)$ and $E_{2 n}(k)$ is called a Kramers pair, as illustrated in Fig. 4.3. These two bands (labeled as $(n, I)$ and $(n, I I)$, respectively) are related to each other by time reversal operation accompanying with a phase factor [11]. Their crossings at time reversal invariant points are protected by time reversal symmetry. If a Kramers pair is isolated from other pairs by finite gaps, a topological invariant associated with this pair can be defined.

For simplicity, we consider a one-dimensional system and suppose that there is no additional degeneracy other than those required by time reversal symmetry. Therefore, the $2 N$ eigenstates can be divided into $N$ pairs that satisfy
$$
\left|u_{n}^{I}(-k)\right|=-\mathrm{e}^{i \chi_{k, n}} \Theta\left|u_{n}^{I I}(k)\right|
$$

Then
$$
\Theta\left|u_{n}^{I}(-k)\right\rangle=-\Theta \mathrm{e}^{i \chi k, n} \Theta\left|u_{n}^{I I}(k)\right\rangle=\mathrm{e}^{-i \chi_{k, n}}\left|u_{n}^{I I}(k)\right\rangle
$$
as $\Theta^{2}=-1$ for electrons with spin $\frac{1}{2}$. Thus, one has the relation
$$
\left|u_{n}^{I I}(-k)\right|=\mathrm{e}^{i \chi-k, n} \Theta\left|u_{n}^{I}(k)\right\rangle
$$
The partial polarization associated with one of the categories $s=I$ and $I I$ can be written as
$$
P^{s}=\int_{B Z} \frac{d k}{2 \pi} A_{k}^{s},
$$
with $A_{k}^{s}=i \sum_{n}^{s}\left\langle u_{n}^{s}(k)\left|\nabla_{k}\right| u_{n}^{s}(k)\right\rangle$. It is invariant (up to a lattice translation) under changes in the phases of $\left|u_{n}^{I}(k)\right\rangle$ and $\left|u_{n}^{I I}(k)\right\rangle$. However, they appear to depend on the arbitrary choice of the label $I$ and $I I$ assigned to each band. To make this invariance explicit for $P^{s}$, we separate the integral into two parts:
$$
\begin{aligned}
P^{I} &=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}^{I}+\int_{-\pi}^{0} \frac{d k}{2 \pi} A_{k}^{I} \\
&=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}^{I}+\int_{0}^{\pi} \frac{d k}{2 \pi} A_{-k}^{I}
\end{aligned}
$$
Using the time reversal constraint,
$$
\begin{array}{r}
\left.\left\langle\Theta u_{n}^{I I}(k)\right| \partial_{k}+\Theta+u_{n}^{I I}(k)\right)=-\left\langle u_{n}^{I I}(k)\right| \partial_{k} \\
A_{-k}^{I}=A_{k}^{I I}-\sum_{n} \partial_{k} \chi_{k, n}
\end{array}
$$
It then follows that
$$
P^{I}=\int_{0}^{\pi} \frac{d k}{2 \pi} A_{k}-\frac{1}{2 \pi} \sum_{n}\left(\chi_{\pi, n}-\chi_{0, n}\right)
$$
where $A_{k}=A_{k}^{I}+A_{k}^{I I}$. Introduce the $U(2 N)$ matrix
$$
w_{m n}(k)=\left\langle u_{m}(-k)|\Theta| u_{n}(k)\right\rangle
$$
Then only nonzero terms are
$$
\begin{array}{l}
\left\langle u_{n}^{I}(-k)|\Theta| u_{n}^{I I}(k)\right\rangle=-\mathrm{e}^{-i \chi_{k, n}} \\
\left\langle u_{n}^{I I}(-k)|\Theta| u_{n}^{I}(k)\right\rangle=\mathrm{e}^{-i \chi_{-k, n}}
\end{array}
$$

The matrix $w$ is a direct product of $2 \times 2$ matrices with $-\mathrm{e}^{-i x i n}$ and $\mathrm{e}^{-i x-t / n}$ on the off-diagonal. At $k=0$ and $\pi, w$ is antisymmetric. An antisymmetric matrix may be characterized by a Pfaffian, whose square is equal to the determinant. Then we have
$$
\frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}=\exp \left[i \sum_{n}\left(\chi_{\pi n}-\chi_{0 n}\right)\right]
$$
Thus,
$$
P^{\prime}=\frac{1}{2 \pi}\left[\int_{0}^{\pi} d k A_{k}+i \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right]
$$
A similar formula can be obtained for $P^{I I}$. It follows from the time reversal symmetry that $P^{I I}=P^{I}$ modulo an integer, reflecting the Kramers pairing of the Wannier states. The charge polarization for one Kramers pair of states is
$$
P_{\rho}=P^{I}+P^{I I}
$$
and the time reversal polarization is defined as
$$
\begin{aligned}
P_{\theta} &=P^{I}-P^{I I} \\
&=\frac{1}{2 \pi}\left[\int_{0}^{\pi} d k A_{k}-\int_{-\pi}^{0} d k A_{k}+2 i \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right]
\end{aligned}
$$
In terms of the matrix $w_{n m}$, the formula can be written in a compact form:
$$
P_{\theta}=\frac{1}{2 \pi i}\left[\int_{0}^{\pi} d k \operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right]-2 \ln \frac{\operatorname{Pf}[w(\pi)]}{\operatorname{Pf}[w(0)]}\right] .
$$
In the matrix $w$, only nonzero elements are off-diagonal:
$$
\begin{aligned}
\operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right] &=\operatorname{Tr}\left[\left(\begin{array}{cc}
0 & \mathrm{e}^{-i \chi-k, n} \\
-\mathrm{e}^{i \chi_{k, n}} & 0
\end{array}\right) \nabla_{k}\left(\begin{array}{cc}
0 & -\mathrm{e}^{-i \chi_{k, n}} \\
\mathrm{e}^{i \chi-k, n} & 0
\end{array}\right)\right] \\
&=i \nabla_{k} \chi-k, n-i \nabla_{k} \chi_{k, n} .
\end{aligned}
$$
Using the unitarity of $w$, we have
$$
\operatorname{Tr}\left[w^{\dagger} \nabla_{k} w\right]=\operatorname{Tr}\left[\nabla_{k} \ln w(k)\right]=\nabla_{k} \ln \operatorname{det}[w(k)]
$$
Thus, $P_{\theta}$ can be expressed as
$$
P_{\theta}=\frac{1}{2 \pi i}\left[\ln \frac{\operatorname{det}(w(\pi))}{\operatorname{det}(w(0))}-2 \ln \frac{\operatorname{Pf}(w(\pi))}{\operatorname{Pf}(w(0))}\right]
$$

$$
(-1)^{P_{\theta}}=\frac{\sqrt{\operatorname{det}(w(0))}}{\operatorname{Pf}(w(0))} \frac{\sqrt{\operatorname{det}(w(\pi))}}{\operatorname{Pf}(w(\pi))}
$$
In general, for a cyclic process of $H(t+T)=H(t)$, it follows that
$$
\begin{array}{l}
H\left(t_{1}^{*}=0\right)=\Theta H(0) \Theta^{-1} \\
H\left(t_{1}^{*}=T / 2\right)=\Theta H(T / 2) \Theta^{-1}
\end{array}
$$
The change of time reversal polarization is gauge invariant
$$
v=\left[P_{\theta}(T / 2)-P_{\theta}(0)\right] \bmod 2
$$
Consider the mapping between the time reversal invariant momenta $\Gamma_{i}$ and the time invariant point of time $t_{i}^{*}$; we conclude that the topological invariant can be written as
$$
(-1)^{v}=\prod_{i} \frac{\sqrt{\operatorname{det}\left(w\left(\Gamma_{i}\right)\right)}}{\operatorname{Pf}\left(w\left(\Gamma_{i}\right)\right)}
$$
Since
$$
\operatorname{det}\left(w\left(\Gamma_{i}\right)\right)=\left[\operatorname{Pf}\left(w\left(\Gamma_{i}\right)\right)\right]^{2},
$$
the right-hand side of Eq. $(4.115)$ is always $+1$ or $-1$. Correspondingly $v$ is only an integer modulo 2 , that is, 0 or 1 . Thus, the time reversal polarization defines two distinct polarization states, topologically trivial $(v=0)$ and nontrivial $(v=1)$. Fu and Kane proposed thtit the value of $v$ is related to the presence or the absence of a Kramers degenerate states at the end of a finite system [11].

If an insulator has the additional inversion symmetry, there is a simplified algorithm to calculate the $\mathrm{Z}_{2}$ invariant. Suppose that the Hamiltonian $H$ has an inversion symmetry,
$$
H(-\mathbf{k})=P H(\mathbf{k}) P^{-1},
$$
where the parity operator is defined by
$$
P\left|\mathbf{r}, s_{z}\right\rangle=P\left|-\mathbf{r}, s_{z}\right\rangle .
$$
Here $\mathbf{r}$ is the coordinate and $s_{z}$ is the spin which is unchanged by the parity $P$ because it is a pseudovector. An explicit consequence of the combination of time reversal symmetry and inversion symmetry is the fact that the Berry curvature must vanish:
$$
F(\mathbf{k})=\nabla_{\mathbf{k}} \times \mathbf{A}(\mathbf{k})=0
$$
It follows from the definition of the Berry curvature that it is odd under time reversal, $F(-\mathbf{k})=-F(\mathbf{k})$, and even under inversion, $F(-\mathbf{k})=F(\mathbf{k})$. Considering the $m$ th pair of the occupied energy bands at time reversal invariant momentum $\Gamma_{i}$, we define$\left.P\left|u_{2 m,} \Gamma_{i}\right\rangle=\xi_{2 m}\left(\Gamma_{i}\right) \mid u_{2 m,} r_{i}\right)$ where the parity eigenvalues $\xi_{2 m}\left(\Gamma_{i}\right)=+1$ or $-1$. The degenerate Kramers partners share the same eigenvalue $\xi_{2 m}=\xi_{2 m-1}$. In this case, one has a simple formula to calculate 8 [13]:
$$
(-1)^{v}=\prod_{i} \prod_{m=1}^{N} \xi_{2 m}\left(\Gamma_{i}\right) .
$$
In Sect. 3.6, we have already used this result to classify the topological phases in the lattice model.

Note on Pfaffian: In muathematics, a skew-symmetric matrix is a square matrix $A$ whose transpose is its negative, $A=-A^{T}$. The determinant of a skew-symmetric muirix $A$ can always be written as the square of a polynomial in the matrix entries, which is called the Pfaffian of the matrix, denoted by $\operatorname{Pf}(A)$, that is,
$$
\operatorname{det}(A)=\operatorname{Pf}(A)^{2}
$$
The term Pfaffian was introduced by [15] who named it after Johann Friedrich Pfaff. The Pfaffian is nonvanishing only for $2 n \times 2 n$ skew-symmetric matrices, in which case it is a polynomial of degree $n$.
For example,
$\operatorname{Pf}\left(\begin{array}{cc}0 & a \\ -a & 0\end{array}\right)=a$,
$\operatorname{Pf}\left(\begin{array}{cccc}0 & a & b & c \\ -a & 0 & d & e \\ -b & -d & 0 & f \\ -c & -e & -f & 0\end{array}\right)=a f-b e+d c$

**4.9 Generalization to Two and Three Dimensions**

Generalization of the $Z_{2}$ invariant from two to three dimensions is a milestone in the development of topological insulator. The topological invariant characterizing a two-dimensional band structure may be constructed by rolling a two-dimensional system into a cylinder as shown in Fig. 4.4a. Then the magnetic flux threading the cylinder plays the role of the circumferential crystal momentum $k_{x}$, with $\phi=0$ and $\phi=\phi_{0} / 2$ corresponding to two edge time reversal momenta $k_{x}=\Lambda_{1}=0$ and $k_{x}=\Lambda_{2}=\pi / a$. The $Z_{2}$ invariant characterizes the change of the time reversal polarization in the Kramers degeneracy at the ends of the one-dimensional system between $k_{x}=\Lambda_{1}$ and $k_{x}=\Lambda_{2}$. The change is related to the bulk band structure for a two-dimensional system with the periodic boundary condition. For a square lattice, there are four time reversal invariant momenta in the first Brillouin zone:
$$
\Gamma_{n_{x} n_y}=\left(\frac{n_{x}}{2} \mathbf{G}_{x}, \frac{n_{y}}{2} \mathbf{G}_{y}\right)
$$

with $n_{x}, n_{y}=0,1$. For an edge perpendicular to $\mathbf{G}_{y}$, the one-dimensional edge time reversal invariant momenta are $k_{x}=\Lambda_{1}$ and $k_{x}=\Lambda_{2}$, which satisfy $\Gamma_{1, n_{y}}-\Gamma_{0, n_{y}}=$ $\frac{\mathrm{G}_{x}}{2}$. Thus, the time reversal polarization can be expressed as $\pi_{x}=\delta_{x 1} \delta_{x 2}$, where
$$
\delta_{x i}=\frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{i, y}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{i, y}\right)\right]}=\pm 1
$$
However, $\pi_{x}$ is not a gauge invariant. A $k$-dependent gauge transformation can change the sign of any pair of $\delta_{i}$. If we roll the system into a cylinder along another direction, we can calculate the time reversal polarization $\pi_{y}=\delta_{y 1} \delta_{y 2}$. The product $\pi_{x} \pi_{y}$ is gauge invariant:
$$
(-1)^{v}=\prod_{n_{x}, n_{y}=0,1} \frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{n_{x}, n_{y}}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{n_{x}, n_{y}}\right)\right]}
$$
This $v$ can be equal to 0 or 1 and define a single $Z_{2}$ invariant in two dimensions.

The $Z_{2}$ invariant for three-dimensional crystals can be reduced to the problems in two dimensions $[11,14,16]$. The three-dimensional Brillouin zone can be rolled into a donut along the $x$ - and $y$-direction as illustrated in Fig. 4.4c. There are eight time reversal invariant momenta for three-dimensional systems:
$$
\Gamma_{i=\left(n_{1}, n_{2}, n_{3}\right)}=\left(\frac{n_{1}}{2} \mathbf{G}_{1}, \frac{n_{2}}{2} \mathbf{G}_{2}, \frac{n_{3}}{2} \mathbf{G}_{3}\right)
$$
with $n_{j}=0,1$. They can be viewed as vertexes of a parallelepiped. For a fixed $n_{1}$, for example, $n_{1}=1$, the point set
$$
\left(\frac{n_{1}}{2} \mathbf{G}_{1}, \frac{a_{2}}{2} \mathbf{G}_{2}, \frac{a_{3}}{2} \mathbf{G}_{3}\right)
$$
for all $a_{2}, a_{3} \in\left[-\frac{1}{2}, \frac{1}{2}\right.$ ) defines a two-dimensional Brillouin zone of a twodimensional system respecting time reversal symmetry, for which a $Z_{2}$ invariant can be calculated from the method for two-dimensional system, referred as $v_{n 1=1}$. The other five invariants $v_{n_{1}=0}, v_{n_{2}=0,1}$, and $v_{n_{3}=0,1}$ can be defined in a similar way. These six invariants are associated with six planes of the above parallelepiped. Since they belong to the same three-dimensional crystal, only four of them are independent due to the constraints $[11,14]$
$$
v_{n_{1}=0} \cdot v_{n_{1}=1}=v_{n_{2}=0} \cdot v_{n_{2}=1}=v_{n_{3}=0} \cdot v_{n_{3}=1} \bmod 2
$$
The four independent invariants can be chosen as, say, $v_{0}=v_{n_{1}=0} v_{n_{1}=1}, v_{1}=$ $v_{n_{1}=1}, v_{2}=v_{n_{2}=1}$, and $v_{3}=v_{n_{3}=1}$. The indices $v_{0} ;\left(v_{1} v_{2} v_{3}\right)$ reflect the topology of the surface states $[13,17] . v_{0}$ is given by
$$
(-1)^{v_{0}}=\prod_{n_{1}, n_{2}, n_{3}=0,1} \frac{\sqrt{\operatorname{det}\left[w\left(\Gamma_{n_{1}, n_{2}, n_{3}}\right)\right]}}{\operatorname{Pf}\left[w\left(\Gamma_{n_{1}, n_{2}, n_{3}}\right)\right]} .
$$
If $\nu_{0}=1$, then the system is a strong topological insulator, with an odd number of Dirac cones on all surfaces of the crystal. If $\nu_{0}=0$, then the crystal is a weak topological insulator, with an even number (including 0) of Dirac cones at the surfaces. The latter one is topologically equivalent to a two-dimensional insulator and therefore is not robust against disorder. Let us take $0 ;(001)$ as an example [13]. The surface states corresponding to the two-dimensional Brillouin zone spanned by $G_{2}$ and $G_{3}$ (with index $v_{1}=0$ ) have two Dirac cones, and the same for the surface states in the Brillouin zone spanned by $G_{1}$ and $G_{3}$, with index $\nu_{2}=0$. But there is no surface states in $G_{2}-G_{3}$ plane, with index $v_{3}=1$.

## Acknowledgments

This note has once again come to a close. I would like to thank all my friends on Zhihu for their support so far. I hope that my meandering learning journey can be of some help to you. Let us encourage each other and move forward together!
