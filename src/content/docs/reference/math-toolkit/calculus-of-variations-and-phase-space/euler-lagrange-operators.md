---
title: "Euler–Lagrange Operators"
description: "Derive Euler–Lagrange operators for local field theories, including total derivatives, higher-derivative Lagrangians, boundary terms, linearization, gauge identities, and QFT examples."
sidebar:
  label: "Euler–Lagrange Operators"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard calculus of variations, jet-bundle variational calculus, and QFT classical-field-theory references, including Gelfand–Fomin, Olver, Anderson, Coleman, Srednicki, Schwartz, Weinberg, and Zinn-Justin."
topics:
  - Euler–Lagrange equations
  - local actions
  - total derivatives
  - boundary terms
  - variational calculus
canonicalTopics:
  - euler-lagrange-operators
  - variational-calculus
  - local-actions
  - field-equations
researchStatus:
  established:
    - "Euler–Lagrange operators are the standard local differential operators obtained by varying an action and integrating by parts until all derivatives have been removed from the variation."
  active:
    - "Boundary-sensitive variational principles, covariant phase space, higher-derivative effective actions, gauge identities, and BV-BRST formulations remain active in modern QFT, gravity, and mathematical physics."
---

## Summary

The Euler–Lagrange operator is the part of the variation of a local action that multiplies the undifferentiated field variation. For fields $\phi^i$ and an action

$$
S[\phi]=\int_M d^dx\,\mathcal L(\phi,\partial\phi,\partial^2\phi,\ldots),
$$

the first variation has the form

$$
\delta S
=
\int_M d^dx\,E_i(\mathcal L)\delta\phi^i
+
\int_{\partial M}\theta(\phi,\delta\phi).
$$

The local equations of motion are

$$
E_i(\mathcal L)=0,
$$

provided the boundary term is compatible with the allowed variations. The boundary term is not decoration. It decides whether the functional derivative exists, which boundary conditions are allowed, and what symplectic structure survives on phase space.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram from a local Lagrangian to its raw variation, integration by parts, Euler–Lagrange operator, boundary term, and phase-space data.](/figures/math-toolkit/euler-lagrange-integration-by-parts.svg)

<figcaption>

The Euler–Lagrange operator is produced by integrating by parts until no derivative acts on $\delta\phi^i$. The same calculation also produces the boundary term $\theta^\mu$, which later becomes the seed of functional differentiability, conserved charges, and symplectic geometry.

</figcaption>
</figure>

The slogan is:

$$
\text{vary locally, integrate by parts, read off the bulk coefficient.}
$$

The warning is:

$$
\text{the bulk equation and the boundary term are born together.}
$$

## Prerequisites

You should know [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/), especially the idea that a functional derivative is a covector on field space represented by a distributional coefficient. The pages on [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) are useful because Euler–Lagrange operators are often kernels of local differential operators acting on delta functions.

You should also be comfortable with integration by parts and with the site convention that the default Lorentzian metric is mostly-minus. For scalar fields, this means

$$
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

## Core idea

Start with a local Lagrangian density depending on fields and finitely many derivatives. For a first-derivative theory,

$$
\mathcal L=\mathcal L(\phi^i,\partial_\mu\phi^i,x).
$$

Its variation is

$$
\delta\mathcal L
=
\frac{\partial\mathcal L}{\partial\phi^i}\delta\phi^i
+
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\partial_\mu\delta\phi^i.
$$

The second term is not yet in functional-derivative form because a derivative acts on $\delta\phi^i$. Integrating by parts gives

$$
\delta\mathcal L
=
\left[
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
\right]\delta\phi^i
+
\partial_\mu
\left(
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\delta\phi^i
\right).
$$

Therefore the Euler–Lagrange operator is

$$
E_i(\mathcal L)
=
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}.
$$

The boundary current for a first-derivative Lagrangian is

$$
\theta^\mu(\phi,\delta\phi)
=
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\delta\phi^i.
$$

The Euler–Lagrange equations are $E_i(\mathcal L)=0$.

## Setup and notation

Fields are denoted $\phi^i(x)$, where $i$ labels all discrete components. The action is

$$
S[\phi]=\int_M d^dx\,\mathcal L.
$$

The variation is written

$$
\delta S
=
\int_M d^dx\,E_i(\mathcal L)\delta\phi^i
+
\int_{\partial M}d\Sigma_\mu\,\theta^\mu.
$$

Here $d\Sigma_\mu$ is the oriented boundary hypersurface element. In flat space, for a constant-time boundary, it reduces to the familiar normal-vector times spatial volume element.

