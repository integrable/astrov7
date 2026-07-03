---
title: "Ward–Takahashi Identity"
description: "Derives and interprets the QED Ward–Takahashi identity, connecting current conservation, off-shell Green functions, on-shell photon gauge invariance, and charge renormalization."
sidebar:
  label: "Ward–Takahashi Identity"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§67–68; Schwartz §14.8 and §19.5; Coleman lectures on Ward identities and QED renormalization; Weinberg Vol. I QED chapters."
topics:
  - Ward–Takahashi identity
  - Ward identity
  - QED
  - current conservation
  - charge renormalization
canonicalTopics:
  - ward-takahashi-identity
  - ward-identity
  - qed-renormalization
  - current-conservation
researchStatus:
  established:
    - "The QED Ward–Takahashi identity is an exact consequence of local Abelian gauge symmetry, assuming a gauge-invariant regularization or appropriate symmetry-restoring counterterms."
  active:
    - "Infrared dressings, asymptotic symmetries, boundary conditions, and precision multi-loop implementations refine how Ward identities are used in modern QED calculations."
---

## Summary

The Ward–Takahashi identity is the exact QED relation expressing local $U(1)$ gauge symmetry in correlation functions. For spinor QED, write the exact fermion propagator as

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)},
\qquad
\mathcal S_0^{-1}(p)=p\!\!\!/-m,
$$

and write the exact proper photon–fermion vertex factor as

$$
-iq\Gamma^\mu(p+k,p),
\qquad
\Gamma_0^\mu=\gamma^\mu.
$$

Then the amputated Ward–Takahashi identity is

$$
\boxed{
 k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p)
}
$$

in the normalization where the charge factor $q$ is kept outside $\Gamma^\mu$. At tree level this reduces to the elementary identity

$$
k_\mu\gamma^\mu
=
(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m).
$$

The same principle has three crucial consequences:

$$
\begin{aligned}
&\text{external photon Ward identity:}
&&k_\mu\mathcal M^\mu=0,\\
&\text{vacuum-polarization transversality:}
&&k_\mu\Pi^{\mu\nu}(k)=0,\\
&\text{spinor-QED renormalization:}
&&Z_1=Z_2.
\end{aligned}
$$

So the Ward–Takahashi identity is not one more optional identity to memorize. It is the mechanism by which gauge redundancy prevents unphysical photon polarizations, relates vertex and propagator renormalization, and protects electric charge conservation.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Diagrammatic form of the Ward–Takahashi identity: contracting the photon vertex with its momentum gives the difference of inverse fermion propagators.](/figures/gauge-theories-standard-model/ward-takahashi-identity.svg)

<figcaption>

The spinor-QED Ward–Takahashi identity says that contracting the exact photon–fermion vertex with the photon momentum turns the current insertion into the difference of inverse fermion two-point functions. On external on-shell legs this difference vanishes; inside a diagram it cancels neighboring propagators and organizes gauge-invariance cancellations.

</figcaption>
</figure>

## Prerequisites

You should read [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) and [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) first. This page uses the spinor-QED convention

$$
\mathcal L_{\mathrm{int}}
=-qA_\mu\bar\psi\gamma^\mu\psi,
\qquad
\psi\mapsto e^{-iq\lambda}\psi,
$$

so the tree-level photon–fermion vertex factor is $-iq\gamma^\mu$.

You should also know that in scalar QED the one-photon scalar vertex and two-photon seagull vertex must be kept together. Scalar QED obeys analogous Ward–Takahashi identities, but the spinor identity is the cleanest place to see the central mechanism.

## Core idea

Current conservation says

$$
\partial_\mu j^\mu=0.
$$

In a quantum field theory this equation is true inside correlation functions only with care. When $\partial_\mu j^\mu(x)$ collides with a charged operator at the same point, there are contact terms. Those contact terms are not annoying debris; they are the Ward–Takahashi identity.

For QED, the identity says that inserting the divergence of the electromagnetic current into a correlator is equivalent to summing over the electric charges of the operators in the correlator. In momentum space, after amputating external fermion propagators, that statement becomes

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

Thus, when a photon momentum flows into a charged line, it measures the difference between the inverse charged-particle propagator on the two sides of the insertion. On shell the inverse propagator vanishes. Off shell it cancels adjacent propagators. That is the whole magic trick, except the magic is just local symmetry refusing to let you cheat.

## Setup and conventions

The spinor-QED Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Expanding the covariant derivative gives

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
$$

The electromagnetic current is

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

For the exact fermion two-point function, we use

$$
S(p)=\frac{i}{\mathcal S^{-1}(p)}.
$$

At tree level,

$$
\mathcal S_0^{-1}(p)=p\!\!\!/-m.
$$

