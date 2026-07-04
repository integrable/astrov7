---
title: "Helicity Amplitudes Preview"
description: "A practical preview of fixed-helicity tree amplitudes, their external wavefunctions, Ward-identity checks, spinor-helicity notation, and conversion to spin-summed observables."
sidebar:
  label: "Helicity Amplitudes Preview"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§46, 48, 50, and 59–60; Weinberg 1995, Vol. I, chs. 2, 5, 6, and 8; Schwartz 2014, chs. 13 and 27"
topics:
  - helicity amplitudes
  - spinor helicity
  - fixed-helicity scattering
  - Ward identities
  - massless particles
  - tree amplitudes
canonicalTopics:
  - helicity-amplitudes
  - fixed-helicity-amplitudes
  - spinor-helicity-preview
  - helicity-versus-chirality
  - ward-identity-checks
researchStatus:
  established:
    - "Fixed-helicity amplitudes, helicity polarization vectors, and their recombination into spin-summed observables are standard parts of perturbative QFT."
  active:
    - "Modern on-shell methods build a much larger formalism around helicity variables, complex momenta, recursion, color ordering, and double-copy structures; this page only previews the tree-level language."
---

## Summary

A helicity amplitude is a scattering amplitude computed for definite external helicities rather than with spins and polarizations already summed. If the external helicity labels are $\boldsymbol{\lambda}=(\lambda_1,\lambda_2,\ldots,\lambda_n)$, we write the stripped amplitude schematically as

$$
\mathcal M_{\lambda_1\ldots\lambda_n}(p_1,\ldots,p_n).
$$

This object is not a new observable. It is a more resolved component of the same $S$-matrix element. The observable cross section or decay rate is obtained by summing over unresolved final helicities and averaging over unresolved initial helicities:

$$
\overline{|\mathcal M|^2}
=
\frac{1}{N_{\rm init}}
\sum_{\rm unresolved\ helicities,\ colors,\ flavors}
|\mathcal M_{\lambda_1\ldots\lambda_n}|^2.
$$

Helicity amplitudes are especially efficient for massless particles. For a massless particle, helicity is invariant under proper orthochronous Lorentz transformations; for a massive particle, helicity is still a useful basis label, but it is not invariant under arbitrary boosts. This is why the massless spinor-helicity formalism is so powerful and why massive helicity amplitudes require a little more bookkeeping.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Fixed-helicity amplitudes are computed first and then recombined into spin-summed observables](/figures/perturbative-qft/helicity-amplitudes-preview.svg)

<figcaption>

A helicity calculation keeps the external spin and polarization labels visible. Fixed-helicity amplitudes are the building blocks; spin sums, color sums, initial-state averages, and phase-space integration are later steps.

</figcaption>
</figure>

## Prerequisites

You should know the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), the $S$-matrix normalization in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), the external-state rules in [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), and the spin and vector projectors in [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/). For examples, it helps to have read [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/).

## Core idea

The trace method hides spin information early. The helicity method keeps it until the end. Instead of immediately replacing external spinors and polarizations by completeness relations, one computes amplitudes between definite external one-particle states:

$$
\text{external helicity labels}
\quad\longrightarrow\quad
\mathcal M_{\lambda_1\ldots\lambda_n}
\quad\longrightarrow\quad
\overline{|\mathcal M|^2}.
$$

This is useful for three reasons. First, experiments sometimes measure polarization information. Second, even when they do not, helicity amplitudes often make zeros, angular dependence, and gauge cancellations obvious. Third, modern amplitude methods use helicity variables as their native language.

## Setup and conventions

We use the qft.org mostly-minus metric, plane waves $e^{-ip\cdot x}$, and relativistic one-particle normalization. The $S$-matrix convention is

$$
S_{fi}=\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

External momenta are on shell. For a massive particle,

$$
p^2=m^2,
\qquad p^0=E_{\mathbf p}>0,
$$

while for a massless particle,

$$
k^2=0,
\qquad k^0=|\mathbf k|.
$$

The helicity operator for a one-particle state of momentum $\mathbf p\neq0$ is

$$
h=\frac{\mathbf J\cdot\mathbf p}{|\mathbf p|}.
$$

Its eigenvalues are the spin projection along the direction of motion. For a massless spin-one particle, the physical helicities are $\lambda=\pm1$; for a massless spin-one-half particle, they are $\lambda=\pm1/2$.

