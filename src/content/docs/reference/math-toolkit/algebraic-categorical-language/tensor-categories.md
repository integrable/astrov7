---
title: "Tensor Categories"
description: "A QFT-oriented introduction to tensor categories: monoidal products, units, associators, coherence, duals, braiding, string diagrams, tensor functors, and examples from representations, defects, and topological lines."
sidebar:
  label: "Tensor Categories"
  order: 6
level: Research
status: "Polished draft"
source: "Standard references on category theory, tensor categories, representation theory, rational conformal field theory, topological field theory, and QFT, including Mac Lane, Etingof–Gelaki–Nikshych–Ostrik, Bakalov–Kirillov, Turaev, Kassel, Fuchs–Runkel–Schweigert, Douglas–Schommer-Pries–Snyder, Di Francesco–Mathieu–Sénéchal, Gaiotto–Kapustin–Seiberg–Willett, Nakahara, Frankel, Weinberg, Srednicki, Schwartz, and modern references on topological defects and generalized symmetries."
topics:
  - tensor category
  - monoidal category
  - associator
  - coherence
  - unit object
  - tensor functor
  - rigid category
  - dual object
  - braiding
  - string diagram
  - representation category
  - topological line
canonicalTopics:
  - tensor-category
  - monoidal-category
  - associator
  - coherence
  - unit-object
  - tensor-functor
  - rigid-category
  - dual-object
  - braiding
  - string-diagram
  - representation-category
  - topological-line
researchStatus:
  established:
    - "Monoidal and tensor categories are standard mathematical structures for objects that can be composed, tensored, dualized, and represented by coherent diagrams."
    - "Representation categories, categories of vector spaces, super vector spaces, and categories of topological lines or defects are basic examples relevant to QFT."
  active:
    - "The categorical organization of extended operators, non-invertible symmetries, higher categories, factorization structures, and non-semisimple QFT sectors remains an active research area."
---

## Summary

A **tensor category** is a category whose objects can be multiplied by a tensor product.

More precisely, the basic data are a category $\mathcal C$, a bifunctor

$$
\otimes:\mathcal C\times\mathcal C\to\mathcal C,
$$

a unit object $\mathbf 1$, and coherent isomorphisms saying that tensoring is associative and unital up to controlled equivalence:

$$
\alpha_{X,Y,Z}:(X\otimes Y)\otimes Z\xrightarrow{\sim}X\otimes(Y\otimes Z),
$$

$$
\lambda_X:\mathbf 1\otimes X\xrightarrow{\sim}X,
\qquad
\rho_X:X\otimes\mathbf 1\xrightarrow{\sim}X.
$$

Many QFT structures have this shape. Charges can be combined. Representations can be tensored. Wilson lines and topological defects can be fused. Boundary conditions and interfaces can be composed. Superselection sectors can have duals. In favorable dimensions, defects can also be braided.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Diagram showing a tensor category as a category with objects and morphisms, a tensor product, associator, unit object, coherence, duals, optional braiding, and QFT applications such as representations, topological lines, charges, sectors, and junctions.](/figures/math-toolkit/tensor-category-structure-flow.svg)

<figcaption>

A tensor category turns “objects that can be combined” into precise data: a tensor product, a unit, associators, coherence laws, and often linearity, duals, or braiding. In QFT, the objects may be representations, sectors, line operators, defects, or boundary conditions; the morphisms are intertwiners, junctions, maps of sectors, or local operators at endpoints.

</figcaption>
</figure>

The main conceptual shift is this: a tensor category is not just a multiplication table. It remembers **how** objects multiply, **how morphisms multiply**, and **how all possible parenthesizations agree**.

:::note[Core slogan]
A tensor category is the algebraic home for objects that can be tensored. It is what replaces a group when the things being “multiplied” have internal morphisms, direct sums, duals, and nontrivial associativity data.
:::

## Prerequisites and conventions

