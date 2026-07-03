---
title: "Functional Renormalization Group Preview"
description: "Introduces the effective-average-action formulation of functional RG, the Wetterich equation, regulator choices, truncations, and its relation to Wilsonian exact RG."
sidebar:
  label: "Functional RG Preview"
  order: 9
level: Graduate
status: "Polished draft"
source: "Wetterich 1993; Morris 1994; Berges, Tetradis, and Wetterich 2002; Delamotte 2012; Zinn-Justin 2021; Wilson and Kogut 1974; Burgess 2020 chs. 2–3."
topics:
  - functional renormalization group
  - effective average action
  - Wetterich equation
  - nonperturbative RG
  - derivative expansion
  - local potential approximation
canonicalTopics:
  - functional-renormalization-group
  - effective-average-action
  - wetterich-equation
  - frg-truncations
  - local-potential-approximation
researchStatus:
  established:
    - "The Wetterich equation is an exact functional flow equation for the effective average action, interpolating between a microscopic action and the full 1PI effective action as an infrared regulator is removed."
  active:
    - "Applications to gauge theories, gravity, real-time dynamics, finite density, strongly correlated matter, and quantitative critical phenomena depend on regulator choices and truncations whose systematic control remains an active subject."
---

## Summary

The **functional renormalization group** (FRG) is a family of exact RG methods that follow a scale-dependent functional rather than a finite list of couplings. The most common modern version uses the **effective average action** $\Gamma_k[\varphi]$, a scale-dependent analogue of the one-particle-irreducible effective action.

Its central equation is the Wetterich equation:

$$
\partial_t\Gamma_k[\varphi]
=
\frac12\operatorname{Tr}\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}
\partial_t R_k
\right],
\qquad
 t=\log k.
$$

Here $R_k$ is an infrared regulator that suppresses modes with momenta $p^2\lesssim k^2$, and $\Gamma_k^{(2)}$ is the second functional derivative of $\Gamma_k$. The equation has a one-loop shape, but it is not an ordinary one-loop approximation: the inverse propagator contains the full running functional $\Gamma_k^{(2)}$.

As $k$ is lowered, $\Gamma_k$ interpolates schematically as

$$
\Gamma_{k\simeq \Lambda}\approx S_\Lambda,
\qquad
\Gamma_{k\to0}=\Gamma,
$$

where $S_\Lambda$ is a microscopic or Wilsonian input action and $\Gamma$ is the full quantum effective action.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Functional RG flow from a UV action through the Wetterich equation and infrared regulator to the full effective action and observables](/figures/renormalization-rg-eft/functional-rg-flow-equation.svg)

<figcaption>

The effective-average-action flow starts near a microscopic action at $k\simeq\Lambda_0$, evolves by the Wetterich equation with an infrared regulator $R_k$, and reaches the ordinary 1PI effective action as $k\to0$. The exact equation is functional; observables require a projection or truncation in practice.

</figcaption>
</figure>

:::note[Preview page]
This page introduces the effective-average-action formalism and its interpretation. It does not attempt a full technical review of FRG for gauge theories, fermions, gravity, or numerical critical-exponent calculations. Those belong in later advanced RG pages and model calculation pages.
:::

## Prerequisites

