---
title: "Flux Factors"
description: "A derivation and practical guide to the invariant two-particle flux factor that converts squared amplitudes and phase space into scattering cross sections."
sidebar:
  label: "Flux Factors"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, chs. 11–12; Schwartz 2014, ch. 5"
topics:
  - flux factors
  - cross sections
  - scattering
  - Møller velocity
  - Lorentz-invariant phase space
canonicalTopics:
  - scattering-flux-factor
  - moller-velocity
  - cross-section-normalization
  - two-to-n-scattering
  - decay-rate-normalization
researchStatus:
  established:
    - "The invariant two-particle flux factor follows from relativistic state normalization and is standard in perturbative cross-section formulas."
  active:
    - "Experimental event rates use luminosities, parton distributions, beam spectra, finite wave packets, cuts, and detector effects; those refinements extend the invariant partonic flux formula rather than replacing it."
---

## Summary

A scattering cross section is not just a squared amplitude times final-state phase space. It also needs an initial-state flux factor. In qft.org conventions, for a two-particle initial state $p_1+p_2\to X$,

$$
 d\sigma_{12\to X}
 =
 \frac{1}{F_{12}}\,
 \overline{|\mathcal M_{12\to X}|^2}\,
 d\Pi_X,
$$

where

$$
F_{12}
=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}
=4E_1E_2v_{\rm M}.
$$

The quantity

$$
 v_{\rm M}
 =
 \frac{\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}{E_1E_2}
$$

is often called the Møller velocity. It is the velocity factor that appears in beam flux. It is not always the ordinary special-relativistic speed of one particle measured in the rest frame of the other.

In the center-of-momentum frame,

$$
F_{12}
=4|\mathbf p_i^*|\sqrt{s}
=2\sqrt{\lambda(s,m_1^2,m_2^2)},
$$

with $s=(p_1+p_2)^2$ and $\lambda$ the Källén function. For massless $2\to X$ scattering, this becomes $F_{12}=2s$.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 52rem;">

![The invariant flux factor normalizes the encounter rate of two incoming relativistic particles](/figures/perturbative-qft/flux-factors-map.svg)

<figcaption>

The flux factor is the initial-state normalization that converts a transition probability into a cross section. It is separate from the final-state phase-space measure. A one-particle decay has no incident two-particle flux; its corresponding prefactor is $1/(2M)$ in the decaying particle's rest frame.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), the amplitude normalization in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), the external-state normalization in [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), the final-state measure in [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), and the kinematic invariants in [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/).

## Core idea

A cross section is an event rate divided by an incident flux. The amplitude describes the quantum transition. The final-state phase space sums over possible final momenta. The flux factor normalizes by how often the two incoming particles encounter each other.

For relativistically normalized plane waves, the usual finite-volume and finite-time factors cancel into an invariant expression. The result is the compact master formula

$$
 d\sigma
 =
 \frac{1}{4E_1E_2v_{\rm M}}
 \overline{|\mathcal M|^2}
 d\Pi_X.
$$

The same formula is often written as

$$
 d\sigma
 =
 \frac{1}{4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}
 \overline{|\mathcal M|^2}
 d\Pi_X.
$$

The second form is usually safer because its Lorentz invariance is explicit.

## Setup and conventions

We use the qft.org $S$-matrix convention

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The incoming particles have momenta

$$
p_1^2=m_1^2,
\qquad
p_2^2=m_2^2,
\qquad
P=p_1+p_2,
\qquad
s=P^2.
$$

The final-state phase space is

$$
 d\Pi_X
 =
 (2\pi)^4\delta^{(4)}\!\left(p_1+p_2-\sum_{a\in X}p_a\right)
 \prod_{a\in X}
 \frac{d^3\mathbf p_a}{(2\pi)^3 2E_a},
$$

with final-state identical-particle factors included separately when needed. The bar in $\overline{|\mathcal M|^2}$ means that unresolved final quantum numbers are summed and unresolved initial quantum numbers are averaged according to the observable being computed.

## The invariant flux

The invariant scalar built from two on-shell initial momenta is

$$
(p_1\cdot p_2)^2-m_1^2m_2^2.
$$

