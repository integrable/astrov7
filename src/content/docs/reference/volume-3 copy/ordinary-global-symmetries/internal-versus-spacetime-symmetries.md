---
title: "Internal versus Spacetime Symmetries"
description: "Explains the distinction between symmetries that rotate internal labels and symmetries that move spacetime points, including their operator actions, generators, examples, and common confusions."
sidebar:
  label: "Internal vs Spacetime"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I Ch. 2; Coleman lectures on spacetime and internal symmetries; Srednicki Sections 22–24 and 33–40; Schwartz Chs. 8, 10–12."
topics:
  - internal symmetry
  - spacetime symmetry
  - Poincaré symmetry
  - operator transformations
  - Coleman–Mandula theorem
canonicalTopics:
  - internal-symmetry
  - spacetime-symmetry
  - poincare-symmetry
researchStatus:
  established:
    - "The distinction between ordinary internal symmetries and spacetime symmetries is standard in relativistic QFT and underlies the classification of particles, operators, currents, and Ward identities."
    - "Under the hypotheses of the Coleman–Mandula theorem, nontrivial bosonic symmetries of the S-matrix split into spacetime and internal parts, with supersymmetry as the famous graded extension."
  active:
    - "Modern generalized symmetries, spacetime defects, subsystem symmetries, fractonic systems, and quantum-gravity constraints refine the clean textbook separation between internal and spacetime symmetry."
---

## Summary

An **internal symmetry** changes labels attached to a field, state, or operator while leaving the spacetime point fixed. A **spacetime symmetry** moves the point, and may also rotate tensor or spinor indices. This distinction is one of the first filters you should apply to any proposed symmetry in QFT.

For a field multiplet $\Phi_i(x)$, an internal symmetry has the schematic form

$$
\Phi_i(x) \mapsto R(g)_i{}^j \Phi_j(x),
$$

while a spacetime symmetry has the schematic form

$$
\Phi_i(x) \mapsto S(\Lambda)_i{}^j \Phi_j(\Lambda^{-1}x).
$$

The first formula changes the value over a fixed point $x$. The second formula compares fields at different spacetime points. If the field carries Lorentz indices, spinor indices, or tensor indices, the matrix $S(\Lambda)$ also acts on those indices.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A diagram contrasting internal symmetries, which rotate the field value over a fixed spacetime point, with spacetime symmetries, which move spacetime points and rotate tensor or spin indices.](/figures/symmetry-anomalies-topology/internal-spacetime-symmetry-actions.svg)

<figcaption>

Internal symmetries act vertically on field-space labels over each point. Spacetime symmetries act horizontally on the point $x$ and, when necessary, vertically on tensor or spin indices. The distinction is cleanest for relativistic QFT on flat spacetime, but the same idea guides background fields, curvature couplings, and Ward identities.

</figcaption>
</figure>

The separation is not just vocabulary. Internal symmetries lead to flavor multiplets, charge sectors, background gauge fields, and ordinary selection rules. Spacetime symmetries lead to energy, momentum, angular momentum, spin, stress tensors, causality constraints, and the classification of particles and local operators.

## Prerequisites

You should first read [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) and the [Conventions and Notation](/symmetry-anomalies-topology/conventions/). This page assumes familiarity with local operators, Hilbert-space symmetries, and the basic idea that fields can carry representation indices.

No detailed representation theory is required, but it helps to know that scalar, vector, tensor, Weyl, and Dirac fields transform differently under Lorentz transformations.

## Core idea

The fastest diagnostic is this:

| Question | Internal symmetry | Spacetime symmetry |
|---|---|---|
| Does it move the spacetime point? | No. | Yes, generally. |
| Does it act on local operators at the same point? | Yes. | It relates operators at different points. |
| Typical generators | Flavor charges $Q_a$. | $P_\mu$, $M_{\mu\nu}$, possibly $D$, $K_\mu$. |
| Typical current | Noether current $j_a^\mu$. | Stress tensor $T^{\mu\nu}$ and angular-momentum currents. |
| Typical background source | Gauge field $A_\mu$ for a global symmetry. | Metric, vielbein, spin connection, or spacetime geometry. |
| Typical local data | Charges and flavor representations. | Scaling dimension, spin, Lorentz representation. |

