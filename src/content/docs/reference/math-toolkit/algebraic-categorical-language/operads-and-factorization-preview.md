---
title: 'Operads and Factorization Preview'
description: 'A QFT-oriented preview of operads, little disks, E_n algebras, factorization algebras, and their relation to OPEs and local observables.'
sidebar:
  label: 'Operads and Factorization Preview'
  order: 9
level: Advanced
status: "Polished draft"
source: 'Modern mathematical QFT, operadic algebra, factorization algebras, perturbative AQFT, and OPE-inspired local-to-global structures.'
topics:
  - operads
  - factorization algebras
  - E_n algebras
  - local observables
  - operator product expansion
  - chiral algebras
canonicalTopics:
  - operads
  - factorization-algebras
  - little-disks-operad
  - local-observables
  - qft-algebraic-structures
researchStatus:
  established:
    - 'Operads encode families of compatible multilinear operations; little-disk operads govern E_n algebra structures on local observables in n-dimensional topological or locally constant theories.'
    - 'Factorization algebras provide a local-to-global formalism for observables, making precise the idea that observables supported in disjoint regions multiply inside a larger region.'
  active:
    - 'The use of factorization methods for general non-topological QFTs, boundary defects, higher categories, renormalization, and nonperturbative reconstruction remains a lively research frontier.'
---

## Summary

Operads are bookkeeping devices for operations with many inputs and one output. Factorization algebras are local-to-global devices for observables in QFT. Together they turn a familiar physical intuition into precise mathematics:

> Observables supported in separated regions can be multiplied, and as the regions collide the product develops structured singularities.

This is the algebraic skeleton behind the operator product expansion, chiral algebras, topological local operators, locally constant field theories, and perturbative constructions of QFT observables.

The page is a preview. The goal is not to teach the full technology, but to make the vocabulary recognizable and useful before it appears in CFT, topological field theory, categorical symmetries, and modern mathematical QFT.

:::note[The slogan]
An operad describes **allowed shapes of operations**. A factorization algebra describes **observables assigned to regions**, together with compatible multiplication maps whenever those regions are disjoint.
:::

## Prerequisites

You should know basic linear algebra, tensor products, associative algebras, and the physical idea of local operators. Category-theory comfort helps, but the page introduces only the minimum needed language.

The closest nearby page is [Modular Tensor Categories](/math-toolkit/algebraic-categorical-language/modular-tensor-categories/), which describes a different but complementary categorical package: fusion and braiding of topological sectors. Operads and factorization algebras are more about **local operations and observables**.

## Why QFT cares

Ordinary algebra is too rigid for QFT. A QFT does not merely have one product. It has products depending on spacetime configuration:

$$
\mathcal O_1(x_1)\mathcal O_2(x_2)\cdots \mathcal O_n(x_n),
$$

which are well behaved when the points are separated and singular when they collide. The structure depends on the geometry of configurations, not just the list of operators.

That is why operads and factorization algebras are natural:

| QFT phenomenon | Algebraic structure |
|---|---|
| Time-ordered products | operations indexed by ordered or stratified configurations |
| OPEs | local factorization as insertion points collide |
| Topological local operators | $E_n$ algebras in $n$ dimensions |
| Chiral CFT | factorization or vertex-algebra structures on a complex curve |
| Perturbative observables | factorization algebras built by renormalized local products |
| Defects and boundaries | colored or stratified versions of operads and factorization algebras |

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flowchart from local regions and little disks to factorization products, OPE limits, and QFT observables.](/figures/math-toolkit/operads-factorization-flow.svg)

<figcaption>

Operads encode the shapes of allowed multi-input operations. Factorization algebras assign observables to regions and multiply observables from disjoint subregions inside a larger region. In QFT, collision limits of these products become OPE data.

</figcaption>
</figure>

## Operads in one paragraph

An operad $\mathcal O$ is a collection of spaces or sets

$$
\mathcal O(n),\qquad n=0,1,2,\ldots,
$$

where an element of $\mathcal O(n)$ represents an abstract operation with $n$ inputs and one output. Operads come with composition maps

$$
\mathcal O(n)\times \mathcal O(k_1)\times\cdots\times\mathcal O(k_n)
\longrightarrow
\mathcal O(k_1+\cdots+k_n),
$$

