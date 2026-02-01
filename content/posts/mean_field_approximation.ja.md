---
title: "🤫平均場近似と変分法｜Hartree, Fock, BCSは1:1:1で混ぜて使えるか？"
date: 2023-03-11T22:30:00-05:00
draft: false
math: true
tags: ["Condensed Matter", "Mean Field"]
categories: ["Physics Notes"]
---

本文は平均場近似を紹介すると同時に、その変分法的本質を説明することを目的としています。

Hartree, Fock, BCSといった個々の平均場近似は、一見すると互いに相容れないdecouple（分離）手法のように見えますが、平均場近似の変分法的本質を利用することで、これらは実際に1:1:1で混ぜて使用できることがわかります。

<!--more-->

## Preface

本文のインスピレーションは、まずクラスメートの[@ykli](https://www.zhihu.com/people/li-yong-kang-9-34)との議論から得られました。導出過程で多大な助けをくれた[@ykli](https://www.zhihu.com/people/li-yong-kang-9-34)に感謝します。

この問題はPhysics Stack Exchangeのウェブサイトでも言及されており（"Multi-channel Mean Field Theory"と呼ばれています）、参考のためにリンクを貼っておきます：

https://physics.stackexchange.com/questions/742905/multi-channel-mean-field-theory

また、[@阿兰那行](https://www.zhihu.com/people/deng-wwzz)先輩の「物理界隈の隠語」に関する回答からもかなりのインスピレーションを得ました。興味のある読者は以下をご覧ください：

https://www.zhihu.com/question/410499049/answer/2442413803

## Introduction

相互作用系において、システムの完全なハミルトニアンは以下の通りです：

$$
\begin{aligned}
\hat{H} = \hat{H}_0 + \hat{V}_{int}
\end{aligned}
$$

ここで、$\hat{H}_0 \sim \sum c^\dagger c$ はフェルミ粒子生成消滅演算子の二次形式部分であり、独立した自由粒子として比較的容易に扱えます。

一方、$\hat{V}_{int} \sim \sum c^\dagger c^\dagger c c$ は相互作用部分です。

相互作用の存在により、システムの基底状態波動関数や平衡状態密度行列を求めることは難しく、相互作用系の様々な情報を計算することも困難になります。そのため、我々はしばしば様々な近似手法を用いて処理します。

平均場近似はそのような手法の一つです。厳密に解くことができる平均場近似ハミルトニアンを取り上げます：

$$
\begin{aligned}
\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}
\end{aligned}
$$

$\hat{V}_{mf}$ もまた二次形式にすることで、厳密解を求めることが容易になります。そして、この平均場近似ハミルトニアンの解を用いて、システムの様々な性質を近似的に導き出すことができます。

## Mean Field Theory by Decoupling

しかし、近似は適当に選べばよいわけではなく、ある程度のテクニックが必要です。

量子力学の教科書では、平均場近似とは演算子の量子揺らぎ部分を無視すること、すなわちDecoupling Method（分離法）であると教えられます：

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

ここで、平均場（mean field）部分は演算子揺らぎ$\delta A$の0次と1次の部分を保持し、量子揺らぎ（quantum fluctuation）は演算子揺らぎ$\delta A$の2次の部分を含んでいます。

したがって、量子揺らぎが小さい場合、平均場近似は比較的正確であることは容易に理解できます。

二体相互作用$\hat{V}_{int}$について：

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

これを$\hat{A}^\dagger\hat{A}$（の和）の形式に分解するには3つの方法があります：

+ Density Channel (Hartree)：$\hat{A}_{i}^{H} = c_i^\dagger c_i$
+ Exchange Channel (Fock)：$\hat{A}_{ij}^{F} = c_i^\dagger c_j$
+ Cooper Channer (BCS)：$\hat{A}_{ij}^{BCS} = c_i c_j$

Density Channelを例にとると、Hartree平均場のDecoupling過程は以下のようになります：

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

Fock平均場のDecouplingについては：

$$
\begin{aligned}
    & \hat{V}_{int} = - \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{F} }^\dagger \hat{A}_{ij}^{F} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx -\frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{F}}^\dagger\rangle  \hat{A}_{ij}^{F} +  {\hat{A}_{ij}^{F}}^\dagger \langle \hat{A}_{ij}^{F}\rangle - \langle {\hat{A}_{ij}^{F}}^\dagger\rangle \langle {\hat{A}_{ij}^{F}}\rangle \right)\\
    & \equiv \hat{V}_{F}
