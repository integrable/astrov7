---
title: "Duality Defects"
description: "Explains duality interfaces and self-duality defects, including half-space gauging, non-invertible fusion, operator crossing, and anomaly caveats."
sidebar:
  label: "Duality Defects"
  order: 4
level: Advanced
status: "Polished draft"
source: "Kramers–Wannier; Fröhlich–Fuchs–Runkel–Schweigert; Shao TASI lectures; Antinucci–Benini–Copetti–Galati–Rizi; Heckman–Hübner–Torres–Yu–Zhang."
topics:
  - duality defects
  - non-invertible symmetry
  - topological interfaces
  - half-space gauging
  - self-duality
  - anomaly
canonicalTopics:
  - duality-defect
  - topological-interface
  - self-duality-defect
  - half-space-gauging
  - non-invertible-duality
researchStatus:
  established:
    - "Duality interfaces and self-duality defects are standard in two-dimensional CFT, lattice statistical models, and many modern generalized-symmetry constructions."
    - "A self-duality operation can become a non-invertible topological symmetry defect when it maps the theory back to itself but loses information through gauging or projection."
  active:
    - "Higher-dimensional duality defects, their anomalies, symmetry-TFT descriptions, and their interaction with higher-form symmetries remain active research topics."
---

## Summary

A **duality defect** is a topological interface that implements a duality. It may separate two different presentations of the same QFT, two genuinely different QFTs, or two points in a family of theories related by a duality transformation.

A useful first picture is

$$
\mathcal D_{T\to T'}:\quad T\;|\;T'.
$$

The theory $T$ lives on one side of the interface, and $T'$ lives on the other. If the interface is topological, it can be moved without changing correlation functions, except when it crosses operator insertions, boundaries, or other defects.

When $T'=T$ after a duality identification, the interface becomes a defect inside a single theory. If its fusion has an inverse, it is an ordinary invertible duality symmetry. If its fusion produces a sum of defects, it is a **non-invertible duality defect**. The canonical example is the Kramers–Wannier defect of the Ising model,

$$
\mathcal N\times\mathcal N=1+\eta,
$$

where $\eta$ is the spin-flip defect.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic showing a duality interface between two theories, a self-duality defect after identifying the two sides, and a fusion rule where two duality defects produce a sum of ordinary symmetry defects.](/figures/symmetry-anomalies-topology/duality-defect-interface.svg)

<figcaption>

A duality interface separates two theories or two presentations. At a self-dual point it becomes a defect of a single theory. If the duality operation includes gauging or projection, fusing the defect with its adjoint can produce a sum over symmetry defects rather than the transparent defect alone.

</figcaption>
</figure>

This page explains the general mechanism. The next page treats the Kramers–Wannier defect as the model example.

## Prerequisites

You should know [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/) and [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/). You should also know the basic distinction between a symmetry of one theory and a duality between two theories.

Helpful background includes [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/), and [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/).

## Core idea

A symmetry is an operation from a theory to itself. A duality is an equivalence between two descriptions, or sometimes two different points in theory space:

$$
T\longleftrightarrow T'.
$$

A duality defect is the operator version of this equivalence. Place $T$ on one side of a codimension-one interface and $T'$ on the other. If the interface can be moved freely, it is topological. If it can end on suitable operators or junctions, those endpoints encode how observables of one description are translated into the other.

There are three increasingly special situations.

| Situation | Defect interpretation |
|---|---|
| $T$ and $T'$ are different theories | $\mathcal D_{T\to T'}$ is an interface, not a symmetry of either side alone. |
| $T$ and $T'$ are equivalent presentations | $\mathcal D$ is a duality interface implementing a change of variables or variables plus gauging. |
| $T=T'$ at a self-dual point | $\mathcal D$ is a topological defect of a single QFT and can be a symmetry operator. |

The non-invertible case appears when the duality operation is not reversible as an operator inside the same theory. Gauging is the cleanest reason this happens: gauging projects and sums, so information is lost. The resulting self-duality defect can be topological and exact, but it need not have an inverse.

## Setup and notation

