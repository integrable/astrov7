---
title: "Gauge Fixing in QED"
description: "Explains why the Maxwell kinetic operator is not invertible before gauge fixing, derives covariant gauges in QED, and shows how gauge fixing preserves physical gauge independence."
sidebar:
  label: "Gauge Fixing in QED"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§55–58 and §§67–68; Schwartz Ch. 8; Coleman lectures on electromagnetic interactions, Faddeev–Popov, and QED in covariant gauge; Weinberg Vol. I QED chapters."
topics:
  - gauge fixing
  - QED
  - Lorenz gauge
  - Faddeev-Popov method
  - covariant gauges
canonicalTopics:
  - qed-gauge-fixing
  - lorenz-gauge
  - faddeev-popov
  - covariant-gauge
researchStatus:
  established:
    - "Perturbative gauge fixing of Abelian QED in covariant gauges is a standard textbook construction; physical gauge independence follows from current conservation and Ward–Takahashi identities."
  active:
    - "Global gauge fixing, boundary conditions, charged-sector dressings, and infrared asymptotic structure are subtler than the local perturbative construction reviewed here."
---

## Summary

Gauge fixing in QED is the step that turns the redundant electromagnetic potential $A_\mu$ into a usable perturbative variable. The Maxwell action is invariant under

$$
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\lambda(x),
$$

so its quadratic operator has zero modes: it cannot be inverted on the full space of vector fields. Since a propagator is the inverse of a quadratic operator, the photon propagator does not exist until we either restrict to physical variables or choose a gauge.

In covariant perturbation theory the standard choice is to add

$$
\mathcal L_{\mathrm{gf}}
=
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2,
$$

so that the gauge-fixed QED Lagrangian is

$$
\mathcal L_\xi
=
-\frac14F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
+\mathcal L_{\mathrm{matter}}.
$$

The parameter $\xi$ labels the covariant gauge. Feynman gauge is $\xi=1$, Landau gauge is the $\xi\to0$ limit, and general $\xi$ is a useful way to check that physical answers do not depend on the gauge choice.

<figure class="doc-figure" style="--figure-width: 49rem;">

![Gauge fixing turns the singular Maxwell kinetic operator into an invertible operator while Abelian ghosts decouple.](/figures/gauge-theories-standard-model/qed-gauge-fixing-kernel.svg)

<figcaption>

The unfixed Maxwell kernel has a longitudinal zero mode, so it cannot be inverted on all $A_\mu$. Adding $-\frac{1}{2\xi}(\partial\!\cdot\!A)^2$ supplies a longitudinal eigenvalue and produces the covariant-gauge photon propagator. In Abelian Lorenz-type gauges the Faddeev–Popov determinant is field-independent, so ghosts decouple.

</figcaption>
</figure>

## Prerequisites

You should know [Maxwell Theory as Gauge Theory](/gauge-theories-standard-model/qed/maxwell-theory-as-gauge-theory/) and the [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/). The key convention is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\mathcal L_{\mathrm{Maxwell}}=-\frac14F_{\mu\nu}F^{\mu\nu},
$$

with mostly-minus metric and plane waves $e^{-ik\cdot x}$. The next page, [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/), performs the inversion of the gauge-fixed quadratic operator derived here.

## Core idea

Gauge fixing is not a small technical decoration. It is the price of using a redundant variable.

The electromagnetic field strength $F_{\mu\nu}$ is gauge invariant, but the potential $A_\mu$ is not. In perturbative QFT we nevertheless use $A_\mu$ because it gives a local Lorentz-covariant description and couples simply to charged matter. This convenience creates a degeneracy: infinitely many configurations of $A_\mu$ represent the same electromagnetic field.

The path integral over all $A_\mu$ therefore contains an infinite overcounting by gauge orbits. The quadratic Maxwell operator also has a corresponding zero direction. Gauge fixing does two related jobs: it controls the overcounting in the path integral, and it makes the quadratic operator invertible so internal photon lines can be defined.

In QED, the simplest covariant gauge fixing is especially gentle. The Abelian Faddeev–Popov determinant is independent of $A_\mu$, so the ghost fields decouple. This is why elementary QED calculations usually contain no ghost diagrams. The same statement fails in non-Abelian Yang–Mills theory, where the Faddeev–Popov determinant depends on the gauge field and ghost loops are essential.

## Setup and conventions

After integrating by parts and discarding boundary terms, the quadratic Maxwell action is

