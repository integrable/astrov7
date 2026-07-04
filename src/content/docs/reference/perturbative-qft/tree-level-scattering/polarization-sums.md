---
title: "Polarization Sums"
description: "A practical guide to summing and averaging external spin and polarization states in tree-level scattering, with massive-vector projectors, massless gauge-boson projectors, Ward-identity simplifications, and spinor trace checks."
sidebar:
  label: "Polarization Sums"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§46, 50, 56, 59–60, and 72; Weinberg 1995, Vol. I, chs. 2, 5, 6, and 8; Schwartz 2014, chs. 8, 13, 26, and 27"
topics:
  - polarization sums
  - spin sums
  - gauge invariance
  - vector bosons
  - Ward identities
  - squared amplitudes
canonicalTopics:
  - polarization-sums
  - massive-vector-polarization-projector
  - massless-gauge-boson-polarization-sum
  - spin-summed-amplitudes
  - ward-identity-simplifications
researchStatus:
  established:
    - "The polarization projectors, spin sums, and gauge-invariance simplifications used for tree-level squared amplitudes are standard textbook consequences of relativistic one-particle state normalization and gauge redundancy."
  active:
    - "Precision calculations require infrared-safe measurement functions, loop corrections, helicity methods, gauge-invariant subtraction schemes, and automated polarization handling; those developments belong to later pages."
---

## Summary

A scattering amplitude is usually computed for fixed external spins, helicities, colors, and polarizations. A cross section or decay rate usually asks a different question: what is the probability when an experiment does not resolve some of those quantum numbers?

The answer is to sum over unresolved final states and average over unresolved initial states. For spin and polarization labels,

$$
\overline{|\mathcal M|^2}
=
\frac{1}{N_{\rm initial}}
\sum_{\rm unresolved\ spins,\ polarizations,\ colors}
|\mathcal M|^2.
$$

The most useful tree-level projectors are the Dirac spin sums,

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-m,
$$

and the massive spin-one polarization sum,

$$
\sum_{\lambda=1}^{3}
\epsilon_\mu^{(\lambda)}(p)
\epsilon_\nu^{(\lambda)}(p)^*
=
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}.
$$

For a massless photon or gluon, there is no Lorentz-covariant sum over only the two physical polarizations without introducing a reference vector. With reference vector $n^\mu$,

$$
\sum_{\lambda=\pm}
\epsilon_\mu^{(\lambda)}(k;n)
\epsilon_\nu^{(\lambda)}(k;n)^*
=
-\eta_{\mu\nu}
+
\frac{k_\mu n_\nu+n_\mu k_\nu}{k\cdot n}
-
\frac{n^2k_\mu k_\nu}{(k\cdot n)^2}.
$$

When this projector is contracted into a gauge-invariant amplitude satisfying $k_\mu\mathcal A^\mu=0$, the reference-vector terms vanish. That is why the replacement

$$
\sum_{\lambda=\pm}
\epsilon_\mu^{(\lambda)}\epsilon_\nu^{(\lambda)*}
\longrightarrow
-\eta_{\mu\nu}
$$

is safe in many textbook calculations — but only after the Ward identity is true for the complete amplitude.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Polarization sums as projectors for spinors, massive vectors, and massless gauge bosons](/figures/perturbative-qft/polarization-sums.svg)

<figcaption>

Spin and polarization sums convert resolved amplitudes into probabilities for unresolved measurements. Massive vectors have a covariant projector onto the three directions transverse to $p^\mu$. Massless gauge bosons need a reference vector $n^\mu$ to project onto the two physical polarizations; the $n$-dependent pieces disappear only when contracted with a conserved current or a gauge-invariant amplitude.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), and [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/). For background on free fields, review the Foundations pages on the [Dirac Field](/foundations/free-fields/dirac-field/), [Maxwell Field](/foundations/free-fields/maxwell-field/), and [Polarizations](/foundations/free-fields/polarizations/).

## Core idea

External wavefunctions remember the quantum state that entered or left the scattering process. If the experiment resolves those states, keep the labels. If it does not, sum or average over them.

The rules are:

| Situation | Operation |
|---|---|
| final unresolved spin or polarization | sum |
| initial unresolved spin or polarization | average |
| final unresolved color | sum |
| initial unresolved color | average |
| fixed helicity amplitude | no sum over that helicity |
| internal propagator | use the propagator, not an external polarization sum |

For a $2\to n$ cross section with unpolarized initial particles, the spin- and color-averaged squared amplitude has the schematic form

