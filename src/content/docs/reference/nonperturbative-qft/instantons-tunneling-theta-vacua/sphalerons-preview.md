---
title: "Sphalerons"
description: "Explains sphalerons as unstable finite-energy saddle configurations, their relation to instantons, Chern–Simons number, thermal activation, and anomalous charge violation."
sidebar:
  label: "Sphalerons"
  order: 11
level: Advanced
status: "Polished draft"
source: "Klinkhamer–Manton; Coleman; Shifman ch. 5; Schwartz ch. 30; Weinberg Vol. II."
topics:
  - sphalerons
  - instantons
  - Chern–Simons number
  - electroweak baryon number violation
  - anomalous symmetries
  - thermal field theory
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - sphalerons
  - anomalies
  - theta-vacua
researchStatus:
  established:
    - "A sphaleron is an unstable finite-energy saddle of the static energy functional, sitting near the top of the barrier between topologically distinct vacua in gauge-Higgs theories."
  active:
    - "Precise real-time sphaleron rates in hot gauge theories require nonperturbative thermal and nonequilibrium methods; electroweak baryogenesis is sensitive to physics beyond the minimal Standard Model."
---

## Summary

A sphaleron is a static, unstable, finite-energy field configuration that sits at the top of an energy barrier separating classically distinct vacua. It is not an instanton. An instanton is a Euclidean finite-action path through configuration space; a sphaleron is a saddle point of the real-time Hamiltonian energy functional.

The clean mental picture is

$$
\text{instanton}
=\text{tunneling path through the barrier},
\qquad
\text{sphaleron}
=\text{unstable point on top of the barrier}.
$$

In Yang–Mills–Higgs theory, the relevant coordinate along the barrier is often represented by the Chern–Simons number $N_{\rm CS}$. Neighboring vacua differ by an integer shift of $N_{\rm CS}$, while the sphaleron lies roughly halfway between them.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A schematic barrier between gauge vacua labeled by Chern–Simons number, with a sphaleron at the top and instanton tunneling under the barrier.](/figures/nonperturbative-qft/sphaleron-barrier-cs-number.svg)

<figcaption>

A sphaleron is the unstable configuration near the top of the barrier between neighboring gauge vacua. Instantons describe Euclidean tunneling through the barrier; finite-temperature transitions can go over it. The horizontal coordinate is schematic Chern–Simons number $N_{\rm CS}$.

</figcaption>
</figure>

Sphalerons matter because anomalous global charges can change when the gauge field moves between neighboring topological sectors. In the electroweak Standard Model,

$$
\Delta B=\Delta L=N_g\,\Delta N_{\rm CS},
\qquad
\Delta(B-L)=0,
$$

where $N_g=3$ is the number of generations. At zero temperature such transitions are fantastically suppressed. At high temperature, thermal fluctuations can cross the sphaleron barrier and make anomalous baryon-plus-lepton violation physically important.

## Prerequisites

You should know [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/), and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/).

The page also uses the idea of a saddle with one negative mode from [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) and [One-Loop Determinants Around Saddles](/nonperturbative-qft/semiclassical-methods/one-loop-determinants-around-saddles/).

## Core idea

Gauge theories can have many classical vacua that are locally pure gauge but globally distinct. In a Yang–Mills theory on a spatial slice, these vacua can be labeled by an integer winding number. A continuous path in configuration space can connect neighboring vacua, but it must climb an energy barrier.

The instanton story asks for the least-action Euclidean trajectory connecting two sectors. The sphaleron story asks for the highest point along the least-energy pass between them. This is the field-theory analogue of a mountain pass. If the system is cold, it tunnels through the mountain; if it is hot, it can be kicked over the pass.

This distinction matters because instanton amplitudes are naturally Euclidean and exponentially suppressed by an action such as $e^{-8\pi^2/g^2}$. Sphaleron transitions are thermal or real-time processes. Their suppression in the broken phase is Boltzmann-like, roughly $e^{-E_{\rm sph}/T}$, and in the symmetric high-temperature phase the rate is a dynamical property of the hot gauge plasma.

## Setup and conventions

We use the conventions of [Conventions and Notation](/nonperturbative-qft/conventions/). Let $A_i$ denote a spatial gauge field on a fixed time slice, and let $E[A,\phi]$ denote the static energy functional of a gauge-Higgs theory. A sphaleron is a stationary point

$$
\delta E[A,\phi]=0
$$

with finite energy and at least one negative fluctuation direction.

For electroweak applications, one usually studies the bosonic $SU(2)\times U(1)$ gauge-Higgs sector, often starting with the simplified $SU(2)$-Higgs model. The exact numerical sphaleron profile depends on the Higgs self-coupling and weak mixing angle, but the structural points do not: the sphaleron is localized, static, unstable, and carries Chern–Simons number near a half-integer in a suitable convention.

The Chern–Simons number is not itself a gauge-invariant real number under all large gauge transformations. Its change along a history is the physical datum:

$$
\Delta N_{\rm CS}=Q,
$$

where $Q$ is the four-dimensional topological charge of the gauge-field history.

