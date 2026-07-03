---
title: "QED One-Loop Renormalization"
description: "A worked one-loop renormalization benchmark in spinor QED: electron self-energy, photon vacuum polarization, vertex correction, Ward identity, and MS-bar counterterms."
sidebar:
  label: "QED One-Loop Renormalization"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§62–68; Schwartz 2014, chs. 16 and 18–19; Weinberg 1995, Vol. I chs. 10–12; Coleman 2019, renormalization and Ward-identity lectures."
topics:
  - QED renormalization
  - vacuum polarization
  - electron self-energy
  - vertex renormalization
  - Ward identity
  - MS-bar scheme
canonicalTopics:
  - qed-one-loop-renormalization
  - spinor-qed-counterterms
  - ward-identity-renormalization
researchStatus:
  established:
    - "One-loop renormalization of spinor QED and the Ward identity relation between vertex and electron-field renormalization are standard benchmark results."
  active:
    - "Precision QED, multi-loop renormalization, infrared-safe observables, unstable charged particles, finite-density QED, and QED embedded in the Standard Model require additional machinery beyond this benchmark page."
---

## Summary

Spinor QED is the first gauge-theory benchmark where renormalization becomes more than a list of divergent integrals. At one loop, three families of diagrams appear:

$$
\text{electron self-energy},
\qquad
\text{photon vacuum polarization},
\qquad
\text{electron-photon vertex correction}.
$$

They require field, mass, and vertex counterterms, but gauge invariance ties them together. In particular, the Ward identity implies

$$
Z_1=Z_\psi,
$$

where $Z_1$ renormalizes the electron-photon vertex and $Z_\psi$ renormalizes the electron field. Charge renormalization is therefore controlled by the photon field renormalization alone:

$$
e_0=\mu^\epsilon Z_A^{-1/2}e
$$

in an MS-like scheme with one Dirac fermion of unit charge.

Using dimensional regularization with $d=4-2\epsilon$, Feynman gauge, and the volume convention

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log4\pi,
$$

the one-loop $\overline{\mathrm{MS}}$ pole parts may be summarized as

$$
Z_A=1-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
$$

