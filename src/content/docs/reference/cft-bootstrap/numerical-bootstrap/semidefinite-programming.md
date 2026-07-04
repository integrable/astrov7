---
title: 'Semidefinite Programming'
description: 'How numerical conformal bootstrap problems become semidefinite programs through positivity of OPE data, polynomial approximations, and matrix-valued crossing equations.'
sidebar:
  label: 'Semidefinite Programming'
  order: 5
level: Graduate
status: 'Polished draft'
source: 'Poland, Rychkov, and Vichi 2019; Simmons-Duffin 2015; Rychkov and Su 2024; standard SDPB literature.'
topics:
  - semidefinite programming
  - numerical conformal bootstrap
  - matrix positivity
  - sums of squares
  - SDPB
canonicalTopics:
  - semidefinite-programming
  - bootstrap-sdp
  - matrix-positivity-bootstrap
researchStatus:
  established:
    - 'Semidefinite programming is the standard optimization framework for modern numerical bootstrap problems with continuous positivity constraints and mixed-correlator matrix positivity.'
  active:
    - 'Active work improves solver scaling, precision, certification, block approximations, mixed systems, navigator methods, and workflows for spinning, supersymmetric, defect, and gauge-theory bootstrap.'
---

## Summary

A **semidefinite program** is an optimization problem with matrix-positivity constraints. In the numerical conformal bootstrap, semidefinite programming appears for two related reasons.

First, even in a single-correlator scalar bootstrap problem, a functional must be positive for a continuum of operator dimensions:

$$
\alpha(\vec F_{\Delta,\ell})\ge0,
\qquad
\Delta\ge\Delta_{\min}(\ell).
$$

After rational approximation of conformal block derivatives, this becomes a polynomial-positivity problem. Polynomial positivity on a half-line can be encoded using sums of squares, and sums of squares are semidefinite constraints.

Second, in mixed-correlator systems, an exchanged operator can have several OPE coefficients. Its contribution is an outer product of an OPE vector with itself, so positivity becomes matrix positivity:

$$
M_{\Delta,\ell}(\alpha)\succeq0.
$$

Here $M\succeq0$ means that $M$ is positive semidefinite:

$$
v^T M v\ge0
\qquad
\text{for all real vectors }v.
$$

The bootstrap-to-SDP dictionary is therefore:

$$
\text{crossing}+\text{unitarity}+\text{gaps}
\quad\longrightarrow\quad
\text{linear functional with scalar or matrix positivity}
\quad\longrightarrow\quad
\text{semidefinite program}.
$$

This page explains the conceptual bridge. The next page, [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), explains how this bridge becomes a practical computation.

## Prerequisites

Read [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) and [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/) first.

You should know the finite vector crossing equation

$$
\vec F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0,
$$

and why an excluding functional satisfies positivity conditions on every allowed exchanged operator.

## Core idea

The bootstrap asks for a functional that is positive on infinitely many possible operator contributions. At fixed spin, the dimension $\Delta$ varies continuously. For mixed correlators, the positivity condition is matrix-valued. Semidefinite programming is the computational technology that handles both issues.

A learner-friendly slogan is

$$
\text{SDP}=
\text{linear optimization with the condition that certain matrices have no negative eigenvalues}.
$$

This is more general than linear programming. A scalar inequality such as

$$
f(x)\ge0
$$

is the special case of a one-by-one positive semidefinite matrix. A matrix inequality such as

$$
\begin{pmatrix}
a & b\\
b & c
\end{pmatrix}\succeq0
$$

requires

$$
a\ge0,
\qquad
c\ge0,
\qquad
ac-b^2\ge0,
$$

or equivalently nonnegative eigenvalues. Mixed-correlator bootstrap naturally produces exactly this kind of constraint.

## Positive semidefinite matrices

A real symmetric matrix $M$ is **positive semidefinite** if

$$
v^T M v\ge0
$$

for every real vector $v$. We write

$$
M\succeq0.
$$

Equivalent tests are:

