---
title: "Bulk-Boundary Viewpoint"
description: "Explains how symmetry operators, charged objects, background fields, gaugings, and anomalies appear through the bulk-boundary relation in a symmetry TFT."
sidebar:
  label: "Bulk-Boundary Viewpoint"
  order: 2
level: Advanced
status: "Polished draft"
source: "Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett; Freed–Hopkins; modern SymTFT and anomaly-inflow literature."
topics:
  - bulk-boundary relation
  - symmetry TFT
  - boundary conditions
  - topological defects
  - anomaly inflow
  - relative QFT
canonicalTopics:
  - bulk-boundary-viewpoint
  - symmetry-tft
  - topological-boundary-condition
  - anomaly-inflow
researchStatus:
  established:
    - "The bulk-boundary viewpoint is the standard geometric language for anomaly inflow and for many TQFT-coupled descriptions of global-form and higher-form symmetry data."
  active:
    - "For non-invertible, fermionic, categorical, and spacetime symmetries, the detailed dictionary between bulk defects, boundary categories, and physical observables remains an active area of research."
---

## Summary

The **bulk-boundary viewpoint** says that a $d$-dimensional QFT with symmetry can often be understood as a boundary condition for a $(d+1)$-dimensional topological theory. The topological bulk contains defects and boundary conditions that encode the symmetry data. The physical boundary contains the local QFT dynamics.

Schematically,

$$
\mathfrak S_{d+1}\quad\text{has boundary}\quad \mathcal B_{\mathrm{phys}}=\mathcal T_d.
$$

Bulk topological defects can be moved around without changing local dynamics. When such a defect approaches or ends on the physical boundary, it becomes a boundary symmetry operator, a charged operator, a background-field insertion, an interface, or a constraint on possible boundary conditions.

The bulk-boundary dictionary is:

| Bulk object in $\mathfrak S_{d+1}$ | Boundary meaning in $\mathcal T_d$ |
|---|---|
| Bulk topological defect | Symmetry operator, charged object, or duality defect |
| Bulk linking invariant | Charge pairing or anomaly diagnostic |
| Physical boundary condition | The QFT whose symmetry is being studied |
| Topological boundary condition | Choice of gauging, global form, or absolute theory |
| Boundary-changing interface | Gauging interface, duality interface, or domain wall |
| Bulk variation | Anomaly inflow cancelling boundary variation |

<figure class="doc-figure" style="--figure-width: 54rem;">

![A bulk-boundary dictionary diagram showing bulk defects ending on a physical boundary and linking with charged boundary operators.](/figures/symmetry-anomalies-topology/bulk-boundary-defect-dictionary.svg)

<figcaption>

Bulk defects in $\mathfrak S_{d+1}$ have boundary shadows. Some end on charged boundary objects, some become symmetry operators on the boundary, some implement interfaces between boundary conditions, and some link with one another to produce anomaly phases or charge pairings.

</figcaption>
</figure>

The slogan is:

$$
\text{boundary QFT sees symmetry actions;}
\qquad
\text{bulk TFT sees their topological origin.}
$$

## Prerequisites

Read [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) first. You should also know the basic language of topological defects, defect fusion, higher-form symmetries, background fields, and ’t Hooft anomalies.

You do not need the full machinery of extended TQFT. The page uses pictures and operator logic: defects can move, link, end on boundaries, and fuse.

## Core idea

A QFT boundary condition is not just a place where fields stop. It can be a whole $d$-dimensional quantum field theory living on the boundary of a topological bulk.

In ordinary anomaly inflow, the boundary theory is anomalous by itself, but the combined bulk-boundary system is consistent. In SymTFT, the bulk can carry more than the anomaly. It can carry the full topological symmetry skeleton.

This reframes symmetry questions:

$$
\text{How does a symmetry act on }\mathcal T_d?
$$

becomes

$$
\text{Which bulk defects can be moved to, end on, or link with }\mathcal B_{\mathrm{phys}}?
$$

The second question knows about charged operators, symmetry defects, dual symmetries, possible gaugings, and anomalies all at once.

## Setup and conventions

Let $\mathfrak S_{d+1}$ be a topological theory on a $(d+1)$-manifold $X_{d+1}$ with boundary

$$
\partial X_{d+1}=M_d.
$$

A boundary condition $\mathcal B$ assigns allowed boundary data and possible boundary degrees of freedom. The physical QFT $\mathcal T_d$ is represented by a boundary condition

$$
\mathcal B_{\mathrm{phys}}.
$$