The exact proper photon–fermion vertex is normalized by

$$
\text{vertex factor}=-iq\Gamma^\mu(p+k,p),
$$

so at tree level $\Gamma^\mu=\gamma^\mu$. With these definitions the Ward–Takahashi identity has no extra charge on the right-hand side. If instead one defines a current-insertion vertex with the charge included, $q\Gamma^\mu$, both sides are multiplied by $q$.

## The current-divergence identity

Under an infinitesimal local $U(1)$ transformation,

$$
\delta\psi=-iq\alpha(x)\psi,
\qquad
\delta\bar\psi=+iq\alpha(x)\bar\psi,
$$

and

$$
\delta A_\mu=\partial_\mu\alpha.
$$

In the path integral, changing variables by this symmetry does not change the integral. When charged fields are inserted, their variations produce contact terms. Schematically,

$$
\partial_\mu\langle T j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
\sum_i \text{contact term at }x=x_i.
$$

For a two-point function with one $\psi$ and one $\bar\psi$, this takes the form

$$
\partial_\mu\langle T j^\mu(x)\psi(y)\bar\psi(z)\rangle
=
-q\delta^{(4)}(x-y)\langle T\psi(y)\bar\psi(z)\rangle
+q\delta^{(4)}(x-z)\langle T\psi(y)\bar\psi(z)\rangle,
$$

up to the standard convention-dependent factors of $i$ associated with time-ordered Green functions. The signs reflect the fact that $\psi$ has charge $q$ but transforms as $e^{-iq\alpha}\psi$, while $\bar\psi$ transforms oppositely.

Fourier transforming and amputating the external fermion legs gives the compact proper-vertex identity

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p).
$$

This is the form to use in renormalization and diagrammatic checks.

:::note[Ward versus Ward–Takahashi]
In common language, “Ward identity” often means the on-shell amplitude statement $k_\mu\mathcal M^\mu=0$. “Ward–Takahashi identity” usually means the stronger off-shell correlation-function identity with contact terms. The second implies the first after LSZ reduction and on-shell limits.
:::

## Tree-level check

At tree level,

$$
\Gamma_0^\mu=\gamma^\mu,
\qquad
\mathcal S_0^{-1}(p)=p\!\!\!/-m.
$$

The Ward–Takahashi identity becomes

$$
k_\mu\gamma^\mu
=
(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m),
$$

which is simply

$$
k\!\!\!/=k\!\!\!/. 
$$

The identity is trivial at tree level because the Dirac vertex and the Dirac kinetic operator come from the same covariant derivative. The nontrivial statement is that the same relation survives quantum corrections, provided the theory is regulated and renormalized in a way compatible with gauge symmetry.

## From the Ward–Takahashi identity to the Ward identity

Consider a scattering amplitude with an external photon of momentum $k$ and polarization $\epsilon_\mu(k)$:

$$
\mathcal M=\epsilon_\mu(k)\mathcal M^\mu.
$$

Gauge invariance of the external photon requires

$$
\epsilon_\mu(k)\mapsto\epsilon_\mu(k)+c k_\mu
$$

not to change the physical amplitude. Equivalently,

$$
k_\mu\mathcal M^\mu=0.
$$

This follows from the Ward–Takahashi identity after LSZ reduction. The reason is the inverse-propagator structure. When the photon momentum contracts into a charged external line, the identity produces a factor such as

$$
\mathcal S^{-1}(p)u(p)=0
$$

or

$$
\bar u(p)\mathcal S^{-1}(p)=0
$$

on shell. When the contraction occurs inside a diagram, the inverse propagator cancels a neighboring propagator, and the resulting terms cancel against the same momentum insertion on adjacent charged-line segments.

For processes with several charged external legs, the sum over all insertions is proportional to total charge flow. Charge conservation then completes the cancellation.

## Longitudinal photons and gauge-parameter cancellation

The covariant-gauge photon propagator contains a longitudinal piece:

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

If a photon line connects two conserved currents $J^\mu$ and $J'^\nu$, then

$$
J^\mu k_\mu=0,
\qquad
k_\nu J'^\nu=0,
$$

and the longitudinal term contributes nothing:

$$
J^\mu
\left(k_\mu k_\nu\right)
J'^\nu
=(J\cdot k)(k\cdot J')=0.
$$

In full quantum amplitudes, the phrase “conserved current” should be understood through the Ward–Takahashi identity. Individual diagrams may contain longitudinal pieces; complete gauge-invariant sums do not leave physical answers depending on $\xi$.

## Vacuum-polarization transversality

The photon self-energy, or vacuum polarization, is defined by the one-particle-irreducible two-point function of the photon. Gauge invariance implies

$$
k_\mu\Pi^{\mu\nu}(k)=0.
$$

Lorentz invariance and transversality then force the tensor structure

$$
\Pi^{\mu\nu}(k)
=
\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2),
$$

