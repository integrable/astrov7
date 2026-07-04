---
title: "AdS as a Spacetime"
description: "A first-principles introduction to Anti-de Sitter spacetime: embedding definition, global coordinates, curvature, cosmological constant, conformal boundary, and the geometric facts used throughout AdS/CFT."
sidebar:
  order: 10
---

We now cross from the field-theory side to the gravity side. The first object to understand is not a black hole, a string background, or a Witten diagram. It is the spacetime itself: Anti-de Sitter space, usually abbreviated AdS.

AdS/CFT is special because the bulk geometry is not arbitrary. Empty AdS is the gravitational dual of the vacuum state of a conformal field theory, and its symmetry group is exactly the conformal group of the boundary theory. In that sense, AdS is to holography what Minkowski space is to ordinary relativistic QFT: the maximally symmetric arena in which the first definitions are cleanest.

But AdS is not just “Minkowski space with negative curvature.” It has a timelike conformal boundary, a natural cylinder at infinity, a finite coordinate light-crossing time, and a radial direction that later becomes tied to energy scale. All of these features are essential for the holographic dictionary.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Anti-de Sitter spacetime viewed as an embedding-space hyperboloid, an intrinsic negatively curved spacetime, and a conformal boundary cylinder](/figures/course/ads-hyperboloid-boundary.svg)

<figcaption>

Three equivalent viewpoints on $\mathrm{AdS}_{d+1}$. It can be defined as a hyperboloid in $\mathbb{R}^{2,d}$, as a maximally symmetric solution of Einstein's equations with $\rho$ or $r$ as a radial coordinate, or by its conformal compactification whose boundary is the cylinder $\mathbb{R}_\tau\times S^{d-1}$ in global coordinates.

</figcaption>
</figure>

## Why this matters

On the CFT side, the vacuum on the cylinder $\mathbb{R}_\tau\times S^{d-1}$ is the most natural state produced by radial quantization. On the bulk side, the corresponding geometry is global AdS. This is already a nontrivial match:

$$
\text{CFT vacuum on }\mathbb{R}\times S^{d-1}
\quad
\longleftrightarrow
\quad
\text{global }\mathrm{AdS}_{d+1}.
$$

The same spacetime also admits Poincaré coordinates whose boundary is $\mathbb{R}^{1,d-1}$:

$$
\text{CFT vacuum on Minkowski space}
\quad
\longleftrightarrow
\quad
\text{Poincaré patch of }\mathrm{AdS}_{d+1}.
$$

These are not different dualities. They are different coordinate and conformal-frame descriptions of the same basic geometry. CFTs are naturally sensitive to conformal classes of boundary metrics, not just one chosen representative metric.

The first geometric facts to internalize are:

- $\mathrm{AdS}_{d+1}$ is a Lorentzian spacetime of constant negative curvature.
- Its isometry group is $SO(2,d)$, matching the conformal group of a $d$-dimensional CFT.
- Its boundary is not an ordinary finite-distance surface; it is a conformal boundary reached after rescaling the metric.
- In global coordinates, that boundary is $\mathbb{R}\times S^{d-1}$.
- In Poincaré coordinates, the boundary looks like Minkowski space.
- The radial direction is geometric in the bulk but becomes associated with scale in the boundary theory.

This page builds these facts carefully.

## Definition by embedding

A compact way to define $\mathrm{AdS}_{d+1}$ is as a hyperboloid embedded in a flat auxiliary space $\mathbb{R}^{2,d}$ with coordinates

$$
X^A=(X_{-1},X_0,X_1,\ldots,X_d)
$$

and metric

$$
ds^2_{\mathbb{R}^{2,d}}
=
-dX_{-1}^2-dX_0^2+dX_1^2+\cdots+dX_d^2.
$$

The notation $\mathbb{R}^{2,d}$ means that the embedding space has two timelike directions and $d$ spacelike directions. Anti-de Sitter spacetime is the hypersurface

$$
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2.
$$

The parameter $L$ is the AdS radius. It sets the curvature scale. If $L$ is large compared with every microscopic length scale in the bulk theory, then the spacetime is weakly curved.

