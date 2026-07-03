---
title: "Critical Exponents"
description: "Defines the standard critical exponents and derives their relation to RG eigenvalues near a fixed point."
sidebar:
  label: "Critical Exponents"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992."
topics:
  - critical exponents
  - scaling fields
  - correlation length
  - susceptibility
  - order parameter
  - anomalous dimension
canonicalTopics:
  - critical-exponents
  - scaling-fields
  - universality
  - correlation-length-exponent
researchStatus:
  established:
    - "Critical exponents are universal data of RG fixed points and are standard observables in critical phenomena, statistical field theory, and conformal field theory."
  active:
    - "High-precision exponent estimates and exponent spectra remain active in conformal bootstrap, Monte Carlo, high-temperature series, functional RG, large-N, and experiment, especially for strongly coupled and constrained systems."
---

## Summary

**Critical exponents** describe how observables become singular near a continuous phase transition. They turn the qualitative statement “the correlation length becomes large” into quantitative power laws.

For a thermal control parameter

$$
\tau\equiv \frac{T-T_c}{T_c},
$$

the correlation length often behaves as

$$
\xi\sim |\tau|^{-\nu}.
$$

The exponent $\nu$ is one example. Other standard exponents describe the heat capacity, order parameter, susceptibility, critical isotherm, and two-point function:

| Exponent | Observable | Definition near criticality |
|---|---|---|
| $\alpha$ | heat capacity | $C_{\text{sing}}\sim A_\pm |\tau|^{-\alpha}$ |
| $\beta_{\mathrm{mag}}$ | order parameter | $M\sim B(-\tau)^{\beta_{\mathrm{mag}}}$ for $\tau<0$, $h=0$ |
| $\gamma$ | susceptibility | $\chi\sim C_\pm |\tau|^{-\gamma}$ |
| $\delta$ | critical isotherm | $M(0,h)\sim D\,\operatorname{sgn}(h)|h|^{1/\delta}$ |
| $\nu$ | correlation length | $\xi\sim \xi_\pm |\tau|^{-\nu}$ |
| $\eta$ | two-point function | $G_c(r)\sim r^{-(d-2+\eta)}$ at $\tau=h=0$ |
| $\omega$ | correction to scaling | leading irrelevant corrections scale as $\xi^{-\omega}$ |

The subscript in $\beta_{\mathrm{mag}}$ is not standard notation in statistical physics; it is used on this page to avoid confusion with RG beta functions. Most books simply write $\beta$ for the magnetization exponent.

The RG explanation is compact. Near a fixed point, the thermal and magnetic scaling fields have eigenvalues $y_t$ and $y_h$. Then, when ordinary hyperscaling applies,

$$
\nu=\frac{1}{y_t},
\qquad
\alpha=2-\frac{d}{y_t},
\qquad
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\gamma=\frac{2y_h-d}{y_t},
\qquad
\delta=\frac{y_h}{d-y_h},
\qquad
\eta=d+2-2y_h.
$$

Critical exponents are universal, but amplitudes such as $A_\pm$, $B$, $C_\pm$, $D$, and $\xi_\pm$ are usually not. This is one of the cleanest ways to see what the renormalization group means by universality.

:::note[One sentence to remember]
Critical exponents are the eigenvalue data of the fixed point, translated into the power laws measured in nearby systems.
:::

## Prerequisites

You should know [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), and [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/).

It helps to have a statistical-mechanics picture in mind: an Ising-like system with temperature $T$, critical temperature $T_c$, magnetization $M$, and magnetic field $h$. The same formulas also apply, with translated names, to many quantum and relativistic field-theory critical points.

## Core idea

At a continuous phase transition, the long-distance physics is controlled by a fixed point. The microscopic lattice spacing, molecular details, or UV cutoff stop being the main story. The main story becomes the few relevant perturbations away from the fixed point.

Suppose the system is close to criticality. The correlation length is large but finite:

$$
a\ll r\ll \xi,
$$

where $a$ is a microscopic length. In this scaling window, correlation functions nearly look like those of the fixed-point theory. At distances comparable to $\xi$, the relevant perturbation eventually matters and cuts off the power law.

A critical exponent measures how this cutoff scale or a related singular observable depends on the distance from the critical point. For example,

$$
\xi\sim |\tau|^{-\nu}
$$

says that the only important long-distance scale diverges as a power of the tuning parameter $\tau$.

