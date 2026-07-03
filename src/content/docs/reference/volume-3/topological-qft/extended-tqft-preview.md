---
title: "Extended TQFT: Preview"
description: "Introduces extended topological quantum field theory, where a TQFT assigns algebraic data not only to closed spatial manifolds but also to lower-dimensional corners, defects, and local pieces."
sidebar:
  label: "Extended TQFT Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Atiyah; Segal; Baez–Dolan; Freed; Lurie; Freed–Teleman; standard extended TQFT and cobordism-hypothesis references."
topics:
  - extended TQFT
  - bordism categories
  - cobordism hypothesis
  - fully dualizable objects
  - defects
  - boundary conditions
  - factorization
canonicalTopics:
  - extended-tqft
  - bordism-category
  - cobordism-hypothesis
  - fully-dualizable-object
  - local-to-global-tqft
researchStatus:
  established:
    - "Ordinary Atiyah–Segal TQFT assigns vector spaces to closed spatial manifolds and linear maps to bordisms; extended TQFT refines this by assigning algebraic data to lower-dimensional manifolds and corners."
    - "The cobordism-hypothesis viewpoint says, roughly, that fully extended framed TQFTs are classified by fully dualizable objects in a suitable higher category."
  active:
    - "Extended TQFT is a mathematically rich and still-developing language for defects, boundaries, non-invertible symmetries, factorization, and SymTFT; this page is a physics-facing preview."
---

## Summary

An ordinary $d$-dimensional TQFT assigns:

$$
\text{closed }(d-1)\text{-manifold }\Sigma
\longmapsto
\text{vector space }Z(\Sigma),
$$

and

$$
\text{bordism }M:\Sigma_{\mathrm{in}}\to\Sigma_{\mathrm{out}}
\longmapsto
\text{linear map }Z(M):Z(\Sigma_{\mathrm{in}})\to Z(\Sigma_{\mathrm{out}}).
$$

An **extended TQFT** goes further. It assigns algebraic data not only to $(d-1)$-manifolds and $d$-dimensional bordisms, but also to lower-dimensional pieces: codimension-two corners, codimension-three junctions, and ultimately points. In a fully extended theory, the slogan is

$$
\text{local data at a point determines the whole TQFT}
$$

provided the point-data is sufficiently dualizable in the target higher category.

This preview explains why physicists should care. Extended TQFT is the natural language for boundaries, interfaces, defects, junctions, fusion categories, modular tensor categories, SymTFTs, and the local-to-global structure of topological phases.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Extended TQFT ladder showing assignments to points, lines, surfaces, spatial manifolds, and bordisms.](/figures/symmetry-anomalies-topology/extended-tqft-ladder.svg)

<figcaption>

Ordinary TQFT remembers closed spatial manifolds and spacetime bordisms. Extended TQFT keeps descending: it assigns data to codimension-two corners, codimension-three junctions, and ultimately points. This is why it naturally describes defects, boundaries, and fusion.

</figcaption>
</figure>

This page is a preview, not a theorem-first account of higher categories. The aim is to give the conceptual map needed to read modern pages on defects, categorical symmetry, and SymTFT without being ambushed by the word “extended.”

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/), [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/), [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/), and [Defects from the Bulk](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/defects-from-the-bulk/). You should also be comfortable with the idea that cutting a manifold should turn a path integral into a state, and gluing should pair states.

The mathematical prerequisites are bordisms, monoidal categories, dual vector spaces, and the idea that higher categories have objects, morphisms, morphisms between morphisms, and so on. This page explains these ideas informally.

## Core idea

The ordinary Atiyah–Segal definition of a $d$-dimensional TQFT can be summarized as a symmetric monoidal functor

$$
Z:\operatorname{Bord}_d\longrightarrow \operatorname{Vect}.
$$

Here $\operatorname{Bord}_d$ is a category whose objects are closed $(d-1)$-manifolds and whose morphisms are $d$-dimensional bordisms. The tensor product is disjoint union on the geometric side and tensor product on the vector-space side.

This definition knows how to cut along codimension-one hypersurfaces. But many physical structures live at higher codimension:

| Object in QFT | Support | Why ordinary TQFT is not enough |
|---|---:|---|
| boundary condition | codimension $1$ | needs boundary sectors and boundary-changing operators |
| interface | codimension $1$ | needs composition and folding |
| line defect in 3d | codimension $2$ | needs endpoint and junction data |
| local operator in 2d | codimension $2$ | needs operator product algebra |
| junction of defects | higher codimension | needs morphisms between defects |
| point in a fully local theory | codimension $d$ | should carry the fundamental local datum |

Extended TQFT adds these assignments. Instead of assigning only vector spaces and linear maps, it assigns objects, categories, functors, natural transformations, and their higher analogues.

The shortest slogan is

