---
title: "Nonabelian Bosonization Preview"
description: "How two-dimensional free fermions with nonabelian symmetry can be reorganized into WZW current algebras, charge sectors, and bosonic matrix fields."
sidebar:
  label: "Nonabelian Bosonization"
  order: 11
level: Graduate
status: "Polished draft"
source: "Witten 1984; Di Francesco, Mathieu, and Senechal chs. 14–16; Fradkin; Affleck; standard bosonization and WZW literature."
topics:
  - nonabelian bosonization
  - WZW models
  - free fermions
  - current algebra
  - spin chains
canonicalTopics:
  - nonabelian-bosonization
  - free-fermion-current-algebras
  - conformal-embedding
researchStatus:
  established:
    - "Two-dimensional free fermions with nonabelian internal symmetry generate affine current algebras, and their low-energy sectors can be reorganized in terms of WZW models and charge bosons."
  active:
    - "Modern applications include spin chains, quantum Hall edges, coupled-wire constructions, dualities, boundary CFT, non-invertible symmetries, and fermionic rational CFTs."
---

## Summary

**Nonabelian bosonization** is the two-dimensional equivalence between certain free-fermion theories and bosonic current-algebra CFTs. It generalizes ordinary abelian bosonization, where a free Dirac fermion is rewritten in terms of a compact boson.

The simplest slogan is

$$
\text{free fermions with nonabelian symmetry}
\quad\Longleftrightarrow\quad
\text{WZW model plus charge sectors}.
$$

For example, $N$ complex chiral fermions generate an affine $U(N)_1$ current algebra. This can be decomposed schematically as

$$
U(N)_1\simeq \frac{SU(N)_1\times U(1)}{\mathbb Z_N},
$$

so the fermion theory can be reorganized into a nonabelian $SU(N)_1$ WZW sector and an abelian charge boson.

More generally, $N_cN_f$ complex fermions carrying color and flavor indices realize the conformal embedding

$$
U(N_cN_f)_1
\supset
SU(N_c)_{N_f}\times SU(N_f)_{N_c}\times U(1),
$$

up to global identifications. This one formula is the backbone of many applications: spin chains, nonabelian Luttinger liquids, two-dimensional gauge theories, quantum Hall edges, and current-algebra decompositions of free fermions.

This page is a preview. It explains the dictionary, the central-charge checks, the origin of the levels, and the common traps. Detailed condensed-matter and gauge-theory applications belong to later chapters.

## Prerequisites

Read [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/), [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/), [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), and [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) first.

You should know how a holomorphic current OPE encodes an affine Lie algebra and why a compact WZW model at positive integer level has finitely many integrable primaries.

## Core idea

In two dimensions, fermion bilinears can behave as bosonic currents. If $\psi^i(z)$ are free chiral fermions, the bilinears

$$
J^a(z)=:\psi_i^\dagger (T^a)^i{}_j\psi^j:(z)
$$

are holomorphic currents. Their OPE is an affine current algebra:

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The level $k$ is determined by the representation and the number of fermion copies. With the standard WZW normalization, $N_f$ copies of fundamental fermions of $SU(N_c)$ generate

$$
SU(N_c)_{N_f}.
$$

Thus a free-fermion theory secretly contains WZW current algebras. Nonabelian bosonization is the statement that, in two dimensions, these current-algebra sectors can often be used as an equivalent bosonic description of the fermionic theory.

The slogan is

$$
\text{fermion bilinears}
\quad\Longrightarrow\quad
\text{affine currents}
\quad\Longrightarrow\quad
\text{WZW sectors}.
$$

## Setup and conventions

Consider left-moving complex fermions with OPE

$$
\psi^I(z)\psi_J^\dagger(w)\sim\frac{\delta^I{}_J}{z-w}.
$$

A single complex chiral fermion has central charge

$$
c=1.
$$

A real chiral Majorana fermion has central charge

$$
c=\frac12.
$$

For fermions transforming in a representation $R$ of a Lie algebra $\mathfrak g$, define currents

$$
J^a(z)=:\psi^\dagger T_R^a\psi:(z).
$$

Then

