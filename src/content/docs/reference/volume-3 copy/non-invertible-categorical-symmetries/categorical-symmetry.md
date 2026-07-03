---
title: "Categorical Symmetry"
description: "Explains categorical symmetry as the symmetry data carried by topological defects, junctions, fusion, associators, modules, and charges."
sidebar:
  label: "Categorical Symmetry"
  order: 6
level: Advanced
status: "Polished draft"
source: "Etingof–Gelaki–Nikshych–Ostrik; Fröhlich–Fuchs–Runkel–Schweigert; Schäfer-Nameki ICTP lectures; Bhardwaj–Schäfer-Nameki; standard 2d CFT and SymTFT references."
topics:
  - categorical symmetry
  - fusion category
  - topological defects
  - junctions
  - modules
  - SymTFT
canonicalTopics:
  - categorical-symmetry
  - fusion-category-symmetry
  - topological-defect-category
  - defect-junction
  - symmetry-category
researchStatus:
  established:
    - "In two-dimensional QFT and rational CFT, topological line defects and their fusion categories are a standard language for ordinary and non-invertible symmetry."
    - "For finite semisimple examples, categorical symmetry refines fusion-rule data by including junction spaces, associators, duals, and module actions."
  active:
    - "Higher-dimensional categorical symmetry, higher-categorical charges, nonsemisimple examples, fermionic refinements, and SymTFT classifications remain active research areas."
---

## Summary

A **categorical symmetry** is symmetry data organized not merely by a group, but by a category of topological defects and junctions.

For an ordinary finite group symmetry, the topological symmetry defects are labeled by group elements:

$$
U_g\times U_h=U_{gh},
\qquad
U_g^{-1}=U_{g^{-1}}.
$$

This is a very special case. More generally, topological defects can fuse as

$$
\mathcal D_a\times\mathcal D_b
=\bigoplus_c N_{ab}{}^c\,\mathcal D_c,
$$

and there may be no inverse for $\mathcal D_a$. The data are no longer just group multiplication. One must also specify junction operators, associativity isomorphisms, dual defects, module actions on charged objects, and consistency relations.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic of categorical symmetry data: topological defects as objects, junctions as morphisms, fusion as a tensor product, associators as moves between fusion orders, and modules as charged sectors.](/figures/symmetry-anomalies-topology/categorical-symmetry-data.svg)

<figcaption>

Categorical symmetry keeps track of more than the fusion coefficients $N_{ab}{}^c$. It includes defects as objects, junctions as morphisms, fusion as a monoidal product, associators as local moves of defect networks, and modules as the spaces on which the symmetry acts.

</figcaption>
</figure>

The slogan is:

$$
\text{group symmetry}
\subset
\text{invertible topological defects}
\subset
\text{categorical symmetry}.
$$

This page explains what the word “categorical” is buying us physically. It is not a decorative synonym for “fancy symmetry.” It is the minimal language needed once topological defects can split, join, and fuse non-invertibly.

## Prerequisites

You should know [Invertible versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/), [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/), and [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/).

It also helps to know [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) and [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/). This page uses a small amount of category language, but every term is translated into defect-network physics.

## Core idea

A group remembers multiplication. A category remembers processes.

For ordinary symmetry, it is often enough to know that group elements multiply:

$$
g_1g_2=g_3.
$$

For topological defects, this is not enough. Defects can meet at junctions, split into sums of channels, wrap around charged operators, end on boundaries, and act on defect-local operators. The physically relevant object is therefore not just a set of labels, but a calculus of defect networks.

A categorical symmetry contains:

| Categorical word | Defect-network meaning |
|---|---|
| Object | A topological defect type, such as $1$, $\eta$, or $\mathcal N$. |
| Morphism | A topological junction or local operator changing one defect configuration into another. |
| Monoidal product | Fusion of parallel defects. |
| Unit object | The transparent defect $1$. |
| Dual object | The orientation-reversed or adjoint defect. |
| Associator | The local move comparing $(a\times b)\times c$ with $a\times(b\times c)$. |
| Module | A space of charged objects, boundary conditions, or sectors on which defects act. |

A fusion rule such as

$$
\mathcal N^2=1+\eta
$$

