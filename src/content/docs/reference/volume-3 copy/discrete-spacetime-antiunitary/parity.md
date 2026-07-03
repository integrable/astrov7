---
title: "Parity"
description: "Defines parity as spatial orientation reversal in QFT, derives its action on scalar, vector, spinor, and gauge-field operators, and explains intrinsic parity, chirality, parity violation, and parity-odd topological terms."
sidebar:
  label: "Parity"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§23, 40; Weinberg Vol. I §§2.6, 5; Coleman, Lectures on QFT ch. 22; Schwartz ch. 11; standard spinor and discrete-symmetry treatments."
topics:
  - parity
  - discrete spacetime symmetry
  - intrinsic parity
  - pseudoscalar
  - axial vector
  - chirality
  - Dirac bilinears
  - topological terms
canonicalTopics:
  - parity
  - spatial-reflection
  - intrinsic-parity
  - pseudoscalar
  - axial-vector
  - chirality
  - parity-violation
researchStatus:
  established:
    - "Parity is the spatial orientation-reversing disconnected Lorentz transformation; its action on scalars, vectors, spinors, bilinears, gauge fields, and local operators is standard QFT material."
    - "Parity is a possible symmetry of a theory, not a guaranteed one; chiral interactions, pseudoscalar couplings, theta terms, and parity anomalies can violate it."
  active:
    - "Parity and reflection symmetries remain active in modern QFT through spin and Pin structures, topological phases, crystalline symmetries, parity anomalies, and reflection-positive Euclidean formulations."
---

## Summary

Parity is the transformation that reverses spatial orientation. In four-dimensional Minkowski spacetime it is represented on coordinates by

$$
\mathsf P^\mu{}_{\nu}=\operatorname{diag}(1,-1,-1,-1),
\qquad
\mathsf P:(t,\mathbf x)\mapsto(t,-\mathbf x).
$$

The determinant is negative:

$$
\det \mathsf P=-1.
$$

So parity is not a proper Lorentz transformation. It is a disconnected spacetime transformation. It cannot be obtained by exponentiating the Lorentz algebra.

A parity symmetry of a QFT is a unitary operator $P$ on the Hilbert space whose action on local operators has the form

$$
P^\dagger\mathcal O_a(x)P
=\rho(\mathsf P)_a{}^b\,\mathcal O_b(\mathsf P x),
$$

with the representation matrix $\rho(\mathsf P)$ depending on the type of operator. The existence of such a transformation rule is kinematic. Whether it is a symmetry of the theory is dynamical: the action, measure, state, boundary condition, and background fields must also be invariant.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Parity sends spacetime points to their spatial reflections and acts on scalars, polar vectors, axial vectors, Dirac fields, chirality, and helicity.](/figures/symmetry-anomalies-topology/parity-action-on-fields.svg)

<figcaption>

Parity reverses spatial orientation. Polar vectors and axial vectors therefore transform differently. For spinors, parity inserts $\gamma^0$ and exchanges left and right chirality. For one-particle states, $\mathbf p$ flips while $\mathbf J$ does not, so helicity changes sign.

</figcaption>
</figure>

The most important warning is:

$$
\text{parity transformation rule}\neq\text{parity symmetry of the theory}.
$$

The weak interactions famously violate parity. Many topological terms also know about parity because parity reverses orientation.

## Prerequisites

Read [Internal versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/), [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), and the chapter overview [Discrete, Spacetime, and Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/).

You should know the mostly-minus convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

and the gamma-matrix convention

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}.
$$

For the spinor sections, it helps to know Dirac conjugation

$$
\bar\psi=\psi^\dagger\gamma^0
$$

and the chirality matrix

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

## Core idea

Parity asks whether the mirror-reflected process is physically equivalent to the original process.

This is not merely a coordinate relabeling. A passive coordinate change rewrites the same configuration using different coordinates. A parity symmetry is an active operation comparing the original physical configuration with the spatially reflected physical configuration.

For example, suppose a process emits a particle preferentially along the direction of a spin. The parity-reflected process reverses the particle momentum but leaves angular momentum as an axial vector. If the rates differ, parity is violated.

