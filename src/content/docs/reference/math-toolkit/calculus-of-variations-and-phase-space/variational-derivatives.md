---
title: "Variational Derivatives"
description: "A QFT-oriented guide to functional derivatives as distributional gradients on field space, including measures, delta kernels, boundary conditions, source differentiation, chain rules, and Grassmann signs."
sidebar:
  label: "Variational Derivatives"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard calculus of variations, distribution theory, functional methods in QFT, and path-integral references."
topics:
  - variational derivatives
  - functional derivatives
  - field space
  - distributions
  - source differentiation
  - Grassmann variables
canonicalTopics:
  - functional-derivatives
  - variational-calculus
  - distributions
  - qft-functional-methods
researchStatus:
  established:
    - "Functional derivatives are the standard distributional gradients used to differentiate actions, generating functionals, source terms, and field redefinitions in QFT."
  active:
    - "In infinite-dimensional field spaces, the precise analytic setting depends on function spaces, boundary conditions, regulators, gauge redundancy, and operator domains."
---

## Summary

A variational derivative is the derivative of a functional with respect to a function or field. If $F[\phi]$ assigns a number to a field configuration $\phi$, then its first variation in the direction $\eta$ is

$$
D F[\phi](\eta)
=
\left.\frac{d}{d\epsilon}F[\phi+\epsilon\eta]\right|_{\epsilon=0}.
$$

When this linear functional of $\eta$ can be represented by integration against a kernel, we write

$$
D F[\phi](\eta)
=
\int_M d\mu_x\,
\frac{\delta F}{\delta\phi^i(x)}\,\eta^i(x).
$$

The object $\delta F/\delta\phi^i(x)$ is the variational derivative. In QFT it is usually a distribution, not an ordinary pointwise gradient. The basic identity

$$
\frac{\delta\phi^j(y)}{\delta\phi^i(x)}
=
\delta_i{}^j\delta_\mu(x,y)
$$

is the continuum version of $\partial q^j/\partial q^i=\delta_i{}^j$. Here $\delta_\mu(x,y)$ denotes the delta distribution associated with the measure used in the pairing; for the coordinate measure $d^dx$, it is $\delta^{(d)}(x-y)$.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Flow diagram explaining a variational derivative as a directional derivative represented by a distributional gradient on field space.](/figures/math-toolkit/functional-derivative-gradient.svg)

<figcaption>

A functional derivative is a continuum gradient: $dF=(\partial_iF)dq^i$ becomes $\delta F=\int d\mu_x\, (\delta F/\delta\phi^i(x))\delta\phi^i(x)$. The same differential can be represented by different kernels if the pairing measure or boundary class changes.

</figcaption>
</figure>

The phrase “take the functional derivative” therefore hides three choices: the class of allowed variations, the measure used in the pairing, and the boundary behavior. Forgetting any one of them is the source of a mildly horrifying fraction of sign and contact-term mistakes.

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/) page, especially the conventions for distributions, delta functions, integration by parts, and functional derivatives. The pages [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), and [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/) explain the distributional language used below.

The chapter overview [Calculus of Variations and Phase Space](/math-toolkit/calculus-of-variations-and-phase-space/) explains why variational derivatives are the first step toward Euler–Lagrange equations, boundary terms, symplectic forms, Poisson brackets, and constraints.

## Core idea

The functional derivative is defined by what it does to a variation. For a finite-dimensional function $F(q)$,

$$
dF
=
\frac{\partial F}{\partial q^i}\,dq^i.
$$

For a field functional, the discrete label $i$ becomes a combined label $(i,x)$, where $i$ names the field component and $x$ is a point of spacetime or space. The finite sum becomes an integral:

$$
\delta F
=
\int_M d\mu_x\,
\frac{\delta F}{\delta\phi^i(x)}\,\delta\phi^i(x).
$$

This is not just notation. It says that $\delta F/\delta\phi^i(x)$ is the kernel representing the linear map

$$
\eta\mapsto D F[\phi](\eta).
$$

If $D F[\phi](\eta)$ depends on $\eta$ only through $\eta(x_0)$, then the kernel is a delta function. If it depends on derivatives of $\eta$, integration by parts may produce derivatives of delta functions or boundary terms. If the variation is not continuous in the chosen topology, there may be no functional derivative in the naive sense.

