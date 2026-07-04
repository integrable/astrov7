---
title: "Two-to-Two Scattering"
description: "A convention-safe derivation and practical workflow for converting a 2→2 invariant amplitude into differential and total cross sections."
sidebar:
  label: "Two-to-Two Scattering"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11; Weinberg 1995, Vol. I, ch. 3; Coleman 2019, chs. 11–12; Schwartz 2014, chs. 5 and 13"
topics:
  - two-to-two scattering
  - differential cross sections
  - Mandelstam variables
  - two-body phase space
  - invariant amplitudes
canonicalTopics:
  - two-to-two-scattering
  - differential-cross-section
  - scattering-angle
  - d-sigma-d-omega
  - d-sigma-dt
researchStatus:
  established:
    - "The 2→2 cross-section formulas follow from the standard S-matrix normalization, invariant flux factor, and two-body phase space."
  active:
    - "Precision applications require radiative corrections, infrared-safe observables, finite-width treatments, PDFs, cuts, and detector modeling beyond the tree-level 2→2 idealization."
---

## Summary

Two-to-two scattering is the workhorse case where amplitudes first become cross sections. For

$$
1(p_1)+2(p_2)\to3(p_3)+4(p_4),
$$

with center-of-momentum energy

$$
s=(p_1+p_2)^2,
$$

the qft.org differential cross-section formula is

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M(s,\theta,\phi)|^2}.
$$

Here $|\mathbf p_i^*|$ and $|\mathbf p_f^*|$ are the initial and final three-momentum magnitudes in the center-of-momentum frame:

$$
|\mathbf p_i^*|
=
\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}},
\qquad
|\mathbf p_f^*|
=
\frac{\sqrt{\lambda(s,m_3^2,m_4^2)}}{2\sqrt{s}}.
$$

For an unpolarized or azimuth-integrated observable, one often trades the scattering angle for the Mandelstam variable $t$. Then

$$
\frac{d\sigma}{dt}
=
\frac{1}{64\pi s |\mathbf p_i^*|^2}
\overline{|\mathcal M(s,t)|^2}
=
\frac{1}{16\pi\lambda(s,m_1^2,m_2^2)}
\overline{|\mathcal M(s,t)|^2}.
$$

For massless initial particles this becomes the familiar

$$
\frac{d\sigma}{dt}
=
\frac{\overline{|\mathcal M(s,t)|^2}}{16\pi s^2}.
$$

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Two-to-two scattering kinematics in the center-of-momentum frame, with incoming and outgoing momenta, scattering angle, and the formulas for d sigma over d Omega and d sigma over dt](/figures/perturbative-qft/two-to-two-scattering.svg)

<figcaption>

In the center-of-momentum frame the incoming momenta are back-to-back with magnitude $|\mathbf p_i^*|$, and the outgoing momenta are back-to-back with magnitude $|\mathbf p_f^*|$. The polar angle $\theta$ between $\mathbf p_1$ and $\mathbf p_3$ is equivalent to the invariant $t$ once $s$ and the masses are fixed.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/), and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/).

## Core idea

A $2\to2$ cross section has three ingredients:

| Ingredient | Role |
|---|---|
| $\mathcal M$ | dynamics of the process |
| $F_{12}$ | initial two-particle flux |
| $d\Pi_2$ | final two-body kinematics |

The formula is just

$$
 d\sigma
=
\frac{1}{F_{12}}
\overline{|\mathcal M|^2}d\Pi_2.
$$

The simplification happens because both factors on the right have closed center-of-momentum forms:

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s},
\qquad
 d\Pi_2=\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega.
$$

Multiplying them gives the master formula. So the problem of computing a $2\to2$ cross section reduces to computing the invariant amplitude, doing the spin and color sums or averages, and inserting the correct kinematics.

## Setup and conventions

We use the qft.org $S$-matrix convention

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The momenta are on shell:

$$
p_i^2=m_i^2,
\qquad
p_i^0>0.
$$

The Mandelstam variables are

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2.
$$

They satisfy

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

The bar in $\overline{|\mathcal M|^2}$ means: sum over unresolved final spins, polarizations, colors, or flavors, and average over unresolved initial ones. It does not include the flux factor.

If the final state contains identical particles, include the final-state counting factor separately when integrating over a region that counts both labelings.

## Center-of-momentum kinematics

In the center-of-momentum frame,

$$
p_1^\mu=(E_1^*,0,0,|\mathbf p_i^*|),
\qquad
p_2^\mu=(E_2^*,0,0,-|\mathbf p_i^*|),
$$