You should know [Algebras and Modules](/math-toolkit/algebraic-categorical-language/algebras-and-modules/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), and [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/). Helpful nearby pages include [Graded Algebras](/math-toolkit/algebraic-categorical-language/graded-algebras/), [Chain Complexes](/math-toolkit/algebraic-categorical-language/chain-complexes/), [Cohomology](/math-toolkit/algebraic-categorical-language/cohomology/), and [Fusion Categories](/math-toolkit/algebraic-categorical-language/fusion-categories/).

This page uses ordinary category-theory notation. Objects are written $X,Y,Z\in\mathcal C$. Morphism spaces are written

$$
\operatorname{Hom}_{\mathcal C}(X,Y).
$$

Composition is written right-to-left:

$$
X\xrightarrow{f}Y\xrightarrow{g}Z
\qquad\leadsto\qquad
 g\circ f:X\to Z.
$$

The word “tensor category” is used in a broad QFT-friendly sense: a monoidal category, often with extra linear, additive, abelian, rigid, semisimple, braided, pivotal, spherical, or unitary structure when the application needs it. Some authors reserve “tensor category” for a $k$-linear abelian rigid monoidal category satisfying finiteness conditions. Always check the local convention.

## Categories in one paragraph

A category $\mathcal C$ consists of objects, morphisms between objects, identity morphisms, and associative composition. For each object $X$ there is an identity

$$
\operatorname{id}_X:X\to X.
$$

For morphisms

$$
X\xrightarrow{f}Y\xrightarrow{g}Z\xrightarrow{h}W,
$$

composition is associative:

$$
h\circ(g\circ f)=(h\circ g)\circ f.
$$

This is deliberately minimal. A category is not necessarily a set of vector spaces, not necessarily a set of groups, and not necessarily a space. It is a bookkeeping device for objects and maps. The power comes from choosing the right objects and maps.

In QFT, useful categories include:

| Category | Objects | Morphisms |
|---|---|---|
| $\operatorname{Vect}_k$ | vector spaces over $k$ | linear maps |
| $\operatorname{Hilb}$ | Hilbert spaces | bounded linear maps, or sometimes unitary maps |
| $\operatorname{Rep}(G)$ | representations of a group $G$ | $G$-equivariant linear maps |
| $\operatorname{Rep}(\mathfrak g)$ | Lie-algebra representations | intertwiners |
| super vector spaces | $\mathbb Z_2$-graded vector spaces | parity-preserving linear maps |
| line-defect category | topological line operators | local junction operators |
| boundary-condition category | boundary conditions | boundary-changing operators or interfaces |

The tensor product is extra structure on top of this category.

## The tensor product as a bifunctor

A tensor product in a category is a functor

$$
\otimes:\mathcal C\times\mathcal C\to\mathcal C.
$$

This means it acts on objects,

$$
(X,Y)\mapsto X\otimes Y,
$$

and on morphisms,

$$
(f:X\to X',\,g:Y\to Y')
\mapsto
f\otimes g:X\otimes Y\to X'\otimes Y'.
$$

Functoriality says

$$
(\operatorname{id}_X\otimes\operatorname{id}_Y)
=
\operatorname{id}_{X\otimes Y},
$$

and, whenever the compositions are defined,

$$
(f_2\circ f_1)\otimes(g_2\circ g_1)
=
(f_2\otimes g_2)\circ(f_1\otimes g_1).
$$

This equation is one of the quiet reasons tensor categories are useful in physics. If two junction operators are composed and two independent line operators are fused, it should not matter whether we first compose the junctions and then fuse, or first fuse and then compose. The bifunctor law is the abstract version of that compatibility.

## Associators and why parentheses matter

In ordinary linear algebra, one often writes

$$
(U\otimes V)\otimes W=U\otimes(V\otimes W)
$$

as if the two vector spaces were literally the same. They are canonically isomorphic, not literally equal. In a general tensor category, that isomorphism is part of the data:

$$
\alpha_{X,Y,Z}:(X\otimes Y)\otimes Z\to X\otimes(Y\otimes Z).
$$

The associator tells us how to change parentheses. This is harmless-looking, but in fusion categories the matrix elements of $\alpha$ become $F$-symbols, and those can encode physically measurable data of anyons or topological lines.

