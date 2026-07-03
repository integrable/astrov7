---
title: "Noether Current for a Dirac Field"
description: "Model calculation deriving the vector and axial Noether currents of the Dirac field, with sign conventions, mass breaking, and anomaly preview."
sidebar:
  label: "Noether Current: Dirac Field"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§22, 36, 40, 75–77; Coleman QFT Lectures chs. 5–6; Schwartz chs. 10, 14, 30."
topics:
  - Noether current
  - Dirac field
  - vector current
  - axial current
  - chiral symmetry
  - anomaly preview
canonicalTopics:
  - noether-current
  - dirac-current
  - vector-current
  - axial-current
  - chiral-symmetry
researchStatus:
  established:
    - "The vector Noether current of a Dirac field is a standard textbook calculation, and the axial current is classically conserved only in the massless theory."
  active:
    - "The axial current is the gateway to anomaly calculations, where regulator and measure choices become physical."
---

## Summary

This page derives the Noether currents of a Dirac field. For a Dirac fermion of charge $q$ with Lagrangian

$$
\mathcal L
=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi,
$$

the global vector symmetry

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto \overline\psi\,e^{iq\alpha}
$$

has Noether current

$$
j^\mu=q\,\overline\psi\gamma^\mu\psi.
$$

Classically,

$$
\partial_\mu j^\mu=0.
$$

For a massless Dirac fermion, there is also an axial symmetry

$$
\psi\mapsto e^{-i\beta\gamma^5}\psi,
\qquad
\overline\psi\mapsto \overline\psi\,e^{-i\beta\gamma^5},
$$

with current

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

Classically,

$$
\partial_\mu j_5^\mu=2im\,\overline\psi\gamma^5\psi,
$$

so $j_5^\mu$ is conserved only when $m=0$. Quantum mechanically, even the massless axial symmetry can be anomalous after coupling to gauge fields.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A flowchart of Dirac Noether currents showing vector phase symmetry leading to the conserved vector current and axial chiral rotation leading to the axial current, with mass breaking and anomaly preview.](/figures/symmetry-anomalies-topology/dirac-noether-current-flow.svg)

<figcaption>

The Dirac field has two basic current calculations. The vector phase rotation gives the conserved charge current. The axial rotation gives a classically conserved current only in the massless theory, and becomes the canonical doorway to anomaly physics after quantization.

</figcaption>
</figure>

## Prerequisites

You should know the Dirac adjoint

$$
\overline\psi=\psi^\dagger\gamma^0,
$$

the Dirac equation, and the gamma-matrix conventions

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu},
\qquad
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

Slash notation is written as $p\!\!\!/\equiv\gamma^\mu p_\mu$. The page uses mostly-minus metric and the active symmetry convention

$$
U(\alpha)=e^{-i\alpha Q},
\qquad
\delta\mathcal O=i\alpha[Q,\mathcal O].
$$

## Setup and conventions

The Dirac Lagrangian is

$$
\mathcal L
=
i\overline\psi\gamma^\mu\partial_\mu\psi
-
m\overline\psi\psi.
$$

In deriving Noether currents, treat $\psi$ and $\overline\psi$ as independent fields. Since the Lagrangian contains derivatives of $\psi$ but not derivatives of $\overline\psi$, the canonical Noether formula contains

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\psi)}
=
i\overline\psi\gamma^\mu.
$$

The equation of motion from varying $\overline\psi$ is

$$
(i\gamma^\mu\partial_\mu-m)\psi=0.
$$

The adjoint equation is

$$
i(\partial_\mu\overline\psi)\gamma^\mu+m\overline\psi=0.
$$

Equivalently,

$$
(\partial_\mu\overline\psi)\gamma^\mu
=
im\overline\psi.
$$

:::note[Grassmann caveat]
In a path-integral derivation, $\psi$ and $\overline\psi$ are Grassmann-valued. The current formulas are the same, but one must be consistent about left and right derivatives. This page suppresses that bookkeeping because the symmetry result is standard and unambiguous once conventions are fixed.
:::

## Vector symmetry

The global vector symmetry is

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto\overline\psi e^{iq\alpha}.
$$

Infinitesimally,

$$
\delta\psi=-iq\alpha\psi,
\qquad
\delta\overline\psi=iq\alpha\overline\psi.
$$

The mass term is invariant:

$$
\delta(\overline\psi\psi)
=
(\delta\overline\psi)\psi+\overline\psi(\delta\psi)
=
iq\alpha\overline\psi\psi-iq\alpha\overline\psi\psi
=0.
$$

For constant $\alpha$, the kinetic term is also invariant. Therefore the transformation is a classical global symmetry.

## Local-parameter derivation of the vector current

Promote $\alpha$ to $\alpha(x)$. Then

$$
\delta(\partial_\mu\psi)
=
-iq(\partial_\mu\alpha)\psi
-
iq\alpha\,\partial_\mu\psi.
$$

Only the first term is new relative to the global symmetry. The variation of the kinetic term contains

$$
\delta\mathcal L
=
i\overline\psi\gamma^\mu\delta(\partial_\mu\psi)
+
\text{terms present for constant }\alpha.
$$

The constant-$\alpha$ terms cancel. Therefore

$$
\delta\mathcal L
=
i\overline\psi\gamma^\mu
\left[-iq(\partial_\mu\alpha)\psi\right]
=
q(\partial_\mu\alpha)\overline\psi\gamma^\mu\psi.
$$

Thus

$$
\delta\mathcal L=(\partial_\mu\alpha)j^\mu,
$$

with

$$
j^\mu=q\,\overline\psi\gamma^\mu\psi.
$$

This is the vector current.

## Canonical Noether formula

The same result follows directly from

$$
j^\mu
=
\frac{\partial\mathcal L}{\partial(\partial_\mu\psi)}\Delta\psi,
$$

where

$$
\delta\psi=\alpha\Delta\psi,
\qquad
\Delta\psi=-iq\psi.
$$

Using

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\psi)}
=
i\overline\psi\gamma^\mu,
$$

we find

$$
j^\mu
=
i\overline\psi\gamma^\mu(-iq\psi)
=
q\overline\psi\gamma^\mu\psi.
$$

There is no separate derivative term from $\overline\psi$ because the Lagrangian has no $\partial_\mu\overline\psi$. If one first integrates the Lagrangian by parts into a symmetrized form, the same current is obtained up to improvement terms and equations of motion.

## Direct conservation check

Compute

$$
\partial_\mu j^\mu
=
q(\partial_\mu\overline\psi)\gamma^\mu\psi
+
q\overline\psi\gamma^\mu\partial_\mu\psi.
$$

Using the adjoint equation,

$$
(\partial_\mu\overline\psi)\gamma^\mu=im\overline\psi,
$$

so the first term is

$$
iqm\overline\psi\psi.
$$

Using the Dirac equation,

$$
\gamma^\mu\partial_\mu\psi=-im\psi,
$$

so the second term is

$$
-iqm\overline\psi\psi.
$$

They cancel:

$$
\partial_\mu j^\mu=0.
$$

The vector current is conserved for any mass $m$ because the mass term respects the vector $U(1)$ symmetry.

## Charge and field action

The charge is

$$
Q=\int d^{d-1}\mathbf x\,j^0
=
q\int d^{d-1}\mathbf x\,\psi^\dagger\psi.
$$

In canonical quantization, $Q$ counts particles with charge $q$ and antiparticles with charge $-q$. With the convention used here,

$$
[Q,\psi(x)]=-q\psi(x),
$$

and

$$
[Q,\overline\psi(x)]=q\overline\psi(x).
$$

Thus

$$
U(\alpha)^\dagger\psi U(\alpha)=e^{-iq\alpha}\psi,
\qquad
U(\alpha)^\dagger\overline\psi U(\alpha)=\overline\psi e^{iq\alpha}.
$$

The charge density is positive for particles created by the particle creation operators appearing in the mode expansion, while antiparticles have opposite charge. The field $\psi$ itself contains both particle annihilation and antiparticle creation pieces, so its transformation law is a compact representation statement rather than a statement that every term in $\psi$ carries the same physical excitation charge.

## Background-field check

Using the covariant derivative

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

the minimally coupled Lagrangian is

$$
\mathcal L
=
\overline\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding,

$$
i\overline\psi\gamma^\mu D_\mu\psi
=
i\overline\psi\gamma^\mu\partial_\mu\psi
-
qA_\mu\overline\psi\gamma^\mu\psi.
$$

Therefore

$$
\mathcal L[A]
=
\mathcal L[0]-A_\mu j^\mu.
$$

With this convention, the source coefficient is $-j^\mu$. Some authors define the current by $\delta S/\delta A_\mu$ and therefore absorb this sign differently. The invariant content is the gauge-covariant derivative, field transformation, and charge action taken together.

