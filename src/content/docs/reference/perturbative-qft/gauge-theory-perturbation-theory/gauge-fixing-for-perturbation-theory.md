---
title: "Gauge Fixing for Perturbation Theory"
description: "Why perturbative gauge theory needs gauge fixing, how covariant gauges make the gauge-field kinetic operator invertible, and what gauge dependence means for amplitudes."
sidebar:
  label: "Gauge Fixing"
  order: 1
level: Graduate
status: "Polished draft"
source: "Faddeev and Popov 1967; Weinberg Vol. II ch. 15; Srednicki §§69–72; Schwartz chs. 25–26; Coleman chs. 31 and 47"
topics:
  - gauge fixing
  - covariant gauges
  - Yang–Mills perturbation theory
  - gauge-field propagators
canonicalTopics:
  - gauge-fixing-for-perturbation-theory
  - covariant-gauge-propagators
  - faddeev-popov-method
researchStatus:
  established:
    - "Gauge fixing is the standard perturbative method for replacing gauge-redundant integration over gauge fields by an invertible propagator and a corresponding Faddeev–Popov determinant."
  active:
    - "Perturbative gauge fixing is locally reliable around weak fields; global nonperturbative issues such as Gribov copies and gauge fixing on lattice configuration space belong to later nonperturbative pages."
---

## Summary

Gauge fields contain redundant variables. The vector potential $A_\mu^a$ is not a coordinate on physical configuration space; it is a coordinate on a larger space in which many field configurations represent the same physics. Perturbation theory cannot ignore that redundancy, because the quadratic gauge-field kinetic operator has zero modes along gauge orbits and therefore has no ordinary inverse.

Gauge fixing is the procedure that makes the free gauge-field propagator well defined. In a covariant gauge for a Yang–Mills theory, one adds

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2,
$$

giving the momentum-space propagator

$$
D_{\mu\nu}^{ab}(k)
=\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

The gauge parameter $\xi$ is not a physical parameter. It changes intermediate propagators and diagrams, but gauge-invariant observables and properly defined S-matrix elements are independent of it. In non-Abelian gauge theory, gauge fixing also produces the Faddeev–Popov determinant, which becomes ghost fields in diagrammatic perturbation theory.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![Gauge fixing selects a local slice through a gauge orbit and makes the quadratic operator invertible](/figures/perturbative-qft/gauge-fixing-perturbation.svg)

<figcaption>

Gauge fixing chooses one representative, locally, from each gauge orbit. Perturbatively this replaces a singular gauge-field kinetic operator by an invertible one and produces a gauge-dependent propagator. Physical results must not depend on the choice of slice.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), and [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/). From Foundations, review [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) and [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) if the distinction between physical symmetry and descriptive redundancy feels slippery.

## Core idea

A gauge theory has more variables than physical degrees of freedom. For a gauge field, infinitesimal gauge transformations move $A_\mu^a$ along a gauge orbit:

$$
A_\mu^a(x)\mapsto A_\mu^a(x)+(D_\mu\alpha)^a(x)+O(\alpha^2).
$$

The direction $(D_\mu\alpha)^a$ is not a new physical fluctuation. It is a change of description. But the path integral over $A_\mu^a$ and the Gaussian integral that defines the free propagator initially include these directions. That causes two related problems:

1. the path integral contains an infinite gauge-volume factor;
2. the quadratic kinetic operator has zero modes and cannot be inverted.

Gauge fixing solves both problems locally. One imposes a condition

$$
G^a[A](x)=0,
$$

such as

$$
G^a[A]=\partial_\mu A^{a\mu},
$$

and then compensates for the change of variables from fields to gauge orbits by the Faddeev–Popov determinant. In perturbation theory, this is not optional bookkeeping. It is what makes the gauge-field propagator exist.

The slogan is:

```txt
gauge redundancy → singular quadratic operator → gauge fixing → propagator + ghosts.
```

For Abelian QED, the ghost determinant is field independent in ordinary covariant gauges, so ghosts decouple. For non-Abelian Yang–Mills theory, the determinant depends on $A_\mu^a$ and becomes ghost interactions. That is the subject of the next page.

## Setup and conventions

