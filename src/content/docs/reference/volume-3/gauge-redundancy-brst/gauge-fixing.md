---
title: "Gauge Fixing"
description: "Explains gauge fixing as a local coordinate choice on gauge-orbit space, derives the Faddeev–Popov insertion, and compares common gauges and their caveats."
sidebar:
  label: "Gauge Fixing"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.4–15.7; Coleman, Lectures Ch. 31; Coleman, ‘Secret Symmetry’; standard BRST and constrained-system treatments."
topics:
  - gauge fixing
  - Faddeev–Popov determinant
  - gauge orbits
  - Lorenz gauge
  - R-xi gauges
  - Gribov copies
canonicalTopics:
  - gauge-fixing
  - faddeev-popov-determinant
  - gauge-orbit
  - covariant-gauge
  - gribov-copy
researchStatus:
  established:
    - "Perturbative gauge fixing is a local choice of representative on each gauge orbit, together with the Jacobian needed to avoid overcounting equivalent field configurations."
    - "Gauge-invariant observables are independent of the gauge-fixing choice when the gauge symmetry is non-anomalous and the path integral is defined consistently."
  active:
    - "Global gauge fixing, Gribov regions, boundary gauge fixing, and gauge choices in nonperturbative or real-time settings remain subtle and context-dependent."
---

## Summary

Gauge fixing is not an extra physical assumption. It is a way of doing calculations in a theory whose field variables contain redundancy. The raw path integral over gauge fields integrates not only over physical configurations but also over all points on every gauge orbit. Gauge fixing chooses, at least locally, one representative on each orbit.

The geometric picture is:

$$
\int_{\mathcal F} \mathcal D A
\quad\text{overcounts by}\quad
\operatorname{Vol}(\mathcal G),
$$

so a gauge-fixed path integral replaces the redundant integral by something like

$$
\frac{1}{\operatorname{Vol}(\mathcal G)}\int_{\mathcal F}\mathcal D A\,e^{iS[A]}
=\int_{\mathcal F}\mathcal D A\,\Delta_{\mathcal F}[A]\,\delta[\mathcal F[A]]\,e^{iS[A]},
$$

where $\mathcal F[A]=0$ is the gauge condition and $\Delta_{\mathcal F}[A]$ is the Faddeev–Popov determinant. In covariant gauges this determinant becomes the ghost action on the next page.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Gauge fixing as a local slice through gauge orbits, with a perturbative patch and a global Gribov-copy warning.](/figures/symmetry-anomalies-topology/gauge-fixing-local-slice.svg)

<figcaption>

Gauge fixing is a local slice through gauge orbits in field space. In a perturbative patch the slice intersects each nearby orbit once. Globally the same condition can intersect an orbit more than once, producing Gribov copies.

</figcaption>
</figure>

The most important lesson is conceptual: a gauge condition is a coordinate choice, not a new law of nature. Good gauge choices make propagators and perturbation theory well-defined. Bad or incomplete gauge choices leave residual redundancies. Nonperturbatively, no single simple gauge condition need describe the whole quotient $\mathcal F/\mathcal G$.

## Prerequisites

