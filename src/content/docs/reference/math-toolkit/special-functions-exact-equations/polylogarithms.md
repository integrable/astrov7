---
title: "Polylogarithms"
description: "Explains logarithms, classical polylogarithms, multiple polylogarithms, iterated integrals, symbols, branch cuts, discontinuities, special constants, and why polylogarithms are the default language of many perturbative QFT amplitudes."
sidebar:
  label: "Polylogarithms"
  order: 7
level: Advanced
status: "Polished draft"
source: "Standard references on polylogarithms, iterated integrals, multiple zeta values, symbols, monodromy, Feynman integrals, and scattering amplitudes, including Lewin, Goncharov, Chen, Brown, Remiddi–Vermaseren, Duhr, Dixon, Henn, Weinzierl, NIST DLMF, Whittaker–Watson, Ahlfors, Smirnov, and modern amplitude and Feynman-integral literature."
topics:
  - polylogarithm
  - dilogarithm
  - multiple polylogarithm
  - iterated integral
  - symbol
  - harmonic polylogarithm
  - multiple zeta value
  - branch cut
  - discontinuity
  - Feynman integral
canonicalTopics:
  - polylogarithm
  - dilogarithm
  - multiple-polylogarithm
  - iterated-integral
  - symbol
  - harmonic-polylogarithm
  - multiple-zeta-value
  - branch-cut
  - discontinuity
  - feynman-integral
researchStatus:
  established:
    - "Classical polylogarithms are analytic continuations of the series Li_n(z)=sum_{m>=1} z^m/m^n, with differential relation z d Li_n/dz = Li_{n-1}."
    - "Multiple polylogarithms are iterated integrals of logarithmic differential forms and provide a natural language for many one-loop and multiloop Feynman integrals."
  active:
    - "Modern work develops symbol alphabets, cluster-algebra structures, single-valued polylogarithms, elliptic polylogarithms, canonical differential equations, amplitude bootstrap methods, and transitions from polylogarithmic to elliptic and higher-genus integrals."
---

## Summary

Polylogarithms are what happen when logarithms are integrated again and again. The classical polylogarithm is initially defined by the convergent series

$$
\operatorname{Li}_n(z)=\sum_{m=1}^{\infty}{z^m\over m^n},
\qquad |z|<1,
$$

and then by analytic continuation. The first case is just a logarithm:

$$
\operatorname{Li}_1(z)=-\log(1-z).
$$

The differential recursion is

$$
z{d\over dz}\operatorname{Li}_n(z)=\operatorname{Li}_{n-1}(z),
$$

so each higher polylogarithm is an iterated integral built from the kernels $dz/z$ and $dz/(1-z)$.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Diagram showing logarithms, classical polylogarithms, iterated integrals, symbols and coproducts, branch cuts, constants, and QFT uses.](/figures/math-toolkit/polylog-iterated-integral-flow.svg)

<figcaption>

Polylogarithms organize repeated integration of $d\log$ kernels. Classical polylogarithms are the simplest tower; multiple polylogarithms generalize them to words in an alphabet of singular points. Symbols and coproducts retain branch and differential data, while constants such as $\zeta_n$ and multiple zeta values appear as boundary data. QFT uses this language for loop integrals, discontinuities, amplitude bootstrap calculations, and OPE data.

</figcaption>
</figure>

In perturbative QFT, polylogarithms are the default special functions of analytic loop calculations. Logs describe one integration. Dilogs describe two. Higher and multiple polylogs describe iterated integrations over rational kernels. They know about thresholds, branch cuts, discontinuities, and analytic continuation, which is exactly what Feynman integrals ask for.

The catch is that polylogarithms are not universal. Once the geometry of the integral contains an elliptic curve or worse, ordinary multiple polylogarithms stop being enough. That boundary is one of the most useful diagnostic lines in modern amplitudes.

## Prerequisites

You should know [Logarithms and branch cuts from Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Dispersion Relations](/math-toolkit/complex-analysis/dispersion-relations/), [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/), [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/), and [Elliptic Functions and Integrals](/math-toolkit/special-functions-exact-equations/elliptic-functions-and-integrals/).

This page uses the principal branch of the logarithm unless otherwise stated. For $\operatorname{Li}_n(z)$, the conventional branch cut is along $z\in[1,\infty)$. QFT applications often specify boundary values by replacing an invariant with $s+i0$ or $s-i0$.

## Classical polylogarithms

The classical polylogarithm is

