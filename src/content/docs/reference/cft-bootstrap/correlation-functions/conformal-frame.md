---
title: "Conformal Frame"
description: "Explains how conformal symmetry fixes representative point configurations, especially the four-point frame with coordinates z and z-bar."
sidebar:
  label: "Conformal Frame"
  order: 5
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Costa et al. 2011; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - conformal frames
  - correlation functions
  - cross ratios
  - tensor structures
canonicalTopics:
  - conformal-frame
  - four-point-kinematics
  - conformal-cross-ratios
  - tensor-structures
researchStatus:
  established:
    - "A conformal frame is a convenient representative of a point configuration modulo the global conformal group; for four scalar insertions it leaves exactly the variables z and z-bar."
    - "For spinning correlators, conformal frames reduce position dependence but leave residual stabilizer data that organizes tensor structures."
  active:
    - "Conformal-frame methods remain important in spinning correlator bootstrap, Lorentzian kinematics, celestial CFT, defect CFT, and higher-point bootstrap problems."
---

## Summary

A conformal frame is a choice of representative for a configuration of points after using conformal symmetry. It is not a gauge choice in the theory. It is a coordinate choice on the space of insertion configurations.

For four generic points in Euclidean $\mathbb R^d$, $d\geq 2$, a standard frame is

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=\frac{z+\bar z}{2}e_1+\frac{z-\bar z}{2i}e_2.
$$

Then the two conformal cross ratios are

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The point of the frame is that conformal covariance has already done the bookkeeping; the remaining variables are the true invariant shape data.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Four generic points mapped to a conformal frame](/figures/cft-bootstrap/four-point-conformal-frame.svg)

<figcaption>

A global conformal transformation can send three generic points to $0$, $1$, and $\infty$. The fourth point remains at $z$ in a two-plane, so the surviving scalar data are $z,\bar z$, or equivalently $u=z\bar z$ and $v=(1-z)(1-\bar z)$.

</figcaption>
</figure>

The frame is most familiar for scalar four-point functions, but the idea is broader. It is also one of the cleanest ways to count tensor structures: after fixing the points, the residual rotations that preserve the frame must still act consistently on spin indices.

## Prerequisites

You should know [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/), [Finite Conformal Transformations](/cft-bootstrap/conformal-symmetry/finite-conformal-transformations/), [Cross Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), and the scalar correlator formulas in [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), and [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/).

This page works in flat Euclidean space unless stated otherwise. Lorentzian conformal frames require additional care with causal ordering and analytic continuation.

## Core idea

Correlation functions are covariant under conformal transformations. With the convention that the metric rescales locally as

$$
ds'^2=\Omega(x)^2 ds^2,
$$

a scalar primary obeys

$$
\mathcal O_i'(x_i')=\Omega(x_i)^{-\Delta_i}\mathcal O_i(x_i).
$$

Equivalently, a correlator at one configuration of points determines the correlator at any conformally equivalent configuration, up to known powers of the local scale factors. The art is to choose a representative that makes the remaining invariant data obvious.

For two scalar points, there is no nontrivial shape. For three scalar points, there is still no nontrivial shape. For four scalar points, one complex coordinate $z$ survives. In bootstrap language, the first genuinely dynamical scalar correlator is a function on the four-point conformal frame.

Conformal frames are especially useful because they separate three different jobs:

| Job | What the frame handles |
|---|---|
| Kinematics | Removes redundant position variables using conformal transformations. |
| Dynamics | Leaves scalar functions of invariant variables such as $z,\bar z$. |
| Representation theory | Reveals the residual rotations that organize spinning tensor structures. |

## Setup and conventions

The connected Euclidean conformal group in $d\geq 3$ is locally $SO(d+1,1)$. In $d=2$, the global conformal group factorizes into holomorphic and antiholomorphic Möbius transformations after complexification.

We use Euclidean dot products and write

$$
x_{ij}^2=(x_i-x_j)^2.
$$

A point at infinity is defined through a primary-operator limit. For a scalar primary of dimension $\Delta$,

$$
\mathcal O(\infty)
\equiv
\lim_{L\to\infty} L^{2\Delta}\mathcal O(L n),
$$

where $n$ is a fixed unit vector. In rotationally invariant scalar formulas, the result is independent of $n$.

For spinning operators, the definition of an operator at infinity includes a corresponding rotation or inversion action on indices. This is one reason spinning correlators are better treated with an explicit representation-theory formalism.

## Two and three points

A two-point configuration can be put in the frame

$$
x_1=0,
\qquad
x_2=\infty,
$$

or, if one wants finite points,

$$
x_1=0,
\qquad
x_2=e_1.
$$

There is no conformal invariant cross ratio. The two-point function is fixed up to normalization and representation-theoretic selection rules.

A three-point configuration can be put in the frame

$$
x_1=0,
\qquad
x_2=e_1,
\qquad
x_3=\infty.
$$

Again, there is no scalar shape variable. The remaining data in a scalar three-point function are constants: the OPE coefficients. For spinning operators, there can be multiple tensor structures even though there are no scalar cross ratios.

