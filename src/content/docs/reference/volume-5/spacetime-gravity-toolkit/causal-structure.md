---
title: "Causal Structure"
description: "A QFT-oriented guide to causal curves, chronological and causal futures, domains of dependence, global hyperbolicity, and locality in curved spacetime."
sidebar:
  label: "Causal Structure"
  order: 20
level: Graduate
status: "Polished draft"
source: "Wald 1984, chs. 8–9; Hawking and Ellis 1973; Penrose 1972; Birrell and Davies 1982, ch. 2; Wald 1994; Fewster and Rejzner 2020"
topics:
  - causal structure
  - domains of dependence
  - global hyperbolicity
  - microcausality
  - Cauchy surfaces
canonicalTopics:
  - causal-structure
  - chronological-future
  - causal-future
  - domain-of-dependence
  - global-hyperbolicity
researchStatus:
  established:
    - "Causal structure is the invariant light-cone ordering of events and is the geometric input that replaces global inertial time in QFT on curved spacetime."
  active:
    - "The local causal framework is settled, while its use in quantum gravity, algebraic holography, and emergent spacetime remains an active research arena."
---

## Summary

Causal structure is the part of Lorentzian geometry that remembers which events can influence which other events. It is determined by the light cones of the metric, not by a chosen coordinate time. In mostly-minus signature, a tangent vector $v^\mu$ is timelike, null, or spacelike according to

$$
g_{\mu\nu}v^\mu v^\nu>0,
\qquad
g_{\mu\nu}v^\mu v^\nu=0,
\qquad
g_{\mu\nu}v^\mu v^\nu<0.
$$

Given an event $p$, its chronological future $I^+(p)$ is the set of events reachable from $p$ by future-directed timelike curves. Its causal future $J^+(p)$ is the set of events reachable by future-directed causal curves, including null curves:

$$
I^+(p)\subseteq J^+(p).
$$

For QFT, this is not just geometry vocabulary. Causal structure tells us where local operators must commute, where retarded Green functions may have support, when an initial-value problem is well posed, and why particle language is less fundamental than local field algebra.

The strongest standard condition used in QFT on fixed backgrounds is global hyperbolicity. It says, roughly, that the spacetime has good Cauchy surfaces and no global causal surprises. It is the condition under which hyperbolic field equations behave most like the familiar flat-space initial-value problem.

## Prerequisites

Read [Conventions and Notation](/spacetime-gravity-holography/conventions/) and [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/) first. You should know what a Lorentzian metric is, how it classifies tangent vectors, and why local field equations should be stated coordinate-independently.

It also helps to know flat-space microcausality: local bosonic observables commute at spacelike separation. This page explains the curved-spacetime geometry behind that statement.

## Core idea

In special relativity, causal structure is the Minkowski light cone. In curved spacetime, the light cone can vary from point to point. The local question is: which directions are timelike, null, or spacelike at one event? The global question is: which events can be connected by curves that remain inside or on the future light cone all the way?

This distinction is essential. A spacetime can be locally Lorentzian and still fail to admit a good global initial-value problem. It may have timelike boundaries, missing regions, closed causal curves, or horizons. Local equations know about the local cone; global evolution knows about how all cones fit together.

For QFT, the safest slogan is

$$
\text{fields are local, but states and particles depend on global causal structure.}
$$

## Setup and conventions

We work on a time-oriented Lorentzian spacetime $(M,g)$ with mostly-minus signature. A curve $\gamma(\lambda)$ has tangent

$$
\dot\gamma^\mu=dx^\mu/d\lambda.
$$

It is called:

| Curve type | Tangent condition |
|---|---|
| Timelike | $g_{\mu\nu}\dot\gamma^\mu\dot\gamma^\nu>0$ everywhere. |
| Null | $g_{\mu\nu}\dot\gamma^\mu\dot\gamma^\nu=0$ everywhere and $\dot\gamma^\mu\neq0$. |
| Causal | Timelike or null, with no spacelike tangent. |
| Spacelike | $g_{\mu\nu}\dot\gamma^\mu\dot\gamma^\nu<0$ everywhere. |

A future-directed causal curve is one whose tangent lies in the chosen future light cone at every point. Time orientation is the structure that makes the word future meaningful globally.

## Chronological and causal futures

For an event $p\in M$, define

$$
I^+(p)=\{q\in M:\ p\ll q\},
$$

where $p\ll q$ means that there exists a future-directed timelike curve from $p$ to $q$. Similarly,

$$
J^+(p)=\{q\in M:\ p\leq q\},
$$

where $p\leq q$ means that there exists a future-directed causal curve from $p$ to $q$, or $p=q$.

The past sets $I^-(p)$ and $J^-(p)$ are defined analogously. For a subset $S\subset M$,

