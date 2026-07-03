---
title: "Hamiltonian Field Theory"
description: "Canonical momenta, Hamiltonian density, equal-time Poisson brackets, Hamilton's equations for fields, and the bridge from classical fields to canonical quantization."
sidebar:
  label: "Hamiltonian Field Theory"
  order: 5
level: Graduate
status: "Polished draft"
topics:
  - Hamiltonian field theory
  - canonical momentum
  - Poisson bracket
  - canonical quantization
  - Legendre transform
canonicalTopics:
  - hamiltonian-field-theory
  - canonical-momentum-density
  - equal-time-poisson-bracket
---

## Summary

Hamiltonian field theory rewrites classical field dynamics as time evolution on an infinite-dimensional phase space. On a fixed time slice, the canonical variables are

$$
\phi^A(t,\mathbf x),
\qquad
\pi_A(t,\mathbf x)=\frac{\partial\mathcal L}{\partial\dot\phi^A}(t,\mathbf x).
$$

When the Legendre transform is nonsingular, the Hamiltonian density is

$$
\boxed{\mathcal H=\pi_A\dot\phi^A-\mathcal L,}
$$

with velocities eliminated in favor of $\phi^A$ and $\pi_A$. The Hamiltonian is

$$
H=\int d^3\mathbf x\,\mathcal H.
$$

The equal-time Poisson bracket is

$$
\boxed{
\{F,G\}=\int d^3\mathbf z
\left(\frac{\delta F}{\delta\phi^A(\mathbf z)}\frac{\delta G}{\delta\pi_A(\mathbf z)}-
\frac{\delta F}{\delta\pi_A(\mathbf z)}\frac{\delta G}{\delta\phi^A(\mathbf z)}\right),
}
$$

so

$$
\boxed{
\{\phi^A(t,\mathbf x),\pi_B(t,\mathbf y)\}=\delta^A{}_B\delta^{(3)}(\mathbf x-\mathbf y).
}
$$

Hamilton's equations are

$$
\boxed{
\dot\phi^A=\frac{\delta H}{\delta\pi_A},
\qquad
\dot\pi_A=-\frac{\delta H}{\delta\phi^A}.
}
$$

This is the classical launchpad for canonical quantization.

## Why use the Hamiltonian formalism?

The Lagrangian formalism is spacetime-friendly: locality, Lorentz invariance, and symmetries are visible. The Hamiltonian formalism is time-evolution-friendly: it asks which data on a spatial slice determine the future.

The dictionary from mechanics to field theory is direct:

| Mechanics | Field theory |
|---|---|
| coordinate $q^a(t)$ | field value $\phi^A(t,\mathbf x)$ |
| momentum $p_a$ | momentum density $\pi_A(t,\mathbf x)$ |
| finite sum over $a$ | spatial integral over $\mathbf x$ and sum over $A$ |
| partial derivative | functional derivative |
| $\{q^a,p_b\}=\delta^a{}_b$ | $\{\phi^A(\mathbf x),\pi_B(\mathbf y)\}=\delta^A{}_B\delta^{(3)}(\mathbf x-\mathbf y)$ |

The spatial coordinate $\mathbf x$ labels a field degree of freedom. It is not the position of a particle.

## Canonical momenta and the Legendre map

For

$$
\mathcal L=\mathcal L(\phi^A,\dot\phi^A,\partial_i\phi^A),
$$

define

$$
\boxed{\pi_A=\frac{\partial\mathcal L}{\partial\dot\phi^A}.}
$$

The velocity–momentum relation is regular if the Hessian

$$
W_{AB}=\frac{\partial^2\mathcal L}{\partial\dot\phi^A\partial\dot\phi^B}
$$

is invertible. Then the velocities can be solved as

$$
\dot\phi^A=\dot\phi^A(\phi,\pi,\partial_i\phi).
$$

If $W_{AB}$ is singular, the momenta obey constraints. Gauge theories and first-order fermionic systems are the most important examples. This is why the next page exists.

## Hamiltonian density

For a regular theory,

$$
\mathcal H=\pi_A\dot\phi^A-\mathcal L,
$$

but the final expression must be written in canonical variables:

$$
\mathcal H=\mathcal H(\phi,\pi,\partial_i\phi).
$$

The canonical stress tensor gives the same object as the time-translation density:

$$
T^0{}_0
=\frac{\partial\mathcal L}{\partial\dot\phi^A}\dot\phi^A-\mathcal L
=\mathcal H.
$$

Thus, for ordinary constant-time slices,

$$
H=P_0=\int d^3\mathbf x\,T^0{}_0.
$$

