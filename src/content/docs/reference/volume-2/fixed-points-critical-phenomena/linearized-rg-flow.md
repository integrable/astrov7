---
title: "Linearized RG Flow"
description: "Derives the linearized renormalization group near a fixed point and explains scaling fields, eigenoperators, relevant directions, critical surfaces, and correction-to-scaling exponents."
sidebar:
  label: "Linearized RG Flow"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Weinberg 1996, ch. 18; Coleman 1985, Dilatations; Cardy 1996; Goldenfeld 1992."
topics:
  - linearized RG flow
  - RG eigenvalues
  - scaling fields
  - relevant operators
  - irrelevant operators
  - critical surface
canonicalTopics:
  - linearized-rg-flow
  - rg-eigenvalues
  - scaling-fields
  - critical-surface
researchStatus:
  established:
    - "Linearizing RG flow near a fixed point gives scaling fields, RG eigenvalues, relevant and irrelevant directions, and the standard derivation of critical exponents such as $\nu=1/y_t$."
  active:
    - "In strongly coupled theories, extracting the linearized spectrum and disentangling nearly marginal, redundant, dangerously irrelevant, and symmetry-breaking perturbations can require bootstrap, lattice, FRG, large-N, or exact methods."
---

## Summary

Near a fixed point, RG flow can be linearized. This is the step that turns the geometric statement “there is a fixed point” into quantitative predictions for critical exponents and scaling laws.

Use an infrared RG time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

so $\ell$ increases as short-distance degrees of freedom are coarse-grained away. Let $g_*^i$ be a fixed point and write

$$
\delta g^i=g^i-g_*^i.
$$

The RG equation has the form

$$
\frac{d\delta g^i}{d\ell}
=M^i{}_j\delta g^j+O(\delta g^2),
\qquad
M^i{}_j=\left.\frac{\partial \mathcal B^i}{\partial g^j}\right|_{g_*},
$$

where $d g^i/d\ell=\mathcal B^i(g)$. Diagonalizing $M$ gives scaling fields $u_a$:

$$
\frac{d u_a}{d\ell}=y_a u_a+O(u^2),
\qquad
u_a(\ell)\simeq u_a(0)e^{y_a\ell}.
$$

In this IR convention:

| Direction | Eigenvalue | Long-distance behavior |
|---|---:|---|
| relevant | $y_a>0$ | grows away from the fixed point |
| irrelevant | $y_a<0$ | shrinks toward the fixed point |
| marginal | $y_a=0$ | decided by nonlinear terms |

For a perturbation by a local scaling operator,

$$
S=S_*+u_a\int d^d x\,\mathcal O_a(x),
$$

the linear RG eigenvalue is

$$
y_a=d-\Delta_a.
$$

This one formula is the bridge between operator dimensions and critical phenomena.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Linearized RG flow near a fixed point showing the critical surface, relevant direction, irrelevant direction, and fixed point](/figures/renormalization-rg-eft/fixed-point-linearized-flow.svg)

<figcaption>

Linearized RG flow near a fixed point. Points on the critical surface flow into $g_*$ along irrelevant directions. Perturbations normal to that surface are relevant and grow under IR coarse graining. Linearization turns this local geometry into eigenvalues $y_a$, which become scaling exponents.

</figcaption>
</figure>

## Prerequisites

You should know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/).

The only mathematical prerequisite is linearizing a vector field near a zero and diagonalizing the resulting matrix. The physics is in interpreting the eigenvectors.

## Core idea

A fixed point by itself says that the RG vector field vanishes. The linearized flow says how nearby theories depart from or approach it.

This local information is enormously powerful. It tells us:

- how many parameters must be tuned to reach criticality;
- which microscopic deformations are forgotten at long distances;
- which perturbations determine phases;
- how correlation lengths diverge;
- why critical exponents are universal.

The fixed point is the scale-invariant theory. The linearized eigenvectors are the allowed ways to leave it. The eigenvalues are the first critical exponents.

In good coordinates, the local RG flow looks like

$$
\frac{d u_a}{d\ell}=y_a u_a.
$$

The solution is exponential in RG time:

$$
u_a(\ell)=u_a(0)e^{y_a\ell}.
$$

