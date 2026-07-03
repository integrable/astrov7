---
title: "Weak Charged Current"
description: "Derives the W± charged-current interaction, its left-chiral structure, CKM mixing, vertex normalization, and low-energy Fermi limit."
sidebar:
  label: "Weak Charged Current"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§88–90; Schwartz Ch. 29; Weinberg Vol. II electroweak chapters."
topics:
  - weak charged current
  - W bosons
  - V minus A interaction
  - CKM matrix
  - Fermi theory
canonicalTopics:
  - charged-current
  - w-boson-coupling
  - left-chiral-weak-interaction
  - ckm-matrix
  - fermi-limit
researchStatus:
  established:
    - "In the minimal Standard Model, charged weak interactions are mediated by W± bosons and couple only to left-handed fermion doublets, with quark flavor mixing described by the CKM matrix."
  active:
    - "Precision tests of charged-current universality, CKM unitarity, semileptonic decays, and possible charged-current flavor anomalies remain active interfaces between electroweak theory and experiment."
---

## Summary

The weak charged current is the part of the electroweak interaction mediated by the charged gauge bosons $W^+$ and $W^-$. It is the interaction behind beta decay, muon decay, charged pion decay, and charged-current neutrino scattering.

In the convention of this volume,

$$
D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu,
$$

so the fermion kinetic term $i\bar\psi\gamma^\mu D_\mu\psi$ gives gauge interactions with an overall minus sign. The charged-current interaction is

$$
\mathcal L_{\rm cc}
=
-\frac{g}{\sqrt2}\left(
W_\mu^+j_{W^+}^\mu+W_\mu^-j_{W^-}^\mu
\right),
$$

where, in the quark and charged-lepton mass basis,

$$
j_{W^+}^\mu
=
\sum_\alpha \bar\nu_{\alpha L}\gamma^\mu e_{\alpha L}
+
\sum_{i,j}\bar u_{iL}\gamma^\mu V_{ij}d_{jL},
\qquad
j_{W^-}^\mu=(j_{W^+}^\mu)^\dagger.
$$

Here $V$ is the CKM matrix. The subscript on $j_{W^+}$ means “the current multiplying $W^+$,” not “the current has electric charge $+1$.” The product $W^+j_{W^+}$ is electromagnetically neutral.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Weak charged current map](/figures/gauge-theories-standard-model/weak-charged-current-map.svg)

<figcaption>

The charged weak current comes from the $SU(2)_L$ ladder generators. The $W^\pm$ bosons connect upper and lower members of left-handed doublets; in the quark mass basis this introduces the CKM matrix. At low momentum transfer, $W$ exchange becomes a local four-fermion interaction with $G_F/\sqrt2=g^2/(8m_W^2)$.

</figcaption>
</figure>

The key phrase is: **charged weak currents are left-chiral ladder interactions**. The $W$ bosons do not couple democratically to all Dirac fermions. They couple to fields that transform as left-handed $SU(2)_L$ doublets.

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/), [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/), and [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/).

You should also be comfortable with the chiral projectors

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
$$

and with the minimal Standard Model assignment that left-handed fermions are weak doublets while right-handed charged fermions are weak singlets.

## Core idea

Charged currents are the observable imprint of the off-diagonal generators of $SU(2)_L$. For a doublet

$$
\Psi_L=
\begin{pmatrix}
\psi_u\\
\psi_d
\end{pmatrix}_L,
$$

define

$$
T^+=T^1+iT^2,
\qquad
T^-=T^1-iT^2.
$$

In the fundamental representation,

$$
T^+
=
\begin{pmatrix}
0&1\\
0&0
\end{pmatrix},
\qquad
T^-
=
\begin{pmatrix}
0&0\\
1&0
\end{pmatrix}.
$$

Thus

