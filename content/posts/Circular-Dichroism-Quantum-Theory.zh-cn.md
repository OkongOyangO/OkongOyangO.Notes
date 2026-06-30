---
title: "😵圆二象性（Circular Dichroism）的量子理论"
date: 2022-08-31T10:00:00+08:00
draft: false
math: true
tags: ["Circular Dichroism", "Chirality", "Quantum Theory", "Multipole Expansion", "Condensed Matter"]
categories: ["Physics Notes"]
---

圆二象性（Circular Dichroism, CD）是研究分子手性的常用实验手段。CD测量物质对左右圆偏振光吸收的差值，作为反映物质手性的依据。圆偏振光在空间中的几何形状是螺旋型的电场，很自然地具有手性，可以想象左、右圆偏振光与不同手性的物质的相互作用也有区别。

<!--more-->

之前的note解释了光与量子系统的相互作用的多极展开理论，此处只要将电磁波的形式改成左、右旋圆偏振光并求差即可得到样品的CD谱。由于之前note的多极展开理论为微扰展开，故在电子波函数尺度$r$远小于光波长$\lambda$的时候成立。

## CD的量子理论

一般看到的CD量子理论中，采用的Hamiltonian为

$$ \hat{H} = \hat{H}_0 - Q \hat{\mathbf{r}} \cdot \mathbf{E} - \hat{\mathbf{m}}\cdot \mathbf{B} $$

此处忽略了电磁场的spatial dependence，是多极展开理论的最低阶情形。事实上，应该从磁矢势$\mathbf{A}$出发，并加入与磁偶极同量级的电四极项，但之后会证明，在randomly oriented的系统中，电四极的贡献可以被忽略。

此处为严格推导，我们从磁矢势（横场规范）引入电磁场，从而给出严格的最低阶近似结果。上述Hamiltonian与从磁矢势（横场规范）引入电磁场的Hamiltonian之间差一个规范变换，具体推导可以参考之前的note。

横场规范磁矢势引入电磁场的Hamiltonian为：

$$ \hat{H} = \frac{1}{2m} (\hat{\mathbf{p}} - Q \mathbf{A}(\hat{\mathbf{r}},t) )^2 + Q \phi(\hat{\mathbf{r}},t) + V(\hat{\mathbf{r}}) -\frac{Q}{m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t) $$

其中电场：

$$ \mathbf{E}(\mathbf{r},t) = \frac{E_0}{2}e^{-iqz} e^{i \omega t} \mathbf{e}_E + c.c. = E_0(z) e^{i \omega t} \mathbf{e}_E + c.c. = \mathbf{E}(\mathbf{r}) e^{i \omega t} + c.c. $$

对于左旋、右旋圆偏振光：

$$ \mathbf{e}_E^{\pm} = \frac{1}{\sqrt{2}}(1,\pm i, 0) $$

磁场部分：

$$ \mathbf{B}(\mathbf{r},t) = \frac{E_0}{2\omega} (\mathbf{k} \times \mathbf{e}_E) e^{-iqz} e^{i \omega t} + c.c. = \mathbf{B}(\mathbf{r}) e^{i \omega t} + c.c. $$

注意$\mathbf{k} = q \hat{z}$。

相应地，可以求出$\mathbf{e}_B^{\pm}$：

$$ \mathbf{e}_B^{\pm} = \frac{1}{\sqrt{2}}(\mp i, 1, 0) $$

对于一般的实验条件下的入射光，将所有上述左旋、右旋圆偏振光带入式子中，根据含时微扰论做费米黄金规则并且减去左旋光的结果，即可得到一般的CD谱（差谱）。

此处不给出一般CD谱的计算，仅在最一般的多极展开框架下给出求CD谱需要计算的项。同样，此处不取旋波近似（Rotating Wave Approximation），而是在下文根据计算需要逐项判断。同时频率求和时，需要同时考虑光场正频和负频部分的贡献。

## 多极展开与CD

对于CD谱，我们分别计算左、右旋光场的吸收谱再相减。由于CD谱$\Delta A(\omega)$的计算公式如下：

$$ \Delta A(\omega) = A_+(\omega) - A_-(\omega) $$

根据费米黄金规则，单光子吸收对应的吸收谱可以写成以下对称形式：

$$
A(\omega) = \frac{\pi Q^2}{\hbar^2} \sum_{i,f} P_i |\langle f | \hat{H}_{int} | i \rangle|^2 \delta(\omega_{fi} - \omega)
$$

其中$\hat{H}_{int}$是光与物质相互作用。带入上面的横场规范磁矢势Hamiltonian，我们可以得到光与物质相互作用的最低阶项：

$$
\hat{H}_{int} = - \frac{Q}{m} \mathbf{A}(\hat{\mathbf{r}},t) \cdot \hat{\mathbf{p}} - \frac{Q}{2m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t)
$$

上式可改写为：

$$
\hat{H}_{int} = \frac{iQE_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c.
$$

在$r \ll \lambda$的前提下，可以将$e^{-iq\hat{z}}$展开：

$$
e^{-iq\hat{z}} = 1 - iq\hat{z} - \frac{1}{2}(q\hat{z})^2 + \cdots
$$

零阶项（电偶极近似）：

$$ \hat{H}_{int}^{(0)} = \frac{iQE_0}{2m\omega} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c. $$

利用以下对易关系：

$$ \hat{\mathbf{p}} = \frac{im}{\hbar}[\hat{H}_0, \hat{\mathbf{r}}] $$

可得电偶极的等价形式：

$$ \langle f | \hat{\mathbf{p}} | i \rangle = \frac{im}{\hbar} (E_f - E_i) \langle f | \hat{\mathbf{r}} | i \rangle $$

因此零阶项可改写为常见的电偶极形式。

对于CD谱，电偶极项对于左、右旋光的贡献完全一致，因而在差谱中扣去。第一项有贡献的为电偶极(E1)-磁偶极(M1)交叉项，以及E1-电四极(E2)交叉项。经过严格计算，最终CD谱的表达式在旋波近似下为：

$$
\Delta A(\omega) \propto \sum_{i,f} P_i \left[ \langle i | \hat{\mathbf{m}} | f \rangle \cdot \langle f | \hat{\mathbf{r}} | i \rangle \times \mathbf{k} + \frac{i\omega}{c} \langle i | \hat{\mathbf{r}} | f \rangle \cdot \mathbf{Q} \cdot (\hat{\mathbf{k}} \times \langle f | \hat{\mathbf{r}} | i \rangle) \right] \delta(\omega_{fi} - \omega)
$$

在randomly oriented系统中，电四极项平均为0，仅磁偶极项贡献CD信号。这就是为何一般教科书只提E1-M1交叉项作为CD来源。

## 总结

本note通过光-物质相互作用的多极展开框架，严格推导了圆二象性（CD）的量子理论。CD信号来自左、右旋圆偏振光吸收的差值，其主导贡献为电偶极-磁偶极（E1-M1）交叉项。该理论为理解手性分子的光谱表征提供了微观基础。