$$
\overline{|\mathcal M|^2}
=
\frac{1}{(\text{spin states})_1(\text{spin states})_2}
\frac{1}{(\text{color states})_1(\text{color states})_2}
\sum_{\rm all\ unresolved}|\mathcal M|^2.
$$

For example, in QCD:

| Particle | physical spin or polarization states | color states |
|---|---:|---:|
| quark | $2$ | $N$ |
| antiquark | $2$ | $N$ |
| gluon | $2$ | $N^2-1$ |
| massive vector | $3$ | depends on the theory |
| real scalar | $1$ | depends on the theory |

The danger is that covariant-looking sums can accidentally include unphysical gauge modes. Ward identities are the safety harness.

## Setup and conventions

We use the qft.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
$$

and on-shell momenta satisfy

$$
p^2=m^2,
\qquad
p^0=E_{\mathbf p}>0.
$$

Dirac slash notation is

$$
p\!\!\!/=\gamma^\mu p_\mu.
$$

The external spinors satisfy

$$
(p\!\!\!/-m)u_s(p)=0,
\qquad
(p\!\!\!/+m)v_s(p)=0,
$$

with spin sums

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+m,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-m.
$$

For a vector polarization, we use

$$
p\cdot\epsilon^{(\lambda)}(p)=0
$$

for physical massive polarizations and

$$
k\cdot\epsilon^{(\lambda)}(k)=0
$$

for physical massless gauge-boson polarizations. Polarization vectors are normalized with mostly-minus sign conventions, so spatial physical polarizations have negative norm.

## Spinor sums

Spinor sums convert products of spinor bilinears into traces. This is the basic technology behind spin-averaged QED and Yukawa cross sections.

Suppose an amplitude contains a fermion current

