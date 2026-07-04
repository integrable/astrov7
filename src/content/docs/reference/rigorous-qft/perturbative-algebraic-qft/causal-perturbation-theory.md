---
title: "Causal Perturbation Theory"
description: "Explains causal perturbation theory as the inductive construction of time-ordered products from causal factorization and extension of distributions to diagonals."
sidebar:
  label: "Causal Perturbation Theory"
  order: 2
level: Advanced
status: "Polished draft"
source: "Epstein–Glaser; Dütsch–Fredenhagen; Brunetti–Fredenhagen; Hollands–Wald"
topics:
  - causal perturbation theory
  - Epstein–Glaser renormalization
  - time-ordered products
  - causal factorization
  - distribution extension
canonicalTopics:
  - causal-perturbation-theory
  - epstein-glaser-renormalization
  - time-ordered-products
researchStatus:
  established:
    - "Causal perturbation theory gives a rigorous position-space construction of perturbative time-ordered products; ultraviolet renormalization appears as extension of distributions to coincident configurations."
  active:
    - "Gauge theories, infrared questions, global states, and nonperturbative completion require additional structures beyond the basic scalar causal construction."
---

## Summary

Causal perturbation theory constructs perturbative QFT from locality. Instead of beginning with divergent momentum-space loop integrals, it builds time-ordered products inductively and uses causal factorization to determine them away from coincident points.

The main object is a family of multilinear maps

$$
T_n(F_1,\ldots,F_n),
$$

where the $F_i$ are local functionals or Wick polynomials. When the supports are causally ordered, $T_n$ must factor into lower-order time-ordered products. This fixes $T_n$ on the configuration space with diagonals removed. Renormalization is then the problem of extending the resulting distributions to the diagonals.

The slogan is:

$$
\text{causality fixes the outside of the diagonals;}
\qquad
\text{renormalization extends to the diagonals.}
$$

This is the Epstein–Glaser viewpoint in modern pAQFT language.

## Prerequisites

Read [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/), [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/), and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). You should also be comfortable with the idea that products of distributions are not automatically defined.

## Core idea

In ordinary perturbative QFT, ultraviolet divergences often appear as ill-defined integrals. Causal perturbation theory moves the problem to position space and asks a sharper question: how should a distribution defined away from coincident points be extended to the coincident locus?

For $n$ insertions, let

$$
\Delta_n\subset M^n
$$

be the union of partial diagonals, where at least two points coincide. Causal factorization and lower-order products determine $T_n$ on

$$
M^n\setminus \Delta_n.
$$

The remaining step is the extension

$$
t\in \mathcal D'(M^n\setminus \Delta_n)
\quad\leadsto\quad
\widetilde t\in \mathcal D'(M^n),
$$

subject to locality, covariance, scaling, symmetry, unitarity, and field-independence conditions.

<figure class="doc-figure" style="--figure-width: 49rem;">

![Causal perturbation theory as distribution extension](/figures/rigorous-qft/causal-perturbation-extension.svg)

<figcaption>

Causal perturbation theory is an induction over the number of insertions. Lower-order products and causal ordering determine the distribution away from diagonals. Renormalization is the controlled extension to coincident configurations, with finite local ambiguity under scaling-degree bounds.

</figcaption>
</figure>

This is why causal perturbation theory is local. The ambiguity is supported where points coincide, so it is described by local counterterms.

## Setup and conventions

Let $M$ be a globally hyperbolic spacetime with causal order $\preceq$. For compactly supported functionals $F$ and $G$, write

$$
\operatorname{supp}F \gtrsim \operatorname{supp}G
$$

when every point in $\operatorname{supp}F$ is not earlier than every point in $\operatorname{supp}G$ in the causal sense appropriate to the chosen convention.

A time-ordered product is a sequence of maps

$$
T_n:\mathcal F_{\mathrm{loc}}^{\otimes n}\to \mathcal A,
\qquad n\geq 0,
$$

with

$$
T_0=1,
\qquad
T_1(F)=F
$$

up to the chosen embedding of local functionals into the free quantum algebra. In pAQFT these maps are used to define

$$
\mathcal S(V)=
\sum_{n=0}^{\infty}
\frac{i^n}{\hbar^n n!}
T_n(V^{\otimes n}).
$$

The maps $T_n$ are not arbitrary. They must satisfy normalization conditions that encode the physical and geometric requirements of perturbative QFT.

## Causal factorization

The defining locality condition is causal factorization. If the index set $\{1,\ldots,n\}$ is split into two nonempty subsets $I$ and $J$, and every support in $I$ is later than every support in $J$, then

$$
T_n(F_1,\ldots,F_n)
=
T_{|I|}(F_I)
\star
T_{|J|}(F_J),
$$

where $F_I$ and $F_J$ denote the ordered sublists. The exact order convention depends on how $T_n$ and the star product are normalized, but the content is invariant: causally separated clusters factor into lower-order products.

For the formal $S$-matrix, the same idea is often expressed as

$$
\mathcal S(F+G)=\mathcal S(F)\star\mathcal S(G)
$$

