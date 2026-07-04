---
title: "Casimir Equation"
description: "Derives conformal blocks as eigenfunctions of the quadratic conformal Casimir and explains the boundary condition that selects the physical block."
sidebar:
  label: "Casimir Equation"
  order: 3
level: Graduate
status: "Polished draft"
source: "Dolan–Osborn 2003; Hogervorst–Rychkov 2013; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - conformal Casimir
  - conformal blocks
  - scalar four-point functions
  - differential equations
  - shadow symmetry
  - OPE boundary conditions
canonicalTopics:
  - casimir-equation
  - conformal-blocks
  - quadratic-conformal-casimir
  - scalar-conformal-blocks
  - bootstrap-kinematics
researchStatus:
  established:
    - "Scalar conformal blocks are eigenfunctions of the quadratic conformal Casimir acting on the two operators fused in a chosen OPE channel."
    - "The Casimir eigenvalue is fixed by the exchanged primary dimension and spin, while the physical block is selected by the OPE-limit boundary condition."
  active:
    - "Casimir equations remain a practical tool for deriving recursion relations, computing derivatives, checking block implementations, and generalizing blocks to spin, defects, and supersymmetry."
---

## Summary

The **Casimir equation** characterizes conformal blocks as eigenfunctions of the quadratic conformal Casimir. In the $12\to34$ channel, the conformal generators acting on points $x_1$ and $x_2$ combine into

$$
\mathcal C_{12}
=
\frac12
(L_1+L_2)_{AB}(L_1+L_2)^{AB}.
$$

If the exchanged primary has dimension $\Delta$ and spin $\ell$, then its conformal multiplet has quadratic Casimir eigenvalue

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

The conformal partial wave obeys

$$
\mathcal C_{12}W_{\Delta,\ell}^{(12)(34)}
=
C_{\Delta,\ell}W_{\Delta,\ell}^{(12)(34)}.
$$

After stripping the usual scalar prefactor, this becomes a differential equation for the scalar block $G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z)$. The eigenvalue fixes the representation. The OPE boundary condition selects the physical block rather than the shadow solution.

## Prerequisites

You should know [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/), [Conformal Casimir](/cft-bootstrap/conformal-symmetry/conformal-casimir/), [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/), and [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/).

The page uses scalar external operators and symmetric traceless exchanged primaries. Spinning external operators lead to matrix-valued Casimir equations and are postponed to [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/).

## Core idea

The OPE fuses two external operators into a conformal multiplet. A conformal multiplet is an irreducible representation of the conformal algebra, so the quadratic Casimir acts on every state in the multiplet by the same number.

That is the whole idea behind the Casimir equation:

$$
\text{fuse }1,2
\quad\Longrightarrow\quad
\text{intermediate representation }(\Delta,\ell)
\quad\Longrightarrow\quad
\text{Casimir eigenvalue }C_{\Delta,\ell}.
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![The Casimir equation selects the conformal block with a given exchanged representation and OPE boundary condition.](/figures/cft-bootstrap/casimir-equation-block.svg)

<figcaption>

The pair Casimir $\mathcal C_{12}$ acts on the two operators fused in the $12\to34$ channel. Its eigenvalue identifies the exchanged representation. The OPE limit selects the physical block from the possible Casimir eigenfunctions.

</figcaption>
</figure>

The Casimir equation is therefore the conformal-block analogue of the angular-momentum equation in quantum mechanics. Symmetry gives the differential operator. Representation labels give the eigenvalue. Boundary behavior tells us which eigenfunction to use.

## Setup and conventions

Let the scalar four-point function be written as

$$
\begin{aligned}
&\langle
\mathcal O_1(x_1)\mathcal O_2(x_2)
\mathcal O_3(x_3)\mathcal O_4(x_4)
\rangle
\\
&=
\frac{
\left(\frac{x_{24}^2}{x_{14}^2}\right)^{\Delta_{12}/2}
\left(\frac{x_{14}^2}{x_{13}^2}\right)^{\Delta_{34}/2}
}{
(x_{12}^2)^{(\Delta_1+\Delta_2)/2}
(x_{34}^2)^{(\Delta_3+\Delta_4)/2}
}
\mathcal G(u,v),
\end{aligned}
$$

