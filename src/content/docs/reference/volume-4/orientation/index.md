---
title: "Orientation"
description: "Chapter overview for conventions, reading strategy, scope boundaries, and maintenance rules in the Gauge Theories and the Standard Model volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, spin-one and Standard Model chapters; Weinberg Vol. II, non-Abelian gauge theory and Standard Model chapters; Schwartz 2014, QED through Standard Model chapters."
topics:
  - gauge-theory orientation
  - conventions
  - reading path
  - Standard Model architecture
canonicalTopics:
  - gauge-theory-orientation
  - gauge-theory-conventions
  - standard-model-learning-path
researchStatus:
  established:
    - "A coherent treatment of gauge theories depends on explicit conventions for covariant derivatives, generators, field strengths, hypercharge, and gauge fixing."
  active:
    - "Modern boundary symmetries, generalized symmetries, global forms of gauge groups, and SMEFT interpretations are active organizing tools and are handed off to later chapters."
---

Orientation is the chapter in the Gauge Theories and the Standard Model volume where the reader fixes the map before entering the machinery. Gauge theory is convention-sensitive, conceptually subtle, and physically broad; this chapter keeps those three facts from obscuring one another.

The chapter exists to answer a practical question: before learning QED, Yang–Mills theory, QCD, electroweak theory, the Higgs sector, flavor, and anomaly cancellation, what should be kept fixed? The answer is a small set of signs, normalizations, boundary conventions, and reading choices.

This is not the physics climax of the volume. It is the compass, ruler, and sign-checking notebook for the physics chapters that follow. The main sequence begins in Gauge Principle and Classical Gauge Theory.

$$
\text{reliable gauge theory}
=
\text{clear conventions}
+
\text{clear redundancy}
+
\text{clear physical observables}.
$$

## Prerequisites

You should know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/), especially the mostly-minus metric, Fourier phase, propagator conventions, and Dirac notation. You should also be comfortable with classical actions, Noether currents, complex fields, and the idea that a field variable can contain more components than physical degrees of freedom.

Readers entering from particle physics should keep the sign of the electric charge and the hypercharge convention nearby. Readers entering from geometry should remember that this volume starts with local QFT conventions before later pages discuss global forms, bundles, line operators, and boundary symmetries.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/) | The sign of $D_\mu$, the normalization of generators, the definition of $F_{\mu\nu}$, and the hypercharge convention $Q=T^3+Y$. |
| 2 | [Gauge Principle and Classical Gauge Theory](/gauge-theories-standard-model/gauge-principle/) | The conceptual doorway into gauge redundancy, covariant derivatives, curvature, matter representations, and gauge-invariant observables. |
| 3 | [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) | The first serious distinction: gauge transformations are usually redundancy, not ordinary physical symmetries. |

After this path, you should be able to read later pages without wondering which sign convention, charge normalization, or conceptual meaning of “gauge symmetry” is being used.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $D_\mu=\partial_\mu+igA_\mu^aT^a$ | Default non-Abelian matter covariant derivative. | Field strengths, vertices, Wilson lines, Standard Model covariant derivatives. |
| $[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a$ | Defines the sign of the non-Abelian curvature in this volume. | Yang–Mills action, gauge-boson self-interactions, calculation library. |
| $Q=T^3+Y$ | Hypercharge convention used for electroweak theory. | Fermion tables, Higgs doublet, anomaly cancellation, electroweak mixing. |
| Gauge redundancy | A local gauge transformation usually changes the representative, not the physical configuration. | Gauge fixing, BRST, Ward identities, physical-state conditions. |
| Gauge-invariant observables | Physical local or extended quantities must be well defined on gauge-equivalence classes. | Wilson loops, confinement diagnostics, Standard Model currents. |
| Symbolic Standard Model data | Field content, representations, charges, and Lagrangian terms are stable reference data. | Standard Model architecture and reference tables. |
| Date-sensitive numerical data | Precision values, limits, and fits require current sources and explicit dates. | Precision Standard Model and SMEFT pages. |

## Common confusions

**Conventions are not physics, but they are not optional.** Changing the sign in $D_\mu$ does not change a measurable prediction. Mixing two sign conventions inside one derivation does.

**The Standard Model is not just a particle table.** A particle table records excitations and measured properties. This volume treats the Standard Model as a gauge quantum field theory: representations, interactions, symmetry breaking, anomaly cancellation, renormalization, and observable limits.

**Gauge theory is not the same topic as Lie theory.** Lie groups, representations, bundles, and characteristic classes are essential background. They are imported here only as needed to understand physical gauge theories; the general mathematical technology belongs in the Mathematical Toolkit volume.

**SMEFT is not a replacement for the Standard Model chapter.** SMEFT describes controlled higher-dimensional deformations of the Standard Model consistent with its symmetries. The Standard Model itself remains the renormalizable gauge theory that supplies the field content, symmetry breaking pattern, and low-energy parameters.

## Boundaries

This chapter does:

- fix the volume-level gauge conventions;
- explain how to enter the gauge-theory sequence;
- separate stable symbolic content from date-sensitive numerical data;
- point out where later chapters handle boundary symmetries, global forms, and SMEFT.

This chapter does not try to do:

- derive the gauge principle or the Yang–Mills action;
- quantize gauge theories or introduce ghosts and BRST;
- teach QCD, electroweak theory, Higgs physics, flavor, or anomaly cancellation;
- provide current particle-data tables or global-fit summaries.

Those topics belong to the physics chapters of this volume, with mathematical background supplied by the Mathematical Toolkit, perturbative methods by Perturbative QFT and Scattering, and scale-dependent interpretation by Renormalization, RG, and EFT.

## Where to go next

For the first conceptual step, continue to [Gauge Principle and Classical Gauge Theory](/gauge-theories-standard-model/gauge-principle/). For sign checks, keep [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/) open while reading any page with covariant derivatives or electroweak charges.

After the gauge-principle chapter, the natural route is QED, then Yang–Mills, then gauge quantization and renormalization. Readers mainly interested in the Standard Model should still take that route; it prevents the electroweak and anomaly pages from becoming a memorization exercise.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for a step-by-step path through photons, QED, non-Abelian gauge theory, anomalies, spontaneous gauge-symmetry breaking, and the Standard Model.
- Schwartz, *Quantum Field Theory and the Standard Model*, for a calculation-oriented route from QED to Yang–Mills theory, weak interactions, anomalies, and precision tests.
- Zee, *Quantum Field Theory in a Nutshell*, for physics-first explanations of gauge invariance, non-Abelian gauge theory, the Anderson–Higgs mechanism, QCD, and electroweak unification.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a systematic treatment of non-Abelian gauge theories, BRST, renormalization, spontaneous symmetry breaking, the Standard Model, and anomalies.
- Coleman, *Aspects of Symmetry*, especially “Secret Symmetry,” for an unusually clear conceptual account of spontaneous symmetry breaking, gauge fields, the Higgs phenomenon, and asymptotic freedom.

## Version history

- **2026-06-17:** Initial chapter overview for the improved gauge-theory volume plan.
