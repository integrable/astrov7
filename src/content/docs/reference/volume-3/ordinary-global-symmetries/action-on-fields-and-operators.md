---
title: "Action on Fields and Operators"
description: "Explains how ordinary global symmetries act on elementary fields, composite operators, renormalized operator multiplets, sources, order parameters, and extended probes."
sidebar:
  label: "Action on Fields and Operators"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman, Srednicki, Weinberg, Zee, Schwartz; standard composite-operator renormalization and operator-algebra language."
topics:
  - field transformations
  - local operators
  - composite operators
  - renormalized operators
  - sources
  - operator product expansion
canonicalTopics:
  - symmetry-action-on-fields
  - symmetry-action-on-operators
  - composite-operator-mixing
  - operator-covariance
researchStatus:
  established:
    - "The action of ordinary global symmetries on fields, states, and local operators is standard QFT material."
    - "Composite-operator mixing constrained by symmetry is standard in perturbative, conformal, and effective field theory."
  active:
    - "In strongly coupled theories, dualities, gauge theories with subtle line operators, and non-invertible extensions, identifying the intrinsic operator action can be nontrivial."
---

## Summary

A symmetry can act on many things: elementary fields, local composite operators, renormalized operator multiplets, states, sources, defects, and boundary conditions. These actions are related, but they are not interchangeable.

For an internal unitary symmetry, the reliable operator statement is

$$
U(g)^\dagger\mathcal O_i(x)U(g)=R(g)_i{}^j\mathcal O_j(x).
$$

A Lagrangian presentation may begin with elementary fields,

$$
\Phi^I(x)\mapsto D(g)^I{}_J\Phi^J(x).
$$

That field transformation is useful because it lets us build the action, derive currents, and compute. But the intrinsic QFT data are closer to the action on genuine operators and states. Composite operators transform in tensor products of field representations, and renormalized composite operators can mix with other operators carrying the same quantum numbers.

The practical lesson is:

$$
\text{field transformation} \longrightarrow \text{candidate operator action},
\qquad
\text{operator action} \longrightarrow \text{physical constraints}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing how field transformations feed into renormalized operators, correlators, OPEs, source couplings, and Hilbert-space actions.](/figures/symmetry-anomalies-topology/symmetry-action-ladder.svg)

<figcaption>

A field-transformation rule is only one rung. A genuine symmetry must act consistently on renormalized local operators, source couplings, correlators, OPEs, Hilbert-space states, and the quantum measure.

</figcaption>
</figure>


## Prerequisites

You should know [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/). We use the same convention:

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+i\alpha^a[Q_a,\mathcal O]+O(\alpha^2),
$$

so

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

Noether currents, Ward identities, background fields, gauge redundancy, and anomalies are only previewed here.

## Core idea

A field is a coordinate used to present a theory. An operator is something the theory can insert, measure, couple to a source, or use to organize states. In the simplest examples an elementary field is itself a good local operator. In many important QFTs the distinction is essential.

There are three reasons.

First, **fields are presentation-dependent**. Bosonization, duality, Hubbard–Stratonovich transformations, nonlinear sigma-model coordinates, and gauge choices can all change the fields without changing the theory.

Second, **not every field is a physical observable**. Gauge-charged fields are useful variables but not gauge-invariant local observables.

Third, **composite operators require renormalization**. A formal product such as $\phi^2(x)$ is not automatically a well-defined quantum operator. After regularization and subtraction, it may mix with every other operator allowed by the same symmetries.

So the better question is:

:::note[Working question]
How does the symmetry act on the genuine operator algebra of the quantum theory, and how is that action represented in a particular choice of fields?
:::

## Setup and conventions

For an internal symmetry, spacetime points are held fixed. A field multiplet transforms as

$$
\Phi^I(x)\mapsto D(g)^I{}_J\Phi^J(x),
$$

where $I,J$ may include flavor, spinor, color-like presentation labels, or other indices. This page focuses on internal labels and suppresses Lorentz transformations unless needed.

For an operator multiplet,

