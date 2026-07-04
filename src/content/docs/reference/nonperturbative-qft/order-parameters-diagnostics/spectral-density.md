---
title: "Spectral Density"
description: "Explains how two-point functions encode the nonperturbative spectrum through Källén–Lehmann representations, Euclidean spectral sums, poles, thresholds, and continua."
sidebar:
  label: "Spectral Density"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki; Schwartz; Weinberg; Zinn-Justin; Altland–Simons."
topics:
  - spectral density
  - Källén–Lehmann representation
  - two-point functions
  - mass gap
  - bound states
  - resonances
  - Euclidean correlators
canonicalTopics:
  - nonperturbative-qft
  - spectral-density
  - correlation-functions
  - mass-gap
  - nonperturbative-spectrum
researchStatus:
  established:
    - "Spectral representations of two-point functions are standard consequences of Hilbert-space positivity, translation invariance, and completeness in unitary QFT."
  active:
    - "Reconstructing real-time spectral densities from Euclidean or lattice data is an ill-conditioned inverse problem and remains a major practical challenge, especially at finite temperature and density."
---

## Summary

A **spectral density** tells a two-point function which physical states it can create. For a Hermitian scalar operator $\mathcal O$ in a unitary relativistic QFT, the Euclidean two-point function has the schematic Källén–Lehmann form

$$
G_E(p_E^2)
=\int_0^\infty ds\,\frac{\rho_{\mathcal O}(s)}{p_E^2+s}
+\text{contact terms},
$$

where $s$ is an invariant mass-squared variable and

$$
\rho_{\mathcal O}(s)\ge 0
$$

under standard positivity assumptions. Delta functions in $\rho_{\mathcal O}$ are stable particles or isolated bound states. Continuous support describes multiparticle states, thresholds, and continua.

At zero spatial momentum, the same idea appears as the Euclidean spectral sum

$$
C_{\mathcal O}(\tau)
=\langle\mathcal O(\tau)\mathcal O^\dagger(0)\rangle_c
=\sum_{n>0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

This is one of the cleanest bridges between Euclidean path integrals and Hilbert-space physics: long Euclidean time filters out high-energy states, while the full spectral density remembers the whole nonperturbative spectrum in the chosen channel.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A spectral density with an isolated pole, a gap, and continuum support above a threshold, together with the corresponding Euclidean correlator decay.](/figures/nonperturbative-qft/spectral-density-reconstruction.svg)

<figcaption>

The spectral density records what a chosen operator can create from the vacuum. An isolated delta function gives a stable particle pole; the continuum begins at a multiparticle threshold. In Euclidean time, the lowest support visible to the operator dominates the large-$\tau$ decay.

</figcaption>
</figure>

## Prerequisites

You should know [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/), [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), and [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/).

It helps to know canonical Hilbert-space time evolution, Fourier transforms, connected correlators, and the idea that composite operators need renormalization.

## Core idea

A two-point function asks a simple physical question:

$$
\text{If }\mathcal O\text{ disturbs the vacuum, what states can propagate?}
$$

Insert a complete set of energy eigenstates between two operators. The correlator becomes a weighted sum over the spectrum. The weights are matrix elements,

$$
|\langle0|\mathcal O|n\rangle|^2,
$$

so the answer depends on the operator. A scalar glueball operator, a meson operator, a conserved current, and a disorder operator can all probe different channels of the same theory.

This is why spectral density is such a powerful nonperturbative diagnostic. It does not ask whether perturbation theory converges. It asks what the exact Hilbert space contains in a given channel:

| Feature of $\rho$ | Physical interpretation |
|---|---|
| Lowest support at $s=m_*^2>0$ | Gap in the channel probed by $\mathcal O$. |
| Delta function $Z\delta(s-m^2)$ | Stable one-particle state or isolated bound state. |
| Continuum beginning at $s=s_{\text{th}}$ | Multiparticle threshold or continuum of states. |
| Power-law threshold behavior | Phase space and matrix-element information. |
| No positive spectral representation | The operator or gauge-fixed correlator is not a physical positive-norm channel. |

The spectral density is therefore not just a calculational trick. It is the dictionary between correlators and particles, bound states, continua, and gaps.

