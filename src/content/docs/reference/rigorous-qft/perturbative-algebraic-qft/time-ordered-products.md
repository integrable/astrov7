---
title: "Time-Ordered Products"
description: "Defines time-ordered products in perturbative algebraic QFT and explains their Wick expansion, causal factorization, and renormalization ambiguities."
sidebar:
  label: "Time-Ordered Products"
  order: 4
level: Advanced
status: "Polished draft"
source: "Epstein–Glaser; Brunetti–Fredenhagen; Hollands–Wald; Rejzner pAQFT"
topics:
  - time-ordered products
  - Wick products
  - causal factorization
  - perturbative algebraic QFT
  - renormalization
canonicalTopics:
  - time-ordered-products
  - perturbative-algebraic-qft
  - causal-factorization
researchStatus:
  established:
    - "Renormalized time-ordered products can be constructed perturbatively as multilinear maps satisfying causal factorization, locality, covariance, scaling, and other normalization conditions."
  active:
    - "In gauge theories, compatibility of time-ordered products with BV-BRST identities and anomalies is a subtle additional problem beyond the scalar construction."
---

## Summary

Time-ordered products are the multilinear operations that generate perturbation theory. In informal notation one writes

$$
T\{\phi(x_1)\cdots\phi(x_n)\},
$$

as though time-ordering were just rearranging operators. In rigorous perturbative QFT, the real object is a family of renormalized maps

$$
T_n:\mathcal F_{\mathrm{loc}}^{\otimes n}\longrightarrow \mathcal A,
$$

where $\mathcal F_{\mathrm{loc}}$ is a space of local functionals or Wick polynomials and $\mathcal A$ is the free quantum algebra.

Away from coincident points, $T_n$ is given by Wick contractions with a Feynman two-point distribution. At coincident points, those contractions become products of singular distributions. Defining $T_n$ there is precisely the Epstein–Glaser renormalization problem.

Thus the time-ordered product is not merely a symbol in the Dyson expansion. It is the place where locality, causality, Wick expansion, and renormalization meet.

## Prerequisites

Read [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/), and [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/). For the distributional background, read [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) and [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/).

## Core idea

For ordinary quantum mechanics with a well-defined Hamiltonian, time-ordering is the instruction

$$
T\{A(t)B(s)\}
=
\begin{cases}
A(t)B(s), & t>s,\\
B(s)A(t), & s>t.
\end{cases}
$$

In QFT this formula is only the beginning. Fields are distributions, so expressions such as $\phi(x)^2$ or $T\{\phi(x)^4\phi(y)^4\}$ must be defined after smearing and renormalization. The problem is not ordering separated operators. The problem is defining the distributional boundary values when points collide.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Time-ordered products in perturbative algebraic QFT](/figures/rigorous-qft/time-ordered-products-structure.svg)

<figcaption>

Time-ordered products are built from Wick expansion away from diagonals and Epstein–Glaser extension at diagonals. The resulting maps $T_n$ generate the formal $S$-matrix and interacting fields while satisfying causal factorization and normalization conditions.

</figcaption>
</figure>

This is why time-ordered products are part of the definition of perturbative QFT, not a harmless afterthought.

## Setup and conventions

Let $\mathcal E$ be the space of smooth field configurations and let $\mathcal F_{\mathrm{loc}}$ denote local functionals. A typical local functional has the form

$$
F(\phi)=\int_M f(x)P\bigl(\phi(x),\nabla\phi(x),\ldots\bigr)\,d\mu_g(x),
$$

where $f$ is compactly supported and $P$ is a polynomial expression in the field and finitely many derivatives.

A time-ordered product is a sequence

$$
T_0=1,
\qquad
T_1(F)=F,
\qquad
T_n(F_1,\ldots,F_n)\in\mathcal A.
$$

In pAQFT, these maps define the formal time-ordered exponential

$$
\mathcal S(V)
=
\exp_T\left(\frac{iV}{\hbar}\right)
=
\sum_{n=0}^{\infty}
\frac{i^n}{\hbar^n n!}
T_n(V,\ldots,V).
$$

This is a formal series. The maps $T_n$ are defined coefficient by coefficient and are not assumed to arise from a convergent operator exponential.

## Wick expansion away from diagonals

For a free scalar field, let $H_F(x,y)$ denote the Feynman contraction in the chosen convention. For separated points, Wick's theorem gives

$$
T\{\phi(x)\phi(y)\}
=:\phi(x)\phi(y):+H_F(x,y)\mathbf 1.
$$

For Wick squares at separated points,

$$
\begin{aligned}
T_2\bigl(:\phi^2:(x),:\phi^2:(y)\bigr)
={}&:\phi^2(x)\phi^2(y):\\
&+4H_F(x,y):\phi(x)\phi(y):\\
&+2H_F(x,y)^2\mathbf 1.
\end{aligned}
$$

The combinatorial factors count contractions. There are four ways to contract one field at $x$ with one field at $y$, and two complete pairings.

