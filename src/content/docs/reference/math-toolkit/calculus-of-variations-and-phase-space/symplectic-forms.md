---
title: "Symplectic Forms"
description: "A QFT-oriented guide to symplectic and presymplectic forms, canonical phase space, Hamiltonian vector fields, field-theory symplectic structures, gauge degeneracy, and boundary charges."
sidebar:
  label: "Symplectic Forms"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard geometric mechanics, Hamiltonian field theory, covariant phase-space, and gauge-theory references, including Arnold, Abraham–Marsden, Frankel, Nakahara, Goldstein, Dirac, Henneaux–Teitelboim, Crnković–Witten, Lee–Wald, Iyer–Wald, Srednicki, Weinberg, Schwartz, and Wald."
topics:
  - symplectic forms
  - phase space
  - Hamiltonian vector fields
  - presymplectic forms
  - covariant phase space
  - gauge degeneracy
canonicalTopics:
  - symplectic-form
  - phase-space
  - hamiltonian-mechanics
  - covariant-phase-space
researchStatus:
  established:
    - "Symplectic geometry is the coordinate-free language of Hamiltonian mechanics; in field theory the canonical symplectic form is standard once boundary conditions and functional differentiability are fixed."
  active:
    - "Boundary-sensitive symplectic structures, edge modes, covariant phase-space charges, degenerate presymplectic forms, and phase spaces in gauge theory and gravity remain active research areas."
---

## Summary

A **symplectic form** is the geometric object that turns phase space into Hamiltonian mechanics. It is a closed, nondegenerate antisymmetric two-form. In canonical coordinates $(q^i,p_i)$ we use the convention

$$
\Omega=\delta q^i\wedge\delta p_i,
$$

where $\delta$ is the exterior derivative on phase space, not a spacetime derivative. Given a Hamiltonian $H$, the Hamiltonian vector field $X_H$ is defined by

$$
\iota_{X_H}\Omega=\delta H.
$$

This one equation is Hamilton's equations in coordinate-free form.

For fields on a spatial slice $\Sigma$, the canonical symplectic form is

$$
\Omega_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,
\delta\phi^a(\mathbf x)\wedge\delta\pi_a(\mathbf x).
$$

This formula is the infinite-dimensional version of $\delta q^i\wedge\delta p_i$. It is also the structure whose inverse gives the canonical Poisson brackets.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram from the symplectic potential to the symplectic form, Hamiltonian vector fields, canonical mechanics, canonical fields, covariant phase space, and presymplectic degeneracies.](/figures/math-toolkit/symplectic-form-geometry.svg)

<figcaption>

The symplectic form is the antisymmetric pairing on phase-space variations. Its potential is visible as a boundary term in the first variation of the action. If the form is nondegenerate, it produces Hamiltonian vector fields and Poisson brackets; if it has a kernel, the system is presymplectic until gauge or boundary data are handled.

</figcaption>
</figure>

The most important distinction is this:

$$
\text{Lagrangian mechanics lives on configurations and velocities; Hamiltonian mechanics lives on phase space with }\Omega.
$$

The Legendre transform gives candidate phase-space variables. The symplectic form tells us which functions generate which motions, which quantities are conjugate, and which directions are actually gauge.

## Prerequisites

You should know [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/), [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/), [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/), and [Legendre Transforms](/math-toolkit/calculus-of-variations-and-phase-space/legendre-transforms/). The [Mathematical Conventions](/math-toolkit/conventions/) page fixes the metric, orientation, and variational notation used here.

The pages [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) are useful for the field-theory formulas, because the inverse of a field-theory symplectic form contains delta functions.

## Core idea

A symplectic form is an antisymmetric way of pairing two infinitesimal variations of a phase-space point. If $\mathcal P$ is phase space and $X,Y\in T_z\mathcal P$ are tangent vectors at a point $z\in\mathcal P$, then

