---
title: "Anomalies and Consistency of the Standard Model"
description: "Chapter overview for gauge anomalies, anomaly cancellation, hypercharge assignments, mixed gauge–gravitational anomalies, the global SU(2) anomaly, and baryon/lepton-number anomalies in the Standard Model."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77 and §§87–91; Schwartz Ch. 30; Burgess Ch. 9; Weinberg Vol. II anomaly and Standard Model material."
topics:
  - gauge anomalies
  - Standard Model anomaly cancellation
  - chiral gauge theory
  - hypercharge
  - mixed gauge-gravitational anomaly
  - global SU(2) anomaly
  - baryon and lepton number anomalies
canonicalTopics:
  - gauge-anomalies
  - standard-model-anomaly-cancellation
  - hypercharge-assignments
  - mixed-gauge-gravitational-anomalies
  - global-su2-anomaly
  - baryon-lepton-number-anomalies
researchStatus:
  established:
    - "The observed one-generation Standard Model fermion representation content cancels all perturbative gauge anomalies and also passes the global SU(2) consistency test."
  active:
    - "Modern anomaly language extends beyond the perturbative triangle calculation to global anomalies, higher-form symmetries, anomaly inflow, and constraints on possible ultraviolet completions."
---

Anomalies and Consistency is the chapter in the Gauge Theories and the Standard Model volume where the chiral Standard Model is tested as a quantum gauge theory. A classical gauge symmetry can fail after quantization. If that happens for a dynamical gauge symmetry, the theory is not merely inelegant; it is inconsistent.

The surprise is that the Standard Model passes. Its fermions are arranged so that the dangerous gauge anomalies cancel generation by generation. That cancellation links color, weak isospin, hypercharge, quarks, and leptons in a way that is much deeper than a particle list.

The chapter also separates two ideas that are often blurred. **Gauge anomalies** must vanish. **Global-current anomalies** can be physical and informative. The Standard Model has both: gauge-anomaly cancellation makes the theory consistent, while baryon and lepton number anomalies explain why classical accidental symmetries are not exact quantum symmetries.

$$
\text{chiral fermions}
\quad\xrightarrow{\text{quantization}}\quad
\text{possible anomalies}
\quad\xrightarrow{\text{cancellation tests}}\quad
\text{consistent gauge theory}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model anomaly consistency map](/figures/gauge-theories-standard-model/standard-model-anomaly-consistency-map.svg)

<figcaption>

Anomaly cancellation is a quantum consistency filter. The Standard Model must cancel perturbative gauge anomalies, mixed gauge–gravitational anomalies, and the global $SU(2)$ anomaly. Global-current anomalies such as $B+L$ violation are different: they are physical selection-rule violations, not failures of gauge consistency.

</figcaption>
</figure>

## Prerequisites

You should know the [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/), [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/), [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/), [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/), and [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/). You should also be comfortable with traces of group generators and with rewriting right-handed fermions as left-handed conjugate fields.

This chapter uses the volume convention $Q=T^3+Y$. For anomaly calculations it is cleanest to use the all-left-handed one-generation ledger

$$
\begin{array}{c|c}
\text{left-handed Weyl field} & SU(3)_c\times SU(2)_L\times U(1)_Y \\
\hline
Q_L & (\mathbf3,\mathbf2)_{1/6}\\
u_L^c & (\overline{\mathbf3},\mathbf1)_{-2/3}\\
d_L^c & (\overline{\mathbf3},\mathbf1)_{1/3}\\
L_L & (\mathbf1,\mathbf2)_{-1/2}\\
e_L^c & (\mathbf1,\mathbf1)_{1}
\end{array}
$$

Here $u_L^c,d_L^c,e_L^c$ denote left-handed charge-conjugate fields associated with the usual right-handed charged fermions. The minimal Standard Model contains no right-handed neutrino singlet.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) | The basic quantum obstruction: why a classical gauge current can fail to remain conserved after quantization. |
| 2 | [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) | The explicit Standard Model cancellation checks for $SU(3)$, $SU(2)$, $U(1)_Y$, and mixed anomalies. |
| 3 | [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/) | How anomaly cancellation, Yukawa couplings, and electric-charge assignments constrain the hypercharge pattern. |
| 4 | [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) | Why coupling the theory to background geometry tests the sum of hypercharges. |
| 5 | [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/) | The nonperturbative consistency check that the number of left-handed $SU(2)$ doublets must be even. |
| 6 | [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/) | Why $B$ and $L$ are accidental at dimension four but anomalous nonperturbatively, while $B-L$ is special. |

