---
title: "Instanton Number"
description: "Defines instanton number as the integer topological charge of finite-action Yang–Mills fields and relates it to Chern–Simons number, winding, and theta sectors."
sidebar:
  label: "Instanton Number"
  order: 4
level: Advanced
status: "Polished draft"
source: "BPST; ’t Hooft; Coleman; Srednicki; Weinberg; Shifman; Mariño; Nakahara."
topics:
  - instanton number
  - topological charge
  - Chern–Simons number
  - winding number
  - theta angle
  - Yang–Mills theory
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - topological-charge
  - theta-vacua
  - gauge-theory-topology
researchStatus:
  established:
    - "For smooth finite-action SU(N) gauge fields on R⁴ with standard boundary conditions, the Yang–Mills instanton number is an integer."
  active:
    - "Fractional topological charge can appear with modified global forms, twisted boundary conditions, defects, compactification, or background fields; these require extra global data."
---

## Summary

The **instanton number** of a finite-action four-dimensional Euclidean Yang–Mills field is the topological charge

$$
Q
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=
\frac{1}{8\pi^2}\int\operatorname{tr}F\wedge F.
$$

For smooth finite-action $SU(N)$ gauge fields on $\mathbb R^4$, with the usual pure-gauge behavior at infinity,

$$
Q\in\mathbb Z.
$$

The integer $Q$ has three equivalent faces:

| Face | Formula | Interpretation |
|---|---|---|
| Local density | $Q=\int d^4x\,q(x)$ | Integral of $F\widetilde F$ over Euclidean spacetime. |
| Boundary winding | $S^3_\infty\to SU(N)$ | Winding of the pure gauge approached at infinity. |
| Tunneling change | $Q=N_{\rm CS}(+\infty)-N_{\rm CS}(-\infty)$ | Change in Chern–Simons number between Euclidean time slices. |

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic relation between instanton number, Chern–Simons number, boundary winding, and the integral of F dual F.](/figures/nonperturbative-qft/instanton-number-sector-flow.svg)

<figcaption>

Instanton number can be read locally as the integral of $F\widetilde F$, globally as the winding of the pure gauge at $S^3_\infty$, or dynamically as the change in Chern–Simons number between Euclidean time slices. A BPST instanton has $Q=1$; an anti-instanton has $Q=-1$.

</figcaption>
</figure>

This page is mostly a normalization and topology page. It exists to prevent one of the most common instanton confusions: $F\widetilde F$ is a total derivative locally, but its integral is not automatically zero because finite-action gauge fields can have nontrivial global boundary data.

## Prerequisites

You should know [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/), [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/).

It also helps to know the idea of a winding number for maps $S^3\to SU(N)$ and the fact that $\pi_3(SU(N))\simeq\mathbb Z$ for $N\ge2$.

## Core idea

In perturbation theory, one usually expands around the trivial gauge field. Then $F\widetilde F$ looks like a total derivative that can be discarded. Nonperturbatively, this is too fast. A total derivative integrates to a boundary term, and the boundary term can be nonzero if the fields approach a topologically nontrivial pure gauge at infinity.

Finite action requires

$$
F_{\mu\nu}\to0
\qquad
(|x|\to\infty).
$$

Thus the field at infinity is pure gauge. The boundary of Euclidean $\mathbb R^4$ is $S^3_\infty$, so the asymptotic gauge transformation defines a map

$$
U:S^3_\infty\to SU(N).
$$

Such maps have an integer winding number. The instanton number $Q$ is the same integer, written as a gauge-invariant bulk integral.

This is the reason theta angles matter. The Euclidean path integral is not one integral over one connected configuration space; it is a sum over sectors,

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

## Setup and conventions

We use the gauge conventions of this volume:

$$
D_\mu=\partial_\mu+iA_\mu,
\qquad
[D_\mu,D_\nu]=iF_{\mu\nu},
$$

with Hermitian generators normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

The dual field strength is

$$
\widetilde F_{\mu\nu}
=
\frac12\epsilon_{\mu\nu\rho\sigma}F_{\rho\sigma},
\qquad
\epsilon_{1234}=+1.
$$

The local topological charge density is

$$
q(x)
=
\frac{1}{16\pi^2}
\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

The total charge is

$$
Q=\int d^4x\,q(x).
$$

In differential-form notation,

$$
F=\frac12F_{\mu\nu}dx^\mu\wedge dx^\nu,
$$

and the same definition becomes

$$
Q
=
\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}F\wedge F.
$$

For a self-dual field $F=\widetilde F$,

$$
Q
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\ge0.
$$

For an anti-self-dual field, $Q\le0$.

## Why the integral is an integer

There are two complementary explanations.

The geometric explanation is that

$$
\frac{1}{8\pi^2}\operatorname{tr}F\wedge F
$$

represents the second Chern character density, in the normalization appropriate to the fundamental representation of $SU(N)$. On a compact four-manifold, its integral is an integer for suitable $SU(N)$ bundles, up to sign conventions for how one defines the second Chern class.

