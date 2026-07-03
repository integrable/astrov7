---
title: "Tambara–Yamagami Preview"
description: "Introduces Tambara–Yamagami fusion categories as the standard categorical pattern behind Abelian Kramers–Wannier duality defects and many non-invertible symmetries."
sidebar:
  label: "Tambara–Yamagami: Preview"
  order: 9
level: Advanced
status: "Polished draft"
source: "Tambara–Yamagami; Etingof–Gelaki–Nikshych–Ostrik; Shao TASI lectures; Schäfer-Nameki ICTP lectures; Ising and orbifold defect literature."
topics:
  - Tambara-Yamagami category
  - non-invertible symmetry
  - Kramers-Wannier duality
  - duality defects
  - fusion category
canonicalTopics:
  - tambara-yamagami-category
  - tambara-yamagami-symmetry
  - abelian-duality-defect
  - kramers-wannier-category
researchStatus:
  established:
    - "Tambara–Yamagami fusion categories are standard semisimple examples with a finite Abelian group of invertible objects and one non-invertible duality object."
    - "The Ising/Kramers–Wannier fusion rule is the basic physical example of the Tambara–Yamagami pattern with A = Z₂."
  active:
    - "Physical realizations, anomaly criteria, higher-dimensional analogues, lattice constructions, and SymTFT interpretations of Tambara–Yamagami-type symmetries remain active research topics."
---

## Summary

A **Tambara–Yamagami category** is one of the cleanest mathematical homes for Kramers–Wannier-type non-invertible symmetry.

It starts with a finite Abelian group $A$ of invertible defects,

$$
U_a\otimes U_b\simeq U_{a+b},
\qquad a,b\in A,
$$

and adds one non-invertible defect $\mathcal N$ satisfying

$$
U_a\otimes\mathcal N\simeq \mathcal N,
\qquad
\mathcal N\otimes U_a\simeq \mathcal N,
$$

and

$$
\mathcal N\otimes\mathcal N
\simeq
\bigoplus_{a\in A}U_a.
$$

For $A=\mathbb Z_2$, this is the fusion-rule skeleton of the critical Ising duality defect:

$$
\mathcal N^2\simeq 1\oplus\eta.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Schematic of Tambara-Yamagami fusion: invertible group defects form a finite Abelian group, the non-invertible defect absorbs group defects, and its square is the sum of all group defects.](/figures/symmetry-anomalies-topology/tambara-yamagami-fusion.svg)

<figcaption>

The Tambara–Yamagami pattern has a finite Abelian group $A$ of invertible defects and one non-invertible duality defect $\mathcal N$. Fusing $\mathcal N$ with itself produces the regular sum of all $A$ defects, so $d_{\mathcal N}=\sqrt{|A|}$.

</figcaption>
</figure>

This page is a preview. It explains the physical meaning of the fusion rules, how they arise from gauging and self-duality, what data are missing from the fusion rules alone, and why this family is a useful laboratory for non-invertible symmetry.

## Prerequisites

You should know [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/), [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/), [Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/), and [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/).

You do not need the formal classification of fusion categories. The goal is to recognize a recurring physical pattern and understand what extra data a full category contains beyond the displayed fusion algebra.

## Core idea

Tambara–Yamagami symmetry is what often appears when a theory with a finite Abelian symmetry is self-dual under gauging that symmetry.

Suppose a theory $\mathcal T$ has an anomaly-free finite Abelian symmetry $A$. Gauging $A$ gives another theory $\mathcal T/A$. If there is an equivalence

$$
\mathcal T/A\simeq\mathcal T,
$$

then the gauging interface can be reinterpreted as a defect $\mathcal N$ inside $\mathcal T$ itself. Fusing the interface with its reverse returns the regular sum of $A$ symmetry defects:

$$
\mathcal N\otimes\mathcal N^\dagger
\simeq
\bigoplus_{a\in A}U_a.
$$

