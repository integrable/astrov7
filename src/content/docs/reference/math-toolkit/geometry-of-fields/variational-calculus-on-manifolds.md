---
title: "Variational Calculus on Manifolds"
description: "Explains covariant variational calculus for actions written as top forms, including Euler–Lagrange forms, boundary terms, Noether currents, stress tensors, and covariant phase space."
sidebar:
  label: "Variational Calculus on Manifolds"
  order: 12
level: Advanced
status: "Polished draft"
source: "Standard references on variational calculus, differential geometry, classical field theory, covariant phase space, and QFT on manifolds, including Frankel, Nakahara, Wald, Lee–Wald, Iyer–Wald, Deligne et al., Anderson, Olver, and modern gauge-theory treatments."
topics:
  - variational calculus
  - manifolds
  - Lagrangian forms
  - Euler–Lagrange forms
  - boundary terms
  - functional differentiability
  - Noether currents
  - stress tensor
  - covariant phase space
  - symplectic current
canonicalTopics:
  - variational-calculus-on-manifolds
  - lagrangian-form
  - euler-lagrange-form
  - presymplectic-potential
  - noether-current
  - stress-tensor
  - covariant-phase-space
  - functional-differentiability
researchStatus:
  established:
    - "For local Lagrangian field theories on manifolds, the first variation splits canonically into Euler–Lagrange terms plus an exact boundary term, up to standard boundary and total-derivative ambiguities."
  active:
    - "Modern work refines this calculus for gauge theory, gravity, boundaries, corners, edge modes, asymptotic symmetries, defects, anomalies, and non-Lagrangian QFT data."
---

## Summary

Variational calculus on manifolds is the invariant language for deriving field equations, boundary conditions, Noether currents, stress tensors, and symplectic structures from an action. The action is written as the integral of an $n$-form over an $n$-dimensional manifold:

$$
S[\phi]=\int_M L(\phi).
$$

The central formula is the first variation

$$
\delta L=E_i(\phi)\,\delta\phi^i+d\theta(\phi,\delta\phi).
$$

Here $E_i=0$ are the Euler–Lagrange equations, while $\theta$ is the boundary term, also called the presymplectic potential current. That tiny $d\theta$ term is responsible for boundary conditions, charges, Hamiltonian differentiability, covariant phase space, and many sign migraines.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flow diagram showing an action as the integral of a top form, the first variation into bulk Euler–Lagrange terms and a boundary term, and the resulting equations, functional differentiability, Noether currents, stress tensors, and covariant phase space.](/figures/math-toolkit/variational-calculus-form-flow.svg)

<figcaption>

The covariant first-variation formula splits the variation of a Lagrangian top form into a bulk term and an exact term. The bulk term gives equations of motion; the exact term controls boundaries, charges, and symplectic structure.

</figcaption>
</figure>

This page explains the invariant form of the calculus. Earlier variational pages treat functional derivatives and Euler–Lagrange operators in coordinates. Here the point is to write everything in a way that survives curved backgrounds, differential forms, gauge fields, boundaries, and diffeomorphisms.

## Prerequisites

Read [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/), [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/) first.

For the coordinate version of the same ideas, see [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/), [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/), and [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/). For spinor actions, the companion page [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) fixes the spin-connection and Clifford-action input.

## Core idea

A field theory action should not depend on a choice of coordinates. The clean way to achieve this is to make the Lagrangian an $n$-form $L$ on spacetime, possibly built from fields, their derivatives, the metric, connections, and background structures.

Then the variation of $L$ always has the schematic form

$$
\delta L=\text{bulk equations}\,+\,d(\text{boundary term}).
$$

The two pieces have different jobs.

| Piece | Role |
|---|---|
| $E_i\delta\phi^i$ | Gives Euler–Lagrange equations and constraints. |
| $d\theta$ | Gives boundary terms, symplectic structure, and charges. |
| Total derivative shifts $L\mapsto L+dB$ | Leave bulk equations unchanged but can change boundary data. |
| Symmetry variations | Produce Noether currents that are closed on shell. |