Read [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/) and [Local versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/) first. You should also know the background-field distinction from [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and the source-functional logic of [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/).

For calculations, you should be comfortable with Gaussian path integrals, Lie-algebra-valued gauge fields, and the idea that a path-integral measure can acquire a Jacobian under a change of variables.

## Core idea

A gauge theory uses redundant coordinates. In electrodynamics,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

leaves $F_{\mu\nu}$ unchanged. In non-Abelian gauge theory, the gauge field moves along a non-linear orbit. A gauge condition tries to cut through those orbits.

A typical gauge condition is a functional

$$
\mathcal F^a[A](x)=0.
$$

For example, Lorenz gauge is

$$
\mathcal F^a[A]=\partial^\mu A_\mu^a.
$$

The condition is useful only if it actually fixes the redundancy. Infinitesimally, this means that motion along a gauge orbit changes $\mathcal F$ in an invertible way. The linearized operator

$$
M^{ab}(x,y;A)
=\left.\frac{\delta\mathcal F^a[A^\alpha](x)}{\delta\alpha^b(y)}\right|_{\alpha=0}
$$

is the Faddeev–Popov operator. If $M$ has zero modes, the gauge condition has not fixed all local redundancy. If the gauge slice intersects the same orbit more than once, the condition has Gribov copies.

The whole perturbative construction is therefore a local coordinate chart on the physical quotient. This is enough for ordinary weak-coupling Feynman rules, but it is not a magic global solution to the geometry of gauge field space.

## Setup and conventions

Write the non-Abelian gauge field as

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators. In this chapter we use

$$
D_\mu=\partial_\mu+igA_\mu
$$

on matter fields transforming as $\psi\mapsto U^{-1}\psi$. Then

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

For an infinitesimal transformation $U=1+ig\alpha+O(\alpha^2)$,

$$
\delta_\alpha A_\mu
=\partial_\mu\alpha+ig[A_\mu,\alpha]
\equiv \mathcal D_\mu\alpha.
$$

In components,

$$
(\mathcal D_\mu\alpha)^a
=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

:::note[Convention-sensitive source note]
Some books use $D_\mu=\partial_\mu-igA_\mu$ and matter transformation $\psi\mapsto U\psi$. That changes signs in $A_\mu^U$, $\delta A_\mu$, the ghost interaction, and the ghost-gluon vertex. The invariant object is the gauge-orbit Jacobian, not the placement of a minus sign in a particular convention.
:::

For Lorenz gauge,

$$
\mathcal F^a[A]=\partial^\mu A_\mu^a,
$$

the Faddeev–Popov operator is

$$
M^{ab}[A]
=\partial^\mu \mathcal D_\mu^{ab}.
$$

At $A=0$, this reduces to

$$
M^{ab}[0]=\delta^{ab}\Box.
$$

Thus even the free gauge field has residual gauge transformations satisfying $\Box\alpha=0$ unless boundary conditions remove them.

## Why the naive gauge-field path integral fails

The classical Yang–Mills action

$$
S_{\rm YM}=-\frac12\int d^4x\,\operatorname{tr}F_{\mu\nu}F^{\mu\nu}
$$

is constant along gauge orbits:

$$
S[A^U]=S[A].
$$

So the formal integral

$$
Z_{\rm naive}=\int\mathcal D A\,e^{iS_{\rm YM}[A]}
$$

contains an infinite factor from integrating over all gauge-equivalent copies. This is not merely an aesthetic problem. The quadratic kinetic operator for $A_\mu$ is not invertible before gauge fixing.

For Abelian Maxwell theory,

$$
\mathcal L_0=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

After integrating by parts,

$$
\mathcal L_0
=\frac12 A_\mu\left(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu\right)A_\nu.
$$

The operator

$$
K^{\mu\nu}=\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu
$$

annihilates pure-gauge modes $A_\nu=\partial_\nu\alpha$:

$$
K^{\mu\nu}\partial_\nu\alpha=0.
$$

No inverse exists on the full vector-field space. Since a propagator is the inverse of the quadratic kinetic operator, the free gauge-field propagator is undefined until we remove or control the longitudinal redundancy.

## The Faddeev–Popov insertion

Choose a gauge functional $\mathcal F[A]$. Locally along a gauge orbit, insert the identity

$$
1
=\Delta_{\mathcal F}[A]\int\mathcal D\alpha\,
\delta[\mathcal F[A^\alpha]],
$$

where

$$
\Delta_{\mathcal F}[A]
=\det M[A]
$$

and

$$
M^{ab}(x,y;A)
=\left.\frac{\delta\mathcal F^a[A^\alpha](x)}{\delta\alpha^b(y)}\right|_{\alpha=0}.
$$

If the measure and action are gauge invariant, the integral over $\alpha$ factors out as $\operatorname{Vol}(\mathcal G)$, leaving

$$
Z
=\int\mathcal D A\,
\Delta_{\mathcal F}[A]\,
\delta[\mathcal F[A]]\,e^{iS[A]}.
$$

This expression is the sharp version of “divide by the gauge group.” The determinant is not optional; it is the Jacobian for replacing the redundant coordinates by coordinates along the gauge slice and coordinates along the gauge orbit.

For Lorenz gauge in Yang–Mills theory,

$$
\Delta_{\rm L}[A]=\det(\partial^\mu\mathcal D_\mu).
$$

In Abelian theory with a linear gauge condition,

$$
\Delta_{\rm L}[A]=\det\Box,
$$

which is independent of $A$. It contributes only an overall normalization, so the Abelian ghosts associated with this determinant decouple. In non-Abelian theory, $\mathcal D_\mu$ contains $A_\mu$, so the determinant is field-dependent and becomes dynamical ghost interactions.

## From delta gauge to Rξ gauges

The delta-functional gauge condition $\delta[\partial^\mu A_\mu]$ is often too sharp for perturbation theory. One instead imposes

$$
\partial^\mu A_\mu^a=f^a
$$

and averages over $f^a$ with a Gaussian weight. In Lorentzian conventions this produces the gauge-fixing term

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}\left(\partial^\mu A_\mu^a\right)^2.
$$