For most QFT calculations, the working rule is:

$$
\text{compute }\delta F,\quad
\text{move derivatives off }\delta\phi\text{ when appropriate},\quad
\text{read off the coefficient of }\delta\phi.
$$

The words “when appropriate” carry the boundary conditions. Boundary terms are not automatically zero; they are zero only for the class of allowed variations or after the functional has been modified by boundary terms.

## Setup and conventions

Let $M$ be the space or spacetime region on which the fields live. We write $d\mu_x$ for the measure used in the variational pairing. In flat coordinates this is often $d^dx$. On a Riemannian or Lorentzian manifold it may be $\sqrt{|g|}\,d^dx$.

For fields $\phi^i(x)$ and variations $\eta^i(x)$, the first variation is

$$
D F[\phi](\eta)
=
\left.\frac{d}{d\epsilon}F[\phi+\epsilon\eta]\right|_{\epsilon=0}.
$$

If there exists an object $K_i(x)$ such that

$$
D F[\phi](\eta)=\int_M d\mu_x\,K_i(x)\eta^i(x)
$$

for all allowed variations $\eta$, then

$$
K_i(x)=\frac{\delta F}{\delta\phi^i(x)}.
$$

The delta distribution associated with $d\mu$ is defined by

$$
\int_M d\mu_y\,\delta_\mu(x,y)f(y)=f(x).
$$

If $d\mu_y=\rho(y)d^dy$, then

$$
\delta_\mu(x,y)=\frac{\delta^{(d)}(x-y)}{\rho(y)}
$$

in local coordinates. Thus the symbol $\delta^{(d)}(x-y)$ is not quite the whole story on a curved background. The measure decides which kernel represents the identity.

With this convention,

$$
\frac{\delta\phi^j(y)}{\delta\phi^i(x)}
=
\delta_i{}^j\delta_\mu(x,y).
$$

When the coordinate measure $d^dx$ is used instead, the same derivative is written with $\delta^{(d)}(x-y)$. Both notations are fine as long as the pairing is clear.

## First examples

The source functional

$$
F[\phi]=\int_M d\mu_x\,J_i(x)\phi^i(x)
$$

has variation

$$
\delta F=\int_M d\mu_x\,J_i(x)\delta\phi^i(x),
$$

so

$$
\frac{\delta F}{\delta\phi^i(x)}=J_i(x).
$$

A point-evaluation functional,

$$
F[\phi]=\phi^j(y),
$$

has variation

$$
\delta F=\eta^j(y)
=
\int_M d\mu_x\,\delta_i{}^j\delta_\mu(x,y)\eta^i(x),
$$

so

$$
\frac{\delta\phi^j(y)}{\delta\phi^i(x)}
=
\delta_i{}^j\delta_\mu(x,y).
$$

For a local potential functional

$$
F[\phi]=\int_M d\mu_x\,V(\phi(x)),
$$

the variation is

$$
\delta F=\int_M d\mu_x\,V'(\phi(x))\delta\phi(x),
$$

and therefore

$$
\frac{\delta F}{\delta\phi(x)}=V'(\phi(x)).
$$

For a quadratic nonlocal functional

$$
F[\phi]
=
\frac12\int_M d\mu_x\,d\mu_y\,\phi(x)K(x,y)\phi(y),
$$

the variation gives

$$
\frac{\delta F}{\delta\phi(z)}
=
\frac12\int_M d\mu_y\,\bigl(K(z,y)+K(y,z)\bigr)\phi(y).
$$

Only the symmetric part of the kernel contributes for an ordinary real bosonic field. If $K$ is self-adjoint with respect to $d\mu$, this becomes simply

$$
\frac{\delta F}{\delta\phi(z)}
=
\int_M d\mu_y\,K(z,y)\phi(y).
$$

That is the finite-dimensional statement $\partial(\frac12 q^TAq)/\partial q=A_{\mathrm{sym}}q$ in field clothing.

## Derivatives of fields and integration by parts

Derivative terms are where the functional derivative starts to earn its rent. Consider the Euclidean-looking functional

