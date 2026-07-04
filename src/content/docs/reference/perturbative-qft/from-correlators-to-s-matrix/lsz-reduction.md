---
title: "LSZ Reduction"
description: "The reduction formula that extracts S-matrix amplitudes from connected time-ordered correlation functions by isolating one-particle poles, amputating external legs, and taking on-shell limits."
sidebar:
  label: "LSZ Reduction"
  order: 3
level: Graduate
status: "Polished draft"
source: "Lehmann–Symanzik–Zimmermann 1955; Srednicki 2007, §§5 and 10; Coleman 2019, chs. 13–14; Weinberg 1995, Vol. I, §10.3; Schwartz 2014, ch. 6"
topics:
  - LSZ reduction
  - S-matrix
  - one-particle poles
  - field-strength residue
  - amputation
  - scattering amplitudes
canonicalTopics:
  - lsz-reduction
  - reduction-formula
  - one-particle-pole-extraction
  - external-leg-amputation
researchStatus:
  established:
    - "The scalar LSZ reduction formula is textbook-standard for relativistic QFTs with stable asymptotic one-particle states and interpolating fields with nonzero pole residue."
  active:
    - "Massless gauge theories, confinement, unstable particles, finite-volume systems, curved backgrounds, and theories without ordinary particle states require refined external-state or observable definitions."
---

## Summary

The **LSZ reduction formula** is the precise bridge from time-ordered correlation functions to scattering amplitudes. Correlators are vacuum expectation values of local fields. Scattering amplitudes are matrix elements between asymptotic particle states. LSZ says that the two are related by the one-particle poles of the correlator.

For a scalar interpolating field whose exact two-point function has a stable one-particle pole,

$$
G_2(p)
\underset{p^2\to m^2}{\sim}
\frac{iZ}{p^2-m^2+i\epsilon}
+\text{regular},
$$

with

$$
\langle0|\phi(0)|\mathbf p\rangle=\sqrt Z,
$$

the all-incoming scalar reduction formula in qft.org conventions is

$$
 i\mathcal M_n
=
\left[
\prod_{a=1}^n
Z_a^{-1/2}
\lim_{p_a^2\to m_a^2}
\frac{p_a^2-m_a^2}{i}
\right]
\widetilde G^{\rm c}_{n,\mathrm{stripped}}(p_1,\ldots,p_n).
$$

Here $\widetilde G^{\rm c}_{n,\mathrm{stripped}}$ is the connected momentum-space Green function with the overall momentum-conservation delta function removed. The formula instructs us to isolate the external one-particle poles, remove them, multiply by one field-strength factor $Z_a^{-1/2}$ per external particle, and then take the external momenta on shell.

The formula is simple because much has been hidden in its hypotheses: stable particles, asymptotic states, a vacuum, a local interpolating field with nonzero overlap, and a pole separated enough from the rest of the spectrum to identify a particle.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/), and [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/). From Foundations, the most relevant pages are [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/), and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/).

The next page, [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/), isolates the amputation operation as a reusable diagrammatic method.

## Core idea

A local field is not a particle detector. But if a field has the right quantum numbers, it can create a one-particle state from the vacuum with nonzero amplitude. That fact shows up analytically as a pole in the two-point function. In higher correlators, the same pole appears once for each external particle.

LSZ is the rule for extracting the residue of those external poles.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A connected Green function with external pole factors is reduced by LSZ to an on-shell invariant amplitude](/figures/perturbative-qft/lsz-reduction-poles.svg)

<figcaption>

LSZ starts from a connected Green function. Near each external one-particle pole, the correlator factorizes into an external pole factor, a field-strength overlap $\sqrt Z$, and the scattering kernel. Multiplying by inverse pole factors and taking the on-shell limit gives $i\mathcal M$.

</figcaption>
</figure>

The mental picture is:

1. local fields interpolate between the vacuum and physical particles;
2. stable particles appear as isolated poles in exact propagators;
3. external propagator poles are not part of the scattering amplitude;
4. amputation removes those poles;
5. the on-shell limit turns the off-shell Green function into an S-matrix amplitude.

The slogan is:

$$
\text{poles of correlators know about asymptotic particles.}
$$

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with the qft.org mostly-minus metric, plane waves $e^{-ip\cdot x}$, and covariantly normalized one-particle states,

$$
\langle \mathbf p'|\mathbf p\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

For clarity, most formulas use one real scalar field. The exact two-point function is

$$
G_2(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle,
$$

with Fourier transform

$$
G_2(p)=\int d^4x\,e^{ip\cdot x}G_2(x).
$$

For an $n$-point connected correlator,

$$
G_n^{\rm c}(x_1,\ldots,x_n)
=\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle_{\rm connected},
$$

translation invariance gives

$$
\widetilde G_n^{\rm c}(p_1,\ldots,p_n)
=
(2\pi)^4\delta^{(4)}\!\left(\sum_{a=1}^n p_a\right)
\widetilde G^{\rm c}_{n,\mathrm{stripped}}(p_1,\ldots,p_n).
$$

The momenta in this formula are **all incoming**. For a physical process

$$
p_1+\cdots+p_r\longrightarrow q_1+\cdots+q_s,
$$

the all-incoming LSZ correlator uses

$$
(p_1,\ldots,p_r,-q_1,\ldots,-q_s).
$$

The outgoing physical particles have positive energy $q_b^0>0$; the minus signs are only the all-incoming analytic convention.

## What LSZ relates

The connected Green function is an off-shell object. Its external momenta are Fourier variables, and before LSZ they need not satisfy $p_a^2=m_a^2$.

The invariant amplitude $\mathcal M$ is an on-shell object. In qft.org conventions it appears in

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

LSZ tells us how to pass from one object to the other. In all-incoming notation the relation is controlled by the external-pole behavior

$$
\widetilde G^{\rm c}_{n,\mathrm{stripped}}(p_1,\ldots,p_n)
\underset{p_a^2\to m_a^2}{\sim}
\left[
\prod_{a=1}^n
\frac{i\sqrt{Z_a}}{p_a^2-m_a^2+i\epsilon}
\right]
i\mathcal M_n(p_1,\ldots,p_n).
$$

Solving this pole-factorization formula for $i\mathcal M_n$ gives the LSZ reduction formula quoted in the summary.

Two parts of this statement are worth separating:

| Operation | What it removes |
|---|---|
| Multiplication by $(p_a^2-m_a^2)/i$ | the scalar Feynman pole on external leg $a$ |
| Multiplication by $Z_a^{-1/2}$ | the overlap between the chosen field and the normalized one-particle state |
| On-shell limit $p_a^2\to m_a^2$ | the remaining off-shell continuation of the external variables |

The result is independent of arbitrary rescalings of the interpolating field. If $\phi\mapsto c\phi$, then $G_n\mapsto c^nG_n$ and $Z\mapsto c^2Z$, so the LSZ combination is unchanged.

## One-particle pole and field-strength residue

The pole residue is not a decorative constant. It measures how strongly the local field overlaps with the physical one-particle state:

$$
\langle0|\phi(0)|\mathbf p\rangle=\sqrt Z.
$$

Equivalently, the exact propagator behaves as

$$
G_2(p)
=
\frac{iZ}{p^2-m^2+i\epsilon}
+\text{terms regular at }p^2=m^2.
$$

In a free theory with the standard canonically normalized scalar field,

$$
Z=1.
$$

In an interacting theory, $Z$ depends on the normalization of the chosen field. A renormalization scheme may choose a renormalized field whose physical pole residue is one. That makes the LSZ factors invisible, but it does not make the pole-residue logic disappear.

For several fields with the same quantum numbers, the two-point function can be a matrix. Then LSZ requires diagonalizing the pole structure and using the appropriate residue matrix or interpolating operators for the physical particle species. This is the same idea with more indices and more bookkeeping.

## Momentum-space reduction formula

For $n$ scalar external particles, possibly of different species and masses, the compact all-incoming formula is

$$
 i\mathcal M_n(p_1,\ldots,p_n)
=
\left[
\prod_{a=1}^n
Z_a^{-1/2}
\lim_{p_a^2\to m_a^2}
\frac{p_a^2-m_a^2}{i}
\right]
\widetilde G^{\rm c}_{n,\mathrm{stripped}}(p_1,\ldots,p_n).
$$

The stripped correlator has no overall delta function. The full connected transition matrix element restores the physical momentum-conservation factor:

$$
\langle f|iT|i\rangle_{\rm connected}
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The order of operations matters. Compute or define the off-shell correlator first, isolate the pole factors, multiply by the inverse pole factors, and only then take the on-shell limit. Setting $p_a^2=m_a^2$ before the poles have been removed is a precision way to manufacture infinities.

## Coordinate-space form

In coordinate space, external amputation is implemented by the inverse wave operator. The scalar Feynman propagator satisfies

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

Thus applying $i(\Box_x+m^2)$ to an external point removes a scalar external propagator with the same normalization as multiplication by $(p^2-m^2)/i$ in momentum space.

A schematic coordinate-space version, written in all-incoming notation, is

$$
 i\mathcal M_n
\sim
\prod_{a=1}^n
\left[
Z_a^{-1/2}
\int d^4x_a\,e^{ip_a\cdot x_a}
 i(\Box_{x_a}+m_a^2)
\right]
G_n^{\rm c}(x_1,\ldots,x_n),
$$

with momentum signs fixed by the all-incoming convention. The momentum-space formula is usually the safest version for calculations.

## Sketch of the derivation

The derivation has two conceptual ingredients.

First, a stable one-particle state can be identified at asymptotic times. If $\phi$ has nonzero overlap with that particle, the creation and annihilation operators for in and out states can be represented, inside matrix elements, by large-time limits of smeared fields. The smearing functions are solutions of the free Klein–Gordon equation with the desired on-shell momentum.

Second, one converts the difference between the large future and large past surface terms into a spacetime integral. The free wave operator $\Box+m^2$ appears because the smearing functions solve the free equation while the interacting field does not. After integration by parts, the operator $\Box+m^2$ acts on the time-ordered Green function.

Repeating the reduction for each external particle turns matrix elements between in and out states into time-ordered vacuum correlators with one inverse wave operator per external point. Fourier transforming gives the momentum-space inverse pole factors.

This proof sketch deliberately hides technical issues such as wave packets, convergence of asymptotic limits, operator domains, and adiabatic switching. Those details matter in precise scattering theory. For perturbative calculations with stable massive particles, the pole-extraction statement is the part that does the daily work.

## Worked check: φ⁴ contact scattering

In real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

the tree-level connected four-point correlator has the stripped form

$$
\widetilde G^{\rm c}_{4,\mathrm{stripped}}
=
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right](-i\lambda),
$$

