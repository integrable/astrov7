---
title: "Euclidean Action as Density"
description: "Explains when an interacting Euclidean action defines a density relative to a Gaussian reference measure, and why this is safer than an infinite-dimensional Lebesgue measure."
sidebar:
  label: "Euclidean Action as Density"
  order: 5
level: Graduate
status: "Polished draft"
source: "Simon functional integration; Glimm–Jaffe constructive QFT; Guerra–Rosen–Simon P(φ)₂; Osterwalder–Schrader Euclidean QFT."
topics:
  - Euclidean action
  - interacting measures
  - Gaussian reference measures
  - Wick ordering
  - Schwinger functions
canonicalTopics:
  - euclidean-action
  - interacting-euclidean-measure
  - gaussian-reference-measure
  - wick-ordering
  - schwinger-functions
researchStatus:
  established:
    - "At finite cutoff, many Euclidean scalar path integrals can be defined as probability measures with densities relative to finite-dimensional or Gaussian reference measures."
  active:
    - "Removing the cutoff, proving regulator independence, and verifying Osterwalder–Schrader properties remain model-dependent constructive problems."
---

## Summary

A Euclidean action becomes mathematically meaningful when it is used to define a measure or a density. In finite dimensions, the basic formula is

$$
d\mu(x)=Z^{-1}e^{-S(x)}\,dx,
\qquad
Z=\int_{\mathbb R^N}e^{-S(x)}\,dx.
$$

In an infinite-dimensional field space, the symbol $dx$ has no analogue as translation-invariant Lebesgue measure. The safer continuum form is therefore not

$$
\mathcal D\phi\,e^{-S[\phi]},
$$

but a density relative to a reference measure:

$$
d\mu_{V}=Z_V^{-1}e^{-V(\Phi)}\,d\mu_C.
$$

Here $\mu_C$ is usually a Gaussian free-field measure with covariance $C$, and $V$ is the interaction. This is the measure-theoretic content of the informal split

$$
S_E[\phi]=\frac12\langle \phi,C^{-1}\phi\rangle+V[\phi].
$$

The caveat is that $V(\Phi)$ is often not defined without ultraviolet cutoff and renormalization. In two-dimensional $P(\phi)_2$ models, one can define finite-volume interacting measures by Wick-ordered polynomial densities relative to the massive Gaussian free field. In higher dimensions the same slogan remains useful, but the construction becomes more delicate and may require counterterms, multiscale estimates, stochastic PDE methods, or a different framework.

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), [Cylinder Measures](/rigorous-qft/path-integrals-as-measures/cylinder-measures/), and the [Minlos Theorem Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/). For the Euclidean-to-Lorentzian bridge, use [OS Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/).

## Core idea

The Gaussian part of a Euclidean action should usually be promoted to the measure, not treated as a formal factor multiplying a nonexistent flat measure. The interaction is then a density with respect to that Gaussian measure.

<figure class="doc-figure" style="--figure-width: 52rem;">

![An interacting Euclidean measure as a density relative to a Gaussian reference measure.](/figures/rigorous-qft/euclidean-action-density.svg)

<figcaption>

At finite cutoff or in favorable continuum settings, the interaction $V$ defines a density $e^{-V}/Z_V$ relative to a Gaussian reference measure $\mu_C$. Schwinger functions are expectations under the resulting measure.

</figcaption>
</figure>

This viewpoint changes the meaning of the action. The expression $\frac12\langle \phi,C^{-1}\phi\rangle$ is not a finite random variable under the free-field measure; it is the formal symbol that identifies the covariance of $\mu_C$. The well-defined object is the characteristic functional

$$
\int e^{i\Phi(f)}\,d\mu_C(\Phi)
=
\exp\!\left(-\frac12 C(f,f)\right).
$$

After the free measure exists, the interaction must be checked as a random variable or as a limit of random variables. This is where ultraviolet cutoffs, Wick ordering, counterterms, and constructive estimates enter.

## Setup and conventions

We work in Euclidean signature. Let $E$ be a real test-function space and $E'$ its distributional dual. A free scalar Euclidean field is represented by a centered Gaussian measure $\mu_C$ on $E'$ such that

