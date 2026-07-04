---
title: "QCD as a Strongly Coupled QFT"
description: "Explains how QCD is weakly coupled in the ultraviolet but reorganizes nonperturbatively into confinement, chiral symmetry breaking, hadrons, and effective degrees of freedom in the infrared."
sidebar:
  label: "QCD as Strongly Coupled"
  order: 1
level: Advanced
status: "Polished draft"
source: "Srednicki; Schwartz; Weinberg, Vol. II; Shifman; Coleman; Burgess."
topics:
  - QCD
  - asymptotic freedom
  - dimensional transmutation
  - confinement
  - chiral symmetry breaking
  - hadrons
  - pions
  - lattice QCD
  - effective field theory
  - strong coupling
canonicalTopics:
  - nonperturbative-qft
  - qcd
  - strongly-coupled-gauge-theories
  - confinement
  - chiral-symmetry-breaking
  - hadron-spectrum
researchStatus:
  established:
    - "QCD is asymptotically free in the ultraviolet and nonperturbative in the infrared, with color-singlet hadrons, chiral symmetry breaking for light quarks, and a dynamically generated scale."
  active:
    - "Quantitative real-time, finite-density, near-conformal, and many excited-hadron questions remain active, and different methods control different observables."
---

## Summary

Quantum chromodynamics is the standard example of a quantum field theory whose microscopic Lagrangian is simple but whose infrared physics is not a weak-coupling expansion around the microscopic fields. At short distances, quarks and gluons are the right variables. At long distances, the right variables are color-singlet hadrons, approximate Goldstone bosons, flux tubes, condensates, topological sectors, and finite-volume spectra.

The basic paradox for a first encounter is this:

$$
\text{QCD is weakly coupled in the ultraviolet, but strongly coupled in the infrared.}
$$

There is no contradiction. The coupling runs. The ultraviolet theory can be studied perturbatively because of asymptotic freedom. The infrared theory is controlled by nonperturbative definitions, symmetry, lattice calculations, large-$N$ limits, chiral effective theory, heavy-quark limits, sum rules, and experimental input. None of these methods is “the whole theory” by itself, but together they form a coherent picture.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A schematic RG map of QCD flowing from asymptotically free quarks and gluons in the ultraviolet to the nonperturbative infrared scale where confinement, chiral symmetry breaking, hadrons, and effective descriptions appear.](/figures/nonperturbative-qft/qcd-strong-coupling-rg-map.svg)

<figcaption>

QCD has different useful variables at different scales. Above the nonperturbative scale, quarks and gluons are useful partonic degrees of freedom. Near and below $\Lambda_{\rm QCD}$, the theory reorganizes into color-singlet states, chiral dynamics, flux tubes, and nonperturbative observables.

</figcaption>
</figure>

## Prerequisites

Read [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/), [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/), [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/), [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/), and [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/) before this page.

It also helps to know [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/), [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/).

This page assumes familiarity with non-Abelian gauge theory and perturbative renormalization, but it states the main formulas needed to orient the nonperturbative discussion.

## Core idea

The microscopic QCD action for gauge group $SU(N_c)$ with $N_f$ Dirac quark flavors is, schematically,

$$
S_{\rm QCD}
=\int d^4x\left[
-\frac{1}{2g^2}\operatorname{tr} F_{\mu\nu}F^{\mu\nu}
+\sum_{f=1}^{N_f}\bar q_f(i\gamma^\mu D_\mu-m_f)q_f
\right]
+S_\theta .
$$

The theta term is

$$
S_\theta
=\theta\, Q,
\qquad
Q=\frac{1}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu},
$$

with the Lorentzian or Euclidean factors fixed by the conventions of [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) and [Conventions and Notation](/nonperturbative-qft/conventions/). For ordinary QCD, $N_c=3$, and the quark masses are hierarchical: $u,d$ are light on the hadronic scale, $s$ is intermediate, and $c,b,t$ are heavy enough that specialized effective descriptions are useful.

The Lagrangian is not the problem. The problem is that the fields appearing in it are not the long-distance particles. Quarks and gluons are excellent ultraviolet variables, but the infrared Hilbert space is organized by color singlets. A page on QCD as a strongly coupled QFT is therefore not primarily a page about writing the Lagrangian; it is about understanding the RG flow from the Lagrangian to the observed and computed long-distance physics.

