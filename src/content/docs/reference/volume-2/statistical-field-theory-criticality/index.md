---
title: "Statistical Field Theory and Criticality"
description: "Chapter overview for Landau–Ginzburg theory, statistical-to-field-theory limits, mean-field theory, Gaussian and Wilson–Fisher fixed points, critical exponents, finite-size scaling, and BKT previews in the Renormalization, RG, and EFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Altland and Simons 2023, ch. 6; Coleman 1985, Dilatations; Schwartz 2014, ch. 23."
topics:
  - statistical field theory
  - critical phenomena
  - Landau–Ginzburg theory
  - Ising universality
  - mean-field theory
  - Wilson–Fisher fixed point
  - finite-size scaling
canonicalTopics:
  - statistical-field-theory
  - critical-phenomena
  - landau-ginzburg-wilson
  - universality-classes
researchStatus:
  established:
    - "The Landau–Ginzburg–Wilson description, RG explanation of universality, epsilon expansion, scaling relations, and finite-size scaling are standard parts of modern critical phenomena."
  active:
    - "Precision critical exponents, conformal-bootstrap data, non-Landau transitions, disorder, long-range interactions, nonequilibrium criticality, and topological or gauge-theoretic critical points remain active research directions."
---

## Summary

**Statistical Field Theory and Criticality** is the chapter where the renormalization group shows its second face. Earlier chapters developed renormalization as the logic of short-distance singularities and scale-dependent couplings in quantum field theory. This chapter explains why the same ideas organize magnets, fluids, lattice models, polymers, superfluids, and many other systems near continuous phase transitions.

The central question is:

> How can many microscopically different systems have the same long-distance singular behavior near a critical point?

The answer is Wilsonian:

$$
\text{microscopic model}
\longrightarrow
\text{coarse graining}
\longrightarrow
\text{RG flow}
\longrightarrow
\text{fixed point}
\longrightarrow
\text{universal critical behavior}.
$$

Near a critical point, the correlation length $\xi$ becomes much larger than the microscopic spacing $a$:

$$
\xi\gg a.
$$

The system forgets most microscopic details. The surviving data are dimension, symmetry, locality, range of interactions, conserved quantities, and the relevant perturbations away from the fixed point. That is the conceptual miracle this chapter is built around.

:::note[Why this chapter is in this volume]
Critical phenomena are not an optional analogy for renormalization. They are one of the places where the Wilsonian meaning of renormalization is clearest: RG flow, fixed points, relevant directions, anomalous dimensions, universality, scaling functions, and irrelevant corrections can all be seen directly in statistical systems.
:::

## Prerequisites

You should know the basic ideas from [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/), especially coarse graining, theory space, relevant and irrelevant perturbations, and universality. You should also know [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/).

For calculations, you should be comfortable with Gaussian integrals, Fourier transforms, dimensional analysis, and the Euclidean path-integral viewpoint. You do not need a full course in condensed matter physics before entering this chapter; the necessary statistical-mechanics language is introduced as needed.

## What this chapter is for

This chapter gives a field-theoretic bridge from microscopic statistical systems to continuum RG fixed points. It teaches how to translate lattice or thermodynamic questions into Euclidean correlation functions and then use RG to understand singular behavior.

The chapter has four jobs.

First, it explains how a continuum field theory emerges from a statistical system. The Ising model, for example, is not literally a scalar field theory at the lattice scale. But near criticality, its long-distance fluctuations are described by a scalar order-parameter field with a local Euclidean action.

Second, it shows why mean-field theory is both useful and wrong in low dimensions. Mean-field theory captures the saddle-point structure but misses the importance of fluctuations when the dimension is below the upper critical dimension.

Third, it connects the Gaussian and Wilson–Fisher fixed points. The Gaussian fixed point is the natural starting point near four dimensions; the Wilson–Fisher fixed point is the interacting fixed point controlling the Ising and $O(N)$ universality classes below four dimensions.

