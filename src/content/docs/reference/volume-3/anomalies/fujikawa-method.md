---
title: "Fujikawa Method"
description: "Derives the chiral anomaly from the regulated Jacobian of the fermion path-integral measure and its heat-kernel trace."
sidebar:
  label: "Fujikawa Method"
  order: 5
level: Graduate
status: "Polished draft"
source: "Fujikawa; Atiyah–Singer index theorem; Srednicki §77; Schwartz §30.3; Weinberg Vol. II anomaly chapters; Fujikawa–Suzuki."
topics:
  - Fujikawa method
  - path integral measure
  - fermion Jacobian
  - heat kernel
  - chiral anomaly
  - index theorem
  - axial anomaly
canonicalTopics:
  - fujikawa-method
  - fermion-measure-jacobian
  - heat-kernel-regularization
  - index-theorem-anomaly
researchStatus:
  established:
    - "The Fujikawa method derives the chiral anomaly as the regulated Jacobian of the fermion path-integral measure under local axial rotations."
    - "The integrated Fujikawa trace is the local heat-kernel version of the index-theorem statement relating chiral zero modes to topological charge."
  active:
    - "The method continues to inform modern treatments of fermion measures, lattice chiral symmetry, global anomalies, eta invariants, and anomaly inflow."
---

## Summary

The **Fujikawa method** is the measure-theoretic derivation of the chiral anomaly. Its core slogan is

$$
\text{chiral anomaly}=\text{regulated Jacobian of the fermion measure}.
$$

For the axial transformation convention

$$
\delta\psi=\frac{i\alpha}{2}\gamma^5\psi,
\qquad
\delta\bar\psi=\bar\psi\frac{i\alpha}{2}\gamma^5,
$$

the regulated Jacobian contributes exactly the local density needed for

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu},
\qquad
j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![Fujikawa method flow. Choose a gauge-covariant Dirac eigenbasis for the fermion measure, perform an axial rotation, encounter an infinite determinant, regulate the trace by a heat kernel, and obtain the local anomaly density proportional to F tilde F.](/figures/symmetry-anomalies-topology/fujikawa-heat-kernel-jacobian.svg)

<figcaption>

Fujikawa’s calculation. The formal trace $\operatorname{tr}\gamma^5$ is not the anomaly. The anomaly is the gauge-covariantly regulated ultraviolet trace $\lim_{M\to\infty}\operatorname{tr}\bigl(\gamma^5 e^{-\mathcal D_E^2/M^2}\bigr)(x,x)$.

</figcaption>
</figure>

The method is powerful because it makes the anomaly look inevitable: if the fermion measure is defined using a gauge-covariant Dirac operator, an axial rotation changes the measure by a local topological density.

## Prerequisites

Read [Regulator and Measure Viewpoints](/symmetry-anomalies-topology/anomalies/regulator-and-measure-viewpoints/), [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/), and [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/) first.

You should also be comfortable with Grassmann Gaussian integrals, Dirac operators, Wick rotation, and the idea of a heat-kernel regulator. The page uses only the first few terms of the heat-kernel expansion; a fuller treatment belongs with index theory and curved-spacetime methods.

## Core idea

The formal path integral for a Dirac fermion in a background gauge field is

$$
Z[A]=\int D\bar\psi D\psi\,e^{iS[\bar\psi,\psi;A]}.
$$

A classical axial rotation can leave the massless action invariant. But the integration measure is not automatically invariant because it is defined by expanding the field in infinitely many modes.

In finite dimensions, a Grassmann change of variables produces an inverse determinant. In field theory, the corresponding determinant is infinite:

$$
D\bar\psi D\psi\longrightarrow J[\alpha,A]D\bar\psi D\psi.
$$

Fujikawa’s insight is to compute $J[\alpha,A]$ using a regulator tied to the Dirac operator. Gauge covariance tells us which regulator to use. The regulated trace is not zero; it is proportional to $F\widetilde F$.

The slogan is

$$
\text{chiral anomaly}=\text{regulated Jacobian of the fermion measure}.
$$

## Setup and conventions

The Lorentzian conventions of this volume are

