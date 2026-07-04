---
title: "Boundary Terms and Functional Differentiability"
description: "A QFT-oriented guide to boundary terms in variational principles, functional differentiability, boundary conditions, boundary counterterms, Hamiltonian generators, and surface charges."
sidebar:
  label: "Boundary Terms"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard calculus of variations, Hamiltonian field theory, covariant phase space, and gauge-theory references, including Regge–Teitelboim, Crnkowic–Witten, Lee–Wald, Iyer–Wald, Henneaux–Teitelboim, Coleman, Weinberg, and Wald."
topics:
  - boundary terms
  - functional differentiability
  - variational principles
  - boundary conditions
  - surface charges
  - covariant phase space
canonicalTopics:
  - boundary-terms
  - functional-differentiability
  - variational-calculus
  - hamiltonian-generators
researchStatus:
  established:
    - "A variational principle or Hamiltonian generator is well-defined only after the boundary terms in its first variation are controlled by boundary conditions, boundary functionals, boundary degrees of freedom, or surface charges."
  active:
    - "Boundary-sensitive phase spaces, edge modes, asymptotic symmetries, holographic counterterms, and covariant definitions of charges remain active in gauge theory, gravity, and QFT with defects or boundaries."
---

## Summary

When we vary a local action, integration by parts produces two things at once:

$$
\delta S
=
\int_M d^dx\,E_i(\mathcal L)\delta\phi^i
+
\int_{\partial M}d\Sigma_\mu\,\theta^\mu(\phi,\delta\phi).
$$

The first term gives the Euler–Lagrange equations. The second term tells us whether the variational problem actually makes sense. A boundary term is not a cosmetic leftover. It decides which boundary conditions are allowed, whether the functional derivative exists, which Hamiltonian generators are well-defined, and what charges live at the boundary.

A functional $F[\phi]$ is functionally differentiable on a chosen space of fields if its variation can be represented as a bulk pairing with all allowed variations:

$$
\delta F[\phi]
=
\int_M d\mu_x\,K_i(x)\delta\phi^i(x),
$$

with no uncontrolled boundary residue. If a boundary residue remains, one must do something about it: restrict the allowed variations, add a boundary functional, introduce boundary degrees of freedom, or reinterpret the boundary term as a surface charge.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram showing how variation of a local action produces a boundary obstruction, and how boundary conditions, boundary terms, boundary variables, or surface charges restore functional differentiability.](/figures/math-toolkit/boundary-functional-differentiability.svg)

<figcaption>

Functional differentiability is not automatic. The variation of a local action first exposes a boundary obstruction. A well-defined variational problem controls that obstruction by boundary conditions, boundary counterterms, boundary degrees of freedom, or Hamiltonian surface charges.

</figcaption>
</figure>

The central lesson is blunt:

$$
\text{the phrase }\frac{\delta S}{\delta\phi(x)}\text{ is incomplete until the boundary behavior is specified.}
$$

That is not pedantry. It is why the same bulk Lagrangian can describe different physical systems on a finite interval, why gauge transformations that vanish at infinity are redundancies while those that do not may carry charges, and why gravitational actions need boundary terms before Dirichlet metric data define a clean variational principle.

## Prerequisites

You should know [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/) and [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/). This page uses the same first-variation calculation but refuses to throw away the boundary term.

The pages [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) are useful background for understanding why functional derivatives are represented by kernels only after a pairing and a domain have been chosen. The [Mathematical Conventions](/math-toolkit/conventions/) page fixes the default metric, orientation, and distribution conventions used below.

## Core idea

In finite-dimensional calculus, a differentiable function $F(q)$ has a differential

$$
dF=\frac{\partial F}{\partial q^i}dq^i.
$$

There is no boundary because the variable $q^i$ is just a point in a finite-dimensional space. In field theory, the variable is a function on a region $M$. Derivatives in the Lagrangian force us to integrate by parts, and integration by parts sees the boundary of $M$.

For a first-derivative Lagrangian density,

$$
\mathcal L=\mathcal L(\phi^i,\partial_\mu\phi^i,x),
$$

we have

$$
\delta\mathcal L
=
\frac{\partial\mathcal L}{\partial\phi^i}\delta\phi^i
+
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\partial_\mu\delta\phi^i.
$$

Integrating by parts gives

$$
\delta\mathcal L
=
\left[
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
\right]\delta\phi^i
+
\partial_\mu\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\delta\phi^i
\right).
$$

