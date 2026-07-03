---
title: "Susceptibility and Critical Exponents"
description: "A derivation-focused page on susceptibility as an integrated connected correlator and its scaling relations with critical exponents."
sidebar:
  label: "Susceptibility and Critical Exponents"
  order: 8
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021, critical phenomena chapters; Coleman 1985, Dilatations; Altland and Simons 2023, ch. 6."
topics:
  - susceptibility
  - critical exponents
  - connected correlation functions
  - fluctuation-response relation
  - Fisher scaling relation
  - finite-size scaling
canonicalTopics:
  - susceptibility
  - critical-exponents
  - fisher-scaling-relation
  - fluctuation-response
researchStatus:
  established:
    - 'Static susceptibility is the zero-momentum connected two-point function and diverges near ordinary continuous transitions as $\chi\sim |t|^{-\gamma}$.'
  active:
    - "Precision exponent estimates, amplitude ratios, disordered systems, quantum critical response, finite-size scaling, and nonequilibrium susceptibilities remain active across statistical field theory and condensed matter physics."
---

## Summary

The **susceptibility** measures how strongly an order parameter responds to its conjugate source. If $h$ couples to a scalar order parameter by

$$
S\to S-h\int d^d x\,\phi(x),
$$

then the uniform magnetization is

$$
m=\frac{1}{V}\frac{\partial \log Z}{\partial h},
$$

and the static susceptibility is

$$
\chi=\left.\frac{\partial m}{\partial h}\right|_{h=0}.
$$

Equivalently,

$$
\chi=\int d^d x\,G_c(x)=\widetilde G_c(k=0),
$$

where

$$
G_c(x)=\langle\phi(x)\phi(0)\rangle-\langle\phi\rangle^2.
$$

Near a continuous transition,

$$
\chi_\pm(t)=C_\pm |t|^{-\gamma},
\qquad
\xi_\pm(t)=\xi_{0,\pm}|t|^{-\nu}.
$$

At criticality,

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

Combining these statements gives the Fisher scaling relation

$$
\gamma=(2-\eta)\nu,
$$

for ordinary scaling regimes.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 54rem;">

![Correlation length cuts off the critical two-point function, and susceptibility is the integral of that connected correlation.](/figures/renormalization-rg-eft/correlation-length-susceptibility-map.svg)

<figcaption>

The susceptibility is the zero-momentum connected two-point function. Near criticality, $G_c(r)$ has a critical power law up to the cutoff scale $\xi$. Integrating this correlated volume gives $\chi\sim\xi^{2-\eta}$ and hence $\gamma=(2-\eta)\nu$.

</figcaption>
</figure>

:::note[Susceptibility is a response and a fluctuation]
The same quantity can be read two ways: as the derivative of the order parameter with respect to a source, or as the integrated connected fluctuation of the order parameter. Missing the word connected is the classic trapdoor.
:::

## Prerequisites

You should know [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/), [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/), [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), and [Wilson-Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/).

## Core idea

The susceptibility diverges at a continuous transition because a uniform source talks to an increasingly large correlated region. If a fluctuation at one point influences a region of size $\xi$, then the response to a uniform source collects contributions from that whole region.

Mathematically, the susceptibility is the integral of the connected two-point function:

$$
\chi=\int d^d x\,G_c(x).
$$

At criticality the connected correlator has the power law

$$
G_c(r)\sim r^{-(d-2+\eta)}.
$$

Away from criticality, the correlation length cuts off this power law at $r\sim\xi$. Therefore, by scaling,

$$
\chi\sim \int^{\xi} d^d x\,\frac{1}{r^{d-2+\eta}}
\sim \int^{\xi} dr\,r^{1-\eta}
\sim \xi^{2-\eta}.
$$

Since

$$
\xi\sim |t|^{-\nu},
$$

we obtain

$$
\chi\sim |t|^{-\nu(2-\eta)}.
$$

Thus

$$
\gamma=(2-\eta)\nu.
$$

This relation is powerful because it ties a thermodynamic response exponent $\gamma$ to the spatial decay exponent $\eta$ and the length exponent $\nu$.

## Setup and conventions

Use the Euclidean partition function

$$
Z[h]=\int\mathcal D\phi\,
\exp\left[-S[\phi]+h\int d^d x\,\phi(x)\right].
$$

The total order parameter is

$$
M=\int d^d x\,\phi(x),
$$

and the volume is $V$. The magnetization density is

$$
m=\frac{\langle M\rangle}{V}.
$$

With the normalization above, the susceptibility is

$$
\chi=\frac{1}{V}\left(\langle M^2\rangle-\langle M\rangle^2\right).
$$

Equivalently, assuming translation invariance,

