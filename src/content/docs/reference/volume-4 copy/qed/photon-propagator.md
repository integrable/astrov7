---
title: "Photon Propagator"
description: "Derives the covariant-gauge photon propagator in QED, explains its gauge-parameter dependence, and shows how conserved currents remove longitudinal contributions from physical amplitudes."
sidebar:
  label: "Photon Propagator"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§57–61 and §§67–68; Schwartz §§8.4–8.5 and Chs. 13–21; Coleman lectures on QED in covariant gauge and Ward identities; Weinberg Vol. I QED chapters."
topics:
  - photon propagator
  - QED
  - covariant gauge
  - Feynman gauge
  - Ward identities
canonicalTopics:
  - photon-propagator
  - qed
  - feynman-gauge
  - landau-gauge
  - ward-identity
researchStatus:
  established:
    - "The covariant-gauge photon propagator is the standard inverse of the gauge-fixed Maxwell quadratic operator in perturbative QED."
  active:
    - "Photon propagators are gauge-dependent intermediate objects; infrared-safe charged observables and asymptotic photon dressings require additional structure beyond the local propagator formula."
---

## Summary

The photon propagator is the gauge-fixed two-point function of the electromagnetic potential $A_\mu$. In covariant QED gauge with

$$
\mathcal L_{\mathrm{gf}}
=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2,
$$

the momentum-space Feynman propagator is

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

Equivalently, away from the pole one may decompose it into transverse and longitudinal projectors,

$$
P^T_{\mu\nu}=\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2},
\qquad
P^L_{\mu\nu}=\frac{k_\mu k_\nu}{k^2},
$$

so that

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left(P^T_{\mu\nu}+\xi P^L_{\mu\nu}\right).
$$

Feynman gauge has $\xi=1$:

$$
D_{\mu\nu}^{(1)}(k)=\frac{-i\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

Landau gauge has $\xi=0$, making the propagator transverse:

$$
k^\mu D_{\mu\nu}^{(0)}(k)=0.
$$

The propagator depends on $\xi$, so it is not itself an observable. When the photon couples to conserved currents or appears inside complete gauge-invariant amplitudes, the longitudinal gauge-dependent parts cancel.

<figure class="doc-figure" style="--figure-width: 49rem;">

![The covariant-gauge photon propagator decomposes into transverse and longitudinal projectors; conserved currents remove the longitudinal part.](/figures/gauge-theories-standard-model/photon-propagator-projectors.svg)

<figcaption>

The gauge-fixed Maxwell operator is diagonal in transverse and longitudinal projectors. Its inverse is the photon propagator: the transverse coefficient is fixed by Maxwell theory, while the longitudinal coefficient is controlled by the gauge parameter $\xi$. Conserved currents remove the longitudinal part because $k_\mu J^\mu=0$.

</figcaption>
</figure>

## Prerequisites

You should read [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/) first. This page uses its gauge-fixed quadratic operator

$$
K_\xi^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}
+\left(1-\frac1\xi\right)k^\mu k^\nu.
$$

You should also know the [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/) and the volume conventions: mostly-minus metric, plane waves $e^{-ik\cdot x}$, and Abelian field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The page assumes familiarity with scalar Feynman propagators. The photon propagator has the same massless pole structure, but its numerator remembers that $A_\mu$ is a gauge-fixed vector field rather than a scalar observable.

## Core idea

The photon propagator is simple only after one accepts a conceptual warning label:

$$
\text{the propagator of } A_\mu \text{ is gauge dependent.}
$$

That warning is not a bug. It is exactly what should happen. The potential $A_\mu$ is a redundant variable, and different choices of gauge correspond to different ways of coordinatizing the same physical photon degrees of freedom.

A covariant gauge keeps Lorentz symmetry manifest by allowing four components of $A_\mu$ to propagate internally. The extra longitudinal and time-like components are not physical external photon states. They cancel from gauge-invariant observables through current conservation and Ward–Takahashi identities.

In calculations, this means: internal photon lines use the gauge-fixed propagator; external photons use physical polarization vectors or Ward-identity-safe replacements; complete physical answers must not depend on $\xi$.

## Setup and conventions

The gauge-fixed free photon Lagrangian is

$$
\mathcal L_{0,\xi}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

After integrating by parts,

