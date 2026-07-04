---
title: "Random Walks"
description: "A QFT-oriented guide to random walks, diffusion limits, heat kernels, lattice propagators, return probabilities, recurrence, Feynman–Kac formulas, and worldline intuition."
sidebar:
  label: "Random Walks"
  order: 6
level: Graduate
status: "Polished draft"
source: "Probability theory, diffusion processes, heat kernels, lattice statistical mechanics, Euclidean path integrals, and worldline representations in QFT."
topics:
  - random walks
  - Brownian motion
  - diffusion
  - heat kernels
  - central limit theorem
  - lattice propagators
  - Feynman-Kac formula
  - worldline representation
canonicalTopics:
  - random-walk
  - diffusion-limit
  - heat-kernel
  - feynman-kac-formula
  - worldline-representation
researchStatus:
  established:
    - "Random walks, diffusion limits, central-limit scaling, recurrence and transience, heat kernels, and Feynman–Kac formulas are standard tools in probability and statistical mechanics."
    - "In QFT, random-walk language underlies heat-kernel methods, lattice propagators, polymer analogies, worldline representations, and the statistical mechanics of fluctuating paths."
  active:
    - "Modern uses include stochastic quantization, random geometry, disordered systems, loop soups, Schramm–Loewner evolution, worldline numerics, and probabilistic constructions of continuum fields."
---

## Summary

A random walk is the simplest model of a fluctuating path. At each step, a walker moves by a random increment. After many steps, microscopic details are washed out and the large-scale motion becomes diffusion.

For a simple random walk on a lattice,

$$
X_N=\xi_1+\cdots+\xi_N,
$$

where the increments $\xi_i$ are independent and identically distributed with mean zero. If the variance per step is finite, then the central-limit theorem says that the rescaled endpoint

$$
\frac{X_N}{\sqrt N}
$$

approaches a Gaussian random variable. In continuum language, the probability density solves a heat equation,

$$
\partial_t p(t,x)=D\nabla^2p(t,x).
$$

This is why random walks keep sneaking into QFT. The free Euclidean propagator is an inverse differential operator; the heat kernel is its proper-time building block; a lattice propagator can be interpreted as a sum over walks; and the worldline representation rewrites determinants and propagators as sums over fluctuating paths.

The slogan is:

$$
\text{free propagation is diffusion with a mass penalty}.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![A lattice random walk coarse-grains to Brownian motion, whose transition density solves the heat equation and builds QFT propagators.](/figures/math-toolkit/random-walk-diffusion-flow.svg)

<figcaption>

A random walk becomes Brownian motion under diffusive scaling. The transition kernel becomes a heat kernel; adding a mass term weights long paths by $e^{-m^2T}$, producing a Schwinger proper-time representation of propagators.

</figcaption>
</figure>

## Prerequisites

You should be comfortable with [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/), [Gaussian Measures](/math-toolkit/probability-statistics-random-matrices/gaussian-measures/), and [Markov Chains and Transfer Matrices](/math-toolkit/probability-statistics-random-matrices/markov-chains-and-transfer-matrices/). The page also uses heat kernels from [Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/) and Green functions from [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/).

The analysis is Euclidean. Lorentzian propagation is obtained by analytic continuation or by oscillatory path integrals, not by literal probabilities.

## Simple random walk

The one-dimensional simple random walk starts at $X_0=0$ and evolves by

$$
X_{n+1}=X_n+\xi_{n+1},
$$

where

$$
\mathbb P(\xi_i=+a)=\mathbb P(\xi_i=-a)=\frac12.
$$

After $N$ steps,

$$
X_N=a\sum_{i=1}^N \epsilon_i,
\qquad
\epsilon_i=\pm1.
$$

The probability that $X_N=ka$ is

$$
\mathbb P(X_N=ka)
=2^{-N}\binom{N}{(N+k)/2},
$$

when $N+k$ is even, and zero otherwise.

The mean and variance are

$$
\mathbb E[X_N]=0,
\qquad
\mathbb E[X_N^2]=Na^2.
$$

The root-mean-square displacement is therefore

$$
\sqrt{\mathbb E[X_N^2]}=a\sqrt N.
$$

