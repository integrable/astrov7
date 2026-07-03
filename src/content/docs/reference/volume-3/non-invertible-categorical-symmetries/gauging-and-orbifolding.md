---
title: "Gauging and Orbifolding"
description: "Explains gauging and orbifolding as defect condensation, from finite group symmetries to non-invertible generalized gauging by algebra objects."
sidebar:
  label: "Gauging and Orbifolding"
  order: 8
level: Advanced
status: "Polished draft"
source: "Dijkgraaf–Witten; Dixon–Harvey–Vafa–Witten; Fröhlich–Fuchs–Runkel–Schweigert; Diatlyk–Luo–Wang–Weller; Shao TASI lectures; Schäfer-Nameki ICTP lectures."
topics:
  - gauging
  - orbifolding
  - non-invertible symmetry
  - topological interfaces
  - algebra objects
  - defect condensation
canonicalTopics:
  - gauging-noninvertible-symmetry
  - generalized-orbifold
  - algebra-object-gauging
  - topological-interface
  - defect-condensation
researchStatus:
  established:
    - "Finite group orbifolds and defect-network formulations of two-dimensional gauging are standard tools in CFT and statistical field theory."
    - "In two-dimensional semisimple settings, generalized gauging is naturally described by condensing suitable algebra objects in a fusion category of topological defects."
  active:
    - "Higher-dimensional generalized gauging, fermionic refinements, nonsemisimple categories, anomaly criteria, and SymTFT formulations remain active research areas."
---

## Summary

**Gauging** means turning symmetry background data into dynamical data. For an ordinary finite group symmetry $G$, this can be described in two equivalent languages.

In the background-field language, one sums over flat $G$ bundles. In the topological-defect language, one sums over networks of $G$ symmetry defects. In two-dimensional QFT and CFT this operation is often called an **orbifold**:

$$
\mathcal T
\quad\longmapsto\quad
\mathcal T/G.
$$

The defect formulation makes the non-invertible generalization almost unavoidable. If a symmetry is a fusion category $\mathcal C$ of topological defects, then a generalized gauging is not “summing over group elements.” There may be no group. Instead, one chooses a condensable algebra object

$$
A\in\mathcal C
$$

and decorates the theory with networks of $A$-defects and their junctions. The gauged or generalized-orbifolded theory is written schematically as

$$
\mathcal T/A.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![Schematic of generalized gauging: a QFT with topological defects, a chosen algebra object, a gauging interface, and a gauged theory with dual defect data.](/figures/symmetry-anomalies-topology/generalized-gauging-interface.svg)

<figcaption>

Generalized gauging is best viewed as a topological interface. Choosing an algebra object $A$ in the symmetry category of $\mathcal T$ produces a new theory $\mathcal T/A$. The interface remembers the gauging operation; composing it with its reverse recovers the condensed defect data.

</figcaption>
</figure>

This page explains the physical picture. The algebra-object language is introduced only as much as needed: it is the compact way to encode which defect networks are allowed, how they fuse, and why the resulting theory remains local.

## Prerequisites

You should know [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/), [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/), [Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/), and [Non-Invertible Ward Identities: Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/non-invertible-ward-identities-preview/).

It also helps to know [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) and [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/). The page uses two-dimensional defect-line language as the cleanest teaching setting; the same words often require higher-categorical upgrades in higher dimensions.

## Core idea

Gauging is a projection plus a sum over twisted sectors.

For a finite group $G$, the rough Hilbert-space picture is:

1. keep $G$-invariant states;
2. add sectors twisted by $G$ holonomies;
3. impose consistency under changing how the twists are represented.

In a two-dimensional Euclidean path integral, those twists can be drawn as topological symmetry lines. Gauging $G$ means allowing networks of these lines to fluctuate and summing over them.

For a non-invertible symmetry, the same picture survives if we replace “group line” by “chosen network of topological defects.” The operation is no longer determined by a group alone. It is determined by an algebra object $A$ whose multiplication tells us how defect segments can join.

The slogan is:

$$
\text{finite group gauging}
=
\text{condense the regular algebra } \bigoplus_{g\in G}U_g,
$$

and

$$
\text{generalized gauging}
=
\text{condense a suitable algebra object } A\in\mathcal C.
$$

## Setup and notation

Let $\mathcal T$ be a two-dimensional QFT with a category $\mathcal C$ of topological line defects. Simple defects are denoted

$$
a,b,c,\ldots\in\mathcal C.
$$

Fusion is denoted by

$$
a\otimes b\simeq \bigoplus_c N_{ab}{}^c\,c
$$

when the category is semisimple. The transparent defect is $1$.

An algebra object $A$ is a formal direct sum of defects together with a multiplication junction

$$
m:A\otimes A\to A
$$

and a unit junction

$$
\iota:1\to A.
$$

