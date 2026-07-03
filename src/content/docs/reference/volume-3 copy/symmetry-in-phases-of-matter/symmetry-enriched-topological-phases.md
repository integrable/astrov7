---
title: "Symmetry-Enriched Topological Phases"
description: "Explains SET phases as intrinsic topological orders enriched by global symmetry actions, including symmetry fractionalization, anyon permutation, defects, gauging, and anomaly constraints."
sidebar:
  label: "SET Phases"
  order: 3
level: Advanced
status: "Polished draft"
source: "Barkeshli–Bonderson–Cheng–Wang; Lu–Vishwanath; Wen; Gaiotto–Kapustin–Seiberg–Willett; standard anyon, TQFT, and symmetry-fractionalization references."
topics:
  - SET phases
  - topological order
  - symmetry fractionalization
  - anyon permutation
  - symmetry defects
  - gauging
canonicalTopics:
  - symmetry-enriched-topological-phase
  - symmetry-fractionalization
  - anyon-permutation
  - symmetry-defect
  - set-anomaly
researchStatus:
  established:
    - "SET phases are standard examples of intrinsic topological order equipped with additional global symmetry action on anyons, defects, and boundary data."
  active:
    - "General SET classification with antiunitary, crystalline, higher-form, fermionic, non-invertible, and subsystem symmetries remains an active research area."
---

## Summary

A **symmetry-enriched topological phase**, or **SET phase**, is a phase with intrinsic topological order together with a nontrivial action of global symmetry on that topological order.

The rough definition is:

$$
\text{SET phase}
=
\text{intrinsic topological order}
+
\text{global symmetry enrichment}.
$$

The intrinsic topological order supplies long-range-entangled data: anyons, fusion, braiding, topological ground-state degeneracy, and a long-distance TQFT. The symmetry enrichment supplies extra data: how the symmetry acts on anyons, whether anyons carry fractional quantum numbers, whether the symmetry permutes anyon types, what symmetry defects exist, and whether the whole pattern is anomaly-free.

An SET phase is therefore not just an SPT phase with a fancier name. SPT phases are short-range-entangled. SET phases are long-range-entangled. They already have intrinsic topological order before symmetry is considered.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Schematic of an SET phase: an underlying topological order with anyons, global symmetry action, symmetry fractionalization, anyon permutation, symmetry defects, and gauging diagnostic.](/figures/symmetry-anomalies-topology/set-fractionalization-defects.svg)

<figcaption>

An SET phase begins with intrinsic topological order $\mathcal C$ and then adds a global symmetry $G$. The symmetry may assign fractional quantum numbers to anyons, permute anyon types, introduce symmetry defects, or produce an obstruction that signals an anomalous boundary of a higher-dimensional phase.

</figcaption>
</figure>

The central questions are:

$$
\text{How does }G\text{ act on the anyons?}
$$

and

$$
\text{Can that action be consistently realized in a strictly }d\text{-dimensional system?}
$$

If the answer to the second question is no, the SET pattern is anomalous and must live as a boundary of a higher-dimensional SPT or more general invertible phase.

## Prerequisites

You should know [Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/), [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/), [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), and the basic notion of anyons in $2+1$ dimensions.

For a first pass, this vocabulary is enough:

| Word | Meaning |
|---|---|
| Anyon | A topological quasiparticle type in $2+1$ dimensions, with fusion and braiding data. |
| Topological order | Long-range-entangled phase with intrinsic topological data independent of local order parameters. |
| Symmetry fractionalization | Anyons carry symmetry quantum numbers not available to strictly local excitations. |
| Anyon permutation | Symmetry maps one anyon type to another. |
| Symmetry defect | An extrinsic twist defect associated with a symmetry element. |
| Gauging | Making the global symmetry dynamical; defects become deconfined excitations. |
| Anomalous SET | A symmetry-enrichment pattern impossible in strict $2+1$D, but possible on a boundary. |

