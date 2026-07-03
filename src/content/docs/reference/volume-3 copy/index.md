---
title: "Symmetry, Anomalies, and Topology"
description: "Volume overview for symmetry structures, anomalies, topological terms, defects, and generalized symmetries in quantum field theory."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman, Srednicki, Weinberg, Zee, Polyakov; Gaiotto–Kapustin–Seiberg–Willett; modern reviews on generalized symmetry."
topics:
  - symmetry
  - anomalies
  - topology
  - generalized symmetries
  - topological defects
canonicalTopics:
  - symmetry-anomalies-topology
  - global-symmetry
  - anomalies
  - generalized-symmetry
researchStatus:
  established:
    - "Ordinary global symmetries, Noether currents, Ward identities, spontaneous symmetry breaking, gauge redundancy, and perturbative anomalies are standard graduate QFT material."
    - "Higher-form symmetries are now a standard structural language for extended operators, background fields, gauging, and anomaly constraints."
  active:
    - "Non-invertible symmetry, categorical symmetry, symmetry TFT, and higher-categorical formulations are active research areas; this volume separates their stable core from frontier claims."
---

Symmetry, Anomalies, and Topology is the volume where the symmetry language of QFT is treated as structure rather than ornament. A symmetry is not merely a transformation that leaves a Lagrangian invariant. It can organize Hilbert spaces, constrain correlation functions, act on local or extended operators, survive without a Lagrangian, fail to be gauged, or appear only after passing to a dual description.

The central message is compact:

$$
\text{symmetry is structure},\qquad
\text{anomaly is obstruction},\qquad
\text{topology records global data}.
$$

The volume starts with ordinary global symmetries, Noether currents, charges, and Ward identities. It then moves through spontaneous symmetry breaking, gauge redundancy, discrete and spacetime symmetries, anomalies, topological terms, solitons, defects, higher-form symmetries, non-invertible symmetries, symmetry TFT, and topological QFT.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A flow diagram from symmetry data to Ward identities, background fields, anomalies, topology, generalized symmetries, and RG constraints.](/figures/symmetry-anomalies-topology/symmetry-volume-map.svg)

<figcaption>

A recurring test for symmetry data: couple to background fields, ask whether gauging is possible, and track the topological operators, defects, and anomaly data that survive along RG flow.

</figcaption>
</figure>

## Prerequisites

You should know the site-wide metric, Fourier, and spinor conventions, especially the mostly-minus convention and the $e^{-ip\cdot x}$ plane-wave phase. For this volume, first read [Conventions and Notation](/symmetry-anomalies-topology/conventions/), which fixes the additional sign choices for symmetry transformations, currents, background fields, anomaly descent, and topological terms.

The main physics prerequisites are classical actions, canonical commutators, path-integral generating functionals, Lie groups and representations, and basic gauge fields. Differential forms, homotopy groups, characteristic classes, and spin structures are helpful but not assumed at the beginning; the relevant facts are introduced when they become load-bearing.

## Reading path

A good first pass is not chronological in research history. It is conceptual: start with symmetries acting on operators, then learn how currents and backgrounds diagnose them, then study the ways topology and quantization obstruct naive symmetry arguments.

