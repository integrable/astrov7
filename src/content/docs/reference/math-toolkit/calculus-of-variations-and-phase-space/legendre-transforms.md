---
title: "Legendre Transforms"
description: "A QFT-oriented guide to Legendre transforms from Lagrangian to Hamiltonian variables, including convex duality, canonical momenta, field-theory Hamiltonian densities, singular Lagrangians, constraints, and the effective action."
sidebar:
  label: "Legendre Transforms"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard mechanics, convex analysis, Hamiltonian field theory, constrained systems, and QFT effective-action references, including Arnold, Abraham–Marsden, Dirac, Henneaux–Teitelboim, Coleman, Weinberg, Zinn-Justin, Srednicki, Schwartz, and Burgess."
topics:
  - Legendre transforms
  - Hamiltonian mechanics
  - canonical momenta
  - Hamiltonian field theory
  - constrained systems
  - effective action
canonicalTopics:
  - legendre-transform
  - hamiltonian-formalism
  - phase-space
  - effective-action
researchStatus:
  established:
    - "Regular Legendre transforms between velocities and momenta are standard in mechanics and field theory; singular Legendre maps are the standard doorway to constraints and gauge systems."
  active:
    - "Infinite-dimensional Legendre transforms, convexity of exact effective actions, constrained phase spaces, gauge-boundary subtleties, and nonperturbative effective actions remain active across QFT, statistical field theory, and gravity."
---

## Summary

A Legendre transform replaces a variable by the derivative conjugate to it. In mechanics it replaces velocities by momenta:

$$
p_i=\frac{\partial L}{\partial\dot q^i},
\qquad
H(q,p)=p_i\dot q^i-L(q,\dot q),
$$

where $\dot q$ must be expressed in terms of $(q,p)$. In field theory it replaces time derivatives of fields by canonical momentum densities:

$$
\pi_i(x)=\frac{\partial\mathcal L}{\partial\dot\phi^i(x)},
\qquad
\mathcal H=\pi_i\dot\phi^i-\mathcal L.
$$

If the velocity–momentum map is invertible, the Legendre transform gives an ordinary Hamiltonian system. If it is not invertible, the result is not “a bad Hamiltonian.” It is a constrained system. Gauge theories, reparametrization-invariant systems, and many gravitational actions live here.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram showing the Legendre transform from Lagrangian data through the momentum map to Hamiltonian data, with branches for regular systems, field theories, constrained systems, and source Legendre transforms.](/figures/math-toolkit/legendre-transform-map.svg)

<figcaption>

The Legendre transform passes through the momentum map. In the regular case, velocities can be solved in terms of momenta. In the singular case, the image is a constrained subspace of phase space. QFT also uses a source Legendre transform from $W[J]$ to the effective action $\Gamma[\varphi]$.

</figcaption>
</figure>

QFT uses Legendre transforms in two closely related but distinct ways:

1. The **canonical Legendre transform** sends a Lagrangian density $\mathcal L(\phi,\dot\phi,\nabla\phi)$ to a Hamiltonian density $\mathcal H(\phi,\pi,\nabla\phi)$.
2. The **source Legendre transform** sends the connected generating functional $W[J]$ to the effective action $\Gamma[\varphi]$.

Both are versions of the same mathematical idea: trade a variable for its conjugate slope.

## Prerequisites

You should know [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/), [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/), and [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/). This page assumes that actions are varied carefully and that boundary terms have been controlled before canonical momenta are read off.

For the source Legendre transform, it is useful to recall from [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/) that with Lorentzian convention

$$
Z[J]
=
\int\mathcal D\phi\,e^{iS[\phi]+i\int J\phi},
\qquad
W[J]=-i\log Z[J],
$$

one has

$$
\frac{\delta W}{\delta J(x)}=\langle\phi(x)\rangle_J.
$$

## Core idea

The one-variable Legendre transform starts from a function $f(v)$. Define the conjugate variable

$$
p=\frac{df}{dv}.
$$

If this relation can be inverted to give $v=v(p)$, define

$$
g(p)=pv(p)-f(v(p)).
$$

Then

$$
\frac{dg}{dp}=v.
$$