and we may choose

$$
p_3^\mu=(E_3^*,|\mathbf p_f^*|\sin\theta\cos\phi,
|\mathbf p_f^*|\sin\theta\sin\phi,
|\mathbf p_f^*|\cos\theta),
$$

$$
p_4^\mu=(E_4^*,-|\mathbf p_f^*|\sin\theta\cos\phi,
-|\mathbf p_f^*|\sin\theta\sin\phi,
-|\mathbf p_f^*|\cos\theta).
$$

The energies are

$$
E_1^*=
\frac{s+m_1^2-m_2^2}{2\sqrt{s}},
\qquad
E_2^*=
\frac{s+m_2^2-m_1^2}{2\sqrt{s}},
$$

and

$$
E_3^*=
\frac{s+m_3^2-m_4^2}{2\sqrt{s}},
\qquad
E_4^*=
\frac{s+m_4^2-m_3^2}{2\sqrt{s}}.
$$

The momentum magnitudes are

$$
|\mathbf p_i^*|=
\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}},
\qquad
|\mathbf p_f^*|=
\frac{\sqrt{\lambda(s,m_3^2,m_4^2)}}{2\sqrt{s}}.
$$

The physical region requires

$$
\sqrt{s}\ge m_1+m_2,
\qquad
\sqrt{s}\ge m_3+m_4.
$$

The first condition says the incoming two-particle state can exist at that $s$. The second says the final two-particle state is kinematically open.

## Deriving dσ over dΩ

The invariant scattering formula is

$$
 d\sigma
=
\frac{1}{F_{12}}\overline{|\mathcal M|^2}d\Pi_2.
$$

For two incoming particles, the center-of-momentum flux denominator is

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s}.
$$

For the two-body final state,

$$
 d\Pi_2
=
\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega.
$$

Therefore

$$
\begin{aligned}
 d\sigma
&=
\frac{1}{4|\mathbf p_i^*|\sqrt{s}}
\overline{|\mathcal M|^2}
\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega \\
&=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}d\Omega.
\end{aligned}
$$

Thus

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

For elastic scattering with the same masses in the initial and final states,

$$
|\mathbf p_f^*|=|\mathbf p_i^*|,
$$

so

$$
\frac{d\sigma}{d\Omega}
=
\frac{\overline{|\mathcal M|^2}}{64\pi^2s}
$$

in the center-of-momentum frame.

## Relation between angle and t

With the momentum assignment above,

$$
t=(p_1-p_3)^2
=m_1^2+m_3^2-2p_1\cdot p_3.
$$

In the center-of-momentum frame,

$$
p_1\cdot p_3
=E_1^*E_3^*-|\mathbf p_i^*||\mathbf p_f^*|\cos\theta.
$$

Therefore

$$
t
=m_1^2+m_3^2-2E_1^*E_3^*
+2|\mathbf p_i^*||\mathbf p_f^*|\cos\theta.
$$

The derivative is

$$
\frac{dt}{d\cos\theta}=2|\mathbf p_i^*||\mathbf p_f^*|.
$$

The physical endpoints are

$$
t_\pm
=m_1^2+m_3^2-2E_1^*E_3^*
\pm2|\mathbf p_i^*||\mathbf p_f^*|.
$$

Here $t_+$ corresponds to forward scattering, $\cos\theta=+1$, and $t_-$ corresponds to backward scattering, $\cos\theta=-1$, with the momentum assignment used above.

## Deriving dσ over dt

For unpolarized scattering, or for a scalar process, rotational symmetry around the beam axis usually removes any dependence on $\phi$. Then

$$
d\Omega=d\phi\,d\cos\theta
\quad\longrightarrow\quad
2\pi\,d\cos\theta.
$$

Using

$$
dt=2|\mathbf p_i^*||\mathbf p_f^*|\,d\cos\theta,
$$

we get

$$
\frac{d\Omega}{dt}
=
\frac{2\pi}{2|\mathbf p_i^*||\mathbf p_f^*|}
=
\frac{\pi}{|\mathbf p_i^*||\mathbf p_f^*|}.
$$

Therefore

$$
\begin{aligned}
\frac{d\sigma}{dt}
&=
\frac{d\sigma}{d\Omega}\frac{d\Omega}{dt} \\
&=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}
\frac{\pi}{|\mathbf p_i^*||\mathbf p_f^*|} \\
&=
\frac{1}{64\pi s|\mathbf p_i^*|^2}
\overline{|\mathcal M|^2}.
\end{aligned}
$$

