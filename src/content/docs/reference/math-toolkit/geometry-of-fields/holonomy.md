---
title: "Holonomy"
description: "Explains holonomy as parallel transport around loops, its relation to curvature, Wilson loops, flat connections, Aharonov–Bohm phases, Berry phases, and gauge-invariant observables."
sidebar:
  label: "Holonomy"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard geometry and gauge-theory references, including Nakahara, Frankel, Kobayashi–Nomizu, Baez–Muniain, Polyakov, and QFT treatments of Wilson lines and gauge fields."
topics:
  - holonomy
  - parallel transport
  - Wilson loops
  - Wilson lines
  - curvature
  - flat connections
  - Berry phase
  - Aharonov–Bohm phase
  - gauge invariance
canonicalTopics:
  - holonomy
  - parallel-transport
  - wilson-loop
  - wilson-line
  - curvature-as-infinitesimal-holonomy
  - flat-connection
  - berry-phase
  - aharonov-bohm-effect
researchStatus:
  established:
    - "Holonomy is the standard geometric description of parallel transport around loops and is central to gauge theory, gravity, Berry phases, Wilson loops, and topological sectors."
  active:
    - "Modern QFT extends holonomy to higher-form gauge fields, non-Abelian defects, generalized symmetries, categorical parallel transport, and singular connections around extended operators."
---

## Summary

Holonomy is what a connection does around a closed loop. A connection tells you how to parallel transport a vector, spinor, or internal charge along a path. If the path starts and ends at the same point, parallel transport gives an automorphism of the same fiber. That automorphism is the holonomy.

For a connection

$$
\nabla=d+\mathcal A
$$

on a vector bundle, parallel transport along a path $\gamma:[0,1]\to M$ is the solution of

$$
\frac{dU_\gamma(t)}{dt}
=-\mathcal A_\mu(\gamma(t))\dot\gamma^\mu(t)U_\gamma(t),
\qquad
U_\gamma(0)=\mathbf 1.
$$

Formally,

$$
U_\gamma
=\mathcal P\exp\left(-\int_\gamma \mathcal A\right),
$$

where $\mathcal P$ denotes path ordering. For a closed loop $C$ based at $x$, this is a map

$$
U_C:E_x\to E_x.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Diagram showing a connection, parallel transport along a closed loop, holonomy, Wilson loop trace, curvature as infinitesimal holonomy, and flat global holonomy.](/figures/math-toolkit/holonomy-wilson-loop-flow.svg)

<figcaption>

Holonomy converts the local data of a connection into transport around paths. Curvature controls the infinitesimal holonomy around tiny loops, while flat connections can still have global holonomy through representations of $\pi_1(M)$.

</figcaption>
</figure>

In gauge theory, the trace of holonomy in a representation is a Wilson loop. In geometric mechanics, Berry phase is holonomy of a line bundle over parameter space. In gravity, holonomy of the Levi-Civita connection measures rotation of frames around loops and is controlled infinitesimally by the Riemann tensor. Same idea; different wardrobe.

This page uses the mathematical anti-Hermitian connection form $\mathcal A$. The site’s default compact-gauge-group convention is

$$
D=d+igA^aT^a,
\qquad
\mathcal A=igA^aT^a,
$$

with Hermitian generators $T^a$. Thus

$$
U_\gamma
=\mathcal P\exp\left(-ig\int_\gamma A^aT^a\right)
$$

in the site convention. Texts that use $D=d-igA^aT^a$ put the opposite sign in this exponent. The physics is unchanged once the convention is used everywhere.

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) and [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) first. You should know how a connection form changes under a change of local frame and why its curvature is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

For the QFT applications, it helps to know [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) and the trace conventions in [Mathematical Conventions](/math-toolkit/conventions/). The page [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) follows this one and gives the full dictionary between local gauge potentials and principal-bundle geometry.

## Core idea

A derivative compares nearby values of a field. A connection makes this comparison possible when the values live in different fibers. Holonomy asks a sharper question: after using the connection to compare fibers all the way around a loop, do you come back to the same value?

Usually the answer is no.

