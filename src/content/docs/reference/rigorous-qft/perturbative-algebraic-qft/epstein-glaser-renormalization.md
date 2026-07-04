---
title: "Epstein–Glaser Renormalization"
description: "Explains Epstein–Glaser renormalization as the extension of causally determined distributions to coincident-point diagonals."
sidebar:
  label: "Epstein–Glaser Renormalization"
  order: 3
level: Advanced
status: "Polished draft"
source: "Epstein–Glaser; Brunetti–Fredenhagen; Dütsch–Fredenhagen; Hollands–Wald"
topics:
  - Epstein–Glaser renormalization
  - causal perturbation theory
  - scaling degree
  - distribution extension
  - local counterterms
canonicalTopics:
  - epstein-glaser-renormalization
  - causal-perturbation-theory
  - distribution-extension
researchStatus:
  established:
    - "Epstein–Glaser renormalization gives a regulator-free, position-space formulation of perturbative renormalization in which ultraviolet ambiguities are local distribution-extension ambiguities."
  active:
    - "The Epstein–Glaser construction is perturbative; gauge theory, infrared limits, and nonperturbative completion require additional structures and hypotheses."
---

## Summary

Epstein–Glaser renormalization is the cleanest way to say what ultraviolet renormalization does in perturbative QFT. At order $n$, causality determines the relevant time-ordered distribution away from coincident configurations. Renormalization is the remaining extension problem:

$$
t_0\in \mathcal D'(M^n\setminus \Delta_n)
\quad\leadsto\quad
\widetilde t\in \mathcal D'(M^n),
$$

where $\Delta_n$ is the union of partial diagonals where some insertion points coincide.

The slogan is not “subtract infinity.” It is:

$$
\text{renormalization}
=\text{extension of singular distributions}
+\text{local normalization choices}.
$$

The main tool is the **scaling degree**, which measures how singular a distribution is near a diagonal. If the singularity is mild, the extension is unique. If it is too singular, the ambiguity is finite-dimensional and supported on the diagonal, hence local. This is the precise mathematical version of finite counterterm freedom.

## Prerequisites

Read [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/), [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/), and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). The next page, [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/), explains the multilinear maps whose construction uses this extension theorem.

## Core idea

The ultraviolet problem appears when products of singular distributions are forced onto coincident points. In a Feynman-graph calculation, this often looks like a divergent momentum integral. In Epstein–Glaser renormalization, the same obstruction is formulated directly in position space.

For separated insertion points, Wick expansion and causal factorization give well-defined distributions. The trouble begins at the diagonals. For two insertions, the diagonal is

$$
\Delta_2=\{(x,y)\in M^2\mid x=y\}.
$$

For $n$ insertions, there are many partial diagonals:

$$
x_i=x_j,
\qquad
x_i=x_j=x_k,
\qquad
\ldots
$$

The induction in causal perturbation theory constructs time-ordered products first away from those diagonals. The extension to the diagonals is exactly the renormalization step.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Epstein–Glaser renormalization as extension to the diagonal](/figures/rigorous-qft/epstein-glaser-extension.svg)

<figcaption>

Epstein–Glaser renormalization turns the ultraviolet problem into an extension problem. Causal factorization fixes the distribution away from coincident configurations. Scaling degree controls whether the extension is unique or has a finite local ambiguity supported on the diagonal.

</figcaption>
</figure>

This does not make renormalization disappear. It identifies precisely what renormalization is allowed to change: local terms supported where points coincide.

## Setup and conventions

Let $M$ be a $d$-dimensional globally hyperbolic spacetime, or take $M=\mathbb R^{1,d-1}$ for the Minkowski first pass. A local field monomial such as $:\phi^k:(x)$ is an operator-valued distribution, so it must be smeared. Products at distinct points can be meaningful even when products at the same point are not.

A typical time-ordered product of Wick monomials has the separated-point form

