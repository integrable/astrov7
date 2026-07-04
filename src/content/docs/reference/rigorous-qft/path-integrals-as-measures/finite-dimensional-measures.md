---
title: "Finite-Dimensional Measures"
description: "A precise finite-dimensional model of path-integral notation, explaining densities, expectations, sources, Gaussian integrals, and the first places where measure language can fail."
sidebar:
  label: "Finite-Dimensional Measures"
  order: 1
level: Graduate
status: "Polished draft"
source: "Finite-dimensional probability and Gaussian integration; Simon functional integration; Glimm–Jaffe constructive QFT; Osterwalder–Schrader Euclidean QFT."
topics:
  - path integrals
  - finite-dimensional measures
  - Gaussian integration
  - Euclidean QFT
  - constructive QFT
canonicalTopics:
  - path-integrals-as-measures
  - finite-dimensional-measure
  - gaussian-integral
  - euclidean-field-theory
researchStatus:
  established:
    - "Finite-dimensional Euclidean path integrals with integrable positive weights are ordinary probability measures, and their expectations are standard Lebesgue integrals."
  active:
    - "The infinite-dimensional continuum limit, gauge redundancy, fermionic variables, and Lorentzian oscillatory integrals require additional frameworks beyond this finite-dimensional model."
---

## Summary

A finite-dimensional Euclidean path integral is an ordinary integral. If $E_N\cong\mathbb R^N$, $dx$ is Lebesgue measure, and $S_N:E_N\to\mathbb R$ is such that $e^{-S_N}$ is integrable, then

$$
Z_N=
\int_{E_N} e^{-S_N(x)}\,dx,
\qquad
 d\mu_N(x)=Z_N^{-1}e^{-S_N(x)}\,dx
$$

defines a probability measure whenever $0<Z_N<\infty$. Observables are measurable functions $F:E_N\to\mathbb C$, and their expectation values are

$$
\langle F\rangle_N=
\int_{E_N}F(x)\,d\mu_N(x).
$$

This is the honest starting point for measure-theoretic path integrals. It explains why Euclidean lattice models, finite-mode cutoffs, and finite-volume approximations are rigorous before any continuum limit is taken.

The caveat is just as important: the formal Lorentzian expression $e^{iS}$ is not positive and usually does not define a probability measure. Also, a family of finite-dimensional measures is not automatically a continuum QFT. One still needs consistency, tightness or renormalized convergence, and axiom checks.

## Prerequisites

You should know the volume [Conventions](/rigorous-qft/conventions/), the constructive page [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), and the idea of [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/). The next page, [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), turns the finite-dimensional Gaussian prototype into a random distribution.

## Core idea

The path-integral slogan

$$
\int \mathcal D\phi\, e^{-S[\phi]}F(\phi)
$$

is modeled, at finite cutoff, by a perfectly ordinary probability expectation. A finite number of coordinates replaces the field, the action becomes a function of those coordinates, and the symbol $\mathcal D\phi$ becomes a genuine reference measure.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A finite-dimensional path-integral pipeline: vector space, Euclidean action, normalized density, probability measure, expectations, and possible continuum limits.](/figures/rigorous-qft/finite-dimensional-measure-pipeline.svg)

<figcaption>

In finite dimensions, a real Euclidean action with integrable $e^{-S_N}$ gives a normalized measure $d\mu_N$. The path integral is then an expectation. The hard QFT questions begin when $N\to\infty$, cutoffs are removed, gauge redundancies appear, or the weight is oscillatory rather than positive.

</figcaption>
</figure>

The finite-dimensional model is not a toy to be discarded. It is the local chart in which most rigorous constructions begin: finite lattice systems, spectral cutoffs, finite-volume Gaussian measures, and regularized interacting measures all use this template.

## Setup and conventions

Let $E_N$ be a real $N$-dimensional vector space. After choosing coordinates, write $E_N=\mathbb R^N$ with Borel $\sigma$-algebra $\mathcal B(E_N)$ and Lebesgue measure $dx$. A finite-dimensional Euclidean action is a measurable function

$$
S_N:E_N\longrightarrow \mathbb R\cup\{+\infty\}.
$$

The partition function is

$$
Z_N=
\int_{E_N} e^{-S_N(x)}\,dx.
$$

When $0<Z_N<\infty$, the normalized measure is

$$
d\mu_N(x)=Z_N^{-1}e^{-S_N(x)}\,dx.
$$

A statement such as

