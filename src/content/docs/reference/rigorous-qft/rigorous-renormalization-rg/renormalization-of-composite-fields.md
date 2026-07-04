---
title: "Renormalization of Composite Fields"
description: "Explains how local composite fields are defined by smearing, subtraction, operator mixing, source derivatives, and RG flow rather than by naive pointwise products."
sidebar:
  label: "Composite Fields"
  order: 9
level: Advanced
status: "Polished draft"
source: "Wilson–Zimmermann; Zimmermann normal products; constructive RG literature"
topics:
  - composite fields
  - operator mixing
  - local observables
  - operator product expansion
  - rigorous renormalization
canonicalTopics:
  - composite-field-renormalization
  - operator-product-expansion
  - rigorous-rg
researchStatus:
  established:
    - "Renormalized local products are not obtained by naive pointwise multiplication; they require subtraction, mixing with fields of compatible quantum numbers, and definition through smeared insertions or source derivatives."
  active:
    - "Nonperturbative control of composite fields is model-dependent; constructive RG can handle important examples, while general interacting four-dimensional gauge-theory constructions remain open."
---

## Summary

A composite field is a local observable built from fields and their derivatives, such as $\phi^2$, $\phi^4$, $(\partial\phi)^2$, a current, or a stress tensor. In a continuum QFT, this phrase is dangerous: fields are distributions, and products of distributions at the same point are usually singular. A renormalized composite field is therefore not the bare pointwise product.

The schematic form is

$$
[\mathcal O_\alpha]_R
=\lim_{\Lambda\to\infty}
\sum_\beta Z_{\alpha\beta}(\Lambda,\mu)\,
\mathcal O_{\beta,\Lambda},
$$

where $\Lambda$ is a UV cutoff, $\mu$ is a normalization scale, and the sum is over local fields with the same symmetries and appropriate dimension. The limit is not a pointwise operator limit. It means convergence after smearing and inside correlation functions.

Composite-field renormalization matters because a QFT is not determined only by its action. Physical questions ask for local observables: energy density, currents, order parameters, densities, Wilsonian perturbations, and the terms appearing in an operator product expansion. Renormalizing the coupling constants in the action does not automatically define all of these local fields.

## Prerequisites

Read [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/), [Rigorous φ⁴ Renormalization](/rigorous-qft/rigorous-renormalization-rg/rigorous-phi-four-renormalization/), and [Multiscale Analysis](/rigorous-qft/rigorous-renormalization-rg/multiscale-analysis/). The page also uses the measure language of [Euclidean Action as Density](/rigorous-qft/path-integrals-as-measures/euclidean-action-as-density/).

## Core idea

The fast mental model is this:

$$
\text{composite field}
=\text{response of the theory to a local source}.
$$

Instead of trying to multiply fields at a point directly, introduce a source $h$ coupled to a cutoff local expression $\mathcal O_\Lambda$:

$$
V_\Lambda(\phi;h)
=V_\Lambda(\phi)
+\int d^dx\,h(x)\mathcal O_\Lambda(x).
$$

Then define the renormalized insertion by differentiating the renormalized generating functional with respect to the renormalized source. Under RG, the source itself flows and mixes with sources for other local fields. Composite-field renormalization is the study of this enlarged RG problem.

<figure class="doc-figure" style="--figure-width: 47rem;">

![Composite-field renormalization as source flow and operator mixing](/figures/rigorous-qft/composite-field-renormalization.svg)

<figcaption>

A bare local product $\mathcal O_{\alpha,\Lambda}$ is not usually a continuum field. One couples sources to a basis of cutoff local fields, runs the RG, subtracts and mixes compatible fields, and obtains smeared renormalized insertions and OPE data.

</figcaption>
</figure>

This point is central in rigorous QFT because it separates two questions that are often conflated:

| Question | What it controls |
|---|---|
| Does the continuum theory exist? | Schwinger functions or local algebras without extra insertions. |
| Do the local observables exist? | Limits of correlation functions with inserted composite fields. |

The first question can be easier than the second. A constructive measure may exist while a particular local product still needs a nontrivial normalization.

## Setup and conventions

We use Euclidean scalar notation for clarity. Let $\phi_\Lambda$ be a cutoff field and let $\mathcal O_{\alpha,\Lambda}(x)$ be a local polynomial in $\phi_\Lambda$ and finitely many derivatives. A smeared cutoff insertion is

$$
\mathcal O_{\alpha,\Lambda}(f)
=\int d^dx\,f(x)\mathcal O_{\alpha,\Lambda}(x),
$$

