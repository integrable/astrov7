---
title: "Holomorphic Factorization"
description: "Explains the left–right decomposition of two-dimensional CFT into holomorphic and antiholomorphic sectors, and why full correlators are usually sums of products of chiral blocks."
sidebar:
  label: "Holomorphic Factorization"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; BPZ 1984; Moore–Seiberg 1988–1989; Ginsparg 1988"
topics:
  - two-dimensional CFT
  - holomorphic factorization
  - chiral algebra
  - conformal blocks
  - modular invariance
  - left and right movers
canonicalTopics:
  - holomorphic-factorization
  - chiral-decomposition
  - left-right-sector-pairing
  - two-dimensional-conformal-blocks
researchStatus:
  established:
    - "The local Ward identities of a 2D CFT split into holomorphic and antiholomorphic parts, so correlators decompose into sums of products of left and right conformal blocks."
  active:
    - "Classifying consistent pairings of chiral data remains a deep problem in rational CFT, logarithmic CFT, defects, boundaries, and categorical formulations of 2D QFT."
---

## Summary

Holomorphic factorization is the statement that two-dimensional conformal symmetry splits local kinematics into a holomorphic sector and an antiholomorphic sector. The stress tensor separates as

$$
\bar\partial T(z)=0,
\qquad
\partial \bar T(\bar z)=0,
$$

and local fields are organized by two weights,

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

At the level of states, a typical 2D CFT Hilbert space decomposes schematically as

$$
\mathcal H
=
\bigoplus_{i,\bar j}M_{i\bar j}\,\mathcal V_i\otimes\bar{\mathcal V}_{\bar j},
$$

where $\mathcal V_i$ and $\bar{\mathcal V}_{\bar j}$ are left and right chiral modules, and $M_{i\bar j}$ records how they are paired in the full local theory.

For correlation functions, the crucial formula is not usually “one holomorphic function times one antiholomorphic function.” It is

$$
\left\langle\prod_a\Phi_a(z_a,\bar z_a)\right\rangle
=
\sum_{\alpha,\bar\alpha}
C_{\alpha\bar\alpha}\,
\mathcal F_\alpha(z_a)\,\bar{\mathcal F}_{\bar\alpha}(\bar z_a).
$$

The $\mathcal F_\alpha$ are chiral conformal blocks. They may be multivalued. The full correlator must be single-valued, local, crossing-consistent, and compatible with the chosen spectrum. Holomorphic factorization is therefore a decomposition plus a gluing problem.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), and [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/).

If you have not yet seen the Virasoro algebra, you can still read this page as a conceptual guide. The detailed mode algebra appears in [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/).

## Core idea

The core idea is that 2D conformal symmetry has two independent local halves:

$$
\text{local conformal symmetry}
=
\text{left-moving holomorphic symmetry}
\times
\text{right-moving antiholomorphic symmetry}.
$$

This gives two commuting operator algebras,

$$
[L_m,L_n]
=
(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0},
$$

and

$$
[\bar L_m,\bar L_n]
=
(m-n)\bar L_{m+n}+\frac{\bar c}{12}m(m^2-1)\delta_{m+n,0},
\qquad
[L_m,\bar L_n]=0.
$$

Local fields carry representations of both algebras. Chiral calculations can often be done separately in the two sectors, but a physical local CFT is not merely a list of left modules and right modules. It also includes a consistent pairing of left and right data.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A full local correlator is assembled from holomorphic and antiholomorphic conformal blocks.](/figures/cft-bootstrap/holomorphic-factorization-blocks.svg)

<figcaption>

Holomorphic factorization separates the local Ward-identity problem into left and right conformal blocks. The full correlator is a single-valued pairing of those blocks, not usually a single product.

</figcaption>
</figure>

## Setup and conventions

On the plane, the Euclidean stress tensor has components $T_{zz}$, $T_{\bar z\bar z}$, and $T_{z\bar z}$. In a conformal theory on flat space, after improvement and away from contact terms,

$$
T_{z\bar z}=0.
$$

Conservation then gives

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0.
$$

We write

$$
T(z)\equiv T_{zz}(z),
\qquad
\bar T(\bar z)\equiv T_{\bar z\bar z}(\bar z),
$$

up to normalization conventions fixed by the $T\phi$ OPE.

A primary field has weights $(h,\bar h)$ and transforms as

