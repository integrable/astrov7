---
title: "Gauge Theories and RG"
description: "Chapter overview for gauge-theory renormalization, beta functions, Ward and Slavnov–Taylor identities, background-field methods, asymptotic freedom, and dimensional transmutation in the Renormalization, RG, and EFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman 1985, asymptotic freedom and renormalization lectures; Srednicki 2007, §§62–78; Schwartz 2014, chs. 16, 19, 23, and 26; Weinberg Vol. II, chs. 15–18; Polyakov 1987, ch. 2; Zinn-Justin 2021, gauge-theory and RG chapters."
topics:
  - gauge-theory renormalization
  - QED beta function
  - Yang–Mills beta function
  - QCD running coupling
  - Ward identities
  - Slavnov–Taylor identities
  - background-field method
canonicalTopics:
  - gauge-theory-rg
  - asymptotic-freedom
  - ward-identities
  - qcd-running-coupling
researchStatus:
  established:
    - "The perturbative renormalization of QED and Yang–Mills theory, the one-loop signs of their beta functions, Ward identities, Slavnov–Taylor identities, and the relation between asymptotic freedom and dimensional transmutation are standard parts of modern QFT."
  active:
    - "Nonperturbative confinement, mass-gap formation, chiral gauge theories beyond perturbation theory, gauge-invariant regulators for all desired theories, and precision high-order RG applications remain active topics handled in later volumes and chapters."
---

Gauge Theories and RG is the chapter in the Renormalization, RG, and EFT volume where scale dependence meets gauge redundancy. The central question is not merely "what is the beta function?" but rather: how can a theory with redundant variables be renormalized without destroying the identities that make only gauge-invariant physics observable?

The chapter explains why QED screens charge, why non-Abelian Yang–Mills theory antiscreens at short distances, why QCD generates a scale from a dimensionless coupling, and why gauge symmetry constrains counterterms much more strongly than naive power counting alone would suggest.

Read this chapter after the general RG pages if you want to understand how the abstract objects $\beta_g$, anomalous dimensions, scheme dependence, dimensional transmutation, and counterterms specialize to gauge theories.

$$
\text{gauge redundancy}
+\text{locality}
+\text{renormalization}
\quad\Longrightarrow\quad
\text{Ward/Slavnov identities and constrained RG flow}.
$$

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/), [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/), and [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/).

You should also be comfortable with perturbative gauge fixing and ghost fields from the perturbative QFT and gauge-theory volumes when those pages are available. This chapter uses gauge theory to study renormalization; it is not the first introduction to gauge redundancy itself.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/) | The simplest gauge-theory running coupling, charge screening, vacuum polarization, and the sign convention for $\beta_e$. |
| 2 | [Yang–Mills Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/yang-mills-beta-function/) | The non-Abelian one-loop result, gauge-boson antiscreening, matter screening, and the condition for asymptotic freedom. |
| 3 | [QCD Running Coupling](/renormalization-rg-eft/gauge-theories-and-rg/qcd-running-coupling/) | The practical running of $\alpha_s(Q)$, flavor thresholds, scheme conventions, and the meaning of $\Lambda_{\text{QCD}}$. |
| 4 | [Background-Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/) | A gauge-covariant way to compute effective actions and beta functions while preserving manifest background gauge invariance. |
| 5 | [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/) | Why regulators matter in gauge theory and how dimensional regularization, lattice regularization, Pauli–Villars variants, and higher-derivative ideas interact with gauge symmetry. |
| 6 | [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/) | The Abelian constraints relating vertex, field, and charge renormalization. |
| 7 | [Slavnov–Taylor Identities Preview](/renormalization-rg-eft/gauge-theories-and-rg/slavnov-taylor-identities-preview/) | The non-Abelian generalization of Ward identities and why ghosts and BRST structure are not optional bookkeeping. |
| 8 | [BRST and Renormalization Preview](/renormalization-rg-eft/gauge-theories-and-rg/brst-and-renormalization-preview/) | The cohomological language that organizes allowed counterterms and physical observables in gauge-fixed theories. |
| 9 | [Confinement Scale and Dimensional Transmutation](/renormalization-rg-eft/gauge-theories-and-rg/confinement-scale-and-dimensional-transmutation/) | How a perturbative running coupling points toward the nonperturbative scale where QCD becomes strongly coupled. |

After this path, you should be able to state the one-loop QED and Yang–Mills beta functions in the conventions of this volume, explain the sign difference between screening and antiscreening, recognize why gauge identities constrain counterterms, and distinguish perturbative asymptotic freedom from nonperturbative confinement.

## Landmarks

