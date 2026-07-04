---
title: "Microlocal Spectrum Condition"
description: "Defines the microlocal spectrum condition as the wavefront-set replacement for the positive-energy spectral condition in curved-spacetime QFT."
sidebar:
  label: "Microlocal Spectrum Condition"
  order: 3
level: Advanced
status: "Polished draft"
source: "Radzikowski; Brunetti–Fredenhagen–Köhler; Sahlmann–Verch; Fewster–Verch; Hollands–Wald."
topics:
  - microlocal spectrum condition
  - Hadamard states
  - wavefront sets
  - curved spacetime QFT
  - spectral condition
canonicalTopics:
  - microlocal-spectrum-condition
  - hadamard-state
  - wavefront-set
  - curved-spacetime-qft
researchStatus:
  established:
    - "The microlocal spectrum condition is the standard local replacement for the positive-energy spectral condition in QFT on curved spacetimes."
    - "For free scalar fields on globally hyperbolic spacetimes, Radzikowski's two-point wavefront-set condition is equivalent to the Hadamard singularity condition."
  active:
    - "Formulations for gauge fields, boundaries, defects, interacting theories, and nonstandard spacetime settings require additional structural assumptions."
---

## Summary

The spectral condition in Wightman QFT says, roughly, that energy–momentum lies in the closed future light cone. It depends on global spacetime translations and therefore has no literal form on a generic curved spacetime. The microlocal spectrum condition replaces global momentum support by local cotangent-direction support.

For a state $\omega$ with $n$-point distributions $\omega_n$, the condition constrains

$$
\operatorname{WF}(\omega_n)
\subset T^*M^n\setminus 0.
$$

The allowed covectors are the local, geometric analogues of positive-energy momenta: they are assembled from future-directed null covectors propagated along causal curves. For a free scalar two-point function, the central formula is Radzikowski's condition

$$
\operatorname{WF}(\omega_2)
=
\{(x,k_x;y,-k_y):(x,k_x)\sim(y,k_y),\ k_x\triangleright0\}.
$$

Here $(x,k_x)\sim(y,k_y)$ means that $x$ and $y$ are joined by a null geodesic and $k_y$ is the parallel transport of $k_x$ along it. The notation $k_x\triangleright0$ means future-directed. Sign conventions vary across sources; the invariant content is that the singular two-point function has one positive-frequency orientation, not both.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Microlocal spectrum condition as local positive frequency](/figures/rigorous-qft/microlocal-spectrum-condition.svg)

<figcaption>

The Wightman spectral condition uses global Fourier support in the future cone. The microlocal spectrum condition replaces this by future-directed cotangent singularities transported along null geodesics.

</figcaption>
</figure>

## Prerequisites

Read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) and [Products of Distributions](/rigorous-qft/microlocal-analysis-qft/products-of-distributions/) first. For the physical origin, compare [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) and [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/). The spacetime setting is the globally hyperbolic Lorentzian geometry introduced in [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/).

## Core idea

The usual spectral condition is global. In Minkowski space, translations let us Fourier transform correlation functions and ask where their momentum-space support lies. For the vacuum two-point function of a scalar field, positive frequency means only future mass-shell momenta appear.

A generic curved spacetime has no global translation group and no conserved total energy. But singularities of distributions are local. A wavefront set tells us which cotangent directions carry high-frequency singular behavior. The microlocal spectrum condition says: even without global momentum, the short-distance singularities of physically admissible states must have the same positive-frequency orientation as the Minkowski vacuum.

This is not merely aesthetic. It is the condition that makes Wick powers, time-ordered products, stress tensors, and perturbative constructions possible on curved backgrounds. It is also what separates physically acceptable states from arbitrary distributional states with the wrong short-distance singularities.

## Setup and conventions

Let $(M,g)$ be a smooth time-oriented globally hyperbolic Lorentzian spacetime. We use the same mostly-minus convention as elsewhere in this volume when a local orthonormal frame is chosen.

A state $\omega$ on a field algebra determines $n$-point distributions

