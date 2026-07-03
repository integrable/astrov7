---
title: "CPT Theorem Perspective"
description: "Explains what the CPT theorem says, what assumptions it uses, how CPT constrains fields and scattering, and why it does not require C, P, or T to be separate symmetries."
sidebar:
  label: "CPT Theorem"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I §§2.2, 2.6, 5.5; Srednicki §§23, 40; Coleman, Lectures on QFT ch. 22; Schwartz ch. 11; standard Wightman/CPT theorem treatments."
topics:
  - CPT theorem
  - discrete spacetime symmetry
  - antiunitary symmetry
  - locality
  - Lorentz invariance
  - spin-statistics
  - particle-antiparticle relation
  - scattering amplitudes
canonicalTopics:
  - cpt-theorem
  - antiunitary-symmetry
  - locality
  - lorentz-invariance
  - particle-antiparticle-cpt
  - cpt-and-scattering
researchStatus:
  established:
    - "The CPT theorem is a structural theorem of local Lorentzian QFT: under standard assumptions, a combined antiunitary CPT symmetry exists even when C, P, and T are not separately symmetries."
    - "CPT invariance implies equality of particle and antiparticle masses and total lifetimes, and relates amplitudes to CPT-reversed amplitudes."
  active:
    - "Modern work refines the theorem's hypotheses in curved spacetime, non-Lagrangian QFT, lattice systems, nonrelativistic systems, defects, boundaries, nonlocal effective descriptions, and quantum-gravity-motivated scenarios."
---

## Summary

The CPT theorem says that a broad class of relativistic quantum field theories has a combined symmetry that reverses charge, space, and time together. More precisely, a local Lorentz-invariant QFT with a sensible Hilbert space, positive energy, spin-statistics, and local commutativity has an **antiunitary** operator, written here as $\Theta_{CPT}$, whose action on local fields is schematically

$$
\boxed{\text{field at }x}\quad\longmapsto\quad
\boxed{\text{conjugate field at }-x}.
$$

For a complex scalar field, this schematic statement can be made as simple as

$$
\Theta_{CPT}\phi(x)\Theta_{CPT}^{-1}
=\eta_\phi\phi^\dagger(-x),
\qquad |\eta_\phi|=1,
$$

where $\eta_\phi$ is a conventional phase. Spinor and tensor fields carry additional representation matrices, but the same message survives: CPT maps each local operator to the appropriate conjugate operator at the inverted point.

<figure class="doc-figure" style="--figure-width: 56rem;">

![CPT theorem map showing assumptions leading to an antiunitary CPT operator, which then implies conjugate fields at inverted spacetime points and particle-antiparticle constraints.](/figures/symmetry-anomalies-topology/cpt-theorem-map.svg)

<figcaption>

The CPT theorem is not a separate dynamical miracle added to QFT. It is a consequence of combining Lorentz covariance, locality, positive energy, the Hilbert-space structure, and the spin-statistics connection. The result is an antiunitary operator $\Theta_{CPT}$ that maps local fields at $x$ to conjugate local fields at $-x$ and constrains scattering and spectra.

</figcaption>
</figure>

The theorem is often misremembered as

$$
\text{CPT}=C\times P\times T.
$$

That slogan is only safe when $C$, $P$, and $T$ have already been defined as separate symmetries. The theorem itself is stronger and subtler: **CPT can exist even when $C$, $P$, and $T$ separately do not**. This is why a chiral gauge theory can violate parity and charge conjugation while still obeying CPT.

## Prerequisites

Read [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/), [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), and [Charge Conjugation](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/charge-conjugation/) first. You should also know [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/), and the contact-term viewpoint from [Ward Identities: Operator Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-operator-form/).

We use the volume conventions

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\bar\psi=\psi^\dagger\gamma^0,
\qquad
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

## Core idea

The conceptual punchline is this:

$$
\text{local relativistic QFT has no way to distinguish a process from its CPT mirror.}
$$

The CPT mirror does three things at once.

First, it sends spacetime points to inverted spacetime points,

$$
x^\mu\mapsto -x^\mu.
$$

Second, it replaces each charged object by its conjugate object: a particle becomes the corresponding antiparticle, a representation becomes the conjugate representation, and a charged field becomes its conjugate field.

Third, because time reversal is involved, the Hilbert-space operator is antiunitary:

$$
\Theta_{CPT} i\Theta_{CPT}^{-1}=-i.
$$

The antiunitarity is not optional. It is what lets the symmetry reverse time while preserving positive energy and transition probabilities.

