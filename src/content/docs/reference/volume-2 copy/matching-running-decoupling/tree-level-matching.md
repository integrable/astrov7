---
title: "Tree-Level Matching"
description: "How tree-level exchange of heavy fields becomes local Wilson coefficients in a low-energy effective field theory."
sidebar:
  label: "Tree-Level Matching"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, EFT and RG chapters; Schwartz 2014, nonrenormalizable theories and RG chapters; Weinberg Vol. I, renormalization and EFT viewpoint; Burgess 2020, decoupling, effective actions, power counting, and matching."
topics:
  - tree-level matching
  - Wilson coefficients
  - integrating out heavy fields
  - local operator expansion
  - effective field theory
canonicalTopics:
  - tree-level-matching
  - eft-wilson-coefficients
  - heavy-field-exchange
researchStatus:
  established:
    - "Tree-level matching is the standard low-energy expansion of full-theory amplitudes or actions after heavy fields have been removed."
  active:
    - "In complicated gauge theories and high-dimensional operator bases, the bookkeeping of redundancies, gauge covariance, and basis conversion remains an active computational problem, even though the principle is standard."
---

## Summary

**Tree-level matching** is the simplest place where the logic of effective field theory becomes concrete. A heavy particle is exchanged in the full theory. At energies much smaller than its mass, the exchange cannot be resolved. Its effect is therefore indistinguishable from a sum of local interactions among the light fields.

The slogan is

$$
\text{heavy propagator at }Q\ll M
\quad\longrightarrow\quad
\text{local operator expansion in }Q/M.
$$

Suppose a full theory contains a heavy field of mass $M$ and light fields with typical momenta $Q\ll M$. The low-energy EFT is organized as

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_i C_i(\mu)\mathcal O_i,
$$

where the local operators $\mathcal O_i$ are built only from light fields. Tree-level matching fixes the leading Wilson coefficients $C_i$ by demanding that low-energy amplitudes, correlation functions, or classical actions agree order by order in $Q/M$.

A canonical example is a heavy scalar $H$ coupled linearly to a light composite source $\mathcal J$:

$$
\mathcal L
=\mathcal L_{\text{light}}
+\frac12\partial_\mu H\partial^\mu H
-\frac12M^2H^2
-H\mathcal J.
$$

At energies below $M$, solving the heavy-field equation of motion gives

$$
\Delta\mathcal L_{\text{EFT}}
=\frac12\mathcal J\frac{1}{M^2+\Box}\mathcal J
=\frac{1}{2M^2}\mathcal J^2
-\frac{1}{2M^4}\mathcal J\Box\mathcal J
+O\left(\frac{\partial^4}{M^6}\right),
$$

up to the overall sign convention chosen for the source coupling. This is tree-level matching in one line: the nonlocal heavy propagator becomes a controlled tower of local operators.

## Prerequisites

You should know the chapter overview [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/), the EFT pages [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/).

It is also useful to know [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/) and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/). Tree-level matching is often easiest on shell, but it becomes cleaner conceptually once operator bases and field redefinitions are already familiar.

## Core idea

Matching is not guessing an EFT coefficient because dimensions look plausible. Matching is an equality statement.

Choose a low-energy quantity $X$, compute it in the full theory, compute it in the EFT, expand both sides in $Q/M$, and solve for the Wilson coefficients:

$$
X_{\text{full}}(Q,M)
= X_{\text{EFT}}(Q;C_i,M,\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

At tree level, $X$ can be a classical action, a Green function, or an on-shell amplitude. The result is the same when redundant operators are treated consistently. The point is that the EFT must reproduce the low-energy behavior of the full theory, not the high-energy details.

The heavy particle has not vanished without consequence. It has left behind numbers. Those numbers are the Wilson coefficients.

## Setup and conventions

This page uses the mostly-minus metric and Fourier conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/). Momenta in amplitudes are physical external momenta unless an all-incoming convention is explicitly stated.

We distinguish four scales:

| Symbol | Meaning |
|---|---|
| $M$ | heavy mass or threshold scale |
| $Q$ | typical light external momentum or mass |
| $\mu_M$ | matching scale, usually chosen near $M$ |
| $\Lambda_{\text{EFT}}$ | breakdown scale of the EFT, often of order $M$ |

