---
title: "Gauging Finite Symmetries"
description: "Explains finite-symmetry gauging in low-dimensional QFT as projection plus twisted sectors, or equivalently as a sum over flat bundles and topological-defect networks."
sidebar:
  label: "Gauging Finite Symmetries"
  order: 4
level: Advanced
status: "Polished draft"
source: "Dijkgraaf–Witten; Dixon–Harvey–Vafa–Witten; Ginsparg; Kapustin–Seiberg; Carqueville–Runkel; standard orbifold and finite-gauge-theory references."
topics:
  - finite symmetry gauging
  - orbifolds
  - twisted sectors
  - topological defects
  - discrete torsion
  - quantum symmetry
canonicalTopics:
  - finite-symmetry-gauging
  - orbifold
  - flat-bundle-sum
  - twisted-sector
  - discrete-torsion
researchStatus:
  established:
    - "Gauging a non-anomalous finite global symmetry is a standard construction in two-dimensional QFT, orbifold CFT, finite gauge theory, lattice models, and topological field theory."
    - "In two dimensions, finite gauging is concretely implemented by projection onto invariant states together with twisted sectors, or equivalently by summing over flat finite-group bundles."
  active:
    - "Modern generalized-symmetry language formulates finite gauging using topological defect networks, condensation, algebra objects, quantum symmetries, and SymTFT boundary conditions."
---

## Summary

To **gauge a finite global symmetry** is to make the symmetry local without introducing a propagating continuous gauge boson. In low-dimensional QFT this operation is everywhere: orbifolds, Ising duality, Dijkgraaf–Witten theory, finite gauge theories, symmetry twists, and non-invertible duality defects all use it.

For a theory $T$ with a finite non-anomalous symmetry group $G$, the gauged theory is often denoted

$$
T/G.
$$

In two-dimensional language, this means two things:

$$
\text{finite gauging}
=
\text{projection onto invariant states}
+
\text{twisted sectors}.
$$

On a torus, the same statement becomes a sum over commuting holonomies,

$$
Z_{T/G}(\tau)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}}
Z_{g,h}(\tau),
$$

possibly modified by discrete-torsion phases. Here $Z_{g,h}$ is the partition function with a $g$ twist around one cycle and an $h$ twist around the other.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Diagram showing finite-symmetry gauging as three equivalent descriptions: projection plus twisted sectors, sum over flat G bundles, and sum over topological defect networks.](/figures/symmetry-anomalies-topology/finite-symmetry-gauging.svg)

<figcaption>

Three equivalent views of finite-symmetry gauging. In Hamiltonian language, one projects and adds twisted sectors. In path-integral language, one sums over flat $G$ bundles. In defect language, one sums over networks of topological symmetry lines. The equality of these pictures is one reason two-dimensional finite gauging is such a useful laboratory.

</figcaption>
</figure>

The construction is simple to state but easy to misuse. Projection alone is not gauging. Twisted sectors are not optional. An anomalous finite symmetry cannot be gauged without extra bulk degrees of freedom or inflow. Nonabelian finite groups require centralizers and conjugacy classes rather than independent labels $g,h$.

## Prerequisites

You should know [Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/), [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/), [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/), and [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/). You should also know the ordinary distinction between global symmetry and gauge redundancy.

The page is written for ordinary finite zero-form symmetries. Higher-form finite gauging follows the same logic but replaces flat $G$ bundles by higher-form background fields and changes the degree of the dual symmetry.

## Core idea

Let $T$ be a QFT with a finite global symmetry group $G$. A background gauge field for $G$ is not a small Lie-algebra-valued one-form. It is a flat finite-group gauge field: a choice of transition functions, holonomies, or branch cuts valued in $G$.

The background-field partition function is

$$
Z_T[M,A],
$$

where $A$ is a flat $G$ background on spacetime $M$. Gauging means summing over such backgrounds:

$$
Z_{T/G}[M]
=
\sum_{[A]} w(A) Z_T[M,A].
$$

The weight $w(A)$ includes the correct groupoid normalization and any allowed topological counterterm. For a finite group, a careful normalization divides by automorphisms of the bundle. Physicists often suppress this detail in simple torus formulas, but it is important for cutting, gluing, and matching to Dijkgraaf–Witten theory.

In two-dimensional CFT, the same sum becomes the familiar orbifold construction. On a spatial circle, the Hilbert space has twisted sectors $\mathcal H_g$ satisfying

$$
\Phi(x+2\pi)=g\cdot\Phi(x).
$$

The gauged Hilbert space is schematically

$$
\mathcal H_{T/G}
=
\bigoplus_{[g]} \mathcal H_g^{C(g)},
$$

