---
layout : post
title : "基础代数几何备忘1"
category : Algebraic geometry
date : 2015-09-13
tags : [math, 代数几何, AG]
SyntaxHihglighter: true
shTheme: shThemeDefault 
duoshuo: true 
math: true
---

##序

最近找到一本本科阶段的代数几何书，就是下面这本，Klaus Hulek所写的 *Elementare Algebraische Geometrie* ,当然我看的是这本书的中译本。译者是胥鸣伟，质量是有保证的。

![book](/res/img/blog/201509/elemAG.jpg)

想来国内在本科阶段能够开设代数几何课的高校并不是很多，一来师资匮乏，二来没有合适的本科生教材，更不必说稀缺的中文版教材。这套教材很适合于代数几何入门的，我们从它的目录开始看

1. 仿射簇 Affine Variet\"aten
2. 射影簇 Projektive Variet\"aten
3. 光滑点和维数 Glatte Punkte und Dimension
4. 平面三次曲线 Ebene kubische Kurven
5. 三次曲面 Kubische Fl\"achen
6. 曲线论简介 Theorie der Kurven

从目录来看并没有引入概形和上同调工具，细致一点观察目录还是能发现还是讲述了一些很重要的概念，如范畴与函子，除子与Riemann-Roch定理等等。本文的目的是力求梳理各章节的脉络，对于一些内容进行简短的注记和说明。鉴于此，很多定理的叙述和复杂的证明就省略掉了，要认真学习这门科目的话还是要去读书。另外该书作者也同样推荐了很好的参考书，比如M. Reid所著 *Undergraduate Algebraic Geometry* 。在这里我同样推荐Reid所写的 *Undergraduate Commutative Algebra* 一书。

##第0章 引言

我们从引言开始：

对于“代数”这门分支，我们最初接触到的是**“线性代数”**（linearen Algebra）。线性代数研究的是一个域上的线性方程组的解。对于线性方程组人们已经发展了完整的理论：对于解的存在性和解集的结构都可以做精确的描述。同样在线性代数中还借用对称矩阵对二次超曲面进行了分类。这两者重要的差别在于二次曲面分类依赖于数域的选择。

而**代数**研究的是任意次多项式方程的解。这个问题的解答依赖于基域的选择。要想使一般的多项式方程有解需要假定基域是代数闭域。

**代数几何**处理的是多变量的任意多项式方程组的解。

接下来便开始了一些简单概念的介绍：代数集（algebraischen Menge），仿射空间（affine Raum），零点（Nullstelle），零点集（Nullstellengebilde），代数闭集（abgeschlossene）等等。

这里需要说明的是$n$维仿射空间作为点集和$k^n$是一样的，但是仿射空间没有线性空间结构，即没有加法，没有特殊的点，特别是没有指定原点。实际上可以给$\mathbb{A}_k^n$一个Zariski拓扑使之称为一个拓扑空间。这个拓扑是和欧式拓扑相差很大的。

对于代数集有重要的例子是一般线性群$GL_n(k)$，它实际上是代数群（algebraischen Gruppe）。这样的例子还有$SL_n(k)$，$O_n(k)$，$Sp_{2n}(k)$等。

最后提到的费马大定理正是激励了一代代数学家来发展这一学科的动力之一。

##第1章 仿射簇

这一章主要是将“代数”和“几何”联系起来。其中自然涉及到一些代数学的定理，特别是交换代数的定理，其中最重要的就是Hilbert零点定理(Hilbertsche Nullstellensatz)，注意讲英文时千万不要叫这一定理为“theorem of zeros”，一看就不专业 = =。当然建立这个联系少不了范畴论的内容，其中最关键的是“函子”（Funktor）这一概念。这一章假定基域是代数闭域。

###简单事实

令$A=k[x_1,\cdots,x_n]$，我们考虑的代数对象是$A$的所有理想组成的集合，相对应的几何对象是$\mathbb{A}_k^n$中的代数集。

首先我们有两个方向的映射

$$V:\{A \mbox{的理想}\}\longrightarrow \{\mathbb{A}_k^n \mbox{中的代数集}\}$$

