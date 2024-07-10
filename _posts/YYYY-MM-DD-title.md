---
title: "test1"
date: 2024-07-11
---
## 说明

我们的目的是给出实数的公理化定义。也可以理解为学习实数的各种性质。

关于集合论的基础知识，比如笛卡尔积，关系，以及映射等，可以自行Google，我们在此不提。

## 实数的性质（公理化定义）

### 有序集
> [!NOTE] 
若 $S$ 是一个集合，如果它上面具有一种关系，记作 <，满足：
(i) 任意 $x\in S,\ y\in S$，以下三种情况有且只有一种成立：
$$x\textless y,\ x=y,\ y\textless x$$
(ii) 对于 $x,y,z\in S$，如果 $x\textless y,\ y\textless z$，则 $x\textless z$.
那么我们叫关系 < 为 $S$ 上的一个序关系，称 $S$ 为一个有序集。

> [!NOTE] 
如果 $S$ 是一个有序集， $E$ 是 $S$ 的一个非空子集，假设 $b\in S$，如果对于任意 $a\in E$，都有 $a\leq b$，则称 $b$ 是 $E$ 的一个上界。称 $E$ 在 $S$ 中有上界。

类似地可以定义下界。

> [!NOTE] 
如果 $S$ 是一个有序集， $E$ 是 $S$ 的一个非空有上界的子集，如果 $b\in S$ 是 $E$ 的一个上界，且满足：任意 $x\in S$，若 $x\textless b$， 则 $x$ 不是 $E$ 的上界。 那么就说 $b$ 是 $E$ 的上确界。记作 $b=\sup E$ 。

那么是不是对于任意的有序集，对于任意的非空有上界的子集，都存在上确界呢？

我们注意到有理数集 $Q$ 和它上面的序关系 $<_Q$ 构成了一个有序集，我们考虑这样一个集合
$$E=\{x\in Q\mid x\textgreater 0\ {且}\ x^2\textless2\}$$
这个集合是非空有上界的。

如果它存在一个上确界 $b=\sup E$ ，它应该要满足 $b^2=2$ 。我们可以导出矛盾，不存在这样的 $b\in Q$ 。

> [!NOTE] 
我们说明 $b^2<2$ 和 $b^2>2$ 都不可能是上确界。
若 $b^2<2$，我们总能构造出一个比 $b$ 更大的 $a\in Q$ 是在 $E$ 中的，这就和 $b$ 是上界矛盾了。
因为我们希望 $a>b$，不妨设 $a=b+\epsilon,\ \epsilon >0 \in Q$，通过控制 $\epsilon$ 的范围（我们当然希望它越来越小），让 $a$ 不超出 $E$ 的范围，我们先假设 $\epsilon\textless b$，则有
$$a^2=(b+\epsilon)^2=b^2+2\epsilon b +\epsilon^2\textless b^2+3\epsilon b$$
只需要
$$b^2+3\epsilon b\textless 2$$
取满足 $\epsilon\textless \frac{2-b^2}{3b}$ 的 $\epsilon\in Q$ 即可。
类似地我们可以说明 $b^2\textgreater 2$ 的情况不是上确界。所以如果 $Q$ 中存在 $E$ 的上确界 $b$，那么它满足 $b^2=2$ 。
我们设 $b=p/q$ 是既约分数（$(p,\ q)=1$ ），则我们有
$$p^2=2q^2$$
故有 $2\mid p$，故 $4\mid p^2$，故 $q^2=p^2/2$ 满足 $2\mid q$ ，矛盾。

对于有序集 $S$，我们称这样的性质，即在每个非空有上界的子集都存在上确界，为最小上界性，显然不是每个有序集都具有这个性质。类似地，我们还有最大下界性。

如果有序集 $S$ 具有最小上界性，那么对于它的任一非空且有下界的子集 $E$，考虑它所有下界组成的集合 $$F=\{b\in S\mid b\ \rm{是}\ E \ {的下界}\}$$
这是一个有上界且非空的集合，我们取它在 $S$ 中的上确界 $b$（一定存在），可以验证 $b$ 也是 $E$ 的下确界。

综上，最小上界性和最大下界性是可以互推的。

### 域

