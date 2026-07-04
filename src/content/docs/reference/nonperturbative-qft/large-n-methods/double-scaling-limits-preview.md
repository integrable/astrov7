---
title: "Double-Scaling Limits Preview"
description: "Explains how matrix-model double-scaling limits combine N to infinity with critical tuning so continuum surfaces and all genera survive."
sidebar:
  label: "Double-Scaling Limits Preview"
  order: 11
level: Research
status: "Polished draft"
source: "Brézin–Kazakov; Douglas–Shenker; Gross–Migdal; Di Francesco–Ginsparg–Zinn-Justin; Mariño; standard matrix-model and two-dimensional-gravity literature."
topics:
  - double-scaling limits
  - matrix models
  - large-N methods
  - random surfaces
  - continuum limits
  - two-dimensional gravity
  - multicritical points
  - genus expansion
  - topological expansion
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - double-scaling-limits
  - matrix-models
  - continuum-random-surfaces
  - topological-expansion
researchStatus:
  established:
    - "Double-scaling limits of matrix models are a standard controlled construction in which N to infinity is combined with tuning to a critical point so that continuum random surfaces and contributions from all genera can survive."
  active:
    - "Modern uses of double-scaling ideas in topological strings, minimal strings, holography, JT-like systems, and nonperturbative completions require separate model-specific analysis."
---

## Summary

A **double-scaling limit** is a large-$N$ limit taken simultaneously with a critical tuning of couplings. In an ordinary matrix-model planar limit, one takes

$$
N\to\infty
$$

at fixed potential. Higher-genus terms are then suppressed by powers of $1/N^2$. In a double-scaling limit, one also tunes a coupling $g$ toward a critical value $g_c$ so that the singular growth near criticality compensates the genus suppression.

Schematically,

$$
N\to\infty,
\qquad
 g\to g_c,
\qquad
\kappa^{-1}=N(g_c-g)^{(2-\gamma_{\rm str})/2}
\quad\text{fixed}.
$$

Here $\gamma_{\rm str}$ is the string susceptibility exponent of the critical point. The exact exponent depends on the universality class. The point is not the particular formula; the point is the **balance**:

$$
\text{large }N\text{ suppresses topology}
\quad\text{while}\quad
\text{criticality enhances topology}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Double-scaling limit: ordinary large N suppresses higher genera, critical tuning makes the eigenvalue edge singular, and the double-scaled limit keeps a renormalized string coupling fixed.](/figures/nonperturbative-qft/double-scaling-critical-edge.svg)

<figcaption>

A double-scaling limit balances two operations. Large $N$ suppresses handles by powers of $1/N^2$, while tuning to a critical edge makes the coefficients of the genus expansion singular. Holding the appropriate combination fixed produces a continuum limit in which contributions from all genera can remain visible.

</figcaption>
</figure>

This page is a preview. It explains why double scaling belongs in nonperturbative QFT and large-$N$ methods, but it does not try to teach minimal strings, topological recursion, or noncritical string theory in full.

## Prerequisites

Read [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/), [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/), [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/), and [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/).

You should be comfortable with the topological expansion

$$
F(N,g)=\log Z_N=\sum_{h=0}^{\infty}N^{2-2h}F_h(g),
$$

and with the idea that eigenvalue densities can become critical when an endpoint develops non-generic behavior.

## Core idea

Large $N$ and criticality each simplify a theory, but they simplify it in opposite ways.

Large $N$ suppresses topology:

$$
F(N,g)=N^2F_0(g)+F_1(g)+\frac1{N^2}F_2(g)+\cdots.
$$

Criticality makes coefficients singular. Near a critical point, the genus-$h$ coefficient may behave schematically as

$$
F_h(g)\sim (g_c-g)^{(2-\gamma_{\rm str})(1-h)}.
$$

Then the $h$-th term behaves like

$$
N^{2-2h}F_h(g)
\sim
\left[N(g_c-g)^{(2-\gamma_{\rm str})/2}\right]^{2-2h}.
$$

So if the combination

$$
\kappa^{-1}=N(g_c-g)^{(2-\gamma_{\rm str})/2}
$$

