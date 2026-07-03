---
title: "Obstruction to Gauging"
description: "Explains how ’t Hooft anomalies obstruct gauging global symmetries and gives a practical background-field checklist for detecting and repairing the obstruction."
sidebar:
  label: "Obstruction to Gauging"
  order: 4
level: Advanced
status: "Polished draft"
source: "Background-field gauging; finite and continuous gauging; gauge anomalies; anomaly inflow; Wess–Zumino consistency; Gaiotto–Kapustin–Seiberg–Willett; Dijkgraaf–Witten; Srednicki; Schwartz; Weinberg."
topics:
  - obstruction to gauging
  - thooft anomalies
  - background fields
  - gauging global symmetries
  - gauge anomalies
  - anomaly cancellation
  - anomaly inflow
canonicalTopics:
  - obstruction-to-gauging
  - anomaly-cancellation
  - gauging-test
  - background-field-gauging
  - anomaly-inflow
researchStatus:
  established:
    - "A global symmetry can be gauged as a standalone $d$-dimensional theory only when its ’t Hooft anomaly class is trivial for the backgrounds being summed over."
    - "An anomaly may be cancelled by adding degrees of freedom with the opposite anomaly or by placing the theory on the boundary of an appropriate invertible bulk theory."
  active:
    - "The obstruction-to-gauging viewpoint is being extended and refined for generalized, non-invertible, subsystem, crystalline, fermionic, and categorical symmetries."
---

## Summary

A global symmetry can be **gauged** only if its background-field partition function can be made gauge invariant. A **’t Hooft anomaly** is exactly the obstruction to doing this.

For a theory $\mathcal T$ with global symmetry $G$, first couple $G$ to background fields $A$ and write $Z_{\mathcal T}[A]$. Gauging means promoting $A$ from a probe to a summed-over variable. For a continuous symmetry, the schematic gauged partition function is

$$
Z_{\mathcal T/G}
=\int \frac{\mathcal D A}{\operatorname{Vol}\mathcal G}
\,e^{iS_{\rm gauge}[A]}Z_{\mathcal T}[A].
$$

For a finite symmetry, it is a groupoid sum over background bundles:

$$
Z_{\mathcal T/G}[M_d]
=\sum_{[A]\in \operatorname{Bun}_G(M_d)}
\frac{1}{|\operatorname{Aut}(A)|}
Z_{\mathcal T}[A].
$$

Both expressions require that isomorphic background configurations have the same weight. If

$$
Z_{\mathcal T}[A^g]
=\exp\!\left(2\pi i\,\mathcal A_g[A]\right)Z_{\mathcal T}[A]
$$

with nontrivial anomaly class $[\mathcal A_G]$, then the gauging sum is not well-defined as a standalone $d$-dimensional QFT.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram comparing anomaly-free gauging, where the partition function descends to gauge-equivalence classes of backgrounds, with anomalous gauging, where a phase prevents a well-defined quotient or sum over backgrounds.](/figures/symmetry-anomalies-topology/obstruction-to-gauging-quotient.svg)

<figcaption>

To gauge a global symmetry, the background-field partition function must descend to gauge-equivalence classes of backgrounds. An anomaly makes it transform by a nontrivial phase, so the quotient integral or finite groupoid sum is not well defined without extra cancelling data.

</figcaption>
</figure>

## Prerequisites

Read [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/), [Anomalies as RG Invariants](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-as-rg-invariants/), [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), and [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/).

You should also know [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), and [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/).

## Core idea

A global symmetry is something we may try to gauge. A ’t Hooft anomaly is the answer “not by itself.”

The operational definition is simple:

1. couple the symmetry to nondynamical background fields;
2. ask whether the partition function is invariant under background gauge transformations;
3. allow local counterterms built from the background fields;
4. if no choice of counterterms makes the answer invariant, the symmetry is anomalous;
5. an anomalous symmetry cannot be gauged as a standalone $d$-dimensional theory.

