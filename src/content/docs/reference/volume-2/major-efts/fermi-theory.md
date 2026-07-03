---
title: "Fermi Theory"
description: "Fermi theory as the prototype effective field theory: integrating out the W boson, matching to four-fermion operators, defining G_F, and understanding the validity of weak interactions at low energy."
sidebar:
  label: "Fermi Theory"
  order: 10
level: Graduate
status: "Polished draft"
source: "Burgess 2020, ch. 7; Schwartz 2014, chs. 22 and 29; Srednicki 2007, §29 and electroweak chapters; Weinberg 1996, weak interactions and EFT; Coleman 1985, weak-current and soft-pion lectures."
topics:
  - Fermi theory
  - four-fermion operators
  - weak interactions
  - matching
  - decoupling
  - Fermi constant
  - nonrenormalizable EFT
canonicalTopics:
  - fermi-theory
  - four-fermion-effective-interaction
  - weak-effective-field-theory
researchStatus:
  established:
    - "Fermi theory is the classic low-energy EFT of charged-current weak interactions, obtained by integrating out the W boson and expanding amplitudes in powers of Q^2/M_W^2."
  active:
    - "Precision weak decays, semileptonic flavor physics, nuclear beta decay, and weak effective Hamiltonians remain active because radiative corrections, hadronic matrix elements, and operator mixing must be controlled carefully."
---

## Summary

Fermi theory is the prototype effective field theory. At energies much smaller than the $W$-boson mass, weak charged-current processes do not resolve the propagation of the $W$. The full electroweak interaction can then be replaced by a local four-fermion interaction,

$$
\mathcal L_{\mathrm F}
=-\frac{4G_F}{\sqrt2}
(\bar\nu_\mu\gamma^\mu P_L\mu)
(\bar e\gamma_\mu P_L\nu_e)
+\text{h.c.}
$$

for muon decay, with

$$
P_L=\frac{1-\gamma^5}{2}.
$$

At tree level in the Standard Model,

$$
\frac{G_F}{\sqrt2}=\frac{g_2^2}{8M_W^2},
$$

up to electroweak radiative corrections when $G_F$ is related to measured input parameters. The important point is not the historical accident of the notation $G_F$. The important point is the EFT mechanism:

$$
\frac{-i}{q^2-M_W^2}
=\frac{i}{M_W^2}
\left(1+\frac{q^2}{M_W^2}+\cdots\right),
\qquad |q^2|\ll M_W^2.
$$

A nonlocal exchange amplitude becomes a local operator expansion. The leading operator has dimension six, so its coefficient has dimension $-2$. That is why Fermi theory is nonrenormalizable in the old sense and perfectly predictive in the EFT sense.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Tree-level matching from W-boson exchange to the Fermi four-fermion contact operator](/figures/renormalization-rg-eft/fermi-theory-w-exchange-matching.svg)

<figcaption>

At energies $Q\ll M_W$, the $W$ propagator can be expanded in powers of $Q^2/M_W^2$. The leading term is a local four-fermion operator. With left-handed projectors included in the currents, the muon-decay convention is $4G_F/\sqrt2=g_2^2/(2M_W^2)$ at tree level.

</figcaption>
</figure>

:::note[Why this page matters]
Fermi theory is the cleanest antidote to the phrase "nonrenormalizable means useless." It is nonrenormalizable, historically older than the Standard Model, and nevertheless one of the most successful EFTs ever written.
:::

## Prerequisites

You should know the basic EFT logic from [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/). You should also be comfortable with tree-level amplitudes, Dirac spinor bilinears, projection operators, and the idea that the Standard Model contains charged weak interactions mediated by $W^\pm$ bosons.

This page uses the mostly-minus metric and the scattering conventions fixed in the site conventions. The charged-current conventions are chosen so that the muon-decay operator with $P_L$ projectors has coefficient $4G_F/\sqrt2$.

## Core idea

Fermi theory describes weak processes at energies far below $M_W$. The theory keeps the light fermions explicitly and removes the heavy $W$ boson from the list of propagating degrees of freedom. Its leading local interaction has the schematic form

$$
\mathcal L_{\mathrm F}\sim G_F(\bar\psi\psi)(\bar\psi\psi),
\qquad [G_F]=-2.
$$

The coefficient is small not because weak interactions are morally weak, but because the mediator is heavy:

$$
G_F\sim \frac{1}{M_W^2}.
$$

At momentum transfer $Q$, the EFT expansion parameter is

$$
\frac{Q^2}{M_W^2}.
$$

