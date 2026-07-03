---
title: "Worldline Effective Field Theory"
description: "Worldline EFT for compact objects and localized probes: multipole expansions, spin, tidal operators, matching, radiation, and long-distance observables."
sidebar:
  label: "Worldline Effective Field Theory"
  order: 110
level: Advanced
status: "Polished draft"
source: "Goldberger and Rothstein 2006; Porto reviews; Levi reviews; Donoghue and Burgess on gravitational EFT; effective action and multipole-expansion literature."
topics:
  - worldline EFT
  - compact objects
  - multipole expansion
  - tidal operators
  - spin EFT
  - gravitational waves
canonicalTopics:
  - worldline-effective-field-theory
  - compact-object-effective-field-theory
  - multipole-expansion
researchStatus:
  established:
    - "Localized objects can be represented at long distances by worldline degrees of freedom plus local operators whose Wilson coefficients encode finite-size, spin, tidal, and dissipative response."
  active:
    - "High-order post-Newtonian and post-Minkowskian calculations, spinning bodies, dissipative horizons, tidal response, radiation reaction, and amplitude-based worldline methods remain active research areas."
---

## Summary

**Worldline effective field theory** is the EFT of localized objects seen from distances much larger than their size. A proton in an atomic bound state, an atom in a long-wavelength electromagnetic field, a neutron star in a binary, and a black hole emitting gravitational waves are all too complicated to describe microscopically in every calculation. At long distances, each can be replaced by a worldline carrying local operators.

The basic hierarchy is

$$
R\ll L,
$$

where $R$ is the size of the object and $L$ is the wavelength, orbital separation, curvature radius, or external-field variation scale being probed. The detailed internal dynamics is encoded in Wilson coefficients:

$$
S_{\text{worldline}}
= -m\int d\tau
+S_{\text{spin}}
+\int d\tau\sum_i C_i\mathcal O_i[x^\mu(\tau),u^\mu(\tau),S^{\mu\nu}(\tau),\text{external fields}].
$$

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![Worldline EFT workflow from extended object to worldline degrees of freedom, local multipole operators, matching, renormalization, and long-distance observables.](/figures/renormalization-rg-eft/worldline-effective-field-theory-map.svg)

<figcaption>

Worldline EFT replaces an extended object by a trajectory plus local operators. Symmetry fixes the operator basis, matching fixes Wilson coefficients such as charges, polarizabilities, spin couplings, tidal Love numbers, and absorption coefficients, and long-distance calculations use only the worldline action.

</figcaption>
</figure>

Worldline EFT is the particle analog of ordinary EFT. Instead of expanding a local spacetime Lagrangian in fields and derivatives, one expands a line action in local operators evaluated on a trajectory. The small parameter is usually a ratio such as

$$
\frac{R}{L},
\qquad
v,
\qquad
\frac{\omega R}{1},
\qquad
\frac{Gm}{r},
$$

depending on the physical problem.

## Prerequisites

You should know the logic of [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/), especially [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), and [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/). You should also be comfortable with classical point-particle actions, multipole expansions, and basic general covariance.

This page uses $x^\mu(\tau)$ for the worldline, $u^\mu=dx^\mu/d\tau$ for the four-velocity, and $\tau$ for proper time when the object is massive. In mostly-minus signature,

$$
u^\mu u_\mu=1.
$$

## Core idea

An extended object has many internal degrees of freedom. A long-wavelength observer cannot resolve them individually. The observer can measure only collective parameters: mass, charge, spin, multipole moments, polarizabilities, tidal response, absorption, and radiation couplings.

Worldline EFT makes this statement systematic. Replace the extended object by a trajectory and write every local operator allowed by symmetries:

$$
S_{\text{eff}}[x,\text{fields}]
=\int d\tau\,L_{\text{worldline}}.
$$

The leading term for a spinless neutral massive object is

$$
S_0=-m\int d\tau.
$$

Coupling to electromagnetism gives

$$
S_q=q\int d\tau\,u^\mu A_\mu(x(\tau)).
$$

Coupling to gravity is automatic through the proper time element,

$$
d\tau=\sqrt{g_{\mu\nu}(x)dx^\mu dx^\nu},
$$

with sign conventions adjusted to the chosen metric signature. Finite-size effects appear as higher-dimension worldline operators.

The worldline action is not just a classical trick. In quantum field theory, it is an EFT action. It can be used in path integrals, Feynman diagrams, matching calculations, and RG equations. Point-particle divergences are absorbed into worldline counterterms, just as bulk UV divergences are absorbed into bulk counterterms.