This $\sqrt N$ scaling is the first sign of diffusion. A typical path has length $Na$, but its net displacement is only of order $a\sqrt N$ because signs cancel randomly.

## Diffusive scaling limit

To obtain a continuum limit, let the lattice spacing be $a$ and the time step be $\Delta t$. Write

$$
t=N\Delta t.
$$

Keep

$$
D=\frac{a^2}{2d\,\Delta t}
$$

fixed as $a,\Delta t\to0$. In $d$ dimensions, the endpoint density approaches

$$
p(t,x|0,0)=\frac{1}{(4\pi Dt)^{d/2}}
\exp\!\left(-\frac{|x|^2}{4Dt}\right).
$$

This is the fundamental solution of

$$
\partial_t p=D\nabla^2p,
\qquad
p(0,x)=\delta^{(d)}(x).
$$

The random walk has become Brownian motion. The scaling

$$
|x|^2\sim t
$$

is the probabilistic reason the Laplacian has engineering dimension two. In field theory language, the diffusion time $t$ has dimension of length squared.

## Heat kernels

Let $K(t;x,y)$ be the heat kernel for an operator $L=-\nabla^2+V(x)$, initially with $V=0$. For the free Laplacian on $\mathbb R^d$,

$$
K_0(t;x,y)=\frac{1}{(4\pi t)^{d/2}}
\exp\!\left(-\frac{|x-y|^2}{4t}\right),
$$

where we have set $D=1$ by rescaling $t$.

The kernel satisfies the semigroup law

$$
K(t+s;x,z)=\int d^dy\,K(t;x,y)K(s;y,z).
$$

This is the continuum version of the Markov property. A path from $x$ to $z$ in time $t+s$ can be decomposed by summing over its intermediate point $y$ at time $t$.

The same semigroup property is central in QFT. Proper-time evolution by an elliptic operator is

$$
e^{-tL},
$$

and its kernel is

$$
K(t;x,y)=\langle x|e^{-tL}|y\rangle.
$$

## Massive propagator as a sum over walk lengths

The Euclidean Green function of a massive scalar in flat space satisfies

$$
(-\nabla^2+m^2)G_m(x,y)=\delta^{(d)}(x-y).
$$

Using the identity

$$
\frac{1}{A}=\int_0^\infty dT\,e^{-TA},
$$

for a positive operator $A$, one obtains the Schwinger proper-time representation

$$
G_m(x,y)=\int_0^\infty dT\,e^{-m^2T}K_0(T;x,y).
$$

Thus the massive propagator is an integral over diffusion times. Long paths are suppressed by $e^{-m^2T}$. The mass is a penalty for long wandering.

In momentum space,

$$
G_m(p)=\frac{1}{p^2+m^2}
=\int_0^\infty dT\,e^{-T(p^2+m^2)}.
$$

The heat kernel is the bridge between the local differential operator and the path picture.

## Lattice propagator as a walk sum

On a hypercubic lattice, a nearest-neighbor random walk has a transition matrix $P$. A massive lattice propagator often has the schematic form

$$
G=(1-\kappa P)^{-1}.
$$

Expanding the inverse gives

$$
G=\sum_{n=0}^\infty \kappa^n P^n.
$$

The matrix element $(P^n)_{xy}$ counts or weights walks from $y$ to $x$ in $n$ steps. Therefore

$$
G_{xy}=\sum_{\gamma:y\to x}\kappa^{|\gamma|}\,w(\gamma),
$$

where $|\gamma|$ is the number of steps and $w(\gamma)$ includes local step weights.

This expansion is the simplest version of the worldline idea. Field propagation can be reorganized as a sum over paths. Interactions, gauge fields, and spin decorate the paths with additional weights.

## Return probability and spectral dimension

The return probability is the probability density to return to the starting point after time $T$:

$$
P_{\rm ret}(T)=K(T;x,x).
$$

For free diffusion in $d$ dimensions,

$$
P_{\rm ret}(T)=\frac{1}{(4\pi T)^{d/2}}.
$$

The exponent defines the spectral dimension. If

$$
P_{\rm ret}(T)\sim T^{-d_s/2},
$$

then $d_s$ is the spectral dimension.

