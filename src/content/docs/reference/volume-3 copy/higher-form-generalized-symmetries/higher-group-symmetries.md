---
title: "Higher-Group Symmetries"
description: "Explains higher-group symmetries as mixed symmetry structures involving ordinary and higher-form symmetries, with Postnikov data, correlated background fields, modified Ward identities, and QFT examples."
sidebar:
  label: "Higher-Group Symmetries"
  order: 7
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Cordova–Dumitrescu–Intriligator; Kapustin–Seiberg; Benini–Cordova–Hsin; standard higher-form and anomaly references."
topics:
  - higher-group symmetry
  - two-group symmetry
  - higher-form symmetry
  - Postnikov class
  - mixed backgrounds
  - anomaly matching
canonicalTopics:
  - higher-group-symmetry
  - two-group-symmetry
  - postnikov-class
  - mixed-higher-form-background
  - modified-ward-identity
researchStatus:
  established:
    - "Higher-group symmetry is the natural language for symmetry structures in which ordinary and higher-form symmetries do not factor as an independent product."
    - "For a two-group built from a zero-form symmetry and an Abelian one-form symmetry, the mixing is encoded by an action on the one-form symmetry and a Postnikov class."
  active:
    - "Precise higher-group, non-invertible, fermionic, and symmetry-TFT formulations remain active research areas, especially in strongly coupled and non-Lagrangian QFT."
---

## Summary

A **higher-group symmetry** is a symmetry structure in which symmetries of different form degrees are mixed. The simplest and most common case is a **two-group symmetry**, involving an ordinary zero-form symmetry $G$ and an Abelian one-form symmetry $A$.

If the symmetry were just a product, the background fields would be independent:

$$
A_G\quad\text{for }G,
\qquad
B_2\quad\text{for }A.
$$

In a two-group, they are not independent. Turning on a background $G$ gauge field can force a correlated transformation or constraint on the two-form background $B_2$. The mixing is measured by a **Postnikov class**, often denoted

$$
\beta\in H^3(BG,A),
$$

in the finite-group topological setting. Schematic background data obeys

$$
\delta B_2 = \beta(A_G)
$$

or, in continuum notation, a modified gauge-transformation or Bianchi-type relation.

The slogan is:

$$
\text{higher-group symmetry}
=
\text{ordinary and higher-form symmetries glued together}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagram showing zero-form background data and one-form background data connected by a Postnikov class, illustrating that the symmetry is not a direct product.](/figures/symmetry-anomalies-topology/higher-group-symmetry-backgrounds.svg)

<figcaption>

In a product symmetry, the zero-form background $A_G$ and one-form background $B_2$ are independent. In a two-group symmetry, the Postnikov class $\beta$ ties them together: changing or curving the $G$ background induces a required shift or constraint on $B_2$.

</figcaption>
</figure>

Higher-group symmetry is the first step beyond “a list of independent symmetry groups.” It teaches a lesson that becomes even more important for non-invertible symmetry and symmetry TFT: the symmetry of a QFT is often structured data, not a product of independent factors.

## Prerequisites

Read [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/), [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/), [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/), and [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/).

The mathematical prerequisites are modest for a first pass: know what a group action is, know that a one-form symmetry acts on line operators, and accept that discrete background gauge fields can be represented by cocycles. The cohomology group $H^3(BG,A)$ appears here as a label for twisting data; its detailed construction belongs to the Mathematical Toolkit.

## Core idea

A product of symmetries means that the symmetry operations can be specified independently. For a zero-form symmetry $G$ and a one-form symmetry $A$, the product symmetry would be

$$
G\times A^{(1)}.
$$

A background for this product consists of independent data:

$$
(A_G,B_2).
$$

Gauge-transforming $A_G$ does not require changing $B_2$, and gauge-transforming $B_2$ does not require changing $A_G$.

A higher-group symmetry replaces this independence by compatibility. A zero-form symmetry transformation may act on the one-form symmetry, and it may also change the one-form background by a fixed topological rule. In a two-group, the rule is encoded by Postnikov data.

There are two ingredients:

1. an action of $G$ on the Abelian group $A$ of one-form charges;
2. a Postnikov class $\beta$ that says how $G$ background fields source or twist $A$ background fields.

The first ingredient is familiar from semidirect products. The second is genuinely higher: it ties a two-form background to a zero-form background.

## Product symmetry versus two-group symmetry