The theorem should be read as a **structural consistency statement**, not as an empirical accident. In the same family as spin-statistics and the existence of antiparticles, CPT is one of the places where relativity, locality, and quantum mechanics lock together.

## Setup and conventions

This page writes the CPT operator as $\Theta_{CPT}$. It is antiunitary, so

$$
\Theta_{CPT}(c_1|\psi_1\rangle+c_2|\psi_2\rangle)
=c_1^*\Theta_{CPT}|\psi_1\rangle
+c_2^*\Theta_{CPT}|\psi_2\rangle.
$$

The spacetime inversion map is

$$
\iota:x\mapsto -x.
$$

For a multiplet of local fields $\Phi_a(x)$, the CPT action has the general form

$$
\Theta_{CPT}\Phi_a(x)\Theta_{CPT}^{-1}
=\sum_b M_a{}^b\Phi_b^\dagger(-x),
$$

where $M_a{}^b$ is fixed by spin, Lorentz representation, internal representation, and phase convention.

For scalar fields there is no spin matrix:

$$
\Theta_{CPT}\phi_a(x)\Theta_{CPT}^{-1}
=\eta_a\phi_a^\dagger(-x).
$$

For vector fields, the spacetime index transforms under the full inversion. With a conventional vector field $V^\mu$, one writes schematically

$$
\Theta_{CPT}V^\mu(x)\Theta_{CPT}^{-1}
=\eta_V V^\mu{}^\dagger(-x)
$$

or with an explicit Lorentz matrix depending on whether the field is treated as a tensor component under $x\mapsto -x$. The two notations differ by where one places the index transformation. What is physical is the transformation of invariant local terms and correlation functions, not the decorative placement of minus signs in a compressed table.

:::note[Convention-sensitive source note]
CPT formulas for spinor fields vary more than scalar formulas because authors differ in gamma-matrix signature, placement of inverses, whether $C$ denotes a matrix or the charge-conjugation operator, and whether transformed fields are written with transposes or daggers. The invariant statement is not the exact displayed spinor matrix; it is that a spinor field is mapped to the conjugate spinor representation at $-x$ with an antiunitary action on coefficients.
:::

## What the theorem says

A useful physicist's version is:

:::note[CPT theorem, working form]
In a Lorentz-invariant local quantum field theory on Minkowski spacetime with a positive-energy Hilbert space, a Lorentz-invariant vacuum, local commutativity, and the usual spin-statistics connection, there is an antiunitary operator $\Theta_{CPT}$ such that correlation functions are invariant when all local operators are replaced by their CPT transforms.
:::

For local operators $\mathcal O_i(x_i)$, this means schematically

$$
\langle 0|\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle
=
\langle 0|\Theta_{CPT}\mathcal O_1(x_1)\Theta_{CPT}^{-1}
\cdots
\Theta_{CPT}\mathcal O_n(x_n)\Theta_{CPT}^{-1}|0\rangle^*,
$$

with the complex conjugation coming from antiunitarity. For scalar fields this becomes a relation between correlators of fields at $x_i$ and conjugate fields at $-x_i$.

The theorem is sometimes presented in a Lagrangian form:

$$
\mathcal L(x)\mapsto\mathcal L(-x)
$$

for any Hermitian Lorentz-scalar local Lagrangian built from fields obeying the spin-statistics connection. This Lagrangian statement is a good check in standard perturbative QFT. The deeper theorem is not restricted to weak coupling or to a particular set of Feynman rules.

## The assumptions are doing work

CPT is powerful because its assumptions are powerful.

### Lorentz covariance

Relativity is essential. The spacetime inversion $x\mapsto -x$ is not connected to the identity inside the real proper orthochronous Lorentz group, but it is naturally reached by analytic continuation to the complexified Lorentz group. This is one of the mathematical reasons CPT is tied to Lorentz covariance rather than to ordinary internal symmetry alone.

In particle language, Lorentz covariance also fixes how spin labels, helicities, and particle-antiparticle states transform. CPT does not merely flip a label on a nonrelativistic Hilbert space; it acts compatibly with relativistic representation theory.

### Locality

Locality enters through the ability to reorder fields at spacelike separation. For bosonic local operators,

$$
[\mathcal O_1(x),\mathcal O_2(y)]=0
\qquad\text{for }(x-y)^2<0,
$$

and for fermionic operators the corresponding graded commutation relation is used. This is often called **local commutativity** or **microcausality**.

Without locality, the analytic continuation argument breaks. This is why genuine CPT violation, if found in a would-be relativistic theory, would usually point not to a small broken discrete symmetry in isolation but to a failure of at least one of locality, Lorentz invariance, unitarity, or ordinary QFT assumptions.

