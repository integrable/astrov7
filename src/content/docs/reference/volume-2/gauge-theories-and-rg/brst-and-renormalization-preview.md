---
title: "BRST and Renormalization Preview"
description: "A preview of BRST symmetry as the nilpotent remnant of gauge redundancy that controls physical states, counterterms, anomalies, and renormalized gauge theory."
sidebar:
  label: "BRST and Renormalization Preview"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§71–74 and 78; Schwartz 2014, chs. 14, 19, 26, 30, and 34; Weinberg Vol. II, gauge-theory and anomaly chapters; Zinn-Justin 2021, BRST and algebraic renormalization sections."
topics:
  - BRST symmetry
  - nilpotent charge
  - gauge fixing
  - Faddeev–Popov ghosts
  - physical cohomology
  - algebraic renormalization
canonicalTopics:
  - brst-symmetry
  - brst-cohomology
  - gauge-theory-renormalization
researchStatus:
  established:
    - "BRST symmetry is the standard perturbative framework for gauge fixing, ghost fields, physical-state cohomology, and Slavnov–Taylor identities."
  active:
    - "BRST and its BV extension remain central in modern gauge theory, anomalies, perturbative algebraic QFT, EFT basis reduction, and higher-gauge or topological field theories."
---

## Summary

BRST symmetry is the cleanest way to say what remains of gauge redundancy after gauge fixing. It introduces a fermionic differential $s$ with

$$
s^2=0,
$$

and packages gauge transformations, ghost fields, gauge fixing, and unphysical-polarization cancellation into one algebraic structure.

For Yang–Mills theory in a covariant gauge, the basic BRST transformations are

$$
sA^a_\mu=D_\mu^{ab}c^b,
\qquad
sc^a=-\frac{g}{2}f^{abc}c^bc^c,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

The gauge-fixed action is BRST invariant. The quantum version of this invariance is the Slavnov–Taylor identity. The physical states are BRST cohomology classes, and the allowed counterterms are local BRST cohomology classes at ghost number zero.

The short version is

$$
\text{BRST symmetry}=\text{gauge redundancy after gauge fixing, written as cohomology}.
$$

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Flow chart from gauge fixing and ghosts to BRST symmetry, Slavnov–Taylor identities, local counterterms, BRST cohomology, and possible anomaly obstructions.](/figures/renormalization-rg-eft/brst-renormalization-cohomology.svg)

<figcaption>

BRST symmetry is the algebraic bridge from gauge-fixed perturbation theory to constrained renormalization. The Slavnov–Taylor identity imposes a local cohomology problem on counterterms: physical counterterms are BRST-closed modulo BRST-exact redefinitions, while genuine gauge anomalies appear as nontrivial ghost-number-one obstructions.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/), [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/), and [Slavnov–Taylor Identities Preview](/renormalization-rg-eft/gauge-theories-and-rg/slavnov-taylor-identities-preview/). You should also be comfortable with ghost fields in Faddeev–Popov gauge fixing.

This page is a preview. It focuses on how BRST symmetry organizes renormalization. The full construction belongs in the Gauge Theories and Symmetry volumes, where one can discuss canonical BRST charge, unitarity, anomalies, BV formalism, and global subtleties with more care.

## Core idea

Gauge symmetry is not an ordinary physical symmetry. It is a redundancy in description. Gauge fixing removes the redundancy enough to define propagators, but it introduces a problem: the gauge-fixed action no longer has manifest gauge invariance, and covariant gauges contain unphysical degrees of freedom.

BRST symmetry solves both problems at once. It replaces the original gauge symmetry by a global fermionic symmetry acting on gauge fields, ghosts, antighosts, and auxiliary fields. Its nilpotency,

$$
s^2=0,
$$

turns gauge redundancy into cohomology. Exact states, exact operators, and exact deformations are considered physically trivial in the appropriate sense.

This is why BRST is not just a clever trick for deriving Ward identities. It is the organizing principle behind renormalized covariant gauge theory.

## Setup and conventions

For a Yang–Mills gauge field $A^a_\mu$, define

$$
F^a_{\mu\nu}
=\partial_\mu A^a_\nu-\partial_\nu A^a_\mu
+g f^{abc}A^b_\mu A^c_\nu,
$$

