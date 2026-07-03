---
title: "Coleman–Mermin–Wagner Theorem Preview"
description: "Explains why continuous symmetries cannot be spontaneously broken in low dimensions under standard assumptions, using Goldstone infrared fluctuations, order-parameter correlations, and QFT/statistical-mechanics comparisons."
sidebar:
  label: "Coleman–Mermin–Wagner"
  order: 9
level: Graduate
status: "Polished draft"
source: "Coleman 1973; Mermin–Wagner 1966; Hohenberg 1967; Coleman on secret symmetry; Zinn-Justin on critical phenomena; Altland–Simons on broken symmetry and collective modes."
topics:
  - Coleman theorem
  - Mermin–Wagner theorem
  - Hohenberg theorem
  - infrared fluctuations
  - low-dimensional QFT
  - spontaneous symmetry breaking
  - Goldstone modes
  - Berezinskii-Kosterlitz-Thouless transition
canonicalTopics:
  - coleman-theorem
  - mermin-wagner-theorem
  - hohenberg-theorem
  - infrared-fluctuation
  - low-dimensional-qft
  - spontaneous-symmetry-breaking
  - goldstone-mode
  - quasi-long-range-order
researchStatus:
  established:
    - "Under standard locality, positivity, finite-temperature or relativistic-QFT assumptions, continuous internal symmetries cannot be spontaneously broken in the relevant low-dimensional settings."
    - "The obstruction is infrared: the massless Goldstone fluctuations required by spontaneous breaking are too large to allow a nonzero local order parameter."
  active:
    - "Modern refinements concern long-range interactions, nonequilibrium systems, gauge constraints, generalized symmetries, defects, topological transitions, finite-size crossovers, and singular large-N limits."
---

## Summary

The **Coleman–Mermin–Wagner theorem** is the low-dimensional warning label on Goldstone’s theorem.

Goldstone’s theorem says that, under suitable assumptions, spontaneous breaking of a continuous global symmetry produces massless modes. In low dimensions, those same massless modes fluctuate so strongly in the infrared that they destroy the assumed order.

The slogan is

$$
\text{continuous symmetry breaking wants a massless field},
$$

but in low dimensions,

$$
\text{the massless field fluctuates too much to choose a direction}.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![A flowchart showing that continuous spontaneous symmetry breaking implies a would-be Goldstone field. Its long-distance fluctuations are controlled by an infrared integral that is finite above the critical dimension but divergent at or below it, obstructing ordinary continuous order.](/figures/symmetry-anomalies-topology/coleman-mermin-wagner-ir-flow.svg)

<figcaption>

A Goldstone mode has low-energy fluctuations controlled by an integral of the form $\int d^Dk/k^2$ in the finite-temperature classical regime, or by the two-dimensional Euclidean massless scalar Green function in $1+1$-dimensional relativistic QFT. The marginal logarithm is enough to destroy a nonzero continuous order parameter.

</figcaption>
</figure>

There are two closely related statements:

| Name | Setting | Rough statement |
|---|---|---|
| Coleman theorem | relativistic QFT in $1+1$ spacetime dimensions | no spontaneous breaking of continuous internal symmetries under standard assumptions |
| Mermin–Wagner–Hohenberg theorem | statistical or many-body systems at finite temperature in $D\le2$ spatial dimensions with sufficiently short-range interactions | no long-range order from breaking continuous symmetries |

The theorem does **not** say that low-dimensional systems are trivial. Quite the opposite: once ordinary long-range order is forbidden, quasi-long-range order, topological defects, bosonization, conformal field theory, and Berezinskii–Kosterlitz–Thouless physics become central. Low dimensions often replace order parameters by more refined infrared diagnostics.

## Prerequisites

Read [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/), [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/), and [Nonlinear Sigma Models Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/) first.

For the order-parameter side, review [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) and [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/). For the current-algebra side, review [Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/).

## Core idea

The theorem is easiest to understand by assuming the opposite and watching the effective theory sabotage the assumption.