The word “internal” does not mean “less physical.” Electric charge, baryon number, flavor symmetry, center symmetry, and many exact or approximate particle-physics symmetries are internal. The word “spacetime” does not mean “geometric decoration.” Translation invariance gives momentum conservation. Lorentz invariance fixes the possible spins of particles. Scale and conformal symmetry control critical phenomena.

Both kinds of symmetry act on the same quantum theory. The distinction is about **what their action does to local spacetime support**.

## Setup and conventions

Let $G_{\rm int}$ be an internal symmetry group. For a local operator multiplet $\mathcal O_i(x)$ in a representation $R$, we write

$$
U(g)^\dagger \mathcal O_i(x) U(g) = R(g)_i{}^j \mathcal O_j(x),    g \in G_{\rm int}.
$$

The point $x$ is unchanged. If $G_{\rm int}$ is continuous, near the identity we use

$$
U(\alpha)=e^{-i\alpha^aQ_a},    \delta_a\mathcal O=i[Q_a,\mathcal O].
$$

Now let $g_{\rm st}$ be a spacetime symmetry. For a Poincaré transformation, write the action on points as

$$
x^\mu \mapsto x'^\mu = \Lambda^\mu{}_\nu x^\nu+a^\mu.
$$

A local operator carrying Lorentz or spin indices transforms by a finite-dimensional matrix $S(\Lambda)$ on those indices and by pullback on the point. With the pullback convention used on this page,

$$
U(a,\Lambda)^\dagger \mathcal O_i(x) U(a,\Lambda)
=
S(\Lambda)_i{}^j \mathcal O_j(\Lambda^{-1}(x-a)).
$$

Different texts place the inverse transformation on the other side of this equation. That is a convention about whether one transforms the operator, the coordinate label, or both. The invariant statement is that a spacetime symmetry maps the local algebra attached to a region $R$ to the local algebra attached to the transformed region $gR$.

:::note[Source note]
Weinberg’s treatment starts from symmetries of quantum states and then derives the Poincaré transformation properties of particles and fields. Many Lagrangian texts instead begin with field transformations. The two approaches agree once the convention for whether $U$ or $U^\dagger$ appears on the left is fixed.
:::

## Internal symmetries

An internal symmetry acts on degrees of freedom that are not spacetime coordinates. Common examples include:

| Symmetry | Typical action | Charged objects |
|---|---|---|
| $U(1)$ phase symmetry | $\phi(x) \mapsto e^{i\alpha}\phi(x)$ | Charged fields, particles, local operators. |
| $SU(N)$ flavor symmetry | $\psi_I(x) \mapsto R_I{}^J \psi_J(x)$ | Flavor multiplets. |
| $\mathbb Z_2$ sign symmetry | $\phi(x) \mapsto -\phi(x)$ | Odd operators. |
| Center symmetry | Acts on line operators rather than local fields in many gauge theories. | Wilson lines or other extended operators. |

For a continuous internal symmetry with generators $Q_a$, the charges usually commute with spacetime translations:

$$
[Q_a,P_\mu]=0.
$$

For ordinary internal symmetries in a Lorentz-invariant QFT, they also commute with Lorentz generators:

$$
[Q_a,M_{\mu\nu}]=0.
$$

This is why internal charges label particle multiplets without changing their momentum or spin. A proton and neutron may sit in an approximate isospin multiplet; the symmetry changes one internal label into another, not the spacetime momentum of the state.

Internal symmetries are also the ones most directly coupled to background gauge fields. If $j_a^\mu$ is the current, the source term has the schematic form

$$
S_{source}=\int d^dx A_\mu^a j_a^\mu.
$$

This coupling is the starting point for background fields, gauging, Ward identities, and ’t Hooft anomalies.

## Spacetime symmetries