$$
J^a(z)J^b(w)
\sim
\frac{\operatorname{Tr}_R(T^aT^b)}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

In the WZW convention used in this chapter, the level is read from

$$
\operatorname{Tr}_R(T^aT^b)=k\kappa^{ab}.
$$

This is why normalization matters. A statement such as “free fermions generate level one” assumes a current metric in which the fundamental representation has index one.

## Abelian bosonization as the warmup

A single complex Dirac fermion in two dimensions can be bosonized as a compact boson. In chiral language, the $U(1)$ current is

$$
J(z)=:\psi^\dagger\psi:(z).
$$

It has OPE

$$
J(z)J(w)\sim\frac{1}{(z-w)^2}
$$

in the usual charge-one normalization. One writes

$$
J(z)=i\partial\varphi(z)
$$

for a chiral boson $\varphi$ with

$$
\varphi(z)\varphi(w)\sim -\log(z-w).
$$

The fermion itself is represented by a vertex operator,

$$
\psi(z)\sim :e^{i\varphi(z)}:,
$$

up to cocycles and normalization.

Nonabelian bosonization keeps this idea but replaces the scalar charge boson by a matrix-valued WZW field for the nonabelian sector. The abelian charge sector often remains as an ordinary compact boson.

## N complex fermions and U(N) at level one

Take $N$ complex chiral fermions

$$
\psi^i(z),
\qquad i=1,\ldots,N.
$$

The bilinears

$$
J^i{}_j(z)=:\psi_j^\dagger\psi^i:(z)
$$

generate $U(N)_1$. Splitting trace and traceless parts gives

$$
U(N)_1\sim SU(N)_1\times U(1)
$$

with a global $\mathbb Z_N$ identification.

The central charges check perfectly. The free fermions have

$$
c_{\rm fermions}=N.
$$

The $SU(N)_1$ WZW central charge is

$$
c_{SU(N)_1}=\frac{1(N^2-1)}{1+N}=N-1.
$$

The $U(1)$ charge boson contributes

$$
c_{U(1)}=1.
$$

Therefore

$$
c_{SU(N)_1}+c_{U(1)}=(N-1)+1=N.
$$

This central-charge identity is the first sanity check of nonabelian bosonization.

## Color-flavor decomposition

Now take fermions with two labels:

$$
\psi^{a\alpha}(z),
\qquad
 a=1,\ldots,N_c,
\qquad
\alpha=1,\ldots,N_f.
$$

Here $a$ is a color index and $\alpha$ is a flavor index. The free chiral fermions have central charge

$$
c=N_cN_f.
$$

They generate the large current algebra

$$
U(N_cN_f)_1.
$$

Inside it are commuting current algebras

$$
SU(N_c)_{N_f},
\qquad
SU(N_f)_{N_c},
\qquad
U(1).
$$

The levels are exchanged: $N_f$ flavors of color fundamentals generate $SU(N_c)_{N_f}$, and $N_c$ colors of flavor fundamentals generate $SU(N_f)_{N_c}$.

The central-charge identity is

$$
N_cN_f
=\frac{N_f(N_c^2-1)}{N_f+N_c}
+\frac{N_c(N_f^2-1)}{N_c+N_f}
+1.
$$

The first term is $c_{SU(N_c)_{N_f}}$, the second is $c_{SU(N_f)_{N_c}}$, and the last is the $U(1)$ charge boson.

This decomposition is often summarized as

$$
U(N_cN_f)_1
\supset
SU(N_c)_{N_f}\times SU(N_f)_{N_c}\times U(1),
$$

with global identifications that matter for the exact operator spectrum.

## What happens to the fermion field?

In abelian bosonization, the fermion becomes a vertex operator. In nonabelian bosonization, the fermion is not represented by the WZW current alone. It carries charge under several sectors.

For the color-flavor decomposition, a fermion transforms simultaneously under

$$
SU(N_c)_{N_f},
\qquad
SU(N_f)_{N_c},
\qquad
U(1).
$$

Schematic bosonization therefore has the form

$$
\psi^{a\alpha}
\sim
\left(\text{color WZW primary}\right)^a
\left(\text{flavor WZW primary}\right)^\alpha
\left(\text{charge vertex operator}\right).
$$

