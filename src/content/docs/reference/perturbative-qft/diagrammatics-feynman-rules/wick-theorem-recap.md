---
title: "Wick Theorem Recap"
description: "A focused recap of Wick's theorem for perturbative QFT, emphasizing contractions, pairings, signs, symmetry factors, and how the theorem becomes diagrammatic rules."
sidebar:
  label: "Wick Theorem Recap"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10 and §19; Coleman 2019, ch. 8; Weinberg 1995, Vol. I, §6.1; Schwartz 2014, ch. 7 and app. 7.A; Zinn-Justin 2021, ch. 7"
topics:
  - Wick theorem
  - contractions
  - Feynman diagrams
  - scalar perturbation theory
  - fermion signs
  - symmetry factors
canonicalTopics:
  - wick-theorem-recap
  - contractions-and-pairings
  - dyson-wick-diagrammatics
researchStatus:
  established:
    - "Wick's theorem for free Gaussian fields, its contraction formula, and its use in perturbative diagrammatics are textbook-standard."
  active:
    - "The theorem is a perturbative Gaussian tool; questions about convergence, non-Gaussian vacua, nonperturbative definitions, and real-time interacting dynamics belong to later pages."
---

## Summary

Wick's theorem is the combinatorial bridge from free-field operator products to Feynman diagrams. For a free real scalar field with

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle,
$$

the vacuum expectation value of an even time-ordered product is

$$
\langle0|T\{\phi(x_1)\cdots\phi(x_{2r})\}|0\rangle
=
\sum_{P}\prod_{\{a,b\}\in P}D_F(x_a-x_b),
$$

where $P$ runs over all complete pairings of the labels $1,\ldots,2r$. Odd vacuum correlators vanish for a free scalar field with zero one-point function.

The operator version is only slightly richer: instead of pairing every field, one may pair some fields and leave the rest normal ordered,

$$
T\{\phi_1\cdots\phi_n\}
=
\sum_{P}
\left(\prod_{\{a,b\}\in P}D_F(x_a-x_b)\right)
:\!\prod_{c\notin P}\phi_c\!:.
$$

Here $\phi_a$ is shorthand for $\phi(x_a)$, and $P$ runs over all partial pairings. This page recalls what the formula means, how to count pairings, how fermion signs enter, and why the theorem is the source code behind perturbative diagrams.

## Prerequisites

You should know the qft.org [Conventions and Notation](/perturbative-qft/conventions/), the Foundations page [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), the [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), and the [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/). The previous page, [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), explains why Wick's theorem appears inside perturbation theory.

## Core idea

Wick's theorem is the statement that a free QFT is Gaussian. Gaussian objects are completely determined by their two-point function. In QFT language, that two-point function is the free Feynman propagator, and every higher free time-ordered correlator is a sum over products of propagators.

The perturbative use is direct:

1. expand the interaction with the Dyson series or source functional;
2. obtain a free-theory time-ordered product with many fields;
3. use Wick's theorem to replace products of free fields by sums of contractions;
4. draw each contraction as a line and each interaction insertion as a vertex;
5. divide by any remaining overcounting not already canceled by factorials.

So diagrams are not a new rule of nature. They are Wick's theorem with better typography.

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with the mostly-minus qft.org convention. Plane waves are written as $e^{-ip\cdot x}$, and the free scalar propagator is

$$
D_F(x-y)
=
\int\frac{d^4p}{(2\pi)^4}\,
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

Unless stated otherwise, fields in this page are interaction-picture free fields. Normal ordering $:\!\cdots\!:$ means that all creation operators are moved to the left of all annihilation operators, so

$$
\langle0|:\!\mathcal O(\phi)\!:|0\rangle=0
$$

for any nonconstant normally ordered product of free scalar fields.

For a free scalar field, the contraction of two fields is the c-number

$$
C_{ab}
\equiv
T\{\phi(x_a)\phi(x_b)\}
-:\!\phi(x_a)\phi(x_b)\!:
=
D_F(x_a-x_b).
$$

