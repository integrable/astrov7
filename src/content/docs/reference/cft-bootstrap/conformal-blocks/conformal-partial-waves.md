---
title: "Conformal Partial Waves"
description: "Explains conformal partial waves as the contribution of one exchanged conformal multiplet to a four-point function and relates them to conformal blocks."
sidebar:
  label: "Conformal Partial Waves"
  order: 1
level: Graduate
status: "Polished draft"
source: "Ferrara–Gatto–Grillo 1973; Polyakov 1974; Dolan–Osborn 2003; Simmons-Duffin 2012; Rychkov 2016; Poland–Rychkov–Vichi 2019"
topics:
  - conformal partial waves
  - conformal blocks
  - OPE channels
  - conformal multiplets
  - four-point functions
  - shadow formalism
canonicalTopics:
  - conformal-partial-waves
  - conformal-blocks
  - ope-decomposition
  - cft-data
  - bootstrap-kinematics
researchStatus:
  established:
    - "A conformal partial wave isolates the contribution of a chosen conformal multiplet to a four-point function in a chosen OPE channel."
    - "For scalar four-point functions in a fixed normalization, the corresponding conformal block is a universal function multiplied by a product of OPE coefficients."
  active:
    - "The terminology and computational realization of partial waves are especially subtle for spinning correlators, shadow representations, defects, Lorentzian inversion, and supersymmetric multiplets."
---

## Summary

A **conformal partial wave** is the contribution of one exchanged conformal multiplet to a four-point function in a chosen OPE channel. It is the conformal analogue of an angular-momentum partial wave in scattering theory: symmetry fixes the shape of each wave, while the particular theory fixes the coefficients with which the waves are combined.

For four scalar primaries, after stripping a conventional kinematic prefactor, the $12\to34$ channel expansion is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v).
$$

Here $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)$ is the conformal block associated with a primary of dimension $\Delta$ and spin $\ell$, together with all of its descendants. The product $\lambda_{12\mathcal O}\lambda_{34\mathcal O}$ is dynamical CFT data. The block is kinematics.

This page explains the Hilbert-space projector picture behind the formula, the distinction between partial waves and blocks, and the shadow subtlety that often appears in the literature.

## Prerequisites

You should know [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), and [Conformal Data from OPE](/cft-bootstrap/operator-product-expansion/conformal-data-from-ope/).

The page uses Euclidean CFT notation. Lorentzian partial waves, inversion formulas, Regge limits, and lightcone expansions are postponed to later chapters.

## Core idea

Choose a four-point function and decide which pair of operators to fuse first. In the $12\to34$ channel, the first OPE creates a sum of states on a sphere surrounding $x_1$ and $x_2$. Those states decompose into conformal multiplets. If we keep only one multiplet and then contract it with the states created by $x_3$ and $x_4$, we get one conformal partial wave.

In radial quantization, the idea is simply

$$
\langle 0|\mathcal O_4\mathcal O_3\mathcal O_2\mathcal O_1|0\rangle
=
\sum_{\mathcal M}
\langle 0|\mathcal O_4\mathcal O_3\,\mathbb P_{\mathcal M}\,\mathcal O_2\mathcal O_1|0\rangle,
$$

where $\mathbb P_{\mathcal M}$ projects onto one conformal multiplet $\mathcal M$. The corresponding term is the partial wave of that multiplet.

<figure class="doc-figure" style="--figure-width: 43rem;">

![A conformal partial wave isolates the exchange of one conformal multiplet between two OPE pairs.](/figures/cft-bootstrap/conformal-partial-wave-exchange.svg)

<figcaption>

A conformal partial wave is the contribution of one exchanged conformal multiplet in a chosen OPE channel. The primary $\mathcal O_{\Delta,\ell}$ and all of its descendants are exchanged together; conformal symmetry fixes their relative weights.

</figcaption>
</figure>

The important point is that descendants are not optional extra operators. Once a primary appears, the whole multiplet appears. A conformal block is the universal function that packages this entire contribution.

## Setup and conventions

Let $\mathcal O_i$ be scalar primaries of dimensions $\Delta_i$. We write

$$
\Delta_{ij}\equiv \Delta_i-\Delta_j,
\qquad
x_{ij}=x_i-x_j,
$$

and use the standard cross-ratios

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

A convenient scalar four-point form is

$$
\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\mathcal G(u,v).
$$

The reduced correlator $\mathcal G(u,v)$ contains the dynamical information. Its $12\to34$ block expansion is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in \mathcal O_1\times\mathcal O_2}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v),
$$

where the sum runs over primary operators that can appear in the $\mathcal O_1\times\mathcal O_2$ OPE and can also couple to $\mathcal O_3\times\mathcal O_4$.

## The partial-wave decomposition

The OPE gives