$$
\Omega_z(X,Y)=-\Omega_z(Y,X).
$$

The form is **closed** if

$$
\delta\Omega=0.
$$

The form is **nondegenerate** if

$$
\iota_X\Omega=0
\quad\Longrightarrow\quad
X=0.
$$

Nondegeneracy says that $\Omega$ can identify tangent vectors with covectors. In coordinates, it is an invertible antisymmetric matrix. This is why it can turn a differential $\delta H$ into a vector field $X_H$.

A Hamiltonian is not merely an energy function. It is a function whose first variation is converted by $\Omega$ into time evolution:

$$
\iota_{X_H}\Omega=\delta H.
$$

Once $X_H$ is known, every observable $F$ evolves by the directional derivative

$$
\dot F=X_H(F).
$$

The Poisson bracket page will rewrite this as $\dot F=\{F,H\}$.

## Setup and conventions

We use $\delta$ for the exterior derivative on phase space or field space. Thus $\delta q^i$ and $\delta p_i$ are one-forms on phase space. They are not time derivatives and not small numbers by themselves. They eat tangent vectors.

For a tangent vector

$$
X=X^i_q\frac{\partial}{\partial q^i}+X_{p_i}\frac{\partial}{\partial p_i},
$$

we have

$$
\delta q^i(X)=X^i_q,
\qquad
\delta p_i(X)=X_{p_i}.
$$

The wedge product is antisymmetric:

$$
\delta q^i\wedge\delta p_i(X,Y)
=
\delta q^i(X)\delta p_i(Y)
-
\delta q^i(Y)\delta p_i(X).
$$

Our canonical convention is

$$
\Omega=\delta q^i\wedge\delta p_i
$$

together with

$$
\iota_{X_H}\Omega=\delta H.
$$

With these choices, Hamilton's equations are

$$
\dot q^i=\frac{\partial H}{\partial p_i},
\qquad
\dot p_i=-\frac{\partial H}{\partial q^i}.
$$

The canonical one-form, also called the symplectic potential, is

$$
\Theta=p_i\delta q^i.
$$

Then

$$
\delta\Theta=\delta p_i\wedge\delta q^i=-\delta q^i\wedge\delta p_i,
$$

so in this convention

$$
\Omega=-\delta\Theta.
$$

Many geometry and covariant phase-space references use the opposite sign convention, or define the symplectic current as $\delta\theta$ rather than $-\delta\theta$. Nothing physical changes, but the sign in $\iota_X\Omega=\pm\delta H$ and in the Poisson bracket changes with it. Check this once at the start of a calculation; otherwise a single sign error can propagate through every Hamiltonian and bracket formula.

## The finite-dimensional canonical form

Let

$$
\mathcal P=T^*Q
$$

be the cotangent bundle of a configuration space $Q$. A point of $\mathcal P$ is written $(q^i,p_i)$. The canonical one-form is

$$
\Theta=p_i\delta q^i.
$$

It has a simple interpretation. If a tangent vector $X$ represents an infinitesimal displacement in phase space, then $\Theta(X)$ extracts the momentum contracted with the induced displacement in configuration space:

$$
\Theta(X)=p_iX^i_q.
$$

The canonical symplectic form is

$$
\Omega=\delta q^i\wedge\delta p_i.
$$

For two tangent vectors

$$
X=(X_q^i,X_{p_i}),
\qquad
Y=(Y_q^i,Y_{p_i}),
$$

this gives

$$
\Omega(X,Y)
=
X_q^iY_{p_i}-Y_q^iX_{p_i}.
$$

This formula is the cleanest way to remember what $\Omega$ does: it pairs the configuration variation of one vector with the momentum variation of the other, then antisymmetrizes.

Because

$$
\delta\Omega=0,
$$

and because the canonical matrix

$$
\Omega_{AB}
=
\begin{pmatrix}
0 & I\\
-I & 0
\end{pmatrix}
$$

