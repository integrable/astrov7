---
title: "Relevant, Irrelevant, and Marginal Directions"
description: "Defines relevant, irrelevant, and marginal RG directions as eigen-directions of the linearized renormalization group near a fixed point, with their role in tuning, universality, and scaling limits."
sidebar:
  label: "Relevant/Irrelevant Directions"
  order: 4
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Wegner; Polchinski; exact and constructive RG literature"
topics:
  - relevant operators
  - irrelevant operators
  - marginal operators
  - RG fixed points
  - universality
canonicalTopics:
  - relevant-irrelevant-marginal
  - rg-fixed-points
  - rigorous-renormalization
researchStatus:
  established:
    - "Near a sufficiently controlled RG fixed point, perturbations can be classified by the eigenvalues of the linearized RG map."
  active:
    - "Marginal directions and dangerously irrelevant variables require nonlinear analysis and can invalidate naive dimensional conclusions."
---

## Summary

Relevant, irrelevant, and marginal directions are the tangent directions of theory space near an RG fixed point, classified by whether the renormalization group expands, contracts, or preserves them to first order.

Let $\mathcal R_b$ be an RG step with scale factor $b>1$, and let $g_*$ be a fixed point:

$$
\mathcal R_b(g_*)=g_*.
$$

For a small perturbation $h=g-g_*$, the linearized RG is

$$
h\longmapsto L_bh,
\qquad
L_b=D\mathcal R_b\big|_{g_*}.
$$

If $h_i$ is an eigen-direction with

$$
L_bh_i=b^{y_i}h_i,
$$

then

$$
\begin{array}{ccl}
y_i>0 &\Longrightarrow& \text{relevant},\\
y_i<0 &\Longrightarrow& \text{irrelevant},\\
y_i=0 &\Longrightarrow& \text{marginal at linear order}.
\end{array}
$$

For a local operator $\mathcal O_i$ of scaling dimension $\Delta_i$ in $d$ Euclidean dimensions, the corresponding coupling has RG exponent

$$
y_i=d-\Delta_i.
$$

This formula is simple, but its meaning is subtle. The dimensions $\Delta_i$ must be dimensions at the fixed point, not necessarily engineering dimensions. Marginal directions require nonlinear beta functions. Irrelevant directions may be “dangerously” irrelevant if some observable depends singularly on them.

## Prerequisites

Read [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) and [Scaling Limits](/rigorous-qft/rigorous-renormalization-rg/scaling-limits/) first. You should also know the cutoff-measure viewpoint in [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/), the role of ultraviolet regulators in [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/), and the constructive endpoint in [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

## Core idea

The renormalization group is usually infinite-dimensional. Integrating out a scale produces all interactions compatible with the cutoff and symmetries. Yet near a fixed point, much of the large-scale behavior is controlled by a finite amount of data because the linearized RG has only finitely many expanding directions in many important examples.

This is the reason critical phenomena can be universal. Microscopic Hamiltonians or actions may contain many couplings, but under repeated coarse-graining the irrelevant directions shrink. Only the relevant directions need tuning to land near the fixed point, while marginal directions need a separate nonlinear analysis.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Linearized RG directions](/figures/rigorous-qft/rg-linearized-directions.svg)

<figcaption>

Near a fixed point, the linearized RG expands relevant directions, contracts irrelevant directions, and leaves marginal directions undecided at first order. The critical surface is locally tangent to the stable directions.

</figcaption>
</figure>

A good way to remember the classification is:

$$
\text{relevant}=\text{must tune},
\qquad
\text{irrelevant}=\text{forgets microscopic detail},
\qquad
\text{marginal}=\text{ask the next term}.
$$

This slogan is useful, but it is only a slogan. A rigorous RG proof must specify the space of interactions, the norm, the fixed point, the linearized map, and the nonlinear estimates that justify the classification.

## Setup and conventions

We use Euclidean dimension $d$ and scale factor $b>1$. A local perturbation of a fixed-point action or effective interaction is written schematically as

$$
S=S_*+
\sum_i g_i\int d^dx\,\mathcal O_i(x).
$$

Under an RG step, the couplings transform as

$$
g_i' = \beta_i^{(b)}(g),
$$

where $\beta^{(b)}$ denotes the finite-step RG map, not necessarily the infinitesimal beta function. Linearizing at $g=0$ gives

$$
g_i'=\sum_j M_{ij}g_j+O(g^2).
$$

If the basis has been diagonalized,

