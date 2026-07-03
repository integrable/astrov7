---
title: "Yang–Mills Beta Function"
description: "A derivation-oriented explanation of the one-loop Yang–Mills beta function, gauge-boson antiscreening, matter screening, group factors, asymptotic freedom, and dimensional transmutation."
sidebar:
  label: "Yang–Mills Beta Function"
  order: 2
level: Graduate
status: "Polished draft"
source: "Gross and Wilczek 1973; Politzer 1973; Coleman 1985, asymptotic freedom lecture; Srednicki 2007, §§69–78; Schwartz 2014, ch. 26; Weinberg Vol. II, chs. 15–18; Polyakov 1987, ch. 2."
topics:
  - Yang–Mills beta function
  - asymptotic freedom
  - gauge-boson antiscreening
  - matter screening
  - background-field method
  - QCD running
canonicalTopics:
  - yang-mills-beta-function
  - asymptotic-freedom
  - non-abelian-gauge-theory
researchStatus:
  established:
    - "The one-loop Yang–Mills beta function and the asymptotic freedom of non-Abelian gauge theories with sufficiently little matter are standard and experimentally central QFT results."
  active:
    - "Nonperturbative confinement, mass-gap formation, chiral gauge theories, high-order precision running, and gauge theories near conformal windows remain active research topics beyond the first one-loop explanation."
---

## Summary

The **Yang–Mills beta function** is the place where non-Abelian gauge theory first reveals that it is not just QED with group labels. In the conventions of this volume,

$$
\beta_g(g)\equiv \left.\mu\frac{dg}{d\mu}\right|_{g_0,\text{bare fields fixed}}.
$$

For a simple gauge group $G$ with $n_f$ Dirac fermions in representation $R$, the one-loop result is

$$
\boxed{
\beta_g=-\frac{g^3}{16\pi^2}
\left[\frac{11}{3}C_A-\frac{4}{3}T(R)n_f\right]+O(g^5)
}.
$$

Here

$$
f^{acd}f^{bcd}=C_A\delta^{ab},
\qquad
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}.
$$

For $SU(N)$ with $n_f$ Dirac fermions in the fundamental representation,

$$
C_A=N,
\qquad
T(F)=\frac12,
$$

so

$$
\boxed{
\beta_g=-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N-\frac{2}{3}n_f\right)+O(g^5).
}
$$

For pure Yang–Mills theory, $n_f=0$, and

$$
\beta_g=-\frac{11C_A}{3}\frac{g^3}{16\pi^2}+O(g^5).
$$

The negative sign means that the coupling decreases toward the ultraviolet. This is **asymptotic freedom**.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Comparison of one-loop gauge beta-function signs: QED matter screening gives positive beta while Yang–Mills gauge and ghost antiscreening can dominate matter screening and give negative beta](/figures/renormalization-rg-eft/gauge-beta-function-signs.svg)

<figcaption>

At one loop, Abelian QED has charged-matter screening and $\beta_e>0$. Non-Abelian Yang–Mills theory has matter screening too, but the gauge and ghost sector contributes the opposite sign. When $11C_A/3$ dominates $4T(R)n_f/3$, the beta function is negative and the theory is asymptotically free.

</figcaption>
</figure>

:::note[The most important lesson]
The non-Abelian gauge field carries its own gauge charge. Gauge boson self-interactions, together with the ghost contribution required by gauge fixing, produce antiscreening. This is the sign reversal that makes QCD possible as a weakly coupled theory at short distances.
:::

## Prerequisites

You should know [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/).

You should also know the basic Yang–Mills Lagrangian, gauge fixing, Faddeev–Popov ghosts, and group-theory notation. This page explains the RG result and its meaning; it is not a first introduction to non-Abelian gauge theory.

## Core idea

In QED, the photon is neutral. At one loop, the running of the electric charge comes from charged matter vacuum polarization. Charged matter screens.

In Yang–Mills theory, the gauge bosons themselves carry non-Abelian gauge charge. The gauge field can polarize the vacuum. The ghost fields introduced by gauge fixing are not physical particles, but their loops are required to subtract unphysical gauge polarizations and preserve gauge invariance. The gauge-plus-ghost sector produces a contribution with the opposite sign from matter.

The one-loop competition is

