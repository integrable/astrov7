---
title: "Wick Rotation: Rigorous View"
description: "Explains Wick rotation as analytic continuation of correlation distributions, not as a formal substitution in an arbitrary path integral."
sidebar:
  label: "Wick Rotation"
  order: 8
level: Advanced
status: "Polished draft"
source: "Wick; Schwinger; Wightman; Osterwalder–Schrader; Streater–Wightman; Glimm–Jaffe."
topics:
  - Wick rotation
  - analytic continuation
  - Wightman functions
  - Schwinger functions
  - Osterwalder–Schrader reconstruction
canonicalTopics:
  - wick-rotation
  - euclidean-quantum-field-theory
  - analytic-continuation-in-qft
researchStatus:
  established:
    - "In Wightman and Osterwalder–Schrader frameworks, Wick rotation is controlled by analyticity, spectral support, locality, and reflection positivity."
  active:
    - "Real-time reconstruction from approximate Euclidean data, especially in numerical and gauge-theoretic settings, is often ill-conditioned or framework-dependent."
---

## Summary

Wick rotation is the controlled passage between Lorentzian time $t$ and Euclidean time $\tau$. In physics notation one writes

$$
t=-i\tau,
$$

but the rigorous content is not a bare substitution. It is a statement about analytic continuation of correlation distributions and about which boundary value of an analytic function is being taken.

In a positive-energy Lorentzian QFT, the spectral condition makes Wightman functions boundary values of analytic functions in complexified spacetime. In favorable cases, their values at imaginary times give Euclidean Schwinger functions. Conversely, Schwinger functions satisfying the Osterwalder–Schrader axioms reconstruct a Lorentzian Wightman theory.

The slogan is therefore

$$
\text{Wick rotation}
=
\text{analytic continuation}
+
\text{positivity data}.
$$

Without analyticity, the symbol $t=-i\tau$ has no theorem behind it. Without reflection positivity, Euclidean correlation functions may fail to reconstruct a Hilbert space with positive norm.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Wick rotation as analytic continuation and boundary values](/figures/rigorous-qft/wick-rotation-analytic-continuation.svg)

<figcaption>

Rigorous Wick rotation compares boundary values of analytic correlation functions. Lorentzian correlators live on real time with an $i\epsilon$ prescription; Euclidean Schwinger functions are obtained on imaginary time in ordered regions; OS reconstruction goes back using reflection positivity.

</figcaption>
</figure>

## Prerequisites

Read [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) and [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) for the Lorentzian analytic side. Read [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) for the Euclidean side.

The free scalar example from [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) is the best concrete model to keep in mind.

## Logical status

| Item | Status |
|---|---|
| Page type | Bridge and caveat page. |
| Framework | Wightman QFT and Osterwalder–Schrader Euclidean QFT. |
| Main input from Lorentzian QFT | Spectrum condition, locality, covariance, and distributional boundary values. |
| Main input from Euclidean QFT | Reflection positivity and OS reconstruction hypotheses. |
| Main caveat | Wick rotation is not a general method for defining Lorentzian path integrals by changing variables. |

## Core idea

The reason imaginary time helps is already visible for a positive-energy state. Lorentzian time evolution contains phases,

$$
e^{-itH},
$$

whereas imaginary time gives decay,

$$
e^{-\tau H},
\qquad \tau>0.
$$

If $H\ge0$, the second expression is bounded. That boundedness is the analytic seed of Euclidean QFT. Correlation functions that oscillate in real time may become better-behaved functions or distributions in imaginary time.

But this reasoning is not reversible by algebra alone. Many Euclidean functions have no positive-energy Lorentzian interpretation. OS reflection positivity is the condition that remembers the Hilbert-space inner product lost when real time was replaced by imaginary time.

## Setup and conventions

Use the mostly-minus Lorentzian convention from the site conventions:

$$
p\cdot x=p^0t-\mathbf p\cdot\mathbf x.
$$

Complexify time by

$$
z^0=t-i\tau.
$$

For a positive-energy plane wave,

$$
e^{-ip^0z^0}=e^{-ip^0t}e^{-p^0\tau},
$$

so $\tau>0$ produces damping when $p^0\ge0$. A Euclidean point is reached by setting $t=0$ and $z^0=-i\tau$.

The Euclidean squared momentum is written

$$
p_E^2=p_0^2+\mathbf p^2,
$$

and the free massive Euclidean covariance is

$$
C_m(p_E)=\frac{1}{p_E^2+m^2}.
$$

The corresponding Lorentzian Feynman denominator is

$$
\frac{i}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ is not cosmetic. It specifies a boundary value and tells the contour how to pass the poles.

## Free two-point function

For the free scalar field, the Euclidean covariance can be written as

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}},
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The Lorentzian Feynman two-point function is

