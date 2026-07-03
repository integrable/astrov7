---
title: "Fermionization"
description: "Explains how bosonic two-dimensional theories can be rewritten as spin/fermionic theories, including fermion parity, spin structures, Arf phases, Jordan–Wigner logic, and Ising/Majorana examples."
sidebar:
  label: "Fermionization"
  order: 2
level: Advanced
status: "Polished draft"
source: "Kadanoff–Ceva; Jordan–Wigner; Coleman; Ginsparg; Di Francesco–Mathieu–Sénéchal; Kapustin–Thorngren; modern spin-TQFT and generalized-symmetry references."
topics:
  - fermionization
  - spin structure
  - fermion parity
  - Jordan–Wigner transformation
  - Arf invariant
  - Ising model
  - Majorana fermion
canonicalTopics:
  - fermionization
  - spin-qft
  - fermion-parity
  - arf-invariant
  - jordan-wigner
researchStatus:
  established:
    - "In 1+1 dimensions, many bosonic lattice and continuum theories can be rewritten in fermionic variables once spin structure and fermion parity are tracked carefully."
    - "The critical Ising model and the Majorana fermion provide the canonical example of bosonic and fermionic descriptions related by fermionization/bosonization."
  active:
    - "Modern formulations express fermionization as a gauging operation involving spin-TQFT kernels, generalized symmetry, bosonic shadow theories, and sometimes higher-dimensional analogues."
---

## Summary

**Fermionization** is the reverse face of bosonization: it rewrites a bosonic theory as a fermionic, or more precisely spin, theory. In two dimensions this is not a slogan about changing statistics by hand. It is a precise operation that introduces dependence on a spin structure and produces a distinguished fermion parity symmetry $(-1)^F$.

The simplest physical picture is the Jordan–Wigner transformation in a one-dimensional spin chain. Local spin variables are rewritten using fermion operators, but the fermion operator includes a nonlocal string of spin operators. The string is not a technical nuisance; it is the signal that fermionic locality and bosonic locality are related in a subtle, dimension-dependent way.

In continuum language, a common schematic fermionization transform starts from a bosonic theory $B$ with a non-anomalous $\mathbb Z_2$ global symmetry. Put $B$ in a background $\mathbb Z_2$ gauge field $a$, couple this background to a spin-dependent Arf kernel, and sum over $a$:

$$
Z_F[\eta]
\;\sim\;
\sum_{a\in H^1(\Sigma,\mathbb Z_2)}
Z_B[a]\,
(-1)^{\mathrm{Arf}(\eta+a)}.
$$

Here $\eta$ is a spin structure on the two-dimensional spacetime $\Sigma$. The precise normalization and whether one includes an extra factor $(-1)^{\mathrm{Arf}(\eta)}$ depend on convention. The invariant content is that fermionization turns a bosonic $\mathbb Z_2$-symmetric theory into a spin theory whose partition function depends on $\eta$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic fermionization transform: a bosonic theory with a Z2 background is summed over backgrounds with an Arf spin-TQFT kernel to produce a spin theory depending on spin structure.](/figures/symmetry-anomalies-topology/fermionization-spin-sum.svg)

<figcaption>

Fermionization in two dimensions can be viewed as a symmetry-gauging transform with a spin-dependent kernel. The bosonic theory is evaluated with $\mathbb Z_2$ background $a$; summing over $a$ with an Arf phase produces a spin theory depending on the spin structure $\eta$.

</figcaption>
</figure>

The lesson is:

$$
\text{fermions}
\quad=\quad
\text{bosonic variables}+\text{strings}+\text{spin-structure data}.
$$

## Prerequisites

Read [Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/) first. You should also know ordinary $\mathbb Z_2$ symmetries, finite-symmetry gauging, twist lines, and the distinction between local operators and defect endpoints.

Useful background pages include [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/), [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), and [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/).

## Core idea

A bosonic QFT can be defined on oriented manifolds without a spin structure. A fermionic QFT generally cannot. Fermions require a choice of spin structure because transporting a fermion around a closed cycle involves a sign choice.

