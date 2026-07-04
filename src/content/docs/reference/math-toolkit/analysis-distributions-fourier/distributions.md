---
title: "Distributions"
description: "A careful introduction to distributions as continuous linear functionals on test functions, with the delta distribution, distributional derivatives, principal values, Green functions, and QFT smearing."
sidebar:
  label: "Distributions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard distribution theory, with QFT applications to smeared fields, propagators, canonical commutators, and Green functions."
topics:
  - distributions
  - test functions
  - delta function
  - Green functions
  - QFT singularities
canonicalTopics:
  - distributions
  - delta-distribution
  - operator-valued-distributions
  - qft-analysis
researchStatus:
  established:
    - "Distributions are the standard mathematical language for delta functions, singular kernels, propagators, and operator-valued fields in QFT."
  active:
    - "Products, restrictions, and extensions of singular distributions are central in renormalization, microlocal QFT, and rigorous treatments of interacting fields."
---

## Summary

A distribution is a generalized function defined by how it acts on smooth test functions. Instead of asking for a pointwise value $T(x)$, we ask for a number

$$
\langle T,\varphi\rangle
$$

for every allowed test function $\varphi$. Ordinary functions define distributions by integration. The delta function defines a distribution by evaluation. Derivatives of distributions are defined by integration by parts. This one idea turns many formal QFT expressions into meaningful formulas.

The basic examples are

$$
\langle T_f,\varphi\rangle=\int d^dx\,f(x)\varphi(x),
\qquad
\langle\delta_y,\varphi\rangle=\varphi(y),
\qquad
\langle\partial_iT,\varphi\rangle=-\langle T,\partial_i\varphi\rangle.
$$

This page explains the definitions, then shows why QFT needs them: fields are operator-valued distributions, propagators are distributional kernels, canonical commutators are equalities after smearing, and the $i0$ in a denominator is part of the object rather than decorative punctuation.

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/), especially the Euclidean and Lorentzian Fourier conventions. You should also be comfortable with multivariable integration, integration by parts, compact support, and the idea of a linear functional.

No measure theory is required for this page. When the distinction matters, we will say “locally integrable function” rather than “function” and “almost everywhere” rather than “pointwise.”

## Core idea

A singular expression is often easier to understand by testing it against smooth probes. The test function $\varphi$ is the probe. The distribution $T$ is the object being probed. The number $\langle T,\varphi\rangle$ is the measurement.


| Part | Meaning |
|---|---|
| Test function $\varphi$ | The smooth probe: a source profile, wavepacket, detector resolution, or mathematical test. |
| Distribution $T$ | The singular object: a delta function, propagator, principal value, or field-valued kernel. |
| Pairing $\langle T,\varphi\rangle$ | The well-defined number or operator obtained after smearing. |


This changes the meaning of equality. The statement $T=S$ means

$$
\langle T,\varphi\rangle=\langle S,\varphi\rangle
\quad\text{for every test function }\varphi.
$$

Many QFT identities are equalities of this kind. The canonical commutator with a delta function, the equation obeyed by a propagator, and the Ward identity with contact terms are not pointwise identities of honest functions. They are distributional identities.

The slogan is:

$$
\text{a distribution is not known by its values; it is known by all its smearings}.
$$

## Setup and conventions

Let $U\subset\mathbb R^d$ be open. The space of test functions on $U$ is

$$
\mathcal D(U)=C_c^\infty(U),
$$

the smooth functions with compact support contained in $U$. A distribution on $U$ is a continuous linear functional

$$
T:\mathcal D(U)\to\mathbb C,
\qquad
\varphi\mapsto\langle T,\varphi\rangle.
$$

The space of distributions is denoted

$$
\mathcal D'(U).
$$

We use a pairing convention that is linear in the test function. Mathematicians sometimes use conventions involving complex conjugation when test spaces are treated as Hilbert spaces; that is not the convention here.

The word “continuous” refers to the natural topology on $C_c^\infty(U)$. A useful local way to remember it is this: for every compact $K\subset U$, there should be constants $C$ and $N$ such that for all test functions supported in $K$,

$$
|\langle T,\varphi\rangle|
\leq C\sum_{|\alpha|\leq N}\sup_{x\in K}|\partial^\alpha\varphi(x)|.
$$

