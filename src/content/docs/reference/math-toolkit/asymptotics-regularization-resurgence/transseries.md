---
title: "Transseries"
description: "Explains transseries as the asymptotic language that combines perturbative series, exponentially small sectors, logarithms, Stokes data, and nonperturbative ambiguities in QFT."
sidebar:
  label: "Transseries"
  order: 6
level: Advanced
status: "Polished draft"
source: "Standard references on asymptotic analysis, Borel summation, resurgence, instantons, WKB, renormalons, and nonperturbative QFT, including Dingle, Écalle, Berry, Zinn-Justin, Coleman, Mariño, Shifman, Weinberg, Srednicki, Schwartz, and modern resurgence literature."
topics:
  - transseries
  - resurgence
  - nonperturbative sectors
  - instantons
  - Borel summation
  - Stokes phenomenon
  - large-order behavior
  - renormalons
  - asymptotic analysis
canonicalTopics:
  - transseries
  - resurgence
  - nonperturbative-sector
  - instanton
  - borel-summation
  - stokes-phenomenon
  - large-order-behavior
  - renormalon
  - asymptotic-analysis
researchStatus:
  established:
    - "Transseries are a standard mathematical language for asymptotic problems in which perturbative powers must be supplemented by exponentially small sectors, powers, and logarithms."
    - "In finite-dimensional saddle problems, the transseries sectors are naturally associated with critical points and their fluctuation expansions."
  active:
    - "For general quantum field theories, especially theories with renormalons, massless fields, complex saddles, and gauge redundancies, the complete resurgent transseries structure is still an active research problem."
---

## Summary

A transseries is what an asymptotic expansion becomes when one stops pretending that an ordinary power series can contain all the information. A perturbative expansion has the form

$$
F(g)\sim \sum_{n=0}^{\infty}a_n g^n,
$$

but QFT often contains effects whose small-coupling size is not a power of $g$ at all:

$$
e^{-S/g},\qquad e^{-S/g^2},\qquad e^{-N S},\qquad g^\beta e^{-S/g}(\log g)^k.
$$

These terms are **flat** at $g=0$: all derivatives of $e^{-1/g}$ vanish at $g=0^+$, so no Taylor series in $g$ can see it. A transseries adds these invisible sectors explicitly.

A typical one-parameter transseries looks like

$$
F(g;\sigma)
\sim
\Phi_0(g)
+
\sigma e^{-A/g}g^\beta \Phi_1(g)
+
\sigma^2 e^{-2A/g}g^{2\beta}\Phi_2(g)
+
\cdots,
$$

where each $\Phi_k(g)$ is itself an asymptotic power series:

$$
\Phi_k(g)\sim \sum_{n=0}^{\infty}a_{k,n}g^n.
$$

The new symbol $\sigma$ is not decoration. It records boundary conditions, integration contours, vacuum choice, lateral Borel prescription, or other global information not contained in one perturbative sector.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing perturbative, instanton, multi-instanton, and renormalon or complex-saddle sectors organized into a transseries and related to Borel-plane singularities and Stokes jumps.](/figures/math-toolkit/transseries-sector-lattice.svg)

<figcaption>

A transseries organizes asymptotic sectors. Perturbative coefficients can grow factorially because they already know about other saddles or Borel singularities. Stokes jumps shift the transseries parameters so that ambiguities in one sector are cancelled by ambiguities in another.

</figcaption>
</figure>

Transseries are the natural language for instantons, bounces, WKB quantization, large-order perturbation theory, matrix models, resurgence, and renormalon-style ambiguities. The hard truth is that a transseries is not automatically a definition of a QFT. It is a structured asymptotic object. To turn it into physics, one still has to specify the contour, Hilbert space, boundary condition, regulator, and prescription.

## Prerequisites

You should be comfortable with [Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/), [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/), [Saddle Points](/math-toolkit/complex-analysis/saddle-points/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), and [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/). For QFT applications, it helps to know [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) and [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/).

The page [Steepest Descent](/math-toolkit/asymptotics-regularization-resurgence/steepest-descent/) explains the contour geometry behind many of the formulas used here.