### Positive energy and the vacuum

The spectral condition says that energy-momentum lies in the future light cone. In the mostly-minus convention,

$$
p^2\ge 0,
\qquad
p^0\ge 0
$$

for massive and massless physical states. This condition chooses a stable vacuum and allows the analytic structure of correlation functions to be controlled.

CPT does **not** turn positive energy into negative energy. Because the CPT operator is antiunitary and includes both parity and time reversal, it commutes with the four-momentum in the usual scattering setting:

$$
\Theta_{CPT}P^\mu\Theta_{CPT}^{-1}=P^\mu.
$$

A particle and its CPT conjugate therefore have the same mass and energy spectrum.

### Spin-statistics

The spin-statistics connection is part of the consistency package. Integer-spin local fields commute at spacelike separation, and half-integer-spin local fields anticommute. If one deliberately gives a spinor bosonic statistics or a scalar fermionic statistics, the assumptions behind the theorem are no longer the assumptions of ordinary local QFT.

This is why CPT, spin-statistics, and locality are often learned together: they are different shadows of the same relativistic quantum structure.

## CPT is not the same as separate C, P, and T

A theory may have CPT while violating $C$, $P$, and $T$ individually.

A left-handed Weyl fermion is the cleanest conceptual example. Parity maps a left-handed Weyl representation to a right-handed one. If the theory contains only the left-handed field in a chiral representation, parity is not a symmetry. Charge conjugation also changes the gauge representation, so it need not be a symmetry. Nevertheless, a consistent local Lorentz-invariant chiral QFT can have CPT.

The Standard Model illustrates the same lesson physically. Weak interactions violate parity. CP is also violated. Under the usual local Lorentz-invariant QFT assumptions, CPT remains a symmetry, so CP violation implies a corresponding T violation in appropriate transition amplitudes.

The slogan to keep is

$$
\text{CPT is guaranteed under QFT assumptions; C, P, and T are optional extra symmetries.}
$$

## Consequences for particles and antiparticles

CPT relates one-particle states to antiparticle states with the same mass and spin. Schematically,

$$
\Theta_{CPT}|p,s,q\rangle
=\eta |p,\widetilde s,-q\rangle_{\text{anti}},
$$

where the precise spin label $\widetilde s$ depends on whether one uses spin along a fixed axis, helicity, or another basis. The important invariant consequences are:

| Quantity | CPT implication |
|---|---|
| Mass | particle and antiparticle masses are equal |
| Total lifetime | particle and antiparticle total lifetimes are equal |
| Spin | spin representation is the same |
| Additive internal charges | charges are conjugated |
| Magnetic/electric moments | related with signs determined by the operator being measured |

For an unstable particle $A$ and its CPT conjugate $\bar A$, CPT gives equality of total widths,

$$
\Gamma_A=\Gamma_{\bar A}.
$$

It does **not** require every partial decay rate to match its naively conjugated partial rate if CP violation and final-state interactions mix channels. The exact statement is a relation among the full transition matrix and the complete set of CPT-conjugate states.

## Consequences for scattering

Let $S$ be the scattering operator. In a CPT-invariant scattering theory, matrix elements are related to matrix elements with all external states replaced by their CPT conjugates and with the in/out roles treated consistently. The exact amplitude formula depends on whether one writes states as in-states and out-states, where one puts antiunitary inverses, and how external-state phases are chosen.

The convention-independent probability statement is the cleanest one:

$$
P(i\to f)=P(\Theta_{CPT}f\to\Theta_{CPT}i),
$$

with the obvious replacement of phase space and spin labels by their CPT-conjugate labels. The reversal of initial and final roles reflects the time-reversal part of CPT.

For amplitudes, one often writes a schematic relation of the form

$$
\mathcal M(i\to f)
\sim
\mathcal M(\Theta_{CPT}f\to\Theta_{CPT}i),
$$

where the symbol $\sim$ hides phase conventions and possible complex conjugations associated with the antiunitary operator. Rates and total probabilities are more robust than named amplitude phases.

A useful diagnostic is:

$$
\text{CPT pairs a process with the antiparticle reverse process.}
$$

Not with the process obtained by only changing charges. That latter operation is closer to charge conjugation or CP, and may fail.

## Lagrangian checks

In ordinary Lagrangian QFT, CPT invariance is often checked term by term.

A Hermitian scalar mass term obeys

$$
m^2\phi^\dagger\phi(x)
\mapsto
m^2\phi^\dagger\phi(-x).
$$

A Yukawa term plus its Hermitian conjugate has the schematic form

$$
y\phi\psi\psi+y^*\phi^\dagger\psi^\dagger\psi^\dagger.
$$

