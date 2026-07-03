---
title: "Integrating Out Modes"
description: "Explains the Wilsonian operation of integrating out high-momentum or heavy degrees of freedom and deriving the effective action for the remaining low-energy modes."
sidebar:
  label: "Integrating Out Modes"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Weinberg Vol. II ch. 18; Srednicki sections 28–29; Schwartz ch. 23; Burgess chs. 2–3; Zinn-Justin 2021."
topics:
  - integrating out modes
  - Wilsonian effective action
  - heavy fields
  - momentum shells
  - local operator expansion
  - derivative expansion
canonicalTopics:
  - integrating-out-modes
  - wilsonian-effective-action
  - derivative-expansion
  - heavy-field-matching
  - mode-integration
researchStatus:
  established:
    - "Integrating out degrees of freedom is the standard operation behind Wilsonian effective actions, EFT matching, decoupling, and coarse-grained descriptions."
  active:
    - "Gauge-invariant mode separation, real-time coarse graining, strongly coupled matching, and nonlocal effective descriptions remain active technical and conceptual areas."
---

## Summary

**Integrating out modes** means removing some variables from the path integral while preserving the observables built from the variables that remain.

In a Wilsonian momentum split, write

$$
\phi=\phi_{<}+\phi_{>},
$$

where $\phi_{<}$ contains momenta below $\Lambda$ and $\phi_{>}$ contains momenta between $\Lambda$ and a microscopic cutoff $\Lambda_0$. The Wilsonian effective action is defined by

$$
e^{-S_\Lambda[\phi_{<}]}
=
\mathcal N_\Lambda
\int_{\Lambda<|p|<\Lambda_0}\mathcal D\phi_{>}
\exp\left[-S_{\Lambda_0}[\phi_{<}+\phi_{>}]
\right].
$$

The high modes are gone as explicit variables, but they are not gone as physics. They shift masses and couplings, generate new operators, renormalize composite operators, and sometimes leave nonlocal remnants when scale separation fails.

The same operation appears in several familiar situations.

| Situation | Variables integrated out | Resulting description |
|---|---|---|
| Wilsonian RG | high-momentum shell | lower-cutoff action $S_\Lambda$ |
| EFT matching | heavy particles of mass $M$ | light-field operators with Wilson coefficients |
| Statistical coarse graining | short-distance spins or block variables | effective Hamiltonian for coarse variables |
| Condensed matter | high-energy bands or off-shell modes | low-energy quasiparticle or order-parameter theory |

A good effective action is not a lossy summary. It is a compressed description tuned to the observables that can actually be resolved.

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), and the locality logic from [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/).

It also helps to have seen [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/). The same reason loop divergences collapse into local counterterms is the reason heavy or high-momentum modes usually collapse into local low-energy operators.

## Core idea

The definition is simplest when the full variables are split into two sets, $(\phi,\chi)$, and the observables of interest depend only on $\phi$. Define

$$
e^{-S_{\mathrm{eff}}[\phi]}
=
\int \mathcal D\chi\,e^{-S[\phi,\chi]}.
$$

Then for every observable $F[\phi]$,

$$
\int \mathcal D\phi\,F[\phi]e^{-S_{\mathrm{eff}}[\phi]}
=
\int \mathcal D\phi\mathcal D\chi\,F[\phi]e^{-S[\phi,\chi]}.
$$

That equality is the definition. Integrating out $\chi$ is legitimate because the effective action is chosen to reproduce the $\phi$ observables.

Three comments prevent common mistakes.

First, $\chi$ need not be a different particle. It can be the high-momentum part of the same field, a fast lattice variable, a heavy band, a bath variable, or any set of degrees of freedom not being observed directly.

Second, the exact effective action can be ugly. It may contain infinitely many operators and, when scale separation is poor, nonlocal terms. Wilsonian predictivity comes from locality, symmetry, and power counting, not from pretending the exact answer is short.

Third, integrating out is not setting a field to zero. Setting $\chi=0$ throws away its virtual effects. Integrating over $\chi$ includes them.

## Setup and conventions

This page uses Euclidean signature unless stated otherwise. The Lorentzian version replaces $e^{-S_E}$ by $e^{iS}$ and requires the usual contour and $i\epsilon$ prescriptions.

We write

$$
\int_p\equiv \int \frac{d^d p}{(2\pi)^d}.
$$

For a scalar field with cutoff $\Lambda_0$, a sharp split is

$$
\phi_{<}(p)=\phi(p)\theta(\Lambda-|p|),
\qquad
\phi_{>}(p)=\phi(p)\theta(|p|-\Lambda)\theta(\Lambda_0-|p|).
$$

A sharp cutoff is pedagogically useful, not holy scripture. Smooth cutoffs, heat-kernel regulators, lattice regulators, dimensional regularization in matching calculations, and symmetry-preserving regulators are often better for actual work. The Wilsonian idea is regulator-independent; the coordinates used to display it are not.

