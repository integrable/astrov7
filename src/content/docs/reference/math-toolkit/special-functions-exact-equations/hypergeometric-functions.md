---
title: "Hypergeometric Functions"
description: "Explains Gauss, generalized, and confluent hypergeometric functions for QFT: singular points, Frobenius series, Euler integrals, transformation formulae, monodromy, and common reductions to Legendre, Jacobi, Gegenbauer, and Coulomb-type functions."
sidebar:
  label: "Hypergeometric Functions"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard references on hypergeometric functions, Fuchsian differential equations, special functions, asymptotics, and QFT applications, including Riemann, Gauss, Kummer, Whittaker–Watson, Erdelyi et al., Abramowitz–Stegun, NIST DLMF, Olver, Temme, Slater, Bender–Orszag, Vilenkin–Klimyk, Morse–Feshbach, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, Di Francesco–Mathieu–Sénéchal, and references on conformal blocks and Feynman integrals."
topics:
  - hypergeometric function
  - Gauss hypergeometric equation
  - generalized hypergeometric function
  - confluent hypergeometric function
  - Euler integral
  - Frobenius method
  - monodromy
  - connection formula
  - conformal blocks
  - Feynman parameter integrals
canonicalTopics:
  - hypergeometric-function
  - gauss-hypergeometric-equation
  - generalized-hypergeometric-function
  - confluent-hypergeometric-function
  - euler-integral
  - frobenius-method
  - monodromy
  - connection-formula
  - conformal-block
  - feynman-parameter-integral
researchStatus:
  established:
    - "The Gauss hypergeometric function is the canonical solution of the second-order Fuchsian equation with three regular singular points, and many classical special functions are reductions or limits of it."
    - "Series expansions, Euler integrals, transformation formulae, connection formulae, contiguous relations, and confluent limits are classical and convention-stable once branches are specified."
  active:
    - "Modern QFT uses hypergeometric technology in conformal blocks, Feynman integrals, Mellin–Barnes representations, radial wave equations, AdS modes, analytic continuation, monodromy methods, and exact/semi-classical spectral problems."
---

## Summary

The hypergeometric function is the special function that appears when a second-order linear differential equation has exactly three regular singular points. By a fractional-linear change of variable, those points can be placed at

$$
z=0,\qquad z=1,\qquad z=\infty.
$$

The corresponding differential equation is the Gauss hypergeometric equation

$$
z(1-z)y''+\big[c-(a+b+1)z\big]y'-ab\,y=0.
$$

The solution regular at $z=0$ and normalized to $1$ is

$$
{}_2F_1(a,b;c;z)
=\sum_{n=0}^\infty
\frac{(a)_n(b)_n}{(c)_n}\frac{z^n}{n!},
\qquad |z|<1,
$$

where

$$
(q)_n=q(q+1)\cdots(q+n-1)=\frac{\Gamma(q+n)}{\Gamma(q)}
$$

is the Pochhammer symbol.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing the Gauss hypergeometric equation, its three regular singular points, Frobenius data, Euler integral, monodromy, connection matrices, transformations, reductions, and QFT uses.](/figures/math-toolkit/hypergeometric-singularity-flow.svg)

<figcaption>

The Gauss hypergeometric function is the meeting point of three languages: power series, beta-function integrals, and monodromy of a differential equation with singularities at $0$, $1$, and $\infty$. QFT uses all three languages: series for conformal blocks and radial modes, Euler integrals for Feynman parameters, and monodromy for analytic continuation and spectral conditions.

</figcaption>
</figure>

The word “hypergeometric” can feel like a fog machine at first. The core idea is simple: a power series is hypergeometric when the ratio of successive coefficients is a rational function of the summation index. That one algebraic fact explains why these functions are tractable, why they have many transformations, and why so many other special functions hide inside them.

## Prerequisites

You should know [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/), [Bessel Functions](/math-toolkit/special-functions-exact-equations/bessel-functions/), [Legendre and Spherical Functions](/math-toolkit/special-functions-exact-equations/legendre-and-spherical-functions/), [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), and [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/).

This page uses standard special-function conventions. Branches must be specified when $z$ crosses cuts, and the default cut for ${}_2F_1$ is usually taken along $[1,\infty)$ in the $z$-plane. QFT applications often move the cut by changing variables or by imposing an $i0$ prescription.

## Why hypergeometric functions matter in QFT

