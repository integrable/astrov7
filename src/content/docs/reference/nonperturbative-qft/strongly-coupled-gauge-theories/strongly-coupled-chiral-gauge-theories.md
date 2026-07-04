---
title: "Strongly Coupled Chiral Gauge Theories"
description: "Explains what makes chiral gauge theories nonperturbatively subtle, including anomaly cancellation, anomaly matching, lattice obstructions, and possible infrared phases."
sidebar:
  label: "Chiral Gauge Theories"
  order: 8
level: Advanced
status: "Polished draft"
source: "Srednicki; Weinberg; Schwartz; Coleman; Shifman; Lüscher; Eichten–Preskill; modern lattice chiral gauge theory literature."
topics:
  - chiral gauge theories
  - gauge anomalies
  - anomaly matching
  - lattice chiral fermions
  - mirror fermions
  - symmetric mass generation
  - chiral confinement
  - strongly coupled gauge dynamics
canonicalTopics:
  - nonperturbative-qft
  - strongly-coupled-gauge-theories
  - chiral-gauge-theories
  - anomalies
  - lattice-fermions
  - gauge-theory-phases
researchStatus:
  established:
    - "Perturbative gauge-anomaly cancellation, global-anomaly constraints, and ’t Hooft anomaly matching are necessary consistency tests for chiral gauge theories."
  active:
    - "A fully practical nonperturbative construction and classification of general four-dimensional chiral gauge theories remains an active area, especially for lattice formulations and strongly coupled infrared phases."
---

## Summary

A **chiral gauge theory** is a gauge theory in which the left-handed and right-handed fermions transform differently under the gauge group. Equivalently, after writing all fermions as left-handed Weyl fields, the representation content is not paired into $R\oplus \bar R$ in a way that permits gauge-invariant Dirac masses for every fermion. The Standard Model is the most important example.

Chiral gauge theories are not just vectorlike gauge theories with fewer mass terms. They are more fragile. A vectorlike theory such as QCD can often be regulated while preserving exact gauge invariance and a positive Euclidean measure. A genuinely chiral gauge theory must satisfy anomaly-cancellation conditions before it even has a chance to exist as a quantum gauge theory, and its nonperturbative definition is much harder.

The first consistency condition is the absence of gauge anomalies. In a four-dimensional theory with left-handed Weyl fermions in representations $R_i$ of a simple gauge group, the perturbative cubic anomaly is proportional to

$$
\sum_i A(R_i),
$$

where

$$
\operatorname{tr}_{R_i}\!\left(T^a\{T^b,T^c\}\right)
=A(R_i)d^{abc}.
$$

A chiral gauge theory can still have global symmetries with ’t Hooft anomalies. Those are not inconsistencies; they are infrared constraints. If the theory confines, breaks symmetry, flows to a conformal fixed point, or develops topological order, the infrared must reproduce the same global anomalies.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A map of the consistency and dynamics of a chiral gauge theory: chiral matter must pass local and global gauge-anomaly tests before possible infrared phases such as confinement, symmetry breaking, massless composites, conformality, or symmetric mass generation can be considered.](/figures/nonperturbative-qft/chiral-gauge-theory-ir-constraints.svg)

<figcaption>

A chiral gauge theory has two layers of difficulty. First, gauge consistency is nonnegotiable: perturbative and global gauge anomalies must vanish. Second, once the theory exists, its infrared dynamics is constrained but usually not determined by anomalies, symmetries, and available nonperturbative methods.

</figcaption>
</figure>

The point of this page is to separate those two layers. **Gauge anomalies decide whether the theory can be gauged. Global anomalies and dynamics decide what the theory can become.**

## Prerequisites

Read [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/), [Conformal Window Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/conformal-window-preview/), [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/), [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/), and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) before this page.

You should know the difference between gauge redundancy and global symmetry. Gauge anomalies are fatal; global ’t Hooft anomalies are data.

## Core idea

The fastest way to understand chiral gauge theories is by comparing three questions.

| Question | Kind of question | Typical tool |
|---|---|---|
| Can the symmetry be gauged? | Consistency | Perturbative and global gauge-anomaly cancellation. |
| What global symmetries remain? | Exact structure | Charges, instantons, mixed anomalies, anomaly matching. |
| What happens in the infrared? | Dynamics | Lattice methods, large-$N$, semiclassics in special regimes, dualities, bootstrap constraints, effective theory. |

In vectorlike QCD, the microscopic quarks can receive gauge-invariant masses, and the Euclidean lattice formulation is conceptually straightforward. In a chiral gauge theory, forbidding unwanted mirror fermions while preserving gauge invariance is part of the problem. This is why chiral gauge theory is a stress test for any proposed nonperturbative definition of QFT.

