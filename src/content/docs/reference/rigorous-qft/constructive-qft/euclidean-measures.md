---
title: "Euclidean Measures"
description: "Explains how Euclidean path integrals become probability measures on spaces of distributions and how their moments define Schwinger functions."
sidebar:
  label: "Euclidean Measures"
  order: 2
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe functional integrals; Simon P(φ)₂; Nelson Markov fields; Osterwalder–Schrader Euclidean QFT."
topics:
  - Euclidean measures
  - Schwinger functions
  - Gaussian free field
  - constructive QFT
  - reflection positivity
canonicalTopics:
  - euclidean-quantum-field-theory
  - path-integrals-as-measures
  - schwinger-functions
  - gaussian-random-fields
researchStatus:
  established:
    - "Free Euclidean scalar fields are Gaussian probability measures on spaces of distributions, and many low-dimensional interacting models are constructed as controlled perturbations or limits of such measures."
  active:
    - "For many physically important interacting and gauge theories, especially in four dimensions, constructing the desired continuum Euclidean measure remains difficult or open."
---

## Summary

A Euclidean measure is the rigorous version of a Euclidean path integral when the expression really can be interpreted as probability theory. Instead of writing only

$$
\int \mathcal D\phi\, e^{-S_E[\phi]}\,\phi(x_1)\cdots\phi(x_n),
$$

one constructs a probability measure $\mu$ on a space of generalized fields and defines Schwinger functions as its moments:

$$
S_n(f_1,\ldots,f_n)
=
\int \phi(f_1)\cdots\phi(f_n)\,d\mu(\phi).
$$

The measure usually lives on distributions, not on ordinary functions. For the massive free scalar field, the Euclidean measure is Gaussian with covariance

$$
C=(-\Delta+m^2)^{-1},
$$

meaning that its characteristic functional is

$$
\int e^{i\phi(f)}\,d\mu_C(\phi)
=
\exp\left(-\frac12\langle f,Cf\rangle\right).
$$

Interacting Euclidean QFT tries to replace this Gaussian measure by a renormalized non-Gaussian measure. That is the constructive path-integral problem.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), and [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/). The page [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) becomes relevant later when singularities are described microlocally rather than by covariance kernels alone.

## Core idea

The expression $\mathcal D\phi$ is not an infinite-dimensional Lebesgue measure. In infinite-dimensional spaces, there is no translation-invariant Lebesgue measure with the properties physicists would want. The rigorous replacement is to choose a real probability measure whose covariance, support, and moments encode the quantum field.

For scalar Euclidean fields, the free measure is the anchor. Interactions are then introduced as densities relative to the free measure, but only after cutoffs and renormalization. The clean slogan is

$$
\text{Euclidean QFT}=
\text{probability measure on generalized fields}
+\text{OS structure}.
$$

The first term gives moments. The second term says when those moments reconstruct a Lorentzian quantum theory.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Euclidean measure construction](/figures/rigorous-qft/euclidean-measure-construction.svg)

<figcaption>

A Euclidean measure turns the formal path integral into probability theory. The measure gives Schwinger functions, while reflection positivity and the other Osterwalder–Schrader conditions decide whether those functions reconstruct a Lorentzian QFT.

</figcaption>
</figure>

## Setup and conventions

Work on Euclidean $\mathbb R^d$ with coordinates $x=(\tau,\mathbf x)$ and Euclidean pairing $p^2=p_0^2+\mathbf p^2$. Test functions are smooth rapidly decreasing functions unless a finite-volume or compact-support variant is stated. A generalized field is a random distribution

$$
\phi\in \mathcal S'(\mathbb R^d),
$$

so that $\phi(f)$ is a real random variable for every real test function $f\in\mathcal S(\mathbb R^d)$.

For a probability measure $\mu$ on $\mathcal S'(\mathbb R^d)$, the Euclidean $n$-point functions are distributions defined by

$$
S_n(f_1,\ldots,f_n)
=
\mathbb E_\mu
\left[
\phi(f_1)\cdots\phi(f_n)
\right].
$$

When the moments have kernels, we write formally