A spacetime symmetry acts on the stage on which local operators are placed. The most important relativistic example is the Poincaré group, generated by translations $P_\mu$ and Lorentz transformations $M_{\mu\nu}$.

The commutation relations include

$$
[P_\mu,P_\nu]=0,
$$

$$
[M_{\mu\nu},P_\rho]
=
i(\eta_{\nu\rho}P_\mu-\eta_{\mu\rho}P_\nu),
$$

and

$$
[M_{\mu\nu},M_{\rho\sigma}]
=
i(\eta_{\mu\rho}M_{\nu\sigma}-\eta_{\mu\sigma}M_{\nu\rho}-\eta_{\nu\rho}M_{\mu\sigma}+\eta_{\nu\sigma}M_{\mu\rho}).
$$

These are not flavor charges. They determine how energy, momentum, spin, and angular momentum behave.

Continuous spacetime symmetries are controlled by the stress tensor. Translation invariance gives conservation of energy and momentum,

$$
\partial_\mu T^{\mu\nu}=0,
$$

and the conserved momentum operators are

$$
P^\nu=\int d^{d-1}\mathbf x T^{0\nu}(t,\mathbf x).
$$

Lorentz invariance gives angular-momentum currents built from $T^{\mu\nu}$ together with possible spin-current terms. In a relativistic theory, the stress tensor can often be improved so that the Lorentz current takes the familiar orbital form

$$
J^\rho_{\mu\nu}=x_\mu T^\rho{}_\nu-x_\nu T^\rho{}_\mu.
$$

Scale and conformal symmetries, when present, are also spacetime symmetries. They do not merely rotate fields; they rescale or conformally transform the coordinates and impose strong constraints on correlation functions.

## The same field can carry both kinds of indices

A Dirac fermion with flavor is a compact example. Write

$$
\psi_{\alpha I}(x),
$$

where $\alpha$ is a spinor index and $I$ is a flavor index.

An internal $SU(N)$ flavor symmetry acts as

$$
\psi_{\alpha I}(x) \mapsto R_I{}^J \psi_{\alpha J}(x).
$$

A Lorentz transformation acts as

$$
\psi_{\alpha I}(x) \mapsto S(\Lambda)_\alpha{}^\beta \psi_{\beta I}(\Lambda^{-1}x).
$$

The flavor index and spinor index behave differently. The flavor index labels an internal multiplet. The spinor index is tied to spacetime rotations and boosts.

This separation is often hidden by notation. A field may carry many indices, but each index has a job. The planned page Symmetry Groups and Representations develops this representation language more systematically.

## Symmetry of the theory versus covariance of operators

A scalar field in a Lorentz-invariant theory is not invariant as a local function of coordinates. It is covariant:

$$
\phi(x) \mapsto \phi(\Lambda^{-1}x).
$$

This is exactly what must happen for correlation functions to be Lorentz invariant in content. For example,

$$
\langle\phi(x)\phi(y)\rangle = F((x-y)^2)
$$

is Lorentz invariant because $(x-y)^2$ is invariant. The local operator at one coordinate label is not fixed; the whole pattern of correlations respects the symmetry.

The same distinction appears for internal symmetries. A charged operator is not invariant under a $U(1)$ symmetry:

$$
\mathcal O_q(x) \mapsto e^{iq\alpha}\mathcal O_q(x).
$$

But the theory can still be invariant. Correlators are nonzero only when the product of representations contains a singlet, or in abelian language when total charge vanishes.

In both cases, the word “invariant” should usually be reserved for the theory, the action, the vacuum, the measure, or singlet observables. Individual nonsinglet operators transform covariantly.

## How currents differ

Internal and spacetime symmetries both produce conserved quantities when they are continuous and exact, but the currents have different meanings.

For an internal symmetry,

$$
\partial_\mu j_a^\mu=0,    Q_a=\int d^{d-1}\mathbf x j_a^0.
$$

The charge $Q_a$ changes the internal quantum numbers of fields and states.

For translations,

$$
\partial_\mu T^{\mu\nu}=0,    P^\nu=\int d^{d-1}\mathbf x T^{0\nu}.
$$

