---
title: "Green Functions"
description: "Explains Green functions as distributional inverse kernels, including boundary conditions, weights, jump conditions, spectral expansions, resolvents, pole prescriptions, zero modes, and QFT propagators."
sidebar:
  label: "Green Functions"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard references on Green functions, PDEs, spectral theory, scattering theory, and QFT propagators, including Courant–Hilbert, Morse–Feshbach, Folland, Evans, Reed–Simon, Teschl, Taylor, Itzykson–Zuber, Weinberg, Srednicki, Schwartz, Zee, and mathematical-physics treatments of resolvents and heat kernels."
topics:
  - Green functions
  - propagators
  - inverse kernels
  - fundamental solutions
  - resolvents
  - boundary conditions
  - pole prescriptions
  - spectral expansions
  - zero modes
  - distributional kernels
  - heat kernels
  - retarded response
canonicalTopics:
  - green-function
  - propagator
  - inverse-kernel
  - fundamental-solution
  - resolvent
  - boundary-condition
  - pole-prescription
  - spectral-expansion
  - zero-mode
  - distributional-kernel
  - heat-kernel
  - retarded-response
researchStatus:
  established:
    - "A Green function is the distributional kernel of an inverse or resolvent once the operator, domain, measure, boundary condition, and prescription have been specified."
  active:
    - "Green functions on singular spaces, gauge theories with boundaries, non-self-adjoint problems, Lorentzian curved spacetimes, real-time finite-temperature formalisms, and nonperturbative spectral reconstructions remain active research topics."
---

## Summary

A Green function is an inverse written as a kernel. For a linear operator $L$, a Green function $G(x,y)$ is supposed to solve

$$
L_xG(x,y)=\delta(x-y),
$$

so that the solution of

$$
Lu=f
$$

can be written as

$$
u(x)=\int dy\,G(x,y)f(y).
$$

That slogan is useful but incomplete. A Green function is not determined by the local differential expression alone. One must also specify the domain, boundary conditions, measure, zero-mode treatment, and, in Lorentzian problems, a pole or support prescription.

<figure class="doc-figure" style="--figure-width: 47rem;">

![Flow diagram showing an operator problem becoming a Green kernel, then a solution map, with boundary or pole prescription, singularity at the diagonal, spectral form, proper-time representation, zero modes, and QFT interpretation.](/figures/math-toolkit/green-function-inverse-kernel.svg)

<figcaption>

A Green function is an inverse kernel, not just a formula with a delta function. Boundary conditions or pole prescriptions select the inverse; the diagonal singularity produces the delta source; spectral, heat-kernel, and zero-mode treatments give complementary ways to compute and interpret it.

</figcaption>
</figure>

In QFT the word *Green function* is used in several closely related ways. It can mean a classical response kernel, a Euclidean inverse, a retarded or advanced propagator, a Feynman propagator, a time-ordered correlation function, or a many-point correlation function. These meanings overlap, but they are not identical. The whole point of this page is to stop the word from becoming fog wearing a hat.

## Prerequisites

You should know [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/), and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/).

The default spacetime convention is mostly-minus metric and plane waves $e^{-ip\cdot x}$, as fixed in [Conventions for Mathematics](/math-toolkit/conventions/).

## Inverse operators and kernels

Let $L$ be a linear operator on functions over a space $X$ with measure $d\mu(x)$. If $L^{-1}$ exists and has kernel $G(x,y)$, then

$$
[L^{-1}f](x)=\int_X d\mu(y)\,G(x,y)f(y).
$$

Applying $L$ to both sides gives

$$
f(x)=\int_X d\mu(y)\,L_xG(x,y)f(y).
$$

Therefore the kernel must satisfy

$$
L_xG(x,y)=\delta_\mu(x,y),
$$

where $\delta_\mu$ is the delta distribution for the measure $d\mu$:

$$
f(x)=\int_X d\mu(y)\,\delta_\mu(x,y)f(y).
$$

If $d\mu(y)=dy$, then $\delta_\mu(x,y)=\delta(x-y)$. If $d\mu(y)=w(y)dy$, then

$$
\delta_\mu(x,y)=\frac{\delta(x-y)}{w(y)}.
$$

This is why weighted Sturm–Liouville Green functions can look off by a factor of $w$. They are not off; they are using different measures.

## Green function versus fundamental solution

A **fundamental solution** solves the local distributional equation

$$
L_xE(x,y)=\delta(x-y)
$$

