---
title: "Ward Identity in QED"
description: "Model calculation deriving the Ward–Takahashi identity in QED from local gauge invariance and checking its momentum-space consequences."
sidebar:
  label: "Ward Identity in QED"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§67–68; Schwartz §§8.4, 14.8, 19.5; Coleman QFT Lectures chs. 5–6; Weinberg Vol. I Ch. 10."
topics:
  - Ward identity
  - QED
  - Ward–Takahashi identity
  - current conservation
  - gauge invariance
  - vertex function
canonicalTopics:
  - ward-identity
  - ward-takahashi-identity
  - qed-current
  - vertex-renormalization
researchStatus:
  established:
    - "The QED Ward–Takahashi identity is a standard consequence of gauge invariance and is central to charge conservation and the equality of vertex and wavefunction renormalization."
  active:
    - "The same logic generalizes to non-Abelian Slavnov–Taylor identities, anomalous currents, background-field methods, and modern symmetry-defect Ward identities."
---

## Summary

This page derives the Ward identity in QED as a model calculation. The starting point is the conserved vector current

$$
j^\mu(x)=q\,\overline\psi(x)\gamma^\mu\psi(x),
$$

for the global phase symmetry of the Dirac field. In QED the same current couples to the photon, and local gauge invariance upgrades current conservation into identities among correlation functions.

The basic position-space Ward–Takahashi identity for the fermion two-point function with one current insertion is

$$
\partial_\mu^x
\left\langle T\,j^\mu(x)\psi(y)\overline\psi(z)\right\rangle
=
-q\,\delta^{(d)}(x-y)
\left\langle T\,\psi(y)\overline\psi(z)\right\rangle
+
q\,\delta^{(d)}(x-z)
\left\langle T\,\psi(y)\overline\psi(z)\right\rangle.
$$

The right-hand side is the contact-term record of the fact that the current insertion generates the charge of the fields it crosses.

After Fourier transform and amputation, the identity becomes

$$
k_\mu\Gamma^\mu(p+k,p)
=
q\left[S^{-1}(p+k)-S^{-1}(p)\right],
$$

where $S(p)$ is the full fermion propagator and $\Gamma^\mu$ is the one-particle-irreducible current vertex. In the zero-momentum limit,

$$
\Gamma^\mu(p,p)=q\,\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

This is the practical identity behind the familiar QED statement $Z_1=Z_2$: the charge vertex and fermion wavefunction renormalization are not independent.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Flowchart of the QED Ward identity: local phase rotation, variation of action, contact terms, Fourier transform, vertex identity.](/figures/symmetry-anomalies-topology/qed-ward-identity-flow.svg)

<figcaption>

The QED Ward identity is the local version of charge conservation. A local phase rotation produces a current-divergence term from the action and contact terms from charged insertions; after amputation this becomes the momentum-space Ward–Takahashi identity.

</figcaption>
</figure>

## Prerequisites

You should know the Dirac Noether current, the meaning of a time-ordered correlation function, and the distinction between a connected correlator and a one-particle-irreducible vertex. It helps to know the QED covariant derivative convention used in this volume,

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

so that

$$
\overline\psi i\gamma^\mu D_\mu\psi
=
\overline\psi i\gamma^\mu\partial_\mu\psi
-
A_\mu j^\mu.
$$

The photon therefore couples to the current by $-A_\mu j^\mu$ in the Lorentzian Lagrangian. If another page or source uses $D_\mu=\partial_\mu-iqA_\mu$, the displayed signs of the current vertex must be translated.

## Setup and conventions

Work in mostly-minus signature. The QED action is

$$
S_{\rm QED}
=
\int d^dx\,
\left[
-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi
\right],
$$

with

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

The gauge transformation is

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
\overline\psi(x)\mapsto \overline\psi(x)e^{iq\alpha(x)},
$$

and

$$
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

The gauge field is dynamical in QED, but the Ward identity can be understood first as a statement about the global current and then as a consequence of invariance under local changes of variables. Gauge fixing complicates the photon sector, but the fermion-current Ward identity below survives in the usual gauge-fixed formulation because it expresses the residual consequence of gauge invariance.