$$
\operatorname{Li}_n(z)=\sum_{m=1}^{\infty}{z^m\over m^n},
\qquad |z|<1.
$$

For $n=0$, one often defines

$$
\operatorname{Li}_0(z)={z\over 1-z},
$$

so that the recursion

$$
z{d\over dz}\operatorname{Li}_n(z)=\operatorname{Li}_{n-1}(z)
$$

also holds for $n=1$. The most important cases are

$$
\operatorname{Li}_1(z)=-\log(1-z),
$$

$$
\operatorname{Li}_2(z)=-\int_0^z {dt\over t}\log(1-t),
$$

and

$$
\operatorname{Li}_n(z)=\int_0^z {dt\over t}\operatorname{Li}_{n-1}(t),
\qquad n\ge2.
$$

The integer $n$ is called the weight. The logarithm has weight one, the dilogarithm has weight two, and so on. In many perturbative calculations, the maximal weight is correlated with the number of integrations, loop order, or differential-equation complexity, though real-world integrals delight in exceptions.

At $z=1$, the values are Riemann zeta values:

$$
\operatorname{Li}_n(1)=\zeta(n),
\qquad n>1.
$$

At $z=-1$,

$$
\operatorname{Li}_n(-1)=-(1-2^{1-n})\zeta(n),
\qquad n>1.
$$

These constants often appear as boundary values of Feynman integrals.

## The dilogarithm

The dilogarithm is the first genuinely new polylogarithm:

$$
\operatorname{Li}_2(z)=-\int_0^z {\log(1-t)\over t}\,dt.
$$

It appears everywhere: one-loop box integrals, phase-space integrals, simple Wilson-line integrals, two-dimensional conformal maps, thermal sums, and threshold functions.

One central identity is the Euler relation

$$
\operatorname{Li}_2(z)+\operatorname{Li}_2(1-z)
={\pi^2\over6}-\log z\log(1-z),
$$

valid first for $0<z<1$ and then by analytic continuation with branches specified. Another useful relation is

$$
\operatorname{Li}_2(z)+\operatorname{Li}_2\left({1\over z}\right)
=-{\pi^2\over6}-{1\over2}\log^2(-z),
$$

for $z$ away from the positive real axis, with branch conventions understood.

These identities are not merely algebraic tricks. They let one rewrite an answer in a form adapted to a physical region. A representation that is real in the Euclidean region may be a terrible representation in a scattering region unless the logarithmic branches are made explicit.

## Branch cuts and discontinuities

With the principal branch, $\operatorname{Li}_n(z)$ has a branch cut along

$$
z\in[1,\infty).
$$

For $x>1$, define the discontinuity by

$$
\operatorname{Disc}\,f(x)=f(x+i0)-f(x-i0).
$$

Then

$$
\operatorname{Disc}\,\operatorname{Li}_n(x)
=2\pi i\,{\log^{n-1}x\over (n-1)!},
\qquad x>1.
$$

For $n=1$, this says

$$
\operatorname{Disc}\big[-\log(1-x)\big]=2\pi i.
$$

For $n=2$,

$$
\operatorname{Disc}\,\operatorname{Li}_2(x)=2\pi i\log x.
$$

In QFT, this is the analytic shadow of unitarity cuts. A discontinuity across a branch cut is not a nuisance; it is physical information. In many amplitude calculations, the discontinuities are easier to understand than the full function, and one reconstructs the function from its differential or symbol data plus boundary constants.

## Multiple polylogarithms as iterated integrals

Classical polylogarithms use only the singular points $0$, $1$, and $\infty$. General Feynman integrals often involve more singular points. The natural generalization is the iterated integral

$$
G(a_1,\ldots,a_r;z)
=\int_0^z {dt\over t-a_1}G(a_2,\ldots,a_r;t),
$$

with

$$
G(;z)=1.
$$

For repeated zeros, one defines

$$
G(\underbrace{0,\ldots,0}_{r};z)={1\over r!}\log^r z.
$$

The list $a_1,\ldots,a_r$ is a word in an alphabet of letters. The letters are singular points, and the kernels are logarithmic differential forms:

$$
{dt\over t-a}=d\log(t-a).
$$

With this convention,

$$
\operatorname{Li}_n(z)=-G(\underbrace{0,\ldots,0}_{n-1},1;z).
$$

For example,

$$
G(1;z)=\log(1-z),
$$

so

$$
\operatorname{Li}_1(z)=-G(1;z).
$$

Multiple polylogarithms can also be written as nested sums. A common convention is

