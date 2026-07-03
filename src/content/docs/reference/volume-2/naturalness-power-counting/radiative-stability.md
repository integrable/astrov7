---
title: "Radiative Stability"
description: "A scale-aware explanation of radiative stability: when small parameters, hierarchies, and EFT power counting survive quantum corrections and threshold matching."
sidebar:
  label: "Radiative Stability"
  order: 5
level: Graduate
status: "Polished draft"
source: "'t Hooft naturalness criterion; Wilson and Kogut 1974; Coleman 1985, dilatations and renormalization lectures; Srednicki 2007, RG and EFT sections; Schwartz 2014, chs. 21–23; Burgess 2020, chs. 2–4 and 9–10."
topics:
  - radiative stability
  - naturalness
  - threshold corrections
  - technical naturalness
  - Wilsonian EFT
canonicalTopics:
  - radiative-stability
  - naturalness
  - threshold-sensitivity
researchStatus:
  established:
    - "Radiative stability is the standard EFT requirement that assumed small parameters and hierarchies remain small under loop corrections and matching, without repeated unexplained cancellations."
  active:
    - "Which radiatively unstable parameters demand new dynamics, environmental selection, or no explanation remains an active interpretive question in particle physics and cosmology."
---

## Summary

A parameter is **radiatively stable** if quantum corrections do not destroy the size one assumed for it. If a low-energy parameter $p$ is small, the first question is not whether one can choose a bare parameter to reproduce it. One usually can. The sharper question is whether the smallness of $p$ survives loops and heavy thresholds without re-adjusting unrelated large numbers order by order.

The stable pattern is multiplicative:

$$
\frac{dp}{dt}=\text{dimensionless factors}\times p,
$$

where $t$ is an RG time such as $t=\log\mu$ in a renormalized description. Then $p=0$ is preserved by the flow. Small values remain small up to logarithms and dimensionless factors.

The unstable pattern is additive:

$$
p_{\text{low}}=p_{\text{bare}}+\frac{c}{16\pi^2}M^{[p]}+\text{smaller terms},
$$

where $M$ is a heavy physical threshold and $[p]$ is the mass dimension of $p$. If $p_{\text{low}}\ll M^{[p]}$, the small observed value requires a cancellation unless a symmetry, dynamics, or selection principle explains why the additive term is absent or small.

:::note[The practical test]
A hierarchy is radiatively stable when all corrections to the small quantity are controlled by the same small parameters, symmetries, or power counting that made it small in the first place.
:::

## Prerequisites

You should know [Technical Naturalness](/renormalization-rg-eft/naturalness-power-counting/technical-naturalness/), [Hierarchy Problem](/renormalization-rg-eft/naturalness-power-counting/hierarchy-problem/), [Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/dimensional-analysis/), [Naive Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/naive-dimensional-analysis/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), and [Running Masses](/renormalization-rg-eft/renormalization-group-equations/running-masses/).

It is useful, but not required, to have read [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/). Radiative stability is easiest to visualize as stability of a trajectory or surface in theory space.

## Core idea

Radiative stability asks whether an EFT estimate is self-consistent after quantum effects are included.

Suppose a low-energy EFT contains

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{main}}+p\mathcal O_p+\cdots,
$$

with $p$ assumed to be small compared with the scale suggested by dimensional analysis. The value of $p$ measured at low energy comes from at least three sources:

$$
p_{\text{low}}
=
\text{UV boundary value}
+
\text{threshold corrections}
+
\text{running inside the EFT}.
$$

Radiative stability is the demand that these terms do not have to conspire mysteriously. If $p$ is small because a symmetry is restored at $p=0$, then loops must respect that symmetry and corrections to $p$ are proportional to $p$ or to controlled symmetry-breaking spurions. If $p$ is small with no such reason, heavy physics can generate additive corrections of the natural size allowed by locality and symmetry.

The slogan is:

$$
\text{small input}
\xrightarrow{\text{loops and matching}}
\text{small output}
$$

only when the smallness is protected by a rule that quantum corrections also obey.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Radiative stability map comparing protected multiplicative corrections with unprotected additive heavy-threshold corrections](/figures/renormalization-rg-eft/radiative-stability-flow-map.svg)

<figcaption>

Radiative stability separates two kinds of quantum correction. In a protected lane, counterterms carry the same small spurion as the parameter, so $p=0$ is stable and $\delta p\propto p$. In an unprotected lane, heavy thresholds can generate additive local terms of order $M^{[p]}$, so a much smaller $p_{\text{low}}$ requires cancellation or a new explanation.

</figcaption>
</figure>

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). In particular:

| Symbol | Meaning |
|---|---|
| $Q$ | low external momentum or physical measurement scale |
| $\mu$ | renormalization scale |
| $\Lambda$ | cutoff or Wilsonian scale |
| $M$ | heavy mass threshold |
| $p$ | a small parameter or coefficient being tested |
| $\Delta p$ | a quantum or threshold correction to $p$ |

