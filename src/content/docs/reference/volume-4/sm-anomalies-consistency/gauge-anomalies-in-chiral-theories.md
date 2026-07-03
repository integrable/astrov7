---
title: "Gauge Anomalies in Chiral Theories"
description: "Explains perturbative gauge anomalies in four-dimensional chiral gauge theories, why gauge-current anomalies are consistency failures, and how anomaly coefficients are computed from left-handed Weyl representations."
sidebar:
  label: "Gauge Anomalies in Chiral Theories"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II anomaly material; Coleman symmetry and Ward-identity lectures; Burgess Ch. 9."
topics:
  - gauge anomalies
  - chiral gauge theory
  - triangle diagrams
  - anomaly cancellation
  - BRST consistency
  - Standard Model consistency
canonicalTopics:
  - gauge-anomalies
  - chiral-gauge-theories
  - triangle-anomalies
  - anomaly-cancellation-conditions
  - brst-consistency
researchStatus:
  established:
    - "Perturbative gauge anomalies in four-dimensional chiral gauge theories are controlled by representation-theoretic cubic and mixed anomaly coefficients; dynamical gauge anomalies must cancel."
  active:
    - "Modern anomaly theory packages local, global, mixed, and higher-form anomalies using anomaly polynomials, inflow, cobordism, and generalized symmetries; this page only develops the four-dimensional perturbative gauge-anomaly entry point."
---

## Summary

A **gauge anomaly** is a quantum failure of a classical gauge symmetry. In an ordinary global symmetry this can be a real physical effect. In a gauge symmetry it is a consistency problem, because gauge symmetry is the redundancy that removes unphysical polarizations and makes Ward identities, BRST cohomology, and unitarity fit together.

The dangerous case is a **chiral gauge theory**: left- and right-handed fermions transform differently under the gauge group. A single left-handed Weyl fermion in a complex representation can produce a triangle anomaly. The anomaly is not measured by the dimension of the representation alone. It is measured by a symmetric group-theory trace,

$$
\mathcal A^{abc}_R
=
\operatorname{tr}_R\!\left(T^a\{T^b,T^c\}\right),
$$

with appropriate modifications for Abelian and mixed anomalies. A four-dimensional chiral gauge theory is perturbatively consistent only if the sum of these coefficients over all left-handed Weyl fermions vanishes for every gauged current.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Gauge anomaly consistency filter](/figures/gauge-theories-standard-model/gauge-anomaly-consistency-filter.svg)

<figcaption>

A chiral fermion measure can generate a local anomaly in a gauge Ward identity. Counterterms can move an anomaly between currents, but if the cohomologically nontrivial gauge-anomaly coefficient is nonzero, the theory is not a consistent quantum gauge theory.

</figcaption>
</figure>

This page develops the general logic. The next page applies it to one Standard Model generation and shows the cancellations explicitly.

## Prerequisites

You should know [Chirality and Gauge Interactions](/gauge-theories-standard-model/flavor-neutrinos/chirality-and-gauge-interactions/), [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/), and [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/). You should also be comfortable with traces of Lie-algebra generators and with rewriting right-handed fermions as left-handed conjugate fields.

We use the volume conventions

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
\qquad
Q=T^3+Y.
$$

For anomaly arithmetic, the clean convention is to list **only left-handed Weyl fields**. A physical right-handed field in representation $R$ and Abelian charge $q$ is equivalently represented by a left-handed conjugate field in $\overline R$ and charge $-q$.

## Classical conservation versus quantum Ward identities

Consider a left-handed Weyl fermion $\psi_L$ transforming in a representation $R$ of a gauge group $G$. Schematically,

$$
\mathcal L
=
i\psi_L^\dagger \bar\sigma^\mu D_\mu\psi_L.
$$

Classically, local gauge invariance implies a covariant conservation law for the gauge current. In the quantum theory, the same statement becomes a Ward identity for the effective action $\Gamma[A]$. Under an infinitesimal gauge transformation with parameter $\alpha^a(x)$, consistency requires

$$
\delta_\alpha \Gamma[A]=0.
$$

A gauge anomaly is the failure of this equation:

$$
\delta_\alpha \Gamma[A]
=
\int d^4x\,\alpha^a(x)\,\mathcal G^a(x),
\qquad
\mathcal G^a(x)\ne0.
$$

