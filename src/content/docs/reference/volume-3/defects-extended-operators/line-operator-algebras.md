---
title: "Line-Operator Algebras"
description: "Explains how line operators form algebraic structures under fusion, braiding, screening, endpoints, electric-magnetic charge lattices, and one-form symmetry actions."
sidebar:
  label: "Line-Operator Algebras"
  order: 11
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Ch. 7; Srednicki §82; Schwartz §25.2; Aharony–Seiberg–Tachikawa; Kapustin–Seiberg; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - line operators
  - Wilson lines
  - "’t Hooft lines"
  - dyonic lines
  - one-form symmetry
  - charge lattices
  - mutual locality
  - operator algebra
canonicalTopics:
  - line-operator-algebra
  - wilson-thooft-line
  - electric-magnetic-charge-lattice
  - one-form-symmetry
  - mutual-locality
researchStatus:
  established:
    - "Line operators and their fusion, screening, endpoint, and linking data are standard tools in gauge theory, topological field theory, conformal field theory, and generalized-symmetry language."
    - "In four-dimensional gauge theories, the allowed spectrum of Wilson, ’t Hooft, and Wilson–’t Hooft lines is part of the global definition of the theory, not merely a decorative observable."
  active:
    - "Line-operator algebras in non-invertible, non-semisimple, fermionic, fractonic, relative, and higher-categorical settings remain active research areas."
---

## Summary

A **line-operator algebra** is the algebraic structure formed by line operators under operations such as fusion, orientation reversal, braiding, endpoint attachment, screening, and action by surface symmetry operators. It is not always an algebra in the elementary linear-algebra sense. Depending on the theory, it may be a representation ring, a braided tensor category, a charge lattice with a pairing, a skein algebra, a category of boundary conditions, or a non-topological operator product expansion with anomalous dimensions.

The simplest mental model is this:

$$
\text{line operators} \quad + \quad \text{fusion} \quad + \quad \text{linking/braiding data}
\quad = \quad \text{line-operator algebra}.
$$

For Wilson lines in a weakly coupled gauge theory, fusion often begins as tensor product of representations:

$$
W_R(C)\,W_S(C)
\sim
\sum_T N_{RS}{}^T W_T(C),
$$

where $N_{RS}{}^T$ are tensor-product multiplicities. For Wilson–’t Hooft lines in four-dimensional gauge theory, the labels include electric and magnetic charges, and consistency requires mutual-locality conditions. For topological lines in two- or three-dimensional TQFT, fusion and braiding may become exact finite algebraic data.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Schematic showing line operators labeled by electric and magnetic charges, fusion as addition of charges, and mutual locality as an antisymmetric pairing.](/figures/symmetry-anomalies-topology/line-operator-algebra-schematic.svg)

<figcaption>

A line-operator algebra records which line labels are allowed, how they fuse, which lines can end or be screened, and what phases or obstructions appear when lines are linked or braided. In four-dimensional gauge theory, Wilson–’t Hooft lines are often organized by an electric–magnetic charge lattice with a Dirac pairing.

</figcaption>
</figure>

This page is the last page of the Defects and Extended Operators chapter. It prepares the next chapters: higher-form symmetries, non-invertible symmetries, symmetry TFT, and TQFT.

## Prerequisites

You should know [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/), [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/), [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), and [Defect Correlation Functions](/symmetry-anomalies-topology/defects-extended-operators/defect-correlation-functions/).

You should also be comfortable with representation labels, tensor products, gauge-group centers, and the idea that an extended operator can be genuine or can require an endpoint, boundary, or attached surface to be gauge invariant.

## Core idea

A local operator algebra is built from local products and OPEs. A line-operator algebra is built from extended analogues.

There are several operations one can perform on line operators:

| Operation | Meaning |
|---|---|
| Fusion | Bring two parallel or coincident lines together. |
| Orientation reversal | Reverse the direction of the line. |
| Braiding or linking | Move one line around another, or link it with a surface. |
| Endpoint attachment | Allow the line to end on a local, boundary, or defect operator. |
| Screening | Declare two lines equivalent if they differ by dynamical charges. |
| Symmetry action | Surround or link a line by a topological surface operator. |
| Junction formation | Let several lines meet at a point or at a defect-local operator. |

The “algebra” is the collection of rules telling us which of these operations are allowed and what their results are.

For ordinary Wilson lines in a gauge theory, the first approximation is representation theory. If two Wilson lines in representations $R$ and $S$ run along the same curve, then their product is governed by

$$
R\otimes S=\bigoplus_T N_{RS}{}^T T.
$$

