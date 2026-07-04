---
title: "Stress Tensor in 2D"
description: "Explains the holomorphic stress tensor of two-dimensional CFT, its Ward identities, central charge, and first Virasoro consequences."
sidebar:
  label: "Stress Tensor in 2D"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; BPZ 1984; Ginsparg 1988; Polchinski 1998"
topics:
  - two-dimensional CFT
  - stress tensor
  - conformal Ward identities
  - central charge
  - Virasoro algebra
canonicalTopics:
  - two-dimensional-stress-tensor
  - stress-tensor-ward-identity
  - virasoro-central-charge-preview
  - conformal-current-modes
researchStatus:
  established:
    - "In a flat two-dimensional CFT, conservation and tracelessness split the stress tensor into holomorphic and antiholomorphic components whose OPEs generate conformal transformations and the Virasoro algebra."
  active:
    - "Subtleties appear when the theory has boundaries, defects, nontrivial spin structure, logarithmic sectors, curved backgrounds, or a gravitational anomaly with different left and right central charges."
---

## Summary

The stress tensor is the local current for spacetime transformations. In a two-dimensional CFT it becomes much more than a conserved tensor: after going to complex coordinates and using conformal invariance, it splits into two chiral fields,

$$
T(z),
\qquad
\bar T(\bar z),
$$

with

$$
\bar\partial T(z)=0,
\qquad
\partial \bar T(\bar z)=0,
$$

away from operator insertions and contact terms.

We normalize $T(z)$ by its OPE with a primary field $\phi$ of weights $(h,\bar h)$:

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

This formula is the local Ward identity in its most compact form. The double pole says that $\phi$ has holomorphic weight $h$. The simple pole says that $T$ generates translations in $z$.

The stress tensor also has a universal self-OPE,

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w},
$$

and similarly for $\bar T$ with central charge $\bar c$. This is the doorway to the Virasoro algebra. The constant $c$ is not merely a normalization artifact: it controls the conformal anomaly, cylinder vacuum energy, density of states, and many exact constraints in two-dimensional CFT.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/), and the general [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/).

It is also helpful to have seen [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/). This page previews the Virasoro algebra; the full representation theory appears later in the Virasoro chapter.

## Core idea

The core idea is that, in two dimensions, the stress tensor is the machine that turns local conformal transformations into contour integrals.

For a holomorphic vector field $\epsilon(z)\partial_z$, define the charge

$$
Q_\epsilon
=
\frac{1}{2\pi i}\oint dz\,\epsilon(z)T(z).
$$

If the contour surrounds a primary operator $\phi(w,\bar w)$, then the $T\phi$ OPE gives

$$
[Q_\epsilon,\phi(w,\bar w)]
=
\left(\epsilon(w)\partial_w+h\,\partial\epsilon(w)\right)\phi(w,\bar w),
$$

up to the usual convention-dependent sign between active and passive variations. Thus one local OPE encodes translations, rotations, dilatations, special conformal transformations, and all local holomorphic conformal transformations.

<figure class="doc-figure" style="--figure-width: 44rem;">

![The holomorphic stress tensor generates local conformal transformations through contour integrals around operator insertions.](/figures/cft-bootstrap/two-dimensional-stress-tensor-ward.svg)

<figcaption>

The contour integral of $\epsilon(z)T(z)$ can be shrunk onto local insertions. The poles in the $T\phi$ OPE produce the primary transformation law: the simple pole translates the operator and the double pole measures its holomorphic weight.

</figcaption>
</figure>

## Setup and conventions

We work on a flat Euclidean patch with

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2,
$$

and

$$
\partial=\partial_z,
\qquad
\bar\partial=\partial_{\bar z},
\qquad
ds^2=dz\,d\bar z.
$$

The physical stress tensor is defined by varying the theory with respect to the metric. Different books distribute factors of $2\pi$, signs, and Euclidean continuation differently. In this CFT chapter, the **CFT-normalized holomorphic stress tensor** is the operator $T(z)$ whose OPE with primaries is

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w}.
$$

This OPE fixes the normalization relevant for Virasoro modes, conformal blocks, and Ward identities. When comparing to a stress tensor defined as $T_{ab}^{\mathrm{phys}}=-4\pi\delta S/\delta g^{ab}$ or with another convention, translate by matching this OPE.

