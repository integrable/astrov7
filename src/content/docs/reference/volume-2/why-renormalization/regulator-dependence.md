---
title: "Regulator Dependence"
description: "Why intermediate QFT calculations depend on a regulator, how that dependence is local, and how renormalized observables become regulator independent."
sidebar:
  label: "Regulator Dependence"
  order: 6
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman, Renormalization and Symmetry; Srednicki §§18–29; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Schwartz chs. 15–23 and app. B; Zinn-Justin, renormalization chapters; Burgess 2020 chs. 2–3."
topics:
  - regulator dependence
  - cutoff dependence
  - dimensional regularization
  - scheme dependence
  - local counterterms
  - universality
canonicalTopics:
  - regulator
  - cutoff-dependence
  - dimensional-regularization
  - local-counterterm
  - scheme-dependence
  - universality
researchStatus:
  established:
    - "Regulator dependence in local QFT is removed from properly defined observables by local counterterms and renormalization conditions, up to controlled cutoff artifacts in an EFT."
  active:
    - "Regulator choices remain technically and conceptually important in chiral gauge theories, lattice fermions, anomalies, curved spacetime, nonperturbative definitions, and quantum gravity EFT."
---

## Summary

A regulator is a way of making short-distance expressions well defined before renormalization has been completed. Cutoffs, lattice spacings, Pauli–Villars fields, dimensional continuation, higher-derivative regulators, and heat-kernel regulators are different ways of asking the same question:

$$
\text{what happens if the theory is not allowed to probe arbitrarily short distances without a rule?}
$$

Intermediate answers depend on that rule. Properly defined physical observables do not, after local counterterms and renormalization conditions are used consistently.

The important structure is

$$
\text{regulator dependence}
\quad\longrightarrow\quad
\text{local terms}
\quad\longrightarrow\quad
\text{renormalized parameters and counterterms}.
$$

Nonlocal dependence on physical scales, such as branch cuts, thresholds, and long-distance logarithms, cannot be removed by local counterterms. That nonlocal structure is physical. The regulator-dependent short-distance part is local.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Different regulators feed into local counterterms and scheme choices, which feed into renormalized coordinates and regulator-independent observables](/figures/renormalization-rg-eft/regulator-dependence-map.svg)

<figcaption>

Different regulators expose short-distance sensitivity in different languages. After local counterterms and renormalization conditions are fixed, properly defined observables agree up to controlled approximation errors and, in EFT, powers of $Q/\Lambda$.

</figcaption>
</figure>

:::note[Regulator dependence is not automatically bad]
A regulator-dependent intermediate expression is not a failed calculation. It is a calculation that has not yet been connected to a renormalization condition. The real test is whether the regulator dependence has the local form allowed by the symmetries and can be absorbed into the parameters required by the theory or EFT.
:::

## Prerequisites

You should have read [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/), [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/), and [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/).

The main ideas needed here are:

- UV divergences multiply local operators;
- bare parameters and counterterms depend on the regulator;
- physical parameters are fixed by observables or precise matching prescriptions.

## Core idea

A regulator changes the short-distance definition of a calculation. Because QFT loop integrals can probe arbitrarily large momenta, one must first decide how to make those integrals meaningful.

A hard cutoff might replace an integral by

$$
\int \frac{d^4 k}{(2\pi)^4}
\quad\longrightarrow\quad
\int_{|k_E|<\Lambda}\frac{d^4 k_E}{(2\pi)^4}.
$$

Dimensional regularization instead replaces spacetime dimension by

$$
d=4-2\epsilon
$$

and interprets divergent integrals by analytic continuation in $d$. A lattice regulator replaces spacetime by a grid with spacing $a$, so momenta live inside a Brillouin zone and the cutoff is roughly $\Lambda\sim 1/a$.

These choices are not identical. They may preserve or break different symmetries. They display different divergent terms. They often make different calculations easy.

Yet for a local QFT the difference between two acceptable UV regulators appears, at long distance, as a sum of local operators:

$$
S_{\text{eff}}^{(A)}-S_{\text{eff}}^{(B)}
=\sum_i c_i^{AB}\int d^d x\,\mathcal O_i(x)
+\text{terms suppressed by the cutoff}.
$$

That is the central reason renormalization works. Regulator dependence changes local coefficients. It does not change the nonlocal long-distance content once the coefficients have been fixed by physical input.

## Setup and conventions

