---
title: "Lorentz-Invariant Phase Space"
description: "A derivation and convention-safe guide to the Lorentz-invariant final-state phase-space measure used in decay rates and scattering cross sections."
sidebar:
  label: "Lorentz-Invariant Phase Space"
  order: 1
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, ch. 3; Srednicki 2007, §§10–11; Coleman 2019, chs. 11–12; Schwartz 2014, ch. 5"
topics:
  - Lorentz-invariant phase space
  - scattering kinematics
  - decay rates
  - cross sections
  - relativistic normalization
canonicalTopics:
  - lorentz-invariant-phase-space
  - final-state-density-of-states
  - two-body-phase-space
  - phase-space-factorization
researchStatus:
  established:
    - "The invariant phase-space measure follows directly from relativistic state normalization and is standard in S-matrix calculations with stable asymptotic particles."
  active:
    - "Finite-volume spectra, unstable particles, infrared-safe inclusive observables, jet measurements, and real-time media require refinements of the simple stable-particle phase-space formulas collected here."
---

## Summary

**Lorentz-invariant phase space** is the kinematic measure that sums over possible final on-shell momenta in scattering and decay problems. It is where the density of final states enters QFT observables.

For $n$ stable final particles with total four-momentum $P$, qft.org uses

$$
 d\Pi_n(P)
=(2\pi)^4\delta^{(4)}
\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n
\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

The measure is Lorentz invariant because each one-particle factor can be written as

$$
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=\frac{d^4p}{(2\pi)^3}\,\theta(p^0)\delta(p^2-m^2).
$$

This page derives the measure, explains how it is used, records the two-body formula, and isolates the bookkeeping issues that usually cause wrong factors of $2\pi$, $2E$, or $1/n!$.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![The invariant final-state phase-space measure is built from positive-energy mass-shell measures and the total momentum-conserving delta function](/figures/perturbative-qft/lorentz-invariant-phase-space.svg)

<figcaption>

The one-particle on-shell measure may be written either as a covariant $d^4p$ measure with $\theta(p^0)\delta(p^2-m^2)$ or as $d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$. Multiplying one such factor for each final particle and imposing total momentum conservation gives $d\Pi_n(P)$, the kinematic measure used in decay rates and cross sections.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/).

## Core idea

The amplitude $\mathcal M$ contains dynamics. Phase space contains the allowed final kinematics.

A schematic decay or scattering probability has the form

$$
\text{observable}
\sim
\text{initial normalization}^{-1}
\times
|\mathcal M|^2
\times
\text{final-state phase space}.
$$

The final-state phase space is not an optional convention. It is the continuum version of inserting a complete set of final multiparticle states. With qft.org's relativistic normalization,

$$
\langle \mathbf p',s'|\mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'},
$$

the one-particle completeness relation is

$$
\mathbf 1_{1\text{-particle}}
=
\sum_s\int
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
|\mathbf p,s\rangle\langle \mathbf p,s|.
$$

That single factor $d^3\mathbf p/[(2\pi)^3 2E_{\mathbf p}]$ is the seed of all Lorentz-invariant phase-space formulas.

## Setup and conventions

We use the qft.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
p^2=(p^0)^2-\mathbf p^2.
$$

A stable on-shell final particle has

$$
p^2=m^2,
\qquad
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}>0.
$$

The S-matrix convention is

$$
S_{fi}=\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

The amplitude $\mathcal M$ is defined with the overall momentum-conserving delta function stripped off. The phase-space measure keeps one overall delta function to enforce conservation of the total final momentum.

Some books write the same measure as $d\Phi_n$ rather than $d\Pi_n$. On qft.org, $d\Pi_n$ denotes Lorentz-invariant final-state phase space.

## The one-particle on-shell measure

The covariant form of the one-particle measure is

$$
d\Pi_p
\equiv
\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
=
\frac{d^4p}{(2\pi)^3}\,\theta(p^0)\delta(p^2-m^2).
$$

Here $\theta(p^0)$ selects the positive-energy mass shell. To check the equality, use

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2,
$$

so

$$
\delta(p^2-m^2)
=
\frac{1}{2E_{\mathbf p}}
\left[
\delta(p^0-E_{\mathbf p})+
\delta(p^0+E_{\mathbf p})
\right].
$$