$$
\mathcal O_i(x)\mapsto R(g)_i{}^j\mathcal O_j(x).
$$

For a continuous symmetry,

$$
[Q_a,\Phi^I]=(T_a^{(\Phi)})^I{}_J\Phi^J,
\qquad
[Q_a,\mathcal O_i]=(T_a^{(R)})_i{}^j\mathcal O_j.
$$

Products of bosonic operators transform by ordinary tensor products. Products involving fermionic operators carry signs when reordered, but the symmetry action itself is an automorphism of the graded operator algebra.

:::note[Convention-sensitive formula]
In canonical treatments, the charge action is derived from equal-time commutators. In path-integral treatments, it is derived from a change of variables and then expressed as a Ward identity. The signs here match the volume convention, not every textbook convention.
:::

## Elementary fields as representation coordinates

In a Lagrangian QFT, one often begins with fields chosen to transform linearly.

For a complex scalar with $U(1)$ symmetry,

$$
\phi\mapsto e^{i\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{-i\alpha}\phi^\dagger.
$$

For a Dirac field with vector $U(1)$ symmetry,

$$
\psi\mapsto e^{i\alpha}\psi,
\qquad
\bar\psi\mapsto \bar\psi e^{-i\alpha}.
$$

For an $SU(N)$ flavor multiplet,

$$
\psi^i\mapsto V^i{}_j\psi^j,
\qquad V\in SU(N).
$$

For an internal symmetry, derivatives carry the same internal representation as the field:

$$
\partial_\mu\phi\mapsto e^{i\alpha}\partial_\mu\phi.
$$

The derivative changes spacetime quantum numbers, not internal charge.

A linear field transformation is convenient but not guaranteed. Shift symmetries, Goldstone fields, sigma-model coordinates, and dual variables can all transform nonlinearly.

## Composite operators inherit tensor products

Once elementary fields transform, products of fields transform in tensor products.

For a $U(1)$ complex scalar,

$$
q\bigl(\phi^m(\phi^\dagger)^n\bigr)=m-n.
$$

Thus $\phi^\dagger\phi$ is neutral, while $\phi^2$ has charge $+2$.

For an $SU(N)$ fundamental field $\psi^i$, the bilinear

$$
\bar\psi_i\psi^j
$$

transforms in

$$
\overline{\mathbf N}\otimes\mathbf N=\mathbf 1\oplus\operatorname{Adj}.
$$

The trace $\bar\psi_i\psi^i$ is a singlet. The traceless part transforms in the adjoint.

These examples are not merely notation. Once the field representation is known, every polynomial operator inherits a representation by tensor products and contractions with invariant tensors.

## Composite local operators need renormalization

Classically, one can multiply fields at the same point and call the result an operator. Quantum mechanically, this is usually singular. A local composite operator must be defined by a renormalization prescription.

In a scalar theory, the naive product $\phi^2(x)$ is replaced by a renormalized operator such as

$$
[\phi^2](x),
$$

or by normal ordering in a free theory:

$$
:\!\phi^2\!:(x).
$$

The notation is less important than the warning: the operator definition includes subtractions and can depend on scale.

Symmetry constrains the allowed subtractions. If the regulator and renormalization scheme preserve $G$, then a renormalized operator in representation $R$ can mix only with operators in the same representation and with the same other quantum numbers:

$$
[\mathcal O_i]_\mathrm{bare}=Z_i{}^j[\mathcal O_j]_\mathrm{ren}.
$$

The matrix $Z_i{}^j$ is block diagonal in irreducible symmetry sectors.

:::caution[Classical monomials are not automatically quantum operators]
The expression $\phi^2(x)$ is a classical-looking symbol. The quantum operator $[\phi^2](x)$ is a renormalized object. Symmetry labels survive renormalization only if the regularization and counterterms preserve the symmetry, or if an anomaly is explicitly accounted for.
:::

## Good operator bases respect symmetry

A good operator basis is adapted to irreducible representations.

For $O(N)$ scalars, the bilinear operators split into

$$
\phi_i\phi_j
=\frac{1}{N}\delta_{ij}\phi_k\phi_k
+\left(\phi_i\phi_j-\frac{1}{N}\delta_{ij}\phi_k\phi_k\right).
$$

The first term is a singlet. The second is traceless symmetric. These pieces cannot mix if $O(N)$ is preserved.

If derivatives are included, more representations appear. For example,

$$
J_{ij}^\mu=\phi_i\partial^\mu\phi_j-\phi_j\partial^\mu\phi_i
$$

is antisymmetric in $i,j$ and is the natural current multiplet for $O(N)$ rotations in a simple scalar theory.

In a conformal field theory, local operators are further organized into conformal multiplets and internal-symmetry representations. In a generic QFT, scaling operators may be less clean, but symmetry labels still block-diagonalize the problem.

## Nonlinear actions

Not all symmetries act linearly on the chosen fields.

The simplest example is a shift symmetry:

$$
\phi(x)\mapsto\phi(x)+c.
$$

The field $\phi$ does not transform by multiplication with a matrix. Nevertheless,

$$
\partial_\mu\phi(x)\mapsto\partial_\mu\phi(x),
$$

and an action such as

$$
S=\int d^dx\,\frac12\partial_\mu\phi\partial^\mu\phi
$$

has the symmetry.

Goldstone bosons provide a more important class. If $G$ is spontaneously broken to $H$, the low-energy fields often parameterize the coset $G/H$. The full group $G$ acts nonlinearly on those coordinates. The elementary Goldstone coordinates are not linear multiplets of $G$, but physical operators and amplitudes still obey the symmetry constraints.

Nonlinear realization is not a loophole. It says that the chosen coordinates on field space are not themselves a linear representation.

## Sources transform in dual representations

Suppose sources $J^i(x)$ couple to operators $\mathcal O_i(x)$:

$$
S\longrightarrow S+\int d^dx\,J^i(x)\mathcal O_i(x).
$$

If

$$
\mathcal O_i\mapsto R(g)_i{}^j\mathcal O_j,
$$

then the source must transform in the dual representation:

$$
J^i\mapsto J^j(R(g)^{-1})_j{}^i.
$$

This keeps $J^i\mathcal O_i$ invariant. The generating functional with sources obeys a symmetry relation of the form

$$
Z[J]=Z[J^g]
$$

when the vacuum, measure, regulator, and counterterms preserve the symmetry.

This source viewpoint is the doorway to background fields. A background gauge field is the source for a symmetry current, but with the extra structure needed to make spacetime-dependent symmetry transformations meaningful.

:::note[Source note]
The source-transformation convention depends on whether one writes sources with upper or lower representation indices and whether the source term is $+\int J\mathcal O$ or $-\int J\mathcal O$. The invariant statement is that $J^i\mathcal O_i$ must be a singlet.
:::

## Correlators and OPE covariance

Let $\mathcal O_i$ and $\mathcal P_a$ transform in representations $R$ and $S$. Their operator product has the schematic form

$$
\mathcal O_i(x)\mathcal P_a(0)
\sim
\sum_k C_{ia}{}^k(x)\mathcal Q_k(0).
$$

Symmetry requires the OPE to be covariant. The tensor $C_{ia}{}^k$ is an intertwiner from $R\otimes S$ to the representation carried by $\mathcal Q_k$. In plainer language, the OPE can contain only operators allowed by the tensor-product decomposition.

For an abelian $U(1)$ symmetry,

$$
\mathcal O_{q_1}(x)\mathcal P_{q_2}(0)
$$

can contain only operators of charge

$$
q_1+q_2.
$$

For a nonabelian symmetry, one decomposes $R\otimes S$ into irreducibles. Operators in irreducibles absent from the product cannot appear in the OPE.

This is why symmetry constraints survive far beyond perturbation theory. Even if the numerical OPE coefficients are strongly coupled and hard to compute, many are exactly zero because representation theory forbids them.

## Fields are not always physical operators

In a scalar theory with global $O(N)$ symmetry, the elementary field $\phi_i(x)$ can be a genuine local operator. In a gauge theory, the situation changes. A gauge-charged elementary field is not a gauge-invariant local observable.

For example, a quark field $q^i_a(x)$ may carry a color index $a$ and a flavor index $i$. The color index is gauge redundancy, while the flavor index may be a global symmetry index. Physical local operators must be color singlets, such as

$$
\bar q_i^a q^j_a,
$$

or baryon-like operators formed with invariant color tensors. These physical operators then transform under the global flavor symmetry.

This is one of the cleanest reasons to separate field transformations from operator transformations. Gauge-variant fields are useful computational variables. Gauge-invariant local operators are physical insertions.

The same caution appears in duality. A field that is elementary in one description may correspond to a composite, disorder operator, or defect endpoint in another. The intrinsic symmetry action is the one on the full operator content.

## Symmetry action and Ward identities

For a continuous internal symmetry with current $j_a^\mu$, the integrated charge acts on operators as

$$
[Q_a,\mathcal O_i]=(T_a)_i{}^j\mathcal O_j.
$$

The local form of this statement is the Ward identity. In the conventions of this volume, for $\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)$,

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle,
$$

