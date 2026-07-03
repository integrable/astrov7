---
title: "Beta Function of Yang–Mills"
description: "A derivation-oriented guide to the one-loop beta function of non-Abelian gauge theory, including group factors, matter contributions, and asymptotic freedom."
sidebar:
  label: "Yang–Mills Beta Function"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§73, 78; Weinberg Vol. II Chs. 17–18; Schwartz Ch. 26; Coleman on asymptotic freedom; Wilson and Kogut on RG."
topics:
  - Yang–Mills beta function
  - asymptotic freedom
  - background-field gauge
  - gauge boson anti-screening
  - group theory factors
canonicalTopics:
  - yang-mills-beta-function
  - asymptotic-freedom
  - background-field-gauge
  - gauge-coupling-running
  - non-abelian-renormalization
researchStatus:
  established:
    - "The one-loop Yang–Mills beta function is a universal perturbative result; its negative sign for sufficiently small matter content explains asymptotic freedom."
  active:
    - "Higher-loop beta functions, conformal windows, threshold matching, scheme dependence, and nonperturbative infrared dynamics remain active areas of gauge-theory research."
---

## Summary

The one-loop beta function of Yang–Mills theory is the result that turns non-Abelian gauge theory from a classical idea into the engine of QCD. Unlike QED, Yang–Mills gauge bosons carry gauge charge. Their self-interactions contribute to the running of the gauge coupling, and the sign of that contribution is opposite to ordinary matter screening.

For a gauge group $G$ with coupling $g$, Dirac fermions in representations $R_f$, and complex scalars in representations $R_s$, the one-loop beta function is

$$
\beta(g)
\equiv \mu\frac{dg}{d\mu}
=-\frac{g^3}{16\pi^2}b_0+O(g^5),
$$

where

$$
b_0
=\frac{11}{3}C_A
-\frac{4}{3}\sum_f T(R_f)
-\frac{1}{3}\sum_s T(R_s).
$$

Here $C_A$ is the quadratic Casimir of the adjoint representation, and $T(R)$ is the Dynkin index of representation $R$.

If $b_0>0$, then $\beta(g)<0$ at weak coupling: the coupling decreases at high energy. This is asymptotic freedom.

## Prerequisites

You should know [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/), [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/), [Gauge Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/), [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/), and [Background-Field Gauge](/gauge-theories-standard-model/gauge-quantization/background-field-gauge/).

For the renormalization logic, read [Renormalizability of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/renormalizability-of-gauge-theories/) and [Gauge-Invariant Counterterms](/gauge-theories-standard-model/gauge-renormalization/gauge-invariant-counterterms/) first. For comparison with the Abelian case, read [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/).

## Core idea

In QED, charged matter screens electric charge. In Yang–Mills theory, matter still screens, but the gauge field itself is charged and produces a larger anti-screening contribution. This is the physical origin of the sign

$$
\beta(g)<0
$$

for pure Yang–Mills theory.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A flowchart showing the gauge-and-ghost contribution, the Dirac matter contribution, and the scalar matter contribution to the one-loop Yang–Mills coefficient $b_0$, followed by the beta function and the criterion for asymptotic freedom.](/figures/gauge-theories-standard-model/yang-mills-beta-function-balance.svg)

<figcaption>

The one-loop coefficient is a competition. Gauge and ghost loops contribute $+(11/3)C_A$ to $b_0$, while matter loops subtract. Since $\beta(g)=-(b_0/16\pi^2)g^3+O(g^5)$, positive $b_0$ means asymptotic freedom.

</figcaption>
</figure>

The calculation is not just a matter of drawing one more loop than in QED. Non-Abelian gauge fixing introduces ghosts, gauge-boson loops are gauge-dependent before summing all contributions, and the relation between field renormalization and coupling renormalization is governed by Slavnov–Taylor identities. Background-field gauge packages the result especially cleanly: the coefficient of the background kinetic term determines the running coupling.

## Setup and conventions

We use Hermitian generators satisfying

$$
[T_R^a,T_R^b]=if^{abc}T_R^c,
$$

and the covariant derivative convention

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a.
$$