The notation $E_i(\mathcal L)$ means the Euler–Lagrange operator applied to the Lagrangian density. Some authors write

$$
\frac{\delta S}{\delta\phi^i(x)}=E_i(\mathcal L)(x),
$$

with the boundary conditions left implicit. This is convenient, but the safer statement is that $E_i(\mathcal L)$ is the bulk coefficient in $\delta S$ after integrating by parts.

## First-derivative field theories

For

$$
\mathcal L=\mathcal L(\phi^i,\partial_\mu\phi^i,x),
$$

the Euler–Lagrange equations are

$$
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
=0.
$$

This looks identical to the finite-dimensional Euler–Lagrange equation

$$
\frac{\partial L}{\partial q^i}
-
\frac{d}{dt}\frac{\partial L}{\partial\dot q^i}=0,
$$

except that time has been replaced by spacetime coordinates and velocities have been replaced by field derivatives.

The expression $\partial\mathcal L/\partial(\partial_\mu\phi^i)$ means an ordinary partial derivative of the function $\mathcal L$ with respect to its argument $\partial_\mu\phi^i$, treating $\phi^i$ and $\partial_\mu\phi^i$ as independent variables during the algebraic differentiation. The spacetime derivative $\partial_\mu$ outside the fraction is then applied to the resulting field-dependent expression.

This distinction is small enough to ignore once and large enough to punish you forever if ignored systematically.

## Example: real scalar field

With mostly-minus metric, take

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-V(\phi).
$$

Then

$$
\frac{\partial\mathcal L}{\partial\phi}
=
-m^2\phi-V'(\phi),
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
=
\partial^\mu\phi.
$$

Therefore

$$
E(\mathcal L)
=
-m^2\phi-V'(\phi)-\partial_\mu\partial^\mu\phi
=
-(\Box+m^2)\phi-V'(\phi).
$$

The Euler–Lagrange equation $E(\mathcal L)=0$ is

$$
(\Box+m^2)\phi+V'(\phi)=0.
$$

For the free scalar, $V=0$, this is the Klein–Gordon equation

$$
(\Box+m^2)\phi=0.
$$

The boundary current is

$$
\theta^\mu=\partial^\mu\phi\,\delta\phi.
$$

Thus

$$
\delta S
=
\int_M d^dx\,[-(\Box+m^2)\phi-V'(\phi)]\delta\phi
+
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

The field equation follows only after the boundary term is made to vanish or is otherwise canceled by boundary data.

## Example: complex scalar field

For a complex scalar, treat $\phi$ and $\phi^*$ as independent during variation. With

$$
\mathcal L
=
\partial_\mu\phi^*\partial^\mu\phi-m^2\phi^*\phi,
$$

variation with respect to $\phi^*$ gives

$$
\frac{\partial\mathcal L}{\partial\phi^*}=-m^2\phi,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^*)}=\partial^\mu\phi.
$$

Therefore

$$
E_{\phi^*}(\mathcal L)=-(\Box+m^2)\phi.
$$

Similarly,

$$
E_{\phi}(\mathcal L)=-(\Box+m^2)\phi^*.
$$

The two equations are complex conjugates after the independent-variation calculation is finished.

## Example: Maxwell theory

Take

$$
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}-J^\mu A_\mu,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

Varying gives

$$
\delta\mathcal L
=
-\frac12F^{\mu\nu}\delta F_{\mu\nu}-J^\nu\delta A_\nu.
$$

Using antisymmetry of $F^{\mu\nu}$,

$$
\delta\mathcal L
=
-F^{\mu\nu}\partial_\mu\delta A_\nu-J^\nu\delta A_\nu.
$$

Integrating by parts,

$$
\delta\mathcal L
=
(\partial_\mu F^{\mu\nu}-J^\nu)\delta A_\nu
-
\partial_\mu(F^{\mu\nu}\delta A_\nu).
$$

Thus

$$
E^\nu(\mathcal L)=\partial_\mu F^{\mu\nu}-J^\nu,
$$

and the equation of motion is

$$
\partial_\mu F^{\mu\nu}=J^\nu.
$$

The boundary current is

$$
\theta^\mu=-F^{\mu\nu}\delta A_\nu.
$$

For $J^\nu=0$, the identity

$$
\partial_\nu\partial_\mu F^{\mu\nu}=0
$$

holds automatically because $F^{\mu\nu}$ is antisymmetric. This is the simplest example of a Noether identity associated with gauge redundancy.

## Higher-derivative Lagrangians

