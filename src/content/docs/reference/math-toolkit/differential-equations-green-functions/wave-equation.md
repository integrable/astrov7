---
title: "Wave Equation"
description: "Explains the wave equation as a hyperbolic initial-value problem, including characteristics, finite propagation speed, Fourier modes, causal Green functions, pole prescriptions, and QFT free-field interpretation."
sidebar:
  label: "Wave Equation"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard references on hyperbolic PDEs, Green functions, scattering theory, and QFT free fields, including Courant–Hilbert, Evans, Taylor, Friedlander, Reed–Simon, Hormander, Weinberg, Srednicki, Schwartz, Zee, Coleman, and mathematical-physics treatments of propagators and spectral theory."
topics:
  - wave equation
  - hyperbolic PDEs
  - Cauchy problem
  - light cones
  - finite propagation speed
  - characteristics
  - retarded Green functions
  - advanced Green functions
  - Feynman propagator
  - Klein–Gordon equation
  - microcausality
  - Fourier modes
canonicalTopics:
  - wave-equation
  - hyperbolic-pde
  - cauchy-problem
  - light-cone
  - finite-propagation-speed
  - characteristic
  - retarded-green-function
  - advanced-green-function
  - feynman-propagator
  - klein-gordon-equation
  - microcausality
  - fourier-mode
researchStatus:
  established:
    - "The wave equation is the canonical hyperbolic PDE: its Cauchy problem is controlled by characteristic cones, energy estimates, and causal Green functions."
  active:
    - "Wave propagation on curved spacetimes, black-hole backgrounds, dispersive media, nonlocal effective theories, rough metrics, boundaries, and interacting real-time QFT remains an active interface between analysis and physics."
---

## Summary

The wave equation is the model hyperbolic equation. In flat spacetime with speed $c=1$, it is

$$
\Box u=0,
\qquad
\Box=\partial_t^2-\nabla^2
$$

in the mostly-minus convention. With a source, one writes

$$
\Box u=f.
$$

The massive relativistic version is the Klein–Gordon equation

$$
(\Box+m^2)\phi=f.
$$

The central difference from the heat equation is causality. Heat flow immediately smooths and spreads. Wave flow propagates from Cauchy data with finite speed along characteristic cones.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Spacetime diagram of a light cone and a flow chart connecting the hyperbolic wave equation to Cauchy data, oscillator modes, causal Green functions, and pole prescriptions.](/figures/math-toolkit/wave-equation-causal-propagation.svg)

<figcaption>

The wave equation is controlled by its principal symbol. In flat space the characteristics are light cones. Cauchy data evolve inside domains of dependence, spatial Fourier modes become harmonic oscillators, and different pole prescriptions produce retarded, advanced, Pauli–Jordan, and Feynman Green functions.

</figcaption>
</figure>

In QFT, the wave equation is not just a classical PDE. It is the equation behind free relativistic fields, oscillator mode decompositions, commutators, causal response, retarded propagators, and the pole structure of scattering amplitudes. The same denominator

$$
p^2-m^2
$$

can produce different distributions depending on the prescription. That prescription is not a minor technicality; it tells you whether the kernel is causal, time-ordered, advanced, or something else.

## Prerequisites

You should know [Partial Differential Equations](/math-toolkit/differential-equations-green-functions/partial-differential-equations/), [Elliptic, Hyperbolic, and Parabolic Equations](/math-toolkit/differential-equations-green-functions/elliptic-hyperbolic-parabolic/), [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/).

It is also useful to have read [Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/), because the contrast between parabolic diffusion and hyperbolic propagation prevents a lot of conceptual mud.

## Core idea

The wave equation turns initial data on a hypersurface into a solution in spacetime. For the massless equation in $1+n$ flat dimensions,

$$
\partial_t^2u-\Delta u=0,
$$

the Cauchy data are

$$
u(0,\mathbf x)=f(\mathbf x),
\qquad
\partial_tu(0,\mathbf x)=g(\mathbf x).
$$

The solution at a later point $(t,\mathbf x)$ depends only on the data in the ball