$$
I^+(S)=\bigcup_{p\in S}I^+(p),
\qquad
J^+(S)=\bigcup_{p\in S}J^+(p).
$$

In Minkowski spacetime,

$$
J^+(0)=\{x:\ x^0\geq0,\ x^2\geq0\},
\qquad
I^+(0)=\{x:\ x^0>0,\ x^2>0\}.
$$

The null cone is the boundary between timelike influence and spacelike separation.

## Spacelike separation and local operators

Two events $p$ and $q$ are spacelike separated if neither can causally influence the other:

$$
q\notin J^+(p),
\qquad
p\notin J^+(q).
$$

For bosonic local observables in a relativistic QFT,

$$
[\mathcal O_1(p),\mathcal O_2(q)]=0
\qquad
\text{when }p\text{ and }q\text{ are spacelike separated}.
$$

For fermionic fields one uses graded commutators. Gauge theories require care because gauge-dependent fields are not local observables; the clean causal statement is for gauge-invariant local observables or for appropriately defined local algebras.

The geometric content is simple: spacelike separated operations cannot influence each other through causal propagation. The phrase spacelike separated is metric-dependent, not chart-dependent.

## Domains of dependence

Let $S$ be an achronal hypersurface: no two points of $S$ are timelike related. The future domain of dependence $D^+(S)$ is the set of points $p$ such that every past-inextendible causal curve through $p$ intersects $S$. The past domain of dependence $D^-(S)$ is defined with future-inextendible causal curves. The full domain of dependence is

$$
D(S)=D^+(S)\cup D^-(S).
$$

Physically, $D(S)$ is the region whose classical evolution is determined by data on $S$, assuming the equations are hyperbolic and no boundary data enter from elsewhere.

For a real scalar field, Cauchy data on a spacelike hypersurface $\Sigma$ are

$$
\phi|_\Sigma,
\qquad
n^\mu\nabla_\mu\phi|_\Sigma,
$$

where $n^\mu$ is the future-directed unit normal to $\Sigma$.

## Cauchy surfaces and global hyperbolicity

A Cauchy surface $\Sigma$ is a hypersurface intersected exactly once by every inextendible causal curve. A spacetime admitting such surfaces is globally hyperbolic.

Equivalently, under standard regularity assumptions, a globally hyperbolic spacetime has no closed causal curves and has compact causal diamonds

$$
J^+(p)\cap J^-(q)
$$

for all suitable events $p,q$. It can also be foliated as

$$
M\simeq\mathbb R\times\Sigma,
$$

with the leaves serving as Cauchy surfaces.

Global hyperbolicity is the default assumption for QFT on a fixed curved background because it gives well-posed hyperbolic evolution. In globally hyperbolic spacetimes, advanced and retarded Green functions for normally hyperbolic operators exist and are unique.

:::note[Why this matters]
Without global hyperbolicity, the field equation may still be locally meaningful, but evolution from initial data can fail to be unique or can require extra boundary conditions.
:::

## Green functions and causal support

For a scalar operator

$$
P=\Box_g+m^2+\xi R,
$$

the retarded Green function satisfies

$$
P_xG_R(x,x')=\delta^{(D)}(x,x')/\sqrt{|g|},
$$

with support only when $x$ lies in the causal future of $x'$:

$$
\operatorname{supp}G_R(\cdot,x')\subseteq J^+(x').
$$