with $f$ a test function. A renormalized composite field is specified by a collection of coefficients $Z_{\alpha\beta}$ and a limiting prescription such that

$$
\left\langle [\mathcal O_\alpha]_R(f)
\prod_{i=1}^n \phi(f_i)\right\rangle
=\lim_{\Lambda\to\infty}
\sum_\beta Z_{\alpha\beta}(\Lambda,\mu)
\left\langle \mathcal O_{\beta,\Lambda}(f)
\prod_{i=1}^n \phi_\Lambda(f_i)\right\rangle_\Lambda
$$

exists as a distribution in all test functions.

The index $\beta$ does not range over every imaginable expression. It is restricted by symmetries, locality, and dimension or power counting. For example, in a $\mathbb Z_2$-symmetric scalar theory, an even scalar field can mix only with even scalar fields. Translation and rotation invariance restrict tensor structure. In perturbative power counting, fields of sufficiently high dimension usually do not enter the subtraction for a given operator.

The mixing matrix is often triangular after fields are ordered by dimension, but the precise ordering depends on the framework. In constructive RG, the mixing is encoded by source coordinates and local projections rather than only by a formal matrix of counterterms.

## Wick powers as the first example

The free Gaussian field already shows why composite fields need definitions. Suppose $\phi_\epsilon$ is a smoothed Gaussian field with covariance $C_\epsilon(x,y)$. The naive square has expectation

$$
\mathbb E\bigl[\phi_\epsilon(x)^2\bigr]
=C_\epsilon(x,x),
$$

which often diverges as $\epsilon\to 0$. The Wick square subtracts this singular mean:

$$
:\!\phi^2\!:_\epsilon(x)
=\phi_\epsilon(x)^2-C_\epsilon(x,x).
$$

For the fourth power,

$$
:\!\phi^4\!:_\epsilon
=\phi_\epsilon^4
-6C_\epsilon(x,x)\phi_\epsilon^2
+3C_\epsilon(x,x)^2.
$$

These formulas are not arbitrary decorations. They are exactly the subtractions that make Gaussian correlation functions with Wick insertions have finite limits under suitable smearing. They also show a general pattern: a composite field is a local expression plus lower-order local counterterms.

Interacting theories require more. Wick ordering with respect to the free covariance removes the purely Gaussian self-contractions, but interactions generate additional short-distance singularities and operator mixing.

## Source derivatives and local perturbations

A clean way to organize composite fields is to extend the action by local sources. Let $\{\mathcal O_\alpha\}$ be a basis of local fields compatible with the symmetries. Write

$$
Z[J,h]
=\int \exp\left\{-V(\phi)+J(\phi)
-\sum_\alpha h_\alpha(\mathcal O_\alpha)\right\}
 d\mu_C(\phi).
$$

Then

$$
\frac{\delta}{\delta h_\alpha(x)}\log Z[J,h]\bigg|_{h=0}
$$

generates connected correlation functions with an insertion of $\mathcal O_\alpha(x)$, after the correct renormalization of the source coordinates has been performed.

This viewpoint has two advantages.

First, it makes the insertion local but not pointwise naive. The source $h_\alpha$ is a test function or smooth background field, so the observable is smeared from the start.

Second, it turns operator mixing into ordinary coordinate mixing. If the RG step sends

$$
h_\alpha\mapsto h'_\alpha
=\sum_\beta M_{\alpha\beta}h_\beta+\text{nonlinear terms},
$$

then the renormalization of composite fields is controlled by the linearized source flow and its counterterms.

## Mixing and anomalous dimensions

The renormalized fields generally depend on the normalization scale $\mu$. This dependence is governed by an anomalous-dimension matrix. In a perturbative notation,

$$
\mu\frac{d}{d\mu}[\mathcal O_\alpha]_R
=-\sum_\beta \gamma_{\alpha\beta}[\mathcal O_\beta]_R.
$$

The matrix $\gamma$ is the infinitesimal version of the RG mixing of local fields. At a fixed point, its eigenvectors are scaling fields. A scaling field $\mathcal O_i$ has a scaling dimension

$$
\Delta_i=\Delta_i^{\mathrm{eng}}+\gamma_i,
$$

where $\Delta_i^{\mathrm{eng}}$ is the engineering dimension and $\gamma_i$ is an anomalous contribution.

This is the local-observable analogue of the classification of relevant and irrelevant coupling directions. Couplings describe perturbations of the action; composite fields describe local coordinates on observables and responses.

## Relation to the operator product expansion

Composite fields are the objects that appear on the right side of an operator product expansion. Schematically,

