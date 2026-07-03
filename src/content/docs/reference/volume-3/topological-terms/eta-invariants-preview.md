---
title: "Eta Invariants: Preview"
description: "Introduces eta invariants as spectral-asymmetry terms that refine Chern–Simons actions, parity anomalies, and fermionic topological response."
sidebar:
  label: "Eta Invariants: Preview"
  order: 11
level: Advanced
status: "Polished draft"
source: "Atiyah–Patodi–Singer; Dai–Freed; Witten on fermion path integrals and topological phases; parity-anomaly and topological-response references."
topics:
  - eta invariant
  - spectral asymmetry
  - Atiyah–Patodi–Singer index theorem
  - parity anomaly
  - fermion determinant
  - topological response
  - anomaly inflow
canonicalTopics:
  - eta-invariant
  - aps-index-theorem
  - spectral-asymmetry
  - parity-anomaly
  - fermionic-topological-response
researchStatus:
  established:
    - "The APS eta invariant measures the regularized spectral asymmetry of a self-adjoint elliptic operator and appears in index theorems on manifolds with boundary."
    - "In QFT, eta invariants give a precise language for phases of fermion determinants, parity anomalies, and certain fermionic invertible phases."
  active:
    - "Current work uses Dai–Freed and eta-invariant language to formulate global anomalies, fermionic SPT phases, domain-wall fermions, and symmetry TFTs with spin or Pin structure."
---

## Summary

An eta invariant is a regularized measure of spectral asymmetry. If $D$ is a self-adjoint Dirac-type operator with real eigenvalues $\lambda$, the eta function is formally

$$
\eta_D(s)=\sum_{\lambda\ne0}\frac{\operatorname{sign}(\lambda)}{|\lambda|^s},
$$

and the eta invariant is the analytically continued value

$$
\eta_D(0).
$$

The number is subtle: it is not simply a count of positive minus negative eigenvalues, because both counts are usually infinite. It is the regularized imbalance.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing spectral asymmetry of a Dirac operator, the eta invariant, the APS index formula, and anomaly inflow.](/figures/symmetry-anomalies-topology/eta-invariant-spectral-inflow.svg)

<figcaption>

Eta invariants turn spectral asymmetry into topological response data. In the APS index theorem, a bulk characteristic-class integral fails to be an integer by a boundary reduced eta invariant. In QFT, the same structure controls fermion determinant phases, parity anomalies, and inflow.

</figcaption>
</figure>

Eta invariants are the refined version of a theme already seen throughout this chapter: local differential forms do not always give the whole topological action. For fermions, especially on manifolds with boundary or with time-reversal/reflection structure, the missing global information is often spectral.

## Prerequisites

Read [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/), [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/), [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/), and [Witten Effect: Preview](/symmetry-anomalies-topology/topological-terms/witten-effect-preview/) first.

You should also know the anomaly-inflow viewpoint from [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) and the fermionic-background caveats from [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/).

## Core idea

Bosonic topological terms are often written as integrals of characteristic classes or Chern–Simons forms. Fermions ask for something sharper.

A massive fermion determinant has a magnitude and a phase. The magnitude is controlled by ordinary eigenvalue sizes. The phase is controlled by how many eigenvalues are positive versus negative, after regularization. That regularized imbalance is the eta invariant.

In odd spacetime dimension, this is the mathematical heart of the parity anomaly. A single massive Dirac fermion induces a Chern–Simons-like response at half-integer level. Written purely as a local Chern–Simons functional, that response can look gauge-variant under large gauge transformations. Written with an eta invariant, the same response can be made globally meaningful, provided the correct spin or bulk data are included.

The slogan is

$$
\text{eta invariant}
=\text{global spectral completion of local Chern–Simons response}.
$$

## Setup and conventions

Let $Y$ be a closed odd-dimensional Riemannian manifold with spin structure, gauge bundle, and a self-adjoint Dirac-type operator

$$
D_Y.
$$

Its nonzero eigenvalues are real:

$$
D_Y\psi_\lambda=\lambda\psi_\lambda,
\qquad \lambda\in\mathbb R.
$$

The eta function is

$$
\eta_D(s)=\sum_{\lambda\ne0}\operatorname{sign}(\lambda)|\lambda|^{-s},
$$

initially defined where the sum converges and then continued meromorphically. For Dirac-type operators in the usual APS setting, it is regular at $s=0$, and one defines

$$
\eta(D_Y)=\eta_D(0).
$$

If $h=\dim\ker D_Y$, the reduced eta invariant is

$$
\bar\eta(D_Y)=\frac{\eta(D_Y)+h}{2}.
$$

Only certain combinations of $\bar\eta$ are invariant under all choices. In physics, the exponentiated quantity is often more meaningful than the real number itself:

$$
\exp\bigl(2\pi i\,\bar\eta(D_Y)\bigr)
\quad\text{or}\quad
\exp\bigl(-i\pi\,\bar\eta(D_Y)\bigr),
$$

depending on the fermion convention and dimension.

:::note[Convention-sensitive source note]
Signs in eta-invariant formulas depend on whether $Y$ is the incoming or outgoing boundary of the bulk, on the orientation convention for the Dirac operator, and on whether the fermion determinant is written for $D+m$, $iD+m$, or a Euclidean hermitian operator. This page fixes the conceptual role and gives standard representative formulas; detailed applications must restate the sign convention.
:::

## From finite matrices to spectral asymmetry

For a finite-dimensional hermitian matrix $H$ with no zero eigenvalues, the naive spectral asymmetry is

$$
N_+-N_-,
$$

where $N_+$ and $N_-$ are the numbers of positive and negative eigenvalues.

Equivalently,

$$
N_+-N_- =\sum_{\lambda\ne0}\operatorname{sign}(\lambda).
$$

For a differential operator, both $N_+$ and $N_-$ are infinite. The eta function regularizes the same idea by weighting high eigenvalues:

$$
\eta_D(s)=\sum_{\lambda\ne0}\operatorname{sign}(\lambda)|\lambda|^{-s}.
$$

For $\operatorname{Re}s$ large, the sum is better behaved. The value at $s=0$ is then defined by analytic continuation.

This is why eta invariants are sensitive but not crude. They remember an infinite-dimensional asymmetry in a way compatible with elliptic analysis.

## The APS index theorem

Eta invariants enter QFT because they appear in index theorems with boundaries. Let $X$ be an even-dimensional compact spin manifold with boundary

$$
\partial X=Y.
$$

Let $\mathcal D_X$ be a Dirac operator on $X$, with an Atiyah–Patodi–Singer boundary condition determined by the boundary operator $D_Y$. A standard form of the APS index theorem is

$$
\operatorname{Ind}(\mathcal D_X^{\mathrm{APS}})
=\int_X \widehat A(TX)\operatorname{ch}(E)
-\bar\eta(D_Y).
$$

Here $\widehat A(TX)$ is the A-roof genus built from curvature, $\operatorname{ch}(E)$ is the Chern character of the gauge bundle, and

$$
\bar\eta(D_Y)=\frac{\eta(D_Y)+h}{2}.
$$

The left-hand side is an integer. Therefore

$$
\int_X \widehat A(TX)\operatorname{ch}(E)-\bar\eta(D_Y)
\in\mathbb Z.
$$

This is the key physics lesson. A bulk integral of characteristic classes is generally not an integer on a manifold with boundary. The eta invariant supplies the boundary correction.

## Eta as the boundary correction to Chern–Simons

Chern–Simons terms are local descendants of characteristic classes. For example, in three dimensions the abelian term

$$
\frac{k}{4\pi}\int_Y A\wedge dA
$$

is locally related to the four-dimensional class

$$
\frac{k}{4\pi}\int_X F\wedge F.
$$

But local Chern–Simons formulas do not always behave well under large gauge transformations, spin-structure changes, or boundary choices. Eta invariants provide a global completion.

A rough but useful relation is

$$
\bar\eta(D_Y)
\equiv
\int_X \widehat A(TX)\operatorname{ch}(E)
\pmod{\mathbb Z},
$$

whenever $Y$ bounds a suitable $X$. The right-hand side has the familiar local characteristic-class form. The left-hand side is intrinsic spectral data on the boundary.

The equality modulo integers is exactly what an exponentiated action needs. Since

$$
e^{2\pi i n}=1
\qquad n\in\mathbb Z,
$$

the phase can be computed either by a bulk integral or by an eta invariant, when the hypotheses apply.

## Massive fermions and determinant phases

Consider a massive fermion in an odd-dimensional Euclidean theory. The fermion path integral produces a determinant. Schematically,

$$
Z_m[A,g]=\det(D_Y+m).
$$

The absolute value of this determinant is not topological. The phase has a topological large-mass limit. In a common convention,

$$
\frac{Z_m}{|Z_m|}
\sim
\exp\!\left(-i\pi\,\operatorname{sign}(m)\,\bar\eta(D_Y)\right)
$$

up to local counterterms and convention-dependent signs.

Changing the sign of the mass changes the topological phase. This is the field-theory reason that massive fermions in odd dimensions induce Chern–Simons terms.

For a three-dimensional Dirac fermion coupled to a background gauge field, integrating out the fermion gives, at low energy,

$$
\Delta k=\frac{1}{2}\operatorname{sign}(m)
$$

