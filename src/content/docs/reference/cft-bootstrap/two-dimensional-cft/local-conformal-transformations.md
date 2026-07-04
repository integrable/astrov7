---
title: "Local Conformal Transformations"
description: "Explains why two-dimensional conformal transformations are locally holomorphic maps, how primaries transform, and how the Witt and Virasoro generators arise."
sidebar:
  label: "Local Conformal Transformations"
  order: 2
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; BPZ 1984; Ginsparg 1988"
topics:
  - two-dimensional CFT
  - local conformal transformations
  - holomorphic maps
  - primary fields
  - Witt algebra
  - Virasoro algebra
canonicalTopics:
  - two-dimensional-local-conformal-transformations
  - holomorphic-conformal-symmetry
  - primary-field-transformation-law
researchStatus:
  established:
    - "In two Euclidean dimensions, orientation-preserving local conformal transformations are holomorphic maps with nonzero derivative, and their infinitesimal generators form two commuting Witt algebras before central extension."
  active:
    - "The subtle part in applications is rarely the local kinematics; it is the global gluing data, monodromy, modular invariance, defects, and extended chiral algebra structure."
---

## Summary

In two Euclidean dimensions, conformal symmetry is dramatically larger than in $d>2$. A local coordinate change

$$
z\mapsto w=f(z),
\qquad
\bar z\mapsto \bar w=\bar f(\bar z),
$$

is conformal wherever $f'(z)\neq0$, because

$$
dw\,d\bar w
=
|f'(z)|^2 dz\,d\bar z.
$$

It preserves angles and rescales lengths by the position-dependent factor $|f'(z)|$. The price is that the map may be only local: it can fail to be one-to-one globally, can have branch points, or can be singular at special points. That local flexibility is exactly what makes two-dimensional CFT powerful.

A primary field $\phi(z,\bar z)$ of weights $(h,\bar h)$ transforms as

$$
\phi'(w,\bar w)
=
\left(\frac{dw}{dz}\right)^{-h}
\left(\frac{d\bar w}{d\bar z}\right)^{-\bar h}
\phi(z,\bar z).
$$

Infinitesimally, for $w=z+\epsilon(z)$ and $\bar w=\bar z+\bar\epsilon(\bar z)$, the same statement becomes

$$
\delta\phi
=
-\left(\epsilon\partial+h\,\partial\epsilon\right)\phi
-\left(\bar\epsilon\bar\partial+\bar h\,\bar\partial\bar\epsilon\right)\phi,
$$

where this is the passive variation at fixed coordinate. The holomorphic and antiholomorphic pieces are independent. This is the first appearance of the left–right split that later becomes the Virasoro algebra, conformal blocks, modular invariance, and rational CFT.

## Prerequisites

You should know the complex-coordinate conventions from [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), the general notion of a conformal map from [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/), and the role of primary fields from [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/).

It is also useful to remember the higher-dimensional result: for $d>2$, conformal transformations are finite-dimensional. In $d=2$, the conformal-Killing equation degenerates into the Cauchy–Riemann equations, and the space of local solutions becomes infinite-dimensional.

## Core idea

The core idea is short but explosive:

$$
\text{2D conformal map}
=
\text{holomorphic map plus antiholomorphic map}.
$$

In real coordinates $x^1,x^2$, a conformal map is one whose Jacobian is a scale times a rotation. In complex coordinates, that condition is simply the Cauchy–Riemann condition. For an orientation-preserving map,

$$
\bar\partial w=0,
\qquad
\partial\bar w=0,
$$

so $w=f(z)$ and $\bar w=\bar f(\bar z)$ locally. The function $f$ can be any holomorphic function with nonzero derivative in the patch where we use it.

This does **not** mean every holomorphic function is a globally allowed symmetry of the plane or sphere. It means local correlation functions are constrained by an infinite-dimensional algebra of local coordinate changes. The global questions — single-valuedness, branch cuts, monodromy, modular invariance, and boundary conditions — come later.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A local holomorphic map rescales and rotates tangent vectors while preserving their angle.](/figures/cft-bootstrap/local-conformal-map.svg)