That is the conceptual heart of parity violation: a mirror world may obey different transition amplitudes from the original world.

The parity operation has three layers:

1. a spacetime map $x\mapsto\mathsf P x$;
2. a representation matrix acting on field or operator components;
3. possible intrinsic parity phases or mixing matrices acting on species labels.

For a local operator multiplet $\mathcal O_a$, the general form is

$$
P^\dagger\mathcal O_a(x)P
=R(P)_a{}^b\,\mathcal O_b(\mathsf P x),
$$

where $R(P)$ may include Lorentz-index signs, spinor matrices, internal mixing, and intrinsic parity factors.

## Setup and conventions

We distinguish three symbols:

| Symbol | Meaning |
|---|---|
| $\mathsf P^\mu{}_{\nu}$ | The spacetime parity matrix $\operatorname{diag}(1,-1,-1,-1)$. |
| $P$ | The unitary Hilbert-space operator implementing parity, when it exists. |
| $\eta_P$ | An intrinsic parity phase or sign attached to a field or one-particle state. |

The coordinate action is

$$
(\mathsf P x)^0=x^0,
\qquad
(\mathsf P x)^i=-x^i.
$$

For derivatives,

$$
\frac{\partial}{\partial x^0}\mapsto
\frac{\partial}{\partial x^0},
\qquad
\frac{\partial}{\partial x^i}\mapsto
-\frac{\partial}{\partial x^i}.
$$

The integration measure is invariant because the absolute value of the determinant is one:

$$
d^4(\mathsf P x)=|\det\mathsf P|\,d^4x=d^4x.
$$

However, orientation-sensitive objects such as the Levi-Civita tensor acquire a sign:

$$
\epsilon^{\mu\nu\rho\sigma}
\mapsto
(\det\mathsf P)\,
\mathsf P^\mu{}_{\alpha}\mathsf P^\nu{}_{\beta}
\mathsf P^\rho{}_{\gamma}\mathsf P^\sigma{}_{\delta}
\epsilon^{\alpha\beta\gamma\delta}.
$$

That sign is the source of many parity-odd topological densities.

:::note[Convention-sensitive source note]
Some books write the operator action as $P^{-1}\mathcal O(x)P$, others as $P\mathcal O(x)P^{-1}$, and some use passive coordinate conventions. This page follows the earlier pages in this volume and writes the transformed operator as $P^\dagger\mathcal O(x)P$. Since parity is unitary, $P^\dagger=P^{-1}$. Translate formulas by keeping track of whether the operator or its inverse is acting on the left.
:::

## Scalars and pseudoscalars

A real scalar field can transform as

$$
P^\dagger\phi(t,\mathbf x)P
=\eta_P\phi(t,-\mathbf x),
\qquad
\eta_P=\pm1.
$$

If $\eta_P=+1$, the field is parity even. If $\eta_P=-1$, the field is parity odd. A parity-odd scalar under proper Lorentz transformations is often called a **pseudoscalar**.

The kinetic term is invariant for either sign:

$$
\frac12\partial_\mu\phi\partial^\mu\phi
\mapsto
\frac12\partial_\mu\phi\partial^\mu\phi
\quad\text{evaluated at }(t,-\mathbf x).
$$

The sign matters in interactions. For a parity-odd pseudoscalar $a$, the term

$$
\lambda a^3
$$

is parity odd and therefore violates parity, while

$$
\lambda a^2\phi^2
$$

is parity even if $\phi$ is parity even.

For several scalar fields $\phi^I$, parity can mix them:

$$
P^\dagger\phi^I(x)P=R(P)^I{}_J\phi^J(\mathsf P x),
$$

with $R(P)^2=1$ for ordinary bosonic fields when parity squares to the identity. The eigenvectors of $R(P)$ are the parity-even and parity-odd combinations.

### A useful diagnostic

An interaction is parity invariant if every monomial transforms into itself after accounting for:

- the coordinate reflection;
- the Lorentz-index signs;
- the intrinsic parity signs;
- possible species mixing;
- background-field transformations.

For scalar potentials, this often reduces to the simple rule: an odd number of parity-odd scalar factors makes the term parity odd.

## Polar vectors and axial vectors

