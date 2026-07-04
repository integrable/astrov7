---
title: "Yang–Mills Instantons"
description: "Derives the core data of Yang–Mills instantons: self-dual gauge fields, the action bound, the BPST solution, collective coordinates, and semiclassical reliability."
sidebar:
  label: "Yang–Mills Instantons"
  order: 3
level: Advanced
status: "Polished draft"
source: "BPST; ’t Hooft; Coleman; Srednicki; Weinberg; Shifman; Mariño; Nakahara."
topics:
  - Yang–Mills instantons
  - BPST instanton
  - self-duality
  - topological charge
  - instanton moduli
  - semiclassical gauge theory
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - yang-mills-theory
  - topological-charge
  - semiclassical-methods
researchStatus:
  established:
    - "The charge-one BPST instanton is the basic finite-action self-dual saddle of four-dimensional Euclidean Yang–Mills theory."
  active:
    - "Instanton ensembles in strongly coupled four-dimensional gauge theories, large-size instantons, renormalons, and their relation to confinement remain research-dependent."
---

## Summary

Yang–Mills instantons are finite-action Euclidean gauge fields in four dimensions. They are localized in Euclidean spacetime, carry integer topological charge, and solve the Yang–Mills equations by satisfying the first-order self-duality equation

$$
F_{\mu\nu}=\widetilde F_{\mu\nu}.
$$

Anti-instantons satisfy

$$
F_{\mu\nu}=-\widetilde F_{\mu\nu}.
$$

With the conventions of this volume,

$$
S_{E,\mathrm{YM}}
=
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
\qquad
Q=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

The action obeys the bound

$$
S_{E,\mathrm{YM}}
\ge
\frac{8\pi^2}{g^2}\lvert Q\rvert,
$$

and a self-dual charge-one instanton saturates it:

$$
S_I=\frac{8\pi^2}{g^2},
\qquad
Q=1.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic summary of the BPST instanton: localized density, self-duality, charge one, action, and collective coordinates.](/figures/nonperturbative-qft/yang-mills-instanton-anatomy.svg)

<figcaption>

The BPST instanton is a localized self-dual gauge field in four Euclidean dimensions. Its universal data are $Q=1$, $S_I=8\pi^2/g^2$, center $x_0$, size $\rho$, and gauge orientation moduli. The size modulus is classical; quantum running and infrared physics decide whether the $\rho$ integral is controlled.

</figcaption>
</figure>

The charge-one solution is called the **BPST instanton**, after Belavin, Polyakov, Schwartz, and Tyupkin. It is the gauge-theory analog of the double-well instanton, but with an important upgrade: the tunneling coordinate is not a single variable but a direction in the infinite-dimensional space of gauge fields, and the barrier crossing is measured by topology.

## Prerequisites