plus an identity operation and symmetric-group actions when input labels may be permuted.

The composition law says that if you know how to perform an $n$-input operation and then plug $k_i$-input operations into its inputs, you get a single operation with $k_1+\cdots+k_n$ inputs. Operads are algebra for “substitution of operations.”

An algebra over an operad $\mathcal O$ is a vector space, chain complex, category, or other object $A$ on which every operation in $\mathcal O(n)$ acts by an $n$-linear map

$$
A^{\otimes n}\longrightarrow A,
$$

compatible with operadic composition.

## Familiar operads hiding in plain sight

The associative operad encodes associative multiplication. An algebra over it is an associative algebra:

$$
(a b)c=a(b c).
$$

The commutative operad encodes commutative associative multiplication:

$$
ab=ba.
$$

The Lie operad encodes Lie brackets:

$$
[x,y]=-[y,x],
$$

and

$$
[x,[y,z]]+[y,[z,x]]+[z,[x,y]]=0.
$$

The point is not that these examples are exotic. The point is that associative, commutative, and Lie algebra structures are all instances of the same template: specify allowed operations and their relations.

## The little disks operad

The little $n$-disks operad $E_n$ is the operad whose $k$-ary operations are configurations of $k$ disjoint embedded disks inside a unit $n$-disk. Composition is insertion of disks into disks.

An algebra over $E_n$ is called an $E_n$ algebra. The low-dimensional cases are worth memorizing:

| Structure | Rough meaning |
|---|---|
| $E_1$ algebra | associative up to coherent homotopy |
| $E_2$ algebra | braided or commutative up to two-dimensional motion |
| $E_\infty$ algebra | commutative up to all coherent homotopies |

For QFT in $n$ Euclidean dimensions, $E_n$ appears because local insertions can move around each other in $n$-dimensional space. If a theory is topological or locally constant, correlation functions depend only on configuration topology, so the little-disk operad acts on local observables.

## Topological local operators as Eₙ algebras

In an $n$-dimensional topological field theory, local operators can be placed in small $n$-balls. If several such balls sit disjointly inside a larger ball, their insertions define a product operation.

This gives maps

$$
\mathcal O(B_1)\otimes\cdots\otimes\mathcal O(B_k)
\longrightarrow
\mathcal O(B),
$$

where $B_1,\ldots,B_k\subset B$ are disjoint balls. Moving the balls gives homotopies between operations. Therefore the local operators form an $E_n$ algebra.

This explains a famous dimension-dependent pattern:

- In one dimension, local operators multiply associatively.
- In two dimensions, exchanging points can produce braided structure.
- In three or more dimensions, local topological operators become increasingly close to commutative, though line and surface operators can still have nontrivial higher braiding.

## Factorization algebras

A factorization algebra $\mathcal F$ assigns data to each open region $U$ in a spacetime manifold $M$:

$$
U\longmapsto \mathcal F(U),
$$

where $\mathcal F(U)$ is interpreted as observables supported in $U$. If $U_1,\ldots,U_k$ are pairwise disjoint open subsets of $V$, there is a structure map

$$
\mathcal F(U_1)\otimes\cdots\otimes\mathcal F(U_k)
\longrightarrow
\mathcal F(V).
$$

These maps must be compatible with refinement of regions. If you multiply observables in small regions and then include them in a larger region, the result should not depend on the arbitrary intermediate cover.

This is very close to how physicists think about locality. The observable algebra of a large region is assembled from observables in smaller regions, and separated observables can be multiplied.

## Cosheaf flavor

A sheaf glues compatible local data by restriction maps from large regions to small regions. A factorization algebra has a cosheaf-like direction: observables supported in small regions push forward into larger regions.

The direction is physically sensible. An observable supported in $U$ is automatically an observable supported in any larger region $V\supset U$:

$$
\mathcal F(U)\longrightarrow\mathcal F(V).
$$

Factorization adds a multilinear version for several disjoint subregions:

$$
\mathcal F(U_1)\otimes\mathcal F(U_2)
\longrightarrow\mathcal F(V),
\qquad U_1\cap U_2=\varnothing.
$$

The disjointness condition is not cosmetic. In QFT, products of observables at coincident support are singular and need renormalization. Factorization begins where naive multiplication is safe.

## OPE as collision limit