The main lesson is simple and merciless:

$$
\text{never throw away a boundary term until you know what boundary problem you are solving.}
$$

On a compact manifold without boundary and with compactly supported variations, $d\theta$ integrates to zero. In QFT, gravity, gauge theory, finite-temperature field theory, defects, entangling surfaces, and asymptotic scattering problems, that assumption is often false. The boundary term is where the physics sneaks back in wearing sensible shoes.

## Setup and conventions

Let $M$ be an oriented $n$-dimensional smooth manifold, possibly with boundary $\partial M$. Fields are denoted collectively by $\phi^i$. More invariantly, fields are sections of some bundle over $M$, but local components are often enough for formulas.

The Lagrangian is an $n$-form

$$
L=L(\phi,d\phi,\nabla\phi,g,A,\ldots).
$$

In coordinates it is often written as

$$
L=\mathcal L\,d^nx
$$

or, on a metric manifold,

$$
L=\mathcal L\,\sqrt{|g|}\,d^nx.
$$

We use two exterior derivatives:

| Symbol | Acts on | Meaning |
|---|---|---|
| $d$ | spacetime forms | Exterior derivative on $M$. |
| $\delta$ | fields | Variation, or field-space exterior derivative. |

They are conceptually different. The first moves around spacetime; the second moves in the space of field configurations. For local field variations one usually takes

$$
\delta d=d\delta.
$$

Unless stated otherwise, variations are assumed to be smooth and either compactly supported or compatible with the boundary conditions under discussion.

## The first variation formula

For a local Lagrangian $n$-form, repeated integration by parts gives

$$
\delta L=E_i(\phi)\,\delta\phi^i+d\theta(\phi,\delta\phi).
$$

The $E_i$ are Euler–Lagrange expressions packaged as $n$-form coefficients. The equation of motion is

$$
E_i(\phi)=0.
$$

The $(n-1)$-form $\theta(\phi,\delta\phi)$ is the boundary term produced by the variation. In the covariant phase-space literature it is called the presymplectic potential current.

In coordinates, for a first-order Lagrangian density

$$
\mathcal L=\mathcal L(\phi^i,\partial_\mu\phi^i,x),
$$

the same formula says

$$
\delta(\mathcal L\,d^nx)
=\left(
\frac{\partial\mathcal L}{\partial\phi^i}
-\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
\right)\delta\phi^i\,d^nx
+d\theta,
$$

with local boundary current

$$
\theta^\mu=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\delta\phi^i.
$$

In form notation, $\theta$ is the $(n-1)$-form obtained from $\theta^\mu$ by contraction with the coordinate volume form.

The variation of the action is therefore

$$
\delta S
=\int_M E_i\delta\phi^i+\int_{\partial M}\theta.
$$

The first integral gives the equations. The second integral tells you whether the variational principle is actually well posed.

## Boundary terms and differentiability

A variational principle is well posed only after specifying what happens at the boundary. The condition is not merely

$$
E_i=0.
$$

It is

$$
\delta S=0
$$

for all allowed variations. On shell,

$$
\delta S\big|_{E=0}=\int_{\partial M}\theta.
$$

Thus a boundary condition must make the boundary integral vanish, or the action must be modified by a boundary term. If

$$
S' = S + \int_{\partial M} B
$$

or equivalently

$$
L' = L+dB,
$$

then

$$
\delta L'=E_i\delta\phi^i+d(\theta+\delta B).
$$

So total derivatives do not change the bulk equations, but they do change the boundary term:

$$
\theta\mapsto\theta+\delta B.
$$

This is why the phrase “up to a total derivative” is harmless for local equations of motion and dangerous for boundary charges.

The same issue appears in Hamiltonian language. A functional $H$ is differentiable only if its variation can be written as a bulk pairing with $\delta\phi$ and no uncanceled boundary variation. Gauge theory and gravity often require adding boundary charges to make the Hamiltonian generators differentiable.

## Example: scalar field on a metric background

Let $M$ be a Lorentzian manifold with mostly-minus signature, and take the scalar action