The obstruction is not a moral flaw of the original theory. A global anomaly is perfectly consistent while the symmetry remains global. The failure appears only when one tries to make the background field dynamical or sum over it.

In one line:

$$
\text{’t Hooft anomaly of }G
=
\text{obstruction to gauging }G.
$$

## Setup and conventions

Let $M_d$ be spacetime and let $G$ be an exact global symmetry of $\mathcal T$. A background field $A$ is shorthand for whatever data are required to couple to $G$: a connection, a flat bundle, a higher-form gauge field, a spin/Pin refinement, or a mixture of these.

For ordinary continuous symmetries, this volume uses Hermitian connections,

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

A background gauge transformation $g$ acts on $A$ and on the background-field partition function as

$$
Z_{\mathcal T}[A^g]
=\exp\!\left(2\pi i\,\mathcal A_g[A]\right)Z_{\mathcal T}[A].
$$

A local background counterterm changes the scheme:

$$
Z_{\mathcal T}[A]
\longmapsto
\exp\!\left(iS_{\rm ct}[A]\right)Z_{\mathcal T}[A].
$$

This shifts the anomaly representative by

$$
\mathcal A_g[A]
\longmapsto
\mathcal A_g[A]
+\frac{1}{2\pi}\left(S_{\rm ct}[A^g]-S_{\rm ct}[A]\right)
\quad\mathrm{mod}\;\mathbb Z.
$$

The obstruction is the equivalence class after all allowed local counterterms are included.

:::note[Convention-sensitive source note]
The word “allowed” is global. A counterterm must be well-defined on every background included in the gauging problem. A differential-form expression that works near the trivial connection may fail on nontrivial bundles, non-spin manifolds, or orientation-reversing backgrounds.
:::

## What gauging requires

Gauging has two conceptually distinct steps.

First, the theory must couple to background $G$ fields. This produces $Z_{\mathcal T}[A]$.

Second, one sums over those background fields, with the appropriate gauge redundancy divided out. At that point, background gauge transformations become redundancies of the new theory.

For a continuous symmetry, the schematic operation is

$$
Z_{\mathcal T/G}
=\int \frac{\mathcal D A}{\operatorname{Vol}\mathcal G}
\,e^{iS_{\rm gauge}[A]}Z_{\mathcal T}[A].
$$

Here $S_{\rm gauge}[A]$ might contain a Yang–Mills term, a Chern–Simons term, a theta term, or no local kinetic term if the gauge field is topological.

For a finite symmetry, there is no local gauge boson. Gauging means summing over flat $G$ bundles:

$$
Z_{\mathcal T/G}[M_d]
=\sum_{[A]\in \operatorname{Bun}_G(M_d)}
\frac{1}{|\operatorname{Aut}(A)|}
Z_{\mathcal T}[A].
$$

The factor $|\operatorname{Aut}(A)|^{-1}$ is the finite-group version of dividing by gauge redundancy. It says that the sum is really a groupoid cardinality, not a naive count of representatives.

Both forms of gauging require

$$
Z_{\mathcal T}[A^g]=Z_{\mathcal T}[A]
$$

after all allowed counterterms have been chosen. If this fails by a nontrivial phase, the path integral assigns different weights to gauge-equivalent configurations. That is not a well-defined gauge theory.

## The finite-group picture

Finite symmetries make the obstruction especially concrete. Suppose $A$ and $A^g$ are isomorphic flat $G$ bundles. In a gauged theory, they represent the same gauge configuration. Therefore their weights in the sum must agree.

If

$$
Z[A^g]=e^{2\pi i\mathcal A_g[A]}Z[A]
$$

with a nontrivial phase, then the groupoid sum depends on the arbitrary representative chosen for each isomorphism class. The gauged partition function is not defined.

A local Dijkgraaf–Witten counterterm can modify the phase. If some counterterm removes the phase for all bundles and gauge transformations, the finite symmetry is gaugeable. If not, the finite symmetry has an ’t Hooft anomaly.