The deep point is that exponents do not depend on most microscopic details. A liquid-vapor critical point, a uniaxial ferromagnet, and a lattice Ising model can share the same exponents because their RG flows approach the same fixed point.

## Setup and conventions

This page uses the conventional statistical-physics variables:

| Symbol | Meaning |
|---|---|
| $d$ | number of Euclidean spacetime dimensions, or spatial dimensions in a classical statistical system |
| $\tau$ | reduced temperature or thermal scaling variable |
| $h$ | field conjugate to the order parameter |
| $M$ | order parameter, such as magnetization |
| $\chi$ | susceptibility, $\chi=\left.\partial M/\partial h\right|_{h=0}$ |
| $G_c(r)$ | connected two-point function of the order parameter |
| $\xi$ | correlation length |

In a quantum critical system with dynamical exponent $z$, the effective scaling dimension of spacetime can involve $d+z$ rather than the number of spatial dimensions alone. This page focuses on the isotropic relativistic or classical Euclidean case. Quantum critical scaling with $z\ne1$ belongs in the statistical and many-body chapters.

The sign convention is

$$
\tau>0
\quad\text{above the critical temperature},
\qquad
\tau<0
\quad\text{in the ordered phase},
$$

for an Ising-like transition. Different physical systems may use a pressure, coupling, mass squared, chemical potential, or disorder strength instead of temperature. The RG object is the thermal scaling field, not the literal thermometer.

## The standard exponents

### Correlation length exponent

The correlation length defines the length scale beyond which the system no longer looks critical. Near the critical point,

$$
\xi(\tau,0)\sim
\begin{cases}
\xi_+\tau^{-\nu}, & \tau>0,\\
\xi_-(-\tau)^{-\nu}, & \tau<0.
\end{cases}
$$

The exponent $\nu$ is universal. The amplitudes $\xi_+$ and $\xi_-$ are usually not, although amplitude ratios such as $\xi_+/\xi_-$ can be universal.

### Heat-capacity exponent

The singular part of the heat capacity behaves as

$$
C_{\text{sing}}\sim
\begin{cases}
A_+\tau^{-\alpha}, & \tau>0,\\
A_-(-\tau)^{-\alpha}, & \tau<0.
\end{cases}
$$

If $\alpha>0$, the heat capacity diverges as a power. If $\alpha=0$, logarithms may appear, as in the two-dimensional Ising model. If $\alpha<0$, the heat capacity can remain finite while still having a nonanalytic cusp.

The word “singular” matters. The full heat capacity can contain analytic background pieces that obscure the critical singularity in data.

### Order-parameter exponent

In the ordered phase at zero external field,

$$
M(\tau,0)\sim B(-\tau)^{\beta_{\mathrm{mag}}},
\qquad \tau<0.
$$

This exponent measures how the order parameter turns on below the transition. In the Ising language, $M$ is magnetization. In a fluid, the analogous order parameter can be the density difference between coexisting phases. In a superfluid, it can be related to the condensate amplitude, though the experimentally clean exponent may involve a related stiffness or density.

### Susceptibility exponent

The susceptibility is the response of the order parameter to its conjugate source:

$$
\chi=\left.\frac{\partial M}{\partial h}\right|_{h=0}.
$$

Near criticality,

$$
\chi(\tau,0)\sim
\begin{cases}
C_+\tau^{-\gamma}, & \tau>0,\\
C_-(-\tau)^{-\gamma}, & \tau<0.
\end{cases}
$$

The susceptibility diverges because a tiny field can align fluctuations over a very large correlation volume. Again, $C_\pm$ are nonuniversal amplitudes, while $\gamma$ is universal inside a universality class.

### Critical-isotherm exponent

At the critical temperature, the order parameter responds nonlinearly to the source:

$$
M(0,h)\sim D\,\operatorname{sgn}(h)|h|^{1/\delta}.
$$

Equivalently,

$$
h\sim M^\delta
$$

on the critical isotherm. Mean-field theory gives $\delta=3$, while interacting critical points usually give different values.

### Anomalous-dimension exponent

At criticality, the connected two-point function of the order parameter has the long-distance form

$$
G_c(r)
=\langle \phi(r)\phi(0)\rangle_c
\sim \frac{1}{r^{d-2+\eta}}.
$$

For a free scalar field in $d$ dimensions, $\eta=0$. Interactions shift the scaling dimension of $\phi$, and the shift is encoded in $\eta$.

If $\Delta_\phi$ is the scaling dimension of the order-parameter field, then