$$
S_n(f_1,\ldots,f_n)
=
\int S_n(x_1,\ldots,x_n)
\prod_{j=1}^n f_j(x_j)\,d^dx_j.
$$

The kernel notation is convenient, but the distributional definition is safer. Coincident-point products usually require renormalization.

## Logical status

| Item | Status in this page |
|---|---|
| Type | Definition and construction framework. |
| Basic object | A probability measure on generalized Euclidean fields. |
| Main output | Schwinger functions as moments. |
| Reconstruction input | OS symmetry, Euclidean covariance, reflection positivity, clustering, and growth conditions. |
| Caveat | Not every formal Euclidean action defines a measure, and not every measure gives a Lorentzian QFT. |

Euclidean measures are rigorous objects, but they are not the whole story. A measure can be well-defined and still fail reflection positivity. It can have moments but fail growth conditions. It can describe a statistical field theory without reconstructing a relativistic quantum theory.

## The free Gaussian measure

The free massive scalar field is the model example. Define

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0.
$$

In momentum space,

$$
\langle f,Cg\rangle
=
\int \frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2}.
$$

The Gaussian measure $\mu_C$ is characterized by

$$
\mathbb E_{\mu_C}\bigl[e^{i\phi(f)}\bigr]
=
\exp\left(-\frac12\langle f,Cf\rangle\right).
$$

It follows that

$$
\mathbb E_{\mu_C}[\phi(f)]=0,
\qquad
\mathbb E_{\mu_C}[\phi(f)\phi(g)]=\langle f,Cg\rangle.
$$

All higher moments are determined by Wick's rule:

$$
S_{2n}(f_1,\ldots,f_{2n})
=
\sum_{\text{pairings }P}
\prod_{\{i,j\}\in P}\langle f_i,Cf_j\rangle,
\qquad
S_{2n+1}=0.
$$

This measure is not concentrated on smooth functions. In dimensions $d\ge2$, typical samples of the free field are distributions with negative regularity. This is not a defect; it is the Euclidean probability version of the statement that quantum fields are distributional objects.

## Why there is no flat measure

In finite dimensions, the Gaussian integral can be written relative to Lebesgue measure:

$$
d\mu_C(x)=
\frac{1}{(2\pi)^{N/2}(\det C)^{1/2}}
\exp\left(-\frac12 x\cdot C^{-1}x\right)d^Nx.
$$

One might hope to imitate this with $N=\infty$ and write

$$
\mathcal D\phi\,e^{-\frac12\langle\phi,C^{-1}\phi\rangle}.
$$

The rigorous construction reverses the logic. There is no background infinite-dimensional Lebesgue measure $\mathcal D\phi$. The Gaussian measure is primary, usually specified by its characteristic functional or by a projective family of finite-dimensional distributions. Interactions, when they make sense, are defined relative to this Gaussian measure.

This changes the meaning of the path integral. The phrase "density $e^{-S_E}$" is only meaningful after saying **with respect to which measure** and **with which renormalized fields**.

## Interacting measures with cutoffs

For a scalar interaction, the naive expression

$$
d\mu(\phi)\stackrel{?}{=}
\frac{1}{Z}
\exp\left(-\int P(\phi(x))\,d^dx\right)d\mu_C(\phi)
$$

is usually ill-defined. The field $\phi(x)$ does not exist pointwise, and powers such as $\phi(x)^4$ need renormalization.

A typical constructive definition introduces a mollified field $\phi_\epsilon$, a finite volume $\Lambda$, and Wick ordering:

$$
d\mu_{\Lambda,\epsilon}(\phi)
=
\frac{1}{Z_{\Lambda,\epsilon}}
\exp\left(
-\int_\Lambda :\!P_\epsilon(\phi_\epsilon(x))\!:\,d^dx
\right)d\mu_C(\phi).
$$

For example, a cutoff $\phi^4$ interaction may use

$$
:\!\phi_\epsilon(x)^4\!:
=
\phi_\epsilon(x)^4
-6C_\epsilon(x,x)\phi_\epsilon(x)^2
+3C_\epsilon(x,x)^2,
$$

with further counterterms depending on the dimension and renormalization scheme. The finite-volume cutoff measure is now a genuine probability measure when the interaction is stable. The constructive work is to prove that its moments or the measures themselves have useful limits as

