---
title: "Nonlinear Sigma Models"
description: "Nonlinear sigma models as geometric effective field theories: fields as maps into target spaces, coset manifolds, constrained variables, derivative interactions, power counting, topology, and RG behavior."
sidebar:
  label: "Nonlinear Sigma Models"
  order: 30
level: Graduate
status: "Polished draft"
source: "Polyakov 1987, chs. 2 and 8; Zinn-Justin 2021, nonlinear sigma models and critical phenomena; Weinberg Vol. II, effective Lagrangians; Coleman 1985, symmetry and soft-pion lectures; Burgess 2020, chs. 2, 4, and 8."
topics:
  - nonlinear sigma models
  - target spaces
  - coset manifolds
  - Goldstone bosons
  - derivative expansion
  - topological terms
canonicalTopics:
  - nonlinear-sigma-model
  - sigma-model-target-space
  - coset-effective-field-theory
researchStatus:
  established:
    - "Nonlinear sigma models are standard EFTs for fields constrained to a target manifold, especially Goldstone bosons and order-parameter fields."
  active:
    - "Sigma models remain active in low-dimensional QFT, condensed matter, asymptotic freedom, topology, anomalies, lattice systems, string theory, and nonperturbative dynamics."
---

## Summary

A nonlinear sigma model is a field theory in which the field is not simply a collection of unconstrained scalar functions. Instead, it is a map

$$
\phi:X\longrightarrow \mathcal M
$$

from spacetime, Euclidean space, or a statistical-mechanical base space $X$ into a target manifold $\mathcal M$.

In local coordinates $\phi^i$ on $\mathcal M$, the leading two-derivative action is

$$
S=\frac12\int d^d x\,g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j,
$$

where $g_{ij}(\phi)$ is the target-space metric. The word nonlinear refers to the fact that the target is curved or constrained, so the kinetic term produces interactions when expanded around a point.

The simplest example is the $O(N)$ model in its nonlinear form:

$$
n^a(x)n^a(x)=1,
\qquad a=1,\ldots,N,
$$

with action

$$
S=\frac{f^2}{2}\int d^d x\,\partial_\mu n^a\partial^\mu n^a.
$$

The field $n(x)$ lives on $S^{N-1}$. Chiral perturbation theory is a more structured example: the target space is the chiral coset

$$
\frac{SU(N_f)_L\times SU(N_f)_R}{SU(N_f)_V}\simeq SU(N_f).
$$

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Nonlinear sigma model as a map from spacetime into a target manifold with tangent fluctuations, target metric, derivative expansion, and possible topological terms](/figures/renormalization-rg-eft/nonlinear-sigma-model-target-map.svg)

<figcaption>

A nonlinear sigma model describes fields as maps into a target manifold $\mathcal M$. The target metric gives the two-derivative kinetic term, curvature generates derivative interactions, and topology can allow terms not visible in the local metric alone.

</figcaption>
</figure>

:::note[Why this page matters]
Nonlinear sigma models are the geometric language of Goldstone bosons, order parameters, strings, spin systems, low-dimensional asymptotic freedom, and many EFTs with constrained fields. They are where symmetry, geometry, topology, and RG meet without asking permission first.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Chiral Perturbation Theory](/renormalization-rg-eft/major-efts/chiral-perturbation-theory/), and the basic idea of spontaneous symmetry breaking. Some comfort with manifolds, tangent spaces, and metrics is useful, but the page develops the needed geometric vocabulary as it goes.

This page uses the mostly-minus Lorentzian convention when writing Lagrangians. Many sigma models in statistical mechanics and string theory are written in Euclidean signature; the geometric structure is the same, while signs in the action change.

## Core idea

An ordinary scalar field is often described as a map

$$
\phi:X\to \mathbb R.
$$

A multiplet of scalar fields is a map to $\mathbb R^N$. A nonlinear sigma model replaces $\mathbb R^N$ by a manifold $\mathcal M$:

$$
\phi:X\to \mathcal M.
$$

The field values are constrained globally by geometry. For example:

| Target $\mathcal M$ | Field description | Common physics |
|---|---|---|
| $S^{N-1}$ | unit vector $n^a n^a=1$ | magnets, Goldstone modes, $O(N)$ models |
| $G/H$ | coset representative | spontaneous symmetry breaking |
| $SU(N_f)$ | chiral matrix $U(x)$ | chiral perturbation theory |
| general Riemannian manifold | coordinates $\phi^i$ with metric $g_{ij}$ | strings, geometric EFTs, disordered systems |

The leading action is the natural kinetic energy for a map into a curved target. It measures how much the field changes in spacetime using the target metric:

$$
\mathcal L_2
=\frac12g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j.
$$

If $g_{ij}$ depends on $\phi$, this kinetic term contains interactions. There is no potential needed for the theory to be nonlinear.

## From linear fields to constrained fields

Consider a scalar multiplet $\Phi^a$ with an $O(N)$-invariant potential

$$
V(\Phi)=\frac\lambda4(\Phi^a\Phi^a-v^2)^2.
$$

For large radial mass, the low-energy configurations lie near

$$
\Phi^a\Phi^a=v^2.
$$

Write

$$
\Phi^a(x)=v\,n^a(x),
\qquad n^a n^a=1.
$$

The radial mode has been integrated out, leaving the unit-vector field $n^a$. The kinetic term becomes

$$
\frac12\partial_\mu\Phi^a\partial^\mu\Phi^a
\longrightarrow
\frac{v^2}{2}\partial_\mu n^a\partial^\mu n^a.
$$

This is the $O(N)$ nonlinear sigma model.

The lesson is very EFT-ish:

$$
\text{heavy radial mode removed}
\quad\Longrightarrow\quad
\text{light angular fields constrained to a target manifold}.
$$

The nonlinear sigma model is not less fundamental because it has a constraint. It is the correct low-energy description when radial fluctuations are not resolved.

## The O(N) example

The $O(N)$ nonlinear sigma model uses a unit vector

$$
n(x)=(n^1(x),\ldots,n^N(x)),
\qquad n^a n^a=1.
$$

A convenient local parametrization near the north pole is

$$
n^i=\frac{\pi^i}{f},
\qquad i=1,\ldots,N-1,
$$

and

$$
n^N=\sqrt{1-\frac{\pi^i\pi^i}{f^2}}.
$$

The action

$$
\mathcal L=\frac{f^2}{2}\partial_\mu n^a\partial^\mu n^a
$$

then becomes

$$
\mathcal L
=\frac12\partial_\mu\pi^i\partial^\mu\pi^i
+\frac{1}{2f^2}\frac{(\pi^i\partial_\mu\pi^i)^2}{1-\pi^j\pi^j/f^2}.
$$

Expanding at small $\pi/f$,

$$
\mathcal L
=\frac12(\partial\pi)^2
+\frac{1}{2f^2}(\pi\cdot\partial_\mu\pi)^2
+O(\pi^4(\partial\pi)^2/f^4).
$$

The interactions are derivative interactions generated by the sphere constraint.

:::tip[The field coordinates are not unique]
The fields $\pi^i$ are coordinates on $S^{N-1}$ near one point. Another parametrization gives different interaction terms off shell, but the same physical observables when used consistently. Coordinates on target space are not physics.
:::

## Geometric form

Let $\phi^i$ be local coordinates on $\mathcal M$. A coordinate change on the target is

$$
\phi^i\longrightarrow \phi^{\prime i}(\phi).
$$

The action

$$
S=\frac12\int d^d x\,g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j
$$

is invariant under such coordinate changes because $g_{ij}$ transforms as a tensor and $\partial_\mu\phi^i$ transforms as a tangent vector on the target.

This makes the sigma model a geometric EFT. The leading data are:

$$
(\mathcal M,g).
$$

Higher-derivative terms involve curvature tensors and covariant derivatives on the target. A schematic derivative expansion is

$$
\mathcal L
=\frac12g_{ij}(\phi)\partial\phi^i\partial\phi^j
+c_1 R_{ikjl}(\phi)\partial\phi^i\partial\phi^j\partial\phi^k\partial\phi^l
+c_2 \nabla R\,\partial\phi\partial\phi\partial\phi\partial\phi\partial\phi
+\cdots,
$$

