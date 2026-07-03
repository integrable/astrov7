---
title: "Gauging Higher-Form Symmetries"
description: "Explains what it means to gauge a higher-form global symmetry, how summing over higher-form backgrounds changes charged operators, and how dual higher-form symmetries appear."
sidebar:
  label: "Gauging Higher-Form Symmetries"
  order: 4
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Kapustin–Seiberg; Aharony–Seiberg–Tachikawa; standard BF-theory and gauge-theory line-operator references."
topics:
  - higher-form symmetry
  - gauging
  - background fields
  - dual symmetry
  - BF theory
  - one-form symmetry
canonicalTopics:
  - gauging-higher-form-symmetry
  - dual-higher-form-symmetry
  - higher-form-background-field
  - anomaly-obstruction
researchStatus:
  established:
    - "For finite Abelian higher-form symmetries, gauging is cleanly described by summing over higher-form background gauge fields and produces a dual higher-form symmetry."
    - "An anomaly-free higher-form symmetry can be gauged; an anomalous higher-form symmetry cannot be gauged as an ordinary standalone operation without extra bulk or boundary data."
  active:
    - "Fermionic, non-invertible, higher-group, non-Abelian higher-form, and symmetry-TFT refinements require more sophisticated background data than the differential-form formulas used for first orientation here."
---

## Summary

To **gauge a higher-form global symmetry** means to promote its background field from a fixed external probe to a dynamical variable and sum over it in the path integral. For a $q$-form symmetry, the background is a $(q+1)$-form gauge field $B_{q+1}$, so schematically

$$
Z_{\text{gauged}}
=
\sum_{[B_{q+1}]}
Z[B_{q+1}],
$$

for a finite symmetry, or

$$
Z_{\text{gauged}}
=
\int \frac{\mathcal D B_{q+1}}{\text{higher-form gauge redundancy}}\,
Z[B_{q+1}]\,e^{iS_{\text{top}}[B,\ldots]},
$$

for a continuous compact or continuum presentation. The precise measure is part of the definition; the displayed formula is the correct physical slogan, not a substitute for a regulator.

Gauging is possible only when the background-field partition function has the required gauge invariance. If

$$
Z[B+d\Lambda]=Z[B]
$$

up to removable local counterterms, the symmetry is gaugeable. If not, the symmetry has an ’t Hooft anomaly.

A striking feature of finite Abelian higher-form gauging is that it usually creates a **dual higher-form symmetry**. Gauging a finite Abelian $q$-form symmetry $A$ in $d$ dimensions produces a dual $(d-q-2)$-form symmetry with group

$$
\widehat A=\operatorname{Hom}(A,U(1)).
$$

This is the higher-form version of the familiar fact that gauging a finite ordinary symmetry can produce a dual quantum symmetry.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic showing a higher-form background field being summed over to gauge a symmetry, with charged operators projected to neutral combinations and a dual topological operator emerging.](/figures/symmetry-anomalies-topology/gauging-higher-form-symmetry.svg)

<figcaption>

Gauging a $q$-form symmetry sums over the background $(q+1)$-form field $B_{q+1}$. Charged $q$-dimensional operators are no longer automatically genuine; the gauged theory keeps gauge-invariant combinations and often gains a dual $(d-q-2)$-form symmetry.

</figcaption>
</figure>

The central intuition is:

$$
\text{background field}
\quad\longrightarrow\quad
\text{dynamical gauge field}
\quad\longrightarrow\quad
\text{projection, new defects, and often a dual symmetry}.
$$

## Prerequisites

Read [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), [Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/), and [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) first.

You should know that a $q$-form symmetry acts on $q$-dimensional charged operators and is probed by topological operators on closed codimension-$q+1$ manifolds. You should also know the ordinary background-field slogan: a global symmetry is gauged by summing over the background gauge field, provided no anomaly obstructs the sum.

## Core idea

A background field is a question. Gauging makes the question part of the theory.