This suggests the line fusion rule

$$
W_R\times W_S=\sum_T N_{RS}{}^T W_T.
$$

That formula is clean in a topological or purely representation-theoretic limit. In a dynamical non-topological gauge theory, coincident Wilson lines may require renormalization, can mix with defect-local operators, and can have cusp or endpoint divergences. The representation-ring rule is the algebraic skeleton; the QFT supplies the analytic flesh.

## Setup and notation

A line operator supported on an oriented curve $C$ is written $L_a(C)$, where $a$ denotes whatever labels the theory requires: a representation, an electric charge, a magnetic charge, a framing, a spin label, a topological-sector label, or a categorical object.

A Wilson line in representation $R$ is schematically

$$
W_R(C)=\operatorname{tr}_R P\exp\left(i\int_C A\right),
$$

with any gauge coupling absorbed into $A$ unless stated otherwise. A magnetic line, or ’t Hooft line, is defined by a prescribed singularity of the gauge field around $C$. A Wilson–’t Hooft line carries both types of data and is written schematically as

$$
L_{(e,m)}(C),
$$

where $e$ is an electric label and $m$ is a magnetic label.

The notation $e,m$ is intentionally schematic. In a non-Abelian theory, they are not simply two integers. They live in weight, coweight, root, coroot, or quotient lattices, with Weyl-group identifications and global-form constraints.

:::note[Source note]
In four-dimensional gauge theory, line operators are part of the global definition of the theory. The same Lie algebra and the same local Lagrangian can admit distinct choices of genuine line operators. This is the main lesson of the “reading between the lines” viewpoint.
:::

## Genuine lines and lines with endpoints

A **genuine line operator** can be inserted on a closed curve, or on an open curve with endpoints only at boundaries or explicitly specified endpoint operators, without requiring an attached higher-dimensional sheet. A line that needs an attached surface is still useful, but it is not genuine in the same sense.

This distinction is essential for global symmetry. Higher-form symmetries act on genuine extended operators. If a line can end on a dynamical local operator, its charge under a one-form symmetry is screened.

For example, in a gauge theory with dynamical matter in representation $R$, a Wilson line in $R$ may end on a dynamical charged field. Such a line is not a conserved charged object for a one-form symmetry. In contrast, if no dynamical field can screen a particular center charge, Wilson lines carrying that charge can be genuine charged objects under a center one-form symmetry.

The slogan is:

$$
\text{unscreened genuine lines carry one-form charge}.
$$

Lines that differ by attaching dynamical particles can represent the same superselection class. This is why the line-operator algebra depends not only on the gauge group but also on the matter content.

## Fusion of Wilson lines

For Wilson lines, the cleanest fusion rule comes from tensor products of representations. If $R$ and $S$ are representations of a compact gauge group, then

$$
W_R\times W_S
\sim
W_{R\otimes S}
=
\sum_T N_{RS}{}^T W_T.
$$

For $SU(2)$, the familiar Clebsch–Gordan rule gives

$$
W_{j_1}\times W_{j_2}
=
\sum_{j=|j_1-j_2|}^{j_1+j_2} W_j,
$$

where $j$ increases in integer steps. For the fundamental $j=1/2$ line,

$$
W_{1/2}\times W_{1/2}=W_0+W_1.
$$

This equation does not say that two heavy external probes literally become a superposition of particles in a dynamical scattering process. It says that the coincident Wilson-line insertion decomposes into irreducible representation channels.

In a non-topological theory, the word “sim” hides regularization. Coincident lines can generate defect-local counterterms and divergent perimeter or cusp contributions. In a topological theory, the same formula can become an exact fusion rule.

## Orientation reversal and dual lines

Reversing the orientation of a Wilson line turns a representation into its dual:

$$
W_R(C^{-1})=W_{R^*}(C).
$$

For a $U(1)$ line of electric charge $q$, orientation reversal sends

$$
q\mapsto -q.
$$

For a Wilson–’t Hooft line,

$$
(e,m)\mapsto (-e,-m)
$$

in the simplest Abelian convention. In non-Abelian theories, duals, Weyl identifications, charge conjugation, and possible discrete theta data must be handled carefully.

The orientation-reversed line is not always an inverse under fusion. A line has an inverse only if fusing it with its reverse gives exactly the identity line. Most Wilson lines do not have inverses; they are not symmetry defects. They are charged probes.

## Electric and magnetic charge lattices

In four-dimensional gauge theory, a line can carry electric and magnetic labels. In Abelian notation, a dyonic line has charge

$$
\gamma=(e,m).
$$

