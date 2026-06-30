---
title: "😌ハミルトニアンにTRSはあるのか？時間反転対称性の実践ガイド"
date: 2021-11-17T10:00:00+08:00
draft: false
math: true
tags: ["Time-Reversal Symmetry", "Topological Insulator", "Kramers Degeneracy", "Condensed Matter"]
categories: ["Physics Notes"]
---

時間反転対称性（TRS）はトポロジカル絶縁体の学習においてあまりにも一般的であるため、次のような状況が頻繁に生じる：最初のページでは結論が自明に思えても、次のページではその結論がどこから来たのか分からなくなる。本稿は時間反転対称性の量子力学およびバンド理論における具体的な現れ方を体系的に整理する。

<!--more-->

## スピンなし粒子のTRS

スピンレス系における時間反転操作$\Theta$は複素共役として作用する：

$$ \Theta = K $$

ここで$K$は複素共役演算子である。スピンレス粒子のハミルトニアンについて、TRSは次を要求する：

$$ \Theta H \Theta^{-1} = H \quad \Leftrightarrow \quad H^* = H $$

すなわちハミルトニアンの行列要素はすべて実数である。Bloch Hamiltonianについては、これは次を意味する：

$$ H(-\mathbf{k}) = H^*(\mathbf{k}) $$

## スピンあり粒子のTRS

スピン$1/2$粒子については、時間反転演算子は：

$$ \Theta = -i \sigma_y K $$

ここで$\sigma_y$はPauli行列である。重要な性質：

$$ \Theta^2 = -1 $$

この性質は有名な**Kramers縮退**を導く：TRSの下で、各固有状態は少なくとも二重に縮退する。

証明：$|\psi\rangle$が$H$の固有状態ならば、$\Theta|\psi\rangle$も$H$の固有状態であり、$|\psi\rangle$と直交する：

$$ \langle \psi | \Theta \psi \rangle = \langle \Theta^2 \psi | \Theta \psi \rangle^* = -\langle \psi | \Theta \psi \rangle^* = 0 $$

## 固体バンド理論におけるTRS

Blochバンド理論において、TRSは次を要求する：

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

これはバンドに関する$k=0$での鏡映対称性を与える：$E_n(\mathbf{k}) = E_n(-\mathbf{k})$。

### 時間反転不変運動量（TRIM）

BZ内で$-\mathbf{k} = \mathbf{k} + \mathbf{G}$を満たす運動量点をTRIM（Time-Reversal Invariant Momentum）と呼ぶ。2D正方格子には4個、3Dには8個のTRIMが存在する。これらの点上では：

$$ H(\Gamma_i) = \Theta H(\Gamma_i) \Theta^{-1} $$

が成り立ち、Kramers縮退が保証される。

### ブリルアンゾーンにおけるBerry曲率の制約

TRSはBerry曲率に制約を課す：

$$ F(-\mathbf{k}) = -F(\mathbf{k}) $$

これはTRIMにおいてBerry曲率が0となることを意味する（$F(\Gamma_i) = -F(\Gamma_i)$より）。したがってTRS系のChern数は必ず0となる——TRS系はChern絶縁体ではあり得ない。

## TRSハミルトニアンの構築方法

あるハミルトニアンがTRSを持つかどうかを判断するには、以下の手順に従う：

1. **時間反転演算子の形式を書き下す**：系がスピンを含むかどうかに応じて$\Theta$を決定する

2. **Bloch HamiltonianにTRS条件を課す**：

$$ \Theta H(\mathbf{k}) \Theta^{-1} = H(-\mathbf{k}) $$

3. **Pauli行列形式に展開する**。二バンド系を例に取る：

$$ H(\mathbf{k}) = d_0(\mathbf{k}) \sigma_0 + \mathbf{d}(\mathbf{k}) \cdot \boldsymbol{\sigma} $$

TRSは$d_i(\mathbf{k})$の対称性に制約を課す。スピンレス系（$\Theta = K$）の場合：

$$ \sigma_x \sigma_0 \sigma_x = \sigma_0 = \sigma_0^* $$
$$ \sigma_x \sigma_x \sigma_x = \sigma_x = \sigma_x^* $$
$$ \sigma_x \sigma_y \sigma_x = -\sigma_y = \sigma_y^* $$
$$ \sigma_x \sigma_z \sigma_x = -\sigma_z $$

したがって$d_y(\mathbf{k})$は0でなければならず、$d_x, d_z$は偶関数となる。

4. **他の対称性と組み合わせる**。例えば$C_{2z}\mathcal{T}$結合対称性は非相反輸送においても重要な応用を持つ。

## スピン-軌道結合におけるTRS

スピン-軌道結合がある系では、TRSはバンドのスピン縮退として現れる。DresselhausおよびRashbaスピン-軌道結合はいずれもTRSを保つ（これらは構造反転非対称性に起因し、TRSを破らない）。

TRSと反転対称性（IS）が共存する場合、各k点の各バンドは二重に縮退する（スピン縮退）。これは$\mathcal{P}\Theta$結合対称性（$\mathcal{P}\Theta^2 = -1$）が局所Kramers縮退（local Kramers degeneracy）を保証するためである。

## まとめ

TRSはトポロジカル分類の三つの基本対称性の一つである（PHS、CSと並んで）。ある系がTRSを持つかどうか、そしてTRSがもたらすバンドの制約（Kramers縮退、Berry曲率が奇関数であること、TRIMにおける縮退）を認識することは、トポロジカル絶縁体やその他のSPT相を学ぶ上での基礎となる。
