---
title: "Gribov Ambiguities Preview"
description: "Explains why common gauge-fixing conditions do not globally pick one representative per gauge orbit, and how Gribov copies affect nonperturbative gauge theory."
sidebar:
  label: "Gribov Ambiguities Preview"
  order: 9
level: Advanced
status: "Polished draft"
source: "Gribov 1978; Singer; Weinberg Vol. II §15.4; Henneaux–Teitelboim; Zwanziger; standard nonperturbative gauge-fixing treatments."
topics:
  - Gribov ambiguity
  - gauge fixing
  - Faddeev-Popov operator
  - Gribov horizon
  - fundamental modular region
  - nonperturbative gauge theory
canonicalTopics:
  - gribov-ambiguity
  - gribov-copies
  - gribov-horizon
  - faddeev-popov-operator
  - fundamental-modular-region
researchStatus:
  established:
    - "For non-Abelian gauge theories, many familiar gauge conditions such as Landau and Coulomb gauge do not globally intersect each gauge orbit exactly once."
    - "The Faddeev–Popov construction is a local gauge-fixing construction and is reliable for ordinary perturbation theory around a configuration where the Faddeev–Popov operator has no zero modes."
  active:
    - "The best nonperturbative treatment of gauge-fixed functional integrals, BRST symmetry in the presence of Gribov restrictions, and the relation to confinement remain active research areas."
---

## Summary

A gauge condition is often drawn as a clean slice through field space. Each gauge orbit intersects the slice once, so one can integrate over the slice instead of over all redundant field configurations. That picture is beautifully useful — and globally false in non-Abelian gauge theory.

A **Gribov copy** is a second field configuration on the same gauge orbit that satisfies the same gauge condition. If both $A$ and $A^U$ obey the gauge condition, then the gauge condition has not selected a unique representative. It has only selected a local slice.

The local Faddeev–Popov construction detects this problem through the Faddeev–Popov operator. For a gauge condition $\mathcal F[A]=0$, define

$$
\mathcal M[A]
=\left.\frac{\delta \mathcal F[A^U]}{\delta\alpha}\right|_{U=1}.
$$

If $\mathcal M[A]$ has a zero mode, nearby points on the same gauge orbit fail to be separated by the gauge condition. In Landau gauge, $\partial_\mu A^\mu=0$, the Euclidean Faddeev–Popov operator is usually written as

$$
\mathcal M^{ab}[A]=-\partial_\mu\mathcal D_\mu^{ab}[A].
$$

The hypersurface on which the lowest eigenvalue of $\mathcal M[A]$ vanishes is called the **Gribov horizon**.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Gauge-fixing slice intersecting the same gauge orbit several times, producing Gribov copies.](/figures/symmetry-anomalies-topology/gribov-copies-gauge-slice.svg)

<figcaption>

A gauge condition $\mathcal F[A]=0$ is only locally a slice through gauge orbits. In non-Abelian gauge theory, the same orbit can intersect the slice at several points $A_1,A_2,A_3$. Zero modes of the Faddeev–Popov operator $\mathcal M[A]$ mark the Gribov horizon. The first Gribov region $\Omega$ and the fundamental modular region $\Lambda$ are attempts to improve the global slice.

</figcaption>
</figure>

The practical lesson is not “Faddeev–Popov is wrong.” The practical lesson is sharper:

$$
\text{Faddeev–Popov gauge fixing is local on orbit space.}
$$

That is enough for perturbation theory near the trivial connection. It is not enough, by itself, for a complete nonperturbative definition of a non-Abelian gauge theory.

## Prerequisites

Read [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/), [Faddeev–Popov Ghosts](/symmetry-anomalies-topology/gauge-redundancy-brst/faddeev-popov-ghosts/), [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/), and [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) first.

You should know the orbit-space picture

$$
\text{physical configurations}=\mathcal A/\mathcal G,
$$

where $\mathcal A$ is the space of gauge fields and $\mathcal G$ is the group of gauge transformations.

## Core idea

Gauge fixing tries to replace the quotient $\mathcal A/\mathcal G$ by a representative surface inside $\mathcal A$. A good global gauge condition would satisfy two properties:

1. Every gauge orbit intersects the gauge-fixing surface.
2. Each gauge orbit intersects it exactly once.

The first property says the gauge condition is not missing physical configurations. The second says the gauge condition is not still overcounting.

For perturbative work, one usually asks only for a local version. Around a background $A_0$, the gauge-fixing surface should be transverse to the gauge orbit. In equations, the Faddeev–Popov operator at $A_0$ should be invertible. If $\mathcal M[A_0]$ has no zero modes, then the gauge condition works in a neighborhood of $A_0$.