With this convention,

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT_R^a,
$$

where

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

The Yang–Mills action is

$$
S_{\rm YM}
=\int d^4x\left(-\frac14 F_{\mu\nu}^aF^{a\mu\nu}\right).
$$

The sign convention for the non-Abelian term in $F_{\mu\nu}^a$ can differ across books. The one-loop beta function above is independent of that convention, provided the Feynman rules are used consistently.

## Group theory data

The beta function uses two standard invariants.

The Dynkin index $T(R)$ is defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab}.
$$

The quadratic Casimir $C_2(R)$ is defined by

$$
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

For the adjoint representation,

$$
C_A\equiv C_2({\rm adj}),
\qquad
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

For $SU(N)$, the most common values are

| Representation | Dimension | $T(R)$ | $C_2(R)$ |
|---|---:|---:|---:|
| Fundamental $F$ | $N$ | $1/2$ | $(N^2-1)/(2N)$ |
| Adjoint | $N^2-1$ | $N$ | $N$ |

For QCD, $G=SU(3)$, so

$$
C_A=3,
\qquad
T(F)=\frac12,
\qquad
C_F=\frac43.
$$

The beta function depends on $C_A$ and $T(R)$ at one loop. The fermion self-energy and many scattering formulas also involve $C_F$, but the universal coefficient $b_0$ uses the trace normalization of matter loops.

## The one-loop result

For a general four-dimensional Yang–Mills theory with Dirac fermions and complex scalars,

$$
\boxed{
\beta(g)
=-\frac{g^3}{16\pi^2}
\left[
\frac{11}{3}C_A
-\frac{4}{3}\sum_fT(R_f)
-\frac{1}{3}\sum_sT(R_s)
\right]
+O(g^5)
}
$$

The sums run over Dirac fermion species and complex scalar species. If instead the theory is described using left-handed Weyl fermions and real scalars, the same result is written as

$$
b_0
=\frac{11}{3}C_A
-\frac{2}{3}\sum_{\rm Weyl}T(R_f)
-\frac{1}{6}\sum_{\rm real}T(R_s).
$$

These are the same formula because one Dirac fermion is two Weyl fermions, and one complex scalar is two real scalars.

Pure Yang–Mills theory has no matter, so

$$
b_0=\frac{11}{3}C_A,
\qquad
\beta(g)=-\frac{11C_A}{48\pi^2}g^3+O(g^5).
$$

For QCD with $n_f$ Dirac quarks in the fundamental representation of $SU(N_c)$,

$$
b_0
=\frac{11}{3}N_c-\frac{4}{3}n_f\frac12
=\frac{11}{3}N_c-\frac{2}{3}n_f.
$$

For $SU(3)$ QCD,

$$
b_0=11-\frac{2}{3}n_f.
$$

Thus QCD is asymptotically free for

$$
n_f<\frac{33}{2}.
$$

For any integer $n_f\leq 16$, the one-loop coefficient is positive.

## What contributes to the coefficient

The one-loop running of a non-Abelian gauge coupling is extracted from logarithmic divergences in gauge-field correlation functions. In a covariant gauge, the relevant one-loop diagrams include:

| Loop type | Exists in QED? | Contribution to $b_0$ | Interpretation |
|---|---:|---:|---|
| Gauge-boson loop | no | part of $+(11/3)C_A$ | non-Abelian self-interaction |
| Ghost loop | no | part of $+(11/3)C_A$ | removes unphysical polarizations consistently |
| Fermion loop | yes | $-(4/3)T(R)$ per Dirac fermion | matter screening |
| Scalar loop | yes | $-(1/3)T(R)$ per complex scalar | matter screening |

One should not overinterpret the separate gauge-boson and ghost entries. Their individual values depend on gauge-fixing choices and bookkeeping. Their sum, together with the required counterterms, gives the gauge-invariant coefficient $+(11/3)C_A$.

The matter terms are easier to recognize. They are the non-Abelian version of vacuum polarization by charged fields. The gauge term is the new non-Abelian ingredient.

## Background-field gauge route