## Setup and conventions

We use mostly-minus Lorentzian conventions and Euclidean conventions as fixed in [Conventions and Notation](/nonperturbative-qft/conventions/). Let $\mathcal O$ be a scalar Hermitian operator with vanishing vacuum expectation value, or replace it by $\mathcal O-\langle\mathcal O\rangle$.

The Lorentzian Wightman function is

$$
W(x)=\langle0|\mathcal O(x)\mathcal O(0)|0\rangle.
$$

Translation invariance gives

$$
\mathcal O(x)=e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x}.
$$

Inserting a complete set of states gives

$$
W(x)=\sum_n |\langle0|\mathcal O(0)|n\rangle|^2 e^{-ip_n\cdot x},
$$

with the sum replaced by integrals in infinite volume. Lorentz invariance packages this information into a spectral density $\rho_{\mathcal O}(s)$ with $s=p^2$.

The time-ordered Lorentzian two-point function has the form

$$
G_F(p^2)
=i\int_0^\infty ds\,\frac{\rho_{\mathcal O}(s)}{p^2-s+i\epsilon}
+\text{contact terms},
$$

while the Euclidean momentum-space correlator has

$$
G_E(p_E^2)
=\int_0^\infty ds\,\frac{\rho_{\mathcal O}(s)}{p_E^2+s}
+\text{contact terms}.
$$

The contact terms are polynomials in momentum, coming from coincident-point singularities and operator renormalization. They affect ultra-local pieces of the correlator, not the separated-distance spectral content.

## The finite-volume spectral sum

The cleanest derivation is in finite spatial volume, where the spectrum is discrete. Let $H|n\rangle=E_n|n\rangle$ and choose the vacuum $|0\rangle$. For Euclidean time $\tau>0$,

$$
C_{\mathcal O}(\tau)
=\langle0|\mathcal O(\tau)\mathcal O^\dagger(0)|0\rangle_c.
$$

Euclidean time evolution gives

$$
\mathcal O(\tau)=e^{H\tau}\mathcal O(0)e^{-H\tau}.
$$

Inserting $\mathbf 1=\sum_n|n\rangle\langle n|$ gives

$$
C_{\mathcal O}(\tau)
=\sum_{n>0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau},
$$

where the disconnected vacuum term has been subtracted. This formula is exact in finite volume.

The large-$\tau$ behavior is dominated by the lowest state with nonzero overlap:

$$
C_{\mathcal O}(\tau)
\sim |\langle0|\mathcal O|n_*\rangle|^2e^{-\Delta_{\mathcal O}\tau},
\qquad
\Delta_{\mathcal O}=E_{n_*}-E_0.
$$

This is the same physics as [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), but the emphasis here is the full distribution of weights rather than only the lowest exponent.

## From finite volume to spectral density

In infinite volume, energy levels form continua. The discrete sum becomes an integral. At zero spatial momentum one often writes

$$
C_{\mathcal O}(\tau)
=\int_0^\infty d\omega\,\rho_{\mathcal O}(\omega,\mathbf 0)e^{-\omega\tau},
$$

where $\omega$ is the energy above the vacuum in the chosen momentum channel. In a relativistic invariant presentation, one instead uses $s=\mu^2$:

$$
G_E(p_E^2)
=\int_0^\infty ds\,\frac{\rho_{\mathcal O}(s)}{p_E^2+s}.
$$

These are two faces of the same idea. The spectral density is the continuum version of the matrix-element-weighted sum over states.

The support of $\rho$ gives immediate phase information. If

$$
\rho_{\mathcal O}(s)=0\qquad 0\le s<m_*^2,
$$

then the channel probed by $\mathcal O$ is gapped. If support reaches $s=0$, the channel is gapless. If a delta function sits below a continuum threshold,

$$
\rho_{\mathcal O}(s)=Z\delta(s-m^2)+\theta(s-s_{\text{th}})\rho_{\text{cont}}(s),
$$

then $\mathcal O$ creates a stable isolated state of mass $m$, plus continuum states above threshold.

## Stable particles, bound states, and continua

A stable one-particle state appears as a delta function in the spectral density. For an interpolating operator $\mathcal O$,

