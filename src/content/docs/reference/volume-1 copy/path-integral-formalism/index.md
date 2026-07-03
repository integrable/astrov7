---
title: "Path Integral Formalism"
description: "Chapter overview for path integrals in the Foundations of QFT volume: finite Gaussians, quantum-mechanical path integrals, scalar and fermionic functional integrals, sources, Euclidean continuation, semiclassical expansion, and measure caveats."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§6–9 and 43–44; Coleman 2019, chs. 28–32; Weinberg 1995, Vol. I, ch. 9; Zee 2010, chs. I.2 and II.5."
topics:
  - path integrals
  - functional integrals
  - generating functionals
  - Euclidean QFT
  - Grassmann variables
  - semiclassical expansion
canonicalTopics:
  - path-integral-formalism
  - functional-integral
  - generating-functional
  - euclidean-qft
  - grassmann-integration
researchStatus:
  established:
    - "Perturbative path integrals, Gaussian functional integrals, source differentiation, Grassmann integration, and Wick rotation are standard foundations of QFT."
    - "Continuum functional integrals must be interpreted through regulators, analytic continuation, or reconstruction data rather than as ordinary infinite-dimensional Riemann integrals."
  active:
    - "Gauge-field measures, real-time path integrals, nonperturbative continuum definitions, sign problems, and rigorous constructive path integrals require later and more specialized treatments."
---

Path Integral Formalism is the chapter in the Foundations of QFT volume where quantum dynamics is reorganized as an integral over histories and fields. The central object is a source-dependent functional such as

$$
Z[J]=\frac{1}{\mathcal N}\int \mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^4x\,J(x)\phi(x)\right),
$$

but the chapter is just as much about how to use this expression responsibly.

The chapter exists because path integrals make locality, covariance, perturbation theory, Euclidean continuation, semiclassical physics, fermion determinants, and source-generated correlators unusually visible. They are not a different quantum theory. They are a representation of quantum theory with its own strengths and its own technical traps.

Read this chapter when you want to understand how finite Gaussian integrals grow into scalar and fermionic functional integrals, how $Z[J]$ produces correlation functions, and why the measure is always part of the physics.

## Prerequisites

You should know [Correlation Functions and Propagators](/foundations/correlators-and-propagators/), especially time ordering and connected correlators, and the free-field formulas in [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/). It also helps to have read [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) and [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/).

The chapter uses the qft.org [Conventions and Normalizations](/foundations/conventions-and-normalizations/) for Fourier transforms, the mostly-minus metric, and the scalar propagator denominator $p^2-m^2+i\epsilon$.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/) | The algebra of Gaussian integrals, determinants, sources, and completing the square. |
| 2 | [Quantum-Mechanical Path Integral](/foundations/path-integral-formalism/quantum-mechanical-path-integral/) | The time-sliced route from transition amplitudes to sums over paths. |
| 3 | [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) | The free scalar functional integral and its propagator as an inverse quadratic operator. |
| 4 | [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) | How $Z[J]$, $W[J]$, and functional derivatives generate full and connected correlators. |
| 5 | [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) | Wick rotation, Euclidean actions, Schwinger functions, and the statistical-mechanics bridge. |
| 6 | [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) | Anticommuting variables, Berezin integration, and fermionic Gaussian rules. |
| 7 | [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) | Dirac fields as Grassmann functional integrals, determinants, propagators, and closed-loop signs. |
| 8 | [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) | Saddles, quadratic fluctuations, one-loop determinants, and instanton previews. |
| 9 | [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) | Regulators, Jacobians, anomalies, zero modes, and why $\mathcal D\phi$ is not harmless notation. |

After this path, you should be able to derive free Gaussian generating functionals, generate correlators with sources, distinguish Lorentzian and Euclidean integrals, and explain why measures and regulators matter.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Finite Gaussian integral | Completing the square gives inverse matrices, determinants, and source contractions. | Free field path integrals, loop determinants. |
| `$\int \mathcal D\phi\,e^{iS[\phi]}$` | The formal Lorentzian field integral organizes quantum amplitudes and perturbation theory. | Wick expansion, Feynman diagrams. |
| `$Z[J]$` | The source functional generates full time-ordered correlators. | Connected correlators, response functions. |
| `$W[J]=-i\log Z[J]$` | The logarithm of the source functional generates connected correlators in Lorentzian conventions. | Connected diagrams, effective action. |
| Wick rotation | Analytic continuation trades oscillatory Lorentzian integrals for Euclidean weights when justified. | Statistical QFT, lattice previews, reflection positivity. |
| Grassmann integration | Fermion path integrals use anticommuting variables and produce determinants or Pfaffians. | Fermion loops, anomalies, BRST previews. |
| Semiclassical expansion | Saddles plus quadratic fluctuations approximate path integrals beyond pure perturbation around zero. | Instantons, tunneling, nonperturbative QFT. |
| Measure Jacobian | A change of variables can contribute to the quantum theory through the measure. | Anomalies, gauge fixing, topology. |

## Common confusions

**The path integral is not an ordinary integral over all functions.** In continuum QFT, $\mathcal D\phi$ is formal until a regulator, measure construction, or reconstruction framework is specified. Perturbation theory can still use it systematically because every formal step has a regulated version.

**Euclidean QFT is not just Lorentzian QFT with $t$ renamed.** Wick rotation changes the analytic domain and the type of boundary data. Recovering Lorentzian physics requires reflection positivity, analytic continuation, or additional real-time methods.

**The determinant is not a decorative normalization.** Gaussian integration over fluctuations produces determinants, and fermionic integration produces inverse determinant behavior depending on conventions. These factors carry loop effects and can change the physics.

**Grassmann variables are not classical fermion values.** They are algebraic devices that reproduce fermionic signs and anticommutators in functional integrals. They should not be interpreted as ordinary numerical field configurations.

**The measure can break a classical symmetry.** A classical action may be invariant under a transformation while the regulated measure is not. This is one path to anomalies and one reason measure language must be handled carefully.

## Boundaries

This chapter does:

- introduce finite and functional Gaussian integrals;
- explain scalar and fermionic source functionals;
- distinguish Lorentzian and Euclidean path integrals;
- preview saddles, determinants, and measure effects.

This chapter does not try to do:

- full gauge fixing and Faddeev–Popov quantization;
- BRST, BV, or anomaly theory in full detail;
- rigorous constructive field theory;
- lattice Monte Carlo or real-time Schwinger–Keldysh methods.

Those topics belong in later chapters and volumes on gauge theory, symmetry and anomalies, nonperturbative QFT, mathematical QFT, computational QFT, and matter or statistical physics.

## Where to go next

For the next Foundations step, go to [Interactions and Wick Expansion](/foundations/interactions-and-wick-expansion/), where source functionals, contractions, and Gaussian integrals become perturbative diagrams. For gauge-field measures, continue later to [Gauge Fields: First Principles](/foundations/gauge-fields-first-principles/).

For Euclidean field theory, critical phenomena, and lattice definitions, this chapter eventually hands off to the Matter, Statistical Physics, and Quantum Information and Nonperturbative QFT volumes.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, for a direct route from finite path integrals to scalar, interacting, and fermionic functional integrals.
- Zee, *Quantum Field Theory in a Nutshell*, for physical motivation and compact path-integral intuition.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for a careful lecture-style development of functional methods and perturbation theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. I, for path integrals, generating functionals, and their relation to perturbative QFT.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean functional integrals, statistical-field-theory language, and renormalization-oriented applications.

## Version history

- **2026-06-10:** Standardized chapter overview using the QFT.org chapter-index template.
