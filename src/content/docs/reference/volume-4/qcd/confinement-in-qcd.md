---
title: "Confinement in QCD"
description: "Explains what confinement means in real QCD, how Wilson-loop and static-potential diagnostics work, and why dynamical quarks make the story subtler than pure Yang–Mills confinement."
sidebar:
  label: "Confinement in QCD"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §82; Schwartz Chs. 25–26 and 32; Polyakov, Gauge Fields and Strings, Chs. 3, 5, 7; Coleman, Aspects of Symmetry, Chs. 5 and 8."
topics:
  - QCD confinement
  - Wilson loops
  - static quark potential
  - string breaking
  - color singlets
  - center symmetry
canonicalTopics:
  - confinement-in-qcd
  - qcd
  - wilson-loop
  - string-breaking
  - color-confinement
  - center-symmetry
researchStatus:
  established:
    - "Color-nonsinglet quarks and gluons are not observed as isolated asymptotic states in zero-temperature QCD, and lattice QCD strongly supports confinement and string breaking in the appropriate regimes."
  active:
    - "A complete analytic derivation of confinement and the Yang–Mills mass gap in four dimensions, together with real-time hadronization from first principles, remains an active frontier."
---

## Summary

**Confinement** is the infrared fact that makes QCD physically unlike its ultraviolet variables. The QCD Lagrangian is written in terms of quark fields $q_f$ and gluon fields $G_\mu^A$, but the isolated particles in the zero-temperature spectrum are color singlets: mesons, baryons, glueball-like states, and multihadron states. No free quark or gluon appears as an asymptotic state.

That sentence is easy to say and hard to make precise. In pure $SU(3)$ Yang–Mills theory, confinement can be sharply diagnosed by an area law for fundamental Wilson loops and by unbroken center one-form symmetry. In real QCD, dynamical quarks transform in the fundamental representation and can screen external color sources. A flux tube between very heavy external probes can break by creating a light quark–antiquark pair, so the asymptotic Wilson-loop area law is not the whole story.

The right first-pass picture is therefore:

$$
\text{QCD confinement}
\neq
\text{one magic Wilson-loop criterion}.
$$

It is a network of facts: color nonsinglets are absent from the physical spectrum, the static potential rises over an intermediate range, flux tubes form, dynamical quarks screen external probes at sufficiently long distance, and the low-energy degrees of freedom are hadrons rather than colored partons.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Static heavy-quark potential in QCD, showing Coulombic short-distance behavior, a linearly rising flux-tube regime, and string breaking when dynamical quarks screen the external sources.](/figures/gauge-theories-standard-model/qcd-confinement-string-breaking.svg)

<figcaption>

In pure Yang–Mills theory, the static potential for fundamental external probes keeps rising linearly in a confining phase. In full QCD, dynamical quark–antiquark pair creation can break the flux tube. The potential then crosses over from a linear regime to a pair of heavy–light color-singlet mesons.

</figcaption>
</figure>

## Prerequisites

You should know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/), [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/), [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/), and [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/).

You should also know the Wilson-loop diagnostics from [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/), [Area Law and Perimeter Law](/gauge-theories-standard-model/wilson-loops-confinement/area-law-and-perimeter-law/), and [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/). This page does not repeat the general line-operator formalism; it specializes the lesson to QCD.

We use the volume convention

$$
D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f,
\qquad
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB},
$$

and Wilson lines are written with the corresponding sign

$$
W_R(C)=P\exp\left[-ig_s\int_C dx^\mu\,G_\mu^A T_R^A\right].
$$

## Core idea

There are two QCD stories that must be held at the same time.

At short distance, QCD is a weakly coupled theory of colored quarks and gluons. Asymptotic freedom says

$$
\alpha_s(\mu)\to 0
\qquad
\text{as}\qquad
\mu\to\infty.
$$

This is why perturbative QCD works for sufficiently hard processes. A high-energy electron, photon, weak boson, or hadron can resolve quark and gluon partons. The short-distance degrees of freedom in the Lagrangian are not a fiction.

