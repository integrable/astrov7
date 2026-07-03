---
title: "Anomalies in Two Dimensions"
description: "Explains gauge, global, gravitational, and trace anomalies in two-dimensional QFT, with emphasis on chiral fermions, current algebras, modular covariance, and anomaly inflow."
sidebar:
  label: "Anomalies in Two Dimensions"
  order: 9
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry, Dilatations; Srednicki §§75–77; Schwartz Ch. 30; Ginsparg, Applied CFT; Alvarez-Gaumé–Witten; standard 2D anomaly and CFT references."
topics:
  - anomalies
  - two-dimensional QFT
  - chiral fermions
  - current algebra
  - gravitational anomaly
  - trace anomaly
canonicalTopics:
  - two-dimensional-anomaly
  - chiral-anomaly
  - gravitational-anomaly
  - trace-anomaly
  - anomaly-inflow
researchStatus:
  established:
    - "Gauge, global, gravitational, and trace anomalies in two-dimensional QFT are standard and can be diagnosed by current nonconservation, modular covariance, current-algebra levels, and anomaly inflow."
    - "The anomaly coefficients of chiral two-dimensional theories are robust data, invariant under symmetry-preserving RG flow."
  active:
    - "Modern work emphasizes anomalous defects, non-invertible symmetries, fermionic/spin anomalies, symmetry TFT descriptions, and anomaly constraints on boundaries and interfaces."
---

## Summary

Two dimensions are where anomalies become visible with very little machinery. A chiral fermion already shows the central lesson:

$$
\text{a symmetry of the classical action may fail as a symmetry of the quantum theory}.
$$

In $1+1$ dimensions, the most important anomalies are:

| Anomaly | What fails | Typical coefficient |
|---|---|---|
| Chiral gauge or flavor anomaly | Conservation of a chiral current in background gauge fields | Current-algebra level or charge-squared difference |
| Gravitational anomaly | Conservation or modular covariance of the stress tensor | $c_L-c_R$ |
| Trace anomaly | Weyl invariance on curved backgrounds | $c_{\mathrm{Weyl}}=(c_L+c_R)/2$ |
| Finite-symmetry anomaly | Consistent twisted sectors and gauging | Discrete topological action or cocycle data |

Two-dimensional anomalies are not isolated curiosities. They connect current algebras, modular invariance, edge modes, anomaly inflow, bosonization, orbifolds, and conformal field theory. They are also the best training ground for the general definition of a ’t Hooft anomaly as an obstruction to gauging a global symmetry.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing two-dimensional anomalies as related descriptions: current nonconservation, modular phases, current algebra levels, and three-dimensional inflow.](/figures/symmetry-anomalies-topology/two-dimensional-anomaly-map.svg)

<figcaption>

In two dimensions, the same anomaly can often be read in several languages: nonconservation of a current in a background field, a central term in a current algebra, a modular phase on the torus, or inflow from a three-dimensional bulk topological action.

</figcaption>
</figure>

## Prerequisites

You should know [Current Algebras](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/current-algebras/), [Affine Symmetries: Preview](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/affine-symmetries-preview/), [Modular Invariance: Preview](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/modular-invariance-preview/), and the general idea of [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/).

We use Euclidean two-dimensional notation when discussing complex coordinates and Lorentzian $1+1$ notation when discussing left- and right-movers. Local signs depend on orientation, Wick rotation, and whether one writes consistent or covariant currents. This page states the convention whenever a coefficient is used.

## Core idea

An anomaly is not just “a current is not conserved.” That phrase is too narrow.

A two-dimensional anomaly can appear as:

$$
\nabla_\mu J^\mu\ne0
$$

in background fields,

$$
J(z)J(0)\sim\frac{k}{z^2}+\cdots
$$

in current algebra,

$$
Z(\tau+1,\bar\tau+1)=e^{i\varphi}Z(\tau,\bar\tau)
$$

under modular transformations, or

$$
\delta W_{\partial M}=-\delta S_{\mathrm{bulk}}
$$

as anomaly inflow from a three-dimensional bulk.

The invariant content is the obstruction: the theory cannot be coupled to arbitrary background fields for the symmetry while preserving all the desired gauge, diffeomorphism, and locality properties. If the anomalous symmetry is a global symmetry, the theory may still be perfectly consistent. If the anomalous symmetry is a gauge redundancy, the theory is inconsistent unless the anomaly cancels or is repaired by inflow.

## Chiral fermions and gauge anomalies

