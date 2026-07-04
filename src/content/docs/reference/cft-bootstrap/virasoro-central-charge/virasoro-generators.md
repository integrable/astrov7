---
title: "Virasoro Generators"
description: "Explains how contour modes of the two-dimensional stress tensor generate local conformal transformations on fields and states."
sidebar:
  label: "Virasoro Generators"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Ginsparg 1988; Cardy 1984; Polchinski 1998"
topics:
  - Virasoro generators
  - radial quantization
  - stress tensor modes
  - highest-weight states
  - conformal transformations
canonicalTopics:
  - virasoro-generators
  - stress-tensor-modes
  - radial-quantization-in-two-dimensional-cft
researchStatus:
  established:
    - "The Virasoro generators are the Laurent modes of the holomorphic stress tensor and act as quantum generators of local conformal transformations."
  active:
    - "In logarithmic, nonunitary, chiral, boundary, and defect settings the same mode algebra can act on modules with nonstandard inner products, indecomposable structure, or modified gluing conditions."
---

## Summary

The Virasoro generators are the contour modes of the holomorphic stress tensor:

$$
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z),
\qquad
T(z)=\sum_{n\in\mathbb Z}L_n z^{-n-2}.
$$

They are the quantum operators that implement infinitesimal holomorphic conformal transformations. Acting on a primary field of holomorphic weight $h$, they obey

$$
[L_n,\mathcal O(w,\bar w)]
=
\left(w^{n+1}\partial_w+(n+1)h\,w^n\right)\mathcal O(w,\bar w).
$$

The modes satisfy the Virasoro algebra

$$
[L_m,L_n]
=(m-n)L_{m+n}
+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The three modes $L_{-1},L_0,L_1$ generate the global holomorphic conformal group. The infinitely many other modes generate genuinely local conformal transformations and organize the descendant tower of each Virasoro primary.

## Prerequisites

You should know [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/), [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Central Charge](/cft-bootstrap/virasoro-central-charge/central-charge/), and [Stress-Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/).

## Core idea

In two-dimensional radial quantization, every contour around the origin defines an operator on the Hilbert space. Since $T(z)$ is the current for holomorphic conformal transformations, the contour integrals

$$
\oint dz\,\varepsilon(z)T(z)
$$

generate the infinitesimal map

$$
z\mapsto z+\varepsilon(z).
$$

Choosing the monomial vector fields

$$
\varepsilon_n(z)=z^{n+1}
$$

defines the modes $L_n$. Thus the Virasoro generators are not abstract decorations added to the theory. They are stress-tensor fluxes around the origin.

## Setup and conventions

We work on the Euclidean plane with radial ordering. The holomorphic stress tensor has Laurent expansion

$$
T(z)=\sum_{n\in\mathbb Z}L_nz^{-n-2}.
$$

The inverse formula is

$$
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z).
$$

The antiholomorphic sector is

$$
\bar T(\bar z)=\sum_{n\in\mathbb Z}\bar L_n\bar z^{-n-2},
\qquad
\bar L_n=\frac{1}{2\pi i}\oint_0 d\bar z\,\bar z^{n+1}\bar T(\bar z).
$$

The two copies commute in the absence of contact-term subtleties:

$$
[L_m,\bar L_n]=0.
$$

This page uses the convention

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

With this convention, the Virasoro central term is $\frac{c}{12}m(m^2-1)\delta_{m+n,0}$.

## Contour charges

For any holomorphic vector field $\varepsilon(z)$ defined near a set of insertions, define

$$
Q_\varepsilon
=\frac{1}{2\pi i}\oint dz\,\varepsilon(z)T(z).
$$

When the contour surrounds a primary field $\mathcal O(w,\bar w)$, the $T\mathcal O$ OPE gives

$$
\frac{1}{2\pi i}\oint_w dz\,\varepsilon(z)T(z)\mathcal O(w,\bar w)
=
\left(\varepsilon(w)\partial_w+h\,\partial_w\varepsilon(w)\right)\mathcal O(w,\bar w).
$$

Choosing $\varepsilon(z)=z^{n+1}$ gives the mode action

$$
[L_n,\mathcal O(w,\bar w)]
=
\left(w^{n+1}\partial_w+(n+1)h\,w^n\right)\mathcal O(w,\bar w).
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![Virasoro generators as stress-tensor contours](/figures/cft-bootstrap/virasoro-generator-contours.svg)

<figcaption>