The boundary explanation is more physical on $\mathbb R^4$. Since finite action implies $F\to0$, the gauge field approaches a pure gauge at infinity. If we write the asymptotic field as

$$
A\to iU^{-1}dU
\qquad
(|x|\to\infty),
$$

then $U$ is a map from the boundary three-sphere to the gauge group:

$$
U:S^3_\infty\to SU(N).
$$

Its winding number is

$$
\nu[U]
=
\frac{1}{24\pi^2}
\int_{S^3_\infty}
\operatorname{tr}(U^{-1}dU)^3
\in\mathbb Z,
$$

with an overall sign depending on whether the pure gauge is written as $iU^{-1}dU$ or $-i(dU)U^{-1}$. With the convention chosen consistently, the bulk integral $Q$ equals this boundary winding number.

The equality is the content of the statement

$$
\operatorname{tr}F\wedge F=d\omega_3(A),
$$

where, in the present Hermitian convention,

$$
\omega_3(A)
=
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right).
$$

Thus

$$
Q
=
\frac{1}{8\pi^2}\int_{M_4}d\omega_3(A)
=
\frac{1}{8\pi^2}\int_{\partial M_4}\omega_3(A),
$$

when the boundary expression is legitimate. The bulk formula is gauge invariant and usually safer; the boundary formula makes integrality visible.

## Chern–Simons number

Instanton number can also be read as a change in Chern–Simons number. Split Euclidean spacetime as $\mathbb R_\tau\times\mathbb R^3$ and consider spatial slices at fixed Euclidean time $\tau$.

Define the Chern–Simons functional

$$
N_{\rm CS}[A(\tau)]
=
\frac{1}{8\pi^2}\int_{\mathbb R^3}\omega_3(A(\tau)).
$$

For a finite-action trajectory whose fields become pure gauge as $\tau\to\pm\infty$, one obtains

$$
Q
=
N_{\rm CS}(+\infty)-N_{\rm CS}(-\infty).
$$

This is the gauge-theory version of tunneling between neighboring minima in a periodic potential. The pure-gauge vacua have integer Chern–Simons numbers, and an instanton changes that integer by one.

There is a subtle but important point: $N_{\rm CS}$ itself is not invariant under large gauge transformations. It can shift by an integer. The difference between two endpoints, or the exponentiated theta weight $e^{i\theta Q}$, is the physical object.

## BPST check

For the charge-one BPST instanton centered at $x_0$ with size $\rho$,

$$
q(x)
=
\frac{6\rho^4}{\pi^2[(x-x_0)^2+\rho^2]^4}.
$$

As shown on [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/),

$$
\int d^4x\,q(x)=1.
$$

The anti-instanton has the opposite duality and

$$
q_{\bar I}(x)=-q_I(x),
\qquad
Q_{\bar I}=-1.
$$

A dilute configuration containing $n_+$ instantons and $n_-$ anti-instantons has total charge

$$
Q=n_+-n_-,
$$

as long as the lumps are well separated and the configuration can be continuously deformed to that dilute collection without changing the boundary class.

## Gauge transformations and theta periodicity

Under a small gauge transformation, $Q$ is unchanged and $N_{\rm CS}$ is unchanged. Under a large gauge transformation of winding number $m$,

$$
N_{\rm CS}\to N_{\rm CS}+m.
$$

This is why the individual winding-sector states $|n\rangle$ are not the final gauge-invariant story. The theta vacua are superpositions of the form

$$
|\theta\rangle
=
\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

Since $Q\in\mathbb Z$ in the standard $SU(N)$ case,

$$
e^{i(\theta+2\pi)Q}=e^{i\theta Q},
$$

so theta is $2\pi$ periodic.

This statement can be modified by global subtleties. If the gauge group is not simply connected, if one allows nontrivial background two-form gauge fields, if spacetime is not spin or has boundaries, or if defects impose singular boundary conditions, the allowed topological charges can be fractional or shifted. Then the correct periodicity and sector sum must be stated with the full global data.

## Total derivative does not mean zero

The most common mistake is to reason as follows:

$$
\operatorname{tr}F\wedge F=d\omega_3(A),
$$

therefore

$$
\int\operatorname{tr}F\wedge F=0.
$$

This conclusion is false unless the boundary term vanishes or the gauge field is globally trivial in the required way. Instantons are precisely the configurations for which the boundary term is nonzero.

There is no contradiction with locality. The theta term does not change the local classical Yang–Mills equations on smooth trivial patches because it is a total derivative. It changes the quantum theory because the path integral sums over globally distinct sectors and weights them differently.

This is one of the cleanest morals of nonperturbative QFT: local equations do not determine the full quantum theory until the global configuration space is specified.

## Orientation and convention checks

Different references differ by signs and factors of $g$ because they choose different gauge-field normalizations. The most common changes are:

| Choice | What changes |
|---|---|
| Hermitian versus anti-Hermitian generators | Factors of $i$ in $F$, $\omega_3$, and the pure-gauge formula. |
| Coupling inside or outside $A_\mu$ | Factors of $g^2$ in the displayed expression for $Q$ and the action. |
| Orientation $\epsilon_{1234}=+1$ or $-1$ | Which saddle is called $Q=+1$. |
| Self-dual convention for $\eta$ symbols | Whether $\eta$ or $\bar\eta$ gives the instanton rather than the anti-instanton. |

