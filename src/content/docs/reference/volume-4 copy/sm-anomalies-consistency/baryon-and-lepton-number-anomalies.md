---
title: "Baryon and Lepton Number Anomalies"
description: "Explains why the Standard Model's classical baryon and lepton number currents are anomalous, why B − L is special, and how electroweak topology gives ΔB = ΔL selection rules."
sidebar:
  label: "Baryon and Lepton Number Anomalies"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§76–77 and §§87–91; Schwartz Chs. 29–30; Burgess Ch. 9; Weinberg Vol. II electroweak and anomaly material."
topics:
  - baryon number
  - lepton number
  - B minus L
  - B plus L
  - electroweak anomaly
  - instantons
  - sphalerons
canonicalTopics:
  - baryon-number-anomaly
  - lepton-number-anomaly
  - b-minus-l
  - b-plus-l-violation
  - electroweak-sphalerons
  - t-hooft-vertex
researchStatus:
  established:
    - "In the renormalizable minimal Standard Model, baryon number and lepton number are classical accidental symmetries but are anomalous global symmetries; B − L is anomaly-free."
  active:
    - "Electroweak B + L violation is central in baryogenesis, leptogenesis, sphaleron dynamics, and Standard Model extensions with neutrino masses or gauged B − L."
---

## Summary

The renormalizable Standard Model Lagrangian accidentally conserves baryon number $B$ and lepton number $L$ in perturbation theory. Quarks carry $B=1/3$, leptons carry $L=1$, and no dimension-four gauge-invariant operator changes either charge.

Quantum mechanically, the story is subtler. The $B$ and $L$ currents have electroweak anomalies. In a standard current convention, the $SU(2)_L$ part of the anomaly is

$$
\partial_\mu J_B^\mu
=
\partial_\mu J_L^\mu
=
N_g\,\frac{g_2^2}{32\pi^2}
W^a_{\mu\nu}\widetilde W^{a\mu\nu},
$$

where $N_g$ is the number of generations. Therefore

$$
\partial_\mu J_{B-L}^\mu=0,
\qquad
\partial_\mu J_{B+L}^\mu
=2N_g\,\frac{g_2^2}{32\pi^2}W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

For a topological electroweak transition with charge

$$
n=\frac{g_2^2}{32\pi^2}\int d^4x\,W^a_{\mu\nu}\widetilde W^{a\mu\nu},
$$

the selection rule is

$$
\Delta B=\Delta L=N_g n,
\qquad
\Delta(B-L)=0,
\qquad
\Delta(B+L)=2N_g n.
$$

<figure class="doc-figure" style="--figure-width: 39rem;">

![Baryon and lepton number anomaly selection rules](/figures/gauge-theories-standard-model/baryon-lepton-anomaly-flow.svg)

<figcaption>

The electroweak anomaly violates $B+L$ but preserves $B-L$. For three generations and one unit of electroweak topological charge, the Standard Model selection rule is $\Delta B=\Delta L=3$ and $\Delta(B+L)=6$.

</figcaption>
</figure>

This page explains why this is not a gauge inconsistency. $B$ and $L$ are global accidental symmetries, not gauge redundancies. Their anomaly is a physical effect, whereas a gauge anomaly would make the theory inconsistent.

## Prerequisites

Read [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/), [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/), and [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/) first. You should also know [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/), [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/), and the [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/).

We work with the minimal renormalizable Standard Model unless stated otherwise. If neutrino masses are added through the dimension-five Weinberg operator, lepton number is explicitly broken by $\Delta L=2$, and the low-energy symmetry story changes.

## Core idea

The Standard Model has two famous kinds of anomaly statements:

1. **Gauge anomalies must cancel.** These are consistency conditions on the gauge currents.
2. **Global-current anomalies can remain.** These are physical violations of classical global current conservation.