Fourth, it introduces finite-size scaling and BKT physics as reminders that not all critical behavior is captured by the simplest power-law story.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/) | The continuum order-parameter action and the logic of local terms allowed by symmetry. |
| 2 | [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/) | How a discrete spin model becomes a scalar statistical field theory near criticality. |
| 3 | [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/) | Why $\phi^4$ theory is the minimal interacting theory near the upper critical dimension. |
| 4 | [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) | The saddle-point approximation, order parameter, susceptibility, and mean-field exponents. |
| 5 | [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/) | Free-field scaling, engineering dimensions, and the classification of perturbations. |
| 6 | [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/) | The interacting fixed point below four dimensions and first universal exponents. |
| 7 | [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/) | Why $\xi$ is the central scale near criticality and how it diverges. |
| 8 | [Susceptibility and Critical Exponents](/renormalization-rg-eft/statistical-field-theory-criticality/susceptibility-and-critical-exponents/) | The observable singularities and their exponent notation. |
| 9 | [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/) | How finite systems reveal critical data and round true singularities. |
| 10 | [BKT Transition Preview](/renormalization-rg-eft/statistical-field-theory-criticality/kt-transition-preview/) | A preview of topological criticality with essential scaling rather than ordinary power laws. |

After this path, you should be able to explain why the Ising model, scalar $\phi^4$ theory, and a uniaxial magnet can share critical exponents; derive mean-field exponents; identify the upper critical dimension of $\phi^4$ theory; interpret the Wilson–Fisher fixed point; and use finite-size scaling forms.

## Landmarks

| Landmark | Meaning | Where it appears next |
|---|---|---|
| Order parameter | A long-distance field distinguishing phases, such as magnetization $\phi$ in an Ising-like system. | Landau–Ginzburg theory, spontaneous symmetry breaking, critical exponents. |
| Correlation length $\xi$ | The length scale over which fluctuations remain correlated. | Scaling, finite-size scaling, continuum limits. |
| Reduced temperature $t$ | A relevant perturbation measuring distance from criticality, often $t=(T-T_c)/T_c$. | Critical exponents, RG linearization. |
| External field $h$ | Source conjugate to the order parameter. | Susceptibility, equation of state, scaling functions. |
| Upper critical dimension | Dimension above which mean-field exponents hold up to logarithmic corrections. | Gaussian fixed point, $\epsilon$ expansion. |
| Wilson–Fisher fixed point | Interacting fixed point controlling many critical systems below four dimensions. | Epsilon expansion, universality classes, CFT and bootstrap. |
| Irrelevant correction | A perturbation that dies under RG but controls corrections to scaling. | Finite-size scaling, crossover, dangerously irrelevant operators. |
| Scaling function | A universal function of dimensionless ratios such as $L/\xi$ or $h/t^{\beta\delta}$. | Finite-size scaling and equation of state. |
| BKT transition | Critical behavior driven by vortex unbinding with essential rather than power-law scaling. | Two-dimensional systems, compact bosons, topological defects. |

The major conceptual move is this: singular thermodynamics comes from an infrared fixed point, not from a microscopic singularity in the Hamiltonian.

## The basic dictionary

Many pages in this chapter use the Euclidean statistical-field-theory dictionary.

| Statistical mechanics | Euclidean field theory |
|---|---|
| Partition function $Z$ | Functional integral $\int\mathcal D\phi\,e^{-S_E[\phi]}$ |
| Free energy $F=-T\log Z$ | Generating functional of connected diagrams |
| Spin correlation $\langle s_i s_j\rangle$ | Field correlator $\langle\phi(x)\phi(0)\rangle$ |
| Correlation length $\xi$ | Inverse mass gap of Euclidean two-point function |
| Critical point | RG fixed point plus relevant tuning |
| Temperature deviation $t$ | Relevant scalar coupling, often mass term $r\phi^2$ |
| Magnetic field $h$ | Source for the order parameter $\phi$ |
| Lattice spacing $a$ | UV cutoff of the continuum description |

For example, the Landau–Ginzburg action for a scalar order parameter is commonly written