is held fixed, contributions from all $h$ can remain in play. The resulting theory is neither the ordinary planar limit nor the finite-$N$ matrix model. It is a continuum limit of the critical edge region.

## Setup and conventions

Use a one-matrix model with a coupling $g$ in the potential:

$$
Z_N(g)=\int dM\,\exp\left[-N\operatorname{Tr}V_g(M)\right].
$$

The large-$N$ free energy has a genus expansion

$$
F(N,g)=\log Z_N
=\sum_{h=0}^{\infty}N^{2-2h}F_h(g).
$$

A critical point $g=g_c$ is a point where the planar eigenvalue density becomes non-generic. For example, at an endpoint $b$ of the support, a regular density behaves as

$$
\rho(x)\sim (b-x)^{1/2}.
$$

At an $m$-th multicritical point, one can tune the potential so that

$$
\rho(x)\sim (b-x)^{m+1/2}.
$$

The critical point is a continuum limit because large random surfaces built from matrix-model diagrams dominate. The double-scaling limit zooms into that continuum regime while keeping the genus expansion alive.

## Why ordinary large N loses too much

The ordinary large-$N$ limit at fixed $g$ gives

$$
F(N,g)=N^2F_0(g)+O(N^0).
$$

That is the planar theory. It is often the desired approximation, especially in gauge theory or localization. But for matrix models that count discretized surfaces, the planar limit throws away all handles. It gives only spherical topology.

If the goal is a string-like sum over surfaces, this is too brutal. One wants a limit in which the lattice spacing of the random surface goes to zero while topology is not frozen to genus zero. The critical point supplies the continuum surface limit; the correlated $N\to\infty$ scaling keeps the effective string coupling finite.

This is why double scaling was historically important: it made matrix models into exactly solvable laboratories for two-dimensional quantum gravity and noncritical strings.

## Critical edge viewpoint

In the eigenvalue-density picture, criticality is visible at the edge. A regular one-cut density has a square-root endpoint. If the density vanishes more strongly, the local spacing and fluctuation behavior near the endpoint change.

Near a critical endpoint, the microscopic eigenvalue spacing and the macroscopic distance to criticality are tied together. The double-scaling limit zooms into this edge region while sending $N$ to infinity. In that zoomed variable, one obtains universal differential equations or kernels depending on the critical class.

A useful cartoon is:

$$
\text{regular edge}
\quad\rho(x)\sim(b-x)^{1/2}
\quad\leadsto\quad
\text{ordinary planar saddle},
$$

but

$$
\text{multicritical edge}
\quad\rho(x)\sim(b-x)^{m+1/2}
\quad\leadsto\quad
\text{new continuum limit}.
$$

The continuum limit is not obtained by merely setting $g=g_c$ after taking $N\to\infty$. One must approach $g_c$ at a rate tied to $N$.

## Random-surface viewpoint

Matrix-model Feynman diagrams are ribbon graphs. A ribbon graph is a discretized surface. The perturbative expansion can therefore be read as a sum over surfaces weighted by topology.

For a graph with many vertices, the coupling $g$ often controls the number of elementary polygons. As $g\to g_c$, the average number of polygons diverges. That is a lattice continuum limit for random geometry: the number of building blocks goes to infinity while their effective size goes to zero.

In this viewpoint, double scaling does two things at once:

1. $g\to g_c$ makes the surface large and continuum-like;
2. $N\to\infty$ controls the weight of handles.

The renormalized expansion parameter is the double-scaled coupling $\kappa$, not simply $1/N$.

## The classic pure-gravity scaling

For the simplest one-matrix model describing pure two-dimensional gravity, the string susceptibility exponent is

$$
\gamma_{\rm str}=-\frac12.
$$

Then

$$
\frac{2-\gamma_{\rm str}}{2}=\frac54,
$$

so a common way to state the double-scaling limit is

$$
N(g_c-g)^{5/4}=\text{fixed}.
$$

Equivalently,

$$
N^{4/5}(g_c-g)=\text{fixed}.
$$