Hypergeometric functions are not rare ornamental functions. They are the “solvable residue” of many QFT calculations.

They appear when angular or radial equations separate into exactly solvable ODEs; when Feynman parameter integrals reduce to Euler-type integrals; when conformal blocks are written in cross-ratio variables; when AdS wave equations reduce to radial equations; when Coulomb-like scattering is solved exactly; and when dimensional regularization produces ratios of gamma functions and series in cross ratios.

The same object can enter through different doors. A one-loop integral may produce ${}_2F_1$ from a Feynman-parameter integral. A conformal block may produce the same ${}_2F_1$ from solving a Casimir equation. A wave equation may produce it from regular singular points. That is the real punchline: hypergeometric functions are not a table lookup; they are a structural marker.

## The hypergeometric series

The Gauss hypergeometric series is

$$
{}_2F_1(a,b;c;z)
=\sum_{n=0}^\infty A_n z^n,
\qquad
A_n=\frac{(a)_n(b)_n}{(c)_n n!}.
$$

The coefficient ratio is

$$
\frac{A_{n+1}}{A_n}
=\frac{(n+a)(n+b)}{(n+c)(n+1)}.
$$

This rational coefficient ratio is the source of the differential equation. Applying $\theta=z\,d/dz$, the series obeys

$$
\big[\theta(\theta+c-1)-z(\theta+a)(\theta+b)\big]{}_2F_1(a,b;c;z)=0.
$$

Expanding this operator gives

$$
z(1-z)y''+\big[c-(a+b+1)z\big]y'-ab\,y=0.
$$

The series has radius of convergence $1$ unless it terminates. The point $z=1$ is a singular point of the differential equation, so the power series around $0$ has no reason to converge beyond it.

A useful special value is Gauss’s summation formula:

$$
{}_2F_1(a,b;c;1)
=\frac{\Gamma(c)\Gamma(c-a-b)}{\Gamma(c-a)\Gamma(c-b)},
\qquad
\operatorname{Re}(c-a-b)>0.
$$

This formula is a compact example of a recurring theme: convergence conditions first define an integral or series, and analytic continuation then extends the final expression meromorphically in the parameters.

## Local exponents and singular points

The hypergeometric equation has regular singular points at $0$, $1$, and $\infty$. The local exponents are conventionally recorded as

$$
\begin{array}{c|ccc}
&0&1&\infty\\
\hline
\text{exponents}&0&0&a\\
&1-c&c-a-b&b
\end{array}
$$

This table says how local solutions behave near each singular point. Near $z=0$, for example, the two local behaviors are

$$
y(z)\sim 1,
\qquad
y(z)\sim z^{1-c},
$$

unless the exponent difference is an integer, in which case logarithms can appear.

A compact way to remember the equation is the Riemann $P$ symbol:

$$
P\left\{
\begin{matrix}
0&1&\infty\\
0&0&a\\
1-c&c-a-b&b
\end{matrix};z\right\}.
$$

The $P$ symbol is not merely notation. It says that the hypergeometric equation is determined, up to equivalence, by three regular singular points and their exponent data. Once a fourth regular singular point appears, a new global parameter enters; that is the beginning of the Heun story.

## Euler integral representation

For suitable real parts of the parameters,

$$
{}_2F_1(a,b;c;z)
=\frac{\Gamma(c)}{\Gamma(b)\Gamma(c-b)}
\int_0^1 dt\,t^{b-1}(1-t)^{c-b-1}(1-zt)^{-a}.
$$

The conditions for the literal integral are

$$
\operatorname{Re}c>\operatorname{Re}b>0,
$$

with branch choices for $(1-zt)^{-a}$. The formula then extends by analytic continuation.

This integral makes the connection to QFT embarrassingly direct. Feynman parameters routinely produce integrals of the shape

$$
\int_0^1 dx\,x^{\alpha-1}(1-x)^{\beta-1}(1-zx)^{-\rho},
$$

and this is exactly a beta-function normalization times a hypergeometric function:

$$
\int_0^1 dx\,x^{\alpha-1}(1-x)^{\beta-1}(1-zx)^{-\rho}
=B(\alpha,\beta)
{}_2F_1(\rho,\alpha;\alpha+\beta;z).
$$

A second useful representation is the Barnes contour integral. One common form is