Here $\alpha=(\alpha_1,\ldots,\alpha_d)$ is a multi-index,

$$
\partial^\alpha
=\partial_1^{\alpha_1}\cdots\partial_d^{\alpha_d},
\qquad
|\alpha|=\alpha_1+\cdots+\alpha_d.
$$

This estimate is the technical guardrail. It allows singular objects, but not completely arbitrary linear rules that ignore the smooth structure of spacetime.

## Ordinary functions as distributions

Every locally integrable function $f\in L^1_{\mathrm{loc}}(U)$ defines a distribution $T_f$ by

$$
\langle T_f,\varphi\rangle
=\int_U d^dx\,f(x)\varphi(x).
$$

Locally integrable means integrable on every compact subset of $U$. This includes many functions that are not globally integrable and many functions with mild singularities.

For example, on $\mathbb R^3$,

$$
f(x)=\frac{1}{|x|}
$$

is locally integrable near the origin because

$$
\int_{|x|<\epsilon}d^3x\,\frac{1}{|x|}
=4\pi\int_0^\epsilon dr\,r
=2\pi\epsilon^2.
$$

So $1/|x|$ defines a distribution in three dimensions. By contrast, $1/|x|^3$ is not locally integrable near the origin in three dimensions and needs a prescription if it is to define a distribution.

Two locally integrable functions that differ only on a set of measure zero define the same distribution. Thus distributions do not remember pointwise changes at isolated points. This is already one reason why trying to assign point values to singular expressions is the wrong game.

## Weak equality

If $f$ and $g$ are ordinary smooth functions, the equality $f=g$ can be checked pointwise. For distributions, equality means equality after pairing:

$$
T=S
\quad\Longleftrightarrow\quad
\langle T-S,\varphi\rangle=0
\quad\text{for all }\varphi\in C_c^\infty(U).
$$

This is called weak equality or distributional equality. It is weaker than pointwise equality for functions, but it is exactly the right strength for singular kernels.

For locally integrable functions,

$$
T_f=T_g
$$

means $f=g$ almost everywhere. So distributional equality does not distinguish functions that differ only on negligible sets. It does, however, distinguish genuine singular distributions such as $\delta_0$ from every locally integrable function.

In QFT, weak equality is not a compromise. It is the natural language of measurement. Fields and correlators are never observed at a mathematical point with infinite resolution; they are smeared against wave packets, detector profiles, sources, or test functions.

## The delta distribution

The delta distribution at $y\in U$ is defined by

$$
\langle\delta_y,\varphi\rangle=\varphi(y).
$$

In integral notation this is written

$$
\int_U d^dx\,\delta^{(d)}(x-y)\varphi(x)=\varphi(y).
$$

The integral notation is useful, but it can mislead. The symbol $\delta^{(d)}(x-y)$ is not a function of $x$ with an enormous value at $x=y$. It is a rule that evaluates test functions at $y$.

The delta distribution has support at one point. Its defining property immediately gives, for a smooth function $f$,

$$
f(x)\delta^{(d)}(x-y)=f(y)\delta^{(d)}(x-y),
$$

because both sides have the same pairing with every test function:

$$
\langle f\delta_y,\varphi\rangle
=\langle\delta_y,f\varphi\rangle
=f(y)\varphi(y)
=\langle f(y)\delta_y,\varphi\rangle.
$$

A standard one-dimensional scaling rule is

$$
\delta(ax)=\frac{1}{|a|}\delta(x)
\qquad(a\neq 0).
$$

More generally, if $g:\mathbb R\to\mathbb R$ has simple zeros $x_i$ with $g'(x_i)\neq0$, then