This page emphasizes $2+1$D because anyon language is most concrete there. The general philosophy extends to higher-dimensional topological orders and higher-form symmetries, but the mathematics changes.

## Core idea

Start with a topological order $\mathcal C$. In $2+1$ dimensions, $\mathcal C$ can often be modeled by a unitary modular tensor category of anyons. It contains:

- anyon types $a,b,c,\ldots$;
- fusion rules $a\times b=\sum_cN_{ab}{}^c\,c$;
- braiding and topological spin data;
- a vacuum anyon $1$;
- antiparticles $\bar a$.

Now add a global symmetry group $G$. The symmetry can act on this topological data in several ways.

First, it can leave each anyon type fixed but let an anyon carry a fractionalized symmetry representation. For example, a spin liquid may have a spinon excitation that carries spin-$1/2$ even though all strictly local bosonic spin operators carry integer spin.

Second, the symmetry can permute anyons:

$$
g:a\mapsto g(a).
$$

This must preserve fusion and braiding data. If $a\times b$ can fuse to $c$, then $g(a)\times g(b)$ must fuse to $g(c)$.

Third, one can introduce symmetry defects. A $g$-defect is an extrinsic defect such that moving an anyon around it applies the symmetry action $g$ to the anyon.

The SET data are the consistent package of all these structures.

## Setup and conventions

Let $G$ be an ordinary global symmetry acting on a $2+1$D topological order $\mathcal C$. The symmetry action on anyon types is a homomorphism, up to equivalence,

$$
\rho:G\to \operatorname{Aut}(\mathcal C),
$$

where $\operatorname{Aut}(\mathcal C)$ means braided autoequivalences of the topological order: transformations preserving fusion, braiding, and topological spin.

If $\rho_g(a)=a$ for every $g$, the symmetry does not permute anyon types. Then the main enrichment is symmetry fractionalization.

If $\rho_g(a)$ can differ from $a$, then symmetry twists can move anyons between superselection sectors. The defect theory is richer and is naturally described by $G$-crossed braided data.

:::note[Source note: notation]
This page uses anyon-category notation only as much as needed for physics. The fully precise classification involves braided tensor categories, $G$-crossed extensions, obstruction classes, and equivalence relations. Those details belong partly to Mathematical and Rigorous QFT; here the goal is to teach the physical diagnostics.
:::

## Distinguishing SPT, topological order, and SET

It is helpful to separate three cases.

| Phase type | Intrinsic topological order? | Needs symmetry to be nontrivial? | Typical diagnostic |
|---|---:|---:|---|
| Trivial short-range-entangled phase | No | No | Product state after local circuit |
| SPT phase | No | Yes | Protected boundary, response action |
| Intrinsic topological order | Yes | No | Anyons, ground-state degeneracy |
| SET phase | Yes | Enrichment needs symmetry | Fractionalization, anyon permutation, symmetry defects |

An SET phase remains topologically ordered even if symmetry is broken. But the **enrichment** can disappear or change when the symmetry is broken.

For example, a $\mathbb Z_2$ topological order with anyons

$$
\{1,e,m,\epsilon\}
$$

is intrinsic topological order. If a global symmetry assigns spin-$1/2$ to $e$, that is additional SET data. Break spin-rotation symmetry, and the underlying topological order can remain while the enrichment is no longer meaningful.

## Symmetry fractionalization

Symmetry fractionalization means that an anyon can carry a projective or fractional symmetry quantum number even though local excitations carry only ordinary representations.

Suppose symmetry does not permute the anyon $a$. Acting by $g$ and then by $h$ on a state containing $a$ may differ from acting by $gh$ by fusing an Abelian anyon or by a phase invisible to local operators. Schematically,

$$
U_g^aU_h^a=\eta_a(g,h)U_{gh}^a.
$$

For simple Abelian fractionalization patterns, $\eta_a(g,h)$ behaves like a projective cocycle. Fusion imposes consistency. If $a\times b$ can fuse to $c$, then the fractionalization data must satisfy