In two Euclidean dimensions, a spin structure can be thought of operationally as specifying periodic or antiperiodic boundary conditions for fermions around each independent cycle. On a torus, one often labels the four spin structures by

$$
(\mathrm{NS},\mathrm{NS}),\qquad
(\mathrm{NS},\mathrm{R}),\qquad
(\mathrm{R},\mathrm{NS}),\qquad
(\mathrm{R},\mathrm{R}),
$$

where NS means antiperiodic and R means periodic along a cycle.

A bosonic theory does not remember these choices by itself. Fermionization is the operation that makes a spin theory out of bosonic data by summing over a $\mathbb Z_2$ background with a spin-dependent phase. The $\mathbb Z_2$ symmetry being gauged is not an arbitrary decoration: it becomes tied to the emergent fermion parity of the resulting spin theory.

The result is not merely a theory with anticommuting variables in a Lagrangian. It is a theory whose partition functions and operator sectors know about spin structure.

## Setup and conventions

Let $B$ be a bosonic two-dimensional QFT with a non-anomalous $\mathbb Z_2$ global symmetry generated by $g$. Let $a$ denote a background flat $\mathbb Z_2$ gauge field. Informally, $a$ records where symmetry-twist lines are inserted or how fields are twisted around cycles.

The background partition function is written

$$
Z_B[a].
$$

A spin structure is denoted $\eta$. The Arf invariant is a mod-two invariant of a spin surface,

$$
\mathrm{Arf}(\eta)\in\mathbb Z_2,
$$

and the invertible spin TQFT with partition function $(-1)^{\mathrm{Arf}(\eta)}$ represents the Kitaev-chain phase in two-dimensional Euclidean spacetime language.

A schematic fermionization transform is

$$
Z_F[\eta]
=
\frac{1}{\mathcal N_\Sigma}
\sum_{a\in H^1(\Sigma,\mathbb Z_2)}
Z_B[a]\,
(-1)^{\mathrm{Arf}(\eta+a)}.
$$

The normalization $\mathcal N_\Sigma$ is chosen so that the operation has the desired inverse and partition-function normalization. Some authors instead write

$$
Z_F[\eta]
=
\frac{1}{\mathcal N_\Sigma}
\sum_a
Z_B[a]\,
(-1)^{\mathrm{Arf}(\eta+a)-\mathrm{Arf}(\eta)}.
$$

Both notations differ by stacking the final spin theory with an invertible Arf theory. This is not a contradiction; it is a choice of fermionization convention.

:::note[Source note: Arf-kernel conventions]
There are several equivalent-looking fermionization formulas in the literature. They differ by normalization, by whether $a$ is treated as a cochain or cohomology class, by cup-product refinements on triangulations, and by stacking with the invertible Arf spin TQFT. This page uses the formula only as a conceptual kernel, and states convention-sensitive signs explicitly when needed.
:::

## Jordan–Wigner as the lattice prototype

On a one-dimensional spin chain, the Jordan–Wigner transformation defines fermion operators using spin operators and a string. For Pauli matrices $\sigma_j^x,\sigma_j^y,\sigma_j^z$, one can define

$$
c_j
=
\left(\prod_{k<j}\sigma_k^z\right)
\frac{\sigma_j^x-i\sigma_j^y}{2}.
$$

The string

$$
\prod_{k<j}\sigma_k^z
$$

is what makes operators at different sites anticommute. Without it, operators built from different spin sites would commute.

This already contains the main physics. Fermionic locality is not the same as bosonic locality. A fermion creation operator is local in the fermion variables but nonlocal in the original spin variables because of the string. Conversely, simple spin operators may become nonlocal disorder operators in the fermion description.

On an open chain the transformation is straightforward. On a circle, the string can wrap around the system, and boundary conditions depend on the total fermion parity. This is the lattice version of spin-structure dependence.

