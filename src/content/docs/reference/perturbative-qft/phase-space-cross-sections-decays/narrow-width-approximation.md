---
title: "Narrow-Width Approximation"
description: "A derivation and practical guide to the narrow-width approximation, Breit–Wigner line shapes, resonant phase-space factorization, and production-times-branching-ratio formulas."
sidebar:
  label: "Narrow-Width Approximation"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §25; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, ch. 17; Schwartz 2014, chs. 5 and 24"
topics:
  - narrow-width approximation
  - Breit-Wigner resonance
  - unstable particles
  - phase-space factorization
  - branching fractions
canonicalTopics:
  - narrow-width-approximation
  - breit-wigner-line-shape
  - resonant-factorization
  - unstable-particle-width
  - production-times-branching-ratio
researchStatus:
  established:
    - "The narrow-width approximation is a standard leading approximation for isolated resonances with Γ/M much smaller than one and slowly varying nonresonant factors."
  active:
    - "Precision treatments of unstable particles require gauge-invariant pole schemes, off-shell effects, interference with nonresonant backgrounds, spin correlations, and higher-order corrections."
---

## Summary

The narrow-width approximation is the statement that an isolated unstable resonance with mass $M$ and total width $\Gamma$ behaves like an on-shell intermediate particle when

$$
\frac{\Gamma}{M}\ll1
$$

and the rest of the integrand varies slowly across the resonance peak.

The basic mathematical identity is

$$
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}
\;\to\;
\frac{\pi}{M\Gamma}\delta(q^2-M^2)
$$

inside an integral over $q^2$. This converts a Breit–Wigner peak into an on-shell delta function.

For a process that produces an intermediate resonance $R$ and then lets it decay,

$$
I\to B+R^*\to B+X,
$$

the narrow-width approximation gives the schematic but extremely useful result

$$
 d\sigma(I\to B+X)
 \simeq
 d\sigma(I\to B+R)\,\operatorname{Br}(R\to X),
$$

or, for a decay cascade,

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\,\operatorname{Br}(R\to X).
$$

These formulas are not magic replacements for a propagator at fixed $q^2$. They are integrated statements about a narrow peak in an invariant-mass distribution.

<figure class="doc-figure" style="--figure-width: 47rem; --caption-width: 54rem;">

![Breit-Wigner resonance becoming a delta function in the narrow-width limit, leading to production times branching fraction](/figures/perturbative-qft/narrow-width-approximation.svg)

<figcaption>

A resonant propagator produces a Breit–Wigner peak in the invariant mass $q^2$. When $\Gamma/M\ll1$ and all nonresonant factors are smooth across the peak, the peak may be replaced by $\pi\delta(q^2-M^2)/(M\Gamma)$ inside the $q^2$ integral. The process then factorizes into on-shell production of $R$ times the branching fraction for $R\to X$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), and [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/).

## Core idea

An unstable particle is not an exact asymptotic state. It is a resonance: a pole of an amplitude away from the real axis. Near the pole, the amplitude is dominated by a propagator-like factor

$$
\frac{i}{q^2-M^2+iM\Gamma}.
$$

Squaring this factor gives

$$
\left|\frac{i}{q^2-M^2+iM\Gamma}\right|^2
=
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}.
$$

If $\Gamma$ is small, the integrand is sharply concentrated near $q^2=M^2$. The resonance then acts like a delta function that forces the intermediate momentum on shell.

Physically, the resonance lives long enough to be approximately produced and decay as two separated stages:

$$
\text{produce }R
\quad\longrightarrow\quad
\text{let }R\text{ decay}.
$$

Mathematically, the $q^2$ integral over the squared propagator supplies $1/\Gamma$, and the decay matrix element supplies the partial width $\Gamma(R\to X)$. Their ratio is the branching fraction.

## Setup and conventions

We use the qft.org mostly-minus metric and scalar propagator convention

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

For an unstable scalar resonance, self-energy corrections move the pole away from the real axis. Near the resonance, the propagator has the approximate form

$$
\Delta_R(q)
\simeq
\frac{iZ}{q^2-M^2+iM\Gamma}.
$$

Here $M$ is the resonance mass, $\Gamma$ is the total width, and $Z$ is the pole residue. For this page we suppress $Z$ or absorb it into properly normalized production and decay amplitudes. The important denominator is

$$
q^2-M^2+iM\Gamma.
$$

The corresponding Breit–Wigner line shape in $q^2$ is

$$
\rho_{\rm BW}(q^2)
=
\frac{1}{\pi}\frac{M\Gamma}{(q^2-M^2)^2+M^2\Gamma^2}.
$$

