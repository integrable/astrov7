---
title: "Polylogarithms and Symbols Preview"
description: "A practical preview of multiple polylogarithms, symbols, alphabets, canonical differential equations, and the limits of symbol-level information in loop-integral calculations."
sidebar:
  label: "Polylogarithms and Symbols"
  order: 10
level: Advanced
status: "Polished draft"
source: "Goncharov; Brown; Duhr–Gangl–Rhodes; Henn; Panzer; Duhr reviews on symbols and polylogarithmic Feynman integrals"
topics:
  - multiple polylogarithms
  - symbols
  - symbol alphabets
  - canonical differential equations
  - iterated integrals
canonicalTopics:
  - polylogarithms-and-symbols
  - multiple-polylogarithms
  - symbol-map
  - symbol-alphabet
  - canonical-differential-equations
researchStatus:
  established:
    - "Multiple polylogarithms, their symbols, and canonical dlog differential equations are standard tools for many one-loop and multi-loop Feynman integrals."
  active:
    - "Modern amplitude and Feynman-integral calculations continue to refine alphabet reconstruction, function-space choices, branch prescriptions, cluster-algebra structures, and extensions beyond the polylogarithmic class."
---

## Summary

Many loop integrals that appear in perturbative QFT can be written in terms of **multiple polylogarithms**. These functions are iterated integrals built from logarithmic kernels. A typical one-variable definition is

$$
G(a_1,\ldots,a_n;z)
=
\int_0^z \frac{dt}{t-a_1}
G(a_2,\ldots,a_n;t),
\qquad
G(;z)=1,
$$

with the special convention

$$
G(\underbrace{0,\ldots,0}_{n};z)=\frac{1}{n!}\log^n z.
$$

The **symbol** is a compressed record of the ordered logarithmic differentials appearing in such an iterated integral. For example,

$$
\mathcal S(\log x)=x,
\qquad
\mathcal S(\operatorname{Li}_2(x))=-(1-x)\otimes x.
$$

Symbols are useful because they turn complicated functional identities into tensor algebra. They expose the possible logarithmic singularities, organize differential equations, and make many amplitude calculations searchable. But the symbol is not the function. It forgets constants such as $\pi^2$ and $\zeta_n$, it does not by itself fix branch choices, and it does not determine boundary data.

<figure class="doc-figure" style="--figure-width: 60rem; --caption-width: 55rem;">

![Flow from a Feynman integral family to a master basis, canonical differential equation, iterated integrals, and symbol alphabet](/figures/perturbative-qft/polylogarithms-and-symbols-preview.svg)

<figcaption>

In a polylogarithmic sector, a well-chosen master-integral basis often satisfies a canonical $d\log$ differential equation. The alphabet $\mathcal A=\{W_a(x)\}$ supplies the symbol letters. Boundary data, constants, branch choices, and $i0$ prescriptions are extra information beyond the symbol.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/), [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/), [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/), and [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/).

This page is a preview. It explains the language needed to recognize and use polylogarithmic answers, not the full theory of periods, motives, or special-function algorithms.

## Core idea

Polylogarithms are what you get when a loop integral can be reduced to repeated integrations of the form

$$
d\log W(x)=\frac{dW(x)}{W(x)},
$$

where the $W(x)$ are algebraic or rational functions of kinematic variables. In the nicest cases, integration-by-parts reduction and a clever choice of master integrals produce a differential equation

$$
d\vec f(x,\epsilon)
=
\epsilon\,A(x)\vec f(x,\epsilon),
\qquad
A(x)=\sum_{a} A_a\,d\log W_a(x),
$$

where the matrices $A_a$ are constant. Expanding in the dimensional regulator,

$$
\vec f(x,\epsilon)=\sum_{w\ge0}\epsilon^w\vec f^{(w)}(x),
$$

shows that $\vec f^{(w)}$ is obtained by $w$ repeated $d\log$ integrations. The ordered sequence of letters $W_a$ is exactly the information recorded by the symbol.

The mental model is:

$$
\text{canonical } d\log \text{ equation}
\quad\Longrightarrow\quad
\text{iterated integrals}
\quad\Longrightarrow\quad
\text{symbol tensor}.
$$

The arrow does not reverse without extra information. The symbol is the skeleton; the full integral also needs normalization, constants, integration contours, branch choices, and boundary conditions.

## Setup and conventions

We work in dimensional regularization with

$$
d=4-2\epsilon,
$$

and use the loop-measure conventions fixed in [Conventions and Notation](/perturbative-qft/conventions/). The variables $x$ may denote a single dimensionless ratio or a collection of kinematic variables, such as ratios built from Mandelstam invariants and masses.

A **letter** is a nonzero function $W_a(x)$ whose logarithmic differential appears in a canonical differential equation:

$$
d\log W_a(x).
$$

An **alphabet** is the set of such letters,

$$
\mathcal A=\{W_a(x)\}.
$$

Letters are defined only up to transformations that do not change their logarithmic differentials in an essential way. For example, multiplying a letter by a nonzero constant changes $\log W_a$ by a constant and does not change $d\log W_a$. In symbol manipulations, one usually works modulo these harmless constant factors.

A function has **weight** $w$ if it is built from $w$ iterated integrations, up to lower-weight constants. For instance, $\log x$ has weight one, while $\operatorname{Li}_2(x)$ has weight two. In dimensional regularization, a pure canonical basis is often normalized so that the coefficient of $\epsilon^w$ has weight $w$.

## Multiple polylogarithms

Multiple polylogarithms generalize ordinary logarithms and classical polylogarithms. The recursive definition

$$
G(a_1,\ldots,a_n;z)
=
\int_0^z \frac{dt}{t-a_1}G(a_2,\ldots,a_n;t)
$$

shows why they are the natural functions for $d\log$ equations. Since

$$
\frac{dt}{t-a}=d\log(t-a),
$$

each integration adds one logarithmic letter.

The ordinary logarithm is included because

$$
G(0;z)=\log z.
$$

The classical polylogarithms $\operatorname{Li}_n(z)$ are also included. One common convention is

$$
\operatorname{Li}_n(z)=-G(\underbrace{0,\ldots,0}_{n-1},1;z),
$$

up to the usual branch conventions.

The key property for loop integrals is not the name of the function but the differential structure. A weight-$w$ multiple polylogarithm differentiates to a sum of weight-$(w-1)$ functions times logarithmic differentials:

$$
dF^{(w)}=
\sum_a F_a^{(w-1)}\,d\log W_a.
$$

This recursive equation is exactly what a canonical differential equation produces order by order in $\epsilon$.

## Symbols

The symbol map extracts the ordered list of $d\log$ letters from a pure iterated integral. It is defined recursively by

$$
\text{if}\qquad
 dF^{(w)}=
\sum_a F_a^{(w-1)}d\log W_a,
\qquad
\text{then}\qquad
\mathcal S(F^{(w)})=
\sum_a \mathcal S(F_a^{(w-1)})\otimes W_a.
$$

The base case is

$$
\mathcal S(\log W)=W.
$$

This gives the standard examples

$$
\mathcal S(\log x\log y)=x\otimes y+y\otimes x,
$$

and

$$
\mathcal S(\operatorname{Li}_n(x))
=-(1-x)\otimes \underbrace{x\otimes\cdots\otimes x}_{n-1}.
$$

The product rule becomes the shuffle product. For example, the symbol of $\log x\log y$ is the sum of the two possible shuffles of the one-letter symbols $x$ and $y$.

This is why symbols are so good at simplifying identities. A difficult-looking identity among weight-four functions may become a statement that two rank-four tensors agree. The catch is that agreement of symbols implies agreement only up to lower-weight constants and lower-weight functions multiplied by constants.

:::caution[The symbol is not injective]
The symbol of $\pi^2$, $\zeta_3$, and every constant period is zero. More generally, two functions with the same symbol can differ by constants times lower-weight functions. Boundary data and independent checks are not optional bookkeeping; they are part of the answer.
:::