<figcaption>

A local holomorphic map $w=f(z)$ sends a small patch to a small patch, multiplying tangent vectors by $f'(z)$. The magnitude $|f'(z)|$ is a local scale factor and the phase $\arg f'(z)$ is a local rotation angle. The map need not define a one-to-one transformation of the whole surface.

</figcaption>
</figure>

## Setup and conventions

We work in Euclidean signature on a local patch with

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2,
$$

and

$$
\partial\equiv\partial_z=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial\equiv\partial_{\bar z}=\frac12(\partial_1+i\partial_2).
$$

The flat metric is

$$
ds^2=dz\,d\bar z.
$$

A local orientation-preserving conformal transformation is

$$
z\mapsto w=f(z),
\qquad
\bar z\mapsto\bar w=\bar f(\bar z),
$$

with $f'(z)\neq0$ in the patch. Then

$$
ds^2\mapsto dw\,d\bar w
=f'(z)\bar f'(\bar z) dz\,d\bar z.
$$

For ordinary real Euclidean maps, $\bar f(\bar z)$ is the complex conjugate of $f(z)$. In complexified CFT calculations, $z$ and $\bar z$ are often treated as independent variables, and the holomorphic and antiholomorphic transformations are independent until a reality condition is imposed.

:::note[Orientation-reversing maps]
Orientation-reversing conformal maps exchange the holomorphic and antiholomorphic sectors. A simple example is $z\mapsto\bar z$. Most local CFT formulas focus first on orientation-preserving transformations; parity, boundaries, and crosscaps bring the orientation-reversing maps back into the story.
:::

## Why two dimensions are special

In $d>2$, the conformal-Killing equation is overdetermined. Its local solutions are generated by translations, rotations, dilatations, and special conformal transformations. The resulting group is finite-dimensional.

In two Euclidean dimensions, write a vector field as

$$
v=v^z(z,\bar z)\partial_z+v^{\bar z}(z,\bar z)\partial_{\bar z}.
$$

The conformal-Killing equation reduces locally to

$$
\bar\partial v^z=0,
\qquad
\partial v^{\bar z}=0.
$$

Therefore

$$
v^z=\epsilon(z),
\qquad
v^{\bar z}=\bar\epsilon(\bar z),
$$

with arbitrary holomorphic and antiholomorphic functions. This is the infinite-dimensional enhancement.

Locally, expand

$$
\epsilon(z)=\sum_{n\in\mathbb Z}\epsilon_n z^{n+1}.
$$

The conventional holomorphic vector-field basis is

$$
\ell_n=-z^{n+1}\partial_z,
\qquad
n\in\mathbb Z,
$$

and similarly

$$
\bar\ell_n=-\bar z^{n+1}\partial_{\bar z}.
$$

These obey two commuting Witt algebras,

$$
[\ell_m,\ell_n]=(m-n)\ell_{m+n},
\qquad
[\bar\ell_m,\bar\ell_n]=(m-n)\bar\ell_{m+n},
\qquad
[\ell_m,\bar\ell_n]=0.
$$

The global conformal transformations on the Riemann sphere are the nonsingular finite transformations generated by

$$
\ell_{-1},\quad \ell_0,
\quad \ell_1,
$$

and their antiholomorphic partners. Finite global maps are Möbius transformations,

$$
w=\frac{az+b}{cz+d},
\qquad
ad-bc\neq0,
$$

with the common rescaling of $a,b,c,d$ modded out. This is $PSL(2,\mathbb C)$ in Euclidean signature.

The rest of the modes are local. They are exactly the modes one needs for local Ward identities, OPEs, descendant states, and Virasoro representation theory.

## Primary fields under finite maps

A scalar primary in higher-dimensional CFT is characterized by its scaling dimension and spin representation. In 2D CFT, the same information is repackaged into holomorphic and antiholomorphic weights

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

A primary field $\phi(z,\bar z)$ of weights $(h,\bar h)$ transforms under a finite local conformal map as