Equivalently, a gauge-current Ward identity acquires a local term. In a perturbative diagrammatic language, the first place this can occur in four dimensions is a triangle diagram with one chiral fermion loop and three current insertions.

The conceptual point is sharper than the diagram. In the path integral, a classical transformation can leave the action invariant while changing the fermion measure. Regularization forces a choice of which identities are preserved. In vectorlike theories one can preserve the gauge identities and put anomalies only in global axial currents. In genuinely anomalous chiral gauge theories, no local counterterm removes the gauge anomaly from all gauge currents at once.

## Why gauge anomalies are fatal

Gauge symmetry is not an ordinary symmetry acting on distinct physical states. It is redundancy in the description. The Hilbert space, propagator, and unphysical polarizations are arranged so that only gauge-invariant states and amplitudes survive.

In a covariantly gauge-fixed theory this statement is encoded by BRST symmetry. Physical states are BRST cohomology classes, and gauge-parameter independence follows from BRST Ward identities. A gauge anomaly breaks the quantum BRST identity. Then the cancellation of negative-norm and longitudinal modes is no longer guaranteed.

That is why the slogan is:

$$
\boxed{\text{global anomaly in a global current: possible physics}}
$$

but

$$
\boxed{\text{anomaly in a dynamical gauge current: inconsistency}.}
$$

This is also why anomaly cancellation is one of the deepest checks of the Standard Model. The Standard Model is chiral, so it is allowed to fail this test. It does not.

## The four-dimensional triangle coefficient

For a simple non-Abelian gauge group, the perturbative gauge anomaly of a left-handed Weyl fermion in representation $R$ is controlled by

$$
\mathcal A^{abc}_R
=
\operatorname{tr}_R\!\left(T^a\{T^b,T^c\}\right).
$$

Here the trace is over the representation space of the left-handed Weyl fermion. The condition for cancellation is

$$
\sum_{\psi_L}\mathcal A^{abc}_{R_\psi}=0
\qquad
\text{for all }a,b,c.
$$

Only the vanishing of this tensor is convention-independent. The overall sign of the local anomaly depends on choices such as whether one writes all fields left-handed, how one defines $\epsilon^{\mu\nu\rho\sigma}$, and whether one writes the consistent or covariant anomaly. But the cancellation condition is not a convention.

For $SU(N)$, $N\ge3$, one often defines an anomaly coefficient $A(R)$ by

$$
\operatorname{tr}_R\!\left(T^a\{T^b,T^c\}\right)
=A(R)d^{abc},
$$

where $d^{abc}$ is the symmetric invariant tensor normalized in the fundamental representation. Then

$$
A(\overline R)=-A(R).
$$

This sign is the algebraic reason vectorlike pairs cancel. A left-handed fermion in $R$ plus a left-handed fermion in $\overline R$ has no cubic non-Abelian gauge anomaly.

For $SU(2)$, there is no perturbative cubic gauge anomaly because the relevant symmetric invariant vanishes: the fundamental representation is pseudoreal, and there is no $d^{abc}$ tensor. However, $SU(2)$ has a separate global anomaly in four dimensions: an odd number of left-handed doublets is inconsistent. That effect is not a triangle diagram and is treated later in [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/).

## Abelian and mixed anomalies

When a $U(1)$ gauge factor is present, anomaly cancellation includes several additional tests. Suppose a left-handed Weyl fermion has Abelian charge $q$ and transforms in a representation $R$ of a non-Abelian group $G$. Let $T_G(R)$ denote the Dynkin index,

$$
\operatorname{tr}_R(T^aT^b)=T_G(R)\delta^{ab}.
$$

Then the mixed $G^2U(1)$ anomaly is proportional to

$$
\sum_{\psi_L}q_\psi\,T_G(R_\psi)\,d_{\rm spectator}(\psi),
$$

where $d_{\rm spectator}$ is the product of dimensions under gauge factors not participating in the trace. For example, in an $SU(3)^2U(1)$ anomaly, an $SU(2)$ doublet counts twice because it contains two color triplets.

For the cubic Abelian anomaly, the condition is

$$
\sum_{\psi_L} q_\psi^3\,d_{\rm nonabelian}(\psi)=0,
$$

where $d_{\rm nonabelian}$ is the product of non-Abelian representation dimensions. For the mixed gravitational–Abelian anomaly, the condition is

