---
title: "Ward Identities and Renormalization"
description: "How Ward, Ward–Takahashi, and Slavnov–Taylor identities constrain counterterms, renormalization constants, charge renormalization, and gauge-theory predictivity."
sidebar:
  label: "Ward Identities and Renormalization"
  order: 6
level: Graduate
status: "Polished draft"
source: "Coleman lectures on QED Ward identities; Srednicki 2007, §§66–68 and 73–78; Weinberg Vol. II, chs. 15–18; Schwartz 2014, chs. 19, 26, and 34; Zinn-Justin 2021, renormalization with symmetries."
topics:
  - Ward identities
  - Ward–Takahashi identity
  - Slavnov–Taylor identities
  - renormalization constants
  - charge renormalization
  - gauge-theory counterterms
canonicalTopics:
  - ward-identities-and-renormalization
  - gauge-theory-renormalization
  - slavnov-taylor-identities
researchStatus:
  established:
    - "Ward and Slavnov–Taylor identities are the standard constraints that make renormalized gauge theories predictive and gauge-consistent."
  active:
    - "Multi-loop gauge-theory calculations, chiral theories, evanescent operators, EFT operator bases, and algebraic-renormalization proofs require careful identity-preserving bookkeeping."
---

## Summary

Ward identities are the equations that keep renormalized gauge theory honest. They say that the redundancy used to describe gauge fields still constrains the quantum theory after regularization, counterterms, and renormalization. In QED they imply the Ward–Takahashi identity

$$
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p),
$$

where $S(p)$ is the full electron propagator and $\Gamma^\mu$ is the proper photon-electron vertex. In particular, at zero photon momentum,

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

This identity is the reason the QED vertex counterterm and electron wavefunction counterterm are equal:

$$
Z_1=Z_2.
$$

In nonabelian gauge theory the corresponding constraints are the Slavnov–Taylor identities. They are more complicated because gauge bosons carry charge, ghosts are dynamical in loops, and the gauge-fixed action is organized by BRST symmetry rather than ordinary current conservation. But the role is the same: they restrict counterterms, relate renormalization constants, and ensure that unphysical gauge degrees of freedom do not appear in physical observables.

The useful slogan is

$$
\text{renormalization of gauge theory}=
\text{local counterterms constrained by gauge identities}.
$$

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Map of Ward identities and renormalization: gauge redundancy gives a Ward identity, which implies transversality, Z one equals Z two in QED, charge running through photon field renormalization, allowed counterterms, and nonabelian Slavnov–Taylor generalization.](/figures/renormalization-rg-eft/ward-identity-renormalization-map.svg)

<figcaption>

Ward identities turn gauge redundancy into renormalization constraints. In QED they imply transversality of vacuum polarization and $Z_1=Z_2$; in nonabelian gauge theory the analogous Slavnov–Taylor identities tie together gauge, ghost, matter, and vertex renormalizations.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), and [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/). The details of BRST symmetry and Slavnov–Taylor identities are developed more fully in the Symmetry, Anomalies, and Topology and Gauge Theories volumes; here we focus on their renormalization meaning.

## Core idea

Gauge invariance is not just a classical aesthetic constraint on the Lagrangian. It is a quantum consistency condition. Once a gauge theory is regularized, loop corrections generate all local terms compatible with the regulator. Ward and Slavnov–Taylor identities decide which of those terms are allowed in the renormalized gauge theory.

In QED, current conservation implies that inserting a longitudinal photon into an amplitude is equivalent to the difference between inverse charged-particle propagators. This is the Ward–Takahashi identity. It makes charge renormalization simpler than it would otherwise be: the charge counterterm is tied to the photon wavefunction renormalization rather than to an independent electron-photon vertex renormalization.

In Yang–Mills theory, gauge bosons interact with themselves and ghosts contribute. There is no simple identity $Z_1=Z_2$ for every vertex. Instead, the Slavnov–Taylor identities relate the renormalization of the gauge coupling, gauge field, ghost field, matter fields, and interaction vertices. They are the algebraic skeleton behind the statement that Yang–Mills theory renormalizes as a gauge theory rather than as a random collection of vector fields.

## Setup and conventions

We use the mostly-minus metric and the renormalization convention

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare}}.
$$

For QED, write the bare fields and parameters as

$$
\psi_0=Z_2^{1/2}\psi,
\qquad
A_{0\mu}=Z_3^{1/2}A_\mu,
\qquad
e_0=\mu^\epsilon Z_e e,
$$

