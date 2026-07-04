---
title: "AdS Coordinate Systems"
description: "A compact coordinate atlas for Anti-de Sitter spacetime: embedding, global, Poincare, Euclidean, Fefferman-Graham, domain-wall, black-brane, Eddington-Finkelstein, and hyperbolic coordinates."
sidebar:
  order: 30
---

This appendix is a coordinate atlas for the AdS geometries used throughout the course. It is deliberately practical. The same spacetime can look like a cylinder, a half-space, a black hole exterior, or a radial RG flow depending on the coordinates. The physics is invariant; the coordinate system chooses the questions that are easy to ask.

Two warnings prevent most mistakes.

First, **the AdS boundary is conformal data**, not an ordinary finite-distance wall. A coordinate system usually chooses a representative of the boundary conformal class.

Second, **not every coordinate chart covers all of AdS**. Poincare coordinates are indispensable for flat-space CFT correlators, but they cover only a patch of global AdS. Global coordinates are indispensable for Hilbert-space questions on the cylinder.

Unless stated otherwise, the bulk dimension is $d+1$, the boundary dimension is $d$, and the AdS radius is $L$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A coordinate atlas for AdS: embedding space, global coordinates, Poincare coordinates, Fefferman-Graham gauge, black-brane coordinates, and hyperbolic/Rindler coordinates.](/figures/course/ads-coordinate-systems-appendix.svg)

<figcaption>

The most common coordinate systems for $\mathrm{AdS}_{d+1}$. Global coordinates see the boundary cylinder, Poincare coordinates see flat boundary space, Fefferman–Graham coordinates organize near-boundary data, black-brane and Eddington–Finkelstein coordinates describe thermal states, and hyperbolic/Rindler coordinates are natural for ball-shaped regions and modular flow.

</figcaption>
</figure>

## Quick coordinate dictionary

| Coordinates | Typical metric form | Boundary frame | Best used for |
|---|---|---|---|
| embedding | $-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2$ | none chosen | symmetries, global definitions |
| global | $-(1+r^2/L^2)dt^2+dr^2/(1+r^2/L^2)+r^2d\Omega_{d-1}^2$ | $\mathbb R_t\times S^{d-1}$ | states, normal modes, global black holes |
| compact global | $L^2\cos^{-2}\chi(-d\tau^2+d\chi^2+\sin^2\chi d\Omega_{d-1}^2)$ | $\mathbb R_\tau\times S^{d-1}$ | causal diagrams, boundary at $\chi=\pi/2$ |
| Poincare | $L^2z^{-2}(dz^2-dt^2+d\vec x^{\,2})$ | $\mathbb R^{1,d-1}$ | vacuum correlators, RG intuition |
| Euclidean Poincare | $L^2z^{-2}(dz^2+d\vec x^{\,2})$ | $\mathbb R^d$ | Euclidean correlators, $H^{d+1}$ |
| Fefferman–Graham | $L^2z^{-2}(dz^2+g_{ij}(z,x)dx^idx^j)$ | arbitrary $g_{(0)ij}$ | holographic renormalization |
| domain wall | $dr^2+e^{2A(r)}ds_d^2$ | usually flat or curved QFT metric | RG flows, relevant deformations |
| planar black brane | $L^2z^{-2}[-f(z)dt^2+d\vec x^{\,2}+dz^2/f(z)]$ | thermal flat-space CFT | thermodynamics, transport |
| ingoing EF | $L^2z^{-2}[-f(z)dv^2-2dvdz+d\vec x^{\,2}]$ | thermal flat-space CFT | horizons, real-time correlators |
| hyperbolic/Rindler | $-(r^2/L^2-1)d\tau^2+dr^2/(r^2/L^2-1)+r^2dH_{d-1}^2$ | $\mathbb R_\tau\times H^{d-1}$ | ball entanglement, modular flow |

The table hides many normalization choices. The sections below spell out the versions used in this course.

## Embedding-space definition

Lorentzian $\mathrm{AdS}_{d+1}$ can be defined as the hyperboloid