is invertible, $\Omega$ is symplectic.

## Hamiltonian vector fields

Let

$$
H=H(q,p)
$$

be a function on phase space. Write the vector field generated by $H$ as

$$
X_H=A^i\frac{\partial}{\partial q^i}+B_i\frac{\partial}{\partial p_i}.
$$

Contracting with the canonical form gives

$$
\iota_{X_H}\Omega
=
A^i\delta p_i-B_i\delta q^i.
$$

The differential of $H$ is

$$
\delta H
=
\frac{\partial H}{\partial q^i}\delta q^i
+
\frac{\partial H}{\partial p_i}\delta p_i.
$$

The equation $\iota_{X_H}\Omega=\delta H$ therefore implies

$$
A^i=\frac{\partial H}{\partial p_i},
\qquad
B_i=-\frac{\partial H}{\partial q^i}.
$$

Thus

$$
X_H
=
\frac{\partial H}{\partial p_i}\frac{\partial}{\partial q^i}
-
\frac{\partial H}{\partial q^i}\frac{\partial}{\partial p_i}.
$$

The integral curves of this vector field satisfy

$$
\dot q^i=\frac{\partial H}{\partial p_i},
\qquad
\dot p_i=-\frac{\partial H}{\partial q^i}.
$$

So Hamilton's equations are not extra equations attached to symplectic geometry. They are the coordinate expression of $\iota_{X_H}\Omega=\delta H$.

## From the action to the symplectic form

The symplectic potential appears already in the variation of the action. For a mechanical action

$$
S[q]=\int_{t_1}^{t_2}dt\,L(q,\dot q,t),
$$

one finds

$$
\delta S
=
\int_{t_1}^{t_2}dt\,
\left(
\frac{\partial L}{\partial q^i}
-
\frac{d}{dt}\frac{\partial L}{\partial\dot q^i}
\right)\delta q^i
+
\left[p_i\delta q^i\right]_{t_1}^{t_2},
$$

where

$$
p_i=\frac{\partial L}{\partial\dot q^i}.
$$

The endpoint term is precisely the symplectic potential:

$$
\Theta=p_i\delta q^i.
$$

Taking one more exterior derivative gives the symplectic form, up to the sign convention fixed above:

$$
\Omega=-\delta\Theta=\delta q^i\wedge\delta p_i.
$$

This is a useful lesson: the symplectic structure is not a decorative add-on to Hamiltonian mechanics. It is already hiding in the boundary term of the Lagrangian variation.

For field theory, the same statement becomes

$$
\delta S
=
\int_M d^dx\,E_a(\mathcal L)\delta\phi^a
+
\int_{\partial M}\theta.
$$

The boundary contribution $\theta$ is the local symplectic potential current. On a Cauchy slice $\Sigma$, it gives

$$
\Theta_\Sigma=\int_\Sigma\theta.
$$

Then the symplectic form on the space of fields is obtained by taking another variation, with the sign convention chosen to match the canonical Hamilton equations.

## Canonical field-theory symplectic form

For fields $\phi^a(t,\mathbf x)$ with canonical momenta $\pi_a(t,\mathbf x)$, the phase space at fixed time consists of pairs

$$
(\phi^a(\mathbf x),\pi_a(\mathbf x)).
$$

The canonical symplectic potential is

$$
\Theta_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,\pi_a(\mathbf x)\delta\phi^a(\mathbf x).
$$

With our sign convention,

$$
\Omega_\Sigma
=
-\delta\Theta_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,
\delta\phi^a(\mathbf x)\wedge\delta\pi_a(\mathbf x).
$$

Given two variations

$$
X=(X_\phi^a,X_{\pi_a}),
\qquad
Y=(Y_\phi^a,Y_{\pi_a}),
$$

we have

$$
\Omega_\Sigma(X,Y)
=
\int_\Sigma d^{d-1}\mathbf x\,
\left(
X_\phi^aY_{\pi_a}-Y_\phi^aX_{\pi_a}
\right).
$$

