---
title: "Triangle Anomaly"
description: "Derives and interprets the axial-vector-vector triangle anomaly as the one-loop obstruction to preserving all classical Ward identities at once."
sidebar:
  label: "Triangle Anomaly"
  order: 3
level: Graduate
status: "Polished draft"
source: "Adler–Bell–Jackiw; Bardeen; Rosenberg; Srednicki §§75–76; Schwartz Ch. 30; Weinberg Vol. II anomaly chapters."
topics:
  - triangle anomaly
  - axial anomaly
  - chiral anomaly
  - Ward identity
  - one-loop diagram
  - gauge anomaly
  - current algebra
canonicalTopics:
  - triangle-anomaly
  - abj-anomaly
  - avv-ward-identity
  - chiral-gauge-anomaly
researchStatus:
  established:
    - "The axial-vector-vector triangle graph gives the Adler–Bell–Jackiw anomaly: a regulator preserving vector gauge invariance necessarily violates the classical axial Ward identity."
    - "Perturbative gauge anomalies in four dimensions are controlled by triangle diagrams and group-theory traces over chiral fermion representations."
  active:
    - "Triangle anomalies remain a gateway to modern anomaly theory, but many current applications use anomaly polynomials, inflow, cobordism, and generalized symmetry rather than explicit loop diagrams."
---

## Summary

The **triangle anomaly** is the first anomaly most QFT students should compute. It is concrete enough to be a one-loop Feynman diagram and deep enough to reveal the modern meaning of an anomaly.

For a Dirac fermion coupled to a background electromagnetic field, the classical massless theory has an axial symmetry. The one-loop three-current correlator with one axial current and two vector currents says otherwise. If the regulator preserves the two vector Ward identities, the axial Ward identity becomes

$$
\partial_\lambda j_A^\lambda
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu},
$$

where

$$
j_A^\lambda=\frac12\bar\psi\gamma^\lambda\gamma^5\psi,
\qquad
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

The loop diagram is not merely a correction to a current. It is an incompatibility statement:

$$
\text{vector gauge invariance} + \text{local regulator}
\quad\Longrightarrow\quad
\text{axial current is anomalous}.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![The axial-vector-vector triangle anomaly. A fermion loop couples one axial current to two vector currents. The vector Ward identities can be preserved, but then the axial divergence is proportional to epsilon contracted with the two vector momenta.](/figures/symmetry-anomalies-topology/triangle-anomaly-ward-identities.svg)

<figcaption>

The AVV triangle. The two vector-current Ward identities are imposed to preserve background gauge invariance. The remaining axial divergence is the anomaly. A different counterterm can move the anomaly among the three legs, but not remove it while preserving all desired symmetries.

</figcaption>
</figure>

This page explains the diagram, the Ward-identity clash, the momentum-routing subtlety, and the group-theory generalization to chiral gauge anomalies.

## Prerequisites

Read [Regulator and Measure Viewpoints](/symmetry-anomalies-topology/anomalies/regulator-and-measure-viewpoints/) first. You should also know [Ward Identities: Operator Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-operator-form/), [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), [Current Algebra](/symmetry-anomalies-topology/noether-currents-ward-identities/current-algebra/), and [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/).

For the spinor algebra, use the site-wide conventions

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

## Core idea

The classical massless Dirac theory coupled to a background vector field has two natural currents:

$$
j_V^\mu=q\bar\psi\gamma^\mu\psi,
\qquad
j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi.
$$

Classically, with $m=0$,

$$
\partial_\mu j_V^\mu=0,
\qquad
\partial_\mu j_A^\mu=0.
$$

Quantum mechanically, the three-point function

$$
\langle j_A^\lambda j_V^\mu j_V^\nu\rangle
$$

cannot satisfy all three naive Ward identities after regularization. If $j_V^\mu$ is the current coupled to a background gauge field, then its Ward identities are gauge redundancies of the source. They must be preserved. The axial Ward identity is the one that fails.

The triangle graph therefore teaches the central anomaly lesson in a minimal setting:

> A symmetry can fail because the regulated loop integral cannot realize all formal current-conservation identities at once.

