---
title: "Path Integrals as Measures"
description: "Chapter overview for path integrals as finite-dimensional measures, Gaussian random fields, cylinder measures, Minlos-type extension, interacting Euclidean measures, cutoff removal, Berezin integration, oscillatory integrals, and Lorentzian caveats in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Simon functional integration; Glimm–Jaffe constructive QFT; Gaussian measures; Bochner–Minlos theorem; Berezin integration; Osterwalder–Schrader Euclidean QFT; Feynman path integrals; oscillatory integrals."
topics:
  - path integrals
  - measures
  - Gaussian random fields
  - cylinder measures
  - Euclidean QFT
  - constructive QFT
  - ultraviolet cutoffs
  - continuum limits
  - Berezin integration
  - oscillatory integrals
  - Lorentzian path integrals
canonicalTopics:
  - path-integrals-as-measures
  - gaussian-random-field
  - cylinder-measure
  - minlos-theorem
  - interacting-euclidean-measure
  - ultraviolet-cutoff
  - continuum-limit
  - berezin-integration
  - oscillatory-integral
  - lorentzian-path-integral
  - rigorous-path-integrals
researchStatus:
  established:
    - "Finite-dimensional Euclidean path integrals, Gaussian random fields, cylinder measures, Minlos-type construction of free fields, finite-cutoff Euclidean measures, cutoff-limit criteria, finite-dimensional Berezin integrals, finite-dimensional oscillatory integrals, and many real-time quantum-mechanical kernels have precise mathematical meanings."
  active:
    - "Continuum interacting measures, regulator-independent cutoff removal, fermionic continuum limits, gauge theories, and direct nonperturbative Lorentzian oscillatory path integrals require additional constructions and remain framework-dependent."
---

Path Integrals as Measures is the chapter in the Mathematical and Rigorous QFT volume where the formal expression $\int\mathcal D\phi$ is slowed down and rebuilt from actual measure theory. It begins with finite-dimensional probability measures, then passes to Gaussian random fields, cylinder measures, Minlos-type extension, interacting densities, ultraviolet cutoffs, continuum limits, fermionic Berezin integration, oscillatory integrals, and Lorentzian caveats.

The chapter exists because path-integral notation is simultaneously one of the most powerful languages in QFT and one of the easiest places to hide undefined objects. The central distinction is simple: a Euclidean cutoff path integral can often be a probability measure, a fermionic path integral is an algebraic Berezin integral, and a Lorentzian path integral is usually an oscillatory object rather than a measure.

Read this chapter when you want to know exactly when a path integral is a measure, when it is a formal asymptotic device, when it is a Grassmann-algebra calculation, and when it is notation awaiting a construction.

$$
\text{rigorous path integral}
\neq
\text{formal symbol } \mathcal D\phi;
\qquad
\text{it is a constructed object in a specified framework.}
$$

## Prerequisites

You should know the volume [Conventions](/rigorous-qft/conventions/), [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/). The Osterwalder–Schrader chapter explains why reflection positivity is needed before a Euclidean measure can be interpreted as a Lorentzian QFT. For the fermionic page, basic familiarity with exterior algebras or canonical anticommutation relations is helpful but not required. For the Lorentzian pages, basic distribution theory and the Feynman $i\epsilon$ prescription are helpful.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/) | The honest finite-cutoff meaning of a Euclidean path integral as a normalized measure and expectation. |
| 2 | [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) | The free-field transition from Gaussian random vectors to Gaussian random distributions. |
| 3 | [Cylinder Measures](/rigorous-qft/path-integrals-as-measures/cylinder-measures/) | How compatible finite-dimensional laws of smeared fields are assembled before an actual continuum measure has been proved. |
| 4 | [Minlos Theorem Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/) | The extension theorem that turns continuous positive-definite functionals on nuclear test-function spaces into measures on distribution spaces. |
| 5 | [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/) | Why interactions are best viewed as densities relative to Gaussian reference measures, not as factors multiplying infinite-dimensional Lebesgue measure. |
| 6 | [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/) | The regularizations that make local interactions finite before renormalized cutoff removal is attempted. |
| 7 | [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/) | What it means for cutoff measures, Schwinger functions, or characteristic functionals to converge after renormalization. |
| 8 | [Fermionic Berezin Integrals: Rigorous View](/rigorous-qft/path-integrals-as-measures/fermionic-berezin-integrals-rigorous-view/) | Why fermionic path integrals are algebraic Grassmann/Berezin operations rather than probability measures. |
| 9 | [Oscillatory Integrals and Lorentzian Path Integrals](/rigorous-qft/path-integrals-as-measures/oscillatory-integrals-and-lorentzian-path-integrals/) | The finite-dimensional and operator-theoretic meanings that can replace naive real-time integration over paths. |
| 10 | [Why Lorentzian Path Integrals Are Hard](/rigorous-qft/path-integrals-as-measures/why-lorentzian-path-integrals-are-hard/) | The obstruction list: no positivity, no infinite-dimensional Lebesgue measure, singular fields, gauge redundancy, sign problem, and contour data. |