Let $\mathcal D_{T\to T'}$ be a codimension-one interface from a theory $T$ to a theory $T'$. The reverse or adjoint interface is denoted

$$
\mathcal D_{T'\to T}^{\dagger}.
$$

Fusion of interfaces is possible when adjacent theories match:

$$
\mathcal D_{T\to T'}\times \mathcal E_{T'\to T''}
= (\mathcal D\mathcal E)_{T\to T''}.
$$

If $T=T'$, this reduces to ordinary defect fusion inside one theory. The transparent interface is denoted by $1_T$.

A duality interface is **invertible** if there exists an inverse interface such that

$$
\mathcal D_{T\to T'}\times \mathcal D^{-1}_{T'\to T}=1_T,
\qquad
\mathcal D^{-1}_{T'\to T}\times \mathcal D_{T\to T'}=1_{T'}.
$$

It is **non-invertible** if no such inverse exists, even though it may still be topological and may still implement exact relations among observables.

:::note[Source note]
In many papers, “duality defect,” “duality wall,” “topological interface,” and “topological domain wall” are used with overlapping meanings. This page uses “duality defect” for a codimension-one topological interface implementing a duality operation; it becomes a symmetry defect only at a self-dual point or after identifying the two sides.
:::

## Duality interface versus symmetry defect

A duality interface should not be called a symmetry too quickly.

Suppose $T$ and $T'$ are related by a duality. A line or wall between them can be topological, but it is still an interface between two sides. It does not act on a Hilbert space of $T$ alone unless one has specified a way to identify $T'$ with $T$.

At a self-dual point, the story changes. If the duality maps $T$ back to itself, then the interface can be viewed as an operator in $T$:

$$
\mathcal D:T\to T.
$$

Now it can be placed on a closed hypersurface, fused with itself, crossed through insertions, or wrapped on a spatial slice. It becomes symmetry-like. Whether it is invertible depends on its fusion.

This distinction is especially important in families of theories. A theory may have an exact duality transformation that sends a coupling $\lambda$ to $\lambda'$:

$$
T(\lambda)\longleftrightarrow T(\lambda').
$$

The corresponding interface is a symmetry defect of one theory only when $\lambda=\lambda'$ or when the two endpoints are identified as the same QFT by additional data.

## The basic fusion test

The diagnostic for invertibility is fusion with the adjoint. If

$$
\mathcal D\times\mathcal D^\dagger=1,
$$

then $\mathcal D$ is invertible. If instead

$$
\mathcal D\times\mathcal D^\dagger
=1+\mathcal E+\cdots,
$$

then $\mathcal D$ is non-invertible.

In many duality-defect constructions from gauging a finite symmetry group $A$, the schematic rule is

$$
\mathcal N\times\mathcal N^\dagger
=\bigoplus_{a\in A} U_a,
$$

where $U_a$ are topological defects for the original $A$ symmetry. For $A=\mathbb Z_2$, this becomes

$$
\mathcal N\times\mathcal N=1+\eta.
$$

This formula says that doing the duality operation twice does not return a single identity channel. It returns a sum over sectors labeled by the gauged symmetry. That is the algebraic footprint of information lost during gauging.

:::caution[Do not read the sum probabilistically]
The expression $1+\eta$ is a direct sum of topological sectors, not a random outcome. The composite defect decomposes into superselection channels. Which channel appears in a correlator depends on the surrounding defect network, operator insertions, and junction data.
:::

## Half-space gauging

A clean way to produce duality defects is to gauge a symmetry only on one side of a wall.

Let $T$ have a finite anomaly-free symmetry $A$. Gauging $A$ produces a new theory $T/A$. There is a natural interface between $T$ and $T/A$:

$$
\mathcal G_{T\to T/A}.
$$

On one side, $A$ is global. On the other side, the $A$ background has been summed over. The interface is topological if the gauging operation is topological and no local scale is introduced.

If the theory is self-dual under gauging,

$$
T/A\simeq T,
$$

then the gauging interface can be reinterpreted as a defect $\mathcal N$ of $T$ itself. Because gauging sums over $A$ bundles and projects onto $A$-invariant data, $\mathcal N$ is generally not invertible.

The resulting fusion rule often remembers the symmetry that was gauged:

$$
\mathcal N\times\mathcal N^\dagger
=\bigoplus_{a\in A}U_a.
$$

This is one of the most important construction mechanisms for non-invertible duality defects.

## What the defect does to operators

A duality defect can act on operators in several ways.

First, it can map an operator of $T$ to an operator of $T'$ when crossed through the interface:

$$
\mathcal O_T\quad\longmapsto\quad\mathcal O_{T'}.
$$

Second, it can map local operators to disorder operators. This is common in order-disorder dualities. In the Ising model, the duality interface relates spin variables to disorder variables.

Third, it can attach a defect endpoint or junction. A local operator may not pass through the defect as another ordinary local operator. It may become the endpoint of a line or the endpoint of a branch cut. This is one reason a duality defect is more than a field redefinition.

Fourth, it can project. In gauging-based examples, crossing the defect can remove operators that are not compatible with the gauged side, or map them to sums over gauge-invariant dressed operators.

Thus the safe statement is not “duality defects act as matrices on fields.” It is:

$$
\text{duality defects translate operator data across a topological interface.}
$$

Sometimes that translation is a matrix. Often it is a richer defect operation.

## Order-disorder duality

The prototype of a duality defect is an order-disorder duality wall. In a spin model, order variables are local spin variables. Disorder variables create branch cuts or twisted boundary conditions. A Kramers–Wannier interface converts one description to the other.

This already shows why duality defects can be non-invertible. A local spin operator and a disorder operator live naturally in different presentations. If one tries to package both into a single self-dual theory, the duality operation may require extra sector data. The missing sector information is precisely what appears as a sum in the fusion rule.

In continuum language, order and disorder operators may be endpoints of different topological lines. A duality defect can move these endpoints around or exchange their roles. The defect is topological at criticality, where the order-disorder map becomes an exact symmetry of the scaling theory.

## Duality defects in gauge theory

Duality defects also appear in gauge theory. Electric-magnetic duality, S-duality, and gauging of higher-form symmetries can produce codimension-one interfaces that act nontrivially on Wilson and ’t Hooft lines.

For example, a duality wall may transform an electric line into a magnetic line, or a dyonic line into another dyonic line:

$$
(q_e,q_m)\mapsto (q'_e,q'_m).
$$

If the duality transformation is invertible and maps the theory to itself, the corresponding wall may be an invertible duality symmetry. If the construction includes gauging a finite one-form symmetry or summing over background fluxes, the resulting wall can be non-invertible.

The details depend on the gauge group global form, the theta angle, spin structure, line-operator lattice, and possible mixed anomalies. This is why four-dimensional duality defects are usually more delicate than the Ising example.

## Anomalies of duality defects

Not every formal self-duality can be gauged or promoted to a consistent topological defect. Duality defects can carry anomalies.

There are two related questions:

1. Can the duality interface be defined consistently on arbitrary backgrounds?
2. Can the duality defect itself be gauged or summed over as part of a larger symmetry construction?

The answer can fail because of an obstruction in a one-higher-dimensional symmetry TFT, because of a mismatch of background fields, or because of a residual anomaly of an invertible symmetry mixed with the duality.

For an ordinary global symmetry, an anomaly obstructs gauging. For a non-invertible duality defect, the corresponding obstruction is subtler because “gauging the defect” is not simply summing over a group bundle. One often needs a duality-invariant algebra of condensable objects, a compatible boundary condition in a symmetry TFT, or fractionalization data.

:::note[Research-status note]
The anomaly theory of non-invertible duality defects is an active subject. Two-dimensional examples are relatively well understood through fusion categories and orbifold theory. Higher-dimensional examples often use symmetry TFT, higher-form symmetries, and duality walls.
:::

## Duality defects and categorical symmetry

A duality defect is a natural source of categorical symmetry because its fusion is rarely a group law. Instead of group elements acting on a Hilbert space, one has a collection of topological defects acting on sectors, operators, and boundary conditions.

The categorical replacement for a representation is a module category: a space of boundary conditions, sectors, or objects on which the fusion category acts. This is the right language when a non-invertible duality defect maps one sector to a direct sum of sectors.

For a beginner, the important point is not to learn all categorical terms at once. It is to stop expecting duality defects to behave like unitary operators with inverses. Their exactness is topological, not group-theoretic.

## Examples to keep in mind

| Example | Duality operation | Defect lesson |
|---|---|---|
| Ising model | Kramers–Wannier order-disorder duality | At criticality the duality line is topological and non-invertible. |
| $\mathbb Z_N$ clock/Potts models | Generalized order-disorder duality | Self-dual defects often fit Tambara–Yamagami-type fusion rules. |
| Orbifold CFTs | Gauging a finite symmetry | Interfaces between original and gauged theories become non-invertible at self-dual points. |
| 4D gauge theories | Electric-magnetic or S-duality plus higher-form gauging | Global form and line-operator lattices affect the defect fusion algebra. |
| Symmetry TFT | Boundary condition changes | Duality defects can be realized by moving branch cuts or changing boundary conditions in one higher dimension. |

## Common pitfalls

**Calling every duality a symmetry.** A duality between $T$ and $T'$ is not a symmetry of $T$ unless $T'$ has been identified with $T$.

**Expecting a duality defect to act on elementary fields.** Many dualities exchange local and nonlocal variables. The correct action may be on operators, disorder insertions, defects, or boundary conditions.

**Assuming self-duality implies invertibility.** A self-dual theory can have a non-invertible self-duality defect. The fusion rule, not the word “self-dual,” decides invertibility.

**Forgetting sector sums.** Gauging projects and sums over bundles. The fusion of the corresponding defect can produce a direct sum over symmetry defects.

**Ignoring anomalies.** A formal duality transformation may fail to define a consistent topological defect on all backgrounds.

**Treating the Ising example as the whole subject.** Kramers–Wannier is the canonical first example, but duality defects also appear in rational CFT, gauge theory, lattice models, and symmetry TFT.

## Relations to other pages

[Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/) explains why topological deformation is the symmetry principle. [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/) explains how to read the sums that appear when duality defects are fused. The next page, [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/), gives the most important worked example.

Later pages on [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) and [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) develop the systematic construction of such defects.

## Research status

Duality defects in two-dimensional CFT and lattice statistical models are established and extremely useful. The Ising and Potts examples are standard teaching examples. Interfaces between CFTs and their orbifolds give a broad class of non-invertible defects.

In higher dimensions, duality defects are a lively research area. Examples involving S-duality, finite higher-form gauging, global forms of gauge groups, mixed anomalies, and symmetry TFT have clarified that duality defects can carry rich fusion algebras. The general classification is not settled.

## Exercises

### Exercise 1: Interface or symmetry?

Suppose a duality maps a theory $T(\lambda)$ to $T(1/\lambda)$. When is the corresponding interface a symmetry defect of one theory?

<details><summary><strong>Solution</strong></summary>

It is an interface between two different points in theory space in general. It becomes a symmetry defect of a single theory when the two sides are identified, for example at a self-dual point $\lambda=1/\lambda$, or after specifying an equivalence between $T(\lambda)$ and $T(1/\lambda)$ as the same QFT. Without such an identification, it is a duality interface, not a symmetry operator of one theory.

</details>

### Exercise 2: Non-invertibility from fusion

Let $\mathcal N$ obey

$$
\mathcal N\times\mathcal N^\dagger=1+\eta,
\qquad
\eta\ne0.
$$

Show that $\mathcal N$ is not invertible.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ were invertible, there would be a defect $\mathcal N^{-1}$ such that

$$
\mathcal N\times\mathcal N^{-1}=1.
$$

In a unitary setting the adjoint is the natural candidate for the inverse, but the given fusion produces $1+\eta$, not $1$. The extra nontrivial channel means the composite defect is not the transparent defect. Therefore $\mathcal N$ has no inverse under fusion and is non-invertible.

</details>

### Exercise 3: Half-space gauging

Let $A$ be a finite anomaly-free symmetry of $T$, and suppose $T/A\simeq T$. Explain why the gauging interface can become a defect of $T$ and why it is usually non-invertible.

<details><summary><strong>Solution</strong></summary>

The interface between $T$ and $T/A$ becomes a defect of $T$ after using the equivalence $T/A\simeq T$ to identify the two sides. It is usually non-invertible because gauging sums over $A$ backgrounds and projects onto $A$-invariant data. That operation forgets information. When the interface is fused with its adjoint, the lost sector data reappears as a sum over $A$ symmetry defects, schematically

$$
\mathcal N\times\mathcal N^\dagger=\bigoplus_{a\in A}U_a.
$$

</details>

### Exercise 4: Operator crossing

Why might a duality defect fail to map a local operator to another local operator?

<details><summary><strong>Solution</strong></summary>

A duality can exchange order variables with disorder variables. Disorder variables are often defined as endpoints of branch cuts or defects rather than as ordinary local polynomials in the original fields. Crossing a duality defect may therefore attach a defect endpoint, produce a sum over sectors, or require additional junction data. The duality still acts topologically, but not necessarily as a simple map from local fields to local fields.

</details>

## References

- H. A. Kramers and G. H. Wannier, “Statistics of the Two-Dimensional Ferromagnet,” Parts I and II.
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, “Kramers–Wannier Duality from Conformal Defects.”
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, “Duality and Defects in Rational Conformal Field Theory.”
- L. Bhardwaj and Y. Tachikawa, “On Finite Symmetries and Their Gauging in Two Dimensions.”
- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.”
- A. Antinucci, F. Benini, C. Copetti, G. Galati, and G. Rizi, “Anomalies of Non-Invertible Self-Duality Symmetries: Fractionalization and Gauging.”
- J. J. Heckman, M. Hübner, E. Torres, X. Yu, and H. Y. Zhang, “Top Down Approach to Topological Duality Defects.”

## Version history

- **2026-06-20:** Initial polished draft. Added duality-interface definition, self-duality criterion, half-space gauging construction, fusion test, operator-crossing cautions, gauge-theory examples, anomaly caveats, and exercises.