At long distance, the physical Hilbert space is organized very differently. The experimentally stable or metastable particles are color singlets. The useful low-energy variables are pions, kaons, nucleons, heavy mesons, glueball-like states, nuclear degrees of freedom, and eventually finite-temperature or finite-density collective modes. The colored fields in the microscopic Lagrangian do not create isolated finite-energy asymptotic particles.

Confinement is the nonperturbative transition between these two descriptions. It is not a contradiction. A field can be an excellent short-distance variable without creating an isolated long-distance particle. Electrons in QED are both fields and asymptotic particles. Quarks in QCD are fields and partons, but not isolated asymptotic particles. That difference is the strong interaction being rude, as usual.

## Setup and conventions

For $n_f$ quark flavors, the minimal QCD Lagrangian is

$$
\mathcal L_{\rm QCD,min}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\sum_{f=1}^{n_f}\bar q_f(i\gamma^\mu D_\mu-m_f)q_f.
$$

The gluons are in the adjoint representation of $SU(3)_c$ and the quarks are in the fundamental representation $\mathbf 3$. Gauge-invariant local composite operators are color singlets, for example

$$
\bar q_i q^i,
\qquad
\epsilon_{ijk}q^iq^jq^k,
\qquad
\operatorname{tr}(G_{\mu\nu}G_{\rho\sigma}),
$$

with spin, flavor, and derivative structures suppressed.

The distinction between color singlets and nonsinglets is gauge-theoretic, not aesthetic. A state that transforms nontrivially under a gauge redundancy is not a physical state in the gauge-invariant Hilbert space. The practical subtlety is that gauge-fixed correlators of quark and gluon fields are still useful in perturbation theory, factorization, lattice gauge-fixed studies, and renormalization. They are not themselves the asymptotic hadron spectrum.

## Pure Yang–Mills versus full QCD

The cleanest confinement diagnostic lives in pure $SU(N)$ Yang–Mills theory. There are no dynamical fundamental charges. The center

$$
Z_N=\{e^{2\pi i k/N}\mathbf 1\mid k=0,1,\ldots,N-1\}
$$

acts as a one-form symmetry on Wilson loops. A fundamental Wilson loop has nonzero $N$-ality and cannot be screened by gluons, because gluons are adjoint fields and have zero center charge.

In that setting, a confining phase is associated with an area law

$$
\langle \mathcal W_{\mathbf N}(C)\rangle
\sim
\exp[-\sigma A(C)]
$$

for large loops, where $\sigma$ is the string tension. For a large Euclidean rectangle $C_{R,T}$,

$$
\langle \mathcal W(C_{R,T})\rangle
\sim
\exp[-V(R)T],
$$

so an area law implies

$$
V(R)\simeq \sigma R
\qquad
\text{at large }R.
$$

That is the pure-gauge flux tube picture.

Full QCD contains dynamical quarks in the fundamental representation. They explicitly break the center one-form symmetry. The vacuum can create a light quark–antiquark pair, and the external heavy source and antisource can reorganize into two heavy–light mesons. Then a linearly rising potential cannot continue forever. It saturates at the string-breaking threshold.

So we should distinguish:

| Theory | Fundamental dynamical matter? | Sharp center symmetry? | Large fundamental Wilson loop |
|---|---:|---:|---|
| Pure $SU(3)$ Yang–Mills | No | Yes | Area law in the confining phase |
| QCD with infinitely heavy quarks | Effectively no at low energy | Approximate/quasi-quenched | Long linear regime |
| Real QCD with light quarks | Yes | Explicitly broken | String breaking and screening at long distance |

This is why a strict Wilson-loop area law is not the definition of confinement in real QCD. It is an extremely useful diagnostic in pure gauge theory and in quenched or heavy-quark regimes.

## The static potential

For two infinitely heavy external color sources in the fundamental and antifundamental representations, a rectangular Wilson loop defines the static energy:

$$
V(R)
=
-\lim_{T\to\infty}\frac1T
\log\langle\mathcal W_{\mathbf 3}(C_{R,T})\rangle.
$$

At short distance, perturbation theory gives a color-Coulomb potential

$$
V(R)
\simeq
-\frac{C_F\alpha_s(1/R)}{R},
\qquad
C_F=\frac43
\quad\text{for }SU(3)_c.
$$

