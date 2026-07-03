---
title: "Non-Abelian Gauge Theory and Yang–Mills"
description: "Chapter overview for non-Abelian gauge transformations, Yang–Mills curvature, gauge-boson self-interactions, representations, color, and global form."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–73; Weinberg Vol. II Ch. 15; Schwartz Chs. 25–26; Coleman, Aspects of Symmetry, Secret Symmetry; Polyakov, Gauge Fields and Strings, Chs. 1–3."
topics:
  - Yang–Mills theory
  - non-Abelian gauge theory
  - gauge transformations
  - field strength
  - gauge-boson self-interactions
  - color representations
  - global form
  - center symmetry
canonicalTopics:
  - yang-mills-theory
  - non-abelian-gauge-theory
  - non-abelian-gauge-transformations
  - gauge-boson-self-interactions
  - color-su3
  - global-form-of-gauge-group
  - center-symmetry
researchStatus:
  established:
    - "The local classical structure of Yang–Mills theory is textbook-standard: non-Abelian gauge transformations, curvature, invariant kinetic terms, and representation-dependent matter couplings."
  active:
    - "The nonperturbative dynamics of Yang–Mills theory, including confinement and the mass gap, remains a central research subject treated later in the volume."
---

Non-Abelian Gauge Theory and Yang–Mills is the chapter where gauge theory stops being a dressed-up version of electromagnetism. In QED the gauge group is Abelian, so the photon carries no electric charge. In Yang–Mills theory the generators do not commute, the field strength is nonlinear, and the gauge bosons themselves carry the charge of the gauge group.

The chapter exists because this one structural change explains a startling amount of modern particle physics. It gives gluon self-interactions in QCD, weak-isospin gauge bosons in the electroweak theory, ghosts in covariant quantization, asymptotic freedom after quantization, Wilson-loop diagnostics, and the representation bookkeeping of the Standard Model.

Read this chapter when you understand QED and want to learn what changes when $U(1)$ is replaced by a compact non-Abelian Lie group such as $SU(N)$.

$$
\text{Yang–Mills theory}
=
\text{gauge principle}
+
\text{noncommuting generators}
+
\text{self-interacting gauge bosons}.
$$

## Prerequisites

You should know [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
\psi\mapsto U^{-1}\psi.
$$

You should also have read the Gauge Principle chapter through [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/) and the QED chapter through [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/). The essential QED lessons are: gauge potentials are redundant, gauge fixing is not physics, covariant derivatives carry the charge convention, and Ward identities protect gauge-independent observables.

The mathematical prerequisites are modest but important: Lie-algebra generators, commutators, structure constants, traces, and representations. The chapter reviews the required group-theory factors when they first appear.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/) | The finite and infinitesimal transformation laws for matter fields, connections, covariant derivatives, and curvature. |
| 2 | [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) | The gauge-invariant kinetic term $-\frac14F_{\mu\nu}^aF^{a\mu\nu}$, equations of motion, Bianchi identity, and conserved-current caveats. |
| 3 | [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/) | The nonlinear curvature $F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu]$ and its component signs in the volume convention. |
| 4 | [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/) | How the same gauge field acts on fundamental, antifundamental, adjoint, singlet, tensor-product, scalar, and spinor matter. |
| 5 | [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/) | Why the Yang–Mills kinetic term contains three- and four-gauge-boson vertices before any matter is added. |
| 6 | [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/) | The $SU(3)$ representation language needed for QCD: triplets, antitriplets, octets, Casimirs, Dynkin index, and color flow. |
| 7 | [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) | Why the Lie algebra is not always the whole gauge group, and how center symmetry and line operators remember global information. |

After this path, you should be able to translate between matrix and component notation, check gauge covariance of a formula, write the Yang–Mills action, identify where self-interactions come from, and recognize which statements are local Lie-algebra facts rather than global facts about the gauge group.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| $[T^a,T^b]=if^{abc}T^c$ | Noncommuting generators define the local Lie algebra. | Produces nonlinear transformations, gauge-boson self-interactions, and adjoint charges. |
| $A_\mu=A_\mu^aT^a$ | The gauge field is a Lie-algebra-valued connection. | Lets $D_\mu$ compare fields in different internal frames. |
| $A_\mu\mapsto U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U$ | Finite non-Abelian gauge transformation in the volume convention. | The inhomogeneous derivative term makes $D_\mu\psi$ transform covariantly. |
| $[D_\mu,D_\nu]=igF_{\mu\nu}$ | Curvature definition of the field strength. | Fixes all signs in $F_{\mu\nu}^a$, the action, and later Feynman rules. |
| $F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U$ | The non-Abelian field strength is covariant, not invariant. | Local gauge-invariant operators require traces or contracted matter fields. |
| $\mathcal L_{\mathrm{YM}}=-\frac14F_{\mu\nu}^aF^{a\mu\nu}$ | Gauge-field kinetic term for generators normalized by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. | Source of three- and four-gauge-boson vertices. |
| Adjoint representation | The representation carried by gauge bosons and ghosts. | Central for QCD, gauge fixing, beta functions, and color factors. |
| Center of the gauge group | Global information invisible in the local Lie algebra. | Controls line operators, one-form symmetries, confinement diagnostics, and global forms of the Standard Model gauge group. |

