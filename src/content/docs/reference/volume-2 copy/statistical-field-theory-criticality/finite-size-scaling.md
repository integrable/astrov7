---
title: "Finite-Size Scaling"
description: "How finite systems round critical singularities, how system size acts as an RG scale, and how finite-size scaling extracts critical exponents from simulations and experiments."
sidebar:
  label: "Finite-Size Scaling"
  order: 9
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Altland and Simons 2023, ch. 6."
topics:
  - finite-size scaling
  - critical phenomena
  - RG scaling
  - critical exponents
  - data collapse
canonicalTopics:
  - finite-size-scaling
  - critical-exponents
  - universality
researchStatus:
  established:
    - "Finite-size scaling is the standard RG framework for extracting critical behavior from finite systems, lattice simulations, and finite experimental samples."
  active:
    - "Precision work requires careful treatment of irrelevant operators, boundary conditions, aspect ratios, improved actions, logarithmic corrections, and non-power-law transitions such as the KT transition."
---

## Summary

A true second-order phase transition requires an infinite system. In a finite box of linear size $L$, the correlation length cannot grow without bound, thermodynamic singularities are rounded, and the critical point is replaced by smooth finite-size crossovers.

Finite-size scaling turns this inconvenience into a tool. Near a critical point, the system size $L$ is an infrared cutoff. The RG cannot run past the scale $L$, so the singular part of the physics is controlled by the dimensionless ratios

$$
tL^{1/\nu},
\qquad
hL^{y_h},
\qquad
L^{-\omega},
\qquad
\frac{\xi}{L},
$$

where $t$ is the reduced temperature, $h$ is the field conjugate to the order parameter, $\nu$ is the correlation-length exponent, $y_h$ is the magnetic scaling exponent, and $\omega>0$ is the leading irrelevant correction exponent.

The central finite-size scaling ansatz is

$$
f_s(t,h,L)
=
L^{-d}\mathcal F\!\left(tL^{1/\nu},hL^{y_h},u_1L^{-\omega_1},u_2L^{-\omega_2},\ldots\right),
$$

where $f_s$ is the singular free-energy density and $u_i$ are irrelevant scaling fields. Differentiating this one formula gives the finite-size scaling of the order parameter, susceptibility, specific heat, Binder cumulants, and many other observables.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![Finite-size scaling turns rounded finite-volume peaks into a universal data collapse after rescaling the temperature variable by L to the one over nu](/figures/renormalization-rg-eft/finite-size-scaling-collapse.svg)

<figcaption>

Finite size rounds a critical singularity. Different system sizes show different peak heights and widths, but near a single critical fixed point the same data collapse when plotted against the scaling variable $tL^{1/\nu}$, up to corrections from irrelevant operators, boundary conditions, and aspect ratio.

</figcaption>
</figure>

## Prerequisites

You should know what a correlation length is, how critical exponents are defined, and how the RG linearizes near a fixed point. Useful earlier pages are [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/), [Susceptibility and Critical Exponents](/renormalization-rg-eft/statistical-field-theory-criticality/susceptibility-and-critical-exponents/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), and [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/).

Throughout this page, $d$ denotes the number of Euclidean spatial dimensions of the statistical system. We use $L$ for the finite linear size and reserve $\Lambda$ for ultraviolet cutoffs.

## Core idea

In the thermodynamic limit, a continuous transition has

$$
\xi(t)\sim |t|^{-\nu}.
$$

In a finite system, the correlation length cannot grow much larger than the system size. More precisely, the finite-volume correlation length $\xi_L$ is controlled by

$$
\xi_L(t)
=
L\,\mathcal X(tL^{1/\nu})
$$

near the critical point, up to corrections. This formula contains two regimes.

If $L\gg \xi_\infty(t)$, the system does not know it is finite and one recovers thermodynamic-limit behavior:

$$
\xi_L(t)\approx \xi_\infty(t).
$$

If $\xi_\infty(t)\gg L$, the finite box cuts off the critical fluctuations and

