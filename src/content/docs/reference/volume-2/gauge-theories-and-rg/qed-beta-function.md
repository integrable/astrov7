---
title: "QED Beta Function"
description: "A derivation-oriented explanation of the one-loop QED beta function, charge screening, vacuum polarization, Ward identities, thresholds, and the Landau-pole tendency."
sidebar:
  label: "QED Beta Function"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§62–68; Schwartz 2014, chs. 16, 19, 23, and 26; Coleman 1985, dilatations and asymptotic freedom lectures; Weinberg Vol. II, ch. 18; Zee 2010, renormalization and QED chapters."
topics:
  - QED beta function
  - vacuum polarization
  - charge screening
  - Ward identity
  - running coupling
  - Landau pole
canonicalTopics:
  - qed-beta-function
  - vacuum-polarization
  - running-electric-charge
researchStatus:
  established:
    - "The one-loop QED beta function, its relation to vacuum polarization, and the Ward-identity constraint on charge renormalization are standard perturbative QFT results."
  active:
    - "Precision QED, multi-loop running, threshold schemes, infrared-safe observables, and QED embedded in the full Standard Model require additional bookkeeping beyond this first conceptual pass."
---

## Summary

The **QED beta function** describes how the renormalized electric charge changes with the subtraction scale. In the conventions of this volume,

$$
\beta_e(e)\equiv \left.\mu\frac{de}{d\mu}\right|_{e_0,m_0,\text{bare fields fixed}}.
$$

For one Dirac fermion of unit electric charge, the one-loop result in four dimensions is

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5).
$$

Equivalently, with

$$
\alpha\equiv \frac{e^2}{4\pi},
$$

one has

$$
\beta_\alpha\equiv \mu\frac{d\alpha}{d\mu}
=\frac{2}{3\pi}\alpha^2+O(\alpha^3).
$$

For Dirac fermions with charges $Q_i$ in units of the coupling $e$, the one-loop coefficient is multiplied by $\sum_i Q_i^2$:

$$
\beta_e=\frac{e^3}{12\pi^2}\sum_i Q_i^2+O(e^5),
\qquad
\beta_\alpha=\frac{2}{3\pi}\left(\sum_i Q_i^2\right)\alpha^2+O(\alpha^3),
$$

as long as the active fermions are light compared with the scale at which the coupling is being run.

The sign is the physics. Since $\beta_e>0$, the QED coupling grows as $\mu$ is increased toward the ultraviolet and decreases toward the infrared. In position-space language, the vacuum is polarizable: virtual charged pairs screen electric charge at long distances, so a shorter-distance probe sees a larger effective charge.

:::note[The most important lesson]
The QED beta function is not a mysterious property of a divergent integral. It is the renormalization-group version of vacuum polarization. Charged matter screens electric charge.
:::

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), and the overview [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/).

For the diagrammatic calculation, review one-loop vacuum polarization in the perturbative QFT volume when available. This page uses that calculation as input and focuses on its RG meaning.

## Core idea

In QED, the electric charge is not measured by opening the Lagrangian and reading off a number. It is measured by the response of charged particles and photons at some physical scale. Quantum loops of charged matter modify the photon propagator. This modification is called **vacuum polarization**.

At momentum transfer $q$, the photon two-point function receives a transverse correction of the form

$$
\Pi^{\mu\nu}(q)=
\left(q^\mu q^\nu-q^2\eta^{\mu\nu}\right)\Pi(q^2),
$$

where transversality follows from gauge invariance:

$$
q_\mu\Pi^{\mu\nu}(q)=0.
$$

The logarithmic ultraviolet part of $\Pi(q^2)$ is local in the action because it multiplies $q^2\eta^{\mu\nu}-q^\mu q^\nu$, the momentum-space structure of $F_{\mu\nu}F^{\mu\nu}$. Thus the divergence renormalizes the photon kinetic term, and through the Ward identity it renormalizes the electric charge.

The chain is

$$
\text{charged matter loop}
\longrightarrow
\text{photon kinetic renormalization}
\longrightarrow
\text{charge renormalization}
\longrightarrow
\beta_e>0.
$$

In Abelian gauge theory, the Ward identity makes this chain unusually clean. It says that the vertex and fermion wavefunction renormalizations are tied together, so charge renormalization may be read from the photon field renormalization alone.

## Setup and conventions

We use mostly-minus metric conventions and write the QED Lagrangian as

