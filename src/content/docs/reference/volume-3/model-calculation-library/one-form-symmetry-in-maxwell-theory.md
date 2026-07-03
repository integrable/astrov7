---
title: "One-Form Symmetry in Maxwell Theory"
description: "A model calculation deriving electric and magnetic one-form symmetries in four-dimensional Maxwell theory and their action on Wilson and ’t Hooft lines."
sidebar:
  label: "One-Form Symmetry in Maxwell"
  order: 12
level: Graduate
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett 2015; Srednicki §§54–58; Schwartz Chs. 8–9 and 25; Altland–Simons Ch. 10."
topics:
  - Maxwell theory
  - one-form symmetry
  - Wilson line
  - "’t Hooft line"
  - electric-magnetic duality
  - higher-form current
canonicalTopics:
  - maxwell-theory
  - electric-one-form-symmetry
  - magnetic-one-form-symmetry
  - higher-form-current
  - model-calculation
researchStatus:
  established:
    - "Pure four-dimensional Maxwell theory has electric and magnetic one-form symmetries whose charged objects are Wilson and ’t Hooft lines."
  active:
    - "Global choices, compactness, charge lattices, boundary conditions, dynamical matter, monopoles, and duality frames refine the precise symmetry group and anomaly data."
---

## Summary

Pure Maxwell theory in four spacetime dimensions has two one-form global symmetries:

$$
U(1)^{(1)}_{\rm e}\times U(1)^{(1)}_{\rm m}.
$$

The electric one-form symmetry acts on Wilson lines. The magnetic one-form symmetry acts on ’t Hooft lines. This is the simplest continuum model where higher-form symmetry is not a fancy abstraction but a direct rewriting of Maxwell’s equations.

Let

$$
F=dA
$$

be the electromagnetic field strength. In the absence of dynamical electric charges and monopoles, Maxwell’s equations are

$$
d{*F}=0,\qquad dF=0.
$$

These are conservation laws. For one-form symmetries in $d=4$, the conserved currents are two-forms. A convenient normalization is

$$
J_{\rm e}=\frac{1}{e^2}F,\qquad
{*J_{\rm m}}=\frac{1}{2\pi}F.
$$

The second equation defines the magnetic current by its dual; this avoids a signature-dependent sign in ${*}{*}$ on two-forms. The conserved charges are integrals over closed two-surfaces $\Sigma$:

$$
Q_{\rm e}(\Sigma)=\int_\Sigma {*J_{\rm e}}
=\frac{1}{e^2}\int_\Sigma {*F},
\qquad
Q_{\rm m}(\Sigma)=\int_\Sigma {*J_{\rm m}}
=\frac{1}{2\pi}\int_\Sigma F.
$$

If $\Sigma$ links a Wilson line, $Q_{\rm e}(\Sigma)$ measures its electric charge. If $\Sigma$ links an ’t Hooft line, $Q_{\rm m}(\Sigma)$ measures its magnetic charge.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A two-sphere linking a line operator in four-dimensional Maxwell theory, measuring electric or magnetic one-form charge.](/figures/symmetry-anomalies-topology/maxwell-one-form-symmetry.svg)

<figcaption>

In four-dimensional Maxwell theory, one-form charges are measured on closed two-surfaces $\Sigma$ linking line operators. Electric flux measures Wilson-line charge; magnetic flux measures ’t Hooft-line charge.

</figcaption>
</figure>

This page derives the currents, charges, charged line operators, breaking by dynamical matter, and the Coulomb-phase interpretation.

## Prerequisites

You should know Maxwell theory, Wilson lines, ’t Hooft lines, and the definition of a $q$-form global symmetry. The useful preceding pages are Higher-Form Symmetries, Charged Extended Operators, Electric and Magnetic One-Form Symmetries, and Wilson-Loop Area Law.

Differential-form notation is used because it makes the symmetry structure nearly impossible to miss. In components, the statements are just Gauss’s law and the absence of magnetic monopoles.

## Core idea

An ordinary zero-form global symmetry has a conserved current one-form $j=j_\mu dx^\mu$, with conservation

$$
d{*j}=0.
$$

A one-form global symmetry has a conserved current two-form $J$, with conservation

$$
d{*J}=0.
$$

The charge is not integrated over a spatial volume. It is integrated over a codimension-two spatial surface.

In four spacetime dimensions, that surface is a closed two-surface. The charged objects are line operators. The topological charge operator can slide freely unless it crosses a charged line.

In Maxwell theory, the two conservation laws are exactly the two Maxwell equations without sources:

$$
d{*F}=0,\qquad dF=0.
$$