$$
Z_\psi=1-\frac{e^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
\qquad
Z_m=1-\frac{3e^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
$$

and

$$
Z_1=Z_\psi.
$$

Only $Z_A$ is needed for the one-loop QED beta function. The other constants are still essential: they make the electron propagator and vertex finite and provide the Ward-identity check that the calculation respects gauge symmetry.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![QED one-loop renormalization map showing electron self-energy, vacuum polarization, vertex correction, counterterms, Ward identity, and charge renormalization](/figures/renormalization-rg-eft/qed-one-loop-renormalization-map.svg)

<figcaption>

The one-loop QED calculation has three UV-sensitive 1PI structures: electron self-energy $\Sigma(p)$, vacuum polarization $\Pi^{\mu\nu}(q)$, and vertex correction $\Lambda^\mu$. Local pole parts are absorbed into $Z_\psi$, $Z_m$, $Z_A$, and $Z_1$. The Ward identity imposes $Z_1=Z_\psi$, so the running of $e$ is controlled by the photon field renormalization $Z_A$.

</figcaption>
</figure>

:::note[What is being calculated]
This page computes the ultraviolet renormalization structure of spinor QED at one loop. It is not a complete calculation of a physical cross section. Real QED observables also require infrared-safe definitions, soft radiation, and sometimes on-shell renormalization conditions.
:::

## Prerequisites

You should know [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), and [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/).

We use mostly-minus metric conventions, plane waves $e^{-ip\cdot x}$, and the Dirac notation

$$
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

The regulator is dimensional regularization with

$$
d=4-2\epsilon.
$$

The subtraction scheme is $\overline{\mathrm{MS}}$ unless stated otherwise. We work in covariant gauge and quote explicit pole constants in Feynman gauge. The Ward identity is gauge-independent, while $Z_\psi$ and $Z_1$ separately depend on the gauge-fixing convention.

## The model and conventions

The renormalized QED Lagrangian in covariant gauge is

$$
\mathcal L_{\mathrm{ren}}
=
-\frac14 F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-\mu^\epsilon e\,\bar\psi\gamma^\mu A_\mu\psi.
$$

Here $\mu^\epsilon$ keeps the renormalized coupling $e$ dimensionless in $d=4-2\epsilon$. The fine-structure constant is

$$
\alpha\equiv\frac{e^2}{4\pi}.
$$

For this page, the default matter content is one Dirac fermion of unit electric charge. For several Dirac fermions with charges $Q_f$ in units of $e$, the vacuum-polarization result is multiplied by

$$
\sum_f Q_f^2.
$$

Ghosts decouple in abelian QED, so they do not appear in the one-loop diagrams. This is a major simplification compared with Yang–Mills theory.

## Bare and renormalized fields

Write the bare fields and parameters as

$$
A_{0\mu}=Z_A^{1/2}A_\mu,
\qquad
\psi_0=Z_\psi^{1/2}\psi,
\qquad
m_0=Z_m m,
$$

and parameterize the interaction by

$$
e_0\bar\psi_0\gamma^\mu A_{0\mu}\psi_0
=
\mu^\epsilon e\,Z_1\bar\psi\gamma^\mu A_\mu\psi.
$$

Equivalently,

$$
e_0=\mu^\epsilon Z_e e,
\qquad
Z_e=Z_1Z_\psi^{-1}Z_A^{-1/2}.
$$

The counterterm Lagrangian is then

$$
\mathcal L_{\mathrm{ct}}
=
-\frac14\delta Z_A F_{\mu\nu}F^{\mu\nu}
+\delta Z_\psi\bar\psi i\gamma^\mu\partial_\mu\psi
-\delta Z_{\psi m}\,m\bar\psi\psi
-\mu^\epsilon e\,\delta Z_1\bar\psi\gamma^\mu A_\mu\psi,
$$

where

$$
\delta Z_A=Z_A-1,
\qquad
\delta Z_\psi=Z_\psi-1,
\qquad
\delta Z_1=Z_1-1,
$$

and $\delta Z_{\psi m}=Z_\psi Z_m-1$ if one expands the bare mass term in the same field convention. Many books distribute the mass counterterm differently. The invariant statement is the pole part of $Z_m$, not the name assigned to the product $Z_\psi Z_m$.

:::tip[Use Z factors for comparisons]
When comparing QED renormalization constants across books, compare the definitions of $A_0$, $\psi_0$, $m_0$, and $e_0$ before comparing signs. The same diagram can be quoted as a self-energy, a counterterm vertex, a contribution to the inverse propagator, or a contribution to the effective action.
:::

## The one-loop diagrams

At one loop, QED has the following UV-sensitive 1PI functions.

| 1PI object | Diagram | Local counterterms | Main check |
|---|---|---|---|
| Fermion two-point function | photon loop correcting the electron line | $Z_\psi$, $Z_m$ | pole structure proportional to $p\!\!\!/$ and $m$ |
| Photon two-point function | fermion loop | $Z_A$ | transversality $q_\mu\Pi^{\mu\nu}=0$ |
| Electron-photon three-point function | photon loop attached to the vertex | $Z_1$ | Ward identity $Z_1=Z_\psi$ |

The three diagrams are not independent. Gauge symmetry does not allow arbitrary local counterterms in QED. In particular, a photon mass counterterm

$$
\frac12\delta m_A^2 A_\mu A^\mu
$$

is forbidden by gauge invariance. Dimensional regularization preserves this automatically in ordinary anomaly-free QED.

## Vacuum polarization

The photon two-point 1PI function has the transverse form

$$
i\Pi^{\mu\nu}(q)
=
i(q^2\eta^{\mu\nu}-q^\mu q^\nu)\Pi(q^2).
$$

The tensor structure is not an aesthetic preference. It follows from current conservation and the Ward identity:

$$
q_\mu\Pi^{\mu\nu}(q)=0.
$$

At one loop, the UV pole for one unit-charge Dirac fermion is local and proportional to the Maxwell kinetic term. In the conventions of this page,

$$
\Pi_{\mathrm{div}}(q^2)
=
\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}.
$$

The photon counterterm cancels this pole, giving

$$
\delta Z_A
=
-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
$$

or

$$
Z_A=1-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

For several Dirac fermions with charges $Q_f$,

$$
Z_A
=
1-\frac{e^2}{12\pi^2}\left(\sum_f Q_f^2\right)\frac{1}{\bar\epsilon}
+O(e^4).
$$

This pole is gauge independent. It is the seed of the one-loop QED beta function.

### A quick derivation of the pole coefficient

The vacuum-polarization numerator is obtained from the fermion trace

$$
\operatorname{tr}\!
\left[
\gamma^\mu(\ell\!\!\!/+m)
\gamma^\nu((\ell+q)\!\!\!/+m)
\right].
$$

After Feynman parametrization and shifting the loop momentum, the UV-divergent transverse part reduces to a term proportional to

$$
8e^2(q^2\eta^{\mu\nu}-q^\mu q^\nu)
\int_0^1 dx\,x(1-x)
\mu^{2\epsilon}\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+\Delta)^2}.
$$

