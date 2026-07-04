---
title: "Threshold Behavior"
description: "How amplitudes, discontinuities, and rates behave near physical production thresholds."
sidebar:
  label: "Threshold Behavior"
  order: 6
level: Graduate
status: "Polished draft"
source: "Weinberg, The Quantum Theory of Fields, Vol. I, scattering theory; Srednicki, Quantum Field Theory, scattering and loop-threshold discussions; Coleman, Lectures on Quantum Field Theory, scattering and unstable-particle chapters; Eden et al., The Analytic S-Matrix."
topics:
  - threshold behavior
  - branch points
  - phase space
  - partial waves
  - unitarity
canonicalTopics:
  - threshold-behavior
  - analytic-structure
  - phase-space-near-threshold
  - partial-wave-threshold-laws
researchStatus:
  established:
    - "Two-body thresholds, square-root branch points, phase-space powers, and partial-wave threshold laws are standard consequences of unitarity, analyticity, and angular momentum."
  active:
    - "Threshold expansions in theories with long-range forces, unstable particles, overlapping scales, or multi-particle cuts require more refined EFT and resummation methods."
---

## Summary

A **threshold** is the energy at which a new set of on-shell intermediate or final states becomes kinematically allowed. Near a threshold, amplitudes are not ordinary Taylor series in the energy. They develop branch points, imaginary parts, and characteristic powers of the center-of-mass momentum.

For two particles of masses $m_1$ and $m_2$ in an $s$-channel, the normal two-particle threshold is

$$
s_{\mathrm{th}}=(m_1+m_2)^2.
$$

The center-of-mass momentum is

$$
k(s)=\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{2\sqrt{s}},
\qquad
\lambda(s,m_1^2,m_2^2)
=\big[s-(m_1+m_2)^2\big]\big[s-(m_1-m_2)^2\big].
$$

The square root is the whole story in miniature: it is real above the physical threshold, imaginary below it, and multi-valued as a function of complex $s$. This is why threshold behavior is simultaneously kinematics, unitarity, and analytic structure.

Near an ordinary two-body threshold, the available phase space behaves as

$$
d\Pi_2\sim k.
$$

If the produced pair is in orbital angular momentum $\ell$, a short-range production amplitude behaves schematically as

$$
\mathcal A_\ell\sim k^\ell,
\qquad
\text{rate contribution}\sim k^{2\ell+1}.
$$

The $+1$ power comes from two-body phase space; the $2\ell$ power comes from the angular-momentum barrier.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![Threshold branch point and physical cut](/figures/perturbative-qft/threshold-behavior.svg)

<figcaption>

A normal two-particle threshold produces a branch point at $s=s_{\mathrm{th}}$ and a physical cut for larger real $s$. The local coordinate is $k\sim\sqrt{s-s_{\mathrm{th}}}$, so threshold expansions naturally involve powers of $k$, not only powers of $s-s_{\mathrm{th}}$.

</figcaption>
</figure>

This page explains the local anatomy of thresholds. The goal is not to catalogue every possible singularity of Feynman integrals, but to make the first threshold laws predictable enough that later pages on cuts, dispersion relations, resonances, positivity, and EFT expansions feel less like magic.

## Prerequisites

You should know [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/), [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/), and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/).

For the spin and angular-momentum language, review [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/).

## Core idea

Threshold singularities arise because denominators can vanish while all cut lines carry physical on-shell momenta. The analytic function that represented an off-shell virtual process now knows about real states.

There are three complementary viewpoints.

| Viewpoint | Threshold meaning |
|---|---|
| Kinematics | A final or intermediate state first becomes allowed. |
| Phase space | The measure for on-shell states opens with a characteristic power of $k$. |
| Analyticity | The amplitude has a branch point and a cut in a complex invariant. |

The simplest mental picture is a two-particle bubble. Below threshold, the two internal particles cannot both be on shell with the required total momentum. Above threshold, they can. The imaginary part that appears is not an optional loop-calculation artifact; it is demanded by unitarity.

## Setup and conventions

We use the qft.org scattering conventions fixed in [Conventions and Notation](/perturbative-qft/conventions/). Amplitudes are defined by

$$
S_{fi}=\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi},
$$

and the invariant $n$-body phase-space measure is

$$
d\Pi_n(P)
=(2\pi)^4\delta^{(4)}\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

The formulas below focus on relativistic QFT in flat spacetime with stable external particles. We distinguish three notions that students often blend together:

| Word | Meaning |
|---|---|
| Threshold | Kinematic onset of a possible on-shell state. |
| Branch point | Analytic singularity at the threshold location. |
| Cut | Conventional line in the complex plane across which the amplitude has a discontinuity. |

The branch point is physical. The exact placement of the cut is a convention, but for scattering amplitudes one usually places the physical right-hand cut along the real axis above threshold.

## Two-body kinematics near threshold

Let $P^\mu$ be the total four-momentum of two particles with invariant mass squared

$$
s=P^2.
$$

In the center-of-mass frame,

$$
P^\mu=(\sqrt{s},\mathbf 0),
$$

and the two final momenta are

$$
p_1^\mu=(E_1,\mathbf k),
\qquad
p_2^\mu=(E_2,-\mathbf k).
$$

The magnitude of the three-momentum is fixed by energy conservation:

$$
\sqrt{s}=\sqrt{k^2+m_1^2}+\sqrt{k^2+m_2^2}.
$$

Solving gives

$$
k(s)=\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{2\sqrt{s}}.
$$

The physical threshold is where $k=0$ at the positive-energy point,

$$
s=(m_1+m_2)^2.
$$

There is also a second zero of $\lambda$ at

$$
s=(m_1-m_2)^2.
$$

For ordinary production in the $s$ channel, this second point is not the physical opening of the two-particle state. It is nevertheless part of the analytic structure of the square root and becomes important when following amplitudes between different sheets or channels.

Near threshold, write

$$
\sqrt{s}=m_1+m_2+E,
\qquad
E\ll m_1+m_2.
$$

Then

$$
k^2\simeq 2\mu E,
\qquad
\mu=\frac{m_1m_2}{m_1+m_2},
$$

where $\mu$ is the reduced mass. Thus

$$
k\sim E^{1/2}.
$$

This square-root behavior is the seed of the threshold branch point.

## Phase-space opening

The two-body phase space in the center-of-mass frame can be written as

$$
d\Pi_2(P;p_1,p_2)
=\frac{k}{16\pi^2\sqrt{s}}\,d\Omega,
$$

so the angularly integrated phase space is

$$
\Phi_2(s;m_1,m_2)
=\int d\Pi_2
=\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{8\pi s}.
$$

Near a normal two-body threshold,

$$
\Phi_2\sim k\sim \sqrt{s-(m_1+m_2)^2}.
$$

Therefore even if the squared matrix element is smooth and nonzero at threshold, the total rate or cross section has a square-root onset.

For a decay $A\to 1+2$, the partial width is

$$
\Gamma_{A\to12}
=\frac{1}{2M_A}\int d\Pi_2\,|\mathcal M|^2,
$$

so if $|\mathcal M|^2$ is smooth at threshold,

$$
\Gamma_{A\to12}\propto k.
$$

For $2\to2$ scattering, the same phase-space factor appears in the final-state density. Flux factors and initial-state kinematics can add other powers, especially if the initial particles are also near threshold, but the basic final-state opening is the same.

## Angular-momentum barriers

The phase-space factor is not the only source of threshold powers. Angular momentum matters.

For short-range interactions, a production amplitude into a final two-particle state with relative orbital angular momentum $\ell$ is suppressed near threshold by

$$
\mathcal A_\ell\sim k^\ell.
$$

The corresponding rate behaves as

$$
\Gamma_\ell\sim k^{2\ell+1}.
$$

The first few cases are worth remembering.

| Final orbital wave | Amplitude behavior | Rate behavior |
|---|---:|---:|
| $s$ wave, $\ell=0$ | $k^0$ | $k$ |
| $p$ wave, $\ell=1$ | $k$ | $k^3$ |
| $d$ wave, $\ell=2$ | $k^2$ | $k^5$ |

This is why a decay barely above threshold can be strongly suppressed even when it is kinematically allowed. Phase space opens the door; angular momentum determines how narrow the door is.

For elastic scattering partial waves, one often says that the short-range partial-wave amplitude begins as $k^{2\ell}$. This is compatible with the production statement once the conventional normalization of incoming and outgoing partial waves is accounted for.

## Bubble integrals and square-root branch points

A scalar one-loop bubble already contains the essential analytic structure. Consider the equal-mass integral with $p^2=s$,

$$
I(s)=\mu^{2\epsilon}\int\frac{d^d\ell}{(2\pi)^d}\,
\frac{i}{\ell^2-m^2+i0}\,
\frac{i}{(\ell+p)^2-m^2+i0}.
$$

After Feynman parametrization, the logarithmic part has the schematic form

