---
layout: default
title: 高代复习
sort_order: 1
is_note: true
---

- 秩一矩阵。

$r(A)=1$,则 $A=uv^T$。

其特征值：

$$
uv^Tx=\lambda x\\
v^Tuv^Tx=\lambda v^T x\\
\lambda=v^Tu
$$

而 $v^Tu=\text{tr}(A)$。

- 当 $\text{tr}(A)\ne 0$ 时，$A$ 可对角化，有特征值 $\text{tr},0,0,...,0$ 。

- 当 $\text{tr}(A)=0$ 时，$A$ 不可对角化，因为 $r(A)=1$ ，$\lambda=0$ 几何重数是 $n-1$ ，代数重数是 $n$，因此不可对角化。

---

- 可交换与同时对角化。

$AB=BA$，并且他们都可对角化，那么有：

$$
Ax=\lambda x\\
BAx=\lambda Bx=ABx\\
Bx\in V_{\lambda}
$$

也就是 $ V_\lambda$ 是 $B$ 的不变子空间，$B$ 在 $V$ 中可对角化，因此在小的空间 $V_{\lambda}$ 中也可对角化，因此 $V_\lambda$ 中找一组基，使得都是 $B$ 的特征向量。

因此我们就找到了一组基，使得是 $A,B$ 的特征向量，也就是 $A,B$ 可以通过矩阵 $P$ 同时对角化。

如何寻找那个公共矩阵 $P$，找公共特征向量即可。

---

- 代替最小多项式的证明可对角化

> 证明，如果 $(A-aI)(A-bI)=0,a\ne b$，那么 $A$ 可对角化。

第一种做法是直接考虑 $V_a+V_b=n$。

$$
r(A-aI)+r(A-bI)\le n+r(A-aI)(A-aI)=n\\
r(A-aI)+r(A-bI)\ge r((a-b)I)=n\\
\ker(A-aI)-\ker(A-bI)=n
$$

因此两个特征子空间维数的和是 $n$，所以可对角化。

还有一种比较厉害的几何做法，可以推广。

> 如果 $\prod_{i=1}^n (A-a_iI) =0,a_i$ 互不相同，那么 $A$ 可对角化。

先回顾一个拉插的东西，令

$$
f_i(x)=\frac{\prod_{j\ne i}(x-a_j)}{\prod_{j\ne i}(a_i-a_j)}
$$

显然满足，$f_i(a_i)=1,f_i(a_j)=0$ 。

令 $f(x)=\sum_{i=1}^n f_i(x)$，那么 $f(x)$ 有 $n$ 个点值为 $1$,那么 $f(x)=1$ 。

这个东西和特征值是很适配的，我们带入矩阵 $A$。

$$
f_i(A)=\frac{\prod_{j\ne i}(A-a_jI)}{\prod_{j\ne i}(a_i-a_j)}\\
\sum_{i=1}^n f_i(A)=I\\
$$

此时我们回归主题，我们要证明，$V$ 可以表示成所有特征子空间的和。

也就是 $\forall x,x=x_1+x_2+...+x_n,(x_i\in V_{a_i})$。

$$
x=\sum_{i=1}^n f_i(A)x
$$

而 $(A-a_i)f_i(A)x=0$ ，所以 $f_i(A)x\in V_{a_i}$。

因此得证，$V$ 可以表示成所有特征子空间的和，因此可对角化。

---

- 反对称矩阵相关：

> 如果 $A$ 是反对称矩阵，那么 $A$ 的特征值是纯虚数或者 $0$ 。

$$
Ax=\lambda x\\
\overline x^TAx=\lambda \overline x^Tx\\
\overline x^TA=-(A\overline x)^T=-(\overline \lambda\overline x)^T=-\overline \lambda \overline x^T\\
\overline x^TA=-\overline \lambda \overline x^Tx\\
\lambda=-\overline \lambda
$$

所以特征值是纯虚数或者 $0$ 。

也就是对于实数 $a$，$|A+aI|\ne 0$ 。

