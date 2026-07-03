---
title: "Model Calculation Library"
description: "Chapter overview for reusable gauge-theory and Standard Model derivations, checks, and calculation templates."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§57–78 and §§81–91; Schwartz Chs. 8–31; Coleman, Aspects of Symmetry; Burgess Chs. 7–9; Weinberg Vol. II Standard Model material."
topics:
  - worked calculations
  - gauge theory derivations
  - Standard Model checks
  - calculation templates
  - sign conventions
  - Feynman rules
  - anomaly cancellation
canonicalTopics:
  - gauge-theory-calculation-library
  - field-strength-commutator
  - qed-ward-identity
  - qed-vacuum-polarization
  - yang-mills-three-gluon-vertex
  - yang-mills-beta-function
  - abelian-higgs-mechanism
  - electroweak-gauge-boson-masses
  - standard-model-anomaly-cancellation
researchStatus:
  established:
    - "The calculations collected here are standard derivations and consistency checks used throughout perturbative gauge theory and the Standard Model."
  active:
    - "The same calculations become subtler in higher-loop, nonperturbative, finite-temperature, curved-spacetime, and EFT settings; those extensions are handed off to the appropriate volumes."
---

The Model Calculation Library is the workshop of the Gauge Theories and the Standard Model volume. The conceptual chapters explain what the objects mean. This chapter collects the calculations that readers will want to redo, quote, debug, or adapt.

A good calculation page should be more than a line of algebra. It should say what is being assumed, which convention is being used, what is being proved, how the result can be checked, and where people usually drop a sign. Gauge theory has a generous supply of signs to drop. Tiny minus signs in a gauge page are like ghosts: invisible until they ruin the amplitude.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Model calculation library architecture](/figures/gauge-theories-standard-model/calculation-library-architecture.svg)

<figcaption>

A calculation-library page turns conventions and assumptions into a reusable formula. The value is not only the final equation, but the intermediate checks that make the result portable.

</figcaption>
</figure>

## What this chapter is for

This chapter collects worked derivations that are repeatedly used across the volume. The emphasis is on reproducibility. A reader should be able to open a page, identify the conventions, follow the algebra, and use the result without guessing which sign convention is hiding behind the notation.

The library has three roles.

First, it provides **derivations**: for example, deriving the non-Abelian field strength from the commutator of covariant derivatives.

Second, it provides **consistency checks**: for example, verifying the Ward–Takahashi identity, the transversality of vacuum polarization, or Standard Model anomaly cancellation.

Third, it provides **calculation templates**: for example, extracting the vector-boson spectrum from a Higgs kinetic term or matching $W$ exchange onto the Fermi theory.

## Prerequisites

You should know the main definitions from the Gauge Principle, QED, Yang–Mills, Gauge Quantization, Gauge Renormalization, Electroweak, Higgs, Flavor, Standard Model, and Anomalies chapters. The library is designed so that individual pages can be used independently, but each calculation points back to the conceptual pages that explain the physics.

The default conventions are those of this volume:

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
\qquad
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a.
$$

Therefore

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-
\partial_\nu A_\mu^a
-g f^{abc}A_\mu^bA_\nu^c.
$$

Pages that use a different convention state it explicitly.

## Reading path