This is the continuum analogue of

$$
X_q^iY_{p_i}-Y_q^iX_{p_i}.
$$

The inverse of $\Omega_\Sigma$ contains the spatial delta function and leads to the canonical brackets

$$
\{\phi^a(t,\mathbf x),\pi_b(t,\mathbf y)\}
=
\delta^a_b\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

which are developed on the next page.

## Example: real scalar field

Consider a real scalar field with Lagrangian density

$$
\mathcal L
=
\frac12\dot\phi^2
-
\frac12\nabla\phi\cdot\nabla\phi
-V(\phi).
$$

The canonical momentum is

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi.
$$

The Hamiltonian is

$$
H[\phi,\pi]
=
\int d^{d-1}\mathbf x\,
\left[
\frac12\pi^2
+
\frac12\nabla\phi\cdot\nabla\phi
+V(\phi)
\right],
$$

assuming boundary conditions that remove spatial surface terms in $\delta H$.

Let the Hamiltonian vector field be

$$
X_H
=
\int d^{d-1}\mathbf x\,
\left(
A(\mathbf x)\frac{\delta}{\delta\phi(\mathbf x)}
+B(\mathbf x)\frac{\delta}{\delta\pi(\mathbf x)}
\right).
$$

The contraction with the symplectic form is

$$
\iota_{X_H}\Omega_\Sigma
=
\int d^{d-1}\mathbf x\,
\left[
A(\mathbf x)\delta\pi(\mathbf x)
-
B(\mathbf x)\delta\phi(\mathbf x)
\right].
$$

The variation of the Hamiltonian is

