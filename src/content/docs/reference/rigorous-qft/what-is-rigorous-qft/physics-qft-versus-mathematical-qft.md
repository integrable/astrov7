---
title: "Physics QFT versus Mathematical QFT"
description: "Explains how the calculational language of physics QFT is translated into the definition, theorem, and construction language of mathematical QFT."
sidebar:
  label: "Physics vs. Mathematical QFT"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg; Streater–Wightman; Osterwalder–Schrader; Haag–Kastler; Glimm–Jaffe; Wilson–Kogut; Rejzner; Costello; Jaffe–Witten."
topics:
  - rigorous QFT
  - physical reasoning
  - mathematical foundations
  - continuum limits
canonicalTopics:
  - rigorous-quantum-field-theory
  - qft-foundations
  - constructive-quantum-field-theory
researchStatus:
  established:
    - "Physics QFT and mathematical QFT often use the same symbols but attach different logical claims to them."
    - "Free fields, many low-dimensional models, perturbative constructions, and structural theorems can be formulated rigorously in appropriate frameworks."
  active:
    - "A complete nonperturbative construction of many physically central four-dimensional interacting QFTs remains open."
---

## Summary

Physics QFT and mathematical QFT are not rival subjects. They are two contracts for using the same ideas. The physics contract asks: **what predictions, organizing principles, and calculational tools follow from this field theory?** The mathematical contract asks: **what object has been defined, under what assumptions, and what has been proved about it?**

The same expression can satisfy one contract and fail to satisfy another. For example,

$$
Z[J]=\int \mathcal D\phi\,
\exp\left(iS[\phi]+i\int J\phi\right)
$$

may be a brilliant physics mnemonic for perturbation theory, a finite-dimensional integral after a cutoff, a Euclidean measure after Wick rotation, or a formal power series in a perturbative algebra. Those are different mathematical statements, even when the displayed symbol is the same.

The working rule for this page is

$$
\text{same notation}
\ne
\text{same claim}.
$$

Good rigorous QFT does not replace physical reasoning. It records which parts of the physical reasoning have become definitions, theorems, constructions, and controlled approximations.

## Prerequisites

Read [Conventions and Logical Status](/rigorous-qft/conventions/) and [Levels of Rigor in QFT](/rigorous-qft/what-is-rigorous-qft/levels-of-rigor-in-qft/) first. You should know the informal physics roles of actions, correlation functions, propagators, regulators, renormalization, and symmetries.

## Core idea

Do not ask whether "QFT" is rigorous in the abstract. Ask which sentence is being asserted.

A physics sentence often has the form:

$$
\text{given a Lagrangian and symmetries, compute an observable}.
$$

A mathematical QFT sentence often has the form:

$$
\text{given a framework and hypotheses, construct an object or prove a theorem}.
$$

Both are essential. The first explains why the theory is useful and how it talks to experiment, universality, duality, and physical intuition. The second explains what the symbols mean as mathematical objects and where theorems begin and end.

## Setup and conventions

In this page, **physics QFT** means the working language used to model and compute quantum many-body, statistical, relativistic, and particle-physics systems: Lagrangians, path integrals, canonical quantization, Feynman rules, effective actions, renormalization group flows, lattice regularizations, and symmetry arguments.

**Mathematical QFT** means the theorem-level treatment of QFT objects: Wightman fields, Osterwalder–Schrader Schwinger functions, Haag–Kastler nets, Euclidean measures, perturbative algebras, BV-BRST complexes, vertex operator algebras, conformal nets, factorization algebras, and functorial field theories.

These are not communities of people. They are standards of claim. The same researcher may use a physics standard while estimating an amplitude, a perturbative rigorous standard while defining renormalized time-ordered products, and an axiomatic standard while proving a structural theorem.

Unless stated otherwise, Lorentzian formulas use the mostly-minus convention from [Conventions and Logical Status](/rigorous-qft/conventions/),

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1.
$$

## The same symbols under two contracts

The following table is a translation guide, not a judgment of value.