$$
\text{ordinary TQFT cuts once; extended TQFT cuts all the way down}.
$$

## Setup and conventions

A $k$-extended $d$-dimensional TQFT assigns data down to codimension $k$. A fully extended $d$-dimensional TQFT assigns data down to points.

There are many choices of tangential structure: oriented, framed, spin, Pin, $G$-structured, and more. To avoid a notation swamp, write

$$
\operatorname{Bord}_d^{\mathcal S}
$$

for a bordism object with structure $\mathcal S$. Examples include

$$
\mathcal S=\text{oriented},\quad \text{framed},\quad \text{spin}.
$$

The target is not always $\operatorname{Vect}$. For extended theories, the target must be a higher category. Schematically,

$$
Z:\operatorname{Bord}_{d}^{\mathcal S,\mathrm{ext}}\longrightarrow \mathcal C.
$$

The object assigned to a point is denoted

$$
Z(\mathrm{pt})\in\mathcal C.
$$

The details of $\mathcal C$ determine what kind of TQFT one is constructing: linear, unitary, finite, semisimple, derived, higher-categorical, or otherwise.

:::note[Source note: preview-level notation]
The symbols $\operatorname{Bord}_{d}^{\mathcal S,\mathrm{ext}}$ and $\mathcal C$ hide substantial higher-category technology. This page uses them as a map, not as a formal definition.
:::

## Ordinary TQFT as the first layer

In ordinary TQFT, a closed $(d-1)$-manifold $\Sigma$ is assigned a vector space,

$$
\Sigma\longmapsto Z(\Sigma).
$$

A $d$-dimensional bordism $M$ from $\Sigma_0$ to $\Sigma_1$ is assigned a linear map,

$$
M:\Sigma_0\to\Sigma_1
\quad\longmapsto\quad
Z(M):Z(\Sigma_0)\to Z(\Sigma_1).
$$

A closed $d$-manifold $M$ is a bordism from the empty set to itself, so it gives a number,

$$
Z(M)\in \mathbb C.
$$

The gluing axiom says that if $M=M_2\circ M_1$, then

$$
Z(M)=Z(M_2)\circ Z(M_1).
$$

Disjoint union becomes tensor product:

$$
Z(\Sigma_1\sqcup\Sigma_2)=Z(\Sigma_1)\otimes Z(\Sigma_2).
$$

This is already powerful. But it does not fully describe local operators, defect endpoints, or the algebra of boundary conditions. For that, one must cut the manifold along smaller pieces.

## What extension adds

A two-dimensional fully extended TQFT might assign:

| Geometry | Algebraic data |
|---|---|
| point | algebra $A$ or object in a suitable category |
| interval | module or bimodule data |
| circle | vector space such as Hochschild homology or center-like data |
| surface bordism | linear map |

A three-dimensional extended TQFT might assign:

| Geometry | Algebraic data |
|---|---|
| point | fusion category or related object |
| circle | category of boundary/line data |
| surface | vector space |
| 3-manifold | number |

These examples are schematic, but they convey the pattern. Lower-dimensional geometric pieces receive richer algebraic objects. Higher-dimensional pieces receive morphisms, maps, and numbers built from those objects.

This is why extended TQFT appears naturally in physics. Boundaries are not afterthoughts. Defects and junctions carry local degrees of freedom. Fusion is not just multiplication; it is composition in a higher-categorical world.

## Dualizability and why it appears

In ordinary quantum mechanics, a finite-dimensional vector space $V$ has a dual $V^*$. There are evaluation and coevaluation maps,

$$
V^*\otimes V\to \mathbb C,
\qquad
\mathbb C\to V\otimes V^*.
$$

These maps express the ability to create and annihilate pairs. In TQFT, the same idea is geometric: cups and caps are bordisms, so the algebraic object assigned to a point must have duals compatible with those bordisms.

In higher dimensions, one needs higher versions of duals. This leads to **fully dualizable objects**. Roughly, an object is fully dualizable if it has all the adjoints and duals needed to evaluate every possible local cup, cap, corner, and higher-dimensional bend.

The cobordism-hypothesis slogan is:

$$
\text{fully extended framed TQFTs}
\quad\leftrightarrow\quad
\text{fully dualizable objects in the target higher category}.
$$

This is not a computational recipe by itself. It is a structural classification principle. It says that a fully local topological theory is determined by its value on a point, provided that value has enough finiteness and duality.

## Examples

### Two-dimensional TQFT and Frobenius algebras

A standard oriented two-dimensional TQFT is closely related to a commutative Frobenius algebra $A$. The multiplication

$$
m:A\otimes A\to A
$$

comes from a pair-of-pants surface, while the trace pairing

$$
\langle a,b\rangle=\epsilon(ab)
$$

comes from the cap/cup structure. Associativity is topological invariance under different decompositions of surfaces.