The finite-group obstruction is often described by group cohomology in bosonic cases, for example by a class in something like

$$
H^{d+1}(BG,U(1)),
$$

though this is not the full story for fermionic theories, continuous groups, antiunitary symmetries, higher-form symmetries, or more general modern classifications.

The practical point is independent of classification language:

$$
\text{gauging requires a well-defined sum over background sectors.}
$$

An anomalous phase spoils that sum.

## The continuous-symmetry picture

For a continuous symmetry, gauging promotes the background connection to a dynamical gauge field. A background gauge transformation becomes a gauge redundancy. Redundancy cannot act projectively on the path integral.

If the effective action changes as

$$
\delta_\alpha W[A]
=2\pi\int_{M_d} I_d^{(1)}(\alpha,A),
$$

then the would-be gauged theory has a gauge anomaly unless this variation is cancelled. In BRST language, the anomaly is an obstruction to solving the quantum master equation or maintaining nilpotent BRST symmetry at the quantum level.

For chiral fermions, this reproduces the familiar gauge-anomaly cancellation conditions. A set of left-handed Weyl fermions can be coupled to background gauge fields for a global symmetry even when the background effective action has an anomaly. But if the same symmetry is made dynamical, the anomaly must vanish.

For a four-dimensional gauge group with generators $T_a$, a typical perturbative condition is the vanishing of the symmetric cubic trace

$$
\operatorname{Tr}_{\rm left\;Weyl}\!\left(T_a\{T_b,T_c\}\right)=0
$$

for every triple of dynamical gauge generators, together with mixed gauge-gravitational and global conditions when $U(1)$ factors are present.

The coefficient convention is not the point. The point is that gauge redundancy cannot have a nontrivial ’t Hooft anomaly.

## Gauge anomaly versus ’t Hooft anomaly

The same mathematical expression can be interpreted in two different ways depending on what is dynamical.

| Symmetry being transformed | Field is background or dynamical? | Consequence of nonzero anomaly |
|---|---|---|
| Global symmetry background | Background | Consistent theory, but symmetry cannot be gauged. |
| Gauge redundancy | Dynamical | Inconsistent unless anomaly cancels. |

This is one of the most important distinctions in QFT.

A left-handed Weyl fermion of charge $1$ under a global $U(1)$ has a perfectly good global symmetry and a computable anomaly in background fields. If one tries to gauge that $U(1)$ with only that fermion, the same anomaly becomes a fatal gauge anomaly.

Conversely, the Standard Model is possible because all anomalies involving dynamical gauge redundancies cancel. Some global symmetries of the Standard Model may still have ’t Hooft anomalies. Those are not inconsistencies; they are constraints and diagnostics.

## Counterterms and removable obstructions

A symmetry is gaugeable if the anomaly can be removed by an allowed local counterterm. This is why one should not stop after seeing a nonzero variation of one effective action representative.

Suppose

$$
\delta_g W[A]=2\pi\mathcal A_g[A].
$$

If there exists a local $S_{\rm ct}[A]$ such that

$$
\delta_g S_{\rm ct}[A]
=-2\pi\mathcal A_g[A]
\quad\mathrm{mod}\;2\pi,
$$

then the redefined effective action

$$
W'[A]=W[A]+S_{\rm ct}[A]
$$

is gauge invariant. The apparent anomaly was a scheme choice.

However, the counterterm must obey all quantization and background-geometry rules. For example:

- a Chern–Simons counterterm must have a properly quantized level;
- a term that is legal on spin manifolds may be illegal on non-spin manifolds;
- a counterterm for $SU(N)$ backgrounds may not be legal for $PSU(N)$ backgrounds;
- an orientation-sensitive counterterm may not respect time reversal or reflection;
- a local expression near $A=0$ may not extend to all topological sectors.

Thus anomaly cancellation is not just algebra. It is algebra plus global geometry.

