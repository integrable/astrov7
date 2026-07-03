---
title: "Defect Correlation Functions"
description: "Explains how to define, compute, and interpret correlation functions containing line, surface, wall, boundary, and topological defect insertions."
sidebar:
  label: "Defect Correlation Functions"
  order: 10
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Ch. 7; Gaiotto–Kapustin–Seiberg–Willett; standard Wilson-loop, CFT-defect, TQFT, and anomaly-inflow references."
topics:
  - defect correlation functions
  - extended operators
  - linking
  - framing
  - defect-local operators
  - bulk-to-defect OPE
canonicalTopics:
  - defect-correlator
  - defect-local-operator
  - bulk-defect-ope
  - linking-phase
  - framing
researchStatus:
  established:
    - "Correlation functions with extended insertions are standard in gauge theory, CFT, TQFT, statistical field theory, and generalized-symmetry applications."
    - "Defects can change selection rules, allow new one-point functions, introduce defect-local operator algebras, and detect linking or framing data invisible to ordinary local correlators."
  active:
    - "Defect correlators in non-invertible, higher-categorical, anomalous, fermionic, and strongly coupled settings remain active research topics."
---

## Summary

A **defect correlation function** is a QFT expectation value with one or more extended insertions:

$$
\left\langle
\mathcal D_1(M_1)\cdots\mathcal D_k(M_k)\,
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle.
$$

The defects $\mathcal D_i(M_i)$ may be Wilson lines, ’t Hooft lines, surface operators, domain walls, boundaries, interfaces, disorder defects, twist defects, or topological symmetry operators. The local operators $\mathcal O_j(x_j)$ may live in the bulk or on one of the defects.

Defect correlators answer questions that ordinary local correlators cannot:

- How does a Wilson loop respond to confinement, screening, or topological order?
- What phase is produced when a line links a surface?
- What one-point functions become allowed near a boundary or defect?
- Which local operators can live on a line, wall, or interface?
- How do topological defects act on charged insertions?
- Which framing, spin, or background data must be specified?

The basic point is:

$$
\text{a defect changes the arena in which correlation functions are evaluated}.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![A schematic defect correlator with a loop linked with a surface, bulk local operators, and defect-local operators.](/figures/symmetry-anomalies-topology/defect-correlator-linking.svg)

<figcaption>

A defect correlator can depend on support geometry, linking, orientation, framing, and defect-local insertions. In a topological subsector, smooth metric dependence disappears but linking and junction data may remain.

</figcaption>
</figure>

## Prerequisites

You should know [Local Versus Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/local-versus-extended-operators/), [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/), [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/), and [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/).

It is also useful to know ordinary local correlation functions, path-integral sources, and basic topology of linking. The page uses “support” to mean the submanifold on which an extended operator lives.

## Core idea

A local correlator is specified by operator labels and insertion points:

$$
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle.
$$

A defect correlator requires more data. For each defect one must specify:

| Data | Meaning |
|---|---|
| Defect type | Wilson line, surface operator, twist defect, boundary, interface, topological operator, and so on. |
| Support | The submanifold $M_p$ where the defect lives. |
| Orientation | Needed for charges, holonomies, integrals, and dual defects. |
| Framing or normal data | Needed when self-linking, spin, Chern–Simons terms, or regularized coincident defects matter. |
| Boundary and junction data | Needed if defects end, meet, or fuse. |
| Defect-local insertions | Operators living on the defect worldvolume. |
| Background fields | Needed to define charged defects, twisted sectors, or anomaly-sensitive phases. |

In ordinary local QFT, moving $x_i$ changes the correlator. In a topological defect sector, moving a defect smoothly may not change the correlator unless it crosses another insertion or changes a linking number. That is why defect correlators naturally mix analysis and topology.

## Setup and notation

A defect supported on a $p$-dimensional submanifold $M_p$ is denoted

$$
\mathcal D(M_p).
$$

A local operator living on the defect is written with a hat:

$$
\widehat{\mathcal O}(y),
\qquad y\in M_p.
$$

A mixed bulk-defect correlator has the form

$$
\left\langle
\mathcal D(M_p)\,
\widehat{\mathcal O}_1(y_1)\cdots\widehat{\mathcal O}_m(y_m)\,
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle.
$$

Here $y_i$ are coordinates along the defect, while $x_j$ are bulk points away from the defect support unless a limiting prescription is specified.

If a defect is topological, the correlator is invariant under smooth deformations of $M_p$ that avoid crossings, endpoints, junctions, and changes of background structure. If the defect is not topological, the correlator can depend on lengths, angles, extrinsic curvature, separation from other defects, and regulator choices.

:::note[Source note]
The convention $\widehat{\mathcal O}$ for defect-local operators is common but not universal. Some CFT and boundary-CFT references write boundary operators as $\psi$, $\hat\phi$, or simply $\mathcal O_{\partial}$. This volume uses hats when confusion with bulk local operators is likely.
:::

## Wilson-loop expectation values

A Wilson-loop expectation value is the prototype of a defect correlator:

$$
\langle W_R(C)\rangle
=
\left\langle
\operatorname{tr}_R P\exp\left(i\oint_C A\right)
\right\rangle.
$$

The curve $C$ is part of the operator. Changing its shape usually changes the answer. In a confining gauge theory, large rectangular Wilson loops can diagnose the potential between heavy external charges. In a topological theory, the same kind of loop expectation value may depend only on the knot or link class of $C$, together with framing and representation labels.

For multiple Wilson loops,

$$
\langle W_{R_1}(C_1)\cdots W_{R_k}(C_k)\rangle,
$$

the relative embedding matters. In a topological theory, the answer can become a link invariant. In an ordinary gauge theory, the answer can also depend on metric data such as sizes, distances, cusps, and perimeter regularization.

The same formula therefore carries different physical meanings in different QFTs:

| Theory type | What the loop correlator probes |
|---|---|
| Gauge theory with dynamics | Screening, confinement, heavy-charge potentials, cusp anomalous dimensions. |
| Chern–Simons-like TQFT | Knot and link invariants, framing, fusion, modular data. |
| Higher-form symmetry setting | Charge of line operators under surface symmetry operators. |
| Holographic or large-$N$ setting | Minimal surfaces or saddle geometries, when applicable. |

## Linking phases

Some of the cleanest defect correlators are pure linking phases. In a $d$-dimensional topological or topological-response theory, a $p$-dimensional defect and a $(d-p-1)$-dimensional defect can link. The correlator may contain a phase

$$
\exp\left(2\pi i\,q_1q_2\,\operatorname{Link}(M_p,N_{d-p-1})/N\right)
$$

in a finite abelian example, or a continuous analogue for $U(1)$-type pairings.

The exact coefficient depends on the theory and normalization, but the structure is important: the correlator detects topology of the embedding, not local metric distance.

A simple physical example is the Aharonov–Bohm effect. A charged particle worldline linked with magnetic flux acquires a phase. In modern language, this is a line-defect/surface-defect correlation effect. In higher-form symmetry language, a topological symmetry operator linking a charged extended operator measures its charge.

:::note[Convention-sensitive point]
The sign of a linking phase depends on orientation conventions for the two defects, the ambient manifold, and the normalization of charges and background fields. Pages using a specific topological action, such as BF theory or Chern–Simons theory, will restate the normalization.
:::

## Defect-local operators

A defect can support its own local operators. If a line defect $L$ is present, one may insert operators at points along the line:

$$
\langle L(C)\,\widehat{\mathcal O}_1(s_1)\widehat{\mathcal O}_2(s_2)\rangle.
$$

If a wall or boundary is present, one can have local operators living on the wall worldvolume. These are not bulk operators restricted to the wall, although some may arise that way. They are operators in the defect theory.