## Setup and conventions

Use the Lorentzian Lagrangian density

$$
\mathcal L=\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu-iqA_\mu.
$$

The vector source $A_\mu$ couples to

$$
j_V^\mu=q\bar\psi\gamma^\mu\psi.
$$

We normalize the axial transformation by

$$
\delta\psi=\frac{i\alpha}{2}\gamma^5\psi,
\qquad
\delta\bar\psi=\bar\psi\frac{i\alpha}{2}\gamma^5,
$$

so the axial current is

$$
j_A^\lambda=\frac12\bar\psi\gamma^\lambda\gamma^5\psi.
$$

With $\epsilon^{0123}=+1$ and

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma},
$$

the anomaly equation is

$$
\partial_\lambda j_A^\lambda
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

:::note[Current-normalization source note]
Many references define $j_5^\mu=\bar\psi\gamma^\mu\gamma^5\psi$ and write an anomaly twice as large as the formula above. This page uses $j_A^\mu=j_5^\mu/2$ because it is the Noether current for $\delta\psi=i\alpha\gamma^5\psi/2$. Always compare the normalization of the axial charge before comparing coefficients.
:::

## The AVV correlator

Define momenta $p$ and $q$ entering the two vector-current insertions. The axial insertion carries momentum

$$
r=-(p+q).
$$

The Fourier transform of the three-current correlator is

$$
T^{\lambda\mu\nu}(p,q)
=\int d^4x\,d^4y\,e^{ip\cdot x+iq\cdot y}
\langle 0|T\{j_A^\lambda(0)j_V^\mu(x)j_V^\nu(y)\}|0\rangle.
$$

At one loop it is represented by a fermion triangle. Suppressing overall sign conventions from time ordering, the two orientations give

$$
T^{\lambda\mu\nu}(p,q)
\sim q^2\int\frac{d^4\ell}{(2\pi)^4}
\operatorname{tr}\left[
\frac12\gamma^\lambda\gamma^5
\frac{i(\ell\!\!\!/+m)}{\ell^2-m^2+i\epsilon}
\gamma^\mu
\frac{i(\ell\!\!\!/+p\!\!\!/+m)}{(\ell+p)^2-m^2+i\epsilon}
\gamma^\nu
\frac{i(\ell\!\!\!/-q\!\!\!/+m)}{(\ell-q)^2-m^2+i\epsilon}
\right]
+\text{crossed}.
$$

Here $\ell\!\!\!/\equiv\gamma^\rho\ell_\rho$. The exact routing of $\ell$ is not important. In fact, the routing ambiguity is the whole point.

A superficial power count says the integral is linearly divergent. Therefore a shift of loop momentum is not automatically allowed. The naive textbook manipulation

$$
p_\mu\gamma^\mu
=S^{-1}(\ell+p)-S^{-1}(\ell)
$$

is valid algebraically inside the integrand, but turning it into a Ward identity requires shifting integration variables in divergent integrals. The difference is a finite surface term. That surface term is the anomaly.

## The Ward-identity clash

The three naive Ward identities are

$$
p_\mu T^{\lambda\mu\nu}(p,q)=0,
\qquad
q_\nu T^{\lambda\mu\nu}(p,q)=0,
\qquad
r_\lambda T^{\lambda\mu\nu}(p,q)=0
$$

for $m=0$. A regulator cannot make all three true while preserving locality and the vector gauge symmetry.

If the vector currents are coupled to a background gauge field, we impose

$$
p_\mu T^{\lambda\mu\nu}=0,
\qquad
q_\nu T^{\lambda\mu\nu}=0.
$$

Then the axial Ward identity becomes

$$
r_\lambda T^{\lambda\mu\nu}(p,q)
\propto q^2\epsilon^{\mu\nu\rho\sigma}p_\rho q_\sigma.
$$

The proportionality coefficient is fixed by matching to the local anomaly equation

$$
\partial_\lambda j_A^\lambda
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This is the cleanest way to remember the result. The momentum-space coefficient depends on Fourier-transform conventions, whether the current insertions include factors of $q$, and whether the axial current is $j_A$ or $j_5=2j_A$.