This is why scalar three-point functions are fixed but scalar four-point functions are not.

## The standard four-point frame

For four generic points, choose

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=z_1e_1+z_2e_2.
$$

Equivalently,

$$
z=z_1+iz_2,
\qquad
\bar z=z_1-iz_2,
$$

so that

$$
x_2=\frac{z+\bar z}{2}e_1+\frac{z-\bar z}{2i}e_2.
$$

In this frame,

$$
x_{12}^2=z\bar z,
\qquad
x_{23}^2=(1-z)(1-\bar z),
\qquad
x_{13}^2=1.
$$

Since $x_4=\infty$, ratios involving $x_{i4}^2$ are understood by the limiting definition of the operator at infinity. The cross ratios become

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}=z\bar z,
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}=(1-z)(1-\bar z).
$$

This is the cleanest way to remember the definitions of $u$ and $v$.

## How to reach the frame

One constructive route is the following. Assume the four points are generic and start by translating $x_1$ to the origin.

A special conformal transformation in the convention

$$
x'^\mu=
\frac{x^\mu+b^\mu x^2}{1+2b\cdot x+b^2x^2}
$$

keeps the origin fixed. Choosing

$$
b^\mu=-\frac{x_4^\mu}{x_4^2}
$$

makes the denominator vanish at $x=x_4$, so $x_4$ is sent to infinity. After that, the transformations that keep $0$ and $\infty$ fixed are rotations and dilatations. Use a rotation and a scale to send the image of $x_3$ to $e_1$. Finally, use the rotations that preserve $e_1$ to place the image of $x_2$ in the $(e_1,e_2)$ plane.

The construction is not unique. Different choices are related by residual symmetries and by permutations of the four points. That is why the same four-point configuration can be described by $z$, $1-z$, $1/z$, and the other anharmonic images discussed in [Cross Ratios](/cft-bootstrap/correlation-functions/cross-ratios/).

## What happens to the correlator

For identical scalar primaries of dimension $\Delta$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2)^\Delta(x_{34}^2)^\Delta}.
$$

In the frame $x_1=0$, $x_2=z$, $x_3=1$, $x_4=\infty$, this becomes

$$
\langle \phi(0)\phi(z,\bar z)\phi(1)\phi(\infty)\rangle
=
\frac{\mathcal G(z\bar z,(1-z)(1-\bar z))}{(z\bar z)^\Delta}.
$$

Equivalently,

$$
\mathcal G(z\bar z,(1-z)(1-\bar z))
=(z\bar z)^\Delta
\langle \phi(0)\phi(z,\bar z)\phi(1)\phi(\infty)\rangle.
$$

This equation is a useful mental model: the reduced four-point function is just the frame correlator with the known external power restored.

For nonidentical scalars, one chooses a different external prefactor. The frame still leaves scalar functions of $u$ and $v$. The only change is the conventional placement of powers of $x_{ij}^2$.

## Residual symmetries

A frame usually has a stabilizer: transformations that preserve the chosen point positions. The stabilizer may act nontrivially on spin indices even when it leaves the scalar position variables unchanged.

For the four-point frame in $d>2$, the points lie in a two-plane. Rotations in the transverse directions form a residual $SO(d-2)$ group. Scalar operators are singlets under this residual group, so scalar four-point functions do not notice it. Spinning operators do.

This gives a practical rule:

$$
\text{tensor structures}
=
\text{residual-stabilizer invariants built from polarizations and spins}.
$$

That sentence is a little dry, but it prevents a common mistake. A conformal frame does not magically turn spinning correlators into scalar correlators. It turns the position dependence into simple coordinates and leaves a finite representation-theory problem.

## Frames and tensor structures

A spinning four-point function can be written schematically as

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_a \mathcal T_a(x_i,\epsilon_i)\,\mathcal G_a(u,v),
$$

where $\epsilon_i$ denotes polarization data. In a conformal frame, this becomes a set of functions $\mathcal G_a(z,\bar z)$ multiplying residual-invariant tensor structures.

There are two complementary approaches:

| Approach | What it emphasizes |
|---|---|
| Embedding-space or index-free formalism | Keeps conformal covariance manifest in arbitrary coordinates. |
| Conformal frame | Makes the independent variables and residual little group transparent. |

Both are useful. Embedding space is often better for deriving covariant formulas. Conformal frames are often better for counting structures, setting up bootstrap equations, and checking whether a formula has too many or too few tensor structures.

## Two-dimensional frames

In two-dimensional Euclidean CFT, use complex coordinates $z,\bar z$ on the plane. The global conformal group acts by Möbius transformations,

$$
z\mapsto \frac{az+b}{cz+d},
\qquad
ad-bc\neq 0,
$$

and similarly for $\bar z$ in the antiholomorphic sector.

For four holomorphic coordinates, the cross ratio can be written directly as

$$
z=\frac{z_{12}z_{34}}{z_{13}z_{24}},
$$