\end{aligned}
$$

BCS平均場のDecouplingについては：

$$
\begin{aligned}
    & \hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} {\hat{A}_{ij}^{BCS} }^\dagger \hat{A}_{ij}^{BCS} \ +\underbrace{\ const}_{\text{ignore it}} \\
    & \approx \frac{1}{2} \sum_{ij}V_{ij} \left(\langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle  \hat{A}_{ij}^{BCS} +  {\hat{A}_{ij}^{BCS}}^\dagger \langle \hat{A}_{ij}^{BCS}\rangle - \langle {\hat{A}_{ij}^{BCS}}^\dagger\rangle \langle {\hat{A}_{ij}^{BCS}}\rangle \right)\\
    & \equiv \hat{V}_{BCS}
\end{aligned}
$$

## Problem of Decoupling

しかし、これでは二体相互作用に対して、Hartree、Fock、あるいはBCSのいずれか一つの近似しか行えないように思えます。

しかし実際には、よく耳にする「Hartree-Fock平均場近似」は2つの近似を使用しているようです。

$$
\begin{aligned}
\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

では、このようにすることによって重複計算（double counting）の問題は生じないのでしょうか？

それとも、$\hat{V}_{int}$を$\frac{\hat{V}_{int}}{2}$と$\frac{\hat{V}_{int}}{2}$に分割して使用するのでしょうか？

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{2} + \frac{\hat{V}_{int}}{2} \approx \frac{\hat{V}_{H}}{2} + \frac{\hat{V}_{F}}{2}
\end{aligned}
$$

あるいは$\frac{\hat{V}_{int}}{3}$と$\frac{2\hat{V}_{int}}{3}$に分割するのでしょうか？

$$
\begin{aligned}
\hat{V}_{int} = \frac{\hat{V}_{int}}{3} + \frac{2\hat{V}_{int}}{3} \approx \frac{\hat{V}_{H}}{3} + \frac{2\hat{V}_{F}}{3}
\end{aligned}
$$

「Hartree-Fock平均場近似」があるなら、なぜ「Hartree-Fock-BCS平均場近似」はないのでしょうか？前述の重複計算の問題や、いわゆる分割の問題はどのように解決されるのでしょうか？

実際には、$\hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}$が正しい方法なのですが、Decoupling Methodを用いてHartree-Fock平均場近似を理解しようとすると、どうしても重複計算のような感覚を与えてしまいます：

$$
\begin{aligned}
\hat{V}_{int} + \hat{V}_{int} \approx \hat{V}_{H} + \hat{V}_{F}
\end{aligned}
$$

これはDecouplingの表現が不正確であることに起因します。次に、平均場近似が非摂動的な方法として、本質的には「解を推測して最適化する」変分法であることを説明します。

その後、変分法から出発して、異なるdecoupling方法（Hartree、Fock、BCS）の選択は実際には互いに影響せず、単に推測解に新たな独立したパラメータを追加するだけであり、いわゆる重複計算の問題は引き起こさないことを証明します。

## Variational Method for Finite Temperature

私たちはすでにゼロ温度での変分法には慣れ親しんでいます。

ゼロ温度系では、ハミルトニアンの基底状態波動関数$|\Psi(\lambda)\rangle$を「推測」するためによく変分法を用います。ここで$\lambda$は「推測される基底状態波動関数」を調節するパラメータです。パラメータを調節し、基底状態エネルギー汎関数：

$$
\begin{aligned}
E[\Psi(\lambda)] = \frac{\langle \Psi(\lambda) | \hat{H} | \Psi(\lambda) \rangle}{\langle \Psi(\lambda) | \Psi(\lambda) \rangle}
\end{aligned}
$$

を最小にすることで、$|\Psi(\lambda)\rangle$が基底状態波動関数に非常に近いと言うことができます。その後、この推測解を用いてシステムの基底状態（ゼロ温度）の様々な性質を計算します。