You should know [Instantons in Quantum Mechanics](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-quantum-mechanics/), [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [BPS Bounds](/nonperturbative-qft/solitons-defects-extended-configurations/bps-bounds-preview/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and the gauge-field conventions in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

The next page, [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), explains why the integer $Q$ is really an integer and how it is related to Chern–Simons number.

## Core idea

Four-dimensional Euclidean Yang–Mills theory has finite-action gauge fields that cannot be continuously unwound to the vacuum while keeping the action finite. The reason is the boundary condition at infinity.

Finite action requires

$$
F_{\mu\nu}(x)\to0
\qquad
(|x|\to\infty).
$$

Therefore the gauge field must approach a pure gauge at infinity. In radial compactification, the boundary of $\mathbb R^4$ is a three-sphere $S^3_\infty$, so the asymptotic pure gauge data defines a map

$$
S^3_\infty\longrightarrow SU(N).
$$

For $N\ge2$,

$$
\pi_3(SU(N))\simeq\mathbb Z.
$$

The integer is the instanton number. A charge-one instanton is the least-action way to move between neighboring winding sectors. Its contribution to the theta-dependent Euclidean path integral is weighted by

$$
e^{-S_I+i\theta}
=
\exp\left(-\frac{8\pi^2}{g^2}+i\theta\right).
$$

This is the cleanest example of a nonperturbative gauge-theory effect: no finite order in the perturbative expansion in $g$ can produce $e^{-8\pi^2/g^2}$.

## Setup and conventions

We work on Euclidean $\mathbb R^4$ with coordinates $x^\mu$, $\mu=1,2,3,4$, and orientation

$$
\epsilon_{1234}=+1.
$$

The gauge connection is

$$
A_\mu=A_\mu^aT^a,
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

and

$$
D_\mu=\partial_\mu+iA_\mu,
\qquad
[D_\mu,D_\nu]=iF_{\mu\nu}.
$$

Thus

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+i[A_\mu,A_\nu].
$$

The dual field strength is

$$
\widetilde F_{\mu\nu}
=
\frac12\epsilon_{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

With these conventions,

$$
S_{E,\mathrm{YM}}
=
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
$$

and

$$
Q
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=
\frac{1}{8\pi^2}\int\operatorname{tr}F\wedge F.
$$

The theta term is included in the Euclidean action as

$$
S_E
=
S_{E,\mathrm{YM}}-i\theta Q,
$$

so a sector with charge $Q$ carries the phase $e^{i\theta Q}$.

## The action bound

The key calculation is a square completion. For any real two-form $F$ in Euclidean four dimensions,

$$
\operatorname{tr}(F_{\mu\nu}\mp\widetilde F_{\mu\nu})
(F_{\mu\nu}\mp\widetilde F_{\mu\nu})\ge0.
$$

Using

$$
\operatorname{tr}\widetilde F_{\mu\nu}\widetilde F_{\mu\nu}
=
\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
$$

we get

$$
\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\ge
\pm
\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

Choosing the sign so that the right side is positive gives

$$
S_{E,\mathrm{YM}}
\ge
\frac{8\pi^2}{g^2}\lvert Q\rvert.
$$

The bound is saturated exactly when

$$
F=+\widetilde F
\qquad(Q>0),
$$

or

$$
F=-\widetilde F
\qquad(Q<0).
$$

This is the Yang–Mills version of a BPS bound. It is not supersymmetry by itself; it is a Euclidean square-completion identity. Supersymmetry later gives a deeper interpretation in theories where instantons preserve some supercharges.

## Why self-duality solves the equations of motion

The Euclidean Yang–Mills equations are

$$
D_\mu F_{\mu\nu}=0.
$$

The Bianchi identity is

$$
D_\mu\widetilde F_{\mu\nu}=0.
$$

If $F=\widetilde F$, then

$$
D_\mu F_{\mu\nu}
=
D_\mu\widetilde F_{\mu\nu}=0.
$$

The anti-self-dual case is identical, with a minus sign. Thus the first-order self-duality equation implies the second-order Yang–Mills equation.

This is why instantons are tractable. Instead of solving the full nonlinear second-order Yang–Mills equation, the BPST solution solves a first-order equation tied directly to the topology and the action bound.

## The BPST charge-one solution

For $SU(2)$, the charge-one instanton can be written explicitly. Let

$$
y=x-x_0,
\qquad
\rho>0,
$$

where $x_0$ is the center and $\rho$ is the size. A convenient regular-gauge representative has the schematic form

$$
A_\mu^a(y)
=
\frac{2\eta^a_{\mu\nu}y_\nu}{y^2+\rho^2},
$$

where $\eta^a_{\mu\nu}$ are self-dual ’t Hooft symbols. Depending on the sign convention for the commutator in $F_{\mu\nu}$ and on whether one uses $\eta$ or $\bar\eta$, this displayed representative may describe the instanton or anti-instanton; the convention-independent data are the self-duality equation, charge, and density below.

For the charge-one BPST instanton normalized as above,

$$
\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
=
\frac{96\rho^4}{(y^2+\rho^2)^4},
$$

and, for a self-dual orientation,

$$
q(x)
\equiv
\frac{1}{16\pi^2}\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=
\frac{6\rho^4}{\pi^2(y^2+\rho^2)^4}.
$$

This density integrates to one:

$$
\int d^4x\,q(x)=1.
$$

The action density is localized near $x_0$ with width of order $\rho$. The integral is independent of $\rho$ because classical Yang–Mills theory in four dimensions is scale invariant. Small instantons are sharp; large instantons are broad. Classically they cost the same action.

A useful check is

$$
\int d^4x\,\frac{\rho^4}{(y^2+\rho^2)^4}
=
\frac{\pi^2}{6},
$$

so

$$
\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
=
\frac{1}{2g^2}(16\pi^2)
=
\frac{8\pi^2}{g^2}.
$$

## Collective coordinates

The BPST instanton is not one isolated field configuration. It comes in a family of equal-action solutions.

For $SU(2)$ and $Q=1$, the basic bosonic collective coordinates are:

| Modulus | Number | Meaning |
|---|---:|---|
| $x_0^\mu$ | 4 | Euclidean center of the instanton. |
| $\rho$ | 1 | Size of the instanton. |
| Gauge orientation | 3 | Global embedding orientation in $SU(2)$. |

Thus a charge-one $SU(2)$ instanton has eight bosonic zero modes. For $SU(N)$, the charge-one BPST instanton is obtained by embedding an $SU(2)$ instanton into $SU(N)$. The number of bosonic zero modes becomes

$$
4N
$$

for a charge-one instanton. For charge $k$, the general anti-self-dual moduli problem is described by the ADHM construction, and the expected dimension is proportional to $4Nk$ in the basic $SU(N)$ case before further global subtleties are imposed.

The collective-coordinate integral has the schematic form

$$
\int d^4x_0\,\frac{d\rho}{\rho^5}\,d\Omega\;
\mathcal J(\rho,g,\mu)
\exp\left[-\frac{8\pi^2}{g^2}+i\theta\right],
$$

where $d\Omega$ is the gauge-orientation measure and $\mathcal J$ includes zero-mode Jacobians, determinant ratios, and renormalization effects. The exact numerical normalization is convention-sensitive and is not the point of this first page. The important fact is that the instanton is a saddle **with zero modes**, not a single Gaussian peak.

## The size modulus and running coupling

The size modulus $\rho$ is the source of much instanton subtlety. Classically, all sizes have the same action. Quantum mechanically, the coupling runs, and the leading exponential is better thought of as

$$
\exp\left[-\frac{8\pi^2}{g^2(1/\rho)}\right].
$$

In an asymptotically free theory, small instantons have $\rho\to0$, so $1/\rho$ is large and $g(1/\rho)$ is small. That region can be semiclassically controlled.

Large instantons have $\rho$ comparable to the infrared scale. In pure Yang–Mills or QCD at zero temperature, this is exactly where the coupling becomes strong. A dilute instanton gas based only on isolated BPST instantons is therefore not a controlled derivation of confinement in four-dimensional QCD.

The same warning has an optimistic side. If the theory has a Higgs scale, compactification scale, finite-temperature scale, supersymmetric protection, or other infrared regulator, the large-$\rho$ region may be cut off or controlled. Instantons are then powerful and sometimes exact.

## Physical effects

Yang–Mills instantons do several different jobs, depending on the theory.

First, they explain why the theta angle matters. Since the path integral decomposes into sectors,

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q,
$$

an instanton in the $Q=1$ sector carries the phase $e^{i\theta}$.

Second, they mediate tunneling between gauge vacua with adjacent Chern–Simons numbers. In temporal language, an instanton interpolates between pure-gauge configurations whose winding numbers differ by one.

Third, in theories with fermions, instantons have fermion zero modes. The fermionic determinant vanishes unless operator insertions or mass terms saturate these modes. This produces selection rules and effective interactions such as the ’t Hooft vertex.

Fourth, instantons relate semiclassical physics to large-order perturbation theory, renormalons, and resurgence. The simplest relation is visible already in quantum mechanics; in four-dimensional gauge theory the story is richer and less completely settled.

## Common pitfalls

**Mistaking the instanton for a Lorentzian particle.** The BPST instanton is localized in Euclidean spacetime. It is not a stable particle propagating in real time. Its physical interpretation is through tunneling amplitudes, sector sums, correlation functions, and theta dependence.

**Forgetting the size integral.** The exponential $e^{-8\pi^2/g^2}$ is only the beginning. The full contribution includes $x_0$, $\rho$, gauge orientation, determinant ratios, zero-mode insertions, and interactions with other saddles.

**Claiming instantons prove confinement in four-dimensional QCD.** Isolated BPST instantons are real and important, but the uncontrolled large-size region prevents a simple dilute-gas derivation of confinement in ordinary zero-temperature QCD.

**Confusing topological charge with magnetic charge.** The instanton number $Q$ is a four-dimensional Euclidean integral of $F\widetilde F$. It is not the magnetic charge of a monopole. The two are related in some compactified or finite-temperature settings, but they are not the same diagnostic.

**Ignoring the global form of the gauge group.** Local formulas use the Lie algebra. The allowed bundles, line operators, and possible fractional topological charges can depend on whether the gauge group is $SU(N)$, $SU(N)/\mathbb Z_N$, or something else.

**Treating all Euclidean saddles as self-dual.** Self-dual fields saturate the instanton bound. General Yang–Mills solutions need not be self-dual, and bounces for false-vacuum decay have a different negative-mode structure.

## Relations to other pages

[Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/) explains the finite-action and boundary-data logic before specializing to Yang–Mills theory.

[Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) makes the integer $Q$ precise and relates it to Chern–Simons number.

[Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) explains how theta dependence is measured through

$$
\chi_{\rm top}
=
\frac{1}{V}\langle Q^2\rangle_{\theta=0}.
$$

[Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) explain the general machinery behind the $x_0$, $\rho$, and gauge-orientation integrations.

[Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/) is the nearby soliton page. Monopoles are finite-energy objects in space; instantons are finite-action objects in Euclidean spacetime.

## Research status

**Established.** The BPST solution, self-duality equations, action bound, charge normalization, and basic collective-coordinate structure are standard. The role of instantons in theta dependence and anomaly-induced fermion selection rules is also standard.

**Semiclassical but conditional.** Instanton calculus is reliable when the relevant instantons are small or otherwise controlled, and when the saddle expansion, zero modes, determinant, and measure are all treated consistently.

**Active.** The relation between instantons, renormalons, resurgence, confinement, dense instanton ensembles, real-time dynamics, and strongly coupled QCD-like vacua remains subtle. Instantons are part of the nonperturbative story, not the whole story.

## Exercises

### Exercise 1: Derive the action bound

Using the definitions above, show that

$$
S_{E,\mathrm{YM}}
\ge
\frac{8\pi^2}{g^2}\lvert Q\rvert.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
0\le
\int d^4x\,\operatorname{tr}(F_{\mu\nu}\mp\widetilde F_{\mu\nu})
(F_{\mu\nu}\mp\widetilde F_{\mu\nu}).
$$

Expanding gives

$$
0\le
2\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\mp
2\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
$$

where we used $\widetilde F_{\mu\nu}\widetilde F_{\mu\nu}=F_{\mu\nu}F_{\mu\nu}$ in Euclidean signature. Hence

$$
\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\ge
\pm16\pi^2 Q.
$$

Choose the sign so that the right side is positive. Multiplying by $1/(2g^2)$ gives

$$
S_{E,\mathrm{YM}}
\ge
\frac{8\pi^2}{g^2}\lvert Q\rvert.
$$

Equality holds when $F=\pm\widetilde F$.

</details>

### Exercise 2: Check the BPST density normalization

Verify that

$$
q(x)=\frac{6\rho^4}{\pi^2[(x-x_0)^2+\rho^2]^4}
$$

integrates to one on $\mathbb R^4$.

<details><summary><strong>Solution</strong></summary>

By translation invariance set $x_0=0$. In four-dimensional spherical coordinates,

$$
d^4x=2\pi^2 r^3dr.
$$

Then

$$
\int d^4x\,q(x)
=
\frac{6\rho^4}{\pi^2}2\pi^2
\int_0^\infty dr\,\frac{r^3}{(r^2+\rho^2)^4}.
$$

Let $u=r^2$, so $r^3dr=\frac12u\,du$. Then

$$
\int_0^\infty dr\,\frac{r^3}{(r^2+\rho^2)^4}
=
\frac12\int_0^\infty du\,\frac{u}{(u+\rho^2)^4}
=
\frac{1}{12\rho^4}.
$$

Therefore

$$
\int d^4x\,q(x)
=
\frac{6\rho^4}{\pi^2}2\pi^2\frac{1}{12\rho^4}=1.
$$

</details>

## References

- A. Belavin, A. Polyakov, A. Schwartz, and Y. Tyupkin, “Pseudoparticle Solutions of the Yang–Mills Equations,” for the original instanton solution.
- G. ’t Hooft, “Computation of the Quantum Effects Due to a Four-Dimensional Pseudoparticle,” for instanton calculus and fermion zero modes.
- M. Srednicki, *Quantum Field Theory*, especially the chapter on instantons and theta vacua.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapter on instantons and the explicit BPST construction.
- M. Mariño, *Instantons and Large N*, especially the chapters on Yang–Mills instantons and instanton calculus.
- S. Coleman, *Aspects of Symmetry*, for the semiclassical and tunneling viewpoint.
- M. Nakahara, *Geometry, Topology and Physics*, for the differential-geometric interpretation of self-dual gauge fields and characteristic classes.

## Version history

- **2026-06-27:** Initial polished draft. Added after Instantons in Field Theory as the first dedicated Yang–Mills instanton page.
