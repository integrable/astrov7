---
title: "Technical Naturalness"
description: "A careful explanation of technical naturalness, radiative stability, symmetry protection, spurions, and what the criterion does and does not say."
sidebar:
  label: "Technical Naturalness"
  order: 3
level: Graduate
status: "Polished draft"
source: "'t Hooft naturalness criterion; Coleman 1985, dilatations and renormalization lectures; Srednicki 2007, RG and EFT sections; Schwartz 2014, chs. 21–23; Burgess 2020, chs. 2–4."
topics:
  - technical naturalness
  - radiative stability
  - symmetry protection
  - spurions
  - effective field theory
canonicalTopics:
  - technical-naturalness
  - radiative-stability
  - symmetry-protection
researchStatus:
  established:
    - "Technical naturalness is the standard EFT criterion that a small parameter is stable when setting it to zero enhances an exact quantum symmetry."
  active:
    - "How much weight to assign naturalness as a guide to unknown short-distance physics remains an active interpretive question, especially for scalar sectors and cosmological terms."
---

## Summary

A parameter is **technically natural** if making it small does not require re-tuning it order by order under quantum corrections. The most useful practical test is the symmetry test:

> A small parameter is technically natural if setting it to zero increases the exact symmetry of the quantum theory.

In that case, quantum corrections to the small parameter must be proportional to the same symmetry-breaking parameter, or to other spurions that break the same symmetry. Small stays small because the symmetry forbids additive corrections.

The archetypal examples are fermion masses protected by chiral symmetry and Goldstone-boson masses protected by an approximate shift symmetry. The archetypal non-example is a generic elementary scalar mass coupled to heavy physics: the scalar mass operator is allowed by all symmetries, so heavy thresholds can add corrections of order the heavy scale squared.

Technical naturalness is not the claim that nature must choose order-one numbers. It is a statement about **radiative stability**: whether a low-energy parameter can remain small without repeatedly cancelling large independent contributions.

:::note[The diagnostic in one line]
If $\epsilon$ is small and the theory at $\epsilon=0$ has an extra exact quantum symmetry, then the RG equation near $\epsilon=0$ has the schematic form

$$
\mu\frac{d\epsilon}{d\mu}=\gamma(g)\epsilon+O(\epsilon^2).
$$

The surface $\epsilon=0$ is stable under RG flow. That is the core of technical naturalness.
:::

## Prerequisites

You should know [Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/dimensional-analysis/), [Naive Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/naive-dimensional-analysis/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Renormalization Group Equations](/renormalization-rg-eft/renormalization-group-equations/), and [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/).

It is also useful to have seen [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), because technical naturalness is most transparent when matching across heavy thresholds.

## Core idea

Quantum corrections are not random decorations added to a Lagrangian. They obey the same exact symmetries as the regulated quantum theory. Therefore, if a parameter is the only thing that breaks a symmetry, any correction to that parameter must also carry the same symmetry-breaking weight.

Write a theory as

$$
\mathcal L=\mathcal L_{\text{sym}}+\epsilon\mathcal O_\epsilon.
$$

Suppose $\mathcal L_{\text{sym}}$ has a symmetry $G$ that is broken by $\mathcal O_\epsilon$. If the regulator, measure, and renormalization prescription preserve $G$ when $\epsilon=0$, then counterterms generated at $\epsilon=0$ cannot contain $\mathcal O_\epsilon$. The coefficient $\epsilon=0$ is an invariant surface in theory space.

Equivalently, the beta function must vanish at $\epsilon=0$:

$$
\beta_\epsilon(g,\epsilon)=\mu\frac{d\epsilon}{d\mu},
\qquad
\beta_\epsilon(g,0)=0.
$$

Expanding near the symmetric surface gives

$$
\beta_\epsilon(g,\epsilon)=\gamma_\epsilon(g)\epsilon+O(\epsilon^2).
$$

This is multiplicative renormalization of the symmetry-breaking parameter. It does not mean $\epsilon$ never runs. It means the running cannot generate a nonzero $\epsilon$ from zero.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Map of technical naturalness: a small parameter, an enhanced symmetry at zero, spurion-controlled counterterms, and RG-stable smallness](/figures/renormalization-rg-eft/technical-naturalness-protection-map.svg)