$$J\mapsto V(J)$$

$$I:\{\mathbb{A}_k^n \mbox{中的子集}\}\longrightarrow \{A \mbox{的理想}\}$$

$$X \mapsto I(X)$$

$V$是满射，不一定单。$I$既不一定单也不一定满。若局限于适当的理想类和代数集，则它俩是互逆的双射。

一些显而易见的结论有: $V(J)$满足闭集公理，$V,I$是反序对应的。每个子集均有$X\subset VI(X)$，等式成立当且仅当$X$是代数集。对于理想$J$,$J\subset IV(J)$。如$J=(x^2),IV(J)=(x)$

定义根式理想后可以得到形如$I(X)$的理想是根式理想，素理想是根式理想。

一些命题如下：
非空代数集$X$不可约当且仅当$I(X)$是素理想。 命题左边是几何，右边是代数。

每个代数集$X\subset \mathbb{A}_k^n$具有一个不计次序的唯一的表达式$X=X_1\cup \cdots \cup_r$，其中每个$X_i$不可约，并且$i\neq j, X_i \nsubseteq X_j$.这样每个$X_i$称为$X$的不可约分支。 注：这个命题对于所有的诺特拓扑空间都成立。

不可约代数集一个重要的等价条件

1. $V$不可约
2. 任意非空开集$U_1,U_2 \subset V$,有$U_1\cap U_2 \neq \emptyset$
3. 每个非空开集$U\subset V$稠于$V$。

### 零点定理

假定$k$是代数闭域,$A=k[x_1,\cdots,x_n]$。

Hilbert NULLSTELLENSATZ有好几个等价的命题，我们首先来看最像“零点”定理的:
**若$J\subset A$为真理想，则$V(J)\neq \emptyset$.**，再来看与之等价的比较容易得到的命题：

- 每个极大理想$m\subset A$具有形式$m=(x_1-a_1,\cdots,x_n-a_n)=I(P)$,其中$P$是仿射空间中的一个点.
- 每个理想$J \subset A$有$IV(J)=\sqrt{J}$. 

其中第一个是说几何上的点对应与环的极大理想，第二个是说对应于代数簇的是根式理想。我们后面来给出对应关系，在这里我们看一个稍微不一样的代数版本的零点定理：

设$A$是有限生成$k$-代数，若$A$是域，则$A$是$k$上的代数扩域。

这个定理可以由诺特正规化定理得到。我们从这个命题立即可以得到极大理想的样子，有理极大理想对应于点立即可以得到最像“零点”定理的命题；接着证明上面两个单独列出来的命题是等价时需要用到"Rabinowitsch's Trick"（引入新变量），详情看书。

----

映射$$\{A \mbox{的理想}\}\overset{V,I}\longleftrightarrow \{\mathbb{A}_k^n \mbox{的子集}\} $$定义了如下双射：

$$\{A \mbox{的根式理想}\}\overset{1:1}\longleftrightarrow \{\mathbb{A}_k^n \mbox{的簇}\} $$

$$\{A \mbox{的素理想}\}\overset{1:1}\longleftrightarrow \{\mathbb{A}_k^n \mbox{的不可约簇}\} $$

$$\{A \mbox{的极大理想}\}\overset{1:1}\longleftrightarrow \{\mathbb{A}_k^n \mbox{的点}\} $$

并且有极大理想$\Rightarrow$素理想$\Rightarrow$根式理想。

$$\mathbb{A}_k^n \mbox{的不可约超曲面}\overset{1:1}\longleftrightarrow \{\mbox{不可约多项式}f\}/k^*$$

----

### 代数结果

这里主要引入的是整扩张，中山引理（NAK）和诺特正规化定理。其中NAK主要使用了叫作"determinant trick"的技巧。

诺特正规化展示了维数的几何观念与簇的坐标环的的联系。一边是几何意义上的仿射簇维数，一边是代数意义上的坐标环的函数域的超越次数。

