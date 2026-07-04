---
title: "Stress-Tensor OPE"
description: "Derives the two-dimensional stress-tensor operator product expansion and explains how its central term becomes the Virasoro central charge."
sidebar:
  label: "Stress-Tensor OPE"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Ginsparg 1988; Cardy 1984; Polchinski 1998"
topics:
  - two-dimensional CFT
  - stress tensor
  - operator product expansion
  - central charge
  - Virasoro algebra
canonicalTopics:
  - stress-tensor-ope
  - virasoro-central-charge
  - two-dimensional-conformal-symmetry
researchStatus:
  established:
    - "The holomorphic stress-tensor OPE is a standard local form of the Virasoro central extension in two-dimensional conformal field theory."
  active:
    - "Applications to logarithmic, nonunitary, boundary, defect, and chiral algebra settings require extra care with modules, contact terms, and positivity."
---

## Summary

The holomorphic stress tensor $T(z)$ is the local current for holomorphic conformal transformations. Its self-OPE is

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

This is one of the central formulas of two-dimensional CFT. The second and first order poles say that $T$ behaves like a field of holomorphic weight two under infinitesimal conformal transformations. The fourth order pole is the quantum central extension. Its coefficient is the central charge $c$.

The formula is local: it is an operator product expansion, not just a statement about expectation values. After contour integration it becomes the Virasoro algebra

$$
[L_m,L_n]
=(m-n)L_{m+n}
+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The antiholomorphic stress tensor $\bar T(\bar z)$ has an independent copy with central charge $\bar c$. For a parity-invariant bosonic CFT one usually has $c=\bar c$, but chiral theories and gravitationally anomalous systems need not.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/). The page also uses the contour language from [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) and prepares the next page, [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/).

## Core idea

A current algebra is a local symmetry algebra written as an OPE. For an ordinary holomorphic current $J(z)$, the current OPE records the symmetry generators and possible levels. For local conformal transformations, the current is the stress tensor $T(z)$, and the current algebra is the $TT$ OPE.

The slogan is

$$
\text{stress tensor OPE}
\quad\Longleftrightarrow\quad
\text{Virasoro algebra}.
$$

The word “Virasoro” is just the quantum name for the central extension of the holomorphic vector-field algebra on the punctured plane. The surprise is not that local conformal transformations form an infinite-dimensional algebra; that already follows from holomorphicity. The surprise is that the quantum theory allows a universal central term.

## Setup and conventions

We use Euclidean complex coordinates

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2,
\qquad
\partial\equiv \partial_z.
$$

In this chapter, $T(z)$ denotes the holomorphic CFT-normalized stress tensor. It is related to the real tensor components by convention-dependent factors fixed in [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/). The OPE convention is the usual radial-ordering convention:

$$
A(z)B(w)\sim \text{singular terms as }z\to w.
$$

Only singular terms are shown. Regular terms are real data too, but they are not fixed by the local Ward identity and do not affect the contour commutators discussed here.

The antiholomorphic sector is obtained by replacing

$$
z\to \bar z,
\qquad
T\to \bar T,
\qquad
c\to \bar c.
$$

Mixed singularities are absent in an ordinary local CFT away from contact terms:

$$
T(z)\bar T(\bar w)\sim \text{regular}.
$$

This statement is local on the plane. On boundaries, defects, curved backgrounds, or singular geometries, additional distributional terms can appear and should be handled separately.

## Stress tensor with a primary field

A holomorphic primary field $\mathcal O(w,\bar w)$ of weights $(h,\bar h)$ is defined by the singular OPE

$$
T(z)\mathcal O(w,\bar w)
\sim
\frac{h\,\mathcal O(w,\bar w)}{(z-w)^2}
+\frac{\partial_w\mathcal O(w,\bar w)}{z-w}.
$$

The first pole translates the insertion. The second pole rescales and rotates it with holomorphic weight $h$.

Equivalently, inserting a contour charge

$$
Q_\varepsilon=\frac{1}{2\pi i}\oint dz\,\varepsilon(z)T(z)
$$

around $w$ gives

$$
\delta_\varepsilon \mathcal O(w,\bar w)
=\frac{1}{2\pi i}\oint_w dz\,\varepsilon(z)T(z)\mathcal O(w,\bar w)
=
\varepsilon(w)\partial_w\mathcal O
+h\,\partial_w\varepsilon(w)\mathcal O.
$$

This is exactly the infinitesimal version of the finite primary transformation law

