---
title: "Globally Hyperbolic Spacetimes"
description: "Define the causal class of Lorentzian spacetimes used in locally covariant QFT and explain why Cauchy surfaces, causal diamonds, and smooth splittings matter."
sidebar:
  label: "Globally Hyperbolic Spacetimes"
  order: 2
level: Advanced
status: "Polished draft"
source: "Wald causal structure; Bernal–Sánchez smooth splitting; Brunetti–Fredenhagen–Verch local covariance."
topics:
  - globally hyperbolic spacetimes
  - Cauchy surfaces
  - causal structure
  - locally covariant QFT
canonicalTopics:
  - globally-hyperbolic-spacetime
  - cauchy-surface
  - locally-covariant-quantum-field-theory
researchStatus:
  established:
    - "Global hyperbolicity is the standard causal hypothesis under which classical wave equations have well-posed Cauchy problems and locally covariant QFT is usually formulated."
  active:
    - "Boundaries, asymptotically anti-de Sitter spacetimes, gauge constraints, and quantum-gravity motivated settings often require variants or extensions of the basic globally hyperbolic category."
---

## Summary

A **globally hyperbolic spacetime** is the Lorentzian background on which hyperbolic field equations behave like honest evolution equations. It has enough causal order to rule out closed causal curves, and enough compactness to prevent signals from escaping to infinity and returning in a way that destroys the Cauchy problem.

The two most useful characterizations are:

$$
M\text{ is globally hyperbolic}
\quad\Longleftrightarrow\quad
M\text{ has a Cauchy surface},
$$

and, in modern smooth form,

$$
M\simeq \mathbb R\times \Sigma,
\qquad
\Sigma_t=\{t\}\times\Sigma
\text{ is a smooth spacelike Cauchy surface}.
$$

With the mostly-minus convention used in this volume, a smooth global splitting can be written locally in the form

$$
g=\beta(t,x)\,dt^2-h_t,
\qquad \beta(t,x)>0,
$$

where $h_t$ is a Riemannian metric on each slice $\Sigma_t$.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A textbook-style spacetime diagram showing a globally hyperbolic splitting by Cauchy surfaces, a causal diamond, and an inextendible causal curve crossing each Cauchy surface once.](/figures/rigorous-qft/globally-hyperbolic-splitting.svg)

<figcaption>

A globally hyperbolic spacetime admits a smooth slicing by Cauchy surfaces $\Sigma_t$. Every inextendible causal curve crosses each Cauchy surface exactly once, and causal diamonds $J^+(p)\cap J^-(q)$ are compact.

</figcaption>
</figure>

Locally covariant QFT uses globally hyperbolic spacetimes because the framework is meant to describe field theories with local propagation. The algebra on a small Cauchy neighborhood should determine the algebra on the whole causal development, and that statement only makes clean sense when Cauchy evolution is well posed.

## Prerequisites

You should know [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) and the fixed-spacetime idea of [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/). The only differential geometry assumed is the idea of a Lorentzian metric, future-directed causal curves, and spacelike hypersurfaces.

For sign conventions, this page uses the mostly-minus convention fixed in [Conventions](/rigorous-qft/conventions/): timelike vectors have positive norm.

## Core idea

The phrase "spacetime" is too broad for rigorous QFT. A Lorentzian manifold may have closed timelike curves, bad singular boundaries, noncompact causal diamonds, or no sensible initial-value formulation. A classical field equation can then fail to have unique solutions from initial data, and the algebraic time-slice property has no stable target.

Global hyperbolicity is the condition that repairs this. It says, roughly:

$$
\text{causal order}+
\text{compact causal diamonds}
=\text{well-posed causal evolution}.
$$

The physical slogan is:

$$
\text{data on one Cauchy surface determine the field everywhere}.
$$

The mathematical content is stronger than a slogan. On globally hyperbolic spacetimes, normally hyperbolic operators such as

$$
P=\Box_g+m^2+\xi R
$$

have unique advanced and retarded Green operators under standard hypotheses. That is why the free scalar field, the causal propagator, canonical commutation relations, Hadamard states, and perturbative renormalization on curved backgrounds are all built on this causal class.

## Setup and conventions

A **spacetime** here is a smooth Lorentzian manifold $(M,g)$, usually assumed connected, Hausdorff, second countable, oriented, and time-oriented. The dimension is fixed, often $d=4$, although the definitions work in any dimension $d\geq 2$.