$$
S[\phi]=\int_M d^nx\sqrt{|g|}\left(
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-V(\phi)
\right).
$$

Varying the scalar gives

$$
\delta S
=\int_M d^nx\sqrt{|g|}\left(
-g^{\mu\nu}\nabla_\mu\nabla_\nu\phi
-V'(\phi)
\right)\delta\phi
+\int_{\partial M} d^{n-1}y\sqrt{|h|}\,n_\mu\nabla^\mu\phi\,\delta\phi.
$$

Equivalently, the bulk equation is

$$
\Box\phi+V'(\phi)=0,
$$

where

$$
\Box=\nabla_\mu\nabla^\mu.
$$

For

$$
V(\phi)=\frac12m^2\phi^2,
$$

this gives

$$
(\Box+m^2)\phi=0.
$$

The boundary term is

$$
\int_{\partial M} d^{n-1}y\sqrt{|h|}\,n_\mu\nabla^\mu\phi\,\delta\phi.
$$

There are several ways to make it vanish or cancel it:

| Boundary choice | Condition |
|---|---|
| Dirichlet | Fix $\phi$ at $\partial M$, so $\delta\phi=0$. |
| Neumann | Impose $n_\mu\nabla^\mu\phi=0$. |
| Robin | Impose a linear relation between $\phi$ and $n_\mu\nabla^\mu\phi$. |
| Boundary action | Add $B(\phi)$ on $\partial M$ and vary the combined action. |

The bulk equation alone does not choose among these. Boundary physics chooses.

## Example: Yang–Mills variation in form language

Let $\mathcal A$ be an anti-Hermitian connection one-form and

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

The Yang–Mills Lagrangian $n$-form can be written schematically as

$$
L_{\mathrm{YM}}=-\frac{1}{2g^2}\operatorname{tr}(\mathcal F\wedge *\mathcal F),
$$

with trace and sign conventions chosen consistently with the metric signature.

The curvature variation is

$$
\delta\mathcal F=D_{\mathcal A}\delta\mathcal A.
$$

The first variation has the form

$$
\delta L_{\mathrm{YM}}
=\frac{1}{g^2}\operatorname{tr}\bigl(\delta\mathcal A\wedge D_{\mathcal A}*\mathcal F\bigr)
+d\theta_{\mathrm{YM}},
$$

up to the standard sign depending on form-degree and trace convention. The Euler–Lagrange equation is

$$
D_{\mathcal A}*\mathcal F=0.
$$

The boundary term is proportional to

$$
\theta_{\mathrm{YM}}\sim -\frac{1}{g^2}\operatorname{tr}(\delta\mathcal A\wedge *\mathcal F).
$$

This boundary term is the geometric ancestor of electric flux, gauge charges, edge modes, and the distinction between fixing the gauge potential versus fixing the electric field at a boundary.

The Bianchi identity

$$
D_{\mathcal A}\mathcal F=0
$$

is not obtained by varying the action. It is an identity following from the definition of curvature. Field equations and Bianchi identities are different beasts. They merely wear similar notation to confuse the sleepy.

## Metric variation and the stress tensor

If the metric is treated as a background field, varying the matter action with respect to the metric defines the stress tensor. With the mostly-minus convention used here, we define

$$
\delta_g S_{\mathrm{matter}}
=\frac12\int_M d^nx\sqrt{|g|}\,T_{\mu\nu}\,\delta g^{\mu\nu}.
$$

Equivalently,

$$
\delta_g S_{\mathrm{matter}}
=-\frac12\int_M d^nx\sqrt{|g|}\,T^{\mu\nu}\,\delta g_{\mu\nu}.
$$

For the scalar action above, this gives

$$
T_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi
-g_{\mu\nu}\left(
\frac12 g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi
-V(\phi)
\right).
$$

In flat mostly-minus coordinates, the energy density is

$$
T_{00}=\frac12\dot\phi^2+\frac12(\nabla\phi)^2+V(\phi),
$$

as it should be.