is only the visible skeleton. The category also specifies how three $\mathcal N$ defects associate, what junctions are allowed, and how $\mathcal N$ acts on operators or boundary conditions.

## Setup and notation

For most examples in this chapter, the symmetry category is denoted by $\mathcal C$. Its simple objects are topological defects

$$
a,b,c,\ldots\in\mathcal C.
$$

Fusion is written as

$$
a\otimes b.
$$

If the category is semisimple, this decomposes as

$$
a\otimes b\simeq\bigoplus_c N_{ab}{}^c\,c,
$$

where $N_{ab}{}^c$ are nonnegative integers. The transparent defect is the unit object $1$:

$$
1\otimes a\simeq a\simeq a\otimes 1.
$$

The dual or adjoint defect is denoted $a^\vee$ or $a^\dagger$, depending on context. It is the defect with opposite orientation, together with evaluation and coevaluation junctions allowing $a$ and $a^\vee$ to annihilate or be created in appropriate channels.

:::note[Source note]
The notation $a\otimes b$ is category-theory notation for fusion. Earlier pages used $\times$ for the same physical operation. This page uses $\otimes$ when emphasizing the monoidal-category structure and $\times$ when emphasizing the defect-network picture.
:::

## From groups to pointed categories

An ordinary finite group symmetry can be viewed categorically. The corresponding topological defects $U_g$ obey

$$
U_g\otimes U_h\simeq U_{gh}.
$$

Every simple object is invertible:

$$
U_g\otimes U_{g^{-1}}\simeq 1.
$$

This is called a **pointed** fusion category when all simple objects are invertible. In the simplest bosonic case it is close to the category of $G$-graded vector spaces, often denoted $\mathrm{Vec}_G$, possibly with a twist in the associator.

The twist matters. Two defect theories may have the same fusion rule

$$
U_g\otimes U_h=U_{gh}
$$

but different associators. In physics, such differences can encode discrete torsion, anomaly data, or different topological phases used to decorate symmetry defects.

Thus even for group-like symmetries, the categorical viewpoint can reveal more structure than the multiplication table alone.

## Fusion coefficients are not the whole category

A common mistake is to identify a categorical symmetry with the integers $N_{ab}{}^c$. Those integers are important, but incomplete.

Consider three defects $a,b,c$. There are two ways to fuse them:

$$
(a\otimes b)\otimes c,
\qquad
a\otimes(b\otimes c).
$$

Topological invariance says these two fusion orders should be related by local moves. The associator is the isomorphism

$$
\alpha_{a,b,c}:(a\otimes b)\otimes c\longrightarrow a\otimes(b\otimes c).
$$

In a basis of junction spaces, its matrix elements are often called **F-symbols**. They obey pentagon identities. Physically, the pentagon identity says that different sequences of local defect-network moves give the same final network.

For braided or higher-dimensional situations there are also braiding or crossing data. In two-dimensional Euclidean QFT, line defects can often pass through each other only with specified junction data. In higher-dimensional QFT, the geometry and codimension of defects changes what “braiding” even means.

:::caution[Fusion algebra versus category]
The fusion algebra remembers the products of simple labels. The category remembers the vector spaces of junctions and the local moves between networks. Two categories can share fusion coefficients but differ physically.
:::

## Junctions and defect-local operators

A morphism in the defect category is a topological junction. If $a$ and $b$ are line defects in two dimensions, then a local junction from $a$ to $b$ is an element of

$$
\operatorname{Hom}(a,b).
$$

More generally, junctions can join several incoming defects to several outgoing defects. A trivalent junction from $a\otimes b$ to $c$ belongs to

$$
\operatorname{Hom}(a\otimes b,c).
$$

The dimension of this space is the fusion multiplicity in semisimple examples:

$$
\dim\operatorname{Hom}(a\otimes b,c)=N_{ab}{}^c.
$$

But the actual vector space matters, not only its dimension. Choosing a basis of junctions is like choosing Clebsch–Gordan coefficients. Physical correlators and defect-network evaluations can depend on the junction data.

Defect-local operators are local operators living on a defect worldvolume. They are not necessarily topological. When a defect is topological, its topological junctions form the protected part of its operator algebra, but there can also be non-topological defect excitations with scaling dimensions or masses.

