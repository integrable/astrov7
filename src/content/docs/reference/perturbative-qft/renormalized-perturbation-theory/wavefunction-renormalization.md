---
title: "Wavefunction Renormalization"
description: "How field-strength renormalization, pole residues, LSZ factors, anomalous dimensions, and kinetic counterterms are related but not identical."
sidebar:
  label: "Wavefunction Renormalization"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§13–16, 19, and 41–46; Coleman 2019, chs. 15, 23, and 32; Weinberg 1995, Vol. I, chs. 10 and 12; Schwartz 2014, chs. 18–20 and 23; Zinn-Justin 2021, chs. 7–10"
topics:
  - wavefunction renormalization
  - field-strength renormalization
  - pole residue
  - LSZ normalization
  - anomalous dimension
canonicalTopics:
  - wavefunction-renormalization
  - field-strength-renormalization
  - pole-residue
  - lsz-factor
  - anomalous-dimension
researchStatus:
  established:
    - "Wavefunction renormalization is the standard field-strength renormalization needed to make two-point functions finite, define pole residues, and track anomalous dimensions in renormalized perturbation theory."
  active:
    - "In gauge theories, unstable-particle schemes, composite-operator mixing, nonperturbative definitions, and precision calculations, field renormalization remains scheme-dependent and technically delicate."
---

## Summary

**Wavefunction renormalization** is better called **field-strength renormalization**. It relates a bare field to a renormalized field,

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z.
$$

The name is historical. In relativistic QFT, $\phi$ is not a single-particle wavefunction. The factor $Z_\phi$ is a renormalization of the field used in correlation functions.

For a scalar field, the kinetic counterterm is

$$
\mathcal L_{\rm ct}^{(2)}
\supset
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi,
$$

which contributes the two-point counterterm vertex

$$
 i(p^2\delta Z-\delta m^2).
$$

Field-strength renormalization is closely related to the pole residue of the propagator, but they are not the same object in every scheme. For a stable scalar particle, the exact renormalized propagator behaves near its pole as

$$
G(p)
\sim
\frac{iZ_{\rm pole}}{p^2-M^2+i\epsilon}
+
\text{regular terms}.
$$

With the scalar self-energy convention

$$
G(p)=\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon},
$$

the pole residue is

$$
Z_{\rm pole}^{-1}
=
1-\Sigma_{\rm ren}'(M^2).
$$

An on-shell scheme chooses counterterms so that $Z_{\rm pole}=1$. Minimal subtraction usually does not. LSZ reduction then supplies the appropriate external-leg residue factors.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Map relating the bare field, the renormalized field, the self-energy slope, the propagator pole residue, and LSZ external-particle factors](/figures/perturbative-qft/wavefunction-renormalization-map.svg)

<figcaption>

The bare field split $\phi_0=Z_\phi^{1/2}\phi$ defines a scheme-dependent field normalization. The pole residue $Z_{\rm pole}$ is extracted from the exact two-point function for a stable particle. LSZ reduction converts interpolating fields into external-particle amplitudes using the pole residue.

</figcaption>
</figure>

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/), [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/), and [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/).

For scattering uses of external factors, review [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) and [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/).

## Core idea

Two-point functions do more than locate masses. They also normalize fields.

At tree level, the scalar propagator is

$$
G_0(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The coefficient of $p^2$ in the inverse propagator is one. Loop corrections change the two-point function. Some loop corrections shift the pole; some change the slope at the pole; some generate branch cuts and spectral continua. The field-strength counterterm is the local kinetic counterterm that absorbs the ultraviolet-divergent part of the slope.

The most useful conceptual separation is

$$
Z_\phi
\text{ is a scheme-dependent field-renormalization factor,}
$$

while

$$
Z_{\rm pole}
\text{ is the residue of a stable one-particle pole.}
$$

Many books use the same letter $Z$ for both. That shortcut is survivable once one is fluent, but it is a factory for mistakes while learning. On QFT.org we will usually distinguish them when both appear.

## Setup and conventions

We use qft.org mostly-minus conventions. For scalar examples,

$$
\mathcal L_{\rm ren}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
+\mathcal L_{\rm int},
$$

and

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2.
$$

In momentum space, the quadratic counterterm contributes

$$
\frac12\int_p
\phi(-p)
\left(p^2\delta Z-\delta m^2\right)
\phi(p),
$$

so the counterterm vertex is

$$
 i(p^2\delta Z-\delta m^2).
$$

The scalar one-particle-irreducible two-point insertion is written

$$
\text{1PI two-point insertion}=-i\Sigma(p^2).
$$

With these conventions,

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2.
$$

The resummed scalar propagator is

$$
G(p)=
\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon}.
$$

