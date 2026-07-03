---
title: "Ward Identities: Operator Form"
description: "Derives Ward identities from conserved charges, time ordering, equal-time commutators, and charge-surface deformation in the operator formalism."
sidebar:
  label: "Operator Ward Identities"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman lectures on symmetries and current algebra; Srednicki §22 and §§67–68; Weinberg Vol. I on symmetry generators; Schwartz chapters on Ward–Takahashi identities."
topics:
  - Ward identities
  - operator formalism
  - time ordering
  - equal-time commutators
  - conserved charges
  - current insertions
canonicalTopics:
  - operator-ward-identity
  - ward-takahashi-identity
  - equal-time-commutator-contact-term
  - charge-surface-deformation
researchStatus:
  established:
    - "For exact nonanomalous continuous symmetries, operator Ward identities follow from current conservation away from insertions plus equal-time commutators of the charge density with charged operators."
  active:
    - "In gauge theories, theories with boundaries or defects, anomalous theories, and theories with composite current insertions, local contact terms and current algebra require regulator and scheme choices."
---

## Summary

The operator proof of a Ward identity is the cleanest way to see why contact terms are unavoidable.

Let $j_a^\mu$ be the current for an exact continuous symmetry and let

$$
\mathcal X=
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n).
$$

Away from operator insertions,

$$
\partial_\mu j_a^\mu=0.
$$

Inside a time-ordered correlator, however, differentiating the time-ordering symbol also differentiates step functions. Those derivatives produce equal-time commutators. With the convention used in this volume,

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O],
$$

the nonanomalous local Ward identity is

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal X\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1(x_1)\cdots
\delta_a\mathcal O_k(x_k)\cdots
\mathcal O_n(x_n)\rangle,
$$

up to the usual local refinements when the current collides with composite operators, other currents, boundaries, defects, or anomalous insertions.

The finite version is even simpler: a charge surface can be deformed freely until it crosses a charged insertion. At the crossing, the operator transforms.

<figure class="doc-figure" style="--figure-width: 40rem;">

![A time-ordered correlator with charge surfaces moved through operator insertions, showing that a contact term appears when the charge surface crosses a charged operator.](/figures/symmetry-anomalies-topology/operator-ward-charge-surface.svg)

<figcaption>

In operator language, a Ward identity says that a charge surface is topological away from insertions. Moving $Q_a(\Sigma)$ through the time-ordered product changes nothing until the surface crosses a charged operator. The crossing gives the equal-time commutator $[Q_a,\mathcal O_k]=-i\delta_a\mathcal O_k$.

</figcaption>
</figure>

## Prerequisites

Read [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/) and [Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/) first. The only new ingredient here is the operator-level mechanism behind the contact terms.

We use the mostly-minus Lorentzian conventions of the volume, and we use

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

with

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+\alpha^a\delta_a\mathcal O+O(\alpha^2).
$$

Therefore

$$
\delta_a\mathcal O=i[Q_a,\mathcal O],
\qquad
[Q_a,\mathcal O]=-i\delta_a\mathcal O.
$$

This page treats bosonic internal symmetries. Spacetime symmetries, supersymmetry, gauge constraints, and BRST identities follow the same broad logic but carry extra index, derivative, or graded-sign structure.

## Core idea

A Ward identity is a conservation law with insertions.

Classically, Noether's theorem says that a continuous symmetry gives a current satisfying

$$
\partial_\mu j_a^\mu=0
$$

on equations of motion. Quantum mechanically, the conserved charge

$$
Q_a(\Sigma)=\int_\Sigma d\Sigma_\mu\,j_a^\mu
$$

acts on operators. If a charge surface surrounds no insertion, it can be deformed away. If it crosses a charged insertion, it acts on that insertion.

So the operator Ward identity has two pieces:

$$
\text{surface independence away from insertions}
\quad + \quad
\text{charge action when crossing insertions}.
$$

The first piece gives separated-point conservation. The second piece gives contact terms.

