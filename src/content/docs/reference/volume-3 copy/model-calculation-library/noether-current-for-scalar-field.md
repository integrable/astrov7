---
title: "Noether Current for a Scalar Field"
description: "Model calculation deriving the Noether current of a complex scalar field with a global U(1) symmetry, with shift-symmetry and real-scalar variants."
sidebar:
  label: "Noether Current: Scalar Field"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §22; Coleman QFT Lectures chs. 5–6; Schwartz §3.3; Zee symmetry chapters."
topics:
  - Noether current
  - scalar field
  - U(1) symmetry
  - conserved charge
  - Ward identity preview
canonicalTopics:
  - noether-current
  - complex-scalar-field
  - global-u1-current
  - scalar-charge
researchStatus:
  established:
    - "The Noether current for a complex scalar field with a global U(1) symmetry is a standard textbook calculation."
  active:
    - "The physically invariant content is the charge action and Ward identity; current signs and source-coupling signs are convention-dependent."
---

## Summary

This page derives the Noether current for a complex scalar field with a global $U(1)$ symmetry. The result, in the convention used on this page, is

$$
j^\mu
=
iq\left(\phi^\dagger\partial^\mu\phi-\phi\,\partial^\mu\phi^\dagger\right),
$$

for the transformation

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger.
$$

On shell,

$$
\partial_\mu j^\mu=0.
$$

The conserved charge is

$$
Q=\int d^{d-1}\mathbf x\,j^0(t,\mathbf x).
$$

In canonical quantization this charge generates the field transformation:

$$
[Q,\phi(x)]=-q\phi(x),
\qquad
[Q,\phi^\dagger(x)]=q\phi^\dagger(x).
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![A flowchart of the scalar-field Noether-current derivation: choose global phase symmetry, promote the parameter to a local function, read off the coefficient of the derivative of the parameter, and obtain the conserved current.](/figures/symmetry-anomalies-topology/scalar-noether-current-flow.svg)

<figcaption>

Noether’s practical recipe for the complex scalar: promote the constant phase $\alpha$ to $\alpha(x)$, isolate the coefficient of $\partial_\mu\alpha$, and then set $\alpha$ constant again. Conservation follows from stationarity under arbitrary local test functions.

</figcaption>
</figure>

This is the simplest nontrivial current calculation in QFT. It is the template behind charge conservation, scalar QED couplings, current insertions in Ward identities, and the distinction between exact, explicitly broken, and anomalous symmetries.

## Prerequisites

You should know the Euler–Lagrange equations for fields, the meaning of a global internal symmetry, and the convention

$$
U(\alpha)=e^{-i\alpha Q},
\qquad
U(\alpha)^\dagger\mathcal O U(\alpha)
=
\mathcal O+\alpha\,i[Q,\mathcal O]+O(\alpha^2).
$$

For the calculation below, no path integrals are required. The path-integral and Ward-identity viewpoints are mentioned only as checks.

## Setup and conventions

Work in $d$-dimensional Minkowski spacetime with mostly-minus metric. Let

$$
\mathcal L
=
\partial_\mu\phi^\dagger\,\partial^\mu\phi
-
V(\phi^\dagger\phi).
$$

For the free massive complex scalar,

$$
V(\phi^\dagger\phi)=m^2\phi^\dagger\phi.
$$

For an interacting but $U(1)$-invariant scalar,

$$
V(\phi^\dagger\phi)=m^2\phi^\dagger\phi+\lambda(\phi^\dagger\phi)^2
$$

is a standard example.

The global symmetry is

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger,
$$

where $\alpha$ is constant. Infinitesimally,

$$
\delta\phi=-iq\alpha\,\phi,
\qquad
\delta\phi^\dagger=iq\alpha\,\phi^\dagger.
$$

:::note[Sign convention]
If you choose $\phi\mapsto e^{iq\alpha}\phi$ instead, the current displayed on this page flips sign. The conservation law and selection rules are unchanged once the charge convention is changed consistently.
:::

