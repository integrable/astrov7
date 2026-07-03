---
title: "QED Renormalization"
description: "A convention-consistent guide to field, mass, vertex, and charge renormalization in QED, with the Ward–Takahashi identity and the origin of charge running."
sidebar:
  label: "QED Renormalization"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§62–68; Schwartz Chs. 16, 18–19, 23; Zee on QED renormalization; Coleman lectures on renormalization and gauge invariance."
topics:
  - QED renormalization
  - Ward–Takahashi identity
  - charge renormalization
  - counterterms
  - running coupling
canonicalTopics:
  - qed-renormalization
  - ward-takahashi-identity
  - charge-renormalization
  - qed-counterterms
  - running-electric-charge
researchStatus:
  established:
    - "Perturbative QED renormalization is a standard, experimentally tested part of quantum field theory; the Ward–Takahashi identity relates the vertex and fermion wavefunction counterterms."
  active:
    - "High-precision QED calculations, bound-state QED, infrared-safe observables, and matching QED onto low-energy EFTs remain active technical areas."
---

## Summary

QED renormalization is the cleanest place to see how gauge symmetry controls ultraviolet divergences. The photon self-energy, electron self-energy, and vertex correction are individually divergent, but the divergences cannot be absorbed arbitrarily. Current conservation imposes the Ward–Takahashi identity, and that identity ties the divergent part of the vertex correction to the divergent part of the fermion wavefunction correction.

The central structural result is

$$
Z_1=Z_2,
$$

where $Z_1$ renormalizes the photon–fermion vertex and $Z_2$ renormalizes the fermion field. Therefore the renormalization of the electric charge is determined by the photon field renormalization $Z_3$, equivalently by vacuum polarization.

In a minimal subtraction convention with $N_f$ Dirac fermions of charges $q_i=Q_i e$, the one-loop running of the positive coupling parameter $e$ is

$$
\beta(e)
\equiv \mu\frac{de}{d\mu}
=\frac{e^3}{12\pi^2}\sum_{i=1}^{N_f}Q_i^2+O(e^5),
$$

or, for $\alpha=e^2/(4\pi)$,

$$
\mu\frac{d\alpha}{d\mu}
=\frac{2\alpha^2}{3\pi}\sum_{i=1}^{N_f}Q_i^2+O(\alpha^3).
$$

This positive sign is the perturbative expression of electric-charge screening: the effective charge grows as one probes shorter distances.

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), [Spinor QED](/gauge-theories-standard-model/qed/spinor-qed/), [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/), [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/), [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/), [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/), and [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/).

You should also know the general renormalization idea from [Renormalizability of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/renormalizability-of-gauge-theories/) and the counterterm logic from [Gauge-Invariant Counterterms](/gauge-theories-standard-model/gauge-renormalization/gauge-invariant-counterterms/).

## Core idea

The easiest wrong way to renormalize QED is to stare at three divergent one-loop diagrams and introduce unrelated counterterms for all of them. That would miss the point. QED has a local gauge redundancy, and after gauge fixing it still remembers that redundancy through the Ward–Takahashi identity.

The identity says, roughly, that inserting the current is the same as differentiating the inverse fermion propagator. Thus the short-distance divergence in the photon–fermion vertex is not a new physical coupling. It is the same divergence already present in the fermion wavefunction normalization.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A flowchart showing bare QED variables, field renormalization, counterterms, the Ward–Takahashi identity, the relation $Z_1=Z_2$, and charge renormalization through $Z_3$.](/figures/gauge-theories-standard-model/qed-renormalization-constants.svg)

<figcaption>

QED has four natural counterterm structures, but the Ward–Takahashi identity removes one would-be independent charge renormalization. Once $Z_1=Z_2$, the running of $q$ is fixed by the photon field renormalization $Z_3$.

</figcaption>
</figure>

The phrase “the electric charge is renormalized” therefore means something precise: after a convention for the renormalized photon field has been chosen, the charge parameter needed to match a physical long-distance measurement depends on the scale at which it is defined.

## Setup and conventions

We use the mostly-minus metric and Abelian covariant derivative convention

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

A field of charge $q$ transforms as

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

For a Dirac field of charge $q$, the gauge-invariant part of the QED Lagrangian is

