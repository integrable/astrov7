---
title: "Currents and Kac–Moody OPEs"
description: "How holomorphic conserved currents realize affine Lie algebra symmetry through local OPEs, contour charges, Ward identities, and current action on primary fields."
sidebar:
  label: "Currents and Kac–Moody OPEs"
  order: 2
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal ch. 14; Ginsparg lectures; Knizhnik and Zamolodchikov 1984; standard WZW current-algebra literature."
topics:
  - holomorphic currents
  - Kac–Moody OPEs
  - affine Lie algebras
  - Ward identities
  - WZW models
canonicalTopics:
  - current-opes
  - kac-moody-ward-identities
  - affine-current-action
researchStatus:
  established:
    - "Holomorphic current OPEs and their contour Ward identities are the standard local realization of affine Lie algebra symmetry in two-dimensional CFT."
  active:
    - "Current-algebra methods remain central in boundary CFT, defects, non-invertible symmetries, condensed-matter edge theories, and nonsemisimple generalizations."
---

## Summary

A conserved current in two-dimensional CFT can become a holomorphic field of weights $(1,0)$:

$$
\bar\partial J^a(z)=0.
$$

Its local operator product expansion is the CFT form of an affine Lie algebra:

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The simple pole says that the zero modes generate the finite Lie algebra $\mathfrak g$. The double pole is the central extension, with coefficient called the **level** $k$. The contour charges

$$
J^a_n=\oint_0\frac{dz}{2\pi i}\,z^nJ^a(z)
$$

obey

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}+k m\kappa^{ab}\delta_{m+n,0}.
$$

This page explains the OPE, its contour meaning, how currents act on affine primary fields, and how Ward identities turn current algebra into concrete correlator constraints.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/), and [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) first.

You should also know basic finite Lie-algebra notation:

$$
[T^a,T^b]=i f^{ab}{}_cT^c,
$$

and the meaning of an invariant bilinear form $\kappa^{ab}$.

## Core idea

A global continuous symmetry has charges $Q^a$ satisfying

$$
[Q^a,Q^b]=i f^{ab}{}_c Q^c.
$$

In two-dimensional CFT, a chiral conserved current upgrades these finitely many charges to infinitely many modes $J^a_n$. The current OPE encodes the whole algebra in one local singularity formula.

The central lesson is

$$
\text{current OPE}
\quad\Longleftrightarrow\quad
\text{contour algebra}
\quad\Longleftrightarrow\quad
\text{Ward identities}.
$$

This is why current algebra is so effective. It gives both algebraic representation theory and explicit differential constraints on correlators.

## Setup and conventions

We work in Euclidean complex coordinates $z,\bar z$. A holomorphic current has weights $(1,0)$ and Laurent expansion

$$
J^a(z)=\sum_{n\in\mathbb Z}J^a_nz^{-n-1}.
$$

The inverse formula is

$$
J^a_n=\oint_0\frac{dz}{2\pi i}\,z^nJ^a(z).
$$

The finite Lie algebra has structure constants

$$
[T^a,T^b]=i f^{ab}{}_cT^c,
$$

and invariant metric $\kappa^{ab}$. The current OPE convention is

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

With anti-Hermitian generators, many books remove the explicit $i$ from the simple pole. The algebra is the same after translating conventions.

Unless stated otherwise, repeated adjoint indices are contracted with $\kappa_{ab}$ and $\kappa^{ab}$.

## The local current OPE

The two singular terms in

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}
$$

have different jobs.

The simple pole is the finite Lie bracket. It says that a current circling another current rotates it in the adjoint representation:

$$
\oint_w\frac{dz}{2\pi i}J^a(z)J^b(w)
=i f^{ab}{}_cJ^c(w).
$$

The double pole is the central term. It fixes the current two-point function:

$$
\langle J^a(z)J^b(w)\rangle
=\frac{k\kappa^{ab}}{(z-w)^2}.
$$

In a unitary compact theory, positive current norms require $k$ to be nonnegative in a positive-definite normalization. In WZW models, $k$ is a nonnegative integer.