You should know [Exact Renormalization Group](/renormalization-rg-eft/wilsonian-renormalization/exact-renormalization-group/), [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

It also helps to know the 1PI effective action from perturbative QFT: the ordinary effective action $\Gamma[\varphi]$ is the Legendre transform of the connected generating functional and generates one-particle-irreducible vertices. FRG modifies this object by adding a scale-dependent infrared regulator.

## Core idea

Wilsonian RG integrates out high-momentum modes and changes a cutoff action $S_\Lambda$. The effective-average-action version of FRG takes a complementary route. It keeps a path integral over all modes but adds a regulator that prevents low-momentum modes from fluctuating. Then it gradually removes that regulator.

The scale $k$ is not a physical mass. It is a sliding infrared resolution scale. For momenta much smaller than $k$, fluctuations are suppressed. For momenta much larger than $k$, fluctuations are essentially included. As $k$ decreases, more and more modes are allowed to fluctuate.

The flow is therefore

$$
\text{microscopic action}
\longrightarrow
\Gamma_k
\longrightarrow
\text{full quantum effective action}.
$$

This is why FRG is especially useful for questions phrased in terms of order parameters and effective potentials. At intermediate $k$, $\Gamma_k$ is already a 1PI-like object, so phases, symmetry breaking, and running effective potentials can be described directly.

The practical discipline is the same as for every exact RG method:

$$
\text{exact functional equation}
+
\text{controlled truncation}
\longrightarrow
\text{physical prediction}.
$$

## Setup and conventions

Work in Euclidean signature with a real scalar field. Add a quadratic regulator term

$$
\Delta S_k[\phi]
=
\frac12\int_p \phi(p)R_k(p)\phi(-p).
$$

The regulator $R_k(p)$ should satisfy the qualitative conditions

$$
R_k(p)\sim k^2\quad\text{for }p^2\ll k^2,
$$

$$
R_k(p)\to0\quad\text{for }p^2\gg k^2,
$$

and

$$
R_{k\to0}(p)=0.
$$

The regulated generating functional is

$$
Z_k[J]
=
\int\mathcal D\phi\,
\exp\left[-S[\phi]-\Delta S_k[\phi]+\int d^d x\,J\phi\right].
$$

Define

$$
W_k[J]=\log Z_k[J]
$$

and the average field

$$
\varphi(x)=\frac{\delta W_k[J]}{\delta J(x)}.
$$

The effective average action is a modified Legendre transform:

$$
\Gamma_k[\varphi]
=
\int d^d x\,J\varphi-W_k[J]-\Delta S_k[\varphi],
$$

where $J$ is eliminated in favor of $\varphi$. The subtraction of $\Delta S_k[\varphi]$ is essential. Without it, the regulator would remain inside the definition in a way that obscures the interpolation to the ordinary effective action.

## The Wetterich equation

The exact flow equation is

$$
\partial_t\Gamma_k[\varphi]
=
\frac12\operatorname{Tr}\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}
\partial_t R_k
\right],
\qquad
 t=\log k.
$$

The notation means:

| Symbol | Meaning |
|---|---|
| $\Gamma_k^{(2)}$ | second functional derivative of $\Gamma_k$ with respect to $\varphi$ |
| $R_k$ | infrared regulator kernel |
| $(\Gamma_k^{(2)}+R_k)^{-1}$ | full regulated propagator at scale $k$ |
| $\partial_tR_k$ | insertion restricting the trace to modes near $p^2\sim k^2$ |
| $\operatorname{Tr}$ | momentum, coordinate, and internal-index trace |

For fermions and ghosts, the trace becomes a supertrace with minus signs for Grassmann fields:

$$
\partial_t\Gamma_k
=\frac12\operatorname{STr}\left[
\left(\Gamma_k^{(2)}+R_k\right)^{-1}\partial_tR_k
\right].
$$

The equation is ultraviolet and infrared finite under suitable regulator choices. The factor $\partial_t R_k$ localizes the flow near the running scale $k$, while $R_k$ suppresses dangerous low-momentum modes.

## Why the equation has one-loop form

The Wetterich equation resembles a one-loop determinant because it contains a trace of a propagator times a scale derivative of the regulator. A mnemonic is

$$
\partial_t\Gamma_k
\sim
\frac12\partial_t\operatorname{Tr}\log(\Gamma_k^{(2)}+R_k),
$$

but this mnemonic is not the derivation. In the actual equation, $\Gamma_k^{(2)}$ itself depends on $k$ and on the full field configuration. The right-hand side is a nonlinear functional of $\Gamma_k$.

The one-loop form is useful because it makes the shell interpretation visible: the trace sums fluctuations with a full, field-dependent, regulated propagator, and $\partial_tR_k$ selects the modes whose suppression changes as $k$ changes.

Thus the slogan is

$$
\text{FRG is one-loop in form and exact in content.}
$$

Of course, once we approximate $\Gamma_k$, exactness is gone. Then the one-loop shape is only part of an approximation scheme.

## Boundary conditions and interpolation

At high scale, if $R_k$ is large enough to suppress nearly all fluctuations, the path integral is dominated by the classical field configuration. Then

$$
\Gamma_{k=\Lambda}\approx S_\Lambda
$$

up to regulator-dependent details and possible counterterms. This provides the initial condition for the flow.

At $k=0$, the regulator vanishes:

$$
R_0=0.
$$

Then the modified Legendre transform becomes the ordinary Legendre transform and

$$
\Gamma_{k=0}=\Gamma,
$$