## Core idea

A power series classifies terms by powers of one small parameter:

$$
1,\quad g,\quad g^2,\quad g^3,\quad\ldots
$$

A transseries classifies terms by a richer hierarchy:

$$
\text{exponential scale}
\quad\times\quad
\text{power scale}
\quad\times\quad
\text{logarithmic scale}
\quad\times\quad
\text{ordinary asymptotic series}.
$$

For a single instanton action $A$, one often writes

$$
F(g;\sigma)
\sim
\sum_{k=0}^{\infty}
\sigma^k e^{-kA/g}g^{k\beta}
\sum_{n=0}^{\infty}a_{k,n}g^n.
$$

For several actions $A_1,\ldots,A_r$, the sector label becomes a multi-index $\mathbf k=(k_1,\ldots,k_r)$:

$$
F(g;\boldsymbol\sigma)
\sim
\sum_{\mathbf k\in\mathbb N^r}
\boldsymbol\sigma^{\mathbf k}
\exp\!\left(-{\mathbf k\cdot\mathbf A\over g}\right)
 g^{\mathbf k\cdot\boldsymbol\beta}
\Phi_{\mathbf k}(g).
$$

Here

$$
\boldsymbol\sigma^{\mathbf k}=\sigma_1^{k_1}\cdots\sigma_r^{k_r},
\qquad
\Phi_{\mathbf k}(g)\sim\sum_{n=0}^{\infty}a_{\mathbf k,n}g^n.
$$

This formula is not meant to say that all physical problems have only exponentials of the form $e^{-A/g}$. In QFT, the small parameter might be $g^2$, $\hbar$, $1/N$, $1/E$, $1/m$, or a semiclassical parameter. For Yang–Mills instantons, the classical weight is usually

$$
e^{-8\pi^2/g^2}.
$$

For a large-N expansion, sectors may be weighted by $e^{-N A}$. For tunneling in quantum mechanics, the small parameter may be $\hbar$, giving $e^{-S/\hbar}$. The point is the hierarchy, not the letter used for the small parameter.

## Setup and conventions

We will use $g\to0^+$ as the small-parameter limit. When the natural small parameter is $g^2$, replace $g$ below by $g^2$. When the natural small parameter is $\hbar$, replace $g$ by $\hbar$.

An ordinary asymptotic expansion is written

$$
\Phi(g)\sim\sum_{n=0}^{\infty}a_n g^n.
$$

A transseries sector is written

$$
\mathfrak s_{A,\beta}(g)\Phi(g)
= e^{-A/g}g^\beta\Phi(g),
$$

where $A$ is an **action scale** or **singulant**, $\beta$ is a characteristic exponent, and $\Phi(g)$ is a fluctuation series.

The action scale $A$ can be real or complex. If $A$ is real and positive, $e^{-A/g}$ is exponentially small for $g>0$. If $A$ is complex, it also carries an oscillatory phase:

$$
e^{-A/g}=e^{-\operatorname{Re}A/g}e^{-i\operatorname{Im}A/g}.
$$

Complex saddles are not optional weirdness. They often control large-order behavior even when the original integration variables are real.

## Why perturbation theory needs completion

The perturbative series around one saddle is usually blind to other saddles at the level of term-by-term expansion. For example,

$$
F(g)=\Phi_0(g)+e^{-A/g}\Phi_1(g)
$$

has the same Poincaré asymptotic expansion as $\Phi_0(g)$ alone if $A>0$ and $g\to0^+$. The difference is smaller than every power of $g$:

$$
e^{-A/g}=o(g^N)\qquad\text{for every fixed }N.
$$

So the perturbative expansion cannot decide whether the coefficient of $e^{-A/g}$ is zero, one, imaginary, or a complicated function of boundary data. This is why perturbation theory by itself is incomplete even when it is known to all orders.

But perturbation theory is not useless. The late coefficients of $\Phi_0$ often grow in a way controlled by the nearest nonperturbative sectors. A typical large-order relation has the schematic form

