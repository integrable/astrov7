---
title: "Interacting Fields as Formal Series"
description: "Explains how perturbative algebraic QFT constructs interacting fields from relative S-matrices, retarded products, and formal power series."
sidebar:
  label: "Interacting Fields"
  order: 9
level: Advanced
status: "Polished draft"
source: "Dütsch–Fredenhagen retarded products; Brunetti–Dütsch–Fredenhagen pAQFT; Fredenhagen–Rejzner; Rejzner pAQFT"
topics:
  - interacting fields
  - formal power series
  - relative S-matrices
  - retarded products
  - perturbative algebraic QFT
canonicalTopics:
  - interacting-fields
  - formal-power-series
  - perturbative-algebraic-qft
  - retarded-products
researchStatus:
  established:
    - "Perturbative algebraic QFT constructs interacting fields and local interacting algebras as formal power series by means of relative S-matrices or retarded products."
  active:
    - "The construction is local and perturbative; convergence, global adiabatic limits, gauge constraints, and physical state construction are separate questions."
---

## Summary

An interacting field in perturbative algebraic QFT is not introduced by putting a formal interaction Hamiltonian on a fixed Fock space and hoping that the result exists. It is constructed locally from the free algebra, a renormalized time-ordered product, and a relative $S$-matrix.

For an interaction functional $V$ and a test interaction $F$, the relative $S$-matrix is

$$
\mathcal S_V(F)
=
\mathcal S(V)^{-1}_{\star}\star \mathcal S(V+F),
$$

and the interacting field associated with $F$ is the Bogoliubov derivative

$$
R_V(F)
=
\left.\frac{\hbar}{i}\frac{d}{d\lambda}
\mathcal S_V(\lambda F)\right|_{\lambda=0}.
$$

This formula should be read coefficient by coefficient in formal parameters such as the coupling and $\hbar$. It is a rigorous perturbative construction, not a convergence theorem. Its power is locality: the field $R_V(F)$ depends only on the interaction in the causal past of the support of $F$, up to the causal domain relevant for the chosen local algebra.

The main lesson is that “the interacting field” is a derived local object. The global $S$-matrix is often the wrong starting point; the relative $S$-matrix and retarded products are the local objects that survive in curved spacetime and in situations where infrared limits are delicate.

## Prerequisites

You should have read [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/), [Causal Factorization](/rigorous-qft/perturbative-algebraic-qft/causal-factorization/), and [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/). The pages on [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) and [Hadamard Condition](/rigorous-qft/locally-covariant-qft/hadamard-condition/) provide the algebraic and microlocal background.

## Core idea

Ordinary perturbation theory often starts from the slogan

$$
\text{interacting theory}
\approx
\text{free theory} + \text{interaction}.
$$

Perturbative algebraic QFT makes the slogan local and algebraic. Start with a free algebra $\mathcal A$ of observables. Choose renormalized time-ordered products, hence a formal $S$-matrix $\mathcal S$. Add an interaction $V$, but use it only through relative changes of $\mathcal S$. Then define interacting fields by differentiating the relative $S$-matrix.

This shifts the meaning of “interaction” from a global operator $e^{-i\int H_I dt}$ to a local response operation:

$$
\text{interacting field}
=
\text{response of }\mathcal S(V)
\text{ to a localized insertion }F.
$$

That response can be expanded in retarded products. These products express causality directly: only insertions in the appropriate causal past contribute to the local interacting observable.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Interacting fields from relative S-matrices](/figures/rigorous-qft/interacting-fields-formal-series.svg)

<figcaption>

The local construction of an interacting field in pAQFT. The interaction $V$ enters through the formal $S$-matrix; the relative $S$-matrix compares $V+F$ with $V$; the Bogoliubov derivative extracts the interacting field $R_V(F)$.

</figcaption>
</figure>

## Setup and conventions

Let $M$ be a globally hyperbolic spacetime and let $\mathcal A(M)$ be the free pAQFT algebra built from microcausal functionals with product $\star$. A local functional has the schematic form

$$
F(\phi)=\int_M f(x)\,\mathcal O(\phi)(x)\,d\mu_g(x),
$$

where $f$ is compactly supported and $\mathcal O$ is a local expression in the field and finitely many derivatives. For example, a local scalar interaction may be written