where $\Gamma$ is the full 1PI effective action.

The FRG flow therefore gives a formal path from microscopic input to the full effective action:

$$
S_\Lambda
\longrightarrow
\Gamma_\Lambda
\longrightarrow
\Gamma_k
\longrightarrow
\Gamma_0.
$$

In practice, one rarely knows the whole functional $\Gamma_k$. The value of FRG is that useful approximations can preserve nonperturbative structures such as convexity of the effective potential, running order parameters, decoupling of massive modes, and fixed-point scaling.

## Regulator choices

The regulator is part of the RG scheme. A common parametrization is

$$
R_k(p)=Z_k k^2 r(p^2/k^2),
$$

where $r(y)$ is a dimensionless shape function. It should be large enough near $y=0$ to suppress infrared modes and small enough at large $y$ to leave high-momentum modes unaffected.

Examples used in the literature include exponential regulators, compactly supported smooth regulators, and optimized regulators. The exact flow should not depend on this choice. Truncated flows do depend on it, and that dependence is often used as an error diagnostic.

A good regulator should:

| Requirement | Reason |
|---|---|
| suppress $p^2\ll k^2$ modes | makes $\Gamma_k$ an effective action at resolution $k$ |
| vanish for $p^2\gg k^2$ | avoids distorting already-integrated high modes |
| vanish as $k\to0$ | recovers the physical effective action |
| be compatible with symmetries as much as possible | reduces spurious symmetry breaking |
| allow stable numerical integrals | makes truncations practical |

No regulator is sacred. The regulator is a tool, not a new physical force.

## Local potential approximation

The simplest useful truncation for a scalar order parameter is the derivative expansion

$$
\Gamma_k[\varphi]
=
\int d^d x\left[
U_k(\varphi)
+\frac12 Z_k(\varphi)(\partial\varphi)^2
+O(\partial^4)
\right].
$$

The **local potential approximation** keeps

$$
\Gamma_k[\varphi]
\approx
\int d^d x\left[
U_k(\varphi)
+\frac12 Z_k(\partial\varphi)^2
\right],
$$

often with $Z_k$ constant or even $Z_k=1$ at the crudest level.

For a constant background field, the Wetterich equation reduces schematically to

$$
\partial_t U_k(\varphi)
=
\frac12\int_p
\frac{\partial_t R_k(p)}{Z_k p^2+R_k(p)+U_k''(\varphi)}.
$$

This is already nonperturbative in the potential because the denominator contains $U_k''(\varphi)$ rather than a fixed mass. Expanding the denominator in powers of couplings recovers perturbative loop terms, but keeping it unexpanded can describe threshold effects and qualitative phase structure beyond naive perturbation theory.

## Dimensionless variables and fixed points

To study fixed points, switch to dimensionless variables. For a scalar with wavefunction factor $Z_k$, define

$$
\tilde\varphi=k^{(2-d)/2}Z_k^{1/2}\varphi,
\qquad
u_k(\tilde\varphi)=k^{-d}U_k(\varphi).
$$

The anomalous dimension is

$$
\eta=-\partial_t\log Z_k.
$$

A fixed point is a $k$-independent dimensionless functional:

$$
\partial_t \tilde\Gamma_k=0.
$$

Linearizing around the fixed point gives scaling exponents. In scalar critical phenomena, this is one of the main computational uses of FRG: find a fixed-point potential and derivative terms, then extract the eigenvalues of perturbations around it.

The same logic extends to more complicated theories, but the functional space and symmetry constraints become more demanding.

## Relation to Wilsonian exact RG

The Wilsonian action $S_\Lambda$ and the effective average action $\Gamma_k$ are both scale-dependent functionals, but they answer different questions.

| Question | Wilsonian action $S_\Lambda$ | Effective average action $\Gamma_k$ |
|---|---|---|
| Which modes are explicit? | modes below a UV cutoff | all modes present, low modes suppressed by $R_k$ |
| Natural output | local operator expansion | effective potential and 1PI vertices |
| Common equation | Polchinski or Wegner–Houghton | Wetterich |
| Regulator role | cutoff in propagator or blocking kernel | infrared mass-like suppression |
| Physical endpoint | low-energy Wilsonian description | full effective action $\Gamma$ at $k=0$ |

The two formulations are related under appropriate Legendre transforms and regulator choices, but the relationship is not the same as saying $S_\Lambda=\Gamma_k$. They are different coordinate systems on RG information. Exact universal data should agree. Truncated results can differ.