$$
a_{0,n}
\sim
{S_{01}\over 2\pi i}
\sum_{m=0}^{\infty}
 a_{1,m}\,{\Gamma(n+\beta-m)\over A^{n+\beta-m}},
\qquad n\to\infty.
$$

The constants $S_{01}$ are Stokes data. The exact normalization depends on conventions, but the message is robust: the perturbative sector knows about the first nonperturbative sector through its large-order growth.

## Anatomy of a transseries

A useful mental picture is this:

$$
\begin{array}{ccl}
\Phi_0(g)&=&\text{perturbative vacuum sector},\\[3pt]
 e^{-A/g}g^\beta\Phi_1(g)&=&\text{one-instanton or one-saddle sector},\\[3pt]
 e^{-2A/g}g^{2\beta}\Phi_2(g)&=&\text{two-instanton or repeated-saddle sector},\\[3pt]
 e^{-B/g}\Psi(g)&=&\text{another saddle, renormalon, or complex sector}.
\end{array}
$$

Each row has its own fluctuation expansion. The word “fluctuation” is important: a sector is not only the exponential. For an instanton saddle $\phi_{\text{inst}}$, the path integral contains

$$
e^{-S[\phi_{\text{inst}}]/g}\times
\left(\text{zero-mode measure}\right)
\times
\left(\text{determinant factor}\right)
\times
\left(1+c_1g+c_2g^2+\cdots\right).
$$

That entire object is a sector. The determinant and zero modes often produce powers of $g$, logarithms, and collective-coordinate integrals.

A more general one-parameter transseries allows logarithms:

$$
F(g;\sigma)
\sim
\sum_{k=0}^{\infty}\sigma^k e^{-kA/g}g^{k\beta}
\sum_{\ell=0}^{L_k}(\log g)^\ell
\sum_{n=0}^{\infty}a_{k,\ell,n}g^n.
$$

Logarithms are common when there are resonances, anomalous dimensions, zero modes, marginal couplings, or running couplings.

## Where the sectors come from

The cleanest origin is a finite-dimensional integral:

$$
I(g)=\int_\Gamma dz\,h(z)e^{-S(z)/g}.
$$

Suppose $S$ has critical points $z_\alpha$ satisfying

$$
S'(z_\alpha)=0.
$$

After complexifying $z$, the contour $\Gamma$ can often be decomposed into steepest-descent cycles, or thimbles,

$$
\Gamma\sim\sum_\alpha n_\alpha\mathcal J_\alpha.
$$

Each thimble contributes

$$
I_\alpha(g)
\sim
n_\alpha e^{-S(z_\alpha)/g}g^{1/2}
\sum_{n=0}^{\infty}a_{\alpha,n}g^n.
$$

Thus the transseries is not invented after the fact. It is the asymptotic expansion of the exact integral after the contour has been resolved into saddle contributions.

QFT path integrals behave similarly in spirit but are harder. Saddles are field configurations $\phi_\alpha$ satisfying the classical equations of motion, and sectors look like

