---
title: "Boundary-Value Problems"
description: "Explains how boundary conditions define operators, spectra, Green kernels, self-adjointness, Fredholm alternatives, and QFT boundary physics."
sidebar:
  label: "Boundary-Value Problems"
  order: 4
level: Graduate
status: "Polished draft"
source: "Standard references on PDE, elliptic boundary-value problems, spectral theory, and mathematical physics, including Evans, Folland, Taylor, Courant–Hilbert, Gilkey, Grubb, Reed–Simon, Teschl, and QFT treatments of Green functions, Casimir problems, gauge fixing, and boundary degrees of freedom."
topics:
  - boundary-value problems
  - boundary conditions
  - operator domains
  - Green functions
  - self-adjointness
  - Fredholm alternative
  - elliptic operators
  - Robin boundary conditions
  - zero modes
  - Casimir effect
  - gauge boundary conditions
canonicalTopics:
  - boundary-value-problem
  - boundary-condition
  - operator-domain
  - green-function
  - self-adjointness
  - fredholm-alternative
  - elliptic-operator
  - robin-boundary-condition
  - zero-mode
  - casimir-effect
  - gauge-boundary-condition
researchStatus:
  established:
    - "Boundary conditions and domains are part of the definition of a differential operator; they determine spectra, Green functions, self-adjointness, zero modes, and variational well-posedness."
  active:
    - "Gauge theories, gravitational theories, corners, edge modes, anomalies, Lorentzian boundaries, nonlocal boundary conditions, and singular boundaries remain active sources of subtle mathematical and physical questions."
---

## Summary

A boundary-value problem is not a differential equation plus some optional fine print. It is the complete object:

$$
\text{differential expression} + \text{domain} + \text{boundary condition}.
$$

The same local expression can define different operators depending on the boundary condition. Those operators can have different spectra, different Green functions, different determinants, different zero modes, and different quantum theories.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing differential expression plus domain and boundary condition becoming an operator with spectrum, Green kernel, determinant, and QFT boundary interpretation.](/figures/math-toolkit/boundary-value-problem-operator-flow.svg)

<figcaption>

A boundary-value problem turns a local differential expression into a global operator. The boundary condition fixes the domain; the domain controls adjoints, self-adjointness, spectra, Green kernels, zero modes, determinants, and the allowed boundary terms in the variational principle.

</figcaption>
</figure>

In QFT, this is not pedantry. Boundary conditions appear in finite volume, finite temperature, Casimir energies, defects, branes, bags, solitons, AdS/CFT, gauge fixing, edge modes, and anomalies. Even in infinite space, pole prescriptions act like boundary conditions in time or in complex momentum space.

The slogan is:

$$
\text{There is no Green function until there is a problem to invert.}
$$

## Prerequisites

You should know [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Partial Differential Equations](/math-toolkit/differential-equations-green-functions/partial-differential-equations/), and [Elliptic, Hyperbolic, and Parabolic Equations](/math-toolkit/differential-equations-green-functions/elliptic-hyperbolic-parabolic/). You should also be comfortable with [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), [Compact Operators](/math-toolkit/functional-analysis-spectral-theory/compact-operators/), and [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/).

This page focuses on the conceptual and computational boundary-value toolkit. Sturm–Liouville theory, Green functions, heat kernels, and wave equations are developed in later pages.

## Differential expression versus operator

The expression

$$
-\frac{d^2}{dx^2}
$$

is local. It tells you what to do to a sufficiently differentiable function near each point. It is not yet a self-adjoint operator on $L^2([0,L])$.

To define an operator, one must specify a domain. For example:

$$
D_D=\{u\in H^2([0,L]):u(0)=u(L)=0\}
$$

defines the Dirichlet Laplacian,

$$
A_Du=-u''.
$$

The Neumann domain

$$
D_N=\{u\in H^2([0,L]):u'(0)=u'(L)=0\}
$$

defines a different operator,

$$
A_Nu=-u''.
$$

The formula is the same. The operator is not.

The spectra already show the difference. On $[0,L]$, the Dirichlet eigenvalues are

$$
\lambda_n^{(D)}=\left(\frac{n\pi}{L}\right)^2,
\qquad n=1,2,3,\ldots,
$$

whereas the Neumann eigenvalues are

$$
\lambda_n^{(N)}=\left(\frac{n\pi}{L}\right)^2,
\qquad n=0,1,2,\ldots.
$$

The Neumann operator has a zero mode: the constant function. That one extra $n=0$ mode changes inverses, determinants, Gaussian path integrals, and infrared behavior.