The infrared possibilities are also richer. A strongly coupled chiral gauge theory may confine and produce massless composite fermions, break global symmetries, flow to an interacting CFT, Higgs itself through condensates, produce a gapped symmetric phase by more subtle interactions, or fail because a hidden anomaly was overlooked.

## Setup and conventions

We work in four-dimensional flat spacetime unless stated otherwise. All fermions are written as left-handed Weyl fermions

$$
\psi_i \in R_i,
$$

where $R_i$ is a representation of the gauge group $G$. A theory is **vectorlike** if the representation content can be organized into pairs $R\oplus \bar R$ so that gauge-invariant Dirac masses are allowed. A theory is **chiral** if some fermions cannot be paired this way.

For a compact simple group, the perturbative gauge anomaly is encoded in the triangle coefficient

$$
\mathcal A^{abc}
=\sum_i \operatorname{tr}_{R_i}\!\left(T^a\{T^b,T^c\}\right).
$$

The necessary perturbative condition is

$$
\mathcal A^{abc}=0
$$

for all gauge generators. For Abelian factors, one also checks cubic and mixed anomalies, for example

$$
\sum_i q_i^3=0,
\qquad
\sum_i q_i=0
$$

for a single $U(1)$, where the second condition is the mixed gauge–gravity anomaly.

Perturbative cancellation is not the whole story. Some groups have **global gauge anomalies** invisible in the triangle diagram. The standard example is the four-dimensional $SU(2)$ anomaly: an odd number of left-handed Weyl doublets is inconsistent. In modern language, global anomalies are often classified using topology of gauge fields and fermion determinant phases. This page uses only the practical lesson: local anomaly cancellation is necessary, not automatically sufficient.

## Gauge anomalies are obstructions

A gauge anomaly means the path integral cannot be made invariant under gauge transformations. In a theory with gauge field $A$ and fermions $\psi_i$, the formal fermion integration produces

$$
Z[A]=\int \prod_i D\psi_i\,D\bar\psi_i\,e^{iS[\psi_i,A]}.
$$

Gauge invariance requires

$$
Z[A^g]=Z[A].
$$

If the fermion measure transforms with a nontrivial phase under a gauge transformation,

$$
Z[A^g]=e^{i\alpha[g,A]}Z[A],
$$

then gauge-equivalent configurations are assigned different weights. That is not a symmetry breaking pattern. It is not a small correction. It is an inconsistency in the proposed gauge theory.

This is why anomaly cancellation is not optional model-building hygiene. It is part of the definition of the theory. A chiral gauge theory that fails this test is not a quantum gauge theory with unusual infrared dynamics; it is not a gauge theory.

For non-Abelian simple groups such as $SU(N)$ with $N\ge 3$, the cubic anomaly is often the first check. If $A(\square)=1$ and $A(\bar\square)=-1$, then a vectorlike pair $\square\oplus\bar\square$ cancels automatically. Chiral theories require more interesting cancellations, such as antisymmetric representations combined with antifundamentals.

## Global anomalies are infrared constraints

Now switch from gauge symmetries to genuine global symmetries. A global ’t Hooft anomaly means that the global symmetry cannot be gauged consistently as a background symmetry, or equivalently that its partition function transforms anomalously under background-field gauge transformations. Unlike gauge anomalies, global anomalies are allowed.

They are powerful because they are invariant under RG flow. If the ultraviolet theory has a global anomaly, the infrared theory must reproduce it. This is **’t Hooft anomaly matching**.

For a global symmetry $H$, imagine coupling to a nondynamical background gauge field $B$. If the UV generating functional transforms as

$$
Z_{\rm UV}[B^h]
=e^{i\alpha[h,B]}Z_{\rm UV}[B],
$$

then the IR generating functional must have the same anomalous phase:

$$
Z_{\rm IR}[B^h]
=e^{i\alpha[h,B]}Z_{\rm IR}[B].
$$

The infrared has several ways to do this:

| Infrared behavior | How the anomaly is matched |
|---|---|
| Massless composite fermions | Composite fermions carry global charges with the same anomaly. |
| Spontaneous symmetry breaking | Goldstone modes and Wess–Zumino terms reproduce the anomaly. |
| Interacting CFT | Local operators and currents realize the anomalous symmetry. |
| Topological order | A topological sector carries the anomaly, often through anomaly inflow. |
| Symmetry explicitly broken | The anomaly constraint applies only to the unbroken exact symmetry. |

