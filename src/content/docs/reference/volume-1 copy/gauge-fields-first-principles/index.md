---
title: "Gauge Fields: First Principles"
description: "Chapter overview for gauge fields as redundant local variables in the Foundations of QFT volume: gauge redundancy, Maxwell theory, charged matter, gauge fixing, non-Abelian fields, and BRST language."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman 2019, chs. 26–31; Srednicki 2007, §§54–58, 61, and 69–74; Weinberg 1995, Vol. I, ch. 8; Weinberg 1996, Vol. II, ch. 15."
topics:
  - gauge fields
  - gauge redundancy
  - Maxwell theory
  - charged matter
  - gauge fixing
  - non-Abelian gauge theory
  - BRST symmetry
canonicalTopics:
  - gauge-fields-first-principles
  - gauge-redundancy
  - maxwell-as-gauge-theory
  - covariant-derivative
  - faddeev-popov-gauge-fixing
  - brst-preview
researchStatus:
  established:
    - "Gauge redundancy, Maxwell theory, covariant derivatives, Faddeev–Popov gauge fixing, non-Abelian field strength, and BRST language are standard ingredients of modern QFT."
  active:
    - "Global aspects of gauge fields, generalized symmetries, anomalies, confinement, and nonperturbative gauge fixing require later volumes."
---

Gauge Fields: First Principles is the chapter in the Foundations of QFT volume where symmetry language meets redundancy. The point is not yet to build QCD or the Standard Model. The point is to understand why some field variables contain more description than physical information.

A gauge transformation is usually not a move from one physical state to another. It is a change of representative inside a redundant description. Once that distinction is clear, the standard machinery begins to look inevitable: covariant derivatives, field strengths, gauge fixing, ghosts, and BRST symmetry.

Read this chapter when the Maxwell field feels familiar as a free field, but the phrase "gauge symmetry" still sounds like a magic rule. By the end, you should know what gauge redundancy buys, what it costs, and why later gauge theory cannot be treated as many uncoupled copies of electromagnetism.

$$
\text{gauge field}
\quad=\quad
\text{local redundant variable whose curvature and couplings carry invariant content}.
$$

## Prerequisites

You should know [Maxwell Field](/foundations/free-fields/maxwell-field/), [Polarizations](/foundations/free-fields/polarizations/), and [Constraints](/foundations/classical-field-theory/constraints/). For charged matter, review [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) and [Dirac Field](/foundations/free-fields/dirac-field/).

For the symmetry side, it helps to know [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/). For the functional-integral side, skim [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/). The conventions are fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/), including the Abelian convention $D_\mu=\partial_\mu+iqA_\mu$.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) | The conceptual distinction between physical symmetry and redundant description. |
| 2 | [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) | The Abelian pattern: potential, field strength, gauge orbit, equations of motion, and current coupling. |
| 3 | [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) | Why local phase covariance forces the covariant derivative and fixes charge conventions. |
| 4 | [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) | Why the gauge-field kinetic operator is not invertible before redundant directions are controlled. |
| 5 | [Non-Abelian Preview](/foundations/gauge-fields-first-principles/non-abelian-preview/) | What changes when the connection is matrix-valued and the field strength contains self-interactions. |
| 6 | [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) | The gauge-fixed algebraic remnant of redundancy and the first appearance of ghosts. |