$$
\mathcal L
=-\frac14 F_{\mu\nu}F^{\mu\nu}
+\sum_i \bar\psi_i\left(i\gamma^\mu D_\mu-m_i\right)\psi_i,
$$

with

$$
D_\mu=\partial_\mu+i e Q_i A_\mu.
$$

Here $Q_i$ is the charge of species $i$ in units of the basic coupling $e$. For a single electron field one may take $Q=-1$, but the one-loop beta function depends on $Q^2$, so the sign of the charge does not matter.

In dimensional regularization near four dimensions,

$$
d=4-2\epsilon,
$$

and we write the bare and renormalized fields as

$$
A_{0\mu}=Z_A^{1/2}A_\mu,
\qquad
\psi_{0i}=Z_{\psi_i}^{1/2}\psi_i.
$$

The bare charge is written

$$
e_0=\mu^\epsilon Z_e e.
$$

Gauge invariance, expressed through the Ward identity, gives the Abelian relation

$$
Z_e=Z_A^{-1/2}
$$

when the charge is defined through the usual QED vertex. Equivalently,

$$
e_0=\mu^\epsilon Z_A^{-1/2}e.
$$

This relation is the reason the QED beta function can be extracted from the photon vacuum polarization.

We use

$$
\frac{1}{\bar\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log(4\pi),
$$

and subtract $1/\bar\epsilon$ poles in $\overline{\mathrm{MS}}$ unless stated otherwise. Replacing $1/\bar\epsilon$ by $1/\epsilon$ gives the MS version; the one-loop beta-function coefficient is the same.

## Vacuum polarization and the local counterterm

The one-loop photon self-energy is the fermion loop with two external photons. Its tensor structure is fixed by gauge invariance:

$$
i\Pi^{\mu\nu}(q)
=i\left(q^\mu q^\nu-q^2\eta^{\mu\nu}\right)\Pi(q^2).
$$

The divergent part has the form

$$
\Pi(q^2)_{\text{div}}
=-\frac{e^2}{12\pi^2}
\left(\sum_i Q_i^2\right)
\frac{1}{\bar\epsilon}
+O(e^4),
$$

in the counterterm convention where

$$
Z_A=1-\frac{e^2}{12\pi^2}
\left(\sum_i Q_i^2\right)
\frac{1}{\bar\epsilon}+O(e^4).
$$

The corresponding photon kinetic term is

$$
-\frac14 Z_A F_{\mu\nu}F^{\mu\nu}
=-\frac14 F_{\mu\nu}F^{\mu\nu}
-\frac14\delta Z_A F_{\mu\nu}F^{\mu\nu}.
$$

The divergence is local because it has the same momentum dependence as the Maxwell term. The finite nonlocal remainder contains logarithms such as

$$
\log\frac{-q^2}{\mu^2}
$$

in Lorentzian momentum-space conventions, with the usual $i\epsilon$ continuation understood.

The split into a divergent counterterm and a finite logarithm is scheme dependent. The coefficient of the leading logarithmic running is not.

## Extracting the beta function

Use

$$
e_0=\mu^\epsilon Z_A^{-1/2}e.
$$

With

$$
Z_A^{-1/2}
=1+\frac{e^2}{24\pi^2}
\left(\sum_i Q_i^2\right)
\frac{1}{\bar\epsilon}+O(e^4),
$$

we have

$$
e_0=
\mu^\epsilon e
\left[1+\frac{e^2}{24\pi^2}
\left(\sum_i Q_i^2\right)
\frac{1}{\bar\epsilon}+O(e^4)\right].
$$

The bare coupling $e_0$ is independent of $\mu$. Differentiating at fixed $e_0$ gives, in $d=4-2\epsilon$,

$$
\beta_e=-\epsilon e+\frac{e^3}{12\pi^2}
\left(\sum_i Q_i^2\right)+O(e^5).
$$

Taking $\epsilon\to0$ gives the four-dimensional beta function

$$
\boxed{
\beta_e=\frac{e^3}{12\pi^2}
\left(\sum_i Q_i^2\right)+O(e^5)
}
$$

for active Dirac fermions.

For $\alpha=e^2/(4\pi)$,

$$
\beta_\alpha
=\mu\frac{d}{d\mu}\left(\frac{e^2}{4\pi}\right)
=\frac{e}{2\pi}\beta_e,
$$

so

$$
\boxed{
\beta_\alpha
=\frac{2}{3\pi}
\left(\sum_i Q_i^2\right)\alpha^2+O(\alpha^3)
}.
$$

The factor $\sum_iQ_i^2$ expresses a simple fact: every light charged Dirac fermion species contributes to vacuum polarization in proportion to the square of its charge.

## Screening interpretation

A classical dielectric screens electric charge. If one inserts a positive test charge into a polarizable medium, negative charges are attracted toward it and positive charges are pushed away. A long-distance observer sees the original charge plus the polarization cloud, so the apparent charge is reduced.

The QED vacuum behaves similarly. The electron-positron field polarizes around an external charge. At long distances the effective charge is screened. At shorter distances one penetrates more of the screening cloud and sees a larger effective charge.

This is why the sign $\beta_e>0$ means screening rather than antiscreening. With $\mu$ interpreted as the momentum resolution, increasing $\mu$ probes shorter distances. The charge grows toward the ultraviolet:

$$
\mu\uparrow
\quad\Longrightarrow\quad
\alpha(\mu)\uparrow.
$$

Equivalently,

$$
\mu\downarrow
\quad\Longrightarrow\quad
\alpha(\mu)\downarrow.
$$

The word "screening" is an infrared statement; the beta-function sign is a UV-flow statement. They are the same statement read in opposite directions.

## One-loop running and the Landau-pole tendency

At one loop, for a fixed set of active Dirac fermions,

$$
\frac{d\alpha}{d\log\mu}
=b\alpha^2,
\qquad
b=\frac{2}{3\pi}\sum_i Q_i^2.
$$

This differential equation integrates to

$$
\frac{1}{\alpha(\mu)}
=
\frac{1}{\alpha(\mu_0)}
-b\log\frac{\mu}{\mu_0}.
$$

Thus

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}{1-b\alpha(\mu_0)\log(\mu/\mu_0)}.
$$