The symbol $C_{ab}$ is only a local abbreviation in this page; it is not a new qft.org convention.

## Statement for scalar fields

Let $\phi_a\equiv\phi(x_a)$. A **partial pairing** $P$ is a set of disjoint unordered pairs $\{a,b\}$ chosen from the labels $1,\ldots,n$. The labels not appearing in any pair are left unpaired. Wick's theorem for a free real scalar field can be written as

$$
T\{\phi_1\cdots\phi_n\}
=
\sum_{P}
\left(\prod_{\{a,b\}\in P}D_F(x_a-x_b)\right)
:\!\prod_{c\notin P}\phi_c\!:.
$$

The empty pairing is included. It gives the fully normal-ordered term. Complete pairings give pure c-number terms. Taking the vacuum expectation value kills all terms with unpaired fields, leaving only complete pairings.

For two fields,

$$
T\{\phi_1\phi_2\}
=:\!\phi_1\phi_2\!:+D_F(x_1-x_2).
$$

For three fields,

$$
\begin{aligned}
T\{\phi_1\phi_2\phi_3\}
&=:\!\phi_1\phi_2\phi_3\!:
+D_F(x_1-x_2):\!\phi_3\!:\\
&\quad+D_F(x_1-x_3):\!\phi_2\!:
+D_F(x_2-x_3):\!\phi_1\!:.
\end{aligned}
$$

Its vacuum expectation value vanishes because every term has at least one unpaired normal-ordered field.

For four fields, the vacuum theorem gives

$$
\begin{aligned}
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
&=D_F(x_1-x_2)D_F(x_3-x_4)\\
&\quad+D_F(x_1-x_3)D_F(x_2-x_4)\\
&\quad+D_F(x_1-x_4)D_F(x_2-x_3).
\end{aligned}
$$

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 48rem;">

![The three Wick pairings of four scalar insertions](/figures/perturbative-qft/wick-four-point-pairings.svg)

<figcaption>

The free scalar four-point function is the sum over the three complete pairings of four insertions: $(12)(34)$, $(13)(24)$, and $(14)(23)$. In an interacting calculation, the same pairing logic applies after inserting interaction vertices.

</figcaption>
</figure>

## Counting pairings

The number of complete pairings of $2r$ labeled scalar fields is

$$
(2r-1)!!=\frac{(2r)!}{2^r r!}.
$$

One quick derivation is to pair label $1$ with any of the other $2r-1$ labels, then pair the remaining $2r-2$ labels recursively. This gives

$$
(2r-1)(2r-3)\cdots3\cdot1.
$$

This counting is the origin of many symmetry factors. In a Lagrangian with

