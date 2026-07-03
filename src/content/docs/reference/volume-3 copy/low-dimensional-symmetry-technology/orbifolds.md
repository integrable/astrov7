---
title: "Orbifolds"
description: "Explains two-dimensional orbifolds as finite-symmetry gauging, including twisted sectors, projections, torus partition functions, discrete torsion, quantum symmetry, defects, and common consistency checks."
sidebar:
  label: "Orbifolds"
  order: 3
level: Advanced
status: "Polished draft"
source: "Dixon–Harvey–Vafa–Witten; Dijkgraaf–Vafa–Verlinde–Verlinde; Ginsparg; Di Francesco–Mathieu–Sénéchal; standard finite-gauging and CFT defect references."
topics:
  - orbifolds
  - finite symmetry gauging
  - two-dimensional CFT
  - twisted sectors
  - modular invariance
  - discrete torsion
  - quantum symmetry
canonicalTopics:
  - orbifold
  - finite-symmetry-gauging
  - twisted-sector
  - projection-onto-invariants
  - discrete-torsion
researchStatus:
  established:
    - "Orbifolding by a finite non-anomalous symmetry is a standard construction in two-dimensional CFT, string theory, statistical field theory, and finite-gauge-theory examples."
    - "The torus orbifold partition function is built from twisted sectors and projection, and modular invariance requires treating twists around both cycles."
  active:
    - "Modern generalized-symmetry language interprets orbifolding as gauging a finite symmetry, often described by summing over topological defect networks and condensation data."
---

## Summary

An **orbifold** is the theory obtained by gauging a finite symmetry. In two-dimensional QFT and CFT, this usually means two operations at once:

1. project onto states invariant under the finite symmetry;
2. add twisted sectors, where fields are periodic only up to a symmetry transformation.

For a theory $T$ with finite symmetry group $G$, the orbifold is often denoted

$$
T/G.
$$

On a torus, the partition function has the schematic form

$$
Z_{T/G}(\tau)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}}
Z_{g,h}(\tau).
$$

Here $Z_{g,h}$ is the partition function with a $g$ twist around one cycle and an $h$ twist around the other. The condition $gh=hg$ says that the two twists define a flat $G$ bundle on the torus.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A torus orbifold sector diagram showing twists g and h around the two cycles, projection, twisted sectors, and the orbifold sum.](/figures/symmetry-anomalies-topology/orbifold-sector-sum.svg)

<figcaption>

A two-dimensional orbifold is finite-symmetry gauging. On the torus, this means summing over flat $G$ bundles, equivalently over commuting twists $g,h$ around the two cycles. The untwisted invariant sector alone is not modular invariant; twisted sectors are part of the construction.

</figcaption>
</figure>

The slogan is

$$
\text{orbifold}
=
\text{projection}
+
\text{twisted sectors}
+
\text{consistency under cutting and gluing}.
$$

Orbifolds are one of the cleanest places where finite symmetries, topological defects, gauging, duality, modular invariance, and anomalies meet.

## Prerequisites

You should know [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/), [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/), and the previous low-dimensional pages [Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/) and [Fermionization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/fermionization/).

You do not need a full string-theory background. This page treats orbifolds as QFT operations. The same language later appears in string compactifications, rational CFT, finite gauge theory, and symmetry TFT.

## Core idea

Suppose a QFT $T$ has a finite global symmetry $G$. If the symmetry is non-anomalous, one can gauge it. For finite $G$, gauging does not introduce a fluctuating continuous gauge potential. Instead, the path integral sums over flat $G$ bundles, or equivalently over networks of topological symmetry defects.

In Hamiltonian language on a circle, the untwisted Hilbert space $\mathcal H_1$ is only the beginning. Gauging requires projecting onto invariant states,

$$
\mathcal H_1^G
=
\{|\psi\rangle\in\mathcal H_1\mid U_g|\psi\rangle=|\psi\rangle \text{ for all }g\in G\}.
$$

But projection alone is not enough. One must also include sectors where fields have twisted boundary conditions around the spatial circle,