where the precise set of terms depends on spacetime dimension, symmetries, integration by parts, and field redefinitions.

## Normal coordinates and interactions

Near a point $p\in\mathcal M$, choose Riemann normal coordinates. Then

$$
g_{ij}(\phi)
=\delta_{ij}
-\frac13R_{ikjl}(p)\phi^k\phi^l
+O(\phi^3).
$$

The leading Lagrangian becomes

$$
\mathcal L_2
=\frac12\delta_{ij}\partial_\mu\phi^i\partial^\mu\phi^j
-\frac16R_{ikjl}(p)\phi^k\phi^l\partial_\mu\phi^i\partial^\mu\phi^j
+\cdots.
$$

Thus target-space curvature is the local source of derivative self-interactions. A flat target has no such interactions in appropriate coordinates. A curved target cannot be flattened globally, and even locally the curvature reappears in higher-order terms.

This is one of the cleanest ways to remember what sigma-model interactions mean:

$$
\text{sigma-model interactions}\quad\leftrightarrow\quad\text{target-space geometry}.
$$

## Coset sigma models

When a continuous global symmetry $G$ is spontaneously broken to a subgroup $H$, the Goldstone fields live on

$$
G/H.
$$

A coset representative can be written as

$$
\xi(x)=\exp\!\left(i\pi^a(x)X_a/f\right),
$$

where $X_a$ are broken generators. The symmetry group acts by left multiplication,

$$
g\xi(x)=\xi'(x)h(g,\pi(x)),
\qquad h\in H.
$$

The compensating transformation $h$ depends on the group element and the Goldstone fields. This is the mathematical expression of nonlinear symmetry realization.

Chiral perturbation theory is a coset sigma model with

$$
G=SU(N_f)_L\times SU(N_f)_R,
\qquad
H=SU(N_f)_V.
$$

The field $U(x)$ used there is a convenient coset coordinate with transformation law

$$
U\mapsto LUR^\dagger.
$$

## Power counting in d dimensions

The leading sigma-model kinetic term has two derivatives. If the target coordinates are normalized so that the fields have canonical kinetic terms, interactions are suppressed by powers of a scale $f$.

In $d$ spacetime dimensions,

$$
[f]=\frac{d-2}{2}.
$$

For $d=4$, $f$ has dimension one and the derivative expansion is nonrenormalizable in the old power-counting sense. This is exactly what happens in chiral perturbation theory: the theory is predictive because it is organized as an EFT.

For $d=2$, the sigma-model coupling is dimensionless. Two-dimensional sigma models have special RG behavior. The $O(N)$ model with $N>2$ is asymptotically free, with schematic one-loop beta function

$$
\mu\frac{dg}{d\mu}
=-\frac{N-2}{2\pi}g^2+O(g^3),
$$

for the conventional action

$$
S=\frac{1}{2g}\int d^2x\,\partial_\mu n^a\partial_\mu n^a.
$$

This is why nonlinear sigma models are central both in EFT and in two-dimensional quantum field theory.

## Topological terms

The target-space metric does not exhaust the possible action. If the target has nontrivial topology, additional terms may be allowed.

Examples include:

| Term | Typical condition | Physical role |
|---|---|---|
| theta term | nontrivial $\pi_d(\mathcal M)$ or cohomology | weights topological sectors |
| Wess-Zumino term | extension to one higher dimension | encodes anomalies and quantized terms |
| Wess-Zumino-Witten term | chiral symmetry and anomaly matching | reproduces anomalous pion processes |
| Berry-phase term | first-order time derivative or coherent-state path integral | spin systems and quantum phases |

For example, a two-dimensional sigma model may have a theta term schematically of the form

$$
S_\theta=i\theta Q,
$$

where $Q$ is an integer-valued topological charge. Such a term does not change the local target metric, but it can dramatically change the quantum theory.

## Relation to linear sigma models

A linear sigma model often has unconstrained fields and a potential that dynamically creates a vacuum manifold. A nonlinear sigma model keeps only the low-energy motion along that vacuum manifold.

