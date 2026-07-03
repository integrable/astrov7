---
title: "Power Counting"
description: "How effective field theories assign sizes to operators, loops, masses, derivatives, and diagrams so that an infinite Lagrangian becomes predictive."
sidebar:
  label: "Power Counting"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg 1979 and 1995; Manohar and Georgi 1984; Georgi EFT lectures; Burgess 2020, ch. 3; Schwartz 2014, chs. 21–23; Weinberg Vol. II, ch. 18."
topics:
  - effective field theory
  - power counting
  - loop expansion
  - dimensional analysis
  - chiral counting
  - Wilson coefficients
canonicalTopics:
  - eft-power-counting
  - derivative-expansion
  - naive-dimensional-analysis
researchStatus:
  established:
    - "Power counting is the standard EFT mechanism that identifies which operators, loops, and counterterms contribute at a given accuracy."
  active:
    - "Power counting remains theory-dependent and is actively refined in nuclear EFT, SCET, nonrelativistic EFTs, hydrodynamics, cosmology, gravity, strongly coupled EFTs, and multi-scale problems."
---

## Summary

Power counting is the rule that tells an effective field theory how large each term is. It turns the infinite local Lagrangian

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{leading}}
+
\sum_i \frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i
$$

into a predictive calculation by assigning an order to derivatives, light masses, fields, loops, couplings, symmetry-breaking parameters, and Wilson coefficients.

The minimal idea is simple:

$$
\partial_\mu\sim Q,
\qquad
m_{\text{light}}\sim Q,
\qquad
\frac{\mathcal O_{\Delta}}{M^{\Delta-d}}
\sim
\left(\frac{Q}{M}\right)^{\Delta-d}
\times \text{leading size},
$$

but the real art is choosing the right counting for the physical regime. Chiral perturbation theory, Fermi theory, HQET, SCET, hydrodynamics, gravity, and nuclear EFT all use the same EFT logic but different detailed power countings.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A power-counting workflow: choose the small parameter, assign weights to derivatives and fields, order operators, include loops and counterterms at the same order, and quote an EFT prediction with a truncation estimate.](/figures/renormalization-rg-eft/eft-power-counting-workflow.svg)

<figcaption>

Power counting is the grammar of an EFT calculation. It begins with a small parameter, assigns weights to ingredients, orders operators and diagrams, includes the counterterms required at that order, and produces a prediction with a controlled truncation estimate.

</figcaption>
</figure>

:::note[The EFT contract]
At any claimed order, include every operator, loop, counterterm, and insertion that contributes at that order according to the stated power counting. Leaving out an allowed same-order term is not an approximation; it is an extra assumption.
:::

## Prerequisites

You should know [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), and [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/).

