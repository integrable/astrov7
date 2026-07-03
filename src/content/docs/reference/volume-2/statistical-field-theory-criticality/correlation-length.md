---
title: "Correlation Length"
description: "A guide to the correlation length as the infrared scale of statistical field theory, its definitions, RG scaling, and relation to mass gaps and continuum limits."
sidebar:
  label: "Correlation Length"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021, critical phenomena chapters; Altland and Simons 2023, ch. 6; Schwartz 2014, ch. 23."
topics:
  - correlation length
  - two-point functions
  - critical phenomena
  - scaling
  - mass gap
  - continuum limit
canonicalTopics:
  - correlation-length
  - critical-scaling
  - mass-gap
  - second-moment-correlation-length
researchStatus:
  established:
    - "The divergence of the correlation length is the central long-distance signature of a continuous phase transition and is encoded by the exponent $\nu$."
  active:
    - "Precise correlation lengths, amplitude ratios, anisotropic scaling, boundary effects, disordered systems, and nonequilibrium definitions remain important in simulations, experiments, conformal bootstrap, and functional RG studies."
---

## Summary

The **correlation length** $\xi$ is the length scale over which fluctuations remain correlated. For a scalar order parameter $\phi(x)$, define the connected two-point function

$$
G_c(x)=\langle \phi(x)\phi(0)\rangle-\langle\phi\rangle^2.
$$

Away from a critical point in a phase with no massless modes, the large-distance behavior is typically

$$
G_c(r)\sim A\,r^{-p}e^{-r/\xi},
\qquad r=|x|,
$$

where the power $p$ depends on dimension and the spectrum of long-distance excitations. At a continuous critical point, the exponential cutoff disappears:

$$
\xi\to\infty,
\qquad
G_c(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

Near the critical temperature, with reduced temperature

$$
t\equiv \frac{T-T_c}{T_c},
$$

the correlation length diverges as

$$
\xi_\pm(t)=\xi_{0,\pm}|t|^{-\nu},
\qquad t\to0^\pm.
$$

The exponent $\nu$ is universal within a universality class. The amplitudes $\xi_{0,+}$ and $\xi_{0,-}$ are not universal by themselves, but their ratio can be universal.

:::note[Why this length is the hero]
A continuous phase transition is not defined by microscopic spins becoming infinitely large or by a coupling literally diverging. It is defined by the emergence of an infrared length scale much larger than the microscopic scale. The continuum field theory is the description of fluctuations at distances

$$
a\ll r\lesssim \xi,
$$

where $a$ is a lattice spacing or other microscopic cutoff.
:::

## Prerequisites

You should know [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/), [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/), [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/), [Wilson-Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/).

## Core idea

The correlation length is the inverse infrared mass scale of the statistical field theory. In a Euclidean field theory with a mass gap $m$, connected correlators decay exponentially:

$$
G_c(r)\sim e^{-mr}\times \text{power of }r,
$$

so

$$
\xi=\frac{1}{m}.
$$

In statistical mechanics this statement has a direct physical interpretation. If two local measurements are separated by many correlation lengths, their connected correlation is exponentially small. If they are separated by less than a correlation length, they still know about the same long-wavelength fluctuation.

At criticality, $m\to0$ and $\xi\to\infty$. This is why microscopic systems with very different lattice details can share the same continuum theory: when $\xi/a\gg1$, the long-distance physics has a wide scaling window and becomes insensitive to most short-distance information.

The renormalization group turns this intuition into a formula. If the temperature-like perturbation has RG eigenvalue $y_t$, then

$$
\nu=\frac{1}{y_t}.
$$

The correlation-length exponent is therefore not an independent decoration. It is the inverse eigenvalue of the relevant direction that moves the theory away from the critical surface.

## Setup and conventions

This page uses Euclidean statistical notation in $d$ spatial dimensions. The order parameter is a scalar $\phi(x)$ unless otherwise stated. For an $O(N)$ model, replace $\phi$ by $\boldsymbol\phi$ and use

$$
G_{ab}(x)=\langle \phi_a(x)\phi_b(0)\rangle_c.
$$

In the symmetric phase, rotational symmetry in internal space gives

$$
G_{ab}(x)=\delta_{ab}G_c(x).
$$

For an isotropic system, $G_c(x)$ depends only on

$$
r=|x|.
$$

The reduced temperature is

$$
t=\frac{T-T_c}{T_c},
$$

with $t>0$ usually denoting the disordered side of the transition for Ising-like systems. Some books use $\tau$ or $r-r_c$ instead. Near the critical point, all of these are proportional after a nonuniversal normalization.

The word **mass** on this page means Euclidean inverse correlation length, not necessarily the rest mass of a stable particle in a Lorentzian scattering experiment.

## Exponential correlation length

The exponential correlation length is defined by the large-distance decay of the connected correlator:

$$
\frac{1}{\xi_{\text{exp}}}
=-\lim_{r\to\infty}\frac{1}{r}\log |G_c(r)|,
$$

when the limit exists. This definition is direct and physically transparent. It asks: how fast does the connected correlation die at long distance?

In a transfer-matrix or Hamiltonian formulation, this length is controlled by the gap between the leading state and the next state that couples to the operator. In one lattice direction, if $\lambda_0$ and $\lambda_1$ are the two largest relevant transfer-matrix eigenvalues, then

$$
\xi_{\text{exp}}^{-1}=\log\frac{\lambda_0}{|\lambda_1|}.
$$

In a Euclidean continuum field theory, the same idea appears as the distance to the nearest singularity or pole in momentum space. For a free massive scalar,

$$
\widetilde G(k)=\frac{1}{k^2+m^2},
$$

so the inverse correlation length is

$$
\xi^{-1}=m.
$$

The exponential definition is excellent for phases with a single leading mass scale. It needs refinement in systems with several nearly degenerate lengths, oscillatory correlations, anisotropic scaling, algebraic order, Goldstone modes, or disorder-averaged rare-region effects.

## Second-moment correlation length

In simulations and experiments, it is often more practical to use the **second-moment correlation length**. Define the susceptibility-like integral

$$
\chi=\int d^d x\,G_c(x)=\widetilde G(0).
$$

Then define

$$
\xi_{\text{2nd}}^2
=\frac{1}{2d}\frac{\int d^d x\,x^2G_c(x)}{\int d^d x\,G_c(x)},
$$

provided the integrals converge. Equivalently, in momentum space,

$$
\xi_{\text{2nd}}^2
=-\frac{1}{2d\widetilde G(0)}
\left.\sum_{i=1}^d\frac{\partial^2\widetilde G(k)}{\partial k_i^2}\right|_{k=0}.
$$

If the small-momentum correlator has the Ornstein–Zernike form

$$
\widetilde G(k)=\frac{\widetilde G(0)}{1+\xi^2k^2+O(k^4)},
$$

then the second-moment definition returns the same $\xi$.

For a single-pole free scalar,

$$
\widetilde G(k)=\frac{1}{k^2+m^2}
=\frac{m^{-2}}{1+k^2/m^2},
$$

so

$$
\xi_{\text{2nd}}=\frac{1}{m}.
$$

For interacting systems, $\xi_{\text{exp}}$ and $\xi_{\text{2nd}}$ need not be exactly equal away from criticality, but their critical divergence is governed by the same exponent $\nu$ in ordinary scaling regimes.

## Gaussian example

Consider the quadratic Landau–Ginzburg action in the symmetric phase:

$$
S_2[\phi]=\frac12\int d^d x\left[(\nabla\phi)^2+r\phi^2\right],
\qquad r>0.
$$

The momentum-space two-point function is

$$
\widetilde G(k)=\frac{1}{k^2+r}.
$$

Therefore

$$
\xi=r^{-1/2}.
$$

If $r=a(T-T_c)+\cdots$, then

$$
\xi\propto (T-T_c)^{-1/2},
$$

so mean-field theory gives

$$
\nu_{\text{MF}}=\frac12.
$$

In position space, for large $r_{\text{pos}}=|x|$ in $d>1$,

$$
G_c(r_{\text{pos}})
\sim
\frac{e^{-r_{\text{pos}}/\xi}}{r_{\text{pos}}^{(d-1)/2}},
$$

up to a dimension-dependent normalization. The exponential part defines $\xi$; the power prefactor is a consequence of spreading in $d$ dimensions.

At criticality, the Gaussian correlator becomes

$$
\widetilde G(k)=\frac{1}{k^2},
\qquad
G_c(r)\sim \frac{1}{r^{d-2}},
$$

so the Gaussian anomalous dimension is

$$
\eta_{\text{G}}=0.
$$

## RG derivation of the exponent

Let $t$ be the temperature-like scaling field near a fixed point. Under an RG rescaling by a factor $b>1$, suppose

$$
t\longrightarrow t(b)=b^{y_t}t.
$$

Lengths rescale oppositely:

$$
\xi(t)=b\,\xi(t(b))
$$

if $b$ is viewed as a coarse-graining factor returning the system to the original cutoff units. Choose $b$ so that the renormalized perturbation is order one:

$$
b^{y_t}|t|\sim 1,
\qquad
b\sim |t|^{-1/y_t}.
$$

Once the perturbation is order one, the remaining correlation length in rescaled units is order one. Therefore

$$
\xi(t)\propto |t|^{-1/y_t}.
$$

Thus

$$
\nu=\frac{1}{y_t}.
$$

This formula is one of the cleanest bridges between RG geometry and measurable critical behavior.

## Scaling form of the two-point function

Near a critical point, the connected two-point function has the scaling form

$$
G_c(r;t)=\frac{1}{r^{d-2+\eta}}\,F_\pm\!\left(\frac{r}{\xi_\pm}\right),
$$

where $F_+$ and $F_-$ apply above and below the transition. The scaling function behaves roughly as

$$
F_\pm(s)\to \text{constant}\quad(s\ll1),
$$

and decays exponentially when

$$
s\gg1
$$

in a phase without massless modes.

This expression says that critical behavior has two parts:

1. the short-to-intermediate-distance power law fixed by the critical theory;
2. the long-distance cutoff controlled by the finite correlation length.

As $t\to0$, the cutoff is pushed to infinity and the pure critical power law remains.

## Above and below the transition

For an Ising-like system, there are generally two correlation-length amplitudes:

$$
\xi_+(t)=\xi_{0,+}t^{-\nu}\quad(t>0),
$$

and

$$
\xi_-(t)=\xi_{0,-}(-t)^{-\nu}\quad(t<0).
$$

The amplitudes are nonuniversal because they depend on how $t$ and microscopic length units are normalized. However, the ratio

$$
\frac{\xi_{0,+}}{\xi_{0,-}}
$$

is often universal within a universality class.

Below the transition, one must specify which fluctuation channel is being measured. In an Ising system, there is no continuous Goldstone mode, so connected correlations still decay exponentially away from criticality. In an $O(N)$ model with $N>1$, the ordered phase has Goldstone modes. Transverse correlations can decay algebraically even away from the critical point, while longitudinal correlations still have a finite massive scale. The phrase "the correlation length" is therefore context-dependent in phases with massless excitations.

## Continuum limit

The continuum limit of a lattice statistical system is not obtained by making the lattice spacing literally disappear while all dimensionless lattice observables remain fixed. It is obtained by tuning toward a critical point so that

$$
\frac{\xi}{a}\to\infty,
$$

where $a$ is the microscopic lattice spacing.

Physical distances are then held fixed in units of $\xi$ or another macroscopic scale. Operators are rescaled so that their correlators have finite limits. The field theory describes the universal scaling regime

$$
a\ll r\ll \xi
$$

near criticality, or

$$
a\ll r
$$

at the critical point itself.

This is why correlation length is the bridge between statistical mechanics and QFT. It is the knob that opens a wide separation between microscopic details and emergent continuum behavior.

## Common pitfalls

**Confusing $r$ with $|x|$.** In Landau–Ginzburg notation, $r$ often denotes the temperature-like mass parameter. In correlation functions, $r$ often denotes distance. This page writes $r=|x|$ only when the meaning is clear.

**Thinking $\xi$ is always a literal domain size.** The correlation length measures decay of connected correlations. It can be related to domains in some regimes, but it is more general than a picture of visible domains.

**Forgetting the connected correlator.** The full two-point function below an ordered transition contains $\langle\phi\rangle^2$. The correlation length is extracted from the connected part.

**Assuming one correlation length always suffices.** Systems with several fields, anisotropy, disorder, conserved quantities, Goldstone modes, or oscillatory correlations can have multiple meaningful lengths.

**Calling $\mu$ the correlation length.** The renormalization scale $\mu$ is a bookkeeping scale. The correlation length $\xi$ is a physical infrared scale.

**Setting $\epsilon=1$ and expecting miracles.** The epsilon expansion gives controlled analytic access near four dimensions. Numerical estimates in three dimensions often require higher orders and resummation.

## Relations to other pages

[Susceptibility and Critical Exponents](/renormalization-rg-eft/statistical-field-theory-criticality/susceptibility-and-critical-exponents/) explains how the integral of the two-point function diverges as $\chi\sim \xi^{2-\eta}$.

[Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/) will explain how the system size $L$ replaces $\xi$ when a finite box cuts off the critical divergence.

[Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) defines $\nu$ together with the other standard exponents.

[Wilson-Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/) computes $\nu$ perturbatively near four dimensions.

[Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) discusses the related high-energy language of masses, poles, and renormalized parameters.

## Research status

The basic scaling law

$$
\xi\sim |t|^{-\nu}
$$

is established for ordinary continuous transitions with short-range interactions and a single relevant temperature-like perturbation. Precision values of $\nu$ in important universality classes are now obtained by combining high-order perturbation theory, Monte Carlo simulations, conformal bootstrap, functional RG, and experiments.

Active research often concerns situations where the simple picture needs refinement: anisotropic scaling, quantum criticality with dynamic exponent $z$, disordered critical points, long-range interactions, boundary criticality, nonequilibrium transitions, dangerously irrelevant variables, topological sectors, and systems where multiple length scales compete.

## Exercises

### Exercise 1: Gaussian correlation length

For

$$
\widetilde G(k)=\frac{1}{k^2+r},
\qquad r>0,
$$

compute the second-moment correlation length from the small-$k$ expansion.

<details><summary><strong>Solution</strong></summary>

Rewrite the correlator as

$$
\widetilde G(k)=\frac{1}{r}\frac{1}{1+k^2/r}.
$$

Comparing with

$$
\widetilde G(k)=\frac{\widetilde G(0)}{1+\xi^2k^2+O(k^4)},
$$

we identify

$$
\xi^2=\frac{1}{r},
\qquad
\xi=r^{-1/2}.
$$

</details>

### Exercise 2: RG derivation of nu

Assume a temperature-like scaling field obeys $t(b)=b^{y_t}t$ under coarse graining by $b$. Use the fact that the correlation length has engineering dimension one to show that $\nu=1/y_t$.

<details><summary><strong>Solution</strong></summary>

The correlation length rescales as

$$
\xi(t)=b\,\xi(b^{y_t}t).
$$

Choose

$$
b=|t|^{-1/y_t},
$$

so that $b^{y_t}t$ is order one. Then $\xi(b^{y_t}t)$ is order one in cutoff units, and therefore

$$
\xi(t)\propto b\propto |t|^{-1/y_t}.
$$

Thus

$$
\nu=\frac{1}{y_t}.
$$

</details>

### Exercise 3: Connected versus disconnected pieces

In the ordered phase of a $Z_2$ model, suppose $\langle\phi\rangle=m\ne0$ and

$$
\langle\phi(x)\phi(0)\rangle=m^2+A e^{-|x|/\xi}.
$$

Which part is used to extract $\xi$?

<details><summary><strong>Solution</strong></summary>

The connected correlator is

$$
G_c(x)=\langle\phi(x)\phi(0)\rangle-\langle\phi\rangle^2
=Ae^{-|x|/\xi}.
$$

The constant piece $m^2$ records long-range order, not decay of fluctuations. The correlation length is extracted from the exponential decay of $G_c(x)$.

</details>

### Exercise 4: Scaling window

Explain why a continuum field-theory description of a lattice critical point requires $\xi/a\gg1$ rather than merely $\xi$ large in meters.

<details><summary><strong>Solution</strong></summary>

The continuum approximation ignores microscopic lattice details. This is justified only when there is a large range of distances much larger than the lattice spacing but smaller than the infrared cutoff:

$$
a\ll r\lesssim \xi.
$$

The dimensionless ratio $\xi/a$ measures the width of this scaling window. A length may be large in meters but still only a few lattice spacings; then the microscopic details have not decoupled.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), for the modern RG view of correlation length, fixed points, scaling, and universality.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic treatments of correlation functions, renormalization, critical exponents, and amplitude ratios.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, for a field-theoretic route from statistical models to RG and correlation lengths.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for renormalization-group intuition and scalar-mass flows from a particle-physics perspective.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for a clear scaling-oriented presentation of correlation length and critical phenomena.

## Version history

- 2026-06-18: First polished draft. Added exponential, second-moment, Gaussian, RG, continuum-limit, and amplitude-ratio interpretations of the correlation length.
