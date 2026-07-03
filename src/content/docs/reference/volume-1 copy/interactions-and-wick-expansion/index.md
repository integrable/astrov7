---
title: "Interactions and Wick Expansion"
description: "Chapter overview for interactions and Wick expansion in the Foundations of QFT volume: interaction picture, Dyson series, Wick theorem, Feynman diagrams, scalar interactions, connected diagrams, effective action, LSZ preview, and ultraviolet divergences."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–19; Coleman 2019, chs. 7–14, 25, and 32; Weinberg 1995, Vol. I, chs. 6, 10, and 12; Zee 2010, chs. I.7–I.9."
topics:
  - interactions
  - Wick theorem
  - Dyson series
  - Feynman diagrams
  - connected diagrams
  - effective action
  - LSZ preview
canonicalTopics:
  - interactions-and-wick-expansion
  - dyson-series
  - wick-theorem
  - feynman-diagrams
  - connected-diagrams
  - effective-action
researchStatus:
  established:
    - "The interaction picture, Dyson expansion, Wick theorem, Feynman diagrams, connected diagrams, and perturbative effective action are standard foundations of perturbative QFT."
  active:
    - "Nonperturbative dynamics, resummation, renormalization beyond previews, gauge-theory consistency, and modern amplitude methods require later volumes."
---

Interactions and Wick Expansion is the chapter in the Foundations of QFT volume where free-field machinery first becomes a calculational engine. The free theory supplies propagators and contractions; the interaction supplies vertices; the Dyson expansion tells us how to combine them.

The chapter exists because perturbative QFT is not just drawing pictures. Feynman diagrams are a compact bookkeeping language for time-ordered operator products, Gaussian functional integrals, symmetry factors, connected pieces, and eventually scattering amplitudes.

Read this chapter when you want to understand what an interaction term does before entering full scattering theory, loop renormalization, gauge-theory perturbation theory, or amplitudes.

$$
\text{interaction picture}
\quad\longrightarrow\quad
\text{Dyson series}
\quad\longrightarrow\quad
\text{Wick contractions}
\quad\longrightarrow\quad
\text{diagrams}.
$$

## Prerequisites

You should know [Correlation Functions and Propagators](/foundations/correlators-and-propagators/), especially time ordering, Feynman propagators, and connected correlators. You should also know the source-functional language from [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) and the free scalar formulas in [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/).

For operator-first reading, review [Normal Ordering](/foundations/canonical-quantization/normal-ordering/). For path-integral-first reading, review [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/) | The split between solvable free evolution and perturbative interaction evolution. |
| 2 | [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) | The time-ordered exponential and the perturbative expansion of evolution operators. |
| 3 | [Wick's Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) | The rule that reduces time-ordered free-field products to normal-ordered pieces and contractions. |
| 4 | [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) | The diagrammatic grammar for propagators, vertices, symmetry factors, and momentum flow. |
| 5 | [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) | Concrete examples such as $\phi^3$ and $\phi^4$ interactions and their first diagrammatic rules. |
| 6 | [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) | Why logarithms of generating functionals isolate connected contributions. |
| 7 | [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) | The Legendre transform from connected correlators to one-particle-irreducible vertices. |
| 8 | [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) | The first bridge from time-ordered correlators to scattering amplitudes. |
| 9 | [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) | The first encounter with short-distance divergences and local counterterm logic. |

After this path, you should be able to explain how a local interaction term produces vertices, how Wick contractions produce diagrams, and why connected and one-particle-irreducible objects are separated.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$H=H_0+H_I$` | Perturbation theory separates exactly solvable free evolution from interaction effects. | Dyson series, scattering. |
| `$U_I(t,t_0)=T\exp[-i\int_{t_0}^t dt' H_I(t')]$` | The interaction-picture evolution operator is a time-ordered exponential. | Perturbative expansion, S-matrix. |
| Wick theorem | Free-field time-ordered products reduce to sums of contractions. | Feynman diagrams, Gaussian path integrals. |
| Contraction | A contraction is a free Feynman propagator inserted by Wick theorem. | Propagators on internal lines. |
| Vertex factor | A local interaction term contributes a local meeting point for fields in a diagram. | Feynman rules, amplitudes. |
| `$W[J]=-i\log Z[J]$` | The logarithm of the source functional generates connected diagrams. | Connected correlators, vacuum diagrams. |
| `$\Gamma[\phi]$` | The effective action generates one-particle-irreducible vertices. | Self-energies, renormalization, background fields. |
| UV divergence | Loop integrals can be singular at short distance, and local counterterms are the first cure. | Renormalization, EFT. |

## Common confusions

**A Feynman diagram is not literally a particle path.** In perturbative QFT, a diagram is a term in an expansion of correlators or amplitudes. Its lines are propagators and its vertices are interaction insertions, not little particles tracing worldlines in spacetime.

**Wick theorem is a theorem about free fields.** It applies because the reference theory is Gaussian or free. In interacting calculations, Wick theorem is used after expanding around the free theory.

**Connected and one-particle-irreducible are different filters.** Connected diagrams cannot be split into separate components by cutting no lines. One-particle-irreducible diagrams remain connected after cutting one internal line.

**The LSZ formula is not a diagram rule.** LSZ relates suitable time-ordered correlators to scattering amplitudes after external legs are treated correctly. This chapter previews the idea but leaves the full scattering machinery to later material.

**A divergence is not automatically a disaster.** A divergent loop integral signals sensitivity to short-distance behavior in a formal continuum calculation. Renormalization explains when and how that sensitivity can be absorbed into local parameters.

## Boundaries

This chapter does:

- introduce the interaction picture and Dyson expansion;
- derive the role of Wick contractions and Feynman diagrams;
- explain connected diagrams and the first appearance of the effective action;
- preview LSZ and ultraviolet divergences.

This chapter does not try to do:

- full cross sections, decay rates, phase space, or precision scattering;
- systematic loop integral reduction or renormalized perturbation theory;
- gauge-theory Feynman rules and BRST consistency;
- nonperturbative resummation or modern on-shell amplitude methods.

Those topics belong in the Perturbative QFT and Scattering, Renormalization, RG, and EFT, Gauge Theories and the Standard Model, and Nonperturbative QFT volumes.

## Where to go next

For the next Foundations step, go to [Symmetry and Spacetime Structure](/foundations/symmetry-and-spacetime/), where symmetries, currents, Ward identities, and structural theorems organize the same fields and correlators.

For computations with observables, continue later to the Perturbative QFT and Scattering volume. For the scale meaning of UV divergences, continue later to Renormalization, RG, and EFT.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for path-integral perturbation theory, diagrams, LSZ, loop previews, and the early renormalization arc.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for interaction-picture perturbation theory, Wick diagrams, scattering, and renormalization-motivated examples.
- Zee, *Quantum Field Theory in a Nutshell*, for a physics-first presentation of diagrams and perturbative intuition.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic relation among fields, the S-matrix, perturbation theory, and symmetries.
- Itzykson and Zuber, *Quantum Field Theory*, for a more encyclopedic treatment of perturbative diagrammatics and generating functionals.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
