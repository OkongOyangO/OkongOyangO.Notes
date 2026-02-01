---
title: "🤫平均场近似与变分法｜Hartree, Fock, BCS能1:1:1混用吗？"
date: 2023-03-11T22:30:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Mean Field"]
categories: ["Physics Notes"]
---

本文旨在介绍平均场近似，同时阐述其变分法本质。

Hartree, Fock, BCS这一个一个一个平均场近似，看似是一个一个一个互不相容的decouple方法，但利用平均场近似的变分法本质，我们发现他们事实上确实可以1:1:1混着用。

<!--more-->

## Preface

本文灵感首先来自来自和[@ykli](https://www.zhihu.com/people/li-yong-kang-9-34)同学的讨论，在此特别感谢[@ykli](https://www.zhihu.com/people/li-yong-kang-9-34)在推导过程中给予的大量帮助。

这个问题在physics stackexchange网站上也被提及（被称为“Multi-channel Mean Field Theory”），在此也放上链接供大家参考：

https://physics.stackexchange.com/questions/742905/multi-channel-mean-field-theory

同时，[@阿兰那行](https://www.zhihu.com/people/deng-wwzz)学长关于“物理圈黑话”的回答也给了我相当多的灵感，有兴趣的读者可以移步：

https://www.zhihu.com/question/410499049/answer/2442413803

## Introduction

对于相互作用体系，系统完整的哈密顿量为：

$$
\begin{aligned}
\hat{H} = \hat{H}_0 + \hat{V}_{int}
\end{aligned}
$$

其中，$\hat{H}_0 \sim \sum c^\dagger c$，为费米子产生湮灭算符的二次型部分，比较容易处理成independent free particle。

而$\hat{V}_{int} \sim \sum c^\dagger c^\dagger c c$，为相互作用部分。

由于相互作用的存在，我们比较难求系统的基态波函数或者平衡态密度矩阵，从而比较难以计算相互作用体系的各种信息。因此，我们常常用各种近似方法来处理。

平均场近似便是一种方法，我们取一个可以严格解的平均场近似哈密顿量：

$$
\begin{aligned}
\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}
\end{aligned}
$$

使得$\hat{V}_{mf}$也为二次型，则比较好求严格解，我们便可以用这个平均场近似哈密顿量的解来近似给出系统的各种性质。

## Mean Field Theory by Decoupling

但取近似不能瞎取，也需要一定技巧。

量子力学课本中教我们，平均场近似就是把算符的quantum fluctuation部分给忽略，即Decoupling Method：

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

其中mean field部分保留了算符涨落$\delta A$的零阶和一阶部分，而quantum fluctuation包含了算符涨落$\delta A$的二阶部分。

故不难理解，量子涨落较小时，平均场近似较为准确。

对于二体相互作用$\hat{V}_{int}$：

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

我们有三种方法将其分解成$\hat{A}^\dagger\hat{A}$（的和）的形式：

+ Density Channel (Hartree)：$\hat{A}_{i}^{H} = c_i^\dagger c_i$
+ Exchange Channel (Fock)：$\hat{A}_{ij}^{F} = c_i^\dagger c_j$
+ Cooper Channer (BCS)：$\hat{A}_{ij}^{BCS} = c_i c_j$

以Density Channel为例，Hartree平均场的Decoupling过程为：

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

对于Fock平均场Decoupling：

$$
\begin{aligned}
    & \hat{V}_{int} = - \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{F} }^\dagger \hat{A}_{ij}^{F} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx -\frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{F}}^\dagger\rangle  \hat{A}_{ij}^{F} +  {\hat{A}_{ij}^{F}}^\dagger \langle \hat{A}_{ij}^{F}\rangle - \langle {\hat{A}_{ij}^{F}}^\dagger\rangle \langle {\hat{A}_{ij}^{F}}\rangle \right)\\
    & \equiv \hat{V}_{F}
\end{aligned}
$$

对于BCS平均场Decoupling：