$$
\phi'(w,\bar w)
=
\left(\frac{dw}{dz}\right)^{-h}
\left(\frac{d\bar w}{d\bar z}\right)^{-\bar h}
\phi(z,\bar z).
$$

Equivalently, in an active convention one often writes

$$
U_f\phi(z,\bar z)U_f^{-1}
=
\left(f'(z)\right)^h
\left(\bar f'(\bar z)\right)^{\bar h}
\phi(f(z),\bar f(\bar z)).
$$

These two formulas differ only by whether one describes the same geometric transformation passively as a coordinate change or actively as an operator transformation.

The simplest checks are worth keeping close:

| Transformation | Map | Effect on a primary |
|---|---|---|
| Translation | $w=z+a$ | No Jacobian factor. |
| Dilation | $w=\lambda z$ | Factor $\lambda^{-h}\bar\lambda^{-\bar h}$ in passive convention. |
| Rotation | $w=e^{i\theta}z$ | Phase $e^{-i\theta h}e^{i\theta\bar h}=e^{-i\theta s}$. |
| Inversion | $w=1/z$ | Local Jacobian factors produce the usual behavior at infinity. |

The rotation line is the quickest way to remember why $h-\bar h$ is spin.

## Infinitesimal transformations

Let

$$
w=z+\epsilon(z),
\qquad
\bar w=\bar z+\bar\epsilon(\bar z),
$$

with small $\epsilon,\bar\epsilon$. Expanding the finite primary transformation at fixed coordinate gives

$$
\delta\phi(z,\bar z)
=
-\left(\epsilon\partial+h\,\partial\epsilon\right)\phi(z,\bar z)
-\left(\bar\epsilon\bar\partial+\bar h\,\bar\partial\bar\epsilon\right)
\phi(z,\bar z).
$$

For the mode $\epsilon(z)=-a_n z^{n+1}$, this gives the differential action

$$
\delta_n\phi
=
a_n\left(z^{n+1}\partial+h(n+1)z^n\right)\phi
$$

in the holomorphic sector. This is the field-level version of the Virasoro generator action.

A useful shorthand is

$$
\mathcal L_n^{(h)}
=
-z^{n+1}\partial-h(n+1)z^n,
$$

so that the primary field carries a representation of the Witt algebra:

$$
[\mathcal L_m^{(h)},\mathcal L_n^{(h)}]
=
(m-n)\mathcal L_{m+n}^{(h)}.
$$

The antiholomorphic sector has the same formula with $z,h,\partial$ replaced by $\bar z,\bar h,\bar\partial$.

## The stress tensor as the generator

In a quantum CFT, local conformal transformations are generated by the stress tensor. The defining OPE with a primary is

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}
+\cdots,
$$

and

$$
\bar T(\bar z)\phi(w,\bar w)
\sim
\frac{\bar h\phi(w,\bar w)}{(\bar z-\bar w)^2}
+
\frac{\bar\partial_{\bar w}\phi(w,\bar w)}{\bar z-\bar w}
+\cdots.
$$

Define the modes by

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z),
\qquad
\bar L_n=\frac{1}{2\pi i}\oint d\bar z\,\bar z^{n+1}\bar T(\bar z).
$$

Then the primary-state conditions in radial quantization are

$$
L_0|h,\bar h\rangle=h|h,\bar h\rangle,
\qquad
\bar L_0|h,\bar h\rangle=\bar h|h,\bar h\rangle,
$$

and

$$
L_n|h,\bar h\rangle=0,
\qquad
\bar L_n|h,\bar h\rangle=0,
\qquad n>0.
$$

The quantum stress tensor does not realize the Witt algebra exactly. It realizes its central extension,

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

with an independent antiholomorphic copy involving $\bar c$. This central extension is the Virasoro algebra. The modes $L_{-1},L_0,L_1$ have no central term, which is why the global conformal algebra remains ordinary $sl(2)$.

## Local versus global transformations

A common source of confusion is the word “symmetry.” In 2D CFT it appears in two related but different ways.