## Quantum dimension

A simple topological defect $a$ has a **quantum dimension** $d_a$. It measures, roughly, how much the defect contributes to the size of state spaces or partition functions when it wraps nontrivial cycles.

In semisimple fusion categories, the quantum dimensions solve

$$
d_a d_b=\sum_c N_{ab}{}^c d_c.
$$

For an invertible defect, $d_a=1$. A non-invertible defect has

$$
d_a>1
$$

in unitary examples.

For the Ising fusion rule

$$
\mathcal N\otimes\mathcal N=1\oplus\eta,
\qquad
\eta\otimes\eta=1,
$$

we get

$$
d_{\mathcal N}^2=d_1+d_\eta=2,
$$

so

$$
d_{\mathcal N}=\sqrt2.
$$

This is one of the fastest diagnostics that $\mathcal N$ cannot be an ordinary group-like symmetry operator.

## Actions and modules

A symmetry should act on something. For an ordinary group, a representation is a vector space $V$ with maps

$$
G\to GL(V).
$$

For a fusion category, the analogue is not an ordinary representation but a **module category** or higher-categorical module. Physically, this may be a category of boundary conditions, a space of defect sectors, or a collection of charged operators with possible attached defects.

The action is written schematically as

$$
a\triangleright X,
$$

where $a\in\mathcal C$ is a topological defect and $X$ is an object being acted on. The compatibility condition is

$$
(a\otimes b)\triangleright X
\simeq
a\triangleright(b\triangleright X).
$$

For ordinary group symmetry this reduces to the usual rule

$$
g_1(g_2 X)=(g_1g_2)X.
$$

For non-invertible symmetry, $a\triangleright X$ may be a direct sum or a more general object. A defect can map a genuine local operator to an operator attached to another defect. That is not a bug; it is one of the basic new phenomena.

## Categorical symmetry versus anomaly

Categorical symmetry and anomaly are related but distinct.

A categorical symmetry is part of the topological-defect data of a QFT. An anomaly is an obstruction to gauging or to realizing the symmetry in a strictly onsite or decoupled way. A category may be perfectly consistent as a symmetry category of a boundary theory while requiring a one-higher-dimensional bulk to realize its gauging or defect network naturally.

In modern language, a symmetry category $\mathcal C$ can often be encoded by a **symmetry TFT** in one higher dimension. The physical QFT appears as a boundary condition of that TFT, and the topological defects of the SymTFT organize generalized charges and symmetry operations.

This perspective is powerful, but it should not obscure the basic defect picture. The first-pass definition remains: categorical symmetry is the algebraic-topological data of topological defects and their junctions inside the QFT.

## Examples

### Ordinary finite group symmetry

For a finite group $G$, the simple topological defects are $U_g$. Their fusion is

$$
U_g\otimes U_h=U_{gh}.
$$

Every defect is invertible, so this is categorical but group-like. The category remembers the transparent defect, fusion, and possibly associator twists.

### Ising non-invertible symmetry

The critical Ising defect category has simple objects

$$
1,\qquad \eta,\qquad \mathcal N,
$$

with

$$
\eta^2=1,\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,\qquad
\mathcal N^2=1+\eta.
$$

The object $\eta$ is the spin-flip defect. The object $\mathcal N$ is the Kramers–Wannier duality defect. The non-invertibility is visible in $\mathcal N^2$, but the full Ising category also contains associators and junction data.

### Representation category symmetry

In some two-dimensional examples, the symmetry category is $\mathrm{Rep}(G)$, the category of representations of a finite group $G$. This is not the same as an ordinary $G$ symmetry. Its simple objects are irreducible representations, and fusion is tensor product of representations:

$$
R_i\otimes R_j=\bigoplus_k N_{ij}{}^k R_k.
$$

If $G$ is nonabelian, some irreducible representations have dimension greater than one, so the corresponding objects are non-invertible.

## Common pitfalls

**“Categorical symmetry means the theory has a category somewhere.”** Too vague. The category must be the topological-defect and junction data acting on the QFT.

**“Fusion rules determine everything.”** Not enough. Associators, junction spaces, duals, module actions, and possible braiding data matter.

**“Category theory is optional formalism.”** For invertible groups, maybe. For non-invertible defects, it is the natural bookkeeping language for the physical operations.