where $[g]$ runs over conjugacy classes and $C(g)$ is the centralizer of $g$. For abelian $G$ this simplifies to

$$
\mathcal H_{T/G}
=
\bigoplus_{g\in G}\mathcal H_g^G.
$$

That formula is the cleanest antidote to the common mistake “gauging means keeping only invariant states.” Keeping invariants is only the untwisted-sector projection. Gauging also sums over nontrivial finite gauge fields, which appear as twisted sectors.

## Defect-network picture

For a finite symmetry, each $g\in G$ can be represented by a topological symmetry line $U_g$. Crossing the line acts by $g$ on fields and operators. Gauging $G$ can be described by summing over networks of these topological lines.

In a lattice path integral, this network picture is extremely concrete. Put a $G$ variable on edges of a triangulation or cell decomposition. Flatness imposes that the product around each plaquette is trivial. Matter fields couple to these edge variables. Summing over the edge variables is the finite-gauge-field path integral.

In a continuum defect picture, the Poincaré dual of the finite gauge field is a network of symmetry defects. Changing triangulation corresponds to sliding, fusing, and resolving the topological lines. Consistency of these moves is precisely the topological condition that the gauging operation is well defined.

This viewpoint is powerful because it generalizes. Ordinary finite gauging is only the group-like case. Generalized gauging replaces the sum over group defects by condensation of a more general algebra object in the defect category. That is the doorway to non-invertible symmetry.

:::note[Source note]
In ordinary orbifold CFT, one usually writes the gauging operation as a sector sum. In modern defect language, the same operation is the insertion and condensation of a network of topological symmetry lines. These are not competing definitions; they are complementary pictures of the same finite-gauge-field sum.
:::

## Projection and twisted sectors

In Hamiltonian language, the first step is projection. If the ungauged Hilbert space on a circle is $\mathcal H$, the invariant subspace is

$$
\mathcal H^G
=
\frac{1}{|G|}\sum_{g\in G}U_g\,\mathcal H.
$$

More precisely, the projector is

$$
P_G=\frac{1}{|G|}\sum_{g\in G}U_g,
$$

for a finite unitary symmetry with no projective anomaly. But $P_G\mathcal H$ is not the full gauged Hilbert space. It is the untwisted invariant sector.

Twisted sectors arise because a finite gauge field on the spatial circle can have holonomy $g$. A state in $\mathcal H_g$ is not periodic in the original variables; it is periodic up to $g$. The residual gauge transformations preserving this holonomy form the centralizer $C(g)$, so the physical states in that sector are $C(g)$-invariant.

For abelian $G$, all elements commute, so every $h\in G$ acts on every $g$-twisted sector. For nonabelian $G$, conjugate holonomies describe gauge-equivalent sectors, and only $C(g)$ acts within a fixed $g$-sector.

This conjugacy-class/centralizer structure is the nonabelian version of the simple abelian formula.

## Torus partition function

A flat $G$ bundle on a torus is specified by two commuting holonomies,

$$
g=\mathrm{hol}_A,
\qquad
h=\mathrm{hol}_B,
\qquad
 gh=hg.
$$

The torus partition function in a background $(g,h)$ is $Z_{g,h}(\tau)$. Gauging gives

$$
Z_{T/G}(\tau)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}} Z_{g,h}(\tau)
$$

when no discrete torsion is turned on.

The modular group acts by changing the basis of torus cycles. For example, the $S$ transformation exchanges the two cycles, so schematically

$$
S: Z_{g,h}\mapsto Z_{h,g^{-1}}.
$$

The $T$ transformation shifts one cycle by the other, so schematically

$$
T: Z_{g,h}\mapsto Z_{g,gh}.
$$

The full sum over commuting pairs is stable under these transformations. This is why twisted sectors are forced by modular consistency.

## Discrete torsion and counterterms

Finite gauging is not always unique. One can multiply the sector sum by topological phases. In two-dimensional orbifolds, this is called **discrete torsion**. For many finite groups it is classified by

$$
H^2(G,U(1)),
$$

with the usual caveat that equivalent cocycles give the same phase choice.

More generally, in $d$ spacetime dimensions, local topological actions for finite $G$ backgrounds are Dijkgraaf–Witten counterterms, often represented by cohomology classes

$$
\omega\in H^d(BG,U(1))
$$

in the bosonic group-cohomology setting. Then

$$
Z_{T/G,\omega}[M]
=
\sum_{[A]} e^{iS_\omega[A]} Z_T[M,A].
$$

Different choices of $\omega$ can give genuinely different gauged theories. They differ not in local Lagrangian terms but in how finite gauge fields are weighted globally.

