---
title: "Examples in Two-Dimensional QFT"
description: "Collects concrete two-dimensional QFT and CFT examples of non-invertible symmetry, including Ising, Potts, orbifold, WZW, and rational-CFT defect examples."
sidebar:
  label: "Examples in 2D QFT"
  order: 10
level: Research
status: "Polished draft"
source: "Kramers–Wannier; Verlinde; Petkova–Zuber; Fuchs–Runkel–Schweigert; Runkel; Shao TASI lectures; Schäfer-Nameki ICTP lectures."
topics:
  - two-dimensional QFT
  - non-invertible symmetry
  - topological defects
  - Ising model
  - Potts model
  - rational CFT
  - orbifolds
canonicalTopics:
  - two-dimensional-noninvertible-symmetry
  - ising-duality-defect
  - rational-cft-defects
  - orbifold-quantum-symmetry
researchStatus:
  established:
    - "Two-dimensional QFT and CFT provide the cleanest laboratory for topological line defects, duality defects, and non-invertible fusion rules."
    - "In rational CFT, many topological defects can be constructed and classified using modular data, boundary CFT, and bimodule/category methods."
  active:
    - "Non-rational, nonsemisimple, fermionic, nonunitary, lattice, and higher-dimensional generalizations remain active research areas."
---

## Summary

Two-dimensional QFT is the best place to learn non-invertible symmetry by example. The reason is geometric: in two spacetime dimensions, topological symmetry operators are **lines**, and lines can be drawn, crossed, fused, ended on local operators, and wrapped around spatial circles. The algebra becomes visible.

The most important examples are:

| Example | Topological defects | Non-invertible feature |
|---|---|---|
| Critical Ising CFT | $1$, spin-flip line $\eta$, duality line $\mathcal N$ | $\mathcal N^2=1+\eta$ |
| Critical Potts and parafermion models | group-like and duality defects | duality defects fuse into sums |
| Orbifolds | defects from twisted sectors and quantum symmetry | gauging can turn group symmetry into categorical symmetry |
| Rational CFT | topological defects labeled by chiral data | Verlinde-like fusion rings |
| WZW models | defects related to integrable representations | fusion follows affine representation theory |
| Minimal models and ADE examples | defect lines tied to modular invariants | nontrivial defect algebras and boundary actions |

<figure class="doc-figure" style="--figure-width: 54rem;">

![A map of two-dimensional examples of non-invertible symmetry: Ising, Potts, orbifolds, WZW models, rational CFT, and lattice/statistical models feeding into topological defect categories.](/figures/symmetry-anomalies-topology/two-dimensional-noninvertible-examples.svg)

<figcaption>

Two-dimensional examples are the training ground for non-invertible symmetry. Statistical models, orbifolds, WZW models, and rational CFTs all produce topological line defects whose fusion can be group-like, duality-like, or genuinely non-invertible.

</figcaption>
</figure>

This page is not a catalogue of every 2D model. It is a conceptual map: what the defects are, what their fusion means, and what each example teaches.

## Prerequisites

You should know [Invertible versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/), [Topological Defects as Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/topological-defects-as-symmetries/), [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/), [Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/), [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/), and [Tambara–Yamagami Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/tambara-yamagami-preview/).

You do not need a full course in rational CFT. The page uses a small amount of CFT vocabulary: primary fields, fusion, modular data, topological line defects, and boundary conditions. When a formula depends on rational CFT assumptions, this is stated explicitly.

## Core idea

In two-dimensional QFT, a topological line defect $\mathcal D$ can be deformed freely as long as it does not cross operator insertions or other defects. This gives three operations:

1. **Crossing:** move $\mathcal D$ across a local operator and get an action on that operator.
2. **Wrapping:** place $\mathcal D$ around the spatial circle and get an operator on the Hilbert space.
3. **Fusion:** bring two parallel topological lines together and replace them by a sum of lines.

The key non-invertible phenomenon is fusion with branching:

$$
\mathcal D_a\otimes\mathcal D_b
\simeq
\bigoplus_c N_{ab}{}^c\,\mathcal D_c.
$$

If all $N_{ab}{}^c$ produce a single invertible answer, the symmetry is group-like. If a product produces a direct sum, there is no inverse operation and the symmetry is non-invertible.

The slogan for this page is:

$$
\text{2D non-invertible symmetry}=
\text{topological line defects with non-group-like fusion}.
$$

## Setup and conventions

We work in Euclidean two-dimensional QFT. Topological defects are drawn as oriented or unoriented lines, depending on the model. The identity defect is denoted $1$. Fusion is denoted by $\otimes$ or by juxtaposition.

A line defect wrapped on a spatial circle defines an operator on the Hilbert space,