$$
g_i'=b^{y_i}g_i+O(g^2).
$$

The exponent $y_i$ is the RG eigenvalue exponent. Many physics references call $y_i$ the scaling dimension of the coupling, while $\Delta_i=d-y_i$ is the scaling dimension of the operator. To avoid ambiguity, this page uses:

| Symbol | Meaning |
|---|---|
| $\Delta_i$ | Scaling dimension of the operator $\mathcal O_i$. |
| $y_i$ | RG exponent of its coupling. |
| $b^{y_i}$ | Linearized finite-step eigenvalue. |

For an infinitesimal RG time $\ell=\log b$, one writes

$$
\frac{dg_i}{d\ell}=y_i g_i+O(g^2).
$$

The sign of $y_i$ is the sign that matters.

## Engineering dimensions at the Gaussian fixed point

At the Gaussian fixed point of a scalar field in $d$ Euclidean dimensions, the free field has engineering dimension

$$
\Delta_\phi^{(0)}=\frac{d-2}{2}.
$$

For a monomial $\mathcal O=\phi^n$ without derivatives,

$$
\Delta_{\phi^n}^{(0)}=n\frac{d-2}{2},
\qquad
 y_{\phi^n}=d-n\frac{d-2}{2}.
$$

Thus the coupling of $\phi^4$ has

$$
y_{\phi^4}=d-2(d-2)=4-d.
$$

This recovers the standard classification:

| Operator | Coupling exponent near Gaussian fixed point | Classification |
|---|---:|---|
| $1$ | $d$ | relevant vacuum-energy direction |
| $\phi$ | $(d+2)/2$ | relevant if symmetry allows it |
| $\phi^2$ | $2$ | relevant mass direction |
| $\phi^4$ | $4-d$ | relevant for $d<4$, marginal at $d=4$, irrelevant for $d>4$ |
| $\phi^6$ | $6-2d$ | irrelevant for $d>3$, marginal at $d=3$ |
| $(\partial\phi)^2$ | $0$ before field normalization conventions | kinetic normalization / redundant or marginal coordinate |

Derivative operators are classified similarly. Each derivative contributes one unit of dimension. For example,

$$
\mathcal O=(\partial\phi)^2\phi^2
$$

has Gaussian dimension

$$
\Delta_{(\partial\phi)^2\phi^2}^{(0)}
=2+4\frac{d-2}{2}=2d-2,
$$

so its coupling exponent is

$$
y=2-d.
$$

It is irrelevant for $d>2$ near the Gaussian fixed point.

## Scaling dimensions at an interacting fixed point

The Gaussian formulas are only the first approximation. At an interacting fixed point, operators acquire anomalous dimensions. The field dimension becomes

$$
\Delta_\phi=\frac{d-2+\eta}{2},
$$

where $\eta$ is the anomalous-dimension exponent. More generally, the scaling operators are eigenoperators of the fixed point, and their dimensions are not always equal to naive engineering dimensions.

This is why one should not define relevance by counting powers in the bare Lagrangian unless the fixed point is Gaussian or perturbatively close to Gaussian. The correct definition is RG-linearized:

$$
D\mathcal R_b\big|_{*}\,h_i=b^{y_i}h_i.
$$

At the Wilson–Fisher fixed point in $d=4-\epsilon$, the $\phi^4$ coupling is no longer a marginal perturbation in the same way it is at the Gaussian fixed point. It is part of the fixed-point data, and the local scaling operators are mixtures of naive monomials. The relevant thermal direction is associated with the mass-like perturbation, while irrelevant directions determine corrections to scaling.

## Relevant directions and critical tuning

A relevant direction grows under coarse-graining. If

$$
g_i'=b^{y_i}g_i,
\qquad y_i>0,
$$

then after $N$ steps,

$$
g_{i,N}=b^{Ny_i}g_{i,0}.
$$

Therefore a tiny microscopic deviation becomes order one at large distances. To obtain a scaling limit governed by the fixed point, the relevant coordinates must be tuned as the cutoff is removed.

This is the mathematical form of critical tuning. If there are $r$ relevant directions, then the critical surface has codimension $r$ under suitable hyperbolicity hypotheses. In statistical mechanics, tuning temperature to $T_c$ is the familiar one-parameter example. In QFT, tuning a bare mass as a function of the cutoff is the familiar renormalization example.

Relevant does not mean “physically more important” in every context. It means unstable under the chosen RG direction. A relevant vacuum-energy coordinate may be crucial for the free energy but irrelevant to normalized connected correlation functions. A symmetry may forbid a relevant perturbation, reducing the number of tunings.