If one extrapolates this one-loop formula far beyond its domain of reliability, the denominator vanishes at

$$
\Lambda_L
=\mu_0\exp\left[
\frac{1}{b\alpha(\mu_0)}
\right]
=
\mu_0\exp\left[
\frac{3\pi}{2\alpha(\mu_0)\sum_iQ_i^2}
\right].
$$

This scale is called the **Landau pole**. In real particle physics, QED is embedded in the electroweak Standard Model before such an extrapolation is meaningful. The Landau-pole lesson is still conceptually important: pure perturbative QED does not become weakly coupled at arbitrarily short distances.

## Thresholds and active charges

The formula

$$
\beta_\alpha
=\frac{2}{3\pi}\left(\sum_i Q_i^2\right)\alpha^2
$$

assumes that all listed fermions are active at the scale of interest. A charged particle with mass $m$ contributes fully to running at scales well above $m$ and decouples from low-energy observables at scales well below $m$ after matching.

The clean EFT workflow is:

$$
\text{run above }m
\quad\longrightarrow\quad
\text{match near }\mu\sim m
\quad\longrightarrow\quad
\text{run below }m\text{ without that field}.
$$

In mass-independent schemes such as MS and $\overline{\mathrm{MS}}$, heavy fields do not automatically disappear from beta functions. One must explicitly construct the lower-energy EFT and match the coupling. In physical momentum-subtraction schemes, decoupling may appear more directly in the running coupling, but the price is more complicated mass dependence.

The statement "a particle contributes to the beta function" therefore always means "a particle contributes in the chosen EFT and scheme over the scale range where it is active."

## Ward identity and charge renormalization

A naive QED calculation contains several renormalization constants:

$$
A_{0\mu}=Z_A^{1/2}A_\mu,
\qquad
\psi_0=Z_\psi^{1/2}\psi,
\qquad
e_0=\mu^\epsilon Z_e e,
$$

and a vertex renormalization constant $Z_1$. The QED Ward identity implies

$$
Z_1=Z_\psi
$$

for the usual electron-photon vertex. Therefore the charge renormalization is tied to the photon wavefunction renormalization:

$$
Z_e=Z_A^{-1/2}.
$$

This is special to Abelian gauge theory. In non-Abelian gauge theory, Slavnov–Taylor identities play the analogous role, but they involve ghosts, gauge self-interactions, and more complicated relations among renormalization constants.

The Ward identity is also a diagnostic. If a regulator or approximation produces a photon self-energy that is not transverse, or a vertex renormalization inconsistent with $Z_1=Z_\psi$, the calculation has broken gauge invariance or has not been organized correctly.

