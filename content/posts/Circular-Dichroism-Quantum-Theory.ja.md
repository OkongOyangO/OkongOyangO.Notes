---
title: "😵円二色性（Circular Dichroism）の量子理論"
date: 2026-06-30T12:00:00+08:00
draft: false
math: true
tags: ["Circular Dichroism", "Chirality", "Quantum Theory", "Multipole Expansion", "Condensed Matter"]
categories: ["Physics Notes"]
---

円二色性（Circular Dichroism, CD）は、分子のキラリティーを調べるための一般的な実験手法である。CDでは、物質による左円偏光と右円偏光の吸収の差を測定し、その差を物質のキラリティーを反映する指標として用いる。円偏光は空間中で螺旋状の電場形状を持ち、本質的にキラリティーを有しており、左・右円偏光が異なるキラリティーの物質と相互作用する際に違いが生じると考えられる。

<!--more-->

以前のノートでは、光と量子系の相互作用の多極展開理論を解説した。ここでは電磁波の形を左・右旋円偏光に変えて差を取るだけで、試料のCDスペクトルが得られる。以前のノートでの多極展開理論は摂動展開に基づいているため、電子の波動関数スケール$r$が光の波長$\lambda$よりも十分小さい場合に成立する。

## CDの量子理論

一般的に見られるCDの量子理論では、採用されるHamiltonianは以下の通りである：

$$ \hat{H} = \hat{H}_0 - Q \hat{\mathbf{r}} \cdot \mathbf{E} - \hat{\mathbf{m}}\cdot \mathbf{B} $$

ここでは電磁場の空間依存性（spatial dependence）を無視しており、これは多極展開理論の最低次の場合に相当する。実際には、磁気ベクトルポテンシャル$\mathbf{A}$から出発し、磁気双極子と同程度の電四極項を加えるべきである。しかし、後で示すように、ランダム配向（randomly oriented）の系では電四極の寄与は無視できる。

ここでは厳密な導出を行うため、磁気ベクトルポテンシャル（横場ゲージ）から電磁場を導入し、厳密な最低次近似結果を与える。上記のHamiltonianと磁気ベクトルポテンシャル（横場ゲージ）から導入したHamiltonianの間にはゲージ変換の差がある。詳細な導出は以前のノートを参照されたい。

横場ゲージの磁気ベクトルポテンシャルによる電磁場導入のHamiltonianは以下の通りである：

$$ \hat{H} = \frac{1}{2m} (\hat{\mathbf{p}} - Q \mathbf{A}(\hat{\mathbf{r}},t) )^2 + Q \phi(\hat{\mathbf{r}},t) + V(\hat{\mathbf{r}}) -\frac{Q}{m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t) $$

ただし電場は：

$$ \mathbf{E}(\mathbf{r},t) = \frac{E_0}{2}e^{-iqz} e^{i \omega t} \mathbf{e}_E + c.c. = E_0(z) e^{i \omega t} \mathbf{e}_E + c.c. = \mathbf{E}(\mathbf{r}) e^{i \omega t} + c.c. $$

左旋・右旋円偏光については：

$$ \mathbf{e}_E^{\pm} = \frac{1}{\sqrt{2}}(1,\pm i, 0) $$

磁場部分：

$$ \mathbf{B}(\mathbf{r},t) = \frac{E_0}{2\omega} (\mathbf{k} \times \mathbf{e}_E) e^{-iqz} e^{i \omega t} + c.c. = \mathbf{B}(\mathbf{r}) e^{i \omega t} + c.c. $$

ここで$\mathbf{k} = q \hat{z}$であることに注意。

これに対応して、$\mathbf{e}_B^{\pm}$も求められる：

$$ \mathbf{e}_B^{\pm} = \frac{1}{\sqrt{2}}(\mp i, 1, 0) $$

一般的な実験条件下での入射光について、上記の左旋・右旋円偏光をすべて式に代入し、時間依存摂動論に基づくフェルミの黄金律を用いて左旋光の結果を差し引くことで、一般的なCDスペクトル（差スペクトル）が得られる。

