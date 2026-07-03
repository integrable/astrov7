---
title: "Foundational Models"
description: "Chapter overview for the model-card chapter in the Foundations of QFT volume: phi-four theory, Yukawa theory, scalar QED, QED preview, and sigma-model preview."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, selected chapters on scalar interactions, Yukawa theory, scalar QED, QED, and symmetry breaking; Coleman 2019, selected lectures on Wick diagrams, renormalization, gauge fields, QED, and sigma models; Zee 2010, selected chapters; Weinberg 1995, Vol. I, chs. 6–13."
topics:
  - foundational models
  - phi-four theory
  - Yukawa theory
  - scalar QED
  - QED
  - sigma models
  - model cards
canonicalTopics:
  - foundational-models
  - phi-four-theory
  - yukawa-theory
  - scalar-qed
  - qed-preview
  - sigma-model-preview
researchStatus:
  established:
    - "Phi-four theory, Yukawa theory, scalar QED, spinor QED, and sigma models are standard laboratories for interactions, symmetries, vertices, counterterms, and effective descriptions."
  active:
    - "Their renormalization, nonperturbative behavior, critical phenomena, gauge dynamics, and low-energy effective-theory roles are treated in later volumes."
---

Foundational Models is the chapter in the Foundations of QFT volume where the machinery stops floating in abstraction and becomes a set of small laboratories. Each model is compact enough to inspect directly, but rich enough to teach a structure that reappears across QFT.

The models here are not chosen because the world is literally built from these few Lagrangians. They are chosen because they are clean places to see how local interactions become vertices, how symmetries restrict terms, how loop corrections generate local counterterms, and how useful approximations turn into effective theories.

Read this chapter after you know free fields, correlators, path integrals, Wick expansion, symmetry, and gauge redundancy. By the end, the basic Lagrangians of graduate QFT should feel like reusable instruments rather than isolated examples.

$$
\text{model card}
\quad=\quad
\text{fields, Lagrangian, symmetries, vertices, lessons, and handoffs}.
$$

## Prerequisites

You should know [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Dirac Field](/foundations/free-fields/dirac-field/), and [Maxwell Field](/foundations/free-fields/maxwell-field/) for the free building blocks. You should also know [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) and [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) for the perturbative language.

For the gauge examples, review [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/). Full renormalization is not required yet; these model cards only mark where it first becomes unavoidable.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/) | The smallest stable scalar interaction with vertices, symmetry factors, loop previews, phases, and critical-phenomena handoffs. |
| 2 | [Yukawa Theory](/foundations/foundational-models/yukawa-theory/) | The scalar–fermion coupling, scalar exchange, fermion-loop signs, and mass-generation previews. |
| 3 | [Scalar QED](/foundations/foundational-models/scalar-qed/) | How gauge invariance packages charged-scalar derivative vertices and seagull vertices together. |
| 4 | [QED Preview](/foundations/foundational-models/qed-preview/) | The basic spinor-QED Lagrangian, fermion-photon vertex, Ward–Takahashi identity, and infrared warnings. |
| 5 | [Sigma Model Preview](/foundations/foundational-models/sigma-model-preview/) | How symmetry breaking, Goldstone fields, target geometry, and low-energy effective dynamics enter QFT. |

After this path, you should be able to read a simple Lagrangian as data: fields, symmetries, interactions, allowed counterterms, useful limits, and the later volume where the full story belongs.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| `$\mathcal L=\frac12(\partial\phi)^2-\frac12m^2\phi^2-\frac{\lambda}{4!}\phi^4$` | The basic real scalar self-interaction and first serious vertex laboratory. | Wick expansion, loops, RG, critical phenomena. |
| `Yukawa vertex $-iy$` | A scalar can couple locally to the fermion bilinear $\overline\psi\psi$. | Scalar exchange, fermion loops, Higgs-like mass terms. |
| `$D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi$` | Scalar QED turns local charge covariance into derivative and seagull interactions. | Gauge theory, Ward identities, Abelian Higgs preview. |
| `$\mathcal L_{\mathrm{QED}}=-\frac14F_{\mu\nu}F^{\mu\nu}+\overline\psi(i\gamma^\mu D_\mu-m)\psi$` | Spinor QED assembles photons, Dirac matter, charge conservation, and gauge-fixed perturbation theory. | Gauge theories, precision QED, infrared physics. |
| `$O(N)\to O(N-1)$` | The linear sigma model gives a clean symmetry-breaking pattern with $N-1$ Goldstone modes. | Goldstone theorem, EFT, critical phenomena. |
| `counterterm closure` | A model is stable under perturbation only if the local operators required by symmetries are included. | Renormalization, EFT, operator bases. |

## Common confusions

**Toy model does not mean disposable.** A useful model is small enough to understand and important enough to reuse. The models in this chapter are selected because they isolate mechanisms that later appear in realistic theories.

**A Lagrangian is not a wish list of terms.** Once fields and symmetries are chosen, quantum corrections usually force a whole compatible set of local operators. Omitting a scalar self-coupling or a gauge-required seagull term can make the model unstable under renormalization.

**Gauge invariance is not diagram-by-diagram obvious.** Scalar QED is the warning sign: derivative exchange diagrams and seagull diagrams work together. Checking one diagram alone can hide the symmetry relation.

**Preview pages can still be precise.** QED and sigma models are too large to finish inside Foundations, but their preview pages still fix conventions and state the core structural facts. A preview is a scoped entrance, not a vague placeholder.

**Model cards do not replace later volumes.** A model card identifies fields, symmetries, vertices, and lessons. Full renormalization, nonperturbative behavior, Standard Model physics, and critical phenomena need their own chapters later.

## Boundaries

This chapter does:

- collect compact model cards for the first interacting QFT laboratories;
- show how free fields, symmetries, Wick expansion, and gauge redundancy assemble into working Lagrangians;
- identify the lesson each model teaches and where its complete treatment belongs later.

This chapter does not try to do:

- full renormalization or RG flow of these models;
- precision QED, QCD, electroweak theory, or the Standard Model;
- nonperturbative sigma-model dynamics, constructive scalar theory, or full critical phenomena.

Those topics belong in Perturbative QFT and Scattering, Renormalization, RG, and EFT, Gauge Theories and the Standard Model, Matter, Statistical Physics, and Quantum Information, Nonperturbative QFT, and Mathematical and Rigorous QFT.

## Where to go next

For calculation, continue to Perturbative QFT and Scattering, where Feynman rules become amplitudes, decay rates, cross sections, and loop corrections. For scale dependence and counterterms, continue to Renormalization, RG, and EFT.

For physical gauge theories, continue to Gauge Theories and the Standard Model. For phases, criticality, sigma models, and Goldstone effective theories, continue to Matter, Statistical Physics, and Quantum Information or Nonperturbative QFT.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for scalar interactions, Yukawa theory, scalar electrodynamics, QED, Ward identities, and symmetry breaking.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for Wick diagrams, mass renormalization, vector fields, QED, gauge fixing, and sigma-model intuition.
- Zee, *Quantum Field Theory in a Nutshell*, for a physics-first introduction to scalar models, gauge theory, symmetry breaking, and sigma-model ideas.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for the structural and perturbative formulation of scalar, spinor, and gauge-field models.
- Schwartz, *Quantum Field Theory and the Standard Model*, for model calculations that connect the first QFT laboratories to QED, renormalization, and the Standard Model.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the scalar and sigma-model bridge to critical phenomena and RG.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
