---
title: "Running Electric Charge"
description: "Explains how QED vacuum polarization produces the one-loop beta function, scale-dependent effective charge, threshold decoupling, and the Landau-pole warning."
sidebar:
  label: "Running Electric Charge"
  order: 10
level: Graduate
status: "Polished draft"
source: "Srednicki §66; Schwartz Chs. 16, 19, and 23; Weinberg Vol. I renormalization chapters; Zee chapters on vacuum polarization and charge renormalization."
topics:
  - running coupling
  - QED beta function
  - charge renormalization
  - vacuum polarization
  - Landau pole
canonicalTopics:
  - running-electric-charge
  - qed-beta-function
  - charge-renormalization
  - renormalization-group
researchStatus:
  established:
    - "The one-loop QED beta function is positive for charged matter and follows from the logarithmic part of vacuum polarization together with Ward identities."
  active:
    - "Precision definitions of effective electromagnetic couplings depend on thresholds, schemes, hadronic vacuum polarization, and the physical observable used to define the charge."
---

## Summary

The electric charge in QED depends on the scale at which it is measured. At long distances the charge is screened by virtual charged pairs; at short distances the probe penetrates the screening cloud and sees a larger effective charge.

For one Dirac fermion of dimensionless charge $Q_f$ and physical charge $q_f=eQ_f$, the one-loop beta function is

$$
\boxed{
\beta(e)\equiv\mu\frac{de}{d\mu}
=
\frac{e^3}{12\pi^2}Q_f^2
}
$$

or equivalently

$$
\boxed{
\beta(\alpha)\equiv\mu\frac{d\alpha}{d\mu}
=
\frac{2\alpha^2}{3\pi}Q_f^2,
\qquad
\alpha=\frac{e^2}{4\pi}.
}
$$

For several Dirac fermions, sum over charges and multiplicities:

$$
\beta(e)
=
\frac{e^3}{12\pi^2}\sum_f N_f Q_f^2
+
\frac{e^3}{48\pi^2}\sum_s N_s Q_s^2
+O(e^5),
$$

where the second sum is over charged complex scalars. Thus charged Dirac fermions contribute four times as much as charged complex scalars of the same charge and multiplicity.

At one loop, for a single unit-charged Dirac fermion active between $\mu_0$ and $\mu$,

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}
{1-\frac{2\alpha(\mu_0)}{3\pi}\log\frac{\mu}{\mu_0}}.
$$

So QED gets stronger at high energy. This is the opposite of non-Abelian asymptotic freedom, where gauge-boson self-interactions can make the coupling weaker at short distances.

<figure class="doc-figure" style="--figure-width: 38rem;">

![A schematic renormalization-group plot for QED: the inverse fine-structure constant decreases linearly with log scale at one loop, so the coupling grows toward the ultraviolet.](/figures/gauge-theories-standard-model/running-electric-charge.svg)

<figcaption>

One-loop QED running for one unit-charged Dirac fermion. The inverse coupling $\alpha^{-1}(\mu)$ decreases linearly with $\log\mu$, so $\alpha(\mu)$ increases toward shorter distances. The far-ultraviolet Landau pole is a warning about extrapolating perturbative QED beyond its domain, not a phenomenon seen in ordinary low-energy QED.

</figcaption>
</figure>

## Prerequisites

You should read [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) first. This page uses its tensor convention

$$
i\Pi^{\mu\nu}(k)
=
 i\left(k^\mu k^\nu-k^2\eta^{\mu\nu}\right)\Pi(k^2),
$$

so the transverse photon propagator is corrected as

$$
\frac{-i}{k^2+i\epsilon}
\longrightarrow
\frac{-i}{(k^2+i\epsilon)[1+\Pi(k^2)]}.
$$

You should also know the [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/), especially the charge-renormalization consequence $Z_1=Z_2$ in spinor QED. That identity is why the running of $e$ can be read from photon vacuum polarization alone.

## Core idea

A coupling constant is not a sacred number etched on the wall of the universe. It is a parameter defined by a measurement prescription at some scale. In QED, the natural question is:

$$
\text{What electric charge does a probe measure at distance }r\sim 1/\mu?
$$

Vacuum polarization answers this question. Virtual charged pairs partially screen a charge at long distances. A short-distance probe sees less of the screening cloud, so the effective charge is larger.

Mathematically, the same fact appears as a logarithm in the photon self-energy:

$$
\Pi_R(-Q_E^2)
\sim
-\frac{e^2}{12\pi^2}\log\frac{Q_E^2}{m^2}
\qquad(Q_E^2\gg m^2)
$$

for one unit-charged Dirac fermion. Since the corrected exchange amplitude contains

$$
\frac{e^2}{1+\Pi_R(-Q_E^2)},
$$

the negative logarithm in $\Pi_R$ makes the effective charge grow with $Q_E$.

The renormalization group packages this logarithmic dependence into a differential equation.

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+iq_f A_\mu,
\qquad
q_f=eQ_f,
$$

where $e>0$ is the magnitude of the proton charge and $Q_f$ is dimensionless. The electron has $Q_f=-1$, but vacuum polarization depends on $Q_f^2$.

The fine-structure constant is

$$
\alpha=\frac{e^2}{4\pi}.
$$

The beta function is defined by

$$
\beta(e)=\mu\frac{de}{d\mu},
\qquad
\beta(\alpha)=\mu\frac{d\alpha}{d\mu}.
$$

For spacelike momentum transfer we write

$$
Q_E^2=-k^2>0.
$$

Do not confuse this Euclidean momentum variable $Q_E$ with the dimensionless electric charge $Q_f$.

## Effective charge from vacuum polarization

For scattering by exchange of a virtual photon between conserved currents, the transverse part of the propagator controls the amplitude. Using the convention of the vacuum-polarization page,

$$
D_T(k)
=
\frac{-i}{(k^2+i\epsilon)[1+\Pi_R(k^2)]}.
$$

This motivates the momentum-dependent effective charge

$$
e_{\mathrm{eff}}^2(Q_E)
=
\frac{e^2}{1+\Pi_R(-Q_E^2)}.
$$

At large spacelike momentum, the one-loop on-shell-subtracted result for a unit-charged Dirac fermion is

$$
\Pi_R(-Q_E^2)
=
-\frac{e^2}{12\pi^2}\log\frac{Q_E^2}{m^2}
+\text{constant}+O(m^2/Q_E^2).
$$

Ignoring the non-logarithmic constant, which depends on the exact definition of the effective charge, gives

$$
e_{\mathrm{eff}}^2(Q_E)
\simeq
\frac{e^2}{1-\frac{e^2}{12\pi^2}\log\frac{Q_E^2}{m^2}}.
$$

Equivalently,

$$
\alpha_{\mathrm{eff}}(Q_E)
\simeq
\frac{\alpha}{1-\frac{\alpha}{3\pi}\log\frac{Q_E^2}{m^2}}
=
\frac{\alpha}{1-\frac{2\alpha}{3\pi}\log\frac{Q_E}{m}}.
$$

This already contains the one-loop beta function.

## Renormalization constants and the Ward identity

In renormalized spinor QED, one often writes

$$
A_{0\mu}=Z_3^{1/2}A_\mu,
\qquad
\psi_0=Z_2^{1/2}\psi,
\qquad
e_0=\mu^\epsilon Z_e e
$$

in $d=4-2\epsilon$ dimensions. The vertex and fermion wavefunction renormalizations are related by the Ward–Takahashi identity:

$$
Z_1=Z_2.
$$

As a result, the electric-charge renormalization is controlled by the photon field renormalization:

$$
Z_e=Z_3^{-1/2}
$$

in the usual normalization of QED. Intuitively, vertex and electron-leg corrections do not independently renormalize the electric charge; gauge invariance ties them together.

At one loop, the photon field renormalization has the schematic form

$$
Z_3
=
1-\frac{e^2}{12\pi^2\epsilon}Q_f^2+O(e^4)
$$

for one Dirac fermion of charge $Q_f$. Keeping the bare charge fixed and differentiating with respect to $\mu$ gives

