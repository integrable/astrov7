---
title: "Spinor QED"
description: "Defines spinor quantum electrodynamics as a Dirac field coupled to a U(1) gauge field, fixing charge conventions, equations of motion, current normalization, vertex signs, and Ward-identity checks."
sidebar:
  label: "Spinor QED"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §58; Schwartz Chs. 8, 10, 13–14; Coleman lectures on electromagnetic interactions and QED; Zee QED chapters."
topics:
  - spinor QED
  - Dirac fields
  - electromagnetic current
  - electron-photon vertex
  - Ward identities
canonicalTopics:
  - spinor-qed
  - quantum-electrodynamics
  - dirac-field
  - electromagnetic-current
researchStatus:
  established:
    - "Spinor QED is the standard renormalizable Abelian gauge theory of a charged Dirac fermion and the prototype for gauge-invariant perturbation theory with spin-one-half matter."
  active:
    - "Precision QED, infrared-safe charged observables, asymptotic dressing, and multi-loop calculations remain active topics, but the local Lagrangian and Ward identities on this page are settled textbook material."
---

## Summary

Spinor QED is the quantum field theory of a Dirac fermion coupled to the electromagnetic $U(1)$ gauge field. In the conventions of this volume, a Dirac field of electric charge $q$ transforms as

$$
\psi(x)\mapsto e^{-iq\lambda(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\lambda(x),
$$

and the covariant derivative is

$$
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi.
$$

The minimal spinor-QED Lagrangian is

$$
\mathcal L_{\mathrm{spinor\ QED}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding the covariant derivative gives

$$
\mathcal L_{\mathrm{spinor\ QED}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
$$

Thus the electromagnetic source current of this Dirac field is

$$
j^\mu=q\bar\psi\gamma^\mu\psi,
$$

and the interaction has the source form

$$
\mathcal L_{\mathrm{int}}=-j^\mu A_\mu.
$$

For the electron, $q=-e$ with $e>0$, so

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e,
\qquad
\mathcal L_{\mathrm{int}}=+eA_\mu\bar\psi_e\gamma^\mu\psi_e.
$$

The corresponding photon–fermion vertex for a fermion of charge $q$ is

$$
-iq\gamma^\mu,
$$

so for the electron in this convention it is $+ie\gamma^\mu$. Many books choose the opposite sign convention for $D_\mu$; the physics is the same, but the vertex sign must be translated consistently.

<figure class="doc-figure" style="--figure-width: 47rem;">

![Spinor QED current, interaction, and vertex structure.](/figures/gauge-theories-standard-model/spinor-qed-current-vertex.svg)

<figcaption>

Spinor QED couples the Dirac current $j^\mu=q\bar\psi\gamma^\mu\psi$ to the gauge field through $-j^\mu A_\mu$. The same current gives the fermion–photon vertex $-iq\gamma^\mu$ and the elementary Ward check $k_\mu\gamma^\mu=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)$.

</figcaption>
</figure>

## Prerequisites

You should know [Maxwell Theory as Gauge Theory](/gauge-theories-standard-model/qed/maxwell-theory-as-gauge-theory/), [Minimal Coupling](/gauge-theories-standard-model/gauge-principle/minimal-coupling/), and the Abelian convention in [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/). You should also be comfortable with the free Dirac field, the adjoint spinor $\bar\psi=\psi^\dagger\gamma^0$, the Clifford algebra

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu},
$$

and the free spinor propagator

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

This page focuses on the local Lagrangian, currents, charge conventions, and first Ward-identity checks. Gauge fixing, photon propagators, loop corrections, renormalization, and infrared subtleties come later in the chapter.

## Core idea

The free Dirac Lagrangian

$$
\mathcal L_0=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
$$

has a global $U(1)$ phase symmetry

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\bar\psi\mapsto \bar\psi e^{iq\alpha}
$$

for constant $\alpha$. The parameter $q$ is included so that the same symbol appearing in the local phase also appears as the electric charge. The corresponding conserved current is

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

Spinor QED promotes the constant phase choice to a spacetime-dependent phase. Ordinary derivatives do not transform covariantly under $\lambda=\lambda(x)$, because

$$
\partial_\mu(e^{-iq\lambda}\psi)
=e^{-iq\lambda}\partial_\mu\psi-iq(\partial_\mu\lambda)e^{-iq\lambda}\psi.
$$

The gauge field is introduced precisely to cancel the extra derivative of the phase:

$$
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi.
$$

With

$$
A_\mu\mapsto A_\mu+\partial_\mu\lambda,
$$

the covariant derivative transforms as

$$
D_\mu\psi\mapsto e^{-iq\lambda}D_\mu\psi.
$$

That one covariance statement fixes the minimal spinor-QED interaction. It is not a decorative rule of thumb; it is the reason the electron-photon vertex, current conservation, and Ward identities fit together.

## Setup and conventions

We use mostly-minus metric and the Abelian convention

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The charge $q$ is the physical electric charge of the field. Equivalently, one can write

$$
q=eQ,
$$

where $e>0$ is the magnitude of the proton charge and $Q$ is the dimensionless charge in proton-charge units. Then

$$
Q_e=-1,
\qquad
Q_u=+\frac23,
\qquad
Q_d=-\frac13.
$$

For a Dirac spinor of charge $q$, the transformations are

$$
\psi\mapsto e^{-iq\lambda}\psi,
\qquad
\bar\psi\mapsto \bar\psi e^{iq\lambda}.
$$

The adjoint covariant derivative is

$$
D_\mu\bar\psi=\partial_\mu\bar\psi-iqA_\mu\bar\psi,
$$

so

$$
D_\mu\bar\psi\mapsto (D_\mu\bar\psi)e^{iq\lambda}.
$$

The mass term is gauge invariant:

$$
\bar\psi\psi\mapsto \bar\psi e^{iq\lambda}e^{-iq\lambda}\psi=\bar\psi\psi.
$$

This is special to a vectorlike Dirac fermion whose left- and right-handed components have the same charge. In the electroweak Standard Model, left- and right-handed fermions transform differently before symmetry breaking, so ordinary Dirac mass terms are not gauge invariant until the Higgs field participates.

## The spinor-QED Lagrangian

The gauge-invariant action is

$$
S=\int d^4x\,\mathcal L,
$$

with

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding the matter term gives

$$
\begin{aligned}
\bar\psi i\gamma^\mu D_\mu\psi
&=\bar\psi i\gamma^\mu\partial_\mu\psi
+\bar\psi i\gamma^\mu(iqA_\mu)\psi\\
&=\bar\psi i\gamma^\mu\partial_\mu\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
\end{aligned}
$$

Therefore

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-j^\mu A_\mu,
$$

where

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

This is the simplest place where the sign convention earns its keep. If $q=-e$ for the electron, then

$$
j_e^\mu=-e\bar\psi_e\gamma^\mu\psi_e,
\qquad
-j_e^\mu A_\mu=+eA_\mu\bar\psi_e\gamma^\mu\psi_e.
$$

The interaction term therefore has the opposite sign from a positively charged fermion of the same mass. That is not a convention-dependent statement; the label “electron” means negative electric charge. What is convention-dependent is whether the negative charge sits in $q$, in the definition of $D_\mu$, or in the gauge transformation parameter.

## Gauge invariance of the action

The Maxwell term is gauge invariant because $F_{\mu\nu}$ is invariant under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$:

$$
F_{\mu\nu}\mapsto
\partial_\mu(A_\nu+\partial_\nu\lambda)
-\partial_\nu(A_\mu+\partial_\mu\lambda)
=F_{\mu\nu}.
$$

The Dirac kinetic term is gauge invariant because

$$
\bar\psi i\gamma^\mu D_\mu\psi
\mapsto
\bar\psi e^{iq\lambda}i\gamma^\mu e^{-iq\lambda}D_\mu\psi
=
\bar\psi i\gamma^\mu D_\mu\psi.
$$

Here the phase commutes with the gamma matrices because the gauge group is the Abelian internal group $U(1)$, not a spacetime spin transformation. The mass term was already checked above. Thus the full Lagrangian is invariant under the local $U(1)$ redundancy.

It is sometimes illuminating to check the same statement using the expanded Lagrangian. The free Dirac term varies under a local phase by a term proportional to $\partial_\mu\lambda$; the variation of $-j^\mu A_\mu$ cancels it. In this expanded form, gauge invariance looks like a conspiracy between two terms. In the covariant-derivative form, the conspiracy is already solved.

## Equations of motion

Varying with respect to $\bar\psi$ gives the minimally coupled Dirac equation

$$
(i\gamma^\mu D_\mu-m)\psi=0.
$$

Varying with respect to $\psi$ gives the adjoint equation

$$
i(D_\mu\bar\psi)\gamma^\mu+m\bar\psi=0.
$$

These imply current conservation. Indeed,

$$
\partial_\mu(\bar\psi\gamma^\mu\psi)
=(\partial_\mu\bar\psi)\gamma^\mu\psi
+\bar\psi\gamma^\mu\partial_\mu\psi.
$$

Replacing ordinary derivatives by covariant derivatives in the gauge-invariant bilinear gives the same result because the connection terms cancel:

$$
\partial_\mu(\bar\psi\gamma^\mu\psi)
=(D_\mu\bar\psi)\gamma^\mu\psi
+\bar\psi\gamma^\mu D_\mu\psi.
$$

Using the two Dirac equations yields

$$
\partial_\mu j^\mu=0.
$$

Varying with respect to $A_\mu$ gives Maxwell's equation with source:

$$
\partial_\nu F^{\nu\mu}=j^\mu.
$$

Taking the divergence of both sides gives

$$
\partial_\mu j^\mu=\partial_\mu\partial_\nu F^{\nu\mu}=0,
$$

where the right-hand side vanishes because $F^{\nu\mu}$ is antisymmetric. Thus the gauge-field equation itself also enforces the consistency condition that the source must be conserved.

## The vertex sign

The interaction term for a fermion of charge $q$ is

$$
\mathcal L_{\mathrm{int}}=-qA_\mu\bar\psi\gamma^\mu\psi.
$$

In the Lorentzian path integral, interaction vertices come from $i\int d^4x\,\mathcal L_{\mathrm{int}}$. Therefore the photon–fermion vertex factor is

$$
-iq\gamma^\mu.
$$

For an electron, $q=-e$, so the vertex factor is

$$
+ie\gamma^\mu.
$$

For a positron, one does not introduce a separate field with charge $+e$ in ordinary Dirac QED. The antiparticle is created and annihilated by the same Dirac field. The sign of its physical charge emerges from the charge operator and the orientation of fermion lines in amplitudes.

A useful convention-independent way to state the rule is this:

$$
\text{vertex}=-i(\text{charge carried by the fermion field})\,\gamma^\mu.
$$

Then translate the charge label and the covariant-derivative sign used in the book you are reading. This tiny translation step prevents a shocking amount of sign confetti.

## Relation to the nonrelativistic coupling

The sign convention also matches the familiar nonrelativistic minimal coupling. The Dirac equation is

$$
(i\gamma^\mu D_\mu-m)\psi=0.
$$

Write the contravariant electromagnetic potential as

$$
A^\mu=(\Phi,\mathbf A),
\qquad
A_\mu=(\Phi,-\mathbf A).
$$

Then the spatial part of $D_\mu=\partial_\mu+iqA_\mu$ is

$$
D_i=\partial_i-iq\mathbf A_i.
$$

The nonrelativistic Hamiltonian for a particle of charge $q$ contains

$$
\frac{1}{2m}(\mathbf p-q\mathbf A)^2+q\Phi.
$$

For the electron, $q=-e$, this is

$$
\frac{1}{2m}(\mathbf p+e\mathbf A)^2-e\Phi.
$$

The relativistic covariant derivative is the field-theory package that reproduces this minimal coupling after the nonrelativistic limit is taken.

## Ward identity at the vertex

Spinor QED is the cleanest place to see why replacing a photon polarization vector by the photon momentum should make an amplitude vanish after all diagrams are included. At the level of one fermion line, the key algebra is

$$
k_\mu\gamma^\mu=k\!\!\!/.
$$

If a photon of momentum $k$ attaches to a fermion line carrying momentum $p$ before the insertion and $p+k$ after the insertion, then

$$
k\!\!\!/
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

The two terms on the right are inverse Dirac operators. Inside a diagram they cancel neighboring fermion propagators. On an external on-shell spinor, they vanish by the free Dirac equation:

$$
(p\!\!\!/-m)u(p)=0,
\qquad
\bar u(p)(p\!\!\!/-m)=0,
$$

with analogous relations for $v$ spinors. The full Ward identity is not merely this one-line algebra, because a photon can attach to every charged line in a process. But the cancellation mechanism starts here: the contraction of the vertex with photon momentum turns into a difference of inverse propagators.

This is the spinor-QED version of a larger principle: gauge invariance makes longitudinal photon polarizations decouple from physical amplitudes. In later pages, the Ward–Takahashi identity upgrades this tree-level check to a statement about full quantum Green functions.

## Several charged Dirac fields

For several Dirac fields $\psi_f$ with charges $q_f=eQ_f$, the natural generalization is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\sum_f\bar\psi_f(i\gamma^\mu D_\mu^{(f)}-m_f)\psi_f,
$$

where

$$
D_\mu^{(f)}=\partial_\mu+iq_fA_\mu.
$$

The total electromagnetic current is

$$
j^\mu=\sum_f q_f\bar\psi_f\gamma^\mu\psi_f.
$$

In pure QED, the allowed charges are input parameters. In the Standard Model, the values of electric charge are not arbitrary independent decorations: they follow from weak isospin and hypercharge after electroweak symmetry breaking,

$$
Q=T^3+Y.
$$

That is why this chapter treats QED first but does not treat the pattern of particle charges as the final word.

## What makes spinor QED different from scalar QED?

Scalar QED and spinor QED are governed by the same Abelian gauge principle, but their interaction structures differ.

For a complex scalar,

$$
(D_\mu\phi)^\dagger D^\mu\phi
$$

contains both a one-photon current coupling and a two-photon seagull term. The seagull appears because the scalar kinetic term is quadratic in the covariant derivative.

For a Dirac spinor,

$$
\bar\psi i\gamma^\mu D_\mu\psi
$$

is first order in the covariant derivative. Therefore minimal spinor QED has a one-photon vertex but no elementary two-photon seagull vertex. Multi-photon interactions involving a fermion line appear through multiple insertions of the one-photon vertex, not through a direct local $A^2\bar\psi\psi$ term.

This difference is responsible for many small differences in scalar and spinor QED calculations, including Ward-identity bookkeeping, vacuum polarization numerators, and low-energy effective photon interactions.

## Common pitfalls

**Mixing charge conventions.** In this volume, $D_\mu=\partial_\mu+iqA_\mu$. The electron has $q=-e$. Therefore the electron-photon vertex is $+ie\gamma^\mu$. If you compare with a book using $D_\mu=\partial_\mu+ieA_\mu$ for the electron, translate before comparing signs.

**Forgetting that $\bar\psi$ transforms oppositely.** Since $\psi\mapsto e^{-iq\lambda}\psi$, the adjoint transforms as $\bar\psi\mapsto\bar\psi e^{iq\lambda}$. This is why $\bar\psi\psi$ and $\bar\psi\gamma^\mu\psi$ are gauge invariant.

**Calling $\psi(x)$ an observable.** The local Dirac field is gauge covariant, not gauge invariant. It is the right variable for gauge-fixed perturbation theory, but local gauge-invariant observables are built from neutral combinations, field strengths, currents, or appropriately dressed charged objects.

**Thinking the Dirac mass always respects gauge symmetry.** A vectorlike Dirac mass $m\bar\psi\psi$ respects $U(1)$ gauge symmetry only when the left- and right-handed components have the same charge. Chiral gauge theories are more restrictive.

**Dropping the sign in the source term.** The source form is $-j^\mu A_\mu$ with $j^\mu=q\bar\psi\gamma^\mu\psi$. The electron current is negative, so the electron interaction term has a plus sign in this convention.

**Treating the vertex Ward check as the full Ward identity.** The identity $k_\mu\gamma^\mu=S^{-1}(p+k)-S^{-1}(p)$ is the local algebraic seed. The full Ward–Takahashi identity is a statement about Green functions, contact terms, and renormalization.

## Relations to other pages

This page is the spin-one-half companion to [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/). Together they show how the same $U(1)$ gauge field couples to the two most important matter types.

The next page, [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/), collects the photon, spinor, optional scalar, gauge-fixing, and counterterm pieces into one reusable reference. Later QED pages use the vertex and current conventions from this page when deriving the photon propagator, QED vertices, Ward–Takahashi identity, vacuum polarization, and running electric charge.

The electroweak chapter revisits spinor gauge couplings in a chiral setting. There the left-handed and right-handed fermions need not transform the same way, and ordinary mass terms are replaced by Yukawa couplings to the Higgs doublet.

## Research status

The local spinor-QED Lagrangian and its Ward identities are established textbook physics. Perturbative QED is one of the best tested quantum field theories, and the electron-photon coupling is the canonical example of a renormalized gauge interaction.

The deeper structure of charged states in theories with massless photons is subtler than the local Lagrangian suggests. Exclusive S-matrix elements with charged particles suffer from infrared divergences, and physically meaningful charged sectors require inclusive observables, dressed asymptotic states, or related infrared-safe frameworks. Those issues do not change the Lagrangian on this page, but they do change the interpretation of charged-particle scattering states.

## Exercises

### Exercise 1: Covariance of the Dirac derivative

Show that if

$$
\psi\mapsto e^{-iq\lambda}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\lambda,
$$

then $D_\mu\psi=(\partial_\mu+iqA_\mu)\psi$ transforms as

$$
D_\mu\psi\mapsto e^{-iq\lambda}D_\mu\psi.
$$

<details><summary><strong>Solution</strong></summary>

Compute directly:

$$
\begin{aligned}
D_\mu'\psi'
&=(\partial_\mu+iqA_\mu+iq\partial_\mu\lambda)(e^{-iq\lambda}\psi)\\
&=e^{-iq\lambda}\partial_\mu\psi-iq(\partial_\mu\lambda)e^{-iq\lambda}\psi
+iqA_\mu e^{-iq\lambda}\psi
+iq(\partial_\mu\lambda)e^{-iq\lambda}\psi\\
&=e^{-iq\lambda}(\partial_\mu+iqA_\mu)\psi\\
&=e^{-iq\lambda}D_\mu\psi.
\end{aligned}
$$

The two terms involving $\partial_\mu\lambda$ cancel.

</details>

### Exercise 2: Current conservation from the equations of motion

Using

$$
(i\gamma^\mu D_\mu-m)\psi=0,
\qquad
i(D_\mu\bar\psi)\gamma^\mu+m\bar\psi=0,
$$

prove that $j^\mu=q\bar\psi\gamma^\mu\psi$ is conserved.

<details><summary><strong>Solution</strong></summary>

Because the connection terms cancel inside the gauge-invariant bilinear,

$$
\partial_\mu(\bar\psi\gamma^\mu\psi)
=(D_\mu\bar\psi)\gamma^\mu\psi+\bar\psi\gamma^\mu D_\mu\psi.
$$

From the adjoint equation,

$$
(D_\mu\bar\psi)\gamma^\mu=i m\bar\psi,
$$

because $i(D_\mu\bar\psi)\gamma^\mu=-m\bar\psi$. From the Dirac equation,

$$
\gamma^\mu D_\mu\psi=-im\psi,
$$

because $i\gamma^\mu D_\mu\psi=m\psi$. Therefore

$$
\partial_\mu(\bar\psi\gamma^\mu\psi)
=im\bar\psi\psi-im\bar\psi\psi=0.
$$

Multiplying by the constant charge $q$ gives $\partial_\mu j^\mu=0$.

</details>

### Exercise 3: The elementary Ward check

Let a photon of momentum $k$ attach to a fermion line whose momentum changes from $p$ to $p+k$. Show that contracting the spinor-QED vertex with $k_\mu$ gives a difference of inverse fermion propagators.

<details><summary><strong>Solution</strong></summary>

The vertex is $-iq\gamma^\mu$, so

$$
k_\mu(-iq\gamma^\mu)=-iqk\!\!\!/.
$$

But

$$
k\!\!\!/
=(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

Therefore

$$
k_\mu(-iq\gamma^\mu)
=-iq\left[(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)\right].
$$

The bracketed terms are inverse Dirac operators. When inserted between neighboring fermion propagators, they cancel those propagators. On external on-shell spinors, they vanish by the free Dirac equation.

</details>

## References

- Srednicki, *Quantum Field Theory*, §58, for spinor electrodynamics in a compact perturbative-QFT sequence.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8, 10, 13, and 14, for gauge invariance, Dirac spinors, QED Feynman rules, and path-integral Ward–Takahashi identities.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on electromagnetic interactions, functional integration, Faddeev–Popov, Ward identities, and QED renormalization.
- Zee, *Quantum Field Theory in a Nutshell*, for a physically motivated route through Dirac fields, gauge invariance, and QED.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic treatment of charged spin-one-half fields, QED amplitudes, renormalization, and infrared structure.

## Version history

- **2026-06-17:** Initial polished draft of the Spinor QED page.
