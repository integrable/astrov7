---
title: "Sine-Gordon Model: Rigorous Construction"
description: "A status-aware guide to the rigorous Euclidean construction of the two-dimensional sine-Gordon model."
sidebar:
  label: "Sine-Gordon Construction"
  order: 7
level: Advanced
status: "Polished draft"
source: "Fröhlich–Seiler sine-Gordon; Dimock–Hurd construction; Coleman sine-Gordon–Thirring; constructive RG."
topics:
  - constructive QFT
  - sine-Gordon model
  - vertex operators
  - Coulomb gas
  - two-dimensional QFT
canonicalTopics:
  - constructive-quantum-field-theory
  - sine-gordon-model
  - euclidean-quantum-field-theory
  - vertex-operators
researchStatus:
  established:
    - "The two-dimensional sine-Gordon model has rigorous Euclidean constructive treatments in subcritical parameter regimes, with precise ultraviolet renormalization of vertex operators."
  active:
    - "The relation among constructive, perturbative algebraic, stochastic, integrable, and operator-algebraic constructions is subtle and remains an active bridge-building topic."
---

## Summary

The sine-Gordon model is the two-dimensional scalar field theory whose interaction is a cosine rather than a polynomial. In Euclidean notation one writes, formally,

$$
S_E(\phi)
=
\int_{\mathbb R^2}
\left(
\frac12 |\nabla \phi|^2
-2z\cos(\beta\phi)
\right)d^2x,
$$

or, with a massive Gaussian reference field and a finite region $\Lambda$,

$$
d\mu_{\mathrm{SG},\Lambda}(\phi)
=
\frac{1}{Z_\Lambda}
\exp\left(
2z\int_\Lambda :\!\cos(\beta\phi(x))\!:\,d^2x
\right)d\mu_C(\phi).
$$

This formula is not a literal density with respect to an infinite-dimensional flat measure. The free field is a Gaussian random distribution, so the expression $\cos(\beta\phi(x))$ has to be defined through Wick-ordered vertex operators. The basic building block is

$$
V_\alpha(x)
=:\!e^{i\alpha\phi(x)}\!:,
\qquad
:\!\cos(\beta\phi)\!:
=\frac12\left(V_\beta+V_{-\beta}\right).
$$

With the covariance normalization used on this page, $V_\beta$ has scaling dimension $\beta^2/(4\pi)$. The cosine perturbation is therefore relevant for

$$
\beta^2<8\pi,
$$

marginal at $\beta^2=8\pi$, and irrelevant above that threshold. This is the same threshold that appears in the Kosterlitz–Thouless picture and in the Coulomb-gas representation, but normalizations vary across the literature.

The page explains what is rigorous in the constructive sine-Gordon story: how the interaction is defined, why charge-neutral Coulomb-gas expansions appear, what the main ultraviolet thresholds mean, and what is not automatically proved by writing the integrable sine-Gordon Lagrangian.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), and [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/). It also helps to know [Wick Rotation: Rigorous View](/rigorous-qft/osterwalder-schrader-euclidean-qft/wick-rotation-rigorous-view/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/).

## Core idea

The sine-Gordon model is a useful constructive example precisely because it is not a Wick polynomial. The interaction is periodic, and physics readers often think of it as a harmless bounded function. But the Euclidean free field in two dimensions is not a pointwise function. It is a random distribution whose variance at a mollified point diverges logarithmically as the mollifier is removed.

The correct local objects are not $e^{i\alpha\phi(x)}$ directly, but renormalized vertex operators. Once vertex operators are used, expanding the cosine creates a gas of positive and negative charges. Small clusters of opposite charges are the ultraviolet problem, and large neutral arrangements of charges are the infrared problem. Constructive sine-Gordon is the theorem-level control of this gas, not merely the formal observation that a cosine can be expanded in exponentials.

