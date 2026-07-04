---
title: "OPE Basics"
description: "Defines the operator product expansion in CFT, derives the scalar primary form, and explains how OPE coefficients organize CFT data."
sidebar:
  label: "OPE Basics"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wilson 1969; Kadanoff 1969; Polyakov 1974; Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - operator product expansion
  - OPE coefficients
  - primary operators
  - descendants
  - radial quantization
  - CFT data
canonicalTopics:
  - ope-basics
  - operator-product-expansion
  - conformal-data
  - radial-quantization
researchStatus:
  established:
    - "The Euclidean OPE of local operators is a standard part of CFT and is convergent inside correlation functions in unitary theories with a normalizable radial-quantization Hilbert space."
    - "For primary exchanges, conformal symmetry fixes descendant contributions once the exchanged primary, its spin, and the relevant three-point coefficient are specified."
  active:
    - "Sharper Lorentzian convergence statements, lightcone limits, spinning and defect OPE technology, and numerical exploitation of large operator bases remain active areas."
---

## Summary

The **operator product expansion** says that a pair of nearby local operators can be replaced, inside correlation functions, by a sum of local operators at one point. In a CFT the schematic statement is

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_{\mathcal O_k}
\lambda_{ijk}\,C_k(x,\partial)\,\mathcal O_k(0),
$$

where $\mathcal O_k$ runs over primary operators, $C_k(x,\partial)$ packages the spacetime dependence and descendants in the conformal multiplet of $\mathcal O_k$, and $\lambda_{ijk}$ is the three-point coefficient in the chosen normalization.

For scalar primaries, the leading part of the contribution of a scalar primary $\mathcal O_k$ has the form

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}\,|x|^{\Delta_k-\Delta_i-\Delta_j}
\left[
\mathcal O_k(0)
+\frac{\Delta_i-\Delta_j+\Delta_k}{2\Delta_k}
 x^\mu\partial_\mu\mathcal O_k(0)
+\cdots
\right].
$$

The ellipsis is not arbitrary. It is fixed by conformal symmetry once the exchanged primary is known. That is why the OPE is the entry point to conformal blocks: a conformal block is the contribution of one entire conformal multiplet to a four-point function.

The OPE is also the most compact way to state what a CFT is made of. A CFT is not primarily a Lagrangian. It is a spectrum of local operators, their spins and symmetry representations, and the OPE coefficients that tell us how operators multiply.

## Prerequisites

You should know the [Conventions and Notation](/cft-bootstrap/conventions/) for this volume, especially the Euclidean two-point normalization conventions. You should also know [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), and the scalar two- and three-point formulas from [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/) and [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/).

The page uses Euclidean CFT notation unless explicitly stated otherwise. Lorentzian caveats are mentioned, but the main convergence picture is Euclidean radial quantization.

## Core idea

Put several local operators in a Euclidean correlator. Suppose two insertions are close to each other compared with their distance to every other insertion. The local physics inside a sphere around the pair can be summarized by the states that the pair creates on the surrounding sphere. By the state–operator correspondence, those states are created by local operators at the center.

That is the OPE in one sentence:

$$
\text{nearby insertions inside a sphere}
\quad\longrightarrow\quad
\text{sum over local operators at the center}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![The OPE replaces nearby insertions by a sum over local operators.](/figures/cft-bootstrap/ope-local-replacement.svg)

<figcaption>

The Euclidean OPE replaces a cluster of insertions inside a sphere by a sum over local operators at the center. The convergence radius is set by the nearest other insertion, so the useful condition is $|x|<R$ inside the correlator.

</figcaption>
</figure>

This is why radial quantization is the natural language. The two nearby operators create a state on a sphere. Expanding that state in an energy eigenbasis on the cylinder is the same as expanding it in local operators of definite scaling dimension.

## Setup and conventions

We use Euclidean distance

$$
x_{ij}^2=|x_i-x_j|^2,
$$

and scalar primary two-point functions normalized as

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{g_{ij}}{|x|^{2\Delta_i}}
\qquad
\text{when }\Delta_i=\Delta_j.
$$

In an orthonormal scalar basis, $g_{ij}=\delta_{ij}$ for real operators. In a charged basis, it is often more natural to pair an operator with its conjugate,