Associativity says that two ways of multiplying three $A$ defects agree:

$$
m\circ(m\otimes 1_A)=m\circ(1_A\otimes m),
$$

up to the associator of $\mathcal C$. In a unitary QFT one also wants positivity and separability conditions; in two-dimensional CFT these are often packaged by saying that $A$ should be a suitable symmetric separable Frobenius algebra.

:::note[Source note]
Different communities use slightly different words: algebra object, condensable algebra, Frobenius algebra, Q-system, gaugable algebra, or generalized orbifold datum. The physical role is the same here: $A$ specifies the topological defect networks that are allowed to fluctuate in the gauged theory.
:::

## Ordinary group gauging as the model case

Suppose $\mathcal T$ has a finite non-anomalous group symmetry $G$. The topological symmetry lines are $U_g$ and obey

$$
U_g\otimes U_h\simeq U_{gh}.
$$

The algebra object for gauging the full group is

$$
A_G=\bigoplus_{g\in G}U_g.
$$

Its multiplication is induced by group multiplication:

$$
U_g\otimes U_h\to U_{gh}.
$$

Networks of $A_G$ lines are the defect version of flat $G$ gauge fields. Moving the network by local topological moves corresponds to changing a triangulation or gauge-field presentation without changing the physical observable.

If the group has a ’t Hooft anomaly, these local moves fail by phases. Then $A_G$ cannot be made into a consistent condensable algebra in the symmetry category of the theory. This is the defect-network version of the statement that an anomalous global symmetry cannot be gauged.

For an Abelian group, the orbifold $\mathcal T/G$ often has a dual quantum symmetry $\widehat G$. For a non-Abelian group, the dual symmetry is not generally a group of invertible lines; representation-theoretic or categorical symmetry data naturally appears. This is one of the simplest ways non-invertible symmetry enters ordinary orbifold physics.

## What changes for non-invertible symmetries

For a non-invertible symmetry category $\mathcal C$, there is no canonical sum over “all group elements,” because the simple defects do not form a group. Fusion may look like

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta.
$$

Trying to “gauge $\mathcal N$” as if it were a group element is the wrong starting point. The correct question is:

$$
\text{Which algebra objects }A\in\mathcal C\text{ can be consistently condensed?}
$$

The answer can include algebra objects built partly or entirely from non-invertible defects. Gauging $A$ means allowing networks of $A$ to fluctuate, with junctions specified by the multiplication map $m$.

The local consistency conditions are the analogues of gauge invariance. If a defect network is moved by local Pachner-like moves, the correlator should not change. Algebra associativity, separability, and Frobenius conditions are the compact categorical version of those physical requirements.

:::caution[Do not gauge a fusion rule]
A fusion rule such as $\mathcal N^2=1+\eta$ is not, by itself, a gauging prescription. Gauging needs junction data and local consistency moves. In categorical language it needs an algebra object, not merely a label.
:::

## Orbifolding as an interface

A clean way to think about gauging is through a topological interface.

Let $I_A$ be the interface from $\mathcal T$ to the gauged theory $\mathcal T/A$. Its orientation reversal or adjoint is $I_A^\dagger$. The composition

$$
I_A^\dagger\otimes I_A
$$

is a topological defect in the original theory. In the simplest defect-condensation picture, it is identified with the condensed algebra $A$:

$$
I_A^\dagger\otimes I_A\simeq A.
$$

This formula is schematic, but the picture is powerful. Gauging is not just a map of partition functions. It is an interface between QFTs, and that interface can be fused with other interfaces. Sequential gauging becomes fusion of interfaces. Self-duality under gauging becomes an invertible or non-invertible interface from a theory to itself.

For ordinary group orbifolds, this explains the familiar relation between a theory and its orbifold. For generalized orbifolds, it explains why the collection of possible gaugings forms a network or groupoid of theories connected by topological interfaces rather than a single quotient operation.

## The dual symmetry after gauging

Gauging often creates a dual symmetry.

For a finite Abelian group $A$, gauging a non-anomalous $A$ zero-form symmetry produces a dual $\widehat A$ symmetry in the gauged theory. This mirrors the higher-form story where gauging a finite Abelian $q$-form symmetry produces a dual $(d-q-2)$-form symmetry.

For a non-Abelian finite group, the dual object is not simply another finite group of invertible defects. The gauged theory contains defects associated with representations, twisted sectors, and quantum symmetry data. In two-dimensional CFT this is one of the oldest sources of non-invertible topological lines.

For generalized gauging by an algebra object $A\in\mathcal C$, the symmetry of $\mathcal T/A$ is typically described by a new category: defects compatible with the $A$-condensation, often phrased as bimodules or module endofunctors. This is why the algebra-object language is not optional bookkeeping. It predicts the symmetry of the theory after gauging.

## Gauging versus projecting