$$
D_F(t,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}}
{2\omega_{\mathbf p}}
\left(
\theta(t)e^{-i\omega_{\mathbf p}t}
+
\theta(-t)e^{i\omega_{\mathbf p}t}
\right).
$$

For $\tau>0$, analytic continuation of the positive-time branch gives

$$
D_F(-i\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}\tau}}
{2\omega_{\mathbf p}}
=
C_m(\tau,\mathbf x).
$$

This calculation is the friendly face of Wick rotation. It works because the pole prescription, the sign of the energy, and the time-ordering agree.

## Wightman functions and tube analyticity

The deeper Lorentzian statement concerns Wightman functions, not merely Feynman propagators. For a scalar field,

$$
W_n(x_1,\ldots,x_n)
=
\langle\Omega,
\phi(x_1)\cdots\phi(x_n)\Omega\rangle.
$$

By translation invariance, write them in difference variables

$$
\xi_j=x_j-x_{j+1},
\qquad j=1,\ldots,n-1.
$$

The spectral condition implies that the Fourier transforms have support in the forward light cone. Consequently the Wightman distributions are boundary values of functions analytic in a tube domain. With the convention $z^0=t-i\tau$, the sign can be written schematically as

$$
-\operatorname{Im}\xi_j\in V_+,
\qquad j=1,\ldots,n-1.
$$

This is the rigorous replacement for the informal idea that one may "rotate time." The analytic function exists in a domain because energy is positive. Lorentzian correlation functions are recovered as boundary values at real spacetime points. Euclidean Schwinger functions are obtained by restricting to imaginary-time configurations in ordered regions.

## Ordering and Schwinger functions

With the convention $z^0=-i\tau$, one convenient ordered Euclidean region for the displayed Wightman ordering is

$$
\tau_1>\tau_2>\cdots>\tau_n.
$$

In this region, the Euclidean Schwinger function is the analytic continuation of the Wightman ordering

$$
\langle\Omega,
\phi(z_1)\phi(z_2)\cdots\phi(z_n)
\Omega\rangle,
\qquad
z_j=(-i\tau_j,\mathbf x_j).
$$

Other Euclidean time orderings correspond to other Wightman orderings. Locality is what lets these pieces glue into a symmetric Euclidean Schwinger distribution. This is why locality and analyticity appear together in the Wightman theory, and why permutation symmetry appears naturally in the OS axioms.

For time-ordered Lorentzian correlators, the same information is packaged differently: the $i\epsilon$ prescription chooses which boundary value one approaches when times collide or reorder.

## Lorentzian to Euclidean

Starting with a Wightman theory, the route to Euclidean data has three conceptual steps.

1. Use the spectral condition to obtain analytic functions in tube domains.
2. Use locality to continue and compare different orderings.
3. Restrict to imaginary-time Euclidean points to obtain Schwinger functions.

Under the usual hypotheses, the resulting Schwinger functions satisfy Euclidean covariance, symmetry, regularity, and reflection positivity. Reflection positivity follows from the original Hilbert-space positivity. In this direction, the Hilbert space is already known; the Euclidean theory inherits positivity from it.

## Euclidean to Lorentzian

Starting with Euclidean data, the route back is not to replace $\tau$ by $it$ in every formula. The route is OS reconstruction.

Given Schwinger functions satisfying the OS axioms, one first builds a Hilbert space from positive-time Euclidean observables using

$$
\langle F,G\rangle_{\mathrm{OS}}
=
\langle \Theta F\,G\rangle_E.
$$

Then positive Euclidean time translations become

$$
T(\tau)=e^{-\tau H},
\qquad H\ge0.
$$

The reconstructed Wightman functions are obtained as Lorentzian boundary values of analytic continuations of the Euclidean data. Thus OS reconstruction is the rigorous Euclidean-to-Lorentzian Wick rotation theorem.

## Momentum-space contour picture

For perturbation theory, Wick rotation is often presented as a contour deformation in the energy variable. For the free scalar propagator one starts with

$$
\frac{i}{(p^0)^2-\mathbf p^2-m^2+i\epsilon}
$$

and rotates the $p^0$ contour to imaginary energy. Formally, with $p^0=ip_0$, this becomes

$$
\frac{1}{p_0^2+\mathbf p^2+m^2}.
$$

This picture is useful but conditional. It assumes that the contour can be moved without crossing singularities and that the arc at infinity does not contribute. In loop integrals, thresholds, branch cuts, finite density, real-time response functions, and nonperturbative problems can make the analytic structure much more complicated.

The rigorous correlation-function viewpoint is safer: first identify the analytic domain and boundary values; then interpret contour manipulations as consequences of that analytic structure.

## Common pitfalls