$$
|\mathbf y-\mathbf x|\le |t|.
$$

This is finite propagation speed. In spacetime language, influence travels inside or on the light cone.

The same statement can be read in frequency space. After a spatial Fourier transform, the wave equation becomes a collection of harmonic oscillators:

$$
\partial_t^2\widetilde u(t,\mathbf k)+|\mathbf k|^2\widetilde u(t,\mathbf k)=0.
$$

For a massive field, the frequency becomes

$$
\omega_{\mathbf k}=\sqrt{|\mathbf k|^2+m^2}.
$$

This oscillator decomposition is the classical shadow of free-field quantization.

## Setup and conventions

We use the mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,\ldots,-1),
$$

so

$$
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

Plane waves are written as

$$
e^{-ip\cdot x}=e^{-ip^0t+i\mathbf p\cdot\mathbf x},
\qquad
p\cdot x=p^0t-\mathbf p\cdot\mathbf x.
$$

Acting on a plane wave,

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x},
\qquad
p^2=(p^0)^2-\mathbf p^2.
$$

Therefore

$$
(\Box+m^2)e^{-ip\cdot x}=-(p^2-m^2)e^{-ip\cdot x}.
$$

This minus sign is why QFT propagator equations often contain factors such as $-i\delta^{(d)}(x-y)$. The pole is at the physically important place,

$$
p^2=m^2,
$$

but the distribution attached to that pole depends on the prescription.

For the nonrelativistic-looking wave equation with speed $c$, one writes

$$
\partial_t^2u-c^2\nabla^2u=f.
$$

Most QFT formulas use $c=1$.

## Characteristics and the light cone

The principal part of the wave operator is

$$
\partial_t^2-\sum_{i=1}^n\partial_i^2.
$$

Its principal symbol is

$$
P(\xi)=\xi_0^2-|\boldsymbol\xi|^2.
$$

The characteristic covectors satisfy

$$
P(\xi)=0,
\qquad
\xi_0^2=|\boldsymbol\xi|^2.
$$

These are null covectors. The corresponding characteristic hypersurfaces are lightlike. In flat spacetime, signals from an event propagate along cones

$$
(t-t_0)^2=|\mathbf x-\mathbf x_0|^2.
$$

For the massive Klein–Gordon equation,

$$
(\Box+m^2)\phi=0,
$$

the mass term does not change the principal symbol. Therefore the characteristic cone is still the light cone. Mass changes the dispersion relation and tail behavior, but it does not allow superluminal propagation.

This is the geometric content of hyperbolicity: the highest-derivative terms decide the causal cones.

## The Cauchy problem

For the wave equation

$$
\partial_t^2u-\Delta u=f,
$$

a natural Cauchy problem specifies

$$
u(0,\mathbf x)=u_0(\mathbf x),
\qquad
\partial_tu(0,\mathbf x)=u_1(\mathbf x).
$$

For smooth compactly supported data, there is a unique smooth solution, and the support propagates at finite speed. More generally, the solution theory extends to Sobolev spaces using energy estimates.

The basic conserved energy for the homogeneous massive equation

$$
(\partial_t^2-\Delta+m^2)u=0
$$

is

$$
E(t)=\frac12\int d^n\mathbf x\,
\left[
(\partial_tu)^2+|\nabla u|^2+m^2u^2
\right].
$$

For sufficiently decaying fields, differentiating and integrating by parts gives

$$
\frac{dE}{dt}=0.
$$

This conservation law proves uniqueness: if two solutions have the same initial data, their difference has zero initial energy and hence vanishes. It also explains why the wave equation is stable in the right norm.

With a source,

$$
(\partial_t^2-\Delta+m^2)u=f,
$$

the energy obeys

$$
\frac{dE}{dt}=\int d^n\mathbf x\,f\,\partial_tu.
$$

The source injects or removes energy. In QFT language, this is the classical version of coupling a field to an external current.

## Fourier-mode solution

Let

$$
u(t,\mathbf x)=\int\frac{d^n\mathbf k}{(2\pi)^n}
e^{i\mathbf k\cdot\mathbf x}\widetilde u(t,\mathbf k).
$$