$$
\eta_a(g,h)\eta_b(g,h)=\eta_c(g,h)
$$

up to the relevant equivalence relation.

In a toric-code spin liquid, the $e$ and $m$ anyons may carry different projective representations of a spin-rotation or lattice symmetry. These choices can produce distinct SET phases even though the underlying topological order is the same.

## Anyon permutation

Symmetry may permute anyon types. A simple possibility in $\mathbb Z_2$ topological order is an electric-magnetic duality exchanging

$$
e\leftrightarrow m.
$$

Such a symmetry cannot be described merely by assigning projective phases to fixed anyons. It changes the labels of superselection sectors.

If $\rho_g$ permutes anyons, then anyon worldlines crossing a $g$-defect can change type:

$$
a\quad\longrightarrow\quad \rho_g(a).
$$

This turns symmetry defects into powerful probes. Moving an anyon around a defect reveals the symmetry action, while fusing defects reveals higher consistency data.

Anyon permutation is one reason SET phases naturally connect to the defect and categorical chapters. The symmetry is not merely a representation on a Hilbert space; it is an action on the full topological operator algebra.

## Symmetry defects

A symmetry defect is an extrinsic defect labeled by $g\in G$. In two spatial dimensions, it is usually a pointlike defect in space, or a line in spacetime. Encircling it applies the symmetry action $g$.

A $g$-defect is not generally a deconfined anyon before gauging. It is an imposed twist defect. But the collection of defects carries fusion rules:

$$
\mathcal D_g\times \mathcal D_h
\sim
\sum_x N_{g,h}^{x}\,\mathcal D_{gh}^{\,x},
$$

where $x$ labels possible attached anyonic charges or defect species.

The defect category contains the data needed for gauging. If we gauge $G$, the extrinsic defects become dynamical fluxes. The resulting topological order depends on the full SET data, not just on $\mathcal C$ and $G$ separately.

This is why gauging is such a sharp diagnostic: two SET phases with the same anyons but different symmetry fractionalization can gauge to different topological orders.

## Obstruction and anomaly

Not every formally written symmetry action on anyons can occur in a strictly two-dimensional lattice system. Some fractionalization patterns or permutation actions are anomalous.

An anomaly means that the SET data cannot be consistently completed in the same dimension. Physically, the phase may occur as the boundary of a three-dimensional SPT phase. This is the SET analogue of the boundary anomaly story.

Mathematically, obstructions appear when trying to build the full $G$-crossed defect theory. If the obstruction vanishes, one can continue to classify possible defect fusion and associativity data. If it does not vanish, the symmetry-enrichment pattern is anomalous.

:::note[Anomaly warning]
An anomalous SET pattern is not nonsense. It is impossible as a standalone strictly $2+1$D system with onsite symmetry, but it can be perfectly meaningful as a surface state of a $3+1$D bulk SPT or topological phase.
:::

## Gauging an SET phase

Gauging $G$ promotes symmetry defects to dynamical excitations. The result is a new topological order, often denoted schematically as

$$
\mathcal C \quad\longrightarrow\quad \mathcal C/G,
$$

though the notation hides important choices.

If the symmetry is finite and anomaly-free, gauging includes:

1. adding dynamical $G$ gauge fields;
2. allowing $G$ flux defects as deconfined excitations;
3. projecting onto gauge-invariant sectors;
4. incorporating fractionalization and defect fusion data.

The gauged phase remembers the original SET data. In favorable cases, different SET phases gauge to inequivalent topological orders. This gives a practical classification diagnostic.

Gauging also shows why SPT and SET phases are related. Gauging a nontrivial SPT can produce a twisted gauge theory. Gauging an SET phase produces a richer topological order containing both the original anyon data and the new gauge-flux sectors.

## Examples

### Toric code enriched by symmetry

The toric code has anyons

$$
1,\quad e,\quad m,\quad \epsilon=e\times m.
$$