$$
I(s)\supset \int_0^1 dx\,\log\!\left[m^2-x(1-x)s-i0\right].
$$

For $s<4m^2$, the argument of the logarithm stays positive for all $0\le x\le1$. For $s>4m^2$, it becomes negative over an interval around $x=1/2$. The logarithm then develops an imaginary part.

The threshold is fixed by

$$
m^2-x(1-x)s=0
$$

having a solution inside the integration region. Since the maximum of $x(1-x)$ is $1/4$, the first solution appears at

$$
s=4m^2.
$$

The discontinuity is proportional to the two-particle phase space. For equal masses, the characteristic factor is

$$
\sqrt{1-\frac{4m^2}{s}}.
$$

The square root is not an accident of a chosen integral representation. It is the analytic version of the center-of-mass momentum.

## Discontinuities from unitarity

Across a physical threshold cut, the discontinuity of an amplitude is governed by on-shell intermediate states. In a schematic two-body channel,

$$
\operatorname{Disc}\mathcal M_{i\to f}
\sim
\int d\Pi_2\,
\mathcal M_{i\to 12}\,\mathcal M_{f\to 12}^*.
$$

This is the local content of perturbative unitarity. The two particles crossing the cut are placed on shell, and their Lorentz-invariant phase space is integrated.

Near a two-body threshold, if the amplitudes on the right-hand side are smooth, the discontinuity inherits the phase-space power:

$$
\operatorname{Disc}\mathcal M\sim k.
$$

If the on-shell subamplitudes vanish by angular momentum, spin, symmetry, helicity, or gauge constraints, additional powers of $k$ appear.

This observation is often more powerful than explicitly evaluating a loop integral. You can predict the leading nonanalytic behavior just by asking which on-shell states can appear and how their phase space opens.

## Multi-particle thresholds

For $n$ massive particles produced near a common nonrelativistic threshold,

$$
\sqrt{s}=\sum_{a=1}^n m_a+E,
\qquad
E\ll \sum_a m_a,
$$

the available momenta scale as

$$
|\mathbf p_a|\sim E^{1/2}.
$$

The total nonrelativistic phase-space volume scales as

$$
\Phi_n(E)\sim E^{\frac{3n}{2}-\frac52},
$$

assuming a smooth matrix element and no additional constraints. This formula gives

$$
\Phi_2(E)\sim E^{1/2},
\qquad
\Phi_3(E)\sim E^2,
\qquad
\Phi_4(E)\sim E^{7/2}.
$$

The power increases because more particles require more momentum components to be distributed while satisfying total momentum and energy conservation.

Massless thresholds behave differently. If some particles are massless, thresholds can begin at $s=0$, and soft or collinear regions can generate logarithms rather than simple integer or half-integer powers. That is why infrared physics has its own chapter.

## Normal, pseudo, and anomalous thresholds

Not every threshold-like singularity has the same interpretation.

A **normal threshold** appears when a set of intermediate particles can all go on shell with positive energies in the channel under consideration. The two-particle threshold at $(m_1+m_2)^2$ is the canonical example.

A **pseudo-threshold** is associated with another zero of a kinematic square root, such as

$$
s=(m_1-m_2)^2.
$$

It belongs to the analytic structure, but it is not the physical onset of producing particles $1$ and $2$ from positive total energy in the usual $s$ channel.

An **anomalous threshold** can occur when a more complicated Landau singularity pinches the integration contour in a way not visible from the simplest two-particle phase-space argument. These appear in multi-leg and multi-loop diagrams and require Landau-equation analysis.

The practical rule is this: identify the physical channel and the on-shell states first. Then use analytic continuation to understand how the same singularity appears on different sheets or in crossed channels.

## Thresholds and resonances

A resonance near threshold is especially delicate. A stable-particle threshold gives a branch point. A resonance gives a pole on an unphysical sheet. When they are close, neither feature can be ignored.

A familiar schematic form is

$$
\mathcal M(s)\sim \frac{g^2}{s-M_0^2-\Sigma(s)},
$$

where $\Sigma(s)$ is a self-energy. If $\Sigma(s)$ has a threshold branch point near $M_0^2$, then the line shape is not a simple constant-width Breit–Wigner curve.

Near-threshold states can look like bound states, virtual states, resonances, or cusps depending on the pole locations on the relevant Riemann sheets. In such cases, one often uses nonrelativistic EFT, effective-range expansions, or unitarized amplitudes rather than an ordinary Taylor expansion.

## Threshold expansion as a local approximation

Near a threshold, it is often better to expand in $k$ rather than in $s$ itself. For equal masses,