:::caution[Convention-sensitive normalization]
The factor $1/|G|$ in the torus formula is a convenient shorthand. On general manifolds and for nonabelian groups, the correct finite-gauge-theory normalization is a groupoid cardinality, with automorphism factors. A page doing exact state-sum TQFT calculations must state this normalization explicitly.
:::

## What happens to operators?

Gauging changes the operator spectrum.

A charged local operator in the original theory is not gauge invariant after gauging. It is projected out unless it is dressed by a defect or becomes an endpoint of an allowed line. Untwisted neutral operators survive.

New local operators also appear: twist fields, disorder operators, or operators living at endpoints or junctions of finite-gauge defects. In two-dimensional orbifolds, these are the local fields of twisted sectors.

Thus gauging does not simply remove data. It reorganizes the theory:

$$
\text{charged operators}
\quad\longleftrightarrow\quad
\text{twist/disorder sectors and dressed operators}.
$$

This is why gauging can turn an ordinary symmetry into a dual symmetry. For finite abelian $G$ in two dimensions, gauging a zero-form $G$ symmetry produces a dual zero-form symmetry

$$
\widehat G=\operatorname{Hom}(G,U(1)),
$$

called the **quantum symmetry** of the orbifold. Twisted sectors are charged under this dual symmetry. Gauging $\widehat G$ can recover the original theory, under appropriate anomaly-free assumptions.

For nonabelian $G$, the dual structure is not simply another ordinary finite group. The natural dual data involve Wilson lines of the finite gauge theory, representation categories, and defects.

## Examples

### Z₂ gauging and the Ising lesson

Let $G=\mathbb Z_2=\{1,\eta\}$. Gauging the spin-flip symmetry of an Ising-like theory projects onto spin-flip-even states and adds twisted sectors where fields pick up $\eta$ around the circle.

In lattice language, this means summing over $\mathbb Z_2$ gauge fields. In defect language, it means summing over networks of spin-flip lines. In the critical Ising CFT, the gauging operation is closely tied to the Kramers–Wannier duality defect.

### Finite gauge theory

If $T$ is the trivial theory and we gauge a finite group $G$, the result is pure finite $G$ gauge theory. In two dimensions this is almost entirely topological: path integrals count flat $G$ bundles with appropriate weights. Adding a Dijkgraaf–Witten cocycle twists the count by a topological phase.

### Orbifold of a compact boson

A compact boson with reflection symmetry

$$
X\mapsto -X
$$

can be orbifolded by $\mathbb Z_2$. The result contains invariant untwisted operators and new twist fields associated with fixed points of the reflection. This is one of the standard CFT examples where twisted sectors are plainly visible.

## Relation to Kramers–Wannier duality

Kramers–Wannier duality is best understood as a gauging operation plus an identification with another description. In the Ising model, high-temperature variables and low-temperature domain-wall variables exchange under duality. In modern language, the duality interface is built from gauging the $\mathbb Z_2$ spin-flip symmetry on one side of a line.

At the self-dual critical point, this interface becomes a topological duality defect. It is not invertible. Fusing it with itself gives a sum of the identity and the spin-flip line:

$$
\mathcal N\times\mathcal N=1+\eta.
$$

This is one of the cleanest examples showing that finite gauging can produce non-invertible symmetry.

## Common pitfalls

**“Gauging means keeping invariant states.”** Projection is only part of gauging. Twisted sectors or nontrivial finite bundles must also be included.

**“Finite gauging introduces a massless gauge boson.”** No. A finite gauge field has no infinitesimal photon-like fluctuation. Its important data are global: holonomies, bundles, defects, and topological sectors.

**“If a finite symmetry exists, it can always be gauged.”** No. A finite symmetry can have a ’t Hooft anomaly. In that case the background-field partition function cannot be consistently summed without extra bulk inflow or additional degrees of freedom.

**“The orbifold is unique.”** Not always. Discrete torsion and Dijkgraaf–Witten counterterms can produce distinct gaugings.

**“Nonabelian finite gauging is just the abelian formula with more elements.”** Nonabelian gauging requires conjugacy classes, centralizers, commuting holonomies, and automorphism factors. The dual symmetry is generally categorical rather than an ordinary group.

## Relations to other pages

[Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/) gives the CFT sector-sum construction. This page explains the general finite-gauging operation behind it.

[Kramers–Wannier Duality](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/kramers-wannier-duality/) shows how finite gauging appears as an order–disorder duality and as a non-invertible defect at criticality.

[Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) explains the generalized defect-category version. [Dijkgraaf–Witten Theory](/symmetry-anomalies-topology/topological-qft/dijkgraaf-witten-theory/) develops pure finite gauge theory as a TQFT.

## Research status

Finite-symmetry gauging is standard. The modern perspective is actively evolving because the same operation is now phrased in terms of topological defects, algebra objects, categorical symmetries, and SymTFT boundary conditions.