A nonzero tangent vector $v$ is timelike, null, or causal according to

$$
g(v,v)>0,
\qquad
g(v,v)=0,
\qquad
g(v,v)\geq 0,
$$

with the mostly-minus sign convention. A causal curve is a piecewise smooth curve whose tangent is everywhere causal and consistently future-directed or past-directed.

For a point $p\in M$, write

$$
J^+(p)=\{q\in M: q\text{ can be reached from }p
\text{ by a future-directed causal curve}\},
$$

and similarly $J^-(p)$ for the causal past. The chronological sets $I^\pm(p)$ use timelike curves instead of causal curves.

A subset $U\subset M$ is **causally convex** if every causal curve in $M$ with endpoints in $U$ lies entirely in $U$. This condition is essential in locally covariant QFT: if an embedded spacetime missed causal shortcuts through the ambient spacetime, the induced algebra map would not respect the causal structure.

## Cauchy surfaces

A subset $\Sigma\subset M$ is a **Cauchy surface** if every inextendible causal curve in $M$ meets $\Sigma$ exactly once.

The "at least once" part says that $\Sigma$ sees every causal history. The "at most once" part says that $\Sigma$ is not crossed twice by the same causal history. For smooth Cauchy surfaces in globally hyperbolic spacetimes, one can choose $\Sigma$ to be spacelike.

The domain of dependence of a set $S\subset M$ is the region determined by $S$ in the causal sense. One common convention is

$$
D(S)=D^+(S)\cup D^-(S),
$$

where $D^+(S)$ consists of points $p$ such that every past-inextendible causal curve through $p$ meets $S$, and $D^-(S)$ is defined with future-inextendible curves. If $S$ is a Cauchy surface for $M$, then

$$
D(S)=M.
$$

This equation is the geometric prototype of the time-slice axiom. If a region contains a Cauchy surface, then in a hyperbolic theory it contains enough information to generate the whole causal development.

## Equivalent definitions of global hyperbolicity

There are several equivalent definitions in common use. For this volume, the following are the most important.

A spacetime $M$ is globally hyperbolic if it is causal and if all causal diamonds

$$
J^+(p)\cap J^-(q)
$$

are compact, for all points $p,q\in M$.

Older references often state the first condition as **strong causality** rather than causality. Modern results show that the weaker formulation with causality and compact diamonds is equivalent under the usual spacetime assumptions. For most QFT purposes, it is safe to remember the robust condition:

$$
\text{no causal loops and no noncompact causal diamonds}.
$$

A second equivalent characterization is the existence of a Cauchy surface. This is often the most physical definition: a spacetime is globally hyperbolic exactly when it admits a global initial-data surface.

A third, deeper, characterization is smooth splitting. Modern Bernal–Sánchez theorems imply that a globally hyperbolic spacetime admits smooth spacelike Cauchy hypersurfaces and a smooth global product decomposition

$$
M\cong \mathbb R\times\Sigma.
$$

With our signature convention, one may write

$$
g=\beta(t,x)\,dt^2-h_t,
\qquad \beta>0,
$$

where $h_t$ is a smooth family of Riemannian metrics on $\Sigma$. Sources using the mostly-plus metric usually write the same statement as

$$
g=-\beta(t,x)\,dt^2+h_t.
$$

The change is only the overall signature convention.

## Why compact causal diamonds matter

The compactness of

$$
J^+(p)\cap J^-(q)
$$

is not a decorative topological condition. It prevents causal influence from wandering off to infinity between two finite events. Without this compactness, a wave equation can lose control of support, and retarded or advanced Green operators can fail to have the properties needed in QFT.

For a field equation, finite propagation speed says that data or sources influence only their causal future. Compact causal diamonds add a global control statement: between two fixed events, the causal region is not allowed to contain an escaping sequence with no convergent subsequence.

This is the analytic reason globally hyperbolic spacetimes are the default background class for free fields. If $P$ is a normally hyperbolic operator, one expects unique advanced and retarded Green operators

$$
G^\pm:C_0^\infty(M)\to C^\infty(M)
$$

with

$$
PG^\pm f=f,
\qquad
G^\pm P f=f,
$$

and support control

$$
\operatorname{supp}(G^\pm f)
\subset J^\pm(\operatorname{supp} f).
$$