$$
k=\frac12\sqrt{s-4m^2}
$$

up to the conventional normalization by $\sqrt{s}$. A threshold expansion therefore has the form

$$
\mathcal M(s)=a_0+a_1 k+a_2 k^2+a_3 k^3+\cdots,
$$

possibly with logarithms or Coulombic singularities.

Which terms are allowed depends on the channel. In a simple elastic $s$ wave, unitarity often makes the imaginary part begin as

$$
\operatorname{Im}\mathcal M\sim k,
$$

while the real part can have a constant threshold value. For higher partial waves, the leading threshold behavior is pushed to higher powers.

This is why a naive Taylor expansion in $s-s_{\mathrm{th}}$ is often the wrong local coordinate. The amplitude is naturally analytic in $k$ on the appropriate sheet, not single-valued in $s$.

## Worked example: scalar decay into two identical scalars

Consider a scalar $A$ of mass $M$ decaying into two identical scalars $\phi$ of mass $m$ through a smooth constant tree amplitude

$$
\mathcal M(A\to\phi\phi)=g.
$$

The decay is allowed only for

$$
M>2m.
$$

The two-body momentum is

$$
k=\frac12\sqrt{M^2-4m^2}.
$$

Because the final particles are identical, the decay width includes a factor $1/2!$:

$$
\Gamma(A\to\phi\phi)
=\frac{1}{2M}\frac{1}{2!}\int d\Pi_2\,|g|^2.
$$

Using

$$
\int d\Pi_2=\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{M^2}},
$$

we get

$$
\Gamma(A\to\phi\phi)
=\frac{|g|^2}{32\pi M}
\sqrt{1-\frac{4m^2}{M^2}}.
$$

Near threshold, with $M=2m+E$ and $E\ll m$,

$$
\Gamma\propto \sqrt{E}.
$$

A single square root encodes the fact that the final particles have almost no room to move.

## What changes with massless particles?

Massless particles replace clean threshold powers with infrared structure. If a massless photon or gluon can be emitted with arbitrarily small energy, the threshold for adding extra radiation coincides with the lower-multiplicity process.

For example, in QED, an exclusive process with no emitted photons is not generally an infrared-safe observable. Virtual soft photons and real soft photons both contribute singular terms. Only sufficiently inclusive observables are finite.

Thus the clean massive threshold statement

$$
\Phi_2\sim k
$$

should not be confused with the infrared behavior of massless theories. In massless gauge theories, soft and collinear limits require eikonal factors, jet functions, factorization, and sometimes resummation.

## Common pitfalls

**Expanding in the wrong variable.** Near a two-body threshold, the natural local variable is often $k\sim\sqrt{s-s_{\mathrm{th}}}$, not $s-s_{\mathrm{th}}$.

**Calling every branch point a physical production threshold.** Pseudo-thresholds and anomalous thresholds are real analytic features, but they are not all ordinary openings of positive-energy final states in the chosen channel.

**Ignoring angular momentum.** Phase space may open as $k$, but a $p$-wave process can still be suppressed as $k^3$ in the rate.

**Using a constant-width Breit–Wigner formula at threshold.** If the width comes from a channel that opens nearby, the width is energy-dependent and inherits threshold powers.

**Forgetting identical-particle factors.** Threshold powers tell you how a rate scales. They do not replace the statistical factors in phase-space integrals.

**Treating massless thresholds like massive thresholds.** Soft and collinear singularities produce logarithms and cancellations between real and virtual processes. The massive square-root intuition is not enough.

## Relations to other pages

- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) derives the phase-space factors used here.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) applies these kinematics to differential cross sections.
- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) explains why discontinuities are computed by putting lines on shell.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) develops the complex-analysis language used for thresholds.
- [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) explains the angular-momentum version of threshold laws.
- [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) gives the general diagrammatic criterion for singularities of Feynman integrals.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) explains when an unstable near-threshold state can or cannot be treated as an ordinary resonance.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) take over when massless particles create infrared thresholds.

## Research status

- **Established:** The normal-threshold branch points, two-body phase-space powers, and angular-momentum threshold laws described here are standard consequences of relativistic kinematics, unitarity, and analyticity.
- **Active:** Precision threshold calculations for heavy particles, unstable particles, hadrons near thresholds, Coulombic systems, and collider observables often require EFT matching, finite-width treatments, resummation, or nonperturbative input.
- **Speculative:** The basic threshold laws are not speculative. What can become model-dependent is the interpretation of near-threshold poles in strongly coupled systems.

## Exercises