Many relativity and QFT references use the opposite sign in the definition of $T_{\mu\nu}$ because they vary with respect to a different metric convention or place a minus sign in the matter-action definition. Do not compare stress tensors without checking the definition of

$$
\delta S_{\mathrm{matter}}.
$$

For a diffeomorphism-invariant matter theory, metric variation also gives covariant conservation on shell:

$$
\nabla_\mu T^{\mu\nu}=0,
$$

modulo external sources and background-field equations.

## Diffeomorphisms and Noether currents

Let $\xi$ be a vector field generating an infinitesimal diffeomorphism. The field variation is

$$
\delta_\xi\phi=\mathcal L_\xi\phi,
$$

with the appropriate Lie derivative for the type of field.

If $L$ is a covariant $n$-form, then

$$
\delta_\xi L=\mathcal L_\xi L=d(\iota_\xi L),
$$

because $dL=0$ for an $n$-form on an $n$-dimensional manifold.

Using the first variation formula,

$$
\delta_\xi L=E_i\mathcal L_\xi\phi^i+d\theta(\phi,\mathcal L_\xi\phi).
$$

On shell, $E_i=0$, so

$$
d\left[\theta(\phi,\mathcal L_\xi\phi)-\iota_\xi L\right]=0.
$$

The Noether current $(n-1)$-form for diffeomorphisms is therefore

$$
J_\xi=\theta(\phi,\mathcal L_\xi\phi)-\iota_\xi L.
$$

On shell,

$$
dJ_\xi=0.
$$

In gauge theories and gravity, such currents often decompose further into constraints plus an exact form:

$$
J_\xi=C_\xi+dQ_\xi,
$$

where $Q_\xi$ is a Noether charge $(n-2)$-form. This is the entry point to black-hole entropy, asymptotic charges, edge modes, and covariant phase space.

## Internal symmetries and conserved currents

For an internal symmetry with infinitesimal parameter $\epsilon$, suppose

$$
\delta_\epsilon L=d\alpha_\epsilon.
$$

Then the Noether current is

$$
J_\epsilon=\theta(\phi,\delta_\epsilon\phi)-\alpha_\epsilon.
$$

The first variation gives

$$
dJ_\epsilon=-E_i\delta_\epsilon\phi^i,
$$

so on shell

$$
dJ_\epsilon=0.
$$

If $J_\epsilon$ is an $(n-1)$-form, the conserved charge on a spatial hypersurface $\Sigma$ is

$$
Q_\epsilon=\int_\Sigma J_\epsilon,
$$

provided the integral is finite and boundary fluxes vanish or are controlled.

For gauge symmetries, the story is subtler. Gauge transformations that vanish at the boundary usually represent redundancy and generate constraints. Gauge transformations that do not vanish at the boundary can generate physical charges. The difference is decided by the boundary term in the variation, not by the local gauge parameter alone.

## Covariant phase space

The same boundary term $\theta$ that appears in the first variation also defines the covariant symplectic current. Treat $\delta$ as an exterior derivative on field space. Then

$$
\omega(\phi;\delta_1\phi,\delta_2\phi)
=\delta_1\theta(\phi,\delta_2\phi)
-\delta_2\theta(\phi,\delta_1\phi).
$$

This is an $(n-1)$-form on spacetime and a two-form on field space. On solutions and for variations satisfying the linearized equations,

$$
d\omega=0.
$$

Given a Cauchy surface or hypersurface $\Sigma$, define

$$
\Omega_\Sigma(\delta_1\phi,\delta_2\phi)=\int_\Sigma\omega(\phi;\delta_1\phi,\delta_2\phi).
$$

If no symplectic flux escapes through the boundary, $\Omega_\Sigma$ is independent of the choice of $\Sigma$. This is the covariant version of the Hamiltonian symplectic form.

There are two important ambiguities:

$$
L\mapsto L+dB,
$$

and

$$
\theta\mapsto\theta+dY.
$$

The first changes $\theta$ by $\delta B$. The second leaves the first variation unchanged but can affect boundary and corner terms. In closed systems these ambiguities may not matter. With boundaries, corners, defects, or asymptotic regions, they can matter a lot.