## Core idea

Noether’s theorem can be used in two equivalent ways.

The first way is to compute the canonical Noether current from the field variations:

$$
j^\mu
=
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\,\Delta\phi
+
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}\,\Delta\phi^\dagger,
$$

where $\delta\phi=\alpha\Delta\phi$ and $\delta\phi^\dagger=\alpha\Delta\phi^\dagger$.

The second way is often safer: promote $\alpha$ to a spacetime-dependent function $\alpha(x)$, keep only terms proportional to $\partial_\mu\alpha$, and read off the current. For an exact global symmetry,

$$
\delta\mathcal L=(\partial_\mu\alpha)j^\mu+\alpha\times(\mathrm{equations\ of\ motion}).
$$

Since $\alpha(x)$ is arbitrary, stationarity of the action gives $\partial_\mu j^\mu=0$ on shell.

The local-parameter method is the better habit. It directly anticipates Ward identities, background fields, and anomalies.

## Step 1: Check the global symmetry

Under the infinitesimal transformation,

$$
\delta(\phi^\dagger\phi)
=
(\delta\phi^\dagger)\phi+\phi^\dagger(\delta\phi)
=
iq\alpha\,\phi^\dagger\phi
-
iq\alpha\,\phi^\dagger\phi
=0.
$$

Thus the potential $V(\phi^\dagger\phi)$ is invariant.

For constant $\alpha$,

$$
\delta(\partial_\mu\phi)=-iq\alpha\,\partial_\mu\phi,
\qquad
\delta(\partial_\mu\phi^\dagger)=iq\alpha\,\partial_\mu\phi^\dagger.
$$

Therefore

$$
\delta\left(\partial_\mu\phi^\dagger\,\partial^\mu\phi\right)
=
iq\alpha\,\partial_\mu\phi^\dagger\partial^\mu\phi
-
iq\alpha\,\partial_\mu\phi^\dagger\partial^\mu\phi
=0.
$$

So $\delta\mathcal L=0$ for constant $\alpha$. The transformation is a genuine classical global symmetry.

## Step 2: Promote the parameter to a function

Now take $\alpha=\alpha(x)$ but do not claim this is a new symmetry. It is a diagnostic trick.

The variations become

$$
\delta\phi=-iq\alpha(x)\phi,
\qquad
\delta\phi^\dagger=iq\alpha(x)\phi^\dagger.
$$

Differentiating gives

$$
\delta(\partial_\mu\phi)
=
-iq(\partial_\mu\alpha)\phi
-
iq\alpha\,\partial_\mu\phi,
$$

and

$$
\delta(\partial_\mu\phi^\dagger)
=
iq(\partial_\mu\alpha)\phi^\dagger
+
iq\alpha\,\partial_\mu\phi^\dagger.
$$

The terms proportional to $\alpha$ cancel as before. The terms proportional to $\partial_\mu\alpha$ are the Noether-current terms.

## Step 3: Read off the current

Vary the kinetic term:

$$
\delta\mathcal L
=
\delta(\partial_\mu\phi^\dagger)\partial^\mu\phi
+
\partial_\mu\phi^\dagger\,\delta(\partial^\mu\phi)
$$

up to the terms that cancel for constant $\alpha$. Keeping only $\partial_\mu\alpha$ terms,

$$
\delta\mathcal L
=
iq(\partial_\mu\alpha)\phi^\dagger\partial^\mu\phi
-
iq(\partial_\mu\alpha)\phi\,\partial^\mu\phi^\dagger.
$$

Thus

$$
\delta\mathcal L=(\partial_\mu\alpha)j^\mu,
$$

with

$$
j^\mu
=
iq\left(\phi^\dagger\partial^\mu\phi-\phi\,\partial^\mu\phi^\dagger\right).
$$

This is the desired current.

