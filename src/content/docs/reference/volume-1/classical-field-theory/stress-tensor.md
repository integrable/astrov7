---
title: "Stress Tensor"
description: "Energy–momentum conservation, canonical stress tensors, improvements, Hilbert stress tensors, trace, and the role of T^{mu nu} in QFT."
sidebar:
  label: "Stress Tensor"
  order: 4
level: Graduate
status: "Polished draft"
topics:
  - stress tensor
  - energy momentum tensor
  - Noether theorem
  - translation symmetry
  - Belinfante tensor
  - Hilbert stress tensor
  - conformal improvement
canonicalTopics:
  - stress-tensor
  - energy-momentum-tensor
  - hilbert-stress-tensor
  - stress-tensor-improvement
---

## Summary

The stress tensor, or energy–momentum tensor, is the local current associated with spacetime translations. For a first-derivative Lagrangian density with no explicit spacetime dependence, the canonical tensor is

$$
\boxed{
T^\mu{}_{\nu}
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}\partial_\nu\phi^A
-\delta^\mu{}_{\nu}\mathcal L.
}
$$

On shell,

$$
\partial_\mu T^\mu{}_{\nu}=0.
$$

The charges are the components of four-momentum:

$$
P_\nu=\int d^3\mathbf x\,T^0{}_{\nu}.
$$

This is only the first representative. The canonical tensor may fail to be symmetric, gauge invariant, or best suited for gravity. Belinfante–Rosenfeld improvements, Hilbert stress tensors, and conformal improvements all appear because different questions ask for different representatives of the same local conservation law.

## What to know first

Read [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) before this page. We use mostly-minus signature. The mixed-index notation $T^\mu{}_{\nu}$ is useful because the first index is the current index and the second labels which translation charge is being transported.

## What the indices mean

The equation

$$
\partial_\mu T^\mu{}_{\nu}=0
$$

is four continuity equations at once. Roughly:

| Component | Meaning |
|---|---|
| $T^0{}_0$ | energy density |
| $T^i{}_0$ | flux of energy through the $i$ direction |
| $T^0{}_i$ | density of lowered spatial momentum $P_i$ |
| $T^i{}_j$ | flux of $P_j$ through the $i$ direction |

With both indices raised,

$$
T^{\mu\nu}=T^\mu{}_{\rho}\eta^{\rho\nu},
$$

the conserved charge on a Cauchy surface $\Sigma$ is

$$
P^\nu(\Sigma)=\int_\Sigma d\Sigma_\mu\,T^{\mu\nu}.
$$

If no energy–momentum flows through the side boundary, $P^\nu(\Sigma)$ is independent of the hypersurface.

## Derivation from translations

For a local first-derivative theory,

$$
\Pi_A^\mu=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^A)}.
$$

Under an active infinitesimal translation,

$$
\delta_a\phi^A=a^\nu\partial_\nu\phi^A,
$$

and, if the Lagrangian density has no explicit $x$ dependence,

$$
\delta_a\mathcal L=a^\nu\partial_\nu\mathcal L
=\partial_\mu(a^\nu\delta^\mu{}_{\nu}\mathcal L).
$$

Noether's theorem gives the current $j^\mu_{(a)}=a^\nu T^\mu{}_{\nu}$ with

$$
T^\mu{}_{\nu}=\Pi_A^\mu\partial_\nu\phi^A-
\delta^\mu{}_{\nu}\mathcal L.
$$

Off shell,

$$
\partial_\mu T^\mu{}_{\nu}
=-E_A(\mathcal L)\partial_\nu\phi^A,
$$

up to active/passive sign conventions. On shell it is conserved.

## Real scalar example

For

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi),
$$

we have $\Pi^\mu=\partial^\mu\phi$. The scalar stress tensor with both indices raised is

$$
\boxed{
T^{\mu\nu}
=\partial^\mu\phi\partial^\nu\phi
-\eta^{\mu\nu}\mathcal L.
}
$$

It is already symmetric. The energy density is

$$
\boxed{
T^{00}
=\frac12\dot\phi^2+\frac12(\nabla\phi)^2+V(\phi).
}
$$

This agrees with the scalar Hamiltonian density.

The spatial momentum is

$$
P^i=\int d^3\mathbf x\,T^{0i}
=-\int d^3\mathbf x\,\dot\phi\,\partial_i\phi,
$$

where the minus sign comes from $\partial^i=-\partial_i$ in the mostly-minus convention.

## Complex scalar example

For

$$
\mathcal L=\partial_\mu\phi^\dagger\partial^\mu\phi
-V(\phi^\dagger\phi),
$$

treat $\phi$ and $\phi^\dagger$ independently. A symmetric stress tensor is

$$
\boxed{
T^{\mu\nu}
=\partial^\mu\phi^\dagger\partial^\nu\phi
+\partial^\mu\phi\partial^\nu\phi^\dagger
-\eta^{\mu\nu}\mathcal L.
}
$$

