---
title: "Cosets and GKO Construction"
description: "How subtracting affine current algebras produces new two-dimensional conformal field theories, including parafermions and Virasoro minimal models."
sidebar:
  label: "Cosets and GKO"
  order: 10
level: Graduate
status: "Polished draft"
source: "Goddard, Kent, and Olive 1985; Di Francesco, Mathieu, and Senechal chs. 15–18; Ginsparg lectures; standard coset CFT literature."
topics:
  - coset CFT
  - GKO construction
  - affine Lie algebras
  - WZW models
  - parafermions
  - minimal models
canonicalTopics:
  - cosets-gko-construction
  - affine-coset-cft
  - branching-functions
researchStatus:
  established:
    - "The GKO construction produces conformal field theories by taking the commutant of an affine subalgebra and subtracting the corresponding Sugawara stress tensors."
  active:
    - "Modern applications include gauged WZW models, parafermions, higher-spin algebras, supersymmetric cosets, noncompact cosets, and categorical formulations of rational CFT."
---

## Summary

A **coset CFT** is built by dividing one chiral current algebra by another. In the Goddard–Kent–Olive construction, one starts with an affine algebra $\widehat{\mathfrak g}_k$ and an embedded affine subalgebra $\widehat{\mathfrak h}_{k_{\mathfrak h}}$. The coset stress tensor is

$$
T_{\mathfrak g/\mathfrak h}(z)=T_{\mathfrak g}(z)-T_{\mathfrak h}(z),
$$

and the central charge is

$$
c_{\mathfrak g/\mathfrak h}
=c(\mathfrak g,k)-c(\mathfrak h,k_{\mathfrak h}).
$$

For compact simple factors in the standard normalization,

$$
c(\mathfrak g,k)=\frac{k\dim\mathfrak g}{k+h^\vee_{\mathfrak g}}.
$$

The word “coset” can be slightly misleading. The construction is not primarily a quotient of spacetime. It is a quotient of **chiral symmetry algebras**: the coset algebra is the part of the numerator current algebra that commutes with the denominator current algebra.

This construction explains many famous rational CFTs. The parafermion theories arise from

$$
\frac{SU(2)_k}{U(1)},
$$

and the unitary Virasoro minimal models arise from

$$
\frac{SU(2)_k\times SU(2)_1}{SU(2)_{k+1}}.
$$

Cosets are one of the cleanest ways to manufacture new CFTs from known WZW models.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/), [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/), and [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) first.

You should also know the rational-CFT ideas of [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/), and [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/).

## Core idea

Suppose a WZW model has chiral algebra $\widehat{\mathfrak g}_k$, and inside it there is a current subalgebra $\widehat{\mathfrak h}_{k_{\mathfrak h}}$. The numerator theory contains both the denominator currents and whatever remains independent of them.

The GKO construction isolates the remainder by subtracting stress tensors:

$$
T_{\rm coset}=T_{\mathfrak g}-T_{\mathfrak h}.
$$

Because both $T_{\mathfrak g}$ and $T_{\mathfrak h}$ make the $\mathfrak h$ currents transform as weight-one primaries, their difference has regular OPE with the $\mathfrak h$ currents:

$$
T_{\rm coset}(z)J^a_{\mathfrak h}(w)\sim\text{regular}.
$$

Thus the coset stress tensor describes degrees of freedom left after the denominator current algebra has been removed.

The slogan is

$$
\text{WZW numerator}
-\text{WZW denominator}
=\text{new CFT}.
$$

The real construction is algebraic: the coset chiral algebra is the commutant of $\widehat{\mathfrak h}_{k_{\mathfrak h}}$ inside the numerator chiral algebra.

## Setup and conventions

Let

$$
\widehat{\mathfrak h}_{k_{\mathfrak h}}\subset \widehat{\mathfrak g}_k
$$

be an affine embedding. If $\mathfrak h$ is embedded in $\mathfrak g$ with embedding index $x_e$, the induced denominator level is