$$
\langle F\rangle_N=Z_N^{-1}
\int_{E_N}F(x)e^{-S_N(x)}\,dx
$$

is meaningful if $F$ is $\mu_N$-integrable. For complex observables, integrability means $\int |F|\,d\mu_N<\infty$.

In a finite lattice scalar model, $E_N$ may be the space of functions on $N$ lattice sites. A point $x\in E_N$ is then a vector

$$
\phi=(\phi_1,
\ldots,\phi_N),
$$

and a simple action has the form

$$
S_N(\phi)=
\frac12\sum_{i,j=1}^N \phi_i K_{ij}\phi_j
+\sum_{i=1}^N V(\phi_i).
$$

Here $K$ is a positive matrix encoding the kinetic term and mass, while $V$ encodes local interactions.

## Probability measure versus unnormalized weight

The unnormalized expression $e^{-S_N(x)}dx$ is a finite positive measure if $Z_N<\infty$. Dividing by $Z_N$ turns it into a probability measure. This distinction matters because many formulas use the unnormalized weight while probability statements use the normalized measure.

For example, the connected generating functional is usually defined from the source-dependent partition function

$$
Z_N(J)=
\int_{E_N}
\exp\bigl(-S_N(x)+J\cdot x\bigr)\,dx,
$$

where $J\in E_N^*$. The normalized moment-generating function is

$$
M_N(J)=\frac{Z_N(J)}{Z_N(0)}.
$$

Then

$$
\left.
\frac{\partial^n M_N(J)}
{\partial J_{i_1}\cdots\partial J_{i_n}}
\right|_{J=0}
=
\langle x_{i_1}\cdots x_{i_n}\rangle_N,
$$

when the derivatives are justified. Connected correlations are generated by

$$
W_N(J)=\log M_N(J).
$$

This is the finite-dimensional ancestor of Schwinger functions, connected correlators, and cumulants.

## The Gaussian prototype

The central example is the centered Gaussian measure. Let $A$ be a real symmetric positive-definite $N\times N$ matrix. Define

$$
S_0(x)=\frac12 x^TAx.
$$

Then

$$
Z_0=
\int_{\mathbb R^N}
\exp\left(-\frac12 x^TAx\right)dx
=(2\pi)^{N/2}(\det A)^{-1/2}.
$$

The normalized Gaussian measure is

$$
d\mu_A(x)=
(2\pi)^{-N/2}(\det A)^{1/2}
\exp\left(-\frac12 x^TAx\right)dx.
$$

Its covariance is

$$
C=A^{-1},
\qquad
\langle x_i x_j\rangle_A=C_{ij}.
$$

Equivalently, its characteristic function is

$$
\int_{\mathbb R^N} e^{ik\cdot x}\,d\mu_A(x)
=
\exp\left(-\frac12 k^T C k\right).
$$

The finite-dimensional free field is exactly this construction with $A$ chosen to be a discrete operator such as $-\Delta_N+m^2$.

## Wick's theorem in finite dimensions

For a centered Gaussian measure, all odd moments vanish and all even moments are sums over pairings. If $X_i(x)=x_i$, then

$$
\langle X_{i_1}\cdots X_{i_{2n}}\rangle_A
=
\sum_{\text{pairings }P}
\prod_{\{r,s\}\in P}
C_{i_r i_s}.
$$

In particular,

$$
\langle X_iX_jX_kX_\ell\rangle_A
=
C_{ij}C_{k\ell}
+C_{ik}C_{j\ell}
+C_{i\ell}C_{jk}.
$$

This is the probability version of Wick's theorem. In perturbative QFT, the covariance $C$ becomes the free propagator and the pairing formula becomes the combinatorial source of Feynman diagrams.

A second useful identity is Gaussian integration by parts. For smooth $F$ with sufficient decay,

$$
\langle X_i F(X)\rangle_A
=
\sum_{j=1}^N C_{ij}
\left\langle
\frac{\partial F}{\partial x_j}(X)
\right\rangle_A.
$$

This identity is the finite-dimensional seed of Schwinger–Dyson equations.

## Interactions as changes of measure

Many Euclidean interacting finite-cutoff models are defined relative to a Gaussian measure. Let $V:E_N\to\mathbb R\cup\{+\infty\}$ be measurable and assume

$$
0<Z_V=
\int e^{-V(x)}\,d\mu_A(x)<\infty.
$$

Then

