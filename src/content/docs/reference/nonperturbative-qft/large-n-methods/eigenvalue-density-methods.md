---
title: "Eigenvalue-Density Methods"
description: "Explains continuum eigenvalue-density methods in large-N matrix models, including Coulomb-gas saddles, resolvents, cuts, endpoint conditions, and observables."
sidebar:
  label: "Eigenvalue-Density Methods"
  order: 10
level: Advanced
status: "Polished draft"
source: "Mariño; Brézin–Itzykson–Parisi–Zuber; Mehta; Eynard; standard matrix-model and random-matrix literature."
topics:
  - eigenvalue density
  - matrix models
  - large-N methods
  - resolvent
  - spectral curve
  - Coulomb gas
  - saddle equations
  - random matrices
  - matrix model phases
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - eigenvalue-density-methods
  - matrix-models
  - resolvent-methods
  - spectral-curves
researchStatus:
  established:
    - "For Hermitian one-matrix models with suitable potentials, the planar large-N limit is captured by a continuum eigenvalue density determined by a singular integral saddle equation or equivalently by an analytic resolvent."
  active:
    - "The same language appears in localization matrix models, non-Hermitian ensembles, multi-matrix models, holographic saddles, and real-time matrix dynamics, where the correct contour, support, and nonperturbative completion can be model-dependent."
---

## Summary

**Eigenvalue-density methods replace $N$ interacting eigenvalues by a continuous distribution.** They are the workhorse of large-$N$ matrix models. Instead of trying to track each eigenvalue $\lambda_i$, one studies

$$
\rho(\lambda)=\frac1N\sum_{i=1}^N\delta(\lambda-\lambda_i),
\qquad
\int d\lambda\,\rho(\lambda)=1.
$$

At $N=\infty$, the density usually becomes a smooth function supported on one or more intervals. Its saddle equation is a singular integral equation. The most efficient way to solve it is often to introduce the **resolvent**

$$
\omega(z)=\int d\lambda\,\frac{\rho(\lambda)}{z-\lambda},
$$

whose discontinuity across its branch cuts reconstructs $\rho$. The payoff is huge: the planar free energy, moments, Wilson-loop-like matrix observables, phase transitions, and double-scaling limits all become questions about the geometry of cuts in the complex plane.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Eigenvalue density and resolvent: eigenvalues spread into a continuum cut, the density is recovered as a discontinuity of the resolvent, and moments come from the large-z expansion.](/figures/nonperturbative-qft/eigenvalue-density-resolvent.svg)

<figcaption>

At finite $N$, the eigenvalues are points. At large $N$, they form a density $\rho(\lambda)$ on one or more cuts. The resolvent $\omega(z)$ is analytic away from the cuts; its jump across a cut gives $\rho$, while its large-$z$ expansion gives the moments $\int d\lambda\,\rho(\lambda)\lambda^k$.

</figcaption>
</figure>

This page is a method page. It expands the shorter discussion in [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) and prepares the next page, [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/).

## Prerequisites

Read [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) and [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) first. You should also know [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) well enough to remember why matrix large $N$ has a $1/N^2$ expansion.

No advanced random-matrix theory is assumed. The needed ingredients are diagonalization of Hermitian matrices, the Vandermonde determinant, principal-value integrals, and elementary complex analysis.

## Core idea

The one-matrix model can be viewed as a gas of eigenvalues. For a Hermitian matrix integral

$$
Z_N=\int dM\,\exp\left[-\frac{N}{t}\operatorname{Tr}V(M)\right],
$$

diagonalization gives

$$
Z_N\propto \int\prod_{i=1}^N d\lambda_i\,
\exp\left[-\frac{N}{t}\sum_i V(\lambda_i)
+2\sum_{i<j}\log|\lambda_i-\lambda_j|\right].
$$

The potential confines the eigenvalues; the Vandermonde determinant repels them. At large $N$, both effects are of order $N^2$, so the equilibrium configuration is a genuine saddle. The density is the large-$N$ collective coordinate.

The method has three steps:

1. write the effective action for $\rho$;
2. solve the singular saddle equation, usually through the resolvent;
3. compute observables from $\rho$ or from the analytic structure of $\omega(z)$.

The method is powerful because it turns a many-variable integral into a classical equilibrium problem.

## Setup and conventions

We use the Hermitian one-matrix normalization

$$
Z_N=\int dM\,\exp\left[-\frac{N}{t}\operatorname{Tr}V(M)\right],
$$

where $t$ is the large-$N$ parameter often called the ’t Hooft parameter in matrix-model language. Setting $t=1$ recovers the normalization used in many introductory formulas.