In self-dual examples where $\mathcal N^\dagger\simeq\mathcal N$, this becomes

$$
\mathcal N^2\simeq\bigoplus_{a\in A}U_a.
$$

That is the Tambara–Yamagami fusion rule. The non-invertible defect remembers that gauging cannot be undone by a unique inverse operation. Undoing it requires summing over sectors.

## Setup and notation

Let $A$ be a finite Abelian group, written additively. The simple objects of a Tambara–Yamagami category are

$$
\{U_a\}_{a\in A}
\qquad\text{and}\qquad
\mathcal N.
$$

The invertible objects obey the group law

$$
U_a\otimes U_b\simeq U_{a+b},
\qquad
U_0\simeq 1.
$$

The non-invertible object is invariant under fusion with the invertible ones:

$$
U_a\otimes\mathcal N\simeq\mathcal N,
\qquad
\mathcal N\otimes U_a\simeq\mathcal N.
$$

Its square is the regular object of $A$:

$$
\mathcal N\otimes\mathcal N
\simeq
\bigoplus_{a\in A}U_a.
$$

The quantum dimensions are therefore

$$
d_{U_a}=1,
\qquad
d_{\mathcal N}^2=\sum_{a\in A}d_{U_a}=|A|,
$$

so

$$
d_{\mathcal N}=\sqrt{|A|}.
$$

This already proves non-invertibility unless $|A|=1$: an invertible object must have quantum dimension $1$.

:::note[Source note]
The displayed fusion rules are not the full category. A Tambara–Yamagami category also depends on associator data controlled by a nondegenerate symmetric bicharacter on $A$ and a sign-like parameter. Physically, those data affect defect-network evaluations and anomaly-like information.
:::

## The Ising example

The critical Ising CFT has a spin-flip symmetry defect $\eta$ obeying

$$
\eta^2=1.
$$

It also has the Kramers–Wannier duality defect $\mathcal N$ obeying

$$
\eta\otimes\mathcal N\simeq\mathcal N,
\qquad
\mathcal N\otimes\eta\simeq\mathcal N,
$$

and

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta.
$$

This is the Tambara–Yamagami pattern for

$$
A=\mathbb Z_2.
$$

The interpretation is familiar from the lattice Ising model. Kramers–Wannier duality exchanges order and disorder variables. At the self-dual critical point, duality becomes a topological defect. But applying duality twice does not return a single identity operator; it produces a sum over the spin-flip sectors. That is why the defect is non-invertible.

This example is pedagogically important because it is not exotic. It is the canonical Ising model, repackaged in the defect language.

## The Zₙ pattern

For a theory with a finite Abelian $\mathbb Z_N$ symmetry generated by $U_1$, the Tambara–Yamagami fusion rules become

$$
U_a\otimes U_b\simeq U_{a+b\,\mathrm{mod}\,N},
$$

$$
U_a\otimes\mathcal N\simeq\mathcal N,
$$

and

$$
\mathcal N^2\simeq\bigoplus_{a=0}^{N-1}U_a.
$$

Then

$$
d_{\mathcal N}=\sqrt N.
$$

Such patterns appear in Abelian duality settings, lattice models, compact boson examples, and generalized Kramers–Wannier dualities. The exact associators depend on more than $N$. They require a bicharacter

$$
\chi:A\times A\to U(1)
$$

that is nondegenerate and symmetric. For $A=\mathbb Z_N$, a typical bicharacter has the form

$$
\chi(a,b)=e^{2\pi i k ab/N}
$$

with $k$ chosen so that the pairing is nondegenerate.

The pairing determines how defect junctions transform when networks are reassociated. It is the categorical analogue of the phase data that appears in Fourier transforms and finite Abelian duality.

## Fusion rules versus full category

The fusion rules tell us which simple objects appear in products. They do not tell us how defect networks evaluate.

For Tambara–Yamagami categories, the missing data include:

| Data | Physical role |
|---|---|
| The finite Abelian group $A$ | Labels invertible defects. |
| A nondegenerate symmetric bicharacter $\chi$ | Controls phases in junction reassociation. |
| A parameter $\tau$ with $\tau^2=1/|A|$ | Controls normalization/sign of certain $\mathcal N$ junction moves. |
| Duality and pivotal/unitary structure | Controls orientation reversal and quantum dimensions. |
| Module data | Controls boundary conditions or sectors on which the category acts. |

Two categories can share the same displayed fusion rules but have different associators. They are not necessarily the same physical symmetry. This is the same lesson as before, now in a very explicit family.

:::caution[Fusion-rule skeleton]
Saying “the symmetry is Tambara–Yamagami” should mean more than $\mathcal N^2=\sum_a U_a$. One should specify, or at least acknowledge, the associator data. The fusion rule is the skeleton; the category is the living animal.
:::

## Why the square is a sum

The formula

$$
\mathcal N^2=\bigoplus_{a\in A}U_a
$$

has a simple gauging interpretation.

Think of $\mathcal N$ as the interface that gauges $A$, followed by an identification of the gauged theory with the original theory. Doing $\mathcal N$ twice means gauging and then ungauging. But the composition of gauging and ungauging is not the identity interface; it leaves behind the regular algebra

$$
A_{\mathrm{reg}}=\bigoplus_{a\in A}U_a.
$$

This is why the square of the duality defect is a sum. It is the memory of all $A$-twisted sectors.

Equivalently, $\mathcal N$ acts like a finite Fourier transform between order and disorder descriptions. Applying a Fourier transform twice gives a sum or projection over charge sectors, depending on normalization and conventions.

## Action on operators

The non-invertible defect $\mathcal N$ generally does not act by multiplying an operator by a phase. Instead, it can map order operators to disorder operators and attach topological lines.

In the Ising example, the spin field $\sigma$ and disorder field $\mu$ are exchanged by duality. The spin-flip defect $\eta$ acts by a sign on $\sigma$ but not in the same way on all defect sectors. The non-invertible defect $\mathcal N$ relates these sectors rather than giving an ordinary representation.

For a general finite Abelian $A$, an $A$-charged order operator can be related to a disorder operator carrying twisted-sector data. The precise action depends on the QFT, but the categorical pattern says that fusing twice sums over $A$ sectors.

This is the origin of Tambara–Yamagami Ward identities: sliding $\mathcal N$ across insertions gives identities among correlators involving order, disorder, and defect-attached operators.

## Quantum dimension as diagnostic

The quantum dimension is multiplicative under fusion and additive under direct sums:

$$
d_{a\otimes b}=d_a d_b,
\qquad
d_{a\oplus b}=d_a+d_b.
$$

For $\mathcal N^2=\bigoplus_{a\in A}U_a$,

$$
d_{\mathcal N}^2=|A|.
$$

Therefore $d_{\mathcal N}=\sqrt{|A|}$.

This is a useful diagnostic. If $|A|$ is not a perfect square, then the non-invertible defect has irrational quantum dimension. Such defects cannot be decomposed into a finite sum of invertible group-like defects. Even when $\sqrt{|A|}$ is an integer, non-invertibility is still visible in the fusion rule: $\mathcal N$ has no inverse because $\mathcal N^2$ is a sum, not the identity.

## Relation to gauging and orbifolding

Tambara–Yamagami categories often arise from a sequence:

$$
\text{finite Abelian symmetry}
\quad\longrightarrow\quad
\text{gauging}
\quad\longrightarrow\quad
\text{self-duality}
\quad\longrightarrow\quad
\text{non-invertible defect}.
$$

The duality defect is not a mystery operator inserted by hand. It is the gauging interface folded back into the original theory using a self-duality equivalence.

This construction explains why Tambara–Yamagami categories are so common in examples of Kramers–Wannier duality, Abelian orbifolds, compact bosons at special radii, and lattice models with generalized dualities.