$$
2\Delta_\phi=d-2+\eta,
\qquad
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

This is the direct bridge from critical phenomena notation to CFT notation.

### Correction-to-scaling exponent

The leading irrelevant direction near the fixed point has eigenvalue

$$
y_{\text{irr}}=-\omega,
\qquad \omega>0.
$$

It produces corrections such as

$$
\chi(\tau)
= C_+\tau^{-\gamma}\left(1+a\tau^{\omega\nu}+\cdots\right),
$$

for $\tau>0$, when no other correction dominates. The exponent $\omega$ is often essential in precision Monte Carlo, high-temperature expansions, bootstrap comparisons, and finite-size scaling.

## RG derivation from scaling fields

Near a fixed point, choose scaling fields $u_t$ and $u_h$ associated with the thermal and magnetic perturbations. Under an IR coarse graining by a factor $b>1$,

$$
u_t\longmapsto b^{y_t}u_t,
\qquad
u_h\longmapsto b^{y_h}u_h.
$$

Here $y_t>0$ and $y_h>0$ for an ordinary Ising-like critical point. The singular part of the free-energy density obeys the homogeneity law

$$
f_s(u_t,u_h)=b^{-d}f_s(b^{y_t}u_t,b^{y_h}u_h).
$$

The correlation length transforms as a length:

$$
\xi(u_t,u_h)=b\,\xi(b^{y_t}u_t,b^{y_h}u_h).
$$

Set $u_h=0$ and choose $b=|u_t|^{-1/y_t}$. Then

$$
\xi(u_t,0)
=|u_t|^{-1/y_t}\xi(\pm1,0),
$$

so

$$
\nu=\frac{1}{y_t}.
$$

Next, the order parameter is

$$
M=-\frac{\partial f_s}{\partial h}.
$$

Since $h$ is proportional to the magnetic scaling field $u_h$ near the fixed point, differentiating the homogeneity law gives

$$
M(u_t,u_h)=b^{-d+y_h}M(b^{y_t}u_t,b^{y_h}u_h).
$$

At zero field, again choose $b=|u_t|^{-1/y_t}$. Then

$$
M(u_t,0)\sim |u_t|^{(d-y_h)/y_t},
$$

so

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t}.
$$

A second derivative gives the susceptibility:

$$
\chi(u_t,u_h)=b^{-d+2y_h}\chi(b^{y_t}u_t,b^{y_h}u_h),
$$

and therefore

$$
\gamma=\frac{2y_h-d}{y_t}.
$$

At critical temperature, choose $b=|u_h|^{-1/y_h}$. The order parameter scales as

$$
M(0,u_h)\sim |u_h|^{(d-y_h)/y_h},
$$

so

$$
\frac{1}{\delta}=\frac{d-y_h}{y_h},
\qquad
\delta=\frac{y_h}{d-y_h}.
$$

Finally, the singular free energy at zero field scales as

$$
f_s(u_t,0)\sim |u_t|^{d/y_t}.
$$

Since the heat capacity involves two derivatives with respect to the thermal variable,

$$
C_{\text{sing}}\sim |u_t|^{d/y_t-2},
$$

and hence

$$
\alpha=2-\frac{d}{y_t}.
$$

## The exponent eta and the magnetic eigenvalue

If the source $h$ couples as

$$
\Delta S=-h\int d^d x\,\phi(x),
$$

then the RG eigenvalue of $h$ is

$$
y_h=d-\Delta_\phi.
$$

At the fixed point,

$$
\langle \phi(r)\phi(0)\rangle_c\sim \frac{1}{r^{2\Delta_\phi}}.
$$

Comparing with

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}},
$$

gives

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

Therefore

$$
y_h=d-\Delta_\phi
=\frac{d+2-\eta}{2},
$$

or equivalently

$$
\eta=d+2-2y_h.
$$

This is why a small anomalous dimension can still change several thermodynamic exponents. The source eigenvalue $y_h$ feeds into $\beta_{\mathrm{mag}}$, $\gamma$, and $\delta$.

## Examples

The following values are meant as orientation, not as precision reference data. Dedicated model pages should quote the most carefully maintained numerical estimates.