Suppose $s(0)\in E_{\gamma(0)}$. Parallel transport along $\gamma$ produces $s(t)\in E_{\gamma(t)}$ satisfying

$$
\nabla_{\dot\gamma}s=0.
$$

If $\gamma$ is closed, then $s(1)$ lies in the same fiber as $s(0)$, but it need not equal $s(0)$. The map

$$
s(0)\mapsto s(1)
$$

is the holonomy around the loop.

The useful slogans are

$$
\text{parallel transport along paths gives Wilson lines,}
$$

and

$$
\text{parallel transport around loops gives holonomy and Wilson loops.}
$$

The first statement is local and path-dependent. The second produces gauge-invariant information after taking traces or conjugacy classes.

## Parallel transport along a path

Let $E\to M$ be a vector bundle with connection $\nabla=d+\mathcal A$ in a local frame. Let $\gamma:[0,1]\to M$ be a smooth path. Write

$$
B(t)=\mathcal A_\mu(\gamma(t))\dot\gamma^\mu(t).
$$

Parallel transport is the matrix $U_\gamma(t)$ satisfying

$$
\dot U_\gamma(t)=-B(t)U_\gamma(t),
\qquad
U_\gamma(0)=\mathbf 1.
$$

Then

$$
U_\gamma:E_{\gamma(0)}\to E_{\gamma(1)}
$$

maps the initial fiber to the final fiber. If a section is parallel along $\gamma$, then

$$
s(t)=U_\gamma(t)s(0).
$$

The formal solution is the path-ordered exponential

$$
U_\gamma
=\mathcal P\exp\left(-\int_0^1 B(t)dt\right).
$$

The path-ordering symbol is necessary because $B(t)$ at different times need not commute. The series is

$$
\begin{aligned}
U_\gamma
&=\mathbf 1
-\int_0^1dt_1\,B(t_1)\\
&\quad
+\int_{0\leq t_2\leq t_1\leq 1}dt_1dt_2\,B(t_1)B(t_2)-\cdots .
\end{aligned}
$$

For an Abelian connection, all matrices commute and path ordering drops out:

$$
U_\gamma=\exp\left(-\int_\gamma\mathcal A\right).
$$

## Composition and orientation

Parallel transport behaves the way a transport operation should.

If $\gamma_1$ goes from $x$ to $y$ and $\gamma_2$ goes from $y$ to $z$, then the concatenated path $\gamma_2\circ\gamma_1$ has transport

$$
U_{\gamma_2\circ\gamma_1}=U_{\gamma_2}U_{\gamma_1}.
$$

The order matters: first apply $U_{\gamma_1}$, then $U_{\gamma_2}$.

If $\gamma^{-1}$ is the same path with reversed orientation, then

$$
U_{\gamma^{-1}}=U_\gamma^{-1}.
$$

If the connection is unitary, then $U_\gamma$ is unitary in a unitary representation, so reversing the path gives the Hermitian adjoint:

$$
U_{\gamma^{-1}}=U_\gamma^{-1}=U_\gamma^\dagger.
$$

Parallel transport is invariant under orientation-preserving reparameterizations of the path. The geometry depends on the image and orientation of the path, not on how quickly it is traversed.

## Gauge transformations

A local frame change changes the matrix that represents parallel transport, but not the geometric transport itself.

Use the convention

$$
\mathcal A' = h^{-1}\mathcal A h+h^{-1}dh,
\qquad
s'=h^{-1}s.
$$

For a path $\gamma$ from $x$ to $y$, the parallel transporter transforms as

$$
U_\gamma' = h(y)^{-1}U_\gamma h(x).
$$

This is exactly what an open Wilson line should do: it carries one endpoint transformation on the right and the other on the left. Therefore an open Wilson line is not gauge invariant by itself. It is gauge-covariant endpoint data.

For a closed loop $C$ based at $x$,

$$
U_C' = h(x)^{-1}U_Ch(x).
$$

Thus the matrix $U_C$ depends on the chosen local frame, but its conjugacy class does not. In particular, traces in finite-dimensional representations are gauge invariant:

$$
\operatorname{tr}_R U_C'=
\operatorname{tr}_R U_C.
$$

