---
title: "Mean-Field Theory"
description: "The saddle-point approximation to Landau–Ginzburg theory, its critical exponents, its domain of validity, and the Ginzburg criterion."
sidebar:
  label: "Mean-Field Theory"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§2–5; Zinn-Justin 2021, critical phenomena chapters; Altland and Simons 2023, ch. 6; Schwartz 2014, chs. 21–23."
topics:
  - mean-field theory
  - Landau theory
  - saddle point approximation
  - critical exponents
  - Ginzburg criterion
  - upper critical dimension
canonicalTopics:
  - mean-field-theory
  - landau-theory
  - saddle-point-approximation
  - ginzburg-criterion
researchStatus:
  established:
    - "Mean-field theory is the saddle-point approximation to a local order-parameter functional and gives the exact leading critical exponents above the upper critical dimension."
  active:
    - "Modern work refines mean-field ideas in long-range systems, large-N limits, dynamical mean-field theory, holography, glassy systems, networks, nonequilibrium criticality, and systems with dangerously irrelevant variables."
---

## Summary

**Mean-field theory** is the saddle-point approximation to the Landau–Ginzburg functional. For a single scalar order parameter with $Z_2$ symmetry, write the uniform free-energy density as

$$
f(m)=\frac12 r m^2+\frac{u}{4!}m^4-hm,
\qquad u>0.
$$

The mean-field order parameter $m$ solves

$$
\frac{\partial f}{\partial m}=rm+\frac{u}{6}m^3-h=0.
$$

At zero external field,

$$
m=0\quad(r>0),
$$

while below the transition,

$$
m=\pm\sqrt{\frac{-6r}{u}}\quad(r<0).
$$

This gives the classical magnetization exponent

$$
\beta_{\text{MF}}=\frac12.
$$

Mean-field theory is not a random approximation. It is the zeroth-order description of the Gaussian fixed point, plus the nonlinear term needed to stabilize the ordered phase. It becomes exact for leading critical exponents above the upper critical dimension $d_c=4$ for short-range scalar $\phi^4$ theory, receives logarithmic corrections at $d=4$, and is modified by fluctuations below four dimensions.

:::note[Mean field is a saddle, not a belief system]
Mean-field theory assumes that the dominant configurations are nearly uniform and that fluctuations around the saddle are small. It is powerful when that assumption is true and misleading when long-wavelength fluctuations dominate the critical region.
:::

## Prerequisites

You should know [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/), [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), and [Crossover and Dangerously Irrelevant Operators](/renormalization-rg-eft/fixed-points-critical-phenomena/crossover-and-dangerously-irrelevant-operators/).

## Core idea

A statistical field theory averages over all configurations:

$$
Z=\int\mathcal D\phi\,e^{-S[\phi]}.
$$

Mean-field theory replaces this functional integral by its dominant saddle point:

$$
Z\approx e^{-S[\phi_{\text{cl}}]},
\qquad
\left.\frac{\delta S}{\delta\phi(x)}\right|_{\phi=\phi_{\text{cl}}}=0.
$$

For a translationally invariant phase, the saddle is constant,

$$
\phi_{\text{cl}}(x)=m,
$$

and the field equation becomes an algebraic equation for the order parameter. This is why mean-field theory is simple: it turns an infinite-dimensional fluctuation problem into minimization of a function.

The price is that it discards the fluctuations that become most important at a continuous transition. The renormalization group tells us exactly when this price is affordable.

## Setup and conventions

This page uses Euclidean statistical notation. The Landau–Ginzburg functional is

$$
S[\phi]=\int d^d x\left[
\frac12 Z(\nabla\phi)^2+V(\phi)-h\phi
\right],
$$

where

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4+\frac{v}{6!}\phi^6+\cdots.
$$

For the ordinary Ising-like transition, one keeps $u>0$ and ignores higher powers near the transition. The external source $h$ is conjugate to the order parameter. The parameter $r$ is proportional to the reduced temperature near the critical point:

$$
r=a(T-T_c)+\cdots,
\qquad a>0,
$$

after nonuniversal normalization choices.

The standard critical-exponent notation is:

| Exponent | Meaning |
|---|---|
| $\alpha$ | singular specific heat, $C\sim |t|^{-\alpha}$ |
| $\beta$ | order parameter, $m\sim (-t)^\beta$ for $t<0$ |
| $\gamma$ | susceptibility, $\chi\sim |t|^{-\gamma}$ |
| $\delta$ | critical isotherm, $m\sim h^{1/\delta}$ at $t=0$ |
| $\nu$ | correlation length, $\xi\sim |t|^{-\nu}$ |
| $\eta$ | anomalous two-point decay at criticality |