when there is no explicit breaking or anomaly.

Thus the current knows the operator transformation. Conversely, the contact terms in the Ward identity are how the current insertion announces that it has crossed a charged operator.

The next chapter derives this carefully. Here the point is only that Ward identities are local expressions of the symmetry action on operators.

## Spontaneous breaking changes the vacuum, not the action law

If a symmetry is spontaneously broken, the symmetry still acts on operators and states. What changes is that the chosen vacuum is not invariant.

An order parameter $\mathcal O_i$ in a nontrivial representation may have

$$
\langle\Omega|\mathcal O_i|\Omega\rangle\ne0.
$$

Then applying $U(g)$ produces another vacuum:

$$
|\Omega_g\rangle=U(g)|\Omega\rangle.
$$

The operator transformation law has not failed. The invariant-vacuum selection rule has failed because the vacuum is no longer invariant.

Spontaneous symmetry breaking is not the absence of a symmetry in the theory. It is the absence of that symmetry in a particular state or phase.

## Extended operators and disorder operators

Ordinary global symmetries act on local operators, but QFT also contains extended probes: lines, surfaces, domain walls, twist defects, disorder operators, and boundary conditions. These objects can transform under ordinary symmetries too.

A simple example is an Ising-like $\mathbb Z_2$ symmetry. The local spin operator is odd. A disorder operator can be defined by a branch cut or defect line ending at the insertion. The symmetry action is physical, but it is not captured merely by transforming a smooth elementary field at a point.