> [!NOTE] 
设 $F$ 是一个集合，并且它配有两个运算，记作 $+,\cdot$，如果这两种运算满足以下一些性质，我们就说 $F$ 是一个域：
(A)
(a1) $\forall\ x,\ y\in F,\ x+y=y+x$ ;
(a2) $\forall\ x,\ y,\ z\in F,\ (x+y)+z=x+(y+z)$ ;
(a3) $\exists\ 0\in F, \ \forall\ x\in F,\ 0+x=x+0=x$ ;
(a4) $\forall\ x\in F,\ \exists \ y\in F,\ x+y=y+x=0$ .
(M)
(m1)  $\forall\ x,\ y\in F,\ xy=yx$ ;
(m2) $\forall\ x,\ y,\ z\in F,\ (xy)z=x(yz)$ ;
(m3) $\exists\ 1\in F,\ 1\neq0, \ \forall\ x\in F,\ 1\cdot x=x\cdot 1=x$ ;
(m4) $\forall\ x\neq0\in F,\ \exists\ y\in F,\ xy=yx=1$ .
(D) $\forall\ x,\ y,\ z\in F,\ x(y+z)=xy+xz$ .

我们可以证明满足(a3)，(m3)的元素都是唯一的，我们分别称为加法，乘法下的单位元。
对于每个符合条件的 $x\in F$ ，满足 (a4)，(m4)的元素 $y$ 也是唯一的，分别称为 $x$ 在加法，乘法下的逆元，记作 $(-x),\ 1/x$ 。
我们还可以引入一些记号，比如 $-,\ \frac{x}{y},\ x^n$ 之类的，在这里不详细说明。

由 (A)，(M)，(D) 我们可以推出一些我们“熟知”的结论。
比如 $x+y=x+z$，则 

$$
\begin{equation}\begin{split} 
y&=0+y=((-x)+x)+y \\ 
&\quad =(-x)+(x+y)=(-x)+(x+z)\\ 
&=((-x)+x)+z=0+z\\ 
& =z 
\end{split}\end{equation}
$$

也就是消去律。

其它的结论可以看《数学分析原理》，有详细的推导，在这里我们不列举了。

### 有序域

> [!NOTE] 
设 $F$ 是一个有序集，同时是一个域，< 是它上面的序关系， $+,\cdot$ 是它的加法和乘法，如果它们满足：
(i) 对于任意 $x\in F$ 与 $y\textless z$，都有 $x+y\textless x+z$ ;
(ii) 对于任意 $x\textgreater 0,\ y\textgreater 0$，都有 $xy\textgreater 0$ .
那么就称 $F$ 是一个有序域。

我们也可以得到很多推论。

比如对于 $a,b,c,d\in F$，如果 $a\textgreater b,\ c\textgreater d$，那么有 $a+c\textgreater b+c\textgreater b+d$ 。

再比如对于 $x\textgreater 0$，若 $(-x)\geq0$，那么 $0=x+(-x)\geq x+0\textgreater 0+0=0$，产生矛盾，所以 $(-x)\textless 0$ 。

### 实数

> [!NOTE] 
实数集 $R$ 是一个有序域，且具有最小上界性，有理数集 $Q$ 是它的子集。

存在性（$R$ 的定义）可以由戴德金分割给出，具体步骤见《数学分析原理》。

我们可能会在后面说明实数的唯一性。在这之前我们要说明实数的一些重要性质。

> [!NOTE] 
设 $x\textgreater 0\in R$ ，$y\in R$，则存在整数 $n$，使得 $nx\textgreater y$。

使用反证法。

> [!NOTE] 
假设对于任意整数 $n$，都有 $nx\leq y$，则 $y$ 是集合 $E={nx}$ 的一个上界。由 $R$ 的最小上界性，$b=\sup E$ 存在。
因为 $b-x\textless b$ 不是 $E$ 的上界，所以存在 $mx\in E \ \textgreater b-x$，所以有 $(m+1)x\textgreater b$，这产生了矛盾。
根据阿基米德性我们可以知道有理数在实数集中是“稠密”的，即对于任意 $x\textless y$，都存在 $q\in Q$ 使得 $x\textless q\textless y$ 。我们只证明 $x\textgreater 0$ 的情况。

> [!NOTE] 
要得到这样的 $q$，我们先设 $q=m/n$ 是分数形式，则 $x\textless m/n\textless y$ 等价于 $nx\textless m\textless ny$，这其实是说 $nx,\ ny$ 中间要放得下一个整数 $m$，所以这等价于 $ny-nx\textgreater 1$ 即 $n(y-x)\textgreater 1$。
我们知道 $y-x\textgreater 0$，根据阿基米德性存在这样的整数 $n$。

