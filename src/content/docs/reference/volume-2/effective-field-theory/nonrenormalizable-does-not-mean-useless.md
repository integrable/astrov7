---
title: "Nonrenormalizable Does Not Mean Useless"
description: "Why higher-dimension operators and nonrenormalizable interactions are predictive in effective field theory once a power-counting accuracy is specified."
sidebar:
  label: "Not Useless"
  order: 11
level: Graduate
status: "Polished draft"
source: "Weinberg 1979 and 1995; Polchinski 1984; Georgi EFT lectures; Burgess 2020, chs. 1–3; Schwartz 2014, chs. 21–23; Srednicki 2007, §§28–29."
topics:
  - effective field theory
  - nonrenormalizable interactions
  - power counting
  - Wilson coefficients
  - predictivity
  - truncation errors
canonicalTopics:
  - nonrenormalizable-theories
  - eft-predictivity
  - higher-dimension-operators
  - low-energy-expansion
researchStatus:
  established:
    - "Nonrenormalizable EFTs are predictive at fixed order in a controlled low-energy expansion, because only finitely many operators contribute at any specified accuracy."
  active:
    - "Modern applications refine power counting, basis reduction, matching, and truncation-error estimates in SMEFT, chiral EFT, gravitational EFT, nuclear EFT, hydrodynamic EFT, amplitudes methods, and automated EFT pipelines."
---

## Summary

The sentence "this interaction is nonrenormalizable" used to sound like a death sentence. In modern QFT it is usually a diagnosis of scope.

A nonrenormalizable interaction is an interaction whose coupling has negative mass dimension in the expansion around a chosen fixed point. In four spacetime dimensions, for example,

$$
\frac{C_6}{M^2}\mathcal O_6
$$

is called nonrenormalizable when $\mathcal O_6$ has engineering dimension $6$. If one insists on using this term as part of a fundamental theory valid to arbitrarily high energy, perturbation theory asks for infinitely many counterterms. But an EFT is not making that promise. It says: work at energies $Q\ll M$, organize all effects in powers of $Q/M$, and keep only the terms needed for the desired accuracy.

The infinite tower is not the problem. It is the bookkeeping device:

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\le d}
+
\sum_{\Delta>d}\frac{C_\Delta(\mu)}{M^{\Delta-d}}\mathcal O_\Delta.
$$

The predictive statement is not "there are finitely many possible operators." There are usually infinitely many. The predictive statement is:

$$
\text{at fixed order in } Q/M,\quad \text{only finitely many independent coefficients are needed.}
$$

That is the whole trick. And it is a very good trick.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![An EFT contains an infinite tower of local operators, but a prediction at fixed accuracy keeps only the finite slice selected by power counting.](/figures/renormalization-rg-eft/nonrenormalizable-predictive-tower.svg)

<figcaption>

A nonrenormalizable EFT contains an infinite tower of allowed local operators. Power counting turns the tower into a predictive expansion: choose a target accuracy, keep the finite set of operators through that order, match or measure their Wilson coefficients, run them if necessary, and quote the omitted tower as a controlled truncation error.

</figcaption>
</figure>

:::note[The modern slogan]
Renormalizable means closed under counterterms in the old all-energies perturbative sense. Predictive means controlled at the accuracy and scale being studied. These are related, but they are not the same word.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

Useful background includes [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Cutoff Versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/).

## Core idea

The old distinction between renormalizable and nonrenormalizable interactions answered a particular question:

> If I keep only this finite set of interactions and demand perturbative closure at arbitrarily high energies, do I need infinitely many new counterterms?

That is a legitimate question. It is not always the most physical question.

EFT asks a different question:

> Given light degrees of freedom, symmetries, locality, and a scale separation $Q\ll M$, how accurately can I predict low-energy observables using a finite number of measured or matched coefficients?

The answer can be excellent even when the EFT contains nonrenormalizable interactions. The nonrenormalizable operators are precisely how unresolved short-distance physics appears at long distances.