Since

$$
|\mathbf p_i^*|^2
=
\frac{\lambda(s,m_1^2,m_2^2)}{4s},
$$

this is also

$$
\frac{d\sigma}{dt}
=
\frac{1}{16\pi\lambda(s,m_1^2,m_2^2)}
\overline{|\mathcal M(s,t)|^2}.
$$

For massless incoming particles, $\lambda(s,0,0)=s^2$, so

$$
\frac{d\sigma}{dt}
=
\frac{\overline{|\mathcal M(s,t)|^2}}{16\pi s^2}.
$$

The $d\sigma/dt$ formula is especially useful when amplitudes are naturally expressed in Mandelstam variables, as in exchange diagrams with denominators such as $1/(t-m^2)$.

## Total cross section

The total cross section is obtained by integrating over the physical angular domain:

$$
\sigma
=
\int d\Omega\,
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M(s,\theta,\phi)|^2}.
$$

For an unpolarized process with no $\phi$ dependence,

$$
\sigma
=
\int_{t_-}^{t_+}dt\,
\frac{1}{16\pi\lambda(s,m_1^2,m_2^2)}
\overline{|\mathcal M(s,t)|^2}.
$$

If $\overline{|\mathcal M|^2}$ is constant and the final particles are distinguishable, the angular integral gives

$$
\sigma
=
\frac{1}{16\pi s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

For elastic massless scattering with constant $\overline{|\mathcal M|^2}$,

$$
\sigma=
\frac{\overline{|\mathcal M|^2}}{16\pi s}.
$$

If the final particles are identical and the integral covers the full labeled sphere, multiply by $1/2!$.

## Practical workflow

A reliable $2\to2$ calculation usually goes in this order.

1. **Compute the stripped amplitude.** Use the momentum-space Feynman rules to compute $\mathcal M$, with the overall $(2\pi)^4\delta^{(4)}(P_f-P_i)$ removed.
2. **Put external states on shell.** Enforce $p_i^2=m_i^2$ and use physical external spinors or polarization vectors.
3. **Sum and average unresolved quantum numbers.** Build $\overline{|\mathcal M|^2}$ with the spin, polarization, color, and flavor sums appropriate to the observable.
4. **Choose kinematic variables.** Use $d\Omega$ for angular distributions and $dt$ when the amplitude is naturally written in terms of $s$ and $t$.
5. **Insert phase space and flux.** Use the master formulas above.
6. **Apply final-state counting and cuts.** Include identical-particle factors, angular restrictions, thresholds, or detector-level cuts only at the phase-space integration stage.

This ordering avoids a common bookkeeping trap: do not put spin averages, identical-particle factors, or flux denominators into the amplitude itself.

## Minimal example: constant scalar amplitude

Consider a toy process of distinguishable scalar particles with a constant tree-level amplitude

$$
\mathcal M=-g.
$$

Then

$$
\overline{|\mathcal M|^2}=g^2.
$$

For massless $2\to2$ scattering, $|\mathbf p_f^*|=|\mathbf p_i^*|$ and

$$
\frac{d\sigma}{d\Omega}
=
\frac{g^2}{64\pi^2s}.
$$

Integrating over the full sphere gives

$$
\sigma=\frac{g^2}{16\pi s}
$$

for distinguishable final particles.

For identical final particles integrated over the full labeled sphere, divide by $2!$:

$$
\sigma_{\mathrm{identical\ final}}
=\frac{g^2}{32\pi s}.
$$

This example is deliberately boring. Its job is to make the normalization unmistakable. In real calculations, the angular dependence usually comes from propagator denominators, spinor traces, polarization sums, and color factors.

## Mass dimensions

In four spacetime dimensions, a cross section has mass dimension

$$
[\sigma]=-2.
$$

For a renormalizable $2\to2$ process, $\mathcal M$ is often dimensionless at tree level. The factor $1/s$ in

$$
\frac{d\sigma}{d\Omega}
\sim
\frac{|\mathcal M|^2}{s}
$$

then supplies the correct dimension. If the amplitude contains higher-dimensional EFT interactions, $\mathcal M$ carries powers of energy over the cutoff scale. The same phase-space and flux formulas still apply; the energy growth is dynamical, not kinematic.

## Identical particles and angular domains

Identical particles require two separate pieces of care.

First, the amplitude must include all exchange-related diagrams with the correct signs before squaring. For identical bosons, exchange-related contributions add; for identical fermions, relative minus signs can appear.

Second, the final-state phase-space integral must not count the same physical final state twice. There are two equivalent strategies:

| Strategy | What to do |
|---|---|
| full labeled angular domain | include a final-state factor $1/2!$ |
| reduced physical angular domain | integrate only one representative of each exchanged pair |

Do not do both. That would undercount by a factor of two.

Identical incoming particles are different. A cross section is normalized by a prepared incident flux, so there is usually no $1/2!$ factor in the elementary $2\to2$ cross-section formula for identical initial particles.

## Common pitfalls

**Dropping the ratio $|\mathbf p_f^*|/|\mathbf p_i^*|$.** This ratio is one for elastic equal-mass scattering, but not for general reactions. It is the combined effect of final two-body phase space and initial flux.

**Using $d\sigma/dt=|\mathcal M|^2/(16\pi s^2)$ with massive initial particles.** The denominator $16\pi s^2$ assumes $m_1=m_2=0$. The massive formula uses $16\pi\lambda(s,m_1^2,m_2^2)$.

**Including the momentum-conserving delta function in $\mathcal M$.** The amplitude in these formulas is the stripped invariant amplitude. The overall $(2\pi)^4\delta^{(4)}(P_f-P_i)$ belongs to the $S$-matrix element, not to $\mathcal M$.

**Averaging spins or colors twice.** Average initial unresolved quantum numbers once in $\overline{|\mathcal M|^2}$. Do not also divide the cross-section formula by those degeneracies.

**Forgetting final-state identical-particle factors.** Exchange diagrams belong in the amplitude. Phase-space overcounting is a separate final-state integration issue.

**Treating tree-level $2\to2$ formulas as detector predictions.** Real collider observables include finite widths, radiative corrections, soft and collinear radiation, PDFs, cuts, efficiencies, and detector response. The ideal $2\to2$ formula is the hard partonic starting point, not the whole experimental prediction.

## Relations to other pages

- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) derives the final-state measure used in this page.
- [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) derives the incoming denominator $F_{12}=4|\mathbf p_i^*|\sqrt{s}$.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) develops the invariant variables $s$, $t$, and $u$ and their physical regions.
- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives simple amplitudes that can be inserted into the formulas here.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explain how spin sums produce $\overline{|\mathcal M|^2}$ for realistic processes.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains exchange amplitudes and phase-space counting for identical final states.