## The result in terms of photon field renormalization

Because of the Ward identity, QED provides a useful mnemonic:

$$
\text{charge running}
\quad\Longleftrightarrow\quad
\text{photon field renormalization}.
$$

Using

$$
e_0 A_{0\mu}=\mu^\epsilon e A_\mu
$$

shows that the product of the bare charge and bare photon field is fixed by the renormalized product. If $A_{0\mu}=Z_A^{1/2}A_\mu$, then

$$
e_0=\mu^\epsilon Z_A^{-1/2}e.
$$

Thus a negative divergent correction to $Z_A$ corresponds to a positive correction to $Z_A^{-1/2}$ and hence to a positive beta function for $e$.

This is a good place to be fussy about signs: different authors define $\Pi(q^2)$, $Z_3$, $Z_A$, and the counterterm Lagrangian with slightly different signs. The invariant content is the positive one-loop $\beta_e$ in the convention $\beta_e=\mu de/d\mu$.

## Relation to physical charge definitions

Several objects are all casually called "the electric charge":

| Object | Meaning |
|---|---|
| $e_0$ | bare coupling in the regulated Lagrangian |
| $e(\mu)$ | renormalized coupling in a scheme such as $\overline{\mathrm{MS}}$ |
| $e_{\text{phys}}(Q)$ | effective charge inferred from an observable at momentum scale $Q$ |
| $e_{\text{Thomson}}$ | low-energy charge defined by Thomson scattering or static Coulomb normalization |

These are related, but they are not identical. The beta function tells us how $e(\mu)$ changes with the arbitrary subtraction scale. A physical effective charge also depends on the observable used to define it and on threshold/infrared conventions.

In simple high-momentum Euclidean comparisons, choosing $\mu\sim Q$ makes the connection transparent: logarithms are minimized, and the running coupling captures the leading scale dependence. In precision QED, one must also handle masses, real radiation, infrared safety, and electroweak effects.

## Common pitfalls

**Saying the charge runs because the bare charge runs.** The bare charge is held fixed when deriving the beta function. The renormalized charge runs because the same bare theory is described using different subtraction scales.

**Confusing screening with the sign of the Coulomb potential.** QED screening means the effective magnitude of electric charge is reduced at long distances. It does not mean like charges attract.

**Forgetting thresholds.** A muon does not contribute to low-energy atomic physics in the same way it contributes to running at momenta far above the muon mass. Decoupling requires matching.

**Treating the Landau pole as a measured physical singularity.** The QED Landau pole is an extrapolation of perturbation theory and of a simplified theory. Its lesson is about UV behavior, not a directly observed pole in nature.

**Ignoring the Ward identity.** In QED, charge renormalization is not independent of photon field renormalization. If the calculation treats them independently without enforcing the Ward identity, something is probably wrong.

**Comparing beta functions without matching charge conventions.** Some authors define the coupling with factors of $4\pi$, absorb charges into generators, or quote beta functions for $\alpha$, $e$, or $1/e^2$. Always translate before comparing signs and coefficients.

## Relations to other pages

This page is the Abelian starting point for [Gauge Theories and RG](/renormalization-rg-eft/gauge-theories-and-rg/). The next page, [Yang–Mills Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/yang-mills-beta-function/), explains why non-Abelian gauge fields reverse the sign when gauge-boson antiscreening dominates matter screening.

For the general framework, see [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/). For the field and counterterm side, see [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) and [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/).

The Ward-identity side is developed later in [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/). The EFT side of thresholds is developed in [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/).

## Research status

The one-loop QED beta function and its interpretation as charge screening are settled textbook material. The result is one of the cleanest places to see how gauge invariance, vacuum polarization, counterterms, and RG flow fit together.

The precision frontier is not the existence of the one-loop beta function. It is the careful use of QED inside realistic calculations: multi-loop corrections, mass thresholds, infrared-safe observables, bound-state effects, hadronic vacuum polarization, and matching QED to the electroweak Standard Model and low-energy EFTs.

Conceptually, QED also remains a useful example in discussions of triviality and UV completion. The Landau-pole tendency of perturbative QED is a warning that a low-energy effective gauge theory need not define a complete theory at arbitrarily high energies.

## Exercises

### Exercise 1: From beta e to beta alpha

Assume

$$
\beta_e=\frac{e^3}{12\pi^2}N
$$