At intermediate distance, lattice simulations and phenomenological models support a flux-tube regime often summarized by the Cornell-like form

$$
V(R)\simeq V_0-\frac{\kappa}{R}+\sigma R.
$$

The parameter $\sigma$ is the string tension. Its square root is of order the QCD scale; the exact value depends on the theory, quark masses, and convention for defining the potential.

In full QCD, the linear regime ends once

$$
\sigma R
\gtrsim
2M_{Q\bar q}-2M_Q
$$

schematically, where $Q$ denotes the external heavy source and $q$ a dynamical light quark. Then it is energetically favorable to create a light pair and form two color-singlet heavy–light mesons:

$$
Q\bar Q
\longrightarrow
(Q\bar q)+(q\bar Q).
$$

This is **string breaking**. It is not a failure of confinement; it is confinement plus dynamical matter.

## What is confined?

A useful practical statement is:

$$
\text{The physical zero-temperature QCD spectrum contains no isolated color nonsinglets.}
$$

This statement is not identical to a linearly rising potential at all distances. With light quarks, a color source can be screened, but the screened final objects are still color singlets. The flux tube breaks into hadrons; it does not release a free quark.

This gives several related but distinct meanings of “confinement.”

| Name | Rough criterion | Best setting |
|---|---|---|
| Color confinement | Physical asymptotic states are color singlets. | Full QCD intuition and phenomenology. |
| Wilson-loop confinement | Center-charged Wilson loops obey an area law. | Pure Yang–Mills and theories with exact one-form center symmetry. |
| Linear potential | Static probe energy grows as $\sigma R$. | Heavy-quark or quenched regimes before string breaking. |
| Hadronization | Colored partons become color-singlet jets and hadrons. | Real-time high-energy QCD; not yet analytically solved from first principles. |
| Mass gap | The theory has no arbitrarily low-energy gluonic excitations above the vacuum. | Pure Yang–Mills as a mathematical problem; QCD with light pions has caveats. |

The table is worth internalizing. Many arguments about confinement are actually arguments about which definition is being used.

## Flux tubes and string breaking

The flux-tube picture says that color electric flux between widely separated external sources is squeezed into a roughly one-dimensional tube rather than spreading like an Abelian Coulomb field. If the energy per unit length is $\sigma$, the energy grows as $\sigma R$.

In pure gauge theory, the tube cannot end on dynamical fundamental matter, so it keeps stretching. In QCD, light quark pair creation supplies endpoints. The tube breaks into two shorter tubes ending on dynamical quarks, and the physical final state is a pair of color-singlet hadrons.

The worldsheet language is often useful here. A long confining flux tube has transverse fluctuations resembling an effective string, and this leads to universal corrections to the linear potential at large $R$ in pure gauge theory. But the QCD string is not a fundamental string in the microscopic Lagrangian. It is an emergent infrared object.

## Relation to chiral symmetry breaking

Confinement and chiral symmetry breaking are both infrared QCD phenomena, but they are not the same statement.

In real-world QCD, they occur in the same strongly coupled regime and influence the same hadron spectrum. Light pions are the pseudo-Goldstone bosons of spontaneous chiral symmetry breaking, while baryons and mesons are color singlets shaped by confinement. At finite temperature, the deconfinement crossover and chiral restoration crossover occur in a related temperature range for physical quark masses, but their precise relation depends on quark masses, number of flavors, and observables.

Conceptually, one can imagine theories with confinement without the same chiral pattern, chiral symmetry breaking without ordinary confinement diagnostics, or transitions where the two phenomena separate. That is why this chapter treats them on neighboring pages rather than mashing them into one blob of “strong stuff.”

## Finite temperature and the Polyakov loop

At finite temperature, the Polyakov loop wraps the Euclidean thermal circle. In pure Yang–Mills theory, it is an order parameter for center symmetry:

$$
\langle P\rangle=0
\quad\text{in the center-symmetric confined phase},
\qquad
\langle P\rangle\neq0
\quad\text{in the deconfined phase}.
$$

With dynamical fundamental quarks, center symmetry is explicitly broken, so the Polyakov loop is no longer an exact order parameter. It remains a useful diagnostic of the thermal crossover and of the free energy of an external heavy color source, but the word “phase transition” must be used with care for physical quark masses.

