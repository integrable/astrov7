---
title: "Chern–Simons Theory"
description: "Introduces Chern–Simons theory as a three-dimensional topological gauge theory, including level quantization, Wilson lines, framing, boundaries, and anomaly inflow."
sidebar:
  label: "Chern–Simons Theory"
  order: 4
level: Advanced
status: "Polished draft"
source: "Chern–Simons; Witten; Polyakov; Nakahara; Frankel; Altland–Simons; standard TQFT and knot-invariant references."
topics:
  - Chern-Simons theory
  - topological gauge theory
  - Wilson lines
  - knot invariants
  - framing
  - boundary WZW theory
  - anomaly inflow
canonicalTopics:
  - chern-simons-theory
  - topological-gauge-theory
  - wilson-line
  - level-quantization
  - framing-anomaly
researchStatus:
  established:
    - "Pure Chern–Simons theory is the canonical three-dimensional Schwarz-type TQFT, with Wilson-line observables related to knot and link invariants."
    - "Level quantization, framing dependence, boundary current algebras, and anomaly-inflow interpretations are standard structural features."
  active:
    - "Modern research uses Chern–Simons theory in topological phases, nonsemisimple TQFT, 3d dualities, Chern–Simons–matter theories, and SymTFT constructions."
---

## Summary

**Chern–Simons theory** is a three-dimensional topological gauge theory whose action is built from a connection rather than from a metric. For a compact gauge group and Hermitian connection

$$
A=A^aT_a,
$$

the nonabelian Chern–Simons action in the conventions of this volume is

$$
S_{\mathrm{CS}}[A]
=
\frac{k}{4\pi}
\int_M
\operatorname{tr}
\left(
A\wedge dA+\frac{2i}{3}A\wedge A\wedge A
\right).
$$

The integer $k$ is the **level**, after choosing a trace normalization and global form of the gauge group. The classical equation of motion is flatness,

$$
F=dA+iA\wedge A=0.
$$

Thus the theory has no ordinary local propagating gauge bosons. Its observables are global: Wilson lines, link invariants, mapping-class-group actions, finite-dimensional Hilbert spaces on surfaces, and boundary current algebras.

The shortest useful slogan is

$$
\text{Chern–Simons theory}
=
\text{three-dimensional topological gauge theory of flat connections with quantum line operators}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![Chern-Simons theory on a three-manifold with linked Wilson loops and a boundary supporting a chiral current algebra.](/figures/symmetry-anomalies-topology/chern-simons-theory-data.svg)

<figcaption>

Chern–Simons theory is topological in the bulk but rich on lines and boundaries. Bulk Wilson lines detect knotting and linking. A boundary supports degrees of freedom, often described by a chiral current algebra or WZW-type theory.

</figcaption>
</figure>

Chern–Simons theory sits at a crossroads: TQFT, knot theory, quantum groups, conformal field theory, topological phases of matter, anomaly inflow, and three-dimensional gauge dynamics all meet here.

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/) and [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/). You should also be comfortable with differential forms, gauge connections, Wilson lines, holonomy, compact gauge groups, and basic topology of three-manifolds.

The page uses the Hermitian gauge-field convention from [Conventions and Notation](/symmetry-anomalies-topology/conventions/):

$$
F=dA+iA\wedge A.
$$

Mathematics references often use anti-Hermitian connections. In that convention the cubic term is written without the explicit $i$. Do not compare signs until the convention for the connection is translated.

## Core idea

Ordinary Yang–Mills theory in three dimensions has action

$$
S_{\mathrm{YM}}\sim \frac{1}{g^2}\int \operatorname{tr}(F\wedge *F),
$$

which requires a metric through the Hodge star $*$. Chern–Simons theory instead uses

$$
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right),
$$

a three-form that can be integrated over an oriented three-manifold without choosing a metric. This is why Chern–Simons theory is a **Schwarz-type** TQFT: topological behavior comes directly from a metric-free classical action, not from a $Q$-exact stress tensor.

The action is not gauge invariant as an ordinary real-valued function under all large gauge transformations. Instead, for properly quantized $k$, the path-integral phase

$$
e^{iS_{\mathrm{CS}}}
$$

is well-defined. This is the first major lesson of Chern–Simons theory: topology and quantization are inseparable.

## Abelian Chern–Simons theory

For a compact $U(1)$ connection $A$, the schematic action is

$$
S=\frac{k}{4\pi}\int_M A\wedge dA.
$$

The equation of motion is

$$
dA=0.
$$

So locally the connection is flat. The theory is nevertheless nontrivial because flat connections can have global holonomy, and Wilson lines can link.

A Wilson line of charge $q$ along a closed curve $\gamma$ is

$$
W_q(\gamma)=\exp\left(iq\oint_\gamma A\right).
$$