$$
\xi_L(t)\sim L.
$$

The crossover occurs when

$$
L\sim \xi_\infty(t),
\qquad
|t|\sim L^{-1/\nu}.
$$

This is why peaks sharpen as $L$ increases. The critical window shrinks like $L^{-1/\nu}$.

## RG derivation of the scaling form

Let $f_s(t,h,L^{-1},\{u_i\})$ be the singular part of the free-energy density near a fixed point. The relevant scaling fields are $t$ and $h$, while $u_i$ denote irrelevant scaling fields. Under an RG transformation with scale factor $b>1$,

$$
f_s(t,h,L^{-1},\{u_i\})
=
b^{-d}
 f_s(t b^{y_t},h b^{y_h},bL^{-1},\{u_i b^{y_i}\}),
$$

where

$$
y_t=\frac1\nu,
\qquad
y_i<0.
$$

Choosing $b=L$, with $L$ measured in microscopic units, gives

$$
f_s(t,h,L)
=
L^{-d}\mathcal F(tL^{y_t},hL^{y_h},\{u_iL^{y_i}\}).
$$

Writing the leading irrelevant exponent as

$$
\omega=-y_1>0,
$$

gives the practical form

$$
f_s(t,h,L)
=
L^{-d}\left[\mathcal F_0(tL^{1/\nu},hL^{y_h})
+L^{-\omega}\mathcal F_1(tL^{1/\nu},hL^{y_h})+\cdots\right].
$$

The first term is the universal finite-size scaling form once boundary conditions, shape, and normalization conventions are fixed. The $L^{-\omega}$ terms are corrections to scaling.

:::note[What is universal?]
Critical exponents and many scaling functions are universal after the normalization of scaling variables is fixed. Raw amplitudes, the precise definition of $L$, boundary-condition effects, and microscopic corrections are not universal.
:::

## Order parameter, susceptibility, and specific heat

Let $m$ be the order parameter density conjugate to $h$:

$$
m(t,h,L)=-\frac{\partial f_s}{\partial h}.
$$

At $h=0$,

$$
m(t,L)
=
L^{-d+y_h}\mathcal M(tL^{1/\nu})
=
L^{-\beta/\nu}\mathcal M(tL^{1/\nu}),
$$

where

$$
\frac{\beta}{\nu}=d-y_h.
$$

At criticality,

$$
m(0,L)\sim L^{-\beta/\nu}.
$$

The susceptibility is

$$
\chi(t,L)=\frac{\partial m}{\partial h}\bigg|_{h=0}
\sim
L^{-d+2y_h}\mathcal X(tL^{1/\nu}).
$$

Using

$$
2y_h-d=\frac{\gamma}{\nu}=2-\eta,
$$

we get

$$
\chi(0,L)\sim L^{\gamma/\nu}=L^{2-\eta}.
$$

For the specific heat,

$$
C(t,L)\sim \frac{\partial^2 f_s}{\partial t^2}
\sim
L^{-d+2/\nu}\mathcal C(tL^{1/\nu}).
$$

If hyperscaling holds, $\alpha=2-d\nu$, so

$$
C(0,L)\sim L^{\alpha/\nu}.
$$

When $\alpha=0$, logarithms can replace simple powers. The two-dimensional Ising model is the classic warning sign: blindly fitting $C(0,L)$ to a power law can manufacture a fake exponent.

## Dimensionless quantities and crossing methods

Dimensionless observables are especially useful because their leading finite-size scaling form is

$$
R(t,L)=\mathcal R(tL^{1/\nu})+L^{-\omega}\mathcal R_1(tL^{1/\nu})+\cdots.
$$

At $t=0$, the leading term is independent of $L$:

$$
R(0,L)=\mathcal R(0)+O(L^{-\omega}).
$$

Examples include:

| Quantity | Meaning |
|---|---|
| $\xi_L/L$ | finite-volume correlation length in units of system size |
| Binder cumulant | dimensionless ratio of moments of the order parameter |
| wrapping probability | dimensionless percolation or cluster observable |
| helicity-stiffness ratios | useful in compact-boson and superfluid transitions |

