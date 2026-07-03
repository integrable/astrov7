---
title: "Symmetry TFT Idea"
description: "Explains the basic symmetry-TFT idea: a QFT’s symmetry data can be encoded by a one-higher-dimensional topological field theory."
sidebar:
  label: "Symmetry TFT Idea"
  order: 1
level: Advanced
status: "Polished draft"
source: "Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Freed–Hopkins; modern SymTFT lecture notes and reviews."
topics:
  - symmetry TFT
  - anomaly inflow
  - generalized symmetry
  - background fields
  - gauging
  - topological defects
canonicalTopics:
  - symmetry-tft
  - anomaly-inflow
  - bulk-boundary-viewpoint
  - generalized-symmetry
researchStatus:
  established:
    - "For ordinary invertible symmetries and many higher-form examples, one-higher-dimensional topological theories give a precise and extremely useful language for background fields, gauging, and anomaly inflow."
  active:
    - "For non-invertible, categorical, fermionic, and spacetime symmetries, the SymTFT language is powerful but still developing, and conventions vary across communities."
---

## Summary

A **symmetry TFT** is a one-higher-dimensional topological field theory that packages the symmetry data of a $d$-dimensional QFT. If the physical QFT is denoted $\mathcal T_d$, the symmetry TFT is often denoted

$$
\mathfrak S_{d+1}.
$$

The idea is not that the QFT secretly has an ordinary extra dimension full of local dynamics. The idea is that symmetry data can be represented topologically in one higher dimension. Symmetry operators, charged objects, background fields, gauging operations, global-form choices, and anomalies become boundary conditions, topological defects, and linking data in $\mathfrak S_{d+1}$.

The most compact picture is a slab:

$$
\mathcal B_{\mathrm{top}}
\quad\big|\quad
\mathfrak S_{d+1}
\quad\big|\quad
\mathcal B_{\mathrm{phys}}=\mathcal T_d .
$$

The physical boundary carries the QFT of interest. The topological boundary encodes a choice of how to turn relative symmetry data into an absolute $d$-dimensional theory. Changing the topological boundary can implement gauging, orbifolding, changing the global form of a gauge group, or passing to a dual presentation.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A slab diagram showing a topological boundary, the symmetry TFT bulk, the physical QFT boundary, bulk defects, and arrows labelled symmetry data, gauging choices, and anomaly inflow.](/figures/symmetry-anomalies-topology/symmetry-tft-idea-slab.svg)

<figcaption>

The SymTFT idea: local dynamics lives on the physical boundary $\mathcal T_d$, while symmetry data lives in the topological bulk $\mathfrak S_{d+1}$. Bulk defects encode symmetry operators and charges; topological boundary choices encode gaugings and global-form choices; anomaly inflow is the statement that the boundary variation is cancelled by the bulk.

</figcaption>
</figure>

The SymTFT viewpoint is useful because it makes many statements geometric: gauging becomes changing a boundary condition, anomalies become bulk topological actions, and non-invertible symmetry becomes ordinary topological defect fusion in one higher dimension.

## Prerequisites

You should know what a global symmetry is, how background fields probe symmetries, and why a ’t Hooft anomaly is an obstruction to gauging. You should also be comfortable with topological defects, higher-form symmetries, and the basic idea of a topological field theory.

The pages on [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/), [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), and [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) are the most important immediate prerequisites.

This page is a conceptual bridge. It deliberately avoids the theorem-level definition of extended TQFT, which belongs in the Topological Quantum Field Theory and Mathematical QFT volumes.

## Core idea

The old way to describe a symmetry is internal to the QFT:

$$
\text{symmetry} \quad \leadsto \quad
\text{operators acting on states and observables}.
$$

The SymTFT way externalizes the symmetry data:

$$
\text{symmetry of }\mathcal T_d
\quad \leadsto \quad
\text{topological bulk data in }\mathfrak S_{d+1}.
$$

This does not remove the symmetry from $\mathcal T_d$. It gives a more invariant bookkeeping system. In ordinary QFT language, we ask:

$$
\text{What are the symmetry operators?}
$$

In SymTFT language, we ask:

$$
\text{What bulk topological defects can end on, link with, or be brought to the physical boundary?}
$$

The answer includes more than a group. It includes fusion rules, background fields, allowed endpoints, anomaly phases, boundary conditions, and gauging interfaces.

A symmetry TFT is therefore not just a fancy way to say “anomaly inflow.” Anomaly inflow is one central use. But the SymTFT also remembers non-anomalous symmetry data: which operators are charged, which backgrounds are allowed, what happens after gauging, and which topological defects survive as dual symmetry operators.