| Symbol or phrase | Physics QFT use | Mathematical QFT question |
|---|---|---|
| $\phi(x)$ | Field inserted at a spacetime point. | Is this an operator-valued distribution? What is the domain of $\phi(f)$? |
| $S[\phi]$ | Action organizing equations of motion, symmetries, and perturbation theory. | Does it define a measure, a formal series, a variational problem, or a local functional? |
| $\int\mathcal D\phi$ | Path-integral notation for amplitudes or correlation functions. | Is there a measure, an oscillatory distribution, a cutoff integral, or only a formal expansion? |
| $D_F(p)$ | Propagator used in Feynman rules. | Which distribution is it, what is its wavefront set, and how are boundary values defined? |
| "renormalize" | Absorb cutoff dependence into parameters and compute finite observables. | Extend distributions, choose local counterterms, prove estimates, or construct a continuum limit. |
| "gauge symmetry" | Redundancy used to organize variables and interactions. | What are the observables, quotient, constraint algebra, BRST/BV complex, or anomaly obstruction? |
| "continuum limit" | Remove the regulator while keeping physical quantities fixed. | In what topology do which observables converge, and what limiting QFT object is produced? |

The table should prevent a common mistake: treating a successful calculation as if it automatically proved every existence statement suggested by its notation. It should also prevent the opposite mistake: treating formal notation as worthless because it is not yet a theorem.

## A free scalar field: where the contracts agree

The free scalar field is the cleanest example where physics and mathematics meet almost perfectly.

Physics starts from the action

$$
S_0[\phi]
=
\int d^4x\,
\left(
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
\right),
$$

obtains the Klein–Gordon equation

$$
(\Box+m^2)\phi=0,
$$

quantizes the oscillator modes, and uses the Feynman propagator

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

Mathematical QFT turns the same physics into distributions and Hilbert-space objects. A real free scalar Wightman two-point function is the positive-frequency distribution

$$
\begin{aligned}
W_2(f,g)
&=
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
\,\overline{\widetilde f(E_{\mathbf p},\mathbf p)}
\,\widetilde g(E_{\mathbf p},\mathbf p),\\
E_{\mathbf p}&=\sqrt{\mathbf p^2+m^2},
\end{aligned}
$$

for suitable test functions. The field is an operator-valued distribution $\phi(f)$ on a dense invariant domain, not an ordinary operator $\phi(x)$ at a point.

Euclideanly, the massive Gaussian free field is a Gaussian random distribution with covariance

$$
C=(-\Delta_E+m^2)^{-1},
$$

again interpreted distributionally. In this example, the physics formulas, Wightman construction, Euclidean Gaussian measure, and algebraic net can be related precisely. This is why free fields are the first theorem-level examples throughout rigorous QFT.

## Interacting theories: where the contracts separate

For an interacting scalar theory, physics may start from

$$
S[\phi]
=
\int d^dx\,
\left(
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
\right).
$$

The physics contract can then produce Feynman rules, renormalized perturbation theory, beta functions, effective potentials, lattice simulations, and scaling predictions. These may be excellent and quantitatively useful.

The mathematical contract asks more specific questions:

| Question | Possible rigorous status |
|---|---|
| Are the perturbative coefficients well-defined? | Yes, after choosing a renormalization framework such as Epstein–Glaser or BPHZ-type methods. |
| Does the formal perturbative series converge? | Usually not expected; often it is asymptotic. |
| Does a Euclidean measure exist after cutoff removal? | Known for important low-dimensional models; hard and model-dependent. |
| Do the limiting Schwinger functions satisfy OS axioms? | A theorem only after proving positivity, covariance, regularity, clustering, and convergence. |
| Does the model give an interacting continuum QFT in four dimensions? | A delicate question; some physically natural limits are believed or proved to be trivial in related settings. |

The lesson is not that physics is unreliable. The lesson is that "the interacting theory exists" is not one statement. It splits into many statements about perturbative coefficients, regulated models, scaling limits, measures, Hilbert spaces, local algebras, and observables.

## Gauge theory: physics success and mathematical challenge

Yang–Mills theory is the best example of the gap between physical authority and mathematical completion.

The physics case is extremely strong: non-Abelian gauge theory underlies the Standard Model, perturbative QCD is controlled at high energies by asymptotic freedom, lattice gauge theory gives strong nonperturbative evidence for confinement and a mass gap, and effective descriptions organize hadronic physics.

