---
title: "Bare and Renormalized Parameters"
description: "A convention-aware explanation of bare parameters, renormalized parameters, field-strength factors, counterterms, scheme dependence, and running couplings in perturbative QFT."
sidebar:
  label: "Bare and Renormalized Parameters"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27; Coleman 2019, chs. 15–16 and 25; Weinberg 1995, Vol. I, ch. 12; Schwartz 2014, chs. 18–21; Zinn-Justin 2021, chs. 8–10"
topics:
  - bare parameters
  - renormalized parameters
  - field-strength renormalization
  - counterterms
  - renormalization schemes
canonicalTopics:
  - bare-parameter
  - renormalized-parameter
  - field-strength-renormalization
  - counterterm
  - renormalization-scheme
researchStatus:
  established:
    - "The distinction between bare and renormalized parameters is textbook-standard in perturbative renormalization: bare quantities define the regulator-level theory, while renormalized quantities are scheme-dependent labels tied to chosen finite observables or subtraction prescriptions."
  active:
    - "In precision gauge theories and EFTs, parameter definitions, scheme conversions, evanescent operators, unstable-particle schemes, and multi-scale running remain technically active topics, even though the basic logic on this page is settled."
---

## Summary

A **bare parameter** belongs to the regulated Lagrangian. A **renormalized parameter** is the finite parameter used in perturbative calculations after a renormalization scheme has been chosen. The two are not usually equal, and neither should be confused automatically with a directly measured observable.

For real scalar $\phi^4$ theory in $d=4-2\epsilon$, a useful bookkeeping convention is

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi m_0^2=m^2+\delta m^2,
\qquad
Z_\phi^2\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda),
$$

with

$$
Z_\phi=1+\delta Z.
$$

The bare Lagrangian can then be rewritten as

$$
\mathcal L_0=\mathcal L_{\rm ren}+\mathcal L_{\rm ct}.
$$

The point is not that nature secretly contains two masses and two couplings. The point is that perturbation theory needs a clean separation between the quantities used to define the regulated theory and the quantities used to label finite predictions.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Map from a regulated bare theory through a renormalization scheme to renormalized parameters, counterterms, and finite predictions](/figures/perturbative-qft/bare-renormalized-parameters.svg)

<figcaption>

A regulator-level theory is written in terms of bare quantities. A renormalization scheme chooses how to express those bare quantities as renormalized parameters plus counterterms. Physical predictions are regulator-independent after all diagrams, counterterms, and parameter definitions are combined consistently.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/).

For the diagrammatic meaning of the functions being renormalized, review [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/).

## Core idea

A bare parameter is a coordinate on the regulated theory. A renormalized parameter is a coordinate adapted to the finite question being asked.

The same physics can be described by many coordinates. For example, a scalar mass parameter can be defined by the pole of the propagator, by a subtraction condition at Euclidean momentum $p^2=-\mu^2$, or by minimal subtraction of epsilon poles. These choices differ by finite redefinitions. They change intermediate formulas but not properly computed observables.

The conceptual chain is

$$
\text{regulated Lagrangian}
\quad\longrightarrow\quad
\text{renormalized labels}+\text{counterterms}
\quad\longrightarrow\quad
\text{finite predictions}.
$$

Counterterms are not optional patches. They are the terms generated when the bare Lagrangian is rewritten in the renormalized variables chosen for the calculation.

## Setup and conventions

We use qft.org mostly-minus conventions. In scalar examples,

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

so the renormalized four-point vertex is $-i\lambda$ in four dimensions. In dimensional regularization we write

$$
d=4-2\epsilon,
$$

and include $\mu^{2\epsilon}$ with the quartic coupling so that $\lambda$ remains dimensionless near four dimensions.

The bare field is denoted $\phi_0$. Renormalized fields and parameters are written without a subscript. This page uses the scalar theory as a transparent example; spinor, gauge, and EFT examples follow the same logic with more indices, symmetries, and operator mixing.

## Bare quantities

The bare Lagrangian is the Lagrangian before renormalized variables have been introduced. For scalar $\phi^4$ theory,

