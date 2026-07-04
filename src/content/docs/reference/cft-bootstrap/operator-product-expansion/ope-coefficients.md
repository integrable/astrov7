---
title: "OPE Coefficients"
description: "Explains how three-point coefficients become OPE structure constants, how normalization choices enter, and how symmetry and unitarity constrain them."
sidebar:
  label: "OPE Coefficients"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn–Petkou 1994; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - OPE coefficients
  - conformal data
  - three-point functions
  - two-point normalization
  - global symmetries
  - bootstrap positivity
canonicalTopics:
  - ope-coefficients
  - conformal-data
  - three-point-functions
  - operator-product-expansion
  - bootstrap-positivity
researchStatus:
  established:
    - "After two-point normalizations and tensor-structure conventions are fixed, OPE coefficients are the structure constants of the local operator algebra."
    - "In unitary bootstrap problems, products or matrices of OPE coefficients obey positivity constraints in reflection-positive channels."
  active:
    - "Spinning structures, parity-odd coefficients, degenerate operators, mixed-correlator systems, and numerical extraction of OPE data require careful convention management."
---

## Summary

An **OPE coefficient** is the dynamical number multiplying a conformal family in the product of two local operators. For scalar primaries in an orthonormal basis,

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0)+\text{descendants}.
$$

The same number appears in the scalar three-point function,

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{|x_{12}|^{\Delta_i+\Delta_j-\Delta_k}
 |x_{23}|^{\Delta_j+\Delta_k-\Delta_i}
 |x_{13}|^{\Delta_i+\Delta_k-\Delta_j}}.
$$

This equality is one of the main reasons CFT is so rigid. Two-point functions define the metric on operator space. Three-point functions define the multiplication law. Four-point functions test associativity.

The warning is equally important: $\lambda_{ijk}$ is not meaningful until operator normalizations, degeneracy bases, spin tensor structures, and global-symmetry tensors are fixed. The invariant content is the full set of CFT data modulo allowed basis changes.

## Prerequisites

You should know [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), and [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/).

This page uses the scalar conventions fixed in [Conventions and Notation](/cft-bootstrap/conventions/). Spinning operators and current/stress-tensor normalizations are included as orientation, but detailed tensor-structure technology belongs to later pages.

## Core idea

The OPE turns local operators into an algebra. The coefficients of that algebra are measured by three-point functions.

For scalar primaries with orthonormal two-point functions, the dictionary is simple:

$$
\boxed{
\text{three-point coefficient}
=
\text{leading primary OPE coefficient}
}
$$

But this box is only true after a convention choice. In a general basis, the two-point function is

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{g_{ij}}{|x|^{2\Delta_i}}
\qquad
\text{for operators with the same quantum numbers},
$$

and the OPE coefficient with an upper index is

$$
C_{ij}{}^k=\lambda_{ij\ell}g^{\ell k}.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![The OPE coefficient is obtained from a three-point coefficient after raising an operator-space index with the two-point metric.](/figures/cft-bootstrap/ope-coefficient-normalization.svg)

<figcaption>

Two-point functions define the operator-space metric $g_{ij}$. Three-point functions define $\lambda_{ijk}$. The OPE coefficient with one output index is $C_{ij}{}^k=\lambda_{ij\ell}g^{\ell k}$.

</figcaption>
</figure>

This is the same distinction as in any algebra with an inner product: a trilinear form and a multiplication map are related by raising an index.

## Setup and conventions

For scalar primaries, we write the two-point function as

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{g_{ij}}{|x|^{2\Delta_i}}
$$

when $\mathcal O_i$ and $\mathcal O_j$ have the same dimension and the same spin and internal quantum numbers. Otherwise the two-point function vanishes.

In an orthonormal real basis,

$$
g_{ij}=\delta_{ij}.
$$

For charged operators, the natural convention is often

$$
\langle \mathcal O_a(x)\mathcal O_b^\dagger(0)\rangle
=\frac{\delta_{ab}}{|x|^{2\Delta_a}}.
$$

For three scalar primaries, conformal symmetry fixes the position dependence and leaves one coefficient:

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{|x_{12}|^{\Delta_i+\Delta_j-\Delta_k}
 |x_{23}|^{\Delta_j+\Delta_k-\Delta_i}
 |x_{13}|^{\Delta_i+\Delta_k-\Delta_j}}.
$$

