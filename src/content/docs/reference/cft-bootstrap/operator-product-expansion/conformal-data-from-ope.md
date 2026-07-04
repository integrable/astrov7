---
title: "Conformal Data from the OPE"
description: "Explains how the operator product expansion packages the spectrum, two-point metric, OPE coefficients, Ward-fixed data, and crossing constraints that define a conformal field theory."
sidebar:
  label: "Conformal Data from OPE"
  order: 9
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Rychkov 2016; Simmons-Duffin 2017; Poland et al. 2019"
topics:
  - conformal field theory
  - conformal data
  - operator product expansion
  - conformal bootstrap
  - OPE coefficients
  - crossing symmetry
canonicalTopics:
  - conformal-data
  - ope-algebra
  - cft-data
  - bootstrap-input-data
researchStatus:
  established:
    - "In a local CFT, the spectrum of primary operators together with two-point normalizations and OPE coefficients determine correlation functions through the OPE, subject to crossing, unitarity, and symmetry constraints."
    - "For ordinary CFT bootstrap problems, conformal data are the natural non-Lagrangian coordinates on the space of theories."
  active:
    - "How best to reconstruct, approximate, organize, and classify full CFT data remains active, especially for strongly coupled, non-Lagrangian, higher-spin, supersymmetric, defect, and numerical-bootstrap applications."
---

## Summary

The OPE turns the vague phrase "solve a CFT" into a concrete data problem. Choose a basis of primary operators $\mathcal O_A$ and write

$$
\mathcal O_A(x)\mathcal O_B(0)
=
\sum_C \lambda_{AB}{}^C\,\mathcal D_{AB}{}^C(x,\partial)\mathcal O_C(0),
$$

where $\mathcal D_{AB}{}^C$ is fixed by conformal symmetry once the dimensions and spins are known. The dynamical input is the spectrum of primaries and the OPE coefficients. Descendants are not new data; their coefficients are dictated by the conformal algebra.

In an orthonormal primary basis, the basic conformal data are

$$
\boxed{
\text{CFT data}
=
\left\{
(\Delta_A,\rho_A),\;\lambda_{ABC}
\right\}
\quad \text{plus global-symmetry and parity labels when present.}
}
$$

Here $\Delta_A$ is the scaling dimension, $\rho_A$ is the Lorentz and internal-symmetry representation, and $\lambda_{ABC}$ are three-point/OPE coefficients. With a non-orthonormal two-point metric $G_{AB}$, the equivalent data are

$$
G_{AB},
\qquad
\lambda_{AB}{}^C,
\qquad
\lambda_{ABC}=\lambda_{AB}{}^D G_{DC}.
$$

The bootstrap then says: not every formal list of $\Delta$'s and $\lambda$'s is allowed. The OPE must be associative, reflection positive in unitary Euclidean theories, compatible with Ward identities, and crossing-symmetric in all correlators.

<figure class="doc-figure" style="--figure-width: 44rem;">

![How the OPE packages conformal data](/figures/cft-bootstrap/conformal-data-from-ope.svg)

<figcaption>

The OPE packages a CFT into spectral data and OPE coefficients. Conformal symmetry supplies the descendant differential operators; crossing and positivity decide whether the proposed data define a consistent theory.

</figcaption>
</figure>

## Prerequisites

You should know [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/), [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), and [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/).

This page is a synthesis page. It explains how the pieces of the previous OPE pages combine into the data language used by conformal blocks and the bootstrap.

## Core idea

A Lagrangian, when one exists, is one way of specifying a quantum field theory. A CFT can often be specified more intrinsically by its local operator algebra. The OPE is the multiplication rule of that algebra.

The slogan is

$$
\text{local CFT}
\quad\Longleftrightarrow\quad
\text{consistent OPE algebra of local operators}.
$$

This slogan is not a theorem in this naive form; reconstructing a full QFT from abstract data requires analytic and Hilbert-space assumptions. But it is the correct working principle of the conformal bootstrap. Instead of starting with microscopic fields and an action, we try to solve directly for the data that appear in correlation functions.

The OPE separates two kinds of information.

| Ingredient | Status |
|---|---|
| Descendant coefficients | Fixed by conformal symmetry. |
| Tensor structures | Fixed up to a finite number by conformal symmetry, spin, parity, and global symmetry. |
| Primary spectrum | Dynamical CFT data. |
| Primary OPE coefficients | Dynamical CFT data, except for Ward-fixed pieces. |
| Crossing and positivity | Consistency constraints on the data. |