$$
\operatorname{Li}_{n_1,\ldots,n_r}(z_1,\ldots,z_r)
=\sum_{0<k_1<\cdots<k_r}
{z_1^{k_1}\cdots z_r^{k_r}\over k_1^{n_1}\cdots k_r^{n_r}},
$$

inside its convergence domain, then analytically continued. Different order conventions exist, so always check the definition before comparing formulae.

## Shuffle algebra

Iterated integrals obey a shuffle product. If $u$ and $v$ are words, then

$$
G(u;z)G(v;z)=\sum_{w\in \operatorname{Sh}(u,v)}G(w;z),
$$

where $\operatorname{Sh}(u,v)$ denotes all ways of interleaving the letters of $u$ and $v$ while preserving the order inside each word.

For instance,

$$
G(a;z)G(b;z)=G(a,b;z)+G(b,a;z).
$$

The shuffle algebra is why products of lower-weight functions can be systematically separated from genuinely new higher-weight functions. In amplitude calculations, this is part of the bookkeeping that turns giant expressions into structured function spaces.

There is also a stuffle algebra for nested sums. The tension between shuffle and stuffle identities produces relations among special constants, especially multiple zeta values.

## Symbols: the differential skeleton

The symbol is a compressed way to record the iterated $d\log$ structure of a polylogarithmic function. It forgets constants such as $\pi^2$ and $\zeta_3$, but remembers enough to track branch points, discontinuities, and differential equations.

A useful rule is

$$
dF=\sum_i F_i\,d\log R_i
\quad\Longrightarrow\quad
\mathcal S(F)=\sum_i \mathcal S(F_i)\otimes R_i.
$$

For the logarithm,

$$
\mathcal S(\log R)=R.
$$

With common conventions,

$$
\mathcal S(\operatorname{Li}_2(z))=-(1-z)\otimes z,
$$

and more generally

$$
\mathcal S(\operatorname{Li}_n(z))=-(1-z)\otimes \underbrace{z\otimes\cdots\otimes z}_{n-1}.
$$

The symbol is not the function. It cannot see additive constants such as $\pi^2$, and it cannot by itself impose all branch choices. Still, it is extraordinarily useful. In modern amplitude bootstrap calculations, one often guesses a symbol alphabet, imposes integrability and physical constraints, then fixes constants by limits or boundary values.

## Weight, transcendentality, and constants

Polylogarithmic functions come with a weight grading. Roughly,

$$
\text{weight}(\log)=1,
\qquad
\text{weight}(\operatorname{Li}_n)=n,
\qquad
\text{weight}(\zeta_n)=n.
$$

Products add weights:

$$
\text{weight}(\zeta_2\log z)=3.
$$

This grading is not a law of nature, but it is extremely useful. Certain theories and observables have uniform transcendental weight, meaning all terms at a given loop order have the same weight. Maximally supersymmetric Yang–Mills theory provides famous examples, but uniform weight also appears in carefully chosen bases of Feynman integrals.

Multiple zeta values are special values of multiple polylogarithms:

$$
\zeta(n_1,\ldots,n_r)
=\sum_{0<k_1<\cdots<k_r}{1\over k_1^{n_1}\cdots k_r^{n_r}}
$$

up to convention choices for the ordering. They appear as constants when integrals are evaluated at special kinematic points.

Do not over-trust transcendental weight. Massive integrals, elliptic sectors, algebraic prefactors, and non-polylogarithmic functions can break simple counting.

## Harmonic polylogarithms

Harmonic polylogarithms are multiple polylogarithms with alphabet

$$
\{0,1,-1\}.
$$

They are especially common in single-scale integrals. One convention defines kernels

$$
f_0(t)={1\over t},
\qquad
f_1(t)={1\over 1-t},
\qquad
f_{-1}(t)={1\over 1+t}.
$$

Then

$$
H_{a_1,\ldots,a_r}(z)=\int_0^z dt\,f_{a_1}(t)H_{a_2,\ldots,a_r}(t),
$$

with $H(;z)=1$ and $H_{0,\ldots,0}(z)=\log^r z/r!$.

Different sign conventions exist between $H$ and $G$ notation, particularly for the letter $1$. In practice, harmonic polylogarithms are a computationally friendly subset of multiple polylogarithms. They are not a different species.

## Polylogarithms from differential equations

Modern Feynman-integral calculations often reduce a family of integrals to differential equations:

$$
d\vec I(\epsilon,x)=A(\epsilon,x)\vec I(\epsilon,x).
$$

