---
title: "Poincaré Symmetry"
description: "Translations, Lorentz transformations, the Poincaré algebra, Noether charges, field covariance, and the mass-spin labels of relativistic quantum states."
sidebar:
  label: "Poincaré Symmetry"
  order: 1
---

## Summary

Poincaré symmetry is the symmetry of flat relativistic spacetime. It combines spacetime translations with Lorentz transformations:

$$
x'^\mu=\Lambda^\mu{}_{\nu}x^\nu+a^\mu,
\qquad
\Lambda^T\eta\Lambda=\eta.
$$

With the qft.org default metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
$$

the connected part of the group is

$$
\boxed{
\mathcal P_+^\uparrow=\mathbb R^{1,3}\rtimes SO^+(1,3).
}
$$

The semidirect product matters: translations form an Abelian subgroup, but Lorentz transformations rotate and boost the translation generators. Quantum mechanically, Poincaré symmetry is represented by unitary operators on the Hilbert space. Its generators are the four-momentum $P^\mu$ and antisymmetric Lorentz generators $M^{\mu\nu}=-M^{\nu\mu}$.

This page fixes the algebraic language used throughout the rest of the Foundations symmetry pages. It is the bridge between the classical Noether currents of [Stress Tensor](/foundations/classical-field-theory/stress-tensor/), the particle-state classification of [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), and the field-representation language of [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/).

Weinberg's treatment starts from relativity and quantum mechanics and derives the Poincaré algebra, one-particle labels, little groups, and Lorentz transformation laws of fields (Weinberg 1995, Vol. I, chs. 2 and 5). Coleman's spacetime-symmetry lectures derive the corresponding Noether currents and charges in field theory (Coleman 2019, ch. 5). Srednicki develops Lorentz invariance early because it fixes the scalar-field normalization and later spinor technology (Srednicki 2007, §§2–3 and §33).

<figure class="doc-figure" style="--figure-width: 50rem;">

![Poincaré symmetry map](/figures/foundations/poincare-symmetry-map.svg)

<figcaption>

Poincaré symmetry combines translations with Lorentz transformations. The Noether currents give conserved charges $P^\mu$ and $M^{\mu\nu}$, while the quantum representation of the same group organizes particles by mass, spin, and helicity.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Noether Theorem](/foundations/classical-field-theory/noether-theorem/), [Stress Tensor](/foundations/classical-field-theory/stress-tensor/), [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/), and [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/).

## The spacetime group

A Poincaré transformation is an affine map of Minkowski spacetime,

$$
x^\mu\mapsto x'^\mu=\Lambda^\mu{}_{\nu}x^\nu+a^\mu,
$$

where $a^\mu$ is a constant translation and $\Lambda$ is a Lorentz matrix preserving the Minkowski inner product:

$$
\eta_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}
=\eta_{\mu\nu}.
$$

Equivalently,

$$
(\Lambda p)^2=p^2,
\qquad
(\Lambda x-\Lambda y)^2=(x-y)^2.
$$

The subgroup with $a^\mu=0$ is the Lorentz group. The subgroup with $\Lambda=1$ is the translation group. Their multiplication law is

$$
(\Lambda,a)(\Lambda',a')=(\Lambda\Lambda',a+\Lambda a').
$$

This is why the group is not a direct product. The translation $a'$ is first Lorentz-transformed before being added to $a$.

For most QFT work one first studies the connected component of the identity: proper, orthochronous Lorentz transformations and translations. Parity and time reversal are discrete spacetime transformations and are treated separately in [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/).

:::note[Connected component]
The connected Lorentz group $SO^+(1,3)$ excludes parity and time reversal. It includes continuously reachable rotations and boosts. In four dimensions its double cover is $SL(2,\mathbb C)$, which is why spinors enter relativistic QFT.
:::

## Quantum representation

In quantum theory, spacetime symmetry acts on states by unitary operators, at least for the connected Poincaré group. We write the generators as

$$
P^\mu=(H,\mathbf P),
\qquad
M^{\mu\nu}=-M^{\nu\mu}.
$$

Translations are represented by

$$
U(a)=e^{i a_\mu P^\mu}.
$$