回过头来我们取任何一个集合 $T$，它是一个有序域，且有着最小上界性（确界原理）。我们看一下它具备怎样的结构。

首先在任何有序域中，我们可以根据定义中那几条性质（公理）出发，得到 $1=1^2\textgreater 0$。所以规定 $n=1+1+...+1$ (一共有自然数 $n$ 个)，我们有 $(n+1)=n+1\textgreater n$ ，所以集合 $\{n\in T\}$ 是无限集（以上的 n 还有 1 都是指 T 中的元素），更准确的说它和自然数集是同构的。
更进一步我们通过做“除法”（乘法）可以得到集合 $\{\frac{m}{n}\in T\}$ ，这和我们的有理数集也是同构的，我们就叫它 $Q_T$ 吧。

同构的意思就是存在双射使这两个集合一一对应，并且这个一一对应保持了集合上面的序结构和运算结果。细节我们可以先不用管，大概意思知道就行了。

这一小节中的证明是可以迁移到 $T$ 上的，所以 $Q_T$ 也在 $T$ 中是稠密的，等我们学了后面的“极限”的概念，我们就可以用 $Q$ 中的序列来逼近 $R$ 中元素 $r$，同理用 $Q_T$ 中对应的序列去逼近 $T$ 中元素 $t$，这样就把 $r,\ t$ 对应起来了。我们就能说明 $R$ 和 $T$ 也是同构的。

这可以看成是度量空间的完备化。

### 一些运算的定义

我们之前举了一个例子
$$E=\lbrace x\in Q\mid x\textgreater 0\ {且}\ x^2\textless 2 \rbrace$$
说明了 $Q$ 上没有确界原理。

我们知道这个集合在实数集的上确界是“根号二”，但是我们没有定义根号这个运算（我们有次方运算，这只需要用乘法归纳定义），我们不是靠“开平方”算出来了“根号二”这个数（这个数我们不知道是什么东西，我们不知道存不存在一个数的平方结果是2），我们是根据确界原理说明了 $E$ 的上确界存在（在 $R$ 上）。

所以我们是用确界原理来定义根号，指数函数这些运算，不要搞反了。

> [!NOTE] 
对于 $x\in R>0$和正整数 $n$，定义 $$ x^{\frac{1}{n}}=\sup \{a\in R_{\textgreater 0} \mid a^n\textless x\}$$
我们发现 $x^{\frac{1}{n}}$（简记作 $y$）满足 $y^n=x$。

我们知道这个 $y$ 是存在的：因为 $(x+1)^n\textgreater (x+1)\textgreater x$ ，所以 $E=\{a\in R_{\textgreater 0} \mid a^n\textless x\}$有上界。
又如果 $x\textgreater 1$，那么 $1^n\textless x$，所以 $1\in E$ ；如果 $x\textless 1$ ，那么 $x^n\textless x$ ，所以 $x\in E$ 。所以 $E$ 是非空的。综上根据确界原理 $y$ 存在。

我们可以用前文类似的方法说明 $y^n=x$ ：假设 $y^n\textless x$ ，我们希望找到一个 $b\textgreater y$ 且 $b\in E$ ，这样就引出矛盾。同样我们设 $b=y+a,\ a\textgreater 0$，有
$$b^n=(y+a)^n=\sum_{0\leq k\leq n}C^k_n a^k y^{n-k}$$
我们同样让 $a\textless y$，就有
$$\sum_{0\leq k\leq n}C^k_n a^k y^{n-k}\textless y^n+a(\sum_{1\leq k\leq n}C^k_n  y^{n-1})$$
所以只需要
$$y^n+a(\sum_{1\leq k\leq n}C^k_n  y^{n-1})\textless x$$
也就是
$$a\textless \frac{x-y^n}{\sum_{1\leq k\leq n}C^k_n  y^{n-1}}$$
我们知道小于号右边的式子是大于0的，所以总能找到这样的正数 $a$，令 $b=y+a$ 即为所求。

$y^n\textgreater x$ 的情形也是类似的。

>[!QUESTION]
我们怎么定义指数函数？并验证这些运算该有的性质，比如 $(xy)^{\frac{1}{n}}=(x)^{\frac{1}{n}}(y)^{\frac{1}{n}}$ 。

更多内容，如复数，欧氏空间等，见《数学分析原理》。