$$
\rho_{\mathcal O}(s)\supset Z_{\mathcal O}\delta(s-m^2),
$$

where

$$
Z_{\mathcal O}=|\langle0|\mathcal O|p\rangle|^2
$$

up to normalization conventions. The mass $m$ is physical; the residue depends on the normalization of $\mathcal O$.

A bound state below a multiparticle threshold also appears as an isolated delta function. This is common in nonperturbative QFT: mesons, glueballs, kinks in finite-volume sectors, and other composite objects can be represented by poles or isolated spectral levels even when no weakly coupled elementary field creates them cleanly.

A multiparticle continuum begins at a threshold. For two identical scalar particles of mass $m$ at zero total momentum, the threshold is

$$
\sqrt{s}_{\text{th}}=2m,
\qquad
s_{\text{th}}=4m^2.
$$

Near threshold, $\rho$ reflects both phase space and the matrix element of $\mathcal O$ into the multiparticle states. This threshold behavior controls the power-law prefactor multiplying the leading Euclidean exponential.

A resonance is subtler. It is not a normalizable stable state and therefore is not a real-axis delta function in the exact infinite-volume spectral density. It usually appears as enhanced continuum weight and, more invariantly, as a pole on an unphysical sheet of analytically continued amplitudes. That is a real physical statement, but it is not the same as a stable particle pole.

## Positivity

For a Hermitian physical operator in a positive-norm Hilbert space,

$$
\rho_{\mathcal O}(s)\ge0.
$$

This follows because spectral weights are squares of matrix elements. Positivity is not merely aesthetic. It underlies reflection positivity, spectral reconstruction constraints, and the interpretation of Euclidean correlators as sums of decaying exponentials with positive weights.

But positivity is not guaranteed for every object one writes down in a gauge-fixed Lagrangian. Gauge-fixed gluon and ghost propagators, for example, need not have positive spectral densities. That does not by itself mean the theory is inconsistent; it means those fields are not physical positive-norm asymptotic operators. Physical gauge-invariant operators should be used for Hilbert-space spectral statements.

This warning is especially important in nonperturbative gauge theory. A correlator can be useful for a gauge-fixed calculation while failing to be a physical spectral density in the Källén–Lehmann sense.

## Operator dependence and invisible states

The spectral density is not “the spectrum” by itself. It is the spectrum **seen by an operator**.

If $\mathcal O$ has quantum numbers $J^{PC}$, flavor representation $R$, global charge $q$, and momentum $\mathbf p$, then $\rho_{\mathcal O}$ only receives contributions from states with the same quantum numbers. If the lightest state of the theory has different quantum numbers, it is absent.

Even within the right symmetry channel, a state can be hard to see if

$$
\langle0|\mathcal O|n\rangle\approx0.
$$

This is why lattice spectroscopy uses operator bases rather than a single operator. One builds a matrix

$$
C_{ij}(\tau)
=\langle\mathcal O_i(\tau)\mathcal O_j^\dagger(0)\rangle_c
$$

and extracts several spectral levels by a variational method. The goal is to improve overlap with the states in the channel.

The philosophical point is useful beyond lattice theory: no diagnostic is universal. Every operator asks a particular question of the Hilbert space.

## Euclidean data and the inverse problem

The Euclidean correlator is a Laplace transform of spectral data:

$$
C(\tau)=\int_0^\infty d\omega\,\rho(\omega)e^{-\omega\tau}.
$$

This map smooths information. Sharp features in $\rho$ can become subtle changes in $C(\tau)$. Recovering $\rho$ from noisy Euclidean data is therefore ill-conditioned.

At zero temperature, extracting the lowest mass from large-$\tau$ decay is often feasible. Reconstructing the full spectral function is much harder. At finite temperature, the Euclidean correlator is only known on a compact interval $0<\tau<\beta$, and the kernel becomes

$$
C(\tau)=\int_0^\infty d\omega\,\rho(\omega)
\frac{\cosh\left[\omega\left(\tau-\frac{\beta}{2}\right)\right]}{\sinh\left(\frac{\beta\omega}{2}\right)},
$$

for many bosonic channels. The inverse problem is then even more delicate.

