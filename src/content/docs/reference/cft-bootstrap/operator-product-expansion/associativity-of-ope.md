---
title: "Associativity of the OPE"
description: "Explains how OPE associativity becomes crossing symmetry and why four-point functions test the consistency of CFT data."
sidebar:
  label: "OPE Associativity"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson 1969; Kadanoff 1969; Polyakov 1974; Belavin–Polyakov–Zamolodchikov 1984; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - operator product expansion
  - OPE associativity
  - crossing symmetry
  - conformal blocks
  - bootstrap equations
  - CFT data
canonicalTopics:
  - associativity-of-ope
  - operator-product-expansion
  - crossing-symmetry
  - conformal-block-decomposition
  - bootstrap-consistency
researchStatus:
  established:
    - "The local operator OPE of a CFT must be associative inside correlation functions: different ways of fusing operators give the same correlator."
    - "For four-point functions, OPE associativity is the conformal bootstrap crossing equation after the correlator is expanded in conformal blocks."
  active:
    - "Making associativity practical for spinning correlators, defects, nonunitary theories, Lorentzian regimes, and high-precision numerical systems remains a major source of technical work."
---

## Summary

The operator product expansion gives local operators a multiplication law. **Associativity of the OPE** says that this multiplication law is consistent: in a correlation function, fusing operators in different allowed orders must produce the same answer.

For four scalar primaries, the schematic statement is

$$
(\mathcal O_1\mathcal O_2)\mathcal O_3
=
\mathcal O_1(\mathcal O_2\mathcal O_3),
$$

where equality means equality inside correlation functions after summing over all primaries and descendants. In a four-point function, this becomes the crossing equation

$$
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,
G_{\mathcal O}^{(s)}(u,v)
=
\sum_{\mathcal O}
\lambda_{23\mathcal O}\lambda_{14\mathcal O}\,
G_{\mathcal O}^{(t)}(u,v),
$$

with the precise prefactors depending on the external dimensions and tensor conventions.

This is the conceptual heart of the conformal bootstrap. CFT data are not arbitrary lists of dimensions and OPE coefficients. They must define an associative local operator algebra compatible with conformal symmetry, unitarity, locality, and any global symmetries.

## Prerequisites

You should know [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), and [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/).

It is helpful to have seen [Conformal Blocks](/cft-bootstrap/conformal-blocks/) at a preview level, but the page is readable before the detailed conformal-block chapter.

## Core idea

The OPE is a local replacement rule. If $x_1$ approaches $x_2$, then

$$
\mathcal O_1(x_1)\mathcal O_2(x_2)
=
\sum_{\mathcal O}C_{12}{}^{\mathcal O}(x_{12},\partial_{x_2})\mathcal O(x_2)
$$

inside correlation functions in its convergence domain. The result is again a sum of local operators, so it can be fused with another operator. Associativity asks whether the answer is independent of which pair was fused first.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Two ways to fuse four operators using the OPE give crossing symmetry.](/figures/cft-bootstrap/ope-associativity-channels.svg)

<figcaption>

OPE associativity is the equality of different fusion histories. The $s$-channel fuses $\mathcal O_1\mathcal O_2$ and $\mathcal O_3\mathcal O_4$; the $t$-channel fuses $\mathcal O_2\mathcal O_3$ and $\mathcal O_1\mathcal O_4$. Crossing symmetry is this equality after each channel is expanded in conformal blocks.

</figcaption>
</figure>

This is not an optional extra axiom tacked onto CFT. It is what makes local operator products mutually consistent. Without associativity, three-point data would define many pairwise products, but there would be no well-defined theory of higher-point functions.

## Setup and conventions

We work in Euclidean signature unless stated otherwise. Local operators are organized into conformal multiplets, and the OPE sums over primary operators plus descendants fixed by conformal symmetry.

For scalar primaries with orthonormal two-point functions, the leading primary part of the OPE is

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ij\mathcal O}|x|^{\Delta_{\mathcal O}-\Delta_i-\Delta_j}\mathcal O(0).
$$

The full contribution of a primary family to a four-point function is its conformal block. Schematically,

