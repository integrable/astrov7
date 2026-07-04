---
title: "Conformal Blocks in Higher Dimensions"
description: "Explains conformal blocks for CFTs in dimensions greater than two, including scalar blocks, Casimir equations, radial expansions, spinning blocks, and bootstrap use."
sidebar:
  label: "Blocks in Higher Dimensions"
  order: 9
level: Graduate
status: "Polished draft"
source: "Dolan–Osborn 2001; Dolan–Osborn 2004; Hogervorst–Rychkov 2013; Costa–Penedones–Poland–Rychkov 2011; Karateev–Kravchuk–Simmons-Duffin 2018; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - higher-dimensional CFT
  - conformal blocks
  - scalar conformal blocks
  - spinning conformal blocks
  - radial expansion
  - Casimir equation
  - numerical bootstrap
canonicalTopics:
  - conformal-blocks-in-higher-dimensions
  - higher-dimensional-conformal-blocks
  - scalar-conformal-blocks
  - spinning-conformal-blocks
  - radial-expansion
  - numerical-bootstrap-inputs
researchStatus:
  established:
    - "For dimensions greater than two, conformal blocks are fixed by the finite-dimensional conformal group and are labeled by conformal multiplets, usually by dimension and spin for scalar external operators."
    - "Casimir equations, radial expansions, recursion relations, and embedding-space methods provide standard ways to compute higher-dimensional blocks."
  active:
    - "Efficient computation of spinning blocks, mixed-correlator systems, noninteger dimensions, defects, boundaries, and large numerical bootstrap problems remains technically active."
---

## Summary

Higher-dimensional conformal blocks are the building blocks of the bootstrap in dimensions $d>2$. They are the contribution of one irreducible conformal multiplet to a four-point function.

For scalar external operators, the exchanged primary is usually labeled by a scaling dimension $\Delta$ and spin $\ell$:

$$
\mathcal O_{\Delta,\ell}
\quad\longrightarrow\quad
G_{\Delta,\ell}^{(d)}(z,\bar z).
$$

The reduced four-point function has the schematic expansion

$$
\mathcal G(z,\bar z)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{12,34}(z,\bar z),
$$

where

$$
 u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The variables $z$ and $\bar z$ are useful coordinates on the two conformal cross-ratios. In dimensions greater than two they are **not** left- and right-moving chiral coordinates, and higher-dimensional blocks do not factor into holomorphic and antiholomorphic pieces.

For radial expansions we use

$$
\alpha=\frac{d-2}{2}
$$

as the Gegenbauer index. In the OPE limit,

$$
G_{\Delta,\ell}^{(d)}(r,\eta)
\sim
r^\Delta C_\ell^{(\alpha)}(\eta),
\qquad
r\to0,
$$

up to the normalization convention for $C_\ell^{(\alpha)}$. This is the compact mental model: a higher-dimensional block is one primary of dimension $\Delta$ and spin $\ell$, plus all descendants, organized by radial quantization.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A higher-dimensional conformal block is computed from representation-theoretic data using Casimir equations, radial expansions, recursion relations, and tensor-structure technology.](/figures/cft-bootstrap/higher-dimensional-block-toolkit.svg)

<figcaption>

Higher-dimensional blocks translate exchanged representation data $(\Delta,\ell)$ and external tensor structures into functions of cross-ratios. Casimir equations, OPE boundary conditions, radial coordinates, recursion relations, and tensor-structure methods are complementary ways of computing the same kinematic object.

</figcaption>
</figure>

## Prerequisites

You should know [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/), [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/), [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/), and [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/).

This page also uses the notation of [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) and [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/). The comparison with $d=2$ is explained in [Conformal Blocks in Two Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-two-dimensions/) and [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/).

## Core idea

The defining property of a conformal block is representation-theoretic:

$$
\text{block}
=
\text{all descendants of one exchanged primary, with coefficients fixed by conformal symmetry}.
$$

For scalar external operators in a parity-even CFT, the exchanged primary transforms in a symmetric traceless representation of $SO(d)$. Its spin is a nonnegative integer $\ell$, and the block is labeled by

$$
(\Delta,\ell).
$$

The OPE limit fixes the leading behavior. In radial variables $r$ and $\eta$, where $\eta$ is the cosine of the angle between two radial directions, the block behaves as

$$
G_{\Delta,\ell}^{(d)}(r,\eta)
\sim
r^\Delta C_\ell^{(\alpha)}(\eta),
\qquad
\alpha=\frac{d-2}{2}.
$$

The hard part is not the leading term. The hard part is summing all descendants efficiently and accurately.

## Setup and conventions

For four scalar primaries $\phi_i$ of dimensions $\Delta_i$, define

$$
 u=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

A convenient stripped form of the four-point function is