$$
\delta(g(x))=
\sum_i\frac{\delta(x-x_i)}{|g'(x_i)|}.
$$

This is the one-dimensional prototype of the constraint delta functions used in phase space, gauge fixing, and changes of variables.

## Derivatives of distributions

Distributional derivatives are defined so that integration by parts remains true without boundary terms. For a distribution $T$,

$$
\langle\partial_iT,\varphi\rangle
=-\langle T,\partial_i\varphi\rangle.
$$

For a multi-index $\alpha$,

$$
\langle\partial^\alpha T,\varphi\rangle
=(-1)^{|\alpha|}\langle T,\partial^\alpha\varphi\rangle.
$$

This definition extends ordinary differentiation. If $f$ is a smooth function, then

$$
\langle\partial_iT_f,\varphi\rangle
=-\int d^dx\,f(x)\partial_i\varphi(x)
=\int d^dx\,(\partial_if)(x)\varphi(x)
=\langle T_{\partial_if},\varphi\rangle.
$$

But the definition also differentiates nonsmooth objects. For the delta distribution,

$$
\langle\partial_i\delta_y,\varphi\rangle
=-\partial_i\varphi(y).
$$

In integral notation,

$$
\int d^dx\,\partial_i\delta^{(d)}(x-y)\varphi(x)
=-\partial_i\varphi(y).
$$

This identity is often the cleanest way to remember signs. The derivative acts on the test function with a minus sign.

## Step functions and jumps

The Heaviside step function $\theta(x)$ defines a distribution by integration. Its distributional derivative is the delta distribution:

$$
\frac{d}{dx}\theta(x)=\delta(x).
$$

Indeed,

$$
\left\langle\frac{d\theta}{dx},\varphi\right\rangle
=-\int_0^\infty dx\,\varphi'(x)
=\varphi(0)
=\langle\delta,\varphi\rangle.
$$

More generally, if a piecewise smooth function $f$ has a jump at $x=0$,

$$
f(0^+)-f(0^-)=A,
$$

then its distributional derivative contains a contact term:

$$
\frac{df}{dx}=\left(\frac{df}{dx}\right)_{\mathrm{ordinary}}+A\delta(x).
$$

This is the elementary ancestor of many QFT contact terms. A discontinuity in an ordered product, for example, can produce a delta function when differentiated.

## Approximating distributions

Distributions can often be approached by families of ordinary functions. Let $\rho\in C_c^\infty(\mathbb R^d)$ satisfy

$$
\int d^dx\,\rho(x)=1.
$$

Define

$$
\rho_\epsilon(x)=\frac{1}{\epsilon^d}\rho\!\left(\frac{x}{\epsilon}\right).
$$

Then $\rho_\epsilon$ converges to $\delta_0$ distributionally:

$$
\lim_{\epsilon\to0}\int d^dx\,\rho_\epsilon(x)\varphi(x)
=\varphi(0).
$$

This justifies the common picture of a delta function as a narrow bump, but only if the limit is understood after smearing. Distributional convergence does not imply pointwise convergence, and it does not preserve nonlinear operations. In particular,

$$
\rho_\epsilon\to\delta
$$

does not mean $\rho_\epsilon^2$ has a canonical limit. Different approximate deltas can lead to different divergent or finite answers for nonlinear expressions. That is the baby version of a renormalization problem.

## Multiplication

A smooth function can multiply a distribution canonically:

$$
\langle fT,\varphi\rangle=\langle T,f\varphi\rangle.
$$

This works because $f\varphi$ is again a test function. The same argument does not define the product of two general distributions. There is no canonical meaning to

$$
\delta(x)^2
$$

inside ordinary distribution theory.

Some products of distributions are well-defined under additional hypotheses. Others require a regulator and a prescription for subtracting or extending singularities. In perturbative QFT, products of propagators at coincident points are precisely where ultraviolet divergences and counterterms enter.

A good rule of thumb is:

$$
\text{smooth}\times\text{distribution is safe; singular}\times\text{singular needs scrutiny}.
$$

## Tempered distributions and Fourier transforms

Fourier transforms are not defined for every distribution in $\mathcal D'(\mathbb R^d)$. A particularly important subspace is the space of tempered distributions,

$$
\mathcal S'(\mathbb R^d),
$$

the continuous linear functionals on the Schwartz space $\mathcal S(\mathbb R^d)$ of smooth functions that decay faster than any power, together with all their derivatives.

Tempered distributions are the natural home for flat-space Fourier analysis in QFT. With the Euclidean convention

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\int_k=\int\frac{d^dk}{(2\pi)^d},
$$

the basic operational rules are

$$
\widehat{\partial_iT}(k)=ik_i\widehat T(k),
\qquad
\widehat{x_iT}(k)=i\partial_{k_i}\widehat T(k),
$$

and

$$
\widehat{\delta_0}(k)=1,
\qquad
\widehat{1}(k)=(2\pi)^d\delta^{(d)}(k).
$$

The last two identities are distributional identities. For example,

$$
1=\int d^dx\,e^{-ik\cdot x}\delta^{(d)}(x)
$$

is harmless, but

$$
(2\pi)^d\delta^{(d)}(k)=\int d^dx\,e^{-ik\cdot x}
$$

only makes sense after smearing against a test function in momentum space.

## Principal values and boundary values

The ordinary function $1/x$ is not locally integrable near $x=0$ in the Lebesgue sense, because $\int_{-\epsilon}^{\epsilon}dx\,|1/x|$ diverges. Its Cauchy principal value is the distribution

$$
\left\langle\operatorname{PV}\frac{1}{x},\varphi\right\rangle
=\lim_{\epsilon\to0^+}
\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x}.
$$

