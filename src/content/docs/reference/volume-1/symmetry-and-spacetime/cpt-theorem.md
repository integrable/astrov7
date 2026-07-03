---
title: "CPT Theorem"
description: "The statement, assumptions, proof idea, consequences, and caveats of the CPT theorem in local relativistic quantum field theory."
sidebar:
  label: "CPT Theorem"
  order: 9
---

## Summary

The **CPT theorem** says that any ordinary local relativistic quantum field theory has a combined symmetry that reverses charge, parity, and time together. Individual $C$, $P$, and $T$ symmetries may fail. Their product is different: under the standard assumptions of local QFT, there is an antiunitary operator $\Theta_{CPT}$ such that

$$
\Theta_{CPT}^{-1} H\Theta_{CPT}=H,
\qquad
\Theta_{CPT}^{-1}S\Theta_{CPT}=S^{-1},
$$

with the precise $S$-matrix form depending on whether one writes the transformation on in/out states or amplitudes.

For fields, the slogan is

$$
\text{field at }x
\quad\longmapsto\quad
\text{charge-conjugate field at }-x,
$$

with the appropriate Lorentz-index and spinor matrices. For a complex scalar field, for example,

$$
\Theta_{CPT}^{-1}\Phi(x)\Theta_{CPT}
=\eta_\Phi\Phi^\dagger(-x),
\qquad |\eta_\Phi|=1.
$$

The theorem is powerful because it is not an extra postulate about each model. It follows from the same architecture that made the previous page work: Lorentz covariance, locality, positive energy, Hilbert-space positivity, and a stable vacuum. Coleman gives a clean perturbative version: if one reverses all momenta in a Feynman graph so that incoming particles become outgoing antiparticles, the graph is unchanged after the correct spinor and fermion-sign factors are included (Coleman 2019, ch. 22). Weinberg gives the general local-field statement using causal fields and complex Lorentz transformations (Weinberg 1995, Vol. I, §§5.8–5.9). Srednicki presents the theorem first in the scalar context and then returns to spinors and discrete symmetries in the spin-one-half part of the book (Srednicki 2007, §§23 and 40).

<figure class="doc-figure" style="--figure-width: 50rem;">

![CPT theorem map](/figures/foundations/cpt-theorem-map.svg)

<figcaption>

The CPT theorem is a structural result. Locality, Lorentz covariance, positive spectrum, and Hilbert-space unitarity imply an antiunitary $CPT$ operation. Its physical consequences include particle–antiparticle equality of mass and lifetime. Apparent violations point to failed assumptions, not merely to a missing discrete sign.

</figcaption>
</figure>

## Prerequisites

You should know [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/), [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/), [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/), [Spinors from Lorentz Symmetry](/foundations/symmetry-and-spacetime/spinors-from-lorentz-symmetry/), [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/), [Dirac Field](/foundations/free-fields/dirac-field/), [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), and [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/).

:::note[Conventions]
We use the qft.org default mostly-minus metric. Write

$$
-x=(-x^0,-\mathbf x).
$$

The CPT operator is antiunitary:

$$
\Theta_{CPT}^{-1}i\Theta_{CPT}=-i.
$$

Intrinsic CPT phases such as $\eta_\Phi$ are convention-dependent for a single field. Relative phases become meaningful only when interactions compare several fields.
:::

:::note[Assumptions]
The theorem assumes an ordinary local relativistic QFT: Poincaré covariance, locality or graded locality of fields, positive energy, a positive-norm Hilbert space, a stable vacuum, Hermitian dynamics, and local fields transforming in finite-dimensional Lorentz representations. Gauge-fixed auxiliary fields, nonlocal theories, theories without a standard Hilbert-space interpretation, backgrounds that spoil global Poincaré invariance, and open systems can fall outside the theorem’s cleanest form.
:::

## What CPT means

The three letters refer to three operations:

| Operation | Basic action |
| --- | --- |
| $C$ | replaces particles by antiparticles and conjugates internal charges |
| $P$ | reverses spatial orientation, $\mathbf x\mapsto-\mathbf x$ |
| $T$ | reverses time, $t\mapsto -t$, and is antiunitary |