$$
\langle\phi_1(x_1)\phi_2(x_2)\phi_3(x_3)\phi_4(x_4)\rangle
=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\mathcal G(u,v),
$$

where $\Delta_{ij}=\Delta_i-\Delta_j$. The $12\to34$ OPE expansion is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\mathcal O}^{(d)}(u,v).
$$

When the external operators are scalars, the exchanged operator in the OPE is a symmetric traceless tensor,

$$
\mathcal O_{\mu_1\cdots\mu_\ell},
$$

so we write

$$
G_{\mathcal O}^{(d)}(u,v)=G_{\Delta,\ell}^{(d)}(u,v).
$$

For spinning external operators or more general exchanged representations, the block carries tensor-structure labels. It becomes a vector or matrix of functions rather than one scalar function.

## Scalar blocks

Scalar blocks are the simplest and most heavily used higher-dimensional blocks. They appear when all four external operators are scalars. The exchanged operator may have spin $\ell$, so the block is not scalar in its representation-theoretic origin, but the final function depends only on cross-ratios.

For identical external scalars $\phi$, the expansion becomes

$$
\mathcal G(u,v)
=
1+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}^{(d)}(u,v).
$$

In a unitary CFT with real operators and diagonal two-point normalization,

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This positivity is what makes the numerical bootstrap powerful.

The OPE limit is the normalization anchor. In the radial frame, with

$$
\rho=re^{i\theta},
\qquad
\bar\rho=re^{-i\theta},
\qquad
\eta=\cos\theta,
$$

the leading term is

$$
G_{\Delta,\ell}^{(d)}(r,\eta)
=
r^\Delta\left(C_\ell^{(\alpha)}(\eta)+O(r)\right),
\qquad
\alpha=\frac{d-2}{2},
$$

up to the conventional normalization of the Gegenbauer polynomial. Some authors divide by $C_\ell^{(\alpha)}(1)$ so that the leading angular factor is $1$ at $\eta=1$.

## Casimir equation

The quadratic conformal Casimir acts on the pair of external points in a chosen OPE channel. The block is an eigenfunction:

$$
\mathcal D_{12}G_{\Delta,\ell}^{(d)}(z,\bar z)
=
C_{\Delta,\ell}G_{\Delta,\ell}^{(d)}(z,\bar z),
$$

where

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

The first term is the dilatation part of the conformal Casimir. The second term is the quadratic Casimir of the spin-$\ell$ symmetric traceless representation of $SO(d)$.

The Casimir equation does not by itself choose the physical block. There is also a shadow solution with dimension $d-\Delta$. The physical block is selected by the OPE boundary condition

$$
G_{\Delta,\ell}^{(d)}(r,\eta)
\sim
r^\Delta C_\ell^{(\alpha)}(\eta).
$$

The Casimir equation is conceptually clean but not always the most efficient computational method. It explains why blocks are special functions; radial and recursion methods explain why they are useful in large numerical calculations.

## Radial expansion

Radial quantization gives a convergent expansion for Euclidean configurations. Insert a complete set of descendants between two spheres. The primary contributes $r^\Delta$, and level-$n$ descendants contribute $r^{\Delta+n}$. A scalar block therefore has the structure

$$
G_{\Delta,\ell}^{(d)}(r,\eta)
=
r^\Delta
\sum_{n=0}^{\infty}
\sum_j
B_{n,j}\,r^n C_j^{(\alpha)}(\eta),
$$

where the spins $j$ are the rotation representations appearing among descendants at level $n$.

This expansion is not just pretty. It is practical. At the crossing-symmetric point, the radial coordinate is small, so a modest number of terms can approximate blocks with high accuracy. This is why radial coordinates and recursion relations are central to numerical bootstrap technology.

## Recursion and poles

Conformal blocks have a useful analytic structure as functions of the exchanged dimension $\Delta$. At special values of $\Delta$, a descendant can itself become primary. The conformal multiplet becomes reducible, and the block develops a pole. The residue is proportional to another block.

Schematically,

$$
G_{\Delta,\ell}
=
G_{\Delta,\ell}^{\rm regular}
+
\sum_A
\frac{R_A}{\Delta-\Delta_A^*}
G_{\Delta_A',\ell_A'}.
$$

This is the representation-theoretic origin of recursion relations. Rather than computing every descendant coefficient independently, one uses the pole structure to bootstrap the block itself.

The same idea underlies the rational approximations used by semidefinite-programming bootstrap codes: after taking derivatives at the crossing-symmetric point, the dependence on $\Delta$ can be approximated by rational functions with controlled precision.

## Special dimensions

Some dimensions have special simplifications.

In $d=2$, global blocks factorize into holomorphic and antiholomorphic hypergeometric functions. This is the global $SL(2)\times SL(2)$ story. Full two-dimensional CFT has Virasoro blocks, which are larger objects.

