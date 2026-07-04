---
title: "Complex Coordinates"
description: "Defines the complex-coordinate dictionary used in two-dimensional CFT, including derivatives, metric factors, tensor components, contour conventions, and conformal maps."
sidebar:
  label: "Complex Coordinates"
  order: 1
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Sénéchal 1997; Ginsparg 1988; Cardy 1996"
topics:
  - complex coordinates
  - two-dimensional CFT
  - holomorphic functions
  - Euclidean signature
  - tensor components
canonicalTopics:
  - complex-coordinates-in-cft
  - holomorphic-antiholomorphic-decomposition
  - two-dimensional-euclidean-cft-conventions
researchStatus:
  established:
    - "Complex coordinates are the standard local language of Euclidean two-dimensional CFT and make the holomorphic and antiholomorphic sectors manifest."
  active:
    - "The basic coordinate dictionary is fixed, while global analytic continuation, nontrivial topology, boundaries, defects, and nonunitary sectors require additional conventions developed later."
---

## Summary

Two-dimensional Euclidean CFT is usually written in complex coordinates

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

The corresponding derivatives are

$$
\partial=\partial_z=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial=\partial_{\bar z}=\frac12(\partial_1+i\partial_2),
$$

so that

$$
\nabla^2=\partial_1^2+\partial_2^2=4\partial\bar\partial.
$$

The payoff is immediate: local conformal transformations become holomorphic or antiholomorphic maps. If

$$
w=f(z),
\qquad
\bar w=\bar f(\bar z),
$$

then

$$
dw\,d\bar w=|f'(z)|^2dz\,d\bar z.
$$

Thus a holomorphic map with $f'(z)\neq0$ preserves angles and changes only the local scale. This is the small coordinate miracle behind the enormous power of two-dimensional CFT.

<figure class="doc-figure" style="--figure-width: 38rem;">

![Complex coordinate plane](/figures/cft-bootstrap/complex-coordinate-plane.svg)

<figcaption>

Complex coordinates package the Euclidean plane into $z=x^1+ix^2$ and $\bar z=x^1-ix^2$. The flat metric becomes $ds^2=dz\,d\bar z$, while holomorphic maps rescale it by $|f'(z)|^2$.

</figcaption>
</figure>

This page fixes the local dictionary. Later pages use it for local conformal transformations, holomorphic factorization, the two-dimensional stress tensor, radial quantization, OPEs, and Virasoro modes.

## Prerequisites

You should know the volume [Conventions and Notation](/cft-bootstrap/conventions/) and the chapter overview [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/). It also helps to know the general pages on [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/), [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), and [Correlation Functions](/cft-bootstrap/correlation-functions/).

Mathematically, you should be comfortable with holomorphic functions, Laurent expansions, residues, and the Cauchy–Riemann equations. This page uses complex analysis as physics notation, not as a theorem-first complex-analysis course.

## Core idea

Complex coordinates are not just shorthand for two real coordinates. They diagonalize the local conformal structure.

In real coordinates, a conformal map is a coordinate transformation whose Jacobian is locally a scale times a rotation. In complex coordinates, the orientation-preserving version is simply

$$
z\mapsto w=f(z),
\qquad
\bar z\mapsto \bar w=\bar f(\bar z),
$$

with $f$ holomorphic and $f'(z)\neq0$ in the region of interest.

This turns many two-dimensional CFT statements into statements about holomorphic functions plus their antiholomorphic partners. For example, a primary field is labeled by two weights,

$$
(h,\bar h),
$$

rather than only by a scaling dimension and spin. The translation between the two languages is

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The pair $(h,\bar h)$ is often more fundamental in two-dimensional calculations. The dimension $\Delta$ tells you the response to scale transformations; the spin $s$ tells you the response to rotations.

## Setup and conventions

We work first on the flat Euclidean plane with real coordinates $(x^1,x^2)$ and metric

$$
ds^2=(dx^1)^2+(dx^2)^2.
$$

Define

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2.
$$

On the ordinary Euclidean real slice, $\bar z$ is the complex conjugate of $z$. In algebraic manipulations, it is often useful to treat $z$ and $\bar z$ as formally independent variables and impose the real-slice relation at the end. This is a bookkeeping device, not a claim that the Euclidean plane has doubled its number of real dimensions.

The inverse relations are

$$
x^1=\frac{z+\bar z}{2},
\qquad
x^2=\frac{z-\bar z}{2i}.
$$