$$
\begin{aligned}
    & \hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{BCS} }^\dagger \hat{A}_{ij}^{BCS} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx \frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle  \hat{A}_{ij}^{BCS} +  {\hat{A}_{ij}^{BCS}}^\dagger \langle \hat{A}_{ij}^{BCS}\rangle - \langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle \langle {\hat{A}_{ij}^{BCS}}\rangle \right)\\
    & \equiv \hat{V}_{BCS}
\end{aligned}
$$

## Problem of Decoupling

但这样，我们似乎只能对二体相互作用作一种近似，或者Hartree，或者Fock，或者BCS。

但事实上，我们经常听到的“Hartree-Fock平均场近似”，似乎用了两种近似.

$$
\begin{aligned}
\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

那么这样做，会不会产生重复计算的问题？

还是说我们要把$\hat{V}_{int}$拆成$\frac{\hat{V}_{int}}{2}$和$\frac{\hat{V}_{int}}{2}$来使用？

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{2} + \frac{\hat{V}_{int}}{2} \approx \frac{\hat{V}_{H}}{2} + \frac{\hat{V}_{F}}{2}
\end{aligned}
$$

还是拆成$\frac{\hat{V}_{int}}{3}$和$\frac{2\hat{V}_{int}}{3}$？

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{3} + \frac{2\hat{V}_{int}}{3} \approx \frac{\hat{V}_{H}}{3} + \frac{2\hat{V}_{F}}{3}
\end{aligned}
$$

既然有“Hartree-Fock平均场近似”，为什么不搞一个“Hartree-Fock-BCS平均场近似”？上述的重复计算问题，所谓的拆分问题又如何解决？

事实上，$\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}$才是正确的做法，但是如果用Decoupling Method的方法去理解Hartree-Fock平均场近似，总给人一种重复计算的感觉：

$$
\begin{aligned}
\hat{V}_{int} + \hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

这是Decoupling表述不严谨所导致的。接下来，我们将说明平均场近似作为一种非微扰方法，本质是一种“猜解再优化”的变分法。

之后，我们再从变分法出发，来证明选择不同的decoupling方法（Hartree、Fock、BCS）事实上互不影响，只是给猜测解增加了新的独立参数，并不会造成所谓的重复计算问题。

## Variational Method for Finite Temperature

我们已经很熟悉零温的变分法。

对于零温体系，我们常用变分法来“猜”Hamiltonian的基态波函数$|\Psi(\lambda)\rangle$，$\lambda$为调节“猜测基态波函数”的参数，通过调节参数，观察基态能量泛函：

$$
\begin{aligned}
E[\Psi(\lambda)] = \frac{\langle \Psi(\lambda) | \hat{H} | \Psi(\lambda) \rangle}{\langle \Psi(\lambda) | \Psi(\lambda) \rangle}
\end{aligned}
$$

使其最小，我们可以说$|\Psi(\lambda)\rangle$和基态波函数十分接近。之后我们便用此猜测解来计算系统基态（零温）的各种性质。

类似的，变分原理可以运用到有限温体系中，只不过将“猜测基态波函数”变为“猜测平衡态密度矩阵”。

此处我们用正则系综进行推导，且为了推导方便，我们取单位制单位制$k_B = 1$。

对于有限温，平衡态密度矩阵为：

$$
\begin{aligned}
\hat{\rho}_{eq} = \frac{e^{-\beta \hat{H}}}{\operatorname{Tr} (e^{-\beta \hat{H}})}
\end{aligned}
$$

“猜测平衡态密度矩阵”总要有特定的形式，我们假设系统的密度矩阵为某个辅助哈密顿量$\hat{H}_{mf}(\lambda)$的平衡态密度矩阵：

$$
\begin{aligned}
\hat{\rho}_{mf}(\lambda) \equiv \hat{\rho}_{eq} [\hat{H}_{mf}(\lambda)] \equiv \frac{e^{-\beta \hat{H}_{mf}(\lambda)}}{\operatorname{Tr} (e^{-\beta \hat{H}_{mf}(\lambda)})}
\end{aligned}
$$