| Landmark | Meaning | Where it is used next |
|---|---|---|
| Gauge coupling $g(\mu)$ | A scheme-dependent coordinate on gauge-theory coupling space. | QED, Yang–Mills, QCD, and threshold matching. |
| Fine-structure variables | $\alpha=e^2/(4\pi)$ for QED and $\alpha_s=g_s^2/(4\pi)$ for QCD. | Running-coupling formulas and phenomenological conventions. |
| QED screening | Vacuum polarization by charged matter makes the effective electric charge grow toward shorter distances. | Landau-pole discussions and precision QED. |
| Non-Abelian antiscreening | Gauge-boson self-interactions drive the Yang–Mills coupling smaller in the ultraviolet when matter does not overwhelm them. | Asymptotic freedom and QCD. |
| One-loop gauge beta function | For Dirac fermions in representations $R_f$, $\beta_g= -b_0g^3/(16\pi^2)+O(g^5)$ with $b_0=11C_A/3-4T(R_f)n_f/3+\cdots$. | Asymptotic freedom, thresholds, and dimensional transmutation. |
| Ward identity | Abelian gauge symmetry relates correlation functions and renormalization constants. | QED charge renormalization and gauge-parameter checks. |
| Slavnov–Taylor identity | BRST-controlled non-Abelian identity relating gauge, ghost, matter, and vertex renormalization. | Renormalizability of Yang–Mills theory. |
| Background-field method | A split of fields into background and quantum pieces preserving background gauge covariance. | Efficient beta-function and effective-action calculations. |
| Dimensional transmutation | A dimensionless gauge coupling is traded for an RG-invariant scale. | $\Lambda_{\text{QCD}}$ and confinement-scale estimates. |
| Threshold matching | Changing the active field content across a mass threshold changes the beta function and matching condition. | QCD running and EFT decoupling. |

The most important conceptual landmark is that a gauge beta function is not a free-floating number. It belongs to a gauge-fixed, regulator-defined, scheme-defined calculation whose physical meaning is recovered through gauge-invariant observables.

## Common confusions

**Gauge symmetry is not an ordinary physical symmetry.** Gauge redundancy removes unphysical variables. Global remnants, center symmetries, and higher-form symmetries can be physical, but the local gauge redundancy itself is not a group that acts faithfully on distinct physical states.

**Gauge invariance does not automatically survive every regulator.** A hard momentum cutoff can break gauge identities if used carelessly. Dimensional regularization is popular partly because it preserves many gauge-theory identities efficiently, though it has its own subtleties.

**The beta function is not itself an observable.** It depends on the definition of the coupling and the scheme. Physical predictions become meaningful after combining running, matching, matrix elements, and observables consistently.

**Asymptotic freedom is not the same as confinement.** Asymptotic freedom is a UV statement accessible in perturbation theory. Confinement is an IR, nonperturbative phenomenon. The former strongly motivates the latter in QCD-like theories, but it is not a proof.

**QED and QCD do not differ only by group labels.** Non-Abelian gauge bosons carry charge under the gauge group. Their self-interactions qualitatively change the sign of the beta function.

**Ward identities are not optional checks after the calculation.** They are structural constraints. If a calculation violates them, either the regulator, counterterms, gauge fixing, algebra, or interpretation needs repair.

**The background-field method is not a new theory.** It is a computational organization of the same gauge theory. Its advantage is that background gauge invariance remains manifest in the effective action.

## Boundaries

This chapter does:

- explain QED, Yang–Mills, and QCD beta functions as examples of RG flow in gauge theory;
- show how gauge identities constrain counterterms and renormalization constants;
- introduce background-field methods as a gauge-covariant computational tool;
- clarify gauge-invariant regularization issues at the conceptual level;
- connect asymptotic freedom to dimensional transmutation and the emergence of a strong scale.

This chapter does not try to do:

- teach gauge symmetry from first principles, which belongs in the gauge-theory and foundations volumes;
- derive every gauge-theory Feynman rule or loop integral, which belongs in perturbative QFT;
- prove confinement or the Yang–Mills mass gap, which belongs in nonperturbative and rigorous QFT;
- develop the full Standard Model, electroweak theory, flavor, or collider phenomenology;
- give a complete BRST or BV treatment, which belongs in symmetry, gauge theory, and mathematical QFT chapters;
- replace QCD phenomenology, lattice QCD, or precision multi-loop running references.

The chapter is deliberately a bridge. It translates the general RG language into gauge theories without trying to become the whole gauge-theory curriculum.

## Where to go next

For the physical construction of QED, Yang–Mills theory, QCD, and the Standard Model, continue to the Gauge Theories and the Standard Model volume when available. For the nonperturbative meaning of the strong scale, Wilson loops, confinement, and the mass gap, continue to Nonperturbative QFT. For Ward identities, BRST, generalized symmetries, and anomalies, continue to Symmetry, Anomalies, and Topology.

Inside this volume, the next natural chapter is Statistical Field Theory and Criticality if you want the parallel story for order parameters and critical systems. If you want to continue particle-physics EFT, go to Matching, Running, and Decoupling and Major Effective Field Theories.

## References

### Standard first pass

- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on dilatations, renormalization and symmetry, secret symmetry, and asymptotic freedom.
- Mark Srednicki, *Quantum Field Theory*, for QED, non-Abelian gauge theory, beta functions, Ward identities, BRST symmetry, and background-field gauge.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for vacuum polarization, renormalization, running couplings, QED, Yang–Mills, and QCD examples.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapters on non-Abelian gauge theories, renormalization of gauge theories, and renormalization group methods.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, gauge-theory renormalization, and the broader RG framework.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the discussion of asymptotic freedom, gauge fields, Wilson loops, and nonperturbative gauge-theory intuition.
- Claude Itzykson and Jean-Bernard Zuber, *Quantum Field Theory*, for classic details on gauge-theory perturbation theory and renormalization.
- John C. Collins, *Renormalization*, for systematic renormalization, gauge-theory subtleties, and factorization-adjacent perspectives.

## Version history

- 2026-06-18: First polished draft. Added chapter overview, reading path, landmarks, boundaries, and references for gauge-theory RG.