For two sizes $L$ and $sL$, the crossing point $t_\times(L)$ of a dimensionless quantity tends to the critical point:

$$
t_\times(L)\to 0
\qquad
\text{as}\qquad
L\to\infty.
$$

With leading irrelevant corrections, the drift often has the form

$$
t_\times(L)
\sim
L^{-1/\nu-\omega},
$$

assuming the scaling function has a nonzero slope at the crossing. In practice, crossing drifts are one of the cleanest ways to locate critical points, but they are also one of the easiest places to underestimate systematic errors.

## Data collapse

Suppose an observable $O$ has thermodynamic critical behavior

$$
O(t,\infty)\sim |t|^{-\rho}.
$$

The finite-size scaling form is usually written

$$
O(t,L)=L^{\rho/\nu}\mathcal O(tL^{1/\nu})
$$

for a diverging observable such as $\chi$, and

$$
O(t,L)=L^{-\rho/\nu}\mathcal O(tL^{1/\nu})
$$

for an observable that vanishes at criticality, such as an order parameter with exponent $\beta$.

A data-collapse plot rescales the axes so that different sizes fall on a common curve. For susceptibility, one plots

$$
L^{-\gamma/\nu}\chi(t,L)
\quad\text{versus}\quad
 tL^{1/\nu}.
$$

For the order parameter, one plots

$$
L^{\beta/\nu}m(t,L)
\quad\text{versus}\quad
 tL^{1/\nu}.
$$

A good collapse is useful evidence, not a proof. Many nearby exponents can produce visually convincing collapse over a limited range. Trustworthy finite-size analysis reports the size range, correction terms, goodness of fit, covariance treatment, boundary conditions, and the stability of the result under removing small sizes.

## Pseudocritical points

In a finite system, peaks and rapid crossovers occur near size-dependent pseudocritical points. If $t_L$ denotes the location of a susceptibility peak, then finite-size scaling gives

$$
t_L\sim L^{-1/\nu}
$$

at leading order, with corrections such as

$$
t_L=aL^{-1/\nu}\left(1+bL^{-\omega}+\cdots\right).
$$

A peak height then scales as

$$
\chi_{\max}(L)\sim L^{\gamma/\nu}
\left(1+cL^{-\omega}+\cdots\right).
$$

These relations are often more stable than trying to fit the full scaling curve, but they lose information away from the peak.

## Boundary conditions and aspect ratio

Finite-size scaling is not just about the number $L$. It also depends on the finite geometry. A cubic box with periodic boundary conditions, a slab with open boundaries, and a cylinder with one compact direction are not interchangeable.

The scaling function knows about the dimensionless shape data:

$$
f_s(t,h,L_1,\ldots,L_d)
=
L^{-d}\mathcal F\!\left(tL^{1/\nu},hL^{y_h},\frac{L_2}{L_1},\ldots,\text{boundary conditions}\right),
$$

where $L$ is a chosen reference length. The exponents are universal; the scaling functions and finite-size amplitudes depend on shape and boundary universality class.

This is not a nuisance detail. Boundary conditions can change finite-size spectra, surface critical behavior, Binder-cumulant crossing values, and Casimir amplitudes. State them.

## Finite temperature as finite size

A quantum system at temperature $T$ has Euclidean time circle length

$$
\beta_T=\frac1T.
$$

Thus finite temperature can act like finite size in the Euclidean time direction. Near a quantum critical point with dynamical exponent $z$, the correlation time scales as

$$
\xi_\tau\sim \xi^z.
$$

The quantum finite-size scaling variables are then

$$
tL^{1/\nu},
\qquad
T L^z,
$$

or, equivalently,

$$
\frac{L_\tau}{L^z},
\qquad
L_\tau\sim \frac1T.
$$

Relativistic quantum critical points have $z=1$, so space and Euclidean time scale in the same way once velocities are normalized. Nonrelativistic critical points generally do not.

