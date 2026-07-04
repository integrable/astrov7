---
title: "Tunneling Between Vacua"
description: "Explains how finite-action Euclidean saddles generate transition amplitudes between topological vacua and produce theta-dependent nonperturbative effects."
sidebar:
  label: "Tunneling Between Vacua"
  order: 6
level: Advanced
status: "Polished draft"
source: "Coleman; Srednicki ch. 93; Mariño chs. 1 and 4; Shifman chs. 5 and 7; Polyakov."
topics:
  - tunneling
  - instantons
  - theta vacua
  - Chern–Simons number
  - dilute instanton gas
  - semiclassical transition amplitudes
canonicalTopics:
  - nonperturbative-qft
  - tunneling
  - instantons
  - theta-vacua
  - semiclassical-methods
researchStatus:
  established:
    - "Finite-action Euclidean saddles give the leading semiclassical transition amplitudes between classically separated sectors when the saddle expansion is controlled."
  active:
    - "In strongly coupled gauge theory, large instantons, dense ensembles, finite-temperature transitions, and resurgence require tools beyond the elementary dilute tunneling picture."
---

## Summary

Tunneling between vacua is the dynamical side of theta vacua. The previous page explained why gauge theory has Bloch-like states

$$
|\theta\rangle=\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

This page explains what produces the mixing among the $|n\rangle$ sectors. In Euclidean time, a finite-action instanton trajectory can begin in a vacuum with Chern–Simons label $n$ and end in a vacuum with label $n+1$. Its leading contribution is exponentially small,

$$
\langle n+1|e^{-HT}|n\rangle
\sim
K\,e^{-S_I},
\qquad
S_I=\frac{8\pi^2}{g^2}
$$

for a charge-one Yang–Mills instanton in the weak-coupling semiclassical normalization.

More generally, a history connecting $n_-$ to $n_+$ has topological charge

$$
Q=n_+-n_-,
$$

and the leading action for well-separated unit instantons is roughly

$$
S_E\simeq |Q|S_I.
$$

In a theta sector, summing instantons and anti-instantons gives the familiar leading dilute-gas form

$$
\mathcal E(\theta)
=
\mathcal E_{\rm pert}-2\kappa e^{-S_I}\cos\theta+\text{higher corrections},
$$

where $\kappa$ is the one-instanton density including zero-mode measures, determinant ratios, and renormalization factors.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Tunneling between neighboring topological vacua through a Euclidean instanton.](/figures/nonperturbative-qft/tunneling-between-vacua-barrier.svg)

<figcaption>

The Chern–Simons functional behaves like a periodic coordinate on the vacuum valley. Instantons describe Euclidean tunneling between neighboring minima, while sphalerons sit near the barrier top and control thermal transitions rather than zero-temperature tunneling.

</figcaption>
</figure>

The cartoon is valuable, but it has a warning label. In quantum mechanics, the tunneling coordinate is a single variable. In Yang–Mills theory, the “coordinate” is a path through infinite-dimensional gauge-field configuration space. The instanton is not a particle moving under a barrier; it is a four-dimensional Euclidean field configuration that extremizes the action.

## Prerequisites

You should know [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), and [Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/).

You should also be comfortable with Euclidean transition amplitudes in quantum mechanics:

$$
\langle q_f|e^{-HT}|q_i\rangle
=
\int_{q(-T/2)=q_i}^{q(T/2)=q_f}\mathcal Dq\,e^{-S_E[q]}.
$$

The gauge-theory formula is the same idea with $q$ replaced by a gauge-field configuration and with boundary conditions labeled by winding data.

## Core idea

A classical Yang–Mills vacuum can be represented by a pure gauge. Distinct pure gauges can carry different winding number. We call the corresponding semiclassical vacuum representatives

$$
|n\rangle,
\qquad n\in\mathbb Z.
$$

Classically, these vacua are separated by energy barriers in configuration space. Quantum mechanically, the system can tunnel between them. The transition amplitude from $|n_-\rangle$ to $|n_+\rangle$ over Euclidean time $T$ has a path-integral representation