$$
\mathbb E_{\mu_C}\,\Phi(f)\Phi(g)=C(f,g).
$$

For the massive scalar field on $\mathbb R^d$, the formal covariance is

$$
C_m=(-\Delta+m^2)^{-1},
$$

meaning

$$
C_m(f,g)=
\int_{\mathbb R^d}
\frac{d^dp}{(2\pi)^d}
\frac{\widetilde f(-p)\widetilde g(p)}{p^2+m^2}.
$$

An interacting finite-volume Euclidean measure is often written as

$$
d\mu_{\Lambda,V}(\Phi)
=
Z_{\Lambda,V}^{-1}e^{-V_\Lambda(\Phi)}\,d\mu_C(\Phi),
$$

where $\Lambda\subset\mathbb R^d$ is bounded and

$$
Z_{\Lambda,V}=
\int e^{-V_\Lambda(\Phi)}\,d\mu_C(\Phi).
$$

This formula is a definition only when $V_\Lambda$ is a measurable random variable and $0<Z_{\Lambda,V}<\infty$. In most QFT examples, $V_\Lambda$ must first be regularized.

## From a finite cutoff to a Gaussian reference measure

In finite dimensions, splitting the action is only algebra. Suppose

$$
S(x)=\frac12 x^T A x+V(x),
\qquad A>0.
$$

Let $\gamma_A$ be the centered Gaussian measure with covariance $A^{-1}$:

$$
d\gamma_A(x)=
\frac{(\det A)^{1/2}}{(2\pi)^{N/2}}
\exp\!\left(-\frac12 x^T A x\right)dx.
$$

Then

$$
Z^{-1}e^{-S(x)}dx
=
Z_V^{-1}e^{-V(x)}d\gamma_A(x),
$$

with

$$
Z_V=\int_{\mathbb R^N}e^{-V(x)}\,d\gamma_A(x).
$$

The infinite-dimensional formula is modeled on this identity. The Gaussian measure survives; the flat measure does not. Thus the expression $e^{-V}d\mu_C$ is not merely a change of notation. It is the mathematically meaningful replacement for the formal path-integral expression.

## Interactions as densities

The cleanest interacting Euclidean measure has the form

$$
d\mu_V=Z_V^{-1}e^{-V}\,d\mu_C.
$$

This is an absolutely continuous perturbation of the Gaussian measure. For bounded continuous $V$, the construction is immediate. For local QFT interactions, $V$ is rarely bounded and may not even be pointwise defined before regularization.

A scalar polynomial model suggests

$$
V_\Lambda(\Phi)
=
\int_\Lambda P(\Phi(x))\,d^dx.
$$

But $\Phi(x)$ is not a random variable for the continuum free field. It is only a distribution tested against smooth functions. A common regulated version is

$$
\Phi_\kappa(x)=\Phi(\rho_\kappa^x),
\qquad
\rho_\kappa^x(y)=\rho_\kappa(y-x),
$$

and

$$
V_{\Lambda,\kappa}(\Phi)
=
\int_\Lambda P_\kappa(\Phi_\kappa(x))\,d^dx.
$$

The subscript on $P_\kappa$ is deliberate. In renormalized models, the interaction is not obtained by simply substituting a smoothed field into the original polynomial. It may need Wick ordering, mass counterterms, vacuum-energy counterterms, coupling renormalization, or field-strength renormalization.

## Wick ordering as a density repair

For the Gaussian field, the variance of the regularized point field is

$$
C_\kappa(x,x)=\mathbb E\,\Phi_\kappa(x)^2.
$$

This quantity often diverges as the ultraviolet cutoff is removed. Wick ordering subtracts the self-contractions with respect to the reference Gaussian measure. For example,

$$
:\!\Phi_\kappa(x)^2\!:
=
\Phi_\kappa(x)^2-C_\kappa(x,x),
$$

and

$$
:\!\Phi_\kappa(x)^4\!:
=
\Phi_\kappa(x)^4
-6C_\kappa(x,x)\Phi_\kappa(x)^2
+3C_\kappa(x,x)^2.
$$

