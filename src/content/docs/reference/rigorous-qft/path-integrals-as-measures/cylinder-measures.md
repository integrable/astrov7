---
title: "Cylinder Measures"
description: "Defines cylinder sets, cylindrical functions, and compatible finite-dimensional laws as the measure-theoretic precursor to continuum Euclidean fields."
sidebar:
  label: "Cylinder Measures"
  order: 3
level: Graduate
status: "Polished draft"
source: "Gaussian measures; Minlos theorem; projective-limit probability; constructive QFT."
topics:
  - cylinder measures
  - cylindrical functions
  - projective systems
  - generalized random fields
  - infinite-dimensional measures
canonicalTopics:
  - cylinder-measure
  - cylindrical-function
  - projective-limit
  - generalized-random-field
researchStatus:
  established:
    - "Cylinder measures rigorously organize the finite-dimensional distributions of a would-be random field."
  active:
    - "Turning cylinder data into a continuum QFT measure with Osterwalder–Schrader properties is model-dependent and usually much harder than checking finite-dimensional consistency."
---

## Summary

A cylinder measure is the bookkeeping device behind the phrase "all finite-dimensional distributions of a field." Instead of pretending that $\mathcal D\phi$ is an infinite-dimensional Lebesgue measure, one records the probability law of every finite list of smeared field variables

$$
\bigl(\Phi(f_1),\ldots,\Phi(f_n)\bigr).
$$

These finite-dimensional laws must agree when one forgets coordinates. If $L\subset K$ are finite-dimensional subspaces of a test-function space $E$, and $r_{LK}:K^*\to L^*$ is restriction, the consistency condition is

$$
(r_{LK})_*\mu_K=\mu_L.
$$

This compatibility defines a cylinder measure. It is exactly what finite cutoff path integrals and Gaussian random fields naturally produce. The caveat is crucial: a cylinder measure is not automatically a countably additive Radon probability measure on an infinite-dimensional configuration space. Extra hypotheses such as tightness, nuclearity, or constructive convergence are what turn compatible finite-dimensional data into an honest continuum measure.

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), and [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/). The next page, [Minlos Theorem Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/), explains one powerful condition under which cylinder data extend to a measure on distributions.

## Core idea

A continuum field is tested through finitely many linear probes. For a distributional configuration $u\in E'$, the probes are

$$
\nu_i(u)=\langle u,f_i\rangle,
\qquad f_i\in E.
$$

Every finite list $f_1,\ldots,f_n$ gives a finite-dimensional random vector. A cylinder measure is the compatible family of all these finite-dimensional laws.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A projective family of finite-dimensional laws for a cylinder measure.](/figures/rigorous-qft/cylinder-measure-consistency.svg)

<figcaption>

A cylinder measure is a compatible projective family. A larger set of test functions gives a law $\mu_K$ on $K^*$; forgetting some test functions pushes it forward to the smaller law $\mu_L$.

</figcaption>
</figure>

The slogan is

$$
\text{field measure}
\quad\leadsto\quad
\text{all finite smeared laws}
\quad\leadsto\quad
\text{compatibility under forgetting probes}.
$$

The last arrow is easy to write and hard to upgrade. The upgrade from compatible finite-dimensional laws to a genuine measure on $E'$ is the main point of extension theorems.

## Setup and conventions

Let $E$ be a real test-function space, for example $\mathcal S(\mathbb R^d)$ or $C_c^\infty(M)$. Let $E'$ be its continuous dual, interpreted as a space of generalized field configurations. The pairing is written

$$
\langle u,f\rangle,
\qquad u\in E',\quad f\in E.
$$

For a finite-dimensional subspace $L\subset E$, define the projection

$$
\pi_L:E'\longrightarrow L^*,
\qquad
\pi_L(u)(f)=\langle u,f\rangle.
$$

If $L=\operatorname{span}(f_1,\ldots,f_n)$ and the $f_i$ are linearly independent, this projection is equivalent to the coordinate map

$$
\pi_L(u)=
\bigl(\langle u,f_1\rangle,
\ldots,
\langle u,f_n\rangle\bigr)
\in \mathbb R^n.
$$

A subset of $E'$ is a cylinder set when it has the form

$$
\pi_L^{-1}(B),
\qquad B\subset L^* \text{ Borel},
$$

for some finite-dimensional $L$. A function on $E'$ is cylindrical when it has the form

$$
F(u)=F_L(\pi_L u),
$$

where $F_L$ is a measurable function on $L^*$.

## Consistent finite-dimensional laws

Suppose that for every finite-dimensional $L\subset E$ we are given a probability measure $\mu_L$ on $L^*$. If $L\subset K$, restriction gives a linear map

$$
r_{LK}:K^*\longrightarrow L^*,
\qquad r_{LK}(\ell)=\ell|_L.
$$

The laws are consistent when

$$
(r_{LK})_*\mu_K=\mu_L
\qquad \text{for every } L\subset K.
$$

Equivalently, for every bounded measurable $F_L$ on $L^*$,