The model sits at a meeting point of four subjects: constructive Euclidean QFT, Coulomb-gas methods, Kosterlitz–Thouless RG, and the sine-Gordon–massive-Thirring correspondence. These viewpoints are compatible in important regimes, but they are not identical mathematical constructions.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Sine-Gordon construction as a chain from Gaussian fields to Coulomb-gas charges and Schwinger functions.](/figures/rigorous-qft/sine-gordon-coulomb-gas.svg)

<figcaption>

A constructive sine-Gordon proof starts from a Gaussian random distribution, defines Wick-ordered vertex operators, expands the cosine into charge configurations, controls the ultraviolet and infrared limits, and then verifies Euclidean QFT data.

</figcaption>
</figure>

## Setup and conventions

We work in two Euclidean dimensions. Let $\mu_C$ be a Gaussian free-field measure with covariance

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0,
$$

or with a finite-volume and infrared-regularized massless covariance when that is more appropriate. For small separation,

$$
C(x-y)
=
-\frac{1}{2\pi}\log |x-y| + O(1).
$$

Let $\phi_\epsilon=\rho_\epsilon\ast\phi$ be a mollified field. The Wick-ordered exponential is normalized by

$$
:\!e^{i\alpha\phi_\epsilon(x)}\!:
=
\exp\left(
 i\alpha\phi_\epsilon(x)
 +\frac{\alpha^2}{2}C_\epsilon(0)
\right),
$$

where $C_\epsilon(0)=\mathbb E[\phi_\epsilon(x)^2]$. The plus sign in the exponential compensates for

$$
\mathbb E\left[e^{i\alpha\phi_\epsilon(x)}\right]
=
\exp\left(-\frac{\alpha^2}{2}C_\epsilon(0)\right).
$$

The renormalized vertex operator $V_\alpha$ is the distributional limit of these Wick-ordered objects, tested against smooth functions. The sine-Gordon interaction in a bounded region is then interpreted as

$$
\int_\Lambda :\!\cos(\beta\phi(x))\!:\,d^2x
=
\frac12\int_\Lambda
\left(V_\beta(x)+V_{-\beta}(x)\right)d^2x.
$$

The symbol $z$ is the activity or cosine coupling. The parameter $\beta$ controls the scaling dimension of the perturbation. Some sources absorb factors of $4\pi$ into the free-field action; always translate thresholds by first fixing the covariance normalization.

## Vertex operators and the first threshold

The Gaussian expectation of Wick exponentials is

$$
\mathbb E\left[
\prod_{j=1}^n V_{\alpha_j}(x_j)
\right]
=
\exp\left(
-\sum_{1\leq i<j\leq n}\alpha_i\alpha_j C(x_i-x_j)
\right),
$$

with an additional neutrality condition in the massless theory. At short distance, this gives the power law

$$
\mathbb E\left[V_\alpha(x)V_{-\alpha}(y)\right]
\sim
|x-y|^{-\alpha^2/(2\pi)}.
$$

Thus the product of opposite charges is locally integrable in two dimensions when

$$
\alpha^2<4\pi.
$$

This is the first threshold. Below it, many estimates are close to ordinary power-counting estimates for integrable singularities. Above it, but still below $8\pi$, the cosine perturbation remains relevant in the RG sense, but simple pairwise integrability is not enough. One needs a more refined multiscale analysis of neutral clusters and dipoles.

The constructive literature therefore often separates regimes:

| Regime | Meaning in this normalization | Typical difficulty |
|---|---|---|
| $\beta^2<4\pi$ | Direct vertex-operator singularities are locally integrable. | Easiest finite-volume construction regime. |
| $4\pi\leq\beta^2<8\pi$ | Perturbation is still relevant but short-distance clusters require renormalization-group control. | Full subcritical constructive regime. |
| $\beta^2=8\pi$ | Marginal Kosterlitz–Thouless threshold. | Borderline behavior. |
| $\beta^2>8\pi$ | Cosine perturbation is irrelevant at the Gaussian fixed point. | Different infrared/ultraviolet questions. |

