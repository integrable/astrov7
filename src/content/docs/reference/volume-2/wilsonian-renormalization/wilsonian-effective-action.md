---
title: "Wilsonian Effective Action"
description: "Defines the Wilsonian effective action as the cutoff-dependent action for low-momentum modes after higher modes have been integrated out, and explains its relation to locality, EFT, and RG flow."
sidebar:
  label: "Wilsonian Effective Action"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Weinberg Vol. II ch. 18; Srednicki §§28–29; Schwartz ch. 23; Burgess chs. 2–3; Zinn-Justin 2021."
topics:
  - Wilsonian effective action
  - integrating out modes
  - cutoff dependence
  - local operator expansion
  - theory space
  - effective field theory
canonicalTopics:
  - wilsonian-effective-action
  - mode-integration
  - cutoff-effective-action
  - local-operator-expansion
  - wilsonian-rg
researchStatus:
  established:
    - "The Wilsonian effective action is the standard scale-dependent action obtained by integrating out degrees of freedom above a cutoff while preserving low-energy observables."
  active:
    - "Precise Wilsonian constructions in gauge theories, gravity, real time, strongly coupled systems, and practical functional RG truncations remain active areas of research and method development."
---

## Summary

The **Wilsonian effective action** $S_\Lambda$ is the action that describes only the degrees of freedom below a cutoff $\Lambda$, after the degrees of freedom above $\Lambda$ have been integrated out.

In Euclidean notation, for a scalar field with microscopic cutoff $\Lambda_0$, split

$$
\phi=\phi_{<}+\phi_{>},
$$

where $\phi_{<}$ contains momenta below $\Lambda$ and $\phi_{>}$ contains momenta between $\Lambda$ and $\Lambda_0$. The Wilsonian effective action is defined by

$$
e^{-S_\Lambda[\phi_{<}]}
=
\mathcal N_\Lambda
\int_{\Lambda<\lvert p\rvert<\Lambda_0}\mathcal D\phi_{>}
\exp\left[-S_{\Lambda_0}[\phi_{<}+\phi_{>}]\right].
$$

The normalization $\mathcal N_\Lambda$ only changes the vacuum-energy convention unless gravity or thermodynamics makes the absolute normalization important.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Wilsonian effective action constructed by splitting fields into low and high momentum modes, integrating out high modes, and expanding the resulting low-mode action in local operators](/figures/renormalization-rg-eft/wilsonian-effective-action-split.svg)

<figcaption>

The Wilsonian effective action $S_\Lambda$ keeps long-distance modes explicit and stores the effect of shorter-distance modes in cutoff-dependent local couplings. Lowering $\Lambda$ changes the action but not the low-energy observables, when the calculation is done exactly.

</figcaption>
</figure>

The point is not to delete short-distance physics. The point is to stop carrying short-distance variables explicitly when the questions being asked cannot resolve them. Their effects survive as local operators and cutoff-dependent couplings in $S_\Lambda$.

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/), [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/), and [Cutoff Regularization](/renormalization-rg-eft/regularization-counterterms/cutoff-regularization/).

It also helps to know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) and [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), but the Wilsonian construction can be understood before computing any beta function.

## Core idea

The Wilsonian effective action is the cleanest mathematical expression of a physical idea:

$$
\text{physics below }\Lambda
\quad\text{does not require explicit variables above }\Lambda.
$$

Suppose an experiment probes momenta $Q\ll\Lambda$. The high-momentum modes are not separately observed. But they can run in virtual processes, change masses and couplings, generate new local interactions, and shift the vacuum energy. Wilsonian renormalization packages all of those effects into a new action for the modes that remain.

This is why $S_\Lambda$ depends on $\Lambda$. Lowering the cutoff changes which modes are still explicit. The action must change to compensate. If the integration is exact, low-energy observables do not change.

A useful slogan is

$$
\text{same long-distance physics}
\quad\Longleftrightarrow\quad
\text{different actions at different cutoffs}.
$$

