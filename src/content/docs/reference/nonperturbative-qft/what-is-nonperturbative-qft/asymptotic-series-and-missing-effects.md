---
title: "Asymptotic Series and Missing Effects"
description: "A guide to asymptotic perturbation series, optimal truncation, Borel summation, and the exponentially small effects that ordinary power series miss."
sidebar:
  label: "Asymptotic Series"
  order: 2
level: Graduate
status: "Polished draft"
source: "Mariño, Instantons and Large N, ch. 3; Zinn-Justin; Coleman; Polyakov."
topics:
  - asymptotic series
  - Borel summation
  - optimal truncation
  - instantons
  - renormalons
  - resurgence
canonicalTopics:
  - asymptotic-series
  - borel-summation
  - nonperturbative-effects
  - instantons
  - transseries
researchStatus:
  established:
    - "Perturbative expansions in quantum mechanics and QFT are often asymptotic, and finite-order power series cannot see contributions exponentially small in the expansion parameter."
  active:
    - "The systematic reconstruction of nonperturbative sectors from perturbative data is highly developed in many controlled examples and remains subtle in realistic four-dimensional QFTs."
---

## Summary

An asymptotic series is not a convergent Taylor series. It is a sequence of coefficients that approximates a function in a limit, usually only up to an order that depends on the small parameter. In perturbative QFT, the schematic expansion

$$
\mathcal O(x)\sim \sum_{n=0}^{\infty}a_n x^n,
\qquad x\to0^+,
$$

often has coefficients that eventually grow like

$$
a_n\sim C\,A^{-n}\Gamma(n+\beta).
$$

Then the terms first decrease and later increase. The best perturbative estimate is usually obtained by truncating near the least term,

$$
n_*\sim \frac{A}{x},
$$

and the irreducible perturbative error is of order

$$
e^{-A/x}.
$$

That is exactly the scale of many nonperturbative effects: tunneling amplitudes, instanton sectors, certain renormalon ambiguities, and more general saddle contributions. The moral is not that perturbation theory is bad. The moral is sharper: perturbation theory is often an asymptotic local description whose error is naturally the size of the physics it cannot see.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Optimal truncation of an asymptotic series](/figures/nonperturbative-qft/asymptotic-optimal-truncation.svg)

<figcaption>

For factorially growing coefficients, the terms of a perturbative expansion first decrease and then increase. Truncating near the least term gives the best perturbative approximation; the leftover uncertainty is exponentially small in the expansion parameter.

</figcaption>
</figure>

## Prerequisites

You should know the conceptual distinction explained in [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) and the Euclidean path-integral conventions in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). Basic familiarity with Gaussian integrals, saddle-point expansion, and perturbative Feynman diagrams is enough.

## Core idea

A perturbative series can be extremely accurate without being convergent. This is the first thing to unlearn if your mental model of “series” comes only from calculus.

The useful picture is this:

1. at small coupling, the first few terms often improve the approximation;
2. after many orders, factorial growth usually wins;
3. the least term sets the intrinsic accuracy of the perturbative expansion;
4. the remaining error is often the same size as an exponentially small nonperturbative effect;
5. in favorable cases, the large-order behavior of the perturbative coefficients carries information about the missing saddles.

So asymptotic series are not failed Taylor series. They are a different kind of approximation technology. The mistake is not using them; the mistake is pretending to be definitions when they are only local data.

## Setup and conventions

This page uses $x$ for a small positive expansion parameter. In many QFT applications,

$$
x=g^2,
$$

so an instanton factor looks like $e^{-A/x}=e^{-A/g^2}$. In quantum mechanics, $x$ may instead be $\hbar$ or a dimensionless coupling. The formulas below are written for $x\to0^+$.

A formal perturbative expansion is written

$$
f(x)\sim \sum_{n=0}^{\infty}a_nx^n.
$$

The symbol $\sim$ here does not mean equality to a convergent sum. It means “has the following asymptotic expansion” in the precise sense explained next.

## What asymptotic means

A function $f(x)$ has the asymptotic expansion

