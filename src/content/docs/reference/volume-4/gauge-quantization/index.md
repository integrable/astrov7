---
title: "Quantization of Gauge Theories"
description: "Chapter overview for gauge fixing, the Faddeev–Popov method, ghosts, BRST symmetry, physical states, covariant gauges, and background-field gauge."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.4–15.7; Coleman lectures on the Faddeev–Popov prescription; Schwartz Chs. 25–26; Zee Part VII.1."
topics:
  - gauge quantization
  - Faddeev–Popov method
  - ghosts
  - BRST symmetry
  - covariant gauges
  - physical state space
  - background-field gauge
canonicalTopics:
  - gauge-quantization
  - faddeev-popov-method
  - ghost-fields
  - brst-symmetry
  - covariant-gauge
  - physical-states-in-gauge-theory
  - background-field-gauge
researchStatus:
  established:
    - "Perturbative quantization of Yang–Mills theory by gauge fixing, Faddeev–Popov determinants, ghosts, and BRST symmetry is standard and underlies practical calculations in QED, QCD, and the electroweak theory."
  active:
    - "Global gauge fixing, Gribov copies, boundary charges, nonperturbative BRST questions, and gauge theory on general manifolds remain subtle and connect to later nonperturbative and symmetry chapters."
---

Quantization of Gauge Theories is the chapter where gauge redundancy stops being a philosophical warning and becomes a calculational constraint. The gauge potential is not an ordinary collection of fields; it contains directions in field space that label the same physical configuration. A quantum path integral or canonical Hilbert space that treats those directions as independent will overcount states and misidentify unphysical modes as particles.

The chapter exists to explain how perturbative gauge theory is made into a workable quantum field theory. The Faddeev–Popov construction divides out gauge orbits in the path integral, ghost fields represent the resulting determinant, and BRST symmetry records the leftover exact structure that replaces manifest gauge invariance after gauge fixing.

Read this chapter after Yang–Mills theory and before gauge-theory renormalization. Without the tools here, the gluon propagator, the Yang–Mills beta function, unitarity of covariant gauges, and the Standard Model’s perturbative rules look like a bag of magic tricks with suspicious minus signs. With them, the tricks become one mechanism.

$$
\text{quantized gauge theory}
=
\frac{\text{field configurations}}{\text{gauge redundancy}}
\quad\text{implemented perturbatively by}\quad
\text{gauge fixing}+\text{ghosts}+\text{BRST}.
$$

## Prerequisites

You should know [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
\psi\mapsto U^{-1}\psi,
$$

and the Yang–Mills chapter through [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/). The most important prerequisites are the gauge transformation law

$$
A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
$$

the curvature definition

$$
[D_\mu,D_\nu]=igF_{\mu\nu},
$$

and the fact that the Yang–Mills action is invariant under local changes of internal frame.

It is also helpful to have read the QED pages on [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/) and [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/). Those pages show the Abelian version of the story, where the Faddeev–Popov determinant is field-independent and ghosts decouple. The non-Abelian chapter explains why that happy accident fails.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) | The path-integral overcounting problem, the gauge-slice identity, the Faddeev–Popov determinant, and covariant gauges for Yang–Mills theory. |
| 2 | [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) | How the determinant becomes anticommuting scalar ghost fields, and how the complete gauge-fixed Yang–Mills action is organized. |
| 3 | [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/) | The nilpotent symmetry that survives gauge fixing and packages gauge independence, ghosts, and physical observables. |
| 4 | [Physical States and Unitarity](/gauge-theories-standard-model/gauge-quantization/physical-states-and-unitarity/) | Why covariant gauges can contain negative-norm or unphysical modes without ruining the unitarity of physical amplitudes. |
| 5 | [Covariant Gauges](/gauge-theories-standard-model/gauge-quantization/covariant-gauges/) | The role of the gauge parameter $\xi$, Landau and Feynman gauges, and gauge-parameter checks in calculations. |
| 6 | [Background-Field Gauge](/gauge-theories-standard-model/gauge-quantization/background-field-gauge/) | A gauge-fixing method that keeps background gauge covariance manifest and streamlines beta-function calculations. |

