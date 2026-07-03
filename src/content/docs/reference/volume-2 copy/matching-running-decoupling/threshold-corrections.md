---
title: "Threshold Corrections"
description: "How finite matching terms appear when heavy degrees of freedom are removed and the RG description changes across a mass threshold."
sidebar:
  label: "Threshold Corrections"
  order: 3
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, RG methods and minimal subtraction; Schwartz 2014, RG and nonrenormalizable theories; Burgess 2020, decoupling, power counting, and matching; Manohar EFT lectures."
topics:
  - threshold corrections
  - decoupling
  - EFT matching
  - running couplings
  - Wilson coefficients
canonicalTopics:
  - threshold-matching
  - decoupling-relations
  - eft-running-and-matching
researchStatus:
  established:
    - "Threshold corrections are standard finite matching terms that relate parameters and Wilson coefficients in theories with different active degrees of freedom."
  active:
    - "Precision threshold matching, multi-loop decoupling, mixed electroweak-QCD thresholds, evanescent operators, and automated basis conversion remain active technical areas."
---

## Summary

A **threshold correction** is the finite local adjustment required when the appropriate low-energy description changes at a heavy mass scale. Above a mass $M$, a particle or multiplet may be active. Below $M$, it is removed from the EFT. The two descriptions use different field content, different beta functions, and sometimes different operator bases. Threshold corrections are the matching terms that make the two descriptions agree on low-energy observables.

The schematic relation is

$$
C_i^{<}(\mu_M)
=R_i{}^j C_j^{>}(\mu_M)+\Delta_i^{\text{th}}(\mu_M,M),
$$

where $>$ denotes the theory above the threshold, $<$ denotes the theory below it, $R_i{}^j$ maps the high-energy operator basis into the low-energy one, and $\Delta_i^{\text{th}}$ is the threshold correction. The matching scale $\mu_M$ is usually chosen near $M$ to avoid large logarithms.

Threshold corrections are not a physical discontinuity. They are a coordinate transformation between two EFT descriptions. Running evolves parameters within a fixed EFT. Matching relates parameters across a change of EFT.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Threshold matching ladder: run in the full theory above the heavy mass, match near the threshold, and run in the low-energy EFT below it.](/figures/renormalization-rg-eft/threshold-matching-ladder.svg)

<figcaption>

A threshold separates two descriptions with different active degrees of freedom. Running above and below the threshold uses different beta functions. The threshold correction $\Delta_{\rm th}$ is fixed by matching low-energy observables near $\mu_M\simeq M$.

</figcaption>
</figure>

The most important practical lesson is:

$$
\text{match near the threshold, then run away from it.}
$$

That single sentence is responsible for much of the power of EFT in particle physics, condensed matter, and gravitational applications.

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), and [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/).

It is also useful to know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/).

## Core idea

Suppose a full theory is valid above a scale $M$, and below $M$ the heavy field is no longer part of the propagating low-energy spectrum. A low-energy observable $\mathcal O_{\text{phys}}$ can be computed in two steps:

$$
\text{high-scale input}
\longrightarrow
\text{running above }M
\longrightarrow
\text{matching at }M
\longrightarrow
\text{running below }M
\longrightarrow
\text{low-energy matrix element}.
$$

The threshold correction is the matching step. It accounts for short-distance virtual effects of the heavy field at the scale where that field is removed.

A threshold correction can affect several kinds of quantities:

| Quantity | Example of threshold correction |
|---|---|
| Couplings | $g_{<}(\mu_M)=g_{>}(\mu_M)+\Delta_g^{\text{th}}$ |
| Masses | $m_{<}^2(\mu_M)=m_{>}^2(\mu_M)+\Delta_{m^2}^{\text{th}}$ |
| Fields | $\phi_{<}=\zeta_\phi^{1/2}\phi_{>}$, with convention-dependent normalization |
| Wilson coefficients | $C_i^{<}=R_i{}^j C_j^{>}+\Delta_i^{\text{th}}$ |
| Operator bases | high-energy operators project onto a different low-energy basis |

The correction is local because the threshold is heavy. At $Q\ll M$, virtual heavy propagation cannot produce long-distance singularities in light external momenta. Its effect can therefore be expanded in local operators.

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). In particular,

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}},
\qquad
 d=4-2\epsilon
