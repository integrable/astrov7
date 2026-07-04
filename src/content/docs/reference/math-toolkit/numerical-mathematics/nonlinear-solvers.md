---
title: "Nonlinear Solvers"
description: "A QFT-oriented guide to fixed-point iteration, Newton methods, quasi-Newton methods, line searches, trust regions, residuals, Jacobians, continuation, and nonlinear equations from saddle points and self-consistency."
sidebar:
  label: "Nonlinear Solvers"
  order: 5
level: Graduate
status: "Polished draft"
source: "Numerical analysis, nonlinear optimization, variational field equations, mean-field theory, Schwinger–Dyson equations, lattice saddle equations, and self-consistency problems in QFT and statistical field theory."
topics:
  - nonlinear solvers
  - Newton method
  - fixed-point iteration
  - quasi-Newton methods
  - line search
  - trust region methods
  - continuation methods
  - self-consistency equations
canonicalTopics:
  - nonlinear-equations
  - newton-method
  - fixed-point-iteration
  - residual-and-jacobian
  - numerical-saddle-equations
researchStatus:
  established:
    - "Fixed-point iteration, Newton methods, quasi-Newton methods, line searches, trust-region globalization, residual norms, and continuation methods are standard tools for solving finite-dimensional nonlinear systems."
  active:
    - "Large-scale nonlinear solves in lattice field theory, tensor networks, conformal bootstrap, functional RG, real-time dynamics, stochastic PDEs, and saddle-point equations remain active computational-QFT topics."
---

## Summary

A nonlinear solver tries to find $u$ such that

$$
F(u)=0,
$$

where $F$ is not a linear map. In QFT and statistical field theory, this plain-looking equation hides many familiar problems:

| Equation | What $u$ is | What $F(u)=0$ means |
|---|---|---|
| Classical field equation | field configuration | stationary action |
| Gap equation | mass, condensate, or order parameter | self-consistency |
| Saddle-point equation | collective field or auxiliary field | dominant large-$N$ configuration |
| Schwinger–Dyson truncation | propagator or vertex function | nonlinear integral equation |
| Lattice minimization | field values on sites and links | discrete Euler–Lagrange equations |
| Bootstrap-style search | spectral or functional parameters | feasibility boundary or stationarity condition |

The main practical lesson is that solving a nonlinear equation is not just “inverting a matrix.” A nonlinear solver is an iterative process that repeatedly asks three questions:

$$
\text{Where am I?}
\qquad
\text{Which linear problem should I solve next?}
\qquad
\text{Can I trust that step?}
$$

Newton’s method answers the second question by linearizing $F$. Globalized Newton methods answer the third question with line searches or trust regions. Continuation methods answer a fourth question: how do I follow a solution as a parameter changes?

## Prerequisites

You should know basic linear algebra, Taylor expansion in several variables, gradients, Hessians, and the idea that a discretized field equation becomes a finite-dimensional system. It helps to have read [Finite-Difference Methods](/math-toolkit/numerical-mathematics/finite-difference-methods/), [Finite-Element Methods](/math-toolkit/numerical-mathematics/finite-element-methods/), and [Eigenvalue Problems](/math-toolkit/numerical-mathematics/eigenvalue-problems/) in this chapter.

We write $u\in\mathbb R^N$ or $\mathbb C^N$ for the unknown vector. In applications, $u$ may be a flattened list of field values, Fourier coefficients, variational parameters, link variables, propagator samples, or Lagrange multipliers.

## The basic problem

Let

$$
F:U\subset V\to W
$$

be a differentiable map between finite-dimensional vector spaces. A nonlinear equation asks for

$$
F(u_*)=0.
$$

The residual at an approximate solution $u$ is

$$
r(u)=F(u).
$$

A numerical method is judged by how it reduces a norm of the residual,

$$
\|F(u_n)\|,
$$

and by whether the computed $u_n$ stabilizes under refinement, parameter variation, and independent checks.

In field theory, $F$ often comes from a functional derivative. If $S[u]$ is a discretized action or energy, then the stationary equation is

$$
F_i(u)=\frac{\partial S}{\partial u_i}=0.
$$

The Jacobian of $F$ is then the Hessian of $S$:

$$
J_{ij}(u)=\frac{\partial F_i}{\partial u_j}
=\frac{\partial^2 S}{\partial u_i\partial u_j}.
$$

