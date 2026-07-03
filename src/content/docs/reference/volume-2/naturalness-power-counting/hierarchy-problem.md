---
title: "Hierarchy Problem"
description: "A scale-aware explanation of the hierarchy problem as radiative sensitivity of relevant scalar operators to heavy thresholds, not merely a cutoff artifact."
sidebar:
  label: "Hierarchy Problem"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; 't Hooft naturalness criterion; Coleman 1985; Srednicki 2007, RG and EFT sections; Schwartz 2014, chs. 21–23; Burgess 2020, naturalness and EFT chapters."
topics:
  - hierarchy problem
  - scalar masses
  - radiative stability
  - threshold corrections
  - naturalness
canonicalTopics:
  - hierarchy-problem
  - scalar-naturalness
  - threshold-sensitivity
researchStatus:
  established:
    - "In Wilsonian EFT, a generic scalar mass is a relevant operator and is sensitive to heavy thresholds unless protected by a symmetry or structure."
  active:
    - "The physical interpretation of the electroweak hierarchy problem, and which mechanism if any explains it, remains an active frontier question."
---

## Summary

The hierarchy problem is the question of why a relevant scalar mass scale is much smaller than other scales to which it is coupled. In particle physics the canonical example is the electroweak scale: the Higgs mass parameter is far below possible heavy scales such as a grand-unification scale, a seesaw scale, or the Planck scale.

The sharp EFT version is not simply “quadratic divergences exist.” A hard cutoff can display the problem as

$$
\delta m_H^2\sim \frac{\lambda}{16\pi^2}\Lambda^2.
$$

But the real issue is physical threshold sensitivity. If a light scalar couples to a heavy particle of mass $M$, matching across that heavy threshold generically produces

$$
\delta m_H^2\sim \frac{g^2}{16\pi^2}M^2
$$

up to constants, signs, and logarithms. Dimensional regularization can hide cutoff power divergences, but it cannot hide the fact that heavy particles can generate relevant scalar operators.

A hierarchy is not impossible. It can be protected by a symmetry, explained by dynamics, selected by environmental conditions, or simply accepted as a tuning. The hierarchy problem is the demand to know which of these, if any, is the right description.

:::note[One-sentence version]
The hierarchy problem is the radiative instability of an allowed relevant scalar operator when the scalar is coupled to much heavier physics.
:::

## Prerequisites

You should know [Technical Naturalness](/renormalization-rg-eft/naturalness-power-counting/technical-naturalness/), [Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/dimensional-analysis/), [Cutoff versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/).

Readers who want the Wilsonian geometry should also review [Relevant, Irrelevant, and Marginal Operators](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) and [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/).

## Core idea

A scalar mass term is a relevant operator. In four dimensions,

$$
\mathcal L\supset -m^2\phi^\dagger\phi,
\qquad
[\phi^\dagger\phi]=2,
\qquad
[m^2]=2.
$$

If the scalar couples to a heavy sector with mass scale $M$, the coefficient $m^2$ can receive corrections proportional to $M^2$. This is allowed by dimensional analysis and by symmetries unless a protection mechanism forbids it.

The contrast with fermions is instructive. A fermion mass term breaks chiral symmetry, so the limit $m_f\to0$ is symmetry-enhanced. Quantum corrections are proportional to $m_f$. A generic scalar mass term does not break such a symmetry. If $m^2=0$ does not restore an exact quantum symmetry, nothing prevents additive corrections.

This is the hierarchy problem in its cleanest form:

$$
\text{light scalar} + \text{heavy coupled physics}
\quad\Longrightarrow\quad
\text{large allowed threshold correction to }m^2.
$$

The problem is not that a small scalar mass cannot be written. It is that maintaining it requires a special explanation when heavy coupled scales exist.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Hierarchy problem map: a heavy threshold produces an allowed scalar mass correction, forcing cancellation or a protection mechanism to keep the low scale small](/figures/renormalization-rg-eft/hierarchy-threshold-sensitivity.svg)

<figcaption>

