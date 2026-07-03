---
title: "Dimensional Analysis"
description: "A guide to using mass dimensions, scales, and dimensionless coefficients to estimate terms in QFT and EFT without confusing bookkeeping with dynamics."
sidebar:
  label: "Dimensional Analysis"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, dimensional analysis and EFT sections; Schwartz 2014, chs. 21–23 and app. A; Weinberg Vol. II, RG methods and EFT; Burgess 2020, chs. 2–3; Wilson and Kogut 1974."
topics:
  - dimensional analysis
  - mass dimension
  - effective field theory
  - power counting
  - Wilson coefficients
canonicalTopics:
  - dimensional-analysis
  - mass-dimension
  - eft-power-counting
researchStatus:
  established:
    - "Mass-dimensional analysis is a standard convention-independent first pass for organizing local operators and EFT expansions."
  active:
    - "The nontrivial work in modern EFT is choosing the right small parameters, field normalizations, symmetry spurions, and kinematic regions beyond dimensional analysis alone."
---

## Summary

Dimensional analysis is the first filter in a quantum field theory calculation. It tells you what powers of mass, momentum, cutoff, or heavy scale must accompany a term so that the action is dimensionless. In an EFT it gives the baseline estimate

$$
\mathcal L_{\text{EFT}}
=\sum_i c_i\,\Lambda^{d-\Delta_i}\mathcal O_i,
$$

where $d$ is spacetime dimension, $\Delta_i$ is the engineering or scaling dimension of the local operator $\mathcal O_i$, $\Lambda$ is the organizing scale, and $c_i$ is dimensionless.

The formula is powerful because it makes scale suppression visible. If $\Delta_i>d$, the operator is accompanied by inverse powers of $\Lambda$ and contributes with powers of $Q/\Lambda$ at low momentum $Q$. If $\Delta_i<d$, the coefficient carries positive powers of a scale and the operator is relevant near the chosen fixed point.

But dimensional analysis is not a dynamics machine. It does not determine the dimensionless coefficient $c_i$, the sign, the flavor structure, the loop order, the symmetry suppression, the possible logarithms, or the presence of infrared enhancements. It tells you what the answer must look like before physics fills in the dimensionless information.

:::note[What this page fixes]
Throughout this page, unless stated otherwise,

$$
\hbar=c=1,
\qquad [x^\mu]=-1,
\qquad [\partial_\mu]=1,
\qquad [S]=0.
$$

The brackets $[X]$ mean mass dimension, not expectation value.
:::

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Relevant, Irrelevant, and Marginal Operators](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), and [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/).

The page also uses the EFT language from [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/) and [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/), but it does not assume any specific EFT example.

## Core idea

The action appears in the path-integral phase $e^{iS}$ or Euclidean weight $e^{-S_E}$, so in natural units the action is dimensionless:

$$
[S]=0.
$$

If the action is local,

$$
S=\int d^d x\,\mathcal L,
$$

then

$$
[d^d x]=-d,
\qquad
[\mathcal L]=d.
$$

Every term in the Lagrangian density must therefore have mass dimension $d$. This simple statement fixes the dimensions of fields and couplings once the kinetic terms are normalized.

For a scalar field with canonical kinetic term,

$$
\mathcal L_{\text{kin}}=\frac12\partial_\mu\phi\,\partial^\mu\phi,
$$

we get

$$
2[\phi]+2=d,
\qquad
[\phi]=\frac{d-2}{2}.
$$

For a Dirac fermion,

$$
\mathcal L_{\text{kin}}=\bar\psi i\gamma^\mu\partial_\mu\psi,
$$

we get

$$
[\psi]=\frac{d-1}{2}.
$$

For a gauge field with kinetic term $-\frac14F_{\mu\nu}F^{\mu\nu}$ and $F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+\cdots$,

$$
[A_\mu]=\frac{d-2}{2}.
$$

In four spacetime dimensions this gives

| Object | Four-dimensional mass dimension |
|---|---:|
| $x^\mu$ | $-1$ |
| $\partial_\mu$ | $1$ |
| $\mathcal L$ | $4$ |
| real scalar $\phi$ | $1$ |
| Dirac fermion $\psi$ | $3/2$ |
| gauge field $A_\mu$ | $1$ |
| field strength $F_{\mu\nu}$ | $2$ |
| mass $m$ | $1$ |