$$
\beta_g=-\frac{g^3}{16\pi^2}
\left[
\underbrace{\frac{11}{3}C_A}_{\text{gauge and ghost antiscreening}}
-
\underbrace{\frac{4}{3}T(R)n_f}_{\text{Dirac matter screening}}
\right]+O(g^5).
$$

If the bracket is positive, the beta function is negative. Then

$$
\mu\uparrow
\quad\Longrightarrow\quad
g(\mu)\downarrow.
$$

The theory becomes weakly coupled at short distances and strongly coupled at long distances. This is why high-energy QCD can be treated perturbatively while low-energy QCD requires nonperturbative methods.

## Setup and conventions

Let $G$ be a compact simple gauge group with Lie algebra generators $T^a_R$ in representation $R$:

$$
[T_R^a,T_R^b]=if^{abc}T_R^c.
$$

The group-theory invariants used on this page are

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
$$

and

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

For $SU(N)$,

$$
C_A=N,
\qquad
T(F)=\frac12,
\qquad
C_F=\frac{N^2-1}{2N}.
$$

The Yang–Mills field strength is

$$
F^a_{\mu\nu}
=\partial_\mu A^a_\nu-\partial_\nu A^a_\mu
+g f^{abc}A^b_\mu A^c_\nu.
$$

The gauge-field part of the Lagrangian is

$$
\mathcal L_{\mathrm{YM}}
=-\frac14 F^a_{\mu\nu}F^{a\mu\nu}.
$$

For Dirac fermions in representation $R$,

$$
\mathcal L_\psi
=\bar\psi\left(i\gamma^\mu D_\mu-m\right)\psi,
\qquad
D_\mu=\partial_\mu+i g A^a_\mu T_R^a.
$$

We use dimensional regularization with

$$
d=4-2\epsilon,
$$

and define the renormalized coupling by

$$
g_0=\mu^\epsilon Z_g g.
$$

The sign convention for the beta function is

$$
\beta_g=\mu\frac{dg}{d\mu}\bigg|_{g_0}.
$$

With this convention, asymptotic freedom means $\beta_g<0$ at weak coupling.

## The one-loop result

For $n_f$ Dirac fermions in representation $R$, the one-loop beta function is

$$
\beta_g=-\frac{b_0}{16\pi^2}g^3+O(g^5),
$$

where

$$
\boxed{
 b_0=\frac{11}{3}C_A-\frac{4}{3}T(R)n_f.
}
$$

For several fermion representations $R_f$, this generalizes to

$$
 b_0=\frac{11}{3}C_A-\frac{4}{3}\sum_f T(R_f),
$$

where the sum is over active Dirac fermions. If there are complex scalar fields in representations $R_s$, the one-loop coefficient becomes

$$
 b_0=\frac{11}{3}C_A-\frac{4}{3}\sum_f T(R_f)-\frac{1}{3}\sum_s T(R_s),
$$

for active complex scalars. Equivalently, a real scalar contributes half as much as a complex scalar.

The sign is controlled by $b_0$:

| Condition | Weak-coupling UV behavior |
|---|---|
| $b_0>0$ | $\beta_g<0$, asymptotically free |
| $b_0=0$ | one-loop term vanishes; higher orders decide |
| $b_0<0$ | $\beta_g>0$, coupling grows toward the UV at one loop |

For $SU(N)$ with $n_f$ Dirac fundamental fermions,

$$
 b_0=\frac{11}{3}N-\frac{2}{3}n_f.
$$

Thus asymptotic freedom at one loop requires

$$
 n_f<\frac{11}{2}N.
$$

For QCD with $N=3$,

$$
 b_0=11-\frac{2}{3}n_f.
$$

## Where the sign comes from

A full one-loop calculation includes gauge-boson loops, ghost loops, matter loops, and counterterm diagrams. Individual pieces can depend on the gauge choice and on the organization of the calculation. The sum does not.

The robust decomposition of the coefficient is

$$
 b_0
=
\underbrace{\frac{11}{3}C_A}_{\text{gauge and ghost sector}}
-
\underbrace{\frac{4}{3}T(R)n_f}_{\text{Dirac matter sector}}.
$$

The matter term has the same physical sign as QED: matter screens gauge charge. The gauge-plus-ghost term has the opposite sign: it antiscreens. Non-Abelian gauge bosons carry charge and interact with each other, so the vacuum responds differently from an ordinary dielectric.

A useful physical summary is:

$$
\text{matter fields screen},
\qquad
\text{non-Abelian gauge fields antiscreen}.
$$

One should not overinterpret this as a literal classical medium picture. It is an intuition for the sign of a quantum beta function. The gauge-invariant statement is the sign of $b_0$.

## Background-field method viewpoint

The **background-field method** is a clean way to compute the gauge beta function because it preserves manifest gauge invariance with respect to a background field. Split

$$
A_\mu=\bar A_\mu+a_\mu,
$$

where $\bar A_\mu$ is a background gauge field and $a_\mu$ is the quantum fluctuation integrated over in the path integral. The one-loop effective action for $\bar A_\mu$ contains a divergent term proportional to

$$
\int d^d x\,\bar F^a_{\mu\nu}\bar F^{a\mu\nu}.
$$

Gauge invariance forces this form. The divergent coefficient determines the renormalization of the background gauge kinetic term, and therefore the running of $g$.

In background-field gauge, the Ward-like identity is especially simple:

$$
Z_g Z_{\bar A}^{1/2}=1.
$$

This resembles the Abelian relation $Z_e=Z_A^{-1/2}$, but the calculation producing $Z_{\bar A}$ includes non-Abelian gauge and ghost loops.

The background-field method is not the only way to calculate $b_0$. It is conceptually valuable because it makes the gauge-invariant structure of the answer visible.

## Running coupling and asymptotic freedom

Write

$$
\alpha_g\equiv \frac{g^2}{4\pi}.
$$

From

$$
\beta_g=-\frac{b_0}{16\pi^2}g^3,
$$

we get

$$
\beta_{\alpha_g}
=\mu\frac{d\alpha_g}{d\mu}
=-\frac{b_0}{2\pi}\alpha_g^2+O(\alpha_g^3).
$$

At one loop,

$$
\frac{d}{d\log\mu}\left(\frac{1}{\alpha_g}\right)
=\frac{b_0}{2\pi}.
$$

Therefore

$$
\frac{1}{\alpha_g(\mu)}
=
\frac{1}{\alpha_g(\mu_0)}
+\frac{b_0}{2\pi}\log\frac{\mu}{\mu_0}.
$$

If $b_0>0$, then $1/\alpha_g$ grows in the UV, so $\alpha_g$ decreases:

$$
\alpha_g(\mu)
=
\frac{\alpha_g(\mu_0)}{1+\frac{b_0\alpha_g(\mu_0)}{2\pi}\log(\mu/\mu_0)}.
$$

This is asymptotic freedom. It is a UV statement. The same formula also says that the coupling grows toward the IR and eventually leaves the perturbative regime.

## Dimensional transmutation

For $b_0>0$, the one-loop solution can be rewritten in terms of an RG-invariant scale:

$$
\Lambda
=
\mu\exp\left[-\frac{8\pi^2}{b_0 g^2(\mu)}\right].
$$

Equivalently,

$$
\alpha_g(\mu)
=\frac{2\pi}{b_0\log(\mu/\Lambda)}.
$$

This is **dimensional transmutation**. A dimensionless coupling at a reference scale is traded for a dimensionful scale $\Lambda$. In QCD this scale is conventionally related to $\Lambda_{\mathrm{QCD}}$, with scheme and threshold conventions understood.

The equation

$$
\alpha_s(\mu)
\sim \frac{1}{\log(\mu/\Lambda_{\mathrm{QCD}})}
$$

explains why high-energy scattering can be perturbative while hadron physics at scales near $\Lambda_{\mathrm{QCD}}$ is strongly coupled.

## Relation to QED

The QED beta function can be read as the Abelian limit where there are no gauge-boson self-interactions:

$$
C_A=0.
$$

Then only charged matter contributes, and the sign is screening:

$$
\beta_e>0.
$$

In non-Abelian theory, the self-interacting gauge sector contributes

$$
+\frac{11}{3}C_A
$$

to $b_0$, and because the beta function is written as $-b_0g^3/(16\pi^2)$, this produces a negative contribution to $\beta_g$.

This is why the sign difference is not a minor convention. It is the dynamical distinction between a neutral photon and gauge bosons that themselves carry non-Abelian charge.

## Matter content and the conformal-window warning

At one loop, adding enough matter can destroy asymptotic freedom. For $SU(N)$ with $n_f$ fundamental Dirac fermions,