Before gauging, the QFT is a family of partition functions

$$
Z[B_{q+1}],
$$

where $B_{q+1}$ is fixed. Correlation functions with charged extended insertions are sections over this background-field space; they transform covariantly under background gauge transformations.

After gauging, the background is no longer fixed. One sums over it:

$$
Z_{\text{new}}
=
\sum_{[B]}Z[B].
$$

This has three immediate effects.

First, the old charged operators are projected. If an operator is charged under the symmetry being gauged, it is not gauge-invariant in the new theory unless it is dressed, attached to a suitable defect, or combined with other insertions so the total charge cancels.

Second, the old symmetry defects become dynamical or summed-over objects. Gauging changes which defects are genuine, topological, or allowed to end.

Third, for finite Abelian higher-form symmetries, the gauged theory has a new dual higher-form symmetry. Its charged operators are the defects or flux operators that measure the newly dynamical gauge field.

The slogan is:

$$
\text{gauging a symmetry}
=
\text{orbifolding by its topological symmetry operators}.
$$

For higher-form symmetry, this “orbifold” happens not by summing over ordinary twisted sectors alone, but by summing over higher-form background fields on spacetime.

## Setup and conventions

Let $X_d$ be a $d$-dimensional spacetime manifold. Let $A$ be a finite Abelian $q$-form global symmetry. A background for this symmetry can be represented, in a lattice or cohomological model, by a flat $(q+1)$-cochain or cocycle

$$
B\in Z^{q+1}(X_d,A),
$$

up to gauge equivalence. The gauged partition function is schematically

$$
Z_{\text{gauged}}(X_d)
=
\frac{1}{|\mathcal G|}
\sum_{[B]\in H^{q+1}(X_d,A)}
Z(X_d;B),
$$

where $|\mathcal G|$ stands for the appropriate gauge-volume normalization. Different regulators implement this normalization differently; the important point is the sum over background topological sectors.

For a continuous compact Abelian symmetry, a differential-form presentation uses a $(q+1)$-form gauge field $B_{q+1}$ with gauge redundancy

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q.
$$

A continuum gauging formula must specify flux quantization, large gauge transformations, and possible topological actions. A common topological way to encode finite $\mathbb Z_N$ higher-form gauge theory is a BF-type action

$$
S_{\text{BF}}
=
\frac{N}{2\pi}\int_{X_d} b_{d-q-2}\wedge dB_{q+1},
$$

where $b_{d-q-2}$ is a Lagrange-multiplier gauge field imposing the appropriate flatness and quantization data.

:::note[Source note: differential forms versus cocycles]
Differential forms are excellent for local formulas. Finite symmetries, torsion classes, large gauge transformations, and discrete theta terms are usually cleaner in cochain, differential-cohomology, or TQFT language. This page uses differential forms for orientation and states when the more global data matter.
:::

## The anomaly test

Gauging requires background gauge invariance. If

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q,
$$

then the partition function must transform as

$$
Z[B+d\Lambda]=Z[B]
$$

or at worst by a phase that can be removed by adding a local counterterm depending on $B$ and background geometry.

If no such counterterm exists, the $q$-form symmetry has an ’t Hooft anomaly. Then gauging the symmetry as an ordinary operation is obstructed.

A useful way to remember the logic is:

$$
\text{anomaly-free}
\quad\Rightarrow\quad
\text{can gauge},
$$

but

$$
\text{anomalous}
\quad\Rightarrow\quad
\text{needs inflow, boundary, extension, or modified data}.
$$

For higher-form symmetries this obstruction is often physically visible in the braiding or linking phases of extended operators. If the would-be gauge invariance of the background field is inconsistent with the phases picked up by charged defects, the gauging operation cannot be defined without extra structure.

## What happens to charged operators?

Before gauging, a charged operator $W_q(M)$ is a legitimate insertion. Under a background gauge transformation,

