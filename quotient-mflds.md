
# Quotients, Actions, and Manifolds

Quotient constructions abound in mathematics. Benedict Gross' excellent lectures on algebra are where I first learned why. Let $f: X \rightarrow Y$ be a function on bare sets. Then we can define an equivalence relation on $X$ as $x \sim  y \iff f(x) = f(y)$. Then the fibers of $f$ are the equivalence classes and now by construction the function 

```{math}
\begin{align*}
f: X/\sim &\rightarrow Y\\
    f([x]) &= f(x)
\end{align*}
```
is injective! 

Because this is such a natural thing to want every structure has some notion of quotients that play an essential role in the theory. However our quotients should respect the structure of the objects at play. Group theory is again instructive, we only allow normal subgroups as quotients because they turn the quotient into a group itself. 

In the same spirit if we are considering quotients of manifolds (smooth or topological) then we should want our quotient space to remain a manifold. Recall that a manifold is a second countable, locally euclidean, **Hausdorff space**. The bold is no mistake dear reader, because quotients generically collapse space we are very often in danger of destroying the Hausdorfness of the underlying manifold.

There are conditions on equivalence relations that repair this but by far the most useful and common scenario is when the quotient arises from a group action.
```{proof:definition}
Let $M$ be a smooth manifold and $G$ a Lie group with a right(left) action. Declare $x \sim y \iff y = xG$ then the equivalence classes are the orbits 
```{math}
[x] = \{xg \ | \ g \in G \}
```

and we have a map 
```{math}
\begin{align*}
    \pi: M &\rightarrow M / G \\
    \pi(x) &= [x]\\
\end{align*}
```

We have a nice theorem that tells us when $M/G$ is itself a smooth manifold

```{proof:theorem}
Let $M$ be a smooth manifold and $G$ a compact Lie group with a smooth right(left) action. If $G$ acts freely then $M/G$ is a smooth manifold with dimension $\text{dim} \ M - \text{dim} \ G$ and each fiber has dimension $\text{dim} \ G$
```

Please note that here I have assumed that $G$ is compact, which allows us to drop the requirement that it acts properly on $M$.
The following example is incredibly instructive


```{proof:example}
Let $M = \mathbb{R}^2/\mathbf{0}$ and let $G = SO(2)$ act on the right, that this is an action and that it is smooth follows immediately from the properties of matrix multiplication. 


To verify that $G$ acts freely we must show that 
$$
    xg = x \implies g = I
$$
Recalling that every element of $G$ is a rotation this follows immediately since no vector is fixed by a non trivial rotation (except for the zero vector, hence the definition of $M$!).

$G$ is compact (in fact it is the circle) so it acts properly and the quotient is itself a smooth manifold of dimension 1. Meditating on the geometry of the situation allows us to easily characterize the orbits.

$$
x \sim y \iff ||x|| = ||y||
$$

To see the forward direction note that if $x \sim y$ then they are related by an element of $SO(2)$ which is an isometry hence the norms are the same. Going the other way we know they lie on the same circle so simply consider the angle between them and transform $x$ to $y$ by rotation by that angle which is in $SO(2)$.

This suggests the following map

\begin{align*}
f M/G &\rightarrow (0,\infty)\\
f([x]) &= ||x||
\end{align*}

This map is well defined since we have already show vectors in the same equivalence class have the same norm, it is a surjection because if $x = (r,0)$ then $f([x]) = r$ for any $r > 0$. And it is injective since any vectors of the same norm belong to the same orbit. So we actually have a diffeomorphism,

$$
    M/G \cong_{\text{diffeo}} (0,\infty)
$$

Once we know this we can also write down the projection map in an easy to understand way
\begin{align*}
    \pi:  M &\rightarrow (0,\infty)\\
    \pi(x,y) &= \sqrt{x^2 + y^2}
\end{align*}
```