A polar vector operator $V^\mu$ transforms as

$$
P^\dagger V^\mu(x)P
=\mathsf P^\mu{}_{\nu}V^\nu(\mathsf P x),
$$

or in components,

$$
P^\dagger V^0(t,\mathbf x)P
=V^0(t,-\mathbf x),
$$

$$
P^\dagger V^i(t,\mathbf x)P
=-V^i(t,-\mathbf x).
$$

A spatial displacement $\mathbf x$, momentum $\mathbf p$, electric current $\mathbf j$, and electric field $\mathbf E$ are polar vectors. They change sign under parity.

An **axial vector**, also called a pseudovector, gets an additional orientation sign. Its components transform oppositely:

$$
P^\dagger A^0(t,\mathbf x)P
=-A^0(t,-\mathbf x),
$$

$$
P^\dagger A^i(t,\mathbf x)P
=+A^i(t,-\mathbf x).
$$

Angular momentum is the canonical example:

$$
\mathbf L=\mathbf x\times\mathbf p.
$$

Both $\mathbf x$ and $\mathbf p$ flip under parity, so $\mathbf L$ does not. Spin behaves as an axial vector as well.

This polar-versus-axial distinction is one of the fastest ways to detect parity violation. A scalar product of a polar vector with an axial vector is a pseudoscalar:

$$
\mathbf p\cdot\mathbf S\mapsto -\mathbf p\cdot\mathbf S.
$$

A Hamiltonian term proportional to $\mathbf p\cdot\mathbf S$ violates parity unless another parity-odd object also transforms.

## Electromagnetic fields and topological density

Take the gauge potential to transform as a polar vector:

$$
P^\dagger A_0(t,\mathbf x)P=A_0(t,-\mathbf x),
$$

$$
P^\dagger A_i(t,\mathbf x)P=-A_i(t,-\mathbf x).
$$

The electric and magnetic fields transform as

$$
\mathbf E(t,\mathbf x)\mapsto -\mathbf E(t,-\mathbf x),
\qquad
\mathbf B(t,\mathbf x)\mapsto +\mathbf B(t,-\mathbf x).
$$

The difference is geometric. The magnetic field is built with a spatial Levi-Civita symbol:

$$
B^i=\frac12\epsilon^{ijk}F_{jk},
$$

so it is an axial vector.

The Maxwell kinetic term is parity even:

$$
F_{\mu\nu}F^{\mu\nu}=2(\mathbf B^2-\mathbf E^2).
$$

The topological density is parity odd:

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
=-4\mathbf E\cdot\mathbf B,
$$

with the sign following the common convention

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}
$$

in mostly-minus conventions. Since $\mathbf E$ is odd and $\mathbf B$ is even under parity,

$$
\mathbf E\cdot\mathbf B\mapsto-\mathbf E\cdot\mathbf B.
$$

Therefore a four-dimensional theta term

$$
S_\theta\propto\theta\int F\wedge F
$$

is parity odd unless $\theta$ also transforms as a pseudoscalar parameter or has a special periodic value. This is the local seed of many later discussions of theta angles, anomalies, and topological terms.

:::note[Convention-sensitive source note]
The overall sign in $F_{\mu\nu}\widetilde F^{\mu\nu}=\pm4\mathbf E\cdot\mathbf B$ depends on metric, epsilon, and electric-field conventions. The parity conclusion does not: $F\widetilde F$ is orientation odd in four dimensions.
:::

## Dirac fields

For a Dirac field, the standard parity action is

$$
P^\dagger\psi(t,\mathbf x)P
=\eta_P\gamma^0\psi(t,-\mathbf x),
\qquad
|\eta_P|=1.
$$

The phase $\eta_P$ is an intrinsic parity convention for the field. For a single free Dirac field it can often be changed by a field redefinition. Relative intrinsic parities between different fields, or parity assignments constrained by interactions, can be physical.

The Dirac conjugate transforms as

$$
P^\dagger\bar\psi(t,\mathbf x)P
=\eta_P^*\bar\psi(t,-\mathbf x)\gamma^0.
$$

The free Dirac Lagrangian

$$
\mathcal L=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
$$