:::caution[The anomaly is not a failure of algebra]
The identities involving $S^{-1}(\ell+p)-S^{-1}(\ell)$ are algebraically true. The anomaly arises because divergent loop integrals require a regulator, and the regulated integral does not allow all formal shifts and all current Ward identities at the same time.
:::

## Momentum routing and local counterterms

Because the triangle integral is linearly divergent before regularization, changing the loop momentum routing changes the answer by a local polynomial in the external momenta. In position space, that is a contact term.

This is not a bug. It is the diagrammatic face of counterterm freedom. A local counterterm in the background effective action shifts the representative of the anomaly. For the AVV triangle, one can choose a scheme in which the anomaly is distributed symmetrically among the three currents, or a scheme in which the two vector currents are exactly conserved and the axial current is anomalous.

For QED, the vector current is coupled to a gauge field. Its Ward identity is non-negotiable, so the physically useful choice is

$$
\partial_\mu j_V^\mu=0,
\qquad
\partial_\mu j_A^\mu
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

For a chiral gauge theory, the same logic is harsher. If the anomalous current is a dynamical gauge current, there is no harmless place to put the anomaly. The fermion spectrum must make it cancel.

## Massive fermions and the pseudoscalar term

For $m\neq0$, the classical axial symmetry is explicitly broken. The divergence equation contains

$$
im\bar\psi\gamma^5\psi.
$$

This term is not the anomaly. It comes directly from the variation of the mass term.

The triangle diagram knows about both pieces. Contracting the axial leg gives a pseudoscalar insertion proportional to $m$ plus the anomalous surface term. In the heavy-mass limit, the pseudoscalar matrix element and the anomaly can cancel in low-energy amplitudes, reflecting decoupling of a heavy ordinary Dirac fermion from low-energy axial physics. In contrast, the anomaly of a chiral gauge representation cannot be removed by simply making the fermion heavy without addressing gauge invariance.

## Physical example: neutral pion decay

The historical puzzle was the decay

$$
\pi^0\to\gamma\gamma.
$$

The neutral pion couples to the axial current of light quarks. The electromagnetic field couples to the vector currents. The AVV triangle gives the anomalous divergence of the axial current and produces the leading low-energy amplitude for two photons.

The important conceptual point is not the phenomenology itself, which belongs in a particle-physics page. The important point here is that a symmetry argument based only on classical current conservation would miss the amplitude. The quantum anomaly supplies it.

## From axial anomaly to chiral gauge anomaly

The AVV diagram involves one axial and two vector currents. It can be rephrased in terms of left- and right-handed currents. Since

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
$$

an axial current is the difference between right- and left-handed currents, while a vector current is their sum.

A purely chiral gauge theory couples gauge fields to only left-handed or only right-handed Weyl fermions. Then triangle diagrams with three gauge-current insertions can produce a gauge anomaly.

For left-handed Weyl fermions in representations $R_i$ of a simple gauge algebra, the perturbative gauge anomaly is proportional to

$$
\sum_i \operatorname{tr}_{R_i}\left(T^a\{T^b,T^c\}\right).
$$

Gauge consistency requires this symmetric tensor to vanish for every triple of generators:

$$
\sum_i \operatorname{tr}_{R_i}\left(T^a\{T^b,T^c\}\right)=0.
$$

For groups such as $SU(2)$, this local cubic invariant vanishes, but global anomalies can still exist. Local triangle cancellation is necessary, not always sufficient.

:::note[Representation source note]
The trace above is over left-handed Weyl fermions. A right-handed Weyl fermion in representation $R$ can be rewritten as a left-handed Weyl fermion in the conjugate representation $\bar R$, which contributes with the corresponding conjugate group factor. This is why anomaly-cancellation checks are usually stated in a left-handed convention.
:::

## Abelian anomaly-cancellation conditions

For a $U(1)$ gauge theory with left-handed Weyl fermions of charges $Q_i$, the cubic gauge anomaly is proportional to