$$
\chi=\int d^d x\,\left[\langle\phi(x)\phi(0)\rangle-\langle\phi\rangle^2\right].
$$

Some statistical-mechanics books define the physical magnetic susceptibility with an extra factor of inverse temperature $\beta_{\text{therm}}=1/(k_BT)$, depending on whether $h$ is an energy-like magnetic field or a dimensionless source. This page absorbs such conventional factors into the normalization of $h$ and focuses on critical scaling.

## Fluctuation-response derivation

Differentiate the magnetization with respect to the source:

$$
\frac{\partial m}{\partial h}
=\frac{1}{V}\frac{\partial^2\log Z}{\partial h^2}.
$$

The first derivative gives

$$
\frac{\partial\log Z}{\partial h}=\langle M\rangle.
$$

The second derivative gives the connected fluctuation:

$$
\frac{\partial^2\log Z}{\partial h^2}
=\langle M^2\rangle-\langle M\rangle^2.
$$

Therefore

$$
\chi=\frac{1}{V}\left(\langle M^2\rangle-\langle M\rangle^2\right).
$$

Using

$$
M=\int d^d x\,\phi(x),
$$

we find

$$
\chi
=\frac{1}{V}\int d^d x\,d^d y\,
\langle\phi(x)\phi(y)\rangle_c.
$$

Translation invariance turns one integral into a volume factor:

$$
\chi=\int d^d x\,G_c(x).
$$

In momentum space this is simply

$$
\chi=\widetilde G_c(0).
$$

This identity is the static fluctuation-response relation.

## Mean-field susceptibility

In mean-field theory, the uniform free-energy density is

$$
f(m)=\frac12 rm^2+\frac{u}{4!}m^4-hm,
\qquad u>0.
$$

The equation of state is

$$
rm+\frac{u}{6}m^3=h.
$$

Above the transition, $r>0$ and $m=0$ at $h=0$. For small $h$,

$$
m=\frac{h}{r}+O(h^3),
$$

so

$$
\chi_+=\frac{1}{r}.
$$

Below the transition, $r<0$ and at $h=0$ the two ordered minima satisfy

$$
m_0^2=-\frac{6r}{u}.
$$

Linearize the equation of state around one minimum:

$$
\left(r+\frac{u}{2}m_0^2\right)\delta m= h.
$$

Since

$$
r+\frac{u}{2}m_0^2=r-3r=-2r,
$$

we get

$$
\chi_- =\frac{1}{-2r}.
$$

Thus mean-field theory gives

$$
\gamma_{\text{MF}}=1,
$$

and the mean-field amplitude ratio is

$$
\frac{C_+}{C_-}=2.
$$

At the critical point $r=0$, the equation of state becomes

$$
h=\frac{u}{6}m^3,
$$

so

$$
m\sim h^{1/3},
\qquad
\delta_{\text{MF}}=3.
$$

## Ornstein-Zernike form

In the Gaussian approximation,

$$
\widetilde G(k)=\frac{1}{k^2+\xi^{-2}}.
$$

The zero-momentum value is

$$
\chi=\widetilde G(0)=\xi^2.
$$

This matches the scaling relation with

$$
\eta=0,
\qquad
\gamma=2\nu.
$$

Since Gaussian or mean-field theory has

$$
\nu_{\text{MF}}=\frac12,
$$

it gives

$$
\gamma_{\text{MF}}=1.
$$

In an interacting critical theory, the small-momentum critical correlator scales as

$$
\widetilde G(k)\sim \frac{1}{k^{2-\eta}}
\quad (t=0),
$$

and away from criticality takes the scaling form

$$
\widetilde G(k;t)=\xi^{2-\eta}\,\Phi_\pm(k\xi).
$$

Setting $k=0$ gives

$$
\chi\sim \xi^{2-\eta}.
$$

## The exponent family

The standard static exponents describe different singular limits near a critical point:

| Exponent | Definition | Meaning |
|---|---|---|
| $\alpha$ | $C\sim |t|^{-\alpha}$ | specific heat singularity |
| $\beta$ | $m\sim (-t)^\beta$ for $t<0$ | order parameter onset |
| $\gamma$ | $\chi\sim |t|^{-\gamma}$ | susceptibility divergence |
| $\delta$ | $m\sim h^{1/\delta}$ at $t=0$ | critical isotherm |
| $\nu$ | $\xi\sim |t|^{-\nu}$ | correlation-length divergence |
| $\eta$ | $G_c(r)\sim r^{-(d-2+\eta)}$ at $t=0$ | anomalous two-point decay |

These exponents are not all independent in ordinary scaling regimes. Common relations include

$$
\gamma=(2-\eta)\nu,
$$

