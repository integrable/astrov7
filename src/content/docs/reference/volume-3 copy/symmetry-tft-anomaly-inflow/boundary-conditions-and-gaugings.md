---
title: "Boundary Conditions and Gaugings"
description: "Explains how topological boundary conditions in the SymTFT encode choices of gauging, orbifolding, global form, discrete theta terms, and absolute versus relative QFTs."
sidebar:
  label: "Boundary Conditions and Gaugings"
  order: 6
level: Advanced
status: "Polished draft"
source: "Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Freed; modern SymTFT and categorical-symmetry references."
topics:
  - boundary conditions
  - gauging
  - symmetry TFT
  - topological boundary
  - absolute QFT
  - global form
canonicalTopics:
  - symtft-boundary-condition
  - gauging-as-boundary-choice
  - topological-boundary-condition
  - absolute-relative-qft
  - condensation
researchStatus:
  established:
    - "For ordinary finite and higher-form symmetries, changing the topological boundary condition of the SymTFT gives a precise way to encode gauging, orbifolding, global-form choices, and dual symmetry descriptions."
    - "In topological field theories, admissible gaugings are controlled by anomaly-free condensable data, often described by isotropic subgroups, Lagrangian algebras, or topological boundary conditions."
  active:
    - "For categorical, non-invertible, subsystem, spacetime, and gapless boundary symmetries, the relation between boundary conditions, gaugings, defects, and absolute theories is an active research area."
---

## Summary

In the SymTFT viewpoint, a $d$-dimensional theory with symmetry is described using a $(d+1)$-dimensional topological theory placed on a slab. One boundary is the physical QFT. The other boundary is a **topological boundary condition** that specifies how the symmetry is realized.

Changing that topological boundary condition can implement:

- gauging a global symmetry,
- orbifolding a finite symmetry,
- choosing a global form of a gauge group,
- summing over higher-form backgrounds,
- adding discrete theta terms,
- choosing which defects are genuine,
- or passing between dual descriptions.

The slogan is:

$$
\text{gauging choice}
=
\text{topological boundary condition in the SymTFT}.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![A SymTFT slab with a physical boundary on one side and several topological boundary choices on the other, representing ungauged, gauged, and discrete-theta versions of a theory.](/figures/symmetry-anomalies-topology/symtft-boundary-gaugings.svg)

<figcaption>

A SymTFT separates the physical boundary theory from the topological boundary choice. Moving between topological boundary conditions can represent gauging, orbifolding, quotienting, changing global form, or adding discrete theta data. The bulk symmetry theory is the common bookkeeping device.

</figcaption>
</figure>

This page explains the dictionary carefully enough to use it, without pretending that every case reduces to an elementary subgroup sum.

## Prerequisites

Read [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/), [Bulk-Boundary Viewpoint](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/bulk-boundary-viewpoint/), [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/), and [SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/) first.

Useful earlier pages include [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/), and [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/).

## Core idea

A global symmetry can be probed by background fields. Gauging means summing over those backgrounds. But the phrase “sum over backgrounds” hides many choices:

1. Which backgrounds are allowed?
2. Which topological sectors are summed?
3. Are there discrete theta weights?
4. Which charged operators remain genuine?
5. Which dual symmetry appears after gauging?
6. What happens to boundaries and defects?

The SymTFT packages these choices geometrically. Let $\mathcal Z_{\mathrm{sym}}$ be the symmetry topological field theory in one higher dimension. Put it on an interval:

$$
X_{d+1}=M_d\times I.
$$

At one end sits the physical boundary condition $\mathcal B_{\mathrm{phys}}$ encoding the QFT. At the other end sits a topological boundary condition $\mathcal B_{\mathrm{top}}$ encoding the choice of absolute theory:

$$
Z_{\mathcal T}^{\mathcal B_{\mathrm{top}}}[M_d]
=
Z_{\mathcal Z_{\mathrm{sym}}}\bigl[M_d\times I;\mathcal B_{\mathrm{top}},\mathcal B_{\mathrm{phys}}\bigr].
$$

Changing $\mathcal B_{\mathrm{top}}$ changes how the same symmetry data is converted into an ordinary $d$-dimensional partition function.

## Absolute and relative theories

A standalone QFT should assign a number to a closed spacetime, after all background and boundary choices have been specified. Such a theory is sometimes called **absolute**.

An anomalous or symmetry-relative theory may instead assign a vector, a line, or an object in the state space of a bulk topological theory. It becomes a number only after pairing with another boundary condition.

