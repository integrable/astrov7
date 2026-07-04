---
title: "Decay Rates"
description: "A derivation and practical guide to differential and total decay rates from invariant amplitudes and Lorentz-invariant phase space."
sidebar:
  label: "Decay Rates"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11 and §25; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, chs. 11–12 and 17; Schwartz 2014, ch. 5"
topics:
  - decay rates
  - partial widths
  - branching ratios
  - two-body decays
  - phase space
canonicalTopics:
  - decay-rate
  - partial-width
  - total-width
  - branching-ratio
  - two-body-decay
researchStatus:
  established:
    - "The decay-rate formula follows from the standard S-matrix normalization, one-particle relativistic state normalization, and Lorentz-invariant final-state phase space."
  active:
    - "Precision decay predictions require radiative corrections, finite-width effects, infrared-safe definitions, hadronic matrix elements, and sometimes nonperturbative input beyond the tree-level rate formula."
---

## Summary

A decay rate is the transition probability per unit time for an unstable particle to turn into a specified set of final states. In qft.org conventions, for an initial particle $A$ of mass $M_A$ and four-momentum $P_A$, the differential rate for

$$
A(P_A)\to X
$$

is

$$
 d\Gamma_{A\to X}
 =
 \frac{1}{S_X}\frac{1}{2M_A}
 \overline{|\mathcal M_{A\to X}|^2}
 d\Pi_X(P_A).
$$

Here $d\Pi_X$ is Lorentz-invariant final-state phase space, $S_X$ is the final-state identical-particle counting factor, and the bar means that unresolved final quantum numbers are summed and unresolved initial spin states are averaged when one wants an unpolarized lifetime.

The total width is the sum of all partial widths,

$$
\Gamma_{\rm tot}=
\sum_X \Gamma_{A\to X},
\qquad
\tau=\frac{1}{\Gamma_{\rm tot}},
\qquad
\operatorname{Br}(A\to X)=\frac{\Gamma_{A\to X}}{\Gamma_{\rm tot}}.
$$

The formula is simple because a decay has no incident flux denominator. The initial state is one particle, so the normalization factor is $2M_A$ in its rest frame. All nontrivial kinematics lives in $d\Pi_X$.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Decay-rate workflow from amplitude and phase space to partial widths, total width, lifetime, and branching ratios](/figures/perturbative-qft/decay-rates-map.svg)

<figcaption>

A decay calculation starts with an invariant amplitude and final-state phase space. Integrating gives partial widths; summing partial widths gives the total width and lifetime; ratios of partial to total widths give branching ratios.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), and [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/).

## Core idea

A cross section measures probability per incident flux. A decay rate measures probability per unit time for one prepared particle. That is the whole conceptual difference.

For scattering,

$$
 d\sigma=\frac{1}{F_{12}}\overline{|\mathcal M|^2}d\Pi_f.
$$

For decay,

$$
 d\Gamma=\frac{1}{2M_A}\overline{|\mathcal M|^2}d\Pi_f
$$

for distinguishable final particles. The factor $1/(2M_A)$ is the one-particle replacement for the incoming-flux denominator. It comes from the relativistic normalization of the initial one-particle state.

The rate formula separates dynamics from kinematics:

| Ingredient | Meaning |
|---|---|
| $\mathcal M$ | short-distance or model-dependent dynamics of the decay |
| $d\Pi_X$ | Lorentz-invariant final-state kinematics |
| $S_X$ | final-state identical-particle overcounting factor |
| $1/(2M_A)$ | normalization of one decaying particle in its rest frame |

## Setup and conventions

We use the qft.org $S$-matrix convention

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
$$

with one-particle normalization