## Gravity and the boundary warning

The Einstein–Hilbert Lagrangian is

$$
L_{\mathrm{EH}}=\frac{1}{16\pi G}R\,\epsilon,
$$

where $\epsilon=\sqrt{|g|}\,d^nx$ is the metric volume form.

Its variation has the form

$$
\delta L_{\mathrm{EH}}
=\frac{1}{16\pi G}G_{\mu\nu}\delta g^{\mu\nu}\epsilon
+d\theta_{\mathrm{EH}}.
$$

The boundary term $\theta_{\mathrm{EH}}$ contains derivatives of $\delta g_{\mu\nu}$. Therefore, fixing the metric at the boundary is not enough to make the Einstein–Hilbert action differentiable. One usually adds the Gibbons–Hawking–York boundary term for Dirichlet metric boundary conditions.

This is the cleanest warning sign in the subject: two actions that differ by a boundary term can give the same Einstein equations and different boundary variational principles. Bulk equations are not the whole theory.

## Locality, higher derivatives, and covariant integration by parts

The first-variation formula remains true for higher-derivative Lagrangians:

$$
L=L(\phi,\nabla\phi,\nabla\nabla\phi,\ldots).
$$

Repeated covariant integration by parts moves derivatives off $\delta\phi$ and into the Euler–Lagrange expressions. For example, a second-derivative term produces boundary terms involving both $\delta\phi$ and derivatives of $\delta\phi$.

When covariant derivatives do not commute, integration by parts may produce curvature terms:

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma.
$$

Gauge-covariant derivatives similarly produce field strengths. This is one reason covariant variational calculus is best done with a clear distinction between identities, equations of motion, and boundary terms.

## Common pitfalls

**Dropping the boundary term too early.** The exact term $d\theta$ vanishes only under specific assumptions. In gauge theory, gravity, finite-volume QFT, and asymptotic scattering, it often carries the charges.

**Confusing $d$ and $\delta$.** The symbol $d$ differentiates spacetime forms. The symbol $\delta$ varies the fields. They often commute in local calculations, but they are not the same operation.

**Thinking total derivatives never matter.** A total derivative does not change local Euler–Lagrange equations, but it can change boundary conditions, canonical momenta, charges, and the symplectic potential.

**Using a stress tensor without checking its sign definition.** The sign of $T_{\mu\nu}$ depends on whether one varies $g^{\mu\nu}$ or $g_{\mu\nu}$ and on the metric-signature convention. Always compare the equation defining $\delta S$.

**Treating gauge symmetries exactly like global symmetries.** Gauge transformations that vanish at the boundary are redundancies. Nonvanishing transformations may generate physical boundary charges. The distinction is encoded in the presymplectic form and boundary terms.

**Ignoring corner ambiguities.** If a boundary has a boundary, or a hypersurface has an edge, shifts of $\theta$ by $dY$ can affect corner charges. This is not pedantry; it is central in modern treatments of gravitational and gauge-theory edge modes.

## Relations to other pages

[Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/) and [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/) give the coordinate calculus behind the bulk term $E_i\delta\phi^i$. [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) explains the Hamiltonian version of the same boundary issue. [Symplectic Forms](/math-toolkit/calculus-of-variations-and-phase-space/symplectic-forms/) and [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/) give the phase-space language that $\omega=\delta\theta$ feeds into.

[Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) explain why actions are naturally integrals of top forms. [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/) supplies the Cartan calculus behind diffeomorphism Noether currents. [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) gives the form-language variation of curvature used in Yang–Mills theory. [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) gives the spinor kinetic operator whose action is varied using this machinery.

Later pages on stress tensors, Ward identities, anomalies, gravitational actions, BRST/BV formalism, covariant phase space, asymptotic symmetries, defects, and edge modes should link back here.

## Research status

The local first-variation formula, Euler–Lagrange equations, Noether currents, and stress-tensor definitions are textbook-standard. The covariant phase-space framework is also well established for classical field theory and gravity, though conventions and boundary choices vary across communities.