## Boundary conditions as domain conditions

Common local boundary conditions for a scalar field on a domain $\Omega$ are:

| Name | Boundary condition | Typical meaning |
|---|---|---|
| Dirichlet | $u|_{\partial\Omega}=g$ | fixed field value |
| Neumann | $\partial_n u|_{\partial\Omega}=h$ | fixed normal derivative or flux |
| Robin | $(\partial_n+\alpha)u|_{\partial\Omega}=r$ | mixed value–flux condition |
| periodic | values and derivatives match | compactification or finite-temperature circle |
| mixed | different conditions on different boundary pieces | interfaces, plates, bags, branes |

Here $\partial_n$ is the outward normal derivative. The outward normal convention matters. On an interval $[0,L]$,

$$
\partial_n u(0)=-u'(0),
\qquad
\partial_n u(L)=u'(L).
$$

A homogeneous boundary condition defines a linear domain. An inhomogeneous boundary condition defines an affine space of functions. For spectral theory and operator inverses, one usually builds the operator using homogeneous boundary conditions and treats inhomogeneous boundary data separately by lifting the boundary values.

## The boundary form from integration by parts

Boundary conditions are often found by looking at integration by parts. Let

$$
A=-\frac{d^2}{dx^2}+V(x)
$$

on $[0,L]$, with real $V$. Using the inner product

$$
\langle u,v\rangle=\int_0^L dx\,\overline{u(x)}v(x),
$$

one finds

$$
\langle u,Av\rangle-\langle Au,v\rangle
=
\left[-\overline u v'+\overline{u'}v\right]_0^L.
$$

The right-hand side is the boundary form. Boundary conditions that make it vanish for all $u,v$ in the domain make the operator symmetric. In regular one-dimensional examples, the standard real separated boundary conditions also give self-adjoint operators.

This boundary form is the same mathematical object that appears in the variation of an action. For a scalar field with action

$$
S[\phi]=\frac12\int_\Omega d^dx\,\left[(\nabla\phi)^2+m^2\phi^2\right],
$$

variation gives

$$
\delta S
=\int_\Omega d^dx\,\delta\phi(-\Delta+m^2)\phi
+\int_{\partial\Omega}d\Sigma\,\delta\phi\,\partial_n\phi.
$$

A variational principle is well posed only after the boundary term is controlled. Dirichlet boundary conditions set $\delta\phi|_{\partial\Omega}=0$. Neumann boundary conditions set $\partial_n\phi|_{\partial\Omega}$ to prescribed data. Robin conditions arise when one adds boundary terms to the action.

## Self-adjointness and spectra

Self-adjointness is the condition that lets a differential operator behave like an observable or a stable quadratic Hamiltonian. For an operator $A$, symmetry means

$$
\langle u,Av\rangle=\langle Au,v\rangle
\qquad
u,v\in D(A).
$$

Self-adjointness means, in addition, that

$$
D(A)=D(A^*).
$$

That domain equality is the part students are tempted to skip. It is also the part that prevents hidden boundary degrees of freedom from sneaking in through the adjoint.

For positive self-adjoint elliptic operators on compact domains, one often gets a discrete spectrum

$$
0\le \lambda_0\le \lambda_1\le\lambda_2\le\cdots,
\qquad
\lambda_n\to\infty,
$$

with an orthonormal basis of eigenfunctions. Then kernels can be written spectrally, for example

$$
K(s;x,y)=\sum_n e^{-s\lambda_n}u_n(x)\overline{u_n(y)},
$$

and, if there are no zero modes,

$$
G(x,y)=\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n}.
$$

If there are zero modes, the second formula must be modified by projecting them out or by adding a small regulator.

## Fredholm alternative and zero modes

The Fredholm alternative is the clean version of a common QFT headache: an equation may not be solvable unless the source is orthogonal to zero modes.

Suppose $A$ is self-adjoint and has a nontrivial kernel. To solve

$$
Au=f,
$$

one must have

$$
\langle z,f\rangle=0
\qquad
\text{for every }z\in\ker A.
$$

If this condition holds, the solution is not unique: one can add any zero mode.

The simplest example is the Neumann Laplacian on a connected bounded region:

$$
-\Delta u=f,
\qquad
\partial_n u|_{\partial\Omega}=0.
$$

The zero modes are constants. Integrating over $\Omega$ and using the divergence theorem gives

$$
\int_\Omega d^dx\,f
=\int_\Omega d^dx\,(-\Delta u)
=-\int_{\partial\Omega}d\Sigma\,\partial_n u
=0.
$$