$$
[\mathcal O_A](x)[\mathcal O_B](y)
\sim
\sum_C C_{AB}^{\;C}(x-y)[\mathcal O_C](y)
\qquad (x\to y).
$$

The OPE is not merely a formal multiplication rule. It says that the singular part of a product of local fields near coincidence can be expanded in a basis of renormalized local fields, with coefficient distributions $C_{AB}^{\;C}$. The meaning of the asymptotic symbol depends on the framework: Wightman distributions, Euclidean Schwinger functions, perturbative algebraic fields, or constructive correlation functions.

In RG language, the OPE expresses the fact that a small cluster of insertions looks local when observed from a larger scale. This is the same locality principle that drives multiscale renormalization: high-momentum or short-distance subclusters are replaced by local fields plus remainders.

## Constructive RG viewpoint

In constructive RG, composite fields are usually handled by adding source-dependent polymer activities or local coordinates. A scale-$j$ representation might have the schematic form

$$
Z_j(\phi;h)=I_j(\phi;h)\circ K_j(\phi;h),
$$

where $h$ records source insertions. The RG step must preserve differentiability or analyticity in $h$:

$$
\mathbb E_{C_{j+1}}
\bigl[Z_j(\phi+\zeta;h)\bigr]
=Z_{j+1}(\phi;h).
$$

The composite-field correlation functions are obtained by differentiating the final object with respect to $h$. The estimates must therefore control not only $K_j$ but also its source derivatives.

For a single insertion, one often proves bounds for a marked polymer: a polymer activity carrying a distinguished point or region where the local observable is inserted. For multiple insertions, one must control marked clusters and their connectedness. This is why composite-field renormalization naturally meets polymer expansions and OPE estimates.

## Checks

A proposed renormalized composite field should pass several checks.

| Check | What it tests |
|---|---|
| Smearing | Correlations are distributions, not pointwise functions. |
| Symmetry | Mixing respects rotations, internal symmetries, parity, charge conjugation, and other constraints. |
| Dimension | Only allowed lower or equal dimension fields enter the subtraction in a given scheme. |
| Normalization | A finite renormalization condition fixes remaining ambiguity. |
| RG covariance | Changing $\mu$ is described by an anomalous-dimension matrix or source flow. |
| OPE compatibility | Short-distance products expand in the chosen field basis. |

The most important check is conceptual: the definition must be formulated in terms of correlation functions, local algebras, or source derivatives. A symbolic monomial alone is not a definition.

## Common pitfalls

**Treating $\phi^2(x)$ as automatically meaningful.** Even in a free field theory, $\phi(x)$ is distributional and $\phi(x)^2$ is singular. Wick ordering or another renormalization prescription is already needed.

**Forgetting operator mixing.** A composite field rarely renormalizes alone. It can mix with all compatible local fields, including lower-dimensional fields and total derivatives, depending on the chosen observable and scheme.

**Confusing a scheme with an observable.** Minimal subtraction, normal products, Wick ordering, and source-normalization conditions define different representatives. Physical statements must be invariant under allowed finite redefinitions or explicitly tied to a convention.

**Thinking action counterterms define all insertions.** Counterterms that make partition functions and ordinary Schwinger functions finite do not automatically fix local inserted products. Local observables need their own normalization conditions.

**Ignoring smearing.** A rigorous local field is usually an operator-valued distribution, a random distribution, or a natural transformation tested against functions. The point label $x$ is a shorthand for distributional behavior.

## Relations to other pages

[Multiscale Analysis](/rigorous-qft/rigorous-renormalization-rg/multiscale-analysis/) explains why short-distance subclusters become local. [Polymer Expansions](/rigorous-qft/rigorous-renormalization-rg/polymer-expansions/) explains the connected estimates used for source-marked activities. [Locally Covariant Fields](/rigorous-qft/locally-covariant-qft/locally-covariant-fields/) develops a categorical and curved-spacetime version of local fields. [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) treats local Wick products and time-ordered products under local covariance.

Later pages in Perturbative Algebraic QFT will return to composite fields through causal perturbation theory, distribution extension, and local covariant time-ordered products.

## Research status

The perturbative theory of composite fields, normal products, and operator mixing is a mature subject. The free and perturbative curved-spacetime theory of local Wick polynomials is also well developed under locality and covariance conditions.

Nonperturbative constructions are more delicate. In two- and three-dimensional constructive models, many local fields and insertions can be controlled with model-specific estimates. In physically central four-dimensional interacting gauge theories, the full nonperturbative construction of the theory and its local composite observables remains part of the broader open problem.

## Exercises

### Exercise 1: Wick square covariance