Another common misunderstanding is to treat gauging as merely “keep invariant operators.”

That is only half the operation. Gauging also adds twisted sectors. In a two-dimensional orbifold, local operators in the gauged theory include operators from sectors with nontrivial monodromy around them. In the defect picture, these are operators attached to or ending defect networks.

For ordinary finite group gauging, this is the familiar difference between taking invariants and constructing an orbifold. For non-invertible generalized gauging, the distinction is even more important: the new theory may contain operators and defects that do not have a simple description in the original untwisted local operator algebra.

The mnemonic is:

$$
\text{gauging} \neq \text{projection only}.
$$

It is

$$
\text{gauging}=\text{projection}+\text{sum over twisted/defect sectors}.
$$

## Examples

### Finite Abelian orbifold

Let $\mathcal T$ have a non-anomalous $\mathbb Z_N$ symmetry. The symmetry defects are $U_k$, with

$$
U_k\otimes U_\ell=U_{k+\ell}.
$$

The gauging algebra is

$$
A_{\mathbb Z_N}=\bigoplus_{k=0}^{N-1}U_k.
$$

The orbifold $\mathcal T/\mathbb Z_N$ contains invariant untwisted operators and twisted-sector operators. It also has a dual quantum symmetry $\widehat{\mathbb Z_N}\cong\mathbb Z_N$ acting on those twisted sectors.

### Non-Abelian orbifold

For a non-Abelian finite group $G$, the same formula

$$
A_G=\bigoplus_{g\in G}U_g
$$

exists when the anomaly vanishes. But the dual symmetry of the orbifold is no longer just another copy of $G$. Representation-theoretic labels and non-invertible defects appear naturally. This is one of the first places where a student trained only on Abelian orbifolds sees why categorical language is more natural than group language.

### Ising self-duality

At the critical Ising point, the Kramers–Wannier duality defect $\mathcal N$ obeys

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta,
$$

where $\eta$ is the spin-flip defect. This non-invertible defect can be understood from the fact that the Ising CFT is self-dual under gauging its $\mathbb Z_2$ spin-flip symmetry. The gauging interface, composed with the self-duality equivalence, becomes a defect of the original theory. Its square is the sum over the $\mathbb Z_2$ symmetry defects.

This example is the prototype for many duality defects produced by gauging plus an equivalence.

## Anomalies and obstruction tests

For ordinary finite group symmetries, a ’t Hooft anomaly obstructs gauging. In defect language, the obstruction appears as a failure of the defect-network local moves to be invariant. In categorical language, it appears as a failure to construct the appropriate condensable algebra.

For non-invertible symmetries, the anomaly story is subtler. A full fusion category may be anomalous in one sense while still containing algebra objects that can be condensed. Conversely, a fusion rule that looks innocent may fail once the associators, junctions, and unitarity conditions are included.

A reliable practical test is:

1. identify the full defect category, not just the fusion algebra;
2. specify the candidate algebra object $A$;
3. check associativity and unit conditions with the actual associators;
4. check the Frobenius/separability/unitarity conditions appropriate to the theory;
5. verify that the resulting defect-network path integral is local and topological under allowed moves.

This is the generalized version of “check the anomaly before gauging.”

## How to use the idea in practice

When reading a paper that says a non-invertible symmetry is gauged, ask:

| Question | Why it matters |
|---|---|
| What is the symmetry category $\mathcal C$? | Fusion labels alone are not enough. |
| What is the algebra object $A$? | This is the actual gauging datum. |
| What are the multiplication junctions? | They define the allowed networks. |
| What local moves are imposed? | These encode gauge invariance and locality. |
| What is the interface $I_A$? | It tracks the relation between the original and gauged theories. |
| What is the dual category after gauging? | Gauging usually creates new symmetry data. |
| Are there anomalies or fractionalization choices? | Different choices can produce inequivalent gaugings. |

This checklist is more useful than asking whether the symmetry is “really” a group. The point of generalized symmetry is that the answer may be no.

## Common pitfalls

**“Gauging a non-invertible defect means summing over that one defect.”** Not quite. Gauging requires an algebra object and junction data. A single defect label is not enough.

**“Orbifolding is just projecting onto invariant states.”** Projection is only the untwisted part. A genuine orbifold includes twisted sectors or defect sectors.

**“The dual symmetry after gauging is always a group.”** Only in special cases. Gauging a non-Abelian finite group or a generalized symmetry naturally produces categorical symmetry data.

**“If a category is anomalous, nothing can be gauged.”** Too quick. The whole category may fail a strong anomaly-free condition while some algebra objects may still define consistent generalized gaugings.

**“An algebra object is abstract math with no physical content.”** The algebra object is the physical network of condensed defects and allowed junctions. It is the generalized gauge field.