$$
W_q(M)\mapsto
\exp\!\left(i n\int_M\Lambda_q\right)W_q(M)
$$

in a simple continuous Abelian normalization.

After gauging, this transformation is a redundancy. A single charged insertion is not gauge-invariant. In the gauged theory one must either insert a neutral combination, attach the operator to a higher-dimensional object whose transformation cancels it, or accept that the operator is not a genuine operator of the new theory.

For a finite $A$ symmetry, this is the higher-form version of projecting onto singlets. A correlator of charged $q$-dimensional operators survives the gauging sum only if the total charge is neutral in the appropriate homological sense.

For ordinary zero-form finite gauging, charged local operators are projected to invariant combinations. For one-form finite gauging, charged lines are projected: line operators with nontrivial charge under the gauged one-form symmetry cease to be genuine unless they are dressed or combined with other line defects.

This mechanism is why gauging a one-form symmetry changes the line-operator spectrum of a gauge theory.

## Dual higher-form symmetry

For a finite Abelian $q$-form symmetry $A$, gauging produces a dual symmetry

$$
\widehat A=\operatorname{Hom}(A,U(1))
$$

of degree

$$
d-q-2.
$$

The degree follows from the fact that the new topological operators measure the holonomy or flux of the dynamical $(q+1)$-form gauge field. A dual charged operator has dimension

$$
d-q-2,
$$

so it links naturally with the $(q+1)$-form gauge-field flux.

Check the formula in familiar cases.

For $d=2$ and $q=0$, gauging a finite ordinary symmetry produces a dual zero-form symmetry:

$$
d-q-2=2-0-2=0.
$$

This is the quantum symmetry of a two-dimensional orbifold.

For $d=4$ and $q=1$, gauging a finite one-form symmetry produces another one-form symmetry:

$$
d-q-2=4-1-2=1.
$$

This is why gauging a $\mathbb Z_N$ one-form symmetry in four-dimensional gauge theory often exchanges or reshuffles electric and magnetic one-form symmetry data.

:::note[Finite Abelian assumption]
The clean dual group $\widehat A$ statement assumes finite Abelian symmetry. Continuous, non-Abelian, non-invertible, and higher-group generalizations require extra care and can behave differently.
:::

## Example: ordinary finite gauging as the zero-form case

Let $q=0$. A finite ordinary symmetry $A$ is gauged by summing over flat $A$ bundles, or equivalently by summing over twisted sectors. Local operators charged under $A$ are projected to invariant combinations.

In two dimensions, the gauged theory often has a dual ordinary symmetry $\widehat A$. Its operators measure the twisted sectors introduced by the gauging.

This example is useful because the higher-form story is not conceptually different; it is geometrically shifted. The charged objects are no longer local operators, and the backgrounds are no longer ordinary one-form gauge fields, but the logic is the same.

## Example: gauging a one-form symmetry in four dimensions

Let a four-dimensional theory have a finite Abelian one-form symmetry $A$. Its charged objects are line operators. A background field is a two-form gauge field

$$
B_2.
$$

Gauging the one-form symmetry means summing over $B_2$ backgrounds. The old charged line operators are no longer automatically genuine in the gauged theory. In a gauge theory, this operation can change the global form of the gauge group and the allowed Wilson–’t Hooft line lattice.

The basic model to keep in mind is the relation between $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ gauge theories. Pure $SU(N)$ Yang–Mills has a $\mathbb Z_N$ electric one-form center symmetry acting on Wilson lines. Gauging that symmetry changes which Wilson lines are genuine and introduces dual magnetic one-form data. Different discrete theta choices can produce distinct theories with the same local Lie algebra.

This is not a small refinement. It changes the global theory.

## Example: BF theory as a gauging kernel

A finite higher-form gauging operation can often be represented by coupling the original theory to a topological BF theory. For a $\mathbb Z_N$ $q$-form symmetry, a schematic continuum kernel is