This is why nonlinear solvers and eigenvalue problems are neighbors: after finding a saddle, the next question is often the spectrum of small fluctuations around it.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A nonlinear solver workflow from residual to Jacobian, step selection, globalization, convergence, and validation.](/figures/math-toolkit/nonlinear-solver-workflow.svg)

<figcaption>

A robust nonlinear solve is a loop, not a single formula. Linearization proposes a step; globalization decides whether to trust it; convergence tests examine both the residual and the step; validation checks that the solution is not a numerical mirage.

</figcaption>
</figure>

## Fixed-point iteration

A fixed-point problem has the form

$$
u=G(u).
$$

The simplest iteration is

$$
u_{n+1}=G(u_n).
$$

A root-finding problem $F(u)=0$ can often be rewritten as a fixed-point problem. For example,

$$
u=G(u)=u-\alpha F(u)
$$

has the same fixed points as $F(u)=0$.

Fixed-point iteration converges locally if $G$ is a contraction. In one dimension, if $u_*$ is a fixed point and

$$
|G'(u_*)|<1,
$$

then nearby iterates converge to $u_*$. In many dimensions the corresponding condition is that the spectral radius of $DG(u_*)$ is less than $1$:

$$
\rho(DG(u_*))<1.
$$

This condition explains why naive iteration can be painfully slow near criticality. If the largest eigenvalue of $DG$ approaches $1$, errors decay slowly. In statistical mechanics this is the numerical shadow of long correlation lengths.

## Relaxation and damping

A common improvement is damped fixed-point iteration:

$$
u_{n+1}=(1-\omega)u_n+\omega G(u_n),
$$

where $0<\omega\le1$. The parameter $\omega$ is a relaxation parameter. Small $\omega$ damps oscillations and can stabilize unstable naive updates, at the price of slower convergence.

For equations coming from minimizing an energy $E(u)$, gradient descent is the fixed-point-like iteration

$$
u_{n+1}=u_n-\alpha_n\nabla E(u_n).
$$

It is robust but can be very slow in ill-conditioned problems. If the Hessian has eigenvalues ranging from tiny to huge, the step size that is stable in the steep direction is too small for the shallow direction. This stiffness is everywhere in discretized field theory.

## Newton’s method

Newton’s method uses the first-order Taylor expansion

$$
F(u+\delta u)=F(u)+J(u)\delta u+O(\|\delta u\|^2),
$$

where

$$
J_{ij}(u)=\frac{\partial F_i}{\partial u_j}.
$$

Set the linear approximation to zero:

$$
F(u)+J(u)\delta u=0.
$$

The Newton step solves

$$
J(u_n)\delta u_n=-F(u_n),
$$

then updates

$$
u_{n+1}=u_n+\delta u_n.
$$

In exact arithmetic and under favorable hypotheses, Newton’s method converges quadratically near a nonsingular root:

$$
\|u_{n+1}-u_*\|\le C\|u_n-u_*\|^2.
$$

That is the good news. The bad news is that Newton’s method only behaves this beautifully once it is already close enough to the correct root and the Jacobian is well-conditioned.

In QFT, the Jacobian is often a discretized fluctuation operator. If it has small eigenvalues, near-zero modes, gauge zero modes, or unstable directions, the Newton step may be singular, enormous, or physically meaningless without constraints.

## Newton’s method for a scalar equation

For one equation $f(x)=0$, Newton’s method is