The SymTFT viewpoint makes this literal. The physical boundary $\mathcal B_{\mathrm{phys}}$ by itself may not define a number. Pairing it with $\mathcal B_{\mathrm{top}}$ does.

The same physical boundary can be paired with different topological boundaries:

$$
\mathcal B_{\mathrm{top}}^{(1)},\quad
\mathcal B_{\mathrm{top}}^{(2)},\quad
\mathcal B_{\mathrm{top}}^{(3)}.
$$

These pairings can produce different absolute theories that share a common underlying symmetry structure. In familiar language, they can be related by gauging, orbifolding, electromagnetic duality, or changing global form.

:::note[Source note: relative does not mean incomplete]
A relative theory is not a mistake. It is a theory whose partition function naturally lives in a background-dependent vector space or line. Choosing a topological boundary condition is one way to extract an absolute theory from it.
:::

## Finite-group gauging as a boundary choice

For an ordinary finite group $G$, a theory with non-anomalous $G$ symmetry can be gauged by summing over $G$ bundles:

$$
Z_{\mathcal T/G}[M]
=
\frac{1}{|G|^{b_0(M)}}\sum_{[A]\in \mathrm{Bun}_G(M)}
Z_{\mathcal T}[M;A],
$$

up to standard normalization conventions.

In the SymTFT, the possible background $G$ bundles are encoded as bulk topological data. The ungauged theory and the gauged theory correspond to different topological boundary conditions. Roughly:

| Boundary choice | Boundary interpretation |
|---|---|
| Fix background data | Ungauged theory with global $G$ symmetry |
| Sum over background data | Gauged or orbifolded theory |
| Sum with topological weight | Gauging with discrete torsion or theta term |

For abelian $G$, gauging often produces a dual symmetry $\widehat G$ acting on disorder or twisted-sector operators. In higher dimensions and for higher-form symmetries, the dual symmetry has shifted form degree. The boundary condition determines which side of this duality is visible as an ordinary global symmetry.

## Higher-form gauging

For an abelian $q$-form symmetry $A$, the background is a $(q+1)$-form gauge field $B_{q+1}$. Gauging means summing over $B_{q+1}$, with possible topological weights.

The effect is not merely to “remove charged operators.” It changes which extended operators are genuine. A line charged under a one-form symmetry may cease to be a genuine line after gauging unless it is attached to an appropriate topological surface. Conversely, disorder operators or dual defects may become genuine.

In the SymTFT, this is boundary behavior of bulk defects. A bulk defect can end on a topological boundary if it is condensed or allowed by that boundary condition. Thus the set of genuine boundary operators is controlled by which bulk topological defects can terminate at the chosen boundary.

This is the geometric reason why gauging and line-operator spectra are inseparable.

## Global form and line operators

In gauge theory, changing the global form of the gauge group can be described as gauging a higher-form symmetry. For example, local Lie algebra data may be the same for $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$, but their line operators and background bundles differ.

The SymTFT viewpoint packages this as a choice of boundary condition in the topological theory governing the one-form symmetry. Different boundary choices select different maximal mutually local sets of line operators. Discrete theta angles are additional topological weights in the gauging sum.

The lesson is:

$$
\text{global form}
+
\text{line spectrum}
+
\text{discrete theta data}
\quad
=
\quad
\text{boundary condition data}.
$$

This is why a Lagrangian Lie algebra is not enough to specify a gauge theory. The absolute theory also needs the topological boundary choice.

## Condensation language

In many topological examples, a boundary condition is specified by a set of topological defects that can end on the boundary. Physically, one says those defects are **condensed** at the boundary.

For a simple abelian anyon theory, a gapped boundary may be described by a subgroup $L$ of line operators satisfying a trivial mutual braiding condition:

$$
\langle \ell,\ell'\rangle=1
\qquad
\text{for all }\ell,\ell'\in L.
$$

A maximal such subgroup is often called Lagrangian. Condensing $L$ means that lines in $L$ can end on the boundary and are treated as trivial there. Lines with nontrivial braiding with $L$ cannot freely end; they are confined or projected out relative to that boundary.

For categorical symmetries, the corresponding language uses algebra objects, module categories, or condensable defects. The details are richer, but the idea is the same:

$$
\text{boundary condition}
\quad \leftrightarrow \quad
\text{choice of condensable topological data}.
$$