$$
\mathcal L_{\rm QED}
=-\frac14 F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-q\bar\psi\gamma^\mu A_\mu\psi.
$$

For the physical electron, $q=-e$ with $e>0$. Many formulas below are written for a generic charge $q$ or for several charges $q_i=Q_i e$. If one reverses the sign convention for the charge, the photon–fermion vertex changes sign, but the renormalization identities and beta functions for $e^2$ are unchanged.

In a covariant gauge, the gauge-fixing term is

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

The photon propagator depends on $\xi$, but gauge-invariant observables and the beta function for the electric charge do not.

## Bare and renormalized QED

In dimensional regularization, take

$$
d=4-2\epsilon.
$$

The bare QED Lagrangian may be written as

$$
\mathcal L_0
=-\frac14 F_{0\mu\nu}F_0^{\mu\nu}
+\bar\psi_0(i\gamma^\mu\partial_\mu-m_0)\psi_0
-q_0\bar\psi_0\gamma^\mu A_{0\mu}\psi_0
-\frac{1}{2\xi_0}(\partial_\mu A_0^\mu)^2.
$$

Introduce renormalized fields by

$$
A_{0\mu}=Z_3^{1/2}A_\mu,
\qquad
\psi_0=Z_2^{1/2}\psi.
$$

There are two common ways to handle the charge. One may define

$$
q_0=\mu^\epsilon Z_q q,
$$

or one may define a vertex renormalization constant $Z_1$ by

$$
q_0 Z_2 Z_3^{1/2}=\mu^\epsilon Z_1 q.
$$

These two definitions are equivalent. They simply package the same bookkeeping differently:

$$
Z_q=Z_1 Z_2^{-1}Z_3^{-1/2}.
$$

The Ward–Takahashi identity will imply $Z_1=Z_2$, and therefore

$$
Z_q=Z_3^{-1/2}.
$$

That is the compact statement of charge renormalization in QED.

## Counterterm Lagrangian

Write each renormalization constant as

$$
Z_i=1+\delta_i.
$$

Then the renormalized Lagrangian plus counterterms can be organized as

$$
\mathcal L
=\mathcal L_{\rm ren}+\mathcal L_{\rm ct},
$$

where

$$
\mathcal L_{\rm ren}
=-\frac14 F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-q\mu^\epsilon\bar\psi\gamma^\mu A_\mu\psi
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

A convenient counterterm basis is

$$
\mathcal L_{\rm ct}
=-\frac14\delta_3 F_{\mu\nu}F^{\mu\nu}
+\delta_2\bar\psi i\gamma^\mu\partial_\mu\psi
-\delta_m m\bar\psi\psi
-\delta_1 q\mu^\epsilon \bar\psi\gamma^\mu A_\mu\psi
+\mathcal L_{\rm gf,ct}.
$$

The exact definitions of $\delta_m$ and $\mathcal L_{\rm gf,ct}$ vary slightly by convention. The important structural point is stable:

| Counterterm | Diagrammatic role | Physical interpretation |
|---|---|---|
| $\delta_3$ | photon two-point function | photon field normalization and charge running |
| $\delta_2$ | fermion two-point function | fermion field normalization |
| $\delta_m$ | fermion two-point function | fermion mass renormalization |
| $\delta_1$ | photon–fermion vertex | not independent after the Ward identity |

Gauge symmetry allows the four local structures, but the Ward–Takahashi identity relates their divergent parts.

## Ward–Takahashi identity and the equality of vertex and wavefunction renormalization

Let $S(p)$ be the full fermion propagator and let $\Gamma^\mu(p+k,p)$ be the full one-particle-irreducible vertex associated with the current insertion. With the current normalized so that the tree-level vertex is $\gamma^\mu$, the Ward–Takahashi identity is

$$
k_\mu\Gamma^\mu(p+k,p)=S^{-1}(p+k)-S^{-1}(p).
$$

The zero-momentum limit gives

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

This equation is powerful because both sides are ultraviolet divergent before renormalization. The divergent part of $\partial S^{-1}/\partial p_\mu$ is exactly the fermion wavefunction divergence. The divergent part of $\Gamma^\mu$ is the vertex divergence. Therefore the counterterms must satisfy