$$
V_g(\phi)
=
\int_M g(x)\,\frac{\lambda}{4!}\phi(x)^4\,d\mu_g(x),
$$

where $g$ is a compactly supported spacetime cutoff. The subscript on $V_g$ is a reminder that a local construction normally begins with a compactly supported interaction. The question of removing $g$ is an infrared or adiabatic-limit question, not the ultraviolet renormalization problem itself.

A renormalized time-ordered product gives the formal $S$-matrix

$$
\mathcal S(F)
=
\exp_T\!\left(\frac{i}{\hbar}F\right)
=
\sum_{n=0}^{\infty}
\frac{i^n}{n!\hbar^n}
T_n(F^{\otimes n}).
$$

This expression lives in a formal power-series algebra. The inverse $\mathcal S(V)^{-1}_{\star}$ is the inverse with respect to the free product $\star$, again understood formally.

:::caution[Status of the formula]
The formula for $\mathcal S(F)$ is not an analytic exponential on a Hilbert space. It is a formal series built from renormalized multilinear maps $T_n$. That is why the inverse, product, and derivative in the relative $S$-matrix are algebraic operations in formal series.
:::

## Relative S-matrices

The relative $S$-matrix is

$$
\mathcal S_V(F)
=
\mathcal S(V)^{-1}_{\star}\star \mathcal S(V+F).
$$

It measures the effect of adding the localized perturbation $F$ when the background interaction $V$ is already present. This is the algebraic version of asking how an interacting theory responds to an additional source.

The formal interacting field is then

$$
R_V(F)
=
\left.\frac{\hbar}{i}\frac{d}{d\lambda}
\mathcal S_V(\lambda F)\right|_{\lambda=0}.
$$

At zeroth order in $V$, this returns the free observable $F$ in the free algebra. At higher orders, it inserts interaction vertices with retarded causal support.

Expanding the relative $S$-matrix gives

$$
R_V(F)
=
\sum_{n=0}^{\infty}
\frac{1}{n!}R_n(V^{\otimes n};F),
$$

up to the conventional powers of $i/\hbar$ absorbed into the definition of $R_n$. Different authors place these factors differently. The invariant content is that $R_n$ is an $(n+1)$-linear retarded product built from time-ordered products and the free $\star$-product.

The first nontrivial term is the retarded response of $F$ to the interaction:

$$
R_V(F)=F+R_1(V;F)+O(V^2).
$$

For regular functionals, $R_1(V;F)$ reduces to a familiar retarded bracket. For local functionals, renormalized time-ordered products are needed to make this expression meaningful at coincident points.

## Retarded products and causal dependence

The word “retarded” is not decorative. If the support of an interaction perturbation lies outside the causal past relevant for $F$, it should not affect $R_V(F)$.

A clean local statement is the algebraic adiabatic principle. Suppose $V$ and $V'$ agree on a causally complete neighborhood of the region that can influence $\operatorname{supp}F$. Then the interacting fields $R_V(F)$ and $R_{V'}(F)$ are identified by a canonical local algebra isomorphism. In practice, this means that the local observable does not remember how the interaction was continued far away.

This is the reason pAQFT does not need a global interaction switched on for all time before local objects can be defined. One can work with compactly supported interactions and compare choices locally.

A useful schematic support rule is

$$
\operatorname{supp} R_n(V_1,\ldots,V_n;F)
\subset
J^-(\operatorname{supp}F)
$$

in the interaction variables, with the precise statement formulated in terms of supports of functional derivatives and causal factorization. The support rule is what distinguishes retarded products from arbitrary multilinear corrections.

## Local interacting algebras

Once relative $S$-matrices are available, the interacting algebra in a region $\mathcal O$ can be generated by elements

$$
\mathcal S_V(F),
\qquad
\operatorname{supp}F\subset \mathcal O,
$$

modulo the local identifications coming from changing the cutoff interaction outside the relevant causal domain. Equivalently, one can generate the algebra by interacting fields $R_V(F)$ with localized $F$.

This gives a perturbative version of a Haag–Kastler net:

$$
\mathcal O\longmapsto \mathcal A_V(\mathcal O).
$$

The construction is formal in the coupling, but the locality statement is exact at the level of formal series. In this sense pAQFT is not merely a diagrammatic expansion of a global transition amplitude. It is a local algebraic construction of interacting observables.

## A scalar example