$$
\int_{K^*} F_L(r_{LK}\xi)\,d\mu_K(\xi)
=
\int_{L^*} F_L(\eta)\,d\mu_L(\eta).
$$

A compatible family $\{\mu_L\}$ defines expectations of cylindrical functions by

$$
\int F\,d\mu_{\mathrm{cyl}}
:=
\int_{L^*}F_L(\eta)\,d\mu_L(\eta),
\qquad F=F_L\circ\pi_L.
$$

The compatibility condition ensures that this value does not depend on which finite-dimensional representation of $F$ is chosen.

## What the finite laws know

Cylinder measures know every finite list of smeared variables. For example, they know all quantities of the form

$$
\mathbb E_{\rm cyl}
\left[\prod_{a=1}^n \langle u,f_a\rangle\right],
$$

whenever the finite-dimensional moments exist. They also know all finite characteristic functions

$$
\mathbb E_{\rm cyl}
\left[
\exp\left(i\sum_{a=1}^n t_a\langle u,f_a\rangle\right)
\right].
$$

This is exactly the data used in Euclidean QFT when one specifies Schwinger functions or a generating functional for smeared fields. The measure-theoretic issue is whether this finite-dimensional data comes from a countably additive probability measure on an actual measurable space of distributions.

## Characteristic functionals

A compact way to specify a cylinder measure is a characteristic functional

$$
\chi:E\longrightarrow \mathbb C.
$$

For a finite list $f_1,\ldots,f_n$, define

$$
\chi_{f_1,\ldots,f_n}(t_1,\ldots,t_n)
=
\chi\left(\sum_{a=1}^n t_a f_a\right).
$$

If each $\chi_{f_1,\ldots,f_n}$ is the characteristic function of a probability measure on $\mathbb R^n$, then these measures are automatically compatible. A convenient sufficient finite-dimensional condition is positive-definiteness:

$$
\sum_{a,b=1}^N \overline{c_a}c_b\,
\chi(f_b-f_a)\ge 0
$$

for all $N$, all $c_a\in\mathbb C$, and all $f_a\in E$, together with $\chi(0)=1$. Bochner's theorem then supplies the finite-dimensional laws. The Minlos theorem adds the infinite-dimensional extension under nuclear-space hypotheses.

## Gaussian cylinder measures

Let $C:E\times E\to\mathbb R$ be a symmetric positive semidefinite bilinear form. The Gaussian characteristic functional is

$$
\chi_C(f)=\exp\left(-\frac12 C(f,f)\right).
$$

For a finite list $f_1,\ldots,f_n$, the associated random vector is centered Gaussian with covariance matrix

$$
C_{ab}=C(f_a,f_b).
$$

Compatibility follows because forgetting some test functions just takes a marginal of a multivariate Gaussian. Thus every positive covariance form gives a Gaussian cylinder measure. It gives an honest Gaussian probability measure on $E'$ only when the extension hypotheses are met.

For the massive free Euclidean scalar field,

$$
C_m(f,g)=
\int \frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2},
\qquad m>0,
$$

and the cylinder data are the finite-dimensional Gaussian laws of the smeared field variables $\Phi(f)$.

## Relation to cutoff path integrals

A finite cutoff path integral usually gives an honest finite-dimensional measure

$$
d\mu_N(\phi)=Z_N^{-1}e^{-S_N(\phi)}\,d\phi.
$$

If the cutoff variables are interpreted as coordinates of finitely many modes, then every finite list of smeared observables has a law. A continuum limit should produce a compatible family of such laws as the cutoff is removed.

In constructive QFT, this step is where analysis enters. One must prove convergence of the finite-dimensional distributions, identify the limiting cylinder measure, extend it to a genuine measure on a distribution space, and then check physical properties such as Euclidean covariance, reflection positivity, clustering, and regularity.

## Cylinder measure versus honest measure

The distinction can be summarized as follows.

| Object | What it controls | What may still be missing |
|---|---|---|
| Finite-dimensional law $\mu_L$ | Joint law of finitely many smeared fields. | Consistency with larger sets of probes. |
| Cylinder measure $\{\mu_L\}$ | All finite-dimensional laws, consistently. | Countable additivity on a useful sigma algebra. |
| Probability measure on $E'$ | Expectations of general measurable functions of distributions. | QFT axioms such as reflection positivity and locality. |
| Euclidean QFT measure | A measure with the extra structure needed for OS reconstruction. | Lorentzian scattering, gauge constraints, and model-specific dynamics. |

The cylinder measure is therefore not a failure. It is the correct intermediate object. It is where one can state exactly what finite-dimensional path-integral expressions are claiming before asking whether a continuum measure exists.

## Common pitfalls

**Calling a cylinder measure a path integral measure too early.** Compatibility of finite-dimensional marginals is not the same as a countably additive probability measure on $E'$.

**Forgetting the test functions.** The coordinates are not point values $\phi(x)$; they are smeared pairings $\langle u,f\rangle$. Point fields are typically singular shorthand.