This embedding definition is useful because the symmetry group is immediate. The flat metric of $\mathbb{R}^{2,d}$ is preserved by $O(2,d)$, and the hyperboloid equation is also preserved by the same group. The identity-connected orientation-preserving part is usually denoted $SO(2,d)$ or $SO_0(2,d)$ depending on how much precision is needed. This is the geometric origin of the group match

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})\simeq SO(2,d),
$$

which is also the conformal group of $d$-dimensional Minkowski space for $d>2$.

A warning: the two timelike directions belong to the embedding space, not to the physical tangent space of AdS. The induced metric on the hyperboloid has one timelike direction and $d$ spacelike directions. AdS is a Lorentzian spacetime, not a two-time physical spacetime.

## Global coordinates

The hyperboloid constraint is solved by the global coordinates

$$
X_{-1}=L\cosh\rho\cos\tau,
$$

$$
X_0=L\cosh\rho\sin\tau,
$$

$$
X_i=L\sinh\rho\, n_i,
\qquad
\sum_{i=1}^d n_i^2=1.
$$

Here $n_i$ parameterize a unit $S^{d-1}$, the radial coordinate satisfies $\rho\ge 0$, and $\tau$ is dimensionless global time. Substituting into the flat embedding metric gives

$$
ds^2
=
L^2\left(
-\cosh^2\rho\, d\tau^2
+d\rho^2
+\sinh^2\rho\, d\Omega_{d-1}^2
\right).
$$

If we introduce dimensionful time $t=L\tau$ and radial coordinate

$$
r=L\sinh\rho,
$$

then the same metric becomes

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2.
$$

This is the standard global AdS metric. The coordinate $r=0$ is the center of AdS, and $r\to\infty$ is the conformal boundary.

A few features are worth noticing immediately. First, at large $r$,

$$
g_{tt}\sim -\frac{r^2}{L^2},
\qquad
 g_{rr}\sim \frac{L^2}{r^2}.
$$

Second, spatial slices at fixed $t$ have topology $\mathbb{R}^d$, described by a radial direction times $S^{d-1}$. Third, the asymptotic sphere does not shrink or disappear; after an appropriate conformal rescaling it becomes the spatial sphere of the boundary CFT.

## The universal cover

The embedding coordinates use $\tau$ through $\sin\tau$ and $\cos\tau$, so the hyperboloid itself identifies

$$
\tau\sim \tau+2\pi.
$$

But the curve at fixed $\rho$ and fixed point on $S^{d-1}$ is timelike, since

$$
ds^2=-L^2\cosh^2\rho\,d\tau^2.
$$

If $\tau$ is periodic, these curves are closed timelike curves. That is not the spacetime usually used in AdS/CFT.

The physical object called global AdS is almost always the **universal cover** of the hyperboloid, obtained by unwrapping $\tau$ so that

$$
\tau\in\mathbb{R}
$$

rather than $\tau\in S^1$. In this course, $\mathrm{AdS}_{d+1}$ means this universal cover unless stated otherwise.

This is a common place where the embedding picture can mislead. The hyperboloid is an elegant definition of the local geometry and the symmetry group, but for causal physics one should remember the universal cover.

## Curvature and negative cosmological constant

AdS is maximally symmetric. With the curvature conventions of this course, its Riemann tensor is

$$
R_{MNPQ}
=
-\frac{1}{L^2}
\left(
 g_{MP}g_{NQ}-g_{MQ}g_{NP}
\right),
$$

where $M,N,\ldots$ are bulk indices. Contracting gives

$$
R_{MN}
=
-\frac{d}{L^2}g_{MN},
$$

and

$$
R
=
-\frac{d(d+1)}{L^2}.
$$

Thus AdS has constant negative scalar curvature. In $(d+1)$-dimensional Einstein gravity with cosmological constant, the vacuum equation is

$$
R_{MN}-\frac12 Rg_{MN}+\Lambda g_{MN}=0.
$$

Substituting the AdS curvature gives

$$
\Lambda=-\frac{d(d-1)}{2L^2}.
$$

So AdS is the maximally symmetric vacuum of Einstein gravity with negative cosmological constant.