## Axial symmetry

Now consider the axial rotation

$$
\psi\mapsto e^{-i\beta\gamma^5}\psi,
\qquad
\overline\psi\mapsto\overline\psi e^{-i\beta\gamma^5}.
$$

The same sign appears in the transformation of $\overline\psi$ because $\gamma^5$ anticommutes with $\gamma^0$.

Infinitesimally,

$$
\delta\psi=-i\beta\gamma^5\psi,
\qquad
\delta\overline\psi=-i\beta\overline\psi\gamma^5.
$$

The kinetic term is invariant for constant $\beta$ because

$$
\{\gamma^5,\gamma^\mu\}=0.
$$

The mass term is not invariant:

$$
\delta(\overline\psi\psi)
=
-2i\beta\,\overline\psi\gamma^5\psi.
$$

So the axial symmetry is exact only when $m=0$.

## Axial current derivation

Promote $\beta$ to $\beta(x)$. The derivative term gives

$$
\delta(\partial_\mu\psi)
=
-i(\partial_\mu\beta)\gamma^5\psi
-
i\beta\gamma^5\partial_\mu\psi.
$$

The local part of the kinetic variation is

$$
i\overline\psi\gamma^\mu
\left[-i(\partial_\mu\beta)\gamma^5\psi\right]
=
(\partial_\mu\beta)\overline\psi\gamma^\mu\gamma^5\psi.
$$

Thus the axial current is

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

The mass variation gives

$$
\delta(-m\overline\psi\psi)
=
2im\beta\,\overline\psi\gamma^5\psi.
$$

On shell,

$$
\delta\mathcal L
=
(\partial_\mu\beta)j_5^\mu
+
2im\beta\,\overline\psi\gamma^5\psi.
$$

Integrating the first term by parts and using arbitrary $\beta(x)$ gives

$$
\partial_\mu j_5^\mu
=
2im\overline\psi\gamma^5\psi.
$$

Therefore $j_5^\mu$ is classically conserved only in the massless theory.

## Left and right currents

Use the chiral projectors

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

Define

$$
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi.
$$

The vector and axial currents can be written as

$$
j^\mu=\overline\psi\gamma^\mu\psi
=
\overline\psi_L\gamma^\mu\psi_L
+
\overline\psi_R\gamma^\mu\psi_R,
$$

and

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi
=
-\overline\psi_L\gamma^\mu\psi_L
+
\overline\psi_R\gamma^\mu\psi_R.
$$

Equivalently,

$$
j_R^\mu=\overline\psi_R\gamma^\mu\psi_R,
\qquad
j_L^\mu=\overline\psi_L\gamma^\mu\psi_L,
$$

so

$$
j^\mu=j_R^\mu+j_L^\mu,
\qquad
j_5^\mu=j_R^\mu-j_L^\mu.
$$

For $m=0$, left and right components decouple classically, producing a larger chiral symmetry. Mass terms couple left and right components and break the axial part.

## Quantum anomaly preview

For a Dirac fermion coupled to a background or dynamical Abelian gauge field, the axial current equation becomes

$$
\partial_\mu j_5^\mu
=
2im\overline\psi\gamma^5\psi
+
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

in the convention used in the anomaly chapter.

The vector current remains conserved in a consistent vectorlike theory. The axial current fails because no regulator can preserve all the desired symmetries simultaneously. Fujikawa’s method attributes the effect to the path-integral measure. Triangle-diagram methods attribute it to the regulated current insertion.

This page does not derive the anomaly. It prepares the classical current whose quantum nonconservation becomes the anomaly.

:::caution[Classical versus quantum conservation]
The equation $\partial_\mu j_5^\mu=0$ for a massless free Dirac field is a classical or formal operator statement before regularization. After coupling to gauge fields, the quantum theory can modify it by an anomaly term.
:::

## Common pitfalls

**Using the same sign for vector and axial adjoint transformations.** For vector rotations, $\overline\psi$ transforms with the opposite phase. For axial rotations, $\overline\psi$ transforms with the same $\gamma^5$ sign because of the anticommutation with $\gamma^0$.

**Forgetting the factor of $i$ in the Dirac Lagrangian.** The current sign follows from $i\overline\psi\gamma^\mu\partial_\mu\psi$.

**Assuming the axial current is always conserved when $m=0$.** It is classically conserved for the free massless theory, but gauge couplings can produce an anomaly.