## Irrelevant directions and universality

An irrelevant direction contracts under coarse-graining:

$$
g_i'=b^{y_i}g_i,
\qquad y_i<0.
$$

After $N$ steps,

$$
g_{i,N}=b^{Ny_i}g_{i,0}\to 0.
$$

This contraction is the mechanism behind universality. Different microscopic systems can have different irrelevant couplings, but those differences fade at long distances if the RG trajectory approaches the same fixed point.

In rigorous RG, this statement is not automatic. The irrelevant sector is infinite-dimensional. A proof must choose a Banach space or norm in which the irrelevant remainder really contracts after local relevant and marginal parts are extracted.

This is the difference between two claims:

| Informal claim | Rigorous replacement |
|---|---|
| “Irrelevant terms go away.” | A specified remainder $K_j$ satisfies a contraction or summability estimate. |
| “Only renormalizable terms matter.” | Local coordinates with $y_i\ge 0$ are tracked; all other generated terms are bounded in a norm. |
| “Microscopic details are forgotten.” | The RG map has stable directions whose effect on selected observables vanishes in the scaling limit. |

Irrelevant does not mean absent. Irrelevant operators are generated by RG steps. They also produce corrections to scaling, lattice artifacts, and finite-size corrections. In precision work, they are often the leading reason data do not sit exactly on the asymptotic scaling curve.

## Marginal directions and logarithms

A marginal direction has $y_i=0$ at linear order. Linearization alone cannot decide its fate. One must inspect the nonlinear beta function. In infinitesimal notation, a single marginal coupling may satisfy

$$
\frac{dg}{d\ell}=ag^2+bg^3+\cdots.
$$

Depending on the sign and domain, the coupling may be marginally relevant, marginally irrelevant, exactly marginal, or flow to a nearby fixed point.

The standard possibilities are:

| Type | Typical beta function | Behavior |
|---|---|---|
| Exactly marginal | $\beta(g)=0$ along a manifold | A continuous family of fixed points. |
| Marginally irrelevant | $dg/d\ell=-c g^2$, $c>0$ | $g(\ell)\sim 1/(c\ell)$ flows slowly to zero. |
| Marginally relevant | $dg/d\ell=+c g^2$, $c>0$ | Small positive $g$ grows and can generate a scale. |
| Marginal with new fixed point | $dg/d\ell=\epsilon g-cg^2$ | A perturbative fixed point $g_*\sim\epsilon/c$. |

Marginally irrelevant directions often produce logarithmic corrections to scaling. This is a central feature in critical dimension problems such as four-dimensional $\phi^4$ models and weakly self-avoiding walk.

Exactly marginal directions are more special. They require structural reasons, such as symmetry, supersymmetry, or special two-dimensional current algebra constraints. They should not be inferred merely from tree-level power counting.

## Dangerous irrelevant variables

An irrelevant variable is called dangerously irrelevant when it flows to zero but observables depend singularly on it. The word “dangerous” means that setting the coupling to zero too early gives the wrong scaling law.

A schematic example is an observable

$$
Q(t,u)=t^\alpha F(u t^{-\omega}),
\qquad \omega>0,
$$

where $u$ is irrelevant at the fixed point. If $F(s)$ has a singular behavior as $s\to 0$ or $s\to\infty$, then the apparent scaling of $Q$ may involve $u$ even though $u$ is irrelevant in the RG eigenvalue sense.

This phenomenon is a useful warning for rigorous QFT. Classification of directions is a statement about flow near a fixed point. It does not automatically justify dropping the corresponding coupling inside every observable, especially when phases, order parameters, constraints, or composite observables are involved.

## Redundant directions and field redefinitions

Not every direction in a coordinate description of an action corresponds to a physical deformation. Some directions are redundant: they arise from field redefinitions or changes of coordinates on theory space.

For example, changing the field normalization

$$
\phi\longmapsto Z^{1/2}\phi
$$

changes coefficients of several terms in the action. Depending on convention, the kinetic coefficient may be treated as a coupling, fixed by normalization, or absorbed into the anomalous dimension. These descriptions can give different coordinate beta functions while representing the same physical RG trajectory.

This is why the most invariant statements are about scaling dimensions of physical operators, critical exponents, universality classes, and convergence of observables. A page that lists relevant operators should always specify the quotient by redundancies or the normalization convention being used.

## Stable, unstable, and critical manifolds

