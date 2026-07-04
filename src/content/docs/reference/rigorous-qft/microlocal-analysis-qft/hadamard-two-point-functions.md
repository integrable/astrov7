---
title: "Hadamard Two-Point Functions"
description: "Explains the local Hadamard form of two-point functions, its wavefront-set characterization, and why it is the correct short-distance condition for states in curved-spacetime QFT."
sidebar:
  label: "Hadamard Two-Point Functions"
  order: 4
level: Advanced
status: "Polished draft"
source: "Radzikowski; Kay–Wald; Wald; Brunetti–Fredenhagen–Köhler; Hollands–Wald; Fulling–Narcowich–Wald."
topics:
  - Hadamard states
  - two-point functions
  - wavefront sets
  - curved spacetime QFT
  - Wick products
canonicalTopics:
  - hadamard-state
  - two-point-function
  - microlocal-analysis
  - curved-spacetime-qft
researchStatus:
  established:
    - "For free scalar fields on globally hyperbolic spacetimes, the Hadamard condition is the standard short-distance regularity condition for physical states, and Radzikowski's theorem gives its wavefront-set form."
    - "The difference of two Hadamard two-point functions is smooth, so the singular part is local and state-independent."
  active:
    - "Gauge fields, constraints, boundaries, interacting theories, and non-globally-hyperbolic settings require additional structure beyond the scalar Hadamard template."
---

## Summary

A Hadamard two-point function is the rigorous replacement for the informal statement that a curved-spacetime state should look like the Minkowski vacuum at very short distances. For a real scalar field, a state $\omega$ has two-point distribution

$$
\omega_2(f,g)=\omega\bigl(\phi(f)\phi(g)\bigr),
\qquad
\omega_2\in \mathcal D'(M\times M),
$$

and the Hadamard condition fixes the singular part of $\omega_2$ near the diagonal and along the light cone.

In four spacetime dimensions, inside a convex normal neighborhood, the local form is schematically

$$
\omega_2(x,y)
\sim
\frac{1}{8\pi^2}\left(
\frac{U(x,y)}{\sigma_\epsilon(x,y)}
+V(x,y)\log \frac{\sigma_\epsilon(x,y)}{\ell^2}
\right)
+W(x,y),
$$

where $\sigma(x,y)$ is Synge's world function, $U$ and $V$ are locally determined by the metric and the wave operator, and $W$ is smooth and state-dependent. The $i\epsilon$ prescription in $\sigma_\epsilon$ fixes the positive-frequency boundary value; sign conventions differ across references.

Microlocally, the same condition is the wavefront-set statement

$$
\operatorname{WF}(\omega_2)
=
\{(x,k_x;y,-k_y):(x,k_x)\sim(y,k_y),\ k_x\triangleright0\}.
$$

Thus the two-point singularities lie on null geodesics and carry one positive-frequency orientation. This is the exact condition that makes Wick powers, stress tensors, and perturbative algebraic QFT possible on curved spacetimes.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Hadamard two-point singularity as universal light-cone singularity plus smooth state dependence](/figures/rigorous-qft/hadamard-two-point-singularity.svg)

<figcaption>

A Hadamard two-point function has a universal singular part determined by local geometry and a smooth state-dependent remainder. The wavefront set records the lightlike relation and the positive-frequency orientation of the singularity.

</figcaption>
</figure>

## Prerequisites

Read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/), [Microlocal Spectrum Condition](/rigorous-qft/microlocal-analysis-qft/microlocal-spectrum-condition/), and [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) first. You should also know the free scalar field equation and the meaning of globally hyperbolic spacetime from [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/).

## Core idea

The vacuum two-point function of the free scalar field in Minkowski space is singular at coincident points and on the light cone. This singularity is not an accident of a bad state. It is the local short-distance behavior forced by relativistic quantum fields.

