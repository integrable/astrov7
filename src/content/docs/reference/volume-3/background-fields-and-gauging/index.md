---
title: "Background Fields and Gauging"
description: "Chapter overview for source couplings, background gauge fields, global-form data, and the operation of gauging global symmetries."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§22 and 67–68; Weinberg Vol. II chs. 16–17; Schwartz chs. 14 and 34; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - background fields
  - source couplings
  - gauging
  - global symmetry
  - Ward identities
  - anomalies
canonicalTopics:
  - background-field
  - source-coupling
  - background-gauge-field
  - gauging-global-symmetry
  - global-form-of-symmetry
researchStatus:
  established:
    - "Coupling QFTs to nondynamical sources and background gauge fields is the standard way to define current correlators, Ward identities, response functions, and tests for anomalies."
  active:
    - "Modern generalized symmetry, non-invertible symmetry, symmetry TFT, and relative QFT refine what counts as background data and what it means to gauge a symmetry."
---

Background Fields and Gauging is the chapter in the Symmetry, Anomalies, and Topology volume where symmetry is tested by coupling the theory to external data. The Noether chapter taught currents and Ward identities inside a fixed theory. This chapter upgrades those ideas to the source-dependent object

$$
Z[J,A,g]=e^{iW[J,A,g]},
$$

where $J$ sources local operators, $A$ is a background gauge field for a global symmetry, and $g_{\mu\nu}$ is a background metric.

The reason this chapter deserves its own home is simple: many of the sharpest statements about symmetry are not statements about a single Lagrangian at $A=0$. They are statements about whether the theory can be consistently placed in arbitrary background fields, how the partition function transforms under background gauge transformations, and whether one is allowed to sum over those backgrounds.

Read this chapter when you want to understand how sources generate correlators, why background gauge invariance is the clean form of a Ward identity, why an anomaly is an obstruction to gauging rather than merely a broken conservation equation, and why the global form of a symmetry group matters.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic map from a QFT and its operators, currents, and stress tensor to background data, the partition functional, correlators, Ward identities, anomaly tests, and gauging.](/figures/symmetry-anomalies-topology/background-fields-gauging-roadmap.svg)

<figcaption>

Background fields turn operators, currents, and stress tensors into functional derivatives of $W$. Gauging is a further operation: one promotes suitable background fields to summed-over fields. An anomaly is detected before gauging, as a failure of background gauge invariance.

</figcaption>
</figure>

## Prerequisites

You should know the [volume conventions](/symmetry-anomalies-topology/conventions/), especially the choices

$$
D=d-iA,
\qquad
F=dA-iA\wedge A,
\qquad
Z[A]=e^{iW[A]},
\qquad
\langle j_a^\mu\rangle_A=\frac{\delta W}{\delta A_\mu^a}.
$$

You should also have read the Ordinary Global Symmetries chapter and the Noether Currents and Ward Identities chapter. The most important preparation is knowing that local Ward identities contain contact terms, and that currents are not unique before one specifies how they couple to sources.

A first pass through this chapter does not require BRST, anomaly polynomials, fiber-bundle theory, or higher-form symmetry. Those subjects enter later, but the language of background fields is the bridge to all of them.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Sources and Background Fields | The basic dictionary between sources, functional derivatives, current insertions, background metrics, and response. |
| 2 | Background Fields for Global Symmetries | Why a global symmetry is more sharply tested by coupling to a background gauge field than by writing a current at $A=0$. |
| 3 | Background Fields versus Dynamical Gauge Fields | The difference between probing a symmetry and introducing a gauge redundancy. |
| 4 | Global Form of Symmetry Groups | Why the Lie algebra is not enough: bundles, allowed background fields, line operators, and quotient groups depend on global form. |
| 5 | Gauging Global Symmetries | The operation of summing over background fields, including gauge equivalence, local counterterms, and anomaly obstructions. |
| 6 | Gauging Finite Symmetries Preview | The finite-group version, where backgrounds are flat bundles or cochains rather than ordinary Noether gauge fields. |
| 7 | Quotienting by Symmetry | The relation between gauging, orbifolding, constraints, projections, and emergent dual symmetries. |

For a minimal path before the anomaly chapters, read steps 1, 2, 3, and 5. Return to the global-form page before studying one-form symmetry, line operators, Yang–Mills theta angles, or discrete anomalies.

## Landmarks

**A source is a probe, not a new particle.** A source $J(x)$ coupled to an operator $\mathcal O(x)$ defines a source-dependent generating functional,

$$
Z[J]=\int\mathcal D\Phi\,\exp\!\left(iS[\Phi]+i\int d^dx\,J(x)\mathcal O(x)\right).
$$

Functional derivatives of $W[J]$ generate connected correlation functions. The source is held fixed; it is not integrated over.

**A background gauge field is a source with transformation law.** For a global symmetry current $j_a^\mu$, the linear coupling is

$$
S\longrightarrow S+\int d^dx\,A_\mu^a j_a^\mu+\cdots.
$$

The dots are often essential. For a non-Abelian or nonlinear symmetry, the full coupling to $A$ is not determined by the current alone. It must be completed so that $W[A]$ has a well-defined transformation law under background gauge transformations.

**Background gauge invariance is the source-space form of the Ward identity.** In a nonanomalous theory on a closed spacetime,

$$
W[A^g]=W[A].
$$

Infinitesimally this gives the covariant Ward identity for the current in the presence of background fields. Differentiating it with respect to sources generates the contact terms in current correlators.