The scalar OPE then begins as

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_k
\lambda_{ij\ell}g^{\ell k}|x|^{\Delta_k-\Delta_i-\Delta_j}
\mathcal O_k(0)+\text{descendants}.
$$

If $g_{ij}=\delta_{ij}$, this reduces to the familiar coefficient $\lambda_{ijk}$.

## Extracting the coefficient from a correlator

Suppose the two-point basis is orthonormal. Insert the OPE into a three-point function and take $x_1\to x_2$. The leading term gives

$$
\mathcal O_i(x_1)\mathcal O_j(x_2)
\supset
\lambda_{ijk}|x_{12}|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(x_2).
$$

Multiplying by $\mathcal O_k(x_3)$ and using

$$
\langle \mathcal O_k(x_2)\mathcal O_k(x_3)\rangle
=\frac{1}{|x_{23}|^{2\Delta_k}},
$$

one finds

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
\sim
\lambda_{ijk}
\frac{|x_{12}|^{\Delta_k-\Delta_i-\Delta_j}}
{|x_{23}|^{2\Delta_k}}.
$$

This is exactly the short-distance limit of the conformally fixed three-point function. Thus the OPE coefficient is the leading coefficient in the coincident-point limit.

Equivalently, in a conformal frame one may send one operator to infinity:

$$
\mathcal O_k(\infty)
\equiv
\lim_{|x|\to\infty}|x|^{2\Delta_k}\mathcal O_k(x),
$$

so that

$$
\lambda_{ijk}
=
\langle \mathcal O_k(\infty)\mathcal O_i(1)\mathcal O_j(0)\rangle
$$

for scalar primaries in a one-dimensional conformal frame inside Euclidean space. This compact formula is often the most convenient mental picture: OPE coefficients are three-point amplitudes in radial quantization.

## Normalization dependence

OPE coefficients change when operators are rescaled. If

$$
\mathcal O_i\to a_i\mathcal O_i,
$$

then

$$
g_{ii}\to a_i^2g_{ii},
\qquad
\lambda_{ijk}\to a_i a_j a_k\lambda_{ijk}.
$$

Therefore a raw number such as $\lambda_{ijk}=2$ is not meaningful unless the two-point normalization is also stated. In bootstrap conventions, one usually normalizes two-point functions to unity and then quotes $\lambda$.

A useful normalization-invariant object for three distinct scalar operators is

$$
\frac{\lambda_{ijk}^2}{g_{ii}g_{jj}g_{kk}},
$$

assuming the two-point metric is diagonal. More generally, invariants are built by contracting all indices with the inverse two-point metric.

This is why two-point functions are not a side convention. They are part of the definition of the coordinates on CFT data space.

## A free scalar check

Let $\phi$ be a free scalar primary normalized by

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{2\Delta_\phi}},
\qquad
\Delta_\phi=\frac{d-2}{2}.
$$

The composite operator $\phi^2$ has two-point function

$$
\langle \phi^2(x)\phi^2(0)\rangle
=\frac{2}{|x|^{4\Delta_\phi}}.
$$

Define the unit-normalized scalar

$$
\mathcal O_{\phi^2}=\frac{1}{\sqrt2}\phi^2,
\qquad
\Delta_{\phi^2}=2\Delta_\phi=d-2.
$$

Wick contraction gives

$$
\phi(x)\phi(0)
=
\frac{1}{|x|^{2\Delta_\phi}}\mathbf 1
+\sqrt2\,\mathcal O_{\phi^2}(0)+\cdots.
$$

Therefore

$$
\lambda_{\phi\phi\mathcal O_{\phi^2}}=\sqrt2.
$$

If instead one used the unnormalized operator $\phi^2$, the coefficient would be $1$. The physics did not change. The operator basis changed.

## Selection rules from global symmetry

If the CFT has a global symmetry group $G$, local operators transform in representations of $G$. An OPE coefficient is nonzero only if the tensor product contains an invariant coupling:

$$
R_i\otimes R_j\otimes R_k\supset \mathbf 1.
$$

Equivalently, the output representation $R_k$ must appear in the product $R_i\otimes R_j$, up to conjugation conventions.

For example, if a theory has a $\mathbb Z_2$ symmetry and $\sigma$ is odd while $\epsilon$ is even, then

$$
\sigma\times\sigma
\sim
\mathbf 1+\epsilon+\cdots,
\qquad
\sigma\times\epsilon
\sim
\sigma+\cdots.
$$