Suppose a continuous internal symmetry is spontaneously broken. Then at long distance there is a Goldstone field. For a single $U(1)$ example, write the order parameter as

$$
\Phi(x)\sim v e^{i\theta(x)}.
$$

The low-energy action for the phase is

$$
S_{\rm eff}\sim \frac{\rho}{2}\int d^D x\,(\nabla\theta)^2
$$

for a $D$-dimensional finite-temperature statistical system, or

$$
S_{\rm eff}\sim \frac{f^2}{2}\int d^2x\,\partial_\mu\theta\partial^\mu\theta
$$

in two-dimensional Euclidean spacetime for a $1+1$-dimensional relativistic QFT.

The order parameter is not $\theta$ itself. It is the exponential $e^{i\theta}$. Gaussian fluctuations give

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
=\exp\left[-\frac12\langle(\theta(x)-\theta(0))^2\rangle\right].
$$

If $\langle\theta^2\rangle$ diverges strongly enough with distance or volume, the system cannot maintain a nonzero expectation value of $e^{i\theta}$. The phase wanders too much.

In higher dimensions, the long-wavelength fluctuations can be finite enough for long-range order to survive. In low dimensions, they are not.

## Setup and conventions

Use $D$ for the number of spatial dimensions in a finite-temperature many-body or statistical system. Use $d=D+1$ for Lorentzian spacetime dimension in relativistic QFT.

There are two related infrared integrals:

1. For a finite-temperature ordered phase with classical long-wavelength Goldstone fluctuations,

$$
\langle\theta^2\rangle_{\rm IR}
\sim
T\int_{1/L}^{\Lambda}\frac{d^Dk}{(2\pi)^D}\frac{1}{\rho k^2}.
$$

2. For a zero-temperature relativistic massless scalar in $1+1$ dimensions, the Euclidean two-point function is governed by

$$
\int\frac{d^2p}{(2\pi)^2}\frac{e^{ip\cdot x}}{p^2},
$$

which has a logarithmic infrared sensitivity.

Here $L$ is an infrared length scale, $\Lambda$ is a UV cutoff, $T$ is temperature, and $\rho$ is the stiffness.

:::note[Source note: dimensions]
Different communities count dimensions differently. Mermin–Wagner–Hohenberg is usually stated for $D\le2$ spatial dimensions at finite temperature. Coleman's theorem is usually stated for $1+1$ spacetime dimensions at zero temperature in relativistic QFT. Both involve a two-dimensional Euclidean infrared logarithm in the simplest Goldstone effective description.
:::

The theorem is about continuous **global** symmetries and local order parameters under appropriate assumptions. Gauge redundancy, discrete symmetries, long-range interactions, finite systems, and topological order require separate discussion.

## The infrared integral

The finite-temperature Goldstone fluctuation integral is

$$
I_D(L)=\int_{1/L}^{\Lambda}\frac{d^Dk}{(2\pi)^D}\frac{1}{k^2}.
$$

At small $k$, the angular part gives

$$
I_D(L)\sim \int_{1/L}^{\Lambda}dk\,k^{D-3}.
$$

Therefore

$$
I_D(L)\sim
\begin{cases}
L, & D=1,\\
\log(\Lambda L), & D=2,\\
\text{finite as }L\to\infty, & D>2.
\end{cases}
$$

For $D\le2$, the fluctuations grow without bound as the system size grows. For $D=2$, the growth is only logarithmic, but logarithmic infinity is still infinity. It is slow enough to allow quasi-long-range order, but not true long-range order for a continuous local order parameter.

For the $1+1$-dimensional relativistic quantum problem, the equal-time zero-temperature fluctuation of a massless mode is roughly

$$
\int_{1/L}^{\Lambda}\frac{dk}{2|k|}\sim\log(\Lambda L),
$$

again logarithmically divergent.

## How the order parameter disappears

Consider the $U(1)$ order parameter

$$
\Phi(x)=v e^{i\theta(x)}.
$$

