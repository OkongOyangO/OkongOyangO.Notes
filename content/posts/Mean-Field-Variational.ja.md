---
title: "😤平均場近似と変分法｜Hartree、Fock、BCSは1:1:1で混合できるか？"
date: 2023-03-10T10:00:00+08:00
draft: false
math: true
tags: ["Mean Field Theory", "Hartree-Fock", "BCS", "Variational Method", "Condensed Matter"]
categories: ["Physics Notes"]
---

本稿は平均場近似を紹介するとともに、その変分法的本質を解説する。Hartree、Fock、BCSという三つの平均場近似は一見互いに相容れないdecouple法に見えるが、平均場近似の変分法的本質を利用すれば、これらを実際に1:1:1で混ぜて使うことができる。

<!--more-->

## 平均場近似の核心思想

平均場近似（Mean Field Approximation）は多体相互作用問題を扱うための基本的な道具である。その核心思想は、二体相互作用項における一つの演算子をその平均値で置き換えることにより、相互作用問題を一体問題に帰着させることにある：

$$ c_1^\dagger c_2^\dagger c_3 c_4 \approx \langle c_1^\dagger c_4 \rangle c_2^\dagger c_3 + \langle c_2^\dagger c_3 \rangle c_1^\dagger c_4 - \langle c_1^\dagger c_4 \rangle \langle c_2^\dagger c_3 \rangle $$

これは本質的に、二次の量子揺らぎを一次の揺らぎの積で近似し、二次以上の揺らぎを無視することに他ならない。

## 変分法の視点

平均場近似は変分法の観点から厳密に理解することができる。試行Hartree-Fock状態（Slater行列式）を考える：

$$ |\Phi_{HF}\rangle = \prod_i c_i^\dagger |0\rangle $$

そのエネルギー期待値$\langle \Phi_{HF} | H | \Phi_{HF} \rangle$は厳密な基底状態エネルギーの上界を与える。変分により：

$$ \frac{\delta \langle H \rangle}{\delta |\Phi_{HF}\rangle} = 0 $$

これによりHartree-Fock方程式が導かれる。鍵となるのは：**変分原理に基づく近似（Hartree、Fock、BCS）はすべて同一の変分フレームワークで統一的に扱える**という点である。

## Hartree項：直接相互作用

Hartree項は密度-密度直接相互作用（direct term / Hartree term）に由来する：

$$ \hat{H}_{Hartree} = \sum_{ij} U_{ij} \langle c_i^\dagger c_i \rangle c_j^\dagger c_j $$

ここで$U_{ij}$はクーロン相互作用行列要素である。この項は古典的な静電エネルギーを与え、全エネルギーへの寄与が最も大きい。

## Fock項：交換相互作用

Fock項は交換相互作用（exchange term）に由来する：

$$ \hat{H}_{Fock} = -\sum_{ij} J_{ij} \langle c_i^\dagger c_j \rangle c_j^\dagger c_i $$

ここで$J_{ij}$は交換積分である。負号はFermi粒子の反交換関係に起因する。Fock項は純粋な量子効果であり、古典的な対応物は存在しない。

実空間において、交換相互作用は平行スピンを持つ電子同士を互いに遠ざけ、クーロン反発エネルギーを低下させる傾向がある。

## BCS項：対形成相互作用

BCS平均場は異常平均（anomalous average）を導入する：

$$ \Delta_{ij} = \langle c_{i\downarrow} c_{j\uparrow} \rangle \neq 0 $$

対応するBCS Hamiltonian：

$$ \hat{H}_{BCS} = \sum_{ij} \Delta_{ij} c_{i\uparrow}^\dagger c_{j\downarrow}^\dagger + h.c. $$

BCS基底状態は粒子数が保存しないコヒーレント状態（Bogoliubov変換後の真空状態）であり、統一的に次のように書ける：

$$ |\Phi_{BCS}\rangle = \prod_k (u_k + v_k c_{k\uparrow}^\dagger c_{-k\downarrow}^\dagger) |0\rangle $$

ただし$|u_k|^2 + |v_k|^2 = 1$。

## 三者混合の可能性

変分法の原理に基づけば、Hartree、Fock、BCSの三つのdecouple方式を同一の変分波動関数の中で統一的に扱うことができる。具体的には、変分波動関数を次のように取る：

$$ |\Phi\rangle = \mathcal{U}_{BCS} \mathcal{U}_{HF} |0\rangle $$

ここで$\mathcal{U}_{HF}$はHartree-Fock基底状態（Slater行列式）を生成するユニタリ変換、$\mathcal{U}_{BCS}$はBogoliubov変換である。

**重要な結論：三重のdecoupleの間には矛盾は存在しない**。なぜなら変分原理によりエネルギーはパラメータの増加に伴って単調に減少することが保証されるからである。decouple方式を一つ追加するごとに変分パラメータ空間が拡大し、得られる基底状態エネルギーはより正確になる（少なくとも悪化することはない）。

実際の数値計算において、Hartree-Fock-Bogoliubov法（HFB）はまさに三者を統合したフレームワークである。原子核物理、超低温原子気体、超伝導理論など幅広い分野で応用されている。

## 具体的な操作手順

Fermi-Hubbard模型を例に取る：

$$ H = -t \sum_{\langle ij\rangle, \sigma} c_{i\sigma}^\dagger c_{j\sigma} + U \sum_i n_{i\uparrow} n_{i\downarrow} $$

相互作用項を完全にdecoupleする：

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

これらの秩序変数は数値的に自己無撞着に解くことができる。

## まとめ

平均場近似の変分法的本質は、Hartree、Fock、BCSの三つのdecouple方式の統一性を明らかにする。変分法の観点からすれば、三者は自由に混ぜて使うことができる——decouple方式を一つ追加することは変分パラメータを一つ増やすことに他ならず、常により正確な（少なくとも悪化しない）基底状態エネルギー推定を与える。