其中$\lambda$为调节哈密顿量$\hat{H}_0$（进而调节“猜测平衡态密度矩阵”）的参数，例如平均场强度、order parameter, etc.

此处我们用“mf”下标，旨在暗示平均场近似就是把这里的提供“猜测平衡态密度函数”的“辅助哈密顿量”取成“平均场近似哈密顿量”，但事实上，对于一般的变分法，“辅助哈密顿量”可以去成任何形式，甚至密度矩阵也可以随便取，不一定非得是某个哈密顿量的平衡态密度矩阵。

此时变分极值条件，也从“使得能量泛函最小”，推广到“使得自由能泛函最小”。

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda)] & = \langle \hat{H} \rangle_{\rho_{mf}(\lambda)} - TS \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{H}) + T \operatorname{Tr} (\hat{\rho}_{mf}(\lambda) \ln \hat{\rho}_{mf}(\lambda) )
\end{aligned}
$$

注意，此处的$\hat{H}$为系统完整的哈密顿量，而非我们的猜测哈密顿量$\hat{H}_{mf}(\lambda)$。

事实上，在平均场近似中，我们用平均场近似后的哈密顿量对应的平衡态密度矩阵来作为“猜测平衡态密度矩阵”。为此，我们需要验证，直接取平均场近似，忽略掉量子涨落，恰好就是自由能泛函的变分极值条件。从而证明平均场近似确实是一种变分法。

在平均场近似中，我们把完整哈密顿量$\hat{H} = \hat{H}_0 + \hat{V}_{int}$中的相互作用部分，替换成一个含参的二次型算符，即

$$
\begin{aligned}
\hat{H}_{mf}(\lambda) = \hat{H}_0 + \hat{V}_{mf}(\lambda)
\end{aligned}
$$

将四次型的相互作用算符，换成二次型平均场算符，会破环一些哈密顿量的对称性，这最终反映在了猜测波函数或者猜测密度算符的对称性破缺中。

在平均场中便是这样，选择不同的channel代表选择破坏不同的对称性。例如，BCS理论选择破坏电荷守恒（U(1)对称性）。

$$
\begin{aligned}
\hat{V}_{mf}(\lambda) \sim \sum \lambda c^\dagger c^\dagger + h.c.
\end{aligned}
$$

而事实上，BCS超导相变中确实会发生对称性自发破缺（Spontaneous Symmetry Breaking），使得严格基态波函数或严格平衡态密度算符相比完整哈密顿量$\hat{H} = \hat{H}_0 + \hat{V}_{int}$，对称性更少。

这说明平均场近似虽然是一种近似方法，但确实抓住了相变过程中的一些essence。所以在量子涨落不大（远离量子相变点）的情况下，我们常常使用平均场近似的对量子体系做出一些近似的预言。

## Variational Method

我们不妨记：

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

需要注意$F[\hat{\rho}(\lambda) ] \neq F_{mf}$，两者相差：

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda) ] - F_{mf} = \langle \hat{V}_{int} - \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

很容易有这样一个误解：对于$F_{mf}$，$\hat{H}_{mf}$的平衡态的密度矩阵本身就是使其最小的密度矩阵，故有

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} = 0
\end{aligned}
$$

但这只在参数$\lambda$固定的时候，即固定的哈密顿量$\hat{H}$不变的情况下，才满足$F_{mf}$的极值条件。$\frac{\partial F_{mf}}{\partial \lambda}$还需要严格计算：

首先，由于$F_{mf}$就是$\hat{H}_{mf}$的平衡态自由能，故我们能便利的得到：

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