接下来引入可分元，可分扩域，本原元定理。这里有扩域$k\subset K$可以分解成一部分纯超越扩张，一部分是单扩张，$k\subset K_0=k(y_1,\cdots,y_m)\subset K=K_0(y_m+1)$,这些$y_i$间只有一个代数关系，每个不可约簇“几乎”同构于一个超曲面。

### 函数与映射

主要有 多项式函数与多项式映射，有理函数与有理映射。并且在这一部分引入了范畴论里的简单概念：对象，态射，函子，共变反变，自然变换，范畴等价，积等概念

这节$V$表示$\mathbb{A}_k^n$中一个仿射簇

#### 多项式函数与多项式映射 ####

首先多项式函数是一个映射$f:V\longrightarrow k$，使得存在多项式$F\in A$，对所有的$P \in V$有$f(P)=F(P)$.

这样的多项式显然不是唯一的，若$G$满足$F\|_V=G\|_V$,即$F-G\|_V=0$也就是$F-G\in I(V)$,从而有了坐标环$k[V]=A/I(V)$,实际上$k[V]=\{f: f\mbox{是一个多项式函数}\}$。

于是我们有前面部分的一些重述

-----
$V$不可约当且仅当$I(V)$是素理想当且仅当$k[V]$是整环。

限制在簇$V$上来看

$$\{k[V] \mbox{的根式理想}\}\overset{1:1}\longleftrightarrow \{ \mbox{代数闭集}W\subset V\} $$

$$\{k[V] \mbox{的素理想}\}\overset{1:1}\longleftrightarrow \{\mbox{不可约集}W\subset V\} $$

$$\{k[V] \mbox{的极大理想}\}\overset{1:1}\longleftrightarrow \{\mbox{点}P\in V\} $$

从而$V$的代数闭子集定义了其上的一个拓扑，它也是从仿射空间诱导来的拓扑

----------

既约代数就是不包含任何幂零元，$A/I$既约当且仅当$I$是根式理想。由于簇$V$的理想总是根式理想，从而坐标环是既约的。

一个仿射簇的坐标环$k[V]$是有限生成的既约$k$-代数。反过来，任何一个有限生成的既约$k$-代数$A$，可以构造一个代数簇$V$，使得它的坐标环$k[V]$就是$A$：下面是详细说明

选定生成元$a_1,\cdots,a_n$,于是$A=k[a_1,\cdots,a_n]$.从而考虑满同态

$$\pi:k[x_1,\cdots,x_n]\longrightarrow A=k[a_1,\cdots,a_n]$$,$x_i\mapsto a_i$

的核$I=ker(\pi)$,令$V=V(I)$是簇。$V$不可约当且仅当$A$整环，由于$A$既约故$I$是根式理想，从而$I(V)=IV(I)=I$,于是$k[V]=k[x_1,\cdots,x_n]/I(V)=A$.

多项式映射是两个簇之间的映射，也就是说$f$的分量是由多项式定义的。多项式映射在Zariski拓扑下连续。

设$f:V\longrightarrow W$为多项式映射，则$f^*:k[W]\longrightarrow k[V]$是$k$-代数同态，反过来也有

若$\phi:k[W]\longrightarrow k[V]$是$k$-代数同态，则恰好存在一个多项式映射$f$使得$\phi=f^*$.(选取$f=(\phi(\bar{y}_1),\cdots,\phi(\bar{y}_m))$)从而有双射

$$\{f:V\rightarrow W \mbox{为多项式映射}\}\overset{1:1}\longleftrightarrow \{\phi:k[W]\rightarrow k[V]\mbox{为$k$-代数同态}\}$$，$f\mapsto f^*$

于是几何的簇的同构问题转化为代数的同构问题

$f$是簇间同构当且仅当$f^*$是$k$-代数间同构。

----

反变函子$V\mapsto k[V],f\mapsto f^*$定义了下述范畴等价

$$\{\mbox{仿射簇，多项式映射}\}\longleftrightarrow \{\mbox{有限生成既约$k$-代数，$k$-代数同态}\}$$

$$\{\mbox{不可约仿射簇，多项式映射}\}\longleftrightarrow \{\mbox{作为整环的有限生成$k$-代数，$k$-代数同态}\}$$

#### 有理函数与有理映射 ####