:::caution[Do not over-universalize subgroup language]
Subgroups are adequate for many ordinary finite and abelian higher-form examples. Nonabelian, non-invertible, fermionic, and higher-categorical cases require more general condensable algebra or boundary-condition data.
:::

## Boundary conditions and anomalies

Not every desired boundary condition exists. An anomaly is precisely an obstruction to making certain boundary choices.

If a symmetry has a ’t Hooft anomaly, then the boundary condition corresponding to “gauge this symmetry on its own” is not available unless the anomaly is cancelled or absorbed by a bulk. In SymTFT language, the relevant topological defects fail to form a condensable set, or the would-be boundary condition is obstructed.

This recovers the familiar rule:

$$
\text{anomalous symmetry}
\quad \Rightarrow \quad
\text{cannot be gauged as a standalone operation}.
$$

It also generalizes the rule. For higher-form and non-invertible symmetries, the obstruction may not look like a local current anomaly. It may appear as inconsistent defect-network moves, nontrivial associator phases, or the absence of a compatible topological boundary.

## Boundary conditions for physical boundaries

There are two kinds of boundary in the discussion, and confusing them is fatal.

The **topological boundary** of the SymTFT is the auxiliary boundary used to extract an absolute theory or choose a gauging.

The **physical boundary** of the QFT is an actual boundary condition, interface, or defect in the $d$-dimensional theory.

The SymTFT can describe both, but they play different roles. A physical boundary may carry a charge under the symmetry, support boundary degrees of freedom, or have its own anomaly. A topological boundary is part of the symmetry-theory construction that tells us which absolute bulk theory we are discussing.

Recent boundary-SymTFT work studies how physical boundary conditions themselves transform under generalized and categorical symmetries. In that setting, boundary conditions can carry generalized charges just as local or extended operators do.

## Discrete theta terms

When gauging, one may multiply the sum over backgrounds by an invertible topological action:

$$
Z_{\mathrm{gauged},\theta}[M]
=
\sum_{[A]} Z_{\mathcal T}[M;A]\,
\exp\bigl(iS_{\theta}[A]\bigr).
$$

For finite groups, these are often called discrete torsion or Dijkgraaf–Witten weights. For higher-form symmetries, the analogues are discrete theta terms or quadratic refinements. In gauge theory, they can change the spectrum of genuine line operators and the action of dual symmetries.

In the SymTFT, these choices are different topological boundary conditions or boundary counterterms. They are not afterthoughts; they are part of the definition of the absolute theory.

## A working dictionary

| SymTFT object | Boundary/QFT meaning |
|---|---|
| Bulk topological defect | Symmetry operator, charge probe, or background-changing operator |
| Topological boundary condition | Choice of gauging, global form, orbifold, or absolute theory |
| Defect ending on boundary | Operator/defect condensed or made trivial by that boundary |
| Defect unable to end | Nontrivial charge, projected sector, or confined object |
| Boundary counterterm | Discrete theta term or local contact-term convention |
| Obstructed boundary | ’t Hooft anomaly or inconsistent gauging |
| Pair of boundary conditions | Interface, duality wall, or map between absolute theories |

This dictionary is intentionally schematic. Its value is that it unifies several constructions that otherwise look unrelated.

## Example: finite abelian symmetry

Let $\mathcal T$ have a non-anomalous finite abelian symmetry $A$. The ungauged theory has charged local operators. Gauging $A$ projects onto invariant local operators and introduces twisted sectors. The gauged theory has a dual $(d-2)$-form symmetry $\widehat A$ acting on codimension-two disorder defects.

In the SymTFT, the two descriptions come from different boundary conditions. One boundary makes the original $A$ symmetry visible. The other condenses the corresponding topological defects and makes the dual $\widehat A$ symmetry visible.

Thus gauging is not merely a quotient. It is a change of polarization in the topological symmetry theory.

## Example: one-form symmetry in four dimensions

A four-dimensional gauge theory with a finite one-form center symmetry can be changed by gauging a subgroup of that one-form symmetry. This changes which Wilson lines are genuine and can change the global form of the gauge group.

For $SU(N)$ Yang–Mills, gauging the full electric $\mathbb Z_N$ one-form symmetry leads toward a $PSU(N)$-type theory, with discrete theta choices. The local gluon dynamics is unchanged, but the allowed line operators and background bundles change.

In SymTFT language, these are different boundary conditions for the topological theory controlling the one-form symmetry. The same local Lagrangian data can correspond to different absolute QFTs because the boundary condition data differ.