$$
\delta H
=
\int d^{d-1}\mathbf x\,
\left[
\pi\delta\pi+
\left(-\nabla^2\phi+V'(\phi)\right)\delta\phi
\right],
$$

again after controlling the spatial boundary term. Therefore $\iota_{X_H}\Omega_\Sigma=\delta H$ gives

$$
A=\pi,
\qquad
B=\nabla^2\phi-V'(\phi).
$$

Thus

$$
\dot\phi=\pi,
\qquad
\dot\pi=\nabla^2\phi-V'(\phi).
$$

Combining them gives

$$
\ddot\phi-\nabla^2\phi+V'(\phi)=0,
$$

which is the Euler–Lagrange equation.

## Covariant phase-space viewpoint

The canonical construction depends on choosing a time slicing. The covariant phase-space construction starts instead from the Lagrangian variation

$$
\delta\mathcal L=E_a(\mathcal L)\delta\phi^a+\partial_\mu\theta^\mu(\phi;\delta\phi).
$$

Here $\theta^\mu$ is the symplectic potential current. With the sign convention of this chapter, define the symplectic current by

$$
\omega=-\delta\theta.
$$

Evaluated on two commuting variations $\delta_1\phi$ and $\delta_2\phi$, this means

$$
\omega^\mu(\phi;\delta_1\phi,\delta_2\phi)
=
-\delta_1\theta^\mu(\phi;\delta_2\phi)
+
\delta_2\theta^\mu(\phi;\delta_1\phi).
$$

If the variations do not commute as vector fields on field space, the usual extra term involving $\theta^\mu(\phi;[\delta_1,\delta_2]\phi)$ must be included. For the linearized variations used here, the variations commute.

For variations that solve the linearized equations of motion around a classical solution, this current is conserved on shell:

$$
\partial_\mu\omega^\mu=0.
$$

Then

$$
\Omega_\Sigma(\delta_1\phi,\delta_2\phi)
=
\int_\Sigma d\Sigma_\mu\,\omega^\mu
$$

is independent of continuous deformations of the Cauchy slice $\Sigma$, provided there is no flux through boundaries. This is the covariant version of phase-space symplectic conservation.

Sign conventions vary here. In this page, the canonical Hamiltonian sign is fixed by

$$
\Omega_\Sigma=\int_\Sigma\delta\phi^a\wedge\delta\pi_a,
\qquad
\iota_{X_H}\Omega_\Sigma=\delta H.
$$

A covariant reference may define $\omega=\delta\theta$ instead. That convention differs by an overall sign from this canonical choice unless the Hamiltonian-vector-field or Poisson-bracket convention is also changed.

## Presymplectic forms and gauge directions

A **presymplectic form** is closed but possibly degenerate. Gauge theories naturally produce presymplectic forms before reduction. This is not an error. Gauge transformations are directions in field space that do not change the physical state.

Let $X$ be a vector field on phase space. If

$$
\iota_X\Omega=0,
$$

then $X$ is invisible to the symplectic pairing. If $\Omega$ is symplectic, this forces $X=0$. If $\Omega$ is presymplectic, nonzero such $X$ may exist. These are the degenerate directions.

Gauge theory supplies the standard example. For an Abelian gauge field on a spatial slice, the canonical symplectic form has the schematic form

$$
\Omega_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,
\delta A_i\wedge\delta E^i.
$$

An infinitesimal gauge transformation is

$$
\delta_\alpha A_i=\partial_i\alpha,
\qquad
\delta_\alpha E^i=0.
$$

Contracting this direction into $\Omega_\Sigma$ gives

$$
\iota_{\delta_\alpha}\Omega_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,\partial_i\alpha\,\delta E^i.
$$

Integrating by parts,

$$
\iota_{\delta_\alpha}\Omega_\Sigma
=
-\int_\Sigma d^{d-1}\mathbf x\,\alpha\,\partial_i\delta E^i
+
\int_{\partial\Sigma}dS_i\,\alpha\,\delta E^i.
$$

On the Gauss-law constraint surface, and for gauge parameters that vanish at the boundary, this contraction is zero. The gauge transformation is then a degenerate direction of the presymplectic form.

If $\alpha$ does not vanish at the boundary, the surface term remains:

$$
\delta Q_\alpha
=
\int_{\partial\Sigma}dS_i\,\alpha\,\delta E^i.
$$

Then the transformation is no longer pure gauge in the same sense; it can carry a boundary charge. This is the seed of a huge amount of physics: electric charge, asymptotic symmetries, edge modes, soft charges, and gravitational surface charges.

## Reduction and gauge fixing

There are two broad ways to turn a presymplectic gauge system into a genuine physical phase space.

The first is **symplectic reduction**. One restricts to the constraint surface and then quotients by degenerate gauge directions:

$$
\mathcal P_{\text{phys}}
=
\frac{\{\text{constraints}=0\}}{\text{gauge orbits}}.
$$

If the quotient is well-behaved, the presymplectic form descends to a nondegenerate symplectic form on $\mathcal P_{\text{phys}}$.

The second is **gauge fixing**. One imposes conditions that intersect gauge orbits once, at least locally. The restricted form can become nondegenerate on the gauge-fixed slice. This is often convenient for calculations but can obscure global questions.

Both procedures have caveats. Gauge orbits may not be globally simple. Boundary conditions may turn would-be gauge transformations into physical symmetries. Constraints may be first-class or second-class. Gauge-fixing conditions can fail globally. In non-Abelian gauge theory, Gribov-type issues can appear. The symplectic form tells you where the problem lives; it does not magically make the quotient polite.

## Symplectic conservation

For Hamiltonian evolution, the symplectic form is preserved. The geometric statement is

$$
\mathcal L_{X_H}\Omega=0,
$$

where $\mathcal L_{X_H}$ is the Lie derivative along the Hamiltonian vector field. Using Cartan's identity,

$$
\mathcal L_{X_H}\Omega
=
\delta(\iota_{X_H}\Omega)+\iota_{X_H}\delta\Omega.
$$

Since

$$
\iota_{X_H}\Omega=\delta H,
\qquad
\delta\Omega=0,
$$

we get

$$
\mathcal L_{X_H}\Omega
=
\delta^2H=0.
$$

So Hamiltonian flow preserves the symplectic form. This is the geometric core of Liouville's theorem and of the fact that canonical transformations preserve Poisson brackets.

## Canonical transformations

A diffeomorphism $\Phi:\mathcal P\to\mathcal P$ is canonical if it preserves the symplectic form:

$$
\Phi^*\Omega=\Omega.
$$

Infinitesimally, a vector field $X$ generates canonical transformations if

$$
\mathcal L_X\Omega=0.
$$

If there exists a function $F$ such that

$$
\iota_X\Omega=\delta F,
$$

then $X$ is Hamiltonian and $F$ is its generator. Locally, on simple phase spaces, many canonical vector fields are Hamiltonian. Globally, topology can obstruct writing a symplectic vector field as the Hamiltonian vector field of a globally defined function.

In physics language, a conserved charge generates a canonical transformation. The symplectic form is what converts the charge into the transformation of fields.

## Why symplectic forms matter in QFT

The symplectic form is the bridge between four things that are often taught separately.

First, it connects Lagrangian boundary terms to Hamiltonian phase space. The term $p_i\delta q^i$ in the endpoint variation is the seed of $\Omega$.

Second, it explains canonical brackets. The Poisson bracket is the inverse of the symplectic form.

Third, it diagnoses gauge redundancy. A nontrivial kernel of $\Omega$ is not a nuisance to hide; it is a signal of constraints, gauge orbits, or boundary charges.

Fourth, it survives beyond canonical coordinates. Covariant phase space, Chern–Simons theory, gravity, sigma models, Wess–Zumino terms, and systems with boundaries all use the same idea even when no simple global coordinates $(q,p)$ exist.

This is why symplectic geometry is not optional decoration for QFT. It is the grammar behind canonical quantization, commutation relations, charges, constraints, and many modern boundary constructions.

## Common pitfalls

**Confusing variations with time derivatives.** The symbol $\delta q$ in $\Omega=\delta q\wedge\delta p$ is a one-form on phase space. It is not $\dot q$ and not an infinitesimal time step.

**Forgetting the sign convention.** Some references use $\Omega=\delta p_i\wedge\delta q^i$ and $\iota_{X_H}\Omega=-\delta H$. This page uses $\Omega=\delta q^i\wedge\delta p_i$ and $\iota_{X_H}\Omega=\delta H$.

**Thinking the Legendre transform is the symplectic form.** The Legendre transform gives phase-space variables. The symplectic form is the extra structure that makes them Hamiltonian variables.

**Treating closed as equivalent to nondegenerate.** Closed means $\delta\Omega=0$. Nondegenerate means $\iota_X\Omega=0$ implies $X=0$. Gauge systems are often closed but degenerate.

**Ignoring boundary terms.** Boundary terms can change the symplectic potential and can turn gauge transformations into charge-carrying transformations.

**Assuming canonical coordinates exist globally.** Darboux's theorem gives local canonical coordinates on a finite-dimensional symplectic manifold. Global topology, constraints, singularities, and field-theory boundary conditions can prevent a single global canonical chart.

**Using the field-theory form without a domain.** The expression $\int\delta\phi\wedge\delta\pi$ is meaningful only after choosing falloff conditions, boundary conditions, and a class of allowed variations.

## Relations to other pages

[Legendre Transforms](/math-toolkit/calculus-of-variations-and-phase-space/legendre-transforms/) explains how canonical momenta arise from velocities. [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) explains why the symplectic potential depends on boundary behavior.

This page prepares [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/), where the inverse of $\Omega$ becomes the bracket $\{F,G\}$. It also prepares the later constraints page: when $\Omega$ is degenerate, Hamiltonian mechanics must be reduced, gauge-fixed, or replaced by a constrained formalism.

For field-theory distributional details, see [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/). For path-integral determinants associated with fluctuations around classical solutions, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/).

