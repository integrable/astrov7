---
title: "Invertible Versus Non-Invertible Symmetry"
description: "Explains the basic distinction between group-like invertible symmetries and non-invertible symmetries whose topological defects fuse into sums of sectors."
sidebar:
  label: "Invertible Versus Non-Invertible"
  order: 1
level: Research
status: "Polished draft"
source: "Shao TASI lectures; Schäfer-Nameki ICTP lectures; Gaiotto–Kapustin–Seiberg–Willett; Ising/Kramers–Wannier defect literature."
topics:
  - invertible symmetry
  - non-invertible symmetry
  - topological defects
  - fusion rules
  - categorical symmetry
  - duality defects
canonicalTopics:
  - invertible-symmetry
  - non-invertible-symmetry
  - topological-defect-fusion
  - categorical-symmetry
  - duality-defect
researchStatus:
  established:
    - "Invertible topological symmetry defects reproduce ordinary group-like symmetries, including ordinary global symmetries and invertible higher-form symmetries."
    - "Two-dimensional QFT and CFT provide canonical, explicit, and well-tested examples of non-invertible topological defects."
  active:
    - "Higher-dimensional non-invertible symmetries, their generalized charges, anomalies, gauging operations, and symmetry-TFT descriptions are active research topics."
---

## Summary

An **invertible symmetry** is one whose topological symmetry defect can be undone. If $U_g$ is the defect for $g$, then there is another defect $U_{g^{-1}}$ such that

$$
U_gU_{g^{-1}}=1.
$$

This is the topological-defect version of ordinary group symmetry.

A **non-invertible symmetry** is different. It is still topological. It still constrains correlation functions. It may still be exact. But a symmetry defect $\mathcal N$ need not have an inverse. Its fusion with another defect may produce a sum:

$$
\mathcal N_a\mathcal N_b
=
\sum_c N_{ab}{}^c\,\mathcal N_c.
$$

That one equation is the conceptual earthquake. The right-hand side is not a single group element. It is a direct sum of possible topological sectors.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A comparison of invertible group-like fusion with non-invertible fusion into a sum of defects.](/figures/symmetry-anomalies-topology/invertible-vs-noninvertible-fusion.svg)

<figcaption>

Invertible symmetry defects fuse like group elements: there is a unique product and an inverse. Non-invertible defects can fuse into sums of defects. The symmetry is still topological, but it is no longer described by a group action.

</figcaption>
</figure>

The slogan is:

$$
\text{invertible symmetry} = \text{topological group action},
\qquad
\text{non-invertible symmetry} = \text{topological fusion action}.
$$

## Prerequisites

You should know the topological-operator view of ordinary symmetry, the basic idea of defect fusion, and the higher-form convention that symmetries can act on extended operators. The essential earlier pages are [Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/), [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), and [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/).

No category theory is assumed. This page uses “category” only as a name for the bookkeeping that becomes unavoidable once defects can be added, fused, and related by defect-local operators.

## Core idea

The modern definition of symmetry starts with topological defects. For an ordinary internal symmetry group $G$, every group element $g\in G$ gives a codimension-one topological operator $U_g(\Sigma)$. It can be deformed freely unless it crosses charged insertions.

The fusion law is group multiplication:

$$
U_g(\Sigma)U_h(\Sigma)=U_{gh}(\Sigma).
$$

The identity is $U_e=1$, and every defect has an inverse:

$$
U_g(\Sigma)U_{g^{-1}}(\Sigma)=1.
$$

This invertibility means the symmetry action can be undone. If $U_g$ crosses an operator and transforms it, $U_{g^{-1}}$ crosses back and restores it.

Non-invertible symmetry keeps the topological-defect part but drops the group part. The defects still form a closed algebra under fusion, but the product can be a sum:

$$
\mathcal N_a\mathcal N_b
=
\mathcal N_c\oplus\mathcal N_d
$$

or more generally

$$
\mathcal N_a\mathcal N_b
=
\sum_c N_{ab}{}^c\mathcal N_c.
$$

There may be no defect $\mathcal N_a^{-1}$ satisfying $\mathcal N_a\mathcal N_a^{-1}=1$. That is non-invertibility.