## A scalar toy model

Consider a compact object coupled to a scalar field $\phi$. At long distances, the most general spinless worldline action begins as

$$
S_{\text{wl}}
= -m\int d\tau
+\int d\tau\left[
q\phi(x(\tau))
+c_1\nabla_\perp^\mu\phi\nabla_{\perp\mu}\phi
+c_2(u^\mu\partial_\mu\phi)^2
+c_3\phi^2
+\cdots
\right].
$$

Here $q$ is a scalar charge, and $\nabla_\perp$ denotes derivatives transverse to the worldline. The coefficients $c_i$ encode short-distance structure. Different microscopic objects can have the same leading charge $q$ but different polarizabilities $c_i$.

Why local operators? Because at wavelengths much larger than the object,

$$
\phi(x+\delta x)
=\phi(x)+\delta x^i\partial_i\phi(x)+\frac12\delta x^i\delta x^j\partial_i\partial_j\phi(x)+\cdots.
$$

The external field varies slowly across the object. The object therefore couples to the field and its derivatives evaluated at the center-of-mass worldline. This is just a multipole expansion, written as EFT.

## Electromagnetic polarizability

For a neutral spinless object in electromagnetism, gauge invariance forbids a direct $A_\mu$ coupling but allows couplings to field strengths. In the object's rest frame, the leading polarizability terms are schematically

$$
S_{\text{pol}}
=\frac12\int d\tau\left[
\alpha_E E_\mu E^\mu
+\alpha_B B_\mu B^\mu
+\cdots
\right],
$$

where $E^\mu$ and $B^\mu$ are electric and magnetic fields measured in the local rest frame. The Wilson coefficients $\alpha_E$ and $\alpha_B$ are electric and magnetic polarizabilities.

The same logic describes atoms, nuclei, hadrons, and compact objects. Long-distance probes do not need the microscopic wavefunction of the object; they need its allowed worldline operators and matched coefficients.

## Gravitational compact-object EFT

In gravity, worldline EFT is especially powerful for compact binaries. For a nonspinning compact object, the leading action is

$$
S=-m\int d\tau.
$$

Finite-size effects begin with tidal couplings built from the electric and magnetic parts of the Weyl tensor:

$$
E_{\mu\nu}=C_{\mu\alpha\nu\beta}u^\alpha u^\beta,
$$

and

$$
B_{\mu\nu}=\frac12\epsilon_{\mu\alpha\rho\sigma}C^{\rho\sigma}{}_{\nu\beta}u^\alpha u^\beta.
$$

The leading parity-even tidal action has the schematic form

$$
S_{\text{tidal}}
=\frac12\int d\tau\left[
C_E E_{\mu\nu}E^{\mu\nu}
+C_B B_{\mu\nu}B^{\mu\nu}
+\cdots
\right].
$$

The coefficients $C_E$ and $C_B$ encode tidal response. In compact-binary physics, they are related to Love numbers and finite-size effects. They can be matched by comparing the long-distance gravitational field of the full object with the field produced by the worldline EFT.

The EFT cleanly separates scales:

| Scale | Meaning in a compact binary |
|---|---|
| $R$ | size of each compact object |
| $r$ | orbital separation |
| $r/v$ | radiation wavelength |
| $m_{\text{Pl}}$ | gravitational coupling scale |

A post-Newtonian binary has

$$
R\ll r\ll \frac{r}{v},
\qquad
v\ll 1.
$$

This hierarchy motivates successive EFTs: first replace each object by a worldline, then integrate out potential gravitons to get an orbital EFT, then compute radiation and radiation reaction.

## Spin on the worldline

Spinning objects require additional worldline degrees of freedom. One may describe spin using an antisymmetric tensor $S^{\mu\nu}$, body-fixed frames, or spin variables with constraints. The action contains terms such as

$$
S_{\text{spin}}
=\frac12\int d\tau\,S_{ab}\Omega^{ab}+\cdots,
$$

where $\Omega^{ab}$ is the angular velocity of a local frame carried by the object. Spin supplementary conditions are needed to choose the representative center of mass. Different choices are related by field redefinitions and should not change physical observables.

Spin allows more operators. In gravity, examples include spin-induced multipole couplings. Schematically,

$$
S_{\text{spin-induced}}
\supset
\int d\tau\,C_{ES^2}E_{\mu\nu}S^\mu S^\nu+\cdots.
$$