$$
\bar\Psi_L\gamma^\mu T^+\Psi_L
=
\bar\psi_{uL}\gamma^\mu\psi_{dL},
\qquad
\bar\Psi_L\gamma^\mu T^-\Psi_L
=
\bar\psi_{dL}\gamma^\mu\psi_{uL}.
$$

The charged gauge fields are the matching combinations

$$
W_\mu^+=\frac{1}{\sqrt2}(W_\mu^1-iW_\mu^2),
\qquad
W_\mu^-=\frac{1}{\sqrt2}(W_\mu^1+iW_\mu^2).
$$

Then

$$
W_\mu^1T^1+W_\mu^2T^2
=
\frac{1}{\sqrt2}\left(W_\mu^+T^+ + W_\mu^-T^-\right).
$$

This identity is the entire algebraic origin of the charged-current normalization.

## Setup and conventions

For a left-handed doublet $\Psi_L$, the weak part of the kinetic term contains

$$
i\bar\Psi_L\gamma^\mu D_\mu\Psi_L
\supset
-g\bar\Psi_L\gamma^\mu W_\mu^aT^a\Psi_L.
$$

The charged part is therefore

$$
\mathcal L_{\rm cc}(\Psi_L)
=
-\frac{g}{\sqrt2}
\left(
W_\mu^+\bar\Psi_L\gamma^\mu T^+\Psi_L
+
W_\mu^-\bar\Psi_L\gamma^\mu T^-\Psi_L
\right).
$$

Right-handed charged fermions are weak-isospin singlets in the minimal Standard Model. Since $T^\pm=0$ on singlets, there is no minimal Standard Model right-handed charged-current gauge coupling.

## Leptonic charged current

For each charged-lepton generation,

$$
L_\alpha=
\begin{pmatrix}
\nu_\alpha\\
e_\alpha
\end{pmatrix}_L,
\qquad
\alpha=e,\mu,\tau.
$$

The leptonic charged current is

$$
j_{W^+}^{\mu,\ell}
=
\sum_{\alpha=e,\mu,\tau}
\bar\nu_{\alpha L}\gamma^\mu e_{\alpha L},
\qquad
j_{W^-}^{\mu,\ell}
=
\sum_{\alpha=e,\mu,\tau}
\bar e_{\alpha L}\gamma^\mu \nu_{\alpha L}.
$$

For example, the $W^-$ term contains

$$
-\frac{g}{\sqrt2}W_\mu^-\bar e_L\gamma^\mu\nu_{eL},
$$

which is one of the vertices used in muon decay,

$$
\mu^-\to e^-\bar\nu_e\nu_\mu.
$$

In the minimal Standard Model with massless neutrinos, one can choose the lepton flavor basis so the leptonic charged current is diagonal. Once neutrino masses are included, the charged-current lepton interaction contains the PMNS matrix in the neutrino mass basis. That mixing is developed in the Flavor and Neutrinos chapter.

## Quark charged current and CKM mixing

Before diagonalizing Yukawa matrices, the weak-basis quark doublets are

$$
Q_i'=
\begin{pmatrix}
u_i'\\ d_i'\end{pmatrix}_L.
$$

Here the symbol $u_i'$ denotes an up-type weak-basis quark, not a neutrino. The left-handed up- and down-type quarks are independently rotated to diagonalize the mass matrices:

$$
u_L'=U_{uL}u_L,
\qquad
d_L'=U_{dL}d_L.
$$

Written less compactly, $u_L$ is the column vector $(u_L,c_L,t_L)^T$, and $d_L$ is the column vector $(d_L,s_L,b_L)^T$. Only the relative left-handed rotation appears in the charged current:

$$
V=U_{uL}^\dagger U_{dL}.
$$

Thus the quark charged current in the mass basis is

$$
j_{W^+}^{\mu,q}
=
\sum_{i,j}\bar u_{iL}\gamma^\mu V_{ij}d_{jL},
\qquad
j_{W^-}^{\mu,q}
=
\sum_{i,j}\bar d_{jL}\gamma^\mu V_{ij}^*u_{iL}.
$$