Here $t=(T-T_c)/T_c$.

## Saddle-point equation

The uniform mean-field free-energy density is

$$
f(m)=\frac12 r m^2+\frac{u}{4!}m^4-hm.
$$

The saddle equation is

$$
0=\frac{\partial f}{\partial m}
=rm+\frac{u}{6}m^3-h.
$$

At $h=0$,

$$
m\left(r+\frac{u}{6}m^2\right)=0.
$$

The stationary points are

$$
m=0,
\qquad
m^2=-\frac{6r}{u}.
$$

For $r>0$, only $m=0$ is stable. For $r<0$, the symmetric point $m=0$ is unstable and the stable minima are

$$
m_\pm=\pm\sqrt{\frac{-6r}{u}}.
$$

Thus below the transition,

$$
|m|\propto (-r)^{1/2},
$$

so

$$
\beta_{\text{MF}}=\frac12.
$$

## Susceptibility

The static susceptibility is the response of the order parameter to the source:

$$
\chi=\left.\frac{\partial m}{\partial h}\right|_{h=0}.
$$

Differentiate

$$
h=rm+\frac{u}{6}m^3
$$

to obtain

$$
\frac{\partial h}{\partial m}=r+\frac{u}{2}m^2.
$$

Therefore

$$
\chi=\frac{1}{r+\frac{u}{2}m^2}.
$$

Above the transition, $m=0$, so

$$
\chi_+=\frac{1}{r}
\quad (r>0).
$$

Below the transition, $m^2=-6r/u$, so

$$
\chi_-=\frac{1}{r+\frac{u}{2}(-6r/u)}
=\frac{1}{-2r}
\quad (r<0).
$$

On both sides,

$$
\chi\sim |r|^{-1},
$$

so

$$
\gamma_{\text{MF}}=1.
$$

The amplitude ratio is

$$
\frac{\chi_+}{\chi_-}=2.
$$

This ratio is a useful mean-field check, not the exact three-dimensional Ising value.

## Critical isotherm

At the critical temperature, $r=0$, the saddle equation becomes

$$
h=\frac{u}{6}m^3.
$$

Thus

$$
m\propto h^{1/3},
$$

and

$$
\delta_{\text{MF}}=3.
$$

This exponent follows from the quartic stabilization of the Landau potential. If the quartic term is tuned away and the leading stabilizing term is $\phi^6$, one obtains tricritical mean-field exponents instead.

## Correlation length and eta

Expand around the uniform saddle:

$$
\phi(x)=m+\varphi(x).
$$

The quadratic fluctuation action is

$$
S^{(2)}[\varphi]
=
\frac12\int d^d x\left[
Z(\nabla\varphi)^2+M^2\varphi^2
\right],
$$

where

$$
M^2=V''(m)=r+\frac{u}{2}m^2.
$$

The Gaussian two-point function is

$$
G(k)=\frac{1}{Zk^2+M^2}.
$$

Therefore

$$
\xi=\sqrt{\frac{Z}{M^2}}.
$$

Above the transition, $M^2=r$; below it, $M^2=-2r$. Hence

$$
\xi\sim |r|^{-1/2},
\qquad
\nu_{\text{MF}}=\frac12.
$$

At criticality, $M^2=0$, so

$$
G(k)=\frac{1}{Zk^2},
$$

and

$$
G(x)\sim \frac{1}{|x|^{d-2}}.
$$

Therefore

$$
\eta_{\text{MF}}=0.
$$

## Specific heat

At $h=0$, the minimum free-energy density is

$$
f_{\min}=0\quad(r>0),
$$

and for $r<0$,

$$
f_{\min}
=\frac12 r\left(\frac{-6r}{u}\right)
+\frac{u}{24}\left(\frac{36r^2}{u^2}\right)
=-\frac{3r^2}{2u}.
$$

Thus the singular free energy scales as

$$
f_{\text{sing}}\sim r^2.
$$

The specific heat is a second temperature derivative of the free energy, so mean-field theory gives a finite jump rather than a power-law divergence:

$$
\alpha_{\text{MF}}=0.
$$

The value $\alpha=0$ needs context: it may mean a jump, a logarithm, or a weak power depending on the theory.