This is why Wilson loops are traces of holonomy, not raw holonomy matrices.

## Wilson lines and Wilson loops

Let $R$ be a representation of $G$. The Wilson line along a path $\gamma$ is parallel transport in that representation:

$$
U_R(\gamma)
=\mathcal P\exp\left(-\int_\gamma \mathcal A_R\right).
$$

For a closed loop $C$, the Wilson loop is usually

$$
W_R(C)=\operatorname{tr}_R U_R(C),
$$

or sometimes the normalized trace

$$
\frac{1}{\dim R}\operatorname{tr}_R U_R(C).
$$

The normalization is a convention and should be stated when comparing formulas.

Wilson loops are central because they are gauge-invariant nonlocal observables. They are sensitive to features that local curvature measurements can miss: global topology, confinement behavior, screening, center symmetry, and the global form of the gauge group. A tiny Wilson loop sees curvature. A large Wilson loop probes the phase of the gauge theory.

An open Wilson line can be made gauge invariant by attaching charged fields at its endpoints. For example, schematically,

$$
\overline\psi(y)U_R(\gamma_{y\leftarrow x})\psi(x)
$$

can be gauge invariant if the endpoint fields transform in the corresponding representations. The Wilson line supplies the parallel transport needed to compare charged fields at different points.

## Curvature as infinitesimal holonomy

Curvature is infinitesimal holonomy. Let $\Sigma$ be a tiny oriented parallelogram at $x$ with area bivector

$$
\Delta\Sigma^{\mu\nu}=\Delta x^\mu\Delta y^\nu-\Delta x^\nu\Delta y^\mu.
$$

Then parallel transport around its boundary satisfies

$$
U_{\partial\Sigma}
=
\mathbf 1
-\frac12\mathcal F_{\mu\nu}(x)\Delta\Sigma^{\mu\nu}
+O(\Delta^3).
$$

The sign follows from the convention $U_\gamma=\mathcal P\exp(-\int_\gamma\mathcal A)$. If the parallel-transporter exponent is defined with the opposite sign, this formula changes sign too.

This formula is the loop version of

$$
[\nabla_\mu,\nabla_\nu]s=\mathcal F_{\mu\nu}s.
$$

If all tiny loops have trivial holonomy, then the curvature vanishes. Conversely, nonzero curvature creates nontrivial holonomy around sufficiently small loops.

A deeper theorem, the Ambrose–Singer theorem, says roughly that the Lie algebra of the holonomy group is generated by curvature transported back to the base point. For QFT purposes, the slogan is usually enough:

$$
\text{curvature is the local generator of holonomy.}
$$

## Holonomy group

Fix a point $x\in M$. The holonomy group of a connection at $x$ is the set of all parallel transports around closed loops based at $x$:

$$
\operatorname{Hol}_x(\nabla)=\{U_C:E_x\to E_x\mid C(0)=C(1)=x\}.
$$

For a principal $G$-connection, the holonomy group is a subgroup of $G$ after choosing a point in the fiber over $x$. Choosing a different point in the same fiber conjugates the subgroup. Moving the base point along a path also conjugates the holonomy group, assuming the base manifold is connected.

Therefore the exact subgroup at a named base point is not usually the invariant statement. The invariant content is its conjugacy class, or representation-theoretic data derived from it.

One often distinguishes:

| Object | Loops allowed | What it sees |
|---|---|---|
| restricted holonomy | contractible loops based at $x$ | local curvature data |
| full holonomy | all loops based at $x$ | local curvature plus global topology |

The distinction matters because a flat connection can have trivial restricted holonomy but nontrivial full holonomy.

## Flat connections

A connection is flat if

$$
\mathcal F=0.
$$

On a simply connected patch, a flat connection is pure gauge. That is, locally one can write

$$
\mathcal A=h^{-1}dh
$$

up to a convention-dependent sign, and choose a frame in which the connection form vanishes.

Globally, flat does not mean trivial. If $M$ is not simply connected, a flat connection can have nontrivial holonomy around noncontractible loops. The data of a flat connection, modulo gauge equivalence, is closely related to a homomorphism