So $f$ had slope $p$ as a function of $v$, while $g$ has slope $v$ as a function of $p$. The Legendre transform swaps the role of variable and slope.

For a function of many variables,

$$
p_i=\frac{\partial f}{\partial v^i},
\qquad
g(p)=p_iv^i-f(v),
$$

again with $v=v(p)$ after inverting the gradient map.

In mechanics, $f$ is the Lagrangian as a function of velocities. In thermodynamics, Legendre transforms exchange extensive variables and intensive variables. In QFT, source Legendre transforms exchange sources and expectation values.

The algebra is tiny. The consequences are not.

## Setup and conventions

Let $q^i(t)$ be generalized coordinates and let

$$
L=L(q,\dot q,t).
$$

The canonical momentum is

$$
p_i=\frac{\partial L}{\partial\dot q^i}.
$$

The Hessian with respect to velocities is

$$
W_{ij}(q,\dot q,t)
=
\frac{\partial^2 L}{\partial\dot q^i\partial\dot q^j}.
$$

If

$$
\det W_{ij}\neq0,
$$

then locally the relation $p_i=\partial L/\partial\dot q^i$ can be inverted to obtain

$$
\dot q^i=\dot q^i(q,p,t).
$$

The Hamiltonian is

$$
H(q,p,t)
=
p_i\dot q^i(q,p,t)-L(q,\dot q(q,p,t),t).
$$

This is the **regular** case.

If $\det W=0$, the momenta do not determine all velocities. Then the Legendre map has a nontrivial kernel and its image is a constrained submanifold of the would-be phase space. This is the **singular** case.

For fields on spacetime with coordinates $x^\mu=(t,\mathbf x)$, the canonical momenta are densities on a spatial slice:

$$
\pi_i(t,\mathbf x)
=
\frac{\partial\mathcal L}{\partial\dot\phi^i(t,\mathbf x)}.
$$

The Hamiltonian is

$$
H[\phi,\pi]
=
\int d^{d-1}\mathbf x\,\mathcal H(\phi,\pi,\nabla\phi),
$$

where

$$
\mathcal H=\pi_i\dot\phi^i-\mathcal L
$$

after solving for $\dot\phi$ in terms of $\pi$ when possible.

## Convex duality version

For a convex function $f(v)$, the globally safe definition is the Legendre–Fenchel transform

$$
f^*(p)=\sup_v\left[p_iv^i-f(v)\right].
$$

If $f$ is smooth and strictly convex, the supremum is achieved where

$$
p_i=\frac{\partial f}{\partial v^i},
$$

and the formula reduces to the usual Legendre transform.

Why mention this in a QFT toolkit? Because the exact Euclidean effective action is naturally convex in many settings, while classical Lorentzian Lagrangians are often not convex functions of all fields. The local canonical transform used in Hamiltonian mechanics is therefore not always the same thing as a global convex dual.

For the canonical part of this page, we use the local differential-geometric version. For the effective-action part, convexity becomes more visible.

## Mechanical Legendre transform

Start with

$$
L(q,\dot q)=\frac12m\dot q^2-V(q).
$$

The momentum is

$$
p=\frac{\partial L}{\partial\dot q}=m\dot q.
$$

Since $m\neq0$, the velocity is

$$
\dot q=\frac{p}{m}.
$$

The Hamiltonian is

$$
H(q,p)=p\dot q-L
=
\frac{p^2}{m}-\left(\frac12m\frac{p^2}{m^2}-V(q)\right)
=
\frac{p^2}{2m}+V(q).
$$

The variational reason this works is visible from the first variation:

$$
\delta L
=
\frac{\partial L}{\partial q^i}\delta q^i+p_i\delta\dot q^i.
$$

The endpoint term in the action variation is

$$
\left[p_i\delta q^i\right]_{t_i}^{t_f},
$$

so $p_i$ is the coefficient conjugate to $\delta q^i$ at the boundary. The Legendre transform is therefore not just algebraic; it is tied to the boundary term of the variational principle.

## Differential identity for the Hamiltonian

Assume a regular Lagrangian. Define

$$
H(q,p,t)=p_i\dot q^i-L(q,\dot q,t),
$$

where $\dot q=\dot q(q,p,t)$. Varying gives