$$
\Phi(x+2\pi)=g\cdot\Phi(x).
$$

The full orbifold Hilbert space is schematically

$$
\mathcal H_{T/G}
=
\bigoplus_{[g]}
\mathcal H_g^{C(g)}.
$$

Here $\mathcal H_g$ is the $g$-twisted Hilbert space, $[g]$ runs over conjugacy classes, and $C(g)$ is the centralizer of $g$, the subgroup commuting with $g$.

For abelian $G$, this simplifies to

$$
\mathcal H_{T/G}
=
\bigoplus_{g\in G}\mathcal H_g^G.
$$

The twisted sectors are not optional. They are forced by locality, modular invariance, and the path integral over finite gauge fields.

## Setup and conventions

Let $T$ be a two-dimensional QFT with a finite internal symmetry group $G$. We write $U_g$ for the corresponding topological symmetry line or Hilbert-space action. A $g$-twisted sector means that crossing the spatial circle applies $g$.

On a torus, choose cycles $A$ and $B$. A flat $G$ bundle assigns holonomies

$$
g=\mathrm{hol}_A,\qquad h=\mathrm{hol}_B,
$$

with

$$
gh=hg
$$

for a torus because the fundamental group is abelian. The partition function with these twists is denoted

$$
Z_{g,h}(\tau).
$$

The orbifold partition function is

$$
Z_{T/G}(\tau)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}}
Z_{g,h}(\tau),
$$

possibly modified by discrete torsion phases.

:::note[Source note: nonabelian groups]
For nonabelian $G$, the sum over commuting pairs is really a sum over flat $G$ bundles on the torus, divided by gauge equivalence. Writing a raw sum over commuting pairs with $1/|G|$ is a compact physics convention; the invariant statement is a groupoid sum over flat bundles.
:::

## Projection is not enough

A first guess might be

$$
\mathcal H_{\rm guess}=\mathcal H_1^G.
$$

This is the invariant subspace of the original Hilbert space. It is part of the orbifold, but it is not the full orbifold.

Why not? Because gauging a finite symmetry introduces gauge-field sectors. On a spatial circle, a flat $G$ gauge field can have holonomy $g$ around the circle. This holonomy cannot necessarily be gauged away globally. The matter fields then obey $g$-twisted boundary conditions.

In path-integral language, the same point says that finite gauging sums over all $G$ bundles, not only the trivial bundle. On the torus, the trivial bundle is just the sector $(g,h)=(1,1)$. A gauge theory sum includes all flat sectors.

In CFT, modular transformations exchange the two cycles of the torus. If one projects only in the untwisted sector, a modular transformation generally produces a sector twisted around the other cycle. Thus modular invariance forces twisted sectors.

## Twisted sectors

A $g$-twisted sector consists of states created by quantizing the theory on a circle with boundary condition

$$
\Phi(\sigma+2\pi)=g\cdot\Phi(\sigma).
$$

For a geometric target-space orbifold $X/G$, this means fields are maps into $X$ that close only up to the action of $g$. For an abstract QFT orbifold, $g$ can be any finite internal symmetry, not necessarily geometric.

A local operator in a twisted sector is often called a twist field. It creates a branch point or defect endpoint such that fields transported around it return transformed by $g$.

For example, in a simple $\mathbb Z_2$ orbifold of a compact boson, twisted fields create configurations where the boson is reflected after circling the insertion. In the Ising model, order and disorder fields can be understood using similar branch-cut logic.

For nonabelian $G$, sectors associated with conjugate elements are equivalent because a global gauge transformation can conjugate the holonomy. That is why the Hilbert-space decomposition uses conjugacy classes $[g]$.

## Projection inside twisted sectors

In the untwisted sector, one projects onto $G$-invariant states. In a $g$-twisted sector, only the subgroup commuting with $g$ acts within that same sector. This subgroup is the centralizer

$$
C(g)=\{h\in G\mid hg=gh\}.
$$

Therefore the projected $g$-twisted Hilbert space is

$$
\mathcal H_g^{C(g)}.
$$