| Criterion | Meaning |
|---|---|
| all eigenvalues are nonnegative | spectral definition |
| $v^TMv\ge0$ for all $v$ | quadratic-form definition |
| all principal minors are nonnegative | finite-dimensional algebraic test |
| $M=B^TB$ for some $B$ | Gram-matrix definition |

The Gram-matrix viewpoint is especially useful. A matrix is positive semidefinite precisely when it can be interpreted as inner products of vectors.

This matches the OPE story. In a mixed-correlator system, the OPE data for one exchanged operator form a vector, and its contribution is an outer product:

$$
\lambda\lambda^T\succeq0.
$$

Thus matrix positivity is not a numerical trick. It is Hilbert-space positivity written in the language of crossing equations.

## Standard SDP form

A semidefinite program can be written schematically as

$$
\text{maximize } b\cdot y
$$

subject to

$$
A_0+\sum_i y_i A_i\succeq0,
$$

where the $A_i$ are known symmetric matrices and the $y_i$ are variables.

In bootstrap language, the variables $y_i$ are often the coefficients of the linear functional,

$$
\alpha=\sum_i y_i\alpha_i.
$$

The matrix

$$
A_0+\sum_i y_i A_i
$$

encodes the condition that applying $\alpha$ to a block matrix gives a positive semidefinite result.

Different solver conventions use primal and dual forms, objective functions, and normalizations that may look different. The invariant content is that the unknown functional coefficients are chosen so that a family of scalar or matrix positivity inequalities holds.

## Scalar bootstrap as an SDP

In the simplest identical-scalar problem, the functional positivity condition is scalar:

$$
\alpha(\vec F_{\Delta,\ell})\ge0.
$$

At first glance this looks like linear programming, not semidefinite programming. The catch is that the inequality must hold for every continuous value

$$
\Delta\ge\Delta_{\min}(\ell).
$$

A practical implementation approximates block derivatives by rational functions of $\Delta$:

$$
\alpha(\vec F_{\Delta,\ell})
\approx
\chi_\ell(\Delta)\frac{P_\ell(\Delta)}{Q_\ell(\Delta)},
$$

where $\chi_\ell$ and $Q_\ell$ are positive in the allowed range. Then positivity reduces to

$$
P_\ell(\Delta)\ge0
\qquad
\Delta\ge\Delta_{\min}(\ell).
$$

A polynomial nonnegative on a half-line can be represented using sums of squares. For example, after shifting the lower endpoint to $x=0$, a polynomial positive for $x\ge0$ can often be written in the form

$$
p(x)=s_0(x)+x s_1(x),
$$

where $s_0$ and $s_1$ are sums of squares of polynomials. A sum of squares is equivalent to a positive semidefinite Gram matrix.

This is how even scalar bootstrap becomes an SDP in practice.

## Mixed correlators and matrix positivity

Mixed-correlator systems make semidefinite programming unavoidable. Suppose two external scalar operators, $\phi_1$ and $\phi_2$, both couple to an exchanged operator $\mathcal O$. The OPE coefficient vector is

$$
\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{11\mathcal O}\\
\lambda_{22\mathcal O}
\end{pmatrix}.
$$

The contribution of $\mathcal O$ to crossing contains the positive semidefinite outer product

$$
\lambda_{\mathcal O}\lambda_{\mathcal O}^T
=
\begin{pmatrix}
\lambda_{11\mathcal O}^2 & \lambda_{11\mathcal O}\lambda_{22\mathcal O}\\
\lambda_{11\mathcal O}\lambda_{22\mathcal O} & \lambda_{22\mathcal O}^2
\end{pmatrix}.
$$

A functional must make the corresponding block matrix positive semidefinite:

$$
M_{\Delta,\ell}(\alpha)\succeq0.
$$

This condition means every possible OPE-vector direction contributes nonnegatively. It is the mixed-correlator analogue of

$$
\lambda^2\ge0.
$$

The matrix size grows with the number of independent external operator pairs and tensor structures. This is why mixed-correlator bootstrap is powerful and expensive at the same time.

## Polynomial matrix programs

After derivative truncation and rational approximation, a bootstrap problem becomes a **polynomial matrix program**. Instead of asking for one polynomial to be positive on a half-line, one asks for a matrix of polynomials to be positive semidefinite:

$$
M_\ell(\Delta)\succeq0
\qquad
\Delta\ge\Delta_{\min}(\ell).
$$

This is stronger than requiring each entry of the matrix to be positive. The condition is that every quadratic form is nonnegative:

$$
w^TM_\ell(\Delta)w\ge0
$$

for every vector $w$ and every allowed $\Delta$.

Sums-of-squares technology converts this continuous matrix positivity condition into finitely many semidefinite constraints on Gram matrices.

This is the mathematical reason specialized solvers such as SDPB were created for bootstrap problems. General-purpose optimization packages are often not designed for the precision, size, and polynomial-matrix structure that bootstrap produces.

## Primal and dual viewpoints

The bootstrap has two complementary optimization viewpoints.

The **primal** viewpoint asks whether crossing can be solved by positive OPE data. It searches for a positive measure over operator dimensions and spins that cancels the identity.

The **dual** viewpoint asks whether an excluding functional exists. It searches for a separating hyperplane.

Schematically:

| Viewpoint | Searches for | Interpretation |
|---|---|---|
| primal | positive OPE data solving crossing | candidate crossing solution |
| dual | positive functional excluding crossing | certificate of inconsistency |

In exact convex optimization, primal and dual feasibility are related by duality theorems. Numerically, solvers report approximate primal and dual statuses, residuals, and gaps.

For ordinary bootstrap exclusion plots, the dual functional is often the object of physical interest: it is the certificate that a point is inconsistent. For spectrum extraction, the extremal functional at a boundary is also a useful diagnostic.

## Feasibility and optimization

Many bootstrap tasks are feasibility problems:

$$
\text{Does there exist a functional satisfying these inequalities?}
$$

Bounds and islands are obtained by solving many feasibility problems at different trial parameter values.

Other tasks are optimization problems. For example, one may optimize an OPE coefficient bound or minimize a navigator-like objective. These problems require a normalization for the functional, such as

$$
\alpha(\vec F_{\mathbf1})=1.
$$

Without a normalization, the functional can be rescaled:

$$
\alpha\mapsto c\alpha,
\qquad
c>0,
$$

and the optimization objective may become meaningless.

The distinction matters in practice. Feasibility, exclusion, OPE bounds, and navigator searches use related SDP machinery but have different objectives and interpretations.

## Reading solver output

An SDP solver usually reports statuses such as primal feasible, dual feasible, primal infeasible, dual infeasible, or numerical failure. The exact labels depend on the solver.

In bootstrap language, a **dual feasible** solution often means an excluding functional has been found. A **primal feasible** solution may indicate that the truncated crossing constraints can be satisfied by positive data, or at least not ruled out in the primal formulation.

One must be careful. Numerical solver status is not a final physics statement by itself. It must be interpreted together with:

- derivative cutoff;
- spin treatment;
- block approximation accuracy;
- arithmetic precision;
- solver tolerances;
- gap assumptions;
- stability under reruns and increased cutoffs.

A bootstrap result is a chain of reasoning, not just the word “feasible” or “infeasible” in a log file.

## Why high precision is common

Bootstrap SDPs are often ill-conditioned. Conformal block derivatives can vary across many orders of magnitude. High derivative orders, large spins, nearly saturated positivity constraints, and mixed-correlator matrices all worsen conditioning.

For this reason, numerical bootstrap computations frequently use arbitrary-precision arithmetic. Low precision may produce false failures, unstable bounds, or unreliable extremal spectra.

High precision is not intellectual ornamentation. It is a practical necessity when the geometry of the allowed cone becomes thin and high-dimensional.

A useful rule of thumb is:

$$
\text{higher cutoff}+\text{larger mixed system}+\text{smaller island}
\quad\Rightarrow\quad
\text{more precision needed}.
$$

The exact precision required is problem-dependent.

## Common pitfalls

**Do not think SDP means the CFT is finite-dimensional.** The finite SDP is a truncated representation of infinitely many crossing constraints and infinitely many possible operators.