$$
D_\mu=\partial_\mu-iqA_\mu,
\qquad
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\epsilon^{0123}=+1.
$$

For the heat-kernel calculation, we temporarily use a Euclidean Dirac operator

$$
\mathcal D_E=\gamma_E^\mu(\partial_\mu-iqA_\mu),
$$

where the Euclidean gamma matrices are Hermitian and satisfy

$$
\{\gamma_E^\mu,\gamma_E^\nu\}=2\delta^{\mu\nu}.
$$

The Euclidean operator $\mathcal D_E^2$ is elliptic, so the heat kernel

$$
e^{-\mathcal D_E^2/M^2}
$$

is a natural local ultraviolet regulator.

:::note[Convention-sensitive source note]
Some derivations use a Lorentzian Dirac operator, some use a Euclidean anti-Hermitian Dirac operator, and some absorb the gauge coupling into $A$. The final Lorentzian identity on this site is

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

for $j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi$. Use this equation as the convention anchor.
:::

## Defining the fermion measure

Choose a complete orthonormal basis of spinor wavefunctions $\{\varphi_n(x)\}$, usually eigenfunctions of the Euclidean Dirac operator:

$$
\mathcal D_E\varphi_n=\lambda_n\varphi_n,
\qquad
\int d^4x\,\varphi_m^\dagger(x)\varphi_n(x)=\delta_{mn}.
$$

Expand

$$
\psi(x)=\sum_n a_n\varphi_n(x),
\qquad
\bar\psi(x)=\sum_n \bar b_n\varphi_n^\dagger(x).
$$

The fermion measure is then

$$
D\bar\psi D\psi=\prod_n d\bar b_n\,da_n.
$$

This equation is a definition. Changing the basis changes the coordinate description of the measure. A unitary change of basis is harmless in finite dimensions, but an infinite product of phases is not automatically well-defined.

The choice of basis is also physical. To preserve gauge invariance, the basis should transform covariantly under gauge transformations. This is why the eigenbasis of the gauge-covariant Dirac operator is the right one for the anomaly calculation.

## Axial rotation and the infinite determinant

Under a local axial rotation,

$$
\psi'(x)=e^{i\alpha(x)\gamma^5/2}\psi(x),
\qquad
\bar\psi'(x)=\bar{\psi}(x)e^{i\alpha(x)\gamma^5/2},
$$

the mode coefficients transform linearly:

$$
a'_m=\sum_n C_{mn}a_n,
$$

where, to first order in $\alpha$,

$$
C_{mn}=\delta_{mn}+\frac{i}{2}\int d^4x\,\varphi_m^\dagger(x)\alpha(x)\gamma^5\varphi_n(x).
$$

Grassmann integration gives the inverse determinant. Since both $\psi$ and $\bar\psi$ transform, the measure acquires a product of two inverse determinants:

$$
D\bar\psi' D\psi'
=(\det C)^{-2}D\bar\psi D\psi.
$$

Formally,

$$
\log J=-2\operatorname{Tr}\log C
=-i\sum_n\int d^4x\,\alpha(x)\varphi_n^\dagger(x)\gamma^5\varphi_n(x).
$$

The sum is the dangerous object:

$$
\sum_n\varphi_n^\dagger(x)\gamma^5\varphi_n(x)
=\operatorname{tr}\left(\gamma^5\delta(x-x)\right).
$$

Naively, $\operatorname{tr}\gamma^5=0$. But the trace is infinite-dimensional and singular at coincident points. One must regulate it.

## Gauge-covariant heat-kernel regulator

Fujikawa’s regulator replaces the formal sum by

$$
\mathcal A_M(x)
=\sum_n\varphi_n^\dagger(x)\gamma^5 e^{-\lambda_n^2/M^2}\varphi_n(x).
$$

Equivalently,

$$
\mathcal A_M(x)
=\operatorname{tr}\left[\gamma^5 e^{-\mathcal D_E^2/M^2}\right](x,x),
$$

where $\operatorname{tr}$ is over spin and internal indices, and $(x,x)$ denotes the coincident-point kernel.

Then define

$$
\mathcal A(x)=\lim_{M\to\infty}\mathcal A_M(x).
$$