同様に、変分原理は有限温度系にも適用できます。「推測される基底状態波動関数」を「推測される平衡状態密度行列」に変えるだけです。

ここでは正準集団を用いて導出を行いますが、導出の便宜上、単位系を$k_B = 1$とします。

有限温度において、平衡状態密度行列は以下の通りです：

$$
\begin{aligned}
\hat{\rho}_{eq} = \frac{e^{-\beta \hat{H}}}{\operatorname{Tr} (e^{-\beta \hat{H}})}
\end{aligned}
$$

「推測される平衡状態密度行列」は何らかの特定の形式を持つ必要があります。システムの密度行列が、ある補助ハミルトニアン$\hat{H}_{mf}(\lambda)$の平衡状態密度行列であると仮定します：

$$
\begin{aligned}
\hat{\rho}_{mf}(\lambda) \equiv \hat{\rho}_{eq} [\hat{H}_{mf}(\lambda)] \equiv \frac{e^{-\beta \hat{H}_{mf}(\lambda)}}{\operatorname{Tr} (e^{-\beta \hat{H}_{mf}(\lambda)})}
\end{aligned}
$$

ここで$\lambda$はハミルトニアン$\hat{H}_0$（ひいては「推測される平衡状態密度行列」）を調節するパラメータ（例えば、平均場の強さや秩序変数など）です。

ここで"mf"という添字を使用していますが、これは平均場近似がここの「推測される平衡状態密度関数」を提供する「補助ハミルトニアン」を「平均場近似ハミルトニアン」とすることを示唆しています。しかし実際には、一般的な変分法において、「補助ハミルトニアン」はどのような形式でも構いませんし、密度行列も自由に選ぶことができ、必ずしも何らかのハミルトニアンの平衡状態密度行列である必要はありません。

このとき、変分極値条件も「エネルギー汎関数を最小にする」ことから「自由エネルギー汎関数を最小にする」ことへと拡張されます。

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda)] & = \langle \hat{H} \rangle_{\rho_{mf}(\lambda)} - TS \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{H}) + T \operatorname{Tr} (\hat{\rho}_{mf}(\lambda) \ln \hat{\rho}_{mf}(\lambda) )
\end{aligned}
$$

注意すべき点として、ここでの$\hat{H}$は我々の推測ハミルトニアン$\hat{H}_{mf}(\lambda)$ではなく、システムの完全なハミルトニアンです。

実際、平均場近似では、平均場近似後のハミルトニアンに対応する平衡状態密度行列を「推測される平衡状態密度行列」として使用します。このために、平均場近似を直接行い、量子揺らぎを無視することが、ちょうど自由エネルギー汎関数の変分極値条件と一致することを検証する必要があります。これにより、平均場近似が確かに一種の変分法であることが証明されます。

平均場近似では、完全なハミルトニアン$\hat{H} = \hat{H}_0 + \hat{V}_{int}$中の相互作用部分を、パラメータを含む二次形式の演算子に置き換えます。すなわち、

$$
\begin{aligned}
\hat{H}_{mf}(\lambda) = \hat{H}_0 + \hat{V}_{mf}(\lambda)
\end{aligned}
$$

四次形式の相互作用演算子を二次形式の平均場演算子に置き換えることは、ハミルトニアンの一部の対称性を破ることであり、これは最終的に推測される波動関数や推測される密度演算子の対称性の破れに反映されます。

平均場においては、異なるチャネル（channel）を選択することは、異なる対称性を破ることを選択することを意味します。例えば、BCS理論は電荷保存（U(1)対称性）を破ることを選択します。

$$
\begin{aligned}
\hat{V}_{mf}(\lambda) \sim \sum \lambda c^\dagger c^\dagger + h.c.
\end{aligned}
$$

実際に、BCS超伝導相転移では対称性の自発的破れ（Spontaneous Symmetry Breaking）が確かに起こり、厳密な基底状態波動関数や厳密な平衡状態密度演算子は、完全なハミルトニアン$\hat{H} = \hat{H}_0 + \hat{V}_{int}$に比べて対称性が低くなります。