This is why the Ward identity is more precise than the sentence “the current is conserved.” It says exactly how current conservation fails as a distribution at points where charged operators sit.

## Setup and conventions

Let

$$
G_a^\mu(x;x_1,\ldots,x_n)
=
\langle T\,j_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle.
$$

We assume first that the symmetry is exact and nonanomalous, that the vacuum is invariant, and that boundary flux vanishes. In symbols,

$$
\partial_\mu j_a^\mu=0,
\qquad
Q_a|\Omega\rangle=0,
\qquad
\langle\Omega|Q_a=0.
$$

The current is an operator-valued distribution, so equations involving products such as $j_a^\mu(x)\mathcal O(y)$ are distributional statements. The equality is tested by smearing $x$ and $y$ or by integrating over regions that avoid coincident singularities.

:::note[Convention-sensitive source note]
Some books define the infinitesimal transformation by $\delta\mathcal O=-i[Q,\mathcal O]$, or use $U\mathcal O U^{-1}$ instead of $U^\dagger\mathcal O U$. This page uses $\delta\mathcal O=i[Q,\mathcal O]$. The sign in the contact term follows from that choice.
:::

## Time ordering produces equal-time commutators

For two bosonic Heisenberg operators,

$$
T\{A(x)B(y)\}
=\theta(x^0-y^0)A(x)B(y)
+\theta(y^0-x^0)B(y)A(x).
$$

Differentiating with respect to $x^0$ gives

$$
\partial_{x^0}T\{A(x)B(y)\}
=T\{\partial_{x^0}A(x)B(y)\}
+\delta(x^0-y^0)[A(x),B(y)].
$$

Apply this to $A=j_a^0$ and $B=\mathcal O$. Then

$$
\partial_\mu^x T\{j_a^\mu(x)\mathcal O(y)\}
=T\{(\partial_\mu j_a^\mu)(x)\mathcal O(y)\}
+\delta(x^0-y^0)[j_a^0(x),\mathcal O(y)].
$$

The first term vanishes at separated points for an exact current. The second term is the equal-time commutator.

The charge-generator statement is

$$
\int d^{d-1}\mathbf x\,[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=[Q_a,\mathcal O(t,\mathbf y)]
=-i\delta_a\mathcal O(t,\mathbf y).
$$

Thus the local current-density commutator has the minimal form

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y)+\cdots,
$$

where the ellipsis denotes derivative contact terms that integrate to boundary terms or encode extra local data.

Ignoring those refinements for the moment,

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle.
$$

That is the one-insertion Ward identity.

## Many insertions

For

$$
\mathcal X=
\mathcal O_1(x_1)\cdots\mathcal O_n(x_n),
$$

the derivative of time ordering produces one equal-time commutator for each insertion:

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal X\rangle
=
\sum_{k=1}^n\delta(x^0-x_k^0)
\langle T\,\mathcal O_1\cdots
[j_a^0(x),\mathcal O_k(x_k)]\cdots
\mathcal O_n\rangle.
$$

Using the local commutator gives

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal X\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1\cdots
\delta_a\mathcal O_k\cdots
\mathcal O_n\rangle.
$$

This is the local operator Ward identity.

When several operators have the same time coordinate, the formula should be understood after smearing, point splitting, or specifying an ordering prescription. If some insertions are fermionic, the time-ordering operation includes the usual signs from permuting fermions. For ordinary bosonic internal symmetries the charge itself is even, but the operator product still knows about fermion ordering.

## Integrated form and charge surfaces

Integrate the local identity over a spacetime region $R$ whose boundary avoids all insertions. Gauss' theorem gives

$$
\int_{\partial R}d\Sigma_\mu\,
\langle T\,j_a^\mu(x)\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

This is the charge-surface version of the Ward identity.

Take $R$ to be the slab between two times $t_-$ and $t_+$, and assume no spatial side flux. Then

$$
\langle T\,Q_a(t_+)\mathcal X\rangle
-
\langle T\,Q_a(t_-)\mathcal X\rangle
=-i\sum_{t_-<x_k^0<t_+}
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