The exponential suppresses high eigenvalues while preserving gauge covariance. This is the crucial move. A regulator such as $e^{-\partial^2/M^2}$ would not be gauge covariant in a background gauge field, and would not define the same quantum theory.

## Evaluating the local trace

The square of the Euclidean Dirac operator has the schematic form

$$
\mathcal D_E^2=D_E^2-\frac{iq}{4}[\gamma_E^\mu,\gamma_E^\nu]F_{\mu\nu}.
$$

Only terms with four gamma matrices survive the $\gamma^5$ trace. Expanding the heat kernel to second order in $F$ gives the finite term. After continuing back to the Lorentzian convention used in this volume, the Jacobian and the action variation combine to produce the Ward-identity density

$$
\mathcal A_{\text{Ward}}(x)
=\frac{q^2}{32\pi^2}\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}
=\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Thus, when $m=0$,

$$
\partial_\mu j_A^\mu
=\frac{q^2}{32\pi^2}\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}
=\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Restoring the explicit mass term gives

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This is the same formula obtained from the triangle diagram.

## Why the formal trace is misleading

It is tempting to say

$$
\operatorname{tr}\gamma^5=0,
$$

so the Jacobian must be one. This is the wrong trace. The anomaly is not the trace over a single finite-dimensional spinor fiber. It is the regulated trace over spin, internal indices, and spacetime modes:

$$
\operatorname{Tr}_{\text{modes}}\left(\alpha\gamma^5 e^{-\mathcal D_E^2/M^2}\right).
$$

The heat kernel detects the ultraviolet asymmetry induced by the gauge-field background. Nonzero eigenvalues of $\mathcal D_E$ often pair between chiralities, but the local regulated density need not vanish before integration; and zero modes can leave an integrated chirality imbalance.

The difference between

$$
\operatorname{tr}_{\text{spin}}\gamma^5=0
$$

and

$$
\lim_{M\to\infty}\operatorname{Tr}_{\text{modes}}
\left(\gamma^5e^{-\mathcal D_E^2/M^2}\right)
\ne 0
$$

is the whole method in one line.

## Integrated anomaly and zero modes

On a compact Euclidean spacetime, the integrated Fujikawa trace is related to the index of the Dirac operator:

$$
\operatorname{index}(\mathcal D_E)
=n_+-n_-,
$$

where $n_\pm$ are the numbers of zero modes with positive and negative chirality. Nonzero eigenmodes pair and do not contribute to the integrated index. The zero modes do.

In a flat four-dimensional gauge background, the index theorem gives schematically

$$
n_+-n_-
=\frac{1}{32\pi^2}\int d^4x\,
\epsilon^{\mu\nu\rho\sigma}\operatorname{tr}_R(F_{\mu\nu}F_{\rho\sigma}),
$$

with trace normalization determined by the representation $R$ and the generator convention.

This is the global version of the local Fujikawa calculation. The heat-kernel coefficient produces the local anomaly density; the integrated density counts net chiral zero modes.

## Nonabelian generalization

For a Dirac fermion in representation $R$, take

$$
D_\mu=\partial_\mu-igA_\mu^aT_R^a.
$$

The regulated trace includes the trace over $R$. The axial anomaly becomes

$$
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{g^2}{16\pi^2}\operatorname{tr}_R(F_{\mu\nu}\widetilde F^{\mu\nu})
$$

in the same current convention, up to the sign conventions already stated. If

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
$$

then

$$
\operatorname{tr}_R(F_{\mu\nu}\widetilde F^{\mu\nu})
=T(R)F_{\mu\nu}^a\widetilde F^{a\mu\nu}.
$$

For chiral gauge anomalies, the same method is applied to Weyl fermion measures. The result is subtler because the anomaly is a gauge variation of the effective action rather than a global axial-current divergence. That story leads to consistent and covariant anomalies, Wess–Zumino consistency, anomaly polynomials, and descent.

## Relation to the triangle diagram

The triangle diagram and the Fujikawa method look different, but they compute the same obstruction.

In the triangle diagram, the anomaly appears because a superficially linearly divergent integral cannot be shifted while preserving all Ward identities. Preserving vector gauge invariance forces the axial divergence.