Differentials obey

$$
dz=dx^1+i dx^2,
\qquad
 d\bar z=dx^1-i dx^2.
$$

The oriented area form is

$$
dx^1\wedge dx^2=\frac{i}{2}dz\wedge d\bar z.
$$

Many CFT formulas abbreviate

$$
d^2z\equiv dx^1dx^2.
$$

With this convention,

$$
\int d^2z\,\delta^{(2)}(z)f(z,\bar z)=f(0,0).
$$

Be careful: some mathematics and string-theory sources absorb factors of $i/2$ into their definition of $d^2z$. Whenever contact terms or path-integral normalizations matter, the area convention must be stated.

## Derivatives and metric factors

By the chain rule,

$$
\partial_z
=\frac{\partial x^1}{\partial z}\partial_1
+\frac{\partial x^2}{\partial z}\partial_2
=\frac12(\partial_1-i\partial_2),
$$

and similarly

$$
\partial_{\bar z}=\frac12(\partial_1+i\partial_2).
$$

We write

$$
\partial\equiv\partial_z,
\qquad
\bar\partial\equiv\partial_{\bar z}.
$$

They satisfy

$$
\partial z=1,
\qquad
\partial\bar z=0,
\qquad
\bar\partial z=0,
\qquad
\bar\partial\bar z=1.
$$

The inverse relations are

$$
\partial_1=\partial+\bar\partial,
\qquad
\partial_2=i(\partial-\bar\partial).
$$

Therefore the scalar Laplacian is

$$
\nabla^2
=\partial_1^2+\partial_2^2
=4\partial\bar\partial.
$$

The metric becomes

$$
ds^2=dz\,d\bar z.
$$

In component language, if the coordinates are ordered as $(z,\bar z)$, then

$$
g_{zz}=g_{\bar z\bar z}=0,
\qquad
 g_{z\bar z}=g_{\bar z z}=\frac12,
$$

and

$$
g^{zz}=g^{\bar z\bar z}=0,
\qquad
 g^{z\bar z}=g^{\bar z z}=2.
$$

This is one of the most common sources of factor-of-two errors. The compact expression $ds^2=dz\,d\bar z$ hides the fact that the symmetric line element contains both $dz\otimes d\bar z$ and $d\bar z\otimes dz$.

For a scalar field $\phi$,

$$
\partial_\mu\phi\,\partial^\mu\phi
=(\partial_1\phi)^2+(\partial_2\phi)^2
=4\partial\phi\,\bar\partial\phi.
$$

Thus a free massless scalar action is naturally written in the form

$$
S=\kappa\int d^2z\,\partial\phi\,\bar\partial\phi,
$$

where the constant $\kappa$ depends on the field normalization used for the boson and its vertex operators. The coordinate factors are fixed; the field normalization is a separate convention.

## Holomorphic functions and conformal maps

A function $f(z,\bar z)$ is holomorphic in a region if

$$
\bar\partial f=0
$$

there. In real coordinates this is exactly the Cauchy–Riemann condition.

Consider a change of coordinate

$$
w=f(z),
\qquad
\bar w=\bar f(\bar z).
$$

Then

$$
dw=f'(z)dz,
\qquad
 d\bar w=\bar f'(\bar z)d\bar z,
$$

and hence

$$
dw\,d\bar w=f'(z)\bar f'(\bar z)dz\,d\bar z.
$$

On the Euclidean real slice, $\bar f'(\bar z)$ is the complex conjugate of $f'(z)$, so

$$
dw\,d\bar w=|f'(z)|^2dz\,d\bar z.
$$

The metric has changed only by a Weyl factor. This is why holomorphic maps are conformal.

Infinitesimally, write

$$
z\mapsto z+\epsilon(z),
\qquad
\bar z\mapsto \bar z+\bar\epsilon(\bar z).
$$

The holomorphic and antiholomorphic parts are independent infinitesimal functions locally. Their Laurent modes are the starting point for the Witt algebra and, quantum mechanically, the Virasoro algebra.

:::note[Local does not mean global]
A holomorphic map is locally conformal wherever $f'(z)\neq0$. Global conformal maps of the Riemann sphere that are nonsingular and one-to-one are much more restricted: they are Möbius transformations. The infinite-dimensional symmetry of two-dimensional CFT is local and infinitesimal before global questions are imposed.
:::

## Primary fields in complex notation

A two-dimensional primary field has weights $(h,\bar h)$. Under a holomorphic coordinate map $w=f(z)$, its correlators transform covariantly as