With this convention, local Heisenberg operators obey

$$
\mathcal O(x)=e^{iP\cdot x}\mathcal O(0)e^{-iP\cdot x},
$$

so

$$
U(a)\mathcal O(x)U(a)^{-1}=\mathcal O(x+a).
$$

The Lorentz generators are packaged into $M^{\mu\nu}$. The spatial rotation generators and boost generators are

$$
J^i=\frac12\epsilon^{ijk}M^{jk},
\qquad
K^i=M^{i0}.
$$

There are six Lorentz generators: three rotations and three boosts. Together with four translations, this gives the ten generators of the Poincaré group.

## The algebra

The Poincaré algebra in qft.org conventions is

$$
\boxed{
[P^\mu,P^\nu]=0,
}
$$

$$
\boxed{
[M^{\mu\nu},P^\rho]
=i\left(\eta^{\nu\rho}P^\mu-\eta^{\mu\rho}P^\nu\right),
}
$$

and

$$
\boxed{
\begin{aligned}
[M^{\mu\nu},M^{\rho\sigma}]
=i(&\eta^{\mu\rho}M^{\nu\sigma}
-\eta^{\nu\rho}M^{\mu\sigma}\\
&-\eta^{\mu\sigma}M^{\nu\rho}
+\eta^{\nu\sigma}M^{\mu\rho}).
\end{aligned}
}
$$

In three-vector notation this becomes

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
\qquad
[J_i,K_j]=i\epsilon_{ijk}K_k,
\qquad
[K_i,K_j]=-i\epsilon_{ijk}J_k.
$$

The minus sign in the boost-boost commutator is the algebraic fingerprint of Lorentzian signature. Rotating twice gives a rotation; boosting in two nonparallel directions gives a boost plus a rotation. That induced rotation is the origin of Thomas precession and Wigner rotations.

The translation generators transform as a Lorentz vector:

$$
[J_i,P_j]=i\epsilon_{ijk}P_k,
\qquad
[J_i,H]=0,
$$

$$
[K_i,H]=iP_i,
\qquad
[K_i,P_j]=i\delta_{ij}H,
$$

where $\mathbf P$ denotes the physical spatial momentum components. If you instead write all spatial components with lowered Lorentz indices, signs move accordingly. The covariant algebra above is the safest reference.

## Noether charges

In a Poincaré-invariant classical field theory, translations and Lorentz transformations produce conserved currents. If a symmetric stress tensor $T^{\mu\nu}$ is available, the translation charges are

$$
\boxed{
P^\nu=\int d^3\mathbf x\,T^{0\nu}.
}
$$

The Lorentz charges are

$$
\boxed{
M^{\mu\nu}
=\int d^3\mathbf x\,
\left(x^\mu T^{0\nu}-x^\nu T^{0\mu}\right).
}
$$

For a nonsymmetric canonical stress tensor, an explicit spin-current term appears:

$$
M^{\mu\nu}
=\int d^3\mathbf x\,
\left(x^\mu T^{0\nu}_{\rm can}-x^\nu T^{0\mu}_{\rm can}
+S^{0\mu\nu}\right).
$$

The Belinfante improvement moves the spin-current contribution into a symmetric stress tensor. This does not erase spin; it repackages the local angular-momentum current.

This is the classical-to-quantum bridge:

```txt
spacetime symmetry of the action
       ↓
Noether current
       ↓
conserved charge
       ↓
operator generator on fields and states
```

## Field covariance

A local field $\Phi_A(x)$ may carry Lorentz indices, spinor indices, or internal indices. Under a connected Poincaré transformation, a common active convention is

$$
\boxed{
U(a,\Lambda)\Phi_A(x)U(a,\Lambda)^{-1}
=D(\Lambda^{-1})_A{}^B\,
\Phi_B(\Lambda x+a).
}
$$

For a scalar field, $D(\Lambda)=1$. For a vector field,

$$
U(a,\Lambda)A^\mu(x)U(a,\Lambda)^{-1}
=(\Lambda^{-1})^\mu{}_{\nu}A^\nu(\Lambda x+a),
$$