## Setup and conventions

A topological defect is written $\mathcal D(\Sigma)$, where $\Sigma$ is its support. When the support is clear, we suppress it and write simply $\mathcal D$.

Fusion means bringing two parallel compatible defects together and replacing the pair by the resulting effective topological defect:

$$
\mathcal D_a\otimes\mathcal D_b.
$$

In this page, we often omit the tensor symbol and write $\mathcal D_a\mathcal D_b$.

We use a semisimple shorthand when writing

$$
\mathcal D_a\mathcal D_b=\sum_cN_{ab}{}^c\mathcal D_c,
$$

where $N_{ab}{}^c$ are nonnegative integers in common finite semisimple examples. This notation assumes we have chosen a basis of simple defects and that direct sums of defects make sense.

:::note[Source note]
The compact formula with coefficients $N_{ab}{}^c$ is the cleanest entry point, but it hides real assumptions: semisimplicity, a choice of simple objects, and a normalization of defect operators. More general QFTs can require nonsemisimple, higher-categorical, or continuum generalizations.
:::

The identity defect is denoted by $1$. It is the invisible defect:

$$
1\mathcal D=\mathcal D1=\mathcal D.
$$

The orientation reversal or dual of a defect is denoted by $\mathcal D^\vee$ when needed. For an invertible group-like defect, $\mathcal D^\vee$ is its inverse. For a non-invertible defect, the dual usually exists but is not an inverse in the group sense.

## Invertible topological defects

A topological defect $\mathcal D$ is invertible if there exists another topological defect $\mathcal D^{-1}$ such that

$$
\mathcal D\mathcal D^{-1}=1,
\qquad
\mathcal D^{-1}\mathcal D=1.
$$

A set of invertible simple topological defects forms a group under fusion. Ordinary symmetry groups are recovered this way.

For a finite ordinary symmetry group $G$,

$$
\{U_g\}_{g\in G}
$$

obey

$$
U_gU_h=U_{gh}.
$$

For an Abelian one-form symmetry $A$, the topological symmetry surfaces also fuse group-like:

$$
U_a(\Sigma)U_b(\Sigma)=U_{a+b}(\Sigma),
\qquad
a,b\in A.
$$

Invertible defects impose constraints through crossing. If a defect $U_g$ surrounds a local operator $\mathcal O$, shrinking it across the operator gives

$$
\mathcal O\mapsto g\cdot\mathcal O.
$$

For a charged operator in a one-dimensional representation of a finite Abelian group, this may be a phase. For a nonabelian group, it may rotate a multiplet. Either way, the action is reversible.

Invertible symmetry is therefore the case where topological fusion reproduces ordinary representation theory.

## What fails for non-invertible defects

A non-invertible defect $\mathcal N$ is topological but lacks a fusion inverse. The simplest diagnostic is that

$$
\mathcal N\mathcal N^\vee
$$

contains more than the identity.

For example, a common schematic pattern is

$$
\mathcal N\mathcal N^\vee=1+\eta,
$$

where $\eta$ is a nontrivial invertible defect. If there were an inverse, fusing $\mathcal N$ with that inverse would give only $1$. The extra sector $\eta$ means the process cannot be undone.

This is why the phrase “what’s done cannot be undone” is apt: after applying $\mathcal N$, the theory is not simply moved to a unique group-related configuration. It is projected, summed, or branched into sectors in a way that loses group-like reversibility.

But non-invertible does not mean useless. Topological deformation still gives Ward-like identities. Fusion still constrains which correlators and defect endpoints are allowed. Non-invertible defects can still organize Hilbert spaces, boundary conditions, local operators, and RG flows.

## The Ising fusion rule as the first example

The two-dimensional Ising CFT has three basic topological lines commonly denoted

$$
1,\qquad \eta,\qquad \mathcal N.
$$

Here $1$ is the trivial line, $\eta$ is the invertible $\mathbb Z_2$ spin-flip line, and $\mathcal N$ is the Kramers–Wannier duality line. The characteristic fusion rules are

$$
\eta^2=1,
\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,
\qquad
\mathcal N^2=1+\eta.
$$