$$
\omega_n(f_1,\ldots,f_n)
=
\omega\bigl(\phi(f_1)\cdots\phi(f_n)\bigr),
\qquad
\omega_n\in\mathcal D'(M^n),
$$

at least for the free scalar field and its algebraic variants. The microlocal spectrum condition is a constraint on the wavefront sets of these distributions.

For covectors, write $k\triangleright0$ when $k$ is future-directed causal after raising the index with the metric. For the two-point condition, write

$$
(x,k_x)\sim(y,k_y)
$$

when $x$ and $y$ lie on the same null geodesic and $k_y$ is obtained by parallel-transporting $k_x$ along that geodesic. The covectors are null because the leading singularities of solutions of normally hyperbolic equations propagate along null bicharacteristics.

## The two-point condition

For a Hadamard two-point function $\omega_2$ of a scalar Klein–Gordon field, the microlocal condition is

$$
\operatorname{WF}(\omega_2)
=
\{(x,k_x;y,-k_y):(x,k_x)\sim(y,k_y),\ k_x\triangleright0\}.
$$

This formula says four things at once.

First, singularities occur only along null-related pairs of points. This is the curved-spacetime version of the light-cone singularity of the Minkowski two-point function.

Second, the singular covectors are cotangent to the connecting null geodesic. The wavefront set does not point in arbitrary directions.

Third, the two arguments carry opposite covectors. This is forced by the fact that the singularity is a distribution in two variables and is locally a function of a geodesic separation variable.

Fourth, one orientation is selected. The first covector is future-directed in the convention above. That is the microlocal replacement for positive frequency.

The antisymmetric part of $\omega_2$ is fixed by the commutator function, while the symmetric part depends on the state. The Hadamard condition fixes the singular part but allows smooth state-dependent additions. Since adding a smooth function does not change the wavefront set, all Hadamard states have the same leading microlocal singularity.

:::note[Hadamard versus microlocal]
For free scalar fields on globally hyperbolic spacetimes, Radzikowski's theorem identifies the local Hadamard singularity condition with the above wavefront-set condition. In practice, the microlocal condition is often the cleaner statement because it is coordinate invariant and directly suited to products of distributions.
:::

## The n-point condition

The full microlocal spectrum condition constrains all $n$-point distributions. For each $n$,

$$
\operatorname{WF}(\omega_n)\subset\Gamma_n,
$$

where $\Gamma_n\subset T^*M^n\setminus0$ is a geometrically defined cone of allowed positive-frequency configurations.

A useful way to remember $\Gamma_n$ is as a graph condition. Draw a finite directed graph with vertices labeled by the points $x_1,\ldots,x_n$. Edges are mapped to causal curves, and covectors assigned to edges are future-directed and transported along the edge. At each vertex, the covector $k_i$ is the signed sum of the covectors on incident edges, with outgoing and incoming signs fixed consistently with the two-point convention. The allowed $n$-tuples are those obtainable in this way.

This formulation is the curved-spacetime analogue of the nested momentum-cone conditions on Minkowski Wightman functions. It does not require a global Fourier transform; it uses local propagation of singularities and the time orientation of the spacetime.

For a quasi-free Hadamard scalar state, all higher $n$-point functions are sums of products of $\omega_2$ by Wick's rule. The two-point microlocal condition, together with Hörmander's product criterion, controls the wavefront sets of these higher functions. For interacting perturbative theories, the same cone conditions are built into the state space and the construction of Wick and time-ordered products.

## Relation to the Wightman spectral condition

In Minkowski space, the Wightman spectral condition can be stated as support of Fourier transforms in future momentum cones. For example, translation invariance reduces the two-point function to a distribution of $x-y$, and positive energy says its Fourier transform is supported on the future mass shell or future cone.

The wavefront set of a distribution is not the same as Fourier support, but for high-frequency singular behavior the two are closely related. The microlocal spectrum condition extracts the part of the spectral condition that survives localization:

$$
\text{global positive energy}
\quad\longrightarrow\quad
\text{future-directed singular covectors}.
$$