$$
\langle \mathbf p',s'|\mathbf p,s\rangle
=
(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'}.
$$

The final-state phase-space measure for $X=\{p_1,\ldots,p_n\}$ is

$$
 d\Pi_n(P_A;p_1,\ldots,p_n)
 =
 (2\pi)^4\delta^{(4)}\!\left(P_A-\sum_{a=1}^np_a\right)
 \prod_{a=1}^n\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

The initial particle is usually evaluated in its rest frame,

$$
P_A^\mu=(M_A,\mathbf 0),
$$

because the lifetime is the proper lifetime. In a lab frame where the particle has energy $E_A$, the decay is time-dilated:

$$
\Gamma_{\rm lab}=\frac{M_A}{E_A}\Gamma_{\rm rest},
\qquad
\tau_{\rm lab}=\frac{E_A}{M_A}\tau_{\rm rest}.
$$

The factor $S_X$ removes overcounting in the final-state phase-space integral. If the final state contains $n_a$ identical particles of species $a$, then

$$
S_X=\prod_a n_a!.
$$

Exchange-related diagrams still belong in the amplitude. The factor $1/S_X$ only corrects phase-space counting.

## General n-body decay rate

The master formula for a decay into $n$ final particles is

$$
\Gamma_{A\to 1\cdots n}
=
\frac{1}{S_X}\frac{1}{2M_A}
\int d\Pi_n(P_A;p_1,
\ldots,p_n)
\overline{|\mathcal M(A\to1\cdots n)|^2}.
$$

This expression is Lorentz invariant, but it computes the rest-frame decay width because of the factor $M_A$ in the initial one-particle normalization. It is often evaluated in the rest frame of $A$ because the delta function then has a direct interpretation as energy conservation.

The amplitude should be the stripped invariant amplitude. It does not include the overall momentum-conserving delta function. It also does not include the final-state phase-space measure.

For spin or polarization sums, use the rule appropriate to the observable:

| Situation | What to do |
|---|---|
| lifetime of an unpolarized spin-$J$ particle | average over the $2J+1$ initial spin states |
| decay of a specified spin state | do not average over that initial spin |
| unresolved final spins, colors, or polarizations | sum over them |
| measured angular or polarization correlations | keep the corresponding labels instead of summing them too early |

For a stable particle, $\Gamma_{\rm tot}=0$ in the exact theory. Perturbative pages sometimes compute a decay rate for a particle that is stable in a toy model after adding a small interaction. The calculation is still meaningful as a leading transition rate when the width is small compared with the mass and with the experimental energy resolution.

## Two-body decays

For

$$
A(P)\to a(p_a)+b(p_b),
\qquad
P^2=M_A^2,
$$

the two-body phase-space formula gives

$$
 d\Pi_2
=
\frac{|\mathbf p_*|}{16\pi^2M_A}d\Omega,
$$

where $d\Omega$ is the solid-angle element of either final momentum in the rest frame of $A$, and

$$
|\mathbf p_*|
=
\frac{\sqrt{\lambda(M_A^2,m_a^2,m_b^2)}}{2M_A}.
$$

Therefore

$$
\frac{d\Gamma}{d\Omega}
=
\frac{1}{S_{ab}}
\frac{|\mathbf p_*|}{32\pi^2M_A^2}
\overline{|\mathcal M(A\to ab)|^2}.
$$

If the squared amplitude is angle independent, then

$$
\Gamma(A\to ab)
=
\frac{1}{S_{ab}}
\frac{|\mathbf p_*|}{8\pi M_A^2}
\overline{|\mathcal M(A\to ab)|^2}.
$$

For two massless distinguishable final particles,

$$
|\mathbf p_*|=\frac{M_A}{2},
$$

so

$$
\Gamma(A\to ab)
=
\frac{1}{16\pi M_A}
\overline{|\mathcal M|^2}
\qquad
(m_a=m_b=0,\ S_{ab}=1).
$$

For identical massless final particles, divide this by $2!$.

## Example: scalar decay into two identical scalars

Consider a real scalar $\Phi$ of mass $M$ decaying into two identical real scalars $\phi$ of mass $m$ through

$$
\mathcal L_{\rm int}=-\frac{g}{2}\Phi\phi^2.
$$

The factor $1/2$ in the interaction is chosen so that the vertex factor is $-ig$. The stripped tree-level amplitude is, up to an irrelevant sign,

$$
\mathcal M(\Phi\to\phi\phi)=-g,
\qquad
|\mathcal M|^2=g^2.
$$

The final particles are identical, so $S_{\phi\phi}=2!$. The final momentum is

$$
|\mathbf p_*|
=
\frac{1}{2}\sqrt{M^2-4m^2}
=
\frac{M}{2}\sqrt{1-\frac{4m^2}{M^2}}.
$$

Thus

$$
\Gamma(\Phi\to\phi\phi)
=
\frac{g^2}{32\pi M}
\sqrt{1-\frac{4m^2}{M^2}}.
$$

This formula makes two important checks visible. First, $g$ has mass dimension one in four spacetime dimensions, so $g^2/M$ has the correct dimension of a decay rate. Second, the rate vanishes at threshold $M=2m$ because phase space closes.

## Angular distributions

The differential formula contains more information than the total width. If the decay has a preferred spin axis, or if one measures final-state polarizations, the angular dependence of $\mathcal M$ can be physical.

For a two-body decay with no azimuthal dependence around a chosen axis,

$$
d\Omega=d\phi\,d\cos\theta
\quad\Rightarrow\quad
\frac{d\Gamma}{d\cos\theta}
=
\frac{1}{S_{ab}}
\frac{|\mathbf p_*|}{16\pi M_A^2}
\overline{|\mathcal M(\theta)|^2}.
$$

If the initial particle is spinless and the final-state spins are unobserved, the decay of a single particle at rest is isotropic whenever the amplitude has no hidden angular dependence from spin correlations. For spinning particles, angular distributions can carry polarization information. That is why decay products are often used as spin analyzers.

## Partial widths and branching ratios

A partial width is the contribution to the total width from a specified class of final states:

$$
\Gamma_X\equiv\Gamma(A\to X).
$$

The total width is

$$
\Gamma_{\rm tot}=\sum_X\Gamma_X,
$$

where the sum includes every open physical decay channel. The branching ratio is

$$
\operatorname{Br}(A\to X)
=
\frac{\Gamma_X}{\Gamma_{\rm tot}}.
$$

Branching ratios are dimensionless probabilities for decay channels, while widths have dimensions of energy. In units with $\hbar=c=1$, the rest-frame lifetime is $\tau=1/\Gamma_{\rm tot}$. Restoring $\hbar$ gives

$$
\tau=\frac{\hbar}{\Gamma_{\rm tot}}.
$$

A small width means a long-lived particle. A large width means the resonance is broad and may not be well described as an isolated on-shell intermediate state.

## Recursive phase space for multi-body decays

For more than two final particles, it is often useful to factorize phase space through an intermediate invariant mass. Let

$$
q=p_1+\cdots+p_k.
$$

Then

$$
 d\Pi_n(P;p_1,\ldots,p_n)
 =
 \frac{dq^2}{2\pi}
 d\Pi_{n-k+1}(P;q,p_{k+1},\ldots,p_n)
 d\Pi_k(q;p_1,\ldots,p_k).
$$

This identity is just momentum conservation reorganized. It is the natural language for sequential decays and for Dalitz-plot variables in three-body decays.

For example, in a three-body decay $A\to1+2+3$, choosing $q=p_1+p_2$ gives

$$
 d\Pi_3(P;p_1,p_2,p_3)
 =
 \frac{dq^2}{2\pi}
 d\Pi_2(P;q,p_3)
 d\Pi_2(q;p_1,p_2).
$$

If the amplitude is nearly constant, the shape of the distribution is mostly phase space. If the amplitude contains an intermediate resonance, the $q^2$ distribution develops a peak. The [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) explains when that peak can be replaced by an on-shell production times a branching ratio.

## Widths and unstable propagators

A decay width also appears in the propagator of an unstable particle. Near an isolated scalar resonance, the resummed propagator is often written schematically as

$$
\frac{i}{q^2-M^2+iM\Gamma_{\rm tot}}.
$$

The positive width moves the pole away from the real axis and produces the Breit–Wigner line shape

$$
\frac{1}{(q^2-M^2)^2+M^2\Gamma_{\rm tot}^2}.
$$

This formula is a near-pole approximation, not a license to insert widths arbitrarily into every propagator. Gauge theories, overlapping resonances, thresholds, and precision calculations require systematic finite-width schemes. The decay-rate formula on this page is the input that gives the on-shell total width appearing in the leading resonance approximation.

## Checks and limits

**Mass dimension.** In four spacetime dimensions, $[\Gamma]=1$. Since $d\Pi_n$ has dimension $2n-4$ and $1/(2M_A)$ has dimension $-1$, the amplitude dimension adjusts so that the rate has dimension one. For a renormalizable two-body decay with a dimension-one coupling, the formula above passes this check immediately.

**Threshold behavior.** For a two-body decay with orbital angular momentum $\ell$, the phase-space factor contributes one power of $|\mathbf p_*|$, while the amplitude often contributes $|\mathbf p_*|^{2\ell}$ to $|\mathcal M|^2$. Near threshold,

$$
\Gamma_\ell\propto |\mathbf p_*|^{2\ell+1}.
$$

The power $+1$ is kinematic. The power $2\ell$ is dynamical.

**Lorentz dilation.** The width is a proper decay rate. A boosted unstable particle travels farther on average by the usual factor $E_A/M_A$. The invariant formula computes the rest-frame width; it does not contradict time dilation.

## Common pitfalls

**Using the lab energy instead of the rest mass in the master formula.** The compact factor $1/(2M_A)$ is the rest-frame one-particle normalization. If you describe decays in a lab frame, the observed rate is time-dilated by $M_A/E_A$.

**Forgetting final-state identical-particle factors.** The amplitude must include all exchange-related diagrams and signs. The additional factor $1/S_X$ only prevents the phase-space integral from counting the same final state multiple times.

**Averaging over initial spin when the initial state is polarized.** An unpolarized lifetime averages over degenerate initial spin states. A polarized angular distribution does not. Averaging too early destroys spin-correlation information.

**Including the momentum-conserving delta function inside $\mathcal M$.** The decay formula uses the stripped invariant amplitude. The overall $(2\pi)^4\delta^{(4)}(P_f-P_i)$ belongs to the $S$-matrix element.

**Confusing width with branching ratio.** A partial width has units of energy. A branching ratio is a dimensionless fraction of the total width. Multiplying a production rate by a branching ratio is a narrow-width approximation, not the definition of a decay rate.

**Treating every unstable particle as an external asymptotic state.** Strictly speaking, unstable particles are not exact asymptotic states of the full theory. Decay-rate calculations are controlled approximations when the width is small enough that the particle can be prepared and identified as a resonance.

## Relations to other pages

- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) defines the final-state measure used in all decay formulas.
- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) derives the closed-form two-body measure used for $A\to ab$.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains exchange amplitudes and final-state phase-space counting.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) contrasts decay rates with cross sections and their flux factors.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) uses partial widths to factor resonant production and decay.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) explains how total transition probabilities are constrained by unitarity.