These support estimates are the backbone of the causal propagator, the commutator function, and the local algebra construction for the Klein–Gordon field.

## The category Loc

The usual source category for locally covariant QFT is denoted $\mathsf{Loc}$. Its objects are globally hyperbolic spacetimes with orientation and time orientation:

$$
M=(\mathcal M,g,\mathfrak o,\mathfrak t).
$$

A morphism

$$
\psi:M\to N
$$

is typically a smooth isometric embedding preserving orientation and time orientation, with causally convex open image. Some authors vary the exact technical choices, but the causal idea is stable: admissible embeddings must preserve the metric and must not create or hide causal shortcuts.

If $U\subset M$ is an admissible causally convex globally hyperbolic open subspacetime, the inclusion

$$
\iota_U:U\hookrightarrow M
$$

is a morphism in $\mathsf{Loc}$. Applying a locally covariant theory gives an algebra map

$$
\mathcal A(\iota_U):\mathcal A(U)\to\mathcal A(M).
$$

This is how fixed-spacetime local nets are recovered from the functorial framework.

## Examples and non-examples

**Minkowski space.** Ordinary Minkowski spacetime is globally hyperbolic. Constant-time hyperplanes are Cauchy surfaces, and double cones are typical globally hyperbolic subregions used in local QFT.

**Ultrastatic spacetimes.** A spacetime of the form

$$
\mathbb R\times\Sigma,
\qquad
g=dt^2-h,
$$

with $h$ a complete Riemannian metric under suitable hypotheses, is a model example. These backgrounds are useful because the time direction is especially transparent.

**Open diamonds.** Many bounded causally complete regions in Minkowski space, such as suitable double cones, can be treated as globally hyperbolic spacetimes in their own right with the induced metric.

**Generic open subsets.** Not every open subset of a globally hyperbolic spacetime is globally hyperbolic. Removing a point, cutting out a causal shortcut, or choosing a region that is not causally convex can break the Cauchy problem.

**Anti-de Sitter spacetime without boundary conditions.** Anti-de Sitter spacetime is not globally hyperbolic in the ordinary sense because causal curves can reach the conformal timelike boundary and return. QFT on AdS is perfectly meaningful in many settings, but it requires boundary conditions or a modified category rather than the basic $\mathsf{Loc}$ framework.

**Spacetimes with closed timelike curves.** These are excluded. A Cauchy surface cannot intersect every inextendible causal curve exactly once if a causal curve closes on itself.

## Common pitfalls

**Thinking global hyperbolicity means low curvature.** It is a causal condition, not a small-curvature condition. A spacetime can be highly curved and still globally hyperbolic.

**Confusing a time coordinate with a Cauchy time function.** A coordinate called $t$ is not enough. Its level sets must be Cauchy surfaces if it is to support global hyperbolic evolution.

**Forgetting causal convexity of subregions.** A subregion can have a nice metric but still be a bad object for local covariance if causal curves between its points can leave the subregion and re-enter.

**Assuming every curved spacetime is in $\mathsf{Loc}$.** The standard locally covariant category excludes many physically interesting backgrounds, including spacetimes with timelike boundaries unless the framework is enlarged.

**Treating the splitting as canonical.** The existence of

$$
M\cong\mathbb R\times\Sigma
$$

is a theorem, but the choice of time function and Cauchy slicing is not unique. Locally covariant QFT should not depend on an arbitrary preferred slicing.

**Using mostly-plus formulas without translating signs.** Many Lorentzian-geometry references use signature $(-,+,+,+)$. With the mostly-minus convention, the sign of the metric splitting is reversed.

## Relations to other pages

[QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) uses globally hyperbolic spacetimes as the objects of the source category and causal embeddings as its morphisms.

[Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/) turns Cauchy surfaces into an algebraic condition: Cauchy morphisms are mapped to algebra isomorphisms.

[Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/) explains the corresponding fixed-spacetime Haag–Kastler language.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) supplies the microlocal language used later to define Hadamard states on globally hyperbolic spacetimes.

## Research status

**Established.** Global hyperbolicity, Cauchy surfaces, causal diamonds, smooth splitting, and well-posedness for normally hyperbolic equations form a mature mathematical foundation for classical and quantum fields on curved backgrounds.