If the physical lower and upper limits can be extended to $-\infty$ and $+\infty$ on the narrow scale of the peak, then

$$
\int_{-\infty}^{\infty}dq^2\,\rho_{\rm BW}(q^2)=1.
$$

That normalization is the mathematical source of the delta-function replacement.

## Delta-function limit

The standard distributional identity is

$$
\lim_{\epsilon\to0^+}
\frac{1}{\pi}\frac{\epsilon}{x^2+\epsilon^2}
=
\delta(x).
$$

Set

$$
x=q^2-M^2,
\qquad
\epsilon=M\Gamma.
$$

Then

$$
\frac{1}{\pi}\frac{M\Gamma}{(q^2-M^2)^2+M^2\Gamma^2}
\to
\delta(q^2-M^2),
$$

or equivalently

$$
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}
\to
\frac{\pi}{M\Gamma}\delta(q^2-M^2).
$$

The arrow means “inside an integral against a smooth test function.” More explicitly, if $f(q^2)$ is smooth on the scale $M\Gamma$, then

$$
\int dq^2\,
\frac{f(q^2)}{(q^2-M^2)^2+M^2\Gamma^2}
\simeq
\frac{\pi}{M\Gamma}f(M^2).
$$

The leading corrections are controlled by how fast $f$ changes across the resonance region and by how much the physical integration limits cut into the peak.

## Phase-space factorization

The narrow-width approximation needs one exact kinematic identity before it needs any approximation.

Suppose a final-state subset has total momentum

$$
q=\sum_{a\in X}p_a.
$$

Then Lorentz-invariant phase space factorizes as

$$
 d\Pi_{B+X}(P;p_B,X)
 =
 \frac{dq^2}{2\pi}\,
 d\Pi_{B R}(P;p_B,q)
 d\Pi_X(q).
$$

The notation $d\Pi_{B R}$ means the phase space for producing a particle of invariant mass $q^2$ and momentum $q$, not yet assuming that $q^2=M^2$. This identity is exact. It is simply a way of inserting the invariant mass $q^2$ of a final-state cluster.

For a longer cascade, the same identity can be applied repeatedly. This is why realistic event generators often organize phase space around intermediate invariant masses even before any narrow-width approximation is made.

## Scalar derivation of factorization

Consider a scalar resonance $R$ appearing in a process

$$
I\to B+R^*(q)\to B+X.
$$

Near the resonant region, assume the amplitude factorizes as

$$
\mathcal M(I\to B+X)
\simeq
\mathcal M_{\rm prod}(I\to B+R)
\frac{i}{q^2-M^2+iM\Gamma}
\mathcal M_{\rm dec}(R\to X).
$$

Then

$$
|\mathcal M|^2
\simeq
\frac{|\mathcal M_{\rm prod}|^2|\mathcal M_{\rm dec}|^2}
{(q^2-M^2)^2+M^2\Gamma^2}.
$$

Using phase-space factorization, a decay cascade has

$$
 d\Gamma(A\to B+X)
 =
 \frac{1}{2m_A}
 \frac{dq^2}{2\pi}
 d\Pi_{B R}
 d\Pi_X
 \frac{|\mathcal M_{\rm prod}|^2|\mathcal M_{\rm dec}|^2}
 {(q^2-M^2)^2+M^2\Gamma^2}.
$$

The decay part is related to the off-shell partial width by

$$
 d\Gamma(R(q)\to X)
 =
 \frac{1}{2\sqrt{q^2}}|\mathcal M_{\rm dec}|^2d\Pi_X.
$$

Near the pole, $\sqrt{q^2}\simeq M$, so

$$
|\mathcal M_{\rm dec}|^2d\Pi_X
\simeq
2M\,d\Gamma(R\to X).
$$

The $q^2$ integral then contains

$$
\int\frac{dq^2}{2\pi}
\frac{2M\,d\Gamma(R\to X)}{(q^2-M^2)^2+M^2\Gamma^2}
\simeq
\frac{d\Gamma(R\to X)}{\Gamma}.
$$

Therefore

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\,
 \frac{d\Gamma(R\to X)}{\Gamma}.
$$

After integrating over the decay variables of $X$,

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\,
 \operatorname{Br}(R\to X).
$$

The same derivation applies to cross sections, replacing the initial decay prefactor $1/(2m_A)$ by the appropriate flux factor for the production process.

## What exactly factorizes?

There are three levels of factorization, and they should not be blurred.