Thus

$$
\delta S
=
\int_M d^dx\,E_i(\mathcal L)\delta\phi^i
+
\int_{\partial M}d\Sigma_\mu\,
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\delta\phi^i.
$$

The bulk coefficient $E_i(\mathcal L)$ is the Euler–Lagrange operator. The boundary term is the obstruction to treating $E_i(\mathcal L)$ as the complete functional derivative on a field space with unrestricted boundary variations.

There are two different questions here.

First, **stationarity** asks whether $\delta S=0$ at a classical solution for all allowed variations. This gives bulk equations plus boundary conditions.

Second, **functional differentiability** asks whether $\delta S$ defines a clean covector on the chosen field space. This is a property of the functional and the space of allowed variations, not only of solutions.

These questions are related but not identical. A boundary term may vanish on a special solution but still prevent $S$ from having a well-defined functional derivative on the whole chosen field space.

## Setup and conventions

Let $M$ be a $d$-dimensional region with boundary $\partial M$. The boundary hypersurface element is denoted

$$
d\Sigma_\mu=n_\mu d\Sigma,
$$

where $n_\mu$ is the outward normal covector and $d\Sigma$ is the induced boundary measure. In Lorentzian signature, signs depend on whether the boundary is spacelike or timelike; the compact notation $d\Sigma_\mu\theta^\mu$ keeps the orientation information in one place.

Fields are denoted $\phi^i(x)$. A field space $\mathcal C$ is not merely the set of all smooth functions. It usually includes boundary behavior:

$$
\mathcal C
=
\{\phi\text{ satisfying the chosen falloff, boundary, or regularity conditions}\}.
$$

An allowed variation $\delta\phi$ is a tangent vector to this space. For example, if $\phi$ obeys fixed Dirichlet data

$$
\phi|_{\partial M}=f,
$$

then the allowed variations obey

$$
\delta\phi|_{\partial M}=0.
$$

If the boundary value itself is allowed to vary because it is a source or a dynamical boundary field, then $\delta\phi|_{\partial M}$ is not zero, and the boundary term must be kept.

For a local Lagrangian, we write the first variation as

$$
\delta S
=
\int_M E_i\delta\phi^i+
\int_{\partial M}\theta.
$$

Here $\theta$ is the boundary contribution, often called the **symplectic potential current** in covariant phase-space language. It is linear in $\delta\phi$ and its derivatives.

A boundary term in the action changes $\theta$. If

$$
S\longmapsto S'=S+\int_{\partial M}B(\phi),
$$

then

$$
\delta S'
=
\int_M E_i\delta\phi^i+
\int_{\partial M}(\theta+\delta B).
$$

The bulk equations do not change, but the variational principle does. This is one reason total derivatives are physically quiet in the bulk but loud at boundaries.

## What functional differentiability means

A functional $F[\phi]$ is differentiable on $\mathcal C$ if for every allowed variation $\eta\in T_\phi\mathcal C$ there is a linear response

$$
D F[\phi](\eta)
=
\left.\frac{d}{d\epsilon}F[\phi+\epsilon\eta]\right|_{\epsilon=0}.
$$

It is **represented by a bulk functional derivative** if

$$
D F[\phi](\eta)
=
\int_M d\mu_x\,K_i(x)\eta^i(x)
$$

for all allowed variations. Then one writes

$$
K_i(x)=\frac{\delta F}{\delta\phi^i(x)}.
$$

If instead

$$
D F[\phi](\eta)
=
\int_M d\mu_x\,K_i(x)\eta^i(x)
+
\int_{\partial M}\beta(\phi,\eta),
$$

then $K_i$ alone is not the full derivative on the chosen field space. The boundary functional $\beta$ must either vanish on allowed variations or be included as part of the differential. Which choice is correct depends on the problem.

For a pure bulk field space, the standard demand is

$$
\int_{\partial M}\beta(\phi,\eta)=0
\qquad\text{for all allowed }\eta.
$$

For a field theory with genuine boundary degrees of freedom, the standard demand is enlarged:

$$
D F
=
\int_M K_i\delta\phi^i+
\int_{\partial M}K_a^{\partial}\delta\psi^a,
$$

where $\psi^a$ are boundary variables or boundary values regarded as independent coordinates. Then the boundary term is not an obstruction; it is part of the derivative.