Thus the source must have zero average. If a solution exists, it is unique only up to adding a constant.

In QFT, the same structure appears in collective coordinates, gauge zero modes, Goldstone modes, instanton moduli, and finite-volume massless fields. Zero modes are not a nuisance variable. They are usually where the physics lives.

## Green functions with boundary conditions

A Green function for a boundary-value problem solves

$$
L_xG(x,y)=\delta(x-y)
$$

and satisfies the boundary condition in the $x$ variable. If the operator is self-adjoint, the kernel often has the symmetry

$$
G(x,y)=\overline{G(y,x)}.
$$

But the boundary condition is essential. On an interval, the Green function for

$$
-u''=f
$$

with Dirichlet boundary conditions is not the same as the Green function with Neumann boundary conditions. In the Neumann case, one must also handle the constant zero mode.

A useful construction is:

1. Find a local fundamental solution, which has the right singularity at $x=y$.
2. Add a homogeneous solution to enforce boundary conditions.
3. Check zero-mode solvability.

This is exactly what image-charge methods do in electrostatics. The image charges are not magic; they are homogeneous corrections designed to enforce boundary data.

## Elliptic boundary problems

For elliptic equations, boundary conditions must be compatible with the operator. A second-order scalar elliptic equation usually needs one scalar boundary condition at each boundary point: Dirichlet, Neumann, Robin, or a suitable mixture.

For higher-order operators, systems, or gauge theories, compatibility is more delicate. The boundary conditions must make the problem well posed and, for many spectral applications, elliptic as a boundary problem. In advanced treatments this is encoded in complementing conditions such as the Lopatinski–Shapiro condition.

For this page, the practical rule is enough:

$$
\text{elliptic operator} + \text{bad boundary condition}
\quad\Rightarrow\quad
\text{bad inverse}.
$$

One may lose uniqueness, existence, regularity, discreteness of spectrum, or self-adjointness.

## Hyperbolic initial-boundary problems

Hyperbolic equations naturally use initial data. On a spacetime region with timelike boundaries, however, one often needs an initial-boundary value problem. For example, a wave equation in a cavity needs initial data at $t=0$ and boundary conditions on the walls.

The boundary condition must not inject unphysical energy unless that is intended. For the wave equation on a spatial region $\Omega$,

$$
\partial_t^2u-\Delta u=0,
$$

the energy is

$$
E(t)=\frac12\int_\Omega d^dx\,\left[(\partial_tu)^2+|\nabla u|^2\right].
$$

Differentiating and integrating by parts gives a boundary flux term:

$$
\frac{dE}{dt}=\int_{\partial\Omega}d\Sigma\,\partial_tu\,\partial_n u.
$$

Dirichlet conditions with fixed boundary value, Neumann conditions with zero normal derivative, and suitable reflecting boundary conditions can make the energy flux vanish. Absorbing or radiative boundary conditions deliberately allow energy to leave.

For Lorentzian QFT, this is where boundary conditions meet unitarity and causality. Boundary conditions are part of the definition of the theory.

## Boundary conditions in QFT examples

### Finite volume and compactification

Putting a field on a circle of length $L$ imposes periodic boundary conditions:

$$
\phi(x+L)=\phi(x).
$$

The momenta become discrete:

$$
p_n=\frac{2\pi n}{L}.
$$

For fermions at finite temperature in Euclidean time, the thermal circle has antiperiodic boundary conditions,

$$
\psi(\tau+\beta)=-\psi(\tau),
$$

leading to fermionic Matsubara frequencies. Boundary conditions encode the trace and statistics.

### Casimir problems

Casimir energies depend on spectra, and spectra depend on boundary conditions. Dirichlet plates, Neumann plates, electromagnetic conductor conditions, and Robin plates give different mode sums and different renormalized energies. The local operator alone does not determine the answer.

### Bag and brane boundary conditions

Spinor fields require boundary conditions compatible with the Dirac operator and the desired flux properties. Bag boundary conditions are designed to make normal fermion current vanish at the boundary. Brane models and defects similarly encode physical boundary degrees of freedom through boundary conditions or boundary actions.

### AdS boundary conditions

In anti-de Sitter space, fields have asymptotic boundary behavior. Different admissible boundary conditions can correspond to different dual CFT data. For scalar fields in a suitable mass window, standard and alternate quantization are distinct choices of boundary condition.

### Gauge theory and edge modes

Gauge theory on a region has an extra subtlety: gauge transformations that do not vanish at the boundary may become physical boundary symmetries. The boundary condition must be compatible with gauge fixing, Gauss constraints, and possible edge degrees of freedom. This is why gauge theories with boundaries are so good at producing both headaches and interesting physics. A suspiciously reliable combo.