A product symmetry has independent defects. A zero-form symmetry defect labeled by $g\in G$ is codimension one. A one-form symmetry defect labeled by $a\in A$ is codimension two in four dimensions.

In a product theory, fusing zero-form defects follows $G$, and one-form surfaces can be added independently.

In a two-group, the fusion of zero-form defects can leave behind a one-form symmetry surface. Schematically,

$$
D_{g_1}D_{g_2}
=
D_{g_1g_2}\,\times\, U_{\beta(g_1,g_2,\ldots)}.
$$

This formula is schematic because the precise expression depends on dimension, triangulation, and whether the symmetry is written in continuum or lattice/cocycle language. The meaning is robust: the zero-form and one-form parts do not factor.

This is the higher analogue of a group extension. An ordinary group extension can make multiplication of lifted elements differ by a central element. A two-group extension can make multiplication or associativity of zero-form symmetry defects differ by a one-form symmetry defect.

:::note[Analogy]
An ordinary central extension is controlled by a two-cocycle. A two-group extension of a zero-form symmetry by a one-form symmetry is controlled by one degree higher: a Postnikov class. The analogy is useful, but the objects are different because the extra symmetry lives on extended operators rather than local states.
:::

## Background fields

Background fields make higher-group symmetry precise.

For an ordinary zero-form symmetry $G$, the background is a $G$ gauge field $A_G$. For a one-form symmetry $A$, the background is a two-form gauge field $B_2$ valued in $A$.

For a product symmetry, $A_G$ and $B_2$ can be chosen independently. For a two-group, the $B_2$ field is not closed or gauge-invariant by itself. It obeys a modified constraint

$$
\delta B_2 = \beta(A_G),
$$

in cocycle notation. In continuum notation one often writes a schematic relation like

$$
dB_2 = \beta(A_G),
$$

where $\beta(A_G)$ is a three-form or discrete three-cocycle built from the $G$ background.

A gauge transformation of $A_G$ may require a compensating gauge transformation of $B_2$ so that the combined background remains valid. The correct background is not “a $G$ bundle plus an $A$ two-form field.” It is a combined higher-bundle-like object.

:::note[Source note]
Different communities write the Postnikov data in different languages: cocycles on a triangulation, classifying-space cohomology, differential cohomology, higher gauge fields, or continuum descent-like formulas. This page uses the compact notation $\delta B_2=\beta(A_G)$ as a signpost, not as a replacement for a full mathematical model.
:::

## Modified Ward identities

Ordinary independent symmetries give independent Ward identities. Higher-group symmetry modifies this independence.

Suppose a theory has a zero-form current $j_G$ and a one-form current $J_A$. In a product symmetry, turning on a background for $G$ should not by itself create one-form charge. In a two-group, background $G$ flux can source the one-form background or appear in the Ward identity for the one-form current.

Schematic continuum equations may look like

$$
d{*J_A}=\beta(F_G),
$$

or the conservation of the ordinary current may be modified in the presence of $B_2$. The exact form is theory-dependent and convention-dependent. The invariant statement is:

$$
\text{Ward identities for the different form degrees are coupled}.
$$

This coupling is not necessarily an anomaly. An anomaly is an obstruction to gauging a symmetry. A higher-group is a symmetry structure whose correct background fields and Ward identities are already mixed. A theory can have a non-anomalous higher-group symmetry, and that higher-group can itself have anomalies.

## Higher-group versus mixed anomaly

Higher-groups and mixed anomalies are related but not the same.

A **mixed anomaly** says that two symmetries cannot both be gauged in the naive independent way. The obstruction appears as a failure of background gauge invariance.

A **higher-group symmetry** says that the correct combined symmetry was never the naive independent product. The background gauge transformations are correlated from the start.

Sometimes what looks like a mixed anomaly between separate symmetries can be reinterpreted as a non-anomalous higher-group symmetry after refining the symmetry structure. Sometimes a higher-group symmetry has its own anomaly. The distinction depends on which transformations are declared to be part of the symmetry and which background fields are included.

A useful diagnostic is:

| Situation | Meaning |
|---|---|
| Independent backgrounds exist, but partition function is not invariant | Mixed anomaly |
| Backgrounds are not independent; valid backgrounds obey a combined constraint | Higher-group structure |
| Combined higher-group background exists, but partition function still fails to be invariant | Higher-group anomaly |

