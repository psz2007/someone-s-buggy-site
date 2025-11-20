---
layout: default
title: 导数与微分
sort_order: 1
is_note: true
---

## 定义

一个点可微分，就是说对于函数 $f(x)$ 的 $f(x_0)$ ，存在一个函数 $g(x)$，满足

$$
df(x_0)=dxg(x_0)+o(dx)
$$

可导就是

$$
f'(x_0)=\lim_{d\to 0}\frac{f(x+d)-f(x)}{d}
$$

不难发现两者等价。

各种求导公式和四则运算啥的都会，背下来就行。

## 隐函数求导

实际上就是一个两边同时求导的 trick。

>$$
>e^{xy}+x^2y-1=0
>$$
>
>求 $\dfrac{\text{d}y}{\text{d}x}$

注意 $y$ 会跟着 $x$ 变，所以可以把 $y$ 看成 $f(x)$，然后左右同时求导即可。

$$
e^{xy}(y+xy')+2xy+x^2y'=0\\
y'=\frac{-ye^{xy}-2xy}{x^2+xe^{xy}}
$$

## 对数求导法

$$
(\ln f(x))'=\frac{f'(x)}{f(x)}\\
f'(x)=(\ln f(x))'f(x)
$$

如果 $f$ 形如 $x^x$ 就可以直接这样搞。