$$
\langle \mathcal O_a(x)\mathcal O_b^\dagger(0)\rangle
=\frac{\delta_{ab}}{|x|^{2\Delta_a}}.
$$

For scalar primaries, the three-point function is written

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{|x_{12}|^{\Delta_i+\Delta_j-\Delta_k}
 |x_{23}|^{\Delta_j+\Delta_k-\Delta_i}
 |x_{13}|^{\Delta_i+\Delta_k-\Delta_j}}.
$$

With these conventions, the same number $\lambda_{ijk}$ appears as the leading primary coefficient in the scalar OPE. If the two-point metric is not orthonormal, indices must be raised with $g^{ij}$, and the coefficient appearing in $\mathcal O_i\times\mathcal O_j$ is $\lambda_{ij\ell}g^{\ell k}$.

## OPE as a statement inside correlators

The safest definition of the OPE is not an isolated algebraic equation. It is a statement inside correlation functions. Let $X$ denote a product of other local operators, all outside a sphere containing $0$ and $x$. Then

$$
\langle \mathcal O_i(x)\mathcal O_j(0)X\rangle
=
\sum_{\mathcal O_k}
\lambda_{ijk}\,
C_k(x,\partial_y)
\langle \mathcal O_k(y)X\rangle\big|_{y=0}.
$$

Here $C_k(x,\partial_y)$ is a differential operator that generates the descendants of $\mathcal O_k$. The expansion is organized by increasing scaling dimension. In radial quantization, the small parameter is roughly

$$
\frac{|x|}{R},
$$

where $R$ is the distance from the origin to the nearest other insertion. Low-dimension operators dominate the short-distance limit; high-dimension operators are suppressed by powers of $|x|/R$.

This is the operational meaning of the OPE. It tells you how to compute correlators in a region of configuration space where two points are close. If you know the spectrum and OPE coefficients, repeated use of the OPE reduces higher-point functions to sums over lower-point matrix elements.

## Scalar primary contribution

Consider the OPE of two scalar primaries and ask for the contribution of a scalar primary $\mathcal O_k$. Dimensional analysis gives the leading power:

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
A_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0).
$$

To determine $A_{ijk}$, insert another scalar primary $\mathcal O_k(y)$ and compare with the three-point function in the limit $|x|\ll |y|$. With orthonormal two-point functions,

$$
\langle \mathcal O_k(0)\mathcal O_k(y)\rangle=\frac{1}{|y|^{2\Delta_k}},
$$

so the leading OPE prediction is

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal O_k(y)\rangle
\sim
A_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}\frac{1}{|y|^{2\Delta_k}}.
$$

The exact three-point function gives the same limit with $A_{ijk}=\lambda_{ijk}$. Therefore

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0).
$$

The first descendant coefficient is fixed by expanding the same three-point function one order further. One finds

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}
\left[
\mathcal O_k(0)
+\frac{\Delta_i-\Delta_j+\Delta_k}{2\Delta_k}
 x^\mu\partial_\mu\mathcal O_k(0)
+\cdots
\right].
$$

The coefficient is asymmetric in $i$ and $j$ because we expanded around the point occupied by $\mathcal O_j(0)$. If we instead expanded around $x$, the corresponding descendant terms would be reorganized.

## Primary families and descendants

A primary does not appear alone. It appears with all of its descendants:

$$
\mathcal O_k,
\qquad
\partial_\mu\mathcal O_k,
\qquad
\partial_\mu\partial_\nu\mathcal O_k,
\qquad
\ldots
$$

or, in radial quantization,

$$
|\mathcal O_k\rangle,
\qquad
P_\mu|\mathcal O_k\rangle,
\qquad
P_\mu P_\nu|\mathcal O_k\rangle,
\qquad
\ldots.
$$

The primary labels the conformal multiplet. The descendants are required by translation invariance and constrained by the full conformal algebra. This is why conformal symmetry is so powerful: the OPE does not need an independent coefficient for every descendant. The independent dynamical data are the primary spectrum and the primary three-point coefficients.

For spinning operators, the same idea holds, but the formula has tensor structures. One should read

$$
\mathcal O_i\times\mathcal O_j
=\sum_{\mathcal O_k}\lambda_{ijk}^{(a)}
\left[\text{tensor structure }a\right]
\left[\mathcal O_k+\text{descendants}\right],
$$

where $a$ labels independent structures allowed by rotations, parity, and internal symmetries. Conservation equations can remove or relate some structures.