The line $\eta$ is invertible. The line $\mathcal N$ is not. There is no line $\mathcal N^{-1}$ such that $\mathcal N\mathcal N^{-1}=1$, because fusing $\mathcal N$ with itself gives two sectors, not one.

This example is pedagogically perfect because it shows the entire phenomenon in one line:

$$
\boxed{\mathcal N^2=1+\eta.}
$$

The duality line is a symmetry defect, but it is not a group element.

:::note[Source note: Ising notation]
The labels $1$, $\eta$, and $\mathcal N$ are common in modern non-invertible-symmetry lectures. Other CFT sources may use labels such as $1$, $\psi$, $\sigma$ or describe the same structure through topological defect lines and the Ising fusion category. The physics is the non-invertible fusion rule.
:::

## Fusion is not ordinary multiplication

The equation

$$
\mathcal N^2=1+\eta
$$

does not mean that $\mathcal N^2$ is numerically equal to $2$. It means that the fused defect decomposes as a direct sum of two topological sectors.

The plus sign is a direct-sum operation in the defect category. Correlation functions with the fused defect are sums of correlation functions with the resulting simple defects. Schematically,

$$
\langle \mathcal N^2\,\mathcal X\rangle
=
\langle \mathcal X\rangle
+
\langle \eta\,\mathcal X\rangle,
$$

when the notation is normalized and the topology of insertions is simple enough.

This is analogous to decomposing a tensor product of representations,

$$
R\otimes S=\bigoplus_T N_{RS}{}^T\,T,
$$

but now the objects being fused are topological defects rather than representation spaces.

## Quantum dimension

In many semisimple examples, each simple topological defect $\mathcal D_a$ has a quantum dimension $d_a$. Fusion implies

$$
d_ad_b=\sum_cN_{ab}{}^c d_c.
$$

Invertible defects have

$$
d_a=1.
$$

For the Ising duality defect,

$$
\mathcal N^2=1+\eta,
\qquad
d_\eta=1,
$$

so

$$
d_\mathcal N^2=2,
\qquad
d_\mathcal N=\sqrt 2.
$$

A noninteger or greater-than-one quantum dimension is a strong signal of non-invertibility in finite semisimple settings.

Quantum dimension is not a substitute for all defect data. It does not determine associators, junction spaces, braiding, or actions on boundary conditions. But it gives an immediate “size” test: if a simple defect has $d_a\ne1$, it is not invertible.

## Non-invertible Ward identities

Ordinary Ward identities come from moving a symmetry defect across operator insertions. The same deformation logic works for non-invertible defects.

Let $\mathcal N(\Sigma)$ be a topological defect. If $\Sigma$ is deformed without crossing anything, correlation functions do not change. If it crosses an operator, boundary, line, or defect endpoint, the insertion is transformed according to the action of $\mathcal N$.

The difference is that the action may not send a single operator to a single operator in a representation. It may map an object to a sum, to a projected sector, or to an operator living in a different defect/background sector.

For this reason, non-invertible Ward identities are often more naturally stated diagrammatically:

$$
\text{slide the defect}
\quad=\quad
\text{decompose the result by fusion}.
$$

The constraint is still powerful: topological deformation equates different correlation functions. But it is not usually a simple charge-conservation rule.

## Relation to gauging

Many non-invertible defects arise from gauging ordinary symmetries in a controlled way.

A rough construction is:

1. Start with a QFT $\mathcal T$ with an ordinary symmetry $G$.
2. Stack or couple to a topological theory carrying related $G$ data.
3. Gauge a diagonal non-anomalous symmetry along a wall or in a region.
4. The resulting topological wall may be non-invertible.

This type of construction explains why gauging is not generally invertible. If one gauges a finite group $G$, the resulting theory typically has a dual higher-form or quantum symmetry, but “ungauging” requires extra data. The operation can forget information, project onto invariant sectors, or sum over bundles. Such operations naturally produce defects that cannot be undone by a single inverse defect.

This is one reason non-invertible symmetry is not an exotic add-on. It is already hiding in familiar operations: gauging, orbifolding, duality, and projection.

## Non-invertible does not mean non-unitary

