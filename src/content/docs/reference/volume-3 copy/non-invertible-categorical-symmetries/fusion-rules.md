---
title: "Fusion Rules"
description: "Explains fusion rules for topological defects, including identity defects, adjoints, associativity, quantum dimensions, junctions, and non-invertible examples."
sidebar:
  label: "Fusion Rules"
  order: 3
level: Advanced
status: "Polished draft"
source: "Shao TASI lectures; Schäfer-Nameki ICTP lectures; standard fusion-category, rational CFT, and topological-defect references."
topics:
  - fusion rules
  - topological defects
  - non-invertible symmetry
  - quantum dimension
  - junctions
  - associativity
canonicalTopics:
  - defect-fusion-rule
  - fusion-coefficient
  - quantum-dimension
  - defect-junction
  - categorical-symmetry
researchStatus:
  established:
    - "Fusion rules are the first algebraic layer of topological defect symmetry: invertible symmetries give group-like fusion, while non-invertible defects can fuse into sums of defects."
    - "In two-dimensional rational CFT and many topological theories, semisimple fusion rules with nonnegative integer coefficients are a standard and powerful organizing language."
  active:
    - "Higher-dimensional, non-semisimple, fermionic, anomalous, and symmetry-TFT settings require richer categorical or higher-categorical data beyond the simple fusion-rule table."
---

## Summary

Fusion rules are the multiplication table of topological defects. If $\mathcal D_a$ and $\mathcal D_b$ are compatible topological defects, bringing them together gives another topological object. In simple semisimple situations one writes

$$
\mathcal D_a\times\mathcal D_b
=
\bigoplus_c N_{ab}{}^c\,\mathcal D_c.
$$

The coefficients $N_{ab}{}^c$ are fusion multiplicities. For ordinary invertible symmetry defects they reproduce a group law:

$$
U_g\times U_h=U_{gh}.
$$

For non-invertible defects they can produce sums:

$$
\mathcal N\times\mathcal N=1+\eta.
$$

Fusion rules are not just notation. They tell us which defects are invertible, how duality defects behave, which junctions can exist, how defect networks simplify, what quantum dimensions are possible, and why non-invertible symmetry is not a group in disguise.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A schematic fusion table comparing group-like fusion with non-invertible fusion into multiple channels.](/figures/symmetry-anomalies-topology/noninvertible-fusion-rules.svg)

<figcaption>

Fusion rules are the multiplication table of topological defects. Group-like defects fuse to a single defect with an inverse. Non-invertible defects can fuse into a direct sum of channels, such as $\mathcal N^2=1+\eta$.

</figcaption>
</figure>

This page explains how to read fusion rules before introducing full categorical language.

## Prerequisites

You should know [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/) and [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/). You should also be comfortable with direct sums of vector spaces and the idea that tensor products of representations decompose into irreducible pieces.

This page uses a simplified semisimple language: defects are labeled by symbols $\mathcal D_a$, fusion coefficients are nonnegative integers, and direct sums behave like formal sums of superselection sectors. Later pages explain where this simplification breaks down.

## Core idea

Topological defects can be moved. If two such defects are parallel and close, their separation is not a physical scale. We can shrink the strip between them and replace the pair by an effective defect:

$$
\mathcal D_a\quad\mathcal D_b
\quad\leadsto\quad
\mathcal D_a\times\mathcal D_b.
$$

For ordinary symmetry defects, this is just group multiplication. For example, if $\eta$ generates a $\mathbb Z_2$ symmetry,

$$
\eta\times\eta=1.
$$

For non-invertible defects, fusion can have several channels. The notation

$$
\mathcal D_a\times\mathcal D_b
=
\mathcal D_c+\mathcal D_d
$$

means that the composite defect decomposes as a direct sum of topological sectors. It does **not** mean a random choice, a probability mixture, or a failure of determinism. It means the defect Hilbert space or category contains multiple superselection channels.