It is nonnegative for physical two-particle scattering. The flux factor is

$$
F_{12}
=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}.
$$

To connect this with the more intuitive velocity language, write

$$
p_i^\mu=E_i(1,\mathbf v_i),
\qquad
|\mathbf v_i|=\frac{|\mathbf p_i|}{E_i}.
$$

Then

$$
p_1\cdot p_2=E_1E_2(1-\mathbf v_1\cdot\mathbf v_2),
$$

and

$$
\frac{\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}}{E_1E_2}
=
\sqrt{(\mathbf v_1-\mathbf v_2)^2-(\mathbf v_1\times\mathbf v_2)^2}.
$$

This is the Møller velocity,

$$
 v_{\rm M}
 =
 \sqrt{(\mathbf v_1-\mathbf v_2)^2-(\mathbf v_1\times\mathbf v_2)^2}.
$$

Thus

$$
F_{12}=4E_1E_2v_{\rm M}.
$$

For collinear beams, the cross product term vanishes and $v_{\rm M}=|\mathbf v_1-\mathbf v_2|$. For two head-on massless particles, $v_{\rm M}=2$. That is not a violation of relativity; $v_{\rm M}$ is a flux factor, not the velocity of one light ray in the rest frame of another.

## Center-of-momentum form

In the center-of-momentum frame,

$$
p_1^\mu=(E_1^*,\mathbf p_i^*),
\qquad
p_2^\mu=(E_2^*,-\mathbf p_i^*),
\qquad
E_1^*+E_2^*=\sqrt{s}.
$$

The incoming momentum magnitude is

$$
|\mathbf p_i^*|
=
\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}},
$$

where

$$
\lambda(x,y,z)=x^2+y^2+z^2-2xy-2xz-2yz.
$$

Since

$$
\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}
=|\mathbf p_i^*|\sqrt{s},
$$

the flux factor becomes

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s}=2\sqrt{\lambda(s,m_1^2,m_2^2)}.
$$

Special cases are worth remembering:

| Initial state | Flux factor |
|---|---:|
| equal masses $m_1=m_2=m$ | $F_{12}=2\sqrt{s(s-4m^2)}$ |
| massless particles | $F_{12}=2s$ |
| fixed target with particle 2 at rest | $F_{12}=4m_2|\mathbf p_1|_{\rm lab}$ |

The fixed-target formula follows from $p_2=(m_2,\mathbf 0)$, so

$$
\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}=m_2|\mathbf p_1|_{\rm lab}.
$$

## Cross sections

The invariant differential cross section for $1+2\to X$ is

$$
 d\sigma_{12\to X}
 =
 \frac{1}{F_{12}}
 \overline{|\mathcal M_{12\to X}|^2}
 d\Pi_X.
$$

This formula assumes the standard relativistic normalization of states and the $S$-matrix convention stated above. If a source uses a different convention for states or amplitudes, the location of $2E$ and $2\pi$ factors may change, but the physical cross section does not.

The factor $\overline{|\mathcal M|^2}$ should be interpreted carefully:

$$
\overline{|\mathcal M|^2}
=
\frac{1}{N_{\rm initial}}
\sum_{\rm unresolved\ final}
\sum_{\rm unresolved\ initial}
|\mathcal M|^2,
$$

where $N_{\rm initial}$ is the number of initial spin, polarization, color, or flavor states being averaged over. Do not include this averaging again in the flux factor.

## Decays are different

A decay has one initial particle, not two colliding beams. There is no two-particle incident flux. For a particle of mass $M$ decaying in its rest frame,

$$
 d\Gamma_{A\to X}
 =
 \frac{1}{2M}
 \overline{|\mathcal M_{A\to X}|^2}
 d\Pi_X.
$$

The factor $1/(2M)$ is the one-particle initial-state normalization in the rest frame. More covariantly, if the initial particle has energy $E_A$ in some frame, the transition probability per coordinate time carries $1/(2E_A)$; the rest-frame decay rate is recovered by multiplying by the time-dilation factor $E_A/M$.

The key distinction is:

| Process | Initial normalization |
|---|---|
| scattering | two incoming particles; divide by incident flux |
| decay | one incoming particle; divide by $2M$ in the rest frame |

## Two-to-two master formula

Combining the invariant flux with two-body phase space gives the standard $2\to2$ formula. In the center-of-momentum frame,

$$
 d\Pi_2
 =
 \frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega,
$$

and

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s}.
$$

Therefore

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

For massless $2\to2$ scattering with $|\mathbf p_f^*|=|\mathbf p_i^*|$,

$$
\frac{d\sigma}{d\Omega}
=
\frac{\overline{|\mathcal M|^2}}{64\pi^2s}.
$$

If the final state contains two identical particles and the angular integral covers the labeled full sphere, include the final-state factor $1/2!$ or restrict the angular domain to avoid double counting.

## Luminosity language

Experiments often write event counts as

$$
N=\mathcal L_{\rm int}\,\sigma,
$$

where $\mathcal L_{\rm int}$ is the integrated luminosity. This is the experimental version of dividing an event rate by an incident flux. The invariant partonic formula above computes $\sigma$ for idealized initial particles. In collider applications, this partonic cross section is then folded with beam spectra, parton distribution functions, cuts, efficiencies, and detector response.

At hadron colliders, for example, a schematic factorized prediction has the form

$$
 d\sigma_{AB\to X}
 =
 \sum_{i,j}\int dx_1dx_2\,
 f_{i/A}(x_1,\mu)f_{j/B}(x_2,\mu)
 d\hat\sigma_{ij\to X}(x_1P_A,x_2P_B;\mu),
$$

where $d\hat\sigma$ uses the same invariant flux formula at the parton level. The parton distributions and factorization scale introduce additional physics beyond the elementary two-particle flux.

## Identical initial particles

There is usually no $1/2!$ factor for identical incoming particles in a cross section. The incoming beams, wave packets, or prepared states define the incident flux. For example, two identical scalar particles in opposing beams still produce a cross section normalized by the flux of encounters between the two beams.

A symmetry factor can appear when computing a total reaction rate in a gas or plasma, because the number of unordered pairs in a single population is $N(N-1)/2$ rather than $N^2$. That is a statistical pair-counting issue, not a modification of the elementary $2\to X$ cross-section formula.

## Common pitfalls

**Calling $v_{\rm M}$ an ordinary relative speed.** The Møller velocity is the velocity factor in the invariant flux. For head-on massless beams it equals $2$, so it cannot be the speed of one particle measured by another.

**Using $4E_1E_2$ as the flux.** The correct denominator is $4E_1E_2v_{\rm M}$, or equivalently $4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}$.

**Mixing the flux factor with final-state phase space.** Flux is initial-state normalization. Phase space is final-state summation.

**Averaging initial spins twice.** Initial spin, polarization, and color averages belong in $\overline{|\mathcal M|^2}$, not in $F_{12}$.

**Using the scattering formula for a decay.** Decays have one initial particle and use $1/(2M)$ in the rest frame, not a two-particle flux.

**Forgetting that collider luminosity is not the same as partonic flux.** The invariant flux normalizes an idealized partonic or particle-level process. Experimental luminosity counts beam encounters and must be combined with PDFs, cuts, and detector effects when appropriate.

## Relations to other pages

- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) gives the final-state measure that appears beside the flux denominator.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains the state-normalization factors behind the $2E$ dependence.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the amplitude convention used in the cross-section formula.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) develops $s$, $t$, $u$, and the Källén function used in center-of-momentum formulas.
- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains how to build $\overline{|\mathcal M|^2}$ from fixed-spin amplitudes.

## Research status

- **Established:** The invariant flux factor is standard relativistic scattering theory with covariantly normalized states.
- **Convention-dependent:** The denominator is tied to the state normalization and amplitude convention. The physical cross section is invariant under consistent convention changes.
- **Active:** Realistic event-rate predictions involve luminosity modeling, beam spectra, PDFs, factorization, finite-width effects, resummation, detector cuts, and Monte Carlo integration.
- **Speculative:** None at the level of the elementary flux formula.

