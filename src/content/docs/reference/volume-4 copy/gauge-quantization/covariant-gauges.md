---
title: "Covariant Gauges"
description: "Explains the covariant gauge family, the gauge parameter, Landau and Feynman gauges, and how BRST symmetry controls gauge-parameter independence."
sidebar:
  label: "Covariant Gauges"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.4–15.7; Coleman lectures on the Faddeev–Popov prescription; Schwartz Chs. 25–26; Zee Part VII.1."
topics:
  - covariant gauges
  - gauge parameter
  - Feynman gauge
  - Landau gauge
  - gluon propagator
  - BRST exactness
canonicalTopics:
  - covariant-gauge
  - gauge-parameter-independence
  - feynman-gauge
  - landau-gauge
  - gauge-boson-propagator
  - brst-exact-deformation
researchStatus:
  established:
    - "Covariant gauges form a standard perturbative family of gauge-fixed Yang–Mills descriptions whose gauge-parameter dependence cancels from BRST-invariant observables."
  active:
    - "Gauge choices become more subtle beyond perturbation theory, especially in relation to Gribov copies, confinement diagnostics, lattice gauge fixing, and gauges in theories with boundaries."
---

## Summary

Covariant gauges are the workhorse gauges of perturbative Yang–Mills theory. They keep Lorentz covariance manifest by imposing the gauge condition

$$
\partial^\mu A_\mu^a=0
$$

not as a rigid constraint on every field configuration, but through a Gaussian-weighted gauge-fixing term. The resulting gauge-fixed Lagrangian is

$$
\boxed{
\mathcal L_{\xi}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter}.
}
$$

The real parameter $\xi$ labels the gauge choice. It is not a physical coupling. The gauge-boson propagator is

$$
\boxed{
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
}
$$

Equivalently, away from the pole,

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left(P_{\mu\nu}^T+\xi P_{\mu\nu}^L\right),
$$

where

$$
P_{\mu\nu}^T=\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2},
\qquad
P_{\mu\nu}^L=\frac{k_\mu k_\nu}{k^2}.
$$

Thus $\xi$ controls only the longitudinal part of the gauge-field propagator. Feynman gauge, $\xi=1$, makes the numerator simple. Landau gauge, $\xi=0$, makes the propagator transverse. General $\xi$ is a diagnostic: if a claimed physical answer depends on $\xi$, something has gone wrong or the quantity was never physical.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Covariant gauges form a one-parameter BRST-exact family; the gauge parameter changes longitudinal propagation but not physical observables.](/figures/gauge-theories-standard-model/covariant-gauge-family.svg)

<figcaption>

Covariant gauges are a one-parameter family. The gauge parameter $\xi$ changes the longitudinal projector in the gauge-boson propagator and leaves the ghost sector fixed in the simplest Lorenz-type gauge. BRST symmetry says that changing $\xi$ changes the action by a BRST-exact term, so BRST-invariant observables are independent of $\xi$ when the symmetry is anomaly-free.

</figcaption>
</figure>

## Prerequisites

You should have read [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/), [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/), and [Physical States and Unitarity](/gauge-theories-standard-model/gauge-quantization/physical-states-and-unitarity/). We will use the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
(D_\mu c)^a=\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

The Abelian version appears in [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/). The Yang–Mills version differs in one crucial way: ghosts interact because the Faddeev–Popov operator $\partial\cdot D[A]$ depends on $A_\mu^a$.

## Core idea

A covariant gauge is not one gauge. It is a family of equivalent gauge-fixed descriptions.

The gauge condition $\partial\cdot A^a=0$ is the Lorenz condition. In the path integral, however, it is often better to average over nearby slices rather than impose a sharp delta-functional constraint. The parameter $\xi$ controls the width of that averaging.

Schematic examples:

| Gauge | Parameter | Propagator feature | Typical use |
|---|---:|---|---|
| Feynman gauge | $\xi=1$ | $D_{\mu\nu}\propto\eta_{\mu\nu}$ | Simplest tensor algebra. |
| Landau gauge | $\xi=0$ | $k^\mu D_{\mu\nu}=0$ | Transverse propagator; useful in identities and nonperturbative studies. |
| General covariant gauge | arbitrary $\xi$ | separates transverse and longitudinal parts | Gauge-parameter checks. |

