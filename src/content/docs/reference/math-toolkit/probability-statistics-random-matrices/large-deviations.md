---
title: "Large Deviations"
description: "A QFT-oriented guide to large-deviation principles, rate functions, Legendre transforms, saddle points, thermodynamic limits, and effective actions."
sidebar:
  label: "Large Deviations"
  order: 4
level: Graduate
status: "Polished draft"
source: "Large-deviation theory, statistical mechanics, saddle-point asymptotics, thermodynamic limits, effective potentials, and Euclidean QFT generating functionals."
topics:
  - large deviations
  - rate functions
  - Laplace principle
  - saddle points
  - thermodynamic limit
  - effective action
  - Legendre transform
canonicalTopics:
  - large-deviation-principle
  - rate-function
  - laplace-principle
  - gartner-ellis-theorem
  - thermodynamic-effective-action
researchStatus:
  established:
    - "Large-deviation principles, rate functions, the Laplace principle, and Legendre-Fenchel duality are standard tools in probability theory and statistical mechanics."
    - "In QFT and statistical field theory, saddle points, thermodynamic limits, effective actions, and instanton estimates are large-deviation ideas in physics clothing."
  active:
    - "Large deviations for interacting continuum fields, stochastic PDEs, nonequilibrium field theories, rare-event algorithms, and dynamical phase transitions remain active research areas."
---

## Summary

Large-deviation theory explains the exponential smallness of rare events. A typical central-limit estimate says that fluctuations of an average are of size $N^{-1/2}$. A large-deviation estimate asks a sharper question: how unlikely is an $O(1)$ fluctuation when $N$ is large?

The canonical form is

$$
\mathbb P(X_N\approx x)\asymp e^{-N I(x)},
$$

where $I(x)$ is the **rate function**. The notation $\asymp$ means equality at the level of exponential rate, not equality of prefactors. A more precise local slogan is

$$
-\frac1N\log \mathbb P(X_N\in A)\longrightarrow \inf_{x\in A} I(x)
$$

under suitable hypotheses.

In QFT and statistical mechanics, the same idea appears under many names:

| Large-deviation language | QFT and statistical-mechanics language |
|---|---|
| large parameter $N$ | volume, inverse temperature, number of degrees of freedom, $1/\hbar$, large-$N$ rank |
| random variable $X_N$ | collective field, order parameter, empirical density, topological density |
| rate function $I$ | free-energy cost, Euclidean action, effective potential, instanton action |
| minimizer of $I$ | thermodynamic phase, classical saddle, mean field |
| Legendre transform | source-to-order-parameter transform, effective action construction |
| rare event | tunneling event, false-vacuum decay, large fluctuation, atypical phase |

The point is not that every path integral is literally a probability problem. The point is that the mathematics of exponential concentration is the same mathematics behind saddle points, free energies, effective actions, and nonperturbative exponential factors.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A flowchart linking distributions of collective variables, scaled cumulant generating functions, Legendre transforms, rate functions, and saddle-point dominance.](/figures/math-toolkit/large-deviation-rate-function-flow.svg)

<figcaption>

Large deviations connect probability tails to saddle-point physics. A scaled generating function $\Lambda(t)$ is dual to a rate function $I(x)$; the minimizers of $I(x)-f(x)$ control exponentially large integrals and thermodynamic limits.

</figcaption>
</figure>

## Prerequisites

You should know the language of [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/) and [Cumulants and Connected Correlators](/math-toolkit/probability-statistics-random-matrices/cumulants-and-connected-correlators/). The page also uses saddle-point intuition from [Steepest Descent](/math-toolkit/asymptotics-regularization-resurgence/steepest-descent/) and the Legendre-transform logic of effective actions.

We use probability notation when the measure is positive and normalized. For Euclidean field theory, this is often a good regularized model. For Lorentzian path integrals, the analogous statements become oscillatory saddle-point statements rather than probability statements.

## Exponential scale