The slogan sounds paradoxical only if one thinks an action is a sacred microscopic object. In the Wilsonian view, an action is a scale-dependent description.

## Setup and conventions

We write formulas in Euclidean signature because mode integration is most transparent in convergent functional integrals. The Lorentzian version replaces $e^{-S_E}$ by $e^{iS}$ with the usual contour and regulator qualifications.

Let

$$
\int_p\equiv\int\frac{d^d p}{(2\pi)^d}.
$$

Assume that the microscopic regulated theory is defined with a UV cutoff $\Lambda_0$. For a real scalar field, write the Fourier-space split

$$
\phi(p)=\phi_{<}(p)+\phi_{>}(p),
$$

with

$$
\phi_{<}(p)=0\quad\text{for}\quad \lvert p\rvert>\Lambda,
\qquad
\phi_{>}(p)=0\quad\text{unless}\quad \Lambda<\lvert p\rvert<\Lambda_0.
$$

The exact Wilsonian definition is the equality of low-mode functional integrals:

$$
\int_{\lvert p\rvert<\Lambda}\mathcal D\phi_{<}\,
F[\phi_{<}]e^{-S_\Lambda[\phi_{<}]}
=
\int_{\lvert p\rvert<\Lambda_0}\mathcal D\phi\,
F[\phi_{<}]e^{-S_{\Lambda_0}[\phi]}
$$

for every observable $F$ depending only on low modes. Equivalently,

$$
e^{-S_\Lambda[\phi_{<}]}
=
\mathcal N_\Lambda
\int_{\Lambda<\lvert p\rvert<\Lambda_0}\mathcal D\phi_{>}
\exp\left[-S_{\Lambda_0}[\phi_{<}+\phi_{>}]\right].
$$

The cutoff can be sharp, smooth, lattice-like, heat-kernel-like, or defined in some other way. A sharp momentum cutoff is pedagogically simple but not always the best regulator, especially in gauge theory. The Wilsonian idea is regulator-independent; the detailed form of $S_\Lambda$ is not.

## The free Gaussian example

Start with the free Euclidean scalar action

$$
S_{\Lambda_0}[\phi]
=
\frac12\int_{\lvert p\rvert<\Lambda_0}
\phi(p)(p^2+m^2)\phi(-p).
$$

Because the action is quadratic and diagonal in momentum, the split into low and high modes factorizes:

$$
S_{\Lambda_0}[\phi_{<}+\phi_{>}]
=
\frac12\int_{\lvert p\rvert<\Lambda}
\phi_{<}(p)(p^2+m^2)\phi_{<}(-p)
+
\frac12\int_{\Lambda<\lvert p\rvert<\Lambda_0}
\phi_{>}(p)(p^2+m^2)\phi_{>}(-p).
$$

Integrating over $\phi_{>}$ gives only a determinant:

$$
S_\Lambda[\phi_{<}]
=
\frac12\int_{\lvert p\rvert<\Lambda}
\phi_{<}(p)(p^2+m^2)\phi_{<}(-p)
+\text{constant}.
$$

The low-mode quadratic action is unchanged. The only effect is a vacuum-energy contribution from the modes that were integrated out.

This is the Gaussian fixed point in its simplest form. A free theory remains free under Wilsonian coarse graining, aside from normalization and rescaling. Interactions are what make the Wilsonian action flow through a larger space of couplings.

## How interactions generate local terms

Now add a quartic interaction,

$$
S_{\text{int}}[\phi]
=
\int d^d x\,\frac{\lambda}{4!}\phi^4.
$$

Insert

$$
\phi=\phi_{<}+\phi_{>}.
$$

The term with two low fields and two high fields is

$$
\int d^d x\,\frac{\lambda}{4}\phi_{<}^2\phi_{>}^2.
$$

When high modes are integrated out, this produces a correction to the low-mode mass term:

$$
\Delta S_\Lambda
\supset
\int d^d x\,\frac{\lambda}{4}\phi_{<}^2(x)
\left\langle \phi_{>}^2(x)\right\rangle_{>}.
$$