$$
\left\langle\prod_i \mathcal O_i(z_i,\bar z_i)\right\rangle
=
\prod_i\left(f'(z_i)\right)^{h_i}
\left(\bar f'(\bar z_i)\right)^{\bar h_i}
\left\langle\prod_i \mathcal O_i(w_i,\bar w_i)\right\rangle.
$$

Equivalently, the field itself carries one holomorphic and one antiholomorphic Jacobian weight. For a scale transformation

$$
z\mapsto \lambda z,
\qquad
\bar z\mapsto \lambda\bar z,
$$

this gives scaling dimension

$$
\Delta=h+\bar h.
$$

For a rotation

$$
z\mapsto e^{i\theta}z,
\qquad
\bar z\mapsto e^{-i\theta}\bar z,
$$

it gives spin

$$
s=h-\bar h.
$$

For scalar local operators, $s=0$, so $h=\bar h=\Delta/2$. For spinful or chiral operators, the two weights need not agree.

The two-point function of scalar primaries in an orthonormal basis becomes

$$
\langle \mathcal O_i(z,\bar z)\mathcal O_j(0,0)\rangle
=\frac{\delta_{ij}}{z^{2h_i}\bar z^{2\bar h_i}},
$$

when the weights match and branch conventions are harmless. In a unitary Euclidean theory, reflection positivity and single-valuedness impose further constraints; these are not merely local coordinate statements.

## Tensor components

Complex coordinates also split tensor components into holomorphic and antiholomorphic pieces.

For a covector

$$
V=V_1dx^1+V_2dx^2=V_zdz+V_{\bar z}d\bar z,
$$

the components are

$$
V_z=\frac12(V_1-iV_2),
\qquad
V_{\bar z}=\frac12(V_1+iV_2).
$$

For a vector

$$
V=V^1\partial_1+V^2\partial_2=V^z\partial_z+V^{\bar z}\partial_{\bar z},
$$

the components are

$$
V^z=V^1+iV^2,
\qquad
V^{\bar z}=V^1-iV^2.
$$

The asymmetry between covariant and contravariant components is another common factor-of-two trap.

For a symmetric rank-two tensor $T_{ij}$,

$$
T_{zz}=\frac14(T_{11}-2iT_{12}-T_{22}),
$$

$$
T_{\bar z\bar z}=\frac14(T_{11}+2iT_{12}-T_{22}),
$$

and

$$
T_{z\bar z}=\frac14(T_{11}+T_{22}).
$$

Thus the trace is proportional to $T_{z\bar z}$. In a flat two-dimensional CFT at separated points, tracelessness and conservation imply the holomorphicity statements

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0,
\qquad
T_{z\bar z}=0.
$$

The standard holomorphic stress tensor $T(z)$ used in the Virasoro OPE is a conventionally normalized version of the holomorphic stress-tensor component. This volume fixes the OPE convention by

$$
T(z)T(0)
\sim
\frac{c}{2z^4}+\frac{2T(0)}{z^2}+\frac{\partial T(0)}{z}.
$$

Do not compare $T(z)$ directly with another text's $T_{zz}$ until the normalization has been checked.

## Contours and distributions

Complex coordinates turn many Ward identities into contour statements. The basic residue convention is

$$
\oint_{C_w}\frac{dz}{2\pi i}\frac{1}{z-w}=1,
$$

where $C_w$ is a small counterclockwise contour around $w$.

The distributional identity compatible with the area convention above is

$$
\bar\partial\left(\frac{1}{z}\right)=\pi\delta^{(2)}(z).
$$

Equivalently,

$$
\partial\bar\partial\log |z|^2=\pi\delta^{(2)}(z).
$$

These identities explain why holomorphic expressions can encode contact terms. Away from coincident points, $1/z$ is holomorphic. At the origin, it knows about a delta function.

In CFT calculations, one often first works at separated points and later restores contact terms when deriving Ward identities, anomalies, or normalization constraints. This is sensible, but only if the distinction is explicit.

## Lorentzian continuation

Two-dimensional Lorentzian CFT is often written in light-cone coordinates

$$
x^+=t+x,
\qquad
x^-=t-x.
$$

After Wick rotation, these are related to the Euclidean complex variables. Schematically, one may think of left-moving and right-moving coordinates as analytic continuations of $z$ and $\bar z$.

The important practical warning is this: in Euclidean signature, $\bar z$ is the complex conjugate of $z$ on the real slice; in Lorentzian signature, the two light-cone variables are real and independent. Many Lorentzian formulas are obtained by analytic continuation with an $i\epsilon$ prescription, not by naively replacing $\bar z$ with the complex conjugate of $z$.

For this chapter, unless explicitly stated otherwise, $z$ and $\bar z$ denote Euclidean complex coordinates.

## Why this dictionary matters

The dictionary matters because the strongest two-dimensional CFT statements are written in complex notation.

The primary-field OPE takes the schematic form

$$
\mathcal O_i(z,\bar z)\mathcal O_j(0,0)
\sim
\sum_k C_{ij}^{\ \ k}
 z^{h_k-h_i-h_j}\bar z^{\bar h_k-\bar h_i-\bar h_j}
\left[\mathcal O_k(0,0)+\text{descendants}\right].
$$

The stress-tensor Ward identity is holomorphic:

$$
T(z)\mathcal O(w,\bar w)
\sim
\frac{h\mathcal O(w,\bar w)}{(z-w)^2}
+\frac{\partial_w\mathcal O(w,\bar w)}{z-w}.
$$

The modes of the stress tensor are contour integrals:

$$
L_n=\oint_0\frac{dz}{2\pi i}\,z^{n+1}T(z).
$$

The cylinder map is exponential:

$$
z=e^w,
\qquad
w=\tau+i\sigma.
$$

All of these formulas are almost unreadable in raw Cartesian coordinates. Complex coordinates are not decorative; they are the natural coordinate system of local two-dimensional conformal symmetry.

## Common pitfalls

**Dropping factors of two.** The definitions of $\partial$, $\bar\partial$, $g_{z\bar z}$, and tensor components contain factors of $1/2$. If a free-boson action, propagator, or stress tensor is off by a factor of two, this is usually the crime scene.

**Forgetting the area convention.** Some authors write $d^2z=dxdy$, while others use $d^2z=(i/2)dz\wedge d\bar z$ or related conventions. These are compatible only if the notation is translated carefully.

**Treating $z$ and $\bar z$ inconsistently.** In Euclidean calculations, they are conjugates on the real slice. In formal manipulations, they are often temporarily independent. In Lorentzian calculations, left and right variables become independent real light-cone coordinates. Mixing these viewpoints without warning produces wrong reality conditions.

**Calling every meromorphic change of variable a symmetry.** A holomorphic map can be locally conformal while failing to be globally one-to-one or nonsingular. Poles, branch points, and nontrivial topology matter.

**Confusing tensor components with normalized CFT operators.** The symbol $T(z)$ is usually normalized by its OPE with itself and with primaries. It may differ by constants and signs from the raw coordinate component $T_{zz}$ of a Noether stress tensor.

**Assuming holomorphic means nonsingular.** Meromorphic fields and OPEs have poles. CFT is full of holomorphic functions with controlled singularities.

## Relations to other pages

[Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/) uses this dictionary to derive the infinite-dimensional local conformal algebra. [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) explains when left and right dependence separates and when it must be recombined.

[Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) turns the tensor-component formulas into Ward identities, central charge, and Virasoro previews. [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) uses circles $|z|=r$ as time slices. [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/) uses $z=e^w$ to relate scaling dimensions to cylinder energies.

The higher-dimensional pages [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/) and [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/) use $z,\bar z$ as four-point cross-ratio variables. That notation is related but conceptually distinct: there $z,\bar z$ parametrize conformal frames for four points, while here they are coordinates on the physical two-dimensional plane.

## Research status

The local coordinate dictionary is settled. The interesting research questions begin when this dictionary is placed on less trivial spaces or in less standard theories: Riemann surfaces with nontrivial topology, boundaries, defects, spin structures, nonunitary models, logarithmic CFTs, noncompact target spaces, and Lorentzian regimes with nontrivial analytic continuation.

In such settings, the formulas on this page remain the local starting point, but global data become essential. For example, a holomorphic field on the plane may become a section of a line bundle on a curved Riemann surface; a fermion requires a spin structure; a chiral correlator may have monodromy and must be combined with an antiholomorphic partner to produce a single-valued local observable.

## Exercises

### Exercise 1: Derive the complex derivatives

Starting from

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2,
$$

derive

$$
\partial=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial=\frac12(\partial_1+i\partial_2).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
x^1=\frac{z+\bar z}{2},
\qquad
x^2=\frac{z-\bar z}{2i}.
$$

Holding $\bar z$ fixed,

$$
\frac{\partial x^1}{\partial z}=\frac12,
\qquad
\frac{\partial x^2}{\partial z}=\frac{1}{2i}=-\frac{i}{2}.
$$

Therefore

$$
\partial_z=\frac12\partial_1-\frac{i}{2}\partial_2.
$$

Holding $z$ fixed gives

$$
\partial_{\bar z}=\frac12\partial_1+\frac{i}{2}\partial_2.
$$

</details>

### Exercise 2: Check the Laplacian

Show that

$$
\partial_1^2+\partial_2^2=4\partial\bar\partial.
$$

<details><summary><strong>Solution</strong></summary>

Using

$$
\partial=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial=\frac12(\partial_1+i\partial_2),
$$

and the fact that partial derivatives commute in flat space,

$$
4\partial\bar\partial
=(\partial_1-i\partial_2)(\partial_1+i\partial_2)
=\partial_1^2+\partial_2^2.
$$

The cross terms cancel.

</details>

### Exercise 3: Metric components

Use

$$
ds^2=dz\,d\bar z
$$

to show that

$$
g_{z\bar z}=g_{\bar z z}=\frac12,
\qquad
 g^{z\bar z}=g^{\bar z z}=2.
$$

<details><summary><strong>Solution</strong></summary>

The coordinate expression for the line element is

$$
ds^2=g_{zz}dz^2+2g_{z\bar z}dz\,d\bar z+g_{\bar z\bar z}d\bar z^2.
$$

Comparing with $ds^2=dz\,d\bar z$ gives

$$
g_{zz}=g_{\bar z\bar z}=0,
\qquad
2g_{z\bar z}=1.
$$

Thus $g_{z\bar z}=g_{\bar z z}=1/2$. The inverse of the matrix

$$
\begin{pmatrix}
0 & 1/2\\
1/2 & 0
\end{pmatrix}
$$

is

$$
\begin{pmatrix}
0 & 2\\
2 & 0
\end{pmatrix},
$$

so $g^{z\bar z}=g^{\bar z z}=2$.

</details>

### Exercise 4: Holomorphic maps are conformal

Let $w=f(z)$ with $f'(z)\neq0$. Show that the flat metric changes by a Weyl factor.

<details><summary><strong>Solution</strong></summary>

Since $dw=f'(z)dz$ and $d\bar w=\bar f'(\bar z)d\bar z$,

$$
dw\,d\bar w=f'(z)\bar f'(\bar z)dz\,d\bar z.
$$

On the Euclidean real slice, $\bar f'(\bar z)$ is the complex conjugate of $f'(z)$, so

$$
dw\,d\bar w=|f'(z)|^2dz\,d\bar z.
$$

The metric is multiplied by a positive scalar function. Such a transformation preserves angles, so it is conformal.

</details>

### Exercise 5: Weight, dimension, and spin

A primary field has weights $(h,\bar h)$. Under a rotation $z\mapsto e^{i\theta}z$, determine its phase. Under a scale transformation $z\mapsto\lambda z$, determine its scale weight.

<details><summary><strong>Solution</strong></summary>

For a rotation,

$$
f'(z)=e^{i\theta},
\qquad
\bar f'(\bar z)=e^{-i\theta}.
$$

The Jacobian factor is

$$
(e^{i\theta})^h(e^{-i\theta})^{\bar h}=e^{i\theta(h-\bar h)}.
$$

Thus the spin is

$$
s=h-\bar h.
$$

For a scale transformation,

$$
f'(z)=\lambda,
\qquad
\bar f'(\bar z)=\lambda,
$$

so the factor is $\lambda^{h+\bar h}$. Thus

$$
\Delta=h+\bar h.
$$

Depending on active versus passive convention, correlator covariance may display the inverse factor, but the definitions of $\Delta$ and $s$ are unchanged.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on global conformal invariance, two-dimensional conformal invariance, Ward identities, and operator formalism.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures. Clear reference for complex coordinates, holomorphic stress tensors, and radial quantization.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*. Useful for the statistical mechanics route into complex coordinates and finite-size scaling.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” *Nuclear Physics B* **241** (1984). Foundational source for the local-conformal-symmetry viewpoint.

## Version history

- **2026-06-28:** Added the first ordinary page in the Two-Dimensional CFT chapter, fixing complex-coordinate, derivative, metric, tensor, contour, and primary-field conventions.