The Gribov problem is the failure of this local picture to extend globally. Non-Abelian gauge orbits curve through field space, and simple gauge-fixing surfaces can meet the same orbit more than once.

This is a global problem, not a small algebra mistake. It is the gauge-theory version of trying to cover a sphere with one nonsingular coordinate chart. Locally everything looks fine. Globally the topology bites.

## Setup and conventions

Let $G$ be a compact non-Abelian gauge group with generators $T^a$ obeying

$$
[T^a,T^b]=if^{abc}T^c.
$$

The gauge field is

$$
A_\mu=A_\mu^aT^a.
$$

We use the convention

$$
D_\mu=\partial_\mu+igA_\mu,
$$

so a finite gauge transformation $U(x)$ acts as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

A gauge condition is a functional equation

$$
\mathcal F[A]=0.
$$

For an infinitesimal gauge transformation $U(x)=1+ig\alpha(x)+O(\alpha^2)$, the variation of the gauge condition defines the Faddeev–Popov operator:

$$
\mathcal F[A^\alpha]=\mathcal F[A]+\mathcal M[A]\alpha+O(\alpha^2).
$$

In Landau gauge,

$$
\mathcal F^a[A]=\partial_\mu A^{a\mu},
$$

one finds, up to sign conventions for $D_\mu^{ab}$,

$$
\mathcal M^{ab}[A]=-\partial_\mu\mathcal D_\mu^{ab}[A].
$$

:::note[Source note on signs]
Some authors define $D_\mu=\partial_\mu-igA_\mu$ or absorb $g$ into $A_\mu$. This changes signs in $A_\mu^U$, $F_{\mu\nu}$, and $\mathcal M[A]$, but not the geometric statement: zero modes of the infinitesimal gauge-fixing map signal failure of local transversality.
:::

## Local gauge fixing and the Faddeev–Popov determinant

The Faddeev–Popov trick inserts the identity

$$
1=\Delta_{\rm FP}[A]\int_{\mathcal G}\mathcal D U\,\delta(\mathcal F[A^U])
$$

into the path integral. Formally, this turns the integral over all gauge fields into an integral over the gauge-fixing surface, accompanied by the determinant

$$
\Delta_{\rm FP}[A]=\det \mathcal M[A].
$$

This formula is local. It assumes the map from gauge transformations to gauge-fixing functions is locally one-to-one near the orbit representative. That assumption is precisely what fails when $\mathcal M[A]$ develops a zero mode.

If the gauge condition intersects an orbit several times, then the same orbit contributes several times to the gauge-fixed integral. The determinant by itself does not know how to divide by the number of intersections globally, especially when that number changes across field space.

For ordinary perturbation theory this problem is usually invisible. Around $A_\mu=0$ in Euclidean Landau gauge,

$$
\mathcal M[0]=-\partial^2,
$$

which has no normalizable zero modes on $\mathbb R^d$ with standard boundary conditions. Small fluctuations around the trivial connection remain inside a local patch where the Faddeev–Popov construction is well behaved. The Gribov ambiguity is an obstruction to a global nonperturbative gauge slice, not to the first few Feynman diagrams around $A=0$.

That sentence is worth keeping. It prevents two opposite mistakes: ignoring Gribov copies entirely, and thinking they invalidate perturbative Yang–Mills theory.

## What a Gribov copy is

A Gribov copy is a pair

$$
A\neq A^U
$$

such that both configurations satisfy the same gauge condition:

$$
\mathcal F[A]=0,
\qquad
\mathcal F[A^U]=0.
$$

They are not physically distinct configurations. They are different representatives of the same gauge orbit. The problem is that the gauge-fixing condition has failed to choose only one.

For infinitesimally nearby copies, take $U=1+ig\alpha+O(\alpha^2)$ and suppose $A$ satisfies $\mathcal F[A]=0$. Then

$$
0=\mathcal F[A^\alpha]=\mathcal F[A]+\mathcal M[A]\alpha+O(\alpha^2)
$$

implies, to leading order,

$$
\mathcal M[A]\alpha=0.
$$

Thus infinitesimal copies are controlled by zero modes of $\mathcal M[A]$.

Finite Gribov copies are subtler. It is possible for two separated points on the same orbit to satisfy the same gauge condition even when there is no infinitesimal zero mode at either point. A determinant is a local diagnostic; the global problem is the topology and geometry of the entire orbit.

## The Abelian contrast

The cleanest way to see why non-Abelian gauge theory is special is to compare with Abelian gauge theory.

