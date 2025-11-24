---
layout: default
title: 数数垃圾桶
sort_order: 1
is_note: true
---

记录一些想不到的神秘东西。

### [CF1838E](https://codeforces.com/problemset/problem/1838/E)

看到题我直接写出答案式子

$$
\sum_{i=n}^m \binom{i-1}{n-1}(K-1)^{i-n}K^{m-i} 
$$

就是枚举预订的子序列匹配位置，然后去填。

类似二项式定理的东西想半天不会做。

然后想了一些非常神秘的，限定当前匹配方案不是最前匹配方案的容斥，完全没用。

最后的容斥，非常简单，先总方案是 $K^m$，然后我们限定没有匹配完，如果只匹配了 $i(i<n)$ 个位置，那么选 $i$ 个位置之后剩下地方方案数就全是 $K-1$。

答案直接就是：

$$
K^m-\sum_{i=0}^{n-1}\binom{m}{i}(K-1)^{m-i}
$$

然后在做开始错误的做法的时候，还发现一个神秘的组合式子：

$$
\sum_{i=0}^m a^i\binom{n+i}{n}
$$

这个东西做起来非常神秘，它需要观察到：

$$
\frac{d^n}{da^n} a^m=n!\binom{m}{n}a^{m-n}\\
\sum_{i=0}^m a^i\binom{n+i}{n}=\frac{1}{n!}\times \frac{d^n}{da^n} \sum_{i=0}^{n+m}a^i
$$

最后把等比数列求和变成分式，莱布尼茨法则展开成 $n$ 项即可。

---

>对于任意 $i\in [0,n-2]$，证明：
>$$
>\sum_{m=0}^{n-1}\binom{n-1}{m} (-1)^m (n-m)^i=0
>$$

这个式子看上去非常抽象，实际上是个观察题：

$$
\Delta F(x)=F(x)-F(x-1)\\
\Delta^{n-1}F(n)=\sum_{m=0}^{n-1}\binom{n-1}{m} (-1)^m F(n-m)
$$

$F$ 是 $i$ 次多项式，差分 $n-1$ 次后肯定变成 $0$ 。