Consider complex Weyl fermions in two dimensions coupled to a background $U(1)$ field. Let right-moving fermions have charges $q_i^R$ and left-moving fermions have charges $q_j^L$. The anomaly coefficient is

$$
k=\sum_i (q_i^R)^2-\sum_j(q_j^L)^2.
$$

In a common consistent-anomaly convention,

$$
\nabla_\mu J^\mu
=
\frac{k}{4\pi}\epsilon^{\mu\nu}F_{\mu\nu}.
$$

The important facts are more robust than the local sign:

1. right- and left-movers contribute with opposite signs;
2. the coefficient is quadratic in charges;
3. the coefficient is invariant under symmetry-preserving RG flow;
4. a dynamical gauge symmetry requires the total coefficient to vanish.

For a non-Abelian symmetry $G$, the charge-squared sum is replaced by the quadratic index of the representation:

$$
k^{ab}=\sum_{R\ \mathrm{right}}\operatorname{tr}_{R}(T^aT^b)
-
\sum_{R\ \mathrm{left}}\operatorname{tr}_{R}(T^aT^b).
$$

This same $k^{ab}$ appears as the level matrix in the chiral current algebra.

:::note[Consistent versus covariant]
Two-dimensional anomaly formulas often differ by a factor or sign because authors use consistent currents, covariant currents, Euclidean conventions, Lorentzian conventions, or different normalizations of $\epsilon^{\mu\nu}$. The invariant object is the anomaly class and its inflow action, not a single isolated sign.
:::

## Current algebra viewpoint

For a holomorphic current,

$$
J^a(z)J^b(w)
\sim
\frac{k\,\kappa^{ab}}{(z-w)^2}
+
\frac{if^{ab}{}_{c}J^c(w)}{z-w}
+\cdots.
$$

The double pole is a central term. It is not an accident of two-dimensional complex analysis; it is the local imprint of the anomaly coefficient.

The mode expansion gives

$$
[J^a_m,J^b_n]
=
if^{ab}{}_{c}J^c_{m+n}
+
k\,m\,\kappa^{ab}\delta_{m+n,0}.
$$

Thus the same integer or level $k$ can be read as:

- a current-algebra central extension;
- a coefficient in the gauge anomaly;
- a coefficient in a three-dimensional Chern–Simons inflow action;
- a label of affine symmetry in a two-dimensional CFT.

This is why current algebra is not merely a computational trick. It is one of the cleanest anomaly detectors in low dimensions.

## Gravitational anomalies

A two-dimensional theory can also be chiral with respect to spacetime. A CFT has left and right central charges $c_L$ and $c_R$. The difference

$$
c_L-c_R
$$

measures the gravitational anomaly. It controls the failure of the theory to be invariant under large diffeomorphisms or, locally, the obstruction to simultaneously maintaining all desired conservation and covariance properties of the stress tensor.

On the torus, this appears in the $T$ transformation. A state with weights $(h,\bar h)$ contributes the phase

$$
\exp\left[
2\pi i\left(h-\bar h-\frac{c_L-c_R}{24}\right)
\right].
$$

If $c_L-c_R$ is nonzero, the partition function is not usually a scalar modular-invariant function. Instead it may transform as a section of a line bundle over moduli space, or it may require a three-dimensional bulk invertible theory for a complete absolute partition function.

This is the same conceptual pattern as gauge anomaly inflow: the anomalous boundary theory becomes well-defined when paired with a bulk whose variation cancels the boundary variation.

## Trace anomaly

The trace anomaly is different. It is not a chiral anomaly and it is not an obstruction to gauging an internal symmetry. It is the statement that a classically Weyl-invariant two-dimensional theory can acquire a nonzero trace of the stress tensor on curved backgrounds:

$$
\langle T^\mu{}_\mu\rangle
=
-\frac{c}{24\pi}R
$$

in a common Euclidean convention, where $c$ is the Weyl central charge. With left and right central charges, this convention is

$$
c=\frac{c_L+c_R}{2}.
$$

Thus a nonchiral CFT with $c_L=c_R=c$ has the usual coefficient $c$. Some authors instead call $c_L+c_R$ the total central charge; translate before comparing formulas.

This anomaly controls the response of the effective action to Weyl rescaling:

$$
g_{\mu\nu}\mapsto e^{2\sigma}g_{\mu\nu}.
$$

It is responsible for the central charge appearing in the finite-size Casimir energy, the Weyl transformation of partition functions, and the Polyakov effective action for the metric.