Read the first page immediately if you are working through the gauge-principle or Yang–Mills chapters. The later pages are best read when the corresponding conceptual chapter asks for them.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Field Strength from the Commutator](/gauge-theories-standard-model/calculation-library/field-strength-from-commutator/) | The algebra behind $[D_\mu,D_\nu]=igF_{\mu\nu}$, including the non-Abelian sign and gauge-covariance checks. |
| 2 | [QED Ward Identity](/gauge-theories-standard-model/calculation-library/qed-ward-identity/) | The momentum-space identity relating the proper vertex function and inverse fermion propagator, including $Z_1=Z_2$. |
| 3 | [QED Vacuum Polarization](/gauge-theories-standard-model/calculation-library/qed-vacuum-polarization/) | A compact one-loop derivation of transversality, the scalar vacuum-polarization function, and the QED beta-function coefficient. |
| 4 | [Yang–Mills Three-Gluon Vertex](/gauge-theories-standard-model/calculation-library/yang-mills-three-gluon-vertex/) | The expansion of $-\frac14F^a_{\mu\nu}F^{a\mu\nu}$ into the cubic gauge-boson vertex. |
| 5 | [Yang–Mills Beta Function](/gauge-theories-standard-model/calculation-library/yang-mills-beta-function/) | The one-loop structure behind asymptotic freedom, with group-theory factors separated. |
| 6 | [Abelian Higgs Mechanism](/gauge-theories-standard-model/calculation-library/abelian-higgs-mechanism/) | The degree-of-freedom reorganization, gauge-boson mass, Higgs mass, and $R_\xi$ gauge diagonalization in the simplest Higgs model. |
| 7 | [Electroweak Gauge-Boson Masses](/gauge-theories-standard-model/calculation-library/electroweak-gauge-boson-masses/) | The derivation of $m_W$, $m_Z$, the massless photon, the weak mixing angle, and the tree-level $\rho=1$ relation from $|D_\mu H|^2$. |
| 8 | CKM Parameter Counting | The field-redefinition argument giving three quark mixing angles and one CP phase. |
| 9 | Standard Model Anomaly Cancellation | The generation-by-generation anomaly ledger in all-left-handed notation. |
| 10 | Fermi Theory from W Exchange | The low-energy matching from tree-level $W$ exchange to the four-fermion Fermi interaction. |

The first seven pages are written in the current pass. The rest of the table is the intended calculation spine for this chapter.

## How to use a calculation page

Each calculation page follows the same pattern.

| Part | Purpose |
|---|---|
| Summary | State the result and the convention in a form suitable for lookup. |
| Setup | List the fields, representations, signs, normalizations, and assumptions. |
| Derivation | Do the calculation slowly enough that the dangerous steps are visible. |
| Checks | Verify gauge covariance, dimensions, symmetry, limits, or known special cases. |
| Common mistakes | Name the usual sign, factor, representation, or convention trap. |
| Exercises | Give small repair problems with solutions. |
| Related pages | Point back to the conceptual explanation and forward to later uses. |

The aim is not to hide the machinery. It is to make the machinery inspectable.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| commutator of covariant derivatives | The local curvature seen by matter fields. | Field strength, Yang–Mills dynamics, Bianchi identity. |
| Ward–Takahashi identity | The quantum expression of gauge invariance in QED. | QED renormalization, charge renormalization, vacuum polarization. |
| transversality | The statement $q_\mu\Pi^{\mu\nu}(q)=0$. | Photon self-energy, running electric charge, gauge-invariant counterterms. |
| group-theory factors | $C_A$, $C_R$, $T_R$, $d_R$. | Yang–Mills beta function, QCD running, matter representations. |
| Abelian Higgs reorganization | A massless vector plus a complex scalar becomes a massive vector plus a real scalar. | Higgs mechanism, $R_\xi$ gauges, Goldstone equivalence. |
| electroweak mass matrix | Quadratic gauge-boson terms from $|D_\mu H|^2$. | Electroweak symmetry breaking, $W$, $Z$, photon. |
| field redefinitions | Unphysical basis choices in flavor space. | CKM, PMNS, parameter counting, CP violation. |
| anomaly ledger | Sum over all left-handed Weyl fermions. | Standard Model consistency, hypercharge, global $SU(2)$ anomaly. |
| tree-level matching | Expand a heavy propagator at low momentum. | Fermi theory, SMEFT, decoupling. |

## Common confusions

**A calculation-library page is not the canonical conceptual page.** For example, the commutator derivation tells you how $F_{\mu\nu}$ appears algebraically. The Gauge Fields as Connections page explains why that object is curvature.