with

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The $12\to34$ block expansion is

$$
\mathcal G(u,v)
=
\sum_{\mathcal O}
\lambda_{12\mathcal O}\lambda_{34\mathcal O}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z).
$$

The differential equation below is written for the reduced block. It depends on the prefactor convention above. If a different prefactor is used, the Casimir operator in $z,\bar z$ is conjugated by the corresponding prefactor.

## The pair Casimir

Let $L_i^{AB}$ denote the conformal generator acting on the $i$th operator. In a Euclidean embedding-space notation, $A,B$ are indices of $SO(d+1,1)$. The quadratic Casimir acting on the pair $(1,2)$ is

$$
\mathcal C_{12}
=
\frac12
(L_1+L_2)_{AB}(L_1+L_2)^{AB}.
$$

The OPE says that the pair $\mathcal O_1\mathcal O_2$ decomposes into conformal multiplets. On the contribution of the multiplet generated by a primary $\mathcal O_{\Delta,\ell}$,

$$
\mathcal C_{12}
=
C_{\Delta,\ell}.
$$

For symmetric traceless spin $\ell$, the eigenvalue is

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

This is the same eigenvalue found from radial quantization: $\Delta$ labels the energy under dilatations, and $\ell$ labels the rotation representation on the sphere.

## Differential operator in cross-ratios

For scalar external operators, the pair Casimir reduces to a second-order differential operator in $z$ and $\bar z$. Define

$$
a=-\frac{\Delta_{12}}{2},
\qquad
b=\frac{\Delta_{34}}{2},
\qquad
\nu=\frac{d-2}{2}.
$$

Introduce the one-variable operator

$$
D_z^{a,b}
=
z^2(1-z)\partial_z^2
-(a+b+1)z^2\partial_z
-abz.
$$

Then a standard reduced Casimir operator is

$$
\mathfrak D_{a,b}
=
D_z^{a,b}+D_{\bar z}^{a,b}
+2\nu\frac{z\bar z}{z-\bar z}
\left[(1-z)\partial_z-(1-\bar z)\partial_{\bar z}\right].
$$

With this normalization, the scalar block satisfies

$$
\mathfrak D_{a,b}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z)
=
\frac12 C_{\Delta,\ell}
G_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z).
$$

The factor of $1/2$ is conventional. Some authors absorb it into the definition of the differential operator or the Casimir. The safe statement is always: the block is an eigenfunction of the pair Casimir with eigenvalue fixed by $(\Delta,\ell)$.

## Boundary condition and the shadow solution

The Casimir eigenvalue is invariant under

$$
\Delta\longrightarrow d-\Delta,
$$

because

$$
\Delta(\Delta-d)=(d-\Delta)((d-\Delta)-d).
$$

Therefore the differential equation cannot by itself distinguish a primary of dimension $\Delta$ from a shadow of dimension $d-\Delta$. It also cannot by itself decide which OPE channel is being used.

The physical scalar block is selected by its OPE-limit behavior:

$$
G_{\Delta,\ell}(r,\eta)
\sim
r^\Delta
\times
\text{spin-}\ell\text{ angular structure}
\qquad(r\to0).
$$

The shadow solution behaves instead like $r^{d-\Delta}$ in the same limit. In ordinary unitary CFT applications, the physical block is the solution whose leading power matches the exchanged operator dimension in the OPE.

This is why the Casimir equation is not just an eigenvalue problem. It is an eigenvalue problem **plus an OPE boundary condition**.

## Two-dimensional simplification

In two dimensions, $\nu=(d-2)/2=0$, so the mixed term in $\mathfrak D_{a,b}$ disappears:

$$
\mathfrak D_{a,b}=D_z^{a,b}+D_{\bar z}^{a,b}.
$$