$$
T_n\bigl(:\phi^{k_1}:(x_1),\ldots,:\phi^{k_n}:(x_n)\bigr)
=
\sum_\Gamma t_\Gamma(x_1,\ldots,x_n)\,\mathcal O_\Gamma,
$$

where $\Gamma$ runs over contraction patterns, $\mathcal O_\Gamma$ is a Wick monomial in the remaining fields, and $t_\Gamma$ is a product of two-point distributions. Away from partial diagonals, the products $t_\Gamma$ are well-defined under the usual microlocal conditions.

In translation-invariant Minkowski space, one often factors out the overall translation and studies relative coordinates. Near the total diagonal, this reduces the local extension problem to

$$
t_0\in \mathcal D'(\mathbb R^N\setminus\{0\}),
\qquad
N=d(n-1),
$$

and asks for an extension $\widetilde t\in \mathcal D'(\mathbb R^N)$.

The curved-spacetime version is local. One works in coordinate neighborhoods, uses covariance and microlocal spectrum conditions to control products, and requires the extension to be local and covariant under isometric embeddings.

## Scaling degree

The scaling degree measures the strength of a distributional singularity at the origin. For a distribution $t\in\mathcal D'(\mathbb R^N\setminus\{0\})$, define

$$
\operatorname{sd}_0(t)
=
\inf\left\{
\delta\in\mathbb R\,\middle|\,
\lambda^\delta t(\lambda x)\to 0
\text{ as }\lambda\to 0^+
\right\}.
$$

This notation abbreviates the usual distributional scaling against test functions. The important point is its meaning:

| Distribution near $0$ in $\mathbb R^N$ | Scaling degree |
|---|---:|
| smooth function | $\leq 0$ |
| $|x|^{-a}$ with $a>0$ | $a$ |
| $\delta(x)$ | $N$ |
| $\partial^\alpha\delta(x)$ | $N+|\alpha|$ |

The **singular order** is

$$
\omega(t)=\operatorname{sd}_0(t)-N.
$$

The sign of $\omega$ tells the story:

$$
\omega<0
\quad\Longrightarrow\quad
\text{unique extension preserving scaling degree},
$$

while

$$
\omega\geq 0
\quad\Longrightarrow\quad
\text{finite local ambiguity}.
$$

More precisely, if two extensions preserve the same scaling-degree bound, then their difference is supported at the origin. A distribution supported at a point is a finite sum of derivatives of the delta distribution, so

$$
\widetilde t'
=
\widetilde t+
\sum_{|\alpha|\leq \lfloor \omega\rfloor}
 c_\alpha\,\partial^\alpha\delta.
$$

This formula is the Epstein–Glaser form of counterterms.

## The extension theorem

The extension theorem used in causal perturbation theory may be stated in the following working form.

:::note[Distribution extension]
Let $t_0\in\mathcal D'(\mathbb R^N\setminus\{0\})$ have finite scaling degree. Then $t_0$ has an extension $\widetilde t\in\mathcal D'(\mathbb R^N)$ with the same scaling degree. If $\operatorname{sd}_0(t_0)<N$, that extension is unique. If $\operatorname{sd}_0(t_0)\geq N$, the extensions preserving the same scaling-degree bound form an affine space modeled on

$$
\operatorname{span}\{\partial^\alpha\delta\mid |\alpha|\leq \operatorname{sd}_0(t_0)-N\}.
$$
:::

When the scaling degree is not an integer, the upper bound is interpreted with the integer part. In physics language, $\operatorname{sd}_0(t_0)-N$ is the superficial degree of divergence of the local position-space problem.

The theorem is useful because it separates three issues that are often entangled in informal perturbation theory:

| Issue | Epstein–Glaser formulation |
|---|---|
| Existence of renormalized amplitudes | Existence of extensions preserving scaling degree. |
| Number of counterterms | Dimension of the space of delta-derivative ambiguities. |
| Renormalization conditions | Choice of a point in this finite-dimensional affine space. |

The extension theorem does not decide the numerical values of the finite constants $c_\alpha$. Those are fixed by normalization conditions, symmetries, measurements, or a chosen renormalization scheme.