This equation is the finite version of the delta functions. As $t_+$ and $t_-$ move, the charge surface crosses insertions. Each crossing contributes the commutator $[Q_a,\mathcal O_k]$.

## Global Ward identities

Suppose the vacuum is invariant:

$$
Q_a|\Omega\rangle=0,
\qquad
\langle\Omega|Q_a=0,
$$

and suppose the current surface can be pushed to infinity with no boundary contribution. Taking $R$ to contain all insertions gives

$$
\sum_{k=1}^n
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle=0.
$$

This is the global Ward identity.

For a $U(1)$ symmetry, if

$$
[Q,\mathcal O_{q_k}]=q_k\mathcal O_{q_k},
$$

then

$$
\delta\mathcal O_{q_k}=iq_k\mathcal O_{q_k}.
$$

The global Ward identity becomes

$$
\left(\sum_{k=1}^nq_k\right)
\langle T\,\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle=0.
$$

Thus a charge-invariant vacuum permits only charge-neutral correlators, unless the assumptions fail. Spontaneous symmetry breaking, boundary charge, non-normalizable charge operators, finite density, or charged external states can all modify this conclusion.

## Example: complex scalar U(1) current

For the complex scalar current in this volume's convention,

$$
j^\mu=i\phi\partial^\mu\phi^\dagger-i\phi^\dagger\partial^\mu\phi,
$$

the charge acts as

$$
\delta\phi=i[Q,\phi]=i\phi,
\qquad
\delta\phi^\dagger=i[Q,\phi^\dagger]=-i\phi^\dagger.
$$

Equivalently,

$$
[Q,\phi]=\phi,
\qquad
[Q,\phi^\dagger]=-\phi^\dagger.
$$

The local equal-time commutators are

$$
[j^0(t,\mathbf x),\phi(t,\mathbf y)]
=\delta^{(d-1)}(\mathbf x-\mathbf y)\phi(t,\mathbf y),
$$

and

$$
[j^0(t,\mathbf x),\phi^\dagger(t,\mathbf y)]
=-\delta^{(d-1)}(\mathbf x-\mathbf y)\phi^\dagger(t,\mathbf y),
$$

with the usual caveat that equal-time products of composite operators are distributions.

For

$$
\mathcal X=\phi(y)\phi^\dagger(z),
$$

the Ward identity gives

$$
\partial_\mu^x\langle T\,j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=
\left[\delta^{(d)}(x-y)-\delta^{(d)}(x-z)\right]
\langle T\,\phi(y)\phi^\dagger(z)\rangle.
$$

The first contact term says the current sees charge $+1$ at $y$; the second says it sees charge $-1$ at $z$.

For $\mathcal X=\phi(y)\phi(z)$, integrating the Ward identity over $x$ gives

$$
2\langle T\,\phi(y)\phi(z)\rangle=0,
$$

so the correlator vanishes in a charge-invariant vacuum.

## Example: Ward–Takahashi identities in QED

The same operator logic gives the usual Ward–Takahashi identities. For a vector current coupled to a Dirac field, the schematic position-space identity is

$$
\partial_\mu^x\langle T\,j^\mu(x)\psi(y)\bar\psi(z)\rangle
=\delta^{(d)}(x-y)\langle T\,\psi(y)\bar\psi(z)\rangle
-\delta^{(d)}(x-z)\langle T\,\psi(y)\bar\psi(z)\rangle,
$$

up to charge normalization and sign conventions for $\bar\psi$.

Fourier transforming gives a relation between the current vertex and the inverse fermion propagator. In a common convention,

$$
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p).
$$

This identity is the perturbative descendant of the same contact-term Ward identity. It is why current conservation constrains vertex corrections and renormalization constants. The gauge-theory pages refine this statement using gauge fixing and BRST symmetry.

:::note[Why this is only a preview]
A global current Ward identity is not yet the full gauge-theory proof. In a dynamical gauge theory, gauge redundancy, gauge fixing, ghosts, longitudinal modes, and BRST symmetry add structure. The full Slavnov–Taylor identities belong to the Gauge Redundancy and BRST chapter and the Gauge Theories volume.
:::

