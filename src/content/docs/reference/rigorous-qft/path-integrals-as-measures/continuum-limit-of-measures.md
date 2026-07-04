---
title: "Continuum Limit of Measures"
description: "Explains what it means to remove ultraviolet and infrared cutoffs from Euclidean field measures, and which notions of convergence are used in rigorous QFT."
sidebar:
  label: "Continuum Limits"
  order: 7
level: Graduate
status: "Polished draft"
source: "Glimm–Jaffe constructive QFT; Simon functional integration; Wilson–Kogut RG; Osterwalder–Schrader Euclidean QFT; weak convergence of measures."
topics:
  - continuum limits
  - weak convergence
  - Schwinger functions
  - renormalization
  - cutoff measures
  - constructive QFT
canonicalTopics:
  - continuum-limit-of-measures
  - weak-convergence
  - schwinger-functions
  - cutoff-removal
  - constructive-qft
  - euclidean-measure
researchStatus:
  established:
    - "For many finite-cutoff Euclidean scalar models the measures are honest probability measures, and in important low-dimensional models one can prove nontrivial continuum limits after renormalization."
  active:
    - "Existence, uniqueness, nontriviality, universality, and Osterwalder–Schrader properties of continuum limits remain model-dependent, especially in four-dimensional interacting gauge and scalar theories."
---

## Summary

The continuum limit of a Euclidean field theory is not the formal operation of erasing the cutoff symbol from an integral. It is a convergence problem for measures, Schwinger functions, or observables. A typical target statement has the form

$$
\lim_{\Lambda\nearrow \mathbb R^d,\,\kappa\to\infty}
\int F(\Phi)
\,d\mu_{\Lambda,\kappa}^{\mathbf b(\kappa)}(\Phi)
=
\int F(\Phi)\,d\mu(\Phi),
$$

where $\Lambda$ is an infrared cutoff, $\kappa$ is an ultraviolet cutoff, and $\mathbf b(\kappa)$ denotes cutoff-dependent bare parameters and counterterms.

The limit may be phrased in several equivalent or partially equivalent ways: convergence of finite-dimensional distributions of smeared fields, convergence of Schwinger functions, weak convergence of probability measures on a distribution space, or convergence of effective interactions under a renormalization group map. The right formulation depends on the model and on what properties one wants to prove.

The main lesson is that cutoff removal has three jobs. It must produce finite limits, avoid collapse to a trivial theory, and preserve the structural axioms needed for Euclidean or Lorentzian QFT. In particular, a limiting probability measure is not enough by itself; for relativistic QFT one also needs Osterwalder–Schrader properties such as reflection positivity, Euclidean covariance, symmetry, and suitable regularity.

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/), and [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/). For the constructive context, use [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) and [What Is Open in Four Dimensions](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/).

## Core idea

A cutoff Euclidean theory is usually easy to define. The hard part is proving that a family of such theories converges to a nontrivial object as the cutoffs are removed. The diagram below shows the logic.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A continuum limit of cutoff Euclidean measures proceeds through renormalized observables, convergence checks, a limiting measure, and Osterwalder–Schrader reconstruction.](/figures/rigorous-qft/continuum-limit-measures.svg)

<figcaption>

Cutoff removal is a convergence theorem. The bare parameters are allowed, and usually required, to depend on the cutoff. The output can be a limiting measure, limiting Schwinger functions, or a reconstructed Lorentzian theory if the Osterwalder–Schrader hypotheses hold.

</figcaption>
</figure>

The mental model is:

1. define a family of finite-cutoff measures;
2. choose the cutoff dependence of masses, couplings, field normalizations, and vacuum-energy constants;
3. prove convergence of selected observables or distributions;
4. identify the limiting object;
5. check the axioms or structural properties that make the limit a QFT rather than merely a probability measure.

The word "renormalized" belongs inside this list. The continuum limit is not a limit at fixed bare Lagrangian in most interacting theories.

## Setup and conventions

We work in Euclidean signature on $\mathbb R^d$. Let $E$ be a nuclear test-function space, often $\mathcal S(\mathbb R^d)$ or $C_c^\infty(\mathbb R^d)$, and let $E'$ be its distributional dual. A random field is treated through the smeared variables

$$
\Phi(f),\qquad f\in E.
$$

A cutoff theory may be a finite-dimensional lattice measure, a smooth Gaussian field with covariance cutoff, a finite-mode spectral approximation, or a finite-volume interacting density relative to a Gaussian reference measure. We denote it schematically by

$$
\mu_{\Lambda,\kappa}^{\mathbf b(\kappa)},
$$