We use $\Lambda$ for a hard cutoff, $a$ for a lattice spacing, $M_{\text{PV}}$ for a Pauli–Villars regulator mass, $\epsilon$ for dimensional regularization with $d=4-2\epsilon$, and $\mu$ for the renormalization scale.

A regulated bare theory may be written schematically as

$$
S_0^{\text{reg}}
=\sum_i g_{i,0}^{\text{reg}}\int d^d x\,\mathcal O_i(x),
$$

where the word “reg” reminds us that the definition of the functional integral, loop expansion, or Hilbert space includes a regulator.

A renormalized calculation rewrites this as

$$
S_0^{\text{reg}}
=S_{\text{ren}}(g_i(\mu),\mu)+S_{\text{ct}}^{\text{reg}}(g_i(\mu),\mu).
$$

The counterterm action depends on the regulator. The renormalized parameters depend on the scheme. Physical predictions do not depend on either arbitrary choice when computed exactly.

## What regulators do

A regulator has three jobs.

First, it makes intermediate expressions finite or at least well defined. For instance, a loop integral that does not converge can become a finite cutoff-dependent integral, a meromorphic function of $\epsilon$, or a finite lattice sum.

Second, it identifies the local short-distance terms that need renormalization. Divergent pieces are not random; they multiply operators compatible with locality and the symmetries left unbroken by the regulator.

Third, it provides a controlled approximation or definition. In a Wilsonian EFT, a finite cutoff can represent the boundary of the theory's intended domain. In lattice field theory, the lattice regulator can define the theory nonperturbatively before the continuum limit is taken.

A regulator is not a moral commitment. It is a controlled way of asking short-distance questions.

## Common regulators

| Regulator | Basic idea | Strength | Caveat |
|---|---|---|---|
| hard momentum cutoff | restrict $|k_E|<\Lambda$ | exposes power sensitivity directly | can break Lorentz or gauge symmetry if used naively |
| dimensional regularization | continue $d$ away from an integer | preserves covariance and is gauge-friendly | hides power divergences and needs care with $\gamma^5$ and evanescent operators |
| Pauli–Villars | add heavy regulator fields | physical intuition from heavy cancellations | not always symmetry-compatible in chiral or non-Abelian settings |
| lattice | discretize spacetime with spacing $a$ | nonperturbative definition | breaks continuous spacetime symmetries and complicates fermions |
| higher-derivative regulator | suppress large momenta with extra derivatives | useful in formal gauge settings | may introduce unphysical poles unless handled carefully |
| heat-kernel or proper-time cutoff | regulate short proper times | natural in curved spacetime and determinants | scheme dependence appears in local curvature terms |

The best regulator is the one that preserves the important symmetries, makes the calculation tractable, and makes the regulator artifacts transparent.

## Local versus nonlocal dependence

The deep distinction is not “finite versus infinite.” It is **local versus nonlocal**.

A local term in momentum space is polynomial in external momenta:

$$
A+Bp^2+Cp^4+\cdots.
$$

It corresponds to local operators in position space:

$$
A\phi^2,
\qquad
B\partial_\mu\phi\partial^\mu\phi,
\qquad
C(\Box\phi)^2,
\qquad\ldots
$$

A nonlocal term is not polynomial in external momenta. Examples include

$$
\log\frac{-p^2-i\epsilon}{\mu^2},
\qquad
\sqrt{1-\frac{4m^2}{s}},
\qquad
\frac{1}{p^2-m^2+i\epsilon}.
$$

These structures encode propagation, thresholds, branch cuts, and long-distance physics. Local counterterms cannot remove them. If two regulators gave different coefficients for a nonlocal physical threshold after the same renormalization conditions were imposed, something would be wrong.

The local part is adjustable. The nonlocal part is predictive.

## A scalar tadpole example

Consider the Euclidean integral

$$
I(m^2)=\int\frac{d^4 k_E}{(2\pi)^4}\frac{1}{k_E^2+m^2}.
$$

With a hard cutoff,

$$
I_\Lambda(m^2)
=\int_{|k_E|<\Lambda}\frac{d^4 k_E}{(2\pi)^4}\frac{1}{k_E^2+m^2}.
$$

For large $\Lambda$,

$$
I_\Lambda(m^2)
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2}{m^2}+O(m^2)
\right].
$$

The $\Lambda^2$ term and the logarithmic cutoff term multiply the local operator $\phi^2$ in a scalar self-energy calculation. They are absorbed into mass renormalization.

In dimensional regularization,