## From OPE to mode algebra

The mode commutator is obtained by nested contour integrals:

$$
[J^a_m,J^b_n]
=\oint_0\frac{dw}{2\pi i}w^n
\oint_w\frac{dz}{2\pi i}z^mJ^a(z)J^b(w).
$$

The simple pole gives

$$
i f^{ab}{}_c\oint_0\frac{dw}{2\pi i}w^{m+n}J^c(w)
=i f^{ab}{}_cJ^c_{m+n}.
$$

The double pole gives

$$
k\kappa^{ab}\oint_0\frac{dw}{2\pi i}w^n
\oint_w\frac{dz}{2\pi i}\frac{z^m}{(z-w)^2}
=k m\kappa^{ab}\delta_{m+n,0}.
$$

Thus

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}
+k m\kappa^{ab}\delta_{m+n,0}.
$$

Setting $m=n=0$ removes the central term and recovers the finite Lie algebra:

$$
[J^a_0,J^b_0]=i f^{ab}{}_cJ^c_0.
$$

The zero modes are the ordinary global symmetry charges. The nonzero modes are the genuinely affine enhancement.

## Currents acting on primary fields

Let $\Phi_i(w,\bar w)$ transform in a representation $R_i$ of $\mathfrak g$, with matrices $t^a_i$. The current OPE is

$$
J^a(z)\Phi_i(w,\bar w)
\sim
\frac{t^a_i\Phi_i(w,\bar w)}{z-w}.
$$

This means that the zero-mode charge acts as

$$
[J^a_0,\Phi_i(w,\bar w)]=t^a_i\Phi_i(w,\bar w).
$$

An **affine primary** is stronger than a finite Lie-algebra primary. At the state level, it is annihilated by positive current modes:

$$
J^a_n|\Phi_i\rangle=0,
\qquad n>0,
$$

and transforms under the zero modes in a finite-dimensional representation:

$$
J^a_0|\Phi_i\rangle=t^a_i|\Phi_i\rangle.
$$

Negative current modes create affine descendants:

$$
J^{a_1}_{-n_1}\cdots J^{a_r}_{-n_r}|\Phi_i\rangle,
\qquad n_i>0.
$$

These descendants are not generally Virasoro descendants. They are descendants with respect to the larger current algebra.

## Current Ward identity

Insert a holomorphic current into a correlator of affine primary fields. The OPE with each insertion gives the singularity:

$$
\left\langle J^a(z)\prod_i\Phi_i(z_i,\bar z_i)\right\rangle
=
\sum_i\frac{t^a_i}{z-z_i}
\left\langle \prod_i\Phi_i(z_i,\bar z_i)\right\rangle,
$$

up to possible regular holomorphic terms. On the sphere, the regular term vanishes if the correlator is nonsingular at infinity with the appropriate current behavior.

Integrating $J^a(z)$ around a contour enclosing all insertions gives the global Ward identity:

$$
\sum_i t^a_i
\left\langle \prod_i\Phi_i(z_i,\bar z_i)\right\rangle=0.
$$

This says that a nonzero correlator must be a singlet under the global symmetry.

The same contour idea gives local Ward identities. Moving the current contour from one set of insertions to another is the current-algebra version of charge conservation.

## Ward identity with several currents

For multiple current insertions, use the current-current OPE recursively. For example,

$$
\left\langle J^a(z)J^b(w)\prod_i\Phi_i(z_i)\right\rangle
$$

has singular terms as $z\to w$:

$$
\frac{k\kappa^{ab}}{(z-w)^2}
\left\langle \prod_i\Phi_i\right\rangle
+
\frac{i f^{ab}{}_c}{z-w}
\left\langle J^c(w)\prod_i\Phi_i\right\rangle.
$$

It also has simple poles as $z$ approaches any primary insertion:

$$
\sum_i\frac{t_i^a}{z-z_i}
\left\langle J^b(w)\prod_i\Phi_i(z_i)\right\rangle.
$$