One equation is dynamical. The other is the Bianchi identity. Both become global symmetries when the corresponding charged dynamical objects are absent.

## Setup and conventions

Take the Lorentzian Maxwell action

$$
S=-\frac{1}{2e^2}\int F\wedge {*F}.
$$

In components this is

$$
S=-\frac{1}{4e^2}\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

Varying $A$ gives

$$
d{*F}=0.
$$

The definition $F=dA$ gives the Bianchi identity

$$
dF=0.
$$

We use the compact $U(1)$ normalization in which magnetic flux obeys

$$
\frac{1}{2\pi}\int_{\Sigma}F\in\mathbb Z
$$

on appropriate closed two-surfaces when magnetic defects or nontrivial bundles are included.

:::note[Source note: compactness]
Noncompact Maxwell theory and compact Maxwell theory have the same local equations but different global line operators and flux sectors. Higher-form symmetry is sensitive to this global choice. This page uses compact normalization when discussing quantized Wilson and ’t Hooft charges.
:::

## Electric one-form symmetry

Define the electric one-form current by

$$
J_{\rm e}=\frac{1}{e^2}F.
$$

Then

$$
d{*J_{\rm e}}=\frac{1}{e^2}d{*F}=0
$$

by the Maxwell equation. The electric one-form charge on a closed two-surface $\Sigma$ is

$$
Q_{\rm e}(\Sigma)=\int_\Sigma {*J_{\rm e}}
=\frac{1}{e^2}\int_\Sigma {*F}.
$$

This is electric flux. If $\Sigma$ is a sphere surrounding an electric charge, $Q_{\rm e}$ measures that charge.

The charged line operators are Wilson lines,

$$
W_q(C)=\exp\left(-iq\oint_C A\right).
$$

In the presence of a Wilson line insertion, the Maxwell equation has a delta-function source supported on $C$:

$$
\frac{1}{e^2}d{*F}=q\,\delta_C.
$$

Therefore a two-surface $\Sigma$ linking $C$ detects

$$
Q_{\rm e}(\Sigma)=q\,\ell(\Sigma,C),
$$

where $\ell(\Sigma,C)$ is the linking number. Equivalently, the electric one-form symmetry operator acts on a Wilson line by a phase,

$$
U_{\rm e}(\alpha,\Sigma)W_q(C)
=
e^{i\alpha q\,\ell(\Sigma,C)}
W_q(C)U_{\rm e}(\alpha,\Sigma).
$$

## Magnetic one-form symmetry

Define the magnetic one-form current by specifying its dual:

$$
{*J_{\rm m}}=\frac{1}{2\pi}F.
$$

Then

$$
d{*J_{\rm m}}
=
\frac{1}{2\pi}dF=0
$$

by the Bianchi identity. The magnetic one-form charge is

$$
Q_{\rm m}(\Sigma)=\int_\Sigma {*J_{\rm m}}
=
\frac{1}{2\pi}\int_\Sigma F.
$$

This is magnetic flux.

The charged line operators are ’t Hooft lines. An ’t Hooft line $T_m(C)$ of magnetic charge $m$ is defined by requiring a singular magnetic flux around the line:

$$
\frac{1}{2\pi}\int_{S^2_{\rm link}}F=m.
$$

A magnetic symmetry surface linking $T_m(C)$ gives the phase

$$
U_{\rm m}(\beta,\Sigma)T_m(C)
=
e^{i\beta m\,\ell(\Sigma,C)}
T_m(C)U_{\rm m}(\beta,\Sigma).
$$

Thus Wilson lines are charged under $U(1)^{(1)}_{\rm e}$, and ’t Hooft lines are charged under $U(1)^{(1)}_{\rm m}$.

## Component translation

In mostly-minus signature, write the electric and magnetic fields as usual. The electric one-form charge on a spatial two-sphere $S^2$ is

$$
Q_{\rm e}(S^2)=\frac{1}{e^2}\int_{S^2}\mathbf E\cdot d\mathbf S.
$$

The magnetic one-form charge is

$$
Q_{\rm m}(S^2)=\frac{1}{2\pi}\int_{S^2}\mathbf B\cdot d\mathbf S.
$$

The conservation of $Q_{\rm e}$ is Gauss’s law with no dynamical electric charges. The conservation of $Q_{\rm m}$ is the absence of magnetic monopoles.

This is the best sanity check: one-form symmetry in Maxwell theory is not new physics added to electromagnetism. It is the symmetry meaning of the familiar flux conservation laws.

## Dynamical charges break the symmetries