**Do not confuse entrywise positivity with positive semidefiniteness.** A matrix can have positive entries but a negative eigenvalue. Bootstrap requires matrix positivity, not entrywise positivity.

**Do not ignore continuous positivity in dimension.** Checking a few sample values of $\Delta$ is not enough for an exclusion certificate.

**Do not treat solver status as a physics result by itself.** The physics statement includes assumptions, truncation, precision, and interpretation.

**Do not compare SDP runs without matching normalizations.** Block conventions, functional normalization, and OPE normalization affect numerical values.

**Do not forget primal-dual distinctions.** A dual feasible point often means an excluding functional; a primal feasible point means something different.

**Do not expect low precision to work at high cutoff.** Ill-conditioning is normal in serious bootstrap computations.

## Relations to other pages

This page follows [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/) and prepares [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/).

It also connects to [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/), and [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/).

For the underlying physics, see [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) and [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/).

## Research status

Semidefinite programming is established as one of the core technologies of the numerical conformal bootstrap. The conversion from crossing equations to polynomial matrix programs is standard in high-precision scalar and mixed-correlator studies.

Active work improves solver scaling, input generation, certification, high-precision numerics, mixed-correlator performance, and alternatives or complements such as navigator methods, cutting-surface algorithms, Delaunay triangulation, and hybrid analytic-numerical techniques.

## Exercises

### Exercise 1

Show that a symmetric matrix $M$ is positive semidefinite if $M=B^TB$ for some matrix $B$.

<details><summary><strong>Solution</strong></summary>

For any vector $v$,

$$
v^TMv=v^TB^TBv=(Bv)^T(Bv)=\|Bv\|^2\ge0.
$$

Therefore $M\succeq0$.

</details>

### Exercise 2

For

$$
M=\begin{pmatrix}a&b\\ b&c\end{pmatrix},
$$

state the positive-semidefinite conditions.

<details><summary><strong>Solution</strong></summary>

For a real symmetric two-by-two matrix, positive semidefiniteness is equivalent to

$$
a\ge0,
\qquad
c\ge0,
\qquad
ac-b^2\ge0.
$$

Equivalently, both eigenvalues are nonnegative.

</details>

### Exercise 3

Why does a mixed-correlator exchanged operator naturally produce an outer product of OPE coefficients?

<details><summary><strong>Solution</strong></summary>

If an operator $\mathcal O$ couples to several external pairs, its OPE data form a vector, for example

$$
\lambda_{\mathcal O}=\begin{pmatrix}\lambda_{11\mathcal O}\\ \lambda_{22\mathcal O}\end{pmatrix}.
$$

The contribution to a four-point crossing equation contains products of OPE coefficients from the left and right OPE channels. These products assemble into

$$
\lambda_{\mathcal O}\lambda_{\mathcal O}^T,
$$

which is positive semidefinite because it is an outer product of a real vector with itself.

</details>

### Exercise 4

Explain why polynomial positivity on a half-line is relevant to scalar bootstrap.

<details><summary><strong>Solution</strong></summary>

At fixed spin, an exchanged operator can have any dimension above the unitarity bound or an assumed gap:

$$
\Delta\ge\Delta_{\min}(\ell).
$$

After rational approximation of conformal block derivatives, the functional positivity condition becomes a polynomial inequality

$$
P_\ell(\Delta)\ge0
$$

on that half-line. Sums-of-squares methods encode this continuous positivity condition as semidefinite constraints.

</details>

### Exercise 5

What is the difference between a primal and dual bootstrap viewpoint?

<details><summary><strong>Solution</strong></summary>

The primal viewpoint searches for positive OPE data that solve the truncated crossing equations. The dual viewpoint searches for a linear functional that proves no such positive solution exists. In geometric terms, the primal asks whether the negative identity vector lies in the allowed cone, while the dual asks for a hyperplane separating it from that cone.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- W. Landry and D. Simmons-Duffin, “Scaling the semidefinite program solver SDPB,” 2019.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-01: First polished draft. Added SDP definitions, positive semidefinite matrices, scalar and mixed-correlator bootstrap routes to SDP, polynomial matrix programs, primal-dual interpretation, solver-output caveats, exercises, and references.