Active work focuses on the boundary and global refinements: edge modes in gauge theory, gravitational corner charges, asymptotic symmetry algebras, null boundaries, entangling surfaces, defects, anomalies, non-Lagrangian theories, extended phase spaces, and the precise relation between covariant phase space and quantum operator algebras.

## Exercises

### Exercise 1: Scalar first variation

For

$$
S[\phi]=\int_M d^nx\sqrt{|g|}\left(
\frac12g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi-V(\phi)
\right),
$$

show that the bulk equation is

$$
\Box\phi+V'(\phi)=0
$$

in mostly-minus Lorentzian convention.

<details><summary><strong>Solution</strong></summary>

Vary $\phi$ while holding $g_{\mu\nu}$ fixed:

$$
\delta S=\int_M d^nx\sqrt{|g|}\left(
 g^{\mu\nu}\partial_\mu\phi\partial_\nu\delta\phi
 -V'(\phi)\delta\phi
\right).
$$

Use covariant integration by parts:

$$
\int_M\sqrt{|g|}\,\nabla^\mu\phi\nabla_\mu\delta\phi
=-\int_M\sqrt{|g|}\,(\nabla_\mu\nabla^\mu\phi)\delta\phi
+\int_{\partial M}\sqrt{|h|}\,n_\mu\nabla^\mu\phi\,\delta\phi.
$$

Thus the bulk variation is