$$
Z_\alpha(g)
\sim
n_\alpha e^{-S[\phi_\alpha]/g}
\left(\det{}' S''[\phi_\alpha]\right)^{-1/2}
\times
\left(\text{zero-mode integrals}\right)
\times
\left(1+O(g)\right).
$$

The prime on $\det{}'$ means zero modes are removed from the determinant and handled separately. Gauge theories require gauge fixing and ghost determinants before this statement becomes meaningful.

## Transseries parameters

The transseries parameters $\sigma$ are sometimes the most misunderstood part of the story.

They are not new coupling constants in the microscopic Lagrangian unless the problem says so. They are labels for global data that ordinary perturbation theory cannot determine. Examples include:

- the choice of integration contour in a complexified integral,
- the choice of lateral Borel summation prescription,
- boundary conditions for a differential equation,
- the choice of vacuum or metastable state,
- a choice of nonperturbative completion,
- theta angles, discrete flux data, or superselection data in special cases.

For an unambiguous real observable, $\sigma$ is fixed so that Stokes ambiguities cancel. For a metastable vacuum, the physically relevant prescription may produce an imaginary part interpreted as a decay rate. For a formal perturbative sector alone, $\sigma$ remains invisible.

A good habit is to separate three questions:

$$
\begin{array}{ccl}
\text{What sectors are allowed?} &\quad& \text{local saddles and asymptotic analysis},\\
\text{What are their coefficients?} && \text{contour and boundary data},\\
\text{Which sum is the physical answer?} && \text{definition of the theory and observable}.
\end{array}
$$

## Stokes jumps and ambiguity cancellation

The Borel sum of a sector can depend on the direction of the Laplace contour. Suppose the Borel transform of $\Phi_0$ has a singularity on the positive real axis at $t=A$. Then the two lateral sums

$$
\mathcal S_{0^+}\Phi_0,
\qquad
\mathcal S_{0^-}\Phi_0
$$

are generally different. Their difference has the scale of the sector associated with the singularity:

$$
\mathcal S_{0^+}\Phi_0-
\mathcal S_{0^-}\Phi_0
\sim
S_{01}e^{-A/g}g^\beta\mathcal S_0\Phi_1.
$$

This looks disastrous if one insists that $\Phi_0$ alone is the answer. It becomes useful if the full answer is a transseries. The jump of the perturbative Borel sum can be cancelled by a compensating jump in the parameter $\sigma$:

$$
\sigma\longmapsto \sigma-S_{01}.
$$

This is the simplest form of **resurgence**: ambiguities of one sector are repaired by other sectors, and the rule for the repair is encoded in Stokes data.

:::note[Not every ambiguity is bad]
An ambiguity in a partial asymptotic description is often a diagnostic. It says, “You have not included enough sectors or enough physical input.” The full physical quantity may be real and unambiguous even though individual sectors are not.
:::

## Logs, anomalous dimensions, and running couplings

In QFT, transseries often contain logarithms. The source can be mundane or profound.

A loop correction may produce

$$
g^2\log {\mu\over m},
$$

and RG improvement may resum such terms. Near a saddle with zero modes, collective-coordinate integrals may produce powers and logs of the coupling. Near a resonance in an exact WKB problem, different sectors may mix and produce logarithmic transmonomials.

A common QFT-looking sector is therefore not merely

$$
e^{-A/g^2}\sum_{n=0}^{\infty}a_n g^{2n},
$$

but rather

$$
e^{-A/g^2}g^\beta
\sum_{\ell=0}^{L}(\log g)^\ell
\sum_{n=0}^{\infty}a_{\ell,n}g^{2n}.
$$

The power $g^\beta$ can encode determinant ratios, zero modes, anomalous dimensions, or one-loop beta-function data. The logarithms can encode running couplings or resonant mixing.

## Instantons, bounces, and renormalons

Instanton sectors come from finite-action Euclidean saddle points. In a weakly coupled theory with action written schematically as

$$
S_E={1\over g^2}\int d^dx\,\mathcal L,
$$

an instanton with reduced action $A$ contributes a weight

$$
e^{-A/g^2}.
$$

Bounces describe false-vacuum decay and usually have a negative mode. Their contribution is tied to an imaginary part of the vacuum energy or effective action.

Renormalons are subtler. They are Borel-plane singularities associated with large or small loop-momentum regions and the running of couplings, not with ordinary finite-action classical solutions. A renormalon contribution may look like

$$
e^{-A/g^2(\mu)}\sim \left({\Lambda_{\text{QFT}}\over \mu}\right)^p,
$$

so a transseries sector can be power-suppressed in physical scales even though it is nonperturbative in the coupling.

This is one reason QFT resurgence is messier than the one-dimensional examples. The Borel plane may contain instanton singularities, infrared renormalons, ultraviolet renormalons, complex saddles, and singularities whose physical interpretation depends on the observable and scheme.

## A toy calculation: flat terms are invisible

Let

$$
F_\sigma(g)=\sum_{n=0}^{N-1}a_n g^n+R_N(g)+\sigma e^{-A/g}
$$

with $A>0$ and $R_N(g)=O(g^N)$ as $g\to0^+$. For every fixed $N$,

$$
e^{-A/g}=O(g^N).
$$

Indeed, for $g>0$ set $u=A/g$. Then

$$
{e^{-A/g}\over g^N}
=A^{-N}u^N e^{-u}\to0
\qquad (u\to\infty).
$$

Therefore every value of $\sigma$ gives the same ordinary perturbative asymptotic expansion. Perturbation theory cannot determine $\sigma$.

This little observation is the conceptual hinge of the whole page. Nonperturbative sectors are not “small corrections to a complete perturbative answer.” They are additional data that are invisible to ordinary asymptotic equality but can be necessary for the exact object.

## Resurgence as a dictionary

The word **resurgence** is used in several levels of precision. At the practical level used in QFT, it means that information recurs across sectors. The late coefficients of one expansion know about the early coefficients of another.

Schematic relation:

$$
\text{large order of }\Phi_0
\quad\longleftrightarrow\quad
\text{Borel singularity at }A
\quad\longleftrightarrow\quad
\text{sector }e^{-A/g}\Phi_1.
$$

In a finite-dimensional saddle problem this relation can often be proven or checked directly. In many QFT applications, especially with renormalons, one has a mixture of rigorous asymptotic analysis, semiclassical calculation, diagrammatic evidence, operator-product logic, and physical consistency.

The payoff is enormous: a divergent perturbative expansion can become a probe of nonperturbative physics.

## What transseries do not do automatically

A transseries is not automatically convergent. Each $\Phi_k(g)$ may be divergent. The sum over $k$ may also be formal. Even when each sector is Borel summable, the full object may require a prescription.

A transseries is not automatically unique. Different choices of transseries variables, sectors, summation directions, and parameterizations can describe the same function.

A transseries is not automatically gauge invariant. In gauge theory, one must define the observable, gauge fixing, zero modes, ghosts, collective coordinates, and regulator carefully.

A transseries is not automatically the nonperturbative definition of a QFT. It may be an asymptotic expansion of a definition supplied elsewhere: a lattice theory, a Hamiltonian, an exact integral, a supersymmetric localization formula, a conformal bootstrap solution, or a rigorous constructive definition.

Tiny trapdoor, giant basement.

## Common pitfalls

**Mistaking “all perturbative orders” for the full answer.** A function can have the same perturbative expansion as another function while differing by $e^{-A/g}$.

**Calling every exponential an instanton.** Some exponentials come from complex saddles, endpoint effects, bounces, renormalons, finite volume, large-N eigenvalue tunneling, or analytic continuation.

**Treating $\sigma$ as arbitrary physics.** The transseries parameter is fixed by the nonperturbative definition or physical prescription. Leaving it arbitrary is useful while classifying solutions, not a license to fit anything.

**Ignoring logarithms and powers.** The exponential is only the leading scale. Determinants, zero modes, RG effects, and resonances can generate powers and logs that are physically important.

**Assuming Borel summability.** A Borel transform with singularities on the integration ray requires lateral sums and ambiguity cancellation. Borel summability is a property to check, not a vibe.

**Forgetting scheme dependence.** Renormalon locations and residues are often discussed in scheme-dependent coordinates, while physical cancellations are scheme-independent.

## Relations to other pages

[Asymptotic Series](/math-toolkit/asymptotics-regularization-resurgence/asymptotic-series/) explains why divergent expansions can still approximate functions. [Borel Transform](/math-toolkit/asymptotics-regularization-resurgence/borel-transform/) explains how factorial growth becomes Borel-plane singularities. [Steepest Descent](/math-toolkit/asymptotics-regularization-resurgence/steepest-descent/) explains why saddle decompositions naturally produce transseries sectors.

[Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) gives the path-integral version of saddle expansion. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) and [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/) explain determinant factors in one-loop saddle expansions. [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/) and [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/) provide the complex-analysis language behind Stokes jumps and lateral sums.