up to conventions for the overall sign in the definition of $\Pi^{\mu\nu}$. This structure is one of the quickest checks of a QED loop calculation.

In scalar QED, the transversality check requires both the loop with two scalar–scalar–photon vertices and the seagull loop. In spinor QED, the one-loop fermion bubble is transverse after a gauge-invariant regularization such as dimensional regularization. A hard cutoff used carelessly can appear to violate transversality; the cure is not to abandon gauge symmetry but to regulate or renormalize in a symmetry-preserving way.

## Renormalization consequence: Z₁ equals Z₂

The Ward–Takahashi identity relates the exact vertex to the exact inverse propagator. Taking the limit $k\to0$ gives

$$
\Gamma^\mu(p,p)
=
\frac{\partial \mathcal S^{-1}(p)}{\partial p_\mu}.
$$

This says that the zero-momentum photon vertex is the momentum derivative of the inverse fermion propagator. Consequently, the divergent local part of the photon–fermion vertex is tied to the divergent local part of the fermion kinetic term.

In standard spinor-QED notation, this gives

$$
Z_1=Z_2,
$$

where $Z_1$ renormalizes the photon–fermion vertex and $Z_2$ renormalizes the fermion field. This equality is the reason charge renormalization in QED can be expressed through the photon field renormalization factor. Schematically, the bare and renormalized charges obey

$$
e_0=Z_3^{-1/2}e_R
$$

in standard Ward-identity-compatible conventions.

Do not overread this statement. $Z_1=Z_2$ is a QED Ward-identity result. Non-Abelian gauge theories have related but more intricate Slavnov–Taylor identities, because gauge bosons and ghosts also carry gauge charge.

## Scalar QED version

Scalar QED has analogous Ward–Takahashi identities, but their diagrammatic bookkeeping includes the seagull vertex. At the single one-photon vertex level,