## Anomaly cancellation by extra degrees of freedom

A nonzero anomaly of one sector can be cancelled by another sector with the opposite anomaly. If

$$
[\mathcal A_G^{(1)}]+[\mathcal A_G^{(2)}]=0,
$$

then the combined theory can be gauged even if neither sector can be gauged alone.

This is how chiral gauge theories work. Individual Weyl fermions can be anomalous. A consistent gauge theory requires the total gauge anomaly to vanish after summing over all matter fields and all relevant contributions.

The cancellation can happen in several ways.

| Cancellation mechanism | Meaning |
|---|---|
| Add matter | New fields contribute the opposite anomaly. |
| Add a local counterterm | The anomaly representative was removable. |
| Add a Wess–Zumino field | A dynamical scalar shifts so that its variation cancels the anomaly. |
| Use Green–Schwarz-like inflow | Higher-form fields and topological couplings cancel the gauge variation. |
| Couple to a bulk | The $d$-dimensional theory is a boundary of an invertible $(d+1)$-dimensional theory. |

Only the combined system is gaugeable.

## Gauging a subgroup

A symmetry $G$ may be anomalous, but a subgroup $H\subset G$ may be gaugeable. The condition is that the restricted anomaly vanishes:

$$
i^*[\mathcal A_G]=0,
\qquad
 i:H\hookrightarrow G.
$$

This is common. A chiral symmetry may be anomalous, while a vector subgroup is anomaly-free. A finite symmetry may have an anomaly, but a smaller subgroup may be gaugeable. A continuous symmetry may have mixed anomalies that obstruct gauging the whole group but not a carefully chosen factor.

There is also a related question: can one gauge a quotient $G/K$? That depends on whether the background fields and anomaly descend to the quotient. This is a global-form question, not just a Lie-algebra question.

The moral is:

$$
\text{gaugeability is a property of a specific symmetry group and its backgrounds.}
$$

Not of a slogan like “the $SU(N)$ flavor symmetry.”

## Symmetry extension and changing the problem

Sometimes an anomalous symmetry $G$ becomes gaugeable after being embedded in a larger symmetry $\widehat G$ or replaced by an extension

$$
1\longrightarrow K\longrightarrow \widehat G\longrightarrow G\longrightarrow 1.
$$

If the anomaly of $G$ pulls back to a trivial anomaly of $\widehat G$, then the extended symmetry may be gaugeable even though the original $G$ was not.

This does not mean the original obstruction was fake. It means the gauging problem changed. The new theory includes extra background data, extra gauge fields, or extra topological sectors associated with $K$.

Symmetry extension is especially important for finite symmetries, fermionic phases, and symmetry-enriched topological phases. It is also one way anomalies can be matched in gapped phases: the IR may contain topological order whose emergent gauge structure effectively extends the symmetry action.

## Bulk inflow and relative theories

A theory with an anomalous global symmetry can often be placed on the boundary of a one-higher-dimensional invertible theory. Let $Y_{d+1}$ be a manifold with boundary $M_d$. The bulk partition function transforms as

$$
Z_{\rm bulk}[A]\longmapsto
\exp\!\left(-2\pi i\mathcal A_g[A|_{M_d}]\right)Z_{\rm bulk}[A],
$$

while the boundary theory transforms with the opposite phase. The product is invariant:

$$
Z_{\rm bulk}[A]Z_{\partial}[A|_{M_d}]
$$

is gauge invariant.

In this situation the boundary theory is not a standalone gaugeable $d$-dimensional theory. It is a boundary condition or relative theory for the bulk anomaly theory. The anomalous symmetry can be made consistent because the missing gauge variation is supplied by inflow.

This is the same logic behind anomaly inflow for chiral edge modes, parity anomalies, topological insulators, and many modern symmetry-protected boundary systems.

## Higher-form symmetries

For a $q$-form global symmetry in $d$ dimensions, the background field is a $(q+1)$-form gauge field, and charged operators are $q$-dimensional extended operators. Gauging the symmetry means summing over the corresponding higher-form background fields.