$$
\mathcal L_0
=
\frac12\partial_\mu\phi_0\,\partial^\mu\phi_0
-
\frac12m_0^2\phi_0^2
-
\frac{\lambda_0}{4!}\phi_0^4
-\Lambda_0.
$$

The subscript $0$ means “bare,” not “tree-level.” Bare quantities know about the regulator. With a hard cutoff, the values required to keep chosen physical quantities fixed depend on the cutoff. In dimensional regularization, the bare coupling is usually written with powers of $\mu$ and counterterm poles so that the bare object itself is independent of the arbitrary renormalization scale when differentiated at fixed regulator.

Bare parameters are not directly measured numbers. They are useful because the regulated Lagrangian is local and symmetry-controlled. Renormalization asks how to express finite predictions in terms of finite labels.

## Renormalized quantities

Introduce the renormalized field $\phi$ by

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z.
$$

Then the bare kinetic term becomes

$$
\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
+
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi.
$$

The first term is put into the renormalized Lagrangian. The second is a counterterm. Similar definitions express the bare mass and coupling in terms of renormalized quantities:

$$
Z_\phi m_0^2=m^2+\delta m^2,
$$

$$
Z_\phi^2\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda).
$$

With these conventions,

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4
-\Lambda,
$$

and

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4
-\delta\Lambda.
$$

The split is conventional. Moving a finite amount from $\mathcal L_{\rm ct}$ into $\mathcal L_{\rm ren}$ is a scheme change, not a new theory.

## Three meanings of mass

Renormalization becomes much less mystical once one stops using one word for several different objects.

| Object | Meaning | Scheme dependence |
|---|---|---|
| $m_0$ | Bare mass in the regulated Lagrangian. | Regulator-dependent and not directly observable. |
| $m$ | Renormalized mass parameter used in perturbation theory. | Yes. Its definition depends on the renormalization scheme. |
| $M$ | Physical pole mass of a stable particle. | No, after all contributions are included. |

For a stable scalar particle, the pole mass is determined by the pole of the resummed propagator,

$$
M^2-m^2-\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
$$

where $\Sigma_{\rm ren}$ is the renormalized self-energy. In an on-shell scheme one chooses counterterms so that $m=M$ order by order. In minimal subtraction one usually does not; $m$ is instead a running parameter tied to the scale $\mu$.

Neither choice is more “real.” The pole location is physical. The parameter used to describe it is a convention.

## Renormalization schemes

A **renormalization scheme** is a rule for fixing the finite and divergent pieces of counterterms. Two common styles are:

| Scheme style | What is fixed? | Typical use |
|---|---|---|
| Physical subtraction | Counterterms are chosen so selected masses, residues, or amplitudes equal measured values at specified kinematics. | Direct physical interpretation, especially for stable particles. |
| Minimal subtraction | Counterterms subtract only pole terms in $\epsilon$, or $1/\overline\epsilon$ in $\overline{\mathrm{MS}}$. | Clean RG equations and multi-loop calculations. |

In minimal subtraction, a generic dimensionless coupling has the schematic form

$$
g_0=\mu^{\kappa\epsilon}
\left[
 g+
 \sum_{n\ge1}\frac{a_n(g)}{\epsilon^n}
\right],
$$

where $\kappa$ depends on the operator dimension and on whether one writes $d=4-\epsilon$ or $d=4-2\epsilon$. The pole coefficients encode beta functions and anomalous dimensions.

In a physical subtraction scheme, one may instead impose conditions such as

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0,
$$

so that the renormalized propagator has a pole at $M^2$ with unit residue. These conditions determine $\delta m^2$ and $\delta Z$, including their finite parts.

## Running from fixed bare quantities

In dimensional regularization, the arbitrary scale $\mu$ enters because the dimension of the coupling changes away from four dimensions. Bare quantities do not depend on this arbitrary bookkeeping scale. Therefore

$$
0=\mu\frac{d}{d\mu}g_0.
$$

Since $g_0$ is written in terms of the renormalized coupling $g(\mu)$, this condition becomes a differential equation for the renormalized coupling:

$$
\beta_g(g)\equiv \mu\frac{dg}{d\mu}\bigg|_{g_0}.
$$

The running coupling is not an extra force. It is the statement that a fixed bare theory can be labeled by different renormalized couplings at different subtraction scales.

A physical prediction $\mathcal O$ cannot depend on the arbitrary scale once all orders are included:

$$
\mu\frac{d}{d\mu}\mathcal O_{\rm physical}=0.
$$

At finite order, residual $\mu$ dependence estimates missing higher-order terms, provided the observable and scheme are chosen sensibly.

## Checks

A good check of the bookkeeping is that the counterterms reproduce local polynomials in external momenta. For the scalar two-point function, the counterterm contribution to the self-energy is

$$
\Sigma_{\rm ct}(p^2)=\delta m^2-\delta Z\,p^2.
$$

This has exactly the form needed to cancel local mass and kinetic divergences. It cannot cancel a threshold logarithm such as $\log(1-p^2/4m^2)$ globally, because that logarithm is nonlocal. That is good: nonlocal finite momentum dependence is part of the prediction, not a convention to subtract away.

A second check is dimensional. In $d=4-2\epsilon$,

$$
[\phi]=1-\epsilon,
\qquad
[\phi^4]=4-4\epsilon,
\qquad
[\lambda_0]=2\epsilon.
$$

Thus $\mu^{2\epsilon}\lambda$ has the correct dimension for the quartic interaction.

## Common pitfalls

**Calling bare parameters physical.** Bare parameters are regulator-level inputs, not measured quantities. The physical content appears after relating renormalized parameters to observables and taking the regulator out of final predictions.

**Thinking renormalized means physical.** Renormalized parameters are finite, but they are still scheme-dependent. A running $\overline{\mathrm{MS}}$ mass is not the same object as a pole mass.

**Forgetting field renormalization.** Field normalization affects residues, external-leg factors, and 1PI functions. Even when $\delta Z$ first appears at higher loop order in a simple scalar example, it is part of the general structure.

**Mixing schemes inside one calculation.** It is fine to convert between schemes, but it is not fine to use a mass from one scheme, a coupling from another, and counterterms from a third without conversion formulas.

**Subtracting nonlocal physics.** Counterterms are local. They cancel local regulator dependence, not physical logarithms, branch cuts, absorptive parts, or thresholds.

## Relations to other pages

- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) derives the explicit counterterm terms and their Feynman rules from the parameter split used here.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how counterterms appear diagrammatically in loop calculations.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) uses $\delta m^2$ and $\delta Z$ to define the renormalized two-point function.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) uses $\delta\lambda$-type counterterms to define finite interaction vertices.
- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains the $d=4-2\epsilon$ regulator and the role of $\mu$.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) defines the 1PI functions to which renormalization conditions are usually applied.

## Research status

The bare-versus-renormalized distinction is settled perturbative QFT. The subtle parts are not the existence of the split, but the bookkeeping in complicated settings: gauge theories, unstable particles, EFT operator bases, evanescent operators, infrared-sensitive observables, and multi-loop scheme conversions.

The conceptual lesson is also stable: parameters in a Lagrangian are coordinates on theory space. Observables are invariant statements extracted after all regulator, scheme, and normalization conventions have been handled consistently.

## Exercises

### Exercise 1: Recover the counterterm split

Start from

$$
\mathcal L_0
=
\frac12\partial_\mu\phi_0\partial^\mu\phi_0
-
\frac12m_0^2\phi_0^2
-
\frac{\lambda_0}{4!}\phi_0^4,
$$

and use

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z,
$$

with

$$
Z_\phi m_0^2=m^2+\delta m^2,
\qquad
Z_\phi^2\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda).
$$

Show that $\mathcal L_0=\mathcal L_{\rm ren}+\mathcal L_{\rm ct}$ with the counterterm Lagrangian stated above.

<details>
<summary><strong>Solution</strong></summary>

Substitute $\phi_0=Z_\phi^{1/2}\phi$ into the kinetic term:

$$
\frac12\partial_\mu\phi_0\partial^\mu\phi_0
=
\frac12Z_\phi\partial_\mu\phi\partial^\mu\phi
=
\frac12\partial_\mu\phi\partial^\mu\phi
+
\frac12\delta Z\partial_\mu\phi\partial^\mu\phi.
$$

The mass term becomes

$$
-\frac12m_0^2\phi_0^2
=-\frac12Z_\phi m_0^2\phi^2
=-\frac12m^2\phi^2-\frac12\delta m^2\phi^2.
$$

The quartic term becomes

$$
-\frac{\lambda_0}{4!}\phi_0^4
=-\frac{Z_\phi^2\lambda_0}{4!}\phi^4
=-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

The first term in each line is $\mathcal L_{\rm ren}$, and the second term in each line is $\mathcal L_{\rm ct}$.

</details>

### Exercise 2: Dimensional check for the quartic coupling

In $d=4-2\epsilon$, show that $[\phi]=1-\epsilon$ and that $\mu^{2\epsilon}\lambda\phi^4$ has mass dimension $d$ when $\lambda$ is dimensionless.

<details>
<summary><strong>Solution</strong></summary>

The kinetic term has dimension $d$:

$$
[\partial_\mu\phi\partial^\mu\phi]=2+2[\phi]=d.
$$

Therefore

$$
[\phi]=\frac{d-2}{2}=1-\epsilon.
$$

Then

$$
[\phi^4]=4(1-\epsilon)=4-4\epsilon.
$$

Since $[\mu^{2\epsilon}]=2\epsilon$, the interaction has dimension

$$
2\epsilon+4-4\epsilon=4-2\epsilon=d.
$$

</details>

### Exercise 3: Scheme change as a finite redefinition

Suppose two schemes define couplings $g$ and $g'$ related by

$$
g'=g+a g^2+O(g^3),
$$

where $a$ is finite. Show how the coefficient of $g^2$ in an observable changes under this finite redefinition.

<details>
<summary><strong>Solution</strong></summary>

Consider an observable expanded as

$$
\mathcal O=c_0+c_1g+c_2g^2+O(g^3).
$$

Invert the scheme relation:

$$
g=g'-a(g')^2+O((g')^3).
$$

Substitution gives

$$
\mathcal O
=c_0+c_1g'+(c_2-a c_1)(g')^2+O((g')^3).
$$

The coefficient of $(g')^2$ differs from the coefficient of $g^2$, but the transformed series describes the same observable. At finite order, inconsistent mixing of the two series produces artificial scheme dependence.

</details>

### Exercise 4: Bare scale independence and beta functions

Let a bare coupling be written schematically as

$$
g_0=\mu^{\kappa\epsilon}F(g(\mu),\epsilon).
$$

Show that $\mu dg_0/d\mu=0$ implies a differential equation for $g(\mu)$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate at fixed bare coupling and fixed regulator:

$$
0=\mu\frac{d}{d\mu}\left[\mu^{\kappa\epsilon}F(g(\mu),\epsilon)\right].
$$

This gives

$$
0=
\kappa\epsilon\mu^{\kappa\epsilon}F
+
\mu^{\kappa\epsilon}\frac{\partial F}{\partial g}\,\mu\frac{dg}{d\mu}.
$$

Therefore

$$
\mu\frac{dg}{d\mu}
=-\kappa\epsilon\frac{F}{\partial F/\partial g}.
$$

After expanding near $\epsilon=0$ and using the counterterm pole structure, this becomes the beta function for the renormalized coupling.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§13–20 and §27, for propagator corrections, vertex corrections, all-order perturbation theory, and renormalization-scheme examples.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterms, renormalized propagators, and the logic of regularization and renormalization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–21, for mass renormalization, counterterms, renormalized perturbation theory, and renormalizability.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, for a general treatment of renormalization and counterterms in perturbative QFT.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for the field-theoretic and statistical-mechanics view of regularization, bare theories, and renormalization.
- J. C. Collins, *Renormalization*, for a systematic treatment of renormalization, subtraction schemes, and perturbative consistency.

## Version history

- **2026-06-12:** Initial standardized page.