A curved spacetime generally has no preferred global vacuum. Even if a preferred state exists in special cases, it is not part of the local definition of the theory. The Hadamard condition separates what is universal from what is state-dependent:

$$
\text{two-point function}
=
\text{universal local singularity}
+
\text{smooth state data}.
$$

This is the curved-spacetime analogue of requiring that the ultraviolet behavior of a state agree with the ordinary positive-frequency vacuum. The condition is local, geometric, and stable under the operations needed for Wick products and renormalized stress tensors.

A non-Hadamard two-point function can still be a distribution and can still solve the field equation. The problem is that its short-distance singularities are wrong. They may make composite fields ill-defined, produce unphysical stress-tensor divergences, or violate the local positive-frequency structure that replaces the spectral condition.

## Setup and conventions

Let $(M,g)$ be a smooth, time-oriented, globally hyperbolic Lorentzian spacetime. For a real scalar field, write

$$
P=\Box_g+m^2+\xi R,
$$

with the sign convention inherited from the mostly-minus local convention used elsewhere in this volume. Other authors absorb signs into $P$; the Hadamard singularity and wavefront condition are invariant after translating conventions.

The field algebra has commutator

$$
[\phi(f),\phi(g)]
=iE(f,g)\mathbf 1,
$$

where

$$
E=E_{\rm ret}-E_{\rm adv}
$$

is the causal propagator. A two-point function of a state is a bidistribution satisfying, in the free scalar case,

$$
P_x\omega_2(x,y)=0,
\qquad
P_y\omega_2(x,y)=0,
$$

in the distributional sense, together with the commutator condition

$$
\omega_2(x,y)-\omega_2(y,x)=iE(x,y).
$$

A state also requires positivity:

$$
\omega_2(\overline f,f)\ge0.
$$

The Hadamard condition is not a replacement for positivity or the field equation. It is an additional short-distance condition on the singular structure of $\omega_2$.

## Synge's world function and the local form

In a convex normal neighborhood, any two sufficiently close points $x,y$ are joined by a unique geodesic. Synge's world function is

$$
\sigma(x,y)=\frac12 s(x,y)^2,
$$

where $s(x,y)$ is the signed geodesic distance. Thus $\sigma=0$ on the local light cone, and the two-point function has singularities as $y$ approaches the light cone of $x$.

In four dimensions, the Hadamard form is usually written as a boundary value of

$$
H_\epsilon(x,y)
=
\frac{1}{8\pi^2}
\left(
\frac{U(x,y)}{\sigma_\epsilon(x,y)}
+V(x,y)\log\frac{\sigma_\epsilon(x,y)}{\ell^2}
\right),
$$

so that

$$
\omega_2(x,y)=\lim_{\epsilon\downarrow0}H_\epsilon(x,y)+W(x,y)
$$

locally, modulo harmless convention-dependent normalizations. Here:

| Symbol | Meaning | Status |
|---|---|---|
| $\sigma(x,y)$ | Half the squared geodesic distance. | Local geometric input. |
| $\sigma_\epsilon$ | Boundary-value prescription selecting positive frequency. | Convention-dependent sign. |
| $U(x,y)$ | Leading transport coefficient, equal to $\Delta^{1/2}$ in the scalar case. | Locally determined. |
| $V(x,y)$ | Logarithmic coefficient with an expansion fixed by transport equations. | Locally determined up to the wave operator. |
| $\ell$ | Reference length in the logarithm. | Renormalization scale. |
| $W(x,y)$ | Smooth bisolution data. | State-dependent. |

The precise $i\epsilon$ prescription is often written using a time function $T$ as

$$
\sigma_\epsilon(x,y)
=
\sigma(x,y)+2i\epsilon\bigl(T(x)-T(y)\bigr)+\epsilon^2,
$$

or with the opposite sign, depending on the convention for positive frequency. The point is not the literal formula with a chosen $T$. The point is that the singular distribution is a boundary value with the same orientation as the positive-frequency Minkowski two-point function.

