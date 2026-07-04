---
title: "Why Lorentzian Path Integrals Are Hard"
description: "Explains the mathematical obstructions that prevent Lorentzian QFT path integrals from being ordinary measures and compares the main rigorous substitutes."
sidebar:
  label: "Why Lorentzian Is Hard"
  order: 10
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader reconstruction; Glimm–Jaffe constructive QFT; Albeverio–Høegh-Krohn–Mazzucchi Feynman integrals; Witten analytic continuation; perturbative algebraic QFT."
topics:
  - Lorentzian path integrals
  - rigorous path integrals
  - sign problem
  - oscillatory integrals
  - Wick rotation
  - real-time QFT
  - gauge fixing
canonicalTopics:
  - lorentzian-path-integral
  - rigorous-path-integrals
  - oscillatory-integral
  - wick-rotation
  - sign-problem
  - perturbative-algebraic-qft
  - constructive-qft
researchStatus:
  established:
    - "There is no general construction of interacting Lorentzian QFT as an ordinary countably additive measure with density e^{iS}; rigorous frameworks instead define operator, algebraic, Euclidean, perturbative, or model-specific objects."
  active:
    - "Real-time nonperturbative QFT, complex contours, gauge-theory path integrals, and nonequilibrium Lorentzian constructions remain active and framework-dependent areas."
---

## Summary

Lorentzian path integrals are hard because they ask one symbol to do too many jobs:

$$
\int\mathcal D\phi\,e^{iS[\phi]}.
$$

For a Euclidean scalar theory with cutoffs, $e^{-S_E}$ may define a positive density relative to a Gaussian measure. For a fermionic theory, Berezin integration gives an algebraic replacement. In Lorentzian signature, $e^{iS}$ is neither positive nor damping; it is a phase. This destroys the most useful tools of probability measure theory.

The difficulties are not a single technical inconvenience. They form a stack:

$$
\begin{array}{c}
\text{no positive density}\\
\text{no infinite-dimensional Lebesgue measure}\\
\text{oscillatory nonconvergence}\\
\text{UV singularities and renormalization}\\
\text{hyperbolic propagation and boundary prescriptions}\\
\text{gauge redundancy and zero modes}\\
\text{analytic continuation and contour ambiguity}
\end{array}
$$

The correct conclusion is not that Lorentzian path integrals are useless. They are extraordinarily useful. The correct conclusion is that, in rigorous QFT, the formal integral must be replaced by a specified construction: operator evolution, Wightman distributions, Osterwalder–Schrader reconstruction, perturbative algebraic QFT, causal perturbation theory, lattice real-time limits, or carefully defined finite-dimensional oscillatory approximations.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Obstruction map for Lorentzian path integrals](/figures/rigorous-qft/lorentzian-path-integral-obstructions.svg)

<figcaption>

The formal Lorentzian path integral fails to be an ordinary measure for several independent reasons. Different rigorous frameworks solve different parts of the obstruction stack.

</figcaption>
</figure>

## Prerequisites

You should know [Oscillatory Integrals and Lorentzian Path Integrals](/rigorous-qft/path-integrals-as-measures/oscillatory-integrals-and-lorentzian-path-integrals/), [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/), and [Fermionic Berezin Integrals: Rigorous View](/rigorous-qft/path-integrals-as-measures/fermionic-berezin-integrals-rigorous-view/). For the Euclidean comparison, read [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). For the Lorentzian singularity language, read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/).

## Core idea

The most compact comparison is this:

| Framework | Typical symbolic weight | Mathematical behavior |
|---|---|---|
| Euclidean bosonic | $e^{-S_E}$ | may be positive and damping |
| Fermionic | $e^{-\bar\psi A\psi}$ | Berezin algebra, determinant or Pfaffian |
| Lorentzian bosonic | $e^{iS}$ | oscillatory phase, not a finite measure |

In finite dimensions, the oscillatory integral

$$
\int_{\mathbb R^n}^{\mathrm{osc}} a(x)e^{i\Phi(x)}d^nx
$$

can be meaningful after specifying a cutoff, contour, distributional pairing, or asymptotic procedure. The problem in QFT is that the formal Lorentzian integral is an infinite-dimensional, ultraviolet-singular, often gauge-redundant version of this expression.

Thus the main question is not

$$
\text{"Does }\int\mathcal D\phi\,e^{iS}\text{ exist?"}
$$

as if there were one universal meaning. The better question is

$$
\text{"Which object is this notation supposed to define, and in which topology or algebra?"}
$$