$$
\mathcal O(z,\bar z)
\mapsto
\left(\frac{dw}{dz}\right)^h
\left(\frac{d\bar w}{d\bar z}\right)^{\bar h}
\mathcal O(w,\bar w).
$$

The stress tensor is almost of this form with $h=2$, but not quite. The exception is the central term.

## The local form of the TT OPE

The universal stress-tensor self-OPE is

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Singular terms in the stress-tensor OPE](/figures/cft-bootstrap/stress-tensor-ope-singular-terms.svg)

<figcaption>

The $TT$ OPE says that $T$ behaves like a weight-two current, except for the fourth-order central singularity. The central term is invisible in classical conformal transformations but becomes decisive in the quantum representation theory.

</figcaption>
</figure>

The terms have different meanings.

| Term | Meaning |
|---|---|
| $\dfrac{c/2}{(z-w)^4}$ | Quantum central extension. It fixes $\langle T(z)T(w)\rangle$ and the Virasoro central term. |
| $\dfrac{2T(w)}{(z-w)^2}$ | $T$ has holomorphic weight two. |
| $\dfrac{\partial T(w)}{z-w}$ | $T$ is translated by local conformal transformations. |

The absence of a third-order pole is important. A third-order pole would correspond to a dimension-one object multiplying the identity in the $TT$ OPE, which would spoil the standard vacuum and Möbius-invariant normalization of the stress tensor. In ordinary CFT conventions, one chooses $\langle T\rangle_{\mathbb C}=0$, and the first nontrivial vacuum singularity is the fourth-order pole.

## Extracting the central charge

On the plane, with the conformally invariant vacuum normalized by

$$
\langle T(z)\rangle_{\mathbb C}=0,
$$

the $TT$ OPE gives

$$
\langle T(z)T(w)\rangle_{\mathbb C}
=\frac{c/2}{(z-w)^4}.
$$

Thus

$$
c=2\lim_{z\to w}(z-w)^4\langle T(z)T(w)\rangle_{\mathbb C}.
$$

This is one of the cleanest definitions of $c$ in a two-dimensional CFT.

There are two normalization warnings.

First, $c$ is defined after $T$ is fixed by Ward identities. If one rescales $T$ by hand, the OPE no longer generates the correctly normalized conformal transformations.

Second, $c$ is not the same object as the higher-dimensional $C_T$ normalization without convention-dependent conversion. In two dimensions, the holomorphic stress tensor has a central extension; in higher dimensions the stress-tensor two-point coefficient is not itself a Virasoro central charge.

## From the OPE to the Virasoro algebra

Define the modes by

$$
T(z)=\sum_{n\in\mathbb Z}L_n z^{-n-2},
\qquad
L_n=\frac{1}{2\pi i}\oint_0 dz\,z^{n+1}T(z).
$$

The commutator of modes is computed by nested radial contours:

$$
[L_m,L_n]
=
\frac{1}{(2\pi i)^2}
\oint_0 dw\,w^{n+1}
\oint_w dz\,z^{m+1}T(z)T(w).
$$

Only the singular terms in the OPE contribute. The simple-pole and double-pole terms give the classical vector-field bracket. The fourth-order pole gives the central term. The result is

$$
[L_m,L_n]
=(m-n)L_{m+n}
+\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

The central term vanishes for $m=-1,0,1$. Therefore $L_{-1},L_0,L_1$ form the global $SL(2,\mathbb C)$ holomorphic algebra without anomaly:

$$
[L_0,L_{-1}]=L_{-1},
\qquad
[L_0,L_1]=-L_1,
\qquad
[L_1,L_{-1}]=2L_0.
$$

This is why the vacuum can be invariant under global conformal transformations even when $c\ne 0$.

## Transformation of the stress tensor

For a primary field of weight $h$, a finite holomorphic map $z\mapsto w=f(z)$ gives a simple Jacobian factor. The stress tensor has an anomalous extra term:

$$
T_z(z)
=\left(\frac{dw}{dz}\right)^2 T_w(w)
+\frac{c}{12}\{w,z\}.
$$

Here

$$
\{w,z\}
=\frac{\partial_z^3 w}{\partial_z w}
-\frac{3}{2}\left(\frac{\partial_z^2 w}{\partial_z w}\right)^2
$$

is the Schwarzian derivative.

The Schwarzian vanishes for Möbius transformations,

$$
w=\frac{az+b}{cz+d},
\qquad
ad-bc\ne 0.
$$