Tree-level matching usually has no loop logarithms, but it still cares about power counting. If the EFT is kept through order $(Q/M)^N$, the full-theory result must be expanded to the same order.

A matching calculation should state:

1. which light fields remain in the EFT;
2. which heavy fields have been removed;
3. which operator basis is being used;
4. which quantity is being matched;
5. which power in $Q/M$ is being retained;
6. which field redefinitions or equations of motion have been used.

That list is not bureaucracy. It is what prevents coefficient values from becoming meaningless.

## Matching by amplitudes

The most direct matching condition uses low-energy amplitudes. Suppose the EFT basis contains operators $\mathcal O_i$ with Wilson coefficients $C_i$. For a chosen set of external light states,

$$
\mathcal A_{\text{full}}(p_a;M)
=\sum_i C_i(\mu_M)\mathcal A_i^{\text{EFT, tree}}(p_a)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right),
$$

where $\mathcal A_i^{\text{EFT, tree}}$ is the tree-level matrix element of $\mathcal O_i$.

The clean workflow is:

| Step | Action | Reason |
|---:|---|---|
| 1 | Choose external light states. | Only light fields appear in the EFT. |
| 2 | Compute the full-theory tree amplitude. | This contains heavy propagators or heavy exchange. |
| 3 | Expand for $p_a^2\ll M^2$. | This turns nonlocal dependence into powers of $p/M$. |
| 4 | Compute EFT matrix elements of local operators. | These are polynomials in momenta at tree level. |
| 5 | Equate coefficients of independent momentum structures. | This solves for $C_i$. |

For example, a heavy mediator exchanged between two light currents gives a full-theory amplitude of the schematic form

$$
\mathcal A_{\text{full}}(q)
\propto
\frac{g^2}{M^2-q^2}
=\frac{g^2}{M^2}
\left(1+\frac{q^2}{M^2}+\frac{q^4}{M^4}+\cdots\right),
$$

for momentum transfer $q^2\ll M^2$. The EFT contains a leading contact operator and derivative corrections:

$$
\Delta\mathcal L_{\text{EFT}}
\sim
\frac{g^2}{M^2}\mathcal O_0
+\frac{g^2}{M^4}\mathcal O_2
+\frac{g^2}{M^6}\mathcal O_4+\cdots.
$$

The amplitude sees only a contact interaction because the heavy propagator cannot go on shell at low energy.

## Matching by solving the heavy-field equation

The same result can often be derived more elegantly by solving the classical equation of motion for the heavy field. Consider

$$
\mathcal L
=\mathcal L_{\text{light}}
+\frac12\partial_\mu H\partial^\mu H
-\frac12M^2H^2
-H\mathcal J.
$$

The heavy field obeys

$$
(\Box+M^2)H=-\mathcal J.
$$

For low momenta, invert the operator as a derivative expansion:

$$
H_{\text{cl}}
=-\frac{1}{M^2+\Box}\mathcal J
=-\frac{1}{M^2}\mathcal J
+\frac{1}{M^4}\Box\mathcal J
+O\left(\frac{\partial^4}{M^6}\right).
$$

Substituting back into the action gives

$$
\Delta\mathcal L_{\text{EFT}}
=\frac12\mathcal J\frac{1}{M^2+\Box}\mathcal J.
$$

Expanding yields

$$
\Delta\mathcal L_{\text{EFT}}
=\frac{1}{2M^2}\mathcal J^2
-\frac{1}{2M^4}\mathcal J\Box\mathcal J
+\frac{1}{2M^6}\mathcal J\Box^2\mathcal J+
\cdots.
$$

After integration by parts, the second term may be written as

$$
-\mathcal J\Box\mathcal J
\simeq
\partial_\mu\mathcal J\partial^\mu\mathcal J,
$$

up to boundary terms. Depending on the operator basis, further use of the light-field equations of motion may move this term into other operators.

The lesson is sharp: tree-level matching is classical elimination plus local expansion.

## A scalar toy model

Let $\phi$ be a light real scalar and $H$ a heavy real scalar with

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
+\frac12\partial_\mu H\partial^\mu H
-\frac12M^2H^2
-\frac{g}{2}H\phi^2,
$$

where $m\ll M$. Here

$$
\mathcal J=\frac{g}{2}\phi^2.
$$

At tree level the heavy field generates