$$

in dimensional regularization. We write

| Symbol | Meaning |
|---|---|
| $M$ | heavy mass or threshold scale |
| $Q$ | typical external low-energy scale |
| $\mu_M$ | matching scale, chosen near $M$ |
| $>$ | theory above the threshold |
| $<$ | EFT below the threshold |
| $\Delta^{\text{th}}$ | threshold correction |

A threshold correction is generally scheme dependent. Its physical role is not to be independently observable; its role is to make predictions invariant under arbitrary choices such as $\mu_M$ and the renormalization scheme.

For dimensionless gauge or Yukawa couplings, it is common to match the coupling itself. For Wilson coefficients, it is often cleaner to regard matching as a linear map plus an additive correction:

$$
C^{<}=R C^{>}+\Delta^{\text{th}}.
$$

Here $R$ includes projection onto the low-energy field content, possible basis changes, and normalization conventions. In many simple examples $R$ is just the identity, but in serious EFT work it is often the source of half the bookkeeping.

## Running versus matching

Running and matching answer different questions.

**Running** asks: how do parameters change with $\mu$ inside one fixed theory?

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j.
$$

**Matching** asks: how do parameters in one theory relate to parameters in another theory at the scale where the descriptions overlap?

$$
C_i^{<}(\mu_M)=R_i{}^j C_j^{>}(\mu_M)+\Delta_i^{\text{th}}(\mu_M,M).
$$

The overlap region is essential. We require

$$
Q\ll M,
\qquad
\mu_M\sim M.
$$

The first condition justifies expanding the heavy dynamics into local operators. The second avoids large logarithms $\log(\mu_M/M)$ in the threshold correction. Logs of widely separated physical scales are then handled by RG evolution, not by a badly chosen matching calculation.

The standard low-energy prediction has the structure

$$
C^{<}(\mu_L)
=U_{<}(\mu_L,\mu_M)
\Big[ R\,U_{>} (\mu_M,\mu_H)C^{>} (\mu_H)
+\Delta^{\text{th}}(\mu_M)\Big],
$$

where $U_{>}$ and $U_{<}$ are the RG evolution operators above and below the threshold. If the calculation is done consistently, dependence on the arbitrary matching scale $\mu_M$ cancels up to terms beyond the order retained.

## The matching-scale check

A good threshold calculation passes a simple test: move the matching scale slightly and see whether the prediction changes only at higher order.

Suppose a single coupling has one-loop beta functions

$$
\mu\frac{dg_{>}}{d\mu}=\beta_{>}(g_{>}),
\qquad
\mu\frac{dg_{<}}{d\mu}=\beta_{<}(g_{<}).
$$

If the active field content changes at $M$, then $\beta_{>}$ and $\beta_{<}$ are different. A threshold relation of the form

$$
g_{<}(\mu_M)=g_{>} (\mu_M)+\Delta_g^{\text{th}}(\mu_M,M)
$$

must contain explicit $\mu_M$ dependence that compensates this change of beta function:

$$
\mu_M\frac{d}{d\mu_M}\Delta_g^{\text{th}}
=\beta_{<}(g)-\beta_{>}(g)+\text{higher orders}.
$$

This equation is not usually the easiest way to compute $\Delta_g^{\text{th}}$, but it is an excellent diagnostic. If explicit threshold logarithms do not know about the difference between the beta functions above and below the threshold, the matching relation cannot be right.

## Gauge-coupling example

Consider a gauge coupling with one-loop convention

$$
\beta_g=-\frac{b}{16\pi^2}g^3+O(g^5).
$$

Then

$$
\mu\frac{d}{d\mu}\frac{1}{g^2}
=\frac{b}{8\pi^2}+O(g^2).
$$

Let the one-loop coefficient above the threshold be

$$
b_{>}=b_{<}+b_H,
$$

where $b_H$ is the contribution of the heavy field to the beta-function coefficient. Matching the inverse coupling at one loop has the logarithmic form

$$
\frac{1}{g_{<}^2(\mu_M)}
=
\frac{1}{g_{>}^2(\mu_M)}
-\frac{b_H}{8\pi^2}\log\frac{\mu_M}{M}
+\Delta_{\text{fin}}+O(g^2).
$$