Suppose $\mathcal L$ depends on derivatives up to order $k$:

$$
\mathcal L
=
\mathcal L(\phi^i,\partial_\mu\phi^i,\partial_\mu\partial_\nu\phi^i,\ldots).
$$

The raw variation contains derivatives of $\delta\phi^i$:

$$
\delta\mathcal L
=
\sum_{|\alpha|\le k}
\frac{\partial\mathcal L}{\partial(D_\alpha\phi^i)}D_\alpha\delta\phi^i.
$$

Here $\alpha$ is a multi-index and $D_\alpha$ is a product of total derivatives. Integrating by parts $|\alpha|$ times gives

$$
\delta\mathcal L
=
\left[
\sum_{|\alpha|\le k}
(-D)_\alpha
\frac{\partial\mathcal L}{\partial(D_\alpha\phi^i)}
\right]\delta\phi^i
+
\partial_\mu\theta^\mu.
$$

Therefore

$$
E_i(\mathcal L)
=
\sum_{|\alpha|\le k}
(-D)_\alpha
\frac{\partial\mathcal L}{\partial(D_\alpha\phi^i)}.
$$

In ordinary coordinate notation, the first terms are

$$
E_i(\mathcal L)
=
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
+
\partial_\mu\partial_\nu
\frac{\partial\mathcal L}{\partial(\partial_\mu\partial_\nu\phi^i)}
-\cdots.
$$

The alternating signs come from repeated integration by parts.

### Total derivatives versus ordinary derivatives

In the higher-derivative formula, $D_\mu$ is the total derivative. It acts on explicit coordinate dependence and on all jet variables:

$$
D_\mu
=
\partial_\mu
+\partial_\mu\phi^i\frac{\partial}{\partial\phi^i}
+\partial_\mu\partial_\nu\phi^i
\frac{\partial}{\partial(\partial_\nu\phi^i)}
+\cdots.
$$

In simple physics notation, one often writes $\partial_\mu$ for this total derivative after the partial derivatives of $\mathcal L$ have been taken. The distinction matters in geometric variational calculus and in symbolic calculations.

## Example: a fourth-order scalar equation

Let

$$
\mathcal L=\frac12(\Box\phi)^2.
$$

Then

$$
\delta S
=
\int d^dx\,(\Box\phi)(\Box\delta\phi).
$$

Integrating by parts twice gives

$$
\delta S
=
\int d^dx\,(\Box^2\phi)\delta\phi
+
\text{boundary terms}.
$$

Thus

$$
E(\mathcal L)=\Box^2\phi.
$$

Higher-derivative actions arise naturally in effective field theory, gravity, anomalies, and regulator terms. They also often introduce extra degrees of freedom if treated as fundamental Lorentzian theories rather than as controlled effective corrections.

## Total divergences

Adding a total divergence to the Lagrangian does not change the Euler–Lagrange operator:

$$
\mathcal L\mapsto\mathcal L+\partial_\mu B^\mu
\qquad\Longrightarrow\qquad
E_i(\mathcal L+\partial_\mu B^\mu)=E_i(\mathcal L).
$$

This is because

$$
\delta\int_M d^dx\,\partial_\mu B^\mu
=
\int_{\partial M}d\Sigma_\mu\,\delta B^\mu.
$$

The bulk equation is unchanged, but the boundary term changes. That change can be physically important. Total derivatives include theta terms, Chern–Simons boundary terms, improvement terms in stress tensors, Gibbons–Hawking–York-like terms in gravity, and counterterms in holographic or effective actions.

So the correct statement is not “total derivatives do nothing.” The correct statement is:

$$
\text{total derivatives do not change bulk Euler–Lagrange equations, but they can change boundary data.}
$$

## Euler–Lagrange operators as variational derivatives

For a local action,

$$
S[\phi]=\int_M d^dx\,\mathcal L,
$$

the functional derivative is

$$
\frac{\delta S}{\delta\phi^i(x)}=E_i(\mathcal L)(x)
$$

only after boundary terms have been controlled. More carefully,

$$
\delta S
=
\int_M d^dx\,E_i(\mathcal L)\delta\phi^i
+
\int_{\partial M}d\Sigma_\mu\,\theta^\mu.
$$

If the allowed variations make the boundary integral vanish, then the functional derivative is represented by the bulk Euler–Lagrange operator. If not, $S$ is not differentiable on that field space without adding boundary terms, changing boundary conditions, or enlarging the phase space.

This distinction is unavoidable in gauge theory, gravity, finite-volume QFT, Hamiltonian mechanics, and any problem with interfaces or defects.