In Abelian gauge theory,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Suppose both $A$ and $A+\partial\alpha$ satisfy Landau gauge on $\mathbb R^d$ with decaying boundary conditions:

$$
\partial_\mu A^\mu=0,
\qquad
\partial_\mu(A^\mu+\partial^\mu\alpha)=0.
$$

Then

$$
\partial^2\alpha=0.
$$

With standard decay conditions, the only allowed solution is the trivial one, up to harmless constant gauge transformations. The gauge-fixing operator does not depend on $A$:

$$
\mathcal M=-\partial^2.
$$

In non-Abelian gauge theory, by contrast,

$$
A_\mu\mapsto A_\mu+D_\mu\alpha+O(\alpha^2),
$$

so the Faddeev–Popov operator depends on the field itself:

$$
\mathcal M[A]=-\partial_\mu\mathcal D_\mu[A].
$$

As $A$ moves through field space, eigenvalues of $\mathcal M[A]$ can cross zero. That is where the Gribov horizon appears.

This Abelian contrast has caveats. Compact Abelian gauge theory, finite volume, nontrivial bundles, and boundary conditions can still have large gauge transformations and topological sectors. But the specific non-Abelian Gribov-copy phenomenon in simple Landau/Coulomb gauge is tied to the field-dependent orbit geometry.

## The first Gribov region

In Euclidean Landau gauge, define the **first Gribov region** $\Omega$ by

$$
\Omega=\{A_\mu:\partial_\mu A^\mu=0,
\quad \mathcal M[A]>0\}.
$$

Here $\mathcal M[A]>0$ means that the Faddeev–Popov operator has positive spectrum on the relevant space of test functions, excluding trivial global zero modes if present.

The boundary of $\Omega$ is the first Gribov horizon:

$$
\partial\Omega:\quad \lambda_{\min}(\mathcal M[A])=0.
$$

The original Gribov proposal was to restrict the gauge-fixed functional integral to this region. The intuition is simple: if zero modes announce the first place where local copies appear, then staying inside the region where $\mathcal M[A]$ is positive avoids at least the nearest overcounting.

This restriction has real consequences. It modifies the infrared behavior of gauge-field propagators and is one route into confinement-motivated gauge-fixed descriptions.

But $\Omega$ is not the final answer. It still contains Gribov copies. It is better than the whole Landau-gauge surface, but it is not a perfect one-representative-per-orbit region.

## The fundamental modular region

A stronger construction uses the norm functional

$$
\|A^U\|^2=\int d^dx\,\operatorname{tr}(A_\mu^U A^{U\mu}).
$$

Landau gauge appears as the stationarity condition for this functional along the gauge orbit. The first Gribov region corresponds roughly to local minima. The **fundamental modular region** $\Lambda$ is the set of absolute minima on each gauge orbit:

$$
\Lambda=\{A:\|A\|^2\leq \|A^U\|^2\text{ for all }U\in\mathcal G\}.
$$

This is closer to an ideal gauge fixing. It tries to pick the best representative on each orbit, not merely a local one. In schematic form,

$$
\Lambda\subset\Omega\subset\{A:\partial_\mu A^\mu=0\}.
$$

Even here life is not perfectly tidy. Boundaries of $\Lambda$ can contain identified points: two distinct-looking boundary configurations may still be gauge equivalent. The geometry of orbit space is doing exactly what quotient spaces tend to do — generating singularities, identifications, and corners.

For most continuum QFT calculations, $\Lambda$ is more a conceptual benchmark than a practical integration domain.

## Singer’s theorem and the coordinate-chart analogy

The Gribov ambiguity is not merely a failure of one unimaginative gauge choice. Singer’s theorem gives a broad obstruction: for non-Abelian gauge theories on many compact manifolds, there is no global continuous gauge fixing that intersects every gauge orbit exactly once.

A useful analogy is a principal bundle. The space of gauge fields maps to the orbit space

$$
\mathcal A\longrightarrow \mathcal A/\mathcal G.
$$

A global gauge fixing would be a global section of this bundle. Singer’s theorem says that, in the relevant non-Abelian cases, such a global section does not exist.

This is the deeper reason Gribov copies feel unavoidable. They are not just a nuisance of Landau gauge. They reflect the topology of the gauge bundle over orbit space.

No analogy is perfect, but the coordinate-chart analogy is healthy: one does not respond to the impossibility of global coordinates on a sphere by declaring spheres inconsistent. One uses patches and transition functions. In gauge theory, however, perturbative Faddeev–Popov quantization often behaves as if one patch covers everything. The Gribov problem is the bill coming due.