Background-field gauge is the shortest conceptual route to the beta function. Split the gauge field into a background field and a quantum fluctuation,

$$
A_\mu^a=\bar A_\mu^a+a_\mu^a.
$$

Choose a gauge-fixing function that is covariant with respect to background gauge transformations, for example

$$
G^a=(\bar D^\mu a_\mu)^a.
$$

Then the effective action $\Gamma[\bar A]$ remains invariant under background gauge transformations. Therefore its divergent local two-derivative term must have the form

$$
\Gamma_{\rm div}[\bar A]
\supset
-\frac14\,\delta Z_{\bar A}\int d^4x\,
\bar F_{\mu\nu}^a\bar F^{a\mu\nu}.
$$

The background Ward identity implies the simple relation

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

Thus the coupling renormalization can be read from the background-field two-point function. This does not make the physics different; it makes the bookkeeping civilized. Without background-field gauge, one can still compute the same beta function, but the Slavnov–Taylor identities distribute the same information among several renormalization constants.

## Running solution

At one loop,

$$
\mu\frac{dg}{d\mu}
=-\frac{b_0}{16\pi^2}g^3.
$$

This equation integrates to

$$
\frac{1}{g^2(\mu)}
=\frac{1}{g^2(\mu_0)}+\frac{b_0}{8\pi^2}\log\frac{\mu}{\mu_0}.
$$

Equivalently, for

$$
\alpha_g=\frac{g^2}{4\pi},
$$

we have

$$
\mu\frac{d\alpha_g}{d\mu}
=-\frac{b_0}{2\pi}\alpha_g^2+O(\alpha_g^3).
$$

If $b_0>0$, then $g(\mu)$ decreases as $\mu$ increases. The ultraviolet theory becomes weakly coupled.

One can trade the dimensionless coupling for a scale,

$$
\Lambda
=\mu\exp\left[-\frac{8\pi^2}{b_0g^2(\mu)}\right]
$$

at one loop. This is the first glimpse of dimensional transmutation. The next pages turn this running into the physics of asymptotic freedom and the emergence of scales such as $\Lambda_{\rm QCD}$.

## Screening versus anti-screening

The word “screening” is intuitive but slightly dangerous. The rigorous perturbative statement is the sign of $\beta(g)$. Still, the physical picture is useful.

Matter fields polarize the vacuum in a way analogous to dielectric screening. That contribution makes the effective charge smaller at long distances and larger at short distances. In the beta-function coefficient $b_0$, matter therefore subtracts.

Non-Abelian gauge bosons carry the charge of the gauge group. Their self-interactions produce an anti-screening effect that dominates in pure Yang–Mills theory and in QCD with not too many quark flavors. In $b_0$, this appears as

$$
+\frac{11}{3}C_A.
$$

Because $\beta(g)=-(b_0/16\pi^2)g^3$, a positive gauge contribution to $b_0$ means a negative contribution to $\beta(g)$.

This sign is the hinge on which QCD turns. Short-distance quarks and gluons can be treated perturbatively; long-distance hadrons cannot.

## Checks and special cases

### Abelian limit

For an Abelian gauge theory, there are no gauge-boson self-interactions and no interacting ghosts, so set

$$
C_A=0.
$$

For Dirac matter of charges $Q_i$ in units of $e$, the formula becomes

$$
\beta(e)=\frac{e^3}{16\pi^2}\frac{4}{3}\sum_iQ_i^2+O(e^5),
$$

which is the QED result

$$
\beta(e)=\frac{e^3}{12\pi^2}\sum_iQ_i^2+O(e^5).
$$

### Pure Yang–Mills

For pure $SU(N)$ Yang–Mills,

$$
\beta(g)=-\frac{11N}{48\pi^2}g^3+O(g^5).
$$

The theory is asymptotically free for all $N\geq2$.

### QCD

For $SU(3)$ with $n_f$ Dirac quarks,

$$
\beta(g_s)
=-\frac{g_s^3}{16\pi^2}\left(11-\frac{2}{3}n_f\right)+O(g_s^5).
$$

For the six quark flavors of the Standard Model, the one-loop coefficient above all thresholds is