is invariant because

$$
\gamma^0\gamma^\mu\gamma^0
=\mathsf P^\mu{}_{\nu}\gamma^\nu,
$$

and derivatives transform with the same parity matrix.

### Chirality is exchanged

The left- and right-handed projections are

$$
\psi_L=\frac{1-\gamma^5}{2}\psi,
\qquad
\psi_R=\frac{1+\gamma^5}{2}\psi.
$$

Since

$$
\gamma^0\gamma^5\gamma^0=-\gamma^5,
$$

parity exchanges chirality:

$$
P^\dagger\psi_L(t,\mathbf x)P
=\eta_P\gamma^0\psi_R(t,-\mathbf x),
$$

$$
P^\dagger\psi_R(t,\mathbf x)P
=\eta_P\gamma^0\psi_L(t,-\mathbf x).
$$

This is the conceptual reason chiral theories are parity-sensitive. A theory containing only left-handed Weyl fermions in a representation generally cannot be parity invariant unless there are corresponding right-handed degrees of freedom, possibly in related representations, for parity to exchange with them.

## Dirac bilinears

The transformation of Dirac bilinears is one of the most useful parity lookup tables in QFT. With the parity action above:

| Bilinear | Name | Parity |
|---|---|---|
| $\bar\psi\psi$ | scalar | even |
| $i\bar\psi\gamma^5\psi$ | pseudoscalar | odd |
| $\bar\psi\gamma^0\psi$ | vector time component | even |
| $\bar\psi\gamma^i\psi$ | vector spatial component | odd |
| $\bar\psi\gamma^0\gamma^5\psi$ | axial-vector time component | odd |
| $\bar\psi\gamma^i\gamma^5\psi$ | axial-vector spatial component | even |

The vector current

$$
j^\mu=\bar\psi\gamma^\mu\psi
$$

is a polar vector. The axial current

$$
j_5^\mu=\bar\psi\gamma^\mu\gamma^5\psi
$$

is an axial vector.

This table explains many model-building facts. For example, the Yukawa coupling

$$
g\phi\bar\psi\psi
$$

is parity even if $\phi$ is an ordinary scalar, while

$$
ig a\bar\psi\gamma^5\psi
$$

is parity even if $a$ is a pseudoscalar. Without the factor of $i$, Hermiticity and convention choices must be checked carefully.

:::note[Convention-sensitive source note]
The table assumes $\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3$ and the parity action $\psi\mapsto\eta_P\gamma^0\psi(\mathsf P x)$. If a source uses the opposite convention for $\gamma^5$ or writes the parity operator on the other side of the field, intermediate signs may look different, but the scalar/pseudoscalar/vector/axial-vector classification is invariant.
:::

## Intrinsic parity of states

Parity also acts on one-particle states. For a spinless particle,

$$
P|\mathbf p\rangle
=\eta_P|-\mathbf p\rangle,
$$

where $\eta_P$ is the intrinsic parity of the particle.

For a two-particle state with relative orbital angular momentum $\ell$, the spatial wavefunction contributes a factor

$$
(-1)^\ell.
$$

Thus the total parity is schematically

$$
\eta_{\mathrm{total}}=\eta_1\eta_2(-1)^\ell,
$$

for distinguishable spinless particles, with additional exchange and spin-statistics details when particles are identical or fermionic.

For fermion–antifermion pairs, the relative intrinsic parity convention is constrained by the field transformation. In the standard Dirac convention, a fermion–antifermion pair carries an extra relative sign compared with two scalar particles. This is why positronium, quarkonium, and meson quantum-number assignments involve formulas such as

$$
P=(-1)^{\ell+1}
$$

for a fermion–antifermion bound state in common conventions.

The useful lesson is not to memorize every bound-state formula in this page. The useful lesson is to separate:

$$
\text{intrinsic parity}\quad\times\quad\text{orbital wavefunction parity}\quad\times\quad\text{spin/statistics data}.
$$

## Parity invariance of an action

A classical action is parity invariant if

$$
S[\Phi^P]=S[\Phi],
$$

where $\Phi^P$ denotes the parity-transformed fields and backgrounds.