| Level | Statement | Caveat |
|---|---|---|
| Propagator peak | Breit–Wigner becomes a delta function in $q^2$ | Only inside an integral |
| Phase space | $d\Pi$ splits into production and decay phase spaces | Exact before approximation |
| Rate or cross section | production $\times$ branching fraction | Requires narrow isolated resonance and smooth background |

The differential form

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\,
 \frac{d\Gamma(R\to X)}{\Gamma}
$$

keeps the decay kinematics of $R\to X$. The more compact formula

$$
\Gamma(A\to B+X)
\simeq
\Gamma(A\to B+R)\,
\operatorname{Br}(R\to X)
$$

is obtained only after integrating over the decay channel $X$.

Likewise, for scattering,

$$
 \sigma(I\to B+X)
 \simeq
 \sigma(I\to B+R)\,\operatorname{Br}(R\to X)
$$

is an integrated resonant approximation. A differential invariant-mass distribution still has a Breit–Wigner shape before the $q^2$ integral is performed.

## Spin correlations

For a spinful resonance, the numerator of the propagator carries polarization information. Near the pole, the amplitude is better written as

$$
\mathcal M
\simeq
\sum_\lambda
\mathcal M^{\lambda}_{\rm prod}
\frac{i}{q^2-M^2+iM\Gamma}
\mathcal M^{\lambda}_{\rm dec},
$$

where $\lambda$ labels physical polarization states of the nearly on-shell resonance. Squaring gives

$$
|\mathcal M|^2
\simeq
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}
\sum_{\lambda,\lambda'}
\mathcal M^{\lambda}_{\rm prod}
\mathcal M^{\lambda' *}_{\rm prod}
\mathcal M^{\lambda}_{\rm dec}
\mathcal M^{\lambda' *}_{\rm dec}.
$$

This is a product of a production spin-density matrix and a decay spin-density matrix. If one integrates inclusively over the decay angles, or if the resonance is scalar, the result often reduces to the simple product of an unpolarized production rate and a branching fraction. If angular correlations matter, the narrow-width approximation can still be used, but the spin density matrices must be retained.

This point matters in decays of polarized particles, vector boson decays, top-quark decays, and collider analyses where angular distributions are observables rather than nuisances.

## When the approximation is reliable

The narrow-width approximation is reliable when all of the following are true.

| Requirement | Meaning |
|---|---|
| $\Gamma/M\ll1$ | The resonance peak is parametrically narrow. |
| Isolated pole | No nearby resonance overlaps significantly. |
| Smooth nonresonant factors | Matrix elements, PDFs, cuts, and phase-space boundaries do not vary rapidly over $\Delta q^2\sim M\Gamma$. |
| Weak interference | Nonresonant background or other resonances do not interfere strongly across the peak. |
| Consistent width definition | The mass and width are defined in a pole or scheme-consistent way. |
| Gauge consistency | In gauge theories, the resonant approximation respects Ward or Slavnov–Taylor identities. |

The most important warning is near thresholds. If $M$ lies close to a kinematic threshold, phase space can change rapidly over the width of the resonance. Then replacing everything by its value at $q^2=M^2$ can be inaccurate even when $\Gamma/M$ looks small.

Cuts can cause the same problem. A detector-level cut on invariant mass, transverse momentum, or angle may carve through the Breit–Wigner peak. Then the naive production-times-branching-fraction formula may miss acceptance effects.

## Gauge theories and unstable particles

In gauge theories, adding a width by hand to one propagator can break gauge cancellations. For example, modifying a vector-boson propagator denominator without consistently modifying the rest of the amplitude can spoil Ward identities.

The clean conceptual object is the pole of the full amplitude. Near an isolated pole, the pole position and residue organize a gauge-invariant expansion of the resonant contribution. Practical schemes such as pole expansions and complex-mass schemes are designed to preserve gauge consistency while keeping finite-width effects.

For this page, the main lesson is simple: the narrow-width approximation is safest when used as an on-shell factorization statement for a gauge-invariant production process times a gauge-invariant decay branching fraction. It is less safe as a casual instruction to insert $iM\Gamma$ into denominators wherever a particle looks unstable.

## Practical workflow

For a resonant process, use this checklist.

1. Identify the invariant mass $q^2$ flowing through the candidate resonance.
2. Check that the resonance is isolated and narrow: $\Gamma/M\ll1$.
3. Factorize phase space using $dq^2/(2\pi)$.
4. Write the resonant amplitude near the pole.
5. Replace the squared Breit–Wigner denominator by $\pi\delta(q^2-M^2)/(M\Gamma)$ only inside the $q^2$ integral.
6. Convert the decay matrix element and decay phase space into a partial width.
7. Keep spin correlations if angular information is part of the observable.
8. Check whether thresholds, cuts, interference, or gauge cancellations invalidate the simple factorized result.

For a first-pass analytic estimate, the approximation is often excellent. For precision predictions, it is a starting point, not the finish line.

## Common pitfalls

**Using the delta function before integrating over invariant mass.** The Breit–Wigner shape is a function of $q^2$. The delta function is its integrated narrow-width limit.

**Forgetting the factor $\pi/(M\Gamma)$.** The width appears in the denominator of the area under the peak. Dropping this factor destroys the branching-ratio interpretation.

**Confusing partial and total widths.** The propagator denominator contains the total width $\Gamma$. The decay channel supplies the partial width $\Gamma(R\to X)$. Their ratio is the branching fraction.

**Ignoring spin correlations.** The simple product of an unpolarized production rate and a branching fraction can wash out angular correlations.

**Applying the approximation near thresholds.** If phase space changes rapidly near $q^2=M^2$, the smooth-test-function assumption fails.

**Neglecting interference.** A nonresonant background or nearby resonance can interfere with the resonant amplitude. The narrow-width approximation isolates the pole contribution; it does not automatically include all physical effects.

**Breaking gauge invariance with an ad hoc width.** In gauge theories, finite-width treatments must respect gauge identities. The pole expansion is the clean organizing principle.

## Relations to other pages

- [Decay Rates](/perturbative-qft/phase-space-cross-sections-decays/decay-rates/) defines partial widths, total widths, lifetimes, and branching fractions.
- [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/) gives the measure whose recursive factorization is used here.
- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) supplies the most common building block for resonance decays.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) gives the cross-section normalization used when the resonant process is produced by two incoming particles.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) explains why total rates are connected to imaginary parts of forward amplitudes.