$$
-X_{-1}^2-X_0^2+X_1^2+\cdots+X_d^2=-L^2
$$

inside $\mathbb R^{2,d}$ with metric

$$
ds^2_{\mathbb R^{2,d}}
=
-dX_{-1}^2-dX_0^2+dX_1^2+\cdots+dX_d^2.
$$

The induced metric has constant negative curvature,

$$
R_{abcd}
=
-\frac{1}{L^2}\left(g_{ac}g_{bd}-g_{ad}g_{bc}\right),
\qquad
R_{ab}=-\frac d{L^2}g_{ab},
\qquad
R=-\frac{d(d+1)}{L^2}.
$$

The manifest symmetry group of the hyperboloid is $SO(2,d)$. This is the global conformal group of a $d$-dimensional Lorentzian CFT, up to global/discrete subtleties.

The literal hyperboloid contains closed timelike curves because the time coordinate is periodic. In AdS/CFT one normally means the **universal cover**, where the global time coordinate is unwrapped.

## Global coordinates

A standard global parametrization is

$$
X_{-1}=\sqrt{L^2+r^2}\cos\frac{t}{L},
\qquad
X_0=\sqrt{L^2+r^2}\sin\frac{t}{L},
\qquad
X_a=r\,\Omega_a,
$$

where $a=1,\ldots,d$, $\sum_a\Omega_a^2=1$, and $\Omega_a$ coordinates a unit $S^{d-1}$. The induced metric is

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+
r^2d\Omega_{d-1}^2.
$$

The boundary lies at $r\to\infty$. Multiplying by $L^2/r^2$ and taking the limit gives the boundary conformal representative

$$
ds^2_{\partial}
=
-dt^2+L^2d\Omega_{d-1}^2.
$$

Thus global AdS is adapted to a CFT on

$$
\mathbb R_t\times S^{d-1}.
$$

This is the natural coordinate system for state-operator correspondence, normal modes, finite-volume spectra, and global AdS black holes.

## Compact global coordinates

Define

$$
r=L\tan\chi,
\qquad
0\le \chi<\frac{\pi}{2},
\qquad
\tau=\frac{t}{L}.
$$

Then global AdS becomes

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

This is often the cleanest form for causal diagrams. The conformally related metric

$$
d\tilde s^2
=
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
$$

is a finite cylinder with boundary at $\chi=\pi/2$. Null rays reach the boundary in finite global time. This is why asymptotically AdS spacetimes require boundary conditions: the boundary is timelike.

## Poincare coordinates

Poincare coordinates are adapted to the flat-space CFT vacuum. In Lorentzian signature,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2-dt^2+d\vec x^{\,2}
\right),
\qquad
z>0.
$$

The boundary is at $z=0$, and the Poincare horizon is at $z\to\infty$. The boundary conformal representative is Minkowski space,

$$
ds^2_{\partial}=-dt^2+d\vec x^{\,2}.
$$

A useful embedding map is

$$
X_{-1}=\frac{L^2+z^2+x^\mu x_\mu}{2z},
\qquad
X_d=\frac{L^2-z^2-x^\mu x_\mu}{2z},
\qquad
X_\mu=\frac{Lx_\mu}{z},
$$

where $x^\mu x_\mu=-t^2+d\vec x^{\,2}$ and $\mu=0,\ldots,d-1$. This makes clear that Poincare coordinates cover only the region where

$$
X_{-1}+X_d>0.
$$

Poincare AdS is often also written with

$$
r=\frac{L^2}{z}.
$$

Then

$$
ds^2
=
\frac{r^2}{L^2}\left(-dt^2+d\vec x^{\,2}\right)
+
\frac{L^2}{r^2}dr^2.
$$

In these coordinates the boundary is at $r\to\infty$, while the Poincare horizon is at $r\to0$.

## Euclidean AdS

Euclidean AdS is hyperbolic space $H^{d+1}$. The Poincare half-space metric is

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+d\vec x^{\,2}\right),
\qquad
z>0.
$$

This coordinate system is ideal for Euclidean CFT correlators on $\mathbb R^d$. The regularity condition in the interior is usually simple: the Euclidean solution should be smooth and should not grow pathologically as $z\to\infty$.