A useful slogan is:

$$
\text{QCD is a weakly coupled theory of partons in the UV and a strongly coupled theory of hadrons in the IR.}
$$

Both clauses are essential. Dropping the first erases asymptotic freedom and high-energy phenomenology. Dropping the second erases confinement, chiral symmetry breaking, and almost all of the hadron spectrum.

## Running coupling and dimensional transmutation

At short distances, QCD is asymptotically free. To one loop, the gauge coupling obeys

$$
\mu\frac{d g}{d\mu}
=\beta(g)
=-\frac{b_0}{16\pi^2}g^3+O(g^5),
\qquad
b_0=\frac{11}{3}N_c-\frac{2}{3}N_f .
$$

For $SU(3)$ with not too many quark flavors, $b_0>0$, so $g(\mu)$ decreases as $\mu$ increases. Solving the one-loop equation gives

$$
\frac{1}{g^2(\mu)}
=\frac{b_0}{8\pi^2}\log\frac{\mu}{\Lambda},
$$

or, equivalently,

$$
\Lambda
=\mu\exp\left[-\frac{8\pi^2}{b_0 g^2(\mu)}\right]
\times\text{higher-loop and scheme factors}.
$$

This formula is the first nonperturbative-looking object in perturbative QCD. The scale $\Lambda$ is invisible in a Taylor expansion in $g^2$ around $g=0$ because it contains $e^{-\mathrm{const}/g^2}$. Yet it is the scale that organizes the infrared theory. This is **dimensional transmutation**: the dimensionless coupling is traded for a dimensionful scale.

The one-loop formula should not be overinterpreted. The precise numerical value of $\Lambda_{\rm QCD}$ depends on scheme and flavor thresholds. But the existence of a dynamically generated scale is a physical fact. It is why a theory with classically dimensionless gauge coupling can produce hadron masses, string tensions, condensates, and topological susceptibilities with dimensions.

:::note[What “large coupling” means]
The phrase “the coupling becomes large” is not an observable statement by itself. The coupling depends on scheme and definition. The physical statement is that there is no small parameter that makes the long-distance expansion in quark and gluon Feynman diagrams reliable. One must use nonperturbative observables and methods.
:::

## The scale hierarchy in QCD

The running coupling divides QCD into regimes.

| Regime | Useful degrees of freedom | Typical tools | What can go wrong |
|---|---|---|---|
| Hard ultraviolet | Quarks and gluons | Perturbation theory, factorization, PDFs, jets | Infrared sensitivity enters through hadronization and matrix elements. |
| Around $\Lambda_{\rm QCD}$ | Mixed partonic and hadronic descriptions | Lattice QCD, sum rules, models, matching | No universal small coupling controls all observables. |
| Light-hadron infrared | Pions, kaons, nucleons, resonances | Chiral perturbation theory, lattice spectra, scattering EFTs | Resonances and multi-particle thresholds require care. |
| Heavy-quark systems | Heavy quarks plus gluons and light hadrons | HQET, NRQCD, potential methods, lattice QCD | Different scales must be separated consistently. |
| Pure gauge limit | Glueballs and flux tubes | Lattice Yang–Mills, large-$N$, effective strings | It is not identical to real-world QCD with light quarks. |

This table is not a replacement for calculations. It is a diagnostic for choosing the right language. A quark-level calculation of a hard scattering amplitude and a chiral effective theory calculation of pion scattering are not competitors; they live in different regimes of the same underlying QFT.

## Confinement with and without dynamical quarks

In pure Yang–Mills theory, confinement can be diagnosed sharply by Wilson loops of nonzero center charge. A large rectangular Wilson loop obeying

$$
\langle W(R,T)\rangle
\sim e^{-T V(R)},
\qquad
V(R)\sim \sigma R,
$$

signals a stable color-electric flux tube with string tension $\sigma$. This is the cleanest version of the Wilson-loop criterion.

Real QCD contains dynamical quarks in the fundamental representation. That changes the asymptotic story. A flux tube between an external heavy quark and antiquark can break by producing a light quark–antiquark pair. Therefore the fundamental Wilson loop need not have an area law at arbitrarily large distances. Instead, the static potential rises approximately linearly over a range and then saturates near the threshold for two heavy-light mesons.