The coefficient $C_{ES^2}$ distinguishes different compact objects. For example, a Kerr black hole and a neutron star have different spin-induced multipole structures.

## Matching Wilson coefficients

Worldline coefficients are fixed by matching. The procedure is the usual EFT procedure:

1. Choose long-distance observables or fields.
2. Compute them in the microscopic or full theory.
3. Compute them in the worldline EFT with unknown coefficients.
4. Expand both answers at low frequency or long distance.
5. Equate the two expansions.

For example, an electromagnetic polarizability can be matched from low-frequency Compton scattering. A gravitational tidal coefficient can be matched from the response of the object's exterior metric to an applied tidal field. Absorption coefficients can be matched from the imaginary part of a response function or an absorption cross section.

Symbolically,

$$
\mathcal A_{\text{full}}(\omega R\ll 1)
=\mathcal A_{\text{worldline}}(C_i,\omega)+O((\omega R)^{N+1}).
$$

The coefficients $C_i$ are not universal numbers. They are physical data of the object.

## Renormalization on the worldline

Point-particle EFTs often have UV divergences localized on the worldline. This is not a disaster. It is exactly what EFT predicts. Local divergences are absorbed into local worldline counterterms:

$$
C_i^{\text{bare}}=C_i(\mu)+\delta C_i(\mu).
$$

The resulting RG equations describe how worldline coefficients run with scale. This running can appear in classical as well as quantum calculations. Classical divergences are common in point-particle descriptions because the EFT has collapsed an extended object into a line.

The important distinction is:

$$
\text{bulk counterterms live in spacetime},
\qquad
\text{worldline counterterms live on the trajectory}.
$$

Both are local in the appropriate sense.

## Radiation and dissipation

Worldline EFT can include radiation and dissipation. Radiation modes couple to multipole moments. For a binary source, the long-distance gravitational radiation is controlled by mass and current multipoles, with leading quadrupole radiation in general relativity.

Dissipation appears when the object has internal states or a horizon that can absorb energy. In EFT, dissipation is encoded through response functions or additional worldline degrees of freedom. The corresponding Wilson coefficients can be complex in frequency space, with imaginary parts related to absorption.

This is another place where the simple conservative action is not enough. A complete real-time EFT of dissipative worldlines uses the same broad logic as Schwinger–Keldysh EFT: doubled variables, causal response, noise, and fluctuation–dissipation relations when the object is in thermal equilibrium.

## Power counting

Worldline EFT has several power countings, depending on the problem.

For a generic finite-size expansion, operators with more derivatives are suppressed by powers of $R/L$:

$$
\mathcal O_n\sim \left(\frac{R}{L}\right)^n.
$$

For nonrelativistic gravitational binaries, the expansion also involves velocity:

$$
v^2\sim \frac{Gm}{r}.
$$

Potential modes and radiation modes scale differently. This is why compact-binary EFT has a multi-scale structure rather than a single derivative expansion.

For a long-wavelength scattering problem, the useful expansion may be

$$
\omega R\ll 1.
$$

For a strongly gravitating object, $R$ may be comparable to the Schwarzschild radius, so $Gm/R$ is not necessarily small. Worldline EFT does not require weak internal gravity. It requires the object to be small compared with the external variation scale.

## Common pitfalls

**Thinking point particles have no structure.** A worldline EFT point particle is not featureless. Its structure appears in infinitely many local operators ordered by power counting.

**Confusing the object's size with the UV cutoff of the whole theory.** The size $R$ is a matching scale for the localized object. The bulk EFT may have its own cutoff or heavy thresholds.

**Dropping finite-size operators because they look higher order.** Higher order does not mean irrelevant forever. Tidal, spin, and absorption effects can be leading for specific observables or precision goals.

**Treating spin supplementary conditions as physical choices.** They are choices of representative worldline and variables. Physical observables should be invariant under consistent changes of spin gauge or center-of-mass convention.

**Ignoring worldline renormalization.** Divergences localized on a trajectory are not signs of failure. They are absorbed into worldline Wilson coefficients.

**Assuming black holes and material bodies differ only by mass.** They can share the same leading point-particle action but differ in spin multipoles, absorption, tidal response, and dissipative coefficients.

## Relations to other pages

This page belongs to the Major Effective Field Theories chapter. It connects most directly to [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/), [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/), and [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/).

The conceptual bridge is this: ordinary EFT expands a bulk action in local spacetime operators, while worldline EFT expands a defect action in local operators supported on a trajectory. The same principles apply: symmetry, locality, matching, power counting, renormalization, and basis independence.