These assignments are not optional once the kinetic terms are canonically normalized. If you rescale a field, the dimensions of the coefficients change accordingly, but the physical estimates must not.

## Setup and conventions

This page uses $d$ for spacetime dimension and writes local interactions as

$$
\mathcal L\supset g_i\mathcal O_i.
$$

If $\mathcal O_i$ has engineering dimension $\Delta_i$, then the coefficient has dimension

$$
[g_i]=d-\Delta_i.
$$

A convenient dimensionless coefficient is obtained by introducing a reference scale $\Lambda$:

$$
g_i=c_i\Lambda^{d-\Delta_i}.
$$

The scale $\Lambda$ may be a Wilsonian cutoff, a heavy mass, a breakdown scale, or some other organizing scale. It is not automatically the renormalization scale $\mu$. The renormalization scale tracks scheme-dependent running; the scale $\Lambda$ in dimensional estimates tracks where the EFT expansion stops being valid or where new physics is expected to enter.

When a page uses $\mu$ rather than $\Lambda$ in a dimensional estimate, it must say whether $\mu$ is merely the renormalization scale or whether it has been chosen near a physical matching scale.

## Classifying coefficients by dimension

The dimension of $g_i$ gives the first classification of interactions around a fixed point:

| Condition | Name | Coefficient dimension | Low-energy expectation |
|---|---|---:|---|
| $\Delta_i<d$ | relevant | positive | grows toward the IR |
| $\Delta_i=d$ | marginal | zero | decided by beta functions |
| $\Delta_i>d$ | irrelevant | negative | suppressed by powers of $Q/\Lambda$ |

In four dimensions:

| Operator | Dimension | Coefficient form | Comment |
|---|---:|---|---|
| $\phi^2$ | $2$ | $m^2\phi^2$ | relevant scalar mass term |
| $\bar\psi\psi$ | $3$ | $m\bar\psi\psi$ | relevant fermion mass term |
| $\phi^4$ | $4$ | $\lambda\phi^4$ | classically marginal |
| $F_{\mu\nu}F^{\mu\nu}$ | $4$ | dimensionless gauge kinetic coefficient | classically marginal |
| $(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi)$ | $6$ | $C\mathcal O/M^2$ | irrelevant four-fermion interaction |
| $\phi^6$ | $6$ | $c\phi^6/\Lambda^2$ | irrelevant scalar interaction |
| $(\partial_\mu\phi\partial^\mu\phi)^2$ | $8$ | $c\mathcal O/\Lambda^4$ | derivative interaction |

The word irrelevant can sound dismissive. It is not. Irrelevant operators are often the most important observables of new short-distance physics precisely because they are the leading corrections to the lower-dimension theory.

## Dimensionless amplitudes and powers of momenta

Dimensional analysis is most useful when it becomes a statement about small ratios. Suppose an EFT contains an operator of dimension $\Delta>d$,

$$
\mathcal L_{\text{EFT}}\supset \frac{c_i}{\Lambda^{\Delta-d}}\mathcal O_i.
$$

At a characteristic external momentum $Q\ll\Lambda$, the relative effect of this operator in a dimensionless observable is typically of order

$$
\Delta\mathcal A_i\sim c_i\left(\frac{Q}{\Lambda}\right)^{\Delta-d},
$$

up to loop factors, symmetry factors, angular factors, infrared enhancements, and process-dependent numerical constants.

This is why EFT works. To compute to a fixed accuracy, one does not need infinitely many operators. One keeps all terms up to the desired order in $Q/\Lambda$ and estimates the omitted terms.

For example, a dimension-six operator in four dimensions contributes schematically as

$$
\Delta\mathcal A_{\Delta=6}
\sim c_6\frac{Q^2}{\Lambda^2},
$$

while a dimension-eight operator contributes as

$$
\Delta\mathcal A_{\Delta=8}
\sim c_8\frac{Q^4}{\Lambda^4}.
$$

If $Q/\Lambda=0.1$ and the coefficients are not abnormally large, dimension-eight effects are usually two orders of magnitude smaller than dimension-six effects.