A Virasoro generator is a stress-tensor contour mode. Deforming the contour onto an insertion converts the mode into a differential operator acting on that field.

</figcaption>
</figure>

The formula is the workhorse behind almost every 2D CFT computation. It converts contour manipulations into differential equations.

## The global generators

The modes $L_{-1},L_0,L_1$ correspond to the vector fields

$$
1,
\qquad
z,
\qquad
z^2.
$$

Their action on a primary field is

$$
[L_{-1},\mathcal O(w)]=\partial_w\mathcal O(w),
$$

$$
[L_0,\mathcal O(w)]=(w\partial_w+h)\mathcal O(w),
$$

and

$$
[L_1,\mathcal O(w)]=(w^2\partial_w+2hw)\mathcal O(w).
$$

These are the infinitesimal translation, dilation/rotation, and special conformal transformation in the holomorphic sector.

The central term vanishes inside this subalgebra, so

$$
[L_0,L_{-1}]=L_{-1},
\qquad
[L_0,L_1]=-L_1,
\qquad
[L_1,L_{-1}]=2L_0.
$$

This is the holomorphic $\mathfrak{sl}_2$ subalgebra. Together with $\bar L_{-1},\bar L_0,\bar L_1$, it generates the global conformal transformations of the sphere.

## Local generators and the Witt algebra

Classically, the holomorphic vector fields

$$
\ell_n=-z^{n+1}\partial_z
$$

satisfy the Witt algebra

$$
[\ell_m,\ell_n]=(m-n)\ell_{m+n}.
$$

Quantum mechanically, the stress-tensor modes satisfy the centrally extended version:

$$
[L_m,L_n]
=(m-n)L_{m+n}
+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The central term is not visible in the classical vector-field bracket. It appears because the quantum stress tensor has the fourth-order singularity

$$
T(z)T(w)\sim \frac{c/2}{(z-w)^4}+\cdots.
$$

The modes with $|n|>1$ are local conformal generators that are singular somewhere on the Riemann sphere. This is why they do not belong to the global conformal group, but they are still perfectly meaningful as local contour operators in radial quantization.

## States from operators

In radial quantization, an operator inserted at the origin creates a state:

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

For a primary field of weight $h$,

$$
L_0|\mathcal O\rangle=h|\mathcal O\rangle.
$$

Also,

$$
L_n|\mathcal O\rangle=0
\qquad
n>0.
$$

This is the highest-weight condition. It follows from the contour formula: for $n>0$, the integrand $z^{n+1}T(z)\mathcal O(0)$ has no $z^{-1}$ residue when $\mathcal O$ is primary.

Descendants are produced by negative modes:

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad
n_i>0.
$$

The level is

$$
N=n_1+n_2+\cdots+n_k.
$$

Since

$$
[L_0,L_{-n}]=nL_{-n},
$$

a level-$N$ descendant has holomorphic weight $h+N$.

## Primary fields versus primary states

The word “primary” is used in two closely related ways.

A **primary field** satisfies the OPE

$$
T(z)\mathcal O(w)
\sim
\frac{h\mathcal O(w)}{(z-w)^2}
+\frac{\partial\mathcal O(w)}{z-w}.
$$

A **primary state** satisfies

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

The state-operator correspondence identifies these two notions when the operator is inserted at the origin.

A **quasi-primary** is killed only by $L_1$ and transforms simply under the global conformal group. A **Virasoro primary** is killed by all $L_n$ with $n>0$. Every Virasoro primary is quasi-primary, but not every quasi-primary is Virasoro primary.

This distinction becomes important in Virasoro conformal blocks and minimal models.

## The vacuum module

The vacuum state $|0\rangle$ is invariant under the global conformal group:

$$
L_{-1}|0\rangle=L_0|0\rangle=L_1|0\rangle=0.
$$

More generally,

$$
L_n|0\rangle=0
\qquad
n\ge -1.
$$

The condition $L_{-1}|0\rangle=0$ says that translating the vacuum gives the same vacuum. The condition $L_0|0\rangle=0$ says the vacuum has zero scaling dimension on the plane. The condition $L_1|0\rangle=0$ says it is invariant under special conformal transformations.

The stress tensor itself is a descendant of the identity:

$$
|T\rangle=L_{-2}|0\rangle.
$$

Its norm is fixed by the central charge:

$$
\langle T|T\rangle
=\langle 0|L_2L_{-2}|0\rangle
=\frac{c}{2}\langle 0|0\rangle.
$$