## Research status

The EFT treatment of localized objects and compact binaries is well established. It has become a major language for high-order post-Newtonian calculations, spin effects, tidal effects, radiation reaction, and gravitational-wave theory.

Active directions include high-order post-Minkowskian amplitudes, spinning worldlines, finite-size and tidal effects, black-hole absorption, horizon degrees of freedom, EFTs for extended defects, classical double-copy methods, and systematic matching between amplitude methods and worldline actions.

## Exercises

### Exercise 1: Multipole expansion as a worldline operator expansion

Let an extended scalar charge distribution $\rho(\mathbf y)$ couple to a slowly varying scalar field by

$$
S_{\text{int}}=\int dt\int d^3\mathbf y\,\rho(\mathbf y)\phi(t,\mathbf X(t)+\mathbf y).
$$

Expand this interaction through quadrupole order.

<details><summary><strong>Solution</strong></summary>

Taylor expand the field around the center-of-mass position $\mathbf X(t)$:

$$
\phi(t,\mathbf X+
\mathbf y)
=\phi(t,\mathbf X)
+y^i\partial_i\phi(t,\mathbf X)
+\frac12 y^iy^j\partial_i\partial_j\phi(t,\mathbf X)
+\cdots.
$$

Substituting into the action gives

$$
S_{\text{int}}
=\int dt\left[
q\phi
+d^i\partial_i\phi
+\frac12 Q^{ij}\partial_i\partial_j\phi
+\cdots
\right]_{\mathbf X(t)},
$$

where

$$
q=\int d^3\mathbf y\,\rho(\mathbf y),
\qquad
d^i=\int d^3\mathbf y\,\rho(\mathbf y)y^i,
\qquad
Q^{ij}=\int d^3\mathbf y\,\rho(\mathbf y)y^iy^j.
$$

These are worldline couplings to local operators evaluated on the trajectory.

</details>

### Exercise 2: Dimensional estimate for a tidal coefficient

In four spacetime dimensions, estimate the scaling of the coefficient $C_E$ multiplying

$$
\int d\tau\, C_E E_{\mu\nu}E^{\mu\nu}
$$

for a compact object of size $R$ and mass $m$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. Proper time has mass dimension

$$
[d\tau]=-1.
$$

The curvature has dimension two, so the electric Weyl tensor $E_{\mu\nu}$ has dimension two. Therefore

$$
[E_{\mu\nu}E^{\mu\nu}]=4.
$$

The coefficient must have dimension

$$
[C_E]+(-1)+4=0,
$$

so

$$
[C_E]=-3.
$$

A natural finite-size estimate is therefore

$$
C_E\sim mR^4
$$

or equivalently a length cubed times an appropriate gravitational normalization, depending on conventions. The precise coefficient is not fixed by dimensional analysis; it is matched from the object's tidal response.

</details>

### Exercise 3: Why worldline counterterms are local

Explain why a divergence that arises from fields evaluated arbitrarily close to a point-particle trajectory should be absorbed into an operator integrated over the worldline rather than into a nonlocal term.

<details><summary><strong>Solution</strong></summary>

A UV divergence comes from a region whose size is much smaller than the long-distance scales being probed. From the perspective of the EFT, the divergent contribution cannot resolve the extended environment along the entire trajectory. It is localized at a point on the worldline and can depend only on the fields and derivatives evaluated there, subject to symmetries.

Therefore the counterterm has the form

$$
\delta S_{\text{wl}}=\int d\tau\,\delta C_i\mathcal O_i(\tau),
$$

where $\mathcal O_i(\tau)$ is a local worldline operator. A nonlocal term would encode long-distance propagation or memory, not a UV subtraction.

</details>

## References

- Goldberger and Rothstein, for the EFT approach to compact binaries and nonrelativistic gravitational systems.
- Porto and Levi reviews, for spinning bodies, finite-size effects, radiation, and high-order compact-binary EFT.
- Donoghue and Burgess, for gravity as an EFT and the interpretation of nonrenormalizable interactions.
- Thorne and related multipole literature, for gravitational radiation and source multipoles.
- Classical electrodynamics and polarizability literature, for the worldline interpretation of finite-size electromagnetic response.

## Version history

- 2026-06-19: First polished draft. Added worldline action, scalar multipole toy model, electromagnetic polarizability, gravitational compact-object EFT, spin, matching, renormalization, radiation, pitfalls, exercises, and workflow figure.