$$
k_{\mathfrak h}=x_e k.
$$

Forgetting this factor is one of the most common errors in coset calculations.

For compact simple algebras, the Sugawara central charge is

$$
c(\mathfrak g,k)=\frac{k\dim\mathfrak g}{k+h^\vee_{\mathfrak g}}.
$$

For direct sums, central charges add. Therefore, for

$$
\widehat{\mathfrak g}_{1,k_1}\oplus\widehat{\mathfrak g}_{2,k_2}
$$

the numerator central charge is

$$
c(\mathfrak g_1,k_1)+c(\mathfrak g_2,k_2).
$$

The coset stress tensor is

$$
T_{\mathfrak g/\mathfrak h}=T_{\mathfrak g}-T_{\mathfrak h},
$$

and its central charge is

$$
c_{\mathfrak g/\mathfrak h}=c_{\mathfrak g}-c_{\mathfrak h}.
$$

This page focuses on compact rational cosets. Noncompact, supersymmetric, logarithmic, and gauged versions require extra conditions.

## The commutant viewpoint

The coset chiral algebra is often written as

$$
\frac{\widehat{\mathfrak g}_k}{\widehat{\mathfrak h}_{k_{\mathfrak h}}}.
$$

A precise algebraic description is

$$
\mathcal A_{\mathfrak g/\mathfrak h}
=\operatorname{Com}(\widehat{\mathfrak h}_{k_{\mathfrak h}},\widehat{\mathfrak g}_k),
$$

where the commutant consists of fields in the numerator chiral algebra with regular OPEs with all denominator currents.

This definition explains two facts.

First, the denominator currents are not local operators of the coset theory. They have been divided out.

Second, the coset theory can have a chiral algebra larger than Virasoro. For example, parafermion cosets have nontrivial parafermionic chiral fields, and many cosets have $W$-algebra symmetry.

The stress tensor $T_{\mathfrak g}-T_{\mathfrak h}$ is only the Virasoro part of the coset algebra. The full commutant may contain additional holomorphic generators.

## Branching functions

Let $\mathcal V^\mathfrak g_\lambda$ be an integrable representation of $\widehat{\mathfrak g}_k$. When restricted to $\widehat{\mathfrak h}_{k_{\mathfrak h}}$, it decomposes as

$$
\mathcal V^\mathfrak g_\lambda
=\bigoplus_\mu
\mathcal B_{\lambda;\mu}\otimes \mathcal V^\mathfrak h_\mu.
$$

Here $\mathcal V^\mathfrak h_\mu$ is an integrable denominator representation, and $\mathcal B_{\lambda;\mu}$ is the multiplicity space. The coset chiral algebra acts on $\mathcal B_{\lambda;\mu}$.

At the level of characters,

$$
\chi^\mathfrak g_\lambda(\tau,z)
=\sum_\mu b_{\lambda;\mu}(\tau)\chi^\mathfrak h_\mu(\tau,z),
$$

where $b_{\lambda;\mu}(\tau)$ are **branching functions**. These branching functions are the coset characters.

This is the most practical way to identify coset spectra:

$$
\text{numerator character}
=\sum_\text{denominator labels}
\text{coset character}\times\text{denominator character}.
$$

The pair $(\lambda;\mu)$ labels a possible coset sector only if $\mu$ appears in the branching of $\lambda$.

## Selection rules and field identification

Coset labels are usually not just arbitrary pairs

$$
(\lambda;\mu).
$$

There are two additional ingredients.

First, there are **selection rules**: the denominator representation $\mu$ must actually occur when the numerator representation $\lambda$ is restricted to $\mathfrak h$.

Second, there are **field identifications**: different pairs $(\lambda;\mu)$ may describe the same coset representation.

In many rational cosets, field identifications are generated by simple currents. Schematically,

$$
(\lambda;\mu)\sim(J_{\mathfrak g}\lambda;J_{\mathfrak h}\mu),
$$