All members of the family describe the same physical gauge theory when used consistently. Different $\xi$ values are different coordinate choices on the same quotient by gauge redundancy.

## Setup and conventions

Start from the Yang–Mills action

$$
\mathcal L_{\rm YM}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

The infinitesimal gauge transformation is

$$
\delta_\alpha A_\mu^a=(D_\mu\alpha)^a
=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

For the Lorenz-type gauge condition

$$
G^a(A)=\partial^\mu A_\mu^a,
$$

the Faddeev–Popov operator is

$$
M^{ab}[A]
=\frac{\delta G^a(A^\alpha)}{\delta\alpha^b}\bigg|_{\alpha=0}
=\partial^\mu D_\mu^{ab}[A].
$$

The ghost term is therefore

$$
\mathcal L_{\rm gh}
=-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

The gauge-fixing term is

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2.
$$

The complete covariant-gauge action is

$$
S_\xi
=\int d^4x\,
\left[
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter}
\right].
$$

This is the default covariant gauge family for perturbative pages in this volume unless stated otherwise.

## How the gauge parameter appears

One way to derive the $\xi$ term is to insert a Gaussian average over gauge conditions. Instead of forcing

$$
\partial^\mu A_\mu^a=0,
$$

one introduces an auxiliary function $f^a(x)$ and averages with weight

$$
\exp\left[-\frac{i}{2\xi}\int d^4x\,f^a f^a\right].
$$

After the Faddeev–Popov insertion and the change of variables along gauge orbits, the integral over $f^a$ produces

$$
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2.
$$

Small $\xi$ makes the weighting sharply enforce $\partial\cdot A^a\approx0$. The limit $\xi\to0$ gives Landau gauge. Large $\xi$ weakens the penalty on $\partial\cdot A^a$. The value $\xi=1$ gives Feynman gauge.

The parameter is not measured in an experiment. It labels how redundant variables are handled inside a calculation.

## Auxiliary-field form

BRST symmetry is clearest before eliminating the auxiliary Nakanishi–Lautrup field $B^a$. Write

$$
\mathcal L_{\rm gf+gh}
=
s\left[\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)\right],
$$

where

$$
sA_\mu^a=(D_\mu c)^a,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

Expanding gives

$$
\mathcal L_{\rm gf+gh}
=
B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

The $B^a$ equation of motion is

$$
B^a=-\frac{1}{\xi}\partial^\mu A_\mu^a.
$$

Substituting back gives

$$
B^a\partial^\mu A_\mu^a+\frac{\xi}{2}B^aB^a
\longrightarrow
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2.
$$

The auxiliary-field form is more than cosmetic. It makes the dependence on $\xi$ visibly BRST exact:

$$
\frac{\partial\mathcal L_{\rm gf+gh}}{\partial\xi}
=
s\left(\frac12\bar c^aB^a\right).
$$

Therefore, for a BRST-closed observable $\mathcal O$,

$$
\frac{\partial}{\partial\xi}\langle\mathcal O\rangle_\xi
\propto
\left\langle\mathcal O\,s\left(\int d^4x\,\frac12\bar c^aB^a\right)\right\rangle_\xi
=0,
$$

provided the measure is BRST invariant and there are no boundary or anomaly terms. This is the clean conceptual reason physical observables do not depend on $\xi$.

## The quadratic operator

The free gauge-field part of the covariant-gauge Lagrangian is obtained by keeping only the quadratic terms in $A_\mu^a$:

$$
\mathcal L_{A,2}
=
-\frac14(\partial_\mu A_\nu^a-\partial_\nu A_\mu^a)
(\partial^\mu A^{a\nu}-\partial^\nu A^{a\mu})
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2.
$$

After integrating by parts,