:::caution[Phase convention]
A helicity amplitude has convention-dependent phases. Relative signs and phases can change when one changes spinor bases, polarization phases, or all-incoming versus in–out conventions. Squared amplitudes, interference terms within a fixed convention, and gauge-invariant observables are the invariant content.
:::

## Helicity as a state label

For massive particles, helicity is a good basis for a chosen frame. A spin-one-half helicity spinor can be built from two-component eigenspinors satisfying

$$
(\sigma\cdot\hat{\mathbf p})\xi_{\lambda}(\mathbf p)
=2\lambda\xi_{\lambda}(\mathbf p),
\qquad
\lambda=\pm\frac12.
$$

This labels the spin projection along $\mathbf p$. A boost that changes the direction of $\mathbf p$ can mix the massive spin labels through a Wigner rotation, so massive helicity is not as rigid as massless helicity.

For massless particles, there is no rest frame. The little group acts differently, and helicity becomes the intrinsic spin label measured along the momentum. This is the physical reason that massless amplitudes are naturally organized by helicity.

The relation between helicity and chirality is simple only in the massless limit. For a massless Dirac particle, the particle spinor $u_\lambda(p)$ has chirality equal to helicity, while the antiparticle spinor has the opposite relation in the usual Dirac-field convention. Once $m\neq0$, chirality and helicity are different concepts: chirality is the eigenvalue of $\gamma^5$, while helicity is a spin projection.

## External wavefunctions

A fixed-helicity fermion amplitude uses external spinors rather than spin sums. For an outgoing fermion and incoming fermion, one meets objects such as

$$
\overline u_{\lambda'}(p')\gamma^\mu u_\lambda(p),
$$

with

$$
(p\!\!\!/-m)u_\lambda(p)=0,
\qquad
\overline u_\lambda(p)(p\!\!\!/-m)=0.
$$

Spin sums enter only when the external spin is not observed:

$$
\sum_\lambda u_\lambda(p)\overline u_\lambda(p)=p\!\!\!/+m.
$$

For a massless vector with momentum $k$, a fixed-helicity amplitude uses a physical polarization vector $\epsilon^\mu_\pm(k;q)$. The extra reference vector $q$ records a gauge choice. The two physical polarizations satisfy

$$
k_\mu\epsilon^\mu_\pm(k;q)=0,
\qquad
\epsilon_\pm(k;q)^*\cdot\epsilon_\pm(k;q)=-1,
\qquad
\epsilon_\pm(k;q)^*\cdot\epsilon_\mp(k;q)=0.
$$

A change of reference vector shifts the polarization by a term proportional to $k^\mu$. In a gauge-invariant amplitude, the Ward identity makes this shift invisible:

$$
\mathcal M(\epsilon^\mu)
=\mathcal M(\epsilon^\mu+\alpha k^\mu)
\quad\text{if}\quad
k_\mu\mathcal A^\mu=0.
$$

This is the most important practical check on any external-photon or external-gluon helicity amplitude.

## From fixed helicities to observables

A fixed-helicity amplitude is a component. An unpolarized cross section is a sum over components. For a $2\to2$ process in the center-of-mass frame, with the usual normalization,

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f|}{|\mathbf p_i|}
\overline{|\mathcal M|^2},
$$

where

$$
\overline{|\mathcal M|^2}
=\frac{1}{N_{\rm init}}
\sum_{\lambda_1,\lambda_2,\lambda_3,\lambda_4}
|\mathcal M_{\lambda_1\lambda_2\lambda_3\lambda_4}|^2
$$

if no external helicities are measured.

Do not average over final helicities. Final states are alternatives, so they are summed. Initial helicities describe how many equally populated incoming states contributed to the prepared beam, so unresolved initial labels are averaged.

## Example: massless QED angular pattern

Consider massless tree-level

$$
e^-e^+\to\mu^-\mu^+.
$$

The amplitude is

$$
\mathcal M
=
\frac{e^2}{s}
\big[
\overline v(p_2)\gamma^\mu u(p_1)
\big]
\big[
\overline u(p_3)\gamma_\mu v(p_4)
\big],
$$

up to convention-dependent overall phases. Because the vector coupling preserves chirality in the massless limit, many helicity assignments vanish. For a fixed incoming helicity choice, the two nonzero final-helicity patterns have squared amplitudes proportional to

