---
title: "Hadamard Condition"
description: "Defines the Hadamard condition for curved-spacetime quantum fields and explains its microlocal form, physical role, and use in renormalization."
sidebar:
  label: "Hadamard Condition"
  order: 8
level: Advanced
status: "Polished draft"
source: "Kay–Wald Hadamard states; Radzikowski microlocal characterization; Hollands–Wald curved-spacetime QFT."
topics:
  - Hadamard states
  - curved spacetime QFT
  - wavefront sets
  - microlocal spectrum condition
  - renormalized composite fields
canonicalTopics:
  - hadamard-condition
  - qft-on-curved-spacetimes
  - microlocal-spectrum-condition
  - locally-covariant-quantum-field-theory
researchStatus:
  established:
    - "For linear scalar fields on globally hyperbolic spacetimes, the Hadamard condition is the standard local replacement for the flat-spacetime positive-frequency singularity condition."
  active:
    - "Gauge fields, state-space selection principles, semiclassical backreaction, and interacting nonperturbative theories require additional structure beyond the basic Hadamard condition."
---

## Summary

The Hadamard condition is the standard regularity condition on physically admissible states of quantum fields on curved spacetimes. It says that the ultraviolet singularity of the two-point function is locally the same as the singularity of the Minkowski vacuum, even though the spacetime may have no time-translation symmetry and no preferred vacuum.

For a quasifree scalar state $\omega$ on a globally hyperbolic spacetime $M$, the condition can be stated locally as

$$
\omega_2(x,y)=H_\ell(x,y)+W_\omega(x,y),
$$

where $H_\ell$ is a locally and geometrically determined Hadamard parametrix and $W_\omega$ is smooth. Equivalently, in Radzikowski's microlocal formulation,

$$
\operatorname{WF}(\omega_2)=
\left\{
(x,k_x;y,-k_y)
\ \middle|\
(x,k_x)\sim(y,k_y),\ k_x\triangleright 0
\right\}.
$$

Here $(x,k_x)\sim(y,k_y)$ means that $x$ and $y$ are joined by a null geodesic and the nonzero covectors are cotangent to that geodesic and parallel transported along it. The symbol $k_x\triangleright0$ denotes the positive-frequency, future-directed choice.

This page explains the local Hadamard form, the microlocal form, why they are equivalent under standard hypotheses, and why the condition is indispensable for Wick products, stress tensors, perturbative interactions, and semiclassical gravity.

## Prerequisites

You should know [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/), [QFT in Curved Spacetime: Rigorous View](/rigorous-qft/locally-covariant-qft/qft-in-curved-spacetime-rigorous-view/), and [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). The pages [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and [Locally Covariant Fields](/rigorous-qft/locally-covariant-qft/locally-covariant-fields/) provide the operator-valued distribution and functorial background.

## Core idea

The Hadamard condition solves a problem created by curvature: in a generic curved spacetime there is no preferred splitting into positive and negative frequencies. Without such a splitting, one cannot pick a canonical Fock vacuum by Fourier analysis. But one still needs to know which states have physically acceptable short-distance behavior.

The answer is local rather than spectral. A good state may differ globally from the Minkowski vacuum in many ways, but when two points approach each other along a sufficiently small normal neighborhood, the singular part of its two-point function must have a universal form determined by the metric and the field equation.

This is the curved-spacetime replacement for the positive-energy singularity structure of the flat vacuum. It has three jobs.

| Job | Meaning |
|---|---|
| State selection | Exclude states with unphysical ultraviolet singularities. |
| Renormalization input | Make point-splitting and Wick products possible by subtracting a universal singular part. |
| Microlocal spectrum condition | Replace global energy positivity by a local condition on singular directions. |

The condition is not a dynamical equation and not a unique vacuum prescription. It is a short-distance admissibility condition on states.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Hadamard wavefront set condition](/figures/rigorous-qft/hadamard-wavefront-condition.svg)

<figcaption>

The Hadamard condition says that the singular directions of $\omega_2(x,y)$ lie on null-related pairs with positive-frequency orientation. The smooth part of the state may vary; the singular cone is universal.

</figcaption>
</figure>

## Setup and conventions

Let $M=(\mathcal M,g)$ be a smooth oriented and time-oriented globally hyperbolic spacetime. We use the mostly-minus metric convention of this volume. For the real scalar field, take

$$
P_M=\Box_g+m^2+\xi R,
$$

where $R$ is scalar curvature. The field algebra is generated by smeared fields $\Phi_M(f)$ satisfying