## Field-strength counterterms

The field split

$$
\phi_0=Z_\phi^{1/2}\phi
$$

means that the bare kinetic term becomes

$$
\frac12\partial_\mu\phi_0\partial^\mu\phi_0
=
\frac12Z_\phi\partial_\mu\phi\partial^\mu\phi.
$$

Writing

$$
Z_\phi=1+\delta Z,
$$

we get

$$
\frac12Z_\phi\partial_\mu\phi\partial^\mu\phi
=
\frac12\partial_\mu\phi\partial^\mu\phi
+
\frac12\delta Z\partial_\mu\phi\partial^\mu\phi.
$$

The first term is placed in the renormalized Lagrangian. The second is the field-strength counterterm.

Why is a kinetic counterterm needed? Because a divergent two-point 1PI function can contain a local term proportional to $p^2$. In position space, such a divergence has the form

$$
\partial_\mu\phi\partial^\mu\phi.
$$

The coefficient of this local divergence is removed by $\delta Z$.

## Pole residue for a scalar particle

Let the physical stable one-particle pole occur at

$$
p^2=M^2.
$$

The pole condition is

$$
M^2-m^2-\Sigma_{\rm ren}(M^2)=0.
$$

Define the denominator

$$
D(p^2)=p^2-m^2-\Sigma_{\rm ren}(p^2).
$$

Near the pole,

$$
D(p^2)
=
(p^2-M^2)D'(M^2)+\cdots.
$$

Since

$$
D'(M^2)=1-\Sigma_{\rm ren}'(M^2),
$$

the propagator behaves as