## Research status

The general structure of transseries in finite-dimensional integrals, ordinary differential equations, and many quantum-mechanical examples is well established. Exact WKB, Borel–Écalle summation, and saddle resurgence provide a precise dictionary in many model problems.

In QFT, the picture is powerful but uneven. Instanton sectors, bounces, semiclassical determinants, and many supersymmetric or lower-dimensional examples are under good control. Renormalons, complex saddles, gauge-field configuration spaces, massless modes, and the global definition of integration cycles in infinite-dimensional path integrals remain much harder. Modern resurgence in QFT is therefore both a toolkit and an active research frontier.

## Exercises

### Exercise 1: Flatness of a nonperturbative exponential

Show that for every integer $N\ge0$,

$$
e^{-A/g}=o(g^N)
$$

as $g\to0^+$, assuming $A>0$.

<details><summary><strong>Solution</strong></summary>

Set $u=A/g$. Then $g=A/u$ and $u\to\infty$ as $g\to0^+$. We have

$$
{e^{-A/g}\over g^N}
={e^{-u}\over (A/u)^N}
=A^{-N}u^N e^{-u}.
$$

Since the exponential beats every power, $u^N e^{-u}\to0$. Therefore $e^{-A/g}/g^N\to0$, which is precisely $e^{-A/g}=o(g^N)$.