The first three pages are the perturbative triangle-anomaly spine. The mixed gravitational page completes the local trace tests. The last two pages explain two different nonperturbative/global phenomena: the fatal Witten anomaly for an odd number of weak doublets, and the physical $B+L$ anomaly of the Standard Model’s accidental global currents.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| chiral gauge theory | Left- and right-handed fermions transform differently under the gauge group. | Chiral theories are where gauge anomalies can appear. |
| $\partial_\mu J^\mu\ne0$ | A classically conserved current may fail quantum mechanically. | For a gauge current this destroys consistency; for a global current it can be physical. |
| $\operatorname{tr}_R(T^a\{T^b,T^c\})$ | The perturbative anomaly coefficient for non-Abelian gauge currents. | Its sum over left-handed Weyl fermions must vanish for every gauged current. |
| $[SU(3)_c]^2U(1)_Y$ | Mixed color–hypercharge anomaly. | Cancels because $2(1/6)-2/3+1/3=0$ per generation. |
| $[SU(2)_L]^2U(1)_Y$ | Mixed weak-isospin–hypercharge anomaly. | Cancels because $3(1/6)-1/2=0$ per generation. |
| $[U(1)_Y]^3$ | Cubic hypercharge anomaly. | Gives the most sensitive check of all hypercharge assignments and multiplicities. |
| gravitational–hypercharge anomaly | Mixed anomaly with two stress tensors and one hypercharge current. | Cancels because the total hypercharge over left-handed Weyl fields vanishes. |
| global $SU(2)$ anomaly | A nonperturbative sign obstruction for an odd number of left-handed doublets. | One Standard Model generation has $3+1=4$ weak doublets, so it passes. |
| $B+L$ anomaly | Anomaly of an accidental global current, not of a gauge current. | Explains electroweak violation of $B+L$ and preservation of $B-L$ in the minimal theory. |

The landmark to keep in your pocket is this: anomaly cancellation is not optional ornamentation. It is one of the quantum consistency conditions that turns a formal chiral Lagrangian into a possible theory.

## Common confusions

**An anomaly is not always bad.** A gauge anomaly is fatal because gauge symmetry is redundancy. A global anomaly in a global current can be a real physical effect, such as the axial anomaly or electroweak $B+L$ violation.

**Gauge-anomaly cancellation is not the same as total electric charge cancellation.** The relevant sums involve representation indices, chirality, multiplicities, and powers of hypercharge. Electric charge neutrality is not the criterion.

**Right-handed fields contribute with conjugate data only after rewriting them as left-handed fields.** Many sign mistakes come from summing $u_R$ and $u_L$ as if they were the same kind of object.

**The global $SU(2)$ anomaly is not a triangle diagram.** It is a genuinely global effect tied to the topology of the gauge group. The even-number-of-doublets rule is not visible from the local cubic trace alone.

**Anomaly cancellation does not explain every Standard Model charge by itself.** It is powerful, especially combined with Yukawa couplings and electric-charge quantization, but normalization choices and global-form data still need careful treatment.

## Boundaries

This chapter does:

- explain why gauge anomalies are consistency conditions for chiral gauge theories;
- compute the Standard Model anomaly-cancellation conditions in one generation;
- clarify the role of hypercharge assignments;
- distinguish perturbative triangle anomalies from global anomalies;
- explain why baryon and lepton number are anomalous global symmetries, not exact gauge symmetries;
- prepare the reader for precision Standard Model and SMEFT consistency checks.

This chapter does not try to:

- give a full classification of anomalies in all dimensions;
- replace the Symmetry, Anomalies, and Topology volume;
- develop anomaly inflow, cobordism, or higher-form symmetry in full generality;
- classify grand unified theories;
- compute every anomaly coefficient in every convention used in the literature;
- turn anomaly cancellation into a numerology contest. The universe already has enough of those.

## Where to go next

Start with [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/). It explains the obstruction before the Standard Model miracle is put on stage.

After this chapter, continue to the [Model Calculation Library](/gauge-theories-standard-model/calculation-library/) for explicit derivations and consistency checks, or to the Symmetry, Anomalies, and Topology volume for the modern anomaly viewpoint involving inflow, generalized symmetries, defects, and global anomaly classification.

For a Standard-Model-facing route, return to [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) and then follow the EFT handoff to neutrino mass, proton decay, and higher-dimensional operators.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomaly, BRST, and Standard Model sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the anomaly chapter and the weak-interaction chapter.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model EFT chapter and its anomaly-cancellation discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and anomaly constraints in a broad field-theoretic setting.
- Coleman, *Aspects of Symmetry*, especially the lectures on symmetry, currents, Ward identities, and spontaneous symmetry breaking.
- Reviews on global anomalies and anomaly inflow for the modern topological viewpoint beyond perturbative triangle diagrams.

## Version history

- **2026-06-19:** Linked the completed Anomalies and Consistency chapter forward into the Model Calculation Library.
- **2026-06-19:** Added Global SU(2) Anomaly and Baryon and Lepton Number Anomalies, completing the first-pass Anomalies and Consistency chapter arc.
- **2026-06-19:** Added Hypercharge Assignments and Mixed Gauge–Gravitational Anomalies, completing the perturbative local anomaly spine before the global SU(2) and baryon/lepton-number pages.
- **2026-06-19:** Added the first two ordinary pages: Gauge Anomalies in Chiral Theories and Anomaly Cancellation in One Generation.
- **2026-06-19:** Initial chapter overview for Anomalies and Consistency, including the reading path from perturbative gauge anomalies to Standard Model baryon/lepton-number anomalies.
