---
title: "Effective Field Theory"
description: "Chapter overview for effective field theory as the systematic low-energy expansion organized by locality, symmetry, power counting, matching, running, and decoupling."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Weinberg 1979 and 1995; Georgi EFT lectures; Polchinski 1984; Manohar and Georgi 1984; Burgess 2020; Schwartz 2014; Wilson and Kogut 1974."
topics:
  - effective field theory
  - locality
  - power counting
  - matching
  - running
  - decoupling
  - Wilson coefficients
canonicalTopics:
  - effective-field-theory
  - wilsonian-effective-action
  - matching-and-running
  - power-counting
researchStatus:
  established:
    - "Effective field theory is the standard framework for constructing predictive descriptions below a separation of scales using locality, symmetries, degrees of freedom, and power counting."
  active:
    - "Modern EFT work continues in precision Standard Model physics, gravity, cosmology, nuclear physics, many-body systems, hydrodynamics, open systems, amplitudes, and automated operator-basis methods."
---

Effective Field Theory is the chapter in the Renormalization, RG, and EFT volume where the Wilsonian lesson becomes a working method. A theory at low energies does not need to know every microscopic detail in order to be predictive. It needs the correct light degrees of freedom, the correct symmetries, locality, and a controlled expansion.

The chapter exists because the phrase "nonrenormalizable interaction" is one of the most historically misleading phrases in QFT. In the modern view, higher-dimension operators are not signs of failure. They are the systematic language of finite-resolution physics.

Read this chapter when you want to understand how to build a low-energy theory, how to organize its operators, how to match it to a more microscopic description, how Wilson coefficients run, why heavy particles decouple, and why field redefinitions and equations of motion are part of the method rather than optional cleanup.

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}
+
\sum_i \frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

Here $M$ is a heavy scale or organizing scale, $\mathcal O_i$ are local operators built from light fields, and $C_i(\mu)$ are Wilson coefficients. The slogan is simple:

$$
\text{EFT}=\text{degrees of freedom}+\text{symmetry}+\text{locality}+\text{power counting}.
$$

## Prerequisites