The coefficient $\lambda_{\sigma\sigma\sigma}$ vanishes by $\mathbb Z_2$ parity. The statement is not dynamical; it is a selection rule.

For continuous groups, multiple invariant tensors may exist. Then the three-point function has several independent symmetry structures:

$$
\langle \mathcal O_i\mathcal O_j\mathcal O_k\rangle
=
\sum_a \lambda_{ijk}^{(a)}\,\mathcal T_{ijk}^{(a)}.
$$

The label $a$ is part of the OPE-coefficient data. Confusing the numerical coefficient with the invariant tensor is a classic source of normalization errors.

## Spin and tensor structures

For spinning operators, conformal symmetry fixes the position dependence only up to a finite number of tensor structures. A general three-point function takes the form

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\sum_a \lambda_{123}^{(a)}\,\mathcal Q_a(x_i,z_i),
$$

where $z_i$ are polarization variables and $\mathcal Q_a$ are conformally invariant tensor structures.

The OPE data are now the coefficients $\lambda_{123}^{(a)}$ together with the chosen tensor-structure basis. Conservation equations, parity, permutation symmetry, and dimension-specific identities can reduce the number of independent structures.

For example, a correlator involving a conserved current or the stress tensor obeys differential constraints. Those constraints often fix some coefficients in terms of charges, scaling dimensions, $C_J$, or $C_T$. The independent OPE data are whatever remains after imposing the Ward identities.

The practical moral is simple: scalar notation hides multiplicity. Spinning bootstrap problems are not governed by one coefficient per exchanged primary, but by vectors or matrices of coefficients.

## Degeneracies and basis rotations

Suppose several primary operators share the same dimension, spin, and global-symmetry representation. Then they can mix under basis rotations. Let these degenerate operators be $\mathcal O_a$. Their two-point functions define a matrix

$$
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle
=\frac{g_{ab}}{|x|^{2\Delta}}.
$$

A change of basis

$$
\mathcal O_a\to M_a{}^b\mathcal O_b
$$

changes both $g_{ab}$ and all three-point coefficients involving these operators. Individual components of $\lambda_{ij a}$ are basis-dependent.

Bootstrap equations avoid this problem by using basis-invariant combinations. For example, in a mixed-correlator system one often encounters positive semidefinite matrices of the form

$$
P_{mn}^{(\mathcal O)}=\lambda_m^{(\mathcal O)}\lambda_n^{(\mathcal O)},
$$

or sums of such matrices over degenerate operators. The positivity of these matrices is the correct invariant statement in a unitary theory.

This is also why “the OPE coefficient of an operator” can be ambiguous when the spectrum has degeneracies. One must specify the basis or quote invariant combinations.

## Positivity in unitary bootstrap equations

For identical real scalar external operators, the four-point conformal block expansion takes the form