$$
b_0=11-4=7.
$$

Below heavy-quark thresholds, the effective value of $n_f$ changes. Matching across thresholds is an EFT question, not a contradiction in the beta function.

### Supersymmetric comparison

For an $\mathcal N=1$ supersymmetric gauge theory, the matter and gaugino content changes the coefficient. In a common convention with chiral multiplets in representations $R_i$, the one-loop coefficient is

$$
b_0^{\mathcal N=1}=3C_A-\sum_iT(R_i).
$$

This is not the formula for an ordinary nonsupersymmetric gauge theory with only Dirac fermions and complex scalars. It is included here only as a warning: field content matters.

## Scheme dependence

The one-loop coefficient $b_0$ is universal. In mass-independent schemes, the two-loop coefficient is also universal for a fixed theory and coupling normalization. Starting at higher orders, beta-function coefficients become scheme dependent.

This does not make the running coupling meaningless. It means that $g(\mu)$ is a coordinate on theory space, not itself an observable. A change of scheme is a change of coordinate. Physical predictions are invariant when matching, running, matrix elements, and observables are treated consistently.

This is especially important in QCD, where different definitions of $\alpha_s$ are useful for different tasks: $\overline{\rm MS}$ running, lattice definitions, effective charges, potential schemes, and event-shape schemes all encode the same physics with different bookkeeping.

## Common pitfalls

**Forgetting the overall minus sign.** The coefficient $b_0$ is often quoted as positive for QCD, but the beta function is

$$
\beta(g)=-\frac{b_0}{16\pi^2}g^3+\cdots.
$$

Positive $b_0$ means the coupling decreases in the ultraviolet.

**Counting Dirac, Weyl, real, and complex fields inconsistently.** One Dirac fermion is two Weyl fermions. One complex scalar is two real scalars. Use one counting convention at a time.

**Confusing $C_A$, $C_F$, and $T(F)$.** For $SU(3)$, $C_A=3$, $C_F=4/3$, and $T(F)=1/2$. The one-loop beta function uses $C_A$ for the gauge contribution and $T(R)$ for matter-loop traces.

**Treating ghosts as optional.** Ghosts do not correspond to external physical particles, but they are essential internal fields in covariant gauges. Omitting them gives the wrong coefficient and violates unitarity/gauge consistency.

**Equating asymptotic freedom with confinement.** Asymptotic freedom is a perturbative ultraviolet result. Confinement is an infrared nonperturbative phenomenon. The first strongly motivates the second in QCD-like theories, but it does not prove it.

**Thinking the separate loop contributions are separately physical.** The clean physical result is the gauge-invariant coefficient $b_0$. The separation into gauge, ghost, and gauge-fixing-dependent pieces is a calculation artifact.

## Relations to other pages

This page is the non-Abelian counterpart of [QED Renormalization](/gauge-theories-standard-model/gauge-renormalization/qed-renormalization/). The Abelian beta function comes only from charged matter. The Yang–Mills beta function also receives the gauge and ghost contribution that produces asymptotic freedom.

The next page, [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/), interprets the sign of the beta function physically. [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/) explains how the running coupling creates a scale.

Later, [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) specializes this formula to the strong interaction, and [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/) connects it to the phenomenological coupling $\alpha_s(\mu)$.

## Research status

The one-loop Yang–Mills beta function is established. It is one of the cornerstone results of modern quantum field theory.

Active research concerns what happens beyond this first coefficient: higher-loop calculations, scheme transformations, conformal windows, chiral gauge theories, nonperturbative RG flows, lattice determinations, threshold matching in precision QCD, and the relation between perturbative asymptotic freedom and nonperturbative infrared phenomena.

## Exercises

### Exercise 1: QCD asymptotic freedom bound

For $SU(N_c)$ gauge theory with $n_f$ Dirac fermions in the fundamental representation, derive the condition for one-loop asymptotic freedom.

<details><summary><strong>Solution</strong></summary>

For the fundamental of $SU(N_c)$,

$$
C_A=N_c,
\qquad
T(F)=\frac12.
$$

Thus