A generic scalar mass operator is allowed by the low-energy symmetries. Heavy thresholds therefore generate local corrections of order $M^2$. A low scalar mass can survive, but the EFT asks whether this is protected, dynamically explained, environmentally selected, or tuned.

</figcaption>
</figure>

## Setup and conventions

This page uses $M$ for a heavy scale, $Q$ for a low external scale, $\mu$ for a renormalization scale, and $\Lambda$ for a cutoff or Wilsonian scale. The distinction matters.

The word hierarchy means a large ratio of physical scales, for example

$$
\frac{M}{m}\gg1.
$$

A hierarchy is not automatically a problem. The proton-electron mass ratio is large, but it is not the same kind of problem as an unprotected elementary scalar mass. The issue is whether the smaller scale is stable under quantum corrections from the larger scale.

For the Standard Model Higgs sector, write schematically

$$
V(H)=-m_H^2 H^\dagger H+\lambda(H^\dagger H)^2.
$$

When $m_H^2>0$ in this convention, electroweak symmetry breaks and

$$
v^2=\frac{m_H^2}{\lambda},
\qquad
m_h^2=2\lambda v^2=2m_H^2.
$$

The hierarchy question is why $m_H^2$ is small compared with any much larger physical scale that couples to $H$.

## Cutoff language and its limits

In a cutoff calculation in a scalar theory, a one-loop self-energy often produces

$$
\delta m^2\sim \frac{\lambda}{16\pi^2}\Lambda^2.
$$

This formula is useful because it shows a Wilsonian fact: relevant operators are sensitive to short distances. If the EFT is defined only below a cutoff $\Lambda$, then the low-energy scalar mass must be chosen as a boundary condition with precision set by the desired low mass.

However, the cutoff formula is also easy to misuse. If $\Lambda$ is merely a regulator that will be removed, then $\Lambda^2$ itself is not an observable. A calculation in dimensional regularization may contain no explicit quadratic divergence. One should not conclude from this that the hierarchy problem has vanished.

The regulator-independent question is:

> What happens when there are actual heavy degrees of freedom with mass $M$ that couple to the scalar?

That question is answered by matching, not by arguing about regulator aesthetics.

## Heavy thresholds are physical

Consider a light real scalar $\phi$ and a heavy real scalar $S$:

$$
\mathcal L\supset
\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
+\frac12\partial_\mu S\partial^\mu S
-\frac12M^2S^2
-\frac{\kappa}{4}\phi^2S^2.
$$

At one loop, the heavy field contributes to the light scalar two-point function. The correction to $m^2$ has the schematic form

$$
\delta m^2
\sim
\frac{\kappa}{16\pi^2}M^2
\left[\log\frac{M^2}{\mu^2}+\text{scheme-dependent constant}\right].
$$

The precise finite constant depends on the subtraction convention, but the existence of an $M^2$ threshold contribution does not. If $M\gg m$, then keeping $m^2$ small requires either

$$
m_{\text{bare}}^2+\delta m^2\ll M^2,
$$

or a reason that $\delta m^2$ is absent or suppressed.

This is the important replacement for loose talk about quadratic divergences:

$$
\text{cutoff sensitivity as a warning}
\quad\longrightarrow\quad
\text{heavy-threshold sensitivity as the physical issue}.
$$

## Why scalars are special

The hierarchy problem is not that every relevant operator is equally mysterious. The protection mechanisms differ by spin and symmetry.

| Parameter | Operator | Small limit | Technical status |
|---|---|---|---|
| fermion mass $m_f$ | $m_f\bar\psi\psi$ | chiral symmetry restored | usually technically natural |
| gauge-boson mass $m_A$ | $m_A^2A_\mu A^\mu$ | gauge structure restored | protected if gauge invariance exact |
| Goldstone mass $m_\pi$ | $m_\pi^2\pi^2$ | shift symmetry restored | technically natural if explicit breaking is small |
| generic scalar mass $m^2$ | $m^2\phi^\dagger\phi$ | no generic exact symmetry restored | not protected |

An elementary scalar field can be light if protected by a special structure. But absent that structure, its mass term is simply allowed. In Wilsonian EFT, allowed relevant operators are expected to be generated by short-distance physics.