**Confusing probabilistic positivity with reflection positivity.** A cylinder measure may be positive as a probability object without satisfying the Osterwalder–Schrader reflection-positivity condition needed for Lorentzian reconstruction.

**Assuming moments determine everything.** Moments are useful, but characteristic functionals are safer. Moment problems can have non-unique solutions unless growth or analyticity conditions are imposed.

**Ignoring support.** Even when a measure exists, it may live on distributions rather than functions. For free fields this is the rule, not the exception.

## Relations to other pages

[Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) gives the main free-field example of cylinder data. [Minlos Theorem Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/) explains when characteristic functionals on nuclear spaces become probability measures on dual spaces. [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) explains the constructive-QFT version of the same problem for interacting models. [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains why not every Euclidean measure is already a Lorentzian QFT.

## Research status

Cylinder measures are standard measure-theoretic objects. Their role in QFT is also settled: they are the correct finite-dimensional shadow of a random field. What is model-dependent is not the definition, but the proof that the cylinder data extend to a useful continuum measure with the right physical properties.

For free Gaussian fields over nuclear test-function spaces, Minlos-type theorems give a clean existence theorem. For interacting constructive models, one usually obtains the measure by cutoff removal, correlation inequalities, cluster expansions, stochastic quantization, or renormalization group methods. In gauge theories and Lorentzian theories, additional structural problems appear before the word "measure" can be used in the same way.

## Exercises

1. Let $L\subset K$ and let $\mu_K$ be a centered Gaussian measure on $K^*$ with covariance $C|_K$. Show that $(r_{LK})_*\mu_K$ is the centered Gaussian measure on $L^*$ with covariance $C|_L$.

<details><summary><strong>Solution</strong></summary>

A pushforward is determined by its characteristic function. For $f\in L$,

$$
\int_{L^*} e^{i\eta(f)}\,d(r_{LK})_*\mu_K(\eta)
=
\int_{K^*} e^{i(r_{LK}\xi)(f)}\,d\mu_K(\xi).
$$

Since $(r_{LK}\xi)(f)=\xi(f)$, this equals

$$
\exp\left(-\frac12 C(f,f)\right),
$$

which is the characteristic function of the centered Gaussian law on $L^*$ with covariance $C|_L$.

</details>

2. Suppose $F=F_L\circ\pi_L$ is also represented as $F=F_K\circ\pi_K$ with $L\subset K$ and $F_K=F_L\circ r_{LK}$. Show that the cylinder integral of $F$ is well-defined.

<details><summary><strong>Solution</strong></summary>

Using compatibility,

$$
\int_{K^*}F_K(\xi)\,d\mu_K(\xi)
=
\int_{K^*}F_L(r_{LK}\xi)\,d\mu_K(\xi)
=
\int_{L^*}F_L(\eta)\,d\mu_L(\eta).
$$

Thus integrating over the larger coordinate space and then forgetting coordinates gives the same answer as integrating directly over the smaller coordinate space.

</details>

3. Explain why the existence of all finite-dimensional distributions of a field does not by itself prove that the field has continuous sample paths.

<details><summary><strong>Solution</strong></summary>

Finite-dimensional distributions say what the random variables $\Phi(f_1),\ldots,\Phi(f_n)$ do for every finite list of test functions. Continuity of sample paths is a statement about the support and regularity of the random object as a function or distribution. That requires additional tightness and regularity estimates. For continuum free fields, the natural support is often a distribution space, not a space of continuous functions.

</details>

## References

### Standard first pass

- Vladimir I. Bogachev, *Gaussian Measures*, American Mathematical Society, 1998. DOI: [10.1090/surv/062](https://doi.org/10.1090/surv/062).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).

### Deeper references

- I. M. Gel'fand and N. Ya. Vilenkin, *Generalized Functions, Volume 4: Applications of Harmonic Analysis*, Academic Press, 1964.
- Hui-Hsiung Kuo, *Gaussian Measures in Banach Spaces*, Lecture Notes in Mathematics **463**, Springer, 1975. DOI: [10.1007/BFb0082007](https://doi.org/10.1007/BFb0082007).
- N. N. Vakhania, V. I. Tarieladze, and S. A. Chobanyan, *Probability Distributions on Banach Spaces*, Springer, 1987. DOI: [10.1007/978-94-009-3873-1](https://doi.org/10.1007/978-94-009-3873-1).
- R. A. Minlos, "Generalized Random Processes and Their Extension to a Measure," *Selected Translations in Mathematical Statistics and Probability* **3** (1963), 291–313; translated from *Trudy Moskovskogo Matematicheskogo Obshchestva* **8** (1959), 497–518.
- Leonard Gross, "Abstract Wiener Spaces," in *Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability*, Volume 2, 1967, 31–42. Project Euclid: [projecteuclid.org/euclid.bsmsp/1200513492](https://projecteuclid.org/euclid.bsmsp/1200513492).

## Version history

- **2026-06-30:** Initial page created for the Path Integrals as Measures chapter.