Large deviations care about logarithms divided by a large parameter. If $P_N$ is a probability that decays like

$$
P_N\sim A_N e^{-N I},
$$

where $A_N$ grows subexponentially, then

$$
-\lim_{N\to\infty}\frac1N\log P_N=I.
$$

The prefactor $A_N$ is invisible at this scale. This is exactly the same loss of information as in a leading saddle-point approximation:

$$
\int dx\,e^{-N S(x)}
\sim e^{-N S(x_*)}\times \text{fluctuation determinant}.
$$

Large-deviation theory focuses first on the exponent $S(x_*)$. Gaussian fluctuations and determinants come later.

The large parameter $N$ need not literally be a particle number. In physics it may be:

$$
N=V,
\qquad
N=\beta V,
\qquad
N=\frac1\hbar,
\qquad
N=N_c^2,
\qquad
N=\text{number of lattice sites}.
$$

The common structure is exponential concentration:

$$
\text{weight}\sim e^{-N\times \text{cost}}.
$$

## The rate function

A rate function $I:E\to[0,\infty]$ assigns a cost to each possible macroscopic value. Its minimizers are typical values. Usually one normalizes so that

$$
\inf_x I(x)=0.
$$

If $x_*$ is the unique minimizer, then $X_N$ concentrates near $x_*$:

$$
X_N\to x_*
$$

in probability. Values with $I(x)>0$ are exponentially suppressed.

A good rate function has compact level sets

$$
\{x:I(x)\le c\}
$$

for all finite $c$. This technical condition is useful because it prevents probability from leaking to infinity at the exponential scale.

In thermodynamics, the rate function is often a constrained free energy. For an order parameter $m$, one may define

$$
\mathbb P_N(m\approx m_0)\asymp e^{-N I(m_0)}.
$$

Then phases are minima of $I(m)$. Phase coexistence means multiple competing minima.

## Large-deviation principle

A sequence of probability measures $\mu_N$ on a space $E$ satisfies a large-deviation principle with speed $N$ and rate function $I$ if, for suitable sets $A$,

$$
\mu_N(A)\asymp e^{-N\inf_{x\in A}I(x)}.
$$

More precisely, for closed sets $F$,

$$
\limsup_{N\to\infty}\frac1N\log\mu_N(F)
\le -\inf_{x\in F}I(x),
$$

and for open sets $G$,

$$
\liminf_{N\to\infty}\frac1N\log\mu_N(G)
\ge -\inf_{x\in G}I(x).
$$

The closed-set upper bound prevents too much probability from sitting in rare closed regions. The open-set lower bound says that neighborhoods of a point $x$ have at least the expected exponential weight.

Most physics use does not require quoting this formal definition every time. But it is valuable because it clarifies what $\mathbb P(X_N\approx x)\asymp e^{-NI(x)}$ really means.

## Sample mean: the basic example

Let $X_1,X_2,\ldots$ be independent identically distributed real random variables. Define the sample mean

$$
\overline X_N=\frac1N\sum_{i=1}^N X_i.
$$

The law of large numbers says

$$
\overline X_N\to \mathbb E[X_1]
$$

under standard hypotheses. The central limit theorem says fluctuations of order $N^{-1/2}$ are approximately Gaussian. Large deviations ask for the probability of

$$
\overline X_N\approx x
$$

when $x$ is not close to $\mathbb E[X_1]$.

If the moment-generating function exists near the origin, define

$$
\lambda(t)=\log \mathbb E[e^{tX_1}].
$$

Then Cramér’s theorem says that $\overline X_N$ satisfies a large-deviation principle with rate function

$$
I(x)=\sup_{t\in\mathbb R}\{tx-\lambda(t)\}.
$$

This is the Legendre-Fenchel transform of $\lambda(t)$.

The derivation already contains the physics. For any $t$,

$$
\mathbb P(\overline X_N\ge x)
=\mathbb P(e^{tN\overline X_N}\ge e^{tNx})
\le e^{-tNx}\mathbb E[e^{t\sum_iX_i}].
$$