After this path, you should be able to say what data define a finite-dimensional measure, why a free Euclidean field is usually distribution-valued, how finite-dimensional field distributions form a cylinder measure, why nuclear-space extension theorems matter, how an interaction can define a density relative to a Gaussian measure, why ultraviolet cutoffs are part of the construction, what cutoff removal asks one to prove, why fermionic integration has a different mathematical status from bosonic probability, and why Lorentzian path integrals are oscillatory constructions rather than probability measures.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $d\mu_N=Z_N^{-1}e^{-S_N}dx$ | A real finite-dimensional Euclidean action gives a probability measure when $0<Z_N<\infty$. | Cutoff models and interacting densities. |
| $C=A^{-1}$ | In a finite Gaussian integral, covariance is the inverse quadratic form. | Free fields and propagators. |
| Cylinder data plus Minlos | Compatible finite-dimensional laws can become a measure when the characteristic functional is continuous and positive-definite on a nuclear space. | Gaussian random fields and free Euclidean QFT. |
| $d\mu_V=Z_V^{-1}e^{-V}d\mu_C$ | Interactions as densities relative to a Gaussian reference measure. | Constructive scalar models and Schwinger functions. |
| $\mu_{\kappa,L}\Rightarrow\mu$ and $S^{\kappa,L}_n\to S_n$ | Continuum limits are convergence statements for measures, characteristic functionals, or smeared Schwinger functions. | Osterwalder–Schrader reconstruction and universality. |
| $\int D(\bar\psi,\psi)e^{-\bar\psi A\psi}=\det A$ | Basic finite-dimensional fermionic Gaussian identity; Majorana analogues give Pfaffians. | Fermion determinants, Pfaffians, and Wick rules. |
| $I(\lambda)=\int e^{i\lambda S}a$ | A finite-dimensional oscillatory integral; cancellation, not positivity, controls its behavior. | Stationary phase and real-time path integrals. |
| $e^{-itH/\hbar}$ | Real-time evolution is rigorously an operator first; time-sliced path integrals are often approximations to its kernel. | Lorentzian quantum mechanics and QFT caveats. |

## Common confusions

**A finite cutoff is not the continuum theory.** Finite-dimensional path integrals can be rigorous while the continuum limit remains hard. The hard step is proving convergence with the correct renormalization and axioms.

**There is no infinite-dimensional Lebesgue measure.** The symbol $\mathcal D\phi$ should not be interpreted as translation-invariant Lebesgue measure on a function space. Infinite-dimensional measures must be built by Gaussian, projective, cylinder, stochastic, or constructive methods.

**A Gaussian random field is usually not a random function.** The safe object is $\Phi(f)$, the field smeared against a test function. Pointwise notation is shorthand and may be singular.

**Minlos is not a theorem that all path integrals exist.** It constructs a measure from a normalized continuous positive-definite characteristic functional on a nuclear space. Producing that functional for an interacting renormalized theory is a separate problem.

**An action density is not automatically defined.** The formula $e^{-V}d\mu_C$ is meaningful only when $V$ is a random variable or a controlled limit. Local products of fields usually require ultraviolet cutoffs and renormalization.

**Fermionic path integrals are not probability measures.** Berezin integration is algebraic integration over Grassmann generators. It is indispensable, but it is not a measure on an ordinary sample space.

**Oscillatory integrals are not probability expectations.** A Lorentzian phase $e^{iS}$ may define an oscillatory integral after a prescription, but it does not define a positive measure.

**Wick rotation is not a one-line proof.** Analytic continuation needs hypotheses. The replacement $t=-i\tau$ is reliable only when spectral, analytic, and positivity conditions justify it.

## Boundaries

This chapter does:

- explain finite-dimensional path integrals as honest measures;
- define Gaussian random fields through smeared variables and covariance;
- explain cylinder sets, compatible marginals, and cylinder measures;
- preview the Bochner–Minlos theorem and why nuclear test-function spaces appear;
- explain interacting Euclidean measures as densities relative to Gaussian references;
- distinguish ultraviolet and infrared cutoffs;
- explain continuum limits as convergence problems after renormalization;
- introduce finite-dimensional Grassmann algebras and Berezin Gaussian identities;
- introduce finite-dimensional oscillatory integrals as the model for Lorentzian phases;
- explain why direct Lorentzian path integrals are not ordinary measure integrals;
- connect cutoff measures to constructive QFT and Osterwalder–Schrader reconstruction.