## The electroweak hierarchy

The Standard Model contains a scalar doublet $H$. The operator

$$
H^\dagger H
$$

is gauge invariant and relevant. Its coefficient controls the electroweak scale. If the Standard Model is valid up to a much higher scale and if heavy physics at that scale couples to the Higgs, then matching generically contributes to $m_H^2$ by amounts of order the heavy scale squared times loop factors.

For example, a heavy particle of mass $M$ with coupling strength $g$ to the Higgs generically gives

$$
\delta m_H^2\sim \frac{g^2}{16\pi^2}M^2.
$$

If $M$ is many orders of magnitude above the electroweak scale, then the bare or short-distance contribution must cancel the threshold contribution to high precision to leave the observed weak scale. The precision of the cancellation scales roughly as

$$
\frac{m_H^2}{M^2}.
$$

This is the electroweak hierarchy problem.

The problem can be phrased without assuming a specific heavy particle. In theory space, the Standard Model sits close to the critical surface separating the electroweak-symmetric phase from the electroweak-broken phase. The question is why the Higgs mass parameter is so close to criticality compared with possible microscopic scales.

## A Wilsonian picture: tuning to a critical surface

In statistical physics, reaching a second-order critical point requires tuning a relevant parameter such as temperature:

$$
t\equiv \frac{T-T_c}{T_c}\to0.
$$

The correlation length then becomes much larger than the microscopic scale:

$$
\xi\gg a.
$$

This is not paradoxical because the experimenter can tune $T$. The critical point is a codimension-one surface in parameter space.

A light scalar in QFT is analogous. If the scalar mass is much smaller than a microscopic scale, the theory is close to a critical surface. In condensed matter this closeness is controlled externally. In particle physics the parameters are just what they are, so the naturalness question becomes:

> What dynamical, symmetry, environmental, or structural reason places the theory close to the critical surface?

This Wilsonian phrasing avoids regulator drama. It says the hierarchy problem is about why a relevant deformation is small relative to the scale where the effective description is born.

## Quadratic divergences versus matching: a comparison

The following table is the sanity-preserving version of the issue.

| Language | What it shows | What it can obscure |
|---|---|---|
| Hard cutoff | Scalar masses are sensitive to short-distance modes as $\Lambda^2$. | A cutoff regulator may be mistaken for a physical heavy scale. |
| Dimensional regularization | Logarithmic running and scheme dependence are handled cleanly. | Power sensitivity to heavy thresholds may be hidden if no heavy mass is included. |
| Wilsonian EFT | Relevant operators must be tuned near critical surfaces unless protected. | Requires specifying the UV scale or microscopic theory. |
| Matching | Physical heavy particles generate finite threshold corrections. | Precise finite parts are scheme and convention dependent. |

A good hierarchy-problem discussion should be able to move between all four languages without changing the physics.

## Known classes of responses

This page is not a BSM model review, but the main logical responses are worth naming.

| Response | Basic idea | What protects or explains the small scale? |
|---|---|---|
| Supersymmetry | Boson and fermion loops cancel in protected limits. | Symmetry relating scalar and fermion masses. |
| Composite Higgs | The Higgs is not elementary above a compositeness scale. | New dynamics; often approximate Goldstone symmetry. |
| Pseudo-Goldstone Higgs | The Higgs mass is controlled by explicit symmetry breaking. | Approximate shift symmetry. |
| Low cutoff or new thresholds nearby | The EFT stops before large corrections accumulate. | No very high coupled scale. |
| Classical scale symmetry | Mass terms absent at classical level. | Requires care: quantum anomalies and thresholds matter. |
| Environmental selection | Different regions or vacua scan parameters. | Selection conditions rather than ordinary technical protection. |
| Acceptance of tuning | The small number is a boundary condition. | No protection; tuning is allowed but unexplained. |

Each response has costs. Supersymmetry must be broken. Composite models must satisfy precision constraints. Environmental reasoning needs a measure and a landscape. Classical scale symmetry must confront quantum thresholds. Accepting tuning is logically consistent but gives up the naturalness demand.