## Corrections to scaling

Real data are never only the leading scaling form. Corrections come from:

| Source | Typical effect |
|---|---|
| irrelevant operators | powers $L^{-\omega}$ |
| analytic background terms | additive nonsingular contributions |
| boundaries | surface powers and boundary scaling functions |
| anisotropy | aspect-ratio and metric corrections |
| marginally irrelevant operators | logarithmic corrections |
| too-small systems | no clean scaling regime yet |

A common practical fitting form for susceptibility is

$$
\chi(t,L)
=
L^{\gamma/\nu}
\left[
\mathcal X_0(tL^{1/\nu})
+L^{-\omega}\mathcal X_1(tL^{1/\nu})
+\cdots
\right]
+
\chi_{\text{reg}}(t),
$$

where $\chi_{\text{reg}}$ is a nonsingular background. If $\gamma/\nu$ is large, the background is often harmless. If the singular exponent is small or negative, the background can dominate finite data.

## Worked example: susceptibility from the correlator

At criticality, the connected two-point function behaves as

$$
G(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

The finite-volume susceptibility is approximately the integral of $G(r)$ up to the largest available distance $L$:

$$
\chi_L
\sim
\int_a^L d^dr\,G(r).
$$

Using $d^dr\sim r^{d-1}dr$,

$$
\chi_L
\sim
\int_a^L dr\,r^{d-1}r^{-(d-2+\eta)}
=
\int_a^L dr\,r^{1-\eta}.
$$

For $\eta<2$,

$$
\chi_L\sim L^{2-\eta}.
$$

Thus

$$
\frac{\gamma}{\nu}=2-\eta,
$$

which is the finite-size version of the Fisher scaling relation. This derivation is deliberately crude, but it captures the RG idea: at criticality, the only infrared cutoff is $L$.

## Common pitfalls

**Treating rounded peaks as true singularities.** In finite volume, all partition functions of finite systems are analytic functions of $t$ and $h$. Critical singularities emerge only as $L\to\infty$.

**Ignoring correction exponents.** If the smallest simulated sizes are included without $L^{-\omega}$ terms, the fit may look precise while being biased.

**Using the wrong universality class.** Finite-size scaling cannot rescue an incorrect symmetry, dimension, conservation law, disorder type, interaction range, or boundary universality class.

**Forgetting aspect ratio.** A $64\times 64$ square and a $16\times 256$ strip are not equivalent finite-size approximations to the same scaling function.

**Overtrusting data collapse by eye.** A pretty collapse is an invitation to quantify, not the end of analysis.

**Applying ordinary power-law finite-size scaling to KT transitions without logarithms.** The KT transition has an essential singularity and marginal flow. It needs its own scaling treatment.

## Relations to other pages

Finite-size scaling is the practical bridge between RG theory and finite data. It uses [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/) and [Susceptibility and Critical Exponents](/renormalization-rg-eft/statistical-field-theory-criticality/susceptibility-and-critical-exponents/), depends conceptually on [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), and becomes more subtle in [KT Transition Preview](/renormalization-rg-eft/statistical-field-theory-criticality/kt-transition-preview/). It also foreshadows finite-volume methods in lattice QFT and conformal finite-size spectra.

## Research status

The basic finite-size scaling framework is settled. Active work is mostly not about whether finite-size scaling is true; it is about precision, corrections, universality of amplitude ratios, improved lattice actions, conformal finite-size spectra, disordered systems, quantum critical scaling, nonequilibrium scaling, and reliable uncertainty estimates in numerical studies.

## Exercises

### Exercise 1: Derive the finite-size scaling form

Assume

$$
f_s(t,h,L^{-1})
=
b^{-d}f_s(tb^{y_t},hb^{y_h},bL^{-1}).
$$

Choose $b=L$ and derive the finite-size scaling form for $f_s$.

<details><summary><strong>Solution</strong></summary>

Choosing $b=L$, with $L$ measured in microscopic units, gives

$$
f_s(t,h,L^{-1})
=
L^{-d}f_s(tL^{y_t},hL^{y_h},1).
$$

Define

$$
\mathcal F(x,y)=f_s(x,y,1).
$$

Then

$$
f_s(t,h,L)
=
L^{-d}\mathcal F(tL^{y_t},hL^{y_h}).
$$

Since $y_t=1/\nu$, this is

$$
f_s(t,h,L)
=
L^{-d}\mathcal F(tL^{1/\nu},hL^{y_h}).
$$

</details>

### Exercise 2: Order parameter and susceptibility at criticality

Starting from

$$
f_s(t,h,L)=L^{-d}\mathcal F(tL^{1/\nu},hL^{y_h}),
$$

show that

$$
m(0,L)\sim L^{-\beta/\nu},
\qquad
\chi(0,L)\sim L^{\gamma/\nu}.
$$

<details><summary><strong>Solution</strong></summary>

The order parameter is

$$
m=-\frac{\partial f_s}{\partial h}
= -L^{-d}L^{y_h}\mathcal F_h(tL^{1/\nu},hL^{y_h}).
$$

At $t=h=0$,

$$
m(0,L)\sim L^{-d+y_h}.
$$

Using $\beta/\nu=d-y_h$, this becomes

$$
m(0,L)\sim L^{-\beta/\nu}.
$$

The susceptibility is

$$
\chi=\frac{\partial m}{\partial h}
\sim L^{-d+2y_h}.
$$

Using $\gamma/\nu=2y_h-d$, we get

$$
\chi(0,L)\sim L^{\gamma/\nu}.
$$

</details>

### Exercise 3: Binder crossing drift

Let a dimensionless observable have the expansion

$$
R(t,L)=R_*+a\,tL^{1/\nu}+bL^{-\omega}+\cdots.
$$

Estimate the crossing point $t_\times(L)$ for sizes $L$ and $sL$.

<details><summary><strong>Solution</strong></summary>

At the crossing,

$$
R(t_\times,L)=R(t_\times,sL).
$$

Using the expansion,

$$
a t_\times L^{1/\nu}+bL^{-\omega}
=
a t_\times (sL)^{1/\nu}+b(sL)^{-\omega}.
$$

Rearrange:

$$
a t_\times L^{1/\nu}(1-s^{1/\nu})
=
bL^{-\omega}(s^{-\omega}-1).
$$

Thus

$$
t_\times(L)
=
\frac{b(s^{-\omega}-1)}{a(1-s^{1/\nu})}
L^{-1/\nu-\omega}.
$$

The crossing approaches the critical point faster than $L^{-1/\nu}$ when this leading correction structure applies.

</details>

### Exercise 4: Why finite systems are analytic

Explain why a finite classical spin system cannot have a true thermodynamic singularity, even if it is very large.

<details><summary><strong>Solution</strong></summary>

For a finite system with finitely many degrees of freedom and finite couplings, the partition function is a finite sum or finite-dimensional integral of smooth functions of the parameters. For example, an Ising model with $N$ spins has

$$
Z_N=\sum_{\{s_i=\pm1\}}e^{-\beta H(\{s_i\})},
$$

which is a finite sum of exponentials. Therefore $Z_N$ and the finite-volume free energy are analytic except at isolated zeros in complexified parameter space, not at real positive temperature in ordinary finite systems. Nonanalytic behavior appears only after taking the thermodynamic limit $N\to\infty$.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on finite-size effects, critical exponents, and RG.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the renormalization-group discussion of critical phenomena.
- Michael E. Fisher, "The Theory of Equilibrium Critical Phenomena," *Reports on Progress in Physics* **30** (1967) 615–730.
- Ferdinand J. Wegner, "Corrections to Scaling Laws," *Physical Review B* **5** (1972) 4529–4536.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact treatment of finite-size scaling and scaling functions.

## Version history

- 2026-06-19: First polished draft. Added RG derivation, observable scaling laws, crossing methods, correction terms, finite-temperature analogy, and exercises.