## Worked example: four-fermion interactions

In four dimensions, a Dirac fermion has dimension $3/2$, so a current-current operator has dimension six:

$$
\mathcal O_6=(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi),
\qquad
[\mathcal O_6]=6.
$$

The Lagrangian term must have the form

$$
\mathcal L\supset \frac{C}{\Lambda^2}(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi),
$$

where $C$ is dimensionless. The resulting low-energy contact amplitude scales like

$$
\mathcal A\sim C\frac{Q^2}{\Lambda^2},
$$

where the factor $Q^2$ comes from external spinor bilinears after the amplitude is made dimensionless.

This estimate does not say whether $C$ is $1$, $g_*^2$, $g^2/(16\pi^2)$, a flavor matrix, or zero by symmetry. It only says where the scale suppression must appear.

## Worked example: scalar masses and relevant operators

In four dimensions,

$$
[\phi^2]=2,
$$

so the scalar mass term is

$$
\mathcal L\supset -\frac12m^2\phi^2.
$$

The coefficient $m^2$ has dimension two. If the natural organizing scale is $\Lambda$, dimensional analysis alone allows

$$
m^2\sim c_m\Lambda^2.
$$

This does not prove that $m^2$ must be of order $\Lambda^2$. Symmetries, supersymmetry, compositeness, Goldstone structure, dimensional transmutation, or special UV dynamics can change the expectation. It does say that a small scalar mass is not automatically explained by dimensional analysis. If no further structure is present, $m^2\ll\Lambda^2$ is a special choice of relevant coupling.

This is the seed of hierarchy-problem reasoning. The physical issue is not the phrase "quadratic divergence" by itself. The physical issue is sensitivity of a relevant scalar mass parameter to high-scale threshold data.

## Worked example: derivative expansion from heavy exchange

Consider a heavy scalar $H$ of mass $M$ coupled to a light scalar $\phi$ through

$$
\mathcal L\supset -\frac12H(M^2-\Box)H-gH\phi^2.
$$

At tree level, solving the heavy-field equation gives schematically

$$
H\sim -\frac{g}{M^2-\Box}\phi^2.
$$

Expanding for momenta much smaller than $M$,

$$
\frac{1}{M^2-\Box}
=\frac{1}{M^2}\left(1+\frac{\Box}{M^2}+\frac{\Box^2}{M^4}+\cdots\right).
$$

The EFT therefore contains local terms such as

$$
\mathcal L_{\text{EFT}}\supset
\frac{g^2}{2M^2}\phi^4
+\frac{g^2}{2M^4}\phi^2\Box\phi^2
+\cdots.
$$

Dimensional analysis tells you that each additional pair of derivatives brings an additional factor of $1/M^2$. Matching determines the actual coefficient, sign, and operator basis.

## Choosing the right scale

A dimensional estimate is only as useful as the scale inserted into it. The same symbol $\Lambda$ is often used for several different ideas:

| Scale | Meaning | Typical mistake |
|---|---|---|
| cutoff | momentum boundary in a regulated calculation | treating it as a measured physical mass without justification |
| breakdown scale | energy where the EFT expansion fails | assuming it equals the lightest omitted particle in every channel |
| matching scale | scale near which a heavy threshold is removed | confusing it with the arbitrary RG scale $\mu$ |
| strong-coupling scale | scale where loops or interactions become order one | applying weak-coupling estimates beyond it |
| symmetry-breaking scale | scale set by an order parameter, such as $f$ or $v$ | forgetting factors such as $4\pi$ or group-theory normalization |

For a weakly coupled heavy particle of mass $M$, the relevant expansion scale is often $M$. For a strongly coupled Goldstone EFT, the derivative expansion may instead break down near $\Lambda\sim4\pi f$, not simply at $f$. For nonrelativistic EFTs, the scale may be a momentum scale rather than a mass gap. For collinear EFTs, several momentum components scale differently.

Dimensional analysis is therefore not a substitute for identifying the regime.

## What dimensions do not tell you

Dimensional analysis cannot decide the following information:

| Missing information | Example |
|---|---|
| symmetry selection | a term may be forbidden by gauge symmetry, chiral symmetry, parity, flavor, or a shift symmetry |
| loop order | a coefficient may first appear at tree level or only at one loop |
| coupling dependence | a coefficient may scale as $g^2$, $y^4$, $1/N$, or $e^{-8\pi^2/g^2}$ |
| sign | stability and interference depend on signs not fixed by dimensions |
| logarithms | RG evolution can produce $\log(Q/\mu)$ or $\log(M/\mu)$ |
| infrared enhancement | massless fields can produce non-analytic behavior such as $Q^2\log Q^2$ or $1/Q^2$ |
| accidental cancellation | independent contributions may cancel in a special model |
| basis dependence | a coefficient can change under field redefinitions or integration by parts |

That is why dimensional analysis is the first line of the estimate, not the last line of the argument.

## Dimensional analysis versus power counting

Dimensional analysis assigns dimensions. Power counting assigns sizes.

For a simple relativistic EFT with one light scale $Q$ and one heavy scale $\Lambda$, the two are close: dimensions often imply powers of $Q/\Lambda$. But realistic EFTs often contain additional small parameters:

| EFT situation | Extra counting rule |
|---|---|
| chiral perturbation theory | derivatives and pion masses count as small momenta |
| HQET | powers of $\Lambda_{\text{QCD}}/m_Q$ organize heavy-quark corrections |
| NRQED and NRQCD | velocities, energies, and momenta scale differently |
| SCET | soft and collinear momentum components carry different powers |
| large-$N$ theories | diagrams and operators carry powers of $1/N$ |
| weakly coupled EFTs | Wilson coefficients include explicit weak couplings and loop factors |
| symmetry-breaking EFTs | spurions count insertions of small symmetry breaking |

A good power-counting rule refines dimensional analysis by specifying these additional weights. Bad power counting is how one gets a tower of operators but no predictive hierarchy. Tiny bookkeeping goblin, huge consequences.

## Common pitfalls

**Confusing dimensionless with unimportant.** A classically marginal coupling can run, become strong, generate a scale by dimensional transmutation, or control an entire phase structure.

**Confusing dimensionful with physical.** A dimensionful parameter can be scheme dependent, regulator dependent, or basis dependent. Its physical meaning comes from observables.

**Using the wrong dimension of fields.** Field dimensions assume a normalization. If the kinetic term is not canonical, first identify the normalization being used.

**Treating $\Lambda$ and $\mu$ as the same thing.** A heavy scale, a Wilsonian cutoff, and a renormalization scale can be chosen near each other, but they are conceptually distinct.

**Forgetting symmetries.** Dimensional analysis may allow an operator that the theory forbids. Symmetry is not optional decoration; it is part of the estimate.

**Assuming order-one coefficients before choosing a convention.** A coefficient is order one only after field normalizations, loop factors, group factors, and operator basis have been fixed.

**Ignoring infrared scales.** Dimensional analysis using only the UV scale misses nonanalytic dependence from massless particles, thresholds, bound states, and long-distance propagation.

## Relations to other pages

[Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) gives the operator-dimension side of the story. [Relevant, Irrelevant, and Marginal Operators](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) explains how dimensions become RG relevance near a fixed point. [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) explains how dimensions are refined into an EFT expansion rule.

The next page, [Naive Dimensional Analysis](/renormalization-rg-eft/naturalness-power-counting/naive-dimensional-analysis/), adds the loop and strong-coupling normalization conventions needed to say what "order one" means in many EFTs.

Later pages on [Technical Naturalness](/renormalization-rg-eft/naturalness-power-counting/technical-naturalness/), [Hierarchy Problem](/renormalization-rg-eft/naturalness-power-counting/hierarchy-problem/), and [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/) will ask when small dimensionless coefficients or small relevant couplings are stable under quantum corrections.

## Research status

Dimensional analysis itself is settled. It is a consequence of units and locality. The active part is not whether dimensions work, but how to choose the right variables, normalizations, expansion parameters, and EFT regime in complicated systems.

Examples include power counting in multi-scale collider EFTs, nonrelativistic bound-state EFTs, dense matter, hydrodynamic EFTs, gravitational EFTs, EFTs with boundaries or defects, and strongly coupled sectors where the correct normalization is inferred indirectly.

