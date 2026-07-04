---
title: "OPE Convergence"
description: "Explains why the Euclidean operator product expansion in a unitary CFT is a convergent expansion inside correlators, not merely a formal asymptotic rule."
sidebar:
  label: "OPE Convergence"
  order: 2
level: Graduate
status: "Polished draft"
source: "Pappadopulo–Rychkov–Espin–Rattazzi 2012; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Di Francesco–Mathieu–Sénéchal 1997"
topics:
  - operator product expansion
  - OPE convergence
  - radial quantization
  - conformal blocks
  - Euclidean CFT
  - Lorentzian limits
canonicalTopics:
  - ope-convergence
  - operator-product-expansion
  - radial-quantization
  - conformal-block-expansion
  - euclidean-cft
researchStatus:
  established:
    - "In unitary Euclidean CFT, the OPE of operators inside a sphere converges inside correlators when all other insertions lie outside the sphere."
    - "For four-point functions, radial variables make the convergence domain and truncation hierarchy more transparent than the bare cross-ratio variables."
  active:
    - "Sharp Lorentzian convergence, lightcone limits, Regge limits, nonunitary theories, logarithmic theories, and defect OPE convergence require additional care beyond the basic Euclidean argument."
---

## Summary

The operator product expansion is often written with a suggestive symbol,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x,\partial)\mathcal O_k(0).
$$

The symbol $\sim$ is dangerous if it makes the OPE look like a merely formal short-distance asymptotic expansion. In Euclidean unitary CFT, the local operator OPE has a stronger meaning: **inside correlation functions, it is a convergent expansion whenever the fused operators can be enclosed by a sphere that excludes all other insertions**.

The radial-quantization picture is the cleanest one. A cluster of operators inside a sphere creates a state on that sphere. Expanding that state in energy eigenstates on the cylinder is expanding it in local operators of definite scaling dimension. If the nearest outside insertion is at radius $R$ and the fused pair has size $r<R$, the expansion parameter is roughly

$$
\frac{r}{R}.
$$

This page explains what convergence means, why radial quantization proves it in the unitary Euclidean setting, how it appears in four-point functions and radial variables, and why Lorentzian limits need separate discussion.

## Prerequisites

You should know [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), and the scalar four-point setup from [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/).

It is also helpful to know [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) and [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/), because convergence is ultimately a Hilbert-space statement.

## Core idea

Choose an origin and put two operators inside a sphere of radius $R$. Keep every other insertion outside that sphere. The pair creates a state on the surrounding sphere. Since radial quantization identifies spheres with equal-time slices on the cylinder, this state can be decomposed in a basis of scaling-dimension eigenstates:

$$
|\Psi_{ij}(r)\rangle
=\sum_n c_n(r)|n\rangle,
\qquad
D|n\rangle=\Delta_n |n\rangle.
$$

By the state–operator correspondence, the states $|n\rangle$ are descendants of local primary operators. Therefore the spectral expansion of $|\Psi_{ij}(r)\rangle$ is the OPE.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Radial quantization gives the Euclidean OPE a geometric convergence domain.](/figures/cft-bootstrap/ope-convergence-domain.svg)

<figcaption>

The OPE of two insertions converges inside a correlator when the fused pair lies inside a sphere that excludes all other insertions. The expansion parameter is controlled by $r/R$, not by $r$ alone.

</figcaption>
</figure>

The crucial point is not that $r$ is small in absolute units. A CFT has no absolute length scale. The point is that the cluster is small compared with the nearest other insertion.

## Setup and conventions

We work in flat Euclidean space unless otherwise stated. A typical OPE statement inside a correlator has the form

$$
\langle \mathcal O_i(x)\mathcal O_j(0)X\rangle
=
\sum_k C_{ij}{}^k(x,\partial_y)
\langle \mathcal O_k(y)X\rangle\big|_{y=0},
$$

where $X$ is a product of other local operators. The convergence domain is geometric: all insertions in $X$ must lie outside a sphere centered near the expansion point and enclosing the pair $0,x$.

For scalar primaries with orthonormal two-point functions, the leading scalar-primary contribution is

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}
\mathcal O_k(0)+\text{descendants}.
$$

The descendants are not extra dynamical data. They are fixed by conformal symmetry. Convergence asks whether the sum over all primaries and descendants produces the correct correlator in a nonzero domain.

## What convergence means

The OPE is not an equality of ordinary pointwise operator products at coincident points. The product $\mathcal O_i(x)\mathcal O_j(0)$ is singular as $x\to0$. Convergence means the following more precise statement.

