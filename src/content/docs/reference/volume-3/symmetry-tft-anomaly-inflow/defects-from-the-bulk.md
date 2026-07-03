---
title: "Defects from the Bulk"
description: "Explains how topological defects in the SymTFT bulk encode boundary symmetry operators, charged defects, junctions, gauging choices, and anomaly inflow."
sidebar:
  label: "Defects from the Bulk"
  order: 7
level: Advanced
status: "Polished draft"
source: "Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Freed; Kaidi–Ohmori–Zheng; Copetti; modern SymTFT and defect references."
topics:
  - symmetry TFT
  - topological defects
  - defect charges
  - bulk-boundary dictionary
  - generalized symmetry
  - anomaly inflow
canonicalTopics:
  - symtft-bulk-defect
  - bulk-boundary-defect-dictionary
  - defect-charge
  - topological-operator
  - defect-inflow
researchStatus:
  established:
    - "For ordinary, finite, and many higher-form symmetries, the SymTFT bulk gives a precise topological description of symmetry operators, charged operators, gauging choices, and anomalies."
    - "Topological defects in the bulk can end on boundaries, fuse with each other, link boundary insertions, and thereby encode boundary symmetry actions."
  active:
    - "For non-invertible, higher-codimensional, gapless, fermionic, and spacetime-sensitive defects, the full bulk-boundary dictionary is active research and not yet universally standardized."
---

## Summary

The SymTFT is useful because it turns symmetry data into topological geometry in one higher dimension. The slogan of this page is:

$$
\text{boundary symmetry data}
\quad
=
\quad
\text{bulk topological defects plus their boundary behavior}.
$$

A topological operator of the $d$-dimensional QFT can often be viewed as the endpoint, shadow, or boundary image of a topological defect in the $(d+1)$-dimensional SymTFT. A charged operator is detected by linking with such a defect. A gauging choice is encoded by which bulk defects are allowed to end on the chosen topological boundary. A defect anomaly appears when the would-be bulk moves fail to be consistently absorbed at the boundary.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A SymTFT slab showing bulk topological defects linking a boundary operator, ending on a topological boundary, and projecting to boundary symmetry defects.](/figures/symmetry-anomalies-topology/symtft-defects-from-bulk.svg)

<figcaption>

Bulk defects in the SymTFT have several boundary shadows. They can link a boundary operator to measure its charge, end on a topological boundary if that boundary condenses them, project to symmetry defects on the physical boundary, or meet at bulk junctions whose images are boundary fusion and selection rules.

</figcaption>
</figure>

The word “bulk” here does not mean ordinary spacetime in which the original QFT lives. It means the auxiliary topological dimension of the SymTFT. That extra dimension separates universal symmetry data from the dynamical details of the physical boundary theory.

## Prerequisites

Read [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/), [Bulk-Boundary Viewpoint](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/bulk-boundary-viewpoint/), [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/), and [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/).

From earlier chapters, the most useful pages are [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), [Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/), [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), and [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/).

## Core idea

Put the SymTFT $\mathcal Z_{\mathrm{sym}}$ on a slab,

$$
X_{d+1}=M_d\times I.
$$

One end of the interval carries a physical boundary condition $\mathcal B_{\mathrm{phys}}$, which contains the actual QFT. The other end carries a topological boundary condition $\mathcal B_{\mathrm{top}}$, which chooses an absolute theory, a gauging, a global form, or a background-sector convention.

Now insert a bulk topological defect $\mathfrak D$ in $\mathcal Z_{\mathrm{sym}}$. Because the bulk theory is topological, $\mathfrak D$ can be moved freely unless it crosses another defect, ends on a boundary, or passes through a junction. Its possible moves encode the symmetry.

There are four basic operations.

| Bulk operation | Boundary meaning |
|---|---|
| Move a bulk defect parallel to the physical boundary | Deform a symmetry operator without changing correlators. |
| Link a boundary insertion with a bulk defect | Measure or act on the charge of that insertion. |
| End a bulk defect on a topological boundary | Condense or gauge the corresponding topological data. |
| Fuse or join bulk defects | Produce boundary fusion rules, selection rules, and defect-network identities. |

This is the geometric content behind a lot of modern symmetry language. Instead of saying only “a symmetry acts on an operator,” we say which topological defects can link it, end on it, or be absorbed by nearby boundary conditions.

## The basic slab dictionary

The following dictionary is schematic, but it is the right first map.

