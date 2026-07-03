---
title: "Correlation Functions and Propagators"
description: "Chapter overview for correlation functions and propagators in the Foundations of QFT volume: vacuum expectation values, time ordering, Wightman functions, causal commutators, Green functions, iε prescriptions, spectral representations, and connected correlators."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman 2019, chs. 3, 7, 8, 13, and 15; Srednicki 2007, §§3, 5, 8, and 13; Weinberg 1995, Vol. I, chs. 5–6 and 10; Zee 2010, Part I."
topics:
  - correlation functions
  - propagators
  - vacuum expectation values
  - Wightman functions
  - Green functions
  - spectral representations
canonicalTopics:
  - correlation-functions
  - propagators
  - wightman-functions
  - feynman-propagator
  - kallen-lehmann-representation
researchStatus:
  established:
    - "Vacuum correlators, Wightman functions, causal commutators, Feynman propagators, retarded and advanced Green functions, and Källén–Lehmann spectral representations are standard QFT material."
  active:
    - "Real-time finite-temperature correlators, analytic continuation, gauge-invariant reconstruction, and nonperturbative spectral densities require later and more specialized treatments."
---

Correlation Functions and Propagators is the chapter in the Foundations of QFT volume where fields become measurable through expectation values. A Lagrangian tells you how to write the theory; correlation functions tell you what the theory says.

The chapter exists because the word "propagator" hides several different objects. Wightman functions, causal commutators, Feynman propagators, retarded Green functions, spectral densities, and connected correlators all come from operator expectation values, but they answer different physical and mathematical questions.

Read this chapter when you want to know which two-point function is being used, what its boundary prescription means, and how correlators encode particles, causality, response, and collective behavior.

$$
\langle 0|\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle
\quad\text{is the basic observable language of QFT.}
$$

## Prerequisites

You should know the qft.org [Conventions and Normalizations](/foundations/conventions-and-normalizations/), the free scalar field from [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and the canonical algebra from [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/). It also helps to have seen [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) and [Free Field Summary](/foundations/free-fields/free-field-summary/).

The chapter uses free fields as its main laboratory, but the point is not limited to free theories. Exact interacting correlators are often the best definition of the physical content of a QFT.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/) | The Hilbert-space meaning of vacuum expectation values and operator insertions. |
| 2 | [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) | The ordering operation that turns operator products into perturbative Green functions. |
| 3 | [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) | Correlators with fixed operator order and positive-energy spectral support. |
| 4 | [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) | The field commutator and the free-field realization of microcausality. |
| 5 | [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) | The time-ordered inverse used by Wick expansion and Feynman diagrams. |
| 6 | [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) | The Green functions that encode causal response to sources. |
| 7 | [iε Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) | The pole prescription that turns a formal denominator into a distribution. |
| 8 | [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) | The Källén–Lehmann relation between exact two-point functions and the spectrum. |
| 9 | [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) | The separation of genuinely connected correlations from disconnected products. |

After this path, you should be able to tell whether a correlator is time-ordered, causal, spectral, connected, or merely a formal inverse of a differential operator.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$\langle0|\mathcal O_1\cdots\mathcal O_n|0\rangle$` | A vacuum correlation function is the basic operator expectation value. | Operator products, generating functionals, spectral data. |
| `$\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle$` | The positive-frequency Wightman function records what the field creates from the vacuum. | Spectral representation, particle poles. |
| `$[\phi(x),\phi(y)]=i\Delta(x-y)$` | The Pauli–Jordan commutator tests locality and causal support. | Microcausality, retarded response. |
| `$D_F(x-y)=\langle0|T\phi(x)\phi(y)|0\rangle$` | The Feynman propagator is the time-ordered two-point function. | Wick theorem, diagrams, loop integrals. |
| `$1/(p^2-m^2+i\epsilon)$` | The infinitesimal prescription specifies how poles are bypassed. | Contours, LSZ, perturbative amplitudes. |
| `$G_R(x-y)=-\theta(x^0-y^0)\Delta(x-y)$` | The retarded Green function vanishes before the source acts. | Linear response, finite-temperature QFT. |
| `$D_F(p)=\int_0^\infty ds\,\rho(s)i/(p^2-s+i\epsilon)$` | The Källén–Lehmann form expresses exact two-point functions through spectral density. | Renormalization, physical poles, thresholds. |
| Connected correlators | Connected pieces remove products of lower correlations. | Source functionals, diagrams, effective action. |

## Common confusions

**Correlation does not mean causal influence.** A Wightman function can be nonzero at spacelike separation without violating causality. Causality is expressed by the vanishing of appropriate commutators or graded commutators outside the light cone.

**The propagator is not a single object.** In casual speech, "the propagator" often means the Feynman propagator. Retarded, advanced, Wightman, Pauli–Jordan, Euclidean, and thermal correlators use related kernels with different prescriptions and different jobs.

**A denominator is not yet a distribution.** The expression $1/(p^2-m^2)$ is ambiguous until a prescription is supplied. The $i\epsilon$ rule, retarded rule, advanced rule, and principal-value rule define different inverses of the same differential operator.

**Connected does not mean interacting.** A free Gaussian theory has connected two-point functions. What vanishes in a free Gaussian theory are connected correlators beyond two points, not every connected object.

**A pole is physical only after interpretation.** A simple pole in an exact two-point function can indicate a stable particle with the operator's quantum numbers. Gauge-dependent fields, unstable resonances, and branch cuts require more careful language.

## Boundaries

This chapter does:

- define the main vacuum two-point functions and their prescriptions;
- distinguish time-ordered propagation, causal response, spectral support, and connectedness;
- prepare the source-functional and diagrammatic language used later in Foundations.

This chapter does not try to do:

- full scattering theory or LSZ reduction;
- finite-temperature Schwinger–Keldysh formalism;
- nonperturbative reconstruction of spectra from numerical or lattice data;
- rigorous distribution theory beyond the level needed for Foundations.

Those topics belong in later volumes on perturbative scattering, matter and statistical physics, nonperturbative QFT, computational QFT, and mathematical QFT.

## Where to go next

For the next Foundations step, go to [Path Integral Formalism](/foundations/path-integral-formalism/), where source functionals generate the same correlators by differentiation. For the diagrammatic route, continue to [Interactions and Wick Expansion](/foundations/interactions-and-wick-expansion/).

For the structural meaning of locality and spectra, return later to [Structural Principles of QFT](/foundations/structural-principles/). For amplitudes and observables, this chapter hands off to the Perturbative QFT and Scattering volume.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for scalar propagators, time-ordered functions, path-integral Green functions, and the Källén–Lehmann representation.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for operator motivation, Green functions, scattering-oriented correlators, and the physical role of spectral representations.
- Zee, *Quantum Field Theory in a Nutshell*, for a compact and intuitive discussion of propagation, diagrams, and generating functions.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the representation-theoretic and structural treatment of free fields, propagators, and correlation functions.
- Streater and Wightman, *PCT, Spin and Statistics, and All That*, for the axiomatic role of Wightman functions and locality.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