$$
{}_2F_1(a,b;c;z)
=\frac{\Gamma(c)}{\Gamma(a)\Gamma(b)}
\frac{1}{2\pi i}
\int_{\mathcal C} ds\,
\frac{\Gamma(a+s)\Gamma(b+s)\Gamma(-s)}{\Gamma(c+s)}(-z)^s,
$$

where the contour separates the poles of $\Gamma(-s)$ from those of $\Gamma(a+s)$ and $\Gamma(b+s)$. This is the seed of many Mellin–Barnes representations for loop integrals.

## Transformation formulae

The hypergeometric equation is rigid enough that solutions around one singular point can be rewritten around another. Some of the most used transformations are Euler’s transformation,

$$
{}_2F_1(a,b;c;z)
=(1-z)^{c-a-b}{}_2F_1(c-a,c-b;c;z),
$$

and Pfaff’s transformations,

$$
{}_2F_1(a,b;c;z)
=(1-z)^{-a}{}_2F_1\!\left(a,c-b;c;\frac{z}{z-1}\right),
$$

$$
{}_2F_1(a,b;c;z)
=(1-z)^{-b}{}_2F_1\!\left(c-a,b;c;\frac{z}{z-1}\right).
$$

These are not random identities. They come from permuting the singular points $0$, $1$, and $\infty$ and adjusting the local exponents.

A connection formula between neighborhoods of $z=0$ and $z=\infty$ is

$$
\begin{aligned}
{}_2F_1(a,b;c;z)
={}&
\frac{\Gamma(c)\Gamma(b-a)}{\Gamma(b)\Gamma(c-a)}
(-z)^{-a}
{}_2F_1\!\left(a,1-c+a;1-b+a;\frac1z\right)\\
&+
\frac{\Gamma(c)\Gamma(a-b)}{\Gamma(a)\Gamma(c-b)}
(-z)^{-b}
{}_2F_1\!\left(b,1-c+b;1-a+b;\frac1z\right),
\end{aligned}
$$

valid away from parameter values where the displayed coefficients need limiting. In physics language, this kind of formula converts one channel expansion into another channel expansion. The gamma-function prefactors are the connection coefficients.

## Polynomial reductions

If $a=-n$ or $b=-n$ with $n=0,1,2,
\dots$, the series terminates. The result is a polynomial of degree $n$. This is how Jacobi, Gegenbauer, and Legendre polynomials fit into the hypergeometric family.

The Jacobi polynomial can be written as

$$
P_n^{(\alpha,\beta)}(x)
=\frac{(\alpha+1)_n}{n!}
{}_2F_1\!\left(-n,n+\alpha+\beta+1;\alpha+1;\frac{1-x}{2}\right).
$$

The Legendre polynomial is the special case

$$
P_\ell(x)
={}_2F_1\!\left(-\ell,\ell+1;1;\frac{1-x}{2}\right).
$$

This formula makes partial waves look less magical. Rotational symmetry gives Legendre functions; the Legendre equation is a special hypergeometric equation; therefore many partial-wave manipulations are hypergeometric manipulations in disguise.

## Generalized hypergeometric functions

The generalized hypergeometric function is

$$
{}_pF_q\!\left(\begin{matrix}a_1,\dots,a_p\\ b_1,\dots,b_q\end{matrix};z\right)
=\sum_{n=0}^\infty
\frac{(a_1)_n\cdots(a_p)_n}{(b_1)_n\cdots(b_q)_n}
\frac{z^n}{n!}.
$$

The coefficient ratio is

$$
\frac{A_{n+1}}{A_n}
=\frac{(n+a_1)\cdots(n+a_p)}{(n+b_1)\cdots(n+b_q)(n+1)}.
$$

The convergence behavior depends on $p$ and $q$:

$$
\begin{array}{c|c}
\text{case}&\text{generic convergence}\\
\hline
p\le q&\text{entire in }z\\
p=q+1&|z|<1\text{ before continuation}\\
p>q+1&\text{divergent asymptotic series unless terminating.}
\end{array}
$$

The Bessel function is already contained in this hierarchy:

$$
J_\nu(z)
=\frac{(z/2)^\nu}{\Gamma(\nu+1)}
{}_0F_1\!\left(\begin{matrix}-\\ \nu+1\end{matrix};-\frac{z^2}{4}\right).
$$

This is one reason hypergeometric functions are a unifying notation for special functions. The notation is not always the most illuminating one, but it reveals family relationships.

## Confluent hypergeometric functions

When two regular singular points of the Gauss equation merge, one obtains a confluent equation. The standard confluent hypergeometric equation is

