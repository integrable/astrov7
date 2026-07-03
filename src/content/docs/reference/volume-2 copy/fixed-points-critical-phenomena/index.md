---
title: "Fixed Points and Critical Phenomena"
description: "Chapter overview for scale invariance, RG fixed points, critical exponents, universality classes, Wilson–Fisher theory, epsilon expansion, large-N methods, and crossover phenomena."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Cardy 1996; Goldenfeld 1992."
topics:
  - fixed points
  - critical phenomena
  - scale invariance
  - critical exponents
  - universality
  - Wilson–Fisher fixed point
canonicalTopics:
  - rg-fixed-points
  - critical-phenomena
  - universality-classes
  - critical-exponents
researchStatus:
  established:
    - "RG fixed points, relevant and irrelevant perturbations, scaling laws, universality, and the epsilon expansion are standard foundations of modern critical phenomena and QFT."
  active:
    - "Precise nonperturbative data for strongly coupled fixed points, emergent symmetry, scale-versus-conformal questions, multicritical behavior, and dangerously irrelevant operators remain active across statistical physics, particle theory, and condensed matter."
---

Fixed Points and Critical Phenomena is the chapter in the Renormalization, RG, and EFT volume where the renormalization group stops being only a differential equation for running parameters and becomes a theory of phases, scaling, and universal behavior.

The chapter exists because the most predictive part of RG is local geometry near special points of theory space. At a fixed point, the theory has no intrinsic length scale. Near a fixed point, only a few perturbations grow at long distances, while infinitely many microscopic details fade away. That is why magnets, fluids, lattice spin systems, and continuum field theories can share the same critical exponents.

Read this chapter when you want to understand why critical phenomena are universal, how anomalous dimensions enter measurable scaling laws, how the Wilson–Fisher fixed point is found, and why the words relevant, irrelevant, and marginal are not adjectives attached to an operator once and for all, but statements about a neighborhood of a fixed point.

$$
\text{critical behavior}
=
\text{RG flow near a fixed point}.
$$

## Prerequisites

You should know the scale conventions in [Conventions and Notation](/renormalization-rg-eft/conventions/), the meaning of [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

It helps to have seen a scalar field theory such as $\phi^4$ theory and to know the idea of a correlation length. The chapter develops the statistical-physics vocabulary as it is needed, rather than assuming a full course in critical phenomena.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/) | The basic meaning of scale transformations, power-law correlators, and the distinction between scale invariance and conformal invariance. |
| 2 | [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) | The definition of an RG fixed point and why fixed points organize continuum limits and critical behavior. |
| 3 | [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) | How perturbations near a fixed point are classified by eigenoperators and RG eigenvalues. |
| 4 | [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) | The measurable scaling exponents $\nu$, $\eta$, $\alpha$, $\beta$, $\gamma$, $\delta$, and their RG meaning. |
| 5 | [Scaling Relations](/renormalization-rg-eft/fixed-points-critical-phenomena/scaling-relations/) | How hyperscaling and exponent identities follow from scaling assumptions and where they can fail. |
| 6 | [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) | Why different microscopic systems share one fixed point and therefore one set of universal long-distance data. |
| 7 | [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) | The canonical interacting fixed point of scalar $\phi^4$ theory below four dimensions. |
| 8 | [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/) | How the small parameter $\epsilon=4-d$ makes the Wilson–Fisher fixed point perturbatively accessible. |
| 9 | [Large-N Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/large-n-expansion/) | A complementary controlled approximation for vector models and critical exponents. |
| 10 | [Crossover and Dangerously Irrelevant Operators](/renormalization-rg-eft/fixed-points-critical-phenomena/crossover-and-dangerously-irrelevant-operators/) | How flows between scaling regimes work and why some irrelevant operators still affect ordered-phase observables. |