$$
\Phi_M(P_Mf)=0,
\qquad
[\Phi_M(f),\Phi_M(g)]=iE_M(f,g)\mathbf 1,
$$

where $E_M=E_M^{\mathrm{ret}}-E_M^{\mathrm{adv}}$ is the causal propagator.

A state $\omega$ determines distributions

$$
\omega_n(f_1,\ldots,f_n)
=\omega\bigl(\Phi_M(f_1)\cdots\Phi_M(f_n)\bigr).
$$

For a quasifree state, all $n$-point functions are determined by $\omega_2$ through Wick-type pairings. The Hadamard condition is most often introduced first for such quasifree two-point functions, then extended to more general states by microlocal conditions on all $n$-point distributions.

## Local Hadamard form

Choose a geodesically convex neighborhood, so that nearby points $x,y$ are joined by a unique geodesic. Let $\sigma(x,y)$ be Synge's world function, one half the signed squared geodesic distance. In four spacetime dimensions the local singular part of a scalar two-point function has the schematic form

$$
H_\ell(x,y)=\frac{1}{8\pi^2}
\left(
\frac{U(x,y)}{\sigma_\epsilon(x,y)}
+V(x,y)\log\frac{\sigma_\epsilon(x,y)}{\ell^2}
\right),
$$

where $\ell$ is a reference length and $\sigma_\epsilon$ denotes the Lorentzian $i\epsilon$ prescription, usually written using a local time function. The coefficients $U$ and $V$ are determined by the metric, the operator $P_M$, and transport equations along geodesics. In particular, $U$ is related to the Van Vleck–Morette determinant.

A state is locally Hadamard if, in every sufficiently small convex neighborhood,

$$
\omega_2(x,y)-H_\ell(x,y)
$$

is smooth. More precisely, the formula is a statement about distributions, not ordinary pointwise functions. The expression $H_\ell(x,y)$ is a local parametrix: it captures the singularity but is not itself a globally defined two-point function and need not be positive.

The length scale $\ell$ does not represent new physics by itself. Changing $\ell$ shifts $H_\ell$ by a smooth local term. That smooth shift reappears later as a finite renormalization ambiguity in Wick powers and stress tensors.

## What is universal and what is state-dependent

The two-point distribution has two pieces:

$$
\omega_2
=
\text{universal singular part}
+
\text{smooth state-dependent part}.
$$

The singular part is local and geometric. It is determined by the principal light-cone propagation of the field equation and by lower-order curvature and mass terms. This is why two Hadamard states have the same short-distance singularity.

The smooth part contains global and state-dependent physics: thermal occupation numbers, cosmological particle creation, boundary conditions, preparation procedures, and other infrared data. It is not fixed by the Hadamard condition.

A crucial consequence is:

$$
\omega_2-\omega_2'\in C^\infty(M\times M)
$$

whenever $\omega$ and $\omega'$ are Hadamard states of the same free scalar field. This smoothness is the technical reason that normal ordering with respect to different Hadamard states differs only by smooth $c$-number terms, and why local Wick products can be defined state-independently after subtracting the universal singularity.

## Microlocal form

The local Hadamard expansion is powerful but cumbersome. The modern invariant formulation uses the wavefront set. It records not only where a distribution is singular, but also in which cotangent directions it is singular.

For a scalar quasifree state, the microlocal Hadamard condition is

$$
\operatorname{WF}(\omega_2)=
\left\{
(x,k_x;y,-k_y)
\in T^*(M\times M)\setminus\{0\}
\ \middle|\
(x,k_x)\sim(y,k_y),\ k_x\triangleright0
\right\}.
$$

The condition has three ingredients.

| Ingredient | Meaning |
|---|---|
| Null relation | Singularities propagate along null geodesics. |
| Parallel transport | The two covectors are the same null momentum transported along the geodesic, with opposite sign at the second argument. |
| Positive-frequency orientation | The first covector is future-directed in the chosen time orientation. |

This is the curved-spacetime analogue of the spectrum condition. In flat spacetime, positive energy means that Fourier singularities lie in the future light cone. In curved spacetime there is no global momentum, but there are local cotangent directions and null bicharacteristics.

## The theorem to remember

Under the standard hypotheses for the linear scalar field on a globally hyperbolic spacetime, the following characterizations agree for quasifree states.