从而,

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} & = -T \frac{1}{\mathcal{Z}_{mf}}\frac{\partial \mathcal{Z}_{mf}}{\partial \lambda} \\
& = - T \frac{\operatorname{Tr} ( -\beta \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \frac{\operatorname{Tr} (  \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{X} ) \\
& =  \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

即平均场相互作用$\hat{V}_{mf}$部分序参量的期望值，一般而言平均场近似计算的序参量非零，说明体系（至少在平均场近似下）有特定的order。

利用上面的结论，为了让自由能泛函$F[\hat{\rho}(\lambda) ]$取极值，现在我们只需令：

$$
\begin{aligned}
& \frac{\partial}{\partial \lambda} (F[\hat{\rho}(\lambda) ] - F_{mf}) \\
& = \frac{\partial}{\partial \lambda} \langle \hat{V}_{int}  \rangle_{\rho_{mf}(\lambda)} - \frac{\partial}{\partial \lambda} \langle \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)} \\
& = -\frac{\partial}{\partial \lambda} F_{mf} = - \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

再利用$\hat{V}_{mf} = \lambda \hat{X}$的形式，可以进一步简化。

注意对$\hat{V}_{mf} = \lambda \hat{X}$和$\hat{\rho}_{mf}(\lambda)$中的$\lambda$均要求导：

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

从而，自由能泛函极值条件可以写成：

$$
\begin{aligned}
\frac{\partial}{\partial \lambda} F[\hat{\rho}(\lambda) ] = 0\  \Leftrightarrow \ 
\frac{\partial}{\partial \lambda} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\lambda)}  = \lambda \frac{\partial }{\partial \lambda}\langle  \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

我们还可以吧这种变分推广到多个参量$\{\lambda_i\}$的情形，使得变分自由度更高，从而让猜测解更接近真实情况。

综上，如果将某（一般只包含二次型的）平均场哈密顿量$\hat{H}_{mf}(\{\lambda_i\}) = \hat{H}_0 + \sum_i \lambda_i \hat{X}_i$对应的平衡态密度矩阵$\rho_{mf}(\{\lambda_i\})$作为猜测解，去计算自由能泛函变分，则使得自由能泛函最小（最接近真实平衡态）的参数$\{\lambda_i\}$取值满足以下条件：

$$
\begin{aligned}
\frac{\partial}{\partial \lambda_i} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}  = \lambda_i \frac{\partial }{\partial \lambda_i}\langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

我们还能进一步利用链式法则，将变分极值条件进一步写成：

$$
\begin{aligned}
\lambda_i  = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}} 
\end{aligned}
$$

这样可以直接得到变分极值条件对应的参数（物理意义是序参量）。

不过这个等式过于形式化，我们可以通过具体例子的计算，发现这与平均场近似说的是一回事。

对于一般的二体相互作用：

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

而一般的平均场相互作用会取成二次型，这样能够严格求解成相互独立的元激发，此处我们取最一般的形式：

$$
\begin{aligned}
\hat{V}_{mf} & = \underbrace{\sum_{i} \lambda_i^{H} c_i^\dagger c_i}_{\text{Hartree}} \\
& + \underbrace{\sum_{i\neq j} \lambda_{ij}^{F} c_i^\dagger c_j }_{\text{Fock}} \\
& + \underbrace{\sum_{i,j} (\lambda_{ij}^{BCS} c_i^\dagger c_j^\dagger  + \bar{\lambda}_{ij}^{BCS} c_j c_i )}_{\text{BCS}}
\end{aligned}
$$

其中，第一行、第二行、第三行分别为Hartree、Fock、BCS平均场部分。

此处我们没有直接用前面所谓的decoupling method：

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

而是取了一个系数完全待定的哈密顿量，之后我们可以证明在取到变分极值的时候，这个哈密顿量就是用decoupling method获得的“平均场近似哈密顿量”。

同时也正是因为系数完全待定，我们可以随意的增加或者减少第一行、第二行、第三行中的各项，因为这只是增加、减少变分的参数罢了。

下面求$\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}$，即严格的二体相互作用算符在平均场对应平衡态下的期望值。

我们需要用到Wick定理，因为mean field的哈密顿量是二次型的，Generating Functional便是高斯型的，从而所以平衡态费米算符的期望值可以严格分解成两两费米算符的contraction。