The word “non-invertible” can sound like a violation of quantum-mechanical unitarity. That is not what it means.

A unitary QFT can have non-invertible topological defects. The non-invertibility is about the **fusion algebra of defects**, not about time evolution by a nonunitary operator.

A topological defect need not be an ordinary unitary operator acting on the Hilbert space of the theory in a way that has a two-sided inverse. Depending on quantization, a defect may map between Hilbert spaces, between sectors, between boundary conditions, or between theory presentations. Its categorical action can be perfectly compatible with unitarity of the QFT.

The safe statement is:

$$
\text{unitarity is a property of the QFT},
\qquad
\text{invertibility is a property of defect fusion}.
$$

They are related in examples, but they are not the same property.

## Categorical symmetry in one paragraph

A category is a structure with objects and morphisms. For defects, the objects are defects and the morphisms are defect-local operators or junction operators. Fusion gives a tensor product of defects. Associativity is not just an equation; it comes with coherent isomorphisms.

For ordinary group symmetry, the category of symmetry defects is very simple: one invertible simple object for each group element, and fusion is group multiplication.

For non-invertible symmetry, the category is richer. Simple objects can have nontrivial fusion multiplicities, nontrivial junction spaces, nontrivial associators, and nontrivial actions on boundary conditions or charged objects.

Thus “categorical symmetry” means:

$$
\text{symmetry data}=
\text{topological defects + fusion + junctions + actions}.
$$

Groups are the special case where this category is pointed: every simple object is invertible.

## How to recognize non-invertible symmetry in practice

Look for these signs:

| Signal | Meaning |
|---|---|
| A topological defect has fusion $\mathcal N^2=1+\eta$ or similar. | The defect is non-invertible. |
| A duality is exact only at a self-dual point. | It may become a non-invertible duality defect. |
| Gauging or orbifolding creates a new topological defect not associated with a group element. | Non-invertible symmetry may have emerged. |
| Defect fusion resembles representation tensor products rather than group multiplication. | The symmetry is categorical. |
| A “symmetry action” projects onto invariant sectors or sums over backgrounds. | The operation is not reversible in the group sense. |
| Topological defects have quantum dimensions larger than one. | In semisimple finite settings, they are not invertible. |

These signals are diagnostics, not definitions. The definition is still topological defect fusion.

## Common pitfalls

**“If it has no inverse, it cannot be a symmetry.”** This is true only if one defines symmetry as a group action. The generalized definition uses topological operators. Non-invertible symmetry is symmetry in that broader, modern sense.

**“The plus sign in fusion is ordinary addition of numbers.”** No. It is direct sum of defect sectors.

**“A non-invertible defect is just a mixed state.”** Not in general. It is an extended operator or interface in the QFT, often topological and compatible with unitary dynamics.

**“All dualities are non-invertible symmetries.”** No. Some dualities are invertible equivalences between theories. A non-invertible duality defect appears when the duality operation becomes a topological defect of a single theory but cannot be inverted by fusion.

**“Category theory is optional decoration.”** For a first physical understanding, diagrams and fusion rules are enough. For associativity, defect junctions, boundary actions, and anomaly questions, categorical language becomes the clean bookkeeping, not decoration.

**“Non-invertible symmetries replace ordinary symmetries.”** They extend them. Group-like symmetry is the pointed/invertible special case.

## Relations to other pages

Topological Defects as Symmetries will make the defect-first definition precise. Fusion Rules will develop the algebraic structure behind equations like $\mathcal N_a\mathcal N_b=\sum_cN_{ab}{}^c\mathcal N_c$. Duality Defects and Kramers–Wannier Duality Defect will supply the canonical examples.

The [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) page gives the general defect-fusion background. The [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) page explains the invertible generalized-symmetry case. [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) prepares the gauging operation that often produces non-invertible defects.

## Research status

The two-dimensional theory of topological defects and non-invertible symmetry is mature and rich, especially in rational CFT, statistical models, orbifolds, and TQFT-related settings.