In a unitary CFT, this implies $c\ge0$.

## Adjoint and unitarity

In unitary radial quantization, Hermitian conjugation maps the inside of the unit circle to the outside. The Virasoro modes obey

$$
L_n^\dagger=L_{-n}.
$$

Then descendant norms are computable from the algebra. For example,

$$
\|L_{-1}|h\rangle\|^2
=\langle h|L_1L_{-1}|h\rangle
=2h\langle h|h\rangle.
$$

So positivity requires

$$
h\ge0.
$$

At the next levels, positivity produces the Kac determinant constraints. These constraints lead to the classification of unitary minimal models for $c<1$ and to the general structure of null vectors and quotient modules.

The punchline: the Virasoro algebra is not only a symmetry algebra. Together with the adjoint, it is a norm machine.

## Mode action on descendants

Because descendants are generated by negative modes, the Virasoro commutator gives a recursive way to act on them. For example,

$$
L_1L_{-2}|h\rangle
=
[L_1,L_{-2}]|h\rangle+L_{-2}L_1|h\rangle
=3L_{-1}|h\rangle.
$$

Similarly,

$$
L_2L_{-2}|h\rangle
=
[L_2,L_{-2}]|h\rangle
=\left(4L_0+\frac{c}{2}\right)|h\rangle
=\left(4h+\frac{c}{2}\right)|h\rangle.
$$

These relations are the elementary ingredients of Gram matrices, null-state conditions, and differential equations for minimal-model correlators.

## Generator language on the cylinder

Under the map

$$
z=e^w,
\qquad
w=\tau+i\sigma,
$$

radial time becomes cylinder time $\tau$. The cylinder Hamiltonian is

$$
H_{\rm cyl}=L_0+\bar L_0-\frac{c+\bar c}{24}.
$$

The angular momentum around the circle is

$$
P_{\rm cyl}=L_0-\bar L_0-\frac{c-\bar c}{24}.
$$

For a nonchiral theory with $c=\bar c$, the momentum shift cancels and

$$
P_{\rm cyl}=L_0-\bar L_0.
$$

This is the finite-size scaling dictionary: scaling dimensions become cylinder energies, while spins become momenta.

## Antiholomorphic copy

Everything above has an antiholomorphic partner:

$$
[\bar L_m,\bar L_n]
=(m-n)\bar L_{m+n}
+\frac{\bar c}{12}m(m^2-1)\delta_{m+n,0}.
$$

A primary field has weights $(h,\bar h)$ and satisfies

$$
[L_n,\mathcal O(w,\bar w)]
=
\left(w^{n+1}\partial_w+(n+1)h\,w^n\right)\mathcal O,
$$

$$
[\bar L_n,\mathcal O(w,\bar w)]
=
\left(\bar w^{n+1}\partial_{\bar w}+(n+1)\bar h\,\bar w^n\right)\mathcal O.
$$

The full scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

For a local bosonic operator in an ordinary bosonic CFT, locality usually imposes integer spin. Fermionic, spin, and defect settings require their own spin-structure language.

## Common pitfalls

**Confusing the vector fields with the operators.** The classical vector fields $-z^{n+1}\partial_z$ obey the Witt algebra. The quantum operators $L_n$ obey its central extension.

**Forgetting the shift on the cylinder.** On the plane, the vacuum has $L_0=\bar L_0=0$. On the cylinder, the vacuum energy is shifted by $-(c+\bar c)/24$.

**Calling every descendant a derivative.** $L_{-1}$ gives an ordinary derivative. Higher descendants such as $L_{-2}|h\rangle$ are not generally ordinary derivatives of the primary; they encode stress-tensor descendants.

**Mixing global and Virasoro primaries.** A field killed by $L_1$ is only quasi-primary. A Virasoro primary is killed by every $L_n$ with $n>0$.

**Assuming positivity without checking unitarity.** The adjoint $L_n^\dagger=L_{-n}$ and positive norms are unitary assumptions. Ghost systems and logarithmic CFTs violate the usual positivity story.

## Relations to other pages

[Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) states the algebra. [Stress-Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/) derives it from the local stress-tensor product. This page explains how the modes act on fields and states.

[Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/) and [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/) develop the representation theory built from these generators. [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) explains what happens when descendant norms vanish. [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) turns contour deformation into differential equations for correlators.

