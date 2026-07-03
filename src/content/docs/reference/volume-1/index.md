---
title: "Foundations of QFT"
description: "The canonical core of QFT.org: fields, states, particles, quantization, propagators, path integrals, symmetry, locality, gauge redundancy, structural principles, and foundational models."
sidebar:
  label: "Overview"
  order: 0
level: "Graduate"
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Weinberg 1995; Zee 2010; Schwartz 2014; Zinn-Justin 2021"
topics:
  - "foundations"
  - "quantum fields"
  - "canonical quantization"
  - "path integrals"
  - "propagators"
  - "symmetry"
  - "gauge redundancy"
  - "locality"
canonicalTopics:
  - "foundations-of-qft"
  - "quantum-field-language"
  - "operator-path-integral-structural-lenses"
researchStatus:
  established:
    - "The introductory architecture of relativistic QFT, free fields, correlators, perturbative expansion, and basic symmetry principles is textbook-standard."
    - "The conventions and assumptions used here are meant to make later QFT.org volumes interoperable."
  active:
    - "The precise nonperturbative and mathematical definition of general interacting QFTs remains a major research area beyond this volume."
---

## Summary

**Foundations of QFT** is the volume where the basic words of quantum field theory become precise enough to use everywhere else on QFT.org.

The volume teaches the shared grammar of the subject: fields, actions, states, particles, Fock space, canonical quantization, path integrals, correlation functions, propagators, Wick expansion, symmetry, locality, gauge redundancy, and the structural assumptions that keep the formalism honest.

It is not trying to be a miniature version of the whole website. Renormalization, full Yang–Mills theory, anomalies, conformal field theory, nonperturbative dynamics, scattering amplitudes, lattice methods, supersymmetry, holography, and rigorous QFT all have their own volumes. Foundations gives you the language needed to enter those volumes without drowning in notation fog.

:::note[North star]
A good Foundations page should answer three questions at once:

1. What is the object?
2. Which formalism is being used?
3. Which assumptions make the statement true?

That is the difference between remembering formulas and understanding QFT.
:::

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Foundations of QFT volume map](/figures/foundations/foundations-section-map.svg)

<figcaption>

The Foundations volume develops the shared language of QFT: classical fields, relativistic particle states, operator quantization, free fields, correlators, path integrals, perturbative expansion, symmetry, gauge redundancy, structural principles, and model examples. Later volumes specialize this language into renormalization, full gauge theory, CFT, scattering, nonperturbative dynamics, rigorous QFT, holography, matter, and frontiers.

</figcaption>
</figure>

## What belongs in this volume

Foundations should answer the questions that reappear no matter which QFT subfield you work in.

| Question | Canonical entrances |
|---|---|
| What is a field? | [Classical Field Theory](/foundations/classical-field-theory/), [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/), [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) |
| Why are particles not enough? | [Relativistic Particles and Fields](/foundations/relativistic-particles-and-fields/), [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) |
| What is Fock space? | [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) |
| How do fields become oscillators? | [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/), [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) |
| What is a free relativistic field? | [Free Relativistic Fields](/foundations/free-fields/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Dirac Field](/foundations/free-fields/dirac-field/), [Maxwell Field](/foundations/free-fields/maxwell-field/) |
| What is a propagator? | [Correlation Functions and Propagators](/foundations/correlators-and-propagators/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) |
| Why do path integrals work? | [Path Integral Formalism](/foundations/path-integral-formalism/), [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) |
| What do Feynman diagrams mean? | [Interactions and Wick Expansion](/foundations/interactions-and-wick-expansion/), [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) |
| What is symmetry doing? | [Symmetry and Spacetime Structure](/foundations/symmetry-and-spacetime/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) |
| What is gauge redundancy? | [Gauge Fields: First Principles](/foundations/gauge-fields-first-principles/), [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) |
| What protects causality and probability? | [Structural Principles of QFT](/foundations/structural-principles/), [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/), [Unitarity](/foundations/structural-principles/unitarity/) |
| What are the first model theories? | [Foundational Models](/foundations/foundational-models/), [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/), [Yukawa Theory](/foundations/foundational-models/yukawa-theory/), [QED Preview](/foundations/foundational-models/qed-preview/) |

A compact slogan for the volume is:

```txt
Fields are the local language.
States are the Hilbert-space language.
Correlators are the measurement-and-dynamics language.
Path integrals are the source-and-summing language.
Symmetry and locality tell the languages how to agree.
```

## What this volume does not try to do

Foundations contains previews, not final destinations. A preview should identify the object, state the conventions, and show why the object belongs in QFT. The full machinery belongs in later volumes.