The same answer follows from the canonical Noether formula. Since

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi^\dagger,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}=\partial^\mu\phi,
$$

and

$$
\Delta\phi=-iq\phi,
\qquad
\Delta\phi^\dagger=iq\phi^\dagger,
$$

we get

$$
j^\mu
=
\partial^\mu\phi^\dagger(-iq\phi)
+
\partial^\mu\phi(iq\phi^\dagger)
=
iq\left(\phi^\dagger\partial^\mu\phi-\phi\,\partial^\mu\phi^\dagger\right).
$$

## Step 4: Check conservation directly

The Euler–Lagrange equations are

$$
\partial_\mu\partial^\mu\phi+V'(\phi^\dagger\phi)\phi=0,
$$

and

$$
\partial_\mu\partial^\mu\phi^\dagger+V'(\phi^\dagger\phi)\phi^\dagger=0,
$$

where $V'$ denotes the derivative of $V(r)$ with respect to $r=\phi^\dagger\phi$.

Now compute

$$
\partial_\mu j^\mu
=
iq\left[
\partial_\mu\phi^\dagger\partial^\mu\phi
+
\phi^\dagger\partial_\mu\partial^\mu\phi
-
\partial_\mu\phi\,\partial^\mu\phi^\dagger
-
\phi\,\partial_\mu\partial^\mu\phi^\dagger
\right].
$$

The first and third terms cancel. Using the equations of motion,

$$
\phi^\dagger\partial_\mu\partial^\mu\phi
=
-V'(\phi^\dagger\phi)\phi^\dagger\phi,
$$

and

$$
\phi\,\partial_\mu\partial^\mu\phi^\dagger
=
-V'(\phi^\dagger\phi)\phi\phi^\dagger.
$$

These are equal, so their difference vanishes. Hence

$$
\partial_\mu j^\mu=0.
$$

This direct check is worth doing at least once. It shows explicitly that conservation depends on the $U(1)$-invariant form of the potential.

## Charge density and canonical generator

The canonical momenta are

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi^\dagger,
\qquad
\pi^\dagger=\frac{\partial\mathcal L}{\partial\dot\phi^\dagger}=\dot\phi.
$$

The charge density is

$$
j^0=iq(\phi^\dagger\pi^\dagger-\phi\pi).
$$

Therefore

$$
Q=iq\int d^{d-1}\mathbf x\,
(\phi^\dagger\pi^\dagger-\phi\pi).
$$

Using the equal-time commutators

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=
i\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

and

$$
[\phi^\dagger(t,\mathbf x),\pi^\dagger(t,\mathbf y)]
=
i\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

one obtains

$$
[Q,\phi(t,\mathbf x)]=-q\phi(t,\mathbf x),
$$

and

$$
[Q,\phi^\dagger(t,\mathbf x)]=q\phi^\dagger(t,\mathbf x).
$$

Thus

$$
U(\alpha)^\dagger\phi U(\alpha)
=
e^{-iq\alpha}\phi,
\qquad
U(\alpha)=e^{-i\alpha Q},
$$

as required.

## Background-field check

A useful cross-check is to couple the scalar to a nondynamical background gauge field. With the convention

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

the transformation

$$
\phi\mapsto e^{-iq\lambda}\phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\lambda
$$

makes $D_\mu\phi$ transform covariantly.

The kinetic term becomes

$$
(D_\mu\phi)^\dagger D^\mu\phi.
$$

Expanding to first order in $A_\mu$ gives

$$
(D_\mu\phi)^\dagger D^\mu\phi
=
\partial_\mu\phi^\dagger\partial^\mu\phi
-
A_\mu j^\mu
+
O(A^2).
$$

So in this convention the source term is $-A_\mu j^\mu$. If instead you define the source coupling as $+A_\mu j^\mu$, then your covariant derivative or current sign must be adjusted. This is a convention issue, not a physics issue.

:::note[Source note]
The Noether current sign is tied to the phase convention for charged fields and to the background-field convention. Always compare the transformation rule and the source coupling together.
:::

