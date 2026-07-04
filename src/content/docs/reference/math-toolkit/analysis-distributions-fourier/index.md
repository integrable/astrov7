---
title: "Analysis, Distributions, and Fourier Methods"
description: "Chapter overview for the analytic language of test functions, distributions, Fourier transforms, singular kernels, and Green functions used throughout quantum field theory."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Standard distribution theory and Fourier analysis, with QFT applications to propagators, Green functions, canonical commutators, and pole prescriptions."
topics:
  - distributions
  - Fourier analysis
  - Green functions
  - singular kernels
  - QFT analysis
canonicalTopics:
  - distributions
  - fourier-methods
  - green-functions
  - mathematical-analysis-for-qft
researchStatus:
  established:
    - "Distributions and Fourier methods are standard mathematical infrastructure for local quantum field theory, perturbation theory, spectral representations, and response functions."
  active:
    - "The rigorous treatment of products, restrictions, microlocal singularities, and distribution-valued quantum fields remains important in mathematical QFT and perturbative algebraic QFT."
---

Analysis, Distributions, and Fourier Methods is the chapter in the Mathematical Toolkit volume where singular expressions become controlled mathematical objects. Delta functions, principal values, Green functions, propagators, and equal-time commutators are not ordinary functions with unusual pointwise behavior. They are distributions: objects defined by how they act on smooth test functions.

The chapter also fixes the Fourier technology behind momentum space. Once a differential operator becomes multiplication by a polynomial in momentum, many QFT calculations become possible. But the price is precision: factors of $2\pi$, pole prescriptions, boundary values, convergence, and contact terms matter.

The guiding principle is:

$$
\text{singular formula} \quad \longrightarrow \quad \text{well-defined pairing with test functions}.
$$

Read this chapter whenever a calculation contains $\delta^{(d)}(x)$, $1/(x\pm i0)$, $\theta(t)$, $\operatorname{PV}(1/x)$, $G(x,y)$, $\int d^dp/(2\pi)^d$, or a propagator denominator that needs an $i\epsilon$ prescription.

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/), especially the Fourier-transform and distribution conventions. You should also be comfortable with multivariable calculus, integration by parts, and the idea that a differential equation can be solved by inverting an operator with boundary conditions.

No prior functional analysis is required for the first pass. The chapter introduces test functions and distributions from scratch, then points to functional analysis only when domain, spectrum, or operator topology becomes unavoidable.

## Reading path

Start with [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/). It explains the central move: replace a singular expression by a continuous linear functional on test functions. Everything else in this chapter refines that move.

A natural first reading order is:

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) | Define distributions, weak equality, derivatives, delta functions, principal values, and QFT smearing. |
| 2 | Delta Functions | Treat $\delta$ as a distribution, not as an infinitely tall function; derive change-of-variables rules and constraint deltas. |
| 3 | Test Functions and Tempered Distributions | Explain $C_c^\infty$, Schwartz functions, tempered distributions, and why Fourier transforms need them. |
| 4 | Fourier Transform Conventions | Compare Lorentzian, Euclidean, spatial, and finite-volume conventions without losing $2\pi$ factors. |
| 5 | Convolution | Explain kernels, translation invariance, products in momentum space, and solutions of linear equations. |
| 6 | Principal Values | Derive principal-value distributions and boundary-value identities such as $1/(x\pm i0)$. |
| 7 | Distributions in QFT | Apply the formalism to fields, propagators, commutators, spectral densities, contact terms, and Ward identities. |
| 8 | Sobolev Spaces Preview | Give the minimal PDE language needed for elliptic estimates, regulators, finite elements, and constructive questions. |

A quick checkpoint before moving on: make sure you can explain why $\delta(0)$ is not a number, why $\partial_i\delta$ is defined by integration by parts, and why $1/(p^2-m^2+i0)$ is a distribution rather than an ordinary reciprocal.

**Checkpoint exercise.** Suppose $T$ is a distribution and $f$ is a smooth function. What is the natural definition of $fT$?

<details><summary><strong>Solution</strong></summary>

Define $fT$ by moving the smooth factor onto the test function:

$$
\langle fT,\varphi\rangle=\langle T,f\varphi\rangle.
$$

This works because $f\varphi$ is again a test function when $\varphi$ is. The same definition does not allow one to multiply two arbitrary distributions, because there is no general way to make $T\varphi$ into a test function when $T$ itself is singular.

</details>

**Checkpoint exercise.** In Euclidean convention, $f(x)=\int_k e^{ik\cdot x}\widehat f(k)$. What should $\widehat{\partial_i f}(k)$ be?

<details><summary><strong>Solution</strong></summary>

Integrating by parts,