For local operators in an ordinary QFT, separated products make sense as distributions:

$$
\mathcal O_i(x)\mathcal O_j(y),
\qquad x\ne y.
$$

As $x\to y$, the product has an asymptotic expansion

$$
\mathcal O_i(x)\mathcal O_j(y)
\sim
\sum_k C_{ij}^{\phantom{ij}k}(x-y)\mathcal O_k(y).
$$

Factorization algebras isolate the local-to-global product structure before taking collision limits. In favorable settings, the OPE is the singular boundary behavior of factorization products on configuration spaces.

This is one reason the language is useful in CFT: conformal symmetry constrains the coefficient distributions $C_{ij}^{\phantom{ij}k}$, while factorization explains the coherence of repeated OPEs.

## Locally constant factorization algebras and Eₙ

A factorization algebra on $\mathbb R^n$ is locally constant if inclusions of disks that are isotopy equivalences induce quasi-isomorphisms. In that case the factorization algebra is essentially the same data as an $E_n$ algebra.

The slogan is:

$$
\text{locally constant factorization algebra on }\mathbb R^n
\quad\leftrightarrow\quad
E_n\text{ algebra}.
$$

This equivalence is one of the main conceptual bridges between topology and QFT. It says that topological local observables can be studied either as observables assigned to regions or as algebras over the little-disks operad.

## Chiral theories and vertex algebras

In two-dimensional chiral CFT, local holomorphic fields have singular products

$$
A(z)B(w)\sim \sum_{m\ge 0}\frac{(A_{(m)}B)(w)}{(z-w)^{m+1}}+\text{regular terms}.
$$

Vertex algebras are one algebraic way to package these singular products. Factorization algebras and factorization spaces provide a geometric way to view the same phenomenon: products are defined for distinct points and have controlled singularities along diagonals.

A useful dictionary is:

| Chiral CFT language | Factorization language |
|---|---|
| field insertion at $z$ | observable supported near $z$ |
| OPE singularity | behavior near configuration-space diagonal |
| normal ordering | renormalized extension to coincident support |
| Ward identities | compatibility with symmetry and descent |
| conformal blocks | global sections or coinvariants of local data |

## Perturbative QFT viewpoint

In perturbative algebraic QFT and related approaches, one constructs observables as complexes of local functionals, then defines products using propagators and renormalization. Singularities appear when supports collide, exactly where factorization has to be treated carefully.

The factorization-algebra viewpoint is useful because it separates three issues:

1. **Locality:** observables are assigned to open sets.
2. **Multiplication:** disjoint observables multiply inside larger regions.
3. **Renormalization:** coincident limits require extensions across diagonals.

That separation prevents a common conceptual mess: the product of separated observables is not the same problem as defining a composite operator at one point.

## Factorization homology

Given an $E_n$ algebra $A$ and an $n$-manifold $M$, factorization homology produces an invariant often denoted

$$
\int_M A.
$$

The notation is intentional. It behaves like “integrating local algebraic data over a manifold.” For topological theories, it is a way to compute global observables or state spaces from local $E_n$ data.

Examples to keep in mind:

- For $E_1$ algebras, factorization homology over $S^1$ recovers Hochschild-type invariants.
- For higher $E_n$ algebras, it generalizes this circle construction to higher-dimensional manifolds.
- In extended TQFT, it is part of the mechanism by which local algebraic input produces global topological invariants.

## Colored and stratified versions

Real QFTs contain more than bulk local operators. They have boundaries, interfaces, line defects, surface defects, and junctions. These require **colored** or **stratified** versions of operads and factorization algebras.

A color records the type of input or output. For example, in a boundary QFT one may have:

| Color | Physical meaning |
|---|---|
| bulk | local operators in the interior |
| boundary | operators on the boundary |
| defect | operators living on a specified defect |
| junction | operators where defects meet |

The structure maps must respect which configurations are geometrically allowed. A bulk operator may approach a boundary and expand into boundary operators. Two line defects may meet at a junction. A categorical symmetry line may end on a charged local operator only when the theory permits such an endpoint.

This is where the technology gets powerful, and also where it gets technical fast.

## What this preview does not cover

This page does not build the formal model category machinery behind operads, nor does it prove the equivalence between locally constant factorization algebras and $E_n$ algebras. It also does not define derived stacks of fields, BV quantization, or renormalization in the Costello–Gwilliam framework.

