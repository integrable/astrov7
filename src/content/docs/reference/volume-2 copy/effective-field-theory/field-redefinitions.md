---
title: "Field Redefinitions"
description: "How local invertible changes of field variables reorganize EFT operators without changing physical observables."
sidebar:
  label: "Field Redefinitions"
  order: 9
level: Graduate
status: "Polished draft"
source: "Kamefuchi, O'Raifeartaigh, and Salam 1961; Chisholm 1961; Weinberg Vol. I, field redefinitions and EFT; Burgess 2020, ch. 2; Georgi EFT lectures; Arzt 1995."
topics:
  - effective field theory
  - field redefinitions
  - equivalence theorem
  - redundant operators
  - equations of motion
canonicalTopics:
  - field-redefinitions
  - equivalence-theorem
  - eom-redundancy
  - eft-operator-bases
researchStatus:
  established:
    - "Local invertible field redefinitions leave physical observables such as on-shell S-matrix elements invariant, while changing off-shell Green functions and operator-basis coordinates."
  active:
    - "Field redefinitions remain technically important in gauge EFTs, gravitational EFT, SMEFT basis conversions, higher-derivative theories, amplitudes bases, composite-operator sources, and nonperturbative formulations where locality, measure, and boundary subtleties matter."
---

## Summary

A **field redefinition** is a change of variables in the fields used to describe a theory. In an effective field theory, one often uses local perturbative redefinitions such as

$$
\phi \longrightarrow \phi' + \frac{1}{M^n}F(\phi',\partial\phi',\ldots),
$$

where $F$ is a local expression built from light fields and derivatives. Such a redefinition can move terms between operators, change Wilson coefficients, and simplify a Lagrangian. It does **not** change physical observables when it is local, invertible order by order in the EFT expansion, and used consistently.

The essential identity is

$$
S[\phi+\delta\phi]
=
S[\phi]
+
\int d^d x\,\frac{\delta S}{\delta\phi(x)}\delta\phi(x)
+O(\delta\phi^2).
$$

Thus an operator proportional to the equations of motion can be generated or removed by a field redefinition. This is why field redefinitions are the mechanism behind many EFT operator-basis reductions.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![A field-redefinition and redundant-operator map: a local field redefinition shifts the action by equations-of-motion terms and total derivatives, which changes the operator basis and Wilson coefficients while leaving physical observables unchanged.](/figures/renormalization-rg-eft/eft-field-redefinition-basis-map.svg)

<figcaption>

A local invertible field redefinition is a coordinate change on the space of EFT descriptions. It can trade operators proportional to equations of motion for shifts of other operators and Wilson coefficients. Off-shell Green functions and basis coordinates change; physical observables do not.

</figcaption>
</figure>

:::note[Field redefinitions are not approximations]
A field redefinition is not the claim that an operator is "small enough to ignore." It is the claim that two Lagrangians are related by a change of variables, so they describe the same physical predictions after all coefficients and observables are transformed consistently.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Matching](/renormalization-rg-eft/effective-field-theory/matching/).

Useful background includes [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/), [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/), and [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/).

## Core idea

A Lagrangian is a coordinate system on physics. It is not the physics itself.

For example, the same low-energy amplitudes can be described using one operator basis or another:

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_0+\frac{C_1}{M^2}\mathcal O_1+\frac{C_2}{M^2}\mathcal O_2+\frac{C_E}{M^2}E_\phi F
$$

or, after a field redefinition,

$$
\mathcal L_{\text{EFT}}'
=
\mathcal L_0+\frac{C_1'}{M^2}\mathcal O_1+\frac{C_2'}{M^2}\mathcal O_2.
$$

Here $E_\phi$ denotes the equation-of-motion operator for $\phi$, and $F$ is a local expression. The primed coefficients are not generally equal to the unprimed coefficients. The individual Lagrangian terms have changed. But amplitudes, spectra, and properly defined observables have not.

The slogan is

$$
\text{field redefinitions move information; they do not delete it.}
$$