This schematic formula hides cocycles, spin structures, branch cuts, and global identifications. It is still conceptually useful: the fermion factorizes into charge and nonabelian sectors.

The currents are simpler than the fermion operators. Current bilinears map directly to WZW currents, while fermions themselves are often nonlocal with respect to the purely bosonic variables unless the full charge and cocycle data are included.

## Matrix field and WZW action

A WZW model contains a group-valued field

$$
g(z,\bar z)\in G.
$$

For nonabelian bosonization, this matrix field is the bosonic variable that captures the nonabelian fermion bilinear sector. In many applications, fermion mass terms or order parameters map to traces of $g$ multiplied by charge-sector vertex operators.

For example, a schematic fermion bilinear can map as

$$
\psi_L^\dagger\psi_R
\quad\longleftrightarrow\quad
\text{charge vertex}\times g,
$$

with representation indices suppressed.

The WZW action for $g$ is

$$
S_{\rm WZW}[g]
=\frac{k}{8\pi}\int_\Sigma \operatorname{Tr}(g^{-1}\partial_\mu g\,g^{-1}\partial^\mu g)
+\frac{k}{12\pi}\int_B\operatorname{Tr}(g^{-1}dg)^3,
$$

up to Euclidean factors and trace conventions. The level $k$ is fixed by the number of fermion species in the corresponding current algebra.

The Wess–Zumino term is not an optional decoration. It encodes the anomalous and current-algebra structure of the fermions.

## Spin chains and SU(2) at level one

One of the most important condensed-matter applications is the spin-$1/2$ antiferromagnetic Heisenberg chain. Its low-energy fixed point is described by the

$$
SU(2)_1
$$

WZW model.

The central charge is

$$
c=\frac{3\cdot1}{1+2}=1,
$$

matching a compact boson. The spin operator decomposes schematically into a smooth current part and a staggered WZW primary part:

$$
\mathbf S_n
\sim
\mathbf J_L(x)+\mathbf J_R(x)+(-1)^n\mathbf n(x)+\cdots.
$$

Here $\mathbf J_L$ and $\mathbf J_R$ are chiral $SU(2)$ currents, and $\mathbf n$ is related to the $SU(2)$ matrix primary $g$. The currents have dimension one, while the staggered field has lower dimension and controls the dominant spin correlations.

This example is a good warning: nonabelian bosonization is not only a particle-physics curiosity. It is one of the standard languages of one-dimensional quantum matter.

## Nonabelian Luttinger liquids

A one-dimensional fermion system with spin or flavor symmetry often separates into charge and spin sectors. For spinful electrons, the low-energy theory has a charge boson and a spin sector described by

$$
SU(2)_1.
$$

Schematically,

$$
\text{spinful Dirac fermions}
\quad\longrightarrow\quad
U(1)_{\rm charge}\times SU(2)_1{}_{\rm spin}.
$$

Interactions can affect the charge Luttinger parameter while preserving the $SU(2)_1$ spin current algebra if spin symmetry remains exact. This is the field-theory origin of spin-charge separation in many one-dimensional systems.

For systems with larger internal symmetry, the spin or flavor sector may become an $SU(N)_k$ WZW model. Nonabelian bosonization is then the natural language for classifying perturbations, computing scaling dimensions, and understanding boundary conditions.

## Two-dimensional gauge theory preview

Nonabelian bosonization is also useful in two-dimensional gauge theory. Fermions coupled to gauge fields can be rewritten in terms of WZW variables, and gauging a symmetry can remove the corresponding current-algebra sector.

This is closely related to coset logic. If fermions decompose as

$$
U(N_cN_f)_1
\supset
SU(N_c)_{N_f}\times SU(N_f)_{N_c}\times U(1),
$$

then gauging the color symmetry interacts strongly with the $SU(N_c)_{N_f}$ sector. The remaining gauge-invariant spectrum can often be described using flavor WZW sectors, charge sectors, and constraints.

This is only a preview. Two-dimensional gauge theory has its own subtleties: confinement, anomalies, mass terms, zero modes, and global structure. The point here is that nonabelian bosonization supplies a dictionary in which gauge and flavor currents are explicit.