$$
z y''+(b-z)y'-a y=0.
$$

One solution regular at the origin is Kummer’s function

$$
M(a,b,z)={}_1F_1(a;b;z)
=\sum_{n=0}^\infty \frac{(a)_n}{(b)_n}\frac{z^n}{n!}.
$$

A second important solution is Tricomi’s function $U(a,b,z)$, selected by its large-$z$ behavior in appropriate sectors:

$$
U(a,b,z)\sim z^{-a},
\qquad |z|\to\infty.
$$

In radial quantum mechanics and QFT, this distinction is exactly the kind of distinction one cares about: regular at the origin versus decaying, incoming, outgoing, or normalizable at infinity.

The Whittaker equation

$$
\frac{d^2W}{dz^2}
+\left(-\frac14+\frac{\kappa}{z}+\frac{1/4-\mu^2}{z^2}\right)W=0
$$

is another confluent hypergeometric equation in disguise. This is why Coulomb wave functions and related scattering problems are hypergeometric rather than merely Bessel-like.

## Monodromy and branch choices

Because the hypergeometric equation has singular points, analytic continuation around loops acts nontrivially on the space of solutions. This action is called monodromy.

Take a basis of local solutions near $z=0$, say

$$
y_1(z)={}_2F_1(a,b;c;z),
$$

and, if $c\notin\mathbb Z$,

$$
y_2(z)=z^{1-c}{}_2F_1(a-c+1,b-c+1;2-c;z).
$$

A loop around $z=0$ leaves $y_1$ invariant and multiplies $y_2$ by

$$
e^{2\pi i(1-c)}.
$$

Loops around $1$ and $\infty$ are diagonal in other local bases. Connection matrices convert between bases. This is the monodromy viewpoint.

In QFT, monodromy shows up whenever “the same formula” must be continued across channels, thresholds, or Euclidean/Lorentzian regions. Branch cuts are not cosmetic; they encode boundary conditions and causal prescriptions.

## Hypergeometric conformal blocks

In two-dimensional global conformal symmetry, and in higher-dimensional special kinematics, hypergeometric functions appear naturally. A simple global $SL(2)$ block has the form

$$
k_h(z)=z^h{}_2F_1(h,h;2h;z).
$$

The differential equation is the Casimir equation for the exchanged representation. Here the singular points $z=0,1,\infty$ correspond to OPE limits and channel boundaries. The hypergeometric connection problem becomes the problem of relating different OPE channels.

This is a useful conceptual bridge: hypergeometric functions are representation theory wearing complex-analysis clothing.

## Common pitfalls

The most common mistake is treating the power series around $z=0$ as the whole function. It is only one local representation. Analytic continuation, branch cuts, and connection formulae are part of the data.

A second mistake is forgetting parameter singularities. Formulae with gamma functions in the denominator may need limits when parameters differ by integers. The limiting formula often contains logarithms.

A third mistake is ignoring branch conventions for powers such as $(-z)^{-a}$ and $(1-z)^{c-a-b}$. These choices are not harmless in Lorentzian QFT, where they carry the $i0$ prescription.

A fourth mistake is assuming that every special-function identity is numerically stable. Transformation formulae that are exact symbolically can be disastrous numerically near cancellation regions.

## Worked example: Euler integral from Feynman parameters

Consider the integral

$$
I(z)=\int_0^1 dx\,x^{\alpha-1}(1-x)^{\beta-1}(1-zx)^{-\rho}.
$$

Expanding the last factor gives

$$
(1-zx)^{-\rho}
=\sum_{n=0}^\infty \frac{(\rho)_n}{n!}(zx)^n,
$$

valid initially for $|zx|<1$. Then

$$
I(z)=\sum_{n=0}^\infty \frac{(\rho)_n z^n}{n!}
\int_0^1 dx\,x^{\alpha+n-1}(1-x)^{\beta-1}.
$$

The integral is a beta function:

$$
\int_0^1 dx\,x^{\alpha+n-1}(1-x)^{\beta-1}
=B(\alpha+n,\beta)
=B(\alpha,\beta)\frac{(\alpha)_n}{(\alpha+\beta)_n}.
$$

Thus

$$
I(z)=B(\alpha,\beta)
{}_2F_1(\rho,\alpha;\alpha+\beta;z).
$$

This is the template behind a huge number of one-parameter Feynman integrals. More complicated loop integrals generalize the same idea to several variables and Mellin–Barnes integrals.