:::note[Convention-sensitive source note]
Some textbooks define the electron charge as $-e$ and write $D_\mu=\partial_\mu+ieA_\mu$ for the electron field. Here $q$ is the charge appearing in $\psi\mapsto e^{-iq\alpha}\psi$. The identity is invariant in content, but signs in the current and photon vertex follow this choice.
:::

## Core idea

A Ward identity is a symmetry statement inside a correlation function. For a continuous global symmetry, current conservation away from insertions is not the whole story. When the current passes through charged operators, it produces contact terms.

For QED, the current insertion satisfies

$$
\partial_\mu j^\mu(x)=0
$$

away from charged fields, but inside

$$
\left\langle T\,j^\mu(x)\psi(y)\overline\psi(z)\right\rangle
$$

the divergence has delta-function support at $x=y$ and $x=z$. Those contact terms are not optional details. They are exactly what makes the current generate the charge of $\psi$ and $\overline\psi$.

Momentum-space Ward identities are the same information after Fourier transform. The divergence turns into contraction by the current momentum $k_\mu$. Contact terms collapse one propagator and become inverse propagators after amputation.

## Step 1: The global vector current

For the free Dirac Lagrangian

$$
\mathcal L=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi,
$$

the global phase transformation

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto\overline\psi e^{iq\alpha}
$$

has Noether current

$$
j^\mu=q\,\overline\psi\gamma^\mu\psi.
$$

Using the equations of motion,

$$
(i\gamma^\mu\partial_\mu-m)\psi=0,
$$

and

$$
i(\partial_\mu\overline\psi)\gamma^\mu+m\overline\psi=0,
$$

one finds

$$
\partial_\mu j^\mu
=
q(\partial_\mu\overline\psi)\gamma^\mu\psi
+
q\overline\psi\gamma^\mu\partial_\mu\psi
=0.
$$

This is the classical conservation law. The Ward identity is the quantum correlation-function version of this statement, including contact terms.

## Step 2: Local phase rotation in the path integral

Consider the time-ordered two-point function

$$
G(y,z)=\left\langle T\,\psi(y)\overline\psi(z)\right\rangle.
$$

Make an infinitesimal change of variables in the path integral,

$$
\delta\psi(x)=-iq\alpha(x)\psi(x),
\qquad
\delta\overline\psi(x)=iq\alpha(x)\overline\psi(x).
$$

For the vector symmetry of QED, the fermionic measure is invariant. The variation of the action under the local version of the transformation is

$$
\delta S
=
-\int d^dx\,\alpha(x)\partial_\mu j^\mu(x),
$$

after integrating by parts and dropping boundary terms.

The insertion also varies:

$$
\delta\bigl(\psi(y)\overline\psi(z)\bigr)
=
-iq\alpha(y)\psi(y)\overline\psi(z)
+
iq\alpha(z)\psi(y)\overline\psi(z).
$$

A change of variables in the path integral cannot change the integral. Therefore

$$
0
=
i\langle \delta S\,T\psi(y)\overline\psi(z)\rangle
+
\langle T\,\delta(\psi(y)\overline\psi(z))\rangle.
$$

Since $\alpha(x)$ is arbitrary, the coefficient of $\alpha(x)$ gives

$$
\partial_\mu^x
\left\langle T\,j^\mu(x)\psi(y)\overline\psi(z)\right\rangle
=
-q\,\delta^{(d)}(x-y)
\left\langle T\,\psi(y)\overline\psi(z)\right\rangle
+
q\,\delta^{(d)}(x-z)
\left\langle T\,\psi(y)\overline\psi(z)\right\rangle.
$$

This is the position-space Ward–Takahashi identity.

:::note[Contact-term source note]
The relative signs of the two delta functions are fixed by the opposite charges of $\psi$ and $\overline\psi$. If the transformation of $\psi$ is written with the opposite phase, the two signs flip together.
:::

## Step 3: Fourier transform

Define the full fermion propagator by

$$
\left\langle T\,\psi(y)\overline\psi(z)\right\rangle
=
\int\frac{d^dp}{(2\pi)^d}\,
e^{-ip\cdot(y-z)}\,iS(p),
$$

where $S(p)$ includes interactions. The exact placement of factors of $i$ is convention-dependent; the final amputated identity is the cleanest statement.

For the three-point function with current momentum $k$, write schematically