$$
\mathcal O_1(x_1)\mathcal O_2(x_2)
=
\sum_{\mathcal O}\lambda_{12\mathcal O}\,
C_{12\mathcal O}(x_{12},\partial_{x_2})\mathcal O(x_2),
$$

where $C_{12\mathcal O}$ is a differential operator that creates the descendants of the primary $\mathcal O$. Applying the same logic to the other pair gives the four-point expansion

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
\Bigl[\text{fixed contribution of the multiplet of }\mathcal O\Bigr].
$$

The phrase in brackets is the conformal partial wave before one strips off the scalar prefactor. After stripping the prefactor, it is the conformal block $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v)$, up to the convention-dependent distinction discussed below.

The decomposition is channel-dependent. The $12\to34$ channel is often called the $s$-channel. The $14\to23$ and $13\to24$ channels give different expansions of the same function. Crossing symmetry is the statement that these expansions agree where their convergence domains overlap and by analytic continuation beyond that overlap.

## Projectors onto conformal multiplets

The cleanest conceptual definition uses a projector. Let $|\mathcal O,a\rangle$ be a basis of states in the conformal multiplet generated from the primary $\mathcal O$, including spin components and descendants. Let

$$
B_{ab}=\langle \mathcal O,a|\mathcal O,b\rangle
$$

be the Gram matrix in radial quantization. Then the projector onto the multiplet is formally

$$
\mathbb P_{\mathcal O}
=
\sum_{a,b}|\mathcal O,a\rangle(B^{-1})^{ab}\langle \mathcal O,b|.
$$

In a unitary theory after null states are quotiented out, $B$ is positive definite. In a nonunitary theory, or before quotienting null descendants, this formula must be interpreted with more care.

The conformal partial wave in the $12\to34$ channel is then

$$
W_{\mathcal O}^{(12)(34)}(x_i)
=
\langle 0|\mathcal O_4(x_4)\mathcal O_3(x_3)
\mathbb P_{\mathcal O}
\mathcal O_2(x_2)\mathcal O_1(x_1)|0\rangle.
$$

This equation is not usually how one computes blocks. It is how one remembers what they mean. A block is a resolution-of-the-identity term in the radial-quantization Hilbert space.

## From partial waves to conformal blocks

A conformal partial wave still includes the external coordinate prefactor. A conformal block is the reduced cross-ratio function that remains after the standard scalar prefactor has been stripped:

$$
W_{\mathcal O}^{(12)(34)}(x_i)
=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(u,v).
$$

This is the convention used on this page: the phrase **partial wave** refers to the projected contribution in the full four-point function; the phrase **conformal block** refers to the reduced function of cross-ratios with unit OPE coefficient.

Other authors sometimes use the words differently. In particular, in Euclidean harmonic analysis, “conformal partial wave” often means a single-valued eigenfunction built from a block plus its shadow. That distinction is real, not pedantry; it affects boundary conditions and analytic structure.

## The shadow subtlety

The conformal Casimir eigenvalue for a symmetric traceless primary of dimension $\Delta$ and spin $\ell$ is

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This is invariant under

$$
\Delta\longrightarrow d-\Delta.
$$

The operator with dimension $d-\Delta$ and the same spin is called the **shadow** of $\mathcal O$. Because the Casimir eigenvalue is the same, the Casimir differential equation alone does not distinguish the physical block from the shadow block.

Schematically, a Euclidean shadow-formalism partial wave often has the form

$$
\Psi_{\Delta,\ell}(u,v)
=
G_{\Delta,\ell}(u,v)
+K_{\Delta,\ell}
G_{d-\Delta,\ell}(u,v),
$$

with a convention-dependent coefficient $K_{\Delta,\ell}$. The physical OPE block is selected by its small-$u$ behavior in the chosen channel. It behaves as the contribution of an operator of dimension $\Delta$, not as the contribution of its shadow.

This is the main reason that one must specify both the differential equation and the OPE boundary condition when defining blocks.

## OPE limits and normalization

The leading behavior of a block is fixed by the primary term in the OPE. In radial variables $(r,\eta)$, a standard normalization is

$$
G_{\Delta,\ell}(r,\eta)
=
r^\Delta C_\ell^{(\nu)}(\eta)+O(r^{\Delta+1}),
\qquad
\nu=\frac{d-2}{2},
$$

where $C_\ell^{(\nu)}$ is a Gegenbauer polynomial. The variable $r$ measures how small the $12$ pair is relative to the other insertions, while $\eta$ records the angle between the two OPE directions.

Different authors absorb constants into $G_{\Delta,\ell}$, into $C_\ell^{(\nu)}$, or into the OPE coefficient. This is harmless only if the convention is used consistently. The product

$$
\lambda_{12\mathcal O}\lambda_{34\mathcal O}G_{\Delta,\ell}
$$