ここでは一般的なCDスペクトルの計算は行わず、最も一般的な多極展開の枠組みにおいてCDスペクトルの計算に必要な項を示すに留める。また、ここでは回転波近似（Rotating Wave Approximation）は採用せず、以下で計算の必要に応じて項ごとに判断する。同時に、周波数総和を取る際には光場の正周波数部分と負周波数部分の両方の寄与を考慮する必要がある。

## 多極展開とCD

CDスペクトルについては、左旋・右旋光場の吸収スペクトルをそれぞれ計算してから差し引く。CDスペクトル$\Delta A(\omega)$の計算式は以下の通りである：

$$ \Delta A(\omega) = A_+(\omega) - A_-(\omega) $$

フェルミの黄金律によれば、単一光子吸収に対応する吸収スペクトルは以下の対称形式で書ける：

$$
A(\omega) = \frac{\pi Q^2}{\hbar^2} \sum_{i,f} P_i |\langle f | \hat{H}_{int} | i \rangle|^2 \delta(\omega_{fi} - \omega)
$$

ここで$\hat{H}_{int}$は光と物質の相互作用である。上記の横場ゲージ磁気ベクトルポテンシャルのHamiltonianを代入すると、光と物質の相互作用の最低次項が得られる：

$$
\hat{H}_{int} = - \frac{Q}{m} \mathbf{A}(\hat{\mathbf{r}},t) \cdot \hat{\mathbf{p}} - \frac{Q}{2m} \hat{\mathbf{S}} \cdot \mathbf{B}(\hat{\mathbf{r}},t)
$$

上式は次のように書き換えられる：

$$
\hat{H}_{int} = \frac{iQE_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} e^{-iq\hat{z}} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c.
$$

$r \ll \lambda$の前提のもとで、$e^{-iq\hat{z}}$を展開できる：

$$
e^{-iq\hat{z}} = 1 - iq\hat{z} - \frac{1}{2}(q\hat{z})^2 + \cdots
$$

ゼロ次項（電気双極子近似）：

$$ \hat{H}_{int}^{(0)} = \frac{iQE_0}{2m\omega} (\hat{\mathbf{p}} \cdot \mathbf{e}_E) - \frac{Q E_0}{2m\omega} (\hat{\mathbf{S}} \cdot \mathbf{e}_B) + h.c. $$

以下の交換関係を利用する：

$$ \hat{\mathbf{p}} = \frac{im}{\hbar}[\hat{H}_0, \hat{\mathbf{r}}] $$

これにより電気双極子の等価形式が得られる：

$$ \langle f | \hat{\mathbf{p}} | i \rangle = \frac{im}{\hbar} (E_f - E_i) \langle f | \hat{\mathbf{r}} | i \rangle $$

したがって、ゼロ次項は一般的な電気双極子形式に書き換えられる。

CDスペクトルにおいて、電気双極子項は左旋・右旋光に対して完全に一致するため、差スペクトルでは打ち消される。最初に寄与するのは電気双極子（E1）-磁気双極子（M1）交差項、およびE1-電四極（E2）交差項である。厳密な計算の結果、最終的なCDスペクトルの式は回転波近似のもとで次のようになる：

$$
\Delta A(\omega) \propto \sum_{i,f} P_i \left[ \langle i | \hat{\mathbf{m}} | f \rangle \cdot \langle f | \hat{\mathbf{r}} | i \rangle \times \mathbf{k} + \frac{i\omega}{c} \langle i | \hat{\mathbf{r}} | f \rangle \cdot \mathbf{Q} \cdot (\hat{\mathbf{k}} \times \langle f | \hat{\mathbf{r}} | i \rangle) \right] \delta(\omega_{fi} - \omega)
$$

ランダム配向（randomly oriented）の系では、電四極項は平均してゼロとなり、磁気双極子項のみがCD信号に寄与する。これが、一般的な教科書でE1-M1交差項のみをCDの起源として挙げる理由である。

## まとめ

本ノートでは、光-物質相互作用の多極展開の枠組みを通じて、円二色性（CD）の量子理論を厳密に導出した。CD信号は左旋・右旋円偏光の吸収差に由来し、その主要な寄与は電気双極子-磁気双極子（E1-M1）交差項である。この理論は、キラル分子の分光学特性評価の微視的基礎を提供する。