## Boundary terms and the variational principle

A classical field equation obtained from an action is not fully defined until the allowed variations are specified. Suppose the variation has the form

$$
\delta S
=\int_\Omega E(\phi)\delta\phi+
\int_{\partial\Omega}\Theta(\phi,\delta\phi).
$$

The bulk equation is

$$
E(\phi)=0.
$$

But the variational principle also requires the boundary term to vanish or be canceled. One may fix boundary values, impose natural boundary conditions, add boundary counterterms or boundary actions, or enlarge the system by adding boundary degrees of freedom.

This point is central in gauge theory and gravity. The correct boundary term is often what makes the variational problem, symplectic form, and conserved charges well defined.

## Common pitfalls

**Pitfall 1: Saying “the Laplacian” without specifying the domain.** On a domain with boundary, there are many Laplacians. Dirichlet, Neumann, Robin, periodic, and mixed conditions define different operators.

**Pitfall 2: Treating inhomogeneous boundary data as an operator domain.** Linear operators usually use homogeneous boundary conditions. Inhomogeneous boundary values are handled by adding a particular lift.

**Pitfall 3: Ignoring zero modes in determinants.** If $A$ has zero modes, $\det A=0$ and $A^{-1}$ does not exist on the full space. One must project, regulate, or integrate over collective coordinates.

**Pitfall 4: Confusing symmetric with self-adjoint.** Vanishing boundary form shows symmetry. Self-adjointness also requires the adjoint domain to match.

**Pitfall 5: Using the wrong normal derivative sign.** Robin and Neumann conditions use the outward normal derivative. On an interval, the signs at the two endpoints differ.

**Pitfall 6: Forgetting boundary degrees of freedom in gauge theory.** Gauge transformations at the boundary can become physical symmetries. “Set it to zero at the boundary” is a choice, not a theorem.

## Exercises

### Exercise 1: Boundary form for the one-dimensional Laplacian

Let

$$
A=-\frac{d^2}{dx^2}
$$

on $[0,L]$ with inner product

$$
\langle u,v\rangle=\int_0^L dx\,\overline u v.
$$

Show that

$$
\langle u,Av\rangle-\langle Au,v\rangle
=\left[-\overline u v'+\overline{u'}v\right]_0^L.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
\langle u,Av\rangle
=\int_0^L dx\,\overline u(-v'').
$$

Integrating by parts once gives