This is one reason finite-temperature transport and real-time dynamics are hard. A Euclidean path integral may define the theory nonperturbatively, but real-time spectral information is not automatically easy to extract from it.

## Contact terms and subtractions

Composite operators have short-distance singularities. In momentum space these can appear as polynomial terms:

$$
G_E(p_E^2)
=\int_0^\infty ds\,\frac{\rho(s)}{p_E^2+s}
+P(p_E^2),
$$

where $P$ is a polynomial or local subtraction term. In position space, these are derivatives of delta functions supported at coincident points.

For separated points, contact terms do not affect the long-distance exponential decay. They do matter for sum rules, OPE matching, stress-tensor correlators, conserved currents, and numerical fits involving short distances.

The spectral density itself can also depend on the normalization and renormalization of $\mathcal O$. Multiplying the operator by $Z_{\mathcal O}$ rescales $\rho$ by $Z_{\mathcal O}^2$. Physical pole positions, thresholds, and symmetry selection rules are more invariant than residues of arbitrary composite operators.

## Spectral density as a diagnostic

A spectral-density analysis should answer these questions:

| Question | What to check |
|---|---|
| Which operator? | Its spin, global charges, gauge invariance, and renormalization. |
| Which channel? | Momentum, angular momentum, charge sector, finite-volume irrep, or lattice symmetry channel. |
| What is the lowest support? | Gapless, gapped, or isolated pole. |
| Is there a continuum? | Threshold location and asymptotic behavior. |
| Is positivity expected? | Physical Hermitian operator versus gauge-fixed or indefinite-metric field. |
| What data are available? | Euclidean correlator, finite-volume spectrum, real-time response, or exact solution. |
| What is convention-dependent? | Operator normalization, contact terms, and scheme-dependent composite-operator factors. |

This is the spectral version of the general diagnostic rule: state the observable, state the limit, and state what conclusion follows.

## Common pitfalls

**Treating a Euclidean correlator as the spectral density.** The correlator is an integral transform of $\rho$, not $\rho$ itself.

**Forgetting operator overlap.** A state absent from one spectral density may still exist; the chosen operator might not couple to it.

**Calling every bump a particle.** Stable particles give isolated delta functions. Resonances are encoded in continuum structure and analytic continuation, not normalizable real-axis delta functions.

**Using gauge-fixed fields as physical spectral probes.** A gauge-fixed propagator can be useful but need not admit a positive physical spectral density.

**Ignoring contact terms.** Short-distance singularities and local subtractions affect momentum-space correlators and sum rules.

**Overfitting Euclidean data.** Analytic continuation is ill-conditioned. Extracting a lowest mass is easier than reconstructing a detailed real-time spectral function.

**Confusing channel gap with full mass gap.** $\rho_{\mathcal O}$ only sees the lightest state with the same quantum numbers and nonzero overlap with $\mathcal O$.

## Relations to other pages

- [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) explains how the lowest spectral support determines exponential decay.
- [Correlation Length](/nonperturbative-qft/order-parameters-diagnostics/correlation-length/) connects spatial decay to inverse mass scales.
- [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/) explains one-point functions and composite-operator renormalization.
- [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) explains the Euclidean positivity condition behind Hilbert-space reconstruction.
- Later pages on **Hadron Spectrum**, **Glueballs**, **Spectral Functions**, and **Real-Time Nonperturbative QFT** will use this page as the basic dictionary.

## Research status

- **Established:** Källén–Lehmann-type spectral representations and finite-volume spectral sums are standard consequences of unitarity, translation invariance, completeness, and positivity.
- **Established:** The lowest spectral support in a channel controls large-distance or large-Euclidean-time decay when the operator has nonzero overlap.
- **Subtle:** Composite-operator normalization, mixing, and contact terms affect the precise form of momentum-space correlators and spectral weights.
- **Subtle:** Gauge-fixed propagators need not admit positive physical spectral densities.
- **Active:** Reconstructing real-time spectral functions from Euclidean lattice data, especially at finite temperature and density, is a major nonperturbative inverse problem.

## Exercises

### Exercise 1: Finite-volume spectral decomposition

Let $H|n\rangle=E_n|n\rangle$ and define

