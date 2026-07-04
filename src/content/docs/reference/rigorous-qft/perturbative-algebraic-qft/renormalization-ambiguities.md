---
title: "Renormalization Ambiguities"
description: "Classifies the finite local freedom left by Epstein–Glaser and perturbative algebraic renormalization."
sidebar:
  label: "Renormalization Ambiguities"
  order: 8
level: Advanced
status: "Polished draft"
source: "Epstein–Glaser; Stückelberg–Petermann; Hollands–Wald; Brunetti–Dütsch–Fredenhagen; Rejzner pAQFT"
topics:
  - renormalization ambiguities
  - finite renormalization
  - local counterterms
  - Stückelberg–Petermann group
  - perturbative algebraic QFT
canonicalTopics:
  - renormalization-ambiguities
  - finite-renormalization
  - perturbative-algebraic-qft
  - epstein-glaser-renormalization
researchStatus:
  established:
    - "In causal perturbation theory and pAQFT, different admissible renormalization prescriptions differ by finite local counterterms, equivalently by a Stückelberg–Petermann finite renormalization."
  active:
    - "In gauge theories, the finite freedom is constrained by BV-BRST cohomology, and anomalies measure possible obstructions to imposing all Ward identities."
---

## Summary

Renormalization ambiguities are the finite choices left after all required axioms have been imposed on time-ordered products. In Epstein–Glaser language, if two extensions of a distribution have the same scaling degree, their difference is supported on the diagonal:

$$
t'-t
=
\sum_{|\alpha|\le \omega}
 c_\alpha\,\partial^\alpha\delta_\Delta.
$$

This formula is the local counterterm principle in its sharpest form. The constants $c_\alpha$ are not infinite quantities. They are finite parameters labelling different admissible renormalization prescriptions.

In perturbative algebraic QFT, the same freedom can be organized by the Stückelberg–Petermann renormalization group. If $\mathcal S$ and $\widehat{\mathcal S}$ are two formal $S$-matrices satisfying the same structural axioms, then under suitable hypotheses there is a finite local redefinition $Z$ such that

$$
\widehat{\mathcal S}(F)=\mathcal S(Z(F)).
$$

This page explains what this statement means, why the freedom is local, how it appears in examples, and why “scheme dependence” is not a synonym for “anything goes.”

## Prerequisites

Read [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/), [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/), [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/), and [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/). For the Wilsonian comparison, see [Renormalization as Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/) and [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/).

## Core idea

A perturbative construction has two separate jobs.

First, it must define time-ordered products away from singular configurations. Causal factorization and Wick expansion handle this part.

Second, it must extend singular distributions to diagonals. This is where ultraviolet renormalization enters. The extension is not always unique, but the non-uniqueness is controlled. It is supported exactly where the original formula was singular.

That is why renormalization ambiguity is local. If two prescriptions agree away from coincident points, their difference cannot be spread across spacetime. It must live on the collision locus. In position space this means derivatives of delta distributions. In Lagrangian language it means local counterterms.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Stückelberg–Petermann finite renormalization](/figures/rigorous-qft/renormalization-ambiguities-sp-group.svg)

<figcaption>

Two admissible renormalization prescriptions are related by a finite local redefinition $Z$. At the distributional level, this redefinition is built from local terms supported on diagonals; at the formal $S$-matrix level, it appears as $\widehat{\mathcal S}=\mathcal S\circ Z$.

</figcaption>
</figure>

## Setup and conventions

Let $t^\circ$ be a distribution originally defined on $\mathbb R^n\setminus\{0\}$. Suppose it has finite scaling degree $\operatorname{sd}(t^\circ)$. An extension $t$ to $\mathbb R^n$ can often be chosen with the same scaling degree. If $t$ and $t'$ are two such extensions, then their difference is supported at the origin. Hence

$$
t'-t
=
\sum_{|\alpha|\le \omega}
 c_\alpha\,\partial^\alpha\delta,
\qquad
\omega=\operatorname{sd}(t^\circ)-n,
$$

where only terms with nonnegative integer degree $\omega$ occur. More precisely, the largest derivative order is bounded by the allowed singular order; if $\omega<0$, the extension preserving scaling degree is unique.

On a manifold, the origin is replaced by a diagonal $\Delta\subset M^k$. Derivatives of $\delta$ along the diagonal are written invariantly using densities, jets, and covariant derivatives. In a local covariant construction, the coefficients $c_\alpha$ are replaced by local covariant expressions built from the metric, curvature, masses, couplings, and tensor data.

## The finite-renormalization viewpoint

Let $\mathcal S$ denote a formal $S$-matrix satisfying causal factorization. A second choice $\widehat{\mathcal S}$ satisfying the same structural axioms should not be unrelated to the first. The finite-renormalization theorem says, schematically, that

$$
\widehat{\mathcal S}=\mathcal S\circ Z,
$$

where $Z$ is a local formal map on interactions. It satisfies conditions of the form

$$
Z(0)=0,
\qquad
Z'(0)=\operatorname{id},
$$