## Research status

The decay-rate formula is textbook-standard for weakly coupled decays of identifiable unstable particles into stable asymptotic final states. Its normalization is fixed by the $S$-matrix convention and relativistic state normalization.

The main active issues arise in realistic applications. Precision decay predictions may require loop corrections, renormalization, infrared-safe inclusive sums, finite-width schemes, nonperturbative hadronic matrix elements, finite-temperature or finite-density effects, and experimental definitions of what final state is actually counted.

## Exercises

### Exercise 1: Derive the two-body decay formula

Starting from

$$
 d\Gamma
=
\frac{1}{2M_A}
\overline{|\mathcal M|^2}d\Pi_2
$$

and

$$
 d\Pi_2=\frac{|\mathbf p_*|}{16\pi^2M_A}d\Omega,
$$

derive

$$
\frac{d\Gamma}{d\Omega}
=
\frac{|\mathbf p_*|}{32\pi^2M_A^2}
\overline{|\mathcal M|^2}
$$

for distinguishable final particles.

<details>
<summary><strong>Solution</strong></summary>

Substitute the two-body phase-space measure into the master formula:

$$
 d\Gamma
=
\frac{1}{2M_A}
\overline{|\mathcal M|^2}
\frac{|\mathbf p_*|}{16\pi^2M_A}d\Omega.
$$