$$
G^\mu(p+k,p)
=
S(p+k)\,\Gamma^\mu(p+k,p)\,S(p),
$$

where $\Gamma^\mu$ is the amputated current vertex, including the charge normalization. Contracting with $k_\mu$ and using the position-space identity gives

$$
k_\mu G^\mu(p+k,p)
=
q\left[S(p)-S(p+k)\right],
$$

up to the same overall $i$ convention used in defining $G^\mu$ and $S$. Multiplying by inverse propagators on the left and right gives the convention-independent structural identity

$$
k_\mu\Gamma^\mu(p+k,p)
=
q\left[S^{-1}(p+k)-S^{-1}(p)\right].
$$

At tree level,

$$
S_0^{-1}(p)=p\!\!\!/-m,
\qquad
\Gamma_0^\mu=q\gamma^\mu.
$$

The identity becomes

$$
k_\mu q\gamma^\mu
=
q\left[(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)\right]
=
q\,k\!\!\!/,
$$

which checks immediately.

## Step 4: Zero-momentum limit and Z₁ equals Z₂

Take $k\to0$ in

$$
k_\mu\Gamma^\mu(p+k,p)
=
q\left[S^{-1}(p+k)-S^{-1}(p)\right].
$$

Expanding to first order in $k$ gives

$$
\Gamma^\mu(p,p)
=
q\,\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

This is the differential Ward identity. It says that the zero-momentum current vertex is determined by the momentum dependence of the inverse fermion propagator.

In perturbative renormalization, write the bare and renormalized fields schematically as

$$
\psi_0=Z_2^{1/2}\psi,
$$

and the photon–fermion vertex renormalization as $Z_1$. Gauge invariance forces

$$
Z_1=Z_2
$$

in QED. This equality is one of the most useful practical consequences of the Ward identity: charge renormalization is controlled by the photon field renormalization rather than by an independent vertex counterterm.

:::caution[What this does not say]
The equality $Z_1=Z_2$ is special to Abelian QED-like Ward identities. Non-Abelian gauge theories have Slavnov–Taylor identities, ghost fields, and more elaborate relations among renormalization constants.
:::

## Step 5: Ward identity for external photons

The same logic implies a simple check on scattering amplitudes with external photons. Replacing the polarization vector of an external photon by its momentum gives zero for a gauge-invariant physical amplitude:

$$
\varepsilon_\mu(k)\mathcal M^\mu=0
\quad\Longrightarrow\quad
k_\mu\mathcal M^\mu=0.
$$

This is often called a Ward identity too. It is closely related to the current Ward identity but is usually applied as a practical amplitude check. In perturbative QED, it is the reason unphysical photon polarizations decouple from physical S-matrix elements.

For example, in a tree-level amplitude with a photon attached to all possible charged external legs, the pieces proportional to $k_\mu$ cancel after using charge conservation and the Dirac equations for external spinors.

## Common pitfalls

**Dropping contact terms.** The divergence of a current is zero away from insertions. Inside a time-ordered correlator, charged insertions produce delta-function contact terms.

**Confusing global current conservation with gauge redundancy.** The Ward identity may be derived from gauge invariance in QED, but the current whose insertion appears here is the physical electric current. Gauge transformations are redundancies; the global electric charge is physical.

**Forgetting amputations.** The identity for the three-point Green function and the identity for the one-particle-irreducible vertex differ by external propagators. The clean form with inverse propagators is the amputated version.

**Using the photon vertex sign as the current vertex sign.** With $D_\mu=\partial_\mu+iqA_\mu$, the interaction is $-A_\mu j^\mu$, so the Feynman vertex for a photon is not the same object as the current insertion $\Gamma^\mu$ without tracking factors of $i$ and signs.

**Assuming QED identities generalize trivially to Yang–Mills theory.** Non-Abelian gauge fixing introduces ghosts and BRST symmetry. The corresponding relations are Slavnov–Taylor identities.

## Relations to other pages

[Noether Current for a Dirac Field](/symmetry-anomalies-topology/model-calculation-library/noether-current-for-dirac-field/) derives the current used here. The Noether Currents and Ward Identities chapter gives the general current-insertion formalism. Background Fields and Gauging explains the same identity in source language.