## Relation to conformal embedding

A **conformal embedding** is an inclusion of chiral algebras such that the Sugawara stress tensor of the subalgebra equals the stress tensor of the larger algebra, or accounts for a full factorization with no missing central charge.

For free fermions, the embedding

$$
SU(N_c)_{N_f}\times SU(N_f)_{N_c}\times U(1)
\subset U(N_cN_f)_1
$$

is conformal because the central charges add to the free-fermion central charge:

$$
c_{SU(N_c)_{N_f}}+c_{SU(N_f)_{N_c}}+1=N_cN_f.
$$

This means the free-fermion stress tensor can be decomposed into commuting Sugawara stress tensors for the color, flavor, and charge sectors:

$$
T_{\rm fermion}=T_{\rm color}+T_{\rm flavor}+T_{U(1)}.
$$

This is the clean algebraic reason sector separation works.

## Operators and global identifications

The symbolic equality

$$
U(N)_1\simeq SU(N)_1\times U(1)
$$

is slightly too naive. There is a global identification by a shared center, often written schematically as

$$
U(N)_1\simeq\frac{SU(N)_1\times U(1)}{\mathbb Z_N}.
$$

This matters for operator spectra. Not every product of an $SU(N)_1$ primary and a $U(1)$ vertex operator is a genuine fermion-theory operator. Allowed operators must obey compatibility conditions between their nonabelian center charge and their abelian charge.

The same warning applies to color-flavor decompositions. The local operator spectrum is not just the Cartesian product of three independent sectors. It is a product followed by a quotient or selection rule imposed by the original fermions.

This is the bosonization analogue of field identification in coset CFT.

## Perturbations

Nonabelian bosonization is especially useful because many fermion perturbations have simple bosonic interpretations.

Examples include:

| Fermion-side perturbation | Bosonized interpretation |
|---|---|
| Current-current interaction | Marginal perturbation of WZW currents. |
| Fermion mass | WZW primary times charge vertex, depending on symmetry. |
| Spin exchange in chains | Current-current perturbation plus relevant staggered operators. |
| Four-fermion interaction | Products of charge and nonabelian currents or primaries. |
| Gauging a symmetry | Coupling to a current algebra, often leading to a coset. |

For instance, a marginal interaction of the form

$$
J_L^aJ_R^a
$$

can be analyzed using current algebra. Depending on its sign and the model, it may be marginally irrelevant, marginally relevant, or exactly marginal. This is a standard tool in one-dimensional quantum matter.

The key benefit is that the bosonic WZW description makes symmetry and scaling dimensions transparent.

## Common pitfalls

**Do not confuse abelian and nonabelian bosonization.** Abelian bosonization uses compact scalar fields. Nonabelian bosonization uses WZW matrix fields and affine current algebras, often together with charge bosons.

**Do not forget the charge sector.** The nonabelian WZW model alone usually does not reproduce the full fermion operator. Fermions also carry $U(1)$ charge and cocycle data.

**Do not ignore global quotients.** Expressions such as $SU(N)_1\times U(1)$ need a $\mathbb Z_N$ identification to reproduce the true local operator spectrum of $U(N)_1$ fermions.

**Do not compare levels without fixing trace conventions.** The statement that fundamental fermions generate level one assumes a standard current metric.

**Do not treat fermions as local operators of the nonabelian sector alone.** Fermions are local in the full fermionic theory. Their representation in bosonic sectors can involve spin structures, cocycles, and branch cuts.

**Do not assume bosonization is only a UV trick.** In many condensed-matter problems, nonabelian bosonization describes the universal infrared fixed point and its perturbations.

**Do not forget right movers.** A full nonchiral theory has left and right current algebras, and perturbations often couple the two.

## Relations to other pages

This page follows [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) because nonabelian bosonization often decomposes free fermions into WZW and coset sectors. It uses [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), and [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) throughout.

It connects backward to [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) and [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/). It prepares later material on spin chains, Luttinger liquids, quantum Hall edges, boundary CFT, and two-dimensional gauge theories.

For rational-CFT structure, it connects to [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/).