For muon decay, beta decay, and many low-energy neutrino processes, this ratio is tiny. The local theory is therefore excellent. At energies comparable to $M_W$, the contact interaction is no longer a good description: the $W$ propagator, electroweak gauge structure, and eventually the full Standard Model must be restored.

## Setup and conventions

### The full-theory charged current

The charged-current part of the Standard Model can be written schematically as

$$
\mathcal L_{\mathrm{cc}}
=-\frac{g_2}{\sqrt2}
\left(J_\mu^+W^{+\mu}+J_\mu^-W^{-\mu}\right),
$$

where

$$
J_\mu^+
=\bar u_L\gamma_\mu V d_L
+\bar\nu_L\gamma_\mu e_L
+\cdots,
\qquad
J_\mu^-=(J_\mu^+)^\dagger.
$$

Here $V$ is the CKM matrix in the quark sector. For purely leptonic muon decay, the relevant pieces are

$$
J_\mu^+\supset \bar\nu_{\mu L}\gamma_\mu\mu_L,
\qquad
J_\mu^-\supset \bar e_L\gamma_\mu\nu_{eL}.
$$

Equivalently,

$$
\bar\nu_{\mu L}\gamma_\mu\mu_L
=\bar\nu_\mu\gamma_\mu P_L\mu,
\qquad
\bar e_L\gamma_\mu\nu_{eL}
=\bar e\gamma_\mu P_L\nu_e.
$$

The tree-level full-theory amplitude for muon decay contains a $W$ propagator. Suppressing spinor wave functions, the relevant factor is

$$
\left(-\frac{ig_2}{\sqrt2}\right)^2
\frac{-i}{q^2-M_W^2}
\left(\bar\nu_\mu\gamma^\mu P_L\mu\right)
\left(\bar e\gamma_\mu P_L\nu_e\right),
$$

up to terms in the gauge-boson propagator that do not affect the leading low-energy current-current result for light external fermions. For $|q^2|\ll M_W^2$,

$$
\frac{1}{q^2-M_W^2}
=-\frac{1}{M_W^2}\left(1+\frac{q^2}{M_W^2}+\cdots\right).
$$

The leading term is momentum independent. Momentum independence in an amplitude is the signature of a local interaction in the EFT.

## Tree-level matching

The leading Fermi operator for muon decay is

$$
\mathcal O_{\mu e}
=(\bar\nu_\mu\gamma^\mu P_L\mu)
(\bar e\gamma_\mu P_L\nu_e).
$$

Write the EFT interaction as

$$
\mathcal L_{\mathrm F}
=-C_{\mu e}\mathcal O_{\mu e}+\text{h.c.}
$$

Matching the low-energy full-theory amplitude to the EFT amplitude gives, at tree level,

$$
C_{\mu e}=\frac{g_2^2}{2M_W^2}.
$$

The conventional Fermi constant is defined by

$$
C_{\mu e}\equiv \frac{4G_F}{\sqrt2}.
$$

Therefore

$$
\frac{G_F}{\sqrt2}=\frac{g_2^2}{8M_W^2}
$$

at tree level.

This is the cleanest matching calculation in EFT. The full theory has a propagating heavy field. The EFT does not. Equality of low-energy amplitudes fixes the local coefficient.

:::tip[The factor-of-four trap]
Some books write the charged current with $1-\gamma^5$ rather than $P_L=(1-\gamma^5)/2$. Then the same physics is written with a coefficient $G_F/\sqrt2$ instead of $4G_F/\sqrt2$. Before comparing formulas, check whether the left-handed projector includes the factor of $1/2$.
:::

## Muon decay and the normalization of G_F

Ignoring the electron mass and radiative corrections, the muon decay width is

$$
\Gamma(\mu^-\to e^-\bar\nu_e\nu_\mu)
=\frac{G_F^2m_\mu^5}{192\pi^3}.
$$

This formula is one of the reasons $G_F$ is such a useful input parameter. Experimentally, the muon lifetime determines $G_F$ very precisely after phase-space, electron-mass, QED, and electroweak corrections are included.

Conceptually, the formula also teaches three EFT lessons.

First, dimensional analysis almost fixes the answer. Since $[G_F]=-2$ and the decay rate has dimension one,

$$
\Gamma\sim G_F^2m_\mu^5.
$$

The nontrivial work is the spin sum and three-body phase-space integral, which produce $1/(192\pi^3)$.