This formula is safe for $x\neq y$. At $x=y$, the term $H_F(x,y)^2$ may fail to be a defined distribution. That is the first place where time-ordered products require renormalization beyond ordinary Wick ordering.

## The time-ordered product of regular functionals

For sufficiently regular functionals, one can write the time-ordered product compactly as a deformation product. Let

$$
\Gamma_{H_F}
=
\int_{M^2}H_F(x,y)
\frac{\delta}{\delta\phi(x)}\otimes
\frac{\delta}{\delta\phi(y)}\,d\mu_g(x)d\mu_g(y).
$$

Then define

$$
F\cdot_T G
=
 m\circ \exp\bigl(\hbar\Gamma_{H_F}\bigr)(F\otimes G),
$$

where $m$ is pointwise multiplication. This formula is a good model for the structure of the answer: functional derivatives create contractions, and $H_F$ supplies the propagator.

For local functionals, however, the same exponential can produce singular products of distributions. The renormalized maps $T_n$ are the extension of this formula to local functionals under the Epstein–Glaser normalization conditions.

## Time-ordered product versus star product

The time-ordered product should not be confused with the quantum operator product. In pAQFT, the free quantum algebra has a star product, often written schematically as

$$
F\star_H G
=
 m\circ \exp\bigl(\hbar\Gamma_H\bigr)(F\otimes G),
$$

where the antisymmetric part of $H$ is fixed by the causal propagator. The star commutator implements the canonical commutation relations:

$$
[F,G]_{\star_H}=i\hbar\{F,G\}+O(\hbar^2).
$$

The time-ordered product uses the Feynman contraction instead. Its job is not to be the operator product at equal time. Its job is to package perturbation theory.

A useful contrast is:

| Product | Distribution used | Role |
|---|---|---|
| $\star_H$ | Hadamard two-point distribution with prescribed antisymmetric part | Free quantum algebra and commutators. |
| $\cdot_T$ or $T_n$ | Feynman contraction or Feynman parametrix | Chronological products and perturbative interactions. |
| pointwise product | no contraction | Classical multiplication of functionals. |

The maps are related but conceptually distinct. Mixing them is a common source of sign and factor errors.

## Causal factorization

Time-ordered products are not arbitrary renormalized Wick expansions. They must satisfy causal factorization. If the supports of $F_1,\ldots,F_k$ are later than the supports of $F_{k+1},\ldots,F_n$, then

$$
T_n(F_1,\ldots,F_n)
=
T_k(F_1,\ldots,F_k)
\star
T_{n-k}(F_{k+1},\ldots,F_n),
$$

up to the grading and ordering conventions appropriate to the fields.

Equivalently, for formal $S$-matrices,

$$
\mathcal S(F+G)=\mathcal S(F)\star\mathcal S(G)
$$

when $\operatorname{supp}F$ is later than $\operatorname{supp}G$.

This condition is the causal heart of the Epstein–Glaser induction. It fixes $T_n$ on causally ordered regions in terms of lower-order products. Renormalization enters only when those local definitions must be extended across coincident configurations.

## Normalization conditions

A renormalized family $T_n$ is usually required to satisfy a package of normalization conditions. The exact list differs by formulation, but the following are the main ideas.

| Condition | What it controls |
|---|---|
| Initial conditions | $T_0=1$ and $T_1$ is the chosen embedding of local fields. |
| Symmetry | Permuting arguments changes only the expected Bose or Fermi signs. |
| Causal factorization | Chronological separation factors into lower time-ordered products. |
| Unitarity | Formal $S$-matrices satisfy the perturbative unitarity relation. |
| Commutator condition | Commutators with free fields reproduce functional derivatives and causal propagation. |
| Covariance | The construction respects Poincaré transformations or local covariance on curved spacetime. |
| Scaling | Short-distance behavior is controlled by scaling degree, allowing logarithms when necessary. |
| Field independence | Functional differentiation commutes with time-ordering in the appropriate sense. |
| Action Ward identity | Total derivative changes of the interaction are physically harmless, modulo anomalies. |

These conditions do not remove all ambiguity. They reduce it to the finite local renormalization freedom expected from perturbative QFT.

## Generating perturbation theory

Once the time-ordered products are chosen, the formal $S$-matrix is determined:

$$
\mathcal S(V)
=1+\frac{i}{\hbar}T_1(V)
+\frac{i^2}{2\hbar^2}T_2(V,V)+\cdots.
$$

Interacting fields are often defined through the relative $S$-matrix:

$$
\mathcal S_V(F)
=\mathcal S(V)^{-1}\star\mathcal S(V+F),
$$

and

$$
R_V(F)
=
\left.\frac{\hbar}{i}\frac{d}{d\tau}\right|_{\tau=0}
\mathcal S_V(\tau F).
$$

This formula shows why $T_n$ is load-bearing. Changing the finite renormalization of $T_n$ changes the definition of composite fields, couplings, and interacting observables by local redefinitions.

## Time-ordered products on curved spacetime

On a generic globally hyperbolic spacetime there is no preferred vacuum and no global translation-invariant Feynman propagator. The replacement is local and microlocal. One uses Hadamard parametrices and requires time-ordered products to be local covariant fields.