This statement is simple, but it carries an important conceptual distinction. Negative cosmological constant is not the same as negative energy density in the boundary CFT. The cosmological constant is a parameter in the bulk gravitational equations. The boundary vacuum energy depends on the CFT, the background geometry, and renormalization scheme; for a CFT on a cylinder, there can be a Casimir energy.

## Conformal compactification

The AdS boundary lies at $r\to\infty$ or equivalently $\rho\to\infty$. The proper radial distance from finite $\rho$ to infinity is infinite, since

$$
\int^{\infty} L\,d\rho=\infty.
$$

So the boundary is not an ordinary surface at finite proper distance. Nevertheless, it can be brought to finite coordinate distance by a conformal compactification.

Define a compact radial coordinate $\chi$ by

$$
\tan\chi=\sinh\rho,
\qquad
0\le \chi < \frac{\pi}{2}.
$$

Then

$$
\cosh\rho=\frac{1}{\cos\chi},
\qquad
\sinh\rho=\tan\chi,
\qquad
 d\rho=\frac{d\chi}{\cos\chi}.
$$

The global AdS metric becomes

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

The conformal boundary is at

$$
\chi=\frac{\pi}{2}.
$$

The metric diverges there because of the factor $L^2/\cos^2\chi$. But if we multiply by the conformal factor

$$
\Omega^2=\frac{\cos^2\chi}{L^2},
$$

we obtain the rescaled metric

$$
d\tilde s^2
=
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2.
$$

Restricting to $\chi=\pi/2$ gives the boundary metric representative

$$
ds^2_{\partial}
=
-d\tau^2+d\Omega_{d-1}^2.
$$

Thus the conformal boundary of global $\mathrm{AdS}_{d+1}$ is

$$
\mathbb{R}_\tau\times S^{d-1}.
$$

This is exactly the spacetime on which radial quantization naturally places the CFT.

## The boundary metric is a conformal class

The previous derivation produced one boundary metric,

$$
g_{(0)}=-d\tau^2+d\Omega_{d-1}^2.
$$

But the choice of conformal factor was not unique. If $\bar\Omega=e^{\omega(x)}\Omega$, then the boundary representative changes by a Weyl rescaling:

$$
g_{(0)}\to e^{2\omega(x)}g_{(0)}.
$$

For this reason, the natural boundary datum of asymptotically AdS geometry is not a single metric but a conformal class

$$
[g_{(0)}].
$$

This is a perfect match with conformal field theory: a CFT can be placed on a background metric, but local Weyl rescalings are part of the conformal structure, up to possible anomalies in even boundary dimension.

In later pages, this statement becomes operational. The boundary metric $g_{(0)\mu\nu}$ acts as the source for the CFT stress tensor $T^{\mu\nu}$:

$$
\delta W[g_{(0)}]
=
\frac12\int d^dx\sqrt{|g_{(0)}|}\,
\langle T^{\mu\nu}\rangle\,
\delta g_{(0)\mu\nu}.
$$

On the bulk side, $g_{(0)\mu\nu}$ is the leading coefficient in the asymptotic expansion of the bulk metric.

## A first look at the Poincaré patch

Global coordinates make the full cylinder boundary visible. The coordinate system most commonly used for computations is the Poincaré patch:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+
\eta_{\mu\nu}dx^\mu dx^\nu
\right),
\qquad
z>0,
$$

where

$$
\eta_{\mu\nu}dx^\mu dx^\nu
=
-dt^2+d\vec x^{\,2}.
$$

The boundary is at $z=0$. After multiplying by $z^2/L^2$, the induced boundary metric is just the Minkowski metric:

$$
ds^2_{\partial}=\eta_{\mu\nu}dx^\mu dx^\nu.
$$

The Poincaré patch does not cover all of global AdS. It covers the region naturally adapted to a CFT on flat Minkowski space. The coordinate $z\to\infty$ is not the global center of AdS; it is a Poincaré horizon.

This metric makes the scale interpretation of the radial coordinate especially transparent. It is invariant under

$$
x^\mu\to \lambda x^\mu,
\qquad
z\to \lambda z.
$$

A boundary scale transformation must be accompanied by a rescaling of the radial coordinate. This is the seed of the UV/IR relation:

$$
\text{near boundary } z\to 0
\quad\longleftrightarrow\quad
\text{UV of the boundary theory},
$$