Using the free high-mode propagator as a first approximation,

$$
\left\langle \phi_{>}^2(x)\right\rangle_{>}
=
\int_{\Lambda<\lvert q\rvert<\Lambda_0}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

Thus the coefficient of $\phi_{<}^2$ changes. In the usual mass-term convention,

$$
\Delta S_\Lambda\supset \int d^d x\,\frac12\Delta m^2\phi_{<}^2,
$$

so at this order

$$
\Delta m^2
=
\frac{\lambda}{2}
\int_{\Lambda<\lvert q\rvert<\Lambda_0}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

The important feature is not the exact coefficient. The important feature is locality: the high-momentum loop has collapsed into a local operator in the low-energy action.

At higher orders, shell integration generates more terms:

$$
\phi^2,
\qquad
\phi^4,
\qquad
(\partial\phi)^2,
\qquad
\phi^6,
\qquad
\phi^2(\partial\phi)^2,
\qquad
(\partial^2\phi)^2,
\qquad\ldots
$$

Even if the microscopic action contains only a few operators, the Wilsonian action generally contains all local operators allowed by the symmetries.

:::note[Locality is doing the heavy lifting]
High modes can generate many operators, but when external momenta are small compared with the cutoff or heavy scale, their effects are analytic in low momenta. Analytic momentum dependence is exactly what a derivative expansion of local operators encodes.
:::

## The local operator expansion

The Wilsonian action is usually written as a sum over local operators:

$$
S_\Lambda
=
\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

For a scalar theory preserving $\phi\to-\phi$, a representative expansion is

$$
S_\Lambda
=
\int d^d x\left[
\frac12 Z_\Lambda(\partial\phi)^2
+\frac12 m^2_\Lambda\phi^2
+\frac{\lambda_\Lambda}{4!}\phi^4
+\frac{c_{6,\Lambda}}{\Lambda^2}\phi^6
+\frac{c_{\partial,\Lambda}}{\Lambda^2}\phi^2(\partial\phi)^2
+\cdots
\right].
$$

The ellipsis is not a failure. It is the point. A general local action contains infinitely many terms. Predictivity comes from the RG hierarchy: near a fixed point, most of these terms are irrelevant and suppressed at long distances.

Define a dimensionless coupling by

$$
\tilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i(\Lambda),
$$

where $\Delta_i$ is the scaling dimension of $\mathcal O_i$ at the fixed point being used for power counting. If we use the IR flow time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

then the linearized flow is

$$
\frac{d\tilde g_i}{d\ell}
=(d-\Delta_i)\tilde g_i+\cdots.
$$

Thus:

| Perturbation | Condition | Wilsonian meaning |
|---|---:|---|
| relevant | $\Delta_i<d$ | grows as the cutoff is lowered; must often be measured or tuned |
| marginal | $\Delta_i=d$ | decided by quantum corrections beyond engineering scaling |
| irrelevant | $\Delta_i>d$ | shrinks toward the IR; gives controlled corrections |

This table is the Wilsonian source of EFT power counting and universality.

## Infinitesimal RG and shell integration

Instead of integrating from $\Lambda_0$ to $\Lambda$ in one step, one can lower the cutoff infinitesimally. Split the field at cutoff $\Lambda$ into

$$
\phi=\phi_{<}+\chi,
$$

where $\chi$ lives only in the shell

$$
\Lambda-d\Lambda<\lvert p\rvert<\Lambda.
$$

Then

$$
e^{-S_{\Lambda-d\Lambda}[\phi_{<}]}
=
\int_{\Lambda-d\Lambda<\lvert p\rvert<\Lambda}\mathcal D\chi\,
\exp\left[-S_\Lambda[\phi_{<}+\chi]\right].
$$

This is the infinitesimal Wilsonian step. After this integration, one usually rescales momenta and fields so the cutoff returns to its original numerical value. The combination of shell integration and rescaling gives beta functions for the couplings.