In abelian Chern–Simons theory, correlation functions of Wilson lines are controlled by linking numbers. Very schematically,

$$
\left\langle W_q(\gamma)W_{q'}(\gamma')\right\rangle
\sim
\exp\left(\frac{2\pi i\,qq'}{k}\operatorname{Link}(\gamma,\gamma')\right),
$$

with self-linking and framing data needed for precise formulas.

The charge labels are periodic:

$$
q\sim q+k
$$

in $U(1)_k$ Chern–Simons theory, again with spin-structure refinements depending on the precise theory. This finite set of line labels is the seed of anyon fusion and modular data.

:::note[Source note]
The differential-form action $A\wedge dA$ is a compact notation. For a compact $U(1)$ gauge field, the globally correct definition uses bundles or differential cohomology, not a single globally defined one-form on all manifolds.
:::

## Nonabelian Chern–Simons theory

Let $G$ be a compact Lie group. The nonabelian action is

$$
S_{\mathrm{CS}}[A]
=
\frac{k}{4\pi}
\int_M
\operatorname{tr}
\left(
A\wedge dA+\frac{2i}{3}A\wedge A\wedge A
\right).
$$

Varying the action gives

$$
\delta S_{\mathrm{CS}}
=
\frac{k}{2\pi}\int_M\operatorname{tr}(\delta A\wedge F)
+\text{boundary term}.
$$

On a closed manifold, the classical equation of motion is

$$
F=0.
$$

Thus the classical configurations are flat $G$-connections modulo gauge transformations. The quantum theory is not simply the finite-dimensional integral over flat connections, because one must also account for determinants, phases, Wilson-line insertions, reducible connections, and framing.

Wilson lines are labeled by representations $R$ of $G$:

$$
W_R(\gamma)=\operatorname{tr}_R\,P\exp\left(-i\oint_\gamma A\right),
$$

with the sign tied to the Hermitian connection convention. In quantum Chern–Simons theory, only a finite set of integrable representations appears at fixed level $k$ for compact simple groups.

## Level quantization

Under a gauge transformation $g:M\to G$, the Chern–Simons action shifts by a topological integer multiple of $2\pi k$ when the trace normalization is chosen so that instanton number is integral. Therefore

$$
k\in\mathbb Z
$$

is required so that

$$
e^{iS_{\mathrm{CS}}}
$$

is gauge invariant.

This statement hides important refinements:

| Refinement | Why it matters |
|---|---|
| Trace normalization | Rescaling $\operatorname{tr}(T_aT_b)$ rescales the numerical level. |
| Global form of $G$ | $SU(N)$ and $PSU(N)$ have different allowed bundles and line operators. |
| Spin structure | Some Chern–Simons theories are spin TQFTs and require a spin manifold. |
| Boundary | Gauge variation becomes a boundary anomaly unless boundary degrees of freedom are added. |
| Framing | The quantum partition function often depends on a framing, not only an oriented manifold. |

So the reliable sentence is: **level quantization is required, but the exact quantization law belongs to the fully specified global theory.**

:::caution[Do not ignore global data]
The Lie algebra and local action do not fully define a Chern–Simons TQFT. One must specify the compact gauge group, global form, level, allowed line operators, spin/framing structure, and boundary conditions.
:::

## Metric independence and framing

The classical action does not use a metric. But quantization requires regularization, and regularization can introduce a subtle dependence on framing. In many Chern–Simons theories, the partition function is not just an invariant of an oriented three-manifold; it is naturally an invariant of a framed three-manifold, or it transforms in a controlled way under framing changes.

For Wilson lines, self-linking is not defined without a framing of the knot. A framing chooses a small normal displacement $\gamma'$ of a loop $\gamma$, so that self-linking is defined as