with index-placement conventions determining the exact matrix used. For spinors, $D(\Lambda)$ is a spinor representation of the double cover $SL(2,\mathbb C)$.

The infinitesimal form is often the most useful. Translations give

$$
i[P_\mu,\Phi_A(x)]=\partial_\mu\Phi_A(x),
$$

and Lorentz transformations give

$$
\boxed{
\begin{aligned}
i[M^{\mu\nu},\Phi_A(x)]
=&\left(x^\mu\partial^\nu-x^\nu\partial^\mu\right)\Phi_A(x)\\
&+(\Sigma^{\mu\nu})_A{}^B\Phi_B(x),
\end{aligned}
}
$$

where $\Sigma^{\mu\nu}$ is the spin matrix appropriate to the field representation. For scalar fields, $\Sigma^{\mu\nu}=0$. For vector fields,

$$
(\Sigma^{\mu\nu})^\rho{}_{\sigma}
=i(\eta^{\mu\rho}\delta^\nu{}_{\sigma}
-\eta^{\nu\rho}\delta^\mu{}_{\sigma}),
$$

up to the sign convention chosen for the infinitesimal transformation. The important conceptual split is invariant:

```txt
orbital part:  spacetime label x moves
spin part:     field components rotate among themselves
```

## Vacuum invariance

In relativistic QFT one usually assumes a Poincaré-invariant vacuum:

$$
U(a,\Lambda)|0\rangle=|0\rangle,
$$

or infinitesimally,

$$
P^\mu|0\rangle=0,
\qquad
M^{\mu\nu}|0\rangle=0,
$$

after setting the vacuum energy to zero.

This assumption has consequences. Translation invariance makes vacuum correlators depend only on coordinate differences:

$$
\langle0|\phi(x)\phi(y)|0\rangle
=G(x-y).
$$

Lorentz invariance then restricts the dependence of scalar correlators to Lorentz-invariant combinations, modulo distributions, time ordering, and the $i\epsilon$ prescription. When a vacuum is not invariant under some symmetry, the symmetry may be spontaneously broken; the operator algebra can still be symmetric even when the chosen vacuum is not.

:::caution[Vacuum invariance is an assumption]
Many structural QFT statements assume a stable Poincaré-invariant vacuum. Finite temperature, finite density, curved spacetime, boundaries, defects, external fields, and spontaneously broken spacetime symmetries all modify the symmetry story.
:::

## Casimirs and particle labels

The Poincaré algebra has invariant operators called Casimirs. The first is

$$
P^2=P_\mu P^\mu.
$$

On a massive one-particle state,

$$
P^2|p,\sigma\rangle=m^2|p,\sigma\rangle.
$$

The second uses the Pauli–Lubanski vector

$$
W^\mu=\frac12\epsilon^{\mu\nu\rho\sigma}P_\nu M_{\rho\sigma}.
$$

For massive particles,

$$
W^2=-m^2s(s+1),
$$

where $s$ is the spin. For massless finite-helicity particles,

$$
W^\mu=\lambda P^\mu,
$$

where $\lambda$ is the helicity.

This is why mass, spin, and helicity are not arbitrary decorative labels. They are representation-theoretic labels of the Poincaré group. Fields are then built so that their quanta transform in the desired particle representations.

## What symmetry fixes, and what it does not

Poincaré symmetry is powerful, but it does not determine the theory by itself.

It fixes the allowed spacetime transformation properties, constrains local terms in the Lagrangian, organizes particles into mass and spin/helicity classes, and gives selection rules for correlators and amplitudes. But it does not tell you the particle content, the values of masses and couplings, the gauge group, the vacuum, or whether perturbation theory is useful.

A scalar theory, QED, Yang–Mills theory, a conformal field theory, and an effective theory with infinitely many higher-derivative operators can all be Poincaré invariant. Symmetry is architecture, not the whole building.

## Common pitfalls

**Confusing Lorentz covariance with Lorentz invariance.** A vector equation can be covariant without every individual component being invariant. Covariant means the equation keeps its form under the transformation.

**Forgetting boosts.** Rotational invariance alone is not relativistic invariance. Boosts mix space and time, energy and momentum, electric and magnetic fields, and spin and orbital parts of angular momentum.