## Setup and conventions

We write the physical QFT as $\mathcal T_d$ and the one-higher-dimensional topological theory as $\mathfrak S_{d+1}$. The physical QFT is regarded as a boundary condition

$$
\mathcal B_{\mathrm{phys}}
$$

for $\mathfrak S_{d+1}$.

An **absolute theory** is a complete $d$-dimensional QFT whose partition function is a number on a closed spacetime, once all needed structures are chosen. A **relative theory** is naturally valued in the state space of a higher-dimensional theory; it needs a bulk or a topological boundary condition to become an ordinary number.

In the slab construction, one places $\mathfrak S_{d+1}$ on an interval times spacetime:

$$
I\times M_d.
$$

One end has the physical boundary $\mathcal B_{\mathrm{phys}}$. The other end has a topological boundary $\mathcal B_{\mathrm{top}}$. The resulting $d$-dimensional theory is schematically

$$
Z_{\mathcal T}^{\mathcal B_{\mathrm{top}}}(M_d)
=
Z_{\mathfrak S}\bigl(I\times M_d;\mathcal B_{\mathrm{top}},\mathcal B_{\mathrm{phys}}\bigr).
$$

This is a schematic formula, not a universal construction recipe. It says that the physical partition function can be obtained from the topological bulk by choosing boundary conditions.

:::note[Source note]
Kapustin and Seiberg’s “couple a QFT to a TQFT” viewpoint is the clean precursor of much of the modern SymTFT language. The modern terminology emphasizes that the added TQFT packages symmetry data: global form, line/surface operators, background fields, duality interfaces, and anomaly inflow.
:::

## Why one higher dimension?

Anomalies already teach the lesson. A $d$-dimensional theory with a ’t Hooft anomaly cannot have a fully gauge-invariant partition function as a standalone function of background fields. But it can be the boundary of a $(d+1)$-dimensional invertible topological theory whose variation cancels the boundary variation.

For a background field $A$, a typical anomalous transformation has the schematic form

$$
Z_{\mathcal T}[A^g]
=
Z_{\mathcal T}[A]\exp\bigl(i\alpha[A,g]\bigr).
$$

If there is a bulk topological action $S_{\mathrm{bulk}}[A]$ such that

$$
\exp\bigl(iS_{\mathrm{bulk}}[A^g]\bigr)
=
\exp\bigl(iS_{\mathrm{bulk}}[A]\bigr)
\exp\bigl(-i\alpha[A,g]\bigr),
$$

then the combined bulk-boundary system is gauge invariant.

The SymTFT idea generalizes this. Instead of keeping only the invertible anomaly action, keep the whole topological theory that knows the symmetry operators, charged defects, and possible boundary conditions.

The phrase “one higher dimension” is therefore not decorative. It is the dimension in which symmetry defects can move, link, end, and fuse in a way that encodes the Ward identities and anomaly data of the boundary theory.

## Symmetry operators as bulk defects

In the ordinary topological-operator viewpoint, a zero-form symmetry element $g$ is represented by a codimension-one topological operator $U_g(\Sigma_{d-1})$ inside the $d$-dimensional QFT. Moving this operator through charged local operators implements the symmetry action.

In the SymTFT viewpoint, the same operator is represented by a bulk topological defect in $\mathfrak S_{d+1}$ that can be moved to the physical boundary. Its boundary shadow is the symmetry operator in $\mathcal T_d$.

For a $q$-form symmetry, the boundary charged operators are $q$-dimensional. The corresponding symmetry operators have codimension $q+1$ in the boundary. In the bulk, they are naturally part of a larger defect system whose linking data records the charge pairing.

This is why SymTFTs are especially useful for generalized symmetries. The familiar boundary equation

$$
U_g(\Sigma)\,\mathcal O_q(C)
=
\chi_g(\mathcal O_q)^{\operatorname{Link}(\Sigma,C)}
\mathcal O_q(C)
$$

becomes a statement about linking of bulk topological defects.

## Backgrounds and gaugings as boundary choices

A global symmetry can be probed by background fields. It can be gauged only if the partition function can be consistently summed over those backgrounds.

In the SymTFT picture, background choices and gauging choices become choices of boundary condition or topological interface. This is one of the cleanest parts of the viewpoint.

For a finite group symmetry, a background is a $G$ bundle. Gauging means summing over such bundles. In the associated topological bulk, there are natural boundary conditions corresponding roughly to fixing a background versus summing over it. Changing between them is a topological operation.