The finite constant $\Delta_{\text{fin}}$ depends on the scheme and on the precise definition of the heavy mass. The logarithm is fixed by the requirement that the slopes above and below the threshold differ correctly.

For a heavy quark threshold in QCD, using the usual $SU(3)$ one-loop coefficient

$$
b=11-\frac{2}{3}n_f,
$$

the heavy quark contributes $b_H=-2/3$. In a common $\overline{\mathrm{MS}}$ convention, the one-loop decoupling relation may be written schematically as

$$
\alpha_s^{(n_l)}(\mu_M)
=
\alpha_s^{(n_l+1)}(\mu_M)
\left[
1-\frac{\alpha_s^{(n_l+1)}(\mu_M)}{6\pi}
\log\frac{\mu_M^2}{M^2}
+O(\alpha_s^2)
\right],
$$

where $n_l$ is the number of light flavors. If one matches at $\mu_M=M$, the explicit one-loop logarithm vanishes. The change in running does not vanish; it begins immediately above and below the threshold because the beta functions are different.

:::note[Continuity is a convention, not a law]
It is often convenient to choose a scheme and a matching scale in which a coupling appears continuous across a threshold at a given perturbative order. That continuity is not a physical principle. The observable is smooth; the coordinate used to describe it can have a finite matching jump.
:::

## Threshold corrections to Wilson coefficients

For Wilson coefficients the matching relation is usually the central object:

$$
C_i^{<}(\mu_M)
=R_i{}^j C_j^{>}(\mu_M)+\Delta_i^{\text{th}}(\mu_M,M).
$$

The correction $\Delta_i^{\text{th}}$ can arise at tree level or loop level.

At tree level, a heavy propagator gives contact operators:

$$
\frac{g^2}{M^2-q^2}
=\frac{g^2}{M^2}
\left(1+\frac{q^2}{M^2}+\cdots\right).
$$

At one loop, the correction is the hard local remainder after subtracting the EFT loop contribution:

$$
\Delta_i^{\text{th}}
\quad\leftrightarrow\quad
\mathcal A_{\text{full}}^{\text{1-loop}}
-
\mathcal A_{\text{EFT}}^{\text{1-loop}}.
$$

The EFT loop subtraction matters because light fields are present on both sides. Threshold corrections should not contain low-energy branch cuts, light thresholds, or nonanalytic dependence such as $\log(-Q^2)$ that is already reproduced by the EFT. After matching and expansion in $Q/M$, the threshold contribution is local.

## Power thresholds and naturalness

Not all threshold corrections are logarithmic. Mass parameters can receive threshold corrections proportional to powers of heavy scales.

For a light scalar coupled to a heavy scalar, a typical one-loop threshold contribution has the form

$$
\Delta m^2_{\text{th}}
\sim
\frac{\kappa}{16\pi^2}M^2
\left[\text{finite constant}+\log\frac{\mu_M^2}{M^2}\right].
$$

The exact coefficient depends on normalization and the interaction. The important point is dimensional: a light scalar mass is a relevant parameter, so heavy thresholds can shift it by an amount of order $M^2$ unless a symmetry forbids or suppresses the correction.

This is the threshold version of the hierarchy problem. It is not merely a story about quadratic divergences in a cutoff regulator. Even in dimensional regularization, finite matching across a heavy threshold can know about $M^2$.

For marginal couplings, threshold corrections are usually logarithmic or finite dimensionless numbers. For relevant couplings, thresholds can be power sensitive. For irrelevant operators, thresholds generate Wilson coefficients suppressed by powers of $1/M$.

## Multiple thresholds

If several heavy scales are well separated,

$$
M_1\gg M_2\gg M_3\gg Q,
$$

one should usually integrate them out one at a time:

$$
\text{Theory above }M_1
\to
\text{EFT below }M_1
\to
\text{EFT below }M_2
\to
\text{EFT below }M_3.
$$

This staged procedure avoids large logarithms such as $\log(M_1/M_3)$ in fixed-order threshold corrections. Those logarithms are resummed by running between thresholds.