Fusion of parallel dyonic lines adds charges:

$$
L_{(e,m)}\times L_{(e',m')}\sim L_{(e+e',m+m')}.
$$

The important extra structure is the antisymmetric Dirac pairing

$$
\langle (e,m),(e',m')\rangle
=em'-e'm.
$$

The mutual-locality condition is that this pairing be integral in appropriate units:

$$
\langle \gamma,\gamma'\rangle\in\mathbb Z.
$$

In non-Abelian theories the same idea becomes a pairing between electric and magnetic weight-type lattices, modulo Weyl transformations and quotient data. A maximal set of mutually local genuine lines is a choice of line-operator spectrum. Changing that choice can produce distinct QFTs with the same local Lie algebra.

:::note[Convention-sensitive normalization]
Some authors put factors of $2\pi$, gauge couplings, or signs into the definition of electric and magnetic charges. This page uses the abstract pairing notation because the invariant statement is integrality of the properly normalized Dirac pairing, not the placement of $2\pi$ in a particular convention.
:::

## Global form of the gauge group

The global form of the gauge group controls which Wilson lines are genuine. The Lie algebra does not suffice.

For example, gauge theories locally based on $\mathfrak{su}(N)$ can have gauge group $SU(N)$ or $PSU(N)=SU(N)/\mathbb Z_N$. They have the same local gluons and the same local Lie algebra, but different genuine line operators.

In an $SU(N)$ theory without matter screening the center, fundamental Wilson lines are allowed genuine Wilson lines. In a $PSU(N)$ theory, fundamental Wilson lines are not honest Wilson lines of the gauge group; magnetic or dyonic lines are correspondingly reorganized. The precise allowed lattice of lines depends on the quotient and on discrete theta-like choices.

This is why line operators are not an afterthought. They can distinguish theories that local operators on $\mathbb R^4$ may not distinguish.

## One-form symmetry action

A one-form symmetry acts on line operators. The symmetry operator is supported on a closed codimension-two surface $\Sigma$ in four dimensions, or more generally on a codimension-$q+1$ surface for a $q$-form symmetry.

If $U_\alpha(\Sigma)$ is a one-form symmetry operator and $L_\gamma(C)$ is a line operator, then linking produces a phase or representation action:

$$
\left\langle U_\alpha(\Sigma)L_\gamma(C)\cdots\right\rangle
=
\chi_\gamma(\alpha)^{\operatorname{Link}(\Sigma,C)}
\left\langle L_\gamma(C)\cdots\right\rangle.
$$

For an Abelian one-form symmetry, $\chi_\gamma$ is a character. The line label $\gamma$ is the one-form charge. If $L_\gamma$ can end on a dynamical object, the charge is not conserved, and the one-form symmetry is explicitly broken or screened.

This is the bridge from the present chapter to Higher-Form and Generalized Symmetries. The line-operator algebra tells us what the charged objects are.

## Braiding, linking, and commutation

Line operators do not always commute in a naive sense. The meaning depends on dimension.

In three-dimensional spacetime, two lines can braid. The exchange can be detected by a braiding matrix or phase. In Chern–Simons theory, this braiding data is part of the modular tensor category of lines.

In four-dimensional spacetime, two closed loops generally do not braid in the same way, but lines can link with surfaces, and electric and magnetic lines can have nontrivial angular-momentum or Dirac-pairing effects. Equal-time versions of line operators can obey commutation relations determined by linking numbers.

A schematic relation is

$$
L_\gamma(C)L_{\gamma'}(C')
=
\exp\left(2\pi i\,\langle\gamma,\gamma'\rangle\,\operatorname{Link}(C,C')\right)
L_{\gamma'}(C')L_\gamma(C),
$$

when the geometry and dimension make this expression meaningful. The formula is a mnemonic, not a universal law: dimensions, framings, orientations, boundary conditions, and the type of theory determine the correct relation.

## Line junctions and defect-local operators

A line algebra is not only fusion of closed loops. Lines can meet at junctions. A junction of lines $L_a,L_b,L_c$ is a local operator living at the meeting point of line defects.

If the fusion rule contains $L_c$ in $L_a\times L_b$, then there may be a junction operator implementing

$$
L_a\otimes L_b\to L_c.
$$

The space of such junction operators is part of the line algebra. In a semisimple topological setting, its dimension may be the fusion multiplicity $N_{ab}{}^c$. In a general QFT, junction operators can have scaling dimensions, spin, charges under residual symmetries, and their own OPEs along the defect network.