An anomaly involving a higher-form symmetry obstructs that sum. For example, a mixed anomaly between an ordinary symmetry and a one-form symmetry can obstruct gauging both simultaneously, or can imply that gauging one symmetry changes the realization of the other.

A schematic version is:

$$
Z[A,B]\longmapsto
\exp\!\left(2\pi i\mathcal A[A,B]\right)Z[A,B],
$$

where $A$ is an ordinary background and $B$ is a higher-form background. Gauging the one-form symmetry requires summing over $B$. If the phase is nontrivial under the higher-form gauge transformations of $B$, the gauging is obstructed unless the anomaly is cancelled or the symmetry data are changed.

This is one reason higher-form anomalies are powerful in confinement problems. They constrain which line operators can become genuine, which one-form symmetries can be gauged, and which gapped phases are possible.

## Examples

### Chiral Weyl fermions

A single left-handed Weyl fermion charged under a candidate dynamical $U(1)$ gauge field has a perturbative gauge anomaly proportional to the cube of its charge. As a theory with a **global** $U(1)$, it can be coupled to a background field and the anomaly is a ’t Hooft anomaly. As a theory with a **dynamical** $U(1)$, the same anomaly is fatal.

A collection of Weyl fermions with charges $q_i$ must satisfy conditions such as

$$
\sum_i q_i^3=0,
\qquad
\sum_i q_i=0
$$

for the pure $U(1)^3$ and mixed gravitational-$U(1)$ perturbative gauge anomalies to cancel, in a standard four-dimensional normalization.

### Witten’s SU(2) anomaly

A four-dimensional $SU(2)$ gauge theory with an odd number of left-handed Weyl doublets has a global gauge anomaly. The obstruction is not visible in the perturbative cubic trace because $SU(2)$ has no local cubic gauge anomaly of that type. Instead, it appears under a large gauge transformation associated with topology.

The consequence is severe: such a theory cannot be gauged as a standalone four-dimensional theory. An even number of doublets cancels the obstruction.

This example is the warning label on purely perturbative anomaly checks.

### Axial symmetry in QED-like theories

A massless Dirac fermion coupled to a dynamical electromagnetic gauge field has a classical axial $U(1)_A$ symmetry. Quantum mechanically,

$$
\partial_\mu J_A^\mu
\propto
F\wedge F
$$

in differential-form language. The axial symmetry has a mixed anomaly with the electromagnetic gauge background or dynamical field. If one tries to gauge $U(1)_A$ without adding additional fields or counterterms, the anomaly obstructs the gauging.

As a global symmetry statement, the anomaly is not an inconsistency. It explains selection rules, theta-angle shifts, and nonconservation in gauge backgrounds.

### Finite symmetry orbifolds

In two-dimensional QFT, gauging a finite symmetry is often called orbifolding. The torus partition function of a non-anomalous finite symmetry can be built from twisted sectors and projections. If the finite symmetry is anomalous, modular covariance and consistency of twisted sectors fail unless one includes a compensating bulk or modifies the gauging problem.

This is the same obstruction in a particularly visible costume: the sum over flat bundles on the torus is not consistent.

### Center one-form symmetry

Pure Yang–Mills theory with gauge algebra $\mathfrak{su}(N)$ has a center one-form symmetry whose exact form depends on the global form of the gauge group and allowed line operators. Gauging a one-form symmetry changes the global form of the gauge group. Mixed anomalies involving center symmetry and other symmetries can obstruct certain gaugings or constrain the resulting theory.

Here “gauging” is not about adding ordinary gauge bosons. It is about summing over higher-form background fields and changing the spectrum of genuine line operators.

## The gauging checklist

To decide whether a symmetry can be gauged, run the following checklist.