The electric one-form symmetry is exact only if Wilson lines cannot end. Dynamical electrically charged matter allows Wilson lines to end on charged particle worldlines. Then the electric flux through a surface can change when a charged particle crosses it.

With electric current $j_{\rm el}$,

$$
\frac{1}{e^2}d{*F}={*j_{\rm el}},
$$

so

$$
d{*J_{\rm e}}={*j_{\rm el}}.
$$

The electric one-form symmetry is explicitly broken.

Similarly, dynamical monopoles break the magnetic one-form symmetry. If magnetic current is present, then

$$
dF=2\pi\,{*j_{\rm mag}},
$$

so

$$
d{*J_{\rm m}}={*j_{\rm mag}}.
$$

This explains the charged-operator criterion: a one-form symmetry is exact when its charged lines are genuine, meaning they cannot end on dynamical local operators.

## Coulomb phase and symmetry breaking

Pure Maxwell theory in four dimensions is gapless. The photon can be interpreted as the Goldstone-like mode for the spontaneous breaking of electric and magnetic one-form symmetries.

This statement is the higher-form analogue of the familiar fact that broken continuous ordinary symmetries produce gapless modes. The analogy is not one-to-one in every detail, but the diagnostic is clear: Wilson and ’t Hooft lines in the Coulomb phase do not have an area law. Their long-distance behavior is controlled by perimeter terms plus Coulomb interactions.

For a rectangular Wilson loop with electric charge $q$, one finds schematically

$$
\langle W_q(C_{R,T})\rangle
\sim
\exp\left[-\mu(2R+2T)-T\,V(R)\right],
$$

with

$$
V(R)\sim \frac{e^2q^2}{4\pi R}.
$$

The $1/R$ potential is the Coulomb signal of a gapless photon, not a confining string tension.

## Electric-magnetic duality

Pure Maxwell theory has an electric-magnetic duality that exchanges equations of motion and Bianchi identities. In a duality frame, Wilson and ’t Hooft lines are exchanged, and the electric and magnetic one-form symmetries are exchanged.

With compact normalization, the electric and magnetic charges form a lattice. A line operator may carry both charges,

$$
(q,m)\in\mathbb Z\oplus\mathbb Z,
$$

and is called a dyonic line. The Dirac pairing between two dyonic lines is

$$
\langle(q,m),(q',m')\rangle=qm'-q'm.
$$

Mutual locality requires this pairing to be integral, with normalization depending on the chosen charge units. This lattice viewpoint becomes essential in nonabelian gauge theory, global forms of gauge groups, and the Witten effect.

## Background fields preview

A one-form symmetry is coupled to a two-form background gauge field. Thus the electric and magnetic one-form symmetries of Maxwell theory are probed by background two-form fields.

Schematically, one introduces two-form backgrounds $B_{\rm e}$ and $B_{\rm m}$ so that surface operators and line operators acquire controlled phases under background gauge transformations. The full compact theory requires careful differential-cohomology language, because flux quantization and line-operator charges matter.

For this model calculation, the practical lesson is:

$$
\text{one-form symmetry}\quad\Rightarrow\quad \text{two-form background field}.
$$

This is the higher-form analogue of coupling an ordinary current $j^\mu$ to a one-form background gauge field $A_\mu$.

## Mixed anomaly preview

The electric and magnetic one-form symmetries are not completely independent in all global formulations. Their symmetry operators can have nontrivial linking phases, and simultaneous background fields can reveal a mixed anomaly.

A rough diagnostic is that an electric symmetry surface and a magnetic symmetry surface can intersect in a way that records the Dirac pairing between Wilson and ’t Hooft lines. A precise statement requires specifying compactness, charge lattice, spacetime topology, and counterterm conventions.

This is why Maxwell theory remains a useful laboratory for anomaly thinking: the local equations are elementary, but the global symmetry data are already rich.

:::caution[Do not overstate the local equations]
The equations $dF=0$ and $d{*F}=0$ are local. The symmetry group, charge lattice, allowed line operators, and mixed anomaly depend on global choices. One-form symmetry is a global statement, not just a differential equation.
:::

## Common pitfalls

**Confusing gauge symmetry with one-form global symmetry.** The transformation $A\mapsto A+d\lambda$ is gauge redundancy. The electric and magnetic one-form symmetries are physical global symmetries acting on line operators.

**Forgetting dynamical matter.** Electrons explicitly break the electric one-form symmetry; monopoles explicitly break the magnetic one-form symmetry.

**Treating $dF=0$ as optional.** In ordinary Maxwell theory without monopoles, $dF=0$ is the Bianchi identity and gives magnetic one-form symmetry.