Second, the EFT is organized by powers of $m_\mu^2/M_W^2$, not by powers of $G_Fm_\mu^2$ alone. The leading operator is dimension six. The next terms from the $W$ propagator expansion and from electroweak matching are suppressed by additional powers of $m_\mu^2/M_W^2$.

Third, $G_F$ is an operationally defined low-energy parameter. In a full Standard Model analysis, the relation between $G_F$, $M_W$, $M_Z$, $\alpha$, the weak mixing angle, and the Higgs/top sector includes radiative corrections. The tree-level formula is a matching result, not a substitute for precision electroweak renormalization.

## Beta decay and semileptonic currents

For nuclear beta decay and semileptonic weak processes, Fermi theory contains quark currents. At the quark level, the leading charged-current operator is

$$
\mathcal L_{\beta}
=-\frac{4G_F}{\sqrt2}V_{ud}
(\bar u\gamma^\mu P_L d)
(\bar e\gamma_\mu P_L\nu_e)
+\text{h.c.}
$$

More generally,

$$
\mathcal L_{\mathrm{semileptonic}}
=-\frac{4G_F}{\sqrt2}V_{ij}
(\bar u_i\gamma^\mu P_L d_j)
(\bar\ell\gamma_\mu P_L\nu_\ell)
+\text{h.c.}
$$

The coefficient contains short-distance weak information, while the hadronic matrix element

$$
\langle \text{hadrons}\mid \bar u_i\gamma^\mu P_L d_j\mid \text{hadrons}\rangle
$$

contains long-distance QCD. For free quarks, the current is simple. For nucleons, pions, or nuclei, the same quark operator must be represented in an appropriate low-energy hadronic EFT or evaluated nonperturbatively.

This is not a defect in Fermi theory. It is exactly how EFT compartmentalizes the problem:

$$
\text{short-distance weak physics}
\quad\times\quad
\text{long-distance hadronic matrix elements}.
$$

## Four-fermion operators and Fierz rearrangements

Four-fermion operators are not unique as written. Spinor identities can rearrange them. For example, an operator may be written schematically as

$$
(\bar\psi_1\Gamma_A\psi_2)(\bar\psi_3\Gamma_B\psi_4)
$$

or, after a Fierz transformation, as a sum of operators pairing the spinors differently. In chiral weak interactions, the most common structure is vector-minus-axial,

$$
\gamma^\mu P_L.
$$

The four-fermion form makes the low-energy chirality structure transparent: charged weak interactions couple to left-handed fermions and right-handed antifermions.

In purely leptonic muon decay, Fierz issues are mostly a convention nuisance. In nonleptonic weak decays, they become central because color structures, current-current operators, penguin operators, and operator mixing under QCD all matter. That more elaborate weak effective Hamiltonian is built on the same Fermi-theory logic.

## Power counting and validity

The leading Fermi operator has dimension six, so a typical amplitude scales as

$$
\mathcal A_{\mathrm F}\sim G_FE^2.
$$

A cross section at low energy then often scales as

$$
\sigma\sim G_F^2E^2,
$$

up to angular factors, masses, and process-dependent coefficients. This energy growth is not a paradox at low energy; it is the expected dimensional behavior of a dimension-six interaction.

It does, however, tell you where the EFT must fail. A contact interaction whose amplitude grows like $G_FE^2$ cannot remain valid indefinitely. Parametrically, perturbative unitarity warns us when

$$
G_FE^2\sim 1,
$$

which is the same rough scale as the electroweak scale. The cure is not to add one magical counterterm and continue forever. The cure is to restore the degrees of freedom that were integrated out, starting with the $W$ boson and the full electroweak gauge theory.

The leading EFT expansion is

$$
\mathcal L_{\mathrm{EFT}}
=\mathcal L_{\text{light}}
+\frac{1}{M_W^2}\mathcal O_6
+\frac{1}{M_W^4}\mathcal O_8
+\cdots.
$$

For an observable at scale $Q$,

$$
\frac{\Delta\mathcal A_{8}}{\mathcal A_6}
\sim \frac{Q^2}{M_W^2}.
$$

Fermi theory is therefore excellent for muon decay and many nuclear processes, but it is the wrong language for producing real $W$ bosons at colliders.

## Loops in Fermi theory

Because the Fermi operator is dimension six, loops in Fermi theory generate divergences that require higher-dimension counterterms. For example, a loop with two insertions of the dimension-six operator can generate local structures suppressed by higher powers of $G_F$ and carrying additional derivatives or fields.

