> This chapter discusses polygons, without using integrals or any kind of limit process.

## Cutting and pasting polygons

How do we prove that two polygons have the same area?

Here is a simple method: we cut the one into finitely many pieces, and then reassemble them into the other one.

First, we must define what we mean by "reassemble". We observe that the area of ​​a piece remains unchanged after the following three rigid motions: 

- Translation.

- rotation.

- reflection.

we can say that two such polygons are **scissors congruent**.

> Theorem: If two polygons have the same area, they are scissors congruent.

We can cut polygons into triangles, then transform them into a $1\times S$ rectangle.

---


We can use fewer transformations to achieve our goal.

The most important part of the processes is cutting the polygons into triangles. And we can do this using only transformation and rotation.

---

What about using only the translation? This might seems possible if we were allowed to cut the polygons into infinite pieces, each small enough to be treated as a point.

But we can only cut the polygons into finite pieces. In fact, it is generally impossible.

To prove it, the best way is to find an **invariant** that remains unchanged during the process.

We cut the polygon $P$ into two pieces, $P_1$ and $P_2$. There is an internal boundary in the $P$. Two pieces share these edges, but they have different directions. We can find a way to cancel them to keep our invariant.

For every unit vector $\vec w$, we define:

$$
\text{had}_{\vec w}(P)=\sum_{e\perp \vec w} \sigma(e) \text{length}(e)
$$

Let's define $\vec n$ is the outward normal of $e$. $\sigma(e)=\dfrac{\vec w|n|}{|w|\vec n}$.

Then for each $w$, we have

$$
\text{had}_w(P) = \text{had}_w(P_1) + \text{had}_w(P_2)
$$

So if two polygons have different $\text{had}_w(P)$, they can't be scissors congruent in the way that uses only translations.

Using inward and outward normal vectors is a clever way to define the invariant. It identifies the orientation of the edges without relying on a global clockwise or counter-clockwise order.

---

For every polygon $P$, let's set a direction for each edge so that Adjacent edges do not point at the same point. And each edge is transformed into a vector.

There is a simple fact :

$$
\sum_{\vec e \in P} \vec e = 0
$$

And if we define $\vec n$ as the vector that rotates the $\vec e$ 90 degrees clockwise. And $\vec n$ is still the outward normal of $\vec e$. We define this direction-setting method as "the counter-clockwise method".

Then, if two edges have opposite outward normals, they are opposite vectors in "the counter-clockwise method".

> Problem 1.10. Is it possible for a polygon to have exactly 2 nonzero Hadwiger invariants (corresponding to a single pair of opposite directions)? How about exactly 4 (two pairs of opposite directions)?

Let the distinct pairs of normal directions present in the polygon be $\{\vec u_1,\vec u_2,...,\vec u_k\}$.

Then we have:

$$
\sum \text{had}_{\vec w_i}(P) R(\vec w_i)=0
$$

Here, $R(\vec a)$ means the vector that rotates the $\vec a$ 90 degrees counter-clockwise.

This is because $\text{had}_{\vec w_i}(P)$ is the sum of length of edges whose outward normal is $\vec w_i$.

Then, we have :

$$
\sum \text{had}_{\vec w_i}(P) \vec w_i=0
$$

Therefore, it is impossible to have exactly 1 or 2 pairs.

## Integer polygons