## Example: a logarithmic singularity

In four spacetime dimensions, the square of a massless scalar Feynman two-point distribution behaves near $x=0$ like

$$
D_F(x)^2\sim \frac{1}{(x^2-i0)^2}.
$$

The ambient relative-coordinate dimension is $N=4$, and this singularity has scaling degree $4$. Hence

$$
\omega=\operatorname{sd}_0(D_F^2)-4=0.
$$

The extension is not unique. Any two extensions preserving scaling degree differ by a constant multiple of $\delta(x)$:

$$
\widetilde{D_F^2}\,{}'
=
\widetilde{D_F^2}+c\,\delta(x).
$$

A common representative introduces a scale $\mu$ and writes the extension schematically as

$$
\left[\frac{1}{(x^2-i0)^2}\right]_\mu
\sim
\Box\left(
\frac{\log\bigl(\mu^2(x^2-i0)\bigr)}{x^2-i0}
\right)
+c\,\delta(x),
$$

with convention-dependent constants and $i0$ prescriptions. The scale $\mu$ is not a new physical field. It records a choice of extension, and changing $\mu$ changes the local $\delta$-term. This is the position-space ancestor of logarithmic running.

## Subdiagonals and the forest intuition

The phrase “extend to the diagonal” hides a subtlety: for $n\geq 3$, there are many diagonals. Points can collide in pairs, triples, or larger subsets. A distribution may be singular near each of these strata.

Epstein–Glaser induction handles this by assuming all lower-order products have already been renormalized. That means singularities on proper subdiagonals have already been addressed. The remaining step at order $n$ is the extension to the total diagonal after those lower-order choices are in place.

This is the position-space analog of the forest structure in BPHZ renormalization. Subdivergences are not ignored; they are removed by earlier inductive steps. What remains is a local extension ambiguity at the current diagonal.

## Normalization conditions

The extension theorem leaves finite local freedom. A QFT is not specified until this freedom is constrained by normalization conditions. Common conditions include:

| Condition | Meaning |
|---|---|
| Symmetry | Time-ordered products are symmetric in their arguments for bosonic fields, with graded signs for fermions. |
| Causal factorization | Ordered supports factor into lower-order products. |
| Unitarity | Time-ordered and anti-time-ordered products are related so that formal $S$-matrices are unitary in the appropriate sense. |
| Poincaré covariance | In Minkowski space, extensions should transform correctly under the Poincaré group. |
| Local covariance | On curved spacetime, extensions should be built locally and geometrically from the metric and other background structures. |
| Scaling or almost homogeneous scaling | Extensions should respect the expected short-distance scaling up to logarithms. |
| Field independence | Functional derivatives of time-ordered products should agree with inserting differentiated fields, modulo stated anomalies. |
| Action Ward identity | Total derivatives in the interaction should not affect interacting fields in the wrong way. |

Not every list of conditions is imposed in every formulation. The modern pAQFT and locally covariant versions are especially careful about locality, covariance, field independence, and the Action Ward identity.

## Comparison with cutoff renormalization

A cutoff computation modifies the theory at short distances, calculates finite quantities, and then adjusts bare parameters as the cutoff is removed. Epstein–Glaser renormalization instead defines the extension directly and never needs divergent intermediate expressions.

The two languages are compatible when both are applied correctly. The cutoff language is often efficient for calculations and physical intuition. The Epstein–Glaser language is often clearer about locality and mathematical status.

A useful dictionary is:

| Cutoff or diagram language | Epstein–Glaser language |
|---|---|
| Divergent loop integral | Distribution too singular at a diagonal. |
| Counterterm | Delta-derivative extension ambiguity. |
| Subdivergence | Singularity on a proper partial diagonal. |
| Renormalization condition | Choice of extension constants. |
| Logarithmic divergence | Scaling degree equal to ambient dimension. |
| Renormalization scale | Parameter in an almost homogeneous extension. |

The Epstein–Glaser construction is not “less physical.” It is a way of making the local content of perturbation theory explicit.