This does not mean QCD is unconfining in the everyday phenomenological sense. Isolated colored particles are not observed as asymptotic states. The physical spectrum consists of color singlets: mesons, baryons, and glue-rich excitations. The point is subtler:

$$
\text{quark confinement in real QCD}
\neq
\text{asymptotic fundamental Wilson-loop area law in pure Yang–Mills}.
$$

The first is a statement about the physical spectrum and color singlet asymptotic states. The second is a sharp line-operator statement in a theory without dynamical fundamental screening.

## Chiral symmetry breaking

If the light quark masses are temporarily set to zero, the QCD Lagrangian has an approximate global chiral symmetry

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_B,
$$

with the axial $U(1)_A$ symmetry broken by the anomaly. The observed light-hadron spectrum and lattice calculations support the spontaneous breaking pattern

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V .
$$

The standard order parameter is the chiral condensate

$$
\langle \bar q q\rangle
\neq 0
$$

in the chiral limit, with a renormalization convention understood. This condensate is not just a number to memorize. It says that the vacuum pairs left- and right-handed quarks and therefore does not respect the full chiral symmetry of the massless Lagrangian.

Goldstone’s theorem then predicts massless pseudoscalar modes in the exact chiral limit. In real QCD the light quark masses are small but nonzero, so the pions are pseudo-Goldstone bosons. The leading relation is the Gell-Mann–Oakes–Renner relation,

$$
f_\pi^2 m_\pi^2
=-(m_u+m_d)\langle \bar u u\rangle+O(m_q^2),
$$

where the condensate and quark masses must be understood in the same renormalization scheme. The important nonperturbative lesson is that the small pion mass is not the generic hadronic mass scale. It is protected by approximate chiral symmetry.

Chiral symmetry breaking and confinement often appear together in QCD-like theories, but they are not logically identical. Some theories may confine without breaking a given chiral symmetry; other strongly coupled gauge theories may flow to a conformal fixed point where neither a mass gap nor a chiral condensate appears. The distinction becomes central in [Conformal Window Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/conformal-window-preview/) and [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/).

## Hadrons as nonperturbative states

The physical states of low-energy QCD are color singlets. They include mesons, baryons, multi-hadron states, resonances, and in pure gauge theory glueballs. A hadron is not a small perturbation of a single quark field. It is a nonperturbative state created by gauge-invariant operators.

For example, meson interpolating operators have the schematic form

$$
\mathcal O_M(x)=\bar q(x)\Gamma q(x),
$$

baryon operators for $SU(3)$ have the schematic form

$$
\mathcal O_B(x)=\epsilon_{abc}q^a(x)q^b(x)q^c(x),
$$

and glueball operators are built from gauge-field strengths, such as

$$
\mathcal O_G(x)=\operatorname{tr}F_{\mu\nu}F^{\mu\nu}(x).
$$

In Euclidean signature, their two-point functions have spectral decompositions. For a zero-momentum operator $\mathcal O$, one expects at large Euclidean time

$$
C(\tau)=\langle \mathcal O(\tau)\mathcal O^\dagger(0)\rangle
=\sum_n |\langle 0|\mathcal O|n\rangle|^2 e^{-E_n\tau}.
$$

At sufficiently large $\tau$, the lowest state with the same quantum numbers dominates. This is the basic reason lattice QCD can extract hadron masses from Euclidean correlators. The hard part is everything hidden in “sufficiently”: operator overlap, excited-state contamination, finite-volume effects, multi-particle states, chiral extrapolation, continuum extrapolation, and statistical errors.

The conceptual point is simple: the hadron spectrum is a property of correlation functions of gauge-invariant operators. It is not a list of elementary fields in the microscopic Lagrangian.

## Partons and hadrons are compatible descriptions

A common beginner mistake is to think that the parton model and confinement contradict each other. They do not. They describe different kinematic regimes.

At high momentum transfer, a hard probe resolves short distances. Because QCD is asymptotically free, the short-distance subprocess can be computed using quarks and gluons. Long-distance information is packaged into parton distribution functions, fragmentation functions, distribution amplitudes, or other nonperturbative matrix elements. Factorization theorems separate the hard and soft pieces when the process and observable allow it.