$$
\delta H
=
\dot q^i\delta p_i+p_i\delta\dot q^i
-
\frac{\partial L}{\partial q^i}\delta q^i
-
\frac{\partial L}{\partial\dot q^i}\delta\dot q^i
-
\frac{\partial L}{\partial t}\delta t.
$$

Since

$$
p_i=\frac{\partial L}{\partial\dot q^i},
$$

the $\delta\dot q^i$ terms cancel. Thus

$$
\delta H
=
\dot q^i\delta p_i
-
\frac{\partial L}{\partial q^i}\delta q^i
-
\frac{\partial L}{\partial t}\delta t.
$$

Therefore

$$
\frac{\partial H}{\partial p_i}=\dot q^i,
\qquad
\frac{\partial H}{\partial q^i}=-\frac{\partial L}{\partial q^i},
\qquad
\frac{\partial H}{\partial t}=-\frac{\partial L}{\partial t}.
$$

Together with the Euler–Lagrange equation

$$
\frac{d p_i}{dt}=\frac{\partial L}{\partial q^i},
$$

this gives Hamilton's equations:

$$
\dot q^i=\frac{\partial H}{\partial p_i},
\qquad
\dot p_i=-\frac{\partial H}{\partial q^i}.
$$

The cancellation of $\delta\dot q$ is the whole trick. A Legendre transform is engineered to remove velocity variations and replace them by momentum variations.

## Field-theory Legendre transform

For fields, split spacetime into time plus space. The Lagrangian is

$$
L(t)=\int d^{d-1}\mathbf x\,\mathcal L(\phi,\dot\phi,\nabla\phi).
$$

The canonical momentum density is

$$
\pi_i(t,\mathbf x)
=
\frac{\partial\mathcal L}{\partial\dot\phi^i(t,\mathbf x)}.
$$

If the velocity–momentum relation is invertible, define

$$
\mathcal H(\phi,\pi,\nabla\phi)
=
\pi_i\dot\phi^i-\mathcal L,
$$

where $\dot\phi$ is expressed in terms of $(\phi,\pi,\nabla\phi)$.

Then

$$
H[\phi,\pi]=\int d^{d-1}\mathbf x\,\mathcal H.
$$

The field-theory Hamilton equations take the formal form

$$
\dot\phi^i(x)=\frac{\delta H}{\delta\pi_i(x)},
\qquad
\dot\pi_i(x)=-\frac{\delta H}{\delta\phi^i(x)},
$$

provided the functional derivatives of $H$ exist on the chosen phase space. This caveat matters. Spatial derivative terms in $\mathcal H$ produce boundary terms when $\delta H$ is computed, so the Hamiltonian must be functionally differentiable before these equations are meaningful.

That is why [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) comes immediately before this page.

## Example: real scalar field

Take the mostly-minus Lorentzian scalar Lagrangian density

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi)
=
\frac12\dot\phi^2-\frac12\nabla\phi\cdot\nabla\phi-V(\phi).
$$

The canonical momentum is

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi.
$$

The Hamiltonian density is

$$
\mathcal H
=
\pi\dot\phi-\mathcal L
=
\pi^2-\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+V(\phi),
$$

so

$$
\mathcal H
=
\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+V(\phi).
$$

The Hamiltonian is

$$
H=\int d^{d-1}\mathbf x\,
\left[
\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+V(\phi)
\right].
$$

Its variation is

$$
\delta H
=
\int d^{d-1}\mathbf x\,
\left[
\pi\delta\pi+\nabla\phi\cdot\nabla\delta\phi+V'(\phi)\delta\phi
\right].
$$

After spatial integration by parts,