$$
\text{one primary family in the OPE}
\quad\longrightarrow\quad
\text{one conformal block in the four-point function}.
$$

Different sources use different normalizations for conformal blocks. The invariant statement is not the name of the block, but equality of the full correlator.

## Four-point functions as the test case

Associativity first becomes nontrivial in four-point functions. Three-point functions are fixed by conformal symmetry up to OPE coefficients, so they define the candidate multiplication law. Four-point functions ask whether this multiplication law is consistent.

For identical scalar primaries $\phi$ with dimension $\Delta_\phi$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}G(u,v),
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The $12\to34$ OPE channel gives

$$
G(u,v)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2 g_{\Delta,\ell}(u,v),
$$

where $g_{\Delta,\ell}$ is the scalar conformal block for an exchanged primary of dimension $\Delta$ and spin $\ell$.

Exchanging $x_1$ and $x_3$ relates the same correlator to the channel in which the pairs are $32$ and $14$. For identical scalars this gives the crossing equation

$$
v^{\Delta_\phi}G(u,v)=u^{\Delta_\phi}G(v,u).
$$

Equivalently,

$$
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
\left[
  v^{\Delta_\phi}g_{\Delta,\ell}(u,v)
  -u^{\Delta_\phi}g_{\Delta,\ell}(v,u)
\right]=0.
$$

This equation is the simplest modern bootstrap equation. The unknowns are the spectrum $\{\Delta,\ell\}$ and the positive coefficients $\lambda_{\phi\phi\mathcal O}^2$.

The equation is infinite-dimensional. That is not a defect. A CFT generally has infinitely many local operators. The miracle is that conformal symmetry packages all descendant contributions into known functions, leaving only the primary spectrum and OPE coefficients to solve for.

## What exactly is associative?

The phrase “the OPE is associative” needs care because the product of local operators at coincident points is singular. The associative object is not an ordinary pointwise product

$$
\mathcal O_i(x)\mathcal O_j(x)
$$

at exactly the same point. The associative object is the system of convergent expansions inside separated correlation functions.

A good operational statement is:

> Pick a configuration of separated insertions. Expand the correlator by applying the OPE in any sequence whose convergence domains are valid, then analytically continue if necessary to compare with another valid channel. The final correlator must be the same.

For four points, this says that the $s$-, $t$-, and $u$-channel conformal-block decompositions describe the same single function. The OPE channels are not different theories. They are different coordinates on the same correlator.

## Algebraic form with operator-space indices

Let $\mathcal V_i$ denote the conformal family of $\mathcal O_i$. The OPE defines maps

$$
\mu_{ij}:\mathcal V_i\otimes\mathcal V_j
\longrightarrow
\bigoplus_k N_{ij}{}^k\mathcal V_k,
$$

where $N_{ij}{}^k$ records how many independent tensor structures or degenerate copies occur. In a scalar nondegenerate case, $N_{ij}{}^k$ is simply $0$ or $1$.

Associativity says that the two composite maps

$$
(\mu_{12}\otimes 1)\circ\mu_{(12)3},
\qquad
(1\otimes \mu_{23})\circ\mu_{1(23)},
$$

lead to the same local expansion after changing basis between intermediate channels. In two-dimensional rational CFT, this basis change is often described using fusion matrices. In higher-dimensional bootstrap practice, the same content appears as crossing equations for conformal blocks.

Do not overread this notation. A generic higher-dimensional CFT is not a finite-dimensional algebra with a small multiplication table. It is an infinite local operator algebra graded by scaling dimension, spin, and internal quantum numbers.

## Crossing as associativity plus kinematics

The bootstrap equation has two ingredients.

First, **kinematics**: conformal symmetry determines how one primary family contributes to a four-point function. That contribution is a conformal block.

Second, **dynamics**: the CFT chooses which primary families appear and with which OPE coefficients.

Associativity says that the dynamical data chosen in one channel must reproduce the same correlator in every other channel. In the identical-scalar example, the equation

$$
\sum_{\mathcal O}\lambda_{\mathcal O}^2 F_{\Delta,\ell}(u,v)=0
$$

uses the crossing vector