$$
 n_f<\frac{11}{2}N
$$

is required for $b_0>0$.

Near the upper edge of this range, higher-loop terms may produce weakly coupled infrared fixed points in some theories. This is the perturbative beginning of the Banks–Zaks idea. Farther away from weak coupling, the question of whether a theory confines, breaks chiral symmetry, flows to an interacting conformal field theory, or realizes more exotic behavior is nonperturbative.

So the one-loop coefficient is powerful but not omniscient. It identifies the UV direction of the flow at weak coupling. It does not by itself solve the infrared theory.

## Gauge dependence and universality

The one-loop coefficient $b_0$ is universal under ordinary scheme changes. Individual diagrams are not. Gauge-boson, ghost, and matter-loop subpieces may look different in different gauges, but the total coefficient is gauge independent.

Changing the renormalization scheme changes higher-order coefficients but not the leading one-loop coefficient for a single gauge coupling under ordinary analytic coupling redefinitions. Therefore the statement

$$
 b_0>0
$$

is a scheme-independent weak-coupling statement.

The coupling $g(\mu)$ itself is still scheme dependent. A physical prediction requires a consistently defined observable, matching conditions across thresholds, and matrix elements or amplitudes computed in the same scheme.

## Common pitfalls

**Thinking ghosts are optional.** Ghosts remove unphysical gauge degrees of freedom in covariant gauges. Their contribution is required for the gauge-invariant value of $b_0$.

**Saying gauge bosons literally form a classical antiscreening medium.** The screening language is useful, but the precise statement is the sign of the beta function computed in a gauge-invariant renormalization framework.

**Confusing asymptotic freedom with confinement.** Asymptotic freedom is perturbative and ultraviolet. Confinement is nonperturbative and infrared. QCD has both, but one is not a proof of the other.

**Forgetting representation factors.** Matter does not contribute only by counting fields. It contributes weighted by $T(R)$.

**Forgetting thresholds.** Heavy quarks or other heavy fields change the beta function only in the EFT where they are active. Across a threshold, one matches and then runs with a different $b_0$.

**Comparing $\beta_g$, $\beta_\alpha$, and $\beta_{1/g^2}$ without translating signs.** The same physics can look like a negative beta function for $g$, a negative beta function for $\alpha_g$, or a positive slope for $1/g^2$.

## Relations to other pages

This page follows [QED Beta Function](/renormalization-rg-eft/gauge-theories-and-rg/qed-beta-function/) and supplies the sign reversal that drives non-Abelian asymptotic freedom. The next natural page is [QCD Running Coupling](/renormalization-rg-eft/gauge-theories-and-rg/qcd-running-coupling/), where the general formula is applied to $SU(3)$ with flavor thresholds and phenomenological conventions.

For the general RG technology, see [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/).

For the gauge-identity structure, continue to [Background-Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/), [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/), [Slavnov–Taylor Identities Preview](/renormalization-rg-eft/gauge-theories-and-rg/slavnov-taylor-identities-preview/), and [BRST and Renormalization Preview](/renormalization-rg-eft/gauge-theories-and-rg/brst-and-renormalization-preview/).

The nonperturbative consequences belong in the nonperturbative QFT and gauge-theory volumes: Wilson loops, confinement, chiral symmetry breaking, mass gaps, and lattice definitions go beyond what a one-loop beta function can prove.

## Research status

The one-loop Yang–Mills beta function is settled. Its negative sign for pure non-Abelian gauge theory is one of the foundational discoveries behind QCD.

What remains active is not the one-loop formula itself, but what lies around and beyond it: precision multi-loop running, threshold matching, conformal-window dynamics, nonperturbative mass gaps, confinement, chiral gauge theories, lattice definitions, and the interplay of gauge dynamics with generalized symmetries and anomalies.

The conceptual status is therefore mixed in the healthy way QFT often is: the UV perturbative result is exact as a weak-coupling expansion coefficient, while many infrared implications require genuinely nonperturbative tools.

## Exercises

### Exercise 1: Asymptotic freedom bound for fundamental matter

For an $SU(N)$ gauge theory with $n_f$ Dirac fermions in the fundamental representation, show that one-loop asymptotic freedom requires

$$
n_f<\frac{11}{2}N.
$$

<details><summary><strong>Solution</strong></summary>

For $SU(N)$,

$$
C_A=N,
\qquad
T(F)=\frac12.
$$