## Research status

Nonabelian bosonization in two-dimensional CFT is established. The current-algebra, WZW, and conformal-embedding descriptions of free fermions are standard tools.

Active work uses and extends these ideas in fermionic rational CFT, boundary and defect CFT, non-invertible symmetries, coupled-wire constructions, quantum Hall edges, non-Fermi liquids in one dimension, dualities, and spin-chain classifications. In these settings, global structure and locality conditions are often the subtle part, not the local current algebra.

## Exercises

### Exercise 1

Check the central-charge identity

$$
U(N)_1\simeq \frac{SU(N)_1\times U(1)}{\mathbb Z_N}
$$

at the level of central charges.

<details><summary><strong>Solution</strong></summary>

$N$ complex chiral fermions have

$$
c=N.
$$

The $SU(N)_1$ WZW model has

$$
c_{SU(N)_1}=\frac{1(N^2-1)}{1+N}=N-1.
$$

A single $U(1)$ chiral boson has

$$
c=1.
$$

Thus

$$
c_{SU(N)_1}+c_{U(1)}=(N-1)+1=N,
$$

matching the free fermions. The $\mathbb Z_N$ quotient affects the operator spectrum, not the central charge.

</details>

### Exercise 2

Show that

$$
c_{SU(N_c)_{N_f}}+c_{SU(N_f)_{N_c}}+1=N_cN_f.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
c_{SU(N)_k}=\frac{k(N^2-1)}{k+N}.
$$

Then

$$
c_{SU(N_c)_{N_f}}
=\frac{N_f(N_c^2-1)}{N_f+N_c},
$$

and

$$
c_{SU(N_f)_{N_c}}
=\frac{N_c(N_f^2-1)}{N_c+N_f}.
$$

Adding them gives

$$
\frac{N_fN_c^2-N_f+N_cN_f^2-N_c}{N_c+N_f}
=\frac{N_cN_f(N_c+N_f)-(N_c+N_f)}{N_c+N_f}
=N_cN_f-1.
$$

Adding the $U(1)$ central charge gives

$$
N_cN_f.
$$

</details>

### Exercise 3

Why do $N_f$ copies of fundamental fermions of $SU(N_c)$ generate level $N_f$?

<details><summary><strong>Solution</strong></summary>

Each flavor copy contributes the same current-current double pole. If the current is

$$
J^a=\sum_{\alpha=1}^{N_f}:\psi^\dagger_{\alpha}T^a\psi_\alpha:,
$$

then the two-point singularity is the sum of $N_f$ identical contractions. In the convention where one fundamental copy gives level one, the total level is therefore

$$
k=N_f.
$$

Equivalently, the level is additive over independent fermion species.

</details>

### Exercise 4

Why is the nonabelian WZW sector alone not enough to represent a fermion operator?

<details><summary><strong>Solution</strong></summary>

A fermion carries nonabelian representation labels and abelian charge. In the decomposition

$$
U(N)_1\simeq \frac{SU(N)_1\times U(1)}{\mathbb Z_N},
$$

the $SU(N)_1$ sector captures the nonabelian transformation, while the $U(1)$ vertex operator carries the fermion charge. Cocycles and global identifications ensure the correct fermionic statistics and locality.

Therefore the fermion is represented by a compatible product of nonabelian and abelian sector operators, not by the WZW primary alone.

</details>

## References

- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- I. Affleck, “Field theory methods and quantum critical phenomena,” Les Houches lectures, 1988.
- I. Affleck, “Exact critical exponents for quantum spin chains, non-linear sigma-models at theta equals pi and the quantum Hall effect,” *Nuclear Physics B* **265** (1986).
- E. Fradkin, *Field Theories of Condensed Matter Physics*, Cambridge University Press, 2013.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- A. M. Tsvelik, *Quantum Field Theory in Condensed Matter Physics*, Cambridge University Press, 2003.

## Version history

- 2026-06-30: First polished draft. Added free-fermion current algebras, $U(N)_1$ and color-flavor decompositions, central-charge checks, WZW matrix-field dictionary, spin-chain and Luttinger-liquid previews, pitfalls, exercises, and references.