Independence gives

$$
\mathbb E[e^{t\sum_iX_i}]=e^{N\lambda(t)}.
$$

Thus

$$
\mathbb P(\overline X_N\ge x)\lesssim e^{-N(tx-\lambda(t))}.
$$

Optimizing over $t$ gives the exponent. The lower bound is subtler, but the exponent is already visible.

## Gaussian example

Let $X_i$ be Gaussian with mean $\mu$ and variance $\sigma^2$. Then

$$
\lambda(t)=\mu t+\frac12\sigma^2t^2.
$$

The rate function is

$$
I(x)=\sup_t\left\{tx-\mu t-\frac12\sigma^2t^2\right\}.
$$

The maximizing $t$ is

$$
t_* = \frac{x-\mu}{\sigma^2},
$$

so

$$
I(x)=\frac{(x-\mu)^2}{2\sigma^2}.
$$

For the sample mean,

$$
\overline X_N\sim \mathcal N\!\left(\mu,\frac{\sigma^2}{N}\right),
$$

and therefore

$$
\mathbb P(\overline X_N\approx x)
\sim \exp\!\left[-N\frac{(x-\mu)^2}{2\sigma^2}\right]
$$

up to prefactors and interval-size effects. Here the large-deviation result is exactly the large-tail form of a Gaussian.

## Bernoulli example and entropy

Let $X_i\in\{0,1\}$ with

$$
\mathbb P(X_i=1)=p,
\qquad
\mathbb P(X_i=0)=1-p.
$$

The sample mean $\overline X_N=k/N$ is the fraction of successes. The exact probability is binomial:

$$
\mathbb P(\overline X_N=k/N)
=\binom Nk p^k(1-p)^{N-k}.
$$

Using Stirling’s formula with $x=k/N$ gives

$$
\mathbb P(\overline X_N\approx x)
\asymp e^{-N I(x)},
$$

where

$$
I(x)=x\log\frac{x}{p}+(1-x)\log\frac{1-x}{1-p}.
$$

This is the relative entropy between Bernoulli distributions with parameters $x$ and $p$.

This example is the miniature version of statistical mechanics. The binomial coefficient is entropy; the probabilities $p^k(1-p)^{N-k}$ are energetic weights. The rate function is the competition between entropy and energy.

## Scaled cumulant-generating functions

For a sequence of random variables $X_N$, define the scaled cumulant-generating function

$$
\Lambda(t)=\lim_{N\to\infty}\frac1N\log\mathbb E[e^{NtX_N}],
$$

when the limit exists. In many good cases, the rate function is the Legendre-Fenchel transform

$$
I(x)=\sup_t\{tx-\Lambda(t)\}.
$$

This is the content of the Gärtner–Ellis theorem under differentiability and regularity assumptions.

The QFT analogy is immediate. A source $J$ coupled to an intensive observable $\mathcal O$ produces a generating functional

$$
Z_N[J]=\left\langle e^{N J\mathcal O}\right\rangle,
$$

and a scaled free energy

$$
W[J]=\lim_{N\to\infty}\frac1N\log Z_N[J].
$$

The rate function for $\mathcal O$ is the Legendre-Fenchel dual

$$
I(o)=\sup_J\{Jo-W[J]\}.
$$

This is the probabilistic ancestor of the effective potential.

## The Laplace principle

The Laplace principle says that if $X_N$ satisfies a large-deviation principle with rate function $I$, then for suitable functions $f$,

$$
\lim_{N\to\infty}\frac1N\log\mathbb E[e^{Nf(X_N)}]
=\sup_x\{f(x)-I(x)\}.
$$

Equivalently,

$$
\mathbb E[e^{Nf(X_N)}]
\asymp \exp\!\left[N\sup_x(f(x)-I(x))\right].
$$

This is just saddle-point approximation in probability language. If