## Spacetime symmetries

For spacetime symmetries, the same operator mechanism applies, but $\delta\mathcal O$ is richer because the transformation moves the insertion point and can rotate indices.

For translations, the current is the stress tensor $T^{\mu\nu}$. A scalar local operator transforms as

$$
\delta_\epsilon\mathcal O(x)=\epsilon^\nu\partial_\nu\mathcal O(x).
$$

The corresponding Ward identity has the schematic form

$$
\partial_\mu^x\langle T\,T^{\mu\nu}(x)\mathcal X\rangle
=-i\sum_k\delta^{(d)}(x-x_k)\partial_{x_k}^\nu
\langle T\,\mathcal X\rangle
+\text{spin and contact terms}.
$$

For rotations, Lorentz transformations, scale transformations, and conformal transformations, the variation also includes spin, scaling dimension, and possible improvement terms. These are not exceptions to the Ward-identity logic; they are more elaborate versions of $\delta\mathcal O$.

## Contact terms beyond the minimal one

The minimal charge-density commutator was

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y).
$$

In a renormalized QFT, the most general local equal-time commutator can include derivatives of delta functions:

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y)
+\partial_i\left[\delta^{(d-1)}(\mathbf x-\mathbf y)\mathcal Y^i(t,\mathbf y)\right]+
\cdots.
$$

Such terms can arise from improvements, derivative operators, spin terms, anomalous commutators, or background-field counterterms. Integrated over all space they may vanish under good boundary conditions, but locally they matter.

This distinction is crucial:

$$
\text{the charge action may be universal, while current-density contact terms are scheme-dependent.}
$$

The later Contact Terms page will make this systematic.

## Current algebra and Schwinger terms

If the inserted operator is itself a current, the commutator gives current algebra. Schematically,

$$
[j_a^0(t,\mathbf x),j_b^\nu(t,\mathbf y)]
=i f_{ab}{}^c\delta^{(d-1)}(\mathbf x-\mathbf y)j_c^\nu(t,\mathbf y)
+\text{Schwinger terms}.
$$

Schwinger terms are local derivative contact terms. They are especially important in two-dimensional current algebra, anomalous theories, and stress-tensor algebras. They can encode central extensions, levels, and anomaly coefficients.

The moral is simple: contact terms are not dirt. They are part of the algebra.

## Explicit breaking and anomalies

If the current is not conserved as an operator equation, the Ward identity has a bulk term. For explicit breaking,

$$
\partial_\mu j_a^\mu=\mathcal B_a,
$$

so