up to the all-incoming momentum-conservation delta function that has already been stripped. At this order $Z=1$. Applying LSZ gives

$$
 i\mathcal M_4
=
\left[\prod_{a=1}^4\lim_{p_a^2\to m^2}\frac{p_a^2-m^2}{i}\right]
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right]
(-i\lambda).
$$

Each external factor cancels, leaving

$$
{i\mathcal M_4=-i\lambda,}
\qquad
{\mathcal M_4=-\lambda.}
$$

This example is intentionally plain. It shows the essential point: external propagators belong to the correlator, not to the final scattering amplitude.

## Worked check: cubic exchange

In a scalar theory with

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3,
$$

the $s$-channel tree contribution to the connected four-point correlator contains

$$
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right]
(-ig)^2\frac{i}{(p_1+p_2)^2-m^2+i\epsilon}.
$$

LSZ removes the four external propagators but does **not** remove the internal exchange propagator. The corresponding amplitude contribution is

$$
 i\mathcal M_s
=
(-ig)^2\frac{i}{s-m^2+i\epsilon},
\qquad
s=(p_1+p_2)^2.
$$

The difference is physical. External propagators represent interpolation between local fields and asymptotic particles. Internal propagators represent propagation inside the scattering process and remain part of the amplitude.

## Beyond scalar fields

