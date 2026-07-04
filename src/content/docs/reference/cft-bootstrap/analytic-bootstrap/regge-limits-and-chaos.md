---
title: "Regge Limits and Chaos"
description: "How Lorentzian Regge limits constrain CFT correlators, control inversion-formula subtractions, and connect conformal bootstrap to causality and quantum chaos."
sidebar:
  label: "Regge Limits and Chaos"
  order: 7
level: Advanced
status: "Polished draft"
source: "Caron-Huot 2017; Maldacena, Shenker, and Stanford; conformal Regge theory; analytic bootstrap and holographic CFT literature."
topics:
  - Regge limit
  - quantum chaos
  - Lorentzian CFT
  - analytic conformal bootstrap
  - causality
canonicalTopics:
  - regge-limits-and-chaos
  - conformal-regge-theory
  - chaos-bound-cft
researchStatus:
  established:
    - "Lorentzian Regge behavior controls the validity of inversion formulas, constrains high-energy CFT correlators, and connects causality with bounds on chaos in thermal systems."
  active:
    - "Current research studies Regge behavior in spinning, thermal, defect, nonunitary, and holographic loop settings, including subtractions, chaos diagnostics, and flat-space limits."
---

## Summary

A **Regge limit** is a Lorentzian high-energy limit of a correlation function. In CFT language, it is a limit of cross-ratios reached after analytic continuation to a Lorentzian sheet. It probes high-spin exchange, causal propagation, and the growth of correlators under large boosts.

Regge behavior matters for analytic bootstrap because the Lorentzian inversion formula relies on contour deformations. These deformations are safe only if the correlator is sufficiently bounded in the Regge limit. If the correlator grows too quickly, extra subtraction terms or low-spin ambiguities can appear.

The same physics is tied to quantum chaos. Thermal out-of-time-order correlators can grow exponentially,

$$
F(t)\sim 1-\frac{1}{N^2}e^{\lambda_L t}+\cdots,
$$

where $\lambda_L$ is the Lyapunov exponent. Under broad assumptions, quantum systems obey the chaos bound

$$
\lambda_L\le \frac{2\pi}{\beta},
$$

with $\beta$ the inverse temperature. Holographic CFTs dual to Einstein gravity saturate this bound.

The slogan is

$$
\text{Regge growth controls causality, inversion, and chaos}.
$$

This page explains the CFT Regge limit, why boundedness matters, how it relates to spin, and how the same Lorentzian analytic structure appears in chaos and holography.

## Prerequisites

Read [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) and [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/) first.

You should know that Lorentzian continuation changes the sheet of a correlator, that inversion formulas use double discontinuities, and that large-spin CFT data are controlled by Lorentzian analytic structure.

Some familiarity with thermal correlators, out-of-time-order correlators, and holographic CFT will help, but the page introduces the main conceptual connections.

## Core idea

Euclidean correlators are ordered and tame. Lorentzian correlators know about causality. By moving operators around branch points in cross-ratio space, one can reach sheets where the correlator behaves like a high-energy scattering amplitude.

The Regge limit is the CFT analogue of high-energy fixed-impact-parameter scattering. Instead of ordinary Mandelstam variables, one uses cross-ratios. Instead of angular momentum partial waves in flat space, one uses conformal spin.

The conceptual chain is

$$
\text{Lorentzian continuation}
\quad\longrightarrow\quad
\text{Regge sheet}
\quad\longrightarrow\quad
\text{large boost / high spin}
\quad\longrightarrow\quad
\text{causality and bounded growth}.
$$

If the correlator grows too fast in this limit, it can violate assumptions used in analytic bootstrap. If it is well behaved, inversion formulas reconstruct CFT data above a spin threshold.

Regge limits are where CFT stops being a peaceful Euclidean garden and starts behaving like a collider in a lightning storm.

## Setup and cross-ratios

For scalar four-point functions, use

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

A convenient Lorentzian Regge limit is reached by analytically continuing around a branch point and then taking a small parameter limit. One common parametrization uses

$$
z=\sigma e^{\rho},
\qquad
\bar z=\sigma e^{-\rho},
$$