For the massive homogeneous equation,

$$
(\partial_t^2-\Delta+m^2)u=0,
$$

each Fourier mode satisfies

$$
\partial_t^2\widetilde u(t,\mathbf k)+\omega_{\mathbf k}^2\widetilde u(t,\mathbf k)=0,
\qquad
\omega_{\mathbf k}=\sqrt{\mathbf k^2+m^2}.
$$

Thus

$$
\widetilde u(t,\mathbf k)
=\widetilde u_0(\mathbf k)\cos(\omega_{\mathbf k}t)
+\frac{\widetilde u_1(\mathbf k)}{\omega_{\mathbf k}}\sin(\omega_{\mathbf k}t).
$$

Equivalently,

$$
\widetilde u(t,\mathbf k)=A(\mathbf k)e^{-i\omega_{\mathbf k}t}+B(\mathbf k)e^{i\omega_{\mathbf k}t}.
$$

The two signs of the frequency are the classical roots of

$$
p^2-m^2=0.
$$

In quantization, $A$ and $B$ become related to annihilation and creation operators, with normalizations chosen so that the canonical commutation relations work.

## Retarded and advanced Green functions

A retarded Green function for

$$
P=\Box+m^2
$$

satisfies

$$
P_xG_R(x,y)=\delta^{(1+n)}(x-y)
$$

and

$$
G_R(x,y)=0
\quad\text{unless}\quad x\in J^+(y),
$$

where $J^+(y)$ is the causal future of $y$. The advanced Green function satisfies the same differential equation but has support in the causal past:

$$
G_A(x,y)=0
\quad\text{unless}\quad x\in J^-(y).
$$

In spatial Fourier space, the retarded Green function for the massive equation is especially transparent:

$$
G_R(t,\mathbf k)=\theta(t)\frac{\sin(\omega_{\mathbf k}t)}{\omega_{\mathbf k}},
$$

because

$$
(\partial_t^2+\omega_{\mathbf k}^2)G_R(t,\mathbf k)=\delta(t).
$$

The advanced kernel is

$$
G_A(t,\mathbf k)=-\theta(-t)\frac{\sin(\omega_{\mathbf k}t)}{\omega_{\mathbf k}}.
$$

Their difference is the causal, or Pauli–Jordan, distribution:

$$
\Delta(t,\mathbf k)=G_R(t,\mathbf k)-G_A(t,\mathbf k)
=\frac{\sin(\omega_{\mathbf k}t)}{\omega_{\mathbf k}}.
$$

In QFT, the commutator of a free real scalar field is proportional to this distribution:

$$
[\phi(x),\phi(y)]=i\Delta(x-y).
$$

Microcausality is the statement that this commutator vanishes at spacelike separation.

## Explicit retarded kernels in low dimensions

For the massless wave operator in $3+1$ dimensions,

$$
\Box=\partial_t^2-\nabla^2,
$$

the retarded Green function is

$$
G_R(t,\mathbf x)=\theta(t)\frac{\delta(t-r)}{4\pi r},
\qquad
r=|\mathbf x|.
$$

Equivalently,

$$
G_R(t,\mathbf x)=\frac{1}{2\pi}\theta(t)\delta(t^2-r^2).
$$

The support lies exactly on the future light cone. This is the sharp Huygens behavior familiar from waves in three spatial dimensions.

In $1+1$ dimensions, the retarded Green function is instead

$$
G_R(t,x)=\frac12\theta(t)\theta(t^2-x^2)
=\frac12\theta(t-|x|).
$$

The support fills the interior of the light cone. This is not less causal; it is causal with a tail.

For massive Klein–Gordon fields, tails inside the light cone generally appear even in $3+1$ dimensions. The principal cone still bounds propagation, but the solution need not live only on the cone.

## Pole prescriptions

The differential equation alone does not select a unique distributional inverse. In momentum space, all Green functions know about the same algebraic denominator, but they place the poles differently.

For a free scalar field, the Feynman propagator is

$$
\Delta_F(x-y)
=\int\frac{d^dp}{(2\pi)^d}
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