After this path, you should be able to look at an RG flow diagram, identify fixed points and relevant directions, predict qualitative phase structure, and understand why critical exponents are insensitive to microscopic details.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| RG fixed point | A point $g_*$ in theory space where $\beta^i(g_*)=0$. | Defines a scale-invariant theory and often a continuum limit. |
| Scaling dimension | The exponent $\Delta$ controlling how a local operator transforms under scale transformations. | Determines power-law correlators and the relevance of perturbations. |
| RG eigenvalue | The linearized exponent $y_i$ of a perturbation near a fixed point. | Positive $y_i$ grows toward the IR; negative $y_i$ shrinks toward the IR in the usual statistical convention. |
| Relevant perturbation | A perturbation that moves the theory away from the fixed point at long distances. | Controls tuning parameters such as temperature, mass, or magnetic field. |
| Critical surface | The surface in theory space flowing into a critical fixed point in the IR. | Explains why reaching a critical point requires tuning only finitely many parameters. |
| Correlation length | The long-distance scale $\xi$ beyond which correlations decay away from criticality. | Diverges at a continuous phase transition and sets the scale for universal behavior. |
| Critical exponent | An exponent governing power-law behavior near a critical point. | Provides experimentally and numerically testable universal data. |
| Universality class | A basin of microscopic theories sharing the same long-distance fixed point and relevant symmetry data. | Explains why very different systems can have the same critical behavior. |
| Wilson–Fisher fixed point | The interacting scalar fixed point near $d=4$ dimensions. | The basic example behind the Ising and $O(N)$ critical universality classes. |
| Dangerously irrelevant operator | An irrelevant perturbation at the fixed point that affects some ordered-phase scaling laws. | Prevents a too-naive reading of irrelevant as harmless. |

The important shift is from asking whether a single Lagrangian contains a scale to asking where a theory lies in theory space and which fixed point controls its long-distance or short-distance behavior.

## Common confusions

**Scale invariance is not the same as dimensional analysis.** Dimensional analysis counts units. Scale invariance is a dynamical statement about a theory or correlation functions. Running couplings and anomalous dimensions are exactly where the difference becomes visible.

**A fixed point is not necessarily a free theory.** The Gaussian fixed point is free, but the Wilson–Fisher fixed point and many conformal field theories are interacting.

**Relevant does not mean important in every context.** It means growing under a specified RG flow near a specified fixed point. A relevant coupling can be tuned to zero to reach criticality; an irrelevant coupling can be crucial for microscopic stability or for ordered-phase amplitudes.

**Universality is not sameness of microscopic systems.** It is sameness of long-distance data after irrelevant details have been washed out by RG flow.

**Critical exponents are not arbitrary fit parameters.** They are eigenvalue data of a fixed point, together with scaling relations and operator normalizations. Experiments and simulations estimate them; RG explains why they are universal.

**Scale invariance does not automatically mean conformal invariance in every imaginable theory.** Under strong assumptions, scale invariance often enhances to conformal invariance, especially in familiar unitary relativistic examples. The distinction still matters conceptually and technically.

## Boundaries

This chapter does:

- explain scale invariance, fixed points, linearized RG flow, and the operator meaning of relevant, irrelevant, and marginal perturbations;
- connect critical exponents to scaling dimensions and RG eigenvalues;
- develop universality classes and scaling relations;
- introduce the Wilson–Fisher fixed point, epsilon expansion, and large-N expansion as controlled analytic tools;
- prepare the reader for CFT, statistical field theory, and nonperturbative critical phenomena.

This chapter does not try to do:

- develop conformal field theory in full detail, which belongs in the CFT and Bootstrap volume;
- provide a complete statistical mechanics course, which belongs in the matter and statistical-physics material;
- derive every multi-loop critical exponent, which belongs in model calculation and advanced RG pages;
- replace lattice, Monte Carlo, conformal bootstrap, or experiment as sources of high-precision exponent data;
- treat every exotic fixed point, deconfined critical point, or nonunitary universality class in the first pass.

## Where to go next

For the perturbative construction of the basic scalar fixed point, continue through [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/). For the broad Wilsonian geometry behind this chapter, return to [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/).

For conformal multiplets, operator product expansions, conformal blocks, and bootstrap constraints, continue to the CFT and Bootstrap volume after this chapter. For phase transitions in matter systems, continue to the statistical-field-theory and matter volumes once their pages are available.

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG equations, short-distance expansion, and critical behavior.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Asymptotic Freedom."
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, especially the sections on RG methods and critical phenomena.
- John Cardy, *Scaling and Renormalization in Statistical Physics*.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*.
- Michael E. Fisher, classic reviews on critical phenomena and scaling theory.

## Version history

- 2026-06-17: First polished chapter overview with reading path, landmarks, boundaries, and references.