$$
\rho:\pi_1(M)\to G
$$

modulo conjugation.

This is the clean mathematical version of a familiar physical lesson: a gauge potential can be locally pure gauge while still producing observable phases around noncontractible loops or around removed regions.

## Example: flat connection on a circle

Let $M=S^1$ with angular coordinate $\theta\sim\theta+2\pi$, and consider a $U(1)$ connection

$$
\mathcal A=i\alpha\,d\theta.
$$

The curvature is zero because $d\mathcal A=0$ and $U(1)$ is Abelian:

$$
\mathcal F=0.
$$

But the holonomy around the circle is

$$
U_{S^1}=\exp\left(-\int_0^{2\pi}i\alpha\,d\theta\right)
=\exp(-2\pi i\alpha).
$$

If $\alpha\notin\mathbb Z$, this is not $1$. The connection is locally gauge-equivalent to zero, but its global holonomy is nontrivial.

The periodicity $\alpha\sim\alpha+n$ for $n\in\mathbb Z$ reflects large gauge transformations. The gauge-invariant datum is the phase $e^{-2\pi i\alpha}$, not the real number $\alpha$ itself.

## Abelian Stokes theorem and its limit

For an Abelian connection, path ordering disappears. If a loop $C$ is the boundary of a surface $\Sigma$ and the connection is globally defined and smooth on $\Sigma$, then Stokes’ theorem gives

$$
U_C
=\exp\left(-\oint_C\mathcal A\right)
=\exp\left(-\int_\Sigma \mathcal F\right).
$$

This is the geometric reason that small Abelian Wilson loops measure flux.

But the assumptions matter. If $C$ winds around a removed region, singularity, defect, or nontrivial cycle, then there may be no globally defined smooth potential on a spanning surface. In that case the loop can have nontrivial holonomy even when the curvature vanishes on the accessible region.

This is the Aharonov–Bohm mechanism in one line.

## Aharonov–Bohm phase

In the Aharonov–Bohm setup, the charged particle moves in a region where the magnetic field may vanish, but the region is not simply connected because an inaccessible solenoid or flux tube has been removed. The connection can be flat on the accessible region,

$$
F=0,
$$

while the holonomy around a loop enclosing the excluded flux is nontrivial:

$$
\exp\left(-iq\oint_C A\right)
\neq 1.
$$

Here $q$ is the charge in a convention where the covariant derivative is $d+iqA$. The observable phase is controlled by the flux modulo the appropriate charge quantization.

The moral is not that potentials are “more real” than fields. The moral is that the gauge field is a connection, and connections have global holonomy data not captured by local curvature on a punctured region.

## Berry phase as holonomy

Berry phase is holonomy in parameter space. Suppose a Hamiltonian $H(\lambda)$ depends smoothly on parameters $\lambda\in M$, and a nondegenerate normalized eigenstate $|n(\lambda)\rangle$ is chosen locally. The eigenstates form a complex line bundle over the parameter space.

A common Berry connection is

$$
A_B=i\langle n(\lambda)|d|n(\lambda)\rangle.
$$

The Berry phase around a closed path $C$ is then

$$
\exp\left(i\oint_C A_B\right)
$$

in the usual physics convention. If one instead uses the anti-Hermitian connection

$$
\mathcal A_B=\langle n|d|n\rangle,
$$

then the holonomy is

$$
\exp\left(-\oint_C\mathcal A_B\right)
$$

up to the corresponding sign convention for parallel transport. The two descriptions are the same after translating $\mathcal A_B=-iA_B$ or $A_B=i\mathcal A_B$ according to the convention used.

Berry phase is a good antidote to a narrow view of gauge fields. The base space is not spacetime; it is parameter space. The bundle is not necessarily a dynamical gauge bundle; it is a bundle of quantum states. Yet holonomy is still the organizing idea.

## Holonomy in gravity

For a Riemannian or Lorentzian manifold, the Levi-Civita connection parallel transports tangent vectors. Holonomy around a small loop is controlled by the Riemann curvature tensor:

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