$$
Z_1=Z_2.
$$

This identity is not a numerical accident of one loop. It follows from the quantum implementation of gauge invariance. In QED, ghosts decouple and the Ward identity is especially simple. In non-Abelian gauge theory, the corresponding statement is replaced by Slavnov–Taylor identities.

## What actually renormalizes the electric charge

Because

$$
Z_q=Z_1Z_2^{-1}Z_3^{-1/2},
$$

the Ward identity gives

$$
Z_q=Z_3^{-1/2}.
$$

Thus the charge running is controlled by the photon two-point function. Physically, this is the statement that the observed electric charge depends on how the vacuum polarizes around a charged source.

In a theory with $N_f$ Dirac fermions of charges $q_i=Q_i e$, the divergent part of the one-loop photon field renormalization in minimal subtraction is

$$
Z_3
=1-\frac{e^2}{12\pi^2\epsilon}\sum_{i=1}^{N_f}Q_i^2+O(e^4).
$$

This implies

$$
\beta(e)
=\frac{e^3}{12\pi^2}\sum_iQ_i^2+O(e^5).
$$

Equivalently,

$$
\beta(\alpha)
\equiv \mu\frac{d\alpha}{d\mu}
=\frac{2\alpha^2}{3\pi}\sum_iQ_i^2+O(\alpha^3),
\qquad
\alpha=\frac{e^2}{4\pi}.
$$

The sign is positive. In a mass-independent scheme, the coupling increases with the renormalization scale. In the effective-charge language, the measured charge is smaller at large distances because virtual charged pairs screen the source.

## One-loop anatomy

The one-loop QED renormalization problem involves three basic divergent amplitudes.

| Amplitude | One-loop diagram | Divergent structure | Main counterterm |
|---|---|---|---|
| Photon two-point function | fermion loop | transverse tensor $(k^2\eta^{\mu\nu}-k^\mu k^\nu)$ | $\delta_3$ |
| Fermion two-point function | photon loop | terms proportional to $p\!\!\!/$ and $m$ | $\delta_2$, $\delta_m$ |
| Vertex function | one photon exchanged inside the vertex | term proportional to $\gamma^\mu$ plus finite form factors | $\delta_1$ |

The photon two-point function is transverse:

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

That transversality forbids a photon mass counterterm. The fermion self-energy can renormalize the fermion kinetic term and mass. The vertex correction can renormalize the coefficient of $\bar\psi\gamma^\mu A_\mu\psi$, but its divergence is locked to the fermion kinetic divergence.

At finite momentum transfer, the vertex also contains physical form factors. For an on-shell fermion, one commonly writes

$$
\bar u(p')\Gamma^\mu(p',p)u(p)
=\bar u(p')\left[\gamma^\mu F_1(k^2)
+\frac{i\sigma^{\mu\nu}k_\nu}{2m}F_2(k^2)\right]u(p),
$$

where $k=p'-p$. The anomalous magnetic moment is encoded in $F_2(0)$. This finite physics is not the same thing as the ultraviolet charge counterterm.

## Schemes and physical meanings

Different renormalization schemes answer different practical questions.

### On-shell scheme

In an on-shell scheme, the renormalized mass is the pole mass of the fermion, and the electric charge is fixed by a low-energy physical measurement, such as the long-distance Coulomb force. This scheme is close to experimental language for ordinary QED.

Its conceptual advantage is direct physical interpretation. Its disadvantage is that it can obscure simple high-energy logarithmic running, especially in theories with multiple thresholds.

### Minimal subtraction

In minimal subtraction or modified minimal subtraction, counterterms subtract poles in $\epsilon$ and standard constants. The coupling is defined at an arbitrary scale $\mu$.

This scheme is efficient for RG equations. Its disadvantage is that particles do not automatically decouple at their masses; threshold matching must be imposed when one changes the effective theory.

### Effective charge

One can also define a physical effective charge by a measured amplitude, for example by the coefficient of the Coulomb potential or a scattering observable. This is often the clearest way to explain screening, but it is observable-dependent beyond leading universal behavior.

The same physics can be expressed in all three languages. The crime is not choosing a scheme; the crime is mixing schemes without saying so.

## Gauge-parameter dependence