| Step | Chapter | What it gives you |
|---:|---|---|
| 1 | Conventions and Notation | The sign, generator, background-field, orientation, and topological-term conventions used throughout the volume. |
| 2 | Ordinary Global Symmetries | The operator meaning of symmetry: actions on fields, states, local operators, and selection rules. |
| 3 | Noether Currents and Ward Identities | The bridge between continuous transformations, conserved currents, charges, contact terms, and correlator identities. |
| 4 | Background Fields and Gauging | The diagnostic technology behind modern anomaly theory: couple to classical sources, then ask whether summing over them is consistent. |
| 5 | Spontaneous Symmetry Breaking | Order parameters, degenerate vacua, Goldstone modes, and the distinction between exact, explicit, and spontaneous breaking. |
| 6 | Gauge Redundancy and BRST | Why gauge symmetry is not an ordinary global symmetry, and how gauge fixing, ghosts, and BRST cohomology preserve physics. |
| 7 | Discrete, Spacetime, and Antiunitary Symmetries | Parity, time reversal, charge conjugation, CPT, fermion parity, and the extra subtleties of antiunitary and spacetime symmetries. |
| 8 | Anomalies | The mechanisms by which a classical symmetry can fail quantum mechanically: regulators, measures, triangle diagrams, and descent. |
| 9 | ’t Hooft Anomalies and Anomaly Matching | Anomalies of global symmetries as RG-invariant obstructions to gauging and as constraints on phases. |
| 10 | Topological Terms | Terms that look locally invisible but change the quantum theory: theta terms, Wess–Zumino terms, Chern–Simons terms, and BF terms. |
| 11 | Topological Sectors and Solitonic Charges | Homotopy classes, winding, instanton number, monopoles, vortices, domain walls, and conserved topological charges. |
| 12 | Defects and Extended Operators | Wilson lines, ’t Hooft lines, surface operators, disorder operators, twist operators, interfaces, and defect fusion. |
| 13 | Higher-Form and Generalized Symmetries | Symmetries whose charged objects are extended operators rather than local fields. |
| 14 | Non-Invertible and Categorical Symmetries | Symmetry defects that fuse non-invertibly, including duality defects and categorical symmetry in low-dimensional examples. |
| 15 | Symmetry TFT and Anomaly Inflow | The bulk-boundary organization of symmetry and anomaly data. |
| 16 | Topological Quantum Field Theory | Metric-independent QFTs and their role as phases, anomaly theories, and effective descriptions of topological sectors. |
| 17 | Low-Dimensional Symmetry Technology | Bosonization, fermionization, orbifolds, current algebras, modular constraints, and two-dimensional anomaly examples. |
| 18 | Symmetry in Phases of Matter | Landau symmetry breaking, SPT phases, SET phases, anomaly-boundary correspondence, and higher-form symmetry in matter systems. |
| 19 | Model Calculation Library | Worked calculations that make the abstract machinery reproducible. |

After this path, a reader should be able to recognize the symmetry data of a QFT, determine what operators are charged, introduce appropriate background fields, diagnose possible anomalies, and understand what topology contributes beyond local equations of motion.

## Landmarks

**Symmetry acts on observables.** In a Lagrangian presentation, a symmetry may be introduced as a transformation of fields. In the quantum theory, the invariant statement is its action on observables and states. This matters because dual descriptions may use different fields while describing the same symmetry.

**Currents are useful but not the whole story.** Continuous ordinary symmetries often have Noether currents, but discrete symmetries do not. Higher-form symmetries have generalized currents. Non-invertible symmetries may be better described by topological defects than by conserved charges.

**Background fields are the honesty test.** Coupling a global symmetry to a classical background field asks whether the symmetry can be probed consistently. Gauging asks a stronger question: can that background be made dynamical or summed over? Anomalies are often most cleanly defined as failures of this procedure.

**Gauge symmetry is redundancy.** A gauge transformation relates two descriptions of the same physical configuration. A global symmetry relates distinct physical states or operators. Many confusions in QFT come from mixing these two ideas.

**Topology can change quantum physics without changing local equations.** Theta terms, Chern–Simons terms, Wess–Zumino terms, spin structures, line operators, instanton sectors, and large gauge transformations all teach the same lesson: local differential equations do not see everything.

**Modern symmetry is defect-theoretic.** The old slogan “symmetry means a group acting on fields” is too narrow. In modern QFT, symmetry may be encoded by deformable topological operators, and those operators may act on local operators, lines, surfaces, boundaries, and other defects.

## Boundaries

This volume is the canonical home of symmetry structures and their obstructions. It does not try to become every subject in which symmetry appears.