## The identity contribution

The identity operator $\mathbf 1$ has dimension zero and no descendants. Its contribution is fixed by the two-point function:

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{g_{ij}\mathbf 1}{|x|^{\Delta_i+\Delta_j}}
\qquad
\text{when }\Delta_i=\Delta_j.
$$

In an orthonormal basis of identical real scalar primaries,

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{\delta_{ij}\mathbf 1}{|x|^{2\Delta_i}}.
$$

This term is simple but crucial. In a four-point function, the identity channel gives the leading disconnected behavior in an OPE limit. For example, if $\mathcal O$ is unit-normalized,

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
\sim
\frac{1}{|x_{12}|^{2\Delta}|x_{34}|^{2\Delta}}
$$

when $x_1\to x_2$ and $x_3\to x_4$, up to contributions from nontrivial operators.

## Simple example: free scalar theory

Let $\phi$ be a canonically normalized free scalar primary in $d>2$, rescaled so that

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{d-2}}.
$$

Then $\Delta_\phi=(d-2)/2$. Wick's theorem gives

$$
\phi(x)\phi(0)
=
\frac{\mathbf 1}{|x|^{d-2}}
+ :\!\phi(x)\phi(0)\!:
$$

inside correlators. Taylor expand the normal-ordered part around the origin:

$$
:\!\phi(x)\phi(0)\!:
=
:\!\phi^2\!:(0)
+x^\mu:\!\partial_\mu\phi\,\phi\!:(0)
+\frac12x^\mu x^\nu:\!\partial_\mu\partial_\nu\phi\,\phi\!:(0)
+\cdots.
$$

This illustrates the two most basic OPE features. The identity term comes from the contraction. The remaining terms are local composite operators and their descendants. In an interacting CFT, the same structure survives, but the list of operators and coefficients is not usually generated by elementary Wick contractions.

## Two-dimensional singular OPE notation

In two-dimensional CFT, one often writes only the singular part of an OPE. For a holomorphic stress tensor $T(z)$ and a primary field $\phi(w,\bar w)$ of holomorphic weight $h$,

$$
T(z)\phi(w,\bar w)
\sim
\frac{h\,\phi(w,\bar w)}{(z-w)^2}
+
\frac{\partial_w\phi(w,\bar w)}{z-w}.
$$

Here $\sim$ means “has the following singular terms as $z\to w$.” It does not display the regular terms. This is a useful convention in 2D because contour integrals of $T(z)$ only see the singular part.

In higher-dimensional bootstrap work, by contrast, the OPE is usually used as a full expansion inside correlators. The two languages are compatible, but one must keep track of what the symbol $\sim$ is hiding.

## OPE and four-point functions

The OPE becomes powerful when inserted into a four-point function. For identical scalar primaries,

$$
\langle \mathcal O(x_1)\mathcal O(x_2)\mathcal O(x_3)\mathcal O(x_4)\rangle
=
\frac{g(u,v)}{|x_{12}|^{2\Delta}|x_{34}|^{2\Delta}},
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Applying the OPE in the $12\to34$ channel gives

$$
g(u,v)=\sum_{\mathcal O_k}\lambda_{\mathcal O\mathcal O k}^2\,G_{\Delta_k,\ell_k}(u,v),
$$

where $G_{\Delta,\ell}(u,v)$ is the conformal block for the exchanged primary of dimension $\Delta$ and spin $\ell$. In a unitary theory with identical real scalars, the squared coefficients are nonnegative in an appropriate normalization:

$$
\lambda_{\mathcal O\mathcal O k}^2\ge 0.
$$

This positivity is one of the engines of the numerical bootstrap. Crossing symmetry says that expanding in another OPE channel gives the same four-point function. The OPE supplies the terms; crossing supplies the consistency condition.

## Euclidean convergence and Lorentzian caveats

In Euclidean radial quantization, the OPE is a Hilbert-space expansion. If a sphere around the fused operators contains no other insertions, the state on the sphere can be expanded in energy eigenstates on the cylinder. Since the cylinder Hamiltonian is the dilatation generator, this is an expansion in scaling dimensions.

The result is a convergent expansion in the Euclidean domain where the fused operators are closer to each other than to any other insertion. This convergence is one reason CFT bootstrap equations are mathematically sharper than ordinary perturbative expansions.