A global symmetry might assign fractional quantum numbers to $e$ and $m$. For instance, in a spin system, $e$ might transform as a spin-$1/2$ object. Since local spin operators carry integer spin, this is fractionalization.

There are also possible symmetries exchanging $e$ and $m$. Such an anyon-permuting symmetry requires defect language: a branch cut ending on a defect can turn an $e$ line into an $m$ line.

### Fractional quantum Hall states with symmetry

A fractional quantum Hall state has intrinsic topological order. Charge conservation enriches it because anyons carry fractional electric charge. The Laughlin quasiparticle at filling $\nu=1/m$ carries charge $1/m$ in units where the electron has charge $1$.

This is symmetry fractionalization with respect to $U(1)$ charge conservation. The topological order exists independently, but the physical electromagnetic symmetry supplies additional quantum-number data and response.

### Spin liquids

A quantum spin liquid may have emergent anyons such as spinons and visons. Microscopic symmetries such as spin rotation, time reversal, lattice translation, and point-group symmetry can act projectively on these anyons.

Different projective symmetry assignments can produce different spin liquids with the same underlying topological order. This is one reason SET language is central in modern spin-liquid classification.

## Relation to boundaries and Lieb–Schultz–Mattis constraints

Some SET patterns are forced by microscopic constraints. For example, systems with fractional filling or half-odd-integer spin per unit cell may be forbidden from having a unique, symmetric, trivially gapped ground state. A symmetric gapped phase may then need topological order, and its anyons may need specific fractional quantum numbers.

These constraints are modern descendants of Lieb–Schultz–Mattis-type theorems. In symmetry/anomaly language, the microscopic system carries an anomaly or obstruction that must be matched in the infrared. SET order is one possible way to match it.

Thus SET phases are not merely optional decorations of topological order. In some systems they are required by microscopic symmetry and filling data.

## Diagnostics

A practical SET checklist:

| Diagnostic | What it asks |
|---|---|
| Underlying topological order | What are the anyons, fusion rules, braiding, and topological spins? |
| Symmetry action | Does $G$ fix anyons or permute them? |
| Fractionalization | What projective or fractional quantum numbers do anyons carry? |
| Defects | What symmetry flux defects exist, and how do they fuse? |
| Gauging | What topological order appears after gauging $G$? |
| Obstruction | Can the data exist in strict dimension, or only at a boundary? |
| Boundary behavior | What symmetric gapped or gapless boundaries are allowed? |

The most robust tests involve combining several diagnostics. Fractional charge alone may not determine the phase. Defect fusion and gauging can reveal hidden distinctions.

## Common pitfalls

**“SET means any phase with symmetry and topological order.”** Not quite. The word “enriched” refers to the nontrivial way symmetry acts on topological data. A completely trivial symmetry action is less interesting, though still a symmetric topological order.

**“SPT and SET are the same because both need symmetry.”** No. SPT phases are short-range-entangled. SET phases have intrinsic topological order.

**“Fractionalization means fractional electric charge only.”** Electric charge is one example. Anyons can fractionalize spin, time reversal, lattice translations, point-group quantum numbers, or finite internal symmetries.

**“Anyon permutation is just relabeling.”** A global relabeling convention is not physical. A symmetry action that permutes anyons is physical when implemented by symmetry defects, boundary conditions, or gauging data.

**“Every algebraic fractionalization pattern is realizable.”** No. Some patterns are anomalous and require a higher-dimensional bulk.

**“Gauging loses information.”** Gauging changes the theory, but it often reveals SET data by turning symmetry defects into deconfined excitations.

## Relations to other pages

[Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/) explains short-range-entangled protected phases. This page adds intrinsic topological order and asks how symmetry enriches it.

[Topological Order Preview](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/topological-order-preview/) introduces the underlying anyon and long-range-entanglement data. [Anomaly-Boundary Correspondence](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/anomaly-boundary-correspondence/) explains anomalous SET patterns as boundary phenomena.

[Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) supplies the defect language. [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) supplies the language of extended charged objects. [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) gives a bulk-boundary packaging of symmetry, defects, gauging, and anomalies.

## Research status

The basic SET framework is established in $2+1$ dimensions: symmetry fractionalization, anyon permutation, symmetry defects, gauging, and obstruction/anomaly tests are standard tools.

Active research includes fermionic SET phases, antiunitary and crystalline symmetries, space-group enrichment, higher-dimensional topological order, higher-form symmetry enrichment, subsystem and fracton orders, non-invertible symmetry enrichment, tensor-network constructions, and boundary/anomaly classifications. There is also ongoing work connecting SET patterns to microscopic constraints such as filling, translation symmetry, and generalized Lieb–Schultz–Mattis theorems.

## Exercises

### Exercise 1: SPT versus SET

Explain why a nontrivial SPT phase is not an SET phase in the usual terminology.

<details><summary><strong>Solution</strong></summary>

An SPT phase is short-range-entangled and has no intrinsic topological order. It may have protected boundary modes or nontrivial response, but it has no deconfined bulk anyons or topological ground-state degeneracy. An SET phase is intrinsic topological order enriched by symmetry. Thus SET phases require long-range entanglement, while SPT phases do not.

</details>

### Exercise 2: Fusion constraint on fractionalization

Suppose $a\times b=c$ and the anyons do not get permuted by the symmetry. If $a$ and $b$ carry projective phases $\eta_a(g,h)$ and $\eta_b(g,h)$, what consistency condition should $\eta_c(g,h)$ satisfy?

<details><summary><strong>Solution</strong></summary>

Because fusion should be compatible with symmetry, the fractionalization of the fusion product should equal the product of fractionalization phases:

$$
\eta_c(g,h)=\eta_a(g,h)\eta_b(g,h),
$$

up to the equivalence relations allowed by attaching local particles or redefining phases. The precise statement can be more subtle when fusion spaces have multiplicity, but this is the core constraint.

</details>

### Exercise 3: Anyon permutation

In the toric code, suppose a symmetry exchanges $e$ and $m$. What happens to an $e$ line crossing a branch cut ending on the corresponding symmetry defect?

<details><summary><strong>Solution</strong></summary>

Crossing the branch cut applies the symmetry action. Since the symmetry exchanges $e$ and $m$, the $e$ line becomes an $m$ line after crossing. Encircling the defect detects the same action: the anyon type is permuted by the monodromy around the defect.

</details>

### Exercise 4: Gauging as a diagnostic

Why can two SET phases with the same underlying anyon theory become different topological orders after gauging the same symmetry?

<details><summary><strong>Solution</strong></summary>

The underlying anyon theory $\mathcal C$ does not include all symmetry data. Two SET phases may differ in symmetry fractionalization, anyon permutation, or defect fusion. Gauging makes symmetry defects dynamical, so those differences become part of the anyon content, fusion, and braiding of the gauged theory. Therefore the gauged topological orders can be distinct.

</details>

## References

- M. Barkeshli, P. Bonderson, M. Cheng, and Z. Wang, “Symmetry Fractionalization, Defects, and Gauging of Topological Phases.”
- Y.-M. Lu and A. Vishwanath, “Classification and Properties of Symmetry Enriched Topological Phases: A Chern–Simons Approach with Applications to $\mathbb Z_2$ Spin Liquids.”
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for topological order, anyons, and quantum order.
- D. J. Williamson, N. Bultinck, and F. Verstraete, “Symmetry-Enriched Topological Order in Tensor Networks: Defects, Gauging and Anyon Condensation.”
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- A. Kitaev, “Anyons in an Exactly Solved Model and Beyond.”
- M. Levin and X.-G. Wen, “String-Net Condensation: A Physical Mechanism for Topological Phases.”

## Version history

- **2026-06-23:** Initial polished draft. Added SET definition, symmetry fractionalization, anyon permutation, symmetry defects, gauging diagnostic, anomaly/obstruction warnings, examples, and exercises.
