---
title: "Wick's Theorem"
description: "Wick's theorem for free fields: contractions, normal-ordered products, fermion signs, Gaussian factorization, and the bridge from Dyson expansion to Feynman diagrams."
sidebar:
  label: "Wick's Theorem"
  order: 3
---

## Summary

Wick's theorem is the algebraic statement that time-ordered products of free fields can be rewritten as normal-ordered products plus contractions. For a free real scalar field, the basic contraction is

$$
\boxed{
\mathcal C_{ij}
\equiv
\langle0|T\{\phi(x_i)\phi(x_j)\}|0\rangle
=D_F(x_i-x_j).
}
$$

Here $D_F$ is the scalar Feynman propagator in the qft.org convention,

$$
D_F(x-y)=
\int\frac{d^4p}{(2\pi)^4}\,
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

For $n$ scalar fields, Wick's theorem says

$$
\boxed{
T\{\phi_1\cdots\phi_n\}
=
\sum_{P}
\left(\prod_{(i,j)\in P}D_F(x_i-x_j)\right)
:\!\prod_{k\notin P}\phi_k\!:
}
$$

where $\phi_i\equiv\phi(x_i)$ and the sum is over all sets $P$ of disjoint unordered pairs of labels. The empty pairing gives the fully normal-ordered product; complete pairings give vacuum expectation values.

This is the engine that turns the Dyson series into perturbation theory. Dyson expansion produces time-ordered products of free interaction-picture fields. Wick's theorem evaluates those products by reducing them to propagators and normal-ordered remainders. Diagrams are just a disciplined way of labeling these contractions. Coleman emphasizes this bridge by first introducing Wick diagrams before passing to Feynman diagrams; Weinberg derives the general Feynman rules from the same time-ordered pairing logic; Srednicki uses Wick contractions as the short path from path integrals to perturbative rules (Coleman 2019, ch. 8; Weinberg 1995, Vol. I, §6.1; Srednicki 2007, §§9–10).

## Prerequisites

You should know [Normal Ordering](/foundations/canonical-quantization/normal-ordering/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/), and [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/).

## Core idea

Free fields are built from creation and annihilation operators. Normal ordering moves all creation operators to the left. Time ordering moves later operators to the left. These two reorderings are not the same. Wick's theorem says that their difference is completely accounted for by pairwise contractions.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Wick theorem for four scalar fields](/figures/foundations/wick-contraction-pairings.svg)

<figcaption>

For four free scalar fields, Wick's theorem has zero-contraction, one-contraction, and two-contraction terms. The contraction $D_{ij}$ is the Feynman propagator $D_F(x_i-x_j)$ in the qft.org convention.

</figcaption>
</figure>

The theorem is powerful because it reduces a many-operator problem to two-point data. Once the free two-point function is known, every free-field time-ordered correlator is determined.

:::note[Assumptions]
This page states Wick's theorem for free fields with a chosen vacuum and a well-defined creation-annihilation split. Interacting fields do not satisfy Wick's theorem as an operator identity. Perturbation theory works by writing interacting quantities in terms of free interaction-picture fields, applying Wick's theorem there, and then integrating over interaction insertions.
:::

## Creation and annihilation pieces

For the free scalar field,

$$
\phi(x)=\phi_+(x)+\phi_-(x),
$$

where $\phi_+$ contains annihilation operators and $\phi_-$ contains creation operators. In the qft.org convention,

$$
\phi_+(x)=\int d\mu(p)\,a(\mathbf p)e^{-ip\cdot x},
\qquad
\phi_-(x)=\int d\mu(p)\,a^\dagger(\mathbf p)e^{ip\cdot x},
$$

with

$$
d\mu(p)=\frac{d^3p}{(2\pi)^3 2E_{\mathbf p}},
\qquad
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Normal ordering puts the creation pieces to the left of the annihilation pieces:

$$
:\!\phi(x)\phi(y)\!:
=\phi_-(x)\phi_-(y)+\phi_-(x)\phi_+(y)
+\phi_-(y)\phi_+(x)+\phi_+(x)\phi_+(y).
$$

The vacuum expectation value of a normal-ordered product vanishes unless the normal-ordered product is the identity:

$$
\langle0|:\!\phi(x_1)\cdots\phi(x_n)\!:|0\rangle=0
\qquad(n>0).
$$

That is why Wick's theorem immediately produces free vacuum correlators.

## What a contraction is

For the time-ordered Wick theorem, the scalar contraction is the Feynman two-point function:

$$
\boxed{
\mathcal C_{ij}=D_F(x_i-x_j)
=\langle0|T\{\phi_i\phi_j\}|0\rangle.
}
$$

Equivalently,

$$
T\{\phi_i\phi_j\}=:\!\phi_i\phi_j\!:+D_F(x_i-x_j).
$$

This is not the same as saying that the fields are set equal or that a particle literally travels from $x_i$ to $x_j$. A contraction is a c-number two-point function. In ordinary Dyson perturbation theory, that two-point function is the Feynman propagator, not the retarded propagator.

If $x_i^0>x_j^0$, then

$$
T\{\phi_i\phi_j\}=\phi_i\phi_j.
$$

The difference between this product and the normal-ordered product is the commutator contribution needed to move annihilators to the right:

$$
\phi_+(x_i)\phi_-(x_j)
=\phi_-(x_j)\phi_+(x_i)
+[\phi_+(x_i),\phi_-(x_j)].
$$

If $x_j^0>x_i^0$, the opposite ordering gives the opposite time-ordering case. Together they form $D_F(x_i-x_j)$.

## Two fields

The two-field case is

$$
\boxed{
T\{\phi_1\phi_2\}=:\!\phi_1\phi_2\!:+D_{12},
\qquad
D_{12}=D_F(x_1-x_2).
}
$$

Taking the vacuum expectation value gives

$$
\langle0|T\{\phi_1\phi_2\}|0\rangle=D_{12}.
$$

This is the smallest nontrivial example. It says that the two-point function is exactly the contraction.

## Four fields

For four scalar fields, Wick's theorem gives

$$
\begin{aligned}
T\{\phi_1\phi_2\phi_3\phi_4\}
=&:\!\phi_1\phi_2\phi_3\phi_4\!:\\
&+D_{12}:\!\phi_3\phi_4\!:
+D_{13}:\!\phi_2\phi_4\!:
+D_{14}:\!\phi_2\phi_3\!: \\
&+D_{23}:\!\phi_1\phi_4\!:
+D_{24}:\!\phi_1\phi_3\!:
+D_{34}:\!\phi_1\phi_2\!: \\
&+D_{12}D_{34}+D_{13}D_{24}+D_{14}D_{23}.
\end{aligned}
$$

Therefore

$$
\boxed{
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
=D_{12}D_{34}+D_{13}D_{24}+D_{14}D_{23}.
}
$$

The four-point function of a free scalar field is not zero, but it is not connected. It is entirely built from two-point functions.

## Counting contractions

The number of complete pairings of $2n$ scalar fields is

$$
\boxed{(2n-1)!!=\frac{(2n)!}{2^n n!}.}
$$

One way to see this is to choose the partner of field $1$ in $2n-1$ ways, then choose the partner of the smallest remaining label in $2n-3$ ways, and continue:

$$
(2n-1)(2n-3)\cdots3\cdot1=(2n-1)!!.
$$

Thus a free scalar six-point function has $15$ terms, and an eight-point function has $105$ terms. This is exactly the combinatorial explosion that diagrams tame.

## Fermion signs

For fermionic fields, Wick's theorem has the same structure but with graded signs. For Dirac fields the basic contraction is usually written

$$
\boxed{
S_{F,\alpha\beta}(x-y)
=\langle0|T\{\psi_\alpha(x)\bar\psi_\beta(y)\}|0\rangle.
}
$$

In momentum space,

$$
\boxed{
S_F(p)=\frac{i(\slashed p+m)}{p^2-m^2+i\epsilon}.
}
$$

A contraction of two charged Dirac fields of the same type vanishes in a vacuum that preserves the fermion number:

$$
\langle0|T\{\psi_\alpha(x)\psi_\beta(y)\}|0\rangle=0,
\qquad
\langle0|T\{\bar\psi_\alpha(x)\bar\psi_\beta(y)\}|0\rangle=0.
$$

The sign of a fermionic Wick term is the sign of the permutation needed to bring the contracted fermion operators into the chosen pairing order. A useful practical rule is:

```txt
Every closed fermion loop contributes an extra minus sign.
Every exchange of two fermionic operators contributes an extra minus sign.
```

The first rule is a diagrammatic consequence of the second. The detailed spinor-index bookkeeping belongs to the fermion and QED pages, but the origin is already here: Wick's theorem is graded.

## Wick theorem inside Dyson expansion

The interaction-picture Dyson expansion gives

$$
\langle0|T\{\mathcal O_1\cdots\mathcal O_n S\}|0\rangle,
\qquad
S=T\exp\left[-i\int dt\,H_I(t)\right].
$$

Expanding the exponential,

$$
S=1-i\int dt\,H_I(t)+\frac{(-i)^2}{2!}\int dt_1dt_2\,T\{H_I(t_1)H_I(t_2)\}+\cdots.
$$

If $\mathcal H_I$ is a product of free interaction-picture fields, Wick's theorem evaluates each time-ordered product as a sum over contractions. For example, with

$$
\mathcal H_I(x)=\frac{\lambda}{4!}\phi(x)^4,
$$

each occurrence of $\mathcal H_I$ supplies four free fields at one spacetime point. Wick's theorem then says: pair fields in all possible ways. A pair joining two different points gives an internal propagator; a pair joining a vertex to an external insertion gives an external contraction; a pair at the same point gives a tadpole contraction.

This is how the algebra becomes the diagram expansion.

## Operator and path-integral views

Wick's theorem is also the operator version of a Gaussian identity. For the free scalar path integral,

$$
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right].
$$

Functional derivatives of $Z_0[J]$ at $J=0$ generate all pairings. Because the exponent is quadratic in $J$, every nonzero derivative at $J=0$ is built by pairing derivatives two by two. Thus

$$
\langle0|T\{\phi_1\cdots\phi_{2n}\}|0\rangle
=\sum_{\text{complete pairings}}\prod_{(i,j)}D_{ij}.
$$

This gives the useful three-way translation:

```txt
operator language:       free fields are oscillator operators;
path-integral language:  the free action is quadratic;
structural language:     higher connected correlators vanish.
```

## Common pitfalls

**Using Wick's theorem on exact interacting fields.** Wick's theorem is exact for free fields and Gaussian states. In perturbation theory, it is applied to interaction-picture fields.

**Forgetting the normal-ordered remainder.** Wick's theorem is an operator identity, not just a vacuum expectation value. Unless one takes a vacuum expectation value, partially contracted normal-ordered terms remain.

**Using the retarded propagator as a contraction.** Ordinary time-ordered perturbation theory uses the Feynman propagator. Retarded and advanced propagators describe response functions, not Dyson-Wick contractions.

**Dropping fermion signs.** Fermionic Wick theorem is graded. A missing minus sign from a fermion permutation can change the answer completely.

**Treating coincident contractions casually.** Quantities such as $D_F(0)$ are ultraviolet singular in continuum QFT. Normal ordering subtracts some free-field vacuum pieces, but it is not a substitute for renormalization.

## Relation to other topics

- [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) defines the ordering operation that Wick's theorem uses.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) is the scalar contraction in time-ordered perturbation theory.
- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) explains why free higher connected correlators vanish.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) gives the path-integral version of the same Gaussian pairing rule.
- [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) supplies the time-ordered products to which Wick's theorem is applied.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) turns Wick contractions into graphical bookkeeping.

## Research status

Wick's theorem is textbook-standard for free fields and Gaussian states. Its use in perturbative QFT is formal until a regulator and renormalization prescription are supplied. In algebraic and constructive QFT, related statements are phrased in terms of quasi-free states and their correlation functions.

## Exercises

### Exercise 1: Two-field Wick theorem

Show that

$$
T\{\phi_1\phi_2\}=:\!\phi_1\phi_2\!:+D_{12}
$$

for a free scalar field.

<details>
<summary><strong>Solution</strong></summary>

Assume first that $x_1^0>x_2^0$. Then

$$
T\{\phi_1\phi_2\}=\phi_1\phi_2.
$$

Write $\phi=\phi_++\phi_-$, where $\phi_+$ annihilates the vacuum and $\phi_-$ creates. The only term not already normally ordered is $\phi_+(x_1)\phi_-(x_2)$. Move it to normal order:

$$
\phi_+(x_1)\phi_-(x_2)
=\phi_-(x_2)\phi_+(x_1)+[\phi_+(x_1),\phi_-(x_2)].
$$

The commutator term is the contraction for this time ordering. The opposite time ordering gives the other step-function piece. Combining the two cases gives $D_{12}$.

</details>

### Exercise 2: Four-field vacuum expectation value

Compute

$$
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
$$

for a free real scalar field.

<details>
<summary><strong>Solution</strong></summary>

Only complete contractions survive in the vacuum expectation value. The complete pairings are

$$
(12)(34),\qquad(13)(24),\qquad(14)(23).
$$

Therefore

$$
\boxed{
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
=D_{12}D_{34}+D_{13}D_{24}+D_{14}D_{23}.
}
$$

</details>

### Exercise 3: Count complete pairings

Prove that the number of complete pairings of $2n$ objects is

$$
(2n-1)!!.
$$

<details>
<summary><strong>Solution</strong></summary>

Choose the partner of object $1$: there are $2n-1$ choices. Then choose the partner of the smallest remaining unpaired object: there are $2n-3$ choices. Continuing gives

$$
(2n-1)(2n-3)\cdots3\cdot1=(2n-1)!!.
$$

Equivalently,

$$
(2n-1)!!=\frac{(2n)!}{2^n n!},
$$

because an ordering of all $2n$ objects overcounts by a factor $2$ for each pair and by $n!$ for the order of the pairs.

</details>

### Exercise 4: The quartic vertex combinatoric

In scalar $\phi^4$ theory with

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

show that the first-order connected contribution to the four-point function has local vertex factor $-i\lambda$.

<details>
<summary><strong>Solution</strong></summary>

At first order,

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle.
$$

The connected tree-level contribution pairs each external field with one of the four fields at $z$. There are $4!$ ways to do this. These $4!$ Wick contractions cancel the $1/4!$ in the interaction. The remaining vertex factor is

$$
-i\lambda.
$$

The corresponding coordinate-space contribution is

$$
(-i\lambda)\int d^4z\,D_F(x_1-z)D_F(x_2-z)D_F(x_3-z)D_F(x_4-z).
$$

</details>

### Exercise 5: Fermion minus sign

Let $\psi_1,\bar\psi_2,\psi_3,\bar\psi_4$ be free Dirac fields. Explain why the pairing $(1,4)(3,2)$ carries a relative minus sign compared with the pairing $(1,2)(3,4)$.

<details>
<summary><strong>Solution</strong></summary>

Fermion contractions inherit signs from permutations of fermionic operators. The pairing $(1,2)(3,4)$ contracts adjacent fermion-antifermion pairs in the displayed order. The pairing $(1,4)(3,2)$ requires moving fermionic operators past one another to bring the contracted pairs together. That odd fermionic permutation contributes a minus sign. The exact sign convention depends on the chosen canonical ordering of spinor contractions, but the principle is invariant: every exchange of two fermionic operators contributes $-1$.

</details>

### Exercise 6: Wick theorem from the free source functional

Use

$$
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right]
$$

to derive the free four-point function.

<details>
<summary><strong>Solution</strong></summary>

The four-point function is obtained by four functional derivatives with respect to $J(x_1),\ldots,J(x_4)$ and then setting $J=0$. Since the exponent is quadratic in $J$, nonzero terms arise only by grouping the four derivatives into two pairs. The three pairings are

$$
(12)(34),\qquad(13)(24),\qquad(14)(23),
$$

so

$$
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
=D_{12}D_{34}+D_{13}D_{24}+D_{14}D_{23}.
$$

This is the path-integral Gaussian form of Wick's theorem.

</details>

## References

- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), 268–272.
- Sidney Coleman, *Lectures on Quantum Field Theory*, ch. 8, for Wick diagrams and the combinatorics of perturbation theory.
- Mark Srednicki, *Quantum Field Theory*, §§9–10 and §19, for a compact path-integral and perturbative treatment of Wick contractions and diagrams.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for the general covariant derivation of the Feynman rules from Wick theorem.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.2 and I.7, for an intuition-first path-integral and diagrammatic introduction.
