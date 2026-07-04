---
title: "Perturbative QFT as Formal Power Series"
description: "Explains how perturbative algebraic QFT treats interacting fields, products, and S-matrices as formal power series rather than convergent functions."
sidebar:
  label: "Formal Power Series"
  order: 1
level: Advanced
status: "Polished draft"
source: "Brunetti–Dütsch–Fredenhagen; Fredenhagen–Rejzner; Rejzner pAQFT"
topics:
  - perturbative algebraic QFT
  - formal power series
  - deformation quantization
  - interacting fields
  - relative S-matrix
canonicalTopics:
  - perturbative-algebraic-qft
  - formal-power-series
  - deformation-quantization
researchStatus:
  established:
    - "Formal power series give a precise algebraic meaning to perturbative interacting fields and local algebras without assuming convergence of the perturbation expansion."
  active:
    - "Understanding when perturbative series are summable or arise from nonperturbative models is a separate problem, tied to constructive QFT, resurgence, and model-specific analysis."
---

## Summary

Perturbative QFT often produces series such as

$$
F(\lambda)\sim \sum_{n=0}^{\infty}\lambda^n F_n.
$$

In perturbative algebraic QFT, this is not treated as a badly behaved ordinary function of $\lambda$. It is treated as a **formal power series**: an object whose coefficients $F_n$ are defined by exact algebraic rules, and whose equality, product, inverse, and composition are interpreted coefficient by coefficient.

The basic move is

$$
A \quad\longmapsto\quad A[[\lambda]],
$$

where $A$ is an algebra of free-field observables or functionals and $A[[\lambda]]$ is the algebra of formal series with coefficients in $A$. Interactions are then introduced by formal $S$-matrices, relative $S$-matrices, or retarded products. This gives rigorous perturbation theory without claiming that the series converges.

This page explains the status of these formal objects, why they are not “just notation,” and how they support a local construction of interacting QFT.

## Prerequisites

Read [Conventions](/rigorous-qft/conventions/), [Physics QFT versus Mathematical QFT](/rigorous-qft/what-is-rigorous-qft/physics-qft-versus-mathematical-qft/), [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), and [Why Lorentzian Path Integrals Are Hard](/rigorous-qft/path-integrals-as-measures/why-lorentzian-path-integrals-are-hard/). For the distributional side, read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/).

## Core idea

A formal power series is a legitimate mathematical object. If $A$ is an algebra, then

$$
A[[\lambda]]
=\left\{
\sum_{n=0}^{\infty}\lambda^n a_n
\,\middle|\, a_n\in A
\right\}
$$

is an algebra with coefficientwise addition and Cauchy-product multiplication:

$$
\left(\sum_{n\geq 0}\lambda^n a_n\right)
\left(\sum_{n\geq 0}\lambda^n b_n\right)
=
\sum_{n\geq 0}\lambda^n
\left(\sum_{k=0}^n a_k b_{n-k}\right).
$$

No analytic convergence is being asserted. The infinite sum is controlled by the $\lambda$-adic topology: to know the answer modulo $\lambda^{N+1}$, only finitely many coefficients are needed.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Perturbative algebraic QFT as formal series](/figures/rigorous-qft/pa-qft-formal-series.svg)

<figcaption>

Perturbative algebraic QFT builds the interacting theory coefficient by coefficient. One starts with classical functionals, quantizes the free theory by a star product, chooses renormalized time-ordered products, and then forms relative $S$-matrices as formal power series.

</figcaption>
</figure>

This is a strong form of rigor, but it is a **perturbative** form of rigor. It proves that every coefficient is well-defined under stated axioms and renormalization choices. It does not prove that the resulting series defines an honest function for nonzero coupling.

## Setup and conventions

Let $M$ be a globally hyperbolic spacetime or, in a simpler first reading, Minkowski spacetime. The configuration space of a real scalar field is the affine space of smooth field configurations

$$
\mathcal E=C^\infty(M,\mathbb R).
$$

A functional is a map

$$
F:\mathcal E\to \mathbb C.
$$

For example,

$$
F_f(\phi)=\int_M f(x)\phi(x)\,d\mu_g(x)
$$

is linear, while

$$
V(\phi)=\int_M f(x)\frac{\lambda}{4!}\phi(x)^4\,d\mu_g(x)
$$