The chapter [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) supplies the coordinate, cylinder, and OPE background. The chapter [Conformal Blocks](/cft-bootstrap/conformal-blocks/) later uses Virasoro generators to distinguish global blocks from Virasoro blocks.

## Research status

For ordinary two-dimensional CFT, the definition and action of Virasoro generators are settled textbook material.

Current research uses the same generators in more elaborate environments: logarithmic modules, chiral algebras from supersymmetric higher-dimensional theories, boundary and defect CFT, modular bootstrap, irrational CFT, holographic large-$c$ limits, and nonunitary statistical systems. The algebra is familiar; the hard part is often the representation category and its physical interpretation. Little algebra, big consequences. A classic 2D CFT mood.

## Exercises

### Exercise 1

Use the contour formula to derive the action of $L_n$ on a primary field of weight $h$.

<details><summary><strong>Solution</strong></summary>

Start with

$$
T(z)\mathcal O(w)
\sim
\frac{h\mathcal O(w)}{(z-w)^2}
+\frac{\partial\mathcal O(w)}{z-w}.
$$

Then

$$
[L_n,\mathcal O(w)]
=\frac{1}{2\pi i}\oint_w dz\,z^{n+1}T(z)\mathcal O(w).
$$

The simple pole term gives

$$
w^{n+1}\partial\mathcal O(w).
$$

The double pole term gives the derivative of $z^{n+1}$ evaluated at $w$:

$$
h(n+1)w^n\mathcal O(w).
$$

Therefore

$$
[L_n,\mathcal O(w)]
=
\left(w^{n+1}\partial+(n+1)h w^n\right)\mathcal O(w).
$$

</details>

### Exercise 2

Show that a primary state $|h\rangle=\mathcal O(0)|0\rangle$ is annihilated by $L_n$ for $n>0$.

<details><summary><strong>Solution</strong></summary>

Using the primary OPE at $w=0$,

$$
T(z)\mathcal O(0)
\sim
\frac{h\mathcal O(0)}{z^2}
+\frac{\partial\mathcal O(0)}{z}.
$$

Then

$$
L_n\mathcal O(0)|0\rangle
=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z)\mathcal O(0)|0\rangle.
$$

The two singular terms scale as $z^{n-1}$ and $z^n$. For $n>0$, neither contains a $z^{-1}$ residue. Hence

$$
L_n|h\rangle=0,
\qquad n>0.
$$

</details>

### Exercise 3

Compute the norm of $L_{-2}|h\rangle$ in a unitary highest-weight representation.

<details><summary><strong>Solution</strong></summary>

Using $L_n^\dagger=L_{-n}$,

$$
\|L_{-2}|h\rangle\|^2
=\langle h|L_2L_{-2}|h\rangle.
$$

Since $L_2|h\rangle=0$,

$$
\langle h|L_2L_{-2}|h\rangle
=\langle h|[L_2,L_{-2}]|h\rangle.
$$

The Virasoro algebra gives

$$
[L_2,L_{-2}]=4L_0+\frac{c}{2}.
$$

Therefore

$$
\|L_{-2}|h\rangle\|^2
=\left(4h+\frac{c}{2}\right)\langle h|h\rangle.
$$

For the vacuum $h=0$, this becomes $c/2$, matching $|T\rangle=L_{-2}|0\rangle$.

</details>

### Exercise 4

Why is the central term absent in $[L_1,L_{-1}]$ but present in $[L_2,L_{-2}]$?

<details><summary><strong>Solution</strong></summary>

The central term is proportional to

$$
m(m^2-1)\delta_{m+n,0}.
$$

For $m=1$, the factor is $1(1^2-1)=0$, so $[L_1,L_{-1}]$ has no central term and equals $2L_0$.

For $m=2$, the factor is $2(4-1)=6$, so

$$
\frac{c}{12}m(m^2-1)=\frac{c}{2}.
$$

Thus

$$
[L_2,L_{-2}]=4L_0+\frac{c}{2}.
$$

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984) 333–380.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- J. L. Cardy, “Conformal invariance and universality in finite-size scaling,” *Journal of Physics A* **17** (1984) L385.
- P. Polchinski, *String Theory*, Vol. 1, Cambridge University Press, 1998.

## Version history

- 2026-06-28: First polished draft. Defines Virasoro generators as stress-tensor modes, derives their action on primary fields and states, records the global subalgebra, vacuum module, adjoint, cylinder dictionary, and exercises.