$$
\operatorname{Link}(\gamma,\gamma').
$$

This is not a failure of topological field theory. It is a lesson: quantum topological theories may depend on extra topological or tangential structures, such as framing, spin structure, orientation, or Pin structure.

## Wilson lines and knot invariants

Chern–Simons theory became famous because Wilson-loop expectation values produce knot and link invariants. In nonabelian Chern–Simons theory with gauge group $G$ and level $k$, the expectation value

$$
\left\langle \prod_i W_{R_i}(\gamma_i)\right\rangle
$$

is a topological invariant of the link $\cup_i\gamma_i$, together with representation labels and framing data.

For $G=SU(2)$, these invariants are related to the Jones polynomial. More generally, compact simple groups give quantum-group link invariants at a root of unity. The appearance of quantum groups is not accidental: line operators have fusion and braiding, and the category of line operators encodes modular tensor category data.

This is the second major lesson of Chern–Simons theory: topological QFT converts path integrals into algebraic and topological invariants.

## Hilbert spaces on surfaces

A three-dimensional TQFT assigns a Hilbert space to a closed two-dimensional surface $\Sigma$:

$$
Z(\Sigma)=\mathcal H_\Sigma.
$$

In Chern–Simons theory, $\mathcal H_\Sigma$ can often be described as the quantization of the moduli space of flat $G$-connections on $\Sigma$. In the relation to two-dimensional conformal field theory, the same space appears as the space of conformal blocks.

For a torus $T^2$, the Hilbert space has a basis labeled by allowed anyon or integrable representation labels. The mapping class group of the torus acts through matrices commonly called $S$ and $T$ in modular tensor category language.

These Hilbert spaces are finite-dimensional in ordinary compact Chern–Simons TQFT. Their dimensions are computable by the Verlinde formula in the semisimple cases.

## Boundaries and chiral theories

On a manifold with boundary, the gauge variation of the Chern–Simons action produces a boundary term. To preserve gauge invariance, one must choose boundary conditions and often add boundary degrees of freedom.

For compact nonabelian Chern–Simons theory, a common boundary theory is a chiral Wess–Zumino–Witten model. The boundary current algebra level is tied to the bulk Chern–Simons level. This is one of the most important examples of anomaly inflow:

$$
\delta S_{\mathrm{bulk}}+\delta S_{\mathrm{boundary}}=0.
$$

The bulk is topological, but the boundary can be chiral, gapless, and metric-dependent. This is exactly what happens in many topological phases: a gapped bulk carries a topological response, while its boundary supports protected modes.

## Relation to three-dimensional massive gauge theory

A Chern–Simons term can be added to a three-dimensional Yang–Mills action:

$$
S=S_{\mathrm{YM}}+S_{\mathrm{CS}}.
$$

The resulting theory is not purely topological at finite Yang–Mills coupling. The gauge field acquires a topological mass, and the theory has local dynamics at intermediate scales. In the deep infrared, the Yang–Mills term is often irrelevant compared with the Chern–Simons term, and the topological sector can dominate.

Chern–Simons–matter theories are also not automatically TQFTs. Coupling to gapless matter introduces local degrees of freedom. Nevertheless, many such theories flow to interacting CFTs or gapped phases whose topological sectors are controlled by Chern–Simons terms.

## Relation to topological phases

Chern–Simons theory is a basic effective field theory for two-dimensional topological phases of matter. For example, abelian Chern–Simons theories describe many fractional quantum Hall states. The $K$-matrix action

$$
S=\frac{1}{4\pi}\int K_{IJ}A^I\wedge dA^J
$$

encodes anyon braiding, ground-state degeneracy, and electromagnetic response after coupling to an external field.

Nonabelian Chern–Simons theories describe nonabelian anyons in idealized topological phases. The line operators are anyon worldlines, fusion gives superselection-sector fusion, and braiding gives unitary operations on fusion spaces.

This is one reason Chern–Simons theory appears simultaneously in high-energy theory, low-dimensional topology, and condensed matter.

## Chern–Simons terms as anomaly inflow

A Chern–Simons action in odd dimensions is closely related to anomaly polynomials in one higher even dimension. In three dimensions,

$$
d\,\operatorname{tr}
\left(
A\wedge dA+\frac{2i}{3}A\wedge A\wedge A
\right)
=
\operatorname{tr}(F\wedge F).
$$

This is the descent relation behind many gauge anomalies. A boundary chiral anomaly in two dimensions can be canceled by the variation of a three-dimensional Chern–Simons bulk.

This is why Chern–Simons theory is central in the Symmetry TFT and Anomaly Inflow chapter: it is both a TQFT and an anomaly inflow theory.

## Common pitfalls

**“Chern–Simons theory is topological, so it has no observables.”** It has no ordinary local propagating bulk modes, but it has rich line operators, Hilbert spaces, mapping-class-group actions, and boundary theories.

**“The level is just a coupling constant.”** The level is quantized. Its allowed values depend on trace normalization, global group, and possible spin/framing structures.

**“Metric-independent means no regularization subtlety.”** The quantum theory can depend on framing even though the classical action uses no metric.

**“All Wilson lines are allowed.”** At finite level, allowed line labels are restricted. The precise set depends on the group, level, global form, and quotient choices.

**“Chern–Simons–matter theory is automatically a TQFT.”** Matter fields can introduce local degrees of freedom. Pure Chern–Simons theory is topological; Chern–Simons–matter theories need separate analysis.

**“A boundary is optional decoration.”** Boundaries change gauge invariance. They often require boundary conditions or boundary degrees of freedom.

## Relations to other pages

[Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/) contrasts Chern–Simons theory with $Q$-cohomological topological theories. [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/) gives another metric-independent topological gauge theory, often better suited to higher-form symmetry and finite gauge examples. [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) gives the finite-group analogue.

The [Topological Terms](/symmetry-anomalies-topology/topological-terms/) chapter explains Chern–Simons terms as topological terms in broader QFT. [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) develops Wilson lines and line fusion. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) explains the anomaly-inflow and symmetry-data roles of Chern–Simons-like theories.