これは、平均場近似が近似手法ではあるものの、相転移過程の本質（essence）を捉えていることを示しています。したがって、量子揺らぎが大きくない（量子臨界点から遠い）場合、我々はしばしば平均場近似を用いて量子系に対する近似的な予言を行います。

## Variational Method

ここで以下のように記すことにします：

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

$F[\hat{\rho}(\lambda) ] \neq F_{mf}$であることに注意が必要です。両者の差は以下の通りです：

$$
\begin{aligned}
F[\hat{\rho}_{mf}(\lambda) ] - F_{mf} = \langle \hat{V}_{int} - \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

よくある誤解として、$F_{mf}$について、$\hat{H}_{mf}$の平衡状態の密度行列自体がそれを最小にする密度行列であるため、

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} = 0
\end{aligned}
$$

であると考えがちです。しかし、これはパラメータ$\lambda$が固定されている場合、すなわち固定されたハミルトニアン$\hat{H}$が変わらない場合にのみ、$F_{mf}$の極値条件を満たします。$\frac{\partial F_{mf}}{\partial \lambda}$は厳密に計算する必要があります：

まず、$F_{mf}$は$\hat{H}_{mf}$の平衡状態自由エネルギーであるため、便利に以下を得ることができます：

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

したがって、

$$
\begin{aligned}
\frac{\partial F_{mf}}{\partial \lambda} & = -T \frac{1}{\mathcal{Z}_{mf}}\frac{\partial \mathcal{Z}_{mf}}{\partial \lambda} \\
& = - T \frac{\operatorname{Tr} ( -\beta \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \frac{\operatorname{Tr} (  \hat{X} e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )}{\operatorname{Tr} ( e^{-\beta [ \hat{H}_0 + \lambda \hat{X} ]} )} \\
& = \operatorname{Tr} ( \hat{\rho}_{mf}(\lambda) \hat{X} ) \\
& =  \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

すなわち、平均場相互作用$\hat{V}_{mf}$部分の秩序変数の期待値です。一般的に平均場近似で計算される秩序変数はゼロではなく、これはシステムが（少なくとも平均場近似の下では）特定の秩序（order）を持っていることを示しています。

上記の結論を利用して、自由エネルギー汎関数$F[\hat{\rho}(\lambda) ]$を極値にするために、以下のようにすればよいことになります：

$$
\begin{aligned}
& \frac{\partial}{\partial \lambda} (F[\hat{\rho}(\lambda) ] - F_{mf}) \\
& = \frac{\partial}{\partial \lambda} \langle \hat{V}_{int}  \rangle_{\rho_{mf}(\lambda)} - \frac{\partial}{\partial \lambda} \langle \hat{V}_{mf} \rangle_{\rho_{mf}(\lambda)} \\
& = -\frac{\partial}{\partial \lambda} F_{mf} = - \langle \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

再び$\hat{V}_{mf} = \lambda \hat{X}$の形式を利用すると、さらに簡略化できます。

$\hat{V}_{mf} = \lambda \hat{X}$と$\hat{\rho}_{mf}(\lambda)$の中の$\lambda$の両方に対して微分を行う必要があることに注意してください：

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

したがって、自由エネルギー汎関数の極値条件は以下のように書けます：

$$
\begin{aligned}
\frac{\partial}{\partial \lambda} F[\hat{\rho}(\lambda) ] = 0\  \Leftrightarrow \ 
\frac{\partial}{\partial \lambda} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\lambda)}  = \lambda \frac{\partial }{\partial \lambda}\langle  \hat{X} \rangle_{\rho_{mf}(\lambda)}
\end{aligned}
$$

さらに、この変分を複数のパラメータ$\{\lambda_i\}$の場合に拡張することもでき、変分の自由度を高めることで、推測解をより真の状況に近づけることができます。

以上より、（一般的に二次形式のみを含む）ある平均場ハミルトニアン$\hat{H}_{mf}(\{\lambda_i\}) = \hat{H}_0 + \sum_i \lambda_i \hat{X}_i$に対応する平衡状態密度行列$\rho_{mf}(\{\lambda_i\})$を推測解として、自由エネルギー汎関数の変分を計算する場合、自由エネルギー汎関数を最小にする（真の平衡状態に最も近い）パラメータ$\{\lambda_i\}$の値は以下の条件を満たします：