<figcaption>

Technical naturalness is radiative stability enforced by an exact symmetry of the quantum theory. If the symmetry-breaking parameter is $\epsilon$, counterterms and RG flow must carry the same spurion charge, so $\epsilon=0$ is not shifted by quantum corrections.

</figcaption>
</figure>

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). We use $\mu$ for a renormalization scale, $\Lambda$ for a Wilsonian or cutoff scale, $M$ for a heavy threshold, and $Q$ for a low external scale.

A Wilsonian action at scale $\Lambda$ is written schematically as

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

A parameter is **radiatively stable** if its smallness at low scales is not spoiled by loop corrections or threshold corrections from heavier scales. More concretely, if $p$ is small compared with a heavy scale $M$, it is radiatively stable when corrections behave schematically as

$$
\delta p\sim p\times \left[\text{logs and dimensionless factors}\right],
$$

rather than

$$
\delta p\sim M^{[p]}\times \left[\text{dimensionless factors}\right].
$$

The second form can still be cancelled by choosing the bare parameter carefully. Technical naturalness asks whether such a cancellation is stable and symmetry-explained.

## The symmetry test

The symmetry test has three parts.

| Step | Question | Failure mode |
|---:|---|---|
| 1 | What is the small parameter $\epsilon$? | Vague claims about “small numbers” without identifying the parameter. |
| 2 | Does setting $\epsilon=0$ increase symmetry? | A field redefinition or accidental notation change is mistaken for a real symmetry. |
| 3 | Is the symmetry exact quantum mechanically? | The symmetry is broken by the regulator, anomaly, boundary condition, or heavy sector. |

The third step is the sneaky one. A symmetry that exists only in the classical Lagrangian may not protect a parameter after quantization. The regulator and measure matter. If the symmetry is anomalous, then it is not an exact symmetry of the quantum theory and cannot be used as an ordinary technical-naturalness protection.

A clean way to state the test is with spurions. Assign transformation properties to the small parameter $\epsilon$ so that the full Lagrangian is formally invariant. Counterterms must be invariant under the spurionized symmetry. If no invariant counterterm can be written without a factor of $\epsilon$, then additive corrections to $\epsilon$ are forbidden.

## Spurions and selection rules

A **spurion** is a book-keeping device: a coupling or parameter is temporarily treated as if it transforms under a symmetry. The symmetry is then restored formally, and all allowed counterterms must respect the formal transformation law.

Suppose a symmetry forbids an operator $\mathcal O$ unless a spurion $\epsilon$ is inserted. Then the EFT contains

$$
\mathcal L\supset \epsilon\mathcal O.
$$

If the spurion charge of $\mathcal O$ is nonzero, loops cannot generate

$$
\Delta\mathcal L\supset c\mathcal O
$$

with $c$ independent of $\epsilon$, because that would violate the spurion selection rule. Instead one gets

$$
\Delta\mathcal L\supset \epsilon\,c(g,\log\mu)\mathcal O.
$$

This is the precise EFT reason that approximate symmetries are useful. The symmetry does not need to be exact in nature; it needs to become exact in the limit where the small breaking parameter is set to zero.

## Fermion masses are technically natural

Consider a Dirac fermion with

$$
\mathcal L=\bar\psi i\gamma^\mu\partial_\mu\psi-m\bar\psi\psi.
$$

When $m=0$, the left- and right-handed components can be rotated independently:

$$
\psi_L\to e^{i\alpha_L}\psi_L,
\qquad
\psi_R\to e^{i\alpha_R}\psi_R.
$$

The mass term couples the two chiralities:

$$
m\bar\psi\psi=m(\bar\psi_L\psi_R+\bar\psi_R\psi_L).
$$

Thus $m$ breaks chiral symmetry. If the mass is the only source of this breaking, quantum corrections to the mass must be proportional to $m$:

$$
\delta m\propto m.
$$

In a mass-independent scheme one writes

$$
\mu\frac{dm}{d\mu}=-\gamma_m(g)m.
$$

The sign convention for $\gamma_m$ depends on definitions; the important point is multiplicative running. If $m=0$ at one scale, it remains zero at all scales.