$$
x_{n+1}=x_n-\frac{f(x_n)}{f'(x_n)}.
$$

Geometrically, one replaces $f$ by its tangent line at $x_n$ and takes the zero of that tangent line.

For

$$
f(x)=x^2-a,
$$

Newton gives

$$
x_{n+1}=\frac12\left(x_n+\frac{a}{x_n}\right),
$$

which is the classical iteration for $\sqrt a$.

This example is too simple for QFT, but it shows the central idea: Newton’s method solves the local linear problem that best approximates the nonlinear one.

## Newton’s method for variational equations

Suppose $u_*$ is a stationary point of an action or energy:

$$
\nabla S(u_*)=0.
$$

Then

$$
F(u)=\nabla S(u),
\qquad
J(u)=\nabla^2S(u).
$$

Newton’s step becomes

$$
\nabla^2S(u_n)\delta u_n=-\nabla S(u_n).
$$

If $S$ is convex near $u_*$, the Hessian is positive definite and the step points toward the minimum. If $S$ has saddle directions, the Hessian is indefinite. Newton’s method may still solve the stationarity equation, but it does not know whether the solution is stable.

This distinction matters for instantons, bounces, mean-field solutions, solitons, and saddle points of large-$N$ effective actions. The nonlinear solver can find the configuration; a fluctuation analysis tells you what kind of stationary point it is.

## Line search

A raw Newton step can be too large. A line-search method replaces

$$
u_{n+1}=u_n+\delta u_n
$$

by

$$
u_{n+1}=u_n+\alpha_n\delta u_n,
\qquad
0<\alpha_n\le1.
$$

The scalar $\alpha_n$ is chosen to reduce a merit function such as

$$
\Phi(u)=\frac12\|F(u)\|^2.
$$

A simple backtracking line search tries $\alpha=1$, then decreases $\alpha$ until the residual decreases sufficiently.

Line search is one form of **globalization**. It turns a locally fast method into a method that has a better chance of reaching the local convergence region from a mediocre initial guess.

In field theory, line searches are especially useful when the action has steep nonlinearities, when field amplitudes must remain in a physical range, or when a guessed update would destroy a constraint.

## Trust regions

A trust-region method chooses the step by solving a constrained local model:

$$
\min_{\delta u}\; m_n(\delta u)
\qquad
\text{subject to}\qquad
\|\delta u\|\le \Delta_n.
$$

For a least-squares residual, the local model might be

$$
m_n(\delta u)=\frac12\|F(u_n)+J(u_n)\delta u\|^2.
$$

The radius $\Delta_n$ measures how far we trust the linearization. If the step works, increase $\Delta_n$. If it fails, decrease $\Delta_n$.

Line search asks: “How far should I go along this direction?” Trust regions ask: “What direction should I choose inside the region where my model is believable?”

Trust-region methods are often more robust for poorly scaled problems, but each iteration may be more expensive.

## Quasi-Newton methods

Newton’s method requires solving with the Jacobian $J(u_n)$. For large systems this may be expensive or impossible to form explicitly. Quasi-Newton methods replace $J$ or $J^{-1}$ by an approximation updated from previous steps.

Let

$$
s_n=u_{n+1}-u_n,
\qquad
 y_n=F(u_{n+1})-F(u_n).
$$

A quasi-Newton approximation $B_n\approx J(u_n)$ is updated so that it satisfies the secant condition

$$
B_{n+1}s_n=y_n.
$$

For optimization problems, the BFGS update approximates the Hessian while preserving positive definiteness under suitable conditions. For general nonlinear equations, Broyden-type updates are common.

Quasi-Newton methods are attractive when exact Jacobians are unavailable, noisy, or too expensive. Their tradeoff is slower local convergence and more delicate behavior on constrained or ill-conditioned field-theory problems.

## Jacobian-free Newton–Krylov methods

In large-scale QFT numerics, the Jacobian matrix may be too large to store. A Krylov method can solve

$$
J(u_n)\delta u_n=-F(u_n)
$$

using only matrix-vector products. These can be approximated by finite differences:

$$
J(u)v\approx \frac{F(u+\epsilon v)-F(u)}{\epsilon}.
$$

This gives a Jacobian-free Newton–Krylov method. The outer iteration is Newton; the inner linear solve is Krylov; the Jacobian action is estimated by directional differences or automatic differentiation.

The catch is preconditioning. Without a good preconditioner, the Krylov iteration may stagnate. In discretized PDEs and lattice systems, preconditioners encode physical and geometric insight: approximate inverse Laplacians, multigrid components, block decompositions, gauge-fixing projections, or Schur complements.

## Least-squares residuals

Sometimes one solves an overdetermined or noisy system by minimizing

$$
\Phi(u)=\frac12\|F(u)\|^2.
$$

The gradient is

$$
\nabla \Phi(u)=J(u)^T F(u)
$$

in a real Euclidean inner product. The Gauss–Newton step solves

$$
J(u)^TJ(u)\delta u=-J(u)^TF(u).
$$

This is Newton’s method for $\Phi$ with second-derivative terms of $F$ dropped. It is excellent when the residual is small and $J$ has full rank, but it can be poor near singular Jacobians or when the residual cannot be made small.

In data-fitting or inverse problems, least-squares language is natural. In QFT saddle equations, it must be used carefully: a small least-squares residual is not the same as finding the correct physical solution if constraints, symmetries, or gauge redundancies are mishandled.

## Constraints

Many nonlinear problems include constraints:

$$
F(u)=0,
\qquad
C(u)=0.
$$

Examples include fixed normalization, fixed charge, gauge conditions, unit-vector sigma-model fields, orthogonality constraints, and determinant constraints.

One can introduce Lagrange multipliers and solve

$$
\nabla_u \mathcal L(u,\lambda)=0,
\qquad
C(u)=0,
$$

or use a parameterization that enforces the constraint automatically. For example, a unit vector $n\in S^{N-1}$ can be updated by projecting steps onto the tangent space and then retracting back to the sphere.

A common numerical mistake is to solve the unconstrained equation and then project the answer. That can work for small corrections, but it is not equivalent to solving the constrained stationarity problem.

## Gauge redundancy and zero modes

Gauge theories create a special kind of constraint problem. If an equation is gauge invariant, then whole gauge orbits of configurations represent the same physical point. The Jacobian has zero modes along gauge directions.

A Newton step may then be nonunique:

$$
J\delta u=-F
$$

has infinitely many solutions or none without a gauge condition, projection, or quotient construction.

Practical remedies include:

| Issue | Typical numerical response |
|---|---|
| Gauge zero modes | gauge fixing or projection away from vertical directions |
| Global symmetry zero modes | collective coordinates or orthogonality constraints |
| Translational zero modes of solitons | pinning condition or moduli treatment |
| Negative modes of bounces | constrained saddle search rather than minimization |
| Redundant parameterization | reparameterization or regularization |

Zero modes are not numerical annoyances. They are physics. The solver should respect them rather than accidentally remove them.

## Continuation methods

Suppose the equation depends on a parameter $\lambda$:

$$
F(u,\lambda)=0.
$$

If a solution is known at $\lambda_0$, one can use it as the initial guess at $\lambda_0+\Delta\lambda$. This is parameter continuation.

A more robust method treats $u$ and $\lambda$ together and follows the solution curve. Differentiating gives

$$
F_u(u,\lambda)\frac{du}{d\lambda}+F_\lambda(u,\lambda)=0.
$$

If $F_u$ is invertible, this predicts the tangent direction. Near turning points, pseudo-arclength continuation is better because $\lambda$ may fail as a coordinate on the solution branch.

Continuation is invaluable in QFT problems with multiple phases or branches: mean-field equations, soliton families, gap equations, nonlinear eigenvalue problems, and saddle points across parameter space.

## Multiple roots and metastability

A nonlinear equation may have many roots. Which one the solver finds depends on the initial guess, damping, continuation path, and constraints.

For a potential $V(u)$ with several stationary points, solving

$$
V'(u)=0
$$

finds minima, maxima, and saddles. In field theory, these may correspond to stable vacua, metastable vacua, bounces, sphalerons, solitons, or unphysical artifacts.

Therefore a nonlinear solve should usually be followed by classification:

$$
\text{solve }F(u)=0
\quad\Longrightarrow\quad
\text{analyze spectrum of }J(u_*).
$$

Positive eigenvalues of a Hessian indicate local stability for a minimum. Negative modes signal instability or saddle directions. Zero modes signal symmetry, constraint, or degeneracy.

## Stopping criteria

A solver needs stopping criteria. Common tests are:

$$
\|F(u_n)\|\le \varepsilon_F,
$$

$$
\|u_{n+1}-u_n\|\le \varepsilon_u(1+\|u_n\|),
$$

and, for minimization,

$$
|S(u_{n+1})-S(u_n)|\le \varepsilon_S(1+|S(u_n)|).
$$

No single criterion is enough. A tiny step can mean convergence, but it can also mean stagnation. A small residual can mean success, but it can also be a consequence of poor scaling. A stable action value can hide large changes in irrelevant directions.

A trustworthy numerical result reports residuals, step sizes, discretization dependence, and sensitivity to tolerances.

## Scaling and nondimensionalization

Nonlinear solvers are sensitive to scale. If one component of $u$ is naturally $10^{12}$ and another is $10^{-6}$, the Euclidean norm of the residual may be meaningless.

Good practice is to nondimensionalize variables and equations so that typical components are order one. In QFT this means respecting physical dimensions. If fields, couplings, and coordinates carry units, rescale them before handing them to a generic numerical algorithm.

For example, in a scalar theory with mass scale $m$, write

$$
\tilde x=mx,
$$

and scale the field by its natural engineering dimension. The resulting equations are easier to solve and easier to compare across parameter values.

## Example: mean-field gap equation

A simple self-consistency equation has the form

$$
m^2=m_0^2+\lambda I(m^2),
$$

where $I$ is a regulated loop integral or mode sum. Define

$$
F(M)=M-m_0^2-\lambda I(M),
\qquad
M=m^2.
$$

Newton’s method gives

$$
M_{n+1}=M_n-
\frac{M_n-m_0^2-\lambda I(M_n)}
{1-\lambda I'(M_n)}.
$$

If $1-\lambda I'(M_n)$ becomes small, the update can become huge. Physically, this may signal proximity to a critical point or instability of the assumed phase. Numerically, it calls for damping, continuation, or a reformulation of the problem.

## Example: nonlinear lattice field equation

Consider a one-dimensional discretized $\phi^4$ energy

$$
E[\phi]
=\sum_i a\left[
\frac12\left(\frac{\phi_{i+1}-\phi_i}{a}\right)^2
+\frac{m^2}{2}\phi_i^2+\frac{\lambda}{4}\phi_i^4
\right].
$$

The stationarity equation is

$$
F_i(\phi)
=-\frac{\phi_{i+1}-2\phi_i+\phi_{i-1}}{a^2}
+m^2\phi_i+\lambda\phi_i^3=0,
$$

up to boundary conventions.

The Jacobian is sparse:

$$
J_{ij}
=\left(\frac{2}{a^2}+m^2+3\lambda\phi_i^2\right)\delta_{ij}
-\frac{1}{a^2}(\delta_{i,j+1}+\delta_{i,j-1}).
$$

This is the typical structure of nonlinear field equations: a sparse differential operator plus a local nonlinear term.

## Validation checklist

A nonlinear solve in QFT should not be trusted just because a library returned “success.” Check:

| Check | Why it matters |
|---|---|
| residual norm | verifies the equation is solved |
| independent initial guesses | detects multiple roots and basins |
| continuation history | distinguishes smooth branches from jumps |
| constraint violation | catches drift off the physical manifold |
| symmetry identities | detects broken exact symmetries |
| discretization refinement | separates continuum physics from grid artifacts |
| fluctuation spectrum | classifies minima, saddles, and zero modes |
| conserved quantities | tests real-time or Hamiltonian dynamics |

The best numerical solvers are not just algorithms. They are experiments with internal consistency checks.

## Common pitfalls

### Treating convergence as correctness

A solver can converge to the wrong branch, a gauge copy, a discretization artifact, or a local saddle that is irrelevant to the physics question. Convergence is necessary, not sufficient.

### Using Newton without globalization

Raw Newton steps can explode far from a root. Line searches, trust regions, damping, and continuation are not training wheels; they are often the difference between a calculation and a fireworks display.

### Ignoring zero modes

If the Jacobian has symmetry zero modes, the linear solve is singular for a good reason. Fix the symmetry, project the zero modes, or introduce collective coordinates. Do not simply add a tiny diagonal term and call it physics.

### Solving dimensionful equations with bad scaling

Poor scaling can make residual norms meaningless and linear solves ill-conditioned. Nondimensionalize before diagnosing an algorithm.

### Forgetting that nonlinear equations have multiple solutions

Mean-field, saddle-point, and soliton equations usually have branches. A single initial guess does not map the solution space.

## Exercises

### Exercise 1: Newton convergence for a simple root

Let $f(x)=x^2-a$ with $a>0$. Derive Newton’s iteration and show that if $x_n=\sqrt a+e_n$, then the leading error obeys

$$
e_{n+1}=\frac{e_n^2}{2\sqrt a}+O(e_n^3).
$$

<details><summary><strong>Solution</strong></summary>

Newton’s method gives

$$
x_{n+1}=x_n-\frac{x_n^2-a}{2x_n}
=\frac12\left(x_n+\frac{a}{x_n}\right).
$$

Set $s=\sqrt a$ and $x_n=s+e_n$. Then

$$
x_{n+1}-s
=\frac12\left(s+e_n+\frac{s^2}{s+e_n}\right)-s.
$$

Use

$$
\frac{s^2}{s+e_n}=s\left(1+\frac{e_n}{s}\right)^{-1}
=s-e_n+\frac{e_n^2}{s}+O(e_n^3).
$$

Therefore

$$
e_{n+1}
=\frac12\left(s+e_n+s-e_n+\frac{e_n^2}{s}\right)-s+O(e_n^3)
=\frac{e_n^2}{2s}+O(e_n^3).
$$

Thus the convergence is quadratic near the root.

</details>

### Exercise 2: Jacobian for a lattice phi-fourth equation

For

$$
F_i(\phi)
=-\frac{\phi_{i+1}-2\phi_i+\phi_{i-1}}{a^2}
+m^2\phi_i+\lambda\phi_i^3,
$$

compute $J_{ij}=\partial F_i/\partial \phi_j$.

<details><summary><strong>Solution</strong></summary>

Differentiate term by term. The derivative of the local nonlinear term is

$$
\frac{\partial}{\partial\phi_j}(m^2\phi_i+\lambda\phi_i^3)
=(m^2+3\lambda\phi_i^2)\delta_{ij}.
$$

The second-difference term gives

$$
-\frac{1}{a^2}
(\delta_{i+1,j}-2\delta_{ij}+\delta_{i-1,j}).
$$

Therefore

$$
J_{ij}
=\left(\frac{2}{a^2}+m^2+3\lambda\phi_i^2\right)\delta_{ij}
-\frac{1}{a^2}(\delta_{i+1,j}+\delta_{i-1,j}).
$$

Equivalently, after relabeling Kronecker deltas,

$$
J_{ij}
=\left(\frac{2}{a^2}+m^2+3\lambda\phi_i^2\right)\delta_{ij}
-\frac{1}{a^2}(\delta_{i,j+1}+\delta_{i,j-1}).
$$

</details>

### Exercise 3: Damped fixed-point convergence

Let $u_*=G(u_*)$ and suppose $G'(u_*)=q$. The damped iteration is

$$
u_{n+1}=(1-\omega)u_n+\omega G(u_n).
$$

Find the local linear convergence factor.

<details><summary><strong>Solution</strong></summary>

Let $e_n=u_n-u_*$. Expand

$$
G(u_n)=G(u_*+e_n)=u_*+q e_n+O(e_n^2).
$$

Then

$$
u_{n+1}-u_*
=(1-\omega)e_n+\omega q e_n+O(e_n^2).
$$

Thus the local convergence factor is

$$
q_\omega=1-\omega+\omega q=1-\omega(1-q).
$$

The iteration converges locally if

$$
|1-\omega(1-q)|<1.
$$

</details>

### Exercise 4: Least-squares normal equation

Let

$$
\Phi(u)=\frac12F(u)^TF(u)
$$

for $F:\mathbb R^N\to\mathbb R^M$. Show that

$$
\nabla\Phi(u)=J(u)^TF(u).
$$

<details><summary><strong>Solution</strong></summary>

In components,

$$
\Phi(u)=\frac12\sum_{a=1}^M F_a(u)^2.
$$

Differentiate with respect to $u_i$:

$$
\frac{\partial\Phi}{\partial u_i}
=\sum_a F_a(u)\frac{\partial F_a}{\partial u_i}.
$$

With $J_{ai}=\partial F_a/\partial u_i$, this is

$$
(\nabla\Phi)_i=(J^TF)_i.
$$

Therefore

$$
\nabla\Phi=J^TF.
$$

</details>

## References

- Deuflhard, *Newton Methods for Nonlinear Problems*.
- Kelley, *Iterative Methods for Linear and Nonlinear Equations*.
- Nocedal and Wright, *Numerical Optimization*.
- Saad, *Iterative Methods for Sparse Linear Systems*.
- Press, Teukolsky, Vetterling, and Flannery, *Numerical Recipes*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Altland and Simons, *Condensed Matter Field Theory*.

## Version history

- **2026-06-27:** First polished draft. Introduces residuals, fixed-point iteration, Newton methods, globalization, quasi-Newton methods, Jacobian-free Newton–Krylov ideas, constraints, gauge zero modes, continuation, validation, examples, and exercises.