:::caution[The sign of the prescription is not universal]
Different metric, Fourier, and commutator conventions move signs between $E$, $\sigma_\epsilon$, and the definition of future-directed covectors. Always compare the wavefront-set orientation, not just the displayed $i\epsilon$ sign.
:::

## The coefficients U, V, and W

The coefficient $U$ is determined by the van Vleck–Morette determinant,

$$
U(x,y)=\Delta(x,y)^{1/2},
$$

with $U(x,x)=1$. It measures the focusing of geodesics and is purely local geometry.

The coefficient $V$ is determined by transport equations involving the operator $P$. It has an asymptotic expansion near the diagonal,

$$
V(x,y)\sim \sum_{j\ge0}V_j(x,y)\sigma(x,y)^j,
$$

where the coefficients $V_j$ are local curvature and mass data. In even dimensions, logarithmic terms are tied to these local coefficients. In odd dimensions the detailed form changes, but the wavefront-set characterization remains the clean invariant statement.

The coefficient $W$ is smooth. It carries the state dependence. Thermal states, quasifree states on stationary spacetimes, and locally constructed states can all have different $W$ while sharing the same singular part.

This is why the difference of two Hadamard two-point functions is smooth:

$$
\omega_2-\omega_2'\in C^\infty(M\times M).
$$

The singularity is universal; the smooth part is where the state lives.

## Microlocal characterization

Radzikowski's theorem identifies the Hadamard condition for scalar two-point functions with the wavefront-set condition

$$
\operatorname{WF}(\omega_2)
=
\{(x,k_x;y,-k_y):(x,k_x)\sim(y,k_y),\ k_x\triangleright0\}.
$$

The notation means:

$$
(x,k_x)\sim(y,k_y)
$$

when $x$ and $y$ are joined by a null geodesic and $k_y$ is the parallel transport of $k_x$ along it. The covector $k_x$ is future-directed, after raising its index with the metric and using the chosen time orientation.

This formula compresses the analytic content of the local Hadamard expansion into a geometric statement:

$$
\text{Hadamard singularities}
=
\text{null propagation}+\text{positive frequency}.
$$

It also explains why the condition belongs in microlocal analysis. The singular support only says that $\omega_2$ is singular on null-related pairs. The wavefront set says which covector directions occur there, and that directionality is exactly what controls products and pullbacks.

## Why Hadamard states are the physical state space

Hadamard states are the natural state space for free fields on globally hyperbolic curved spacetimes for four reasons.

First, they reproduce the correct short-distance behavior of the Minkowski vacuum. The equivalence principle suggests that sufficiently small neighborhoods should not allow arbitrary ultraviolet singularities.

Second, Hadamard states form a large class. The condition is restrictive in the ultraviolet but does not pick a unique global vacuum. It admits ground states on stationary spacetimes when they exist, KMS states, and many locally constructed states.

Third, Wick powers and time-ordered products are defined by subtracting the universal singular part. For example, a Wick square is morally obtained from

$$
\phi^2(x)
\sim
\lim_{y\to x}\bigl(\phi(x)\phi(y)-H(x,y)\mathbf 1\bigr),
$$

where $H$ is a chosen Hadamard parametrix. This expression is schematic, but it explains the role of the condition: subtract the universal singularity, then take the coincident limit.

Fourth, the renormalized stress tensor requires the same singularity control. Since stress tensors involve derivatives and coincident limits, wrong ultraviolet behavior creates divergences that cannot be removed by the usual local geometric counterterms.

## Relation to Wick products

Choose a Hadamard parametrix $H$. Normal ordering with respect to $H$ defines local Wick polynomials by subtracting the singular part rather than by referring to a preferred vacuum. For example,

$$
:\!\phi^2\!:_H(f)
$$

is a well-defined smeared field after the appropriate distributional extension and subtraction. If one changes $H$ by a smooth function, the Wick polynomial changes by local smooth terms. This is the curved-spacetime version of finite renormalization ambiguity.