A useful way to separate the issues is this table:

| Question | Old renormalizability answer | EFT answer |
|---|---|---|
| How many counterterms are needed to all orders and all energies? | finitely many only for power-counting renormalizable theories | usually infinitely many, because the EFT contains every allowed local operator |
| How many parameters are needed at fixed low-energy accuracy? | finitely many | finitely many |
| What happens near the cutoff or heavy scale? | the theory may fail or require UV completion | the EFT is expected to break down there |
| Is a higher-dimension operator meaningful? | suspicious in a fundamental all-scale theory | exactly the expected imprint of short-distance physics |
| Does failure at high energy mean failure at low energy? | often treated that way historically | no; the expansion has a stated domain of validity |

The phrase "nonrenormalizable theory" is therefore dangerously compressed. It may mean "not UV complete by itself in perturbation theory." It does not mean "unable to make predictions."

## Setup and conventions

We work in $d$ spacetime dimensions and use the conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/). Let the EFT be valid for processes characterized by a physical scale $Q$, with

$$
Q\ll M,
$$

where $M$ is a heavy threshold, a breakdown scale, or an organizing scale. The EFT Lagrangian is written as

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light},\le d}
+
\sum_i \frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

Here:

| Symbol | Meaning |
|---|---|
| $\mathcal O_i$ | local operator made from light fields and derivatives |
| $\Delta_i$ | engineering or assigned EFT dimension of $\mathcal O_i$ |
| $M$ | heavy scale or breakdown scale suppressing the operator |
| $C_i(\mu)$ | dimensionless Wilson coefficient in a chosen scheme and basis |
| $\mu$ | renormalization scale, not the physical cutoff |
| $Q$ | external momentum, mass, temperature, inverse length, or other low-energy scale |

The power-counting estimate for an operator contribution is schematically

$$
\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i
\quad\Longrightarrow\quad
C_i\,Q^d\left(\frac{Q}{M}\right)^{\Delta_i-d}
$$

up to fields, dimensionless couplings, loop factors, angular factors, symmetry-breaking spurions, velocity scalings, and matrix-element normalizations.

The essential property is suppression by powers of $Q/M$. Once $Q/M$ is small, higher-dimension operators are ordered.

## Why infinitely many terms do not destroy predictivity

An EFT Lagrangian usually contains infinitely many terms:

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_0+\frac{1}{M}\mathcal L_1+\frac{1}{M^2}\mathcal L_2+\frac{1}{M^3}\mathcal L_3+\cdots.
$$

This looks terrifying only if one forgets the expansion parameter. Suppose an observable has the low-energy expansion

$$
\mathcal A(Q)
=
A_0
+A_1\frac{Q}{M}
+A_2\left(\frac{Q}{M}\right)^2
+A_3\left(\frac{Q}{M}\right)^3
+\cdots.
$$

A prediction through relative order $(Q/M)^2$ needs only $A_0$, $A_1$, and $A_2$. Those coefficients are built from only the finite set of Wilson coefficients and loops that can contribute at that order. The rest of the Lagrangian estimates the uncertainty:

$$
\delta\mathcal A
=O\left(\left(\frac{Q}{M}\right)^3\right).
$$

This is ordinary scientific life. A Taylor series has infinitely many terms, but nobody refuses to use the first few terms of $\sin x$ at small $x$ because the series continues forever. The nontrivial QFT point is that locality and symmetry tell us what the allowed Taylor coefficients are, and renormalization tells us how to absorb short-distance loop sensitivity into the coefficients.

The predictive ingredients are:

1. a small parameter, such as $Q/M$;
2. a power-counting rule that says which terms appear at each order;
3. a finite independent operator basis at the order of interest;
4. coefficients fixed by matching, data, symmetry, or naturalness assumptions;
5. an error estimate from the first omitted order.

Without these ingredients, a list of higher-dimension operators is just a list. With them, it is an EFT.