$$
\alpha+2\beta+\gamma=2,
$$

and, when hyperscaling holds,

$$
2-\alpha=d\nu.
$$

Hyperscaling can fail above the upper critical dimension or in the presence of dangerously irrelevant variables. The susceptibility relation $\gamma=(2-\eta)\nu$ is more robust, but it still assumes the usual scaling form for the connected two-point function and a single dominant correlation length.

## Finite-size scaling of susceptibility

In a finite system of linear size $L$, the correlation length cannot grow indefinitely. At criticality, $L$ replaces $\xi$ as the infrared cutoff. Therefore

$$
\chi(t=0,L)\sim L^{2-\eta}
$$

in an ordinary finite-size scaling regime.

More generally,

$$
\chi(t,L)=L^{2-\eta}\,\mathcal X(tL^{1/\nu}),
$$

where $\mathcal X$ is a scaling function. This form is central in simulations: one estimates critical exponents by measuring how the peak or critical value of susceptibility grows with system size.

For lattice spins $s_i$, a common finite-volume susceptibility is

$$
\chi_L=\frac{1}{L^d}\left(\left\langle\left(\sum_i s_i\right)^2\right\rangle
-\left\langle\sum_i s_i\right\rangle^2\right).
$$

This is the lattice version of the integrated connected correlator.

## Generalized susceptibilities

Susceptibility is not limited to magnets. The same logic applies whenever a source couples to an operator.

If a source $J_a$ couples to operators $\mathcal O_a$, then

$$
S\to S-\sum_a J_a\int d^d x\,\mathcal O_a(x),
$$

and the susceptibility matrix is

$$
\chi_{ab}=\int d^d x\,
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle_c.
$$

Examples include compressibility, charge susceptibility, nematic susceptibility, pairing susceptibility, chiral susceptibility, Polyakov-loop susceptibility, and energy-density susceptibility. The critical exponent depends on the scaling dimension of the operator being sourced.

For an operator $\mathcal O$ with scaling dimension $\Delta_\mathcal O$, the integrated correlator at criticality scales in a finite box as

$$
\chi_\mathcal O(L)
\sim \int^{L} d^d x\,\frac{1}{|x|^{2\Delta_\mathcal O}}
\sim L^{d-2\Delta_\mathcal O},
$$

when the integral is infrared divergent. For the order parameter field,

$$
2\Delta_\phi=d-2+\eta,
$$

so this reduces to

$$
\chi\sim L^{2-\eta}.
$$

## Common pitfalls

**Using the full correlator instead of the connected correlator.** Below a symmetry-breaking transition, $\langle\phi(x)\phi(0)\rangle$ contains $\langle\phi\rangle^2$. Susceptibility uses the connected fluctuation.

**Forgetting the volume normalization.** The fluctuation formula is

$$
\chi=\frac{1}{V}(\langle M^2\rangle-\langle M\rangle^2),
$$

not just the variance of $M$ without dividing by volume.

**Confusing $\beta$ the exponent with inverse temperature.** The magnetization exponent $\beta$ and thermodynamic inverse temperature $\beta_{\text{therm}}$ are different objects. This page avoids using $\beta$ for inverse temperature.

**Assuming susceptibility and order parameter diverge together.** The order parameter vanishes as $t\to0^-$ in an ordinary continuous transition, while the susceptibility diverges.

**Applying hyperscaling above the upper critical dimension.** Mean-field exponents hold above $d_c=4$ for short-range scalar $\phi^4$ theory, but hyperscaling fails because of dangerous irrelevance of the quartic coupling.

**Ignoring which operator is being sourced.** Different susceptibilities correspond to different operators and can have different scaling exponents.

## Relations to other pages

[Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/) explains the infrared scale whose growth drives the susceptibility divergence.

[Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) derives the saddle-point exponents $\gamma_{\text{MF}}=1$ and $\delta_{\text{MF}}=3$.

[Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) develops the exponent identities from the scaling form of the singular free energy.

[Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) explains why the exponent $\eta$ is an anomalous-dimension effect.

[Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/) will use $\chi(L)\sim L^{2-\eta}$ as one of the main numerical diagnostics of criticality.

## Research status

The relation between susceptibility, connected two-point functions, and zero-momentum response is established. In ordinary equilibrium critical phenomena with short-range interactions, the exponent $\gamma$ and the scaling relation

$$
\gamma=(2-\eta)\nu
$$

are standard consequences of scaling.

Active work refines susceptibility measurements and interpretations in finite-size Monte Carlo, conformal bootstrap, functional RG, quantum critical matter, gauge theories at finite temperature, disordered systems, glassy systems, nonequilibrium transitions, and experiments where the measured response mixes several scaling operators.

## Exercises