In old language, this means Fermi theory is nonrenormalizable. In modern EFT language, it means the EFT is renormalized order by order in the expansion. If you compute only to leading order in $Q^2/M_W^2$, you need only the operators that contribute at that order. If you compute to higher accuracy, you include the additional local terms required by power counting.

The lesson is:

$$
\text{nonrenormalizable}
\neq
\text{unpredictive}.
$$

Unpredictive would mean requiring infinitely many independent measurements for one finite-accuracy prediction. EFT does not do that. At any fixed order in $Q/M_W$, only finitely many operators contribute.

## Running and radiative corrections

For purely leptonic muon decay, much of the practical work lies in QED corrections, phase-space effects, and precision electroweak matching. For semileptonic and nonleptonic processes, QCD makes the Wilson-coefficient evolution essential.

A weak effective Hamiltonian is often written as

$$
\mathcal H_{\mathrm{eff}}
=\sum_i C_i(\mu)\mathcal O_i(\mu).
$$

Scale independence of physical amplitudes requires

$$
\mu\frac{d}{d\mu}\mathcal H_{\mathrm{eff}}=0.
$$

If the operators mix as

$$
\mu\frac{d}{d\mu}\mathcal O_i=-\gamma_i{}^j\mathcal O_j,
$$

then the coefficients obey

$$
\mu\frac{d}{d\mu}C_i=C_j\gamma_i{}^j,
$$

with the precise matrix-convention depending on row/column choices. This is the same dual evolution explained in the matching and operator-basis pages.

Running is not a decorative improvement. It resums logarithms such as

$$
\alpha_s^n\log^n\frac{M_W}{\mu}
$$

that appear when matching occurs at a high scale but matrix elements are evaluated at a lower hadronic scale.

## Relation to the Standard Model

Fermi theory is not a rival to the Standard Model. It is the Standard Model seen through a low-energy lens.

At energies below $M_W$, the heavy electroweak fields are not resolved. Their effects appear as Wilson coefficients. At energies near or above $M_W$, the EFT description breaks down and the full electroweak gauge theory becomes necessary.

The conceptual chain is

$$
SU(2)_L\times U(1)_Y\text{ gauge theory}
\quad\xrightarrow{\text{electroweak symmetry breaking}}\quad
W^\pm,Z,h,\gamma
\quad\xrightarrow{Q\ll M_W}\quad
\text{Fermi theory}.
$$

In modern language, Fermi theory is also the lowest-dimensional piece of a weak effective theory below the electroweak scale. For physics above the electroweak scale but below possible heavy new physics, the appropriate language is usually SMEFT, not the old four-fermion Fermi theory.

## Common pitfalls

**Forgetting the projector convention.** With $P_L=(1-\gamma^5)/2$, the muon-decay operator has coefficient $4G_F/\sqrt2$. With $(1-\gamma^5)$ written explicitly instead, the coefficient looks like $G_F/\sqrt2$. These are the same convention dressed differently.

**Calling the Fermi interaction fundamental at all energies.** The contact interaction is the low-energy expansion of $W$ exchange. It is not meant to describe real $W$ production or high-energy electroweak scattering.

**Saying Fermi theory is invalid because it is nonrenormalizable.** It is invalid only outside its regime or beyond the order to which its operator expansion has been specified. Within its regime, it is a controlled EFT.

**Confusing $G_F$ with a gauge coupling.** $G_F$ has mass dimension $-2$. It is not the same kind of object as $g_2$. At tree level $G_F$ is proportional to $g_2^2/M_W^2$.

**Ignoring hadronic matrix elements.** In semileptonic and nonleptonic processes, the weak coefficient is only half the story. Long-distance QCD must still be handled by symmetry, lattice QCD, chiral perturbation theory, heavy-quark methods, or phenomenological input.

**Matching at one scale and evaluating at another without running.** If large logarithms appear, Wilson coefficients must be evolved between scales.

## Relations to other pages
This page is the simplest worked example of [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/) and [Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/). It is also the canonical example behind [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/).

For the general coefficient evolution used in weak effective Hamiltonians, see [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/). For operator bases and Fierz/EOM issues, see [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/). For the full electroweak theory, continue to the gauge-theory and Standard Model volumes.

## Research status

The existence and interpretation of Fermi theory as the low-energy EFT of charged-current weak interactions is settled. The leading tree-level matching relation is elementary, and the muon lifetime provides one of the cleanest precision definitions of $G_F$.