**A formula without its convention is only half a formula.** In this volume the sign of the non-Abelian term in $F_{\mu\nu}^a$ follows from $D_\mu=\partial_\mu+igA_\mu^aT^a$. If you use $D_\mu=\partial_\mu-igA_\mu^aT^a$, several signs move.

**A check is part of the calculation.** Gauge covariance, Abelian limits, Ward identities, zero determinants, and symmetry under index exchange are not decorative. They are the best debugging tools we have.

**A Standard Model calculation almost always requires multiplicities.** Color factors, weak-doublet components, generations, chirality, and conjugate representations all matter. Many wrong anomaly calculations are really wrong bookkeeping calculations.

## Boundaries

This chapter does:

- collect reusable calculations from gauge theory and the Standard Model;
- make sign and normalization choices explicit;
- give compact derivations with checks and exercises;
- cross-link each calculation to the conceptual pages where it is used;
- serve as a repair shop for common algebraic mistakes.

This chapter does not try to:

- replace the full conceptual chapters;
- provide a complete perturbative-scattering course;
- cover every Standard Model process or collider observable;
- maintain date-sensitive numerical parameter tables;
- become a package manual for symbolic computation tools;
- prove deep structural theorems in mathematical gauge theory.

## Where to go next

Start with [Field Strength from the Commutator](/gauge-theories-standard-model/calculation-library/field-strength-from-commutator/). It is the canonical quick derivation behind the curvature formula used throughout the gauge-theory chapters. Then read [QED Ward Identity](/gauge-theories-standard-model/calculation-library/qed-ward-identity/) and [QED Vacuum Polarization](/gauge-theories-standard-model/calculation-library/qed-vacuum-polarization/) if you are working through QED renormalization or the running electric charge. If you are working through Yang–Mills or QCD, read [Yang–Mills Three-Gluon Vertex](/gauge-theories-standard-model/calculation-library/yang-mills-three-gluon-vertex/) and [Yang–Mills Beta Function](/gauge-theories-standard-model/calculation-library/yang-mills-beta-function/) next.

For the electroweak and Higgs chapters, read [Abelian Higgs Mechanism](/gauge-theories-standard-model/calculation-library/abelian-higgs-mechanism/) before [Electroweak Gauge-Boson Masses](/gauge-theories-standard-model/calculation-library/electroweak-gauge-boson-masses/). The first page shows the mechanism with one gauge field; the second shows the Standard Model mass matrix.

After that, return to the page that sent you here. The library is meant to be entered repeatedly from nearby pages, not necessarily read straight through in one heroic sitting.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the spin-one chapters from QED through Yang–Mills, BRST, anomalies, background-field gauge, QCD, spontaneous gauge-symmetry breaking, and the Standard Model.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the QED, Yang–Mills, renormalization, weak-interaction, anomaly, and precision-test chapters.
- Coleman, *Aspects of Symmetry*, especially the lectures on symmetry, renormalization, spontaneous symmetry breaking, gauge fields, and the Higgs phenomenon.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a systematic field-theoretic treatment of gauge theories and the Standard Model.
- Burgess, *Introduction to Effective Field Theory*, for matching, power counting, Fermi theory, SMEFT, and Standard Model EFT logic.
- Geometry references such as Nakahara and Frankel for the connection/curvature viewpoint behind the commutator calculation.

## Version history

- **2026-06-19:** Added Abelian Higgs Mechanism and Electroweak Gauge-Boson Masses calculation pages, including the degree-of-freedom count, $R_\xi$ gauge check, neutral mass matrix, photon–$Z$ rotation, and tree-level $\rho=1$ relation.
- **2026-06-19:** Added Yang–Mills Three-Gluon Vertex and Yang–Mills Beta Function calculation pages, including the cubic-vertex sign checks and the one-loop $b_0$ ledger.
- **2026-06-19:** Added QED Ward Identity and QED Vacuum Polarization calculation pages, including the $Z_1=Z_2$ check and one-loop photon self-energy.
- **2026-06-19:** Initial chapter overview and first calculation-library entry, Field Strength from the Commutator.
