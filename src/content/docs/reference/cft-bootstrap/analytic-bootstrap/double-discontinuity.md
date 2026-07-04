---
title: "Double Discontinuity"
description: "What the double discontinuity is, why it is positive in unitary Lorentzian CFT, and how it supplies the input to the Lorentzian inversion formula."
sidebar:
  label: "Double Discontinuity"
  order: 6
level: Advanced
status: "Polished draft"
source: "Caron-Huot 2017; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019; analytic bootstrap literature."
topics:
  - double discontinuity
  - Lorentzian inversion formula
  - analytic conformal bootstrap
  - positivity
  - branch cuts
canonicalTopics:
  - double-discontinuity
  - lorentzian-discontinuities
  - ddisc-positivity
researchStatus:
  established:
    - "The double discontinuity is the Lorentzian branch-cut combination that appears in the Lorentzian inversion formula and isolates the crossed-channel data relevant for large-spin CFT reconstruction."
  active:
    - "Current work refines double-discontinuity methods for spinning correlators, defects, thermal systems, holographic loops, nonunitary theories, and subtracted dispersion relations."
---

## Summary

The **double discontinuity** is a Lorentzian combination of analytic continuations of a four-point function around a branch cut. It is usually written as

$$
\operatorname{dDisc}\,\mathcal G.
$$

In the simplest identical-scalar discussion around a crossed-channel cut, it has the schematic form

$$
\operatorname{dDisc}[\mathcal G]
=
\mathcal G
-\frac12\mathcal G^{\circlearrowleft}
-\frac12\mathcal G^{\circlearrowright},
$$

where $\mathcal G^{\circlearrowleft}$ and $\mathcal G^{\circlearrowright}$ are the two analytic continuations around the branch point.

For a simple branch-cut term,

$$
(1-\bar z)^a,
$$

the double discontinuity is proportional to

$$
\sin^2(\pi a)(1-\bar z)^a,
$$

up to convention-dependent phases and external-dimension factors. Integer-power analytic terms have zero double discontinuity.

The double discontinuity matters because it is the input to the Lorentzian inversion formula. It isolates the part of a correlator that reconstructs large-spin CFT data and has positivity properties in unitary theories.

The slogan is

$$
\text{dDisc}=
\text{the positive Lorentzian branch-cut data seen by inversion}.
$$

## Prerequisites

Read [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/), and [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) first.

You should know the cross-ratios

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

and the basic idea that Lorentzian analytic continuation creates branch cuts associated with causal operator ordering.

## Core idea

A Euclidean correlator is often single-valued in its Euclidean domain. After analytic continuation to Lorentzian kinematics, the same function has branch cuts. Moving an insertion around another insertion changes the operator ordering and can put the correlator on a different sheet.

The ordinary discontinuity measures the jump across one branch cut. The double discontinuity measures a more symmetric combination of the two paths around the cut. This combination is adapted to conformal blocks and unitarity.

The conceptual chain is

$$
\text{Lorentzian branch cut}
\quad\longrightarrow\quad
\text{double discontinuity}
\quad\longrightarrow\quad
\text{positive inversion input}
\quad\longrightarrow\quad
\text{CFT data at large spin}.
$$

This is why modern analytic bootstrap is not just Euclidean Taylor expansion. Lorentzian sheet structure carries dynamical information.

## Setup and conventions

Consider identical scalar primaries $\phi$ with four-point function

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(z,\bar z),
$$

where

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The crossed-channel OPE limit is often associated with

$$
z\to1,
\qquad
\bar z\to1.
$$

The double discontinuity used in the inversion formula is usually taken around the branch cut beginning at

$$
\bar z=1
$$

with $z$ held in a suitable range. The exact definition depends on channel, operator ordering, and external dimensions.

For identical external scalars, a simple schematic definition is enough for intuition:

$$
\operatorname{dDisc}[\mathcal G]
=\mathcal G-\frac12\mathcal G^{\circlearrowleft}-\frac12\mathcal G^{\circlearrowright}.
$$

For non-identical external operators, phase factors involving external dimension differences must be included. Always check conventions before copying exact coefficients.

## Simple powers

The easiest example is a pure power near the branch point:

$$
f(\bar z)=(1-\bar z)^a.
$$

Analytically continuing around $\bar z=1$ multiplies this by phases:

$$
f^{\circlearrowleft}=e^{2\pi i a}f,
\qquad
f^{\circlearrowright}=e^{-2\pi i a}f.
$$

Therefore

$$
\operatorname{dDisc}f
=f-\frac12e^{2\pi i a}f-\frac12e^{-2\pi i a}f
=\left(1-\cos 2\pi a\right)f.
$$

Using

$$
1-\cos 2\pi a=2\sin^2\pi a,
$$

we get

$$
\operatorname{dDisc}(1-\bar z)^a
=2\sin^2(\pi a)(1-\bar z)^a.
$$