with

$$
\sigma\to0
$$

on an appropriate Lorentzian sheet while $\rho$ is held fixed. Different conventions use different variables, but the invariant idea is a large relative boost between pairs of operators.

On the Euclidean sheet, the same small-cross-ratio region may be controlled by an ordinary OPE. On the Regge sheet, analytic continuation changes which singularities and exchanges dominate.

Therefore, always specify the sheet. The words “small $z$ and $\bar z$” are not enough.

## Regge growth

In the Regge limit, a correlator may behave schematically like

$$
\mathcal G_{\rm Regge}\sim \sigma^{1-J_0}
$$

where $J_0$ is an effective leading Regge intercept. If

$$
J_0>1,
$$

the correlator grows as $\sigma\to0$. If

$$
J_0\le1,
$$

it is bounded or decays in the relevant sense.

The precise bound depends on the correlator and normalization, but the moral is stable:

$$
\text{larger Regge intercept}\quad\Rightarrow\quad\text{faster Lorentzian growth}.
$$

Regge growth is controlled by high-spin exchanges and Regge trajectories. In holographic CFTs, the leading Regge behavior is often associated with graviton exchange or its stringy Reggeization.

For analytic bootstrap, the important question is whether the growth is mild enough for contour deformations and inversion formulas to be valid without extra subtractions.

## Spin and Regge trajectories

In ordinary scattering theory, Regge theory analytically continues angular momentum. In CFT, the analogous variable is spin or conformal spin. Operators can organize into analytic trajectories

$$
\Delta(J).
$$

The Lorentzian inversion formula gives one route to these trajectories for sufficiently large spin. Regge theory asks how these trajectories control high-energy Lorentzian correlators.

A rough dictionary is:

| Scattering language | CFT language |
|---|---|
| angular momentum | spin $J$ |
| Regge pole | analytic spin trajectory |
| high energy | Lorentzian Regge limit |
| impact parameter | transverse or hyperbolic-space separation |
| intercept | leading effective spin controlling growth |

The Regge limit and the lightcone limit are related but distinct. Lightcone bootstrap studies large spin through OPE singularities. Regge analysis studies high-energy Lorentzian growth after moving to a different sheet.

They are cousins, not twins. Family resemblance, separate holiday drama.

## Regge boundedness and inversion

The Lorentzian inversion formula is derived by deforming contours. A contour deformation can fail if the integrand has a large contribution from infinity. Regge boundedness is the condition that this bad contribution is absent or controlled.

If the correlator is sufficiently bounded, the inversion formula reconstructs CFT data for spins above a threshold:

$$
J>J_0.
$$

If the correlator grows too fast, one may need subtractions. These subtractions correspond to ambiguities that affect low-spin data.

This explains why inversion formulas often come with statements like:

$$
\text{valid for spin greater than one}
$$

or

$$
\text{valid above a Regge intercept threshold}.
$$

The exact threshold is not decoration. It is a physical statement about Lorentzian high-energy behavior.

## Causality constraints

Lorentzian correlators must respect causality. In CFT, this leads to constraints on singularities, commutators, and Regge growth.

One important class of results comes from demanding that high-energy scattering in a CFT does not lead to time advances or other causal pathologies. In holographic theories, this becomes the statement that particles propagating through shockwave geometries should experience allowed time delays.

Causality constraints imply restrictions on CFT data such as:

- signs and sizes of stress-tensor couplings;
- higher-derivative corrections in holographic duals;
- central-charge ratios;
- higher-spin gaps;
- Regge intercepts and growth rates.

These constraints are related to conformal collider bounds and averaged energy conditions. Regge behavior is one of the Lorentzian arenas where those constraints become sharp.

## Chaos and OTOCs

Quantum chaos is often diagnosed using an out-of-time-order correlator, or OTOC. A schematic thermal OTOC is

$$
F(t)=\langle V(t)W(0)V(t)W(0)\rangle_\beta.
$$

In chaotic systems with many degrees of freedom, one may find an intermediate-time regime

$$
F(t)\approx F_0-\epsilon e^{\lambda_L t},
$$

where $\lambda_L$ is the Lyapunov exponent.