The trace anomaly is sometimes called a conformal anomaly. It does not mean scale invariance is “fake.” It means the theory cannot be made invariant under local Weyl rescalings on curved backgrounds without paying a local curvature-dependent price.

## Inflow from three dimensions

Two-dimensional anomalies are naturally packaged by one-higher-dimensional topological terms. For a $U(1)$ anomaly coefficient $k$, the three-dimensional inflow action is schematically

$$
S_{\mathrm{bulk}}[A]
=
\frac{k}{4\pi}\int_M A\wedge dA.
$$

If $M$ has boundary $\Sigma$, a background gauge transformation produces a boundary variation. The anomalous variation of the two-dimensional theory on $\Sigma$ cancels it:

$$
\delta W_{\Sigma}[A]=-\delta S_{\mathrm{bulk}}[A].
$$

For gravitational anomalies, the analogous bulk term is a gravitational Chern–Simons action built from the spin connection. Its coefficient is controlled by $c_L-c_R$.

Inflow is not merely a trick for canceling signs. It explains why an anomalous two-dimensional theory can be a perfectly good boundary of a three-dimensional topological phase. This is the language behind edge modes of quantum Hall systems, chiral CFT boundaries, and modern symmetry TFT.

## Finite symmetries and orbifold anomalies

A finite symmetry in two dimensions has no Noether current, but it can still be anomalous. The anomaly is visible when trying to define twisted sectors

$$
Z_{g,h}
$$

for commuting twists around the two cycles of a torus.

Modular transformations act by

$$
S:\ (g,h)\mapsto(h,g^{-1}),
\qquad
T:\ (g,h)\mapsto(g,gh),
$$

up to convention. If the twisted sectors acquire phases that cannot be removed consistently, the finite symmetry has a ’t Hooft anomaly. Equivalently, the symmetry cannot be gauged without adding a bulk inflow theory or changing the theory.

For finite groups, the anomaly is often represented by a discrete topological action in one higher dimension. In bosonic two-dimensional systems, this is closely related to group-cohomology data in degree three, though fermionic and spacetime symmetries require more refined structures.

## Examples

### One right-moving charged fermion

A single right-moving complex Weyl fermion of charge $q$ has

$$
k=q^2.
$$

It has a chiral $U(1)$ anomaly if that $U(1)$ is treated as a background flavor symmetry. If one attempts to gauge it dynamically with no additional matter, the theory is anomalous.

Adding a left-moving fermion of the same charge cancels the anomaly:

$$
k=q^2-q^2=0.
$$

The resulting Dirac fermion has no vector gauge anomaly, though it may still have an axial anomaly depending on which current is considered.

### Chiral CFT

A purely holomorphic CFT has

$$
c_R=0,\qquad c_L=c.
$$

It is chiral and has gravitational anomaly. It can still appear as the boundary theory of a three-dimensional Chern–Simons theory, where the bulk supplies the missing anomaly inflow.

### Critical Ising model

The ordinary critical Ising CFT has

$$
c_L=c_R=\frac12
$$

in its nonchiral formulation. It has no gravitational anomaly in the full local bosonic theory. But individual chiral sectors, Majorana fermion descriptions, and spin-structure-resolved partition functions require careful modular-covariance bookkeeping.

## Modular invariance as anomaly test

The previous page introduced modular invariance. Now we can reinterpret it: modular covariance of all twisted and spin-structure sectors is a global anomaly test.

A nonanomalous bosonic theory with no background fields should have a modular-invariant torus partition function. A theory with background fields should have a set of partition functions closed under modular transformations. A theory with an anomaly may transform with phases that cannot be removed by local counterterms in two dimensions alone.

Thus modular invariance is not only a CFT consistency condition. It is a low-dimensional version of the background-field anomaly test.

## Common pitfalls

**“A finite symmetry cannot have an anomaly because it has no current.”** False. Anomalies are obstructions to background coupling or gauging, not only current-divergence equations.

**“A gravitational anomaly is the same as a trace anomaly.”** No. The trace anomaly is controlled by the Weyl central charge $c_{\mathrm{Weyl}}=(c_L+c_R)/2$ in the convention where a nonchiral CFT has $c_L=c_R=c_{\mathrm{Weyl}}$. The gravitational anomaly is controlled by $c_L-c_R$ and concerns diffeomorphism or modular covariance.

**“A chiral theory is always inconsistent.”** A chiral theory may be inconsistent as a standalone nonanomalous bosonic two-dimensional theory, but perfectly consistent as a relative theory or boundary of a three-dimensional invertible phase.

