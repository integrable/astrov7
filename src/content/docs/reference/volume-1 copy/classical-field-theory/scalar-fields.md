---
title: "Scalar Fields"
description: "Real and complex scalar fields, the Klein–Gordon equation, scalar potentials, U(1) charge, Hamiltonian density, mass dimensions, and scalar fields as the simplest relativistic field theories."
sidebar:
  label: "Scalar Fields"
  order: 2
level: Graduate
status: "Polished draft"
topics:
  - scalar fields
  - Klein–Gordon equation
  - complex scalar field
  - U(1) symmetry
  - scalar potential
  - mass dimensions
canonicalTopics:
  - scalar-field
  - real-scalar-field
  - complex-scalar-field
  - klein-gordon-equation
---

## Summary

A scalar field is the simplest relativistic field: it has no Lorentz index. Under a Lorentz transformation $x\mapsto x'$, a real scalar transforms as

$$
\phi'(x')=\phi(x).
$$

The standard real scalar Lagrangian density is

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi - V(\phi).
$$

For the free massive potential $V(\phi)=\frac12m^2\phi^2$, the equation of motion is the Klein–Gordon equation

$$
\boxed{(\Box+m^2)\phi=0,}
\qquad
\Box=\partial_t^2-\nabla^2.
$$

A complex scalar field is equivalent to two real scalar fields. Its phase symmetry gives a conserved $U(1)$ current. After quantization, a free real scalar describes a neutral spin-zero particle, while a free complex scalar describes charged spin-zero particles and antiparticles. That interpretation comes later; this page fixes the classical theory.

## What this page assumes

Use [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) for the general variational derivation. Here we use that machinery rather than repeating it at full length. Conventions are those of [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric and $\hbar=c=1$.

Scalar fields are the cleanest examples because they postpone spin, gauge redundancy, and polarization. They still contain the important QFT architecture: mass terms, interactions, conserved currents, normal modes, propagators, path integrals, and renormalization.

## Real scalar field

A real scalar field is a map

$$
\phi:M^{1,3}\to\mathbb R.
$$

The standard first-derivative action is

$$
S[\phi]=\int d^4x\,
\left[\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)\right].
$$

With the qft.org metric,

$$
\partial_\mu\phi\partial^\mu\phi
=(\partial_t\phi)^2-(\nabla\phi)^2,
$$

so

$$
\mathcal L
=\frac12\dot\phi^2-\frac12(\nabla\phi)^2-V(\phi).
$$

The gradient term has a minus sign in $\mathcal L$ but contributes positively to the Hamiltonian. The Euler–Lagrange equation is

$$
\boxed{\Box\phi+V'(\phi)=0.}
$$

For $V=\frac12m^2\phi^2$, this becomes

$$
(\partial_t^2-\nabla^2+m^2)\phi=0.
$$

## Plane waves and the mass shell

For the free field, insert a plane wave

$$
\phi(x)\sim e^{-ip\cdot x},
\qquad
p\cdot x=p^0t-\mathbf p\cdot\mathbf x.
$$

Since

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x},
\qquad
p^2=(p^0)^2-\mathbf p^2,
$$

the Klein–Gordon equation requires

$$
\boxed{p^2=m^2.}
$$

Equivalently,

$$
p^0=\pm E_{\mathbf p},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The negative-frequency branch is not a negative probability branch. For a real field it is paired with the positive-frequency branch by reality. For a complex field it becomes part of the particle-antiparticle structure after quantization.

:::tip[Read this as a field equation]
The Klein–Gordon equation is safest as a field equation. Treating it as a single-particle relativistic wave equation leads to the familiar trouble with non-positive densities and misses particle creation.
:::

## Potentials and vacua

The potential controls self-interactions and classical vacuum structure. Common choices are

$$
V(\phi)=\frac12m^2\phi^2,
$$

for a free massive scalar,

$$
V(\phi)=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4,
$$

for the simplest parity-even interacting scalar theory, and

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
\qquad \lambda>0,
$$

for a double-well potential.

A constant classical background $\bar\phi$ is stationary when