A radiative correction is any loop-generated correction to a parameter, operator coefficient, matrix element, or observable. In EFT discussions, it is important to distinguish two related but different effects:

| Effect | What changes | Typical formula |
|---|---|---|
| Running | coefficients vary with $\mu$ inside a fixed EFT | $\mu dC_i/d\mu=\gamma_i{}^j C_j$ |
| Matching | coefficients jump when heavy degrees of freedom are removed | $C_i^{\text{below}}(M)=C_i^{\text{above}}(M)+\Delta C_i^{\text{thr}}$ |

Running often produces logarithms. Matching can produce finite power-sized threshold corrections. Naturalness problems are usually about threshold sensitivity and relevant operators, not merely about logarithmic running.

## What radiative stability tests

Radiative stability tests an assumption about sizes. The assumption might be:

| Assumption | Radiative-stability question |
|---|---|
| $m_f\ll M$ for a fermion | Do loops generate $m_f\sim M$, or only corrections proportional to $m_f$? |
| $m_\theta^2\ll M^2$ for a pseudo-Goldstone boson | Are corrections proportional to symmetry-breaking spurions? |
| $m_{\text{s}}^2\ll M^2$ for a generic scalar | Do heavy thresholds generate additive $M^2$ corrections? |
| $C_i\sim O(1)$ in an EFT expansion | Do loops generate coefficients larger than the assigned power counting? |
| $\theta\ll1$ for a mixing angle | Does a symmetry appear when $\theta=0$? |
| $\rho_{\text{vac}}\ll M^4$ for vacuum energy | Is there any symmetry or dynamics forcing additive contributions to cancel? |

The answer depends on the full quantum theory: field content, exact symmetries, regulator, anomaly structure, matching scale, and which parameters are independent.

## Multiplicative stability

The cleanest stable case is multiplicative renormalization. Suppose $p=0$ is an invariant surface in theory space. Then the beta function has the form

$$
\beta_p(g,p)\equiv \mu\frac{dp}{d\mu}
=
\gamma_p(g)p+O(p^2).
$$

Solving at leading order gives