is a compactly supported local interaction when $f$ is a compactly supported switching function.

A pAQFT construction usually separates three ingredients:

| Ingredient | Role |
|---|---|
| Classical functionals | The off-shell objects to be quantized. |
| Free equation of motion | Determines the causal propagator and the on-shell ideal. |
| Choice of two-point distribution | Determines a concrete star product representation. |
| Time-ordered products | Encode perturbative interaction and renormalization. |
| Formal coupling | Records perturbative order without convergence assumptions. |

The word “off-shell” matters. In pAQFT one often first builds an algebra of functionals on all configurations, then imposes the free equation of motion by quotienting an ideal or by using the Peierls bracket and causal propagator. This is one reason the framework is flexible on curved spacetimes.

## Formal series as algebra, not approximation

Let $A$ be an algebra. The formal algebra $A[[\lambda]]$ has a precise notion of equality:

$$
\sum_{n\geq 0}\lambda^n a_n
=
\sum_{n\geq 0}\lambda^n b_n
\quad\Longleftrightarrow\quad
 a_n=b_n\text{ for every }n.
$$

The phrase “up to order $N$” means equality in the quotient

$$
A[[\lambda]]/(\lambda^{N+1}).
$$

Thus a statement such as

$$
F=G+O(\lambda^{N+1})
$$

means

$$
F_n=G_n\qquad \text{for }0\leq n\leq N.
$$

This is not numerical error analysis. It is algebraic truncation.

A formal series with invertible zeroth coefficient has a formal inverse. If

$$
A(\lambda)=a_0+\lambda a_1+\lambda^2a_2+\cdots
$$

and $a_0$ is invertible, then there is a unique formal series $B(\lambda)$ such that

$$
A(\lambda)B(\lambda)=1.
$$

This justifies, for example, the formal inverse of an $S$-matrix whose zeroth order term is the identity.

## The free star product

For a free scalar field, the quantum product is a deformation of the pointwise product of functionals. Given a suitable bidistribution $H$, define schematically

$$
F\star_H G
=
\sum_{n=0}^{\infty}
\frac{\hbar^n}{n!}
\left\langle
H^{\otimes n},
F^{(n)}\otimes G^{(n)}
\right\rangle .
$$

Here $F^{(n)}$ denotes the $n$th functional derivative, and the wavefront-set restrictions on $F$ and $G$ make the pairings meaningful. The antisymmetric part of $H$ is fixed by the causal propagator:

$$
H(x,y)-H(y,x)=i\Delta(x,y),
$$

so the star commutator begins as

$$
[F,G]_{\star_H}
=i\hbar\{F,G\}+O(\hbar^2),
$$

where $\{F,G\}$ is the Peierls bracket.

Different choices of $H$ with the same antisymmetric part give isomorphic descriptions of the same free algebra. They correspond to different normal-ordering prescriptions, not different physics.

## Time-ordering and the formal S-matrix

The free star product describes the noninteracting theory. Interactions enter through time-ordered products. Formally, a time-ordered exponential is written

$$
\mathcal S(V)
=\exp_T\!\left(\frac{i}{\hbar}V\right)
=\sum_{n=0}^{\infty}
\frac{i^n}{\hbar^n n!}
T_n(V^{\otimes n}).
$$

This expression is a formal series. Its coefficients are not obtained by multiplying distributions naively; the maps $T_n$ must be renormalized multilinear maps satisfying symmetry, causal factorization, microlocal spectrum conditions, field independence, and other normalization conditions.

For a local interaction $V$, the relative $S$-matrix is

$$
\mathcal S_V(F)
=\mathcal S(V)^{-1}\star
\mathcal S(V+F).
$$

An interacting field is obtained by differentiating with respect to $F$:

$$
R_V(F)
=\left.\frac{\hbar}{i}\frac{d}{d\tau}\right|_{\tau=0}
\mathcal S_V(\tau F).
$$

The factor $\hbar/i$ is conventional and matches the usual normalization of retarded products. The important point is structural: $R_V(F)$ is a formal power series in the interaction and a quantum observable in the free algebra.

## Local algebras from relative S-matrices

One of the strengths of pAQFT is that it does not require a global interacting Hilbert space at the start. Instead, it constructs local interacting algebras.