## Research status

- **Established:** The delta-function limit of a Breit–Wigner peak and the resulting production-times-branching-fraction formula are standard tools for isolated narrow resonances.
- **Approximate:** Corrections are controlled by $\Gamma/M$, by variation of the nonresonant factors across the peak, and by the size of interference with other amplitudes.
- **Convention-dependent:** Different mass and width definitions, such as on-shell parameters and pole parameters, agree at leading narrow width but differ beyond leading order.
- **Active:** Precision unstable-particle physics uses pole schemes, complex-mass schemes, off-shell calculations, resummation, nonfactorizable corrections, and careful treatment of experimental cuts.

## Exercises

### Exercise 1: Prove the delta-function identity

Show that

$$
\lim_{\epsilon\to0^+}
\frac{1}{\pi}\frac{\epsilon}{x^2+\epsilon^2}
=
\delta(x)
$$

as a distribution.

<details>
<summary><strong>Solution</strong></summary>

Let $f(x)$ be smooth and slowly varying near $x=0$. Consider

$$
I_\epsilon
=
\int_{-\infty}^{\infty}dx\,
\frac{1}{\pi}\frac{\epsilon}{x^2+\epsilon^2}f(x).
$$

Set $x=\epsilon y$, so $dx=\epsilon dy$. Then

$$
I_\epsilon
=
\int_{-\infty}^{\infty}dy\,
\frac{1}{\pi}\frac{1}{1+y^2}f(\epsilon y).
$$

As $\epsilon\to0^+$, $f(\epsilon y)\to f(0)$ for the region contributing to the integral. Thus

$$
I_\epsilon
\to
f(0)\int_{-\infty}^{\infty}dy\,\frac{1}{\pi}\frac{1}{1+y^2}
=f(0),
$$

because

$$
\int_{-\infty}^{\infty}\frac{dy}{1+y^2}=\pi.
$$

Therefore the sequence of functions converges to $\delta(x)$ in the distributional sense.

</details>

### Exercise 2: Area under the Breit–Wigner peak

Evaluate

$$
I=
\int_{-\infty}^{\infty}dq^2\,
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Set

$$
x=q^2-M^2,
\qquad
\epsilon=M\Gamma.
$$

Then $dq^2=dx$ and

$$
I=\int_{-\infty}^{\infty}dx\,\frac{1}{x^2+\epsilon^2}
=\frac{\pi}{\epsilon}
=\frac{\pi}{M\Gamma}.
$$

This is exactly the normalization appearing in

$$
\frac{1}{(q^2-M^2)^2+M^2\Gamma^2}
\to
\frac{\pi}{M\Gamma}\delta(q^2-M^2).
$$

</details>

### Exercise 3: Derive production times branching fraction