## Real-scalar shift current

A real scalar with a potential $V(\varphi)$ has no phase rotation. But a free massless real scalar,

$$
\mathcal L=\frac12\partial_\mu\varphi\,\partial^\mu\varphi,
$$

has a shift symmetry

$$
\varphi\mapsto\varphi+a,
$$

where $a$ is constant. Taking $a=a(x)$,

$$
\delta\mathcal L
=
\partial_\mu\varphi\,\partial^\mu a
=
(\partial_\mu a)\partial^\mu\varphi.
$$

The Noether current is therefore

$$
j^\mu_{\mathrm{shift}}=\partial^\mu\varphi.
$$

Conservation gives

$$
\partial_\mu j^\mu_{\mathrm{shift}}
=
\partial_\mu\partial^\mu\varphi
=0,
$$

which is just the massless equation of motion.

A mass term breaks the shift symmetry explicitly:

$$
\mathcal L=\frac12\partial_\mu\varphi\partial^\mu\varphi-\frac12m^2\varphi^2
$$

is not invariant under $\varphi\mapsto\varphi+a$.

## Ward identity preview

In the quantum theory, the same current appears in Ward identities. For an operator $\mathcal O_q$ of charge $q$,

$$
[Q,\mathcal O_q]=-q\mathcal O_q
$$

in the field convention used here. Current conservation inside correlation functions therefore has contact terms:

$$
\partial_\mu
\langle T j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
i\sum_k q_k\,\delta^{(d)}(x-x_k)
\langle T\mathcal O_1\cdots\mathcal O_n\rangle,
$$

up to the standard time-ordering and convention details. Integrating over $x$ gives the selection rule that total charge must vanish in a symmetric vacuum.

The Ward-identity chapter derives this carefully. Here the point is that the local current calculated above is the operator that enforces charge conservation.

## Common pitfalls

**Flipping the current sign without flipping the field transformation.** If $\phi\mapsto e^{iq\alpha}\phi$ instead of $e^{-iq\alpha}\phi$, the current changes sign.

**Forgetting that $\phi$ and $\phi^\dagger$ are independent variables in the variation.** In the Lagrangian derivation, vary them independently and impose conjugation only after the calculation.

**Calling every complex scalar current “particle number.”** The conserved charge is a $U(1)$ charge. Whether it is particle number, electric charge, flavor number, or something else depends on the model.

**Using the free equation of motion for an interacting theory.** Conservation still holds for $V(\phi^\dagger\phi)$, but the equation of motion includes $V'(\phi^\dagger\phi)$.

**Confusing background gauge invariance with dynamical gauging.** Coupling to $A_\mu$ as a source probes the global symmetry. Making $A_\mu$ dynamical is a new gauge theory.

## Relations to other pages

This calculation is the scalar-field model for the Noether Currents and Ward Identities chapter. It also prepares for scalar QED, background fields for global symmetries, selection rules, and spontaneous symmetry breaking.

The Dirac-field calculation is the spinor analogue. The Ward identity in QED is the gauge-theory cousin, where the current couples to a dynamical photon and gauge redundancy enters.

## Research status

This calculation is fully standard. The only subtlety is convention management: current signs, source-coupling signs, and charge conventions vary across textbooks. In interacting and gauge theories, additional subtleties arise from operator renormalization, improvement terms, background fields, and anomalies.

## Exercises

### Exercise 1: Current for a general invariant potential

Show that the current

$$
j^\mu=iq(\phi^\dagger\partial^\mu\phi-\phi\,\partial^\mu\phi^\dagger)
$$

is conserved for any potential $V(\phi^\dagger\phi)$.

<details><summary><strong>Solution</strong></summary>

The equations of motion are

$$
\partial_\mu\partial^\mu\phi+V'(\phi^\dagger\phi)\phi=0,
$$

and