That is another way to say that the anomaly affects local conformal transformations but not the global conformal subgroup.

For the cylinder map

$$
z=e^w,
\qquad
w=\tau+i\sigma,
$$

the cylinder stress tensor is

$$
T_{\rm cyl}(w)
=z^2T_{\rm plane}(z)-\frac{c}{24}.
$$

The shift $-c/24$ is the two-dimensional Casimir energy density on the cylinder. It is the same central charge reappearing in finite-size spectra and modular partition functions.

## Ward identity with one stress tensor

The $T\mathcal O$ OPE implies the holomorphic Ward identity

$$
\left\langle T(z)\prod_{i=1}^N\mathcal O_i(z_i,\bar z_i)\right\rangle
=
\sum_{i=1}^N
\left[
\frac{h_i}{(z-z_i)^2}
+\frac{1}{z-z_i}\partial_{z_i}
\right]
\left\langle \prod_{i=1}^N\mathcal O_i(z_i,\bar z_i)\right\rangle
$$

when all $\mathcal O_i$ are primaries and no other singularities are present.

With another stress tensor inserted, the $TT$ OPE adds the central pole:

$$
\langle T(z)T(w)\cdots\rangle
\sim
\frac{c/2}{(z-w)^4}\langle\cdots\rangle
+\frac{2}{(z-w)^2}\langle T(w)\cdots\rangle
+\frac{1}{z-w}\partial_w\langle T(w)\cdots\rangle.
$$

This compactly encodes how repeated infinitesimal conformal transformations fail to commute by the central extension.

## Examples

### Free boson

For one noncompact free boson $X$ with the standard normalization

$$
\partial X(z)\partial X(w)\sim -\frac{1}{(z-w)^2},
$$

the holomorphic stress tensor can be written

$$
T(z)=-\frac12 :\partial X\partial X:(z).
$$

A Wick-contraction computation gives

$$
T(z)T(w)
\sim
\frac{1/2}{(z-w)^4}
+\frac{2T(w)}{(z-w)^2}
+\frac{\partial T(w)}{z-w},
$$

so a single real free boson has

$$
c=1.
$$

### Free Majorana fermion

For a holomorphic Majorana fermion

$$
\psi(z)\psi(w)\sim \frac{1}{z-w},
$$

a standard stress tensor is

$$
T(z)=-\frac12:\psi\partial\psi:(z).
$$

It gives

$$
c=\frac12.
$$

This is the chiral half of the critical Ising CFT. The full diagonal Ising CFT has $c=\bar c=1/2$.

### Ghost systems

Ghost systems provide important nonunitary examples. The reparametrization $bc$ ghost system of bosonic string theory has

$$
c=-26.
$$

Negative central charge is not compatible with a positive-definite Hilbert space in the usual vacuum representation, but it is essential in gauge-fixed theories where ghost degrees of freedom cancel unphysical modes.

## Central charge and additivity

If two decoupled CFTs have stress tensors $T_1$ and $T_2$, the product theory has

$$
T=T_1+T_2.
$$

Since the two sectors have regular mixed OPEs,

$$
T_1(z)T_2(w)\sim \text{regular},
$$

the central charges add:

$$
c=c_1+c_2.
$$

This simple rule is used constantly in free-field constructions, cosets, ghost cancellations, string worldsheet theories, and rational CFT.

## What the OPE does not say by itself

The local $TT$ OPE determines the local Virasoro algebra, but it does not by itself determine the full CFT. To specify a CFT one still needs the spectrum of local operators, their OPE coefficients, modular properties when the theory is placed on a torus, global symmetry data, and locality constraints between chiral and antichiral sectors.

For example, many different $c=1$ theories exist. A free noncompact boson, a compact boson at different radii, and orbifolds can share the same value of $c$ but have different spectra and operator algebras. The central charge is a powerful invariant, not a complete fingerprint.

## Common pitfalls

**Treating the stress tensor as an ordinary primary.** The stress tensor is not a primary under the full local conformal group when $c\ne0$. It is quasi-primary under the global group because the Schwarzian vanishes for Möbius maps.

**Forgetting the factor of one half.** In the convention used here,

$$
\langle T(z)T(w)\rangle=\frac{c/2}{(z-w)^4}.
$$

Some references use different stress-tensor normalizations. Always translate before comparing quoted values of two-point coefficients.

