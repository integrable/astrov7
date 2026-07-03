---
title: "Higgs Sector"
description: "Chapter overview for the Higgs mechanism, the Standard Model Higgs doublet, electroweak gauge-boson masses, Higgs couplings, and the Goldstone equivalence theorem."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - Higgs mechanism
  - Higgs sector
  - electroweak symmetry breaking
  - Standard Model Higgs doublet
  - gauge boson masses
  - Goldstone equivalence theorem
canonicalTopics:
  - higgs-sector
  - higgs-mechanism
  - standard-model-higgs-doublet
  - electroweak-symmetry-breaking
  - gauge-boson-masses
  - higgs-couplings
researchStatus:
  established:
    - "The minimal Standard Model Higgs sector uses one complex SU(2)L doublet whose vacuum gives masses to W and Z bosons while leaving U(1)em unbroken."
  active:
    - "Precision Higgs-coupling measurements, Higgs self-coupling constraints, vacuum-stability analyses, and SMEFT interpretations remain active interfaces between the Higgs sector and experiment."
---

The Higgs Sector is the chapter where electroweak symmetry breaking becomes a dynamical field theory rather than a slogan. The previous chapter showed how $SU(2)_L\times U(1)_Y$ turns into electromagnetism and produces $W^\pm$, $Z$, and $A$. This chapter asks what field does that job, what degrees of freedom remain afterward, and how the resulting masses and couplings are organized.

The central object is the Standard Model Higgs doublet,

$$
H
=
\begin{pmatrix}
H^+\\ H^0
\end{pmatrix},
\qquad
Y_H=\frac12,
$$

with a vacuum direction chosen so that the unbroken generator is $Q=T^3+Y$. In unitary-gauge language one writes

$$
H(x)=\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v+h(x)
\end{pmatrix},
$$

but the physical content is not “the gauge symmetry disappeared.” The physical content is that three would-be Goldstone modes become the longitudinal polarizations of $W^\pm$ and $Z$, while one scalar excitation remains as the Higgs boson.

Read this chapter when you want the Higgs mechanism as a reusable QFT tool: first in Abelian and non-Abelian examples, then in the Standard Model, then in the high-energy behavior of longitudinal gauge bosons.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Higgs sector architecture](/figures/gauge-theories-standard-model/higgs-sector-architecture.svg)

<figcaption>

The minimal Higgs sector converts one complex electroweak doublet into three longitudinal gauge-boson modes plus one physical scalar. The same vacuum scale $v$ controls $m_W$, $m_Z$, tree-level fermion masses through Yukawa couplings, and the low-energy Fermi constant.

</figcaption>
</figure>

## Prerequisites

You should know the Electroweak Theory chapter through [Fermi Theory Limit](/gauge-theories-standard-model/electroweak/fermi-theory-limit/), especially the generator convention

$$
Q=T^3+Y
$$

and the covariant derivative on the Higgs doublet,

$$
D_\mu H
=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'\frac12 B_\mu\right)H.
$$

You should also know [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/) and [Gauge Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/). Those pages are conceptually important because the Higgs mechanism is often misdescribed as ordinary spontaneous breaking of a physical global symmetry.