It satisfies

$$
(\Box+m^2)\Delta_F(x-y)=-i\delta^{(d)}(x-y).
$$

The retarded Green function can be written as

$$
G_R(x-y)
=\int\frac{d^dp}{(2\pi)^d}
\frac{-e^{-ip\cdot(x-y)}}{(p^0+i\epsilon)^2-\omega_{\mathbf p}^2},
$$

with

$$
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The advanced kernel uses the opposite shift:

$$
G_A(x-y)
=\int\frac{d^dp}{(2\pi)^d}
\frac{-e^{-ip\cdot(x-y)}}{(p^0-i\epsilon)^2-\omega_{\mathbf p}^2}.
$$

The signs are less important than the lesson: a pole prescription is part of the Green function. If someone writes

$$
\frac1{p^2-m^2},
$$

without saying how the poles are bypassed, they have not yet specified a spacetime distribution.

## Duhamel formula for sources

For the inhomogeneous equation

$$
(\partial_t^2-\Delta+m^2)u=f
$$

with zero initial data, the retarded solution is

$$
u(t,\mathbf x)=\int d^{1+n}y\,G_R(t- y^0,\mathbf x-\mathbf y)f(y^0,\mathbf y).
$$

If one separates time and space, this becomes

$$
\widetilde u(t,\mathbf k)
=\int_{-\infty}^t ds\,
\frac{\sin[\omega_{\mathbf k}(t-s)]}{\omega_{\mathbf k}}
\widetilde f(s,\mathbf k).
$$

This formula is the forced harmonic oscillator response for each momentum mode. The retarded condition is the upper limit $s\le t$.

With nonzero initial data at $t=0$, the full solution is the sum of the homogeneous Cauchy evolution and the retarded source response:

$$
\widetilde u(t,\mathbf k)
=\widetilde u_0(\mathbf k)\cos(\omega_{\mathbf k}t)
+\frac{\widetilde u_1(\mathbf k)}{\omega_{\mathbf k}}\sin(\omega_{\mathbf k}t)
+\int_0^t ds\,
\frac{\sin[\omega_{\mathbf k}(t-s)]}{\omega_{\mathbf k}}
\widetilde f(s,\mathbf k).
$$

That is Duhamel's principle in oscillator language.

## Boundaries and normal modes

On a spatial domain $\Omega$, boundary conditions affect the mode expansion. For example, suppose $A=-\Delta+m^2$ is a positive self-adjoint operator on $\Omega$ with chosen boundary conditions. Let

$$
A u_n=\omega_n^2 u_n,
\qquad
\langle u_m,u_n\rangle=\delta_{mn}.
$$

Then a wave field can be expanded as

$$
\phi(t,\mathbf x)=\sum_n q_n(t)u_n(\mathbf x),
$$

where

$$
\ddot q_n+\omega_n^2q_n=0.
$$

This is why cavities, finite volume QFT, Casimir problems, Kaluza–Klein compactifications, and fluctuation theory around solitons all reduce to spectral problems. The boundary condition is part of the physics: Dirichlet, Neumann, Robin, periodic, absorbing, and gauge-compatible boundary conditions generally give different spectra and different propagators.

## From wave equation to free quantum fields

A real scalar field with action

$$
S=\int d^dx\,\frac12\left(\partial_\mu\phi\partial^\mu\phi-m^2\phi^2\right)
$$

obeys

$$
(\Box+m^2)\phi=0.
$$

The spatial Fourier modes are harmonic oscillators with frequency

$$
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Canonical quantization promotes the coefficients to operators and gives the familiar expansion

$$
\phi(x)=\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac1{\sqrt{2\omega_{\mathbf p}}}
\left[
a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}
\right]_{p^0=\omega_{\mathbf p}}.
$$

The normalization is chosen so that

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]=i\delta^{(d-1)}(\mathbf x-\mathbf y),
\qquad
\pi=\partial_t\phi.
$$

The causal structure of the classical wave equation survives as the vanishing of commutators outside the light cone. This is one of the reasons relativistic QFT is built from hyperbolic equations rather than arbitrary dispersion relations.