$$
\beta(e)
=
\frac{e^3}{12\pi^2}Q_f^2+O(e^5).
$$

The positive sign is the perturbative expression of charge screening.

## Solving the one-loop RG equation

For one Dirac fermion of charge $Q_f$, the one-loop equation is

$$
\mu\frac{d\alpha}{d\mu}
=
\frac{2Q_f^2}{3\pi}\alpha^2.
$$

It is easier to solve for $1/\alpha$:

$$
\mu\frac{d}{d\mu}\left(\frac{1}{\alpha}\right)
=
-\frac{2Q_f^2}{3\pi}.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
\frac{1}{\alpha(\mu)}
=
\frac{1}{\alpha(\mu_0)}
-\frac{2Q_f^2}{3\pi}\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\alpha(\mu)
=
\frac{\alpha(\mu_0)}
{1-\frac{2Q_f^2\alpha(\mu_0)}{3\pi}\log\frac{\mu}{\mu_0}}.
$$

For multiple active Dirac fermions and complex scalars,

$$
\mu\frac{d}{d\mu}\left(\frac{1}{\alpha}\right)
=
-\frac{2}{3\pi}\sum_f N_fQ_f^2
-\frac{1}{6\pi}\sum_s N_sQ_s^2
+O(\alpha).
$$

Here “active” means the renormalization scale is high enough compared with the particle's mass that it contributes to the running in the chosen effective theory.

## Thresholds and decoupling

A charged particle of mass $m$ does not contribute equally at all scales. In a physical momentum-subtraction definition, the on-shell-subtracted vacuum polarization behaves for $Q_E^2\ll m^2$ as

$$
\Pi_R(-Q_E^2)
=
-\frac{q_f^2}{60\pi^2}\frac{Q_E^2}{m^2}+O(Q_E^4/m^4).
$$

So heavy charged particles decouple from low-momentum electromagnetic measurements.

In an $\overline{\mathrm{MS}}$ calculation, massive particles do not automatically disappear from beta functions when $\mu<m$. One usually constructs an effective theory below each threshold and matches the charge across the threshold:

$$
\alpha_{\mathrm{above}}(\mu=m)
=
\alpha_{\mathrm{below}}(\mu=m)
+\text{finite matching correction}.
$$

At one-loop order for elementary QED, choosing the matching scale near the mass keeps large logarithms out of the matching correction. This threshold logic becomes crucial in the Standard Model, QCD, and EFT.

## Landau pole warning

The one-loop solution has a formal pole when the denominator vanishes:

$$
1-\frac{2Q_f^2\alpha(\mu_0)}{3\pi}\log\frac{\mu}{\mu_0}=0.
$$

For one unit-charged Dirac fermion,

$$
\mu_{\mathrm{Landau}}
=
\mu_0\exp\left(\frac{3\pi}{2\alpha(\mu_0)}\right).
$$

Because $\alpha$ is small at ordinary energies, this scale is fantastically large in pure QED. The Landau pole should not be read as a directly observable energy scale of the real world. Real electromagnetism is embedded in the electroweak Standard Model, and new charged degrees of freedom enter at higher scales.

The safer lesson is conceptual: pure perturbative QED is not asymptotically free. Extrapolated by itself, it does not become a weakly coupled theory at arbitrarily high energies.

## Relation to screening

The sign of the beta function can be understood without doing the full integral. In ordinary dielectric matter, mobile charges rearrange to screen an external charge. The QED vacuum has no real particles at zero temperature, but virtual charged pairs still polarize. A distant probe sees the bare charge plus its polarization cloud as a smaller net charge. A short-distance probe resolves inside the cloud and sees a larger charge.

Thus,

$$
\mu\uparrow
\quad\Rightarrow\quad
\alpha(\mu)\uparrow
$$

for QED with charged matter.

Non-Abelian gauge theory adds a new effect: gauge bosons carry the non-Abelian charge and self-interact. Their contribution can dominate with the opposite sign, producing antiscreening and asymptotic freedom. QED has no photon self-interaction in the minimal Abelian gauge field, so matter screening wins.