and it preserves support locality in the sense that changing $F$ in a region changes $Z(F)$ only in that region. One may write

$$
Z(F)
=
F+
\sum_{k\ge 2}Z_k(F^{\otimes k}),
$$

where the higher $Z_k$ encode finite counterterms. The maps $Z_k$ are supported on diagonals and are local in the functional sense.

This is the Stückelberg–Petermann idea in algebraic form: renormalization transformations form a group of finite local redefinitions. It is conceptually different from a cutoff flow, but the two are related. The Stückelberg–Petermann group compares prescriptions; Wilsonian RG compares effective descriptions at different scales.

## What counts as the same physics?

Renormalization ambiguity does not mean that predictions are arbitrary. It means that a perturbative construction contains finite parameters that must be fixed by convention, symmetry, measurement, or matching.

A simple scalar example is the Wick square in curved spacetime:

$$
:\!\phi^2\!:
\longmapsto
:\!\phi^2\!:
+(c_1m^2+c_2R)\mathbf 1.
$$

The constants $c_1$ and $c_2$ label different definitions of the composite operator. Once a convention or normalization condition fixes them, later calculations must use the same convention.

For an interacting $\phi^4$ theory in four dimensions, local counterterms can shift the coefficients of

$$
\phi^4,
\qquad
(\nabla\phi)^2,
\qquad
m^2\phi^2,
\qquad
R\phi^2,
$$

and can also introduce purely geometric scalar densities in the effective action. The exact form depends on dimension, field content, symmetries, and normalization conditions.

## Ambiguity in time-ordered products

For two Wick squares at separated points, the Wick expansion contains

$$
T_2\bigl(:\!\phi^2\!:(x),:\!\phi^2\!:(y)\bigr)
\supset
2H_F(x,y)^2\mathbf 1.
$$

The expression $H_F(x,y)^2$ is defined away from $x=y$. Extending it to the diagonal may require a choice. In four-dimensional flat spacetime, the difference between two allowed extensions has the form

$$
c_0\delta(x-y)
+
 c_1\Box\delta(x-y)
+
\cdots,
$$

with the actual list bounded by the scaling degree and by the field expression being renormalized.

When this distribution is integrated against local test functions, the delta terms become local terms in the action or in composite operator definitions. Thus the diagrammatic phrase “add a counterterm” becomes a theorem about distributions supported on diagonals.

## Locality, covariance, and symmetry constraints

The allowed finite terms are cut down by the same principles used to define the theory.

| Constraint | Effect on ambiguity |
|---|---|
| Support locality | Counterterms must live where insertions collide. |
| Scaling degree | Only finitely many delta derivatives are allowed at each order. |
| Lorentz or local covariance | Coefficients must be invariant or natural geometric tensors. |
| Field dimension | Terms must have the correct engineering dimension, up to logarithmic scaling behavior. |
| Internal symmetry | Counterterms must transform as the original observable or interaction. |
| Field equation or Action Ward identity | Some derivative and equation-of-motion terms are related or forbidden. |
| BRST or BV identity | Gauge-compatible counterterms are cohomologically constrained. |

This is why a renormalization ambiguity is a classification problem, not a license to modify the theory arbitrarily.

## Stückelberg–Petermann versus Wilsonian RG

Two phrases called “renormalization group” coexist here.

The **Stückelberg–Petermann renormalization group** is the group of finite local redefinitions relating admissible renormalization prescriptions:

$$
\widehat{\mathcal S}=\mathcal S\circ Z.
$$

The **Wilsonian renormalization group** is a coarse-graining or scale-change procedure relating effective descriptions at different cutoffs or length scales.

They are related because changing scale changes the appropriate finite local terms. But they answer different questions.

| Question | Framework |
|---|---|
| How do two renormalization prescriptions differ? | Stückelberg–Petermann finite renormalization. |
| How does an effective action change when short-distance modes are integrated out? | Wilsonian RG. |
| Why are counterterms local? | Epstein–Glaser extension and causal factorization. |
| Which couplings run with scale? | Scaling action on finite renormalizations or Wilsonian flow. |

In pAQFT this distinction is useful because the finite-renormalization group can be formulated locally, without relying on an adiabatic limit or global momentum-space quantities.

## Operator mixing

Composite operators rarely renormalize alone. A local field $\mathcal O$ can mix with other local fields of the same quantum numbers and no larger dimension. Schematically,

$$
[\mathcal O]_R
\longmapsto
[\mathcal O]_R
+
\sum_i c_i[\mathcal O_i]_R.
$$

For example, a scalar operator of dimension four may mix with

$$
\phi^4,
\quad
m^2\phi^2,
\quad
(\nabla\phi)^2,
\quad
R\phi^2,
\quad
m^4\mathbf 1,
\quad
m^2R\mathbf 1,
\quad
R^2\mathbf 1,
\ldots
$$

subject to the equations of motion, total derivatives, and curvature identities. In gauge theory, the list must be replaced by BRST cohomology classes plus BRST-exact and equation-of-motion terms.

## Anomalies are not ordinary ambiguities