where $\Lambda$ is the region, $\kappa$ is the UV resolution, and $\mathbf b(\kappa)$ collects bare data. For a scalar model this data might include

$$
\mathbf b(\kappa)
=\bigl(m_\kappa^2,\lambda_\kappa,Z_\kappa,E_\kappa,\ldots\bigr),
$$

with $Z_\kappa$ a field-strength factor and $E_\kappa$ a vacuum-energy counterterm.

The Schwinger functions of the cutoff theory are

$$
S_{n,\Lambda,\kappa}(f_1,\ldots,f_n)
=
\int
\Phi(f_1)\cdots\Phi(f_n)
\,d\mu_{\Lambda,\kappa}^{\mathbf b(\kappa)}(\Phi).
$$

When kernels exist, one writes $S_{n,\Lambda,\kappa}(x_1,\ldots,x_n)$, but the smeared definition is safer and is the one used here.

## Logical status

| Item | Status in this page |
|---|---|
| Type | Construction framework and convergence criterion. |
| Basic input | A family of cutoff Euclidean measures or Schwinger functions. |
| Main output | A limiting measure, a compatible family of limiting moments, or a reconstructed QFT. |
| Necessary choices | Topology on field space, observable class, cutoff-removal path, and renormalization conditions. |
| Caveat | Different notions of convergence are not automatically equivalent in infinite dimensions. |

A continuum limit theorem is stronger than a formal scaling argument and weaker than a complete classification of universality. It says that a specified family converges, usually after tuning, and that the limit has specified properties.

## What convergence can mean

### Convergence of expectations

The most direct statement fixes a class of observables $\mathcal F$ and asks whether

$$
\lim_{\Lambda,\kappa}
\mathbb E_{\Lambda,\kappa}[F]
$$

exists for every $F\in\mathcal F$. If $F$ is a bounded continuous function on $E'$, this is the usual language of weak convergence of probability measures. If $F$ is a polynomial in smeared fields, this is moment convergence.

The choice of $\mathcal F$ matters. Convergence of all bounded continuous functionals is strong and often difficult. Convergence of smeared $n$-point functions is physically natural but may not by itself determine a unique probability measure unless moment growth and positivity conditions are controlled.

### Convergence of finite-dimensional distributions

Given test functions $f_1,\ldots,f_N$, the cutoff field defines a probability law on $\mathbb R^N$ by

$$
\Phi\longmapsto
\bigl(\Phi(f_1),\ldots,\Phi(f_N)\bigr).
$$

A natural requirement is that these finite-dimensional laws converge for every finite list of test functions. This is the continuum-field analogue of convergence of all joint distributions.

If the limiting finite-dimensional laws are compatible and satisfy an extension theorem, they define a cylinder measure or an actual measure on $E'$. The [Minlos Theorem Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/) explains one clean route when the characteristic functional is continuous and positive-definite on a nuclear space.

### Convergence of Schwinger functions

For QFT, the standard observable data are Schwinger functions. One asks whether

$$
S_n(f_1,\ldots,f_n)
=
\lim_{\Lambda,\kappa}
S_{n,\Lambda,\kappa}(f_1,\ldots,f_n)
$$

exists and satisfies the Euclidean axioms. The point is not only to get limits, but to get limits with structure:

$$
\begin{gathered}
\text{symmetry under permutations},\qquad
\text{Euclidean covariance},\\
\text{reflection positivity},
\qquad
\text{clustering or mass-gap behavior},\\
\text{regularity and growth conditions.}
\end{gathered}
$$

Schwinger-function convergence is often the most efficient route from constructive Euclidean field theory to axiomatic QFT, because the Osterwalder–Schrader reconstruction theorem is formulated in terms of such functions.

## The cutoff family

A simple scalar cutoff family has the form

$$
d\mu_{\Lambda,\kappa}(\phi)
=
Z_{\Lambda,\kappa}^{-1}
\exp\bigl(-V_{\Lambda,\kappa}(\phi)\bigr)
\,d\mu_{C_\kappa}(\phi),
$$

where $C_\kappa$ is a regularized covariance and $V_{\Lambda,\kappa}$ is a finite-volume regularized interaction. In a renormalized model one should write

$$
V_{\Lambda,\kappa}
=
\int_\Lambda
\mathcal L_{\mathrm{int},\kappa}
\bigl(\phi_\kappa(x)\bigr)
\,d^dx,
$$

with $\mathcal L_{\mathrm{int},\kappa}$ depending on counterterms.

For example, the symbolic $\phi^4$ interaction in low dimensions may be represented by

$$
\int_\Lambda
\left[
\lambda_\kappa :\!\phi_\kappa(x)^4\!:
+
\frac12\delta m_\kappa^2 :\!\phi_\kappa(x)^2\!:
+E_\kappa
\right]d^dx,
$$