The ordering is important. Out-of-time ordering forces a Lorentzian analytic continuation to a nontrivial sheet. This is why chaos and Regge physics are connected: both probe correlator growth on Lorentzian sheets reached by moving operators around branch points.

The chaos bound states, under broad assumptions, that

$$
\lambda_L\le\frac{2\pi}{\beta}.
$$

The bound is saturated by many holographic large-$N$ CFTs with Einstein gravity duals.

## Holographic picture

In AdS/CFT, the Regge limit corresponds to high-energy scattering in AdS. The leading contribution at strong coupling often comes from graviton exchange. This produces maximal chaos:

$$
\lambda_L=\frac{2\pi}{\beta}.
$$

Stringy corrections soften the Regge behavior. Instead of a spin-two graviton alone, one has a Reggeized trajectory, and the effective intercept can be below two. This lowers the chaos exponent below the maximal value.

The holographic dictionary is:

| CFT Regge or chaos object | Bulk interpretation |
|---|---|
| Regge limit | high-energy scattering in AdS |
| leading intercept | leading exchanged Regge trajectory |
| stress tensor | graviton |
| higher-spin gap | string scale or higher-spin mass scale |
| OTOC growth | shockwave scattering near a horizon |
| chaos bound saturation | Einstein gravity behavior |

This is one of the cleanest places where bootstrap, causality, thermal physics, and quantum gravity all shake hands.

## Higher-spin currents

A theory with exactly conserved higher-spin currents has very special Regge behavior. In many cases, exact higher-spin symmetry implies that the CFT is free or generalized-free-like under suitable assumptions.

A sparse holographic CFT should have a large gap to higher-spin single-trace operators. This gap helps keep Regge growth under control and makes the bulk dual look local and gravitational rather than stringy or higher-spin at low energies.

The rough principle is

$$
\text{large higher-spin gap}
\quad\Rightarrow\quad
\text{Einstein-like Regge behavior at low energies}.
$$

Conversely, light higher-spin operators can dramatically change Regge growth and chaos.

This is why Regge limits are a diagnostic of whether a large-$N$ CFT is holographic in the Einstein-gravity sense.

## Relation to conformal collider bounds

Conformal collider bounds constrain energy flux measured at null infinity after inserting local operators. These bounds are Lorentzian, causal, and positive.

Regge constraints are part of the same family of ideas. Both rely on:

- analytic continuation from Euclidean correlators;
- positivity or causality in Lorentzian signature;
- stress-tensor and current three-point data;
- restrictions on high-energy or null propagation.

For example, requiring no causality violation in a holographic shockwave background can reproduce or sharpen constraints on stress-tensor three-point couplings.

The moral is:

$$
\text{Lorentzian consistency sees data invisible to purely Euclidean symmetry counting.}
$$

## Regge versus lightcone limits

The lightcone limit and Regge limit are easy to blur. Here is the safe comparison.

| Limit | What it probes | Main output |
|---|---|---|
| Euclidean OPE limit | nearby operator products | ordinary OPE expansion |
| lightcone limit | low twist and large spin | double-twist families and anomalous dimensions |
| Regge limit | high-energy Lorentzian growth | intercepts, causality, inversion thresholds |
| chaos limit | thermal out-of-time ordering | Lyapunov growth and chaos bound |

The same correlator can be studied in all these limits. The analytic continuation path determines which physics is visible.

This is why drawings of the $z,\bar z$ plane matter. The coordinate values alone do not tell the whole story; the sheet matters.

## Common pitfalls

**Do not define the Regge limit without specifying the Lorentzian sheet.** Euclidean small-cross-ratio limits and Regge limits can look similar but mean different things.

**Do not confuse Regge growth with ordinary OPE convergence.** Regge behavior probes high-energy Lorentzian dynamics.

**Do not ignore boundedness assumptions in inversion.** They determine spin thresholds and possible subtraction terms.

**Do not claim every CFT is maximally chaotic.** Maximal chaos is special, often associated with Einstein-like holographic dynamics.

**Do not quote the chaos bound outside its assumptions.** It requires conditions such as thermal equilibrium, analyticity, factorization-like regimes, and appropriate operator choices.