## Exercises

### Exercise 1: Center-of-momentum flux

Show that in the center-of-momentum frame

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s}.
$$

<details>
<summary><strong>Solution</strong></summary>

In the center-of-momentum frame,

$$
p_1=(E_1^*,\mathbf p_i^*),
\qquad
p_2=(E_2^*,-\mathbf p_i^*),
\qquad
E_1^*+E_2^*=\sqrt{s}.
$$

The Møller velocity for collinear incoming particles is

$$
v_{\rm M}=|\mathbf v_1-\mathbf v_2|
=|\mathbf p_i^*|\left(\frac{1}{E_1^*}+\frac{1}{E_2^*}\right)
=\frac{|\mathbf p_i^*|\sqrt{s}}{E_1^*E_2^*}.
$$

Thus

$$
F_{12}=4E_1^*E_2^*v_{\rm M}
=4|\mathbf p_i^*|\sqrt{s}.
$$

</details>

### Exercise 2: Flux in terms of the Källén function

Use

$$
|\mathbf p_i^*|=\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}}
$$

to show that

$$
F_{12}=2\sqrt{\lambda(s,m_1^2,m_2^2)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the center-of-momentum momentum into the previous result:

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s}
=4\left(\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}}\right)\sqrt{s}
=2\sqrt{\lambda(s,m_1^2,m_2^2)}.
$$

</details>

### Exercise 3: Fixed-target flux

Let particle $2$ be at rest in the lab frame, $p_2=(m_2,\mathbf 0)$. Show that

$$
F_{12}=4m_2|\mathbf p_1|_{\rm lab}.
$$

<details>
<summary><strong>Solution</strong></summary>

Since $p_2=(m_2,\mathbf 0)$,

$$
p_1\cdot p_2=m_2E_1.
$$

Therefore

$$
\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}
=
\sqrt{m_2^2E_1^2-m_1^2m_2^2}
=m_2\sqrt{E_1^2-m_1^2}
=m_2|\mathbf p_1|_{\rm lab}.
$$

Multiplying by $4$ gives

$$
F_{12}=4m_2|\mathbf p_1|_{\rm lab}.
$$

</details>

### Exercise 4: Derive the two-to-two formula

Use

$$
 d\sigma=\frac{1}{F_{12}}\overline{|\mathcal M|^2}d\Pi_2,
$$

with

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s},
\qquad
 d\Pi_2=\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega,
$$

to derive

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the two ingredients:

$$
 d\sigma
 =
 \frac{1}{4|\mathbf p_i^*|\sqrt{s}}
 \overline{|\mathcal M|^2}
 \frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega.
$$

Thus

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

</details>

### Exercise 5: Head-on photons

For two head-on photons with energies $E_1$ and $E_2$, show that $v_{\rm M}=2$ and $F_{12}=8E_1E_2=2s$.

<details>
<summary><strong>Solution</strong></summary>

Take

$$
p_1=(E_1,0,0,E_1),
\qquad
p_2=(E_2,0,0,-E_2).
$$

Then

$$
p_1\cdot p_2=E_1E_2-\mathbf p_1\cdot\mathbf p_2
=E_1E_2+E_1E_2=2E_1E_2.
$$

Since both masses vanish,

$$
v_{\rm M}
=
\frac{|p_1\cdot p_2|}{E_1E_2}=2.
$$

Therefore

$$
F_{12}=4E_1E_2v_{\rm M}=8E_1E_2.
$$

Also

$$
s=(p_1+p_2)^2=2p_1\cdot p_2=4E_1E_2,
$$

so

$$
F_{12}=2s.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§10–11, for the connection between amplitudes, phase space, decay rates, and cross sections.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering-theory normalizations, rates, and cross sections.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 11–12, for phase space, differential cross sections, decay rates, and the optical theorem.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 5, for a practical introduction to cross sections and decay rates.

## Version history

- **2026-06-12:** Initial polished draft for qft.org. Fixes the invariant two-particle flux factor, Møller velocity, center-of-momentum and fixed-target forms, decay normalization, and the $2\to2$ cross-section formula in qft.org conventions.