Since a length scale grows as $e^\ell$ under coarse graining, this exponential in RG time is the origin of power laws in physical distance.

## Setup and conventions

This page uses IR RG time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

with

$$
\frac{d g^i}{d\ell}=\mathcal B^i(g).
$$

The relation to the renormalized convention $d g^i/dt=\beta^i(g)$ with $t=\log\mu$ is

$$
\mathcal B^i=-\beta^i
$$

when the sliding renormalization scale is identified with the Wilsonian cutoff. This sign is only a convention, but it matters when reading eigenvalues. In this page:

$$
y>0
\quad\text{means relevant toward the IR}.
$$

When this page uses the Wilson–Fisher epsilon expansion, it uses $d=4-\epsilon$, the critical-phenomena convention near the upper critical dimension. This is not the same notation choice as dimensional regularization with $d=4-2\epsilon$.

Let $g_*^i$ be a fixed point:

$$
\mathcal B^i(g_*)=0.
$$

Expand around it:

$$
g^i=g_*^i+\delta g^i.
$$

Then

$$
\frac{d\delta g^i}{d\ell}
=\mathcal B^i(g_*+\delta g)
=M^i{}_j\delta g^j+O(\delta g^2),
$$

where

$$
M^i{}_j=\left.\frac{\partial \mathcal B^i}{\partial g^j}\right|_{g_*}.
$$

The matrix $M$ is the stability matrix in IR time.

## Scaling fields

The original couplings $g^i$ are rarely the best coordinates near a fixed point. The best local coordinates are **scaling fields** $u_a$, chosen so that the linearized RG flow is diagonal:

$$
\frac{d u_a}{d\ell}=y_a u_a+O(u^2).
$$

At linear order, each scaling field evolves independently:

$$
u_a(\ell)=u_a(0)e^{y_a\ell}.
$$

The numbers $y_a$ are RG eigenvalues. The corresponding directions in theory space are eigenvectors of $M$:

$$
M^i{}_j v_a^j=y_a v_a^i.
$$

The original microscopic couplings are usually mixtures of scaling fields. For example, a lattice temperature parameter might be mostly the energy-density scaling field, plus smaller admixtures of irrelevant fields. This is why scaling behavior can have corrections: the relevant scaling field controls the leading singularity, while irrelevant admixtures decay only as powers.

### Scaling fields are not always individual Lagrangian couplings

A common mistake is to identify a coupling in a chosen Lagrangian with an RG eigen-direction. Sometimes that is approximately correct. Often it is not.

If operators mix under RG, then the eigenoperators are linear combinations. If two perturbations have the same symmetries, they can mix. If a perturbation is redundant because it can be removed by a field redefinition, it may appear in a Lagrangian while not changing physical observables. If a symmetry is imposed, some relevant directions may be absent from the allowed theory space.

The eigenvectors of the linearized RG flow are therefore physical local coordinates near the fixed point, not necessarily the first couplings written on a blackboard.

## Eigenoperators and scaling dimensions

At a fixed point, local operators can be chosen to have definite scaling dimensions. Suppose $\mathcal O_a$ is a scalar scaling operator with dimension $\Delta_a$. Perturb the fixed point by

$$
\delta S=u_a\int d^d x\,\mathcal O_a(x).
$$

Under a scale transformation $x\to b x$, the measure contributes $b^d$, while the operator contributes $b^{-\Delta_a}$. Therefore the coupling transforms as

$$
u_a\to b^{d-\Delta_a}u_a.
$$

With $b=e^\ell$, the linearized flow is

$$
\frac{d u_a}{d\ell}= (d-\Delta_a)u_a.
$$

Thus

$$
y_a=d-\Delta_a.
$$

This is the cleanest interpretation of relevance:

| Operator dimension | RG eigenvalue | Name |
|---:|---:|---|
| $\Delta_a<d$ | $y_a>0$ | relevant |
| $\Delta_a=d$ | $y_a=0$ | marginal |
| $\Delta_a>d$ | $y_a<0$ | irrelevant |

The engineering version of this table is only the Gaussian approximation. At an interacting fixed point, the full scaling dimension $\Delta_a$ includes anomalous contributions.

## Relevant directions and tuning

A relevant perturbation grows under IR flow. If $y_a>0$, then