| Characterization | Content |
|---|---|
| Local Hadamard expansion | $\omega_2-H_\ell$ is smooth in convex normal neighborhoods. |
| Global Hadamard condition | The singularity has the correct globally propagated form. |
| Microlocal spectrum condition | $\operatorname{WF}(\omega_2)$ has the positive null-geodesic form above. |

Radzikowski's theorem is the reason the Hadamard condition became so useful in modern rigorous curved-spacetime QFT. It turns an expansion with local coordinates, transport equations, and $i\epsilon$ prescriptions into a clean statement about wavefront sets. It also makes clear why the condition is stable under propagation by the field equation.

For non-quasifree states, one usually asks for a microlocal spectrum condition on all $n$-point functions. Roughly, the allowed wavefront sets are built from future-directed causal covectors flowing through graphs connecting the insertion points. The two-point formula above is the simplest and most important case.

## Examples and non-examples

The Minkowski vacuum is Hadamard. In fact, the curved-spacetime condition was designed so that the short-distance singularity reduces locally to the familiar flat-vacuum singularity.

Finite-particle excitations of a Hadamard representation remain Hadamard, because adding finitely many smooth wave packets changes the two-point function by a smooth term. Thermal equilibrium states in many stationary situations are also Hadamard, under appropriate hypotheses.

The Bunch–Davies, or Euclidean, state for the free scalar field on de Sitter spacetime is the standard Hadamard de Sitter-invariant state in the usual mass ranges. By contrast, the other de Sitter $\alpha$-vacua often discussed formally have additional singularities, including antipodal singularity structure, and fail the microlocal Hadamard condition in the usual interacting-QFT sense.

A distribution that merely has the correct equal-time ultraviolet power counting is not automatically Hadamard. The full condition includes the Lorentzian $i\epsilon$ orientation and the propagation of singularities along null geodesics.

## Why renormalization needs Hadamard states

Composite fields involve products of distributions at coincident points. For example, the formal square $\Phi(x)^2$ is not defined by multiplying point fields. Hadamard states make a controlled subtraction possible:

$$
:\!\Phi^2\!:_M(x)
\sim
\lim_{y\to x}
\bigl(\Phi_M(x)\Phi_M(y)-H_\ell(x,y)\mathbf 1\bigr).
$$

This formula is schematic, because the rigorous object is an operator-valued distribution smeared with test functions. The important point is that $H_\ell$ subtracts the universal singularity. The remainder is regular enough to define Wick powers, currents, and stress tensors after imposing additional local covariance and scaling conditions.

Hadamard states also provide the correct domain for perturbative algebraic QFT on curved spacetimes. Time-ordered products are built by extending distributions to diagonals; microlocal control is what tells us when products and extensions are meaningful.

## Common pitfalls

**Hadamard does not mean vacuum.** It is a short-distance regularity condition. A curved spacetime may admit many Hadamard states and no preferred one.

**The parametrix is not a two-point function.** $H_\ell$ captures the local singularity. It need not be positive, symmetric in the right way, or globally defined as a state.

**Smooth differences are not irrelevant.** The smooth part of $\omega_2$ contains real state-dependent physics. It is irrelevant only to the ultraviolet singularity class.

**The $i\epsilon$ prescription is not decorative.** It fixes the positive-frequency orientation. Ignoring it loses the distinction between a physically admissible singularity and its time-reversed or symmetric variants.

**Hadamard is stronger than dimensional ultraviolet counting.** Correct scaling near coincidence is not enough; the wavefront directions must also have the right causal orientation.

**A state can be symmetric but not Hadamard.** Large spacetime symmetry does not guarantee physical short-distance behavior. The de Sitter $\alpha$-vacua are the standard warning example.

**The condition is local but not trivial.** Locality does not mean one checks only a Taylor expansion at one point. Null propagation, positivity orientation, and smoothness of remainders are global enough to be highly constraining.

## Relations to other pages

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives the analytic language used in Radzikowski's formulation. [QFT in Curved Spacetime: Rigorous View](/rigorous-qft/locally-covariant-qft/qft-in-curved-spacetime-rigorous-view/) explains why curved-spacetime QFT uses classes of states instead of a preferred vacuum. [Stress Tensor from Local Covariance](/rigorous-qft/locally-covariant-qft/stress-tensor-from-local-covariance/) explains why the stress tensor is tied to metric response. [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) uses Hadamard subtraction to define Wick products and time-ordered products locally and covariantly.

## Research status