and

$$
D_\mu^{ab}c^b=\partial_\mu c^a+g f^{acb}A^c_\mu c^b.
$$

The gauge-invariant part of the action is

$$
\mathcal L_{\text{YM}}=-\frac14F^a_{\mu\nu}F^{a\mu\nu}.
$$

A covariant gauge-fixing fermion may be written as

$$
\Psi=\bar c^a\left(\partial^\mu A^a_\mu+\frac{\xi}{2}B^a\right).
$$

The gauge-fixing plus ghost Lagrangian is BRST exact:

$$
\mathcal L_{\text{gf+gh}}=s\Psi
=B^a\partial^\mu A^a_\mu
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

Eliminating $B^a$ gives the more familiar covariant-gauge term

$$
\mathcal L_{\text{gf}}=-\frac{1}{2\xi}\left(\partial^\mu A^a_\mu\right)^2
$$

up to sign conventions associated with Lorentzian continuation and the choice of $B^a$ normalization.

## Ghost number

BRST transformations carry ghost number $+1$. The assignments are

| Object | Ghost number |
|---|---:|
| $A^a_\mu$, $B^a$, ordinary matter fields | $0$ |
| $c^a$ | $+1$ |
| $\bar c^a$ | $-1$ |
| $s$ | $+1$ |

The action has ghost number zero. Physical local counterterms must also have ghost number zero. Gauge anomalies appear as possible ghost-number-one breakings of the Slavnov–Taylor identity.

This grading is not cosmetic. It is what prevents the cohomology problem from becoming mush. Counterterms, anomalies, gauge-fixing changes, and physical observables live in different ghost-number sectors.

## Nilpotency

The nilpotency $s^2=0$ is the algebraic form of closure of the gauge algebra.

For the ghost,

$$
sc^a=-\frac{g}{2}f^{abc}c^bc^c.
$$

Applying $s$ again gives a cubic ghost expression proportional to the Jacobi identity for $f^{abc}$. Thus

$$
s^2c^a=0.
$$

For the gauge field,

$$
sA^a_\mu=D_\mu^{ab}c^b.
$$

A second BRST variation gives the covariant derivative of $sc$ plus the variation of the gauge field inside $D_\mu$. The two contributions cancel because the gauge algebra closes. Therefore

$$
s^2A^a_\mu=0.
$$

This computation is the ghost-language version of a familiar statement: two infinitesimal gauge transformations commute into another gauge transformation, with structure constants fixed by the Lie algebra.

## Physical states and observables

In canonical language, BRST symmetry is generated by a nilpotent charge $Q_{\text{BRST}}$:

$$
Q_{\text{BRST}}^2=0.
$$

Physical states are closed modulo exact states:

$$
Q_{\text{BRST}}\mid\text{phys}\rangle=0,
\qquad
\mid\text{phys}\rangle\sim
\mid\text{phys}\rangle+Q_{\text{BRST}}\mid\chi\rangle.
$$

This quotient removes unphysical gauge polarizations and ghosts from the physical spectrum. It also explains why BRST-exact operator insertions vanish between physical states, provided no anomaly or boundary subtlety spoils the argument.

For local operators, the analogous condition is

$$
s\mathcal O=0,
\qquad
\mathcal O\sim \mathcal O+s\mathcal X.
$$

Gauge-invariant operators define BRST-closed classes. Operators that differ by BRST-exact terms represent the same physical insertion in separated gauge-invariant correlators.

## BRST and counterterms

Renormalization asks which local counterterms can be added while preserving the defining identities of the theory. BRST says the answer in cohomological language.

Let $\Gamma$ be the renormalized effective action. The Slavnov–Taylor identity is

$$
\mathcal S(\Gamma)=0.
$$

At a given loop order, local counterterms must solve the linearized condition

$$
\mathcal B_\Gamma\Gamma_{\text{ct}}=0,
$$

where $\mathcal B_\Gamma$ is the linearized Slavnov–Taylor operator. Two counterterms that differ by a BRST-exact term,

$$
\Gamma_{\text{ct}}\sim \Gamma_{\text{ct}}+\mathcal B_\Gamma X,
$$

are related by field redefinitions, gauge-parameter changes, or other redundant choices.