in a coordinate patch, on all of $\mathbb R^d$, or away from global complications. A **Green function for a problem** also satisfies the boundary conditions, falloff conditions, periodicity conditions, or pole prescription of that problem.

For example, on $\mathbb R$ the operator

$$
L=-\frac{d^2}{dx^2}+m^2,
\qquad m>0,
$$

has translation-invariant Green function

$$
G(x,y)=\frac{1}{2m}e^{-m|x-y|}.
$$

On an interval $[0,L]$, the same differential expression has different Green functions depending on whether one chooses Dirichlet, Neumann, Robin, or periodic boundary conditions. The singularity at $x=y$ is local; the rest of the kernel knows the global problem.

So the equation

$$
L_xG(x,y)=\delta(x-y)
$$

is only half the address. The other half is where the Green function lives.

## A one-dimensional construction

Consider a second-order operator

$$
L=-(p\partial_x)'+q
$$

on $[a,b]$, with boundary conditions. To solve

$$
LG(x,y)=\delta(x-y),
$$

one uses two homogeneous solutions. Let $u_L$ solve $Lu_L=0$ and satisfy the left boundary condition. Let $u_R$ solve $Lu_R=0$ and satisfy the right boundary condition.

Define

$$
W_p[u_L,u_R]
=p(x)\left(u_Lu_R'-u_L'u_R\right).
$$

For homogeneous solutions this is independent of $x$. If $W_p\ne0$, then

$$
G(x,y)=-\frac{u_L(x_<)u_R(x_>)}{W_p[u_L,u_R]},
$$

where

$$
x_<=\min(x,y),
\qquad
x_>=\max(x,y).
$$

This formula has three built-in facts:

1. for $x\ne y$, $G$ solves the homogeneous equation;
2. at $x=y$, $G$ is continuous;
3. the derivative has the jump required to produce the delta function.

For $L= -d^2/dx^2+V(x)$, the jump condition is

$$
\partial_xG(y^+,y)-\partial_xG(y^-,y)=-1.
$$

For $L=-(p\partial_x)'+q$, it becomes

$$
p(y)\partial_xG(y^+,y)-p(y)\partial_xG(y^-,y)=-1.
$$

This jump is the distributional fingerprint of the inverse.

## Spectral representation

Suppose $A$ is a self-adjoint operator with normalized eigenfunctions $u_n$ and eigenvalues $\lambda_n$:

$$
Au_n=\lambda_n u_n,
\qquad
\langle u_m,u_n\rangle=\delta_{mn}.
$$

If $0$ is not in the spectrum, then formally

$$
A^{-1}f=\sum_n\frac{\langle u_n,f\rangle}{\lambda_n}u_n.
$$

Thus the Green kernel is

$$
G(x,y)=\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n},
$$

with the understanding that the kernel is written relative to the chosen measure.

More generally, the resolvent is

$$
R(z)=(A-z)^{-1},
$$

and its kernel is

$$
G_z(x,y)=\sum_n\frac{u_n(x)\overline{u_n(y)}}{\lambda_n-z}.
$$

The resolvent is often the cleaner object. It exists away from the spectrum and encodes the spectrum through its singularities. Poles correspond to discrete eigenvalues. Branch cuts encode continuous spectrum. Spectral density is recovered from discontinuities across cuts.

For continuous spectrum, the sum becomes a spectral integral. Schematically,

$$
G_z(x,y)=\int d\lambda\,\frac{\rho(x,y;\lambda)}{\lambda-z}.
$$

This is the same idea behind Källén–Lehmann representations in QFT: analytic structure stores spectral information.

## Zero modes and pseudo-inverses

If $A$ has a zero mode $u_0$, then $A^{-1}$ does not exist on the whole Hilbert space. The equation

$$
Au=f
$$

is solvable only if $f$ is orthogonal to every zero mode:

$$
\langle u_0,f\rangle=0.
$$

On the orthogonal complement of the zero modes, one can define a reduced Green function

$$
G'(x,y)=\sum_{\lambda_n\ne0}\frac{u_n(x)\overline{u_n(y)}}{\lambda_n}.
$$

It satisfies

$$
A_xG'(x,y)=\delta(x-y)-P_0(x,y),
$$

where $P_0$ is the kernel of the projection onto the zero-mode subspace.

In QFT, this is not rare. Zero modes appear from translations of solitons, gauge transformations, global symmetries, moduli, Neumann boundary conditions, and massless fields. The correct response is not to divide by zero with confidence. One projects, fixes a gauge, introduces collective coordinates, or regulates and interprets the limit.

## Constant-coefficient Euclidean Green functions