$$
C(\tau)=\langle0|\mathcal O(\tau)\mathcal O^\dagger(0)|0\rangle_c.
$$

Derive

$$
C(\tau)=\sum_{n>0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

<details>
<summary><strong>Solution</strong></summary>

Euclidean time evolution gives

$$
\mathcal O(\tau)=e^{H\tau}\mathcal O(0)e^{-H\tau}.
$$

Insert a complete set of energy eigenstates:

$$
\langle0|\mathcal O(\tau)\mathcal O^\dagger(0)|0\rangle
=\sum_n\langle0|e^{H\tau}\mathcal Oe^{-H\tau}|n\rangle
\langle n|\mathcal O^\dagger|0\rangle.
$$

Using $H|0\rangle=E_0|0\rangle$ and $H|n\rangle=E_n|n\rangle$ gives

$$
\sum_n e^{-(E_n-E_0)\tau}\langle0|\mathcal O|n\rangle
\langle n|\mathcal O^\dagger|0\rangle.
$$

The $n=0$ term is the disconnected contribution. Subtracting it leaves

$$
C(\tau)=\sum_{n>0}|\langle0|\mathcal O|n\rangle|^2e^{-(E_n-E_0)\tau}.
$$

</details>

### Exercise 2: Lowest support controls large Euclidean time

Suppose

$$
C(\tau)=A e^{-m\tau}+B e^{-M\tau},
\qquad
0<m<M,
$$

with $A\neq0$. Show that

$$
-\lim_{\tau\to\infty}\frac{1}{\tau}\log C(\tau)=m.
$$

<details>
<summary><strong>Solution</strong></summary>

Factor out the lightest exponential:

$$
C(\tau)=A e^{-m\tau}\left(1+\frac{B}{A}e^{-(M-m)\tau}\right).
$$

Then

$$
\log C(\tau)=\log A-m\tau+
\log\left(1+\frac{B}{A}e^{-(M-m)\tau}\right).
$$

The last term tends to zero as $\tau\to\infty$, while $\log A/\tau\to0$. Therefore

$$
-\lim_{\tau\to\infty}\frac{1}{\tau}\log C(\tau)=m.
$$

</details>

### Exercise 3: Free scalar spectral density

For a canonically normalized free scalar field of mass $m$, the Feynman propagator is

$$
G_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

What spectral density $\rho(s)$ reproduces this in the Källén–Lehmann form?

<details>
<summary><strong>Solution</strong></summary>

The Källén–Lehmann form is

$$
G_F(p)=i\int_0^\infty ds\,\frac{\rho(s)}{p^2-s+i\epsilon}.
$$

Choosing

$$
\rho(s)=\delta(s-m^2)
$$

gives

$$
G_F(p)=i\int_0^\infty ds\,\frac{\delta(s-m^2)}{p^2-s+i\epsilon}
=\frac{i}{p^2-m^2+i\epsilon}.
$$

Thus a free stable scalar has a single delta-function spectral density.

</details>

### Exercise 4: Why positivity can fail for gauge-fixed fields

The spectral weights in a physical channel are squares of matrix elements in a positive Hilbert space. Explain why this argument does not directly apply to ghost fields or gauge-fixed elementary gauge fields.

<details>
<summary><strong>Solution</strong></summary>

The positivity argument assumes that the operator acts within a physical Hilbert space with positive norm and that the inserted complete set consists of physical states. Gauge-fixed formulations often introduce unphysical degrees of freedom, constraints, ghosts, or an indefinite metric before projecting to the physical Hilbert space. Therefore the intermediate objects in a gauge-fixed propagator need not have positive spectral weights. Positivity should be expected for gauge-invariant physical operators, not for every gauge-fixed field appearing in the Lagrangian.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, especially the Lehmann–Källén form of the exact propagator and related discussions of exact two-point functions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on path integrals, unitarity, spectral decomposition, and implications of unitarity.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Hilbert-space foundations, spectral representations, and analytic structure.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean correlation functions, renormalization, and statistical-field-theory spectral interpretation.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for response functions, analytic structure, and many-body spectral functions.

## Version history

- **2026-06-26:** Initial polished draft.