</details>

### Exercise 2: Same perturbative expansion, different functions

Let

$$
F_0(g)=\sum_{n=0}^{M}a_n g^n,
\qquad
F_1(g)=F_0(g)+\sigma e^{-A/g},
$$

with $A>0$. Show that $F_0$ and $F_1$ have the same Poincaré asymptotic expansion through every power of $g$ as $g\to0^+$.

<details><summary><strong>Solution</strong></summary>

Their difference is $\sigma e^{-A/g}$. By Exercise 1 this is $o(g^N)$ for every $N$. Therefore the difference is smaller than any power retained in a Poincaré asymptotic expansion. Ordinary power-series asymptotics cannot detect $\sigma$.

</details>

### Exercise 3: Sector weights from two saddles

Suppose an integral has two saddle contributions

$$
I(g)\sim e^{-S_0/g}\Phi_0(g)+n_1e^{-S_1/g}\Phi_1(g),
$$

with $\operatorname{Re}(S_1-S_0)>0$. Factor out the dominant saddle and identify the transseries action.

<details><summary><strong>Solution</strong></summary>

Factor out $e^{-S_0/g}$:

$$
I(g)\sim e^{-S_0/g}\left[\Phi_0(g)+n_1e^{-(S_1-S_0)/g}\Phi_1(g)\right].
$$

The relative transseries action is

$$
A=S_1-S_0.
$$

Since $\operatorname{Re}A>0$, the second sector is exponentially suppressed relative to the first for $g\to0^+$.

</details>

### Exercise 4: Ambiguity cancellation in a two-sector transseries

Assume a lateral Borel jump

$$
\mathcal S_+\Phi_0-\mathcal S_-\Phi_0
= C e^{-A/g}\mathcal S\Phi_1.
$$

Show how a jump of the transseries parameter cancels this ambiguity in

$$
F=\mathcal S\Phi_0+\sigma e^{-A/g}\mathcal S\Phi_1.
$$

<details><summary><strong>Solution</strong></summary>

Across the Stokes ray, the perturbative sector changes by

$$
\Delta(\mathcal S\Phi_0)=C e^{-A/g}\mathcal S\Phi_1.
$$

If simultaneously

$$
\Delta\sigma=-C,
$$

then the nonperturbative term changes by

$$
\Delta\left(\sigma e^{-A/g}\mathcal S\Phi_1\right)
=-C e^{-A/g}\mathcal S\Phi_1.
$$

The two changes cancel, so the full transseries sum is unchanged.

</details>

## References

- R. B. Dingle, *Asymptotic Expansions: Their Derivation and Interpretation*.
- J. Écalle, *Les fonctions résurgentes*.
- M. V. Berry and C. J. Howls, work on hyperasymptotics and Stokes phenomena.
- C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- S. Coleman, *Aspects of Symmetry*.
- M. Mariño, *Instantons and Large N*.
- M. Shifman, *Advanced Topics in Quantum Field Theory*.
- M. Srednicki, *Quantum Field Theory*.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–III.

## Version history

- 2026-06-26: First polished draft for the Mathematical Toolkit volume.