| Universality class or approximation | $\alpha$ | $\beta_{\mathrm{mag}}$ | $\gamma$ | $\delta$ | $\nu$ | $\eta$ |
|---|---:|---:|---:|---:|---:|---:|
| Mean-field scalar theory | $0$ | $1/2$ | $1$ | $3$ | $1/2$ | $0$ |
| Two-dimensional Ising | $0$ with log | $1/8$ | $7/4$ | $15$ | $1$ | $1/4$ |
| Three-dimensional Ising, representative estimates | $0.110$ | $0.326$ | $1.237$ | $4.79$ | $0.630$ | $0.036$ |

Mean-field exponents are exact for sufficiently high dimension in short-range scalar models, but ordinary hyperscaling fails above the upper critical dimension because of a dangerously irrelevant coupling. This is not a contradiction; it is a warning that the assumptions behind the simplest exponent formulas must be checked.

## What is universal?

Critical exponents are universal within a universality class. The amplitudes in front of the singularities usually are not:

$$
\xi_+,
\xi_-,
A_+,
A_-,
B,
C_+,
C_-,D
\quad\text{are usually nonuniversal}.
$$

However, some combinations of amplitudes can be universal. Examples include amplitude ratios such as

$$
\frac{\xi_+}{\xi_-},
\qquad
\frac{C_+}{C_-},
$$

and more refined combinations that cancel metric factors in the scaling fields. Universality is not “all numbers are the same.” It is the more precise statement that after nonuniversal choices of units and coordinates are removed, the fixed point controls the remaining data.

Critical exponents are among the most robust universal data because they are eigenvalues or operator dimensions. They do not depend on the microscopic lattice, molecular details, or regulator, provided the system flows to the same fixed point.

## Common pitfalls

**Confusing the magnetization exponent with the RG beta function.** The traditional symbol $\beta$ for the order-parameter exponent predates much of the modern RG notation. This page writes $\beta_{\mathrm{mag}}$ to avoid ambiguity.

**Treating amplitudes as universal.** The exponent $\nu$ is universal. The amplitude $\xi_+$ is not usually universal. Ratios can be universal, but only after the relevant nonuniversal normalizations cancel.

**Forgetting analytic backgrounds.** A measured heat capacity or susceptibility can contain analytic pieces in addition to the singular part. The exponent refers to the singular part.

**Assuming every exponent is independent.** Scaling relations reduce the number of independent exponents under appropriate assumptions. For ordinary Ising-like scaling with hyperscaling, two independent exponents determine the familiar six.

**Using hyperscaling above the upper critical dimension.** Above the upper critical dimension, dangerously irrelevant variables can invalidate $2-\alpha=d\nu$ while leaving other scaling relations intact.

**Thinking exponent notation is globally uniform.** Some communities use $t$ for reduced temperature, some use $r$ for the thermal mass, some use $H$ for magnetic field, and some reserve $h$ for a source. Always identify the scaling fields, not only the letters.

## Relations to other pages

[Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) explains where the eigenvalues $y_t$ and $y_h$ come from. [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) derives the algebraic relations among the exponents. Later pages on universality classes will explain why different systems share the same exponent data. Later pages on the Wilson–Fisher fixed point and epsilon expansion will compute exponents perturbatively near four dimensions.

The CFT and Bootstrap volume uses the equivalent language of scaling dimensions, OPE coefficients, and conformal data. The Matter and Statistical Physics volume uses the same exponents for experimental and many-body systems.

## Research status

The conceptual role of critical exponents is settled. They are universal data of RG fixed points and can be derived from scaling dimensions or RG eigenvalues.

Precision values are still an active subject. Different methods — conformal bootstrap, Monte Carlo simulation, high-temperature series, large-N expansions, epsilon expansions, functional RG, exact two-dimensional methods, and experiments — provide complementary access. The interesting frontier is often not the definition of an exponent, but the identification of the fixed point, the treatment of corrections to scaling, and the control of systematic errors.

In systems with disorder, long-range interactions, gauge constraints, anisotropic scaling, nonequilibrium dynamics, or dangerously irrelevant variables, exponent extraction can require extra care. In such cases the simple six-exponent picture is a starting point, not the final taxonomy.

## Exercises

### Exercise 1: Exponents from two RG eigenvalues

Assume the singular free-energy density obeys

$$
f_s(u_t,u_h)=b^{-d}f_s(b^{y_t}u_t,b^{y_h}u_h).
$$

Derive $\nu$, $\beta_{\mathrm{mag}}$, $\gamma$, $\delta$, and $\alpha$ in terms of $y_t$, $y_h$, and $d$.

<details><summary><strong>Solution</strong></summary>

The correlation length obeys

$$
\xi(u_t,u_h)=b\,\xi(b^{y_t}u_t,b^{y_h}u_h).
$$