Lorentzian physics is subtler. Operators can become timelike or lightlike separated, ordering matters, and analytic continuation can cross branch cuts. The lightcone OPE is still one of the most important tools in analytic bootstrap, but it is not the same as casually setting $x^2\to0$ in a Euclidean formula. The Lorentzian continuation must remember the operator ordering and $i\epsilon$ prescription.

## The OPE as CFT data

A local CFT is often described by its **CFT data**:

$$
\left\{\Delta_i,\ \rho_i,\ \lambda_{ijk}^{(a)}\right\}.
$$

Here $\Delta_i$ are scaling dimensions, $\rho_i$ are spin and internal-symmetry representations, and $\lambda_{ijk}^{(a)}$ are OPE coefficients for all allowed tensor structures. This data is not arbitrary. It must satisfy:

| Constraint | What it demands |
|---|---|
| Conformal symmetry | Correlators and OPE structures transform correctly. |
| Unitarity or reflection positivity | Norms are positive and certain OPE coefficients enter four-point functions with positive signs. |
| Locality | Correlators are single-valued or have controlled spin-statistics monodromy. |
| Associativity | Different OPE orders give the same correlators. |
| Global symmetries | Selection rules and tensor structures match representation theory. |

The conformal bootstrap is the program of solving or constraining this data. The OPE is the multiplication table whose associativity the bootstrap tests.

## Common pitfalls

**Treating the OPE as only a singular expansion.** In two-dimensional holomorphic computations, the singular terms are often all one needs for contour manipulations. In higher-dimensional CFT and bootstrap, the full conformal-family expansion is usually the object of interest.

**Ignoring the two-point metric.** The coefficient with all lower indices, $\lambda_{ijk}$, is a three-point coefficient. The coefficient multiplying $\mathcal O_k$ in an OPE may require raising an index with the two-point metric. This matters when operators mix or when a basis is not orthonormal.

**Forgetting descendants.** Writing $\mathcal O_i\times\mathcal O_j\sim\lambda_{ijk}\mathcal O_k$ is only a shorthand. The exchanged primary brings its whole conformal multiplet.

**Assuming every operator appears.** Symmetries impose selection rules. If $\mathcal O_i$ and $\mathcal O_j$ carry global charges, only operators in representations contained in their product can appear.

**Confusing OPE coefficients with coupling constants.** In a Lagrangian CFT, coupling constants may help compute OPE coefficients perturbatively, but the OPE coefficients are physical CFT data. Many CFTs of interest are not most naturally defined by a weakly coupled Lagrangian.

## Relations to other pages

This page is the entry point for the OPE chapter. [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) gives the Hilbert-space argument behind the Euclidean convergence statement. [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) focuses on normalization, selection rules, and tensor structures.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) builds the contribution of one exchanged primary and all its descendants to a four-point function. [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) turns equality of different OPE channels into bootstrap equations.

The 2D version of singular OPE technology is developed later in [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) and [Stress-Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/). Current and stress-tensor OPEs also connect to Ward identities from the [Correlation Functions](/cft-bootstrap/correlation-functions/) chapter.

## Research status

The Euclidean OPE of local operators is established technology in CFT. In unitary theories with radial quantization, it has a genuine convergence interpretation inside correlation functions, and it underlies both analytic and numerical bootstrap methods.

Active work concerns harder regimes and broader categories: Lorentzian OPE limits, lightcone expansions, Regge limits, spinning and supersymmetric OPE structures, boundary and defect OPEs, logarithmic and nonunitary theories, nonlocal operators, and practical algorithms for extracting or constraining large amounts of OPE data.

A useful attitude is: the basic OPE is settled, but every time you change the kinematic regime, the operator type, or the positivity assumptions, you should recheck exactly which version of the statement you are using.

## Exercises

1. **Power counting in a scalar OPE.** Let $\mathcal O_i$, $\mathcal O_j$, and $\mathcal O_k$ be scalar primaries. Use scale covariance to determine the power of $|x|$ multiplying $\mathcal O_k(0)$ in the OPE of $\mathcal O_i(x)\mathcal O_j(0)$.

<details><summary><strong>Solution</strong></summary>

Under $x\mapsto \lambda x$, a scalar primary transforms as

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda x).
$$