The symmetric exclusion around $0$ is part of the definition. Without it, the limit is not well-defined.

A related and extremely important identity is

$$
\frac{1}{x\pm i0}
=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
$$

This means

$$
\lim_{\epsilon\to0^+}\int dx\,\frac{\varphi(x)}{x\pm i\epsilon}
=
\left\langle\operatorname{PV}\frac{1}{x},\varphi\right\rangle
\mp i\pi\varphi(0).
$$

In QFT, expressions such as

$$
\frac{1}{p^2-m^2+i0}
$$

are boundary-value distributions. The $+i0$ specifies how the pole is approached in complexified momentum space. It is not a tiny correction to be forgotten after the algebra. It is the causal prescription.

## Green functions as distributional inverses

Let $P$ be a differential operator. A Green function for $P$ is a distributional kernel $G(x,y)$ satisfying

$$
P_xG(x,y)=\delta^{(d)}(x-y)
$$

with specified boundary conditions. Without boundary conditions, “the inverse of $P$” is usually ambiguous.

For example, in three-dimensional Euclidean space,

$$
G(x)=\frac{1}{4\pi|x|}
$$

satisfies

$$
-\Delta G(x)=\delta^{(3)}(x)
$$

as a distribution. Away from the origin, $G$ is harmonic. The delta function appears entirely from the singularity at $x=0$.

For the Lorentzian Klein–Gordon operator in the mostly-minus convention, define the Feynman propagator by

$$
\Delta_F(x-y)=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i0}.
$$

Then

$$
(\Box_x+m^2)\Delta_F(x-y)=-i\delta^{(4)}(x-y).
$$

The retarded, advanced, Wightman, and Euclidean propagators solve related distributional equations with different support, boundary, spectral, or analyticity conditions. That difference is physics, not bookkeeping.

## Fields as operator-valued distributions

In rigorous language, a quantum field is not usually an operator $\phi(x)$ at a point. It is an operator-valued distribution. The safer object is the smeared field

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
$$

where $f$ is a suitable test function.

The canonical equal-time commutator

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y)
$$

means that after smearing with spatial test functions $f$ and $g$,

$$
[\phi(t,f),\pi(t,g)]
=i\int d^3\mathbf x\,f(\mathbf x)g(\mathbf x),
$$

where

$$
\phi(t,f)=\int d^3\mathbf x\,f(\mathbf x)\phi(t,\mathbf x),
\qquad
\pi(t,g)=\int d^3\mathbf x\,g(\mathbf x)\pi(t,\mathbf x).
$$

The unsmeared formula is a compressed notation for the smeared formula. This is not pedantry. Products such as $\phi(x)^2$ at the same point are singular in many QFTs and require normal ordering, point splitting, operator-product expansion, or renormalization.

## Contact terms and local ambiguity

A contact term is a distribution supported on coincident points, usually a delta function or one of its derivatives. Contact terms vanish at separated points but affect identities involving derivatives, conservation laws, or coincident insertions.

For example, a current conservation equation inside correlation functions often has the schematic form

$$
\partial_\mu\langle j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=\sum_{r=1}^n \delta^{(d)}(x-x_r)
\langle \mathcal O_1(x_1)\cdots \delta\mathcal O_r(x_r)\cdots\mathcal O_n(x_n)\rangle.
$$