## Euclidean continuation

The Lorentzian Klein–Gordon operator is

$$
\Box+m^2=\partial_t^2-\nabla^2+m^2.
$$

Under Wick rotation $t=-i\tau_E$, one obtains a Euclidean operator of the form

$$
-\partial_{\tau_E}^2-\nabla^2+m^2.
$$

This is elliptic and positive under suitable boundary conditions. Euclidean Green functions and heat kernels are therefore controlled by elliptic theory, while real-time propagation is controlled by hyperbolic theory.

The continuation is powerful but delicate. The retarded propagator, advanced propagator, Feynman propagator, Wightman functions, and Euclidean correlator are different boundary values of related analytic objects when the theory has the right spectral and causality properties. They are not interchangeable just because they share a denominator.

## Common pitfalls

**Confusing the wave equation with the heat equation.** The heat equation is first order in diffusion time and smooths instantly. The wave equation is second order in time and propagates Cauchy data causally.

**Forgetting the second initial datum.** A wave equation needs both $u$ and $\partial_tu$ on a Cauchy surface. Giving only $u$ is not a complete Cauchy problem.

**Thinking mass changes the light cone.** The mass term changes the frequency and tail behavior, but the principal symbol and characteristic cone are unchanged.

**Writing a denominator without a prescription.** The expression $1/(p^2-m^2)$ is not yet a Green function. Retarded, advanced, Feynman, and principal-value prescriptions are different distributions.

**Assuming all waves live only on the light cone.** In $3+1$ massless flat space the retarded kernel is supported on the cone. In other dimensions, curved spacetimes, and massive equations, causal tails can fill the interior.

**Ignoring boundary conditions.** On a finite domain, the wave equation is not fully specified until the boundary condition and operator domain are specified.

**Mistaking group velocity statements for proof of causality.** Dispersion relations are useful, but causality in relativistic field theory is fundamentally tied to hyperbolicity, support properties, and commutators.

## Relations to other pages

[Heat Equation and Heat Kernel](/math-toolkit/differential-equations-green-functions/heat-equation-and-heat-kernel/) explains the parabolic Euclidean side: semigroups, smoothing, proper time, determinants, and UV asymptotics.

[Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/) explains inverse kernels and prescriptions in a broader setting. The wave equation supplies the canonical causal examples.

[Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) fixes the plane-wave convention used in the momentum-space denominators.

[Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/) explains why propagators and commutators are distributions rather than ordinary functions.

[Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/) explains normal-mode expansions in one-dimensional or separated problems.

## Research status

The flat-space wave equation, its Cauchy problem, energy estimates, Fourier solution, and retarded and advanced Green functions are textbook material.

Research-level complications appear when the causal geometry or operator is nontrivial: curved spacetimes, horizons, trapping, black-hole quasi-normal modes, boundaries, rough coefficients, dispersive effective media, nonlocal corrections, interacting real-time QFT, thermal real-time contours, and reconstruction of Lorentzian dynamics from Euclidean data. These topics use the elementary wave equation as their grammar, but the sentences get spicy.

## Exercises

### Exercise 1: Solve the massive wave equation by Fourier transform

Let

$$
(\partial_t^2-\Delta+m^2)u=0
$$

on $\mathbb R^n$, with data

$$
u(0,\mathbf x)=u_0(\mathbf x),
\qquad
\partial_tu(0,\mathbf x)=u_1(\mathbf x).
$$

Derive the Fourier-space solution.

<details><summary><strong>Solution</strong></summary>

Write

$$
u(t,\mathbf x)=\int\frac{d^n\mathbf k}{(2\pi)^n}
e^{i\mathbf k\cdot\mathbf x}\widetilde u(t,\mathbf k).
$$

Then $-\Delta$ becomes $\mathbf k^2$, so the equation becomes

$$
\partial_t^2\widetilde u(t,\mathbf k)+\omega_{\mathbf k}^2\widetilde u(t,\mathbf k)=0,
\qquad
\omega_{\mathbf k}=\sqrt{\mathbf k^2+m^2}.
$$