The exact numerical boundary depends on conventions, but the hierarchy of integrability threshold, subcritical regime, and marginal threshold is robust.

## Coulomb-gas representation

Expand the interaction in a finite volume:

$$
\begin{aligned}
&\exp\left(
2z\int_\Lambda :\!\cos(\beta\phi(x))\!:\,d^2x
\right) \\
&\quad=
\sum_{n\geq0}\frac{z^n}{n!}
\sum_{\sigma_j=\pm1}
\int_{\Lambda^n}
\prod_{j=1}^n V_{\sigma_j\beta}(x_j)d^2x_j .
\end{aligned}
$$

Taking the Gaussian expectation turns this into a gas of charges $\sigma_j=\pm1$ with pair interaction controlled by $C(x_i-x_j)$:

$$
\mathbb E\left[
\prod_{j=1}^n V_{\sigma_j\beta}(x_j)
\right]
=
\exp\left(
-\beta^2\sum_{i<j}\sigma_i\sigma_j C(x_i-x_j)
\right).
$$

For the massless theory, charge neutrality

$$
\sum_{j=1}^n\sigma_j=0
$$

is forced by the zero mode. This is why the sine-Gordon model is inseparable from the two-dimensional neutral Coulomb gas. Opposite charges attract, like charges repel, and the ultraviolet problem is the possibility that attractive dipoles collapse at arbitrarily short distances.

The constructive problem is to prove that after the correct Wick renormalization, and sometimes additional infrared choices, the correlation functions have limits as the ultraviolet cutoff is removed. In favorable settings, the resulting Schwinger functions satisfy the Osterwalder–Schrader requirements needed for Hilbert-space reconstruction.

## What the construction proves

A typical constructive theorem is not the sentence "the sine-Gordon Lagrangian exists." It has a more precise shape.

One fixes a finite volume, a covariance, an ultraviolet cutoff, a coupling regime, and test observables. One defines cutoff Schwinger functions by a finite-dimensional or Gaussian-relative expression. Then one proves estimates uniform in the ultraviolet cutoff, takes the cutoff to zero, and identifies the limiting Schwinger functions. Depending on the theorem, one also proves Euclidean invariance, reflection positivity, clustering, analyticity in the activity, or compatibility with field equations.

Classical constructive work treats the sine-Gordon measure and its Coulomb-gas expansion in subcritical regimes. Dimock–Hurd give a rigorous construction of the two-dimensional sine-Gordon model in finite volume in the full subcritical range; their paper writes the threshold as $\beta<8\pi$, while this page uses the common physics convention in which the same relevance threshold is written $\beta^2<8\pi$. Other treatments isolate the easier first-threshold regime or analyze the Kosterlitz–Thouless flow. Modern stochastic-PDE methods give complementary constructions of sine-Gordon measures and dynamics in more restricted but conceptually powerful settings.

This page deliberately does not claim that every famous property of the integrable sine-Gordon model follows from a single constructive theorem. Exact factorized scattering, soliton form factors, the sine-Gordon–Thirring correspondence, and local-net constructions are related but separate theorem packages.

## Checks

A few checks prevent most wrong readings of the model.

First, in the free-field normalization above, the two-point function of vertex operators has the expected scaling law:

$$
\mathbb E[V_\alpha(x)V_{-\alpha}(y)]
\sim |x-y|^{-2\Delta_\alpha},
\qquad
\Delta_\alpha=\frac{\alpha^2}{4\pi}.
$$

Second, the coupling $z$ has engineering dimension

$$
[z]=2-\frac{\beta^2}{4\pi}.
$$

This gives the relevance threshold $\beta^2<8\pi$.

Third, the cosine expansion contains both signs of charge. If a proposed derivation keeps only $e^{i\beta\phi}$, it has broken the real interaction and lost the neutral Coulomb-gas structure.

## Common pitfalls

