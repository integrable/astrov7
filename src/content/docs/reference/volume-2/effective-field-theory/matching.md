---
title: "Matching"
description: "How effective field theories determine Wilson coefficients by requiring low-energy agreement with a more microscopic theory or with physical data."
sidebar:
  label: "Matching"
  order: 6
level: Graduate
status: "Polished draft"
source: "Weinberg 1979 and Vol. II, ch. 18; Burgess 2020, chs. 2–3; Schwartz 2014, chs. 22–23 and 33; Manohar EFT lectures; Georgi EFT lectures."
topics:
  - effective field theory
  - matching
  - Wilson coefficients
  - integrating out heavy fields
  - threshold corrections
  - running
canonicalTopics:
  - eft-matching
  - wilson-coefficients
  - threshold-matching
researchStatus:
  established:
    - "Matching is the standard procedure for fixing EFT Wilson coefficients by equating low-energy observables in two descriptions to a specified order."
  active:
    - "Matching remains technically active in multi-loop SMEFT, SCET, heavy-particle EFTs, nonrelativistic EFTs, gravitational EFT, finite-temperature EFT, and automated amplitude-to-EFT workflows."
---

## Summary

Matching is how an EFT learns its Wilson coefficients. The EFT contains all operators allowed by locality and symmetry,

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}
+
\sum_i \frac{C_i(\mu)}{M^{\Delta_i-4}}\mathcal O_i,
$$

but the numbers $C_i(\mu)$ are not fixed by symmetry alone. Matching fixes them by requiring agreement with a more microscopic description, or directly with measured low-energy data, for a chosen set of observables.

The basic condition is

$$
\mathcal A_{\text{full}}(Q\ll M)
=
\mathcal A_{\text{EFT}}(Q;C_i(\mu),\mu)
+O\left(\frac{Q^{n+1}}{M^{n+1}}\right),
$$

where both sides are expanded to the same order in the low-energy expansion and computed in the same infrared setup.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![A matching and running workflow: full theory at heavy scale M is matched onto EFT Wilson coefficients near mu about M, then RG running evolves the coefficients to mu about Q, where EFT matrix elements produce low-energy observables.](/figures/renormalization-rg-eft/matching-running-workflow.svg)

<figcaption>

Matching fixes Wilson coefficients at a scale near the heavy threshold. Running then evolves those coefficients to a scale appropriate for the low-energy matrix element. The physical observable is independent of the arbitrary matching and renormalization scales up to truncation errors.

</figcaption>
</figure>

:::note[Matching in one sentence]
Compute the same low-energy quantity in the full theory and in the EFT, subtract the common long-distance physics, and assign the remaining short-distance difference to Wilson coefficients.
:::

## Prerequisites

You should know [Cutoff versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), and [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/).

Useful background includes [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/).

## Core idea

An EFT is not a guess about ignorance. It is a controlled replacement of a more detailed description by a simpler low-energy one.

Suppose the full theory has light fields $\phi$ and heavy fields $H$ with mass $M$. At energies $Q\ll M$, the heavy field cannot be produced on shell. Its effects appear through local interactions among the light fields:

$$
\text{full theory: }\phi,H
\qquad\longrightarrow\qquad
\text{EFT: }\phi\text{ only, with }C_i\mathcal O_i.
$$

Matching determines the coefficients $C_i$. The EFT side has unknown coefficients; the full theory side has the heavy-particle dynamics. Equality at low energies solves for the unknowns.

The important phrase is **at low energies**. Matching does not require the EFT to reproduce the full theory at all momenta. It requires the EFT to reproduce the low-energy expansion of the full theory up to the desired order.

## Setup and conventions

We use $M$ for the heavy scale, $Q$ for the external low scale, and $\mu$ for the renormalization scale. A matching scale $\mu_M$ is usually chosen near $M$:

$$
\mu_M\sim M.
$$

The matching scale is not a physical cutoff. It is a convenient renormalization point at which threshold logarithms are small.

We write Wilson coefficients as

$$
C_i(\mu)=C_i^{(0)}(\mu)+\frac{1}{16\pi^2}C_i^{(1)}(\mu)+\cdots,
$$

when a perturbative loop expansion is available. In a strongly coupled matching problem, the coefficients may instead be estimated by symmetry, dimensional analysis, lattice input, sum rules, experimental data, or nonperturbative methods.