$$
G(p)
\sim
\frac{i}{(p^2-M^2)\left[1-\Sigma_{\rm ren}'(M^2)\right]+i\epsilon}.
$$

Thus

$$
Z_{\rm pole}
=
\frac{1}{1-\Sigma_{\rm ren}'(M^2)},
\qquad
Z_{\rm pole}^{-1}=1-\Sigma_{\rm ren}'(M^2).
$$

This formula assumes an isolated stable pole. If the particle is unstable, the pole moves off the real axis. If the field creates a confined excitation rather than an asymptotic particle, there may be no physical one-particle pole of this kind.

## On-shell versus minimal subtraction

In an on-shell scheme for a stable scalar particle, one imposes

$$
\operatorname{Re}\Sigma_{\rm ren}(M^2)=0,
\qquad
\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0.
$$

The derivative condition gives

$$
Z_{\rm pole}=1.
$$

Using

$$
\Sigma_{\rm ren}'(p^2)
=
\Sigma_{\rm loop}'(p^2)-\delta Z,
$$

the on-shell field-strength counterterm is

$$
\delta Z_{\rm OS}
=
\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

This includes both divergent and finite pieces.

In MS or $\overline{\mathrm{MS}}$, the rule is instead

$$
\delta Z_{\rm MS}
=
\text{pole part of }\Sigma_{\rm loop}'(p^2).
$$

No finite residue condition is imposed. Therefore $Z_{\rm pole}$ is generally not one in an MS scheme. That is not an error; it is the definition of the scheme.

## What LSZ does with the residue

The field $\phi$ is an interpolating field. It creates a one-particle state from the vacuum with an overlap

$$
\langle0|\phi(0)|\mathbf p\rangle
=
\sqrt{Z_{\rm pole}}
$$

for a stable scalar particle, up to the state-normalization conventions. This overlap is what appears as the pole residue in the two-point function.

Schematically, the LSZ formula converts an $n$-point Green function into an S-matrix element by multiplying by inverse propagator factors and by one residue factor for each external leg:

$$
\mathcal M
\sim
Z_{\rm pole}^{-n/2}
\left[\prod_{a=1}^n(p_a^2-M^2)\right]
G_n(p_1,\ldots,p_n)
\bigg|_{p_a^2\to M^2}.
$$

The exact factors of $i$ and signs depend on the detailed LSZ convention, but the residue logic is robust. If the renormalized field has unit pole residue, the explicit $Z_{\rm pole}^{-1/2}$ factors disappear. If it does not, they must be included.

This is why field normalization is not just cosmetic. It affects the relation between Green functions and scattering amplitudes.

## Example: φ⁴ theory at one loop

In four-dimensional real $\phi^4$ theory, the one-loop self-energy is the tadpole diagram. Its loop integral is independent of the external momentum:

$$
\Sigma_{\rm loop}^{(1)}(p^2)=\text{constant in }p^2.
$$

Therefore

$$
\frac{d}{dp^2}\Sigma_{\rm loop}^{(1)}(p^2)=0.
$$

So, in an MS-type scheme,

$$
\delta Z^{(1)}=0
\qquad
\text{in four-dimensional }\phi^4\text{ theory}.
$$

This does not mean wavefunction renormalization is unimportant. It means the first scalar $\phi^4$ diagram that produces momentum-dependent two-point UV divergence appears later, at two loops through the sunset topology. In other theories, such as $\phi^3$ theory in six dimensions, Yukawa theory, QED, or Yang–Mills theory, field-strength renormalization already appears at one loop.

## Fermions and gauge fields

For a Dirac field,

$$
\psi_0=Z_\psi^{1/2}\psi.
$$

The free propagator has numerator $p\!\!\!/+m$, where

$$
p\!\!\!/=\gamma^\mu p_\mu.
$$

The one-particle pole residue is extracted from the full matrix-valued propagator. Near a stable fermion pole, the propagator has the schematic form

$$
S(p)
\sim
\frac{iZ_{\psi,\rm pole}(p\!\!\!/+M)}{p^2-M^2+i\epsilon}
+
\text{regular terms}.
$$

The actual extraction can involve decomposing the self-energy into $p\!\!\!/$ and mass structures. The principle is the same: the kinetic part of the self-energy controls the field-strength counterterm and the pole residue.

For a gauge field,

$$
A_{0\mu}=Z_A^{1/2}A_\mu.
$$

The field-strength factor $Z_A$ is gauge- and scheme-dependent. Ward or Slavnov–Taylor identities relate it to other renormalization constants. For example, in QED the Ward identity implies the equality of the vertex and electron field renormalization constants in common conventions,

$$
Z_1=Z_2.
$$

Gauge-field wavefunction renormalization is therefore not merely a matter of normalizing a photon field. It is tied to charge renormalization and gauge symmetry.

## Anomalous dimensions

Field-strength renormalization also defines an anomalous dimension. With the convention

$$
\gamma_\phi(\mu)
\equiv
\frac12\mu\frac{d}{d\mu}\ln Z_\phi
\bigg|_{\rm bare},
$$

fixed bare fields imply

$$
\mu\frac{d\phi}{d\mu}
=
-\gamma_\phi\phi.
$$

For renormalized $n$-point functions, this produces field-scaling terms in RG equations. A schematic massless Callan–Symanzik equation has the form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta_i\frac{\partial}{\partial g_i}
+n\gamma_\phi
\right)
G^{(n)}_{\rm ren}=0,
$$

up to sign conventions and possible mass, operator-mixing, and gauge-parameter terms.

The anomalous dimension is not usually an observable by itself. At fixed points, however, anomalous dimensions contribute to scaling dimensions of operators, and those are physical CFT data in unitary conformal theories.

## Rescaling fields is not harmless bookkeeping

Classically, one might think field normalization is arbitrary: rescale $\phi\mapsto a\phi$ and compensate by changing couplings. In quantum theory, that intuition is partly right and partly dangerous.

It is right because local field rescalings can be viewed as changes of variables and scheme choices. Properly computed S-matrix elements do not depend on a convention for normalizing an unphysical interpolating field.

It is dangerous because field normalization enters:

| Object | Why field strength matters |
|---|---|
| Propagators | It controls the coefficient of the pole and the kinetic counterterm. |
| LSZ reduction | External-particle amplitudes require the correct pole residue. |
| RG equations | $Z_\phi$ defines anomalous dimensions. |
| Gauge theories | Ward and Slavnov–Taylor identities relate field and coupling renormalization. |
| Composite operators | Operator renormalization mixes with field renormalization. |

The safe rule is: field rescalings are allowed, but every induced change in propagators, vertices, counterterms, and external factors must be carried along.

## Common pitfalls

**Calling $\phi$ a wavefunction.** The term “wavefunction renormalization” is historical. The quantum field is an operator or path-integral variable, not a first-quantized wavefunction.

**Confusing $Z_\phi$ with $Z_{\rm pole}$.** $Z_\phi$ is a scheme-dependent renormalization constant. $Z_{\rm pole}$ is the residue of a stable one-particle pole. They coincide only under special choices and notations.

**Forgetting finite parts in on-shell schemes.** On-shell $\delta Z$ fixes the pole residue, so it includes finite pieces. MS $\delta Z$ subtracts only pole pieces.

**Assuming $\delta Z$ is always nonzero at one loop.** In four-dimensional $\phi^4$ theory, the one-loop tadpole is momentum independent, so $\delta Z^{(1)}=0$. Other theories differ.

**Using pole residues for unstable particles as if they were external LSZ factors.** Unstable particles are not asymptotic states. Their propagators have complex poles, and the treatment of residues is more subtle.

**Ignoring gauge dependence.** Field renormalization constants for gauge-dependent fields are generally gauge dependent. Physical S-matrix elements or gauge-invariant observables are not.

## Relations to other pages

- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) introduces $\Sigma(p^2)$ and the resummed propagator.
- [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/) imposes unit pole residue as a renormalization condition.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) fixes $\delta Z$ by pole subtraction rather than by a physical residue condition.
- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains why pole residues enter external-particle amplitudes.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) tracks external factors in scattering conventions.
- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) derives the kinetic counterterm vertex $i(p^2\delta Z-\delta m^2)$.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) will use field-strength factors in complete S-matrix calculations.