## Scheme dependence and what is physical

The beta function's leading coefficient is universal in ordinary perturbative QED, but the phrase “the running electric charge” still needs a definition. Different schemes define the charge by different measurements or subtractions:

| Definition | What is fixed | Natural use |
|---|---|---|
| Thomson or on-shell charge | Long-distance low-energy scattering, effectively $k^2=0$ | Atomic physics and low-energy QED |
| Momentum-subtraction charge | Photon exchange at a chosen spacelike momentum | Physical intuition about screening |
| $\overline{\mathrm{MS}}$ charge | Minimal pole subtraction at scale $\mu$ | Loop calculations and RG-improved perturbation theory |

The first coefficient of the beta function is not the problem. The finite constants in $\alpha_{\mathrm{eff}}(Q_E)$ do depend on how the charge is defined. Observables do not depend on this choice when all pieces are computed consistently.

## Common pitfalls

**Thinking the electron charge changes in time.** Running is scale dependence, not time evolution. It tells you how the charge parameter changes when the measurement scale or renormalization scale changes.

**Confusing $Q_f$ with $Q_E$.** This page uses $Q_f$ for dimensionless electric charge and $Q_E$ for Euclidean momentum. One is a representation label; the other is a momentum scale.

**Forgetting thresholds.** A muon does not affect atomic-scale QED in the same way it affects high-energy scattering. Heavy charged particles decouple from low-energy physical charge measurements.

**Calling the Landau pole a prediction of a real catastrophe.** The pole is a warning about extrapolating pure perturbative QED. It is not a verified physical singularity of the real Standard Model.

**Using $\alpha(Q_E)$ without saying the scheme.** A running coupling is a convention-dependent intermediate object. Cross sections, decay rates, energy levels, and other observables are the physical quantities.

**Missing the Ward-identity simplification.** In spinor QED, $Z_1=Z_2$ means charge renormalization can be read from the photon field renormalization. Without the Ward identity, vertex and external-leg corrections would have to be tracked separately.

**Assuming all gauge theories screen like QED.** Non-Abelian gauge theories contain charged gauge bosons. Their self-interactions can make the beta function negative.

## Relations to other pages

- [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) derives the logarithm that produces the running charge.
- [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) explains why charge renormalization is constrained by $Z_1=Z_2$.
- [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/) introduces the counterterm structure that absorbs the vacuum-polarization divergence.
- Later Yang–Mills and QCD pages explain how non-Abelian self-interactions reverse the sign of the beta function.
- The Renormalization, RG, and EFT volume develops scheme dependence, matching, decoupling, and RG-improved perturbation theory in a more general framework.

## Research status

The one-loop QED beta function is established textbook physics. It is one of the standard examples showing how renormalization turns logarithms in loop diagrams into scale-dependent couplings.

The precision use of electromagnetic running is more subtle. At high precision, one must specify the observable definition of $\alpha$, include leptonic and hadronic vacuum polarization, account for thresholds, and combine QED with electroweak corrections. Those refinements live closer to precision Standard Model physics, but the conceptual backbone is the one-loop screening calculation on this page.

## Exercises

1. **Solve the beta function.** Starting from

   $$
   \mu\frac{d\alpha}{d\mu}=b\alpha^2,
   $$

   derive the one-loop running formula for $\alpha(\mu)$.

   <details><summary><strong>Solution</strong></summary>

   Write $t=\log\mu$. Then

   $$
   \frac{d\alpha}{dt}=b\alpha^2.
   $$

   Equivalently,

   $$
   \frac{d}{dt}\left(\frac{1}{\alpha}\right)
   =
   -\frac{1}{\alpha^2}\frac{d\alpha}{dt}
   =-b.
   $$

   Integrating from $\mu_0$ to $\mu$ gives

   $$
   \frac{1}{\alpha(\mu)}
   =
   \frac{1}{\alpha(\mu_0)}-b\log\frac{\mu}{\mu_0}.
   $$

   Therefore

   $$
   \alpha(\mu)
   =
   \frac{\alpha(\mu_0)}{1-b\alpha(\mu_0)\log(\mu/\mu_0)}.
   $$

   For one unit-charged Dirac fermion, $b=2/(3\pi)$.

   </details>