## Linearization and the Jacobi operator

The linearization of the Euler–Lagrange equation controls small fluctuations around a background. Let $\phi_0$ be a solution and write

$$
\phi^i=\phi_0^i+\eta^i.
$$

Then

$$
E_i(\mathcal L)[\phi_0+\eta]
=
E_i(\mathcal L)[\phi_0]
+\mathcal J_{ij}\eta^j
+O(\eta^2).
$$

Since $\phi_0$ solves the equation, the first term vanishes. The operator $\mathcal J_{ij}$ is the linearized Euler–Lagrange operator, often called the Jacobi operator or fluctuation operator.

For the scalar example,

$$
E(\mathcal L)=-(\Box+m^2)\phi-V'(\phi),
$$

so around $\phi_0$,

$$
\mathcal J\eta=-(\Box+m^2+V''(\phi_0))\eta.
$$

This is the operator whose determinant appears in one-loop saddle-point expansions and whose inverse, after prescriptions and boundary conditions, gives the propagator in a background.

For action-derived equations, the linearized operator is formally self-adjoint under appropriate boundary conditions. This is the field-theory version of the symmetry of second derivatives.

## Gauge identities

Gauge theories have redundant field variables. This redundancy appears in the Euler–Lagrange equations as differential identities.

Suppose an infinitesimal gauge transformation is

$$
\delta_\epsilon\phi^i=R^i{}_\alpha(\phi)\epsilon^\alpha,
$$

possibly with derivatives acting on $\epsilon^\alpha$. If the action is gauge invariant up to a boundary term, then

$$
0=\delta_\epsilon S
=
\int_M d^dx\,E_i(\mathcal L)R^i{}_\alpha\epsilon^\alpha
+
\text{boundary terms}.
$$

After integrating derivatives off $\epsilon^\alpha$, one obtains a Noether identity

$$
R^{\dagger i}{}_{\alpha}E_i(\mathcal L)=0.
$$

For Maxwell theory without sources,

$$
E^\nu=\partial_\mu F^{\mu\nu},
$$

and the identity is

$$
\partial_\nu E^\nu=0.
$$

These identities mean the equations are not independent. In the Hamiltonian language they lead to constraints. In the path integral they lead to gauge fixing, ghosts, and Faddeev–Popov determinants.

## Common pitfalls

The first pitfall is forgetting to integrate by parts. The coefficient of $\partial_\mu\delta\phi$ in the raw variation is not the Euler–Lagrange equation.

The second pitfall is losing a sign in Lorentzian scalar theory. With mostly-minus metric and

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2,
$$

the Euler–Lagrange operator is

$$
E=-(\Box+m^2)\phi,
$$

so $E=0$ gives $(\Box+m^2)\phi=0$.

The third pitfall is saying that total derivatives do not matter. They do not change bulk equations, but they change boundary terms, charges, and sometimes quantum phases.

The fourth pitfall is treating $\phi$ and $\partial_\mu\phi$ as independent forever. They are treated as independent only during the algebraic partial differentiation of $\mathcal L$. The spacetime derivative then acts on the resulting expression as a function of the actual field.

The fifth pitfall is ignoring gauge identities. Gauge-field Euler–Lagrange equations are related by differential identities; the Hessian has zero directions before gauge fixing.

The sixth pitfall is assuming that a formally correct bulk equation defines a good variational problem. A variational principle is a pair: bulk action plus boundary conditions or boundary terms.

## Relations to other pages

This page is the local-action continuation of [Variational Derivatives](/math-toolkit/calculus-of-variations-and-phase-space/variational-derivatives/). It supplies the bulk operator that appears when a local action is varied.

The boundary current $\theta^\mu$ is the starting point for the later pages on boundary terms, functional differentiability, symplectic forms, and Poisson brackets. The Hessian and Jacobi operator connect directly to [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Stationary Phase and Saddle Points](/math-toolkit/functional-integrals-determinants/stationary-phase-and-saddle-points/), and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

Gauge identities foreshadow [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/) and the later phase-space discussion of constraints.

## Research status

Euler–Lagrange operators are settled mathematics and standard physics. They are the classical backbone of field theory, mechanics, effective actions, and saddle-point expansions.

The subtle parts are not the local formula itself. They are the domains, boundary conditions, gauge redundancies, higher-derivative effective interpretations, and global field-space structure. Modern work on covariant phase space, asymptotic symmetries, edge modes, BV-BRST theory, gravitational boundary terms, and extended defects can all be read as increasingly careful answers to the question: what exactly did we mean by $\delta S=0$?