This is the same moral as before: pure Yang–Mills theory gives sharp symmetry diagnostics; full QCD gives physically richer but less sharply ordered diagnostics.

## Why perturbation theory cannot see confinement

Confinement is invisible at any fixed order in weak-coupling perturbation theory. Expanding around $g_s=0$ gives quark and gluon propagators, vertices, and scattering amplitudes. No finite number of diagrams can produce a mass gap of order

$$
\Lambda_{\rm QCD}
\sim
\mu\exp\left[-\frac{2\pi}{b_0\alpha_s(\mu)}\right],
$$

because this scale is nonanalytic at $\alpha_s=0$.

This does not make perturbation theory wrong. It means perturbation theory has a domain. At high energies, it computes short-distance coefficients and partonic hard processes. At long distances, those coefficients must be combined with nonperturbative matrix elements, lattice data, effective theories, or phenomenological inputs.

A good slogan is

$$
\text{QCD is perturbative in the ultraviolet and nonperturbative in the infrared.}
$$

The slogan is not a substitute for calculation, but it is a reliable compass.

## What lattice QCD contributes

Lattice gauge theory gives a nonperturbative Euclidean definition of QCD with an ultraviolet cutoff. It is central evidence for confinement physics. In pure gauge theory, lattice simulations show an area law and a nonzero string tension. In full QCD, simulations show string breaking, a color-singlet hadron spectrum, chiral symmetry breaking, topological susceptibility, and finite-temperature crossovers or transitions depending on quark masses.

The lattice is not merely a numerical trick. Conceptually, it shows how gauge invariance can be preserved nonperturbatively through link variables and plaquettes. It also makes precise the difference between the strong-coupling expansion at large lattice spacing and the continuum limit obtained by tuning the bare coupling according to the renormalization group.

The analytic challenge is that the strong-coupling lattice area law does not automatically prove continuum four-dimensional confinement. The continuum limit lives near weak bare coupling. Showing that the confining phase persists all the way to the continuum is the hard part.

## Common pitfalls

**Pitfall: defining confinement only as a linear potential at arbitrarily large distance.** That definition is good for pure Yang–Mills fundamental probes. In full QCD, string breaking prevents an indefinitely rising fundamental static potential.

**Pitfall: saying “quarks are not real.”** Quark fields are real ingredients of the QCD Lagrangian, and quarks are experimentally meaningful partons in high-energy processes. What is absent is an isolated quark as an asymptotic color-nonsinglet particle.

**Pitfall: treating color singlet as an ordinary global-charge selection rule.** Color is gauged. Physical states are gauge invariant; they do not merely have a conserved charge that happens to vanish.

**Pitfall: thinking asymptotic freedom proves confinement.** Asymptotic freedom shows that the coupling grows toward the infrared. It does not by itself derive the hadron spectrum, the mass gap, or flux tubes.

**Pitfall: using pure Yang–Mills center symmetry without checking matter content.** Fundamental quarks explicitly break center one-form symmetry. The center diagnostic must be modified or replaced in full QCD.

**Pitfall: confusing confinement with chiral symmetry breaking.** They are deeply related in real QCD, but they are logically distinct phenomena with different diagnostics.

## Relations to other pages

This page completes the infrared side of the QCD chapter. The [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) and [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/) pages explain why the coupling grows. [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) and [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/) explain one major consequence of the strong infrared regime.

For line-operator diagnostics, see [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/), [Area Law and Perimeter Law](/gauge-theories-standard-model/wilson-loops-confinement/area-law-and-perimeter-law/), [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/), and [Polyakov Loop](/gauge-theories-standard-model/wilson-loops-confinement/polyakov-loop/).

For a broader treatment, the Nonperturbative QFT volume should eventually contain the deeper pages on the mass gap, continuum limits, lattice gauge theory, confinement mechanisms, large-$N$ gauge theory, and rigorous open problems.

## Research status

The following facts are established at the level used in graduate QFT and phenomenology:

- QCD is asymptotically free in the ultraviolet.
- Physical hadrons are color singlets.
- Lattice QCD strongly supports confinement, string breaking, and the observed hadron spectrum within controlled numerical frameworks.
- Pure Yang–Mills theory has sharp center-symmetry and Wilson-loop confinement diagnostics.
- Full QCD with fundamental quarks modifies those diagnostics through screening.

The following remain active or open:

- a rigorous analytic proof of four-dimensional Yang–Mills confinement and mass gap;
- a first-principles real-time derivation of hadronization in full generality;
- the precise relation between confinement and chiral symmetry breaking across the space of gauge theories;
- the finite-density QCD phase diagram;
- continuum analytic control of strongly coupled QCD away from special limits.

The honest lesson is not “we do not understand confinement.” We understand a lot: diagnostics, lattice evidence, effective descriptions, large-$N$ clues, string-like flux tubes, and phenomenology. What remains hard is a complete analytic solution.

## Exercises

### Exercise 1: Area law and static potential

Suppose a large rectangular Wilson loop obeys

$$
\langle \mathcal W(C_{R,T})\rangle
\sim
\exp[-\sigma RT-\mu(2R+2T)]
$$

for $T\gg R$. Extract the static potential using

$$
V(R)=-\lim_{T\to\infty}\frac1T\log\langle \mathcal W(C_{R,T})\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Taking the logarithm gives

$$
\log\langle \mathcal W(C_{R,T})\rangle
\sim
-\sigma RT-2\mu R-2\mu T.
$$

Therefore

$$
V(R)
=
\lim_{T\to\infty}\frac{\sigma RT+2\mu R+2\mu T}{T}
=
\sigma R+2\mu.
$$

The $2\mu$ term is the self-energy of the external static sources. The physically important long-distance $R$-dependent part is $\sigma R$.

</details>

### Exercise 2: Why adjoint charges can be screened in pure Yang–Mills

Explain why an external adjoint source can be screened by gluons in pure $SU(N)$ Yang–Mills theory, while a fundamental source cannot.

<details><summary><strong>Solution</strong></summary>

Gluons transform in the adjoint representation. The adjoint representation has zero $N$-ality because the center of $SU(N)$ acts trivially on it. Combining an external adjoint source with dynamical gluons can therefore produce a color-singlet object.

A fundamental source has nonzero $N$-ality. Since gluons carry zero $N$-ality, no collection of gluons can neutralize the center charge of a single external fundamental source. In pure Yang–Mills theory this makes fundamental Wilson loops sharply sensitive to confinement. In full QCD, dynamical fundamental quarks are available, so the fundamental source can be screened.

</details>

### Exercise 3: String breaking threshold

In a simplified heavy-probe model, suppose the unscreened potential is $V_{Q\bar Q}(R)=V_0+\sigma R$ and the screened two-meson state has energy $E_{\rm br}=2M_{Q\bar q}$ independent of $R$. Estimate the string-breaking distance.

<details><summary><strong>Solution</strong></summary>

String breaking occurs when the two energies become comparable:

$$
V_0+\sigma R_{\rm br}\simeq 2M_{Q\bar q}.
$$

Thus

$$
R_{\rm br}\simeq \frac{2M_{Q\bar q}-V_0}{\sigma}.
$$

In real QCD this is only schematic because the external-source self-energy, mixing between flux-tube and two-meson states, quark masses, and lattice scheme dependence must be handled carefully. The physical point is that dynamical pair creation prevents an indefinitely rising fundamental potential.

</details>

## References

- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, strong-coupling area laws, and confinement diagnostics.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26 and 32, for Yang–Mills theory, quantum Yang–Mills, running coupling, and QCD/parton-model physics.
- Polyakov, *Gauge Fields and Strings*, especially Chs. 3, 5, and 7, for strong-coupling expansions, confinement criteria, and loop dynamics.
- Coleman, *Aspects of Symmetry*, Chs. 5 and 8, for gauge fields, asymptotic freedom, and large-$N$ intuition.
- Greensite, *An Introduction to the Confinement Problem*, for a dedicated treatment of confinement diagnostics and lattice perspectives.

## Version history

- **2026-06-18:** Initial page. Added the distinction between pure Yang–Mills confinement, full-QCD string breaking, color-singlet spectra, Wilson-loop diagnostics, and research-status caveats.