$$
d\mu_{A,V}(x)=Z_V^{-1}e^{-V(x)}\,d\mu_A(x)
$$

is a probability measure absolutely continuous with respect to the Gaussian measure $\mu_A$.

This formula is more than notation. It tells us what is being proved in a finite-dimensional Euclidean construction:

| Ingredient | Meaning |
|---|---|
| $\mu_A$ | Free reference measure with covariance $A^{-1}$. |
| $e^{-V}$ | Interaction weight. |
| $Z_V$ | Normalization, or partition function relative to $\mu_A$. |
| $d\mu_{A,V}$ | Interacting finite-cutoff probability measure. |
| $\langle F\rangle_{A,V}$ | Interacting expectation of an observable. |

The finite-dimensional perturbative expansion is obtained by formally expanding $e^{-V}$ and evaluating Gaussian moments. The constructive question is different: whether the full measure exists and whether its cutoff sequence converges.

## Change of variables and Jacobians

Finite-dimensional measures transform by the ordinary change-of-variables formula. If $y=T(x)$ is an invertible smooth map, then

$$
\int_{E_N}F(y)\rho_Y(y)\,dy
=
\int_{E_N}F(T(x))\rho_Y(T(x))
\left|\det DT(x)\right|dx.
$$

In QFT this elementary formula becomes conceptually loaded. Field redefinitions, gauge transformations, chiral rotations, and changes of variables in path integrals all inherit a finite-dimensional Jacobian question. In infinite dimensions, the Jacobian can become a determinant requiring regularization, or it can encode an anomaly.

The finite-dimensional lesson is not that every path-integral Jacobian is harmless. The lesson is that a change of variables is a theorem with hypotheses. In continuum QFT, those hypotheses must be replaced by regulator-dependent or algebraic statements.

## Why positive Euclidean weights matter

If $S_N$ is real and bounded below strongly enough, $e^{-S_N}dx$ can be normalized. If $S_N$ is complex, the object

$$
 e^{-S_N(x)}dx
$$

is a complex measure only if its total variation is finite:

$$
\int |e^{-S_N(x)}|\,dx<\infty.
$$

The Lorentzian phase $e^{iS_N(x)}$ has modulus one, so on $\mathbb R^N$ it is not integrable against Lebesgue measure unless extra damping or contour prescriptions are supplied. At finite $N$, oscillatory integrals can often be defined by limits, distributions, or contour deformations. They are not probability measures.

This is why Euclidean path integrals are the natural home of measure theory, while Lorentzian path integrals require a different discussion. The finite-dimensional expression

$$
\int_{\mathbb R^N} e^{iS_N(x)}F(x)\,dx
$$

can be useful and rigorous in special oscillatory-integral settings, but its logic is not the logic of probability.

## From finite dimensions to fields

A cutoff scalar field may be represented by a finite vector

$$
\phi_N=
\sum_{a=1}^N q_a e_a,
$$

where $e_a$ are lattice basis functions, Fourier modes, or eigenfunctions of an elliptic operator. The finite-dimensional integral defines a measure on the coefficients $q_a$. The continuum question asks whether these measures have a limit as $N\to\infty$ and other cutoffs are removed.

There are several different limiting problems:

| Limiting problem | Typical tool |
|---|---|
| Consistent finite-dimensional marginals | Projective limits and cylinder measures. |
| Gaussian continuum fields | Characteristic functionals and Minlos-type theorems. |
| Interacting Euclidean fields | Cutoffs, Wick ordering, counterterms, and estimates. |
| Critical lattice scaling limits | Tightness, convergence of correlations, and universality. |
| Lorentzian continuum amplitudes | Analytic continuation, distributions, or oscillatory methods. |

Finite-dimensional rigor is therefore necessary but not sufficient. It tells us what each cutoff approximation means; it does not by itself solve the continuum problem.

## Common pitfalls

**Writing $\mathcal D\phi$ as if it were Lebesgue measure.** There is no translation-invariant Lebesgue probability measure on an infinite-dimensional separable Banach or Hilbert space. In finite dimensions, $dx$ is real. In infinite dimensions, the reference object must be constructed differently.

**Confusing the unnormalized weight with a probability measure.** The expression $e^{-S}dx$ is not a probability measure until it is normalized, and normalization can fail.

**Assuming that $e^{iS}$ is a measure.** A phase is not a positive density. Lorentzian path integrals may be defined by oscillatory-integral or distributional procedures, but not by the same probability argument used for Euclidean measures.

