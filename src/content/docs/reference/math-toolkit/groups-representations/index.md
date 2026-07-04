---
title: "Lie Groups, Lie Algebras, and Representations"
description: "Chapter overview for groups, Lie algebras, representations, Lorentz and Poincaré symmetry, compact gauge groups, weights, roots, characters, Young tableaux, and gauge-theory group data in the Mathematical Toolkit volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard group theory and representation theory for QFT, including Georgi, Hall, Fulton–Harris, Tung, Cornwell, Weinberg, Srednicki, Coleman, Schwartz, and gauge-theory references."
topics:
  - Lie groups
  - Lie algebras
  - representation theory
  - Lorentz group
  - Poincaré group
  - gauge groups
canonicalTopics:
  - lie-groups
  - lie-algebras
  - representation-theory
  - lorentz-group
  - poincare-group
  - compact-gauge-groups
researchStatus:
  established:
    - "Lie groups, Lie algebras, and their representations are the standard mathematical language for spacetime symmetry, internal symmetry, spin, particle multiplets, and gauge-theory group factors in QFT."
  active:
    - "Modern QFT also uses representation theory of infinite-dimensional algebras, quantum groups, tensor categories, higher symmetries, non-invertible symmetries, and categorical structures, which are treated elsewhere after the finite-dimensional toolkit is in place."
---

Lie Groups, Lie Algebras, and Representations is the chapter in the Mathematical Toolkit volume where symmetry becomes calculable. A symmetry is not useful only because it sounds elegant; it is useful because it tells us how states, fields, operators, currents, charges, defects, and amplitudes transform.

This chapter exists because QFT constantly asks representation-theoretic questions. What Lorentz representation does a field carry? Which spin labels describe a particle? Which gauge representation contains a quark? Which invariant tensors can appear in an interaction? Which Casimir controls a beta function, anomaly coefficient, or color factor?

The basic slogan is

$$
\text{symmetry data}
=
\text{group }G
+
\text{representations }V
+
\text{invariant maps between them}.
$$

The group says what transformations are allowed. A representation says how a vector space of fields, states, or operators transforms. Invariant tensors say which combinations can appear in actions, correlation functions, scattering amplitudes, and selection rules.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Concept map from a symmetry group to its Lie algebra, representations, generators, invariant tensors, Casimirs, and QFT uses such as fields, charges, multiplets, and gauge interactions.](/figures/math-toolkit/groups-representations-map.svg)

<figcaption>

The QFT use of representation theory. A group $G$ has a Lie algebra $\mathfrak g$ near the identity. A representation assigns matrices $T^a$ to generators. Invariant tensors, Casimirs, weights, roots, and characters then organize fields, particles, currents, gauge interactions, Ward identities, and amplitudes.

</figcaption>
</figure>

This chapter is not a pure-math survey of all representation theory. It is the reusable QFT-facing layer: finite-dimensional Lie groups and Lie algebras, Lorentz and Poincaré representations, compact gauge groups, roots and weights, characters, Young tableaux, and the group-theory data needed for gauge theories and perturbation theory.

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/) page, especially the conventions for indices, traces, Lie-algebra generators, and complex conjugation. Basic linear algebra is assumed: vector spaces, duals, tensor products, eigenvectors, bilinear forms, and change of basis.

It is useful, but not required at the entrance, to know the phase-space meaning of charges from [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/) and the constraint language from [Constraints Preview](/math-toolkit/calculus-of-variations-and-phase-space/constraints-preview/). Symmetry generators in QFT are ultimately charges, and charges act by brackets or commutators.

No differential geometry is required for the first pass through this chapter. Connections, bundles, holonomy, and characteristic classes belong to later geometry and topology chapters.

## Reading path

Start with **Groups and Algebras**. The goal is to distinguish a group, an algebra, a representation, a generator, and an invariant tensor. Do not rush this distinction. Many later sign and normalization problems are just this distinction wearing a trench coat.

Then read **Lie Groups and Lie Algebras**. This page should fix the exponential map, structure constants, adjoint representation, Hermitian versus anti-Hermitian generator conventions, and the relation between infinitesimal and finite transformations.

Next read **SU(2) and Angular Momentum**. $SU(2)$ is the training ground for almost everything: spin, tensor products, Clebsch–Gordan decomposition, raising and lowering operators, characters, and the difference between group representations and Lie-algebra representations.

After that, read **SL(2,C) and the Lorentz Group**. This is the bridge to relativistic QFT. Weyl spinors, dotted and undotted indices, four-vectors, and finite-dimensional Lorentz representations all sit here.