The eigenvalue density is normalized as

$$
\int_{\mathcal C}d\lambda\,\rho(\lambda)=1,
$$

where $\mathcal C=\operatorname{supp}\rho$ is the support. For a one-cut solution,

$$
\mathcal C=[a,b].
$$

The resolvent is

$$
\omega(z)=\int_{\mathcal C}d\lambda\,\frac{\rho(\lambda)}{z-\lambda}.
$$

Its large-$z$ behavior is fixed by normalization:

$$
\omega(z)=\frac1z+O(z^{-2}).
$$

For real eigenvalues, the density is recovered from the discontinuity

$$
\rho(x)=\frac{1}{2\pi i}
\left[\omega(x-i0)-\omega(x+i0)\right],
\qquad x\in\mathcal C.
$$

The sign convention here follows the definition $\omega(z)=\int \rho(\lambda)/(z-\lambda)$. If you use $1/(\lambda-z)$ instead, the discontinuity sign flips. This little sign is a certified gremlin.

## Density saddle equation

At large $N$, the effective action per $N^2$ is

$$
s[\rho]
=\frac1t\int d\lambda\,\rho(\lambda)V(\lambda)
-\int d\lambda d\mu\,\rho(\lambda)\rho(\mu)\log|\lambda-\mu|
+\ell\left(\int d\lambda\,\rho(\lambda)-1\right),
$$

where $\ell$ enforces normalization. Varying $\rho$ gives

$$
\frac1t V(x)-2\int d\mu\,\rho(\mu)\log|x-\mu|+\ell=0,
\qquad x\in\mathcal C.
$$

Differentiating along the support gives

$$
\frac1t V'(x)=2\,\mathcal P\int_{\mathcal C}d\mu\,\frac{\rho(\mu)}{x-\mu}.
$$

This is the central eigenvalue-density equation. It is a Hilbert-transform equation. The principal value is not optional: it removes the singular self-force of an eigenvalue on itself.

Outside the support, the undifferentiated equation becomes an inequality. Physically, the effective potential felt by an extra eigenvalue must be at least as large outside the filled cut as it is on the cut. This is the density version of saddle stability.

## Resolvent solution for one cut

For a one-cut saddle $[a,b]$, the resolvent has two boundary values on the cut. The sum of the two values reproduces the saddle equation:

$$
\omega(x+i0)+\omega(x-i0)=\frac1t V'(x),
\qquad x\in[a,b].
$$

The difference gives the density:

$$
\omega(x-i0)-\omega(x+i0)=2\pi i\rho(x).
$$

For polynomial $V$, one often writes