## Functional derivatives

For a functional $F[\phi,\pi]$, the variation is written

$$
\delta F
=\int d^3\mathbf x\left(
\frac{\delta F}{\delta\phi^A(\mathbf x)}\delta\phi^A(\mathbf x)
+\frac{\delta F}{\delta\pi_A(\mathbf x)}\delta\pi_A(\mathbf x)
\right).
$$

Spatial derivatives are moved off variations by integration by parts. Boundary conditions are therefore part of the functional derivative.

Example:

$$
F[\phi]=\int d^3\mathbf x\,\frac12(\nabla\phi)^2.
$$

Then

$$
\delta F=\int d^3\mathbf x\,\partial_i\phi\partial_i\delta\phi
=-\int d^3\mathbf x\,(\nabla^2\phi)\delta\phi,
$$

assuming the boundary term vanishes. Hence

$$
\frac{\delta F}{\delta\phi}=-\nabla^2\phi.
$$

## Example: real scalar field

For

$$
\mathcal L=\frac12\dot\phi^2-\frac12(\nabla\phi)^2-V(\phi),
$$

the momentum is

$$
\pi=\dot\phi.
$$

The Hamiltonian density is

$$
\boxed{
\mathcal H=\frac12\pi^2+\frac12(\nabla\phi)^2+V(\phi).
}
$$

Hamilton's equations are

$$
\dot\phi=\frac{\delta H}{\delta\pi}=\pi,
$$

and

$$
\dot\pi=-\frac{\delta H}{\delta\phi}=\nabla^2\phi-V'(\phi).
$$

Combining them gives

$$
\ddot\phi-\nabla^2\phi+V'(\phi)=0,
$$

which is the Euler–Lagrange equation.

## Example: complex scalar field

For

$$
\mathcal L=\dot\phi^\dagger\dot\phi-
\nabla\phi^\dagger\cdot\nabla\phi-V(\phi^\dagger\phi),
$$

treat $\phi$ and $\phi^\dagger$ independently:

$$
\pi_\phi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi^\dagger,
\qquad
\pi_{\phi^\dagger}=\frac{\partial\mathcal L}{\partial\dot\phi^\dagger}=\dot\phi.
$$

Then

$$
\boxed{
\mathcal H=\pi_\phi\pi_{\phi^\dagger}
+\nabla\phi^\dagger\cdot\nabla\phi
+V(\phi^\dagger\phi).
}
$$

The nonzero elementary brackets are

$$
\{\phi(\mathbf x),\pi_\phi(\mathbf y)\}=\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
\{\phi^\dagger(\mathbf x),\pi_{\phi^\dagger}(\mathbf y)\}=\delta^{(3)}(\mathbf x-\mathbf y).
$$

For phase symmetry, the charge

$$
Q=i\int d^3\mathbf x(\phi^\dagger\pi_{\phi^\dagger}-\pi_\phi\phi)
$$

generates

$$
\{\phi,Q\}=-i\phi,
\qquad
\{\phi^\dagger,Q\}=i\phi^\dagger.
$$

## Momentum generates spatial translations

The Hamiltonian generates time translations. Spatial momentum generates spatial translations. From the canonical stress tensor,

$$
T^0{}_i=\pi_A\partial_i\phi^A,
$$

so

$$
P_i=\int d^3\mathbf x\,\pi_A\partial_i\phi^A.
$$

Using the canonical bracket,

$$
\{\phi^A(\mathbf x),P_i\}=\partial_i\phi^A(\mathbf x),
$$

and, up to boundary terms,

$$
\{\pi_A(\mathbf x),P_i\}=\partial_i\pi_A(\mathbf x).
$$

Because qft.org uses mostly-minus signature, $P^i=-P_i$.

## Why interaction Hamiltonians need care

For non-derivative scalar interactions, one often has

$$
\mathcal H_{\rm int}=-\mathcal L_{\rm int}.
$$

Do not promote this to a law. If interactions contain time derivatives, the momentum definition changes, so the Legendre transform changes.

For example,

$$
\mathcal L=\frac12Z(\phi)\dot\phi^2-\frac12(\nabla\phi)^2-V(\phi),
\qquad Z(\phi)>0,
$$

gives

$$
\pi=Z(\phi)\dot\phi,
\qquad
\dot\phi=\frac{\pi}{Z(\phi)},
$$

and therefore

$$
\mathcal H=\frac{\pi^2}{2Z(\phi)}+\frac12(\nabla\phi)^2+V(\phi).
$$

The velocity-dependent factor moved into the denominator. This is why scattering theory distinguishes the interaction Hamiltonian from the interaction Lagrangian.

