---
title: "Gaussian Free Field"
description: "Constructs the Gaussian free field as a Euclidean generalized random field, records its Schwinger functions, and checks the Osterwalder–Schrader conditions."
sidebar:
  label: "Gaussian Free Field"
  order: 7
level: Graduate
status: "Polished draft"
source: "Nelson; Osterwalder–Schrader; Glimm–Jaffe; Simon."
topics:
  - Gaussian free field
  - Euclidean covariance
  - reflection positivity
  - Wick theorem
  - Osterwalder–Schrader reconstruction
canonicalTopics:
  - gaussian-free-field
  - euclidean-quantum-field-theory
  - osterwalder-schrader-qft
researchStatus:
  established:
    - "The massive Gaussian free field is a completely rigorous Euclidean QFT and satisfies the Osterwalder–Schrader requirements in the scalar bosonic setting."
  active:
    - "Massless limits, composite fields, boundary conditions, curved backgrounds, and gauge analogues require additional analysis beyond the basic massive model."
---

## Summary

The Gaussian free field is the Euclidean form of the free scalar quantum field. It is a centered Gaussian generalized random field $\Phi$ with covariance

$$
C_m=(-\Delta_E+m^2)^{-1},
\qquad m>0,
$$

meaning that for test functions $f,g\in\mathcal S(\mathbb R^d)$,

$$
\mathbb E[\Phi(f)\Phi(g)]=C_m(f,g).
$$

Its Schwinger functions are determined by Wick's rule:

$$
S_{2n}(x_1,\ldots,x_{2n})
=
\sum_{\text{pairings }P}
\prod_{\{i,j\}\in P}C_m(x_i-x_j),
\qquad
S_{2n+1}=0.
$$

This page explains the construction, the covariance, the Wick rule, and the Osterwalder–Schrader checks. The main point is that the phrase "Euclidean path integral for the free scalar" can be replaced here by an honest Gaussian probability measure on distributions.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Gaussian free field data and reconstruction](/figures/rigorous-qft/gaussian-free-field-data.svg)

<figcaption>

The massive Gaussian free field starts from the positive operator $K=-\Delta_E+m^2$, uses its inverse $C_m=K^{-1}$ as covariance, defines a Gaussian measure on distributions, produces Wick Schwinger functions, and reconstructs the free scalar Wightman theory.

</figcaption>
</figure>

## Prerequisites

Read [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/), [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) first. The distributional background comes from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and the reconstructed Lorentzian target is explained in [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/).

The page uses flat Euclidean space $\mathbb R^d$ and a real scalar field. The massive case $m>0$ is the clean first model because it avoids infrared zero-mode difficulties.

## Logical status

| Item | Status |
|---|---|
| Page type | Construction and model page. |
| Framework | Scalar Euclidean QFT on $\mathbb R^d$. |
| Object constructed | A Gaussian probability measure on $\mathcal S'(\mathbb R^d)$ with covariance $(-\Delta_E+m^2)^{-1}$. |
| Main result | The resulting Schwinger functions satisfy the OS axioms and reconstruct the free scalar Wightman theory. |
| Main caveat | The field is usually a distribution, not a pointwise random function. Composite fields require Wick ordering or renormalized definitions. |

## Core idea

A finite-dimensional centered Gaussian random vector is determined by its covariance matrix. The Gaussian free field is the infinite-dimensional version: it is determined by a covariance operator. The formal Euclidean action

$$
S_E[\phi]=\frac12\int_{\mathbb R^d}
\left((\nabla\phi)^2+m^2\phi^2\right)d^dx
$$

suggests the inverse covariance

$$
K=-\Delta_E+m^2.
$$

The rigorous statement is not that one integrates over ordinary functions $\phi(x)$. Instead, one constructs a Gaussian probability measure on tempered distributions $\Phi\in\mathcal S'(\mathbb R^d)$ whose characteristic functional is

