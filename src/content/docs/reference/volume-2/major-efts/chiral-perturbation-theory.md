---
title: "Chiral Perturbation Theory"
description: "Chiral perturbation theory as the low-energy effective field theory of QCD: Goldstone bosons, nonlinear chiral symmetry, derivative power counting, quark-mass insertions, loops, and low-energy constants."
sidebar:
  label: "Chiral Perturbation Theory"
  order: 20
level: Graduate
status: "Polished draft"
source: "Coleman 1985, Soft Pions; Weinberg Vol. II, effective Lagrangians and chiral dynamics; Burgess 2020, ch. 8; Schwartz 2014, chs. 22 and 29; Gasser and Leutwyler 1984–1985."
topics:
  - chiral perturbation theory
  - Goldstone bosons
  - pion effective field theory
  - nonlinear symmetry realization
  - derivative expansion
  - low-energy constants
canonicalTopics:
  - chiral-perturbation-theory
  - pion-eft
  - goldstone-effective-action
researchStatus:
  established:
    - "Chiral perturbation theory is the standard low-energy EFT of QCD Goldstone bosons, organized by momenta and light-quark masses over the chiral symmetry-breaking scale."
  active:
    - "Higher-order low-energy constants, lattice-QCD matching, finite-volume effects, baryon and nuclear chiral EFT, and precision hadronic inputs remain active research areas."
---

## Summary

Chiral perturbation theory, usually abbreviated ChPT or $\chi\mathrm{PT}$, is the low-energy effective field theory of QCD in the regime where the relevant light degrees of freedom are pions, and sometimes kaons and the eta, rather than quarks and gluons.

Its starting point is a symmetry fact about QCD with light quarks. If $N_f$ quark masses are neglected, the classical QCD Lagrangian has an approximate chiral symmetry

$$
G=SU(N_f)_L\times SU(N_f)_R.
$$

The QCD vacuum does not preserve this whole group. It preserves the diagonal vector subgroup

$$
H=SU(N_f)_V.
$$

The symmetry-breaking pattern is therefore

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V.
$$

The associated Goldstone fields live on the coset space

$$
\frac{SU(N_f)_L\times SU(N_f)_R}{SU(N_f)_V}
\simeq SU(N_f).
$$

They are packaged into a unitary matrix field

$$
U(x)=\exp\!\left(\frac{2i\Pi(x)}{f}\right),
\qquad
\Pi(x)=\pi^a(x)T^a,
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

which transforms as

$$
U(x)\longmapsto L\,U(x)\,R^\dagger,
\qquad L\in SU(N_f)_L,
\qquad R\in SU(N_f)_R.
$$

At leading order, the mesonic chiral Lagrangian is

$$
\mathcal L_2
=\frac{f^2}{4}\operatorname{tr}\!\left(\partial_\mu U\,\partial^\mu U^\dagger\right)
+\frac{f^2B_0}{2}\operatorname{tr}\!\left(MU^\dagger+UM^\dagger\right).
$$

The first term is fixed by chiral symmetry and the normalization of $f$. The second term includes the light-quark mass matrix $M$ as a spurion that explicitly breaks chiral symmetry. The expansion is not an expansion in a small coupling in the usual particle-physics sense. It is an expansion in

$$
\frac{p}{\Lambda_\chi},
\qquad
\frac{m_\pi}{\Lambda_\chi},
\qquad
\Lambda_\chi\sim 4\pi f_\pi,
$$

with light-quark masses counted as order $p^2$ because $m_\pi^2\propto m_q$.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Map from QCD chiral symmetry to Goldstone coset fields, the leading chiral Lagrangian, loop corrections, low-energy constants, and hadronic observables](/figures/renormalization-rg-eft/chiral-perturbation-theory-map.svg)

<figcaption>

Chiral perturbation theory replaces quarks and gluons at low momentum by Goldstone fields $U(x)\in G/H$. Symmetry fixes the allowed local terms; power counting orders derivatives, quark-mass insertions, loops, and low-energy constants.

</figcaption>
</figure>