$$
\widehat{\partial_i f}(k)
=\int d^dx\,e^{-ik\cdot x}\partial_i f(x)
=ik_i\widehat f(k),
$$

assuming $f$ decays fast enough, or distributionally if $f$ is a tempered distribution. This is one reason Fourier methods are so powerful: differentiation becomes multiplication by momentum.

</details>

## Landmarks

The main landmarks of the chapter are these.

| Landmark | Meaning | Where used next |
|---|---|---|
| Test function | A smooth, controlled probe used to measure a singular object. | Smearing fields and correlators. |
| Distribution | A continuous linear functional on test functions. | Delta functions, propagators, commutators, spectral densities. |
| Weak equality | Equality after pairing with every test function. | The actual meaning of many QFT identities. |
| Distributional derivative | Differentiation defined by integration by parts. | Conservation laws, Ward identities, equations of motion with contact terms. |
| Tempered distribution | A distribution compatible with Schwartz functions and Fourier transform. | Momentum-space QFT on flat spacetime. |
| Principal values and boundary values | Prescriptions for singular integrals and limits from complexified variables. | Dispersion relations, $i\epsilon$ prescriptions, causal response. |
| Convolution | The operation that turns translation-invariant kernels into multiplication in momentum space. | Green functions, loop integrals, response functions. |
| Contact term | A distribution supported at coincident points. | Ward identities, anomalies, counterterms, operator products. |

The deepest lesson is not that distributions make singular expressions legal. It is that they reveal which parts of a formula are local, which are nonlocal, and which are convention- or scheme-dependent.

## Common confusions

**“The delta function is an infinitely tall function.”** That picture is sometimes useful for intuition, but it is not the definition. The definition is $\langle\delta_y,\varphi\rangle=\varphi(y)$. The symbol $\delta(0)$ is usually a warning sign that a distribution has been treated as a pointwise function.

**“A distribution has a value at each point.”** In general it does not. A distribution is known by all of its pairings with test functions. Some distributions come from ordinary functions, but many important ones do not.

**“Fourier transforms are just changes of notation.”** They are more than notation. Fourier transformation changes differentiation into multiplication, convolution into multiplication, support properties into analyticity properties, and boundary conditions into pole prescriptions.

**“Green function means propagator.”** A Green function is a distributional inverse of an operator together with boundary conditions. A propagator is a QFT-specific two-point object or kernel. Many propagators are Green functions, but the word also carries physical information about time ordering, causality, vacuum choice, or thermal state.

**“Products of distributions are automatically allowed.”** They are not. Multiplying a distribution by a smooth function is canonical. Multiplying two singular distributions generally needs extra structure, a regulator, or a renormalization prescription.

**“Contact terms are ignorable.”** Contact terms vanish at separated points, but they often control Ward identities, anomalies, equal-time commutators, operator mixing, and conservation laws. They are the small print that can run the whole contract.

## Boundaries

This chapter is not a full course in real analysis, functional analysis, or PDE theory. It introduces enough distribution theory to support QFT calculations and enough Fourier analysis to make propagators, Green functions, and momentum-space manipulations honest.

The chapter does not attempt a theorem-first treatment of wavefront sets, microlocal analysis, Sobolev estimates, or renormalized products of distributions. Those appear later only as previews or handoffs to rigorous QFT and advanced perturbative methods.

It also does not replace the physics pages on propagators, canonical quantization, LSZ reduction, loop integrals, response theory, or spectral representations. Those pages use the tools developed here in their physical settings.

## Where to go next

After the [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) page, the next two technical pages should be Delta Functions and Fourier Transform Conventions. Together they remove the most common normalization traps in free-field quantization, scattering, and path integrals.

If you are reading Foundations of QFT, continue from this chapter to Gaussian integrals and variational derivatives. If you are reading perturbation theory, prioritize Fourier transforms, principal values, and convolution. If you are reading anomalies, CFT, or rigorous QFT, do not skip contact terms.

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for the physicist's use of Fourier transforms, delta functions, propagators, and momentum-space normalization throughout perturbative QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical Green-function, propagator, $i\epsilon$, and operator-product identities in calculations.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for the role of delta functions, principal values, relativistic normalization, and distributions in scattering and field theory.

### Deeper references

- L. Schwartz, *Théorie des distributions*, for the original source of distribution theory.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for a classic reference on generalized functions and Fourier transforms.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for distributions, singular support, wavefront sets, and microlocal analysis.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for fields as operator-valued distributions in axiomatic QFT.

## Version history

- **2026-06-23:** Initial polished draft. Created as the chapter overview for the Analysis, Distributions, and Fourier Methods chapter, with local checkpoint exercises.