What remains active is not the principle but the precision frontier: radiative corrections, hadronic matrix elements, nuclear beta-decay corrections, CKM extractions, rare decays, flavor-changing processes, operator mixing, lattice inputs, and searches for tiny deviations from the Standard Model pattern. In these applications, the humble Fermi interaction becomes part of a larger weak effective Hamiltonian.

## Exercises

### Exercise 1: Dimension of the Fermi constant

In four spacetime dimensions, a Dirac field has engineering dimension $3/2$. Show that the coefficient of a four-fermion operator has mass dimension $-2$.

<details><summary><strong>Solution</strong></summary>

A four-fermion operator contains four Dirac fields, so

$$
[(\bar\psi\psi)(\bar\psi\psi)]=4\cdot\frac32=6.
$$

The Lagrangian density has dimension $4$. If

$$
\mathcal L\supset C\mathcal O_6,
$$

then

$$
[C]=4-6=-2.
$$

Thus $G_F$ has dimension $-2$, consistent with $G_F\sim 1/M_W^2$.

</details>

### Exercise 2: Leading W-propagator expansion

Starting from the scalar part of the $W$ propagator denominator, expand

$$
\frac{1}{q^2-M_W^2}
$$

for $|q^2|\ll M_W^2$ and identify the relative size of the first correction to the Fermi interaction.

<details><summary><strong>Solution</strong></summary>

Factor out $-M_W^2$:

$$
\frac{1}{q^2-M_W^2}
=-\frac{1}{M_W^2}\frac{1}{1-q^2/M_W^2}.
$$

For $|q^2|\ll M_W^2$,

$$
\frac{1}{1-q^2/M_W^2}
=1+\frac{q^2}{M_W^2}+O\left(\frac{q^4}{M_W^4}\right).
$$

Therefore

$$
\frac{1}{q^2-M_W^2}
=-\frac{1}{M_W^2}
\left[1+\frac{q^2}{M_W^2}+O\left(\frac{q^4}{M_W^4}\right)\right].
$$

The leading term gives the dimension-six Fermi operator. The first correction is suppressed by $q^2/M_W^2$ and corresponds to higher-dimension operators with derivatives.

</details>

### Exercise 3: Scaling of the muon decay width

Use dimensional analysis to show that the leading muon decay width must scale as $G_F^2m_\mu^5$ when $m_e$ and neutrino masses are neglected.

<details><summary><strong>Solution</strong></summary>

A decay width has mass dimension one. The Fermi constant has dimension $-2$, so $G_F^2$ has dimension $-4$. If the only available mass scale is $m_\mu$, the width must scale as

$$
\Gamma\sim G_F^2m_\mu^n.
$$

Dimensional consistency requires

$$
-4+n=1,
$$

so $n=5$. Thus

$$
\Gamma\sim G_F^2m_\mu^5.
$$

The exact tree-level coefficient for massless final particles is $1/(192\pi^3)$.

</details>

### Exercise 4: When does the contact theory warn you?

A rough high-energy estimate gives a four-fermion amplitude $\mathcal A\sim G_FE^2$. Estimate the scale at which perturbation theory in the contact interaction stops looking small.

<details><summary><strong>Solution</strong></summary>

The contact-theory expansion parameter is roughly

$$
G_FE^2.
$$

It becomes order one when

$$
E\sim G_F^{-1/2}.
$$

Since $G_F\sim 1/M_W^2$ up to coupling factors, this is parametrically the electroweak scale. The exact numerical partial-wave bound depends on the process and angular-momentum channel, but the message is robust: the Fermi contact theory itself announces the need for new degrees of freedom near the weak scale.

</details>

## References

- E. Fermi, "Versuch einer Theorie der β-Strahlen," *Zeitschrift für Physik* **88** (1934) 161–177, for the original four-fermion theory of beta decay.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapter 7, for Fermi theory as a modern EFT example.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 22 and 29, for nonrenormalizable interactions, weak interactions, and the four-Fermi theory.
- Mark Srednicki, *Quantum Field Theory*, section 29 and electroweak chapters, for EFT logic and the Standard Model context.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, for weak interactions, chiral dynamics, and the effective-Lagrangian viewpoint.
- Sidney Coleman, *Aspects of Symmetry*, especially soft-pion and weak-current lectures, for current algebra and low-energy weak-interaction perspective.
- A. J. Buras, "Weak Hamiltonian, CP Violation and Rare Decays," for the weak effective Hamiltonian and operator mixing in flavor physics.

## Version history

- 2026-06-19: First polished draft. Added tree-level $W$-exchange matching, $G_F$ conventions, muon-decay normalization, power counting, running, pitfalls, and exercises.