**Do not treat stress-tensor exchange and full Regge behavior as identical.** At finite coupling or with stringy corrections, the stress tensor can be part of a larger Regge trajectory.

**Do not forget global symmetry and spin.** Different channels can have different leading Regge behavior.

## Relations to other pages

This page follows [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/) and prepares [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/).

It also connects to [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) because Regge boundedness controls inversion thresholds and subtractions.

For causality and energy positivity, see [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/) and [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/). For holographic applications, see [Holographic CFT](/cft-bootstrap/holographic-cft/) and [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/).

## Research status

Regge limits are established tools in Lorentzian CFT and analytic bootstrap. They control inversion-formula assumptions, high-spin analytic structure, and causality constraints.

The chaos bound is established under broad physical assumptions and is a central result connecting thermal quantum systems, holography, and black-hole dynamics. Active research continues on precise assumptions, finite-coupling corrections, spinning and defect correlators, nonunitary cases, thermal inversion, and flat-space limits.

## Exercises

### Exercise 1

What is the main difference between a Euclidean OPE limit and a Regge limit?

<details><summary><strong>Solution</strong></summary>

A Euclidean OPE limit takes operators close together on the Euclidean sheet and is controlled by ordinary OPE convergence. A Regge limit is reached after Lorentzian analytic continuation to a different sheet and probes high-energy or large-boost behavior. The same cross-ratio values can have different meanings depending on the sheet.

</details>

### Exercise 2

Why does Regge boundedness matter for the Lorentzian inversion formula?

<details><summary><strong>Solution</strong></summary>

The derivation of the inversion formula uses contour deformation. If the correlator grows too fast in the Regge limit, the contour at infinity can contribute. Then the inversion formula may need subtractions or may only determine CFT data above a spin threshold. Regge boundedness ensures that the unwanted boundary term is absent or controlled.

</details>

### Exercise 3

If a Regge-limit correlator behaves like $\sigma^{1-J_0}$ as $\sigma\to0$, what happens when $J_0>1$?

<details><summary><strong>Solution</strong></summary>

If

$$
\mathcal G_{\rm Regge}\sim \sigma^{1-J_0}
$$

and $J_0>1$, then the exponent $1-J_0$ is negative. Therefore the correlator grows as $\sigma\to0$. The larger $J_0$ is, the faster the Regge growth.

</details>

### Exercise 4

State the chaos bound and identify the quantity it constrains.

<details><summary><strong>Solution</strong></summary>

The chaos bound states that, under broad assumptions, the Lyapunov exponent $\lambda_L$ governing intermediate-time growth of suitable thermal out-of-time-order correlators satisfies

$$
\lambda_L\le\frac{2\pi}{\beta},
$$

where $\beta$ is inverse temperature. It constrains the exponential growth rate of chaos diagnostics.

</details>

### Exercise 5

Why do holographic CFTs with Einstein gravity duals saturate the chaos bound?

<details><summary><strong>Solution</strong></summary>

In the holographic description, the relevant OTOC is controlled by high-energy shockwave scattering near a black-hole horizon. Einstein gravity gives a universal gravitational shockwave effect whose growth rate is

$$
\lambda_L=\frac{2\pi}{\beta}.
$$

This saturates the chaos bound. Stringy or higher-derivative corrections can soften the Regge behavior and reduce the exponent.

</details>

## References

- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- J. Maldacena, S. H. Shenker, and D. Stanford, “A bound on chaos,” *Journal of High Energy Physics* **2016**.
- J. Maldacena, D. Stanford, and Z. Yang, “Conformal symmetry and its breaking in two dimensional nearly anti-de-Sitter space,” *Progress of Theoretical and Experimental Physics* **2016**.
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- D. M. Hofman and J. Maldacena, “Conformal collider physics: Energy and charge correlations,” *Journal of High Energy Physics* **2008**.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added Regge-limit setup, growth and intercept language, inversion-formula boundedness, causality constraints, chaos and OTOCs, holographic interpretation, higher-spin comments, collider-bound connections, exercises, and references.
