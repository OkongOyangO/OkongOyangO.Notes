---
title: "😤平均场近似与变分法｜Hartree, Fock, BCS能1:1:1混用吗？"
date: 2026-06-30T17:00:00+08:00
draft: false
math: true
tags: ["Mean Field Theory", "Hartree-Fock", "BCS", "Variational Method", "Condensed Matter"]
categories: ["Physics Notes"]
---

本文旨在介绍平均场近似，同时阐述其变分法本质。Hartree、Fock、BCS这三个平均场近似，看似是互不相容的decouple方法，但利用平均场近似的变分法本质，我们发现它们确实可以1:1:1混着用。

<!--more-->

## 平均场近似的核心思想

平均场近似（Mean Field Approximation）是处理多体相互作用问题的基本工具。其核心思想是将两体相互作用项中一个算符用其平均值代替，从而将相互作用问题化为单体问题：

$$ c_1^\dagger c_2^\dagger c_3 c_4 \approx \langle c_1^\dagger c_4 \rangle c_2^\dagger c_3 + \langle c_2^\dagger c_3 \rangle c_1^\dagger c_4 - \langle c_1^\dagger c_4 \rangle \langle c_2^\dagger c_3 \rangle $$

这本质上是将二阶量子涨落用一阶涨落的乘积近似，忽略了二阶及以上的涨落。

## 变分法视角

平均场近似可以从变分法的角度严格理解。考虑一个试探的Hartree-Fock态（Slater行列式）：

$$ |\Phi_{HF}\rangle = \prod_i c_i^\dagger |0\rangle $$

其能量期望值$\langle \Phi_{HF} | H | \Phi_{HF} \rangle$给出了严格基态能量的上界。通过变分：

$$ \frac{\delta \langle H \rangle}{\delta |\Phi_{HF}\rangle} = 0 $$

即可得到Hartree-Fock方程。关键在于：**任何基于变分原理的近似（Hartree、Fock、BCS）都可以在同一变分框架下统一处理**。

## Hartree项：直接相互作用

Hartree项来自密度-密度直接相互作用（direct term / Hartree term）：

$$ \hat{H}_{Hartree} = \sum_{ij} U_{ij} \langle c_i^\dagger c_i \rangle c_j^\dagger c_j $$

其中$U_{ij}$为库仑相互作用矩阵元。这一项给出经典的静电能，对总能量贡献最大。

## Fock项：交换相互作用

Fock项来自交换相互作用（exchange term）：

$$ \hat{H}_{Fock} = -\sum_{ij} J_{ij} \langle c_i^\dagger c_j \rangle c_j^\dagger c_i $$

其中$J_{ij}$为交换积分。负号来源于Fermi子的反对易关系。Fock项是纯粹的量子效应，无经典对应。

在实空间中，交换相互作用倾向于使平行自旋的电子彼此远离，降低库仑排斥能。

## BCS项：配对相互作用

BCS平均场引入了反常平均值（anomalous average）：

$$ \Delta_{ij} = \langle c_{i\downarrow} c_{j\uparrow} \rangle \neq 0 $$

对应的BCS Hamiltonian：

$$ \hat{H}_{BCS} = \sum_{ij} \Delta_{ij} c_{i\uparrow}^\dagger c_{j\downarrow}^\dagger + h.c. $$

BCS基态是粒子数不守恒的相干态（Bogoliubov变换后的真空态），可以统一写为：

$$ |\Phi_{BCS}\rangle = \prod_k (u_k + v_k c_{k\uparrow}^\dagger c_{-k\downarrow}^\dagger) |0\rangle $$

其中$|u_k|^2 + |v_k|^2 = 1$。

## 三者混用的可能性

从变分法原理出发，我们可以将Hartree、Fock、BCS三种decouple方案在同一个变分波函数中统一处理。具体而言，取变分波函数为：

$$ |\Phi\rangle = \mathcal{U}_{BCS} \mathcal{U}_{HF} |0\rangle $$

其中$\mathcal{U}_{HF}$为生成Hartree-Fock基态（Slater行列式）的幺正变换，$\mathcal{U}_{BCS}$为Bogoliubov变换。

关键结论：**三重decouple之间不存在矛盾**，因为变分原理保证了能量随参数单调下降。每多考虑一种decouple方案，变分参数空间扩大，得到的基态能量就更低（或至少不升高）。

在实际数值计算中，Hartree-Fock-Bogoliubov方法（HFB）正是三者统一的框架。广泛应用于核物理、超冷原子气体、超导理论等领域。

## 具体操作步骤

以Fermi-Hubbard模型为例：

$$ H = -t \sum_{\langle ij\rangle, \sigma} c_{i\sigma}^\dagger c_{j\sigma} + U \sum_i n_{i\uparrow} n_{i\downarrow} $$

对相互作用项做完全decouple：

$$
n_{i\uparrow} n_{i\downarrow} \approx 
\langle n_{i\uparrow} \rangle n_{i\downarrow} + n_{i\uparrow} \langle n_{i\downarrow} \rangle - \langle n_{i\uparrow} \rangle \langle n_{i\downarrow} \rangle \quad (\text{Hartree})
$$
$$
- \langle c_{i\uparrow}^\dagger c_{i\downarrow} \rangle c_{i\downarrow}^\dagger c_{i\uparrow} - c_{i\uparrow}^\dagger c_{i\downarrow} \langle c_{i\downarrow}^\dagger c_{i\uparrow} \rangle + \langle c_{i\uparrow}^\dagger c_{i\downarrow} \rangle \langle c_{i\downarrow}^\dagger c_{i\uparrow} \rangle \quad (\text{Fock})
$$
$$
+ \langle c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \rangle c_{i\downarrow} c_{i\uparrow} + c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \langle c_{i\downarrow} c_{i\uparrow} \rangle - \langle c_{i\uparrow}^\dagger c_{i\downarrow}^\dagger \rangle \langle c_{i\downarrow} c_{i\uparrow} \rangle \quad (\text{BCS})
$$

数值上可以自洽求解这些序参量。

## 总结

平均场近似的变分法本质揭示了Hartree、Fock、BCS三种decouple方案的统一性。从变分法角度出发，三者可以自由混用——多一种decouple就多一个变分参数，总能给出更精确（或至少不更差）的基态能量估计。