Let $\mathcal O\subset M$ be relatively compact. Choose an interaction $V$ whose coupling function is equal to the desired coupling near $\mathcal O$. The interacting observables localized in $\mathcal O$ are generated by the relative $S$-matrices $\mathcal S_V(F)$ with

$$
\operatorname{supp}F\subset \mathcal O.
$$

The causal structure implies that changing $V$ outside the causal domain relevant to $\mathcal O$ gives an isomorphic local algebra. This is the algebraic replacement for the often problematic adiabatic limit in which one tries to turn a compactly supported coupling into a constant coupling over all spacetime.

The slogan is:

$$
\text{global interaction may be infrared delicate,}
\qquad
\text{local interacting algebra is still meaningful.}
$$

## Example: scalar φ⁴ interaction

For scalar $\phi^4$ theory, the local interaction with compact spacetime cutoff $g$ is

$$
V_g(\phi)
=\int_M g(x)\frac{\lambda}{4!}\phi(x)^4\,d^4x.
$$

The interacting field associated with a test function $f$ is formally

$$
R_{V_g}(\phi(f))
=\phi(f)
+\lambda R_1(f)
+\lambda^2 R_2(f)+\cdots.
$$

Each coefficient $R_n(f)$ is built from retarded products or, equivalently, time-ordered products. The renormalization problem is to define those products when some integration variables coincide.

At first order, the classical equation suggests a correction involving the retarded propagator:

$$
R_1(f)
\sim
-\frac{1}{3!}
\int f(x)\Delta_R(x,y)g(y)\phi(y)^3
\,d^4x\,d^4y,
$$

up to convention-dependent signs and quantum normal-ordering choices. Higher orders require renormalized products of distributions.

## What formal perturbation theory can prove

A pAQFT theorem can prove statements such as:

| Statement | Precise meaning |
|---|---|
| The interacting field exists perturbatively. | Each coefficient in $R_V(F)$ is a well-defined element of the formal free algebra. |
| Renormalization ambiguities are local. | Different admissible $T_n$ differ by local counterterms supported on diagonals. |
| Locality is preserved. | Interacting observables assigned to causally disjoint regions commute. |
| The time-slice axiom holds perturbatively. | The algebra generated near a Cauchy surface determines the algebra in its domain of dependence. |
| Curved-spacetime perturbation theory exists. | Time-ordered products can be chosen locally and covariantly, with curvature-dependent ambiguities. |

These are powerful results. They are also not the same as proving that $\sum_n \lambda^n R_n(F)$ converges for a nonzero real value of $\lambda$.

## Formal, asymptotic, Borel, and convergent

The word “series” hides several distinct statuses.

| Status | Meaning |
|---|---|
| Formal series | Algebraic object; no convergence claim. |
| Asymptotic series | Finite truncations approximate a function in a limit. |
| Borel-summable series | A divergent series determines a function by Borel summation under analytic hypotheses. |
| Convergent series | The infinite sum converges in a specified topology. |
| Constructive limit | A genuine nonperturbative object is built and shown to have the perturbative expansion. |

pAQFT primarily provides the first kind of control. Some models have additional summability or constructive results, but those are extra theorems, not automatic consequences of the formal construction.

## Common pitfalls

**Thinking formal means sloppy.** A formal power series is exact in the formal category. Sloppiness enters only when one silently treats it as a convergent function without proof.

**Confusing a coupling cutoff with a UV cutoff.** In pAQFT the spacetime switching function $g$ controls the support of the interaction. It is not the same as a short-distance regularization. Ultraviolet renormalization is handled by extension of distributions and normalization conditions.

**Assuming diagrams are fundamental.** In this framework, diagrams are derived from the expansion of time-ordered products and functional derivatives. They are extremely useful bookkeeping devices, not the primitive definition.

**Forgetting the state-independent algebra.** pAQFT first constructs algebras. States can then be chosen on those algebras. This is different from starting with a preferred interacting vacuum.

**Calling the perturbative algebra a full model.** A formal interacting algebra is a rigorous perturbative model. A nonperturbative Wightman, OS, or constructive model requires additional existence theorems.

## Relations to other pages

This page clarifies the logical status of perturbation theory before the technical construction in [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/). It relies on the locality viewpoint of [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) and the microlocal restrictions introduced in [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). It contrasts with [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), where the goal is a genuine nonperturbative object, and with [Why Lorentzian Path Integrals Are Hard](/rigorous-qft/path-integrals-as-measures/why-lorentzian-path-integrals-are-hard/), where oscillatory integrals are discussed directly.