**Ignoring compactness.** Noncompact Maxwell theory and compact $U(1)$ gauge theory differ globally. Flux quantization, monopoles, and line-operator spectra depend on the compact theory.

**Expecting an area law.** Pure Maxwell theory is a Coulomb phase. Its Wilson loops do not show confinement; the gapless photon gives Coulomb interactions.

## Relations to other pages

The Higher-Form Symmetries page gives the general definition. Charged Extended Operators explains why line operators are the charged objects. Electric and Magnetic One-Form Symmetries gives the general gauge-theory context. Wilson-Loop Area Law contrasts the Maxwell Coulomb phase with confinement. Center Symmetry explains the discrete nonabelian analogue in pure Yang–Mills theory.

## Research status

The electric and magnetic one-form symmetries of pure Maxwell theory are standard and form one of the simplest examples in generalized global symmetry.

The subtleties are global rather than local: compactness, spin structure, charge lattice, boundary conditions, line-operator spectrum, monopole sectors, duality frames, and mixed anomaly conventions. These subtleties are exactly why the example is so useful.

## Exercises

### Exercise 1: Conservation of the electric current

Let

$$
J_{\rm e}=\frac{1}{e^2}F.
$$

Show that $d{*J_{\rm e}}=0$ follows from the Maxwell equation.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
{*J_{\rm e}}=\frac{1}{e^2}{*F}.
$$

Therefore

$$
d{*J_{\rm e}}=\frac{1}{e^2}d{*F}.
$$

The source-free Maxwell equation is $d{*F}=0$, so $d{*J_{\rm e}}=0$.

</details>

### Exercise 2: Conservation of the magnetic current

Let the magnetic current be defined by

$$
{*J_{\rm m}}=\frac{1}{2\pi}F.
$$

Show that $d{*J_{\rm m}}=0$ follows from the Bianchi identity.

<details><summary><strong>Solution</strong></summary>

Using the definition,

$$
d{*J_{\rm m}}=\frac{1}{2\pi}dF.
$$

The Bianchi identity is $dF=0$, so $d{*J_{\rm m}}=0$. Thus the magnetic one-form current is conserved when there are no monopoles.

</details>

### Exercise 3: Wilson-line charge

Assume a Wilson line of charge $q$ along $C$ sources the Maxwell equation as

$$
\frac{1}{e^2}d{*F}=q\,\delta_C.
$$

Show that an electric charge surface $\Sigma$ linking $C$ once measures charge $q$.

<details><summary><strong>Solution</strong></summary>

Let $M_\Sigma$ be a three-chain with boundary $\partial M_\Sigma=\Sigma$. Then

$$
Q_{\rm e}(\Sigma)=\frac{1}{e^2}\int_\Sigma {*F}
=\frac{1}{e^2}\int_{M_\Sigma}d{*F}
=q\int_{M_\Sigma}\delta_C.
$$

The last integral is the intersection number of $M_\Sigma$ with $C$, equal to the linking number $\ell(\Sigma,C)$. If $\Sigma$ links $C$ once, $Q_{\rm e}=q$.

</details>

### Exercise 4: Breaking by electric matter

Explain why adding a dynamical electron field breaks the electric one-form symmetry but not necessarily the magnetic one-form symmetry.

<details><summary><strong>Solution</strong></summary>

A dynamical electron worldline can be the endpoint of an external Wilson line. Therefore Wilson lines are no longer genuine closed charged operators of an exact electric one-form symmetry. In equations,

$$
\frac{1}{e^2}d{*F}={*j_{\rm el}},
$$

so the electric one-form current is not conserved.

If no magnetic monopoles are added, the Bianchi identity remains

$$
dF=0.
$$

Then the magnetic one-form symmetry can remain exact, though global issues and boundary conditions still matter.

</details>

## References

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the definition of higher-form symmetries and the Maxwell example.
- M. Srednicki, *Quantum Field Theory*, §§54–58 for Maxwell theory and QED foundations, and §82 for Wilson loops and confinement diagnostics.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8–9 and 25 for gauge invariance, QED, Wilson lines, and Yang–Mills context.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 10 for geometric and gauge-theory viewpoints in many-body language.
- J. Polchinski, *String Theory*, Vol. II, for electric-magnetic charge lattices and duality-related conventions in a broader context.

## Version history

- 2026-06-23: Polished draft. Added electric and magnetic one-form currents, flux charges, Wilson and ’t Hooft line actions, dynamical-matter breaking, Coulomb-phase interpretation, duality and anomaly previews, and exercises.