This chapter does not try to do:

- replace a full course in measure theory, probability, nuclear-space theory, oscillatory-integral theory, or supergeometry;
- prove all constructive QFT existence theorems;
- treat numerical lattice simulation methods in detail;
- develop perturbative Feynman rules as the main topic;
- make Lorentzian path integrals look like ordinary probability measures;
- solve real-time nonequilibrium QFT, the finite-density sign problem, or Schwinger–Keldysh theory in detail;
- solve gauge fixing, BRST, BV theory, or chiral gauge theories in detail.

Those topics belong to the Constructive QFT, Osterwalder–Schrader, Perturbative Algebraic QFT, BV-BRST, Microlocal Analysis, and Lattice-to-Continuum chapters. Here the goal is to make the word "measure" precise before the notation becomes infinite-dimensional.

## Where to go next

After this chapter, read [Constructive QFT](/rigorous-qft/constructive-qft/) for interacting Euclidean models, [Osterwalder–Schrader and Euclidean QFT](/rigorous-qft/osterwalder-schrader-euclidean-qft/) for Euclidean-to-Lorentzian reconstruction, and [Wightman and Axiomatic QFT](/rigorous-qft/wightman-axiomatic-qft/) for Lorentzian operator-valued distributions. For the singularity theory behind Lorentzian propagators, continue to [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). For gauge-theoretic odd variables and ghosts, continue later to BV-BRST and Perturbative Algebraic QFT.

## References

### Standard first pass

- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Vladimir I. Bogachev, *Gaussian Measures*, Mathematical Surveys and Monographs **62**, American Mathematical Society, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- F. A. Berezin, *The Method of Second Quantization*, Academic Press, 1966. ISBN: [9780120894505](https://books.google.com/books/about/The_Method_of_Second_Quantization.html?id=fAlRAAAAMAAJ).
- R. P. Feynman and A. R. Hibbs, *Quantum Mechanics and Path Integrals*, McGraw–Hill, 1965; emended edition by Daniel F. Styer, Dover, 2010.

### Deeper references

- R. A. Minlos, "Generalized Random Processes and Their Extension to a Measure," *Selected Translations in Mathematical Statistics and Probability* **3** (1963), 291–313; translated from *Trudy Moskov. Mat. Obšč.* **8** (1959), 497–518.
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. P. Feynman, "Space-Time Approach to Non-Relativistic Quantum Mechanics," *Reviews of Modern Physics* **20** (1948), 367–387. DOI: [10.1103/RevModPhys.20.367](https://doi.org/10.1103/RevModPhys.20.367).
- R. H. Cameron, "A Family of Integrals Serving to Connect the Wiener and Feynman Integrals," *Journal of Mathematics and Physics* **39** (1960), 126–140. DOI: [10.1002/sapm1960391126](https://doi.org/10.1002/sapm1960391126).
- Sergio Albeverio, Raphael Høegh-Krohn, and Sonia Mazzucchi, *Mathematical Theory of Feynman Path Integrals: An Introduction*, second edition, Lecture Notes in Mathematics **523**, Springer, 2008. DOI: [10.1007/978-3-540-76956-9](https://doi.org/10.1007/978-3-540-76956-9).
- Sergio Albeverio and Raphael Høegh-Krohn, "Oscillatory Integrals and the Method of Stationary Phase in Infinitely Many Dimensions," *Inventiones Mathematicae* **40** (1977), 59–106. DOI: [10.1007/BF01389861](https://doi.org/10.1007/BF01389861).
- Edward Witten, "Analytic Continuation Of Chern-Simons Theory," arXiv: [1001.2933](https://arxiv.org/abs/1001.2933).
- Matthias Troyer and Uwe-Jens Wiese, "Computational Complexity and Fundamental Limitations to Fermionic Quantum Monte Carlo Simulations," *Physical Review Letters* **94** (2005), 170201. DOI: [10.1103/PhysRevLett.94.170201](https://doi.org/10.1103/PhysRevLett.94.170201).

## Version history

- **2026-06-30:** Updated reading path, landmarks, common confusions, boundaries, and references after adding Oscillatory Integrals and Why Lorentzian Path Integrals Are Hard.
- **2026-06-30:** Updated reading path, landmarks, common confusions, boundaries, and references after adding Continuum Limit of Measures and Fermionic Berezin Integrals.
- **2026-06-30:** Updated reading path, landmarks, common confusions, boundaries, and references after adding Euclidean Action as Density and Ultraviolet Cutoffs.
- **2026-06-30:** Updated reading path and landmarks after adding Cylinder Measures and Minlos Theorem Preview.
- **2026-06-30:** Initial chapter overview created after the chapter reached two ordinary pages.