## Common pitfalls

**“Gauging is just dividing by a group.”** Gauging includes summing over backgrounds, choosing normalization, specifying topological sectors, adding possible theta weights, and tracking operators and defects.

**“The SymTFT boundary is a physical boundary of spacetime.”** Sometimes one studies physical boundaries too, but the topological boundary used to define an absolute theory is an auxiliary boundary in the slab construction.

**“All boundary conditions are allowed.”** Anomalies obstruct some boundary choices. In topological language, not every set of defects is condensable.

**“Gauging only affects local operators.”** Gauging often has its most important effect on extended operators: Wilson lines, ’t Hooft lines, surface defects, and disorder operators.

**“Changing global form is a small convention.”** It can change genuine line operators, background bundles, one-form symmetries, anomalies, and discrete theta sectors.

**“Subgroup condensation is the whole story.”** It is a good first model for abelian invertible defects. Non-invertible and categorical settings require algebra objects, module categories, or higher-categorical boundary data.

## Relations to other pages

[Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) explains the background-field version of higher-form gauging. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) explains the categorical and two-dimensional defect-network viewpoint. This page explains the SymTFT boundary-condition viewpoint.

[Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/) and [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) provide the operator examples where boundary choices become visible.

## Research status

For finite ordinary symmetries, abelian higher-form symmetries, and many gauge-theory global-form choices, the boundary-condition picture is well established and computationally useful. For fully extended TQFTs, it fits naturally with condensation and boundary classification.

Active research focuses on gapless physical boundaries, non-invertible and categorical symmetry boundary conditions, subsystem symmetries, fermionic refinements, spacetime symmetries, and the use of SymTFT boundary data to classify phases and defects.

## Exercises

### Exercise 1: Gauging as a sum

A finite group $G$ acts non-anomalously on a theory $\mathcal T$. What additional data, besides the group $G$, must be specified to define the gauged theory carefully?

<details><summary><strong>Solution</strong></summary>

One must specify which $G$ backgrounds or bundles are summed over, the normalization of the sum, possible discrete torsion or theta weights, and the resulting operator spectrum. On manifolds with boundary, one must also specify boundary conditions and how background data restricts to the boundary.

</details>

### Exercise 2: Condensed line operators

Suppose a topological boundary condenses a set $L$ of line operators. What does it mean for a line $\ell\in L$ to be condensed?

<details><summary><strong>Solution</strong></summary>

It means that $\ell$ can end on the boundary and is treated as topologically trivial relative to that boundary. Lines that braid nontrivially with condensed lines generally cannot end freely on that boundary and may be projected out, confined, or charged under the remaining boundary symmetry.

</details>

### Exercise 3: Anomaly obstruction

Why does an anomalous symmetry fail to define a standalone gauged theory?

<details><summary><strong>Solution</strong></summary>

Gauging requires summing over background fields while maintaining gauge invariance under transformations of those backgrounds. A ’t Hooft anomaly means that no choice of local counterterm makes the background-field partition function gauge invariant. Therefore the gauging sum is not well-defined as a standalone $d$-dimensional theory unless the anomaly is cancelled or supplied by a bulk inflow theory.

</details>

### Exercise 4: Global form is boundary data

Explain why two gauge theories with the same Lie algebra can correspond to different SymTFT boundary conditions.

<details><summary><strong>Solution</strong></summary>

The Lie algebra controls local gauge-boson dynamics, but not the global form of the gauge group, allowed bundles, discrete theta terms, or the spectrum of genuine line operators. Those choices are topological data. In the SymTFT, they are represented by different topological boundary conditions for the one-higher-dimensional symmetry theory.

</details>

## References

- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- O. Aharony, N. Seiberg, and Y. Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories.”
- D. Gaiotto and T. Johnson-Freyd, “Condensations in Higher Categories.”
- L. Bhardwaj, C. Copetti, D. Pajer, and S. Schäfer-Nameki, “Boundary SymTFT.”
- C. Copetti, “Defect Charges, Gapped Boundary Conditions, and the Symmetry TFT.”
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for topological phases and response.
- M. Nakahara, *Geometry, Topology and Physics*, for bundle, holonomy, and characteristic-class background.

## Version history

- **2026-06-20:** Initial polished draft. Added SymTFT boundary-condition dictionary, finite and higher-form gauging examples, condensation language, anomaly obstructions, and exercises.