in $d=4-2\epsilon$. A common counterterm notation writes

$$
\mathcal L
=-\frac14Z_3F_{\mu\nu}F^{\mu\nu}
+Z_2\bar\psi i\gamma^\mu\partial_\mu\psi
-Z_m m\bar\psi\psi
-Z_1 e\mu^\epsilon \bar\psi\gamma^\mu A_\mu\psi
+\mathcal L_{\mathrm{gf}}.
$$

Different books distribute $Z_e$, $Z_1$, $Z_2$, and $Z_3$ differently. The invariant content is not the notation but the identity relating the vertex and fermion wavefunction renormalizations. With the convention above, the QED Ward identity gives

$$
Z_1=Z_2.
$$

Then the bare charge can be expressed as

$$
e_0=\mu^\epsilon Z_3^{-1/2}e,
$$

up to the precise placement of $Z$ factors chosen in the Lagrangian. Thus QED charge renormalization is controlled by photon-field renormalization.

## The ordinary Ward identity

Before QFT, the prototype Ward identity is simply current conservation. If a global $U(1)$ symmetry has a conserved current $j^\mu$, then in a correlator of charged local operators,

$$
\partial_\mu\langle T\,j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
$$

is not zero as an ordinary function. It contains contact terms when $x$ collides with the charged operators. Schematically,

$$
\partial_\mu\langle T\,j^\mu(x)\mathcal O_1\cdots\mathcal O_n\rangle
=-i\sum_{k=1}^n q_k\delta^{(4)}(x-x_k)
\langle T\,\mathcal O_1\cdots\mathcal O_k\cdots\mathcal O_n\rangle,
$$

where $q_k$ is the charge of $\mathcal O_k$ and the notation suppresses the transformation of operator indices.

The contact terms are not an annoyance. They are the whole point. They encode how the symmetry charge acts on operator insertions.

For gauge theory, the analogous identities are stronger because the current is coupled to a gauge field and gauge redundancy removes unphysical polarizations. Longitudinal gauge-field insertions are not independent physical data.

## The Ward–Takahashi identity in QED

Let $S(p)$ be the full electron propagator and let $\Gamma^\mu(p+q,p)$ be the full one-particle-irreducible photon-electron vertex, with incoming electron momentum $p$, outgoing electron momentum $p+q$, and incoming photon momentum $q$. The Ward–Takahashi identity is

$$
q_\mu\Gamma^\mu(p+q,p)
=S^{-1}(p+q)-S^{-1}(p).
$$

At zero photon momentum, expand the right-hand side to first order in $q$:

$$
S^{-1}(p+q)-S^{-1}(p)
=q_\mu\frac{\partial S^{-1}(p)}{\partial p_\mu}+O(q^2).
$$

Therefore

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

This identity says that the ultraviolet divergence in the vertex at zero momentum transfer is tied to the ultraviolet divergence in the inverse propagator. Therefore the counterterm that renormalizes the electron-photon vertex is tied to the counterterm that renormalizes the electron kinetic term.

This is the conceptual origin of

$$
Z_1=Z_2
$$

in QED.

## Consequences for QED counterterms

The most important consequences are:

| Identity consequence | Renormalization meaning |
|---|---|
| $q_\mu\Pi^{\mu\nu}(q)=0$ | vacuum polarization is transverse |
| no $A_\mu A^\mu$ counterterm | photon mass is forbidden |
| $q_\mu\Gamma^\mu=S^{-1}(p+q)-S^{-1}(p)$ | vertex and electron wavefunction divergences are tied |
| $Z_1=Z_2$ | electric charge renormalization is governed by $Z_3$ |
| longitudinal photons decouple from conserved external currents | physical amplitudes are gauge-parameter independent after all diagrams are included |

Let the photon two-point function have the form

$$
\Pi^{\mu\nu}(q)
=(q^2\eta^{\mu\nu}-q^\mu q^\nu)\Pi(q^2).
$$

The tensor structure is forced by Lorentz invariance and transversality. A gauge-invariant counterterm can renormalize

$$
-\frac14F_{\mu\nu}F^{\mu\nu},
$$

but cannot introduce

$$
\frac12m_\gamma^2A_\mu A^\mu.
$$

This is a sharp example of how a Ward identity restricts the local terms produced by renormalization.

## Charge renormalization in QED