Do not memorize this exponent as “the” double-scaling exponent. It is the exponent for a particular universality class. Multicritical models have different exponents.

## What survives in the limit

In an ordinary planar limit, the leading answer is $F_0$. In a double-scaled limit, the object of interest is closer to

$$
F_{\rm ds}(\kappa)=\sum_{h=0}^{\infty}\kappa^{2h-2}f_h,
$$

where the $f_h$ are the universal singular parts of the genus-$h$ free energies. This is a string-like genus expansion with effective string coupling

$$
g_s^{\rm eff}\sim \kappa.
$$

The precise normalization varies by convention. The invariant content is that all genera can survive.

This is one of the cleanest places in theoretical physics where the slogan “large $N$ is a string expansion” becomes a calculable statement rather than a metaphor.

## Nonperturbative completion

The double-scaled genus expansion is usually asymptotic. Like many perturbative string expansions, it may not define a unique nonperturbative object without extra data. Matrix models can sometimes provide such data, but the answer can depend on the contour, potential, stability, or completion chosen before taking the limit.

This is why double scaling belongs in a nonperturbative QFT volume. It is not only about summing diagrams. It exposes the tension between:

$$
\text{formal genus expansion}
\quad\text{and}\quad
\text{nonperturbative definition}.
$$

In many models, effects of order

$$
e^{-c/g_s^{\rm eff}}
$$

come from eigenvalue tunneling or related nonperturbative saddles. They are invisible to the genus expansion but can be essential for defining the theory.

## Checks and diagnostics

A claimed double-scaling limit should answer these questions.

| Check | What to ask |
|---|---|
| Critical point | What coupling or endpoint is being tuned to criticality? |
| Universality class | What is $\gamma_{\rm str}$ or the relevant critical exponent? |
| Scaling variable | What combination of $N$ and $g_c-g$ is held fixed? |
| Surviving terms | Which genus terms survive, and why? |
| Continuum observable | What object has a finite limit: free energy, correlators, loop amplitudes, kernels, or spectra? |
| Nonperturbative definition | Does the finite-$N$ model define the double-scaled object uniquely? |
| Physical interpretation | Is the limit a random surface theory, a string theory, a spectral edge theory, or a QFT reduction? |

These checks are especially important because “double scaling” is sometimes used loosely for any correlated limit. Here it means a correlated large-$N$ and critical limit that keeps a nontrivial continuum expansion.

## Common pitfalls

**Taking the limits in the wrong order.** If $N\to\infty$ is taken first at fixed noncritical coupling, higher genera disappear. If $g\to g_c$ is taken without controlling $N$, the finite-$N$ integral may simply become ill-conditioned or unstable.

**Confusing critical tuning with strong coupling.** A double-scaling limit is not just “go to strong coupling.” It is a specific critical limit of the eigenvalue density or graph-counting expansion.

**Memorizing the pure-gravity exponent as universal.** The $5/4$ exponent belongs to the simplest pure-gravity one-matrix universality class. Other multicritical points have different scaling laws.

**Assuming the genus expansion is nonperturbatively complete.** The double-scaled genus series can be asymptotic. Nonperturbative completion requires additional input, often visible as eigenvalue instantons or contour choices.

**Importing the result into four-dimensional Yang–Mills without justification.** Large-$N$ gauge theories are string-like in important ways, but the classic matrix-model double-scaling construction is a special solvable lower-dimensional/random-geometry setting.

## Relations to other pages

- [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/) explains the density and endpoint language used here.
- [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) introduces matrix integrals, planar free energy, and multi-cut saddles.
- [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) explains why ribbon graphs are discretized surfaces.
- [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) explains the gauge-theory version of large-$N$ topology, where a direct double-scaled solution is not generally available.
- Future pages in the Spacetime, Gravity, and Holography volume should take over the full story of matrix models, minimal strings, topological strings, and noncritical string theory.
- Future pages in Resurgence and Transseries should take over the analysis of asymptotic genus series, eigenvalue instantons, and nonperturbative completions.

## Research status