:::note[The punchline]
ChPT is not a model of pions guessed from intuition. It is the most general local EFT compatible with QCD's approximate chiral symmetry, organized by a derivative and quark-mass expansion.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Nonlinear Sigma Models](/renormalization-rg-eft/major-efts/nonlinear-sigma-models/). It is also useful to know spontaneous symmetry breaking, Noether currents, and the distinction between exact and approximate symmetries.

This page uses the mostly-minus metric. The displayed Lagrangians are Lorentzian. In Euclidean statistical or lattice contexts, signs in the action change in the usual way.

## Core idea

QCD is strongly coupled at low energies. That sounds like bad news for perturbation theory in the quark-gluon variables. But the infrared theory is not arbitrary. It is constrained by symmetries.

For two nearly massless quarks, $u$ and $d$, QCD approximately has

$$
SU(2)_L\times SU(2)_R
$$

chiral symmetry. For three light quarks, $u,d,s$, the corresponding approximate symmetry is

$$
SU(3)_L\times SU(3)_R,
$$

though the strange quark is less light, so the convergence of the $SU(3)$ chiral expansion is typically more delicate.

The vacuum forms a quark condensate with the schematic transformation property

$$
\langle \bar q_R q_L\rangle\neq 0,
$$

which locks the left and right rotations together and leaves only $SU(N_f)_V$. Goldstone's theorem then requires $N_f^2-1$ light pseudoscalar bosons in the chiral limit.

The key EFT move is:

$$
\text{low-energy QCD}
\quad\leadsto\quad
\text{Goldstone fields on }G/H
\quad+\quad
\text{all local terms allowed by symmetry}.
$$

Because Goldstone bosons interact derivatively in the exact symmetry limit, amplitudes vanish when one external Goldstone momentum is taken soft, modulo explicit symmetry breaking and anomaly effects. This is the physical reason why a momentum expansion can work even when the underlying QCD coupling is strong.

## Symmetry pattern and fields

### Left and right rotations

For $N_f$ massless quarks, decompose

$$
q_L=P_L q,
\qquad
q_R=P_R q,
\qquad
P_{L,R}=\frac{1\mp\gamma^5}{2}.
$$

The chiral symmetry acts as

$$
q_L\mapsto Lq_L,
\qquad
q_R\mapsto Rq_R,
\qquad
L\in SU(N_f)_L,
\qquad R\in SU(N_f)_R.
$$

The Goldstone field $U(x)$ is chosen to transform as

$$
U\mapsto LUR^\dagger.
$$

This transformation law is the main reason $U$ is useful. It lets us write symmetry-invariant terms by taking traces of products such as

$$
\partial_\mu U\,\partial^\mu U^\dagger.
$$

The field $U$ is not a small fluctuation in a vector space. It is a coordinate on the group manifold. The pion fields $\pi^a$ are local coordinates near the identity.

### Two flavors

For $N_f=2$,

$$
\Pi=\frac12\pi^a\tau^a,
$$

where $\tau^a$ are Pauli matrices. The three Goldstone bosons are

$$
\pi^+,
\qquad \pi^0,
\qquad \pi^-.
$$

The coset relation

$$
\frac{SU(2)_L\times SU(2)_R}{SU(2)_V}\simeq SU(2)\simeq S^3
$$

means the two-flavor pion field is a map from spacetime into a three-sphere, at least before explicit symmetry breaking is included.

### Three flavors

For $N_f=3$,

$$
\Pi=\pi^aT^a,
\qquad a=1,\ldots,8,
$$

and the Goldstone multiplet contains

$$
\pi^\pm,
\quad \pi^0,
\quad K^\pm,
\quad K^0,
\quad \bar K^0,
\quad \eta.
$$

In practice, $SU(3)$ ChPT has more low-energy constants and often converges more slowly than $SU(2)$ ChPT because $m_K$ and $m_\eta$ are not as small as $m_\pi$.

## Leading chiral Lagrangian

The leading chiral Lagrangian contains all terms of chiral order $p^2$. Quark masses also count as order $p^2$ because the Goldstone masses are linear in quark masses but squared in the relativistic dispersion relation.