The same logic extends to time-ordered products. The singularities away from diagonals are controlled by wavefront-set criteria, while extension to diagonals introduces local ambiguities. Hadamard two-point functions are therefore not an isolated state condition; they are the input that lets perturbative algebraic QFT work.

## Relation to the commutator function

The causal propagator $E$ has wavefront set containing both time orientations. It is the difference of advanced and retarded fundamental solutions, and it is fixed by the equation of motion and causal structure.

A Hadamard two-point function has an antisymmetric part fixed by $E$:

$$
\omega_2(x,y)-\omega_2(y,x)=iE(x,y),
$$

but its full singularity selects a positive-frequency splitting. In flat space this splitting is encoded by Fourier support on the positive-energy mass shell. In curved space it is encoded by the wavefront-set orientation.

Thus the Hadamard condition can be understood as a microlocal choice of the positive-frequency part of the causal singularity.

## Example: Minkowski vacuum

For a massive scalar field in Minkowski space, the vacuum two-point function is

$$
\omega_2(x,y)
=
\int \frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
 e^{-ip\cdot(x-y)},
\qquad
p^0=E_{\mathbf p}>0.
$$

Its singularities occur when $x-y$ is lightlike, and the positive-energy condition selects one orientation of the covectors. Locally, after translating to curved coordinates and adding curvature corrections, this is exactly what the Hadamard form captures.

The mass affects the smooth and logarithmic coefficient structure, but the leading wavefront-set directions are null. High-frequency singularities do not see the mass term at leading order; they are governed by the principal symbol of $P$.

## Common pitfalls

**Hadamard means vacuum.** No. A Hadamard state is a state with the right ultraviolet singularity. There can be many Hadamard states on the same spacetime.

**The smooth term is irrelevant.** The smooth term does not affect the wavefront set, but it contains the actual state-dependent physics, including expectation values and thermal data.

**The local formula is globally valid.** The displayed Hadamard expansion is local, usually in a convex normal neighborhood. Global topology, caustics, and boundary conditions require separate analysis.

**The logarithm is optional bookkeeping.** In even spacetime dimensions the logarithmic term carries real geometric information and is tied to renormalization scale dependence.

**Correct commutator implies Hadamard.** The commutator fixes only the antisymmetric part. The symmetric part can still have pathological singularities.

**The $i\epsilon$ sign can be read without conventions.** It cannot. Compare Fourier phase, metric signature, and commutator convention before deciding which sign represents positive frequency.

## Relations to other pages

The page [Microlocal Spectrum Condition](/rigorous-qft/microlocal-analysis-qft/microlocal-spectrum-condition/) gives the wavefront-set form of the condition. This page explains the local two-point parametrix behind that statement.

The page [Propagation of Singularities](/rigorous-qft/microlocal-analysis-qft/propagation-of-singularities/) explains why singularities of solutions to the wave equation move along null geodesics. That theorem is the analytic engine behind the null-geodesic relation in the Hadamard wavefront set.

The page [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) uses Hadamard parametrices to build Wick powers, time-ordered products, and local counterterms.

## Research status

For linear scalar fields on globally hyperbolic spacetimes, the Hadamard condition is a settled part of rigorous curved-spacetime QFT. Radzikowski's microlocal characterization is now the standard definition used in algebraic and perturbative frameworks.

For gauge fields, the situation is more delicate because constraints, gauge equivalence, and indefinite auxiliary spaces must be handled before one can state the physical two-point function condition cleanly. For interacting theories, Hadamard states are used order by order in perturbative algebraic QFT, while nonperturbative interacting constructions on generic curved spacetimes remain much harder.

For boundaries, defects, horizons, and non-globally-hyperbolic backgrounds, extra singularities or boundary wavefront conditions can appear. The scalar Hadamard template remains the starting point, not the whole story.

## Exercises