With the $Z_1=Z_2$ relation, the renormalization of the electric charge can be read from the photon field renormalization. In a common convention,

$$
e_0=\mu^\epsilon Z_3^{-1/2}e.
$$

Taking $\mu d/d\mu$ at fixed $e_0$ gives the QED beta function. At one loop with one Dirac fermion,

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

The positivity means that the QED coupling grows toward the ultraviolet in perturbation theory.

The important conceptual point is that one does not separately renormalize an arbitrary photon-electron vertex. Gauge invariance ties the vertex to the charged field and the photon normalization. This is part of why QED is so predictive.

## Nonabelian Slavnov–Taylor identities

In nonabelian gauge theory, the analogous story is more intricate. Gauge bosons carry gauge charge, and the gauge-fixed action contains ghosts. The identities are not simple current-conservation Ward identities but Slavnov–Taylor identities derived from BRST symmetry.

Introduce schematic renormalizations

$$
A_0^a=Z_A^{1/2}A^a,
\qquad
c_0^a=Z_c^{1/2}c^a,
\qquad
\psi_0=Z_\psi^{1/2}\psi,
\qquad
g_0=\mu^\epsilon Z_g g.
$$

The interaction vertices have their own apparent renormalization constants, such as

$$
Z_{3g},\qquad Z_{4g},\qquad Z_{\bar c c A},\qquad Z_{\bar\psi\psi A}.
$$

Slavnov–Taylor identities relate them. Schematically, the same coupling $g$ must appear in all gauge interactions after the proper field renormalizations are included. For example, the ghost-gluon, three-gluon, and quark-gluon vertices cannot run as independent couplings in a genuine Yang–Mills theory.

The exact algebra depends on conventions, but the pattern is universal:

$$
\text{one gauge coupling}
\quad\Longrightarrow\quad
\text{many vertex counterterms tied by BRST identities}.
$$

Without these identities, a general interacting vector theory would generate many independent Lorentz-invariant counterterms. With gauge symmetry, the counterterms reorganize into the renormalization of

$$
-\frac14F_{\mu\nu}^aF^{a\mu\nu},
$$

matter kinetic terms, gauge-fixing and ghost terms, and BRST-compatible field and parameter redefinitions.

## Background-field simplification

The background field method splits the gauge field as

$$
A_\mu=\bar A_\mu+a_\mu,
$$

where $\bar A_\mu$ is a background field and $a_\mu$ is the quantum field integrated over. With background-covariant gauge fixing, the effective action remains invariant under background gauge transformations.

This gives a particularly simple relation between the gauge coupling and background gauge-field renormalization. In common conventions,

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

Therefore the beta function can be extracted from the background two-point function. This is why the background field method is so efficient for nonabelian beta-function calculations.

The simplification is not magic. It is the same Ward-identity idea in a better coordinate system: background gauge invariance makes the relevant identity look more like the QED Ward identity.

## Renormalization as an identity-preserving induction

A powerful way to understand gauge-theory renormalization is inductive.

Assume that through loop order $L-1$, the renormalized effective action satisfies the Ward or Slavnov–Taylor identities. At loop order $L$, locality says the remaining ultraviolet divergence is a local functional. Symmetry says that this local functional must satisfy the linearized version of the identity. Therefore it belongs to a restricted set of allowed counterterms.

In QED, the allowed divergent local terms are essentially field-strength, fermion kinetic, mass, and gauge-fixing renormalizations, with $Z_1=Z_2$. In Yang–Mills theory, the allowed terms are gauge-invariant terms plus BRST-exact gauge-fixing terms and field redefinitions.

This is the reason renormalizable gauge theory does not require infinitely many independent counterterms at each order. Locality alone is not enough; Lorentz invariance alone is not enough; power counting alone is not enough. The identities are essential.

## What happens with a symmetry-breaking regulator

If the regulator preserves the identities, the proof is clean. Dimensional regularization usually does this for vectorlike gauge theories. If the regulator breaks the identities, then the renormalized effective action may satisfy

$$
\mathcal W(\Gamma_\Lambda)=\Delta_\Lambda
$$

for a Ward operator $\mathcal W$, or

$$
\mathcal S(\Gamma_\Lambda)=\Delta_\Lambda
$$

for a Slavnov–Taylor operator $\mathcal S$. The breaking $\Delta_\Lambda$ must be studied.