Multiplying the denominators gives

$$
2M_A\times16\pi^2M_A=32\pi^2M_A^2.
$$

Therefore

$$
\frac{d\Gamma}{d\Omega}
=
\frac{|\mathbf p_*|}{32\pi^2M_A^2}
\overline{|\mathcal M|^2}.
$$

For identical final particles, multiply the right-hand side by $1/2!$ if the full labeled angular domain is integrated.

</details>

### Exercise 2: Constant massless two-body decay

A particle of mass $M$ decays to two distinguishable massless particles with angle-independent squared amplitude $\overline{|\mathcal M|^2}=C$. Show that

$$
\Gamma=\frac{C}{16\pi M}.
$$

<details>
<summary><strong>Solution</strong></summary>

For two massless final particles,

$$
|\mathbf p_*|=\frac{M}{2}.
$$

The distinguishable two-body formula gives

$$
\Gamma
=
\frac{|\mathbf p_*|}{8\pi M^2}C
=
\frac{M/2}{8\pi M^2}C
=
\frac{C}{16\pi M}.
$$

</details>

### Exercise 3: Identical scalar decay

For

$$
\mathcal L_{\rm int}=-\frac{g}{2}\Phi\phi^2,
$$

with $M_\Phi=M$ and $m_\phi=m$, derive