Thus the more accurate structure is not merely a set of lines with multiplication. It is a web of lines, junctions, local operators on the lines, and correlation functions of their networks.

## Screening and equivalence classes

Suppose a Wilson line $W_R$ can end on a dynamical field in representation $R$. Then a segment of $W_R$ can be created or annihilated by local dynamical processes. Such a line is screened.

Screening identifies line labels modulo charges carried by dynamical matter. If the gauge group has center $Z(G)$, the surviving one-form symmetry is often a subgroup of the Pontryagin dual of the unscreened center charges. For example, fundamental matter in an $SU(N)$ gauge theory screens fundamental Wilson lines and breaks the electric center one-form symmetry.

This is why line-operator algebras depend on matter content. Pure Yang–Mills theory and Yang–Mills theory with fundamental quarks do not have the same genuine Wilson-line charge structure, even if the gauge boson Lagrangian looks the same.

## Topological line categories

In a topological theory, line operators can form a category rather than merely a ring. The objects are line types, morphisms are junction or defect-local operators, tensor product is fusion, and braiding records the effect of exchanging lines.

In a two-dimensional CFT, topological defect lines may form a fusion category. In a three-dimensional TQFT, topological line operators may form a braided tensor category, and in a fully extended framed theory one often expects richer higher-categorical structure.

The decategorified shadow of this structure is the fusion ring:

$$
[L_a][L_b]=\sum_c N_{ab}{}^c[L_c].
$$

Decategorification remembers multiplicities but forgets the actual spaces of junctions, associators, braiding maps, and coherence data. For many physics calculations the fusion ring is enough. For anomaly, boundary, non-invertible, and symmetry-TFT questions, the missing categorical data can be decisive.

## Examples

### Wilson lines in pure Yang–Mills

In a pure $SU(N)$ Yang–Mills theory, Wilson lines are labeled by representations of $SU(N)$. The center charge, or $N$-ality, of a representation controls its charge under the electric $\mathbb Z_N$ one-form symmetry. Tensor product adds $N$-ality modulo $N$.

A fundamental Wilson line has nontrivial $N$-ality. If there is no fundamental dynamical matter, it cannot end on a local dynamical field. It is therefore a genuine charged line under the center one-form symmetry.

### Gauge theory with fundamental matter

Add dynamical fundamental matter. Now a fundamental Wilson line can end on a fundamental field insertion, after appropriate gauge-invariant dressing. The electric center one-form symmetry is explicitly broken. The line-operator algebra is correspondingly quotiented by screening.

This is the line-operator version of a familiar physical fact: external charges can be screened by dynamical matter.

### Abelian Maxwell theory

In four-dimensional compact $U(1)$ gauge theory, idealized Wilson–’t Hooft lines can be labeled by integer electric and magnetic charges:

$$
(e,m)\in\mathbb Z\oplus\mathbb Z.
$$

Fusion adds the pair, while mutual locality is controlled by

$$
em'-e'm.
$$

Depending on the spectrum of dynamical electric or magnetic charges, the genuine unscreened line algebra may be reduced by screening.

### Chern–Simons theory

In Chern–Simons theory, Wilson lines are topological after choosing framing data. The allowed line labels are integrable representations at level $k$ for compact simple examples. Fusion is not the ordinary tensor product of finite-dimensional representations; it is truncated by the level. Braiding and framing phases are part of the data.

This example is the cleanest place to see why “line algebra” really wants categorical language.

## Common pitfalls

**“The line algebra is just the representation ring.”** Sometimes it starts that way, especially for Wilson lines. But magnetic lines, dyonic lines, screening, braiding, framing, endpoints, discrete theta angles, and topological sectors can change the answer.

**“The Lie algebra determines the lines.”** No. The global form of the gauge group and the allowed line spectrum are extra data. Theories with the same local Lie algebra can have different genuine line operators.

**“Every Wilson line is genuine.”** A Wilson line may fail to be a genuine operator if it requires an attached surface, or it may be screenable if it can end on dynamical matter.

**“Fusion means a dynamical physical process.”** Fusion is an operator operation. It describes how coincident insertions decompose, not necessarily a real-time scattering event.

**“Topological line algebra applies to every line.”** Most line operators in ordinary QFT are not topological. Their coincident limits can involve anomalous dimensions, cusp divergences, and defect-local renormalization.

**“The fusion ring contains all information.”** The ring forgets junction spaces, associators, braiding, twists, framings, and higher morphisms. Those data matter in TQFT and non-invertible symmetry.

## Relations to other pages

[Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) introduces the fusion operation for general defects. This page specializes to lines and adds electric/magnetic charge lattices, screening, endpoints, and one-form symmetry action.