$$
G(u,v)=1+
\sum_{\mathcal O\ne \mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
g_{\Delta,\ell}(u,v).
$$

The coefficients appearing here are squares. In a unitary, reflection-positive theory, they are nonnegative:

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This positivity is the engine behind the simplest numerical bootstrap bounds. Crossing symmetry gives a linear equation in the conformal blocks, while unitarity says the coefficients multiplying allowed blocks are nonnegative.

For multiple external operators, the coefficient is no longer a single square. It is a positive semidefinite matrix built from products of OPE coefficients. The scalar slogan “coefficients are positive” becomes

$$
P^{(\mathcal O)}\succeq 0.
$$

For spinning operators, parity-odd structures, complex operators, and non-reflection-symmetric configurations, additional reality and sign conventions enter. The safe rule is to derive positivity from the radial-quantization inner product, not from visual similarity to the identical-scalar formula.

## Ward-fixed OPE coefficients

Some OPE coefficients are not independent. They are fixed by Ward identities once normalizations are chosen.

If $J_\mu^A$ is a conserved current for a global symmetry, its OPE with a charged operator includes the action of the symmetry generator:

$$
J_\mu^A(x)\mathcal O_i(0)
\sim
\frac{x_\mu}{|x|^d}\,(T^A)_i{}^j\mathcal O_j(0)+\cdots,
$$

up to a convention-dependent normalization involving the area of the unit sphere and the normalization of $J_\mu^A$. The key point is invariant: the leading singularity is fixed by the charge.

Similarly, the stress tensor OPE with a primary knows the scaling dimension and spin of that primary. The coefficient of $\langle \mathcal O\mathcal O T\rangle$ is fixed relative to the normalization of $T_{\mu\nu}$ by the conformal Ward identity. Once the stress-tensor two-point coefficient $C_T$ is chosen, the corresponding normalized OPE coefficient is not arbitrary.

This is why $C_J$ and $C_T$ often appear in bootstrap bounds. Bounding a current or stress-tensor OPE coefficient is equivalent, after Ward identities, to bounding the current or stress-tensor two-point normalization.

## OPE coefficients versus fusion rules

The phrase “fusion” is used in several related ways.

In a general CFT, the OPE coefficient is a number or tensor coefficient. It can vanish accidentally or by symmetry.

In rational two-dimensional CFT, a fusion rule is often written

$$
\mathcal V_i\times \mathcal V_j
=
\sum_k N_{ij}{}^k\mathcal V_k,
$$

where $N_{ij}{}^k$ is a nonnegative integer counting allowed chiral conformal blocks or representation-theoretic channels. This is not the same object as the numerical OPE coefficient.

The relation is:

| Object | Meaning |
|---|---|
| $N_{ij}{}^k$ | Whether a representation channel is allowed, and with what multiplicity. |
| $\lambda_{ijk}$ | The dynamical coefficient of a chosen physical three-point structure. |
| $C_{ij}{}^k$ | The OPE multiplication coefficient after raising an index with the two-point metric. |

In minimal models, fusion rules can force many OPE coefficients to vanish. But knowing the allowed channels is not the same as knowing the numerical structure constants.

## Common pitfalls

Do not quote an OPE coefficient without its two-point normalization. Rescaling an operator changes the coefficient.

Do not confuse $\lambda_{ijk}$ with the full position-dependent Wilson coefficient $C_{ij}{}^k(x,\partial)$. The number $\lambda_{ijk}$ is the dynamical primary coefficient; the differential operator includes kinematics and descendants.

Do not forget to raise an index when the two-point metric is not the identity. The three-point coefficient $\lambda_{ijk}$ is a trilinear form. The OPE multiplication coefficient is $C_{ij}{}^k=\lambda_{ij\ell}g^{\ell k}$.

Do not assume every OPE coefficient is positive. In the simplest identical-scalar bootstrap, squared coefficients are nonnegative. In general, coefficients can have signs, phases, tensor-structure labels, or matrix-valued positivity conditions.

Do not confuse selection rules with dynamics. A coefficient can vanish because symmetry forbids it, because a fusion rule excludes the channel, because of conservation, or because of an accidental dynamical zero. These are different explanations.

## Relations to other pages

[Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/) derives the conformal form of scalar three-point functions. This page interprets the remaining constants as OPE coefficients.

[OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) explains the local replacement formula and descendant structure. This page focuses on the dynamical coefficients multiplying the conformal families.

[Identity Operator in the OPE](/cft-bootstrap/operator-product-expansion/identity-operator-in-the-ope/) explains the special coefficient fixed by two-point normalization.

[Stress-Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) and [Current OPE](/cft-bootstrap/operator-product-expansion/current-ope/) explain how Ward identities fix universal singular terms.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) uses OPE coefficients to weight exchanged conformal families in four-point functions. [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) turns those weighted sums into constraints.

## Research status

For scalar primaries, the relation between three-point functions and OPE coefficients is standard. For spinning operators, the same principle holds, but the number of independent tensor structures and their normalization conventions become important. Modern conformal-bootstrap calculations often spend a large fraction of their setup effort getting these tensor structures, reality conditions, and positivity matrices right.

Active work includes precision extraction of OPE coefficients in strongly coupled CFTs, mixed-correlator systems with many external operators, spinning and parity-odd bootstrap problems, defects and boundaries, supersymmetric protected coefficients, and asymptotic formulas for OPE data at large dimension, large spin, or high energy.

## Exercises

### Exercise 1: Rescaling a primary

Let scalar primaries have unit two-point normalization and OPE coefficient $\lambda_{123}$. Now redefine $\mathcal O_1'=a\mathcal O_1$ while leaving the other two operators unchanged. What happens to the three-point coefficient and the two-point normalization of $\mathcal O_1'$?

<details><summary><strong>Solution</strong></summary>