The important shift is:

$$
\text{Poincaré-invariant extension in Minkowski space}
\quad\leadsto\quad
\text{local covariant extension on curved spacetime}.
$$

Curvature terms can appear in the finite renormalization freedom. For example, Wick powers and stress tensors may have ambiguities involving local curvature polynomials. This is not a bug: it is the curved-spacetime version of local counterterm freedom.

The Hollands–Wald construction imposes locality, covariance, scaling, microlocal spectrum conditions, and continuity under metric variations. The result is a curved-spacetime analog of renormalized time-ordered products suitable for perturbative interacting fields.

## What time-ordering does not do

Time-ordering is often introduced in physics courses through theta functions:

$$
T\{\phi(x)\phi(y)\}
=
\theta(x^0-y^0)\phi(x)\phi(y)
+\theta(y^0-x^0)\phi(y)\phi(x).
$$

This formula is useful but incomplete. It assumes a coordinate time, hides distributional boundary-value issues, and does not define products at coincident points. In a rigorous construction, time-ordering is characterized by causal factorization and renormalized extension, not by theta functions alone.

Likewise, the Feynman propagator is not a probability measure. It is a distributional kernel used in contractions. Products of such kernels require microlocal and renormalization analysis.

## Common pitfalls

**Thinking $T$ only reorders operators.** Reordering is only the separated-point part. The coincident-point extension is the renormalization problem.

**Confusing Wick products with time-ordered products.** Wick products define composite normal-ordered fields relative to a two-point function. Time-ordered products multiply such composites in perturbation theory.

**Assuming normal ordering removes all divergences.** It removes self-contractions inside one Wick monomial. It does not define products of Wick monomials at coincident spacetime points.

**Forgetting the star product.** The formal $S$-matrix multiplies by $\star$, not by ordinary pointwise multiplication, when causal factorization is stated inside the free quantum algebra.

**Treating renormalization constants as nonlocal choices.** Under the standard axioms, the ambiguity is local: derivatives of delta functions in flat space and local curvature-polynomial analogs on curved spacetime.

## Relations to other pages

[Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/) explains why $\mathcal S(V)$ is interpreted formally. [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/) explains the induction principle behind $T_n$. [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/) explains the extension theorem that makes the maps finite.

For background on singular products, see [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). For curved-spacetime renormalization, see [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) and [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/).

## Research status

For scalar fields and many perturbative models, renormalized time-ordered products are a settled part of rigorous perturbation theory. The Epstein–Glaser, Brunetti–Fredenhagen, Hollands–Wald, and pAQFT formulations give mathematically precise constructions under explicit hypotheses.

The active frontier is not whether scalar time-ordered products can be defined. It is how the construction interacts with gauge symmetry, BV-BRST cohomology, anomalies, infrared limits, states, and nonperturbative completions.

## Exercises

### Exercise 1: Wick contraction count

Use Wick's theorem to explain the coefficients in

$$
\begin{aligned}
T_2\bigl(:\phi^2:(x),:\phi^2:(y)\bigr)
={}&:\phi^2(x)\phi^2(y):\\
&+4H_F(x,y):\phi(x)\phi(y):\\
&+2H_F(x,y)^2\mathbf 1.
\end{aligned}
$$

<details><summary><strong>Solution</strong></summary>

There are two fields at $x$ and two fields at $y$. A single cross-contraction chooses one of the two fields at $x$ and one of the two fields at $y$, giving $2\cdot 2=4$ choices. After one contraction, one field remains at each point, producing $:\phi(x)\phi(y):$.

For complete cross-contractions, the first field at $x$ can be paired with either of the two fields at $y$, and the remaining fields are then forced. This gives $2$ complete pairings, hence the coefficient of $H_F(x,y)^2$ is $2$.

</details>

### Exercise 2: Where renormalization enters

In the same formula, which term first requires renormalization at $x=y$ in four-dimensional scalar theory?

<details><summary><strong>Solution</strong></summary>

The term $H_F(x,y)^2\mathbf 1$ is the most immediate problem. For $x\neq y$ it is a product of two distributions evaluated away from the diagonal. As $x\to y$, it has a singularity with scaling degree equal to $4$ in four relative dimensions for the massless scalar case, giving a logarithmic extension ambiguity. The term with one $H_F$ is also singular as a distributional kernel but appears with remaining fields and is handled in the same renormalized time-ordered-product framework.

</details>

### Exercise 3: Causal factorization for two interactions

Let $F$ and $G$ have causally ordered supports, with $\operatorname{supp}F$ later than $\operatorname{supp}G$. What does causal factorization say about $\mathcal S(F+G)$?

<details><summary><strong>Solution</strong></summary>

It says

$$
\mathcal S(F+G)=\mathcal S(F)\star\mathcal S(G),
$$

up to the convention for what “later” means in the ordering. The product is the free quantum star product. This identity is the generating-functional version of factorization of time-ordered products for ordered supports.

</details>

## References

- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015). [arXiv:1208.1428](https://arxiv.org/abs/1208.1428).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