Euclidean global AdS can be written as

$$
ds^2
=
\left(1+\frac{r^2}{L^2}\right)d\tau_E^2
+
\frac{dr^2}{1+r^2/L^2}
+
r^2d\Omega_{d-1}^2.
$$

If $\tau_E$ is periodically identified, the boundary is $S^1_\beta\times S^{d-1}$, which prepares a thermal state of the CFT on the sphere.

## Fefferman–Graham gauge

Fefferman–Graham coordinates are not primarily a global coordinate system. They are a **near-boundary gauge**. In one common convention,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
dz^2+g_{ij}(z,x)dx^idx^j
\right),
\qquad
z\to0.
$$

The expansion has the schematic form

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)
+z^2g_{(2)ij}(x)
+\cdots
+z^d g_{(d)ij}(x)
+z^d\log z^2\,h_{(d)ij}(x)
+\cdots.
$$

The coefficient $g_{(0)ij}$ is the boundary metric source. The coefficient $g_{(d)ij}$ contains state-dependent information and is related to the renormalized stress tensor. The logarithmic term appears for even boundary dimension $d$ and is tied to the Weyl anomaly.

A second common convention uses $\rho=z^2$:

$$
ds^2
=
\frac{L^2}{4\rho^2}d\rho^2
+
\frac{L^2}{\rho}g_{ij}(\rho,x)dx^idx^j.
$$

Fefferman–Graham gauge fixes

$$
g_{zz}=\frac{L^2}{z^2},
\qquad
 g_{zi}=0,
$$

but it does not fix all diffeomorphisms. The residual transformations include boundary diffeomorphisms and Weyl transformations of $g_{(0)ij}$.

## Domain-wall coordinates

For holographic RG flows it is often useful to write

$$
ds^2
=
dr^2+e^{2A(r)}ds_d^2,
$$

where $ds_d^2$ is usually a flat or curved boundary metric. Pure Poincare AdS is recovered from

$$
A(r)=\frac rL,
\qquad
z=L e^{-r/L},
$$

up to a constant rescaling of boundary coordinates. The boundary is $r\to\infty$, and moving inward toward smaller $r$ corresponds roughly to flowing toward the infrared.

For Einstein-scalar flows, scalar profiles $\phi^I(r)$ are interpreted as running couplings or expectation values. Domain-wall coordinates make this interpretation transparent but are often less convenient for extracting precise counterterms than Fefferman–Graham coordinates.

## Planar black brane coordinates

The planar AdS-Schwarzschild black brane is

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

The boundary is at $z=0$, and the horizon is at $z=z_h$. Smoothness of the Euclidean geometry gives

$$
T=\frac{d}{4\pi z_h}.
$$

The same geometry can be written in $r=L^2/z$ coordinates as

$$
ds^2
=
-\frac{r^2}{L^2}f(r)dt^2
+
\frac{L^2}{r^2f(r)}dr^2
+
\frac{r^2}{L^2}d\vec x^{\,2},
\qquad
f(r)=1-\left(\frac{r_h}{r}\right)^d.
$$

Then

$$
T=\frac{d\,r_h}{4\pi L^2}.
$$

Black-brane coordinates are adapted to a thermal CFT on $\mathbb R^{d-1}$. They are the default setup for transport, real-time correlators, and finite-density generalizations.

## Ingoing Eddington–Finkelstein coordinates

Schwarzschild-like black-brane coordinates are singular at the future horizon. For real-time problems one often uses ingoing Eddington–Finkelstein coordinates. Define

$$
v=t-z_*(z),
\qquad
\frac{dz_*}{dz}=\frac{1}{f(z)}.
$$

Then

$$
dt=dv+\frac{dz}{f(z)},
$$

and the black-brane metric becomes

$$
ds^2
=
\frac{L^2}{z^2}
\left[
-f(z)dv^2-2dvdz+d\vec x^{\,2}
\right].
$$

This form is regular at the future horizon. Infalling fields are smooth functions of $v$ and $z$ near $z=z_h$. That is the geometric origin of the infalling prescription for retarded Green functions.