For a higher-form symmetry, the background is a higher-form gauge field, such as a $(q+1)$-form background for a $q$-form symmetry. Gauging means summing over the appropriate higher-form backgrounds, subject to quantization and global constraints. Again, the topological bulk is the place where those choices become geometric.

This explains a useful slogan:

$$
\text{gauging}
\quad \leadsto \quad
\text{changing the topological boundary}.
$$

It also explains why gauging often produces a dual symmetry. After summing over an $A$-valued symmetry background, the gauged theory often has a dual $\widehat A$-valued symmetry. In the SymTFT, both pieces are visible as different aspects of the same bulk defect system.

## A first example: finite-group symmetry

For a finite ordinary group $G$, a standard symmetry TFT is a finite-gauge-theory-like topological theory in one higher dimension. If the symmetry has an anomaly, the bulk is a Dijkgraaf–Witten theory or a related twisted topological theory.

In a simple untwisted situation, boundary data can encode:

- symmetry defects labelled by group elements;
- twisted sectors or background $G$ bundles;
- gauging as a sum over $G$ backgrounds;
- the dual or quantum symmetry after gauging;
- possible defects implementing orbifold or gauging interfaces.

This finite-group example is a good mental model because no continuous gauge-field analysis is needed. It also makes the relation to orbifolds transparent: orbifolding is gauging a finite symmetry, and in the SymTFT language it is a boundary operation.

However, finite groups already show the main warning. The symmetry group alone is not the full story. Twists, anomalies, boundary conditions, and defect junctions matter. The SymTFT remembers that extra structure.

## A second example: higher-form Abelian symmetry

For an Abelian $q$-form symmetry in $d$ dimensions, the symmetry can be probed by a $(q+1)$-form background field $B_{q+1}$. The topological bulk often has a BF-like description with fields whose boundary values encode background fields and dual background fields.

Schematic bulk actions of the form

$$
S_{\mathrm{BF}}
\sim
2\pi i\int_{M_{d+1}} B\wedge dC
$$

capture the canonical pairing between a symmetry and its dual. The exact degrees and quantization depend on dimension, the finite or continuous nature of the symmetry, and the global form of the fields.

The important idea is not the schematic action itself. It is that the bulk contains the electric and magnetic background data in one package. Boundary choices decide which data are fixed, summed over, or interpreted as defects in the boundary theory.

This is why BF theories and Dijkgraaf–Witten theories appear so frequently in examples of SymTFT.

## SymTFT versus anomaly theory

An anomaly theory is often invertible: it assigns phases and has no nontrivial local excitations. For many ordinary ’t Hooft anomalies, the anomaly is captured by an invertible field theory in one higher dimension.

A SymTFT may be non-invertible. It can have nontrivial topological line, surface, or higher defects. It can encode symmetry operators themselves, not just their anomalous phases.

So the relation is:

$$
\text{anomaly theory}
\subset
\text{SymTFT data}.
$$

The inclusion is conceptual, not literally a subtheory in every formulation. The anomaly theory records the obstruction. The full SymTFT records the symmetry category, charged objects, background fields, gaugings, and anomaly data together.

This distinction matters especially for non-invertible symmetries. Their anomalies are not always well described by a single invertible response action. Instead, one studies linking invariants, boundary conditions, module categories, and defect networks in the SymTFT.

## What the SymTFT does not contain

The SymTFT does not usually contain the full local dynamics of $\mathcal T_d$. It does not know all scaling dimensions, masses, S-matrix elements, beta functions, or OPE coefficients.

It knows the topological symmetry skeleton. For example, it may know that certain lines are charged under a one-form symmetry, that a background field has a mixed anomaly, or that gauging one symmetry produces another. It does not compute the detailed expectation value of every Wilson loop in a confining gauge theory.

A good analogy is:

$$
\text{SymTFT} : \text{QFT}
\quad \sim \quad
\text{symmetry group} : \text{Hamiltonian}.
$$

A symmetry group constrains a Hamiltonian without determining it. A SymTFT constrains and organizes a QFT without replacing its dynamics.

## Common pitfalls

**“The SymTFT is the physical QFT.”** Usually not. The SymTFT is topological and one dimension higher. The physical QFT is a boundary condition or boundary sector.

**“The bulk is an ordinary extra dimension.”** Usually not. The bulk is an auxiliary topological bookkeeping device. It need not be a physical spacetime dimension.