when $\operatorname{supp}F$ is later than $\operatorname{supp}G$.

This condition is powerful because it determines the $n$th product away from the diagonals using only lower-order information. The inductive problem is therefore local around coincident points.

## The induction step

Assume $T_k$ has been constructed for $k<n$. To construct $T_n$:

| Step | Task | Mathematical issue |
|---|---|---|
| 1 | Use causal factorization on causally ordered configurations. | Determines $T_n$ on regions of $M^n\setminus\Delta_n$. |
| 2 | Glue the definitions on overlapping regions. | Consistency follows from associativity and the induction hypothesis. |
| 3 | Obtain distributions away from diagonals. | Products are well-defined because points are separated. |
| 4 | Extend distributions to diagonals. | This is the ultraviolet renormalization step. |
| 5 | Impose normalization conditions. | Fixes part of the finite local ambiguity. |

The difficult part is step 4. If a distribution has sufficiently controlled scaling degree near a diagonal, extensions exist, and the ambiguity is finite-dimensional at each order. This is the rigorous version of the counterterm freedom familiar from perturbative renormalization.

## Extension to the diagonal

In a local coordinate chart, the essential problem often reduces to extending a distribution

$$
t\in \mathcal D'(\mathbb R^N\setminus\{0\})
$$

to a distribution $\widetilde t\in\mathcal D'(\mathbb R^N)$. The scaling degree measures the singularity at the origin:

$$
\operatorname{sd}(t)
=\inf\left\{\delta\,\middle|\,
\lambda^\delta t(\lambda x)\to 0
\text{ as }\lambda\to 0^+
\right\}.
$$

If $\operatorname{sd}(t)<N$, the extension is unique under preservation of scaling degree. If $\operatorname{sd}(t)\geq N$, extensions exist but are not unique. The ambiguity is a finite linear combination of derivatives of the delta distribution:

$$
\widetilde t\mapsto
\widetilde t+
\sum_{|\alpha|\leq \operatorname{sd}(t)-N}
 c_\alpha\,\partial^\alpha\delta.
$$

This formula is the cleanest mathematical image of renormalization in the causal approach. Counterterms are not infinite quantities being subtracted. They are local extension ambiguities compatible with the chosen normalization conditions.

## Retarded products and interacting fields

Causal perturbation theory can be expressed in terms of time-ordered products or retarded products. In pAQFT the relative $S$-matrix is

$$
\mathcal S_V(F)
=\mathcal S(V)^{-1}\star\mathcal S(V+F),
$$

and the interacting field associated with $F$ is

$$
R_V(F)
=\left.\frac{\hbar}{i}\frac{d}{d\tau}\right|_{\tau=0}
\mathcal S_V(\tau F).
$$

Expanding in $V$ gives retarded products:

$$
R_V(F)
=\sum_{n=0}^{\infty}\frac{1}{n!}
R_n(V^{\otimes n};F).
$$

Retarded support encodes causality: the effect of the interaction on $F$ is localized in the causal past of the observable insertion, according to the chosen convention for retarded fields. This is why retarded products are well adapted to local interacting fields.

## Renormalization conditions

The extension to diagonals is not unique, so one imposes normalization conditions. Common conditions include:

| Condition | Meaning |
|---|---|
| Symmetry | $T_n$ is symmetric under permutation of arguments. |
| Causal factorization | Time ordering factors for causally ordered supports. |
| Unitarity | The formal $S$-matrix satisfies the appropriate adjoint relation. |
| Field independence | Functional differentiation commutes with time ordering in a controlled way. |
| Scaling degree | Extensions do not become more singular than necessary. |
| Local covariance | Definitions are natural under spacetime embeddings. |
| Microlocal spectrum condition | Wavefront sets have the allowed causal structure. |
| Action Ward identity | Total derivatives in the Lagrangian do not change interacting fields. |

Different admissible choices correspond to finite renormalizations. They form the Stückelberg–Petermann renormalization group in the modern algebraic formulation.

## Relation to Feynman diagrams

Feynman diagrams are still present, but they are not primary. Once the time-ordered products are expanded using Wick's theorem or functional derivatives, each graph gives a distribution on configuration space. Away from diagonals, the graph distribution is well-defined. Renormalization extends it across coincident vertices.

For example, a graph with vertices $x_1,\ldots,x_n$ gives a product of propagator-type distributions on

$$
M^n\setminus \Delta_n.
$$

The causal construction does not integrate over ill-defined products first and repair them later. It defines the products as distributions with specified extension rules before they are inserted into the perturbative algebra.

This is the conceptual inversion:

$$
\text{not }\quad
\text{divergent integral}\to\text{subtraction},
$$

but

$$
\text{distribution off diagonal}\to
\text{local extension}\to
\text{finite renormalization freedom}.
$$

## A minimal example of local ambiguity

Consider a distribution on $\mathbb R^4\setminus\{0\}$ whose scaling degree is $4$. Its extensions to $\mathbb R^4$ preserving scaling degree can differ by a multiple of $\delta(x)$:

$$
\widetilde t_1-\widetilde t_2=c\,\delta(x).
$$

In a scalar theory, this ambiguity corresponds to a local counterterm. If the graph has external field factors, the same delta-supported ambiguity becomes a local monomial in the fields and derivatives. This is how the ordinary list of counterterms emerges from locality and scaling.

If the scaling degree is $6$ in four dimensions, the ambiguity can include derivatives up to order $2$:

$$
\sum_{|\alpha|\leq 2}c_\alpha\partial^\alpha\delta(x).
$$

Symmetry and covariance restrict which combinations are allowed.

## Why this matters

Causal perturbation theory matters for three reasons.

First, it separates ultraviolet and infrared issues. The local extension problem is ultraviolet. Whether one can take an adiabatic limit or construct a preferred state is a separate infrared question.

Second, it works naturally on curved spacetimes. Momentum-space subtraction schemes depend heavily on translation symmetry. Causal perturbation theory uses locality, covariance, and microlocal analysis instead.

Third, it clarifies what renormalization freedom is. The ambiguity is local, finite at each order, and organized by normalization conditions. This is exactly the kind of statement that can be compared across algebraic QFT, curved-spacetime QFT, and effective field theory.

## Common pitfalls

**Saying causal perturbation theory has no renormalization.** It has renormalization, but it appears as extension freedom rather than divergent subtraction.

**Thinking the diagonal is only the total diagonal.** Partial diagonals also matter. Subdivergences correspond to coincident subsets of vertices, and the induction must handle them consistently.

**Confusing causal factorization with Euclidean clustering.** Causal factorization is a Lorentzian locality condition about causal order, not a large-distance decay statement.

**Forgetting normalization conditions.** Extension alone is too broad. The physical construction requires symmetry, unitarity, covariance, microlocal spectrum restrictions, and other conditions.

**Assuming gauge theory is automatic.** Gauge theories require Ward identities or BV-BRST cohomology to control the compatibility of renormalization with gauge symmetry.

## Relations to other pages

This page follows [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/) and prepares the later pages on Epstein–Glaser renormalization, time-ordered products, extension of distributions, causal factorization, and renormalization ambiguities. It is also the perturbative counterpart of [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/). The microlocal condition behind multiplication and extension should be read with [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/).

## Research status

Causal perturbation theory is an established rigorous formulation of perturbative renormalization. The Epstein–Glaser construction gives a position-space inductive method; modern pAQFT combines it with local algebras, microlocal analysis, and local covariance.

The scalar and nongauge framework is conceptually clean. Gauge theories require extra cohomological control, usually BV-BRST. The adiabatic limit, existence of physical states, and nonperturbative completion are additional questions.

The framework remains active because it interfaces with curved-spacetime QFT, locally covariant fields, perturbative quantum gravity, factorization algebras, and modern algebraic descriptions of renormalization.

## Exercises

### Exercise 1: Unique extension below the critical degree

Let $t\in\mathcal D'(\mathbb R^N\setminus\{0\})$ have scaling degree $\operatorname{sd}(t)<N$. Why is there no delta-function ambiguity preserving the scaling degree?

<details><summary><strong>Solution</strong></summary>

The delta distribution has scaling degree $N$, and its derivative $\partial^\alpha\delta$ has scaling degree $N+|\alpha|$. If $\operatorname{sd}(t)<N$, adding any nonzero distribution supported at the origin would add a term of scaling degree at least $N$, increasing the scaling degree. Therefore an extension that preserves the original scaling degree is unique.

</details>

### Exercise 2: Ambiguity in four dimensions

Suppose a scalar graph distribution on $\mathbb R^4\setminus\{0\}$ has scaling degree $5$. What is the most general form of the difference between two extensions that preserve scaling degree?

<details><summary><strong>Solution</strong></summary>

For $N=4$ and $\operatorname{sd}(t)=5$, the allowed order of derivatives is

$$
|\alpha|\leq \operatorname{sd}(t)-N=1.
$$

Thus two extensions can differ by

$$
c\delta(x)+c_\mu\partial^\mu\delta(x).
$$

If Lorentz invariance, parity, or other symmetries are imposed, some of the coefficients may be forced to vanish.

</details>

### Exercise 3: Causal factorization for three insertions

Let $F_1$ be later than both $F_2$ and $F_3$, with no causal ordering assumed between $F_2$ and $F_3$. What does causal factorization say about $T_3(F_1,F_2,F_3)$?

<details><summary><strong>Solution</strong></summary>

Take $I=\{1\}$ and $J=\{2,3\}$. Since $F_1$ is later than both $F_2$ and $F_3$, causal factorization gives

$$
T_3(F_1,F_2,F_3)
= T_1(F_1)\star T_2(F_2,F_3),
$$

up to the convention for which factor is written first for later supports. No factorization of $T_2(F_2,F_3)$ is implied unless $F_2$ and $F_3$ are also causally ordered.

</details>

## References

- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015). [arXiv:1208.1428](https://arxiv.org/abs/1208.1428).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