For spinor and vector particles, LSZ has the same logical structure but with external wavefunctions and polarization data.

For a Dirac field, the one-particle overlap has the form

$$
\langle0|\psi(0)|\mathbf p,s\rangle
=\sqrt{Z_\psi}\,u_s(p),
$$

and external fermion lines are reduced with the appropriate Dirac inverse operator and spinor wavefunctions. For photons or other gauge bosons, external physical polarization vectors and Ward identities are essential. One does not simply put arbitrary components of a gauge field on shell and call the result physical.

The scalar formula on this page is the clean template. Spin, gauge redundancy, ghosts, polarization sums, and infrared subtleties are additional layers, not different magic.

## Common pitfalls

**Putting external momenta on shell too early.** LSZ extracts residues of poles. If you set $p^2=m^2$ before multiplying by the inverse pole factor, you have destroyed the limiting operation that defines the amplitude.

**Leaving external propagators in the amplitude.** A Green function with external propagator tails is still a correlator. The S-matrix amplitude is amputated and on shell.

**Forgetting the field-strength residue.** In interacting theories, the field in the Lagrangian need not create a normalized one-particle state with unit amplitude. The $Z^{-1/2}$ factors are what make the answer independent of arbitrary field normalization.

**Amputating internal lines.** LSZ applies to external asymptotic particles only. Internal propagators are part of the scattering kernel and remain unless a separate factorization or cutting argument is being used.

**Treating every field as an interpolating field for a physical particle.** A field with the wrong quantum numbers, zero overlap, gauge redundancy, or color charge in a confining theory may fail to create a physical asymptotic particle. LSZ requires the relevant one-particle pole.

## Relations to other pages

- [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/) defines the in and out particle states that LSZ connects to correlators.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the normalization of $S$, $T$, and $\mathcal M$ used in the reduction formula.
- [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) separates the amputation operation from the on-shell LSZ limit.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) explains why stable particles appear as poles in exact two-point functions.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the diagrammatic rules whose output is usually interpreted as $i\mathcal M$ after LSZ.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) explains the irreducible kernels used to build connected amputated functions.

## Research status

LSZ reduction is a settled structural result in ordinary scattering theory for relativistic QFTs with stable asymptotic particles and suitable interpolating fields. The scalar formula on this page is the textbook case.

The difficult questions are about the hypotheses. Long-range gauge fields produce infrared degeneracies. Confining theories do not have colored asymptotic states. Unstable particles are resonances, not exact external states. Finite-volume, finite-temperature, curved-spacetime, and strongly coupled theories may require different observables or refined scattering constructions.

## Exercises

### Exercise 1: Amputate one scalar pole

Show that the LSZ inverse pole factor removes a scalar external propagator:

$$
\lim_{p^2\to m^2}
\frac{p^2-m^2}{i}
\frac{i}{p^2-m^2+i\epsilon}=1.
$$

<details>
<summary><strong>Solution</strong></summary>

The factors of $i$ cancel, leaving

$$
\lim_{p^2\to m^2}
\frac{p^2-m^2}{p^2-m^2+i\epsilon}.
$$

LSZ is a residue operation. After the pole has been isolated, the infinitesimal $i\epsilon$ specifies the distributional prescription and the residue is one:

$$
\lim_{p^2\to m^2}
\frac{p^2-m^2}{p^2-m^2+i\epsilon}=1.
$$

</details>

### Exercise 2: Check field-rescaling independence

Suppose $\phi'=c\phi$ for a nonzero constant $c$. Show that the LSZ amplitude is unchanged.