This page is also a bridge to the Anomalies chapter. Vector QED has a nonanomalous gauge current, but the axial current of a massless Dirac fermion can have an anomalous Ward identity after coupling to gauge fields.

## Research status

The QED Ward–Takahashi identity is settled textbook physics. Its perturbative and nonperturbative versions are basic consistency conditions on QED.

The broader idea remains central in active research: gauge symmetry leads to Slavnov–Taylor identities in non-Abelian gauge theory, background gauge invariance constrains effective actions, generalized symmetries have defect Ward identities, and anomalies appear precisely as controlled failures of Ward identities.

## Exercises

### Exercise 1: Contact terms from charges

Assume

$$
[Q,\psi]=-q\psi,
\qquad
[Q,\overline\psi]=q\overline\psi.
$$

Explain why the two contact terms in

$$
\partial_\mu^x
\langle T\,j^\mu(x)\psi(y)\overline\psi(z)\rangle
$$

come with opposite signs.

<details><summary><strong>Solution</strong></summary>

The current divergence generates the infinitesimal charge action at the insertion point. Since $\psi$ has charge $q$ in the convention $[Q,\psi]=-q\psi$ while $\overline\psi$ has the opposite charge, crossing the current through $\psi$ and crossing it through $\overline\psi$ produce opposite variations. This gives delta functions at $x=y$ and $x=z$ with opposite signs.

</details>

### Exercise 2: Tree-level Ward identity

Check that

$$
k_\mu\Gamma_0^\mu(p+k,p)
=
q\left[S_0^{-1}(p+k)-S_0^{-1}(p)\right]
$$

using

$$
\Gamma_0^\mu=q\gamma^\mu,
\qquad
S_0^{-1}(p)=p\!\!\!/-m.
$$

<details><summary><strong>Solution</strong></summary>

The left-hand side is

$$
k_\mu q\gamma^\mu=q\,k\!\!\!/.
$$

The right-hand side is

$$
q\left[(p\!\!\!/+k\!\!\!/-m)-(p\!\!\!/-m)\right]
=q\,k\!\!\!/.
$$

The two sides agree.

</details>

### Exercise 3: Zero-momentum limit

Starting from

$$
k_\mu\Gamma^\mu(p+k,p)
=
q\left[S^{-1}(p+k)-S^{-1}(p)\right],
$$

derive

$$
\Gamma^\mu(p,p)=q\,\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

<details><summary><strong>Solution</strong></summary>

Expand both sides to first order in $k$:

$$
S^{-1}(p+k)-S^{-1}(p)
=
k_\mu\frac{\partial S^{-1}(p)}{\partial p_\mu}
+O(k^2).
$$

Also,

$$
k_\mu\Gamma^\mu(p+k,p)
=
k_\mu\Gamma^\mu(p,p)+O(k^2).
$$

Equating the linear terms in arbitrary $k_\mu$ gives

$$
\Gamma^\mu(p,p)=q\,\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

</details>

### Exercise 4: Why anomalies would break the derivation

Where would the derivation fail if the fermion measure were not invariant under the local change of variables?

<details><summary><strong>Solution</strong></summary>

The change-of-variables argument assumes that the path-integral measure is invariant. If

$$
\mathcal D\psi\,\mathcal D\overline\psi
$$

acquires a nontrivial Jacobian, then an extra term appears in the Ward identity. This extra term is the anomaly. For the vector current in ordinary QED the gauge-invariant regulator preserves the identity, but for the axial current the fermion measure produces the familiar chiral anomaly after coupling to gauge fields.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§67–68, for Ward identities in QED.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, §§8.4, 14.8, and 19.5, for Ward identities, Ward–Takahashi identities, and $Z_1=Z_2$.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6, for symmetries, currents, and conservation laws.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, for the operator and Green-function perspective on QED identities.
- Kazuo Fujikawa and Hiroshi Suzuki, *Path Integrals and Quantum Anomalies*, for the measure-based viewpoint that explains how anomalous Ward identities arise.

## Version history

- **2026-06-23:** Initial polished draft. Derived the position-space Ward identity, momentum-space Ward–Takahashi identity, zero-momentum vertex identity, and $Z_1=Z_2$ consequence with explicit convention notes.