The advanced Green function has support in $J^-(x')$. Their difference,

$$
\Delta(x,x')=G_R(x,x')-G_A(x,x'),
$$

is the causal propagator. In canonical quantization of the real scalar field,

$$
[\phi(x),\phi(x')]=i\Delta(x,x').
$$

Thus microcausality follows from causal support: $\Delta(x,x')=0$ when $x$ and $x'$ are spacelike separated.

The Feynman propagator is different. It is a time-ordered two-point function and depends on the state or boundary prescription. Its singularities know about causal structure, but its support is not confined to the light cone in the same way as the retarded propagator.

## Examples

### Minkowski spacetime

In flat spacetime,

$$
ds^2=dt^2-d\mathbf x^2,
$$

constant-$t$ hyperplanes are Cauchy surfaces. The usual flat-space commutator condition is

$$
[\mathcal O(x),\mathcal O(y)]=0
\qquad
\text{for }(x-y)^2<0.
$$

### Rindler wedge

The right Rindler wedge is

$$
\mathcal R=\{(t,x,\mathbf y):\ x>|t|\}.
$$

Its boundaries $x=\pm t$ are null surfaces. A field theory restricted to this wedge has a horizon even though the full Minkowski spacetime has none. This is the geometric setup behind the Unruh effect.

### Schwarzschild exterior

The exterior region of a Schwarzschild black hole has a causal boundary at the event horizon. Signals from inside the horizon cannot reach future null infinity. Constant Schwarzschild-time slices in the exterior do not by themselves form Cauchy surfaces for the maximally extended spacetime.

### Anti-de Sitter spacetime

Anti-de Sitter spacetime has a timelike conformal boundary. Null rays can reach the boundary and return in finite global time after boundary conditions are imposed. Therefore AdS is not globally hyperbolic without boundary conditions at infinity. In holography, this boundary structure is a feature, not a bug.

## Common pitfalls

**Confusing coordinate speed with causal speed.** Causal curves stay inside or on the metric light cone. Coordinate velocities depend on the chart.

**Assuming local Lorentzian geometry implies a good initial-value problem.** Local cones do not guarantee global hyperbolicity.

**Treating the Feynman propagator as the causal propagator.** Retarded and advanced Green functions have causal support. The Feynman propagator encodes time ordering and state information.

**Forgetting boundary data.** Spacetimes with timelike boundaries, such as AdS, need boundary conditions before evolution is determined.

**Confusing spacelike separation with distance on one slice.** The invariant question is whether a causal curve connects the events.

## Relations to other pages

This page follows [Lorentzian Geometry for QFT](/spacetime-gravity-holography/spacetime-gravity-toolkit/lorentzian-geometry-for-qft/) and prepares the reader for [Horizons](/spacetime-gravity-holography/spacetime-gravity-toolkit/horizons/), Penrose diagrams, QFT in curved spacetime, the Unruh effect, Hawking radiation, and AdS boundary conditions.

Later pages use the retarded/advanced Green-function discussion here to explain mode expansions, commutators, particle creation, black-hole causal structure, and holographic boundary conditions.

## Research status

The causal definitions on this page are standard mathematical relativity. Their role in QFT on globally hyperbolic spacetimes is also well established, especially in the algebraic formulation.

Active questions begin when one weakens the assumptions: spacetimes with boundaries, singularities, horizons, quantum energy inequalities, and emergent causal structure in holography or quantum gravity. In these settings, the classical causal diagram is often the starting point, not the final answer.

## Exercises

### Exercise 1: Minkowski future sets

In $D$-dimensional Minkowski spacetime with mostly-minus signature, show that

$$
J^+(0)=\{x:\ x^0\geq0,\ x^2\geq0\},
\qquad
I^+(0)=\{x:\ x^0>0,\ x^2>0\}.
$$

<details><summary><strong>Solution</strong></summary>

A future-directed causal curve from the origin has tangent satisfying

$$
(\dot x^0)^2-|\dot{\mathbf x}|^2\geq0,
\qquad
\dot x^0\geq0.
$$

Therefore the spatial distance traveled is at most the elapsed time. Any endpoint obeys $x^0\geq0$ and $(x^0)^2-|\mathbf x|^2\geq0$. Conversely, if $x^0\geq|\mathbf x|$, the straight line from $0$ to $x$ is future-directed causal. If the inequality is strict and $x^0>0$, it is timelike.

</details>

### Exercise 2: Retarded support implies microcausality

Suppose $\Delta(x,x')=G_R(x,x')-G_A(x,x')$, with $G_R$ supported in $J^+(x')$ and $G_A$ supported in $J^-(x')$. Show that $[\phi(x),\phi(x')]=0$ for spacelike separated points.

<details><summary><strong>Solution</strong></summary>

If $x$ and $x'$ are spacelike separated, then $x\notin J^+(x')$ and $x\notin J^-(x')$. The support conditions imply

$$
G_R(x,x')=0,
\qquad
G_A(x,x')=0.
$$

Therefore $\Delta(x,x')=0$. Since $[\phi(x),\phi(x')]=i\Delta(x,x')$, the commutator vanishes.

</details>

### Exercise 3: Why AdS needs boundary conditions

Global AdS has a timelike conformal boundary. Explain why this prevents ordinary global hyperbolicity unless boundary conditions are added.

<details><summary><strong>Solution</strong></summary>

A globally hyperbolic spacetime has Cauchy surfaces whose data determine evolution without extra input. In AdS, null causal curves can reach the timelike conformal boundary in finite global time. From the viewpoint of the interior, information can leave through the boundary and later re-enter. Therefore interior Cauchy data are not enough until boundary conditions are supplied.

</details>

## References

- R. M. Wald, *General Relativity*, University of Chicago Press, 1984.
- S. W. Hawking and G. F. R. Ellis, *The Large Scale Structure of Space-Time*, Cambridge University Press, 1973.
- R. Penrose, *Techniques of Differential Topology in Relativity*, SIAM, 1972.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- C. J. Fewster and K. Rejzner, “Algebraic quantum field theory: an introduction,” in *Progress and Visions in Quantum Theory in View of Gravity*, Birkhäuser, 2020.

## Version history

- 2026-07-01: Added a polished QFT-oriented page on causal structure, global hyperbolicity, domains of dependence, and causal propagators.