**Treating finite-dimensional field representations as particle Hilbert spaces.** A vector field has four Lorentz components, but a massive spin-one particle has three physical polarizations and a photon has two helicities. Field components are not automatically physical degrees of freedom.

**Assuming equal-time quantization makes Lorentz symmetry absent.** Canonical quantization chooses a time coordinate, but the resulting theory can still carry the full Poincaré algebra if the Hamiltonian, momentum, rotations, and boosts are correctly constructed.

**Ignoring boundary terms.** The derivation of Noether charges assumes suitable falloff or boundary conditions. In gauge theory, gravity, and systems with defects or boundaries, surface terms can become physical charges.

## Relations to other pages

- [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) derives translation and Lorentz currents from the action.
- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) explains mass shell, little groups, and one-particle labels.
- [Polarizations](/foundations/free-fields/polarizations/) applies the little-group story to spin-one fields.
- [Lorentz Representations](/foundations/symmetry-and-spacetime/lorentz-representations/) classifies scalar, vector, tensor, and spinor fields.
- [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/) will distinguish spacetime symmetries from symmetries that act only on field labels.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will explain how Poincaré symmetry and causal commutators work together.

## Research status

- **Established:** The Poincaré group, its Lie algebra, Noether charges in flat spacetime, and the classification of massive and massless one-particle representations are textbook-standard.
- **Subtle:** Interacting QFTs may realize spacetime symmetries nontrivially through anomalies, spontaneous breaking, boundary charges, gauge constraints, or infrared effects.
- **Beyond this page:** Supersymmetry extends the Poincaré algebra by fermionic generators. Conformal symmetry extends it by dilations and special conformal transformations. General relativity replaces global Poincaré symmetry with local Lorentz symmetry plus diffeomorphism invariance.

## Exercises

### Exercise 1: Infinitesimal Lorentz antisymmetry

Let

$$
\Lambda^\mu{}_{\nu}=\delta^\mu{}_{\nu}+\omega^\mu{}_{\nu}
$$

with $\omega$ infinitesimal. Use $\Lambda^T\eta\Lambda=\eta$ to show that

$$
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

<details>
<summary><strong>Solution</strong></summary>

The Lorentz condition is

$$
\eta_{\rho\sigma}\Lambda^\rho{}_{\mu}\Lambda^\sigma{}_{\nu}
=\eta_{\mu\nu}.
$$

Substitute $\Lambda=1+\omega$ and keep first order terms:

$$
\eta_{\rho\sigma}
(\delta^\rho{}_{\mu}+\omega^\rho{}_{\mu})
(\delta^\sigma{}_{\nu}+\omega^\sigma{}_{\nu})
=\eta_{\mu\nu}+\omega_{\nu\mu}+\omega_{\mu\nu}.
$$

Therefore

$$
\omega_{\mu\nu}+\omega_{\nu\mu}=0,
$$

so

$$
\boxed{\omega_{\mu\nu}=-\omega_{\nu\mu}.}
$$

This gives six independent infinitesimal Lorentz parameters in four dimensions.

</details>

### Exercise 2: Translation generators commute

Use the group law for translations,

$$
T(a)T(b)=T(a+b),
$$

to explain why

$$
[P^\mu,P^\nu]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Translations form an Abelian subgroup:

$$
T(a)T(b)=T(b)T(a).
$$

With

$$
U(a)=e^{ia_\mu P^\mu},
$$

commutativity for arbitrary infinitesimal $a$ and $b$ implies the commutator of the generators vanishes:

$$
\boxed{[P^\mu,P^\nu]=0.}
$$

Physically, translating in one spacetime direction and then another gives the same spacetime point as doing the operations in the opposite order.

</details>

### Exercise 3: Boosts do not commute

Using the three-vector Lorentz algebra,

$$
[J_i,J_j]=i\epsilon_{ijk}J_k,
\qquad
[J_i,K_j]=i\epsilon_{ijk}K_k,
\qquad
[K_i,K_j]=-i\epsilon_{ijk}J_k,
$$