**“A non-invertible defect acts as a nonunitary operator on the Hilbert space, so it is not a symmetry.”** Ordinary unitarity of a single operator is not the defining criterion here. The defining criterion is topological deformation invariance and consistent action on observables or sectors.

**“Every categorical symmetry is fully understood by a fusion category.”** In two-dimensional semisimple bosonic examples, often yes. In higher dimensions, fermionic systems, nonsemisimple theories, or systems with extended charged objects, higher categories and extra structures appear.

## Relations to other pages

[Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/) gives the geometric origin of categorical symmetry. [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/) gives the first algebraic shadow. This page explains why fusion rules must be completed by junction and associator data.

[Non-Invertible Ward Identities: Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/non-invertible-ward-identities-preview/) explains how categorical symmetry constrains correlators. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) will explain how categorical symmetry arises from gauging and generalized orbifolds. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) will package the same data in one higher dimension.

## Research status

For two-dimensional rational CFT and many semisimple topological-defect systems, categorical symmetry is mature and precise. Fusion categories, module categories, and related tensor-categorical structures give a detailed language for line defects, junctions, and boundary conditions.

For higher-dimensional QFTs the subject is rapidly developing. The appropriate structures are often fusion higher-categories rather than ordinary fusion categories. Fermionic systems, nonsemisimple theories, continuous symmetries with noncompact sectors, and theories involving gravity require additional care. The guiding principle remains stable: symmetry is encoded by topological defects and their consistent fusion/action data.

## Exercises

### Exercise 1: Pointed category from a group

Let $G$ be a finite group and let simple defects be $U_g$ with fusion $U_g\otimes U_h=U_{gh}$. Show that every simple object is invertible.

<details><summary><strong>Solution</strong></summary>

For each $g\in G$, the group inverse $g^{-1}$ exists. Therefore

$$
U_g\otimes U_{g^{-1}}=U_e=1,
\qquad
U_{g^{-1}}\otimes U_g=U_e=1.
$$

So every $U_g$ has an inverse defect $U_{g^{-1}}$. The category is pointed: all simple objects are invertible.

</details>

### Exercise 2: Quantum dimension of the Ising duality defect

Use

$$
\mathcal N\otimes\mathcal N=1\oplus\eta,
\qquad
\eta\otimes\eta=1
$$

to compute $d_\eta$ and $d_{\mathcal N}$ in a unitary normalization with $d_1=1$.

<details><summary><strong>Solution</strong></summary>

From $\eta\otimes\eta=1$,

$$
d_\eta^2=d_1=1.
$$

In a unitary fusion category, quantum dimensions are positive, so $d_\eta=1$. Then

$$
d_{\mathcal N}^2=d_1+d_\eta=2,
$$

so

$$
d_{\mathcal N}=\sqrt2.
$$

Since $d_{\mathcal N}\ne1$, $\mathcal N$ is not invertible.

</details>

### Exercise 3: Why associators matter

Explain why the equality of fusion coefficients does not guarantee that two categorical symmetries are the same.

<details><summary><strong>Solution</strong></summary>

Fusion coefficients only tell us which simple labels appear in a product and with what multiplicities. They do not specify the vector spaces of junctions or the associator maps comparing $(a\otimes b)\otimes c$ with $a\otimes(b\otimes c)$. Different associators, or $F$-symbols, can give inequivalent defect-network evaluations even when the fusion coefficients agree. Therefore the full category contains more data than the fusion algebra.

</details>

## References

- P. Etingof, S. Gelaki, D. Nikshych, and V. Ostrik, *Tensor Categories*, for the mathematical language of tensor and fusion categories.
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, papers on topological defects and dualities in rational CFT.
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” for a physics-oriented introduction to non-invertible and categorical symmetry.
- L. Bhardwaj and S. Schäfer-Nameki, “Generalized Charges, Part II: Non-Invertible Symmetries and the Symmetry TFT,” for the SymTFT and generalized-charge viewpoint.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the topological-operator framework that categorical symmetry generalizes.

## Version history

- **2026-06-20:** Initial polished draft. Introduced categorical symmetry through defects, junctions, fusion, associators, quantum dimensions, modules, and SymTFT connections.