$$
f(x)\sim \sum_{n=0}^{\infty}a_nx^n
$$

as $x\to0^+$ if, for every fixed $N$,

$$
f(x)-\sum_{n=0}^{N-1}a_nx^n=O(x^N).
$$

Equivalently, for each fixed $N$, the truncated polynomial

$$
f_N(x)=\sum_{n=0}^{N-1}a_nx^n
$$

approximates $f(x)$ with an error that is smaller than the last retained power as $x\to0^+$.

The phrase “for every fixed $N$” is doing heavy lifting. In an asymptotic expansion, one first fixes the truncation order $N$ and then takes $x$ small. One is not promised that the sequence of partial sums converges as $N\to\infty$ at fixed $x$.

A convergent Taylor series is stronger. It defines the function inside a nonzero radius of convergence:

$$
f(x)=\sum_{n=0}^{\infty}a_nx^n
$$

for all sufficiently small $x$. An asymptotic expansion may approximate $f$ beautifully while the infinite series diverges for every nonzero $x$.

The difference is not philosophical. It controls what information perturbation theory can and cannot supply.

## A function with no perturbative shadow

The simplest missing effect is

$$
f(x)=e^{-A/x},
\qquad A>0.
$$

As $x\to0^+$ this function is smaller than every power of $x$:

$$
e^{-A/x}=O(x^N)
$$

for every $N$. Therefore

$$
e^{-A/x}\sim 0+0x+0x^2+\cdots.
$$

It has the zero asymptotic power series, but it is not the zero function.

This is the mathematical core of “beyond all orders.” A finite-order perturbative calculation in powers of $x$ cannot distinguish

$$
f(x)
$$

from

$$
f(x)+C e^{-A/x}
$$

for any constant $C$. Both have the same asymptotic expansion in powers of $x$.

In QFT language, this is why an instanton sector with weight $e^{-8\pi^2/g^2}$ cannot be produced by any finite number of ordinary Feynman diagrams around the trivial vacuum. The diagrams know the coefficients of powers of $g^2$. The instanton carries a different functional dependence on $g$.

:::note[Zero series does not mean zero physics]
A term can have zero perturbative expansion and still be measurable. Energy splittings in a double well, theta-angle dependence, and certain tunneling rates are standard examples.
:::

## Factorial growth and optimal truncation

Why do perturbative series so often diverge? There are several mechanisms. One is combinatorial: the number of diagrams grows rapidly with loop order. Another is analytic: the function being expanded may have singularities or saddle contributions in nearby complex directions. In QFT there are also infrared and ultraviolet mechanisms associated with renormalons.

The common large-order pattern is

$$
a_n\sim C\,A^{-n}\Gamma(n+\beta),
$$

so the $n$th term behaves like

$$
T_n(x)=a_nx^n
\sim C\,\Gamma(n+\beta)\left(\frac{x}{A}\right)^n.
$$

To estimate where the terms are smallest, use the ratio

$$
\left|\frac{T_{n+1}}{T_n}\right|
\sim \frac{x}{A}(n+\beta).
$$

The terms decrease while this ratio is less than one and increase after it becomes greater than one. Thus the least term occurs near

$$
n_*\sim \frac{A}{x}.
$$

At small $x$, this can be a large number. That is why the first many orders of a divergent series can be useful.

Using Stirling’s approximation, the size of the least term is exponentially small:

$$
|T_{n_*}(x)|\sim \text{power of }x\times e^{-A/x}.
$$

This is the central bridge. A factorially divergent perturbative series naturally leaves an uncertainty of order $e^{-A/x}$, the same order as a nonperturbative saddle of action $A/x$.

A good asymptotic approximation is therefore not obtained by summing everything. It is obtained by truncating intelligently.

## A zero-dimensional model

A useful laboratory is the ordinary integral

$$
I(\lambda)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dq\,
\exp\left[-\frac12 q^2-\frac{\lambda}{4}q^4\right],
\qquad \lambda>0.
$$

This is a zero-dimensional cousin of the Euclidean $\phi^4$ path integral. Expanding the interaction gives