A **global conformal transformation** is a genuine automorphism of the surface. On the Riemann sphere, these are Möbius transformations. They can be applied to a correlator without changing its global definition.

A **local conformal transformation** is a holomorphic coordinate change in a patch, or equivalently a meromorphic vector field used inside a contour integral. It need not define a globally regular one-to-one map. It is still a symmetry in the Ward-identity sense: deforming a small contour, collecting residues at operator insertions, and using holomorphicity gives exact identities.

The distinction is not pedantry. The map

$$
w=z+\alpha z^3
$$

is perfectly valid as a local conformal map near $z=0$ for small enough $\alpha$, but it is not a Möbius transformation of the sphere. Its infinitesimal generator is a local mode. Those local modes create descendants and generate the Virasoro representation, but not all of them exponentiate to globally well-defined transformations on the original surface.

## Three practical uses

### Deriving correlation functions

Global conformal invariance fixes two- and three-point functions of primaries. Local conformal invariance gives much more: Ward identities with insertions of $T(z)$ and $\bar T(\bar z)$, differential equations when null states exist, and recursive control over descendants.

For example,

$$
\langle T(z)\prod_{i=1}^n\phi_i(z_i,\bar z_i)\rangle
=
\sum_{i=1}^n
\left[
\frac{h_i}{(z-z_i)^2}
+
\frac{1}{z-z_i}\partial_{z_i}
\right]
\langle\prod_{i=1}^n\phi_i(z_i,\bar z_i)\rangle,
$$

up to possible regular terms determined by the surface and boundary conditions. This is the local conformal Ward identity on the plane.

### Organizing descendants

The local modes $L_{-n}$ with $n>0$ generate descendants of a primary state:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle.
$$

The total level is

$$
N=n_1+n_2+\cdots+n_k.
$$

This tower is not extra decoration. It is the 2D replacement for the finite set of derivative descendants in a global conformal multiplet. Conformal blocks, characters, null vectors, minimal models, and modular invariance all depend on this tower.

### Turning symmetry into solvability

The decisive feature of 2D CFT is that the stress tensor supplies infinitely many conserved charges. With enough representation-theoretic input — for example null vectors, affine currents, supersymmetry, or rational chiral algebra — local conformal symmetry can reduce correlation functions to finite-dimensional differential equations or finite sums of conformal blocks.

This is why two-dimensional CFT is not just a special case of higher-dimensional CFT. It is a different ecosystem.

## Common pitfalls

**Pitfall 1: saying “all holomorphic maps are global symmetries.”**

They are not. A holomorphic map with nonzero derivative is locally conformal. Global conformal automorphisms of the sphere are only Möbius transformations.

**Pitfall 2: forgetting the antiholomorphic sector.**

A full local operator usually has weights $(h,\bar h)$. Holomorphic formulas alone describe a chiral half, not automatically a complete local field.

**Pitfall 3: using the primary transformation law for every field.**

The stress tensor is not an ordinary primary. Under a finite map it acquires an anomalous Schwarzian term,

$$
T(z)
\mapsto
\left(\frac{dw}{dz}\right)^2T(w)
+
\frac{c}{12}\{w,z\},
$$

up to convention-dependent signs associated with active versus passive transformations. This is one of the cleanest ways the central charge enters.

**Pitfall 4: treating local singular-vector equations as full correlators.**

Local conformal symmetry often determines chiral blocks. Full correlators require single-valued combinations of holomorphic and antiholomorphic blocks.

**Pitfall 5: mixing active and passive signs.**

The component law $\phi'(w)=J^{-h}\bar J^{-\bar h}\phi(z)$ and the charge law $[Q_\epsilon,\phi]=(\epsilon\partial+h\partial\epsilon)\phi$ are both standard. Be explicit about which variation is being used.

## Relations to other pages

This page builds directly on [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/) and prepares the pages on [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), and [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/).

For the higher-dimensional comparison, see [Conformal Killing Equation](/cft-bootstrap/conformal-symmetry/conformal-killing-equation/) and [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/). For the operator-language version, see [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/).

## Research status