If $\theta$ is Gaussian at long distances, then

$$
\langle\Phi(x)\Phi^*(0)\rangle
\sim
v^2\exp\left[-\frac12\langle(\theta(x)-\theta(0))^2\rangle\right].
$$

In two Euclidean dimensions,

$$
\langle(\theta(x)-\theta(0))^2\rangle
\sim
\frac{1}{\pi K}\log\frac{|x|}{a},
$$

where $K$ is a stiffness-like constant and $a$ is a short-distance cutoff. Thus

$$
\langle\Phi(x)\Phi^*(0)\rangle
\sim
\frac{1}{|x|^\eta}
$$

for some positive exponent $\eta$.

Power-law decay is not long-range order. A nonzero order parameter would imply

$$
\lim_{|x|\to\infty}\langle\Phi(x)\Phi^*(0)\rangle
=|\langle\Phi\rangle|^2\ne0.
$$

Instead the correlator decays to zero, although only algebraically. This is why two-dimensional $XY$-type systems can have quasi-long-range order without ordinary spontaneous breaking of the continuous symmetry.

## Coleman theorem in relativistic QFT

Coleman's theorem says, roughly, that continuous internal symmetries cannot be spontaneously broken in relativistic QFT in $1+1$ spacetime dimensions, assuming the usual positivity, locality, spectral, and regularity conditions.

The proof is not merely the handwavy statement “the massless scalar diverges.” But that handwavy statement captures the mechanism. A broken continuous symmetry would require a Goldstone contribution to a current-order-parameter correlator. In two spacetime dimensions, the corresponding massless scalar behavior is too infrared singular for the assumed local order parameter and clustering properties.

The result is sometimes summarized as

$$
\text{no Goldstone bosons from spontaneous breaking in }1+1\text{ dimensions}.
$$

More precisely, the theorem rules out the Goldstone phenomenon associated with a nonzero local order parameter for a continuous internal symmetry under the theorem's assumptions. Two-dimensional theories can still contain massless excitations, current algebras, conformal fields, and bosonized scalar variables. The point is that they do not arise as ordinary Goldstone bosons of a spontaneously broken continuous internal symmetry.

This distinction is crucial in two-dimensional CFT and bosonization. A compact boson can have a shift symmetry and vertex operators with algebraic correlations, but not a nonzero expectation value of $e^{i\theta}$ selecting a point on a circle of vacua.

## Mermin–Wagner–Hohenberg theorem

The Mermin–Wagner–Hohenberg theorem is the statistical-mechanics and many-body counterpart. It forbids spontaneous breaking of continuous symmetries at finite temperature in $D\le2$ spatial dimensions, under conditions such as sufficiently short-range interactions.

The finite-temperature qualification is essential. At nonzero temperature, the static long-wavelength mode behaves classically and produces the integral

$$
T\int\frac{d^Dk}{k^2}.
$$

For $D=2$, the logarithm is the same infrared enemy as in Coleman's two-dimensional Euclidean QFT argument. For $D=1$, the divergence is even stronger.

The theorem was originally formulated in magnetic and many-body contexts, but the underlying lesson is broad:

$$
\text{continuous long-range order is fragile in low dimensions}.
$$

It is not a statement that all phase transitions are impossible in two dimensions. The two-dimensional Ising model has a discrete symmetry and does order. The two-dimensional $XY$ model has a Berezinskii–Kosterlitz–Thouless transition, but not ordinary spontaneous breaking of the continuous $U(1)$ symmetry.

## Relation to Goldstone’s theorem

There is no contradiction between Goldstone’s theorem and Coleman–Mermin–Wagner.

Goldstone’s theorem says:

> If a continuous symmetry is spontaneously broken and the standard assumptions hold, then massless excitations follow.

Coleman–Mermin–Wagner says:

> In the relevant low-dimensional settings, the assumptions needed for ordinary spontaneous breaking cannot all be satisfied.