If a basis can be chosen so that

$$
d\vec J(\epsilon,x)=\epsilon\sum_i M_i\,d\log \alpha_i(x)\,\vec J(\epsilon,x),
$$

with constant matrices $M_i$, then the solution is naturally an $\epsilon$ expansion in iterated integrals over the alphabet $\{\alpha_i\}$.

The letters $\alpha_i(x)$ determine the possible branch points. The matrices determine how different integrals mix. Boundary values determine constants. This is one of the cleanest reasons polylogarithms dominate large parts of perturbative QFT.

If the homogeneous equation contains elliptic periods instead of rational $d\log$ kernels, then this canonical polylogarithmic form does not exist in the same way. That is the transition to elliptic integrals and elliptic polylogarithms.

## Single-valued polylogarithms

Ordinary polylogarithms are multivalued. Some Euclidean correlation functions, string amplitudes, and conformal integrals require single-valued combinations. The simplest example is not $\log z$, but combinations of $\log z$ and $\log\bar z$ whose monodromies cancel.

The single-valued dilogarithm is closely related to the Bloch–Wigner function

$$
D(z)=\operatorname{Im}\operatorname{Li}_2(z)+\arg(1-z)\log|z|.
$$

It is real and single-valued on $\mathbb C\setminus\{0,1\}$ after the appropriate interpretation at branch points. In QFT, single-valued polylogarithms are useful when locality or Euclidean reality forbids monodromy in the full observable even though intermediate holomorphic pieces are multivaled.

## Where polylogarithms appear in QFT

**One-loop integrals.** Scalar triangles and boxes often evaluate to logarithms and dilogarithms. Analytic continuation determines physical cuts.

**Multiloop massless amplitudes.** Many massless multiloop amplitudes can be expressed in multiple polylogarithms with specific symbol alphabets.

**Canonical differential equations.** When a Feynman-integral basis has $d\log$ form, the $\epsilon$ expansion is an iterated integral expansion.

**Wilson lines and cusp physics.** Polylogs appear in cusp anomalous dimensions, soft functions, and eikonal integrals.

**Conformal integrals.** Cross-ratio dependence in conformal perturbation theory and position-space integrals often produces polylogarithms.

**Thermal and statistical sums.** Bose and Fermi integrals often involve $\operatorname{Li}_n(e^{-\beta m})$ or related functions.

**Amplitude bootstrap.** Symbols, alphabets, final-entry conditions, collinear limits, and discontinuities organize analytic ansätze for scattering amplitudes.

## Common pitfalls

**Forgetting the branch.** $\operatorname{Li}_2(x)$ for $x>1$ is not just a real number. The $i0$ prescription matters.

**Thinking the symbol is the function.** Symbols forget constants and can miss information about branches. They are a skeleton, not the whole animal.

**Mixing conventions for iterated integrals.** Some authors use kernels $dt/(t-a)$, others $dt/(a-t)$, and some reverse the order of letters. Check signs before translating.

**Assuming all Feynman integrals are polylogarithmic.** Elliptic and higher-genus sectors exist. The sunrise integral is the standard friendly ambush.

**Ignoring boundary constants.** Differential equations determine functions only up to constants. Those constants often include $\pi^2$, $\zeta_3$, and multiple zeta values.

**Over-interpreting weight.** Uniform weight is powerful when present, but not automatic. Masses, algebraic letters, elliptic sectors, and nontrivial dimensions can spoil the party.

## Exercises

### Exercise 1: The derivative recursion

Starting from

$$
\operatorname{Li}_n(z)=\sum_{m=1}^{\infty}{z^m\over m^n},
\qquad |z|<1,
$$

show that

$$
z{d\over dz}\operatorname{Li}_n(z)=\operatorname{Li}_{n-1}(z).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate term by term inside the disk of convergence:

$$
{d\over dz}\operatorname{Li}_n(z)=\sum_{m=1}^\infty {m z^{m-1}\over m^n}
=\sum_{m=1}^\infty {z^{m-1}\over m^{n-1}}.
$$

Multiplying by $z$ gives

$$
z{d\over dz}\operatorname{Li}_n(z)=\sum_{m=1}^\infty {z^m\over m^{n-1}}
=\operatorname{Li}_{n-1}(z).
$$

The identity then extends by analytic continuation on compatible branches.

</details>

### Exercise 2: The discontinuity of the dilogarithm

Use

$$
{d\over d\log x}\operatorname{Li}_2(x)=\operatorname{Li}_1(x)
$$

