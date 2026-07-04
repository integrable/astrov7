---
title: "Local Covariant Time-Ordered Products"
description: "Explains how time-ordered products in perturbative algebraic QFT are made local and covariant on curved spacetimes."
sidebar:
  label: "Local Covariant T-Products"
  order: 7
level: Advanced
status: "Polished draft"
source: "Hollands–Wald local covariance; Brunetti–Fredenhagen curved-spacetime pAQFT; Rejzner pAQFT"
topics:
  - local covariance
  - time-ordered products
  - curved spacetime QFT
  - perturbative algebraic QFT
  - renormalization
canonicalTopics:
  - local-covariant-time-ordered-products
  - perturbative-algebraic-qft
  - locally-covariant-qft
  - renormalization
researchStatus:
  established:
    - "For scalar fields on globally hyperbolic curved spacetimes, local covariant Wick powers and time-ordered products can be constructed perturbatively with finite local renormalization freedom."
  active:
    - "Gauge theories, anomalies, stress-tensor identities, and nonperturbative existence require additional structure beyond the scalar local-covariant construction."
---

## Summary

Local covariant time-ordered products are the curved-spacetime version of renormalized chronological products. They are families of maps

$$
T_n^M:
\mathcal F_{\mathrm{loc}}(M)^{\otimes n}
\longrightarrow \mathcal A(M),
$$

defined for each globally hyperbolic spacetime $M$, such that the construction is natural under spacetime embeddings. If $\psi:M\to N$ is an admissible embedding, local covariance requires

$$
\alpha_\psi\!
\left(T_n^M(F_1,\ldots,F_n)\right)
=
T_n^N(\psi_*F_1,\ldots,\psi_*F_n).
$$

This condition is not decoration. It is a renormalization condition. Without it, curved-spacetime time-ordered products can depend on arbitrary coordinate choices or arbitrary functions on spacetime. With it, the remaining freedom is local and geometric: constants, masses, couplings, curvature tensors, and their covariant derivatives, combined with the correct dimension and field content.

The main lesson is that renormalization on curved spacetime is not “flat-space renormalization plus gravity words.” Curvature changes the list of allowed local counterterms, and local covariance tells us exactly what kind of geometric dependence is legitimate.

## Prerequisites

Read [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/), [Causal Factorization](/rigorous-qft/perturbative-algebraic-qft/causal-factorization/), and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). You should also know [QFT as Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) and the [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/).

## Core idea

On Minkowski space, Poincaré invariance is often used to restrict renormalization. A two-point counterterm cannot depend on a preferred origin or a preferred vector, because that would break translation or Lorentz invariance. On a generic curved spacetime there may be no nontrivial isometries, no preferred vacuum, and no Fourier transform. The replacement principle is **local covariance**.

A construction is local and covariant when it is made from the local spacetime geometry and behaves naturally under embeddings. It may depend on $g$, $m^2$, $\xi$, curvature tensors, orientations, spin structures when present, and the causal structure. It may not depend on a coordinate chart, an arbitrary global time function, a preferred state, or an unexplained function inserted by hand.

For time-ordered products this means that the ultraviolet extension problem must be solved in a way compatible with geometry. The singularity near the total diagonal is local, so the allowed ambiguity is also local. In curved spacetime, “local” means built from fields and curvature at the same point.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Naturality square for local covariant time-ordered products](/figures/rigorous-qft/local-covariant-time-ordered-products.svg)

<figcaption>

A local covariant time-ordered product is a natural family of maps. Pushing local functionals forward along a spacetime embedding and then time-ordering gives the same result as time-ordering first and then embedding the observable algebra.

</figcaption>
</figure>

## Setup and conventions

Let $\mathbf{Loc}$ denote a category of oriented, time-oriented globally hyperbolic spacetimes. A locally covariant theory is a covariant functor

$$
\mathcal A:\mathbf{Loc}\longrightarrow \mathbf{Alg},
$$

where $\mathcal A(M)$ is the algebra of observables on $M$ and an embedding $\psi:M\to N$ induces an algebra morphism

$$
\alpha_\psi:\mathcal A(M)\longrightarrow \mathcal A(N).
$$