$$
\partial_\mu\langle T\,j_a^\mu(x)\mathcal X\rangle
=\langle T\,\mathcal B_a(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

For an anomaly, the form is similar:

$$
\partial_\mu\langle T\,j_a^\mu(x)\mathcal X\rangle
=\langle T\,\mathcal A_a(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

The difference is conceptual. $\mathcal B_a$ is an explicit-breaking operator visible in the action. $\mathcal A_a$ is a quantum obstruction: the classical symmetry exists, but the quantum regulator or measure cannot preserve it together with the other required structures.

The operator derivation can detect an anomaly as a failure of current conservation or as an anomalous Schwinger term in current algebra. The path-integral derivation on the next page shows the complementary viewpoint: an anomaly appears as a Jacobian of the measure.

## Boundaries, states, and infrared caveats

The operator derivation assumes that charges exist as honest operators on the Hilbert space. This can fail or require refinement.

In a theory with a boundary, charge may flow into boundary degrees of freedom:

$$
\frac{dQ_{\mathrm{bulk}}}{dt}
=-\int_{\partial\Sigma}dS_i\,j^i.
$$

Then the Ward identity for bulk operators alone is incomplete. One must include boundary operators, edge modes, or boundary conditions.

In a theory with massless particles, the spatial integral defining $Q$ can have infrared subtleties. Soft charges, asymptotic symmetries, and spontaneous symmetry breaking often require surface charges rather than naive volume charges.

In a spontaneously broken continuous symmetry, the vacuum is not invariant under the charge, and the global Ward identity is modified. This modification is the operator seed of Goldstone's theorem.

## Common pitfalls

**Forgetting that $\partial_\mu$ differentiates time ordering.** The contact terms in the Ward identity come exactly from differentiating the step functions hidden in $T$.

**Writing the commutator with the wrong sign.** In this volume, $\delta_a\mathcal O=i[Q_a,\mathcal O]$, so $[Q_a,\mathcal O]=-i\delta_a\mathcal O$.

**Assuming charge-density commutators are ordinary functions.** They are distributions. Equal-time products of local operators need renormalization and can contain derivative contact terms.

**Using the global Ward identity when the vacuum is not invariant.** Spontaneous symmetry breaking, charged states, finite density, and boundary conditions can invalidate the step $Q|\Omega\rangle=0$.

**Confusing global-symmetry Ward identities with gauge redundancy.** Global charges act on physical operators. Gauge transformations are redundancies; after gauge fixing, their identities are BRST or Slavnov–Taylor identities.

**Ignoring anomaly terms.** A classical current can look conserved until the regulator is specified. Quantum anomalies add bulk terms to the Ward identity.

## Relations to other pages

[Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/) stated the local contact-term identity. This page derives it from time ordering and equal-time commutators.

[Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/) explains why the spatial integral of $j_a^0$ generates the symmetry. This page uses that charge action inside time-ordered correlators.

[Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) derives the same identity from a change of integration variables and explains where the measure, regulator, and anomalies enter.

[Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) will refine the local distributional terms suppressed here.

[Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/) studies commutators of currents with currents, including central extensions and Schwinger terms.

[Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) gives the finite topological-operator version of the same crossing rule.

## Research status

The operator derivation of Ward identities is established graduate-level QFT. It is the backbone of current algebra, soft theorems, Goldstone's theorem, gauge-theory Ward–Takahashi identities, and many selection rules.

The research-level subtleties are local and global rather than slogan-level. One must specify the renormalized current representative, the domain of the charge operator, boundary conditions, infrared dressing, gauge constraints, and contact-term scheme. In modern language, the cleanest object is often not the current density alone but the topological charge operator, the background-field generating functional, or the defect implementing the symmetry.

## Exercises

### Exercise 1: Differentiate a two-operator time-ordered product

For bosonic operators $A(x)$ and $B(y)$, show that

$$
\partial_{x^0}T\{A(x)B(y)\}
=T\{\partial_{x^0}A(x)B(y)\}
+\delta(x^0-y^0)[A(x),B(y)].
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
T\{A(x)B(y)\}
=\theta(x^0-y^0)A(x)B(y)+\theta(y^0-x^0)B(y)A(x).
$$

Differentiating gives two types of terms. The derivatives of the operators give

$$
\theta(x^0-y^0)\partial_{x^0}A(x)B(y)
+\theta(y^0-x^0)B(y)\partial_{x^0}A(x)
=T\{\partial_{x^0}A(x)B(y)\}.
$$

The derivatives of the step functions give

$$
\delta(x^0-y^0)A(x)B(y)-\delta(y^0-x^0)B(y)A(x).
$$

Since $\delta(y^0-x^0)=\delta(x^0-y^0)$, this equals

$$
\delta(x^0-y^0)[A(x),B(y)].
$$

Combining the two terms proves the identity.

</details>

### Exercise 2: Derive the one-insertion Ward identity

Assume

$$
\partial_\mu j_a^\mu=0
$$

away from insertions and

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y).
$$

Derive

$$
\partial_\mu\langle T\,j_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Using Exercise 1 with $A=j_a^0$ and $B=\mathcal O$, and adding the spatial derivative, gives

$$
\partial_\mu^x T\{j_a^\mu(x)\mathcal O(y)\}
=T\{(\partial_\mu j_a^\mu)(x)\mathcal O(y)\}
+\delta(x^0-y^0)[j_a^0(x),\mathcal O(y)].
$$

The separated-point conservation law sets the first term to zero. Insert the equal-time commutator:

$$
\delta(x^0-y^0)[j_a^0(x),\mathcal O(y)]
=-i\delta(x^0-y^0)\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(y).
$$

The product of delta functions is $\delta^{(d)}(x-y)$, so after taking the vacuum expectation value,

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle.
$$

</details>

### Exercise 3: Global Ward identity from the local one

Assume the vacuum is invariant and boundary terms vanish at infinity. Starting from the local Ward identity, show that

$$
\sum_{k=1}^n
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Integrate the local Ward identity over a region $R$ enclosing all insertions:

$$
\int_R d^dx\,\partial_\mu\langle T\,j_a^\mu(x)\mathcal X\rangle
=-i\sum_k\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

The left-hand side becomes a boundary integral:

$$
\int_{\partial R}d\Sigma_\mu\,\langle T\,j_a^\mu\mathcal X\rangle.
$$

If the boundary can be pushed to infinity and gives no contribution, the left-hand side is zero. Therefore

$$
0=-i\sum_k\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle,
$$

which implies the stated identity.

</details>

### Exercise 4: Charge neutrality

Let $[Q,\mathcal O_{q_k}]=q_k\mathcal O_{q_k}$. Show that the global Ward identity implies

$$
\left(\sum_k q_k\right)
\langle T\,\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

The convention $\delta\mathcal O=i[Q,\mathcal O]$ gives

$$
\delta\mathcal O_{q_k}=iq_k\mathcal O_{q_k}.
$$

Substitute this into the global Ward identity:

$$
0=\sum_k
\langle T\,\mathcal O_{q_1}\cdots iq_k\mathcal O_{q_k}\cdots\mathcal O_{q_n}\rangle.
$$

The factors $q_k$ are numbers, so

$$
0=i\left(\sum_k q_k\right)
\langle T\,\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

Dividing by $i$ gives the result.

</details>

### Exercise 5: Derivative contact terms and integrated charges

Suppose the equal-time commutator contains an improvement term,

$$
[j^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta\mathcal O(t,\mathbf y)
+\partial_i\left[\delta^{(d-1)}(\mathbf x-\mathbf y)Y^i(t,\mathbf y)\right].
$$

Show that the derivative term does not contribute to the full-space charge commutator if the surface term vanishes.

<details><summary><strong>Solution</strong></summary>

Integrate the commutator over $\mathbf x$:

$$
[Q,\mathcal O(t,\mathbf y)]
=\int d^{d-1}\mathbf x\,[j^0(t,\mathbf x),\mathcal O(t,\mathbf y)].
$$

The first term gives

$$
-i\int d^{d-1}\mathbf x\,\delta^{(d-1)}(\mathbf x-\mathbf y)\delta\mathcal O(t,\mathbf y)
=-i\delta\mathcal O(t,\mathbf y).
$$

The derivative term gives

$$
\int d^{d-1}\mathbf x\,\partial_i\left[\delta^{(d-1)}(\mathbf x-\mathbf y)Y^i(t,\mathbf y)\right].
$$

By Gauss' theorem this is a surface integral at spatial infinity. If the surface term vanishes, it contributes zero. Thus

$$
[Q,\mathcal O]=-i\delta\mathcal O.
$$

The local current-density contact term can therefore matter locally even when it does not change the integrated charge action.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on symmetries and conservation laws, current algebra, and Ward identities.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” “Dilatations,” and “Renormalization and Symmetry.” Classic operator uses of Ward identities.
- Mark Srednicki, *Quantum Field Theory*, §22 and §§67–68. Compact treatment of currents and Ward identities, including QED applications.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the discussion of symmetries, generators, and S-matrix constraints.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on path integrals, Schwinger–Dyson equations, Ward–Takahashi identities, and anomalies.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for the distributional and renormalized-composite-operator viewpoint.

## Version history

- **2026-06-17:** Initial polished page deriving Ward identities from time ordering and equal-time commutators.