is the meaningful contribution to the reduced correlator.

For identical real scalars $\phi$ with unit two-point normalization, reflection positivity implies

$$
\lambda_{\phi\phi\mathcal O}^2\ge 0
$$

for every allowed exchanged primary in the Euclidean OPE. Bose symmetry also restricts the spins that can appear. For identical scalar pairs, odd-spin symmetric-traceless exchanges are absent in the $\phi\times\phi$ OPE. This positivity is what makes the simplest numerical bootstrap bounds possible.

## Why descendants bring no new data

The four-point function could have looked hopeless: after inserting one primary, one might expect every descendant to require an independent coefficient. Conformal symmetry prevents that. Descendants are generated by the momentum operators $P_\mu$, and their inner products and transformation laws are fixed by the conformal algebra.

Once the three-point coefficient $\lambda_{12\mathcal O}$ is fixed, the matrix elements

$$
\langle \mathcal O_1\mathcal O_2|P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
$$

are fixed relative to the primary matrix element. The same is true on the $34$ side. Summing over the descendant tower gives the block.

This is the kinematic miracle behind conformal blocks:

$$
\text{one primary coefficient}
\quad\Longrightarrow\quad
\text{one entire descendant tower}.
$$

For spinning external operators, there may be several independent three-point tensor structures, and therefore several OPE coefficients. But the descendant contributions attached to each tensor structure are still fixed by symmetry.

## Spinning and mixed-correlator generalization

For spinning correlators or external operators in nontrivial global-symmetry representations, the block expansion becomes matrix-valued. A typical schematic form is

$$
\mathcal G_I(u,v)
=
\sum_{\mathcal O}\sum_{a,b}
\lambda_{12\mathcal O}^{(a)}
\lambda_{34\mathcal O}^{(b)}
G_{\mathcal O,I}^{ab}(u,v),
$$

where $I$ labels four-point tensor structures and $a,b$ label independent three-point structures. The object $G_{\mathcal O,I}^{ab}$ is still fixed by symmetry, but it is no longer a single scalar function.

This is why mixed-correlator bootstrap problems naturally lead to vector and matrix crossing equations. The block remains kinematic; the bookkeeping becomes richer.

## Checks

A conformal partial-wave expansion should pass four basic checks.

First, the identity multiplet should reproduce the correct disconnected or vacuum-channel contribution. For a unit-normalized identical scalar $\phi$, the $12\to34$ identity contribution gives

$$
\mathcal G(u,v)=1+\text{non-identity exchanges}.
$$

Second, the small-$u$ OPE limit should match the leading power dictated by the exchanged dimension. If the leading behavior looks like the shadow dimension instead, the wrong solution of the Casimir equation has been selected.

Third, the block should be an eigenfunction of the quadratic conformal Casimir in the chosen channel:

$$
\mathcal C_{12}G_{\Delta,\ell}=C_{\Delta,\ell}G_{\Delta,\ell}.
$$

Fourth, after summing all exchanged multiplets with their coefficients, the result must satisfy the required permutation, global-symmetry, and crossing relations. A single block is not crossing symmetric by itself.

## Common pitfalls

Do not use “partial wave” and “block” interchangeably without checking convention. In many bootstrap papers the block is the OPE-selected contribution, while the partial wave in shadow language includes both physical and shadow branches.

Do not forget the channel. The same exchanged primary may appear in different channels with different OPE coefficient products and different cross-ratio arguments.

Do not infer CFT dynamics from the shape of a block alone. The block knows representation theory. The spectrum and OPE coefficients know the theory.

Do not ignore degeneracies. If several primaries have the same $\Delta$, spin, and symmetry representation, a block expansion may only see sums of products of OPE coefficients unless an additional basis choice or mixed-correlator data resolves the degeneracy.

Do not assume that positivity survives every generalization. Identical scalar unitary correlators have positive squared OPE coefficients in the right basis. Spinning correlators, nonidentical correlators, nonunitary theories, and nontrivial tensor-structure bases require more careful positivity statements.

## Relations to other pages

[OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) explains why exchanging a conformal multiplet is natural. This page explains what the exchanged multiplet contributes to a four-point function.

[Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) turns the present conceptual picture into explicit scalar-block formulas. [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) derives blocks as Casimir eigenfunctions. [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) explains the descendant-level expansion and convergence.

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) uses block decompositions in different channels and requires them to agree. [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) uses block vectors and OPE positivity to derive rigorous constraints.

## Research status

The basic conformal partial-wave and block decomposition is settled. For scalar four-point functions it is standard technology, and several equivalent characterizations are known: OPE sums, projectors, Casimir equations, shadow integrals, and radial expansions.