## Gauge theories and symmetry caveats

Gauge theories are subtle in FRG because a regulator term like

$$
\Delta S_k[A]=\frac12\int_p A_\mu^a(p)R_k^{\mu\nu}(p)A_\nu^a(-p)
$$

generally breaks ordinary gauge invariance. There are several ways to handle this:

| Method | Idea |
|---|---|
| background-field FRG | preserve background gauge invariance while tracking modified identities |
| modified Ward or Slavnov–Taylor identities | enforce the symmetry constraints deformed by $R_k$ |
| gauge-invariant variables | formulate the flow in terms of invariant objects when possible |
| physical gauges or special regulators | reduce unphysical components at the cost of other complications |

None of these is a magic wand. Gauge-compatible truncations require much more care than scalar order-parameter truncations. A calculation can look impressive and still violate the identities that protect the physics if the truncation is careless.

For fermions, the flow uses Grassmann fields and supertraces. For supersymmetric theories, regulators can break supersymmetry unless chosen carefully. For gravity and asymptotic-safety applications, diffeomorphism symmetry and background dependence introduce further conceptual and technical issues.

## What FRG is good for

FRG is especially useful when the problem is not simply a small-coupling expansion. Typical applications include:

| Area | What FRG can do |
|---|---|
| critical phenomena | compute critical exponents and scaling functions with derivative expansions |
| scalar phase transitions | follow effective potentials and order-parameter flows |
| many-body systems | treat competing channels and threshold effects |
| low-energy QCD models | study chiral symmetry breaking and phase diagrams in truncations |
| quantum gravity programs | search for non-Gaussian fixed points in asymptotic-safety truncations |
| nonequilibrium systems | organize scale-dependent stochastic or real-time effective actions |

The keyword is **organize**. FRG is not a universal black-box solver. Its reliability depends on the ansatz, the symmetry constraints, the regulator, and checks against other methods.

## How to read FRG calculations

When reading an FRG paper or page, ask these questions:

| Question | Why it matters |
|---|---|
| What is the flowing object? | Wilsonian action, effective average action, vertex functional, or something else? |
| What regulator is used? | Truncated answers can depend on the regulator. |
| What truncation is made? | This is where the approximation enters. |
| Which symmetries are exact in the truncation? | Broken identities can contaminate results. |
| Are dimensionless variables used for fixed points? | Fixed points are statements about rescaled functionals. |
| Are results stable under enlarging the truncation? | Stability is the main sanity check. |
| Are there benchmark comparisons? | Perturbation theory, lattice, exact limits, or bootstrap data can calibrate the method. |

A good FRG calculation is not one with the longest ansatz. It is one whose approximation is matched to the physics and whose errors are probed honestly.

## Common pitfalls

**Calling the Wetterich equation one-loop.** It has a one-loop trace structure, but the propagator contains the full running second derivative $\Gamma_k^{(2)}$. The equation is exact before truncation.

**Forgetting the regulator breaks some symmetries.** Gauge symmetry, supersymmetry, chiral symmetry, and spacetime symmetries can be distorted by $R_k$. The calculation must account for this.

**Treating $k$ as a physical energy.** The scale $k$ is a sliding resolution scale. Physical observables are obtained at $k=0$ or from scale-independent fixed-point data.

**Believing a truncation because it is nonperturbative.** Nonperturbative does not mean reliable. A bad nonperturbative truncation can be worse than a good perturbative calculation.

**Confusing the Wilsonian action with the effective average action.** They are related RG languages, not the same functional.

**Ignoring field redefinitions.** Different choices of fields and normalization can change the apparent form of a truncation, especially near interacting fixed points.

## Relations to other pages

[Exact Renormalization Group](/renormalization-rg-eft/wilsonian-renormalization/exact-renormalization-group/) introduces the broader family of exact functional flows. This page focuses on the effective-average-action version. [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) explains why $\Gamma_k$ should be viewed as a point in an infinite-dimensional functional space. [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) explains how fixed-point eigenperturbations are classified.

Later pages on [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) will use the same fixed-point logic with more concrete examples.

## Research status

The Wetterich equation and related FRG equations are established exact identities. Their numerical and conceptual power comes from truncations: derivative expansions, vertex expansions, BMW-type schemes, grid methods for potentials, form-factor expansions, and symmetry-adapted ansätze.