## Sphalerons versus instantons

The two objects are closely related, but they answer different variational problems.

| Object | Variational problem | Lives in | Main use |
|---|---|---|---|
| Instanton | stationary point of Euclidean action $S_E$ | Euclidean spacetime | tunneling amplitude, theta dependence, anomalous vertices |
| Bounce | stationary point of $S_E$ with a false-vacuum boundary condition | Euclidean spacetime | decay rate of a metastable vacuum |
| Sphaleron | stationary point of static energy $E$ with one unstable direction | spatial configuration space | thermal/topological transitions over a barrier |

A one-instanton history in Yang–Mills theory changes $N_{\rm CS}$ by one unit between early and late Euclidean times. The sphaleron sits on a spatial time slice near the midpoint of the corresponding barrier. In the electroweak theory, this is why the same topology that appears in the anomaly equation also appears in high-temperature baryon-number violation.

The saddle has one negative mode because it is not a local minimum. One direction rolls down toward one vacuum; the opposite direction rolls down toward the neighboring vacuum. Quantizing fluctuations around a sphaleron is therefore not like quantizing around a stable soliton. The negative direction is the direction of transition, not a particle mode.

## Chern–Simons number and anomalous charge violation

The anomaly equation relates the divergence of a current to a topological density. Schematically, for baryon and lepton number in the electroweak theory,

$$
\partial_\mu J_B^\mu
=\partial_\mu J_L^\mu
=N_g\frac{g^2}{32\pi^2}W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

Integrating over spacetime gives

$$
\Delta B=\Delta L=N_g Q,
$$

where

$$
Q=\frac{g^2}{32\pi^2}\int d^4x\,W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

For histories connecting neighboring vacua, $Q=\Delta N_{\rm CS}\in\mathbb Z$. Thus a transition with $\Delta N_{\rm CS}=1$ changes baryon and lepton number by three units in the Standard Model, while preserving $B-L$.

This is a nonperturbative effect. The anomaly equation is local and exact, but a perturbative fluctuation around one vacuum cannot change the integer label of the gauge field at infinity. The change requires a topologically nontrivial history or a real-time thermal excursion over the barrier.

## Energy scale and thermal activation

In the $SU(2)$-Higgs theory, dimensional analysis and classical scaling give the characteristic sphaleron energy

$$
E_{\rm sph}\sim \frac{4\pi v}{g}\,\mathcal B\!\left(\frac{\lambda}{g^2}\right),
$$

where $v$ is the Higgs vacuum expectation value, $g$ is the weak gauge coupling, $\lambda$ is the Higgs self-coupling, and $\mathcal B$ is a dimensionless number obtained from the classical profile.

At temperatures well below the barrier, the transition rate is Boltzmann suppressed:

$$
\Gamma \propto e^{-E_{\rm sph}/T}
$$

up to prefactors and fluctuation determinants. Near and above the electroweak crossover, the broken-phase barrier description becomes less literal, and one must use finite-temperature gauge theory. The rate is then a real-time transport problem, not just a Euclidean saddle calculation.

The important lesson is qualitative but sharp:

| Regime | Dominant picture | Suppression |
|---|---|---|
| zero temperature | quantum tunneling | instanton-like $e^{-8\pi^2/g^2}$ |
| broken phase at finite temperature | thermal activation over a barrier | roughly $e^{-E_{\rm sph}/T}$ |
| symmetric hot plasma | diffusion in Chern–Simons number | nonperturbative thermal rate |

This is why sphalerons are central in baryogenesis and leptogenesis. If a lepton asymmetry is generated above the electroweak scale, sphaleron processes can partially convert it into baryon asymmetry while preserving $B-L$.

## Checks

A useful way to check the topology is to compare the three-dimensional and four-dimensional viewpoints. The change in Chern–Simons number between two times equals the integral of the topological density between those times:

$$
N_{\rm CS}(t_f)-N_{\rm CS}(t_i)
=\frac{g^2}{32\pi^2}\int_{t_i}^{t_f}d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu},
$$

up to the usual convention choices for the normalization of $N_{\rm CS}$. This equation explains why a real-time transition over the sphaleron barrier and a Euclidean instanton tunneling event can produce the same net anomalous charge violation.

A second check is the negative mode. A stable soliton should have nonnegative fluctuation eigenvalues after removing symmetry zero modes. A sphaleron must have one unstable direction: if it did not, it would be a local minimum rather than a barrier-top configuration.

A third check is $B-L$. The electroweak anomaly violates $B+L$ but not $B-L$. Any proposed sphaleron selection rule that changes $B-L$ is not the Standard Model electroweak sphaleron rule.

## Common pitfalls

**A sphaleron is not a Euclidean instanton.** The sphaleron is a static saddle of the energy functional. Instantons are Euclidean spacetime saddles of the action. They are related by the topology of configuration space, not by being the same object.

**The Chern–Simons number is not an ordinary potential coordinate.** It is a useful coordinate on the space of gauge-field configurations modulo subtleties. Only integer changes, or gauge-invariant statements about histories and anomalies, are physical.