A tensor category is called **strict** if

$$
(X\otimes Y)\otimes Z=X\otimes(Y\otimes Z)
$$

and the unit constraints are identities. Mac Lane coherence says that, up to monoidal equivalence, every monoidal category can be strictified. That theorem is wonderful, but it is not a license to delete associators from physics. Strictification changes presentation; it does not say the $F$-symbol data of a chosen basis is meaningless.

A good practical rule is:

$$
\text{erase parentheses for easy notation, but remember that an associator made it legal.}
$$

## Coherence laws

The associator cannot be arbitrary. If four objects are tensored, there are several ways to rebracket them. Coherence requires all legal rebracketings between the same endpoints to agree.

One standard form of the pentagon identity is

$$
\alpha_{X,Y,Z\otimes W}\circ\alpha_{X\otimes Y,Z,W}
=
(\operatorname{id}_X\otimes\alpha_{Y,Z,W})
\circ\alpha_{X,Y\otimes Z,W}
\circ(\alpha_{X,Y,Z}\otimes\operatorname{id}_W).
$$

Both sides are maps

$$
((X\otimes Y)\otimes Z)\otimes W
\to
X\otimes(Y\otimes(Z\otimes W)).
$$

Similarly, the unit object $\mathbf 1$ comes with left and right unit constraints

$$
\lambda_X:\mathbf 1\otimes X\to X,
\qquad
\rho_X:X\otimes\mathbf 1\to X.
$$

The triangle identity says that inserting and then removing the unit is compatible with rebracketing:

$$
(\operatorname{id}_X\otimes\lambda_Y)\circ\alpha_{X,\mathbf 1,Y}
=
\rho_X\otimes\operatorname{id}_Y.
$$

Coherence laws are not decorative bureaucracy. They are what make string diagrams and fusion computations independent of arbitrary parenthesization choices. Without coherence, “the tensor product of four things” would not be a well-defined operation even up to canonical isomorphism.

## Linear, additive, and abelian tensor categories

QFT rarely uses bare categories. It usually uses categories enriched by vector-space structure.

A category is **$k$-linear** if each morphism set is a vector space over $k$ and composition is bilinear:

$$
\operatorname{Hom}_{\mathcal C}(X,Y)
\quad\text{is a }k\text{-vector space}.
$$

A $k$-linear tensor category also has tensor product bilinear on morphisms. This is natural when morphisms are intertwiners, local operators, junction fields, or amplitudes.

An **additive** category has finite direct sums. In such a category one can form

$$
X\oplus Y.
$$

In a semisimple additive category, objects decompose as finite direct sums of simple objects. This is the setting where statements like

$$
X_a\otimes X_b\simeq\bigoplus_c N_{ab}^{\;c}X_c
$$

make sense. The integers $N_{ab}^{\;c}$ are fusion multiplicities, and the next page develops that case.

An **abelian** category has kernels, cokernels, exact sequences, images, and cohomology-like algebra. Categories of representations of many familiar algebraic objects are abelian. Abelian structure matters whenever one studies subobjects, quotients, exact functors, derived functors, or extensions.

## Representation categories as the basic example

Let $G$ be a group. The category $\operatorname{Rep}_k(G)$ has finite-dimensional $k$-linear representations as objects and $G$-equivariant maps as morphisms.

If $V$ and $W$ are representations, then their tensor product is again a representation with diagonal action:

$$
g\cdot(v\otimes w)=(g\cdot v)\otimes(g\cdot w).
$$

The unit object is the trivial representation $k$. The associator and unit maps are inherited from vector spaces.

This category remembers more than the list of irreducible representations. It remembers morphisms, tensor products, duals, direct sums, and the way tensor products decompose. In particle physics language, it knows how multiplets combine and how invariant couplings are built. In QFT language, it is a clean algebraic model for ordinary finite or compact internal symmetry sectors.

For a Lie algebra $\mathfrak g$, the category $\operatorname{Rep}(\mathfrak g)$ is similarly monoidal: the action on $V\otimes W$ is