The algebraic form of the fusion rule is the first hint of category theory. The full category remembers not only which channels appear, but also the junction spaces and associativity maps among them.

## Setup and conventions

Let $1$ denote the transparent identity defect. A finite set of simple topological defects is denoted

$$
\{\mathcal D_a\}_{a\in I}.
$$

A simple defect is one that cannot be decomposed further as a nontrivial direct sum. In the semisimple setting, every finite direct sum decomposes into simple defects.

Fusion is written

$$
\mathcal D_a\times\mathcal D_b
=
\bigoplus_{c\in I} N_{ab}{}^c\,\mathcal D_c,
$$

where

$$
N_{ab}{}^c\in\mathbb Z_{\ge0}.
$$

The identity defect satisfies

$$
1\times\mathcal D_a=\mathcal D_a,
\qquad
\mathcal D_a\times 1=\mathcal D_a.
$$

A defect $\mathcal D_a$ is **invertible** if there is a defect $\mathcal D_b$ such that

$$
\mathcal D_a\times\mathcal D_b=1,
\qquad
\mathcal D_b\times\mathcal D_a=1.
$$

Otherwise it is non-invertible.

:::note[Semisimple caveat]
The notation $\bigoplus_c N_{ab}{}^c\mathcal D_c$ is the cleanest first language, but it is not the final word. Non-semisimple theories, logarithmic CFTs, higher-dimensional defects, fermionic defects, and anomalous settings may require categories, higher categories, module categories, or nontrivial extension data rather than a simple integer fusion table.
:::

## Reading a fusion rule

Consider

$$
\mathcal N\times\mathcal N=1+\eta,
\qquad
\eta\times\eta=1,
\qquad
\eta\times\mathcal N=\mathcal N.
$$

This compact algebra says several things.

First, $\eta$ is invertible because $\eta^2=1$.

Second, $\mathcal N$ is not invertible because $\mathcal N^2$ is not a single identity defect. It is a direct sum of two channels.

Third, fusing $\eta$ with $\mathcal N$ leaves $\mathcal N$ unchanged. This means $\mathcal N$ is neutral under the $\mathbb Z_2$ action generated by $\eta$, or more precisely that $\eta$ can be absorbed into $\mathcal N$ under fusion.

Fourth, the algebra already implies a nontrivial quantum dimension. If $d_a$ denotes the quantum dimension of $\mathcal D_a$, then

$$
d_a d_b=\sum_c N_{ab}{}^c d_c.
$$

With $d_1=d_\eta=1$, the rule $\mathcal N^2=1+\eta$ gives

$$
d_{\mathcal N}^2=2,
\qquad
d_{\mathcal N}=\sqrt2.
$$

Since invertible simple defects have quantum dimension $1$, this diagnoses non-invertibility.

## Identity, adjoint, and inverse

The identity defect $1$ is the unit of fusion. It is transparent: crossing it changes nothing.

The **adjoint** defect $\mathcal D^\dagger$ is the orientation-reversed or Hermitian-conjugate defect. It is the natural partner that appears when one reverses a defect line, surface, or wall. In unitary examples, adjoints behave much like dual representations.

But adjoint does not mean inverse. A defect can obey

$$
\mathcal D\times\mathcal D^\dagger
=
1+\mathcal E
$$

for some extra nontrivial defect $\mathcal E$. In that case $\mathcal D^\dagger$ is not an inverse. It is a dual or adjoint object, not a group inverse.

A useful diagnostic is:

| Equation | Interpretation |
|---|---|
| $\mathcal D\times\mathcal D^{-1}=1$ | $\mathcal D$ is invertible. |
| $\mathcal D\times\mathcal D^\dagger=1+\cdots$ | $\mathcal D^\dagger$ is adjoint, not inverse. |
| $\mathcal D\times\mathcal D=1+\eta$ | $\mathcal D$ is non-invertible in a semisimple setting. |