$$
d\mu_N(x)\asymp e^{-NI(x)}dx,
$$

then

$$
\int dx\,e^{Nf(x)}d\mu_N(x)
\asymp
\int dx\,e^{-N[I(x)-f(x)]}
\asymp
\exp\!\left[-N\inf_x(I(x)-f(x))\right].
$$

In statistical mechanics, this is the bridge between microcanonical and canonical ensembles. In field theory, it is the bridge between constrained path integrals and source-deformed generating functionals.

## Thermodynamics

Let $E_N$ be an energy-like random variable, and let $e=E_N/N$ be the energy density. Suppose the density of states has the asymptotic form

$$
\Omega_N(e)\asymp e^{Ns(e)},
$$

where $s(e)$ is the entropy density. The canonical partition function is

$$
Z_N(\beta)=\int de\,\Omega_N(e)e^{-N\beta e}.
$$

At large $N$,

$$
Z_N(\beta)
\asymp
\exp\!\left[N\sup_e(s(e)-\beta e)\right].
$$

The free-energy density is

$$
f(\beta)=-\frac1\beta\lim_{N\to\infty}\frac1N\log Z_N(\beta),
$$

so

$$
-\beta f(\beta)=\sup_e(s(e)-\beta e).
$$

This is a Legendre transform. Phase transitions occur when the maximizing saddle changes non-analytically or when the thermodynamic function fails to be strictly convex or smooth.

## Effective actions as rate functions

Let $\phi$ be a microscopic field and let $M[\phi]$ be a collective observable, for example an average magnetization,

$$
M[\phi]=\frac1V\int_V d^dx\,\phi(x).
$$

The probability density for $M=m$ can be written formally as a constrained path integral:

$$
P_V(m)=\frac1Z\int \mathcal D\phi\,
\delta(M[\phi]-m)e^{-S_E[\phi]}.
$$

A large-deviation form is

$$
P_V(m)\asymp e^{-V I(m)}.
$$

The function $I(m)$ is a constrained free-energy cost. In a homogeneous system it is closely related to the effective potential. With a source $J$,

$$
Z_V[J]=\int \mathcal D\phi\,
\exp\!\left[-S_E[\phi]+VJM[\phi]\right],
$$

and

$$
W(J)=\lim_{V\to\infty}\frac1V\log Z_V[J].
$$

Then the convex rate function is

$$
I(m)=\sup_J\{Jm-W(J)+W(0)\}.
$$

The subtraction by $W(0)$ enforces $\inf I=0$.

This formula explains why the exact effective potential is convex. It is a Legendre-Fenchel transform. Nonconvex mean-field potentials are usually saddle approximations before the thermodynamic and source Legendre transform are fully completed.

## Instantons and rare events

A rare event in a field theory often has weight

$$
\exp\!\left(-\frac{S_{\mathrm{inst}}}{\hbar}\right)
$$

or, in Euclidean statistical language,

$$
\exp(-S_{\mathrm{inst}}).
$$

This is a large-deviation statement with speed $1/\hbar$ or with a large action scale. The instanton is the saddle that minimizes the action subject to boundary conditions defining the rare event.

For false-vacuum decay, the rate per unit volume has the schematic form

$$
\Gamma/V\sim A e^{-B/\hbar},
$$

where $B$ is the Euclidean bounce action. The prefactor $A$ comes from fluctuations and zero modes. Large-deviation language identifies $B$ as the exponential cost.

The same pattern appears in domain-wall nucleation, phase slips, tunneling between vacua, and rare topological sectors.

## Large N and concentration

In vector and matrix models, the large parameter may be the number of components or the matrix size. A collective observable such as an eigenvalue density $\rho(\lambda)$ may satisfy

$$
\mathbb P(\rho\approx \rho_*)\asymp e^{-N^2 I[\rho_*]}.
$$

The power $N^2$ reflects the number of matrix degrees of freedom. The equilibrium density minimizes $I[\rho]$. The saddle-point equation for $I$ is then the large-$N$ master equation for the eigenvalue distribution.

