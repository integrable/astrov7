---
title: "Structural Principles of QFT"
description: "Chapter overview for the structural assumptions of relativistic QFT in the Foundations of QFT volume: locality, unitarity, spectrum, clustering, reflection positivity, analyticity, sectors, and axiomatic viewpoints."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, chs. 3–6 and 10; Coleman 2019, selected lectures on locality, scattering, and spectral representations; Streater and Wightman; Haag; Glimm and Jaffe."
topics:
  - structural principles
  - locality
  - microcausality
  - unitarity
  - spectral condition
  - cluster decomposition
  - reflection positivity
  - analyticity
  - superselection sectors
canonicalTopics:
  - structural-principles-of-qft
  - locality-and-microcausality
  - unitarity
  - spectral-condition
  - cluster-decomposition
  - reflection-positivity
  - analyticity-and-causality
  - superselection-sectors
researchStatus:
  established:
    - "Locality, positive energy, unitarity, clustering, analytic structure, and positivity conditions are standard organizing principles of ordinary relativistic QFT."
  active:
    - "The precise realization of these principles in gauge theory, curved spacetime, non-Lorentzian systems, nonunitary theories, and rigorous constructions remains a rich area of research."
---

Structural Principles of QFT is the chapter in the Foundations of QFT volume where the assumptions behind the formalism are named. Earlier chapters teach fields, states, propagators, path integrals, interactions, symmetries, and gauge redundancy. This chapter asks what makes those objects part of a coherent relativistic quantum theory.

The chapter is not a theorem-first course in axiomatic QFT. It is a structural map for readers who want to know which facts are assumptions, which are consequences, and which require extra hypotheses. Locality, unitarity, positive energy, clustering, reflection positivity, analyticity, and sectors are the beams holding up much of the subject.

Read this chapter when formulas have begun to work, but you want to understand what keeps them honest.

$$
\text{relativistic QFT}
\quad\text{is constrained by}\quad
\text{locality, spectrum, positivity, and consistency}.
$$

## Prerequisites

You should know [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) for the first explicit examples of causal support. For the Hilbert-space and scattering side, review [States, Operators, and Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/) and [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/).

For symmetry-sensitive statements, know [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/) and [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/). The conventions are fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) | The spacelike commutation principle for local observables and its role in relativistic causality. |
| 2 | [Unitarity](/foundations/structural-principles/unitarity/) | Probability conservation, $S^\dagger S=1$, optical-theorem logic, and positivity constraints. |
| 3 | [Spectral Condition](/foundations/structural-principles/spectral-condition/) | The positive-energy assumption and support of energy–momentum in the forward light cone. |
| 4 | [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) | Why widely separated experiments should decorrelate in ordinary vacuum sectors. |
| 5 | [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) | The Euclidean positivity condition needed to reconstruct a Hilbert-space theory. |
| 6 | [Analyticity and Causality](/foundations/structural-principles/analyticity-and-causality/) | How causal support and positive spectrum become analytic structure in correlators and amplitudes. |
| 7 | [Superselection Sectors](/foundations/structural-principles/superselection-sectors/) | Why some states cannot be coherently superposed by local observables. |
| 8 | [Axiomatic QFT Preview](/foundations/structural-principles/axiomatic-qft-preview/) | The Wightman, Osterwalder–Schrader, Haag–Kastler, and constructive viewpoints as maps of the terrain. |

After this path, you should be able to say which structural assumptions are being used when a QFT calculation invokes locality, positive energy, unitarity, Euclidean continuation, or particle sectors.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `microcausality` | Local bosonic observables commute, and local fermionic fields anticommute, at spacelike separation. | Spin–statistics, CPT, scattering. |
| `$S^\dagger S=1$` | Time evolution and scattering preserve total probability in a Hilbert space with positive norm. | Optical theorem, cuts, partial waves. |
| `spectrum in $\overline V_+$` | Physical energy–momentum lies in the closed forward light cone. | Källén–Lehmann representations, analyticity. |
| `cluster decomposition` | Connected correlations decay when groups of insertions are widely separated in a vacuum sector. | Scattering, phases, sectors. |
| `reflection positivity` | Euclidean correlators must satisfy a positivity condition to reconstruct a Lorentzian Hilbert space. | Euclidean QFT, lattice QFT, constructive QFT. |
| `analyticity from causality` | Causal support and positive spectrum imply domains of analyticity for correlators and amplitudes. | Dispersion relations, crossing, bootstrap. |
| `superselection sector` | Local observables may not connect all Hilbert-space sectors. | Gauge theory, charged sectors, phases. |
| `axiomatic frameworks` | Wightman, Osterwalder–Schrader, and Haag–Kastler viewpoints state QFT assumptions precisely. | Mathematical and Rigorous QFT. |

## Common confusions

**Structural principles are not optional philosophy.** They are the assumptions that make standard manipulations meaningful. A propagator, spectral representation, Wick rotation, or scattering amplitude often uses more structure than the formula alone displays.

**Fields are not always observables.** A charged field, a spinor field, or a gauge potential may be a useful local object without being a directly measurable local observable. Locality statements must be phrased with the right graded or gauge-invariant objects.

**Euclidean positivity is not ordinary pointwise positivity.** Reflection positivity is a condition on Euclidean correlation functions after reflection through a time slice. It is the hidden Hilbert-space positivity check behind many Euclidean path-integral constructions.

**Clustering is not the same as locality.** Locality constrains spacelike separated operations. Clustering is a statement about correlations at large separations in a chosen state or sector.

**Axioms are not meant to replace physics.** Axiomatic frameworks make assumptions explicit and reveal obstructions. They are maps of what has to be true, not substitutes for model construction or physical interpretation.

## Boundaries

This chapter does:

- identify the structural assumptions behind ordinary relativistic QFT;
- explain how locality, unitarity, spectrum, clustering, reflection positivity, analyticity, and sectors fit together;
- preview theorem-level formulations without turning Foundations into a rigorous-QFT volume.

This chapter does not try to do:

- full Wightman, Osterwalder–Schrader, Haag–Kastler, or constructive QFT;
- detailed dispersion relations, amplitudes, or bootstrap methods;
- nonperturbative proofs of confinement, mass gaps, or continuum limits;
- full gauge-theory, curved-spacetime, or algebraic-QFT treatment.

Those topics belong in Mathematical and Rigorous QFT, Perturbative QFT and Scattering, Nonperturbative QFT, CFT and Bootstrap, Gauge Theories and the Standard Model, and Spacetime, Gravity, and Holography.

## Where to go next

For the last Foundations chapter, go to [Foundational Models](/foundations/foundational-models/), where the abstract machinery is packaged into compact model cards. For calculation-oriented structure, continue later to Perturbative QFT and Scattering. For theorem-level foundations, continue to Mathematical and Rigorous QFT.

When reading advanced material, return to this chapter whenever a result depends on locality, positivity, a spectrum condition, Euclidean reconstruction, or sector structure. These assumptions often decide where a theorem applies and where a familiar formula can fail.

## References

### Standard first pass

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the structural construction of relativistic quantum fields, particle representations, locality, and analyticity.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for physical discussions of locality, spectral representations, scattering, and renormalized propagators.
- Schwartz, *Quantum Field Theory and the Standard Model*, for unitarity, spectral decompositions, locality, and their use in particle-physics calculations.

### Deeper references

- Streater and Wightman, *PCT, Spin and Statistics, and All That*, for the Wightman-axiom viewpoint.
- Haag, *Local Quantum Physics*, for the algebraic viewpoint and local nets of observables.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive and Euclidean methods.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
