---
title: "Charges Acting on Local Operators"
description: "Explains how conserved charges act on local operators through equal-time commutators, charge surfaces, Ward-identity contact terms, and operator multiplets."
sidebar:
  label: "Charges on Local Operators"
  order: 9
level: Graduate
status: "Polished draft"
source: "Coleman lectures on symmetries and current algebra; Srednicki §22; Weinberg Vol. I on symmetry generators; standard Ward-identity and radial-quantization conventions."
topics:
  - conserved charges
  - local operators
  - Ward identities
  - operator multiplets
  - charge surfaces
  - representation theory
canonicalTopics:
  - charge-action-on-local-operator
  - local-operator-multiplet
  - charge-surface-action
  - symmetry-action-on-ope
researchStatus:
  established:
    - "For an exact ordinary continuous symmetry, the conserved charge acts on local operators by commutator, and the same action appears as the leading contact term in the Ward identity."
  active:
    - "In theories with gauge constraints, boundaries, defects, generalized symmetries, or anomalous symmetries, identifying which charge surfaces act on which operators is a central organizing question."
---

## Summary

A conserved charge is not just a number that labels states. It is an operator that acts on other operators.

For an internal continuous symmetry with current $j_a^\mu$, the charge on a time slice is

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

With the convention used throughout this chapter,

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

Thus a local operator multiplet $\mathcal O_i$ transforms by the equal-time commutator

$$
[Q_a,\mathcal O_i(x)]=-i\,\delta_a\mathcal O_i(x).
$$

Equivalently, the current Ward identity says that when the current insertion collides with $\mathcal O_i(x)$, it produces a contact term proportional to $\delta_a\mathcal O_i(x)$. In Euclidean or radial language, the same statement says that a small charge surface surrounding the insertion acts on the operator placed inside it.

<figure class="doc-figure" style="--figure-width: 43rem;">

![A charge surface surrounding a local operator. Deforming the surface changes nothing unless it crosses the operator insertion, where it produces the infinitesimal symmetry action.](/figures/symmetry-anomalies-topology/charge-surface-operator-action.svg)

<figcaption>

A conserved charge can be represented by a surface integral of the current. The surface can be deformed freely until it crosses an insertion. Crossing $\mathcal O_i(y)$ inserts the local action $\delta_a\mathcal O_i(y)$, which is the geometric version of the Ward-identity contact term.

</figcaption>
</figure>

This page is the bridge between three ways of saying the same thing:

$$
\text{commutator with }Q_a
\quad\Longleftrightarrow\quad
\text{current contact term}
\quad\Longleftrightarrow\quad
\text{charge surface crossing an operator}.
$$

## Prerequisites

Read [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/), [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/), and [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/) first. From the previous chapter, the most relevant pages are [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), and [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/).

The page assumes ordinary internal continuous symmetries unless stated otherwise. Spacetime symmetries are similar but require the current to act also on the insertion point, so the formulas acquire orbital terms.

## Core idea

The action of a charge on a local operator is the infinitesimal version of the symmetry action.

Suppose a local operator multiplet transforms as

$$
U(g)^\dagger\mathcal O_i(x)U(g)=R(g)_i{}^j\mathcal O_j(x).
$$

Near the identity, write $g=e^{\alpha^aT_a}$. The infinitesimal transformation is

$$
\delta_a\mathcal O_i(x)=\left.\frac{\partial}{\partial\alpha^a}
\left(R(e^{\alpha^bT_b})_i{}^j\mathcal O_j(x)\right)\right|_{\alpha=0}.
$$

The quantum generator statement is

$$
\delta_a\mathcal O_i(x)=i[Q_a,\mathcal O_i(x)].
$$

This formula is easy to memorize and easy to misuse. It is an equality of local operators, defined after regulating products and contact terms. The commutator is really an equal-time or radially ordered statement. In correlation functions, it becomes the contact term in the divergence of a current insertion.

The useful picture is:

$$
Q_a\text{ measures what lies inside a surface, and crossing an insertion acts on it.}
$$

That picture survives far beyond elementary Noether calculations. It becomes the language of higher-form symmetries, topological defects, non-invertible symmetries, and anomaly inflow. Ordinary charges are the first, simplest case.

## Setup and conventions

We use Hermitian charges and the pullback action on operators:

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\mathcal O\mapsto U(\alpha)^\dagger\mathcal O U(\alpha).
$$

Expanding to first order gives

$$
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+i\alpha^a[Q_a,\mathcal O]+O(\alpha^2),
$$

so