## The heavy-exchange example

The cleanest example is a heavy particle exchanged between light particles. Suppose a microscopic theory contains a heavy mediator of mass $M$. At low momentum transfer $q^2\ll M^2$, a tree-level exchange amplitude has the schematic form

$$
\mathcal A_{\text{full}}(q^2)
=-\frac{g^2}{M^2-q^2}.
$$

At low energy,

$$
\mathcal A_{\text{full}}(q^2)
=-\frac{g^2}{M^2}
\left[
1+\frac{q^2}{M^2}
+\left(\frac{q^2}{M^2}\right)^2
+\cdots
\right].
$$

The EFT reproduces this expansion using local operators. The leading term is a contact interaction. The next term is a derivative contact interaction. Then come more derivatives:

$$
\mathcal L_{\text{EFT}}
\supset
\frac{c_0}{M^2}\mathcal O_0
+\frac{c_2}{M^4}\mathcal O_2
+\frac{c_4}{M^6}\mathcal O_4
+\cdots.
$$

The EFT is nonrenormalizable by old power counting because the contact interactions have couplings with negative mass dimension. But at $|q^2|\ll M^2$, it is not merely acceptable; it is the correct low-energy expansion.

If one wants accuracy through $q^2/M^2$, only $c_0$ and $c_2$ are needed. If one wants accuracy through $q^4/M^4$, include $c_4$. The infinite tower is just the Taylor expansion of the unresolved heavy propagator.

:::tip[Integrating out is not forgetting]
The heavy particle disappears as an explicit line in low-energy diagrams. Its effects do not disappear. They become local Wilson coefficients.
:::

## Fermi theory as the classic lesson

The four-fermion theory of weak interactions is historically the example that rehabilitates nonrenormalizable interactions.

At energies much smaller than the $W$-boson mass, weak charged-current exchange is well approximated by a local four-fermion interaction,

$$
\mathcal L_F
\sim
-G_F\,J_\mu^\dagger J^\mu,
\qquad
G_F\sim \frac{g^2}{M_W^2}.
$$

The coefficient $G_F$ has mass dimension $-2$ in four dimensions. The interaction is nonrenormalizable. Still, it gives excellent low-energy predictions for beta decay, muon decay, and many weak processes when used within its domain.

What goes wrong at high energy is not a mysterious inconsistency of low-energy beta decay. The amplitude grows with energy roughly as

$$
\mathcal A\sim G_F Q^2.
$$

When $Q$ approaches the weak scale, the local approximation breaks down. The EFT itself tells us this. The cure is not to throw out the low-energy theory; it is to replace it by a theory with the $W$ boson included explicitly.

The four-fermion theory is therefore predictive and incomplete. That combination is not an embarrassment. It is the normal status of an EFT.

## Gravity as an EFT

General relativity is another essential example. In four dimensions the Einstein-Hilbert term is

$$
\mathcal L_{\text{grav}}
=\frac{M_{\text{Pl}}^2}{2}\sqrt{-g}\,R.
$$

Expanding around a background, graviton interactions are suppressed by powers of $1/M_{\text{Pl}}$. Perturbative quantum gravity is nonrenormalizable in the old sense. Loops generate curvature-squared and higher-curvature counterterms,

$$
\mathcal L_{\text{grav,EFT}}
=\sqrt{-g}\left[
\frac{M_{\text{Pl}}^2}{2}R
+c_1R^2
+c_2R_{\mu\nu}R^{\mu\nu}
+c_3R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right].
$$

As a fundamental all-scale theory, this perturbative expansion is not enough. As a low-energy EFT for gravitons and matter at curvatures small compared with the Planck scale, it is perfectly meaningful. It predicts the form and size of quantum corrections organized by powers of

$$
\frac{Q}{M_{\text{Pl}}}.
$$

Again, nonrenormalizable means "there is a breakdown scale," not "there is no physics."

## Loops in nonrenormalizable EFTs

