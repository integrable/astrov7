---
title: "Test Functions and Tempered Distributions"
description: "A QFT-oriented guide to compactly supported test functions, Schwartz functions, supports, singular supports, tempered distributions, and distributional Fourier transforms."
sidebar:
  label: "Test Functions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard distribution theory and Fourier analysis, with QFT applications to smearing, momentum space, propagators, and operator-valued distributions."
topics:
  - test functions
  - Schwartz functions
  - tempered distributions
  - Fourier transforms
  - supports
canonicalTopics:
  - test-functions
  - schwartz-space
  - tempered-distributions
  - distributional-fourier-transform
researchStatus:
  established:
    - "Compactly supported test functions, Schwartz functions, distributions, and tempered distributions are standard analytic frameworks for making singular QFT expressions meaningful."
  active:
    - "Beyond the tempered setting, modern QFT often needs microlocal control, non-Schwartz boundary behavior, gauge-invariant smearing, curved-spacetime test spaces, and renormalized products of distributions."
---

## Summary

A distribution is not defined in isolation. It is defined by the class of test functions it is allowed to eat. Changing the test-function space changes the distribution space, the topology, the allowed singular behavior, and the Fourier-transform theory.

The two test-function spaces used most often in QFT are:

$$
\mathcal D(\Omega)=C_c^\infty(\Omega),
$$

the smooth functions with compact support in an open region $\Omega$, and

$$
\mathcal S(\mathbb R^d),
$$

the Schwartz functions, which are smooth and decay faster than any inverse power together with all derivatives.

Their continuous duals are

$$
\mathcal D'(\Omega)=\text{all distributions on }\Omega,
\qquad
\mathcal S'(\mathbb R^d)=\text{tempered distributions}.
$$

The crucial flat-space fact is that the Fourier transform is an automorphism of $\mathcal S$ and of $\mathcal S'$. This is why momentum-space QFT is usually formulated with tempered distributions.

<figure class="doc-figure" style="--figure-width: 36rem;">

![Diagram showing compactly supported test functions, Schwartz functions, all distributions, and tempered distributions, with inclusions and dual arrows.](/figures/math-toolkit/test-function-spaces.svg)

<figcaption>

The inclusion $\mathcal D\subset\mathcal S$ reverses on duals: every tempered distribution restricts to an ordinary distribution, so $\mathcal S'\subset\mathcal D'$. The Fourier transform preserves $\mathcal S$ and $\mathcal S'$, not $\mathcal D$ and $\mathcal D'$.

</figcaption>
</figure>

## Prerequisites

