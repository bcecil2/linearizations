# The Many Faces of Curvature

Curvature comes in many varieties, some easier to get our hands on than others. A math pupils experience of learning, is akin to the acolyte being inducted into the mysteries of a cult. The gaussian curvature of a surface is accessible to anyone who has gone skiing, go off a hill and you will land somewhere, the more curved the hill is the further down you will land. By the time one is talking about the Riemann curvature Tensor it is no longer so obvious what curvature should mean, but we will always grasp onto this vague sense that it is telling us how much space "bends".

# The Guassian Curvature of a Surface

# The Connection form and Curvature 2-Forms

Let $\pi: V \rightarrow M$ be a vector bundle of rank $d$ over a smooth manifold $M$ also of rank $d$ (One should always have in mind here the tangent bundle $TM$). Then the Riemannian connection grows up into something that differentiates sections of $V$ rather than vector fields on $M$. More precisely

```{math}
\begin{align*}
\nabla&: \mathfrak{X}(M) \times \Gamma(V) \rightarrow \Gamma(V)\\
\end{align*} 
```

We require this mysterious new object to satsify the properites of the Riemannian connection that you know and that I trust you love. Most importantly the Liebniz rule

```{math}
\begin{align*}
\nabla_{X} fs = (Xf)s + f\nabla_{X} s
\end{align*}
```
for any $f \in C^{\infty}(M)$


Now consider a subset $U$ in $V$ then we have a trivialization with a frame $e_1,...,e_n$, and any section $s$ can then be expressed as 
$$
    s(p) = \sum a^i(p)e_i 
$$

Then we can compute the following

```{math}
\begin{align*}
\nabla_X s &= \sum_n \nabla_X a^ie_i\\
&= \sum_n (X a^i)e_i + \nabla_X e_i  \  \text{ by the Liebniz rule}\\
\end{align*}
```

Which means that any section can be understood locally by understanding the connection on the frame. Notice however that if we fix an $X$ then the connection is a linear map from sections to sections so it can in turn be expressed in terms of the frame

```{math}
\nabla_X e_j = \sum_i \omega^i_j(X) e_i
```

We have written the coefficient in an evocative way, the linearity of the conncetion implies that $\omega$ is a linear function of tangent vectors and hence a one form. The matrix
$$
\omega = [\omega^i_j]
$$ 
is a matrix of one forms called the **connection matrix**.

Let $R(X,Y)$ be the Riemannian curvature, then we can play a similar game and define
```{math}
R(X,Y)e_j = \sum_i \Omega^i_j(X,Y) e_i
```

Each $\Omega^i_j$ is a two form and collecting them in a matrix produces the **curvature matrix**. Since the curvature is defined in terms of the connection we would hope the curvature matrix should be related to the connection forms. Miracuously this is true. In order to state it as elegantly as possibly we breifly remark that for matrices of forms $A,B$ we define $A \wedge B$ as the matrix obtained as through the usual row column products, except the product is replace with $\wedge$ 

```{proof:theorem}
Let $\nabla$ be a connection on a rank $d$ vector bundle $E \rightarrow M$. Then on a frame $e_1,...,e_n$ for a trivializing set $U$ the curvature forms are given by the second structural equation 

$$
\Omega = d\omega + \omega \wedge \omega
$$
```