## Research status

- **Established:** Field-strength renormalization, pole residues, LSZ residue factors, and anomalous dimensions are standard parts of perturbative QFT.
- **Active:** Gauge-dependent field renormalization, unstable-particle residues, multi-loop anomalous dimensions, evanescent-field effects, composite-operator mixing, and nonperturbative residue definitions remain technically important.
- **Speculative:** The perturbative definitions here are not speculative. Interpretations become subtler when fields do not interpolate physical particles, as in confinement or gauge-redundant descriptions.

## Exercises

### Exercise 1: Derive the pole residue

Starting from

$$
G(p)=\frac{i}{p^2-m^2-\Sigma_{\rm ren}(p^2)+i\epsilon},
$$

show that near a stable pole $p^2=M^2$,

$$
Z_{\rm pole}^{-1}=1-\Sigma_{\rm ren}'(M^2).
$$

<details>
<summary><strong>Solution</strong></summary>

The pole condition is

$$
M^2-m^2-\Sigma_{\rm ren}(M^2)=0.
$$

Let

$$
D(p^2)=p^2-m^2-\Sigma_{\rm ren}(p^2).
$$

Taylor expand around $p^2=M^2$:

$$
D(p^2)=D(M^2)+(p^2-M^2)D'(M^2)+\cdots.
$$

The first term vanishes by the pole condition. The derivative is

$$
D'(M^2)=1-\Sigma_{\rm ren}'(M^2).
$$

Therefore