### Exercise 1: Two-body momentum

Starting from

$$
\sqrt{s}=\sqrt{k^2+m_1^2}+\sqrt{k^2+m_2^2},
$$

show that

$$
k(s)=\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{2\sqrt{s}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Move one square root to the other side and square:

$$
s+m_1^2-m_2^2=2\sqrt{s}\,E_1.
$$

Therefore

$$
E_1=\frac{s+m_1^2-m_2^2}{2\sqrt{s}}.
$$

Since $E_1^2=k^2+m_1^2$,

$$
k^2=\frac{(s+m_1^2-m_2^2)^2}{4s}-m_1^2.
$$

Expanding the numerator gives

$$
k^2=\frac{s^2+m_1^4+m_2^4-2sm_1^2-2sm_2^2-2m_1^2m_2^2}{4s}.
$$

The numerator is

$$
\lambda(s,m_1^2,m_2^2)
=\big[s-(m_1+m_2)^2\big]\big[s-(m_1-m_2)^2\big],
$$

so

$$
k=\frac{\lambda^{1/2}(s,m_1^2,m_2^2)}{2\sqrt{s}}.
$$

</details>

### Exercise 2: Near-threshold expansion

Let $\sqrt{s}=m_1+m_2+E$ with $E\ll m_1+m_2$. Show that

$$
k^2\simeq 2\mu E,
\qquad
\mu=\frac{m_1m_2}{m_1+m_2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Near threshold the particles are nonrelativistic, so

$$
E_1=m_1+\frac{k^2}{2m_1}+\cdots,
\qquad
E_2=m_2+\frac{k^2}{2m_2}+\cdots.
$$

Energy conservation gives

$$
E=\frac{k^2}{2}\left(\frac1{m_1}+\frac1{m_2}\right)+\cdots
=\frac{k^2}{2\mu}+\cdots.
$$

Thus

$$
k^2\simeq 2\mu E.
$$

</details>

### Exercise 3: Multi-particle phase-space scaling

Derive the nonrelativistic scaling

$$
\Phi_n(E)\sim E^{\frac{3n}{2}-\frac52}
$$

for $n$ massive particles near common threshold, assuming a smooth matrix element.

<details>
<summary><strong>Solution</strong></summary>

Near threshold all momenta scale as

$$
|\mathbf p_a|\sim E^{1/2}.
$$

The product of $n$ three-momentum measures scales as

$$
\prod_{a=1}^n d^3\mathbf p_a\sim E^{3n/2}.
$$

The momentum-conservation delta function scales as

$$
\delta^{(3)}\!\left(\sum_a\mathbf p_a\right)\sim E^{-3/2},
$$

and the energy-conservation delta function scales as

$$
\delta\!\left(E-\sum_a \frac{\mathbf p_a^2}{2m_a}\right)\sim E^{-1}.
$$

The factors $1/(2E_a)$ are finite constants near threshold. Thus

$$
\Phi_n(E)\sim E^{3n/2}E^{-3/2}E^{-1}
=E^{\frac{3n}{2}-\frac52}.
$$

</details>

### Exercise 4: Angular-momentum barrier

Suppose a two-body decay amplitude into relative orbital angular momentum $\ell$ behaves as $\mathcal A_\ell\sim k^\ell$. Show that the corresponding decay rate scales as $k^{2\ell+1}$.

<details>
<summary><strong>Solution</strong></summary>

The squared amplitude scales as

$$
|\mathcal A_\ell|^2\sim k^{2\ell}.
$$

Two-body phase space contributes one additional power,

$$
d\Pi_2\sim k.
$$

Therefore the rate scales as

$$
\Gamma_\ell\sim k^{2\ell}k=k^{2\ell+1}.
$$

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering theory, partial waves, thresholds, and resonances.
- M. Srednicki, *Quantum Field Theory*, especially the sections on scattering amplitudes, decay rates, loop corrections, and unstable particles.
- S. Coleman, *Lectures on Quantum Field Theory*, especially the scattering, phase-space, LSZ, renormalization, and unstable-particle discussions.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for classic analytic-structure and threshold theory.
- G. F. Chew, *The Analytic S-Matrix*, for the historical S-matrix viewpoint on thresholds, cuts, and singularities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for unitarity, spectral structure, and threshold intuition in modern QFT language.

## Version history

- **2026-06-13:** Initial polished draft. Added two-body threshold laws, phase-space powers, partial-wave barriers, bubble-integral branch points, multi-particle scaling, common pitfalls, exercises, and a threshold branch-cut figure.