When the RG map is sufficiently regular near a hyperbolic fixed point, the tangent-space classification becomes a local geometric statement.

The unstable manifold is tangent to the relevant eigenspaces. Trajectories on it flow away from the fixed point under coarse-graining and toward the fixed point under the inverse RG, when the inverse is meaningful.

The stable manifold is tangent to the irrelevant eigenspaces. Trajectories on it flow into the fixed point under coarse-graining.

The critical surface is often the stable manifold, possibly enlarged or modified by marginal directions. To obtain a critical scaling limit, the microscopic model must lie on or approach this surface. To obtain a massive continuum limit, one approaches the critical surface in a controlled way while keeping renormalized relevant coordinates finite.

Schematic codimension counting is useful. If a fixed point has $r$ relevant directions and no marginal complications, then reaching it requires tuning $r$ independent parameters. This is why a one-temperature statistical model can reach a critical point when only one symmetry-allowed relevant direction is present.

## Connection with renormalizability

In the Wilsonian viewpoint, perturbative renormalizability is tied to the number of relevant and marginal directions near a UV fixed point. If only finitely many directions have $y_i\ge 0$, then only finitely many parameters need independent renormalization to define a trajectory near that fixed point.

This gives a conceptual explanation of the older distinction between renormalizable and nonrenormalizable interactions. Near the Gaussian fixed point in $d=4$, operators of dimension at most four have couplings with nonnegative engineering dimension. Operators of higher dimension are irrelevant in the ultraviolet Gaussian power counting.

Effective field theory changes the emphasis. Irrelevant interactions are not forbidden; they are organized by suppression at low energy. A Wilsonian effective action includes all symmetry-allowed operators,

$$
S_{\mathrm{eff}}
=\sum_i g_i\int d^dx\,\mathcal O_i(x),
$$

but low-energy predictions to a given accuracy require only finitely many terms because irrelevant couplings are suppressed by powers of the scale ratio.

Rigorous continuum construction asks a sharper question: can one tune the relevant and marginal coordinates and control the irrelevant remainder uniformly as the cutoff is removed?

## Common pitfalls

| Pitfall | Correction |
|---|---|
| “Relevant means large coupling.” | Relevance is about growth under RG near a fixed point, not the current numerical size of the coupling. |
| “Irrelevant means physically unimportant.” | Irrelevant operators control corrections to scaling and may be dangerous for some observables. |
| “Marginal means exactly constant.” | Marginal means undecided at linear order; nonlinear terms decide the flow. |
| “Power counting is always enough.” | Power counting gives Gaussian engineering relevance; interacting fixed points require anomalous dimensions and operator mixing. |
| “The list of operators in a Lagrangian is the list of RG eigenoperators.” | RG eigenoperators are usually linear combinations of local monomials and may include descendants or redundant directions. |
| “Changing scheme changes relevance.” | Coordinate beta functions change with scheme, but physical scaling exponents at a fixed point are invariant under suitable changes of coordinates. |

## Relations to other pages

[Scaling Limits](/rigorous-qft/rigorous-renormalization-rg/scaling-limits/) uses relevant directions to explain why critical tuning is necessary and irrelevant directions to explain universality.

[Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) explains how a rigorous RG step tracks local coordinates and controls the irrelevant remainder.

[Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) gives the constructive-QFT version of cutoff removal and tuning.

[What Is Open in Four Dimensions](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/) explains why marginal four-dimensional interactions are mathematically delicate.

[Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/) gives the measure-theoretic map whose linearization is being classified here.

## Research status

**Established.** The relevant/irrelevant/marginal classification is one of the basic structural outputs of Wilsonian RG. In perturbative and many rigorous models, it can be made precise as a statement about the spectrum of a linearized RG map or flow.

**Rigorous in selected settings.** Constructive RG methods implement this classification by splitting the exact RG map into finitely many local coupling coordinates and an infinite-dimensional remainder controlled by norms. The nonperturbative coordinate is essential; perturbative beta functions alone do not prove contraction.

**Subtle for marginal directions.** Marginal couplings are where naive power counting is least reliable. They can generate logarithms, dimensional transmutation, lines of fixed points, or runaway flows.

**Framework-dependent.** The exact list of coordinates depends on symmetries, field variables, regulator, and whether one works with actions, measures, Schwinger functions, or local algebras. Physical scaling exponents should be invariant under appropriate changes of coordinates, but proving this invariance is part of the mathematical work.

## Exercises

### Exercise 1. Gaussian power counting for scalar monomials