This is especially important in EFT because one writes all allowed local operators. Many of those operators are not independent once integration by parts, algebraic identities, equations of motion, and field redefinitions are taken into account.

## Setup and conventions

We use the conventions in [Conventions and Notation](/renormalization-rg-eft/conventions/). For a real scalar, the mostly-minus kinetic convention is

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-V_{\text{int}}(\phi).
$$

The Euler–Lagrange derivative is

$$
\frac{\delta S_0}{\delta\phi}
=
-\left(\Box+m^2\right)\phi
-\frac{\partial V_{\text{int}}}{\partial\phi}.
$$

It is convenient to define

$$
E_\phi
\equiv
-\frac{\delta S_0}{\delta\phi}
=
\left(\Box+m^2\right)\phi
+\frac{\partial V_{\text{int}}}{\partial\phi}.
$$

With this convention, the classical equation of motion is $E_\phi=0$.

For several fields $\Phi^A$, a local field redefinition has the form

$$
\Phi^A \longrightarrow \Phi^{\prime A}+\Delta^A(\Phi',\partial\Phi',\ldots),
$$

where $\Delta^A$ is organized in the EFT expansion:

$$
\Delta^A
=
\frac{1}{M}F_1^A
+
\frac{1}{M^2}F_2^A
+
\cdots.
$$

The redefinition must respect the degrees of freedom of the EFT. It can be nonlinear and derivative-dependent, but it must be invertible order by order in $1/M$.

## The basic identity

Let

$$
\phi=\phi'+\delta\phi.
$$

Expanding the action gives