$$
\partial_\mu\partial^\mu\phi^\dagger+V'(\phi^\dagger\phi)\phi^\dagger=0.
$$

The divergence is

$$
\partial_\mu j^\mu
=
iq\left(
\phi^\dagger\partial_\mu\partial^\mu\phi
-
\phi\partial_\mu\partial^\mu\phi^\dagger
\right),
$$

after canceling the derivative-product terms. Substituting the equations of motion gives

$$
iq\left(
-\phi^\dagger V'\phi+\phi V'\phi^\dagger
\right)=0.
$$

</details>

### Exercise 2: Explicit breaking

Add

$$
\Delta\mathcal L=-\frac{\epsilon}{2}(\phi^2+\phi^{\dagger 2}).
$$

Compute the nonzero divergence of the $U(1)$ current to first order in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

Under the infinitesimal transformation,

$$
\delta\phi=-iq\alpha\phi,
\qquad
\delta\phi^\dagger=iq\alpha\phi^\dagger.
$$

The variation of the breaking term is

$$
\delta\Delta\mathcal L
=
-\frac{\epsilon}{2}
\left(
2\phi\,\delta\phi+2\phi^\dagger\,\delta\phi^\dagger
\right)
=
iq\epsilon\alpha(\phi^2-\phi^{\dagger 2}).
$$

For an explicitly broken symmetry,

$$
\delta\mathcal L=-\alpha\,\partial_\mu j^\mu
$$

on shell. Therefore

$$
\partial_\mu j^\mu
=
-iq\epsilon(\phi^2-\phi^{\dagger 2}).
$$

The current is conserved only when $\epsilon=0$ or when the remaining discrete subgroup is used instead of the full $U(1)$.

</details>

### Exercise 3: Shift-current breaking

For a real scalar with

$$
\mathcal L=\frac12\partial_\mu\varphi\partial^\mu\varphi-\frac12m^2\varphi^2,
$$

show that the shift current $j^\mu=\partial^\mu\varphi$ is not conserved.

<details><summary><strong>Solution</strong></summary>

The equation of motion is

$$
\partial_\mu\partial^\mu\varphi+m^2\varphi=0.
$$

Thus

$$
\partial_\mu j^\mu
=
\partial_\mu\partial^\mu\varphi
=
-m^2\varphi.
$$

The mass term explicitly breaks the shift symmetry.

</details>

### Exercise 4: Source-coupling sign

Using $D_\mu=\partial_\mu+iqA_\mu$, expand $(D_\mu\phi)^\dagger D^\mu\phi$ to first order in $A_\mu$ and verify that the linear term is $-A_\mu j^\mu$ with the current convention of this page.

<details><summary><strong>Solution</strong></summary>

We have

$$
D_\mu\phi=\partial_\mu\phi+iqA_\mu\phi,
$$

and

$$
(D_\mu\phi)^\dagger=\partial_\mu\phi^\dagger-iqA_\mu\phi^\dagger.
$$

Multiplying and keeping terms linear in $A_\mu$,

$$
(D_\mu\phi)^\dagger D^\mu\phi
=
\partial_\mu\phi^\dagger\partial^\mu\phi
+
iqA^\mu\partial_\mu\phi^\dagger\phi
-
iqA_\mu\phi^\dagger\partial^\mu\phi
+
O(A^2).
$$

This equals

$$
\partial_\mu\phi^\dagger\partial^\mu\phi
-
A_\mu\,iq(\phi^\dagger\partial^\mu\phi-\phi\partial^\mu\phi^\dagger)
+
O(A^2),
$$

so the linear term is $-A_\mu j^\mu$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §22.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 5–6.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §3.3.
- A. Zee, *Quantum Field Theory in a Nutshell*, symmetry and Noether-current discussions.

## Version history

- 2026-06-17: Initial polished model calculation. Added local-parameter derivation, direct conservation check, canonical generator check, background-field sign check, shift-current variant, and exercises.