**Established.** Classic double-scaling limits of one-matrix and related matrix models are controlled solvable examples of continuum random surfaces and two-dimensional gravity. The balancing of $N$ with critical tuning is standard.

**Established with caveats.** The genus expansion obtained after double scaling is a powerful continuum expansion, but the nonperturbative definition may depend on the finite-$N$ completion or integration contour.

**Active.** Double-scaling ideas continue to appear in modern matrix models, topological strings, minimal strings, JT-like systems, holography, and spectral-edge problems. Each modern application needs its own definition of the scaling variable, observables, and completion.

## Exercises

### Exercise 1: Balance the genus expansion

Suppose the genus expansion near a critical point has singular terms

$$
F_h(g)\sim (g_c-g)^{A(1-h)}.
$$

Show that the combination

$$
N(g_c-g)^{A/2}
$$

must be held fixed for all genera to contribute at comparable order.

<details>
<summary><strong>Solution</strong></summary>

The genus-$h$ contribution is

$$
N^{2-2h}F_h(g)
\sim
N^{2-2h}(g_c-g)^{A(1-h)}.
$$

Factor this as

$$
\left[N(g_c-g)^{A/2}\right]^{2-2h}.
$$

Thus if

$$
N(g_c-g)^{A/2}
$$

is fixed, the genus-$h$ terms do not vanish solely because of the explicit factor $N^{2-2h}$. They are reorganized into an expansion in the fixed double-scaled coupling.

</details>

### Exercise 2: Pure-gravity exponent

For pure two-dimensional gravity, take

$$
\gamma_{\rm str}=-\frac12.
$$

Using

$$
\kappa^{-1}=N(g_c-g)^{(2-\gamma_{\rm str})/2},
$$

show that the scaling variable can be written as $N^{4/5}(g_c-g)$.

<details>
<summary><strong>Solution</strong></summary>

First compute

$$
\frac{2-\gamma_{\rm str}}{2}
=\frac{2+1/2}{2}
=\frac54.
$$

The fixed combination is

$$
N(g_c-g)^{5/4}=\text{fixed}.
$$

Raise this expression to the power $4/5$:

$$
N^{4/5}(g_c-g)=\text{fixed}.
$$

The two statements are equivalent up to a monotonic redefinition of the fixed parameter.

</details>

### Exercise 3: Why double scaling is not the planar limit

Explain in words why the planar limit and the double-scaling limit answer different questions.

<details>
<summary><strong>Solution</strong></summary>

The planar limit takes $N\to\infty$ at fixed couplings, so all higher-genus terms are suppressed by powers of $1/N^2$. It isolates $F_0$ and discards handles.

The double-scaling limit also tunes the theory to a critical point. The singularity of $F_h(g)$ near $g_c$ compensates the factor $N^{2-2h}$, allowing many or all genera to survive in a renormalized continuum expansion. It is therefore a continuum random-surface or string-like limit, not just the leading planar approximation.

</details>

## References

### Standard first pass

- P. Di Francesco, P. Ginsparg, and J. Zinn-Justin, “2D Gravity and Random Matrices,” for a broad pedagogical review of matrix-model double scaling.
- M. Mariño, *Instantons and Large N*, for matrix-model large $N$, eigenvalue methods, and nonperturbative large-$N$ effects.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for the neighboring CFT language used in minimal-model applications.

### Classic papers

- E. Brézin and V. Kazakov, “Exactly Solvable Field Theories of Closed Strings.”
- D. Gross and A. Migdal, “Nonperturbative Two-Dimensional Quantum Gravity.”
- M. Douglas and S. Shenker, “Strings in Less Than One Dimension.”

### Deeper references

- B. Eynard, *Counting Surfaces*, for modern matrix-model and topological-recursion technology.
- J. Polchinski, *String Theory*, Vol. 1, for the broader worldsheet/string context.
- M. Mariño, *Les Houches Lectures on Matrix Models and Topological Strings*, for the bridge to topological strings.

## Version history

- **2026-06-28:** Initial polished preview explaining large $N$ plus critical tuning, critical edges, random surfaces, genus survival, and nonperturbative-completion caveats.