At the Gaussian fixed point in $d$ Euclidean dimensions, classify the coupling of $\phi^n$ using

$$
\Delta_\phi=\frac{d-2}{2}.
$$

For which $n$ is $\phi^n$ relevant, marginal, or irrelevant in $d=3$?

<details><summary><strong>Solution</strong></summary>

The operator dimension is

$$
\Delta_{\phi^n}=n\frac{d-2}{2},
$$

so the coupling exponent is

$$
y_n=d-n\frac{d-2}{2}.
$$

In $d=3$,

$$
y_n=3-\frac n2.
$$

Thus $y_n>0$ for $n<6$, $y_n=0$ for $n=6$, and $y_n<0$ for $n>6$. Therefore $\phi^n$ is relevant for $n=0,1,2,3,4,5$ if allowed by symmetry, marginal for $n=6$, and irrelevant for $n\ge 7$ by Gaussian power counting. If a $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$ is imposed, odd $n$ are forbidden.

</details>

### Exercise 2. Marginally irrelevant flow

Suppose a marginal coupling satisfies

$$
\frac{dg}{d\ell}=-c g^2,
\qquad c>0,
\qquad g(0)>0.
$$

Solve the flow and determine its large-$\ell$ behavior.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^2}=-c\,d\ell.
$$

Integrating gives

$$
-\frac1{g(\ell)}=-c\ell-\frac1{g(0)},
$$

so

$$
g(\ell)=\frac{g(0)}{1+c g(0)\ell}.
$$

As $\ell\to\infty$,

$$
g(\ell)\sim\frac1{c\ell}.
$$

The coupling flows to zero, but only logarithmically. This slow decay is why marginally irrelevant couplings often produce logarithmic corrections to scaling.

</details>

### Exercise 3. Codimension of the critical surface

Assume an RG fixed point has two relevant directions, no marginal directions, and all remaining directions irrelevant. What is the local codimension of its stable critical surface? What does this mean physically?

<details><summary><strong>Solution</strong></summary>

The stable surface is tangent to the irrelevant eigenspaces. Since there are two relevant directions transverse to it, its local codimension is two.

Physically, a generic microscopic theory near this fixed point must tune two independent parameters to approach the critical surface. If only one tunable parameter is available, the theory will generically miss the fixed point unless a symmetry or constraint sets one relevant coordinate to zero automatically.

</details>

### Exercise 4. Why engineering relevance is not enough

Explain why the Gaussian formula $y=d-\Delta^{(0)}$ may fail to classify perturbations near an interacting fixed point.

<details><summary><strong>Solution</strong></summary>

The Gaussian formula uses engineering dimensions computed at the free fixed point. At an interacting fixed point, local operators generally acquire anomalous dimensions and can mix with other operators with the same quantum numbers. The correct scaling operators are eigenoperators of the linearized RG at the interacting fixed point, and their dimensions are $\Delta_i$, not necessarily the Gaussian dimensions $\Delta_i^{(0)}$.

Therefore the sign of $d-\Delta_i^{(0)}$ can be misleading. The correct classification uses the eigenvalues of $D\mathcal R_b$ at the fixed point under discussion.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–199. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- L. P. Kadanoff, “Scaling Laws for Ising Models Near $T_c$,” *Physics Physique Fizika* **2** (1966) 263–272. [doi:10.1103/PhysicsPhysiqueFizika.2.263](https://doi.org/10.1103/PhysicsPhysiqueFizika.2.263).
- F. J. Wegner, “Corrections to Scaling Laws,” *Physical Review B* **5** (1972) 4529–4536. [doi:10.1103/PhysRevB.5.4529](https://doi.org/10.1103/PhysRevB.5.4529).
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295. [doi:10.1016/0550-3213(84)90287-6](https://doi.org/10.1016/0550-3213(84)90287-6).
- O. J. Rosten, “Fundamentals of the Exact Renormalization Group,” *Physics Reports* **511** (2012) 177–272. [arXiv:1003.1366](https://arxiv.org/abs/1003.1366).
- D. C. Brydges and G. Slade, “A Renormalisation Group Method. V. A Single Renormalisation Group Step,” *Journal of Statistical Physics* **159** (2015) 589–667. [arXiv:1403.7256](https://arxiv.org/abs/1403.7256).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).

## Version history

- 2026-06-30: First polished draft. Added fixed-point linearization, Gaussian examples, marginal flows, dangerous irrelevant variables, and rigorous-RG caveats.