$$
\widehat{\mathcal D}:\mathcal H\to\mathcal H.
$$

For an invertible symmetry line $U_g$,

$$
U_g\otimes U_h\simeq U_{gh}.
$$

For a non-invertible line $\mathcal N$, a typical fusion rule is

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta.
$$

Here $\oplus$ means a direct sum of superselection sectors in the topological-defect category. It is not ordinary addition of local operators.

:::note[Source note: rational versus general QFT]
Many exact formulas on this page come from rational CFT, where topological defects are especially rigid and semisimple. The conceptual lessons often survive more broadly, but non-rational and nonsemisimple theories require more careful functional-analytic and categorical language.
:::

## The critical Ising model

The critical Ising CFT is the smallest serious example. It has three primary fields,

$$
1,\qquad \sigma,\qquad \varepsilon,
$$

and central charge $c=1/2$. It also has a $\mathbb Z_2$ spin-flip symmetry. Let $\eta$ denote the corresponding topological symmetry line. It is invertible:

$$
\eta^2=1.
$$

The duality defect $\mathcal N$ implements Kramers–Wannier duality. It is topological at the critical point and obeys

$$
\eta\otimes\mathcal N\simeq\mathcal N,
\qquad
\mathcal N\otimes\eta\simeq\mathcal N,
$$

and

$$
\mathcal N\otimes\mathcal N\simeq 1\oplus\eta.
$$

This is the basic Ising non-invertible symmetry rule. It says that doing Kramers–Wannier duality twice does not give one unique inverse operation on the nose. It gives a sum over the identity and spin-flip sectors.

A useful way to remember it is through gauging. Gauging the $\mathbb Z_2$ spin-flip symmetry maps the critical Ising CFT back to itself. The gauging interface can therefore be folded into a line defect of the same theory. That line is $\mathcal N$. Composing the gauging interface with its reverse produces the regular sum

$$
1\oplus\eta.
$$

This is the physical origin of $\mathcal N^2=1+\eta$.

## Ising order and disorder operators

The Ising model also teaches how defect lines act on local operators. The spin field $\sigma$ and disorder field $\mu$ are exchanged by Kramers–Wannier duality. In a defect picture, crossing a duality line changes the kind of local field inserted.

Very schematically,

$$
\mathcal N\text{ crossing }\sigma
\quad\leadsto\quad
\mu,
$$

and conversely. But the complete statement requires specifying which side of the defect the operator lives on and which defect-changing field appears at the junction. This is not a bug; it is the lesson. Non-invertible defects do not simply act as functions on the set of local operators. They can create sums, junction sectors, and defect-local operators.

A group-like symmetry line gives an automorphism of the local operator algebra. A non-invertible line gives a more general operation: it maps local data into a defect-decorated or sector-decomposed space.

## Potts and parafermion examples

The $Q$-state Potts models, especially the three-state Potts critical point, provide the next family of examples. Their ordinary symmetry can be non-Abelian or discrete, and their dualities can be topological at criticality.

The three-state critical Potts model is related to the $\mathbb Z_3$ parafermion CFT. It has order and disorder fields, duality transformations, and defect lines whose fusion is richer than the Ising case. The moral is similar:

$$
\text{duality defect}\times\text{duality defect}
=
\text{sum of symmetry defects}.
$$

For a finite Abelian group $A$, this pattern is captured by Tambara–Yamagami fusion:

$$
\mathcal N\otimes\mathcal N
\simeq
\bigoplus_{a\in A}U_a.
$$

For $A=\mathbb Z_2$ this is Ising. For $A=\mathbb Z_3$ and related settings, it captures the basic shape of Abelian order-disorder duality. The associators and phases matter; the fusion rule alone is not the full theory.

## Orbifolds and quantum symmetry

Orbifolds are one of the most reliable machines for producing non-invertible defects.

Start with a two-dimensional QFT $\mathcal T$ with a finite non-anomalous group symmetry $G$. Gauging produces an orbifold theory

$$
\mathcal T/G.
$$

In the defect-network description, one allows topological $G$ symmetry lines to fluctuate. The object condensed in $\mathcal T$ is the regular algebra

$$
A_G=\bigoplus_{g\in G}U_g.
$$

The gauging interface from $\mathcal T$ to $\mathcal T/G$ can be composed with its reverse. That composition is generally not a single invertible defect; it is a sum of sectors. This is the seed of non-invertibility.

For Abelian $G$, the orbifold often has a dual quantum symmetry $\widehat G$. For non-Abelian $G$, the dual structure is more naturally categorical. It involves twisted sectors, representation labels, and defects whose fusion reflects the representation theory and conjugacy structure of $G$ rather than a simple dual group.