The local transformation laws, Witt algebra, Virasoro central extension, and primary Ward identities are standard, settled parts of 2D CFT.

The active research begins when local symmetry is combined with global data: modular tensor categories, non-diagonal modular invariants, logarithmic CFTs, defects, boundary conditions, non-invertible symmetries, chiral algebras of higher-dimensional supersymmetric theories, and the analytic structure of conformal blocks on higher-genus surfaces.

## Exercises

### Exercise 1: Holomorphic maps preserve angles

Let $w=f(z)$ with $f'(z_0)\neq0$. Show that two tangent vectors at $z_0$ have their angle preserved under the map.

<details><summary><strong>Solution</strong></summary>

Near $z_0$,

$$
dw=f'(z_0)dz+O(dz^2).
$$

Multiplication by the complex number $f'(z_0)$ rescales tangent vectors by $|f'(z_0)|$ and rotates them by $\arg f'(z_0)$. Rescaling and common rotation preserve the angle between any two tangent vectors.

</details>

### Exercise 2: Compute the Witt algebra

Using

$$
\ell_n=-z^{n+1}\partial_z,
$$

show that

$$
[\ell_m,\ell_n]=(m-n)\ell_{m+n}.
$$

<details><summary><strong>Solution</strong></summary>

Act on a test function $f(z)$. Then

$$
\ell_m\ell_n f
=
z^{m+1}\partial_z\left(z^{n+1}\partial_z f\right)
=
(n+1)z^{m+n+1}\partial_z f+z^{m+n+2}\partial_z^2 f.
$$

Interchanging $m$ and $n$ and subtracting gives

$$
[\ell_m,\ell_n]f
=
(n-m)z^{m+n+1}\partial_z f
=
(m-n)\ell_{m+n}f.
$$

</details>

### Exercise 3: Identify the global modes

Show that $\ell_{-1}$, $\ell_0$, and $\ell_1$ generate infinitesimal translations, dilatations/rotations, and special conformal transformations of $z$.

<details><summary><strong>Solution</strong></summary>

An infinitesimal holomorphic transformation has $\delta z=\epsilon(z)$. The vector fields are proportional to $-z^{n+1}\partial_z$, so the coordinate changes are proportional to

$$
1,
\qquad
z,
\qquad
z^2
$$

for $n=-1,0,1$. These are respectively translations, dilatations/rotations, and special conformal transformations. Exponentiating linear combinations of these three vector fields gives the Möbius transformations.

</details>

### Exercise 4: Recover the primary OPE with the stress tensor

Assume the contour charge

$$
Q_\epsilon=\frac{1}{2\pi i}\oint dz\,\epsilon(z)T(z)
$$

acts on a primary as

$$
[Q_\epsilon,\phi(w,\bar w)]
=
\left(\epsilon(w)\partial_w+h\partial_w\epsilon(w)\right)\phi(w,\bar w).
$$

Show that the singular part of $T(z)\phi(w,\bar w)$ must be

$$
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

<details><summary><strong>Solution</strong></summary>

The contour integral extracts residues. If

$$
T(z)\phi(w,\bar w)
\sim
\frac{A}{(z-w)^2}+\frac{B}{z-w},
$$

then

$$
\frac{1}{2\pi i}\oint dz\,\epsilon(z)T(z)\phi(w,\bar w)
=
\partial_w\epsilon(w)A+\epsilon(w)B.
$$

Matching with the assumed charge action gives

$$
A=h\phi(w,\bar w),
\qquad
B=\partial_w\phi(w,\bar w).
$$

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984) 333.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997, chapters 5–6.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- P. Goddard and D. Olive, “Kac–Moody and Virasoro algebras in relation to quantum physics,” *International Journal of Modern Physics A* **1** (1986) 303.
- J. Polchinski, *String Theory*, Vol. 1, Cambridge University Press, 1998, chapters 2–3.

## Version history

- 2026-06-28: First polished draft. Introduced local holomorphic maps, primary transformation laws, Witt generators, stress-tensor Ward identities, and the local/global distinction.