## Research status

The formulas on this page are textbook-standard for stable asymptotic particles in infinite-volume relativistic QFT. They are exact kinematic consequences of the stated $S$-matrix normalization, invariant flux, and two-body phase space.

The main active issues arise in realistic applications rather than in the formula itself. Precision predictions require loop corrections, renormalization schemes, infrared-safe observables, real-emission phase space, finite-width effects, parton distributions, resummation, event generators, and detector definitions. Those refinements keep the same hard-scattering normalization but embed it in a larger observable calculation.

## Exercises

### Exercise 1: Derive the center-of-momentum master formula

Starting from

$$
 d\sigma
=\frac{1}{F_{12}}\overline{|\mathcal M|^2}d\Pi_2,
$$

with

$$
F_{12}=4|\mathbf p_i^*|\sqrt{s},
\qquad
 d\Pi_2=\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega,
$$

derive

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the flux and phase-space factors:

$$
 d\sigma
=
\frac{1}{4|\mathbf p_i^*|\sqrt{s}}
\overline{|\mathcal M|^2}
\frac{|\mathbf p_f^*|}{16\pi^2\sqrt{s}}d\Omega.
$$

Multiplying denominators gives

$$
4\times16\pi^2\times s=64\pi^2s.
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

### Exercise 2: Derive the dσ over dt formula

Assume the unpolarized squared amplitude has no $\phi$ dependence. Use

$$
\frac{dt}{d\cos\theta}=2|\mathbf p_i^*||\mathbf p_f^*|
$$

to derive

$$
\frac{d\sigma}{dt}
=
\frac{1}{16\pi\lambda(s,m_1^2,m_2^2)}
\overline{|\mathcal M|^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

With no $\phi$ dependence,

$$
d\Omega=2\pi\,d\cos\theta.
$$

The relation between $t$ and $\cos\theta$ gives

$$
\frac{d\Omega}{dt}
=
\frac{2\pi}{2|\mathbf p_i^*||\mathbf p_f^*|}
=
\frac{\pi}{|\mathbf p_i^*||\mathbf p_f^*|}.
$$

Therefore

$$
\frac{d\sigma}{dt}
=
\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}
\frac{\pi}{|\mathbf p_i^*||\mathbf p_f^*|}
=
\frac{1}{64\pi s|\mathbf p_i^*|^2}
\overline{|\mathcal M|^2}.
$$