After this path, you should be able to write a gauge-fixed Yang–Mills path integral, explain why non-Abelian ghosts couple to gauge fields, state the BRST transformations, describe the physical state space as BRST cohomology, and distinguish physical gauge invariance from gauge-dependent intermediate expressions.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| Gauge orbit | The set of field configurations related by gauge transformations. | The path integral must count each orbit once, not every representative. |
| Gauge condition $G^a(A)=0$ | A choice of local slice through field space. | Makes the quadratic gauge-field operator invertible. |
| Faddeev–Popov determinant | The Jacobian for converting integration along gauge orbits into integration over the gauge condition. | Produces ghost fields in non-Abelian perturbation theory. |
| Ghost fields $c^a,\bar c^a$ | Anticommuting Lorentz scalars in the adjoint representation. | Cancel unphysical gauge polarizations and enter loop diagrams. |
| Gauge-fixed action | The Yang–Mills action plus gauge-fixing and ghost terms. | Supplies propagators and vertices for perturbation theory. |
| BRST differential $s$ | A nilpotent operation, $s^2=0$, combining infinitesimal gauge transformations with ghosts. | Defines physical observables through cohomology and controls Slavnov–Taylor identities. |
| Gauge parameter $\xi$ | A parameter labeling covariant gauges, not a physical coupling. | Physical observables must be independent of $\xi$. |
| Gribov copies | Multiple intersections of a gauge orbit with a gauge condition. | Warns that perturbative gauge fixing is local in field space, not a global theorem. |

## Common confusions

**Gauge fixing is not symmetry breaking.** Adding a gauge-fixing term breaks manifest gauge redundancy in the formula for the action, but it does not pick a physical vacuum that violates a real global symmetry. Gauge-related configurations were never distinct physical states.

**Ghosts are not physical particles.** Faddeev–Popov ghosts are anticommuting Lorentz scalars introduced to represent a determinant. They appear on internal lines in covariant non-Abelian calculations, but they are not asymptotic states in the physical Hilbert space.

**The ghost minus sign is not optional bookkeeping.** Ghost loops contribute with signs required by the gauge-orbit Jacobian. Dropping them destroys Ward/Slavnov–Taylor identities, spoils unitarity in covariant gauges, and gives wrong beta functions.

**The Abelian case is dangerously simple.** In QED with Lorenz gauge, the Faddeev–Popov determinant is independent of $A_\mu$, so ghosts decouple. In Yang–Mills theory the determinant depends on $A_\mu$, so ghosts interact with gauge bosons.

**Gauge-fixed Green functions are usually gauge dependent.** The propagator of $A_\mu$, the ghost propagator, and off-shell Green functions depend on the gauge choice. Gauge-invariant observables and properly defined physical S-matrix elements do not.

**BRST is not an extra physical symmetry of nature.** BRST is the cohomological remnant of gauge redundancy after gauge fixing. It is a powerful organizing principle, but it should not be confused with a global symmetry that rotates physical states into new physical states.

## Boundaries

This chapter does:

- explain the local perturbative quantization of Yang–Mills theory;
- derive the Faddeev–Popov determinant from gauge-orbit overcounting;
- introduce ghost fields and the gauge-fixed action;
- state and use BRST symmetry;
- explain physical-state and unitarity logic in covariant gauges;
- introduce background-field gauge as preparation for renormalization.

This chapter does not try to do:

- give a fully rigorous construction of four-dimensional Yang–Mills theory;
- solve the nonperturbative Gribov problem;
- classify global line operators or higher-form symmetries;
- compute the full one-loop Yang–Mills beta function;
- quantize every possible gauge condition or constrained Hamiltonian system;
- treat the Batalin–Vilkovisky formalism beyond brief orientation.

Those topics belong to [Renormalization of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/), Wilson Loops and Confinement, Nonperturbative QFT, Symmetry and Anomalies, and Mathematical and Rigorous QFT.

## Where to go next

On the linear path, start with [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/), then continue to [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) and [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/) before Physical States and Unitarity, Covariant Gauges, and Background-Field Gauge.

After this chapter, the next chapter is [Renormalization of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/), where gauge-fixed perturbation theory is used to prove the structure of counterterms, compute beta functions, and explain asymptotic freedom. For physical applications, continue later to QCD and Electroweak Theory. For conceptual depth, pair this chapter with the symmetry volume’s treatment of BRST cohomology and the nonperturbative volume’s treatment of Gribov copies and confinement.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§71–74, for path-integral quantization of non-Abelian gauge theory, Feynman rules, the beta function, and BRST symmetry.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Yang–Mills theory, gluon propagators, Feynman rules, ghost loops, and one-loop running.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Ch. 31 and nearby lectures, for a clear finite-dimensional route to the Faddeev–Popov prescription.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.4–15.8, for canonical constraints, the DeWitt–Faddeev–Popov method, ghosts, BRST symmetry, and generalizations.
- Zee, *Quantum Field Theory in a Nutshell*, Part VII.1, for a compact and intuitive route into quantizing Yang–Mills theory.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Chs. 21 and 26, for functional methods, BRST symmetry, and the Zinn-Justin equation.

## Version history

- **2026-06-18:** Added Background-Field Gauge and linked the chapter forward to Renormalization of Gauge Theories.
- **2026-06-18:** Updated the reading path after adding Physical States and Unitarity and Covariant Gauges.
- **2026-06-18:** Updated the reading path after adding Ghosts and Gauge-Fixed Action and BRST Symmetry in Gauge Theory.
- **2026-06-17:** Initial chapter overview for the improved Quantization of Gauge Theories chapter.