For abelian $G$, $C(g)=G$ for every $g$, so the formula becomes simpler. For nonabelian groups, centralizers are essential and are a good test of whether one is treating the orbifold as a genuine gauging rather than a heuristic quotient.

## Torus partition function

The torus formula packages projection and twisted sectors in one line:

$$
Z_{T/G}(\tau)
=
\frac{1}{|G|}
\sum_{\substack{g,h\in G\\ gh=hg}}
Z_{g,h}(\tau).
$$

Here $g$ is usually interpreted as the spatial twist and $h$ as the insertion of $h$ in the trace,

$$
Z_{g,h}(\tau)
=
\operatorname{Tr}_{\mathcal H_g}
\left(
h\,q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}
\right),
\qquad
q=e^{2\pi i\tau}.
$$

For nonabelian $G$, the trace makes sense only when $h$ preserves the $g$-twisted Hilbert space, hence $hg=gh$.

Modular transformations act on the pair $(g,h)$. Schematically,

$$
S:\ (g,h)\mapsto(h,g^{-1}),
\qquad
T:\ (g,h)\mapsto(g,gh),
$$

up to convention about which cycle is called spatial. The sum over all commuting pairs is what makes the orbifold partition function modular invariant when there is no anomaly.

:::caution[Orbifold consistency is more than a formula]
A modular-invariant torus partition function is a powerful check, but it is not the whole definition of a QFT. One also needs consistent local operator products, defect junctions, higher-genus sewing, and, for spin theories, spin-structure data.
:::

## Discrete torsion

Sometimes the orbifold sum can be modified by phases. For finite $G$, these phases are called **discrete torsion**. On a torus, one writes schematically

$$
Z_{T/G,\epsilon}(\tau)
=
\frac{1}{|G|}
\sum_{gh=hg}
\epsilon(g,h)\,Z_{g,h}(\tau).
$$

The phase $\epsilon(g,h)$ must satisfy consistency conditions so that the theory is modular invariant and glues consistently. In cohomological language, discrete torsion is often classified by

$$
H^2(G,U(1))
$$

for ordinary bosonic two-dimensional orbifolds, though refinements appear when spacetime, spin, higher-form, or anomaly data are included.

Discrete torsion is not an arbitrary decoration. It changes the orbifold theory. It can change operator products, projective actions in twisted sectors, and the resulting spectrum.

## Quantum symmetry

For abelian $G$, the orbifold $T/G$ often has a new symmetry called the **quantum symmetry**,

$$
\widehat G=\operatorname{Hom}(G,U(1)).
$$

It acts on twisted sectors by phases. If a state lies in the $g$-twisted sector, a character $\chi\in\widehat G$ acts as

$$
|\psi\rangle_g\mapsto \chi(g)|\psi\rangle_g.
$$

This is the finite-gauge-theory analogue of the dual symmetry that appears after gauging. Gauging the quantum symmetry can recover the original theory:

$$
(T/G)/\widehat G \simeq T
$$

under suitable assumptions and with consistent normalization.

This statement is one reason orbifolds are a perfect training ground for generalized symmetry. Gauging changes the symmetry of the theory, but it does not destroy symmetry logic; it reorganizes it.

## Defect-network viewpoint

In two dimensions, a finite symmetry element $g$ is represented by a topological line $U_g$. Orbifolding can be described by summing over networks of these topological lines. On a triangulated surface, one labels edges by group elements and imposes flatness around faces. This is the defect-network version of summing over flat $G$ bundles.

In this language, projection comes from inserting symmetry lines along the time direction. Twisted sectors come from inserting symmetry lines along the spatial direction. The torus sum is just the sum over both directions.

The network viewpoint generalizes beautifully. Replacing group-like symmetry lines by more general algebra objects in a fusion category leads to generalized gauging and non-invertible orbifold-like constructions. That is why orbifolds sit next to non-invertible symmetry in the larger volume plan.

## Geometric versus internal orbifolds

The word “orbifold” has two closely related meanings.

In geometry, an orbifold is a space that locally looks like