Extended versions refine this by keeping track of intervals, boundary conditions, and modules. The algebra $A$ is no longer just a vector space attached to a circle; it becomes local data attached lower down.

### Three-dimensional TQFT and fusion categories

In three dimensions, line operators and their fusion become central. Fully extended finite-type examples often involve fusion categories or modular tensor categories, depending on the amount of structure and whether one is describing boundaries, bulk lines, or closed theories.

Chern–Simons theory provides the physics template. Wilson lines form braided tensor categories. Boundary conditions lead to module categories. Junctions of lines are morphism spaces. These are exactly the sorts of data ordinary non-extended TQFT compresses too much.

### Dijkgraaf–Witten theory

Finite-group gauge theory is an especially friendly extended TQFT laboratory. The fields are flat $G$-bundles or cocycles; the action may be twisted by a cocycle

$$
\omega\in H^d(BG,U(1)).
$$

The extended theory assigns categories of representations, twisted sectors, and defect data to lower-dimensional manifolds. It is one of the cleanest places to see how gauging, orbifolding, defects, and finite homotopy theory become the same topological story.

### Invertible TQFTs

Invertible TQFTs are also naturally extended. They assign one-dimensional state spaces to closed spatial manifolds and invertible phases under stacking. Their fully extended data are closely related to generalized cohomology and bordism invariants.

In physics, invertible TQFTs are anomaly theories and SPT response actions. Extended language matters because anomalies can live on boundaries, interfaces, and defects, not only on closed manifolds.

## Boundaries, defects, and modules

An extended TQFT is not just a more elaborate closed-manifold invariant. It is the right language for boundary conditions.

A boundary condition for a TQFT can often be understood as a module object over the bulk theory. An interface between two TQFTs is a bimodule-like object. A junction between interfaces is a morphism between such objects.

This matches the folding trick. An interface between theories $T_1$ and $T_2$ can be folded into a boundary condition for

$$
T_1\otimes T_2^{\mathrm{op}}.
$$

Extended TQFT makes this systematic. It assigns algebraic data to the interface itself and to the local operators that can live where interfaces meet.

This is the bridge to categorical symmetry. Once topological defects are treated as objects and junctions as morphisms, fusion and associativity become categorical structure, not optional notation.

## Extended TQFT and SymTFT

Symmetry TFT is almost never just a closed-manifold partition function. Its purpose is to encode symmetry operators, charged objects, background choices, gauging, defects, and boundary conditions. All of those require extended data.

For example, a SymTFT bulk defect may end on a topological boundary, producing a boundary symmetry operator. Two bulk defects may fuse before ending. Junctions of bulk defects become local relations among symmetry operators. A different topological boundary corresponds to gauging or changing the global form.

This is exactly extended-TQFT behavior:

$$
\text{bulk defects}
\quad\leftrightarrow\quad
\text{objects/morphisms in an extended topological theory}.
$$

Thus extended TQFT is not a separate abstract chapter detached from physics. It is the mathematical grammar behind many modern statements about generalized symmetry and non-invertible symmetry.

## The cobordism hypothesis in plain language

The cobordism hypothesis is often summarized too cryptically. Here is the physics-friendly version.

A fully extended TQFT must know how to evaluate every possible local patch of spacetime. But every manifold can be assembled from local pieces, and topological invariance says the answer cannot depend on the arbitrary details of the assembly. Therefore the entire theory should be determined by the data assigned to the smallest possible piece: a point.

However, not every object can be assigned to a point. The object must support all the operations corresponding to cups, caps, rotations, and higher-dimensional adjunctions. This is the fully dualizable condition.

So the slogan

$$
Z\longmapsto Z(\mathrm{pt})
$$

is not saying that TQFT is trivial. It is saying that all topology is generated locally, and fully dualizable point-data is exactly the algebraic structure needed to make every gluing consistent.

## What this page is not doing

This page does not define $(\infty,n)$-categories, prove the cobordism hypothesis, classify fully dualizable objects, or construct extended Chern–Simons theory rigorously. It also does not settle the analytic difficulties of continuum path integrals.

Its goal is to make modern physics language intelligible:

```txt
extended TQFT
fully local theory
point value
fully dualizable object
defect category
boundary module
junction morphism
SymTFT extended data
```

If those phrases no longer sound like mysterious incantations after this page, it has done its job.

## Common pitfalls

**“Extended” means higher-dimensional.”** No. A $d$-dimensional extended TQFT is still $d$-dimensional. “Extended” means it assigns data to lower-dimensional pieces inside that $d$-dimensional theory.

**“The point value is just a number.”** In a fully extended theory, the point value is often a rich algebraic object: an algebra, category, higher category object, or fully dualizable object in a target.