$$
\mathcal L_{\mathrm{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the factor $1/4!$ is not decorative. It cancels the $4!$ ways of attaching four distinguishable external scalar insertions to the four identical fields at a quartic vertex. In other graphs, such as tadpoles or bubbles, some relabelings remain invisible in the drawn graph, and the graph keeps a nontrivial symmetry factor.

## Wick theorem inside perturbation theory

For normalized interacting correlators, the operator formula is

$$
\langle T\mathcal O\rangle
=
\frac{
\langle0|T\{\mathcal O S\}|0\rangle_0
}{
\langle0|S|0\rangle_0
},
\qquad
S=T\exp\left[-i\int dt\,H_I(t)\right].
$$

Expanding $S$ produces time-ordered products of free fields. Wick's theorem evaluates those products. The result is a sum of terms with three kinds of pieces:

| Wick-theorem piece | Diagrammatic piece | Example in scalar theory |
|---|---|---|
| contraction between two fields | line | $D_F(x-y)$ |
| interaction insertion | vertex | $-i\lambda\int d^4z$ for $\phi^4$ |
| unpaired external insertion in operator theorem | external operator leg | propagator from $x_i$ to a vertex |

The denominator removes vacuum bubbles disconnected from the inserted operators. Diagrammatically, any vacuum component that factors from the numerator is reproduced by $\langle0|S|0\rangle_0$ and cancels in the normalized correlator.

## Source-functional viewpoint

The same theorem is encoded by the free generating functional. With the qft.org convention that $D_F$ includes the factor of $i$,

$$
Z_0[J]
=
\left\langle0\left|T\exp\left(i\int d^4x\,J(x)\phi(x)\right)\right|0\right\rangle
=
\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right].
$$

Taking source derivatives reproduces the pairing formula:

$$
\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle
=
\left.
\frac{1}{i^n}
\frac{\delta^n Z_0[J]}{\delta J(x_1)\cdots\delta J(x_n)}
\right|_{J=0}.
$$

This is often the cleanest way to remember Wick's theorem. The exponential is quadratic in $J$, so every nonzero derivative must hit $J$'s in pairs.

## Fermions and signs

For fermions, the theorem is structurally the same but algebraically less forgiving. The fields anticommute, so every contraction pattern comes with the sign of the permutation needed to bring the contracted fermionic fields next to each other in a fixed convention.

For Dirac fields, a basic contraction is

$$
\langle0|T\{\psi_\alpha(x)\overline\psi_\beta(y)\}|0\rangle
=(S_F)_{\alpha\beta}(x-y),
$$

with momentum-space propagator

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon},
\qquad
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

Two practical rules survive into Feynman diagrams:

1. each closed fermion loop contributes an extra factor of $-1$;
2. exchanging external fermions changes the sign according to their ordering.

These are not independent magic signs. They are the signs of Wick's theorem for anticommuting fields.

## Checks

A good first check is the free four-point function. It must be symmetric under exchange of any two scalar insertions, and the three-pairing formula above is manifestly symmetric after summing all pairings.

A second check is the vanishing of odd scalar vacuum correlators. If the free vacuum has $\langle0|\phi|0\rangle=0$, an odd number of fields cannot be completely paired.

A third check is the contact term in $\phi^4$ theory. At first order,

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle_0
$$

has $4!$ contractions that connect the four external fields to the four fields at $z$. The factor $4!$ cancels the $1/4!$, leaving the vertex factor $-i\lambda$ attached to four propagators.

## Common pitfalls

**Thinking Wick's theorem is true in any state.** Wick factorization is true for Gaussian states and free vacua. Interacting vacua do not generally factor into two-point functions, which is why perturbation theory expands around a free vacuum and treats interactions order by order.

**Forgetting the normal-ordered terms.** Vacuum expectation values only keep complete pairings, but the operator theorem includes partial pairings and normal-ordered leftovers. Those leftovers matter when the time-ordered product is inserted into a larger expression.

**Dropping fermion signs.** Fermionic contractions are not just scalar contractions with arrows. The signs come from permuting anticommuting operators, and closed fermion loops remember that bookkeeping.

**Counting diagrams instead of Wick contractions.** A clean drawing may represent many labeled contractions. Symmetry factors are the quotient between the Wick-contraction count and the number of times the same unlabeled diagram has been drawn.

**Confusing vacuum bubbles with zero.** Vacuum bubbles cancel from normalized ordinary correlators, but they are not intrinsically meaningless. They contribute to vacuum energy and to effective actions when those quantities are being studied.

## Relations to other pages

- [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/) explains why Wick's theorem is applied to Dyson-expanded interacting correlators.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) Fourier transforms the contraction and vertex rules into propagators, momentum-conserving delta functions, and loop integrals.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) introduces the diagrammatic notation that this page now uses for calculations.
- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) explains how disconnected pieces are organized by logarithms of generating functionals.
- [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) gives the Grassmann version of the same Gaussian logic.

## Research status

This page is textbook-standard perturbative QFT. The theorem itself is a precise statement about free Gaussian fields, while its use inside interacting QFT is normally as a formal perturbative expansion. The main subtleties beyond this page are convergence and summability of perturbation theory, renormalization of singular products, gauge fixing and BRST structure, and nonperturbative definitions of interacting theories.