$$
\Lambda\nearrow\mathbb R^d,
\qquad
\epsilon\to0.
$$

## Schwinger functions from moments

Given a measure $\mu$, the Schwinger functions are the moments of the random field. For a single test function $f$, the generating functional is

$$
Z(J)=\int e^{\phi(J)}\,d\mu(\phi),
$$

when the expression exists. More commonly one works with the characteristic functional

$$
\widehat\mu(f)=\int e^{i\phi(f)}\,d\mu(\phi).
$$

Moments can be recovered by differentiation at the origin:

$$
S_n(f_1,\ldots,f_n)
=\frac{1}{i^n}
\left.
\frac{\partial^n}{\partial t_1\cdots\partial t_n}
\widehat\mu\left(\sum_{j=1}^n t_jf_j\right)
\right|_{t=0}.
$$

Connected Schwinger functions come from the logarithm of the generating functional. In constructive arguments, connected functions are often easier to estimate because clustering and exponential decay are statements about connected correlations.

## Reflection positivity

A positive measure gives ordinary probabilistic positivity:

$$
\int |F(\phi)|^2\,d\mu(\phi)\ge0.
$$

Osterwalder–Schrader reconstruction needs a different positivity. Let $\theta$ be Euclidean time reflection, $\theta(\tau,\mathbf x)=(-\tau,\mathbf x)$, and let $\Theta F$ be the reflected functional. If $F$ depends only on the field at positive Euclidean times, reflection positivity requires

$$
\int (\Theta F)(\phi)\,F(\phi)\,d\mu(\phi)
\ge0.
$$

This is the condition that produces the Hilbert-space inner product after quotienting null vectors. It is the bridge from Euclidean probability to quantum positivity.

Finite-dimensional analogy can mislead here. Ordinary positivity of a measure is automatic once $\mu$ is a probability measure. Reflection positivity is a special compatibility between the measure and a chosen Euclidean time reflection.

## Measures, phases, and infinite volume

In finite volume, the normalized measure is often unique. In infinite volume, limits may depend on boundary conditions. This is familiar from statistical mechanics and essential in constructive QFT.

For instance, a symmetric finite-volume measure may converge to a symmetric mixture, while plus or minus boundary conditions may converge to distinct pure phases. The Schwinger functions then describe different states of the same formal model.

The infinite-volume issue is therefore not merely about making $\Lambda$ large. It is about selecting a physical state or phase. In Lorentzian reconstruction, this affects the vacuum, clustering, particle interpretation, and spontaneous symmetry breaking.

## Checks for a useful Euclidean measure

A Euclidean measure intended to define a relativistic QFT should pass several checks.

| Check | What it tests |
|---|---|
| Existence | The measure or all moments are well-defined. |
| Regularity | Moments are distributions with controlled growth. |
| Euclidean covariance | Schwinger functions transform correctly under Euclidean motions. |
| Symmetry | Bosonic Schwinger functions are permutation symmetric. |
| Reflection positivity | Positive-time observables give a Hilbert-space inner product. |
| Clustering | Widely separated observables factorize in a vacuum phase. |
| Nontriviality | The limit is not accidentally free or zero. |

Different constructive theorems package these checks differently. Some construct measures first and derive Schwinger functions. Others construct Schwinger functions directly and verify OS axioms. Both routes are legitimate if the final assumptions are explicit.

## Common pitfalls

**Thinking $\mathcal D\phi$ is a hidden Lebesgue measure.** In infinite dimensions there is no such measure with the expected translation invariance. The Gaussian measure, not a flat measure, is the rigorous starting point.

**Expecting fields to be functions.** The free Euclidean field is typically a random distribution. Interacting fields are at least as singular, and composite fields require renormalization.

**Confusing probabilistic positivity with reflection positivity.** A probability measure makes $\int |F|^2d\mu$ nonnegative. Reconstruction needs the reflected form $\int \Theta F\,F\,d\mu$ to be nonnegative for positive-time functionals.

**Writing $e^{-\int P(\phi)}$ before defining products.** Since $\phi(x)$ is not a pointwise random variable in the usual sense, local powers must be cutoff and renormalized before the exponential density can be interpreted.

