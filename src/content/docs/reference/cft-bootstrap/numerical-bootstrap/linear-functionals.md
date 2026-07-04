---
title: "Linear Functionals"
description: "How linear functionals turn bootstrap crossing equations into exclusion certificates, bounds, and the geometric separating-hyperplane picture."
sidebar:
  label: "Linear Functionals"
  order: 3
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Simmons-Duffin TASI lectures; Rychkov lectures; standard numerical bootstrap literature."
topics:
  - linear functionals
  - numerical conformal bootstrap
  - crossing symmetry
  - convex optimization
  - exclusion certificates
canonicalTopics:
  - linear-functionals
  - bootstrap-exclusion-certificates
  - separating-hyperplane-bootstrap
researchStatus:
  established:
    - "Linear functionals provide the basic exclusion certificates in the numerical conformal bootstrap by separating the identity contribution from the cone of allowed conformal block vectors."
  active:
    - "Modern work refines functional searches through semidefinite programming, navigator methods, cutting-surface algorithms, mixed-correlator systems, and rigorous numerical certification."
---

## Summary

A **linear functional** is a linear map applied to the crossing equation. In the simplest identical-scalar bootstrap, crossing has the schematic vector form

$$
\vec F_{\mathbf 1}+\sum_{\mathcal O\ne\mathbf 1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0,
$$

with

$$
\lambda_{\mathcal O}^2\ge0
$$

in a unitary normalization. A linear functional $\alpha$ assigns a number to each vector:

$$
\vec F\mapsto \alpha(\vec F).
$$

If one can find $\alpha$ such that

$$
\alpha(\vec F_{\mathbf 1})>0,
\qquad
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for every non-identity operator allowed by the assumed spectrum, then applying $\alpha$ to crossing gives a contradiction:

$$
0=\alpha(\vec F_{\mathbf 1})+\sum_{\mathcal O\ne\mathbf 1}\lambda_{\mathcal O}^2\alpha(\vec F_{\Delta,\ell})>0.
$$

Thus the assumed spectrum is impossible.

This is the basic engine of the numerical bootstrap. The computer searches for a linear functional that proves a proposed gap, spectrum, or parameter point inconsistent. Bounds are obtained by scanning assumptions and asking where such functionals exist.

## Prerequisites

Read [What the Numerical Bootstrap Computes](/cft-bootstrap/numerical-bootstrap/what-the-numerical-bootstrap-computes/) and [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/) first.

You should know the vector crossing equation

$$
\vec F_{\mathbf 1}+\sum_{\mathcal O\ne\mathbf 1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0,
$$

and why the coefficients $\lambda_{\mathcal O}^2$ are nonnegative for unitary identical scalar four-point functions.

## Core idea

Crossing asks whether the negative identity vector can be built from allowed conformal block vectors:

$$
-\vec F_{\mathbf 1}
\in
\operatorname{Cone}\{\vec F_{\Delta,\ell}\text{ allowed}\}.
$$

Here the cone consists of all positive linear combinations of allowed block vectors. If $-\vec F_{\mathbf 1}$ lies inside the cone, the assumed spectrum might be consistent. If it lies outside, convex geometry says there is a hyperplane separating it from the cone.

A linear functional is precisely that hyperplane. It is a covector that tests every block vector and returns a sign.

The numerical bootstrap slogan is

$$
\text{exclusion}=
\text{separating hyperplane for the crossing cone}.
$$

This is why the method is so robust. One does not need to find the actual CFT. To rule out a proposed spectrum, it is enough to find one functional with the right positivity properties.

## Setup and conventions

Fix a finite derivative basis. Each crossing function becomes a vector

$$
\vec F_{\Delta,\ell}\in\mathbb R^K,
$$

where $K$ is the number of derivative components kept. A linear functional is an element of the dual vector space:

$$
\alpha\in(\mathbb R^K)^*.
$$

In coordinates,

$$
\alpha(\vec F)=\sum_{a=1}^K\alpha_a F_a.
$$

If the vector entries are derivatives, then $\alpha$ is a linear combination of derivatives at the crossing-symmetric point. For example,

$$
\alpha(F)=
\sum_{(m,n)\in\mathcal D}
\alpha_{m,n}\,
\partial_z^m\partial_{\bar z}^nF(z,\bar z)\bigg|_{z=\bar z=1/2}.
$$

The derivative set $\mathcal D$ is finite in an actual computation. Increasing the derivative cutoff enlarges the space of possible functionals.

The sign convention on this page is

$$
\alpha(\vec F_{\mathbf 1})>0,
\qquad
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for allowed non-identity operators. Some papers put the identity on the other side and reverse all signs. The exclusion logic is identical.

## The exclusion lemma

The basic argument is short enough to deserve a name.

Suppose an assumed spectrum would make crossing possible:

$$
\vec F_{\mathbf 1}+\sum_{\mathcal O\ne\mathbf 1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0.
$$

Assume unitarity gives

$$
\lambda_{\mathcal O}^2\ge0.
$$

Now suppose there exists a linear functional $\alpha$ such that

$$
\alpha(\vec F_{\mathbf 1})>0
$$

and

$$
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for every allowed non-identity primary. Applying $\alpha$ to crossing gives

$$
0=\alpha(\vec F_{\mathbf 1})+\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\mathcal O}^2\alpha(\vec F_{\Delta,\ell}).
$$

The first term is strictly positive. Every term in the sum is nonnegative. Hence the right-hand side is strictly positive, contradicting zero.

Therefore no unitary CFT satisfying the assumed spectral conditions exists.

This is the rigorous core of a bootstrap exclusion plot.

## Example: bounding a scalar gap

Consider an identical scalar $\phi$ in a unitary CFT. Suppose we want to test the hypothesis:

$$
\text{there is no scalar in }\phi\times\phi\text{ with }0<\Delta<\Delta_{\rm gap}.
$$

The allowed non-identity spectrum is then assumed to include:

| Sector | Allowed dimensions |
|---|---|
| scalar, $\ell=0$ | $\Delta\ge\Delta_{\rm gap}$ |
| spin $\ell\ge2$ even | $\Delta\ge\ell+d-2$ |
| optional stress tensor | $\Delta=d$, $\ell=2$, with Ward-identity coefficient if imposed |

A functional excluding this hypothesis satisfies

$$
\alpha(\vec F_{\mathbf 1})>0,
$$

$$
\alpha(\vec F_{\Delta,0})\ge0
\qquad
\Delta\ge\Delta_{\rm gap},
$$

and

$$
\alpha(\vec F_{\Delta,\ell})\ge0
\qquad
\Delta\ge\ell+d-2,
\qquad
\ell=2,4,6,\ldots .
$$

If such a functional exists, the proposed scalar gap is too large. Thus crossing requires a scalar below $\Delta_{\rm gap}$.

Scanning $\Delta_{\rm gap}$ gives an upper bound on the first scalar dimension as a function of the external dimension $\Delta_\phi$.

## Bounds as optimization problems

A bound is obtained by turning exclusion into an optimization problem. There are two common viewpoints.

First, one can scan. Pick a trial gap and ask whether an excluding functional exists. Repeat for many trial gaps. The boundary between excluded and not-excluded values is the numerical bound.

Second, one can optimize directly. Normalize the functional by fixing the identity contribution, for example

$$
\alpha(\vec F_{\mathbf 1})=1,
$$

and then optimize some objective related to the desired CFT datum.

For example, to bound an OPE coefficient of a particular operator $\mathcal O_*$, isolate its contribution:

$$
\vec F_{\mathbf 1}+\lambda_*^2\vec F_*+\sum_{\mathcal O\ne \mathbf 1,\mathcal O_*}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0.
$$

A functional with

$$
\alpha(\vec F_{\mathbf 1})=1,
\qquad
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for all other allowed operators gives, after applying to crossing,

$$
0=1+\lambda_*^2\alpha(\vec F_*)+\text{nonnegative terms}.
$$

If $\alpha(\vec F_*)<0$, then

$$
\lambda_*^2\le -\frac{1}{\alpha(\vec F_*)}.
$$

Optimizing over $\alpha$ produces the strongest bound available in the chosen functional space.

## Linear programming versus semidefinite programming

In the simplest identical-scalar setup, the unknown coefficients are nonnegative numbers:

$$
\lambda_{\mathcal O}^2\ge0.
$$

The dual positivity constraints are scalar inequalities:

$$
\alpha(\vec F_{\Delta,\ell})\ge0.
$$

This is morally a linear programming problem, although the constraints are continuous in $\Delta$ and involve conformal blocks.

In mixed-correlator systems, an exchanged operator can have several OPE coefficients. For example, in the Ising mixed system an even operator may couple to both $\sigma\sigma$ and $\epsilon\epsilon$:

$$
\lambda_{\sigma\sigma\mathcal O},
\qquad
\lambda_{\epsilon\epsilon\mathcal O}.
$$

The contribution is an outer product of OPE vectors and is positive semidefinite. The functional must make a matrix positive semidefinite:

$$
\alpha(\vec F_{\Delta,\ell})\succeq0.
$$

This is the origin of semidefinite programming in modern bootstrap calculations.

The conceptual role of $\alpha$ is unchanged. It is still the separating object. The positivity condition has simply become matrix-valued.

## Functionals as differential operators

At finite derivative cutoff, a functional is explicitly a differential operator evaluated at the symmetric point. In one common language,

$$
\alpha=\sum_{m+n\le\Lambda}a_{m,n}\partial_z^m\partial_{\bar z}^n\bigg|_{z=\bar z=1/2},
$$

with only derivatives of the correct crossing parity included.

The coefficients $a_{m,n}$ are the unknowns solved for by the optimization algorithm. The conformal blocks are known functions. Thus each positivity constraint is a condition on a known function of $\Delta$ and $\ell$:

$$
\alpha(\vec F_{\Delta,\ell})\ge0.
$$

Because $\Delta$ is continuous, one needs a way to enforce this inequality for all $\Delta$ above the relevant bound. Practical implementations use rational approximations and convert the condition into positivity of polynomials or matrices, which is handled by semidefinite programming.

This is where the abstract hyperplane picture becomes real computation.

## Geometry of allowed and excluded regions

For fixed external data and assumptions, the set of crossing-compatible solutions is convex in the space of positive OPE measures. Linear functionals detect when a proposed point lies outside the projection of that convex set.

This explains the shape of many bootstrap plots. An excluded point has a separating functional. A not-excluded point has no separating functional in the searched space. A boundary point has an extremal functional, often with zeros at operator dimensions in a candidate extremal spectrum.

The geometry can be summarized as follows:

| Object | Geometric meaning |
|---|---|
| block vector $\vec F_{\Delta,\ell}$ | generator of a cone of possible contributions |
| OPE square $\lambda^2$ | nonnegative coordinate in the cone |
| identity vector $\vec F_{\mathbf1}$ | fixed vector that must be canceled |
| functional $\alpha$ | hyperplane normal vector |
| excluded point | separated from the cone |
| boundary point | functional touches the cone |
| extremal spectrum | approximate points where the hyperplane touches generators |

This geometric picture is one of the best ways to understand why numerical bootstrap works.

## Extremal functionals

At an optimal bound, the excluding functional becomes extremal. It is just barely able to satisfy positivity. As a result, it often has zeros at dimensions of operators that would appear in the putative solution saturating the bound:

$$
\alpha(\vec F_{\Delta_i,\ell_i})=0.
$$

If an operator had positive OPE coefficient and

$$
\alpha(\vec F_{\Delta_i,\ell_i})>0,
$$

it would contribute positively after applying $\alpha$ and could not appear in a crossing-saturating solution. Therefore operators in an extremal solution tend to sit at zeros of the functional.

This is the intuition behind the extremal functional method. The functional is not only an exclusion certificate; at the boundary, it becomes a spectroscopic tool.

The method is powerful but delicate. Degeneracies, finite cutoff, numerical precision, mixed systems, and accidental zeros can complicate interpretation.

## Functionals and islands

Islands are built by combining many exclusions. A point in parameter space, such as

$$
(\Delta_\sigma,\Delta_\epsilon),
$$

is excluded if a functional exists for the crossing equations and spectral assumptions at that point. The allowed island is the region where no such functional is found at the chosen cutoff.

The boundary of an island is therefore made of many functional certificates. Each excluded exterior point has its own separating functional.

This is why island computations are expensive. One is not solving one optimization problem. One is mapping a high-dimensional landscape of feasibility problems.

Modern algorithms such as navigator methods and cutting-surface methods improve this search, but the underlying logic remains functional separation.

## Normalization choices

To search for a functional, one must fix an overall scale. If $\alpha$ excludes, then any positive multiple of $\alpha$ also excludes. A common normalization is

$$
\alpha(\vec F_{\mathbf1})=1.
$$

Another choice may normalize a target vector or objective. The normalization does not change whether a functional exists, but it matters for numerical conditioning and for objective values in OPE coefficient bounds.

Sign conventions also vary. Some authors write crossing as

$$
-\vec F_{\mathbf1}=\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell},
$$

and then demand the functional be positive on the right-hand cone and negative on the left-hand side. Others use the convention of this page. Always translate the signs before comparing formulas.

The invariant statement is:

$$
\text{a functional separates the fixed identity contribution from the allowed positive cone.}
$$

## Continuous positivity

A subtle point is that the functional must be positive not just on a finite list of operator dimensions, but for a continuum:

$$
\Delta\ge\Delta_{\rm min}(\ell).
$$

At fixed spin $\ell$, this means checking

$$
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for all allowed $\Delta$. This is infinitely many inequalities.

Practical bootstrap methods handle this by approximating conformal block derivatives as rational functions of $\Delta$. After multiplying by a positive denominator, the positivity condition becomes polynomial positivity on a half-line. Polynomial positivity can be encoded using sums of squares and semidefinite constraints.

This step is where numerical rigor and implementation details enter. A beautiful analytic hyperplane idea becomes a large but finite semidefinite program.

## What failure to find a functional means

If the solver does not find an excluding functional, the proposed assumptions are **not excluded** at the chosen cutoff and precision. This is weaker than saying they are consistent.

Possible reasons for failure include:

| Reason | Meaning |
|---|---|
| assumptions are actually consistent | A CFT or crossing solution may exist. |
| cutoff too small | A separating functional exists only at higher derivative order. |
| precision too low | Numerical instability prevents finding the certificate. |
| block approximation too crude | The finite problem does not faithfully represent the intended constraints. |
| search formulation incomplete | Missing sectors, spins, or positivity constraints weaken the problem. |

Thus “no functional found” is not evidence of existence by itself. It is a finite computational statement.

## Common pitfalls

**Do not confuse the functional with a CFT solution.** A functional proves inconsistency. It is not itself a spectrum or correlator.

**Do not forget the identity sign.** The fixed identity contribution is what makes the contradiction possible. Sign conventions vary, but the identity must be separated from the allowed cone.

**Do not assume positivity without checking unitarity and external operators.** The simple $\lambda^2\ge0$ structure applies to unitary identical-scalar correlators. Other systems require matrix or modified positivity.

**Do not treat finite cutoff as exact.** A functional at cutoff $\Lambda$ proves exclusion in the truncated setup. The full crossing problem is recovered only in an appropriate infinite-cutoff limit.

**Do not interpret failure to find a functional as proof of existence.** It means only that the searched functional space did not exclude the assumptions.

**Do not compare OPE coefficient bounds without matching normalizations.** Functional normalizations, two-point normalizations, and block conventions all matter.

**Do not trust accidental zeros automatically.** Extremal functional zeros need convergence checks and physical interpretation.

## Relations to other pages

This page follows [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/). The next page, [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), explains how the finite functional space is chosen.

[Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) explains how continuous positivity constraints are converted into a numerical optimization problem. [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/) explains how scanning with functionals produces familiar bootstrap plots. [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/) explains how optimal functionals can extract spectra.

For the physics input, see [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) and [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/).

## Research status

The linear-functional exclusion method is established. It is the foundational idea behind modern numerical bootstrap bounds and remains visible even in sophisticated semidefinite, mixed-correlator, and navigator-based computations.

Active work focuses on making functional searches more powerful and reliable: improved SDP solvers, better block approximations, rigorous certificates, large-scale mixed systems, spinning correlators, defect bootstrap, nonunitary variants, and algorithms that navigate high-dimensional allowed regions efficiently.

## Exercises

### Exercise 1

Prove the exclusion lemma for the crossing equation

$$
\vec F_{\mathbf 1}+\sum_i p_i\vec F_i=0,
\qquad
p_i\ge0.
$$

<details><summary><strong>Solution</strong></summary>

Assume there is a linear functional $\alpha$ such that

$$
\alpha(\vec F_{\mathbf 1})>0,
\qquad
\alpha(\vec F_i)\ge0
$$

for all $i$. Applying $\alpha$ to crossing gives

$$
0=\alpha(\vec F_{\mathbf 1})+\sum_i p_i\alpha(\vec F_i).
$$

The first term is strictly positive. Since $p_i\ge0$ and $\alpha(\vec F_i)\ge0$, every term in the sum is nonnegative. Therefore the right-hand side is strictly positive, contradicting zero. Hence no such positive solution exists.

</details>

### Exercise 2

Why must one fix a normalization for $\alpha$ in an optimization problem?

<details><summary><strong>Solution</strong></summary>

If $\alpha$ satisfies the positivity inequalities, then $c\alpha$ also satisfies them for any $c>0$. Without fixing this scale, an optimization objective may be unbounded or meaningless. A common choice is

$$
\alpha(\vec F_{\mathbf1})=1.
$$

This removes the overall rescaling freedom and lets the optimizer compare functionals meaningfully.

</details>

### Exercise 3

In an OPE coefficient bound, suppose

$$
0=1+\lambda_*^2\alpha(\vec F_*)+\sum_i p_i\alpha(\vec F_i),
$$

where $p_i\ge0$, $\alpha(\vec F_i)\ge0$, and $\alpha(\vec F_*)<0$. Derive an upper bound on $\lambda_*^2$.

<details><summary><strong>Solution</strong></summary>

The non-target sum is nonnegative, so

$$
0\ge 1+\lambda_*^2\alpha(\vec F_*).
$$

Since $\alpha(\vec F_*)<0$, rearranging gives

$$
\lambda_*^2\le -\frac{1}{\alpha(\vec F_*)}.
$$

Optimizing the functional can improve this upper bound.

</details>

### Exercise 4

Explain the cone picture of the identical-scalar crossing equation.

<details><summary><strong>Solution</strong></summary>

The non-identity terms in crossing are

$$
\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}.
$$

Since $\lambda_{\mathcal O}^2\ge0$, this is a positive linear combination of allowed block vectors. The set of all such combinations is a convex cone. Crossing requires this cone to contain

$$
-\vec F_{\mathbf1}.
$$

If it does not, a separating hyperplane exists. The corresponding hyperplane normal is the excluding linear functional.

</details>

### Exercise 5

Why do mixed correlators require matrix positivity rather than ordinary scalar positivity?

<details><summary><strong>Solution</strong></summary>

In a mixed-correlator system, one exchanged operator can couple to several pairs of external operators. Its OPE data form a vector, for example

$$
\lambda_{\mathcal O}=\begin{pmatrix}\lambda_{11\mathcal O}\\ \lambda_{22\mathcal O}\end{pmatrix}.
$$

The contribution to crossing contains the outer product

$$
\lambda_{\mathcal O}\lambda_{\mathcal O}^{T},
$$

which is positive semidefinite. Therefore a functional must make the corresponding block matrix positive semidefinite. This is stronger and more structured than requiring a single number to be nonnegative.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-01: First polished draft. Added exclusion lemma, cone geometry, gap bounds, OPE coefficient bounds, differential-functional interpretation, matrix positivity preview, extremal-functional connection, exercises, and references.