If two thresholds are not well separated, one can match them together. There is no virtue in inventing artificial scale separation. The useful rule is:

$$
\text{separate thresholds only when the logarithms between them are worth resumming.}
$$

In realistic theories, thresholds may be fuzzy: particles can be unstable, masses may be split inside multiplets, or symmetry breaking may mix fields. Then the matching calculation must use the physical assumptions appropriate to the process. EFT is systematic; it is not mindless.

## Thresholds in mass-independent schemes

Mass-independent schemes such as MS and $\overline{\mathrm{MS}}$ are convenient because beta functions have simple algebraic structure. But they do not automatically decouple heavy particles from the running of couplings at low scales. A heavy field can keep contributing to a beta function even when $\mu\ll M$ unless one changes to a low-energy EFT where that field is removed.

This is why threshold matching is not optional in mass-independent schemes. The full-theory coupling and the EFT coupling are different coordinates:

$$
g_{>} (\mu)
\quad\text{is not the same coordinate as}\quad
 g_{<}(\mu).
$$

The relation between them is fixed by matching. Once the heavy field is removed, low-energy running is governed only by the light degrees of freedom.

In a physical momentum-subtraction scheme, heavy-particle effects can decouple more automatically from low-momentum running. The price is that beta functions and finite parts become more mass dependent and less universal. This is a tradeoff of coordinates, not a disagreement about physics.

## A worked toy threshold

Consider a full theory with a light scalar $\phi$ and a heavy scalar $H$:

$$
\mathcal L
=\frac12(\partial\phi)^2-\frac12m^2\phi^2
+\frac12(\partial H)^2-\frac12M^2H^2
-\frac{\kappa}{4}\phi^2 H^2.
$$

At energies $Q\ll M$, $H$ is absent from the EFT. However, an $H$ loop shifts the light scalar mass. The full-theory self-energy contains a tadpole integral of the form

$$
\Pi_H(0)
\propto
\kappa\,\mu^{2\epsilon}
\int\frac{d^d k}{(2\pi)^d}\frac{i}{k^2-M^2+i\epsilon}.
$$

After renormalization, the finite threshold contribution is of order

$$
\Delta m^2_{\text{th}}
\sim
\frac{\kappa M^2}{16\pi^2}
\left[a+b\log\frac{\mu_M^2}{M^2}\right],
$$

where $a$ and $b$ depend on conventions and scheme. The EFT below $M$ contains only $\phi$, with a mass parameter

$$
m_{<}^2(\mu_M)=m_{>}^2(\mu_M)+\Delta m^2_{\text{th}}(\mu_M).
$$

The low-energy mass is not obtained by simply deleting $H$ from the Lagrangian. Deleting $H$ changes the degrees of freedom; matching transfers its virtual effects into low-energy parameters.

## Common pitfalls

**Confusing matching with running.** Running changes parameters inside one theory. Matching relates two different EFT descriptions.

**Matching far from the threshold.** Choosing $\mu_M$ far from $M$ produces large logarithms in the threshold correction. The point of RG is to avoid that.

**Assuming couplings must be continuous.** A coupling is a coordinate. Coordinates can jump when the chart changes. Observables must agree.

**Forgetting the EFT loop subtraction.** At loop level, the full theory and EFT share light-region physics. Matching keeps the hard local difference, not the entire full-theory loop.

**Ignoring power-sensitive thresholds.** Heavy particles can shift relevant operators by powers of their mass. Dimensional regularization does not make this physical issue disappear.

**Integrating out split multiplets carelessly.** If a symmetry relates fields with different masses, threshold corrections can encode symmetry breaking. The low-energy theory must respect the symmetries that remain, not the ones one wishes were still manifest.

## Relations to other pages

[Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/) and [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/) explain how the matching calculation is performed. This page focuses on what happens when that matching occurs at a physical threshold.

[Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/) explains the path-integral and classical operations that remove heavy fields. [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) explains evolution below the threshold. [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/) explains why heavy physics is local at low energies. [Naturalness in Wilsonian Language](/renormalization-rg-eft/naturalness-power-counting/naturalness-in-wilsonian-language/) develops the power-sensitive side of threshold corrections.

## Research status