**“Ordinary TQFT already includes all defects.”** Ordinary Atiyah–Segal TQFT sees codimension-one cuts well. Defects, junctions, and point-like local data require extended structure.

**“The cobordism hypothesis is a computational shortcut.”** It is a structural classification theorem, not a replacement for calculating partition functions or constructing field theories.

**“All physical TQFTs are fully extended.”** Many physically defined TQFTs are known only partially, or require extra structures, anomalies, framings, spin structures, or boundary choices. Fully extended construction can be difficult.

## Relations to other pages

[What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/) introduces the ordinary functorial picture. [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) and [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) provide examples where extended data become concrete through Wilson lines, defects, and finite gauge sectors.

[Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) supplies the physical operator vocabulary. [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) uses categories and defect fusion. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) uses extended topological data to encode symmetry, gauging, boundary conditions, and anomaly inflow.

## Research status

The ordinary Atiyah–Segal definition of TQFT is established. The extended viewpoint is also standard in modern mathematical physics, with the cobordism hypothesis giving the organizing classification principle for fully extended framed theories.

Active work includes extended TQFTs with tangential structures, defects and singular strata, nonsemisimple and derived targets, factorization homology, extended SymTFTs, non-invertible symmetry, condensed-matter topological orders, and the precise continuum construction of physically motivated examples.

## Exercises

### Exercise 1: Ordinary TQFT gluing

Let $M_1:\Sigma_0\to\Sigma_1$ and $M_2:\Sigma_1\to\Sigma_2$ be bordisms. What does the TQFT gluing axiom say?

<details><summary><strong>Solution</strong></summary>

The glued bordism is

$$
M_2\circ M_1:\Sigma_0\to\Sigma_2.
$$

The TQFT assigns linear maps

$$
Z(M_1):Z(\Sigma_0)\to Z(\Sigma_1),
\qquad
Z(M_2):Z(\Sigma_1)\to Z(\Sigma_2).
$$

The gluing axiom says

$$
Z(M_2\circ M_1)=Z(M_2)\circ Z(M_1).
$$

Thus geometric gluing becomes composition of linear maps.

</details>

### Exercise 2: Why intervals require more than vector spaces

In a two-dimensional extended TQFT, why might assigning only vector spaces to circles fail to describe boundary conditions on intervals?

<details><summary><strong>Solution</strong></summary>

A circle is a closed one-dimensional manifold. An interval has boundary points. To describe an interval, the theory must know what data live at endpoints and how boundary conditions compose along intervals. Vector spaces assigned only to closed circles do not contain this endpoint information. Extended TQFT assigns lower-dimensional data, such as algebras, modules, or objects, so intervals and their endpoints can be treated functorially.

</details>

### Exercise 3: Duals from cups and caps

Explain why a TQFT assigning an object $X$ to a point should require a dual object $X^\vee$.

<details><summary><strong>Solution</strong></summary>

In a bordism category, a cup can create a pair of points and a cap can annihilate a pair of points. Algebraically, these correspond to coevaluation and evaluation maps,

$$
\mathbf 1\to X\otimes X^\vee,
\qquad
X^\vee\otimes X\to \mathbf 1.
$$

Thus the point value must have a dual if the TQFT is to assign consistent algebraic data to these elementary bordisms.

</details>

### Exercise 4: Symmetry defects as extended data

Why does a topological line defect in a three-dimensional TQFT suggest extended, rather than only ordinary, TQFT structure?

<details><summary><strong>Solution</strong></summary>

A line defect is supported on a one-dimensional submanifold, which is codimension two in a three-dimensional theory. Ordinary TQFT assigns data mainly to closed two-manifolds and three-dimensional bordisms. To describe line defects, their endpoints, and their junctions, the theory must assign data to lower-dimensional strata. This is precisely the role of extended TQFT.

</details>

## References

- M. Atiyah, “Topological Quantum Field Theories,” *Publications Mathématiques de l’IHÉS* **68** (1988). The classic functorial definition.
- G. Segal, “The Definition of Conformal Field Theory,” for the related functorial viewpoint in conformal field theory.
- J. Baez and J. Dolan, “Higher-Dimensional Algebra and Topological Quantum Field Theory,” for the higher-categorical and cobordism-hypothesis program.
- D. Freed, “Extended Structures in Topological Quantum Field Theory,” for an early physics-facing view of extended structure.
- J. Lurie, “On the Classification of Topological Field Theories,” for the cobordism-hypothesis framework.
- D. Freed and C. Teleman, “Relative Quantum Field Theory,” for relative theories and modern TQFT perspective.
- D. Ayala and J. Francis, “The Cobordism Hypothesis,” for a modern mathematical treatment.

## Version history

- **2026-06-23:** Initial polished preview. Added ordinary-versus-extended comparison, point-value intuition, fully dualizable objects, examples, boundary/defect links, and SymTFT motivation.