:::note[Why mixing appears here]
The charged current connects the upper and lower components of an $SU(2)_L$ doublet. Because the up-type and down-type Yukawa matrices are not generally diagonalized by the same left-handed rotation, the $W$ interaction is not diagonal in the quark mass basis.
:::

The CKM matrix is unitary in the three-generation Standard Model. Its off-diagonal entries are why a $W$ can couple an up quark to a strange quark, or a charm quark to a down quark, with amplitudes proportional to the corresponding CKM elements.

## Vertex rule and chiral projector

In four-component notation, the $W^+$ vertex coupling an up-type fermion to a down-type fermion is proportional to

$$
-i\frac{g}{\sqrt2}\gamma^\mu P_L.
$$

For quarks, include the CKM factor:

$$
W_\mu^+\bar u_i d_j:
\qquad
-i\frac{g}{\sqrt2}\gamma^\mu P_L V_{ij}.
$$

For the conjugate $W^-$ vertex, use $V_{ij}^*$ with the conjugate fermion ordering.

The old phrase **$V-A$ interaction** is the same statement in a different notation. Since

$$
\gamma^\mu P_L
=
\frac12\gamma^\mu(1-\gamma^5),
$$

a current written with left-handed fields differs by factors of $2$ from a current written with explicit $(1-\gamma^5)$ factors. Mixing those conventions is the fastest route to a factor-of-four error.

## Low-energy Fermi limit

At momentum transfers much smaller than the $W$ mass,

$$
q^2\ll m_W^2,
$$

tree-level $W$ exchange becomes a local interaction:

$$
\mathcal L_{\rm eff}^{\rm cc}
=
-\frac{g^2}{2m_W^2}j_{W^+}^\mu j_{W^-\,\mu}
+O\!\left(\frac{q^2}{m_W^2}\right).
$$

Using

$$
m_W=\frac{gv}{2},
$$

the conventional Fermi constant is

$$
\frac{G_F}{\sqrt2}
=
\frac{g^2}{8m_W^2}
=
\frac{1}{2v^2}.
$$

For muon decay, one useful left-handed-field form is

$$
\mathcal L_{\rm eff}^{\mu\to e}
=
-\frac{4G_F}{\sqrt2}
(\bar e_L\gamma^\mu\nu_{eL})
(\bar\nu_{\mu L}\gamma_\mu\mu_L)+\cdots.
$$

Equivalently, using full Dirac spinors,

$$
\mathcal L_{\rm eff}^{\mu\to e}
=
-\frac{G_F}{\sqrt2}
\left[\bar e\gamma^\mu(1-\gamma^5)\nu_e\right]
\left[\bar\nu_\mu\gamma_\mu(1-\gamma^5)\mu\right]
+\cdots.
$$

The two formulas are identical because $(1-\gamma^5)=2P_L$.

## What charged currents do physically

Charged currents change the weak-isospin component of a left-handed doublet:

$$
e_L\leftrightarrow \nu_L,
\qquad
d_L\leftrightarrow u_L.
$$

Consequently they mediate processes that change particle species:

$$
n\to p e^-\bar\nu_e,
\qquad
\mu^-\to e^-\bar\nu_e\nu_\mu,
\qquad
\nu_\mu N\to \mu^- X.
$$

The charged-current structure explains three qualitative facts at once: weak interactions violate parity at the gauge vertex, quark charged currents contain CKM flavor mixing, and low-energy weak interactions look pointlike because the $W$ boson is heavy.

## Common pitfalls

**Calling $j_{W^+}$ a positively charged current.** With the definition used here, $j_{W^+}$ is the current that multiplies $W^+$. Its electromagnetic charge is opposite to the $W^+$ charge.

**Forgetting the factor of $1/\sqrt2$.** It comes from the definitions of $W^\pm$ and $T^\pm$.