In $d=4$, scalar blocks have compact Dolan–Osborn formulas in terms of one-variable hypergeometric functions. A common building block is

$$
k_\beta(x)
=
x^{\beta/2}
{}_2F_1\left(
\frac{\beta-\Delta_{12}}{2},
\frac{\beta+\Delta_{34}}{2};
\beta;
x
\right).
$$

Four-dimensional scalar blocks can be written as antisymmetrized combinations of $k$ functions divided by $z-\bar z$, with convention-dependent prefactors.

In $d=3$, which is central for critical phenomena, there is no equally simple universal factorized expression for general external dimensions and spins. Recursion and radial methods are the workhorses.

In noninteger dimension, blocks can still be analytically continued and used in bootstrap and $\epsilon$-expansion comparisons. One must then interpret spin and representation theory with appropriate care.

## Spinning blocks

When external operators carry spin, a four-point function has multiple tensor structures. A block is no longer a single scalar function; it is a vector or matrix of functions multiplying tensor structures.

Schematic notation looks like

$$
\mathcal G^a(u,v)
=
\sum_{\mathcal O}
\sum_{b,c}
\lambda_{12\mathcal O}^{(b)}
\lambda_{34\mathcal O}^{(c)}
G_{\mathcal O}^{a;bc}(u,v),
$$

where $a$ labels a four-point tensor structure and $b,c$ label three-point tensor structures.

Useful methods include:

| Method | Role |
|---|---|
| Embedding-space formalism | Makes conformal covariance manifest. |
| Differential operators | Generates spinning structures from scalar seed structures. |
| Weight-shifting operators | Moves systematically between representations. |
| Radial expansion | Computes spinning blocks as convergent series. |
| Coupled Casimir equations | Treats tensor structures as a vector-valued eigenvalue problem. |

For mixed-correlator bootstrap equations, these structures naturally assemble into matrices. Positivity becomes matrix positivity, not just positivity of a single number.

## Conserved operators and shortening

Higher-dimensional CFTs contain important conserved operators: global symmetry currents, stress tensors, and sometimes higher-spin currents. Conservation imposes shortening conditions. For a conserved symmetric traceless spin-$\ell$ current,

$$
\partial^{\mu_1}J_{\mu_1\cdots\mu_\ell}=0,
\qquad
\Delta=\ell+d-2.
$$

The stress tensor is the spin-two case with

$$
\Delta_T=d,
\qquad
\ell=2.
$$

When a block corresponds to a conserved exchanged operator, the generic long-multiplet block must be specialized carefully. Sometimes the block is obtained by taking a limit of a long block; sometimes one should impose conservation before choosing the tensor-structure basis. Sloppy limits can produce spurious null contributions.

## Bootstrap role

For identical scalar operators $\phi$ of dimension $\Delta_\phi$, crossing symmetry says

$$
v^{\Delta_\phi}\mathcal G(u,v)
=u^{\Delta_\phi}\mathcal G(v,u).
$$

With the block expansion, crossing becomes

$$
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0,
$$

where

$$
F_{\Delta,\ell}(u,v)
=
v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u).
$$

The identity block is separated, and unitarity imposes positivity on OPE-squared coefficients.

A numerical bootstrap calculation usually needs derivatives of $F_{\Delta,\ell}$ at the crossing-symmetric point. The block-computation pipeline is therefore

$$
(\Delta,\ell,d,\Delta_i)
\longrightarrow
G_{\Delta,\ell}(u,v)
\longrightarrow
\partial_z^m\partial_{\bar z}^nF_{\Delta,\ell}
\longrightarrow
\text{linear or semidefinite constraints}.
$$

That pipeline is why conformal blocks sit between abstract representation theory and concrete numerical bounds.

## Common pitfalls

**Importing holomorphic factorization from two dimensions.** In $d>2$, $z$ and $\bar z$ parametrize two real conformal invariants. They are not left- and right-moving chiral coordinates.

**Confusing blocks with OPE coefficients.** Blocks are kinematic functions fixed by symmetry. OPE coefficients are dynamical CFT data multiplying them.

**Ignoring normalization.** Different sources normalize the leading Gegenbauer factor differently. Always compare the OPE limit before comparing formulas.

**Forgetting representation labels.** For spinning external operators or non-scalar exchanged operators, $\ell$ is not enough. One must specify the full $SO(d)$ representation and tensor-structure labels.

**Treating conserved blocks as generic long blocks.** Conservation shortens multiplets. Limits must be taken carefully.

**Assuming numerical block generation is automatic.** Real computations require choices of derivative basis, truncation, rational approximation, precision, and spin cutoff or tail control.

## Relations to other pages

[Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) introduces the scalar external case. [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/) explains the tensor-structure generalization. [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) gives the eigenvalue definition. [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) explains convergence, and [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/) explains efficient computation.

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/) use these blocks as the kinematic input to bootstrap constraints. [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) explains how block derivatives become optimization constraints.

## Research status

The representation-theoretic definition of higher-dimensional conformal blocks is settled. The active work is computational and structural: spinning blocks, defect blocks, supersymmetric blocks, mixed-correlator systems, noninteger dimensions, Lorentzian limits, and high-precision implementations.

Current numerical bootstrap work depends heavily on robust block computation. Recent software and algorithmic developments have made much larger scalar, mixed-correlator, spinning, and noninteger-dimensional computations possible. The frontier is no longer “do conformal blocks exist?” It is “can we compute exactly the blocks we need, with enough precision, in the basis that makes the physics transparent?”

## Exercises

### Exercise 1: Casimir eigenvalue

Show that the quadratic conformal Casimir eigenvalue for an exchanged symmetric traceless spin-$\ell$ primary is

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

<details><summary><strong>Solution</strong></summary>

A conformal primary is labeled by its dilatation eigenvalue $\Delta$ and its $SO(d)$ representation. For a symmetric traceless spin-$\ell$ representation, the rotation-group quadratic Casimir is

$$
C_2^{SO(d)}(\ell)=\ell(\ell+d-2).
$$

The conformal Casimir contributes the dilatation-dependent piece

$$
\Delta(\Delta-d).
$$

Adding the two terms gives

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This is the eigenvalue appearing in the pairwise Casimir equation for scalar blocks.

</details>

### Exercise 2: Why Gegenbauer polynomials appear

Explain why $C_\ell^{(\alpha)}(\eta)$ appears in the leading OPE behavior of a higher-dimensional scalar block.

<details><summary><strong>Solution</strong></summary>

In the radial conformal frame, the exchanged primary creates a spin-$\ell$ state on $S^{d-1}$. For scalar external operators, the leading angular dependence is the rotationally invariant contraction of a spin-$\ell$ symmetric traceless tensor with the two unit vectors defining the frame.

The corresponding zonal spherical harmonic on $S^{d-1}$ is a Gegenbauer polynomial with index

$$
\alpha=\frac{d-2}{2}.
$$

Therefore the leading angular factor is $C_\ell^{(\alpha)}(\eta)$, where $\eta$ is the cosine of the angle between the two directions.

</details>

### Exercise 3: Leading radial behavior

For an exchanged spin-$\ell$ symmetric traceless operator, what is the leading small-$r$ behavior of the scalar conformal block?

<details><summary><strong>Solution</strong></summary>

The leading behavior is

$$
G_{\Delta,\ell}(r,\eta)
\sim
r^\Delta C_\ell^{(\alpha)}(\eta),
\qquad
\alpha=\frac{d-2}{2}.
$$

The factor $r^\Delta$ is the radial-energy contribution of the primary state, while the Gegenbauer polynomial carries the angular dependence of a spin-$\ell$ symmetric traceless representation.

</details>

### Exercise 4: Positivity in the identical-scalar bootstrap

Why do the coefficients multiplying blocks in the identical-scalar four-point function have the form $\lambda_{\phi\phi\mathcal O}^2$?

<details><summary><strong>Solution</strong></summary>

For identical external operators, the same OPE coefficient appears on the left and right sides of the exchanged block:

$$
\lambda_{\phi\phi\mathcal O}\lambda_{\phi\phi\mathcal O}
=
\lambda_{\phi\phi\mathcal O}^2.
$$

With real operators and positive two-point normalization in a unitary CFT, these squared coefficients are nonnegative. Reflection positivity makes this coefficient nonnegative. This nonnegativity is the basic input that allows linear functionals to exclude spectra in numerical bootstrap.

</details>

## References

- F. A. Dolan and H. Osborn, “Conformal Four Point Functions and the Operator Product Expansion,” *Nuclear Physics B* **599** (2001).
- F. A. Dolan and H. Osborn, “Conformal Partial Waves and the Operator Product Expansion,” *Nuclear Physics B* **678** (2004).
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Correlators,” 2011.
- M. Hogervorst and S. Rychkov, “Radial Coordinates for Conformal Blocks,” 2013.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, 2017.
- D. Karateev, P. Kravchuk, and D. Simmons-Duffin, “Weight Shifting Operators and Conformal Blocks,” 2018.
- D. Poland, S. Rychkov, and A. Vichi, “The conformal bootstrap: theory, numerical techniques, and applications,” *Reviews of Modern Physics* **91** (2019) 015002.
- S. Rychkov and N. Su, “New developments in the numerical conformal bootstrap,” arXiv:2311.15844.

## Version history

- 2026-06-27: First polished draft for the Conformal Blocks chapter.