$$
\int_{\mathcal S'}e^{i\Phi(f)}\,d\mu_C(\Phi)
=
\exp\left(-\frac12 C_m(f,f)\right).
$$

This is the correct model for the free scalar Euclidean field. Point values $\Phi(x)$ are notation; smeared variables $\Phi(f)$ are the random variables.

## Setup and conventions

Use Euclidean coordinates $x=(\tau,\mathbf x)$ and Euclidean momentum $p=(p_0,\mathbf p)$, with

$$
p_E^2=p_0^2+\mathbf p^2.
$$

For a Schwartz test function, take

$$
\widetilde f(p)=\int_{\mathbb R^d}d^dx\,e^{-ip\cdot_E x}f(x),
\qquad
p\cdot_E x=p_0\tau+\mathbf p\cdot\mathbf x.
$$

The massive covariance is the positive tempered distribution

$$
C_m(f,g)=
\int\frac{d^dp}{(2\pi)^d}
\frac{\overline{\widetilde f(p)}\,\widetilde g(p)}{p_E^2+m^2}.
$$

Equivalently, its kernel is the Green distribution solving

$$
(-\Delta_E+m^2)C_m(x)=\delta^{(d)}(x).
$$

Because $p_E^2+m^2>0$, the quadratic form $C_m(f,f)$ is nonnegative. Since $C_m$ is continuous on the Schwartz space, the Bochner–Minlos theorem gives a unique centered Gaussian probability measure on $\mathcal S'(\mathbb R^d)$ with this characteristic functional.

## The Schwinger functions

The $n$-point Schwinger distributions are the moments of the Gaussian field:

$$
S_n(f_1,\ldots,f_n)
=
\int_{\mathcal S'}
\Phi(f_1)\cdots\Phi(f_n)\,d\mu_C(\Phi).
$$

Since the measure is centered Gaussian,

$$
S_1=0,
\qquad
S_2(f,g)=C_m(f,g),
$$

and all higher moments are obtained by pairings. In smeared form,

$$
S_{2n}(f_1,\ldots,f_{2n})
=
\sum_{P}\prod_{\{i,j\}\in P}C_m(f_i,f_j),
\qquad
S_{2n+1}=0.
$$

This is Wick's theorem, but here it is a theorem of Gaussian probability rather than a diagrammatic rule. The Feynman diagrams of the free Euclidean theory are just a graphical notation for Gaussian pairings.

The source generating functional is correspondingly simple. For real $J\in\mathcal S(\mathbb R^d)$,

$$
Z[J]
=
\mathbb E\left[e^{\Phi(J)}\right]
=
\exp\left(\frac12 C_m(J,J)\right).
$$

Derivatives of $Z[J]$ at $J=0$ reproduce the Schwinger functions.

## Euclidean invariance

The covariance is translation invariant because its kernel depends only on $x-y$. It is rotation invariant because the denominator $p_E^2+m^2$ is invariant under $O(d)$. Thus

$$
C_m(Rx+a,Ry+a)=C_m(x,y)
$$

in the distributional sense. Since all Schwinger functions are sums of products of $C_m$, the entire family $S_n$ is Euclidean invariant.

The same argument also gives permutation symmetry. Products in a classical probability space commute, so

$$
S_n(x_{\sigma(1)},\ldots,x_{\sigma(n)})
=
S_n(x_1,\ldots,x_n)
$$

for every permutation $\sigma$, again as a distributional statement.

## Reflection positivity

Reflection positivity is the decisive OS check. Let

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x),
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The covariance has the mixed representation

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}}.
$$

If $f$ is supported in positive Euclidean time, then

$$
\begin{aligned}
C_m(\theta\overline f,f)
&=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{1}{2\omega_{\mathbf p}}
\left|
\int_0^\infty d\tau\,
 e^{-\omega_{\mathbf p}\tau}
 \widetilde f(\tau,\mathbf p)
\right|^2
\ge0.
\end{aligned}
$$

This identity is the one-particle heart of reflection positivity. For polynomial observables, Gaussian Wick expansion upgrades this covariance positivity to full OS reflection positivity.

Notice what is special. Ordinary positive definiteness of $C_m$ as a covariance is not the same condition as reflection positivity. The formula above uses the split of Euclidean time into positive and negative halves and the exponential kernel $e^{-\omega\tau}$ that later becomes $e^{-\tau H}$.

## What OS reconstruction gives

Applying OS reconstruction to the Gaussian free field gives the usual free scalar Wightman theory. On the one-particle subspace, a positive-time test function $f$ maps to the momentum-space wavefunction

$$
\widehat f_+(\mathbf p)
=
\int_0^\infty d\tau\,
 e^{-\omega_{\mathbf p}\tau}
 \widetilde f(\tau,\mathbf p),
$$

with inner product

$$
\langle f,g\rangle_1
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{\overline{\widehat f_+(\mathbf p)}\widehat g_+(\mathbf p)}
{2\omega_{\mathbf p}}.
$$

The full Hilbert space is the bosonic Fock space over this one-particle space. Euclidean time translations act as $e^{-\tau H}$, and the reconstructed Hamiltonian is the second quantization of multiplication by $\omega_{\mathbf p}$.

Thus the free scalar field is not merely a motivating example. It is the benchmark in which the Euclidean measure, OS positivity, Hilbert-space reconstruction, Wightman functions, and particle interpretation all match explicitly.

## Singularities and Wick powers

For $d\ge2$, the kernel $C_m(x)$ is singular at $x=0$. The field $\Phi$ is therefore not an ordinary random function. In fact, typical samples of the Gaussian free field are distributions of negative regularity.

The square $\Phi(x)^2$ is not automatically defined. The correct free-field composite is the Wick square

$$
:\!\Phi^2\!:(f),
$$

obtained by subtracting the divergent covariance before removing a regulator. More generally, Wick powers and Wick products are well-defined as random distributions after renormalization. This is the free-field prototype for the more difficult problem of defining composite fields in interacting Euclidean QFT.