## The mean-field exponent table

For the ordinary scalar $\phi^4$ transition, the mean-field exponents are:

| Exponent | Mean-field value | Quick origin |
|---|---:|---|
| $\alpha$ | $0$ | $f_{\text{sing}}\sim r^2$ |
| $\beta$ | $1/2$ | $m\sim (-r)^{1/2}$ |
| $\gamma$ | $1$ | $\chi\sim |r|^{-1}$ |
| $\delta$ | $3$ | $h\sim m^3$ at $r=0$ |
| $\nu$ | $1/2$ | $\xi\sim M^{-1}\sim |r|^{-1/2}$ |
| $\eta$ | $0$ | $G(k)\sim k^{-2}$ at criticality |

They obey

$$
\alpha+2\beta+\gamma=2,
$$

and

$$
\gamma=\beta(\delta-1).
$$

But hyperscaling,

$$
2-\alpha=d\nu,
$$

selects $d=4$ when the mean-field values are inserted. This is the first warning that hyperscaling fails above the upper critical dimension.

## The Ginzburg criterion

Mean-field theory is reliable when fluctuations inside a correlation volume are small compared with the square of the order parameter. A quick estimate compares

$$
\langle \varphi^2\rangle_\xi
\sim
\int_{|k|\lesssim \xi^{-1}}\frac{d^d k}{(2\pi)^d}\frac{1}{k^2+\xi^{-2}}
\sim
\xi^{2-d}
$$

with

$$
m^2\sim |r|/u.
$$

Using

$$
\xi\sim |r|^{-1/2},
$$

the ratio scales as

$$
\frac{\langle\varphi^2\rangle_\xi}{m^2}
\sim
u\,|r|^{(d-4)/2}
$$

up to nonuniversal constants.

As $r\to0$:

| Dimension | Fluctuation ratio | Mean-field verdict |
|---:|---|---|
| $d>4$ | goes to zero | asymptotically valid |
| $d=4$ | marginal | logarithmic corrections |
| $d<4$ | grows | fails close enough to criticality |

This is the Ginzburg criterion and the physical meaning of the upper critical dimension.

## Why mean field often works anyway

Mean-field theory often gives a good first picture even when it does not give exact exponents. It correctly identifies possible phases and broken symmetries in many ordinary transitions. Away from the asymptotic critical region, a saddle-point or Gaussian approximation can be quantitatively useful. Long-range interactions, high spatial dimension, large coordination number, and large-$N$ limits can suppress fluctuations. And mean-field theory provides the starting point for systematic improvements: Gaussian fluctuations, loop expansions, large-$N$ methods, RG, variational approximations, and self-consistent approximations.

## Dangerous irrelevance above four dimensions

For $d>4$, the quartic coupling $u$ is irrelevant at the Gaussian fixed point. But the ordered phase still needs $u>0$ for stability, since

$$
V(m)=\frac12 r m^2
$$

is unstable for $r<0$. The quartic coupling is irrelevant for the fixed-point flow but essential for some ordered-phase observables.

This is the classic dangerous-irrelevance caveat. It explains why mean-field exponents can hold while naive hyperscaling fails above $d_c=4$.

## What mean field gets right and wrong

Mean-field theory usually gets the **order-parameter logic** right. It identifies the symmetry, the candidate phases, the conjugate source, and the local stability conditions. It is also a good first approximation far from criticality, where the correlation length is not large and fluctuations are not coherently organized over many microscopic spacings.

Mean-field theory usually gets the **critical singularities** wrong below the upper critical dimension. Close to criticality the low-momentum modes become strongly populated, and the saddle is surrounded by fluctuations whose correlations extend over the same scale as the system being measured. The problem is not that the polynomial potential was a silly idea. The problem is that minimizing it is not enough.

The renormalization-group refinement is therefore not:

$$
\text{throw away Landau theory}.
$$

It is:

$$
\text{keep the local functional, but let fluctuations renormalize its couplings and operator dimensions}.
$$

This is why the Landau–Ginzburg-Wilson framework is more durable than mean-field exponents. The functional form is the right local language; the saddle-point exponents are only the Gaussian approximation to its critical behavior.

## Common pitfalls

**Thinking mean field means no interactions.** Mean-field theory can include nonlinear terms such as $u m^4$. It neglects fluctuations around the saddle, not the nonlinear potential itself.