At low energies, a detector does not see isolated colored partons. It sees color-singlet hadrons. The transition from colored partons in a hard subprocess to color-singlet final states is hadronization, a genuinely nonperturbative process.

Thus the right statement is not “quarks are real” or “quarks are not real.” In QFT language, quark fields are the correct microscopic variables in the Lagrangian and the correct short-distance degrees of freedom in many observables, but quark states are not isolated asymptotic particles in the confining regime.

## Topology and theta dependence

QCD also has topological sectors. Gauge fields in Euclidean spacetime can carry integer topological charge in suitable finite-action settings,

$$
Q=\frac{1}{32\pi^2}\int F^a_{\mu\nu}\widetilde F^{a\mu\nu}\,d^4x.
$$

The theta angle weights sectors by phases. The vacuum energy as a function of $\theta$ defines the topological susceptibility,

$$
\chi_t
=\left.\frac{\partial^2 E(\theta)}{\partial\theta^2}\right|_{\theta=0}
=\frac{\langle Q^2\rangle}{V}
$$

in a Euclidean finite-volume normalization where the last expression is meaningful. The exact relation depends on volume, boundary conditions, fermion content, and continuum limit.

Instantons make topology visible semiclassically in some regimes, but ordinary low-energy QCD is not generally controlled by a dilute instanton gas. The anomaly, fermion zero modes, chiral rotations, and theta dependence are nevertheless central to QCD. They explain, among other things, why the $U(1)_A$ symmetry does not produce a ninth light Goldstone boson in the same way as the non-Abelian chiral symmetries.

The strong CP problem is not solved on this page. The nonperturbative point needed here is that topology is not optional extra decoration in QCD; it is part of the vacuum structure.

## Methods that actually compute things

Strongly coupled does not mean “incalculable.” It means that the ordinary expansion in small $g$ around quark and gluon fields is not the universal tool. Different questions use different methods.

| Method | What it is good for | Main caveat |
|---|---|---|
| Lattice QCD | Hadron masses, matrix elements, thermodynamics at zero or small chemical potential, Wilson loops, topological susceptibility. | Real time and finite baryon density are difficult; continuum, volume, and quark-mass extrapolations matter. |
| Chiral perturbation theory | Low-energy pion and light-hadron physics controlled by approximate chiral symmetry. | It is an expansion below a breakdown scale, not a model of all hadrons. |
| Heavy-quark effective theory | Systems with a quark mass much larger than $\Lambda_{\rm QCD}$. | Requires careful matching and power counting. |
| Large-$N_c$ | Planar organization, narrow resonances, baryon scaling, and qualitative string-like structure. | Real QCD has $N_c=3$; the limit is powerful but not exact. |
| QCD sum rules | Relates operator product expansions to hadronic spectral information. | Requires modeling or controlling spectral continua and condensates. |
| Schwinger–Dyson and Bethe–Salpeter equations | Dynamical mass generation and bound-state equations. | Exact equations require truncation; gauge covariance and systematic error control are subtle. |
| Experiment plus factorization | Hard scattering, PDFs, jets, and extraction of nonperturbative functions. | Factorization is observable-dependent and has power corrections. |

This division of labor is a sign of maturity, not weakness. Strong QFT is not conquered by one magic method. It is triangulated.

## What QCD teaches about nonperturbative QFT

QCD teaches several general lessons.

First, microscopic fields need not be asymptotic particles. The Lagrangian fields are not always the particles in the detector.

Second, RG flow can generate scales. A classically scale-free gauge theory can produce masses through dimensional transmutation and strong dynamics.

Third, global symmetries and anomalies are more robust than perturbative diagrams. Chiral symmetry, baryon number, flavor symmetry, anomalies, and theta dependence constrain the infrared even when the coupling is large.

Fourth, numerical and analytic methods are complementary. Lattice simulations can compute spectra and matrix elements; chiral effective theory explains low-energy symmetry structure; large-$N$ organizes diagrams and resonances; continuum functional methods supply approximations and intuition.

Fifth, nonperturbative physics is not synonymous with mystery. It is physics whose expansion variables, degrees of freedom, and definitions differ from the most familiar perturbative ones.

## A compact diagnostic table