## Common confusions

**Non-Abelian does not mean merely “many photons.”** A product gauge group such as $U(1)^k$ has several gauge bosons but is still Abelian. Non-Abelian means the generators do not commute, so $f^{abc}\ne0$ in some basis.

**The field strength is not gauge invariant as a matrix.** In QED, $F_{\mu\nu}$ is invariant. In Yang–Mills theory, $F_{\mu\nu}$ transforms by conjugation. Gauge-invariant local quantities are built from traces such as $\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})$ or from gauge-invariant contractions with matter fields.

**Gauge bosons are charged, but not under an ordinary global color charge.** The gauge field transforms in the adjoint representation under changes of local frame. The associated local redundancy is not an ordinary physical symmetry. Later pages distinguish carefully between gauge covariance, global remnants, boundary charges, and center symmetries.

**The same symbol $T^a$ means different matrices in different representations.** A quark, an antiquark, a gluon, a Higgs doublet, and a singlet do not all see the same matrix. They see the generator in their own representation.

**The coupling convention is tied to the gauge parameter convention.** Here $U(x)=\exp\{ig\alpha^a(x)T^a\}$ and $D_\mu=\partial_\mu+igA_\mu$. If another source uses $D_\mu=\partial_\mu-igA_\mu$, several signs in transformation laws and $F_{\mu\nu}^a$ flip.

**Local Lie algebra is not the global gauge group.** $SU(N)$ and $SU(N)/\mathbb Z_N$ have the same Lie algebra but different line-operator spectra and global one-form symmetry structure. This chapter begins locally; the last page introduces the global-form caveat.

## Boundaries

This chapter does:

- define non-Abelian gauge transformations in the volume convention;
- construct the Yang–Mills field strength and action;
- explain how curvature, covariant derivatives, and representations fit together;
- show why gauge bosons self-interact;
- introduce the representation data needed for QCD and Standard Model gauge factors;
- preview global form and center symmetry as local formulas become insufficient.

This chapter does not try to do:

- quantize Yang–Mills theory or derive Faddeev–Popov ghosts;
- prove perturbative renormalizability;
- compute the one-loop Yang–Mills beta function;
- solve confinement, mass gap, chiral symmetry breaking, or theta-vacuum physics;
- build the full Standard Model Lagrangian;
- treat anomalies in chiral gauge theories.

Those topics belong to Gauge Quantization, Gauge Renormalization, Wilson Loops and Confinement, QCD, Standard Model Architecture, and Standard Model Anomalies.

## Where to go next

On a linear path, start with [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), then proceed through [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/) and [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/), then continue through [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/), [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/), [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/), and [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/). The next conceptual chapter is [Gauge Quantization](/gauge-theories-standard-model/gauge-quantization/), where non-Abelian gauge redundancy forces the Faddeev–Popov determinant, ghost fields, BRST symmetry, and Slavnov–Taylor identities.

For the physical Standard Model path, continue from this chapter to QCD for $SU(3)_c$, Electroweak Theory for $SU(2)_L\times U(1)_Y$, and Standard Model Architecture for the synthesis.

For nonperturbative physics, pair this chapter with Wilson Loops, Phases, and Confinement and the Nonperturbative QFT volume.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§69–73, for non-Abelian gauge theory, group representations, path-integral quantization, Feynman rules, and the Yang–Mills beta function.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for gauge invariance, Wilson lines, Yang–Mills theory, gluon propagators, color factors, and running coupling.
- Zee, *Quantum Field Theory in a Nutshell*, especially the non-Abelian gauge theory and grand-unification chapters, for physical intuition and compact derivations.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for a systematic treatment of non-Abelian gauge invariance, field equations, constraints, Faddeev–Popov quantization, ghosts, and BRST symmetry.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic conceptual route through gauge fields and the Higgs phenomenon.
- Polyakov, *Gauge Fields and Strings*, especially Chs. 1–3 and 7–8, for the geometric and nonperturbative viewpoint on gauge fields, loops, strong coupling, and large-$N$ ideas.

## Version history

- **2026-06-17:** Linked the Yang–Mills chapter forward to Gauge Quantization.
- **2026-06-17:** Updated the reading path to link the Color and Representations and Global Form and Center pages.
- **2026-06-17:** Updated the reading path to link the Covariant Derivative in Representations and Gauge-Boson Self-Interactions pages.
- **2026-06-17:** Updated the reading path to link the Yang–Mills Action and Non-Abelian Field Strength pages.
- **2026-06-17:** Initial chapter overview for the improved Non-Abelian Gauge Theory and Yang–Mills chapter.