| SymTFT bulk object | Boundary interpretation |
|---|---|
| Bulk codimension-one wall | Ordinary or categorical symmetry defect on the physical boundary. |
| Bulk higher-codimension defect | Higher-form symmetry operator, charge detector, or topological excitation. |
| Bulk line or surface ending on $\mathcal B_{\mathrm{phys}}$ | Charged local or extended operator on the physical QFT. |
| Bulk defect ending on $\mathcal B_{\mathrm{top}}$ | Condensed/gauged defect; data made invisible at that topological boundary. |
| Bulk defect crossing a boundary operator | Symmetry action or charge measurement. |
| Bulk junction | Boundary defect junction, fusion vertex, or selection-rule tensor. |
| Bulk braiding or linking | Boundary charge pairing, anomaly phase, or nontrivial commutation relation. |

The topological boundary $\mathcal B_{\mathrm{top}}$ is not decorative. It says which bulk defects may be trivialized at the boundary. That is exactly what gauging and quotienting do: they change which operators are genuine, which charged objects survive, and which dual symmetries appear.

## Ordinary symmetry defects from the bulk

For an ordinary finite group $G$, a symmetry defect in $d$ dimensions is a codimension-one wall labeled by $g\in G$. Crossing the wall transforms local operators:

$$
\mathcal O(x)\mapsto g\cdot\mathcal O(x).
$$

In the SymTFT, this wall is naturally represented as a bulk topological defect whose endpoint or shadow on the physical boundary is the $G$ symmetry wall. Fusion of bulk defects gives

$$
U_g\,U_h=U_{gh}.
$$

If a local boundary operator $\mathcal O_R$ transforms in representation $R$, the bulk defect linked around it returns the representation matrix $R(g)$.

For an anomalous finite symmetry, the same walls may exist but their junctions pick up nontrivial phases, or they may require a bulk topological action for consistent deformation. That is anomaly inflow in defect language.

:::note[Source note: finite symmetry]
For ordinary finite symmetries, the SymTFT often reduces to a Dijkgraaf–Witten-type topological gauge theory. The anomaly is encoded by the bulk topological action, while the boundary symmetry defects are the shadows of bulk topological data.
:::

## Higher-form symmetry defects from the bulk

For a $q$-form symmetry in a $d$-dimensional QFT, charged operators have dimension $q$. The symmetry operators live on closed codimension-$q+1$ manifolds. In the SymTFT, these symmetry operators can be described as boundary images of bulk topological defects that link the charged operator.

For example, a one-form symmetry in four dimensions acts on line operators. A closed two-dimensional symmetry surface surrounds or links a Wilson line, giving a phase or representation label:

$$
U_\alpha(\Sigma_2)\,W(C)
=
\chi_\alpha(W)^{\operatorname{Link}(\Sigma_2,C)}\,W(C).
$$

The bulk picture makes this linking relation literal. The surface can be pushed into the bulk, moved topologically, and then brought back to the boundary. If it links the boundary line, the correlator changes by the charge pairing.

The same viewpoint explains why gauging a higher-form symmetry changes the line spectrum. If a bulk surface can end on the chosen topological boundary, the corresponding one-form charge is condensed there. Boundary line operators that braid nontrivially with it are no longer genuine without dressing.

## Defect charges and tubular neighborhoods

A powerful way to study a defect $\mathscr D$ is to excise a small tubular neighborhood around it. If $\mathscr D$ has codimension $p$, the boundary of that neighborhood looks locally like

$$
\widehat\Sigma=\Sigma_{\mathscr D}\times S^{p-1}.
$$

The sphere $S^{p-1}$ links the defect. Symmetry data acting on $\mathscr D$ is therefore data living on this linking sphere and along the defect worldvolume.

In the SymTFT, one can reduce the bulk symmetry theory on $S^{p-1}$. The charge or multiplet structure of $\mathscr D$ is then described by a boundary condition or module-like object for the reduced topological theory:

$$
\mathcal Z_{\mathrm{sym}}[S^{p-1}].
$$

This is one of the cleanest modern uses of the SymTFT: it treats charges of boundaries, interfaces, line defects, surface defects, and higher-codimension operators in a unified way.

:::note[Source note: defect charges]
Recent SymTFT work describes charges of codimension-$p$ defects by reducing the SymTFT on the linking sphere $S^{p-1}$ and studying appropriate gapped boundary conditions for the reduced topological theory. This is a sharper version of the older slogan that “charges are measured by linking.”
:::

## Bulk junctions and boundary fusion

A symmetry is not only a list of defects. It includes how defects join and fuse. In the bulk, this information is carried by junctions.

Suppose two topological defects $\mathfrak D_a$ and $\mathfrak D_b$ can be brought together. In a simple semisimple setting, their fusion may be

$$
\mathfrak D_a\otimes\mathfrak D_b
\simeq
\bigoplus_c N_{ab}{}^c\,\mathfrak D_c.
$$