$$
F[\phi]=\frac12\int_M d^dx\,\partial_\mu\phi\,\partial^\mu\phi.
$$

Its variation is

$$
\delta F
=
\int_M d^dx\,\partial_\mu\phi\,\partial^\mu\delta\phi.
$$

If variations are compactly supported, or if boundary terms vanish for the allowed variations, integration by parts gives

$$
\delta F
=
-\int_M d^dx\,(\partial_\mu\partial^\mu\phi)\delta\phi.
$$

Therefore

$$
\frac{\delta F}{\delta\phi(x)}
=
-\partial_\mu\partial^\mu\phi(x).
$$

But the full variation before imposing boundary behavior is

$$
\delta F
=
-\int_M d^dx\,(\partial_\mu\partial^\mu\phi)\delta\phi
+
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\,\delta\phi.
$$

The bulk functional derivative is not the whole first variation unless the boundary term has been dealt with.

Equivalently, before integrating over the point $y$, one may write the local identity

$$
\frac{\delta(\partial_\mu\phi(y))}{\delta\phi(x)}
=
\partial_{y^\mu}\delta^{(d)}(y-x).
$$

Derivatives of delta functions are normal. They are the distributional way of saying that the functional depends on derivatives of the field.

## Functional derivatives of local actions

For a local first-derivative action

$$
S[\phi]=\int_M d^dx\,\mathcal L(\phi^i,\partial_\mu\phi^i),
$$

the raw variation is

$$
\delta S
=
\int_M d^dx\,
\left(
\frac{\partial\mathcal L}{\partial\phi^i}\delta\phi^i
+
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}\partial_\mu\delta\phi^i
\right).
$$

After integrating by parts,

$$
\delta S
=
\int_M d^dx\,
\left(
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}
\right)\delta\phi^i
+
\int_{\partial M}\theta.
$$

Thus, for allowed variations that remove the boundary term,

$$
\frac{\delta S}{\delta\phi^i(x)}
=
\frac{\partial\mathcal L}{\partial\phi^i}
-
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^i)}.
$$

The expression on the right is the Euler–Lagrange operator. The next page, [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/), develops this systematically, including higher derivatives and boundary currents.

## Second functional derivatives and Hessian kernels

The second functional derivative is the continuum Hessian. If

$$
\delta F
=
\int d\mu_x\,F_i^{(1)}(x)\delta\phi^i(x),
$$

then

$$
\delta F_i^{(1)}(x)
=
\int d\mu_y\,F^{(2)}_{ij}(x,y)\delta\phi^j(y),
$$

where

$$
F^{(2)}_{ij}(x,y)
=
\frac{\delta^2 F}{\delta\phi^i(x)\delta\phi^j(y)}.
$$

For bosonic variables, a sufficiently regular second derivative is symmetric in the combined labels:

$$
F^{(2)}_{ij}(x,y)=F^{(2)}_{ji}(y,x),
$$

up to boundary terms and domain questions. This kernel is central in QFT. Expanding an action around a saddle $\phi_{\rm cl}$ gives

$$
S[\phi_{\rm cl}+\eta]
=
S[\phi_{\rm cl}]
+
\frac12\int d\mu_xd\mu_y\,
\eta^i(x)
\left.
\frac{\delta^2S}{\delta\phi^i(x)\delta\phi^j(y)}
\right|_{\phi_{\rm cl}}
\eta^j(y)
+
\cdots,
$$

provided the first variation vanishes for allowed variations. The inverse of this Hessian, after gauge fixing and boundary conditions when needed, is the propagator or Green kernel used in perturbation theory.

## Source differentiation in generating functionals

Functional derivatives with respect to sources are the cleanest way to generate correlation functions. With Lorentzian source convention

$$
Z[J]
=
\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^dx\,J(x)\phi(x)\right),
$$

we get

$$
\frac{1}{i}\frac{\delta Z[J]}{\delta J(x)}
=
\int\mathcal D\phi\,\phi(x)
\exp\left(iS[\phi]+i\int d^dx\,J\phi\right).
$$

Repeated source differentiation inserts repeated fields:

$$
\frac{1}{i^n}\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}
=
\int\mathcal D\phi\,\phi(x_1)\cdots\phi(x_n)e^{iS+i\int J\phi}.
$$