**Thinking the central term is optional decoration.** The central term controls the cylinder vacuum energy, the Cardy growth of states, the Kac determinant, the unitarity classification of minimal models, and modular constraints. It is not a harmless extra constant.

**Confusing holomorphic and full central charges.** The full CFT has both $c$ and $\bar c$. In parity-invariant theories they are equal, but chiral theories can have $c\ne\bar c$.

**Using the plane formula on curved backgrounds without contact terms.** The OPE gives the singular local behavior in flat coordinates. Curved backgrounds, boundaries, and defects introduce additional geometric and distributional data.

## Relations to other pages

The page [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) states the algebraic structure. This page shows its local OPE origin. The page [Central Charge](/cft-bootstrap/virasoro-central-charge/central-charge/) explains the physical meanings of $c$; this page explains where $c$ enters the stress-tensor product.

The next page, [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/), turns the contour modes of $T$ into operators $L_n$ acting on states and fields. Later pages on [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/) and [Verma Modules](/cft-bootstrap/virasoro-central-charge/verma-modules/) use the same modes as representation-theoretic raising and lowering operators.

The page [Stress Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) in the broader OPE chapter discusses stress-tensor OPEs in general CFT language. This page is specifically the two-dimensional Virasoro-normalized holomorphic version.

## Research status

The $TT$ OPE and its Virasoro central extension are completely standard in ordinary two-dimensional CFT.

Active work appears in settings where one or more assumptions are changed: logarithmic CFT, nonunitary models, chiral algebras from higher-dimensional theories, boundaries and defects, celestial or warped variants, and theories with gravitational anomalies. In those cases, the local $TT$ OPE remains a guide, but the representation theory and positivity statements can change substantially.

## Exercises

### Exercise 1

Use the $TT$ OPE to compute the central term in $[L_m,L_n]$.

<details><summary><strong>Solution</strong></summary>

Use

$$
L_m=\frac{1}{2\pi i}\oint dz\,z^{m+1}T(z).
$$

The central contribution comes only from

$$
T(z)T(w)\sim \frac{c/2}{(z-w)^4}.
$$

Thus

$$
[L_m,L_n]_{\rm central}
=\frac{c}{2}\frac{1}{(2\pi i)^2}
\oint_0 dw\,w^{n+1}\oint_w dz\,\frac{z^{m+1}}{(z-w)^4}.
$$

The inner residue is

$$
\operatorname{Res}_{z=w}\frac{z^{m+1}}{(z-w)^4}
=\frac{1}{3!}\partial_w^3 w^{m+1}
=\frac{(m+1)m(m-1)}{6}w^{m-2}.
$$

Therefore

$$
[L_m,L_n]_{\rm central}
=\frac{c}{12}m(m^2-1)\frac{1}{2\pi i}\oint_0 dw\,w^{m+n-1}
=\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

</details>

### Exercise 2

Show that the Schwarzian derivative of $z=e^w$ with respect to $w$ is $-1/2$.

<details><summary><strong>Solution</strong></summary>

For $z=e^w$,

$$
\partial_w z=z,
\qquad
\partial_w^2 z=z,
\qquad
\partial_w^3 z=z.
$$

Hence

$$
\{z,w\}
=\frac{\partial_w^3 z}{\partial_w z}-\frac32\left(\frac{\partial_w^2 z}{\partial_w z}\right)^2
=1-\frac32
=-\frac12.
$$

Therefore

$$
T_{\rm cyl}(w)=z^2T(z)+\frac{c}{12}\{z,w\}
=z^2T(z)-\frac{c}{24}.
$$

</details>

### Exercise 3

Why does the central term vanish inside the global subalgebra generated by $L_{-1},L_0,L_1$?

<details><summary><strong>Solution</strong></summary>

The central coefficient is

$$
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

For $m=-1,0,1$, the factor $m(m^2-1)$ is zero. Thus the anomaly does not affect the $SL(2,\mathbb C)$ global conformal subalgebra. This is why a nonzero central charge is compatible with a globally conformally invariant vacuum on the plane.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984) 333–380.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- J. L. Cardy, “Conformal invariance and universality in finite-size scaling,” *Journal of Physics A* **17** (1984) L385.
- P. Polchinski, *String Theory*, Vol. 1, Cambridge University Press, 1998.

## Version history

- 2026-06-28: First polished draft. Fixes the $TT$ OPE convention, central-charge extraction, Schwarzian transformation, cylinder shift, examples, and contour derivation of the Virasoro central term.