Anomaly matching is a constraint, not a solution algorithm. It can rule out a trivially gapped symmetric phase, but it usually does not uniquely determine the infrared theory.

## Why chiral theories are harder than QCD

QCD with massless quarks is chiral in its **global** flavor symmetry, but vectorlike in its **gauge** interactions. Left- and right-handed quarks transform the same way under color. This permits a gauge-invariant lattice regulator and gauge-invariant mass terms.

A chiral gauge theory is different. The gauge interaction itself distinguishes chirality. A gauge-invariant mass term may be forbidden. The fermion determinant is not generally positive. The regulator must preserve gauge invariance without accidentally introducing mirror fermions that turn the theory vectorlike.

This creates three nonperturbative challenges.

First, the theory must be defined at finite cutoff without breaking the gauge symmetry that it is trying to gauge. Gauge symmetry is not merely an aesthetic feature; it removes unphysical states and controls locality and unitarity.

Second, the regulator must represent chiral fermions correctly. Naive lattice fermions produce doublers, and the doubling theorem obstructs a simple local, translationally invariant, chirally symmetric lattice fermion action of the naive kind.

Third, any extra mirror degrees of freedom must decouple without breaking the target gauge symmetry or changing the infrared theory. Mirror decoupling sounds easy until one remembers that strongly interacting mirror sectors may carry anomalies, global charges, or topological obstructions.

## Nonperturbative regulators and mirror sectors

The modern lattice story has several intertwined ideas.

**Ginsparg–Wilson and overlap fermions.** The Ginsparg–Wilson relation modifies chiral symmetry at finite lattice spacing in a way that becomes ordinary chiral symmetry in the continuum. Overlap and domain-wall constructions make chiral anomaly physics geometrically visible and have been crucial for vectorlike theories with good chiral symmetry. For genuinely chiral gauge theories, they help organize the problem but do not make every theory automatically practical.

**Gauge-invariant fermion measures.** Even after choosing a chiral lattice Dirac operator, one must define a fermion measure whose phase varies correctly and locally over gauge-field configuration space. In anomaly-free cases, this can be done in important classes of theories, but the construction is subtle.

**Mirror-fermion decoupling.** Another strategy begins with a vectorlike lattice theory and tries to gap out the unwanted mirror sector using strong interactions, leaving only the desired chiral sector. The obstacle is that a mirror sector cannot be trivially gapped if it carries an uncancelled anomaly for an exact symmetry. This connects chiral lattice gauge theory to modern ideas about symmetric mass generation and topological phases.

**Gauge fixing and noninvariant regulators.** Some approaches regulate the theory in a way that breaks gauge invariance at intermediate steps, then attempt to recover gauge invariance after counterterms and continuum limits. This can work in perturbative settings but is delicate nonperturbatively.

The conceptual checkpoint is simple: an acceptable regulator must produce a local, unitary, gauge-invariant continuum theory with the desired chiral matter and no unintended light mirror sector.

## Possible infrared phases

Strongly coupled chiral gauge theories do not have a single QCD-like default phase. The possibilities include:

| IR behavior | What it means | Typical diagnostic |
|---|---|---|
| Confinement with massless composites | Gauge-charged fields disappear, but composite fermions remain massless. | Anomaly matching and candidate composite operators. |
| Confinement with symmetry breaking | Gauge dynamics forms condensates that break global symmetries. | Order parameters, Goldstone counting, Wess–Zumino terms. |
| Higgs phase | Gauge symmetry is Higgsed by scalar fields or fermion bilinears in a gauge-noninvariant description. | Gauge-invariant spectrum, complementarity checks. |
| Interacting CFT | The theory flows to a nontrivial scale-invariant fixed point. | Scaling dimensions, conformal data, finite-size scaling. |
| Symmetric mass generation | Fermions become massive without a bilinear condensate and without breaking the target symmetry. | Absence of anomaly obstruction, gapped symmetric spectrum. |
| Topological phase | A gapped sector with long-range topological data matches anomalies. | Ground-state degeneracy, topological response, anomaly inflow. |

The phrase “chiral confinement” is sometimes used for the first option: the gauge theory confines, but the infrared contains massless composite fermions because global anomaly matching forbids a trivial massive phase. The classic attraction of this possibility is that it would produce massless fermions dynamically, without elementary scalars. The challenge is that the actual dynamics of four-dimensional chiral gauge theories is hard to control.

## A canonical family of checks

A serious proposed chiral gauge theory should pass a checklist before one speculates about its phase diagram.