This is why a tiny fermion mass is technically natural. The smallness may still call for a flavor theory if many masses and mixings appear in a pattern, but radiative corrections do not by themselves force a small fermion mass up to a heavy scale.

## Gauge-boson masses are protected by gauge structure

A mass term for an Abelian gauge field would be

$$
\Delta\mathcal L=\frac12m_A^2 A_\mu A^\mu.
$$

This term is not invariant under

$$
A_\mu\to A_\mu+\partial_\mu\alpha.
$$

If gauge invariance is exact, a gauge-boson mass cannot be generated by loops. This is not because loops are too polite. It is because a local counterterm $A_\mu A^\mu$ is forbidden by the gauge redundancy and associated Ward identities or BRST structure.

The statement should be phrased carefully. Gauge symmetry is a redundancy, not an ordinary physical global symmetry. But as a constraint on the quantum theory it is extremely powerful: it restricts the allowed counterterms and physical state space. A massless photon is technically natural because the massless limit has the gauge structure that forbids the mass term.

Massive gauge bosons in the electroweak theory are not obtained by simply violating gauge invariance. They arise from the Higgs mechanism, where gauge invariance remains present but is realized with additional fields and a vacuum expectation value.

## Goldstone and pseudo-Goldstone masses

A Goldstone boson has an approximate shift symmetry

$$
\pi(x)\to \pi(x)+c.
$$

The shift symmetry forbids a potential $V(\pi)$ and allows derivative interactions. A mass term

$$
\frac12m_\pi^2\pi^2
$$

breaks the shift symmetry. If the shift symmetry is exact, $m_\pi=0$ is protected. If the symmetry is explicitly broken by a small spurion $\epsilon$, then the mass is proportional to that spurion:

$$
m_\pi^2\propto \epsilon.
$$

This is the logic behind pseudo-Goldstone bosons. They can be much lighter than the symmetry-breaking scale because their mass measures explicit symmetry breaking, not the full scale of the dynamics.

The same logic appears in many EFTs: pions in chiral perturbation theory, axion-like particles, composite-Higgs models, and low-energy modes in condensed matter. The details differ, but the protection mechanism is the same: an approximate symmetry becomes exact in the small-mass limit.

## Generic scalar masses are not protected

Now consider a real scalar field with

$$
\mathcal L=\frac12\partial_\mu\phi\,\partial^\mu\phi-\frac12m^2\phi^2-\frac{\lambda}{4!}\phi^4.
$$

The operator $\phi^2$ is usually allowed by the same symmetries that allow the kinetic term and quartic interaction. Setting $m^2=0$ may make the classical Lagrangian scale invariant, but in a generic interacting quantum theory scale invariance is already broken by running couplings and by heavy thresholds. Unless there is an additional exact symmetry, loops can add scalar mass terms.

With a hard cutoff one expects schematically

$$
\delta m^2\sim \frac{\lambda}{16\pi^2}\Lambda^2.
$$

In dimensional regularization, pure power divergences do not appear in the same way. But the naturalness issue does not disappear. If the scalar couples to a heavy field of mass $M$, matching across the heavy threshold generically produces

$$
\delta m^2\sim \frac{\kappa}{16\pi^2}M^2
$$

up to scheme-dependent constants and logarithms. The heavy mass is physical. Hiding the cutoff does not hide the threshold.

A small scalar mass can be technically natural if an actual symmetry protects it: for example, a shift symmetry for a Goldstone boson, supersymmetry relating scalar and fermion masses, or a more subtle nonlinearly realized symmetry. Without such protection, a light elementary scalar coupled to very heavy physics is radiatively fragile.

## Technical naturalness versus ordinary dimensional analysis

Dimensional analysis asks what size a coefficient would have if the scale $\Lambda$ is the only scale and the dimensionless coefficient is ordinary:

$$
g_i\sim \Lambda^{d-\Delta_i}.
$$

Technical naturalness asks whether a coefficient much smaller than this estimate is stable.

For example, a fermion mass in four dimensions has dimension one, so dimensional analysis alone might suggest

$$
m\sim M.
$$

But chiral symmetry can make

$$
m\ll M
$$

stable. The small mass is controlled by a symmetry-breaking spurion, not by the heavy scale alone.