The massless mode predicted by Goldstone’s theorem would be too infrared singular. Thus the correct conclusion is not “there is breaking but no Goldstone.” The correct conclusion is “there is no ordinary continuous symmetry breaking of the assumed kind.”

In logical form:

$$
\text{SSB}\Rightarrow\text{Goldstone mode},
$$

but in low dimensions,

$$
\text{Goldstone mode}\Rightarrow\text{IR fluctuations destroy SSB}.
$$

So SSB is excluded.

## What survives in two dimensions

Two-dimensional systems often replace long-range order by more delicate structures.

### Quasi-long-range order

A two-dimensional $XY$ model at low temperature can have algebraically decaying correlations,

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
\sim |x|^{-\eta(T)}.
$$

This is not a nonzero order parameter, but it is much more ordered than exponential decay.

### BKT transitions

The Berezinskii–Kosterlitz–Thouless transition is driven by vortices, not by the onset of a nonzero local order parameter. Below the transition, vortices are bound and correlations decay algebraically. Above it, vortices proliferate and correlations decay exponentially.

This is a beautiful loophole only if one states the theorem badly. Properly stated, there is no loophole: the BKT transition is not spontaneous breaking of a continuous symmetry with a local order parameter.

### Bosonization and current algebra

In $1+1$ dimensions, massless scalar fields, compact bosons, fermions, and current algebras are deeply related. These theories can have exact continuous symmetries and rich operator spectra. Coleman theorem does not erase them; it tells us how not to interpret them.

### Discrete symmetry breaking

The theorem is about continuous symmetries. Discrete symmetry breaking can occur in low-dimensional quantum systems at zero temperature and in two-dimensional classical statistical systems at finite temperature. The Ising model is the canonical example.

## What the theorem does not say

**It does not forbid discrete symmetry breaking.**

A discrete order parameter has no Goldstone field, so the massless-fluctuation argument does not apply.

**It does not forbid all phase transitions in two dimensions.**

BKT transitions, Ising transitions, topological transitions, and CFT critical points are all compatible with the theorem.

**It does not say finite systems cannot look ordered.**

A large but finite two-dimensional magnet can have a very long correlation length and can look ordered on laboratory scales. The theorem concerns the infinite-volume limit.

**It does not apply unchanged to long-range interactions.**

If interactions decay slowly enough, the infrared cost of twisting the order parameter changes. The standard theorem assumes sufficiently short-range interactions.

**It does not apply to gauge redundancy as if gauge redundancy were a global symmetry.**

Gauge redundancy is not a physical symmetry that breaks in the same sense. Elitzur's theorem and the Higgs mechanism involve different logic.

**It does not forbid topological order.**

Topological order is not diagnosed by a local order parameter transforming under a continuous internal symmetry.

**It does not make all large-N saddle points trustworthy.**

Large-$N$ limits can be singular. A saddle may show an order parameter that is washed out at any finite $N$ in low dimensions.

## A quick dimension guide

The following guide is only for ordinary continuous internal symmetries with local order parameters and short-range interactions.

| Setting | Long-range continuous order? | Comment |
|---|---:|---|
| $D=1$ finite temperature | no | thermal fluctuations are too strong |
| $D=2$ finite temperature | no | logarithmic Goldstone fluctuations |
| $D>2$ finite temperature | possible | theorem no longer forbids it |
| $1+1$ relativistic QFT at zero temperature | no | Coleman theorem |
| $2+1$ relativistic QFT at zero temperature | possible | ordinary Goldstone phases exist |

This table is not a substitute for checking assumptions. It is a map of the standard cases.

## Relation to pseudo-Goldstone bosons

Adding a small explicit-breaking term gives the would-be Goldstone mode a mass. A mass cuts off the infrared divergence:

$$
\int\frac{d^Dk}{k^2+m^2}
$$

is less singular at small $k$ than the massless integral.