**Treating $\cos(\beta\phi(x))$ as a bounded random variable.** The classical cosine is bounded, but $\phi(x)$ is not defined pointwise. The rigorous interaction is built from Wick-ordered vertex operators.

**Forgetting the normalization of $\beta$.** The number $8\pi$ is convention-dependent. It is meaningful only after the free covariance or kinetic term has been fixed.

**Confusing the first threshold with the full subcritical threshold.** Direct dipole integrability naturally leads to $\beta^2<4\pi$, while the full subcritical RG regime extends to $\beta^2<8\pi$. The second statement is harder.

**Calling the Coulomb-gas expansion merely perturbative.** The expansion begins as a power series in the activity, but constructive estimates can use it to define nonperturbative Euclidean objects in a domain of parameters.

**Identifying integrability with construction.** Exact S-matrix and form-factor formulas are powerful, but a rigorous construction must specify Hilbert spaces, local fields or algebras, domains, positivity, and limiting procedures.

**Ignoring infrared choices.** The massless two-dimensional scalar field has a zero-mode problem. Massive covariance, finite volume, charge neutrality, or spatial cutoffs are not cosmetic; they are part of the definition.

## Relations to other pages

This page follows [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/) and [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) as the first non-polynomial constructive model in the chapter. It relies on [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) for the covariance and on [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) for the idea that interactions are defined relative to a Gaussian field.

The [Euclidean versus Lorentzian QFT](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-versus-lorentzian-qft/) page explains why Euclidean construction is not automatically a Lorentzian theorem. Later pages on rigorous renormalization and integrable models should return to the Kosterlitz–Thouless flow, Coulomb-gas methods, and the sine-Gordon–Thirring relation.

## Research status

The sine-Gordon model is one of the best-tested meeting points between exact physics and rigorous analysis. Its Euclidean constructive treatment is established in important subcritical settings, including finite-volume ultraviolet construction and Coulomb-gas/RG control. There are also rigorous results on soliton sectors, perturbative algebraic QFT constructions, stochastic quantization, and operator-algebraic local nets.

The active part is not whether the sine-Gordon model is a serious mathematical object. It is how the different mathematical objects compare: Euclidean measures, Lorentzian perturbative constructions, integrable S-matrix data, soliton sectors, thermal states, local von Neumann nets, and stochastic dynamics are related but not automatically identical.

## Exercises

### Exercise 1: Scaling dimension of the vertex operator

Assume

$$
C(x-y)
=-\frac{1}{2\pi}\log |x-y|+O(1)
$$

near $x=y$. Show that

$$
\mathbb E[V_\alpha(x)V_{-\alpha}(y)]
\sim |x-y|^{-\alpha^2/(2\pi)}.
$$

What is the scaling dimension $\Delta_\alpha$?

<details>
<summary><strong>Solution</strong></summary>

The Wick-exponential rule gives

$$
\mathbb E[V_\alpha(x)V_{-\alpha}(y)]
=
\exp(\alpha^2 C(x-y)).
$$

Using the short-distance form of $C$,

$$
\exp(\alpha^2 C(x-y))
\sim
\exp\left(-\frac{\alpha^2}{2\pi}\log|x-y|\right)
=|x-y|^{-\alpha^2/(2\pi)}.
$$

In two-dimensional CFT notation a scalar two-point function behaves as $|x-y|^{-2\Delta}$, so

$$
\Delta_\alpha=\frac{\alpha^2}{4\pi}.
$$

</details>

### Exercise 2: Relevance of the cosine perturbation

Using the result of Exercise 1, compute the engineering dimension of the activity $z$ in

$$
z\int d^2x\, :\!\cos(\beta\phi)\!:.
$$

When is this perturbation relevant?

<details>
<summary><strong>Solution</strong></summary>

The operator $:\!\cos(\beta\phi)\!:$ has the same scaling dimension as $V_\beta$:

$$
\Delta_\beta=\frac{\beta^2}{4\pi}.
$$