Readers who want the perturbative side should later pair this chapter with Gauge Quantization, because quantizing spontaneously broken gauge theories requires gauge choices that keep the Goldstone, ghost, and gauge-boson sectors under control.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Abelian Higgs Model](/gauge-theories-standard-model/higgs-sector/abelian-higgs-model/) | The cleanest laboratory for a gauge field eating one Goldstone mode and becoming massive. |
| 2 | [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/) | How the counting generalizes when several gauge generators are broken. |
| 3 | [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) | The electroweak representation $H\sim(\mathbf 1,\mathbf 2)_{1/2}$ and why its neutral vacuum preserves electromagnetism. |
| 4 | [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/) | The potential $V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2$, the vacuum scale, and the Higgs mass at tree level. |
| 5 | [Gauge Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/) | The derivation of $m_W=gv/2$, $m_Z=\sqrt{g^2+g'^2}\,v/2$, and $m_A=0$. |
| 6 | [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/) | How $hWW$, $hZZ$, Yukawa, and self-interactions follow from expanding around the vacuum. |
| 7 | [Goldstone Equivalence Theorem](/gauge-theories-standard-model/higgs-sector/goldstone-equivalence-theorem/) | Why high-energy longitudinal $W$ and $Z$ amplitudes are controlled by the would-be Goldstone fields. |

The Electroweak Theory chapter already introduced electroweak symmetry breaking as part of the gauge-boson story. This chapter revisits the same structure from the Higgs-field point of view, with more attention to potentials, counting, couplings, and high-energy consistency.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| $H$ | The Standard Model Higgs doublet with hypercharge $Y=1/2$. | It is the only scalar field in the minimal Standard Model. |
| $V(H)$ | The Higgs potential. | Determines the vacuum scale and the physical Higgs mass at tree level. |
| $v$ | The Higgs vacuum scale. | Sets $m_W$, $m_Z$, tree-level fermion masses, and $G_F$ at tree level. |
| $G^\pm,G^0$ | Would-be Goldstone fields. | Become the longitudinal modes of $W^\pm$ and $Z$ in a Higgs phase. |
| $h$ | The physical Higgs boson. | The remaining scalar excitation after three Goldstone modes are absorbed. |
| $m_W,m_Z$ | Gauge-boson masses from $|D_\mu H|^2$. | Show that gauge-boson masses arise without explicit gauge-breaking mass terms. |
| $m_f$ | Fermion masses from Yukawa couplings. | Explain why fermion masses are proportional to Yukawa matrices, not predicted by gauge symmetry alone. |
| $hVV$ and $hff$ | Higgs couplings to vectors and fermions. | Encode how masses are tied to observable Higgs interactions. |
| Equivalence theorem | High-energy relation between longitudinal vectors and Goldstone fields. | Explains why the Higgs sector is essential for perturbative unitarity. |

The landmarks are not independent facts to memorize. They are all consequences of one representation choice and one vacuum direction.

## Common confusions

**Gauge symmetry is not literally destroyed.** Gauge symmetry is redundancy. In a Higgs phase, the gauge redundancy remains, but the spectrum and the convenient field variables reorganize.

**The Higgs boson is not one of the eaten Goldstone modes.** The Standard Model doublet contains four real fields. Three are reorganized into longitudinal $W^\pm$ and $Z$ modes; one remains as the physical scalar $h$.

**The photon is massless because the Higgs vacuum is electrically neutral.** The vacuum preserves $Q=T^3+Y$, so $U(1)_{\rm em}$ remains unbroken.

**The Higgs mechanism is not just adding Proca masses.** Explicit vector-boson mass terms would spoil gauge structure. Higgs masses arise from the gauge-invariant kinetic term $|D_\mu H|^2$ after expanding around the vacuum.

**The Higgs vacuum scale and the Higgs mass are not the same parameter.** At tree level, $v$ fixes weak-boson masses and $G_F$, while $m_h^2=2\lambda v^2$ depends on the quartic coupling $\lambda$.

**Yukawa couplings are part of the Higgs sector story but not predicted by it.** Gauge invariance allows Yukawa matrices; their observed values are input parameters of the minimal Standard Model.

**Unitary gauge is useful but not always the best gauge.** It makes the physical spectrum look simple, but covariant $R_\xi$ gauges are often better for loop calculations and renormalization.

## Boundaries

This chapter does:

- explain Abelian and non-Abelian versions of the Higgs mechanism;
- define the Standard Model Higgs doublet and its vacuum direction;
- derive the tree-level gauge-boson masses from $|D_\mu H|^2$;
- connect the Higgs vacuum scale to the Fermi constant at tree level;
- explain physical Higgs couplings to vectors, fermions, and itself;
- prepare the Goldstone equivalence theorem and high-energy longitudinal gauge-boson scattering;
- prepare the Flavor and Neutrinos chapter, where Yukawa matrices become flavor structure.

This chapter does not try to:

- give a full collider Higgs phenomenology course;
- maintain current numerical Higgs-coupling global fits;
- derive electroweak precision observables beyond tree level;
- classify extended Higgs sectors, composite Higgs models, or supersymmetric Higgs sectors;
- treat the hierarchy problem or naturalness in depth;
- replace the later SMEFT material on Higgs-coupling deviations.

The chapter’s job is to make the minimal Higgs sector feel like a gauge-theory mechanism, not a list of experimentally discovered couplings.

## Where to go next

After this chapter, continue to [Flavor and Neutrinos](/gauge-theories-standard-model/flavor-neutrinos/). The Higgs field gives masses to charged fermions through Yukawa couplings; flavor physics begins when those Yukawa matrices are diagonalized.

Then continue to Standard Model Architecture, where the gauge sector, Higgs sector, Yukawa sector, anomaly cancellation, accidental symmetries, and parameter counting are assembled into the full Standard Model Lagrangian.

For a deeper conceptual route, compare this chapter with the Symmetry, Anomalies, and Topology volume’s treatment of spontaneous symmetry breaking and with the Gauge Quantization chapter’s treatment of gauge fixing in spontaneously broken gauge theories.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§84–87, for spontaneous breaking of gauge symmetries, Abelian and non-Abelian Higgs mechanisms, and the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for spontaneous symmetry breaking, the Higgs mechanism, weak interactions, and electroweak symmetry breaking.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for a classic conceptual treatment of spontaneous symmetry breaking, Goldstone modes, Yang–Mills fields, and the Higgs phenomenon.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for spontaneously broken gauge theories and the electroweak theory.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for a standard perturbative treatment of the Higgs mechanism, electroweak symmetry breaking, and gauge choices.
- Burgess, *Introduction to Effective Field Theory*, for the effective-field-theory perspective on the Standard Model, low-energy weak interactions, and naturalness issues.

## Version history

- **2026-06-18:** Linked the Goldstone Equivalence Theorem page and added the handoff to Flavor and Neutrinos.
- **2026-06-18:** Linked the Gauge Boson Masses and Higgs Boson Couplings pages.
- **2026-06-18:** Linked the Standard Model Higgs Doublet and Higgs Potential pages.
- **2026-06-18:** Linked the first two chapter pages: Abelian Higgs Model and Non-Abelian Higgs Mechanism.
- **2026-06-18:** Initial chapter overview. Added the first-pass Higgs-sector reading path, landmarks, boundaries, and architecture figure.