The same junction data controls the boundary fusion of the corresponding symmetry defects. If the defects are invertible, the coefficients describe group multiplication. If not, fusion can produce a sum of sectors. This is the bridge from SymTFT to non-invertible symmetry.

The bulk also remembers associativity data. Three defects can be fused in two orders:

$$
(\mathfrak D_a\otimes\mathfrak D_b)\otimes\mathfrak D_c,
\qquad
\mathfrak D_a\otimes(\mathfrak D_b\otimes\mathfrak D_c).
$$

The equivalence between these two descriptions is part of the categorical symmetry data. Boundary pages that mention “associators” are referring to this bulk junction coherence.

## Endpoints and genuine operators

A boundary operator is **genuine** if it can exist without being attached to extra topological data extending away from it. The SymTFT gives a precise way to decide this.

A bulk defect ending on $\mathcal B_{\mathrm{phys}}$ creates a charged boundary operator. If the endpoint is topologically well-defined by itself, the boundary operator is genuine. If it requires an attached surface, line, or branch sheet, then the operator is not genuine as a standalone object.

This distinction is central in gauge theory. Wilson lines, ’t Hooft lines, and dyonic lines can become genuine or non-genuine depending on global form, matter content, and which one-form symmetries are gauged. In the SymTFT, those choices are boundary conditions.

The practical rule is:

$$
\text{genuine boundary operator}
\quad
\Longleftrightarrow
\quad
\text{consistent endpoint of bulk topological data}.
$$

This rule is especially useful when Lagrangian language is misleading or unavailable.

## Condensation at the topological boundary

A topological boundary condition can absorb certain bulk defects. In physical language, those defects are **condensed** at the boundary.

If a defect is condensed at $\mathcal B_{\mathrm{top}}$, it can end there without leaving a nontrivial boundary excitation. This changes the boundary theory obtained from the slab. Defects that braid nontrivially with the condensed set may be projected out, confined, or forced to attach to additional data.

For an abelian anyon theory, the condensed set is often a mutually transparent subgroup or a Lagrangian algebra. For a finite group gauge theory, it may correspond to fixing or summing over bundles. For non-invertible symmetries, it is described by algebra objects and module categories rather than ordinary subgroups.

The conceptual point is stable even when the mathematics changes:

$$
\text{topological boundary condition}
=
\text{choice of which bulk defects may disappear at the boundary}.
$$

## Anomaly inflow onto defects

Anomaly inflow is not limited to the physical spacetime boundary. It can also be localized on defects.

Suppose a boundary defect $\mathscr D$ tries to preserve a symmetry. In the bulk picture, this requires certain topological defects to be moved through or end on the region around $\mathscr D$. If the moves are inconsistent, the defect carries an anomaly. The anomaly may be cancelled by a lower-dimensional theory living on $\mathscr D$, by a bulk topological term, or by allowing the defect to transform nontrivially.

Schematic inflow looks like

$$
\delta S_{\mathrm{bulk}}
=
-\delta S_{\mathscr D}.
$$

The same idea applies to ordinary boundaries, interfaces, line defects, and higher-codimension defects. A defect can be symmetric only if the surrounding bulk defect moves admit the required topological boundary condition after reducing on the linking sphere.

This is a useful generalization of a familiar statement: anomalous symmetries cannot have completely symmetric, trivially gapped boundaries. The SymTFT version says that obstructions can be diagnosed for defects of many codimensions.

## Examples

### One-form symmetry and a Wilson line

In a four-dimensional gauge theory with a one-form center symmetry, a Wilson line $W_R(C)$ is charged by its center character. The symmetry operator is a surface $U(\Sigma_2)$. Its action is

$$
U(\Sigma_2)W_R(C)
=
\chi_R^{\operatorname{Link}(\Sigma_2,C)}W_R(C).
$$

In the SymTFT, $U(\Sigma_2)$ is the boundary image of a bulk surface. The line $W_R(C)$ is an endpoint or boundary charged object. Linking in the boundary is represented by moving the bulk surface around the endpoint.

### Non-invertible duality defect

In the Ising-like examples of the previous chapter, the duality defect $\mathcal N$ obeys

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta.
$$

A SymTFT can represent $\mathcal N$ as a bulk topological defect whose fusion is not group-like. The boundary non-invertible Ward identities are shadows of bulk topological-network moves.

### Boundary condition as a condensed phase

A topological boundary condition that condenses a set of bulk lines can be viewed as a gapped phase attached to the boundary. Lines that can end are condensed. Lines that braid nontrivially with them are not allowed to pass freely. This is the topological explanation of many “projection” effects in gauging.

## Common pitfalls

**Thinking the SymTFT bulk is an extra physical dimension.** It is an auxiliary topological theory encoding symmetry data. It may be physically realized in special systems, but the SymTFT construction does not require the original QFT to literally live on the boundary of a material bulk.