When the removed modes are short-distance compared with the observables of interest, the Wilsonian action can be expanded in local operators:

$$
S_\Lambda[\phi]
=
\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

The coefficients $g_i(\Lambda)$ remember the modes that were removed.

## Finite-dimensional Gaussian warm-up

Before field theory, do the ordinary Gaussian integral. Let

$$
S(x,y)=\frac12 a x^2+bxy+\frac12 c y^2,
\qquad c>0.
$$

Define $S_{\mathrm{eff}}(x)$ by

$$
e^{-S_{\mathrm{eff}}(x)}
=\int_{-\infty}^{\infty}dy\,e^{-S(x,y)}.
$$

Complete the square:

$$
\frac12 c y^2+bxy
=
\frac12 c\left(y+\frac{b}{c}x\right)^2
-\frac12\frac{b^2}{c}x^2.
$$

The $y$ integral gives an $x$-independent constant, so

$$
S_{\mathrm{eff}}(x)
=
\frac12\left(a-\frac{b^2}{c}\right)x^2+\text{constant}.
$$

The integrated-out variable changes the effective coefficient of $x^2$. Setting $y=0$ would have given the wrong coefficient, $a$, instead of $a-b^2/c$.

This tiny calculation is the whole Wilsonian philosophy in miniature: unobserved variables still affect the dynamics of observed variables.

## Tree-level heavy-field matching

Consider a light scalar $\phi$ coupled linearly to a heavy scalar $H$ through a source $J[\phi]$. In Euclidean notation,

$$
S[\phi,H]
=S_\phi[\phi]+\frac12\int d^d x\,
H\left(-\partial^2+M^2\right)H
+\int d^d x\,H J[\phi].
$$

The heavy-field kernel is

$$
K_H=-\partial^2+M^2.
$$

Completing the square gives

$$
\frac12 H K_H H+H J
=\frac12(H+K_H^{-1}J)K_H(H+K_H^{-1}J)
-\frac12 J K_H^{-1}J.
$$

After integrating over $H$,

$$
S_{\mathrm{eff}}[\phi]
=S_\phi[\phi]
-\frac12\int d^d x\,d^d y\,
J(x)G_M(x-y)J(y)
+\text{constant},
$$

where $G_M=K_H^{-1}$.

If $J[\phi]=\kappa \phi^2/2$, then at momenta $Q\ll M$,

$$
G_M=\frac{1}{M^2-\partial^2}
=\frac{1}{M^2}+\frac{\partial^2}{M^4}+O\left(\frac{\partial^4}{M^6}\right).
$$

The effective action contains

$$
S_{\mathrm{eff}}
=S_\phi
-\frac{\kappa^2}{8M^2}\int d^d x\,\phi^4
+\frac{\kappa^2}{8M^4}\int d^d x\,\partial_\mu(\phi^2)\partial^\mu(\phi^2)
+O\left(\frac{\partial^4}{M^6}\right),
$$

where the derivative term has been integrated by parts. The exact nonlocal exchange has become a local derivative expansion.

This is the tree-level version of integrating out. It is also the simplest way to see why EFT coefficients are powers of the heavy scale.

## One-loop heavy-field effects

If the heavy field appears quadratically but with a light-field-dependent mass, for example

$$
S[\phi,H]
=S_\phi[\phi]+\frac12\int d^d x\,
H\left(-\partial^2+M^2+g\phi^2\right)H,
$$

then integrating out $H$ gives

$$
S_{\mathrm{eff}}[\phi]
=S_\phi[\phi]
+\frac12\operatorname{Tr}\log\left(-\partial^2+M^2+g\phi^2\right)
+\text{constant}.
$$

Expanding the logarithm around $A=-\partial^2+M^2$ gives

$$
\operatorname{Tr}\log(A+B)
=\operatorname{Tr}\log A
+\operatorname{Tr}(A^{-1}B)
-\frac12\operatorname{Tr}(A^{-1}BA^{-1}B)+\cdots,
$$

with $B=g\phi^2$. The first light-dependent term corrects the mass of $\phi$; the next corrects the quartic coupling and derivative interactions. These are threshold corrections from virtual heavy particles.

The same operation is used in one-loop EFT matching. The full theory and EFT are compared at low external momenta, and the Wilson coefficients are chosen so that the low-energy amplitudes agree.

## Integrating out a momentum shell

For Wilsonian RG, the removed variable is often a thin shell of momenta of the same field. Write

$$
S[\phi_<+\phi_>]
=S_<[\phi_<]+S_>[\phi_>]+S_{\mathrm{int}}[\phi_<,\phi_>].
$$

Then