Defect-local operators form an operator algebra of their own. For a line defect, their ordering along the line matters. For a topological line, the defect-local theory can be topological quantum mechanics. For a conformal defect, the defect-local operators are constrained by the subgroup of the conformal group preserving the defect.

Defect-local operators are essential because fusing defects often produces not only a new defect but also defect-local insertions. They also describe excitations, endpoints, junctions, and boundary degrees of freedom.

## Bulk-to-defect OPE

When a bulk local operator approaches a defect, it can be expanded in defect-local operators. Let $x=(y,x_\perp)$, where $y$ is parallel to the defect and $x_\perp$ is transverse. The schematic bulk-to-defect OPE is

$$
\mathcal O(x_\perp,y)
\sim
\sum_{\widehat{\mathcal O}}
b_{\mathcal O\widehat{\mathcal O}}\,
|x_\perp|^{\widehat\Delta-\Delta}\,
\widehat{\mathcal O}(y)+\cdots.
$$

Here $\Delta$ is the scaling dimension of the bulk operator and $\widehat\Delta$ is the scaling dimension of the defect-local operator in a conformal setting. Away from conformal theories, the expansion still exists as a short-distance expansion but the simple power law is replaced by scale-dependent coefficients.

This OPE explains why one-point functions can become nonzero in the presence of a defect. In the vacuum without a defect, a nontrivial primary may have zero one-point function. With a planar conformal defect, symmetry can allow

$$
\langle \mathcal O(x_\perp,y)\rangle_{\mathcal D}
=
\frac{a_{\mathcal O}}{|x_\perp|^\Delta}
$$

for scalar bulk primaries compatible with the defect symmetries.

## Defect OPE and fusion inside correlators

Defect fusion becomes visible inside correlators. If two defects approach each other, one can write

$$
\left\langle
\mathcal D_a(M+\epsilon n)\mathcal D_b(M)\,\cdots
\right\rangle
\sim
\sum_c C_{ab}{}^c(\epsilon)
\left\langle
\mathcal D_c(M)\,\cdots
\right\rangle
+\cdots.
$$

If the defects are topological, this becomes the fusion rule

$$
\mathcal D_a\times\mathcal D_b=\sum_c N_{ab}{}^c\mathcal D_c.
$$

If they are not topological, the ellipses may include defect-local operators, divergent counterterms, and RG flow on the fused defect. A defect correlator is therefore not just a number; it is a diagnostic for the operator content of the defect sector.

This is especially important for line defects. Parallel lines can fuse into a new line sector, with defect-local excitations encoding the short-distance spectrum between them. Boundaries and interfaces behave similarly: bringing an interface close to a boundary gives a new boundary condition plus possible boundary degrees of freedom.

## Ward identities with defects

A conserved current inserted into a correlator with defects can have extra contact terms when the current crosses or approaches a defect.

For a topological symmetry defect $U_g(\Sigma)$, the Ward identity is geometric: deform $\Sigma$ freely until it crosses charged operators or other defects. Crossing a charged local operator transforms it. Crossing another defect may transform the defect label or create a junction.

For an infinitesimal continuous symmetry with current $j^\mu$, the divergence equation in the presence of a defect can include bulk contact terms and defect contact terms:

$$
\partial_\mu j^\mu(x)
=
\sum_i \delta^{(d)}(x-x_i)\,\delta_i
+
\delta_{\mathcal D}(x)\,\widehat{\mathcal A}(y),
$$

schematically. The last term means that the symmetry may act nontrivially on defect-local degrees of freedom, or that the defect may carry an anomaly or inflow contribution. The exact expression depends on the theory and on the defect.

This is the correlator-level reason defects are so useful in anomaly physics: they can localize symmetry variation on a submanifold.

## Renormalization and divergences

Defect correlators often have divergences not present in purely local correlators. Common examples include:

| Divergence | Where it appears |
|---|---|
| Perimeter divergence | Wilson loops in ordinary gauge theory. |
| Area or volume divergence | Higher-dimensional defects with tension-like counterterms. |
| Endpoint divergence | Open lines ending on charged or boundary operators. |
| Cusp divergence | Wilson lines with corners or lightlike segments. |
| Self-linking ambiguity | Framed topological line operators. |
| Boundary short-distance divergence | Bulk operators approaching a boundary or defect. |

These divergences are not bugs. They mean that extended operators, like local composite operators, must be defined by a renormalization prescription. One may need counterterms supported on the defect worldvolume:

$$
S_{\mathcal D}\to S_{\mathcal D}+\int_{M_p} d^p y\,\lambda_i\widehat{\mathcal O}_i(y).
$$

A well-defined defect operator is a renormalized object, not merely a formal expression.

## Framing and self-linking

When two distinct defects link, the linking number can be topological. When a defect links with itself, one needs a way to displace one copy from the other. That displacement is a framing.

In Chern–Simons theory, expectation values of Wilson loops depend on framing unless a compensating convention is chosen. In fermionic theories, spin structure can play a similar role. In topological-response theories, changing a framing can shift phases.

The operational rule is:

$$
\text{self-correlators of extended objects often need extra normal data}.
$$

For students, the warning is simple: a curve, surface, or wall may not be enough information to define the correlator. Orientation, framing, spin structure, and background bundles can be part of the operator definition.

## Boundaries and one-point functions

A boundary condition is a codimension-one defect. Correlators in the presence of a boundary are defect correlators. If the boundary is planar, translational symmetry along the boundary remains, while translation perpendicular to the boundary is broken.

As a result, one-point functions that vanish in the bulk vacuum may become nonzero:

$$
\langle\mathcal O(x_\perp,y)\rangle_{\partial}
\neq0.
$$

In boundary CFT, a scalar primary of dimension $\Delta$ has the form

$$
\langle\mathcal O(x_\perp,y)\rangle_{\partial}
=
\frac{a_{\mathcal O}}{|x_\perp|^\Delta}
$$

when allowed by the remaining symmetries.

Similarly, interface correlators can compare operator data across two theories. A topological interface can sometimes transport operators from one side to the other. A non-topological interface can support its own local dynamics.

## Common pitfalls

**“A defect correlator is just a local correlator with an integral.”** Sometimes, but many defects are defined by holonomy, singular boundary conditions, monodromy, topology, or boundary degrees of freedom. They are not generally smeared local operators.

**“Topological means independent of all choices.”** Topological correlators can still depend on linking, framing, orientation, spin structure, background bundles, and junction labels.

**“Wilson loops are finite as written.”** In ordinary gauge theory, Wilson loops need renormalization. Perimeter and cusp divergences are physical parts of the definition.

**“A boundary operator is just a bulk operator evaluated at the boundary.”** Some boundary operators arise as limits of bulk operators, but a boundary condition can have independent degrees of freedom and independent local operators.

**“A vanishing bulk one-point function must still vanish with a defect.”** A defect reduces symmetry. New one-point functions and tensor structures can become allowed.

**“Fusion rules are enough to determine all correlators.”** Fusion rules are only part of the data. Junction spaces, associators, braiding, framing phases, and defect-local operator spectra can also matter.

## Relations to other pages

[Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) explains the limiting process in which nearby defects are replaced by effective defects. This page explains how that process appears in correlation functions.

[Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/), and [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) give the main extended-operator examples. [Boundaries and Interfaces](/symmetry-anomalies-topology/defects-extended-operators/boundaries-and-interfaces/) develops the codimension-one case.

[Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) uses linking of symmetry operators with charged extended operators as the generalized Ward identity. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) explains how anomaly phases in defect correlators are captured by a one-higher-dimensional bulk.

## Research status

Defect correlators are standard in Wilson-loop physics, Chern–Simons theory, boundary and defect CFT, statistical field theory, TQFT, and generalized symmetry.