$$
|\mathcal M_{LR\to LR}|^2=e^4(1+\cos\theta)^2,
\qquad
|\mathcal M_{LR\to RL}|^2=e^4(1-\cos\theta)^2,
$$

with corresponding amplitudes for the opposite incoming helicities. Here $L$ and $R$ denote helicity for the charged leptons in the massless limit, and $\theta$ is the center-of-mass scattering angle of the outgoing $\mu^-$ relative to the incoming $e^-$.

Summing over final helicities and averaging over the two nonzero incoming helicity pairs gives

$$
\overline{|\mathcal M|^2}=e^4(1+\cos^2\theta).
$$

Therefore

$$
\frac{d\sigma}{d\Omega}
=\frac{\alpha^2}{4s}(1+\cos^2\theta),
\qquad
\alpha=\frac{e^2}{4\pi},
$$

which is the familiar unpolarized result. The helicity calculation explains where the angular dependence came from: it is the coherent spin information before the final helicities are summed.

## Spinor-helicity notation preview

For massless momenta, spinor-helicity notation packages on-shell kinematics into two-component spinors. The basic factorization is

$$
p_{\alpha\dot\alpha}
=p_\mu\sigma^\mu_{\alpha\dot\alpha}
=|p\rangle_\alpha[p|_{\dot\alpha},
\qquad
p^2=0.
$$

The invariant spinor brackets are

$$
\langle ij\rangle
=\epsilon^{\alpha\beta}|i\rangle_\alpha |j\rangle_\beta,
\qquad
[ij]
=\epsilon^{\dot\alpha\dot\beta}[i|_{\dot\alpha}[j|_{\dot\beta},
$$

and, with standard phase conventions,

$$
2p_i\cdot p_j=\langle ij\rangle[ji].
$$

The little-group scaling

$$
|i\rangle\to t_i|i\rangle,
\qquad
|i]\to t_i^{-1}|i]
$$

tracks helicity weights. A physical $n$-point amplitude with external helicities $h_i$ scales as

$$
\mathcal M_n\longrightarrow
\prod_{i=1}^n t_i^{-2h_i}\mathcal M_n.
$$

This one line is a preview of why spinor-helicity methods are so constraining. Lorentz invariance, little-group weights, locality, and factorization often determine much of the amplitude before any diagram is drawn.

## Checks

**Ward identity check.** For an external photon or gluon, replace $\epsilon^\mu(k)$ by $k^\mu$. A gauge-invariant tree amplitude with physical external states should vanish after all diagrams are included.

**Trace-method check.** Sum the fixed-helicity answers and compare with the result obtained from spin sums and traces. Agreement checks spinor phases, normalization, and averaging factors.

**Soft and collinear limits.** In massless amplitudes, helicity expressions often reveal factorization when a momentum becomes soft or two momenta become collinear. These limits are a powerful diagnostic, although their systematic use belongs to later infrared and on-shell-amplitude pages.

## Common pitfalls

**Confusing helicity with chirality.** They coincide for massless particles in a convention-dependent particle–antiparticle sense, but they are not the same operator. Massive fermions can have definite helicity without definite chirality.

**Comparing helicity amplitudes by phase.** The sign or phase of a fixed-helicity amplitude can change under harmless basis choices. Compare gauge-invariant squared quantities, relative phases within one convention, or factorization properties.

**Using $-\eta_{\mu\nu}$ blindly for external photons.** That replacement is safe only after gauge invariance ensures that unphysical terms decouple. For fixed helicities, use physical polarization vectors and check the Ward identity.

**Averaging over final helicities.** Final helicities are summed, not averaged. Averages apply to unresolved labels in the initial ensemble.

**Treating helicity zeros as universal.** Some amplitudes vanish only in the massless limit or only for special interactions. Mass terms, Yukawa couplings, symmetry breaking, and loop corrections can change selection rules.

## Relations to other pages

- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains how fixed-helicity amplitudes recombine into spin-summed squared amplitudes.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) provides the vector-current examples used here.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) uses the same Ward-identity logic with color and gluon self-interactions.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) supplies the $s,t,u$ kinematics behind the angular formulas.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains how external spinors and polarizations enter the $S$-matrix normalization.

## Research status