The physically meaningful counterterms are therefore cohomology classes at ghost number zero. In ordinary Yang–Mills theory, the main class is the gauge-invariant field-strength term,

$$
\int d^d x\,F^a_{\mu\nu}F^{a\mu\nu},
$$

along with matter kinetic terms, masses, gauge-invariant interactions, and BRST-exact gauge-fixing or field-redefinition terms.

## BRST and anomalies

Gauge anomalies are also classified by BRST cohomology, but at ghost number one.

If the Slavnov–Taylor identity fails by a local term,

$$
\mathcal S(\Gamma)=\Delta,
$$

then consistency requires

$$
\mathcal B_\Gamma\Delta=0.
$$

If

$$
\Delta=\mathcal B_\Gamma X,
$$

then the breaking can be removed by a local counterterm. If not, it is a genuine anomaly. In that case the gauge theory is inconsistent unless the anomaly cancels among all fields.

The standard chiral gauge anomaly fits this pattern. In four dimensions, the dangerous contribution is controlled by the group-theoretic cubic trace

$$
\operatorname{tr}_R\left(T^a\{T^b,T^c\}\right).
$$

A consistent chiral gauge theory requires the sum of this tensor over all left-handed fermion representations to vanish.

## Renormalization without losing gauge theory

BRST is the reason covariant renormalized Yang–Mills theory remains a gauge theory rather than degenerating into a general theory of interacting vector fields.

Power counting alone would allow many local terms. Lorentz symmetry alone would allow even more. BRST narrows the allowed counterterms to gauge-invariant physical terms plus BRST-exact redundancies. This is why renormalization can shift

$$
g,
\qquad
Z_A,
\qquad
Z_c,
\qquad
Z_\psi,
\qquad
\xi,
$$

while preserving the gauge-theory form of the interactions.

The moral is subtle but important: gauge fixing breaks manifest gauge invariance, but BRST keeps enough of it alive to make the renormalized theory consistent.

## Worked example: BRST-exact gauge fixing

Start with

$$
\Psi=\bar c^a\left(\partial^\mu A^a_\mu+\frac{\xi}{2}B^a\right).
$$

Using

$$
s\bar c^a=B^a,
\qquad
sA^a_\mu=D_\mu^{ab}c^b,
\qquad
sB^a=0,
$$

and remembering that $s$ is odd, we find

$$
s\Psi
=B^a\left(\partial^\mu A^a_\mu+\frac{\xi}{2}B^a\right)
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

Thus the gauge-fixing and ghost terms are not arbitrary additions. They are one BRST-exact package. The ghost term is forced by the BRST variation of the gauge-fixing condition.

## Common pitfalls

**Saying BRST is a physical supersymmetry.** BRST is fermionic, but it is not spacetime supersymmetry. It is a cohomological symmetry associated with gauge redundancy.

**Thinking ghosts are external particles.** Ghosts are internal bookkeeping fields in covariant gauges. Physical external states are BRST cohomology classes, not ghost particles.

**Forgetting ghost number.** Counterterms, observables, and anomalies live in different ghost-number sectors. Mixing them up destroys the logic.

**Confusing BRST-exact with zero as an operator identity.** BRST-exact terms can affect gauge-dependent correlators and contact terms. They are physically trivial only in the appropriate cohomological sense.

**Assuming every BRST breaking can be fixed.** Trivial breakings can be removed by counterterms. Nontrivial ghost-number-one cohomology classes are anomalies.

## Relations to other pages

BRST symmetry underlies [Slavnov–Taylor Identities Preview](/renormalization-rg-eft/gauge-theories-and-rg/slavnov-taylor-identities-preview/). It also explains why [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/) is delicate: a regulator should preserve BRST symmetry, or else any breaking must be removable by local counterterms.

In Effective Field Theory, BRST and equation-of-motion reasoning help organize gauge-invariant operator bases. In Symmetry, Anomalies, and Topology, BRST cohomology becomes the natural language for anomalies and Wess–Zumino consistency. In Mathematical and Rigorous QFT, related structures appear in BV-BRST and perturbative algebraic QFT.

## Research status

The perturbative role of BRST symmetry in gauge theory is settled. It is standard machinery in the renormalization of Yang–Mills theory, the proof of gauge-parameter independence of physical observables, and the classification of gauge anomalies.