It also explains why anomaly and fractionalization data matter. If gauging $A$ is obstructed, or if the self-duality equivalence carries extra choices, the would-be Tambara–Yamagami defect may be anomalous or may come in inequivalent versions.

## Anomaly cautions

Not every Tambara–Yamagami-looking fusion algebra is an anomaly-free physical symmetry of a standalone QFT.

Possible issues include:

1. the finite Abelian subgroup $A$ may have an anomaly;
2. the duality defect may fail to be consistently oriented or gauged;
3. the associator data may not admit the required unitary realization;
4. the category may be realizable only as a boundary of a nontrivial SymTFT;
5. gauging the non-invertible defect itself may be obstructed.

This does not make the formalism less useful. It makes it more useful: the categorical data remember precisely the obstructions that a bare fusion rule would hide.

## Common examples and non-examples

The Ising fusion category is the smallest example:

$$
A=\mathbb Z_2,
\qquad
\mathcal N^2=1+\eta.
$$

Finite Abelian $\mathbb Z_N$ duality categories give larger examples with

$$
\mathcal N^2=\sum_{a\in\mathbb Z_N}U_a.
$$

Compact boson CFTs and parafermionic theories furnish many related examples, sometimes with additional defects and symmetries beyond the basic Tambara–Yamagami pattern.

A Fibonacci category is not Tambara–Yamagami. It has a non-invertible object $\tau$ with

$$
\tau^2=1+\tau,
$$

which is a different fusion rule. This contrast is useful: not every non-invertible category is a duality category of Tambara–Yamagami type.

## How to recognize the pattern

When reading a paper or computing defect fusion, look for the following signs.

| Sign | Interpretation |
|---|---|
| A finite Abelian group of invertible defects $A$ | Candidate invertible part of a Tambara–Yamagami category. |
| One non-invertible defect $\mathcal N$ absorbing all $A$ defects | The duality object is blind to left or right fusion by $A$. |
| Fusion $\mathcal N^2=\bigoplus_{a\in A}U_a$ | Core Tambara–Yamagami fusion rule. |
| Quantum dimension $\sqrt{|A|}$ | Non-invertible duality object. |
| Order-disorder exchange | Physical Kramers–Wannier-type action. |
| Bicharacter phases in junction moves | Full category data beyond the fusion algebra. |
| Self-duality under gauging $A$ | Common origin of the defect. |

If all of these appear, Tambara–Yamagami language is probably the right first model.

## Common pitfalls

**“Tambara–Yamagami means just $\mathcal N^2=\sum_aU_a$.”** That is only the fusion-rule skeleton. The category also contains associator data.

**“The non-invertible defect acts like a phase.”** No. It usually maps order operators to disorder or defect-attached operators, and fusing twice produces a sum over sectors.

**“The Ising example is too special to be a guide.”** It is special, but it is the minimal model of the general pattern: a finite Abelian symmetry, gauging self-duality, and a non-invertible duality defect.

**“If $d_{\mathcal N}$ is an integer, the defect must be invertible.”** Invertibility requires fusing with a dual to get the identity, not merely integer quantum dimension.

**“All Tambara–Yamagami categories are automatically anomaly-free QFT symmetries.”** Realization in a QFT requires additional consistency. Anomalies and SymTFT data can obstruct gauging or standalone realization.

## Relations to other pages

[Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) explains how gauging a finite Abelian symmetry and identifying the orbifold with the original theory produces a duality defect.

[Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/) gives the basic Ising example.

[Non-Invertible Ward Identities: Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/non-invertible-ward-identities-preview/) explains how sliding $\mathcal N$ through insertions produces identities among order, disorder, and defect sectors.

[Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) will later reinterpret Tambara–Yamagami data through bulk topological theories and boundary conditions.

## Research status

Tambara–Yamagami fusion categories are mathematically standard and physically central as a clean family of non-invertible duality symmetries. Their Ising realization is textbook-level modern defect lore.