Baryon number and lepton number belong to the second category. There is no Standard Model gauge boson for $U(1)_B$ or $U(1)_L$. Therefore a nonzero divergence of $J_B^\mu$ or $J_L^\mu$ is not a breakdown of gauge redundancy. It is a statement that the classical global symmetry is not exact in the quantum theory.

The anomaly is tied to the fact that only left-handed fermion doublets couple to $SU(2)_L$. A vectorlike gauge theory would treat the two chiralities symmetrically and the corresponding vector current would be conserved. The weak interaction does not.

## Baryon and lepton number in the classical Lagrangian

Assign baryon and lepton charges to one generation as follows:

$$
\begin{array}{c|c|c}
\text{field} & B & L \\
\hline
Q_L & 1/3 & 0 \\
u_R,d_R & 1/3 & 0 \\
L_L & 0 & 1 \\
e_R & 0 & 1
\end{array}
$$

Equivalently, in all-left-handed notation, the conjugate fields $u_L^c,d_L^c,e_L^c$ carry the opposite global charges from $u_R,d_R,e_R$ because they create antiparticles. An optional sterile field $N_L^c$ would carry $L=-1$ if it is the conjugate of a right-handed neutrino.

The renormalizable Standard Model interactions preserve $B$ and $L$ separately:

- gauge interactions preserve species number and do not convert quarks into leptons;
- Yukawa interactions connect left- and right-handed fields of the same baryon or lepton assignment;
- the Higgs field has $B=L=0$;
- no renormalizable gauge-invariant operator contains three quarks and one lepton.

This is why $U(1)_B$ and $U(1)_L$ are called **accidental symmetries** of the dimension-four Standard Model Lagrangian. They were not imposed as gauge principles. They survive because the gauge representation content and operator dimension happen to forbid their violation at the renormalizable level.

## The SU(2) anomaly coefficient

The electroweak anomaly of a global current $J_X^\mu$ with charge $X$ is controlled by the mixed coefficient

$$
[SU(2)_L]^2U(1)_X:
\qquad
\sum_{\psi_L\,\text{doublets}} X_\psi\,T(\mathbf2)\,d_{\rm spectator}(\psi),
$$

where

$$
T(\mathbf2)=\frac{1}{2}.
$$

For baryon number in one generation, only $Q_L$ contributes. It has three color copies and $B=1/3$, so

$$
C_{BWW}=3\left(\frac{1}{3}\right)T(\mathbf2)
=\frac{1}{2}.
$$

For lepton number, only $L_L$ contributes. It has $L=1$, so

$$
C_{LWW}=1\cdot T(\mathbf2)=\frac{1}{2}.
$$

Thus the $SU(2)_L$ anomaly coefficients are equal:

$$
C_{BWW}=C_{LWW}.
$$

The difference current has coefficient

$$
C_{(B-L)WW}=C_{BWW}-C_{LWW}=0,
$$

while the sum current has coefficient

$$
C_{(B+L)WW}=C_{BWW}+C_{LWW}=1
$$

per generation. This is the group-theoretic reason that $B-L$ is special.

With $N_g$ generations, the anomaly equation can be normalized as

$$
\partial_\mu J_B^\mu
=
\partial_\mu J_L^\mu
=
N_g\frac{g_2^2}{32\pi^2}W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

Different definitions of global currents can move Abelian total-derivative terms between the current and the anomaly. The robust, gauge-invariant selection rule from $SU(2)_L$ topology is the equality of $\Delta B$ and $\Delta L$ and the conservation of $B-L$.

## Topological transitions and selection rules

The density

$$
\frac{g_2^2}{32\pi^2}W^a_{\mu\nu}\widetilde W^{a\mu\nu}
$$

is a total derivative. Perturbatively, total derivatives do not change ordinary scattering amplitudes between topologically trivial gauge-field configurations. Nonperturbatively, however, four-dimensional gauge fields can have nonzero topological charge,

$$
n=\frac{g_2^2}{32\pi^2}\int d^4x\,W^a_{\mu\nu}\widetilde W^{a\mu\nu}.
$$