:::caution[Boundary conditions are part of the dictionary]
The Jordan–Wigner map on a circle is not complete until one states how fermion parity and boundary conditions are related. Many apparent paradoxes in fermionization come from silently using the open-chain dictionary on a closed spatial circle.
:::

## Fermion parity

Every fermionic theory has a distinguished central symmetry

$$
(-1)^F.
$$

Local bosonic operators commute with $(-1)^F$, while fermionic operators anticommute. The Hilbert space decomposes as

$$
\mathcal H=\mathcal H_{\rm even}\oplus\mathcal H_{\rm odd}.
$$

Fermionization produces such a structure from bosonic data. In the bosonic shadow, the operator that becomes a fermion is not an ordinary local bosonic operator. It is typically an endpoint of a symmetry defect line or a disorder operator with an attached string. After fermionization, that string is absorbed into the spin-structure-dependent definition of locality, and the endpoint becomes a local fermion.

This is why fermionization is naturally phrased in terms of defects. A fermion is not just a field with a minus sign. It is a local excitation whose exchange and transport signs are globally consistent on spin manifolds.

## Ising and Majorana

The canonical continuum example is the relation between the critical Ising model and the free Majorana fermion.

The bosonic critical Ising CFT has three primary fields:

| Field | Meaning | Scaling dimension |
|---|---|---:|
| $1$ | identity | $0$ |
| $\sigma$ | spin/order operator | $1/8$ |
| $\varepsilon$ | energy operator | $1$ |

It also has disorder fields and a $\mathbb Z_2$ spin-flip symmetry. The free Majorana fermion has chiral fermions $\psi,\bar\psi$ and depends on spin structure. The two descriptions are closely related but not literally the same object before choosing how to sum over spin structures or how to gauge fermion parity.

A compact summary is:

$$
\text{Majorana spin CFT}
\quad
\xleftrightarrow{\;\text{gauge }(-1)^F\text{ / fermionize}\;}
\quad
\text{bosonic Ising CFT}.
$$

Depending on convention, the bosonic Ising model can be viewed as the fermion-parity gauging of the Majorana theory, while fermionization of the Ising spin-flip symmetry recovers a Majorana spin theory, possibly stacked with the Arf invertible theory.

At the operator level, the Majorana fermion is related to a disorder-line endpoint in the Ising model. The familiar order and disorder fields $\sigma$ and $\mu$ are bosonic local fields in the appropriate sectors, while the fermion can be thought of schematically as a composite

$$
\psi \sim \sigma\,\mu
$$

with careful attention to chirality, branch cuts, and normalization.

## Spin structures and torus sectors

A good way to see the difference between bosonic and fermionic theories is to place them on a torus. A fermionic theory has four partition functions,

$$
Z_{\rm NS,NS},\quad
Z_{\rm NS,R},\quad
Z_{\rm R,NS},\quad
Z_{\rm R,R},
$$

corresponding to spin structures around the two cycles. These are not four unrelated theories; modular transformations permute them.

A bosonic theory with $\mathbb Z_2$ symmetry has twisted partition functions

$$
Z_B[a_t,a_x],
$$

where $a_t,a_x\in\mathbb Z_2$ specify twists around temporal and spatial cycles. Fermionization combines these twisted bosonic partition functions with spin-structure-dependent signs.

The punchline is:

$$
\text{fermionic spin sectors}
\quad
\leftrightarrow
\quad
\text{bosonic twisted sectors with Arf signs}.
$$

This is the torus version of the Jordan–Wigner boundary-condition subtlety.

## Fermionization versus bosonization

The words “bosonization” and “fermionization” are often used loosely. It helps to separate three statements.

First, **operator bosonization** gives a dictionary between fermion bilinears, currents, vertex operators, and compact bosons. This is the standard free Dirac/compact-boson dictionary.

Second, **lattice fermionization** gives a map such as Jordan–Wigner, where spin variables and fermion variables are related by strings.