In two-dimensional CFT and lattice models, finite gauging is one of the clearest routes to non-invertible symmetries. In higher dimensions, finite gauging interacts with higher-form symmetries, anomaly inflow, topological order, and global-form choices.

## Exercises

### Exercise 1: Why commuting twists?

Explain why a flat $G$ bundle on a torus is specified by commuting holonomies $g,h\in G$ up to simultaneous conjugation.

<details><summary><strong>Solution</strong></summary>

The fundamental group of the torus has presentation

$$
\pi_1(T^2)=\langle A,B\mid ABA^{-1}B^{-1}=1\rangle.
$$

A flat finite $G$ bundle is a homomorphism

$$
\pi_1(T^2)\to G
$$

up to gauge equivalence. The images of $A$ and $B$ are $g$ and $h$. The relation requires

$$
ghg^{-1}h^{-1}=1,
$$

so $gh=hg$. A global gauge transformation conjugates both holonomies at once:

$$
(g,h)\mapsto (kgk^{-1},khk^{-1}).
$$

</details>

### Exercise 2: Projection is not enough

For $G=\mathbb Z_2$, write the untwisted projection operator. Why does applying this projector to the original Hilbert space fail to give the full orbifold Hilbert space?

<details><summary><strong>Solution</strong></summary>

If $\eta$ generates $\mathbb Z_2$, the projector is

$$
P=\frac12(1+U_\eta).
$$

The projected untwisted Hilbert space is $P\mathcal H_1$. But a finite gauge field on the spatial circle can also have nontrivial holonomy $\eta$, producing an $\eta$-twisted Hilbert space $\mathcal H_\eta$. The full orbifold Hilbert space is

$$
\mathcal H_{T/\mathbb Z_2}=\mathcal H_1^{\mathbb Z_2}\oplus \mathcal H_\eta^{\mathbb Z_2}.
$$

The second term is missing if one only projects the original Hilbert space.

</details>

### Exercise 3: Quantum symmetry of a Zₙ orbifold

For $G=\mathbb Z_N$, the orbifold has sectors $\mathcal H_g$ labeled by $g\in\mathbb Z_N$. Show how the dual group $\widehat{\mathbb Z_N}\cong\mathbb Z_N$ can act on twisted sectors.

<details><summary><strong>Solution</strong></summary>

A character $\chi\in\widehat{\mathbb Z_N}$ is a homomorphism

$$
\chi:\mathbb Z_N\to U(1).
$$

If a state lies in the $g$-twisted sector $\mathcal H_g$, define the dual action by multiplying that sector by the phase $\chi(g)$. Since characters multiply and $g$ labels the holonomy sector, this gives an action of $\widehat{\mathbb Z_N}$ on the orbifold Hilbert space. This is the quantum symmetry.

</details>

### Exercise 4: Discrete torsion phase

For abelian $G$, a discrete-torsion choice multiplies $Z_{g,h}$ by a phase $\epsilon(g,h)$. What condition should $\epsilon$ satisfy under modular transformations, at least schematically?

<details><summary><strong>Solution</strong></summary>

The phase choice must be compatible with large diffeomorphisms of the torus. Since modular transformations send

$$
Z_{g,h}\mapsto Z_{h,g^{-1}},
\qquad
Z_{g,h}\mapsto Z_{g,gh},
$$

the phases must transform consistently under these maps so that the full sector sum remains modular invariant. In cohomological language, $\epsilon$ should come from a valid $U(1)$ two-cocycle modulo coboundaries. The cocycle condition is the algebraic form of consistency under cutting and gluing.

</details>

## References

- L. Dixon, J. Harvey, C. Vafa, and E. Witten, “Strings on Orbifolds,” for the classic orbifold sector construction.
- R. Dijkgraaf, C. Vafa, E. Verlinde, and H. Verlinde, “The Operator Algebra of Orbifold Models,” for orbifold operator algebra.
- P. Ginsparg, “Applied Conformal Field Theory,” for an efficient CFT presentation of sectors, twists, and modular constraints.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the background-field and gauging viewpoint.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for QFT–TQFT coupling and finite/higher-form symmetry refinements.
- N. Carqueville and I. Runkel, “Orbifold Completion of Defect Bicategories,” for generalized orbifolds in defect language.
- N. Carqueville, I. Runkel, and G. Schaumann, “Orbifolds of n-Dimensional Defect TQFTs,” for a modern defect-TQFT generalization.

## Version history

- **2026-06-23:** Initial polished draft. Added projection/twisted-sector construction, flat-bundle sum, defect-network picture, discrete torsion, quantum symmetry, operator reorganization, examples, and exercises.