| Preview here | Full home |
|---|---|
| UV divergences, counterterms, and running | [Renormalization, RG, and EFT](/renormalization-rg-eft/) |
| scattering amplitudes, cross sections, and precision calculations | [Perturbative QFT and Scattering](/perturbative-qft/) |
| full Yang–Mills theory, QCD, electroweak theory, and the Standard Model | [Gauge Theories and the Standard Model](/gauge-theories-standard-model/) |
| anomalies, topological terms, generalized symmetries, and defects | [Symmetry, Anomalies, and Topology](/symmetry-anomalies-topology/) |
| confinement, instantons, strong coupling, and lattice definitions | [Nonperturbative QFT](/nonperturbative-qft/) |
| conformal symmetry, crossing, conformal blocks, and bootstrap | [CFT and Bootstrap](/cft-bootstrap/) |
| theorem-first definitions, reconstruction, and constructive QFT | [Mathematical and Rigorous QFT](/rigorous-qft/) |

This boundary matters. Without it, Foundations becomes a polite junk drawer. With it, the volume stays readable.

## Prerequisites

You should know ordinary quantum mechanics, special relativity, classical mechanics, and basic electromagnetism. You should also be comfortable with Fourier transforms, distributions, linear algebra, and the idea of a group acting on fields or states.

Start with [Conventions and Normalizations](/foundations/conventions-and-normalizations/). It fixes the mostly-minus metric, Fourier phases, relativistic state normalization, propagator denominators, spinor conventions, path-integral normalization, and Euclidean continuation rules used throughout the volume.

:::tip[Do not skip conventions]
A surprising fraction of QFT frustration is not physics. It is mismatched signs, factors of $2\pi$, and incompatible normalizations. The convention page is the boring shield against fake confusion.
:::

## How to read this volume

The chapter overviews are now the best entrances. Read them first when you are entering a chapter, then follow the reading path inside the chapter.

| Chapter | Role in the volume | Best first use |
|---|---|---|
| [Classical Field Theory](/foundations/classical-field-theory/) | Turns fields into dynamical variables with actions, equations, symmetries, stress tensors, Hamiltonians, constraints, and normal modes. | You need the classical grammar before quantization. |
| [Relativistic Particles and Fields](/foundations/relativistic-particles-and-fields/) | Explains why relativistic quantum theory naturally leads to Fock space, particle species, antiparticles, and fields. | You are asking why QFT is not just relativistic quantum mechanics. |
| [Canonical Quantization](/foundations/canonical-quantization/) | Builds the operator route from oscillators to equal-time commutators, scalar fields, normal ordering, and fermionic anticommutators. | You want to know what the Hilbert-space construction is doing. |
| [Free Relativistic Fields](/foundations/free-fields/) | Collects the basic free scalar, spinor, and vector fields used everywhere later. | You need the standard field equations, mode expansions, propagators, and spin or polarization sums. |
| [Correlation Functions and Propagators](/foundations/correlators-and-propagators/) | Distinguishes Wightman functions, commutators, Feynman propagators, retarded functions, spectral representations, and connected correlators. | You are confused by the word “Green function.” |
| [Path Integral Formalism](/foundations/path-integral-formalism/) | Builds the source-functional route from finite Gaussians to field integrals, Euclidean continuation, Grassmann variables, determinants, and measures. | You want to understand why diagrams come from Gaussian integrals. |
| [Interactions and Wick Expansion](/foundations/interactions-and-wick-expansion/) | Shows how the interaction picture, Dyson series, Wick theorem, and source functionals produce diagrams and perturbative bookkeeping. | You want the bridge from free fields to Feynman diagrams. |
| [Symmetry and Spacetime Structure](/foundations/symmetry-and-spacetime/) | Organizes Poincaré symmetry, Lorentz representations, spinors, internal symmetries, currents, Ward identities, discrete symmetries, spin–statistics, and CPT. | You want to know what symmetry controls before gauge theory and anomalies. |
| [Gauge Fields: First Principles](/foundations/gauge-fields-first-principles/) | Explains gauge redundancy, Maxwell theory, charged matter, gauge fixing, non-Abelian previews, and BRST as first-principles ideas. | You need to separate physical symmetry from descriptive redundancy. |
| [Structural Principles of QFT](/foundations/structural-principles/) | States the assumptions behind locality, unitarity, spectral positivity, clustering, reflection positivity, analyticity, sectors, and axiomatic previews. | You want to know which famous statements have hidden hypotheses. |
| [Foundational Models](/foundations/foundational-models/) | Gives first model cards for φ⁴ theory, Yukawa theory, Scalar QED, QED, and sigma-model previews. | You want concrete Lagrangians where the abstract machinery has something to act on. |