Multiplying by $\theta(p^0)$ keeps only $p^0=E_{\mathbf p}$, giving

$$
\int d^4p\,\theta(p^0)\delta(p^2-m^2)F(p)
=
\int\frac{d^3\mathbf p}{2E_{\mathbf p}}
F(E_{\mathbf p},\mathbf p).
$$

This formula also explains why the measure is Lorentz invariant. The measure $d^4p$ is invariant, $p^2-m^2$ is invariant, and the positive-energy branch is preserved by proper orthochronous Lorentz transformations.

## The n-body phase-space measure

For total final momentum $P$, the $n$-body phase space is

$$
 d\Pi_n(P;p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}
\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n d\Pi_{p_a}.
$$

Written out,

$$
 d\Pi_n(P)
=(2\pi)^4\delta^{(4)}
\!\left(P-\sum_{a=1}^n p_a\right)
\prod_{a=1}^n
\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}.
$$

The total momentum $P$ is normally

$$
P=p_A
$$

for a decay $A\to1+\cdots+n$, and

$$
P=p_1+p_2
$$

for a scattering process $1+2\to X$.

The measure vanishes unless $P$ lies in a physical region. For a decay in the rest frame of $P$, this means

$$
\sqrt{P^2}\ge \sum_{a=1}^n m_a.
$$

The equality case is threshold: all final particles are at rest relative to each other in the center-of-mass frame.

## From completeness to phase space

The phase-space measure is just the complete set of final states written in momentum variables.

For one final particle, completeness gives

$$
\sum_s\int d\Pi_p\,|\mathbf p,s\rangle\langle \mathbf p,s|.
$$

For $n$ final particles, we insert one such factor for each particle. Translational invariance of the S-matrix gives the overall delta function

$$
(2\pi)^4\delta^{(4)}(P-\sum_a p_a).
$$

After squaring the S-matrix element, one of the squared delta functions becomes a spacetime volume factor that is interpreted as the total observation time times spatial volume. The remaining finite differential measure is precisely $d\Pi_n(P)$, with the appropriate initial normalization handled separately by decay-rate or cross-section formulas.

This is the clean way to remember what phase space is: it is not guessed by dimensional analysis. It is the Lorentz-invariant continuum resolution of final states.

## Identical final particles

The expression $d\Pi_n(P;p_1,\ldots,p_n)$ treats the final momenta as labeled integration variables. If the final state contains identical particles, the physical phase-space integral must not count label permutations as distinct states.

If the final state contains $n_a$ identical particles of species $a$, use

$$
 d\Pi_n^{\rm physical}
=
\frac{1}{\prod_a n_a!}
 d\Pi_n^{\rm labeled}.
$$

For example, a decay into two identical scalars has

$$
 d\Gamma
=\frac{1}{2M}|\mathcal M|^2\frac{1}{2!}d\Pi_2.
$$

This factorial is a final-state counting factor, not an amplitude factor. Exchange-related amplitudes must still be added or subtracted before squaring, as explained in [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/).

## Decays and scattering

For a one-particle decay

$$
A(P)\to1+\cdots+n,
$$

the differential decay rate is

$$
 d\Gamma
=\frac{1}{2M_A}\,
\overline{|\mathcal M|^2}\,d\Pi_n(P),
$$

where $P^2=M_A^2$. The bar denotes whatever spin or polarization average is appropriate for the physical lifetime. If the initial particle is prepared in a definite spin state, do not average over it.

For two-particle scattering,

$$
1(p_1)+2(p_2)\to X,
$$

the differential cross section is

$$
 d\sigma
=\frac{1}{F_{12}}
\overline{|\mathcal M|^2}
\,d\Pi_X(P),
\qquad
P=p_1+p_2,
$$

with the invariant flux denominator

$$
F_{12}
=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}.
$$

The flux factor is developed in [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/). This page focuses on $d\Pi_X$.

## Two-body phase space

The most important explicit example is two-body phase space. Let

$$
P^2=s,
\qquad
P=(\sqrt{s},\mathbf 0)
$$