For a scalar resonance, use

$$
 d\Pi_{B+X}
 =
 \frac{dq^2}{2\pi}d\Pi_{B R}d\Pi_X
$$

and

$$
|\mathcal M|^2
\simeq
\frac{|\mathcal M_{\rm prod}|^2|\mathcal M_{\rm dec}|^2}
{(q^2-M^2)^2+M^2\Gamma^2}
$$

to show that

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\frac{\Gamma(R\to X)}{\Gamma}
$$

after integrating over the decay phase space of $X$.

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
 d\Gamma(A\to B+X)
 =
 \frac{1}{2m_A}\frac{dq^2}{2\pi}d\Pi_{B R}d\Pi_X
 \frac{|\mathcal M_{\rm prod}|^2|\mathcal M_{\rm dec}|^2}
 {(q^2-M^2)^2+M^2\Gamma^2}.
$$

The decay phase-space integral defines the partial width:

$$
\Gamma(R\to X)
=
\frac{1}{2M}\int d\Pi_X|\mathcal M_{\rm dec}|^2.
$$

Thus near $q^2=M^2$,

$$
\int d\Pi_X|\mathcal M_{\rm dec}|^2
=2M\Gamma(R\to X).
$$

The $q^2$ integral gives

$$
\int\frac{dq^2}{2\pi}
\frac{2M\Gamma(R\to X)}{(q^2-M^2)^2+M^2\Gamma^2}
=
\frac{2M\Gamma_X}{2\pi}\frac{\pi}{M\Gamma}
=
\frac{\Gamma_X}{\Gamma}.
$$

The remaining production factors are

$$
\frac{1}{2m_A}|\mathcal M_{\rm prod}|^2d\Pi_{B R}
=d\Gamma(A\to B+R),
$$

so

$$
 d\Gamma(A\to B+X)
 \simeq
 d\Gamma(A\to B+R)\frac{\Gamma(R\to X)}{\Gamma}.
$$

</details>

### Exercise 4: Threshold failure

Explain why the narrow-width approximation can fail when $M$ is close to the threshold for $R\to X$, even if $\Gamma/M$ is numerically small.

<details>
<summary><strong>Solution</strong></summary>

The narrow-width approximation assumes that the nonresonant part of the integrand is smooth across the peak width

$$
\Delta q^2\sim M\Gamma.
$$

Near a threshold, the decay phase space changes rapidly. For example, a two-body decay has

$$
|\mathbf p_*|
=\frac{\sqrt{\lambda(q^2,m_1^2,m_2^2)}}{2\sqrt{q^2}},
$$

which vanishes at

$$
q^2=(m_1+m_2)^2.
$$

If $M^2$ is within order $M\Gamma$ of this threshold, the factor $|\mathbf p_*|$ varies strongly across the Breit–Wigner peak. Then replacing it by its value at $q^2=M^2$ is not reliable.

</details>

### Exercise 5: Spin correlations

For a spinful resonance, why is

$$
\sigma(I\to R\to X)
\simeq
\sigma(I\to R)\operatorname{Br}(R\to X)
$$

not always enough to predict angular distributions in $X$?

<details>
<summary><strong>Solution</strong></summary>

A spinful resonance can be produced with a nontrivial polarization density matrix. The decay distribution depends on that polarization. In the narrow-width approximation, the amplitude has the structure

$$
\mathcal M
\simeq
\sum_\lambda
\mathcal M_{\rm prod}^{\lambda}
\frac{i}{q^2-M^2+iM\Gamma}
\mathcal M_{\rm dec}^{\lambda}.
$$

Squaring gives interference between polarization labels:

$$
\sum_{\lambda,\lambda'}
\mathcal M_{\rm prod}^{\lambda}
\mathcal M_{\rm prod}^{\lambda' *}
\mathcal M_{\rm dec}^{\lambda}
\mathcal M_{\rm dec}^{\lambda' *}.
$$

The total rate may reduce to production times branching fraction after summing inclusively over decay angles. But differential angular distributions retain the spin-density information. Therefore a spin-correlated narrow-width approximation is needed when the angular distribution is part of the observable.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §25, for unstable particles, resonances, and Breit–Wigner behavior.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, rates, resonances, and the $S$-matrix framework.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 17, for unstable particles and the Breit–Wigner formula.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 24, for decay/cross-section normalization and implications of unitarity.

## Version history

- **2026-06-12:** Initial qft.org page on Breit–Wigner line shapes, the delta-function narrow-width limit, resonant phase-space factorization, branching fractions, spin correlations, and gauge-theory caveats.