If $\Delta_\Lambda$ is local and trivial in the appropriate cohomology, it can be canceled by a local counterterm. If it is a nontrivial anomaly, it cannot. This is the clean distinction between regulator artifacts and quantum obstructions.

The phrase "restore the Ward identity" should therefore always be accompanied by two checks:

| Check | Meaning |
|---|---|
| locality | the breaking can be represented by local operators |
| cohomological triviality | the breaking is not a true anomaly |

In anomaly-free gauge theories, identity-breaking regulators can sometimes be used, but the calculation is more delicate than one done with an identity-preserving regulator.

## Gauge-parameter independence

Ward and Slavnov–Taylor identities are also responsible for the gauge-parameter independence of physical observables. Individual Green functions usually depend on the gauge-fixing parameter $\xi$. For example, the photon or gluon propagator in covariant gauge contains longitudinal pieces depending on $\xi$.

This does not mean physical amplitudes depend on arbitrary gauge choices. The identities ensure that, after summing all diagrams and applying LSZ to physical external states, the dependence on unphysical polarizations and gauge-fixing parameters cancels.

The cancellation can be subtle. A single diagram, a truncated self-energy, or an off-shell Green function may be gauge-dependent. A properly defined observable should not be.

This is one of the most important habits in gauge-theory calculations:

$$
\text{do not demand gauge independence of intermediate quantities; demand the correct identity structure.}
$$

## Ward identities for composite operators

Local operator insertions introduce additional contact terms and mixing. If $\mathcal O_a$ is a set of composite operators, renormalization generally takes the form

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Gauge identities constrain the operator basis. Gauge-invariant operators can mix with other gauge-invariant operators of the same quantum numbers and equal or lower dimension, but in gauge-fixed perturbation theory the full story can include BRST-exact operators and equations-of-motion operators. These unphysical operators may be needed for off-shell renormalization but drop out of suitable physical matrix elements.

In EFT calculations this is a major bookkeeping issue. A gauge-invariant operator basis is not just an aesthetic choice; it prevents spurious gauge-breaking Wilson coefficients and makes matching and running compatible with the symmetry.

## Common pitfalls

**Quoting $Z_1=Z_2$ outside QED without qualification.** The simple equality is special to QED-like Ward identities. Nonabelian gauge theories have Slavnov–Taylor relations among several constants, not a universal copy of the QED formula.

**Thinking Ward identities say loop corrections vanish.** They do not. They constrain the form of loop corrections. Vacuum polarization is nonzero, but it is transverse.

**Forgetting contact terms.** Current conservation inside time-ordered correlators includes contact terms. Dropping them erases the action of the charge on fields.

**Confusing gauge invariance of observables with gauge independence of Green functions.** Off-shell Green functions and gauge-fixed propagators can depend on $\xi$. Physical on-shell observables should not.

**Treating anomalies as failed algebra.** An anomaly is often the correct quantum Ward identity for a global symmetry. For a gauge symmetry, however, it is an obstruction unless it cancels.

**Using a noninvariant regulator and assuming the identity survives.** The identity must be checked or restored. It does not survive by wishful thinking.

## Relations to other pages

This page continues [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/). The QED consequences connect to [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), while the nonabelian consequences connect to [Yang–Mills Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/yang-mills-beta-function/) and [QCD Running Coupling](/renormalization-rg-eft/gauge-theories-and-rg/qcd-running-coupling/).

The background-field shortcut is explained in [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/). The operator-mixing version connects to [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/). The full BRST, anomaly, and cohomological interpretation belongs in the Symmetry, Anomalies, and Topology volume.

## Research status

The role of Ward identities in QED renormalization and Slavnov–Taylor identities in nonabelian gauge-theory renormalization is settled. These identities are part of the standard proof that anomaly-free gauge theories can be renormalized consistently.

The hard work in modern calculations lies in implementation. Multi-loop EFT anomalous dimensions, chiral gauge theories, $\gamma^5$ prescriptions, evanescent operators, nonlinear gauges, unstable particles, infrared subtractions, and automated amplitude pipelines all require identity-preserving bookkeeping. The principle is old; the engineering remains lively.

## Exercises

### Exercise 1: Derive the zero-momentum Ward identity

Starting from

$$
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p),
$$

show that

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

<details><summary><strong>Solution</strong></summary>

Expand the inverse propagator for small $q$:

$$
S^{-1}(p+q)=S^{-1}(p)+q_\mu\frac{\partial S^{-1}(p)}{\partial p_\mu}+O(q^2).
$$