This is why the OPE is the bridge between representation theory and dynamics.

## Setup and conventions

Let $\mathcal O_A$ denote primary operators. The index $A$ is a compact label containing all discrete and continuous information needed to identify a primary:

$$
A=(\Delta_A,\rho_A,\alpha_A),
$$

where $\rho_A$ includes Lorentz spin and internal-symmetry representation, while $\alpha_A$ labels degeneracies among primaries with the same quantum numbers.

The two-point function defines an operator-space metric. For scalar primaries of equal dimension in a basis that may not be orthonormal,

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\rangle
={G_{AB}\over |x|^{2\Delta_A}},
$$

with the understanding that the correlator vanishes unless the quantum numbers of $A$ and $B$ are compatible. In an orthonormal basis one sets $G_{AB}=\delta_{AB}$ within each compatible block.

The three-point function defines coefficients $\lambda_{ABC}$ after stripping off the conformally fixed spacetime dependence. For scalar primaries,

$$
\langle \mathcal O_A(x_1)\mathcal O_B(x_2)\mathcal O_C(x_3)\rangle
=
{\lambda_{ABC}\over
|x_{12}|^{\Delta_A+\Delta_B-\Delta_C}
|x_{13}|^{\Delta_A+\Delta_C-\Delta_B}
|x_{23}|^{\Delta_B+\Delta_C-\Delta_A}}.
$$

The OPE coefficient with one index raised is

$$
\lambda_{AB}{}^C=\lambda_{ABD}G^{DC}.
$$

In spinning or global-symmetry-covariant cases, the same idea holds, but $\lambda_{ABC}$ is a vector in the finite-dimensional space of allowed tensor structures.

## What the OPE contributes beyond three-point functions

It is tempting to say "conformal data are dimensions and three-point coefficients" and stop there. That is almost right, but the OPE adds essential structure.

First, it tells us how three-point coefficients appear in products of local operators:

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\sum_C \lambda_{AB}{}^C\,\mathcal D_{AB}{}^C(x,\partial)\mathcal O_C(0).
$$

Second, it fixes the descendants. Once $\mathcal O_C$ appears, all of its descendants appear with coefficients determined by conformal symmetry. The tower of descendants is not optional.

Third, it provides a convergent expansion in Euclidean radial quantization under the usual assumptions. That makes it a calculation method, not just a symbolic multiplication table.

Fourth, it allows one to build higher-point functions recursively. A four-point function can be computed by applying the OPE to pairs of operators, leading to conformal block decompositions.

Fifth, it turns consistency into associativity. The same four-point function can be expanded in different channels. Equating them gives crossing symmetry.

## The identity and the two-point metric

The identity operator is the first piece of conformal data hidden in the OPE. For scalar primaries,

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
{G_{AB}\over |x|^{2\Delta_A}}\mathbf 1+\cdots,
$$

when $A$ and $B$ have compatible quantum numbers. Thus the identity coefficient is the two-point metric. In an orthonormal basis, this becomes

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
{\delta_{AB}\over |x|^{2\Delta_A}}\mathbf 1+\cdots.
$$

This is not just normalization bookkeeping. The inverse metric $G^{AB}$ raises OPE indices, and a nontrivial metric matters whenever there are degeneracies, conjugate representations, nontrivial reality conditions, or non-unit-normalized operators.

In reflection-positive theories, $G$ is positive definite after choosing a compatible Hermitian conjugation. That positivity is one of the roots of bootstrap positivity.

## Primary coefficients and three-point functions

For scalar primaries, compare the OPE

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\lambda_{AB}{}^C C_{AB}{}^C(x)\mathcal O_C(0)+\cdots
$$

with the three-point function

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\mathcal O_D(y)\rangle.
$$

Using the two-point function of $\mathcal O_C$ with $\mathcal O_D$ relates the OPE coefficient to $\lambda_{ABD}$:

$$
\lambda_{ABD}=\lambda_{AB}{}^C G_{CD}.
$$

Thus, once the two-point metric is fixed, OPE coefficients and three-point coefficients are the same data in different index positions.

For spinning operators, a three-point function may have several independent tensor structures:

$$
\langle \mathcal O_A\mathcal O_B\mathcal O_C\rangle
=
\sum_{n} \lambda_{ABC}^{(n)}\,\mathcal T_{ABC}^{(n)}.
$$

The label $n$ is part of the OPE data. Conservation laws, parity, permutation symmetry, and dimension-specific identities can reduce the allowed list.