$$
\exp\!\left(
\frac{iN}{2\pi}\int b_{d-q-2}\wedge dB_{q+1}
\right).
$$

The field $b_{d-q-2}$ enforces the finite flatness structure of $B_{q+1}$ and also makes the dual symmetry visible. Operators of the form

$$
\exp\!\left(i\int_{\Gamma^{d-q-2}}b_{d-q-2}\right)
$$

are natural candidates for charged operators under the dual symmetry.

This formula is schematic because an honest finite gauge theory is not just an ordinary real differential form with an $N$ in front. Its global definition includes periods, gauge identifications, and torsion sectors. Still, the BF kernel is the right first picture: gauging introduces a new topological gauge field whose holonomies encode the dual symmetry.

## Gauging versus quotienting

In ordinary group theory one sometimes says “quotient by a symmetry.” In QFT, gauging is the operational version of quotienting: project to invariant sectors and sum over twisted or background sectors.

For higher-form symmetry, the quotient affects extended operators. If a one-form symmetry acts on Wilson lines, gauging it removes or reclassifies those Wilson lines. If a two-form symmetry acts on surface operators, gauging it changes the surface-operator spectrum.

This is why the phrase “same local Lagrangian” can be misleading. Two theories can have the same local equations but different higher-form symmetry gauging choices, hence different line operators, different background fields, and different global forms.

## Boundaries and defects

Gauging also affects boundaries and defects.

If a charged operator used to be able to end on a boundary, gauging may require boundary degrees of freedom to make that endpoint gauge-invariant. Conversely, a boundary condition may be interpreted as choosing how the gauged higher-form field behaves at the boundary.

This is the doorway to symmetry TFT. In that language, gauging corresponds to changing a topological boundary condition in one higher dimension. The old symmetry defects, new gauge fields, and dual symmetry operators are all different boundary manifestations of the same bulk topological theory.

This page does not require the symmetry-TFT language, but it prepares for it: gauging is not just an algebraic operation on a group. It is an operation on topological defects, background fields, and boundary conditions.

## Common pitfalls

**“Gauging means adding a new local gauge boson.”** Not always. Gauging a finite higher-form symmetry can produce a topological gauge theory rather than a propagating gauge boson.

**“If the local Lagrangian is unchanged, the theory is unchanged.”** False. Gauging a one-form symmetry can change the global form of the gauge group and the line-operator spectrum while leaving local perturbation theory almost identical.

**“Charged operators remain ordinary operators after gauging.”** Charged operators under the gauged symmetry are not gauge-invariant. They must be projected, dressed, attached to defects, or removed from the genuine operator spectrum.

**“A background gauge transformation is optional bookkeeping.”** No. Background gauge invariance is the Ward identity. If it fails nontrivially, the symmetry is anomalous and cannot be gauged in the usual way.

**“The dual symmetry exists for every gauging.”** The simple dual $\widehat A$ statement is for finite Abelian higher-form symmetries. More general symmetry structures require more general language.

**“BF formulas are the whole story.”** BF actions capture the useful continuum intuition, but finite gauge theories also require global cohomology, periods, torsion sectors, and possible discrete theta terms.

## Relations to other pages

[Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) defines the source fields that are summed over here.

[Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) explains which operators become non-genuine, projected, or dressed after gauging.

[Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) gives the most important gauge-theory example: gauging a center one-form symmetry changes the global form and line-operator spectrum.

The [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) chapter treats ordinary global symmetries and finite gauging. The [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) chapter explains the obstruction to gauging. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) packages gauging as a topological boundary operation.

## Research status

The basic picture of gauging finite Abelian higher-form symmetries is standard. It is now part of the common language of generalized global symmetry, global forms of gauge groups, line-operator lattices, and topological phases.

Several refinements remain research-active. Non-Abelian higher-form symmetries are subtle. Higher-group symmetries mix ordinary and higher-form transformations. Fermionic systems require spin and Pin data. Non-invertible symmetries replace group gauging by condensation or summing over defect networks. Symmetry TFT gives a unified framework, but the level of categorical precision varies by dimension and example.