$$
G(p)
\sim
\frac{i}{(p^2-M^2)[1-\Sigma_{\rm ren}'(M^2)]+i\epsilon}.
$$

Comparing with

$$
G(p)\sim\frac{iZ_{\rm pole}}{p^2-M^2+i\epsilon}
$$

gives

$$
Z_{\rm pole}^{-1}=1-\Sigma_{\rm ren}'(M^2).
$$

</details>

### Exercise 2: On-shell field-strength counterterm

Using

$$
\Sigma_{\rm ren}(p^2)=\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2,
$$

show that the on-shell residue condition $\operatorname{Re}\Sigma_{\rm ren}'(M^2)=0$ implies

$$
\delta Z_{\rm OS}=\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the renormalized self-energy:

$$
\Sigma_{\rm ren}'(p^2)
=
\Sigma_{\rm loop}'(p^2)-\delta Z.
$$

The on-shell condition is

$$
0=\operatorname{Re}\Sigma_{\rm ren}'(M^2)
=\operatorname{Re}\Sigma_{\rm loop}'(M^2)-\delta Z.
$$

Thus

$$
\delta Z_{\rm OS}=\operatorname{Re}\Sigma_{\rm loop}'(M^2).
$$

</details>

### Exercise 3: Why the one-loop φ⁴ tadpole gives no δZ

In four-dimensional $\phi^4$ theory, the one-loop tadpole self-energy is independent of the external momentum. Explain why this implies $\delta Z^{(1)}=0$ in an MS-type scheme.

<details>
<summary><strong>Solution</strong></summary>

The field-strength counterterm cancels the divergent part proportional to $p^2$ in the self-energy. Equivalently, it is fixed by the pole part of

$$
\Sigma_{\rm loop}'(p^2).
$$

For the one-loop tadpole,

$$
\Sigma_{\rm loop}^{(1)}(p^2)=\text{constant},
$$

so

$$
\Sigma_{\rm loop}^{(1)\prime}(p^2)=0.
$$

There is no momentum-dependent one-loop divergence to cancel. Hence

$$
{\delta Z^{(1)}=0}
$$

in an MS-type scheme for this model.

</details>

### Exercise 4: LSZ residue factor

Suppose a scalar four-point connected Green function has one-particle pole residue $Z_{\rm pole}$ for each external leg. What overall residue factor converts the amputated on-shell Green function into the corresponding four-particle amplitude?

<details>
<summary><strong>Solution</strong></summary>

Each external scalar leg contributes a factor

$$
Z_{\rm pole}^{-1/2}
$$

in LSZ reduction. For four external particles, the product is

$$
\left(Z_{\rm pole}^{-1/2}\right)^4
=
{Z_{\rm pole}^{-2}.}
$$

If the on-shell scheme has chosen $Z_{\rm pole}=1$, this factor is one.

</details>

### Exercise 5: Field running from the anomalous dimension

With

$$
\gamma_\phi=\frac12\mu\frac{d}{d\mu}\ln Z_\phi\bigg|_{\rm bare},
$$

use $\phi_0=Z_\phi^{1/2}\phi$ to show that

$$
\mu\frac{d\phi}{d\mu}=-\gamma_\phi\phi
$$

at fixed bare field.

<details>
<summary><strong>Solution</strong></summary>

Differentiate

$$
\phi_0=Z_\phi^{1/2}\phi
$$

at fixed $\phi_0$:

$$
0=
\mu\frac{d}{d\mu}\left(Z_\phi^{1/2}\phi\right).
$$

This gives

$$
0=
Z_\phi^{1/2}
\left[
\frac12\mu\frac{d\ln Z_\phi}{d\mu}\phi
+
\mu\frac{d\phi}{d\mu}
\right].
$$

Using the definition of $\gamma_\phi$,

$$
0=Z_\phi^{1/2}
\left[
\gamma_\phi\phi+
\mu\frac{d\phi}{d\mu}
\right],
$$

so

$$
\mu\frac{d\phi}{d\mu}=-\gamma_\phi\phi.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§13–16 and §§41–46, for spectral residues, self-energies, LSZ normalization, scalar and fermion field-strength factors.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15 and 23, for renormalized propagators and field-strength renormalization in scalar and spinor examples.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10 and 12, for renormalization constants, LSZ-related normalization, and the general perturbative framework.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–20 and 23, for mass renormalization, counterterms, field renormalization, and RG equations.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 7–10, for generating functionals, vertex functions, field renormalization, and anomalous dimensions.

## Version history

- **2026-06-12:** Initial polished draft. Added distinction between $Z_\phi$ and $Z_{\rm pole}$, scalar residue derivation, on-shell versus MS field-strength conditions, LSZ factors, anomalous-dimension convention, solved exercises, and a compact wavefunction-renormalization map.