The standard leading-order mesonic Lagrangian is

$$
\mathcal L_2
=\frac{f^2}{4}\operatorname{tr}\!\left(\partial_\mu U\,\partial^\mu U^\dagger\right)
+\frac{f^2B_0}{2}\operatorname{tr}\!\left(MU^\dagger+UM^\dagger\right).
$$

Here:

| Symbol | Meaning |
|---|---|
| $f$ | Goldstone decay constant in the chiral limit. |
| $B_0$ | Low-energy constant relating quark masses to Goldstone masses. |
| $M$ | Light-quark mass matrix, treated as a spurion. |
| $U$ | Goldstone matrix transforming as $U\to LUR^\dagger$. |

The spurion rule is important. To write the mass term in a formally chiral-invariant way, assign

$$
M\mapsto LMR^\dagger.
$$

Then

$$
\operatorname{tr}(MU^\dagger+UM^\dagger)
$$

is invariant. After the invariant terms are listed, set $M$ equal to the physical quark mass matrix. This is the EFT version of saying that quark masses explicitly break the symmetry in a controlled way.

## Canonical normalization and pion masses

Expand

$$
U=1+\frac{2i\Pi}{f}-\frac{2\Pi^2}{f^2}+O(\Pi^3).
$$

The kinetic term gives

$$
\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a+O(\pi^4/f^2).
$$

This fixes the normalization of the exponential parametrization used on this page.

For two degenerate light quarks,

$$
M=m_q\mathbf 1_2,
$$

the mass term expands as

$$
\frac{f^2B_0}{2}\operatorname{tr}\left(MU^\dagger+UM^\dagger\right)
=\text{constant}-B_0m_q\,\pi^a\pi^a+O(\pi^4/f^2).
$$

Comparing with

$$
\mathcal L\supset -\frac12m_\pi^2\pi^a\pi^a,
$$

gives

$$
m_\pi^2=2B_0m_q.
$$

For nondegenerate quarks in $SU(3)$, the same leading-order Lagrangian gives relations such as

$$
m_\pi^2=B_0(m_u+m_d),
\qquad
m_K^2=B_0(m_s+m_{u,d}),
$$

with the precise kaon formula depending on the kaon charge and the quark masses kept distinct.

:::tip[The mass is order p squared]
In chiral power counting, $m_q$ counts as order $p^2$, not order $p$. This is because $m_\pi^2\sim m_q$, while derivatives enter through $p^2$ in the kinetic term.
:::

## Why Goldstone interactions are derivative

In the exact chiral limit $M=0$, the action is invariant under a constant shift of the Goldstone coordinates induced by broken symmetry transformations. A non-derivative potential for the Goldstones would choose preferred points on the coset and would therefore break the symmetry explicitly.

The leading interactions therefore arise from expanding the kinetic term on the curved target space:

$$
\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
=\frac12(\partial\pi)^2
+\frac{1}{f^2}\pi^2(\partial\pi)^2
+\cdots.
$$

The schematic form is what matters:

$$
\mathcal L_{\mathrm{int}}
\sim \frac{1}{f^2}\pi^2(\partial\pi)^2+\frac{1}{f^4}\pi^4(\partial\pi)^2+\cdots.
$$

Every interaction in the chiral limit carries derivatives. This is the EFT origin of soft-pion behavior.

## Weinberg power counting

For purely mesonic ChPT, a connected diagram with $L$ loops and vertices of chiral order $d_v$ contributes at chiral order

$$
D=2+2L+\sum_v(d_v-2).
$$

Here $d_v$ counts derivatives and powers of $m_q$ with $m_q\sim p^2$. The amplitude scales schematically as

$$
\mathcal A_D\sim p^D.
$$

This formula is a small masterpiece of EFT bookkeeping. It says:

- tree diagrams from $\mathcal L_2$ are order $p^2$;
- one-loop diagrams built only from $\mathcal L_2$ are order $p^4$;
- tree diagrams with one vertex from $\mathcal L_4$ are also order $p^4$;
- two-loop diagrams from $\mathcal L_2$ appear at order $p^6$.