$$
\mathcal L_{A,2}
=
\frac12A_\mu^a
\left[
\eta^{\mu\nu}\Box
-\left(1-\frac1\xi\right)\partial^\mu\partial^\nu
\right]
A_\nu^a.
$$

In momentum space, with the Fourier convention $e^{-ik\cdot x}$, the quadratic operator is

$$
K_\xi^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}
+\left(1-\frac1\xi\right)k^\mu k^\nu.
$$

The propagator is $i$ times the inverse of this operator with the Feynman pole prescription.

## Projector inversion

For $k^2\neq0$, define

$$
P_{\mu\nu}^T=\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2},
\qquad
P_{\mu\nu}^L=\frac{k_\mu k_\nu}{k^2}.
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

The quadratic operator is diagonal in this basis:

$$
K_\xi(k)
=
-k^2P^T-\frac{k^2}{\xi}P^L.
$$

Thus

$$
K_\xi^{-1}(k)
=
-\frac{1}{k^2}P^T-\frac{\xi}{k^2}P^L.
$$

Multiplying by $i$ and adding the pole prescription gives

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left(P_{\mu\nu}^T+\xi P_{\mu\nu}^L\right),
$$

or, in expanded form,

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

The second expression is the one most commonly used in Feynman rules. The first expression is the one that makes the meaning of $\xi$ transparent.

## Feynman gauge

Feynman gauge is

$$
\xi=1.
$$

The propagator becomes

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

This is often the simplest gauge for explicit perturbative calculations. Lorentz indices contract directly through $\eta_{\mu\nu}$, and the price is that unphysical polarizations are maximally visible internally. Ghost loops and Ward or Slavnov–Taylor identities are essential for cancellations.

Feynman gauge is a computational convenience, not a claim that a gauge boson has four physical polarizations.

## Landau gauge

Landau gauge is the limit

$$
\xi\to0.
$$

The propagator becomes transverse:

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left(\eta_{\mu\nu}-\frac{k_\mu k_\nu}{k^2+i\epsilon}\right),
$$

and, away from the pole,

$$
k^\mu D_{\mu\nu}^{ab}(k)=0.
$$

Landau gauge is useful when transversality simplifies the structure of Green functions. It is also common in nonperturbative studies of gauge-field propagators. The price is that the $\xi\to0$ limit should be handled carefully: the longitudinal part is suppressed by a limiting procedure, and global gauge-fixing issues are not solved by writing $\xi=0$.

## Ghosts in the covariant gauge family

In the simple Lorenz-type covariant family, the ghost Lagrangian is

$$
\mathcal L_{\rm gh}
=-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

Its free part is

$$
\mathcal L_{{\rm gh},2}
=(\partial^\mu\bar c^a)(\partial_\mu c^a),
$$

so the ghost propagator is

$$
\Delta_{\rm gh}^{ab}(k)
=
\frac{i\delta^{ab}}{k^2+i\epsilon}.
$$

The ghost–gauge-boson interaction is

$$
\mathcal L_{{\rm gh},A}
=-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

Notice that $\xi$ does not appear explicitly in this ghost Lagrangian. The gauge parameter changes the gauge-boson propagator. Ghost interactions are fixed by the Faddeev–Popov operator for the chosen gauge condition. In more general gauges, both statements can look different, but in this chapter this is the standard setup.

## Conserved currents and the longitudinal part

In QED, the longitudinal part of the photon propagator drops out immediately when the photon is exchanged between conserved currents:

$$
k_\mu J^\mu(k)=0.
$$

Then

$$
J^\mu(k)D_{\mu\nu}^{(\xi)}(k)J'^\nu(-k)
=
\frac{-i}{k^2+i\epsilon}J^\mu J'_\mu,
$$

because the $k_\mu k_\nu$ term vanishes.

In non-Abelian gauge theory, the analogous cancellations are more elaborate. Gauge bosons carry charge, self-interact, and ghosts participate in the Slavnov–Taylor identities. The simple conserved-current argument is replaced by BRST identities. But the moral is the same:

$$
\text{longitudinal gauge dependence is not physical.}
$$

## Gauge-parameter checks