Does that mean a two-dimensional system can have a nonzero order parameter once the symmetry is explicitly broken? Yes, but then it is not spontaneous breaking of the continuous symmetry. The source pins the direction. The real test is what happens as the explicit breaking is removed after the infinite-volume limit.

In low dimensions, the pseudo-Goldstone mass can produce a very large correlation length,

$$
\xi\sim \frac{1}{m_\pi},
$$

so the system may look ordered for distances $|x|\ll\xi$. At distances much larger than $\xi$, the explicit pinning and infrared physics determine the actual behavior.

## Common pitfalls

**Pitfall 1: “Coleman–Mermin–Wagner says there are no massless bosons in two dimensions.”**

No. It says there are no Goldstone bosons arising from ordinary spontaneous breaking of continuous internal symmetry under the theorem's assumptions. Two-dimensional theories can certainly be massless.

**Pitfall 2: “Power-law correlations mean spontaneous symmetry breaking.”**

No. True long-range order requires the correlator to approach a nonzero constant at large distance.

**Pitfall 3: “A finite simulation with magnetization disproves the theorem.”**

No. Finite volume, finite time, weak anisotropy, boundary conditions, and explicit sources can all mimic order.

**Pitfall 4: “The theorem forbids the BKT transition.”**

No. The BKT transition is not a Landau transition with a local order parameter acquiring a nonzero expectation value.

**Pitfall 5: “The theorem applies to discrete symmetry.”**

No. Discrete symmetry has no Goldstone field, and the Ising model is the standard counterexample to that overstatement.

**Pitfall 6: “The theorem applies to every interaction.”**

No. Long-range interactions can change the infrared estimates. The usual theorem assumes sufficiently short-range interactions.

## Relations to other pages

This page qualifies [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) by explaining when its premise fails in low dimensions.

It connects to [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) because the obstruction is precisely the infrared behavior of the Goldstone mode.

It prepares for pages on two-dimensional field theory, bosonization, orbifolds, BKT physics, and CFT. It also cross-links conceptually to [Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) and [Pseudo-Goldstone Bosons](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/pseudo-goldstone-bosons/), where small explicit breaking cuts off infrared wandering but also changes the question.

## Research status

The core theorem is established. Its proofs and variants are standard in rigorous statistical mechanics, many-body theory, and relativistic QFT.

Active work concerns boundaries and refinements: long-range interactions, non-equilibrium steady states, driven systems, disorder, finite-size scaling, quasi-long-range order, topological transitions, large-$N$ limits, gauge constraints, generalized symmetries, and low-dimensional phases not captured by a local order parameter.

For this chapter, the theorem is a preview rather than a full rigorous treatment. A later low-dimensional symmetry technology chapter should return to compact bosons, BKT transitions, bosonization, and two-dimensional current algebra in detail.

## Exercises

### Exercise 1: Infrared divergence by dimension

Evaluate the infrared behavior of

$$
I_D(L)=\int_{1/L}^{\Lambda}dk\,k^{D-3}
$$

for $D=1,2,3$.

<details><summary><strong>Solution</strong></summary>

For $D=1$,

$$
I_1(L)=\int_{1/L}^{\Lambda}\frac{dk}{k^2}
=L-\frac{1}{\Lambda},
$$

so it diverges linearly with $L$.

For $D=2$,

$$
I_2(L)=\int_{1/L}^{\Lambda}\frac{dk}{k}
=\log(\Lambda L),
$$

so it diverges logarithmically.

For $D=3$,

$$
I_3(L)=\int_{1/L}^{\Lambda}dk
=\Lambda-\frac1L,
$$

so it is finite as $L\to\infty$.

</details>

### Exercise 2: Algebraic decay from logarithmic wandering

Suppose

$$
\langle(\theta(x)-\theta(0))^2\rangle=A\log\frac{|x|}{a}.
$$

Show that

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
$$

decays as a power law in a Gaussian approximation.

<details><summary><strong>Solution</strong></summary>

For a Gaussian variable $X$, $\langle e^{iX}\rangle=e^{-\langle X^2\rangle/2}$. Taking