Since $d^2x$ has dimension $-2$, the coupling has dimension

$$
[z]=2-\Delta_\beta
=2-\frac{\beta^2}{4\pi}.
$$

It is relevant when $[z]>0$, hence when

$$
\beta^2<8\pi.
$$

</details>

### Exercise 3: Neutrality in the massless theory

Explain why a massless free scalar with an unconstrained constant zero mode forces

$$
\sum_{j=1}^n \alpha_j=0
$$

for a vertex-operator correlation function to be nonzero.

<details>
<summary><strong>Solution</strong></summary>

Split the field formally into a constant mode $c$ and a fluctuation $\phi'$. Then

$$
\prod_{j=1}^n e^{i\alpha_j\phi(x_j)}
=
\exp\left(i c\sum_{j=1}^n\alpha_j\right)
\prod_{j=1}^n e^{i\alpha_j\phi'(x_j)}.
$$

Integrating over the constant mode gives zero unless the phase is independent of $c$. Thus the total charge must vanish:

$$
\sum_{j=1}^n\alpha_j=0.
$$

This is the origin of charge neutrality in the Coulomb-gas representation.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).

### Constructive and exact-model references

- Jürg Fröhlich, "New Super-Selection Sectors ('Soliton-States') in Two Dimensional Bose Quantum Field Models," *Communications in Mathematical Physics* **47** (1976), 269–310. DOI: [10.1007/BF01609844](https://doi.org/10.1007/BF01609844).
- Sidney Coleman, "Quantum Sine-Gordon Equation as the Massive Thirring Model," *Physical Review D* **11** (1975), 2088–2097. DOI: [10.1103/PhysRevD.11.2088](https://doi.org/10.1103/PhysRevD.11.2088).
- J. Dimock and T. R. Hurd, "Construction of the Two-Dimensional Sine-Gordon Model for $\beta<8\pi$," *Communications in Mathematical Physics* **156** (1993), 547–580. DOI: [10.1007/BF02096863](https://doi.org/10.1007/BF02096863). [Project Euclid](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-156/issue-3/Construction-of-the-two-dimensional-sine-Gordon-model-for-betalt8pi/cmp/1104253717.full).
- J. Dimock and T. R. Hurd, "Sine-Gordon Revisited," *Annales Henri Poincaré* **1** (2000), 499–541. arXiv: [math-ph/9907017](https://arxiv.org/abs/math-ph/9907017).
- Daniela Bahns, Kasia Rejzner, and Jochen Zahn, "The Quantum Sine-Gordon Model in Perturbative AQFT," *Communications in Mathematical Physics* **357** (2018), 421–446. DOI: [10.1007/s00220-017-2944-4](https://doi.org/10.1007/s00220-017-2944-4). arXiv: [1609.08530](https://arxiv.org/abs/1609.08530).
- Dorothea Bahns, Klaus Fredenhagen, and Kasia Rejzner, "Local Nets of von Neumann Algebras in the Sine–Gordon Model," *Communications in Mathematical Physics* **383** (2021), 1–33. DOI: [10.1007/s00220-021-03961-y](https://doi.org/10.1007/s00220-021-03961-y). arXiv: [1712.02844](https://arxiv.org/abs/1712.02844).

### Modern stochastic references

- Ajay Chandra, Martin Hairer, and Hao Shen, "The Dynamical Sine-Gordon Model in the Full Subcritical Regime," arXiv: [1808.02594](https://arxiv.org/abs/1808.02594).
- Massimiliano Gubinelli, Martin Hairer, Tadahiro Oh, and Younes Zine, "A Simple Construction of the Sine-Gordon Model via Stochastic Quantization," *Journal of the London Mathematical Society* **112** (2025), e70214. DOI: [10.1112/jlms.70214](https://doi.org/10.1112/jlms.70214). arXiv: [2412.16404](https://arxiv.org/abs/2412.16404).

## Version history

- **2026-06-29:** Initial page created.