By contrast, a generic scalar mass-squared has dimension two and is not protected by ordinary internal symmetries. If a scalar couples to a heavy sector at scale $M$, dimensional analysis and explicit matching agree that

$$
m^2\sim M^2
$$

is the generic expectation unless a protection mechanism is present.

## Technical naturalness versus probability

Technical naturalness is sometimes described as a statement about “unlikely” cancellations. That language is suggestive, but it can be misleading.

A probability statement requires a measure on theory space or on UV parameters. Technical naturalness by itself does not provide that measure. It gives a sharper, more operational diagnostic:

| Question | Technical-naturalness answer |
|---|---|
| Is a small parameter stable under loops? | Check whether corrections are multiplicative or additive. |
| Is the small limit symmetry-enhanced? | Check the exact quantum symmetries and spurion charges. |
| Does a heavy threshold generate the parameter? | Match the heavy theory onto the EFT. |
| Is a cancellation probable? | Not answered without a measure or UV theory. |

This distinction matters. Technical naturalness is a tool for organizing EFT sensitivity. It is not a theorem that nature cannot contain finely adjusted parameters.

## A Wilsonian view

In Wilsonian language, a technically natural surface is often an invariant surface in theory space. If $\epsilon=0$ is symmetry-enhanced, then RG flow cannot leave that surface:

$$
\epsilon=0\quad\Longrightarrow\quad\frac{d\epsilon}{d\ell}=0.
$$

Near the surface,

$$
\frac{d\epsilon}{d\ell}=y\epsilon+O(\epsilon^2),
$$

where $\ell$ is an IR RG time. Small departures may grow or shrink depending on the RG eigenvalue $y$, but the surface itself is not shifted.

This is the geometry behind technical naturalness. The symmetry carves out a stable submanifold. If the low-energy theory lies close to it, quantum corrections slide it along or away from the surface according to controlled equations; they do not kick it to a generic point in theory space.

## A practical checklist

When faced with a small parameter, use this checklist.

| Step | What to check |
|---:|---|
| 1 | Identify the parameter and the operator it multiplies. |
| 2 | Set the parameter to zero and list the symmetries gained. |
| 3 | Check whether those symmetries survive quantization and regularization. |
| 4 | Treat the parameter as a spurion and classify allowed counterterms. |
| 5 | Check heavy thresholds by matching, not only by reading beta functions. |
| 6 | Decide whether smallness is multiplicatively renormalized or additively regenerated. |
| 7 | Separate the technical statement from any claim about probability, aesthetics, or UV completion. |

This checklist is more reliable than asking whether a number “looks small.” The same numerical smallness can be natural, unnatural, conventional, or meaningless depending on normalization and symmetry.

## Common pitfalls

**Confusing technical naturalness with beauty.** A technically natural theory can be ugly. A visually elegant theory can contain unstable small parameters.

**Using dimensional regularization to declare victory over scalar sensitivity.** Dimensional regularization removes explicit cutoff power divergences from intermediate expressions. It does not remove physical heavy-threshold corrections.

**Forgetting that the protecting symmetry must be exact in the limit.** A classical symmetry broken by an anomaly is not an ordinary protection mechanism. A symmetry broken by the heavy sector does not protect low-energy parameters from that heavy sector.

**Treating all small numbers alike.** A small angle, a small mass, a small vacuum energy, and a small dimensionless coupling can have completely different naturalness status.

**Ignoring basis dependence.** A parameter may look small in one operator basis and not in another. The invariant question is whether physical symmetry-breaking data are radiatively stable.

**Overstating the conclusion.** Technical naturalness can diagnose sensitivity, but it cannot force the UV theory to avoid fine tuning.

## Relations to other pages

[Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/dimensional-analysis/) gives the first scale estimate. [Naive Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/naive-dimensional-analysis/) refines that estimate with loop factors and strong-coupling normalization. This page explains when small coefficients are stable despite those estimates.

[Hierarchy Problem](/renormalization-rg-eft/naturalness-power-counting/hierarchy-problem/) applies the logic to scalar masses and the electroweak scale. [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/) will systematize the loop-and-threshold version. [Symmetry Protection](/renormalization-rg-eft/naturalness-power-counting/symmetry-protection/) will collect the major protection mechanisms.