$$
I(\lambda)=\sum_{n=0}^{\infty}\frac{1}{n!}\left(-\frac{\lambda}{4}\right)^n
\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dq\,q^{4n}e^{-q^2/2}.
$$

The Gaussian moment is

$$
\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dq\,q^{4n}e^{-q^2/2}
=\frac{(4n)!}{2^{2n}(2n)!}.
$$

Therefore

$$
I(\lambda)\sim \sum_{n=0}^{\infty}(-1)^n
\frac{(4n)!}{2^{4n}n!(2n)!}\lambda^n.
$$

The coefficients grow factorially. The alternating sign helps Borel summation, but it does not make the ordinary power series convergent.

This toy integral also shows Dyson’s instability logic in miniature. The integral is well-defined for $\lambda>0$, but if one analytically continues to negative $\lambda$, the quartic term makes the integrand blow up at large $|q|$. A nonzero radius of convergence around $\lambda=0$ would not know about this instability. The instability sitting on the other side of the origin is one reason the expansion around the Gaussian point is only asymptotic.

In real QFT, the same idea appears in richer forms. A sign flip of a coupling may destabilize the vacuum, high-order Feynman diagrams proliferate, instanton saddles appear in complexified field space, and renormalized momentum regions produce additional large-order behavior.

## Borel transform and Borel sum

The Borel transform is a way to remove a factorial from the coefficients. Given

$$
f(x)\sim \sum_{n=0}^{\infty}a_nx^n,
$$

define the formal Borel transform

$$
\mathcal Bf(t)=\sum_{n=0}^{\infty}\frac{a_n}{n!}t^n.
$$

If this series has a useful analytic continuation, one tries to reconstruct $f$ by the Laplace-type integral

$$
\mathcal S_B f(x)=\frac{1}{x}\int_0^{\infty}dt\,e^{-t/x}\mathcal Bf(t).
$$

The reason this works formally is

$$
\frac{1}{x}\int_0^{\infty}dt\,e^{-t/x}t^n=n!x^n.
$$

So if the integral is well-defined and term-by-term integration is justified, the Borel sum has the desired asymptotic expansion.

Borel summation is not magic. It requires analytic continuation of $\mathcal Bf(t)$ beyond its radius of convergence, and the integration contour must avoid singularities. If the Borel transform has no singularity on the positive real $t$ axis and suitable growth properties, the series may be Borel summable along the positive direction.

If there is a singularity on the positive real axis, the integral is ambiguous. One can pass above or below the singularity, obtaining lateral Borel sums

$$
\mathcal S_{+}f(x),
\qquad
\mathcal S_{-}f(x).
$$

Their difference is typically of order

$$
\mathcal S_{+}f(x)-\mathcal S_{-}f(x)
\sim e^{-A/x}
$$

when the singularity sits at $t=A$.

This is not a failure. It is a clue. The ambiguity in summing the perturbative sector has exactly the size needed to be canceled by an ambiguity in a nonperturbative sector. That cancellation is one of the organizing ideas behind resurgence and transseries.

## What Borel singularities mean

A singularity of the Borel transform at $t=A$ usually signals large-order behavior of the form

$$
a_n\sim A^{-n}n!\times \text{powers of }n.
$$

Physically, $A$ is often related to an action, an action difference, or a characteristic nonperturbative scale.

There are several important sources:

| Source | Typical meaning | Typical missing scale |
|---|---|---|
| Instanton saddle | A finite-action Euclidean configuration not continuously connected to the perturbative vacuum. | $e^{-S_{\mathrm{inst}}}$, often $e^{-A/g^2}$. |
| Instanton–anti-instanton sector | A correlated event with zero net topological charge but nontrivial saddle structure. | Ambiguities that cancel perturbative Borel ambiguities. |
| Renormalon | Factorial growth from integration over large or small momentum regions in renormalized perturbation theory. | Powers of $\Lambda/Q$ or related OPE-like corrections. |
| Complex saddle | A saddle reached after complexifying fields or parameters. | Stokes jumps and exponentially small complex contributions. |