This distinction is one of the main conceptual speed bumps for students entering non-invertible symmetry.

## Associativity

Fusion must be associative, at least up to canonical equivalence. If three defects are fused, it should not matter physically which pair we fuse first:

$$
(\mathcal D_a\times\mathcal D_b)\times\mathcal D_c
\simeq
\mathcal D_a\times(\mathcal D_b\times\mathcal D_c).
$$

At the level of fusion coefficients, this implies

$$
\sum_e N_{ab}{}^e N_{ec}{}^f
=
\sum_e N_{ae}{}^f N_{bc}{}^e.
$$

This equation is necessary but not sufficient for full consistency. The actual equivalence between the two fusion orderings is implemented by associator maps, often called $F$-symbols in two-dimensional topological or rational CFT settings. These maps must obey a pentagon identity.

For a first pass, remember:

$$
\text{fusion coefficients are the multiplication table;}
\qquad
\text{associators say multiplication is consistently associative}.
$$

:::note[Source note]
A fusion rule table can pass simple associativity checks while still failing to define a consistent defect category unless the required associators, unit maps, and positivity/unitarity data exist. This is why category language eventually becomes unavoidable.
:::

## Fusion matrices

For each defect $\mathcal D_a$, define a fusion matrix $N_a$ by

$$
(N_a)_b{}^c=N_{ab}{}^c.
$$

Then fusion by $\mathcal D_a$ acts on the vector space spanned by defect labels:

$$
\mathcal D_b\mapsto \mathcal D_a\times\mathcal D_b.
$$

The fusion algebra becomes matrix multiplication:

$$
N_a N_b=\sum_c N_{ab}{}^c N_c.
$$

The largest positive eigenvalue of $N_a$ is the quantum dimension $d_a$ in unitary semisimple examples. The vector of quantum dimensions satisfies

$$
d_a d_b=\sum_c N_{ab}{}^c d_c.
$$

For a group-like symmetry, all fusion matrices are permutation matrices and all quantum dimensions are $1$. Non-invertible defects have fusion matrices that are not simply permutations and often have $d_a>1$.

## Quantum dimension

Quantum dimension is a measure of the “size” of a defect. It is not usually the dimension of an ordinary vector space, though in simple finite examples it behaves similarly under fusion.

The defining relation is

$$
d_a d_b=\sum_c N_{ab}{}^c d_c,
$$

with

$$
d_1=1.
$$

For invertible defects,

$$
\mathcal D_a\times\mathcal D_a^{-1}=1
$$

implies

$$
d_a d_{a^{-1}}=1.
$$

In unitary settings dimensions are positive, so $d_a=1$.

For the Ising-like non-invertible rule,

$$
\mathcal N^2=1+\eta,
$$

one gets

$$
d_{\mathcal N}=\sqrt2.
$$

Quantum dimension often controls asymptotic growth of defect Hilbert spaces, normalization of defect networks, and the relative weight of topological sectors. It is a quick way to see that a defect is not group-like.

## Fusion and crossing

Fusion rules do not only simplify parallel defects. They constrain how defects cross operators and other defects.

Suppose a local operator $\mathcal O$ lies between two defects. If one fuses those defects, the action on $\mathcal O$ must agree with the action of the fused defect. For group-like defects this says

$$
g\cdot(h\cdot \mathcal O)=(gh)\cdot\mathcal O.
$$

For non-invertible defects, the corresponding statement can involve a sum over channels:

$$
\mathcal D_a\cdot(\mathcal D_b\cdot\mathcal O)
=
\bigoplus_c N_{ab}{}^c(\mathcal D_c\cdot\mathcal O),
$$

schematically. The precise meaning may require defect endpoints and junction operators. This is the seed of non-invertible Ward identities.

Fusion is therefore not only a property of isolated defects. It governs the consistency of their action on the whole QFT.

## Junctions and multiplicities