when the numerator and denominator simple currents are compatible.

This is the coset analogue of Kac-table field identification in minimal models. Ignoring field identification double-counts the spectrum and usually breaks modular invariance.

The safe workflow is:

1. List integrable numerator labels.
2. Branch them into denominator labels.
3. Keep only allowed pairs.
4. Divide by field identifications.
5. Check characters and modular invariance.

## Example: parafermions

The standard $\mathbb Z_k$ parafermion CFT is the coset

$$
\frac{SU(2)_k}{U(1)}.
$$

The numerator central charge is

$$
c_{SU(2)_k}=\frac{3k}{k+2}.
$$

The denominator $U(1)$ current has central charge

$$
c_{U(1)}=1.
$$

Therefore the parafermion central charge is

$$
c_{\rm PF_k}
=\frac{3k}{k+2}-1
=\frac{2(k-1)}{k+2}.
$$

For $k=2$,

$$
c=\frac12,
$$

which is the Ising central charge. For $k=3$,

$$
c=\frac45,
$$

which is the central charge of the three-state Potts CFT.

The labels can be written as pairs

$$
(j,m),
$$

where $j$ labels an $SU(2)_k$ integrable representation and $m$ labels the $U(1)$ charge sector, subject to selection rules and identifications. The coset removes the abelian current and leaves the neutral parafermionic degrees of freedom.

This example is the fastest way to see what a coset does: it strips a WZW model of a current subalgebra and leaves a smaller, still highly structured CFT.

## Example: Virasoro minimal models

The unitary Virasoro minimal models arise from the diagonal coset

$$
\frac{SU(2)_k\times SU(2)_1}{SU(2)_{k+1}}.
$$

Compute the central charge:

$$
c
=\frac{3k}{k+2}+\frac{3}{3}-\frac{3(k+1)}{k+3}.
$$

Since $SU(2)_1$ has $c=1$, this becomes

$$
c=1-\frac{6}{(k+2)(k+3)}.
$$

If we set

$$
m=k+2,
$$

then

$$
c=1-\frac{6}{m(m+1)}.
$$

This is exactly the central charge of the unitary minimal model

$$
\mathcal M(m,m+1).
$$

For $k=1$, we get $m=3$ and

$$
c=\frac12,
$$

which is the Ising model. For $k=2$, we get $m=4$ and

$$
c=\frac{7}{10},
$$

which is the tricritical Ising model.

This is one of the most beautiful checks of the GKO construction: subtracting affine $SU(2)$ stress tensors reproduces the whole unitary Virasoro minimal series.

## Coset weights

A coset primary label $(\lambda;\mu)$ has conformal weight roughly given by the difference of numerator and denominator weights:

$$
h_{\lambda;\mu}
=h^\mathfrak g_\lambda-h^\mathfrak h_\mu+N_{\lambda;\mu}.
$$

Here $N_{\lambda;\mu}$ is a nonnegative integer or grade shift determined by where the denominator representation $\mu$ appears inside the numerator module. This shift is important. The naive difference of highest weights is not always the final lowest coset weight.

For a simple numerator and denominator,

$$
h^\mathfrak g_\lambda
=\frac{C_2^\mathfrak g(\lambda)}{2(k+h^\vee_\mathfrak g)},
$$

and similarly for $\mathfrak h$ with its induced level.

Thus coset dimensions are representation-theoretic. They come from Sugawara energies before and after subtracting the denominator current algebra.

In diagonal cosets, the full scaling dimension of a scalar local field is often

$$
\Delta=2h_{\lambda;\mu},
$$

but non-diagonal and extended-algebra cases require specifying the left-right pairing.

## Fusion in coset CFT

Coset fusion is inherited from numerator and denominator fusion, with selection rules and identifications imposed. Schematically,