$$
V'(\bar\phi)=0.
$$

Expanding $\phi=\bar\phi+\eta$ gives, to quadratic order,

$$
\mathcal L_2
=\frac12\partial_\mu\eta\partial^\mu\eta
-\frac12V''(\bar\phi)\eta^2.
$$

Thus the fluctuation mass squared is

$$
\boxed{M^2=V''(\bar\phi).}
$$

Positive $M^2$ means small fluctuations oscillate. Negative $M^2$ means the chosen background is unstable to sufficiently long-wavelength fluctuations.

:::caution[Tachyonic mass squared means unstable background]
A negative quadratic coefficient around a proposed vacuum does not mean the stable spectrum contains faster-than-light particles. It usually means you expanded around the wrong point in field space.
:::

## Complex scalar field

A complex scalar may be written as

$$
\phi=\frac1{\sqrt2}(\phi_1+i\phi_2),
$$

where $\phi_1$ and $\phi_2$ are real scalars. The standard Lagrangian is

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-V(\phi^\dagger\phi).
$$

For the free massive case,

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi-m^2\phi^\dagger\phi.
$$

In terms of real components this is

$$
\mathcal L
=\frac12\partial_\mu\phi_1\partial^\mu\phi_1
+\frac12\partial_\mu\phi_2\partial^\mu\phi_2
-\frac12m^2\phi_1^2
-\frac12m^2\phi_2^2.
$$

So a free complex scalar is two degenerate free real scalars. The useful new feature is its phase symmetry.

## Global U(1) current

If $V$ depends only on $\phi^\dagger\phi$, the theory is invariant under

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger,
$$

with constant $\alpha$. Noether's theorem gives

$$
\boxed{
j^\mu
=iq\,\phi^\dagger\overleftrightarrow{\partial^\mu}\phi
=iq\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
}
$$

Here

$$
f\overleftrightarrow{\partial^\mu}g
\equiv f\partial^\mu g-(\partial^\mu f)g.
$$

The equations of motion imply

$$
\partial_\mu j^\mu=0.
$$

The corresponding conserved charge is

$$
Q=\int d^3\mathbf x\,j^0.
$$

The overall sign of $Q$ follows the sign convention for the phase rotation. The invariant statement is that a complex scalar with phase symmetry has one conserved global $U(1)$ charge.

## Hamiltonian density

For a real scalar,

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi,
$$

and

$$
\boxed{
\mathcal H
=\frac12\pi^2+\frac12(\nabla\phi)^2+V(\phi).
}
$$

For a complex scalar, treat $\phi$ and $\phi^\dagger$ independently:

$$
\Pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi^\dagger,
\qquad
\Pi^\dagger=\frac{\partial\mathcal L}{\partial\dot\phi^\dagger}=\dot\phi.
$$

Then

$$
\boxed{
\mathcal H
=\Pi^\dagger\Pi+\nabla\phi^\dagger\cdot\nabla\phi+V(\phi^\dagger\phi).
}
$$

The charge density can be written canonically as

$$
j^0=iq(\phi^\dagger\Pi^\dagger-\Pi\phi).
$$

This is the classical ancestor of the quantum charge operator that counts particles minus antiparticles.

## Mass dimensions

In $d$ spacetime dimensions, $[\mathcal L]=d$ and $[\partial_\mu]=1$. The kinetic term gives

$$
2+2[\phi]=d,
$$

so

$$
\boxed{[\phi]=\frac{d-2}{2}.}
$$

For an interaction

$$
\mathcal L_{\rm int}=-\frac{g_n}{n!}\phi^n,
$$

the coupling dimension is

$$
\boxed{[g_n]=d-n\frac{d-2}{2}.}
$$

In four spacetime dimensions, $[\phi]=1$ and $[g_n]=4-n$. This is the first hint of the later relevant/marginal/irrelevant classification.

## Scalar multiplets

For $N$ real scalar fields,

$$
\phi^a(x),\qquad a=1,\ldots,N,
$$

an $O(N)$-invariant Lagrangian can be written as