Later chapters on defects, higher-form symmetries, and non-invertible symmetries broaden this idea. The durable question remains:

$$
\text{what objects exist, and how does symmetry act on them?}
$$

## Common pitfalls

**Treating elementary fields as physical observables.** This fails in gauge theory and can mislead under duality.

**Assigning charges to classical composites without renormalization.** Quantum composite operators require counterterms or subtractions, and operators with identical symmetry quantum numbers can mix.

**Forgetting the dual transformation of sources.** If $\mathcal O_i$ transforms in $R$, the source coupled to it transforms in the dual representation so that $J^i\mathcal O_i$ is invariant.

**Assuming all symmetries act linearly on chosen fields.** Shift symmetries, Goldstone fields, sigma models, dual variables, and emergent infrared variables often transform nonlinearly.

**Confusing symmetry breaking with failure of the action law.** In spontaneous breaking, the symmetry still acts. The vacuum is not invariant.

## Relations to other pages

[Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/) supplies the representation language used throughout this page.

[What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) explains why the operator-first definition is more durable than a Lagrangian-only definition. [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/) explains when the action can be differentiated to produce charges and Noether currents.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter turns operator transformations into current insertions and contact terms. The [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) chapter promotes sources to background fields. The [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/) chapter explains why gauge transformations are not physical global symmetry actions.

## Research status

For ordinary global symmetries, the action on fields and local operators is established textbook material. The modern frontier is not the basic formula $U^\dagger\mathcal O U$; it is identifying the correct objects on which the symmetry acts.