The energy density is

$$
T^{00}
=\dot\phi^\dagger\dot\phi
+\nabla\phi^\dagger\cdot\nabla\phi
+V(\phi^\dagger\phi).
$$

Do not confuse this stress tensor with the internal $U(1)$ current

$$
j^\mu=i\phi^\dagger\overleftrightarrow{\partial^\mu}\phi.
$$

The stress tensor transports energy and momentum. The $U(1)$ current transports internal charge.

## Maxwell example

For electromagnetism,

$$
\mathcal L=-\frac14F_{\rho\sigma}F^{\rho\sigma},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

the direct canonical tensor is conserved on shell but not manifestly gauge invariant because it contains $A_\mu$ explicitly. A physically preferred gauge-invariant representative is

$$
\boxed{
T^{\mu\nu}_{\rm Maxwell}
=-F^{\mu\rho}F^\nu{}_{\rho}
+\frac14\eta^{\mu\nu}F_{\rho\sigma}F^{\rho\sigma}.
}
$$

It gives

$$
T^{00}=\frac12(\mathbf E^2+\mathbf B^2)
$$

with standard electric and magnetic conventions. This example is the first warning that the first Noether tensor is not always the tensor you want to display.

## The stress tensor is not unique

If

$$
K^{\rho\mu\nu}=-K^{\mu\rho\nu},
$$

then

$$
T'^{\mu\nu}=T^{\mu\nu}+\partial_\rho K^{\rho\mu\nu}
$$

has the same divergence:

$$
\partial_\mu T'^{\mu\nu}=\partial_\mu T^{\mu\nu}.
$$

The extra term is an improvement. Under suitable boundary conditions, improvements do not change the total four-momentum. They can change local density, local flux, trace, symmetry, and gauge-invariance properties.

:::tip[Which stress tensor should I use?]
For canonical quantization, start from the canonical tensor. For angular momentum and spin, use the Belinfante–Rosenfeld construction. For gauge theory, use a gauge-invariant representative. For coupling to gravity, use the metric/Hilbert tensor. For CFT, use an improved symmetric traceless tensor when it exists.
:::

## Lorentz symmetry and Belinfante improvement

Lorentz transformations produce angular-momentum and boost currents. For fields with spin, the current contains orbital and spin pieces:

$$
M^{\lambda\mu\nu}
=x^\mu T^{\lambda\nu}_{\rm can}
-x^\nu T^{\lambda\mu}_{\rm can}
+B^{\lambda\mu\nu},
$$

where $B^{\lambda\mu\nu}$ is the spin current. Conservation implies that the antisymmetric part of the canonical tensor is balanced by the divergence of spin current.

The Belinfante–Rosenfeld tensor improves the canonical tensor so that spin information is folded into a symmetric stress tensor:

$$
T^{\mu\nu}_{\rm B}
=T^{\mu\nu}_{\rm can}
+\frac12\partial_\lambda
\left(B^{\lambda\mu\nu}+B^{\mu\nu\lambda}+B^{\nu\mu\lambda}\right).
$$

Then $T^{\mu\nu}_{\rm B}=T^{\nu\mu}_{\rm B}$ on shell and gives the same total four-momentum under standard boundary conditions.

## Metric or Hilbert stress tensor

Another definition comes from coupling the theory to a background metric:

$$
S_m[g,\phi]=\int d^4x\sqrt{-g}\,\mathcal L_m(g,\phi,\nabla\phi).
$$

With qft.org mostly-minus conventions,

$$
\boxed{
T_{\mu\nu}^{\rm H}
=\frac{2}{\sqrt{-g}}\frac{\delta S_m}{\delta g^{\mu\nu}}.
}
$$

Equivalently,

$$
\delta S_m
=\frac12\int d^4x\sqrt{-g}\,T_{\mu\nu}^{\rm H}\delta g^{\mu\nu}.
$$

For the scalar Lagrangian

$$
\mathcal L=\frac12g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi-V(\phi),
$$

the Hilbert tensor is

$$
T_{\mu\nu}^{\rm H}
=\partial_\mu\phi\partial_\nu\phi
-g_{\mu\nu}\mathcal L.
$$

In flat space this agrees with the symmetric scalar stress tensor.

:::caution[Metric variation remembers choices]
Two flat-space Lagrangians that differ by a total derivative can lead to different curved-space covariantizations. Curvature couplings such as $\xi R\phi^2$ change the flat-space stress tensor by improvement terms after taking the flat limit.
:::

## Trace and conformal improvement

The trace

$$
T^\mu{}_{\mu}
$$

measures response to scale transformations. For a massless scalar in four dimensions, the canonical tensor is symmetric and conserved, but its trace is not zero:

$$
T^\mu{}_{\mu}=-\partial_\mu\phi\partial^\mu\phi.
$$

On shell, $\Box\phi=0$, so