The EFT operator basis should be chosen before matching. Operators related by integrations by parts, field redefinitions, equations of motion, algebraic identities, or symmetry relations should not be double-counted.

## Matching observables

In principle, any complete set of low-energy observables can be used for matching. Common choices include:

| Matching quantity | Typical use |
|---|---|
| on-shell amplitudes | efficient when S-matrix elements are the target |
| off-shell Green functions | useful in gauge-fixed perturbation theory and operator mixing |
| background-field effective action | preserves symmetries and packages many operators at once |
| current matrix elements | useful for weak Hamiltonians, form factors, and HQET |
| static potentials | useful in nonrelativistic and gravitational EFTs |
| thermodynamic functions | useful in finite-temperature dimensional reduction |
| lattice observables | useful when the short-distance theory is nonperturbative |

The matching observable must distinguish the coefficients you want. If two operators give identical matrix elements in the chosen process, that process cannot determine their coefficients separately.

A good matching calculation states:

1. the full theory;
2. the EFT field content;
3. the operator basis;
4. the power-counting order;
5. the renormalization scheme;
6. the matching scale;
7. the infrared regulator or kinematic setup;
8. which observables or Green functions are equated.

## Tree-level matching

The simplest matching happens at tree level. Consider a heavy scalar $H$ coupled to a light scalar $\phi$:

$$
\mathcal L
=\frac12(\partial\phi)^2-\frac12m^2\phi^2
+\frac12(\partial H)^2-\frac12M^2H^2
-\frac{g}{2}H\phi^2.
$$

At tree level, $H$ exchange contributes to light-scalar scattering. The full-theory amplitude contains

$$
\mathcal A_{\text{full}}(p^2)
\supset
-\frac{g^2}{M^2-p^2},
$$

where $p$ is the momentum through the heavy propagator. For $p^2\ll M^2$,

$$
-\frac{g^2}{M^2-p^2}
=
-\frac{g^2}{M^2}
-\frac{g^2p^2}{M^4}
-\frac{g^2p^4}{M^6}
-\cdots.
$$

The EFT therefore contains local operators such as

$$
\mathcal L_{\text{EFT}}
\supset
-\frac{g^2}{8M^2}\phi^4
+\text{derivative operators}.
$$

The numerical factor depends on the convention for the operator normalization. The physics does not: heavy exchange becomes a tower of local interactions.

The same result can be obtained by solving the heavy-field classical equation of motion:

$$
(\Box+M^2)H=-\frac{g}{2}\phi^2,
$$

so that

$$
H=-\frac{g}{2}\frac{1}{M^2+\Box}\phi^2
=-\frac{g}{2M^2}\left(1-\frac{\Box}{M^2}+\cdots\right)\phi^2.
$$

Substituting back gives the same local derivative expansion, up to integrations by parts and operator-basis choices.

## Matching by expanding amplitudes

A standard amplitude matching procedure is:

1. compute $\mathcal A_{\text{full}}$ in the full theory;
2. expand it for $Q\ll M$;
3. compute $\mathcal A_{\text{EFT}}$ using the EFT operator basis;
4. equate the two expansions order by order;
5. solve for $C_i(\mu)$.

For example, if the EFT has

$$
\mathcal A_{\text{EFT}}
=
C_0(\mu)+C_2(\mu)\frac{p^2}{M^2}+O(p^4/M^4),
$$

and the full theory gives

$$
\mathcal A_{\text{full}}
=A_0+A_2\frac{p^2}{M^2}+O(p^4/M^4),
$$

then tree-level matching gives

$$
C_0(\mu_M)=A_0,
\qquad
C_2(\mu_M)=A_2,
$$

modulo the normalization of the EFT operators and any loop or scheme effects.

The EFT is not being fit point-by-point as a function of $p^2$. It is matching Taylor coefficients in the low-energy expansion.

## One-loop matching

At one loop, both the full theory and the EFT may contain loop diagrams. Matching compares the two after renormalization:

$$
\mathcal A_{\text{full}}^{\text{ren}}
=
\mathcal A_{\text{EFT}}^{\text{ren}}.
$$

Schematically,

$$
C_i^{(1)}(\mu_M)
=
\left[\mathcal A_{\text{full}}^{(1)}\right]_i
-
\left[\mathcal A_{\text{EFT loops}}^{(1)}\right]_i,
$$

where the subscript means “project onto the coefficient of the EFT operator structure $\mathcal O_i$.”