$$
\langle n_+|e^{-HT}|n_-\rangle
=
\int_{n_-}^{n_+}\mathcal DA\,e^{-S_E[A]}.
$$

Finite-action histories obey

$$
Q[A]=n_+-n_-.
$$

Thus the tunneling problem is organized by topological charge. A charge-one instanton mediates a transition

$$
n\longrightarrow n+1,
$$

while an anti-instanton mediates

$$
n\longrightarrow n-1.
$$

This is the precise sense in which instantons “connect vacua.” They do not connect different theta vacua; theta labels an energy sector and is conserved. They connect different winding representatives inside the same theta-sector construction.

## Setup and conventions

We work in Euclidean time $\tau$ and in the same gauge conventions as the previous pages. The topological charge is

$$
Q[A]
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

For a finite-action trajectory on $\mathbb R_\tau\times\mathbb R^3$ whose endpoints are pure gauge,

$$
Q=N_{\rm CS}(+\infty)-N_{\rm CS}(-\infty).
$$

A charge-one self-dual Yang–Mills instanton has

$$
Q=1,
\qquad
S_I=\frac{8\pi^2}{g^2}.
$$

A charge-minus-one anti-instanton has

$$
Q=-1,
\qquad
S_{\bar I}=\frac{8\pi^2}{g^2}.
$$

The theta term modifies the Euclidean weight by

$$
e^{-S_E[A;\theta]}
=
e^{-S_{E,\mathrm{YM}}[A]+i\theta Q[A]}.
$$

Therefore an instanton and anti-instanton carry weights

$$
I:
\quad
\exp\left(-\frac{8\pi^2}{g^2}+i\theta\right),
\qquad
\bar I:
\quad
\exp\left(-\frac{8\pi^2}{g^2}-i\theta\right).
$$

## The quantum-mechanical prototype

The cleanest prototype is a particle in a periodic potential,

$$
V(q)=V(q+a).
$$

Let $|n\rangle$ be a wavefunction localized near the $n$th minimum, $q=na$. Tunneling gives off-diagonal Hamiltonian matrix elements,

$$
\langle n+1|H|n\rangle\sim -K e^{-S_I}.
$$

The energy eigenstates are Bloch waves,

$$
|\theta\rangle=\sum_n e^{-in\theta}|n\rangle,
$$

with leading energy

$$
E(\theta)=E_{\rm well}-2K e^{-S_I}\cos\theta.
$$

Gauge theory repeats this story with two changes. First, the “position” $q$ is replaced by the gauge field $A_i(\mathbf x)$. Second, the periodic coordinate is not ordinary spatial periodicity but the integer shift of Chern–Simons number under large gauge transformations.

## One-instanton transition amplitude

The saddle-point expansion around a charge-one instanton has the schematic form