Third, **spin-TQFT fermionization** is the background-field operation using an Arf kernel. It says how to turn a bosonic theory with a suitable $\mathbb Z_2$ symmetry into a spin theory, and how to track partition functions on general spin surfaces.

These are not competing definitions. They are different levels of the same phenomenon.

## What can be fermionized?

Not every bosonic theory admits a useful fermionization. At minimum, one needs a suitable $\mathbb Z_2$ symmetry that can be coupled to backgrounds in the required way. In continuum language, one needs the twisted sectors and defect endpoints needed to produce fermionic local operators. In lattice language, one needs a structure analogous to a Jordan–Wigner string.

A practical checklist is:

| Question | Why it matters |
|---|---|
| Is there a non-anomalous $\mathbb Z_2$ symmetry? | One must be able to sum over its backgrounds. |
| Are the twisted sectors understood? | Fermions often emerge from disorder/twist sectors. |
| Is spin structure included? | A fermionic theory must know boundary-condition signs. |
| What is $(-1)^F$ after the transformation? | The result should have a distinguished fermion parity. |
| Is the result local as a spin theory? | Fermionic locality differs from bosonic locality. |
| Has an Arf stacking convention been chosen? | Different conventions differ by an invertible spin phase. |

In many solvable examples, the answer is yes. In a general interacting QFT, fermionization is a structural operation, not a promise of a simple free-fermion Lagrangian.

## Relation to gauging

Fermionization is closely related to gauging, but it is not just ordinary bosonic gauging. Ordinary gauging of a finite symmetry sums over background gauge fields and produces another bosonic theory. Fermionization sums over a $\mathbb Z_2$ background with a spin-dependent kernel and produces a spin theory.

A useful schematic comparison is:

$$
\text{bosonic gauging:}\qquad
Z_{B/G}\sim \sum_a Z_B[a],
$$

while

$$
\text{fermionization:}\qquad
Z_F[\eta]\sim \sum_a Z_B[a]\,(-1)^{\mathrm{Arf}(\eta+a)}.
$$

The extra spin-dependent factor is what changes the kind of theory produced. It is also why fermionization naturally belongs next to orbifolds and finite-symmetry gauging in this chapter.

## Common pitfalls

**“Fermionization means every bosonic theory is secretly free fermions.”** No. Fermionization can produce interacting fermionic theories. It is a change in the type of variables and global structure, not a guarantee of solvability.

**“Spin structure is optional bookkeeping.”** It is not. A fermionic partition function is not defined on a general surface without a spin structure.

**“The Jordan–Wigner string is an artifact.”** The string is the mechanism by which bosonic commuting operators become fermionic anticommuting operators.

**“The Ising model is simply the Majorana fermion.”** They are related, but one must specify whether one means a bosonic CFT, a spin CFT, a sum over spin structures, or a theory stacked with the Arf phase.

**“Gauging $\mathbb Z_2$ and fermionizing are the same operation.”** They are related, but fermionization includes a spin-dependent kernel and produces a spin theory.

**“The local operator spectra must match one-to-one.”** Some operators are local in one description and disorder-line endpoints or nonlocal strings in the other.

## Relations to other pages

[Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/) gives the complementary fermion-to-boson dictionary. [Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/) and Gauging Finite Symmetries explain the bosonic gauging operation that fermionization refines with spin data. [Kramers–Wannier Duality](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/kramers-wannier-duality/) uses the Ising order/disorder map, which is one of the most concrete settings for fermionization.

The [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) chapter explains how duality defects encode the same order/disorder operations in topological-defect language. The [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) chapter explains how spin-TQFT kernels and bulk-boundary viewpoints package the global data.

## Research status

The basic 1+1-dimensional fermionization examples, including Jordan–Wigner, Ising/Majorana, and compact-boson/Dirac dictionaries, are established. The modern spin-TQFT formulation is also standard in current generalized-symmetry and topological-phase language.

Active work continues on higher-dimensional analogues, bosonic shadows of fermionic phases, categorical formulations of fermionic defects, non-invertible fermionization operations, and lattice realizations that keep locality and spin-structure data manifest.