## A first-pass spine

A first pass should be linear enough to build momentum, but not so long that it becomes a second textbook. Here is the shortest path that still carries the main architecture.

1. [Conventions and Normalizations](/foundations/conventions-and-normalizations/)
2. [Classical Field Theory](/foundations/classical-field-theory/)
3. [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/)
4. [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/)
5. [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/)
6. [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/)
7. [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/)
8. [Dirac Field](/foundations/free-fields/dirac-field/)
9. [Time Ordering](/foundations/correlators-and-propagators/time-ordering/)
10. [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/)
11. [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/)
12. [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/)
13. [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/)
14. [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/)
15. [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/)
16. [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/)
17. [Common Confusions](/foundations/common-confusions/)

After that, fill in the chapters you skipped: complex scalars, fermionic quantization, Weyl and Majorana fields, spinor bilinears, Maxwell and Proca fields, spectral representations, Euclidean QFT, Grassmann variables, Ward identities, spin–statistics, CPT, BRST previews, and the model pages.

## Study routes

Different readers should cut through the same volume differently.

| Route | Recommended path |
|---|---|
| Operator-first | particles and Fock space → canonical quantization → free fields → commutators and locality → perturbation theory |
| Path-integral-first | classical actions → finite Gaussians → quantum-mechanical path integral → scalar field path integral → sources → Euclidean QFT → Wick expansion |
| Particle-theory-first | single-particle states → relativistic normalization → free fields → LSZ preview → Feynman diagrams → QED preview → unitarity |
| Gauge-theory-first | gauge redundancy → Maxwell as gauge theory → charged matter → gauge fixing → non-Abelian preview → BRST preview |
| Mathematical-physics-first | locality → spectral condition → cluster decomposition → reflection positivity → analyticity → axiomatic QFT preview |
| Fast conceptual repair | common confusions → conventions → Why Fields? → Feynman propagator → gauge redundancy → locality |

The operator route is best for seeing what Hilbert space and particles are doing. The path-integral route is best for sources, determinants, Euclidean continuation, and diagram generation. The structural route is best for learning why QFT is not just a bag of computational tricks.

## The three-language rule

A mature QFT explanation should usually say the same thing in three languages.

| Language | Typical object | What it makes transparent |
|---|---|---|
| Operator language | $\langle 0|T\phi(x)\phi(y)|0\rangle$ | Hilbert space, states, unitarity, commutators, causality |
| Path-integral language | $Z[J]=\int\mathcal D\phi\,e^{iS+i\int J\phi}$ | sources, Gaussian integrals, diagrams, determinants, semiclassics |
| Structural language | locality, spectrum, clustering, analyticity | what is assumed, what is derived, and what can fail |

For example, the scalar Feynman propagator is simultaneously a time-ordered vacuum correlator, an inverse of the quadratic path-integral kernel with an $i\epsilon$ prescription, and an analytic object whose pole structure encodes one-particle states. Treating only one of those descriptions as “the real one” is how a lot of avoidable confusion enters.

## Core formula anchors

These formulas are not a substitute for the chapter pages. They are landmarks: you should know where each one lives and what assumptions support it.

| Anchor | Formula | Main page |
|---|---|---|
| On-shell measure | $d\mu(p)=\dfrac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}$ | [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) |
| Equal-time scalar algebra | $[\phi(t,\mathbf x),\pi(t,\mathbf y)]=i\delta^{(3)}(\mathbf x-\mathbf y)$ | [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) |
| Real scalar expansion | $\phi(x)=\int d\mu(p)\,[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}]$ | [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) |
| Scalar Feynman propagator | $D_F(p)=\dfrac{i}{p^2-m^2+i\epsilon}$ | [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) |
| Source functional | $Z[J]=\int\mathcal D\phi\,e^{iS[\phi]+i\int J\phi}$ | [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) |
| Wick contraction logic | time-ordered products become sums of normal-ordered products and contractions | [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) |
| Ward identity logic | symmetry of the action and measure implies identities among correlators | [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) |
| Microcausality | $[\mathcal O_1(x),\mathcal O_2(y)]=0$ for spacelike separation, for bosonic local observables | [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) |

## Assumptions to watch

Many famous QFT statements are conditional statements. When using a theorem or structural slogan, check the assumptions.

:::note[Common structural assumptions]
Relativistic-QFT theorems usually rely on some combination of locality or microcausality, Lorentz or Poincaré invariance, positive energy, unitarity, a stable vacuum, cluster decomposition, and an appropriate domain of fields or observables.
:::