[Defect Correlation Functions](/symmetry-anomalies-topology/defects-extended-operators/defect-correlation-functions/) explains how line correlators depend on linking, framing, and support geometry.

[Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) and [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) give the two basic families of line operators. The present page explains why their allowed joint spectrum is part of the definition of the QFT.

[Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) uses genuine line operators as charged objects under one-form symmetries. [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) upgrades the line-fusion viewpoint into categorical symmetry. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) packages many line and surface data into a bulk topological theory.

## Research status

The basic physics of Wilson lines, ’t Hooft lines, screening, and center symmetry is established. The modern viewpoint that the allowed set of genuine line operators is part of the global definition of a gauge theory is also standard in current high-energy theory.

The active frontier is the generalization of line-operator algebras beyond semisimple bosonic examples: non-invertible lines, fermionic lines, nonsemisimple categories, noncompact theories, defects in higher dimensions, relative QFTs, subsystem symmetries, and the interplay with symmetry TFT. In those settings, “algebra” is often only the visible shadow of a higher categorical structure.

## Exercises

### Exercise 1: Wilson-line fusion in SU(2)

Use the $SU(2)$ tensor-product rule to compute

$$
W_{1/2}\times W_1.
$$

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
j_1\otimes j_2
=
\bigoplus_{j=|j_1-j_2|}^{j_1+j_2} j,
$$

with $j$ increasing in integer steps. With $j_1=1/2$ and $j_2=1$,

$$
\frac12\otimes 1=\frac12\oplus\frac32.
$$

Therefore

$$
W_{1/2}\times W_1=W_{1/2}+W_{3/2}
$$

in the representation-ring approximation.

</details>

### Exercise 2: Dirac pairing

Let two Abelian dyonic lines have charges

$$
\gamma=(2,1),
\qquad
\gamma'=(1,3).
$$

Compute the antisymmetric pairing

$$
\langle (e,m),(e',m')\rangle=em'-e'm.
$$

<details><summary><strong>Solution</strong></summary>

Substitute $e=2$, $m=1$, $e'=1$, and $m'=3$:

$$
\langle\gamma,\gamma'\rangle
=2\cdot3-1\cdot1=6-1=5.
$$

The two lines are mutually local in the simple normalization where the condition is integrality of the pairing.

</details>

### Exercise 3: Screening by matter

Explain why adding dynamical fundamental matter to an $SU(N)$ gauge theory destroys the electric $\mathbb Z_N$ one-form symmetry detected by fundamental Wilson lines.

<details><summary><strong>Solution</strong></summary>

The electric $\mathbb Z_N$ one-form symmetry acts on Wilson lines according to their center charge, or $N$-ality. In pure $SU(N)$ Yang–Mills theory, a fundamental Wilson line cannot end on a local dynamical field, so it is a genuine charged line.

After adding dynamical fundamental matter, the fundamental Wilson line can end on a dynamical fundamental field insertion, with appropriate gauge-invariant dressing. Its charge is no longer conserved as an unscreened line charge. The would-be one-form symmetry is therefore explicitly broken by the dynamical matter.

</details>

### Exercise 4: Fusion ring versus category

What information is lost when one replaces a category of topological lines by its fusion ring?

<details><summary><strong>Solution</strong></summary>

The fusion ring remembers only the formal multiplication rule

$$
[L_a][L_b]=\sum_c N_{ab}{}^c[L_c].
$$

It forgets the actual vector spaces of junction operators, associators, braiding maps, twists, framings, duality maps, and higher coherence data. Those data are invisible in the decategorified ring but can be physically important, especially for braiding, anomalies, boundaries, and non-invertible symmetry.

</details>

## References

- Wilson, “Confinement of Quarks,” for Wilson loops as gauge-theory probes.
- Polyakov, *Gauge Fields and Strings*, especially Ch. 7 on non-Abelian phase factors and loop dynamics.
- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice theory, and confinement orientation.
- Schwartz, *Quantum Field Theory and the Standard Model*, §25.2, for gauge invariance and Wilson lines.
- Aharony, Seiberg, and Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for the modern view that allowed line operators are part of the global definition of a four-dimensional gauge theory.
- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for changing operator spectra, topological couplings, and global-form data.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for line operators as charged objects under one-form symmetries and for the background-field/gauging viewpoint.

## Version history

- **2026-06-20:** Initial polished draft. Added fusion, orientation, electric/magnetic charge lattices, mutual locality, global-form dependence, screening, one-form symmetry action, topological line categories, examples, and exercises.