In exact RG language, this idea becomes a functional differential equation. A schematic Polchinski-type form is

$$
-\Lambda\frac{\partial S_\Lambda}{\partial\Lambda}
=
\frac12\frac{\delta S_\Lambda}{\delta\phi}\cdot\dot C_\Lambda\cdot\frac{\delta S_\Lambda}{\delta\phi}
-
\frac12\operatorname{Tr}\left(\dot C_\Lambda\frac{\delta^2 S_\Lambda}{\delta\phi\,\delta\phi}\right),
$$

where $C_\Lambda$ is a regulated propagator and the dot denotes the cutoff derivative. The precise form depends on cutoff convention, but the structure is universal: one term is tree-like and one term is loop-like.

This equation is not needed for first-pass learning, but it is a powerful reminder that RG flow is not only a list of beta functions for a few couplings. It is a flow of an entire action.

## Wilsonian action versus 1PI effective action

The phrase "effective action" is used for more than one object. The two most common are the Wilsonian effective action $S_\Lambda$ and the 1PI quantum effective action $\Gamma[\varphi]$.

| Object | What is integrated out? | Is there a cutoff on remaining modes? | Typical locality |
|---|---|---|---|
| Wilsonian action $S_\Lambda$ | modes above $\Lambda$ | yes | local derivative expansion when scales are separated |
| 1PI effective action $\Gamma$ | all quantum fluctuations around a background | not in the same sense | generally nonlocal, especially with massless fields |

The Wilsonian action is used to change the resolution of a theory. The 1PI effective action generates one-particle-irreducible correlation functions and quantum-corrected equations of motion.

Both are useful. They answer different questions. Confusing them is a reliable way to make renormalization feel haunted.

## Relation to EFT

Effective field theory is Wilsonian reasoning made practical. Suppose a theory contains light fields $\phi$ and a heavy field $\chi$ of mass $M$. At momenta $Q\ll M$, one can integrate out $\chi$ and write

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\frac{C_4}{M^0}\mathcal O_4
+\frac{C_5}{M}\mathcal O_5
+\frac{C_6}{M^2}\mathcal O_6+\cdots.
$$

The coefficients $C_i$ are Wilson coefficients. They remember the heavy physics.

For a concrete tree-level example, consider the Euclidean action

$$
S[\phi,\chi]
=\int d^d x\left[
\frac12\chi(-\partial^2+M^2)\chi
+\frac{g}{2}\chi\phi^2
+\mathcal L_{\text{light}}(\phi)
\right].
$$

The Gaussian integral over $\chi$ gives

$$
\Delta S_{\text{eff}}[\phi]
=-\frac{g^2}{8}\int d^d x\,d^d y\,
\phi^2(x)G_M(x-y)\phi^2(y),
$$

where

$$
(-\partial^2+M^2)G_M(x-y)=\delta^{(d)}(x-y).
$$

At momenta much smaller than $M$,

$$
\frac{1}{p^2+M^2}
=
\frac{1}{M^2}-\frac{p^2}{M^4}+O\left(\frac{p^4}{M^6}\right).
$$

Therefore the nonlocal expression becomes a local derivative expansion:

$$
\Delta\mathcal L_{\text{eff}}
=-\frac{g^2}{8M^2}\phi^4
+\frac{g^2}{8M^4}\phi^2\partial^2\phi^2
+\cdots,
$$

up to integrations by parts and convention-dependent signs between Euclidean and Lorentzian actions. The expansion parameter is $Q/M$.

This example is Wilsonian EFT in miniature: heavy physics becomes an infinite tower of local operators, ordered by powers of the heavy scale.

## Relation to renormalized perturbation theory

In renormalized perturbation theory, one often writes bare parameters in terms of renormalized parameters and counterterms, then removes regulator dependence from observables. In Wilsonian language, the same success has a geometric explanation.