You should know the scale conventions in [Conventions and Notation](/renormalization-rg-eft/conventions/), especially the distinction between a cutoff $\Lambda$, a renormalization scale $\mu$, a physical scale $Q$, and a heavy threshold $M$. You should also know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/), [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

Readers who want the perturbative machinery behind matching should know [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/) and [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/). Readers who want the RG machinery should know [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

You do not need to know SMEFT, chiral perturbation theory, SCET, HQET, gravitational EFT, or nuclear EFT before starting. Those are examples. This chapter teaches the shared logic.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/) | The conceptual shift from microscopic finality to controlled finite-resolution description. |
| 2 | [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/) | Why the EFT Lagrangian contains all local operators compatible with the light fields and symmetries. |
| 3 | [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/) | How powers of external momenta organize local interactions when $Q\ll M$. |
| 4 | [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) | The rule that assigns a parametric size to diagrams and operators. |
| 5 | [Cutoff Versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/) | The distinction between the physical validity range, a regulator, and the arbitrary scale $\mu$. |
| 6 | [Matching](/renormalization-rg-eft/effective-field-theory/matching/) | How Wilson coefficients are fixed by requiring agreement with the more microscopic theory. |
| 7 | [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) | How Wilson coefficients evolve between scales and resum logarithms. |
| 8 | [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/) | Why heavy physics leaves local imprints at low energy under appropriate assumptions. |
| 9 | [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/) | How different Lagrangians can describe the same observables. |
| 10 | [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/) | How integration by parts, equations of motion, and field redefinitions reduce operator bases. |
| 11 | [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/) | Why higher-dimension operators are predictive once an expansion order is specified. |

After this path, you should be able to construct a simple EFT Lagrangian, state its expansion parameter, identify which coefficients must be matched, distinguish matching from running, and explain why an infinite tower of operators can still give finite predictive power.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Light degrees of freedom | Fields kept explicitly below the scale of interest. | Choosing them correctly is the first EFT decision. |
| Heavy scale $M$ | A mass gap, threshold, breakdown scale, or organizing scale. | Suppresses higher-dimension operators by powers of $Q/M$. |
| Wilson coefficient $C_i(\mu)$ | A coefficient multiplying a local EFT operator. | Stores short-distance information not represented by light fields. |
| Operator basis | A chosen set of independent local operators. | Makes matching and running finite-dimensional at each order. |
| Power counting | A rule for estimating the size of operators and diagrams. | Turns an infinite Lagrangian into an ordered calculation. |
| Matching | Fixing EFT coefficients by comparing to a more microscopic description. | Transfers information across a threshold. |
| Running | RG evolution of Wilson coefficients inside the EFT. | Resums logarithms and separates scales. |
| Decoupling | Heavy physics affects low-energy observables through local suppressed operators. | Explains why low-energy physics is insensitive to most UV details. |
| Redundant operator | An operator removable by field redefinitions or equations of motion. | Prevents overcounting Wilson coefficients. |
| Breakdown scale | The scale where neglected degrees of freedom or operators become important. | Defines the domain of validity of the EFT. |
| Naturalness | A criterion for whether parameter sizes are stable under radiative corrections. | Diagnoses sensitivity to short-distance physics. |

The most important landmark is power counting. Without power counting, an EFT is merely a long list of allowed terms. With power counting, it is a predictive expansion.

## Common confusions

**EFT is not an approximation to laziness.** It is the correct language when physics separates into scales. Sometimes the EFT is more predictive and more transparent than the microscopic theory for the questions being asked.

**Nonrenormalizable does not mean nonpredictive.** A nonrenormalizable interaction requires more counterterms at higher orders, but only finitely many at any fixed order in the low-energy expansion.

**The cutoff is not the renormalization scale.** The cutoff or breakdown scale describes where the EFT stops being valid. The scale $\mu$ labels a convention for renormalized coefficients.

**Matching is not running.** Matching fixes boundary conditions for Wilson coefficients at a threshold. Running evolves those coefficients within a fixed EFT.

**Integrating out is not deleting.** Heavy fields disappear as explicit degrees of freedom, but their effects remain in Wilson coefficients and higher-dimension operators.

**Symmetry does not pick one operator.** Symmetry usually permits many operators. The EFT rule is to include all operators compatible with the symmetries, then organize them by power counting.

**Field redefinitions do not change physics.** They change coordinates on theory space. A different-looking Lagrangian can describe the same $S$-matrix after coefficients and operator definitions are transformed consistently.

**Wilson coefficients are not usually observables.** They depend on scheme, scale, normalization, and basis. Observables are obtained after combining coefficients, matrix elements, and running consistently.

**Power counting is not only engineering dimension.** Engineering dimension is the start. Loops, symmetry breaking, small couplings, velocity scalings, chiral counting, large-$N$ counting, and kinematic modes can modify the appropriate power-counting rule.

**EFT does not require knowing the UV theory.** Matching to a known UV theory is wonderful when available. But an EFT can also be defined phenomenologically, with coefficients measured from data.

## Boundaries

This chapter does:

- explain EFT as a systematic expansion in local operators;
- distinguish light degrees of freedom from heavy or unresolved physics;
- introduce Wilson coefficients, operator bases, derivative expansions, and power counting;
- explain matching, running, threshold corrections, and decoupling;
- clarify the difference between a cutoff, a breakdown scale, and a renormalization scale;
- explain how field redefinitions, redundant operators, and equations of motion simplify EFT bases;
- prepare the reader for major examples such as Fermi theory, chiral perturbation theory, HQET, SCET, SMEFT, gravitational EFT, hydrodynamic EFT, and worldline EFT.

This chapter does not try to do:

- provide a complete basis for SMEFT, LEFT, HEFT, or any other large phenomenological EFT;
- replace the Major Effective Field Theories chapter, where named EFTs are collected;
- teach every loop integral needed for one-loop matching, which belongs in perturbative and model-calculation pages;
- develop the full theory of naturalness and hierarchy problems, which has its own chapter;
- cover nonlocal EFTs, open-system EFTs, or stochastic effective theories in full detail;
- treat EFT in quantum gravity or cosmology beyond the general logic and selected previews.

The boundary is useful. This chapter teaches the reusable grammar. Later chapters and volumes apply it to particular physical languages.

## Where to go next

After this chapter, the natural continuation is [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/), where the conceptual steps become explicit workflows. Then go to [Naturalness and Power Counting](/renormalization-rg-eft/naturalness-power-counting/) for radiative stability, hierarchy problems, and dimensional estimates.

For examples, continue to [Major Effective Field Theories](/renormalization-rg-eft/major-efts/). There the abstract logic becomes Fermi theory, chiral perturbation theory, nonlinear sigma models, heavy-quark EFT, nonrelativistic QED and QCD, SCET, SMEFT, gravitational EFT, hydrodynamic EFT, and worldline EFT.

For the operator language behind EFT bases, return to [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/). For the Wilsonian origin of EFT, return to [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/). For gauge-theory applications, go later to Gauge Theories and the Standard Model.

## References

- Steven Weinberg, "Phenomenological Lagrangians," *Physica A* **96** (1979) 327–340, and *The Quantum Theory of Fields*, especially the effective-field-theory perspective in Vols. I and II.
- Howard Georgi, *Weak Interactions and Modern Particle Theory*, and lectures on effective field theory, for the pragmatic particle-physics EFT viewpoint.
- Aneesh V. Manohar, "Effective Field Theories," for a concise modern review of EFT logic, power counting, and applications.
- C. P. Burgess, *Introduction to Effective Field Theory*, for a broad, scale-hierarchy-centered treatment across particle, gravitational, atomic, nuclear, and condensed-matter examples.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for renormalization, nonrenormalizable theories, RG, and Standard Model EFT motivations.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian origin of scale-dependent effective descriptions.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," for the Wilsonian and perturbative foundations of effective Lagrangians.
- A. V. Manohar and H. Georgi, "Chiral Quarks and the Nonrelativistic Quark Model," for naive dimensional analysis and chiral EFT intuition.

## Version history

- 2026-06-17: First polished chapter overview. Added reading path, landmarks, common confusions, boundaries, references, and cross-links to Wilsonian RG, local operators, matching, running, decoupling, and major EFT examples.