$$
u_a(\ell)=u_a(0)e^{y_a\ell}
$$

eventually becomes order one unless $u_a(0)$ is tuned to zero.

This is why critical points require tuning. To land on the critical surface that flows into the fixed point, all relevant scaling fields must be set to their critical values. If a fixed point has $n_{\text{rel}}$ relevant directions, then the critical surface has codimension $n_{\text{rel}}$ in the full theory space, after imposing symmetries and removing redundant directions.

For the Ising universality class, the two most familiar relevant perturbations are:

| Perturbation | Physical name | Symmetry |
|---|---|---|
| energy operator | temperature-like perturbation | even under $\mathbb Z_2$ |
| spin operator | magnetic-field perturbation | odd under $\mathbb Z_2$ |

If one restricts to $\mathbb Z_2$-symmetric systems, the magnetic perturbation is forbidden. Then only the temperature-like perturbation must be tuned. Without that symmetry restriction, both must be tuned to reach the critical fixed point.

## Irrelevant directions and universality

An irrelevant perturbation shrinks under IR flow. If $y_a<0$, then

$$
u_a(\ell)=u_a(0)e^{-|y_a|\ell}.
$$

This is the mathematical core of universality. Microscopic systems differ by many irrelevant couplings, but those differences fade at long distances. What remains is the fixed-point data and the small number of relevant scaling fields.

Irrelevant does not mean nonexistent, unphysical, or never measurable. It means subleading near the fixed point. Irrelevant operators control corrections to scaling, lattice artifacts, finite-cutoff effects, and many EFT corrections.

If the leading irrelevant eigenvalue is

$$
y_{\text{irr}}=-\omega,
\qquad \omega>0,
$$

then corrections to scaling often appear as powers such as

$$
\xi^{-\omega}
$$

or, in finite-size systems,

$$
L^{-\omega}.
$$

The exponent $\omega$ is itself universal, although amplitudes multiplying these corrections are not.

## Marginal directions

A marginal perturbation has $y=0$ at linear order. Linearization alone cannot decide its fate. One must examine nonlinear terms:

$$
\frac{d u}{d\ell}=a u^2+b u^3+\cdots.
$$

Depending on these coefficients, the perturbation may be:

| Type | Behavior |
|---|---|
| exactly marginal | stays marginal and generates a line or manifold of fixed points |
| marginally relevant | grows slowly toward the IR |
| marginally irrelevant | shrinks slowly toward the IR |
| marginal with higher-order structure | requires more global or symmetry information |

Marginally irrelevant perturbations often produce logarithmic corrections to scaling. Marginally relevant perturbations can generate exponentially large correlation lengths, as in Berezinskii–Kosterlitz–Thouless-type flows.

This is why the word marginal is a warning label rather than a conclusion.

## Critical surface

The **critical surface** is the set of points that flow into a fixed point in the infrared. In linearized coordinates, it is locally given by setting all relevant scaling fields to zero:

$$
u_a=0
\qquad\text{for all relevant }a.
$$

The irrelevant scaling fields can be nonzero. They decay as the flow approaches the fixed point.

If there is one relevant perturbation, the critical surface has codimension one. If there are two, it has codimension two. Symmetries can reduce the number of tunings by forbidding some relevant perturbations.

The critical surface is sometimes called the stable manifold of the fixed point under IR flow. The word stable here means stable against irrelevant perturbations, not stable against every perturbation.

## Correlation length exponent

Linearized flow gives a quick derivation of the correlation length exponent. Suppose there is one relevant temperature-like scaling field $u_t$ with eigenvalue $y_t>0$:

$$
\frac{d u_t}{d\ell}=y_t u_t.
$$

The solution is

$$
u_t(\ell)=u_t(0)e^{y_t\ell}.
$$

The flow remains close to the fixed point until $u_t(\ell)$ becomes order one. Define $\ell_*$ by

$$
u_t(0)e^{y_t\ell_*}\sim1.
$$

Then

$$
e^{\ell_*}\sim |u_t(0)|^{-1/y_t}.
$$

The correlation length is the microscopic length multiplied by the coarse-graining factor at which the flow leaves the critical regime:

$$
\xi\sim a e^{\ell_*}.
$$