**“SymTFT means only anomaly inflow.”** Anomaly inflow is central, but the SymTFT also packages non-anomalous symmetry operators, charges, dual symmetries, background choices, and gaugings.

**“Every SymTFT is invertible.”** No. Invertible theories capture many anomaly phases. Full SymTFTs for non-invertible or categorical symmetries are often non-invertible topological theories.

**“Changing the topological boundary is a small deformation.”** It can change the absolute $d$-dimensional theory, for example by gauging a symmetry or changing the global form. It is topological in the bulk, not dynamically small in the boundary interpretation.

**“The SymTFT determines the RG flow.”** It constrains RG flow through anomaly matching and symmetry preservation, but it does not determine the full dynamics.

## Relations to other pages

[Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) explains the sources that the SymTFT packages.

[Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) gives the boundary operation that becomes a topological boundary change here.

[Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/) explains why non-invertible symmetry data are naturally described by defect categories. The SymTFT is one way those categories arise from bulk topological defects.

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) develops the cancellation mechanism in detail. [Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) develops the boundary-choice viewpoint.

## Research status

The one-higher-dimensional anomaly-inflow viewpoint is established. The idea that coupling a QFT to a TQFT changes global operator data without changing local dynamics in flat space is also a standard tool.

The modern term “SymTFT” is part of a rapidly developing language. It is widely used for higher-form, non-invertible, categorical, and string-theoretic symmetry data. The precise mathematical package varies by context: finite TQFT, extended TQFT, fusion categories, higher categories, relative field theory, or brane-engineered topological sectors. The pedagogical rule is to treat the SymTFT as a powerful organizing principle and state assumptions in every example.

## Exercises

### Exercise 1: What does the bulk know?

List three kinds of information a SymTFT can encode and two kinds of information it usually does not encode.

<details><summary><strong>Solution</strong></summary>

A SymTFT can encode symmetry operators, charged objects, background fields, gauging operations, global-form choices, and anomaly data. It usually does not encode detailed local dynamics such as the exact mass spectrum of a generic non-topological QFT, scattering amplitudes, beta functions, or generic OPE coefficients.

</details>

### Exercise 2: Gauging as a boundary operation

Explain in words why gauging a finite symmetry can be interpreted as changing a topological boundary condition in the SymTFT picture.

<details><summary><strong>Solution</strong></summary>

A finite symmetry background is a choice of finite-group bundle. Gauging means summing over such backgrounds. In the SymTFT, one boundary condition can correspond to fixing the background data, while another can correspond to allowing or summing over it. Changing from one to the other implements the gauging operation as a topological boundary change.

</details>

### Exercise 3: Invertible anomaly theory versus SymTFT

Why is an invertible anomaly theory not always the same as the full SymTFT?

<details><summary><strong>Solution</strong></summary>

An invertible anomaly theory records an anomalous phase, usually as a one-higher-dimensional response theory. The full SymTFT may also contain nontrivial topological defects, charged objects, dual symmetries, boundary conditions, and gauging interfaces. Thus the anomaly theory captures an obstruction, while the SymTFT can package the entire topological symmetry data.

</details>

### Exercise 4: Relative partition function

Suppose a boundary QFT has an anomaly. Why might its partition function be better regarded as a vector rather than a number?

<details><summary><strong>Solution</strong></summary>

If a theory is anomalous, its partition function may transform by a phase under background gauge transformations rather than being a gauge-invariant number. In the inflow picture, it is naturally an element of the state space of the bulk anomaly theory on the boundary manifold. Pairing it with a choice of bulk state or topological boundary condition gives a gauge-invariant number.

</details>

## References

- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality.” Foundational for the idea that coupling to a topological theory changes global operator data and duality structure.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Standard source for higher-form symmetries, background fields, gauging, and anomalies.
- Daniel S. Freed and Michael J. Hopkins, “Reflection Positivity and Invertible Topological Phases.” Standard reference for invertible phases and anomaly theories.
- Justin Kaidi, Emily Nardoni, Gabi Zafrir, and Yunqin Zheng, “Symmetry TFTs and Anomalies of Non-Invertible Symmetries.” Useful for non-invertible anomaly diagnostics through SymTFT linking data.
- Sakura Schäfer-Nameki, lecture notes and reviews on generalized symmetries, non-invertible symmetries, and SymTFT.

## Version history

- **2026-06-20:** Initial polished draft. Introduced the slab picture, physical and topological boundaries, bulk defects, background fields, gauging as boundary change, anomaly theories versus full SymTFTs, and relative QFT previews.