The active frontier is not the existence of blocks but their efficient and conceptually clean use in harder settings. Spinning correlators, mixed systems, defects, supersymmetric multiplets, Lorentzian inversion formulas, nonunitary theories, and numerical implementations continue to motivate new block technology.

## Exercises

1. **OPE products in a four-point function.** Use the OPE twice to explain why the coefficient multiplying a scalar block in the $12\to34$ channel is $\lambda_{12\mathcal O}\lambda_{34\mathcal O}$.

<details><summary><strong>Solution</strong></summary>

Apply the OPE to the first pair:

$$
\mathcal O_1\mathcal O_2
\sim
\sum_{\mathcal O}\lambda_{12\mathcal O}\,C_{12\mathcal O}\mathcal O.
$$

Apply the OPE to the second pair:

$$
\mathcal O_3\mathcal O_4
\sim
\sum_{\mathcal O'}\lambda_{34\mathcal O'}\,C_{34\mathcal O'}\mathcal O'.
$$

The two-point function pairs operators only with operators in the same conformal representation, up to degeneracies and index contractions. Therefore the contribution of the multiplet $\mathcal O$ is proportional to the product $\lambda_{12\mathcal O}\lambda_{34\mathcal O}$. The remaining descendant sum is fixed by symmetry and is called the block.

</details>

2. **Identity block.** For a unit-normalized identical scalar $\phi$, show that the identity exchange gives $\mathcal G(u,v)=1$ in the $12\to34$ channel.

<details><summary><strong>Solution</strong></summary>

The identity term in the OPE is

$$
\phi(x_1)\phi(x_2)
\supset
\frac{\mathbf 1}{(x_{12}^2)^\Delta}.
$$

Similarly,

$$
\phi(x_3)\phi(x_4)
\supset
\frac{\mathbf 1}{(x_{34}^2)^\Delta}.
$$

Thus the identity contribution to the full correlator is

$$
\frac{1}{(x_{12}^2)^\Delta(x_{34}^2)^\Delta}.
$$

For identical scalars, the standard four-point prefactor is exactly this factor. After stripping it off, the reduced identity contribution is

$$
\mathcal G_{\mathbf 1}(u,v)=1.
$$

</details>

3. **Why the Casimir equation is not enough.** Explain why the same quadratic Casimir eigenvalue cannot distinguish an exchanged dimension $\Delta$ from $d-\Delta$.

<details><summary><strong>Solution</strong></summary>

For a symmetric traceless exchanged primary, the quadratic Casimir eigenvalue is

$$
C_{\Delta,\ell}
=\Delta(\Delta-d)+\ell(\ell+d-2).
$$

Replacing $\Delta$ by $d-\Delta$ gives

$$
(d-\Delta)((d-\Delta)-d)+\ell(\ell+d-2)
=(d-\Delta)(-\Delta)+\ell(\ell+d-2),
$$

which equals $\Delta(\Delta-d)+\ell(\ell+d-2)$. Therefore the Casimir equation has both physical and shadow branches. The OPE limit selects the physical conformal block.

</details>

4. **Degenerate primaries.** Suppose two primaries $\mathcal O_A$ and $\mathcal O_B$ have identical dimension, spin, and global-symmetry representation. What does a single scalar four-point block expansion measure?

<details><summary><strong>Solution</strong></summary>

If the two primaries have the same quantum numbers, they contribute the same block function in that correlator. The coefficient multiplying that block is the sum of products of OPE coefficients, schematically

$$
\lambda_{12A}\lambda_{34A}+\lambda_{12B}\lambda_{34B},
$$

after choosing an orthonormal basis in the degenerate space. A single correlator may not separate the two operators. Additional correlators or a basis adapted to more data may be needed to resolve the degeneracy.

</details>

## References

- A. M. Polyakov, “Nonhamiltonian Approach to Conformal Quantum Field Theory,” *Soviet Physics JETP* **39** (1974). Early bootstrap and OPE-channel viewpoint.
- F. A. Dolan and H. Osborn, “Conformal Partial Waves and the Operator Product Expansion,” *Nuclear Physics B* **678** (2004). Classic derivation of higher-dimensional conformal partial waves from Casimir equations.
- D. Simmons-Duffin, “Projectors, Shadows, and Conformal Blocks,” *Journal of High Energy Physics* **04** (2014). Modern treatment of conformal projectors, shadows, and spinning blocks.
- M. Hogervorst and S. Rychkov, “Radial Coordinates for Conformal Blocks,” *Physical Review D* **87** (2013). Radial-quantization interpretation and efficient series expansion for blocks.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Pedagogical source for OPE, radial quantization, conformal blocks, and bootstrap.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Detailed lecture-note account of conformal blocks and numerical bootstrap setup.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Review of modern conformal-block technology and applications.

## Version history

- 2026-06-27: Added first polished version explaining conformal partial waves, projectors, shadows, and their relation to conformal blocks.