Useful background includes [Power Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

## Core idea

An EFT contains all local operators compatible with its light fields and symmetries. Without an ordering principle, this sounds like disaster. With power counting, it becomes a finite calculation.

Suppose the observable depends on a small parameter

$$
\varepsilon\equiv \frac{Q}{M}\ll 1.
$$

A power counting claims that the observable has an expansion such as

$$
\mathcal A
=
\mathcal A_{\text{LO}}
+
\mathcal A_{\text{NLO}}
+
\mathcal A_{\text{NNLO}}
+
\cdots,
$$

with

$$
\frac{\mathcal A_{\text{NLO}}}{\mathcal A_{\text{LO}}}
\sim \varepsilon^{n_1},
\qquad
\frac{\mathcal A_{\text{NNLO}}}{\mathcal A_{\text{LO}}}
\sim \varepsilon^{n_2},
\qquad
0<n_1<n_2<\cdots.
$$

The labels LO, NLO, and NNLO mean leading order, next-to-leading order, and next-to-next-to-leading order. They are not universal labels; they refer to the chosen counting.

A useful power counting answers four questions:

1. Which operators enter at a given order?
2. Which loop diagrams enter at the same order?
3. Which counterterms are required to absorb divergences at that order?
4. What size should be assigned to the neglected terms?

That is the difference between an EFT as a list of terms and an EFT as a prediction machine.

## Setup and conventions

We use $Q$ for the characteristic low-energy scale and $M$ for the heavy scale or breakdown scale. In relativistic four-dimensional examples, a local operator of engineering dimension $\Delta$ is often written as

$$
\mathcal L\supset \frac{C_\Delta}{M^{\Delta-4}}\mathcal O_\Delta.
$$

If the matrix element of $\mathcal O_\Delta$ scales like $Q^\Delta$, then the insertion is suppressed by a power

$$
\left(\frac{Q}{M}\right)^{\Delta-4}
$$

relative to a dimension-four interaction of comparable field content. This is the simplest engineering-dimension counting.

However, power counting is not just engineering dimension. It may also assign sizes to:

| Ingredient | Typical assignment | Comment |
|---|---:|---|
| derivative | $\partial\sim Q$ | basis of derivative expansion |
| light mass | $m\sim Q$ or $m^2\sim Q^2$ | depends on symmetry and kinematics |
| loop | often $1/(16\pi^2)$ plus powers of $Q$ | theory-dependent suppression |
| weak coupling | $g\ll 1$ | separate perturbative parameter |
| symmetry breaking | spurion $\eta\ll 1$ | tracks approximate symmetries |
| velocity or residual momentum | $v$, $k/M$ | nonrelativistic and heavy-particle EFTs |
| collinear scaling | components scale differently | SCET-style multi-region counting |
| inverse large number | $1/N$ | large-$N$ EFTs and saddle expansions |

Every EFT page should state its counting before using phrases like leading order or suppressed.

## Canonical dimension counting

The simplest estimate comes from engineering dimensions. In $d$ spacetime dimensions,

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\le d}
+
\sum_{\Delta>d}\frac{C_\Delta}{M^{\Delta-d}}\mathcal O_\Delta.
$$

If the operator contains $n_\partial$ derivatives and light fields whose matrix elements carry powers of $Q$, then its contribution is suppressed by powers of $Q/M$. For a process at $Q\ll M$, higher-dimension operators are increasingly small.

This counting explains why a nonrenormalizable interaction can be predictive. An infinite tower exists, but only finitely many operators contribute up to any fixed power of $Q/M$.

For example, in four dimensions a dimension-six operator contributes schematically as

$$
\mathcal A_{d=6}\sim C_6\left(\frac{Q}{M}\right)^2\mathcal A_{\text{ref}},
$$

while a dimension-eight operator contributes as

$$
\mathcal A_{d=8}\sim C_8\left(\frac{Q}{M}\right)^4\mathcal A_{\text{ref}},
$$

again modulo field content, selection rules, loops, and the normalization of the reference amplitude.

## Diagrammatic power counting

Power counting must include diagrams, not just Lagrangian terms. A loop made from lower-order vertices can contribute at the same order as a tree diagram from a higher-order operator. When this happens, the higher-order operator is not optional; it is the counterterm that absorbs the loop divergence and parametrizes the corresponding short-distance finite part.

For relativistic loop integrals in four dimensions, a rough estimate is

$$
\int\frac{d^4\ell}{(2\pi)^4}
\sim
\frac{Q^4}{16\pi^2},
$$

while a light scalar propagator scales as

$$
\frac{1}{\ell^2}
\sim
\frac{1}{Q^2}.
$$

A derivative at a vertex contributes a power of $Q$. Combining these ingredients with graph topology gives the diagram's order.

This estimate is deliberately rough. It is not a substitute for a regulator and an actual calculation. Its job is to tell you which diagrams must be included.

## Weinberg counting for Goldstone EFTs

A particularly clean example is a four-dimensional Goldstone EFT whose leading interactions contain two derivatives. Suppose a connected diagram has loop order $L$ and vertices $v$ with derivative order $d_v$. The overall momentum power is

$$
D
=
4L-2I+\sum_v d_v,
$$

where $I$ is the number of internal propagators. Using the topology identity

$$
L=I-V+1,
$$

with $V$ the total number of vertices, we obtain

$$
D
=
2+2L+\sum_v(d_v-2).
$$

This is the basic Weinberg power-counting formula for a broad class of derivative-coupled Goldstone EFTs. It says:

- each loop raises the order by two powers of momentum;
- a leading two-derivative vertex does not raise the order beyond the baseline;
- a four-derivative vertex raises the order by two powers;
- a six-derivative vertex raises the order by four powers.

Thus an order-$Q^4$ calculation contains both one-loop diagrams made only from two-derivative vertices and tree diagrams with one four-derivative vertex. They belong together. Cute trick? No. Renormalization demands it.

## Example: Fermi theory

The four-fermion Fermi interaction has schematic form

$$
\mathcal L_F
\sim
G_F(\bar\psi\Gamma\psi)(\bar\psi\Gamma\psi),
\qquad
G_F\sim \frac{1}{M_W^2}.
$$

At energy $Q\ll M_W$, a tree-level amplitude scales as

$$
\mathcal A_F\sim G_F Q^2\sim \frac{Q^2}{M_W^2}.
$$

Derivative corrections from higher operators are suppressed by additional powers of $Q^2/M_W^2$. Loop corrections inside the EFT bring factors such as

$$
\frac{G_F Q^2}{16\pi^2}
\sim
\frac{Q^2}{16\pi^2M_W^2},
$$

together with operator mixing and counterterms. The detailed counting depends on the process and on which light particles are retained, but the principle is stable: the EFT orders corrections in powers of $Q/M_W$ and loop factors.

## Example: chiral perturbation theory

In chiral perturbation theory, the light fields are Goldstone bosons and the expansion is in momenta and light quark masses. The leading Lagrangian has two derivatives or one power of the quark-mass spurion:

$$
\mathcal L_2\sim O(p^2).
$$

The next order contains

$$
\mathcal L_4\sim O(p^4),
$$

and an $O(p^4)$ calculation includes both:

$$
\text{one-loop diagrams from }\mathcal L_2,
\qquad
\text{tree diagrams from }\mathcal L_4.
$$

The loop divergences from $\mathcal L_2$ are absorbed into coefficients in $\mathcal L_4$. This is the cleanest example of the EFT slogan:

$$
\text{same order}=
\text{all loops and local terms required by the counting}.
$$

The chiral expansion also shows that masses may count as powers of momenta. For pions,

$$
m_\pi^2\sim p^2,
$$

because the pion mass is controlled by explicit chiral-symmetry breaking.

## Naturalness and naive dimensional analysis

Power counting often assumes that dimensionless Wilson coefficients are **natural**, meaning order one after the correct normalization has been chosen:

$$
C_i\sim O(1).
$$

This is not a theorem. It is a hypothesis about the absence of unexplained tuning or hidden small parameters. If a coefficient is much smaller or larger than expected, the EFT is telling you something: perhaps a symmetry was missed, a resonance is nearby, a coupling is weak, a large-$N$ limit is present, the chosen normalization is poor, or the system is fine-tuned.

Naive dimensional analysis refines this estimate by including loop factors such as $4\pi$ in strongly coupled four-dimensional EFTs. A commonly used schematic form is

$$
\mathcal L_{\text{NDA}}
\sim
\frac{\Lambda^4}{16\pi^2}
\widehat{\mathcal L}\left(
\frac{\partial}{\Lambda},
\frac{4\pi\phi}{\Lambda},
\frac{4\pi\psi}{\Lambda^{3/2}},
\frac{gA}{\Lambda}
\right),
$$

where $\Lambda$ is the EFT breakdown scale and $\widehat{\mathcal L}$ has order-one coefficients if the dynamics at $\Lambda$ is strongly coupled in the NDA sense. Different communities use slightly different normalizations. The point is not the decoration by $4\pi$; the point is that loop factors and strong-coupling estimates are part of the counting.

## Counterterms at the same order

A consistent EFT calculation at order $\varepsilon^n$ must include all counterterms needed to renormalize loop diagrams that contribute at order $\varepsilon^n$. This is not an aesthetic preference. It is required for regulator independence.

For example, suppose a loop built from leading interactions produces a divergence with the structure of a four-derivative operator:

$$
\mathcal A_{\text{loop}}
\supset
\frac{1}{\epsilon}\,Q^4.
$$

Then the EFT Lagrangian must contain a four-derivative counterterm whose coefficient absorbs the pole:

$$
\mathcal L\supset C_4(\mu)\mathcal O_4.
$$

The finite part of $C_4(\mu)$ is not fixed by the low-energy theory alone. It must be matched or measured. This is why loops and higher-order local operators appear together.

## Multiple small parameters

Many useful EFTs have more than one small parameter. Examples include:

| EFT setting | Small parameters |
|---|---|
| weakly coupled EFT | $Q/M$ and coupling $g$ |
| chiral perturbation theory | $p/\Lambda_\chi$ and light quark masses |
| HQET | residual momentum $k/m_Q$ and $\Lambda_{\text{QCD}}/m_Q$ |
| NRQED/NRQCD | velocity $v$, coupling $\alpha$, and $Q/M$ |
| SCET | different scalings for collinear, soft, and ultrasoft momenta |
| hydrodynamics | gradients over local thermal scales and fluctuation strength |
| large-$N$ theories | $Q/M$ and $1/N$ |
| gravitational EFT | $E/M_{\text{Pl}}$, curvature radius, and possible matter thresholds |

There is no shame in this. The power counting just has to say what is being expanded and what is being held fixed. Ambiguity about small parameters is where EFT calculations quietly go feral.

## Breakdown of naive counting

A proposed power counting can fail. Common reasons include:

- a light mode was integrated out by mistake;
- a threshold or resonance lies near the region of interest;
- an interaction is enhanced by infrared behavior;
- a scattering length is unnaturally large;
- Coulomb exchange requires resummation;
- collinear and soft modes have different scalings;
- loop integrals receive contributions from multiple momentum regions;
- symmetry forces the leading term to vanish;
- a coefficient is tuned or accidentally small.

When this happens, one should not blame EFT. One should refine the EFT. The correct response is usually to change degrees of freedom, reorganize the counting, or resum a class of diagrams.

## This is the most important part of this page

Power counting is a **claim about uniform approximation**. It says that in a specified regime, all contributions can be ordered by a small set of parameters, and that neglected terms are parametrically smaller than kept terms.

Therefore a good EFT calculation must state:

1. the degrees of freedom;
2. the small parameter or parameters;
3. the scaling assigned to derivatives, masses, fields, and couplings;
4. which operators and loops are included at the claimed order;
5. the expected size of omitted terms.

If any of these are missing, the calculation may still be correct, but the reader cannot tell why.

## Common pitfalls

**Counting operators but not loops.** Loops of lower-order interactions can contribute at the same order as higher-order tree operators.

**Using engineering dimension as the whole story.** Engineering dimension is only the first estimate. Symmetry, kinematics, loops, couplings, and infrared enhancements can change the counting.

**Forgetting same-order counterterms.** If a loop divergence has the form of an allowed operator at the same order, that operator must be included.

**Calling all coefficients order one without choosing normalization.** Naturalness statements require a convention. A coefficient that looks large in one basis may be ordinary in another.

**Using a relativistic counting in a nonrelativistic problem.** Nonrelativistic propagators, energy scalings, and loop measures differ from relativistic ones.

**Ignoring accidental zeros.** If the leading contribution vanishes by symmetry or kinematics, the first nonzero term may be higher order.

**Overtrusting the expansion near breakdown.** When $Q/M$ is not small, the EFT may still be qualitatively useful, but the truncation estimate is no longer controlled.

## Relations to other pages

[Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/) explains why local operators with more derivatives arise. This page explains how to decide which of them matter at a given accuracy.

[Matching](/renormalization-rg-eft/effective-field-theory/matching/) uses power counting to know which Wilson coefficients must be fixed. [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) uses the same counting to organize logarithms and operator mixing. [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/) explains why a theory with infinitely many operators can remain predictive.

The discussion of natural sizes connects to [Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/dimensional-analysis/) and [Naive Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/naive-dimensional-analysis/). The loop-and-counterterm logic connects to [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) and [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/).

## Research status

The general logic of EFT power counting is established. What varies by research area is the correct counting for a given physical regime.

Active work includes power counting in nuclear forces, few-body systems with large scattering lengths, soft-collinear factorization, heavy-particle EFTs, hydrodynamic EFT, open-system EFTs, cosmological EFTs, gravitational radiation, finite-density systems, nonperturbative matching, and automated operator-basis construction.