after choosing a labeling convention compatible with $u=z\bar z$. The global conformal group sends three insertion points to $0$, $1$, and $\infty$; the fourth coordinate is the cross ratio.

The infinite-dimensional local conformal symmetry of two-dimensional CFT does not mean that four arbitrary insertions have no invariant data. Ordinary local conformal maps are not all globally single-valued maps of the punctured sphere preserving the operator insertions as a simple point configuration. For the global four-point problem, the cross ratio remains.

## Lorentzian frames

Lorentzian CFT uses the same algebraic group after analytic continuation, but conformal frames are more delicate. Timelike, spacelike, and null separations are not interchangeable under real Lorentzian conformal transformations. Operator ordering also matters.

The safe workflow is:

1. Start with a Euclidean frame and a Euclidean correlator when possible.
2. Continue $z,\bar z$ with a specified $i\epsilon$ prescription.
3. Track branch cuts and singularities rather than assuming $\bar z=z^*$.

Many Lorentzian regimes are naturally described by independent real variables $z$ and $\bar z$. The lightcone limit, Regge limit, and chaos limit all exploit this extra analytic structure.

## Common pitfalls

Do not think of a conformal frame as changing the theory. It changes coordinates on the configuration space of insertions.

Do not forget the operator at infinity. The limit includes the power $L^{2\Delta}$ for a scalar primary. Without it, the frame correlator would vanish.

Do not over-fix spinning correlators. After the points are fixed, residual rotations still act on polarization data.

Do not use the Euclidean relation $\bar z=z^*$ in Lorentzian arguments unless the analytic continuation justifies it.

Do not compare reduced correlators from different sources without checking the external prefactor convention.

## Relations to other pages

[Cross Ratios](/cft-bootstrap/correlation-functions/cross-ratios/) derives $u,v,z,\bar z$ and their crossing transformations.

[Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) uses the four-point frame to explain the first appearance of a dynamical scalar function.

[Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) develops the tensor-structure side of the conformal-frame story.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) expands frame functions in OPE channels.

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) turns the permutation ambiguity of conformal frames into equations for CFT data.

## Research status

Conformal frames are standard conformal kinematics. They are a reliable way to derive and check scalar correlation-function formulas in any dimension and to organize spinning tensor structures.

Active uses include high-spin and mixed-correlator bootstrap systems, efficient numerical implementations, Lorentzian analytic continuations, celestial conformal frames, defect frames, and higher-point kinematics.

## Exercises

### Exercise 1: The point at infinity

Let $\phi$ be a scalar primary of dimension $\Delta$. Starting from

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{(x^2)^\Delta},
$$

show that the definition

$$
\phi(\infty)=\lim_{L\to\infty} L^{2\Delta}\phi(Ln)
$$

gives

$$
\langle \phi(\infty)\phi(0)\rangle=1.
$$

<details><summary><strong>Solution</strong></summary>

Insert the definition:

$$
\langle \phi(\infty)\phi(0)\rangle
=
\lim_{L\to\infty} L^{2\Delta}
\langle \phi(Ln)\phi(0)\rangle.
$$

Since $n^2=1$,

$$
\langle \phi(Ln)\phi(0)\rangle
=\frac{1}{(L^2)^\Delta}=L^{-2\Delta}.
$$

The factors cancel, giving $1$.

</details>

### Exercise 2: Cross ratios in the frame

Use the frame

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=\frac{z+\bar z}{2}e_1+\frac{z-\bar z}{2i}e_2
$$

to show that $u=z\bar z$ and $v=(1-z)(1-\bar z)$.

<details><summary><strong>Solution</strong></summary>

In the finite part of the frame,

$$
x_{12}^2=x_2^2=z\bar z,
\qquad
x_{13}^2=1,
\qquad
x_{23}^2=(x_2-e_1)^2=(1-z)(1-\bar z).
$$

Since $x_4$ is at infinity, the ratios $x_{34}^2/x_{24}^2$ and $x_{14}^2/x_{24}^2$ both approach $1$ in the limiting definition. Therefore

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}=z\bar z,
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}=(1-z)(1-\bar z).
$$

</details>

### Exercise 3: Residual rotations

In $d>2$, show that the four-point frame leaves an $SO(d-2)$ rotation group unbroken.

<details><summary><strong>Solution</strong></summary>

The frame places all four points in the plane spanned by $e_1$ and $e_2$, with $0$, $e_1$, and $\infty$ fixed. A rotation acting only on the orthogonal subspace spanned by $e_3,\ldots,e_d$ leaves every point in the frame unchanged. These rotations form $SO(d-2)$. Scalar operators are invariant under this group, but spinning operators can transform nontrivially under it.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters 4–6.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning conformal correlators,” *Journal of High Energy Physics* **2011**.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D at least 3 Dimensions*, sections on conformal kinematics.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, sections on conformal transformations, correlation functions, and conformal blocks.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” section III.

## Version history

- 2026-06-27: First polished draft. Introduced scalar conformal frames, the four-point $z,\bar z$ frame, operators at infinity, residual stabilizers, spinning-operator caveats, and Lorentzian caveats.