**Setting $u=0$ above four dimensions in every formula.** The quartic coupling is irrelevant at the Gaussian fixed point for $d>4$, but it is dangerously irrelevant for the ordered phase.

**Treating hyperscaling as universally valid.** Hyperscaling fails above the upper critical dimension because the singular free energy is not governed by a single correlation-volume estimate.

**Using mean-field exponents in three dimensions without warning.** Three-dimensional Ising exponents are not mean-field exponents. The anomalous dimension is small, but $\nu$, $\beta$, and $\gamma$ receive important corrections.

**Forgetting the limits of scalar Landau theory.** Gauge constraints, topological order, disorder, long-range forces, and deconfined criticality can require different variables or different field theories.

## Relations to other pages

This page is the saddle-point counterpart to [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/). It uses the Landau–Ginzburg functional introduced in [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/) and explains the zeroth-order exponent values corrected by [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/).

For the scaling relations among the exponents, see [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/). For the role of dangerously irrelevant variables, see [Crossover and Dangerously Irrelevant Operators](/renormalization-rg-eft/fixed-points-critical-phenomena/crossover-and-dangerously-irrelevant-operators/).

## Research status

Mean-field theory is fully established as the saddle-point approximation to statistical field theory and as the exact leading critical theory above the upper critical dimension in ordinary short-range scalar models. Its modern descendants are everywhere: large-$N$ saddle points, dynamical mean-field theory, Hartree–Fock theory, Gross–Pitaevskii theory, BCS theory, mean-field spin glasses, and holographic classical-gravity limits.

The active questions are about controlled extensions: fluctuation corrections, finite-size scaling above $d_c$, long-range interactions, disordered systems, nonequilibrium transitions, conservation laws, and mean-field-like behavior in complex networks or effectively high-connectivity systems.

## Exercises

### Exercise 1: Magnetization exponent

At $h=0$, minimize

$$
f(m)=\frac12 r m^2+\frac{u}{4!}m^4,
\qquad u>0.
$$

Find the stable minima for $r>0$ and $r<0$, and derive $\beta_{\text{MF}}$.

<details><summary><strong>Solution</strong></summary>

The saddle equation is

$$
0=\frac{\partial f}{\partial m}
=rm+\frac{u}{6}m^3
=m\left(r+\frac{u}{6}m^2\right).
$$

For $r>0$, the stable solution is $m=0$. For $r<0$, the stable solutions are

$$
m=\pm\sqrt{\frac{-6r}{u}}.
$$

Thus

$$
|m|\sim (-r)^{1/2},
$$

so

$$
\beta_{\text{MF}}=\frac12.
$$

</details>

### Exercise 2: Susceptibility amplitudes

Use

$$
h=rm+\frac{u}{6}m^3
$$

to compute the susceptibility above and below the transition at $h=0$. Show that $\chi_+/\chi_-=2$.

<details><summary><strong>Solution</strong></summary>

Differentiate with respect to $m$:

$$
\frac{\partial h}{\partial m}=r+\frac{u}{2}m^2.
$$

Therefore

$$
\chi=\frac{1}{r+\frac{u}{2}m^2}.
$$

For $r>0$, $m=0$, so $\chi_+=1/r$. For $r<0$, $m^2=-6r/u$, so

$$
\chi_-=\frac{1}{r-3r}=\frac{1}{-2r}.
$$

Thus $\chi_+/\chi_-=2$.

</details>

### Exercise 3: Hyperscaling check

Insert $\alpha=0$ and $\nu=1/2$ into

$$
2-\alpha=d\nu.
$$

What dimension does it select?

<details><summary><strong>Solution</strong></summary>

The relation becomes

$$
2=d\cdot\frac12,
$$

so

$$
d=4.
$$

Thus the mean-field exponent set satisfies hyperscaling only at the upper critical dimension. Above $d=4$, mean-field exponents hold for ordinary short-range scalar criticality, but hyperscaling fails because the quartic coupling is dangerously irrelevant.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Landau theory, saddle points, Gaussian fluctuations, and RG corrections.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the ferromagnetic transition and RG chapters.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, scalar masses, and RG flows.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for a physics-first treatment of mean field, scaling, and the Ginzburg criterion.

## Version history

- 2026-06-18: First polished draft. Added saddle-point derivations of mean-field exponents, Gaussian correlation length, Ginzburg criterion, upper-critical-dimension interpretation, and dangerous-irrelevance caveats.