Then the Ward–Takahashi identity becomes

$$
q_\mu\Gamma^\mu(p+q,p)
=q_\mu\frac{\partial S^{-1}(p)}{\partial p_\mu}+O(q^2).
$$

Taking $q\to0$ and comparing the coefficient of arbitrary $q_\mu$ gives

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

</details>

### Exercise 2: Why $Z_1=Z_2$ in QED

Let the divergent part of the inverse electron propagator contain

$$
S^{-1}(p)_{\mathrm{div}}=Z_2^{\mathrm{div}}p\!\!\!/-Z_m^{\mathrm{div}}m+\text{finite},
$$

and let the divergent part of the vertex at zero photon momentum be

$$
\Gamma^\mu(p,p)_{\mathrm{div}}=Z_1^{\mathrm{div}}\gamma^\mu+\text{finite}.
$$

Use the zero-momentum Ward identity to explain why the kinetic and vertex divergences are equal.

<details><summary><strong>Solution</strong></summary>

The zero-momentum Ward identity gives

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

Differentiating the divergent kinetic part gives

$$
\frac{\partial}{\partial p_\mu}(Z_2^{\mathrm{div}}p\!\!\!/)
=Z_2^{\mathrm{div}}\gamma^\mu.
$$

The mass divergence has no $p_\mu$ dependence and does not contribute. Therefore the divergent coefficient of $\gamma^\mu$ in the vertex equals the divergent coefficient of the fermion kinetic term. In standard notation this is written

$$
Z_1=Z_2.
$$

</details>

### Exercise 3: Transverse tensor structure

Assume Lorentz invariance and transversality for the vacuum polarization:

$$
q_\mu\Pi^{\mu\nu}(q)=0.
$$

Show that the parity-even tensor structure depending only on $q$ has the form

$$
\Pi^{\mu\nu}(q)=(q^2\eta^{\mu\nu}-q^\mu q^\nu)\Pi(q^2).
$$

<details><summary><strong>Solution</strong></summary>

Lorentz invariance allows

$$
\Pi^{\mu\nu}(q)=A(q^2)\eta^{\mu\nu}+B(q^2)q^\mu q^\nu.
$$

Transversality gives

$$
0=q_\mu\Pi^{\mu\nu}(q)
=A(q^2)q^\nu+B(q^2)q^2q^\nu.
$$

For generic $q$, this implies

$$
A(q^2)=-q^2B(q^2).
$$

Therefore

$$
\Pi^{\mu\nu}(q)=B(q^2)(q^\mu q^\nu-q^2\eta^{\mu\nu}).
$$

Defining $\Pi(q^2)=-B(q^2)$ gives

$$
\Pi^{\mu\nu}(q)=(q^2\eta^{\mu\nu}-q^\mu q^\nu)\Pi(q^2).
$$

</details>

### Exercise 4: Background-field charge renormalization

Suppose a background-field calculation gives

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

Explain why this means the gauge beta function can be extracted from the divergent part of the background gauge-field two-point function.

<details><summary><strong>Solution</strong></summary>

The relation implies

$$
Z_g=Z_{\bar A}^{-1/2}.
$$

The bare coupling is

$$
g_0=\mu^\epsilon Z_g g
=\mu^\epsilon Z_{\bar A}^{-1/2}g.
$$

Holding $g_0$ fixed and differentiating with respect to $\mu$ determines $\beta_g$. Therefore the beta function is determined by the renormalization factor of the background field. Since $Z_{\bar A}$ is obtained from the divergent part of the background two-point function, that two-point function is enough to extract the beta function in the background-field method.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on Ward identities and QED renormalization.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on QED Ward identities, nonabelian beta functions, BRST symmetry, and background field gauge.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on nonabelian gauge theory, BRST symmetry, renormalization, and renormalization group methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on renormalized perturbation theory, QED Ward identities, Yang–Mills renormalization, and background fields.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the discussions of renormalization, symmetries, BRST identities, and gauge theories.
- J. C. Ward, original paper on QED identities.
- Y. Takahashi, original extension to the Ward–Takahashi identity.
- A. A. Slavnov and J. C. Taylor, original work on nonabelian gauge-theory identities.

## Version history

- 2026-06-18: First polished draft. Added QED Ward–Takahashi identities, $Z_1=Z_2$, charge-renormalization consequences, nonabelian Slavnov–Taylor constraints, background-field relation, and exercises.