## Descendants are fixed

Suppose a scalar primary $\mathcal O_C$ appears in the OPE of two scalar primaries. Then its descendants appear as

$$
\mathcal O_A(x)\mathcal O_B(0)
\supset
\lambda_{AB}{}^C |x|^{\Delta_C-\Delta_A-\Delta_B}
\left(
\mathcal O_C(0)
+a_1 x^\mu \partial_\mu \mathcal O_C(0)
+a_2 x^\mu x^\nu \partial_\mu\partial_\nu \mathcal O_C(0)
+\cdots
\right),
$$

where the coefficients $a_n$ are fixed by conformal symmetry. Their explicit form depends on normalization conventions, but their existence is universal.

This is why conformal blocks are useful. A conformal block is the total contribution of one primary plus all of its descendants to a four-point function. Once the primary dimension, spin, and OPE coefficient are known, the descendant sum is fixed.

So the bootstrap does not sum over every descendant independently. It sums over primary families.

## Ward-fixed data

Some OPE coefficients are not independent. If a conserved current or stress tensor appears, Ward identities can fix its coupling to external operators.

For an ordinary global current,

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
{1\over S_d}{x_\mu\over |x|^d}(T^a)_i{}^j\mathcal O_j(0)+\cdots.
$$

For the stress tensor, the leading singular terms in $T_{\mu\nu}(x)\mathcal O(0)$ encode translations, rotations, and dilatations of $\mathcal O$. Their coefficients are fixed once the physical stress tensor normalization is chosen.

This means that the data set is not simply "all coefficients are free variables." It is a constrained collection:

$$
\text{free dynamical data}
+
\text{Ward-fixed data}
+
\text{normalization choices}
+
\text{consistency equations}.
$$

Good bootstrap bookkeeping keeps these categories separate.

## From OPE data to four-point functions