Therefore loops and higher-derivative counterterms enter at the same chiral order, exactly as EFT demands.

## Low-energy constants

The leading constants $f$ and $B_0$ are not predicted by chiral symmetry. They encode QCD dynamics. At next-to-leading order, the Lagrangian contains many more constants, traditionally denoted $L_i$ in $SU(3)$ ChPT and $\ell_i$ in $SU(2)$ ChPT.

The general structure is

$$
\mathcal L_{\chi\mathrm{PT}}
=\mathcal L_2+\mathcal L_4+\mathcal L_6+\cdots.
$$

The low-energy constants do three jobs.

First, they encode short-distance QCD information not resolved by the pion EFT. Resonances such as the $\rho$ meson are not usually explicit in the simplest ChPT; their effects appear inside low-energy constants.

Second, they absorb divergences from loops. One-loop graphs from $\mathcal L_2$ generate local divergences of order $p^4$, and those are canceled by counterterms in $\mathcal L_4$.

Third, they make predictions possible once a finite number of constants is measured or matched. At any fixed chiral order, only finitely many low-energy constants are needed for a given sector.

## Soft-pion behavior and Adler zeros

Goldstone bosons are special because broken symmetries constrain amplitudes with soft external pions. In many processes, taking a pion momentum to zero forces the amplitude to vanish in the chiral limit. This is called an Adler zero.

A schematic version is

$$
\mathcal A(\pi(q)+X\to Y)\longrightarrow 0
\qquad \text{as }q^\mu\to 0,
$$

when the symmetry and external states allow it. The exact statement depends on the current algebra, external states, and explicit symmetry breaking, so one should not apply the slogan blindly.

ChPT builds this behavior into the Lagrangian. Since Goldstone interactions are derivative in the chiral limit, every external soft Goldstone tends to bring a factor of its momentum, except where current insertions, anomalies, or explicit symmetry breaking modify the limit.

## Example: pion-pion scattering at leading order

For two-flavor ChPT, the leading $\pi\pi$ scattering amplitude is fixed by $f_\pi$ and $m_\pi$ at order $p^2$. In a standard isospin convention, the invariant amplitude has the schematic structure

$$
A(s,t,u)=\frac{s-m_\pi^2}{f_\pi^2}+O(p^4),
$$

with physical channel amplitudes obtained by combining $A(s,t,u)$ with the appropriate isospin Kronecker deltas and permutations of $s,t,u$.

The important lesson is not the exact channel bookkeeping. It is that the leading low-energy amplitude is fixed by symmetry up to the measured constants $f_\pi$ and $m_\pi$. Corrections are organized systematically by $p^4$, $p^6$, and so on.

## Loops and the chiral scale

A typical loop correction in four dimensions brings a factor

$$
\frac{p^2}{16\pi^2f^2}.
$$

This motivates the estimate

$$
\Lambda_\chi\sim 4\pi f_\pi.
$$

The chiral scale is not a magic wall. It is an estimate of where the derivative expansion becomes strongly corrected and where heavier hadronic degrees of freedom, such as vector mesons and baryon resonances, can no longer be ignored.

The practical expansion is therefore

$$
\mathcal A
=\mathcal A_{p^2}
+\mathcal A_{p^4}
+\mathcal A_{p^6}
+\cdots,
$$

where

$$
\mathcal A_{p^4}
=\text{one-loop graphs from }\mathcal L_2
+\text{tree graphs from }\mathcal L_4.
$$

This is the usual EFT pattern: loop divergences force precisely the higher-order local terms that symmetry already allowed.

## SU(2), SU(3), and baryons

There are several commonly used versions of ChPT.