$$
X\cdot(v\otimes w)=(X\cdot v)\otimes w+v\otimes(X\cdot w),
\qquad X\in\mathfrak g.
$$

This is the infinitesimal version of the diagonal group action.

## Super vector spaces and the sign lesson

Super vector spaces form a tensor category whose objects are $\mathbb Z_2$-graded vector spaces

$$
V=V^{\bar0}\oplus V^{\bar1}.
$$

The tensor product is graded by

$$
(V\otimes W)^{\bar0}
=
(V^{\bar0}\otimes W^{\bar0})\oplus(V^{\bar1}\otimes W^{\bar1}),
$$

$$
(V\otimes W)^{\bar1}
=
(V^{\bar0}\otimes W^{\bar1})\oplus(V^{\bar1}\otimes W^{\bar0}).
$$

There is a symmetric braiding, but it is not the naive flip. For homogeneous elements,

$$
\tau(v\otimes w)=(-1)^{|v||w|}w\otimes v.
$$

This is the categorical origin of the Koszul sign rule. It is the same sign principle that appears in fermions, ghosts, Grassmann variables, BRST complexes, differential forms, and graded commutators. Whenever a QFT calculation says “move one odd thing past another,” it is using this tensor category in the background.

## Duals and rigidity

A tensor category is **rigid** if every object has a left and right dual. For an object $X$, a right dual $X^\vee$ comes with evaluation and coevaluation morphisms

$$
\operatorname{ev}_X:X^\vee\otimes X\to\mathbf 1,
\qquad
\operatorname{coev}_X:\mathbf 1\to X\otimes X^\vee,
$$

satisfying zigzag identities. Suppressing associators and unit constraints, one identity is

$$
(\operatorname{id}_X\otimes\operatorname{ev}_X)
\circ
(\operatorname{coev}_X\otimes\operatorname{id}_X)
=
\operatorname{id}_X.
$$

The other is

$$
(\operatorname{ev}_X\otimes\operatorname{id}_{X^\vee})
\circ
(\operatorname{id}_{X^\vee}\otimes\operatorname{coev}_X)
=
\operatorname{id}_{X^\vee}.
$$

In vector spaces, $X^\vee$ is the dual vector space. In representation theory, $X^\vee$ is the dual representation. In a line-operator category, $X^\vee$ is often the oppositely oriented line. Evaluation and coevaluation are endpoint or pair-creation maps. In particle language, duality often resembles charge conjugation; in defect language, it resembles reversing orientation.

Rigid categories are the natural setting for string diagrams with cups and caps. They also allow categorical traces and dimensions once extra pivotal or spherical structure is available.

## Braiding and symmetry are not the same word

A **braiding** on a tensor category is a natural isomorphism

$$
c_{X,Y}:X\otimes Y\to Y\otimes X
$$

compatible with the associator through the hexagon identities. The braiding says one can exchange two tensor factors coherently.

A braiding is **symmetric** if

$$
c_{Y,X}\circ c_{X,Y}=\operatorname{id}_{X\otimes Y}.
$$

Vector spaces have the symmetric flip

$$
v\otimes w\mapsto w\otimes v.
$$

Super vector spaces have the symmetric Koszul flip. Anyonic systems in $2+1$ dimensions usually have braidings that are not symmetric. In that case, exchanging $X$ and $Y$ and then exchanging back need not be the identity; it can produce a nontrivial monodromy.

This distinction matters in QFT. Ordinary global symmetries often lead to symmetric representation categories. Topological line operators in two-dimensional QFT may form fusion categories that are not automatically braided. Anyons in three-dimensional topological phases require braided, often modular, tensor categories. Braiding is extra data, not a synonym for tensoring.

## String diagrams

Tensor categories are often easier to compute with using diagrams.

The translation dictionary is:

| Algebraic notation | Diagrammatic idea |
|---|---|
| object $X$ | labeled wire |
| morphism $f:X\to Y$ | box or vertex with input $X$ and output $Y$ |
| composition $g\circ f$ | vertical stacking |
| tensor product $f\otimes g$ | horizontal juxtaposition |
| unit object $\mathbf 1$ | empty line or no wire |
| evaluation | cap |
| coevaluation | cup |
| braiding $c_{X,Y}$ | crossing of two wires |