For the connected generating functional $W[J]=-i\log Z[J]$, one has

$$
\frac{\delta W[J]}{\delta J(x)}
=
\langle\phi(x)\rangle_J.
$$

Euclidean conventions differ by signs depending on whether the source is included as $-\int J\phi$ or $+\int J\phi$ in the exponent. The structural point is invariant: source derivatives insert fields because the source couples linearly to the field.

This is the same functional derivative as before, now applied to the source $J$ rather than to the dynamical field $\phi$.

## Complex fields and independent variables

For a complex field, the default QFT convention is to treat $\phi$ and $\phi^*$ as independent variables during variation. For example,

$$
F[\phi,\phi^*]
=
\int d^dx\,\phi^*(x)K\phi(x)
$$

has

$$
\frac{\delta F}{\delta\phi^*(x)}=(K\phi)(x),
$$

and, after moving derivatives in $K$ by integration by parts as needed,

$$
\frac{\delta F}{\delta\phi(x)}=(K^\dagger\phi^*)(x).
$$

Only after deriving the equations or identities should one impose relations such as complex conjugation, reality conditions, Majorana conditions, or Euclidean-continuation constraints.

The same idea appears in finite-dimensional complex analysis: when a function is not holomorphic, $z$ and $\bar z$ are treated as independent variables for differentiation. In QFT this is not a trick; it is the clean way to obtain both equations of motion.

## Grassmann fields and left versus right derivatives

For Grassmann-odd variables, order matters. A fermionic variation $\delta\psi$ anticommutes with fermionic fields. One must specify whether derivatives act from the left or from the right.

A common convention defines left and right variational derivatives by

$$
\delta F
=
\int d\mu_x\,\delta\psi(x)\frac{\delta_L F}{\delta\psi(x)}
=
\int d\mu_x\,\frac{\delta_R F}{\delta\psi(x)}\delta\psi(x).
$$

For two odd variables $\psi_1,\psi_2$ and

$$
F=\psi_1\psi_2,
$$

the variation is

$$
\delta F=\delta\psi_1\psi_2+\psi_1\delta\psi_2
=\delta\psi_1\psi_2-\delta\psi_2\psi_1.
$$

Therefore the left derivatives are

$$
\frac{\delta_L F}{\delta\psi_1}=\psi_2,
\qquad
\frac{\delta_L F}{\delta\psi_2}=-\psi_1.
$$

Writing the same variation with $\delta\psi$ on the right gives

$$
\delta F=-\psi_2\delta\psi_1+\psi_1\delta\psi_2,
$$

so the right derivatives are

$$
\frac{\delta_R F}{\delta\psi_1}=-\psi_2,
\qquad
\frac{\delta_R F}{\delta\psi_2}=\psi_1.
$$

This is why fermionic path integrals, BRST transformations, BV antibrackets, and ghost actions are fussy about left and right derivatives. The signs are not decoration; they are the calculation.

## Chain rule and field redefinitions

Suppose $F$ depends on $\phi$ through another field variable $\chi[\phi]$. The chain rule is a kernel identity:

$$
\frac{\delta F}{\delta\phi^i(x)}
=
\int d\mu_y\,
\frac{\delta\chi^a(y)}{\delta\phi^i(x)}
\frac{\delta F}{\delta\chi^a(y)},
$$

with the order adjusted for Grassmann variables.

For a pointwise field redefinition

$$
\chi(x)=f(\phi(x)),
$$

one has

$$
\frac{\delta\chi(y)}{\delta\phi(x)}
=
f'(\phi(y))\delta_\mu(x,y),
$$

so

$$
\frac{\delta F}{\delta\phi(x)}
=
f'(\phi(x))\frac{\delta F}{\delta\chi(x)}.
$$

For a nonlocal field redefinition, such as

$$
\chi(x)=\int d\mu_y\,K(x,y)\phi(y),
$$

the chain rule keeps the full kernel:

$$
\frac{\delta F}{\delta\phi(y)}
=
\int d\mu_x\,K(x,y)\frac{\delta F}{\delta\chi(x)}.
$$