For a Lagrangian density, the usual local condition is

$$
\mathcal L(\Phi^P(x),\partial\Phi^P(x))
=\mathcal L(\Phi(\mathsf P x),\partial\Phi(\mathsf P x)),
$$

so that after changing variables $x\mapsto\mathsf P x$ in the integral, the action is unchanged.

In the quantum theory, this is not enough. One also needs the measure and regularization to preserve parity:

$$
\mathcal D\Phi^P=\mathcal D\Phi.
$$

If the classical action is invariant but the regulated quantum measure cannot be chosen parity invariant, parity is anomalous. The most famous examples are parity anomalies in odd-dimensional fermion systems, where gauge invariance and parity can be in tension.

## Background fields and parity

A symmetry of a theory with sources must act on the sources too. If a current couples to a background field as

$$
\Delta S=\int d^4x\,A_\mu j^\mu,
$$

then parity invariance requires $A_\mu$ and $j^\mu$ to transform compatibly. If $j^\mu$ is a vector current, $A_\mu$ should transform as a vector background. If the source is held fixed while fields are transformed, the source may explicitly break parity.

This is not a technical nuisance. It is how response theory detects symmetry. For example, a background magnetic field is parity even as an axial vector but time-reversal odd. Therefore the presence of a fixed magnetic field may preserve parity while breaking time reversal.

For an effective action $W[A,g,\dots]$, parity invariance means

$$
W[A^P,g^P,\dots]=W[A,g,\dots],
$$

possibly up to local counterterms or anomaly phases. Later anomaly pages refine this statement.

## Parity violation

Parity can be broken in three different ways.

**Explicit breaking** occurs when the action contains terms that are not invariant. For example, with an ordinary scalar $\phi$ and pseudoscalar $a$,

$$
\lambda a\phi^2
$$

breaks parity if no parameter or field transformation compensates the odd sign of $a$.

**Spontaneous breaking** occurs when the action is parity invariant but the chosen state is not. A parity-odd order parameter has

$$
\langle a\rangle\neq0,
$$

which selects one of two parity-related vacua.

**Anomalous breaking** occurs when the classical parity symmetry cannot be preserved by the quantum definition. The classical transformation law exists, but the regulated measure or partition function fails to be invariant.

The weak interactions give the historically decisive example of explicit parity violation in nature: the charged weak interaction couples chirally to left-handed fermions. From the QFT viewpoint, the key fact is the same as above: parity exchanges left and right chirality, so a purely left-handed interaction cannot be parity invariant by itself.

## Parity versus a single spatial reflection

In three spatial dimensions, “parity” often means inversion of all spatial coordinates:

$$
(x,y,z)\mapsto(-x,-y,-z).
$$

A single mirror reflection, such as

$$
(x,y,z)\mapsto(-x,y,z),
$$

also reverses orientation. The two differ by a proper rotation:

$$
(-x,-y,-z)=R_\pi\circ(-x,y,z)
$$

for a suitable rotation $R_\pi$. In a rotationally invariant relativistic theory, these are equivalent choices of orientation reversal up to a continuous rotation.

In a crystal or a theory with only a discrete rotation group, the distinction becomes physical. Mirror symmetries, glide symmetries, inversion, and rotations are separate crystalline operations. This is why the later crystalline-symmetry preview does not simply identify every orientation-reversing operation with parity.

## Parity and topology

Parity reverses orientation. Topological terms often depend on orientation. Therefore parity is a natural diagnostic for topological response.

In four dimensions,

$$
\int F\wedge F
$$

is orientation odd. In three dimensions, the Chern–Simons action

$$
S_{\mathrm{CS}}=\frac{k}{4\pi}\int \operatorname{tr}\left(A\wedge dA+\frac23 A\wedge A\wedge A\right)
$$

is also odd under orientation reversal. Thus a pure Chern–Simons term generally breaks parity unless additional fields or levels transform so that the full theory is invariant.

This is the seed of the **parity anomaly**: in odd dimensions, integrating out massive fermions can generate half-integer Chern–Simons contact terms. One may be forced to choose between preserving gauge invariance and preserving parity, depending on the theory and background structure.