Then read **Poincaré Group**. Particle states are not classified only by finite-dimensional Lorentz representations. They are classified by unitary irreducible representations of the Poincaré group, with mass and spin or helicity labels. This is where the Wigner little group enters.

For gauge theory, move through **Compact Lie Groups**, **Roots, Weights, and Dynkin Diagrams**, **Characters**, **Young Tableaux**, and **Gauge Group Data**. These pages should gradually build the information needed to compute dimensions, tensor-product decompositions, Casimirs, Dynkin indices, anomaly coefficients, and color factors.

A practical reading order is:

```txt
Groups and Algebras
Lie Groups and Lie Algebras
SU(2) and Angular Momentum
SL(2,C) and the Lorentz Group
Poincaré Group
Compact Lie Groups
Roots, Weights, and Dynkin Diagrams
Characters
Young Tableaux
Gauge Group Data
```

Readers mainly interested in spinors may read through **SL(2,C) and the Lorentz Group** and then continue to the Clifford Algebras and Spinors chapter. Readers mainly interested in Yang–Mills theory should continue through **Gauge Group Data**.

## Landmarks

The first landmark is a **group action**. A group $G$ acts on a set $X$ if each $g\in G$ gives a map $X\to X$ compatible with multiplication:

$$
g_1(g_2x)=(g_1g_2)x,
\qquad
ex=x.
$$

In QFT, $X$ might be a space of fields, states, operators, vacua, couplings, or defects.

The second landmark is a **linear representation**. A representation of $G$ on a vector space $V$ is a homomorphism

$$
\rho:G\to GL(V).
$$

The representation property is

$$
\rho(g_1g_2)=\rho(g_1)\rho(g_2).
$$

When a field $\phi^i$ transforms in a representation $R$, a finite transformation is written schematically as

$$
\phi^i\mapsto R(g)^i{}_j\phi^j.
$$

The third landmark is the **Lie algebra**. Near the identity, a Lie group is described infinitesimally by generators. In a common physicist convention for compact groups, the representation matrices $T^a_R$ are Hermitian and obey

$$
[T_R^a,T_R^b]=i f^{ab}{}_c T_R^c.
$$

Mathematicians often prefer anti-Hermitian generators with no explicit $i$. Both conventions are legitimate. The page-level convention must be stated before comparing formulas.

The fourth landmark is an **invariant tensor**. A tensor $I_{i_1\cdots i_n}$ is invariant if it is unchanged by the group action. Infinitesimally, this means the sum of generator actions on every index vanishes. Invariant tensors decide which expressions can appear in a Lagrangian or correlator. For example, a mass term for complex fields in representation $R$ needs an invariant pairing between $R^*$ and $R$.

The fifth landmark is **irreducible decomposition**. A representation is irreducible if it has no nontrivial invariant subspace. Decompositions such as

$$
R_1\otimes R_2=\bigoplus_i N_i R_i
$$

organize angular momentum addition, particle multiplets, operator products, tensor structures, and color factors.

The sixth landmark is the **Casimir operator**. For a simple Lie algebra, the quadratic Casimir in representation $R$ is

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R,
$$

with the repeated adjoint index contracted using the chosen invariant metric on the algebra. The Dynkin index $T(R)$ is defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}
$$

in a chosen normalization. The numbers $C_2(R)$, $T(R)$, and $C_2(G)$ appear constantly in beta functions, anomalies, Wilson loops, and scattering amplitudes.

The seventh landmark is the **Lorentz/Poincaré split**. Fields usually transform in finite-dimensional representations of the Lorentz group or its double cover. Particles are classified by unitary irreducible representations of the Poincaré group. These are related, but they are not the same classification problem.

For massive particles in $3+1$ dimensions, the little group is $SO(3)$ or its double cover $SU(2)$, giving spin $s$. For massless particles, the physical little-group representations are labeled by helicity. This is why a vector field, a photon state, and a gauge redundancy are entangled but not identical.

The eighth landmark is **gauge group data**. A gauge theory requires a choice of gauge group $G$, matter representations $R_i$, invariant tensors for couplings, and global information such as the center and possible quotient by a subgroup. The same Lie algebra can correspond to different global groups, and that difference can matter for line operators, magnetic charges, instantons, and generalized symmetries.

## Common confusions

**A group is not its Lie algebra.** The Lie algebra describes infinitesimal transformations near the identity. The global group also contains topology, center, disconnected components, and representation-integrality data. $SU(2)$ and $SO(3)$ have the same Lie algebra but different representations and different global physics.