$$
X=\theta(x)-\theta(0),
$$

we get

$$
\langle e^{i\theta(x)}e^{-i\theta(0)}\rangle
=
\exp\left[-\frac{A}{2}\log\frac{|x|}{a}\right]
=\left(\frac{a}{|x|}\right)^{A/2}.
$$

Thus the decay is algebraic, not constant.

</details>

### Exercise 3: Why discrete symmetry is different

Why does the infrared Goldstone argument not forbid Ising order in two-dimensional classical statistical mechanics?

<details><summary><strong>Solution</strong></summary>

The Ising order parameter is associated with a discrete $\mathbb Z_2$ symmetry. Breaking a discrete symmetry does not produce a continuous family of vacua and therefore does not produce a massless Goldstone field. The infrared integral $\int d^Dk/k^2$ describes long-wavelength Goldstone fluctuations of continuous order, so it does not apply to the Ising order parameter.

</details>

### Exercise 4: Explicit pinning

Add a small explicit-breaking field $h$ to a two-dimensional $XY$ model. Why can the magnetization be nonzero at finite $h$ without contradicting Mermin–Wagner?

<details><summary><strong>Solution</strong></summary>

The theorem forbids spontaneous breaking of the continuous symmetry. A nonzero $h$ explicitly breaks the symmetry and selects a direction. The resulting magnetization is induced by the external field, not spontaneously selected by the infinite-volume system. The correct spontaneous-breaking test requires studying the order of limits as $h\to0$ and $L\to\infty$.

</details>

### Exercise 5: Massive cutoff of the logarithm

Estimate the infrared behavior of

$$
\int_{1/L}^{\Lambda}\frac{d^2k}{(2\pi)^2}\frac{1}{k^2+m^2}
$$

for small nonzero $m$.

<details><summary><strong>Solution</strong></summary>

Using polar coordinates,

$$
\int\frac{d^2k}{(2\pi)^2}\frac{1}{k^2+m^2}
=\frac{1}{2\pi}\int_{1/L}^{\Lambda}\frac{k\,dk}{k^2+m^2}.
$$

For $L\gg1/m$,

$$
\frac{1}{2\pi}\int_0^{\Lambda}\frac{k\,dk}{k^2+m^2}
=\frac{1}{4\pi}\log\frac{\Lambda^2+m^2}{m^2}
\sim\frac{1}{2\pi}\log\frac{\Lambda}{m}.
$$

The mass cuts off the infrared divergence at $k\sim m$.

</details>

## References

- S. Coleman, “There are no Goldstone bosons in two dimensions,” **Communications in Mathematical Physics** 31, 259–264 (1973).
- N. D. Mermin and H. Wagner, “Absence of Ferromagnetism or Antiferromagnetism in One- or Two-Dimensional Isotropic Heisenberg Models,” **Physical Review Letters** 17, 1133–1136 (1966).
- P. C. Hohenberg, “Existence of Long-Range Order in One and Two Dimensions,” **Physical Review** 158, 383–386 (1967).
- V. L. Berezinskii, “Destruction of Long-range Order in One-dimensional and Two-dimensional Systems having a Continuous Symmetry Group,” **Soviet Physics JETP** 32, 493 (1971).
- J. M. Kosterlitz and D. J. Thouless, “Ordering, metastability and phase transitions in two-dimensional systems,” **Journal of Physics C** 6, 1181–1203 (1973).
- S. Coleman, **Aspects of Symmetry**, especially “Secret Symmetry.”
- J. Zinn-Justin, **Quantum Field Theory and Critical Phenomena**, chapters on critical phenomena and low-dimensional field theory.
- A. Altland and B. Simons, **Condensed Matter Field Theory**, chapters on broken symmetry, collective phenomena, renormalization group, and topological field theory.

## Version history

- 2026-06-17: First polished draft. Added infrared-fluctuation derivation, Coleman/Mermin–Wagner comparison, BKT caveats, and exercises.