$$
S_{0,\xi}
=
\frac12\int d^4x\,
A_\mu
\left[
\eta^{\mu\nu}\Box
-\left(1-\frac1\xi\right)\partial^\mu\partial^\nu
\right]
A_\nu.
$$

In momentum space,

$$
S_{0,\xi}
=
\frac12\int\frac{d^4k}{(2\pi)^4}\,
A_\mu(-k)K_\xi^{\mu\nu}(k)A_\nu(k),
$$

where

$$
K_\xi^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}
+\left(1-\frac1\xi\right)k^\mu k^\nu.
$$

The Feynman propagator is $i$ times the inverse of this quadratic operator, with the pole prescription $k^2\to k^2+i\epsilon$.

We define the two-point function by

$$
\langle0|T A_\mu(x)A_\nu(y)|0\rangle
=
\int\frac{d^4k}{(2\pi)^4}\,
D_{\mu\nu}^{(\xi)}(k)e^{-ik\cdot(x-y)}.
$$

## Inverting the quadratic operator

The cleanest inversion uses projectors. For $k^2\neq0$, define

$$
P^T_{\mu\nu}=\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2},
\qquad
P^L_{\mu\nu}=\frac{k_\mu k_\nu}{k^2}.
$$

They obey

$$
P^T+P^L=\eta,
\qquad
P^TP^T=P^T,
\qquad
P^LP^L=P^L,
\qquad
P^TP^L=0.
$$

The gauge-fixed quadratic operator becomes

$$
K_\xi
=
-k^2P^T-\frac{k^2}{\xi}P^L.
$$

Its inverse is therefore

$$
K_\xi^{-1}
=
-\frac1{k^2}P^T-\frac{\xi}{k^2}P^L.
$$

Multiplying by $i$ and adding the Feynman prescription gives

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left(P^T_{\mu\nu}+\xi P^L_{\mu\nu}\right).
$$

In ordinary tensor form this is

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

The two formulas express the same algebraic decomposition. The second form is usually safer near the pole because it keeps the Feynman prescription visible.

## Special covariant gauges

The most common covariant gauges are these.

| Gauge | Parameter | Propagator numerator | Use |
|---|---:|---|---|
| Feynman gauge | $\xi=1$ | $\eta_{\mu\nu}$ | Minimizes numerator algebra. |
| Landau gauge | $\xi=0$ | $\eta_{\mu\nu}-k_\mu k_\nu/k^2$ | Makes transversality manifest. |
| General covariant gauge | arbitrary $\xi$ | $\eta_{\mu\nu}-(1-\xi)k_\mu k_\nu/k^2$ | Tracks gauge-parameter cancellation. |

In Feynman gauge,

$$
D_{\mu\nu}^{(1)}(k)
=
\frac{-i\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

This looks like four independent massless scalar propagators times $-\eta_{\mu\nu}$, but that interpretation is too literal. The gauge-fixed field has unphysical components, and only complete gauge-invariant quantities have direct physical meaning.

In Landau gauge,

$$
D_{\mu\nu}^{(0)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2+i\epsilon}\right],
$$

so $k^\mu D_{\mu\nu}^{(0)}(k)=0$, up to the usual distributional care at the pole.

## Contraction with conserved currents

Suppose two conserved currents exchange a photon with momentum $k$:

$$
k_\mu J^\mu(k)=0,
\qquad
k_\nu J'^\nu(-k)=0.
$$

The photon line contributes

$$
J^\mu(k)D_{\mu\nu}^{(\xi)}(k)J'^\nu(-k).
$$

The longitudinal term is proportional to

$$
J^\mu k_\mu\,k_\nu J'^\nu,
$$

which vanishes. Hence

$$
J^\mu D_{\mu\nu}^{(\xi)}J'^\nu
=
\frac{-i}{k^2+i\epsilon}J_\mu J'^\mu.
$$

This is the elementary reason gauge-parameter dependence disappears from tree-level exchange between conserved currents.

The loop-level statement is more subtle but structurally the same. Individual diagrams and off-shell Green functions can depend on $\xi$. Complete physical amplitudes and gauge-invariant correlation functions do not. The precise quantum identities enforcing this are Ward–Takahashi identities.

## Photon propagator versus physical polarization sum