**“Anomaly cancellation means every anomalous-looking current is conserved.”** Cancellation means the gauge redundancy or background symmetry can be implemented consistently. Different linear combinations of currents may still have anomalous divergences depending on the backgrounds coupled.

**“The local coefficient is the whole story.”** Local anomaly polynomials do not always capture global, finite, or spin-sensitive anomalies. Two-dimensional examples are a good place to learn this humility.

## Relations to other pages

This page closes the Low-Dimensional Symmetry Technology chapter. It ties together [Bosonization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/bosonization/), [Fermionization](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/fermionization/), [Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/), [Current Algebras](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/current-algebras/), [Affine Symmetries: Preview](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/affine-symmetries-preview/), and [Modular Invariance: Preview](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/modular-invariance-preview/).

The full anomaly formalism lives in [Anomalies](/symmetry-anomalies-topology/anomalies/) and [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/). The inflow and relative-QFT viewpoint lives in [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/).

## Research status

The perturbative gauge, gravitational, and trace anomalies of two-dimensional chiral theories are standard. The current-algebra and modular-covariance diagnostics are also standard tools in two-dimensional CFT.

Active research extends this language to finite and non-invertible symmetries, spin and Pin structures, anomalous topological defects, boundary anomalies, symmetry TFT, fermionic orbifolds, and categorical descriptions of low-dimensional symmetry. The message for readers is stable: anomalies are part of the symmetry data, not optional decorations.

## Exercises

### Exercise 1: Gauge anomaly cancellation

A two-dimensional theory has right-moving Weyl fermions of charges $1,1,2$ and left-moving Weyl fermions of charges $1,3$. Does the $U(1)$ gauge anomaly cancel?

<details><summary><strong>Solution</strong></summary>

Compute

$$
k=\sum_R q_R^2-\sum_L q_L^2.
$$

The right-moving contribution is

$$
1^2+1^2+2^2=6.
$$

The left-moving contribution is

$$
1^2+3^2=10.
$$

Thus

$$
k=6-10=-4.
$$

The anomaly does not cancel. This $U(1)$ cannot be gauged dynamically without adding additional matter or inflow.

</details>

### Exercise 2: Vectorlike pair

Show that a right-moving fermion and a left-moving fermion with the same $U(1)$ charge have no vector gauge anomaly.

<details><summary><strong>Solution</strong></summary>

If both have charge $q$, then

$$
k=q^2-q^2=0.
$$

The right- and left-moving contributions cancel. This is the two-dimensional version of the vectorlike cancellation familiar from Dirac fermions.

</details>

### Exercise 3: Gravitational versus trace anomaly

A CFT has $c_L=5$ and $c_R=2$. Which coefficient controls the gravitational anomaly? Which controls the trace anomaly?

<details><summary><strong>Solution</strong></summary>

The gravitational anomaly is controlled by the difference

$$
c_L-c_R=3.
$$

The trace anomaly is controlled by the Weyl central charge

$$
c_{\mathrm{Weyl}}=\frac{c_L+c_R}{2}=\frac{7}{2}
$$

in the convention of this page. Thus the theory is chiral and also has a nonzero Weyl anomaly on curved backgrounds.

</details>

### Exercise 4: Finite symmetry anomaly as modular obstruction

Explain why inconsistent phases in the modular transformations of twisted sectors $Z_{g,h}$ signal a finite-symmetry anomaly.

<details><summary><strong>Solution</strong></summary>

Gauging a finite symmetry requires summing over all background flat bundles, which on the torus are represented by commuting twists $(g,h)$. The set of sectors must be closed under large diffeomorphisms of the torus, including $S$ and $T$. If modular transformations produce phases that cannot be removed by local counterterms, then the background-field partition function is not consistently defined. That is precisely a ’t Hooft anomaly of the finite symmetry.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “Dilatations,” for current-algebra and anomaly intuition.
- M. Srednicki, *Quantum Field Theory*, §§75–77, for anomalies and fermion path-integral viewpoints.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30, for triangle anomalies, measure derivations, and anomaly matching orientation.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” for the classic treatment of gravitational anomalies.
- P. Ginsparg, “Applied Conformal Field Theory,” for two-dimensional CFT, free fermions on the torus, current algebra, and modular technology.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for modular invariance, characters, minimal models, and 2D CFT anomalies.
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*, for measure-based anomaly derivations.

## Version history

- 2026-06-23: Initial polished draft. Added chiral gauge anomalies, current-algebra levels, gravitational and trace anomalies, finite-symmetry anomaly diagnostics, inflow, modular tests, examples, and exercises.