$$
\sum_{\psi_L} q_\psi\,d_{\rm nonabelian}(\psi)=0.
$$

These formulas are the workhorses of Standard Model anomaly cancellation. Hypercharge is Abelian, so the Standard Model must pass

$$
[SU(3)_c]^2U(1)_Y,
\qquad
[SU(2)_L]^2U(1)_Y,
\qquad
[U(1)_Y]^3,
\qquad
[\text{gravity}]^2U(1)_Y.
$$

It also must have no $[SU(3)_c]^3$ anomaly and no global $SU(2)_L$ anomaly.

## Left-handed bookkeeping

A huge fraction of anomaly mistakes come from mixing two bookkeepings.

One method sums over physical chiralities. Then a right-handed fermion contributes with the opposite chirality sign from a left-handed fermion.

The other method, used here, converts every fermion into a left-handed Weyl field. Then there is no separate chirality sign, but right-handed fields are replaced by conjugates. For a right-handed field

$$
\psi_R\sim R_q,
$$

the corresponding left-handed conjugate is

$$
\psi_L^c\sim \overline R_{-q}.
$$

For a Dirac fermion with vectorlike gauge coupling, the left-handed ledger contains

$$
\psi_L\sim R_q,
\qquad
\psi_L^c\sim \overline R_{-q},
$$

so the cubic Abelian anomaly cancels as

$$
q^3+(-q)^3=0,
$$

and the non-Abelian anomaly cancels as

$$
A(R)+A(\overline R)=0.
$$

This is why QED and QCD with ordinary Dirac fermions are not gauge-anomalous, while the electroweak theory must be checked more carefully.

## Consistent and covariant anomalies

There are two anomaly formulas that students often meet: the **consistent anomaly** and the **covariant anomaly**.

The consistent anomaly is obtained from variation of an effective action. It obeys the Wess–Zumino consistency condition,

$$
\delta_{\alpha_1}\mathcal A(\alpha_2)
-
\delta_{\alpha_2}\mathcal A(\alpha_1)
=
\mathcal A([\alpha_1,\alpha_2]).
$$

The covariant anomaly transforms more simply under gauge transformations, but it is not directly the variation of an ordinary local effective action in the same way. The two differ by a local Bardeen–Zumino polynomial.

For anomaly cancellation in the Standard Model, this distinction usually does not affect the arithmetic. If the representation-theoretic anomaly coefficients vanish, both descriptions are safe. If they do not vanish, reshuffling local terms cannot make the gauge theory consistent.

## Anomaly polynomial viewpoint

A compact modern way to encode anomalies is through a higher-dimensional anomaly polynomial. In four dimensions, perturbative anomalies are encoded by a six-form. For a left-handed Weyl fermion, schematically,

$$
I_6
=
\left[\widehat A(TX)\,\operatorname{ch}_R(F)\right]_6.
$$

The purely gauge part contains the same cubic trace as the triangle diagram,

$$
I_6^{\rm gauge}\propto \operatorname{tr}_R(F^3),
$$

while the mixed gravitational–Abelian anomaly comes from terms involving the spacetime curvature and the $U(1)$ field strength.

This page does not develop descent, inflow, or global anomaly classification. The point of mentioning $I_6$ is to show that the triangle formula is not a random one-loop artifact. It is the local face of a robust topological structure.

## Common mistakes

**Summing physical right-handed charges without conjugating.** If you list $u_R$ rather than $u_L^c$, you must include a chirality sign. If you list everything left-handed, you must flip both the representation and Abelian charge for conjugate fields. Pick one ledger and stick to it.

**Forgetting multiplicities.** A quark doublet $Q_L$ is three colors times two weak components. In a $[U(1)_Y]^3$ anomaly it counts six times. In an $[SU(3)]^2U(1)$ anomaly it counts twice. In an $[SU(2)]^2U(1)$ anomaly it counts three times.

**Confusing perturbative and global anomalies.** The absence of an $SU(2)^3$ triangle anomaly does not imply every $SU(2)$ chiral theory is consistent. The global $SU(2)$ anomaly is a separate nonperturbative test.

**Calling every anomalous current a disaster.** The axial anomaly in QED and QCD is physical. The electroweak $B+L$ anomaly is physical. A hypercharge gauge anomaly would be fatal.

**Thinking anomaly cancellation is only a one-loop accident.** The one-loop triangle is how the local anomaly appears perturbatively, but its coefficient is protected. If it is nonzero, higher loops do not rescue the gauge symmetry.