For the Euclidean massive scalar operator

$$
L_E=-\partial^2+m^2
$$

on $\mathbb R^d$, translation invariance gives

$$
G_E(x-y)=\int\frac{d^dp}{(2\pi)^d}\,\frac{e^{ip\cdot(x-y)}}{p^2+m^2}.
$$

This solves

$$
(-\partial_x^2+m^2)G_E(x-y)=\delta^{(d)}(x-y).
$$

In one Euclidean dimension,

$$
G_E(x)=\int_{-\infty}^{\infty}\frac{dp}{2\pi}\,\frac{e^{ipx}}{p^2+m^2}
=\frac{1}{2m}e^{-m|x|}.
$$

At $m=0$, the inverse of $-\partial^2$ on all of $\mathbb R^d$ becomes infrared-sensitive. In low dimensions, this is not a tiny nuisance; it is the calculation trying to tell you that zero momentum matters.

## Lorentzian Green functions and prescriptions

For the mostly-minus convention,

$$
p^2=(p^0)^2-\mathbf p^2.
$$

The free Klein–Gordon operator is

$$
\Box+m^2.
$$

The momentum-space denominator vanishes on shell:

$$
p^2-m^2=0.
$$

A Lorentzian Green function is not fixed until one says how to pass the poles. Important choices include:

| Object | Physical role | Prescription idea |
|---|---|---|
| retarded Green function | causal response to sources | support only for $t>0$ |
| advanced Green function | response from future data | support only for $t<0$ |
| Feynman propagator | time-ordered quantum amplitude | positive-energy poles below, negative-energy poles above |
| Wightman function | unordered vacuum correlation | on-shell positive-frequency part |
| Euclidean Green function | elliptic inverse after Wick rotation | no real-time pole ambiguity |

With the site convention $e^{-ip\cdot x}$, the scalar Feynman propagator is written

$$
D_F(x-y)=\int\frac{d^dp}{(2\pi)^d}\,\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

It satisfies, in distributional form,

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(d)}(x-y),
$$

with this normalization. Some authors instead define $G_F=iD_F$ or absorb signs into the operator. Always check which object is being called the propagator.

The retarded Green function for the Klein–Gordon equation is a different inverse. It is selected by support:

$$
G_R(t,\mathbf x)=0
\qquad
\text{for }t<0.
$$

The Feynman propagator is not the classical causal response to a source. It is the kernel suited to time-ordered quantum correlation functions and perturbation theory.

## Green functions as QFT correlators

For a free scalar field, the time-ordered two-point function is

$$
\langle 0|T\phi(x)\phi(y)|0\rangle=D_F(x-y).
$$

In the path integral, the free generating functional has the schematic Gaussian form

$$
Z[J]=Z[0]\exp\left(\frac{i}{2}\int d^dx\,d^dy\,J(x)D_F(x-y)J(y)\right),
$$

up to sign conventions tied to the quadratic action. Functional derivatives with respect to $J$ produce correlation functions.

In Euclidean signature, for a positive operator $L_E$, the Gaussian integral gives

$$
\langle \phi(x)\phi(y)\rangle_E=G_E(x,y),
$$

where

$$
L_{E,x}G_E(x,y)=\delta(x-y).
$$

Thus the inverse of the quadratic operator is the two-point function of the free theory. Interacting correlation functions are then built by perturbing around this inverse.

## Boundary Green functions

Let $L=-d^2/dx^2+m^2$ on $[0,L]$ with Dirichlet boundary conditions. The Green function satisfies

$$
[-\partial_x^2+m^2]G_D(x,y)=\delta(x-y),
$$

with

$$
G_D(0,y)=G_D(L,y)=0.
$$

Using the left and right homogeneous solutions

$$
u_L(x)=\sinh(mx),
\qquad
u_R(x)=\sinh(m(L-x)),
$$

one obtains

$$
G_D(x,y)=
\frac{\sinh(m x_<)\sinh(m(L-x_>))}{m\sinh(mL)}.
$$

This kernel is symmetric:

$$
G_D(x,y)=G_D(y,x),
$$

because the operator with Dirichlet domain is self-adjoint. If one changes the boundary condition, the formula changes.

## Heat-kernel representation

If $L$ is positive and self-adjoint, then

$$
L^{-1}=\int_0^\infty ds\,e^{-sL}
$$

on the subspace where the integral converges. In kernel form,

$$
G(x,y)=\int_0^\infty ds\,K(s;x,y),
$$

where

$$
K(s;x,y)=\langle x|e^{-sL}|y\rangle
$$