Do not confuse the internal photon propagator with a sum over physical external photon polarizations.

For an internal photon line in covariant gauge, use $D_{\mu\nu}^{(\xi)}(k)$. For an external photon, use a polarization vector $\varepsilon_\mu(k)$ satisfying

$$
k^\mu\varepsilon_\mu(k)=0,
\qquad
k^2=0,
$$

with only two physical helicities. A change

$$
\varepsilon_\mu(k)\mapsto \varepsilon_\mu(k)+c\,k_\mu
$$

is a gauge change of the external polarization. Physical amplitudes are invariant under this replacement.

Feynman gauge often tempts one to replace physical polarization sums by $-\eta_{\mu\nu}$. This is allowed only when the remaining expression is Ward-identity safe, so that longitudinal contributions vanish. Otherwise, use a physical polarization basis or a gauge-invariant polarization-sum formula with a reference vector.

## Coordinate-space interpretation

The propagator satisfies the Green-function equation

$$
\left[
\eta^{\mu\rho}\Box
-\left(1-\frac1\xi\right)\partial^\mu\partial^\rho
\right]
D_{\rho\nu}^{(\xi)}(x-y)
=i\delta^\mu_{\ \nu}\delta^{(4)}(x-y),
$$

with Feynman boundary conditions. This equation is the vector analogue of the scalar propagator equation.

In Feynman gauge,

$$
D_{\mu\nu}^{(1)}(x-y)=-\eta_{\mu\nu}\Delta_F(x-y),
$$

where the massless scalar Feynman propagator in the same convention is

$$
\Delta_F(k)=\frac{i}{k^2+i\epsilon}.
$$

The minus sign follows from the vector kinetic operator and mostly-minus metric conventions.

## Static limit and Coulomb exchange

For slowly moving charges, the dominant component is the $00$ component. In Feynman gauge,

$$
D_{00}(k)=\frac{-i\eta_{00}}{k^2+i\epsilon}=\frac{-i}{k^2+i\epsilon}.
$$

In the static limit $k^0=0$, one has $k^2=-\mathbf k^2$, so

$$
D_{00}(0,\mathbf k)=\frac{i}{\mathbf k^2}.
$$

Combined with the QED vertices and source signs, this produces the familiar momentum-space Coulomb factor proportional to $1/\mathbf k^2$. The Coulomb potential itself is gauge invariant. The split between instantaneous Coulomb exchange and propagating transverse photons depends on gauge: Coulomb gauge makes that split explicit, while covariant gauges hide it inside a Lorentz-covariant propagator.

## Massive vector comparison

A massive Proca field has no gauge redundancy. Its propagator is commonly written as

$$
D_{\mu\nu}^{\mathrm{Proca}}(k)
=
\frac{-i}{k^2-m^2+i\epsilon}
\left(\eta_{\mu\nu}-\frac{k_\mu k_\nu}{m^2}\right).
$$

This is not the photon propagator with a small mass inserted by hand. The massless limit of a massive vector field is subtle because a massive spin-one particle has three polarizations, while a photon has two. Gauge theory handles the massless limit by keeping redundancy and removing unphysical components through gauge invariance.

## Common pitfalls

**Treating the photon propagator as observable.** The $A_\mu$ two-point function depends on $\xi$. Gauge-invariant information is found in physical amplitudes, current-current exchange, $F_{\mu\nu}$ correlators, Wilson lines, or properly dressed charged observables.

**Forgetting the longitudinal term in general gauge.** In Feynman gauge it disappears from the numerator, but in general $\xi$ it must be carried until current conservation or a Ward identity removes it.

**Using current conservation too early.** Internal subdiagrams are often off shell. You may only drop longitudinal pieces when the object they hit is known to obey the appropriate Ward identity or conservation law.

**Confusing Feynman gauge with a physical polarization sum.** The numerator $-i\eta_{\mu\nu}$ is a propagator numerator, not a statement that the photon has four physical polarizations.

**Losing the $i\epsilon$ prescription.** The photon is massless, so the pole structure matters. Keep $k^2+i\epsilon$ visible, especially when Fourier transforming or comparing to retarded and advanced Green functions.

## Relations to other pages

[Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/) derives the gauge-fixed quadratic operator inverted here.

[QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) combines this propagator with scalar and spinor QED interaction vertices.

[Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) proves the quantum identities that remove gauge-dependent longitudinal terms from physical amplitudes.

[Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) studies the first loop correction to this propagator and explains why the photon self-energy is transverse.

[Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/) interprets the renormalized photon two-point function as charge screening in QED.

## Research status

The covariant-gauge photon propagator is settled textbook material. Its derivation, gauge-parameter dependence, and cancellation between conserved currents are standard.

The deeper infrared meaning of photons and charged particles remains a rich topic. The local propagator is not by itself a complete description of asymptotic charged states in QED. Inclusive observables, coherent soft-photon dressings, memory effects, and large gauge symmetries at null infinity refine the simple perturbative picture. Those topics do not alter the local propagator, but they determine how to turn QED amplitudes into fully physical charged-sector predictions.

## Exercises

1. **Invert the gauge-fixed operator.** Starting from

   $$
   K_\xi=-k^2P^T-\frac{k^2}{\xi}P^L,
   $$

   show that

   $$
   iK_\xi^{-1}=\frac{-i}{k^2}(P^T+\xi P^L).
   $$

   <details><summary><strong>Solution</strong></summary>

   Since $P^T$ and $P^L$ are orthogonal projectors, invert the two subspaces separately:

   $$
   K_\xi^{-1}=-\frac1{k^2}P^T-\frac{\xi}{k^2}P^L.
   $$

   Multiplying by $i$ gives the result, with $k^2\to k^2+i\epsilon$ understood for the Feynman propagator.

   </details>

2. **Longitudinal contraction.** Show that

   $$
   k^\mu D_{\mu\nu}^{(\xi)}(k)=\frac{-i\xi k_\nu}{k^2+i\epsilon}.
   $$

   <details><summary><strong>Solution</strong></summary>

   Use the projector form. Since $k^\mu P^T_{\mu\nu}=0$ and $k^\mu P^L_{\mu\nu}=k_\nu$,

   $$
   k^\mu D_{\mu\nu}^{(\xi)}
   =
   \frac{-i\xi k_\nu}{k^2+i\epsilon}.
   $$

   In Landau gauge, $\xi=0$, this contraction vanishes.

   </details>

3. **Current-current gauge independence.** Let $k_\mu J^\mu=k_\nu J'^\nu=0$. Prove that $J^\mu D_{\mu\nu}^{(\xi)}J'^\nu$ is independent of $\xi$.

   <details><summary><strong>Solution</strong></summary>

   The $\xi$-dependent part is proportional to $J^\mu k_\mu\,k_\nu J'^\nu$, which vanishes by current conservation. Therefore

   $$
   J^\mu D_{\mu\nu}^{(\xi)}J'^\nu
   =
   \frac{-i}{k^2+i\epsilon}J\cdot J'.
   $$

   </details>

4. **Projector algebra.** Verify that $P^T$ and $P^L$ are projectors and that $P^TP^L=0$.

   <details><summary><strong>Solution</strong></summary>

   Since $P^L_{\mu\nu}=k_\mu k_\nu/k^2$,

   $$
   (P^L)^\mu_{\ \rho}(P^L)^\rho_{\ \nu}
   =
   \frac{k^\mu k_\rho}{k^2}\frac{k^\rho k_\nu}{k^2}
   =
   \frac{k^\mu k_\nu}{k^2}
   =
   (P^L)^\mu_{\ \nu}.
   $$

   Since $P^T=\eta-P^L$,

   $$
   (P^T)^2=(\eta-P^L)^2=\eta-2P^L+(P^L)^2=P^T,
   $$

   and $P^TP^L=(\eta-P^L)P^L=0$.

   </details>

## References

- M. Srednicki, *Quantum Field Theory*, sections on Maxwell theory, photon path integrals, spinor electrodynamics, and Ward identities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on spin-one fields, gauge invariance, the photon propagator, and path integrals.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on massless electrodynamics, the Faddeev–Popov prescription, covariant-gauge QED, and Ward identities.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on quantum electrodynamics and covariant perturbation theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on gauge invariance, QED, and vacuum polarization.

## Version history

- 2026-06-17: First polished draft for the QED chapter; derived the covariant-gauge propagator in the volume conventions and separated propagator gauge dependence from physical polarization sums.