$$
\delta_a\mathcal O=i[Q_a,\mathcal O],
\qquad
[Q_a,\mathcal O]=-i\delta_a\mathcal O.
$$

For a $U(1)$ eigenoperator with charge $q$,

$$
\mathcal O_q\mapsto e^{i\alpha q}\mathcal O_q,
\qquad
\delta\mathcal O_q=iq\mathcal O_q,
$$

and therefore

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

Both formulas are consistent because $\delta\mathcal O_q=iq\mathcal O_q$.

For a nonabelian multiplet, it is safest to write

$$
[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j,
$$

where the matrices $\tau_a$ encode the chosen index placement and pullback convention. The infinitesimal variation is then

$$
\delta_a\mathcal O_i=i(\tau_a)_i{}^j\mathcal O_j.
$$

:::note[Convention-sensitive source note]
Some books define the active transformation of fields, others define the pullback action on operators. Some use Hermitian representation matrices, others use anti-Hermitian Lie-algebra generators. The invariant statement is the finite conjugation law $U(g)^\dagger\mathcal O U(g)=R(g)\mathcal O$. The signs in infinitesimal formulas follow from that choice.
:::

## From equal-time commutators to Ward identities

Let $\mathcal O(y)$ be a bosonic local operator. The operator Ward identity comes from differentiating a time-ordered product:

$$
\partial_\mu^x T\,j_a^\mu(x)\mathcal O(y)
=T\,\partial_\mu j_a^\mu(x)\mathcal O(y)
+\delta(x^0-y^0)[j_a^0(x),\mathcal O(y)].
$$

For an exact symmetry, $\partial_\mu j_a^\mu=0$ at separated points. The remaining term is the equal-time commutator. Locality implies the leading singular part has the form

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y)
+\text{derivative contact terms}.
$$

Multiplying by $\delta(x^0-y^0)$ gives

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal O(y)\rangle
=-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle
+\cdots.
$$

For many insertions,

$$
\partial_\mu^x\left\langle T\,j_a^\mu(x)\prod_{k=1}^n\mathcal O_k(x_k)\right\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\left\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\right\rangle
+\cdots.
$$

The dots stand for additional local terms from composite-operator renormalization, current-current collisions, background sources, anomalies, boundaries, or defects. The leading term is fixed by the charge action.

## Charge surfaces

The same statement can be written geometrically. Let $\Sigma$ be a codimension-one surface with future-pointing normal element $d\Sigma_\mu$. Define the surface charge

$$
Q_a[\Sigma]=\int_\Sigma d\Sigma_\mu\,j_a^\mu.
$$

If $\partial_\mu j_a^\mu=0$ and no operator insertion lies between two homologous surfaces $\Sigma_1$ and $\Sigma_2$, then

$$
Q_a[\Sigma_1]=Q_a[\Sigma_2]
$$

inside correlation functions. This is just Stokes' theorem:

$$
Q_a[\Sigma_2]-Q_a[\Sigma_1]
=\int_M d^dx\,\partial_\mu j_a^\mu,
$$

where $M$ is the region between the surfaces.

But if the deformation crosses a local operator insertion at $y$, the Ward identity says that the difference is not zero. It is the action of the charge on that operator:

$$
Q_a[\Sigma_{\text{after}}]\,\mathcal O_i(y)
-Q_a[\Sigma_{\text{before}}]\,\mathcal O_i(y)
\sim -i\delta_a\mathcal O_i(y),
$$

with the precise factor depending on whether the formula is written as a commutator, a radially ordered product, or an integrated Ward identity.

A small sphere $S_y^{d-1}$ surrounding $y$ isolates this local action:

$$
\int_{S_y^{d-1}} d\Sigma_\mu\,
\langle j_a^\mu(x)\mathcal O_i(y)\mathcal X\rangle
\propto
\langle \delta_a\mathcal O_i(y)\mathcal X\rangle.
$$

In two-dimensional CFT this becomes the familiar contour statement: the zero mode of a current acting on an operator is obtained by integrating the current around the operator. In higher-dimensional QFT, the contour is replaced by a surrounding sphere or charge surface.

:::note[Why the surface picture matters]
The surface picture is overkill for an elementary $U(1)$ scalar field, but it is the right mental model for modern symmetry. Higher-form symmetries act by topological surfaces on extended operators. Non-invertible symmetries act by topological defects rather than group-like charges. Ordinary charge surfaces are the baby version.
:::

## Charged eigenoperators and multiplets

For an abelian symmetry, one can often choose local operators with definite charge:

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

Then a finite transformation gives

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{i\alpha q}\mathcal O_q.
$$