## Exercises

1. For

   $$
   \mathcal L
   =
   \frac12\partial_\mu\phi\partial^\mu\phi
   -\frac{\lambda}{4}(\phi^2-v^2)^2,
   $$

   compute $E(\mathcal L)$ and the field equation.

2. Let $B^\mu=B^\mu(\phi,x)$ and $\mathcal L=\partial_\mu B^\mu$. Show directly that the bulk Euler–Lagrange operator vanishes.

3. For Maxwell theory with $J^\mu=0$, show that $\partial_\nu E^\nu=0$ identically.

4. Compute the Euler–Lagrange operator for

   $$
   \mathcal L=\frac12(\Box\phi)^2-\frac12M^2\partial_\mu\phi\partial^\mu\phi.
   $$

5. For the scalar theory with potential $V(\phi)$, compute the linearized equation around a solution $\phi_0$.

<details><summary><strong>Solution</strong></summary>

1. We have

   $$
   \frac{\partial\mathcal L}{\partial\phi}
   =
   -\lambda\phi(\phi^2-v^2),
   \qquad
   \frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
   =
   \partial^\mu\phi.
   $$

   Therefore

   $$
   E(\mathcal L)
   =
   -\lambda\phi(\phi^2-v^2)-\Box\phi.
   $$

   The equation $E=0$ is

   $$
   \Box\phi+\lambda\phi(\phi^2-v^2)=0.
   $$

2. Vary

   $$
   S=\int_M d^dx\,\partial_\mu B^\mu.
   $$

   Then

   $$
   \delta S
   =
   \int_M d^dx\,\partial_\mu
   \left(\frac{\partial B^\mu}{\partial\phi^i}\delta\phi^i\right)
   =
   \int_{\partial M}d\Sigma_\mu\,
   \frac{\partial B^\mu}{\partial\phi^i}\delta\phi^i.
   $$

   There is no bulk term proportional to $\delta\phi^i$, so

   $$
   E_i(\partial_\mu B^\mu)=0.
   $$

3. For Maxwell theory,

   $$
   E^\nu=\partial_\mu F^{\mu\nu}.
   $$

   Taking the divergence gives

   $$
   \partial_\nu E^\nu
   =
   \partial_\nu\partial_\mu F^{\mu\nu}.
   $$

   Since partial derivatives commute and $F^{\mu\nu}=-F^{\nu\mu}$, the symmetric derivative operator is contracted with an antisymmetric tensor. Hence

   $$
   \partial_\nu\partial_\mu F^{\mu\nu}=0.
   $$

4. Varying the first term gives

   $$
   \delta\int d^dx\,\frac12(\Box\phi)^2
   =
   \int d^dx\,(\Box\phi)(\Box\delta\phi)
   =
   \int d^dx\,(\Box^2\phi)\delta\phi
   +\text{boundary terms}.
   $$

   The second term gives

   $$
   \delta\int d^dx\,\left(-\frac12M^2\partial_\mu\phi\partial^\mu\phi\right)
   =
   \int d^dx\,M^2\Box\phi\,\delta\phi
   +\text{boundary terms}.
   $$

   Therefore

   $$
   E(\mathcal L)=\Box^2\phi+M^2\Box\phi.
   $$

5. For

   $$
   E(\mathcal L)=-(\Box+m^2)\phi-V'(\phi),
   $$

   write $\phi=\phi_0+\eta$. Keeping first order in $\eta$ gives

   $$
   0=-(\Box+m^2)\eta-V''(\phi_0)\eta.
   $$

   Equivalently,

   $$
   (\Box+m^2+V''(\phi_0))\eta=0.
   $$

</details>

## References

- I. M. Gelfand and S. V. Fomin, *Calculus of Variations*, for the classical Euler–Lagrange formalism.
- P. J. Olver, *Applications of Lie Groups to Differential Equations*, for Euler operators, total derivatives, and the jet-space formulation.
- I. Anderson, *The Variational Bicomplex*, for the geometric structure behind local variational calculus.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on functional methods, solitons, instantons, and gauge fields.
- M. Srednicki, *Quantum Field Theory*, for scalar, spinor, and gauge-field actions and functional-method applications.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for classical field theory, Euler–Lagrange equations, Noether’s theorem, Green functions, and path integrals.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for variational principles, field equations, symmetries, gauge theory, and effective actions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for variational methods in field integrals, statistical field theory, and renormalization.

## Version history

- 2026-06-24: First polished draft.
