---
title: "Locally Covariant QFT"
description: "Chapter overview for functorial algebraic QFT on globally hyperbolic spacetimes in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Brunetti–Fredenhagen–Verch local covariance; Fewster–Verch curved-spacetime AQFT."
topics:
  - locally covariant QFT
  - curved spacetime
  - algebraic QFT
  - Cauchy dynamics
  - relative Cauchy evolution
  - locally covariant fields
  - Hadamard states
  - algebraic renormalization
canonicalTopics:
  - locally-covariant-quantum-field-theory
  - qft-on-curved-spacetimes
  - algebraic-quantum-field-theory
researchStatus:
  established:
    - "Locally covariant QFT is the standard functorial extension of algebraic QFT from one fixed spacetime to all globally hyperbolic spacetimes."
  active:
    - "Gauge theories, state spaces, dynamical locality, boundaries, and perturbative gravity require refinements of the basic functorial framework."
---

Locally Covariant QFT is the chapter in the Mathematical and Rigorous QFT volume where algebraic QFT is lifted from a fixed background to a category of spacetimes. The central move is to replace covariance under the symmetry group of one spacetime by functoriality over all admissible globally hyperbolic spacetimes.

This chapter exists because generic curved spacetimes have no Poincaré group and no preferred vacuum. A rigorous framework for QFT on curved backgrounds must therefore say what is local, covariant, and dynamical without relying on global symmetry.

Read this chapter when you want to understand the mathematical meaning of a statement like "the same QFT on every curved spacetime." The chapter explains how Cauchy surfaces, causal embeddings, the time-slice axiom, relative Cauchy evolution, locally covariant fields, Hadamard states, and local covariant renormalization replace the flat-spacetime tools of time translations, vacuum normal ordering, and momentum-space counterterms.

$$
\text{locally covariant QFT}
=
\text{functorial algebraic QFT over globally hyperbolic spacetimes}.
$$

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), and [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/). The pages [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) become important when the chapter reaches fields, Hadamard states, and renormalized composite observables.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) | The basic definition $\mathcal A:\mathsf{Loc}\to\mathsf{Alg}$ and how it recovers fixed-spacetime nets. |
| 2 | [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/) | The causal class of backgrounds used in the source category: Cauchy surfaces, causal diamonds, and smooth splitting. |
| 3 | [Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/) | The algebraic expression of hyperbolic dynamics: Cauchy morphisms are mapped to isomorphisms. |
| 4 | [Relative Cauchy Evolution](/rigorous-qft/locally-covariant-qft/relative-cauchy-evolution/) | The automorphism comparing a theory on $g$ with the same theory on a compactly perturbed metric $g+h$. |
| 5 | [Stress Tensor from Local Covariance](/rigorous-qft/locally-covariant-qft/stress-tensor-from-local-covariance/) | The stress tensor as the infinitesimal generator of metric response, rather than merely a Noether current for translations. |
| 6 | [Locally Covariant Fields](/rigorous-qft/locally-covariant-qft/locally-covariant-fields/) | Fields as natural transformations from test data to observable algebras. |
| 7 | [QFT in Curved Spacetime: Rigorous View](/rigorous-qft/locally-covariant-qft/qft-in-curved-spacetime-rigorous-view/) | How the algebraic and locally covariant framework organizes fixed-background curved-spacetime QFT. |
| 8 | [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) | The short-distance and microlocal condition selecting physically admissible curved-spacetime states. |
| 9 | [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) | How Wick products, time-ordered products, and perturbative interactions are defined locally and covariantly. |

After this path, you should be able to state the functorial definition of a locally covariant theory, identify the geometric hypotheses behind $\mathsf{Loc}$, explain why Cauchy regions determine the observable algebra, describe metric response and the stress tensor, state why curved-spacetime QFT uses classes of Hadamard states rather than one preferred vacuum, and identify the finite local curvature ambiguities in curved-spacetime renormalization.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\mathsf{Loc}$ | Category of oriented and time-oriented globally hyperbolic spacetimes with causal embeddings. | All locally covariant formulations. |
| $\mathcal A:\mathsf{Loc}\to\mathsf{Alg}$ | A theory as a covariant functor assigning observable algebras to spacetimes. | Fields, state spaces, and subtheories. |
| Global hyperbolicity | Causality plus compact causal diamonds, equivalently existence of Cauchy surfaces. | Green operators, Hadamard states, and curved-spacetime fields. |
| Time-slice axiom | Cauchy morphisms are sent to algebra isomorphisms. | Metric response and local perturbations. |
| $\operatorname{rce}_M[h]$ | Automorphism comparing $\mathcal A(M)$ and $\mathcal A(M[h])$ through past and future Cauchy regions. | Dynamical locality and stress tensor. |
| $T_M(h)$ | Smeared stress tensor implementing infinitesimal metric response when it exists. | Local covariant fields, Hadamard renormalization, and trace anomaly. |
| $\Phi:\mathcal D\Rightarrow\mathcal A$ | A field as a natural transformation from test data to observables. | Wick powers, currents, and stress tensors. |
| Hadamard state | State with universal short-distance singularity and microlocal spectrum condition. | Curved-spacetime physical state selection and renormalized composite fields. |
| $\operatorname{WF}(\omega_2)$ | Wavefront-set encoding of the positive-frequency null singularities of a Hadamard two-point function. | Wick products, stress tensors, and perturbative states. |
| $T_M^{(n)}$ | Locally covariant time-ordered product extended to coincident diagonals. | Perturbative algebraic QFT and curved-spacetime counterterms. |
| Curvature counterterms | Finite local covariant ambiguities built from $g$, curvature, masses, and couplings. | Stress-tensor renormalization, trace anomaly, and interacting fields. |