### Exercise 1: Fluctuation-response identity

Starting from

$$
Z[h]=\int\mathcal D\phi\,e^{-S[\phi]+hM[\phi]},
\qquad
M=\int d^d x\,\phi(x),
$$

show that

$$
\frac{\partial}{\partial h}\frac{\langle M\rangle}{V}
=\frac{1}{V}(\langle M^2\rangle-\langle M\rangle^2).
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
\langle M\rangle=\frac{1}{Z}\frac{\partial Z}{\partial h}
=\frac{\partial\log Z}{\partial h}.
$$

Differentiating again,

$$
\frac{\partial\langle M\rangle}{\partial h}
=\frac{\partial^2\log Z}{\partial h^2}
=\frac{1}{Z}\frac{\partial^2Z}{\partial h^2}
-\frac{1}{Z^2}\left(\frac{\partial Z}{\partial h}\right)^2.
$$

Since

$$
\frac{1}{Z}\frac{\partial^2Z}{\partial h^2}=\langle M^2\rangle,
\qquad
\frac{1}{Z}\frac{\partial Z}{\partial h}=\langle M\rangle,
$$

we get

$$
\frac{\partial}{\partial h}\frac{\langle M\rangle}{V}
=\frac{1}{V}(\langle M^2\rangle-\langle M\rangle^2).
$$

</details>

### Exercise 2: Mean-field amplitude ratio

Use

$$
f(m)=\frac12 rm^2+\frac{u}{4!}m^4-hm
$$

to compute $\chi_+$ and $\chi_-$ and show that $C_+/C_-=2$.

<details><summary><strong>Solution</strong></summary>

The equation of state is

$$
rm+\frac{u}{6}m^3=h.
$$

For $r>0$, expand around $m=0$:

$$
r\delta m=h,
\qquad
\chi_+=\frac{\partial m}{\partial h}=\frac{1}{r}.
$$

For $r<0$, the ordered solution obeys

$$
m_0^2=-\frac{6r}{u}.
$$

Linearizing around $m_0$ gives

$$
\left(r+\frac{u}{2}m_0^2\right)\delta m=h.
$$

The coefficient is

$$
r+\frac{u}{2}\left(-\frac{6r}{u}\right)=r-3r=-2r,
$$

so

$$
\chi_- =\frac{1}{-2r}.
$$

Thus if $r\propto t$,

$$
C_+=1,
\qquad
C_-=\frac12,
\qquad
\frac{C_+}{C_-}=2.
$$

</details>

### Exercise 3: Fisher scaling relation

Assume

$$
G_c(r;t)=r^{-(d-2+\eta)}F(r/\xi),
$$

where $F(s)$ decays rapidly for $s\gg1$. Derive $\gamma=(2-\eta)\nu$.

<details><summary><strong>Solution</strong></summary>

The susceptibility scales as

$$
\chi\sim \int d^d x\,G_c(x;t).
$$

Using spherical scaling and cutting the integral off at $r\sim\xi$,

$$
\chi\sim \int^{\xi} dr\,r^{d-1}r^{-(d-2+\eta)}
=\int^{\xi}dr\,r^{1-\eta}
\sim \xi^{2-\eta}.
$$

Since

$$
\xi\sim |t|^{-\nu},
$$

we find

$$
\chi\sim |t|^{-\nu(2-\eta)}.
$$

Comparing with $\chi\sim |t|^{-\gamma}$ gives

$$
\gamma=(2-\eta)\nu.
$$

</details>

### Exercise 4: Finite-size susceptibility

At criticality in a finite box of size $L$, assume the only infrared cutoff is $L$. Show that

$$
\chi_L\sim L^{2-\eta}.
$$

<details><summary><strong>Solution</strong></summary>

At criticality,

$$
G_c(r)\sim r^{-(d-2+\eta)}.
$$

In a finite box, integrate only up to $r\sim L$:

$$
\chi_L\sim\int^L dr\,r^{d-1}r^{-(d-2+\eta)}
=\int^L dr\,r^{1-\eta}
\sim L^{2-\eta}.
$$

This gives the standard finite-size scaling of the critical susceptibility.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), for scaling, correlation functions, and exponent relations from the RG viewpoint.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic treatments of susceptibility, scaling functions, amplitude ratios, and critical exponents.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for the relation between scaling, anomalous dimensions, and correlation functions.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, for response functions, statistical field theory, and RG treatments of criticality.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for an accessible scaling derivation of susceptibility exponents.

## Version history

- 2026-06-18: First polished draft. Added fluctuation-response derivation, mean-field susceptibility, Ornstein–Zernike scaling, Fisher relation, finite-size scaling, and generalized susceptibility matrix.