## Exercises

### Exercise 1: Verify the hypergeometric differential equation

Starting from

$$
y(z)=\sum_{n=0}^\infty
\frac{(a)_n(b)_n}{(c)_n n!}z^n,
$$

show that $y$ solves

$$
z(1-z)y''+[c-(a+b+1)z]y'-ab\,y=0.
$$

<details><summary><strong>Solution</strong></summary>

Let $A_n=(a)_n(b)_n/[(c)_n n!]$. The coefficient ratio is

$$
\frac{A_n}{A_{n-1}}
=\frac{(n-1+a)(n-1+b)}{(n-1+c)n}.
$$

For $y=\sum A_nz^n$, compare the coefficient of $z^n$ in the differential equation. The terms give

$$
(n+1)(n+c)A_{n+1}-(n+a)(n+b)A_n=0,
$$

which is exactly the recurrence implied by the coefficient ratio. Therefore the series solves the equation within its disk of convergence, and then by analytic continuation wherever the solution is defined.

</details>

### Exercise 2: Legendre as hypergeometric

Use the hypergeometric equation to show that

$$
P_\ell(x)={}_2F_1\!\left(-\ell,\ell+1;1;\frac{1-x}{2}\right)
$$

satisfies the Legendre equation.

<details><summary><strong>Solution</strong></summary>

Set

$$
z=\frac{1-x}{2},
\qquad
\frac{d}{dz}=-2\frac{d}{dx},
\qquad
\frac{d^2}{dz^2}=4\frac{d^2}{dx^2}.
$$

For $a=-\ell$, $b=\ell+1$, $c=1$, the hypergeometric equation is

$$
z(1-z)y''+(1-2z)y'+\ell(\ell+1)y=0.
$$

Since $z(1-z)=(1-x^2)/4$ and $1-2z=x$, substituting derivatives gives

$$
(1-x^2)y_{xx}-2xy_x+\ell(\ell+1)y=0.
$$

Because $a=-\ell$, the hypergeometric series terminates and is a polynomial of degree $\ell$, normalized by $P_\ell(1)=1$.

</details>

### Exercise 3: A Feynman-parameter integral

Evaluate

$$
I(z)=\int_0^1 dx\,\frac{x^{\alpha-1}(1-x)^{\beta-1}}{1-zx}
$$

in terms of a hypergeometric function.

<details><summary><strong>Solution</strong></summary>

This is the Euler integral with $\rho=1$:

$$
I(z)=B(\alpha,\beta)
{}_2F_1(1,\alpha;\alpha+\beta;z),
$$

initially for parameters and $z$ in a convergence domain, and then by analytic continuation with the chosen branch of $(1-zx)^{-1}$.

</details>

### Exercise 4: Termination condition

Suppose $a=-N$ with $N\in\mathbb Z_{\ge0}$. Why does ${}_2F_1(a,b;c;z)$ terminate?

<details><summary><strong>Solution</strong></summary>

For $a=-N$,

$$
(a)_n=(-N)_n
$$

vanishes for $n=N+1,N+2,\dots$, because one factor in the product is zero. Therefore all terms after $n=N$ vanish. The result is a polynomial of degree at most $N$, unless further parameter degeneracies reduce the degree.

</details>

## Related pages

For the integral technology behind the Euler representation, see [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/). For radial and angular reductions of hypergeometric functions, see [Bessel Functions](/math-toolkit/special-functions-exact-equations/bessel-functions/) and [Legendre and Spherical Functions](/math-toolkit/special-functions-exact-equations/legendre-and-spherical-functions/). For the analytic-continuation side, see [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/) and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/). For the next step beyond three regular singular points, continue to Heun equations.

## References and further reading

Classic references include Whittaker and Watson, Erdelyi et al., Abramowitz and Stegun, Slater, Olver, Temme, and the NIST Digital Library of Mathematical Functions. For asymptotic and differential-equation methods, see Bender and Orszag. For physics applications, see standard QFT texts by Weinberg, Srednicki, Schwartz, Zee, and Zinn-Justin, and conformal field theory references such as Di Francesco, Mathieu, and Sénéchal.

## Version history

- 2026-06-26: First polished draft. Added singular-point viewpoint, Euler integral, transformations, polynomial reductions, generalized and confluent hypergeometric functions, QFT applications, pitfalls, and exercises with solutions.