The coefficient $N_{ab}{}^c$ can be interpreted as the dimension of the space of topological junctions from $\mathcal D_a\times\mathcal D_b$ to $\mathcal D_c$:

$$
N_{ab}{}^c
=
\dim \operatorname{Hom}(\mathcal D_a\times\mathcal D_b,\mathcal D_c)
$$

in a simple categorical model.

This interpretation explains why $N_{ab}{}^c$ is a nonnegative integer in semisimple finite settings. It counts independent topological ways for two defects to meet and become a third.

If $N_{ab}{}^c>1$, there are multiple independent junction channels. Then the fusion rule alone is not enough; one must also track the junction label. Diagrams with trivalent junctions, associators, and defect-local operators become part of the data.

For many introductory examples, multiplicities are $0$ or $1$. But multiplicities greater than one are common enough that the notation should be learned early.

## Braiding and commutativity

Fusion need not be commutative. In two-dimensional Euclidean QFT, codimension-one defects are lines, and their parallel fusion is often ordered. In three-dimensional topological theories, line operators can braid, and the braiding data is extra information beyond fusion.

One may have

$$
\mathcal D_a\times\mathcal D_b
\not\simeq
\mathcal D_b\times\mathcal D_a.
$$

Even when the labels commute, the process of moving defects around each other can produce nontrivial braiding phases or matrices. This is familiar from anyons: the fusion rules tell us which charge channels can result, while the braiding tells us what happens when worldlines wind around each other.

For codimension-one symmetry defects in a relativistic QFT, the relevant braiding-like data depends strongly on dimension. This is one reason higher-dimensional categorical symmetry is subtler than the two-dimensional examples.

## Examples

### Finite group defects

For an ordinary finite symmetry group $G$,

$$
U_g\times U_h=U_{gh}.
$$

The fusion coefficients are

$$
N_{gh}{}^k=
\begin{cases}
1,& k=gh,\\
0,& k\ne gh.
\end{cases}
$$

Every simple defect is invertible and has quantum dimension $1$. The fusion matrices are permutation matrices.

This is the special case where the defect algebra is just the group algebra of symmetry surfaces.

### Ising-like fusion

The simplest non-invertible fusion algebra has defects

$$
1,\qquad \eta,\qquad \mathcal N,
$$

with

$$
\eta^2=1,
\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,
\qquad
\mathcal N^2=1+\eta.
$$

This is the canonical fusion pattern of the Kramers–Wannier duality line in the two-dimensional Ising model. Its quantum dimensions are

$$
d_1=d_\eta=1,\qquad d_{\mathcal N}=\sqrt2.
$$

The defect $\eta$ is invertible; $\mathcal N$ is not.

### Fibonacci-type fusion

Another famous fusion rule is

$$
\tau\times\tau=1+\tau.
$$

The quantum dimension obeys

$$
d_\tau^2=1+d_\tau,
$$

so

$$
d_\tau=\frac{1+\sqrt5}{2}.
$$

This is the golden ratio. Fibonacci-type fusion appears in topological phases and TQFT examples. It is useful pedagogically because it makes clear that non-invertible fusion is not limited to $\sqrt2$-type duality defects.

### Representation-category example

If $G$ is a finite group, the irreducible representations of $G$ obey tensor-product fusion:

$$
R_a\otimes R_b
=
\bigoplus_c N_{ab}{}^c R_c.
$$

This is not the same as the group-like defect fusion $U_gU_h=U_{gh}$, but it is a useful algebraic analogy. Tensor products of irreducible representations generally decompose into sums. This is why fusion categories feel like a natural generalization of representation theory.

In many two-dimensional constructions, symmetry defects and topological lines can indeed be organized by categories closely related to representation categories, module categories, or categories of bimodules.

## Fusion rules and gauging