in the center-of-mass frame, and consider

$$
P\to p_1+p_2,
\qquad
p_i^2=m_i^2.
$$

The two final particles have equal and opposite three-momenta,

$$
\mathbf p_1=\mathbf p_* ,
\qquad
\mathbf p_2=-\mathbf p_*.
$$

The magnitude is

$$
|\mathbf p_*|
=
\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{2\sqrt{s}},
$$

where the Källén function is

$$
\lambda(x,y,z)=x^2+y^2+z^2-2xy-2xz-2yz.
$$

The two-body measure becomes

$$
 d\Pi_2(P;p_1,p_2)
=
\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}\,d\Omega
=
\frac{\sqrt{\lambda(s,m_1^2,m_2^2)}}{32\pi^2 s}\,d\Omega.
$$

For massless final particles, $m_1=m_2=0$, this reduces to

$$
 d\Pi_2=\frac{1}{32\pi^2}\,d\Omega,
\qquad
\int d\Pi_2=\frac{1}{8\pi}.
$$

For equal final masses $m$, the momentum is

$$
|\mathbf p_*|=\frac{\sqrt{s}}{2}\sqrt{1-\frac{4m^2}{s}},
$$

so the integrated two-body phase space is

$$
\int d\Pi_2
=\frac{|\mathbf p_*|}{4\pi\sqrt{s}}
=\frac{1}{8\pi}\sqrt{1-\frac{4m^2}{s}}.
$$

The square-root threshold factor is purely kinematic. Dynamics enters through $|\mathcal M|^2$.

## Derivation of the two-body formula

Start from

$$
 d\Pi_2
=(2\pi)^4\delta^{(4)}(P-p_1-p_2)
\frac{d^3\mathbf p_1}{(2\pi)^3 2E_1}
\frac{d^3\mathbf p_2}{(2\pi)^3 2E_2}.
$$

In the center-of-mass frame $P=(\sqrt{s},\mathbf 0)$, the spatial delta function sets

$$
\mathbf p_2=-\mathbf p_1.
$$

Writing $p=|\mathbf p_1|$, we get

$$
 d\Pi_2
=\frac{1}{16\pi^2}
\frac{p^2\,dp\,d\Omega}{E_1E_2}
\delta(\sqrt{s}-E_1(p)-E_2(p)).
$$

The delta function fixes $p=|\mathbf p_*|$. Since

$$
\frac{d}{dp}\big(E_1+E_2\big)
=
\frac{p}{E_1}+\frac{p}{E_2}
=
\frac{p(E_1+E_2)}{E_1E_2}
=
\frac{p\sqrt{s}}{E_1E_2},
$$

the $p$ integral gives

$$
 d\Pi_2
=\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}\,d\Omega.
$$

The expression for $|\mathbf p_*|$ follows from solving the two-body energy equations or, equivalently, from the invariant identity

$$
\lambda(s,m_1^2,m_2^2)
=
4s|\mathbf p_*|^2.
$$

## Recursive factorization

Higher-body phase space can be built recursively. If $q$ is the total momentum carried by a subset of final particles, then

$$
 d\Pi_n(P;p_1,\ldots,p_n)
=
\frac{dq^2}{2\pi}\,
 d\Pi_2(P;q,p_n)\,
 d\Pi_{n-1}(q;p_1,\ldots,p_{n-1}).
$$

This formula is especially useful for three-body decays, cascade decays, and numerical phase-space generation.

For $n=3$, one convenient choice is

$$
q=p_1+p_2,
$$

so

$$
 d\Pi_3(P;p_1,p_2,p_3)
=
\frac{dq^2}{2\pi}
 d\Pi_2(P;q,p_3)
 d\Pi_2(q;p_1,p_2).
$$

The variable $q^2$ is an invariant mass squared. Its allowed range is fixed by the two nested thresholds:

$$
(m_1+m_2)^2\le q^2\le (\sqrt{P^2}-m_3)^2.
$$

This is the first glimpse of Dalitz-plot kinematics.

## Mass dimension

The one-particle measure has mass dimension two:

$$
\left[\frac{d^3\mathbf p}{2E_{\mathbf p}}\right]=2.
$$