Active research directions include non-invertible defect correlators in higher dimensions, strongly coupled defect CFT data, categorical and symmetry-TFT formulations, fermionic and antiunitary defects, anomaly-sensitive junctions, and the role of extended operators in quantum information and holography.

## Exercises

### Exercise 1: Linking charge measurement

Suppose a topological surface operator $U_\alpha(\Sigma)$ links a line operator $L_q(C)$ once and acts by

$$
U_\alpha(\Sigma)\,L_q(C)=e^{i\alpha q}L_q(C)
$$

inside correlators. What happens if the linking number is $n$?

<details><summary><strong>Solution</strong></summary>

If one linking gives the phase $e^{i\alpha q}$, then $n$ oriented linkings give the phase

$$
e^{i n\alpha q}.
$$

The sign of $n$ depends on orientation conventions. This is the higher-form symmetry analogue of measuring the charge of a local operator by surrounding it with an ordinary symmetry operator.

</details>

### Exercise 2: Bulk-to-defect OPE power

In a defect CFT, a scalar bulk primary $\mathcal O$ of dimension $\Delta$ approaches a planar defect. A defect operator $\widehat{\mathcal O}$ has dimension $\widehat\Delta$. What power of the transverse distance appears in the leading OPE coefficient?

<details><summary><strong>Solution</strong></summary>

Dimensional analysis along the defect gives

$$
\mathcal O(x_\perp,y)
\sim
b_{\mathcal O\widehat{\mathcal O}}\,
|x_\perp|^{\widehat\Delta-\Delta}
\widehat{\mathcal O}(y)+\cdots.
$$

The power is $\widehat\Delta-\Delta$. This ensures that both sides have the same scaling dimension.

</details>

### Exercise 3: Why framing is extra data

Explain why a self-linking number for a loop requires a framing.

<details><summary><strong>Solution</strong></summary>

A loop does not have a well-defined linking number with itself because it coincides with itself. To define self-linking, one first creates a nearby displaced copy of the loop. The displacement requires a choice of normal vector field along the loop, which is a framing. The linking number of the original loop with the displaced loop can depend on that framing.

</details>

### Exercise 4: Boundary one-point function

Why can a scalar operator have a nonzero one-point function in the presence of a planar boundary even if its one-point function vanishes in the full-space vacuum?

<details><summary><strong>Solution</strong></summary>

The boundary breaks part of the spacetime symmetry. In full space, translation and rotation symmetry can forbid nonzero one-point functions for nontrivial operators. With a planar boundary, the transverse distance $x_\perp$ becomes an invariant variable, and symmetry allows

$$
\langle\mathcal O(x_\perp,y)\rangle_{\partial}
=
\frac{a_{\mathcal O}}{|x_\perp|^\Delta}
$$

for a scalar primary of dimension $\Delta$, if internal symmetry and boundary conditions allow it. The coefficient $a_{\mathcal O}$ is boundary data.

</details>

## References

- K. G. Wilson, “Confinement of Quarks,” for Wilson-loop expectation values as gauge-theory observables.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the discussion of non-Abelian phase factors and loop dynamics.
- M. Srednicki, *Quantum Field Theory*, §82, for Wilson loops and lattice/confinement orientation.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for linking of topological symmetry operators with charged extended operators.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for background fields, line operators, and topological couplings.
- O. Aharony, N. Seiberg, and Y. Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line operators and global-form data.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for boundary and defect correlators in two-dimensional CFT.
- J. L. Cardy, “Conformal Invariance and Surface Critical Behavior,” for boundary CFT one-point and bulk-boundary OPE ideas.
- E. Witten, “Quantum Field Theory and the Jones Polynomial,” for Chern–Simons Wilson-loop correlators and framing.

## Version history

- **2026-06-20:** Initial polished draft. Added mixed bulk-defect correlators, linking phases, defect-local operators, bulk-to-defect OPE, defect OPE, Ward identities, renormalization, framing, and exercises.