The table is schematic. In serious QFT examples, identifying the Borel singularities and their physical interpretation can be delicate. Instantons are geometric and semiclassical; renormalons are tied to momentum regions and renormalization. They should not be casually identified with each other.

## Transseries: adding the missing sectors

A power series alone cannot encode all exponentially small sectors as ordinary terms. A transseries enlarges the expansion by adding them explicitly:

$$
f(x)\sim
\sum_{n\geq0}a_{0,n}x^n
+\sigma e^{-A/x}\sum_{n\geq0}a_{1,n}x^n
+\sigma^2e^{-2A/x}\sum_{n\geq0}a_{2,n}x^n
+\cdots.
$$

The first line is the perturbative sector. The next lines are one-instanton, two-instanton, or more general exponential sectors, depending on the problem. The parameter $\sigma$ is a transseries parameter. In physics it is fixed by the definition of the problem: boundary conditions, integration contour, vacuum choice, theta angle, or reality/unitarity requirements.

This is important. Perturbation theory around one saddle may know about the existence and fluctuation series of other sectors through large-order relations, but the full physical answer still needs global data. A transseries without boundary conditions is not yet a QFT.

In quantum mechanics, this structure can be made very explicit in double-well and periodic potentials. In many QFT settings, it becomes subtler because there are infinitely many degrees of freedom, renormalization, infrared effects, compactification choices, and possible renormalons.

## How missing effects appear in familiar physics

### Tunneling in quantum mechanics

For a double-well potential, perturbation theory around one minimum gives a local oscillator expansion. The exact ground-state doublet is split by tunneling. Semiclassically,

$$
\Delta E\sim e^{-S_0/\hbar}\times \text{fluctuation series}.
$$

Every coefficient in ordinary perturbation theory around one well misses the splitting.

### Yang–Mills instantons

In four-dimensional Yang–Mills theory, a unit instanton has action

$$
S_{\mathrm{inst}}=\frac{8\pi^2}{g^2}.
$$

Its weight is

$$
e^{-8\pi^2/g^2+i\theta}.
$$

The dependence on $g$ and $\theta$ is not produced by perturbative Feynman diagrams in the trivial topological sector. The instanton lives in a different topological sector of Euclidean gauge fields.

### Dimensional transmutation

In an asymptotically free theory with

$$
\mu\frac{dg}{d\mu}=-b_0g^3+O(g^5),
\qquad b_0>0,
$$

the RG-invariant scale is schematically

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]\times(\text{higher-loop factors}).
$$

A mass gap proportional to $\Lambda$ is nonanalytic at $g=0$. Perturbation theory can define the short-distance running and the scheme-dependent form of $\Lambda$, but it does not by itself compute the full spectrum.

### Renormalons and operator corrections

Renormalons are not classical saddle points. They arise from certain high-order regions of renormalized Feynman integrals. Their ambiguities often have the same size as power corrections in an operator product expansion. In favorable contexts, the ambiguity of perturbative summation cancels against the ambiguity in defining nonperturbative matrix elements or condensates.

The caution is essential: renormalon language is powerful, but it is also easy to abuse. The location and interpretation of singularities depend on the observable, scheme, and expansion variable.

## What perturbative data can determine

Finite-order perturbation theory cannot determine a term with zero perturbative expansion. But large-order perturbation theory may reveal its shadow.

If

$$
a_n\sim C\,A^{-n}\Gamma(n+\beta),
$$

then the perturbative coefficients suggest a Borel singularity at $t=A$. In favorable cases, the subleading large-order expansion determines the fluctuation series around the associated nonperturbative saddle. This is one of the central ideas of resurgence.

But there are three caveats.

First, knowing many perturbative coefficients is not the same as knowing the exact large-order law. In QFT, only finitely many coefficients may be available.

Second, a Borel singularity need not be a simple instanton. It may be a renormalon, a complex saddle, a boundary effect, or a combination of mechanisms.

Third, even if perturbative data reveal the possible exponential sectors, the physical answer needs a prescription: which lateral sum, which contour, which vacuum, which theta angle, and which boundary conditions.