| Step | Question | Failure mode |
|---:|---|---|
| 1 | What is the exact symmetry group? | Wrong global form or missing quotient. |
| 2 | What background fields define it? | Missing spin, Pin, discrete, or higher-form data. |
| 3 | Is $Z[A]$ defined on all allowed backgrounds? | Background coupling itself fails. |
| 4 | Is $Z[A]$ invariant under background gauge transformations? | Candidate anomaly. |
| 5 | Can local counterterms remove the variation? | If no, genuine obstruction. |
| 6 | Are counterterms globally well-defined and quantized? | Fake cancellation. |
| 7 | Are there mixed anomalies with other symmetries? | Cannot gauge all chosen symmetries simultaneously. |
| 8 | If obstructed, is there cancellation, subgroup gauging, extension, or inflow? | Gauging problem must be modified. |

The order matters. Many mistakes come from computing a local variation before specifying the actual backgrounds.

## What if you gauge anyway?

If one tries to gauge an anomalous symmetry without cancelling the anomaly, several things can go wrong depending on the formalism.

- The path integral over gauge fields is not invariant under changes of representative.
- Gauge fixing gives inconsistent Faddeev–Popov or BRST identities.
- The Gauss-law constraint cannot be imposed consistently on the Hilbert space.
- Longitudinal gauge modes fail to decouple.
- The theory violates unitarity, locality, or factorization.
- The partition function becomes a section of a nontrivial line bundle over gauge-field space rather than a function that can be integrated.

Different languages diagnose the same sickness. Gauge redundancy is not allowed to be anomalous.

## Common pitfalls

**Thinking every anomalous global symmetry is inconsistent.** It is not. A global anomaly is consistent and physically useful. The inconsistency arises only if the anomalous symmetry is promoted to gauge redundancy without cancellation.

**Forgetting the counterterm quotient.** Non-invariance of one representative does not prove an obstruction. Non-invariance modulo all allowed local counterterms does.

**Using the wrong background space.** Gauging $SU(N)$ and gauging $PSU(N)$ are different questions. So are gauging on spin versus non-spin manifolds.

**Confusing gauging with projecting to singlets.** For finite symmetries and orbifolds, gauging includes twisted sectors or nontrivial bundles, not only projection onto invariant states.

**Ignoring mixed anomalies.** A symmetry may be gaugeable alone but not simultaneously gaugeable with another symmetry.

**Treating inflow as cancellation inside the boundary theory.** Inflow makes the combined bulk-boundary system gauge invariant. The boundary alone remains anomalous as a standalone theory.

**Assuming a subgroup inherits the same obstruction.** The anomaly may vanish when restricted to a subgroup. Gaugeability must be checked for the actual subgroup.

## Relations to other pages

- [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) explains the gauging operation before anomalies enter.
- [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) defines the background-field obstruction.
- [Anomalies as RG Invariants](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-as-rg-invariants/) explains why the obstruction survives RG flow.
- [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/) gives the local gauge-anomaly version of the obstruction.
- [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) explains large-transformation obstructions such as the $SU(2)$ anomaly.
- [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) will develop the higher-form analogue.
- [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) treats the bulk-cancellation viewpoint.

## Research status

For ordinary continuous symmetries, finite symmetries in many standard settings, and perturbative gauge anomalies, the obstruction-to-gauging statement is established and foundational. It is one of the basic consistency tests for chiral gauge theories and one of the basic uses of background fields in modern QFT.

The active frontier is broader symmetry. Higher-form symmetries fit beautifully into the same framework. Fermionic, spin/Pin, crystalline, higher-group, subsystem, and non-invertible symmetries require more refined notions of background, gauging, and anomaly. In many examples the slogan remains exactly right: anomaly means obstruction to gauging. The ongoing work is to say precisely what “gauging” means for each generalized symmetry structure.

## Exercises

### 1. Why projection is not finite gauging

Let $G$ be a finite symmetry. Explain why gauging $G$ is not merely projecting the Hilbert space onto $G$-invariant states.

<details><summary><strong>Solution</strong></summary>