In large-$N$ QFT, factorization is another concentration phenomenon:

$$
\langle \mathcal O_1\mathcal O_2\rangle
-
\langle \mathcal O_1\rangle\langle \mathcal O_2\rangle
=O(N^{-p})
$$

for some positive power $p$ depending on normalization. The leading saddle behaves classically because fluctuations of suitable observables are suppressed.

## Convexity and phase coexistence

Legendre-Fenchel transforms produce convex functions. Therefore the rate function obtained from the source generating functional is convex. But many mean-field calculations produce nonconvex potentials. Is that a contradiction? No. It means one is comparing different objects.

A constrained finite-volume free energy may have nonconvex-looking saddle branches. In the infinite-volume limit, phase coexistence fills in the convex envelope. This is the Maxwell construction in thermodynamic language.

For an order parameter $m$, a double-well mean-field potential suggests two phases. The exact convex effective potential is flat between coexistence values in the infinite-volume limit. The flat region means mixed states or phase separation, not that the system has lost all restoring force microscopically.

## Dynamical large deviations

Large deviations also apply to histories. Let $X_t$ be a stochastic process and let $A_T$ be a time-averaged observable,

$$
A_T=\frac1T\int_0^T dt\,a(X_t).
$$

A dynamical large-deviation principle has the form

$$
\mathbb P(A_T\approx a)\asymp e^{-T I(a)}.
$$

The scaled cumulant-generating function is

$$
\Lambda(k)=\lim_{T\to\infty}\frac1T\log\mathbb E[e^{kT A_T}].
$$

In Markov systems, $\Lambda(k)$ is often the largest eigenvalue of a tilted generator. This is the nonequilibrium cousin of transfer-matrix dominance by the largest eigenvalue.

In QFT language, dynamical large deviations are useful for stochastic quantization, nonequilibrium statistical mechanics, quantum trajectories, and rare-event ensembles.

## Common pitfalls

### Treating $\asymp$ as equality

The statement

$$
P_N\asymp e^{-NI}
$$

does not determine prefactors, powers of $N$, determinants, or zero-mode volumes. Those are subleading at the large-deviation scale but often physically important.

### Forgetting the speed

The exponent may scale like $N$, $V$, $\beta V$, $N^2$, or $1/\hbar$. The rate function is defined only after choosing the speed.

### Assuming the rate function is the bare action

The rate function is usually an effective constrained free energy. Entropy and fluctuations contribute. A bare classical action becomes a rate function only in special limits.

### Missing convexification

The Legendre-Fenchel transform gives a convex object. Nonconvex saddle potentials and exact thermodynamic rate functions are related but not identical.

### Applying probability results to oscillatory integrals without translation

Lorentzian path integrals involve phases, not positive probabilities. Large-deviation intuition may survive as stationary-phase or steepest-descent intuition, but positivity-based theorems do not apply directly.

### Ignoring boundary and ensemble dependence

Rate functions depend on what is held fixed: energy, source, charge, order parameter, volume, boundary condition, topological sector. Switching ensembles can change which rate function is natural.

## Exercises

### Exercise 1: Gaussian sample mean

Let $X_i$ be independent Gaussian variables with mean $0$ and variance $\sigma^2$. Compute the large-deviation rate function for

$$
\overline X_N=\frac1N\sum_{i=1}^NX_i.
$$

<details><summary><strong>Solution</strong></summary>

The cumulant-generating function of one variable is

$$
\lambda(t)=\log\mathbb E[e^{tX_i}]=\frac12\sigma^2t^2.
$$

Cramér’s theorem gives

$$
I(x)=\sup_t\left(tx-\frac12\sigma^2t^2\right).
$$

The maximizing value is

$$
t_* = \frac{x}{\sigma^2}.
$$

Therefore

$$
I(x)=\frac{x^2}{2\sigma^2}.
$$