$$
I_{\text{dimreg}}(m^2)
=\mu^{2\epsilon}\int\frac{d^d k_E}{(2\pi)^d}\frac{1}{k_E^2+m^2}.
$$

Using the standard gamma-function formula gives, near $d=4-2\epsilon$,

$$
I_{\text{dimreg}}(m^2)
=\frac{m^2}{16\pi^2}
\left[
-\frac{1}{\bar\epsilon}
+\log\frac{m^2}{\mu^2}
-1+O(\epsilon)
\right],
$$

where

$$
\frac{1}{\bar\epsilon}
=\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

The quadratic divergence is not displayed as a $\Lambda^2$ term in dimensional regularization. This does not mean the mass term has no UV sensitivity. It means dimensional regularization packages the local mass sensitivity differently. Both regulators tell us that the local operator $\phi^2$ must have a renormalized coefficient.

## A logarithmic example and universality

Logarithmic divergences are especially important because they generate RG running. A typical one-loop integral after Feynman parametrization has the form

$$
J(Q^2)=\int\frac{d^4 k}{(2\pi)^4}\frac{1}{(k^2+\Delta(Q^2))^2}.
$$

With a cutoff, its large-$\Lambda$ behavior contains

$$
J_\Lambda(Q^2)
=\frac{1}{16\pi^2}\left[\log\frac{\Lambda^2}{\Delta(Q^2)}+\cdots\right].
$$

With dimensional regularization, the same logarithmic structure appears as

$$
J_{\text{dimreg}}(Q^2)
=\frac{1}{16\pi^2}\left[\frac{1}{\bar\epsilon}-\log\frac{\Delta(Q^2)}{\mu^2}+\cdots\right].
$$

The divergent languages differ:

$$
\log\Lambda^2
\quad\text{versus}\quad
\frac{1}{\epsilon}+\log\mu^2.
$$

But the coefficient of the physical logarithm is the same when the regulators preserve the relevant symmetries and the same operator normalization is used. That coefficient often determines the leading beta function.

This is one sense in which RG data can be universal. The local finite pieces may change with the scheme; the long-distance logarithmic response to scale separation carries physical information.

## Regulator dependence and counterterms

Suppose a regulated one-loop amplitude has the form

$$
\mathcal M_{\text{loop}}^{\text{reg}}(p_i)
=A^{\text{reg}}+B^{\text{reg}}s+C^{\text{reg}}t
+\mathcal M_{\text{nonlocal}}(p_i).
$$

Here $s$ and $t$ are Mandelstam invariants. The first three terms are local polynomials in external momenta. They correspond to local operators. The nonlocal term contains logs, cuts, thresholds, or other physical momentum dependence.

A counterterm amplitude has the form

$$
\mathcal M_{\text{ct}}^{\text{reg}}(p_i)
=\delta A^{\text{reg}}+\delta B^{\text{reg}}s+\delta C^{\text{reg}}t+\cdots.
$$

The coefficients are chosen so that renormalization conditions are satisfied. After this is done, the observable amplitude is independent of the regulator:

$$
\mathcal M_{\text{phys}}
=\mathcal M_{\text{tree}}
+\mathcal M_{\text{loop}}^{\text{reg}}
+\mathcal M_{\text{ct}}^{\text{reg}}
$$

up to the order being computed.

This is not cancellation by wishful thinking. It works because locality restricts regulator dependence to the same form as allowed terms in the action.

## Regulator artifacts in EFT

In an EFT, the cutoff does not always have to be removed. The theory may only be intended for momenta

$$
Q\ll\Lambda.
$$

Then cutoff artifacts can appear as powers of $Q/\Lambda$:

$$
\mathcal A(Q)
=\mathcal A_0(Q)
+\frac{Q}{\Lambda}\mathcal A_1(Q)
+\frac{Q^2}{\Lambda^2}\mathcal A_2(Q)+\cdots.
$$

A good EFT organizes these artifacts as higher-dimension local operators. If the calculation keeps operators through order $Q^n/M^n$, then residual regulator dependence should be of higher order.

This is the practical EFT test:

$$
\text{change regulator or cutoff}
\quad\Rightarrow\quad
\text{predictions change only beyond the claimed accuracy}.
$$

If changing the cutoff changes a leading-order prediction after refitting the allowed coefficients, the EFT is missing an operator, a symmetry condition, or a power-counting ingredient.

## Symmetries and bad regulators

A regulator may break a symmetry that the target theory is supposed to have. Sometimes this is harmless: the broken symmetry is restored by adding symmetry-restoring counterterms. Sometimes it is a disaster or a clue.