Current research studies their anomalies, generalized gauging, lattice realizations, higher-dimensional analogues, relation to SymTFT, and variants involving fermions, higher-form symmetries, nonsemisimple structures, or subsystem symmetries.

## Exercises

### Exercise 1: Quantum dimension

Use the Tambara–Yamagami fusion rule

$$
\mathcal N^2=\bigoplus_{a\in A}U_a
$$

and $d_{U_a}=1$ to show that $d_{\mathcal N}=\sqrt{|A|}$.

<details><summary><strong>Solution</strong></summary>

Quantum dimension is multiplicative under fusion and additive under direct sums. Therefore

$$
d_{\mathcal N}^2
=
d_{\mathcal N\otimes\mathcal N}
=
d_{\oplus_{a\in A}U_a}
=
\sum_{a\in A}d_{U_a}
=
|A|.
$$

Taking the positive root in a unitary theory gives

$$
d_{\mathcal N}=\sqrt{|A|}.
$$

</details>

### Exercise 2: Ising as Tambara–Yamagami

Show that the Ising fusion rules

$$
\eta^2=1,\qquad
\eta\mathcal N=\mathcal N\eta=\mathcal N,\qquad
\mathcal N^2=1+\eta
$$

fit the Tambara–Yamagami pattern.

<details><summary><strong>Solution</strong></summary>

Take

$$
A=\mathbb Z_2=\{0,1\}
$$

and identify

$$
U_0=1,\qquad U_1=\eta.
$$

Then the group law gives $\eta^2=1$. The non-invertible object $\mathcal N$ obeys

$$
U_a\mathcal N=\mathcal N
$$

for both $a=0,1$, and

$$
\mathcal N^2=U_0\oplus U_1=1\oplus\eta.
$$

This is exactly the Tambara–Yamagami fusion-rule skeleton for $A=\mathbb Z_2$.

</details>

### Exercise 3: Why no inverse?

Suppose $|A|>1$. Explain why $\mathcal N$ is not invertible.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ were invertible, there would be an object $\mathcal N^{-1}$ such that

$$
\mathcal N\otimes\mathcal N^{-1}=1.
$$

In a unitary fusion category, invertible objects have quantum dimension $1$. But

$$
d_{\mathcal N}=\sqrt{|A|}>1
$$

when $|A|>1$. Therefore $\mathcal N$ cannot be invertible. Equivalently, its square is a direct sum of several objects rather than a single simple object.

</details>

### Exercise 4: Fusion rule is not full data

Give two reasons why the displayed Tambara–Yamagami fusion rules do not fully specify the category.

<details><summary><strong>Solution</strong></summary>

First, the category needs associator data: local moves comparing $(a\otimes b)\otimes c$ and $a\otimes(b\otimes c)$. In Tambara–Yamagami categories these depend on a nondegenerate symmetric bicharacter $\chi$ and a parameter $\tau$.

Second, physical applications may require unitary, pivotal, module, boundary, or anomaly data. Two categories can share the same fusion coefficients but evaluate defect networks differently. Thus the fusion rules are only the skeleton of the category.

</details>

## References

- D. Tambara and S. Yamagami, “Tensor Categories with Fusion Rules of Self-Duality for Finite Abelian Groups.”
- P. Etingof, S. Gelaki, D. Nikshych, and V. Ostrik, *Tensor Categories*.
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, works on defect lines, Frobenius algebras, and rational CFT.
- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.”
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries.”
- A. Antinucci, F. Benini, C. Copetti, G. Galati, and G. Rizi, “Anomalies of Non-Invertible Self-Duality Symmetries: Fractionalization and Gauging.”
- S. Kim, O. Sela, and Z. Sun, “Higher Structure of Non-Invertible Symmetries from Lagrangian Descriptions.”

## Version history

- 2026-06-20: Initial polished preview. Added Tambara–Yamagami fusion rules, Ising example, gauging/self-duality origin, associator caveats, anomaly cautions, diagnostics, and exercises.