$$
S_0[A]
=
\frac12\int d^4x\,
A_\mu
\Bigl(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu\Bigr)
A_\nu.
$$

In momentum space, using $\partial_\mu\to -ik_\mu$, the quadratic operator is

$$
K_0^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}+k^\mu k^\nu.
$$

It obeys

$$
K_0^{\mu\nu}(k)k_\nu=0.
$$

That equation is the whole problem in one line: the pure-gauge direction $A_\nu(k)\propto k_\nu$ is a zero mode, so $K_0$ has no inverse.

Adding the covariant gauge-fixing term gives

$$
\mathcal L_{\mathrm{gf}}
=
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

The quadratic operator becomes

$$
K_\xi^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}
+\left(1-\frac1\xi\right)k^\mu k^\nu.
$$

For finite nonzero $\xi$, this operator is invertible away from the usual massless pole $k^2=0$. The pole is physical; the gauge zero mode was not.

## The degeneracy of Maxwell theory

The classical Maxwell equations with a source are

$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$

Written in terms of $A_\mu$, this is

$$
\Box A^\nu-\partial^\nu(\partial_\mu A^\mu)=j^\nu.
$$

If $A_\mu=\partial_\mu\lambda$, then $F_{\mu\nu}=0$, and the Maxwell action assigns no cost to this direction. In momentum space this says

$$
A_\mu(k)=k_\mu\lambda(k)
\quad\Longrightarrow\quad
K_0^{\mu\nu}(k)A_\nu(k)=0.
$$

A propagator is an inverse. If a matrix has a zero eigenvalue, it cannot be inverted. Thus the free photon propagator cannot be obtained from the gauge-invariant Maxwell action alone.

This is the sharp distinction between a massless gauge field and an ordinary massless vector field. The Maxwell field has fewer physical degrees of freedom than the four components of $A_\mu$, and the redundancy must be handled before quantization.

## Lorenz gauge

The Lorenz gauge condition is

$$
\partial_\mu A^\mu=0.
$$

It is named after Ludvig Lorenz, not after Lorentz. The condition is Lorentz covariant, which is why the typo is so seductive.

Given a gauge field $A_\mu$, a gauge transformation gives

$$
\partial_\mu A^\mu
\mapsto
\partial_\mu A^\mu+\Box\lambda.
$$

So, locally and with suitable boundary conditions, one can try to choose $\lambda$ so that

$$
\Box\lambda=-\partial_\mu A^\mu.
$$

This brings the transformed field into Lorenz gauge.

Lorenz gauge does not completely fix the gauge. Transformations satisfying

$$
\Box\lambda=0
$$

preserve $\partial\!\cdot\!A=0$. These are residual gauge transformations. In perturbative QED on flat spacetime, with standard boundary conditions and the Feynman $i\epsilon$ prescription, this residual freedom is harmless. In more global questions, boundary conditions and large gauge transformations can carry real information.

## Covariant gauges from the Lagrangian

Instead of imposing $\partial\!\cdot\!A=0$ as a sharp classical constraint, covariant path-integral quantization usually averages over gauges with a Gaussian weight. The result is

$$
\mathcal L_\xi
=
-\frac14F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
+\mathcal L_{\mathrm{matter}}.
$$

The gauge-fixed equation of motion is

$$
\partial_\mu F^{\mu\nu}
+\frac1\xi\partial^\nu(\partial_\mu A^\mu)
=j^\nu,
$$

or

$$
\Box A^\nu
-\left(1-\frac1\xi\right)\partial^\nu(\partial_\mu A^\mu)
=j^\nu.
$$

Two common choices are worth memorizing.

| Gauge | Choice | Main feature |
|---|---:|---|
| Feynman gauge | $\xi=1$ | The quadratic operator is proportional to $\eta^{\mu\nu}\Box$, so the propagator has numerator $\eta_{\mu\nu}$. |
| Landau gauge | $\xi\to0$ | The propagator is transverse in momentum space, $k^\mu D_{\mu\nu}(k)=0$. |

Feynman gauge is algebraically simple. Landau gauge makes transversality manifest. General $\xi$ is often useful because it lets you check that physical answers do not depend on $\xi$.

## Faddeev–Popov in Abelian theory

The path integral over $A_\mu$ overcounts gauge-equivalent configurations. The Faddeev–Popov idea is to insert