This formula explains the name. The double discontinuity is sensitive to branch cuts, not to analytic Taylor terms.

## What dDisc kills

Analytic terms with integer powers around the branch point have zero double discontinuity. For example,

$$
\operatorname{dDisc}(1-\bar z)^n=0,
\qquad
n\in\mathbb Z.
$$

This is useful. It means the double discontinuity ignores many contact-like or analytic contributions and focuses on branch-cut data.

But this statement needs care. A contribution can be invisible to dDisc in one channel but still affect low-spin data or require subtractions. The inversion formula reconstructs sufficiently high spin under Regge assumptions; low spin can retain ambiguities.

So the correct lesson is

$$
\operatorname{dDisc}\text{ removes analytic clutter, not all physically relevant subtleties.}
$$

This is the tiny trapdoor under many too-fast analytic-bootstrap explanations.

## Positivity

In a unitary CFT, the double discontinuity has positivity properties. For identical scalar four-point functions in an appropriate Lorentzian regime, one can often regard

$$
\operatorname{dDisc}\mathcal G(z,\bar z)
$$

as a positive quantity or as built from positive spectral data.

This positivity is the Lorentzian cousin of OPE coefficient positivity in Euclidean bootstrap. It supports:

- analyticity and convexity properties of large-spin trajectories;
- sign constraints on anomalous dimensions;
- causal constraints related to energy conditions;
- inversion-formula reconstruction from physical spectral information;
- dispersion-relation interpretations of CFT correlators.

The positivity is not a random miracle. It comes from Hilbert-space positivity, operator ordering, and the specific double-continuation combination. Ordinary discontinuities do not generally have the same positivity properties.

## Relation to conformal blocks

A crossed-channel conformal block has a branch-cut structure controlled by the twist and dimension of the exchanged operator. Its double discontinuity is usually nonzero unless the contribution is too analytic in the chosen channel.

For an exchanged primary $\mathcal O_m$ with twist

$$
\tau_m=\Delta_m-\ell_m,
$$

the crossed-channel block contributes to

$$
\operatorname{dDisc}\mathcal G.
$$

When inserted into the Lorentzian inversion formula, this contribution produces large-spin corrections of the form

$$
\gamma_{n,J}^{(m)}\sim J^{-\tau_m}
$$

for direct-channel double-twist operators.

Thus the double discontinuity is the precise object that converts crossed-channel low-twist exchange into direct-channel large-spin CFT data.

## Identity and disconnected pieces

The identity contribution is special. It produces the leading mean-field double-twist spectrum, but its double discontinuity can vanish or require separate treatment depending on the channel and convention.

For generalized free fields, the correlator contains disconnected terms such as

$$
1,
\qquad
u^{\Delta_\phi},
\qquad
\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

Some of these terms are analytic in the relevant channel, while others create branch cuts. The inversion formula can reproduce mean-field OPE data, but one must be careful about which part of the correlator is being inverted and which channel is used.

The safe statement is:

$$
\text{identity exchange sets the mean-field skeleton; dDisc tracks branch-cut data in the chosen channel.}
$$

Do not apply a one-line dDisc formula to disconnected correlators without checking the channel.

## Relation to anomalous dimensions

Anomalous dimensions show up as logarithms:

$$
u^{\Delta/2}
= u^{\Delta^{(0)}/2}
\left(1+\frac{\gamma}{2}\log u+\cdots\right).
$$

The double discontinuity detects branch-cut behavior, and logarithms are branch-cut factories. In the crossed channel, low-twist exchange contributes to dDisc. In the direct channel, inversion turns that contribution into pole shifts, which are anomalous dimensions.

This gives the chain:

$$
\operatorname{dDisc}_{\text{crossed}}
\quad\to\quad
\text{pole shift in }c(\Delta,J)
\quad\to\quad
\gamma_{n,J}.
$$

This is the modern, systematic version of the older lightcone matching argument.

## Relation to Regge behavior

The derivation of Lorentzian inversion involves contour deformations. These are valid when the correlator is sufficiently bounded in a Lorentzian Regge limit.

If the correlator grows too fast, the contour deformation can pick up boundary terms. Those terms correspond to subtractions or low-spin ambiguities. The double discontinuity alone may then be insufficient to reconstruct all data.

This is why one often says that inversion determines CFT data only above a spin threshold:

$$
J>J_0.
$$

The threshold depends on Regge behavior and the correlator being studied.

Double discontinuity is powerful, but it lives inside a larger analytic story. Regge bounds are the safety rails.

## Holographic interpretation

In holographic CFTs, the double discontinuity resembles an absorptive part of an AdS scattering process. Tree-level exchange diagrams and loop diagrams create branch cuts. Inverting the double discontinuity reconstructs double-trace anomalous dimensions and OPE coefficients.

The rough dictionary is:

| Boundary object | Bulk intuition |
|---|---|
| double discontinuity | absorptive or cut part of an amplitude |
| crossed-channel exchange | bulk particle exchange |
| large-spin double twist | two-particle AdS state |
| anomalous dimension | binding energy |
| low-spin ambiguity | contact-term or subtraction ambiguity |

This dictionary is not a substitute for formulas, but it is a good compass. The double discontinuity is the part of the correlator most directly tied to physical intermediate states.

## Common pitfalls

**Do not confuse discontinuity with double discontinuity.** The double discontinuity is a particular symmetric combination of two analytic continuations.

**Do not forget external-dimension phases.** For non-identical external operators, the simple identical-scalar formula must be modified.

**Do not say dDisc sees everything.** Analytic and contact-like terms can have zero dDisc but still affect low-spin data or require subtractions.

**Do not ignore channel labels.** The double discontinuity is defined around a particular branch cut in a particular OPE channel.

**Do not treat positivity as automatic in every theory.** Standard positivity relies on unitarity and appropriate Lorentzian ordering.

**Do not mishandle the identity.** Disconnected pieces and identity exchange may require separate bookkeeping.

**Do not quote exact coefficients from schematic formulas.** Measures, phases, and normalizations vary across references.

## Relations to other pages

This page follows [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) and prepares [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/).

It also connects back to [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/) because dDisc is the object whose inversion produces large-spin anomalous dimensions.

For numerical connections, see [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/). For holographic uses, see [Holographic CFT](/cft-bootstrap/holographic-cft/) and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/).

## Research status

The double discontinuity is established as a central object in Lorentzian inversion and analytic bootstrap. Its positivity properties and role in reconstructing large-spin data are standard in modern CFT.

Active research extends double-discontinuity methods to spinning correlators, supersymmetric theories, boundary and defect CFTs, thermal correlators, holographic loop amplitudes, nonunitary settings, and subtracted dispersion relations.

## Exercises

### Exercise 1

Compute the double discontinuity of

$$
f(\bar z)=(1-\bar z)^a
$$

using the schematic identical-scalar definition.

<details><summary><strong>Solution</strong></summary>

The two analytic continuations around $\bar z=1$ give

$$
f^{\circlearrowleft}=e^{2\pi ia}f,
\qquad
f^{\circlearrowright}=e^{-2\pi ia}f.
$$

Therefore

$$
\operatorname{dDisc}f
=f-\frac12 e^{2\pi ia}f-\frac12 e^{-2\pi ia}f
=(1-\cos2\pi a)f.
$$

Since

$$
1-\cos2\pi a=2\sin^2\pi a,
$$

we get

$$
\operatorname{dDisc}(1-\bar z)^a
=2\sin^2(\pi a)(1-\bar z)^a.
$$

</details>

### Exercise 2

Why does an integer power have zero double discontinuity?

<details><summary><strong>Solution</strong></summary>

If $a=n\in\mathbb Z$, then

$$
e^{2\pi i n}=e^{-2\pi i n}=1.
$$

Thus

$$
\operatorname{dDisc}(1-\bar z)^n
=\left(1-\frac12-\frac12\right)(1-\bar z)^n=0.
$$

Equivalently,

$$
\sin^2(\pi n)=0.
$$

Integer powers are analytic around the branch point, so there is no branch cut for dDisc to detect.

</details>

### Exercise 3

Why is dDisc better suited to the inversion formula than an ordinary discontinuity?

<details><summary><strong>Solution</strong></summary>

The double discontinuity is designed to have positivity properties in unitary Lorentzian CFT and to remove many analytic or contact-like terms. The Lorentzian inversion formula integrates this positive branch-cut data against a known kernel. An ordinary discontinuity does not generally have the same positivity or projection properties.

</details>

### Exercise 4

What does it mean to say that dDisc can miss low-spin ambiguities?

<details><summary><strong>Solution</strong></summary>

Some analytic or contact-like contributions may have zero double discontinuity in a given channel. These terms can still affect low-spin CFT data. The Lorentzian inversion formula reconstructs data above a spin threshold under Regge-boundedness assumptions; below that threshold, extra subtractions or independent input may be needed.

</details>

### Exercise 5

How does crossed-channel dDisc determine direct-channel anomalous dimensions?

<details><summary><strong>Solution</strong></summary>

Crossed-channel low-twist operators contribute to the double discontinuity. The Lorentzian inversion formula integrates this dDisc and produces a function $c(\Delta,J)$ whose poles encode direct-channel CFT data. Shifts in the pole locations relative to mean-field double-twist values are anomalous dimensions:

$$
\Delta_{n,J}=\Delta_{n,J}^{(0)}+\gamma_{n,J}.
$$

Thus crossed-channel dDisc data determine large-spin anomalous dimensions.

</details>

## References

- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).

## Version history

- 2026-07-01: First polished draft. Added definition of dDisc, simple-power example, positivity, relation to conformal blocks, identity subtleties, anomalous dimensions, Regge caveats, holographic interpretation, exercises, and references.