for the induced Chern–Simons level, in the simplest unit-charge normalization. A half-integer level is exactly where large-gauge and spin-structure subtleties become unavoidable.

## The parity anomaly

The parity anomaly is the statement that a single massless Dirac fermion in three dimensions cannot be regularized while preserving both gauge invariance and parity or time reversal as standalone symmetries, under the usual assumptions.

A Pauli–Villars regulator mass has a sign. That sign induces a half-level Chern–Simons counterterm. Choosing one sign preserves gauge invariance but breaks parity. Trying to keep parity makes gauge invariance under large transformations fail.

The eta-invariant viewpoint makes the tension precise. The fermion determinant phase is not an ordinary function on the space of background gauge fields; it is more naturally a section of a determinant line. The eta invariant, or more precisely the Dai–Freed construction, supplies the extra data needed to define the exponentiated partition function globally.

This is why eta invariants sit at the meeting point of three subjects:

$$
\text{fermion determinants}
\quad\leftrightarrow\quad
\text{Chern–Simons response}
\quad\leftrightarrow\quad
\text{global anomalies}.
$$

## Topological insulators and theta equals pi

The Witten-effect page explained that a four-dimensional theta term at $\theta=\pi$ gives half electric charge to a unit monopole, in suitable units. For an ordinary bosonic theory, writing $\theta=\pi$ while preserving time reversal can be subtle. For electronic topological insulators, the subtlety is resolved by the fact that the microscopic theory is fermionic and depends on spin structure.

A three-dimensional boundary Dirac cone has a parity anomaly. It cannot be defined as a standalone time-reversal-invariant, gauge-invariant theory in complete generality. But it can live as the boundary of a four-dimensional bulk whose response cancels the anomaly by inflow.

Eta invariants give a precise global language for that statement. They refine the naive boundary Chern–Simons term and keep track of the spectral asymmetry of the boundary Dirac operator.

## Eta invariant versus local counterterms

Eta invariants are not immune to all choices. As the metric or background connection varies, $\eta(D_Y)$ can vary continuously. Its variation is local and is captured by characteristic forms. Local counterterms can shift the representative of the response.

This mirrors the anomaly story:

$$
\text{representative changes, anomaly class remains.}
$$

For many physical applications, the invariant information is not the real number $\eta(D_Y)$ itself, but an exponentiated phase modulo local counterterms and integers.

One should therefore avoid saying “the eta invariant is topological” without qualification. It is spectral. It becomes part of a topological or invertible response only after the correct combination, quotient, or exponentiation is specified.

## Dai–Freed viewpoint

The APS formula is powerful, but ordinary APS boundary conditions are nonlocal from the boundary QFT point of view. The Dai–Freed framework packages the exponentiated eta invariant as an object living in a determinant line associated with the boundary fermions.

Physically, this says that an anomalous boundary partition function may not be a complex number by itself. It may be a vector in a line. The bulk eta-invariant term supplies the dual vector needed to produce an honest number:

$$
Z_{\mathrm{bulk}}\,Z_{\mathrm{boundary}}\in\mathbb C.
$$

This is one mathematically precise version of anomaly inflow.

The slogan is not “the boundary anomaly disappears.” It is

$$
\text{boundary non-invariance is canceled by bulk non-invariance}.
$$

The combined bulk-boundary system is well-defined.

## Global anomalies

Perturbative anomalies are visible from local anomaly polynomials. Global anomalies are often invisible to infinitesimal transformations and appear only around nontrivial loops in background-field space.

Eta invariants detect such effects. If one moves around a closed loop of background fields, eigenvalues can flow through zero. The determinant line can acquire holonomy. The eta invariant records the corresponding global phase.

This is why eta-invariant and determinant-line language appears in modern treatments of global anomalies. It is the spectral counterpart of the statement that not every anomaly is captured by a local Feynman diagram.

## Common pitfalls

**Confusing eta with the Dedekind eta function.** They are different objects. The APS eta invariant is a spectral invariant of an operator.

**Calling eta simply positive eigenvalues minus negative eigenvalues.** That slogan is useful but incomplete. In QFT, both counts are infinite and require analytic regularization.

**Forgetting zero modes.** The reduced eta invariant includes $h=\dim\ker D$. Zero modes matter for continuity and for index-theorem formulas.

**Treating eta as purely topological.** Eta depends on spectral geometry. Only particular exponentiated or combined quantities define topological response data.

**Replacing eta by Chern–Simons too quickly.** Chern–Simons forms are local representatives. Eta invariants are global spectral completions. The difference matters for large gauge transformations, spin structures, boundaries, and global anomalies.