> 对于任意对角矩阵 $D$，若 $D_{i,i}>0$ ，证明 $|A+D|\ne 0$ 。

有 $P_{i,i}=\sqrt{D_{i,i}}$。

那么

$$
A+D=P(P^{-1}AP^{-1}+I)P
$$

$P^{-1}AP^{-1}$ 还是反对称矩阵，因此中间行列式不是 $0$,因此总行列式不是 $0$。

---

> 已知矩阵 $A$，满足 $\forall x\in R^n,x^TAx\ge 0$，证明 $Au=0$ 和 $A^Tu=0$ 充要。

注意 $A$ 不一定是对称矩阵，所以不是直接半正定。

路线一：$\dfrac{A+A^T}{2}$ 是对称矩阵。

路线二：$A=B+C$，其中 $B$ 是对称矩阵，$C$ 是反对称矩阵。

按照路线二做，那么 $B$ 是半正定矩阵。

- 重要推论：对于半正定矩阵 $A$，如果 $x^TAx=0$ ，那么 $Ax=0$ 。

证明考虑 $A=P^TP$，$(Px)^TPx=|Px|^2=0$ ，因此 $Px=0,Ax=0$ 。

那么就很简单了，$x^T(B+C)x=0,x^TCx=x^TBx=0,Bx=Cx=0$ ，而 $A^T=B-C$，所以 $A^Tx=0$ ，反过来是一样的。

> 已知 $(v_1,v_2,..,v_m)\in R^n,\forall i\ne j,(v_i,v_j)\le 0$，证明 $m\le 2n$。

这题用归纳法，我们想要把问题缩小一个维度。

此时不应该想，先确定 $v_1,v_2$ 然后去锁维度，而是应该用投影，来缩维度。

归纳，已经证明 $n-1$ 维空间只能容纳最多 $2(n-1)$ 个向量。

投影到哪个平面上呢，对于 $v_1$ ，得到一个平面 $W$ 垂直 $v_1$,然后把所有向量投影到 $W$ 上。

则 $v_i=v_i'+a_iv_1(v_i'\in W,a_i\le 0)$ ，如果 $a_i>0$ 显然寄。

$$
(v_i,v_j)=(v_i'+a_iv_1,v_j'+a_jv_1)\\
=v_i'v_j'+a_ia_j|v_1|^2\\
(v_i,v_j)\le 0\to (v_i',v_j')\le 0
$$

因此投影后的向量要在 $W$ 上满足，因此最多 $2(n-1)$ 个，以及最多还有一个零向量，所以归纳成立。

---

- Garm 矩阵：

对于向量组 $A=(a_1,a_2,...,a_n)$，定义其 Garm 矩阵为：

$$
g_{i,j}=(a_i,a_j)\\
G=A^TA
$$

- $r(A)=r(A^TA)$。

这个还是比较重要的一个结论，证明考虑证明他们零空间大小相同。

$$
Ax=0\to A^TAx=0\\
A^TAx=0\to x^TA^TAx=0\\
\to |Ax|^2 =0\\
Ax=0
$$

- $A^TA$ 一定是半正定的。

因为 $x^TA^TAx=|Ax|^2\ge 0$ 。

并且如果一个矩阵是半正定的，一定可以拆成 $A^TA$。

---

- 过渡矩阵

好像很容易绕晕。

一组基 $\alpha$，要变换成 $\beta$，那么矩阵是要乘在右边，因为对列向量线性变换要乘在右边。

$$
\alpha C=\beta
$$

而对于 $\alpha$ 上的坐标 $a$，$\beta$ 上对应坐标是 $b$。

$$
\alpha a=\beta b\\
\alpha a=\alpha Cb\\
a=Cb
$$

这里就反过来了，变成 $b$ 通过坐标变换变成原向量。

形象考虑：比如我基从 $1$ 变成了 $10$,那么坐标当然是会变小。

---

分块矩阵 

$$
\begin{vmatrix}
E & A\\
A^T & E
\end{vmatrix}
$$

非常重要。