| Version | Light fields | Typical use | Caveat |
|---|---|---|---|
| $SU(2)$ mesonic ChPT | pions | very low-energy pion physics and light-quark extrapolations | does not keep kaons and eta as light fields |
| $SU(3)$ mesonic ChPT | pions, kaons, eta | strange processes and flavor symmetry | convergence can be slower |
| baryon ChPT | pions plus nucleons or baryons | low-energy pion-nucleon and nuclear inputs | power counting is subtler with heavy baryon masses |
| heavy-baryon ChPT | velocity-labeled baryons plus pions | restores transparent low-energy counting | sacrifices manifest Lorentz invariance unless corrected systematically |

This page focuses on the mesonic logic. Baryon and nuclear chiral EFT require additional care because nucleons remain massive in the chiral limit.

## Anomalies and the Wess-Zumino-Witten term

The ordinary derivative expansion is not the whole story. QCD has anomalies, and the chiral EFT must reproduce them. The most famous example is the anomalous process

$$
\pi^0\to \gamma\gamma.
$$

The anomaly is encoded in the chiral theory by the Wess-Zumino-Witten term. This term is topological in origin and is not simply another ordinary trace of two-derivative or four-derivative operators. It is fixed in normalization by anomaly matching.

For this page, the main lesson is:

$$
\text{EFT must match not only symmetries, but also anomalies.}
$$

Anomalies are infrared data that cannot be erased by changing short-distance variables.

## What ChPT predicts and what it fits

ChPT predicts the form of low-energy amplitudes, the dependence on momenta and quark masses, the nonanalytic terms from loops, and relations enforced by symmetry. It does not predict every number from symmetry alone.

The constants

$$
f,
\qquad B_0,
\qquad L_i,
\qquad \ell_i,
\qquad \cdots
$$

must be obtained from experiment, lattice QCD, resonance estimates, or matching. Once fixed, the EFT makes correlated predictions for many low-energy observables.

A particularly important class of terms is nonanalytic dependence such as

$$
m_\pi^2\log m_\pi^2,
$$

which comes from pion loops. Such chiral logarithms are robust predictions of the light degrees of freedom and their symmetry structure.

## Common pitfalls

**Thinking pions are weakly coupled because QCD is weakly coupled.** Low-energy QCD is not weakly coupled in quark-gluon variables. ChPT works because Goldstone symmetry enforces a derivative expansion.

**Confusing $f$ with $f_\pi$ without convention checks.** Different normalizations use $f_\pi\simeq 92\,\mathrm{MeV}$ or $F_\pi\simeq 184\,\mathrm{MeV}$ depending on current and generator conventions. This page uses the convention in which the leading kinetic term is canonically normalized by $U=\exp(2i\Pi/f)$.

**Forgetting that quark masses count as order $p^2$.** The chiral expansion counts $m_q\sim p^2$, because $m_\pi^2\sim m_q$.

**Treating $SU(3)$ ChPT as automatically as accurate as $SU(2)$ ChPT.** The strange quark is heavier, and kaon/eta loops probe higher scales. The expansion is still systematic, but numerical convergence can be less friendly.

**Calling every low-energy pion model ChPT.** ChPT is the general symmetry-based EFT with a controlled power counting. A model with pions is not automatically ChPT.

**Ignoring anomalies.** The Wess-Zumino-Witten term is not optional if the EFT is meant to reproduce anomalous QCD processes.

## Relation to other pages

Chiral perturbation theory is a concrete example of [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), and [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/). It is also a special case of [Nonlinear Sigma Models](/renormalization-rg-eft/major-efts/nonlinear-sigma-models/), with target space $G/H$ determined by the chiral symmetry-breaking pattern.

The pages on [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) explain the statistical-field-theory side of symmetry and universality. The gauge-theory pages explain why QCD becomes strongly coupled in the infrared and why hadrons, not quarks and gluons, are the natural low-energy variables.

## Research status

The core symmetry and power-counting structure of mesonic ChPT is established. The EFT is a standard tool for low-energy hadronic physics.

Active work includes higher-order calculations, determining low-energy constants, matching to lattice QCD, finite-volume effects, isospin breaking, electromagnetic corrections, baryon and nuclear chiral EFT, and using chiral constraints in precision Standard Model and beyond-Standard-Model observables.