**Assuming every bulk defect has a boundary endpoint.** Endability is boundary-condition data. A defect may exist in the bulk but fail to end on a particular boundary.

**Confusing linking with local OPE.** Linking is a topological relation between supports. It is not the same as bringing local operators to coincident points.

**Treating all defects as invertible.** Bulk fusion can be non-invertible, and the boundary symmetry can be categorical rather than group-like.

**Assuming subgroup language is universal.** Subgroups work for many ordinary invertible examples. General non-invertible and higher-categorical examples require algebra objects, module categories, and boundary-condition data.

## Relations to other pages

[Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) explains how topological boundaries choose absolute theories. This page explains how bulk defects behave relative to those boundaries.

[Relative QFT Preview](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/relative-qft-preview/) explains what happens when the physical boundary by itself does not produce a number-valued partition function.

[Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) and [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/) develop the boundary and categorical versions of bulk junction data.

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) explains the linking action of topological operators on charged extended operators.

## Research status

The defect-from-bulk viewpoint is well-established in ordinary finite symmetry, Dijkgraaf–Witten theory, many higher-form symmetry examples, rational CFT, and topological phases. It is a standard organizing principle in modern SymTFT.

It remains active research in higher-dimensional non-invertible symmetry, defect charge classification, gapless defects, intrinsically relative theories, fermionic and spin-sensitive defects, subsystem symmetry, and gravitational settings. In these cases, the physical picture is often clearer than the fully general mathematical formalism.

## Exercises

### Exercise 1: Linking as charge measurement

In a four-dimensional theory, let $U(\Sigma_2)$ be a surface operator for a $\mathbb Z_N$ one-form symmetry, and let $W_q(C)$ be a line operator of charge $q\in\mathbb Z_N$. Assume

$$
U(\Sigma_2)W_q(C)
=
\exp\!\left(\frac{2\pi iq}{N}\operatorname{Link}(\Sigma_2,C)\right)W_q(C).
$$

What happens if $\Sigma_2$ is deformed without crossing $C$? What happens if the deformation changes the linking number by one?

<details><summary><strong>Solution</strong></summary>

If $\Sigma_2$ is deformed without crossing $C$, the linking number is unchanged and the correlator is unchanged. That is the topological Ward identity.

If the deformation changes the linking number by one, the correlator is multiplied by

$$
\exp\!\left(\frac{2\pi iq}{N}\right).
$$

This is the one-form charge of the line operator.

</details>

### Exercise 2: Endability and gauging

Explain why gauging a one-form symmetry can make a previously genuine line operator non-genuine.

<details><summary><strong>Solution</strong></summary>

Gauging a one-form symmetry sums over its background fields. A line charged under that symmetry is not invariant under the gauged topological data. In the SymTFT picture, the corresponding bulk symmetry surface is condensed at the gauging boundary. A boundary line that braids nontrivially with the condensed surface cannot end as an isolated genuine operator; it must be attached to additional topological data or projected out. Thus gauging changes the genuine line spectrum.

</details>

### Exercise 3: Defect charge from a linking sphere

A defect has codimension $p$. Why is the sphere $S^{p-1}$ around the defect the right place to look for its generalized charge?

<details><summary><strong>Solution</strong></summary>

The boundary of a small tubular neighborhood around a codimension-$p$ defect is locally

$$
\Sigma_{\mathscr D}\times S^{p-1}.
$$

The sphere $S^{p-1}$ links the defect. Topological symmetry operators detect charge by linking, so the possible symmetry actions on the defect are encoded by topological data on this linking sphere. Reducing the SymTFT on $S^{p-1}$ turns the question into one about boundary conditions or modules for the reduced topological theory.

</details>

## References

- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for QFT–TQFT coupling, global forms, and topological boundary choices.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for charged extended operators, higher-form symmetries, backgrounds, gauging, and anomalies.
- Freed, “Anomalies and Invertible Field Theories,” for anomaly theories and relative partition-function language.
- Kaidi, Ohmori, and Zheng, “Symmetry TFTs for Non-Invertible Defects,” for SymTFT constructions of non-invertible defects.
- Copetti, “Defect Charges, Gapped Boundary Conditions, and the Symmetry TFT,” for defect charges via linking spheres and reduced SymTFT boundary conditions.
- Kong, Kitaev, Fuchs, Runkel, Schweigert, and related TQFT/RCFT defect literature for topological defect networks, boundaries, and module categories.

## Version history

- **2026-06-20:** Initial polished draft. Added bulk-defect dictionary, linking charge measurement, endability, condensation, defect charges from tubular neighborhoods, anomaly inflow onto defects, examples, and exercises.