The right-hand side is not a failure of conservation. It says that the charge generated by $j^0$ acts on the inserted operators. The delta functions mark where the current hits an insertion.

Renormalization often appears mathematically as the problem of extending a distribution defined away from coincident points to a distribution on the diagonal. The extension may be ambiguous by local contact terms. Physics then fixes, constrains, or parametrizes the ambiguity through symmetries, renormalization conditions, and measured couplings.

## Restrictions and singular subspaces

Smooth functions can be restricted to submanifolds without much drama. Distributions cannot always be restricted. For instance, the distribution $\delta(x)$ on $\mathbb R$ cannot be naively restricted to the point $x=0$; its singularity is already concentrated there.

This matters in QFT whenever one tries to evaluate fields on lower-dimensional supports, multiply coincident operators, define defects, or take equal-time limits. Some restrictions are harmless, some require renormalization, and the general criterion is expressed using wavefront sets. The main lesson for now is simpler: restricting or multiplying singular objects is an operation, not a birthright.

## Common pitfalls

**Treating $\delta$ as a number-valued function.** The expression $\delta(0)$ is not defined in distribution theory. In finite volume or with a regulator, a related expression may become a large finite number, but that number belongs to the regulator, not to the delta distribution itself.

**Forgetting the test function.** If a distributional identity is confusing, pair both sides with $\varphi$ and integrate by parts. Most signs and factors become obvious.

**Multiplying singular distributions without a prescription.** Products like $\delta^2$, $\Delta_F(x)^2$ at $x=0$, or composite fields $\phi(x)^2$ generally need renormalization or another definition.

**Dropping contact terms.** Contact terms vanish at separated points, but they are often the whole point in Ward identities, anomalies, equal-time commutators, and operator mixing.

**Ignoring the $i0$ prescription.** The expression $1/(p^2-m^2+i0)$ is not the same distribution as $1/(p^2-m^2-i0)$, and neither is merely $1/(p^2-m^2)$.

**Assuming every distribution has a Fourier transform.** Every tempered distribution has a Fourier transform. General distributions need not. In flat-space QFT, temperedness is common but should not be silently assumed in every mathematical context.

## Relations to other pages

This page is the first technical page in the Analysis, Distributions, and Fourier Methods chapter. The [chapter overview](/math-toolkit/analysis-distributions-fourier/) explains the reading path and boundaries.

The [Mathematical Conventions](/math-toolkit/conventions/) page fixes the Fourier-transform signs, delta-function normalization, and principal-value convention used here.

The later Delta Functions page should specialize the present material to evaluation distributions, constraint deltas, Jacobians, and phase-space identities. The later Fourier Transform Conventions page should make the momentum-space rules used here systematic across Lorentzian, Euclidean, spatial, and finite-volume settings.

## Research status

The core theory of distributions is established mathematics. Its role in QFT is also established: fields, propagators, commutators, and many singular kernels are naturally distributional.

The active and delicate part is not the definition of distributions themselves. It is what one does with singular distributions: products, restrictions, nonlinear functions, renormalized extensions, wavefront-set control, gauge-theoretic constraints, and operator-valued versions in interacting QFT.

For ordinary perturbative calculations, the practical rule is to regulate, compute with a consistent prescription, subtract or renormalize local singularities, and state the remaining convention-dependent choices. For rigorous QFT, the rule is harsher: define the objects on a domain or test-function space before manipulating them.

## Exercises

### Exercise 1: Distributional derivative of a regular distribution