String diagrams are not informal doodles. Under suitable coherence assumptions, isotopic diagrams represent the same morphism. That is why graphical calculi are so effective for angular momentum recoupling, spin networks, anyon fusion, tensor networks, and topological field theory.

The phrase “under suitable assumptions” is doing work. Plain monoidal categories allow planar string diagrams with parentheses controlled by associators. Rigid categories allow cups and caps. Braided categories allow crossings. Ribbon or pivotal categories allow traces and twists with better isotopy properties. One should not draw a move unless the category has the structure that makes the move legal.

## Tensor functors

A functor between tensor categories should preserve tensor products, but again usually up to specified isomorphism rather than equality.

A monoidal functor

$$
F:\mathcal C\to\mathcal D
$$

comes with natural maps

$$
F(X)\otimes F(Y)\to F(X\otimes Y),
$$

and a unit map

$$
\mathbf 1_{\mathcal D}\to F(\mathbf 1_{\mathcal C}),
$$

or the reversed directions depending on whether one uses lax, oplax, or strong monoidal conventions. If these maps are isomorphisms, the functor is strong monoidal.

In QFT, tensor functors appear when one changes description while preserving fusion-like structure. Examples include:

| Physics operation | Categorical shadow |
|---|---|
| restrict a representation from $G$ to a subgroup $H$ | tensor functor $\operatorname{Rep}(G)\to\operatorname{Rep}(H)$ |
| forget symmetry action | forgetful tensor functor $\operatorname{Rep}(G)\to\operatorname{Vect}$ |
| map bulk lines to boundary operators | monoidal or module functor, depending on setup |
| topological interface between phases | functor or bimodule category between line categories |
| RG flow preserving topological sectors | functorial map on surviving defect data |

The moral is that equivalence of tensor categories is stronger than equivalence of underlying categories. It must respect tensor product and coherence data.

## QFT interpretations

Tensor categories show up in several increasingly structured ways.

### Ordinary symmetry representations

If a theory has an internal symmetry group $G$, its charged sectors often organize into representations. Tensor product describes combining charges. Invariant couplings are morphisms

$$
\mathbf 1\to V_1\otimes\cdots\otimes V_n
$$

or, equivalently, $G$-equivariant maps

$$
V_1\otimes\cdots\otimes V_n\to\mathbf 1.
$$

This is a categorical way to phrase selection rules and tensor-product decompositions.

### Topological line operators

Suppose a QFT has topological line operators. If two parallel lines are brought together, their product is another line or a sum of lines. This product is tensor-like:

$$
L_a\otimes L_b.
$$

Local operators at junctions between lines are morphisms. Fusion of junctions is composition. Parallel placement of junctions is tensor product of morphisms. Associativity says fusing three nearby lines does not depend on the arbitrary order of bringing them together, except through the associator.

This is why tensor categories are the natural language for non-invertible symmetries. A group is the special case where every simple object is invertible and morphisms are trivial enough that only multiplication remains.

### Defects and boundary conditions

Defects of different codimensions often form higher-categorical structures. This page only treats ordinary tensor categories, but the intuition generalizes. Objects may be boundary conditions, morphisms may be line defects between them, and 2-morphisms may be local operators at junctions. In a fully extended TQFT, this becomes higher category theory.

For much of QFT, however, ordinary tensor categories already explain a great deal: sectors, fusion, duals, junctions, selection rules, and topological invariance.

## What data is not visible in the fusion ring

If a tensor category is semisimple with simple objects $X_a$, one can record fusion multiplicities

$$
X_a\otimes X_b\simeq\bigoplus_c N_{ab}^{\;c}X_c.
$$

The numbers $N_{ab}^{\;c}$ define a fusion ring, also called the Grothendieck ring. This ring is useful, but it is not the whole category.

The category also contains:

- morphism spaces;
- associator isomorphisms;
- unit constraints;
- duality maps;
- possible braiding, twist, pivotal, or spherical structure;
- choices of equivalence and gauge transformations of bases;
- module categories, defects, and boundary data in applications.