$$
\begin{aligned}
\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} & = \frac{1}{2} \sum_{ij}V_{ij} \langle c_i^\dagger c_j^\dagger c_j c_i \rangle_{\rho_{mf}(\{\lambda_i\})} \\
& = \frac{1}{2} \sum_{ij}V_{ij} (\langle c_i^\dagger  c_i \rangle \langle c_j^\dagger  c_j \rangle \\
& - \langle c_i^\dagger  c_j \rangle \langle c_j^\dagger  c_i \rangle + \langle c_i^\dagger  c_j^\dagger \rangle \langle c_j  c_i \rangle)
\end{aligned}
$$

从而利用变分极值条件，我们有：

$$
\begin{aligned}
    \lambda_i^H & = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  c_i^\dagger c_i \rangle_{\rho_{mf}(\{\lambda_i\})}} \\
    & = \frac{1}{2} \sum_j \left( V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} +  V_{ji} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} \right)\\
    & = \sum_{j} V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

此处我们利用了$V_{ij} = V_{ji}$，通过观察不难发现，这就是之前用“decoupling”得到的Hartree平均场近似项，至多差一个常数。

先前我们选定$\hat{A}_{i}^{H} = c_i^\dagger c_i$，并略去其量子涨落的二阶项；而这里，我们单纯是用变分极值条件再确定使得自由能泛函最小的猜测哈密顿量参数。

同理，对于其他对应Fock、BCS平均场近似的待定参数，我们有：

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

将其带入$\hat{V}_{mf}(\{\lambda_i\})$中，不难发现他们也分别对应Fock、BCS平均场近似。

但从变分法的角度而言，这些待定系数和猜测哈密顿量的项都是独立互不影响的。对猜测哈密顿量加减项，只不过改变了猜测解的形式，增加或减少了变分的参数罢了，所以Hartree、Fock、BCS平均场近似确实可以1:1:1混合，或者两两混合使用，都是满足给定参数的变分极值条件。

但特定的问题中，我们关心特定的序参量，所以把变分参数尽量减少（只用BCS或者Hartree-Fock），以获得尽可能简洁有效的结论。

## Summary

综上，我们通过变分法的严格推导，证明了Hartree，Fock，BCS这些平均场理论确实可以1:1:1混合使用。

首先，我们利用量子力学书中经常出现的decouple method，通过“暴力”略去算符的二阶涨落项，近似得到某一种平均场近似下的平均场哈密顿量。

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

但这种decouple method在使用两种及以上的平均场近似时，容易让人产生重复计算的错觉。

之后我们用变分法的语言，重新描述了一遍平均场近似的变分法本质，即认为系统$\hat{H} = \hat{H}_0 + \hat{V}_{int}$的平衡态和某一平均场哈密顿量$\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i\})$（猜测哈密顿量，含各种待定系数$\{\lambda_i\}$）的平衡态很接近。

选取使得体系的自由能变分最小的待定系数$\{\lambda_i^{mf}\}$，从而用该系数选取下的平均场哈密顿量$\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i^{mf}\})$来近似原（相互作用）系统哈密顿量$\hat{H} = \hat{H}_0 + \hat{V}_{int}$，便是平均场近似。

而通过变分法和Wick定理，我们证明了最佳待定系数$\{\lambda_i^{mf}\}$，恰好和decouple method中选取一阶涨落项的结果一致，即最佳的待定系数$\{\lambda_i^{mf}\}$就是系统的平均场（序参量）。

再回到原来的“Hartree，Fock，BCS这些平均场理论能否1:1:1混合使用”的问题，在使用变分法时，没有规定待定系数的多少，或者说各个待定系数的变分极值条件是相互独立的。

所以，Hartree，Fock，BCS这些平均场理论在decouple method中对应的Density，Exchange，Cooper Channel事实上是独立的，不重复计算的，从而我们证明了：

**Hartree，Fock，BCS这些平均场理论确实可以1:1:1混合使用。**

## Reference

- [1] Bruus, H., & Flensberg, K. (2004). Many-body quantum theory in condensed matter physics: an introduction. Oxford university press.
- [2] Coleman, P. (2015). Introduction to many-body physics. Cambridge University Press.
- [3] Altland, A., & Simons, B. D. (2010). Condensed matter field theory. Cambridge university press.