A common misconception is that tree-level higher-dimension operators are fine, but loops make the EFT collapse. Loops do not collapse the EFT. They enforce its logic.

Suppose the EFT contains an operator

$$
\frac{C_6}{M^2}\mathcal O_6.
$$

Loop diagrams involving $\mathcal O_6$ may produce divergences proportional to dimension-eight operators,

$$
\frac{1}{\epsilon}\frac{C_6^2}{16\pi^2M^4}\mathcal O_8.
$$

The response is not panic. The response is: include the dimension-eight counterterm, because the EFT already told us that every allowed dimension-eight operator must be present at order $1/M^4$.

Thus the loop expansion and the EFT expansion are intertwined. A typical observable has the schematic double expansion

$$
\mathcal A(Q)
=
\sum_{n,L}
\frac{1}{(16\pi^2)^L}
\left(\frac{Q}{M}\right)^n
A_{n,L}\!\big(\log(Q/\mu),C_i(\mu)\big).
$$

The exact counting of $n$ depends on the EFT. In chiral perturbation theory, derivatives and masses have their own chiral order. In nonrelativistic EFTs, velocities can matter. In SCET, soft and collinear modes carry different scalings. But the organizing principle is the same: loops generate local counterterms that appear at definite order in the power counting.

## Renormalizable theories are EFTs too

It is tempting to say:

$$
\text{renormalizable theory} = \text{fundamental theory},
\qquad
\text{nonrenormalizable theory} = \text{approximation}.
$$

That is not the modern view.

A renormalizable Lagrangian can be the leading part of an EFT. For example, the Standard Model contains all operators of dimension $\le 4$ compatible with its gauge symmetries and field content. But if it is an EFT below some higher scale, the full Lagrangian also contains higher-dimension operators:

$$
\mathcal L_{\text{SMEFT}}
=
\mathcal L_{\text{SM}}
+\frac{1}{\Lambda}\mathcal L_5
+\frac{1}{\Lambda^2}\mathcal L_6
+\cdots.
$$

The dimension-four part is special because it dominates at low energies. It is not automatically the whole story.

This reframes renormalizability. Power-counting renormalizable interactions are the relevant and marginal interactions near the Gaussian fixed point in four dimensions. They dominate the infrared expansion. Higher-dimension interactions are suppressed, but they are still real possible effects.

## What predictivity actually requires

A theory is predictive in a regime when it uses fewer inputs than outputs to a specified accuracy. EFT predictivity is therefore conditional and quantitative.

Suppose there are $N_k$ independent Wilson coefficients through order $k$ in the power counting. After those $N_k$ coefficients are fixed by matching or measurement, the EFT can predict all other observables through that order, with errors of order $k+1$.

More compactly:

$$
\text{inputs through order }k
\quad\Longrightarrow\quad
\text{outputs through order }k
+O\big((Q/M)^{k+1}\big).
$$

The number $N_k$ may be large. In SMEFT at dimension six, for example, the number of independent coefficients is not tiny. But large is not the same as infinite, and a large parameter set can still be useful when constrained by symmetry, flavor assumptions, experimental data, positivity, matching hypotheses, or correlations among observables.

The predictive question is not "Are there many Wilson coefficients?" It is:

> At the accuracy and in the sector I care about, how many independent combinations of coefficients enter the observables I can measure?

That is the practical EFT question.

## Truncation error is part of the prediction

A serious EFT prediction should say where it stops. If an observable is computed through order $(Q/M)^k$, then the first omitted terms estimate the truncation error:

$$
\delta_{\text{EFT}}
\sim
\left(\frac{Q}{M}\right)^{k+1}
$$

up to coefficients, loop factors, and accidental enhancements or suppressions.

This error estimate is one of the reasons EFT is powerful. The theory does not merely give a number. It gives a hierarchy of improvements and a way to decide whether the calculation is worth doing at the next order.

