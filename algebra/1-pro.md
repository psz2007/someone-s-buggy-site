---

layout: default
title: 线性代数复习
sort_order: 1
is_node: true

---

> 有 $n\times n$ 矩阵 $C$，已知 $c_{i,j}=\dfrac{1}{a_i+b_j}$，求 $|C|$。

第 $i$ 行减去第一行，那么对于 $i>1$，得到：

$$
c_{i,j}-c_{1,j}=\frac{1}{a_i+b_j}-\frac{1}{a_1+b_j}\\
=\frac{a_i-a_1}{(a_1+b_j)(a_i+b_j)}
$$

每行可以提出 $a_i-a_1$,并且每列可以拿出来 $\dfrac{1}{a_1+b_j}$，这样的话第一行就全是 $1$，而下面的保持不变。

然后每一列减去第一列，除了第一行第一列，别的地方变成：

$$
c_{i,j}-c_{i,1}=\frac{1}{a_i+b_j}-\frac{1}{a_i+b_1}\\
=\frac{b_j-b_1}{(a_i+b_1)(a_i+b_j)}
$$

我们同样，提出 $b_j-b_1$ 和 $\dfrac{1}{a_i+b_1}$,注意这里 $i>1$ ，此时第一行只有 $c_{1,1}=1$ ，因此变成子问题。

归纳得到答案：

$$
|C|=\frac{\prod_{i<j}(a_j-a_i)(b_j-b_i)}{\prod_{i,j}(a_i+b_j)}
$$

> 对于可逆矩阵 $A$，求解行列式 $|A+x^Ty|$。

构造分块矩阵

$$
\begin{vmatrix}
A & x\\
y^T & 1
\end{vmatrix}
$$

就可以得到答案是 $|A|(1+y^TA^{-1}x)$。

> 有反对称矩阵 $A$，证明 $R(A)$ 一定是偶数。

可以做合同变换，保持秩不变。

归纳，对于 $n=2$，可以证明一定可以合同成：

$$
\begin{pmatrix}
0&1\\
-1 & 0
\end{pmatrix}
$$

然后对于 $n>2$ ，先通过交换，使得 $a_{1,2}\ne 0$ 。

得到分块矩阵：

$$
\begin{pmatrix}
A_1&A_2\\
-A_2^T&A_3
\end{pmatrix}
$$

其中 $A_1$ 可逆，然后对角化一下：

$$
\begin{pmatrix}
A_1& 0\\
0 &A_3+A_2^TA_1^{-1}A_2
\end{pmatrix}
$$

由于进行的是合同变换，右下角必然还满足是反对称矩阵，因此归纳成立。

最后对角化的结果一定是对角线上若干个 $\begin{pmatrix}
0&1\\
-1 & 0
\end{pmatrix}$ 和 $(0)$ ，因此秩是偶数。

> 已知 $A$ 的特征值：$\{\lambda_1,\lambda_2,...,\lambda_n\}$，求 $f(A)$ 的特征值。

根据定义：

$$
Ax=\lambda x\\
A^2x=\lambda Ax=\lambda^2x
$$

归纳可以证明 $f(A)x=f(\lambda)x$。

> 证明 $R(A)+R(I-A)=n$。

- $R(A)+R(B)\le n+R(AB)$

- $R(A)+R(B)\ge R(A+B)$

就可以简单证明。

也可以注意到，两者的零空间互补，如果在一个里面是非 $0$ 那么另一边一定是零向量。

所以是直和，然后就可以简单证明。

其本质是，幂等矩阵拆成了核空间和像空间。

> 设 $A, B$ 均为 $n$ 阶可对角化矩阵，且 $AB = BA$。
>
>证明：存在同一个可逆矩阵 $P$，使得 $P^{-1}AP$ 与 $P^{-1}BP$ 同时为对角阵。

也就是证明，$AB$ 有一组相同的特征向量。

$$
Ax=\lambda x\\
BAx=ABx=\lambda Bx
$$

也就是，$Bx\in V_{\lambda}$。

因此 $V_{\lambda}$ 是 $B$ 的不变子空间，所以在 $V_{\lambda}$ 内部可以找到一组特征向量，它们同时肯定也是 $A$ 的特征向量。