## Singular theories and constraints

Maxwell theory illustrates the issue:

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

The velocity $\dot A_0$ does not appear, so

$$
\pi^0=\frac{\partial\mathcal L}{\partial\dot A_0}=0.
$$

This is a primary constraint. The variable $A_0$ is not an independent propagating degree of freedom; it enforces Gauss's law. Gauge theories cannot be quantized by treating every component as a physical oscillator.

## Phase-space action and path integral preview

Hamiltonian dynamics can be written as

$$
S_H[\phi,\pi]=\int dt\,d^3\mathbf x\,[\pi_A\dot\phi^A-\mathcal H(\phi,\pi)].
$$

The corresponding formal phase-space path integral is

$$
Z=\int\mathcal D\phi\,\mathcal D\pi\,
\exp\left(i\int dt\,d^3\mathbf x\,[\pi_A\dot\phi^A-\mathcal H]\right).
$$

For simple scalar theories the $\pi$ integral is Gaussian and returns the Lagrangian path integral. For constrained systems, constraints, gauge fixing, determinants, or ghosts modify this statement.

## From Poisson brackets to commutators

Canonical quantization promotes

$$
\{F,G\}_{\rm PB}\longrightarrow\frac1i[\widehat F,\widehat G].
$$

Thus

$$
\boxed{
[\widehat\phi^A(t,\mathbf x),\widehat\pi_B(t,\mathbf y)]
=i\delta^A{}_B\delta^{(3)}(\mathbf x-\mathbf y).
}
$$

For fermions, anticommutators and graded brackets replace the bosonic bracket. For constrained systems, Dirac brackets or gauge-fixed formulations may be needed first.

## Common pitfalls

**Thinking $\mathcal H=-\mathcal L$.** The Legendre transform, not sign flipping, defines the Hamiltonian.

**Dropping boundary terms during functional differentiation.** Boundary conditions are part of the phase space.

**Confusing canonical momentum with spacetime momentum.** $\pi_A$ is conjugate to $\phi^A$; $P^\mu$ is a Noether charge.

**Treating all components as physical.** Gauge theories contain redundant variables and constraints.

**Expecting manifest Lorentz invariance.** Hamiltonian methods choose a time coordinate, so Lorentz symmetry is less visible.

## Relation to nearby pages

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) gives the Lagrangian equations.
- [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) identifies $H$ and $P_i$ as translation charges.
- [Constraints](/foundations/classical-field-theory/constraints/) treats singular Legendre transforms.
- [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) diagonalizes quadratic Hamiltonians into oscillators.
- [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) quantizes these brackets.

## Exercises

### Exercise 1: Real scalar Hamiltonian

Derive the Hamiltonian density for $\mathcal L=\frac12\dot\phi^2-\frac12(\nabla\phi)^2-V(\phi)$.

<details>
<summary><strong>Solution</strong></summary>

$\pi=\dot\phi$, so $\mathcal H=\pi\dot\phi-\mathcal L=\frac12\pi^2+\frac12(\nabla\phi)^2+V(\phi)$.

</details>

### Exercise 2: Hamilton equations

Use the real scalar Hamiltonian to recover $\ddot\phi-\nabla^2\phi+V'(\phi)=0$.

<details>
<summary><strong>Solution</strong></summary>

$\dot\phi=\delta H/\delta\pi=\pi$. Also $\delta H/\delta\phi=-\nabla^2\phi+V'(\phi)$, so $\dot\pi=\nabla^2\phi-V'(\phi)$. Use $\pi=\dot\phi$.

</details>

### Exercise 3: Maxwell primary constraint

Show that the momentum conjugate to $A_0$ vanishes in Maxwell theory.

<details>
<summary><strong>Solution</strong></summary>

$F_{0i}=\dot A_i-\partial_iA_0$ contains $\dot A_i$ but not $\dot A_0$, and $F_{ij}$ has no time derivatives. Hence $\mathcal L$ has no $\dot A_0$ dependence and $\pi^0=0$.

</details>

## References

- W. R. Hamilton, “On a General Method in Dynamics,” *Philosophical Transactions of the Royal Society of London* **124** (1834), 247–308.
- P. A. M. Dirac, *Lectures on Quantum Mechanics*.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 4.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§7.1–7.2 and §7.6.
- M. Srednicki, *Quantum Field Theory*, §3.

## Version history

- **2026-06-08:** Revised for tighter reader flow, clearer Legendre-transform warnings, less repetition with constraints, and a stronger handoff to canonical quantization.
- **2026-05-22:** Initial qft.org page.