If the SymTFT is placed on a slab,

$$
X_{d+1}=M_d\times I,
$$

there may be a second boundary condition $\mathcal B_{\mathrm{top}}$ at the other end. Pairing the physical boundary with a topological boundary produces an absolute $d$-dimensional theory.

A bulk defect is denoted $\mathcal D$ and may be supported on a submanifold of $X_{d+1}$. If it is topological, its correlation functions are invariant under smooth deformations that do not cross other defects or boundaries.

The central operation is to move $\mathcal D$ until it approaches the boundary. The boundary must then decide what $\mathcal D$ becomes.

## Boundary shadows of bulk defects

A bulk defect can have several kinds of boundary shadow.

First, it may become a **symmetry operator** in the boundary QFT. An ordinary symmetry defect $U_g(\Sigma)$ can be regarded as the boundary image of a bulk topological defect that has been pushed against $\mathcal B_{\mathrm{phys}}$.

Second, it may end on a **charged boundary operator**. A bulk line ending on a boundary point can indicate a local operator charged under a zero-form symmetry. A bulk surface ending on a boundary line can indicate a line operator charged under a one-form symmetry.

Third, it may become a **boundary-changing interface**. If the bulk defect separates two boundary conditions, then its endpoint on the boundary is a domain wall or interface between two $d$-dimensional theories.

Fourth, it may be forbidden to end on a given boundary. That failure is not a bug; it is symmetry data. It can say that certain charged objects are absent, confined, projected out, or incompatible with a chosen gauging.

The boundary shadow depends on the boundary condition. The same bulk defect may have different interpretations on different boundaries.

:::note[Important]
A bulk defect is topological in the bulk. Its boundary shadow need not be a topological operator in the full boundary QFT unless the boundary dynamics permits it. The bulk controls the topological symmetry data; the boundary controls local dynamics.
:::

## Symmetry action from crossing

Suppose a bulk defect $\mathcal U$ becomes a boundary symmetry operator $U(\Sigma)$, and another bulk defect can end on a boundary charged operator $\mathcal O(C)$. The symmetry action is encoded by linking or crossing in the bulk.

The boundary Ward identity

$$
U(\Sigma)\,\mathcal O(C)
=
\chi^{\operatorname{Link}(\Sigma,C)}\mathcal O(C)
$$

is the boundary shadow of a bulk topological linking invariant.

This is the same logic as ordinary topological symmetry operators, but the bulk makes it more flexible. It can describe ordinary symmetries, higher-form symmetries, dual symmetries after gauging, and sometimes non-invertible fusion networks.

For non-invertible symmetry, the result of crossing may not be multiplication by a phase. It can be a sum over sectors, a projection, or a defect-network relation. The bulk still supplies the invariant topological move; the boundary interprets it.

## Background fields from boundary data

A background field in the boundary theory can be represented as a choice of bulk topological data that reaches the boundary. For a zero-form finite symmetry, this may be a $G$ bundle on $M_d$. For a higher-form symmetry, it may be a higher-form gauge field.

In the bulk, background fields are often encoded by topological gauge fields or defects whose boundary values are fixed. The difference between “fixing a background” and “summing over a background” is then a difference between boundary conditions.

This is why the SymTFT is so good at describing gauging. Gauging is not an algebraic afterthought. It is a change in what is allowed to fluctuate at the topological boundary.

For example, a boundary condition might fix a discrete gauge field, corresponding to an ungauged global symmetry. Another boundary condition might sum over it, corresponding to gauging the symmetry. A dual boundary defect then records the quantum symmetry of the gauged theory.

## Physical and topological boundaries

The physical boundary $\mathcal B_{\mathrm{phys}}$ carries local dynamics. It contains the QFT whose operators, states, and phases we care about.

The topological boundary $\mathcal B_{\mathrm{top}}$ is chosen to turn the relative boundary theory into an ordinary absolute theory. It is topological: its correlation functions depend only on the topology and defect data, not on local metric details.

Different choices of $\mathcal B_{\mathrm{top}}$ can produce different-looking boundary theories with the same underlying symmetry TFT. This is the topological source of many dualities and gauging relations.

For instance:

$$
\mathcal B_{\mathrm{top}}^{(1)}
\quad\longleftrightarrow\quad
\text{ungauged presentation},
$$

while

$$
\mathcal B_{\mathrm{top}}^{(2)}
\quad\longleftrightarrow\quad
\text{gauged or dual presentation}.
$$