These identities determine many current correlators algebraically. For pure current correlators on the sphere, the two-point and three-point functions follow directly:

$$
\langle J^a(z_1)J^b(z_2)\rangle
=\frac{k\kappa^{ab}}{z_{12}^2},
$$

and

$$
\langle J^a(z_1)J^b(z_2)J^c(z_3)\rangle
=\frac{i k f^{abc}}{z_{12}z_{23}z_{31}},
$$

with $f^{abc}=f^{ab}{}_d\kappa^{dc}$.

## Charges as contours

For a holomorphic current, a charge associated with a contour $C$ is

$$
Q^a_C=\oint_C\frac{dz}{2\pi i}J^a(z).
$$

If $C$ is deformed without crossing an insertion, the charge is unchanged. If $C$ crosses a charged operator, the contour picks up the residue of the current-primary OPE.

This gives the intuitive picture:

$$
\text{current contour crosses an operator}
\quad\Longrightarrow\quad
\text{the symmetry generator acts on that operator}.
$$

The affine modes are similar contours with extra powers of $z$:

$$
J^a_n=\oint\frac{dz}{2\pi i}z^nJ^a(z).
$$

Radial quantization turns these contours into operators acting on the Hilbert space on the circle.

## Relation to the stress tensor

In WZW models, the stress tensor can be built from currents by the Sugawara construction:

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z),
$$

in the common simple-algebra normalization. This implies

$$
T(z)J^a(w)
\sim
\frac{J^a(w)}{(z-w)^2}
+\frac{\partial J^a(w)}{z-w}.
$$

So currents are Virasoro primaries of weight one. The resulting central charge is

$$
c=\frac{k\dim\mathfrak g}{k+h^\vee}.
$$

This relation is developed in the Sugawara page. Here it serves as a reminder: the current OPE does not replace the Virasoro algebra; it extends the chiral symmetry so strongly that the Virasoro stress tensor can often be constructed from currents.

## Abelian current algebra

For a single $U(1)$ current, there are no structure constants. The OPE is simply

$$
J(z)J(w)\sim\frac{k}{(z-w)^2},
$$

and the modes obey

$$
[J_m,J_n]=k m\delta_{m+n,0}.
$$

This is the Heisenberg algebra. A charged primary of charge $q$ has

$$
J(z)\Phi_q(w,\bar w)\sim\frac{q\Phi_q(w,\bar w)}{z-w}.
$$

The Ward identity becomes charge neutrality:

$$
\sum_i q_i\left\langle\prod_i\Phi_{q_i}\right\rangle=0.
$$

For free bosons and compact bosons, this is the current-algebra version of momentum conservation in vertex-operator correlators.

## Antiholomorphic currents

A full two-dimensional CFT can also have antiholomorphic currents

$$
\bar J^a(\bar z)=\sum_{n\in\mathbb Z}\bar J^a_n\bar z^{-n-1}.
$$

They obey a separate affine algebra:

$$
\bar J^a(\bar z)\bar J^b(\bar w)
\sim
\frac{\bar k\kappa^{ab}}{(\bar z-\bar w)^2}
+\frac{i f^{ab}{}_c\bar J^c(\bar w)}{\bar z-\bar w}.
$$

In diagonal compact WZW models, the left and right levels are usually equal:

$$
k=\bar k.
$$

But left and right current algebras can be paired in nontrivial ways in heterotic, chiral, boundary, or defect settings. Always specify which chiral algebra is being used.

## Common pitfalls

**Do not confuse the current OPE with a classical Poisson bracket.** It is a quantum operator statement. The double pole is the central extension.

**Do not call $k$ the Virasoro central charge.** The level $k$ controls current-current singularities. The Virasoro central charge $c$ follows from the stress tensor, for example through Sugawara in WZW models.

**Do not drop the double pole.** Without it, the current two-point function vanishes and the affine representation theory is wrong.

**Do not confuse finite primaries with affine primaries.** An affine primary is annihilated by positive current modes and transforms under the zero modes. This is stronger than just being a highest-weight vector of the finite algebra.