You should know the basic definition of a distribution from [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and the normalization of the delta distribution from [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/). The Fourier conventions used here agree with [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

No measure theory is required for a first reading. The only analytic idea you need is continuity: a distribution should respond continuously when the test function is changed slightly in the relevant sense.

## Core idea

The slogan is:

$$
\text{distribution} = \text{continuous linear functional on a chosen test-function space}.
$$

The phrase "chosen test-function space" is doing real work. For example, a locally integrable function $F$ defines an ordinary distribution on $\mathbb R^d$ by

$$
\langle T_F,\varphi\rangle=\int d^dx\,F(x)\varphi(x),
\qquad \varphi\in C_c^\infty(\mathbb R^d),
$$

provided the integral is finite on every compact set. This allows very fast growth at infinity, because $\varphi$ vanishes outside a compact region.

The same formula defines a tempered distribution only if $F$ has sufficiently controlled growth at infinity. The function $e^{x^2}$ is locally integrable and therefore defines an ordinary distribution on $\mathbb R$, but it does not define a tempered distribution because Schwartz test functions need not decay exponentially enough to make

$$
\int_{-\infty}^{\infty}dx\,e^{x^2}\varphi(x)
$$

finite.

That distinction matters in QFT. Ultraviolet singularities are local and are visible already to compactly supported tests. Momentum-space methods also require control at infinity, and that is what Schwartz functions and tempered distributions provide.

## Setup and conventions

Let $\Omega\subset\mathbb R^d$ be open. A multi-index is

$$
\alpha=(\alpha_1,\ldots,\alpha_d),
\qquad
|\alpha|=\alpha_1+\cdots+\alpha_d,
$$

and

$$
\partial^\alpha
=\partial_1^{\alpha_1}\cdots\partial_d^{\alpha_d},
\qquad
x^\alpha=x_1^{\alpha_1}\cdots x_d^{\alpha_d}.
$$

Pairings of distributions with test functions are written

$$
\langle T,\varphi\rangle.
$$

This pairing is linear in the test function. We use no complex conjugation in the distributional pairing unless explicitly discussing Hilbert-space inner products. Thus

$$
\langle \delta_a,\varphi\rangle=\varphi(a),
\qquad
\langle \partial_i T,\varphi\rangle=-\langle T,\partial_i\varphi\rangle.
$$

For Fourier transforms on $\mathbb R^d$, we use

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\int_k=\int\frac{d^dk}{(2\pi)^d}.
$$

## Compactly supported test functions

The space

$$
\mathcal D(\Omega)=C_c^\infty(\Omega)
$$

consists of smooth functions whose support is compact and contained in $\Omega$.

The support of a function is the closure of the set where it is nonzero:

$$
\operatorname{supp}\varphi
=\overline{\{x\in\Omega\mid \varphi(x)\neq0\}}.
$$

Compact support means that $\varphi$ is exactly zero outside a bounded closed region, not merely small there. This makes integration by parts painless: all boundary terms at infinity vanish.

A standard one-dimensional bump is

$$
\eta(x)=
\begin{cases}
\exp\!\left(-\frac{1}{1-x^2}\right),& |x|<1,\\
0,& |x|\ge1.
\end{cases}
$$

It is not analytic at $x=\pm1$, but it is $C^\infty$. Every derivative vanishes at the boundary because the exponential goes to zero faster than any inverse power of $1-x^2$.

Compactly supported tests are the right local probes. If you want to know whether a distribution has a singularity near a point, you test it with functions supported in a tiny neighborhood of that point. This is why $\mathcal D$ is the natural home for local distribution theory.

## The topology behind continuity

A linear functional on $C_c^\infty$ is not automatically a distribution. It must be continuous in the test-function topology.

For a fixed compact set $K\subset\Omega$, a sequence $\varphi_n\in C_c^\infty(\Omega)$ supported inside $K$ converges to zero if every derivative converges uniformly to zero on $K$:

$$
\sup_{x\in K}|\partial^\alpha\varphi_n(x)|\to0
\qquad\text{for every multi-index }\alpha.
$$

A distribution $T\in\mathcal D'(\Omega)$ is a linear functional such that, locally on every compact set $K$, there exist constants $C_K$ and $N_K$ with

$$
|\langle T,\varphi\rangle|
\le C_K\sum_{|\alpha|\le N_K}\sup_{x\in K}|\partial^\alpha\varphi(x)|
$$

for all $\varphi$ supported in $K$.

This estimate is the sober version of "$T$ is no worse than finitely many derivatives on each compact set." It rules out pathological linear functionals that depend discontinuously on infinitely fine information in the test function.

The order of a distribution on $K$ is the smallest such $N_K$, if one exists. The delta distribution has order $0$ because

$$
|\langle\delta_a,\varphi\rangle|=|\varphi(a)|\le\sup_K|\varphi|
$$

when $a\in K$. The derivative $\partial_i\delta_a$ has order $1$ because

$$
|\langle\partial_i\delta_a,\varphi\rangle|
=|\partial_i\varphi(a)|.
$$

## Ordinary distributions

The space $\mathcal D'(\Omega)$ is the continuous dual of $\mathcal D(\Omega)$. It contains:

| Object | Pairing |
|---|---|
| Locally integrable function $F$ | $\langle T_F,\varphi\rangle=\int_\Omega d^dx\,F(x)\varphi(x)$ |
| Delta distribution at $a$ | $\langle\delta_a,\varphi\rangle=\varphi(a)$ |
| Derivative of delta | $\langle\partial^\alpha\delta_a,\varphi\rangle=(-1)^{|\alpha|}\partial^\alpha\varphi(a)$ |
| Principal value | $\left\langle\operatorname{PV}\frac1x,\varphi\right\rangle=\lim_{\epsilon\to0^+}\int_{|x|>\epsilon}dx\,\frac{\varphi(x)}{x}$ |
| Finite linear combinations of derivatives | Defined by repeated integration by parts |

The locally integrable example is extremely important. It means that ordinary functions are embedded in distributions, but the embedding forgets pointwise changes on sets of measure zero. If $F$ and $G$ are equal almost everywhere, then

$$
T_F=T_G.
$$

Distributions also include objects that do not come from locally integrable functions, such as $\delta$ and its derivatives.

## Support of a distribution

A distribution $T$ vanishes on an open set $U\subset\Omega$ if

$$
\langle T,\varphi\rangle=0
$$

for every $\varphi\in C_c^\infty(U)$.

The support of $T$ is the complement of the largest open set on which $T$ vanishes:

$$
\operatorname{supp}T
=\Omega\setminus\bigcup\{U\subset\Omega\text{ open}\mid T\text{ vanishes on }U\}.
$$

Examples:

$$
\operatorname{supp}\delta_a=\{a\},
\qquad
\operatorname{supp}\partial^\alpha\delta_a=\{a\}.
$$

If $F$ is an ordinary continuous function, the support of $T_F$ agrees with the closure of the set where $F\neq0$. If $F$ is only locally integrable, the distributional support ignores changes on measure-zero sets.

A distribution with compact support is especially well behaved. Derivatives of deltas, finite sums of point-supported distributions, and compactly supported locally integrable functions are examples. Compact support is one of the main hypotheses that makes convolution of distributions unambiguous.

## Singular support

The support of a distribution tells you where it is nonzero. The singular support tells you where it fails to be smooth.

A distribution $T$ is smooth on an open set $U$ if there exists a smooth function $f\in C^\infty(U)$ such that

$$
\langle T,\varphi\rangle=\int_U d^dx\,f(x)\varphi(x)
$$

for all $\varphi\in C_c^\infty(U)$. The singular support of $T$ is the complement of the largest open set on which this is true.

Examples:

$$
\operatorname{sing\,supp}\delta_0=\{0\},
\qquad
\operatorname{sing\,supp}\frac1{|x|}=\{0\}
\quad\text{in }\mathbb R^d\text{ when locally integrable}.
$$

For QFT, singular support identifies coincident-point singularities. A two-point function $G(x,y)$ may be smooth away from $x=y$ but singular on the diagonal. Contact terms are distributions supported on that diagonal.

Singular support is still not the full story. It says where a distribution is singular, but not in which covector directions it is singular. That sharper information is the wavefront set, which becomes essential for products and restrictions of distributions in rigorous perturbation theory.

## Schwartz functions

A Schwartz function is a smooth function that decays faster than any inverse power, together with all of its derivatives. The space is denoted

$$
\mathcal S(\mathbb R^d).
$$

Explicitly, $\varphi\in\mathcal S(\mathbb R^d)$ if for every pair of multi-indices $\alpha,\beta$,

$$
p_{\alpha\beta}(\varphi)
=\sup_{x\in\mathbb R^d}|x^\alpha\partial^\beta\varphi(x)|<\infty.
$$

The quantities $p_{\alpha\beta}$ are seminorms. They define the Schwartz topology.

Examples:

$$
e^{-|x|^2}\in\mathcal S(\mathbb R^d),
\qquad
C_c^\infty(\mathbb R^d)\subset\mathcal S(\mathbb R^d).
$$

Nonexamples:

$$
\frac{1}{1+|x|^2}\notin\mathcal S(\mathbb R^d),
\qquad
1\notin\mathcal S(\mathbb R^d),
\qquad
e^{ik\cdot x}\notin\mathcal S(\mathbb R^d).
$$

The last line is a useful warning: plane waves are not test functions. They are idealized generalized modes. In QFT one often writes plane waves freely, but the distributional meaning is recovered by smearing wave packets or by working in finite volume before taking the continuum limit.

## Tempered distributions

A tempered distribution is a continuous linear functional on $\mathcal S(\mathbb R^d)$:

$$
\mathcal S'(\mathbb R^d)=\text{continuous dual of }\mathcal S(\mathbb R^d).
$$

Equivalently, $T\in\mathcal S'$ if there exist constants $C$, $N$, and $M$ such that

$$
|\langle T,\varphi\rangle|
\le C\sum_{|\alpha|\le N,\,|\beta|\le M}
\sup_x |x^\alpha\partial^\beta\varphi(x)|
$$

for all $\varphi\in\mathcal S(\mathbb R^d)$.

The word "tempered" means polynomially controlled at infinity. It does not mean nonsingular. The delta distribution is tempered. Its derivatives are tempered. Principal values such as $\operatorname{PV}(1/x)$ are tempered. Polynomially bounded locally integrable functions define tempered distributions.

A useful sufficient condition is: if $F$ is locally integrable and there exist $C,N$ such that

$$
|F(x)|\le C(1+|x|)^N
$$

for large $|x|$, then

$$
\langle T_F,\varphi\rangle=\int d^dx\,F(x)\varphi(x)
$$

defines a tempered distribution.

Fast growth can break temperedness. The function $e^{x^2}$ defines an ordinary distribution on $\mathbb R$ because compactly supported tests make the pairing finite. It does not define a tempered distribution, since the Schwartz function $e^{-x^2}$ would produce a divergent integral.

## Why tempered distributions are natural in flat-space QFT

Flat-space QFT uses momentum space everywhere: free-field mode expansions, propagators, Feynman rules, spectral representations, phase space, loop integrals, and response functions. For this to be clean, Fourier transformation must preserve the class of objects under study.

The Schwartz space has exactly this property:

$$
\mathcal F:\mathcal S(\mathbb R^d)\to\mathcal S(\mathbb R^d)
$$

is a continuous bijection with continuous inverse. By duality,

$$
\mathcal F:\mathcal S'(\mathbb R^d)\to\mathcal S'(\mathbb R^d)
$$

is also an isomorphism.

This makes identities like

$$
\widehat{\partial_i T}(k)=ik_i\widehat T(k),
\qquad
\widehat{x_iT}(k)=i\partial_{k_i}\widehat T(k)
$$

well-defined for tempered distributions.

Many standard QFT objects are tempered distributions after the usual prescriptions are included:

$$
\delta^{(d)}(x),
\qquad
\operatorname{PV}\frac1x,
\qquad
\frac{1}{p^2-m^2+i0},
\qquad
\theta(\pm p^0)\delta(p^2-m^2).
$$

The qualifier "many" matters. Finite-temperature, finite-density, curved-spacetime, massless infrared, and gauge-fixed systems can force extra care. Temperedness is the right default in flat-space perturbative QFT, not a universal law of nature.

## Distributional Fourier transform

For an ordinary Schwartz function,

$$
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x).
$$

For a tempered distribution $T$, the Fourier transform is defined by duality: $\widehat T$ is the distribution whose action reproduces the ordinary formula whenever $T=T_f$ comes from an integrable function.

With the convention above, this can be written as

$$
\langle\widehat T,\varphi\rangle
=\left\langle T,\int d^dk\,e^{-ik\cdot x}\varphi(k)\right\rangle.
$$

The expression in the second slot is a Schwartz function of $x$ when $\varphi$ is a Schwartz function of $k$. The factors of $2\pi$ live in the inverse transform, not in this dual formula.

The basic examples are

$$
\widehat{\delta^{(d)}(x)}=1,
\qquad
\widehat{1}=(2\pi)^d\delta^{(d)}(k),
$$

and

$$
\widehat{\delta^{(d)}(x-a)}=e^{-ik\cdot a}.
$$

These identities are not pointwise evaluations of divergent integrals. They are equalities in $\mathcal S'$.

## Cutoffs, mollifiers, and approximate identities

Test functions are not only passive probes. They also build regulators.

Let $\rho\in\mathcal S(\mathbb R^d)$ satisfy

$$
\int d^dx\,\rho(x)=1,
$$

and define

$$
\rho_\epsilon(x)=\frac{1}{\epsilon^d}\rho\!\left(\frac{x}{\epsilon}\right).
$$

Then $\rho_\epsilon\to\delta$ distributionally. Convolution with $\rho_\epsilon$ smooths a function or distribution:

$$
T_\epsilon=T*\rho_\epsilon.
$$

For each fixed $\epsilon>0$, $T_\epsilon$ is much better behaved than $T$. As $\epsilon\to0$, the singularities return. This is the distribution-theory model for a regulator: smooth first, compute, then understand the limit.

A smooth cutoff works similarly. Instead of imposing a hard condition like $|p|<\Lambda$, one often inserts a smooth rapidly decreasing factor such as

$$
\chi_\Lambda(p)=\chi(p/\Lambda),
$$

where $\chi$ is $1$ near the origin and decays or vanishes at large momentum. Smooth cutoffs avoid spurious boundary singularities and behave better under integrations by parts.

## Locality and partitions of unity

Compactly supported test functions let one localize a question. If $\{U_i\}$ is an open cover of a region, a partition of unity is a collection of smooth functions $\{\chi_i\}$ such that

$$
0\le\chi_i\le1,
\qquad
\operatorname{supp}\chi_i\subset U_i,
\qquad
\sum_i\chi_i=1
$$

locally finitely. Then a test function can be decomposed as

$$
\varphi=\sum_i\chi_i\varphi.
$$

This is the analytic mechanism behind many local-to-global arguments. In QFT language, it is why a counterterm, contact term, or Ward-identity anomaly can be checked in coordinate patches and then assembled globally, provided the geometry and symmetry data patch consistently.

Partitions of unity also explain why local distribution theory does not care about behavior at infinity. If a question is truly local, compactly supported tests are enough.

## Operator-valued distributions

Quantum fields are not operator-valued functions of spacetime. They are operator-valued distributions. The expression $\phi(x)$ is a symbolic density; the honest object is smeared:

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

where $f$ is a suitable test function.

For a Wightman field on Minkowski space, one typically smears with Schwartz functions. Correlators such as

$$
\langle0|\phi(x_1)\cdots\phi(x_n)|0\rangle
$$

are then tempered distributions in the variables $x_1,\ldots,x_n$ under standard assumptions. This is what makes momentum-space Wightman functions and spectral conditions meaningful.

The test-function choice encodes physics. Compactly supported test functions are natural for local algebras and causal localization. Schwartz functions are natural for scattering wave packets and Fourier analysis. Gauge theories, constrained systems, and curved spacetimes often require extra structure because not every smearing respects the physical state space or gauge-invariant observable algebra.

## Which test space should you use?

Use this rough guide.

| Goal | Natural test space | Reason |
|---|---|---|
| Local singularity, contact term, PDE identity | $C_c^\infty(\Omega)$ | Localizes the question and kills boundary terms. |
| Flat-space momentum transform | $\mathcal S(\mathbb R^d)$ | Fourier transform preserves the space. |
| Compactly supported source | $C_c^\infty$ or smooth compact support in time/space | Good for causal response and local perturbations. |
| Scattering wave packet | Schwartz or suitable wave-packet space | Controls momentum tails and avoids plane-wave idealizations. |
| Periodic finite volume | Smooth functions on a torus | Momentum becomes a discrete Fourier series. |
| Curved spacetime local QFT | Compactly supported smooth sections | Local covariance and causal support matter more than global Fourier transforms. |

For most graduate QFT calculations on $\mathbb R^d$, the practical rhythm is: use compactly supported tests to define local singular expressions, then use Schwartz tests to Fourier transform them.

## Common pitfalls

**Treating plane waves as test functions.** Plane waves are useful generalized modes, but they are not in $\mathcal S$ and not in $C_c^\infty$. A formula involving plane waves usually means a distributional identity or a limit of wave packets.

**Forgetting that the dual depends on the test space.** A functional that is continuous on $C_c^\infty$ need not be continuous on $\mathcal S$. Exponential growth at infinity is invisible to compactly supported tests but visible to Schwartz tests.

**Confusing support with singular support.** The distribution $1/(1+x^2)$ has support all of $\mathbb R$ but empty singular support. The delta distribution has support and singular support both equal to one point.

**Assuming all QFT distributions are tempered.** Tempered distributions are the right default for flat-space momentum-space QFT. They are not guaranteed in every physical setting, especially in curved spacetime, non-equilibrium systems, or theories with delicate infrared behavior.

**Multiplying distributions because their test spaces look nice.** Test functions make linear pairings safe. They do not automatically make nonlinear products of singular distributions safe. Products require additional hypotheses, regularization, or renormalization.

## Relations to other pages

[Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) gives the basic definition and examples. [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) treats the most important point-supported distribution. [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) fixes the transform normalizations that make $\mathcal S'$ useful in momentum space.

The next natural page is [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), where test functions become smoothing kernels, approximate identities, Green-function kernels, and translation-invariant operators.

## Research status

The material on $C_c^\infty$, $\mathcal S$, $\mathcal D'$, and $\mathcal S'$ is established mathematics. Its role in QFT as the baseline language of smearing and Fourier transformation is also established.

The active frontier begins when one asks which products, restrictions, pullbacks, time orderings, boundary values, and renormalized extensions of distributions are allowed. In perturbative algebraic QFT and curved-spacetime QFT, this is controlled by microlocal analysis and wavefront sets. In gauge theory, the correct test spaces are constrained by gauge invariance, BRST cohomology, and the observable algebra.

## Exercises

### Exercise 1: A bump function is smooth

Let

$$
\eta(x)=
\begin{cases}
\exp\!\left(-\frac{1}{1-x^2}\right),& |x|<1,\\
0,& |x|\ge1.
\end{cases}
$$

Explain why $\eta\in C_c^\infty(\mathbb R)$.

<details>
<summary><strong>Solution</strong></summary>

The support is contained in $[-1,1]$, so it is compact. Smoothness is obvious for $|x|<1$ and for $|x|>1$. The only issue is $x=\pm1$.

Near $x=1$ set $u=1-x^2$. For $u>0$ the function is $e^{-1/u}$. Every derivative has the form

$$
P(1/u)e^{-1/u}
$$

for some polynomial $P$ in $1/u$, times smooth factors from differentiating $u$. Since $e^{-1/u}$ goes to zero faster than any power of $u$ as $u\to0^+$, every derivative tends to zero at the boundary. The same argument applies at $x=-1$.

Thus the extension by zero is smooth and compactly supported.

</details>

### Exercise 2: Delta is tempered

Show that $\delta_a$ and $\partial^\alpha\delta_a$ are tempered distributions on $\mathbb R^d$.

<details>
<summary><strong>Solution</strong></summary>

For $\delta_a$,

$$
|\langle\delta_a,\varphi\rangle|=|\varphi(a)|.
$$

A Schwartz seminorm controls this value. For example,

$$
|\varphi(a)|\le\sup_x|\varphi(x)|.
$$

For a derivative,

$$
|\langle\partial^\alpha\delta_a,\varphi\rangle|
=|\partial^\alpha\varphi(a)|
\le\sup_x|\partial^\alpha\varphi(x)|.
$$

This is one of the defining seminorms of $\mathcal S$. Hence both functionals are continuous on $\mathcal S$.

</details>

### Exercise 3: Polynomial growth gives a tempered distribution

Suppose $F$ is locally integrable and

$$
|F(x)|\le C(1+|x|)^N
$$

for large $|x|$. Show that $F$ defines a tempered distribution.

<details>
<summary><strong>Solution</strong></summary>

Choose $M>N+d+1$. For a Schwartz test function $\varphi$,

$$
|F(x)\varphi(x)|
\le C'(1+|x|)^N|\varphi(x)|.
$$

Insert

$$
|\varphi(x)|\le \frac{p_M(\varphi)}{(1+|x|)^M},
\qquad
p_M(\varphi)=\sup_x(1+|x|)^M|\varphi(x)|.
$$

Then

$$
\int d^dx\,|F(x)\varphi(x)|
\le C'p_M(\varphi)\int d^dx\,(1+|x|)^{N-M}.
$$

The last integral converges because $M>N+d$. Therefore the pairing is bounded by a Schwartz seminorm, so $F$ defines a continuous linear functional on $\mathcal S$.

</details>

### Exercise 4: Support of a derivative

Show that

$$
\operatorname{supp}(\partial_iT)\subseteq\operatorname{supp}T.
$$

<details>
<summary><strong>Solution</strong></summary>

Let $U$ be an open set on which $T$ vanishes. For every $\varphi\in C_c^\infty(U)$,

$$
\langle\partial_iT,\varphi\rangle
=-\langle T,\partial_i\varphi\rangle.
$$

Since $\partial_i\varphi$ is also in $C_c^\infty(U)$, the right-hand side vanishes. Thus $\partial_iT$ vanishes on every open set where $T$ vanishes. Therefore the support of $\partial_iT$ is contained in the support of $T$.

</details>

### Exercise 5: A locally integrable distribution that is not tempered

Show that $F(x)=e^{x^2}$ defines an ordinary distribution on $\mathbb R$ but not a tempered distribution by the same integral formula.

<details>
<summary><strong>Solution</strong></summary>

For every compactly supported smooth $\varphi$, the integral

$$
\int dx\,e^{x^2}\varphi(x)
$$

is finite, because $e^{x^2}$ is locally integrable and the support of $\varphi$ is compact. Thus $F$ defines an element of $\mathcal D'(\mathbb R)$.

For a tempered distribution defined by the same integral formula, the integral would have to be finite for every Schwartz function. But $\varphi(x)=e^{-x^2}$ is Schwartz, and

$$
\int_{-\infty}^{\infty}dx\,e^{x^2}e^{-x^2}
=\int_{-\infty}^{\infty}dx
$$

diverges. Therefore $e^{x^2}$ does not define a tempered distribution by this pairing.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for the use of distributions, Fourier transforms, and wave-packet normalizations in standard perturbative QFT.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for practical distributional manipulations in propagators, path integrals, and operator products.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for the role of tempered distributions, spectral conditions, and momentum-space normalization in relativistic QFT.

### Deeper references

- L. Schwartz, *Théorie des distributions*, for the original construction of distribution theory.
- I. M. Gel'fand and G. E. Shilov, *Generalized Functions*, Vol. I, for test-function spaces, generalized functions, and Fourier transforms.
- F. G. Friedlander and M. Joshi, *Introduction to the Theory of Distributions*, for a clear mathematical introduction to $C_c^\infty$, distributions, supports, and Fourier transforms.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for wavefront sets, singular support, pullbacks, and products of distributions.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for quantum fields as operator-valued distributions.

## Version history

- **2026-06-23:** Initial polished draft. Added compactly supported tests, Schwartz functions, supports, singular supports, tempered distributions, distributional Fourier transforms, mollifiers, QFT smearing, and exercises with solutions.