We will return to this in [Anomalies of Discrete Symmetries Preview](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/anomalies-of-discrete-symmetries-preview/) and the Anomalies chapter.

## Common pitfalls

**Treating parity as an infinitesimal symmetry.** Parity is disconnected from the identity. There is no Noether current whose charge generates parity by exponentiation.

**Confusing passive coordinates with active symmetry.** A coordinate relabeling is always allowed. A parity symmetry is a physical equivalence between a configuration and its mirror.

**Forgetting intrinsic parity.** The spacetime reflection is only part of the transformation. Fields may also carry intrinsic signs, phases, or species-mixing matrices.

**Calling every parity-odd scalar a Lorentz non-scalar.** A pseudoscalar is still a scalar under proper orthochronous Lorentz transformations. It is odd only under orientation reversal.

**Treating magnetic fields as polar vectors.** $\mathbf B$ is an axial vector. It is parity even and time-reversal odd.

**Assuming parity exists in chiral theories.** Parity exchanges left and right chirality. A theory with asymmetric chiral matter generally cannot have parity unless parity also maps it to another sector or another theory.

**Ignoring background fields.** A Lagrangian may look parity invariant, but a fixed background source, boundary condition, theta angle, or defect can break parity.

**Declaring all intrinsic parity phases physical.** Many phases can be changed by field redefinitions. Relative phases constrained by interactions, particle–antiparticle assignments, or reflection-square data are the meaningful ones.

## Relations to other pages

- **Time Reversal** develops the antiunitary cousin of parity. Do not copy parity rules and replace $\mathbf x$ by $t$; time reversal is subtler.
- **Charge Conjugation** explains how representation conjugation and particle–antiparticle exchange interact with parity in $CP$.
- **CPT Theorem Perspective** explains why $CPT$ is structurally protected under standard local relativistic assumptions even when $C$, $P$, and $T$ are separately broken.
- **Spin Structures and Fermion Parity** revisits reflection symmetries using spin and Pin structures.
- [Topological Terms](/symmetry-anomalies-topology/topological-terms/) develops the orientation-sensitive terms, such as theta terms and Chern–Simons terms, that parity often constrains.
- [Anomalies](/symmetry-anomalies-topology/anomalies/) explains how a classical parity symmetry can fail after quantization.

## Research status

The transformation rules in this page are established textbook QFT. They are not speculative.

The active frontier begins when parity is coupled to global topology: nontrivial manifolds, spin and Pin structures, boundaries, defects, crystalline symmetries, topological phases, anomaly inflow, and dualities. In those settings, “parity” is no longer just a sign table for fields. It becomes part of the spacetime-background data used to define the theory.

A practical research-level warning is that reflection symmetries can be presentation-dependent in dualities. One Lagrangian description may realize parity geometrically, while a dual description realizes it as parity combined with internal symmetry, charge conjugation, or a topological operation.

## Exercises

### Exercise 1: Scalar and pseudoscalar interactions

Let $\phi$ be parity even and $a$ parity odd:

$$
P^\dagger\phi(t,\mathbf x)P=\phi(t,-\mathbf x),
\qquad
P^\dagger a(t,\mathbf x)P=-a(t,-\mathbf x).
$$

Which of the following terms are parity invariant?

$$
\phi^3,
\qquad
\phi a^2,
\qquad
a\phi^2,
\qquad
a^3,
\qquad
(\partial_\mu a)(\partial^\mu a).
$$

<details><summary><strong>Solution</strong></summary>

Count the number of parity-odd factors $a$. Terms with an even number of $a$ fields are parity even; terms with an odd number are parity odd.

Thus $\phi^3$ and $\phi a^2$ are parity invariant, while $a\phi^2$ and $a^3$ are parity odd and break parity unless their coefficients also transform as pseudoscalars.

The kinetic term $(\partial_\mu a)(\partial^\mu a)$ is parity invariant. The field contributes two minus signs overall, and the spatial derivative signs are contracted into the Lorentz scalar.

</details>

### Exercise 2: Vector and axial-vector currents

Using

$$
P^\dagger\psi(x)P=\eta_P\gamma^0\psi(\mathsf P x),
$$

show that