$$
\Delta\mathcal L_{\text{EFT}}
=\frac{g^2}{8M^2}\phi^4
-\frac{g^2}{8M^4}\phi^2\Box\phi^2
+O\left(\frac{\partial^4}{M^6}\right).
$$

For four-light-particle scattering, the full theory contains $s$-, $t$-, and $u$-channel heavy exchange. For one channel, the low-energy expansion is

$$
\frac{g^2}{M^2-s}
=\frac{g^2}{M^2}
+\frac{g^2s}{M^4}
+O\left(\frac{s^2}{M^6}\right).
$$

The contact operator $\phi^4$ reproduces the constant term. The derivative operator reproduces the terms proportional to $s$, $t$, and $u$, after accounting for the chosen operator basis and external equations of motion.

This example is deliberately simple. In a realistic EFT, the same calculation is decorated by spin, gauge indices, flavor, symmetry factors, and field redefinitions. The principle does not change.

## Fermi theory from heavy W exchange

The historical archetype of tree-level matching is the low-energy weak interaction. At energies far below the $W$ mass, the charged weak boson cannot be resolved. The full-theory exchange of a $W$ between two charged currents becomes a four-fermion interaction.

Schematically,

$$
\mathcal L_{\text{full}}
\supset
-\frac{g_2}{\sqrt2}\left(W^+_\mu J_-^\mu+W^-_\mu J_+^\mu\right)
+M_W^2 W^+_\mu W^{-\mu},
$$

and tree-level matching gives

$$
\mathcal L_{\text{Fermi}}
\supset
-\frac{g_2^2}{2M_W^2}J_+^\mu J_{-\mu}
+O\left(\frac{\partial^2}{M_W^4}\right),
$$

up to the current normalization convention. In the common weak-interaction convention this is written in terms of the Fermi constant as

$$
\frac{G_F}{\sqrt2}=\frac{g_2^2}{8M_W^2}
\qquad\text{at tree level}.
$$

The first derivative corrections are suppressed by $Q^2/M_W^2$. For nuclear beta decay, muon decay, and many low-energy weak processes, that suppression is enormous compared with the leading four-fermion term.

This is why the four-fermion theory was useful before the electroweak theory was known. EFT does not require ignorance of the UV theory. It also explains why an older low-energy theory could work so well.

## Matching by actions versus matching by observables

There are two common languages for tree-level matching.

In **action matching**, one eliminates the heavy field from the action and expands the resulting nonlocal expression:

$$
e^{iS_{\text{EFT}}[\phi]}
=\int\mathcal D H\,e^{iS[\phi,H]}.
$$

At tree level, this is dominated by $H=H_{\text{cl}}[\phi]$:

$$
S_{\text{EFT}}^{\text{tree}}[\phi]=S[\phi,H_{\text{cl}}[\phi]].
$$

In **observable matching**, one equates amplitudes or correlators. This is often more economical when only a few coefficients are needed.

The two approaches agree when used consistently. Their advantages differ:

| Method | Strength | Risk |
|---|---|---|
| Action matching | Produces many operators at once; can preserve symmetries manifestly. | May include redundant operators that later need basis reduction. |
| Amplitude matching | Directly tied to physical quantities; avoids some redundant operators. | May miss off-shell or background-field structures needed elsewhere. |
| Background-field matching | Keeps gauge covariance and organizes derivative expansions. | Requires more formal machinery. |

A good EFT calculation chooses the method that makes the symmetries and the desired coefficients hardest to mess up.

## Operator basis and field redefinitions

Tree-level matching does not determine a unique list of coefficients until an operator basis is chosen. This is not a defect. It is coordinate dependence.

For example, derivative operators related by integration by parts, algebraic identities, or light-field equations of motion may describe the same on-shell physics. A term such as

$$
\mathcal J\Box\mathcal J
$$

may be kept as written, integrated by parts, or transformed using the equations of motion for the light fields. Different choices move numbers among Wilson coefficients.

The invariant statement is not

$$
C_7=\text{the number I found in my favorite basis}.
$$

The invariant statement is

$$
\sum_i C_i\langle f|\mathcal O_i|i\rangle
$$

for properly matched physical quantities at the order being computed.

When comparing results across papers, always compare:

| Item | Why it matters |
|---|---|
| Operator normalization | A factor of $2$, $4!$, or gauge generator normalization changes $C_i$. |
| Field basis | Field redefinitions reshuffle redundant operators. |
| Use of equations of motion | On-shell and off-shell bases differ. |
| Matching observable | Amplitudes, Green functions, and background-field actions expose different structures. |
| Sign conventions | Current definitions and metric conventions affect displayed signs. |

Wilson coefficients are meaningful only with their basis attached. Little labels, giant consequences.

## Power counting and truncation

Tree-level matching naturally produces an infinite tower of local operators. Predictivity comes from truncation. If $Q/M\ll1$, keeping terms through $1/M^N$ gives an error of order

$$
O\left(\frac{Q^{N+1}}{M^{N+1}}\right)
$$

or whatever power is implied by the chosen expansion.

For the heavy-scalar example,

$$
\Delta\mathcal L_{\text{EFT}}
=\frac{1}{2M^2}\mathcal J^2
-\frac{1}{2M^4}\mathcal J\Box\mathcal J
+\frac{1}{2M^6}\mathcal J\Box^2\mathcal J+
\cdots.
$$

If the calculation only needs relative accuracy $O(Q^2/M^2)$, the leading operator may be enough. If it needs $O(Q^4/M^4)$, derivative corrections must be included. The EFT expansion is not a vibes-based hierarchy. It is an error budget.

A practical rule:

$$
\text{include every operator allowed by symmetry at the order of the desired accuracy.}
$$

Leaving out an allowed operator because it feels ugly is not power counting. It is wishful thinking in a lab coat.

## Matching scale

At tree level, matching coefficients often contain no logarithms, so the matching scale $\mu_M$ may not visibly appear. Still, one usually records the coefficient as $C_i(\mu_M)$ because loop corrections and RG evolution will make the scale dependence explicit.

The usual choice is

$$
\mu_M\sim M,
$$

because this avoids large logarithms of the form $\log(M/\mu_M)$. After matching, the coefficients can be run to lower scales using EFT anomalous dimensions.

The conceptual separation is:

$$
\text{matching fixes boundary data at }M,
\qquad
\text{running transports that data to }Q.
$$

Tree-level matching gives the first boundary condition. One-loop matching improves it.

## Common pitfalls

**Matching the Lagrangian by eye instead of matching quantities.** Dimensional analysis tells you possible sizes. It does not fix coefficients. Matching fixes coefficients.

**Expanding outside the EFT domain.** The expansion

$$
\frac{1}{M^2-q^2}=\frac{1}{M^2}\left(1+\frac{q^2}{M^2}+\cdots\right)
$$

requires $|q^2|\ll M^2$. Near the heavy-particle pole, the EFT contact expansion fails.

**Forgetting derivative corrections.** The leading contact operator is only the first term. Higher accuracy requires higher-derivative operators.

**Comparing coefficients without comparing bases.** A Wilson coefficient is a coordinate. The physical prediction is the coefficient times the matrix element, summed over the basis.

**Using equations of motion inconsistently.** EOM reductions are allowed for S-matrix elements and basis simplification, but they must be applied consistently to sources, off-shell quantities, and higher-order terms.

**Confusing integrating out with deleting.** Removing a heavy field leaves local operators. If you simply erase the heavy field, you erase its low-energy effects.

## Relations to other pages

This page is the tree-level entry point for the Matching, Running, and Decoupling chapter. [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/) explains what changes when loop corrections are included. [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) explains finite shifts when a field leaves the active spectrum. [Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/) gives the functional-integral version of the same idea.

The background EFT logic is developed in [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/). Operator-basis issues connect to [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/), and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

## Research status

The principle of tree-level matching is completely standard. What remains nontrivial in current research is scale, complexity, and automation: large operator bases, gauge-covariant bases, flavor structures, nonlinear symmetry realization, gravity EFT, SMEFT/HEFT basis conversion, and matching in theories with multiple thresholds or spontaneously broken symmetries.

For strongly coupled UV theories, tree-level matching may not literally mean drawing a weakly coupled heavy-particle exchange diagram. The EFT idea still applies, but the Wilson coefficients may be fixed by symmetry, data, lattice input, bootstrap information, or nonperturbative calculations rather than by a simple propagator expansion.

## Exercises