We use the QFT.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
$$

and the non-Abelian convention

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

With this convention,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c,
$$

and the Yang–Mills Lagrangian density is

$$
\mathcal L_{\rm YM}
=-\frac14 F_{\mu\nu}^aF^{a\mu\nu}.
$$

The adjoint covariant derivative acting on an adjoint-valued infinitesimal parameter or ghost is

$$
(D_\mu X)^a
=\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

All momentum-space propagators below use the Feynman $i\epsilon$ prescription. Momentum-space diagrams use the convention that momenta are incoming to a vertex unless the page says otherwise.

## Why the free gauge-field operator is singular

The issue already appears in Abelian gauge theory. Start from

$$
\mathcal L_0=-\frac14 F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

After integrating by parts, the quadratic action is

$$
S_2
=\frac12\int d^4x\,
A_\mu
\left(\eta^{\mu\nu}\partial^2-\partial^\mu\partial^\nu\right)
A_\nu.
$$

In momentum space the kinetic operator is proportional to

$$
K^{\mu\nu}(k)=
-k^2\eta^{\mu\nu}+k^\mu k^\nu.
$$

It has a null vector:

$$
K^{\mu\nu}(k)k_\nu=0.
$$

This is exactly the infinitesimal gauge direction $A_\mu(k)\sim k_\mu\alpha(k)$. Since $K^{\mu\nu}$ has a zero eigenvalue, there is no tensor $D_{\nu\rho}$ satisfying

$$
K^{\mu\nu}D_{\nu\rho}=i\delta^\mu_{\rho}
$$

on the full vector space of $A_\mu$. Saying “the photon has two physical polarizations” is true, but it does not by itself give a covariant propagator for perturbation theory. The redundant variables must be handled explicitly.

## Covariant gauge fixing

The simplest covariant gauge family uses

$$
G^a[A]=\partial_\mu A^{a\mu}.
$$

Instead of imposing $G^a[A]=0$ as a sharp delta function, perturbation theory usually averages over the gauge condition with a Gaussian weight. This gives the gauge-fixing Lagrangian

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2.
$$

The parameter $\xi$ labels the gauge choice:

| Gauge | Value of $\xi$ | Practical feature |
|---|---:|---|
| Feynman gauge | $\xi=1$ | Propagator numerator is just $\eta_{\mu\nu}$; algebra is often shortest. |
| Landau gauge | $\xi\to0$ | Propagator is transverse; useful in many loop and nonperturbative contexts. |
| General covariant gauge | arbitrary $\xi$ | Useful for checking gauge-parameter cancellation. |

Adding $\mathcal L_{\rm gf}$ changes the quadratic operator to

$$
\mathcal L_2+\mathcal L_{\rm gf}
=\frac12 A_\mu^a
\left[
\eta^{\mu\nu}\partial^2
-\left(1-\frac1\xi\right)\partial^\mu\partial^\nu
\right]
A_\nu^a.
$$

The inverse is the propagator

$$
D_{\mu\nu}^{ab}(k)
=\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

In Feynman gauge this reduces to