Once that question is asked, the options become clearer.

## Setup and conventions

We use the mostly-minus Lorentzian convention from the volume conventions. For a real scalar field, the formal Lorentzian action is

$$
S[\phi]=\int d^4x\,\left[
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2-V(\phi)\right],
$$

and the formal phase is $e^{iS[\phi]}$. The Euclidean comparison uses $t=-i\tau$ and, when it exists, a weight $e^{-S_E[\phi]}$. The page is about continuum QFT, not finite-dimensional toy integrals alone: every obstruction below should be read together with ultraviolet regularization, domain, and distributional issues.

We distinguish three different claims. A **symbolic path integral** is a compact notation for expected rules. A **regularized path integral** is a finite-dimensional or cutoff-dependent object. A **constructed continuum theory** is the limiting object that survives cutoff removal and satisfies a chosen set of axioms or reconstruction criteria. The last claim is the hard one.

## No positive measure

A probability measure $\mu$ satisfies

$$
\mu(A)\ge 0,
\qquad
\mu\left(\bigcup_j A_j\right)=\sum_j\mu(A_j)
$$

for disjoint measurable sets. It supports powerful tools: monotone convergence, dominated convergence, conditional expectation, Markov properties, tightness, weak convergence, correlation inequalities, and reflection positivity.

A Lorentzian phase does not have this structure. Even in finite dimensions,

$$
\left|e^{iS(x)}\right|=1,
$$

so oscillation produces cancellation but no probabilistic suppression. If the configuration space has infinite volume, the total variation of the would-be complex measure is formally infinite.

For example, the expression

$$
e^{ix^2}dx
$$

can define an oscillatory distribution after a prescription, but its total variation would be

$$
|e^{ix^2}|dx=dx,
$$

which has infinite mass on $\mathbb R$. In field theory the corresponding problem is much worse because the configuration space is infinite-dimensional.

The absence of positivity also causes the numerical sign problem: sampling a probability measure is natural, sampling a rapidly oscillating complex phase is not.

## No infinite-dimensional Lebesgue measure

Even before adding the phase $e^{iS}$, the formal symbol

$$
\mathcal D\phi
$$

cannot mean translation-invariant Lebesgue measure on an infinite-dimensional field space. There is no locally finite, nontrivial, countably additive translation-invariant measure on an infinite-dimensional separable Banach space with the properties one expects from Lebesgue measure.

Euclidean field theory does not solve this by inventing such a measure. It usually starts from a Gaussian measure $\mu_C$ and then, if possible, defines an interacting measure by

$$
d\mu=Z^{-1}e^{-V}d\mu_C.
$$

Lorentzian notation often pretends to start from something like

$$
e^{iS[\phi]}\mathcal D\phi,
$$

but neither factor is independently a good measure-theoretic object. A rigorous construction must replace the whole expression, not merely patch $\mathcal D\phi$.

## Hyperbolic rather than elliptic behavior

Euclidean free fields are governed by elliptic operators such as

$$
-\Delta_E+m^2,
$$

whose inverse has smoothing and positivity properties useful in probability. Lorentzian free fields are governed by hyperbolic operators such as

$$
\Box+m^2.
$$

Hyperbolic equations propagate singularities along light cones. Their inverses are not unique: one has retarded, advanced, Feynman, anti-Feynman, and other propagators depending on boundary conditions and state choices.

For the scalar field, the formal denominator

$$
\frac{1}{p^2-m^2}
$$

is incomplete. The Feynman distribution is

$$
\frac{i}{p^2-m^2+i\epsilon},
$$

while retarded and advanced propagators use different prescriptions. The singular support and wavefront set of these distributions are part of the definition.

Thus Lorentzian QFT is not just Euclidean QFT with $t$ changed back to real time. It has causal propagation, state-dependent singularity structure, and boundary-value prescriptions.

## Ultraviolet singularities

The free scalar field is already distribution-valued. Local interactions require products such as

$$
\phi(x)^2,
\qquad
\phi(x)^4,
\qquad
T\{\phi(x_1)\cdots\phi(x_n)\}
$$

at coincident or partially coincident points. These products are generally undefined without renormalization.

In Euclidean constructive QFT, one introduces cutoffs and counterterms, then tries to prove convergence of measures or Schwinger functions. In Lorentzian perturbation theory, one defines time-ordered products as distributions on configuration space and extends them across diagonals. The extension is not unique; renormalization conditions classify the ambiguity.

The path-integral notation hides this. It suggests one can simply integrate over all fields with the bare local action. Rigorous QFT says instead:

$$
\text{local Lorentzian interaction}
\quad\Rightarrow\quad
\text{renormalized products and prescriptions.}
$$

## Continuum limits of oscillatory objects

Finite-dimensional oscillatory integrals can be delicate but manageable. Infinite-dimensional limits are harder because cancellation can destroy ordinary compactness arguments.

For positive measures, a standard strategy is to prove tightness and convergence of finite-dimensional distributions. For oscillatory objects, total variation bounds are usually absent. Even if each cutoff expression

$$
Z_\Lambda[J]
=
\int^{\mathrm{osc}}d\phi_\Lambda\,
 e^{iS_\Lambda[\phi_\Lambda]+i\langle J,\phi_\Lambda\rangle}
$$

is defined, the limit

$$
\lim_{\Lambda\to\infty}Z_\Lambda[J]
$$

may fail to exist, depend on the prescription, or exist only as an asymptotic formal series.

This is one reason rigorous constructions often go through Euclidean probability first. Positive or reflection-positive Euclidean objects provide compactness tools that real-time oscillatory integrals lack.

## Gauge redundancy

Gauge fields add a separate problem. The formal integral

$$
\int\mathcal DA\,e^{iS[A]}
$$

overcounts gauge-equivalent configurations. The quadratic form has zero directions along gauge orbits, so the naive Gaussian determinant is ill-defined.

Perturbative physics introduces gauge fixing and ghosts. More invariant approaches use BRST or BV formalisms, where gauge symmetry is treated cohomologically. Nonperturbatively, gauge theory also has global issues: Gribov ambiguities, bundle topology, boundary conditions, line operators, and choices of global form of the gauge group.

Thus the Lorentzian path integral for gauge theory is not merely

$$
\frac{1}{\operatorname{Vol}(\mathcal G)}
\int\mathcal DA\,e^{iS[A]}.
$$

That expression is a useful slogan, not a complete construction.

## Wick rotation is conditional

The Euclidean-to-Lorentzian bridge is powerful but conditional. Osterwalder–Schrader reconstruction shows that Euclidean Schwinger functions satisfying suitable axioms reconstruct a Lorentzian Wightman theory. But the hypotheses are strong: reflection positivity, Euclidean invariance, symmetry, regularity, clustering, and growth conditions all matter.

In practical physics one often performs a Wick rotation in momentum integrals. In rigorous QFT the issue is broader. One needs analytic functions with the correct domains and boundary values. Singularities may obstruct contour deformation. In gauge theories, finite-temperature systems, curved spacetimes, nonequilibrium states, and theories with chemical potentials, there may be no simple Euclidean counterpart with the desired positivity.

The safest statement is:

$$
\text{Euclidean construction + OS axioms}
\quad\Rightarrow\quad
\text{Lorentzian QFT},
$$

not

$$
\text{any Euclidean-looking integral}
\quad\Rightarrow\quad
\text{real-time QFT}.
$$

## What works instead

The failure of a literal Lorentzian measure does not leave a vacuum. It leads to several rigorous substitutes.

| Goal | Better-defined framework |
|---|---|
| Real-time quantum mechanics | Self-adjoint Hamiltonians and unitary groups; time-sliced formulas when justified. |
| Free Lorentzian fields | Operator-valued distributions, Wightman functions, CCR/CAR algebras. |
| Nonperturbative scalar models in low dimensions | Euclidean constructive QFT plus Osterwalder–Schrader reconstruction. |
| Perturbative interacting fields | Causal perturbation theory, Epstein–Glaser extension, perturbative algebraic QFT. |
| Curved spacetime QFT | Algebraic QFT with Hadamard states and microlocal spectrum condition. |
| Gauge theory perturbation theory | BRST/BV complexes and renormalized time-ordered products. |
| Complex saddles and phases | Contour prescriptions and Picard–Lefschetz analysis, usually model by model. |
| Numerical real-time dynamics | Schwinger–Keldysh methods, tensor networks, Hamiltonian simulation, or analytic continuation, each with its own limitations. |

A rigorous page should therefore not ask the path integral to be all of these at once. It should state which object is being constructed.

## The Schwinger–Keldysh contour

Real-time expectation values are often not vacuum transition amplitudes but in-in quantities:

$$
\langle \Omega|\mathcal O(t)|\Omega\rangle.
$$

The Schwinger–Keldysh or closed-time-path formalism doubles fields on a forward and backward time contour. Symbolically one writes

$$
\int\mathcal D\phi_+\mathcal D\phi_-
\exp\left(iS[\phi_+]-iS[\phi_-]\right).
$$