**Do not forget antiholomorphic data.** A local nonchiral CFT needs left and right sectors, even if a calculation focuses on the holomorphic algebra.

**Do not compare signs without checking generator conventions.** Hermitian versus anti-Hermitian generators move factors of $i$ between the commutator and OPE.

## Relations to other pages

This page follows [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/) by translating the abstract mode algebra into local CFT OPEs and contour Ward identities.

[Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) explains how $k$, $\kappa^{ab}$, trace conventions, and Dynkin indices are compared across sources. [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) uses the current OPE to build the stress tensor. [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) uses the current-primary OPE to define affine primaries and compute their conformal weights.

The contour logic is parallel to [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) and [Current OPE](/cft-bootstrap/operator-product-expansion/current-ope/), but here the symmetry is an infinite-dimensional chiral current algebra.

## Research status

The current OPE, affine mode algebra, current Ward identities, and their role in WZW models are established. They are standard tools in rational CFT and string worldsheet theory.

Active research uses the same structures in more elaborate settings: boundary current algebras, conformal defects, non-invertible symmetries, logarithmic current algebras, chiral edge theories, and categorical formulations of rational CFT.

## Exercises

### Exercise 1

Derive the simple-pole contribution to the affine mode commutator from the OPE

$$
J^a(z)J^b(w)
\sim\frac{i f^{ab}{}_cJ^c(w)}{z-w}+\cdots .
$$

<details><summary><strong>Solution</strong></summary>

The simple-pole contribution to $[J^a_m,J^b_n]$ is

$$
\oint_0\frac{dw}{2\pi i}w^n
\oint_w\frac{dz}{2\pi i}z^m
\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The inner contour gives $w^m$, so the result is

$$
i f^{ab}{}_c\oint_0\frac{dw}{2\pi i}w^{m+n}J^c(w)
=i f^{ab}{}_cJ^c_{m+n}.
$$

</details>

### Exercise 2

Show that the zero modes reproduce the finite Lie algebra.

<details><summary><strong>Solution</strong></summary>

Set $m=n=0$ in

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}+k m\kappa^{ab}\delta_{m+n,0}.
$$

The central term is proportional to $m$, so it vanishes. Therefore

$$
[J^a_0,J^b_0]=i f^{ab}{}_cJ^c_0.
$$

This is the finite Lie algebra acting on the Hilbert space.

</details>

### Exercise 3

Use the current-primary OPE to derive the global Ward identity

$$
\sum_i t_i^a\left\langle\prod_i\Phi_i\right\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Insert $J^a(z)$ into the correlator and integrate around a contour enclosing all insertions:

$$
\oint_C\frac{dz}{2\pi i}\left\langle J^a(z)\prod_i\Phi_i(z_i)\right\rangle.
$$

On the sphere this contour can be pushed to infinity, where there is no contribution for an ordinary current insertion. Shrinking the contour around the insertions gives the sum of residues from

$$
J^a(z)\Phi_i(z_i)\sim\frac{t_i^a\Phi_i(z_i)}{z-z_i}.
$$

Therefore

$$
\sum_i t_i^a\left\langle\prod_i\Phi_i\right\rangle=0.
$$

</details>

### Exercise 4

For a $U(1)$ current with $J(z)\Phi_q(w)\sim q\Phi_q(w)/(z-w)$, show that a correlator of charged primaries on the sphere vanishes unless the total charge is zero.

<details><summary><strong>Solution</strong></summary>

The global Ward identity becomes

$$
\sum_i q_i\left\langle\prod_i\Phi_{q_i}(z_i)\right\rangle=0.
$$

If the correlator is nonzero, the prefactor must vanish:

$$
\sum_i q_i=0.
$$

Thus charge neutrality is required for a nonzero sphere correlator.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).

## Version history

- 2026-06-30: First polished draft. Added current OPE conventions, mode derivation, current-primary OPE, Ward identities, charge contours, examples, pitfalls, exercises, and references.
