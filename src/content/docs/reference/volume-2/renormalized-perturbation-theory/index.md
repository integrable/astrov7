---
title: "Renormalized Perturbation Theory"
description: "Chapter overview for renormalized Lagrangians, renormalization conditions, schemes, field and parameter renormalization, Green functions, and S-matrix elements in the Renormalization, RG, and EFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§18–29; Schwartz chs. 18–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Zinn-Justin, renormalization chapters."
topics:
  - renormalized perturbation theory
  - counterterms
  - renormalization conditions
  - renormalization schemes
  - Green functions
  - S-matrix
canonicalTopics:
  - renormalized-perturbation-theory
  - renormalization-schemes
  - renormalized-lagrangian
  - renormalized-green-functions
researchStatus:
  established:
    - "Renormalized perturbation theory is the standard framework for computing finite, scheme-defined Green functions and amplitudes order by order from a regulated local QFT."
  active:
    - "Scheme choices, gauge identities, unstable particles, infrared singularities, EFT matching, automated multi-loop workflows, and nonperturbative definitions remain important handoffs to later chapters and other volumes."
---

Renormalized Perturbation Theory is the chapter in the Renormalization, RG, and EFT volume where counterterms stop being only a conceptual cure for divergences and become a working calculation scheme. The central object is a regulated bare theory rewritten in terms of renormalized fields, renormalized parameters, and local counterterm vertices.

The chapter exists because the phrase "cancel the infinity" is not enough to do physics. A calculation must say which parameters are being held fixed, how finite parts are chosen, what counts as a measured input, which Green functions or amplitudes are being renormalized, and how the answer changes when the subtraction convention changes.

Read this chapter when you want to turn loop corrections into finite perturbative predictions without losing track of the distinction between bare quantities, renormalized coordinates, scheme choices, and physical observables.

$$
\text{regulated loops}
\quad +\quad
\text{local counterterms}
\quad +\quad
\text{renormalization conditions}
\quad =\quad
\text{finite scheme-defined predictions}.
$$

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), the conceptual arc of [Why Renormalization?](/renormalization-rg-eft/why-renormalization/), and the counterterm logic developed in [Regularization and Counterterms](/renormalization-rg-eft/regularization-counterterms/). In particular, this chapter assumes the reader understands [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/).

For actual loop-integral evaluation, use the Loop Expansion and Regularization and Loop Integral Technology chapters in the Perturbative QFT and Scattering volume. This chapter cares about the renormalized organization of the calculation, not about replacing a table of integrals.

## Reading path

Read these pages in order on a first pass. Pages listed without links are planned pages in this chapter and should become links as they are published.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) | The basic split $\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}$ and the meaning of counterterm vertices. |
| 2 | Renormalization Conditions | How measured inputs or subtraction rules fix the otherwise ambiguous finite parts. |
| 3 | Counterterm Schemes | A unified language for on-shell, momentum-subtraction, MS, and $\overline{\mathrm{MS}}$-style choices. |
| 4 | On-Shell Scheme | How pole masses, residues, and physical thresholds can define parameters when stable particles exist. |
| 5 | Minimal Subtraction | How subtracting pole parts in dimensional regularization produces mass-independent schemes and efficient beta functions. |
| 6 | MS-bar Scheme | The modified subtraction convention used in most modern perturbative calculations. |
| 7 | Wavefunction Renormalization | How field normalization, propagator residues, anomalous dimensions, and LSZ factors are related. |
| 8 | Mass and Coupling Renormalization | How renormalized masses and couplings are fixed, shifted, and run. |
| 9 | Renormalized Green Functions | How connected and 1PI functions become finite scheme-dependent objects. |
| 10 | Renormalized S-Matrix | How field normalization, poles, residues, and counterterms enter physical scattering amplitudes. |

After this path, you should be able to read a one-loop renormalization calculation and know which choices are physics, which choices are conventions, and which expressions are merely intermediate regulated objects.

## Landmarks