The left side has scaling dimension $\Delta_i+\Delta_j$. The operator $\mathcal O_k(0)$ has dimension $\Delta_k$, so its coefficient must scale with dimension $\Delta_i+\Delta_j-\Delta_k$. Therefore the coefficient is proportional to

$$
|x|^{\Delta_k-\Delta_i-\Delta_j}
$$

up to angular dependence for spinning exchanges and up to descendant corrections.

</details>

2. **Identity coefficient.** Suppose $\mathcal O$ is a real scalar primary with

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{|x|^{2\Delta}}.
$$

What is the identity term in $\mathcal O(x)\mathcal O(0)$?

<details><summary><strong>Solution</strong></summary>

The identity contribution must reproduce the two-point function after taking the vacuum expectation value. Since $\langle \mathbf 1\rangle=1$ and nonidentity primaries have zero one-point function in flat space,

$$
\mathcal O(x)\mathcal O(0)
\supset
\frac{\mathbf 1}{|x|^{2\Delta}}.
$$

</details>

3. **First descendant coefficient.** Starting from the scalar three-point function, expand the factor $|y-x|^{-(\Delta_i+\Delta_k-\Delta_j)}$ for $|x|\ll |y|$ and recover the coefficient of $x^\mu\partial_\mu\mathcal O_k(0)$ in the scalar OPE.

<details><summary><strong>Solution</strong></summary>

Let

$$
\alpha=\Delta_i+\Delta_k-\Delta_j.
$$

For $|x|\ll |y|$,

$$
\frac{1}{|y-x|^\alpha}
=
\frac{1}{|y|^\alpha}
\left(1+\alpha\frac{x\cdot y}{y^2}+\cdots\right).
$$

The OPE ansatz gives

$$
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}
\left[
\langle \mathcal O_k(0)\mathcal O_k(y)\rangle
+a x^\mu\langle \partial_\mu\mathcal O_k(0)\mathcal O_k(y)\rangle+
\cdots
\right].
$$

Using

$$
\langle \partial_\mu\mathcal O_k(0)\mathcal O_k(y)\rangle
=2\Delta_k\frac{y_\mu}{|y|^{2\Delta_k+2}},
$$

we match $2a\Delta_k=\alpha$, hence

$$
a=\frac{\Delta_i-\Delta_j+\Delta_k}{2\Delta_k}.
$$

</details>

4. **Free scalar OPE.** For a unit-normalized free scalar with $\langle\phi(x)\phi(0)\rangle=|x|^{-(d-2)}$, use Wick's theorem to identify the identity contribution and the first normal-ordered scalar contribution in $\phi(x)\phi(0)$.

<details><summary><strong>Solution</strong></summary>

Wick's theorem gives

$$
\phi(x)\phi(0)=\langle\phi(x)\phi(0)\rangle\mathbf 1+:\!\phi(x)\phi(0)\!:.
$$

The contraction is

$$
\frac{\mathbf 1}{|x|^{d-2}}.
$$

Taylor expanding the normal-ordered product around the origin gives

$$
:\!\phi(x)\phi(0)\!:
=:\!\phi^2\!:(0)+x^\mu:\!\partial_\mu\phi\,\phi\!:(0)+\cdots.
$$

Thus the first nonidentity scalar contribution is $:\!\phi^2\!:(0)$, followed by descendants and other composite operators.

</details>

## References

- K. G. Wilson, “Non-Lagrangian Models of Current Algebra,” *Physical Review* **179** (1969). Original operator-product framework.
- L. P. Kadanoff, “Operator Algebra and the Determination of Critical Indices,” *Physical Review Letters* **23** (1969). Operator algebra in critical phenomena.
- A. M. Polyakov, “Nonhamiltonian Approach to Conformal Quantum Field Theory,” *Soviet Physics JETP* **39** (1974). Classic conformal-bootstrap formulation.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory* (Springer, 1997), especially the operator formalism and OPE chapters.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016), for higher-dimensional OPE and bootstrap basics.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017), for radial quantization, OPE convergence, and conformal blocks.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), for the role of OPE data in modern bootstrap.
- S. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE Convergence in Conformal Field Theory,” *Physical Review D* **86** (2012), for quantitative convergence estimates.

## Version history

- 2026-06-27: Initial polished draft defining the OPE, deriving the scalar primary contribution, and connecting OPE data to conformal blocks and crossing.