## Research status

The formal-power-series formulation of pAQFT is established. It gives a precise home for perturbative interacting fields, relative $S$-matrices, local algebras, and renormalization ambiguities in Minkowski and globally hyperbolic curved spacetimes.

The main caveat is the perturbative status. The construction is not a proof that the interacting theory exists as a convergent operator-valued distribution, Euclidean measure, or $C^*$-net at finite coupling. The relation between perturbative constructions and nonperturbative completions remains model-dependent.

Gauge theories require additional homological structure. The BV-BRST extension of pAQFT treats gauge symmetry as a cohomological problem and is developed in the later BV-BRST chapter.

## Exercises

### Exercise 1: Formal inverse

Let $A(\lambda)=1+\lambda a_1+\lambda^2a_2+O(\lambda^3)$ in a possibly noncommutative algebra. Find $B(\lambda)=1+\lambda b_1+\lambda^2b_2+O(\lambda^3)$ such that $A(\lambda)B(\lambda)=1+O(\lambda^3)$.

<details><summary><strong>Solution</strong></summary>

Compute the product:

$$
A(\lambda)B(\lambda)
=1+\lambda(a_1+b_1)
+\lambda^2(a_2+a_1b_1+b_2)
+O(\lambda^3).
$$

The coefficient of $\lambda$ vanishes if

$$
b_1=-a_1.
$$

The coefficient of $\lambda^2$ then gives

$$
a_2+a_1(-a_1)+b_2=0,
$$

so

$$
b_2=a_1^2-a_2.
$$

Thus

$$
B(\lambda)=1-\lambda a_1+
\lambda^2(a_1^2-a_2)+O(\lambda^3).
$$

The order of factors matters in higher orders if the algebra is noncommutative.

</details>

### Exercise 2: Meaning of equality modulo λ³

Suppose $F,G\in A[[\lambda]]$ and

$$
F=F_0+\lambda F_1+\lambda^2F_2+\lambda^3F_3+\cdots,
$$

$$
G=G_0+\lambda G_1+\lambda^2G_2+\lambda^3G_3+\cdots.
$$

What does $F=G+O(\lambda^3)$ mean?

<details><summary><strong>Solution</strong></summary>

It means equality in the quotient $A[[\lambda]]/(\lambda^3)$, so the coefficients agree through order $\lambda^2$:

$$
F_0=G_0,
\qquad
F_1=G_1,
\qquad
F_2=G_2.
$$

No statement is made about $F_3,G_3$ or higher coefficients. This is an algebraic statement, not a numerical bound.

</details>

### Exercise 3: First nontrivial star commutator

Use the schematic first-order expansion

$$
F\star_H G=FG+\hbar\langle H,F^{(1)}\otimes G^{(1)}\rangle+O(\hbar^2)
$$

and $H-H^{\operatorname{op}}=i\Delta$ to show that the star commutator begins with the Peierls bracket.

<details><summary><strong>Solution</strong></summary>

The reversed product is

$$
G\star_H F
=GF+\hbar\langle H,G^{(1)}\otimes F^{(1)}\rangle+O(\hbar^2).
$$

Since $FG=GF$ for the underlying pointwise product, the zeroth-order term cancels. Rewriting the second pairing with the opposite kernel gives

$$
[F,G]_{\star_H}
=\hbar\langle H-H^{\operatorname{op}},F^{(1)}\otimes G^{(1)}\rangle+O(\hbar^2).
$$

Using $H-H^{\operatorname{op}}=i\Delta$,

$$
[F,G]_{\star_H}
=i\hbar\langle \Delta,F^{(1)}\otimes G^{(1)}\rangle+O(\hbar^2).
$$

The bracket defined by the causal propagator is the Peierls bracket, so

$$
[F,G]_{\star_H}=i\hbar\{F,G\}+O(\hbar^2).
$$

</details>

## References

- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015). [arXiv:1208.1428](https://arxiv.org/abs/1208.1428).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- M. Dütsch, *From Classical Field Theory to Perturbative Quantum Field Theory*, Birkhäuser, 2019. [doi:10.1007/978-3-030-04738-2](https://doi.org/10.1007/978-3-030-04738-2).

## Version history

- **2026-07-01:** First polished draft.