A useful rule of thumb is that ChPT is most authoritative when it states symmetry constraints, soft limits, nonanalytic light-mass dependence, and systematic low-energy expansions. It is less automatic when extrapolated to momenta near resonances or when many-body nuclear dynamics introduces additional low scales.

## Exercises

### Exercise 1: Canonical normalization

Using

$$
U=\exp\!\left(\frac{2i\pi^aT^a}{f}\right),
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

show that

$$
\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a+O(\pi^4/f^2).
$$

<details><summary><strong>Solution</strong></summary>

Expand to first order in the pion field:

$$
U=1+\frac{2i\pi^aT^a}{f}+O(\pi^2),
\qquad
U^\dagger=1-\frac{2i\pi^aT^a}{f}+O(\pi^2).
$$

Then

$$
\partial_\mu U=\frac{2i}{f}\partial_\mu\pi^aT^a+O(\pi\partial\pi/f^2),
$$

and

$$
\partial^\mu U^\dagger=-\frac{2i}{f}\partial^\mu\pi^bT^b+O(\pi\partial\pi/f^2).
$$

Therefore

$$
\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
=\frac{4}{f^2}\partial_\mu\pi^a\partial^\mu\pi^b\operatorname{tr}(T^aT^b)+O(\pi^2(\partial\pi)^2/f^4).
$$

Using $\operatorname{tr}(T^aT^b)=\delta^{ab}/2$ gives

$$
\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
=\frac{2}{f^2}\partial_\mu\pi^a\partial^\mu\pi^a+\cdots.
$$

Multiplication by $f^2/4$ yields the canonical kinetic term.

</details>

### Exercise 2: Pion mass from the spurion term

For two degenerate quarks with $M=m_q\mathbf 1_2$, derive $m_\pi^2=2B_0m_q$ from the leading chiral Lagrangian.

<details><summary><strong>Solution</strong></summary>

Use

$$
U+U^\dagger=2-\frac{4\Pi^2}{f^2}+O(\Pi^4/f^4),
\qquad
\Pi=\pi^aT^a.
$$

The mass term is

$$
\frac{f^2B_0}{2}\operatorname{tr}(M(U^\dagger+U))
=\frac{f^2B_0m_q}{2}\operatorname{tr}(U+U^\dagger).
$$

The quadratic part is

$$
-2B_0m_q\operatorname{tr}(\Pi^2)
=-2B_0m_q\pi^a\pi^b\frac12\delta^{ab}
=-B_0m_q\pi^a\pi^a.
$$

Since the Lorentzian mass term is

$$
-\frac12m_\pi^2\pi^a\pi^a,
$$

we obtain

$$
m_\pi^2=2B_0m_q.
$$

</details>

### Exercise 3: Chiral order of a loop amplitude

Use the formula

$$
D=2+2L+\sum_v(d_v-2)
$$

to determine the chiral order of a one-loop diagram built only from vertices in $\mathcal L_2$.

<details><summary><strong>Solution</strong></summary>

For vertices from $\mathcal L_2$, each $d_v=2$, so every term in the sum vanishes:

$$
\sum_v(d_v-2)=0.
$$

For one loop, $L=1$. Therefore

$$
D=2+2(1)=4.
$$

So one-loop diagrams made only from leading-order vertices contribute at order $p^4$. This is why $\mathcal L_4$ counterterms are needed at the same order.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for effective Lagrangians, current algebra, and chiral dynamics.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, PCAC, and dilatations.
- J. Gasser and H. Leutwyler, classic papers on chiral perturbation theory and the systematic low-energy expansion.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapter on QCD and chiral perturbation theory.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for the EFT viewpoint on nonrenormalizable theories, weak interactions, QCD, and chiral dynamics.
- A. Pich, chiral perturbation theory lecture notes, for a compact phenomenological introduction.

## Version history

- 2026-06-19: First polished draft. Introduced the symmetry pattern, Goldstone field $U(x)$, leading chiral Lagrangian, power counting, low-energy constants, soft-pion behavior, and worked normalization exercises.