## Exercises

### Exercise 1: Count six-field pairings

How many complete Wick pairings are there for six labeled scalar fields? Write the answer both as a double factorial and as an ordinary integer.

<details>
<summary><strong>Solution</strong></summary>

For $2r=6$, we have $r=3$. The number of complete pairings is

$$
(2r-1)!!=5!!=5\cdot3\cdot1=15.
$$

Equivalently,

$$
\frac{6!}{2^3 3!}=\frac{720}{8\cdot6}=15.
$$

</details>

### Exercise 2: Derive the free four-point function

Use the operator form of Wick's theorem to derive

$$
\begin{aligned}
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
&=D_F(x_1-x_2)D_F(x_3-x_4)\\
&\quad+D_F(x_1-x_3)D_F(x_2-x_4)\\
&\quad+D_F(x_1-x_4)D_F(x_2-x_3).
\end{aligned}
$$

<details>
<summary><strong>Solution</strong></summary>

The operator theorem sums over all partial pairings. After taking the vacuum expectation value, every term with at least one unpaired normal-ordered field vanishes. Therefore only complete pairings remain.

There are three complete pairings of four labels:

$$
(12)(34),\qquad (13)(24),\qquad (14)(23).
$$

Replacing each pair $(ab)$ by $D_F(x_a-x_b)$ gives the stated formula.

</details>

### Exercise 3: Quartic contact counting

In $\phi^4$ theory, show that the connected first-order four-point contact term has coefficient $-i\lambda$, not $-i\lambda/4!$.

<details>
<summary><strong>Solution</strong></summary>

At first order, the relevant term is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle_0.
$$

For the connected contact contribution, each external field must contract with one of the four fields at $z$. There are $4!$ assignments. Thus

$$
\frac{-i\lambda}{4!}\times4!=-i\lambda.
$$

The position-space connected term is therefore

$$
(-i\lambda)\int d^4z\,
D_F(x_1-z)D_F(x_2-z)D_F(x_3-z)D_F(x_4-z).
$$

</details>

### Exercise 4: Tadpole coefficient

In $\phi^4$ theory, compute the coefficient of the first-order tadpole correction to the two-point function.

<details>
<summary><strong>Solution</strong></summary>

The first-order term is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle_0.
$$

For the tadpole contribution, choose one of the four fields at $z$ to contract with $\phi(x)$ and one of the remaining three to contract with $\phi(y)$. The remaining two fields at $z$ contract with each other. This gives $4\cdot3=12$ contractions, so

$$
\frac{-i\lambda}{4!}\times12=\frac{-i\lambda}{2}.
$$

Hence

$$
G_2^{\mathrm{tad}}(x,y)
=
\frac{-i\lambda}{2}
\int d^4z\,D_F(x-z)D_F(y-z)D_F(0).
$$

</details>

### Exercise 5: Gaussian source check

Starting from

$$
Z_0[J]=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
$$

show why the three-point function vanishes at $J=0$.

<details>
<summary><strong>Solution</strong></summary>

The exponent is quadratic in $J$. Each functional derivative removes one source. Three derivatives can never remove sources in complete pairs: after two derivatives have produced one propagator, one derivative remains and leaves a factor proportional to $J$. Setting $J=0$ kills that term.

Equivalently, Wick's theorem says a nonzero free vacuum correlator needs a complete pairing of all insertions. Three labels cannot be completely paired.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§9–10 and §19, for path-integral perturbation theory, Feynman rules, and all-order perturbation theory.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 8, for Wick diagrams and the transition from Dyson's formula to diagrammatic perturbation theory.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 7 and app. 7.A, for Feynman rules and a concise Wick-theorem review.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §6.1, for a general derivation of Feynman rules from Wick contractions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 7, for the generating-functional and diagrammatic viewpoint.
- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), 268–272, for the original theorem in the S-matrix context.

## Version history

- **2026-06-11:** Initial standardized page.