$$
k_\mu\bigl[-iq(p+p')^\mu\bigr]
=-iq\left[(p'^2-m^2)-(p^2-m^2)\right].
$$

This mirrors the spinor identity: contraction with the photon momentum gives a difference of inverse scalar propagators.

However, when two photons interact with a scalar line, there is also the contact vertex

$$
2iq^2\eta^{\mu\nu}.
$$

The scalar Ward identities therefore relate the one-photon vertex, the seagull vertex, and the scalar propagator. This is why scalar-QED counterterms cannot be chosen independently if gauge invariance is to survive renormalization.

## Gauge invariance and regularization

The Ward–Takahashi identity is exact, but a calculation can obscure it. Regulators that preserve gauge invariance, such as dimensional regularization in ordinary perturbative QED, make the identity manifest or at least recoverable with gauge-invariant counterterms. Regulators that break gauge invariance can generate spurious terms, such as an apparent photon mass or a nontransverse vacuum polarization.

A useful diagnostic is the photon two-point function. A gauge-invariant renormalized QED cannot generate a photon mass term

$$
\frac12m_\gamma^2A_\mu A^\mu
$$

because it is not gauge invariant. Thus any calculation that produces an uncancelled photon mass in ordinary QED has either used a symmetry-breaking regulator without proper counterterms or dropped required diagrams.

The same warning appears more dramatically in chiral gauge theories. There the problem may not be a bad regulator but a real gauge anomaly. Vectorlike QED is anomaly-free as a gauge theory; the axial anomaly is a different statement about the axial current, not a violation of electromagnetic gauge invariance.

## Common pitfalls

**Confusing current conservation with absence of contact terms.** The current divergence vanishes away from operator insertions. At insertions of charged fields it produces contact terms, and those terms are exactly what make the Ward–Takahashi identity useful.

**Checking only external on-shell photons.** The on-shell Ward identity $k_\mu\mathcal M^\mu=0$ is important, but weaker than the off-shell Ward–Takahashi identity. Renormalization uses the off-shell identity.

**Forgetting inverse propagators.** Contracting a photon vertex with momentum does not simply give zero. It gives a difference of inverse propagators. It becomes zero only on shell or after cancellations inside a complete diagram.

**Dropping scalar seagulls.** In scalar QED, the seagull vertex is part of the Ward–Takahashi machinery. Omitting it breaks transversality of scalar-loop vacuum polarization and scalar Compton scattering.

**Letting the regulator decide the symmetry.** A regulator that violates gauge invariance may produce fake violations of Ward identities. The renormalized theory must satisfy the symmetry unless there is a genuine anomaly.

**Assuming the non-Abelian story is identical.** QED has Abelian Ward–Takahashi identities. Yang–Mills theory has Slavnov–Taylor identities involving ghosts, gauge-boson self-interactions, and BRST symmetry.

## Relations to other pages

- [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) gives the tree-level vertex rules whose contractions are the first Ward checks.
- [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) explains the gauge-dependent longitudinal pieces that Ward identities remove from physical amplitudes.
- [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/) shows why scalar Ward identities require the seagull interaction.
- Vacuum Polarization uses $k_\mu\Pi^{\mu\nu}=0$ as the structural constraint on the one-loop photon self-energy.
- Running Electric Charge uses Ward identities to isolate the physical charge renormalization controlled by photon vacuum polarization.
- Gauge Quantization later generalizes this logic to Faddeev–Popov ghosts, BRST symmetry, and Slavnov–Taylor identities.

## Research status

The Ward–Takahashi identity in vectorlike QED is established textbook material. Its modern importance lies in how it is implemented in demanding settings: high-order precision QED, infrared-safe inclusive observables, dressed charged states, finite-volume calculations, boundary conditions, and automated multiloop pipelines.

The identity is old; the ways people manage to accidentally violate it in calculations remain evergreen.

## Exercises

### Exercise 1: Tree-level Ward–Takahashi identity

Verify that the tree-level spinor-QED vertex satisfies

$$
k_\mu\gamma^\mu
=
\mathcal S_0^{-1}(p+k)-\mathcal S_0^{-1}(p),
$$

where $\mathcal S_0^{-1}(p)=p\!\!\!/-m$.

<details>
<summary><strong>Solution</strong></summary>

The right-hand side is

$$
(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)=k\!\!\!/.
$$

The left-hand side is

$$
k_\mu\gamma^\mu=k\!\!\!/. 
$$

They agree.

</details>

### Exercise 2: Longitudinal propagator between conserved currents

Show that the gauge-parameter-dependent part of the covariant-gauge photon propagator does not contribute between two conserved currents.

<details>
<summary><strong>Solution</strong></summary>

The gauge-dependent part is proportional to

$$
\frac{k_\mu k_\nu}{k^2+i\epsilon}.
$$

Inserted between currents, it gives

$$
J^\mu k_\mu k_\nu J'^\nu=(J\cdot k)(k\cdot J').
$$

If both currents are conserved in momentum space,

$$
k_\mu J^\mu=0,
\qquad
k_\nu J'^\nu=0,
$$

then the expression vanishes.

</details>

### Exercise 3: Zero-momentum vertex relation

Starting from

$$
k_\mu\Gamma^\mu(p+k,p)
=
\mathcal S^{-1}(p+k)-\mathcal S^{-1}(p),
$$

show that

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}
$$

provided the functions are smooth near $k=0$.

<details>
<summary><strong>Solution</strong></summary>

Expand both sides to first order in $k$:

$$
k_\mu\Gamma^\mu(p,p)+O(k^2)
=
k_\mu\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}+O(k^2).
$$

Since this holds for arbitrary infinitesimal $k_\mu$, the coefficients agree:

$$
\Gamma^\mu(p,p)=\frac{\partial\mathcal S^{-1}(p)}{\partial p_\mu}.
$$

</details>

### Exercise 4: Scalar single-vertex check

For scalar QED, use

$$
V^\mu(p',p)=-iq(p+p')^\mu,
\qquad
k=p'-p,
$$

to show that contracting the vertex with $k_\mu$ gives the difference of inverse scalar propagators.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
k_\mu V^\mu(p',p)
=-iq(p'-p)\cdot(p'+p)
=-iq(p'^2-p^2).
$$

Add and subtract $m^2$:

$$
-iq(p'^2-p^2)
=-iq\left[(p'^2-m^2)-(p^2-m^2)\right].
$$

Thus the contraction gives the difference of inverse free scalar operators, multiplied by $-iq$.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§67–68, for the LSZ-based Ward-identity argument and the proof of $Z_1=Z_2$ in QED.
- Schwartz, *Quantum Field Theory and the Standard Model*, §14.8 for the path-integral Ward–Takahashi identity and §19.5 for the renormalization consequence $Z_1=Z_2$.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, and QED renormalization.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for QED Ward identities, renormalization, and gauge-invariance constraints in the broader scattering framework.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, Chs. 7 and 10, for standard diagrammatic Ward-identity and QED-renormalization treatments.

## Version history

- **2026-06-17:** Initial polished draft. Connects QED vertices, external-photon Ward identities, off-shell Ward–Takahashi identities, vacuum-polarization transversality, and $Z_1=Z_2$.