$$
\mathcal L
=\frac12\partial_\mu\phi^a\partial^\mu\phi^a
-V(\phi^a\phi^a).
$$

The complex scalar is the $N=2$ case written in notation adapted to the $U(1)\subset O(2)$ symmetry. Scalar multiplets become essential in symmetry breaking, Goldstone physics, Higgs physics, critical phenomena, and nonlinear sigma models.

## Common pitfalls

**Confusing scalar fields with scalar wavefunctions.** A field is a dynamical variable. A wavefunction is a state-dependent amplitude.

**Losing the metric sign.** With mostly-minus signature, $\frac12\partial_\mu\phi\partial^\mu\phi=\frac12\dot\phi^2-\frac12(\nabla\phi)^2$.

**Missing the factor of one half.** A real scalar free Lagrangian has $\frac12m^2\phi^2$. A complex scalar free Lagrangian has $m^2\phi^\dagger\phi$, which already equals $\frac12m^2(\phi_1^2+\phi_2^2)$.

**Varying complex fields incorrectly.** During the variational calculation, treat $\phi$ and $\phi^\dagger$ as independent variables.

**Reading $M^2<0$ too literally.** Negative curvature of the potential is an instability of the background, not a healthy particle mass.

## Relation to nearby pages

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) gives the general action principle.
- [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) derives the $U(1)$ current systematically.
- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) develops the canonical variables used above.
- [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) explains why scalar quadratic fluctuations become oscillator modes.
- [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) explains why relativistic quantum theory wants fields rather than single-particle Klein–Gordon wavefunctions.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) turns the classical scalar into a quantum field.

## Exercises

### Exercise 1: Real scalar equation

Derive $\Box\phi+V'(\phi)=0$ from $\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)$.

<details>
<summary><strong>Solution</strong></summary>

Use $\partial\mathcal L/\partial\phi=-V'(\phi)$ and $\partial\mathcal L/\partial(\partial_\mu\phi)=\partial^\mu\phi$. The Euler–Lagrange equation gives $-V'-\Box\phi=0$.

</details>

### Exercise 2: Complex scalar as two real scalars

Let $\phi=(\phi_1+i\phi_2)/\sqrt2$. Show that the free complex scalar Lagrangian equals two free real scalar Lagrangians with equal mass.

<details>
<summary><strong>Solution</strong></summary>

Compute $\phi^\dagger\phi=\frac12(\phi_1^2+\phi_2^2)$ and $\partial_\mu\phi^\dagger\partial^\mu\phi=\frac12\partial_\mu\phi_1\partial^\mu\phi_1+\frac12\partial_\mu\phi_2\partial^\mu\phi_2$. Substitute into $\mathcal L=\partial\phi^\dagger\partial\phi-m^2\phi^\dagger\phi$.

</details>

### Exercise 3: Current conservation

Use the complex scalar equations of motion to show $\partial_\mu j^\mu=0$ for $j^\mu=iq(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi)$.

<details>
<summary><strong>Solution</strong></summary>

The derivative-product terms cancel, leaving

$$
\partial_\mu j^\mu=iq(\phi^\dagger\Box\phi-(\Box\phi^\dagger)\phi).
$$

Using $\Box\phi=-V'\phi$ and $\Box\phi^\dagger=-V'\phi^\dagger$ gives zero.

</details>

### Exercise 4: Mass dimension of $\phi^4$

In $d=4$, find the mass dimension of the coupling $\lambda$ in $\mathcal L_{\rm int}=-\lambda\phi^4/4!$.

<details>
<summary><strong>Solution</strong></summary>

In $d=4$, $[\phi]=1$. Since $[\mathcal L]=4$, we need $[\lambda]+4=4$, so $[\lambda]=0$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§1–3 and §22.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3–6.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.1–5.2 and §§7.1–7.3.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.3, I.8, and I.10.

## Version history

- **2026-06-08:** Revised for cleaner reader path, less duplication of the general variational derivation, sharper complex-scalar and mass-dimension sections, and improved cross-links.
- **2026-05-22:** Initial qft.org page.