In Fujikawa’s method, the anomaly appears because the gauge-covariant definition of the fermion measure is not invariant under axial rotations. Preserving vector gauge covariance in the regulator forces the axial Jacobian.

The matching is not an accident. Both calculations ask for a local, gauge-invariant ultraviolet definition of the fermion determinant. The triangle calculation sees the determinant expanded to third order in sources. Fujikawa sees the same determinant through its infinitesimal change under a chiral rotation.

## Relation to index theory

Fujikawa’s computation is also the physicist’s local version of the index theorem. The same heat-kernel coefficient that produces the anomaly density appears in the index formula for a Dirac operator.

This connection explains several facts at once:

- the anomaly coefficient is topological and robust;
- instantons produce chiral zero modes;
- axial charge violation is tied to gauge-field topology;
- anomaly inflow can package boundary anomalies using one-higher-dimensional topological terms.

A useful mental picture is

$$
\text{triangle graph}
\quad\leftrightarrow\quad
\text{local heat-kernel coefficient}
\quad\leftrightarrow\quad
\text{index density}
\quad\leftrightarrow\quad
\text{inflow polynomial}.
$$

Each arrow hides convention choices, but the invariant content is the same.

## What the method does not say by itself

Fujikawa’s method is elegant, but it is easy to overstate what it proves on its own.

First, the method assumes a regulated fermion determinant and a choice of measure. It diagnoses how that measure transforms; it does not by itself solve every problem of defining an interacting chiral gauge theory nonperturbatively.

Second, the heat-kernel calculation is one-loop in disguise. The anomaly coefficient is one-loop exact, but that exactness is an additional theorem, not merely a consequence of writing down a Jacobian.

Third, global anomalies may not be visible in an infinitesimal local trace. Some anomalies appear only under large gauge transformations or on manifolds with nontrivial topology. Those require eta invariants, determinant-line bundles, cobordism, or related global tools.

## Common pitfalls

**Pitfall 1: Treating $\operatorname{tr}\gamma^5=0$ as the end of the calculation.**  
The anomaly uses an infinite-dimensional, regulated, coincident-point trace. The finite spinor trace alone is not the right object.

**Pitfall 2: Using a non-gauge-covariant regulator.**  
A regulator built from $\partial^2$ rather than the gauge-covariant Dirac operator can erase or distort the anomaly by breaking the wrong symmetry.

**Pitfall 3: Forgetting the Grassmann inverse determinant.**  
Fermion variables transform with inverse determinants. Both $\psi$ and $\bar\psi$ contribute.

**Pitfall 4: Comparing Euclidean signs too literally.**  
Different Wick rotations and Hermiticity conventions change intermediate signs. Anchor comparisons to the final Lorentzian Ward identity.

**Pitfall 5: Thinking Fujikawa replaces the triangle diagram.**  
It complements it. The two calculations are different presentations of the same ultraviolet obstruction.

## Relations to other pages

This page is the measure-level derivation of the [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/). The diagrammatic derivation is [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/), and the broader conceptual setup is [Regulator and Measure Viewpoints](/symmetry-anomalies-topology/anomalies/regulator-and-measure-viewpoints/).