$$
p(\mu)=p(\mu_0)
\exp\left[
\int_{\mu_0}^{\mu}\frac{d\mu'}{\mu'}\gamma_p(g(\mu'))
\right].
$$

If $p(\mu_0)=0$, then $p(\mu)=0$. If $p(\mu_0)$ is small, it remains small unless the exponential contains enormous RG time or strong dynamics.

This is the pattern behind technical naturalness. The small parameter is allowed to run, but it is not generated from nothing.

### Example: fermion masses

For a Dirac fermion, the mass term

$$
\mathcal L_m=-m\bar\psi\psi
$$

breaks chiral symmetry. In the limit $m\to0$, the theory has an enhanced chiral symmetry, up to anomalies and other explicit breakings. Therefore the mass beta function has the form

$$
\mu\frac{dm}{d\mu}=\gamma_m(g)m.
$$

Loops do not generate a Dirac mass unless the chiral symmetry is broken. A small fermion mass is radiatively stable, even if it is unexplained as a numerical pattern.

### Example: pseudo-Goldstone masses

If a scalar is a Goldstone boson of a spontaneously broken approximate symmetry, the exact symmetry limit forbids a potential. A small explicit breaking spurion $\epsilon$ can generate

$$
m_\theta^2\sim \epsilon f^2
$$

or the appropriate low-energy analogue. Loops can renormalize the coefficient, but they must carry the same symmetry-breaking spurion. The small mass is stable because the shift symmetry is restored when $\epsilon=0$.

## Additive threshold sensitivity

The dangerous case is additive correction from a heavy threshold. Consider two real scalars,

$$
\mathcal L
=
\frac12(\partial\phi)^2-\frac12m^2\phi^2
+\frac12(\partial H)^2-\frac12M^2H^2
-\frac{\lambda}{4}\phi^2H^2,
$$

with $M\gg m$. Integrating out $H$ generates a local correction to the light scalar mass. The precise finite part depends on scheme and matching convention, but dimensional analysis and locality allow

$$
\Delta m^2\sim \frac{\lambda}{16\pi^2}M^2.
$$

This is not merely a story about a cutoff. The heavy particle is physical. After it is removed from the EFT, its effect remains in Wilson coefficients of local light-field operators.

If $m_{\text{low}}^2\ll M^2$, the matching equation has the schematic form

$$
m_{\text{low}}^2
=
m_{\text{bare or UV}}^2
+
\frac{\lambda}{16\pi^2}M^2
+
\cdots.
$$

Unless a symmetry or structure sets the two large terms in relation, the small output requires cancellation.

## Running is not the same as matching

A common mistake is to inspect an RG equation below $M$ and conclude that the heavy scale has disappeared. It has disappeared from running, not from boundary data.

Below the heavy threshold, the EFT may have

$$
\mu\frac{dm^2}{d\mu}=\gamma_m m^2.
$$

This looks multiplicative. But the value of $m^2$ just below the threshold was fixed by matching:

$$
m^2(M^-) = m^2(M^+) + \Delta m^2_{\text{thr}}.
$$

If

$$
\Delta m^2_{\text{thr}}\sim \frac{\lambda}{16\pi^2}M^2,
$$

then the low-energy parameter remembers the heavy scale through its boundary condition. Decoupling says that heavy particles affect low-energy amplitudes through local operators suppressed by powers of $Q/M$ or through renormalized lower-dimension parameters. It does not say that heavy particles cannot affect relevant light-sector parameters.

## Regulator language and physical language

In a hard-cutoff calculation one may write

$$
\Delta m^2\sim \frac{\lambda}{16\pi^2}\Lambda^2.
$$

In dimensional regularization, power divergences may not appear as explicit $\Lambda^2$ terms. This does not settle the radiative-stability question. The physical question is whether there are heavy thresholds or UV boundary conditions that generate the same allowed local operator.

The safest language is:

$$
\text{radiative instability}
\neq
\text{mere presence of a regulator-dependent power divergence}.
$$

Instead,

$$
\text{radiative instability}
=
\text{small coefficient sensitive to larger independent physical scales}.
$$

Cutoff formulas are useful diagnostics when interpreted Wilsonianly. They become misleading when read as literal observables.

## Wilsonian geometry

In Wilsonian language, radiative stability is a statement about flows and submanifolds in theory space.

If $p=0$ is protected by a symmetry, then the surface $p=0$ is invariant under RG flow. Starting near it remains near it. That is a stable hierarchy.

If $p=0$ is not protected, then integrating out modes can move the theory away from $p=0$ by an amount set by the cutoff or by heavy thresholds. Keeping $p$ small requires choosing the UV trajectory to land close to a thin target surface in the IR.

Relevant operators make this especially sharp. A small coefficient of a relevant operator in the IR can correspond to a very special UV boundary condition. Critical phenomena make this familiar: to reach a critical point, the temperature must be tuned. Particle-physics hierarchy problems ask whether similarly special conditions are explained by symmetry or dynamics.

## Comparison of common cases

| Quantity | Protected limit | Stable pattern | Comments |
|---|---|---|---|
| Dirac fermion mass $m$ | chiral symmetry at $m=0$ | $\delta m\propto m$ | technically natural |
| Gauge boson mass | gauge symmetry at $m_A=0$ | forbidden unless symmetry broken | depends on gauge realization |
| Goldstone mass | shift symmetry in exact limit | $m^2\propto$ explicit breaking | pseudo-Goldstone logic |
| Generic scalar mass $m^2$ | usually none | $\delta m^2\sim M^2$ allowed | hierarchy problem prototype |
| Vacuum energy $\rho$ | usually none in nongravitational EFT | $\delta\rho\sim M^4$ allowed | becomes physical with gravity |
| Irrelevant EFT coefficient $C/M^k$ | locality and power counting | suppressed by powers of $Q/M$ | stable after correct basis choice |

The table is schematic. The actual answer can change if additional symmetry, supersymmetry, compositeness, dimensional transmutation, large-$N$ structure, sequestering, or other dynamics is present.

## Radiative stability and predictivity

A radiatively unstable theory can still be predictive. Once its parameters are measured, it may accurately predict other observables. Radiative instability is not a failure of calculation. It is a statement about explanatory economy and sensitivity to short-distance input.

For example, if an EFT contains a scalar mass parameter $m^2$, one can measure $m^2$ and compute low-energy scattering. That is perfectly legitimate. The naturalness question is different: why is $m^2$ so much smaller than heavy scales that couple to it?

This distinction matters because EFTs are not required to be natural in order to be useful. The Fermi theory of weak interactions is nonrenormalizable and perfectly useful below the weak scale. Its coefficients are organized by powers of $Q/M_W$. Nonrenormalizable does not mean unstable. Radiatively unstable means that a low-dimensional coefficient is smaller than corrections that the theory allows.

## Common pitfalls

**Using divergence language as if it were observable language.** A quadratic divergence can be a useful diagnostic, but physical radiative instability is about heavy thresholds and UV sensitivity.

**Forgetting matching.** A multiplicative RG equation below a heavy scale does not erase additive threshold corrections at that scale.

**Assuming small means unstable.** Small fermion masses, small symmetry-breaking spurions, and small Goldstone masses can be radiatively stable.

**Assuming stable means explained.** Technical naturalness explains why smallness persists. It does not necessarily explain why the symmetry-breaking spurion has the value it has.

**Confusing scheme dependence with non-existence.** Individual counterterms and finite pieces are scheme dependent. Whether an allowed relevant operator is sensitive to heavy physical thresholds is not removed by changing schemes.

**Counting correlated parameters as independent.** If UV dynamics enforces a relation among parameters, an apparent cancellation may be physical rather than tuned.

**Applying the test without checking anomalies.** A symmetry that is broken by the quantum measure cannot protect a parameter in the ordinary way.

## Relations to other pages

[Technical Naturalness](/renormalization-rg-eft/naturalness-power-counting/technical-naturalness/) gives the symmetry criterion behind many radiatively stable small parameters. [Hierarchy Problem](/renormalization-rg-eft/naturalness-power-counting/hierarchy-problem/) applies the instability logic to scalar masses and heavy thresholds. [Fine-Tuning](/renormalization-rg-eft/naturalness-power-counting/fine-tuning/) discusses how to quantify cancellations once radiative instability is present.

[Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/), and [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/) give the practical calculation language. [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) and [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) give the Wilsonian geometry behind the diagnostic.

## Research status

The technical concept of radiative stability is established. It is part of the standard EFT vocabulary used to diagnose whether small coefficients are stable under loops, matching, and RG flow.

The interpretation is active. In particular, the significance of radiative instability for the Higgs mass, the cosmological constant, axion quality, inflationary potentials, dark-sector hierarchies, and quantum-gravity constraints remains debated. The technical calculation is often clear; the conclusion one draws about unknown UV physics is not dictated by EFT alone.

## Exercises

### Exercise 1: Multiplicative flow

Let $p$ obey

$$
\mu\frac{dp}{d\mu}=\gamma p,
$$

where $\gamma$ is constant. Solve for $p(\mu)$ in terms of $p(\mu_0)$. What happens if $p(\mu_0)=0$?

<details><summary><strong>Solution</strong></summary>

Write $t=\log\mu$. Then

$$
\frac{dp}{dt}=\gamma p.
$$

The solution is

$$
p(t)=p(t_0)e^{\gamma(t-t_0)}.
$$

Equivalently,

$$
p(\mu)=p(\mu_0)\left(\frac{\mu}{\mu_0}\right)^\gamma.
$$

If $p(\mu_0)=0$, then $p(\mu)=0$ at all scales. This is the basic mathematical form of a protected surface.

</details>

### Exercise 2: Heavy scalar threshold estimate

A light scalar $\phi$ couples to a heavy scalar $H$ through

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4}\phi^2H^2,
\qquad M_H=M.
$$

Use dimensional analysis and the loop factor to estimate the correction to the coefficient of $\phi^2$ after integrating out $H$.

<details><summary><strong>Solution</strong></summary>

The operator $\phi^2$ has coefficient with mass dimension two. The heavy scalar provides the physical scale $M$, and the one-loop diagram with an $H$ loop carries a loop factor. Therefore the threshold correction has the schematic form

$$
\Delta m_\phi^2\sim \frac{\lambda}{16\pi^2}M^2.
$$

The coefficient and finite scheme-dependent terms depend on the precise matching prescription, but the scaling with $M^2$ is the radiative-stability issue.

</details>

### Exercise 3: Running versus matching

Suppose below a threshold $M$ a scalar mass obeys

$$
\mu\frac{dm^2}{d\mu}=\gamma m^2.
$$

At the threshold,

$$
m^2(M^-)=m^2(M^+)+cM^2.
$$

Explain why the multiplicative running below $M$ does not imply radiative stability if $m^2(M^-)\ll M^2$.

<details><summary><strong>Solution</strong></summary>

The running below $M$ says that once the low-energy EFT is specified, $m^2=0$ is stable under the low-energy RG equation. But the boundary value of the EFT parameter is set by matching at $M$.

If $cM^2$ is much larger than the desired low-energy value, then $m^2(M^+)$ and $cM^2$ must cancel to high accuracy. The instability is in the threshold boundary condition, not in the subsequent low-energy running.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian view of relevant operators, flows, and UV sensitivity.
- Gerard 't Hooft, "Naturalness, chiral symmetry, and spontaneous chiral symmetry breaking," for the symmetry criterion for stable small parameters.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," "Renormalization and Symmetry," and "Secret Symmetry."
- Mark Srednicki, *Quantum Field Theory*, especially the renormalization group and effective field theory chapters.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, scalar masses, and naturalness.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the RG methods and EFT sections.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, matching, symmetries, and naturalness.

## Version history

- 2026-06-18: First polished draft. Added radiative-stability definition, protected versus additive correction patterns, threshold/running distinction, examples, Wilsonian interpretation, exercises, and figure.