Thus even ordinary group gauging can lead to non-invertible symmetry in the gauged theory.

## Rational CFT and Verlinde defects

In rational CFT, the category of topological defects can be computed with remarkable precision. In diagonal rational CFTs, there are topological defects labeled by primary fields $a$, and their fusion often follows the same fusion coefficients as the chiral algebra:

$$
\mathcal D_a\otimes\mathcal D_b
\simeq
\bigoplus_c N_{ab}{}^c\,\mathcal D_c.
$$

The coefficients $N_{ab}{}^c$ are the Verlinde fusion coefficients. If $a$ is a simple current, $\mathcal D_a$ is invertible. If $a$ is not a simple current, $\mathcal D_a$ is typically non-invertible.

The operator on a bulk primary sector $i$ is diagonal in many simple examples:

$$
\widehat{\mathcal D}_a|_{\mathcal H_i}
=
\frac{S_{ai}}{S_{0i}}\,\mathrm{id}_{\mathcal H_i},
$$

where $S$ is the modular $S$-matrix. This formula is convention-dependent and assumes a diagonal rational CFT setup, but it is an excellent illustration: topological defects act on Hilbert-space sectors by numbers determined by modular data.

:::note[Source note: Verlinde-line normalization]
Different RCFT sources normalize defect operators and modular data differently. The robust statement is that topological defect fusion is governed by the same fusion algebra encoded by the modular $S$-matrix in the diagonal rational case.
:::

## WZW models

Wess–Zumino–Witten models give a large and structured class of examples. A WZW model based on a compact Lie group $G$ at level $k$ has chiral algebra $\widehat{\mathfrak g}_k$. Its integrable highest-weight representations label primary fields.

Topological defects preserving the full chiral algebra are labeled by integrable representations, and their fusion is governed by the affine fusion rules. Schematically,

$$
\mathcal D_\lambda\otimes\mathcal D_\mu
\simeq
\bigoplus_\nu N_{\lambda\mu}{}^\nu\,\mathcal D_\nu.
$$

The invertible defects correspond to simple currents. The remaining defects are non-invertible. For example, in $SU(2)_k$ WZW models, most representation labels do not define invertible defects. Their fusion resembles truncated spin addition.

WZW examples are useful because they show that non-invertible symmetry is not a curiosity of the Ising model. It appears naturally in the most symmetric 2D CFTs.

## Minimal models and ADE structure

Virasoro minimal models also contain rich topological defect spectra. The unitary minimal models include the Ising model and tricritical Ising model. Their topological defects can be organized by the same labels that organize primary fields, with additional structure depending on modular invariants.

ADE classifications appear in several related settings: modular invariants, boundary conditions, and defect systems. The details belong to CFT and Bootstrap, but the message for symmetry is simple:

$$
\text{2D CFT consistency data}
\quad\Rightarrow\quad
\text{topological defect fusion data}.
$$

Non-invertible symmetry is therefore not an extra decoration added after solving a CFT. In many rational theories it is already built into the exact operator and modular data.

## Lattice statistical models

The continuum topological defects of a critical 2D QFT often have lattice ancestors.

In the Ising model, the spin-flip line can be implemented by changing signs of couplings along a curve. Kramers–Wannier duality can be implemented by a duality wall. At criticality, these defects become topological in the scaling limit.

This is pedagogically important because it demystifies topological lines. A topological defect is not necessarily a mysterious continuum object. It may descend from a lattice operation whose position can be moved by local transformations at criticality.

The lattice viewpoint also teaches a warning. Away from criticality, a defect may fail to be topological. It can acquire tension or depend on its shape. Non-invertible symmetry as a topological symmetry is usually a property of a special point, phase, or topological subsector.

## What these examples teach

The examples above teach four durable lessons.

First, **non-invertible symmetry is common in 2D**. Ising, Potts, WZW, minimal-model, rational-CFT, and orbifold examples all produce it naturally.

Second, **duality is a source of non-invertibility**. If gauging or dualizing a theory returns an equivalent theory, the duality interface becomes a self-defect. Its square often produces a sum over symmetry defects.

Third, **fusion rules are not the full data**. The Ising rule $\mathcal N^2=1+\eta$ is memorable, but complete defect-network calculations also need junction spaces, associators, orientations, and defect-local operators.

Fourth, **2D examples are laboratories, not cages**. The same ideas motivate higher-dimensional non-invertible defects, condensation surfaces, symmetry TFT, and generalized charges. The categorical language is sharpest in two dimensions, but the physical questions are broader.

## Common pitfalls

**“The Ising example is the whole subject.”** It is the best first example, not the endpoint. WZW models, orbifolds, minimal models, and non-rational QFTs greatly enlarge the landscape.