This formalism is indispensable in nonequilibrium physics, finite-density systems, open quantum systems, and real-time response. But it does not by itself turn the expression into a positive measure. The doubled structure encodes unitarity and causal response identities, not ordinary probability on classical field histories.

A rigorous treatment still needs an underlying Hilbert-space, algebraic, perturbative, or regulator-based construction.

## A diagnostic checklist

When encountering a Lorentzian path integral in a paper or textbook, ask the following.

| Question | Why it matters |
|---|---|
| What is the target object? | Kernel, correlation function, S-matrix element, effective action, state, or algebra? |
| Is the theory finite-dimensional, quantum-mechanical, or field-theoretic? | The mathematical problems differ sharply. |
| Is the integral meant exactly or perturbatively? | A formal power series is not a convergent integral. |
| What is the pole or contour prescription? | It selects boundary conditions and distributions. |
| What is the regulator? | UV and IR cutoffs may be hidden in notation. |
| What is being renormalized? | Bare parameters, fields, composite operators, and time-ordered products may all require choices. |
| Is there gauge redundancy? | Gauge fixing, ghosts, BRST/BV data, and global sectors may be required. |
| Is positivity used? | If yes, the argument may secretly be Euclidean or probabilistic. |
| Is Wick rotation justified? | Analyticity and reflection positivity are nontrivial assumptions. |

This checklist prevents a common mistake: treating a formal expression as a theorem because it looks familiar.

## Common pitfalls

**Saying that the Lorentzian path integral is simply not rigorous.** That is too crude. Some real-time path integrals are rigorous in quantum mechanics, free fields are rigorous as distributions, and perturbative Lorentzian QFT has rigorous algebraic formulations. What is false is the idea that the general interacting QFT expression is an ordinary measure.

**Thinking that $i\epsilon$ is only for convergence.** The $i\epsilon$ prescription also selects boundary values, time ordering, vacuum conditions, and pole placement.

**Assuming Euclidean and Lorentzian observables are the same object.** Euclidean Schwinger functions and Lorentzian Wightman or time-ordered functions are related by analytic continuation only under hypotheses.

**Ignoring real-time state dependence.** In Lorentzian QFT, the two-point singularity structure depends on the state class. In curved spacetime, the Hadamard condition replaces a naive vacuum prescription.

**Treating gauge division formally.** Dividing by the volume of the gauge group is not a construction. Gauge fixing, ghost determinants, BRST/BV cohomology, and global issues must be specified.

**Confusing computational success with mathematical existence.** Feynman rules can predict experiments with spectacular accuracy while the corresponding full nonperturbative Lorentzian integral remains undefined as a measure.

## Relations to other pages

This page closes the Path Integrals as Measures chapter by explaining the boundary of the word "measure." It should be read after [Oscillatory Integrals and Lorentzian Path Integrals](/rigorous-qft/path-integrals-as-measures/oscillatory-integrals-and-lorentzian-path-integrals/).

The main bridges are:

- [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) for positive constructive objects;
- [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) for one rigorous Euclidean-to-Lorentzian route;
- [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) for Lorentzian correlation distributions;
- [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) for state-dependent Lorentzian singularities on curved spacetime;
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) for the distributional language behind products and time ordering.

## Research status

There is no general theorem constructing arbitrary interacting Lorentzian QFT path integrals as ordinary countably additive complex measures with density $e^{iS}$. For many rigorous purposes, this is the wrong target.

The strongest existing frameworks define different but related objects. Wightman and algebraic QFT define Lorentzian operator or algebraic structures directly. Osterwalder–Schrader theory reconstructs Lorentzian QFT from Euclidean Schwinger functions. Constructive QFT builds Euclidean measures or correlation functions for selected models. Perturbative algebraic QFT constructs interacting fields as formal power series using locality and microlocal analysis. Lattice and Hamiltonian methods provide regulator-dependent approximations whose continuum limits are major mathematical problems.

Real-time nonperturbative QFT remains especially hard in gauge theories, finite-density systems, nonequilibrium settings, and quantum gravity. The path-integral notation remains central, but its rigorous interpretation is plural.

## Exercises

### Exercise 1: Total variation obstruction in finite dimensions

Consider the formal complex density

$$
d\nu(x)=e^{ix^2}dx
$$

on $\mathbb R$. Show that it cannot be a finite complex measure absolutely continuous with respect to Lebesgue measure with this density.

<details><summary><strong>Solution</strong></summary>

If $d\nu=e^{ix^2}dx$, then the total variation measure would have density