## What the hierarchy problem is not

It is not a proof that new particles must appear at a particular energy. EFT can diagnose sensitivity, but it cannot force nature to provide a protection mechanism within experimental reach.

It is not merely a dislike of small numbers. Small numbers are common and often natural. The question is whether a small number is stable under the interactions and thresholds present in the theory.

It is not solved by choosing a regulator in which quadratic divergences are absent. The physical question is threshold sensitivity to actual heavy scales.

It is not a contradiction in the Standard Model. The Standard Model can be renormalized and used to make predictions. The hierarchy problem is about the interpretation of its scalar mass parameter in relation to higher scales.

## A toy matching calculation

Suppose the low-energy scalar mass after matching is

$$
m_{\text{low}}^2=m_{\text{short}}^2+\frac{\kappa}{16\pi^2}M^2.
$$

If the desired low mass satisfies $m_{\text{low}}^2\ll M^2$, then the short-distance parameter must be chosen so that

$$
m_{\text{short}}^2\approx -\frac{\kappa}{16\pi^2}M^2
$$

with a residual mismatch of order $m_{\text{low}}^2$. A rough tuning measure is

$$
\Delta^{-1}\sim \frac{m_{\text{low}}^2}{|\delta m^2|}
\sim
\frac{16\pi^2m_{\text{low}}^2}{\kappa M^2}.
$$

This is not a probability. It is a sensitivity estimate: how precisely independent contributions must cancel to yield the low scale.

## Relation to the cosmological constant problem

The cosmological constant problem is sometimes called a hierarchy problem, but it is more severe and conceptually different. Vacuum energy multiplies the identity operator in the effective action, and heavy thresholds contribute terms of order

$$
\delta\rho_{\text{vac}}\sim M^4.
$$

The observed vacuum energy density is extraordinarily small compared with known particle-physics scales. Unlike ordinary scalar masses, the vacuum energy is tied to gravity and spacetime curvature. Some lessons overlap — relevant operators, heavy-threshold sensitivity, lack of simple protection — but the cosmological constant problem deserves separate treatment.

This page focuses on scalar mass hierarchies, especially the electroweak hierarchy.

## Common pitfalls

**Saying dimensional regularization solves the hierarchy problem.** It changes the regulator language. It does not remove heavy-threshold corrections.

**Equating naturalness with experimental inevitability.** Naturalness has motivated many searches, but an EFT sensitivity argument does not guarantee where or whether a protection mechanism appears.

**Forgetting couplings.** A heavy particle that does not couple to the scalar does not generate the same threshold correction. The hierarchy problem concerns heavy scales coupled to the light scalar.

**Treating the cutoff as automatically physical.** A Wilsonian cutoff can represent where an EFT breaks down, but a formal regulator introduced for calculation is not itself a particle threshold.

**Ignoring symmetry.** A light scalar that is a Goldstone boson, supersymmetric partner, or otherwise protected is not a generic scalar.

**Using one tuning measure as if it were invariant.** Fine-tuning measures depend on parameter choices and assumptions. The robust statement is radiative sensitivity to allowed relevant operators.

## Relations to other pages

[Technical Naturalness](/renormalization-rg-eft/naturalness-power-counting/technical-naturalness/) gives the symmetry criterion. [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/) will develop the loop-and-threshold bookkeeping more systematically. [Relevant Operators and Sensitivity](/renormalization-rg-eft/naturalness-power-counting/relevant-operators-and-sensitivity/) will present the Wilsonian critical-surface picture in greater generality.

[Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/) explains why heavy fields usually affect low-energy physics through parameter shifts and higher-dimension operators. The hierarchy problem is precisely about the relevant parameter shift. [Matching](/renormalization-rg-eft/effective-field-theory/matching/) and [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) provide the technical tools for computing the effect.

The electroweak hierarchy connects to gauge-theory and Standard Model pages, while the broader logic connects to [Naturalness in Wilsonian Language](/renormalization-rg-eft/naturalness-power-counting/naturalness-in-wilsonian-language/), [Symmetry Protection](/renormalization-rg-eft/naturalness-power-counting/symmetry-protection/), and later BSM-focused material.

