---
title: "Asymptotic Series"
description: "Explains asymptotic expansions, asymptotic scales, divergent but useful series, remainder estimates, optimal truncation, flat functions, Watson's lemma, saddle expansions, and QFT uses."
sidebar:
  label: "Asymptotic Series"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard references on asymptotic analysis and QFT perturbation theory, including Poincaré, Watson, Hardy, Dingle, Olver, Bender–Orszag, Berry–Howls, Zinn-Justin, Weinberg, Srednicki, Schwartz, Zee, Mariño, and Shifman."
topics:
  - asymptotic series
  - divergent series
  - asymptotic scale
  - remainder estimate
  - optimal truncation
  - Watson lemma
  - saddle expansion
  - perturbation theory
  - nonperturbative correction
canonicalTopics:
  - asymptotic-series
  - divergent-series
  - asymptotic-scale
  - remainder-estimate
  - optimal-truncation
  - watson-lemma
  - saddle-expansion
  - perturbation-theory
  - nonperturbative-correction
researchStatus:
  established:
    - "Poincaré asymptotic expansions, asymptotic scales, Watson's lemma, integration-by-parts expansions, and optimal truncation are standard tools in asymptotic analysis."
    - "Perturbative QFT expansions are generally treated as formal or asymptotic series, and finite-order truncations can be predictive even when the infinite series diverges."
  active:
    - "The precise large-order structure of QFT perturbation theory, its relation to saddles, renormalons, Borel singularities, transseries, and nonperturbative definitions remains an active research area."
---

## Summary

An asymptotic series is a finite-order approximation machine, not necessarily an infinite sum. When we write

$$
F(g)\sim \sum_{n=0}^{\infty} a_n g^n,
\qquad g\to0,
$$

we are saying that successive finite partial sums approximate $F(g)$ with a controlled hierarchy of errors as $g$ becomes small. We are not promising that the series converges for fixed nonzero $g$. In QFT, that distinction is not a technical footnote. It is the difference between using perturbation theory honestly and asking it to do magic.

The practical rule is:

$$
\text{use finitely many terms, estimate the remainder, stop before the series turns against you.}
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Diagram of asymptotic terms that first decrease, reach a least term, then grow, with optimal truncation near the least term and exponentially small remainder.](/figures/math-toolkit/asymptotic-series-optimal-truncation.svg)

<figcaption>

A typical factorially divergent asymptotic series has terms that first decrease and then grow. The best finite approximation at fixed small $g$ usually comes from truncating near the least term. The error is then often of the same order as the least term, frequently an exponentially small scale such as $e^{-A/g}$.

</figcaption>
</figure>

This page explains the definition, why divergent asymptotic series can be useful, how remainders work, why exponentially small terms are invisible to ordinary power expansions, and how this logic appears in QFT.

## Prerequisites and conventions