So the right statement is balanced:

$$
\text{perturbation theory may encode nonperturbative data, but it does not replace the nonperturbative definition.}
$$

## Practical diagnostic for a perturbative expansion

When facing a perturbative expansion in QFT, ask these questions.

| Question | Why it matters |
|---|---|
| What is the expansion parameter? | A series in $g$, $g^2$, $1/N$, $\epsilon$, or $E/M$ has different nonperturbative scales. |
| What saddle or fixed point is being used? | The expansion is local around that choice. |
| Are coefficients expected to grow factorially? | If yes, infinite-order summation needs care. |
| Is the series sign-alternating or same-sign? | Sign patterns influence Borel summability along the physical direction. |
| Where are the Borel singularities? | Their locations estimate missing exponential scales. |
| Are there known saddles or topological sectors? | They supply candidate nonperturbative sectors. |
| Is the observable infrared safe? | Infrared sensitivity can produce factorial growth and nonperturbative power corrections. |
| What fixes the boundary condition or contour? | The same asymptotic series may correspond to different exact functions. |

For ordinary precision calculations, one may not need the full answer to all these questions. But if the calculation is being used as a definition, or if the observable is sensitive to mass gaps, tunneling, confinement, or condensates, ignoring them is dangerous.

## Common pitfalls

**Treating divergence as failure.** A divergent asymptotic series may be the best available approximation. The problem is not divergence itself; the problem is summing or interpreting the series without a prescription.

**Assuming Borel summability automatically.** Dividing coefficients by $n!$ is only the first step. One also needs analytic continuation of the Borel transform and a contour free of uncanceled ambiguities.

**Forgetting the expansion variable.** A contribution $e^{-A/g^2}$ is beyond all orders in $g^2$, while $e^{-A/g}$ is beyond all orders in $g$. Mixing the variables can hide the real semiclassical scale.

**Identifying every Borel singularity with an instanton.** Instantons are one source of large-order behavior, but renormalons and complex saddles are different mechanisms. The physical interpretation depends on the observable and the theory.

**Thinking large-order data fix the answer alone.** Large-order relations may reveal missing sectors, but the final answer also depends on global input such as integration cycles, boundary conditions, theta angles, and reality conditions.

**Ignoring scheme and normalization dependence.** The location and normalization of perturbative coefficients depend on the definition of the coupling and observable. Universal physics must be phrased in quantities whose convention dependence is controlled.

## Relations to other pages

- [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/) gives the conceptual overview that this page sharpens mathematically.
- [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/) fixes the Euclidean, theta-angle, and instanton-weight conventions used in the examples.
- Later pages on semiclassical saddle-point expansion, instantons in quantum mechanics, Yang–Mills instantons, renormalons, Borel summability, and transseries will turn these diagnostics into detailed calculations.

## Research status

The distinction between convergent and asymptotic expansions is standard mathematics, and the asymptotic nature of perturbation theory is textbook-standard in quantum mechanics, statistical field theory, and QFT. The connection between factorial growth and nonperturbative saddles is established in many controlled examples.

Borel summability is model- and observable-dependent. Some theories and observables are Borel summable in suitable regimes; others have singularities on the physical Borel contour and require nonperturbative sectors or prescriptions to cancel ambiguities.

Resurgence gives a powerful framework relating perturbative and nonperturbative sectors. It is exceptionally explicit in many quantum-mechanical problems and in several lower-dimensional, supersymmetric, compactified, or otherwise controlled QFT settings. The complete nonperturbative organization of realistic four-dimensional gauge theories remains an active and nuanced research area, with renormalons, instantons, complex saddles, compactification, and scheme dependence all playing roles.

## Exercises

### Exercise 1: The zero asymptotic expansion

Show that

$$
f(x)=e^{-A/x},\qquad A>0,
$$

has the asymptotic expansion $f(x)\sim0$ as $x\to0^+$.

<details>
<summary><strong>Solution</strong></summary>

For any fixed integer $N\geq0$,