Antiunitarity complex-conjugates $y$, while the field conjugation swaps the term with its Hermitian conjugate. The pair is CPT invariant.

Gauge interactions behave similarly. A local Hermitian Lorentz scalar made from covariant derivatives, field strengths, and matter fields transforms into the same local scalar at $-x$. The action is unchanged because

$$
\int d^4x\,\mathcal L(-x)=\int d^4x\,\mathcal L(x).
$$

This is why complex phases in a Lagrangian do not automatically violate CPT. They may violate CP. CPT survives because antiunitarity conjugates coefficients and the transformed field monomial is the Hermitian-conjugate monomial.

:::note[Convention-sensitive source note]
A common source of confusion is the role of the coefficient $i$ in terms such as fermion kinetic terms or topological terms. Under CPT, $i$ is complex-conjugated because the operator is antiunitary. When checking a Lagrangian, transform both the fields and the explicit numerical coefficients. Checking only the field signs gives wrong answers.
:::

## CPT and topological terms

Consider the four-dimensional Yang–Mills theta term

$$
S_\theta=\frac{\theta}{32\pi^2}\int d^4x\,
F^a_{\mu\nu}\widetilde F^{a\mu\nu}.
$$

The density $F\widetilde F$ is odd under parity and odd under time reversal. It is even under the combined $PT$, and charge conjugation does not change it in ordinary Yang–Mills theory. Therefore the theta term is CPT even.

This is an instructive example because it separates several ideas:

$$
\theta F\widetilde F
\quad\text{violates }P\text{ and }T\text{ separately, but not CPT.}
$$

On the other hand, time reversal by itself sends $\theta\mapsto -\theta$. Because $\theta$ is periodic, special values such as $\theta=0$ and $\theta=\pi$ can have extra time-reversal structure. Those subtleties belong to the anomaly and topological-term chapters.

## Proof idea without proving the theorem

The full proof belongs to axiomatic and rigorous QFT, but the physics logic is worth knowing.

The Wightman functions

$$
W_n(x_1,\ldots,x_n)=\langle 0|\Phi_1(x_1)\cdots\Phi_n(x_n)|0\rangle
$$

are boundary values of analytic functions in complexified spacetime variables. Positive energy gives the analyticity domain. Lorentz covariance extends the allowed transformations to the complexified Lorentz group. Local commutativity lets one exchange operators when separations are spacelike. These ingredients together imply a relation between

$$
W_n(x_1,\ldots,x_n)
$$

and the reversed, conjugated correlator with points $-x_i$.

The antiunitary operator $\Theta_{CPT}$ is then reconstructed from its action on states created by local fields acting on the vacuum.

This proof strategy is a beautiful example of the deeper theme: in QFT, symmetries are often encoded not only by Lagrangian transformations but by analytic and algebraic properties of correlation functions.

## What would CPT violation mean?

Within ordinary local Lorentz-invariant QFT, CPT violation is not just “one more small symmetry breaking.” It would mean that at least one assumption of the theorem fails.

Possible failure points include:

| Possible failure | Meaning |
|---|---|
| Lorentz invariance fails | A preferred vector, frame, lattice, foliation, or background invalidates the theorem's relativistic hypothesis. |
| Locality fails | The theory has genuinely nonlocal interactions or nonlocal effective dynamics outside the theorem's domain. |
| Unitarity fails | Time evolution is not described by a standard Hilbert-space unitary scattering theory. |
| Positive energy fails | The spectral condition or stable-vacuum assumption is absent. |
| Ordinary field/operator assumptions fail | The system is not a relativistic local QFT in the relevant sense. |

This does not mean every approximate model must visibly exhibit CPT. Nonrelativistic effective Hamiltonians, open systems, thermal density matrices, matter in external magnetic fields, and lattice regulators can obscure or explicitly break pieces of the theorem's assumptions. The theorem applies to the underlying relativistic local QFT, not to every truncated description.

## Common pitfalls

**Mistake 1: Treating CPT as an empirical product of three separate symmetries.**

CPT is guaranteed under broad QFT assumptions. Separate $C$, $P$, and $T$ symmetries are additional properties a theory may or may not have.

**Mistake 2: Forgetting antiunitarity.**

CPT contains time reversal, so coefficients are complex-conjugated. This matters for Yukawa phases, CKM phases, fermion bilinears, and path-integral phases.

**Mistake 3: Thinking CPT sends energy to negative energy.**

It does not. CPT maps particles to antiparticles with the same positive energy.

**Mistake 4: Using a spinor matrix formula without translating conventions.**