A renormalizable theory is one whose long-distance predictions near a fixed point depend on only finitely many relevant and marginally relevant directions. The infinitely many irrelevant couplings are present, but their effects at low energy are suppressed. The old phrase "renormalizable interaction" is therefore not a moral distinction between good and bad terms. It is a statement about directions in theory space.

The Wilsonian view also explains why nonrenormalizable interactions are allowed in EFT. They are irrelevant near the low-energy fixed point, so they contribute controlled corrections:

$$
\mathcal A(Q)
=\mathcal A_0(Q)
+c_1\left(\frac{Q}{M}\right)
+c_2\left(\frac{Q}{M}\right)^2
+\cdots.
$$

Nonrenormalizable does not mean meaningless. It means organized by a power expansion.

## Symmetries and regulator choices

The Wilsonian action should include all local operators compatible with the symmetries that are actually preserved. If a regulator breaks a symmetry, counterterms may be needed to restore it in physical quantities, or the symmetry may be obscured throughout the calculation.

For global symmetries, the rule is usually straightforward: include all operators invariant under the symmetry. For gauge theories, the situation is subtler because gauge symmetry is a redundancy, not an ordinary global symmetry. A naive momentum cutoff can clash with gauge invariance. One may instead use gauge-invariant regulators, background-field methods, BRST-compatible formulations, lattice gauge theory, or symmetry-restoring counterterms.

The conceptual Wilsonian statement remains true:

$$
\text{integrated-out short-distance physics must reappear in allowed long-distance operators.}
$$

The technical challenge is to implement "allowed" correctly.

## Common pitfalls

**Thinking $S_\Lambda$ is less real than the bare action.** The bare action at $\Lambda_0$ is also a regulated effective description unless one has a complete microscopic definition. The Wilsonian action at $\Lambda$ is simply the description adapted to longer wavelengths.

**Thinking integrating out means setting fields to zero.** Integrating out means functionally summing over fields. Setting a field to zero is usually wrong. At tree level, integrating out a heavy field often means solving its equation of motion and substituting back, but even that is a controlled approximation to the functional integral.

**Forgetting generated operators.** If an operator is allowed by symmetries, RG flow will generally generate it. Declaring it absent at one scale is not enough unless a symmetry or structural reason keeps it absent.

**Confusing cutoff dependence with observable dependence.** $S_\Lambda$ depends on $\Lambda$. Properly computed low-energy observables do not depend on the arbitrary intermediate cutoff.

**Assuming locality without scale separation.** The derivative expansion is controlled when external momenta are small compared with the modes or masses that were integrated out. Near thresholds or in gapless systems, nonlocal terms may be physically important.

## Relations to other pages

[Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/) turns the definition here into explicit calculations. [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/) derives beta functions by integrating out a thin shell and rescaling. [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) interprets $S_\Lambda$ as a point moving through the space of local actions.

[Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) develops the operator classification introduced here. [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/) explains why irrelevant details are forgotten. [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) uses the same logic for systematic low-energy expansions.

## Research status

The basic Wilsonian construction is established. It is the standard conceptual framework behind modern renormalization, universality, EFT, lattice continuum limits, and critical phenomena.

The active frontier is not whether Wilsonian RG is the right idea. The frontier is how to implement it efficiently and faithfully in hard systems: gauge theories without breaking gauge structure, chiral gauge theories, gravity, real-time dynamics, finite-density systems, strongly coupled theories, tensor-network coarse graining, and functional RG truncations whose errors can be controlled.

## Exercises

### Exercise 1: Free fields stay free

Use the Gaussian free scalar action to show explicitly that integrating out high-momentum modes changes only the normalization of the path integral, not the quadratic low-mode kernel.

<details><summary><strong>Solution</strong></summary>

For the free action,

$$
S[\phi]
=\frac12\int_{\lvert p\rvert<\Lambda_0}\phi(p)(p^2+m^2)\phi(-p),
$$

the split $\phi=\phi_{<}+\phi_{>}$ has disjoint momentum support. Therefore the cross term vanishes and

$$
S[\phi_{<}+\phi_{>}]=S[\phi_{<}]+S[\phi_{>}].
$$