In two-dimensional $P(\phi)_2$ theory, Wick-ordered polynomial interactions give a robust route to finite-volume measures:

$$
d\mu_{\Lambda,\kappa}
=Z_{\Lambda,\kappa}^{-1}
\exp\!\left(
-\int_\Lambda :\!P(\Phi_\kappa(x))\!:\,d^2x
\right)d\mu_C.
$$

The construction theorem is not just this displayed formula. One must prove that the measures converge as $\kappa\to\infty$ and have the desired Euclidean properties.

## Schwinger functions from the measure

Once $\mu_V$ is constructed, Euclidean correlation functions are moments:

$$
S_n(f_1,\ldots,f_n)
=
\int_{E'}\Phi(f_1)\cdots\Phi(f_n)\,d\mu_V(\Phi).
$$

For local notation one writes formally

$$
S_n(x_1,\ldots,x_n)
=
\int \Phi(x_1)\cdots\Phi(x_n)\,d\mu_V(\Phi),
$$

but the distributional version is the safe definition. The generating functional is

$$
Z_V(J)=\int e^{\Phi(J)}\,d\mu_V(\Phi),
$$

whenever this expression exists. Connected Schwinger functions are obtained from $\log Z_V(J)$ by differentiation at $J=0$.

This is the rigorous interpretation of the physics phrase "the Euclidean path integral generates correlation functions." It is true only after a measure, or a suitable substitute, has been constructed.

## Checks

A proposed density $e^{-V}d\mu_C/Z_V$ should pass several elementary checks before it is advertised as a QFT construction.

First, it must be a probability measure:

$$
0<Z_V<\infty,
\qquad
\int d\mu_V=1.
$$

Second, its moments should exist at least as distributions on test functions. Third, its Schwinger functions should have the symmetries expected from the Euclidean theory. Fourth, for a relativistic QFT interpretation, the Schwinger functions must satisfy Osterwalder–Schrader conditions such as reflection positivity. Fifth, the construction should be stable under removing cutoffs and enlarging the volume, if a continuum or infinite-volume theory is being claimed.

These checks are independent. A measure can be normalized but fail reflection positivity. A family of cutoff measures can have finite moments but no useful limit. A perturbation can preserve Euclidean invariance but fail to define local relativistic observables after reconstruction.

## Common pitfalls

**Treating $\mathcal D\phi$ as Lebesgue measure.** There is no infinite-dimensional translation-invariant Lebesgue probability measure on the spaces used for fields. The meaningful object is usually a Gaussian measure or a limit of cutoff measures.

**Putting the quadratic action in the density twice.** Once $\mu_C$ has been chosen, the quadratic free part is already in the reference measure. The interaction density is $e^{-V}$, not $e^{-\frac12\langle\phi,C^{-1}\phi\rangle-V}$ relative to $\mu_C$.

**Ignoring ultraviolet singularities.** The expression $\int P(\Phi(x))\,dx$ is not automatically defined. Fields are distributions, and products at the same point need renormalization.

**Assuming absolute continuity survives every limit.** Finite-cutoff measures may be absolutely continuous with respect to a free Gaussian reference, while the limiting measures can be singular or live naturally in a different topology.

**Confusing a Euclidean probability measure with a Lorentzian amplitude.** The density $e^{-V}d\mu_C$ is a Euclidean object. Lorentzian time evolution requires reconstruction, analytic continuation, or another real-time framework.

## Relations to other pages

- [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/) explains the regulators that make $V_{\Lambda,\kappa}$ an honest random variable before a limit is attempted.
- [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) places this density viewpoint inside the constructive program.
- [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) gives the classic two-dimensional setting where Wick-ordered polynomial densities are constructed rigorously.
- [Phi-Four Two](/rigorous-qft/constructive-qft/phi-four-two/) and [Phi-Four Three](/rigorous-qft/constructive-qft/phi-four-three/) explain how the difficulty grows with dimension.
- [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) explains the positivity condition needed to turn Euclidean moments into a Lorentzian Hilbert space.
- [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) explains why the safe variables are $\Phi(f)$ rather than point values $\Phi(x)$.

## Research status

The density viewpoint is settled for finite-dimensional measures and for many Gaussian-based Euclidean constructions. In classic low-dimensional constructive models, it is part of the actual proof strategy: define cutoff densities, renormalize them, prove convergence, and verify axioms.

The hard part is not the formal expression $e^{-V}d\mu_C$. The hard part is proving that $V$ exists as a random variable or limit, that $Z_V$ stays meaningful, that Schwinger functions converge, and that the limiting theory satisfies locality, covariance, reflection positivity, and clustering. Four-dimensional interacting continuum gauge theories remain far beyond this simple density formula as mathematical constructions.

## Exercises

### Exercise 1: Move the Gaussian into the measure

Let $A$ be a positive-definite $N\times N$ matrix and let $S(x)=\frac12x^TAx+V(x)$. Show that the probability measure $Z^{-1}e^{-S(x)}dx$ can be written as $Z_V^{-1}e^{-V(x)}d\gamma_A(x)$, where $\gamma_A$ is the centered Gaussian with covariance $A^{-1}$.

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
d\gamma_A(x)=
\frac{(\det A)^{1/2}}{(2\pi)^{N/2}}
e^{-x^TAx/2}\,dx.
$$

Therefore

$$
e^{-S(x)}dx
=\frac{(2\pi)^{N/2}}{(\det A)^{1/2}}
e^{-V(x)}d\gamma_A(x).
$$

The constant is absorbed into the normalization. Thus

$$
Z^{-1}e^{-S(x)}dx
=Z_V^{-1}e^{-V(x)}d\gamma_A(x),
$$

where $Z_V=\int e^{-V}d\gamma_A$.

</details>

### Exercise 2: Wick-order the fourth power

Let $X$ be a centered Gaussian random variable with variance $\sigma^2$. Verify that

$$
:X^4:=X^4-6\sigma^2X^2+3\sigma^4
$$

has zero expectation.

<details>
<summary><strong>Solution</strong></summary>

For a centered Gaussian variable,

$$
\mathbb E X^2=\sigma^2,
\qquad
\mathbb E X^4=3\sigma^4.
$$

Therefore

$$
\mathbb E(:X^4:)
=3\sigma^4-6\sigma^2\sigma^2+3\sigma^4=0.
$$

The same subtraction pattern removes Gaussian self-contractions in regularized field powers.

</details>

### Exercise 3: Reflection positivity is not normalization

Explain why $0<Z_V<\infty$ does not imply reflection positivity.

<details>
<summary><strong>Solution</strong></summary>

Normalization only says that $e^{-V}d\mu_C/Z_V$ is a probability measure. Reflection positivity is an additional inequality involving Euclidean time reflection and observables supported in positive Euclidean time. It constrains the covariance, interaction, and time-reflection structure. A normalized measure can fail this inequality, so it need not reconstruct a Lorentzian Hilbert space with positive norm.

</details>

## References

### Standard first pass

- Barry Simon, *Functional Integration and Quantum Physics*, second edition, AMS Chelsea Publishing, 2005. AMS page: [bookstore.ams.org/view?ProductCode=CHEL%2F351.H](https://bookstore.ams.org/view?ProductCode=CHEL%2F351.H).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The P(φ)₂ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.

### Deeper references

- Francesco Guerra, Lon Rosen, and Barry Simon, "The P(φ)₂ Euclidean Quantum Field Theory as Classical Statistical Mechanics. Part I," *Annals of Mathematics* **101** (1975), 111–189. DOI: [10.2307/1970988](https://doi.org/10.2307/1970988).
- Francesco Guerra, Lon Rosen, and Barry Simon, "The P(φ)₂ Euclidean Quantum Field Theory as Classical Statistical Mechanics. Part II," *Annals of Mathematics* **101** (1975), 191–259. DOI: [10.2307/1970989](https://doi.org/10.2307/1970989).
- Edward Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](https://doi.org/10.1016/0022-1236(73)90025-6).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- Jürg Fröhlich, "Schwinger Functions and Their Generating Functionals. I," *Helvetica Physica Acta* **47** (1974), 265–306.

## Version history

- **2026-06-30:** Initial page on Euclidean actions as densities relative to Gaussian reference measures.