## Alphabets and analytic structure

The letters in a symbol alphabet often encode the possible logarithmic singularities of the integral. If a letter $W_a(x)$ vanishes, then $d\log W_a$ has a pole, so the integral can develop logarithmic behavior near

$$
W_a(x)=0.
$$

This relation is powerful but not automatic in both directions. Landau equations give candidate singular loci. A symbol alphabet gives the letters that actually appear in a chosen function basis. A candidate Landau singularity may not appear in a particular integral because of numerator cancellations, symmetry, a chosen sheet, or a sum over diagrams. Conversely, a compact alphabet may hide algebraic transformations used to rationalize square roots.

A few useful distinctions:

| Object | What it tells you | What it does not tell you |
|---|---|---|
| Landau equations | Candidate singular loci from pinches | Which letters appear in a chosen basis |
| Alphabet $\mathcal A$ | Possible logarithmic letters in the answer | Boundary constants and branch choices |
| Symbol $\mathcal S(F)$ | Ordered iterated-integral skeleton | Terms invisible to the symbol |
| Full function $F$ | Physical value on a chosen sheet | Usually not determined by local data alone |

For scattering amplitudes, the first entries of symbols often obey physical constraints: the first discontinuity should occur in physical channels. Later entries can satisfy additional constraints such as Steinmann-type restrictions in appropriate settings. Those constraints are powerful, but they belong to the full analytic and causal structure of amplitudes, not merely to formal tensor algebra.

## Canonical differential equations

The cleanest entry point to symbols in loop-integral calculations is the canonical differential equation. Suppose integration-by-parts identities reduce an integral family to master integrals $\vec I$. A change of basis

$$
\vec I=B(x,\epsilon)\vec f
$$

may put the differential equation into the form

$$
d\vec f=
\epsilon\sum_a A_a\,d\log W_a\,\vec f.
$$

The solution is an ordered exponential:

$$
\vec f(x,\epsilon)
=
\mathcal P\exp\left[
\epsilon\int_{x_0}^{x}\sum_a A_a\,d\log W_a
\right]
\vec f(x_0,\epsilon).
$$

Expanding the ordered exponential gives iterated integrals. At weight two, for instance, one obtains terms of the schematic form

$$
\int_{x_0}^{x}d\log W_a(x_1)
\int_{x_0}^{x_1}d\log W_b(x_2),
$$

whose symbol contains

$$
W_b\otimes W_a,
$$

with the order determined by the differentiation convention. This reversal is a common source of mistakes: the last letter is the one exposed by the exterior derivative.

In practice, finding a canonical basis is a major part of the problem. Uniform weight, constant leading singularities, simple maximal cuts, and good differential equations are all clues that such a basis may exist. None of them is a theorem that it must exist in the desired form.

## When the polylogarithmic ansatz works

A loop integral is often polylogarithmic when its parameter integrations are **linearly reducible** or when all algebraic square roots can be rationalized so that the remaining integrations are iterated $d\log$ integrations on a genus-zero space. Massless one-loop integrals, many massless two-loop integrals, and many planar amplitude integrals fall into this class after choosing good variables.

A quick diagnostic is the maximal cut. If the maximal cut gives only rational functions, logarithms, or rationalizable square roots, a polylogarithmic answer is plausible. If the maximal cut is an elliptic period, ordinary multiple polylogarithms are not enough. The next page, [Elliptic Integrals Preview](/perturbative-qft/loop-integral-technology/elliptic-integrals-preview/), explains this obstruction.

Polylogarithmic does not mean simple. Weight-four and weight-five polylogarithmic functions can involve large alphabets, complicated algebraic letters, and nontrivial identities. The point is that the function class is still governed by iterated $d\log$ forms, so symbols, coproducts, and differential equations are highly effective.

## Reconstructing functions from symbols

A symbol is often an intermediate object. To reconstruct a function from it, one needs:

1. an integrable tensor satisfying the symbol integrability conditions;
2. a chosen alphabet and branch convention;
3. an ansatz for a function basis, such as logarithms, $\operatorname{Li}_n$, or general $G$ functions;
4. boundary values at a convenient kinematic point;
5. checks against cuts, limits, differential equations, or numerical integration.

The integrability condition is important. Not every tensor

$$
\sum_\alpha c_\alpha W_{\alpha,1}\otimes\cdots\otimes W_{\alpha,w}
$$

is the symbol of a function. For each adjacent pair of entries, the antisymmetric part of the corresponding logarithmic differentials must vanish in the appropriate tensor component. At weight two, this means that

$$
\sum_\alpha c_\alpha\,d\log W_{\alpha,1}\wedge d\log W_{\alpha,2}=0.
$$

For one-variable functions this condition is automatically satisfied because every two-form in one variable vanishes. For multivariable amplitudes it is a real constraint.

## Common pitfalls

**Treating the symbol as the answer.** The symbol misses constants, lower-weight constant multiples, and branch information. It is best viewed as the differential skeleton of a function, not as a numerical prescription.

**Assuming every singular locus is a letter.** Landau analysis gives candidate singularities, while the actual alphabet depends on the integral, basis, numerator, and sheet. Some candidate singularities cancel; some letters appear only after algebraic changes of variables.

**Ignoring the order of entries.** In a symbol, $x\otimes y$ and $y\otimes x$ are different. The last entry is controlled by the final differential, so reconstruction requires careful convention tracking.

**Forgetting integrability.** An arbitrary tensor made from letters need not be the symbol of any function. For multivariable problems, integrability is one of the fastest ways to catch an impossible ansatz.

**Overusing classical polylogarithms.** General multiple polylogarithms are broader than $\log$, $\operatorname{Li}_2$, $\operatorname{Li}_3$, and $\operatorname{Li}_4$. Some symbols cannot be represented compactly using only classical polylogarithms.

**Trying to rationalize the impossible.** Some square roots come from genus-one or higher geometry. If the maximal cut is an elliptic period, the failure of rationalization is a feature of the integral, not a lack of algebraic stamina.

## Relations to other pages

- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) explains the master-integral equations from which many polylogarithmic solutions are built.
- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains why a finite basis of integrals is the input to the symbol and alphabet story.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) supplies discontinuity checks that help fix branch and boundary data.
- [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) explains candidate singular loci; symbol letters are a refined function-level version of this analytic information.
- [Elliptic Integrals Preview](/perturbative-qft/loop-integral-technology/elliptic-integrals-preview/) explains what happens when the polylogarithmic function class is no longer large enough.

## Research status

The use of multiple polylogarithms and symbols in loop-integral and amplitude calculations is established. Canonical $d\log$ differential equations, symbol alphabets, coproduct methods, and boundary-value reconstruction are standard parts of modern perturbative QFT.

Several aspects remain active. For complicated multi-scale integrals, finding the correct alphabet, choosing a good function basis, controlling branch structure, and recognizing when a sector is elliptic or more general can be research problems. Symbols also sit inside a richer mathematical structure involving periods, motives, cluster algebras, coactions, and generalized iterated integrals; this preview only opens the door.

## Exercises

### Exercise 1: Symbol of the dilogarithm

Use

$$
\frac{d}{dx}\operatorname{Li}_2(x)=-\frac{\log(1-x)}{x}
$$

to derive

$$
\mathcal S(\operatorname{Li}_2(x))=-(1-x)\otimes x.
$$

<details>
<summary><strong>Solution</strong></summary>

Write the differential as

$$
d\operatorname{Li}_2(x)=-\log(1-x)d\log x.
$$

The recursive symbol rule says that the last entry is the logarithmic differential exposed by the derivative. Since

$$
\mathcal S(\log(1-x))=1-x,
$$

we get

$$
\mathcal S(\operatorname{Li}_2(x))=-(1-x)\otimes x.
$$

</details>

### Exercise 2: Shuffle product for two logarithms

Show that