## Massless and finite-volume caveats

The massive field on $\mathbb R^d$ is the clean model. The massless covariance $1/p_E^2$ has infrared subtleties near $p=0$. In dimensions where

$$
\int_{|p|<1}\frac{d^dp}{p^2}
$$

fails to be locally integrable against arbitrary test functions, one must remove the zero mode, restrict to test functions of integral zero, work in finite volume with boundary conditions, or change the observable algebra.

This is why the two-dimensional massless scalar is often better treated through derivatives, vertex operators with charge-neutrality conditions, or compactified boson data rather than through an unconstrained point field.

## Common pitfalls

**Thinking the field is a random function.** The rigorous object is a random distribution. Values like $\Phi(x)$ are shorthand for limiting or smeared operations.

**Confusing covariance positivity with reflection positivity.** Gaussian covariance positivity constructs the Euclidean probability measure. Reflection positivity is the additional time-reflection inequality needed to reconstruct a Hilbert space.

**Forgetting the zero mode.** The massless limit is not obtained by blindly setting $m=0$ in every formula. Infrared behavior depends strongly on dimension and boundary conditions.

**Treating Wick powers as ordinary powers.** Products at the same point require subtraction. The notation $:\!\Phi^k\!:$ is a renormalized object, not a decorative pair of colons.

**Assuming the free model represents the hard part of constructive QFT.** The Gaussian measure is the starting point. Interacting Euclidean measures require controlling non-Gaussian weights, ultraviolet limits, and renormalization.

## Relations to other pages

The Gaussian free field is the canonical example for [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). Its Lorentzian counterpart is the free scalar Wightman theory discussed in the Wightman chapter.

Later constructive pages use the Gaussian free field as the reference measure for interacting models such as $P(\phi)_2$ and $\phi^4_3$. Later pages on path integrals as measures explain why this model is one of the rare cases where the formal expression $e^{-S_E[\phi]}D\phi$ can be replaced directly by a probability measure.

## Research status

The massive Gaussian free field is fully established and forms part of the standard rigorous foundation of Euclidean QFT. It satisfies the scalar OS axioms and reconstructs the free scalar Wightman theory.

What remains delicate is not the free construction itself but the structures built on top of it: Wick powers, interacting measures, scaling limits, massless fields, boundary conditions, fermionic variants, gauge theories, curved backgrounds, and probabilistic regularity theory.

## Exercises

### Exercise 1

Show that the covariance kernel satisfies

$$
(-\Delta_E+m^2)C_m=\delta^{(d)}
$$

in the sense of distributions.

<details>
<summary><strong>Solution</strong></summary>

For test functions $f,g\in\mathcal S(\mathbb R^d)$,

$$
C_m(f,g)=
\int\frac{d^dp}{(2\pi)^d}
\frac{\overline{\widetilde f(p)}\widetilde g(p)}{p_E^2+m^2}.
$$

Applying $(-\Delta_E+m^2)$ to the first kernel variable multiplies the Fourier transform by $p_E^2+m^2$. Therefore

$$
\left((-\Delta_E+m^2)C_m\right)(f,g)
=
\int\frac{d^dp}{(2\pi)^d}
\overline{\widetilde f(p)}\widetilde g(p),
$$

which is the distributional pairing of $\delta^{(d)}(x-y)$ with $\overline f(x)g(y)$.

</details>

### Exercise 2

Derive the mixed representation

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
C_m(\tau,\mathbf x)=
\int\frac{dp_0}{2\pi}
\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{ip_0\tau+i\mathbf p\cdot\mathbf x}}
{p_0^2+\omega_{\mathbf p}^2}.
$$

The one-dimensional integral is standard:

$$
\int\frac{dp_0}{2\pi}
\frac{e^{ip_0\tau}}{p_0^2+\omega^2}
=
\frac{e^{-\omega|\tau|}}{2\omega}.
$$

Substituting $\omega=\omega_{\mathbf p}$ gives the formula.

</details>

### Exercise 3

Use Wick's rule to compute the four-point Schwinger function of the Gaussian free field.

<details>
<summary><strong>Solution</strong></summary>

There are three pairings of four labels. Therefore

$$
\begin{aligned}
S_4(x_1,x_2,x_3,x_4)
&=C_m(x_1-x_2)C_m(x_3-x_4)
\\
&\quad+C_m(x_1-x_3)C_m(x_2-x_4)
\\
&\quad+C_m(x_1-x_4)C_m(x_2-x_3).
\end{aligned}
$$

The connected four-point function vanishes. This is the probabilistic statement that a centered Gaussian field has no cumulants of order higher than two.

</details>

## References

- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- E. Nelson, "The Free Markoff Field," *Journal of Functional Analysis* **12** (1973), 211–227. DOI: [10.1016/0022-1236(73)90025-6](https://doi.org/10.1016/0022-1236(73)90025-6).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.

## Version history

- **2026-06-28:** Initial polished page.