The active frontier is broader: BV-BRST in modern perturbative QFT, gauge theories with boundaries and defects, higher-form and higher-gauge structures, effective field theory operator reduction, chiral regularization schemes, and global obstructions not visible in purely local BRST algebra.

## Exercises

### Exercise 1: Ghost number of the BRST differential

Using the assignments

$$
\operatorname{gh}(A)=0,
\qquad
\operatorname{gh}(c)=1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(B)=0,
$$

show that $s$ has ghost number $+1$ in the transformations

$$
sA=Dc,
\qquad
sc=-\frac{g}{2}[c,c],
\qquad
s\bar c=B.
$$

<details><summary><strong>Solution</strong></summary>

The variation $sA=Dc$ has ghost number $1$, while $A$ has ghost number $0$, so $s$ raises ghost number by one. The variation $sc\sim cc$ has ghost number $2$, while $c$ has ghost number $1$, again showing that $s$ raises ghost number by one. Finally, $s\bar c=B$ maps ghost number $-1$ to ghost number $0$, which is also an increase by one.

</details>

### Exercise 2: BRST-exact gauge fixing

Starting from

$$
\Psi=\bar c^a\left(\partial^\mu A^a_\mu+\frac{\xi}{2}B^a\right),
$$

compute $s\Psi$ and identify the gauge-fixing and ghost terms.

<details><summary><strong>Solution</strong></summary>

Because $s$ is odd and $\bar c$ is odd,

$$
s\left(\bar c^a X^a\right)
=(s\bar c^a)X^a-\bar c^a sX^a,
$$

where

$$
X^a=\partial^\mu A^a_\mu+\frac{\xi}{2}B^a.
$$

Using $s\bar c^a=B^a$, $sB^a=0$, and $sA^a_\mu=D_\mu^{ab}c^b$, we find

$$
s\Psi
=B^a\partial^\mu A^a_\mu+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

The first two terms impose the covariant gauge condition after eliminating $B^a$. The last term is the Faddeev–Popov ghost Lagrangian.

</details>

### Exercise 3: BRST-exact insertions between physical states

Assume $Q_{\text{BRST}}\mid\alpha\rangle=Q_{\text{BRST}}\mid\beta\rangle=0$ and that the BRST charge can be moved through the matrix element without anomaly or boundary terms. Show that a BRST-exact operator has vanishing matrix element between physical states:

$$
\langle\alpha\mid \{Q_{\text{BRST}},X\}\mid\beta\rangle=0
$$

up to the appropriate graded sign convention.

<details><summary><strong>Solution</strong></summary>

Using the graded Leibniz rule, the matrix element is a sum of two terms in which $Q_{\text{BRST}}$ acts either to the left or to the right:

$$
\langle\alpha\mid Q_{\text{BRST}}X\mid\beta\rangle
\pm
\langle\alpha\mid XQ_{\text{BRST}}\mid\beta\rangle.
$$

The second term vanishes because $Q_{\text{BRST}}\mid\beta\rangle=0$. The first vanishes because $\langle\alpha\mid Q_{\text{BRST}}=0$ for a physical bra, assuming the BRST charge is conserved and no anomaly or boundary term appears. Thus BRST-exact insertions decouple from physical matrix elements.

</details>

## References

- C. Becchi, A. Rouet, and R. Stora, original papers on what is now called BRST symmetry.
- I. V. Tyutin, original preprint on gauge invariance in field theory and statistical physics.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on Faddeev–Popov ghosts, nonabelian gauge theory, BRST symmetry, and background-field gauge.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on path integrals, Ward identities, Yang–Mills renormalization, anomalies, and background fields.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, for gauge-theory renormalization and anomaly cancellation.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional BRST methods and renormalization with symmetries.
- Olivier Piguet and Silvio P. Sorella, *Algebraic Renormalization*, for the local cohomological treatment.
- Joseph Polchinski, *String Theory*, Vol. I, for BRST cohomology in string quantization and its relation to gauge redundancy in a different setting.

## Version history

- 2026-06-18: First polished draft. Added BRST transformations, ghost number, nilpotency, BRST-exact gauge fixing, counterterm cohomology, anomaly cohomology, and exercises.