## Global AdS black holes and topological black holes

A useful family of static asymptotically AdS metrics is

$$
ds^2
=
-f_k(r)dt^2+
\frac{dr^2}{f_k(r)}
+r^2d\Sigma_{k,d-1}^2,
$$

with

$$
f_k(r)=k+\frac{r^2}{L^2}-\frac{\mu}{r^{d-2}}.
$$

Here $d\Sigma_{k,d-1}^2$ is a unit metric of constant curvature

$$
k=1,0,-1.
$$

The cases are:

| $k$ | Horizon geometry | Boundary spatial geometry | Common use |
|---:|---|---|---|
| $1$ | sphere $S^{d-1}$ | $S^{d-1}$ | Hawking–Page transition |
| $0$ | plane $\mathbb R^{d-1}$ | $\mathbb R^{d-1}$ | thermal plasma, transport |
| $-1$ | hyperbolic space $H^{d-1}$ or quotient | $H^{d-1}$ or quotient | ball entanglement, hyperbolic black holes |

The planar case is obtained from the large-black-hole or infinite-volume limit of the spherical case.

## Hyperbolic/Rindler AdS coordinates

A particularly important hyperbolic slicing is

$$
ds^2
=
-\left(\frac{r^2}{L^2}-1\right)d\tau^2
+
\frac{dr^2}{r^2/L^2-1}
+r^2dH_{d-1}^2.
$$

This is pure AdS written as a hyperbolic black hole with horizon at $r=L$. It is not a new state of the full theory; it is a coordinate patch adapted to an accelerated observer or, on the boundary, to the domain of dependence of a ball-shaped region.

This coordinate system is central in the relation between vacuum entanglement across a sphere and thermal physics on $\mathbb R\times H^{d-1}$.

## Coordinate transformations worth memorizing

The most useful transformations are:

$$
r=L\tan\chi
\qquad
\text{global radial coordinate to compact global coordinate},
$$

$$
r=\frac{L^2}{z}
\qquad
\text{Poincare } r\text{ coordinate to Poincare }z\text{ coordinate},
$$

$$
z=L e^{-r/L}
\qquad
\text{domain-wall radial coordinate to Poincare }z,
$$

and

$$
v=t-z_*(z),
\qquad
\frac{dz_*}{dz}=\frac{1}{f(z)}
\qquad
\text{Schwarzschild time to ingoing EF time}.
$$

You do not need to memorize the full global-to-Poincare transformation. What matters more is the conceptual fact: Poincare coordinates cover only a wedge of global AdS, and the Poincare boundary is conformal to Minkowski space plus a point.

## Which coordinates should I use?

Use **global coordinates** when the boundary theory lives on $\mathbb R\times S^{d-1}$, when you care about the spectrum, or when the state-operator correspondence is central.

Use **Poincare coordinates** when the boundary theory lives on flat space and translation invariance is present.

Use **Fefferman–Graham coordinates** when you need near-boundary expansions, sources, counterterms, and one-point functions.

Use **domain-wall coordinates** when you want physical intuition for RG flows.

Use **black-brane coordinates** when you want thermodynamics.

Use **ingoing Eddington–Finkelstein coordinates** when you want retarded real-time correlators or regularity at a future horizon.

Use **hyperbolic coordinates** when the boundary problem involves ball-shaped regions, modular flow, or hyperbolic thermal states.

## Common confusions

### “The coordinate $z$ is the energy scale.”

More carefully, small $z$ corresponds to the UV and large $z$ corresponds to the IR in many Poincare-domain-wall setups. But $z$ is a bulk coordinate, not literally an energy. The energy-scale interpretation is a powerful organizing principle, not a replacement for a holographic calculation.

### “The Poincare horizon is a black-hole horizon.”

In pure AdS, the Poincare horizon at $z\to\infty$ is a coordinate horizon, not a thermal black-hole horizon. It becomes physically analogous to a horizon in certain wedges, but it does not by itself imply a nonzero CFT temperature.

### “Fefferman–Graham coordinates always reach the horizon.”