Integrating the anomaly equation gives

$$
\Delta B=N_g n,
\qquad
\Delta L=N_g n.
$$

For the observed three generations and $n=1$,

$$
\Delta B=3,
\qquad
\Delta L=3,
\qquad
\Delta(B+L)=6,
\qquad
\Delta(B-L)=0.
$$

The corresponding fermionic operator is often described schematically as the electroweak ’t Hooft vertex. For one generation it has the form

$$
Q_LQ_LQ_LL_L,
$$

with color, weak-isospin, Lorentz, and flavor contractions suppressed. For three generations, the full instanton vertex contains one such factor for each generation,

$$
\prod_{i=1}^{3}(Q_{Li}Q_{Li}Q_{Li}L_{Li}).
$$

Each one-generation factor carries

$$
\Delta B=1,
\qquad
\Delta L=1.
$$

This is the compact operator-level memory of the zero modes in an electroweak topological background.

## Instantons and sphalerons

At zero temperature, electroweak $B+L$ violation is nonperturbative and fantastically suppressed. The semiclassical suppression is controlled by the weak gauge coupling, schematically by a factor of order

$$
\exp\left(-\frac{8\pi^2}{g_2^2}\right)
$$

in amplitudes associated with instanton tunneling. This is why ordinary low-energy proton stability is not threatened by electroweak instantons.

At finite temperature, the picture changes. Instead of tunneling through the barrier between electroweak vacua of different Chern–Simons number, the system can thermally cross over the barrier through saddle-point configurations called **sphalerons**. Sphaleron processes violate $B+L$ but preserve $B-L$.

This makes sphalerons central in early-universe physics. If some mechanism creates a nonzero $B-L$ asymmetry, electroweak sphalerons can redistribute it between baryons and leptons. If a mechanism creates only $B+L$ while sphalerons are in equilibrium, the asymmetry can be washed out.

## Why B minus L is special

The current

$$
J_{B-L}^\mu=J_B^\mu-J_L^\mu
$$

has no $SU(2)_L$ anomaly because the quark and lepton doublet contributions cancel generation by generation:

$$
3\left(\frac{1}{3}\right)-1=0.
$$

The same cancellation also appears in the anomaly-free $U(1)_{B-L}$ pattern when a sterile neutrino is included. Without $N_L^c$, the minimal Standard Model has $B-L$ as an anomaly-free global symmetry of the renormalizable theory, but gauging $B-L$ runs into additional conditions, including the mixed gravitational anomaly discussed in [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/).

With one sterile neutrino per generation, $B-L$ can be gauged in a very economical way. With the dimension-five Weinberg operator,

$$
\mathcal O_5=(L H)(L H),
$$

lepton number and $B-L$ are explicitly broken by two units. In that case $B-L$ is no longer an exact symmetry of the low-energy effective theory.

## Common pitfalls

**Baryon number anomaly does not mean the Standard Model has a gauge anomaly.** $B$ and $L$ are global currents. Their anomaly is allowed. Hypercharge, color, and weak-isospin gauge anomalies must cancel.

**Electroweak B violation is not ordinary proton decay.** The anomaly selection rule for three generations gives $\Delta B=3$, not $\Delta B=1$. Conventional proton decay in grand unified theories comes from higher-dimensional operators or heavy gauge bosons, not from the low-energy electroweak anomaly alone.

**B and L are separately anomalous, but B minus L is not.** In the minimal renormalizable Standard Model, $B-L$ is the protected linear combination.

**The anomaly is invisible in ordinary perturbation theory.** The density $W\widetilde W$ is a total derivative. Its physical effect appears through topologically nontrivial gauge fields and through finite-temperature sphaleron transitions.

**The Weinberg operator changes the symmetry story.** Once $(LH)(LH)$ is included, lepton number is explicitly violated by $\Delta L=2$. That is not the same mechanism as the electroweak anomaly.

## Relations to other pages