For identical scalar primaries $\phi$ with unit two-point normalization, the OPE gives the schematic four-point decomposition

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
{1\over x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
\sum_{\mathcal O} \lambda_{\phi\phi\mathcal O}^2 G_{\Delta,\ell}(u,v).
$$

Here $u$ and $v$ are cross-ratios and $G_{\Delta,\ell}$ is the conformal block for the primary $\mathcal O$ and its descendants. The sum is over primaries allowed in the $\phi\times\phi$ OPE.

The same correlator can be expanded in another channel. Crossing symmetry says the answers agree:

$$
\sum_{\mathcal O} \lambda_{\phi\phi\mathcal O}^2 G_{\Delta,\ell}(u,v)
=
\left({u\over v}\right)^{\Delta_\phi}
\sum_{\mathcal O} \lambda_{\phi\phi\mathcal O}^2 G_{\Delta,\ell}(v,u),
$$

up to the precise block normalization convention. This equation is where conformal data become constrained data.

For non-identical, spinning, or global-symmetry-covariant external operators, the same logic produces vector or matrix crossing equations.

## What counts as data

A practical CFT data record usually needs the following fields.

| Data field | Examples |
|---|---|
| Spacetime dimension | $d=2$, $d=3$, $d=4$, non-integer $d$ in continuation. |
| Symmetry labels | Spin, parity, global representation, charge, defect representation if present. |
| Primary dimensions | $\Delta_\sigma$, $\Delta_\epsilon$, $\Delta_J=d-1$, $\Delta_T=d$. |
| Two-point metric | $G_{AB}$ or a declaration of unit normalization. |
| OPE coefficients | $\lambda_{ABC}$, including tensor-structure labels when needed. |
| Central charges | $C_T$, $C_J$, 2D $c$, current levels, anomaly coefficients where applicable. |
| Selection rules | Which triples and OPE channels are allowed by symmetry. |
| Reality and positivity | Which coefficients can be chosen real, positive, or sign-convention-dependent. |

A Lagrangian may help compute these data. A lattice model may approximate them. A numerical bootstrap problem may bound them. But the data themselves are the CFT-facing language.

## Basis dependence

OPE coefficients are not invariant under arbitrary changes of operator basis. If primaries with the same quantum numbers mix by

$$
\mathcal O_A'=M_A{}^B\mathcal O_B,
$$

then the two-point metric and OPE coefficients transform. For example,

$$
G'_{AB}=M_A{}^C M_B{}^D G_{CD},
$$

and

$$
\lambda'_{ABC}=M_A{}^D M_B{}^E M_C{}^F \lambda_{DEF}.
$$

This is not a flaw. It is just linear algebra. Physical statements are basis-invariant: dimensions, representation content, invariant eigenvalues, properly normalized coefficients, and crossing-symmetric correlators.

Degeneracies deserve particular care. If two primaries have identical $\Delta$, spin, and symmetry labels, then individual OPE coefficients can be basis-dependent even though sums over the degenerate subspace are physical.

## Positivity and signs

In a unitary Euclidean CFT with reflection positivity, one can often choose real OPE coefficients for Hermitian scalar operators. In identical-scalar four-point functions, block coefficients often appear as squares:

$$
\lambda_{\phi\phi\mathcal O}^2\ge 0.
$$

This positivity is the engine of many numerical bootstrap bounds.

But do not overgeneralize it. Signs and phases can be convention-dependent when operators are charged, non-Hermitian, spinning, degenerate, or organized into nontrivial tensor structures. Mixed-correlator systems lead to positive semidefinite matrices rather than single nonnegative numbers. Nonunitary theories need not obey reflection positivity at all.

The safe statement is:

$$
\text{unitarity gives positivity after the correct inner product and channel decomposition are chosen.}
$$

## Free scalar example

For a free scalar in $d>2$, the elementary field $\phi$ has

$$
\Delta_\phi={d-2\over 2}.
$$

With unit-normalized two-point function,

$$
\langle \phi(x)\phi(0)\rangle={1\over |x|^{d-2}}.
$$

The OPE begins

$$
\phi(x)\phi(0)
\sim
{1\over |x|^{d-2}}\mathbf 1
+ \lambda_{\phi\phi \phi^2}|x|^{\Delta_{\phi^2}-2\Delta_\phi}\phi^2(0)
+ \cdots.
$$

Here $\Delta_{\phi^2}=d-2$ in the free theory, so the $\phi^2$ term has no power of $|x|$. Derivative descendants and higher composite primaries follow. Wick's theorem computes all OPE coefficients, but the conformal-data viewpoint packages the answer as a spectrum and OPE algebra rather than as a Gaussian path integral.

This example is almost too easy, which makes it useful. It shows the distinction between:

- the identity coefficient, fixed by the two-point function;
- primary coefficients, such as the coefficient of $\phi^2$;
- descendant coefficients, fixed once the primary coefficient is known;
- higher composite operators, which are additional primaries in the spectrum.

## Non-Lagrangian CFTs

The conformal-data language becomes essential for non-Lagrangian CFTs. In such theories, there may be no known weakly coupled fields, action, or Feynman diagram expansion. Yet the local operator spectrum and OPE coefficients still make sense.

Examples where this viewpoint is natural include:

- the 3D Ising CFT;
- many strongly coupled fixed points of RG flows;
- rational and irrational 2D CFTs;
- superconformal theories with no simple Lagrangian frame;
- holographic CFTs at strong coupling;
- defect CFTs and boundary CFTs.

The bootstrap is powerful precisely because it speaks the language of these theories directly.

## Common pitfalls

**Calling dimensions alone the conformal data.** Dimensions are only the spectrum. The OPE coefficients are equally important. A list of dimensions without OPE coefficients is like a multiplication table with the products erased.

**Counting descendants as independent data.** Descendants are fixed by representation theory. The primary spectrum is independent data; descendant contributions are packaged by conformal blocks.

**Ignoring the two-point metric.** Unit normalization is a choice, not a law. In degenerate spaces, charged sectors, and mixed systems, the two-point metric is part of the bookkeeping.

**Forgetting Ward-fixed coefficients.** Current and stress-tensor coefficients are constrained by charges, dimensions, and normalizations. They should not be varied freely in a bootstrap setup.

**Assuming every OPE coefficient is positive.** Positivity appears in specific unitary channels after choosing the right inner product and basis. It is not a universal sign rule for every $\lambda_{ABC}$.

**Confusing a CFT data set with a consistent CFT.** A formal spectrum and set of coefficients must still satisfy crossing, unitarity, permutation symmetry, Ward identities, and analytic consistency.

## Relations to other pages

- [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) introduces the data viewpoint before the OPE machinery is developed.
- [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) focuses on normalization, index raising, and coefficient extraction.
- [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) explains why different OPE channels must agree.
- [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) turns OPE families into four-point building blocks.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) develops the block decomposition used in scalar bootstrap equations.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) is where the consistency equations become the main object.
- [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) uses positivity and truncations of the conformal-data problem to obtain rigorous bounds and islands.