Therefore

$$
\xi\sim |u_t(0)|^{-1/y_t},
\qquad
\nu=\frac{1}{y_t}.
$$

This derivation is one of the triumphs of the RG. A measurable singular exponent is an eigenvalue of the linearized flow near a fixed point.

## Example: Wilson–Fisher near four dimensions

For the $O(N)$ model in $d=4-\epsilon$, a common dimensionless quartic coupling $u$ has beta function

$$
\beta_u=-\epsilon u+\frac{N+8}{6}u^2+O(u^3)
$$

in the renormalized convention. The Wilson–Fisher fixed point is

$$
u_*=\frac{6\epsilon}{N+8}+O(\epsilon^2).
$$

In the $u$ direction, the derivative of the renormalized beta function is

$$
\beta_u'(u_*)=\epsilon+O(\epsilon^2).
$$

Since IR time reverses the sign relative to $t=\log\mu$, the quartic direction is irrelevant at the Wilson–Fisher fixed point with

$$
y_u=-\epsilon+O(\epsilon^2).
$$

This gives the leading correction-to-scaling exponent

$$
\omega=\epsilon+O(\epsilon^2).
$$

The temperature-like relevant eigenvalue is

$$
y_t=2-\frac{N+2}{N+8}\epsilon+O(\epsilon^2),
$$

so

$$
\nu=\frac{1}{y_t}
=\frac{1}{2}+\frac{N+2}{4(N+8)}\epsilon+O(\epsilon^2).
$$

For $\epsilon=1$, this is only the beginning of the three-dimensional estimate, but it already shows the logic: critical exponents come from eigenvalues at the fixed point, not from fitting arbitrary powers.

## Corrections to scaling

Real systems are never exactly at the fixed point. Even after relevant perturbations are tuned, irrelevant perturbations are present. Let $u_i$ be the leading irrelevant scaling field with

$$
y_i=-\omega.
$$

Under coarse graining,

$$
u_i(\ell)=u_i(0)e^{-\omega\ell}.
$$

At a distance scale $r\sim a e^\ell$, this becomes

$$
u_i(r)\sim u_i(0)\left(\frac{a}{r}\right)^\omega.
$$

Thus observables have scaling forms such as

$$
G(r)=\frac{1}{r^{2\Delta}}
\left[ C_0+C_1\left(\frac{a}{r}\right)^\omega+\cdots\right]
$$

at criticality. The exponent $\omega$ is universal; the coefficient $C_1$ is not.

This explains why high-precision numerical or experimental analyses of critical phenomena must include correction-to-scaling terms. Ignoring them can bias estimates of leading critical exponents.

## Redundant directions

Some directions in theory space correspond to field redefinitions rather than new physics. For example, a small local redefinition

$$
\phi\to \phi+\epsilon F(\phi,\partial\phi,\ldots)
$$

can change the form of the action while leaving physical observables unchanged. The induced operators are called redundant operators or equation-of-motion operators, depending on context.

Redundant directions can appear in the stability matrix, but their eigenvalues should not be confused with physical critical exponents. A careful treatment of linearized RG distinguishes physical scaling operators from coordinate artifacts.

This is especially important in functional RG truncations, EFT operator bases, and gauge theories, where field redefinitions and gauge redundancies are not optional fine print.

## Common pitfalls

**Using the wrong RG time sign.** In the IR convention of this page, $y>0$ means relevant. In the UV convention $t=\log\mu$, the corresponding eigenvalue has the opposite sign when $\mu$ tracks the cutoff.

**Calling every Lagrangian coupling a scaling field.** Scaling fields diagonalize the linearized flow. Microscopic couplings are usually mixtures.

**Forgetting operator mixing.** If operators have the same quantum numbers, the stability matrix must be diagonalized in that subspace.

**Thinking marginal means harmless.** Marginal directions require nonlinear analysis. They can be exactly marginal, marginally relevant, or marginally irrelevant.

**Treating irrelevant as unobservable.** Irrelevant perturbations control corrections to scaling and finite-cutoff effects. In EFT they are often the leading measurable imprint of heavy physics.

**Ignoring symmetry restrictions.** A relevant operator forbidden by symmetry does not require tuning within the symmetric theory space. Break the symmetry, and the tuning problem can change.