For QFT use, the important first step is recognizing the shape of the idea: local observables form a structure richer than one algebra, because spacetime configurations themselves label the operations.

## Common pitfalls

**Pitfall 1: thinking an operad is just a category.** Operads are built to encode multi-input operations. Categories encode one-input composable arrows. They are related but not interchangeable.

**Pitfall 2: replacing factorization by ordinary multiplication.** Factorization products are naturally defined for disjoint supports. Coincident products require renormalization or OPE expansions.

**Pitfall 3: saying Eₙ means commutative.** $E_n$ algebras become more commutative as $n$ grows, but $E_1$, $E_2$, and $E_\infty$ carry genuinely different coherence data.

**Pitfall 4: forgetting geometry.** The whole point is that operations are indexed by configurations of points, disks, or regions in spacetime. Removing the geometry removes the physics.

**Pitfall 5: assuming the topological story covers all QFTs.** Locally constant factorization algebras model topological or protected sectors. General QFTs have metric dependence, singularities, and analytic constraints.

## Exercises

### Exercise 1: Associativity from operadic composition

Let $\mathcal O$ be the associative operad with one binary multiplication operation $m$ and relations identifying $m\circ_1 m$ with $m\circ_2 m$. Show that an algebra over $\mathcal O$ has associative multiplication.

<details><summary><strong>Solution</strong></summary>

An algebra over $\mathcal O$ assigns to $m\in\mathcal O(2)$ a bilinear map

$$
\mu:A\otimes A\to A.
$$

The composite $m\circ_1 m$ corresponds to first multiplying the first two inputs and then multiplying with the third:

$$
\mu(\mu(a,b),c).
$$

The composite $m\circ_2 m$ corresponds to first multiplying the last two inputs:

$$
\mu(a,\mu(b,c)).
$$

The operadic relation $m\circ_1 m=m\circ_2 m$ therefore becomes

$$
\mu(\mu(a,b),c)=\mu(a,\mu(b,c)),
$$

which is associativity.

</details>

### Exercise 2: Why disjointness matters

Explain why a factorization product

$$
\mathcal F(U_1)\otimes\mathcal F(U_2)\to\mathcal F(V)
$$

is naturally required only when $U_1$ and $U_2$ are disjoint.

<details><summary><strong>Solution</strong></summary>

If $U_1$ and $U_2$ are disjoint, observables supported in those regions are separated. Their product is physically meaningful without forcing two insertions to occupy the same point or overlapping support.

If the supports overlap, one is trying to multiply local distributions at coincident points. In QFT this is generally singular. Defining such a product requires extra choices: normal ordering, counterterms, point splitting, an OPE prescription, or another renormalization scheme.

Thus factorization starts with the safe product of separated observables and studies coincident limits as additional structure.

</details>

### Exercise 3: Local constancy and topological dependence

Suppose a factorization algebra on $\mathbb R^n$ assigns quasi-isomorphic observables to any two disks related by inclusion. Why should this be interpreted as topological rather than metric dependence?

<details><summary><strong>Solution</strong></summary>

If every inclusion of disks that preserves the local topology induces a quasi-isomorphism, then changing the size or precise shape of a disk does not change the observable data up to homotopy. The observables depend on the disk as a small neighborhood, not on its metric radius or detailed geometry.

The operations are then controlled by configurations of disks up to deformation. Those configurations form the little-disks operad, so the local observables carry an $E_n$ algebra structure. This is the algebraic signature of a topological or locally constant sector.

</details>

## References

- Boardman and Vogt, *Homotopy Invariant Algebraic Structures on Topological Spaces*.
- May, *The Geometry of Iterated Loop Spaces*.
- Lurie, *Higher Algebra*.
- Costello and Gwilliam, *Factorization Algebras in Quantum Field Theory*.
- Beilinson and Drinfeld, *Chiral Algebras*.
- Francis, “Factorization homology of topological manifolds.”
- Ayala and Francis, “Factorization homology of stratified spaces.”

## Version history

- **2026-06-27:** First polished preview. Introduces operads, little disks, $E_n$ algebras, factorization algebras, OPE interpretation, locally constant theories, chiral examples, and common pitfalls.