The product $CPT$ sends all spacetime coordinates to their negatives:

$$
x^\mu\mapsto -x^\mu.
$$

For a scalar field, this is simple. A real scalar can transform as

$$
\Theta_{CPT}^{-1}\phi(x)\Theta_{CPT}
=\eta_\phi\phi(-x),
\qquad \eta_\phi=\pm1.
$$

A complex scalar maps to its charge-conjugate field:

$$
\Theta_{CPT}^{-1}\Phi(x)\Theta_{CPT}
=\eta_\Phi\Phi^\dagger(-x).
$$

For a Lorentz vector, there is also the vector transformation under $x^\mu\mapsto -x^\mu$:

$$
\Theta_{CPT}^{-1}V^\mu(x)\Theta_{CPT}
= -\eta_V\,V^{\mu\dagger}(-x),
$$

with possible internal charge conjugation suppressed. A rank-$n$ tensor gets one sign from each Lorentz index under the full inversion.

For a Dirac field, one common schematic convention is

$$
\Theta_{CPT}^{-1}\psi(x)\Theta_{CPT}
=\eta_\psi\, i\gamma^5\psi^c(-x),
\qquad
\psi^c=C\bar\psi^{\,T},
$$

where $C$ is the charge-conjugation matrix. The exact phase and matrix placement depend on gamma-matrix and operator conventions. The invariant content is not the decoration by $i\gamma^5$; it is that a spinor field is mapped to the corresponding antiparticle spinor at the inverted spacetime point, with the correct spin-statistics signs.

## Why this is not just C then P then T

It is tempting to say: “If the theory is invariant under $C$, under $P$, and under $T$, then it is invariant under $CPT$.” That statement is true but weak. The theorem says something much stronger.

A local relativistic QFT can violate $C$, violate $P$, and violate $T$ separately. It can also violate $CP$. The theorem says that the combined operation $CPT$ is still a symmetry, provided the structural assumptions hold.

That is why the theorem matters. It is not merely the product of three optional model symmetries. It is a constraint on the whole framework.

A useful way to say it is:

$$
\boxed{\text{locality + Lorentz covariance + positivity} \Longrightarrow \text{CPT symmetry}.}
$$

The details behind that arrow are subtle, but the arrow is the right memory hook.

## The proof idea

There are several versions of the proof. A foundations page should not pretend to give the full rigorous theorem. But the proof has a memorable spine.

First, positive energy implies analyticity. Vacuum correlation functions are boundary values of analytic functions in suitable complexified spacetime domains. This is one place where the spectral condition matters: without positive energy, the analytic continuation has no reason to exist in the required region.

Second, Lorentz covariance can be extended to complex Lorentz transformations. The full spacetime inversion $x\mapsto -x$ is not continuously connected to the identity in the real proper orthochronous Lorentz group. But in the complexified Lorentz group, the necessary continuation can be reached.

Third, locality lets one reverse the order of spacelike-separated fields. The analytic continuation effectively rearranges field insertions. Locality supplies the rule that this rearrangement is harmless for bosons and produces exactly the graded signs required for fermions.

Fourth, Hilbert-space positivity lets the transformed vacuum correlation functions be represented by an antiunitary operator on states. This operator is $\Theta_{CPT}$.

In short:

$$
\text{positive spectrum}
\quad\Rightarrow\quad
\text{analyticity},
$$

$$
\text{Lorentz covariance}
\quad\Rightarrow\quad
\text{complex Lorentz continuation},
$$

$$
\text{locality}
\quad\Rightarrow\quad
\text{consistent field reordering},
$$

and together these imply an antiunitary CPT operator.

## Perturbative intuition

In perturbation theory, the theorem has a much more concrete face.

A local Lorentz-invariant interaction is built from fields contracted into a scalar density. The Feynman rules inherit this locality and Lorentz covariance. When all external momenta in a diagram are reversed, incoming particles become outgoing antiparticles and outgoing particles become incoming antiparticles. Bosonic lines transform in the obvious way. Fermionic lines require the spinor transformation and the signs from reversing fermion order.