- [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/) explains why $B$ and $L$ appear in the dimension-four Standard Model Lagrangian.
- [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) explains why anomalies in gauged currents are fatal.
- [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) shows that the Standard Model gauge currents are anomaly-free.
- [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) explains why gauging $B-L$ requires attention to singlet neutrinos.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explains the minimal low-energy source of explicit lepton-number violation.
- [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) places baryon asymmetry, neutrino mass, and proton stability among the clues beyond the minimal theory.

## Research status

The electroweak $B+L$ anomaly and the conservation of $B-L$ by Standard Model gauge dynamics are established. Their applications remain live: sphaleron processes are essential in baryogenesis and leptogenesis, and the fate of $B-L$ is a major organizing question in neutrino-mass models, grand unification, and Standard Model effective field theory.

A useful status distinction is this:

$$
\text{electroweak anomaly: established Standard Model effect},
$$

while

$$
\text{origin of the cosmic baryon asymmetry: not explained by the minimal Standard Model}.
$$

## Exercises

### Exercise 1: Compute the SU(2) anomaly coefficients

Using $T(\mathbf2)=1/2$, compute the coefficients of the mixed anomalies $[SU(2)_L]^2U(1)_B$ and $[SU(2)_L]^2U(1)_L$ in one generation.

<details><summary><strong>Solution</strong></summary>

For baryon number, there are three color copies of $Q_L$, each with $B=1/3$:

$$
C_{BWW}=3\left(\frac{1}{3}\right)\frac{1}{2}=\frac{1}{2}.
$$

For lepton number, there is one lepton doublet with $L=1$:

$$
C_{LWW}=1\cdot\frac{1}{2}=\frac{1}{2}.
$$

Thus the coefficients are equal.

</details>

### Exercise 2: Show that B minus L is anomaly-free under SU(2)

Use the result of Exercise 1 to compute the $[SU(2)_L]^2U(1)_{B-L}$ coefficient.

<details><summary><strong>Solution</strong></summary>

The coefficient is the difference

$$
C_{(B-L)WW}=C_{BWW}-C_{LWW}.
$$

Since both coefficients are $1/2$,

$$
C_{(B-L)WW}=\frac{1}{2}-\frac{1}{2}=0.
$$

So $B-L$ has no $SU(2)_L$ anomaly.

</details>

### Exercise 3: Integrated selection rule

Assume $N_g=3$ and electroweak topological charge $n=1$. Compute $\Delta B$, $\Delta L$, $\Delta(B+L)$, and $\Delta(B-L)$.

<details><summary><strong>Solution</strong></summary>

The selection rule is

$$
\Delta B=\Delta L=N_g n.
$$

With $N_g=3$ and $n=1$,

$$
\Delta B=3,
\qquad
\Delta L=3.
$$

Therefore

$$
\Delta(B+L)=6,
\qquad
\Delta(B-L)=0.
$$

</details>

### Exercise 4: Charge of the one-generation ’t Hooft vertex

Show that the schematic one-generation operator

$$
Q_LQ_LQ_LL_L
$$

has $B=1$ and $L=1$.

<details><summary><strong>Solution</strong></summary>

Each quark doublet field has $B=1/3$, and there are three $Q_L$ factors. Thus

$$
B=3\left(\frac{1}{3}\right)=1.
$$

The lepton doublet has $L=1$, and the quark fields have $L=0$, so

$$
L=1.
$$

Thus the vertex carries $\Delta B=\Delta L=1$ per generation.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the anomaly, Standard Model, and electroweak sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction and anomaly chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory, the Fermi theory, and anomaly matching discussions.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and anomalous current constraints.
- Reviews on electroweak instantons, sphalerons, baryogenesis, and leptogenesis for the finite-temperature and cosmological applications.

## Version history

- **2026-06-19:** Initial page explaining electroweak $B+L$ violation, $B-L$ conservation, and the topological selection rule $\Delta B=\Delta L=N_g n$.