| Topic | Canonical home here | Main handoff elsewhere |
|---|---|---|
| Lie groups and representation theory | How symmetry groups act in QFT examples | Mathematical Toolkit |
| Basic Noether theorem | Symmetry interpretation, currents, charges, ambiguities, Ward identities | Foundations of QFT for the first derivation |
| Yang–Mills dynamics | Gauge redundancy, global form, anomalies, one-form symmetry, line operators | Gauge Theories and the Standard Model |
| Full confinement story | Center symmetry and Wilson/’t Hooft-line diagnostics | Nonperturbative QFT |
| Conformal symmetry | Ward identities and anomaly interfaces | CFT and Bootstrap |
| Topological phases of matter | Symmetry/anomaly/topological-response structure | Matter, Statistical Physics, and Quantum Information |
| Rigorous categorical formulation | Conceptual physics and examples | Mathematical and Rigorous QFT |

## Common confusions

**“Gauge symmetry” does not mean a very important global symmetry.** Gauge transformations are redundancies in description. The physical symmetry content of a gauge theory includes gauge-invariant global symmetries, large transformations not connected to the identity, center symmetries, higher-form symmetries, and sometimes boundary symmetries.

**A conserved current is not unique.** Currents can be shifted by improvement terms without changing the charge under suitable boundary conditions. In anomaly questions, contact terms and background-field counterterms can make this ambiguity physically visible.

**An anomaly is not merely “a broken symmetry.”** An explicitly broken symmetry is absent because the action was not invariant. An anomalous symmetry is more subtle: a classical symmetry cannot be implemented together with locality, regularization, gauge invariance, or background-field consistency in the quantum theory.

**Topological does not mean dynamically irrelevant.** A term may be locally a total derivative and still affect tunneling, line operators, boundary states, response coefficients, and the spectrum on nontrivial manifolds.

**The global form of a symmetry matters.** The Lie algebra does not determine the spectrum of allowed line operators, bundles, large gauge transformations, or background fields. Distinguishing $SU(N)$ from $PSU(N)$ is not pedantry; it changes the theory.

## How to use this volume

Linear readers should follow the reading path above. Returning readers should use the volume as a diagnostic atlas: identify the symmetry, determine the charged operators, ask what background field couples to it, test whether gauging is possible, and then look for anomalies, topological terms, or defects.

For calculations, use the Model Calculation Library as the repair shop. The core chapters explain what the structures mean; the library shows how the signs, factors of $2\pi$, current normalizations, and contact terms work in explicit theories.

For research topics, pay attention to status labels. Ordinary Noether symmetry, perturbative gauge anomalies, and Goldstone’s theorem are textbook-standard. Higher-form symmetry is now standard modern language. Non-invertible symmetry, categorical symmetry, and symmetry TFT are active, fast-moving areas; pages on those topics will distinguish stable definitions from conjectural or example-driven claims.

## References

### Standard first pass

- Sidney Coleman, *Aspects of Symmetry*. Especially useful for symmetry breaking, current algebra, instantons, solitons, and large-$N$ methods.
- Mark Srednicki, *Quantum Field Theory*. Useful for continuous symmetries, discrete symmetries, BRST symmetry, anomalies, instantons, and theta vacua.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for Ward identities, gauge symmetry, spontaneous symmetry breaking, and anomalies in Standard Model language.
- A. Zee, *Quantum Field Theory in a Nutshell*. Useful for physical intuition, chiral anomalies, monopoles, Chern–Simons theory, and topological field theory.

### Deeper and modern references

- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Useful for symmetry in quantum theory, gauge theory, BRST, anomalies, and effective actions.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for global and local symmetry, instantons, topology of gauge fields, loop operators, strings, and statistical-field-theory viewpoints.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” The standard entry point for higher-form symmetries in modern QFT.
- Clay Córdova, Thomas T. Dumitrescu, Kenneth Intriligator, and related modern lectures and reviews on generalized symmetry, anomaly constraints, and topological operators.
- Shu-Heng Shao and Sakura Schafer-Nameki lecture notes on non-invertible and generalized symmetries. Useful for the research-facing chapters.

## Version history

- **2026-06-16:** Initial polished volume overview with the added Background Fields and Gauging chapter and the renamed Gauge Redundancy and BRST chapter.