This subtraction is the heart of loop matching. The full theory and EFT share the same long-distance physics. The Wilson coefficient should contain only the short-distance difference. Therefore the infrared behavior must be treated identically on both sides.

A common clean method is to use the same external states, the same light masses, the same infrared regulator, and the same renormalization scheme for light fields on both sides. Then infrared logarithms cancel in the difference, leaving a short-distance coefficient.

## Infrared cancellation in matching

Wilson coefficients are short-distance quantities. They should not depend on arbitrary infrared regulators. If a matching result contains uncanceled terms like

$$
\log m_{\text{IR}}
\qquad\text{or}\qquad
\frac{1}{\epsilon_{\text{IR}}},
$$

something is wrong unless those terms are part of a deliberately infrared-sensitive definition.

The cancellation works because the EFT is constructed to reproduce the same low-energy propagation as the full theory. The heavy modes differ; the light modes agree. Thus

$$
\text{matching coefficient}
=
\text{full short-distance part}
-
\text{EFT short-distance overlap convention},
$$

with common infrared pieces canceling.

This is especially important in gauge theories, where individual off-shell Green functions may have gauge-parameter dependence and infrared singularities. Gauge-invariant on-shell matching often avoids some problems, while background-field matching can preserve useful covariance. But no method removes the need to track infrared physics carefully.

## Matching and running

Matching and running answer different questions.

Matching fixes boundary conditions for Wilson coefficients at a scale near the heavy threshold:

$$
C_i(\mu_M)=C_i^{\text{match}}(\mu_M).
$$

Running evolves those coefficients inside the EFT:

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j.
$$

The solution transports the coefficients from $\mu_M$ to a scale $\mu_Q$ appropriate for the low-energy observable:

$$
C_i(\mu_Q)=U_i{}^j(\mu_Q,\mu_M)C_j(\mu_M),
$$

where $U$ is the RG-evolution matrix.

A complete EFT prediction often has the structure

$$
\mathcal A(Q)
=
\sum_i C_i(\mu_Q)\langle\mathcal O_i(\mu_Q)\rangle_Q.
$$

If $M\gg Q$, matching at $\mu_M\sim M$ and evaluating at $\mu_Q\sim Q$ avoids large logarithms in both steps. The RG evolution resums logarithms of $M/Q$.

## Matching versus integrating out

“Integrating out” is a formal operation on the path integral. “Matching” is the determination of the EFT parameters. They are related but not identical.

If the full theory path integral is

$$
Z[J]=\int\mathcal D\phi\,\mathcal DH\,e^{iS[\phi,H]+i\int J\phi},
$$

then integrating out $H$ gives

$$
e^{iS_{\text{eff}}[\phi]}
=
\int\mathcal DH\,e^{iS[\phi,H]}.
$$

This formal effective action can be nonlocal. Expanding it for low momenta gives a local EFT. Matching is the practical procedure that fixes the local coefficients, whether or not the formal path integral can be evaluated exactly.

In many realistic cases, the “full theory” is not known or not perturbative. Then matching may mean using data or nonperturbative input to fix coefficients. EFT logic still applies.

## Matching and scheme dependence

Wilson coefficients are not observables. They depend on:

- the operator basis;
- the renormalization scheme;
- the normalization of operators;
- the definition of evanescent operators in dimensional regularization;
- the treatment of redundant operators;
- the matching scale;
- the field variables used.

Physical predictions do not depend on these choices when coefficients and matrix elements are used consistently.

A basis change

$$
\mathcal O_i'=R_i{}^j\mathcal O_j
$$

requires the inverse transformation on coefficients:

$$
C_i'=(R^{-1})^j{}_i C_j.
$$

If anomalous dimensions are involved, the transformation must also be applied to the RG equations. Comparing Wilson coefficients from two papers without comparing schemes and bases is an elite way to manufacture nonsense.

## Example: Fermi theory from W exchange

At energies far below the $W$ mass, the charged-current weak interaction reduces to a four-fermion operator. In the full electroweak theory, a tree-level amplitude contains a $W$ propagator:

$$
\mathcal A_{\text{full}}
\sim
\frac{g^2}{q^2-M_W^2}
J_\mu J^{\mu\dagger}.
$$

For $q^2\ll M_W^2$,

$$
\frac{g^2}{q^2-M_W^2}
=
-\frac{g^2}{M_W^2}
\left(1+\frac{q^2}{M_W^2}+\cdots\right).
$$