On ordinary smooth $d$-dimensional space, $d_s=d$. On fractals, random geometries, and certain quantum-gravity-inspired models, the spectral dimension can differ from the topological dimension. This is one reason random walks are useful probes of geometry.

## Recurrence and transience

A random walk is recurrent if it returns to its starting point with probability one. It is transient if there is a nonzero probability of never returning.

For the simple random walk on $\mathbb Z^d$:

$$
\begin{array}{c|c}
d & \text{behavior} \\
\hline
1,2 & \text{recurrent} \\
3,4,\ldots & \text{transient}
\end{array}
$$

The heat-kernel explanation is simple. The expected total return time is controlled by

$$
\int^{\infty} dT\,K(T;0,0)
\sim
\int^{\infty} dT\,T^{-d/2}.
$$

This diverges for $d\le2$ and converges for $d>2$.

The same integral appears in massless Green functions. The infrared behavior of

$$
\int \frac{d^dp}{(2\pi)^d}\frac{1}{p^2}
$$

is tied to the recurrence of diffusion. This is a miniature version of the deep relation between random walks, infrared divergences, and lower critical dimensions.

## Feynman–Kac formula

For an operator

$$
L=-\frac12\nabla^2+V(x),
$$

the Feynman–Kac formula expresses the heat kernel as an expectation over Brownian paths:

$$
K(T;x,y)
=\mathbb E_{x\to y}\!
\left[
\exp\!\left(-\int_0^T d\tau\,V(X_\tau)\right)
\right]
K_0(T;x,y).
$$

Here $\mathbb E_{x\to y}$ is expectation over Brownian bridges from $x$ to $y$ in time $T$. The potential $V$ weights paths by the exponential of minus the accumulated cost.

This is the rigorous cousin of the Euclidean path integral

$$
K(T;x,y)=\int_{x(0)=y}^{x(T)=x}\mathcal Dx\,
\exp\!\left[-\int_0^T d\tau\,\left(\frac12\dot x^2+V(x)\right)\right].
$$

The formula makes the probabilistic meaning precise when the operator and potential satisfy appropriate hypotheses.

## Worldline representation

The one-loop effective action of a scalar field with operator $L$ can be written formally as

$$
\Gamma^{(1)}=\frac12\operatorname{Tr}\log L.
$$

Using

$$
\log L=-\int_0^\infty \frac{dT}{T}e^{-TL}
$$

up to regularization-dependent constants, one obtains

$$
\Gamma^{(1)}=-\frac12\int_0^\infty\frac{dT}{T}\operatorname{Tr}e^{-TL}.
$$

The trace of the heat kernel is a sum over closed paths:

$$
\operatorname{Tr}e^{-TL}=\int d^dx\,K(T;x,x).
$$

Thus determinants can be represented by ensembles of closed random loops. In gauge backgrounds, the loops acquire Wilson-loop factors. In curved backgrounds, they probe curvature through heat-kernel coefficients. In spinor theories, spin degrees of freedom add Grassmann or matrix factors.

This does not make every QFT calculation easy, but it gives a powerful geometric picture: one-loop physics is a gas of closed worldlines.

## Polymer analogy

A random walk of $N$ steps is also the simplest model of a polymer chain. The endpoint distribution of an ideal chain is Gaussian with size

$$
R\sim aN^{1/2}.
$$

Self-avoiding walks modify this scaling:

$$
R\sim aN^\nu,
$$

where $\nu$ depends on dimension. The field-theory description of self-avoiding walks is related to the $O(n)$ model in the limit $n\to0$.

This is a lovely example of QFT as a unifying language: a model of long molecules becomes a scalar field theory with a strange-looking analytic continuation in the number of components.

## Brownian paths are rough

Brownian paths are continuous but almost surely nowhere differentiable. This matters because the continuum expression

$$
\int_0^T d\tau\,\frac12\dot x^2
$$

is not literally evaluated on ordinary differentiable paths under the Wiener measure. It is a formal action whose discretized limit defines a measure.

The lesson for QFT is familiar: path integrals are usually defined by regularization first, then limit. Writing a continuum action is compact notation, not a license to ignore ultraviolet roughness.

## Common pitfalls