The four-dimensional delta function has dimension $-4$. Therefore

$$
[d\Pi_n]=2n-4.
$$

For two-body phase space, $[d\Pi_2]=0$, consistent with

$$
 d\Pi_2
=\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}d\Omega.
$$

For three-body phase space, $[d\Pi_3]=2$, consistent with the extra invariant-mass integral $dq^2$ in the recursive factorization formula.

## Common pitfalls

**Forgetting the positive-energy condition.** The covariant measure uses $\theta(p^0)\delta(p^2-m^2)$, not merely $\delta(p^2-m^2)$. Without $\theta(p^0)$, both energy sheets are counted.

**Dropping factors of $2\pi$.** The convention

$$
 d\Pi_n=(2\pi)^4\delta^{(4)}(P-\sum p_a)\prod_a\frac{d^3\mathbf p_a}{(2\pi)^3 2E_a}
$$

is tied to the S-matrix convention with $(2\pi)^4\delta^{(4)}\mathcal M$. Changing one convention changes the other.

**Confusing phase space with dynamics.** The threshold factor in $d\Pi_2$ is kinematic. Resonances, spin correlations, angular dependence, and selection rules live in $\mathcal M$.

**Counting identical particles twice.** The labeled measure overcounts identical final particles. Divide by $\prod_a n_a!$ after constructing the physical amplitude.

**Using the two-body formula outside its frame.** The formula $d\Pi_2=|\mathbf p_*|d\Omega/(16\pi^2\sqrt{s})$ is written in the center-of-mass frame of $P$. The measure is invariant, but $d\Omega$ and $|\mathbf p_*|$ are frame-specific coordinates on it.

**Forgetting massless boundary singularities.** The measure itself is finite for a fixed number of massless particles in many simple kinematic regions, but matrix elements can develop soft or collinear singularities on phase-space boundaries. Infrared-safe observables require inclusive definitions.

## Relations to other pages

- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains why the one-particle measure contains $2E_{\mathbf p}$.
- [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/) combines $d\Pi_n$ with the incoming two-particle normalization to produce cross sections.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) supplies the invariant kinematics used in two-body scattering.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains exchange interference and final-state factorials.
- [Optical Theorem Preview](/perturbative-qft/from-correlators-to-s-matrix/optical-theorem-preview/) relates phase-space sums over intermediate states to unitarity.

## Research status

The formulas on this page are textbook-standard for stable asymptotic particles in infinite-volume relativistic QFT.

There are several important extensions. In finite volume, phase space is replaced by a discrete spectrum and must be connected to infinite-volume scattering through finite-volume formalism. For unstable particles, one often integrates over an invariant-mass distribution, leading to Breit–Wigner and narrow-width approximations. For massless gauge theories, physically measurable quantities require inclusive sums over unresolved soft and collinear radiation. In media, the Lorentz-invariant vacuum phase-space measure is replaced or supplemented by thermal distribution functions, spectral densities, and response functions.

## Exercises

### Exercise 1: Positive-energy mass shell

Show that

$$
\frac{d^3\mathbf p}{2E_{\mathbf p}}
=
d^4p\,\theta(p^0)\delta(p^2-m^2)
$$

as measures acting on smooth test functions.

<details>
<summary><strong>Solution</strong></summary>

Let $E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}$. Then

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2.
$$

Using

$$
\delta(f(x))=\sum_i\frac{\delta(x-x_i)}{|f'(x_i)|},
$$

we find

$$
\delta((p^0)^2-E_{\mathbf p}^2)
=
\frac{1}{2E_{\mathbf p}}
\left[
\delta(p^0-E_{\mathbf p})+
\delta(p^0+E_{\mathbf p})
\right].
$$

Multiplication by $\theta(p^0)$ keeps only $p^0=E_{\mathbf p}$. Therefore

$$
\int d^4p\,\theta(p^0)\delta(p^2-m^2)F(p)
=
\int\frac{d^3\mathbf p}{2E_{\mathbf p}}
F(E_{\mathbf p},\mathbf p).
$$

</details>

### Exercise 2: Two-body phase space

Starting from the definition of $d\Pi_2$, derive

$$
 d\Pi_2
=\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}d\Omega.
$$