### Exercise 1: Smooth differences

Let $\omega_2$ and $\omega_2'$ be two Hadamard two-point functions for the same scalar operator $P$. Explain why their difference is smooth, and why this matters for defining Wick products.

<details><summary><strong>Solution</strong></summary>

Both two-point functions have the same universal local singular part. In the local Hadamard form,

$$
\omega_2=H+W,
\qquad
\omega_2'=H+W',
$$

after choosing the same local parametrix $H$. Therefore

$$
\omega_2-\omega_2'=W-W',
$$

which is smooth. In the wavefront-set formulation, both have the same allowed singular structure, but the theorem says more: the singular parts agree locally, so their difference has empty wavefront set. This matters because changing the reference Hadamard parametrix changes Wick products only by smooth local terms, interpreted as finite renormalization ambiguities.

</details>

### Exercise 2: Why null directions?

For $P=\Box_g+m^2+\xi R$, explain why the wavefront set of a singular bisolution is controlled by null covectors rather than by the mass shell $g^{-1}(k,k)=m^2$.

<details><summary><strong>Solution</strong></summary>

Wavefront sets record high-frequency singularities, and high-frequency propagation is controlled by the principal symbol of the differential operator. The lower-order terms $m^2$ and $\xi R$ do not contribute to the principal symbol. For a normally hyperbolic operator,

$$
p(x,k)=g^{\mu\nu}(x)k_\mu k_\nu.
$$

The characteristic set is

$$
\operatorname{Char}(P)=\{(x,k):k\ne0,\ p(x,k)=0\},
$$

which is the bundle of nonzero null covectors. Thus singularities propagate along null bicharacteristics even for massive fields. The mass affects amplitudes and smooth terms, not the leading null wavefront relation.

</details>

### Exercise 3: Hadamard versus positivity

Does the Hadamard wavefront-set condition alone prove that a bidistribution is the two-point function of a state?

<details><summary><strong>Solution</strong></summary>

No. The Hadamard wavefront-set condition controls singularities. A two-point function of a state must also satisfy the field equation, the commutator condition, hermiticity, and positivity. Positivity is the Hilbert-space condition

$$
\omega_2(\overline f,f)\ge0
$$

for all test functions $f$. A bidistribution can have the correct wavefront set but fail positivity, or fail the commutator condition, and therefore not define a physical state.

</details>

## References

### Standard first pass

- Marek J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. [DOI: 10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- Robert M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- Bernard S. Kay and Robert M. Wald, "Theorems on the Uniqueness and Thermal Properties of Stationary, Nonsingular, Quasifree States on Spacetimes with a Bifurcate Killing Horizon," *Physics Reports* **207** (1991), 49–136. [DOI: 10.1016/0370-1573(91)90015-E](https://doi.org/10.1016/0370-1573(91)90015-E).

### Deeper references

- S. A. Fulling, F. J. Narcowich, and Robert M. Wald, "Singularity Structure of the Two-Point Function in Quantum Field Theory in Curved Spacetime, II," *Annals of Physics* **136** (1981), 243–272. [DOI: 10.1016/0003-4916(81)90088-0](https://doi.org/10.1016/0003-4916(81)90088-0).
- Romeo Brunetti, Klaus Fredenhagen, and Martin Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. [arXiv:gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056), [DOI: 10.1007/BF02099626](https://doi.org/10.1007/BF02099626).
- Stefan Hollands and Robert M. Wald, "Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [DOI: 10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- Christian Gérard and Michał Wrochna, "Construction of Hadamard States by Pseudo-Differential Calculus," *Communications in Mathematical Physics* **325** (2014), 713–755. [arXiv:1209.2604](https://arxiv.org/abs/1209.2604), [DOI: 10.1007/s00220-013-1824-9](https://doi.org/10.1007/s00220-013-1824-9).

## Version history

- **2026-07-01:** Initial page on Hadamard two-point functions and their microlocal characterization.