## Common pitfalls

**Thinking the extension is unique.** It is unique only when the scaling degree is below the dimension of the local extension problem.

**Confusing local ambiguity with arbitrary functions.** Local covariance and scaling reduce the ambiguity to finitely many local curvature and field terms at each order, not arbitrary spacetime-dependent functions.

**Forgetting subdivergences.** At high orders, one must control partial diagonals, not only the total diagonal. The induction hypothesis is essential.

**Treating the cutoff as the definition.** A cutoff can be useful, but in the Epstein–Glaser formulation the renormalized distribution is the object, and divergent regularized expressions are optional scaffolding.

**Assuming perturbative existence implies nonperturbative existence.** Epstein–Glaser renormalization constructs formal series. It does not prove that the series sums to a genuine theory at nonzero coupling.

## Relations to other pages

[Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/) explains the induction that produces the distributions needing extension. [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) explains the $T_n$ maps that Epstein–Glaser renormalization defines.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives the microlocal language for products of distributions. [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) explains how local covariance and curvature terms enter. [Constructive RG Methods](/rigorous-qft/rigorous-renormalization-rg/constructive-rg-methods/) treats a different, nonperturbative renormalization tradition.

## Research status

For scalar and many nongauge perturbative theories, Epstein–Glaser and pAQFT methods give a precise perturbative construction. On curved spacetimes, microlocal analysis and local covariance provide a robust replacement for translation invariance and vacuum normal ordering.

Gauge theories require extra homological structure. In modern treatments, this is supplied by BV-BRST methods, where the compatibility of renormalization with the master equation becomes the central issue. Infrared problems and adiabatic limits are also separate from the ultraviolet extension theorem.

The construction is rigorous as perturbation theory. It is not a proof that a nontrivial interacting continuum measure, Hilbert-space representation, or convergent $S$-matrix exists beyond formal power series.

## Exercises

### Exercise 1: Scaling degree of a power singularity

Let $t(x)=|x|^{-a}$ on $\mathbb R^N\setminus\{0\}$ with $a>0$. What is its scaling degree near $0$? For which $a$ is the extension preserving scaling degree unique?

<details><summary><strong>Solution</strong></summary>

Under $x\mapsto \lambda x$,

$$
|\lambda x|^{-a}=\lambda^{-a}|x|^{-a}.
$$

Thus $\operatorname{sd}_0(t)=a$. The extension preserving scaling degree is unique if $a<N$. If $a\geq N$, the ambiguity is supported at the origin and is a finite sum of derivatives of $\delta$ up to order $\lfloor a-N\rfloor$.

</details>

### Exercise 2: Delta derivatives as counterterms

Suppose $t_0\in\mathcal D'(\mathbb R^4\setminus\{0\})$ has scaling degree $6$. What is the most general difference between two extensions preserving the same scaling-degree bound?

<details><summary><strong>Solution</strong></summary>

Here $N=4$ and $\omega=6-4=2$. Therefore two such extensions differ by

$$
\sum_{|\alpha|\leq 2}c_\alpha\partial^\alpha\delta.
$$

The allowed ambiguity includes $\delta$, first derivatives of $\delta$, and second derivatives of $\delta$. Additional symmetries, such as Lorentz invariance or parity, can remove some of these coefficients.

</details>

### Exercise 3: Why locality follows from support

Why is an ambiguity supported on the diagonal interpreted as a local counterterm?

<details><summary><strong>Solution</strong></summary>

A distribution supported on the diagonal only contributes when insertion points coincide. In relative coordinates it is a finite sum of derivatives of $\delta$. After smearing against local field monomials, such terms become integrals of local expressions built from fields and their derivatives at a single spacetime point. That is exactly the form of a local counterterm.

</details>

## References

- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- O. Steinmann, *Perturbation Expansions in Axiomatic Field Theory*, Lecture Notes in Physics **11**, Springer, 1971. [doi:10.1007/BFb0025525](https://doi.org/10.1007/BFb0025525).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