$$
\begin{aligned}
\frac{\partial}{\partial \lambda_i} \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}  = \lambda_i \frac{\partial }{\partial \lambda_i}\langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

さらに連鎖律を利用して、変分極値条件を以下のように書くこともできます：

$$
\begin{aligned}
\lambda_i  = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  \hat{X}_i \rangle_{\rho_{mf}(\{\lambda_i\})}} 
\end{aligned}
$$

これにより、変分極値条件に対応するパラメータ（物理的な意味は秩序変数）を直接得ることができます。

しかし、この等式は形式的すぎるため、具体的な例の計算を通じて、これが平均場近似と言っていることと同じであることを発見できます。

一般的な二体相互作用に対して：

$$
\begin{aligned}
\hat{V}_{int} = \frac{1}{2} \sum_{ij}V_{ij} c_i^\dagger c_j^\dagger c_j c_i
\end{aligned}
$$

一般的な平均場相互作用は二次形式として取られ、これにより相互に独立した素励起として厳密に解くことができます。ここでは最も一般的な形式を取ります：

$$
\begin{aligned}
\hat{V}_{mf} & = \underbrace{\sum_{i} \lambda_i^{H} c_i^\dagger c_i}_{\text{Hartree}} \\
& + \underbrace{\sum_{i\neq j} \lambda_{ij}^{F} c_i^\dagger c_j }_{\text{Fock}} \\
& + \underbrace{\sum_{i,j} (\lambda_{ij}^{BCS} c_i^\dagger c_j^\dagger  + \bar{\lambda}_{ij}^{BCS} c_j c_i )}_{\text{BCS}}
\end{aligned}
$$

ここで、1行目、2行目、3行目はそれぞれHartree、Fock、BCS平均場部分に対応します。

ここでは、前述のいわゆるdecoupling methodを直接使用してはいません：

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

その代わりに、係数が完全に未定のハミルトニアンを取りました。その後、変分極値を取るとき、このハミルトニアンがdecoupling methodで得られる「平均場近似ハミルトニアン」であることを証明できます。

同時に、係数が完全に未定であるがゆえに、1行目、2行目、3行目の各項を自由に追加したり減らしたりすることができます。これは単に変分のパラメータを増減させるだけだからです。

次に$\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})}$を求めます。これは平均場に対応する平衡状態下での厳密な二体相互作用演算子の期待値です。

Wickの定理を使用する必要があります。なぜなら、平均場のハミルトニアンは二次形式であり、生成汎関数（Generating Functional）はガウス型であるため、平衡状態のフェルミ演算子の期待値は、2つのフェルミ演算子の縮約（contraction）に厳密に分解できるからです。

$$
\begin{aligned}
\langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} & = \frac{1}{2} \sum_{ij}V_{ij} \langle c_i^\dagger c_j^\dagger c_j c_i \rangle_{\rho_{mf}(\{\lambda_i\})} \\
& = \frac{1}{2} \sum_{ij}V_{ij} (\langle c_i^\dagger  c_i \rangle \langle c_j^\dagger  c_j \rangle \\
& - \langle c_i^\dagger  c_j \rangle \langle c_j^\dagger  c_i \rangle + \langle c_i^\dagger  c_j^\dagger \rangle \langle c_j  c_i \rangle)
\end{aligned}
$$

したがって、変分極値条件を利用すると、以下のようになります：

$$
\begin{aligned}
    \lambda_i^H & = \frac{\partial \langle \hat{V}_{int} \rangle_{\rho_{mf}(\{\lambda_i\})} }{\partial \langle  c_i^\dagger c_i \rangle_{\rho_{mf}(\{\lambda_i\})}} \\
    & = \frac{1}{2} \sum_j \left( V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} +  V_{ji} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})} \right)\\
    & = \sum_{j} V_{ij} \langle  c_j^\dagger c_j \rangle_{\rho_{mf}(\{\lambda_i\})}
\end{aligned}
$$