The charge is additive under products. If $\mathcal O_q$ and $\mathcal P_r$ are bosonic operators with charges $q$ and $r$, then

$$
[Q,\mathcal O_q\mathcal P_r]
=[Q,\mathcal O_q]\mathcal P_r+
\mathcal O_q[Q,\mathcal P_r]
=(q+r)\mathcal O_q\mathcal P_r.
$$

So

$$
q(\mathcal O_q\mathcal P_r)=q+r.
$$

For a nonabelian symmetry, local operators are usually organized into multiplets:

$$
[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j.
$$

A singlet satisfies

$$
[Q_a,\mathcal O]=0
\qquad\text{for all }a.
$$

A vector multiplet, adjoint multiplet, spinor multiplet, or tensor multiplet transforms by mixing components. Individual components are not invariant, but the multiplet as a whole carries a representation.

The physical content is not the matrix $\tau_a$ alone. It is also the statement that the operator is a well-defined local operator of the quantum theory, with a renormalization prescription compatible with the symmetry.

## Charges act as derivations

A symmetry acts on products as an algebra automorphism:

$$
U^\dagger(\mathcal O\mathcal P)U
=(U^\dagger\mathcal O U)(U^\dagger\mathcal P U).
$$

Infinitesimally, the charge commutator obeys the Leibniz rule:

$$
[Q_a,\mathcal O\mathcal P]
=[Q_a,\mathcal O]\mathcal P+
\mathcal O[Q_a,\mathcal P],
$$

up to the usual grading if the symmetry generator or the operators are fermionic. For ordinary bosonic internal symmetries, no extra sign appears.

This derivation property is the operator-algebra version of charge additivity. It explains why composite operators transform in tensor products and why invariant couplings are built by contracting indices with invariant tensors.

For example, for a complex scalar with $U(1)$ charge $+1$,

$$
[Q,\phi]=\phi,
\qquad
[Q,\phi^\dagger]=-\phi^\dagger.
$$

Then

$$
[Q,\phi^\dagger\phi]
=[Q,\phi^\dagger]\phi+\phi^\dagger[Q,\phi]
=-\phi^\dagger\phi+\phi^\dagger\phi=0.
$$

The operator $\phi^\dagger\phi$ is neutral.

## OPE covariance

The operator product expansion must respect the charge action.

Suppose

$$
\mathcal O_i(x)\mathcal P_j(0)
\sim \sum_k C_{ij}{}^k(x)\mathcal R_k(0).
$$

Acting with $Q_a$ on both sides gives

$$
[Q_a,\mathcal O_i(x)]\mathcal P_j(0)
+\mathcal O_i(x)[Q_a,\mathcal P_j(0)]
\sim
\sum_k C_{ij}{}^k(x)[Q_a,\mathcal R_k(0)],
$$

for an internal symmetry whose charge commutes with translations. In representation language, the OPE coefficients are intertwiners. They map the tensor product representation of $\mathcal O_i\otimes\mathcal P_j$ into the representation carried by $\mathcal R_k$.

For an abelian symmetry, this reduces to charge conservation in the OPE:

$$
\mathcal O_q(x)\mathcal P_r(0)
\sim \sum_k C_{qr}{}^k(x)\mathcal R_k(0),
\qquad
\mathcal R_k\text{ can appear only if }q_k=q+r.
$$

This is the local-operator version of a selection rule. Correlators, OPEs, source couplings, and matrix elements all obey the same charge bookkeeping.

## Derivatives and descendants

For an internal symmetry, the charge commutes with spacetime translations:

$$
[Q_a,P_\mu]=0.
$$

Since derivatives of local operators are generated by translations, an internal charge acts on derivatives by differentiating the transformed operator:

$$
[Q_a,\partial_\mu\mathcal O_i]
=\partial_\mu[Q_a,\mathcal O_i].
$$

Thus if $\mathcal O_i$ is in a representation $R$, then $\partial_\mu\mathcal O_i$ is in the same internal representation but with different spacetime quantum numbers.

For spacetime symmetries, this statement is modified. A Lorentz generator acts both on the tensor or spinor indices and on the coordinate dependence. A translation generator acts as a derivative. A scale generator acts with both scaling dimension and position-dependent terms. That is why internal symmetries are the cleanest place to learn the charge-action story first.

## Singlets, invariant deformations, and sources

A deformation of the action by a local operator,

$$
S\mapsto S+\lambda\int d^dx\,\mathcal O(x),
$$

preserves the symmetry only if the integrated insertion is invariant. For an internal symmetry with constant coupling $\lambda$, this usually means

$$
[Q_a,\mathcal O]=0
$$

up to total derivatives.

If $\mathcal O_i$ is not a singlet, one can still couple it to a source $J^i(x)$ that transforms in the dual representation:

$$
\int d^dx\,J^i(x)\mathcal O_i(x).
$$

The combined source-operator term is invariant if

$$
\delta(J^i\mathcal O_i)=0.
$$

This source viewpoint is not a cosmetic detail. Background fields and sources are the cleanest way to organize Ward identities, current contact terms, and anomalies. The next chapter, [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), turns this into a systematic language.

## Gauge charges are different

For a genuine global symmetry, a charge can act nontrivially on local operators. For a gauge redundancy, the story is subtler.

Gauge-invariant local operators commute with small gauge transformations. In a closed system with no boundary, the Gauss-law generator annihilates physical states and acts trivially on gauge-invariant local observables. A gauge-charged elementary field may transform under the gauge redundancy, but it is not by itself a gauge-invariant local observable.

Boundary conditions change this. In gauge theory on a space with boundary or at asymptotic infinity, transformations that do not vanish at the boundary can become physical global symmetries with boundary charges. Such charges may act on charged states, Wilson lines ending at the boundary, or dressed operators.

This is a common source of confusion:

$$
\text{gauge redundancy in the bulk}\neq
\text{physical global symmetry at the boundary}.
$$

The distinction is developed in the Gauge Redundancy and BRST chapter and returns in the soft-theorem preview below.

## When the action fails

The formula

$$
\delta_a\mathcal O=i[Q_a,\mathcal O]
$$

assumes that $Q_a$ is a well-defined conserved charge. There are several ways this can fail or require refinement.

First, the symmetry can be explicitly broken:

$$
\partial_\mu j_a^\mu\neq 0.
$$

Then the surface charge is not topological, and deformations of the charge surface pick up bulk terms.

Second, the symmetry can be anomalous. Classically one may find a current, but the quantum measure or regulator fails to preserve the symmetry. Then the Ward identity contains an anomaly term:

$$
\partial_\mu j_a^\mu=\mathcal A_a.
$$

For a gauge symmetry this is an inconsistency unless canceled. For a global symmetry it is an obstruction to gauging and a source of anomaly matching constraints.

Third, the operator may not be genuine. In gauge theory and in theories with topological order, some objects require attached lines, surfaces, or framing data. The action of a charge surface can then depend on the topology of those attachments.

Fourth, boundaries and defects can carry their own degrees of freedom. A bulk charge surface moved across a boundary may leave behind a boundary charge, anomaly inflow term, or defect operator.

## Common pitfalls

**Pitfall 1: Treating charge as only a label.** A charge labels states and eigenoperators in abelian examples, but the charge operator also acts by commutator. In nonabelian examples, the action mixes components.

**Pitfall 2: Forgetting contact terms.** The local action of a charge on an operator is precisely the contact term in the current Ward identity. If you drop contact terms, the integrated charge action disappears.

**Pitfall 3: Confusing fields with genuine operators.** A gauge-charged field may transform under a gauge redundancy, but it is not a gauge-invariant local observable. A genuine global charge acts on genuine operators or on properly dressed charged objects.

**Pitfall 4: Using a conserved-current formula when the symmetry is anomalous.** If the divergence contains an anomaly, the charge surface is not freely deformable. The failure of deformation invariance is physical.

**Pitfall 5: Ignoring index placement.** The sign and transpose of representation matrices depend on whether the operator has upper or lower indices and whether one writes an active or pullback action. The finite conjugation law is safer than memorized infinitesimal signs.

## Relations to other pages

- [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/) defines $Q_a$ and explains why charge conservation is surface independence.
- [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) explains the distributional terms that encode charge action in correlators.
- [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/) extends the charge action from operators to currents themselves.
- [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) uses charge action to constrain correlators, OPEs, and matrix elements.
- [Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) gives the finite, topological-defect version of this infinitesimal charge-surface action.
- [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) upgrades source transformations into a systematic formalism.

## Research status

For ordinary continuous internal symmetries in standard QFT, the action of charges on local operators is settled textbook material. What remains subtle is not the basic commutator, but its domain of validity and its modern refinements.

In strongly coupled theories, one may know the operator algebra and charge action without a Lagrangian. In gauge theories, charged objects may require dressing or endpoints on boundaries. In theories with generalized symmetries, charge operators are higher-codimension topological operators acting on extended operators. In non-invertible symmetry, the acting object is not a group element but a defect with fusion rules. In anomalous theories, the obstruction to consistently defining or gauging the charge action is itself physical data.

So the elementary equation $\delta\mathcal O=i[Q,\mathcal O]$ is not obsolete. It is the seed from which much of modern symmetry language grows.

## Exercises

### Exercise 1: U(1) charge of a composite operator

Let $[Q,\phi]=\phi$ and $[Q,\phi^\dagger]=-\phi^\dagger$. Compute the charge of

$$
\mathcal O_{m,n}=\phi^m(\phi^\dagger)^n.
$$

<details><summary><strong>Solution</strong></summary>

Use the Leibniz rule repeatedly:

$$
[Q,\phi^m]=m\phi^m,
\qquad
[Q,(\phi^\dagger)^n]=-n(\phi^\dagger)^n.
$$

Therefore

$$
[Q,\phi^m(\phi^\dagger)^n]
=(m-n)\phi^m(\phi^\dagger)^n.
$$

So the charge is

$$
q=m-n.
$$

</details>

### Exercise 2: Contact term from a commutator

Assume

$$
[j^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta\mathcal O(t,\mathbf y).
$$

Show that differentiating the time-ordered product $Tj^\mu(x)\mathcal O(y)$ gives the spacetime contact term

$$
-i\delta^{(d)}(x-y)\delta\mathcal O(y).
$$

<details><summary><strong>Solution</strong></summary>

The derivative of the time-ordering step function gives

$$
\partial_\mu^x Tj^\mu(x)\mathcal O(y)
=T\partial_\mu j^\mu(x)\mathcal O(y)
+\delta(x^0-y^0)[j^0(x),\mathcal O(y)].
$$

For a conserved current, the first term vanishes at separated points. Substitute the equal-time commutator:

$$
\delta(x^0-y^0)[j^0(x),\mathcal O(y)]
=-i\delta(x^0-y^0)\delta^{(d-1)}(\mathbf x-\mathbf y)\delta\mathcal O(y).
$$

Since

$$
\delta(x^0-y^0)\delta^{(d-1)}(\mathbf x-\mathbf y)=\delta^{(d)}(x-y),
$$

we obtain

$$
-i\delta^{(d)}(x-y)\delta\mathcal O(y).
$$

</details>

### Exercise 3: OPE charge conservation

Suppose $\mathcal O_q$ and $\mathcal P_r$ are $U(1)$ eigenoperators. Their OPE contains a term

$$
\mathcal O_q(x)\mathcal P_r(0)\sim C(x)\mathcal R_s(0).
$$

Use charge conservation to show that $s=q+r$ if $C(x)\neq 0$.

<details><summary><strong>Solution</strong></summary>

Act with $Q$ on the left:

$$
[Q,\mathcal O_q(x)\mathcal P_r(0)]
=(q+r)\mathcal O_q(x)\mathcal P_r(0).
$$

Act with $Q$ on the displayed OPE term on the right:

$$
[Q,C(x)\mathcal R_s(0)]=sC(x)\mathcal R_s(0),
$$

because $C(x)$ is an ordinary coefficient function. Equality requires

$$
s=q+r
$$

for any nonzero coefficient.

</details>

### Exercise 4: Internal charges and derivatives

Assume $[Q_a,P_\mu]=0$ and $[Q_a,\mathcal O_i]=(\tau_a)_i{}^j\mathcal O_j$. Show that

$$
[Q_a,\partial_\mu\mathcal O_i]=(\tau_a)_i{}^j\partial_\mu\mathcal O_j.
$$

<details><summary><strong>Solution</strong></summary>

Translations generate derivatives, so an internal charge commuting with $P_\mu$ commutes with the derivative operation. Therefore

$$
[Q_a,\partial_\mu\mathcal O_i]
=\partial_\mu[Q_a,\mathcal O_i].
$$

Substitute the representation action:

$$
\partial_\mu[Q_a,\mathcal O_i]
=\partial_\mu\left((\tau_a)_i{}^j\mathcal O_j\right).
$$

The representation matrix is constant, so

$$
[Q_a,\partial_\mu\mathcal O_i]
=(\tau_a)_i{}^j\partial_\mu\mathcal O_j.
$$

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on spacetime and internal symmetries.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” for charge commutators acting on currents and operators.
- Mark Srednicki, *Quantum Field Theory*, §22 on continuous symmetries and conserved currents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, Ch. 2 on symmetries, Wigner's theorem, and quantum generators.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 3 and 14 for Noether's theorem and Ward identities.
- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*, for the contour-integral version of current actions in two-dimensional CFT.

## Version history

- **2026-06-17:** Initial polished page explaining charge actions on local operators, charge surfaces, contact terms, OPE covariance, source couplings, and gauge-theory caveats.