For example, if $Q/M\sim 0.1$, then ignoring terms of order $(Q/M)^3$ suggests a nominal error around $10^{-3}$, before coefficient estimates. If the desired precision is only percent level, computing those terms may be overkill. If the desired precision is permille level, they may be essential.

EFT is therefore not only a theory of terms. It is a theory of errors.

## When nonrenormalizable EFTs fail

A nonrenormalizable EFT fails when its expansion fails. Common warning signs include:

| Warning sign | Meaning |
|---|---|
| $Q/M$ is not small | higher-dimension operators are no longer suppressed |
| amplitudes violate perturbative unitarity | the local approximation is being pushed past its domain |
| omitted operators become numerically important | the truncation error is underestimated |
| a new threshold is approached | a field integrated out of the EFT must be restored |
| large logarithms spoil fixed-order perturbation theory | RG improvement or a different EFT is needed |
| power counting is inconsistent with data | the assumed hierarchy or symmetry is wrong |

These are not humiliations. They are diagnostic tools. A good EFT does not hide its breakdown scale. It advertises it.

The failure of Fermi theory near the weak scale points to $W$ and $Z$ bosons. The failure of a pion-only chiral EFT near resonances points to heavier hadronic degrees of freedom. The failure of a nonrelativistic EFT near particle-production thresholds points to missing relativistic degrees of freedom.

## Common pitfalls

**Thinking nonrenormalizable means mathematically meaningless.** A nonrenormalizable EFT can be perfectly well defined order by order in its low-energy expansion.

**Thinking renormalizable means fundamental.** A renormalizable theory can itself be the leading approximation to a deeper EFT.

**Forgetting the accuracy target.** The sentence "infinitely many operators are allowed" is irrelevant until one asks the order in $Q/M$ being computed.

**Comparing coefficients without fixing the basis.** Wilson coefficients depend on operator basis, scheme, scale, and field variables. Physical observables do not.

**Confusing cutoff dependence with physical sensitivity.** A regulator-dependent divergence is absorbed into local coefficients. Physical UV sensitivity is encoded in matched Wilson coefficients and power counting.

**Dropping all higher-dimension operators because they are suppressed.** Suppressed is not zero. Precision physics is often precisely the art of detecting small higher-dimension effects.

**Keeping higher-dimension operators without a power-counting rule.** A random subset of operators is usually not an EFT. It is a guess.

**Treating EFT breakdown as failure of science.** Breakdown is information. It tells us where new degrees of freedom, new symmetries, or a different description must enter.

## Relations to other pages

[Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) explains the older classification in terms of operator dimensions and superficial divergences. This page explains why that classification is not the same as predictivity.

[EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/) gives the conceptual motivation. [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) gives the ordering rule. [Matching](/renormalization-rg-eft/effective-field-theory/matching/) explains how Wilson coefficients inherit microscopic information. [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) explains how those coefficients evolve with $\mu$. [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/) explains when heavy physics becomes local at low energy.

The next chapter, [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/), turns these ideas into a workflow: match at a high scale, run to a low scale, compute matrix elements, and estimate errors.

## Research status

The basic claim of this page is settled: EFTs with nonrenormalizable interactions are predictive at fixed order in a controlled expansion. This is standard across particle physics, nuclear physics, gravity, condensed matter, hydrodynamics, and many-body physics.

What remains active is not the slogan but the implementation. Active work includes constructing complete operator bases, handling redundancies and evanescent operators, automating one-loop and two-loop matching, estimating truncation errors in strongly coupled EFTs, organizing multi-scale EFTs, preserving gauge and spacetime symmetries, and deciding which power counting best describes a given physical system.

There is also a conceptual frontier: some EFTs are local but subtle because of boundaries, defects, dissipation, non-equilibrium dynamics, gravity, nonlocal order parameters, or emergent gauge constraints. The phrase "nonrenormalizable does not mean useless" survives these complications, but the details of the expansion must be handled with care.

## Exercises

### Exercise 1: Heavy exchange becomes a local tower