$$
\sum_i Q_i^3.
$$

There is also a mixed gauge-gravitational anomaly proportional to

$$
\sum_i Q_i.
$$

A consistent four-dimensional $U(1)$ chiral gauge theory therefore requires

$$
\sum_i Q_i^3=0,
\qquad
\sum_i Q_i=0,
$$

along with any mixed non-Abelian conditions if additional gauge groups are present.

These formulas are not optional model-building decorations. They are consistency conditions for the gauge theory path integral.

## Why the anomaly is one-loop exact

The triangle graph gives the coefficient of the axial anomaly. In ordinary gauge theories, the Adler–Bardeen theorem states that the coefficient of the chiral anomaly is not renormalized by higher-loop corrections, once the current and coupling conventions are fixed appropriately.

A modern way to understand this is that the anomaly is a cohomological and topological piece of the effective action. Higher loops can renormalize many current correlators, but they cannot continuously change the quantized obstruction class.

This statement has hypotheses. It should not be casually applied to every anomalous-looking contact term in every effective theory. But for the standard four-dimensional chiral anomaly, one-loop exactness is one of the reasons the triangle diagram is so powerful.

## The same result in three languages

| Language | What you compute | What fails |
|---|---|---|
| Triangle diagram | One-loop three-current correlator | The three naive Ward identities are mutually incompatible. |
| Fujikawa method | Regularized Jacobian of the fermion measure | The chiral measure is not invariant in a gauge-covariant regulator. |
| Background effective action | Variation of $W[A]$ | The anomalous variation cannot be removed by allowed local counterterms. |

The diagram is often the most memorable calculation. The background-field and descent languages are usually the best way to organize complicated anomaly systems.

## Common pitfalls

**Pitfall 1: Shifting loop momentum in a divergent integral without a regulator.**  
The triangle anomaly is exactly where that move is dangerous. First regulate, then derive the Ward identity.

**Pitfall 2: Treating all current conservation laws equally.**  
If a current is coupled to a dynamical gauge field, its Ward identity is a redundancy and must be preserved. A global axial current can be anomalous; a gauge current cannot be anomalous in a consistent theory.

**Pitfall 3: Forgetting the crossed diagram.**  
The full AVV amplitude includes both fermion-loop orientations. Omitting one orientation gives wrong symmetry factors and can obscure Bose symmetry of the vector legs.

**Pitfall 4: Comparing anomaly coefficients without current normalization.**  
The currents $j_A^\mu=\frac12\bar\psi\gamma^\mu\gamma^5\psi$ and $j_5^\mu=\bar\psi\gamma^\mu\gamma^5\psi$ differ by a factor of two. So do their Ward identities.

**Pitfall 5: Thinking local triangle cancellation rules out every anomaly.**  
Triangle diagrams diagnose perturbative local anomalies in even-dimensional theories. They do not detect every possible global anomaly, finite-group anomaly, or higher-form anomaly.

## Relations to other pages

This page prepares [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/), where the axial Ward identity and its physical consequences are treated directly, and [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/), where the measure calculation is done more systematically.