| Diagnostic | In QCD-like theories | What it tells you |
|---|---|---|
| Wilson loop | Shows flux-tube behavior in pure gauge theory and intermediate string formation with heavy sources. | Confinement and screening of external charges. |
| Polyakov loop | Thermal center diagnostic in pure gauge theory; crossover indicator with dynamical quarks. | Deconfinement and heavy-quark free energy. |
| Chiral condensate | Nonzero in the chiral limit for ordinary low-flavor QCD. | Spontaneous chiral symmetry breaking. |
| Pion mass dependence | $m_\pi^2$ proportional to light quark masses at leading order. | Pseudo-Goldstone nature of pions. |
| Hadron correlators | Exponential falloff in Euclidean time. | Masses and finite-volume spectra. |
| Topological susceptibility | Curvature of vacuum energy in $\theta$. | Topological fluctuations and anomaly-sensitive physics. |
| String tension | Slope of the static potential in the unbroken flux-tube regime. | Energy per unit length of color-electric flux. |
| Spectral functions | Real-time response and resonances. | Transport, scattering, decay channels, and analytic continuation challenges. |

## Common pitfalls

**Mistake: treating $\Lambda_{\rm QCD}$ as a particle mass.** It is a scheme-dependent scale parameter. Physical masses, string tensions, and condensates are related to it but are not identical to it.

**Mistake: saying perturbation theory fails everywhere in QCD.** It fails for generic long-distance hadronic physics. It works extremely well for sufficiently hard processes after infrared-safe observables and factorization are handled correctly.

**Mistake: equating confinement with a fundamental Wilson-loop area law in real QCD.** Light dynamical quarks screen fundamental sources and break strings. The absence of isolated colored asymptotic particles remains, but the pure-gauge Wilson criterion must be modified.

**Mistake: thinking pions are light because quarks are weakly bound.** Pions are light because they are pseudo-Goldstone bosons of approximate chiral symmetry breaking, not because all hadrons are weakly bound.

**Mistake: treating the quark condensate as an ordinary classical field.** It is a renormalized vacuum expectation value of a composite operator, defined with a scheme and scale, and meaningful through symmetry realization and observable consequences.

**Mistake: using instantons as the default explanation for every QCD nonperturbative effect.** Instantons are crucial for topology, anomalies, and some semiclassical regimes. They do not by themselves give a general controlled derivation of confinement in ordinary four-dimensional QCD.

## Worked exercises

### Exercise 1: Dimensional transmutation at one loop

Starting from

$$
\mu\frac{dg}{d\mu}
=-\frac{b_0}{16\pi^2}g^3,
$$

show that the RG-invariant scale can be written as

$$
\Lambda=\mu\exp\left[-\frac{8\pi^2}{b_0g^2(\mu)}\right]
$$

at one loop.

<details>
<summary><strong>Solution</strong></summary>

Rewrite the beta function as

$$
\frac{dg}{g^3}=-\frac{b_0}{16\pi^2}\frac{d\mu}{\mu}.
$$

Integrating gives

$$
-\frac{1}{2g^2(\mu)}
=-\frac{b_0}{16\pi^2}\log\mu+C.
$$

Equivalently,

$$
\frac{1}{g^2(\mu)}
=\frac{b_0}{8\pi^2}\log\frac{\mu}{\Lambda},
$$

where the integration constant has been written as a scale $\Lambda$. Solving for $\Lambda$ gives

$$
\Lambda=\mu\exp\left[-\frac{8\pi^2}{b_0g^2(\mu)}\right].
$$

This scale is RG invariant at this order.

</details>

### Exercise 2: Asymptotic freedom bound at one loop

For an $SU(N_c)$ gauge theory with $N_f$ Dirac fermions in the fundamental representation, the one-loop coefficient is

$$
b_0=\frac{11}{3}N_c-\frac{2}{3}N_f.
$$

For $N_c=3$, what is the condition on $N_f$ for one-loop asymptotic freedom?

<details>
<summary><strong>Solution</strong></summary>

Asymptotic freedom at one loop requires $b_0>0$:

$$
\frac{11}{3}N_c-\frac{2}{3}N_f>0.
$$

For $N_c=3$,

$$
11-\frac{2}{3}N_f>0,
$$