You should know big-$O$ and little-$o$ notation, elementary complex analysis, Taylor series, Gaussian integrals, and the basic idea of a saddle-point approximation. Useful nearby pages are [Gamma and Beta Functions](/math-toolkit/special-functions-exact-equations/gamma-and-beta-functions/), [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/), [Saddle Points](/math-toolkit/complex-analysis/saddle-points/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

Throughout this page, $g$ denotes a small positive parameter unless another limit is stated. The same definitions apply to $x\to0$, $\lambda\to\infty$, $\hbar\to0$, large quantum number $n$, short proper time $s\to0^+$, or large momentum $|p|\to\infty$ after translating the asymptotic scale.

## The definition

Let $\{\phi_n(g)\}_{n\ge0}$ be an **asymptotic scale** as $g\to0^+$, meaning

$$
\phi_{n+1}(g)=o(\phi_n(g))
\qquad (g\to0^+).
$$

For the ordinary power scale, $\phi_n(g)=g^n$, this says

$$
g^{n+1}=o(g^n).
$$

We write

$$
F(g)\sim \sum_{n=0}^{\infty} a_n\phi_n(g)
$$

if, for every $N\ge1$,

$$
F(g)-\sum_{n=0}^{N-1}a_n\phi_n(g)=o(\phi_{N-1}(g))
\qquad (g\to0^+).
$$

For power series, one often uses the slightly sharper form

$$
F(g)-\sum_{n=0}^{N-1}a_n g^n=O(g^N).
$$

The important phrase is **for every fixed $N$**. The definition does not say that $N$ can be sent to infinity at fixed $g$. Asymptotic expansions are statements about two operations that do not commute:

$$
\text{take }g\to0
\qquad\text{and}\qquad
\text{take more terms}.
$$

Convergent Taylor series are special because taking more terms at fixed $g$ makes sense inside a disk of convergence. Asymptotic series are more general. They can diverge and still provide better and better approximations for a while.

:::note[Language]
A finite expression

$$
\sum_{n=0}^{N-1}a_n g^n
$$

is an **asymptotic approximation of order $N$**. The infinite symbol $\sum_{n=0}^{\infty}a_n g^n$ is often a compact record of all finite-order approximations. It is not automatically a function.
:::

## Coefficients are unique, functions are not

Once the asymptotic scale is fixed, the coefficients are unique. Suppose

$$
F(g)\sim \sum_{n=0}^{\infty}a_n\phi_n(g)
\sim \sum_{n=0}^{\infty}b_n\phi_n(g).
$$

Subtracting the two expansions and taking the first nonzero coefficient would violate the hierarchy $\phi_{n+1}=o(\phi_n)$. Thus $a_n=b_n$ for all $n$.

But the function is not unique. For the power scale $g^n$ as $g\to0^+$,

$$
e^{-1/g}=o(g^N)
$$

for every $N$. Therefore $F(g)$ and

$$
F(g)+C e^{-1/g}
$$

have the same power asymptotic expansion for every constant $C$.

This is the simplest example of a **beyond-all-orders** effect. It is smaller than every power of $g$ near the expansion point, so no ordinary perturbative coefficient can detect it.

In QFT, such effects are not rare decorations. They are the natural size of instanton effects, tunneling splittings, complex-saddle contributions, finite-action Euclidean configurations, and many nonperturbative ambiguities. Perturbation theory can gesture toward them through large-order growth, but the ordinary power expansion alone cannot determine their coefficients.

## A divergent asymptotic series that works

Consider

$$
I(g)=\int_0^\infty dt\,\frac{e^{-t}}{1+gt},
\qquad g>0.
$$

For fixed $t$ and small $g$,

$$
\frac{1}{1+gt}=1-gt+g^2t^2-g^3t^3+\cdots.
$$

If we integrate term by term formally, we get

$$
I(g)\sim \sum_{n=0}^{\infty}(-1)^n n!\,g^n,
$$

because

$$
\int_0^\infty dt\,e^{-t}t^n=n!.
$$

This series diverges for every nonzero $g$, since the terms $n!g^n$ eventually grow. Yet it is asymptotic. The finite geometric identity

$$
\frac{1}{1+gt}
=
\sum_{n=0}^{N-1}(-gt)^n+\frac{(-gt)^N}{1+gt}
$$

gives

$$
I(g)-\sum_{n=0}^{N-1}(-1)^n n!\,g^n
=
(-g)^N\int_0^\infty dt\,\frac{e^{-t}t^N}{1+gt}.
$$

Since $1+gt\ge1$ for $g,t>0$,

$$
\left|I(g)-\sum_{n=0}^{N-1}(-1)^n n!\,g^n\right|
\le g^N N!.
$$

For each fixed $N$, this is $O(g^N)$ as $g\to0^+$. That is exactly the asymptotic property. The infinite series is divergent; the finite approximations are useful.

This example is a toy model of QFT perturbation theory. Expanding the integrand creates factorial coefficients, finite-order truncations are meaningful, and the infinite perturbative series is not the same object as the original integral.

## Optimal truncation

For the example above, the magnitude of the $n$th term is

$$
T_n=n!g^n.
$$

The ratio of successive magnitudes is

$$
\frac{T_{n+1}}{T_n}=(n+1)g.
$$

The terms decrease while $(n+1)g<1$ and increase after $(n+1)g>1$. The least term is near

$$
N_\ast\sim \frac{1}{g}.
$$

Using Stirling's approximation,

$$
N!\sim \sqrt{2\pi N}\left(\frac{N}{e}\right)^N,
$$

we estimate the least term at $N\sim1/g$ as

$$
N!g^N
\sim
\sqrt{\frac{2\pi}{g}}\,e^{-1/g}.
$$

The optimally truncated perturbative error is therefore of order $e^{-1/g}$ up to a power prefactor. This is not an accident. In many problems, the least perturbative term has the same scale as the nearest nonperturbative contribution.

This is one of the main reasons late terms matter. Early terms approximate; late terms diagnose what perturbation theory is missing.

:::caution[Do not blindly add more terms]
For a divergent asymptotic series, the approximation usually improves only up to a finite order depending on $g$. After that, adding terms can make the result worse. “Higher loop” is not automatically “more accurate” unless the expansion parameter and the truncation regime justify it.
:::

## Remainders and what they mean

Given an asymptotic expansion

$$
F(g)\sim\sum_{n=0}^{\infty}a_n g^n,
$$

define the $N$th remainder by

$$
R_N(g)=F(g)-\sum_{n=0}^{N-1}a_n g^n.
$$

The statement $R_N(g)=O(g^N)$ means that for small enough $g$,

$$
|R_N(g)|\le C_N g^N
$$

for some constant $C_N$ that may depend on $N$. The dependence on $N$ matters. In factorially divergent expansions, $C_N$ often grows like $N!$ or faster.

There are three increasingly strong kinds of information:

| Information | Meaning | Typical use |
|---|---|---|
| Formal expansion | Algebraic coefficients $a_n$ are computed by a rule | Feynman diagrams, saddle expansion |
| Asymptotic expansion | For each fixed $N$, $R_N=O(g^N)$ or better | Controlled small-coupling approximation |
| Uniform remainder bound | Bound holds over a whole range of variables or parameters | Boundary layers, large masses, thermal limits, spectral sums |

QFT calculations often begin formally. Making them predictive requires knowing the regime in which the formal expansion is asymptotic and how the remainder behaves after truncation.

## Flat functions and invisible sectors

A function $h(g)$ is called **flat** relative to the power scale at $g=0^+$ if

$$
h(g)=o(g^N)
$$

for every $N$. The basic example is

$$
h(g)=e^{-A/g},
\qquad A>0.
$$

To see this, set $u=A/g$. Then $g^N e^{A/g}=A^N u^{-N}e^u$, and $e^u$ beats every power of $u$. Thus

$$
\frac{e^{-A/g}}{g^N}=A^{-N}u^N e^{-u}\to0.
$$

Flat functions explain why perturbation theory is underdetermined. If a calculation only determines the coefficients of powers of $g$, then it cannot distinguish between answers that differ by $e^{-A/g}$.

In semiclassical QFT, the number $A$ is often an action difference between saddles. For example, if one saddle has action $S_0$ and another has action $S_1$, their relative contribution can scale like

$$
\exp\left[-\frac{S_1-S_0}{\hbar}\right].
$$

The expansion around the first saddle is a power series in $\hbar$ multiplying $e^{-S_0/\hbar}$. It cannot, by itself, determine the coefficient of $e^{-S_1/\hbar}$.

## Watson's lemma

A standard source of asymptotic series is the Laplace-type integral

$$
I(g)=\int_0^\infty dt\,e^{-t/g}f(t),
\qquad g\to0^+.
$$

The exponential localizes the integral near $t=0$. If

$$
f(t)\sim \sum_{n=0}^{\infty}c_n t^n
\qquad (t\to0^+),
$$

then formally

$$
I(g)\sim \sum_{n=0}^{\infty}c_n\int_0^\infty dt\,e^{-t/g}t^n.
$$

Using $t=gu$,

$$
\int_0^\infty dt\,e^{-t/g}t^n
=
g^{n+1}\int_0^\infty du\,e^{-u}u^n
=
n!\,g^{n+1}.
$$

Therefore

$$
I(g)\sim \sum_{n=0}^{\infty} c_n n!\,g^{n+1}.
$$

This is Watson's lemma in its most useful physics form. The small-$g$ expansion of the integral is determined by the near-endpoint expansion of $f(t)$. Local data near the dominant region generate the asymptotic series.

The same logic appears in Schwinger proper-time expansions, heat kernels, threshold expansions, nonrelativistic limits, effective field theory, and short-distance operator product expansions. You identify the dominant region, expand locally, integrate term by term, and then remember that the resulting series may be asymptotic rather than convergent.

## Saddle-point expansions

The saddle-point version is just as important. Consider a one-dimensional integral

$$
Z(\hbar)=\int_C dx\,A(x)e^{-S(x)/\hbar},
\qquad \hbar\to0^+,
$$

where $C$ is a contour and $x_0$ is a nondegenerate saddle:

$$
S'(x_0)=0,
\qquad S''(x_0)\neq0.
$$

Expanding near $x_0$ gives

$$
S(x)=S(x_0)+\frac12 S''(x_0)(x-x_0)^2+\cdots.
$$

After rescaling $x-x_0=\sqrt{\hbar}\,y$, the integral takes the form

$$
Z(\hbar)
\sim
\exp\left[-\frac{S(x_0)}{\hbar}\right]
\sqrt{\frac{2\pi\hbar}{S''(x_0)}}
\sum_{n=0}^{\infty} c_n\hbar^n,
$$

up to phase and contour conventions.

This is the finite-dimensional ancestor of the loop expansion in QFT. The classical solution is the saddle. The Gaussian determinant gives the one-loop prefactor. Higher powers of $\hbar$ come from higher interaction vertices around the saddle. Other saddles produce other exponential sectors, such as

$$
\exp\left[-\frac{S_1}{\hbar}\right]
\sum_{n=0}^{\infty} c_{1,n}\hbar^n.
$$

A single saddle expansion is therefore not the whole answer unless the contour and problem select only that saddle.

## Operations with asymptotic series

Asymptotic expansions can be manipulated, but with more care than convergent power series.

If

$$
F(g)\sim\sum_{n=0}^{\infty}a_n g^n,
\qquad
G(g)\sim\sum_{n=0}^{\infty}b_n g^n,
$$

then, under ordinary local boundedness assumptions,

$$
F(g)+G(g)
\sim
\sum_{n=0}^{\infty}(a_n+b_n)g^n.
$$

Products also work formally:

$$
F(g)G(g)
\sim
\sum_{n=0}^{\infty}\left(\sum_{k=0}^n a_k b_{n-k}\right)g^n.
$$

If $a_0\neq0$, reciprocals can be expanded recursively:

$$
\frac{1}{F(g)}\sim\sum_{n=0}^{\infty}c_n g^n,
$$

where

$$
a_0 c_0=1,
\qquad
\sum_{k=0}^n a_k c_{n-k}=0\quad(n\ge1).
$$

Differentiation is subtler. A differentiable function can have an asymptotic expansion whose derivative is not obtained by termwise differentiation unless additional uniformity or smoothness assumptions hold. In QFT, this matters when differentiating with respect to masses, couplings, sources, moduli, and background fields. Differentiation can amplify remainders or change which regions dominate.

Integration is usually safer if the integration range is controlled. But if an integral extends to infinity, termwise integration can fail because a local expansion is being used outside its domain. This is the seed of many ultraviolet and infrared mistakes.

## Asymptotic equality is directional

Asymptotic statements require a direction or domain. The expansion

$$
e^{-1/g}=o(g^N)
$$

is true as $g\to0^+$ along the positive real axis. It is false in directions where $\operatorname{Re}(1/g)<0$, because then the exponential grows.

For complex $g$, asymptotic expansions are usually valid in sectors:

$$
|\arg g-\theta_0|<\alpha.
$$

When crossing special rays, exponentially small terms can switch on or off. This is the Stokes phenomenon. It is invisible if one only thinks about real Taylor series, but it is central in steepest descent, WKB, Borel summation, and resurgence.

The moral for QFT is simple: an expansion in $g$, $\hbar$, $1/N$, $1/m$, or proper time $s$ is not complete until the domain of validity is stated. A Euclidean expansion, Lorentzian boundary value, retarded prescription, or Feynman prescription may select different analytic continuations.

## Comparison with Taylor series

A Taylor series is built from derivatives at a point:

$$
F(g)=\sum_{n=0}^{\infty}\frac{F^{(n)}(0)}{n!}g^n
$$

inside its radius of convergence, if the function is analytic there. An asymptotic power series may exist even when $F$ is not analytic at the expansion point.

For example,

$$
F(g)=e^{-1/g}
$$

for $g>0$, extended by $F(0)=0$, is smooth at $g=0$ and all derivatives at $0$ vanish. Its Taylor series is zero. But the function is not zero. Smooth does not imply analytic.

This is why nonperturbative physics can be invisible to perturbative Taylor coefficients. A function can be perfectly smooth and still not be determined by its Taylor series.

## QFT dictionary

| Mathematical phrase | QFT translation |
|---|---|
| Small parameter $g$ | Coupling, loop-counting parameter, $\hbar$, $1/N$, $E/M$, lattice spacing, proper time |
| Asymptotic scale | Powers, powers times logs, exponentials, fractional powers, operator dimensions |
| Coefficients $a_n$ | Loop coefficients, heat-kernel coefficients, Wilson coefficients, saddle expansion coefficients |
| Remainder $R_N$ | Truncation error, neglected higher-dimension operators, omitted loops, omitted saddles |
| Optimal truncation | Best perturbative approximation before factorial growth dominates |
| Flat term $e^{-A/g}$ | Instanton, tunneling, complex saddle, mass gap, renormalon-type scale, nonperturbative ambiguity |
| Sector of validity | Euclidean region, Lorentzian boundary value, Borel summation direction, RG regime |
| Stokes phenomenon | Change of saddle decomposition under analytic continuation |

This dictionary is intentionally approximate. In an actual QFT calculation, the expansion parameter may be a matrix of couplings, logarithms may mix with powers, and the relevant nonperturbative terms may involve $e^{-A/g^2}$, $e^{-A/g}$, $e^{-A N}$, $e^{-A mL}$, $e^{-A/a}$, or powers generated by anomalous dimensions.

## Example: loop expansion as an asymptotic series

A formal path integral has the schematic form

$$
Z[J]=\int \mathcal D\phi\,\exp\left\{\frac{i}{\hbar}\left(S[\phi]+\int d^dx\,J\phi\right)\right\}.
$$

Expanding around a classical solution $\phi_{\mathrm{cl}}$ gives

$$
\phi=\phi_{\mathrm{cl}}+\sqrt{\hbar}\,\eta.
$$

The action becomes

$$
S[\phi]
=
S[\phi_{\mathrm{cl}}]
+
\frac{\hbar}{2}\int \eta K\eta
+
\hbar^{3/2}V_3[\eta]
+
\hbar^2 V_4[\eta]
+
\cdots.
$$

The Gaussian integral over $\eta$ gives the one-loop determinant. Expanding the interaction terms and evaluating Gaussian expectations gives Feynman diagrams. The resulting expression has the form

$$
Z[J]
\sim
\exp\left(\frac{i}{\hbar}S[\phi_{\mathrm{cl}}]
\right)
(\det K)^{-1/2}
\sum_{L=0}^{\infty} c_L[J]\hbar^L.
$$

The loop number $L$ is the asymptotic order in $\hbar$. The expansion is local around one saddle and one choice of contour. Other saddles, zero modes, gauge redundancies, determinant phases, and nonperturbative sectors require extra treatment.

This is why the words “perturbative QFT” and “formal power series” appear together so often. The formal series is not a failure. It is the correct local language around a saddle.

## Logs and generalized asymptotic expansions

QFT expansions often involve logarithms. For example, a dimensionless observable at momentum scale $Q$ may contain

$$
F(g,Q/\mu)
\sim
\sum_{n=0}^{\infty}\sum_{k=0}^{n}a_{n,k}g^n\log^k\frac{Q}{\mu}.
$$

The logarithms are not a contradiction of asymptotic analysis. They simply mean the asymptotic scale is larger than pure powers. A typical ordered scale near $g=0^+$ might include

$$
g^n\log^k g,
$$

arranged so that each successive term is smaller in the specified limit.

In renormalization problems, large logarithms can ruin a naive fixed-order expansion even when $g$ is small. The renormalization group reorganizes the expansion by summing classes of logarithms. This is not separate from asymptotics; it is asymptotics with scale dependence handled intelligently.

## Common pitfalls

**Treating $\sim$ as equality.** The symbol $\sim$ records an asymptotic relation, not an exact identity. It does not license arbitrary rearrangement, infinite summation, or evaluation at moderate coupling.

**Forgetting the limit.** Every asymptotic expansion needs a limit: $g\to0$, $x\to\infty$, $s\to0^+$, $m\to\infty$, $N\to\infty$, or something similar. Without the limit, the expansion is not a mathematical statement.

**Ignoring the domain.** A complex asymptotic expansion may be valid only in a sector. Crossing a Stokes ray can change which exponentially small terms are present.

**Confusing divergent with meaningless.** Divergence of the infinite series says nothing by itself about the usefulness of finite truncations.

**Assuming all small effects are perturbative.** Terms like $e^{-A/g}$ are smaller than every power of $g$ but can dominate physical phenomena such as tunneling, splitting, false-vacuum decay, or mass-gap generation.

**Integrating an expansion outside its region.** Expanding an integrand locally and integrating over an infinite domain can produce wrong answers unless the remainder is controlled. This is the sneaky little goblin behind many naive loop-integral manipulations.

**Expecting coefficients to determine the full function.** They may determine a formal sector. They do not, by themselves, determine the nonperturbative completion.

## Exercises

### Exercise 1: A factorially divergent asymptotic series

For

$$
I(g)=\int_0^\infty dt\,\frac{e^{-t}}{1+gt},
\qquad g>0,
$$

show that

$$
I(g)\sim \sum_{n=0}^{\infty}(-1)^n n!g^n
\qquad(g\to0^+).
$$

<details><summary><strong>Solution</strong></summary>

Use the finite identity

$$
\frac{1}{1+gt}
=
\sum_{n=0}^{N-1}(-gt)^n+\frac{(-gt)^N}{1+gt}.
$$

After multiplying by $e^{-t}$ and integrating,

$$
I(g)=\sum_{n=0}^{N-1}(-g)^n\int_0^\infty dt\,e^{-t}t^n
+(-g)^N\int_0^\infty dt\,\frac{e^{-t}t^N}{1+gt}.
$$

Since

$$
\int_0^\infty dt\,e^{-t}t^n=n!,
$$

we get

$$
I(g)-\sum_{n=0}^{N-1}(-1)^n n!g^n
=
(-g)^N\int_0^\infty dt\,\frac{e^{-t}t^N}{1+gt}.
$$

For $g,t>0$, $1/(1+gt)\le1$, so

$$
\left|I(g)-\sum_{n=0}^{N-1}(-1)^n n!g^n\right|
\le
 g^N N!.
$$

For each fixed $N$, this is $O(g^N)$ as $g\to0^+$. Therefore the series is asymptotic, even though it diverges for every $g\neq0$.

</details>

### Exercise 2: Exponentials are invisible to power asymptotics

Show that for any $A>0$ and any integer $N\ge0$,

$$
e^{-A/g}=o(g^N)
\qquad(g\to0^+).
$$

<details><summary><strong>Solution</strong></summary>

Set $u=A/g$. Then $g=A/u$, and $g\to0^+$ means $u\to\infty$. We have

$$
\frac{e^{-A/g}}{g^N}
=
\frac{e^{-u}}{(A/u)^N}
=
A^{-N}u^N e^{-u}.
$$

Since $u^N e^{-u}\to0$ as $u\to\infty$, it follows that

$$
\frac{e^{-A/g}}{g^N}\to0.
$$

Thus $e^{-A/g}=o(g^N)$ for every $N$. Adding $C e^{-A/g}$ to a function does not change its ordinary power asymptotic expansion at $g=0^+$.

</details>

### Exercise 3: Least term estimate

For the formal terms

$$
T_n=n!g^n,
\qquad g>0,
$$

estimate the location and size of the least term for small $g$.

<details><summary><strong>Solution</strong></summary>

The ratio is

$$
\frac{T_{n+1}}{T_n}=(n+1)g.
$$

The terms decrease when $(n+1)g<1$ and increase when $(n+1)g>1$. Therefore the least term occurs near

$$
N_\ast\sim\frac{1}{g}.
$$

Using Stirling's approximation at $N=1/g$,

$$
N!g^N
\sim
\sqrt{2\pi N}\left(\frac{N}{e}\right)^N g^N.
$$

Since $Ng\sim1$,

$$
N!g^N
\sim
\sqrt{\frac{2\pi}{g}}\,e^{-1/g}.
$$

Thus the optimally truncated error is exponentially small in $1/g$, up to a power prefactor.

</details>

### Exercise 4: Watson's lemma for a simple polynomial germ

Let

$$
I(g)=\int_0^\infty dt\,e^{-t/g}\left(1+a t+b t^2+O(t^3)\right),
\qquad g\to0^+.
$$

Assuming the large-$t$ behavior is harmless enough to justify the local expansion, find the first three terms.

<details><summary><strong>Solution</strong></summary>

Use

$$
\int_0^\infty dt\,e^{-t/g}t^n=n!g^{n+1}.
$$

The first three contributions are

$$
\int_0^\infty dt\,e^{-t/g}=g,
$$

$$
a\int_0^\infty dt\,e^{-t/g}t=a g^2,
$$

and

$$
b\int_0^\infty dt\,e^{-t/g}t^2=2b g^3.
$$

Therefore

$$
I(g)=g+a g^2+2b g^3+O(g^4),
$$

under the stated assumptions.

</details>

### Exercise 5: Termwise inversion

Suppose

$$
F(g)\sim a_0+a_1g+a_2g^2+\cdots,
\qquad a_0\neq0.
$$

Find the first three coefficients in

$$
\frac{1}{F(g)}\sim c_0+c_1g+c_2g^2+\cdots.
$$

<details><summary><strong>Solution</strong></summary>

Impose

$$
(a_0+a_1g+a_2g^2+\cdots)(c_0+c_1g+c_2g^2+\cdots)
\sim1.
$$

Matching powers gives

$$
a_0c_0=1,
$$

so

$$
c_0=\frac{1}{a_0}.
$$

At order $g$,

$$
a_0c_1+a_1c_0=0,
$$

hence

$$
c_1=-\frac{a_1}{a_0^2}.
$$

At order $g^2$,

$$
a_0c_2+a_1c_1+a_2c_0=0,
$$

so

$$
c_2=\frac{a_1^2}{a_0^3}-\frac{a_2}{a_0^2}.
$$

Therefore

$$
\frac{1}{F(g)}
\sim
\frac{1}{a_0}
-
\frac{a_1}{a_0^2}g
+
\left(\frac{a_1^2}{a_0^3}-\frac{a_2}{a_0^2}\right)g^2
+\cdots.
$$

</details>

## References and further reading

For general asymptotic series, divergent series, Watson's lemma, saddle-point methods, and error estimates, see G. H. Hardy, *Divergent Series*; E. T. Whittaker and G. N. Watson, *A Course of Modern Analysis*; F. W. J. Olver, *Asymptotics and Special Functions*; R. B. Dingle, *Asymptotic Expansions*; and C. M. Bender and S. A. Orszag, *Advanced Mathematical Methods for Scientists and Engineers*.

For QFT applications, large-order behavior, instantons, saddle expansions, functional determinants, and perturbation theory, see Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*; Steven Weinberg, *The Quantum Theory of Fields*; Mark Srednicki, *Quantum Field Theory*; Matthew Schwartz, *Quantum Field Theory and the Standard Model*; A. Zee, *Quantum Field Theory in a Nutshell*; Marcos Mariño, *Instantons and Large N*; and Mikhail Shifman, *Advanced Topics in Quantum Field Theory*.

For the next layer — Borel summation, Stokes phenomena, transseries, and resurgence — see J. Écalle, *Les fonctions résurgentes*; O. Costin, *Asymptotics and Borel Summability*; and the modern physics literature on resurgence, exact WKB, instantons, and renormalons.

## Version history

- 2026-06-26: First polished draft. Added definitions, asymptotic scales, uniqueness of coefficients, flat functions, divergent integral example, optimal truncation, Watson's lemma, saddle expansions, operations, domain dependence, QFT dictionary, common pitfalls, exercises with solutions, and remainder-flow figure.