Non-invertible defects often arise from gauging operations. Gauging a finite symmetry is not invertible as an operation on local data: it projects to invariant sectors and sums over twisted sectors. At special self-dual points, the interface associated with such a gauging can become a non-invertible topological defect.

This intuition explains why fusion into sums is natural. A gauging operation remembers several sectors at once. Fusing a gauging defect with itself may therefore produce a sum over invertible symmetry defects.

Schematic examples often take the form

$$
\mathcal N^\dagger\times\mathcal N
=
\sum_{g\in G} U_g.
$$

This says that doing a gauging-like operation and its adjoint gives a projector-like sum over group defects, not the identity alone. Hence $\mathcal N$ is non-invertible unless $G$ is trivial.

## Fusion rules versus anomalies

Fusion rules say how defects multiply. Anomalies say whether the full symmetry structure can be consistently coupled to backgrounds, gauged, or realized on a trivially gapped boundary.

These are related but distinct. A set of fusion rules can be non-invertible without being anomalous. Conversely, an invertible group-like symmetry can have an anomaly. In modern language, the anomaly may be encoded by a bulk symmetry TFT whose boundary defects have the given fusion behavior.

When comparing sources, keep the layers separate:

| Layer | Data |
|---|---|
| Fusion | Which defect channels appear in products. |
| Junctions | Spaces of local operators where defects meet. |
| Associators | How different fusion orders are identified. |
| Braiding | How defects move around one another, when meaningful. |
| Anomaly | Obstruction to gauging or to certain symmetric boundaries. |

The fusion table is the beginning, not the end.

## How to check a proposed fusion rule

A proposed fusion rule should pass several tests.

First, it should have an identity:

$$
1\times\mathcal D_a=\mathcal D_a.
$$

Second, it should be associative at the level of coefficients:

$$
\sum_e N_{ab}{}^eN_{ec}{}^f
=
\sum_e N_{ae}{}^fN_{bc}{}^e.
$$

Third, it should admit positive quantum dimensions in a unitary semisimple setting:

$$
d_a d_b=\sum_c N_{ab}{}^c d_c,
\qquad d_a>0.
$$

Fourth, it should be compatible with adjoints. In a unitary setting, the identity should appear in

$$
\mathcal D_a\times\mathcal D_a^\dagger
$$

with multiplicity one for a simple defect.

Fifth, it should admit consistent associators and junction data. This last check cannot be read off from the multiplication table alone.

## Common pitfalls

**Reading $1+\eta$ as probability.** It is a direct sum of topological channels, not a random outcome.

**Thinking fusion coefficients are amplitudes.** In the simplest setting they are nonnegative integer multiplicities. Amplitudes enter when one evaluates networks with chosen junctions and normalizations.

**Equating adjoint with inverse.** The adjoint of a non-invertible defect is generally not an inverse.

**Ignoring associativity data.** Fusion coefficients are necessary but not sufficient. The associator maps and their consistency conditions are part of the full structure.

**Assuming fusion is commutative.** Defect fusion can be ordered, braided, or higher-categorical depending on dimension and codimension.

**Calling every algebra a symmetry.** A fusion rule becomes symmetry data only when realized by topological defects acting consistently on a QFT.

## Relations to other pages

[Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/) explains why topological defects deserve to be called symmetry data. [Duality Defects](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/duality-defects/) will explain how duality interfaces often produce non-invertible fusion. [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/) will develop the Ising example in detail.

The later [Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/) page explains how fusion coefficients, junctions, associators, and defect-local operators fit into category language. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) will reinterpret fusion rules as data of topological boundary conditions and bulk defects.

## Research status

Fusion rules for topological defects are standard in two-dimensional CFT, rational CFT, topological phases, and TQFT. They are also the standard first language for non-invertible symmetries.

The active frontier is the generalization. In higher-dimensional QFT, defects can form higher categories. In non-semisimple theories, direct-sum decompositions can fail or require extensions. In fermionic theories, spin structures and signs enter. In anomalous settings, fusion may only be fully consistent together with a bulk symmetry TFT. For a physics reader, the right attitude is: learn the semisimple fusion table first, then remember that it is a shadow of richer data.