The covariant-gauge photon propagator is

$$
D_{\mu\nu}(k)
=\frac{-i}{k^2+i\epsilon}
\left[\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right].
$$

Some intermediate quantities depend on $\xi$. In particular, the fermion wavefunction renormalization $Z_2$ and the vertex renormalization $Z_1$ can depend on the gauge parameter. The equality $Z_1=Z_2$ is compatible with that dependence.

The charge beta function does not depend on $\xi$ at one loop, and physical observables do not depend on $\xi$ when all diagrams, counterterms, and external-leg factors are included consistently.

This is an important practical diagnostic: if a calculation of a gauge-invariant observable retains a leftover $\xi$, something has been omitted or mis-renormalized.

## How to check a QED renormalization calculation

A reliable QED renormalization calculation should pass these tests.

| Check | What should happen |
|---|---|
| Photon transversality | $k_\mu\Pi^{\mu\nu}(k)=0$ after a gauge-respecting regulator or subtraction. |
| No photon mass counterterm | No local term $m_\gamma^2A_\mu A^\mu/2$ is allowed. |
| Ward identity | The divergent parts of the vertex and fermion kinetic counterterms obey $Z_1=Z_2$. |
| Charge running | The beta function follows from $Z_3$. |
| Gauge-parameter cancellation | Physical observables do not depend on $\xi$. |
| Scheme bookkeeping | The same renormalization convention is used in loops, counterterms, and parameter definitions. |

These checks are often more valuable than memorizing a table of $Z$ factors. The $Z$ factors change with conventions; the identities are the skeleton.

## Common pitfalls

**Mistaking $Z_1=Z_2$ for “there is no charge renormalization.”** QED has charge renormalization. The equality $Z_1=Z_2$ says that charge renormalization comes through $Z_3$, not through an independent vertex divergence.

**Forgetting the sign of the physical electron charge.** The covariant derivative is $D_\mu=\partial_\mu+iqA_\mu$. For the electron, $q=-e$. Many textbook formulas use $e>0$ while writing the interaction as $-e\bar\psi\gamma^\mu A_\mu\psi$ for a representative charged fermion. Always check which symbol denotes the signed charge.

**Confusing a field renormalization with an observable.** $Z_2$ and $Z_3$ depend on convention. The S-matrix, properly defined effective charges, and bound-state observables do not.

**Dropping finite terms without specifying a scheme.** Minimal subtraction removes pole terms. On-shell renormalization also fixes selected finite parts. Both are valid, but they define different renormalized parameters.

**Treating the Landau pole as a laboratory prediction at the pole scale.** The perturbative Landau pole indicates that pure QED cannot be a complete ultraviolet theory in that naive form. In the real Standard Model, QED is embedded in electroweak theory long before such an extrapolation becomes meaningful.

**Using a hard cutoff carelessly.** A naive momentum cutoff can violate gauge invariance and produce spurious non-transverse terms. It can be used with care, but dimensional regularization or a gauge-invariant regulator usually makes the Ward identity easier to preserve.

## Relations to other pages

This page is the renormalization sequel to [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) and [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/). Those pages explain the one-loop physics of screening; this page explains how the same effect appears in the full counterterm structure of QED.

It is the Abelian prototype for [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/). In QED, ghosts decouple and the Ward identity is simple. In Yang–Mills theory, gauge bosons carry gauge charge, ghosts are essential, and the Slavnov–Taylor identities replace the simple Abelian identity.

It also prepares for Standard Model renormalization. The electroweak theory contains Abelian and non-Abelian gauge factors, chiral fermions, spontaneous symmetry breaking, and mixing angles. The same logic survives, but the bookkeeping gets more interesting. Naturally.

## Research status

The conceptual structure of perturbative QED renormalization is established. The Ward–Takahashi identity, the equality $Z_1=Z_2$, and the one-loop beta function are standard material.

Active work is mostly not about whether QED is renormalizable. It concerns very high-order calculations, precision comparison with experiment, bound-state QED, effective-field-theory matching, infrared-safe observables, and QED corrections inside the full Standard Model.

## Exercises

### Exercise 1: From the Ward identity to $Z_1=Z_2$

Assume the inverse fermion propagator has divergent part