Let $X$ be a product of operators outside the OPE sphere. Then the partial sums

$$
S_{\Delta_*}(x;X)
=
\sum_{\mathcal O_k:\,\Delta_k\le \Delta_*}
C_{ij}{}^k(x,\partial_y)
\langle \mathcal O_k(y)X\rangle\big|_{y=0}
$$

approach the full correlator as the cutoff $\Delta_*$ is taken to infinity:

$$
\lim_{\Delta_*\to\infty}S_{\Delta_*}(x;X)
=
\langle \mathcal O_i(x)\mathcal O_j(0)X\rangle.
$$

The convergence is controlled by radial separation. If the fused pair lies within radius $r$ and the nearest other insertion is at radius $R$, then high-dimension states are suppressed by powers comparable to

$$
\left(\frac{r}{R}\right)^{\Delta_k}.
$$

This formula is schematic because descendants, spins, tensor structures, and angular dependence matter. But it captures the real reason the expansion works: radial time evolution suppresses high-energy states when there is a positive Euclidean time gap between the cluster and the rest of the correlator.

## Radial-quantization derivation

Place the expansion point at the origin and write Euclidean space as

$$
x^\mu=r n^\mu,
\qquad
r=e^\tau,
\qquad
n\in S^{d-1}.
$$

The flat metric becomes conformal to the cylinder metric,

$$
ds^2=dr^2+r^2d\Omega_{d-1}^2
=e^{2\tau}\left(d\tau^2+d\Omega_{d-1}^2\right).
$$

Dilatations in flat space become translations in cylinder time $\tau$. The dilatation operator $D$ becomes the cylinder Hamiltonian.

Now suppose the pair of operators lies at radial times smaller than some surface $\tau_0$, while all other insertions lie at radial times larger than $\tau_1>\tau_0$. Insert a complete set of energy eigenstates on a cylinder slice between them:

$$
\mathbf 1=\sum_n |n\rangle\langle n|.
$$

The correlator becomes a spectral sum,

$$
\langle X_{\mathrm{out}}\,\mathcal O_i\mathcal O_j\rangle
=
\sum_n
\langle X_{\mathrm{out}}|n\rangle
\langle n|\mathcal O_i\mathcal O_j|0\rangle.
$$

Radial time evolution inserts factors of the form

$$
e^{-(\tau_1-\tau_0)\Delta_n}.
$$

Since $\tau_1-\tau_0=\log(R/r)$, this is the same suppression as

$$
\left(\frac{r}{R}\right)^{\Delta_n}.
$$

The OPE is therefore the spectral decomposition of the state created by the inner operators. In a unitary theory the Hilbert-space norm is positive, so the standard completeness and convergence logic of spectral decompositions applies.

This is the basic reason Euclidean OPE convergence is stronger than a generic asymptotic expansion. The expansion is backed by a Hilbert space.

## A scalar four-point example

Consider identical scalar primaries $\phi$ with

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{2\Delta_\phi}}.
$$

The four-point function can be written

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}G(u,v),
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The OPE in the $12\to34$ channel gives