## Relations to other pages

[Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) defines the fixed-point theory. This page studies the first neighborhood around it. [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) turns $y_t$, $y_h$, $\eta$, and related data into the standard exponent notation. [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) derives relations among those exponents. [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) explains why the same eigenvalue data recur in very different systems.

The Wilsonian page [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) gives the broader classification. The later Local Operators and OPE chapter develops operator mixing, anomalous-dimension matrices, redundant operators, and OPE data in more detail.

## Research status

Linearized RG flow near fixed points is established and is one of the basic tools of modern critical phenomena and QFT. Its predictions are tested through experiment, Monte Carlo simulation, conformal bootstrap, high-temperature expansions, epsilon expansions, large-N methods, and exact two-dimensional models.

Active questions include extracting spectra of relevant and irrelevant operators in strongly coupled theories, identifying emergent symmetries, treating nearly marginal operators, distinguishing physical from redundant directions in approximate RG schemes, and understanding dangerously irrelevant perturbations in systems where naive linearized relevance does not tell the whole story.

## Exercises

### Exercise 1: Solve the linearized flow

Let $u_1$ and $u_2$ obey

$$
\frac{d u_1}{d\ell}=2u_1,
\qquad
\frac{d u_2}{d\ell}=-u_2.
$$

Classify the two directions and solve for $u_1(\ell)$ and $u_2(\ell)$.

<details><summary><strong>Solution</strong></summary>

The solutions are

$$
u_1(\ell)=u_1(0)e^{2\ell},
\qquad
u_2(\ell)=u_2(0)e^{-\ell}.
$$

Since $\ell$ increases toward the infrared, $u_1$ grows and is relevant. The coupling $u_2$ shrinks and is irrelevant.

</details>

### Exercise 2: Derive the correlation length exponent

Assume a single relevant scaling field $u_t$ obeys

$$
\frac{d u_t}{d\ell}=y_t u_t,
\qquad y_t>0.
$$

Show that the correlation length exponent is $\nu=1/y_t$.

<details><summary><strong>Solution</strong></summary>

The solution is

$$
u_t(\ell)=u_t(0)e^{y_t\ell}.
$$

The flow exits the critical regime when $u_t(\ell_*)\sim1$, so

$$
e^{\ell_*}\sim |u_t(0)|^{-1/y_t}.
$$

Since lengths scale as $e^\ell$, the correlation length behaves as

$$
\xi\sim a e^{\ell_*}\sim |u_t(0)|^{-1/y_t}.
$$

Comparing with $\xi\sim |u_t(0)|^{-\nu}$ gives

$$
\nu=\frac1{y_t}.
$$

</details>

### Exercise 3: Relevance from operator dimension

In $d=3$, classify perturbations by scalar operators with dimensions $\Delta=1.2$, $\Delta=3$, and $\Delta=4.1$.

<details><summary><strong>Solution</strong></summary>

The RG eigenvalue is

$$
y=d-\Delta.
$$

For $\Delta=1.2$ in $d=3$,

$$
y=3-1.2=1.8>0,
$$

so the perturbation is relevant.

For $\Delta=3$,

$$
y=0,
$$

so the perturbation is marginal at linear order.

For $\Delta=4.1$,

$$
y=3-4.1=-1.1<0,
$$

so the perturbation is irrelevant.

</details>

### Exercise 4: Correction-to-scaling exponent

Suppose the leading irrelevant scaling field has eigenvalue $y_i=-0.8$. What correction-to-scaling exponent $\omega$ should appear in finite-size corrections?

<details><summary><strong>Solution</strong></summary>

By definition,

$$
y_i=-\omega.
$$

Thus

$$
\omega=0.8.
$$

Finite-size corrections often include powers such as

$$
L^{-\omega}=L^{-0.8},
$$

up to nonuniversal amplitudes and additional subleading corrections.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations."
- John Cardy, *Scaling and Renormalization in Statistical Physics*.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*.
- Michael E. Fisher, classic reviews on scaling theory and critical exponents.

## Version history

- 2026-06-17: First polished draft deriving linearized RG flow, scaling fields, critical surfaces, relevance, corrections to scaling, and $\nu=1/y_t$.