The logarithmic Euclidean integral has pole part

$$
\mu^{2\epsilon}\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}\frac{1}{\bar\epsilon}+\text{finite},
$$

and

$$
\int_0^1 dx\,x(1-x)=\frac16.
$$

This is the origin of the coefficient $1/(12\pi^2)$ after the conventional tensor and sign factors are assembled. The finite part contains the physical logarithm that later becomes the running of the electric charge.

## Electron self-energy

The electron self-energy is the one-loop correction to the fermion two-point function. It can be decomposed as

$$
\Sigma(p)=p\!\!\!/\,\Sigma_V(p^2)+m\Sigma_S(p^2).
$$

The two available local structures are therefore

$$
\bar\psi i\gamma^\mu\partial_\mu\psi,
\qquad
m\bar\psi\psi.
$$

Those are exactly the structures renormalized by $Z_\psi$ and $Z_m$.

In Feynman gauge, the $\overline{\mathrm{MS}}$ pole parts are conventionally summarized by

$$
Z_\psi
=
1-\frac{e^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
$$

and

$$
Z_m
=
1-\frac{3e^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

The field renormalization $Z_\psi$ depends on the covariant gauge parameter. The mass renormalization $Z_m$ is gauge independent at this order in the usual MS-like conventions.

The pole in $Z_m$ is the source of the leading QED mass anomalous dimension. With the convention

$$
\gamma_m\equiv -\left.\mu\frac{d\log m}{d\mu}\right|_{m_0,e_0},
$$

one obtains at leading order

$$
\gamma_m=\frac{3e^2}{8\pi^2}+O(e^4)
=
\frac{3\alpha}{2\pi}+O(\alpha^2).
$$

The sign means that, in this convention, the running mass decreases toward the ultraviolet in perturbative QED.

## Vertex correction

The one-loop electron-photon vertex correction contributes to the 1PI three-point function

$$
\Gamma^\mu(p',p)
=
\gamma^\mu+\Lambda^\mu(p',p).
$$

The local UV-divergent part has the same Dirac structure as the original vertex:

$$
\bar\psi\gamma^\mu A_\mu\psi.
$$

In Feynman gauge, the corresponding MS-like pole is

$$
Z_1
=
1-\frac{e^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

This equals $Z_\psi$ at the same order.

The equality is not a one-loop accident. The Ward–Takahashi identity for the full vertex and inverse fermion propagator is

$$
q_\mu\Gamma^\mu(p+q,p)
=
S^{-1}(p+q)-S^{-1}(p).
$$

Taking the limit $q\to0$ gives

$$
\Gamma^\mu(p,p)
=
\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

The UV pole in the zero-momentum-transfer vertex must therefore match the UV pole in the derivative of the inverse fermion propagator. In renormalization-constant language,

$$
Z_1=Z_\psi.
$$

:::note[Why the Ward identity matters]
Without the Ward identity, charge renormalization could depend on a separate vertex counterterm. In QED it does not. The cancellation $Z_1Z_\psi^{-1}=1$ leaves $Z_A^{-1/2}$ as the only factor in $Z_e$.
:::

## Charge renormalization

From the interaction term,

$$
Z_e=Z_1Z_\psi^{-1}Z_A^{-1/2}.
$$

The Ward identity gives

$$
Z_e=Z_A^{-1/2}.
$$

Using the one-loop photon-field renormalization,

$$
Z_A=1-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4),
$$

we get

$$
Z_e
=
1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

Therefore

$$
e_0
=
\mu^\epsilon e
\left[
1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4)
\right]
$$

for one Dirac fermion of unit charge. The next page differentiates this fixed bare coupling to obtain

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

## What is gauge-dependent?

The individual off-shell Green functions in QED are not all observables. A useful separation is:

| Quantity | Gauge dependence? | Comment |
|---|---|---|
| $Z_\psi$ | yes | Off-shell electron field renormalization depends on gauge fixing. |
| $Z_1$ | yes | Equal to $Z_\psi$ by the Ward identity. |
| $Z_m$ | no at this order in MS-like schemes | The mass anomalous dimension is a physical RG datum in this sense. |
| $Z_A$ pole | no | Controls the one-loop beta function. |
| $Z_1/Z_\psi$ | no | Equals one in QED. |
| S-matrix elements | no, when properly defined | Infrared-safe observables require real radiation. |

This table is often the cure for a first encounter with gauge dependence. Gauge-dependent intermediate quantities are not mistakes. Gauge-dependent final observables are.

## Checks

A trustworthy one-loop QED renormalization calculation should pass these checks.

| Check | What it verifies |
|---|---|
| Transversality $q_\mu\Pi^{\mu\nu}=0$ | No photon mass counterterm is generated. |
| Ward identity $Z_1=Z_\psi$ | Vertex and electron-field counterterms respect gauge invariance. |
| Locality of UV poles | Divergences match local operators already present in the Lagrangian. |
| Dimensional analysis | The pole terms have the correct dimensions and powers of $e$. |
| Gauge-parameter bookkeeping | Gauge-dependent constants do not enter the beta function or physical amplitude. |
| Infrared separation | UV renormalization is not confused with soft-photon physics. |

The Ward identity is the most diagnostic check. If a regulator or algebraic manipulation gives $Z_1\ne Z_\psi$ in ordinary QED, something has broken gauge invariance or the definitions of the constants are not being compared consistently.

## Common pitfalls

**Mistaking the electron field renormalization for charge renormalization.** The electron field appears in the vertex, but the Ward identity cancels its effect in $Z_e$. The QED beta function is controlled by $Z_A$.

**Forgetting that $Z_\psi$ is gauge dependent.** The residue of an off-shell Green function is not a physical observable. Gauge-dependent $Z$ factors are normal.

**Adding a photon mass counterterm.** A hard cutoff calculation may produce terms that look gauge-violating if used carelessly. In gauge-invariant renormalization, no local $A_\mu A^\mu$ counterterm is allowed in QED.

**Confusing UV and IR divergences.** QED with massless photons has infrared singularities in on-shell amplitudes. Dimensional regularization can regulate both UV and IR singularities, but they have different physical meanings and must not be subtracted indiscriminately.

**Comparing $Z_m$ to a mass counterterm with a different field convention.** Some authors quote $m_0=Z_m m$; others quote the coefficient of $m\bar\psi\psi$ in the counterterm Lagrangian. These are related but not identical.

**Expecting the beta function from the vertex diagram.** In QED, the vertex and electron-field factors cancel in charge renormalization. The beta function comes from vacuum polarization.

## Relations to other pages

This page is the QED analogue of [Phi-Four One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/phi-four-one-loop-renormalization/) and [Yukawa Theory One Loop](/renormalization-rg-eft/model-calculation-library/yukawa-theory-one-loop/). It prepares [QED Beta Function](/renormalization-rg-eft/model-calculation-library/qed-beta-function/), where the fixed-bare-coupling derivative is carried out explicitly.

For the conceptual background, see [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/), [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/), [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/), and [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/). For the nonabelian contrast, continue to [Yang–Mills One-Loop Beta Function](/renormalization-rg-eft/model-calculation-library/yang-mills-one-loop-beta-function/) when that page is available.

## Research status

The one-loop renormalization of QED is established textbook material. It is also a useful portal into more delicate questions. Precision QED requires multi-loop corrections, on-shell schemes, soft-photon resummation, bound-state methods, and careful treatment of experimental observables. QED embedded in the Standard Model requires electroweak matching and running across thresholds. None of those subtleties changes the one-loop Ward-identity lesson of this page.

## Exercises

### Exercise 1: Extract the charge renormalization factor

Assume

$$
Z_1=Z_\psi,
\qquad
Z_A=1-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

Using

$$
Z_e=Z_1Z_\psi^{-1}Z_A^{-1/2},
$$

show that

$$
Z_e=1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

<details><summary><strong>Solution</strong></summary>

The Ward identity gives $Z_1Z_\psi^{-1}=1$, so

$$
Z_e=Z_A^{-1/2}.
$$

For small $x$,

$$
(1+x)^{-1/2}=1-\frac{x}{2}+O(x^2).
$$

Here

$$
x=-\frac{e^2}{12\pi^2}\frac{1}{\bar\epsilon},
$$

so

$$
Z_A^{-1/2}
=
1+\frac{e^2}{24\pi^2}\frac{1}{\bar\epsilon}+O(e^4).
$$

</details>

### Exercise 2: Several charged fermions

Suppose QED contains $N_f$ Dirac fermions with charges $Q_f e$. What is the one-loop photon field renormalization constant?

<details><summary><strong>Solution</strong></summary>

Each fermion contributes a vacuum-polarization loop weighted by the square of its electric charge. Therefore

$$
Z_A
=
1-\frac{e^2}{12\pi^2}\left(\sum_{f=1}^{N_f}Q_f^2\right)\frac{1}{\bar\epsilon}+O(e^4).
$$

The square appears because vacuum polarization has two photon-fermion vertices.

</details>

### Exercise 3: Why no photon mass counterterm?

Explain why a divergence proportional to $\eta^{\mu\nu}$ without a factor of $q^2$ or $q^\mu q^\nu$ would be unacceptable in the photon two-point function.

<details><summary><strong>Solution</strong></summary>

A term proportional to $\eta^{\mu\nu}$ in the inverse photon propagator corresponds to a local operator

$$
\frac12m_A^2 A_\mu A^\mu.
$$

This is a photon mass term. It is not invariant under the gauge transformation

$$
A_\mu\to A_\mu+\partial_\mu\alpha.
$$

The Ward identity requires the vacuum polarization to be transverse,

$$
q_\mu\Pi^{\mu\nu}=0,
$$

so the allowed local UV divergence is proportional to

$$
q^2\eta^{\mu\nu}-q^\mu q^\nu,
$$

which corresponds to the gauge-invariant operator $F_{\mu\nu}F^{\mu\nu}$.

</details>

### Exercise 4: Ward identity and counterterms

Use the Ward–Takahashi identity

$$
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p)
$$

to explain why the local UV pole in the vertex at zero momentum transfer must match the local UV pole in the derivative of the inverse fermion propagator.

<details><summary><strong>Solution</strong></summary>

Take $q$ small and expand the right-hand side:

$$
S^{-1}(p+q)-S^{-1}(p)
=
q_\mu\frac{\partial S^{-1}(p)}{\partial p_\mu}+O(q^2).
$$

The Ward–Takahashi identity then implies

$$
\Gamma^\mu(p,p)=\frac{\partial S^{-1}(p)}{\partial p_\mu}.
$$

The coefficient of the local $\gamma^\mu$ UV pole in the vertex is therefore tied to the coefficient of the local $p\!\!\!/$ UV pole in the inverse propagator. In terms of renormalization constants, this is $Z_1=Z_\psi$.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the chapters on loop corrections in spinor electrodynamics, QED beta functions, and Ward identities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on vacuum polarization, mass renormalization, renormalized perturbation theory, and QED Ward identities.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, for general renormalization theory and Ward identities in perturbative QED.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the counterterm and symmetry logic behind renormalization.

## Version history

- 2026-06-19: First polished draft. Added one-loop QED renormalization constants, Ward identity check, charge-renormalization relation, exercises, and figure.