For the $O(N)$ example:

$$
\text{linear field }\Phi^a
\quad\xrightarrow{\text{integrate out radial mode}}\quad
\text{unit vector }n^a=\Phi^a/v.
$$

The linear theory knows about both radial and angular fluctuations. The nonlinear theory knows only about angular fluctuations. The nonlinear theory is therefore the right EFT below the radial mass.

This relation is useful, but it can also mislead. Not every nonlinear sigma model needs a weakly coupled linear parent. Some target spaces, topological terms, and strongly coupled phases are best understood intrinsically.

## Example: CP models

Another important family is the complex projective sigma model $\mathbb{CP}^{N-1}$. One representation uses complex fields $z_i$ with constraint

$$
z^\dagger z=1,
$$

and a local redundancy

$$
z(x)\sim e^{i\alpha(x)}z(x).
$$

The target space is

$$
\mathbb{CP}^{N-1}=\frac{SU(N)}{SU(N-1)\times U(1)}.
$$

These models are important because they share features with non-Abelian gauge theory: asymptotic freedom in two dimensions, instantons, large-$N$ structure, and nonperturbative mass generation. They are a favorite laboratory for the physics of confinement-like behavior in simpler settings.

## What the sigma model does and does not know

A nonlinear sigma model knows the low-energy geometry of the light fields. It knows:

- the vacuum manifold or target space;
- symmetry actions on the target;
- derivative interactions;
- possible topological sectors;
- the local EFT expansion around slowly varying configurations.

It does not automatically know:

- the UV completion;
- the mass and couplings of radial modes;
- the values of all higher-derivative coefficients;
- whether a perturbative expansion remains reliable at all scales;
- which nonperturbative phase is realized without additional dynamics.

This is the standard EFT contract. The sigma model gives the most general low-energy description consistent with its degrees of freedom and symmetries, not a microscopic confession of the universe.

## Common pitfalls

**Thinking nonlinear means nonperturbative.** A nonlinear sigma model can be treated perturbatively around slowly varying fields or small fluctuations. Nonlinear means the target-space geometry is nonlinear, not that calculations are impossible.

**Forgetting coordinate dependence.** Individual interaction terms depend on the coordinates chosen on $\mathcal M$. Physical observables do not.

**Treating the constraint as a gauge symmetry.** The condition $n^a n^a=1$ is a constraint on field values. It is not by itself a gauge redundancy. Some parametrizations, such as $\mathbb{CP}^{N-1}$ variables, do introduce redundancies.

**Ignoring topology.** A sigma model is not determined only by its local metric if topological terms are allowed.

**Using four-dimensional EFT intuition in two dimensions without adjustment.** In $d=4$, sigma models are nonrenormalizable EFTs. In $d=2$, the leading coupling is dimensionless and the RG can produce asymptotic freedom and mass gaps.

**Confusing the linear and nonlinear sigma models.** The nonlinear model is a low-energy limit of some linear models, but it is not just the linear model with a parameter set to infinity in every context.

## Relation to other pages

[Chiral Perturbation Theory](/renormalization-rg-eft/major-efts/chiral-perturbation-theory/) is the main particle-physics example of a nonlinear sigma model. [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/) explains why all symmetry-allowed local terms must be included. [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/) and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/) explain why different target coordinates and operator bases can describe the same physics.

The fixed-point and critical-phenomena chapters explain why sigma models also arise as continuum limits of spin systems. The gauge-theory chapters explain why two-dimensional sigma models provide useful analogies to asymptotic freedom and dimensional transmutation.

## Research status

The geometric formulation of nonlinear sigma models is established. Their use as EFTs for Goldstone bosons and order parameters is standard.

Active research includes sigma models with topological terms, boundary conditions and defects, anomaly constraints, generalized symmetries, nonperturbative mass generation, large-$N$ expansions, conformal sigma models, string-worldsheet beta functions, and condensed-matter applications to quantum magnets and topological phases.

The main practical caveat is scale. A nonlinear sigma model can be an excellent low-energy EFT and still fail at high enough energy, where radial modes, resonances, lattice effects, or other degrees of freedom become visible.