$$
D_{\mu\nu}^{ab}(k)
=\frac{-i\delta^{ab}\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

In Landau gauge, formally,

$$
D_{\mu\nu}^{ab}(k)
=\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left(
\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right),
$$

so the propagator is transverse:

$$
k^\mu D_{\mu\nu}^{ab}(k)=0
$$

away from the pole, in the limiting sense appropriate to the prescription.

:::note[Gauge fixing changes the description, not the theory]
The term $\mathcal L_{\rm gf}$ is not a new physical interaction. It is part of the definition of the perturbative coordinate system on the gauge-redundant field space. Gauge-invariant quantities cannot depend on $\xi$.
:::

## Faddeev–Popov determinant in one paragraph

Gauge fixing in the path integral is implemented by inserting a cleverly normalized version of one:

$$
1=\Delta_{\rm FP}[A]
\int\mathcal D\alpha\,
\delta\big(G[A^\alpha]\big).
$$

Here $A^\alpha$ is the gauge transform of $A$, and $\Delta_{\rm FP}[A]$ is the Jacobian that accounts for how the gauge condition changes along the gauge orbit. For the covariant condition $G^a[A]=\partial_\mu A^{a\mu}$,

$$
M^{ab}(x,y)
=\left.\frac{\delta G^a[A^\alpha](x)}{\delta\alpha^b(y)}\right|_{\alpha=0}
=\partial^\mu D_\mu^{ab}\,\delta^{(4)}(x-y),
$$

and

$$
\Delta_{\rm FP}[A]=\det M[A].
$$

The gauge-fixed generating functional schematically becomes

$$
Z=\int\mathcal D A\,
\Delta_{\rm FP}[A]
\exp\left\{
i\int d^4x\left(
\mathcal L_{\rm YM}
-\frac{1}{2\xi}(\partial\cdot A^a)^2
\right)
\right\}.
$$

In a non-Abelian theory, $D_\mu^{ab}$ contains $A_\mu^a$, so $\Delta_{\rm FP}[A]$ is not a harmless constant. It becomes ghost fields in perturbation theory.

## How to use the propagator in amplitudes

The covariant-gauge propagator separates into a transverse-looking part and a longitudinal gauge-dependent part:

$$
D_{\mu\nu}^{ab}(k)
=\frac{-i\delta^{ab}}{k^2+i\epsilon}\eta_{\mu\nu}
+\frac{i\delta^{ab}(1-\xi)}{k^2+i\epsilon}
\frac{k_\mu k_\nu}{k^2+i\epsilon}.
$$

In an Abelian tree amplitude where the gauge field couples to conserved currents, the longitudinal part drops out because

$$
k_\mu J^\mu=0.
$$

For example, an exchange diagram has the current factor

$$
J_1^\mu D_{\mu\nu}(k)J_2^\nu.
$$

The gauge-dependent piece is proportional to

$$
(J_1\cdot k)(k\cdot J_2),
$$

and therefore vanishes if both currents are conserved.

In non-Abelian loop calculations the cancellation is less visible diagram by diagram. Gauge boson loops, ghost loops, counterterm diagrams, and external-leg factors must be combined correctly. The final physical observable is gauge independent; individual diagrams are usually not.

## Other gauges and why covariant gauges are not the whole story

Covariant gauges are the default because they preserve manifest Lorentz covariance and make diagrammatic perturbation theory systematic. They are not the only useful choices.

**Coulomb gauge** separates transverse radiation from instantaneous Coulomb interactions. It is physically transparent in QED but less convenient for manifest covariance.

**Axial and light-cone gauges** impose conditions such as $n\cdot A=0$. They can reduce or remove ghost interactions in certain perturbative setups, but introduce spurious denominators such as $1/(n\cdot k)$ that require prescriptions.

**Background-field gauges** preserve gauge covariance with respect to a background field and are especially useful for deriving beta functions and effective actions.

**$R_\xi$ gauges** in spontaneously broken gauge theories keep renormalizability manifest while assigning gauge-dependent masses to Goldstone and ghost fields. They are indispensable in electroweak calculations, but the detailed Higgs-sector story belongs to the gauge-theory and Standard Model volumes.

The right gauge is usually the one that makes the calculation honest and short. The wrong habit is to confuse a gauge-specific simplification with a physical statement.

## Common pitfalls

**Thinking gauge fixing breaks gauge invariance physically.** Gauge fixing breaks manifest redundancy in the description. Physical gauge invariance survives as Ward identities, Slavnov–Taylor identities, or BRST symmetry.

**Treating $\xi$ as measurable.** The gauge parameter appears in propagators and off-shell Green functions. It must cancel from physical S-matrix elements and gauge-invariant observables.

**Dropping ghosts in non-Abelian loops.** Ghosts decouple in ordinary Abelian covariant gauges, but not in Yang–Mills theory. Omitting them generally violates unitarity and gauge-parameter cancellation.

**Using off-shell Green functions as observables.** Gauge-fixed correlators of $A_\mu^a$ are useful computational objects, but they are not themselves gauge-invariant observables.

**Forgetting global gauge-fixing issues.** The perturbative Faddeev–Popov construction is local in field space. Nonperturbatively, a gauge condition may intersect a gauge orbit more than once. Those Gribov-copy issues are real, but they are not needed for ordinary weak-field Feynman rules.

## Relations to other pages

- [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) turns the determinant on this page into propagators, vertices, and loop signs.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) uses gauge-boson propagators and three- and four-gauge-boson vertices at tree level.
- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains how physical external gauge bosons are represented without confusing them with internal gauge-fixed propagator components.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how loop, counterterm, and external-leg pieces combine into finite physical predictions.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) is the conceptual foundations page for why gauge transformations are redundancies rather than ordinary physical symmetries.