## Common confusions

**Local covariance is not just diffeomorphism invariance.** Diffeomorphisms or isometries of one spacetime are special morphisms. Local covariance is a functorial statement over a whole category of spacetimes.

**The source category is not all Lorentzian manifolds.** The standard framework uses globally hyperbolic spacetimes, because hyperbolic field equations and Cauchy evolution need good causal control.

**The target is usually algebras, not Hilbert spaces.** Hilbert spaces appear after choosing states and representations. The functorial theory is usually formulated before choosing a vacuum or a GNS representation.

**The time-slice axiom is not finite predictability.** It says a Cauchy neighborhood carries the same observable algebra as its causal development. It does not say finitely many measured numbers determine the future.

**Relative Cauchy evolution is not ordinary time evolution.** It compares two background metrics that agree outside a compact disturbance. It is a metric-response automorphism, not a Hamiltonian flow chosen inside one spacetime.

**A locally covariant field is not merely a tensor with good index notation.** It is a natural transformation whose smearing maps commute with spacetime embeddings.

**No preferred vacuum is not a bug.** Generic curved spacetimes lack a time-translation symmetry. Locally covariant QFT treats state selection as additional structure rather than pretending that every spacetime has a canonical vacuum.

**Hadamard is not a dynamical law.** It is a regularity and singularity condition on states. It does not choose a unique state or determine the global infrared physics.

**Curved-spacetime counterterms are not arbitrary functions.** Local covariance permits local curvature polynomials, not freely chosen spacetime-dependent renormalization constants.

**Gauge theories are not automatically covered by the simplest target category.** Constraints, BRST/BV cohomology, edge data, and topological sectors may require enriched algebraic targets or refined state spaces.

## Boundaries

This chapter does:

- define locally covariant QFT as a functorial version of algebraic QFT;
- define the globally hyperbolic spacetimes and causal embeddings used in the source category;
- explain the time-slice axiom as the algebraic form of Cauchy evolution;
- define relative Cauchy evolution for compact metric perturbations;
- explain how the stress tensor arises from infinitesimal metric response;
- define locally covariant fields as natural transformations;
- explain how fixed-background curved-spacetime QFT is organized algebraically;
- define the Hadamard condition as the curved-spacetime replacement for the positive-frequency short-distance singularity;
- explain local covariant renormalization of Wick products, time-ordered products, and curvature counterterms.

This chapter does not try to do:

- teach all of Lorentzian geometry or PDE theory from scratch;
- replace the physical curved-spacetime QFT chapter in the Spacetime, Gravity, and Holography volume;
- solve quantum gravity;
- give a complete BV-BRST treatment of gauge theory;
- fix all finite renormalization ambiguities of Wick products or the stress tensor;
- give a full nonperturbative construction of interacting four-dimensional QFTs on curved spacetimes.

Those topics belong to later pages in this volume or to neighboring volumes. Here the goal is the rigorous functorial framework.

## Where to go next

The next natural chapter is Constructive QFT, starting with the constructive program and Euclidean measures. That chapter changes emphasis from functorial control of a theory on backgrounds to the harder question of constructing interacting theories as honest mathematical objects.

## References

### Standard first pass

- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The Generally Covariant Locality Principle – A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. DOI: [10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Christopher J. Fewster and Rainer Verch, "Dynamical Locality and Covariance: What Makes a Physical Theory the Same in all Spacetimes?" *Annales Henri Poincaré* **13** (2012), 1613–1674. DOI: [10.1007/s00023-012-0165-0](https://doi.org/10.1007/s00023-012-0165-0), arXiv: [1106.4785](https://arxiv.org/abs/1106.4785).
- Stefan Hollands and Robert M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. DOI: [10.1016/j.physrep.2015.02.001](https://doi.org/10.1016/j.physrep.2015.02.001), arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).

### Geometry, fields, and renormalization

- Robert M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- Antonio N. Bernal and Miguel Sánchez, "On Smooth Cauchy Hypersurfaces and Geroch's Splitting Theorem," *Communications in Mathematical Physics* **243** (2003), 461–470. DOI: [10.1007/s00220-003-0982-6](https://doi.org/10.1007/s00220-003-0982-6), arXiv: [gr-qc/0306108](https://arxiv.org/abs/gr-qc/0306108).
- Marek J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. DOI: [10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- Romeo Brunetti, Klaus Fredenhagen, and Martin Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. DOI: [10.1007/BF02099626](https://doi.org/10.1007/BF02099626), arXiv: [gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056).
- Stefan Hollands and Robert M. Wald, "Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **223** (2001), 289–326. DOI: [10.1007/s002200100540](https://doi.org/10.1007/s002200100540), arXiv: [gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074).
- Stefan Hollands and Robert M. Wald, "Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **231** (2002), 309–345. DOI: [10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y), arXiv: [gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108).
- Christian Bär, Nicolas Ginoux, and Frank Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*, European Mathematical Society, 2007. DOI: [10.4171/037](https://doi.org/10.4171/037), arXiv: [0806.1036](https://arxiv.org/abs/0806.1036).

## Version history

- **2026-06-29:** Updated after adding Hadamard condition and algebraic renormalization pages.
- **2026-06-29:** Updated after adding locally covariant fields and the rigorous curved-spacetime QFT view.
- **2026-06-29:** Updated after adding relative Cauchy evolution and stress-tensor pages.
- **2026-06-29:** Initial chapter overview created after the chapter reached three ordinary pages.