A naive hard momentum cutoff can break gauge invariance because it does not respect momentum routing and Ward identities automatically. Dimensional regularization is popular partly because it preserves gauge covariance well in many vectorlike gauge theories.

A lattice regulator preserves gauge invariance beautifully when gauge fields are represented by link variables, but it breaks continuous rotations and translations down to a discrete subgroup. Those spacetime symmetries must re-emerge in the continuum limit.

Chiral symmetry on the lattice is subtle because of fermion doubling and anomaly constraints. This is not a technical nuisance; it reflects deep compatibility conditions among locality, chirality, gauge symmetry, and topology.

The general rule is:

$$
\text{regulator artifacts must be removable by allowed local counterterms.}
$$

If they cannot be removed, the obstruction may be an anomaly, an inconsistent theory, or a regulator that does not define the desired continuum limit.

## Power divergences and dimensional regularization

Dimensional regularization often sets scaleless integrals to zero:

$$
\mu^{2\epsilon}\int\frac{d^d k}{(2\pi)^d}\frac{1}{k^2}=0.
$$

This identity is extremely useful, but it can mislead. A cutoff regulator would display power-law sensitivity. Dimensional regularization discards such scaleless power terms because there is no scale with which to express them.

Therefore the absence of a $\Lambda^2$ term in dimensional regularization does not prove the absence of physical sensitivity to heavy scales. If a heavy mass $M$ is present, dimensional regularization has no problem producing terms proportional to $M^2$ or $M^4$ multiplying local operators.

Naturalness questions should therefore not be settled by saying “I used dimensional regularization and the quadratic divergence vanished.” The better question is whether low-energy parameters are radiatively sensitive to heavy physical thresholds in a way not protected by symmetry.

## Scheme dependence versus regulator dependence

Regulator dependence and scheme dependence are related but not identical.

A regulator specifies how the UV is made finite:

$$
\Lambda,
\qquad
\epsilon,
\qquad
M_{\text{PV}},
\qquad
 a.
$$

A renormalization scheme specifies which finite parts are subtracted or which conditions define the renormalized parameters:

$$
\text{on-shell},
\qquad
\text{momentum subtraction},
\qquad
\mathrm{MS},
\qquad
\overline{\mathrm{MS}}.
$$

The same regulator can support many schemes. Dimensional regularization can be used with $\mathrm{MS}$, $\overline{\mathrm{MS}}$, or momentum subtraction. A cutoff can be used with physical renormalization conditions or with a Wilsonian matching prescription.

When a result changes under a scheme change, the change should be equivalent to a redefinition of renormalized parameters:

$$
g^i\longrightarrow g^{\prime i}(g).
$$

When a result changes under a regulator change after physical inputs are refit, the change should vanish in the continuum limit or be suppressed beyond the EFT order.

## How to check regulator independence

A trustworthy calculation should pass several checks.

**Locality check.** The regulator-dependent pieces should be polynomial in external momenta at low momentum. Nonlocal regulator-dependent terms are a warning sign.

**Symmetry check.** Counterterms should respect the symmetries, or symmetry-breaking regulator artifacts should be removable by known symmetry-restoring counterterms.

**Input-output check.** After using the required number of physical inputs to fix parameters, independent predictions should not depend on the regulator at the claimed accuracy.

**Scheme-translation check.** Changing from one scheme to another should be reproducible by finite parameter redefinitions.

**RG check.** Explicit logarithms of $\mu$ should cancel against running parameters in physical observables.

**Power-counting check.** In EFT, residual cutoff dependence should appear at orders not yet included.

These checks are not bureaucratic. They are how one distinguishes a physical prediction from a regulator artifact wearing a nice hat.

## Common pitfalls

**Thinking the cutoff must always be sent to infinity.** In a renormalizable continuum theory one often studies the limit $\Lambda\to\infty$. In an EFT, a finite cutoff can be part of the description, and predictions are organized in powers of $Q/\Lambda$ or $Q/M$.

**Thinking dimensional regularization proves power sensitivity is fake.** Dimensional regularization hides scaleless power divergences. It does not erase physical sensitivity to heavy thresholds.

**Using a symmetry-breaking regulator without repairing the symmetry.** This can produce wrong Ward identities, wrong beta functions, or fake mass terms.

**Calling every cutoff-dependent term unphysical.** Some cutoff dependence is removed by renormalization. Some finite cutoff dependence is a controlled EFT artifact. Some cutoff sensitivity to heavy physical masses is real and encoded in Wilson coefficients.