A general $\xi$ calculation is often longer than a Feynman-gauge calculation, but it gives a powerful check. If an observable is physical, the final answer should be independent of $\xi$.

Examples of objects that may depend on $\xi$:

- the gauge-boson propagator;
- off-shell Green functions of $A_\mu^a$;
- self-energies away from a physical pole definition;
- intermediate loop integrals;
- effective potentials away from gauge-invariant interpretations.

Examples of objects that should not depend on $\xi$ when properly defined:

- S-matrix elements between physical states;
- inclusive physical rates after infrared issues are handled;
- gauge-invariant Wilson-loop expectation values;
- pole masses of physical particles;
- beta-function coefficients for the gauge coupling in standard mass-independent schemes at universal orders.

The phrase “properly defined” is doing some work. Gauge-dependent intermediate quantities can sometimes be combined into gauge-invariant observables only after including all diagrams, counterterms, real-emission contributions, or operator definitions required by the question.

## Relation to other gauges

Covariant gauges are not the only useful gauges.

Coulomb gauge sacrifices manifest Lorentz covariance but keeps only physical transverse photons especially visible in electrodynamics. Axial and light-cone gauges can remove ghosts in some perturbative contexts but introduce spurious denominators requiring prescriptions. Background-field gauges keep covariance with respect to a background gauge transformation and are especially useful for renormalization.

The point of this page is narrower: the covariant $\xi$ family is the default local perturbative gauge family for Yang–Mills theory. It is the family in which the BRST, ghost, and propagator story takes its simplest textbook form.

## Common pitfalls

**Pitfall 1: Treating $\xi$ as a physical parameter.**

Changing $\xi$ changes the gauge-fixed representation, not the theory. Physical observables must not depend on it.

**Pitfall 2: Setting $\xi=1$ and forgetting ghosts.**

Feynman gauge simplifies the gauge-boson propagator. It does not remove the Faddeev–Popov determinant. Non-Abelian ghosts still interact.

**Pitfall 3: Thinking Landau gauge leaves only physical particles.**

Landau gauge makes the propagator transverse, but it is still a gauge-fixed covariant formalism with ghosts and residual subtleties. Transverse propagator does not mean “the physical Hilbert space has been constructed.”

**Pitfall 4: Checking gauge independence diagram by diagram.**

Gauge-parameter cancellation usually requires complete gauge-invariant sets of diagrams and counterterms. One diagram can depend on $\xi$ without causing trouble.

**Pitfall 5: Confusing Lorenz and Lorentz.**

The condition is named after Ludvig Lorenz and is written $\partial_\mu A^\mu=0$. It is Lorentz covariant, but the gauge condition is Lorenz gauge.

## Relations to other pages

This page extends the QED [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) page to Yang–Mills theory. The tensor structure of the propagator is the same for each adjoint color index, but the ghost sector is interacting.

It follows [Physical States and Unitarity](/gauge-theories-standard-model/gauge-quantization/physical-states-and-unitarity/): the reason $\xi$ is harmless is that BRST symmetry makes changes in $\xi$ cohomologically trivial.

The next natural page is [Background-Field Gauge](/gauge-theories-standard-model/gauge-quantization/background-field-gauge/), where gauge fixing is arranged to preserve a background gauge covariance. That method is especially useful for deriving the structure of gauge coupling renormalization.

## Research status

Perturbative covariant gauges are completely standard. They are the default language for many QED, QCD, electroweak, and general Yang–Mills calculations.

Beyond perturbation theory, gauge fixing is more delicate. Landau gauge is widely studied on the lattice, but Gribov copies and global gauge-fixing ambiguities matter. Gauge choices in the presence of boundaries, horizons, asymptotic charges, or topologically nontrivial bundles can carry physical subtleties. These refinements do not invalidate the perturbative $\xi$-gauge formalism; they tell us where its local field-space picture stops being the whole story.

## Exercises

### Exercise 1: Invert the covariant-gauge quadratic operator

Starting from