## Exercises

### Exercise 1: Associativity check for Ising-like fusion

Consider defects $1$, $\eta$, and $\mathcal N$ with

$$
\eta^2=1,\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,\qquad
\mathcal N^2=1+\eta.
$$

Check associativity for $(\mathcal N\mathcal N)\mathcal N$ and $\mathcal N(\mathcal N\mathcal N)$.

<details><summary><strong>Solution</strong></summary>

Compute the left side:

$$
(\mathcal N\mathcal N)\mathcal N=(1+\eta)\mathcal N
=\mathcal N+\eta\mathcal N
=\mathcal N+\mathcal N
=2\mathcal N.
$$

Compute the right side:

$$
\mathcal N(\mathcal N\mathcal N)=\mathcal N(1+\eta)
=\mathcal N+\mathcal N\eta
=\mathcal N+\mathcal N
=2\mathcal N.
$$

The two agree at the level of fusion coefficients.

</details>

### Exercise 2: Quantum dimension of Fibonacci fusion

Let $\tau$ obey

$$
\tau^2=1+\tau.
$$

Find $d_\tau$ assuming $d_\tau>0$ and $d_1=1$.

<details><summary><strong>Solution</strong></summary>

Quantum dimensions obey the same fusion equation:

$$
d_\tau^2=1+d_\tau.
$$

Thus

$$
d_\tau^2-d_\tau-1=0.
$$

The positive solution is

$$
d_\tau=\frac{1+\sqrt5}{2}.
$$

</details>

### Exercise 3: Invertible defects have dimension one

Assume a unitary semisimple fusion rule with positive quantum dimensions. Show that an invertible defect has quantum dimension $1$.

<details><summary><strong>Solution</strong></summary>

If $\mathcal D$ is invertible, there is $\mathcal D^{-1}$ with

$$
\mathcal D\times\mathcal D^{-1}=1.
$$

Taking quantum dimensions gives

$$
d_{\mathcal D}d_{\mathcal D^{-1}}=1.
$$

Similarly, $\mathcal D^{-1}$ is also invertible. In a unitary fusion setting simple invertible objects have positive dimensions and their adjoints have the same dimension, so

$$
d_{\mathcal D}=d_{\mathcal D^{-1}}.
$$

Therefore

$$
d_{\mathcal D}^2=1,
$$

and positivity gives

$$
d_{\mathcal D}=1.
$$

</details>

### Exercise 4: Direct sum versus probability

Explain why the rule

$$
\mathcal N^2=1+\eta
$$

should not be interpreted as “with probability one half the result is $1$ and with probability one half the result is $\eta$.”

<details><summary><strong>Solution</strong></summary>

The plus sign denotes a direct sum of topological sectors or fusion channels. It is an algebraic decomposition, like the decomposition of a tensor product of representations into irreducible representations. It is not a stochastic process. To compute numbers, one must specify a network, junction operators, normalizations, and a correlation function. The fusion rule only says which topological channels are present.

</details>

## References

- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries,” for a physics-first introduction to fusion rules and duality defects.
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” for modern conventions and the symmetry-TFT perspective.
- P. Etingof, D. Nikshych, V. Ostrik, and collaborators, for mathematical background on fusion categories.
- J. Fuchs, I. Runkel, and C. Schweigert, for topological defects and fusion in rational CFT.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for two-dimensional CFT examples and fusion rules.
- A. Kitaev, and related work on anyons and topological phases, for the topological-order side of fusion rules.

## Version history

- **2026-06-20:** Initial polished draft. Added semisimple fusion-rule notation, identity/adjoint/inverse distinction, associativity, fusion matrices, quantum dimension, examples, checks, pitfalls, and exercises.