Let $\phi_\epsilon$ be a centered Gaussian field with covariance $C_\epsilon(x,y)$. Define

$$
:\!\phi^2\!:_\epsilon(x)=\phi_\epsilon(x)^2-C_\epsilon(x,x).
$$

Show that

$$
\mathbb E\left[:\!\phi^2\!:_\epsilon(x):\!\phi^2\!:_\epsilon(y)\right]
=2C_\epsilon(x,y)^2.
$$

<details><summary><strong>Solution</strong></summary>

For centered Gaussian variables $X=\phi_\epsilon(x)$ and $Y=\phi_\epsilon(y)$, Wick's theorem gives

$$
\mathbb E[X^2Y^2]
=\mathbb E[X^2]\mathbb E[Y^2]
+2\mathbb E[XY]^2.
$$

Subtracting the two means gives

$$
\mathbb E[(X^2-\mathbb E[X^2])(Y^2-\mathbb E[Y^2])]
=2\mathbb E[XY]^2
=2C_\epsilon(x,y)^2.
$$

This is the first indication that Wick ordering removes the coincident self-contractions but keeps genuine correlations.

</details>

### Exercise 2: Mixing by symmetry

In a $\mathbb Z_2$-invariant scalar theory, which fields can mix with an even scalar composite field? Explain why $\phi$ cannot appear in the subtraction for $\phi^2$.

<details><summary><strong>Solution</strong></summary>

The subtraction must respect the symmetries used to define the theory and the observable. Under $\phi\mapsto -\phi$, the field $\phi$ is odd, while $\phi^2$ is even. Therefore an even scalar field cannot mix with $\phi$ if the renormalization prescription preserves the $\mathbb Z_2$ symmetry.

Compatible candidates include the identity, $\phi^2$, $\phi^4$, $(\partial\phi)^2$, and derivative terms such as $\partial^2\phi^2$, subject to dimension and tensor-structure restrictions. For the renormalization of $\phi^2$ in a power-counting scheme, only fields allowed by the dimension bound and the chosen normalization conditions enter.

</details>

### Exercise 3: Source derivative

Let

$$
Z[h]=\int e^{-V(\phi)-h(\mathcal O)}d\mu(\phi),
$$

where $h(\mathcal O)=\int h(x)\mathcal O(x)d^dx$. Compute $-\delta\log Z[h]/\delta h(x)$ at $h=0$ formally and interpret the result.

<details><summary><strong>Solution</strong></summary>

Formally differentiating gives

$$
-\frac{\delta}{\delta h(x)}\log Z[h]\bigg|_{h=0}
=\frac{1}{Z[0]}
\int \mathcal O(x)e^{-V(\phi)}d\mu(\phi)
=\langle \mathcal O(x)\rangle.
$$

With additional field sources $J$, further derivatives generate correlation functions with one insertion of $\mathcal O(x)$. In a rigorous treatment, $h$ is a test function and $\mathcal O$ must be replaced by its renormalized smeared version.

</details>

## References

- K. G. Wilson, “Non-Lagrangian Models of Current Algebra,” *Physical Review* **179** (1969) 1499–1512. [doi:10.1103/PhysRev.179.1499](https://doi.org/10.1103/PhysRev.179.1499).
- K. G. Wilson and W. Zimmermann, “Operator Product Expansions and Composite Field Operators in the General Framework of Quantum Field Theory,” *Communications in Mathematical Physics* **24** (1972) 87–106. [doi:10.1007/BF01878448](https://doi.org/10.1007/BF01878448).
- W. Zimmermann, “Composite Operators in the Perturbation Theory of Renormalizable Interactions,” *Annals of Physics* **77** (1973) 536–569. [doi:10.1016/0003-4916(73)90430-2](https://doi.org/10.1016/0003-4916(73)90430-2).
- W. Zimmermann, “Normal Products and the Short Distance Expansion in the Perturbation Theory of Renormalizable Interactions,” *Annals of Physics* **77** (1973) 570–601. [doi:10.1016/0003-4916(73)90429-6](https://doi.org/10.1016/0003-4916(73)90429-6).
- J. C. Collins, *Renormalization*, Cambridge University Press, 1984.
- S. Hollands, “The Operator Product Expansion for Perturbative Quantum Field Theory in Curved Spacetime,” *Communications in Mathematical Physics* **273** (2007) 1–36. [doi:10.1007/s00220-007-0230-6](https://doi.org/10.1007/s00220-007-0230-6), [arXiv:gr-qc/0605072](https://arxiv.org/abs/gr-qc/0605072).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001) 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074).
- V. Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991.
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).

## Version history

- **2026-07-01:** First polished draft.