$$
e^{-\Delta S[\phi_<]}
=
\left\langle e^{-S_{\mathrm{int}}[\phi_<,\phi_>]}\right\rangle_>,
$$

where the expectation value uses the high-mode Gaussian action $S_>$. Expanding the logarithm gives the cumulant expansion

$$
\Delta S
=\left\langle S_{\mathrm{int}}\right\rangle_>
-\frac12\left(
\left\langle S_{\mathrm{int}}^2\right\rangle_>
-\left\langle S_{\mathrm{int}}\right\rangle_>^2
\right)+\cdots.
$$

The connected high-mode contractions produce new low-mode vertices.

In scalar $\phi^4$ theory,

$$
S_{\mathrm{int}}
=\int d^d x\,\frac{\lambda}{4!}(\phi_<+\phi_>)^4.
$$

The term with two low fields and two high fields is

$$
\int d^d x\,\frac{\lambda}{4}\phi_<^2\phi_>^2.
$$

Therefore

$$
\Delta S\supset
\int d^d x\,\frac{\lambda}{4}\phi_<^2(x)
\left\langle \phi_>^2(x)\right\rangle_>,
$$

where

$$
\left\langle \phi_>^2(x)\right\rangle_>
=
\int_{\Lambda'<|q|<\Lambda}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

Using $\Delta S\supset \int d^d x\,\frac12\Delta m^2\phi_<^2$, one obtains

$$
\Delta m^2
=
\frac{\lambda}{2}
\int_{\Lambda'<|q|<\Lambda}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

At the next cumulant order, shell contractions correct the quartic coupling:

$$
\Delta\lambda
=
-\frac{3\lambda^2}{2}
\int_{\Lambda'<|q|<\Lambda}\frac{d^d q}{(2\pi)^d}\frac{1}{(q^2+m^2)^2}
+\text{higher-derivative terms}.
$$

These are shell corrections before rescaling. [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/) adds the rescaling step.

## Locality and the derivative expansion

The crucial reason integrating out works is locality. If a heavy or high-momentum mode propagates only over distances much shorter than the wavelengths being probed, its effects can be expanded in local operators.

In momentum space, a massive propagator has the low-momentum expansion

$$
\frac{1}{p^2+M^2}
=
\frac{1}{M^2}
-\frac{p^2}{M^4}
+\frac{p^4}{M^6}-\cdots.
$$

In position space, powers of $p$ become derivatives. Thus a nonlocal exchange becomes

$$
\text{nonlocal heavy exchange}
\quad\longrightarrow\quad
\text{local operators suppressed by powers of }M.
$$

The expansion fails when the removed modes can propagate over the same distances as the retained modes. Massless particles, near-threshold heavy particles, Fermi-surface modes, Goldstone bosons, and critical fluctuations should usually be kept explicit unless a more specialized effective description is being used.

## Integrating out versus solving equations of motion

At tree level, integrating out a heavy field often agrees with solving its classical equation of motion and substituting back. In the source example,

$$
K_HH=-J[\phi],
\qquad
H=-K_H^{-1}J[\phi].
$$

Substitution gives the same tree-level term

$$
-\frac12\int J K_H^{-1}J.
$$

But the path integral also includes fluctuation determinants and loops. Solving the classical equation is a shortcut for tree-level matching, not the definition of integrating out.

This distinction matters whenever threshold corrections, anomalies, determinants, or one-loop Wilson coefficients are important.

## What is preserved

Exact integration preserves the expectation values of observables built from the retained variables:

$$
\left\langle F[\phi_<]\right\rangle_{S_{\Lambda_0}}
=
\left\langle F[\phi_<]\right\rangle_{S_\Lambda}.
$$

What changes is the representation: field normalization, coupling values, operator basis, vacuum energy, and cutoff-dependent terms may all change.

The invariant statement is not that the Lagrangian looks the same. The invariant statement is that the low-resolution physics is reproduced by the effective action when used with its cutoff and matching conditions.

## Common pitfalls

**Setting heavy fields to zero.** A heavy field can mediate interactions even when no heavy particle appears externally. Integrating it out keeps those effects.

**Forgetting the cutoff of the effective theory.** If a Wilsonian action has cutoff $\Lambda$, loops computed with it should not re-integrate over modes above $\Lambda$.

**Assuming locality without scale separation.** Local EFT expansions require momenta below thresholds and a clean separation between retained and removed modes.

**Confusing Wilsonian actions with 1PI effective actions.** A Wilsonian action keeps low modes dynamical. A 1PI effective action generates one-particle-irreducible vertices after a different integration over fluctuations.

**Ignoring symmetries during the split.** A poor regulator or cutoff can obscure a symmetry. Gauge theories require special care.

**Thinking generated operators are optional.** Once modes are integrated out, all operators compatible with the symmetries are generally generated. Power counting decides which ones matter at a given accuracy.

## Relations to other pages

This page explains the operational step behind [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and prepares [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/).

The heavy-field examples connect directly to [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) and [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/). The shell examples connect to [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

The local-operator logic connects backward to [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) and forward to [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/).

## Research status

Integrating out degrees of freedom is established and central to QFT, statistical mechanics, EFT, condensed matter, and quantum many-body physics.

Active questions are mostly about implementation in difficult settings: gauge-invariant coarse graining, real-time open-system effective actions, strongly coupled matching without weakly coupled variables, nonperturbative functional RG truncations, and the role of locality in quantum gravity or holography.

## Exercises

### Exercise 1: Gaussian integration changes the coefficient

Evaluate

$$
\int_{-\infty}^{\infty}dy\,
\exp\left[-\frac12 a x^2-bxy-\frac12 c y^2\right]
$$

for $c>0$, up to an $x$-independent normalization.

<details><summary><strong>Solution</strong></summary>

Complete the square:

$$
\frac12 c y^2+bxy
=
\frac12 c\left(y+\frac{b}{c}x\right)^2
-\frac12\frac{b^2}{c}x^2.
$$

The Gaussian integral over the shifted $y$ gives a constant. Therefore

$$
S_{\mathrm{eff}}(x)
=
\frac12\left(a-\frac{b^2}{c}\right)x^2+\text{constant}.
$$

The integrated-out variable changes the coefficient of $x^2$.

</details>

### Exercise 2: Heavy source expansion

Let $J[\phi]$ be a local light-field source coupled to a heavy field as above. Show that

$$
-\frac12\int J\frac{1}{M^2-\partial^2}J
=
-\frac{1}{2M^2}\int d^d x\,J^2
+\frac{1}{2M^4}\int d^d x\,\partial_\mu J\partial^\mu J
+\cdots.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\frac{1}{M^2-\partial^2}
=\frac{1}{M^2}+\frac{\partial^2}{M^4}+\cdots.
$$

Then

$$
-\frac12\int J\frac{1}{M^2-\partial^2}J
=
-\frac{1}{2M^2}\int J^2
-\frac{1}{2M^4}\int J\partial^2J+\cdots.
$$

Integrating by parts gives

$$
-\int J\partial^2J
=\int \partial_\mu J\partial^\mu J,
$$

assuming boundary terms vanish. Hence

$$
-\frac12\int J\frac{1}{M^2-\partial^2}J
=
-\frac{1}{2M^2}\int J^2
+\frac{1}{2M^4}\int \partial_\mu J\partial^\mu J+\cdots.
$$

</details>

### Exercise 3: The shell tadpole in scalar theory

In $\phi^4$ theory with interaction $\lambda \phi^4/4!$, show that the high-shell contraction produces

$$
\Delta m^2
=
\frac{\lambda}{2}
\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

<details><summary><strong>Solution</strong></summary>

Expand

$$
(\phi_<+\phi_>)^4
=\phi_<^4+4\phi_<^3\phi_>+6\phi_<^2\phi_>^2+4\phi_<\phi_>^3+\phi_>^4.
$$

The two-low, two-high term in the action is

$$
\frac{\lambda}{4!}6\phi_<^2\phi_>^2
=\frac{\lambda}{4}\phi_<^2\phi_>^2.
$$

Contracting the high fields gives

$$
\Delta S\supset
\int d^d x\,\frac{\lambda}{4}\phi_<^2(x)
\int_{\mathrm{shell}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

Comparing with $\Delta S\supset \int d^d x\,\frac12\Delta m^2\phi_<^2$ gives the stated result.

</details>

### Exercise 4: Why threshold regions cannot be integrated out locally

Explain why the expansion

$$
\frac{1}{M^2-p^2}=\frac{1}{M^2}\sum_{n=0}^{\infty}\left(\frac{p^2}{M^2}\right)^n
$$

cannot be trusted near $p^2=M^2$.

<details><summary><strong>Solution</strong></summary>

The geometric series converges only for $|p^2/M^2|<1$ and becomes singular as $p^2$ approaches $M^2$. Physically, $p^2=M^2$ is the threshold where the heavy particle can go on shell. The heavy field is no longer a purely short-distance virtual effect, so a local low-energy expansion in powers of $p^2/M^2$ is not valid there.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the Wilsonian connection between mode elimination, critical phenomena, and QFT.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," for the Wilsonian action and exact-RG viewpoint.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods and effective theories.
- Mark Srednicki, *Quantum Field Theory*, sections on the renormalization group and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on renormalization, Wilsonian RG, and nonrenormalizable theories.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3, for effective actions, Wilson actions, power counting, and matching.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for field-theoretic RG and statistical critical phenomena.

## Version history

- 2026-06-17: First polished draft. Defined mode integration, heavy-field matching, shell integration, locality conditions, and common mistakes.