For a scalar field with interaction

$$
V_g(\phi)
=
\int g(x)\,\frac{\lambda}{4!}\phi(x)^4\,d^dx,
$$

and a linear observable

$$
F_f(\phi)=\int f(x)\phi(x)\,d^dx,
$$

the first-order interacting field has the schematic form

$$
R_{V_g}(F_f)
=
F_f
-
\frac{\lambda}{3!}
\int d^dx\,d^dy\,
 g(x)f(y)\Delta_R(y,x)\phi(x)^3
+O(\lambda^2),
$$

up to sign conventions for $\Delta_R$ and the interaction action. The important feature is not the sign in this schematic display. It is the retarded kernel: the response at the insertion $y$ only receives contributions from interaction points $x$ in the causal past of $y$.

At second and higher orders, products such as $\phi(x)^k$ at coincident points appear. Their definition uses the renormalized time-ordered products studied earlier in the chapter. Thus the interacting field construction combines two facts:

| Ingredient | Job |
|---|---|
| retarded support | enforces causal dependence |
| time-ordered products | organize perturbative insertions |
| distribution extension | repairs ultraviolet singularities |
| finite renormalization | records the remaining local freedom |

## Why this is not the interaction picture

The interaction picture in a textbook usually assumes a fixed free Hilbert space and writes a formal operator

$$
U_I(t_2,t_1)
=
T\exp\!\left(
-i\int_{t_1}^{t_2} H_I(t)\,dt
\right).
$$

That notation is useful in perturbative flat-spacetime calculations, but it hides several issues: domains of unbounded operators, Haag-type obstructions, infrared switching, and ultraviolet singularities of time-ordered products.

The pAQFT construction avoids making the global interaction-picture operator fundamental. It keeps the free algebra as a reference algebra, but interacting fields are defined by relative $S$-matrices and retarded products. This is weaker than a nonperturbative construction, but much stronger than informal interaction-picture manipulation: each coefficient has a precise local meaning.

## This is the most important part of this page

The formal interacting field is local before it is global. The formula

$$
R_V(F)
=
\left.\frac{\hbar}{i}\frac{d}{d\lambda}
\bigl(\mathcal S(V)^{-1}_{\star}\star
\mathcal S(V+\lambda F)\bigr)
\right|_{\lambda=0}
$$

is not a decorative rewrite of the textbook $S$-matrix. It is the construction. It says:

1. choose the free algebra;
2. choose renormalized time-ordered products;
3. form the formal $S$-matrix;
4. compare $V+F$ with $V$;
5. differentiate with respect to $F$;
6. use causal factorization to prove locality and independence from irrelevant cutoff changes.

That sequence is why pAQFT can discuss interacting fields on curved spacetime and in local regions without first solving the nonperturbative Hilbert-space problem.

## Common pitfalls

**Treating $\mathcal S(V)$ as a genuine unitary operator.** In this chapter, $\mathcal S(V)$ is a formal series in an abstract algebra. Unitarity becomes a formal algebraic identity when the time-ordered products satisfy the appropriate reality conditions.

**Forgetting the cutoff interaction.** The local construction starts with compact support. Statements about constant coupling require local algebraic arguments or an adiabatic limit, and the latter can fail for infrared reasons.

**Confusing retarded products with time-ordered products.** Time-ordered products build $\mathcal S$. Retarded products arise from relative $S$-matrices and encode causal response.

**Expecting convergence.** The construction is coefficientwise. A divergent perturbation series can still have well-defined coefficients and well-defined renormalization freedom.

**Ignoring renormalization choices.** The interacting field depends on the chosen renormalized time-ordered products. Different admissible choices are related by finite local renormalizations, not by arbitrary nonlocal changes.

**Assuming gauge theory is automatic.** Gauge theories require BRST or BV machinery to define observables, impose Ward identities, and analyze anomalies. The scalar example does not contain those constraints.

## Relations to other pages

- [Causal Factorization](/rigorous-qft/perturbative-algebraic-qft/causal-factorization/) explains the structural identity that makes relative $S$-matrices local.
- [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) supplies the multilinear maps used in $\mathcal S(F)$.
- [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) explains how different choices of $T_n$ change interacting fields by finite local redefinitions.
- [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) is the curved-spacetime compatibility condition needed for local interacting fields on general backgrounds.
- [Comparison with Feynman Diagrams](/rigorous-qft/perturbative-algebraic-qft/comparison-with-feynman-diagrams/) translates this construction into the diagrammatic language used in ordinary perturbation theory.
- The later BV-BRST and Gauge Theory chapter is where gauge redundancy is incorporated cohomologically.