<details>
<summary><strong>Solution</strong></summary>

The $n$-point connected correlator scales as

$$
G_n^{\prime\,\rm c}=c^nG_n^{\rm c}.
$$

The one-particle matrix element becomes

$$
\langle0|\phi'(0)|p\rangle=c\sqrt Z,
$$

so the pole residue scales as

$$
Z'=c^2Z.
$$

The LSZ residue factors scale as

$$
\prod_{a=1}^n (Z')^{-1/2}=c^{-n}\prod_{a=1}^n Z^{-1/2},
$$

which cancels the factor $c^n$ from the correlator. The amplitude is unchanged.

</details>

### Exercise 3: Extract the φ⁴ tree amplitude

Use LSZ to extract the tree-level amplitude from

$$
\widetilde G^{\rm c}_{4,\mathrm{stripped}}
=
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right](-i\lambda).
$$

<details>
<summary><strong>Solution</strong></summary>

At tree level $Z=1$. Apply one factor $(p_a^2-m^2)/i$ to each external leg:

$$
 i\mathcal M_4
=
\left[\prod_{a=1}^4\frac{p_a^2-m^2}{i}\right]
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right](-i\lambda).
$$

The four external pole factors cancel, giving

$$
 i\mathcal M_4=-i\lambda,
\qquad
\mathcal M_4=-\lambda.
$$

</details>

### Exercise 4: Why the cubic exchange propagator remains

In $g\phi^3$ theory, the $s$-channel four-point correlator contains the factor

$$
\left[\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\right]
(-ig)^2\frac{i}{s-m^2+i\epsilon}.
$$

Explain why LSZ removes only the first four propagators.

<details>
<summary><strong>Solution</strong></summary>

The first four propagators are attached to the four external field insertions. Each one corresponds to the pole by which a local field creates or annihilates an asymptotic one-particle state. LSZ applies once for each external particle, so these poles are removed.

The factor

$$
\frac{i}{s-m^2+i\epsilon}
$$

is an internal exchange propagator. It is part of the scattering process itself and is not associated with an external asymptotic field insertion. Therefore it remains in $i\mathcal M_s$.

</details>

### Exercise 5: Translate outgoing momenta

A physical process has incoming momenta $p_1,p_2$ and outgoing momenta $q_1,q_2$. Which four momenta appear in the all-incoming LSZ correlator?

<details>
<summary><strong>Solution</strong></summary>

Outgoing physical momenta are represented by incoming momenta with the opposite sign. The all-incoming list is

$$
(p_1,p_2,-q_1,-q_2).
$$

The all-incoming conservation law is

$$
p_1+p_2-q_1-q_2=0,
$$

which is just the physical statement that total incoming momentum equals total outgoing momentum.

</details>

### Exercise 6: State one failure mode of the naive formula

Give one situation where the simple scalar LSZ formula must be modified or interpreted carefully.

<details>
<summary><strong>Solution</strong></summary>

One example is an unstable particle. An unstable particle is not a stable asymptotic state as $t\to\pm\infty$, so it should not be placed on an external LSZ leg. It appears instead through resonance poles and amplitudes for its stable decay products.

Other examples include charged particles in theories with massless gauge bosons, colored quarks and gluons in confining QCD, and finite-temperature systems where vacuum scattering is not the relevant observable.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §5, for a concise scalar LSZ derivation, and §§10–11 for amplitudes, cross sections, and decay rates.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 13–14, for Green functions, in/out states, and the LSZ formalism.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 6, for the S-matrix, time-ordered products, and LSZ reduction.

### Deeper references

- H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* **1** (1955), 205–225, for the original LSZ framework.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §10.3, for the reduction formula, field renormalization, propagator poles, and external-line factors.
- M. E. Peskin and D. V. Schroeder, *An Introduction to Quantum Field Theory*, §7.2, for a standard textbook derivation and discussion of field-strength renormalization.

## Version history

- **2026-06-12:** Initial standardized page.
