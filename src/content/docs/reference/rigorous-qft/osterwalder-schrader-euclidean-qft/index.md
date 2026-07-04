---
title: "Osterwalder–Schrader and Euclidean QFT"
description: "Chapter overview for Euclidean correlation functions, Schwinger functions, reflection positivity, and Osterwalder–Schrader reconstruction in rigorous QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Schwinger; Symanzik; Osterwalder–Schrader; Nelson; Glimm–Jaffe; Simon."
topics:
  - Osterwalder–Schrader axioms
  - Euclidean QFT
  - Schwinger functions
  - reflection positivity
  - reconstruction
canonicalTopics:
  - osterwalder-schrader-qft
  - euclidean-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "The Osterwalder–Schrader framework gives a theorem-level bridge from suitable Euclidean Schwinger functions to Lorentzian Wightman QFT."
  active:
    - "Constructing nontrivial continuum Schwinger functions satisfying the full Euclidean requirements remains difficult in important interacting and gauge-theoretic models."
---

Osterwalder–Schrader and Euclidean QFT is the chapter in the Mathematical and Rigorous QFT volume where imaginary time becomes a theorem-level tool. Instead of starting from Hilbert-space fields on Minkowski spacetime, this chapter starts from Euclidean correlation distributions on $\mathbb R^d$.

The chapter explains why Euclidean methods are powerful but delicate. The replacement $t=-i\tau$ turns oscillatory evolution into decay and opens the door to probability, statistical mechanics, constructive methods, and lattice regularization. But a Euclidean theory reconstructs a Lorentzian quantum theory only when it satisfies the right positivity condition: reflection positivity.

Read this chapter when you want to understand what a Schwinger function is, why reflection positivity is more important than pointwise positivity, and how Euclidean data can reconstruct a positive-energy Wightman theory.

$$
\text{Euclidean correlations}
\quad\xrightarrow{\text{reflection positivity}}\quad
\text{Hilbert space and positive Hamiltonian}.
$$

## Prerequisites

You should know the distributional language from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) and the Lorentzian correlation-function language from [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/). The analytic-continuation background from [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) is helpful but not required on a first pass.

A standard first course in QFT is enough motivation: Wick rotation, Euclidean propagators, path integrals, and correlation functions.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/) | The imaginary-time idea, formal path-integral notation, free scalar example, and first encounter with reflection positivity. |
| 2 | [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/) | The Euclidean $n$-point distributions and the main requirements they must satisfy. |
| 3 | [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) | The axiom package: regularity, Euclidean covariance, symmetry, reflection positivity, and clustering. |
| 4 | [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) | The positivity condition that turns positive-time Euclidean observables into Hilbert-space vectors. |
| 5 | [Euclidean Invariance](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-invariance/) | The precise distributional meaning of Euclidean covariance and how it becomes Poincaré covariance. |
| 6 | [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) | The theorem that builds the Hilbert space, Hamiltonian, fields, and Wightman functions from valid OS data. |
| 7 | [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) | The clean model where the Euclidean measure, Wick rule, reflection positivity, and reconstructed free scalar theory are explicit. |
| 8 | [Wick Rotation: Rigorous View](/rigorous-qft/osterwalder-schrader-euclidean-qft/wick-rotation-rigorous-view/) | The analytic-continuation meaning of Wick rotation and the caveats behind the symbol $t=-i\tau$. |
| 9 | [Euclidean Versus Lorentzian QFT](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-versus-lorentzian-qft/) | The dictionary between signatures: what is equivalent, what is not, and why real-time physics still needs Lorentzian tools. |
| 10 | [Markov Property Preview](/rigorous-qft/osterwalder-schrader-euclidean-qft/markov-property-preview/) | The probabilistic locality idea: conditional independence across Euclidean hypersurfaces. |