**Confusing vectorlike and chiral symmetries.** A Dirac mass preserves the vector $U(1)$ but breaks axial $U(1)$.

**Ignoring regulator dependence.** The vector current can be preserved by a gauge-invariant regulator in vectorlike QED. The axial current cannot be preserved simultaneously with all the same requirements.

## Relations to other pages

This calculation is the spinor counterpart of the scalar-field Noether current. It feeds directly into Ward identities, QED current conservation, chiral symmetry, axial anomalies, anomaly matching, and Standard Model anomaly cancellation.

The axial-current part is a prerequisite for the ABJ anomaly triangle and Fujikawa chiral Jacobian pages in this model calculation library.

## Research status

The vector and axial current derivations are standard. The subtle physics begins when these currents are inserted into a regulated quantum theory. Vector-current conservation is a consistency requirement for a gauged vector symmetry. Axial-current nonconservation is a physical anomaly with consequences for pion decay, instantons, chiral symmetry, and anomaly matching.

## Exercises

### Exercise 1: Vector current conservation

Starting from

$$
j^\mu=q\overline\psi\gamma^\mu\psi,
$$

use the Dirac equation and adjoint Dirac equation to show $\partial_\mu j^\mu=0$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu
=
q(\partial_\mu\overline\psi)\gamma^\mu\psi
+
q\overline\psi\gamma^\mu\partial_\mu\psi.
$$

The adjoint equation gives

$$
(\partial_\mu\overline\psi)\gamma^\mu=im\overline\psi,
$$

and the Dirac equation gives

$$
\gamma^\mu\partial_\mu\psi=-im\psi.
$$

Thus

$$
\partial_\mu j^\mu
=
iqm\overline\psi\psi
-
iqm\overline\psi\psi
=0.
$$

</details>

### Exercise 2: Mass breaking of axial symmetry

Show that the Dirac mass term is not invariant under

$$
\psi\mapsto e^{-i\beta\gamma^5}\psi.
$$

<details><summary><strong>Solution</strong></summary>

Infinitesimally,

$$
\delta\psi=-i\beta\gamma^5\psi,
\qquad
\delta\overline\psi=-i\beta\overline\psi\gamma^5.
$$

Therefore

$$
\delta(\overline\psi\psi)
=
-2i\beta\overline\psi\gamma^5\psi.
$$

The mass term varies as

$$
\delta(-m\overline\psi\psi)
=
2im\beta\overline\psi\gamma^5\psi.
$$

It is invariant only if $m=0$ or if the transformation parameter is trivial.

</details>

### Exercise 3: Chiral currents

Using $P_L=(1-\gamma^5)/2$ and $P_R=(1+\gamma^5)/2$, show that

$$
j^\mu=j_R^\mu+j_L^\mu,
\qquad
j_5^\mu=j_R^\mu-j_L^\mu.
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
j_R^\mu=\overline\psi_R\gamma^\mu\psi_R,
\qquad
j_L^\mu=\overline\psi_L\gamma^\mu\psi_L.
$$

Because $\gamma^\mu$ flips chirality in the bilinear pairing with the Dirac adjoint, the vector current decomposes into the sum of right and left chiral currents. Since $\gamma^5\psi_R=\psi_R$ and $\gamma^5\psi_L=-\psi_L$, the axial current weights the two pieces with opposite signs:

$$
j_5^\mu=j_R^\mu-j_L^\mu.
$$

</details>

### Exercise 4: Source-coupling sign

With $D_\mu=\partial_\mu+iqA_\mu$, show that the minimally coupled Dirac Lagrangian contains $-A_\mu j^\mu$.

<details><summary><strong>Solution</strong></summary>

The kinetic term becomes

$$
i\overline\psi\gamma^\mu D_\mu\psi
=
i\overline\psi\gamma^\mu\partial_\mu\psi
+
i\overline\psi\gamma^\mu(iqA_\mu\psi).
$$

The second term is

$$
-qA_\mu\overline\psi\gamma^\mu\psi
=
-A_\mu j^\mu.
$$

Thus the source coefficient is $-j^\mu$ with this covariant-derivative convention.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§22, 36, 40, 75–77.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 10, 14, and 30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 5, and Vol. II anomaly chapters.
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*.

## Version history

- 2026-06-17: Initial polished model calculation. Added vector current derivation, canonical charge check, axial current derivation, chiral-current decomposition, anomaly preview, and exercises.