The invariant statements are:

$$
Q\in\mathbb Z,
\qquad
S_I=\frac{8\pi^2}{g^2}\lvert Q\rvert
\quad\text{for self-dual or anti-self-dual saddles},
$$

and a theta term weights sectors by

$$
e^{i\theta Q}.
$$

When comparing two sources, translate these invariant statements first. Then translate the local formulas.

## Common pitfalls

**Forgetting the trace normalization.** The formula for $Q$ depends on whether $\operatorname{tr}(T^aT^b)=\delta^{ab}/2$, $\delta^{ab}$, or another convention is used. The integer is invariant; the printed coefficient changes.

**Treating Chern–Simons number as an ordinary gauge-invariant observable.** $N_{\rm CS}$ shifts by an integer under large gauge transformations. Its changes, exponentiated forms, and role in tunneling are physical; its absolute representative depends on conventions.

**Confusing instanton number with monopole charge.** Instanton number is a four-dimensional Euclidean topological charge. Monopole charge is measured by magnetic flux at spatial infinity. Related constructions exist, but the diagnostics are different.

**Assuming $Q$ is always an integer without global data.** For smooth $SU(N)$ bundles on $\mathbb R^4$ with standard boundary conditions, yes. With other global forms, twisted bundles, defects, boundaries, or background fields, one must reanalyze the allowed charges.

**Dropping theta because it is a total derivative.** Total derivatives can be physically meaningful when the configuration space has disconnected sectors or nontrivial boundary data.

## Relations to other pages

[Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) uses this integer to derive the instanton action and normalize the BPST density.

[Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) uses $Q$ to build theta-dependent sector sums and theta superselection sectors.

[Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) studies fluctuations of $Q$ and the curvature of the vacuum energy as a function of $\theta$.

[Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/) explains why global data and operator insertions matter for nonlocal observables.

[Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/) records the trace, dual, theta, and gauge-field normalization choices used here.

## Research status

**Established.** For smooth finite-action $SU(N)$ gauge fields on $\mathbb R^4$ with standard boundary conditions, $Q$ is an integer. The equivalence between the $F\widetilde F$ integral, boundary winding, and Chern–Simons-number change is standard.

**Convention-dependent.** Signs and factors of $g$, $2$, $i$, and $\pi$ vary across the literature. This page fixes one convention and flags where translations occur.

**Active and global.** Fractional instanton number, theta periodicity in the presence of background higher-form gauge fields, gauge groups with nontrivial global form, and topological sectors on general manifolds are modern active topics. They do not invalidate the basic $SU(N)$ story; they refine its global assumptions.

## Exercises

### Exercise 1: Show that self-dual charge is nonnegative

Using the definitions on this page, show that a self-dual field has $Q\ge0$ and an anti-self-dual field has $Q\le0$.

<details><summary><strong>Solution</strong></summary>

If $F=\widetilde F$, then

$$
Q
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}.
$$

For compact gauge group and Hermitian generators, $\operatorname{tr}F_{\mu\nu}F_{\mu\nu}$ is nonnegative, so $Q\ge0$. If $F=-\widetilde F$, then

$$
Q
=-
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\le0.
$$

</details>

### Exercise 2: Theta periodicity from integer charge

Assume the path integral decomposes as

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Show that $Z(\theta+2\pi)=Z(\theta)$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
Z(\theta+2\pi)
=
\sum_{Q\in\mathbb Z}e^{i(\theta+2\pi)Q}Z_Q
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}e^{2\pi iQ}Z_Q.
$$

Since $Q$ is an integer,

$$
e^{2\pi iQ}=1.
$$

Therefore

$$
Z(\theta+2\pi)=Z(\theta).
$$

The assumption $Q\in\mathbb Z$ is doing the work. If the allowed charges are fractional because of additional global data, the periodicity must be reanalyzed.

</details>

## References

- A. Belavin, A. Polyakov, A. Schwartz, and Y. Tyupkin, “Pseudoparticle Solutions of the Yang–Mills Equations,” for the original instanton solution and charge-one example.
- G. ’t Hooft, “Computation of the Quantum Effects Due to a Four-Dimensional Pseudoparticle,” for instanton calculus and the role of fermion zero modes.
- M. Srednicki, *Quantum Field Theory*, especially the chapter on instantons and theta vacua.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for theta terms, topology, and gauge-theory applications.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussion of topological charge, BPST instantons, and Chern–Simons number.
- M. Mariño, *Instantons and Large N*, for instanton number, theta dependence, and instanton calculus.
- M. Nakahara, *Geometry, Topology and Physics*, for Chern classes, Chern–Simons forms, and the differential-geometric normalization of instantons.

## Version history

- **2026-06-27:** Initial polished draft. Added after Yang–Mills Instantons as the normalization and topology page for $Q$.
- **2026-06-27:** Linked forward to Theta Vacua after drafting that page.