The parameter $\xi$ labels a family of gauges, not a family of physical theories. Common choices are:

| Gauge | Parameter choice | Useful feature |
|---|---:|---|
| Feynman gauge | $\xi=1$ | Simplest covariant propagator numerator |
| Landau gauge | $\xi\to0$ | Enforces $\partial^\mu A_\mu=0$ sharply |
| General covariant gauge | arbitrary $\xi$ | Checks gauge-parameter independence |
| Background-field gauge | $\bar D^\mu a_\mu=0$ | Preserves background gauge covariance |

For Abelian theory, adding $\mathcal L_{\rm gf}$ gives the momentum-space propagator

$$
D_{\mu\nu}(p)
=\frac{-i}{p^2+i\epsilon}
\left(\eta_{\mu\nu}-(1-\xi)\frac{p_\mu p_\nu}{p^2+i\epsilon}\right),
$$

in the mostly-minus convention used in this volume.

:::note[Propagator sign note]
Gauge-field propagator signs are among the most convention-sensitive formulas in QFT. The expression above is tied to $\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}-\frac{1}{2\xi}(\partial\cdot A)^2$ with mostly-minus metric and $e^{iS}$ in Lorentzian signature. Different metric or Fourier conventions move signs between the quadratic operator and propagator.
:::

Physical gauge-invariant observables do not depend on $\xi$ when the theory is consistently gauge-fixed and free of gauge anomalies. In perturbation theory this gauge-parameter independence is usually proven through BRST symmetry and Slavnov–Taylor identities, not by checking diagram after diagram by hand.

## Common gauges and what they buy you

No gauge is universally best. Gauge choice is like choosing coordinates: the best one depends on the calculation.

### Lorenz and covariant gauges

Lorenz gauge is

$$
\partial^\mu A_\mu=0.
$$

It is called Lorenz gauge after Ludvig Lorenz, not Lorentz gauge, though it is Lorentz covariant. Covariant gauges are well matched to relativistic perturbation theory because propagators and vertices keep spacetime covariance manifest.

Their price is that unphysical polarizations appear in intermediate steps. The cancellation of these modes is enforced by gauge invariance or, quantum mechanically, BRST symmetry.

### Coulomb gauge

Coulomb gauge is

$$
\nabla\cdot\mathbf A=0.
$$

It makes the physical transverse photon polarizations more visible and is useful in canonical quantization, nonrelativistic bound states, and some Hamiltonian approaches. Its price is loss of manifest Lorentz covariance and a more complicated instantaneous Coulomb interaction.

### Axial and light-cone gauges

Axial gauges impose

$$
n^\mu A_\mu=0
$$

for a fixed vector $n^\mu$. Light-cone gauge is the special case $n^2=0$. These gauges can remove Faddeev–Popov ghosts in many perturbative applications, but they introduce singular denominators such as $1/(n\cdot p)$ and require a prescription. They are powerful but not free lunch. QFT, naturally, charges interest.

### Background-field gauge

Split the gauge field into a background and fluctuation,

$$
A_\mu=\bar A_\mu+a_\mu,
$$

and fix the quantum gauge redundancy using

$$
\bar D^\mu a_\mu=0.
$$

The resulting effective action remains invariant under background gauge transformations. This makes renormalization of gauge couplings and effective actions especially clean.

### Unitary gauge

In a Higgs phase, unitary gauge removes Goldstone fields from the spectrum of perturbative variables. It displays the massive vector particles directly, but often obscures renormalizability and high-energy behavior. It is a useful physical gauge for some tree-level reasoning, not the cleanest gauge for loop proofs.

## Residual gauge transformations

A gauge condition may leave transformations that preserve it. In Abelian Lorenz gauge,

$$
\partial^\mu A_\mu=0
$$

is preserved by

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

if

$$
\Box\alpha=0.
$$

These are residual gauge transformations. Whether they are redundancies, boundary symmetries, or excluded transformations depends on boundary conditions.

This is why gauge fixing is never just the equation $\mathcal F[A]=0$. A complete gauge choice also includes boundary conditions, zero-mode treatment, topological-sector rules, and sometimes operator insertions.

## Gribov copies and the limits of one gauge slice

The Faddeev–Popov construction assumes that the gauge condition intersects each relevant gauge orbit once. Perturbatively near $A_\mu=0$, this is often true after boundary conditions are imposed. Globally it can fail.

A **Gribov copy** is a distinct gauge-equivalent field configuration that satisfies the same gauge condition:

$$
A\neq A^g,
\qquad
\mathcal F[A]=0,
\qquad
\mathcal F[A^g]=0.
$$

Equivalently, the gauge slice intersects the same orbit more than once. At a boundary of a local gauge patch, the Faddeev–Popov operator develops zero modes:

$$
M[A]\alpha=0.
$$

The existence of Gribov copies does not invalidate perturbative QCD calculations. It says that a simple local gauge condition is not a global coordinate system on non-Abelian field space. Nonperturbative gauge fixing, confinement diagnostics, lattice gauge theory, and BRST beyond perturbation theory must reckon with this fact.

## Gauge fixing with boundaries

On a manifold with boundary, or in an asymptotically noncompact spacetime, the gauge-fixing problem changes. A transformation that would be pure redundancy in the bulk can act nontrivially on boundary data. The generator of a gauge transformation may acquire a boundary term, and that boundary term is a physical charge.

Consequently, one must not casually gauge-fix away boundary modes. In electrodynamics, asymptotic gauge transformations are tied to electric charge and soft photon physics. In Chern–Simons theory, boundary gauge degrees of freedom become edge modes. In gravity, the analogous issue is even sharper, because diffeomorphisms with boundary action are related to asymptotic symmetries.

The operational rule is:

$$
\text{fix redundancy, but do not erase physical boundary data.}
$$

## How gauge independence is actually checked

Gauge-invariant quantities should not depend on the gauge condition. But intermediate objects often do. Propagators, off-shell Green functions, gauge-field components, and individual diagrams are generally gauge dependent.

For example, the gauge-boson propagator depends on $\xi$. A scattering amplitude between physical states does not. In a non-Abelian theory, the cancellation of $\xi$ dependence may involve gauge bosons, ghosts, external-state restrictions, counterterms, and Slavnov–Taylor identities.

BRST symmetry packages the gauge-fixed theory so that physical observables are BRST cohomology classes. Changing the gauge-fixing fermion changes the representative of the path integral, not the expectation values of BRST-closed observables, provided the measure is BRST invariant and there are no boundary or anomaly obstructions.

This is the bridge to the next pages: ghosts are not optional decorations, and BRST is not philosophical perfume. They are the machinery that makes covariant gauge fixing compatible with unitarity and locality.

## Common pitfalls

**Pitfall: treating the gauge condition as physics.** The equation $\partial^\mu A_\mu=0$ is not a physical equation of motion. It is a coordinate condition on redundant variables.

**Pitfall: saying gauge fixing breaks gauge symmetry as if it were an ordinary global symmetry.** Gauge fixing breaks manifest gauge redundancy in the description. It does not turn a redundancy into a physical symmetry that can be spontaneously broken.

**Pitfall: forgetting the determinant.** A gauge slice changes the integration measure. Dropping $\Delta_{\mathcal F}[A]$ gives wrong non-Abelian perturbation theory.

**Pitfall: confusing Lorenz and Lorentz.** Lorenz gauge is named after Ludvig Lorenz. It is Lorentz covariant, but the name is Lorenz.

**Pitfall: assuming one gauge fixes everything globally.** Perturbative gauge fixing is local in field space. Gribov copies and topological sectors are real.

**Pitfall: using gauge-dependent quantities as observables.** A gauge-field component, a propagator, or an off-shell effective potential can be useful without being directly observable.

## Relations to other pages

This page depends on [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/) and [Local versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/). The next page, [Faddeev–Popov Ghosts](/symmetry-anomalies-topology/gauge-redundancy-brst/faddeev-popov-ghosts/), exponentiates $\Delta_{\mathcal F}[A]$ and explains why anticommuting scalar fields appear in gauge-fixed non-Abelian perturbation theory.

Later, [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/) will show how gauge-fixed actions retain a fermionic remnant of gauge invariance. [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) will explain physical operators and states. [Gribov Ambiguities Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/gribov-ambiguities-preview/) returns to global gauge-fixing failure.

This page also connects to [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), and the later gauge-theory volume, where gauge fixing becomes a computational tool for QED, Yang–Mills theory, QCD, and the Standard Model.

## Research status

Perturbative Faddeev–Popov gauge fixing and covariant gauges are established technology. They are part of the standard definition of perturbative non-Abelian gauge theory and are supported by BRST symmetry, Slavnov–Taylor identities, and extensive phenomenological success.

The global geometry of gauge fixing is subtler. Gribov copies show that a simple gauge condition is not a global slice through non-Abelian gauge orbit space. Boundary gauge transformations and edge modes remain an active interface among gauge theory, topological phases, soft theorems, and quantum gravity.