$$
|e^{ix^2}|=1.
$$

Thus

$$
|\nu|(\mathbb R)=\int_{\mathbb R}dx=\infty.
$$

So $\nu$ is not a finite complex measure on $\mathbb R$. The oscillatory integral may still exist as a distributional or regularized object, but not as a finite measure with finite total variation.

</details>

### Exercise 2: Why Euclidean damping helps

Compare the two one-dimensional integrals

$$
I_L=\int_{\mathbb R}e^{ix^2}dx,
\qquad
I_E=\int_{\mathbb R}e^{-x^2}dx.
$$

Which one is absolutely convergent, and why?

<details><summary><strong>Solution</strong></summary>

The Euclidean integral is absolutely convergent because

$$
|e^{-x^2}|=e^{-x^2},
$$

and

$$
\int_{\mathbb R}e^{-x^2}dx=\sqrt{\pi}<\infty.
$$

The Lorentzian oscillatory integral is not absolutely convergent because

$$
|e^{ix^2}|=1,
$$

so

$$
\int_{\mathbb R}|e^{ix^2}|dx=\infty.
$$

It may be assigned an oscillatory value by a prescription, but that is different from absolute convergence.

</details>

### Exercise 3: Propagator prescriptions

Explain why the symbol

$$
\frac{1}{p^2-m^2}
$$

is not enough to define a Lorentzian two-point distribution.

<details><summary><strong>Solution</strong></summary>

The denominator vanishes on the mass shell $p^2=m^2$, so the expression has singularities. Different prescriptions specify different boundary values around these singularities. For example, the Feynman prescription is

$$
\frac{i}{p^2-m^2+i\epsilon},
$$

while retarded and advanced propagators use different placements relative to the energy variable. These choices encode different support, causality, and time-ordering properties. Therefore the algebraic fraction alone does not define a distribution.

</details>

### Exercise 4: Diagnose a formal expression

A paper writes

$$
Z=\int\mathcal DA\,e^{iS_{\mathrm{YM}}[A]}.
$$

List four pieces of additional information needed before this can be treated as a mathematical construction.

<details><summary><strong>Solution</strong></summary>

Reasonable answers include:

1. the spacetime manifold, boundary conditions, and signature;
2. the gauge group, global form of the gauge group, and bundle sectors;
3. a gauge-fixing or BRST/BV prescription;
4. ultraviolet and infrared regulators;
5. the contour or $i\epsilon$ prescription;
6. the renormalization scheme and bare-parameter tuning;
7. the target object, such as a formal perturbative series, a lattice limit, an S-matrix element, or a correlation function;
8. the topology in which the regulator is supposed to converge.

Any four of these show that the bare symbol is not yet a definition.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

### Deeper references

- Sergio A. Albeverio, Raphael J. Høegh-Krohn, and Sonia Mazzucchi, *Mathematical Theory of Feynman Path Integrals: An Introduction*, second corrected and enlarged edition, Lecture Notes in Mathematics **523**, Springer, 2008. DOI: [10.1007/978-3-540-76956-9](https://doi.org/10.1007/978-3-540-76956-9).
- R. H. Cameron, "A Family of Integrals Serving to Connect the Wiener and Feynman Integrals," *Journal of Mathematics and Physics* **39** (1960), 126–140. DOI: [10.1002/sapm1960391126](https://doi.org/10.1002/sapm1960391126).
- Edward Witten, "Analytic Continuation Of Chern-Simons Theory," arXiv: [1001.2933](https://arxiv.org/abs/1001.2933); in *Chern–Simons Gauge Theory: 20 Years After*, AMS/IP Studies in Advanced Mathematics **50**, 2011.
- Michael Dütsch and Klaus Fredenhagen, "Perturbative Algebraic Field Theory, and Deformation Quantization," arXiv: [hep-th/0101079](https://arxiv.org/abs/hep-th/0101079).
- Romeo Brunetti, Michael Dütsch, and Klaus Fredenhagen, "Perturbative Algebraic Quantum Field Theory and the Renormalization Groups," *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. arXiv: [0901.2038](https://arxiv.org/abs/0901.2038).
- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory — an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Robert M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994. ISBN: [9780226870274](https://press.uchicago.edu/ucp/books/book/chicago/Q/bo3684008.html).
- Christian Bär, Nicolas Ginoux, and Frank Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*, European Mathematical Society, 2007. DOI: [10.4171/037](https://doi.org/10.4171/037).

## Version history

- **2026-06-30:** Initial polished draft.