**Gauging is not the same operation as coupling to a background.** Coupling to $A$ asks how the original theory responds to a nondynamical probe. Gauging asks one to form a new theory by summing over gauge-equivalence classes of $A$ and specifying allowed bundles, counterterms, and topological sectors:

$$
Z_{\mathcal T/G}
\sim
\sum_{[A]} Z_{\mathcal T}[A]e^{iS_{\mathrm{local}}[A]}.
$$

The symbol $\sum_{[A]}$ is schematic. It can mean a path integral over connections, a sum over flat finite-group bundles, a sum over higher-form fields, or a more general categorical operation.

**Anomalies are detected before gauging.** A global symmetry can be a perfectly good physical symmetry even if it cannot be gauged. The obstruction is visible as a failure of background gauge invariance,

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A].
$$

For a dynamical gauge field this would be an inconsistency. For a background field of a global symmetry it is an ’t Hooft anomaly, hence physical data that must be matched along RG flow.

**The global form matters.** The Lie algebra tells you infinitesimal currents. It does not tell you which bundles are allowed, which line operators are genuine, what the center symmetry is, or whether the symmetry is $SU(N)$, $PSU(N)$, $SO(3)$, $Spin(N)$, or a quotient. Background fields remember this information.

**Finite symmetries also have background fields.** A finite symmetry has no ordinary Noether current, but it can still be coupled to a background bundle. This is why finite symmetries have Ward identities, selection rules, anomalies, and gauging operations even without a conserved current density.

## Common confusions

**“A background field is just a classical value of a dynamical field.”** Sometimes, but not in general. A background field can be a nondynamical source for an operator that has no dynamical counterpart in the original theory.

**“The current determines the full background coupling.”** Usually only to first order in $A$. Gauge invariance, locality, counterterms, and global topology determine the nonlinear completion.

**“If a symmetry is anomalous, it is not a symmetry.”** A gauge anomaly ruins a dynamical gauge theory. An ’t Hooft anomaly of a global symmetry is a consistent and extremely useful property of the theory.

**“Gauging means allowing the parameter to depend on spacetime.”** Localizing a parameter is how one derives a current. Gauging is the stronger operation of introducing or summing over gauge fields and quotienting by gauge equivalence.

**“The Lie algebra specifies the symmetry.”** It specifies only local infinitesimal data. The global group, possible quotients, background bundles, and allowed charged operators are extra global data.

**“Finite symmetries cannot have anomalies because they have no currents.”** Finite symmetries can have ’t Hooft anomalies. Their anomalies are diagnosed by background bundles and partition functions, not by divergences of Noether currents.

## Boundaries

This chapter is about source couplings, background fields, and the operation of gauging. It deliberately stops before the following subjects take over.

| Topic | Treated here | Continued in |
|---|---|---|
| Noether currents | Used as first-order source couplings | Noether Currents and Ward Identities |
| Gauge redundancy | Contrasted with background gauge invariance | Gauge Redundancy and BRST |
| Dynamical Yang–Mills theory | Only the distinction between background and dynamical fields | Gauge Theories and the Standard Model |
| ’t Hooft anomalies | Defined as obstruction to gauging | ’t Hooft Anomalies and Anomaly Matching |
| Perturbative anomaly calculations | Previewed through $\delta W[A]$ | Anomalies |
| Higher-form symmetry backgrounds | Mentioned as generalized background fields | Higher-Form and Generalized Symmetries |
| Non-invertible gauging | Only a research-status preview | Non-Invertible and Categorical Symmetries; Symmetry TFT and Anomaly Inflow |
| BRST and Faddeev–Popov | Not used in the basic background-field formalism | Gauge Redundancy and BRST |
| Effective action methods | Used only as source language | Renormalization, RG, and EFT; Perturbative QFT |

## Where to go next

After this chapter, continue to Spontaneous Symmetry Breaking if you want the fate of global symmetries in the vacuum. Background sources are useful there because order parameters and Goldstone currents are best understood as responses to external probes.

If your goal is anomalies, continue from here to Anomalies and then to ’t Hooft Anomalies and Anomaly Matching. The anomaly chapters assume you know the distinction between a dynamical gauge field and a background gauge field.

If your goal is generalized symmetry, return to this chapter before reading Higher-Form and Generalized Symmetries. Higher-form symmetry is largely the same story with higher-degree background gauge fields and extended charged operators.

## References

- Mark Srednicki, *Quantum Field Theory*, §§22 and 67–68. Useful for ordinary currents and Ward identities, including gauge-theory applications.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters 16–17. Useful for external-field methods, effective actions, background-field gauge, and Slavnov–Taylor/Zinn–Justin identities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 14 and 34. Useful for generating functionals, Ward–Takahashi identities, and background-field methods.
- Sidney Coleman, *Aspects of Symmetry*. Useful for current algebra, broken symmetries, Ward identities, and the physical role of symmetry probes.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Standard modern reference for coupling ordinary and higher-form global symmetries to classical background fields and for gauging them when unobstructed.
- Edward Witten, “Global Aspects of Current Algebra” and related papers. Classic source for background-field and anomaly-inflow reasoning in current algebra and Wess–Zumino terms.
- Daniel Freed and Michael Hopkins, “Reflection Positivity and Invertible Topological Phases.” Useful advanced reference for anomaly and invertible-field-theory language.

## Version history

- **2026-06-17:** Initial polished chapter overview for Background Fields and Gauging.