## Exercises

### Exercise 1: Vectorlike cancellation

A Dirac fermion has left-handed component $\psi_L\sim R_q$ and right-handed component $\psi_R\sim R_q$. Rewrite the theory using only left-handed Weyl fields and show that the $U(1)^3$ and $G^3$ gauge anomalies cancel.

<details><summary><strong>Solution</strong></summary>

The right-handed field is represented by a left-handed conjugate field

$$
\psi_L^c\sim \overline R_{-q}.
$$

The $U(1)^3$ anomaly is proportional to

$$
q^3+(-q)^3=0.
$$

For the non-Abelian part,

$$
A(R)+A(\overline R)=A(R)-A(R)=0.
$$

Thus a vectorlike Dirac pair is gauge-anomaly free, although axial global currents may still be anomalous.

</details>

### Exercise 2: Mixed anomaly multiplicity

A left-handed Weyl fermion transforms as $(R,S)_q$ under $G_1\times G_2\times U(1)$. Show that its contribution to the $G_1^2U(1)$ anomaly is proportional to $qT_{G_1}(R)\dim S$.

<details><summary><strong>Solution</strong></summary>

The anomaly trace contains two $G_1$ generators and one $U(1)$ generator. On the full product representation, these act as

$$
T^a_{G_1}\otimes \mathbf1_S,
\qquad
T^b_{G_1}\otimes \mathbf1_S,
\qquad
q\,\mathbf1_R\otimes\mathbf1_S.
$$

The trace factorizes:

$$
q\,\operatorname{tr}_R(T^aT^b)\operatorname{tr}_S(\mathbf1_S)
=
qT_{G_1}(R)\delta^{ab}\dim S.
$$

So every spectator component contributes a copy of the same $G_1^2U(1)$ anomaly.

</details>

### Exercise 3: Why SU(2) has no perturbative cubic anomaly

Explain why a four-dimensional chiral theory with only $SU(2)$ gauge symmetry has no perturbative $SU(2)^3$ anomaly, even though it may still be inconsistent.

<details><summary><strong>Solution</strong></summary>

The perturbative cubic anomaly is controlled by a symmetric invariant tensor

$$
d^{abc}\propto\operatorname{tr}(T^a\{T^b,T^c\}).
$$

For $SU(2)$, the anticommutator of fundamental generators is proportional to the identity, and the trace of a single generator vanishes. More generally, $SU(2)$ has no independent symmetric cubic invariant. Therefore the local triangle anomaly vanishes.

However, $SU(2)$ has a global anomaly in four dimensions: a theory with an odd number of left-handed doublets has an ill-defined fermion determinant sign under a large gauge transformation. That is not detected by the local cubic trace.

</details>

## Relations to other pages

- [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) performs the Standard Model cancellation arithmetic.
- [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/) explains how anomaly cancellation interacts with Yukawa invariance and electric-charge assignments.
- [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) isolates the gravitational test $\sum Y=0$.
- [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/) treats the nonperturbative even-doublet condition.
- [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/) explains why anomalous global currents can be physically meaningful.

## Research status

Perturbative four-dimensional gauge anomalies and their cancellation conditions are established. The modern research frontier concerns the broader anomaly landscape: global anomalies, anomaly inflow, higher-form symmetries, non-invertible symmetries, cobordism constraints, and anomaly matching across phases and dual descriptions. Those refinements extend this page; they do not weaken the basic Standard Model gauge-anomaly test.

## Where to go next

Continue to [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/). The abstract condition $\sum\mathcal A=0$ becomes a short but surprisingly rigid set of Standard Model arithmetic identities.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomaly, and Standard Model sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the anomaly chapter and the weak-interaction chapter.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory and anomaly-matching discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and anomaly constraints in a broad field-theoretic setting.
- Coleman, *Aspects of Symmetry*, especially the lectures on currents, Ward identities, scale anomalies, and spontaneous symmetry breaking.
- Modern reviews on anomaly polynomials, inflow, global anomalies, and generalized symmetries for the topological formulation beyond triangle diagrams.

## Version history

- **2026-06-19:** Initial page explaining perturbative gauge anomalies, left-handed anomaly bookkeeping, Abelian and mixed anomaly tests, and the consistency reason gauge anomalies must cancel.