A Ward identity may fail after renormalization. Sometimes a finite counterterm can restore it. Sometimes no allowed local counterterm can restore all identities simultaneously. The latter case is an anomaly.

In cohomological language, the possible violation is a local cocycle. If it is a coboundary, it can be removed by a finite renormalization. If it represents a nontrivial cohomology class, it is a genuine anomaly.

This distinction is essential. Renormalization ambiguities are choices inside the space of admissible prescriptions. Anomalies are obstructions to satisfying a desired package of prescriptions.

## Common pitfalls

**Ambiguity means inconsistency.** No. It means additional finite normalization data are needed. The ambiguity is constrained and classifiable.

**Counterterms are only infinite subtractions.** In the Epstein–Glaser viewpoint, counterterms are local finite choices in distribution extension. Divergent regularization schemes are one way to find them, not the definition.

**Every local term is allowed.** No. It must satisfy scaling, covariance, support, symmetry, and field-content constraints.

**Scheme dependence means observables are meaningless.** Physical predictions require specifying how parameters and composite operators are normalized. Scheme changes are compensated by parameter changes.

**The Stückelberg–Petermann group is just the Wilsonian RG.** They are related but not identical. One compares renormalization prescriptions; the other changes scale or coarse-grains.

**Anomalies are removable counterterms.** Only trivial anomalies are removable. Genuine anomalies are precisely the non-removable cases.

## Relations to other pages

[Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) gives the local mathematical origin of the ambiguity. [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) explains how curved-spacetime covariance restricts it. [Renormalization of Composite Fields](/rigorous-qft/rigorous-renormalization-rg/renormalization-of-composite-fields/) gives the Wilsonian and operator-mixing perspective.

For the gauge-theory version, continue later to the BV-BRST chapter. There, finite counterterms are constrained by the quantum master equation and by the cohomology of the BRST differential.

## Research status

**Established.** In scalar perturbative algebraic QFT and causal perturbation theory, finite renormalization freedom is rigorously described by local counterterms and by the Stückelberg–Petermann renormalization group.

**Broadly understood.** The relation between finite renormalizations, scaling behavior, beta functions, and Wilsonian flow is well developed, though different frameworks organize the same physics differently.

**Subtle in gauge theory.** Gauge theories require compatibility with Ward identities, BRST/BV structure, and possible anomalies. The allowed ambiguity is not merely “all gauge-invariant terms” until one specifies the cohomological problem and the field-antifield complex.

## Exercises

1. **Uniqueness below critical scaling degree.** Let $t^\circ$ be a distribution on $\mathbb R^n\setminus\{0\}$ with $\operatorname{sd}(t^\circ)<n$. Explain why an extension preserving scaling degree is unique.

<details><summary><strong>Solution</strong></summary>

If two extensions $t$ and $t'$ preserve the scaling degree, their difference is supported at the origin. Any distribution supported at the origin is a finite sum of derivatives of $\delta$. The scaling degree of $\partial^\alpha\delta$ is $n+|\alpha|\ge n$. Since the allowed scaling degree is less than $n$, no nonzero such difference is allowed. Thus the extension is unique.

</details>

2. **Delta terms as counterterms.** Suppose an ambiguity in a two-point extension is $c\delta(x-y)$. Show how it becomes local after smearing with test functions $f(x)$ and $g(y)$.

<details><summary><strong>Solution</strong></summary>

Smearing gives

$$
\int dx\,dy\,f(x)g(y)c\delta(x-y)
=
c\int dx\,f(x)g(x).
$$

The result depends only on fields or test functions at the same point. This is the position-space reason that diagonal ambiguities correspond to local counterterms.

</details>

3. **Distinguish the two RGs.** In one sentence each, say what the Stückelberg–Petermann group and Wilsonian RG compare.

<details><summary><strong>Solution</strong></summary>

The Stückelberg–Petermann group compares different admissible finite renormalization prescriptions for the same perturbative construction. Wilsonian RG compares effective descriptions obtained by changing the scale or integrating out degrees of freedom.

</details>

## References

- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- E. C. G. Stückelberg and A. Petermann, “La normalisation des constantes dans la théorie des quanta,” *Helvetica Physica Acta* **26** (1953), 499–520.
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- M. Dütsch and K. Fredenhagen, “Action Ward Identity and the Stückelberg–Petermann Renormalization Group,” in *Rigorous Quantum Field Theory*, Progress in Mathematics **251** (2007), 113–124. [arXiv:hep-th/0501228](https://arxiv.org/abs/hep-th/0501228), [doi:10.1007/978-3-7643-7434-1_9](https://doi.org/10.1007/978-3-7643-7434-1_9).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- S. Hollands and R. M. Wald, “On the Renormalization Group in Curved Spacetime,” *Communications in Mathematical Physics* **237** (2003), 123–160. [arXiv:gr-qc/0209029](https://arxiv.org/abs/gr-qc/0209029), [doi:10.1007/s00220-003-0837-1](https://doi.org/10.1007/s00220-003-0837-1).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