The mathematical problem is sharper. One wants a nonperturbative four-dimensional continuum quantum Yang–Mills theory satisfying a standard set of axioms, together with a positive mass gap. The Clay problem asks for precisely this kind of construction and proof, not merely for perturbative control or numerical evidence.

Thus the sentence "Yang–Mills theory works" is a physics statement with enormous empirical and theoretical support. The sentence "four-dimensional quantum Yang–Mills theory has been constructed with a mass gap" is a theorem-level statement that remains open.

## Effective field theory is not a loophole

Effective field theory changes the question rather than evading rigor. An EFT is not usually claiming to be a fundamental continuum theory at arbitrarily short distances. It claims to describe observables below a scale $\Lambda$ using the most general local interactions consistent with symmetries, organized by relevance and power counting.

A typical EFT statement is

$$
\mathcal L_{\mathrm{eff}}
=
\sum_i c_i(\Lambda)\,\mathcal O_i,
\qquad
\Delta_i\le \Delta_{\max}
\quad\text{to a chosen accuracy}.
$$

The mathematical standard is then not necessarily "construct a theory at all scales." It may be: prove a controlled expansion, define the regulated theory, justify matching, control the error below the cutoff, or formulate the perturbative series as a local formal object.

This is why renormalizability changed meaning in modern QFT. In older language, nonrenormalizable interactions threatened predictivity. In EFT language, they are expected and useful, provided the expansion is organized by scale and the desired accuracy is specified.

## How to translate a physics claim

When you see a physics statement, translate it by asking five questions.

| Question | Example |
|---|---|
| What is the object? | A correlation function, S-matrix element, Hilbert space, local algebra, measure, formal series, category, or scaling limit. |
| What is the framework? | Wightman, OS, algebraic, constructive, perturbative algebraic, BV-BRST, VOA, lattice, EFT, or another framework. |
| What is the regulator or topology? | Lattice spacing, cutoff, volume, test-function topology, distribution topology, operator topology, or formal power-series topology. |
| What are the hypotheses? | Locality, covariance, positivity, spectral condition, reflection positivity, gauge anomaly cancellation, mass gap, clustering, or bounds. |
| What is the status? | Definition, theorem, construction, proof sketch, standard result, conjecture, physics expectation, or open problem. |

For example, the informal sentence

> The path integral defines the theory.

should become something like one of the following:

| Precise version | Status |
|---|---|
| The finite lattice path integral defines a probability measure for each finite lattice and cutoff. | Regulated construction. |
| The Euclidean Schwinger functions converge after renormalization and satisfy the OS axioms. | Constructive theorem, if proved. |
| The perturbative expansion defines time-ordered products as formal power series satisfying causal factorization. | Perturbative theorem. |
| The Lorentzian oscillatory path integral exists as a countably additive measure on fields. | Usually false or not the intended claim. |

## Common pitfalls

**Turning working notation into ontology too quickly.** The symbol $\phi(x)$ is often the fastest way to compute. It is not automatically an operator at a spacetime point.

**Demanding the wrong kind of rigor.** A perturbative page should not be judged as a failed constructive page. It may be doing a different job: defining coefficients, local counterterms, or formal algebras.

**Confusing empirical certainty with mathematical theoremhood.** QCD is a successful physical theory. The Clay Yang–Mills mass-gap problem asks for a specific nonperturbative construction and proof.

**Confusing mathematical caution with physical nihilism.** Saying that a continuum construction is open does not erase the success of perturbation theory, EFT, lattice simulation, or phenomenology.

**Forgetting positivity.** Many formal Euclidean correlation functions have the right symmetry and singularity structure but do not reconstruct a physical Hilbert space unless positivity conditions hold.

## Relations to other pages

- [Levels of Rigor in QFT](/rigorous-qft/what-is-rigorous-qft/levels-of-rigor-in-qft/) gives the hierarchy of claim types used here.
- [Conventions and Logical Status](/rigorous-qft/conventions/) fixes status labels such as theorem, construction, conjecture, and physics expectation.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) explains a modern tool that turns the phrase "singular product of fields" into a precise microlocal condition.
- Later pages on Wightman, OS, algebraic, constructive, and perturbative algebraic QFT will make each translation framework explicit.