Coleman’s spinor proof emphasizes this point. For scalar fields, the CPT-reversed graph has the same value after all external momenta are reversed. For spin-one-half fields, one must include the correct spinor map and one minus sign per external fermion line in the amplitude convention. Once those are included, the CPT-reversed process has the same amplitude in the appropriate sense (Coleman 2019, ch. 22).

This perturbative picture is not the full theorem. It is still valuable because it shows why CPT is not magic. Local Lorentz scalar vertices and the spin-statistics signs have very little freedom.

## Consequences for particles

The theorem implies strong constraints on the particle spectrum.

If $|A\rangle$ is a one-particle state with mass $m$, spin $s$, and additive charges $q_i$, then $\Theta_{CPT}|A\rangle$ is a state with

$$
m_{\bar A}=m_A,
\qquad
s_{\bar A}=s_A,
\qquad
q_i(\bar A)=-q_i(A).
$$

Thus particles and antiparticles have the same mass and spin and opposite additive charges. A neutral particle may be its own antiparticle, as for a real scalar or a Majorana fermion, but it is not required to be.

The theorem also implies equality of total lifetimes. If a particle and its antiparticle are both unstable, then the total decay widths agree:

$$
\Gamma_A=\Gamma_{\bar A}.
$$

Individual partial widths are related to CPT-conjugate final states, not necessarily to superficially similar final states. This distinction matters in theories with CP violation.

For scattering, a schematic amplitude relation is

$$
\mathcal M(A_1\cdots A_n\to B_1\cdots B_m)
\quad\leftrightarrow\quad
\mathcal M(\bar B_1\cdots \bar B_m\to \bar A_1\cdots \bar A_n)^*,
$$

with spin labels reversed appropriately and with conventional phase choices suppressed. The important idea is: reverse the process, replace every particle by the corresponding antiparticle, and complex conjugate because the operator is antiunitary.

## CPT, CP, and T violation

CPT symmetry does not imply CP symmetry. It also does not imply T symmetry. It only constrains their combination.

If CPT is exact and CP is violated, then T must be violated in the corresponding processes. Roughly,

$$
CPT=1
\quad\text{and}\quad
CP\ne1
\quad\Longrightarrow\quad
T\ne1,
$$

where the symbols are only mnemonic; actual statements are made about amplitudes and transition probabilities.

This is why CP violation in weak interactions is not in conflict with the CPT theorem. It is exactly the situation in which time-reversal violation must appear as well, assuming the usual local relativistic framework.

## Lagrangian test

For many practical theories, checking CPT is simple. Write every term in the Lagrangian as a local Hermitian Lorentz scalar with contracted spinor and tensor indices. If the regulator and quantization preserve the assumptions, the theory is CPT invariant.

For example, the scalar interaction

$$
\mathcal L_{\text{int}}
=-\frac{\lambda}{4!}\phi^4
$$

is CPT invariant because $\phi(x)\mapsto \eta_\phi\phi(-x)$ and $\eta_\phi^4=1$.

For a Yukawa coupling,

$$
\mathcal L_{\text{int}}=-g\phi\bar\psi\psi,
$$

CPT invariance follows from the fact that $\bar\psi\psi$ is a Lorentz scalar bilinear and the full term is Hermitian, assuming the field phases are chosen consistently. Separate $C$, $P$, or $T$ invariance may impose additional restrictions, but CPT does not require each factor separately.

Gauge theories work the same way after one treats gauge redundancy correctly. Gauge-fixed Lagrangians may contain ghosts and auxiliary fields with unusual transformation rules, but physical gauge-invariant observables still obey the theorem under the standard assumptions.

## Path-integral viewpoint

In the path integral, CPT is a change of variables plus complex conjugation. The complex conjugation is essential because CPT is antiunitary. Schematically,

$$
\int \mathcal D\Phi\,e^{iS[\Phi]}
\quad\longmapsto\quad
\int \mathcal D\Phi^{CPT}\,e^{-iS[\Phi]^{*}}.
$$