## Exercises

### Exercise 1: Degree of the dual symmetry

A finite Abelian $q$-form symmetry is gauged in $d$ spacetime dimensions. Show that the dual symmetry has degree $d-q-2$. What is the dual degree for a one-form symmetry in four dimensions?

<details><summary><strong>Solution</strong></summary>

The background field for the original $q$-form symmetry is a $(q+1)$-form $B_{q+1}$. After gauging, the dual topological operators measure the flux or holonomy of this dynamical field. Such operators naturally live on closed manifolds of dimension

$$
d-(q+1)-1=d-q-2.
$$

Therefore the dual symmetry is a $(d-q-2)$-form symmetry. For $d=4$ and $q=1$,

$$
d-q-2=4-1-2=1,
$$

so the dual symmetry is again a one-form symmetry.

</details>

### Exercise 2: Projection of charged operators

Explain why a single operator charged under a symmetry being gauged is not a genuine operator of the gauged theory.

<details><summary><strong>Solution</strong></summary>

After gauging, the former background gauge transformation becomes a redundancy. A genuine operator must be invariant under redundancies. If an operator transforms as

$$
W(M)\mapsto e^{i\theta(\Lambda,M)}W(M),
$$

then it is not gauge-invariant unless the phase is always trivial. To make an allowed insertion, one must combine it with other charged operators so the total transformation cancels, attach it to a dressing defect, put it on a boundary with compensating degrees of freedom, or omit it from the genuine operator spectrum.

</details>

### Exercise 3: BF degree check

For a $\mathbb Z_N$ $q$-form gauging in $d$ dimensions, check that

$$
\int b_{d-q-2}\wedge dB_{q+1}
$$

has degree $d$.

<details><summary><strong>Solution</strong></summary>

The form $B_{q+1}$ has degree $q+1$, so $dB_{q+1}$ has degree $q+2$. The form $b_{d-q-2}$ has degree $d-q-2$. Therefore

$$
\deg(b_{d-q-2}\wedge dB_{q+1})
=
(d-q-2)+(q+2)=d.
$$

So the integral is over a top-degree form on $X_d$.

</details>

### Exercise 4: Gauging a center symmetry

In four-dimensional pure $SU(N)$ Yang–Mills, the electric center symmetry is a $\mathbb Z_N$ one-form symmetry. What kind of objects does it act on, and what kind of dual symmetry should appear after gauging it?

<details><summary><strong>Solution</strong></summary>

A one-form symmetry acts on line operators. In pure $SU(N)$ Yang–Mills, the $\mathbb Z_N$ electric center symmetry acts on Wilson lines by their $N$-ality.

Since $d=4$ and $q=1$, the dual degree is

$$
4-1-2=1.
$$

Thus gauging the electric center one-form symmetry produces another one-form symmetry, often interpreted as magnetic one-form data in the resulting global form of the gauge theory.

</details>

## References

- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” The foundational modern reference for higher-form global symmetries, their background fields, gauging, spontaneous breaking, and anomalies.
- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality.” A central reference for coupling to topological gauge theories and understanding gauging as a global operation.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories.” Essential for global forms, line operators, and one-form gauging in four-dimensional gauge theory.
- Michael Freed and Greg Moore, “Setting the Quantum Integrand of M-Theory,” and related differential-cohomology references for global background-field refinements.
- Mikio Nakahara, *Geometry, Topology and Physics*, for cohomology, bundles, connections, and topological gauge-field background.
- A. M. Polyakov, *Gauge Fields and Strings*, for Wilson loops, compact gauge systems, confinement intuition, and loop dynamics.

## Version history

- **2026-06-20:** Initial polished draft. Added finite Abelian gauging, dual higher-form symmetry, operator projection, BF kernel, anomaly test, examples, and exercises.