## Research status

Finite-dimensional symplectic geometry and canonical Hamiltonian mechanics are settled mathematical subjects. Their application to classical field theory is also standard in regulated or sufficiently controlled settings.

The active frontier lies in boundary-sensitive and gauge-sensitive phase spaces: edge modes, asymptotic symmetries, gravitational charges, subregion factorization, covariant phase space with corners, and singular or infinite-dimensional reductions. The basic equations on this page remain the starting point, but deciding the correct field space and boundary data can be the hard part.

In quantum field theory, canonical commutators are the quantized version of Poisson brackets, but turning these formal structures into operators requires domains, regularization, renormalization, and gauge constraints. The symplectic form is the classical skeleton; quantization adds operator domains, regularization, constraints, and possible anomalies.

## Exercises

### Exercise 1: Hamilton's equations from the canonical form

Let

$$
\Omega=\delta q\wedge\delta p,
\qquad
H=\frac{p^2}{2m}+V(q).
$$

Use $\iota_{X_H}\Omega=\delta H$ to derive Hamilton's equations.

<details><summary><strong>Solution</strong></summary>

Write

$$
X_H=A\frac{\partial}{\partial q}+B\frac{\partial}{\partial p}.
$$

Then

$$
\iota_{X_H}\Omega=A\delta p-B\delta q.
$$