**Expecting off-shell Green functions to be regulator independent.** Off-shell quantities can depend on scheme, gauge, field variables, and regulator. Observables and properly matched quantities are the invariants.

## Relations to other pages

[Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/) explains why UV divergences have the form of local operators. This page explains why regulator dependence has the same local structure.

[Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/) explains the parameter split used to absorb regulator dependence. [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/) explains how physical input data fix the otherwise scheme-dependent renormalized coordinates.

Later pages on cutoff regularization, dimensional regularization, minimal subtraction, Wilsonian effective actions, matching, and decoupling will turn this conceptual structure into calculational machinery.

## Research status

The local nature of regulator dependence in perturbative local QFT is settled and is one of the foundations of renormalization theory and EFT.

The difficult issues appear in demanding contexts: gauge-invariant regulators, chiral gauge theories, lattice fermions, anomalies, curved-spacetime counterterms, nonperturbative continuum limits, real-time finite-density systems, and quantum gravity. In those settings the regulator is not a disposable afterthought. It can be part of the definition of the problem.

## Exercises

### Exercise 1: Difference of two cutoff schemes

Suppose two cutoff regulators give the following low-momentum expansion for a two-point loop contribution:

$$
\Pi_A(p^2)=a_A\Lambda^2+b_Ap^2+c p^2\log\frac{-p^2}{\mu^2}+O(p^4/\Lambda^2),
$$

and

$$
\Pi_B(p^2)=a_B\Lambda^2+b_Bp^2+c p^2\log\frac{-p^2}{\mu^2}+O(p^4/\Lambda^2).
$$

Show that the difference can be absorbed into local counterterms up to cutoff-suppressed corrections.

<details><summary><strong>Solution</strong></summary>

Subtract the two expressions:

$$
\Pi_A(p^2)-\Pi_B(p^2)
=(a_A-a_B)\Lambda^2+(b_A-b_B)p^2+O(p^4/\Lambda^2).
$$

The nonlocal logarithmic term cancels because it has the same coefficient $c$. The remaining leading terms are polynomial in $p^2$. A constant term renormalizes a mass operator such as $\phi^2$, while a term proportional to $p^2$ renormalizes the kinetic operator $\partial_\mu\phi\partial^\mu\phi$. The $O(p^4/\Lambda^2)$ terms correspond to higher-derivative local operators suppressed by the cutoff.

</details>

### Exercise 2: Why a logarithm is not a local counterterm

Explain why a momentum dependence of the form

$$
p^2\log\frac{-p^2-i\epsilon}{\mu^2}
$$

cannot be canceled by adding a finite number of ordinary local counterterms.

<details><summary><strong>Solution</strong></summary>

A local counterterm contains a finite number of derivatives. In momentum space it contributes a polynomial in external momenta, such as

$$
A+Bp^2+Cp^4+\cdots
$$

with finitely many terms at a given order in the action. The function

$$
p^2\log\frac{-p^2-i\epsilon}{\mu^2}
$$

is not a polynomial. It has a branch cut and nonanalytic behavior. Such nonanalyticity reflects propagation of degrees of freedom and long-distance or threshold physics. It cannot be removed by local counterterms. Only its local polynomial pieces, if any are separated by expansion around a reference point, can be changed by counterterms.

</details>

### Exercise 3: EFT cutoff variation

An EFT prediction through order $Q^2/M^2$ has residual cutoff dependence proportional to $Q^4/\Lambda^4$ after all coefficients through dimension six have been refit. Is this a problem?

<details><summary><strong>Solution</strong></summary>

No. If the EFT calculation claims accuracy only through order $Q^2/M^2$, then residual dependence at order $Q^4/\Lambda^4$ is beyond the retained accuracy. It indicates the size of omitted higher-dimension operators. A problem would arise if cutoff variation changed terms at order $Q^0$, $Q/M$, or $Q^2/M^2$ after the coefficients included at those orders had been properly refit.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Renormalization and Symmetry" and "Dilatations."
- Mark Srednicki, *Quantum Field Theory*, especially sections on renormalization, regulators, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 15–23 and appendix B.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 2–3 on Wilson actions, power counting, and matching.

## Version history

- 2026-06-16: First polished draft. Added conceptual distinction between regulator dependence, scheme dependence, local counterterms, physical nonlocal structure, EFT cutoff artifacts, and symmetry-sensitive regulator choices.