The oscillator solution is

$$
\widetilde u(t,\mathbf k)
=A(\mathbf k)\cos(\omega_{\mathbf k}t)
+B(\mathbf k)\sin(\omega_{\mathbf k}t).
$$

The data give

$$
A(\mathbf k)=\widetilde u_0(\mathbf k),
\qquad
B(\mathbf k)=\frac{\widetilde u_1(\mathbf k)}{\omega_{\mathbf k}}.
$$

Therefore

$$
\widetilde u(t,\mathbf k)
=\widetilde u_0(\mathbf k)\cos(\omega_{\mathbf k}t)
+\frac{\widetilde u_1(\mathbf k)}{\omega_{\mathbf k}}\sin(\omega_{\mathbf k}t).
$$

</details>

### Exercise 2: Energy conservation

For a real solution of

$$
(\partial_t^2-\Delta+m^2)u=0
$$

with sufficient decay at spatial infinity, prove that

$$
E(t)=\frac12\int d^n\mathbf x\,
\left[(\partial_tu)^2+|\nabla u|^2+m^2u^2\right]
$$

is conserved.

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dE}{dt}
=\int d^n\mathbf x\,
\left[\partial_tu\,\partial_t^2u+\nabla u\cdot\nabla\partial_tu+m^2u\partial_tu\right].
$$

Integrate the gradient term by parts, dropping the boundary term:

$$
\int d^n\mathbf x\,\nabla u\cdot\nabla\partial_tu
=-\int d^n\mathbf x\,(\Delta u)\partial_tu.
$$

Thus

$$
\frac{dE}{dt}
=\int d^n\mathbf x\,\partial_tu
\left[\partial_t^2u-\Delta u+m^2u\right].
$$

The bracket vanishes by the equation of motion, so $dE/dt=0$.

</details>

### Exercise 3: Retarded oscillator kernel

Show that

$$
G_R(t)=\theta(t)\frac{\sin(\omega t)}{\omega}
$$

satisfies

$$
(\partial_t^2+\omega^2)G_R(t)=\delta(t).
$$

<details><summary><strong>Solution</strong></summary>

For $t>0$, $G_R$ solves the homogeneous equation. For $t<0$, it vanishes. The possible delta function comes from the jump in the first derivative at $t=0$.

The function is continuous at $t=0$ because $\sin(0)=0$. Its derivative for $t>0$ is $\cos(\omega t)$, while for $t<0$ it is $0$. Therefore

$$
G_R'(0^+)-G_R'(0^-)=1.
$$

A function with a unit jump in its first derivative has a delta function in its second derivative. Hence

$$
(\partial_t^2+\omega^2)G_R(t)=\delta(t).
$$

</details>

### Exercise 4: Compare retarded support in one and three spatial dimensions

The massless retarded kernels are

$$
G_R^{1+1}(t,x)=\frac12\theta(t-|x|)
$$

and

$$
G_R^{3+1}(t,\mathbf x)=\theta(t)\frac{\delta(t-r)}{4\pi r}.
$$

Describe their support.

<details><summary><strong>Solution</strong></summary>

For $1+1$ dimensions, $G_R^{1+1}$ is nonzero when

$$
t\ge |x|.
$$

Thus it is supported throughout the interior and boundary of the future light cone.

For $3+1$ dimensions, the delta function enforces

$$
t=r
$$

with $t\ge0$. Thus the kernel is supported only on the future light cone, not inside it. Both kernels are causal; they just have different tail behavior.

</details>

## References

- R. Courant and D. Hilbert, *Methods of Mathematical Physics*, Vol. II.
- L. C. Evans, *Partial Differential Equations*.
- M. E. Taylor, *Partial Differential Equations*.
- F. G. Friedlander, *The Wave Equation on a Curved Space-Time*.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*.
- L. Hormander, *The Analysis of Linear Partial Differential Operators*.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I.
- M. Srednicki, *Quantum Field Theory*.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*.
- A. Zee, *Quantum Field Theory in a Nutshell*.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*.

## Version history

- 2026-06-25: First polished draft for the Mathematical Toolkit.