$$
\delta S_{\mathrm{bulk}}
=-\int_M d^nx\sqrt{|g|}\left(\Box\phi+V'(\phi)\right)\delta\phi.
$$

For arbitrary allowed bulk variations, stationarity requires

$$
\Box\phi+V'(\phi)=0.
$$

</details>

### Exercise 2: Scalar stress tensor

Using the convention

$$
\delta_gS=\frac12\int_M d^nx\sqrt{|g|}\,T_{\mu\nu}\delta g^{\mu\nu},
$$

derive the stress tensor for the scalar action in Exercise 1.

<details><summary><strong>Solution</strong></summary>

Write

$$
\mathcal L=\frac12g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi-V(\phi).
$$

The metric variation is

$$
\delta_gS=\int_M d^nx\left[\delta\sqrt{|g|}\,\mathcal L
+\sqrt{|g|}\frac12\partial_\mu\phi\partial_\nu\phi\,\delta g^{\mu\nu}\right].
$$

For variation with respect to the inverse metric,

$$
\delta\sqrt{|g|}=-\frac12\sqrt{|g|}\,g_{\mu\nu}\delta g^{\mu\nu}.
$$

Therefore

$$
\delta_gS=\frac12\int_M d^nx\sqrt{|g|}\left(
\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L
\right)\delta g^{\mu\nu}.
$$

Comparing with the definition gives

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\left(
\frac12g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi-V(\phi)
\right).
$$

</details>

### Exercise 3: Shift current for a free scalar

For a massless scalar with form Lagrangian

$$
L=\frac12d\phi\wedge *d\phi
$$

in Riemannian signature, the shift symmetry is

$$
\delta_\epsilon\phi=\epsilon,
$$

with constant $\epsilon$. Show that the Noether current is proportional to $*d\phi$ and is conserved on shell.

<details><summary><strong>Solution</strong></summary>

The variation of the Lagrangian is

$$
\delta L=d(\delta\phi)\wedge *d\phi.
$$

Integrate by parts:

$$
d(\delta\phi)\wedge *d\phi
=d(\delta\phi\,*d\phi)-\delta\phi\,d*d\phi.
$$

Thus

$$
\theta=\delta\phi\,*d\phi,
\qquad
E=-d*d\phi.
$$

For the shift symmetry $\delta_\epsilon\phi=\epsilon$ and $\delta_\epsilon L=0$, so $\alpha_\epsilon=0$. The Noether current is

$$
J_\epsilon=\theta(\delta_\epsilon\phi)=\epsilon *d\phi.
$$

On shell,

$$
d*d\phi=0,
$$

so

$$
dJ_\epsilon=\epsilon\,d*d\phi=0.
$$

Hence $*d\phi$ is the conserved current up to the constant parameter $\epsilon$.

</details>

### Exercise 4: Total derivative shift

Suppose

$$
L'=L+dB.
$$

If

$$
\delta L=E_i\delta\phi^i+d\theta,
$$

show that $L'$ has the same Euler–Lagrange equations but a shifted boundary term.

<details><summary><strong>Solution</strong></summary>

Vary $L'$:

$$
\delta L'=\delta L+\delta dB.
$$

Since $\delta$ and $d$ commute in this local field-space calculus,

$$
\delta dB=d\delta B.
$$

Therefore

$$
\delta L'=E_i\delta\phi^i+d\theta+d\delta B
=E_i\delta\phi^i+d(\theta+\delta B).
$$

The Euler–Lagrange term $E_i\delta\phi^i$ is unchanged, so the bulk equations are the same. The boundary term shifts as

$$
\theta\mapsto\theta+\delta B.
$$

</details>

### Exercise 5: Diffeomorphism Noether current

Assume $L$ is a covariant $n$-form and $\delta_\xi\phi=\mathcal L_\xi\phi$. Show that

$$
J_\xi=\theta(\phi,\mathcal L_\xi\phi)-\iota_\xi L
$$

is closed on shell.

<details><summary><strong>Solution</strong></summary>

For a covariant $n$-form,

$$
\delta_\xi L=\mathcal L_\xi L.
$$

By Cartan's formula,

$$
\mathcal L_\xi L=\iota_\xi dL+d(\iota_\xi L).
$$

Since $L$ is an $n$-form on an $n$-dimensional manifold, $dL=0$, so

$$
\delta_\xi L=d(\iota_\xi L).
$$

The first variation formula gives

$$
\delta_\xi L=E_i\mathcal L_\xi\phi^i+d\theta(\phi,\mathcal L_\xi\phi).
$$

Equating the two expressions,

$$
E_i\mathcal L_\xi\phi^i+d\theta(\phi,\mathcal L_\xi\phi)=d(\iota_\xi L).
$$

Rearranging,

$$
d\left[\theta(\phi,\mathcal L_\xi\phi)-\iota_\xi L\right]
=-E_i\mathcal L_\xi\phi^i.
$$

On shell $E_i=0$, hence

$$
dJ_\xi=0.
$$

</details>

## References

- T. Frankel, *The Geometry of Physics*. Useful for exterior forms, variational principles, stress tensors, and geometric physics examples.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented reference for forms, bundles, gauge fields, path integrals, monopoles, and instantons.
- R. M. Wald, *General Relativity*. Standard reference for covariant variation, stress tensors, and gravitational boundary terms.
- J. Lee and R. M. Wald, “Local Symmetries and Constraints.” Classic reference for covariant phase space in diffeomorphism-invariant theories.
- V. Iyer and R. M. Wald, “Some Properties of Noether Charge and a Proposal for Dynamical Black Hole Entropy.” Standard source for Noether charge methods in gravity.
- P. Deligne et al., *Quantum Fields and Strings: A Course for Mathematicians*, Vol. 1. Useful for geometric and variational formulations of classical field theory.
- I. M. Anderson, *The Variational Bicomplex*. Mathematical reference for the systematic separation of spacetime and field-space differentials.
- P. J. Olver, *Applications of Lie Groups to Differential Equations*. Broad reference for variational symmetries and conservation laws.
- C. Crnkovic and E. Witten, “Covariant Description of Canonical Formalism in Geometrical Theories.” Early covariant phase-space reference.
- G. Barnich and F. Brandt, “Covariant Theory of Asymptotic Symmetries, Conservation Laws and Central Charges.” Useful for gauge symmetries, boundaries, and charges.

## Version history

- **2026-06-25:** Initial polished draft. Added Lagrangian-form setup, first variation formula, boundary terms and differentiability, scalar and Yang–Mills examples, stress tensor convention, diffeomorphism and internal Noether currents, covariant phase space, gravity boundary warning, higher-derivative comments, exercises, and figure.