## Exercises

### Exercise 1: Field dimensions in general spacetime dimension

Using canonically normalized kinetic terms, derive the mass dimensions of a scalar field, a Dirac fermion, and a gauge field in $d$ spacetime dimensions.

<details><summary><strong>Solution</strong></summary>

The Lagrangian density has dimension $d$.

For a scalar kinetic term,

$$
\frac12\partial_\mu\phi\partial^\mu\phi,
$$

the dimension is $2+2[\phi]$, so

$$
2+2[\phi]=d,
\qquad
[\phi]=\frac{d-2}{2}.
$$

For a Dirac kinetic term,

$$
\bar\psi i\gamma^\mu\partial_\mu\psi,
$$

the dimension is $2[\psi]+1$, so

$$
2[\psi]+1=d,
\qquad
[\psi]=\frac{d-1}{2}.
$$

For a gauge kinetic term,

$$
-\frac14F_{\mu\nu}F^{\mu\nu},
$$

with $F\sim\partial A+\cdots$, the dimension is $2(1+[A])$, so

$$
2+2[A]=d,
\qquad
[A]=\frac{d-2}{2}.
$$

</details>

### Exercise 2: Four-fermion coefficient

In four spacetime dimensions, find the dimension of

$$
\mathcal O=(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi)
$$

and write the coefficient in terms of a dimensionless number and a heavy scale $M$.

<details><summary><strong>Solution</strong></summary>

In four dimensions $[\psi]=3/2$, so one bilinear $\bar\psi\gamma^\mu\psi$ has dimension $3$. The product has dimension

$$
[\mathcal O]=6.
$$

Since $[\mathcal L]=4$, the coefficient has dimension $-2$. Therefore one writes

$$
\mathcal L\supset \frac{C}{M^2}(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi),
$$

where $C$ is dimensionless.

</details>

### Exercise 3: Which terms matter first?

Suppose an EFT has dimension-six and dimension-eight corrections with coefficients $c_6$ and $c_8$ of comparable size. Estimate the ratio of their contributions at energy $Q\ll\Lambda$.

<details><summary><strong>Solution</strong></summary>

The dimension-six contribution scales as

$$
\Delta\mathcal A_6\sim c_6\frac{Q^2}{\Lambda^2},
$$

while the dimension-eight contribution scales as

$$
\Delta\mathcal A_8\sim c_8\frac{Q^4}{\Lambda^4}.
$$

Therefore

$$
\frac{\Delta\mathcal A_8}{\Delta\mathcal A_6}
\sim
\frac{c_8}{c_6}\frac{Q^2}{\Lambda^2}.
$$

If $c_8/c_6$ is order one, dimension-eight effects are suppressed by an extra factor of $Q^2/\Lambda^2$.

</details>

### Exercise 4: A relevant scalar coupling

In four dimensions, estimate the size allowed by dimensional analysis for a scalar mass parameter if the only UV scale is $\Lambda$. Why does this estimate not prove that the mass must be large?

<details><summary><strong>Solution</strong></summary>

The operator $\phi^2$ has dimension two, so its coefficient has dimension two. Dimensional analysis therefore allows

$$
m^2\sim c_m\Lambda^2.
$$

This is only a baseline estimate. The coefficient $c_m$ may be small because of symmetry, dynamics, compositeness, supersymmetry, Goldstone structure, or a special UV boundary condition. Dimensional analysis identifies sensitivity to the high scale; it does not replace the dynamical explanation.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on dimensional analysis, renormalization, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially appendix A and the chapters on renormalizability, nonrenormalizable theories, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, for RG methods, dimensional estimates, and EFT interpretation.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 2 and 3 for effective actions, dimensional analysis, scaling, power counting, and matching.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian interpretation of dimensions, relevance, and scaling near fixed points.
- Howard Georgi, EFT lectures, for the practical culture of estimating operator sizes with the correct normalization conventions.

## Version history

- 2026-06-18: First polished draft. Added dimensional conventions, coefficient classification, EFT estimates, worked examples, pitfalls, exercises, and links to NDA and technical naturalness.