$$
K_\xi^{\mu\nu}(k)
=
-k^2\eta^{\mu\nu}
+\left(1-\frac1\xi\right)k^\mu k^\nu,
$$

show that

$$
D_{\mu\nu}^{(\xi)}(k)
=
\frac{-i}{k^2+i\epsilon}
\left(P^T_{\mu\nu}+\xi P^L_{\mu\nu}\right).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\eta=P^T+P^L,
\qquad
k_\mu k_\nu=k^2P^L_{\mu\nu}.
$$

Then

$$
K_\xi
=-k^2(P^T+P^L)+\left(1-\frac1\xi\right)k^2P^L
=-k^2P^T-\frac{k^2}{\xi}P^L.
$$

Since $P^T$ and $P^L$ are orthogonal projectors,

$$
K_\xi^{-1}
=-\frac{1}{k^2}P^T-\frac{\xi}{k^2}P^L.
$$

The Feynman propagator is $iK_\xi^{-1}$ with $k^2\to k^2+i\epsilon$, giving

$$
D^{(\xi)}
=\frac{-i}{k^2+i\epsilon}(P^T+\xi P^L).
$$

</details>

### Exercise 2: Longitudinal exchange between conserved currents

Let $k_\mu J^\mu=k_\nu J'^\nu=0$. Show that the $\xi$-dependent part of the covariant-gauge propagator does not contribute to $J^\mu D_{\mu\nu}^{(\xi)}J'^\nu$.

<details><summary><strong>Solution</strong></summary>

The $\xi$-dependent term is proportional to

$$
J^\mu k_\mu k_\nu J'^\nu.
$$

Since both currents are conserved in momentum space,

$$
J^\mu k_\mu=0,
\qquad
k_\nu J'^\nu=0.
$$

Thus the longitudinal contribution vanishes. The exchange amplitude depends only on the transverse part of the propagator.

</details>

### Exercise 3: Gauge-parameter dependence is BRST exact

Using

$$
\mathcal L_{\rm gf+gh}
=s\left[\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right)\right],
$$

show that $\partial\mathcal L_{\rm gf+gh}/\partial\xi$ is BRST exact.

<details><summary><strong>Solution</strong></summary>

Differentiate with respect to $\xi$:

$$
\frac{\partial\mathcal L_{\rm gf+gh}}{\partial\xi}
=
s\left(\frac12\bar c^aB^a\right).
$$

Because $s\bar c^a=B^a$ and $sB^a=0$, this equals

$$
\frac12B^aB^a.
$$

The important structural result is the first equation: changing $\xi$ changes the action by a BRST-exact deformation. Insertions of BRST-exact deformations vanish in expectation values of BRST-closed observables when the measure is BRST invariant.

</details>

### Exercise 4: Abelian versus non-Abelian ghosts

Explain why ghosts decouple in QED Lorenz gauge but not in Yang–Mills covariant gauge.

<details><summary><strong>Solution</strong></summary>

In QED, the gauge transformation is

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

so

$$
\frac{\delta(\partial^\mu A_\mu^\alpha)}{\delta\alpha}=\Box.
$$

The Faddeev–Popov operator is field-independent. Its determinant is an overall normalization in ordinary photon and matter correlators.

In Yang–Mills theory,

$$
\delta A_\mu^a=(D_\mu\alpha)^a,
$$

so

$$
M^{ab}[A]=\partial^\mu D_\mu^{ab}[A].
$$

This depends on $A_\mu^a$. The determinant therefore produces an interacting ghost action with a ghost–gauge-boson vertex.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§71–74, for covariant gauge fixing, ghost fields, Feynman rules, and BRST symmetry.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.4–15.7, for canonical constraints, covariant gauges, ghosts, and BRST invariance.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Chs. 30–31, for the Faddeev–Popov prescription and covariant QED/Yang–Mills quantization.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Yang–Mills propagators, ghost loops, and practical gauge-theory perturbation theory.
- Zee, *Quantum Field Theory in a Nutshell*, Part VII.1, for an intuitive path into quantizing Yang–Mills theory.

## Version history

- **2026-06-18:** Initial polished draft.