**A representation is not a choice of matrices.** Matrices are a basis-dependent description of a representation. The representation is the abstract action on a vector space. Changing basis changes matrices but not the representation.

**A field representation is not automatically a particle representation.** Local fields transform in finite-dimensional Lorentz representations. One-particle Hilbert-space states transform in unitary irreducible Poincaré representations. Gauge fields make this distinction extra visible.

**A gauge symmetry is not an ordinary physical symmetry.** Gauge transformations are redundancies of description. Global symmetries act on physical states and operators. Boundary conditions and large gauge transformations can blur the naive distinction, which is exactly why the distinction has to be made carefully.

**The fundamental representation is not always “the smallest thing.”** For $SU(N)$ the defining $N$-dimensional representation is usually called fundamental. For other groups, “fundamental representation” can mean one associated with a fundamental weight. Context matters.

**Real, complex, and pseudoreal representations behave differently.** The existence of invariant bilinear forms controls whether fields can satisfy Majorana-like reality conditions, whether representations are equivalent to their conjugates, and how global anomalies can appear.

**Dynkin labels are not weights themselves.** Dynkin labels are coordinates of a highest weight in the basis of fundamental weights. They are excellent labels, but they should not be confused with weight vectors in an arbitrary basis.

**Normalization is not optional.** The same formula for a beta function or anomaly coefficient can differ by factors of $2$ if $T(R)$ and $C_2(R)$ are normalized differently. Always identify the trace convention.

## Boundaries

This chapter stops at the finite-dimensional representation theory and Lie-theoretic data most commonly used in graduate QFT. It does not try to replace a full representation-theory textbook.

Spinor conventions, gamma matrices, Clifford algebras, Fierz identities, and spinor helicity are treated in the Clifford Algebras and Spinors chapter. This chapter supplies the Lorentz-group bridge, but it does not become the full spinor chapter.

Bundles, connections, curvature, holonomy, characteristic classes, and index theorems belong to the geometry and topology chapters. This chapter explains gauge-group representation data; geometry explains gauge fields as connections.

Infinite-dimensional representation theory, Virasoro algebras, affine Kac–Moody algebras, vertex operator algebras, conformal blocks, and modular tensor categories belong mainly to CFT, algebraic/categorical language, and rigorous QFT pages.

Higher-form symmetries, non-invertible symmetries, symmetry TFTs, and categorical symmetries are not introduced here as primary topics. They use representation-like ideas, but their natural home is later, after ordinary group representation theory is solid.

## Where to go next

If your goal is relativistic fields, go next to the Lorentz and spinor pages in this chapter, then to the Clifford Algebras and Spinors chapter.

If your goal is gauge theory, read through compact Lie groups, roots and weights, characters, Young tableaux, and gauge group data. The important computational outputs are representation dimensions, invariant tensors, Casimirs, Dynkin indices, and conjugacy properties.

If your goal is canonical symmetry, connect this chapter to [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/) and [Constraints Preview](/math-toolkit/calculus-of-variations-and-phase-space/constraints-preview/). Charges generate symmetry transformations, and gauge generators are constrained Hamiltonian objects.

If your goal is scattering amplitudes, pay special attention to Lorentz representations, little-group weights, spinor representations, and invariant tensors. Those are the algebraic skeleton behind polarization sums, helicity amplitudes, color ordering, and selection rules.

The next pages to write in this chapter should be **Groups and Algebras** and **Lie Groups and Lie Algebras**. They will set the notation for everything that follows.

## References

- H. Georgi, *Lie Algebras in Particle Physics*, a standard physics-oriented source for Lie algebras, representations, weights, roots, and particle-physics applications.
- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, a clear bridge between mathematical and physical conventions.
- W. Fulton and J. Harris, *Representation Theory*, a standard mathematically precise reference for finite-dimensional representation theory.
- W.-K. Tung, *Group Theory in Physics*, for physical representation theory and spacetime-symmetry applications.
- J. F. Cornwell, *Group Theory in Physics*, for detailed group-theory technology used in particle physics.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Poincaré representations, Lorentz invariance, one-particle states, and quantum fields; Vol. II for gauge groups and non-Abelian gauge theories.
- M. Srednicki, *Quantum Field Theory*, especially the sections on Lorentz representations, spinors, non-Abelian symmetry, group representations, non-Abelian gauge theory, and BRST symmetry.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the Lorentz, spinor, Yang–Mills, and Standard Model group-theory material.
- S. Coleman, *Aspects of Symmetry* and *Lectures of Sidney Coleman on Quantum Field Theory*, for symmetry, current algebra, spontaneous symmetry breaking, gauge theory, and representation-theoretic physics examples.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