The equation separates into holomorphic and antiholomorphic hypergeometric equations. This is the global reason behind the factorized two-dimensional scalar-block formula

$$
g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z)
=
\frac{1}{(-2)^\ell(1+\delta_{\ell0})}
\left[
 k_{\Delta+\ell}^{a,b}(z)k_{\Delta-\ell}^{a,b}(\bar z)
+
 k_{\Delta+\ell}^{a,b}(\bar z)k_{\Delta-\ell}^{a,b}(z)
\right],
$$

where

$$
k_\beta^{a,b}(x)
=
x^{\beta/2}
{}_2F_1\left(\frac{\beta}{2}+a,\frac{\beta}{2}+b;\beta;x\right).
$$

Again, these are **global** two-dimensional blocks, not Virasoro blocks.

## Four-dimensional check

In four dimensions, $\nu=1$, and the mixed term is present. A standard closed-form solution is

$$
g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(z,\bar z)
=
\frac{1}{(-2)^\ell}
\frac{z\bar z}{z-\bar z}
\left[
 k_{\Delta+\ell}^{a,b}(z)k_{\Delta-\ell-2}^{a,b}(\bar z)
-
 k_{\Delta+\ell}^{a,b}(\bar z)k_{\Delta-\ell-2}^{a,b}(z)
\right].
$$

This expression is a useful check on the differential equation. It also illustrates why closed-form blocks become less elementary outside special dimensions: the coupling between $z$ and $\bar z$ encodes angular momentum on $S^{d-1}$.

## Relation to radial quantization

The Casimir equation and radial expansion are two views of the same representation theory.

In radial quantization, a block is a sum over descendants:

$$
G_{\Delta,\ell}(r,\eta)
=
\sum_{n=0}^{\infty}r^{\Delta+n}
\sum_j B_{n,j}C_j^{(\nu)}(\eta).
$$

The Casimir equation imposes relations among the coefficients $B_{n,j}$. In practice, this gives recursion relations. The leading term is supplied by the primary; the differential equation propagates that information through the descendant tower.

This is why one can compute blocks without writing every descendant explicitly. The Casimir equation already knows the representation.

## How the equation is used

The Casimir equation is useful in several ways.

First, it derives closed forms in special dimensions. The two-dimensional and four-dimensional formulas above are classic examples.

Second, it computes derivatives away from special loci. In numerical bootstrap calculations, derivatives of blocks at symmetric points such as $z=\bar z=1/2$ are central inputs.

Third, it provides a check on block implementations. A block generator that fails the Casimir equation is not computing conformal blocks in the stated convention.

Fourth, it generalizes. Spinning blocks, defect blocks, boundary blocks, and supersymmetric blocks often satisfy Casimir-type equations, although the resulting systems can be matrix-valued and technically much richer.

## Common pitfalls

**Forgetting the OPE boundary condition.** The Casimir equation has multiple solutions. The physical block is selected by the $r^\Delta$ OPE limit.

**Losing the factor of one half.** Some authors write $\mathfrak D G=C_{\Delta,\ell}G$, while others write $\mathfrak D G=\frac12 C_{\Delta,\ell}G$. Check the definition of $\mathfrak D$.

**Confusing pair Casimirs.** $\mathcal C_{12}$ gives blocks in the $12\to34$ channel. A different OPE channel uses a different pair Casimir.

**Forgetting external dimension differences.** The parameters $a$ and $b$ are not decorative. They encode the dimension differences of the external scalar pairs.

**Mistaking the shadow solution for the block.** The equality of Casimir eigenvalues under $\Delta\to d-\Delta$ is useful, but it is also a source of normalization and analytic-continuation traps.

**Applying scalar equations to spinning correlators.** Spinning correlators have multiple tensor structures, so the Casimir equation becomes a coupled system.

## Relations to other pages

- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) defines the objects whose differential equation is derived here.
- [Conformal Casimir](/cft-bootstrap/conformal-symmetry/conformal-casimir/) explains the group-theoretic origin of the eigenvalue $C_{\Delta,\ell}$.
- [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) develops the convergent expansion that supplies practical boundary data.
- [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/) uses the Casimir equation and analytic structure to compute blocks efficiently.
- [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/) generalizes the scalar equation to tensor-valued block systems.
- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) uses Casimir eigenfunctions as the building blocks of bootstrap equations.

## Research status

The scalar Casimir equation is established textbook technology. It remains important because modern bootstrap work is computationally unforgiving: wrong factors, wrong external-dimension parameters, or a mismatched block normalization can silently spoil a calculation.

Current research uses Casimir ideas in more elaborate settings: spinning correlators, supersymmetric multiplets, defect and boundary CFTs, Lorentzian inversion, and efficient numerical block generation. The idea is stable; the implementation frontier keeps moving.

## Exercises

### Exercise 1: Shadow invariance of the eigenvalue

Show that

$$
C_{\Delta,\ell}=C_{d-\Delta,\ell}.
$$

Explain why this means the Casimir equation alone does not select the physical block.

<details>
<summary><strong>Solution</strong></summary>

The spin-dependent term is unchanged. For the dimension-dependent term,

$$
(d-\Delta)((d-\Delta)-d)
=
(d-\Delta)(-\Delta)
=
\Delta(\Delta-d).
$$

Thus $C_{d-\Delta,\ell}=C_{\Delta,\ell}$. The same differential equation has solutions associated with $\Delta$ and with the shadow dimension $d-\Delta$. The physical block is chosen by the OPE boundary condition $G\sim r^\Delta$, not merely by the eigenvalue.

</details>

### Exercise 2: Identity block and the Casimir equation

For identical scalar external operators, show that the identity block $G_{0,0}(u,v)=1$ solves the reduced Casimir equation.

<details>
<summary><strong>Solution</strong></summary>

For the identity, $\Delta=0$ and $\ell=0$, so

$$
C_{0,0}=0.
$$

For identical external scalars, $a=b=0$. The differential operator $\mathfrak D_{0,0}$ contains only derivatives when acting on a constant; the term $-abz$ also vanishes. Therefore

$$
\mathfrak D_{0,0}(1)=0=\frac12 C_{0,0}(1).
$$

So the identity block solves the equation.

</details>

### Exercise 3: Which channel is being diagonalized?

Why does $\mathcal C_{12}$ produce the $12\to34$ block expansion rather than the $13\to24$ expansion?

<details>
<summary><strong>Solution</strong></summary>

The operator $\mathcal C_{12}$ is built from generators acting on the first two insertions. It diagonalizes the representation produced when $\mathcal O_1$ and $\mathcal O_2$ are fused by the OPE. That is exactly the intermediate representation in the $12\to34$ channel.

For the $13\to24$ channel, one would instead use

$$
\mathcal C_{13}
=
\frac12(L_1+L_3)_{AB}(L_1+L_3)^{AB}.
$$

The same four-point function can be expanded in different channels, but each channel diagonalizes a different pair Casimir.

</details>

## References

- F. A. Dolan and H. Osborn, “Conformal Four Point Functions and the Operator Product Expansion,” *Nuclear Physics B* **599** (2001). Classic derivation and closed-form block formulas.
- F. A. Dolan and H. Osborn, “Conformal Partial Waves and the Operator Product Expansion,” *Nuclear Physics B* **678** (2004). Standard Casimir-equation treatment of higher-dimensional conformal blocks.
- M. Hogervorst and S. Rychkov, “Radial Coordinates for Conformal Blocks,” *Physical Review D* **87** (2013). Radial expansion and convergence-oriented block technology.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Pedagogical account of conformal blocks and the Casimir equation.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Clear derivation of Casimir equations and bootstrap setup.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Review of conformal-block technology and numerical applications.

## Version history

- **2026-06-27:** Added Casimir-equation page with pair-Casimir derivation, scalar differential operator, boundary conditions, shadow caveats, examples, and exercises.