## Research status

The basic conformal-data statement is established: local CFT correlators are organized by primary spectra and OPE coefficients, with descendants fixed by conformal symmetry and consistency imposed by crossing and unitarity.

Active work concerns reconstruction and classification. Numerical bootstrap methods bound or approximate pieces of the data. Analytic bootstrap methods determine asymptotic regions of the data, such as large spin. In 2D, extended chiral algebras reorganize the data into Virasoro, affine, or vertex-operator-algebra structures. In holographic CFTs, large-$N$ and large-gap assumptions translate CFT data into bulk locality constraints.

## Exercises

### Exercise 1: Identity coefficient and two-point metric

Assume scalar primaries have OPE

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
c_{AB}{\mathbf 1\over |x|^{2\Delta_A}}+\cdots.
$$

Use the vacuum expectation value to show that $c_{AB}$ is the two-point metric $G_{AB}$.

<details><summary><strong>Solution</strong></summary>

Taking the vacuum expectation value gives

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\rangle
\sim
c_{AB}{\langle \mathbf 1\rangle\over |x|^{2\Delta_A}}+\cdots.
$$

Since $\langle \mathbf 1\rangle=1$ and non-identity operators have vanishing one-point functions in flat-space CFT vacuum, this becomes

$$
\langle \mathcal O_A(x)\mathcal O_B(0)\rangle
={c_{AB}\over |x|^{2\Delta_A}}.
$$

Comparing with the definition of the two-point metric gives $c_{AB}=G_{AB}$.

</details>

### Exercise 2: Raising an OPE index

Given $\lambda_{ABC}$ and two-point metric $G_{AB}$, show that the coefficient with one raised index is $\lambda_{AB}{}^C=\lambda_{ABD}G^{DC}$.

<details><summary><strong>Solution</strong></summary>

Insert the OPE into a three-point function with $\mathcal O_E$:

$$
\mathcal O_A\mathcal O_B\sim \lambda_{AB}{}^C\mathcal O_C.
$$

Taking the two-point function with $\mathcal O_E$ gives

$$
\lambda_{AB}{}^C G_{CE}=\lambda_{ABE}.
$$

Multiplying by the inverse metric $G^{ED}$ gives

$$
\lambda_{AB}{}^D=\lambda_{ABE}G^{ED}.
$$

Renaming dummy indices gives the stated formula.

</details>

### Exercise 3: Why descendants are not independent

Explain why a four-point conformal block is labeled by a primary dimension and spin, not by a separate coefficient for every descendant.

<details><summary><strong>Solution</strong></summary>

A descendant is obtained by acting on a primary with translation generators $P_\mu$. The commutation relations of the conformal algebra determine how all descendants transform. Once a primary appears in an OPE with coefficient $\lambda$, conformal symmetry fixes the coefficients of all descendant terms relative to $\lambda$.

A conformal block is precisely the sum of the primary contribution and this fixed descendant tower. Therefore each exchanged conformal family contributes one block multiplied by the relevant primary OPE coefficient or coefficient matrix.

</details>

### Exercise 4: Basis dependence

Let $\mathcal O_1$ and $\mathcal O_2$ be two degenerate scalar primaries with the same quantum numbers. Why can individual coefficients $\lambda_{AB1}$ and $\lambda_{AB2}$ be basis-dependent while the full contribution of the degenerate subspace to a correlator is basis-independent?

<details><summary><strong>Solution</strong></summary>

Because $\mathcal O_1$ and $\mathcal O_2$ have identical quantum numbers, one can rotate them by an invertible matrix without changing the spectrum. The individual coefficients transform under this rotation, so their numerical values depend on basis.

However, the correlator includes the complete sum over the degenerate subspace with the appropriate two-point metric. This full contraction is invariant under the change of basis. The basis-dependent components cancel between transformed OPE coefficients and transformed metric/projector data.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2016.
- D. Simmons-Duffin, "The Conformal Bootstrap", TASI lectures, 2017.
- D. Poland, S. Rychkov, and A. Vichi, "The Conformal Bootstrap: Theory, Numerical Techniques, and Applications", 2019.
- A. M. Polyakov, "Nonhamiltonian approach to conformal quantum field theory", 1974.
- K. G. Wilson, "Non-Lagrangian models of current algebra", 1969.

## Version history

- 2026-06-27: First polished draft. Synthesizes how the OPE encodes spectrum, two-point metric, primary coefficients, Ward-fixed data, and crossing constraints.