$$
G(u,v)=
1+
\sum_{\mathcal O\ne \mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
g_{\Delta,\ell}(u,v),
$$

where $g_{\Delta,\ell}$ is the conformal block for the primary $\mathcal O$ of dimension $\Delta$ and spin $\ell$. The identity block gives the leading $1$.

This expansion is convergent in the Euclidean region where points $x_1,x_2$ can be separated from $x_3,x_4$ by a sphere. In practical bootstrap work, the convergence is usually discussed using the complex cross-ratio variables

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

and especially the radial variables

$$
\rho=\frac{z}{\left(1+\sqrt{1-z}\right)^2},
\qquad
z=\frac{4\rho}{(1+\rho)^2}.
$$

For Euclidean configurations $\bar z=z^*$ and $\bar\rho=\rho^*$. The center of the convergence story is the condition

$$
|\rho|<1.
$$

The variable $\rho$ is not just cosmetic. It is adapted to the radial-quantization geometry of the four-point function and usually makes convergence much faster than using $z$ directly.

## Why radial variables help

The cross-ratio $z$ has branch points at $0,1,\infty$, corresponding to OPE limits and crossing-channel singularities. The map

$$
z=\frac{4\rho}{(1+\rho)^2}
$$

maps the cut $z$-plane to the unit disk in $\rho$. The dangerous crossing-channel singularity is pushed to the boundary $|\rho|=1$.

This is why conformal block expansions are often better behaved as expansions in $\rho$. A typical contribution has a leading radial behavior like

$$
\rho^\Delta \times \text{angular structure}.
$$

Large-dimension operators are therefore suppressed by $|\rho|^\Delta$. Near the crossing-symmetric point $z=\bar z=1/2$, one finds

$$
\rho=3-2\sqrt2\approx 0.1716.
$$

That is a small number. It explains why a surprisingly low number of low-dimension operators can already give accurate estimates in favorable Euclidean regimes, even though a full CFT has infinitely many primaries.

## Truncation and error intuition

The convergence theorem says the infinite expansion converges. It does not say every short truncation is accurate in every configuration.

A practical truncation keeps operators with $\Delta\le \Delta_*$. The omitted tail is schematically controlled by

$$
\sum_{\Delta>\Delta_*} a_\Delta |\rho|^\Delta,
$$

where $a_\Delta$ includes OPE coefficients, degeneracies, and angular data. The factor $|\rho|^\Delta$ suppresses heavy operators. The coefficients and density of states push back. Convergence is the statement that suppression wins inside the Euclidean domain.

For computations, this has three lessons.

First, Euclidean points deep inside the radial disk are friendly. Low-dimension data dominate.

Second, the lightcone and Regge regimes are not friendly merely because some coordinate looks small. They are controlled by different analytic continuations and can require resummation of infinitely many operators.

Third, bootstrap equations are powerful because they use convergence in multiple channels. The same correlator has several OPE expansions, and their common domain makes crossing symmetry a meaningful equality rather than a formal comparison of divergent series.

## What can go wrong

The clean convergence argument uses several assumptions.

The theory should have a genuine radial-quantization Hilbert space with positive norm. This is why unitarity, or Euclidean reflection positivity, matters. Nonunitary CFTs can still have useful OPEs, but the positivity-based Hilbert-space proof no longer applies in the same way.

The operator insertions should be separated. The OPE organizes coincident singularities, but the expansion is not a license to ignore contact terms when points collide exactly.

The chosen channel must have a separating sphere. If other insertions lie inside the same sphere as the pair being fused, that OPE channel is not in its convergence domain.

Analytic continuation to Lorentzian signature can cross branch cuts. A Euclidean convergent expansion can become a more subtle Lorentzian statement after operators are time-ordered, commuted, or placed near null separation.

Finally, special theories may have continuous spectra, logarithmic multiplets, gauge constraints, defect sectors, or non-normalizable states. Those cases require adaptations of the basic story.

## Euclidean and Lorentzian OPEs

The Euclidean OPE is a radial expansion. The Lorentzian OPE is more delicate because causal ordering matters. Two operators can approach one another spacelike, timelike, or lightlike, and the analytic continuation from Euclidean space depends on the $i\epsilon$ prescription.

For spacelike-separated Lorentzian points, the Euclidean OPE often gives the correct local singularity structure after continuation. For lightlike limits, the dominant contributions can reorganize. Infinite towers of large-spin operators can become important even if individual high-dimension terms are suppressed in a Euclidean region.

This is not a failure of the OPE. It is a reminder that different limits ask different questions:

| Limit | Main tool | Typical issue |
|---|---|---|
| Euclidean short distance | Radial OPE | Convergent local expansion. |
| Lorentzian spacelike short distance | Analytic continuation of Euclidean OPE | Operator ordering and $i\epsilon$ prescriptions. |
| Lightcone limit | Lightcone OPE and large-spin expansion | Infinite towers can dominate. |
| Regge limit | Lorentzian analytic continuation | Causality, chaos, and high-spin constraints. |

The ordinary OPE is the first tool, not the final word in every Lorentzian regime.

## Common pitfalls

Do not say simply “the OPE converges when $x$ is small.” Small compared with what? The correct statement is local and relational: the fused cluster must be separated from all other insertions.

Do not confuse the singular part of a two-dimensional holomorphic OPE with the full convergent operator expansion. In 2D CFT one often writes only singular terms because they determine Ward identities or algebraic relations. The full radial expansion also contains regular descendant contributions.

Do not assume convergence means positivity term by term in every basis. Positivity is cleanest for reflection-positive configurations, real scalar external operators, and appropriately normalized conformal blocks. With spin, parity-odd structures, complex operators, or multiple tensor structures, the positivity statement becomes matrix-valued or convention-dependent.

Do not use a Euclidean truncation estimate in a Lorentzian lightcone limit without checking analytic continuation. The villain here is not a tiny minus sign. It is an infinite tower dressed as a shortcut.

## Relations to other pages

[OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) defines the local replacement and the scalar primary contribution. This page explains why the replacement converges in the Euclidean radial domain.

[OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) explains the structure constants that multiply the conformal families. Convergence tells us those coefficients appear in an actual expansion, not merely in a formal algebra.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) turns the OPE of a pair inside a four-point function into a sum over exchanged conformal multiplets.

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) uses the fact that different convergent OPE channels compute the same correlator in overlapping Euclidean domains.

[Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) will revisit the story in Lorentzian kinematics, where the expansion reorganizes around null separation.

## Research status

The Euclidean convergence of the OPE in unitary CFT is established and is part of the standard modern foundation of the conformal bootstrap. The radial-coordinate technology used in conformal blocks is also standard.

Active directions include sharper control of tails at high dimension and spin, convergence in nonunitary and logarithmic theories, OPEs involving defects and boundaries, Lorentzian convergence after analytic continuation, and rigorous estimates in lightcone or Regge regimes. In practice, modern bootstrap work often needs not only convergence, but quantitative control over how fast the expansion converges under truncation.

## Exercises

### Exercise 1: Find the convergence parameter

A correlator contains $\mathcal O_i(x)\mathcal O_j(0)$ and other insertions at distances at least $R$ from the origin. Suppose $|x|=r<R$. What is the radial expansion parameter, and what happens as another insertion approaches radius $r$?

<details><summary><strong>Solution</strong></summary>

The expansion parameter is controlled by $r/R$. More precisely, one chooses a sphere enclosing the fused pair and excluding all other insertions; the radial time gap is $\log(R/r)$, so high-dimension states are suppressed by roughly

$$
\left(\frac rR\right)^\Delta.
$$

As another insertion approaches the same radius as the fused pair, the separating annulus shrinks. The radial time gap tends to zero, so the simple suppression of high-dimension states disappears. The OPE channel reaches the boundary of its convergence domain.

</details>

### Exercise 2: Radial variable at the crossing point

For the crossing-symmetric Euclidean point $z=\bar z=1/2$, compute

$$
\rho=\frac{z}{\left(1+\sqrt{1-z}\right)^2}.
$$

<details><summary><strong>Solution</strong></summary>

Set $z=1/2$. Then

$$
\rho=
\frac{1/2}{\left(1+1/\sqrt2\right)^2}
=
\frac{1/2}{3/2+\sqrt2}
=
\frac{1}{3+2\sqrt2}.
$$

Rationalizing gives

$$
\rho=3-2\sqrt2\approx0.1716.
$$

This small number explains why radial expansions are numerically efficient near the crossing-symmetric point.

</details>

### Exercise 3: Why the OPE is not a Taylor series

Explain why the OPE of two scalar operators generally contains operators that are not derivatives of either scalar.

<details><summary><strong>Solution</strong></summary>

A Taylor expansion of $\mathcal O_i(x)$ around the origin would produce only derivatives of $\mathcal O_i(0)$. The OPE is different. It expands the state created by the pair $\mathcal O_i(x)\mathcal O_j(0)$ in a complete basis of local-operator states. That basis includes every primary and descendant allowed by symmetry, not just descendants of $\mathcal O_i$ or $\mathcal O_j$.

For example, in a theory with a scalar $\phi$, the product $\phi(x)\phi(0)$ can contain the identity, $\phi^2$, the stress tensor, and many other operators. These are not Taylor coefficients of one original operator. They are independent local operators appearing in the operator algebra.

</details>

## References

- D. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE Convergence in Conformal Field Theory,” *Physical Review D* **86** (2012). Standard modern discussion of Euclidean OPE convergence and radial expansion estimates.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions* (2016). Clear introduction to radial quantization, OPE convergence, and bootstrap applications.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures (2017). Pedagogical treatment of reflection positivity, radial quantization, OPE, and conformal blocks.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019). Review of the CFT and bootstrap toolkit, including OPE, unitarity, conformal blocks, and crossing.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory* (Springer, 1997). Standard reference for two-dimensional radial quantization, OPEs, conformal families, and crossing.

## Version history

- 2026-06-27: Added a polished first version explaining Euclidean OPE convergence, radial quantization, radial variables, truncation intuition, and Lorentzian caveats.