The charge $P^\nu$ changes spacetime dependence. It generates translations.

For rotations and boosts, the currents are built from the stress tensor and spin terms. Thus spacetime symmetry is inseparable from the local flow of energy and momentum.

This difference matters for background fields. Internal currents couple to background gauge fields. The stress tensor couples to the metric:

$$
\delta S=(1/2)\int d^dx \sqrt{|g|} T^{\mu\nu}\delta g_{\mu\nu}.
$$

That is why anomalies of internal symmetries are tested by background gauge fields, while gravitational and mixed anomalies involve background geometry.

:::note[Source note]
The normalization of $T^{\mu\nu}$ and the sign in the metric variation are convention-sensitive. This volume uses the mostly-minus metric by default; pages on stress tensors and gravitational anomalies will state their metric-variation convention explicitly.
:::

## Coleman–Mandula as a warning sign

In a relativistic theory with a nontrivial analytic S-matrix, a mass gap, a finite number of particle species below any mass, and other technical assumptions, the Coleman–Mandula theorem says roughly that ordinary bosonic symmetries of the S-matrix cannot mix spacetime and internal symmetries in an interesting way. They must split into the Poincaré symmetry times an internal symmetry group.

This is not a theorem about every QFT in every setting. It is a theorem with hypotheses. It does not apply directly to CFTs without a mass gap, to topological theories in the same way, to theories without an S-matrix, or to graded symmetries. Supersymmetry evades the conclusion because it uses fermionic generators and a graded algebra.

The lesson for this chapter is modest but important: the textbook separation between internal and spacetime symmetries is not merely aesthetic. Under broad particle-physics assumptions, attempts to combine them are highly constrained.

## Examples

### Complex scalar with phase symmetry

Let

$$
\mathcal L=\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi-\lambda(\phi^\dagger\phi)^2.
$$

The phase rotation

$$
\phi(x) \mapsto e^{i\alpha}\phi(x)
$$

is internal. The spacetime point stays fixed.

The same theory is also Poincaré invariant. Under a Lorentz transformation,

$$
\phi(x) \mapsto \phi(\Lambda^{-1}x),
$$

because $\phi$ is a Lorentz scalar. These are two different symmetries of the same QFT.

### Vector field

For a Lorentz vector operator $V_\mu(x)$,

$$
V_\mu(x) \mapsto \Lambda_\mu{}^\nu V_\nu(\Lambda^{-1}x)
$$

under Lorentz transformations. The vector index is a spacetime index, not a flavor index.

If $V_\mu^a(x)$ also carries an adjoint flavor index $a$, then an internal transformation may act as

$$
V_\mu^a(x) \mapsto R^a{}_b V_\mu^b(x).
$$

The same object can therefore transform under both spacetime and internal groups.

### Spin rotations in condensed matter

In a relativistic theory, spin is tied to spacetime rotations. In many nonrelativistic condensed-matter systems, however, an $SU(2)$ spin symmetry can behave like an internal symmetry: it rotates spin labels while leaving spatial coordinates fixed. This is possible because the microscopic spacetime symmetry is not the relativistic Lorentz group, and because spin-orbit coupling may be negligible or absent.

This is a good reminder that “internal versus spacetime” is always relative to the spacetime structure of the theory.

### Conformal symmetry

A conformal transformation changes spacetime points by angle-preserving maps and rescales local operators according to their scaling dimensions and spins. A scalar primary operator $\mathcal O$ transforms schematically as

$$
\mathcal O(x) \mapsto \Omega(x)^{-\Delta}\mathcal O(g^{-1}x),
$$

where $\Delta$ is the scaling dimension. This is a spacetime symmetry, not an internal one, even though scaling dimensions can look like charges.

## Practical checklist

When you meet a proposed symmetry, ask:

1. Does it move $x$?
2. Does it rotate Lorentz, spinor, or tensor indices?
3. Does it commute with $P_\mu$ and $M_{\mu\nu}$?
4. Does its conserved current look like an ordinary internal current $j^\mu_a$, or is it the stress tensor or a stress-tensor descendant?
5. Does its background source look like a gauge field, or like geometry?
6. Does it act faithfully on local operators, or only on extended operators?
7. Is it a symmetry of the theory, the chosen state, or merely the classical equations?