is the heat kernel.

This relation is the Schwinger proper-time representation. It turns inverse operators into evolution in an auxiliary positive parameter $s$. In QFT it is a workhorse for one-loop effective actions:

$$
\log\det L=\operatorname{Tr}\log L
=-\int_0^\infty \frac{ds}{s}\,\operatorname{Tr}e^{-sL},
$$

again with regularization and zero-mode treatment understood.

Short proper time probes high eigenvalues and therefore short distances. This is why heat-kernel coefficients know about UV divergences, anomalies, curvature terms, and boundary counterterms.

## Dyson and resolvent identities

Green functions are useful because they turn differential equations into integral equations. Suppose

$$
L=L_0+V.
$$

If $G=L^{-1}$ and $G_0=L_0^{-1}$ exist, then

$$
G=G_0-G_0VG.
$$

Equivalently,

$$
G=G_0-G_0VG_0+G_0VG_0VG_0-\cdots,
$$

when the expansion makes sense. This is the operator form behind Born series, Dyson equations, Lippmann–Schwinger equations, and perturbative propagator corrections.

The resolvent identity says

$$
(A-z)^{-1}-(A-z_0)^{-1}
=(z-z_0)(A-z)^{-1}(A-z_0)^{-1}.
$$

It is a compact algebraic fact with a lot of physics packed inside: moving the spectral parameter changes the Green function in a controlled way, except where the spectrum itself obstructs the inverse.

## Symmetry of Green functions

If $A$ is self-adjoint and invertible, then its Green kernel satisfies

$$
G(x,y)=\overline{G(y,x)}
$$

relative to the same measure. For real self-adjoint operators, this becomes

$$
G(x,y)=G(y,x).
$$

Retarded Green functions are not symmetric in this way, because the retarded inverse is selected by causal support rather than by Euclidean self-adjoint inversion. This is another place where “the Green function” is too vague. There are many inverses of the same local hyperbolic equation, and the physical prescription selects one.

## Contact terms and local ambiguities

Green functions are distributions. Acting with differential operators on singular kernels can produce contact terms supported at $x=y$. In QFT, local contact terms are not usually optional clutter. They encode Ward identities, anomalies, renormalization ambiguities, operator mixing, and scheme-dependent local counterterms.

For example, away from $x=y$, a Green function may solve the homogeneous equation. The entire source may be hidden at the diagonal. That is normal. A propagator is allowed to be singular exactly where two operator insertions collide.

The safe test is always distributional: smear with test functions and integrate by parts.

## Common pitfalls

### Saying “the Green function” without the problem

Ask: which operator, which domain, which measure, which boundary condition, which zero-mode prescription, and which pole prescription? Without those, the phrase is underspecified.

### Confusing Feynman and retarded propagators

The Feynman propagator computes time-ordered amplitudes. The retarded Green function computes causal response. They solve related differential equations but have different prescriptions and different support properties.

### Forgetting the measure

If the Hilbert space is $L^2_w$, then the identity kernel is normalized with $w(y)dy$. A missing weight can make a correct spectral expansion look wrong.

### Dividing by zero modes

If the operator has a kernel, the inverse must be restricted, regulated, or replaced by a pseudo-inverse. In gauge theory, this is the doorway to gauge fixing and ghosts; in soliton physics, it is the doorway to collective coordinates.

### Trusting pointwise equations too much

The equation $L_xG(x,y)=\delta(x-y)$ is not an ordinary pointwise equality. It means equality after smearing. Away from the diagonal, $G$ usually solves the homogeneous equation.

### Ignoring signs in jump conditions

For $L=-d^2/dx^2+m^2$, the derivative jump is $G'_+-G'_-=-1$. For $L=+d^2/dx^2-m^2$, signs change. The operator sign decides the jump sign.

## Exercises

### Exercise 1: The one-dimensional massive Green function

Show that

$$
G(x)=\frac{1}{2m}e^{-m|x|}
$$

satisfies

$$
\left(-\frac{d^2}{dx^2}+m^2\right)G(x)=\delta(x)
$$

on $\mathbb R$.

<details><summary><strong>Solution</strong></summary>

For $x\ne0$,

$$
G''(x)=m^2G(x),
$$

so

$$
(-\partial_x^2+m^2)G(x)=0.
$$

The only possible contribution is at $x=0$. The function is continuous, but

$$
G'(0^+)=-\frac12,
\qquad
G'(0^-)=\frac12.
$$

Thus

$$
G'(0^+)-G'(0^-)=-1.
$$