The leading EFT is

$$
\mathcal L_{\text{Fermi}}
=-\frac{G_F}{\sqrt2}J_\mu J^{\mu\dagger}+\cdots,
$$

with tree-level matching giving the familiar schematic relation

$$
\frac{G_F}{\sqrt2}\sim \frac{g^2}{8M_W^2},
$$

up to the precise normalization of the charged current. Higher powers of $q^2/M_W^2$ correspond to higher-dimension derivative operators. Loop matching gives threshold corrections and scheme-dependent finite parts.

## Example: Euler–Heisenberg matching

At photon energies $\omega\ll m_e$, electron loops can be integrated out of QED. The low-energy photon EFT contains operators such as

$$
\mathcal L_{\text{EH}}
\supset
\frac{a}{m_e^4}(F_{\mu\nu}F^{\mu\nu})^2
+
\frac{b}{m_e^4}(F_{\mu\nu}\widetilde F^{\mu\nu})^2
+\cdots.
$$

The coefficients $a$ and $b$ are fixed by matching the four-photon amplitude in full QED to the local photon EFT at low energy. The electron loop is short-distance from the viewpoint of photons with $\omega\ll m_e$, so its effect is encoded in local field-strength operators.

This example is conceptually useful because the EFT has no dynamical electron. If a calculation below $m_e$ accidentally reintroduces low-energy electron propagation, it is no longer the same EFT.

## Background-field matching

Instead of matching individual amplitudes, one can match effective actions in a background field. Split the light fields into slowly varying backgrounds and fluctuations, integrate out the heavy fields, and expand the resulting action in local invariants.

For a gauge theory, background-field matching is especially attractive because it can keep background gauge invariance manifest. The output is a local action built from covariant objects such as

$$
F_{\mu\nu},
\qquad
D_\rho F_{\mu\nu},
\qquad
\bar\psi i\gamma^\mu D_\mu\psi,
\qquad
\bar\psi\Gamma\psi.
$$

One still has to reduce the resulting operator list to an independent basis. Background covariance does not automatically remove redundancies.

## Matching to data

Sometimes the more microscopic theory is unknown or nonperturbative. Then Wilson coefficients are fit to data or extracted from numerical calculations. Examples include low-energy constants in chiral perturbation theory, contact interactions in nuclear EFT, hadronic matrix elements in weak decays, and coefficients in hydrodynamic or condensed-matter EFTs.

This is not a failure of EFT. It is the point. EFT separates universal long-distance structure from a finite number of short-distance constants that must be supplied by experiment, simulation, or a more microscopic theory.

The predictive content comes from the fact that the same coefficient appears in many observables. Once fixed in one set of measurements, it can be used elsewhere within the EFT domain.

## Matching with multiple heavy thresholds

If there are several separated heavy scales,

$$
M_1\gg M_2\gg Q,
$$

it is usually best to match in stages:

$$
\text{full theory}
\xrightarrow{\mu\sim M_1}
\text{EFT}_1
\xrightarrow{\text{run}}
\text{EFT}_1
\xrightarrow{\mu\sim M_2}
\text{EFT}_2
\xrightarrow{\text{run}}
\text{low-energy prediction}.
$$

Each threshold removes the degrees of freedom that are no longer active below that scale. Each running interval resums logarithms between neighboring scales.

Trying to match all the way from $M_1$ to $Q$ in one fixed-order step may leave large logarithms that spoil perturbation theory.

## Common pitfalls

**Matching the wrong theory.** The full theory and EFT must have the same light degrees of freedom in the infrared. If a light mode is accidentally omitted from the EFT, matching will produce nonlocal or infrared-sensitive coefficients.

**Comparing off-shell quantities without controlling field redefinitions.** Off-shell Green functions depend on field variables and gauge choices. They can be useful, but they are not automatically physical.

**Forgetting EFT loops.** At loop level, the EFT side is not just a tree-level operator insertion. EFT loops often contain the same infrared behavior as the full theory and must be included for correct matching.

**Double-counting heavy physics.** Once a heavy particle is integrated out, its effect should appear through Wilson coefficients, not also through explicit low-energy propagation.

**Matching far from the threshold.** Choosing $\mu$ very different from $M$ can move large logarithms into the coefficients. Match near the heavy scale unless there is a reason not to.

**Assuming Wilson coefficients are observables.** They are scheme- and basis-dependent. The observable is the product of coefficients and matrix elements.