Let $\mathcal F_{\mathrm{loc}}(M)$ be the space of compactly supported local functionals on $M$. A typical element has the form

$$
F(\phi)
=
\int_M f(x)
P(\phi,\nabla\phi,\ldots,\nabla^k\phi;g)(x)
\,d\mu_g(x),
$$

where $P$ is polynomial in the field and finitely many covariant derivatives, with coefficients constructed locally from the background geometry and parameters.

A family of local covariant time-ordered products is a sequence of multilinear maps

$$
T_n^M:
\mathcal F_{\mathrm{loc}}(M)^{\otimes n}
\to
\mathcal A(M),
\qquad n\ge 0,
$$

satisfying the usual perturbative conditions: initial condition, graded symmetry, causal factorization, microlocal spectrum bounds, scaling control, and compatibility with local covariance. Different authors package these axioms differently. The important point for this page is that the maps are indexed by spacetimes and must commute with admissible embeddings.

## Local covariance as a naturality condition

For an embedding $\psi:M\to N$, a compactly supported local functional $F$ on $M$ has a pushforward $\psi_*F$ on $N$. Informally, it is the same local expression, now regarded as supported in the embedded region $\psi(M)\subset N$.

The covariance condition is

$$
\alpha_\psi
\left(T_n^M(F_1,\ldots,F_n)\right)
=
T_n^N(\psi_*F_1,\ldots,\psi_*F_n).
$$

For distribution-valued fields, the same idea says that if $\Phi_M(f)$ is a locally covariant field, then

$$
\alpha_\psi\bigl(\Phi_M(f)\bigr)
=
\Phi_N(\psi_*f).
$$

Time-ordered products are a higher multilinear version of this naturality condition. They must not secretly use a construction available only on one spacetime.

:::note[Why this matters]
In flat spacetime, translation invariance prevents a renormalized Wick square from being shifted by an arbitrary function $c(x)$. In curved spacetime there is usually no translation group to enforce this. Local covariance replaces that missing symmetry and rules out arbitrary $c(x)$ unless it is a natural scalar built locally from the geometry and parameters.
:::

## The curved-spacetime Wick square as the first example

The simplest example is the Wick square of a scalar field. In flat space one expects the ambiguity

$$
:\!\phi^2\!:\ \longmapsto
:\!\phi^2\!:+c\,m^2\mathbf 1,
$$

with a constant $c$ in four dimensions. On a curved spacetime, local covariance allows one additional term of the same engineering dimension:

$$
:\!\phi^2\!:_M
\longmapsto
:\!\phi^2\!:_M
+
(c_1m^2+c_2R)\mathbf 1.
$$

Here $R$ is the scalar curvature. The term $R\mathbf 1$ is not an arbitrary gravitational decoration; it is allowed because it is a locally and covariantly defined scalar of the correct dimension.

For the stress tensor and higher Wick powers, the ambiguity grows. Curvature terms such as $R^2$, $R_{ab}R^{ab}$, $R_{abcd}R^{abcd}$, $\Box R$, and covariant derivatives can appear when dimension, tensor type, and conservation conditions allow them. Local covariance determines the form of the list; additional physical or algebraic normalization conditions may reduce it.

## Time-ordered products and curvature counterterms

For an interaction such as

$$
V(\phi)
=
\int_M f(x)\frac{\lambda}{4!}\phi(x)^4\,d\mu_g(x),
$$

the time-ordered exponential is

$$
\mathcal S_M(V)
=
\exp_T\left(\frac{i}{\hbar}V\right)
=
\sum_{n=0}^\infty
\frac{i^n}{\hbar^n n!}
T_n^M(V,\ldots,V).
$$

The products $T_n^M$ are first defined away from coincident points by causal factorization and Wick expansion. Near the diagonals, one extends distributions. In curved spacetime, the extension may introduce local curvature terms. For scalar $\phi^4$ theory in four dimensions, the renormalized action can require the familiar local terms

$$
\int_M
\left(
\frac12 Z(\nabla\phi)^2
+
\frac12 Z_m m^2\phi^2
+
\frac12 Z_\xi R\phi^2
+
Z_\lambda\frac{\lambda}{4!}\phi^4
\right)d\mu_g
$$