The same logic appears throughout EFT: [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/), and [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) all require symmetry-aware bookkeeping.

## Research status

The symmetry criterion and spurion method are established parts of EFT practice. Fermion masses, Goldstone masses, gauge-boson masses, and many flavor suppressions are standard examples of technically natural small parameters.

The interpretation of naturalness as a guide to unknown UV physics is more delicate. It has been enormously productive, especially in building BSM models, but it is not a theorem. Modern discussions distinguish sharply between the calculable EFT fact of radiative sensitivity and broader claims about probability, typicality, selection effects, or UV completion.

## Exercises

### Exercise 1: Multiplicative stability

Suppose a parameter $\epsilon$ has beta function

$$
\mu\frac{d\epsilon}{d\mu}=a g^2\epsilon+O(\epsilon^2).
$$

Show that if $\epsilon(\mu_0)=0$, then $\epsilon(\mu)=0$ at all scales in perturbation theory. Then solve the equation for approximately constant $g$.

<details><summary><strong>Solution</strong></summary>

The equation is first order and homogeneous in $\epsilon$ at leading order. The solution with initial condition $\epsilon(\mu_0)=0$ is identically zero.

If $g$ is treated as constant, then

$$
\frac{d\log\epsilon}{d\log\mu}=a g^2,
$$

so

$$
\epsilon(\mu)=\epsilon(\mu_0)\left(\frac{\mu}{\mu_0}\right)^{a g^2}.
$$

A small but nonzero value can run, but it remains proportional to the initial small value.

</details>

### Exercise 2: Fermion mass and chiral symmetry

For a Dirac fermion, write the mass term in terms of $\psi_L$ and $\psi_R$. Explain why independent phase rotations of $\psi_L$ and $\psi_R$ forbid the mass term.

<details><summary><strong>Solution</strong></summary>

The mass term is

$$
m\bar\psi\psi=m(\bar\psi_L\psi_R+\bar\psi_R\psi_L).
$$

Under

$$
\psi_L\to e^{i\alpha_L}\psi_L,
\qquad
\psi_R\to e^{i\alpha_R}\psi_R,
$$

we have

$$
\bar\psi_L\psi_R\to e^{i(\alpha_R-\alpha_L)}\bar\psi_L\psi_R.
$$

This is invariant only if $\alpha_L=\alpha_R$ or if $m$ is assigned a compensating spurion transformation. Therefore the mass term breaks the axial part of the chiral symmetry. When $m=0$, the symmetry is restored, so corrections to $m$ must be proportional to chiral-symmetry-breaking spurions.

</details>

### Exercise 3: Heavy scalar threshold

Let a light scalar $\phi$ couple to a heavy scalar $S$ through

$$
\mathcal L\supset -\frac12M^2S^2-\frac{\kappa}{4}\phi^2S^2.
$$

Use dimensional analysis to estimate the one-loop threshold correction to the light scalar mass.

<details><summary><strong>Solution</strong></summary>

The coupling $\kappa$ is dimensionless in four dimensions. A one-loop diagram with an $S$ loop and two external $\phi$ legs corrects the coefficient of $\phi^2$. The result must have mass dimension two. The only heavy mass scale in the loop is $M$, so the threshold correction is schematically

$$
\delta m_\phi^2\sim \frac{\kappa}{16\pi^2}M^2,
$$

up to scheme-dependent constants and logarithms. Unless a symmetry forbids the $\phi^2$ operator or forces $\kappa$ to be tiny, the light scalar mass is sensitive to the heavy threshold.

</details>

## References

- G. 't Hooft, "Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking," in *Recent Developments in Gauge Theories*, for the symmetry criterion for natural small parameters.
- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on dilatations, renormalization and symmetry, and secret symmetry.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on dimensional analysis, renormalization, RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, and RG.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapters on renormalization group methods and EFT.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on decoupling, effective actions, power counting, symmetries, and the Standard Model as an EFT.

## Version history

- 2026-06-18: First polished draft. Introduced the symmetry criterion, spurion language, radiative stability, protected fermion and Goldstone masses, unprotected scalar masses, and the distinction between technical naturalness and probability claims.