while deeper regions of the bulk correspond roughly to lower energy scales.

We will study coordinate systems systematically in the next page. For now, the point is that global and Poincaré coordinates answer different physical questions:

| Bulk coordinates | Boundary frame | Natural use |
|---|---|---|
| global AdS | $\mathbb{R}\times S^{d-1}$ | Hilbert space, states, spectrum |
| Poincaré AdS | $\mathbb{R}^{1,d-1}$ | local correlators, flat-space CFT |
| Fefferman–Graham | arbitrary boundary metric | holographic renormalization |
| Eddington–Finkelstein | black branes and horizons | real-time dynamics |

## AdS is a gravitational box

In asymptotically flat spacetime, outgoing radiation can escape to null infinity. In global AdS, light reaches the boundary in finite global time.

Using the compactified metric

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2
\right),
$$

consider a radial null ray with $d\Omega_{d-1}=0$. The null condition gives

$$
-d\tau^2+d\chi^2=0,
$$

so

$$
\frac{d\chi}{d\tau}=\pm 1.
$$

A radial light ray starting at the center $\chi=0$ reaches the boundary $\chi=\pi/2$ in

$$
\Delta\tau=\frac{\pi}{2}.
$$

This is finite global coordinate time. If the boundary reflects the signal, it returns to the center after another interval $\pi/2$.

This “box” property is part of why thermal equilibrium in AdS is natural. It is also why boundary conditions at infinity are not optional. A field theory in AdS is not fully specified until one states what fields are allowed to do at the timelike boundary.

In holography, those boundary conditions are not arbitrary technical details. They are the sources, states, and deformations of the boundary theory.

## Boundary conditions and dynamics

Because the conformal boundary of AdS is timelike, AdS is not globally hyperbolic in the same way Minkowski space is. Initial data on a bulk Cauchy slice do not determine future evolution unless one also specifies boundary conditions at infinity.

This is not a pathology for holography. It is the point.

For a scalar field $\phi$ in AdS, one must specify its allowed near-boundary behavior. Later we will see that near $z=0$ the scalar behaves schematically as

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x).
$$

The leading coefficient $\phi_{(0)}(x)$ is interpreted as the source for a CFT operator $\mathcal O(x)$, while the subleading coefficient is related to the expectation value $\langle\mathcal O(x)\rangle$ after holographic renormalization.

Thus the same mathematical feature that makes AdS require boundary conditions is also what makes it holographic: the boundary behavior of bulk fields is boundary QFT data.

## Energy, redshift, and the radial direction

The global AdS metric

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2
$$

has a timelike Killing vector $\partial_t$. A static observer at radius $r$ has proper time

$$
d\tau_{\mathrm{proper}}
=
\sqrt{1+\frac{r^2}{L^2}}\,dt.
$$

Therefore an energy measured with respect to the global time $t$ differs from a local proper energy. Near the boundary, the redshift factor becomes large.

In the Poincaré patch, the corresponding intuition is even sharper. The metric

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2-dt^2+d\vec x^{\,2}\right)
$$

contains an overall warp factor $L^2/z^2$. A fixed proper length in the bulk projects to a boundary length scale controlled by $z$. Small $z$ is associated with short-distance boundary physics; large $z$ is associated with long-distance boundary physics.

This relation is often summarized as the UV/IR connection. It should be treated as a guiding principle, not as a literal equality between $z$ and an RG scale in every coordinate system.

## Units and normalization

In this course, $L$ will often be set to one in intermediate calculations. Restoring it is usually straightforward by dimensional analysis. For example, the curvature tensors are

$$
R_{MNPQ}
\sim
\frac{1}{L^2},
\qquad
R_{MN}
\sim
\frac{1}{L^2},
\qquad
R
\sim
\frac{1}{L^2}.
$$

A dimensionless bulk mass is written as

$$
m^2L^2,
$$

and the scalar mass-dimension relation will later be

$$
m^2L^2=\Delta(\Delta-d).
$$