## Exercises

### Exercise 1: Derive the Goldstone counting formula

For a connected four-dimensional Goldstone EFT diagram, let $L$ be the number of loops, $I$ the number of internal propagators, and $V$ the number of vertices. A vertex $v$ carries $d_v$ derivatives. Show that the amplitude scales as $Q^D$ with

$$
D=2+2L+\sum_v(d_v-2).
$$

<details><summary><strong>Solution</strong></summary>

The loop measures contribute $Q^{4L}$, the internal scalar propagators contribute $Q^{-2I}$, and the vertices contribute $Q^{\sum_v d_v}$. Therefore

$$
D=4L-2I+\sum_v d_v.
$$

For a connected diagram,

$$
L=I-V+1,
$$

so $I=L+V-1$. Substituting gives

$$
D=4L-2(L+V-1)+\sum_v d_v
=2+2L+\sum_v(d_v-2).
$$

This shows that each loop raises the order by two powers of momentum, while vertices with more than two derivatives raise the order by their excess derivative count.

</details>

### Exercise 2: Same order in chiral perturbation theory

Use the formula from Exercise 1 to show that one-loop diagrams made only of two-derivative vertices and tree diagrams with one four-derivative vertex both contribute at order $Q^4$.

<details><summary><strong>Solution</strong></summary>

For a one-loop diagram with only two-derivative vertices, $L=1$ and every $d_v=2$. Therefore

$$
D=2+2(1)+\sum_v(2-2)=4.
$$

For a tree diagram with one four-derivative vertex and any number of two-derivative vertices, $L=0$, one vertex has $d_v=4$, and the rest have $d_v=2$. Therefore

$$
D=2+0+(4-2)=4.
$$

They contribute at the same order and must be included together.

</details>

### Exercise 3: Dimension-six versus dimension-eight

In a four-dimensional EFT with a heavy scale $M$, estimate the relative size of a dimension-six and a dimension-eight operator in a process with momentum $Q\ll M$, assuming dimensionless coefficients of order one.

<details><summary><strong>Solution</strong></summary>

A dimension-six operator appears as

$$
\frac{C_6}{M^2}\mathcal O_6,
$$

so its contribution is suppressed by approximately

$$
\left(\frac{Q}{M}\right)^2.
$$

A dimension-eight operator appears as

$$
\frac{C_8}{M^4}\mathcal O_8,
$$

so its contribution is suppressed by approximately

$$
\left(\frac{Q}{M}\right)^4.
$$

The dimension-eight contribution is therefore smaller by another factor of $(Q/M)^2$, unless symmetry, loops, selection rules, or coefficient sizes alter the estimate.

</details>

### Exercise 4: A loop and a counterterm

Suppose a leading EFT interaction produces a one-loop divergence proportional to $Q^4/\epsilon$. What must be true of the EFT operator basis at the same order?

<details><summary><strong>Solution</strong></summary>

The EFT must contain a local operator whose matrix element has the same $Q^4$ structure and the same quantum numbers. Its coefficient contains a counterterm that absorbs the $1/\epsilon$ divergence. The finite part of that coefficient is a Wilson coefficient to be fixed by matching or measurement. Without this operator, the EFT prediction at that order would be regulator dependent.

</details>

## References

- Steven Weinberg, "Phenomenological Lagrangians," *Physica A* **96** (1979), for the EFT logic behind symmetry-based derivative expansions.
- Aneesh Manohar and Howard Georgi, "Chiral Quarks and the Nonrelativistic Quark Model," *Nuclear Physics B* **234** (1984), for influential normalization and power-counting ideas.
- Howard Georgi, EFT lectures and reviews, for practical EFT dimensional analysis and power-counting intuition.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapter 3, for power counting, matching, and the Wilsonian rationale.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 21–23, for renormalizability, nonrenormalizable theories, and RG methods.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods, nonrenormalizable interactions, and critical phenomena.

## Version history

- 2026-06-18: First polished draft. Added engineering counting, diagrammatic counting, Weinberg formula, Fermi and chiral examples, NDA discussion, counterterm logic, and exercises with solutions.