In higher dimensions, the subject is developing quickly. There are now many constructions using gauging, duality, condensation defects, higher-form symmetries, and symmetry TFT. The core concept is stable: topological defects with non-group-like fusion. The taxonomy, representation theory, anomaly theory, and best computational tools are still active research areas.

## Exercises

### Exercise 1: Invertibility test

Suppose $\eta^2=1$ and $\mathcal N^2=1+\eta$. Which defect is invertible?

<details><summary><strong>Solution</strong></summary>

The defect $\eta$ is invertible because

$$
\eta\eta=1.
$$

Its inverse is itself.

The defect $\mathcal N$ is not invertible. Fusing it with itself gives

$$
\mathcal N^2=1+\eta,
$$

not the identity alone. There is no simple inverse defect $\mathcal N^{-1}$ whose product with $\mathcal N$ gives only $1$.

</details>

### Exercise 2: Quantum dimension from fusion

Assume $d_1=d_\eta=1$ and

$$
\mathcal N^2=1+\eta.
$$

Use the fusion rule for quantum dimensions to compute $d_\mathcal N$.

<details><summary><strong>Solution</strong></summary>

Quantum dimensions obey

$$
d_ad_b=\sum_cN_{ab}{}^c d_c.
$$

Thus

$$
d_\mathcal N^2=d_1+d_\eta=1+1=2.
$$

Taking the positive root,

$$
d_\mathcal N=\sqrt2.
$$

Since this is not $1$, $\mathcal N$ is non-invertible in this semisimple setting.

</details>

### Exercise 3: Why group multiplication cannot give sums

Explain why the fusion rule

$$
\mathcal N^2=1+\eta
$$

cannot be the multiplication law of an ordinary group.

<details><summary><strong>Solution</strong></summary>

In an ordinary group, the product of two elements is a single element. If $\mathcal N$ were a group element, then $\mathcal N^2$ would have to be one group element. But the rule says the product decomposes into a direct sum of two defect sectors, $1$ and $\eta$. This is not group multiplication. It is fusion in a category of topological defects.

</details>

### Exercise 4: Non-invertible does not mean broken

A topological defect $\mathcal N$ has no inverse, but correlation functions are unchanged when its support is smoothly deformed without crossing insertions. Is $\mathcal N$ broken, anomalous, or non-invertible?

<details><summary><strong>Solution</strong></summary>

The information given says $\mathcal N$ is topological and non-invertible. It does not say the symmetry is broken or anomalous. Breaking would require a failure of the vacuum or phase to respect the corresponding topological constraints. An anomaly would be an obstruction to gauging or consistently coupling to appropriate backgrounds. Non-invertibility alone is a statement about fusion, not about breaking or anomaly.

</details>

### Exercise 5: Direct sums in correlators

Assume a defect fusion rule

$$
\mathcal A\mathcal B=\mathcal C+\mathcal D.
$$

What should this mean schematically for a correlator containing the fused defect?

<details><summary><strong>Solution</strong></summary>

In a semisimple topological setting, the fused defect decomposes as a direct sum of sectors. Therefore a correlator with the fused defect is the sum of correlators with the resulting simple defects:

$$
\langle \mathcal A\mathcal B\,\mathcal X\rangle
=
\langle \mathcal C\,\mathcal X\rangle
+
\langle \mathcal D\,\mathcal X\rangle,
$$

up to the conventions and normalizations used for defect operators. The plus sign is not ordinary multiplication of numbers; it denotes direct-sum decomposition of defect sectors.

</details>

## References

- Shu-Heng Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.” A physics-first introduction centered on duality defects and examples.
- Sakura Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries.” A broad introduction to topological defects, non-invertible symmetry, gauging constructions, and symmetry TFT.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” The standard topological-operator starting point for generalized symmetry.
- Petkova and Zuber, papers on generalized twisted partition functions and topological defect lines in rational CFT.
- Fröhlich, Fuchs, Runkel, and Schweigert, papers on topological defects, rational CFT, and tensor-categorical structures.
- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, for 2D CFT background and Ising-model context.

## Version history

- **2026-06-20:** Initial polished draft. Introduced invertible group-like defects, non-invertible fusion, Ising duality fusion, quantum dimension, non-invertible Ward identities, and common pitfalls.