Spinor CPT formulas are convention-heavy. Check the metric, gamma matrices, $C$ matrix, phase convention, and whether the author writes $\Theta\psi\Theta^{-1}$ or $\Theta^{-1}\psi\Theta$.

**Mistake 5: Confusing CP violation with CPT violation.**

CP violation is observed in weak interactions. Under CPT, it implies corresponding T violation in the appropriate sense; it does not imply CPT violation.

## Relations to other pages

[Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) explains why antiunitarity is forced by time evolution. [Charge Conjugation](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/charge-conjugation/) explains representation conjugation. [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) explains orientation reversal and pseudoscalars.

The anomaly chapters will revisit CPT-adjacent issues for discrete symmetries, fermions, Pin structures, and topological terms. The rigorous QFT volume gives the theorem-level Wightman and Osterwalder–Schrader versions. The Standard Model volume uses CPT when discussing particle-antiparticle masses, CP violation, and anomaly cancellation.

## Research status

The CPT theorem is established in standard local relativistic QFT. Its textbook consequences for spectra, scattering, and particle-antiparticle relations are settled.

Active and subtle directions include CPT in curved spacetime, algebraic QFT, non-Lorentz-invariant systems, nonlocal effective theories, lattice regularizations, open quantum systems, defects and boundaries, fermionic phases of matter, and quantum-gravity-motivated tests of the theorem's assumptions. In these settings the right question is often not “does CPT fail?” but “which hypothesis of the ordinary theorem is being changed?”

## Exercises

### Exercise 1: CPT and a complex scalar

Let $\phi$ be a charged scalar with

$$
\Theta_{CPT}\phi(x)\Theta_{CPT}^{-1}=\eta\phi^\dagger(-x),
\qquad |\eta|=1.
$$

Show that the kinetic and mass terms

$$
\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi
$$

are CPT invariant after integration over spacetime.

<details><summary><strong>Solution</strong></summary>

Under $x\mapsto -x$, each derivative picks up a minus sign:

$$
\partial_\mu\phi(x)\mapsto -\partial_\mu\phi^\dagger(-x)
$$

up to the phase $\eta$. The two derivative signs multiply to $+1$, and the phases cancel between $\phi$ and $\phi^\dagger$. The mass term is simply mapped to itself at $-x$. Finally,

$$
\int d^4x\,\mathcal L(-x)=\int d^4x\,\mathcal L(x),
$$

so the action is invariant.

</details>

### Exercise 2: Why a complex Yukawa coupling need not violate CPT

Consider a schematic interaction

$$
\mathcal L_{\text{int}}=y\phi\psi\psi+y^*\phi^\dagger\psi^\dagger\psi^\dagger.
$$

Explain why a complex $y$ can violate CP but need not violate CPT.

<details><summary><strong>Solution</strong></summary>

CPT is antiunitary, so it complex-conjugates numerical coefficients. Thus $y$ is sent to $y^*$. At the same time, the fields are mapped to conjugate fields at $-x$, so the monomial $\phi\psi\psi$ is mapped to the conjugate monomial. The first term is therefore exchanged with the second term. Since the Hermitian Lagrangian contains both terms, the pair is invariant.

CP is unitary, so it does not automatically complex-conjugate the coefficient. A complex phase can therefore be a genuine CP-violating phase even though CPT is preserved.

</details>

### Exercise 3: CPT and total widths

Assume CPT invariance and let $A$ be an unstable particle. Explain why CPT implies equality of the total decay width of $A$ and its antiparticle $\bar A$, but does not require every named partial width to be equal channel by channel in a CP-violating theory.

<details><summary><strong>Solution</strong></summary>

The total width is obtained by summing over a complete set of final states. CPT maps the complete set of final states for $A$ to the complete set of CPT-conjugate final states for $\bar A$, and transition probabilities are preserved after the appropriate reversal and complex conjugation of amplitudes. Therefore the total sums agree.

Individual partial rates can involve channels that mix under strong final-state interactions or under the chosen experimental classification of states. CP violation can redistribute rates among conjugate-looking channels while preserving the equality of the complete CPT-related total widths.

</details>

## References

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the sections on Wigner's theorem, inversions, and discrete transformations of fields.
- Mark Srednicki, *Quantum Field Theory*, sections on discrete symmetries and spinor transformations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapter on CPT and Fermi fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter on spinor solutions and CPT.
- R. Jost, classic axiomatic treatments of the CPT theorem.

## Version history

- 2026-06-17: First polished draft. Added theorem statement, assumptions, Lagrangian checks, scattering consequences, CPT-violation diagnostics, and convention-sensitive notes.