**Ignoring determinant lines.** An anomalous fermion partition function may not be an ordinary function. The line-bundle viewpoint is not pedantry; it is the clean way to say what the path integral means.

## Relations to other pages

[Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) gives the local descendant actions that eta invariants refine. [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/) explains why response phases are robust modulo counterterms. [Witten Effect: Preview](/symmetry-anomalies-topology/topological-terms/witten-effect-preview/) gives the theta-angle manifestation of the same fermionic-topological-insulator story.

The anomaly side is developed in [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/), and [Anomalies and Boundaries](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-boundaries/).

## Research status

The APS eta invariant and the APS index theorem are established mathematics. Their use in fermion determinant phases, parity anomalies, and anomaly inflow is also standard in modern QFT.

Active research concerns the best physics-friendly formulations of these structures for general global symmetries, spin and Pin structures, lattice/domain-wall fermions, crystalline and reflection symmetries, interacting fermionic SPT phases, and symmetry TFTs. A recurring theme is to replace informal “half Chern–Simons” language with globally meaningful eta-invariant or invertible-field-theory statements.

## Exercises

### Exercise 1: Eta invariant for a symmetric spectrum

Suppose a self-adjoint operator has nonzero eigenvalues paired as $\lambda$ and $-\lambda$, with equal multiplicity, and has no zero modes. What is $\eta(0)$?

<details><summary><strong>Solution</strong></summary>

For every positive eigenvalue contribution

$$
+|\lambda|^{-s},
$$

there is a negative eigenvalue contribution

$$
-|\lambda|^{-s}.
$$

The terms cancel pairwise, so

$$
\eta_D(s)=0
$$

where the sum is defined, and hence by analytic continuation

$$
\eta_D(0)=0.
$$

</details>

### Exercise 2: Reduced eta and zero modes

Let $\eta(D)=3$ and $h=\dim\ker D=1$. Compute $\bar\eta(D)$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\bar\eta(D)=\frac{\eta(D)+h}{2}
=\frac{3+1}{2}=2.
$$

The reduced invariant includes the zero-mode contribution.

</details>

### Exercise 3: APS integrality check

Assume

$$
\int_X\widehat A(TX)\operatorname{ch}(E)=\frac{5}{3}
$$

and

$$
\bar\eta(D_Y)=\frac{2}{3}.
$$

What is the APS index?

<details><summary><strong>Solution</strong></summary>

The APS formula gives

$$
\operatorname{Ind}(\mathcal D_X^{\mathrm{APS}})
=\frac{5}{3}-\frac{2}{3}=1.
$$

The result is an integer, as required.

</details>

### Exercise 4: Why half-level Chern–Simons is suspicious

For an ordinary bosonic $U(1)$ Chern–Simons action,

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int A\wedge dA,
$$

large-gauge invariance usually requires $k\in\mathbb Z$. Why does a single massive three-dimensional Dirac fermion inducing $\Delta k=\frac{1}{2}\operatorname{sign}(m)$ signal a subtlety?

<details><summary><strong>Solution</strong></summary>

A half-integer level is not an ordinary standalone bosonic Chern–Simons response under the usual assumptions. Therefore the induced response cannot be interpreted naively as an independent bosonic topological field theory on all manifolds. The missing data are supplied by spin structure, a regulator choice, a boundary/bulk inflow term, or an eta-invariant refinement. This is the parity-anomaly subtlety.

</details>

## References

- M. F. Atiyah, V. K. Patodi, and I. M. Singer, “Spectral Asymmetry and Riemannian Geometry I,” *Mathematical Proceedings of the Cambridge Philosophical Society* **77** (1975) 43–69.
- M. F. Atiyah, V. K. Patodi, and I. M. Singer, “Spectral Asymmetry and Riemannian Geometry II,” *Mathematical Proceedings of the Cambridge Philosophical Society* **78** (1975) 405–432.
- M. F. Atiyah, V. K. Patodi, and I. M. Singer, “Spectral Asymmetry and Riemannian Geometry III,” *Mathematical Proceedings of the Cambridge Philosophical Society* **79** (1976) 71–99.
- X. Dai and D. S. Freed, “Eta-Invariants and Determinant Lines,” arXiv:hep-th/9405012.
- E. Witten, “Fermion Path Integrals And Topological Phases,” arXiv:1508.04715.
- K. Yonekura, “Dai–Freed theorem and topological phases of matter,” arXiv:1607.01873.
- M. F. Lapa, “A note on the parity anomaly from the Hamiltonian point of view,” arXiv:1903.06719.

## Version history

- 2026-06-18: First polished draft. Added spectral-asymmetry definition, APS index formula, determinant-phase interpretation, parity-anomaly discussion, Dai–Freed viewpoint, and exercises.