A surprisingly large fraction of symmetry mistakes are caught by the first two questions.

## Common pitfalls

**Calling every transformation of fields internal.** A Lorentz transformation acts on fields, but it also moves the argument $x$. That makes it a spacetime symmetry.

**Calling every matrix index an internal index.** Spinor and vector indices are spacetime representation indices. Flavor, color-flavor, and multiplet labels are internal indices. Gauge indices require separate care because gauge redundancy is not ordinary global symmetry.

**Forgetting that spacetime symmetries act on operators, not just coordinates.** A vector, spinor, tensor, current, or stress tensor has index transformations in addition to the motion of its point.

**Confusing spin with flavor.** In relativistic QFT, spin is a label of Poincaré representations. In some nonrelativistic systems, spin rotations may be treated as an internal symmetry. Context matters.

**Assuming scale symmetry is internal because it gives a number.** Scaling dimension is not an internal charge. Dilatations move spacetime points by $x\mapsto\lambda x$.

**Treating Coleman–Mandula as a slogan without hypotheses.** The theorem is powerful, but it is about S-matrix symmetries under specific assumptions. Supersymmetry, conformal symmetry, topological theories, and theories without an ordinary S-matrix require separate discussion.

**Equating gauge transformations with internal global symmetries.** A gauge transformation may look like a local internal rotation, but it is a redundancy unless a genuine global remnant acts on physical operators.

## Relations to other pages

- [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/) gives the general operator, Hilbert-space, path-integral, and topological-operator viewpoints.
- [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/) explains the separate distinction between connected transformations and disconnected or finite transformations.
- The later page on symmetry groups and representations will develop the representation-theoretic language used for spin, flavor, and multiplets.
- The later chapter on Noether currents and Ward identities derives internal currents and stress-tensor currents from continuous symmetries.
- The later chapter on background fields and gauging explains why internal symmetries couple to background gauge fields while spacetime symmetries couple to geometry.

## Research status

The internal–spacetime distinction is settled for ordinary relativistic QFT on fixed Minkowski spacetime. It is part of the standard representation theory of the Poincaré group and the standard construction of currents, stress tensors, and Ward identities.

Several frontiers complicate the clean picture. Supersymmetry extends spacetime symmetry by fermionic generators. Conformal symmetry replaces the Poincaré group by a larger spacetime group. Subsystem and fractonic symmetries can act on lower-dimensional spatial leaves rather than on all spacetime uniformly. Non-invertible topological defects generalize internal symmetry actions. Quantum gravity is expected not to allow ordinary global internal symmetries, while spacetime symmetry itself may be emergent or asymptotic rather than exact.

For this volume, the practical rule remains: first decide whether the transformation moves spacetime support. Then decide whether it is global, gauge, higher-form, anomalous, broken, or emergent.

## Exercises

### Exercise 1: Classify the symmetry

Classify each transformation as internal, spacetime, gauge redundancy, or ambiguous without more information.

1. $\phi(x)\mapsto e^{i\alpha}\phi(x)$ for a complex scalar.
2. $\phi(x)\mapsto \phi(x-a)$ for a scalar.
3. $A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\lambda(x)$ in electrodynamics.
4. $\psi_{\alpha I}(x)\mapsto R_I{}^J\psi_{\alpha J}(x)$.
5. $\psi_\alpha(x)\mapsto S(\Lambda)_\alpha{}^\beta\psi_\beta(\Lambda^{-1}x)$.

<details>
<summary><strong>Solution</strong></summary>

1. Internal. It changes the phase of the field at fixed $x$.
2. Spacetime. It translates the argument of the field.
3. Gauge redundancy, not an ordinary global symmetry. Special boundary conditions or large transformations may leave genuine global remnants, but that requires more information.
4. Internal. It rotates the flavor index $I$ at fixed $x$.
5. Spacetime. It moves $x$ and rotates the spinor index.