| Statement | Assumptions to inspect |
|---|---|
| Spin–statistics | Lorentz invariance, locality, positive energy, Hilbert-space positivity |
| CPT theorem | locality, Lorentz invariance, unitarity or Hilbert-space positivity, stable vacuum |
| Källén–Lehmann representation | translation invariance, spectral condition, positivity, completeness of states |
| Reflection positivity | Euclidean covariance plus a reflection-positive Euclidean measure or correlator system |
| Cluster decomposition | appropriate vacuum choice, locality, spectrum, and absence of long-range obstructions |
| Gauge-fixing independence | gauge-invariant observables, correct measure, ghosts or BRST structure when needed |

The point is not to bury the reader in axioms. The point is to prevent a theorem from being applied outside the world where it is true.

## Common checkpoints

By the end of this volume, you should be able to explain the following without reaching for a formula sheet:

- why the Klein–Gordon equation failed as one-particle probability mechanics but succeeds as a field equation;
- how a free real scalar field decomposes into harmonic oscillator modes;
- why complex scalar fields contain particles and antiparticles;
- why fermionic fields use anticommutators;
- why the Feynman propagator is not the same object as a retarded response function;
- what the $i\epsilon$ prescription does;
- why connected correlators are generated by the logarithm of the source functional;
- how Wick's theorem turns operator contractions into diagrammatic bookkeeping;
- why gauge symmetry is redundancy rather than an ordinary physical symmetry;
- how Ward identities express symmetry inside correlation functions;
- which assumptions sit behind spin–statistics, CPT, spectral positivity, and cluster decomposition.

These checkpoints are a better measure of progress than how many diagrams you can draw quickly.

## Sources and further reading

### Standard textbook treatments

- Mark Srednicki, *Quantum Field Theory* (2007). Especially useful for a step-by-step construction through spin zero, spin one-half, spin one, path integrals, Feynman rules, Ward identities, and renormalization.
- Sidney Coleman, *Lectures on Quantum Field Theory* (2019). Especially valuable for the operator viewpoint, Fock space, Wick expansion, scattering, current algebra, gauge fixing, and the habit of asking what a formula really means.
- Steven Weinberg, *The Quantum Theory of Fields, Volume I: Foundations* (1995). The most systematic particle-first treatment of why relativistic quantum mechanics, cluster decomposition, and locality lead naturally to quantum fields.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed. (2010). A physically motivated companion, especially useful for path integrals, diagrams, symmetry, gauge theory, and connections to statistical and condensed matter physics.
- Matthew Schwartz, *Quantum Field Theory and the Standard Model* (2014). A modern route from foundations to Standard Model calculations, with useful parallel derivations and many worked problems.

### For broader perspective

- A. M. Polyakov, *Gauge Fields and Strings* (1987). Valuable for the deep relation between statistical mechanics, quantum fields, gauge systems, topology, and strings.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed. (2021). Excellent for Euclidean functional integrals, renormalization, RG, and the bridge between QFT and critical phenomena.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory* (1995). A standard route toward perturbative QFT and the Standard Model.
- Claude Itzykson and Jean-Bernard Zuber, *Quantum Field Theory* (1980). Dense, old-school, and still useful as a reference.

### How to read multiple sources without going mildly feral

Different books use different metric signatures, Fourier phases, gamma matrices, and normalizations. Do not memorize contradictions. Translate them. Start from [Conventions and Normalizations](/foundations/conventions-and-normalizations/), rewrite the formula in components if needed, and only then compare.

## Where to go next

After this volume, the natural destinations are:

| You want to learn... | Go next to... |
|---|---|
| real scattering calculations | [Perturbative QFT and Scattering](/perturbative-qft/) |
| divergences, counterterms, running, and universality | [Renormalization, RG, and EFT](/renormalization-rg-eft/) |
| full Yang–Mills, QCD, and electroweak theory | [Gauge Theories and the Standard Model](/gauge-theories-standard-model/) |
| anomalies, topological terms, generalized symmetries, and defects | [Symmetry, Anomalies, and Topology](/symmetry-anomalies-topology/) |
| mass gaps, instantons, lattice QFT, and confinement | [Nonperturbative QFT](/nonperturbative-qft/) |
| conformal symmetry, CFT data, and crossing | [CFT and Bootstrap](/cft-bootstrap/) |
| theorem-first formulations and mathematical status | [Mathematical and Rigorous QFT](/rigorous-qft/) |

Foundations is where the language becomes stable. The rest of QFT.org is where that language gets powerful.