Thus

$$
\mathbb P(\overline X_N\approx x)\asymp
\exp\!\left(-N\frac{x^2}{2\sigma^2}\right).
$$

</details>

### Exercise 2: Bernoulli rate function

For $X_i\in\{0,1\}$ with $\mathbb P(X_i=1)=p$, derive the rate function for the sample mean by Legendre transform.

<details><summary><strong>Solution</strong></summary>

The moment-generating function is

$$
\mathbb E[e^{tX_i}]=(1-p)+pe^t,
$$

so

$$
\lambda(t)=\log(1-p+pe^t).
$$

The rate function is

$$
I(x)=\sup_t\{tx-\lambda(t)\}.
$$

The saddle equation is

$$
x=\lambda'(t)=\frac{pe^t}{1-p+pe^t}.
$$

Solving gives

$$
e^t=\frac{x(1-p)}{p(1-x)}.
$$

Substituting into $tx-\lambda(t)$ yields

$$
I(x)=x\log\frac{x}{p}+(1-x)\log\frac{1-x}{1-p}.
$$

</details>

### Exercise 3: Laplace principle for a quadratic rate function

Suppose $X_N$ has rate function

$$
I(x)=\frac{x^2}{2\sigma^2}.
$$

Use the Laplace principle to compute

$$
\lim_{N\to\infty}\frac1N\log \mathbb E[e^{Ntx}]
$$

where $x$ denotes the realized value of $X_N$.

<details><summary><strong>Solution</strong></summary>

The Laplace principle gives

$$
\Lambda(t)=\sup_x\left(tx-\frac{x^2}{2\sigma^2}\right).
$$

The maximizing point satisfies

$$
t-\frac{x}{\sigma^2}=0,
\qquad
x_* = \sigma^2 t.
$$

Thus

$$
\Lambda(t)=t(\sigma^2t)-\frac{(\sigma^2t)^2}{2\sigma^2}
=\frac12\sigma^2t^2.
$$

This is the Gaussian scaled cumulant-generating function.

</details>

### Exercise 4: Effective potential as a rate function

Let $M[\phi]$ be a volume-averaged order parameter and suppose

$$
P_V(m)\asymp e^{-V I(m)}.
$$

Show that the source-deformed free energy

$$
W(J)=\lim_{V\to\infty}\frac1V\log\left\langle e^{VJM}\right\rangle
$$

satisfies

$$
W(J)=\sup_m\{Jm-I(m)
\}
$$

up to an additive normalization convention.

<details><summary><strong>Solution</strong></summary>

Write the expectation over $M$ using its probability density:

$$
\left\langle e^{VJM}\right\rangle
=\int dm\,P_V(m)e^{VJm}.
$$

Using the large-deviation form,

$$
P_V(m)\asymp e^{-VI(m)},
$$

we get

$$
\left\langle e^{VJM}\right\rangle
\asymp
\int dm\,e^{V[Jm-I(m)]}.
$$

The leading exponential is determined by the maximum of $Jm-I(m)$, so

$$
W(J)=\sup_m\{Jm-I(m)\}.
$$

If $P_V$ is normalized so that $I$ has minimum zero, then $W(0)=0$. Other conventions shift $I$ or $W$ by constants.

</details>

## References

- Dembo and Zeitouni, *Large Deviations Techniques and Applications*.
- Touchette, “The large deviation approach to statistical mechanics.”
- Ellis, *Entropy, Large Deviations, and Statistical Mechanics*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Wilson and Kogut, “The renormalization group and the $\epsilon$ expansion.”
- Marino, *Instantons and Large N*.
- Coleman, “The fate of the false vacuum.”

## Version history

- **2026-06-27:** First polished draft. Introduces large-deviation principles, rate functions, Cramér and Gärtner–Ellis logic, the Laplace principle, thermodynamic Legendre transforms, effective actions, instanton costs, large-$N$ concentration, and common QFT caveats.