$$
\mathbb R^n/\Gamma
$$

for a finite group $\Gamma$ acting linearly. In string theory, one often studies a sigma model with target $X/G$, where $G$ acts geometrically on $X$.

In QFT, the more general operation is gauging a finite internal symmetry. The symmetry need not act on a target-space manifold. It may act on operators, defects, or sectors.

Thus every geometric orbifold sigma model is an orbifold QFT construction, but not every QFT orbifold is a geometric quotient.

## Orbifolds and anomalies

A finite symmetry can be orbifolded only if it is non-anomalous. An anomaly is an obstruction to coupling the symmetry consistently to background $G$ bundles and then summing over them.

In two-dimensional language, an anomaly may show up as an inconsistent transformation of the twisted partition functions under modular transformations, or as a failure of defect networks to be topologically well-defined. If the symmetry line has anomalous associativity or cannot be consistently summed over, the orbifold is not a standalone ordinary QFT unless additional bulk inflow is supplied.

This is the same principle seen throughout the volume:

$$
\text{gauging possible}
\quad\Longleftrightarrow\quad
\text{no obstruction/anomaly}.
$$

Orbifolds are often the easiest place to see this principle concretely.

## Examples

### Reflection orbifold of a compact boson

Let $X$ be a compact boson with reflection symmetry

$$
X\mapsto -X.
$$

The orbifold by $\mathbb Z_2$ includes the invariant operators of the original compact boson, but also twisted sectors associated with fixed points of the reflection. Twist fields create branch points around which

$$
X\to -X.
$$

The resulting orbifold CFT is not just the invariant subsector of the original compact boson. Its twisted-sector operators are new local operators of the orbifold.

### Ising and fermion parity

The bosonic Ising CFT can be related to a Majorana spin theory by gauging/fermionization operations. Conversely, summing over spin structures or gauging fermion parity produces bosonic theories. The details depend on Arf phases and spin-structure conventions, but the orbifold lesson is universal: gauging a finite symmetry changes the sector structure.

### Finite group gauge theory

A pure finite group gauge theory in two dimensions is itself a topological orbifold-like theory. Its path integral sums over flat $G$ bundles. Defects are labeled by holonomies and representations of centralizers. This is the topological skeleton behind many orbifold sector formulas.

## Common pitfalls

**“Orbifold means keep only invariant operators.”** Projection is only half the story. Twisted sectors are required.

**“Twisted sectors are string-only objects.”** They appear in ordinary two-dimensional QFT whenever one gauges a finite symmetry and quantizes on a circle with nontrivial holonomy.

**“All pairs $g,h$ contribute on the torus.”** Only commuting pairs define flat bundles on the torus. For nonabelian groups, this matters.

**“Discrete torsion is an arbitrary phase.”** It must obey consistency conditions and changes the theory.

**“A modular-invariant torus partition function proves everything.”** It is a major check, not a full sewing proof.

**“Geometric quotient and QFT orbifold are the same thing.”** Geometric orbifolds are important examples, but QFT orbifolding means finite-symmetry gauging and can be non-geometric.

**“An anomalous finite symmetry can still be orbifolded if one is careful.”** Not as an ordinary standalone theory. An anomaly must be canceled, extended, or supplied by inflow.

## Relations to other pages

[Fermionization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/fermionization/) explains a spin-refined gauging operation using an Arf kernel. Gauging Finite Symmetries will treat the finite-gauge-field path integral more systematically. [Kramers–Wannier Duality](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/kramers-wannier-duality/) is naturally phrased using orbifold and duality-defect ideas.

The [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) chapter explains how orbifolding can produce non-invertible duality defects. The [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) chapter explains finite-symmetry gauging and orbifold choices as boundary conditions in a one-higher-dimensional topological theory.

## Research status

The basic orbifold construction in two-dimensional CFT is standard. Twisted sectors, projection, modular-invariant torus sums, and discrete torsion are classic tools.

The modern frontier is not the basic construction but its generalization: orbifolding by categorical symmetries, gauging algebra objects, treating fermionic and spin-refined orbifolds, understanding anomalies and SymTFT boundaries, and using defect networks to formulate orbifolds beyond Lagrangian or geometric settings.