This table is a guide, not a theorem. The exact classification depends on the category of QFTs, spacetime structures, and allowed counterterms.

## Physical examples

### Flavor and center symmetry

Many gauge theories have both ordinary flavor symmetries and center one-form symmetries. The true global symmetry may involve a quotient by shared center elements. When coupling to flavor background fields, the obstruction to lifting a flavor bundle can force a correlated two-form background for the center symmetry.

The result is often naturally described by higher-group-like background data. A flavor background and a center one-form background are not always independent. This happens especially when matter fields transform under both gauge and flavor centers and only a quotient acts faithfully.

The physics is simple: the global form of the flavor symmetry and the one-form center symmetry know about each other because the matter representation ties them together.

### Axion-like couplings

In theories with axion fields and couplings such as

$$
\phi\, F\wedge F,
$$

a shift symmetry of $\phi$ can mix with a higher-form symmetry of the gauge field. Depending on the spectrum and compactness, the shift symmetry and the one-form symmetry may form a higher-group-like structure.

The point is not the exact formula, which depends on the model. The point is that a zero-form shift can change the effective theta angle, and this can alter the transformation of line operators or background fields.

### Abelian gauge theories with charged matter

In Abelian gauge theories, charge lattices, screening, monopoles, and topological currents can create mixed ordinary/higher-form structures. If a zero-form symmetry acts nontrivially on the charge lattice of line operators, it acts on the one-form symmetry group. If the action is accompanied by a cocycle obstruction, the result can be a two-group rather than a semidirect product.

### Sigma models and Wess–Zumino terms

Sigma models with Wess–Zumino terms often contain topological currents and ordinary global symmetries. Coupling ordinary symmetries to background fields can shift topological charge currents. Such effects are natural breeding grounds for higher-group structures, though the details depend strongly on target-space topology and quantization conditions.

## Operator viewpoint

The operator-language meaning of a two-group is that symmetry defects of different codimension do not decouple.

Let $D_g(M_{d-1})$ be a codimension-one defect implementing $g\in G$, and let $U_a(\Sigma_{d-2})$ be a codimension-two defect for $a\in A$. In a product symmetry, the $D_g$ defects fuse by group multiplication and the $U_a$ defects are independent.

In a two-group, moving and fusing $D_g$ defects can create or drag $U_a$ defects. Junctions of ordinary symmetry defects can carry one-form symmetry flux. Associating three $G$ defects in different orders can differ by an $A$ surface determined by the Postnikov class.

This operator viewpoint is often more intuitive than the background-field viewpoint:

$$
\text{Postnikov class}
\quad\leftrightarrow\quad
\text{one-form defect living at junctions of zero-form defects}.
$$

The figure below is a schematic, not a literal spacetime drawing for every dimension.

## Gauging a higher-group symmetry

To gauge a higher-group symmetry, one must sum over combined higher-group backgrounds, not over independent $G$ and $A$ backgrounds. The constraint

$$
\delta B_2=\beta(A_G)
$$

must be part of the sum.

This can change the result compared with gauging $G$ and $A^{(1)}$ separately. Some defects that would have been genuine in a product gauging become attached to higher surfaces. Some background sectors are allowed only when their Postnikov obstruction is matched. Some dual symmetries after gauging are ordinary, some are higher-form, and some are again higher-group.

This is one reason higher-group symmetry is not optional bookkeeping: gauging depends on it.

## Relation to symmetry TFT

Symmetry TFT packages symmetry data in one higher dimension. From that perspective, a higher-group is a topological theory whose boundary symmetry defects include objects of multiple dimensions with nontrivial junctions.

The Postnikov class appears as a bulk topological term or constraint. Boundary conditions of the symmetry TFT correspond to choices of gauging, quotienting, or keeping certain symmetries global. This viewpoint becomes especially efficient for non-invertible and categorical symmetries, where ordinary group language is too small.

This page only prepares the vocabulary. The Symmetry TFT and Anomaly Inflow chapter develops the bulk-boundary formalism.

## Common pitfalls

**“A higher-group is just a product of groups.”** No. A product means independent symmetry factors. A higher-group has mixed background data or defect junctions.

**“A higher-group is the same as a mixed anomaly.”** Not quite. A mixed anomaly is an obstruction to independent gauging. A higher-group is a refined symmetry structure. A higher-group can be anomaly-free or anomalous.