ここで$V_{ij} = V_{ji}$を利用しました。観察すると、これが以前に「decoupling」を用いて得られたHartree平均場近似項であり、せいぜい定数差であることがわかります。

以前は$\hat{A}_{i}^{H} = c_i^\dagger c_i$を選定し、その量子揺らぎの二次項を省略しました。一方ここでは、単に変分極値条件を用いて、自由エネルギー汎関数を最小にする推測ハミルトニアンのパラメータを決定しただけです。

同様に、Fock、BCS平均場近似に対応する他の未定パラメータについても、以下のようになります：

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

これらを$\hat{V}_{mf}(\{\lambda_i\})$に代入すると、それらがそれぞれFock、BCS平均場近似に対応することも容易にわかります。

しかし、変分法の観点からは、これらの未定係数と推測ハミルトニアンの項は独立しており、互いに影響しません。推測ハミルトニアンに項を加減することは、推測解の形式を変え、変分のパラメータを増減させることに過ぎません。したがって、Hartree、Fock、BCS平均場近似は確かに1:1:1で混ぜたり、ペアで混ぜて使用したりすることができ、すべて与えられたパラメータに対する変分極値条件を満たします。

ただし、特定の問題においては、特定の秩序変数に関心があるため、変分パラメータを極力減らし（BCSまたはHartree-Fockのみを使用するなど）、可能な限り簡潔で有効な結論を得ようとします。

## Summary

以上より、我々は変分法の厳密な導出を通じて、Hartree、Fock、BCSといった平均場理論が確かに1:1:1で混ぜて使用できることを証明しました。

まず、量子力学の教科書によく出てくるdecouple methodを利用し、演算子の二次揺らぎ項を「強引に」省略することで、ある種の平均場近似下での平均場ハミルトニアンを近似的に得ました。

$$
\begin{aligned}
A^\dagger A \approx \langle A^\dagger \rangle A + A^\dagger \langle A \rangle - \langle A^\dagger \rangle \langle A \rangle
\end{aligned}
$$

しかし、このdecouple methodは、2種類以上の平均場近似を使用する場合、重複計算の錯覚を生じさせやすいものでした。

その後、変分法の言語を用いて、平均場近似の変分法的本質を再記述しました。すなわち、システム$\hat{H} = \hat{H}_0 + \hat{V}_{int}$の平衡状態と、ある平均場ハミルトニアン$\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i\})$（推測ハミルトニアン、様々な未定係数$\{\lambda_i\}$を含む）の平衡状態が非常に近いと考えます。

システムの自由エネルギー変分を最小にする未定係数$\{\lambda_i^{mf}\}$を選択し、その係数選択下での平均場ハミルトニアン$\hat{H}_{mf} = \hat{H}_0 + \hat{V}_{mf}(\{\lambda_i^{mf}\})$を用いて元の（相互作用）システムハミルトニアン$\hat{H} = \hat{H}_0 + \hat{V}_{int}$を近似することが、平均場近似です。

そして変分法とWickの定理を通じて、最適な未定係数$\{\lambda_i^{mf}\}$が、decouple methodにおける一次揺らぎ項を選択した結果と正確に一致すること、すなわち最適な未定係数$\{\lambda_i^{mf}\}$がシステムの平均場（秩序変数）であることを証明しました。

元の「Hartree、Fock、BCSといった平均場理論は1:1:1で混ぜて使えるか」という問題に戻ると、変分法を使用する場合、未定係数の数に規定はなく、あるいは各未定係数の変分極値条件は互いに独立しています。

したがって、decouple methodにおけるHartree、Fock、BCS平均場理論に対応するDensity、Exchange、Cooper Channelは実際には独立しており、重複計算にはなりません。これにより、以下が証明されました：

**Hartree、Fock、BCSといった平均場理論は確かに1:1:1で混ぜて使用できます。**

## Reference

- [1] Bruus, H., & Flensberg, K. (2004). Many-body quantum theory in condensed matter physics: an introduction. Oxford university press.
- [2] Coleman, P. (2015). Introduction to many-body physics. Cambridge University Press.
- [3] Altland, A., & Simons, B. D. (2010). Condensed matter field theory. Cambridge university press.