After this path, you should be able to explain why gauge potentials are useful but gauge-dependent, why gauge fixing is a coordinate choice on redundant field space, and why non-Abelian gauge theory has genuinely new dynamics.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$A_\mu\mapsto A_\mu+\partial_\mu\alpha$` | Abelian gauge transformations relate different potentials with the same electromagnetic field strength. | Maxwell theory, photon propagators. |
| `$F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu$` | The Abelian field strength is the local gauge-invariant curvature. | QED, scalar QED, gauge observables. |
| `$D_\mu=\partial_\mu+iqA_\mu$` | The covariant derivative makes charged matter transform locally and consistently. | Charged scalar and Dirac matter, minimal coupling. |
| `$\mathcal L_{\mathrm{gf}}=-\frac1{2\xi}(\partial_\mu A^\mu)^2$` | A covariant gauge-fixing term makes the quadratic photon operator invertible. | Gauge-fixed propagators and perturbation theory. |
| `Faddeev–Popov determinant` | Gauge fixing in the path integral introduces a Jacobian; in non-Abelian theory this becomes ghost dynamics. | Gauge-theory loops, BRST, Yang–Mills. |
| `$F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]$` | Non-Abelian curvature contains a commutator term and gives gauge-boson self-interactions. | Yang–Mills theory, QCD. |
| `$s^2=0$` | BRST symmetry packages gauge-fixed redundancy into a nilpotent differential. | Gauge fixing, ghosts, cohomological formulations. |

## Common confusions

**Gauge redundancy is not just a local version of an ordinary symmetry.** Ordinary global symmetries can act on physical states and generate conserved charges. Gauge transformations that vanish appropriately at boundaries usually relate different descriptions of the same physical situation.

**Gauge-dependent does not mean meaningless.** The potential $A_\mu$ is not itself a gauge-invariant observable, but it is the local variable that couples to charged matter and makes perturbative quantization practical. The rule is not to discard gauge-dependent variables; it is to ask which final quantities are invariant or gauge independent.

**Gauge fixing does not physically break gauge redundancy.** Gauge fixing chooses a representative or coordinate system for calculation. Physical gauge-invariant quantities must not depend on that choice, although intermediate propagators and diagrams usually do.

**Ghosts are not external particles.** Faddeev–Popov ghosts are anticommuting fields introduced by gauge fixing in the path integral. In non-Abelian perturbation theory they run in internal loops, but they are not physical asymptotic states.

**Non-Abelian theory is not many photons with labels.** The commutator in the field strength makes the gauge bosons self-interact and makes gauge fixing dynamical. This is the seed of asymptotic freedom, confinement, and the Standard Model gauge sector.

## Boundaries

This chapter does:

- introduce gauge redundancy as a first-principles idea;
- explain Maxwell theory, charged matter, and covariant derivatives;
- preview gauge fixing, Faddeev–Popov ghosts, non-Abelian curvature, and BRST language.

This chapter does not try to do:

- full Yang–Mills quantization or renormalization;
- QED precision physics, QCD, confinement, or the Standard Model;
- anomalies, generalized symmetries, large gauge transformations, or full BRST/BV formalism.

Those topics belong in Perturbative QFT and Scattering, Renormalization, RG, and EFT, Gauge Theories and the Standard Model, Symmetry, Anomalies, and Topology, Nonperturbative QFT, and Mathematical and Rigorous QFT.

## Where to go next

For the next Foundations step, go to [Structural Principles of QFT](/foundations/structural-principles/) if you want the assumptions behind locality, unitarity, spectrum, clustering, and analyticity. Go to [Foundational Models](/foundations/foundational-models/) if you want compact model cards where scalar QED and QED preview assemble the gauge-field ingredients.

For calculations, continue later to Perturbative QFT and Scattering. For the full physical theory of QED, Yang–Mills theory, QCD, electroweak theory, and the Standard Model, continue to the Gauge Theories and the Standard Model volume.

## References

### Standard first pass

- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for Maxwell theory, massive and massless vector fields, gauge fixing, and QED motivation.
- Srednicki, *Quantum Field Theory*, for Maxwell theory, photon quantization, scalar electrodynamics, spinor electrodynamics, non-Abelian gauge theory, and BRST symmetry.
- Zee, *Quantum Field Theory in a Nutshell*, for a compact physical route through gauge fields and gauge redundancy.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for massless spin-one fields, gauge invariance, Yang–Mills theory, and BRST-based quantization.
- Faddeev and Popov, "Feynman Diagrams for the Yang–Mills Field," for the original path-integral gauge-fixing determinant.
- Becchi, Rouet, Stora, and Tyutin, original papers on BRST symmetry, for the cohomological viewpoint behind gauge-fixed theories.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