$$
\langle n+1|e^{-HT}|n\rangle_{I}
\simeq
\int d\mu_I\,
\exp[-S_I]
\left(\frac{\det \Delta_{\rm vac}}{\det'\Delta_I}\right)^{1/2}
\times
(\text{ghost and gauge-fixing factors}).
$$

The measure $d\mu_I$ includes bosonic collective coordinates. For a charge-one $SU(2)$ BPST instanton on $\mathbb R^4$, these include at least

$$
x_0^\mu,
\qquad
\rho,
\qquad
\text{gauge orientation},
$$

where $x_0$ is the instanton center and $\rho$ is the instanton size. The prime on the determinant means that zero modes are removed from the Gaussian determinant and replaced by integrations over collective coordinates.

For a translationally invariant theory, integration over the instanton center gives a factor of the Euclidean four-volume $V_4$. Thus one often writes the one-instanton contribution schematically as

$$
Z_{Q=1}
\sim
V_4\,\kappa\,e^{-S_I},
$$

where $\kappa$ is a density containing the remaining collective-coordinate integrals, determinant ratios, and renormalization factors.

This shorthand is useful only if $\kappa$ is finite or made finite by the physical setup. In pure four-dimensional Yang–Mills on $\mathbb R^4$, the instanton size integral is not a harmless constant at strong coupling. The small-$\rho$ region is controlled by asymptotic freedom, but the large-$\rho$ region probes infrared dynamics. A formula that writes $\kappa$ without discussing the $\rho$ integral is hiding the hard part.

## Multi-instantons and sector changes

A transition with

$$
Q=k>0
$$

can be approximated, in a dilute regime, by $k$ well-separated instantons. The leading action is additive:

$$
S_E\simeq kS_I.
$$

Similarly, a sector with $Q=-\ell<0$ is approximated by $\ell$ anti-instantons. A configuration with $N_I$ instantons and $N_{\bar I}$ anti-instantons has

$$
Q=N_I-N_{\bar I},
$$

and leading semiclassical weight

$$
\frac{1}{N_I!N_{\bar I}!}
\left(V_4\kappa e^{-S_I+i\theta}\right)^{N_I}
\left(V_4\kappa e^{-S_I-i\theta}\right)^{N_{\bar I}}.
$$

The factorials appear because well-separated instantons of the same type are indistinguishable events in the gas approximation. Summing over $N_I$ and $N_{\bar I}$ gives

$$
Z(\theta)
\propto
\exp\left[
V_4\kappa e^{-S_I+i\theta}
+
V_4\kappa e^{-S_I-i\theta}
\right]
$$

or

$$
Z(\theta)
\propto
\exp\left[2V_4\kappa e^{-S_I}\cos\theta\right].
$$

Since

$$
Z(\theta)\sim e^{-V_4\mathcal E(\theta)},
$$

the leading dilute-gas contribution to the vacuum energy density is

$$
\mathcal E(\theta)
=
\mathcal E_{\rm pert}-2\kappa e^{-S_I}\cos\theta+\text{higher corrections}.
$$

This is the field-theory version of band formation in a periodic quantum-mechanical potential.

## Why theta vacua do not tunnel into each other

A phrase like “tunneling between theta vacua” is usually misleading. Instantons tunnel between winding representatives $|n\rangle$. The theta states are already the diagonal combinations.

In formulas, the theta transition amplitude has the form

$$
Z_{\theta'\leftarrow\theta}
=
\sum_{n_+,n_-}e^{in_+\theta'}e^{-in_-\theta}Z_{n_+\leftarrow n_-}.
$$

Because

$$
Z_{n_+\leftarrow n_-}=Z_{n_+-n_-},
$$

the sum over the common shift of $n_+$ and $n_-$ enforces

$$
\theta'=\theta
$$

modulo $2\pi$. In other words, theta is conserved. The instanton changes Chern–Simons number along the Euclidean history, but it does not change the theta label of the Hilbert-space sector.

This distinction prevents a lot of conceptual static. The object that tunnels is the winding representative. The object that labels the exact sector is $\theta$.

## Tunneling versus thermal transitions

Instanton tunneling is a zero-temperature quantum process. In Euclidean language, it is controlled by finite-action saddles that pass through classically forbidden regions of configuration space.

At finite temperature, the Euclidean time direction is compact:

$$
\tau\sim\tau+\beta,
\qquad
\beta=1/T.
$$

There can also be thermal activation over the barrier. The relevant static unstable configuration near the top of the barrier is called a sphaleron. It is not an instanton. It is a saddle of the energy functional on a spatial slice, not a localized four-dimensional Euclidean event.

The rough contrast is

$$
\text{instanton tunneling}
\sim e^{-S_E},
\qquad
\text{thermal sphaleron transition}
\sim e^{-E_{\rm sph}/T}.
$$

In electroweak theory, this distinction matters for baryon-plus-lepton number violation: instantons encode the anomalous zero-temperature tunneling amplitude, while sphalerons control unsuppressed or less-suppressed thermal transitions at high temperature. The detailed electroweak story belongs elsewhere; the conceptual distinction belongs here.

## When the semiclassical picture is reliable

The formal saddle expansion is most trustworthy when the instanton action is large:

$$
S_I\gg1.
$$

In Yang–Mills theory this means

$$
\frac{8\pi^2}{g^2(\mu)}\gg1
$$

at the scale that controls the instanton. Because instantons have a size modulus $\rho$, the relevant running coupling is roughly evaluated at

$$
\mu\sim\frac{1}{\rho}.
$$

Small instantons can be weakly coupled in asymptotically free theories. Large instantons probe the infrared, where pure Yang–Mills becomes strongly coupled. Therefore the elementary instanton gas on $\mathbb R^4$ is not automatically a controlled approximation to confinement or the full Yang–Mills vacuum.

There are controlled settings where instanton-like objects are powerful: quantum mechanics, weakly coupled Higgsed gauge theories, some compactified gauge theories, high-temperature regimes with screening scales, supersymmetric theories with protected quantities, and lower-dimensional models. The moral is not “instantons always solve nonperturbative QFT.” The moral is “when a finite-action saddle is controlled, it gives a calculable nonperturbative effect.”

## Common pitfalls

**Saying that instantons connect theta vacua.** They connect winding sectors $|n\rangle$. Theta vacua are the linear combinations that diagonalize the tunneling problem.

**Counting only the exponential.** The factor $e^{-S_I}$ is the leading suppression. A correct amplitude also includes determinant ratios, ghost factors, collective-coordinate Jacobians, zero-mode insertions, and renormalization.

**Ignoring the instanton size integral.** In four-dimensional Yang–Mills, the size modulus $\rho$ is central. Large instantons can invalidate a naive dilute-gas estimate.

**Treating anti-instantons as optional.** At $\theta=0$, instantons and anti-instantons usually contribute together. Their sum gives real CP-even effects such as $\cos\theta$ terms.

**Confusing false-vacuum bounces with instantons between degenerate vacua.** A false-vacuum bounce has one negative mode and computes an imaginary part of the false-vacuum energy. An instanton between degenerate topological sectors usually contributes to tunneling splittings or theta dependence.

**Forgetting fermion zero modes.** In theories with massless fermions, an instanton background can make the fermion determinant vanish unless external operators or mass insertions absorb the zero modes. The bosonic tunneling picture is incomplete without this qualification.

## Relations to other pages

[Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) explains the Bloch-state basis that diagonalizes the tunneling Hamiltonian.

[Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) explains why the tunneling history has integer $Q=n_+-n_-$.

[Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) derives the self-dual saddle and the action $S_I=8\pi^2/g^2$.

[Dilute-Gas Approximation](/nonperturbative-qft/semiclassical-methods/dilute-gas-approximation/) explains the general exponentiation logic used in the multi-instanton sum.

[False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) explains the related but distinct bounce calculation.

[Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) refine the selection-rule and anomaly aspects of this page. [Instanton Measure](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-measure-preview/), [Instanton Gas](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-gas/), and [Sphalerons](/nonperturbative-qft/instantons-tunneling-theta-vacua/sphalerons-preview/) refine the measure, ensemble, and thermal-transition aspects.

## Research status

**Established.** The Euclidean saddle-point derivation of tunneling amplitudes is standard in quantum mechanics and in weakly coupled field-theory settings. For Yang–Mills instantons, the relation $Q=n_+-n_-$ and the action $S_I=8\pi^2/g^2$ are standard under the usual finite-action assumptions.

**Approximation-dependent.** The dilute-gas expression for $\mathcal E(\theta)$ is an approximation, not a universal theorem. Its reliability depends on the instanton density, interactions, determinant factors, zero modes, and size integrals.

**Active.** Strongly coupled instanton ensembles, the role of instantons versus renormalons, resurgence, compactified gauge theories, large-N theta branches, and real-time topology-changing dynamics are active research topics.

## Exercises

### Exercise 1: Sector change equals topological charge

Suppose a finite-action Euclidean gauge-field history begins in a pure-gauge vacuum with Chern–Simons number $n_-$ and ends in one with Chern–Simons number $n_+$. Using

$$
Q=N_{\rm CS}(+\infty)-N_{\rm CS}(-\infty),
$$

show that a charge-one instanton connects neighboring sectors.

<details><summary><strong>Solution</strong></summary>

If the endpoints have

$$
N_{\rm CS}(-\infty)=n_-,
\qquad
N_{\rm CS}(+\infty)=n_+,
$$

then

$$
Q=n_+-n_-.
$$

For a charge-one instanton, $Q=1$, so

$$
n_+-n_-=1.
$$

Therefore

$$
n_+=n_-+1.
$$

It connects neighboring winding sectors.

</details>

### Exercise 2: Dilute-gas exponentiation

Assume instantons and anti-instantons have equal density $\kappa e^{-S_I}$ and weights $e^{i\theta}$ and $e^{-i\theta}$. Show that summing over arbitrary numbers of noninteracting instantons and anti-instantons gives

$$
Z(\theta)\propto \exp\left[2V_4\kappa e^{-S_I}\cos\theta\right].
$$

<details><summary><strong>Solution</strong></summary>

The contribution from $N_I$ instantons and $N_{\bar I}$ anti-instantons is

$$
\frac{1}{N_I!N_{\bar I}!}
\left(V_4\kappa e^{-S_I+i\theta}\right)^{N_I}
\left(V_4\kappa e^{-S_I-i\theta}\right)^{N_{\bar I}}.
$$

Summing independently over $N_I$ and $N_{\bar I}$ gives two exponentials:

$$
\sum_{N_I=0}^\infty\frac{(V_4\kappa e^{-S_I+i\theta})^{N_I}}{N_I!}
=
\exp(V_4\kappa e^{-S_I+i\theta}),
$$

and

$$
\sum_{N_{\bar I}=0}^\infty\frac{(V_4\kappa e^{-S_I-i\theta})^{N_{\bar I}}}{N_{\bar I}!}
=
\exp(V_4\kappa e^{-S_I-i\theta}).
$$

Multiplying them,

$$
Z(\theta)
\propto
\exp\left[V_4\kappa e^{-S_I}(e^{i\theta}+e^{-i\theta})\right]
=
\exp\left[2V_4\kappa e^{-S_I}\cos\theta\right].
$$

</details>

### Exercise 3: Vacuum energy from the dilute gas

Given

$$
Z(\theta)
\propto
\exp\left[-V_4\mathcal E_{\rm pert}+2V_4\kappa e^{-S_I}\cos\theta\right],
$$

extract the leading theta-dependent vacuum energy density.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
Z(\theta)\sim e^{-V_4\mathcal E(\theta)}.
$$

Comparing exponents,

$$
-V_4\mathcal E(\theta)
=
-V_4\mathcal E_{\rm pert}+2V_4\kappa e^{-S_I}\cos\theta.
$$

Divide by $-V_4$:

$$
\mathcal E(\theta)
=
\mathcal E_{\rm pert}-2\kappa e^{-S_I}\cos\theta.
$$

Higher-order corrections come from interactions, determinant corrections, higher-charge sectors, and breakdown of the dilute approximation.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, for the classic semiclassical tunneling and false-vacuum lectures.
- M. Srednicki, *Quantum Field Theory*, chapter 93, for winding vacua, theta states, instanton-mediated tunneling, and the theta-weighted path integral.
- M. Mariño, *Instantons and Large N*, chapters 1 and 4, for instantons in quantum mechanics, multi-instantons, Yang–Mills topology, and theta dependence.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters 5 and 7, for Yang–Mills tunneling, BPST instantons, Chern–Simons number, and false-vacuum decay.
- A. M. Polyakov, *Gauge Fields and Strings*, for instantons, topology of gauge fields, and confinement-related semiclassical mechanisms in lower-dimensional examples.
- G. ’t Hooft, “Computation of the Quantum Effects Due to a Four-Dimensional Pseudoparticle,” for the instanton measure and fermion-zero-mode effects.

## Version history

- **2026-06-27:** Added links to Instanton Measure, Instanton Gas, and Sphalerons.

- **2026-06-27:** Initial polished draft. Added after Theta Vacua to explain the instanton-generated transition amplitudes between winding sectors and the leading dilute-gas theta dependence.