$$
\Gamma(\Phi\to\phi\phi)
=
\frac{g^2}{32\pi M}
\sqrt{1-\frac{4m^2}{M^2}}.
$$

<details>
<summary><strong>Solution</strong></summary>

The tree-level amplitude has magnitude squared

$$
|\mathcal M|^2=g^2.
$$

The final scalars are identical, so $S=2!$. The final momentum is

$$
|\mathbf p_*|=\frac{M}{2}\sqrt{1-\frac{4m^2}{M^2}}.
$$

Using the angle-independent two-body formula with the identical-particle factor,

$$
\Gamma
=
\frac{1}{2}
\frac{|\mathbf p_*|}{8\pi M^2}g^2.
$$

Substituting $|\mathbf p_*|$ gives

$$
\Gamma
=
\frac{1}{2}\frac{1}{8\pi M^2}
\frac{M}{2}
\sqrt{1-\frac{4m^2}{M^2}}g^2
=
\frac{g^2}{32\pi M}
\sqrt{1-\frac{4m^2}{M^2}}.
$$

</details>

### Exercise 4: Branching ratios

An unstable particle has partial widths

$$
\Gamma_1=2\,\text{MeV},
\qquad
\Gamma_2=3\,\text{MeV},
\qquad
\Gamma_3=5\,\text{MeV}.
$$

Compute the total width and the three branching ratios.

<details>
<summary><strong>Solution</strong></summary>

The total width is

$$
\Gamma_{\rm tot}=2+3+5=10\,\text{MeV}.
$$

Therefore

$$
\operatorname{Br}_1=\frac{2}{10}=0.2,
\qquad
\operatorname{Br}_2=\frac{3}{10}=0.3,
\qquad
\operatorname{Br}_3=\frac{5}{10}=0.5.
$$

The branching ratios add to one because the listed channels exhaust the total width.

</details>

### Exercise 5: Threshold scaling

Suppose a two-body decay near threshold has orbital angular momentum $\ell=1$. If the amplitude scales as $\mathcal M\sim |\mathbf p_*|$, how does the rate scale with $|\mathbf p_*|$?

<details>
<summary><strong>Solution</strong></summary>

The two-body phase-space measure contributes one power of $|\mathbf p_*|$ to the rate. If

$$
\mathcal M\sim |\mathbf p_*|,
$$

then

$$
|\mathcal M|^2\sim |\mathbf p_*|^2.
$$

Thus

$$
\Gamma\sim |\mathbf p_*|\,|\mathbf p_*|^2=|\mathbf p_*|^3.
$$

This agrees with the general threshold scaling $\Gamma_\ell\sim |\mathbf p_*|^{2\ell+1}$ for $\ell=1$.

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, §§10–11, for amplitudes, phase space, cross sections, and decay rates.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 11–12, for scattering kinematics, phase space, and decay applications.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 5, for practical cross-section and decay-rate normalization.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for the general scattering-theory framework behind rates and phase space.
- Mark Srednicki, *Quantum Field Theory*, §25, for unstable particles and resonances.
- Sidney Coleman, *Lectures on Quantum Field Theory*, ch. 17, for unstable particles, Breit–Wigner physics, and decay-law considerations.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for standard decay and scattering examples.

## Version history

- **2026-06-12:** Initial polished draft for qft.org. Adds the general decay-rate formula, two-body specialization, scalar worked example, branching ratios, recursive phase space, and width interpretation in qft.org conventions.