**Standard in rigorous QFT.** The locally covariant framework normally uses globally hyperbolic spacetimes as objects and causally convex isometric embeddings as morphisms.

**Active at the boundary.** Important physical settings stretch the framework: spacetimes with timelike boundaries, asymptotically AdS physics, null boundaries, gauge theories with global constraints, edge modes, defects, and quantum-gravity motivated categories. These do not invalidate global hyperbolicity; they show where the basic category must be adapted.

## Exercises

1. **Cauchy surface in Minkowski space.** Show that $\Sigma=\{t=0\}$ is a Cauchy surface in ordinary Minkowski spacetime.

<details><summary><strong>Solution</strong></summary>

Every inextendible future-directed causal curve in Minkowski spacetime has a nondecreasing time coordinate. If the curve is inextendible to the past and future, its time coordinate ranges from $-\infty$ to $+\infty$. Therefore it crosses $t=0$ at least once. Since a causal curve cannot reverse in time, it crosses $t=0$ at most once. Thus $\Sigma$ is a Cauchy surface.

</details>

2. **Why a closed timelike curve is forbidden.** Explain why a spacetime with a closed timelike curve cannot have a Cauchy surface.

<details><summary><strong>Solution</strong></summary>

Let $\gamma$ be a closed timelike curve. If a Cauchy surface $\Sigma$ intersects $\gamma$, then following $\gamma$ around the loop returns to the same event and crosses $\Sigma$ again. This violates the requirement that each inextendible causal curve meet $\Sigma$ exactly once. If $\Sigma$ does not intersect $\gamma$, then it violates the requirement that every inextendible causal curve meet $\Sigma$ at least once. Either way, no Cauchy surface exists.

</details>

3. **Causal convexity.** Let $U\subset M$ be causally convex. If $p,q\in U$, what does causal convexity say about causal curves from $p$ to $q$? Why is this useful for local algebras?

<details><summary><strong>Solution</strong></summary>

Causal convexity says that any causal curve in $M$ from $p$ to $q$ must lie entirely inside $U$. Thus the causal relation between points of $U$ is the same whether computed internally in $U$ or externally in $M$. This is useful because the algebra assigned to $U$ should embed into the algebra assigned to $M$ without changing which observables are causally related or causally disjoint.

</details>

## References

### Standard first pass

- Robert M. Wald, *General Relativity*, University of Chicago Press, 1984. DOI: [10.7208/chicago/9780226870373.001.0001](https://doi.org/10.7208/chicago/9780226870373.001.0001).
- Barrett O'Neill, *Semi-Riemannian Geometry with Applications to Relativity*, Academic Press, 1983.
- Christian Bär, Nicolas Ginoux, and Frank Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*, European Mathematical Society, 2007. arXiv: [0806.1036](https://arxiv.org/abs/0806.1036).

### Smooth splitting and local covariance

- Antonio N. Bernal and Miguel Sánchez, "On Smooth Cauchy Hypersurfaces and Geroch's Splitting Theorem," *Communications in Mathematical Physics* **243** (2003), 461–470. DOI: [10.1007/s00220-003-0982-6](https://doi.org/10.1007/s00220-003-0982-6), arXiv: [gr-qc/0306108](https://arxiv.org/abs/gr-qc/0306108).
- Antonio N. Bernal and Miguel Sánchez, "Smoothness of Time Functions and the Metric Splitting of Globally Hyperbolic Spacetimes," *Communications in Mathematical Physics* **257** (2005), 43–50. DOI: [10.1007/s00220-005-1346-1](https://doi.org/10.1007/s00220-005-1346-1), arXiv: [gr-qc/0401112](https://arxiv.org/abs/gr-qc/0401112).
- Antonio N. Bernal and Miguel Sánchez, "Globally Hyperbolic Spacetimes Can be Defined as “Causal” Instead of “Strongly Causal”," *Classical and Quantum Gravity* **24** (2007), 745–749. DOI: [10.1088/0264-9381/24/3/008](https://doi.org/10.1088/0264-9381/24/3/008), arXiv: [gr-qc/0611138](https://arxiv.org/abs/gr-qc/0611138).
- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The Generally Covariant Locality Principle – A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).

## Version history

- **2026-06-29:** Initial polished draft. Defined global hyperbolicity, Cauchy surfaces, causal diamonds, smooth splitting, causal convexity, and the role of these structures in locally covariant QFT.