This is the same kernel that appears in Jacobians and measures. The derivative tells how variations transform; the determinant of the derivative tells how volume elements transform.

## Contact terms

When functional derivatives hit fields inside products, they produce delta functions. For example,

$$
\frac{\delta}{\delta\phi(x)}\bigl(\phi(y)\phi(z)\bigr)
=
\delta^{(d)}(y-x)\phi(z)+\phi(y)\delta^{(d)}(z-x).
$$

If $y$ or $z$ is later integrated against another distribution, these delta functions may become contact terms. In QFT, contact terms are terms supported when insertion points coincide. They are not automatically mistakes. Ward identities, Schwinger–Dyson equations, current conservation inside correlators, and operator product expansions all contain contact terms.

A good habit is to ask: is the identity meant away from coincident points, or as a distributional identity? The answer decides whether contact terms are present.

## Common pitfalls

**Treating $\delta F/\delta\phi(x)$ as an ordinary function.** Sometimes it is one, but often it is a distribution. The derivative of $\phi(y)$ with respect to $\phi(x)$ is a delta distribution, and derivative couplings produce derivatives of delta distributions.

**Forgetting the measure.** The expression $\delta^{(d)}(x-y)$ is tied to the coordinate measure $d^dx$. With an invariant measure $d\mu=\rho d^dx$, the identity kernel is $\delta_\mu(x,y)=\delta^{(d)}(x-y)/\rho(y)$.

**Dropping boundary terms before deciding the variational problem.** A functional derivative is defined relative to allowed variations. If the boundary term does not vanish for those variations, the bulk coefficient alone is not the derivative of the functional.

**Varying $\phi$ and $\partial_\mu\phi$ as if they were independent after the variation.** In the raw variation they appear separately, but $\delta(\partial_\mu\phi)=\partial_\mu\delta\phi$. The derivative on the variation must be integrated by parts before reading off the Euler–Lagrange derivative.

**Confusing source derivatives with field derivatives.** Differentiating $Z[J]$ with respect to $J$ inserts fields. Differentiating an action with respect to $\phi$ gives equations of motion. Same calculus, different variable.

**Ignoring left and right derivatives for fermions.** For Grassmann variables, moving $\delta\psi$ from one side to the other changes signs. Pick a convention and keep it visible.

## Relations to other pages

This page is the entry point for [Euler–Lagrange Operators](/math-toolkit/calculus-of-variations-and-phase-space/euler-lagrange-operators/), where the coefficient of $\delta\phi$ in a local action is computed systematically.

It also connects back to [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) and [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), because functional derivatives are distributional kernels. For path integrals, it connects to [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/), and [Jacobians and Measures](/math-toolkit/functional-integrals-determinants/jacobians-and-measures/).

Later pages on boundary terms, Legendre transforms, symplectic forms, Poisson brackets, and constraints use the same first variation but ask different questions of it.

## Research status

The formal rules in this page are established and used throughout classical field theory, perturbative QFT, statistical field theory, and path-integral methods.

The analytic foundations are more delicate. In infinite-dimensional spaces, the existence and continuity of $D F[\phi]$, the choice of test-function space, the topology on fields, the treatment of boundaries, and the definition of products of distributions can all matter. Gauge theories add another layer: variations along gauge orbits may be degenerate directions rather than physical directions.

For most QFT calculations, one works with regulated systems, compactly supported variations, or formal power series. For rigorous QFT, stochastic PDEs, constructive field theory, and geometric analysis, those choices must be sharpened.

## Exercises

### Exercise 1: Source derivative

Let

$$
F[J]=\exp\left(\int d^dx\,J(x)f(x)\right).
$$

Compute $\delta F/\delta J(y)$.

<details><summary><strong>Solution</strong></summary>

Vary $J\mapsto J+\epsilon K$:

$$
F[J+\epsilon K]
=
F[J]\exp\left(\epsilon\int d^dx\,K(x)f(x)\right).
$$

Therefore

$$
\delta F
=
F[J]\int d^dx\,f(x)\delta J(x),
$$

so

$$
\frac{\delta F}{\delta J(y)}=f(y)F[J].
$$

</details>

### Exercise 2: Local potential

For

$$
F[\phi]=\int d^dx\,\left(\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4\right),
$$