## BRST and the Gribov problem

Perturbative BRST quantization assumes the Faddeev–Popov construction. The gauge-fixed action has a nilpotent BRST symmetry, and physical quantities are extracted from BRST cohomology.

The Gribov problem makes this picture subtle nonperturbatively. If one restricts the path integral to the first Gribov region, the integration domain is no longer the original BRST-invariant domain in the naive sense. Standard BRST transformations can take a configuration outside the restricted region. Thus the simple perturbative BRST symmetry is not automatically preserved by a Gribov-region cutoff.

This is a big deal. BRST symmetry is the formal engine behind gauge-parameter independence, Slavnov–Taylor identities, and the cohomological definition of physical states. If the nonperturbative gauge-fixed measure changes, one must understand what replaces or modifies the BRST structure.

Several approaches exist:

- Use only gauge-invariant formulations, such as lattice gauge theory without gauge fixing, when possible.
- Study gauge-fixed nonperturbative descriptions such as the Gribov–Zwanziger and refined Gribov–Zwanziger frameworks.
- Look for modified, nonperturbative, or softly broken BRST structures.
- Treat the issue through the geometry of orbit space rather than through one global gauge slice.

The honest status is this: perturbative BRST is one of the most successful tools in QFT, but its naive global nonperturbative extension is not the end of the story.

## Relation to confinement

Gribov’s original motivation was not just a tidy mathematical complaint. The ambiguity appears in the infrared of non-Abelian gauge theory, exactly where confinement lives.

In Coulomb or Landau gauge, approaching the Gribov horizon enhances the influence of low eigenvalues of the Faddeev–Popov operator. This affects ghost and gluon correlation functions and suggests mechanisms by which the infrared theory differs qualitatively from perturbation theory.

One should not oversell this. “Gribov copies explain confinement” is too strong as a standalone slogan. Confinement is a gauge-invariant dynamical phenomenon involving Wilson loops, center symmetry, mass gaps, flux tubes, screening, and the physical spectrum. The Gribov problem is a gauge-fixed window into some of the same infrared structure.

The right statement is more modest and more useful:

$$
\text{Gribov ambiguities reveal that non-Abelian gauge fixing is globally entangled with infrared dynamics.}
$$

That is already plenty.

## Gauge-invariant observables

Gauge-invariant observables do not require choosing a global gauge slice. Wilson loops, correlation functions of gauge-invariant local operators, and lattice path integrals can be defined without fixing gauge at all.

This does not make the Gribov problem irrelevant. Many analytic and perturbative tools use gauge-fixed variables. Gluon and ghost propagators are gauge-dependent but informative. Nonperturbative continuum approaches often need a gauge. The Gribov issue tells us what assumptions are hidden inside those gauges.

A good rule of thumb:

$$
\text{Gauge-invariant question? Avoid gauge fixing if possible.}
$$

$$
\text{Gauge-fixed question? Track the domain and the residual overcounting.}
$$

In perturbative particle physics, the first line is often impractical and the second line is handled by BRST. In nonperturbative Yang–Mills theory, the second line becomes genuinely delicate.

## Common pitfalls

**Pitfall 1: Thinking a gauge condition is automatically a global quotient.**

A gauge condition is a local coordinate choice unless proven otherwise. In non-Abelian gauge theory, familiar gauge conditions are not global.

**Pitfall 2: Confusing Gribov copies with gauge anomalies.**

A gauge anomaly means the quantum theory fails to respect a gauge redundancy. Gribov copies mean a gauge-fixing condition overcounts the same redundancy. One is an inconsistency; the other is a global gauge-fixing problem.

**Pitfall 3: Saying perturbation theory is invalid because of Gribov copies.**

Perturbation theory around $A=0$ uses a local patch where the Faddeev–Popov operator is invertible. Gribov copies become unavoidable in global and nonperturbative questions.

**Pitfall 4: Thinking the first Gribov region solves everything.**

The first Gribov region removes configurations beyond the first horizon, but it still contains copies. The fundamental modular region is closer to one representative per orbit, but it has boundary identifications and is difficult to use.

**Pitfall 5: Treating gauge-dependent propagators as physical observables.**

Gluon and ghost propagators are useful diagnostics in a chosen gauge. They are not directly gauge-invariant observables like Wilson loops or hadron masses.

## Relations to other pages

This page refines [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/) by explaining where gauge fixing fails globally. It also refines [Faddeev–Popov Ghosts](/symmetry-anomalies-topology/gauge-redundancy-brst/faddeev-popov-ghosts/) by identifying the determinant as a local Jacobian rather than a magic global quotient.