where Wick ordering and counterterms are defined relative to the chosen cutoff covariance. The details vary by dimension. The important point is structural: the limiting theory is defined by the whole renormalized family, not by a single bare expression.

## Tightness, moments, and the measure problem

Weak convergence of probability measures often proceeds through tightness. A family of probability measures $\{\mu_i\}$ on a topological space $X$ is tight if for every $\varepsilon>0$ there is a compact set $K_\varepsilon\subset X$ such that

$$
\mu_i(K_\varepsilon)>1-\varepsilon
\qquad\text{for all }i.
$$

On infinite-dimensional distribution spaces, compactness is subtle. One usually proves estimates on Sobolev or Besov norms, bounds on smeared moments, or covariance estimates that imply relative compactness in a suitable topology.

Moment convergence is also subtle. A collection of candidate moments must satisfy positivity. For real scalar fields, a minimal positivity condition says that for any polynomial functional

$$
P(\Phi)=\sum_\alpha c_\alpha
\Phi(f_{\alpha,1})\cdots \Phi(f_{\alpha,n_\alpha}),
$$

one should have

$$
\mathbb E\bigl[|P(\Phi)|^2\bigr]\geq 0.
$$

In terms of Schwinger functions this becomes a family of positivity inequalities. Moment growth conditions are then needed to ensure that the moment data determine a measure.

## Renormalization as stability of observables

Renormalization can be described as the search for cutoff-dependent coordinates in which long-distance observables stabilize. A typical renormalization condition fixes one or more observables at a reference scale:

$$
S_{2,\Lambda,\kappa}(f_R,f_R)=\text{prescribed value},
\qquad
S_{4,\Lambda,\kappa}(f_R,f_R,f_R,f_R)=\text{prescribed value}.
$$

These conditions determine $m_\kappa^2$, $\lambda_\kappa$, or $Z_\kappa$ as functions of the cutoff. The continuum limit is then taken along this tuned trajectory.

This is the measure-theoretic version of the Wilsonian picture. A cutoff defines coordinates on theory space. Removing the cutoff means following a trajectory toward a fixed point or along a critical surface so that macroscopic observables converge. The output is not merely a finite answer; it is a limiting law of the field.

## Gaussian example

The free massive scalar field gives the cleanest example. Let

$$
\widehat C_\kappa(p)
=
\frac{\chi(p^2/\kappa^2)}{p^2+m^2},
$$

where $\chi$ is smooth, bounded, and tends to $1$ on compact momentum sets as $\kappa\to\infty$. For test functions $f,g\in\mathcal S(\mathbb R^d)$,

$$
C_\kappa(f,g)
=
\int\frac{d^dp}{(2\pi)^d}
\widehat f(-p)
\frac{\chi(p^2/\kappa^2)}{p^2+m^2}
\widehat g(p)
$$

converges to

$$
C(f,g)
=
\int\frac{d^dp}{(2\pi)^d}
\widehat f(-p)
\frac{1}{p^2+m^2}
\widehat g(p).
$$

The characteristic functionals

$$
\exp\left(-\frac12 C_\kappa(f,f)\right)
$$

therefore converge to

$$
\exp\left(-\frac12 C(f,f)\right).
$$

By the Gaussian construction, this identifies the continuum Gaussian free field. Notice what made the example easy: no local product such as $\phi(x)^4$ had to be controlled. Interactions introduce exactly that difficulty.

## What can go wrong

Several failures are common and genuinely different.

**No limit.** The Schwinger functions may diverge, oscillate, or depend on the cutoff path.

**A trivial limit.** Correlations may converge to those of a free field or to a degenerate field even though the cutoff models were interacting. This is one form of the triviality problem.

**Regulator dependence.** Two cutoff schemes may produce inequivalent limiting theories unless the correct universality statement is proved.

**Loss of positivity.** A formal limiting set of functions may fail positivity, reflection positivity, or moment positivity.

**Loss of locality.** A regulator or renormalization procedure may leave nonlocal artifacts unless locality is recovered in the limit.

**Infrared failure.** Even if the UV limit exists in finite volume, the infinite-volume limit may fail because of massless modes, symmetry breaking, or phase coexistence.

## Checks

A well-stated continuum-limit result should say at least five things.

| Check | Question |
|---|---|
| Observable class | Which functions, fields, or Schwinger functions converge? |
| Topology | In what topology or distributional sense is convergence proved? |
| Renormalization | Which bare parameters depend on the cutoff? |
| Nontriviality | Why is the limit not zero, infinite, or merely Gaussian? |
| Structural axioms | Does the limit satisfy Euclidean covariance, reflection positivity, locality, or OS hypotheses? |