$$
1
=
\Delta_{\mathrm{FP}}[A]
\int\mathcal D\lambda\,
\delta\!\bigl(G(A^\lambda)-f\bigr),
$$

where $A^\lambda_\mu=A_\mu+\partial_\mu\lambda$. For Lorenz-type gauge fixing,

$$
G(A)=\partial_\mu A^\mu.
$$

Then

$$
G(A^\lambda)=\partial_\mu A^\mu+\Box\lambda.
$$

Therefore the Faddeev–Popov determinant is

$$
\Delta_{\mathrm{FP}}[A]=\det(\Box),
$$

up to sign and normalization conventions. The important point is that $\det(\Box)$ is independent of $A_\mu$. It can be absorbed into the overall normalization of the QED path integral.

If one exponentiates this determinant using anticommuting ghost fields $c,\bar c$, the ghost action is free:

$$
\mathcal L_{\mathrm{ghost}}=\bar c\,\Box c.
$$

There is no photon–ghost vertex in Abelian QED. Hence ghosts decouple from ordinary QED amplitudes.

## Source conservation and consistency

Taking the divergence of the gauge-fixed equation of motion gives

$$
\frac1\xi\Box(\partial\!\cdot\!A)=\partial_\nu j^\nu.
$$

For matter coupled by QED gauge invariance, the electromagnetic current is conserved:

$$
\partial_\nu j^\nu=0.
$$

Then

$$
\Box(\partial\!\cdot\!A)=0.
$$

In Lorenz gauge, or with appropriate boundary conditions in the path integral, the unphysical longitudinal part does not propagate as an independent physical photon. In perturbation theory, this same fact appears as cancellation of longitudinal terms against conserved currents and Ward–Takahashi identities.

This is a recurring pattern in gauge theory:

$$
\text{gauge fixing introduces unphysical variables,}
\qquad
\text{Ward identities remove them from physics.}
$$

## Relation to canonical quantization

Canonical quantization makes the same difficulty look different. The canonical momentum conjugate to $A_0$ vanishes because the Maxwell Lagrangian contains no $\dot A_0$ term. This is a primary constraint. Varying $A_0$ gives Gauss law,

$$
\nabla\cdot\mathbf E=\rho.
$$

Thus $A_0$ is not an independent propagating degree of freedom. The physical photon has two transverse polarizations, not four components.

Different quantization schemes handle this fact differently.

| Quantization style | What it does |
|---|---|
| Coulomb gauge | Keeps transverse spatial photons explicit; Gauss law generates an instantaneous Coulomb interaction. |
| Covariant gauge | Keeps Lorentz covariance manifest; introduces unphysical longitudinal/time-like components that cancel from physical answers. |
| BRST language | Enlarges the field space and identifies physical states by cohomology; Abelian ghosts are free, non-Abelian ghosts interact. |

This chapter uses covariant gauges because they are the most convenient bridge to relativistic Feynman rules, Ward identities, and later Yang–Mills theory.

## Common pitfalls

**Saying “Lorentz gauge” when you mean Lorenz gauge.** The gauge condition is Lorentz covariant, but the name is Lorenz. It is a tiny typo with suspiciously good camouflage.

**Thinking gauge fixing breaks gauge invariance physically.** Gauge fixing breaks the manifest redundancy of the description, not the gauge independence of physical observables. In the path integral, it is a way of dividing by gauge volume.

**Forgetting residual gauge freedom.** The condition $\partial\!\cdot\!A=0$ still allows transformations with $\Box\lambda=0$. Boundary conditions, $i\epsilon$ prescriptions, and asymptotic assumptions matter.

**Confusing $A_\mu$ with an observable.** The gauge-fixed two-point function $\langle A_\mu A_\nu\rangle$ depends on $\xi$. Gauge-invariant observables are built from $F_{\mu\nu}$, Wilson lines, dressed charged operators, or S-matrix elements with appropriate infrared treatment.

**Assuming Abelian ghost decoupling generalizes.** It does not. In Yang–Mills theory, ghosts interact with gauge bosons and are required for unitarity and Slavnov–Taylor identities.

## Relations to other pages

[QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/) gives the gauge-invariant starting point and the source-current form of QED.

[Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) inverts the gauge-fixed quadratic operator derived here.

[QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) will combine the photon propagator with scalar and spinor interaction terms to form diagrammatic rules.

[Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) explains why gauge-dependent longitudinal pieces cancel from physical amplitudes and renormalized correlation functions.

[Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) generalizes this Abelian discussion to non-Abelian gauge theories, where ghosts no longer decouple.

## Research status

The local perturbative construction of covariant gauge fixing in Abelian QED is settled. The gauge-fixed Lagrangian, Faddeev–Popov determinant, and covariant-gauge photon propagator are standard textbook material.

Several nearby topics remain conceptually and technically subtle: the precise construction of charged asymptotic states in the presence of massless photons, infrared-safe inclusive observables, large gauge transformations at null infinity, edge modes on boundaries, and global gauge fixing on nontrivial manifolds. Those issues do not change the local Feynman rules derived here, but they matter when one asks what the physical Hilbert space and charged observables really are.

## Exercises

1. **Zero mode of the Maxwell operator.** Starting from

   $$
   K_0^{\mu\nu}(k)=-k^2\eta^{\mu\nu}+k^\mu k^\nu,
   $$

   show that $K_0^{\mu\nu}(k)k_\nu=0$.

   <details><summary><strong>Solution</strong></summary>

   Contract directly:

   $$
   K_0^{\mu\nu}k_\nu
   =
   -k^2k^\mu+k^\mu(k^\nu k_\nu)
   =0.
   $$

   This is the momentum-space statement that $A_\mu\propto k_\mu$ is pure gauge.

   </details>

2. **Gauge-fixed equation of motion.** Vary

   $$
   \mathcal L_\xi
   =
   -\frac14F_{\mu\nu}F^{\mu\nu}
   -\frac{1}{2\xi}(\partial\!\cdot\!A)^2
   -j_\mu A^\mu
   $$

   with respect to $A_\nu$ and derive

   $$
   \partial_\mu F^{\mu\nu}
   +\frac1\xi\partial^\nu(\partial\!\cdot\!A)=j^\nu.
   $$

   <details><summary><strong>Solution</strong></summary>

   The Maxwell term gives $\partial_\mu F^{\mu\nu}\delta A_\nu$ after integrating by parts. The gauge-fixing term varies as

   $$
   \delta\mathcal L_{\mathrm{gf}}
   =
   -\frac1\xi(\partial\!\cdot\!A)\partial_\mu\delta A^\mu
   =
   \frac1\xi\partial_\mu(\partial\!\cdot\!A)\delta A^\mu,
   $$

   up to a boundary term. The source term contributes $-j^\nu\delta A_\nu$. Setting the coefficient of $\delta A_\nu$ to zero gives the stated equation.

   </details>

3. **Abelian Faddeev–Popov determinant.** Let $G(A)=\partial_\mu A^\mu$. For $A^\lambda_\mu=A_\mu+\partial_\mu\lambda$, compute $\delta G(A^\lambda)/\delta\lambda$ and explain why the ghosts decouple.

   <details><summary><strong>Solution</strong></summary>

   Since

   $$
   G(A^\lambda)=\partial_\mu A^\mu+\Box\lambda,
   $$

   one has

   $$
   \frac{\delta G(A^\lambda)}{\delta\lambda}=\Box.
   $$

   The determinant is $\det\Box$, independent of $A_\mu$. If represented by ghost fields, the ghost action is free and has no photon–ghost interaction vertex. Therefore ghost loops do not contribute to ordinary Abelian QED amplitudes.

   </details>

4. **Residual Lorenz-gauge transformations.** Suppose $\partial\!\cdot\!A=0$. Which gauge transformations preserve this condition?

   <details><summary><strong>Solution</strong></summary>

   Under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$,

   $$
   \partial\!\cdot\!A\mapsto \partial\!\cdot\!A+\Box\lambda.
   $$

   If $\partial\!\cdot\!A=0$ before and after the transformation, then $\Box\lambda=0$.

   </details>

## References

- M. Srednicki, *Quantum Field Theory*, sections on Maxwell theory, the photon path integral, spinor electrodynamics, and Ward identities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on spin-one fields, gauge invariance, quantization, and the photon propagator.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on electromagnetic interactions, the Faddeev–Popov prescription, and QED in a covariant gauge.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on quantum electrodynamics and covariant perturbation theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on gauge invariance and QED.

## Version history

- 2026-06-17: First polished draft for the QED chapter; fixed conventions to $D_\mu=\partial_\mu+iqA_\mu$ and $A_\mu\mapsto A_\mu+\partial_\mu\lambda$.