Also

$$
\delta H=V'(q)\delta q+\frac{p}{m}\delta p.
$$

Equating coefficients gives

$$
A=\frac{p}{m},
\qquad
-B=V'(q),
$$

so

$$
\dot q=\frac{p}{m},
\qquad
\dot p=-V'(q).
$$

</details>

### Exercise 2: Check that the canonical form is closed

Show that

$$
\Omega=\delta q^i\wedge\delta p_i
$$

satisfies $\delta\Omega=0$.

<details><summary><strong>Solution</strong></summary>

Using the exterior derivative on phase space,

$$
\delta\Omega
=
\delta(\delta q^i\wedge\delta p_i).
$$

The exterior derivative squares to zero:

$$
\delta^2q^i=0,
\qquad
\delta^2p_i=0.
$$

Therefore

$$
\delta\Omega=0.
$$

The result is independent of the number of canonical pairs.

</details>

### Exercise 3: Scalar field equations from the symplectic form

For

$$
H=\int d^{d-1}\mathbf x\,
\left[
\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+\frac12m^2\phi^2
\right]
$$

and

$$
\Omega_\Sigma=\int d^{d-1}\mathbf x\,\delta\phi\wedge\delta\pi,
$$

derive the Hamiltonian equations, assuming boundary terms vanish.

<details><summary><strong>Solution</strong></summary>

The variation of the Hamiltonian is

$$
\delta H
=
\int d^{d-1}\mathbf x\,
\left[
\pi\delta\pi+
\left(-\nabla^2\phi+m^2\phi\right)\delta\phi
\right].
$$

Write

$$
X_H=\int d^{d-1}\mathbf x\,
\left[
A(\mathbf x)\frac{\delta}{\delta\phi(\mathbf x)}
+B(\mathbf x)\frac{\delta}{\delta\pi(\mathbf x)}
\right].
$$

Then

$$
\iota_{X_H}\Omega_\Sigma
=
\int d^{d-1}\mathbf x\,
\left[A\delta\pi-B\delta\phi\right].
$$

Equating this to $\delta H$ gives

$$
A=\pi,
\qquad
-B=-\nabla^2\phi+m^2\phi.
$$

Thus

$$
\dot\phi=\pi,
\qquad
\dot\pi=\nabla^2\phi-m^2\phi.
$$

Combining the two equations gives

$$
\ddot\phi-\nabla^2\phi+m^2\phi=0.
$$

</details>

### Exercise 4: Gauge degeneracy in electrodynamics