| Check | Why it matters |
|---|---|
| Perturbative gauge anomalies vanish | Otherwise the gauge theory is inconsistent. |
| Global gauge anomalies vanish | Otherwise large gauge transformations or nontrivial bundles obstruct the theory. |
| Mixed gauge–gravity anomalies vanish for gauged symmetries | Otherwise coupling to gravity or curved backgrounds is inconsistent. |
| Exact global symmetries are identified | These are the symmetries whose anomalies constrain the IR. |
| Instanton-induced symmetry violation is included | Some classical global symmetries are not quantum symmetries. |
| Candidate mass terms and condensates are classified | Determines what phases are possible without explicit breaking. |
| ’t Hooft anomalies of global symmetries are computed | Constrains massless composites, Goldstone modes, or topological order. |
| Regulator degrees of freedom are controlled | Prevents accidental vectorlike completion by mirror sectors. |

This checklist does not solve the theory. It prevents false starts.

## Example: anomaly-free does not mean vectorlike

Consider $SU(5)$ with left-handed Weyl fermions in

$$
\mathbf{10}\oplus \bar{\mathbf 5}.
$$

For $SU(5)$, the two-index antisymmetric representation $\mathbf{10}$ has cubic anomaly coefficient

$$
A(\mathbf{10})=1,
$$

while

$$
A(\bar{\mathbf 5})=-1.
$$

Thus the perturbative gauge anomaly cancels:

$$
A(\mathbf{10})+A(\bar{\mathbf 5})=0.
$$

The theory is nevertheless chiral: there is no gauge-invariant fermion mass term pairing all fields into $R\oplus\bar R$. This example is important because it separates two ideas that students often conflate:

$$
\text{anomaly-free}
\quad \not\Rightarrow \quad
\text{vectorlike}.
$$

A theory can be chiral and consistent. The hard question is what it does in the infrared.

## Relation to the Standard Model

The Standard Model is a chiral gauge theory with gauge group locally

$$
SU(3)\times SU(2)\times U(1).
$$

Its gauge anomalies cancel in a highly nontrivial way among quarks and leptons in each generation. This cancellation is one of the deepest consistency checks on the pattern of Standard Model charges. It is not a nonperturbative prediction of QCD; it is a quantum consistency condition on the electroweak and color gauge theory itself.

At the same time, the Standard Model contains vectorlike strong dynamics. QCD is vectorlike under color, even though the full electroweak theory is chiral. This is why lattice QCD is vastly more mature than a fully chiral lattice formulation of the entire Standard Model at finite cutoff.

## Common pitfalls

**Calling every Weyl-fermion theory chiral.** A theory written with Weyl fermions may still be vectorlike if the representation content pairs into $R\oplus\bar R$ and admits gauge-invariant masses. Chirality is about gauge representation content, not notation.

**Treating anomaly cancellation as a dynamical phase.** Gauge-anomaly cancellation is a consistency condition before dynamics. It does not say whether the theory confines, breaks symmetry, or flows to a CFT.

**Forgetting global gauge anomalies.** Vanishing triangle anomalies can miss large-gauge-transformation obstructions. The $SU(2)$ odd-doublet anomaly is the standard warning.

**Using anomaly matching backward.** If the UV has a global anomaly, the IR must match it. But many different IR phases can match the same anomaly, so anomaly matching rarely gives a unique answer.

**Assuming mirror fermions are harmless because they are heavy.** In a chiral lattice construction, making mirror fermions heavy without breaking the target gauge symmetry is the main problem, not a detail.

**Confusing chiral gauge theories with chiral symmetry breaking in QCD.** Massless QCD has chiral global flavor symmetries, but its color gauge coupling is vectorlike. Genuinely chiral gauge dynamics is a different problem.

## Relations to other pages

- [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/) is the vectorlike benchmark; this page explains what changes when the gauge theory itself is chiral.
- [Chiral Symmetry Breaking](/nonperturbative-qft/strongly-coupled-gauge-theories/chiral-symmetry-breaking/) treats chiral symmetry as a global symmetry of QCD-like theories, not as gauge chirality.
- [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) explain how topology produces anomalous selection rules.
- [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/) is a different frontier: near-conformal vectorlike or gauge-matter dynamics.
- [Nonperturbative Standard Model Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/nonperturbative-standard-model-preview/) applies these lessons to the actual chiral gauge theory of known particles.

## Research status

The perturbative anomaly-cancellation rules for four-dimensional chiral gauge theories are textbook-standard. The existence and importance of global gauge anomalies and ’t Hooft anomaly matching are also established.