At $u_h=0$, choose $b=|u_t|^{-1/y_t}$ to get

$$
\xi\sim |u_t|^{-1/y_t},
$$

so $\nu=1/y_t$.

The order parameter is one derivative of $f_s$ with respect to $u_h$, so

$$
M(u_t,u_h)=b^{-d+y_h}M(b^{y_t}u_t,b^{y_h}u_h).
$$

At $u_h=0$, choosing $b=|u_t|^{-1/y_t}$ gives

$$
M\sim |u_t|^{(d-y_h)/y_t},
$$

so

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t}.
$$

The susceptibility is a second derivative, so

$$
\chi(u_t,u_h)=b^{-d+2y_h}\chi(b^{y_t}u_t,b^{y_h}u_h).
$$

Thus

$$
\gamma=\frac{2y_h-d}{y_t}.
$$

At $u_t=0$, choose $b=|u_h|^{-1/y_h}$. Then

$$
M\sim |u_h|^{(d-y_h)/y_h},
$$

so

$$
\frac1\delta=\frac{d-y_h}{y_h},
\qquad
\delta=\frac{y_h}{d-y_h}.
$$

Finally,

$$
f_s(u_t,0)\sim |u_t|^{d/y_t}.
$$

Two thermal derivatives give

$$
C_{\text{sing}}\sim |u_t|^{d/y_t-2},
$$

so

$$
\alpha=2-\frac{d}{y_t}.
$$

</details>

### Exercise 2: Eta and the scaling dimension of the order parameter

The source $h$ couples to the order parameter by $-h\int d^d x\,\phi(x)$. Show that

$$
y_h=d-\Delta_\phi.
$$

Then use $G_c(r)\sim r^{-(d-2+\eta)}$ to derive $y_h=(d+2-\eta)/2$.

<details><summary><strong>Solution</strong></summary>

The perturbation

$$
h\int d^d x\,\phi(x)
$$

must be dimensionless. Under a scale transformation, the integral of $\phi$ has scaling dimension

$$
\Delta_\phi-d.
$$

Therefore the source has RG eigenvalue

$$
y_h=d-\Delta_\phi.
$$

At the fixed point,

$$
G_c(r)\sim \frac{1}{r^{2\Delta_\phi}}.
$$

Comparing this with

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}}
$$

gives

$$
2\Delta_\phi=d-2+\eta,
\qquad
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

Hence

$$
y_h=d-\Delta_\phi
=d-\frac{d-2+\eta}{2}
=\frac{d+2-\eta}{2}.
$$

</details>

### Exercise 3: Mean-field exponents from Landau theory

Consider the Landau free-energy density

$$
f(M)=\frac12 a\tau M^2+\frac14 uM^4-hM,
\qquad a>0,
\qquad u>0.
$$

Find $\beta_{\mathrm{mag}}$, $\gamma$, and $\delta$.

<details><summary><strong>Solution</strong></summary>

The equation of state is

$$
\frac{\partial f}{\partial M}=a\tau M+uM^3-h=0.
$$

At $h=0$ and $\tau<0$, the nonzero minimum satisfies

$$
M^2=-\frac{a\tau}{u},
$$

so

$$
M\sim (-\tau)^{1/2}.
$$

Thus $\beta_{\mathrm{mag}}=1/2$.

For $\tau>0$ and small $h$, the cubic term is negligible and

$$
M\simeq \frac{h}{a\tau}.
$$

Therefore

$$
\chi=\frac{\partial M}{\partial h}\simeq \frac{1}{a\tau},
$$

so $\gamma=1$.

At $\tau=0$, the equation of state becomes

$$
u M^3=h,
$$

so

$$
M\sim h^{1/3}.
$$

Therefore $\delta=3$.

</details>

## References

- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974), for the Wilsonian RG origin of critical exponent calculations.
- Sidney Coleman, “Dilatations,” in *Aspects of Symmetry*, for scale transformations, anomalous dimensions, and Callan–Symanzik reasoning.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, critical phenomena, and relations among fixed points and exponents.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for a comprehensive field-theoretic treatment of critical exponents and renormalization.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact statistical-physics treatment of scaling and exponent relations.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for physical explanations and examples.

## Version history

- 2026-06-17: First polished draft. Defined the standard exponents, fixed notation for $\beta_{\mathrm{mag}}$, derived exponent formulas from RG eigenvalues, and added exercises with solutions.