$$
b_0=\frac{11}{3}N_c-\frac{4}{3}n_f\frac12
=\frac{11}{3}N_c-\frac{2}{3}n_f.
$$

Asymptotic freedom requires $b_0>0$, so

$$
\frac{11}{3}N_c-\frac{2}{3}n_f>0
\quad\Longrightarrow\quad
n_f<\frac{11}{2}N_c.
$$

For $SU(3)$, this gives $n_f<33/2$, so integer $n_f\leq16$.

</details>

### Exercise 2: Pure Yang–Mills running

Solve the one-loop RG equation for pure $SU(N)$ Yang–Mills between scales $\mu_0$ and $\mu$.

<details><summary><strong>Solution</strong></summary>

For pure $SU(N)$,

$$
b_0=\frac{11}{3}N.
$$

The one-loop equation is

$$
\mu\frac{dg}{d\mu}=-\frac{b_0}{16\pi^2}g^3.
$$

Equivalently,

$$
\frac{d}{d\log\mu}\frac{1}{g^2}
=\frac{b_0}{8\pi^2}.
$$

Integrating gives

$$
\frac{1}{g^2(\mu)}
=\frac{1}{g^2(\mu_0)}+\frac{11N}{24\pi^2}\log\frac{\mu}{\mu_0}.
$$

The inverse coupling grows with $\mu$, so the coupling decreases at high energy.

</details>

### Exercise 3: Dirac versus Weyl counting

Show that the Dirac-fermion matter term

$$
-\frac{4}{3}T(R)
$$

is equivalent to two Weyl fermions contributing

$$
-\frac{2}{3}T(R)
$$

each.

<details><summary><strong>Solution</strong></summary>

A Dirac fermion consists of two Weyl fermions in conjugate representations. For complex representations $R$ and $\bar R$,

$$
T(\bar R)=T(R).
$$

Thus two Weyl fermions contribute

$$
-\frac{2}{3}T(R)-\frac{2}{3}T(\bar R)
=-\frac{4}{3}T(R).
$$

This reproduces the Dirac formula.

</details>

### Exercise 4: Abelian check

Set $C_A=0$ and take $N_f$ Dirac fermions of charges $q_i=Q_i e$. Recover the one-loop QED beta function.

<details><summary><strong>Solution</strong></summary>

For $U(1)$, the adjoint self-interaction is absent, so $C_A=0$. The representation index is replaced by the charge squared,

$$
T(R_i)\rightarrow Q_i^2.
$$

Then

$$
b_0=-\frac{4}{3}\sum_iQ_i^2.
$$

Since

$$
\beta(e)=-\frac{b_0}{16\pi^2}e^3,
$$

we get

$$
\beta(e)=\frac{e^3}{12\pi^2}\sum_iQ_i^2,
$$

which is the QED result.

</details>

### Exercise 5: Scalars and loss of asymptotic freedom

Consider $SU(2)$ Yang–Mills theory with $n_s$ complex scalars in the fundamental representation and no fermions. For what values of $n_s$ is the one-loop theory asymptotically free?

<details><summary><strong>Solution</strong></summary>

For $SU(2)$,

$$
C_A=2,
\qquad
T(F)=\frac12.
$$

The coefficient is

$$
b_0=\frac{11}{3}(2)-\frac{1}{3}n_s\frac12
=\frac{22}{3}-\frac{n_s}{6}.
$$

Asymptotic freedom requires

$$
\frac{22}{3}-\frac{n_s}{6}>0.
$$

Multiplying by $6$ gives

$$
44-n_s>0.
$$

Therefore the one-loop condition is

$$
n_s<44.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§73 and 78, for the non-Abelian beta function and background-field gauge.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 26, for quantum Yang–Mills theory and the running coupling.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 17–18, for renormalization of gauge theories and RG methods.
- Coleman, *Aspects of Symmetry*, “Secret symmetry” and “Asymptotic freedom,” for the conceptual picture of gauge fields, ghosts, and asymptotic freedom.
- Wilson and Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the broader RG viewpoint linking field theory and critical phenomena.

## Version history

- **2026-06-18:** Initial polished draft for the Gauge Renormalization chapter.
