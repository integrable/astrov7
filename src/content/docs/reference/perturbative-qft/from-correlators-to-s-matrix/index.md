---
title: "From Correlators to the S-Matrix"
description: "Chapter overview for the bridge from time-ordered correlation functions to scattering amplitudes in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, LSZ, Feynman rules, and scattering; Coleman 2019, scattering and LSZ chapters; Weinberg 1995, Vol. I, scattering theory and Feynman rules; Schwartz 2014, S-matrix and LSZ chapters."
topics:
  - scattering theory
  - S-matrix
  - LSZ reduction
  - asymptotic states
  - amputated correlators
  - crossing symmetry
  - optical theorem
canonicalTopics:
  - correlators-to-s-matrix
  - asymptotic-states
  - lsz-reduction
  - connected-amputated-correlators
  - scattering-amplitudes
researchStatus:
  established:
    - "The use of asymptotic states, the S-matrix, LSZ reduction, connected amputated correlators, crossing, and unitarity relations is standard in perturbative QFT when suitable particle states exist."
  active:
    - "In massless gauge theories, confining theories, finite-volume settings, curved spacetime, and nonperturbative regimes, the existence or interpretation of asymptotic particle states requires extra care."
---

From Correlators to the S-Matrix is the chapter in the Perturbative QFT and Scattering volume where vacuum correlation functions become particle-scattering amplitudes. Foundations teaches what fields, propagators, and time ordering are; this chapter explains how those objects are converted into transition amplitudes between incoming and outgoing particle states.

The chapter exists because a time-ordered Green function is not yet an experiment. To reach scattering, one must isolate one-particle poles, remove external propagator factors, put external momenta on shell, and keep track of relativistic state normalization.

Read this chapter when you want to understand why Feynman diagrams for correlators are related to measured cross sections, but are not identical to them.

$$
\text{time-ordered correlator}
\quad\xrightarrow{\text{poles, amputation, on-shell limits}}\quad
\text{S-matrix amplitude}.
$$

## Prerequisites

You should know the qft.org [Conventions and Normalizations](/foundations/conventions-and-normalizations/), the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), and the basic meaning of the [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/). You should also be comfortable with [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) and the diagrammatic language summarized in [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/).

A reader who has not yet seen relativistic state normalization should review [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) or use this chapter together with [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/) | The incoming and outgoing particle states that make scattering theory possible. |
| 2 | [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) | The normalization of $S$, $T$, delta functions, and invariant amplitudes. |
| 3 | [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) | The pole-amputation formula that extracts amplitudes from time-ordered correlators. |
| 4 | [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) | The distinction between Green functions with external propagators and kernels with those factors removed. |
| 5 | [Connected Correlators and Scattering](/perturbative-qft/from-correlators-to-s-matrix/connected-correlators-and-scattering/) | Why scattering amplitudes use the nontrivial connected part rather than products of independent processes. |
| 6 | [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) | The residues, wavefunctions, polarization vectors, and state-normalization factors attached to external particles. |
| 7 | [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) | How related physical channels arise from analytic continuation of one amplitude. |
| 8 | [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) | The first unitarity relation between forward scattering and inclusive total probability. |

After this path, you should be able to say exactly which correlator is being used, which propagators are amputated, which momenta are on shell, and which normalization convention defines the amplitude.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `in` and `out` states | Scattering compares asymptotically free particle states in the far past and far future. | LSZ reduction, cross sections, optical theorem. |
| $S=1+iT$ | The identity part describes no scattering; $T$ carries the nontrivial transition amplitude. | Phase space, unitarity, model calculations. |
| $(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M$ | Translation invariance factors out total energy–momentum conservation and leaves the invariant amplitude. | Tree-level amplitudes, decay rates, cross sections. |
| One-particle pole | A field creates a particle through the pole of an exact two-point function. | LSZ, external-leg normalization, wavefunction renormalization. |
| Amputation | External propagator factors are removed before the on-shell amplitude is read off. | Feynman rules, loop corrections, renormalized amplitudes. |
| Connected part | The physically interesting scattering process excludes vacuum bubbles and independent spectator processes. | Connected diagrams, cluster decomposition, optical theorem. |
| Crossing | Initial particles and final antiparticles are related by analytic continuation of external momenta. | Mandelstam variables, tree amplitudes, dispersion relations. |
| Optical theorem | Unitarity relates a forward amplitude to a sum over allowed intermediate states. | Total rates, cuts, inclusive observables, unitarity methods. |

## Common confusions

**A correlator is not automatically an S-matrix element.** A time-ordered correlator may have off-shell external momenta and external propagator factors. LSZ reduction turns the appropriate pole part of the correlator into a scattering amplitude.

**Connected, amputated, and on-shell are different adjectives.** A connected correlator removes disconnected products. An amputated correlator removes external propagators. An on-shell amplitude further evaluates the external momenta at physical one-particle poles.

**Crossing is analytic continuation, not a drawing trick.** In diagrams one may visually move a leg from one side to another, but the statement depends on analyticity, momentum continuation, and the correct particle–antiparticle interpretation.

**The optical theorem is not just a rule for cutting a favorite diagram.** It is a consequence of $S$-matrix unitarity. Diagrammatic cutting rules are perturbative implementations of that statement after the relevant normalization and intermediate-state sums are specified.

## Boundaries

This chapter does:

- define the asymptotic-state, S-matrix, and T-matrix language used throughout scattering pages;
- explain the LSZ bridge between time-ordered correlators and amplitudes;
- separate connected correlators, amputated correlators, and on-shell amplitudes;
- introduce crossing and the optical theorem as structural constraints on amplitudes.

This chapter does not try to do:

- derive Wick's theorem or the full diagrammatic expansion, which belongs in [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/);
- compute detailed tree-level amplitudes, which belongs in [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/);
- turn amplitudes into differential rates and cross sections, which belongs in [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/);
- develop full Cutkosky rules, dispersion relations, or partial-wave unitarity, which belongs in [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/);
- solve the special infrared and confinement problems that complicate asymptotic particle language.

## Where to go next

For the diagrammatic machinery behind the correlators, go to [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/). For the first concrete scattering calculations, continue to [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/).

For physical observables, go next to [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/). For unitarity, cuts, branch cuts, and dispersion relations, return later through [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for LSZ reduction, Feynman rules, scattering amplitudes, and decay and cross-section normalization.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for a physically sharp route from the interaction picture to scattering, phase space, and LSZ.
- Schwartz, *Quantum Field Theory and the Standard Model*, for a modern graduate treatment of cross sections, LSZ, and the connection between amplitudes and observables.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the representation-theoretic and structural construction of scattering theory and the S-matrix.
- Streater and Wightman, *PCT, Spin and Statistics, and All That*, for axiomatic background on fields, states, and the assumptions behind particle scattering.

## Version history

- **2026-06-14:** Replaced scaffold with standardized chapter overview, reading path, landmarks, boundaries, and references.