## Research status

The EFT statement that unprotected scalar masses are sensitive to heavy thresholds is established. It is part of ordinary Wilsonian reasoning and appears in both particle-physics EFT and statistical-field-theory language.

What remains unsettled is the interpretation. The electroweak hierarchy problem has motivated supersymmetry, compositeness, extra dimensions, neutral naturalness, relaxion-like mechanisms, scale-symmetry ideas, and environmental approaches. None is presently forced by first principles alone. A careful page should therefore distinguish the robust EFT diagnosis from proposed solutions and from sociological expectations about what nature “should” have done.

## Exercises

### Exercise 1: Threshold sensitivity estimate

A light scalar has mass $m=100\,\mathrm{GeV}$ and couples to a heavy scalar of mass $M=10\,\mathrm{TeV}$ with $\kappa=1$. Estimate

$$
\frac{\delta m^2}{m^2}
$$

using $\delta m^2\sim \kappa M^2/(16\pi^2)$.

<details><summary><strong>Solution</strong></summary>

We estimate

$$
\frac{\delta m^2}{m^2}
\sim
\frac{M^2}{16\pi^2m^2}.
$$

With $M/m=10\,\mathrm{TeV}/100\,\mathrm{GeV}=100$, this gives

$$
\frac{\delta m^2}{m^2}
\sim
\frac{100^2}{16\pi^2}
\approx
\frac{10000}{158}
\approx 63.
$$

So the threshold correction is roughly two orders of magnitude larger than the desired low mass-squared. This is a sensitivity estimate, not a precise observable.

</details>

### Exercise 2: Why the fermion case differs

A heavy scalar of mass $M$ couples to a light fermion $\psi$. Explain why a correction to the fermion mass must vanish when the chiral-symmetry-breaking spurions vanish.

<details><summary><strong>Solution</strong></summary>

A Dirac mass term

$$
m\bar\psi\psi=m(\bar\psi_L\psi_R+\bar\psi_R\psi_L)
$$

breaks independent chiral rotations of $\psi_L$ and $\psi_R$. If the heavy scalar interactions preserve this chiral symmetry, then no loop diagram can generate $\bar\psi_L\psi_R$ without inserting a chiral-symmetry-breaking spurion. Therefore

$$
\delta m\propto m
$$

or to some other chiral-breaking parameter. Unlike a generic scalar mass, the fermion mass is protected by the enhanced symmetry at $m=0$.

</details>

### Exercise 3: Critical-surface analogy

In a statistical system, the correlation length near a critical point scales as

$$
\xi\sim a |t|^{-\nu},
$$

where $a$ is a microscopic length and $t$ is a reduced temperature. If $\xi/a=10^{10}$ and $\nu=1$, what value of $|t|$ is required? Explain the analogy to a light scalar mass.

<details><summary><strong>Solution</strong></summary>

With $\nu=1$,

$$
\frac{\xi}{a}\sim |t|^{-1}.
$$

Thus $\xi/a=10^{10}$ requires

$$
|t|\sim 10^{-10}.
$$

The system must be tuned close to the critical point. A light scalar mass compared with a microscopic scale similarly means the theory is close to a critical surface in theory space. In condensed matter, an external parameter like temperature can be tuned. In particle physics, the question is what explains the closeness.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for the Wilsonian theory-space and critical-surface perspective.
- G. 't Hooft, "Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking," in *Recent Developments in Gauge Theories*, for the symmetry criterion.
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on dilatations, renormalization, secret symmetry, and asymptotic freedom.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, scalar masses, and RG flows.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the discussion of RG methods, mass effects, critical phenomena, and EFT.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on decoupling, power counting, symmetries, and the Standard Model as an effective theory.

## Version history

- 2026-06-18: First polished draft. Framed the hierarchy problem as scalar threshold sensitivity, separated cutoff language from physical matching, connected the electroweak hierarchy to Wilsonian critical surfaces, and summarized major classes of responses without turning the page into a BSM review.