### Exercise 1: Heavy scalar exchange

Let

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
+\frac12\partial_\mu H\partial^\mu H
-\frac12M^2H^2
-\frac{g}{2}H\phi^2.
$$

Integrate out $H$ at tree level through order $1/M^4$.

<details><summary><strong>Solution</strong></summary>

The heavy field satisfies

$$
(\Box+M^2)H=-\frac{g}{2}\phi^2.
$$

Thus

$$
H_{\text{cl}}
=-\frac{g}{2}\frac{1}{M^2+\Box}\phi^2
=-\frac{g}{2M^2}\phi^2
+\frac{g}{2M^4}\Box\phi^2
+O(M^{-6}).
$$

Substituting into the quadratic heavy-field action gives

$$
\Delta\mathcal L_{\text{EFT}}
=\frac12\left(\frac{g}{2}\phi^2\right)
\frac{1}{M^2+\Box}
\left(\frac{g}{2}\phi^2\right).
$$

Therefore

$$
\Delta\mathcal L_{\text{EFT}}
=\frac{g^2}{8M^2}\phi^4
-\frac{g^2}{8M^4}\phi^2\Box\phi^2
+O(M^{-6}).
$$

The second term may be integrated by parts and then simplified further using the light-field equations of motion if one is constructing an on-shell operator basis.

</details>

### Exercise 2: Expansion of a heavy propagator

Show that the low-energy expansion of the scalar exchange propagator is local by expanding

$$
\frac{1}{M^2-q^2}
$$

for $|q^2|\ll M^2$. What is the physical meaning of the first omitted term if the expansion is stopped after $q^2/M^2$?

<details><summary><strong>Solution</strong></summary>

Use the geometric series

$$
\frac{1}{M^2-q^2}
=\frac{1}{M^2}\frac{1}{1-q^2/M^2}
=\frac{1}{M^2}\left(1+\frac{q^2}{M^2}+\frac{q^4}{M^4}+\cdots\right).
$$

Each power of $q^2$ corresponds in position space to additional derivatives acting on local operators. If the expansion is stopped after $q^2/M^2$, the first omitted term is of relative order

$$
O\left(\frac{q^4}{M^4}\right),
$$

which is the expected truncation error from neglecting the next higher-derivative operator.

</details>

### Exercise 3: Fermi constant at tree level

Assume the charged-current interaction is normalized as

$$
\mathcal L_{\text{int}}
=-\frac{g_2}{\sqrt2}\left(W^+_\mu J_-^\mu+W^-_\mu J_+^\mu\right).
$$

Using the low-momentum approximation to the $W$ propagator, show why the Fermi interaction scales as $g_2^2/M_W^2$ and recover

$$
\frac{G_F}{\sqrt2}=\frac{g_2^2}{8M_W^2}
$$

in the standard weak-current normalization.

<details><summary><strong>Solution</strong></summary>

At momentum transfer $q^2\ll M_W^2$, the massive vector propagator is approximately proportional to

$$
\frac{1}{q^2-M_W^2}\simeq -\frac{1}{M_W^2}.
$$

Two charged-current vertices therefore generate a local current-current interaction proportional to

$$
\frac{g_2^2}{M_W^2}J_+^\mu J_{-\mu}.
$$

The precise numerical factor depends on how the charged current is normalized. With the conventional weak-interaction normalization, the low-energy four-fermion Lagrangian is written so that

$$
\frac{G_F}{\sqrt2}=\frac{g_2^2}{8M_W^2}
$$

at tree level. Loop corrections and the precise experimental definition of $G_F$ refine this relation, but the tree-level EFT scaling and the $1/M_W^2$ origin are exactly the heavy-exchange matching statement.

</details>

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on decoupling, effective actions, power counting, matching, and redundant interactions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on nonrenormalizable theories, the four-Fermi theory, RG, and effective actions.
- Mark Srednicki, *Quantum Field Theory*, especially the renormalization group and effective field theory sections.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I and Vol. II, for the modern renormalization and EFT viewpoint.
- Aneesh V. Manohar, EFT lecture notes, for compact practical matching examples and Wilson-coefficient normalization discipline.

## Version history

- 2026-06-18: First polished draft. Added amplitude matching, equation-of-motion matching, heavy-scalar example, Fermi-theory example, basis caveats, and exercises.