**“Sequential gauging is always commutative.”** Fusing topological interfaces can be nontrivial. The generalized orbifold groupoid records which sequences of gaugings are equivalent and which are not.

## Relations to other pages

[Duality Defects](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/duality-defects/) explains why gauging followed by an equivalence can create a non-invertible defect in the original theory.

[Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/) gives the basic Ising example.

[Tambara–Yamagami Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/tambara-yamagami-preview/) explains the standard fusion category pattern arising from Abelian duality defects.

[Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) will later package gauging, interfaces, boundary conditions, and anomalies in a one-higher-dimensional topological theory.

## Research status

Ordinary finite group orbifolds are classical material in two-dimensional CFT. The formulation of generalized gauging by algebra objects and topological interfaces is now a standard research language in two-dimensional semisimple settings.

Several frontiers remain open or rapidly developing: generalized gauging in higher-dimensional QFT, nonsemisimple and logarithmic theories, fermionic and spin-refined settings, boundary conditions and defects after gauging, anomaly criteria, and the SymTFT classification of possible gaugings.

## Exercises

### Exercise 1: Regular algebra for a finite group

Let $G$ be a finite group with invertible defects $U_g$ satisfying $U_g\otimes U_h=U_{gh}$. Show that

$$
A_G=\bigoplus_{g\in G}U_g
$$

has a natural multiplication map $A_G\otimes A_G\to A_G$.

<details><summary><strong>Solution</strong></summary>

The tensor product is

$$
A_G\otimes A_G
=
\bigoplus_{g,h\in G}U_g\otimes U_h
=
\bigoplus_{g,h\in G}U_{gh}.
$$

The multiplication map sends the summand $U_g\otimes U_h$ to the summand $U_{gh}$ of $A_G$. Associativity follows from associativity of group multiplication, up to the associator of the defect category. If the group symmetry is anomalous, that associator can contain nontrivial phases obstructing consistent gauging.

</details>

### Exercise 2: Projection is not enough

Explain why gauging a finite symmetry is not the same as keeping only invariant local operators.

<details><summary><strong>Solution</strong></summary>

Keeping invariant local operators produces the invariant part of the untwisted sector. Gauging also sums over nontrivial background bundles or, in defect language, includes configurations with nontrivial symmetry-defect networks. In two-dimensional orbifolds these configurations produce twisted sectors and twist fields. Therefore gauging is projection plus a sum over twisted sectors, not projection alone.

</details>

### Exercise 3: Interface composition

Suppose $I_A$ is a topological interface from $\mathcal T$ to $\mathcal T/A$. What is the physical meaning of the schematic relation

$$
I_A^\dagger\otimes I_A\simeq A?
$$

<details><summary><strong>Solution</strong></summary>

Crossing from $\mathcal T$ to $\mathcal T/A$ and back to $\mathcal T$ should leave behind the topological defect data that was condensed in the gauging operation. The interface followed by its reverse therefore behaves, as a defect in the original theory, like the algebra object $A$. This relation is schematic because its precise interpretation depends on the defect category and normalization, but it captures the idea that gauging is encoded by an interface whose self-composition remembers the condensed network.

</details>

### Exercise 4: A self-duality defect

Assume $\mathcal T$ has an anomaly-free finite Abelian symmetry $K$ and that $\mathcal T/K$ is equivalent to $\mathcal T$. Explain why one expects a duality defect $\mathcal N$ in $\mathcal T$ whose square is roughly a sum over $K$ symmetry defects.

<details><summary><strong>Solution</strong></summary>

Gauging $K$ gives an interface $I_K:\mathcal T\to\mathcal T/K$. If $\mathcal T/K\simeq\mathcal T$, compose $I_K$ with this equivalence to get a defect $\mathcal N$ of $\mathcal T$. Fusing $\mathcal N$ with its adjoint corresponds to going through the gauging interface and back, which leaves the regular algebra

$$
A_{\mathrm{reg}}=\bigoplus_{k\in K}U_k.
$$

Thus one expects

$$
\mathcal N\otimes\mathcal N^\dagger\simeq\bigoplus_{k\in K}U_k,
$$

with details depending on conventions and orientation.

</details>

## References

- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology.”
- L. Dixon, J. Harvey, C. Vafa, and E. Witten, “Strings on Orbifolds.”
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, works on defect lines, Frobenius algebras, and rational CFT correlators.
- I. Brunner, N. Carqueville, and D. Plencner, “Orbifolds and topological defects.”
- O. Diatlyk, C. Luo, Y. Wang, and Q. Weller, “Gauging Non-Invertible Symmetries: Topological Interfaces and Generalized Orbifold Groupoid in 2d QFT.”
- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.”
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries.”

## Version history

- 2026-06-20: Initial polished draft. Added generalized gauging as defect condensation, algebra-object terminology, orbifold/interface viewpoint, anomaly cautions, examples, and exercises.