The Wilsonian definition gives

$$
e^{-S_\Lambda[\phi_{<}]}
=\mathcal N_\Lambda e^{-S[\phi_{<}]}
\int\mathcal D\phi_{>}e^{-S[\phi_{>}]}.
$$

The remaining integral is independent of $\phi_{<}$. It contributes only a constant to $S_\Lambda$. Thus

$$
S_\Lambda[\phi_{<}]=S[\phi_{<}]+\text{constant}.
$$

The free theory is closed under Wilsonian mode integration.

</details>

### Exercise 2: The tadpole mass correction in scalar theory

In $\lambda\phi^4/4!$ theory, expand $(\phi_{<}+\phi_{>})^4$ and identify the term that corrects the low-mode mass at first order in $\lambda$. Show that

$$
\Delta m^2
=\frac{\lambda}{2}
\int_{\text{high modes}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

<details><summary><strong>Solution</strong></summary>

The binomial expansion gives

$$
(\phi_{<}+\phi_{>})^4
=\phi_{<}^4+4\phi_{<}^3\phi_{>}+6\phi_{<}^2\phi_{>}^2+4\phi_{<}\phi_{>}^3+\phi_{>}^4.
$$

At first order in $\lambda$, the term with two high fields and two low fields gives

$$
\frac{\lambda}{4!}6\phi_{<}^2\phi_{>}^2
=\frac{\lambda}{4}\phi_{<}^2\phi_{>}^2.
$$

Averaging over high modes gives

$$
\Delta S
=\int d^d x\,\frac{\lambda}{4}\phi_{<}^2(x)
\left\langle\phi_{>}^2(x)\right\rangle.
$$

For a free high-mode propagator,

$$
\left\langle\phi_{>}^2(x)\right\rangle
=
\int_{\text{high modes}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

Comparing with

$$
\Delta S=\int d^d x\,\frac12\Delta m^2\phi_{<}^2,
$$

we obtain

$$
\Delta m^2
=\frac{\lambda}{2}
\int_{\text{high modes}}\frac{d^d q}{(2\pi)^d}\frac{1}{q^2+m^2}.
$$

</details>

### Exercise 3: Relevance from rescaling

Let $S\supset g_i\int d^d x\,\mathcal O_i(x)$ near a fixed point, with $\mathcal O_i$ of scaling dimension $\Delta_i$. Define $\tilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i$. Show that under the IR flow time $\ell=\log(\Lambda_0/\Lambda)$,

$$
\frac{d\tilde g_i}{d\ell}=(d-\Delta_i)\tilde g_i
$$

at the linearized level.

<details><summary><strong>Solution</strong></summary>

After lowering the cutoff, rescale coordinates by $x\to bx$ with $b=e^\ell$ to restore the cutoff. The measure scales as $d^d x\to b^d d^d x$, while the operator scales as $\mathcal O_i\to b^{-\Delta_i}\mathcal O_i$. Therefore the coupling multiplying the dimensionless perturbation scales as

$$
\tilde g_i(\ell)=b^{d-\Delta_i}\tilde g_i(0).
$$

Since $b=e^\ell$,

$$
\tilde g_i(\ell)=e^{(d-\Delta_i)\ell}\tilde g_i(0),
$$

and differentiation gives

$$
\frac{d\tilde g_i}{d\ell}=(d-\Delta_i)\tilde g_i.
$$

If $\Delta_i<d$, the coupling grows toward the IR and the perturbation is relevant.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984) 269–295.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18.
- Mark Srednicki, *Quantum Field Theory*, sections on the renormalization group and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on renormalization and critical phenomena.
- Tim R. Morris, "The Exact Renormalization Group and Approximate Solutions," *International Journal of Modern Physics A* **9** (1994) 2411–2450.

## Version history

- 2026-06-17: First polished draft. Defined the Wilsonian effective action, worked through free and interacting examples, distinguished it from the 1PI effective action, and connected it to EFT and RG flow.