Two tensor categories can have the same fusion rules and different associators. In physics language, the same charge-combination table may support different topological theories. The multiplication table is the skeleton; the category is the living animal. Weird animal. Useful animal.

## Worked example: representations of SU(2)

Finite-dimensional representations of $SU(2)$ form a tensor category. Simple objects are labeled by spin

$$
j=0,\frac12,1,\frac32,\ldots.
$$

The tensor product decomposes as

$$
V_{j_1}\otimes V_{j_2}
\simeq
\bigoplus_{j=|j_1-j_2|}^{j_1+j_2}V_j,
$$

where $j$ increases in integer steps. For example,

$$
V_{1/2}\otimes V_{1/2}\simeq V_0\oplus V_1.
$$

The associator is inherited from vector spaces, but if one chooses Clebsch–Gordan bases for fusion channels, changes of parenthesization are described by recoupling coefficients, namely $6j$ symbols. This is the representation-theory ancestor of the $F$-symbols used in fusion categories and anyon models.

So even in a familiar representation category, the categorical message is already present:

$$
\text{decomposition rules} + \text{basis choices} + \text{associativity}
\quad\leadsto\quad
\text{recoupling coefficients}.
$$

## Common pitfalls

### Pitfall 1: Treating tensor product as literal equality

The expression

$$
(X\otimes Y)\otimes Z=X\otimes(Y\otimes Z)
$$

is usually shorthand for a specified isomorphism. In a tensor category, the associator is part of the data. Suppressing it is fine only after one understands what is being suppressed.

### Pitfall 2: Thinking objects must be vector spaces

Objects in a tensor category can be vector spaces, representations, modules, sectors, defects, lines, boundary conditions, or abstract simple labels. The tensor product may be ordinary vector-space tensor product, fusion of defects, composition of interfaces, or something else.

### Pitfall 3: Confusing braiding with symmetry

A tensor category need not be braided. A braided tensor category need not be symmetric. A symmetric tensor category is a special case. Anyonic braiding is precisely interesting because exchanging twice can be nontrivial.

### Pitfall 4: Believing fusion rules determine the theory

Fusion multiplicities $N_{ab}^{\;c}$ do not determine the full tensor category. Associators, duals, braidings, twists, and gauge-equivalence data matter.

### Pitfall 5: Ignoring morphisms

The morphisms are not decoration. They represent intertwiners, junctions, local operators, or maps between sectors. A category with the right objects and wrong morphisms is the wrong category.

## Exercises

### Exercise 1: Tensor product of group representations

Let $V$ and $W$ be representations of a group $G$. Define

$$
g\cdot(v\otimes w)=(g\cdot v)\otimes(g\cdot w).
$$

Show that this defines a representation of $G$ on $V\otimes W$.

<details><summary><strong>Solution</strong></summary>

We must check the identity and multiplication laws. For the identity element $e\in G$,

$$
e\cdot(v\otimes w)=(e\cdot v)\otimes(e\cdot w)=v\otimes w.
$$

For $g,h\in G$,

$$
(gh)\cdot(v\otimes w)=((gh)\cdot v)\otimes((gh)\cdot w).
$$

Since $V$ and $W$ are representations,

$$
(gh)\cdot v=g\cdot(h\cdot v),
\qquad
(gh)\cdot w=g\cdot(h\cdot w).
$$

Thus

$$
(gh)\cdot(v\otimes w)
=(g\cdot(h\cdot v))\otimes(g\cdot(h\cdot w))
=g\cdot\bigl((h\cdot v)\otimes(h\cdot w)\bigr).
$$

Therefore

$$
(gh)\cdot(v\otimes w)=g\cdot\bigl(h\cdot(v\otimes w)\bigr),
$$

so the diagonal action is a representation.

</details>

### Exercise 2: The Koszul sign

Let $V$ and $W$ be super vector spaces. Suppose $v\in V$ and $w\in W$ are homogeneous of parities $|v|$ and $|w|$. The super braiding is