so

$$
N_f<\frac{33}{2}=16.5.
$$

Since $N_f$ is an integer, this gives $N_f\le16$ at one loop. This condition is necessary for asymptotic freedom in this perturbative analysis, but it does not by itself determine whether the infrared theory confines, breaks chiral symmetry, or flows to a conformal fixed point.

</details>

### Exercise 3: Pions in the chiral limit

Use the leading relation

$$
f_\pi^2m_\pi^2=-(m_u+m_d)\langle \bar u u\rangle+O(m_q^2)
$$

to explain why pions become massless when $m_u,m_d\to0$, assuming the condensate remains nonzero and $f_\pi$ remains finite.

<details>
<summary><strong>Solution</strong></summary>

If $m_u,m_d\to0$, the right-hand side goes to zero linearly in the light quark masses, up to higher-order corrections. If $f_\pi$ remains finite and nonzero, then

$$
m_\pi^2\to0.
$$

This is the pseudo-Goldstone interpretation of the pion. In the exact chiral limit, the spontaneously broken axial generators produce massless Goldstone bosons. With small but nonzero quark masses, the pions acquire small masses.

</details>

### Exercise 4: Why string breaking modifies the Wilson criterion

Suppose the static potential between external fundamental sources behaves approximately as

$$
V(R)\approx \sigma R
$$

for intermediate separations, but dynamical quark pair creation allows the flux tube to break into two heavy-light mesons of total energy $2M_{Qq}$. Estimate the distance at which string breaking becomes energetically favorable.

<details>
<summary><strong>Solution</strong></summary>

String breaking becomes favorable when the energy stored in the flux tube is comparable to the two-meson threshold:

$$
\sigma R_{\rm break}\sim 2M_{Qq}-2m_Q^{\rm bare/eff},
$$

where the subtraction indicates that the static-source self-energy convention must be handled consistently. In a schematic potential model one often writes simply

$$
R_{\rm break}\sim \frac{E_{\rm threshold}}{\sigma}.
$$

The main point is not the precise formula but the logic: once pair creation is allowed, the linearly rising potential is replaced at large distance by a screened two-hadron state. Therefore an asymptotic fundamental Wilson-loop area law is not the right confinement criterion in QCD with light dynamical quarks.

</details>

## Relations to other pages

This page begins the [Strongly Coupled Gauge Theories](/nonperturbative-qft/strongly-coupled-gauge-theories/) chapter. Continue to [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/) for the chiral condensate and pions, to [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/) for color-singlet states, finite-volume levels, and resonances, to [Glueballs](/nonperturbative-qft/strongly-coupled-gauge-theories/glueballs/) for pure-gauge bound states, to [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) for the long-flux-tube string picture, to [Conformal Window Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/conformal-window-preview/) for many-flavor infrared fixed points, and to [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/) for near-conformal slow running. It uses the confinement dictionary developed in [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/), [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/), and [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/).

For operator diagnostics, see [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/), and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/).

For topology and theta dependence, see [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/), and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/). For large-$N$ intuition, see [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) before the later Large-N Methods chapter.

## References

- M. Srednicki, *Quantum Field Theory*, especially the chapters on non-Abelian gauge theory, beta functions, QCD, Wilson loops, lattice theory, confinement, chiral symmetry breaking, and theta vacua.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on Yang–Mills theory, quantum Yang–Mills theory, QCD, running coupling, partons, and chiral symmetry.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for QCD, chiral symmetry, current algebra, and strong-interaction applications.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, current algebra, anomalies, and asymptotic freedom.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on phases of gauge theories, anomalies, confinement, and large-$N$.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling, compact gauge theory, confinement, and large-$N$/string intuition.
- C. P. Burgess, *Introduction to Effective Field Theory*, for QCD and chiral perturbation theory as effective field theory.

## Version history

- **2026-06-27:** Added links to the new Conformal Window Preview and Walking Gauge Theories Preview pages.
- **2026-06-27:** Added links to the new Glueballs and QCD String Preview pages.
- **2026-06-27:** Added links to the new Chiral Symmetry Breaking and Hadron Spectrum pages.
- **2026-06-27:** Initial polished draft, added as the anchor ordinary page for the Strongly Coupled Gauge Theories chapter.