## Exercises

### Exercise 1. Zero modes of the Maxwell kinetic operator

Show that the quadratic Maxwell operator

$$
K^{\mu\nu}=\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu
$$

annihilates $\partial_\nu\alpha$ for any sufficiently smooth $\alpha$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
K^{\mu\nu}\partial_\nu\alpha
=\eta^{\mu\nu}\Box\partial_\nu\alpha-\partial^\mu\partial^\nu\partial_\nu\alpha.
$$

Since partial derivatives commute,

$$
\eta^{\mu\nu}\Box\partial_\nu\alpha
=\Box\partial^\mu\alpha
=\partial^\mu\Box\alpha,
$$

and

$$
\partial^\mu\partial^\nu\partial_\nu\alpha
=\partial^\mu\Box\alpha.
$$

The two terms cancel, so

$$
K^{\mu\nu}\partial_\nu\alpha=0.
$$

This is the quadratic-level expression of gauge redundancy.

</details>

### Exercise 2. Faddeev–Popov operator in Abelian Lorenz gauge

For $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ and $\mathcal F[A]=\partial^\mu A_\mu$, compute $M=\delta\mathcal F[A^\alpha]/\delta\alpha$.

<details><summary><strong>Solution</strong></summary>

We have

$$
\mathcal F[A^\alpha]
=\partial^\mu(A_\mu+\partial_\mu\alpha)
=\partial^\mu A_\mu+\Box\alpha.
$$

Therefore

$$
M(x,y)=\Box_x\delta^{(4)}(x-y).
$$

The determinant $\det\Box$ is independent of $A_\mu$. In ordinary Abelian covariant gauges it can be absorbed into the normalization of the path integral.

</details>

### Exercise 3. Residual transformations in Lorenz gauge

Assume $\partial^\mu A_\mu=0$. Find the condition on $\alpha$ such that $A_\mu+\partial_\mu\alpha$ also satisfies Lorenz gauge.

<details><summary><strong>Solution</strong></summary>

The transformed field obeys

$$
\partial^\mu(A_\mu+\partial_\mu\alpha)
=\partial^\mu A_\mu+\Box\alpha.
$$

If $\partial^\mu A_\mu=0$, the transformed field is still in Lorenz gauge exactly when

$$
\Box\alpha=0.
$$

Boundary conditions decide whether such transformations are allowed residual redundancies, excluded, or physical boundary transformations.

</details>

### Exercise 4. Why Landau gauge is a sharp limit

Start from the Gaussian gauge-fixing weight

$$
\exp\left[-\frac{i}{2\xi}\int d^4x\,f^a f^a\right]
$$

for the auxiliary function $f^a=\partial^\mu A_\mu^a$. Explain why $\xi\to0$ imposes $\partial^\mu A_\mu^a=0$ sharply.

<details><summary><strong>Solution</strong></summary>

The smaller $\xi$ is, the more rapidly the phase oscillates for configurations with nonzero $f^a$. With the usual $i\epsilon$ or Euclidean continuation that makes the Gaussian damped, the weight becomes sharply peaked at

$$
f^a=0.
$$

Thus the limit $\xi\to0$ enforces

$$
\partial^\mu A_\mu^a=0.
$$

This is Landau gauge. It is often useful because the gauge field propagator becomes transverse in momentum space.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§71–74. Path integrals for non-Abelian gauge theory, gauge fixing, ghosts, and BRST.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.4–15.7. Constraint quantization, Faddeev–Popov method, ghosts, and BRST symmetry.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Ch. 31. The Faddeev–Popov prescription and its relation to canonical quantization.
- S. Coleman, “Secret Symmetry,” in *Aspects of Symmetry*. Classic physical discussion of spontaneous symmetry breaking, gauge fields, and the Faddeev–Popov Ansatz.
- L. D. Faddeev and V. N. Popov, “Feynman diagrams for the Yang–Mills field,” *Physics Letters B* **25** (1967) 29–30.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Constraint and BRST perspective.
- I. M. Singer, “Some remarks on the Gribov ambiguity,” *Communications in Mathematical Physics* **60** (1978) 7–12.
- V. N. Gribov, “Quantization of non-Abelian gauge theories,” *Nuclear Physics B* **139** (1978) 1–19.

## Version history

- 2026-06-17: Initial polished draft. Added gauge-orbit slice figure, Faddeev–Popov insertion, covariant gauges, residual transformations, Gribov-copy caveats, boundary warnings, and exercises with solutions.