$$
\mathcal S(\log x\log y)=x\otimes y+y\otimes x.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
d(\log x\log y)=\log y\,d\log x+\log x\,d\log y.
$$

Using the recursive rule gives

$$
\mathcal S(\log x\log y)
=\mathcal S(\log y)\otimes x+\mathcal S(\log x)\otimes y
=y\otimes x+x\otimes y.
$$

The order of the two terms is immaterial in the sum, so this is

$$
x\otimes y+y\otimes x.
$$

</details>

### Exercise 3: Integrability at weight two

In two variables $x,y$, explain why $x\otimes y$ alone is not the symbol of a function, while

$$
x\otimes y+y\otimes x
$$

is integrable.

<details>
<summary><strong>Solution</strong></summary>

At weight two, integrability requires

$$
\sum_\alpha c_\alpha\,d\log W_{\alpha,1}\wedge d\log W_{\alpha,2}=0.
$$

For $x\otimes y$, this gives

$$
d\log x\wedge d\log y,
$$

which is not zero for independent variables $x$ and $y$. For the symmetric sum,

$$
d\log x\wedge d\log y+d\log y\wedge d\log x=0,
$$

because the wedge product is antisymmetric. This is consistent with the fact that the symmetric symbol is the symbol of $\log x\log y$.

</details>

### Exercise 4: Constants invisible to the symbol

Give two distinct functions with the same symbol.

<details>
<summary><strong>Solution</strong></summary>

A simple example is

$$
F(x)=\operatorname{Li}_2(x),
\qquad
G(x)=\operatorname{Li}_2(x)+\pi^2.
$$

Since constants have zero differential, they have zero symbol. Therefore

$$
\mathcal S(F)=\mathcal S(G).
$$

More generally, a weight-$w$ symbol cannot detect additions of pure weight-$w$ constants such as zeta values, nor can it fully determine lower-weight functions multiplied by constants without additional coproduct data.

</details>

### Exercise 5: Reading a canonical equation

Suppose a one-component pure integral satisfies

$$
df=
\epsilon f\,d\log x,
\qquad
f(1,\epsilon)=1.
$$

Solve for $f(x,\epsilon)$ and identify the symbol of the coefficient of $\epsilon^2$.

<details>
<summary><strong>Solution</strong></summary>

The equation is

$$
d\log f=\epsilon\,d\log x.
$$

Using $f(1,\epsilon)=1$, we obtain

$$
f(x,\epsilon)=x^\epsilon=
\exp(\epsilon\log x).
$$

Expanding,

$$
f(x,\epsilon)=1+
\epsilon\log x+
\frac{\epsilon^2}{2}\log^2 x+\cdots.
$$

The coefficient of $\epsilon^2$ is $\frac12\log^2x$. Since

$$
\mathcal S(\log^2x)=2x\otimes x,
$$

we get

$$
\mathcal S\left(\frac12\log^2x\right)=x\otimes x.
$$

</details>

## References

### Standard first pass

- J. M. Henn, "Multiloop integrals in dimensional regularization made simple," for canonical differential equations and pure integral bases.
- C. Duhr, "Mathematical aspects of scattering amplitudes," for a physicist-friendly introduction to multiple polylogarithms, symbols, and amplitudes.
- V. A. Smirnov, *Feynman Integral Calculus*, for loop-integral technology and analytic methods around Feynman integrals.

### Deeper references

- A. B. Goncharov, "Multiple polylogarithms and mixed Tate motives," for the mathematical structure behind multiple polylogarithms.
- F. Brown, works on multiple zeta values, moduli spaces, and periods, for the deeper period-theoretic setting.
- C. Duhr, H. Gangl, and J. R. Rhodes, "From polygons and symbols to polylogarithmic functions," for symbol technology and reconstruction.
- E. Panzer, "Feynman integrals and hyperlogarithms," for linear reducibility and algorithmic hyperlogarithmic integration.
- S. Weinzierl, review articles and lecture notes on Feynman integrals, multiple polylogarithms, and related computational methods.

## Version history

- **2026-06-12:** Initial standardized page.
