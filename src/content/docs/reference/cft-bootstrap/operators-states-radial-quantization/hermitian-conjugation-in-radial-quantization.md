---
title: "Hermitian Conjugation in Radial Quantization"
description: "Defines radial adjoints, inversion conjugation, inner products, and generator adjoints in CFT radial quantization."
sidebar:
  label: "Hermitian Conjugation"
  order: 7
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - radial quantization
  - Hermitian conjugation
  - inversion positivity
  - reflection positivity
  - state-operator correspondence
  - conformal generators
canonicalTopics:
  - radial-adjoint
  - inversion-conjugation
  - reflection-positivity
  - generator-adjoints
  - radial-quantization-inner-product
researchStatus:
  established:
    - 'In radial quantization, Hermitian conjugation is implemented by inversion, so $P_\mu^\dagger=K_\mu$, $D^\dagger=D$, and descendant norms are computed from the conformal algebra.'
    - 'For unitary Euclidean CFTs, inversion positivity in radial quantization is equivalent to ordinary reflection positivity after a conformal transformation.'
  active:
    - "The basic construction is standard; active refinements concern defects, boundaries, Lorentzian reconstruction, continuous spectra, nonunitary theories, and algebraic formulations of reflection positivity."
---

## Summary

Hermitian conjugation in radial quantization is not obtained by simply taking the complex conjugate of a local operator at the same Euclidean point. Radial time is

$$
\tau=\log r,
\qquad
x=r n,
\qquad
n\in S^{d-1},
$$

so reversing Euclidean time sends $\tau\mapsto-\tau$ and therefore $r\mapsto r^{-1}$. On flat space this is the inversion map

$$
R x = \frac{x}{x^2}.
$$

For a scalar primary of dimension $\Delta$, the radial adjoint is

$$
\mathcal O(x)^{\dagger_{\rm rad}}
=|x|^{-2\Delta}\,\mathcal O^\dagger\!\left(\frac{x}{x^2}\right)
$$

with the obvious replacement by the conjugate operator if $\mathcal O$ is complex. For spinning operators, one must also rotate the indices by the inversion tensor.

<figure class="doc-figure" style="--figure-width: 34rem;">

![Radial Hermitian conjugation maps an insertion inside the unit sphere to the conjugate insertion at the inverted point outside the sphere.](/figures/cft-bootstrap/radial-adjoint-inversion.svg)

<figcaption>

Radial Hermitian conjugation reverses cylinder time. On flat space this sends an insertion at $x$ to the conjugate insertion at $x'=x/x^2$. The unit sphere is the equal-time slice used for the inner product.

</figcaption>
</figure>

This page fixes the adjoint operation used in the operator–state correspondence. Its most important algebraic consequence is

$$
D^\dagger=D,
\qquad
M_{\mu\nu}^\dagger=M_{\mu\nu},
\qquad
P_\mu^\dagger=K_\mu.
$$

The last formula is the engine behind unitarity bounds: descendant norms become computable algebraic quantities.

## Prerequisites

You should know [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), the [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), and the [Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/). The pages [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/) and [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/) fix the generator conventions used below.

This page is written in Euclidean signature. Lorentzian unitarity is recovered by analytic continuation when the Euclidean theory satisfies the appropriate reflection-positivity conditions.

## Core idea

Radial quantization chooses spheres centered at the origin as equal-time surfaces. A ket is prepared by operator insertions inside a sphere; the dual bra is prepared by the complementary path integral outside the sphere.

The subtlety is that the outside of a sphere is naturally compared to the inside by inversion. In coordinates

$$
x=r n,
\qquad
r=e^\tau,
$$

radial time reversal is

$$
\tau\mapsto -\tau,
\qquad
r\mapsto r^{-1},
\qquad
n\mapsto n.
$$

Thus

$$
x=r n
\quad\longmapsto\quad
x'=r^{-1}n=\frac{x}{x^2}.
$$

Hermitian conjugation in radial quantization is therefore anti-linear complex conjugation plus this geometric inversion, including the conformal transformation factor appropriate to the operator.

This is the same idea as ordinary Euclidean reflection positivity, but adapted to spherical time slices rather than planar time slices. Planar quantization reflects across a plane. Radial quantization reflects through a sphere.

## Setup and conventions

Let $R$ denote inversion:

$$
R x=\frac{x}{x^2},
\qquad
R^2=1.
$$

The Jacobian of inversion is

$$
\frac{\partial (R x)^\mu}{\partial x^\nu}
=\frac{1}{x^2}I^\mu{}_{\nu}(x),
$$

where