Active research includes improving error estimates, preserving gauge and BRST identities, handling real-time and finite-density systems, connecting FRG to lattice and bootstrap results, treating fermionic and topological systems, and applying FRG to quantum gravity and strongly coupled matter. Many claims in these areas are valuable but truncation-dependent; careful pages should always say what was assumed.

## Exercises

### Exercise 1: Recovering the full effective action

Explain why $\Gamma_{k\to0}$ becomes the ordinary 1PI effective action.

<details><summary><strong>Solution</strong></summary>

The effective average action is defined by a modified Legendre transform with subtraction of $\Delta S_k[\varphi]$. If $R_k\to0$ as $k\to0$, then

$$
\Delta S_k[\phi]\to0.
$$

The regulated generating functional $Z_k[J]$ becomes the ordinary generating functional $Z[J]$, and the modified Legendre transform becomes the ordinary Legendre transform. Therefore

$$
\Gamma_{k\to0}=\Gamma,
$$

where $\Gamma$ is the full 1PI effective action.

</details>

### Exercise 2: The local potential flow

Assume the truncation

$$
\Gamma_k[\varphi]
=\int d^d x\left[U_k(\varphi)+\frac12 Z_k(\partial\varphi)^2\right]
$$

with constant background $\varphi$. Show why the denominator in the flow of $U_k$ contains $Z_kp^2+R_k(p)+U_k''(\varphi)$.

<details><summary><strong>Solution</strong></summary>

For a constant background, derivative terms vanish in the action itself, but the second functional derivative with respect to fluctuations contains the inverse propagator. The kinetic term contributes $Z_kp^2$ in momentum space. The regulator contributes $R_k(p)$. The second derivative of the potential contributes

$$
\frac{d^2U_k}{d\varphi^2}=U_k''(\varphi).
$$

Thus

$$
\Gamma_k^{(2)}+R_k
=Z_kp^2+R_k(p)+U_k''(\varphi),
$$

and the Wetterich equation gives

$$
\partial_t U_k(\varphi)
=\frac12\int_p
\frac{\partial_tR_k(p)}{Z_kp^2+R_k(p)+U_k''(\varphi)}.
$$

</details>

### Exercise 3: One-loop approximation from the exact equation

Show how the Wetterich equation reduces to a one-loop-like approximation if one replaces $\Gamma_k^{(2)}$ on the right-hand side by the second derivative of a fixed classical action $S^{(2)}$.

<details><summary><strong>Solution</strong></summary>

The exact equation is

$$
\partial_t\Gamma_k
=\frac12\operatorname{Tr}\left[(\Gamma_k^{(2)}+R_k)^{-1}\partial_tR_k\right].
$$

If we approximate

$$
\Gamma_k^{(2)}\approx S^{(2)},
$$

then

$$
\partial_t\Gamma_k
\approx
\frac12\operatorname{Tr}\left[(S^{(2)}+R_k)^{-1}\partial_tR_k\right].
$$

This is the scale derivative of a regulated one-loop determinant,

$$
\partial_t\Gamma_k
\approx
\frac12\partial_t\operatorname{Tr}\log(S^{(2)}+R_k),
$$

up to terms from any explicit $k$ dependence of $S^{(2)}$. Integrating over $t$ gives the familiar one-loop effective action structure. The exact FRG improves this by replacing $S^{(2)}$ with the full running $\Gamma_k^{(2)}$.

</details>

## References

- C. Wetterich, "Exact Evolution Equation for the Effective Potential," *Physics Letters B* **301** (1993) 90–94.
- T. R. Morris, "The Exact Renormalization Group and Approximate Solutions," *International Journal of Modern Physics A* **9** (1994) 2411–2450.
- J. Berges, N. Tetradis, and C. Wetterich, "Non-Perturbative Renormalization Flow in Quantum Field Theory and Statistical Physics," *Physics Reports* **363** (2002) 223–386.
- B. Delamotte, "An Introduction to the Nonperturbative Renormalization Group," in *Renormalization Group and Effective Field Theory Approaches to Many-Body Systems*.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, RG, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, for the Wilson action, effective action logic, and exact RG motivation.

## Version history

- 2026-06-17: First polished draft. Introduced the effective average action, Wetterich equation, regulator requirements, local potential approximation, fixed-point variables, symmetry caveats, and relation to Wilsonian exact RG.