**Using too few observables.** If the chosen matching conditions do not distinguish all operators at a given order, some coefficient combinations remain undetermined.

## Relations to other pages

[Cutoff versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/) explains the scale vocabulary used here. [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) tells which coefficients are needed at a given order. [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/) explains why heavy propagation becomes a local tower. [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) will take the boundary conditions from matching and evolve them between scales.

For operator-basis issues, see [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

## Research status

The logic of matching is settled. The technical frontier lies in difficult implementations: multi-loop matching, large operator bases, evanescent operators, gauge-invariant automated matching, nonperturbative matrix elements, EFTs with overlapping momentum regions, and multi-scale threshold problems.

Modern EFT practice often combines matching with amplitude methods, background-field techniques, symbolic operator reduction, lattice calculations, and RG evolution. The conceptual rule remains the same: Wilson coefficients capture short-distance information not generated by the low-energy degrees of freedom themselves.

## Exercises

### Exercise 1: Tree-level heavy exchange

A heavy scalar produces the full-theory low-energy amplitude

$$
\mathcal A_{\text{full}}(p^2)=-\frac{g^2}{M^2-p^2}.
$$

If the EFT amplitude is written

$$
\mathcal A_{\text{EFT}}=C_0+C_2\frac{p^2}{M^2}+O(p^4/M^4),
$$

find $C_0$ and $C_2$ at tree level.

<details><summary><strong>Solution</strong></summary>

Expand the full-theory amplitude:

$$
-\frac{g^2}{M^2-p^2}
=
-\frac{g^2}{M^2}\left(1+\frac{p^2}{M^2}+O(p^4/M^4)\right).
$$

Therefore, in the normalization used in the question,

$$
C_0=-\frac{g^2}{M^2},
\qquad
C_2=-\frac{g^2}{M^2}.
$$

If instead one defines $C_2$ as the coefficient of $p^2$ rather than $p^2/M^2$, the numerical mass dimension assigned to $C_2$ changes. Matching always depends on the operator normalization.

</details>

### Exercise 2: Why infrared terms cancel

Explain why a Wilson coefficient determined by matching should not contain a logarithm of an artificial light mass $m_{\text{IR}}$ introduced only to regulate infrared divergences.

<details><summary><strong>Solution</strong></summary>

A Wilson coefficient describes short-distance physics from modes at or above the heavy scale. An artificial light mass regulates long-distance propagation. Since the EFT and full theory have the same light degrees of freedom, the dependence on the infrared regulator appears on both sides of the matching equation and cancels in the difference used to extract the coefficient. If it does not cancel, then the EFT has not reproduced the same infrared physics, the matching observable was not treated consistently, or the coefficient being defined is not a purely short-distance Wilson coefficient.

</details>

### Exercise 3: Matching and running

Suppose $C(M)=1$ at a matching scale $M$, and below $M$ the coefficient obeys

$$
\mu\frac{dC}{d\mu}=\gamma C,
$$

with constant $\gamma$ at the order considered. Find $C(Q)$ for $Q<M$.

<details><summary><strong>Solution</strong></summary>

The RG equation is

$$
\frac{d\log C}{d\log\mu}=\gamma.
$$

Integrating from $M$ to $Q$ gives

$$
\log\frac{C(Q)}{C(M)}=\gamma\log\frac{Q}{M}.
$$

Since $C(M)=1$,

$$
C(Q)=\left(\frac{Q}{M}\right)^\gamma.
$$

For small $\gamma$, this resums logarithms generated by repeated insertions of the anomalous dimension.

</details>

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, matching, and examples across particle, gravitational, and many-body physics.
- Steven Weinberg, “Phenomenological Lagrangians” and *The Quantum Theory of Fields*, Vol. II, chapter 18, for the general EFT and RG logic.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 22–23 and 33, for nonrenormalizable theories, RG methods, and effective actions from matching.
- Aneesh Manohar, EFT lectures and reviews, for practical matching, Wilson coefficients, and EFT power counting.
- Howard Georgi, EFT lectures and reviews, for the physical interpretation of matching, naturalness, and operator organization.
- Mark Srednicki, *Quantum Field Theory*, sections on the renormalization group and effective field theory, for a compact introduction to matching ideas in perturbative QFT.

## Version history

- 2026-06-18: First polished draft. Added tree-level and loop matching logic, infrared cancellation, scheme dependence, staged threshold matching, examples, and exercises.