## Research status

The distinction between physics standards and theorem-level standards is settled and widely used in mathematical physics. The active work lies in proving more constructions, comparing frameworks, extending perturbative constructions to gauge theories and curved backgrounds, understanding scaling limits, and making dualities and generalized symmetries mathematically precise.

The frontier is not one problem but a spectrum: nonperturbative four-dimensional gauge theory, chiral gauge theories, interacting conformal field theories in dimensions greater than two, rigorous holography, and the relation between categorical protected sectors and full local QFTs.

## Exercises

### Exercise 1: Translate the claim

Rewrite the sentence "the path integral defines the QFT" in three mathematically different ways.

<details>
<summary><strong>Solution</strong></summary>

One possible answer:

1. With a finite lattice and finite volume, the path integral is a finite-dimensional integral defining a regulated model.
2. In Euclidean constructive QFT, the cutoff measures may converge to a probability measure or to Schwinger functions satisfying OS axioms.
3. In perturbative algebraic QFT, the path integral may be interpreted as a formal device for producing a renormalized formal power series of time-ordered products.

These are not equivalent statements. They have different objects, topologies, and proof obligations.

</details>

### Exercise 2: Free scalar alignment

Explain why the free massive scalar field is unusually friendly to both physics QFT and mathematical QFT.

<details>
<summary><strong>Solution</strong></summary>

The equations are linear, the oscillator quantization is explicit, the two-point function is a well-defined distribution, the Fock representation can be constructed, the Euclidean theory is Gaussian, and Wick's theorem defines all higher correlation functions. The same model can therefore be described in canonical, Wightman, Euclidean, and algebraic languages with relatively direct translations.

</details>

### Exercise 3: The status of a lattice calculation

A lattice simulation gives strong numerical evidence for a mass gap in a gauge theory. Which mathematical claim does this support, and which does it not prove?

<details>
<summary><strong>Solution</strong></summary>

It supports the physics expectation that the continuum theory has a mass gap and may provide quantitative evidence after careful finite-size and cutoff analysis. It does not by itself prove that the continuum theory exists, that the infinite-volume and zero-lattice-spacing limits converge in a theorem-level sense, or that the limiting theory satisfies a chosen axiom system with a positive mass gap.

</details>

### Exercise 4: Effective theory status

Why is a nonrenormalizable interaction not automatically a problem in effective field theory?

<details>
<summary><strong>Solution</strong></summary>

In EFT, nonrenormalizable interactions are organized by powers of a high scale. At energies well below that scale, only finitely many operators contribute to a fixed desired accuracy. The theory is predictive after specifying symmetries, power counting, matching data, and error estimates. It is not necessarily claiming to define a fundamental continuum QFT at arbitrarily short distances.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields, Volume I: Foundations*, Cambridge University Press. DOI: [10.1017/CBO9781139644167](https://doi.org/10.1017/CBO9781139644167).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-97306-2](https://doi.org/10.1007/978-3-642-97306-2).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- K. G. Wilson and J. Kogut, "The Renormalization Group and the ε Expansion," *Physics Reports* **12** (1974), 75–199. DOI: [10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573%2874%2990023-4).
- C. P. Burgess, *Introduction to Effective Field Theory: Thinking Effectively about Hierarchies of Scale*, Cambridge University Press. DOI: [10.1017/9781139048040](https://doi.org/10.1017/9781139048040). Review: arXiv: [hep-th/0701053](https://arxiv.org/abs/hep-th/0701053).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Costello, *Renormalization and Effective Field Theory*, American Mathematical Society. DOI: [10.1090/surv/170](https://doi.org/10.1090/surv/170).
- K. Fredenhagen and K. Rejzner, "Perturbative Algebraic Quantum Field Theory," arXiv: [1208.1428](https://arxiv.org/abs/1208.1428).
- A. Jaffe and E. Witten, "Quantum Yang–Mills Theory," Clay Mathematics Institute problem description. [PDF](https://www.claymath.org/wp-content/uploads/2022/06/yangmills.pdf).

## Version history

- **2026-06-27:** Initial polished draft for the What Is a Rigorous QFT? chapter.