**Ignoring infinite-volume boundary conditions.** Different boundary conditions can lead to different infinite-volume measures. That is a phase-selection fact, not merely a nuisance.

## Relations to other pages

- [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) explains how Euclidean measures fit into the larger cutoff-removal and reconstruction strategy.
- [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) gives the basic Gaussian example in more detail.
- [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) explains the key positivity condition needed for reconstruction.
- [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains how Schwinger functions produce a Lorentzian Hilbert space and Wightman fields.
- [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) explains why random fields and operator-valued fields must be smeared.

## Research status

The free Euclidean scalar measure is a standard, fully controlled object. Interacting low-dimensional scalar measures are among the major achievements of constructive QFT, especially in the $P(\phi)_2$ family and related models. The same probability viewpoint also underlies modern SPDE approaches to singular Euclidean fields.

The broad lesson is settled: Euclidean path integrals can sometimes be honest measures, but they require precise state spaces, regulators, counterterms, and positivity conditions. The open frontier is model-dependent. Four-dimensional interacting scalar theories raise triviality and ultraviolet-limit questions, while four-dimensional non-Abelian gauge theories require substantially more than the scalar Gaussian-measure template.

## Exercises

### Exercise 1: Recover the covariance

Starting from

$$
\widehat\mu_C(f)=
\exp\left(-\frac12\langle f,Cf\rangle\right),
$$

show that $\mathbb E_{\mu_C}[\phi(f)\phi(g)]=\langle f,Cg\rangle$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate the two-parameter characteristic functional

$$
\widehat\mu_C(tf+sg)
=
\exp\left(
-\frac12t^2\langle f,Cf\rangle
-ts\langle f,Cg\rangle
-\frac12s^2\langle g,Cg\rangle
\right).
$$

Since

$$
\mathbb E[\phi(f)\phi(g)]
=\frac{1}{i^2}
\left.\partial_t\partial_s\widehat\mu_C(tf+sg)\right|_{t=s=0},
$$

the two minus signs cancel and give $\langle f,Cg\rangle$.

</details>

### Exercise 2: Wick ordering in one variable

Let $X$ be a centered Gaussian random variable with variance $c$. Show that

$$
:X^4:=X^4-6cX^2+3c^2
$$

has expectation zero.

<details>
<summary><strong>Solution</strong></summary>

For a centered Gaussian variable, $\mathbb E[X^2]=c$ and $\mathbb E[X^4]=3c^2$. Therefore

$$
\mathbb E[:X^4:]
=3c^2-6c\cdot c+3c^2=0.
$$

The field-theoretic formula is the same idea applied to the cutoff random variable $\phi_\epsilon(x)$, whose variance is $C_\epsilon(x,x)$.

</details>

### Exercise 3: Ordinary positivity versus reflection positivity

Give an example of two different quadratic forms associated with a Euclidean measure and explain which one is relevant for OS reconstruction.

<details>
<summary><strong>Solution</strong></summary>

Ordinary probabilistic positivity is $\int |F|^2d\mu\ge0$. Reflection positivity is $\int \Theta F\,F\,d\mu\ge0$ for functionals supported at positive Euclidean time. OS reconstruction uses the second form because it is interpreted as the Hilbert-space inner product after reflecting one observable across the time-zero slice.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

### Euclidean probability and constructive measures

- Edward Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](<https://doi.org/10.1016/0022-1236(73)90091-8>).
- Edward Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](<https://doi.org/10.1016/0022-1236(73)90025-6>).
- Francesco Guerra, Lon Rosen, and Barry Simon, "The $P(\phi)_2$ Euclidean Quantum Field Theory as Classical Statistical Mechanics," *Annals of Mathematics* **101** (1975), 111–189 and 191–259. DOI: [10.2307/1970988](https://doi.org/10.2307/1970988) and [10.2307/1970989](https://doi.org/10.2307/1970989).
- Barry Simon and Raphael Høegh-Krohn, "Hypercontractive Semigroups and Two Dimensional Self-Coupled Bose Fields," *Journal of Functional Analysis* **9** (1972), 121–180.

## Version history

- **2026-06-29:** Initial page.