After this path, you should be able to distinguish an informal Euclidean path integral from a Schwinger-function family suitable for reconstruction, and to explain how the reconstructed Hilbert space and positive Hamiltonian appear.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $t=-i\tau$ | Imaginary-time continuation from Lorentzian to Euclidean variables; meaningful only with analytic and positivity hypotheses. | Wick rotation and Euclidean–Lorentzian comparison. |
| $W_n$ and $S_n$ | Lorentzian Wightman distributions and Euclidean Schwinger distributions. | Reconstruction and signature dictionary. |
| $E(d)=\mathbb R^d\rtimes O(d)$ | Euclidean translations and rotations acting on Schwinger data. | Poincaré covariance after reconstruction. |
| $\theta(\tau,\mathbf x)=(-\tau,\mathbf x)$ | Euclidean time reflection. | Reflection positivity. |
| $\langle F,F\rangle_{\mathrm{OS}}=\langle\Theta F\,F\rangle_E$ | The OS positive semidefinite form. | Hilbert-space construction. |
| $T(\tau)=e^{-\tau H}$ | Positive Euclidean time translations become a contraction semigroup. | Positive energy and the spectral condition. |
| $C_m=(-\Delta_E+m^2)^{-1}$ | Massive Gaussian free-field covariance. | Wick Schwinger functions and the free scalar example. |
| $\mathcal F_{M_+}\perp\!\!\!\perp\mathcal F_{M_-}\mid\mathcal F_\Sigma$ | Markov conditional independence across a Euclidean hypersurface. | Probabilistic and constructive QFT. |

## Common confusions

**Euclidean does not mean less physical.** Euclidean correlators often contain the same spectral and operator data as Lorentzian correlators, but encoded in imaginary time.

**Wick rotation is not an axiom-free substitution.** The relation between Euclidean and Lorentzian theories is controlled by analyticity and positivity hypotheses.

**Reflection positivity is not pointwise positivity.** It is a quadratic inequality involving reflected positive-time test functions.

**Euclidean invariance is not unitarity.** Euclidean covariance becomes Lorentzian covariance only after reflection positivity and reconstruction.

**Gaussian does not mean pointwise classical field.** The Gaussian free field is usually a random distribution, and its composite fields require Wick ordering or renormalization.

**A formal path integral is not automatically a construction.** A rigorous construction must say what the measure or limiting distributional data are and prove the required properties.

**A Markov property is not clustering.** Clustering is an asymptotic independence statement at large separation; Markovianity is conditional independence across a separating hypersurface.

## Boundaries

This chapter focuses first on scalar Euclidean QFT on flat $\mathbb R^d$. Fermions, gauge theories, curved Euclidean manifolds, finite temperature, and statistical-mechanical lattice models require additional conventions and will be treated later or in neighboring volumes.

The chapter is not a replacement for constructive QFT. It introduces the Euclidean axiomatic framework; proving that a particular interacting model satisfies it is a separate construction problem.

The chapter also does not treat every analytic-continuation issue. The Wightman chapter explains tube-domain analyticity from the Lorentzian side; this chapter explains the Euclidean data and positivity from the Euclidean side.

## Where to go next

For the Lorentzian analogue, return to the Wightman and Axiomatic QFT chapter. For probabilistic constructions and interacting examples, continue later to the Constructive QFT and Path Integrals as Measures chapters. For observables organized by regions rather than by fields, the next major framework is Algebraic QFT.

## References

- J. Schwinger, "On the Euclidean Structure of Relativistic Field Theory," *Proceedings of the National Academy of Sciences* **44** (1958), 956–965. DOI: [10.1073/pnas.44.9.956](https://doi.org/10.1073/pnas.44.9.956).
- K. Symanzik, "Euclidean Quantum Field Theory. I. Equations for a Scalar Model," *Journal of Mathematical Physics* **7** (1966), 510–525. DOI: [10.1063/1.1704960](https://doi.org/10.1063/1.1704960).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- E. Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](https://doi.org/10.1016/0022-1236(73)90025-6).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.

## Version history

- **2026-06-28:** Updated after adding Euclidean versus Lorentzian QFT and Markov property preview.
- **2026-06-28:** Updated after adding Gaussian free field and Wick rotation pages.
- **2026-06-28:** Updated after adding Euclidean invariance and OS reconstruction.
- **2026-06-28:** Updated after adding the OS axioms and reflection positivity pages.
- **2026-06-28:** Initial polished overview after the chapter reached two ordinary pages.