## Exercises

### Exercise 1: Jordan–Wigner anticommutation

Let

$$
c_j=
\left(\prod_{k<j}\sigma_k^z\right)\sigma_j^-,
\qquad
\sigma_j^-=\frac{\sigma_j^x-i\sigma_j^y}{2}.
$$

Explain why the string is needed for $c_i$ and $c_j$ to anticommute when $i\ne j$.

<details><summary><strong>Solution</strong></summary>

Spin operators on different sites commute. Without the string, $\sigma_i^-$ and $\sigma_j^-$ would commute. For $i<j$, the operator $c_j$ contains a factor $\sigma_i^z$ in its string. Since

$$
\sigma_i^z\sigma_i^-=-\sigma_i^-\sigma_i^z,
$$

moving $c_i$ past $c_j$ produces a minus sign. The string converts commuting spin-site variables into anticommuting fermionic variables.

</details>

### Exercise 2: Spin structures on a torus

How many spin structures are there on a two-torus? Label them using NS/R notation.

<details><summary><strong>Solution</strong></summary>

A torus has two independent one-cycles. Around each cycle a fermion can be antiperiodic, denoted NS, or periodic, denoted R. Therefore there are four spin structures:

$$
(\mathrm{NS},\mathrm{NS}),\qquad
(\mathrm{NS},\mathrm{R}),\qquad
(\mathrm{R},\mathrm{NS}),\qquad
(\mathrm{R},\mathrm{R}).
$$

</details>

### Exercise 3: Gauging versus fermionization

Compare

$$
Z_{B/\mathbb Z_2}\sim\sum_a Z_B[a]
$$

with

$$
Z_F[\eta]\sim\sum_a Z_B[a](-1)^{\mathrm{Arf}(\eta+a)}.
$$

What extra datum appears in the second expression?

<details><summary><strong>Solution</strong></summary>

The second expression depends on a spin structure $\eta$ and includes the spin-dependent Arf phase. Ordinary bosonic gauging sums over $\mathbb Z_2$ backgrounds and produces a bosonic theory. Fermionization sums with an Arf kernel and produces a spin theory with fermion parity.

</details>

### Exercise 4: Ising versus Majorana

Why is it imprecise to say “the Ising CFT is the Majorana fermion” without qualification?

<details><summary><strong>Solution</strong></summary>

The bosonic Ising CFT is defined without choosing a spin structure. A Majorana fermion is a spin theory whose partition function depends on spin structure. The two are related by gauging/fermionization operations involving fermion parity and spin-structure sums. Thus one must specify whether one means the bosonic Ising model, a Majorana spin CFT, a sum over spin structures, or a theory stacked with an invertible Arf phase.

</details>

## References

- P. Jordan and E. Wigner, “Über das Paulische Äquivalenzverbot,” for the original spin-chain fermionization transformation.
- L. P. Kadanoff and H. Ceva, “Determination of an Operator Algebra for the Two-Dimensional Ising Model,” for order and disorder operators.
- S. Coleman, “Quantum Sine-Gordon Equation as the Massive Thirring Model,” for the classic bosonization duality.
- P. Ginsparg, “Applied Conformal Field Theory,” for compact bosons, fermions, spin sectors, and 2D CFT conventions.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for Ising, fermions, orbifolds, and modular-invariance technology.
- A. Kapustin and R. Thorngren, “Fermionic SPT Phases in Higher Dimensions and Bosonization,” for the modern spin-TQFT and bosonic-shadow viewpoint.
- D. Gaiotto and A. Kapustin, “Spin TQFTs and Fermionic Phases of Matter,” for fermionic phases, spin TQFTs, and shadow theories.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for condensed-matter bosonization and Jordan–Wigner-style intuition.

## Version history

- **2026-06-23:** Initial polished draft. Introduced fermionization through Jordan–Wigner strings, spin structures, Arf kernels, fermion parity, Ising/Majorana, torus sectors, and relation to finite-symmetry gauging.