This is weaker than having a conserved Hamiltonian bounded below, because a generic curved spacetime may not have such a Hamiltonian. It is stronger than saying the two-point function has the right singular support, because it fixes the orientation of the singularity.

Thus the condition is best read as a local positive-frequency condition, not as a global energy theorem.

## Why it matters for products

The microlocal spectrum condition was introduced because products of fields and Wick polynomials on curved spacetime need a replacement for the flat-space spectral condition. The product criterion asks whether opposite covectors occur at the same point. The microlocal spectrum condition prevents precisely the wrong combinations for many physically important products.

For example, Wick powers are constructed by subtracting the Hadamard two-point singularity. Time-ordered products are then built by extending distributions to diagonals. The allowed wavefront cones ensure that these operations can be formulated locally and covariantly.

This is one reason Hadamard states are not merely convenient. In curved-spacetime QFT, the Hadamard/microlocal spectrum condition is part of the definition of the physically acceptable state space for free fields and the starting point for perturbative interacting fields.

## Checks

**Minkowski vacuum check.** In flat spacetime the vacuum two-point function has positive-frequency singularities on the light cone. Its wavefront set has the Radzikowski form, with covectors oriented by the future cone.

**Smooth perturbation check.** If $\omega_2$ satisfies the two-point microlocal condition and $S\in C^\infty(M\times M)$, then $\omega_2+S$ has the same wavefront set. Smooth changes alter the state but not the universal short-distance singularity.

**Commutator check.** The antisymmetric part of the scalar two-point function is fixed by the causal propagator. The Hadamard condition selects which positive-frequency part may serve as the two-point function of a physical state.

**Curved-spacetime check.** The formula uses null geodesics and parallel transport, not Fourier modes. It therefore makes sense without a timelike Killing vector.

## Common pitfalls

**Confusing the condition with a Hamiltonian bound.** The microlocal spectrum condition is not a statement that a global Hamiltonian exists. It is a local statement about the wavefront sets of correlation functions.

**Keeping only the singular support.** Saying that singularities lie on the light cone is not enough. The condition also fixes the cotangent orientation of those singularities.

**Assuming every state is Hadamard.** Algebraic states can be non-Hadamard. Such states may exist as positive functionals but fail to support Wick powers, stress tensors, or perturbation theory with the desired local properties.

**Forgetting smooth state dependence.** The Hadamard singularity is universal, but the smooth part of $\omega_2$ contains physical state information.

**Applying the scalar formula blindly to gauge fields.** Gauge theories require constraints, ghosts, quotient structures, and sometimes indefinite auxiliary spaces. Their microlocal conditions must be formulated with the relevant gauge or BRST structure.

**Treating the graph condition as a Feynman diagram expansion.** The graph definition of $\Gamma_n$ is a geometric way to describe allowed covector sums. It is not a perturbative Feynman diagram expansion.

## Relations to other pages

- [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) gives the flat-spacetime positive-energy axiom that the microlocal condition generalizes.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) explains the singular-direction language used in the definition.
- [Products of Distributions](/rigorous-qft/microlocal-analysis-qft/products-of-distributions/) explains why wavefront cones control Wick products and time-ordered products.
- [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) explains the same physical state condition through the universal short-distance form of the two-point function.
- [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) uses Hadamard/microlocal input for local Wick products and time-ordered products.

## Research status

For scalar free fields on globally hyperbolic spacetimes, the equivalence between the Hadamard condition and the two-point microlocal spectrum condition is a standard theorem. The full microlocal spectrum condition for $n$-point functions is a standard framework in algebraic QFT on curved spacetimes and in perturbative algebraic QFT.

The active questions lie in extensions and interfaces: gauge fields and BRST complexes, boundary conditions, defects, states on nonstandard spacetime classes, interacting nonperturbative theories, and the precise relationship between microlocal admissibility and other physical selection principles.

## Exercises

### Exercise 1: Smooth changes do not change the condition