The same physical boundary, paired with different topological boundaries, can yield different absolute theories related by gauging, orbifolding, or changing global form.

## Anomaly inflow in boundary language

An anomaly means that the boundary theory cannot be made fully invariant under background gauge transformations by itself. In the bulk-boundary viewpoint, this is allowed because the bulk transforms oppositely.

Let $A$ denote background data. The boundary variation is schematically

$$
Z_{\partial}[A^g]=Z_{\partial}[A]\exp(i\alpha[A,g]).
$$

The bulk topological theory supplies

$$
Z_{\mathrm{bulk}}[A^g]=Z_{\mathrm{bulk}}[A]\exp(-i\alpha[A,g]).
$$

The product is invariant:

$$
Z_{\mathrm{bulk}}[A]Z_{\partial}[A].
$$

This is the simplest form of anomaly inflow. The bulk-boundary viewpoint does not merely cancel a formula; it changes what the boundary partition function is. The anomalous boundary partition function is naturally a vector in the bulk state space, and a topological boundary condition supplies the dual vector needed to make a number.

:::note[Source note]
This “partition function as a vector” viewpoint is common in modern anomaly theory and relative QFT. It is especially useful for global, finite, higher-form, and non-invertible anomalies where a local current-divergence formula is not the most invariant description.
:::

## Defect endpoints and allowed operators

Not every bulk defect can end on every boundary. The allowed endpoints are part of the boundary condition.

This explains many familiar statements.

If a charged local operator exists, then the corresponding symmetry-defect line may end on the physical boundary at that operator. If a line operator is screened, then a corresponding surface or line defect can end on dynamical matter. If a line is genuine, it cannot end in the bulk of spacetime without an allowed charged endpoint.

In a gauge theory, the global form of the gauge group changes which line operators are genuine. The SymTFT packages that choice as boundary data. The line-operator lattice is not merely a list of observables; it is part of the global definition of the theory.

For higher-form symmetries, this endpoint logic is central. A one-form symmetry is exact only when charged line operators cannot end on dynamical local operators. If they can end, the would-be one-form symmetry is explicitly broken or screened.

## Interfaces and dualities

A bulk topological defect can connect two boundary conditions. When seen from the boundary, it is an interface between two $d$-dimensional theories or two presentations of the same theory.

If the interface has an inverse, it behaves like an ordinary duality wall. If it does not, it can implement a gauging operation or a non-invertible duality defect.

This is the bulk version of a lesson from the non-invertible chapter:

$$
\text{gauging interface}
\quad \text{often has no inverse}.
$$

Composing interfaces is then a form of fusion. In the bulk, this is topological fusion of defects or boundary conditions. On the boundary, it becomes a relation between operations on QFTs: gauge, orbifold, stack with an SPT phase, change global form, or dualize.

## Examples of the dictionary

For an ordinary finite group symmetry $G$, bulk defects encode symmetry twists and background bundles. A physical boundary may carry a $G$-symmetric QFT. A topological boundary can choose whether the $G$ background is fixed or summed over. The resulting boundary theory may be the original theory or its $G$ orbifold.

For an Abelian one-form symmetry, a bulk BF-type theory can encode electric and magnetic higher-form backgrounds. A boundary condition decides which line operators are genuine and which backgrounds are summed over. Changing the boundary can exchange electric and magnetic descriptions.

For a non-invertible symmetry in two dimensions, the three-dimensional SymTFT may contain topological lines whose boundary category is the non-invertible defect category. The fusion of boundary defects is then a shadow of bulk fusion and boundary endpoint data.

These examples differ technically, but their logic is the same: symmetry data is encoded by what bulk defects can do near the boundary.

## What is gained by going to the bulk?

The bulk-boundary viewpoint gives four practical advantages.

First, it separates local dynamics from symmetry topology. The same SymTFT can organize many boundary theories with the same symmetry data.

Second, it makes gauging geometric. Summing over backgrounds becomes a boundary-condition operation.

Third, it packages anomalies invariantly. Local divergence equations are replaced by bulk topological response and relative partition functions.

Fourth, it unifies invertible and non-invertible symmetries. Both are described by topological defects; the difference is in the fusion and boundary endpoint structure.

This does not mean every calculation becomes easier. It means the global bookkeeping becomes less ad hoc.

## Common pitfalls

**“Every bulk defect has a boundary endpoint.”** No. Which defects may end is part of the boundary condition and therefore part of the physical symmetry data.