and the principal-branch discontinuity of $\operatorname{Li}_1(x)$ for $x>1$ to show that

$$
\operatorname{Disc}\,\operatorname{Li}_2(x)=-2\pi i\log x,
$$

where $\operatorname{Disc} f(x)=f(x+i0)-f(x-i0)$.

<details><summary><strong>Solution</strong></summary>

For $x>1$,

$$
\operatorname{Li}_1(x)=-\log(1-x)
$$

has discontinuity

$$
\operatorname{Disc}\,\operatorname{Li}_1(x)=-2\pi i.
$$

Indeed, $\log(1-x+i0)-\log(1-x-i0)=2\pi i$, and the extra minus sign comes from $\operatorname{Li}_1=-\log(1-z)$. Therefore

$$
{d\over d\log x}\operatorname{Disc}\,\operatorname{Li}_2(x)
=-2\pi i.
$$

Integrating with respect to $\log x$ gives

$$
\operatorname{Disc}\,\operatorname{Li}_2(x)=-2\pi i\log x+C.
$$

The discontinuity vanishes at the branch point in the limiting sense $x\to1^+$, so $C=0$. Thus

$$
\operatorname{Disc}\,\operatorname{Li}_2(x)=-2\pi i\log x.
$$

</details>

### Exercise 3: Euler's dilogarithm identity

For $0<z<1$, prove

$$
\operatorname{Li}_2(z)+\operatorname{Li}_2(1-z)
={\pi^2\over6}-\log z\log(1-z).
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
F(z)=\operatorname{Li}_2(z)+\operatorname{Li}_2(1-z)+\log z\log(1-z).
$$

Differentiate. Using

$$
{d\over dz}\operatorname{Li}_2(z)=-{\log(1-z)\over z}
$$

and

$$
{d\over dz}\operatorname{Li}_2(1-z)={\log z\over 1-z},
$$

we get

$$
F'(z)=-{\log(1-z)\over z}+{\log z\over1-z}
+{\log(1-z)\over z}-{\log z\over1-z}=0.
$$

Thus $F(z)$ is constant. Evaluate at $z=0^+$:

$$
\operatorname{Li}_2(0)=0,
\qquad
\operatorname{Li}_2(1)=\zeta(2)={\pi^2\over6},
$$

and $\log z\log(1-z)\to0$. Therefore $F(z)=\pi^2/6$, which gives the identity.

</details>

### Exercise 4: A simple shuffle identity

Using the shuffle product, show that

$$
G(a;z)G(b;z)=G(a,b;z)+G(b,a;z).
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
G(a;z)G(b;z)=
\left(\int_0^z {dt_1\over t_1-a}\right)
\left(\int_0^z {dt_2\over t_2-b}\right).
$$

The square integration region decomposes into two ordered regions:

$$
0<t_2<t_1<z
\qquad\text{and}\qquad
0<t_1<t_2<z,
$$

with contours interpreted in the complex plane as ordered simplices. The first region gives $G(a,b;z)$ and the second gives $G(b,a;z)$. Thus

$$
G(a;z)G(b;z)=G(a,b;z)+G(b,a;z).
$$

</details>

## Related pages

For the branch-cut and boundary-value language, see [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/) and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/). For discontinuities and reconstruction ideas, see [Dispersion Relations](/math-toolkit/complex-analysis/dispersion-relations/). For the first obstruction to ordinary polylogarithms, see [Elliptic Functions and Integrals](/math-toolkit/special-functions-exact-equations/elliptic-functions-and-integrals/). For integral representations that lead to polylogarithms, see [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/) and [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/).

## References and further reading

Classic references include Lewin's books on polylogarithms, Chen's work on iterated integrals, Goncharov's work on multiple polylogarithms and motivic structures, and the NIST Digital Library of Mathematical Functions for standard classical definitions. For harmonic polylogarithms, see Remiddi and Vermaseren. For symbols, coproducts, and amplitude applications, see reviews and papers by Duhr, Dixon, Henn, Weinzierl, Brown, Goncharov, and many collaborators. For Feynman-integral applications, see standard texts and reviews by Smirnov, Weinzierl, and modern amplitudes literature.

## Version history

- **2026-06-26:** Initial polished draft. Added classical polylogarithms, dilogarithm identities, branch cuts and discontinuities, multiple polylogarithms, shuffle algebra, symbols, constants, harmonic polylogarithms, differential equations, QFT uses, common pitfalls, exercises with solutions, and TikZ/SVG figure.