For scalar linear fields on globally hyperbolic spacetimes, the Hadamard condition is a mature and central part of rigorous curved-spacetime QFT. It is stable under propagation, admits microlocal characterization, and supports the construction of Wick polynomials, stress tensors, and perturbative interacting fields.

The condition has also been generalized to other linear fields, including spinor and vector fields, with modifications appropriate to their bundles, constraints, and gauge structure. In gauge theories, however, physical state spaces and observables often require BRST/BV or cohomological formulations.

For semiclassical gravity, Hadamard states are indispensable because $\langle T_{\mu\nu}\rangle$ must be renormalized. The coupled semiclassical Einstein equation remains mathematically delicate, especially regarding existence, stability, higher derivatives, and physical state selection.

For nonperturbative interacting QFT on general curved spacetimes, the Hadamard framework is a necessary local regularity input but not a complete construction of the theory.

## Exercises

### Exercise 1: Smooth difference of Hadamard two-point functions

Let $\omega$ and $\omega'$ be two Hadamard quasifree states for the same scalar field. Explain why $\omega_2-\omega_2'$ is smooth.

<details><summary><strong>Solution</strong></summary>

In every sufficiently small convex normal neighborhood, both two-point distributions have the same singular Hadamard form up to the same geometric parametrix:

$$
\omega_2=H_\ell+W_\omega,
\qquad
\omega_2'=H_\ell+W_{\omega'},
$$

with $W_\omega$ and $W_{\omega'}$ smooth. Therefore

$$
\omega_2-\omega_2'=W_\omega-W_{\omega'}
$$

is smooth locally. Smoothness is a local property, so the difference is smooth on $M\times M$. If two parametrices with different length scales or local choices are used, their difference is itself smooth, so the conclusion is unchanged.

</details>

### Exercise 2: Why finite-particle excitations preserve the Hadamard property

Starting with a Hadamard representation, explain why adding finitely many smooth one-particle wave packets does not change the Hadamard singularity class.

<details><summary><strong>Solution</strong></summary>

A finite-particle excitation changes the two-point function by terms built from finitely many smooth classical solutions or wave packets. Such terms are smooth functions or smooth bisolutions on $M\times M$. The wavefront set is insensitive to adding smooth terms, and the local Hadamard singularity $H_\ell$ is unchanged. Hence the excited state remains Hadamard.

</details>

### Exercise 3: Why the Hadamard parametrix is not a state

The expression $H_\ell(x,y)$ contains the singular part of the two-point function. Give two reasons why $H_\ell$ itself should not be identified with $\omega_2$.

<details><summary><strong>Solution</strong></summary>

First, $H_\ell$ is locally constructed in a convex normal neighborhood and is not generally a globally defined bidistribution on all of $M\times M$. Second, a two-point function of a state must satisfy positivity and the correct commutator antisymmetric part. A parametrix is built to reproduce the singularity of the differential equation; it is not built to satisfy the positivity condition of a quantum state. The missing smooth part $W_\omega$ is where state-dependent global information enters.

</details>

## References

### Standard references

- Bernard S. Kay and Robert M. Wald, "Theorems on the Uniqueness and Thermal Properties of Stationary, Nonsingular, Quasifree States on Spacetimes with a Bifurcate Killing Horizon," *Physics Reports* **207** (1991), 49–136. DOI: [10.1016/0370-1573(91)90015-E](https://doi.org/10.1016/0370-1573(91)90015-E).
- Marek J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. DOI: [10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- Romeo Brunetti, Klaus Fredenhagen, and Martin Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. DOI: [10.1007/BF02099626](https://doi.org/10.1007/BF02099626), arXiv: [gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056).
- Stefan Hollands and Robert M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. DOI: [10.1016/j.physrep.2015.02.001](https://doi.org/10.1016/j.physrep.2015.02.001), arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).

### Further reading

- Robert M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- Hanno Sahlmann and Rainer Verch, "Microlocal Spectrum Condition and Hadamard Form for Vector-Valued Quantum Fields in Curved Spacetime," *Reviews in Mathematical Physics* **13** (2001), 1203–1246. arXiv: [math-ph/0008029](https://arxiv.org/abs/math-ph/0008029).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. DOI: [10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Romeo Brunetti, Klaus Fredenhagen, and Stefan Hollands, "A Remark on Alpha Vacua for Quantum Field Theories on de Sitter Space," *Journal of High Energy Physics* **2005** (2005), 063. arXiv: [hep-th/0503022](https://arxiv.org/abs/hep-th/0503022).

## Version history

- **2026-06-29:** Initial polished draft.