For

$$
\Omega_\Sigma=\int_\Sigma d^{d-1}\mathbf x\,\delta A_i\wedge\delta E^i,
$$

consider the gauge variation

$$
\delta_\alpha A_i=\partial_i\alpha,
\qquad
\delta_\alpha E^i=0.
$$

Show that $\iota_{\delta_\alpha}\Omega_\Sigma$ is a bulk Gauss-law term plus a boundary term.

<details><summary><strong>Solution</strong></summary>

Contracting into the symplectic form gives

$$
\iota_{\delta_\alpha}\Omega_\Sigma
=
\int_\Sigma d^{d-1}\mathbf x\,\partial_i\alpha\,\delta E^i.
$$

Integrating by parts,

$$
\int_\Sigma \partial_i\alpha\,\delta E^i
=
-\int_\Sigma \alpha\,\partial_i\delta E^i
+
\int_{\partial\Sigma}dS_i\,\alpha\,\delta E^i.
$$

Thus

$$
\iota_{\delta_\alpha}\Omega_\Sigma
=
-\int_\Sigma d^{d-1}\mathbf x\,\alpha\,\partial_i\delta E^i
+
\int_{\partial\Sigma}dS_i\,\alpha\,\delta E^i.
$$

On the Gauss-law constraint surface and for $\alpha|_{\partial\Sigma}=0$, this contraction vanishes. If $\alpha$ is nonzero at the boundary, the boundary term is the variation of a surface charge.

</details>

### Exercise 5: Symplectic conservation

Assume $\Omega$ is closed and $X_H$ satisfies $\iota_{X_H}\Omega=\delta H$. Show that the Hamiltonian flow preserves $\Omega$.

<details><summary><strong>Solution</strong></summary>

Use Cartan's identity:

$$
\mathcal L_{X_H}\Omega
=
\delta(\iota_{X_H}\Omega)+\iota_{X_H}\delta\Omega.
$$

Since $\iota_{X_H}\Omega=\delta H$ and $\delta\Omega=0$,

$$
\mathcal L_{X_H}\Omega
=
\delta(\delta H)+0
=\delta^2H=0.
$$

Therefore Hamiltonian flow preserves the symplectic form.

</details>

## References

- V. I. Arnold, *Mathematical Methods of Classical Mechanics*. Standard geometric mechanics and symplectic geometry.
- R. Abraham and J. E. Marsden, *Foundations of Mechanics*. Cotangent bundles, symplectic forms, momentum maps, reduction, and Hamiltonian systems.
- T. Frankel, *The Geometry of Physics*. Differential forms, cotangent bundles, phase space, Hamiltonian mechanics, and geometric physics.
- M. Nakahara, *Geometry, Topology and Physics*. Differential forms, bundles, gauge fields, and topological structures used in field theory.
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*. Canonical mechanics and transformations.
- P. A. M. Dirac, *Lectures on Quantum Mechanics*. Constraints and Hamiltonian structure in singular systems.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Presymplectic constraints, gauge fixing, and constrained Hamiltonian systems.
- C. Crnković and E. Witten, "Covariant description of canonical formalism in geometrical theories." Early covariant phase-space formulation.
- J. Lee and R. M. Wald, "Local symmetries and constraints." Covariant phase space, symplectic current, and constraints.
- V. Iyer and R. M. Wald, "Some properties of Noether charge and a proposal for dynamical black hole entropy." Covariant phase-space charges in gravity.
- R. M. Wald, *General Relativity*. Hamiltonian and covariant methods in gravity.
- M. Srednicki, *Quantum Field Theory*. Canonical field variables and quantization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. Canonical formalism, fields, symmetries, and quantization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Classical field theory, canonical Hamiltonians, and path-integral connections.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit, covering canonical symplectic forms, Hamiltonian vector fields, scalar-field phase space, covariant phase space, gauge degeneracy, and boundary charges.