## Exercises

### Exercise 1: Derive the O(N) nonlinear kinetic term

Let

$$
n^i=\frac{\pi^i}{f},
\qquad
n^N=\sqrt{1-\frac{\pi^i\pi^i}{f^2}},
\qquad i=1,\ldots,N-1.
$$

Show that

$$
\frac{f^2}{2}\partial_\mu n^a\partial^\mu n^a
=\frac12\partial_\mu\pi^i\partial^\mu\pi^i
+\frac{1}{2f^2}\frac{(\pi^i\partial_\mu\pi^i)^2}{1-\pi^j\pi^j/f^2}.
$$

<details><summary><strong>Solution</strong></summary>

The first $N-1$ components give

$$
\partial_\mu n^i=\frac{1}{f}\partial_\mu\pi^i,
$$

so

$$
\frac{f^2}{2}\partial_\mu n^i\partial^\mu n^i
=\frac12\partial_\mu\pi^i\partial^\mu\pi^i.
$$

For the last component,

$$
\partial_\mu n^N
=\frac{1}{2}\left(1-\frac{\pi^2}{f^2}\right)^{-1/2}
\left(-\frac{2\pi^i\partial_\mu\pi^i}{f^2}\right)
=-\frac{\pi^i\partial_\mu\pi^i}{f^2\sqrt{1-\pi^2/f^2}}.
$$

Therefore

$$
\frac{f^2}{2}\partial_\mu n^N\partial^\mu n^N
=\frac{1}{2f^2}\frac{(\pi^i\partial_\mu\pi^i)^2}{1-\pi^j\pi^j/f^2}.
$$

Adding the two pieces gives the stated result.

</details>

### Exercise 2: Dimension of the sigma-model scale

For the leading Lagrangian

$$
\mathcal L=\frac{f^2}{2}\partial_\mu n^a\partial^\mu n^a,
\qquad n^a n^a=1,
$$

find the mass dimension of $f$ in $d$ spacetime dimensions.

<details><summary><strong>Solution</strong></summary>

The unit vector $n^a$ is dimensionless. The derivative has dimension one, so

$$
[\partial_\mu n^a\partial^\mu n^a]=2.
$$

Since the Lagrangian density has dimension $d$,

$$
[f^2]+2=d.
$$

Thus

$$
[f^2]=d-2,
\qquad
[f]=\frac{d-2}{2}.
$$

In $d=4$, $f$ has dimension one. In $d=2$, $f$ is dimensionless.

</details>

### Exercise 3: Why the target metric matters

In Riemann normal coordinates near $p\in\mathcal M$,

$$
g_{ij}(\phi)=\delta_{ij}-\frac13R_{ikjl}(p)\phi^k\phi^l+O(\phi^3).
$$

Show that a nonzero target-space curvature produces a four-field derivative interaction.

<details><summary><strong>Solution</strong></summary>

Insert the metric expansion into

$$
\mathcal L=\frac12g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j.
$$

The first term gives the free kinetic term:

$$
\frac12\delta_{ij}\partial_\mu\phi^i\partial^\mu\phi^j.
$$

The next term gives

$$
-\frac16R_{ikjl}(p)\phi^k\phi^l\partial_\mu\phi^i\partial^\mu\phi^j.
$$

This contains two undifferentiated fields and two differentiated fields, so it is a four-field derivative interaction. It vanishes locally only when the relevant curvature components vanish.

</details>

## References

- A. M. Polyakov, *Gauge Fields and Strings*, for sigma models, asymptotic freedom, large-$N$ methods, and the relation to gauge and string ideas.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for sigma models in critical phenomena and RG.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for effective Lagrangians and nonlinear realizations.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, symmetry, and spontaneous symmetry breaking.
- C. P. Burgess, *Introduction to Effective Field Theory*, for EFT logic, symmetry realization, and redundant interactions.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for sigma models in many-body and condensed-matter settings.

## Version history

- 2026-06-19: First polished draft. Introduced sigma models as maps into target manifolds, the $O(N)$ example, coset construction, geometric interactions, power counting, topological terms, and worked exercises.