For a proposed continuum limit, ask these questions before trusting the notation. They separate a scaling argument from a construction.

## Common pitfalls

**Confusing regularization with renormalization.** A cutoff makes a model finite. Renormalization chooses cutoff dependence so that meaningful quantities converge.

**Demanding pointwise field convergence.** The continuum field may be distribution-valued. The natural quantities are smeared fields, Schwinger functions as distributions, or observables built from renormalized composite fields.

**Assuming moment convergence gives a measure.** Moment data require positivity, growth, and determinacy conditions. Without them, the moments may not define a unique probability measure.

**Assuming a Euclidean probability measure gives a relativistic QFT.** Reflection positivity and the rest of the OS hypotheses are additional constraints. A statistical Euclidean field theory can be mathematically meaningful without reconstructing a Lorentzian QFT.

**Treating universality as automatic.** To say that different regulators produce the same continuum theory is itself a theorem or a conjecture, not a definition.

## Relations to other pages

- [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/) explains the regularized objects whose limits are studied here.
- [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/) explains why interacting scalar measures are usually built relative to Gaussian reference measures.
- [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) gives the constructive-QFT version of the same problem.
- [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains how good Euclidean data can produce a Lorentzian Hilbert-space theory.
- [What Is Open in Four Dimensions](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/) explains why four-dimensional interacting continuum limits are especially delicate.

## Research status

The conceptual framework is established: continuum Euclidean QFT is a limit problem for measures, Schwinger functions, or RG trajectories. Constructive QFT provides rigorous examples in low dimensions, especially superrenormalizable scalar models and some fermionic models.

The general problem is far from solved. Four-dimensional interacting scalar theories face triviality questions; non-Abelian gauge theories require controlling gauge-invariant observables, continuum limits, and mass generation; fermionic theories have algebraic rather than probabilistic integration; and Lorentzian path integrals require different methods. The safe status label is therefore: framework established, examples deep and nontrivial, general existence problem open.

## Exercises

### Exercise 1: Gaussian covariance convergence

Let

$$
\widehat C_\kappa(p)
=
\frac{\chi(p^2/\kappa^2)}{p^2+m^2},
$$

where $0\leq \chi\leq 1$, $\chi(u)\to 1$ for fixed $u$ as $\kappa\to\infty$, and $f\in\mathcal S(\mathbb R^d)$. Show that $C_\kappa(f,f)\to C(f,f)$.

<details>
<summary><strong>Solution</strong></summary>

The difference is

$$
C(f,f)-C_\kappa(f,f)
=
\int\frac{d^dp}{(2\pi)^d}
\frac{1-\chi(p^2/\kappa^2)}{p^2+m^2}
|\widehat f(p)|^2.
$$

For each fixed $p$, the factor $1-\chi(p^2/\kappa^2)$ tends to zero. Since $f$ is Schwartz, $|\widehat f(p)|^2/(p^2+m^2)$ is integrable. The dominated convergence theorem gives the result.

</details>

### Exercise 2: Why fixed bare parameters are not enough

Explain why a sequence of cutoff interactions with fixed bare mass and fixed bare coupling is not, in general, the right definition of a continuum interacting QFT.

<details>
<summary><strong>Solution</strong></summary>

Local field products become increasingly singular as the UV cutoff is removed. The effects of these singularities can shift the physical mass, coupling, field normalization, and vacuum energy. If the bare parameters are kept fixed, the physical observables may diverge, vanish, or flow to an unintended theory. Renormalization chooses cutoff-dependent bare parameters so that chosen physical quantities remain finite and the limiting Schwinger functions have a chance to exist.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

### Deeper references

- Stephen J. Summers, "A Perspective on Constructive Quantum Field Theory," arXiv: [1203.3991](https://arxiv.org/abs/1203.3991).
- Vincent Rivasseau, "Constructive Renormalization Theory," arXiv: [math-ph/9902023](https://arxiv.org/abs/math-ph/9902023).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991.
- Patrick Billingsley, *Weak Convergence of Measures: Applications in Probability*, SIAM, 1971. DOI: [10.1137/1.9781611970623](https://doi.org/10.1137/1.9781611970623).
- Vladimir I. Bogachev, *Gaussian Measures*, Mathematical Surveys and Monographs **62**, American Mathematical Society, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the ε Expansion," *Physics Reports* **12** (1974), 75–200. DOI: [10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).

## Version history

- **2026-06-30:** Initial page on continuum limits of Euclidean measures, Schwinger functions, and cutoff removal.