The frontier is nonperturbative construction and classification. There has been major progress using overlap fermions, domain-wall ideas, Ginsparg–Wilson relations, mirror-fermion strategies, anomaly inflow, and topological phases. Still, a broadly practical lattice formulation for arbitrary four-dimensional chiral gauge theories is not in the same mature state as lattice QCD. The dynamics of many strongly coupled chiral gauge theories also remains poorly controlled compared with QCD-like vectorlike theories.

A useful attitude is: consistency constraints are sharp; infrared dynamics is case-by-case.

## Exercises

### Exercise 1: Vectorlike cancellation

Let a four-dimensional $SU(N)$ gauge theory contain one left-handed Weyl fermion in $R$ and one left-handed Weyl fermion in $\bar R$. Show that the perturbative cubic gauge anomaly cancels.

<details>
<summary><strong>Solution</strong></summary>

The anomaly coefficient changes sign under complex conjugation:

$$
A(\bar R)=-A(R).
$$

Therefore

$$
A(R)+A(\bar R)=0.
$$

The pair $R\oplus\bar R$ is vectorlike: the two Weyl fermions can be combined into a Dirac fermion, and a gauge-invariant mass term is allowed if no extra symmetry forbids it.

</details>

### Exercise 2: Anomaly-free need not mean vectorlike

Use the quoted $SU(5)$ anomaly coefficients

$$
A(\mathbf{10})=1,
\qquad
A(\bar{\mathbf 5})=-1
$$

 to show that $\mathbf{10}\oplus\bar{\mathbf 5}$ is perturbatively anomaly-free. Why does this not prove that the theory is vectorlike?

<details>
<summary><strong>Solution</strong></summary>

The total cubic gauge anomaly is

$$
A_{\rm total}=A(\mathbf{10})+A(\bar{\mathbf 5})=1-1=0.
$$

Thus the perturbative $SU(5)^3$ anomaly cancels. The theory is still chiral because the representations do not come in conjugate pairs that allow gauge-invariant Dirac masses for all fermions. The conjugate of $\mathbf{10}$ is $\bar{\mathbf{10}}$, not $\bar{\mathbf 5}$.

</details>

### Exercise 3: Matching a global anomaly

Suppose a chiral gauge theory confines and preserves a global symmetry $H$. The UV theory has a nonzero $H^3$ ’t Hooft anomaly. Explain why a completely trivial gapped infrared theory is impossible.

<details>
<summary><strong>Solution</strong></summary>

A trivial gapped theory with a unique vacuum and no topological sector has no massless degrees of freedom, no Goldstone modes, and no topological response that could reproduce an anomalous transformation of the background $H$ gauge field. But ’t Hooft anomalies are RG invariant. Therefore the IR must contain something that matches the anomaly: massless composites, spontaneous symmetry breaking with Wess–Zumino terms, an interacting CFT, or topological order.

</details>

### Exercise 4: Gauge anomaly versus global anomaly

Explain why a gauge anomaly is fatal but a global ’t Hooft anomaly is useful data.

<details>
<summary><strong>Solution</strong></summary>

A gauge symmetry is a redundancy used to remove unphysical configurations. If the quantum theory is not invariant under gauge transformations, gauge-equivalent configurations receive different weights, and the theory is inconsistent. A global symmetry acts on physical states. Its anomaly means that the symmetry cannot be gauged as a background symmetry without an anomalous phase, but the ungauged theory can still exist. That anomalous phase must be reproduced in the infrared, so it becomes a constraint on possible phases.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for chiral gauge theories, anomalies, and the path-integral treatment of anomalous fermion measures.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for gauge theories, anomalies, and the Standard Model as a chiral gauge theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for a modern treatment of anomalies, gauge consistency, and Standard Model anomaly cancellation.
- S. Coleman, *Aspects of Symmetry*, for anomaly matching, current algebra, and the physical logic of symmetries.

### Deeper references

- E. Witten, “An $SU(2)$ Anomaly,” for the classic global gauge-anomaly example.
- G. ’t Hooft, “Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking,” for anomaly matching as an infrared constraint.
- M. Lüscher, “Exact chiral symmetry on the lattice and the Ginsparg–Wilson relation,” and related work on chiral gauge theories.
- E. Eichten and J. Preskill, “Chiral Gauge Theories on the Lattice,” for mirror-sector ideas.
- M. Golterman, D. B. Kaplan, Y. Shamir, E. Poppitz, Y. Kikukawa, and later lattice chiral-gauge-theory literature for nonperturbative constructions and obstructions.
- Recent work on symmetric mass generation and anomaly inflow for the connection between chiral fermions, mirror decoupling, and topological phases.

## Version history

- **2026-06-27:** Initial polished draft, added after Walking Gauge Theories Preview in the Strongly Coupled Gauge Theories chapter.