**“The Postnikov class is an optional decoration.”** It is part of the symmetry data. Changing it changes allowed backgrounds, defect junctions, and gauging.

**“Only exotic theories have higher-groups.”** No. Gauge theories with quotient global symmetries, center one-form symmetries, axion couplings, and topological terms can naturally produce higher-group structures.

**“The formulas are always differential forms.”** For finite symmetries, cocycles and cohomology classes are often the correct language. Differential forms are a useful continuum shadow, not always the full global data.

**“If the zero-form current is conserved and the one-form current is conserved, the symmetry is a product.”** Conservation laws do not by themselves determine global background compatibility. Higher-group data can appear in how backgrounds, defects, and junctions are glued.

## Relations to other pages

[Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) gives key one-form examples. [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) explains the center one-form symmetry that often participates in higher-group structures. [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) gives the $B_2$ background language needed here.

The ’t Hooft Anomalies chapter distinguishes anomalies from refined symmetry structures. The Non-Invertible and Categorical Symmetries chapter generalizes the defect viewpoint. The Symmetry TFT and Anomaly Inflow chapter gives the one-higher-dimensional packaging.

## Research status

Higher-group symmetry is an established modern framework, especially for two-groups mixing ordinary and one-form symmetries. It is now widely used in discussions of gauge theories, flavor-center quotients, anomalies, topological terms, and generalized symmetry.

The active frontier includes fermionic higher-groups, continuous higher-group symmetries with differential refinements, non-invertible analogues, symmetry-TFT descriptions, higher-group anomalies, and applications to strongly coupled non-Lagrangian QFTs. Conventions are less standardized than for ordinary symmetries, so pages using higher-group data should always state their background-field model.

## Exercises

### Exercise 1: Product or higher-group?

A theory has a zero-form symmetry $G$ and a one-form symmetry $A$. In background fields, $A_G$ and $B_2$ can be chosen independently and have independent gauge transformations. Is this a product symmetry or a higher-group?

<details><summary><strong>Solution</strong></summary>

This is a product symmetry, at least at the level of the background data described. A higher-group structure would require a compatibility condition or transformation law tying $B_2$ to the $G$ background, such as $\delta B_2=\beta(A_G)$.

</details>

### Exercise 2: Reading the Postnikov constraint

Suppose a two-group background obeys

$$
\delta B_2=\beta(A_G).
$$

What does this say in words?

<details><summary><strong>Solution</strong></summary>

It says that the two-form background for the one-form symmetry is not an independent closed cocycle. Its failure to be closed, or its gauge-transformation behavior, is fixed by a three-cocycle built from the zero-form background. In physical terms, turning on a $G$ background forces correlated one-form background data.

</details>

### Exercise 3: Higher-group versus anomaly

Explain the difference between the following statements:

1. $G$ and $A^{(1)}$ have a mixed anomaly.
2. $G$ and $A^{(1)}$ form a two-group.

<details><summary><strong>Solution</strong></summary>

A mixed anomaly says that independent $G$ and $A^{(1)}$ backgrounds can be introduced, but the partition function fails to be invariant under their background gauge transformations in a way that cannot be removed by local counterterms.

A two-group says that the correct symmetry backgrounds are not independent in the first place. The $A^{(1)}$ background must transform or fail to close according to Postnikov data built from the $G$ background. A two-group can still have an anomaly, but the two concepts are distinct.

</details>

### Exercise 4: Defect-junction interpretation

In a two-group, what operator phenomenon corresponds to the Postnikov class?

<details><summary><strong>Solution</strong></summary>

The Postnikov class can be seen as a rule saying that junctions or fusions of zero-form symmetry defects carry one-form symmetry defect data. Equivalently, fusing or reassociating codimension-one $G$ defects can leave behind codimension-two $A$ defects. The one-form part is therefore built into the defect algebra rather than being an independent product factor.

</details>

## References

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- C. Córdova, T. T. Dumitrescu, and K. Intriligator, “Exploring 2-Group Global Symmetries.”
- F. Benini, C. Córdova, and P.-S. Hsin, “On 2-Group Global Symmetries and Their Anomalies.”
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.”
- N. Seiberg, “Field Theories With a Vector Global Symmetry.”
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”

## Version history

- **2026-06-20:** Initial polished draft. Added definition of two-group symmetry, background-field formulation, Postnikov class, operator-defect interpretation, anomaly distinction, gauging preview, and exercises.