$$
\frac{e^{-A/x}}{x^N}=\exp\left[-\frac{A}{x}-N\log x\right].
$$

As $x\to0^+$, the term $A/x$ dominates $|N\log x|$, so the ratio tends to zero. Therefore

$$
e^{-A/x}=O(x^N)
$$

for every $N$. This is exactly the statement that the asymptotic power series has all coefficients equal to zero.

</details>

### Exercise 2: Estimate the best truncation order

Suppose

$$
a_n\sim A^{-n}n!,
\qquad A>0,
$$

and consider the term $T_n=a_nx^n$. Estimate the order $n_*$ where $|T_n|$ is smallest.

<details>
<summary><strong>Solution</strong></summary>

Use the ratio of successive terms:

$$
\left|\frac{T_{n+1}}{T_n}\right|
\sim \frac{x}{A}(n+1).
$$

The terms decrease while this ratio is less than one and increase after it is greater than one. Thus the crossover occurs near

$$
n_*\sim \frac{A}{x}.
$$

Using Stirling’s formula at this order gives a least term proportional to $e^{-A/x}$ times powers of $x$.

</details>

### Exercise 3: Coefficients of the zero-dimensional quartic integral

For

$$
I(\lambda)=\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dq\,
\exp\left[-\frac12q^2-\frac{\lambda}{4}q^4\right],
$$

expand in powers of $\lambda$ and show that the coefficient of $\lambda^n$ is

$$
(-1)^n\frac{(4n)!}{2^{4n}n!(2n)!}.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the quartic interaction:

$$
e^{-\lambda q^4/4}=\sum_{n=0}^{\infty}\frac{1}{n!}\left(-\frac{\lambda}{4}\right)^n q^{4n}.
$$

The normalized Gaussian moment is

$$
\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty}dq\,q^{2m}e^{-q^2/2}
=\frac{(2m)!}{2^m m!}.
$$

Set $m=2n$ to get

$$
\frac{1}{\sqrt{2\pi}}\int dq\,q^{4n}e^{-q^2/2}
=\frac{(4n)!}{2^{2n}(2n)!}.
$$

Multiplying by $(-\lambda/4)^n/n!$ gives

$$
(-1)^n\frac{(4n)!}{4^n n!2^{2n}(2n)!}
=(-1)^n\frac{(4n)!}{2^{4n}n!(2n)!}.
$$

The factorials grow too fast for the power series to have a nonzero radius of convergence.

</details>

### Exercise 4: A non-Borel-summable toy series

Consider the formal series

$$
f(x)\sim\sum_{n=0}^{\infty}n!x^n.
$$

Compute its formal Borel transform and explain why the positive-axis Borel integral is ambiguous.

<details>
<summary><strong>Solution</strong></summary>

The Borel transform is

$$
\mathcal Bf(t)=\sum_{n=0}^{\infty}t^n=\frac{1}{1-t}
$$

inside its radius of convergence, with analytic continuation given by the same rational function away from $t=1$.

The Borel sum would be

$$
\frac{1}{x}\int_0^\infty dt\,\frac{e^{-t/x}}{1-t}.
$$

But the integrand has a pole at $t=1$ on the integration contour. Passing above or below the pole gives different answers whose difference is proportional to the residue times $e^{-1/x}$. Thus the perturbative series alone is ambiguous by a nonperturbative amount.

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapter on large-order behavior and Borel summability.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for asymptotic perturbation theory, field integrals, instantons, and summation methods.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on instantons and semiclassical physics.

### Deeper references

- A. M. Polyakov, *Gauge Fields and Strings*, for instantons, topology of gauge fields, confinement-motivated nonperturbative physics, and large-N viewpoints.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, 2nd ed., for instantons, false-vacuum decay, anomalies, confinement in lower-dimensional models, and modern gauge-theory phases.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the Wilsonian background behind asymptotic expansions, critical phenomena, and continuum limits.

## Version history

- **2026-06-25:** Initial polished draft. Added optimal-truncation figure and exercises on zero asymptotic expansions, least-term truncation, zero-dimensional quartic coefficients, and Borel ambiguity.