$$
j^\mu=\bar\psi\gamma^\mu\psi
$$

is a vector and

$$
j_5^\mu=\bar\psi\gamma^\mu\gamma^5\psi
$$

is an axial vector.

<details><summary><strong>Solution</strong></summary>

The Dirac conjugate transforms as

$$
P^\dagger\bar\psi(x)P=\eta_P^*\bar\psi(\mathsf P x)\gamma^0.
$$

For the vector current,

$$
P^\dagger j^\mu(x)P
=\bar\psi(\mathsf P x)\gamma^0\gamma^\mu\gamma^0\psi(\mathsf P x).
$$

Using

$$
\gamma^0\gamma^\mu\gamma^0=\mathsf P^\mu{}_{\nu}\gamma^\nu,
$$

gives

$$
P^\dagger j^\mu(x)P
=\mathsf P^\mu{}_{\nu}j^\nu(\mathsf P x).
$$

For the axial current,

$$
P^\dagger j_5^\mu(x)P
=\bar\psi(\mathsf P x)\gamma^0\gamma^\mu\gamma^5\gamma^0\psi(\mathsf P x).
$$

Since $\gamma^0\gamma^5\gamma^0=-\gamma^5$, this gains one extra sign relative to the vector current:

$$
P^\dagger j_5^\mu(x)P
=-\mathsf P^\mu{}_{\nu}j_5^\nu(\mathsf P x).
$$

Therefore $j_5^0$ is parity odd and $j_5^i$ is parity even: it is an axial vector.

</details>

### Exercise 3: The theta density is parity odd

Assume

$$
\mathbf E\mapsto-\mathbf E,
\qquad
\mathbf B\mapsto+\mathbf B
$$

under parity. Show that $F_{\mu\nu}\widetilde F^{\mu\nu}$ is parity odd.

<details><summary><strong>Solution</strong></summary>

In common mostly-minus conventions,

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
=-4\mathbf E\cdot\mathbf B.
$$

Under parity,

$$
\mathbf E\cdot\mathbf B
\mapsto
(-\mathbf E)\cdot(+\mathbf B)
=-\mathbf E\cdot\mathbf B.
$$

Therefore

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
\mapsto
-F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The conclusion is independent of the overall sign convention in the relation to $\mathbf E\cdot\mathbf B$.

</details>

### Exercise 4: Why a single Weyl fermion resists parity

Let $\psi_L$ be a left-handed Weyl fermion. Explain why a theory containing only $\psi_L$ and no suitable right-handed partner generally cannot have ordinary parity symmetry.

<details><summary><strong>Solution</strong></summary>

Parity exchanges chirality:

$$
P^\dagger\psi_L(x)P
=\eta_P\gamma^0\psi_R(\mathsf P x).
$$

Thus the parity transform of a left-handed field is right-handed. If the theory has no right-handed field with the required quantum numbers, the transformed field is not an operator in the same theory. Then parity cannot be represented as a symmetry acting within the Hilbert space of that theory.

There are loopholes in special situations: parity might map the theory to a distinct mirror theory, exchange sectors, or combine with another operation. But ordinary parity as an internal operation of the same chiral theory requires appropriate right-handed degrees of freedom.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§23 and 40. Discrete symmetries for scalar and spinor fields.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially §§2.6–2.7 and the free-field chapters. Space inversion, time reversal, projective representations, and field transformations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 22. CPT and Fermi fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 11. Spinor conventions and discrete transformations.
- Claude Itzykson and Jean-Bernard Zuber, *Quantum Field Theory*, sections on discrete symmetries and spinor bilinears.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, sections on parity, charge conjugation, time reversal, and the Standard Model.
- R. Jackiw, lectures and reviews on parity anomalies and topological mass generation.
- A. N. Redlich, classic papers on gauge noninvariance and parity violation of three-dimensional fermions.

## Version history

- 2026-06-17: Initial polished page. Added parity conventions, scalar and pseudoscalar rules, vector and axial-vector rules, electromagnetic fields, Dirac spinor transformation, chirality exchange, bilinear table, intrinsic parity, background-field cautions, parity violation types, topology handoff, and exercises with solutions.