For the antiholomorphic stress tensor,

$$
\bar T(\bar z)\phi(w,\bar w)
\sim
\frac{\bar h\phi(w,\bar w)}{(\bar z-\bar w)^2}
+
\frac{\bar\partial\phi(w,\bar w)}{\bar z-\bar w}.
$$

The mixed OPE $T(z)\bar T(\bar w)$ is nonsingular in an ordinary local product CFT away from contact terms.

## From conservation to holomorphy

In real coordinates, the stress tensor obeys conservation

$$
\partial^a T_{ab}=0
$$

and, in a conformal theory on flat space after improvement,

$$
T^a_{\ a}=0.
$$

In complex coordinates the components are $T_{zz}$, $T_{\bar z\bar z}$, and $T_{z\bar z}$. Tracelessness sets

$$
T_{z\bar z}=0
$$

up to contact terms and possible anomaly terms on curved backgrounds. Conservation then becomes

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0.
$$

Thus the stress tensor separates into a holomorphic component and an antiholomorphic component:

$$
T(z)\sim T_{zz}(z),
\qquad
\bar T(\bar z)\sim T_{\bar z\bar z}(\bar z),
$$

where $\sim$ hides only the normalization convention just discussed.

This is the local origin of holomorphic factorization. The stress tensor is not merely conserved. It is chiral.

:::caution[Contact terms matter]
Equations such as $\bar\partial T(z)=0$ are true away from insertions. Inside correlation functions, derivatives can hit singularities and produce contact terms. Those contact terms are exactly what Ward identities measure. Dropping them too early is the 2D CFT version of losing the plot while holding all the symbols.
:::

## Ward identity from the OPE

Let

$$
X=\prod_i \phi_i(z_i,\bar z_i)
$$

be a product of primary fields. Suppose $\epsilon(z)$ is holomorphic in a region containing the insertions. Insert $T(z)$ and integrate over a contour $C$ enclosing all $z_i$:

$$
\frac{1}{2\pi i}\oint_C dz\,\epsilon(z)\langle T(z)X\rangle.
$$

Deforming $C$ into small contours $C_i$ around each insertion and using the $T\phi_i$ OPE gives

$$
\frac{1}{2\pi i}\oint_C dz\,\epsilon(z)\langle T(z)X\rangle
=
\sum_i
\left(
\epsilon(z_i)\partial_{z_i}
+h_i\partial\epsilon(z_i)
\right)
\langle X\rangle.
$$

This is the holomorphic conformal Ward identity. The antiholomorphic identity is obtained by replacing

$$
T,z,h,\partial
\quad\longrightarrow\quad
\bar T,\bar z,\bar h,\bar\partial.
$$

For the global vector fields

$$
\epsilon(z)=1,
\qquad
\epsilon(z)=z,
\qquad
\epsilon(z)=z^2,
$$

the Ward identity enforces translation, dilatation/rotation, and special conformal invariance. For general holomorphic $\epsilon(z)$, it gives the local conformal Ward identities that lead to Virasoro constraints.

## The stress tensor as a field

The stress tensor is not a primary field. It is a quasi-primary field under global conformal transformations and transforms anomalously under general local conformal maps.

In the standard normalization,

$$
T_{\mathrm{new}}(w)
=
\left(\frac{dz}{dw}\right)^2T_{\mathrm{old}}(z)
+
\frac{c}{12}\{z,w\},
$$

where the Schwarzian derivative is