If the action is local, Hermitian, and Lorentz invariant, and if the measure and regulator respect the transformation, the transformed integral gives the CPT-related correlation function.

This phrasing also shows where problems can enter. If the measure is not invariant, a symmetry can fail quantum mechanically. For CPT in ordinary local Lorentzian QFT, the theorem says the full structure prevents such a failure. For other transformations, such as chiral symmetries, the measure can produce anomalies.

## What apparent CPT violation would mean

Because the theorem is structural, apparent CPT violation is a diagnostic. It means at least one assumption is not satisfied or has been misidentified.

Possible exits include:

| Possible exit | What changes |
| --- | --- |
| Lorentz violation | the complex Lorentz argument no longer applies |
| nonlocality | spacelike reordering can fail |
| nonunitarity or open dynamics | no antiunitary Hilbert-space symmetry need exist |
| lack of positive energy | analyticity can fail |
| no stable vacuum | the reference state for the theorem is absent |
| curved or time-dependent background | global Poincaré symmetry may not exist |
| gauge-fixed auxiliary sector | unphysical fields need not obey particle-level conclusions |

This is why CPT tests are so conceptually sharp. They are not merely tests of a discrete sign rule; they test the architecture of local relativistic quantum theory.

## Common pitfalls

### “CPT means C, P, and T are separately conserved”

No. A theory can violate $C$, $P$, $T$, and $CP$ while preserving $CPT$.

### “CPT maps a particle to the same particle”

Not generally. It maps a particle to the corresponding antiparticle. A particle maps to itself only if it is self-conjugate, as for a real scalar or Majorana fermion.

### “The theorem is obvious from the Lagrangian”

For many textbook Lagrangians, CPT invariance is easy to check. The theorem is deeper: it explains why every local Lorentz-invariant QFT satisfying the assumptions has such a symmetry, even beyond a term-by-term mnemonic.

### “Time reversal is unitary”

No. Time reversal, and hence CPT, is antiunitary. This is why amplitudes are complex-conjugated in CPT relations.

### “A background field can never affect CPT”

Backgrounds matter. A fixed external background may fail to transform with the dynamical fields, or may select a time orientation or spacetime direction. Then the theory under study may no longer satisfy the assumptions of the theorem as a closed Poincaré-invariant QFT.

## Relation to other topics

- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) introduces $C$, $P$, $T$, antiunitarity, and intrinsic phases.
- [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/) explains the graded locality and fermion signs used in CPT arguments.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) explains why relativistic fields naturally contain particle and antiparticle modes.
- [Dirac Field](/foundations/free-fields/dirac-field/) gives the spinor transformations and particle–antiparticle mode expansion.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) gives the scalar, pseudoscalar, vector, axial, and tensor bilinears used in Lagrangian checks.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) explains how continuous symmetries constrain correlators; CPT is a discrete structural symmetry rather than a Noether-current symmetry.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will state the locality assumption in its broader structural form.

## Exercises

### Exercise 1

Show why time reversal must be antiunitary if it is to preserve positive energy while reversing time translations.

<details>
<summary><strong>Solution</strong></summary>

Time evolution is generated by

$$
U(t)=e^{-iHt}.
$$

Time reversal should exchange evolution by $t$ with evolution by $-t$:

$$
\Theta^{-1}U(t)\Theta=U(-t)=e^{+iHt}.
$$

If $\Theta$ is antiunitary, then $\Theta^{-1}i\Theta=-i$. Assuming $\Theta^{-1}H\Theta=H$,

$$
\Theta^{-1}e^{-iHt}\Theta
=e^{+iHt},
$$

as desired. If $\Theta$ were unitary, the sign of $i$ would not change, and one would instead need $H\mapsto -H$, which would conflict with a positive-energy theory.

</details>

### Exercise 2

Let $\Phi$ be a complex scalar field with $\Theta_{CPT}^{-1}\Phi(x)\Theta_{CPT}=\eta\Phi^\dagger(-x)$. Show that the interaction $\lambda(\Phi^\dagger\Phi)^2$ is CPT invariant for real $\lambda$.

<details>
<summary><strong>Solution</strong></summary>

Under CPT,