Let $\omega_2$ satisfy Radzikowski's two-point condition and let $S\in C^\infty(M\times M)$. Show that $\omega_2+S$ has the same wavefront set.

<details>
<summary><strong>Solution</strong></summary>

Smooth functions have empty wavefront set. The wavefront set of a sum satisfies

$$
\operatorname{WF}(u+v)
\subset
\operatorname{WF}(u)\cup\operatorname{WF}(v),
$$

with the caveat that cancellation can reduce singularities. Adding a smooth $S$ cannot add singular directions. It also cannot cancel the universal Hadamard singularity unless that singularity was already absent, which it is not for a two-point function with the stated wavefront set. Thus the singular directions remain those of $\omega_2$.

</details>

### Exercise 2: Why singular support is not enough

Explain why the statement "the two-point function is singular only on the light cone" is weaker than the microlocal spectrum condition.

<details>
<summary><strong>Solution</strong></summary>

Singular support specifies only the base points $(x,y)$ where the distribution is not smooth. The microlocal spectrum condition specifies the covectors over those points. Two distributions may have the same light-cone singular support but opposite frequency orientations. Only the wavefront-set condition selects the positive-frequency orientation corresponding to the spectral condition.

</details>

### Exercise 3: Flat-space interpretation

In Minkowski space, why should the future orientation of $k_x$ in

$$
\operatorname{WF}(\omega_2)
=\{(x,k_x;y,-k_y):(x,k_x)\sim(y,k_y),\ k_x\triangleright0\}
$$

be regarded as a local replacement for positive energy?

<details>
<summary><strong>Solution</strong></summary>

Translation invariance lets the two-point function be written in terms of $x-y$ and Fourier transformed. Positive energy restricts the high-frequency support to future-directed mass-shell or light-cone momenta. The wavefront set records exactly the high-frequency directions visible after localization. Therefore, when the covector at the first argument is future-directed, the singularity has the same local orientation as a positive-energy Minkowski two-point function.

</details>

### Exercise 4: Why the condition helps products

Use the product criterion to explain why controlling the signs of singular covectors is relevant for defining Wick products.

<details>
<summary><strong>Solution</strong></summary>

The product criterion fails when opposite covectors occur at the same base point. Wick products and their correlation functions require multiplying distributions obtained from two-point functions and then restricting or extending near diagonals. If the two-point functions had arbitrary singular directions, opposite pairs could appear and products would be undefined. The microlocal spectrum condition restricts the allowed directions so that the necessary products are either defined directly or have controlled extension ambiguities.

</details>

## References

### Standard first pass

- Marek J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. [DOI: 10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- Romeo Brunetti, Klaus Fredenhagen, and Martin Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. [arXiv:gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056), [DOI: 10.1007/BF02099626](https://doi.org/10.1007/BF02099626).
- Christian Bär, Nicolas Ginoux, and Frank Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*, for globally hyperbolic geometry, Green operators, and quantization background.

### Deeper references

- Hanno Sahlmann and Rainer Verch, "Microlocal Spectrum Condition and Hadamard Form for Vector-Valued Quantum Fields in Curved Spacetime," *Reviews in Mathematical Physics* **13** (2001), 1203–1246. [arXiv:math-ph/0008029](https://arxiv.org/abs/math-ph/0008029), [DOI: 10.1142/S0129055X01001010](https://doi.org/10.1142/S0129055X01001010).
- Ko Sanders, "Equivalence of the (Generalised) Hadamard and Microlocal Spectrum Condition for (Generalised) Free Fields in Curved Spacetime," *Communications in Mathematical Physics* **295** (2010), 485–501. [arXiv:0903.1021](https://arxiv.org/abs/0903.1021), [DOI: 10.1007/s00220-009-0900-7](https://doi.org/10.1007/s00220-009-0900-7).
- Romeo Brunetti and Klaus Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [DOI: 10.1007/s002200050004](https://doi.org/10.1007/s002200050004).

## Version history

- **2026-07-01:** Initial page defining the microlocal spectrum condition and its relation to Hadamard states.