**Writing a right-handed charged weak current in the minimal Standard Model.** Right-handed charged leptons and right-handed quarks are $SU(2)_L$ singlets, so the Standard Model gauge interaction gives them no $W^\pm$ coupling.

**Confusing CKM and PMNS mixing.** CKM mixing appears in quark charged currents after diagonalizing quark masses. PMNS mixing appears in lepton charged currents once neutrino masses are included.

**Mixing Fermi-normalization conventions.** A current written with $P_L$ is not normalized the same way as a current written with $(1-\gamma^5)$.

## Relations to other pages

- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) defines the $W^\pm$ fields and their mass.
- [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/) gives the corresponding $Z$ interaction, where $T^3$ and $Q$ appear without changing electric charge.
- Fermi Theory Limit derives the low-energy four-fermion description more systematically.
- The later Flavor and Neutrinos chapter explains why mass diagonalization produces CKM and PMNS matrices, and develops the quark mixing matrix beyond the short structural treatment here.

## Research status

The charged-current structure of the Standard Model is established. The $W^\pm$ bosons, left-chiral weak couplings, CKM mixing, and Fermi limit are core ingredients of precision weak physics.

Active work concerns the interfaces: high-precision measurements of $G_F$, $m_W$, CKM unitarity tests, lattice inputs to semileptonic decays, rare decays, lepton-flavor universality tests, and SMEFT interpretations of possible deviations. This page gives the tree-level gauge-theory architecture; precision applications require radiative corrections and effective operators.

## Exercises

### Exercise 1: Derive the charged-current normalization

Starting from $W_\mu^1T^1+W_\mu^2T^2$ and the definitions of $W^\pm$ and $T^\pm$, show that

$$
W_\mu^1T^1+W_\mu^2T^2
=
\frac{1}{\sqrt2}(W_\mu^+T^+ + W_\mu^-T^-).
$$

<details><summary><strong>Solution</strong></summary>

Invert the charged-field definitions:

$$
W_\mu^1=\frac{W_\mu^+ + W_\mu^-}{\sqrt2},
\qquad
W_\mu^2=\frac{i(W_\mu^+ - W_\mu^-)}{\sqrt2}.
$$

Then

$$
W_\mu^1T^1+W_\mu^2T^2
=
\frac{1}{\sqrt2}\left[W_\mu^+(T^1+iT^2)+W_\mu^-(T^1-iT^2)\right],
$$

which is the desired formula.

</details>

### Exercise 2: Relate the Fermi constant to the Higgs scale

Using $m_W=gv/2$ and $G_F/\sqrt2=g^2/(8m_W^2)$, show that $G_F/\sqrt2=1/(2v^2)$.

<details><summary><strong>Solution</strong></summary>

Substitute $m_W^2=g^2v^2/4$:

$$
\frac{g^2}{8m_W^2}
=
\frac{g^2}{8(g^2v^2/4)}
=
\frac{1}{2v^2}.
$$

</details>

### Exercise 3: Show that the CKM matrix is unitary

Let $V=U_{uL}^\dagger U_{dL}$ with $U_{uL}$ and $U_{dL}$ unitary. Show that $V^\dagger V=1$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
V^\dagger V
=(U_{uL}^\dagger U_{dL})^\dagger(U_{uL}^\dagger U_{dL})
=U_{dL}^\dagger U_{uL}U_{uL}^\dagger U_{dL}
=U_{dL}^\dagger U_{dL}=1.
$$

Similarly, $VV^\dagger=1$.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§88–90, for the lepton sector, quark sector, and electroweak interactions of hadrons.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29, for weak interactions, electroweak symmetry breaking, the fermion sector, the Fermi theory, and CP violation.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and chiral gauge interactions.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a compact treatment of charged currents, weak mixing, and low-energy weak interactions.

## Version history

- **2026-06-18:** Initial polished draft. Added the charged-current normalization, CKM structure, Fermi limit, and charged-current map figure.