$$
\{z,w\}
=
\frac{z'''(w)}{z'(w)}
-
\frac{3}{2}\left(\frac{z''(w)}{z'(w)}\right)^2.
$$

The Schwarzian term is the local sign that $T$ is not an ordinary primary of weight $(2,0)$. It is also the bridge from the $TT$ OPE to cylinder vacuum energy and the conformal anomaly.

For a primary of weight $h$, the transformation law has no Schwarzian:

$$
\phi_{\mathrm{new}}(w,\bar w)
=
\left(\frac{dz}{dw}\right)^h
\left(\frac{d\bar z}{d\bar w}\right)^{\bar h}
\phi_{\mathrm{old}}(z,\bar z).
$$

The exceptional behavior of $T$ is not a defect. It is what allows the quantum theory to remember the central charge.

## The TT OPE and central charge

The most important OPE in two-dimensional CFT is

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

The coefficient $c$ is the holomorphic central charge. Similarly,

$$
\bar T(\bar z)\bar T(\bar w)
\sim
\frac{\bar c/2}{(\bar z-\bar w)^4}
+
\frac{2\bar T(\bar w)}{(\bar z-\bar w)^2}
+
\frac{\bar\partial \bar T(\bar w)}{\bar z-\bar w}.
$$

The central charge appears in several related ways:

| Appearance | Meaning |
|---|---|
| $TT$ OPE | central extension of local conformal transformations |
| Schwarzian term | anomalous transformation of $T$ under local conformal maps |
| cylinder energy | Casimir energy on a circle |
| curved background | Weyl or trace anomaly |
| modular bootstrap | controls the asymptotic density of states |

For a parity-invariant bosonic CFT on a closed oriented surface one often has

$$
c=\bar c.
$$

If $c-\bar c\neq0$, the theory has a gravitational anomaly: the left and right sectors carry different chiral central charge. Such theories can still appear as chiral boundary theories of higher-dimensional topological phases, but they require extra care as stand-alone local theories on arbitrary curved backgrounds.

## Virasoro modes

Expand the holomorphic stress tensor on the plane as

$$
T(z)=\sum_{n\in\mathbb Z}\frac{L_n}{z^{n+2}}.
$$

Equivalently,

$$
L_n=\frac{1}{2\pi i}\oint dz\,z^{n+1}T(z).
$$

The $TT$ OPE implies

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

This is the Virasoro algebra. The antiholomorphic modes obey the same algebra with $\bar c$, and the two sectors commute:

$$
[L_m,\bar L_n]=0.
$$

The global conformal generators are

$$
L_{-1},\quad L_0,
\quad L_1,
$$

and their barred partners. The central term vanishes inside this global $SL(2,\mathbb C)$ subalgebra because $m(m^2-1)=0$ for $m=-1,0,1$.

For a primary field,

$$
[L_n,\phi(w,\bar w)]
=
\left(w^{n+1}\partial_w+h(n+1)w^n\right)\phi(w,\bar w).
$$

This follows immediately by inserting the $T\phi$ OPE into the contour definition of $L_n$.

## Examples

### Free boson

For a canonically normalized free scalar field $X(z,\bar z)$ with

$$
X(z,\bar z)X(0,0)\sim -\log |z|^2,
$$

the holomorphic stress tensor is

$$
T(z)=-\frac{1}{2}:\!\partial X\partial X\!:.
$$

Its central charge is

$$
c=1.
$$

Vertex operators $V_k=e^{ikX}$ have weights depending on the normalization of $X$ and the compactification radius. This example is the workhorse behind compact bosons, Coulomb-gas methods, and many string worldsheet calculations.

### Free Majorana fermion

For a chiral Majorana fermion with

$$
\psi(z)\psi(w)\sim\frac{1}{z-w},
$$

the stress tensor is

$$
T(z)=-\frac{1}{2}:\!\psi\partial\psi\!:,
$$

and

$$
c=\frac{1}{2}.
$$

The Ising CFT has this central charge, though its full operator content includes spin and disorder fields not built as simple local polynomials of $\psi$.

### Ghost systems

In string theory and gauge-fixed CFTs, ghost systems contribute central charges that can be negative. This is not a paradox; the ghost theory is not a unitary standalone matter CFT. For the bosonic string, matter and ghost central charges cancel in the critical dimension.

## Common pitfalls

1. **Forgetting normalization.** The physical stress tensor from metric variation and the CFT-normalized $T(z)$ can differ by factors of $2\pi$ and signs. Match the $T\phi$ OPE before comparing formulas.

2. **Calling $T$ primary.** The stress tensor behaves like a weight-two field under global conformal transformations, but under a general local conformal transformation it has a Schwarzian shift.

3. **Treating holomorphy as an operator equation without contact terms.** Inside correlators, $\bar\partial T(z)$ produces delta-function support at operator insertions.

4. **Confusing $c$ with the number of fields.** For free unitary bosons and fermions, $c$ loosely counts degrees of freedom. In interacting, chiral, nonunitary, or ghost systems, that slogan can mislead.

5. **Assuming $c=\bar c$ automatically.** Many parity-invariant local CFTs have $c=\bar c$, but chiral theories and anomalous boundary theories can have $c\neq\bar c$.

## Relations to other pages

This page supplies the stress-tensor technology used in [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

The full algebraic consequences are developed in [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Central Charge](/cft-bootstrap/virasoro-central-charge/central-charge/), [TT OPE and Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/tt-ope-and-virasoro-algebra/), and [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/).

For the higher-dimensional perspective, compare [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) and [Stress Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/). The 2D stress tensor is special because it is chiral and generates infinitely many local conformal transformations.

## Research status

The local formulas on this page are established textbook material. They are the backbone of two-dimensional CFT, string worldsheet theory, statistical-mechanics applications, and rational CFT.

Active directions concern the global and categorical consequences: modular tensor categories, logarithmic CFT, nonsemisimple chiral algebras, boundaries and defects, gravitational anomalies, entanglement, and the relation of chiral central charge to topological phases of matter.

## Exercises

### Exercise 1: Holomorphy from conservation

Assume $T_{z\bar z}=0$ and stress-tensor conservation in flat complex coordinates. Show that $T_{zz}$ is holomorphic and $T_{\bar z\bar z}$ is antiholomorphic away from insertions.

<details><summary><strong>Solution</strong></summary>

In complex coordinates the conservation equations can be written schematically as

$$
\bar\partial T_{zz}+\partial T_{\bar z z}=0,
\qquad
\partial T_{\bar z\bar z}+\bar\partial T_{z\bar z}=0.
$$

Tracelessness gives $T_{z\bar z}=T_{\bar z z}=0$ on flat space away from contact terms. Therefore

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0.
$$

Thus $T_{zz}$ depends only on $z$ and $T_{\bar z\bar z}$ depends only on $\bar z$ locally.

</details>

### Exercise 2: Primary transformation from the OPE

Using

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial\phi(w,\bar w)}{z-w},
$$

show that

$$
[Q_\epsilon,\phi(w,\bar w)]
=
(\epsilon\partial+h\partial\epsilon)\phi(w,\bar w),
$$

where $Q_\epsilon=(2\pi i)^{-1}\oint dz\,\epsilon(z)T(z)$.

<details><summary><strong>Solution</strong></summary>

Insert the OPE into the contour integral:

$$
[Q_\epsilon,\phi]
=
\frac{1}{2\pi i}\oint_w dz\,\epsilon(z)
\left(
\frac{h\phi(w)}{(z-w)^2}+
\frac{\partial\phi(w)}{z-w}
\right).
$$

The simple pole gives

$$
\frac{1}{2\pi i}\oint_w dz\,\frac{\epsilon(z)}{z-w}\partial\phi(w)
=\epsilon(w)\partial\phi(w).
$$

The double pole gives

$$
\frac{1}{2\pi i}\oint_w dz\,\frac{\epsilon(z)}{(z-w)^2}h\phi(w)
=h\partial\epsilon(w)\phi(w).
$$

Adding the two residues gives the stated result.

</details>

### Exercise 3: Global modes have no central term

Use the Virasoro commutator to show that the subalgebra generated by $L_{-1},L_0,L_1$ has no central extension.

<details><summary><strong>Solution</strong></summary>

The central term is

$$
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

For $m=-1,0,1$, the factor $m(m^2-1)$ vanishes. Hence the central term is zero within the global subalgebra. The remaining commutators are

$$
[L_m,L_n]=(m-n)L_{m+n},
\qquad m,n=-1,0,1,
$$

which is the Lie algebra of holomorphic global conformal transformations.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters 5–6.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* 241 (1984).
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures (1988).
- J. Polchinski, *String Theory*, Vol. 1, chapters 2–3.
- P. Bouwknegt and K. Schoutens, “W-symmetry in conformal field theory,” *Physics Reports* 223 (1993).

## Version history

- 2026-06-28: First polished draft. Fixes the CFT-normalized stress-tensor convention, derives the local Ward identity, previews the $TT$ OPE and Virasoro modes, and records common normalization pitfalls.