<details>
<summary><strong>Solution</strong></summary>

In the center-of-mass frame, $P=(\sqrt{s},\mathbf 0)$, so the spatial delta function sets $\mathbf p_2=-\mathbf p_1$. Write $p=|\mathbf p_1|$. Then

$$
 d\Pi_2
=\frac{1}{16\pi^2}
\frac{p^2dp\,d\Omega}{E_1E_2}
\delta(\sqrt{s}-E_1(p)-E_2(p)).
$$

The derivative of the delta-function argument is

$$
\frac{d}{dp}(E_1+E_2)
=\frac{p\sqrt{s}}{E_1E_2}
$$

at the solution $p=|\mathbf p_*|$. Thus

$$
 d\Pi_2
=\frac{1}{16\pi^2}
\frac{|\mathbf p_*|^2d\Omega}{E_1E_2}
\frac{E_1E_2}{|\mathbf p_*|\sqrt{s}}
=\frac{|\mathbf p_*|}{16\pi^2\sqrt{s}}d\Omega.
$$

</details>

### Exercise 3: Integrated massless two-body phase space

For $m_1=m_2=0$, show that

$$
\int d\Pi_2=\frac{1}{8\pi}.
$$

<details>
<summary><strong>Solution</strong></summary>

For massless final particles,

$$
|\mathbf p_*|=\frac{\sqrt{s}}{2}.
$$

Hence

$$
 d\Pi_2
=\frac{1}{32\pi^2}d\Omega.
$$

Integrating over the full solid angle gives

$$
\int d\Pi_2
=\frac{1}{32\pi^2}\int d\Omega
=\frac{1}{32\pi^2}(4\pi)
=\frac{1}{8\pi}.
$$

</details>

### Exercise 4: Dimension of n-body phase space

Show that $[d\Pi_n]=2n-4$ in four spacetime dimensions.

<details>
<summary><strong>Solution</strong></summary>

Each one-particle measure contributes

$$
\left[\frac{d^3\mathbf p}{2E}\right]=3-1=2.
$$

There are $n$ such factors, contributing $2n$. The four-dimensional delta function has dimension $-4$. Factors of $2\pi$ are dimensionless. Therefore

$$
[d\Pi_n]=2n-4.
$$

</details>

### Exercise 5: Recursive three-body phase space

Use the factorization formula to show that for $P\to1+2+3$ with $q=p_1+p_2$,

$$
 d\Pi_3(P;p_1,p_2,p_3)
=
\frac{dq^2}{2\pi}
 d\Pi_2(P;q,p_3)
 d\Pi_2(q;p_1,p_2).
$$

What is the allowed range of $q^2$?

<details>
<summary><strong>Solution</strong></summary>

Insert

$$
1=\int d^4q\,\delta^{(4)}(q-p_1-p_2)
$$

into $d\Pi_3$. The factors involving $p_1,p_2$ combine into $d\Pi_2(q;p_1,p_2)$. The remaining $q$ integration may be decomposed as

$$
\frac{d^4q}{(2\pi)^4}
=\frac{dq^2}{2\pi}
\frac{d^3\mathbf q}{(2\pi)^3 2E_q},
$$

where $E_q=\sqrt{\mathbf q^2+M_q^2}$ with $M_q^2=q^2$ for the intermediate composite momentum. The factors involving $q$ and $p_3$ combine into $d\Pi_2(P;q,p_3)$, giving the stated formula.

The invariant mass $q^2$ must be large enough to produce particles $1$ and $2$, but small enough that $P$ can produce the composite object $q$ together with particle $3$:

$$
(m_1+m_2)^2\le q^2\le(\sqrt{P^2}-m_3)^2.
$$

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for S-matrix normalization, rates, cross sections, and Lorentz-invariant phase space.
- M. Srednicki, *Quantum Field Theory*, §§10–11, for scattering amplitudes, Feynman rules, cross sections, and decay rates.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 11–12, for Mandelstam variables, phase space, cross sections, decays, and the optical theorem.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 5, for a calculation-oriented treatment of cross sections and decay rates.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for standard phase-space and cross-section conventions in perturbative calculations.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume.