The two-point function becomes

$$
\langle \mathcal O_1'(x)\mathcal O_1'(0)\rangle
=
\frac{a^2}{|x|^{2\Delta_1}}.
$$

The three-point coefficient becomes

$$
\lambda'_{123}=a\lambda_{123}.
$$

Thus the raw number changed. If one then renormalizes $\mathcal O_1'$ back to unit two-point normalization, the coefficient returns to the original value up to the sign or phase of $a$ allowed by the reality convention.

</details>

### Exercise 2: Raising the output index

Suppose two scalar primaries $\mathcal O_a$ with the same quantum numbers have two-point metric $g_{ab}$. The three-point coefficient with two external operators is $\lambda_{ij a}$. What is the coefficient multiplying $\mathcal O_b$ in the OPE of $\mathcal O_i\times\mathcal O_j$?

<details><summary><strong>Solution</strong></summary>

The OPE coefficient with an upper output index is obtained by raising the index using the inverse two-point metric:

$$
C_{ij}{}^b=\lambda_{ij a}g^{ab}.
$$

The leading primary contribution is therefore

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\sum_b C_{ij}{}^b |x|^{\Delta_b-\Delta_i-\Delta_j}\mathcal O_b(0).
$$

If $g_{ab}=\delta_{ab}$, this reduces to $C_{ij}{}^b=\lambda_{ijb}$.

</details>

### Exercise 3: Free scalar coefficient

For a free scalar with $\langle\phi(x)\phi(0)\rangle=|x|^{-2\Delta_\phi}$, define $\mathcal O_{\phi^2}=\phi^2/\sqrt2$. Show that $\lambda_{\phi\phi\mathcal O_{\phi^2}}=\sqrt2$.

<details><summary><strong>Solution</strong></summary>

Wick contraction gives

$$
\phi(x)\phi(0)=\frac{1}{|x|^{2\Delta_\phi}}\mathbf 1+\phi^2(0)+\cdots.
$$

Since $\mathcal O_{\phi^2}=\phi^2/\sqrt2$, we have $\phi^2=\sqrt2\mathcal O_{\phi^2}$. Therefore

$$
\phi(x)\phi(0)
\supset
\sqrt2\mathcal O_{\phi^2}(0).
$$

Because $\Delta_{\phi^2}=2\Delta_\phi$, there is no extra power of $|x|$ multiplying this primary term. Hence

$$
\lambda_{\phi\phi\mathcal O_{\phi^2}}=\sqrt2.
$$

</details>

### Exercise 4: Symmetry selection

A CFT has a $\mathbb Z_2$ symmetry. Operators $\sigma$ and $\chi$ are odd; $\epsilon$ is even. Which of $\lambda_{\sigma\sigma\epsilon}$, $\lambda_{\sigma\epsilon\chi}$, and $\lambda_{\sigma\epsilon\epsilon}$ are allowed by the symmetry?

<details><summary><strong>Solution</strong></summary>

A three-point coefficient is allowed only if the product of parities is even. Therefore

$$
\sigma\sigma\epsilon:
(-)(-)(+)=+,
$$

so $\lambda_{\sigma\sigma\epsilon}$ is allowed. Also

$$
\sigma\epsilon\chi:
(-)(+)(-)=+,
$$

so $\lambda_{\sigma\epsilon\chi}$ is allowed. But

$$
\sigma\epsilon\epsilon:
(-)(+)(+)=-,
$$

so $\lambda_{\sigma\epsilon\epsilon}$ is forbidden.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory* (Springer, 1997). Standard reference for OPE coefficients, conformal families, fusion rules, and two-dimensional structure constants.
- H. Osborn and A. C. Petkou, “Implications of Conformal Invariance in Field Theories for General Dimensions,” *Annals of Physics* **231** (1994). Classic treatment of conformal constraints on currents, stress tensors, and correlation functions in general dimension.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Modern introduction to CFT data, OPE coefficients, unitarity, and bootstrap equations.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Pedagogical account of reflection positivity, OPE coefficients, conformal blocks, and semidefinite bootstrap logic.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Broad review emphasizing OPE coefficients as CFT data and as variables in crossing equations.

## Version history

- 2026-06-27: Added a polished first version covering normalization dependence, index raising, symmetry selection rules, spinning structures, degeneracies, positivity, Ward-fixed coefficients, and fusion-rule caveats.