$$
\Phi(z,\bar z)
\mapsto
\left(f'(z)\right)^h
\left(\bar f'(\bar z)\right)^{\bar h}
\Phi(f(z),\bar f(\bar z))
$$

in the active convention. Its scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

In a bosonic local CFT on the plane, mutual locality usually requires appropriate integrality conditions on spins and OPE monodromies. In fermionic CFTs or theories with spin structure, half-integer spins and spin-structure dependence enter.

## Chiral fields and chiral algebras

A field $W(z)$ is holomorphic, or chiral, if

$$
\bar\partial W(z)=0
$$

as an operator equation away from contact terms. The stress tensor $T(z)$ is the universal example. Conserved currents in WZW models and many rational CFTs give additional examples.

A chiral field has weights $(h,0)$ and OPEs of the form

$$
W_a(z)W_b(0)
\sim
\sum_c\sum_{n}
\frac{C_{ab}^{\phantom{ab}c,n}\,\partial^n W_c(0)}
{z^{h_a+h_b-h_c-n}}.
$$

The collection of holomorphic fields closed under OPE is called a chiral algebra. The minimal chiral algebra of any 2D CFT contains the Virasoro algebra generated by $T(z)$. Some theories have a larger one: affine Kac–Moody algebras, $\mathcal W$-algebras, superconformal algebras, or other vertex-operator algebras.

The antiholomorphic sector has its own chiral algebra generated by $\bar T(\bar z)$ and possible antiholomorphic currents.

:::note[Terminology]
Physicists often say “holomorphic factorization” for several related ideas: left–right splitting of Ward identities, decomposition into conformal blocks, factorization of the Hilbert space into chiral modules, or the special case of a purely chiral theory. Always check which meaning is intended.
:::

## Hilbert-space decomposition

In radial quantization, states decompose into representations of the left and right chiral algebras. For the Virasoro algebra alone, a primary state obeys

$$
L_0|h,\bar h\rangle=h|h,\bar h\rangle,
\qquad
\bar L_0|h,\bar h\rangle=\bar h|h,\bar h\rangle,
$$

and

$$
L_n|h,\bar h\rangle=\bar L_n|h,\bar h\rangle=0,
\qquad n>0.
$$

Descendants are generated independently:

$$
L_{-n_1}\cdots L_{-n_k}\bar L_{-m_1}\cdots\bar L_{-m_r}|h,\bar h\rangle.
$$

Thus a full local primary labels a tensor product of a left representation and a right representation. The Hilbert space takes the schematic form

$$
\mathcal H
=
\bigoplus_{i,\bar j}M_{i\bar j}\,\mathcal V_i\otimes\bar{\mathcal V}_{\bar j}.
$$

Here $M_{i\bar j}$ is a matrix of nonnegative integers. In a diagonal theory,

$$
M_{i\bar j}=\delta_{i\bar j},
$$

after identifying the left and right labels. Non-diagonal theories pair left and right sectors in more interesting ways. These pairings are not optional decoration: they determine which local operators exist.

## Correlators as sums of block products

The simplest misleading slogan is

$$
\text{2D correlator}=\text{holomorphic part}\times\text{antiholomorphic part}.
$$

A better slogan is

$$
\text{2D correlator}=\sum \text{left block}\times\text{right block}.
$$

Consider a four-point function of local fields. After extracting fixed kinematic factors, it depends on cross-ratios $z$ and $\bar z$:

$$
G(z,\bar z).
$$

Using the OPE in one channel gives a conformal-block expansion

$$
G(z,\bar z)
=
\sum_{p,\bar p}C_{12}^{\phantom{12}p,\bar p}C_{34}^{\phantom{34}p,\bar p}\,
\mathcal F_p(z)\,\bar{\mathcal F}_{\bar p}(\bar z).
$$

The left block $\mathcal F_p(z)$ solves the holomorphic Ward-identity and representation-theory problem. The right block $\bar{\mathcal F}_{\bar p}(\bar z)$ solves the antiholomorphic problem. The full correlator chooses a sum of products that is single-valued and crossing-consistent.

This is why conformal blocks are not themselves usually physical correlators. They are building blocks. They can have branch cuts and monodromy. The physical correlator is the monodromy-safe combination.

## OPE factorization

The local OPE of two primary fields has the schematic form

$$
\Phi_i(z,\bar z)\Phi_j(0,0)
=
\sum_k C_{ij}^{\phantom{ij}k}
 z^{h_k-h_i-h_j}
 \bar z^{\bar h_k-\bar h_i-\bar h_j}
\left[\Phi_k(0,0)+\text{descendants}\right].
$$

The descendant part factorizes into holomorphic and antiholomorphic descendants. In a Virasoro theory, these are generated by $L_{-n}$ and $\bar L_{-n}$ independently. In an extended chiral algebra, the descendant tower is generated by the larger chiral algebra.

This factorization makes the OPE efficient: once the primary spectrum, two-point metric, and OPE coefficients are known, the conformal symmetry determines the descendant contributions. That is the two-dimensional version of the general CFT-data idea, sharpened by the infinite-dimensional symmetry.

## Characters and torus partition functions

Holomorphic factorization is also visible on the torus. Define

$$
q=e^{2\pi i\tau},
\qquad
\bar q=e^{-2\pi i\bar\tau}.
$$

A chiral character is

$$
\chi_i(q)=\operatorname{Tr}_{\mathcal V_i}q^{L_0-c/24}.
$$

The full torus partition function is

$$
Z(\tau,\bar\tau)
=
\operatorname{Tr}_{\mathcal H}
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}
=
\sum_{i,\bar j}M_{i\bar j}\chi_i(q)\bar\chi_{\bar j}(\bar q).
$$

On a consistent bosonic CFT on a closed oriented torus, $Z$ must have the appropriate modular behavior under

$$
\tau\mapsto\tau+1,
\qquad
\tau\mapsto -\frac1\tau.
$$

This modular constraint is one of the main ways global consistency restricts the pairing matrix $M_{i\bar j}$.

## Examples

### Free compact boson

For a free compact boson, one writes locally

$$
X(z,\bar z)=X_L(z)+X_R(\bar z).
$$

Vertex operators factor into left and right pieces,

$$
V_{p_L,p_R}(z,\bar z)
=
:e^{i p_L X_L(z)}::e^{i p_R X_R(\bar z)}:.
$$

In a common normalization,

$$
h=\frac{p_L^2}{2},
\qquad
\bar h=\frac{p_R^2}{2}.
$$

But the allowed pairs $(p_L,p_R)$ are not arbitrary. Compactification, winding, momentum quantization, and mutual locality choose a lattice of allowed left–right momenta. This is the gluing data.

### Ising CFT

The critical Ising model has a small set of primary fields, but its spin-field four-point function is not just one holomorphic block times one antiholomorphic block. It is a sum of products of blocks, chosen so that the full correlator is single-valued and has the correct OPE limits.

This is the clean beginner example of the central caveat:

$$
\text{chiral blocks are not automatically local correlators}.
$$

### WZW models

In a WZW model, holomorphic currents $J^a(z)$ and antiholomorphic currents $\bar J^a(\bar z)$ generate affine Lie algebras. The chiral representations are labeled by integrable highest weights at level $k$. A full local theory must choose a modular-invariant pairing of left and right affine representations.

Diagonal pairings are common, but non-diagonal modular invariants and extended chiral algebras are essential in the broader classification of rational CFTs.

## What holomorphic factorization does not mean

Holomorphic factorization does **not** mean every field is holomorphic. A generic local field has both $h$ and $\bar h$ nonzero.

It does **not** mean a full correlator is one product $f(z)\bar f(\bar z)$. That happens in special cases, but generic correlators are sums over block pairings.

It does **not** mean the left and right sectors are physically independent. Locality, modular invariance, spin selection rules, boundary conditions, and defects can strongly constrain how they are glued.

It does **not** mean every 2D CFT is rational. Rational CFTs have finitely many irreducible chiral modules with respect to a chosen chiral algebra. Many important CFTs are not rational.

## Boundaries and defects

On a space with boundary, the left and right sectors are no longer independent in the same way. A conformal boundary condition typically imposes a gluing relation such as

$$
T(z)=\bar T(\bar z)
$$

on the boundary, possibly with an automorphism for extended currents. This is why boundary CFT often replaces an $n$-point function on a half-plane by a chiral $2n$-point problem on the full plane, using a method-of-images logic.

Defects and interfaces can also act on the gluing data. Topological defects may commute with the chiral algebra, implement symmetries, or realize non-invertible fusion rules. Thus holomorphic factorization is the starting point, not the end of the story.

## Common pitfalls

**Pitfall 1: treating a chiral block as a physical correlator.**

A chiral block can be multivalued under analytic continuation. Physical local correlators must have acceptable monodromy.

**Pitfall 2: forgetting the pairing matrix.**

The same left chiral algebra can support different full CFTs depending on how left and right sectors are paired.

**Pitfall 3: assuming diagonal pairing.**

Diagonal theories are pedagogically convenient, but non-diagonal modular invariants and extended chiral algebras are not exotic footnotes. They are central in rational CFT.

**Pitfall 4: confusing holomorphic with meromorphic.**

Chiral correlators are holomorphic away from operator insertions, where they have prescribed singularities. On compact surfaces, global meromorphic data are constrained strongly.

**Pitfall 5: ignoring anomalies.**

If $c\neq\bar c$, the theory has a gravitational anomaly. Such theories can still be meaningful, especially as chiral theories or edge theories, but they require extra care as standalone nonchiral CFTs on arbitrary curved backgrounds.

## Relations to other pages

This page follows [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/) and prepares [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), and [Cylinder-Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/).

It also connects directly to [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/) and [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/). Later, the same ideas return in [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), and [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/).

## Research status

The left–right decomposition of local 2D conformal symmetry, Virasoro representations, chiral blocks, and modular-invariant partition functions are standard parts of the subject.

The classification and construction problems remain rich. Active and advanced areas include logarithmic CFT, nonsemisimple tensor categories, boundary and defect CFT, non-invertible symmetries, holomorphic VOAs, moonshine, rational versus irrational CFT, and the appearance of chiral algebras in higher-dimensional supersymmetric theories.

## Exercises

### Exercise 1: Conservation implies holomorphicity

Assume flat-space conformal invariance gives $T_{z\bar z}=0$ away from contact terms. Use stress-tensor conservation to show that $T_{zz}$ is holomorphic and $T_{\bar z\bar z}$ is antiholomorphic.

<details><summary><strong>Solution</strong></summary>

In complex coordinates, conservation implies equations of the form

$$
\bar\partial T_{zz}+\partial T_{\bar z z}=0,
\qquad
\partial T_{\bar z\bar z}+\bar\partial T_{z\bar z}=0.
$$

With $T_{z\bar z}=T_{\bar z z}=0$ away from contact terms, these reduce to

$$
\bar\partial T_{zz}=0,
\qquad
\partial T_{\bar z\bar z}=0.
$$

Thus $T(z)=T_{zz}$ is holomorphic and $\bar T(\bar z)=T_{\bar z\bar z}$ is antiholomorphic.

</details>

### Exercise 2: Spin from left and right weights

Under a rotation $z\mapsto e^{i\theta}z$, show that a primary of weights $(h,\bar h)$ has spin $s=h-\bar h$.

<details><summary><strong>Solution</strong></summary>

For a passive rotation,

$$
\frac{dw}{dz}=e^{i\theta},
\qquad
\frac{d\bar w}{d\bar z}=e^{-i\theta}.
$$

The primary transformation gives the phase

$$
e^{-i h\theta}e^{i\bar h\theta}=e^{-i(h-\bar h)\theta}.
$$

Therefore the spin is

$$
s=h-\bar h.
$$

The sign in the phase depends on active versus passive convention, but the spin assignment does not.

</details>

### Exercise 3: Why a single chiral block can fail locality

Suppose a chiral block behaves near $z=0$ as $z^\alpha$. What condition must hold for the product $z^\alpha\bar z^{\bar\alpha}$ to be single-valued around $z=0$?

<details><summary><strong>Solution</strong></summary>

Taking $z\mapsto e^{2\pi i}z$ and $\bar z\mapsto e^{-2\pi i}\bar z$ gives

$$
z^\alpha\bar z^{\bar\alpha}
\mapsto
 e^{2\pi i\alpha}e^{-2\pi i\bar\alpha}z^\alpha\bar z^{\bar\alpha}.
$$

Single-valuedness requires

$$
\alpha-\bar\alpha\in\mathbb Z.
$$

For full correlators with several blocks, the condition is more general: the full sum must have trivial allowed monodromy, even if individual blocks mix under analytic continuation.

</details>

### Exercise 4: Character decomposition

Given

$$
\mathcal H
=
\bigoplus_{i,\bar j}M_{i\bar j}\,\mathcal V_i\otimes\bar{\mathcal V}_{\bar j},
$$

show that the torus partition function decomposes as

$$
Z(\tau,\bar\tau)=\sum_{i,\bar j}M_{i\bar j}\chi_i(q)\bar\chi_{\bar j}(\bar q).
$$

<details><summary><strong>Solution</strong></summary>

The partition function is the trace over the full Hilbert space:

$$
Z=\operatorname{Tr}_{\mathcal H}q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}.
$$

On each tensor factor $\mathcal V_i\otimes\bar{\mathcal V}_{\bar j}$, the trace factorizes because $L_0$ acts only on the left module and $\bar L_0$ acts only on the right module:

$$
\operatorname{Tr}_{\mathcal V_i\otimes\bar{\mathcal V}_{\bar j}}
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}
=
\chi_i(q)\bar\chi_{\bar j}(\bar q).
$$

Summing with multiplicity $M_{i\bar j}$ gives the result.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984) 333.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997, chapters 5–10 and 17.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- G. Moore and N. Seiberg, “Polynomial equations for rational conformal field theories,” *Physics Letters B* **212** (1988) 451.
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989) 177.
- G. Segal, “The definition of conformal field theory,” in *Topology, Geometry and Quantum Field Theory*, Cambridge University Press, 2004.
- E. Witten, “Three-dimensional gravity revisited,” arXiv:0706.3359.

## Version history

- 2026-06-28: First polished draft. Added left–right decomposition, chiral blocks, Hilbert-space pairings, torus characters, examples, caveats, and exercises.