$$
\tau(v\otimes w)=(-1)^{|v||w|}w\otimes v.
$$

Show that $\tau_{W,V}\circ\tau_{V,W}=\operatorname{id}_{V\otimes W}$.

<details><summary><strong>Solution</strong></summary>

Apply the braiding twice:

$$
\tau_{V,W}(v\otimes w)=(-1)^{|v||w|}w\otimes v.
$$

Now apply $\tau_{W,V}$:

$$
\tau_{W,V}(w\otimes v)=(-1)^{|w||v|}v\otimes w.
$$

Therefore

$$
(\tau_{W,V}\circ\tau_{V,W})(v\otimes w)
=(-1)^{|v||w|}(-1)^{|w||v|}v\otimes w.
$$

Since $|v||w|=|w||v|$ modulo $2$,

$$
(-1)^{|v||w|}(-1)^{|w||v|}=(-1)^{2|v||w|}=1.
$$

Hence the double braiding is the identity. Super vector spaces are symmetric braided, but with a nontrivial sign in the symmetry.

</details>

### Exercise 3: Evaluation and coevaluation for vector spaces

Let $V$ be a finite-dimensional vector space with basis $e_i$ and dual basis $e^i$. Define

$$
\operatorname{ev}:V^*\otimes V\to k,
\qquad
\operatorname{ev}(\varphi\otimes v)=\varphi(v),
$$

and

$$
\operatorname{coev}:k\to V\otimes V^*,
\qquad
\operatorname{coev}(1)=\sum_i e_i\otimes e^i.
$$

Check one zigzag identity on a vector $v\in V$.

<details><summary><strong>Solution</strong></summary>

Suppressing associators, the relevant composite is

$$
V\xrightarrow{\operatorname{coev}\otimes\operatorname{id}_V}
V\otimes V^*\otimes V
\xrightarrow{\operatorname{id}_V\otimes\operatorname{ev}}
V.
$$

Applied to $v$, it gives

$$
v\mapsto \sum_i e_i\otimes e^i\otimes v
\mapsto \sum_i e_i\,e^i(v).
$$

Because $e_i,e^i$ are dual bases,

$$
\sum_i e_i\,e^i(v)=v.
$$

Thus the composite is $\operatorname{id}_V$.

</details>

### Exercise 4: Intertwiners as morphisms

Let $V,W$ be representations of a group $G$. A linear map $T:V\to W$ is an intertwiner if

$$
T(g\cdot v)=g\cdot T(v)
$$

for all $g\in G$ and $v\in V$. Show that if $S:W\to U$ is another intertwiner, then $S\circ T:V\to U$ is an intertwiner.

<details><summary><strong>Solution</strong></summary>

For all $g\in G$ and $v\in V$,

$$
(S\circ T)(g\cdot v)=S(T(g\cdot v)).
$$

Since $T$ is an intertwiner,

$$
T(g\cdot v)=g\cdot T(v).
$$

Then, since $S$ is an intertwiner,

$$
S(g\cdot T(v))=g\cdot S(T(v)).
$$

Therefore

$$
(S\circ T)(g\cdot v)=g\cdot(S\circ T)(v),
$$

so $S\circ T$ is an intertwiner. This is why representations and intertwiners form a category.

</details>

## Further reading

For the foundations of category theory and monoidal categories, see Mac Lane. For tensor categories and fusion categories, see Etingof, Gelaki, Nikshych, and Ostrik; Bakalov and Kirillov; Turaev; and Kassel. For applications to rational conformal field theory and topological phases, see Di Francesco, Mathieu, and Sénéchal; Fuchs, Runkel, and Schweigert; and standard references on topological quantum field theory. For geometric and physical background on bundles, defects, and field theory, see Nakahara, Frankel, Weinberg, Srednicki, Schwartz, and modern references on generalized symmetries and topological defects.

## Version history

- 2026-06-26: Initial polished draft. Introduced tensor categories, bifunctorial tensor products, associators, coherence, linear/additive structure, representation categories, super vector spaces, rigidity, duals, braiding, string diagrams, tensor functors, QFT interpretations, pitfalls, and exercises.