2. **Convert beta functions.** Show that

   $$
   \beta(e)=\frac{e^3}{12\pi^2}
   $$

   implies

   $$
   \beta(\alpha)=\frac{2\alpha^2}{3\pi}.
   $$

   <details><summary><strong>Solution</strong></summary>

   Since $\alpha=e^2/(4\pi)$,

   $$
   \beta(\alpha)
   =
   \mu\frac{d}{d\mu}\left(\frac{e^2}{4\pi}\right)
   =
   \frac{e}{2\pi}\beta(e).
   $$

   Inserting $\beta(e)=e^3/(12\pi^2)$ gives

   $$
   \beta(\alpha)
   =
   \frac{e^4}{24\pi^3}.
   $$

   But $e^4=(4\pi\alpha)^2=16\pi^2\alpha^2$, so

   $$
   \beta(\alpha)
   =
   \frac{16\pi^2\alpha^2}{24\pi^3}
   =
   \frac{2\alpha^2}{3\pi}.
   $$

   </details>

3. **Charge multiplicities.** Suppose a theory has two Dirac fermions of charges $Q_1=1$ and $Q_2=2$, both active at the scale $\mu$. What is the one-loop coefficient in

   $$
   \beta(\alpha)=b\alpha^2?
   $$

   <details><summary><strong>Solution</strong></summary>

   The coefficient for Dirac fermions is

   $$
   b=\frac{2}{3\pi}\sum_f Q_f^2.
   $$

   Here

   $$
   \sum_f Q_f^2=1^2+2^2=5.
   $$

   Thus

   $$
   b=\frac{10}{3\pi}.
   $$

   </details>

4. **Landau-pole scale.** For one unit-charged Dirac fermion, solve for the scale at which the one-loop denominator vanishes.

   <details><summary><strong>Solution</strong></summary>

   The denominator is

   $$
   1-\frac{2\alpha(\mu_0)}{3\pi}\log\frac{\mu}{\mu_0}.
   $$

   Setting it to zero gives

   $$
   \log\frac{\mu}{\mu_0}
   =
   \frac{3\pi}{2\alpha(\mu_0)}.
   $$

   Therefore

   $$
   \mu_{\mathrm{Landau}}
   =
   \mu_0\exp\left(\frac{3\pi}{2\alpha(\mu_0)}\right).
   $$

   Because $\alpha(\mu_0)$ is small in ordinary QED, this is enormously larger than $\mu_0$.

   </details>

5. **Low-energy decoupling.** Use the low-momentum expansion of vacuum polarization to explain why a heavy charged particle does not contribute a logarithmic running term to a physical low-energy charge measurement.

   <details><summary><strong>Solution</strong></summary>

   For $Q_E^2\ll m^2$, the on-shell-subtracted vacuum polarization behaves as

   $$
   \Pi_R(-Q_E^2)
   =
   -\frac{q_f^2}{60\pi^2}\frac{Q_E^2}{m^2}+O(Q_E^4/m^4).
   $$

   This is power-suppressed, not logarithmically enhanced. Therefore the heavy charged particle affects low-energy photon exchange only through small local corrections suppressed by powers of $1/m^2$. In an effective field theory below the heavy-particle threshold, the particle is integrated out and its effect is stored in matching coefficients rather than in active low-energy running.

   </details>

## References

- Srednicki, *Quantum Field Theory*, §66, for the QED beta function and its relation to vacuum polarization.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 16, 19, and 23, for vacuum polarization, counterterms, and running couplings.
- Zee, *Quantum Field Theory in a Nutshell*, chapters on vacuum polarization and renormalizing the charge, for physical intuition about screening.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on QED renormalization and Ward identities.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic renormalization-group treatment of QED and charge definitions.

## Version history

- **2026-06-17:** Initial polished draft. Explains the QED beta function, effective charge, threshold decoupling, scheme dependence, and Landau-pole warning in the volume conventions.