$$
(\lambda;\mu)\times(\lambda';\mu')
=\sum_{\lambda'',\mu''}
N^\mathfrak g_{\lambda\lambda'}{}^{\lambda''}
N^\mathfrak h_{\mu\mu'}{}^{\mu''}
(\lambda'';\mu''),
$$

followed by the coset selection rule and field identification.

The denominator appears with the same fusion coefficient rather than an inverse operation because the coset branching spaces are intertwiners compatible with both numerator and denominator chiral algebras. More refined statements require care with fixed points under simple-current identification.

In rational cosets, the Verlinde formula applied to the coset modular $S$ matrix gives the final fusion ring. The schematic product above is best used as intuition and as a first-pass calculation, not as a substitute for checking identifications and multiplicities.

## Gauged WZW interpretation

Coset CFTs also have a Lagrangian interpretation as gauged WZW models. Roughly, one starts with a WZW model on $G$ and gauges a subgroup $H$.

The result is often denoted

$$
G/H.
$$

This notation is geometrically suggestive, but the quantum CFT is not merely a sigma model on an ordinary quotient space. The Wess–Zumino term, level quantization, gauge anomaly cancellation, and chiral algebra quotient all matter.

For compact group cosets, the gauged-WZW picture and the GKO chiral-algebra picture are two complementary routes to the same family of theories. The GKO construction is usually the cleanest for computing central charges, characters, and representation labels. The gauged-WZW construction is often better for action principles, anomalies, and target-space intuition.

## Minimal-model dictionary

The GKO construction of unitary minimal models gives a useful bridge between the WZW labels and the Kac table. For

$$
\frac{SU(2)_k\times SU(2)_1}{SU(2)_{k+1}},
$$

let the two numerator labels be spins

$$
j_1,\quad j_2=0\text{ or }\frac12,
$$

and let the denominator label be $j_3$. The branching condition is the $SU(2)$ tensor-product selection rule, truncated by level.

The resulting coset labels can be matched to Kac labels of

$$
\mathcal M(k+2,k+3).
$$

The detailed dictionary depends on label conventions, but the central charge and field-identification structure reproduce the unitary minimal-model spectrum.

This connection is conceptually important. Minimal models are not isolated miracles. They sit inside a larger family of current-algebra constructions.

## Common pitfalls

**Do not interpret the slash as an ordinary geometric quotient only.** The GKO coset is a quotient of chiral algebras or a commutant construction. Gauged WZW models provide a geometric-looking action, but the CFT data are algebraic.

**Do not forget the denominator level.** If $\mathfrak h\subset\mathfrak g$ has embedding index $x_e$, then $k_{\mathfrak h}=x_e k_{\mathfrak g}$.

**Do not subtract dimensions instead of central charges.** The coset central charge is $c_{\mathfrak g}-c_{\mathfrak h}$, with each $c$ computed at the correct level.

**Do not ignore branching.** A pair $(\lambda;\mu)$ is allowed only if $\mu$ appears in the restriction of the numerator representation.

**Do not ignore field identification.** Different label pairs can describe the same coset representation.

**Do not assume the coset chiral algebra is only Virasoro.** Many cosets have extended $W$-algebra, parafermion, or other chiral symmetry.

**Do not assume diagonal local pairing.** A chiral coset spectrum still needs a modular invariant to define a full local CFT.

## Relations to other pages

This page uses [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) for the subtraction of stress tensors and [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) for embedding indices. It relies on [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/), [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/), and [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) for the numerator and denominator representation theory.

It connects backward to [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) because the unitary minimal series is a GKO coset. It also connects to [Three-State Potts CFT](/cft-bootstrap/minimal-models-rational-cft/three-state-potts-cft/) through parafermions and non-diagonal modular invariants.

The next page, [Nonabelian Bosonization Preview](/cft-bootstrap/current-algebras-wzw/nonabelian-bosonization-preview/), explains why WZW models and current algebras also arise from free fermions and condensed-matter systems.

## Research status

The GKO coset construction for compact rational current algebras is established. It is one of the standard tools for building and organizing two-dimensional rational CFTs.

Active research uses cosets in broader settings: noncompact target spaces, supersymmetric cosets, Kazama–Suzuki models, higher-spin holography, logarithmic current algebras, nonsemisimple representation categories, boundary and defect cosets, and chiral algebras associated with higher-dimensional QFT.

## Exercises

### Exercise 1

Compute the central charge of the parafermion coset

$$
\frac{SU(2)_k}{U(1)}.
$$

<details><summary><strong>Solution</strong></summary>

The $SU(2)_k$ central charge is

$$
c_{SU(2)_k}=\frac{3k}{k+2}.
$$

A single $U(1)$ current has central charge

$$
c_{U(1)}=1.
$$

Therefore

$$
c=\frac{3k}{k+2}-1
=\frac{3k-(k+2)}{k+2}
=\frac{2k-2}{k+2}
=\frac{2(k-1)}{k+2}.
$$

</details>

### Exercise 2

Use the coset

$$
\frac{SU(2)_k\times SU(2)_1}{SU(2)_{k+1}}
$$

to derive the central charge of the unitary minimal model series.

<details><summary><strong>Solution</strong></summary>

The central charges are

$$
c_{SU(2)_k}=\frac{3k}{k+2},
\qquad
c_{SU(2)_1}=1,
\qquad
c_{SU(2)_{k+1}}=\frac{3(k+1)}{k+3}.
$$

Thus

$$
c=\frac{3k}{k+2}+1-\frac{3(k+1)}{k+3}.
$$

Putting over a common denominator gives

$$
c=1-\frac{6}{(k+2)(k+3)}.
$$

With $m=k+2$,

$$
c=1-\frac{6}{m(m+1)},
$$

which is the unitary minimal-model central charge.

</details>

### Exercise 3

Why does the denominator level become $k_{\mathfrak h}=x_e k_{\mathfrak g}$ for a nontrivial embedding?

<details><summary><strong>Solution</strong></summary>

The level measures the current two-point function relative to a chosen invariant form. When $\mathfrak h$ is embedded in $\mathfrak g$, the invariant form inherited from $\mathfrak g$ restricts to an invariant form on $\mathfrak h$. This restricted form can be $x_e$ times the standard form used to normalize $\mathfrak h$.

Therefore the induced current-current double pole for the $\mathfrak h$ currents is multiplied by the embedding index:

$$
k_{\mathfrak h}=x_e k_{\mathfrak g}.
$$

</details>

### Exercise 4

Explain why a branching function is naturally a coset character.

<details><summary><strong>Solution</strong></summary>

Restrict a numerator representation to the denominator algebra:

$$
\mathcal V^\mathfrak g_\lambda
=\bigoplus_\mu \mathcal B_{\lambda;\mu}\otimes\mathcal V^\mathfrak h_\mu.
$$

The denominator algebra acts on $\mathcal V^\mathfrak h_\mu$, while the commutant, or coset algebra, acts on the multiplicity space $\mathcal B_{\lambda;\mu}$. Taking characters gives

$$
\chi^\mathfrak g_\lambda=\sum_\mu b_{\lambda;\mu}\chi^\mathfrak h_\mu.
$$

The coefficient $b_{\lambda;\mu}$ counts the graded states in $\mathcal B_{\lambda;\mu}$, so it is the coset character.

</details>

## References

- P. Goddard, A. Kent, and D. Olive, “Virasoro algebras and coset space models,” *Physics Letters B* **152** (1985).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- D. Gepner and E. Witten, “String theory on group manifolds,” *Nuclear Physics B* **278** (1986).
- K. Gawedzki and A. Kupiainen, “G/H conformal field theory from gauged WZW model,” *Physics Letters B* **215** (1988).
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.

## Version history

- 2026-06-30: First polished draft. Added GKO stress-tensor subtraction, branching functions, selection rules, field identification, parafermion and minimal-model examples, gauged-WZW preview, exercises, and references.