## Exercises

### Exercise 1: Projection operator

For a finite group $G$ acting on a Hilbert space $\mathcal H$, show that

$$
P_G=\frac{1}{|G|}\sum_{g\in G}U_g
$$

is a projection operator onto the invariant subspace, assuming $U_gU_h=U_{gh}$.

<details><summary><strong>Solution</strong></summary>

First,

$$
P_G^2
=
\frac{1}{|G|^2}\sum_{g,h}U_gU_h
=
\frac{1}{|G|^2}\sum_{g,h}U_{gh}.
$$

For each $k\in G$, there are exactly $|G|$ pairs $(g,h)$ with $gh=k$. Therefore

$$
P_G^2
=
\frac{1}{|G|}\sum_k U_k=P_G.
$$

Also, for any $\ell\in G$,

$$
U_\ell P_G
=
\frac{1}{|G|}\sum_g U_{\ell g}
=
P_G.
$$

Thus the image of $P_G$ is invariant.

</details>

### Exercise 2: Commuting twists on a torus

Why must the twists $g,h$ around the two torus cycles commute?

<details><summary><strong>Solution</strong></summary>

The fundamental group of the torus is

$$
\pi_1(T^2)=\langle A,B\mid ABA^{-1}B^{-1}=1\rangle.
$$

A flat $G$ bundle assigns holonomies $g$ and $h$ to $A$ and $B$. The relation in the fundamental group requires

$$
ghg^{-1}h^{-1}=1,
$$

or

$$
gh=hg.
$$

</details>

### Exercise 3: Z₂ orbifold sectors

List the four torus sectors $Z_{g,h}$ for $G=\mathbb Z_2=\{1,r\}$.

<details><summary><strong>Solution</strong></summary>

Since $\mathbb Z_2$ is abelian, all pairs commute. The four sectors are

$$
Z_{1,1},\qquad
Z_{1,r},\qquad
Z_{r,1},\qquad
Z_{r,r}.
$$

The sector $Z_{1,1}$ is untwisted with no insertion. $Z_{1,r}$ is untwisted with an $r$ insertion in the trace. $Z_{r,1}$ has an $r$ spatial twist. $Z_{r,r}$ has an $r$ spatial twist and an $r$ insertion around the other cycle.

</details>

### Exercise 4: Quantum symmetry for Zₙ

For $G=\mathbb Z_N$, what is the quantum symmetry of the orbifold, and how does it act on a $g^k$-twisted sector?

<details><summary><strong>Solution</strong></summary>

The quantum symmetry is

$$
\widehat{\mathbb Z_N}\cong\mathbb Z_N.
$$

A character labeled by $\ell\in\mathbb Z_N$ acts on the $g^k$-twisted sector by the phase

$$
e^{2\pi i\ell k/N}.
$$

Thus the quantum symmetry measures the twist sector.

</details>

## References

- L. Dixon, J. Harvey, C. Vafa, and E. Witten, “Strings on Orbifolds,” for the original string/CFT orbifold construction.
- R. Dijkgraaf, C. Vafa, E. Verlinde, and H. Verlinde, “The Operator Algebra of Orbifold Models,” for operator-algebra and twisted-sector structure.
- P. Ginsparg, “Applied Conformal Field Theory,” for a compact CFT treatment of orbifolds and modular constraints.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for detailed orbifold CFT examples.
- C. Vafa, “Modular Invariance and Discrete Torsion on Orbifolds,” for discrete torsion.
- J. Fuchs, I. Runkel, and C. Schweigert, works on TFT construction of RCFT correlators, for the defect/TFT viewpoint.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern background-field and gauging language.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for finite-gauging, global-form, and topological-coupling viewpoints.

## Version history

- **2026-06-23:** Initial polished draft. Explained orbifolds as finite-symmetry gauging with twisted sectors, projection, torus sector sums, discrete torsion, quantum symmetry, defect networks, and anomaly caveats.