compute $[K_x,K_y]$.

<details>
<summary><strong>Solution</strong></summary>

Set $i=x$, $j=y$. Since $\epsilon_{xyz}=+1$,

$$
[K_x,K_y]=-i\epsilon_{xyz}J_z.
$$

Thus

$$
\boxed{[K_x,K_y]=-iJ_z.}
$$

Two nonparallel boosts fail to commute; their commutator is a rotation.

</details>

### Exercise 4: Translation action on a scalar field

Assume

$$
\phi(x)=e^{iP\cdot x}\phi(0)e^{-iP\cdot x}.
$$

Show that

$$
i[P_\mu,\phi(x)]=\partial_\mu\phi(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate with respect to $x^\mu$:

$$
\partial_\mu\phi(x)
=iP_\mu e^{iP\cdot x}\phi(0)e^{-iP\cdot x}
-e^{iP\cdot x}\phi(0)e^{-iP\cdot x}iP_\mu.
$$

Therefore

$$
\partial_\mu\phi(x)
=iP_\mu\phi(x)-i\phi(x)P_\mu
=i[P_\mu,\phi(x)].
$$

So

$$
\boxed{i[P_\mu,\phi(x)]=\partial_\mu\phi(x).}
$$

</details>

### Exercise 5: Conservation of four-momentum

Assume the stress tensor obeys

$$
\partial_\mu T^{\mu\nu}=0
$$

and falls off fast enough at spatial infinity. Show that

$$
P^\nu=\int d^3\mathbf x\,T^{0\nu}
$$

is time-independent.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dP^\nu}{dt}
=\int d^3\mathbf x\,\partial_0 T^{0\nu}.
$$

Use conservation:

$$
\partial_0T^{0\nu}=-\partial_iT^{i\nu}.
$$

Thus

$$
\frac{dP^\nu}{dt}
=-\int d^3\mathbf x\,\partial_iT^{i\nu}.
$$

By the divergence theorem this is a surface term at spatial infinity. With suitable falloff,

$$
\boxed{\frac{dP^\nu}{dt}=0.}
$$

</details>

### Exercise 6: Lorentz invariance of mass shell

Show that if $p^2=m^2$ and $\Lambda^T\eta\Lambda=\eta$, then $(\Lambda p)^2=m^2$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
(\Lambda p)^2
=\eta_{\mu\nu}(\Lambda p)^\mu(\Lambda p)^\nu
=\eta_{\mu\nu}\Lambda^\mu{}_{\rho}\Lambda^\nu{}_{\sigma}p^\rho p^\sigma.
$$

Using the Lorentz condition,

$$
\eta_{\mu\nu}\Lambda^\mu{}_{\rho}\Lambda^\nu{}_{\sigma}
=\eta_{\rho\sigma},
$$

so

$$
(\Lambda p)^2=\eta_{\rho\sigma}p^\rho p^\sigma=p^2=m^2.
$$

Therefore the mass shell is invariant.

</details>

## Sources and further reading

- H. Poincaré, “Sur la dynamique de l'électron,” *Rendiconti del Circolo Matematico di Palermo* **21** (1906), 129–176, for early Lorentz-group and relativistic-dynamics ideas.
- E. Wigner, “On unitary representations of the inhomogeneous Lorentz group,” *Annals of Mathematics* **40** (1939), 149–204, for the classic classification of relativistic particle representations.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§2.3–2.7 and §§5.1–5.9, for the Poincaré algebra, one-particle states, little groups, projective representations, and field transformation laws.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 5, for Noether currents from spacetime symmetries and the stress-tensor route to $P^\mu$ and $M^{\mu\nu}$.
- M. Srednicki, *Quantum Field Theory*, §§2–5 and §33, for Lorentz invariance, scalar quantization, spin-statistics preview, and Lorentz representations.
- R. Haag, *Local Quantum Physics*, chs. I–II, for the algebraic-QFT perspective on spacetime symmetry, locality, and representations.

## Version history

- **2026-05-23:** Initial qft.org page on Poincaré transformations, the Poincaré algebra, Noether charges, field covariance, vacuum invariance, and mass-spin Casimirs.