**Forgetting the cutoff dependence of the action.** In QFT, the finite-dimensional action usually depends on the cutoff. Counterterms and field normalizations are not decorative additions; they may be required for convergence.

**Treating gauge orbits as ordinary coordinates.** A gauge-redundant finite-dimensional integral often has infinite or overcounted volume unless one quotients, fixes gauge, or works only with gauge-invariant variables.

## Relations to other pages

[Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) explains how this finite-dimensional picture enters constructive QFT. [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) treats the free measure in the constructive chapter, while [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/) emphasizes the probability-theoretic transition from random vectors to random distributions.

[OS Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explain what additional Euclidean properties are needed to reconstruct Lorentzian QFT. Later pages in this chapter discuss cylinder measures, Minlos-type construction, ultraviolet cutoffs, fermionic Berezin integration, and Lorentzian oscillatory integrals.

## Research status

Finite-dimensional probability measures and Gaussian integration are completely standard. The research-level issues arise in the limits and in the structures suppressed by finite-dimensional notation: infinite-dimensional support, ultraviolet divergences, reflection positivity, gauge redundancy, fermionic variables, renormalization, and Lorentzian oscillations.

The main lesson for rigorous QFT is conservative but powerful. A cutoff path integral can be a measure; the continuum path integral must be constructed, not merely written.

## Exercises

### Exercise 1

Let $A$ be a positive-definite symmetric $N\times N$ matrix. Prove that the centered Gaussian with density proportional to $e^{-x^TAx/2}$ has covariance $A^{-1}$.

<details><summary><strong>Solution</strong></summary>

Introduce a source $J\in\mathbb R^N$ and complete the square:

$$
-\frac12 x^TAx+J\cdot x
=
-\frac12 (x-A^{-1}J)^T A (x-A^{-1}J)
+\frac12 J^T A^{-1}J.
$$

Therefore

$$
M(J)=
\left\langle e^{J\cdot X}\right\rangle
=
\exp\left(\frac12 J^T A^{-1}J\right).
$$

Differentiating twice gives

$$
\langle X_iX_j\rangle
=
\left.
\frac{\partial^2 M}{\partial J_i\partial J_j}
\right|_{J=0}
=(A^{-1})_{ij}.
$$

</details>

### Exercise 2

Use the source formula to compute $\langle X_iX_jX_kX_\ell\rangle$ for a centered Gaussian with covariance $C$.

<details><summary><strong>Solution</strong></summary>

The moment-generating function is

$$
M(J)=\exp\left(\frac12 J^TCJ\right).
$$

The fourth derivative at $J=0$ receives contributions only from products of two quadratic factors. Hence

$$
\langle X_iX_jX_kX_\ell\rangle
=
C_{ij}C_{k\ell}
+C_{ik}C_{j\ell}
+C_{i\ell}C_{jk}.
$$

This is the four-point case of Wick's theorem.

</details>

### Exercise 3

Explain why $Z=\int_{\mathbb R}e^{ix^2}\,dx$ is not the normalization of a probability measure on $\mathbb R$.

<details><summary><strong>Solution</strong></summary>

A probability measure must be positive and countably additive. The expression $e^{ix^2}dx$ is not positive, because $e^{ix^2}$ is a complex phase. Its total variation would be

$$
\int_{\mathbb R}|e^{ix^2}|\,dx
=\int_{\mathbb R}1\,dx
=\infty.
$$

The Fresnel integral can be assigned a value by oscillatory limiting procedures, such as adding a damping factor $e^{-\epsilon x^2}$ and taking $\epsilon\downarrow0$ in a controlled way. That is not the same as normalizing a probability measure.

</details>

## References

### Standard references

- Gerald B. Folland, *Real Analysis: Modern Techniques and Their Applications*, second edition, Wiley, 1999.
- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

### Gaussian and QFT references

- Leon Isserlis, "On a Formula for the Product-Moment Coefficient of Any Order of a Normal Frequency Distribution in Any Number of Variables," *Biometrika* **12** (1918), 134–139. DOI: [10.1093/biomet/12.1-2.134](https://doi.org/10.1093/biomet/12.1-2.134).
- G. C. Wick, "The Evaluation of the Collision Matrix," *Physical Review* **80** (1950), 268–272. DOI: [10.1103/PhysRev.80.268](https://doi.org/10.1103/PhysRev.80.268).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

## Version history

- **2026-06-30:** Initial version.