The BRST consequences connect to [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/), [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/), and [Physical State Space](/symmetry-anomalies-topology/gauge-redundancy-brst/physical-state-space/).

The topological side points forward to [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/), [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/), and the nonperturbative QFT pages on confinement and lattice gauge theory.

## Research status

The existence of Gribov copies in non-Abelian gauge theory and the local nature of the Faddeev–Popov construction are established. The perturbative use of Faddeev–Popov ghosts and BRST symmetry remains one of the core tools of gauge theory.

The nonperturbative gauge-fixed story is more delicate. The Gribov–Zwanziger framework, refined versions, lattice Landau-gauge studies, functional methods, and attempts to formulate suitable nonperturbative BRST structures are active areas. The conceptual lesson is stable; the best universal formalism for every nonperturbative gauge-fixed question is not.

## Exercises

### Exercise 1: Zero modes and infinitesimal copies

Let $\mathcal F[A]=\partial_\mu A^\mu$ and suppose $A$ satisfies $\mathcal F[A]=0$. Under an infinitesimal gauge transformation,

$$
A_\mu\mapsto A_\mu+D_\mu\alpha.
$$

Show that an infinitesimal copy satisfying the same gauge condition obeys

$$
\partial_\mu D^\mu\alpha=0.
$$

<details><summary><strong>Solution</strong></summary>

The transformed field satisfies

$$
0=\partial_\mu(A^\mu+D^\mu\alpha)
=\partial_\mu A^\mu+\partial_\mu D^\mu\alpha.
$$

Since $A$ already satisfies Landau gauge, $\partial_\mu A^\mu=0$. Therefore

$$
\partial_\mu D^\mu\alpha=0.
$$

Up to the sign convention used to define the Faddeev–Popov operator, this is

$$
\mathcal M[A]\alpha=0.
$$

Thus infinitesimal Gribov copies are zero modes of the Faddeev–Popov operator.

</details>

### Exercise 2: Abelian Landau gauge on flat space

For an Abelian gauge field on $\mathbb R^d$, suppose

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

and both $A$ and $A+\partial\alpha$ obey Landau gauge. Assuming $\alpha$ decays suitably at infinity, show that $\alpha=0$.

<details><summary><strong>Solution</strong></summary>

The two gauge conditions imply

$$
0=\partial_\mu(A^\mu+\partial^\mu\alpha)-\partial_\mu A^\mu
=\partial^2\alpha.
$$

Multiply by $\alpha$ and integrate by parts:

$$
\int d^dx\,\alpha\partial^2\alpha
=-\int d^dx\,\partial_\mu\alpha\partial^\mu\alpha,
$$

with the boundary term vanishing by assumption. Since $\partial^2\alpha=0$, the left-hand side is zero, so

$$
\int d^dx\,(\partial\alpha)^2=0.
$$

Hence $\partial_\mu\alpha=0$. With decay at infinity, the constant is zero. Thus there is no nontrivial copy of this kind.

</details>

### Exercise 3: First Gribov region versus fundamental modular region

Explain why

$$
\Lambda\subset\Omega
$$

is plausible when $\Lambda$ is defined by absolute minima of $\|A^U\|^2$ along gauge orbits and $\Omega$ is defined by local minima with positive Faddeev–Popov operator.

<details><summary><strong>Solution</strong></summary>

Absolute minima are in particular local minima, except possibly at boundary points where degeneracies or identifications occur. The stationarity condition for $\|A^U\|^2$ along the orbit gives Landau gauge. The second variation along the orbit is the Faddeev–Popov operator, up to convention-dependent signs. At a local minimum this second variation is nonnegative; in the interior it is positive. Therefore a representative that is an absolute minimum should lie inside, or on the boundary of, the region defined by positive Faddeev–Popov operator. Schematically, this gives

$$
\Lambda\subset\Omega.
$$

</details>

## References

- V. N. Gribov, “Quantization of Non-Abelian Gauge Theories.”
- I. M. Singer, “Some Remarks on the Gribov Ambiguity.”
- D. Zwanziger, papers on the Gribov horizon and the Gribov–Zwanziger action.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, Chapter 15.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on non-Abelian gauge theory, Faddeev–Popov quantization, and BRST.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*.
- C. Becchi, A. Rouet, R. Stora, and I. V. Tyutin, original BRST papers.
- Lattice and continuum reviews on Landau gauge, Gribov copies, and the refined Gribov–Zwanziger framework.

## Version history

- 2026-06-17: Initial polished preview for the Gauge Redundancy and BRST chapter.