### Thinking a random walk path has a well-defined velocity

The continuum Brownian path is too rough. Velocity is not a pointwise function. Use increments, quadratic variation, or heat kernels rather than naive derivatives.

### Confusing Euclidean and Lorentzian path integrals

Random walks are positive-measure objects. Lorentzian amplitudes are oscillatory. Wick rotation connects them in favorable cases, but they are not the same object.

### Ignoring the mass penalty

The mass term in a Euclidean propagator is not just a denominator decoration. In proper time it suppresses long paths by $e^{-m^2T}$ and controls correlation length.

### Treating recurrence as a UV statement

Recurrence and transience are infrared properties governed by large $T$. They are related to low-momentum behavior of Green functions, not to short-distance divergences.

### Forgetting boundary conditions

Random walks on bounded domains depend strongly on boundary behavior: absorbing, reflecting, periodic, and mixed boundaries produce different kernels and spectra.

## Exercises

### Exercise 1: Mean-square displacement

For the one-dimensional simple random walk with step size $a$, show that $\mathbb E[X_N^2]=Na^2$.

<details><summary><strong>Solution</strong></summary>

Write

$$
X_N=a\sum_{i=1}^N\epsilon_i,
$$

where $\mathbb E[\epsilon_i]=0$ and $\mathbb E[\epsilon_i\epsilon_j]=\delta_{ij}$. Then

$$
\mathbb E[X_N^2]
=a^2\sum_{i,j=1}^N\mathbb E[\epsilon_i\epsilon_j]
=a^2\sum_{i=1}^N1
=Na^2.
$$

</details>

### Exercise 2: Heat kernel normalization

Show that

$$
K_0(T;x,y)=\frac{1}{(4\pi T)^{d/2}}e^{-|x-y|^2/(4T)}
$$

is normalized as a transition density in $x$.

<details><summary><strong>Solution</strong></summary>

Shift $u=x-y$. Then

$$
\int d^dx\,K_0(T;x,y)
=\frac{1}{(4\pi T)^{d/2}}\int d^du\,e^{-u^2/(4T)}.
$$

The Gaussian integral is

$$
\int d^du\,e^{-u^2/(4T)}=(4\pi T)^{d/2}.
$$

Therefore

$$
\int d^dx\,K_0(T;x,y)=1.
$$

</details>

### Exercise 3: Proper-time propagator

Use

$$
\int_0^\infty dT\,e^{-T(p^2+m^2)}
$$

to recover the Euclidean momentum-space propagator.

<details><summary><strong>Solution</strong></summary>

For $p^2+m^2>0$,

$$
\int_0^\infty dT\,e^{-T(p^2+m^2)}
=\frac{1}{p^2+m^2}.
$$

Thus the proper-time integral represents the inverse of the positive operator $p^2+m^2$:

$$
G_m(p)=\frac{1}{p^2+m^2}.
$$

</details>

### Exercise 4: Recurrence criterion from the heat kernel

Use $K(T;0,0)\sim T^{-d/2}$ to determine for which dimensions the integral $\int^\infty dT\,K(T;0,0)$ diverges.

<details><summary><strong>Solution</strong></summary>

At large $T$,

$$
\int^\infty dT\,K(T;0,0)\sim \int^\infty dT\,T^{-d/2}.
$$

The integral $\int^\infty dT\,T^{-\alpha}$ diverges when $\alpha\le1$ and converges when $\alpha>1$. Here $\alpha=d/2$. Therefore the return integral diverges for

$$
d\le2,
$$

and converges for

$$
d>2.
$$

This matches recurrence in $d=1,2$ and transience for $d\ge3$.

</details>

## References

- Feller, *An Introduction to Probability Theory and Its Applications*.
- Lawler and Limic, *Random Walk: A Modern Introduction*.
- Simon, *Functional Integration and Quantum Physics*.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Polyakov, *Gauge Fields and Strings*.
- Schulman, *Techniques and Applications of Path Integration*.

## Version history

- **2026-06-27:** First polished draft. Introduces simple random walks, diffusion limits, heat kernels, massive propagators, lattice walk sums, recurrence, Feynman–Kac formulas, worldline representations, and polymer analogies.