The ratio $L/\ell_s$, where $\ell_s=\sqrt{\alpha'}$, controls stringy curvature corrections. The ratio $L^{d-1}/G_N$ controls the strength of bulk quantum gravity effects. This is why the AdS radius is not merely a coordinate scale: it measures the separation between the curvature scale and microscopic bulk scales.

## Dictionary checkpoint

The geometric statements of this page already contain several entries of the holographic dictionary.

| Bulk statement | Boundary statement |
|---|---|
| $\mathrm{AdS}_{d+1}$ has isometry group $SO(2,d)$ | the vacuum CFT has conformal group $SO(2,d)$ |
| global AdS boundary is $\mathbb{R}\times S^{d-1}$ | the CFT Hilbert space is naturally defined on the cylinder |
| Poincaré AdS boundary is $\mathbb{R}^{1,d-1}$ | the CFT can be studied on Minkowski space |
| radial coordinate approaches boundary | boundary UV region |
| timelike AdS boundary requires boundary conditions | CFT sources and deformations must be specified |
| boundary metric is a conformal class $[g_{(0)}]$ | CFT data are naturally conformal, up to anomalies |
| $L$ sets curvature scale | $L$ controls the relation between bulk curvature and CFT parameters |

The most important takeaway is this:

$$
\text{the CFT does not live inside AdS; it lives on the conformal boundary of AdS.}
$$

## Common confusions

### “AdS has two times because $\mathbb{R}^{2,d}$ has two times.”

The two times are in the auxiliary embedding space. The induced metric on the AdS hyperboloid is Lorentzian, with one physical time direction. The embedding is a mathematical construction, not an assertion that the physical bulk has two time dimensions.

### “The boundary is at finite distance because the Penrose diagram has finite width.”

The conformal boundary is at finite coordinate distance only after a conformal rescaling. The proper distance to the boundary is infinite. This is why the boundary is not an ordinary wall, even though diagrams often draw it as a finite line or cylinder.

### “Global AdS and Poincaré AdS are different spacetimes.”

Poincaré AdS is a coordinate patch of global AdS. The corresponding boundary conformal frames are different: the global frame is the cylinder, while the Poincaré frame is Minkowski space. The choice depends on the question being asked.

### “Negative curvature means the spacetime is unstable.”

Constant negative curvature by itself does not imply instability. AdS is the maximally symmetric vacuum of gravity with negative cosmological constant. Stability questions require specifying matter content, boundary conditions, and allowed perturbations. For scalar fields, for example, AdS allows certain negative $m^2$ values without instability, as long as the Breitenlohner–Freedman bound is satisfied.

### “The boundary metric is uniquely determined.”

The natural boundary datum is a conformal class of metrics. Choosing one representative, such as $-d\tau^2+d\Omega_{d-1}^2$ or $\eta_{\mu\nu}dx^\mu dx^\nu$, is a choice of conformal frame.

## Exercises

### Exercise 1: Verify the hyperboloid constraint

Show that the global coordinate parameterization

$$
X_{-1}=L\cosh\rho\cos\tau,
\qquad
X_0=L\cosh\rho\sin\tau,
\qquad
X_i=L\sinh\rho\,n_i
$$

with $\sum_i n_i^2=1$ obeys

$$
-X_{-1}^2-X_0^2+\sum_{i=1}^d X_i^2=-L^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the coordinates:

$$
-X_{-1}^2-X_0^2
=
-L^2\cosh^2\rho(\cos^2\tau+\sin^2\tau)
=
-L^2\cosh^2\rho.
$$

Also,

$$
\sum_{i=1}^d X_i^2
=
L^2\sinh^2\rho\sum_{i=1}^d n_i^2
=
L^2\sinh^2\rho.
$$

Therefore

$$
-X_{-1}^2-X_0^2+\sum_iX_i^2
=
-L^2\cosh^2\rho+L^2\sinh^2\rho
=
-L^2,
$$

using $\cosh^2\rho-\sinh^2\rho=1$.

</details>

### Exercise 2: Derive the global AdS metric

Using the same embedding coordinates, show that the induced metric is

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+
\sinh^2\rho\,d\Omega_{d-1}^2
\right).
$$

<details>
<summary><strong>Solution</strong></summary>

For the two embedding-time coordinates,

$$
X_{-1}=L\cosh\rho\cos\tau,
\qquad
X_0=L\cosh\rho\sin\tau.
$$

Their contribution is