Projection onto invariant states accounts only for the trivial background sector. Gauging a finite symmetry requires summing over all flat $G$ bundles. In Hamiltonian language this introduces twisted sectors when space has nontrivial cycles. In path-integral language the gauged partition function is a groupoid sum

$$
Z_{\mathcal T/G}[M_d]
=\sum_{[A]\in\operatorname{Bun}_G(M_d)}
\frac{1}{|\operatorname{Aut}(A)|}Z_{\mathcal T}[A].
$$

The projection is only one part of this sum. Omitting twisted sectors usually violates locality, modular invariance in two dimensions, or factorization.

</details>

### 2. Subgroup gauging

Suppose $G$ has anomaly class $[\mathcal A_G]$ and $H\subset G$ is a subgroup. What condition must hold for $H$ to be gaugeable?

<details><summary><strong>Solution</strong></summary>

The anomaly must vanish after restriction to $H$:

$$
i^*[\mathcal A_G]=0,
\qquad i:H\hookrightarrow G.
$$

This means that when the allowed $G$ backgrounds are restricted to $H$ backgrounds, the anomalous phase can be removed by $H$-background local counterterms. If the restricted class is nonzero, $H$ is also obstructed. If it vanishes, $H$ may be gaugeable even though the full $G$ is not.

</details>

### 3. Anomaly cancellation by a second sector

Two decoupled theories $\mathcal T_1$ and $\mathcal T_2$ have the same global symmetry $G$ and anomaly classes $[\mathcal A_1]$ and $[\mathcal A_2]$. Show that the diagonal $G$ symmetry of $\mathcal T_1\times\mathcal T_2$ is gaugeable if $[\mathcal A_1]+[\mathcal A_2]=0$.

<details><summary><strong>Solution</strong></summary>

The background-field partition function of the product theory is

$$
Z[A]=Z_1[A]Z_2[A].
$$

Under a background gauge transformation,

$$
Z[A^g]
=\exp\!\left(2\pi i(\mathcal A_{1,g}[A]+\mathcal A_{2,g}[A])\right)Z[A].
$$

If $[\mathcal A_1]+[\mathcal A_2]=0$, the sum of representatives differs from zero by a local counterterm variation. After adding that counterterm, the product partition function is background gauge invariant. Therefore the diagonal $G$ symmetry is gaugeable.

</details>

### 4. Bulk inflow is not standalone gauging

An anomalous $d$-dimensional boundary theory becomes gauge invariant when combined with a $(d+1)$-dimensional bulk invertible theory. Does this mean the boundary symmetry is gaugeable as a standalone $d$-dimensional theory?

<details><summary><strong>Solution</strong></summary>

No. The combined bulk-boundary system is gauge invariant because the bulk variation cancels the boundary variation. The boundary partition function by itself still transforms anomalously. Therefore the boundary theory alone is not a standalone gaugeable $d$-dimensional theory. It is a boundary condition, or relative theory, for the bulk anomaly theory.

</details>

## References

- G. ’t Hooft, “Naturalness, chiral symmetry, and spontaneous chiral symmetry breaking,” in *Recent Developments in Gauge Theories*, 1980.
- L. D. Faddeev and S. L. Shatashvili, “Algebraic and Hamiltonian Methods in the Theory of Nonabelian Anomalies,” *Theoretical and Mathematical Physics* 60 (1984) 770.
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology,” *Communications in Mathematical Physics* 129 (1990) 393.
- M. Srednicki, *Quantum Field Theory*, §§74–77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on non-Abelian gauge theory, BRST, and anomalies.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- E. Witten, “An SU(2) Anomaly,” *Physics Letters B* 117 (1982) 324.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* 234 (1984) 269.
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” arXiv:1604.06527.

## Version history

- 2026-06-18: First polished draft. Added finite and continuous gauging tests, counterterm caveats, subgroup gauging, anomaly cancellation, inflow, higher-form orientation, and exercises.