$$
\Box\phi^2=2\partial_\mu\phi\partial^\mu\phi.
$$

Adding the Callan–Coleman–Jackiw improvement

$$
\Delta T^{\mu\nu}
=\frac16(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu)\phi^2
$$

makes the improved tensor conserved, symmetric, and traceless on shell. In $d$ spacetime dimensions the conformal coefficient is

$$
\xi_d=\frac{d-2}{4(d-1)}.
$$

Quantum mechanically, even a classically traceless tensor can acquire a trace anomaly. That belongs later, but the classical lesson is already useful: the trace knows about scale symmetry.

## Stress tensor as a quantum operator

In QFT, $T^{\mu\nu}(x)$ is a local composite operator. Products of fields at the same point are singular, so the quantum stress tensor requires regularization and renormalization.

The integrated charge

$$
P^\nu=\int d^3\mathbf x\,T^{0\nu}
$$

generates spacetime translations. Stress-tensor correlation functions encode central-charge-like data in CFT, response to metric perturbations, thermal energy density and pressure, and transport coefficients.

This page stays mostly classical. The quantum stress tensor reappears in Ward identities, anomalies, CFT, curved-spacetime QFT, and hydrodynamics.

## Common pitfalls

**Treating the canonical tensor as sacred.** It is the first Noether tensor, not always the best one.

**Forgetting boundary flux.** Local conservation implies conserved charges only after boundary flux is handled.

**Confusing internal currents with stress tensors.** Charge current and energy–momentum current correspond to different symmetries.

**Expecting symmetry without improvement.** Lorentz invariance does not force the canonical tensor itself to be symmetric.

**Assuming masslessness implies tracelessness.** A massless scalar needs conformal improvement in four dimensions.

**Ignoring gauge invariance.** Gauge theories often require improved or metric-derived representatives.

## Relation to nearby pages

- [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) gives the current formula used here.
- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) identifies $T^0{}_0$ with the Hamiltonian density for ordinary systems.
- [Constraints](/foundations/classical-field-theory/constraints/) explains why gauge variables require special care.
- [Poincare Symmetry](/foundations/symmetry-and-spacetime/poincare-symmetry/) studies $P^\mu$ and $M^{\mu\nu}$ as generators.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) promotes conservation laws to correlation-function identities.

## Exercises

### Exercise 1: Scalar conservation

For $\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)$, show that $T^{\mu\nu}=\partial^\mu\phi\partial^\nu\phi-\eta^{\mu\nu}\mathcal L$ is conserved on shell.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu T^{\mu\nu}
=(\Box\phi)\partial^\nu\phi+\partial^\mu\phi\partial_\mu\partial^\nu\phi-\partial^\nu\mathcal L.
$$

The derivative-product terms cancel. The remaining term is

$$
(\Box\phi+V'(\phi))\partial^\nu\phi,
$$

which vanishes on shell.

</details>

### Exercise 2: Improvement preserves conservation

Show that $T'^{\mu\nu}=T^{\mu\nu}+\partial_\rho K^{\rho\mu\nu}$ has the same divergence as $T^{\mu\nu}$ when $K^{\rho\mu\nu}=-K^{\mu\rho\nu}$.

<details>
<summary><strong>Solution</strong></summary>

The difference in divergences is $\partial_\mu\partial_\rho K^{\rho\mu\nu}$. This vanishes because $\partial_\mu\partial_\rho$ is symmetric in $\mu,\rho$, while $K^{\rho\mu\nu}$ is antisymmetric in those indices.

</details>

### Exercise 3: Hilbert tensor for a scalar

Starting from $S=\int d^4x\sqrt{-g}[\frac12g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi-V(\phi)]$, derive $T_{\mu\nu}^{\rm H}=\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L$.

<details>
<summary><strong>Solution</strong></summary>

Use $\delta\sqrt{-g}=-\frac12\sqrt{-g}g_{\mu\nu}\delta g^{\mu\nu}$ and vary the explicit $g^{\mu\nu}$ in the kinetic term. Then compare with $\delta S=\frac12\int\sqrt{-g}T_{\mu\nu}\delta g^{\mu\nu}$.

</details>

## References

- F. J. Belinfante, “On the current and density of the electric charge, the energy, the linear momentum and the angular momentum of arbitrary fields,” *Physica* (1940).
- L. Rosenfeld, “Sur la tenseur d'impulsion-énergie,” *Mémoires de l'Académie Royale de Belgique* (1940).
- C. G. Callan, S. Coleman, and R. Jackiw, “A New Improved Energy-Momentum Tensor,” *Annals of Physics* **59** (1970), 42–73.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 5.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§7.3–7.4.
- M. Srednicki, *Quantum Field Theory*, §22 and problem 36.4.

## Version history

- **2026-06-08:** Revised for stronger reader orientation, clearer representative-choice guidance, and reduced overlap with Noether and Hamiltonian pages.
- **2026-05-22:** Initial qft.org page.