Let $f\in C^1(\mathbb R)$ and let $T_f$ be the associated distribution. Show that $\frac{d}{dx}T_f=T_{f'}$.

<details>
<summary><strong>Solution</strong></summary>

For every test function $\varphi$,

$$
\left\langle\frac{dT_f}{dx},\varphi\right\rangle
=-\langle T_f,\varphi'\rangle
=-\int_{\mathbb R}dx\,f(x)\varphi'(x).
$$

Since $\varphi$ has compact support, the boundary term vanishes under integration by parts:

$$
-\int dx\,f\varphi'
=\int dx\,f'\varphi
=\langle T_{f'},\varphi\rangle.
$$

Therefore $dT_f/dx=T_{f'}$ as distributions.

</details>

### Exercise 2: Scaling of the delta distribution

For $a\neq0$, prove

$$
\delta(ax)=\frac{1}{|a|}\delta(x)
$$

as distributions on $\mathbb R$.

<details>
<summary><strong>Solution</strong></summary>

Pair the left-hand side with a test function $\varphi$:

$$
\int_{\mathbb R}dx\,\delta(ax)\varphi(x).
$$

Set $u=ax$, so $dx=du/a$ if $a>0$ and $dx=du/a$ with reversed limits if $a<0$. In either case the absolute Jacobian appears:

$$
\int dx\,\delta(ax)\varphi(x)
=\frac{1}{|a|}\int du\,\delta(u)\varphi(u/a)
=\frac{1}{|a|}\varphi(0).
$$

This is the pairing of $|a|^{-1}\delta(x)$ with $\varphi$.

</details>

### Exercise 3: Derivative of a step function

Let $\theta(x)$ be $1$ for $x>0$ and $0$ for $x<0$. Show that $\theta'=\delta$ distributionally.

<details>
<summary><strong>Solution</strong></summary>

For every test function $\varphi$,

$$
\langle\theta',\varphi\rangle
=-\langle\theta,\varphi'\rangle
=-\int_0^\infty dx\,\varphi'(x).
$$

Because $\varphi$ has compact support, $\varphi(x)=0$ for sufficiently large $x$. Hence

$$
-\int_0^\infty dx\,\varphi'(x)
=-(0-\varphi(0))
=\varphi(0)
=\langle\delta,\varphi\rangle.
$$

Thus $\theta'=\delta$.

</details>

### Exercise 4: The Coulomb Green function

In $\mathbb R^3$, show that

$$
-\Delta\frac{1}{4\pi r}=\delta^{(3)}(x),
\qquad r=|x|,
$$

as distributions.

<details>
<summary><strong>Solution</strong></summary>

Let $G(x)=1/(4\pi r)$ and let $\varphi\in C_c^\infty(\mathbb R^3)$. Since $G$ is harmonic away from $0$, integrate over $\mathbb R^3\setminus B_\epsilon$ and use Green's identity:

$$
\langle-\Delta G,\varphi\rangle
=\lim_{\epsilon\to0}\int_{r>\epsilon}d^3x\,G(-\Delta\varphi).
$$

Integrating by parts twice and using $\Delta G=0$ for $r>0$ leaves only the boundary term on the small sphere. The outward normal for the region $r>\epsilon$ at the inner boundary points toward the origin, so $n=-\hat r$. The leading contribution is

$$
\lim_{\epsilon\to0}\int_{r=\epsilon}dS\,\varphi\,\partial_r G\,(-1)
=
\lim_{\epsilon\to0}\int_{r=\epsilon}dS\,\varphi\,\frac{1}{4\pi\epsilon^2}.
$$

Since $dS=\epsilon^2d\Omega$ and $\varphi(\epsilon\hat r)\to\varphi(0)$,

$$
\lim_{\epsilon\to0}\frac{1}{4\pi}\int d\Omega\,\varphi(\epsilon\hat r)
=\varphi(0).
$$

Therefore $-\Delta G$ has the same pairing as $\delta^{(3)}(x)$.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for delta functions, Fourier transforms, Green functions, propagator normalizations, and the distributional notation used in perturbative QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical Green-function, propagator, $i\epsilon$, and operator-product identities in calculations.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for the role of delta functions, principal values, relativistic normalization, and distributions in scattering and field theory.

### Deeper references

- L. Schwartz, *Théorie des distributions*, for the original systematic development of distributions.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for generalized functions and Fourier transforms.
- F. G. Friedlander and M. Joshi, *Introduction to the Theory of Distributions*, for a readable mathematical introduction.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for singular support, wavefront sets, and the microlocal language behind restrictions and products.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the operator-valued distribution viewpoint in axiomatic QFT.

## Version history

- **2026-06-23:** Initial polished draft. Introduced distributions, delta functions, distributional derivatives, tempered distributions, principal values, Green functions, QFT smearing, contact terms, and local exercises with solutions.