**“A topological bulk defect always gives a topological boundary operator.”** Not necessarily. The boundary shadow can become non-topological if it couples to local boundary dynamics, unless protected by the boundary condition.

**“The physical and topological boundaries are interchangeable.”** They play different roles. The physical boundary carries local QFT dynamics. The topological boundary chooses how to complete or gauge the relative symmetry data.

**“Anomaly inflow removes the anomaly.”** It does not remove the boundary ’t Hooft anomaly. It explains how the anomalous boundary can exist consistently as the boundary of a bulk theory.

**“Gauging always gives a theory with less symmetry.”** Gauging removes the original global symmetry as a global symmetry, but it often creates a dual symmetry. The SymTFT sees both.

**“The bulk-boundary picture determines all correlators.”** It determines topological constraints and symmetry relations. It does not determine generic non-topological correlators of the boundary QFT.

## Relations to other pages

[Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) gives the big picture. This page develops the boundary dictionary.

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) will focus on the variation-cancellation mechanism.

[Boundary Conditions and Gaugings](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/boundary-conditions-and-gaugings/) will develop the topological boundary choices in detail.

[Defects from the Bulk](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/defects-from-the-bulk/) will explain how bulk defects descend to boundary symmetry operators and charged objects.

[Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/) and [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) give important examples where boundary choices determine genuine operators and dual symmetries.

## Research status

The bulk-boundary viewpoint is established for anomaly inflow, finite-group gaugings, many higher-form examples, BF theories, Dijkgraaf–Witten theories, Chern–Simons examples, and global-form choices in gauge theory.

It is actively developing for non-invertible symmetry, fermionic symmetries, spacetime symmetries, categorical symmetries, and brane-engineered SymTFTs. The basic geometric logic is robust, but the precise category or higher-category of boundary conditions and defects depends on dimension, tangential structure, unitarity assumptions, and whether the theory is bosonic, fermionic, or includes time-reversal or orientation-reversing data.

## Exercises

### Exercise 1: Boundary shadows

Give three possible boundary interpretations of a bulk topological defect.

<details><summary><strong>Solution</strong></summary>

A bulk topological defect may become a boundary symmetry operator, end on a charged boundary operator, or become a boundary-changing interface/domain wall. Depending on the boundary condition, it may also be forbidden to end, which itself carries symmetry information.

</details>

### Exercise 2: Linking as charge measurement

Explain why a boundary charge measurement can be represented by bulk linking.

<details><summary><strong>Solution</strong></summary>

A topological symmetry operator can be deformed freely unless it crosses or links a charged insertion. In the bulk, this crossing becomes a topological linking invariant between defects. The value of the linking invariant records the charge pairing, such as a phase for an Abelian symmetry or a more general defect-network transformation for non-invertible symmetry.

</details>

### Exercise 3: Anomalous partition function as a vector

Why is it useful to regard an anomalous boundary partition function as a vector in a bulk state space?

<details><summary><strong>Solution</strong></summary>

An anomalous partition function may transform by a phase or more general topological factor under background gauge transformations, so it is not naturally a gauge-invariant number. In the bulk-boundary viewpoint, it is an element of the state space assigned by the anomaly/SymTFT to the boundary manifold. Pairing it with a bulk state or topological boundary condition gives a well-defined number.

</details>

### Exercise 4: Gauging and dual symmetry

Why can gauging a finite Abelian symmetry produce a dual symmetry?

<details><summary><strong>Solution</strong></summary>

Gauging sums over the original background bundles, so the original global symmetry no longer acts as an ordinary global symmetry. But the summed gauge configurations have topological sectors that can be measured by characters of the original group. For a finite Abelian group $A$, these characters form the Pontryagin dual $\widehat A$. In the SymTFT, both $A$ and $\widehat A$ appear as complementary boundary or defect data.

</details>

## References

- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality.”
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.”
- Daniel S. Freed and Michael J. Hopkins, “Reflection Positivity and Invertible Topological Phases.”
- Justin Kaidi, Emily Nardoni, Gabi Zafrir, and Yunqin Zheng, “Symmetry TFTs and Anomalies of Non-Invertible Symmetries.”
- Sakura Schäfer-Nameki, lecture notes and reviews on SymTFT and generalized symmetry.
- Theo Johnson-Freyd and David Reutter, references on extended TQFT and higher-categorical boundary-defect structures.

## Version history

- **2026-06-20:** Initial polished draft. Developed the bulk-boundary dictionary for symmetry operators, charged objects, background fields, topological and physical boundaries, anomaly inflow, endpoints, interfaces, and dualities.