$$
S^{-1}_{\rm div}(p)=A_{\rm div}p\!\!\!/-B_{\rm div}m.
$$

Use the zero-momentum Ward identity

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}
$$

to identify the divergent part of the vertex proportional to $\gamma^\mu$.

<details><summary><strong>Solution</strong></summary>

Differentiate the divergent inverse propagator with respect to $p_\mu$:

$$
\frac{\partial S^{-1}_{\rm div}(p)}{\partial p_\mu}
=A_{\rm div}\gamma^\mu.
$$

The divergent vertex proportional to $\gamma^\mu$ is therefore controlled by the same coefficient $A_{\rm div}$ that renormalizes the fermion kinetic term. This is the diagrammatic content of $Z_1=Z_2$. The mass divergence $B_{\rm div}m$ does not contribute to the zero-momentum current vertex because it has no $p$ dependence.

</details>

### Exercise 2: Charge beta function from $Z_3$

For one Dirac fermion of unit charge, minimal subtraction gives

$$
Z_3=1-\frac{e^2}{12\pi^2\epsilon}+O(e^4).
$$

Using $e_0=\mu^\epsilon Z_3^{-1/2}e$, extract the one-loop beta function.

<details><summary><strong>Solution</strong></summary>

Since the bare coupling is independent of $\mu$,

$$
0=\mu\frac{d}{d\mu}\left(\mu^\epsilon Z_3^{-1/2}e\right).
$$

In minimal subtraction, the coefficient of the simple pole determines the one-loop beta function. With

$$
Z_3^{-1/2}=1+\frac{e^2}{24\pi^2\epsilon}+O(e^4),
$$

the result in four dimensions is

$$
\beta(e)=\frac{e^3}{12\pi^2}+O(e^5).
$$

For charges $q_i=Q_i e$, multiply the coefficient by $\sum_i Q_i^2$.

</details>

### Exercise 3: Multiple charged fermions

Suppose QED contains two Dirac fermions with charges $e$ and $2e$. What is the one-loop beta function for $e$ in minimal subtraction?

<details><summary><strong>Solution</strong></summary>

The charge weights are $Q_1=1$ and $Q_2=2$, so

$$
\sum_i Q_i^2=1^2+2^2=5.
$$

Therefore

$$
\beta(e)=\frac{5e^3}{12\pi^2}+O(e^5).
$$

The charge with magnitude $2e$ contributes four times as much as the unit-charge fermion because vacuum polarization contains two electromagnetic vertices.

</details>

### Exercise 4: Why a photon mass counterterm is forbidden

Show that the local term $m_\gamma^2A_\mu A^\mu/2$ is not invariant under

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Why is this related to the transversality of the vacuum polarization tensor?

<details><summary><strong>Solution</strong></summary>

Under a gauge transformation,

$$
A_\mu A^\mu
\mapsto
A_\mu A^\mu+2A^\mu\partial_\mu\alpha+\partial_\mu\alpha\,\partial^\mu\alpha.
$$

The extra terms are not a total derivative for arbitrary $\alpha(x)$. Thus a photon mass term is not gauge invariant.

At the level of the photon two-point function, gauge invariance requires

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

The only Lorentz-covariant two-index structure consistent with this condition is proportional to

$$
k^2\eta^{\mu\nu}-k^\mu k^\nu,
$$

up to gauge-fixing artifacts. A mass term would contribute a term proportional to $\eta^{\mu\nu}$ without the compensating $k^\mu k^\nu$ structure, so it is forbidden.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§62–68, for loop corrections, QED beta functions, and Ward identities in spinor electrodynamics.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 16, 18–19, and 23, for vacuum polarization, mass renormalization, renormalized perturbation theory, and RG equations.
- Zee, *Quantum Field Theory in a Nutshell*, sections on renormalization and gauge invariance, for the physical charge-screening narrative.
- Coleman, *Aspects of Symmetry*, lectures on renormalization and gauge invariance, for a concise conceptual perspective.
- Weinberg, *The Quantum Theory of Fields*, Vol. I and Vol. II, for the systematic treatment of renormalization and gauge-theory identities.

## Version history

- **2026-06-18:** Initial polished draft for the Gauge Renormalization chapter.