No. Fefferman–Graham coordinates are guaranteed only near the conformal boundary under suitable asymptotic assumptions. They often break down before reaching a black-hole horizon.

### “The boundary metric is unique.”

The boundary metric is defined only up to Weyl rescaling. A coordinate system chooses a representative $g_{(0)ij}$ of the boundary conformal class.

## Exercises

### Exercise 1: Compact global AdS

Starting from

$$
ds^2
=
-\left(1+\frac{r^2}{L^2}\right)dt^2
+
\frac{dr^2}{1+r^2/L^2}
+r^2d\Omega_{d-1}^2,
$$

set $r=L\tan\chi$ and $t=L\tau$. Derive the compact global metric.

<details>
<summary><strong>Solution</strong></summary>

Since

$$
1+\frac{r^2}{L^2}=1+\tan^2\chi=\sec^2\chi,
\qquad
 dr=L\sec^2\chi\,d\chi,
$$

we have

$$
\frac{dr^2}{1+r^2/L^2}
=
\frac{L^2\sec^4\chi\,d\chi^2}{\sec^2\chi}
=
L^2\sec^2\chi\,d\chi^2.
$$

Also

$$
-\left(1+\frac{r^2}{L^2}\right)dt^2
=-L^2\sec^2\chi\,d\tau^2,
$$

and

$$
r^2d\Omega_{d-1}^2
=L^2\tan^2\chi\,d\Omega_{d-1}^2
=L^2\sec^2\chi\,\sin^2\chi\,d\Omega_{d-1}^2.
$$

Combining terms gives

$$
ds^2
=
\frac{L^2}{\cos^2\chi}
\left(
-d\tau^2+d\chi^2+\sin^2\chi\,d\Omega_{d-1}^2
\right).
$$

</details>

### Exercise 2: Black-brane temperature

For

$$
ds^2
=
\frac{L^2}{z^2}
\left[
f(z)d\tau_E^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right],
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d,
$$

derive $T=d/(4\pi z_h)$ from smoothness at $z=z_h$.

<details>
<summary><strong>Solution</strong></summary>

Near the horizon set $z=z_h-y$, with $y\ll z_h$. Then

$$
f(z)
=
1-\left(1-\frac{y}{z_h}\right)^d
\simeq
\frac{d y}{z_h}.
$$

The $(\tau_E,z)$ part of the metric is approximately

$$
\frac{L^2}{z_h^2}
\left(
\frac{d y}{z_h}d\tau_E^2
+
\frac{dy^2}{d y/z_h}
\right).
$$

Define

$$
\rho^2=\frac{4L^2 y}{d z_h}.
$$

Then the metric becomes

$$
d\rho^2+
\rho^2\left(\frac{d}{2z_h}d\tau_E\right)^2.
$$

Smoothness at the origin requires the angular variable $(d/2z_h)\tau_E$ to have period $2\pi$, so

$$
\beta=\frac{4\pi z_h}{d},
\qquad
T=\frac{1}{\beta}=\frac{d}{4\pi z_h}.
$$

</details>

### Exercise 3: Why ingoing EF coordinates are regular

Show that the transformation

$$
v=t-z_*(z),
\qquad
\frac{dz_*}{dz}=\frac{1}{f(z)}
$$

turns

$$
-f(z)dt^2+\frac{dz^2}{f(z)}
$$

into

$$
-f(z)dv^2-2dvdz.
$$

<details>
<summary><strong>Solution</strong></summary>

The definition gives

$$
dv=dt-\frac{dz}{f(z)},
\qquad
 dt=dv+\frac{dz}{f(z)}.
$$

Therefore

$$
-fdt^2+\frac{dz^2}{f}
=
-f\left(dv+\frac{dz}{f}\right)^2+\frac{dz^2}{f}.
$$

Expanding,

$$
-fdv^2-2dvdz-\frac{dz^2}{f}+\frac{dz^2}{f}
=
-fdv^2-2dvdz.
$$

The $1/f$ singularity has disappeared. This is why ingoing EF coordinates are regular at a future horizon.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