$$
-dX_{-1}^2-dX_0^2
=
-L^2\sinh^2\rho\,d\rho^2
-L^2\cosh^2\rho\,d\tau^2.
$$

For the spatial embedding coordinates $X_i=L\sinh\rho\,n_i$, with $n_i n_i=1$, one has $n_i dn_i=0$ and

$$
\sum_i dX_i^2
=
L^2\cosh^2\rho\,d\rho^2
+L^2\sinh^2\rho\,d\Omega_{d-1}^2.
$$

Adding the two pieces gives

$$
ds^2
=
L^2(\cosh^2\rho-\sinh^2\rho)d\rho^2
-L^2\cosh^2\rho\,d\tau^2
+L^2\sinh^2\rho\,d\Omega_{d-1}^2.
$$

Since $\cosh^2\rho-\sinh^2\rho=1$, this becomes

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+
\sinh^2\rho\,d\Omega_{d-1}^2
\right).
$$

</details>

### Exercise 3: Find the boundary cylinder

Starting from

$$
ds^2
=
L^2\left(
-\cosh^2\rho\,d\tau^2+d\rho^2+
\sinh^2\rho\,d\Omega_{d-1}^2
\right),
$$

use $\tan\chi=\sinh\rho$ to show that the conformal boundary metric is

$$
ds_{\partial}^2=-d\tau^2+d\Omega_{d-1}^2.
$$

<details>
<summary><strong>Solution</strong></summary>

If $\tan\chi=\sinh\rho$, then

$$
\cosh^2\rho=1+\sinh^2\rho=1+\tan^2\chi=\frac{1}{\cos^2\chi},
$$

and

$$
d\rho=\frac{d\chi}{\cos\chi}.
$$

Also,

$$
\sinh^2\rho=\tan^2\chi=\frac{\sin^2\chi}{\cos^2\chi}.
$$

Therefore

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+
\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

Multiplying by $\Omega^2=\cos^2\chi/L^2$ gives a finite rescaled metric. Restricting to the boundary $\chi=\pi/2$ gives $\sin\chi=1$, so

$$
ds_{\partial}^2=-d\tau^2+d\Omega_{d-1}^2.
$$

</details>

### Exercise 4: Determine the cosmological constant

Assume

$$
R_{MN}=-\frac{d}{L^2}g_{MN},
\qquad
R=-\frac{d(d+1)}{L^2}
$$

in $(d+1)$ bulk dimensions. Use the vacuum Einstein equation

$$
R_{MN}-\frac12 Rg_{MN}+\Lambda g_{MN}=0
$$

to derive $\Lambda$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the curvature tensors:

$$
-\frac{d}{L^2}g_{MN}
-
\frac12\left(-\frac{d(d+1)}{L^2}\right)g_{MN}
+
\Lambda g_{MN}=0.
$$

The coefficient of $g_{MN}$ is

$$
-\frac{d}{L^2}
+
\frac{d(d+1)}{2L^2}
+
\Lambda
=
\frac{d(d-1)}{2L^2}+\Lambda.
$$

Therefore

$$
\Lambda=-\frac{d(d-1)}{2L^2}.
$$

</details>

### Exercise 5: Light reaches the boundary in finite global time

For radial null motion in compactified global AdS,

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2
\right),
$$

show that a light ray starting at the center reaches the boundary in $\Delta\tau=\pi/2$.

<details>
<summary><strong>Solution</strong></summary>

For a null ray, $ds^2=0$. The overall conformal factor does not affect the null condition, so

$$
-d\tau^2+d\chi^2=0.
$$

Thus

$$
\frac{d\chi}{d\tau}=\pm1.
$$

The center is at $\chi=0$, and the boundary is at $\chi=\pi/2$. For an outgoing radial light ray,

$$
\Delta\tau=\int_0^{\pi/2}d\chi=\frac{\pi}{2}.
$$

</details>

## Further reading

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111), especially the review of AdS geometry.
- M. Henneaux and C. Teitelboim, [Asymptotically anti-de Sitter Spaces](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-98/issue-3/Asymptotically-anti-de-Sitter-spaces/cmp/1103942454.full), for the role of asymptotic conditions.
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067), for the Fefferman–Graham and boundary-metric viewpoint.