$$
\int_0^L dx\,\overline u(-v'')
=\left[-\overline u v'\right]_0^L
+\int_0^L dx\,\overline{u'}v'.
$$

Similarly,

$$
\langle Au,v\rangle
=\int_0^L dx\,(-\overline{u''})v
=\left[-\overline{u'}v\right]_0^L
+\int_0^L dx\,\overline{u'}v'.
$$

Subtracting gives

$$
\langle u,Av\rangle-\langle Au,v\rangle
=\left[-\overline u v'+\overline{u'}v\right]_0^L.
$$

</details>

### Exercise 2: Dirichlet and Neumann spectra on an interval

Find the eigenvalues of

$$
-u''=\lambda u
$$

on $[0,L]$ for Dirichlet boundary conditions and for Neumann boundary conditions.

<details><summary><strong>Solution</strong></summary>

For $\lambda=k^2>0$, the general solution is

$$
u(x)=A\cos kx+B\sin kx.
$$

For Dirichlet conditions,

$$
u(0)=u(L)=0.
$$

The condition $u(0)=0$ gives $A=0$. Then $u(L)=0$ gives

$$
B\sin kL=0.
$$

Nonzero solutions require

$$
kL=n\pi,
\qquad n=1,2,3,\ldots.
$$

Thus

$$
\lambda_n^{(D)}=\left(\frac{n\pi}{L}\right)^2,
\qquad n\ge1.
$$

For Neumann conditions,

$$
u'(0)=u'(L)=0.
$$

Since

$$
u'(x)=-Ak\sin kx+Bk\cos kx,
$$

the condition $u'(0)=0$ gives $B=0$. Then $u'(L)=0$ gives

$$
-Ak\sin kL=0.
$$

For $k>0$, this gives $kL=n\pi$ with $n=1,2,3,\ldots$. There is also a zero mode with $k=0$, namely a constant function. Therefore

$$
\lambda_n^{(N)}=\left(\frac{n\pi}{L}\right)^2,
\qquad n=0,1,2,3,\ldots.
$$

</details>

### Exercise 3: Neumann solvability condition

Let $\Omega$ be a connected bounded region. Show that the Neumann problem

$$
-\Delta u=f,
\qquad
\partial_n u|_{\partial\Omega}=0
$$

requires

$$
\int_\Omega d^dx\,f=0.
$$

<details><summary><strong>Solution</strong></summary>

Integrate the equation over $\Omega$:

$$
\int_\Omega d^dx\,f
=\int_\Omega d^dx\,(-\Delta u).
$$

Using the divergence theorem,

$$
\int_\Omega d^dx\,\Delta u
=\int_{\partial\Omega}d\Sigma\,\partial_n u.
$$

The Neumann condition says $\partial_n u=0$ on $\partial\Omega$, so

$$
\int_\Omega d^dx\,f
=-\int_{\partial\Omega}d\Sigma\,\partial_n u=0.
$$

Thus zero average is necessary. It is also the Fredholm solvability condition because constants are zero modes of the Neumann Laplacian.

</details>

### Exercise 4: Robin boundary condition from a boundary action

Consider the Euclidean scalar action on $\Omega$,

$$
S[\phi]=\frac12\int_\Omega d^dx\,\left[(\nabla\phi)^2+m^2\phi^2\right]
+\frac12\int_{\partial\Omega}d\Sigma\,\alpha\phi^2.
$$

Show that free variations give the Robin boundary condition

$$
(\partial_n+\alpha)\phi|_{\partial\Omega}=0.
$$

<details><summary><strong>Solution</strong></summary>

Varying the bulk term gives

$$
\delta S_{\mathrm{bulk}}
=\int_\Omega d^dx\,\delta\phi(-\Delta+m^2)\phi
+\int_{\partial\Omega}d\Sigma\,\delta\phi\,\partial_n\phi.
$$

Varying the boundary term gives

$$
\delta S_{\mathrm{bdry}}
=\int_{\partial\Omega}d\Sigma\,\alpha\phi\delta\phi.
$$

The total boundary variation is

$$
\int_{\partial\Omega}d\Sigma\,\delta\phi(\partial_n\phi+\alpha\phi).
$$

For arbitrary boundary variations $\delta\phi$, this vanishes only if

$$
(\partial_n+\alpha)\phi|_{\partial\Omega}=0.
$$

</details>

### Exercise 5: Energy flux for the wave equation

Let $u$ solve

$$
\partial_t^2u-\Delta u=0
$$

on a spatial region $\Omega$. Show that

$$
E(t)=\frac12\int_\Omega d^dx\,\left[(\partial_tu)^2+|\nabla u|^2\right]
$$

satisfies

$$
\frac{dE}{dt}=\int_{\partial\Omega}d\Sigma\,\partial_tu\,\partial_n u.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the energy:

$$
\frac{dE}{dt}
=\int_\Omega d^dx\,\left[\partial_tu\,\partial_t^2u+\nabla u\cdot\nabla\partial_tu\right].
$$

Integrate the second term by parts:

$$
\int_\Omega \nabla u\cdot\nabla\partial_tu
=\int_{\partial\Omega}d\Sigma\,\partial_tu\,\partial_n u
-\int_\Omega d^dx\,\partial_tu\,\Delta u.
$$

Therefore

$$
\frac{dE}{dt}
=\int_\Omega d^dx\,\partial_tu(\partial_t^2u-\Delta u)
+\int_{\partial\Omega}d\Sigma\,\partial_tu\,\partial_n u.
$$

Using the wave equation, the bulk term vanishes, leaving

$$
\frac{dE}{dt}=\int_{\partial\Omega}d\Sigma\,\partial_tu\,\partial_n u.
$$

</details>

## References

For boundary-value problems and elliptic theory, see Evans, *Partial Differential Equations*; Folland, *Introduction to Partial Differential Equations*; Taylor, *Partial Differential Equations*; Courant and Hilbert, *Methods of Mathematical Physics*; Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*; and Grubb, *Functional Calculus of Pseudodifferential Boundary Problems*. For operator domains, self-adjointness, spectra, and resolvents, see Reed and Simon, *Methods of Modern Mathematical Physics* and Teschl, *Mathematical Methods in Quantum Mechanics*. For QFT applications, compare standard discussions of finite volume, finite temperature, Casimir problems, Green functions, gauge fixing, zero modes, and boundary terms in Srednicki, Zee, Weinberg, Coleman, Schwartz, Zinn-Justin, Altland–Simons, Fradkin, Marino, Shifman, and Burgess.

## Version history

- 2026-06-25: Initial polished draft.