Since

$$
|\mathbf p_i^*|^2=\frac{\lambda(s,m_1^2,m_2^2)}{4s},
$$

we find

$$
\frac{d\sigma}{dt}
=
\frac{1}{16\pi\lambda(s,m_1^2,m_2^2)}
\overline{|\mathcal M|^2}.
$$

</details>

### Exercise 3: Physical t range

Show that the physical range of $t$ is

$$
t_-\le t\le t_+,
$$

where

$$
t_\pm=m_1^2+m_3^2-2E_1^*E_3^*
\pm2|\mathbf p_i^*||\mathbf p_f^*|.
$$

<details>
<summary><strong>Solution</strong></summary>

In the center-of-momentum frame,

$$
t=m_1^2+m_3^2-2E_1^*E_3^*
+2|\mathbf p_i^*||\mathbf p_f^*|\cos\theta.
$$

The only angular restriction for two-body kinematics is

$$
-1\le\cos\theta\le1.
$$

Substituting $\cos\theta=+1$ gives

$$
t_+=m_1^2+m_3^2-2E_1^*E_3^*
+2|\mathbf p_i^*||\mathbf p_f^*|,
$$

and substituting $\cos\theta=-1$ gives

$$
t_-=m_1^2+m_3^2-2E_1^*E_3^*
-2|\mathbf p_i^*||\mathbf p_f^*|.
$$

</details>

### Exercise 4: Constant massless scalar amplitude

For massless distinguishable scalar scattering with constant amplitude $\mathcal M=-g$, compute $d\sigma/d\Omega$ and $\sigma$.

<details>
<summary><strong>Solution</strong></summary>

For massless elastic scattering,

$$
|\mathbf p_f^*|=|\mathbf p_i^*|.
$$

The master formula gives

$$
\frac{d\sigma}{d\Omega}
=
\frac{|\mathcal M|^2}{64\pi^2s}
=
\frac{g^2}{64\pi^2s}.
$$

For distinguishable final particles, integrate over the full sphere:

$$
\sigma
=\frac{g^2}{64\pi^2s}\int d\Omega
=\frac{g^2}{64\pi^2s}(4\pi)
=\frac{g^2}{16\pi s}.
$$

</details>

### Exercise 5: Identical final particles

Repeat Exercise 4 when the two final particles are identical and the integral is taken over the full labeled solid angle.

<details>
<summary><strong>Solution</strong></summary>

The full labeled angular integral counts the same physical final state twice. Therefore multiply the result of Exercise 4 by $1/2!$:

$$
\sigma_{\mathrm{identical\ final}}
=\frac{1}{2}\frac{g^2}{16\pi s}
=\frac{g^2}{32\pi s}.
$$

Equivalently, one could integrate over only one representative angular region and omit the explicit $1/2!$ factor.

</details>

### Exercise 6: Dimension check

Assume a four-dimensional renormalizable interaction gives a dimensionless tree-level amplitude. Check that $d\sigma/d\Omega$ has the correct mass dimension.

<details>
<summary><strong>Solution</strong></summary>

In natural units, a cross section has dimension $-2$. The solid angle is dimensionless, so $d\sigma/d\Omega$ also has dimension $-2$.

For a dimensionless tree-level amplitude,

$$
[\overline{|\mathcal M|^2}]=0.
$$

The ratio $|\mathbf p_f^*|/|\mathbf p_i^*|$ is dimensionless, and

$$
[s]=2.
$$

Therefore

$$
\left[\frac{1}{64\pi^2s}
\frac{|\mathbf p_f^*|}{|\mathbf p_i^*|}
\overline{|\mathcal M|^2}\right]
=-2,
$$

as required.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§10–11, for amplitudes, Feynman rules, phase space, cross sections, and decay rates.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering-theory normalization, rates, cross sections, and phase space.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 11–12, for Mandelstam variables, phase space, differential cross sections, decays, and the optical theorem.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 13, for practical cross-section calculations and QED examples.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for standard $2\to2$ scattering examples in perturbative QFT.

## Version history

- **2026-06-12:** Initial polished draft for qft.org. Derives the $2\to2$ formulas for $d\sigma/d\Omega$ and $d\sigma/dt$, fixes the center-of-momentum kinematics, records the physical $t$ range, and gives a constant-amplitude normalization check.