$$
\delta H
=
\int d^{d-1}\mathbf x\,
\left[
\pi\delta\pi+\left(-\nabla^2\phi+V'(\phi)\right)\delta\phi
\right]
+
\int_{\partial\Sigma}dS_i\,\partial_i\phi\,\delta\phi.
$$

If the boundary term vanishes under the chosen boundary conditions, Hamilton's equations are

$$
\dot\phi=\pi,
$$

and

$$
\dot\pi=
\nabla^2\phi-V'(\phi).
$$

Combining them gives

$$
\ddot\phi-\nabla^2\phi+V'(\phi)=0,
$$

or

$$
\Box\phi+V'(\phi)=0.
$$

This matches the Euler–Lagrange equation.

## Example: complex scalar field

For a complex scalar field, treat $\phi$ and $\phi^*$ as independent variables during variation. With

$$
\mathcal L
=
\partial_\mu\phi^*\partial^\mu\phi-V(|\phi|^2),
$$

the time-derivative part is

$$
\dot\phi^*\dot\phi.
$$

The conjugate momenta are

$$
\pi_\phi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi^*,
\qquad
\pi_{\phi^*}=\frac{\partial\mathcal L}{\partial\dot\phi^*}=\dot\phi.
$$

Thus the Hamiltonian density is

$$
\mathcal H
=
\pi_\phi\dot\phi+
\pi_{\phi^*}\dot\phi^*-\mathcal L.
$$

Substituting

$$
\dot\phi=\pi_{\phi^*},
\qquad
\dot\phi^*=\pi_\phi,
$$

gives

$$
\mathcal H
=
\pi_\phi\pi_{\phi^*}
+
\nabla\phi^*\cdot\nabla\phi
+V(|\phi|^2).
$$

The apparent cross-labeling of momenta is not a mistake. It comes from treating $\phi$ and $\phi^*$ as independent variables.

## Singular Legendre maps

The regularity condition

$$
\det\left(\frac{\partial^2 L}{\partial\dot q^i\partial\dot q^j}\right)\neq0
$$

is not a technical nicety. It is the condition that momenta determine velocities.

If the Hessian is singular, some relations among $(q,p)$ appear before any equation of motion is used. These are **primary constraints**.

A very simple finite-dimensional example is

$$
L(q^1,q^2,\dot q^1,\dot q^2)
=
\frac12(\dot q^1-q^2)^2.
$$

The momenta are

$$
p_1=\dot q^1-q^2,
\qquad
p_2=0.
$$

The relation

$$
p_2=0
$$

is a primary constraint. The velocity $\dot q^2$ is absent from $L$, so no Legendre transform can solve for it.

The canonical Hamiltonian is

$$
H_c=p_1\dot q^1+p_2\dot q^2-L.
$$

Using

$$
\dot q^1=p_1+q^2,
$$

and imposing $p_2=0$ only after identifying the constraint, one finds

$$
H_c=\frac12p_1^2+p_1q^2.
$$

The undetermined velocity $\dot q^2$ enters the total Hamiltonian with a multiplier:

$$
H_T=H_c+u(t)p_2.
$$

This is the first glimpse of Dirac's constrained Hamiltonian formalism. Later pages on constraints should develop the algorithm systematically.

## Gauge fields are singular

Gauge theories usually have singular Legendre maps because not all components of the gauge field carry independent velocities.

For electromagnetism,

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu},
$$

with

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The time derivative of $A_0$ does not appear in $F_{\mu\nu}$. Therefore its conjugate momentum vanishes:

$$
\pi^0=0.
$$

This is a primary constraint. The field $A_0$ is not an ordinary dynamical coordinate with an independently determined velocity. It acts as a multiplier imposing Gauss's law.

This is not a defect of electromagnetism. It is how gauge redundancy appears in Hamiltonian language. A naive attempt to invert the Legendre map before recognizing constraints will misidentify the phase space.

The same story becomes richer in non-Abelian gauge theory and gravity, but the first sign is already visible in Maxwell theory.

## Boundary terms and the Legendre transform

The canonical momentum is read from the boundary term in the action variation. For mechanics,

$$
\delta S
=
\int_{t_i}^{t_f}dt\,E_i(L)\delta q^i
+
\left[p_i\delta q^i\right]_{t_i}^{t_f}.
$$

Thus

$$
p_i=\frac{\partial L}{\partial\dot q^i}
$$

is also the endpoint response conjugate to $q^i$.

If we add a total derivative,

$$
L'=L+\frac{dF(q,t)}{dt},
$$

then the momentum changes:

$$
p'_i
=
\frac{\partial L'}{\partial\dot q^i}
=
p_i+\frac{\partial F}{\partial q^i}.
$$

The equations of motion are unchanged, but the canonical one-form changes by an exact term:

$$
p'_i\delta q^i=p_i\delta q^i+\delta F-\frac{\partial F}{\partial t}\delta t.
$$

This is the finite-dimensional ancestor of boundary-term ambiguities in covariant phase space. In field theory, a total derivative can shift momenta, charges, and symplectic potentials even though it does not change the bulk Euler–Lagrange equations.

## Partial Legendre transforms

Sometimes only some variables should be transformed. Suppose the variables split into $v^a$ and $y^A$, and define

$$
p_a=\frac{\partial f}{\partial v^a}.
$$

A partial Legendre transform is

$$
g(p,y)=p_av^a-f(v,y),
$$

with $v=v(p,y)$.

This appears in several places:

- in mechanics when only some cyclic or auxiliary variables are transformed;
- in thermodynamics when changing ensembles;
- in QFT when integrating out or Legendre-transforming only selected sources;
- in constrained systems where only the nondegenerate velocities can be solved for.

A partial Legendre transform is not a compromise. It is often the correct operation because different variables play different roles.

## Source Legendre transform and effective action

The connected generating functional $W[J]$ is a functional of sources. With the Lorentzian convention

$$
Z[J]=e^{iW[J]},
$$

the source expectation value is

$$
\varphi(x)=\frac{\delta W[J]}{\delta J(x)}.
$$

The effective action is the Legendre transform

$$
\Gamma[\varphi]
=
W[J]-\int d^dx\,J(x)\varphi(x),
$$

where $J$ is expressed as a functional of $\varphi$.

Varying gives

$$
\delta\Gamma
=
\delta W-
\int d^dx\,\delta J\,\varphi
-
\int d^dx\,J\,\delta\varphi.
$$

Since

$$
\delta W=\int d^dx\,\frac{\delta W}{\delta J}\delta J
=\int d^dx\,\varphi\delta J,
$$

the $\delta J$ terms cancel, leaving

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

At zero source,

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=0.
$$

Thus the quantum effective action gives the quantum-corrected equation of motion for the expectation value.

Euclidean conventions often define $W_E[J]=\log Z_E[J]$ with

$$
Z_E[J]=\int\mathcal D\phi\,e^{-S_E[\phi]+\int J\phi}.
$$

Then many authors define

$$
\Gamma_E[\varphi]
=
\sup_J\left(\int J\varphi-W_E[J]\right),
$$

so that

$$
\frac{\delta\Gamma_E}{\delta\varphi}=J.
$$

The sign difference is convention, but it must be tracked.

## Legendre transform versus integrating out

A Legendre transform is not the same as integrating out a field.

Integrating out means performing, exactly or approximately, an integral over degrees of freedom:

$$
e^{iS_{\rm eff}[\ell]}
=
\int\mathcal Dh\,e^{iS[\ell,h]}.
$$

A Legendre transform means replacing a variable by its conjugate derivative:

$$
\Gamma[\varphi]=W[J]-\int J\varphi.
$$

Both operations produce objects called “effective actions” in different contexts, and this is historically responsible for some notational soup. The Wilsonian effective action, the 1PI effective action, and a classical Hamiltonian are related ideas, but they are not the same operation.

A good diagnostic is:

$$
\text{integration removes variables; Legendre transformation changes variables.}
$$

## Legendre transform and stationary phase

The Legendre transform also appears in stationary-phase approximations. Suppose

$$
I(p)=\int dv\,e^{i\lambda(pv-f(v))}
$$

with large $\lambda$. The saddle equation is

$$
p=f'(v_*).
$$

The leading phase is

$$
\lambda\left(pv_*-f(v_*)\right)
=
\lambda f^*(p).
$$

Thus the Legendre transform is the classical saddle of a Fourier-type transform. This observation underlies many appearances of Legendre transforms in semiclassical mechanics, thermodynamics, large-deviation theory, and path integrals.

In QFT, the effective action can be viewed semiclassically as the object whose stationary points encode the relation between sources and classical fields.

## Common pitfalls

**Forgetting to solve for velocities.** The expression $H=p_i\dot q^i-L$ is not a Hamiltonian until $\dot q$ has been written in terms of $(q,p)$, unless one is explicitly working with constraints and multipliers.

**Assuming every Lagrangian has an ordinary Hamiltonian.** Singular Hessians lead to constraints. Gauge theories are supposed to be singular.

**Dropping boundary terms before reading momenta.** Canonical momenta are coefficients in the endpoint or hypersurface variation. Boundary terms can shift them.

**Confusing a Legendre transform with a Fourier transform.** They are related by saddle point in some limits, but they are not the same operation.

**Confusing the Wilsonian action with the 1PI effective action.** Integrating out modes and Legendre-transforming sources answer different questions.

**Ignoring convexity.** The classical local Legendre transform used in mechanics requires local invertibility. The global Legendre–Fenchel transform requires convexity. Exact Euclidean effective actions have convexity properties that the classical potential may not share.

**Treating $\phi$ and $\phi^*$ as dependent during canonical variation.** In complex-field calculations, treat them as independent variables, impose reality or conjugacy conditions afterward as appropriate.

**Using a Hamiltonian before checking differentiability.** If spatial boundary terms remain in $\delta H$, Hamilton's equations are not yet well-defined on the chosen phase space.

## Relations to other pages

[Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) explains why canonical momenta and Hamiltonians depend on boundary behavior. [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/) supplies the Lagrangian equations that Hamilton's equations must reproduce.

This page prepares the phase-space pages that follow. A Legendre transform gives canonical variables, but the symplectic form explains their geometry, Poisson brackets invert that geometry, and constraints explain what happens when the Legendre map is singular.

For path-integral applications, [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/) explains how classical and one-loop effective actions arise from saddle expansions. [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) and [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explain the determinant factors that appear when quadratic fluctuations are integrated out.

## Research status

Finite-dimensional Legendre transforms and regular Hamiltonian mechanics are settled. Singular Legendre transforms and Dirac constraints are also standard, although their boundary-sensitive and gauge-theoretic applications require care.

In QFT, the canonical formalism is rigorous in many regulated settings and formal in the continuum unless domains, boundary conditions, and operator issues are controlled. The source Legendre transform defining the 1PI effective action is perturbatively standard. Nonperturbatively, convexity, gauge dependence, composite operators, renormalization, and field-space geometry make the effective action a subtle object.

The main working rule remains reliable: check the Hessian, check the boundary terms, then transform.

## Exercises

### Exercise 1: Quadratic Legendre transform

Let

$$
f(v)=\frac12av^2
$$

with $a>0$. Compute $f^*(p)$.

<details><summary><strong>Solution</strong></summary>

The conjugate variable is

$$
p=\frac{df}{dv}=av,
$$

so

$$
v=\frac{p}{a}.
$$

Then

$$
f^*(p)=pv-f(v)
=\frac{p^2}{a}-\frac12a\frac{p^2}{a^2}
=\frac{p^2}{2a}.
$$

Thus

$$
f^*(p)=\frac{p^2}{2a}.
$$

</details>

### Exercise 2: Particle in a vector potential

Let

$$
L=\frac12m\dot{\mathbf q}^{\,2}+e\mathbf A(\mathbf q)\cdot\dot{\mathbf q}-e\Phi(\mathbf q).
$$

Find the canonical momentum and Hamiltonian.

<details><summary><strong>Solution</strong></summary>

The canonical momentum is

$$
\mathbf p=\frac{\partial L}{\partial\dot{\mathbf q}}
=m\dot{\mathbf q}+e\mathbf A(\mathbf q).
$$

Thus

$$
\dot{\mathbf q}=\frac{\mathbf p-e\mathbf A}{m}.
$$

The Hamiltonian is

$$
H=\mathbf p\cdot\dot{\mathbf q}-L.
$$

Substitute $\dot{\mathbf q}=(\mathbf p-e\mathbf A)/m$:

$$
H
=
\frac{\mathbf p\cdot(\mathbf p-e\mathbf A)}{m}
-\frac12m\left(\frac{\mathbf p-e\mathbf A}{m}\right)^2
-e\mathbf A\cdot\frac{\mathbf p-e\mathbf A}{m}
+e\Phi.
$$

The cross terms combine to give

$$
H=\frac{(\mathbf p-e\mathbf A)^2}{2m}+e\Phi.
$$

The canonical momentum $\mathbf p$ is not the kinetic momentum $m\dot{\mathbf q}$; rather,

$$
m\dot{\mathbf q}=\mathbf p-e\mathbf A.
$$

</details>

### Exercise 3: Scalar Hamiltonian density

For

$$
\mathcal L=\frac12\dot\phi^2-\frac12\nabla\phi\cdot\nabla\phi-\frac12m^2\phi^2,
$$

compute $\pi$ and $\mathcal H$.

<details><summary><strong>Solution</strong></summary>

The canonical momentum is

$$
\pi=\frac{\partial\mathcal L}{\partial\dot\phi}=\dot\phi.
$$

Therefore

$$
\mathcal H
=\pi\dot\phi-\mathcal L
=\pi^2-\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+\frac12m^2\phi^2.
$$

Thus

$$
\mathcal H
=
\frac12\pi^2+\frac12\nabla\phi\cdot\nabla\phi+\frac12m^2\phi^2.
$$

</details>

### Exercise 4: A singular Lagrangian

Let

$$
L=\frac12(\dot q^1-q^2)^2.
$$

Find the momenta, identify the primary constraint, and compute the canonical Hamiltonian.

<details><summary><strong>Solution</strong></summary>

The momenta are

$$
p_1=\frac{\partial L}{\partial\dot q^1}=\dot q^1-q^2,
\qquad
p_2=\frac{\partial L}{\partial\dot q^2}=0.
$$

Thus

$$
p_2=0
$$

is a primary constraint. The first equation gives

$$
\dot q^1=p_1+q^2.
$$

The canonical Hamiltonian is

$$
H_c=p_1\dot q^1+p_2\dot q^2-L.
$$

Using $p_2=0$ after identifying the constraint and substituting $\dot q^1=p_1+q^2$,

$$
H_c
=p_1(p_1+q^2)-\frac12p_1^2
=\frac12p_1^2+p_1q^2.
$$

The undetermined velocity $\dot q^2$ is associated with the constraint and appears with a multiplier in the total Hamiltonian.

</details>

### Exercise 5: Source Legendre transform sign

Suppose

$$
\varphi(x)=\frac{\delta W[J]}{\delta J(x)},
\qquad
\Gamma[\varphi]=W[J]-\int d^dx\,J(x)\varphi(x).
$$

Show that

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

<details><summary><strong>Solution</strong></summary>

Vary $\Gamma$:

$$
\delta\Gamma
=\delta W-
\int d^dx\,\delta J(x)\varphi(x)
-
\int d^dx\,J(x)\delta\varphi(x).
$$

Since

$$
\delta W
=\int d^dx\,\frac{\delta W}{\delta J(x)}\delta J(x)
=\int d^dx\,\varphi(x)\delta J(x),
$$

the first two terms cancel. Therefore

$$
\delta\Gamma
=-\int d^dx\,J(x)\delta\varphi(x).
$$

Reading off the functional derivative gives

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

</details>

## References

- V. I. Arnold, *Mathematical Methods of Classical Mechanics*. Geometric mechanics and Legendre transforms.
- R. Abraham and J. E. Marsden, *Foundations of Mechanics*. Tangent and cotangent bundles, Legendre maps, symplectic geometry, and Hamiltonian mechanics.
- H. Goldstein, C. Poole, and J. Safko, *Classical Mechanics*. Standard mechanics treatment of Lagrangian and Hamiltonian formalisms.
- P. A. M. Dirac, *Lectures on Quantum Mechanics*. The classic short account of constrained Hamiltonian systems.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Constrained Hamiltonian systems, gauge symmetries, and canonical quantization.
- S. Coleman, *Aspects of Symmetry*. Functional methods, effective potentials, gauge fixing, and Hamiltonian intuition in field theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Canonical formalism, external-field methods, and effective actions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Generating functionals, Legendre transforms, effective actions, and convexity issues.
- M. Srednicki, *Quantum Field Theory*. Canonical fields, path integrals, source functionals, and effective actions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Classical field theory, Hamiltonians, path integrals, and effective actions.
- C. P. Burgess, *Introduction to Effective Field Theory*. Wilsonian actions, 1PI actions, integrating out, matching, and effective-action logic.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit, covering regular and singular Legendre maps, scalar field Hamiltonians, gauge constraints, boundary sensitivity, and source Legendre transforms.