$$
J^\mu=\overline u(p')\gamma^\mu u(p).
$$

The spin-summed product is

$$
\sum_{s,s'}J^\mu J^{\nu *}
=
\operatorname{tr}\left[
(p'\!\!\!/+m)\gamma^\mu(p\!\!\!/+m)\gamma^\nu
\right],
$$

where the trace is over Dirac indices. More generally, if

$$
\mathcal M=\overline u(p')\Gamma u(p),
$$

then

$$
\sum_{s,s'}|\mathcal M|^2
=
\operatorname{tr}\left[
(p'\!\!\!/+m)\Gamma(p\!\!\!/+m)\overline\Gamma
\right],
$$

with

$$
\overline\Gamma=\gamma^0\Gamma^\dagger\gamma^0.
$$

For antifermions, use

$$
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-m.
$$

The sign difference is a common source of errors in annihilation amplitudes.

## Massive vector polarization sum

A massive spin-one particle has three physical polarizations. Choose polarization vectors satisfying

$$
p\cdot\epsilon^{(\lambda)}(p)=0,
\qquad
\epsilon^{(\lambda)}(p)\cdot\epsilon^{(\lambda')}(p)^*=-\delta^{\lambda\lambda'}.
$$

The completeness relation is

$$
\Pi_{\mu\nu}^{(m)}(p)
\equiv
\sum_{\lambda=1}^{3}
\epsilon_\mu^{(\lambda)}(p)
\epsilon_\nu^{(\lambda)}(p)^*
=
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}.
$$

This projector is transverse:

$$
p^\mu\Pi_{\mu\nu}^{(m)}(p)=0.
$$

Its trace is

$$
\eta^{\mu\nu}\Pi_{\mu\nu}^{(m)}(p)=-3,
$$

which reflects the three physical polarizations, each with norm $-1$.

In the rest frame $p^\mu=(m,0,0,0)$, the three polarizations may be chosen as

$$
\epsilon^{(1)}=(0,1,0,0),
\qquad
\epsilon^{(2)}=(0,0,1,0),
\qquad
\epsilon^{(3)}=(0,0,0,1).
$$

Then

$$
\sum_{\lambda=1}^3
\epsilon_\mu^{(\lambda)}
\epsilon_\nu^{(\lambda)*}
=
\operatorname{diag}(0,1,1,1)
$$

with lower indices, which agrees with

$$
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}
$$

in the rest frame.

## Massless gauge-boson polarization sum

A massless spin-one particle has two physical polarizations, not three and not four. For a photon or gluon with momentum $k^\mu$, physical polarizations satisfy

$$
k^2=0,
\qquad
k\cdot\epsilon^{(\lambda)}(k)=0,
\qquad
\lambda=\pm.
$$

There is no Lorentz-covariant way to sum only the two physical polarizations using $k^\mu$ and $\eta_{\mu\nu}$ alone. One introduces a reference vector $n^\mu$ with $k\cdot n\ne0$. The physical-polarization projector is

$$
\Pi_{\mu\nu}^{(0)}(k;n)
=
\sum_{\lambda=\pm}
\epsilon_\mu^{(\lambda)}(k;n)
\epsilon_\nu^{(\lambda)}(k;n)^*
=
-\eta_{\mu\nu}
+
\frac{k_\mu n_\nu+n_\mu k_\nu}{k\cdot n}
-
\frac{n^2k_\mu k_\nu}{(k\cdot n)^2}.
$$

It is transverse to $k^\mu$ and $n^\mu$:

$$
k^\mu\Pi_{\mu\nu}^{(0)}(k;n)=0,
\qquad
n^\mu\Pi_{\mu\nu}^{(0)}(k;n)=0.
$$

If $n^2=0$, the last term vanishes and the formula simplifies to

$$
\Pi_{\mu\nu}^{(0)}(k;n)
=
-\eta_{\mu\nu}
+
\frac{k_\mu n_\nu+n_\mu k_\nu}{k\cdot n}.
$$

A change of $n^\mu$ changes the representative polarization vectors. Physical gauge-invariant answers cannot depend on that choice.

## The covariant shortcut

Suppose a gauge-boson amplitude has the form

$$
\mathcal M=\epsilon_\mu(k)^*\mathcal A^\mu(k),
$$

and the full amplitude satisfies the Ward identity

$$
k_\mu\mathcal A^\mu(k)=0.
$$

Then the physical polarization sum gives

$$
\begin{aligned}
\sum_{\lambda=\pm}|\mathcal M|^2
&=
\mathcal A^\mu\mathcal A^{\nu *}
\Pi_{\mu\nu}^{(0)}(k;n) \\
&=
-\mathcal A^\mu\mathcal A_\mu^*,
\end{aligned}
$$

because every term containing $k_\mu$ or $k_\nu$ vanishes.

This is why many calculations replace

$$
\sum_{\lambda=\pm}\epsilon_\mu^{(\lambda)}\epsilon_\nu^{(\lambda)*}
$$

by

$$
-\eta_{\mu\nu}.
$$

The replacement is not a definition of the physical polarization sum. It is a shortcut that is valid only inside a gauge-invariant contraction.

:::caution[Do not use the shortcut too early]
If you have dropped diagrams, used a nonconserved current, or kept only a gauge-dependent subset of an amplitude, the $n$-dependent terms in the physical projector may not vanish. In that situation, replacing the physical sum by $-\eta_{\mu\nu}$ can hide an error rather than simplify a calculation.
:::

## Explicit photon polarizations

For a massless momentum along the $z$ axis,

$$
k^\mu=(E,0,0,E),
$$

a convenient helicity basis is

$$
\epsilon_+^\mu(k)=\frac{1}{\sqrt2}(0,1,i,0),
\qquad
\epsilon_-^\mu(k)=\frac{1}{\sqrt2}(0,1,-i,0).
$$

These obey

$$
k\cdot\epsilon_\pm=0,
\qquad
\epsilon_\pm\cdot\epsilon_\pm^*=-1,
\qquad
\epsilon_+\cdot\epsilon_-^*=0.
$$

They are not unique. A gauge transformation shifts

$$
\epsilon_\mu(k)\mapsto \epsilon_\mu(k)+\alpha k_\mu.
$$

For an amplitude satisfying $k_\mu\mathcal A^\mu=0$, this shift changes nothing:

$$
(\epsilon_\mu+\alpha k_\mu)\mathcal A^\mu
=
\epsilon_\mu\mathcal A^\mu.
$$

This is the practical reason that external photon and gluon polarizations can be chosen for convenience.

## Initial-state averages

The amplitude $\mathcal M$ is a transition amplitude for specified external quantum numbers. Experiments often prepare beams without fixed spin, helicity, or color. Then we average over initial unresolved states.

For common cases:

| Initial particle | spin/polarization average | color average |
|---|---:|---:|
| real scalar | $1$ | representation-dependent |
| Dirac fermion | $1/2$ | $1/N$ for fundamental $SU(N)$ |
| photon | $1/2$ | none |
| gluon | $1/2$ | $1/(N^2-1)$ |
| massive vector | $1/3$ | representation-dependent |

Thus for unpolarized, color-averaged QCD scattering

$$
q\overline q\to gg,
$$

the initial averaging factor is

$$
\frac{1}{2}\frac{1}{2}\frac{1}{N}\frac{1}{N}
=
\frac{1}{4N^2}.
$$

For

$$
gg\to gg,
$$

the initial averaging factor is

$$
\frac{1}{2}\frac{1}{2}
\frac{1}{N^2-1}\frac{1}{N^2-1}
=
\frac{1}{4(N^2-1)^2}.
$$

Final states are summed, not averaged.

## Worked example: photon emission from a conserved current

Let

$$
\mathcal M_\lambda=\epsilon_\mu^{(\lambda)}(k)^*J^\mu,
$$

where

$$
k_\mu J^\mu=0.
$$

Then

$$
\begin{aligned}
\sum_{\lambda=\pm}|\mathcal M_\lambda|^2
&=
J^\mu J^{\nu *}
\left[
-\eta_{\mu\nu}
+
\frac{k_\mu n_\nu+n_\mu k_\nu}{k\cdot n}
-
\frac{n^2k_\mu k_\nu}{(k\cdot n)^2}
\right] \\
&=-J_\mu J^{\mu *}.
\end{aligned}
$$

Every reference-vector term vanished because it contains either $k_\mu J^\mu$ or $k_\nu J^{\nu *}$. This calculation is the cleanest way to remember the rule: physical polarization sums are reference-vector projectors, but conserved currents let us use the covariant numerator.

## Worked example: massive vector trace check

For a massive vector amplitude

$$
\mathcal M_\lambda=\epsilon_\mu^{(\lambda)}(p)^*B^\mu,
$$

the polarization sum gives

$$
\sum_{\lambda=1}^{3}|\mathcal M_\lambda|^2
=
B^\mu B^{\nu *}
\left(-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}\right).
$$

Unlike the massless gauge-boson case, the $p_\mu p_\nu/m^2$ term is not a disposable gauge artifact. It represents the longitudinal polarization of the massive vector. If the massive vector comes from a spontaneously broken gauge theory, this longitudinal mode has a Goldstone-boson interpretation at high energy, but it is still a physical external polarization.

## Common pitfalls

**Averaging over final states.** Final spin, polarization, and color states are summed. Only unresolved initial states are averaged.

**Using four photon polarizations.** A real photon or gluon has two physical helicities. The factor for an unpolarized initial photon or gluon is $1/2$, not $1/4$.

**Using $-\eta_{\mu\nu}$ without a Ward identity.** The covariant shortcut is safe only after the amplitude is gauge invariant and conserved-current terms have been checked.

**Confusing external sums with internal propagators.** Internal gauge bosons are represented by propagators. External physical gauge bosons are represented by polarization vectors and physical polarization sums.

**Dropping the longitudinal massive-vector polarization.** Massive spin-one particles have three physical polarizations. The longitudinal mode matters, especially at high energy.

**Forgetting color averages.** QCD spin averages and color averages are separate. A gluon has two physical polarizations and $N^2-1$ color states.

**Mixing helicity amplitudes with spin-summed amplitudes.** If you compute a fixed-helicity amplitude, do not also sum over that helicity unless the observable asks for it.

## Relations to other pages

- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) uses photon polarization vectors and Ward identities in concrete processes.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) uses gluon polarization sums and color averages for Yang–Mills scattering.
- [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/) introduces external spinors and spin sums in a scalar-mediated setting.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains how LSZ residues and external wavefunctions enter amplitudes.
- [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/) uses spin- and polarization-summed squared amplitudes to compute observable rates.
- [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/) explains the gauge-fixing and ghost machinery behind covariant gauge-boson propagators.
- [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/) develops helicity methods that often avoid explicit polarization sums until the final observable is assembled.

## Research status

The spin sums and polarization projectors on this page are standard. They are not research questions, but they remain common sources of errors in practical calculations.

Active work enters when polarization sums meet realistic observables: infrared-safe definitions with unresolved radiation, automated amplitude generators, helicity and color sampling, subtraction schemes, gauge-invariant parton showers, massive-vector high-energy behavior, and numerical stability in multi-leg amplitudes.

## Exercises

### Exercise 1: Massive-vector transversality

Show that

$$
\Pi_{\mu\nu}^{(m)}(p)
=
-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}
$$

satisfies

$$
p^\mu\Pi_{\mu\nu}^{(m)}(p)=0
$$

when $p^2=m^2$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\begin{aligned}
p^\mu\Pi_{\mu\nu}^{(m)}(p)
&=
p^\mu\left(-\eta_{\mu\nu}+\frac{p_\mu p_\nu}{m^2}\right) \\
&=
-p_\nu+\frac{p^2p_\nu}{m^2} \\
&=
-p_\nu+p_\nu \\
&=0.
\end{aligned}
$$

The result uses the on-shell condition $p^2=m^2$.

</details>

### Exercise 2: Counting massive polarizations

Show that

$$
\eta^{\mu\nu}\Pi_{\mu\nu}^{(m)}(p)=-3.
$$

<details>
<summary><strong>Solution</strong></summary>

Using $\eta^{\mu\nu}\eta_{\mu\nu}=4$ and $p^2=m^2$,

$$
\eta^{\mu\nu}\Pi_{\mu\nu}^{(m)}
=
-4+\frac{p^2}{m^2}
=
-4+1
=
-3.
$$

The minus sign comes from the mostly-minus metric and the convention that physical vector polarizations have norm $-1$.

</details>

### Exercise 3: Reference-vector terms vanish

Let $J^\mu$ be a conserved current with

$$
k_\mu J^\mu=0.
$$

Show that

$$
J^\mu J^{\nu *}\Pi_{\mu\nu}^{(0)}(k;n)
=
-J_\mu J^{\mu *}.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the massless projector:

$$
\Pi_{\mu\nu}^{(0)}(k;n)
=
-\eta_{\mu\nu}
+
\frac{k_\mu n_\nu+n_\mu k_\nu}{k\cdot n}
-
\frac{n^2k_\mu k_\nu}{(k\cdot n)^2}.
$$

Then

$$
J^\mu J^{\nu *}(-\eta_{\mu\nu})=-J_\mu J^{\mu *}.
$$

Every remaining term contains $J\cdot k$ or $J^*\cdot k$:

$$
J^\mu J^{\nu *}k_\mu n_\nu=(J\cdot k)(J^*\cdot n)=0,
$$

$$
J^\mu J^{\nu *}n_\mu k_\nu=(J\cdot n)(J^*\cdot k)=0,
$$

and

$$
J^\mu J^{\nu *}k_\mu k_\nu=(J\cdot k)(J^*\cdot k)=0.
$$

Therefore the $n$-dependent terms vanish.

</details>

### Exercise 4: Spin trace for a vector current

Using

$$
\sum_su_s(p)\overline u_s(p)=p\!\!\!/+m,
$$

show that

$$
\sum_{s,s'}
\left[\overline u_{s'}(p')\gamma^\mu u_s(p)\right]
\left[\overline u_{s'}(p')\gamma^\nu u_s(p)\right]^*
=
\operatorname{tr}\left[(p'\!\!\!/+m)\gamma^\mu(p\!\!\!/+m)\gamma^\nu\right].
$$

<details>
<summary><strong>Solution</strong></summary>

The complex conjugate of the current can be written as

$$
\left[\overline u(p')\gamma^\nu u(p)\right]^*
=
\overline u(p)\gamma^\nu u(p'),
$$

using $\gamma^0(\gamma^\nu)^\dagger\gamma^0=\gamma^\nu$. Therefore

$$
\sum_{s,s'}
\overline u_{s'}(p')\gamma^\mu u_s(p)
\overline u_s(p)\gamma^\nu u_{s'}(p')
$$

can be read as a trace over Dirac indices:

$$
\operatorname{tr}\left[
\left(\sum_{s'}u_{s'}(p')\overline u_{s'}(p')\right)
\gamma^\mu
\left(\sum_su_s(p)\overline u_s(p)\right)
\gamma^\nu
\right].
$$

Using the spin sums gives

$$
\operatorname{tr}\left[(p'\!\!\!/+m)\gamma^\mu(p\!\!\!/+m)\gamma^\nu\right].
$$

</details>

### Exercise 5: Initial-state averaging in gluon scattering

For $SU(N)$ Yang–Mills theory, what is the initial spin/color averaging factor for unpolarized gluon scattering

$$
gg\to gg?
$$

<details>
<summary><strong>Solution</strong></summary>

Each initial gluon has two physical polarizations and $N^2-1$ color states. Therefore the averaging factor is

$$
\frac{1}{2(N^2-1)}\frac{1}{2(N^2-1)}
=
\frac{1}{4(N^2-1)^2}.
$$

For QCD, $N=3$, so the factor is

$$
\frac{1}{4\cdot8^2}=\frac{1}{256}.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially §§46, 50, 56, 59–60, and 72, for spin sums, photon polarizations, QED scattering, and non-Abelian gauge-boson rules.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2, 5, 6, and 8, for one-particle states, massless polarizations, Feynman rules, and QED examples.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 8, 13, 26, and 27, for gauge-boson polarizations, QED/QCD amplitudes, Ward identities, and helicity-oriented calculations.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 5 and 15–17, for spin averages, polarization sums, and QCD scattering conventions.

## Version history

- **2026-06-12:** Initial polished draft. Establishes qft.org conventions for spin sums, massive and massless vector polarization projectors, initial-state averaging, and Ward-identity simplifications in tree-level scattering.