$$
S[\phi'+\delta\phi]
=
S[\phi']
+
\int d^d x\,\frac{\delta S}{\delta\phi'(x)}\delta\phi(x)
+O(\delta\phi^2).
$$

If $\delta\phi$ is order $1/M^n$, then the leading change in the Lagrangian is an equation-of-motion operator:

$$
\Delta\mathcal L
=
\frac{\delta S}{\delta\phi}\delta\phi
+\text{higher order}.
$$

Using the convention $E_\phi=-\delta S_0/\delta\phi$, a redefinition

$$
\phi\to\phi'+\frac{a}{M^n}F
$$

changes the leading Lagrangian by

$$
\mathcal L_0[\phi]
=
\mathcal L_0[\phi']
-\frac{a}{M^n}E_\phi F
+\text{total derivative}
+O(M^{-2n}).
$$

Therefore, if an EFT contains

$$
\mathcal L_{\text{EFT}}
\supset
\frac{c_E}{M^n}E_\phi F,
$$

one can remove this operator at that order by choosing $a=c_E$, while shifting other terms at higher orders.

:::tip[The order matters]
Removing an operator at order $1/M^n$ generally generates new operators at order $1/M^{2n}$ and beyond. In a truncated EFT this is not a problem; it is part of the power counting.
:::

## Example: removing an EOM operator

Consider a scalar EFT whose leading Lagrangian is

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The leading equation-of-motion operator is

$$
E_\phi
=
(\Box+m^2)\phi+\frac{\lambda}{3!}\phi^3.
$$

Suppose the EFT also contains

$$
\Delta\mathcal L
=
\frac{c}{M^2}\phi^2 E_\phi.
$$

Use the field redefinition

$$
\phi=\phi'+\frac{c}{M^2}\phi'^2.
$$

Then, to order $1/M^2$,

$$
\mathcal L_0[\phi]
=
\mathcal L_0[\phi']
-\frac{c}{M^2}\phi'^2E_{\phi'}
+O(M^{-4}).
$$

This cancels the original $c\phi^2E_\phi/M^2$ term, up to higher-order effects and coefficient shifts in other operators.

The operator was not physically meaningless. It encoded a choice of field coordinate. Removing it changes the mapping between the coefficient list and the observables.

## Example: derivative field redefinitions

Derivative redefinitions are common in EFT. For instance,

$$
\phi=\phi'+\frac{a}{M^2}\Box\phi'
$$

changes the leading scalar action by

$$
\Delta\mathcal L
=-\frac{a}{M^2}E_\phi\Box\phi
+O(M^{-4}).
$$

After integrations by parts, this can trade higher-derivative quadratic operators for lower-derivative operators plus higher-order corrections. This is one reason EFTs can have higher-derivative operators without necessarily introducing new propagating ghost degrees of freedom inside the regime of validity.

The phrase "inside the regime of validity" is doing real work. A truncated higher-derivative EFT should not be interpreted as an exact high-energy theory with additional poles trusted all the way to arbitrarily large momenta. The EFT is an expansion for $Q/M\ll1$.

## Why the S-matrix is unchanged

The on-shell invariance of scattering amplitudes under local field redefinitions is often called the **equivalence theorem**.

A quick way to see the idea is through LSZ reduction. A term proportional to the free equation of motion contributes factors such as

$$
(p^2-m^2)
$$

on external scalar legs. LSZ also multiplies the connected Green function by external inverse propagator factors and then takes $p^2\to m^2$. Contributions that differ only by equation-of-motion insertions either vanish on shell or are absorbed into residue and contact-term changes, provided the field redefinition is local and invertible.

The more invariant statement is:

$$
\mathcal L
\quad\text{and}\quad
\mathcal L'
=\mathcal L+\text{EOM terms}+\text{consistent coefficient shifts}
$$

give the same physical $S$-matrix.

They do not give the same off-shell Green functions. Off-shell correlators depend on the interpolating fields used to probe the theory. Physical amplitudes do not.

## Path-integral viewpoint

In the path integral, a field redefinition is a change of variables:

$$
Z[J]
=
\int\mathcal D\phi\,e^{iS[\phi]+i\int J\phi}
=
\int\mathcal D\phi'\,\mathcal J[\phi']
\,e^{iS[\phi(\phi')]+i\int J\phi(\phi')}.
$$

The Jacobian is

$$
\mathcal J[\phi']
=
\det\left(\frac{\delta\phi}{\delta\phi'}\right).
$$

For ordinary local perturbative field redefinitions in dimensional regularization, the Jacobian often contributes only local terms that can be absorbed into the EFT coefficients, or is formally unity in common calculations. In a cutoff regulator, the same Jacobian is more visibly a local contribution to the Wilsonian action.

This should not be turned into the dangerous slogan "Jacobians never matter." They can matter for anomalous transformations, nonlocal transformations, transformations of constrained variables, boundary-sensitive problems, and changes of variables that are not innocent in the chosen regulator.

The safe EFT statement is:

$$
\text{a local Jacobian contributes local terms, so it belongs in the EFT action.}
$$

## What changes and what does not

| Object | Does it change under field redefinitions? | Comment |
|---|---:|---|
| Off-shell Green functions | Yes | They depend on the field coordinates and sources. |
| Wilson coefficients | Yes | They are basis coordinates, not observables. |
| Operator basis | Yes | EOM and redundant operators can be removed or introduced. |
| Counterterms | Yes | The split among operators changes. |
| Pole masses | No | When consistently defined. |
| On-shell scattering amplitudes | No | Up to standard wavefunction normalization and external-state conventions. |
| Symmetry realization | Can change | A symmetry may become nonlinear or less manifest. |
| Anomaly matching | No | Anomalies are physical obstruction data, though their representatives can shift. |

The most common student mistake is to think that if a coefficient changes, the theory has changed. Coefficients are coordinates. Observables are the coordinate-independent output.

## Sources, currents, and composite operators

Field redefinitions are simplest for the $S$-matrix. They are more delicate for correlation functions of composite operators.

If a source $J$ couples to a field or operator,

$$
S\supset \int d^d x\,J\mathcal O,
$$

and one changes field variables, the operator coupled to $J$ generally changes. Therefore, a statement like

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\quad\text{is invariant}
$$

is not correct unless the source and operator definition are transformed as part of the same change of variables.

For EFT matching this matters a lot. Matching a current, stress tensor, weak Hamiltonian operator, or density response requires tracking how the external source couples in the chosen basis. A redundant operator in the action can still affect contact terms or source-dependent definitions if the source sector is not transformed consistently.

## Gauge theories

In gauge theories, field redefinitions must preserve the gauge redundancy or be accompanied by a consistent transformation of gauge fixing, ghosts, sources, and BRST data.

A gauge-covariant field redefinition might look like

$$
\psi\to\psi+\frac{a}{M^2}D^2\psi,
\qquad
A_\mu\to A_\mu+\frac{b}{M^2}D^\nu F_{\nu\mu},
$$

where $D_\mu$ is the covariant derivative. Such redefinitions can remove operators proportional to gauge-field or matter equations of motion. But a noncovariant change of variables can hide gauge invariance, complicate Ward identities, or mix physical and gauge-fixing sectors.

The practical rule is:

$$
\text{do field redefinitions in a symmetry-respecting language whenever possible.}
$$

For gauge EFTs this often means using covariant derivatives, field strengths, BRST-aware operator bases, and background-field methods.

## Field redefinitions as coordinate changes on theory space

Theory space contains actions modulo redundancies. A local field redefinition moves along a redundant direction. If $g^i$ are couplings, a redefinition induces a coordinate transformation

$$
g^i\to g^{\prime i}(g).
$$

Beta functions transform as vector fields:

$$
\beta^{\prime i}(g')
=
\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

This is the same geometric point that appears in scheme dependence. Some changes of variables are called changes of renormalization scheme; others are called field redefinitions or basis changes. In all cases, physical statements should be formulated in terms of invariant data.

## Common pitfalls

**Thinking off-shell equality is required.** Field redefinitions generally change off-shell Green functions. The invariant objects are physical observables, not arbitrary correlators of arbitrary field variables.

**Dropping an EOM operator without transforming coefficients.** Removing a redundant operator shifts other coefficients. If those shifts are ignored, the calculation has changed.

**Using lowest-order equations of motion beyond their order.** In EFT, one uses the lower-order EOM to remove operators at a fixed order. At the next order, the redefinition generates additional terms that must be included if working to that accuracy.

**Treating nonlocal transformations like local field redefinitions.** The equivalence theorem assumes locality and invertibility. A nonlocal transformation can change the analytic structure and the degrees of freedom.

**Forgetting sources and contact terms.** Composite-operator correlators require transforming the source sector. On-shell scattering is safer than off-shell response functions.

**Mistaking a bad truncation for a ghost.** A higher-derivative EFT term may produce extra poles if treated as exact. Those poles often lie outside the EFT regime and should not be trusted.

## Relations to other pages

This page explains the mechanism behind many reductions in [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/). It extends the operator-level discussion in [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/) into the EFT language of Wilson coefficients and basis choice.

It is also closely related to [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), because field redefinitions are organized order by order; to [Matching](/renormalization-rg-eft/effective-field-theory/matching/), because matching coefficients are basis-dependent; and to [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), because both scheme changes and field redefinitions are coordinate changes on descriptions.

## Research status

The equivalence of local field redefinitions for on-shell observables is established perturbative QFT technology. It underlies EFT operator-basis construction, amplitude bases, chiral perturbation theory, SMEFT and HEFT basis changes, heavy-particle EFTs, and gravitational EFT.

Active technical issues appear when the simple theorem is pushed into more delicate settings: gauge-fixed variables, BRST/BV formalisms, anomalous transformations, boundaries, finite density, nonperturbative measures, curved spacetime, evanescent operators in dimensional regularization, and automated basis-reduction software.

## Exercises

### Exercise 1: Generate an EOM operator

Let $S_0[\phi]$ be any action and perform the perturbative field redefinition

$$
\phi=\phi'+\frac{a}{M^2}F(\phi').
$$

Show that the order-$1/M^2$ change in the action is proportional to the Euler–Lagrange derivative of $S_0$.

<details><summary><strong>Solution</strong></summary>

Taylor expand the action as a functional:

$$
S_0[\phi'+\delta\phi]
=
S_0[\phi']
+
\int d^d x\,\frac{\delta S_0}{\delta\phi'(x)}\delta\phi(x)
+O(\delta\phi^2).
$$

With

$$
\delta\phi=\frac{a}{M^2}F(\phi'),
$$

we get

$$
S_0[\phi]
=
S_0[\phi']
+
\frac{a}{M^2}
\int d^d x\,\frac{\delta S_0}{\delta\phi'}F(\phi')
+O(M^{-4}).
$$

Thus the induced order-$1/M^2$ operator is proportional to the leading Euler–Lagrange derivative.

</details>

### Exercise 2: Removing a redundant scalar operator

For

$$
\mathcal L_0
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2,
$$

show that the operator

$$
\mathcal O_E=\phi^3(\Box+m^2)\phi
$$

can be removed at order $1/M^2$ by a local field redefinition. What other operator is generated if the original theory also contains $-\lambda\phi^4/4!$ at leading order?

<details><summary><strong>Solution</strong></summary>

For the free part,

$$
E_\phi=(\Box+m^2)\phi.
$$

The field redefinition

$$
\phi=\phi'+\frac{c}{M^2}\phi'^3
$$

shifts the free Lagrangian by

$$
\Delta\mathcal L_0
=-\frac{c}{M^2}\phi'^3(\Box+m^2)\phi'+O(M^{-4}).
$$

Thus it removes $c\mathcal O_E/M^2$ at this order.

If the leading interaction includes

$$
-\frac{\lambda}{4!}\phi^4,
$$

then the leading equation of motion is

$$
(\Box+m^2)\phi+\frac{\lambda}{3!}\phi^3=0.
$$

Using the interacting EOM, the same redundant structure trades into a contribution proportional to

$$
-\frac{\lambda}{3!}\phi^6.
$$

Equivalently, the field redefinition shifts the coefficient of the $\phi^6$ operator at order $1/M^2$. The information was moved into another Wilson coefficient.

</details>

### Exercise 3: Why off-shell Green functions change

Let a scalar source couple as $\int J\phi$. Under the field redefinition $\phi=\phi'+a\phi'^2/M$, what happens to the source term? Explain why this means off-shell correlators of $\phi$ and $\phi'$ need not agree.

<details><summary><strong>Solution</strong></summary>

The source term becomes

$$
\int d^d x\,J\phi
=
\int d^d x\,J\phi'
+\frac{a}{M}\int d^d x\,J\phi'^2.
$$

Thus the source no longer couples only linearly to the new field. Functional derivatives with respect to $J$ insert the old composite expression

$$
\phi'+\frac{a}{M}\phi'^2,
$$

not simply $\phi'$. Therefore correlators of the old field and the new field are different unless the source coupling is transformed consistently. This is why off-shell Green functions are field-coordinate dependent.

</details>

## References

- Kamefuchi, O'Raifeartaigh, and Salam, "Change of Variables and Equivalence Theorems in Quantum Field Theories," *Nuclear Physics* **28** (1961) 529–549.
- J. S. R. Chisholm, "Change of Variables in Quantum Field Theories," *Nuclear Physics* **26** (1961) 469–479.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially discussions of field redefinitions, interpolating fields, and effective interactions.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, redundant interactions, and power counting.
- Howard Georgi, EFT lectures and *Weak Interactions and Modern Particle Theory*, for the practical EFT view of basis choice.
- C. Arzt, "Reduced Effective Lagrangians," *Physics Letters B* **342** (1995) 189–195.
- Aneesh V. Manohar, EFT lecture notes, for applications to operator bases and matching.

## Version history

- 2026-06-18: First polished draft. Added the field-redefinition identity, EOM-operator removal, on-shell equivalence, path-integral Jacobian caveats, gauge-theory cautions, and EFT basis interpretation.