Integrating $(-G''+m^2G)$ across a small interval around zero gives

$$
-G'(0^+)+G'(0^-)=1,
$$

so the distributional source is $\delta(x)$.

</details>

### Exercise 2: Symmetry from self-adjointness

Let $A$ be an invertible self-adjoint operator with real normalized eigenfunctions $u_n$. Show from the spectral representation that

$$
G(x,y)=G(y,x).
$$

<details><summary><strong>Solution</strong></summary>

The spectral representation is

$$
G(x,y)=\sum_n\frac{u_n(x)u_n(y)}{\lambda_n}.
$$

Since multiplication of real numbers is commutative,

$$
u_n(x)u_n(y)=u_n(y)u_n(x),
$$

so

$$
G(x,y)=\sum_n\frac{u_n(y)u_n(x)}{\lambda_n}=G(y,x).
$$

For complex modes, the statement becomes $G(x,y)=\overline{G(y,x)}$ with the standard Hermitian convention.

</details>

### Exercise 3: Dirichlet Green function on an interval

Verify that

$$
G_D(x,y)=
\frac{\sinh(m x_<)\sinh(m(L-x_>))}{m\sinh(mL)}
$$

solves

$$
[-\partial_x^2+m^2]G_D(x,y)=\delta(x-y)
$$

with $G_D(0,y)=G_D(L,y)=0$.

<details><summary><strong>Solution</strong></summary>

For $x<y$, $G_D$ is proportional to $\sinh(mx)$, so it vanishes at $x=0$ and solves the homogeneous equation. For $x>y$, it is proportional to $\sinh(m(L-x))$, so it vanishes at $x=L$ and solves the homogeneous equation.

The two pieces agree at $x=y$, so $G_D$ is continuous. Compute the derivative jump. For $x>y$,

$$
\partial_xG_D(x,y)
=-\frac{\sinh(my)\cosh(m(L-x))}{\sinh(mL)}.
$$

For $x<y$,

$$
\partial_xG_D(x,y)
=\frac{\cosh(mx)\sinh(m(L-y))}{\sinh(mL)}.
$$

At $x=y$,

$$
\partial_xG_D(y^+,y)-\partial_xG_D(y^-,y)
=-\frac{\sinh(my)\cosh(m(L-y))+\cosh(my)\sinh(m(L-y))}{\sinh(mL)}.
$$

Using $\sinh A\cosh B+\cosh A\sinh B=\sinh(A+B)$ gives

$$
\partial_xG_D(y^+,y)-\partial_xG_D(y^-,y)=-1.
$$

Therefore $[-\partial_x^2+m^2]G_D=\delta(x-y)$.

</details>

### Exercise 4: Zero-mode projection

Let $A$ have normalized eigenfunctions $u_n$ with $\lambda_0=0$ and $\lambda_n\ne0$ for $n\ge1$. Define

$$
G'(x,y)=\sum_{n\ge1}\frac{u_n(x)\overline{u_n(y)}}{\lambda_n}.
$$

Show that

$$
A_xG'(x,y)=\delta(x-y)-u_0(x)\overline{u_0(y)},
$$

assuming the kernel is written with respect to the same measure as the orthonormality relation.

<details><summary><strong>Solution</strong></summary>

Apply $A_x$ term by term:

$$
A_xG'(x,y)=\sum_{n\ge1}u_n(x)\overline{u_n(y)}.
$$

Completeness gives

$$
\delta(x-y)=\sum_{n\ge0}u_n(x)\overline{u_n(y)}.
$$

Removing the $n=0$ term yields

$$
\sum_{n\ge1}u_n(x)\overline{u_n(y)}
=\delta(x-y)-u_0(x)\overline{u_0(y)}.
$$

So the reduced Green function inverts $A$ only on the subspace orthogonal to the zero mode.

</details>

## References

- R. Courant and D. Hilbert, *Methods of Mathematical Physics*, Vols. 1–2.
- P. M. Morse and H. Feshbach, *Methods of Theoretical Physics*.
- L. C. Evans, *Partial Differential Equations*.
- G. B. Folland, *Introduction to Partial Differential Equations*.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, especially Vols. 1–3.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*.
- M. Srednicki, *Quantum Field Theory*, for path-integral and propagator uses.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for Green functions and Feynman propagators in perturbation theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. 1, for propagators, analyticity, and spectral ideas.
- A. Zee, *Quantum Field Theory in a Nutshell*, for physical intuition about propagators and response.

## Version history

- 2026-06-25: Initial polished draft for the Mathematical Toolkit.