| Landmark | Meaning | Where it is used next |
|---|---|---|
| Bare Lagrangian $\mathcal L_0$ | The regulated local expression written in terms of bare fields and bare parameters. | Defining what is held fixed when differentiating with respect to $\mu$. |
| Renormalized Lagrangian $\mathcal L_{\text{ren}}$ | The part used for propagators and interaction vertices expressed in terms of renormalized parameters. | Organizing perturbation theory around measured or scheme-defined inputs. |
| Counterterm Lagrangian $\mathcal L_{\text{ct}}$ | The local remainder that cancels regulator dependence and implements the scheme. | Loop calculations, renormalization conditions, and beta functions. |
| Renormalization condition | A rule that fixes finite parts of counterterms. | On-shell schemes, momentum subtraction, physical inputs. |
| Renormalization scheme | A systematic convention for defining renormalized parameters. | Scheme dependence, matching, running, and uncertainty estimates. |
| $Z$ factor | A multiplicative renormalization constant for a field, parameter, or operator. | Wavefunction renormalization, anomalous dimensions, operator mixing. |
| Minimal subtraction | A scheme that subtracts pole terms in dimensional regularization. | Efficient RG equations and mass-independent beta functions. |
| $\overline{\mathrm{MS}}$ | A modified minimal-subtraction convention subtracting $1/\bar\epsilon$. | Modern perturbative QCD, EFT, and multi-loop calculations. |
| Pole mass | A mass defined by a pole of a propagator, when such a pole is meaningful. | On-shell schemes and LSZ normalization. |
| Renormalized 1PI function | A finite scheme-defined vertex function. | Effective actions, Callan–Symanzik equations, and matching. |

The most important structural landmark is that a renormalized Lagrangian is not a new theory added on top of the bare theory. It is a coordinate system for doing perturbation theory in a way that keeps finite measured quantities visible.

## Common confusions

**Regularization is not renormalization.** A regulator makes intermediate expressions well defined. Renormalized perturbation theory says how to express those expressions in terms of finite fields and parameters.

**A counterterm is not an ad hoc force.** Counterterms are the local operators already allowed by symmetries and power counting. Their coefficients encode how the chosen renormalized coordinates sit inside the regulated bare theory.

**Bare parameters are not measured inputs.** In perturbative continuum language, bare parameters are regulator-dependent. Measured masses, couplings, rates, and cross sections are compared to finite quantities after renormalization.

**Finite parts are not meaningless.** Infinite or pole parts are forced by finiteness. Finite parts choose the scheme. Changing finite parts changes the numerical values assigned to renormalized parameters, but not physical predictions when the calculation is done consistently.

**Minimal subtraction is not automatically physical.** MS and $\overline{\mathrm{MS}}$ are efficient, clean, and widely used. They are not direct experimental definitions of parameters.

**Renormalized fields are not automatically particles.** A field can interpolate a particle, but particle masses and residues are extracted from poles of correlation functions. In gauge theories and confining theories, this relation becomes especially delicate.

**Scheme dependence is not a bug.** Scheme dependence is coordinate dependence on theory space. Truncated perturbation theory leaves residual scheme and scale dependence, which is useful as a diagnostic but not itself an observable.

## Boundaries

This chapter does:

- define the renormalized Lagrangian and counterterm Lagrangian;
- explain how renormalization conditions fix finite parts;
- compare common perturbative schemes;
- organize field, mass, and coupling renormalization;
- connect renormalized Green functions to amplitudes and observables;
- prepare the derivation of beta functions and anomalous dimensions.

This chapter does not try to do:

- evaluate general loop integrals, which belongs in Perturbative QFT and Scattering;
- give the Wilsonian explanation of coarse graining, which belongs in [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/);
- develop full RG flow, which belongs in [Renormalization Group Equations](/renormalization-rg-eft/renormalization-group-equations/);
- prove all-orders renormalizability, which belongs later with structural and gauge-theory material;
- handle infrared divergences and factorization, which belong in Perturbative QFT and Scattering;
- define EFT matching in full, which belongs in [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) and [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/).

## Where to go next

After this chapter, continue to [Renormalization Group Equations](/renormalization-rg-eft/renormalization-group-equations/). The beta function is easiest to understand after the reader has seen why renormalized parameters depend on an arbitrary scale $\mu$.

For a deeper physical interpretation, continue to [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/), where changing scale means changing which degrees of freedom are explicit. For applications in low-energy expansions, go to [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/). For gauge-theory-specific identities and constraints, use [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/).

When you want concrete benchmark calculations, use the [Model Calculation Library](/renormalization-rg-eft/model-calculation-library/), especially the pages on one-loop $\phi^4$ renormalization and beta functions.

## References

### Standard first pass

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures and the discussion of counterterms and physical perturbation theory.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on higher-order corrections, renormalizability, schemes, the renormalization group, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 18–23, for mass renormalization, counterterms, renormalized perturbation theory, renormalizability, and RG.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18, for a systematic treatment of renormalization, scheme dependence, and RG methods.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the all-orders field-theoretic and statistical-field-theory perspective.
- John Collins, *Renormalization*, for a classic systematic account of perturbative renormalization.
- C. P. Burgess, *Introduction to Effective Field Theory*, for the EFT interpretation of renormalized perturbation theory and matching.

## Version history

- 2026-06-17: First polished draft as the chapter overview for renormalized perturbation theory.