**Treating Wick rotation as a change of variables in a measure.** Lorentzian path integrals are usually oscillatory objects, not probability measures. Euclideanization may produce a measure in special cases, but it is not automatic.

**Dropping the $i\epsilon$.** The $i\epsilon$ prescription records which boundary value is meant. Removing it before analytic continuation loses information.

**Ignoring reflection positivity.** Euclidean invariance and smoothness do not guarantee a positive Hilbert space. Reflection positivity is the missing unitarity data.

**Assuming all real-time observables are easy to recover.** Analytic continuation from noisy or discrete Euclidean data is often severely ill-conditioned. This is a major practical issue in lattice and thermal QFT.

**Using the same rule at finite temperature without changes.** Thermal Euclidean time is compact, and the Lorentzian reconstruction is governed by KMS analyticity rather than the vacuum OS theorem in its simplest form.

**Forgetting gauge and fermion subtleties.** Fermions require graded reflection positivity and spin structure conventions. Gauge theories often require working with gauge-invariant observables, gauge fixing plus ghosts, or lattice formulations.

## Relations to other pages

This page connects the Wightman chapter and the Osterwalder–Schrader chapter. The Lorentzian analytic facts are introduced in [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/). The Euclidean reconstruction theorem is developed in [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/).

The free scalar computation is the analytic counterpart of the [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) construction. Later pages on path integrals as measures and Lorentzian path integrals explain why Euclidean measures are far better behaved than oscillatory real-time integrals.

## Research status

The analytic-continuation relation between Wightman and OS frameworks is established under precise hypotheses. In constructive models, proving those hypotheses is part of the construction.

Several active or delicate areas remain. Analytic continuation from numerical Euclidean data is ill-posed; gauge theories require care with the physical Hilbert space; real-time finite-density systems may have sign problems and complicated singularities; curved spacetimes do not generally have a global Wick rotation.

## Exercises

### Exercise 1

For the free scalar field, verify directly that $D_F(-i\tau,\mathbf x)=C_m(\tau,\mathbf x)$ for $\tau>0$ using the mixed momentum representation.

<details>
<summary><strong>Solution</strong></summary>

For $t>0$,

$$
D_F(t,\mathbf x)=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-i\omega_{\mathbf p}t}}
{2\omega_{\mathbf p}}.
$$

Set $t=-i\tau$ with $\tau>0$. Then

$$
e^{-i\omega_{\mathbf p}(-i\tau)}=e^{-\omega_{\mathbf p}\tau},
$$

so

$$
D_F(-i\tau,\mathbf x)=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}\tau}}
{2\omega_{\mathbf p}}
=C_m(\tau,\mathbf x).
$$

</details>

### Exercise 2

Explain why positive energy is needed for imaginary-time damping.

<details>
<summary><strong>Solution</strong></summary>

For an energy eigenstate with energy $E$, complex time gives

$$
e^{-iE(t-i\tau)}=e^{-iEt}e^{-E\tau}.
$$

If $E\ge0$ and $\tau>0$, this is bounded by $1$ in magnitude. If arbitrarily negative energies were present, the factor $e^{-E\tau}$ would grow exponentially. Thus the spectral condition is what makes the forward imaginary-time continuation behave like a Laplace transform rather than an uncontrolled exponential growth.

</details>

### Exercise 3

A Euclidean two-point function of a quantum-mechanical system has the spectral form

$$
S(\tau)=\int_0^\infty e^{-E\tau}\,d\rho(E),
\qquad \tau>0.
$$

What Lorentzian object does it suggest, and why is recovering $d\rho$ from approximate $S(\tau)$ difficult?

<details>
<summary><strong>Solution</strong></summary>

The expression is a Laplace transform. The corresponding Lorentzian positive-frequency correlation is formally

$$
W(t)=\int_0^\infty e^{-iEt}\,d\rho(E).
$$

Recovering $d\rho$ from exact $S(\tau)$ is an inverse Laplace-transform problem. From approximate or finitely sampled Euclidean data it is ill-conditioned: high-energy and fine spectral features can have exponentially small effects on $S(\tau)$ at accessible Euclidean times.

</details>

## References

- G. C. Wick, "Properties of Bethe–Salpeter Wave Functions," *Physical Review* **96** (1954), 1124–1134. DOI: [10.1103/PhysRev.96.1124](https://doi.org/10.1103/PhysRev.96.1124).
- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- J. Schwinger, "On the Euclidean Structure of Relativistic Field Theory," *Proceedings of the National Academy of Sciences* **44** (1958), 956–965. DOI: [10.1073/pnas.44.9.956](https://doi.org/10.1073/pnas.44.9.956).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press, 2000.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

## Version history

- **2026-06-28:** Initial polished page.