The one-loop coefficient is

$$
b_0=\frac{11}{3}C_A-\frac{4}{3}T(F)n_f
=\frac{11}{3}N-\frac{4}{3}\frac12 n_f
=\frac{11}{3}N-\frac{2}{3}n_f.
$$

Asymptotic freedom requires $b_0>0$, so

$$
\frac{11}{3}N-\frac{2}{3}n_f>0.
$$

Multiplying by $3/2$ gives

$$
\frac{11}{2}N-n_f>0,
$$

or

$$
n_f<\frac{11}{2}N.
$$

</details>

### Exercise 2: Running of the inverse coupling

Starting from

$$
\beta_g=-\frac{b_0}{16\pi^2}g^3,
$$

show that

$$
\frac{d}{d\log\mu}\left(\frac{1}{g^2}\right)=\frac{b_0}{8\pi^2}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate $g^{-2}$:

$$
\frac{d}{d\log\mu}\left(g^{-2}\right)
=-2g^{-3}\frac{dg}{d\log\mu}
=-2g^{-3}\beta_g.
$$

Substituting the beta function gives

$$
-2g^{-3}\left(-\frac{b_0}{16\pi^2}g^3\right)
=\frac{b_0}{8\pi^2}.
$$

Therefore

$$
\frac{d}{d\log\mu}\left(\frac{1}{g^2}\right)=\frac{b_0}{8\pi^2}.
$$

</details>

### Exercise 3: One-loop RG-invariant scale

Assume $b_0>0$. Show that

$$
\Lambda=\mu\exp\left[-\frac{8\pi^2}{b_0g^2(\mu)}\right]
$$

is independent of $\mu$ at one loop.

<details><summary><strong>Solution</strong></summary>

Take the logarithm:

$$
\log\Lambda=\log\mu-\frac{8\pi^2}{b_0g^2(\mu)}.
$$

Differentiate with respect to $\log\mu$:

$$
\frac{d\log\Lambda}{d\log\mu}
=1-\frac{8\pi^2}{b_0}
\frac{d}{d\log\mu}\left(\frac{1}{g^2}\right).
$$

Using Exercise 2,

$$
\frac{d}{d\log\mu}\left(\frac{1}{g^2}\right)=\frac{b_0}{8\pi^2}.
$$

Therefore

$$
\frac{d\log\Lambda}{d\log\mu}
=1-\frac{8\pi^2}{b_0}\frac{b_0}{8\pi^2}=0.
$$

So $\Lambda$ is RG invariant at this order.

</details>

### Exercise 4: Matter screening versus gauge antiscreening

For $SU(3)$ with $n_f$ Dirac fundamental fermions, compute $b_0$ for $n_f=0$, $n_f=6$, and $n_f=17$. Interpret the sign.

<details><summary><strong>Solution</strong></summary>

For $SU(3)$,

$$
b_0=11-\frac{2}{3}n_f.
$$

For $n_f=0$,

$$
b_0=11>0,
$$

so the theory is asymptotically free.

For $n_f=6$,

$$
b_0=11-4=7>0,
$$

so the theory is still asymptotically free at one loop.

For $n_f=17$,

$$
b_0=11-\frac{34}{3}=-\frac{1}{3}<0.
$$

At one loop the beta function is then positive, so the weak-coupling flow is not asymptotically free. Matter screening has overwhelmed gauge antiscreening.

</details>

## References

- David Gross and Frank Wilczek, "Ultraviolet Behavior of Non-Abelian Gauge Theories," *Physical Review Letters* **30** (1973) 1343–1346.
- H. David Politzer, "Reliable Perturbative Results for Strong Interactions?" *Physical Review Letters* **30** (1973) 1346–1349.
- Sidney Coleman, *Aspects of Symmetry*, especially the lecture on asymptotic freedom.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on non-Abelian gauge theory, beta functions, BRST symmetry, and background-field gauge.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapter on quantum Yang–Mills theory and running coupling.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapters on non-Abelian gauge theories, gauge-theory renormalization, and RG methods.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapter on asymptotic freedom and the renormalization group.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional and RG treatments of gauge theories and critical behavior.

## Version history

- 2026-06-18: First polished draft. Added one-loop Yang–Mills beta function, group conventions, sign interpretation, running-coupling solution, dimensional transmutation, and exercises.