$$
\omega(z)=\frac{1}{2t}\left[V'(z)-M(z)\sqrt{(z-a)(z-b)}\right],
$$

where $M(z)$ is a polynomial fixed by requiring

$$
\omega(z)=\frac1z+O(z^{-2})
$$

as $z\to\infty$. The endpoints $a,b$ are also fixed by this large-$z$ condition. Equivalently, they are fixed by the normalization and moment constraints.

The associated spectral curve is commonly written

$$
y(z)=V'(z)-2t\omega(z)
=M(z)\sqrt{(z-a)(z-b)}.
$$

The word “curve” is not ornamental. The branch cuts of this algebraic function encode the density, the planar free energy, and the analytic continuation data.

## Minimal example: Gaussian model

Take

$$
V(x)=\frac12x^2.
$$

The one-cut solution is symmetric, so the support is $[-2\sqrt t,2\sqrt t]$. The resolvent is

$$
\omega(z)=\frac{1}{2t}\left(z-\sqrt{z^2-4t}\right),
$$

where the branch is chosen so that $\omega(z)\sim1/z$ at infinity. The density is

$$
\rho(x)=\frac{1}{2\pi t}\sqrt{4t-x^2},
\qquad |x|\le2\sqrt t.
$$

This is the Wigner semicircle law in this normalization. Notice the endpoint behavior

$$
\rho(x)\sim \sqrt{2\sqrt t-|x|}.
$$

That square-root edge is generic for regular one-cut saddles. Higher-order endpoint zeros require tuning and are the gateway to multicritical and double-scaling behavior.

## Observables from the density

The simplest observables are moments:

$$
\frac1N\left\langle\operatorname{Tr}M^k\right\rangle
\longrightarrow
\int d\lambda\,\rho(\lambda)\lambda^k.
$$

The resolvent packages all of them:

$$
\omega(z)=\frac1z+\frac{m_1}{z^2}+\frac{m_2}{z^3}+\cdots,
\qquad
m_k=\int d\lambda\,\rho(\lambda)\lambda^k.
$$

For exponential observables,

$$
\frac1N\left\langle\operatorname{Tr}e^{sM}\right\rangle
\longrightarrow
\int d\lambda\,\rho(\lambda)e^{s\lambda}.
$$

This is why the same technology appears in supersymmetric localization: after localization, certain QFT observables reduce to matrix-model averages, and at large $N$ those averages are governed by an eigenvalue density. The physics of the original QFT is not automatically “random matrix physics,” but the mathematical saddle is the same kind of object.

## Multi-cut saddles and filling fractions

A one-cut solution is not always the correct saddle. If the potential has several wells, the support may split:

$$
\operatorname{supp}\rho=\bigcup_{\alpha=1}^{s}[a_\alpha,b_\alpha].
$$

The filling fractions are

$$
\nu_\alpha=\int_{a_\alpha}^{b_\alpha}d\lambda\,\rho(\lambda),
\qquad
\sum_{\alpha=1}^{s}\nu_\alpha=1.
$$

Different filling fractions can describe different saddle sectors. In a symmetric double well, for example, a saddle with half the eigenvalues in each well is not the same object as a saddle with all eigenvalues in one well. At finite $N$, eigenvalue tunneling between cuts can be exponentially suppressed in $N$ and is invisible in the ordinary $1/N$ expansion.

The practical warning is: solving the local resolvent equation is not enough. One must also specify the cut structure, filling fractions, contour, and stability conditions.

## Endpoint behavior and criticality

Near a regular endpoint $b$, a one-cut density behaves as

$$
\rho(x)\sim (b-x)^{1/2}.
$$

A critical point occurs when the density develops a higher-order zero, schematically

$$
\rho(x)\sim (b-x)^{m+1/2},
$$

or when two cuts collide. Such critical points signal that the usual smooth density approximation is becoming sensitive to edge fluctuations. That is exactly where double-scaling limits live.

In ordinary large $N$, one first takes $N\to\infty$ at fixed couplings. In a double-scaling limit, one lets $N\to\infty$ while tuning the couplings toward a critical point so that the edge region remains resolved. The next page explains why that keeps infinitely many corrections alive.

## Checks and diagnostics

A proposed eigenvalue-density solution should pass these checks.

| Check | What to verify |
|---|---|
| Normalization | $\int d\lambda\,\rho(\lambda)=1$. |
| Positivity | $\rho(\lambda)\ge0$ on the chosen physical support. |
| Large-$z$ behavior | $\omega(z)=1/z+O(z^{-2})$. |
| Saddle equation | $\omega_+(x)+\omega_-(x)=V'(x)/t$ on the support. |
| Stability | The effective potential outside the support does not undercut the filled cut. |
| Symmetry | If $V(x)$ is even and the saddle preserves the symmetry, $\rho(x)$ should be even. |
| Limits | As $t\to0$, the support should collapse toward minima of $V$, unless the limit is singular. |

These checks catch most algebraic mistakes. They also catch a surprisingly common conceptual error: choosing the wrong branch of the square root.

## Common pitfalls

**Forgetting the Vandermonde determinant.** Without the Vandermonde factor, all eigenvalues would independently sit at minima of $V$. The continuum support is caused by logarithmic eigenvalue repulsion.

**Solving the equation but not the support problem.** The resolvent equation needs branch cuts, endpoint conditions, and filling fractions. A formula for $\omega(z)$ is not a physical solution until these data are fixed.

**Choosing the wrong branch at infinity.** The branch of the square root must make $\omega(z)\sim1/z$. A wrong branch can produce a beautifully written density that is negative or incorrectly normalized.

**Treating every matrix model as a gauge theory.** Matrix models share the planar and eigenvalue grammar of gauge theories, but a zero-dimensional matrix integral is not Yang–Mills. The physical interpretation comes from the model being represented.

**Equating the planar density with the full answer.** The density gives leading large-$N$ data. Finite-$N$ corrections, endpoint fluctuations, eigenvalue instantons, and double-scaling limits can be essential.

## Relations to other pages

- [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) introduces the same objects at a broader level.
- [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) explains why density saddles are steepest-descent problems.
- [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) gives the ribbon-graph interpretation of the same $1/N^2$ expansion.
- [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/) explains what happens when the density becomes critical.
- [Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) gives the gauge-theory analogue of replacing all invariant observables by a classical large-$N$ object.

## Research status

**Established.** Hermitian one-matrix models at large $N$ are a mature subject. The eigenvalue-density saddle, resolvent, one-cut and multi-cut solutions, spectral curves, and planar expansion are standard tools.

**Established with model-specific interpretation.** In supersymmetric localization and related exact reductions, matrix-model densities compute genuine QFT observables. The matrix model is then not a metaphor; it is the reduced integral produced by the exact calculation.

**Active.** Non-Hermitian ensembles, time-dependent matrix models, multi-matrix models, eigenvalue instantons, holographic matrix integrals, and rigorous nonperturbative completions remain active. In these settings, contours and saddle dominance are often part of the physics, not an afterthought.

## Exercises

### Exercise 1: The finite-N saddle

Starting from

$$
S_{\rm eig}
=\frac{N}{t}\sum_i V(\lambda_i)-2\sum_{i<j}\log|\lambda_i-\lambda_j|,
$$

show that the finite-$N$ saddle equation is

$$
\frac{N}{t}V'(\lambda_i)=2\sum_{j\ne i}\frac{1}{\lambda_i-\lambda_j}.
$$

Then derive the continuum equation for $\rho$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate $S_{\rm eig}$ with respect to $\lambda_i$:

$$
\frac{\partial S_{\rm eig}}{\partial\lambda_i}
=\frac{N}{t}V'(\lambda_i)-2\sum_{j\ne i}\frac{1}{\lambda_i-\lambda_j}.
$$

Setting this to zero gives the finite-$N$ saddle. Dividing by $N$ and replacing

$$
\frac1N\sum_{j\ne i}f(\lambda_j)
\to
\int d\mu\,\rho(\mu)f(\mu)
$$

gives

$$
\frac1tV'(x)
=2\,\mathcal P\int d\mu\,\frac{\rho(\mu)}{x-\mu}.
$$

The principal value is needed because $f(\mu)=1/(x-\mu)$ is singular at $\mu=x$.

</details>

### Exercise 2: Semicircle moments

For

$$
\rho(x)=\frac{1}{2\pi}\sqrt{4-x^2},
\qquad |x|\le2,
$$

compute

$$
\int_{-2}^2dx\,\rho(x)x^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Use $x=2\sin\theta$. Then

$$
\int_{-2}^2dx\,\frac{x^2}{2\pi}\sqrt{4-x^2}
=\frac{1}{2\pi}\int_{-\pi/2}^{\pi/2}
(4\sin^2\theta)(2\cos\theta)(2\cos\theta)d\theta.
$$

Thus

$$
=\frac{8}{\pi}\int_{-\pi/2}^{\pi/2}\sin^2\theta\cos^2\theta\,d\theta
=\frac{8}{\pi}\cdot\frac{\pi}{8}=1.
$$

So the second moment is $1$.

</details>

### Exercise 3: Resolvent discontinuity

Assume

$$
\omega(z)=\frac12\left(z-\sqrt{z^2-4}\right)
$$

with the branch chosen so that $\sqrt{z^2-4}\sim z$ at infinity. Show that the discontinuity of $\omega$ on $[-2,2]$ gives the semicircle density.

<details>
<summary><strong>Solution</strong></summary>

For $x\in(-2,2)$,

$$
\sqrt{x^2-4+i0}=+i\sqrt{4-x^2},
\qquad
\sqrt{x^2-4-i0}=-i\sqrt{4-x^2},
$$

with the stated branch convention. Therefore

$$
\omega(x-i0)-\omega(x+i0)
=\frac12\left[x+i\sqrt{4-x^2}-x+i\sqrt{4-x^2}\right]
=i\sqrt{4-x^2}.
$$

Using

$$
\rho(x)=\frac{1}{2\pi i}[\omega(x-i0)-\omega(x+i0)]
$$

gives

$$
\rho(x)=\frac{1}{2\pi}\sqrt{4-x^2}.
$$

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapter on Hermitian matrix models.
- E. Brézin, C. Itzykson, G. Parisi, and J.-B. Zuber, “Planar Diagrams,” for the classic matrix-model planar expansion.
- M. L. Mehta, *Random Matrices*, for the random-matrix background.

### Deeper references

- B. Eynard, *Counting Surfaces*, for resolvents, spectral curves, loop equations, and topological recursion.
- P. Di Francesco, P. Ginsparg, and J. Zinn-Justin, “2D Gravity and Random Matrices,” for matrix models, criticality, and double scaling.
- V. Pestun et al., *Localization Techniques in Quantum Field Theories*, for matrix models arising from supersymmetric localization.

## Version history

- **2026-06-28:** Initial polished page on continuum eigenvalue densities, resolvents, cuts, endpoint behavior, checks, and observables.