</details>

### Exercise 2: Commutator with momentum

Suppose $Q$ generates an internal $U(1)$ symmetry and commutes with translations, $[Q,P_\mu]=0$. If $|p,q\rangle$ is a simultaneous eigenstate of $P_\mu$ and $Q$, what are the momentum and charge of $Q|p,q\rangle$?

<details>
<summary><strong>Solution</strong></summary>

Since $Q|p,q\rangle=q|p,q\rangle$, the state $Q|p,q\rangle$ is proportional to $|p,q\rangle$ unless $q=0$, in which case it is zero. It has the same momentum because $[P_\mu,Q]=0$:

$$
P_\mu Q|p,q\rangle=Q P_\mu|p,q\rangle=p_\mu Q|p,q\rangle.
$$

For a nonabelian internal generator $Q_a$, acting with $Q_a$ can rotate a state within an internal multiplet, but it still does not change the spacetime momentum if $[Q_a,P_\mu]=0$.

</details>

### Exercise 3: Flavor versus Lorentz action

Let $\psi_{\alpha I}(x)$ carry a spinor index $\alpha$ and a flavor index $I$. Write the transformation under a flavor rotation $R$ and under a Lorentz transformation $\Lambda$.

<details>
<summary><strong>Solution</strong></summary>

A flavor rotation acts only on $I$:

$$
\psi_{\alpha I}(x)\mapsto R_I{}^J\psi_{\alpha J}(x).
$$

A Lorentz transformation acts on the spinor index and on the point:

$$
\psi_{\alpha I}(x)\mapsto S(\Lambda)_\alpha{}^\beta\psi_{\beta I}(\Lambda^{-1}x).
$$

The two actions can coexist and, for an ordinary internal symmetry in a relativistic QFT, commute with each other.

</details>

### Exercise 4: Why scaling dimension is not an internal charge

A scalar primary operator in a CFT transforms under dilatations as

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda^{-1}x).
$$

Explain why $\Delta$ should not be interpreted as an internal charge.

<details>
<summary><strong>Solution</strong></summary>

The transformation moves the point $x$. The factor $\lambda^{-\Delta}$ accompanies a spacetime rescaling, not a phase rotation at fixed $x$. Internal charges label how operators transform under symmetries that leave $x$ fixed. Scaling dimension labels the representation of the spacetime conformal group.

</details>

### Exercise 5: Current versus stress tensor

A theory has a conserved internal current $j^\mu$ and a conserved stress tensor $T^{\mu\nu}$. Which source should couple to each object?

<details>
<summary><strong>Solution</strong></summary>

An internal current couples to a background gauge field:

$$
\Delta S=\int d^dx A_\mu j^\mu.
$$

The stress tensor couples to the background metric:

$$
\delta S=(1/2)\int d^dx \sqrt{|g|} T^{\mu\nu}\delta g_{\mu\nu},
$$

up to the sign convention used to define $T^{\mu\nu}$. This reflects the difference between internal symmetry sources and spacetime geometry sources.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, Chapter 2. A foundational treatment of quantum symmetries, Poincaré transformations, one-particle states, antiunitary symmetries, and projective representations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on spacetime and internal symmetries. Useful for current algebra, charges, and the separation between spacetime and internal structures.
- Sidney Coleman, *Aspects of Symmetry*. Especially useful for symmetry, spontaneous breaking, scale symmetry, and the Coleman–Mandula viewpoint.
- Mark Srednicki, *Quantum Field Theory*, Sections 22–24 and 33–40. Useful for continuous, discrete, nonabelian, Lorentz, spinor, and discrete spacetime symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapters 8 and 10–12. Useful for Poincaré representations, spin, gauge invariance, and CPT-related discrete transformations.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. III, for supersymmetry as the graded extension of spacetime symmetry.

## Version history

- **2026-06-17:** Initial polished page distinguishing internal and spacetime symmetries, including operator conventions, current diagnostics, background sources, and Coleman–Mandula context.