**“Fusion rules determine all correlators.”** Fusion rules constrain defect networks, but correlators also need junction data, defect-local operator spectra, OPE coefficients, and normalization choices.

**“A duality defect acts like a permutation of fields.”** Sometimes it exchanges familiar order and disorder fields, but generally it maps local data into defect sectors or sums. It need not be an automorphism of the local operator algebra.

**“All topological defects in RCFT are invertible.”** Only simple-current defects are invertible in the usual rational examples. Most topological defects are non-invertible.

**“Orbifolding destroys symmetry.”** Gauging an ordinary symmetry can remove that symmetry as a global symmetry, but it can create a dual or categorical symmetry in the orbifold theory.

## Relations to other pages

[Tambara–Yamagami Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/tambara-yamagami-preview/) abstracts the Ising and Abelian-duality pattern. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) explains why orbifolds naturally produce non-invertible defect data. [Categorical Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/categorical-symmetry/) gives the language needed to organize these examples systematically.

The CFT and Bootstrap volume is the proper home for detailed minimal-model, WZW, modular tensor category, and boundary-CFT calculations. This page only extracts the symmetry lesson.

## Research status

Two-dimensional rational examples are well established. The Ising, Potts, WZW, minimal-model, and orbifold defect stories are standard reference points in the physics of non-invertible symmetry.

Active directions include non-rational CFT, nonsemisimple logarithmic CFT, fermionic refinements, lattice realizations away from criticality, categorical anomalies, interfaces between different 2D theories, and the use of 2D examples as boundary conditions or test cases for symmetry TFT.

## Exercises

### Exercise 1: Ising quantum dimension

Using

$$
\mathcal N^2=1+\eta,
\qquad
d_1=d_\eta=1,
$$

compute $d_{\mathcal N}$.

<details><summary><strong>Solution</strong></summary>

Quantum dimensions multiply under fusion and add under direct sums. Therefore

$$
d_{\mathcal N}^2=d_1+d_\eta=2.
$$

Thus

$$
d_{\mathcal N}=\sqrt2.
$$

Since an invertible defect has quantum dimension $1$, $\mathcal N$ is not invertible.

</details>

### Exercise 2: Simple currents and invertibility

In a diagonal rational CFT, suppose a defect $\mathcal D_a$ obeys

$$
\mathcal D_a\otimes\mathcal D_b\simeq \mathcal D_c
$$

for every simple defect $\mathcal D_b$, with no sums and with a permutation of labels $b\mapsto c$. Why is $\mathcal D_a$ a candidate invertible defect?

<details><summary><strong>Solution</strong></summary>

If fusion by $\mathcal D_a$ permutes simple defects, then it behaves like multiplication by a group element on the set of simples. In particular, there is a label $a^{-1}$ such that fusion by $\mathcal D_{a^{-1}}$ reverses this permutation. Then one expects

$$
\mathcal D_a\otimes\mathcal D_{a^{-1}}\simeq 1.
$$

In RCFT language such defects are associated with simple currents. One still needs the full category data to check orientations and associators, but the fusion pattern is the diagnostic.

</details>

### Exercise 3: Orbifold origin of non-invertibility

Let $G$ be a finite group symmetry of a 2D QFT. Explain why the object

$$
A_G=\bigoplus_{g\in G}U_g
$$

is generally not invertible when $|G|>1$.

<details><summary><strong>Solution</strong></summary>

The quantum dimension of each invertible group defect $U_g$ is $1$. The direct sum has quantum dimension

$$
d_{A_G}=\sum_{g\in G}d_{U_g}=|G|.
$$

An invertible simple defect must have quantum dimension $1$. For $|G|>1$, $A_G$ has dimension greater than $1$ and is a sum of multiple sectors. It is therefore not an invertible simple defect. This is why gauging interfaces and orbifold defects naturally lead beyond group-like symmetry.

</details>

## References

- Petkova and Zuber, papers on generalized twisted partition functions and defect lines in rational CFT.
- Fuchs, Runkel, and Schweigert, papers on topological defects, boundary CFT, and Frobenius algebras in rational CFT.
- Runkel, “Perturbed Defects and T-Systems in Conformal Field Theory,” for concrete defect-fusion methods.
- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, for minimal models, modular data, WZW models, and the Ising/Potts context.
- Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries,” for modern physics-oriented examples.
- Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” for the connection to generalized symmetry and symmetry TFT.

## Version history

- 2026-06-20: Initial polished draft. Added 2D examples of non-invertible symmetry from Ising, Potts/parafermion models, orbifolds, rational CFT, WZW models, minimal models, and lattice statistical systems.