Next, the same mechanism leads to [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

For topological consequences, see [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/), [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), and [Eta Invariants](/symmetry-anomalies-topology/topological-terms/eta-invariants-preview/).

## Research status

The Fujikawa method is established. It is a standard and reliable way to compute local perturbative fermion anomalies when the regulator, current normalization, and Euclidean continuation are specified.

Modern uses go beyond the original local chiral anomaly. The underlying idea — anomalies as phases or sections of determinant lines associated with fermion measures — is central to global anomalies, eta invariants, lattice chiral fermions, anomaly inflow, and fermionic symmetry-protected phases.

## Exercises

### Exercise 1: Grassmann inverse determinant

Let $a'_m=C_{mn}a_n$ for finitely many Grassmann coefficients. Show that

$$
\prod_m da'_m=(\det C)^{-1}\prod_m da_m.
$$

<details><summary><strong>Solution</strong></summary>

For one Grassmann variable $a'=ca$, Berezin integration requires

$$
1=\int da'\,a'=\int c^{-1}da\,ca.
$$

Thus $da'=c^{-1}da$. For many variables, diagonalize or triangularize the matrix $C$, or use the defining Berezin integral of the top monomial. Each eigenvalue contributes inversely, so

$$
\prod_m da'_m=(\det C)^{-1}\prod_m da_m.
$$

In a field theory the determinant becomes infinite-dimensional and must be regulated.

</details>

### Exercise 2: Why nonzero modes pair in the integrated trace

Assume the massless Euclidean Dirac operator anticommutes with $\gamma^5$:

$$
\{\mathcal D_E,\gamma^5\}=0.
$$

Show that if $\varphi$ is an eigenmode with nonzero eigenvalue $\lambda$, then $\gamma^5\varphi$ is an eigenmode with eigenvalue $-\lambda$.

<details><summary><strong>Solution</strong></summary>

If

$$
\mathcal D_E\varphi=\lambda\varphi,
$$

then using $\mathcal D_E\gamma^5=-\gamma^5\mathcal D_E$ gives

$$
\mathcal D_E(\gamma^5\varphi)
=-\gamma^5\mathcal D_E\varphi
=-\lambda\gamma^5\varphi.
$$

Thus nonzero eigenvalues come in opposite-sign pairs. In the integrated trace of $\gamma^5$, these paired modes cancel. Zero modes need not pair and give the index.

</details>

### Exercise 3: Regulated trace versus finite spin trace

Explain why the equality

$$
\operatorname{tr}_{\text{spin}}\gamma^5=0
$$

does not imply

$$
\operatorname{Tr}\left(\gamma^5e^{-\mathcal D_E^2/M^2}\right)=0.
$$

<details><summary><strong>Solution</strong></summary>

The first trace is over a finite-dimensional spinor space at a point. The second trace is over spinor indices, internal indices, and spacetime modes, with a differential operator inserted.

The heat-kernel factor depends on the gauge background through $\mathcal D_E^2$. Its short-distance expansion contains gamma-matrix structures built from $F_{\mu\nu}$. When two field strengths appear, their gamma matrices can combine with $\gamma^5$ to produce an epsilon tensor. Therefore the regulated trace has a finite local term proportional to $F\widetilde F$.

</details>

### Exercise 4: From Jacobian to Ward identity

For a local axial rotation, suppose the first-order change of the action and measure combine as

$$
D\bar\psi'D\psi'\,e^{iS'}
=D\bar\psi D\psi\,e^{iS}
\exp\left[-i\int d^4x\,\alpha(x)
\left(\partial_\mu j_A^\mu-\mathcal A(x)\right)\right]
$$

inside correlation functions of invariant insertions. Show that the Ward identity is

$$
\partial_\mu j_A^\mu=\mathcal A
$$

up to contact terms.

<details><summary><strong>Solution</strong></summary>

A change of integration variables cannot change the value of the path integral. Expanding the exponential to first order in the arbitrary function $\alpha(x)$ gives

$$
0=-i\int d^4x\,\alpha(x)
\left\langle\partial_\mu j_A^\mu(x)-\mathcal A(x)\right\rangle
$$

for invariant insertions. Since $\alpha(x)$ is arbitrary,

$$
\partial_\mu j_A^\mu=\mathcal A
$$

inside such correlators. If the inserted operators transform under the axial symmetry, their variations add the usual contact terms.

</details>

## References

- K. Fujikawa, “Path-Integral Measure for Gauge-Invariant Fermion Theories,” *Physical Review Letters* **42** (1979).
- K. Fujikawa, “Path Integral for Gauge Theories with Fermions,” *Physical Review D* **21** (1980).
- M. F. Atiyah and I. M. Singer, “The Index of Elliptic Operators,” *Annals of Mathematics* **87** (1968).
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*, Oxford University Press.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*, Oxford University Press.
- M. Srednicki, *Quantum Field Theory*, §77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.3.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, anomaly chapters.

## Version history

- 2026-06-18: First polished draft. Added fermion-measure construction, axial Jacobian, heat-kernel regulator, local trace evaluation, index-theorem connection, nonabelian generalization, and exercises.