$$
S_E[\phi]=\int d^d x\left[
\frac12(\nabla\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4-h\phi
\right].
$$

This is not a microscopic identity for every magnet. It is a long-distance effective description. The terms are chosen by locality, symmetry, and relevance.

## Recommended routes

### Core critical-phenomena route

Start here if your goal is to understand universality, exponents, and RG in statistical systems:

$$
\text{Landau–Ginzburg}
\longrightarrow
\text{mean field}
\longrightarrow
\text{Gaussian fixed point}
\longrightarrow
\text{Wilson–Fisher fixed point}
\longrightarrow
\text{critical exponents}.
$$

This route is the most direct bridge from the previous fixed-point chapters.

### Particle-theory route

Start here if you know relativistic QFT but not statistical mechanics. Read [Phi-Four Near Four Dimensions](/renormalization-rg-eft/statistical-field-theory-criticality/phi-four-near-four-dimensions/) together with [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/). The goal is to see how a familiar Euclidean scalar field theory becomes a theory of critical exponents rather than scattering amplitudes.

### Condensed-matter route

Start here if you know phase transitions but want the field-theory organization. Read [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/), [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/), and [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/) before returning to the perturbative $\epsilon$ expansion.

### Advanced route

After the basic route, continue to the CFT and Bootstrap volume. Critical fixed points are conformal field theories in many important cases, and modern high-precision critical exponents often come from bootstrap methods, lattice simulations, high-order perturbation theory, or resummation.

## Common confusions

**The Landau–Ginzburg field is not necessarily a microscopic field.** In an Ising magnet, $\phi(x)$ is a coarse-grained magnetization, not a literal lattice spin at a single site.

**Mean-field theory is not the same as RG.** Mean-field theory is a saddle-point approximation. RG explains when fluctuations invalidate it and how universal scaling emerges.

**A divergent correlation length is not a UV divergence.** Critical singularities are infrared phenomena. They come from large distances, not from arbitrarily short distances.

**Universality does not mean everything is universal.** Exponents, scaling functions, and amplitude ratios can be universal. Critical temperatures, microscopic amplitudes, lattice spacings, and many normalization choices are not.

**The upper critical dimension is not a dimension where the theory stops existing.** It is the dimension above which certain interactions are irrelevant at the Gaussian fixed point and mean-field behavior becomes correct up to possible logarithmic corrections.

**The Wilson–Fisher fixed point is not just a small correction to mean-field theory in three dimensions.** The $\epsilon$ expansion begins near four dimensions and must be extrapolated or resummed to reach $d=3$.

**BKT transitions are not ordinary second-order transitions with unusual exponents.** They have essential scaling and a line of fixed points; the ordinary power-law exponent story is not enough.

## Boundaries

This chapter does:

- explain the statistical-mechanics meaning of RG flow;
- introduce Landau–Ginzburg effective actions for order parameters;
- derive and interpret mean-field exponents;
- show how Gaussian and Wilson–Fisher fixed points control critical behavior;
- connect critical exponents, correlation functions, and finite-size scaling;
- preview BKT physics as a topological transition outside the simplest power-law framework.

This chapter does not try to do:

- provide a full condensed-matter field theory course, which belongs in the Matter, Statistical Physics, and Quantum Information volume;
- develop all of conformal field theory, which belongs in the CFT and Bootstrap volume;
- present lattice Monte Carlo algorithms, which belong in Computational QFT and Tools;
- prove rigorous scaling limits of lattice models, which belongs in Mathematical and Rigorous QFT;
- cover non-Landau deconfined criticality or topological phases in full, which belong in later symmetry, matter, and nonperturbative chapters.

## Where to go next

After this chapter, continue in two directions.

For the RG side, return to [Fixed Points and Critical Phenomena](/renormalization-rg-eft/fixed-points-critical-phenomena/) and [Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/) to connect the statistical examples to theory-space geometry.

For the physical statistical side, continue to the Matter, Statistical Physics, and Quantum Information volume, especially pages on Landau theory, many-body path integrals, response functions, finite-temperature field theory, superfluids, superconductors, and topological phases.

For the fixed-point side, continue to the CFT and Bootstrap volume. The Ising and $O(N)$ critical points are among the best examples of interacting conformal field theories beyond perturbation theory.

## References

### Standard first pass

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the original Wilsonian connection between critical phenomena, RG transformations, fixed points, and the $\epsilon$ expansion.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for a systematic field-integral treatment of critical phenomena, renormalization, and RG methods.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the chapter on the renormalization group and the ferromagnetic transition.

### QFT-oriented references

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, anomalous dimensions, Callan–Symanzik equations, and scaling.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the renormalization group chapter and Wilsonian RG discussion.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on dimensional analysis, the renormalization group, and effective field theory.

### Further directions

- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for a physics-first route through scaling and universality.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact and elegant treatment of scaling, finite-size effects, and two-dimensional methods.
- H. Kleinert and V. Schulte-Frohlinde, *Critical Properties of $\phi^4$-Theories*, for high-order perturbative and resummation methods.

## Version history

- 2026-06-18: First polished draft. Established the chapter doorway, reading path, landmarks, boundaries, and references for statistical field theory and criticality.