Let a full-theory tree amplitude be

$$
\mathcal A_{\text{full}}(q^2)=-\frac{g^2}{M^2-q^2}.
$$

Expand it for $|q^2|\ll M^2$ through order $q^4/M^4$. Explain why this expansion corresponds to local EFT operators.

<details><summary><strong>Solution</strong></summary>

Use the geometric series

$$
\frac{1}{M^2-q^2}
=
\frac{1}{M^2}\frac{1}{1-q^2/M^2}
=
\frac{1}{M^2}
\left[
1+\frac{q^2}{M^2}+\frac{q^4}{M^4}+O\left(\frac{q^6}{M^6}\right)
\right].
$$

Therefore

$$
\mathcal A_{\text{full}}(q^2)
=
-\frac{g^2}{M^2}
-\frac{g^2q^2}{M^4}
-\frac{g^2q^4}{M^6}
+O\left(\frac{q^6}{M^8}\right).
$$

Polynomial dependence on $q^2$ corresponds in position space to contact interactions with increasing numbers of derivatives. The leading term is a local contact operator. The $q^2$ term is a two-derivative contact operator. The $q^4$ term is a four-derivative contact operator. The pole at $q^2=M^2$ has disappeared because the EFT is not valid near the heavy-particle threshold.

</details>

### Exercise 2: Finite prediction from an infinite tower

Suppose an EFT amplitude has the schematic expansion

$$
\mathcal A(Q)=A_0+A_2\left(\frac{Q}{M}\right)^2+A_4\left(\frac{Q}{M}\right)^4+\cdots.
$$

If $Q/M=0.2$ and you keep terms through $A_2$, what is the expected parametric size of the first omitted correction? What information would you need to turn this into a numerical error bar?

<details><summary><strong>Solution</strong></summary>

The first omitted term is order

$$
\left(\frac{Q}{M}\right)^4=(0.2)^4=0.0016.
$$

So the nominal truncation error is at the few-per-mille level, times the size of the dimensionless coefficient and matrix element multiplying the omitted term.

To convert this into a numerical error bar, one needs an estimate of $A_4$ relative to the leading terms. This may come from matching, dimensional analysis, naturalness assumptions, known loop factors, symmetry suppressions, experimental fits, or comparison with lower-order terms.

</details>

### Exercise 3: Parametric breakdown of Fermi theory

In Fermi theory, a typical weak amplitude grows parametrically like

$$
\mathcal A\sim G_F Q^2.
$$

Estimate the energy scale where this dimensionless amplitude becomes order one. What does that mean physically?

<details><summary><strong>Solution</strong></summary>

Set

$$
G_F Q^2\sim 1.
$$

Then

$$
Q\sim G_F^{-1/2}.
$$

Since $G_F\sim g^2/M_W^2$, this gives a scale of order the weak scale, up to coupling and numerical factors. Physically, this means the local four-fermion approximation is being pushed beyond its domain. The correct description near and above that scale restores the $W$ boson as an explicit degree of freedom. The low-energy theory was not useless; it was telling us where it stops.

</details>

## References

- Steven Weinberg, "Phenomenological Lagrangians," *Physica A* **96** (1979) 327–340, and *The Quantum Theory of Fields*, especially the modern effective-field-theory perspective.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984) 269–295.
- Howard Georgi, lectures on effective field theory and *Weak Interactions and Modern Particle Theory*.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on decoupling, effective actions, power counting, and matching.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, and the renormalization group.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on the renormalization group and effective field theory.
- Aneesh V. Manohar, "Effective Field Theories," for a concise modern review of EFT logic and power counting.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian viewpoint behind effective descriptions.

## Version history

- 2026-06-18: First polished draft. Added the finite-accuracy predictivity criterion, heavy-exchange example, Fermi-theory example, gravitational EFT example, loop-renormalization discussion, truncation-error logic, exercises, and a figure explaining how an infinite operator tower becomes a finite prediction.