The material on this page is textbook-standard tree-level QFT. The active frontier is not whether helicity amplitudes exist, but how far on-shell principles can replace diagrammatic computation, especially in gauge theory, gravity, effective field theory, and loop-level amplitudes.

## Exercises

### Exercise 1: Check a photon helicity basis

For a photon moving in the positive $z$ direction,

$$
k^\mu=(E,0,0,E),
$$

consider

$$
\epsilon_\pm^\mu(k)=\frac{1}{\sqrt2}(0,1,\pm i,0).
$$

Show that $k\cdot\epsilon_\pm=0$ and $\epsilon_\pm^*\cdot\epsilon_\pm=-1$ in mostly-minus signature.

<details>
<summary><strong>Solution</strong></summary>

Using $\eta=\operatorname{diag}(+,-,-,-)$,

$$
k\cdot\epsilon_\pm
=E\epsilon_\pm^0-E\epsilon_\pm^3=0.
$$

For the norm,

$$
\epsilon_\pm^*\cdot\epsilon_\pm
=|\epsilon^0|^2-|\epsilon^1|^2-|\epsilon^2|^2-|\epsilon^3|^2
=0-\frac12-\frac12-0=-1.
$$

The overall phase of $\epsilon_\pm$ is conventional.

</details>

### Exercise 2: Recover the unpolarized QED angular factor

Assume the nonzero massless helicity amplitudes for $e^-e^+\to\mu^-\mu^+$ have squared magnitudes

$$
|\mathcal M_{LR\to LR}|^2=e^4(1+\cos\theta)^2,
\qquad
|\mathcal M_{LR\to RL}|^2=e^4(1-\cos\theta)^2,
$$

with the same pattern for the opposite incoming helicities. Average over the four initial spin states and sum over final helicities.

<details>
<summary><strong>Solution</strong></summary>

Only two of the four initial helicity pairs contribute. For one nonzero incoming pair, the final-helicity sum gives

$$
e^4(1+\cos\theta)^2+e^4(1-\cos\theta)^2
=2e^4(1+\cos^2\theta).
$$

There are two contributing initial pairs, so the full spin sum is

$$
4e^4(1+\cos^2\theta).
$$

The unpolarized average divides by $4$, giving

$$
\overline{|\mathcal M|^2}=e^4(1+\cos^2\theta).
$$

</details>

### Exercise 3: Ward identity for an external photon

Suppose a tree amplitude with one external photon can be written as

$$
\mathcal M=\epsilon_\mu(k)\mathcal A^\mu,
$$

and current conservation implies $k_\mu\mathcal A^\mu=0$. Show that the amplitude is invariant under $\epsilon^\mu\to\epsilon^\mu+\alpha k^\mu$.

<details>
<summary><strong>Solution</strong></summary>

The shifted amplitude is

$$
\mathcal M'
=(\epsilon_\mu+\alpha k_\mu)\mathcal A^\mu
=\mathcal M+\alpha k_\mu\mathcal A^\mu.
$$

The second term vanishes by the Ward identity, so $\mathcal M'=\mathcal M$.

</details>

### Exercise 4: Little-group weight

Let a massless amplitude contain one external positive-helicity photon. Under little-group scaling, the corresponding polarization vector has weight $t^{-2}$. What scaling should the amplitude have in that external leg?

<details>
<summary><strong>Solution</strong></summary>

For a particle of helicity $h$, a massless amplitude scales as

$$
\mathcal M_n\to t^{-2h}\mathcal M_n
$$

in that leg. For a positive-helicity photon, $h=+1$, so the amplitude scales as

$$
\mathcal M_n\to t^{-2}\mathcal M_n.
$$

This is the spinor-helicity bookkeeping version of saying that the external wavefunction carries helicity information.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the sections on spin sums, spin-averaged cross sections, massless particles, spinor helicity, and QED scattering.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 13 and 27, for QED helicity examples and a modern spinor-helicity introduction.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2, 5, 6, and 8, for one-particle helicity states, massless particles, and perturbative amplitudes.

### Deeper references

- L. J. Dixon, “Calculating scattering amplitudes efficiently,” for a classic review of helicity and color methods.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a systematic on-shell-amplitude treatment.
- M. L. Mangano and S. J. Parke, “Multiparton amplitudes in gauge theories,” for the classic amplitude-review perspective.

## Version history

- **2026-06-12:** Initial standardized page.