find $\delta F/\delta\phi(x)$.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta F
=
\int d^dx\,\left(m^2\phi+\frac{\lambda}{3!}\phi^3\right)\delta\phi.
$$

Thus

$$
\frac{\delta F}{\delta\phi(x)}
=
m^2\phi(x)+\frac{\lambda}{3!}\phi(x)^3.
$$

</details>

### Exercise 3: Quadratic kernel

Let

$$
F[\phi]=\frac12\int d^dx\,d^dy\,\phi(x)K(x,y)\phi(y).
$$

Show that the functional derivative depends only on the symmetric part of $K$.

<details><summary><strong>Solution</strong></summary>

Varying gives

$$
\delta F
=
\frac12\int d^dx\,d^dy\,
\delta\phi(x)K(x,y)\phi(y)
+
\frac12\int d^dx\,d^dy\,
\phi(x)K(x,y)\delta\phi(y).
$$

In the second term, rename $x\leftrightarrow y$:

$$
\delta F
=
\frac12\int d^dx\,d^dy\,
\delta\phi(x)K(x,y)\phi(y)
+
\frac12\int d^dx\,d^dy\,
\delta\phi(x)K(y,x)\phi(y).
$$

Therefore

$$
\frac{\delta F}{\delta\phi(x)}
=
\frac12\int d^dy\,\bigl(K(x,y)+K(y,x)\bigr)\phi(y).
$$

The antisymmetric part cancels.

</details>

### Exercise 4: Derivative term and boundary term

For

$$
F[\phi]=\frac12\int_M d^dx\,\partial_\mu\phi\partial^\mu\phi,
$$

compute the full first variation and identify the bulk functional derivative when $\delta\phi$ vanishes on $\partial M$.

<details><summary><strong>Solution</strong></summary>

The raw variation is

$$
\delta F
=
\int_M d^dx\,\partial_\mu\phi\partial^\mu\delta\phi.
$$

Integrating by parts,

$$
\delta F
=
-\int_M d^dx\,(\partial_\mu\partial^\mu\phi)\delta\phi
+
\int_{\partial M}d\Sigma_\mu\,\partial^\mu\phi\delta\phi.
$$

If $\delta\phi|_{\partial M}=0$, the boundary term vanishes and

$$
\frac{\delta F}{\delta\phi(x)}
=
-\partial_\mu\partial^\mu\phi(x).
$$

</details>

### Exercise 5: Grassmann sign check

Let $\psi_1,\psi_2,\psi_3$ be Grassmann-odd variables and

$$
F=\psi_1\psi_2\psi_3.
$$

Find the left derivative $\delta_LF/\delta\psi_2$.

<details><summary><strong>Solution</strong></summary>

Vary only $\psi_2$:

$$
\delta F=\psi_1\delta\psi_2\psi_3.
$$

To write this in the left-derivative convention, move $\delta\psi_2$ to the left. Since $\psi_1$ is odd,

$$
\psi_1\delta\psi_2\psi_3
=
-\delta\psi_2\psi_1\psi_3.
$$

Thus

$$
\frac{\delta_LF}{\delta\psi_2}
=-\psi_1\psi_3.
$$

</details>

## References

- I. M. Gelfand and S. V. Fomin, *Calculus of Variations*. Classical reference for variational derivatives and Euler–Lagrange equations.
- L. C. Evans, *Partial Differential Equations*. Useful for weak derivatives, distributions, and variational methods in PDE language.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. I. Functional-analytic background for linear operators and distributions.
- P. J. Olver, *Applications of Lie Groups to Differential Equations*. Jet-space and variational-calculus treatment of Euler operators and symmetries.
- M. Srednicki, *Quantum Field Theory*. Practical use of functional derivatives in path integrals, sources, and perturbation theory.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Source differentiation, path integrals, Schwinger–Dyson equations, and Ward identities.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II. Functional methods, variational principles, sources, and gauge-theory applications.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, generating functionals, and field-theoretic variational calculus.

## Version history

- 2026-06-24: First polished draft. Defined variational derivatives as distributional field-space gradients, fixed measure conventions, worked examples, source differentiation, Hessian kernels, Grassmann signs, contact terms, and exercises.