It also prepares [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

For Standard Model applications, see the later pages on anomaly cancellation in the Gauge Theories and Standard Model volume and [Anomaly Cancellation in the Standard Model](/symmetry-anomalies-topology/model-calculation-library/anomaly-cancellation-in-the-standard-model/).

## Research status

The triangle anomaly is established and exact in the standard perturbative setting. It is one of the cleanest examples where a one-loop computation reveals global information about the quantum theory.

Modern research rarely stops at the triangle graph. For complicated theories, anomalies are more efficiently classified by anomaly polynomials, inflow, generalized cohomology, cobordism, symmetry TFT, or categorical defect data. The triangle remains the local perturbative shadow of a broader anomaly structure.

## Exercises

### Exercise 1: Momentum-shift surface term

Consider a linearly divergent integral

$$
I(a)=\int^\Lambda d^4\ell\,f(\ell+a)
$$

with a cutoff that is not invariant under shifts of $\ell$. Explain why $I(a)-I(0)$ can have a finite limit as $\Lambda\to\infty$ even if $a$ is fixed and small.

<details><summary><strong>Solution</strong></summary>

For small $a$,

$$
f(\ell+a)-f(\ell)=a_\mu\frac{\partial f}{\partial \ell_\mu}+O(a^2).
$$

Integrating over the cutoff region gives

$$
I(a)-I(0)
=a_\mu\int_{|\ell|<\Lambda}d^4\ell\,\partial_{\ell_\mu}f(\ell)+\cdots.
$$

By the divergence theorem, this becomes a surface integral at $|\ell|=\Lambda$. For a linearly divergent integral, the large-$\ell$ falloff is just slow enough that the surface term can approach a finite value. This is the loop-momentum-routing mechanism behind the triangle anomaly.

</details>

### Exercise 2: Which Ward identity should be preserved?

In QED with a background electromagnetic field, the AVV triangle cannot preserve both vector Ward identities and the axial Ward identity. Which identities should be preserved, and why?

<details><summary><strong>Solution</strong></summary>

The vector current is coupled to the electromagnetic gauge field. Its Ward identity is the statement of background gauge invariance and, when the gauge field is dynamical, of gauge redundancy. It must be preserved for the theory to be consistent.

Therefore one chooses a regulator and counterterm scheme with

$$
p_\mu T^{\lambda\mu\nu}=0,
\qquad
q_\nu T^{\lambda\mu\nu}=0.
$$

The remaining violation appears in the axial Ward identity:

$$
\partial_\lambda j_A^\lambda
=im\bar\psi\gamma^5\psi
+\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The axial symmetry is global, so its anomaly is physical rather than inconsistent.

</details>

### Exercise 3: Abelian anomaly cancellation

A four-dimensional chiral $U(1)$ gauge theory has left-handed Weyl fermions with charges

$$
1,
\quad
1,
\quad
-2.
$$

Does it satisfy the cubic and mixed gravitational anomaly cancellation conditions?

<details><summary><strong>Solution</strong></summary>

The cubic condition is

$$
\sum_i Q_i^3=1^3+1^3+(-2)^3=1+1-8=-6.
$$

This does not vanish. The mixed gauge-gravitational condition is

$$
\sum_i Q_i=1+1-2=0.
$$

The mixed condition is satisfied, but the cubic gauge anomaly is not. The theory is not a consistent chiral $U(1)$ gauge theory as stated.

</details>

### Exercise 4: Vectorlike cancellation

Show that a Dirac fermion in a representation $R$ of a non-Abelian gauge group is free of perturbative gauge anomaly when written as two left-handed Weyl fermions.

<details><summary><strong>Solution</strong></summary>

A Dirac fermion consists of a left-handed Weyl fermion in representation $R$ and a right-handed Weyl fermion in the same representation. To express everything using left-handed fields, rewrite the right-handed fermion as a left-handed charge-conjugate fermion in $\bar R$.

The gauge anomaly contribution is proportional to

$$
\operatorname{tr}_{R}\left(T^a\{T^b,T^c\}\right)
+\operatorname{tr}_{\bar R}\left(T^a\{T^b,T^c\}\right).
$$

For the conjugate representation, the cubic anomaly coefficient has the opposite sign. Therefore the sum vanishes. This is why vectorlike gauge theories such as QED and QCD have no perturbative gauge anomaly.

</details>

## References

- S. L. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* **177** (1969).
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the $\sigma$-Model,” *Nuovo Cimento A* **60** (1969).
- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969).
- L. Rosenberg, “Electromagnetic Interactions of Neutrinos,” *Physical Review* **129** (1963).
- S. L. Adler and W. A. Bardeen, “Absence of Higher-Order Corrections in the Anomalous Axial-Vector Divergence Equation,” *Physical Review* **182** (1969).
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*, Oxford University Press.
- M. Srednicki, *Quantum Field Theory*, §§75–76.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, anomaly chapters.

## Version history

- 2026-06-18: First polished draft. Added AVV setup, Ward-identity clash, momentum-routing explanation, chiral gauge anomaly bridge, and exercises.