$$
I_{\mu\nu}(x)
=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The tensor $I_{\mu\nu}(x)$ is an orthogonal reflection matrix:

$$
I_{\mu\rho}(x)I_{\rho\nu}(x)=\delta_{\mu\nu}.
$$

For scalar operators we only need the Weyl factor. For tensor operators we also need one factor of $I_\mu{}^\nu(x)$ for each vector index. For spinors, one uses the corresponding lift of inversion to the spin representation; that extra spinor structure is important in spinning bootstrap work but is not needed for the scalar and symmetric-traceless examples in this chapter.

We use the radial-quantization generator convention

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}.
$$

With this convention, $P_\mu$ raises dimension, $K_\mu$ lowers dimension, and a primary state satisfies $K_\mu|\mathcal O\rangle=0$.

## Radial adjoint of primary operators

For a scalar primary of dimension $\Delta$, the adjoint is

$$
\mathcal O(x)^{\dagger_{\rm rad}}
=|x|^{-2\Delta}\,\mathcal O^\dagger(Rx).
$$

This formula is not arbitrary. It is exactly the conformal transformation law for a primary under inversion, combined with ordinary Hermitian conjugation of the operator label.

For a symmetric-traceless spin-$\ell$ primary, written with explicit indices, the radial adjoint is

$$
\mathcal O_{\mu_1\cdots\mu_\ell}(x)^{\dagger_{\rm rad}}
=|x|^{-2\Delta}
I_{\mu_1}{}^{\nu_1}(x)\cdots I_{\mu_\ell}{}^{\nu_\ell}(x)
\mathcal O^\dagger_{\nu_1\cdots\nu_\ell}(Rx).
$$

The inversion tensors are not decorative. They are required because inversion reverses the radial direction. Forgetting them gives wrong signs and wrong positivity conditions for spinning correlators.

For an operator inserted at the origin, the conjugate insertion sits at infinity. A scalar state is

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle,
$$

and the corresponding bra is

$$
\langle \mathcal O|
=\lim_{x\to\infty}|x|^{2\Delta}\langle0|\mathcal O^\dagger(x).
$$

The factor $|x|^{2\Delta}$ is what makes the limit finite. This is the higher-dimensional version of the familiar two-dimensional rule that a primary inserted at infinity is defined with a compensating power of its coordinate.

## Inner products from two-point functions

The inner product of states is a correlation function on the sphere. For scalar primaries,

$$
\langle \mathcal O_i|\mathcal O_j\rangle
=\lim_{x\to\infty}|x|^{2\Delta_i}
\langle0|\mathcal O_i^\dagger(x)\mathcal O_j(0)|0\rangle.
$$

If the scalar two-point function is normalized as

$$
\langle \mathcal O_i^\dagger(x)\mathcal O_j(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_i}},
$$

then

$$
\langle \mathcal O_i|\mathcal O_j\rangle=\delta_{ij}.
$$

This is the cleanest way to understand two-point normalization in a unitary CFT. It is a choice of orthonormal basis for primary states.

For descendants, the same inner product is computed by moving the adjoint generators across the bracket. Since $P_\mu^\dagger=K_\mu$,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

The right-hand side is now determined by the conformal algebra. This is why the representation theory of $SO(d+1,1)$ in Euclidean kinematics becomes Hilbert-space positivity after radial quantization.

## Generator adjoints

On the cylinder, the Hamiltonian is the dilatation generator:

$$
H_{\rm cyl}=D.
$$

A sensible Hilbert-space inner product therefore requires

$$
D^\dagger=D.
$$

Rotations act within the spatial sphere $S^{d-1}$, so their generators are also Hermitian in the radial Hilbert-space convention:

$$
M_{\mu\nu}^\dagger=M_{\mu\nu}.
$$

Translations and special conformal transformations are exchanged by inversion. Algebraically this gives

$$
P_\mu^\dagger=K_\mu,
\qquad
K_\mu^\dagger=P_\mu.
$$

This is the most important adjoint relation in the chapter. It says that $P_\mu$ is a raising operator and $K_\mu$ is its lowering adjoint. A primary is a lowest-weight state:

$$
K_\mu|\mathcal O\rangle=0.
$$

Descendants are obtained by acting with $P_\mu$, and their norms are constrained because adjoints bring down $K_\mu$.

For example, for a scalar primary normalized by $\langle\mathcal O|\mathcal O\rangle=1$,

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=\sum_\mu\langle\mathcal O|K_\mu P_\mu|\mathcal O\rangle
=2d\Delta.
$$

A unitary theory requires this to be nonnegative. Stronger constraints come from higher-level descendants and spinning representations; those are the subject of [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/).

## Inversion positivity