This distinction is easy to miss because physicists often write

$$
\delta S=\int_M \frac{\delta S}{\delta\phi^i}\delta\phi^i
$$

after silently imposing boundary conditions. The equation is fine when the silence is justified. It is dangerous when it is not.

## Scalar field on a region

Consider a real scalar field with the mostly-minus convention and Lorentzian action

$$
S[\phi]
=
\int_M d^dx\,
\left(
\frac12\partial_\mu\phi\partial^\mu\phi
-V(\phi)
\right).
$$

Its variation is

$$
\delta S
=
\int_M d^dx\,
\left(\partial_\mu\phi\partial^\mu\delta\phi-V'(\phi)\delta\phi\right).
$$

Integrating by parts gives

$$
\delta S
=
-\int_M d^dx\,(\Box\phi+V'(\phi))\delta\phi
+
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

The bulk equation is

$$
\Box\phi+V'(\phi)=0.
$$

The boundary term is

$$
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

For fixed Dirichlet data,

$$
\delta\phi|_{\partial M}=0,
$$

so the boundary term vanishes. On that field space,

$$
\frac{\delta S}{\delta\phi(x)}=-(\Box\phi+V'(\phi)).
$$

For natural homogeneous Neumann data,

$$
n_\mu\partial^\mu\phi|_{\partial M}=0,
$$

one allows $\delta\phi$ at the boundary but restricts the boundary value of the normal derivative on the classical configurations. Then the boundary term vanishes on configurations satisfying the Neumann boundary condition.

A more flexible Robin condition comes from adding a boundary potential. Let

$$
S_{\partial}[\phi]
=-\int_{\partial M}d\Sigma\,U(\phi).
$$

Then

$$
\delta(S+S_{\partial})
=
-\int_M d^dx\,(\Box\phi+V'(\phi))\delta\phi
+
\int_{\partial M}d\Sigma\,
\left(n_\mu\partial^\mu\phi-U'(\phi)\right)\delta\phi.
$$

If boundary variations are unrestricted, stationarity gives

$$
n_\mu\partial^\mu\phi=U'(\phi)
\qquad\text{on }\partial M.
$$

Thus the boundary action is not an afterthought. It selects the boundary condition.

## Boundary conditions are part of the variational problem

The same bulk action can define different variational problems depending on what is held fixed at the boundary.

For a scalar field, common choices are:

| Boundary behavior | Allowed variation | Boundary equation or condition |
|---|---|---|
| Dirichlet | $\delta\phi\vert_{\partial M}=0$ | $\phi\vert_{\partial M}=f$ is fixed. |
| Neumann | $\delta\phi\vert_{\partial M}$ arbitrary | $n_\mu\partial^\mu\phi=0$, or a prescribed normal derivative after adding a boundary source. |
| Robin | $\delta\phi\vert_{\partial M}$ arbitrary | $n_\mu\partial^\mu\phi=U'(\phi)$. |
| Mixed | Some components fixed, others free | A combination determined by $\theta+\delta B$. |

A boundary condition is not merely a condition imposed after the equations of motion are found. It is part of what defines the variational derivative in the first place.

There is also a difference between **fixing a boundary value** and **solving a boundary equation**. Dirichlet conditions are imposed on the field space before variation. Neumann and Robin conditions often appear as equations required by stationarity when boundary variations are allowed.

In applications, both viewpoints occur. For example, in the path integral with fixed boundary values, the boundary data label an amplitude. In an effective theory on a material interface, boundary values may be dynamical or coupled to sources. In holographic setups, the distinction between fixed sources and expectation values becomes a central organizing principle.

## Adding a boundary functional

Suppose the raw variation has boundary term

$$
\int_{\partial M}\theta.
$$

If there exists a boundary functional $B$ such that

$$
\theta+\delta B
$$

vanishes under the desired boundary conditions, then

$$
S'=S+\int_{\partial M}B
$$

has a better variational principle for those boundary conditions.

This pattern is everywhere.

In mechanics, adding a total time derivative

$$
L\mapsto L+\frac{dF(q,t)}{dt}
$$

changes the endpoint term in the action variation:

$$
\delta S\mapsto \delta S+\delta F\big|_{t_i}^{t_f}.
$$

The equations of motion are unchanged, but the canonical momenta and Hamilton–Jacobi boundary data can shift.

In field theory, adding a total divergence

$$
\mathcal L\mapsto \mathcal L+\partial_\mu K^\mu
$$

leaves the Euler–Lagrange operator unchanged:

$$
E_i(\partial_\mu K^\mu)=0,
$$

but changes the boundary current by

$$
\theta^\mu\mapsto \theta^\mu+\delta K^\mu+\text{possible tangential divergence terms}.
$$

In gravity, the Einstein–Hilbert action contains second derivatives of the metric after integration by parts. Its variation with fixed boundary metric contains normal derivatives of $\delta g_{\mu\nu}$. The Gibbons–Hawking–York term cancels those derivative-of-variation terms and makes the Dirichlet metric variational principle well-posed.

The precise term is a gravity topic, not needed here. The mathematical pattern is the same: the bulk equations were never the whole variational problem.

## Higher-derivative actions

For a Lagrangian depending on second derivatives,

$$
\mathcal L=\mathcal L(\phi,\partial\phi,\partial^2\phi),
$$

the raw variation contains terms involving

$$
\partial_\mu\partial_\nu\delta\phi.
$$

After integrating by parts, the bulk term is

$$
E(\mathcal L)\delta\phi,
$$

but the boundary term may involve both

$$
\delta\phi|_{\partial M}
\qquad\text{and}\qquad
n^\mu\partial_\mu\delta\phi|_{\partial M}.
$$

For a Dirichlet variational problem, fixing $\phi$ at the boundary does not automatically fix the normal derivative of $\delta\phi$. Thus higher-derivative theories often need extra boundary data or extra boundary terms.

A simple one-dimensional example shows the issue. Let

$$
S[q]=\frac12\int_{t_i}^{t_f}dt\,\ddot q^2.
$$

Then

$$
\delta S
=
\int dt\,\ddot q\,\delta\ddot q.
$$

Integrating by parts twice gives

$$
\delta S
=
\int dt\,q^{(4)}\delta q
+
\left[\ddot q\,\delta\dot q-\dddot q\,\delta q\right]_{t_i}^{t_f}.
$$

Fixing only $q$ at the endpoints kills the second endpoint term but not the first. To make the variational problem well-defined, one must also fix $\dot q$, impose a boundary equation, or modify the action by an appropriate boundary functional if possible.

This is the finite-dimensional prototype of the boundary problems that appear in higher-derivative effective actions and gravity.

## Hamiltonian differentiability

Boundary terms become even more decisive in Hamiltonian field theory. A Hamiltonian functional $H[\phi,\pi]$ on a spatial region $\Sigma$ is functionally differentiable if

$$
\delta H
=
\int_\Sigma d^{d-1}x\,
\left(
\frac{\delta H}{\delta\phi}\delta\phi
+
\frac{\delta H}{\delta\pi}\delta\pi
\right)
$$

with no leftover boundary term.

For a scalar field on a spatial region, take

$$
H[\phi,\pi]
=
\int_\Sigma d^{d-1}x\,
\left[
\frac12\pi^2+\frac12\partial_i\phi\partial_i\phi+V(\phi)
\right].
$$

Varying gives

$$
\delta H
=
\int_\Sigma d^{d-1}x\,
\left[
\pi\delta\pi+
\partial_i\phi\partial_i\delta\phi+V'(\phi)\delta\phi
\right].
$$

Integrating by parts on $\Sigma$ gives

$$
\delta H
=
\int_\Sigma d^{d-1}x\,
\left[
\pi\delta\pi+
\left(-\partial_i\partial_i\phi+V'(\phi)\right)\delta\phi
\right]
+
\int_{\partial\Sigma}dS_i\,\partial_i\phi\,\delta\phi.
$$

Therefore the naive Hamiltonian is differentiable only if

$$
\int_{\partial\Sigma}dS_i\,\partial_i\phi\,\delta\phi=0
$$

for allowed variations, or if the Hamiltonian is improved by a boundary term.

This condition is not a decorative consistency check. Hamilton's equations are derived by pairing $\delta H$ with the symplectic structure. If $\delta H$ is not a well-defined covector on phase space, the corresponding Hamiltonian vector field is not well-defined.

## Surface charges and gauge generators

Gauge theory makes the previous point unavoidable. A gauge transformation whose parameter vanishes at the boundary is usually a redundancy. A gauge transformation whose parameter survives at the boundary may be a physical symmetry with a charge.

A schematic Abelian example is enough. Let $E^i$ be the electric field on a spatial region $\Sigma$, and consider the Gauss-law generator with parameter $\alpha$:

$$
G_{\rm bulk}[\alpha]
=
\int_\Sigma d^{d-1}x\,\alpha\,\partial_iE^i.
$$

Varying with respect to $E^i$ gives

$$
\delta G_{\rm bulk}[\alpha]
=
-\int_\Sigma d^{d-1}x\,(\partial_i\alpha)\delta E^i
+
\int_{\partial\Sigma}dS_i\,\alpha\delta E^i.
$$

If $\alpha|_{\partial\Sigma}=0$, the boundary term vanishes. If $\alpha$ approaches a nonzero value at the boundary, the bulk generator is not differentiable. One can improve it by subtracting a surface term,

$$
G[\alpha]
=
G_{\rm bulk}[\alpha]-\int_{\partial\Sigma}dS_i\,\alpha E^i,
$$

assuming $\alpha$ is fixed at the boundary. Then

$$
\delta G[\alpha]
=
-\int_\Sigma d^{d-1}x\,(\partial_i\alpha)\delta E^i.
$$

The surface term is the charge associated with the non-vanishing boundary parameter. This is the basic mechanism behind electric charge, asymptotic symmetry charges, angular momentum at infinity, and many boundary charges in gauge theory and gravity.

The slogan is:

$$
\text{small gauge transformations have no boundary charge; large or asymptotic ones can.}
$$

The adjective “large” has several meanings in the literature. Here the important point is simply whether the transformation acts nontrivially on boundary data.

## Boundary terms and symplectic structure

The boundary term in the variation of the action is also the seed of the symplectic structure. For a first-order mechanical action,

$$
S[q]=\int_{t_i}^{t_f}dt\,L(q,\dot q),
$$

variation gives

$$
\delta S
=
\int_{t_i}^{t_f}dt\,
\left(
\frac{\partial L}{\partial q^i}
-
\frac{d}{dt}\frac{\partial L}{\partial\dot q^i}
\right)\delta q^i
+
\left[p_i\delta q^i\right]_{t_i}^{t_f},
$$

where

$$
p_i=\frac{\partial L}{\partial\dot q^i}.
$$

The endpoint term

$$
\Theta=p_i\delta q^i
$$

is the canonical one-form on phase space. Its exterior derivative on phase space is

$$
\Omega=\delta q^i\wedge\delta p_i.
$$

In field theory, the boundary current $\theta$ plays the analogous role. Its field-space exterior derivative gives the symplectic current

$$
\omega=\delta\theta.
$$

Integrating $\omega$ over a Cauchy surface gives a symplectic form, up to the usual caveats about gauge degeneracies and boundary flux. This is why boundary terms cannot be postponed forever. They are the bridge from the variational principle to phase space.

## Total derivatives are bulk-invisible but boundary-visible

If two Lagrangians differ by a total derivative,

$$
\mathcal L' = \mathcal L+\partial_\mu K^\mu,
$$

then their Euler–Lagrange operators agree:

$$
E_i(\mathcal L')=E_i(\mathcal L).
$$

But their boundary currents differ. Schematically,

$$
\theta' = \theta+\delta K+\text{corner terms}.
$$

The phrase “corner terms” refers to contributions supported on boundaries of boundaries, such as initial and final corners of a spacetime region or intersections of boundary components. In many simple examples they vanish or are ignored. In precision work with finite regions, gravitational charges, entangling surfaces, defects, or null boundaries, they matter.

This is why “total derivatives do not matter” is a half-truth. A better statement is:

$$
\text{total derivatives do not change local bulk Euler–Lagrange equations.}
$$

They can change canonical momenta, boundary conditions, charges, symplectic potentials, and quantum phases.

## Euclidean path integrals and boundary data

In a Euclidean path integral, boundary conditions are part of the definition of the integration domain. For a scalar field on $M$ with boundary, the formal expression

$$
Z=
\int_{\mathcal C}\mathcal D\phi\,e^{-S_E[\phi]}
$$

is not defined until $\mathcal C$ says what happens at $\partial M$.

If one fixes Dirichlet boundary data,

$$
\phi|_{\partial M}=f,
$$

then $Z[f]$ is a functional of $f$. Varying $f$ probes the boundary canonical momentum. If instead one integrates over boundary values, adds a boundary action, or couples boundary values to sources, one defines a different theory.

This is the path-integral version of the same point: boundary terms are part of the object being computed, not just a detail in deriving the equations of motion.

## Common pitfalls

**Saying “drop the boundary term” without saying why.** Boundary terms vanish because of compact support, falloff, fixed boundary values, boundary equations, or added counterterms. They do not vanish by social convention.

**Confusing stationarity with differentiability.** A boundary term may vanish on a particular solution but still obstruct a functional derivative on the chosen field space.

**Treating Dirichlet, Neumann, and Robin as afterthoughts.** They define different variational problems. The same bulk equation with different boundary data is not the same physical problem.

**Forgetting derivative-of-variation terms in higher-derivative theories.** Fixing a field at the boundary does not automatically fix its normal derivative.

**Assuming all gauge transformations are pure redundancy.** Gauge transformations that vanish at the boundary are often redundancies. Transformations with nonzero boundary action can carry physical charges.

**Saying total derivatives never matter.** They do not change bulk Euler–Lagrange equations, but they can change boundary conditions, charges, canonical momenta, symplectic potentials, and quantum phases.

**Ignoring corners.** If the boundary has its own boundary, corner terms may be required for a clean variational principle or charge algebra.

## Relations to other pages

[Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/) explains what it means to represent a first variation by a functional derivative. [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/) explains how the bulk equations arise from integration by parts.

This page supplies the missing boundary logic needed before [Legendre Transforms](/math-toolkit/calculus-of-variations-and-phase-space/legendre-transforms/) and later phase-space pages. The boundary term in the action variation becomes the canonical one-form, the symplectic potential, and eventually the source of Poisson brackets, constraints, and charges.

The same ideas reappear in [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/), where gauge redundancy produces directions that should not be integrated over naively. They also reappear in functional determinants because the spectrum of a differential operator depends on its boundary conditions.

## Research status

The basic mathematics of boundary terms and functional differentiability is established. It is standard in calculus of variations, Hamiltonian mechanics, canonical field theory, gauge theory, and covariant phase-space methods.

The active part is not the elementary integration by parts. It is the correct handling of boundaries in complicated systems: gauge theories with edge modes, gravity with asymptotic or finite boundaries, null surfaces, corners, anomalies inflowing to defects, holographic renormalization, subregion factorization, and quantum theories where boundary conditions themselves form a dynamical sector.

For ordinary graduate-QFT calculations, the practical rule is still simple: before writing $\delta S/\delta\phi$, specify the allowed variations.

## Exercises

### Exercise 1: Scalar Dirichlet boundary data

Let

$$
S[\phi]
=
\int_M d^dx\,
\left(
\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
\right).
$$

Vary the action and show that it is functionally differentiable on the field space with fixed Dirichlet data $\delta\phi|_{\partial M}=0$.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S
=
\int_M d^dx\,
\left(\partial_\mu\phi\partial^\mu\delta\phi-m^2\phi\delta\phi\right).
$$

Integrating by parts,

$$
\delta S
=
-\int_M d^dx\,(\Box+m^2)\phi\,\delta\phi
+
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

For fixed Dirichlet data, $\delta\phi|_{\partial M}=0$, so the boundary term vanishes. Thus

$$
\delta S
=
\int_M d^dx\,
\frac{\delta S}{\delta\phi}\delta\phi
$$

with

$$
\frac{\delta S}{\delta\phi}=-(\Box+m^2)\phi.
$$

The action is functionally differentiable on this field space.

</details>

### Exercise 2: Boundary potential and Robin condition

For the same scalar field, add

$$
S_{\partial}[\phi]
=-\frac{\lambda}{2}\int_{\partial M}d\Sigma\,\phi^2.
$$

Assuming boundary variations are unrestricted, derive the boundary condition required by stationarity.

<details><summary><strong>Solution</strong></summary>

The bulk variation gives the boundary term

$$
\int_{\partial M}d\Sigma\,n_\mu\partial^\mu\phi\,\delta\phi.
$$

The boundary action varies as

$$
\delta S_{\partial}
=-\lambda\int_{\partial M}d\Sigma\,\phi\delta\phi.
$$

Thus the total boundary term is

$$
\int_{\partial M}d\Sigma\,
\left(n_\mu\partial^\mu\phi-\lambda\phi\right)\delta\phi.
$$

If $\delta\phi$ is arbitrary at the boundary, stationarity requires

$$
n_\mu\partial^\mu\phi=\lambda\phi
\qquad\text{on }\partial M.
$$

This is a Robin boundary condition.

</details>

### Exercise 3: Hamiltonian differentiability on an interval

Let

$$
H[\phi,\pi]
=
\int_0^L dx\,
\left(
\frac12\pi^2+\frac12(\partial_x\phi)^2+V(\phi)
\right).
$$

Compute $\delta H$ and identify boundary conditions that make $H$ functionally differentiable.

<details><summary><strong>Solution</strong></summary>

Varying gives

$$
\delta H
=
\int_0^L dx\,
\left[
\pi\delta\pi+\partial_x\phi\,\partial_x\delta\phi+V'(\phi)\delta\phi
\right].
$$

Integrating by parts,

$$
\delta H
=
\int_0^L dx\,
\left[
\pi\delta\pi+\left(-\partial_x^2\phi+V'(\phi)\right)\delta\phi
\right]
+
\left[\partial_x\phi\,\delta\phi\right]_{0}^{L}.
$$

Therefore $H$ is differentiable if the endpoint term vanishes for all allowed variations. This happens, for example, if

$$
\delta\phi(0)=\delta\phi(L)=0
$$

fixed endpoint Dirichlet data, or if

$$
\partial_x\phi(0)=\partial_x\phi(L)=0
$$

on the relevant field space with endpoint values allowed to vary. More general Robin conditions require adding endpoint terms to $H$.

</details>

### Exercise 4: Surface term in a Gauss-law generator

Let

$$
G_{\rm bulk}[\alpha]
=
\int_\Sigma d^{d-1}x\,\alpha\partial_iE^i.
$$

Assume $\alpha$ is fixed while $E^i$ varies. Show that $G_{\rm bulk}$ is differentiable if $\alpha|_{\partial\Sigma}=0$, and find an improved generator for nonzero fixed boundary $\alpha$.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta G_{\rm bulk}[\alpha]
=
\int_\Sigma d^{d-1}x\,\alpha\partial_i\delta E^i.
$$

Integrating by parts,

$$
\delta G_{\rm bulk}[\alpha]
=
-\int_\Sigma d^{d-1}x\,(\partial_i\alpha)\delta E^i
+
\int_{\partial\Sigma}dS_i\,\alpha\delta E^i.
$$

If $\alpha|_{\partial\Sigma}=0$, the boundary term vanishes. If $\alpha$ is nonzero but fixed at the boundary, define

$$
G[\alpha]
=
G_{\rm bulk}[\alpha]-\int_{\partial\Sigma}dS_i\,\alpha E^i.
$$

Then

$$
\delta G[\alpha]
=
-\int_\Sigma d^{d-1}x\,(\partial_i\alpha)\delta E^i,
$$

so the improved generator is differentiable. The subtracted surface term is the associated boundary charge in this convention.

</details>

## References

- I. M. Gelfand and S. V. Fomin, *Calculus of Variations*. A compact classic treatment of variational derivatives and boundary terms.
- P. J. Olver, *Applications of Lie Groups to Differential Equations*. Variational calculus, total derivatives, and Noether identities.
- R. Abraham and J. E. Marsden, *Foundations of Mechanics*. Geometric mechanics, cotangent bundles, canonical forms, and Hamiltonian differentiability.
- T. Regge and C. Teitelboim, “Role of Surface Integrals in the Hamiltonian Formulation of General Relativity.” The classic source for differentiability of Hamiltonian generators and surface charges.
- C. Crnkowic and E. Witten, “Covariant Description of Canonical Formalism in Geometrical Theories.” Covariant phase-space origin of symplectic structures.
- J. Lee and R. M. Wald, “Local Symmetries and Constraints.” Covariant phase space, boundary terms, and gauge degeneracies.
- V. Iyer and R. M. Wald, “Some Properties of Noether Charge and a Proposal for Dynamical Black Hole Entropy.” Noether charges and boundary terms in generally covariant theories.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Constraints, gauge generators, and boundary-sensitive Hamiltonian methods.
- R. M. Wald, *General Relativity*. Variational principles, boundary terms, symplectic currents, and conserved charges in gravity.
- S. Coleman, *Aspects of Symmetry*. Functional methods, gauge fixing, solitons, instantons, and the practical role of boundary behavior in field theory.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit, with scalar, Hamiltonian, gauge-generator, and symplectic-potential examples.
