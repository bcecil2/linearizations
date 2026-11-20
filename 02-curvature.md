# The Many Faces of Curvature

Curvature comes in many varieties, some easier to get our hands on than others. A math pupils experience of learning, is akin to the acolyte being inducted into the mysteries of a cult. The gaussian curvature of a surface is accessible to anyone who has gone skiing, go off a hill and you will land somewhere, the more curved the hill is the further down you will land. By the time one is talking about the Riemann curvature Tensor it is no longer so obvious what curvature should mean, but we will always grasp onto this vague sense that it is telling us how much space "bends".

# The Guassian Curvature of a Surface

Let $S$ be a surface in 3 space, for every point we have an open neighborhood and a parameterization by some function $s(u,v) = (x(u,v), y(u,v), z(u,v))$. The parametrization gives us a basis for the tangent space for points in that neighborhood given by the coordinate vectors

```{math}
\begin{align*}
\mathbf{x}_u &= \langle x_u, y_u, z_u \rangle\\
\mathbf{x}_v &= \langle x_v, v_z, z_v \rangle\\
\end{align*}
```

The inner product of the ambient space induces an inner product on the tangent spaces which controls the geometry of the surface.

```{proof:definition}
Let $\mathbf{x}_u, \mathbf{x}_v$ form a basis for the tangent space of a surface at a point p, then the
**coefficients of the first fundamental form** are

\begin{align*}
E &= \langle \mathbf{x}_u, \mathbf{x}_u \rangle\\
F &= \langle \mathbf{x}_u, \mathbf{x}_v \rangle = \langle \mathbf{x}_v, \mathbf{x}_u \rangle\\
G &= \langle \mathbf{x}_v, \mathbf{x}_v \rangle\\
\end{align*}
```
This means that for any vector written in this basis $\mathbf{w} = \langle a , b \rangle$ its length is given by

```{math}
||\mathbf{w}|| = Ea^2 + Fab + Gb^2
```

The form lets us compute geometric quantites on our surface, for instance suppose we have a curve $\alpha(t) = \mathbf{x}(u(t),v(t))$ for some parameterization then we can find its arc length by
```{math}
\int_0^1 ||a'(t)||dt = \int_0^1 \sqrt{E(u,v)u'(t)^2 + 2Fu'(t)v'(t) + G(u,v)v'(t)^2}dt
```

```{proof:example}
Parameterize the sphere with coordinates $\theta,\phi$ with theta the angle from the z axis and phi the angle of rotation around the origin. Then consider the curve given by $\theta(t) = \pi $ and $\phi(t) = t$ 
$$
    \alpha(t) = x(\pi,t) = (-\cos \phi, -sin \phi, 0 )
$$

Then $\theta'(t) = 0$ and $\phi'(t) = 1$, and $E = 1, F = 0, G = \sin^2 \theta$ and its arc length is
\begin{align*}
\int_{0}^{2 \pi} \sqrt{G(\theta(t), \phi(t)) \phi'(t)^2} dt &= \int_{0}^{2 \pi} \sqrt{\sin^2(\pi) 1} dt\\ 
&= \int_{0}^{2\pi} dt\\
&= 2\pi
\end{align*}

as expected since the curve corresponds to the great circle around the equator.
```

Another geometric quantity of fundamental importance is the area of regions within our surface. One way of defining the integral over the surface is to retreat to the coordinate patch and integrate

```{proof:definition}
Surface integral over a bounded region $R \subset S$ contained in a parameterization $x: U \subset \mathbb{R}^2 \rightarrow S$, is defined by integrative in $u,v$ coordinates over the region $Q = x^{-1}(R)$

$$
\iint_Q ||x_u \times x_v|| du \ dv = \iint_Q \sqrt{EG - F^2} du \ dv 
$$
```

This magic formula appears in standard vector calculus courses, the coefficients of the metric offers the correct explanation why for surfaces. For surfaces without a metric, one needs differential forms. However on a riemannian manifold the volume form can be written as the determinant of matrix formed by applying the metric to a basis, which is exactly what we have done here.


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

Each $\Omega^i_j$ is a two form and collecting them in a matrix produces the **curvature matrix**. Since the curvature is defined in terms of the connection we would hope the curvature matrix should be related to the connection forms. Miracuously this is true. In order to state it as elegantly as possibly we breifly remark that for matrices of forms $A,B$ we define $A \wedge B$ as the matrix obtained as through the usual row column products, except the product is replaced with $\wedge$ 

```{proof:theorem}
Let $\nabla$ be a connection on a rank $d$ vector bundle $E \rightarrow M$. Then on a frame $e_1,...,e_n$ for a trivializing set $U$ the curvature forms are given by the second structural equation 

$$
\Omega = d\omega + \omega \wedge \omega
$$
```