## Research status

The construction of interacting fields as formal series by relative $S$-matrices and retarded products is established within perturbative algebraic QFT. It is one of the central achievements of the framework.

The main qualifications are important. The construction is perturbative, local, and formal. It does not usually prove convergence. It does not by itself produce a preferred physical state. It does not automatically solve the adiabatic limit. In gauge theories, the construction must be combined with BV-BRST methods and cohomological anomaly analysis.

## Exercises

### Exercise 1: Zeroth order

Show that $R_0(F)=F$ if $\mathcal S(0)=1$ and $\mathcal S(\lambda F)=1+(i\lambda/\hbar)F+O(\lambda^2)$.

<details><summary><strong>Solution</strong></summary>

For $V=0$,

$$
\mathcal S_0(\lambda F)=\mathcal S(\lambda F).
$$

Therefore

$$
R_0(F)
=
\left.\frac{\hbar}{i}\frac{d}{d\lambda}
\mathcal S(\lambda F)\right|_{\lambda=0}
=
\frac{\hbar}{i}\frac{i}{\hbar}F
=F.
$$

</details>

### Exercise 2: First-order structure

Assume the schematic expansion

$$
\mathcal S(V)=1+\frac{i}{\hbar}V+O(V^2),
\qquad
\mathcal S(V+\lambda F)
=1+\frac{i}{\hbar}(V+\lambda F)
+\frac{i^2}{2\hbar^2}T_2(V+\lambda F,V+\lambda F)+\cdots.
$$

Explain why the coefficient of first order in both $V$ and $F$ involves a difference between a time-ordered product and a free product.

<details><summary><strong>Solution</strong></summary>

The inverse $\mathcal S(V)^{-1}_{\star}$ begins as

$$
1-\frac{i}{\hbar}V+O(V^2),
$$

where the multiplication is the free $\star$-product. Multiplying by $\mathcal S(V+\lambda F)$ and keeping the coefficient linear in both $V$ and $F$ gives terms from $T_2(V,F)$ and terms from the product $V\star F$. Their difference is the retarded response kernel in algebraic form. Causal support enters after imposing causal factorization on the time-ordered products.

</details>

### Exercise 3: Why compact support?

Why does the local construction use a compactly supported interaction $V_g$ instead of immediately setting $g=1$ everywhere?

<details><summary><strong>Solution</strong></summary>

Compact support avoids infrared assumptions. The ultraviolet problem is local and can be handled by distribution extension at diagonals. A constant interaction over all spacetime introduces large-distance questions: existence of the adiabatic limit, scattering behavior, vacuum selection, and possible massless infrared effects. pAQFT first constructs local observables with compactly supported interactions and then compares different cutoffs by local isomorphisms.

</details>

### Exercise 4: Causal dependence

Suppose two cutoff interactions $V$ and $V'$ agree in a neighborhood of $J^-(\operatorname{supp}F)\cap\mathcal O$ for a region $\mathcal O$. What should be true of the corresponding local interacting fields in $\mathcal O$?

<details><summary><strong>Solution</strong></summary>

They should define the same local observable after the canonical identification of the local interacting algebras. The reason is retarded dependence: changing the interaction outside the causal region that can influence $F$ cannot change the response measured by $R_V(F)$ inside $\mathcal O$.

</details>

## References

### Standard first pass

- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015), 17–55. [arXiv:1208.1428](https://arxiv.org/abs/1208.1428), [doi:10.1007/978-3-319-09949-1_2](https://doi.org/10.1007/978-3-319-09949-1_2).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).

### Deeper references

- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- K. Fredenhagen and F. Lindner, “Construction of KMS States in Perturbative QFT and Renormalized Hamiltonian Dynamics,” *Communications in Mathematical Physics* **332** (2014), 895–932. [arXiv:1306.6519](https://arxiv.org/abs/1306.6519), [doi:10.1007/s00220-014-2141-7](https://doi.org/10.1007/s00220-014-2141-7).

## Version history

- **2026-07-01:** First polished draft.