$$
\Phi^\dagger(x)\Phi(x)
\mapsto
\Phi(-x)\Phi^\dagger(-x).
$$

For bosonic scalar fields this is the same local product as

$$
\Phi^\dagger(-x)\Phi(-x),
$$

up to the harmless intrinsic phase cancellation $\eta^*\eta=1$. Therefore

$$
(\Phi^\dagger\Phi)^2(x)
\mapsto
(\Phi^\dagger\Phi)^2(-x).
$$

The spacetime integral is invariant after the change of variables $x\mapsto -x$, and real $\lambda$ makes the term Hermitian.

</details>

### Exercise 3: Equal masses

Assume $\Theta_{CPT}^{-1}H\Theta_{CPT}=H$. Explain why a particle and its antiparticle must have the same mass.

<details>
<summary><strong>Solution</strong></summary>

Let $|A,\mathbf 0,\sigma\rangle$ be a one-particle rest state. Then

$$
H|A,\mathbf 0,\sigma\rangle=m_A|A,\mathbf 0,\sigma\rangle.
$$

Since $\Theta_{CPT}$ commutes with $H$ in the antiunitary sense,

$$
H\Theta_{CPT}|A,\mathbf 0,\sigma\rangle
=\Theta_{CPT}H|A,\mathbf 0,\sigma\rangle
=m_A\Theta_{CPT}|A,\mathbf 0,\sigma\rangle,
$$

where $m_A$ is real. The transformed state is the corresponding antiparticle rest state, possibly with a transformed spin label and a convention-dependent phase. Therefore

$$
m_{\bar A}=m_A.
$$

</details>

### Exercise 4: CP violation and CPT

Explain why CP violation is compatible with CPT invariance.

<details>
<summary><strong>Solution</strong></summary>

CP compares a process with the charge-conjugated and parity-reflected process. CPT compares it with the charge-conjugated, parity-reflected, time-reversed process. These are different comparisons.

If CPT is exact, then violation of CP is accompanied by the corresponding violation of T, so that the product CPT remains a symmetry. Thus CP violation is not evidence against CPT; it is evidence that CP is not one of the separately respected symmetries of the dynamics.

</details>

### Exercise 5: Reversing a process

In words, state the CPT-reversed version of the process $A+B\to C+D$.

<details>
<summary><strong>Solution</strong></summary>

CPT reverses the in/out roles and replaces every particle by its antiparticle, with spin labels transformed appropriately. Thus the CPT-reversed process is

$$
\bar C+\bar D\to\bar A+\bar B,
$$

up to the conventional ordering of external particles and spin labels. The amplitude relation may include complex conjugation depending on whether one writes it as a relation between matrix elements, transition probabilities, or invariant amplitudes.

</details>

### Exercise 6: Failed assumptions

List three assumptions whose failure could allow apparent CPT violation.

<details>
<summary><strong>Solution</strong></summary>

Possible failed assumptions include:

- Lorentz invariance;
- locality or graded locality;
- unitarity or positive Hilbert-space norm;
- positive energy or a stable vacuum;
- a standard flat-spacetime particle interpretation;
- invariance of the regulator, measure, and boundary conditions.

Any three of these are enough for the exercise. Apparent CPT violation should therefore be read as a diagnostic: the setup may not be an ordinary local Lorentz-invariant QFT satisfying the theorem’s hypotheses.

</details>

## Sources and further reading

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.8–5.9, for the general local-field proof and its connection with causal fields.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 11 and 22, for the perturbative scalar and spinor viewpoints.
- M. Srednicki, *Quantum Field Theory*, §§23 and 40, for discrete symmetries and spinor transformations.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the classic axiomatic treatment.
- R. Jost, *The General Theory of Quantized Fields*, for the analytic-continuation viewpoint behind the theorem.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§3.6 and 4.4, for discrete symmetries and spinor conventions in common particle-physics notation.

## Version history

- **2026-05-23:** Initial qft.org page on the CPT theorem, assumptions, antiunitarity, field transformations, proof ideas, consequences for particles and antiparticles, path-integral viewpoint, caveats, and exercises.