A general ket in radial quantization is prepared by insertions inside the unit sphere:

$$
|\Psi\rangle
=\sum_a c_a\,\mathcal O_a(x_a)|0\rangle,
\qquad
|x_a|<1.
$$

The bra is prepared by the radially conjugate insertions outside the unit sphere:

$$
\langle\Psi|
=\sum_a c_a^*\langle0|\mathcal O_a(x_a)^{\dagger_{\rm rad}}.
$$

Unitarity requires

$$
\langle\Psi|\Psi\rangle\ge0
$$

for all choices of coefficients $c_a$ and all allowed insertion points. Written as a correlation function, this is a positivity condition on configurations related by inversion. It is often called **inversion positivity**.

For scalar operators, this means the matrix

$$
G_{ab}
=|x_a|^{-2\Delta_a}
\left\langle
\mathcal O_a^\dagger\!\left(\frac{x_a}{x_a^2}\right)
\mathcal O_b(x_b)
\right\rangle
$$

must be positive semidefinite, with the appropriate extension to spinning operators using inversion tensors.

This positivity condition is one reason radial quantization is so natural for the bootstrap. The OPE becomes a Hilbert-space expansion, and unitarity becomes positivity of norms and OPE coefficients.

## Two-dimensional mode adjoints

In two dimensions, use complex coordinates and write a primary field as

$$
\phi(z,\bar z)
=\sum_{m,n}z^{-m-h}\bar z^{-n-\bar h}\phi_{m,n}.
$$

Radial conjugation sends

$$
z\mapsto \frac{1}{\bar z},
\qquad
\bar z\mapsto \frac{1}{z}.
$$

For a real primary, the mode adjoint is

$$
\phi_{m,n}^\dagger=\phi_{-m,-n}.
$$

For a complex primary, the right-hand side is the corresponding mode of the conjugate primary.

For the stress tensor modes, this gives the standard radial adjoint

$$
L_n^\dagger=L_{-n},
\qquad
\bar L_n^\dagger=\bar L_{-n}.
$$

Thus $L_{-1}$ is the adjoint of $L_1$, just as $P_\mu$ is the adjoint of $K_\mu$ in higher-dimensional notation. This is why two-dimensional unitarity starts with conditions such as

$$
\langle h|L_1L_{-1}|h\rangle=2h\langle h|h\rangle\ge0.
$$

The full Virasoro story is richer because the stress-tensor modes generate infinitely many descendants and include the central charge. That belongs to [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/).

## How this is used

Radial adjoints appear in four recurring ways.

First, they define the Hilbert-space metric on local operators. Two-point functions are Gram matrices of states.

Second, they determine descendant norms. The adjoint relation $P_\mu^\dagger=K_\mu$ turns descendant norms into algebraic expressions involving $\Delta$, spin, and the conformal commutators.

Third, they explain why conserved currents shorten multiplets. At a unitarity bound, a descendant has zero norm. In a unitary theory, a zero-norm state is removed from the Hilbert space, giving an operator equation such as

$$
\partial^\mu J_\mu=0
$$

or

$$
\partial^\mu T_{\mu\nu}=0.
$$

Fourth, they justify positivity in bootstrap equations. In a unitary CFT, OPE coefficients of real scalar operators can be chosen real, and squared OPE coefficients appearing in identical-scalar four-point functions are nonnegative.

## Common pitfalls

**Using ordinary Euclidean conjugation instead of radial conjugation.** In radial quantization, the adjoint of an insertion at $x$ is not at the same point. It is at the inverted point $x/x^2$.

**Forgetting the conformal factor.** The factor $|x|^{-2\Delta}$ is needed for primary operators. Without it, the operator at infinity does not define a finite bra state.

**Forgetting inversion tensors for spin.** A vector, current, stress tensor, or spinning primary requires index rotation by $I_{\mu\nu}(x)$. This is essential for correct signs.

**Assuming $P_\mu^\dagger=P_\mu$.** That is not the radial Hilbert-space adjoint. The correct relation is $P_\mu^\dagger=K_\mu$.

**Confusing reflection positivity with positivity of every Euclidean correlator.** Reflection positivity is a structured positivity condition: operators must be paired with reflected or inverted conjugates. A generic Euclidean correlator need not be positive as a number.

**Ignoring null states.** If a descendant has zero norm in a unitary theory, it must be quotiented out. Keeping it as an ordinary state double-counts the conformal multiplet.

## Relations to other pages

[State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/) explains why local operators create states on spheres. This page explains how to form the dual bra and inner product.

[Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/) explains why radial time reversal is inversion on flat space.

[Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) uses $P_\mu^\dagger=K_\mu$ to derive lower bounds on operator dimensions.

[Correlation Functions](/cft-bootstrap/correlation-functions/) uses the same adjoint structure to normalize two-point functions and control positivity.

[Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) uses positivity of OPE data as one of the main inputs of numerical bootstrap constraints.

## Research status

For ordinary unitary local CFTs, radial adjoints, inversion positivity, and the generator adjoints above are standard. They are part of the basic operator formalism of CFT.

The subtle cases are not failures of the construction but extensions of it. Nonunitary CFTs can have useful Euclidean correlation functions without a positive radial Hilbert space. Logarithmic CFTs can have indecomposable operator spaces and non-diagonal dilatation action. Defect and boundary CFTs modify the equal-time surfaces and the state–operator map. Lorentzian CFT uses related but sharper positivity and analyticity structures.

For the bootstrap pages in this volume, the default assumption is an ordinary unitary CFT unless a page explicitly says otherwise.

## Exercises

### Exercise 1: The scalar bra at infinity

Let $\mathcal O$ be a scalar primary with

$$
\langle \mathcal O^\dagger(x)\mathcal O(0)\rangle=\frac{1}{|x|^{2\Delta}}.
$$

Show that

$$
\langle \mathcal O|
=\lim_{x\to\infty}|x|^{2\Delta}\langle0|\mathcal O^\dagger(x)
$$

gives $\langle\mathcal O|\mathcal O\rangle=1$.

<details><summary><strong>Solution</strong></summary>

Insert the definition:

$$
\langle\mathcal O|\mathcal O\rangle
=\lim_{x\to\infty}|x|^{2\Delta}
\langle\mathcal O^\dagger(x)\mathcal O(0)\rangle.
$$

Using the normalized two-point function gives

$$
\langle\mathcal O|\mathcal O\rangle
=\lim_{x\to\infty}|x|^{2\Delta}\frac{1}{|x|^{2\Delta}}
=1.
$$

The compensating factor is exactly what makes the insertion at infinity finite.

</details>

### Exercise 2: The first descendant norm of a scalar

Let $|\mathcal O\rangle$ be a scalar primary with $D|\mathcal O\rangle=\Delta|\mathcal O\rangle$, $K_\mu|\mathcal O\rangle=0$, and $\langle\mathcal O|\mathcal O\rangle=1$. Use

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}
$$

to compute $\sum_\mu\|P_\mu|\mathcal O\rangle\|^2$.

<details><summary><strong>Solution</strong></summary>

Since $P_\mu^\dagger=K_\mu$,

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=\sum_\mu\langle\mathcal O|K_\mu P_\mu|\mathcal O\rangle.
$$

Because $K_\mu|\mathcal O\rangle=0$, we may replace $K_\mu P_\mu$ by the commutator:

$$
\sum_\mu\langle\mathcal O|[K_\mu,P_\mu]|\mathcal O\rangle.
$$

For a scalar primary, $M_{\mu\nu}|\mathcal O\rangle=0$, so

$$
[K_\mu,P_\mu]=2D
$$

for each fixed $\mu$. Summing over $\mu=1,\ldots,d$ gives

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=2d\Delta.
$$

Positivity therefore requires $\Delta\ge0$. The sharper scalar bound comes from a level-two descendant.

</details>

### Exercise 3: Two-dimensional mode adjoints

Let a holomorphic primary have the mode expansion

$$
\phi(z)=\sum_n z^{-n-h}\phi_n.
$$

Assuming radial conjugation gives $\phi(z)^\dagger=z^{-2h}\phi(1/z)$ on the unit radial slice, show that $\phi_n^\dagger=\phi_{-n}$ for a real primary.

<details><summary><strong>Solution</strong></summary>

Taking the adjoint of the mode expansion gives

$$
\phi(z)^\dagger
=\sum_n z^{-n-h}\phi_n^\dagger.
$$

The radial-conjugation formula gives

$$
\phi(z)^\dagger
=z^{-2h}\sum_n (1/z)^{-n-h}\phi_n
=\sum_n z^{n-h}\phi_n.
$$

Relabel $m=-n$:

$$
\sum_n z^{n-h}\phi_n
=\sum_m z^{-m-h}\phi_{-m}.
$$

Comparing coefficients of $z^{-m-h}$ gives

$$
\phi_m^\dagger=\phi_{-m}.
$$

</details>

## References

- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, chapter 6.
- Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*.
- Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap.”
- Poland, Rychkov, and Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications.”
- Osterwalder and Schrader, “Axioms for Euclidean Green's Functions.”

## Version history

- 2026-06-27: First polished draft.