together with purely geometric terms such as

$$
\int_M
\left(
Z_\Lambda
+Z_G R
+Z_1R^2
+Z_2R_{ab}R^{ab}
+Z_3R_{abcd}R^{abcd}
\right)d\mu_g,
$$

up to identities and total derivatives. The exact basis is convention-dependent, but the principle is not: allowed counterterms are local covariant scalar densities of the correct dimension and symmetry.

## The Hollands–Wald existence and uniqueness picture

For the free scalar field on globally hyperbolic curved spacetimes, Hollands and Wald gave a precise axiomatic treatment of Wick powers and time-ordered products as local covariant fields. The headline result, in the scalar case, is:

**Theorem schema.** Under the standard locality, covariance, microlocal spectrum, scaling, smoothness, analytic-dependence, symmetry, causal factorization, and initial-product requirements, local covariant Wick powers and time-ordered products exist. They are unique up to finite local covariant renormalization ambiguities.

This is a theorem schema rather than a one-line theorem because the exact hypotheses are technical. The technical hypotheses matter: scaling degree controls ultraviolet singularity, microlocal conditions control products of distributions, and local covariance prevents arbitrary spacetime-dependent subtractions.

The theorem has an important conceptual consequence. Perturbative renormalization in curved spacetime can be done without choosing a preferred state, without choosing a global coordinate system, and without relying on momentum space. The construction is intrinsically local.

## Scaling and almost homogeneous behavior

Flat-space renormalization often classifies counterterms by mass dimension. Curved-spacetime local covariance refines this by requiring controlled behavior under metric scaling. If

$$
g\longmapsto \lambda^{-2}g,
$$

then lengths, masses, fields, and curvature tensors scale in prescribed ways. A locally covariant Wick power or time-ordered product should scale almost homogeneously: it may acquire logarithmic scaling terms, but those terms must themselves be local and covariant.

This is the curved-spacetime version of the fact that renormalization introduces a scale. The logarithm is not a violation of locality; it is an allowed finite scaling anomaly. What is forbidden is a nonlocal or state-dependent response masquerading as a counterterm.

## Comparison with flat-space renormalization

The curved-spacetime framework agrees with flat-space perturbative renormalization when specialized to Minkowski space, but it organizes the logic differently.

| Flat-space habit | Local covariant replacement |
|---|---|
| Fourier transform and momentum subtraction. | Extension of distributions near diagonals. |
| Poincaré invariance. | Naturality under spacetime embeddings plus local geometry. |
| Constant counterterms. | Local covariant scalar, tensor, or spinor densities. |
| Vacuum normal ordering. | Hadamard subtraction and local covariant Wick powers. |
| Global $S$-matrix when available. | Local relative $S$-matrices and local algebras. |

The curved-spacetime formulation is more general but also stricter. It exposes which parts of perturbation theory are genuinely local and which parts rely on special global structure.

## What local covariance does not solve

Local covariance does not prove convergence of perturbation series. It does not remove infrared problems. It does not automatically produce a preferred physical state. It does not by itself solve gauge invariance: Ward identities, BRST identities, BV cohomology, and anomalies must be imposed or analyzed separately.

It also does not make all renormalization choices unique. The point is not to abolish renormalization freedom. The point is to classify it as finite, local, covariant freedom.

## Common pitfalls

**Thinking that curved spacetime just adds $R$ everywhere.** Curvature terms are allowed only when they have the correct covariance, tensor type, dimension, and field dependence.

**Using a preferred vacuum as part of the definition.** Generic curved spacetimes do not have a preferred vacuum. Local covariant time-ordered products must be defined independently of such a choice.

**Confusing local covariance with invariance under isometries.** Isometry covariance is a special case. Local covariance is functorial behavior under admissible embeddings between spacetimes.

**Forgetting the diagonal.** Away from coincident points, time ordering is controlled by causal factorization. Renormalization enters at diagonals.

**Calling every finite term a scheme choice.** In curved spacetime, finite terms must still satisfy locality, covariance, scaling, microlocal, and field-equation requirements.

## Relations to other pages

[Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) explains the singular two-point structure that replaces the flat vacuum two-point function. [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) gives the broader curved-spacetime renormalization picture.

Within this chapter, [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) defines the multilinear operations, [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) describes the ultraviolet extension problem, and [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) classifies the finite freedom left after the axioms are imposed.

## Research status

**Established.** The scalar-field framework of local covariant Wick powers and time-ordered products on globally hyperbolic spacetimes is a mature theorem-level part of perturbative algebraic QFT. It gives a precise curved-spacetime meaning to renormalized perturbation theory as formal power series.

**Technically subtle.** The detailed axiom lists are not optional: smooth and analytic dependence on the metric, microlocal spectrum bounds, scaling behavior, and causal factorization all do work.

**Active and adjacent.** Gauge theory requires compatibility with BRST or BV identities. Anomalies appear as obstructions to imposing all desired identities simultaneously. Nonperturbative construction remains outside the scope of the local-covariant time-ordered-product theorem.

## Exercises

1. **Naturality check.** Suppose $:\!\phi^2\!:_M$ is shifted by $c(x)\mathbf 1$ for an arbitrary smooth function $c$ on each spacetime. Explain why this is generally not a local covariant prescription.

<details><summary><strong>Solution</strong></summary>

A local covariant prescription must be natural under embeddings. If $\psi:M\to N$, the shift on $M$ must match the pullback of the shift on $N$:

$$
c_M(x)=c_N(\psi(x)).
$$

An arbitrary independently chosen function $c_M$ will not satisfy this for all embeddings. A scalar such as $R_M(x)$ does satisfy naturality because scalar curvature is constructed functorially from the metric.

</details>

2. **Allowed dimensions.** In four dimensions, $[\phi]=1$, $[m]=1$, and $[R]=2$. Which local covariant scalar terms can be added to $:\!\phi^2\!:$ without changing its engineering dimension?

<details><summary><strong>Solution</strong></summary>

The Wick square has dimension $2$. Scalar local covariant terms of dimension $2$ include $m^2\mathbf 1$ and $R\mathbf 1$, with dimensionless coefficients. A constant term alone has dimension $0$ and is not allowed unless multiplied by a dimension-two parameter. Terms such as $R^2$ have dimension $4$ and belong to higher-dimensional ambiguities, not to $:\!\phi^2\!:$.

</details>

3. **Flat limit.** What happens to the $R\mathbf 1$ ambiguity in $:\!\phi^2\!:$ when the spacetime is specialized to Minkowski space?

<details><summary><strong>Solution</strong></summary>

Minkowski space has $R=0$, so the curvature ambiguity vanishes in that specialization. This is why flat-space renormalization does not reveal the full curved-spacetime ambiguity. The term is nevertheless necessary in the locally covariant classification because it can appear on general backgrounds.

</details>

## References

- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).
- S. Hollands and R. M. Wald, “On the Renormalization Group in Curved Spacetime,” *Communications in Mathematical Physics* **237** (2003), 123–160. [arXiv:gr-qc/0209029](https://arxiv.org/abs/gr-qc/0209029), [doi:10.1007/s00220-003-0837-1](https://doi.org/10.1007/s00220-003-0837-1).
- S. Hollands and R. M. Wald, “Conservation of the Stress Tensor in Perturbative Interacting Quantum Field Theory in Curved Spacetimes,” *Reviews in Mathematical Physics* **17** (2005), 227–312. [arXiv:gr-qc/0404074](https://arxiv.org/abs/gr-qc/0404074), [doi:10.1142/S0129055X05002340](https://doi.org/10.1142/S0129055X05002340).
- R. Brunetti, K. Fredenhagen, and M. Köhler, “The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes,” *Communications in Mathematical Physics* **180** (1996), 633–652. [arXiv:gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056), [doi:10.1007/BF02099626](https://doi.org/10.1007/BF02099626).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- R. Brunetti, K. Fredenhagen, and R. Verch, “The Generally Covariant Locality Principle: A New Paradigm for Local Quantum Physics,” *Communications in Mathematical Physics* **237** (2003), 31–68. [arXiv:math-ph/0112041](https://arxiv.org/abs/math-ph/0112041), [doi:10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