$$
F_{\Delta,\ell}(u,v)
=
  v^{\Delta_\phi}g_{\Delta,\ell}(u,v)
  -u^{\Delta_\phi}g_{\Delta,\ell}(v,u).
$$

The identity operator is always present in $\phi\times\phi$, so the equation is often written as

$$
F_{\mathbf 1}(u,v)+
\sum_{\mathcal O\ne \mathbf 1}\lambda_{\mathcal O}^2 F_{\Delta,\ell}(u,v)=0.
$$

This is the form used by many numerical bootstrap algorithms. Unitarity supplies

$$
\lambda_{\mathcal O}^2\ge 0,
$$

and the bootstrap asks which spectra can make the vector equation vanish.

## A simple example: generalized free fields

A generalized free scalar $\phi$ has a four-point function built by Wick-like pairings,

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
+
\frac{1}{x_{13}^{2\Delta_\phi}x_{24}^{2\Delta_\phi}}
+
\frac{1}{x_{14}^{2\Delta_\phi}x_{23}^{2\Delta_\phi}}.
$$

This function is manifestly crossing symmetric. But its OPE is not just the identity. It contains an infinite tower of double-trace-like primaries schematically

$$
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}\partial^{2n}\phi
\quad
\text{with}
\quad
\Delta=2\Delta_\phi+2n+\ell.
$$

Thus even the simplest crossing-symmetric four-point function needs an infinite operator spectrum in its OPE decomposition. Associativity is powerful precisely because it constrains the full tower, not because it reduces the theory to finitely many fields.

## A two-dimensional preview

In two-dimensional CFT there are two related but distinct notions:

1. associativity of the full local operator OPE;
2. associativity of chiral operator products in a holomorphic sector.

The Virasoro algebra and possible extended chiral algebras make the problem more rigid. Minimal models, for example, have finite sets of primary families under the full Virasoro symmetry. Their consistency conditions can be expressed through fusion rules, conformal blocks, modular data, and crossing equations.

The higher-dimensional bootstrap uses the same moral idea but less chiral algebra. Instead of relying on infinite-dimensional local conformal symmetry, it combines finite-dimensional conformal symmetry with unitarity and numerical convex optimization.

## Global symmetries and multiple channels

If operators transform under a global symmetry group $G$, the OPE decomposes into irreducible representations of $G$. For example, in an $O(N)$ model, the OPE of a vector scalar $\phi_i$ with itself contains singlet, symmetric traceless, and antisymmetric sectors:

$$
\phi_i\times\phi_j
\sim
S^+ + T^+ + A^-.
$$

The superscripts indicate the spin parity in the identical-boson case. Crossing becomes a vector or matrix equation coupling different representation sectors. This is why mixed-correlator and global-symmetry bootstrap problems have matrix-valued positivity conditions rather than a single scalar sum.

The principle is unchanged: all channels are different expansions of the same correlator. The bookkeeping becomes richer because the OPE has representation labels and tensor structures.

## Common pitfalls

**Pitfall 1: thinking associativity means ordinary multiplication of singular operators.** Local operator products are distributions with short-distance singularities. Associativity is a statement about convergent OPE expansions inside separated correlators.

**Pitfall 2: checking only one OPE channel.** A list of dimensions and OPE coefficients that gives a plausible $s$-channel expansion is not automatically a CFT. It must also satisfy crossing with the other channels.

**Pitfall 3: forgetting descendants.** The bootstrap sum is over primaries, but each primary contribution includes all descendants through its conformal block.

**Pitfall 4: treating $\lambda^2$ as always positive.** Positivity of squared OPE coefficients is a special feature of reflection-positive channels with real identical external operators and appropriate two-point normalization. General mixed or spinning systems use positive matrices, not always simple positive numbers.

**Pitfall 5: confusing fusion rules with OPE coefficients.** A fusion rule says whether a family can appear. An OPE coefficient says with what strength it appears. Both matter.

## Relations to other pages

[OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) explains why an OPE channel is a controlled expansion in Euclidean radial quantization. This page explains why different controlled expansions must agree.

[OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) explains the three-point data that enter the crossing equation. [Conformal Blocks](/cft-bootstrap/conformal-blocks/) develops the functions $g_{\Delta,\ell}(u,v)$ that package descendant contributions. [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) will turn the associativity statement into the main bootstrap logic.

## Research status

For ordinary unitary Euclidean CFTs, OPE associativity and crossing symmetry are foundational and established. They are the organizing principle behind the modern conformal bootstrap.

The frontier is not whether associativity matters. The frontier is how to implement it completely and efficiently: spinning correlators, defects, boundaries, supersymmetric multiplets, non-invertible symmetries, Lorentzian causality, Regge limits, modular constraints, numerical precision, and rigorous reconstruction of a full CFT from finite bootstrap data all remain technically demanding.

## Exercises

### Exercise 1: derive identical-scalar crossing

Starting from

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}G(u,v),
$$

show that invariance under $x_1\leftrightarrow x_3$ implies

$$
v^{\Delta_\phi}G(u,v)=u^{\Delta_\phi}G(v,u).
$$

<details><summary><strong>Solution</strong></summary>

Under $x_1\leftrightarrow x_3$, the cross-ratios transform as

$$
u\leftrightarrow v.
$$

The same correlator can also be written as

$$
\langle \phi_3\phi_2\phi_1\phi_4\rangle
=
\frac{1}{x_{23}^{2\Delta_\phi}x_{14}^{2\Delta_\phi}}G(v,u).
$$

Equating the two forms gives

$$
\frac{G(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}
=
\frac{G(v,u)}{x_{23}^{2\Delta_\phi}x_{14}^{2\Delta_\phi}}.
$$

Using

$$
\frac{x_{12}^2x_{34}^2}{x_{23}^2x_{14}^2}=\frac{u}{v},
$$

we get

$$
G(u,v)=\left(\frac{u}{v}\right)^{\Delta_\phi}G(v,u),
$$

or equivalently

$$
v^{\Delta_\phi}G(u,v)=u^{\Delta_\phi}G(v,u).
$$

</details>

### Exercise 2: why even spins appear for identical scalars

Assume $\phi$ is a real identical scalar operator. Explain why the OPE $\phi\times\phi$ contains only even-spin primaries in parity-even scalar tensor structures.

<details><summary><strong>Solution</strong></summary>

The product of two identical bosonic scalar insertions is symmetric under exchanging the two operators. In a three-point function

$$
\langle \phi(x_1)\phi(x_2)\mathcal O_{\mu_1\cdots\mu_\ell}(x_3)\rangle,
$$

the unique parity-even scalar-scalar-spin-$\ell$ tensor structure changes by $(-1)^\ell$ under $x_1\leftrightarrow x_2$. Symmetry of the identical scalar pair therefore requires

$$
(-1)^\ell=1,
$$

so $\ell$ must be even. With non-identical scalars, parity-odd structures, or extra internal tensors, the selection rule can change.

</details>

### Exercise 3: identity block and the need for other operators

For an identical scalar, the identity contribution in the $12\to34$ channel gives $G(u,v)\supset 1$. Show that the identity block alone cannot satisfy crossing unless $\Delta_\phi=0$.

<details><summary><strong>Solution</strong></summary>

If the four-point function were only the identity contribution, then

$$
G(u,v)=1.
$$

Crossing would require

$$
v^{\Delta_\phi}=u^{\Delta_\phi}
$$

for arbitrary cross-ratios $u,v$. This is false unless $\Delta_\phi=0$. Therefore a nontrivial scalar four-point function must include additional operator contributions in the OPE so that the full sum, not the identity term alone, obeys crossing.

</details>

## References

- K. G. Wilson, “Non-Lagrangian Models of Current Algebra,” 1969.
- L. P. Kadanoff, “Operator Algebra and the Determination of Critical Indices,” 1969.
- A. M. Polyakov, “Non-Hamiltonian Approach to Conformal Quantum Field Theory,” 1974.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” 1984.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, 1997.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” 2017.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.

## Version history

- **2026-06-27:** First polished draft. Defines OPE associativity, derives the identical-scalar crossing equation, and connects associativity to conformal blocks and bootstrap positivity.