## Research status

The perturbative gauge-fixing construction, including covariant gauges and the Faddeev–Popov determinant, is textbook-standard and experimentally indispensable. In Abelian and non-Abelian gauge theories it gives a systematic route to propagators, loop calculations, renormalization, and precision predictions.

The active and subtle issues are not whether perturbative gauge fixing works in its domain. They concern global gauge fixing, nonperturbative gauge configuration space, Gribov copies, confinement diagnostics, gauge-invariant operator definitions, and gauge fixing in real-time, finite-density, and curved-spacetime settings.

## Exercises

### Exercise 1: The zero mode of the Maxwell kinetic operator

For the free Maxwell action, show that

$$
K^{\mu\nu}(k)=-k^2\eta^{\mu\nu}+k^\mu k^\nu
$$

satisfies $K^{\mu\nu}(k)k_\nu=0$.

<details>
<summary><strong>Solution</strong></summary>

Directly contract with $k_\nu$:

$$
K^{\mu\nu}k_\nu
=(-k^2\eta^{\mu\nu}+k^\mu k^\nu)k_\nu
=-k^2k^\mu+k^\mu k^2=0.
$$

The null vector is the momentum-space gauge transformation direction $A^\mu(k)\sim k^\mu\alpha(k)$. Therefore the ungauge-fixed kinetic operator is not invertible.

</details>

### Exercise 2: Longitudinal terms and conserved currents

Let two conserved currents exchange a gauge boson with momentum $k$. Show that the $\xi$-dependent part of

$$
J_1^\mu D_{\mu\nu}(k)J_2^\nu
$$

vanishes when $k_\mu J_1^\mu=k_\nu J_2^\nu=0$.

<details>
<summary><strong>Solution</strong></summary>

The $\xi$-dependent part of the propagator is proportional to

$$
k_\mu k_\nu.
$$

Thus the corresponding contribution to the exchange amplitude is proportional to

$$
J_1^\mu k_\mu k_\nu J_2^\nu
=(J_1\cdot k)(k\cdot J_2).
$$

Current conservation gives both factors equal to zero, so the gauge-dependent piece does not contribute. This is the simplest tree-level shadow of the more general gauge-independence story.

</details>

### Exercise 3: Abelian Faddeev–Popov determinant

For Abelian gauge theory with

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
G[A]=\partial_\mu A^\mu,
$$

show that the Faddeev–Popov operator is independent of $A_\mu$.

<details>
<summary><strong>Solution</strong></summary>

Under the infinitesimal gauge transformation,

$$
G[A^\alpha]
=\partial_\mu(A^\mu+\partial^\mu\alpha)
=\partial_\mu A^\mu+\partial^2\alpha.
$$

Therefore

$$
M(x,y)
=\frac{\delta G[A^\alpha](x)}{\delta\alpha(y)}
=\partial_x^2\delta^{(4)}(x-y).
$$

This operator does not depend on $A_\mu$. Its determinant is a field-independent constant, so in ordinary Abelian covariant gauges the ghost fields decouple from all diagrams.

</details>

## References and further reading

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 15, for non-Abelian gauge quantization, the Faddeev–Popov method, ghosts, and BRST symmetry.
- M. Srednicki, *Quantum Field Theory*, especially §§57 and 69–72, for photon path integrals, non-Abelian gauge theory, and Feynman rules.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 25–26, for Yang–Mills theory, gauge fixing, gluon propagators, and QCD applications.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 31 and 47, for the Faddeev–Popov prescription and quantization of non-Abelian gauge fields.

## Version history

- **2026-06-13:** Initial polished draft for the Gauge-Theory Perturbation Theory chapter of QFT.org.