for $N=\sum_iQ_i^2$. Derive the beta function for $\alpha=e^2/(4\pi)$.

<details><summary><strong>Solution</strong></summary>

Differentiate

$$
\alpha=\frac{e^2}{4\pi}
$$

with respect to $\log\mu$:

$$
\beta_\alpha
=\mu\frac{d\alpha}{d\mu}
=\frac{e}{2\pi}\beta_e.
$$

Substituting the given beta function gives

$$
\beta_\alpha
=\frac{e}{2\pi}\frac{e^3}{12\pi^2}N
=\frac{e^4}{24\pi^3}N.
$$

Since $e^4=(4\pi\alpha)^2=16\pi^2\alpha^2$,

$$
\beta_\alpha
=\frac{16\pi^2}{24\pi^3}N\alpha^2
=\frac{2N}{3\pi}\alpha^2.
$$

</details>

### Exercise 2: One-loop Landau scale

For one charge-one Dirac fermion, solve

$$
\frac{d\alpha}{d\log\mu}=\frac{2}{3\pi}\alpha^2
$$

with initial condition $\alpha(\mu_0)=\alpha_0$. At what scale does the one-loop expression diverge?

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\alpha}{\alpha^2}=\frac{2}{3\pi}d\log\mu.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
-\frac{1}{\alpha(\mu)}+\frac{1}{\alpha_0}
=\frac{2}{3\pi}\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\frac{1}{\alpha(\mu)}
=\frac{1}{\alpha_0}-\frac{2}{3\pi}\log\frac{\mu}{\mu_0}.
$$

The denominator of $\alpha(\mu)$ vanishes when

$$
\log\frac{\Lambda_L}{\mu_0}=\frac{3\pi}{2\alpha_0},
$$

so

$$
\Lambda_L=\mu_0\exp\left(\frac{3\pi}{2\alpha_0}\right).
$$

</details>

### Exercise 3: Threshold bookkeeping

Suppose a theory has an electron-like fermion of charge $1$ and a heavy Dirac fermion of charge $2$ and mass $M$. What is $\sum_iQ_i^2$ well above $M$? What is it well below $M$ in the EFT where the heavy fermion has been integrated out?

<details><summary><strong>Solution</strong></summary>

Well above $M$, both fermions are active, so

$$
\sum_iQ_i^2=1^2+2^2=5.
$$

Well below $M$, the heavy charge-$2$ fermion is not an explicit light degree of freedom in the EFT. The active sum is therefore

$$
\sum_iQ_i^2=1.
$$

The two EFTs are related by matching near $\mu\sim M$. The heavy fermion can still affect low-energy physics through finite threshold corrections and higher-dimension local operators, but it no longer appears as an active contribution to the low-energy QED beta function.

</details>

### Exercise 4: Ward identity and charge renormalization

Assume the Ward identity gives $Z_1=Z_\psi$ for the electron-photon vertex. Show that charge renormalization is controlled by $Z_A$.

<details><summary><strong>Solution</strong></summary>

The bare interaction may be written schematically as

$$
e_0\bar\psi_0\gamma^\mu A_{0\mu}\psi_0.
$$

Using

$$
\psi_0=Z_\psi^{1/2}\psi,
\qquad
A_{0\mu}=Z_A^{1/2}A_\mu,
$$

the interaction coefficient expressed in renormalized fields contains

$$
e_0 Z_\psi Z_A^{1/2}.
$$

The vertex renormalization is usually represented by $Z_1$, while the fermion external normalization contributes $Z_\psi$. The Ward identity $Z_1=Z_\psi$ cancels the independent vertex and fermion renormalizations in the charge definition. Thus

$$
e_0=\mu^\epsilon Z_A^{-1/2}e,
$$

or equivalently $Z_e=Z_A^{-1/2}$.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the chapters on spinor electrodynamics, QED beta functions, Ward identities, and background-field methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on vacuum polarization, mass and charge renormalization, and the renormalization group.
- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on dilatations, renormalization, and asymptotic freedom.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the renormalization-group methods chapter.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the chapters on renormalization, vacuum polarization, and charge renormalization.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, for a standard diagrammatic treatment of QED vacuum polarization and charge renormalization.

## Version history

- 2026-06-18: First polished draft. Added one-loop QED beta function, Ward-identity derivation, screening interpretation, threshold discussion, Landau-pole tendency, and exercises.