**The zero-temperature electroweak rate is not phenomenologically large.** The instanton-like suppression at zero temperature is enormous. Sphalerons become important in hot environments because thermal activation and real-time diffusion change the rate problem.

**Baryon number violation does not automatically mean proton decay.** Electroweak sphaleron processes violate $B$ and $L$ while preserving $B-L$ and involve many fermions. Low-energy proton decay usually points to different, higher-scale interactions.

**The minimal Standard Model does not by itself give successful electroweak baryogenesis.** Sphalerons provide anomalous baryon violation, but successful baryogenesis also requires sufficient CP violation and appropriate departure from equilibrium. The observed Higgs-sector parameters make the minimal scenario inadequate.

## Relations to other pages

- [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) explains why topological gauge histories violate anomalous global charges.
- [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/) gives the vacuum-to-vacuum barrier picture that sphalerons sharpen.
- [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) explains negative modes and decay-rate logic for Euclidean bounces.
- [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/) helps separate dynamical field configurations from external insertions and Hilbert-space sectors.

The next chapter, [Confinement, Screening, and Mass Gap](/nonperturbative-qft/confinement-screening-mass-gap/), uses a different kind of nonperturbative global information: line operators, flux tubes, screening, and spectra.

## Research status

The existence and structure of sphalerons in electroweak-type gauge-Higgs theories are established semiclassical physics. Their relation to anomalous $B+L$ violation is also established: the anomaly fixes the selection rule, while topology supplies the nonperturbative path between sectors.

The rate is more delicate. In the broken phase at weak coupling, a barrier-crossing picture with fluctuation prefactors is useful. In the high-temperature symmetric phase, the Chern–Simons number performs a kind of non-Abelian diffusion, and the rate is a real-time finite-temperature observable. Its quantitative determination requires nonperturbative thermal methods, not just the static sphaleron profile.

For cosmology, sphalerons are necessary ingredients in many baryogenesis and leptogenesis mechanisms, but not sufficient by themselves. The minimal Standard Model has the right anomaly structure but not enough CP violation and not a strong enough electroweak phase transition for successful electroweak baryogenesis.

## Exercises

### Exercise 1: Anomaly selection rule

Assume the electroweak anomaly gives

$$
\partial_\mu J_B^\mu=\partial_\mu J_L^\mu
=N_g\frac{g^2}{32\pi^2}W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

Show that a history with topological charge $Q=1$ changes $B+L$ but preserves $B-L$.

<details>
<summary><strong>Solution</strong></summary>

Integrating the anomaly over spacetime gives

$$
\Delta B=\Delta L=N_g Q.
$$

For $Q=1$, this gives $\Delta B=\Delta L=N_g$. Therefore

$$
\Delta(B+L)=2N_g,
\qquad
\Delta(B-L)=N_g-N_g=0.
$$

For the Standard Model, $N_g=3$, so $\Delta B=\Delta L=3$.

</details>

### Exercise 2: Barrier-top instability

Explain why a sphaleron should have a negative fluctuation mode.

<details>
<summary><strong>Solution</strong></summary>

A sphaleron is a saddle point of the static energy functional, not a local minimum. Along one direction in configuration space, the energy decreases toward one neighboring vacuum; along the opposite direction, it decreases toward the adjacent vacuum. The second variation of the energy must therefore have a negative eigenvalue in the barrier-crossing direction. Symmetry zero modes, such as translations or gauge rotations after gauge fixing, are separate from this physical unstable mode.

</details>

### Exercise 3: Tunneling versus thermal activation

A toy barrier has height $E_b$ and instanton action $S_I$. Write the parametric suppression of a zero-temperature tunneling transition and a finite-temperature over-barrier transition. Which one is more relevant at high temperature?

<details>
<summary><strong>Solution</strong></summary>

The zero-temperature tunneling amplitude is suppressed by a factor of order $e^{-S_I}$, or a rate by a related exponential such as $e^{-2S_I}$ depending on conventions and observable. A thermal over-barrier transition is suppressed by a Boltzmann factor $e^{-E_b/T}$. At sufficiently high temperature, the thermal factor is much less suppressed, and the barrier-crossing picture becomes the relevant one. In gauge theory, the precise hot-phase rate is a real-time nonperturbative observable, but this toy comparison captures the reason sphalerons matter thermally.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, for semiclassical tunneling, false-vacuum decay, and the physical interpretation of saddle points.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussion of instantons, anomalies, baryon-number violation, and the height of the barrier.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for anomalies in the Standard Model and the baryon/lepton-number selection rule.

### Deeper references

- F. Klinkhamer and N. Manton, “A Saddle-Point Solution in the Weinberg–Salam Theory,” for the original electroweak sphaleron.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory, anomalies, and nonperturbative baryon-number violation.
- A. Ringwald, “Electroweak Instantons/Sphalerons at Very High Energies,” for a review-oriented entry into high-energy and thermal sphaleron physics.

## Version history

- **2026-06-27:** Initial polished page, added as the final bridge from instantons and theta vacua to confinement, screening, and mass-gap diagnostics.