In contemporary QFT, symmetries may act most naturally on extended operators rather than elementary fields. They may be higher-form, higher-group, non-invertible, categorical, anomalous, emergent, or visible only after coupling to background fields. Even for ordinary symmetries, global form and defect data can change the correct answer.

The safe habit remains the same: start from whatever field variables are convenient, but translate the final statement into an action on operators, states, correlators, and allowed backgrounds.

## Exercises

### Exercise 1: Charges of composite operators

Let $\phi$ have $U(1)$ charge $+1$ and $\phi^\dagger$ have charge $-1$. Find the charges of

$$
\phi^3,
\qquad
\phi^\dagger\phi,
\qquad
(\phi^\dagger)^2\partial_\mu\phi,
\qquad
\partial_\mu(\phi^\dagger\phi).
$$

<details><summary><strong>Solution</strong></summary>

Charges add under products, and derivatives carry no internal charge. Therefore

$$
q(\phi^3)=3,
$$

$$
q(\phi^\dagger\phi)=-1+1=0,
$$

$$
q((\phi^\dagger)^2\partial_\mu\phi)=-2+1=-1,
$$

and

$$
q(\partial_\mu(\phi^\dagger\phi))=0.
$$

</details>

### Exercise 2: Decomposing an O(N) bilinear

Let $\phi_i$ transform as a vector of $O(N)$. Show that $\phi_i\phi_j$ decomposes into a singlet and a traceless symmetric tensor.

<details><summary><strong>Solution</strong></summary>

The bilinear is symmetric in $i,j$ for bosonic fields, before renormalization subtleties are addressed. Split it as

$$
\phi_i\phi_j
=\frac{1}{N}\delta_{ij}\phi_k\phi_k
+\left(\phi_i\phi_j-\frac{1}{N}\delta_{ij}\phi_k\phi_k\right).
$$

The first term is the singlet. The second term is symmetric and traceless because

$$
\delta^{ij}\left(\phi_i\phi_j-\frac{1}{N}\delta_{ij}\phi_k\phi_k\right)=0.
$$

</details>

### Exercise 3: Source transformation

Let $\mathcal O_i\mapsto R_i{}^j\mathcal O_j$. Find the transformation of $J^i$ that makes $J^i\mathcal O_i$ invariant.

<details><summary><strong>Solution</strong></summary>

We require

$$
J^{\prime i}\mathcal O'_i=J^i\mathcal O_i.
$$

Using $\mathcal O'_i=R_i{}^j\mathcal O_j$, this becomes

$$
J^{\prime i}R_i{}^j\mathcal O_j=J^j\mathcal O_j.
$$

Thus

$$
J^{\prime i}=J^j(R^{-1})_j{}^i.
$$

The source transforms in the dual representation.

</details>

### Exercise 4: Shift symmetry and invariant operators

Suppose $\phi\mapsto\phi+c$ with constant $c$. Which of the following are invariant?

$$
\phi,
\qquad
\partial_\mu\phi,
\qquad
(\partial_\mu\phi)(\partial^\mu\phi),
\qquad
\phi^2.
$$

<details><summary><strong>Solution</strong></summary>

The field $\phi$ is not invariant because it shifts by $c$. The derivative is invariant because $c$ is constant:

$$
\partial_\mu(\phi+c)=\partial_\mu\phi.
$$

Therefore $(\partial_\mu\phi)(\partial^\mu\phi)$ is invariant. The operator $\phi^2$ is not invariant because

$$
(\phi+c)^2=\phi^2+2c\phi+c^2.
$$

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, spontaneous symmetry breaking, and functional methods.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on spacetime symmetries, internal symmetries, and currents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on symmetries, fields, and particles.
- Mark Srednicki, *Quantum Field Theory*, sections on continuous symmetries, discrete symmetries, nonabelian symmetries, and Ward identities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Noether’s theorem, gauge invariance, Ward–Takahashi identities, Yang–Mills theory, and anomalies.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry, symmetry breaking, and effective field theory examples.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