For spinors, the spin connection gives parallel transport in a spin representation. Around a loop, a spinor may transform by a spin-group element whose projection to the orthogonal group is the frame holonomy.

In general relativity, holonomy encodes curvature and global geometry. In gauge theory, holonomy encodes field strength and global gauge data. The analogy is not poetic; it is the same connection-curvature-holonomy mechanism applied to different bundles.

## What holonomy can and cannot tell you

Holonomy is powerful, but it is not magic.

For a connection on a fixed bundle, the collection of all parallel transports along all paths determines the connection. In practice, however, a small set of Wilson loops does not determine a gauge field uniquely. Gauge theories also involve quantum averaging over gauge-equivalence classes of connections, possible sums over bundles, operator renormalization, and choices of allowed representations.

A Wilson loop expectation value such as

$$
\langle W_R(C)\rangle
$$

is not the same object as the classical holonomy $W_R(C)$ of a single connection. The former is a quantum observable computed in a path integral or Hilbert space; the latter is a function on the space of connections modulo gauge transformations. This distinction becomes crucial in confinement, screening, topological field theory, and lattice gauge theory.

## Common pitfalls

**Forgetting path ordering.** In non-Abelian gauge theory,

$$
\exp\left(-\int_\gamma\mathcal A\right)
$$

is only symbolic unless the connection values commute along the path. The correct expression is path ordered.

**Calling an open Wilson line gauge invariant.** An open line transforms at its endpoints. It becomes gauge invariant only after suitable endpoint data, boundary conditions, or charged operators are included.

**Thinking flat means trivial.** Flat means $\mathcal F=0$. Trivial means the holonomy can be gauged away globally. On a non-simply-connected space, these are different statements.

**Ignoring the representation.** A Wilson loop is not just attached to a curve; it is attached to a representation $R$. The same connection can have different traces in different representations.

**Confusing matrix holonomy with its trace.** The holonomy around a closed loop changes by conjugation under a gauge transformation. The trace is gauge invariant.

**Dropping sign conventions in the exponent.** The sign in $\mathcal P\exp(\mp\int\mathcal A)$ depends on whether the covariant derivative is $d+\mathcal A$ or $d-\mathcal A$. Always translate together with the curvature convention.

## Exercises

### Exercise 1: Abelian holonomy and Stokes’ theorem

Let $\mathcal A$ be a globally defined Abelian connection on a surface $\Sigma$ with boundary $C=\partial\Sigma$. Show that

$$
U_C=\exp\left(-\int_\Sigma \mathcal F\right).
$$

<details><summary><strong>Solution</strong></summary>

For an Abelian connection,

$$
\mathcal F=d\mathcal A.
$$

The holonomy around $C$ is

$$
U_C=\exp\left(-\oint_C\mathcal A\right).
$$

By Stokes’ theorem,

$$
\oint_C\mathcal A=\int_\Sigma d\mathcal A=\int_\Sigma\mathcal F.
$$

Therefore

$$
U_C=\exp\left(-\int_\Sigma\mathcal F\right).
$$

The assumptions that $\mathcal A$ is globally defined and smooth on $\Sigma$ are essential.

</details>

### Exercise 2: Gauge transformation of an open transporter

Assume

$$
\mathcal A' = h^{-1}\mathcal A h+h^{-1}dh.
$$

Show that if $U_\gamma$ solves the parallel-transport equation for $\mathcal A$, then

$$
U_\gamma'=h(\gamma(1))^{-1}U_\gamma h(\gamma(0))
$$

solves the parallel-transport equation for $\mathcal A'$.

<details><summary><strong>Solution</strong></summary>

Let $h(t)=h(\gamma(t))$ and $B(t)=\mathcal A(\dot\gamma)$. Then

$$
B'(t)=h^{-1}Bh+h^{-1}\dot h.
$$

Define

$$
U'(t)=h(t)^{-1}U(t)h(0).
$$

Differentiate:

$$
\dot U'
=-h^{-1}\dot h h^{-1}Uh(0)+h^{-1}\dot Uh(0).
$$

Using $\dot U=-BU$, this becomes

$$
\dot U'
=-(h^{-1}\dot h+h^{-1}Bh)h^{-1}Uh(0)
=-B'U'.
$$