## Research status

Pure compact Chern–Simons theory is one of the best-understood examples of TQFT. Its relation to knot invariants, quantum groups, modular tensor categories, WZW conformal blocks, and topological phases is foundational.

Active directions include nonsemisimple and logarithmic variants, spin and fermionic Chern–Simons theories, higher-categorical extensions, 3d bosonization and level-rank dualities, Chern–Simons–matter dynamics, and SymTFT applications to generalized and non-invertible symmetries.

## Exercises

### Exercise 1: Variation of the abelian action

For

$$
S=\frac{k}{4\pi}\int_M A\wedge dA
$$

on a closed three-manifold, show that the equation of motion is $dA=0$.

<details><summary><strong>Solution</strong></summary>

Vary the action:

$$
\delta S=\frac{k}{4\pi}\int_M \delta A\wedge dA+A\wedge d\delta A.
$$

Using

$$
A\wedge d\delta A=d(A\wedge\delta A)+dA\wedge\delta A
$$

and dropping the total derivative on a closed manifold, we get

$$
\delta S=\frac{k}{4\pi}\int_M \delta A\wedge dA+dA\wedge\delta A.
$$

Since $dA$ is a two-form and $\delta A$ is a one-form, $dA\wedge\delta A=\delta A\wedge dA$. Therefore

$$
\delta S=\frac{k}{2\pi}\int_M \delta A\wedge dA.
$$

For arbitrary $\delta A$, the equation of motion is

$$
dA=0.
$$

</details>

### Exercise 2: Why the Yang–Mills term is metric-dependent

Explain why

$$
\int \operatorname{tr}(F\wedge *F)
$$

requires a metric, while the Chern–Simons action does not.

<details><summary><strong>Solution</strong></summary>

The Hodge star $*$ is defined using the metric. It maps $p$-forms to $(d-p)$-forms by using lengths, angles, and the volume form. Thus $F\wedge *F$ depends on the metric.

By contrast,

$$
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right)
$$

is already a three-form built from the connection and exterior derivative. It can be integrated over an oriented three-manifold without a metric.

</details>

### Exercise 3: Boundary term in the variation

Repeat the variation of the abelian Chern–Simons action on a manifold with boundary. What extra term appears?

<details><summary><strong>Solution</strong></summary>

From the computation in Exercise 1,

$$
A\wedge d\delta A=d(A\wedge\delta A)+dA\wedge\delta A.
$$

On a manifold with boundary, the total derivative contributes

$$
\frac{k}{4\pi}\int_{\partial M}A\wedge\delta A.
$$

Thus

$$
\delta S
=
\frac{k}{2\pi}\int_M\delta A\wedge dA
+
\frac{k}{4\pi}\int_{\partial M}A\wedge\delta A.
$$

The boundary term must be canceled or controlled by boundary conditions or boundary degrees of freedom.

</details>

### Exercise 4: Linking phase intuition

In abelian Chern–Simons theory, why should Wilson-line correlators depend on linking rather than on distances?

<details><summary><strong>Solution</strong></summary>

The theory has no metric in its action, so protected Wilson-line correlators cannot depend on distances, angles, or shapes that can be smoothly deformed. However, two closed loops in a three-manifold can have a topological linking number that cannot be removed by smooth deformation without crossing. Therefore the correlator can depend on linking. In abelian Chern–Simons theory, this dependence appears as a phase proportional to the product of charges and the linking number.

</details>

## References

- S. S. Chern and J. Simons, “Characteristic Forms and Geometric Invariants.”
- E. Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989).
- A. M. Polyakov, *Gauge Fields and Strings*, especially the discussion of loop dynamics and gauge holonomy.
- M. Nakahara, *Geometry, Topology and Physics*, for connections, characteristic classes, monopoles, instantons, and Chern–Simons-related geometry.
- T. Frankel, *The Geometry of Physics*, for differential forms, gauge fields, Chern forms, and geometric background.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for Chern–Simons terms and topological quantum matter.
- G. Moore and N. Seiberg, “Classical and Quantum Conformal Field Theory,” for the CFT/TQFT relation.
- E. Witten, *Chern–Simons Gauge Theory as a String Theory*, for large-N and string-theoretic connections.

## Version history

- **2026-06-22:** Initial polished draft. Added action conventions, level quantization caveats, Wilson lines, framing, boundaries, knot invariants, topological phases, anomaly inflow, and exercises.