The concept of threshold matching is settled. It is used routinely in QCD, electroweak EFT, flavor EFTs, heavy-quark EFT, nonrelativistic EFTs, supersymmetric EFTs, gravitational EFT, and condensed-matter effective descriptions.

The technical frontier is precision and automation. Multi-loop threshold corrections, gauge-covariant matching, evanescent-operator effects, large operator bases, thresholds in theories with spontaneous symmetry breaking, and mixed-scale problems can be very demanding. The underlying principle is simple; the bookkeeping can be a swamp with tenure.

## Exercises

### Exercise 1: Matching-scale cancellation

Let

$$
\beta_g=-\frac{b}{16\pi^2}g^3,
\qquad
\mu\frac{d}{d\mu}\frac1{g^2}=\frac{b}{8\pi^2}.
$$

Suppose $b_{>}=b_{<}+b_H$. Show that the threshold relation

$$
\frac1{g_{<}^2(\mu_M)}=\frac1{g_{>}^2(\mu_M)}-\frac{b_H}{8\pi^2}\log\frac{\mu_M}{M}
$$

has the correct $\mu_M$ dependence at this order.

<details><summary><strong>Solution</strong></summary>

Differentiate the matching relation with respect to $\log\mu_M$:

$$
\mu_M\frac{d}{d\mu_M}\frac1{g_{<}^2}
=
\mu_M\frac{d}{d\mu_M}\frac1{g_{>}^2}
-\frac{b_H}{8\pi^2}.
$$

Using the high-energy RGE gives

$$
\mu_M\frac{d}{d\mu_M}\frac1{g_{<}^2}
=\frac{b_{>}}{8\pi^2}-\frac{b_H}{8\pi^2}
=\frac{b_{<}}{8\pi^2}.
$$

Thus the explicit logarithm in the threshold relation converts the high-energy slope into the low-energy slope.

</details>

### Exercise 2: Why match near the heavy mass?

A one-loop threshold relation contains $\log(\mu_M^2/M^2)$. Compare the size of this logarithm for $\mu_M=M$, $\mu_M=10M$, and $\mu_M=M/10$. What does this say about the preferred matching scale?

<details><summary><strong>Solution</strong></summary>

For $\mu_M=M$,

$$
\log\frac{\mu_M^2}{M^2}=0.
$$

For $\mu_M=10M$,

$$
\log\frac{\mu_M^2}{M^2}=\log 100\approx 4.6.
$$

For $\mu_M=M/10$,

$$
\log\frac{\mu_M^2}{M^2}=\log 10^{-2}\approx -4.6.
$$

The logarithm is small near $M$ and large when the matching scale is far from $M$. Large logarithms should be produced by RG running between separated scales, not left inside a fixed-order threshold correction.

</details>

### Exercise 3: Power sensitivity of a scalar mass

A heavy scalar of mass $M$ couples to a light scalar through $\kappa\phi^2H^2$. Use dimensional analysis to explain why the one-loop threshold correction to $m_\phi^2$ is proportional to $\kappa M^2/(16\pi^2)$ times a dimensionless function of $\mu/M$.

<details><summary><strong>Solution</strong></summary>

The correction is one-loop, so it carries the loop factor $1/(16\pi^2)$. It is proportional to $\kappa$ because one insertion of the interaction is needed. The quantity being corrected is a mass squared, so the correction must have mass dimension two. After the heavy field is removed, the only heavy scale available is $M$, so the correction has the form

$$
\Delta m_\phi^2
=\frac{\kappa M^2}{16\pi^2}
F\left(\frac{\mu}{M}\right),
$$

where $F$ is dimensionless and may contain constants and logarithms. This is the threshold version of scalar-mass sensitivity to heavy physics.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the discussion of RG methods, mass effects, minimal subtraction, and effective theories.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalization, nonrenormalizable theories, RG, and EFT applications.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on decoupling, matching, Wilson actions, and power counting.
- Aneesh V. Manohar, EFT lecture notes, for practical matching, running, threshold, and operator-basis methods.
- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian viewpoint on changing descriptions across scales.

## Version history

- 2026-06-18: First polished draft. Added threshold matching relation, matching-scale cancellation, gauge-coupling example, scalar mass threshold discussion, and exercises.