Also $U'(0)=\mathbf 1$. Thus $U'$ is the parallel transporter for the transformed connection.

</details>

### Exercise 3: Flat connection on $S^1$

Let

$$
\mathcal A=i\alpha\,d\theta
$$

on $S^1$, where $\theta\sim\theta+2\pi$. Compute the curvature and the holonomy around the circle.

<details><summary><strong>Solution</strong></summary>

Since $d(d\theta)=0$ and the group is Abelian,

$$
\mathcal F=d\mathcal A=0.
$$

The holonomy is

$$
U_{S^1}=\exp\left(-\int_0^{2\pi}i\alpha\,d\theta\right)
=\exp(-2\pi i\alpha).
$$

Therefore the connection is flat but has nontrivial holonomy unless $\alpha\in\mathbb Z$ modulo the charge normalization.

</details>

### Exercise 4: Wilson loop under orientation reversal

Let $C^{-1}$ denote the loop $C$ with the opposite orientation. Show that

$$
U_{C^{-1}}=U_C^{-1}.
$$

If $U_C$ is unitary, what is $\operatorname{tr}_R U_{C^{-1}}$ in terms of $\operatorname{tr}_R U_C$?

<details><summary><strong>Solution</strong></summary>

Parallel transport along a path followed by the same path in reverse gives the identity map:

$$
U_{C^{-1}}U_C=\mathbf 1.
$$

Hence

$$
U_{C^{-1}}=U_C^{-1}.
$$

If $U_C$ is unitary, then $U_C^{-1}=U_C^\dagger$. Therefore

$$
\operatorname{tr}_R U_{C^{-1}}
=\operatorname{tr}_R U_C^\dagger
=\overline{\operatorname{tr}_R U_C}.
$$

Thus orientation reversal complex conjugates the Wilson loop trace in a unitary representation.

</details>

## Relations to other pages

[Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) explains the connection and curvature forms whose path-ordered exponential appears here. [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) explains why holonomy lives in a fiber and why changing trivializations conjugates it. [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) translates this page into the local $A_\mu^a$ language of gauge theory. [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) supplies Stokes’ theorem, which explains the Abelian relation between holonomy and flux.

Later pages on Riemannian and Lorentzian geometry, spin structures, Dirac operators, characteristic classes, topological terms, confinement, lattice gauge theory, and generalized symmetries should link back here.

## Research status

Classical holonomy of smooth connections on finite-dimensional bundles is a settled part of differential geometry. In QFT, the subtleties enter through the quantum theory of holonomy observables: renormalization of Wilson loops, framing dependence in Chern–Simons theory, line defects, non-Abelian surface operators, higher-form holonomies, global forms of gauge groups, and the spectrum of allowed line operators.

A useful habit is to separate three layers: the classical parallel transporter of one connection, the gauge-invariant trace as a function on the space of connections, and the quantum expectation value of that function in a chosen QFT.

## References

- M. Nakahara, *Geometry, Topology and Physics*. Useful for bundles, connections, curvature, holonomy, monopoles, instantons, and gauge theory.
- T. Frankel, *The Geometry of Physics*. Excellent geometric intuition for forms, connections, curvature, and physical applications.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*, Vol. I. A standard mathematical reference for connections and holonomy.
- J. Baez and J. P. Muniain, *Gauge Fields, Knots and Gravity*. A friendly bridge between differential geometry, gauge fields, and holonomy.
- A. M. Polyakov, *Gauge Fields and Strings*. Classic source for Wilson loops, gauge fields, topology, and nonperturbative viewpoints.
- M. Srednicki, *Quantum Field Theory*, S. Weinberg, *The Quantum Theory of Fields*, Vol. II, and M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for the physics use of Wilson lines and non-Abelian gauge fields.

## Version history

- **2026-06-25:** Initial polished draft. Added parallel transport, path ordering, gauge transformation laws, Wilson lines and loops, curvature as infinitesimal holonomy, holonomy groups, flat connections, Aharonov–Bohm and Berry phase examples, common pitfalls, exercises, and figure.
