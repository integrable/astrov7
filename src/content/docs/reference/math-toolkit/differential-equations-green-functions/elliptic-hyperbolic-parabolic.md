---
title: "Elliptic, Hyperbolic, and Parabolic Equations"
description: "Classifies PDEs by their principal symbols and explains the QFT meaning of elliptic boundary-value problems, hyperbolic causal evolution, and parabolic heat-kernel flow."
sidebar:
  label: "Elliptic, Hyperbolic, and Parabolic Equations"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard PDE and mathematical-physics references, including Evans, Folland, Taylor, Hörmander, Courant–Hilbert, Strauss, Reed–Simon, Bär–Ginoux–Pfäffle, Gilkey, Vassilevich, and QFT treatments of Euclidean operators, Lorentzian propagation, heat kernels, and propagator prescriptions."
topics:
  - elliptic equations
  - hyperbolic equations
  - parabolic equations
  - principal symbols
  - characteristic varieties
  - Cauchy problems
  - boundary-value problems
  - heat kernels
  - Wick rotation
  - propagators
  - gauge fixing
canonicalTopics:
  - elliptic-equation
  - hyperbolic-equation
  - parabolic-equation
  - principal-symbol
  - characteristic-variety
  - cauchy-problem
  - boundary-value-problem
  - heat-kernel
  - wick-rotation
  - propagator
  - gauge-fixing
researchStatus:
  established:
    - "The principal symbol controls the local type of a linear PDE: elliptic problems are naturally boundary-value problems, hyperbolic problems are naturally initial-value problems, and parabolic problems describe heat-like semigroup evolution."
  active:
    - "Mixed-type operators, singular geometries, gauge-degenerate symbols, low-regularity coefficients, Lorentzian boundaries, and nonlinear field equations require more refined PDE and microlocal tools."
---

## Summary

The words *elliptic*, *hyperbolic*, and *parabolic* are not decorative labels. They say what kind of mathematical problem a differential equation wants to be.

Elliptic equations behave like equilibrium or Euclidean problems: one supplies boundary data and solves everywhere at once. Hyperbolic equations behave like causal evolution: one supplies initial data and evolves within light cones. Parabolic equations behave like heat flow: one supplies initial data and obtains smoothing forward in an auxiliary time. In QFT, these three behaviors reappear as Euclidean propagators, Lorentzian propagators, and heat-kernel or Schwinger-parameter evolution.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Classification flow for elliptic, hyperbolic, and parabolic equations from the principal symbol to QFT interpretations.](/figures/math-toolkit/elliptic-hyperbolic-parabolic-map.svg)

<figcaption>

The highest-derivative part of a differential operator determines the local PDE type. Elliptic operators have no real characteristic cone and lead to boundary-value problems; hyperbolic operators have characteristic cones and lead to causal initial-value problems; parabolic operators combine first-order evolution with an elliptic spatial operator and lead to heat-kernel semigroups.

</figcaption>
</figure>

The classification is local and leading-order. It does not by itself solve the global problem. Boundary conditions, domains, source spaces, singularities, gauge redundancies, and pole prescriptions still matter. But the classification tells you which additional data are natural and which expectations are dangerous.

The small dictionary is:

| PDE type | Local prototype | Natural data | QFT reading |
|---|---|---|---|
| elliptic | $(-\Delta+m^2)u=f$ | boundary data | Euclidean inverse, instanton fluctuation operator, determinant |
| hyperbolic | $(\partial_t^2-\nabla^2+m^2)u=f$ | initial data | causal propagation, retarded/advanced/Feynman propagators |
| parabolic | $(\partial_s-\nabla^2)u=0$ | initial data at $s=0$ | heat kernel, proper time, UV expansion |

Tiny warning label: the same formal expression can change type after analytic continuation. Wick rotation is not just a costume change for a minus sign; it changes a hyperbolic Lorentzian operator into an elliptic Euclidean one.

## Prerequisites

You should know the previous page, [Partial Differential Equations](/math-toolkit/differential-equations-green-functions/partial-differential-equations/), especially differential operators, Fourier symbols, and principal symbols. You should also be comfortable with [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Unbounded Operators](/math-toolkit/functional-analysis-spectral-theory/unbounded-operators/), [Self-Adjointness](/math-toolkit/functional-analysis-spectral-theory/self-adjointness/), and [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/).

The next page, [Boundary-Value Problems](/math-toolkit/differential-equations-green-functions/boundary-value-problems/), explains why the boundary conditions are part of the operator, not an afterthought.

## The principal part decides the local type

Consider a scalar linear differential operator of order $m$ on a coordinate patch:

$$
L=\sum_{|\alpha|\le m}a_\alpha(x)\partial^\alpha.
$$

Its principal part is the order-$m$ piece,

$$
L_{\mathrm{pr}}=\sum_{|\alpha|=m}a_\alpha(x)\partial^\alpha,
$$

and its principal symbol is the homogeneous polynomial

$$
\sigma_L(x,\xi)=\sum_{|\alpha|=m}a_\alpha(x)\xi^\alpha.
$$

Some authors include factors of $i$ by replacing $\partial_\mu$ with $i\xi_\mu$ or $-ip_\mu$. For classification, those factors do not change the characteristic set in any essential way. What matters is the highest-derivative polynomial and where it degenerates.

For a system of equations, the coefficients $a_\alpha(x)$ are matrices, and ellipticity or hyperbolicity is tested using the matrix symbol. This is where gauge theory immediately becomes more subtle: gauge redundancies often make the symbol degenerate until one fixes a gauge or quotients by gauge transformations.

For a second-order scalar operator,

$$
L=\sum_{i,j=1}^n a^{ij}(x)\partial_i\partial_j+
\text{lower-order terms},
$$

the principal symbol is

$$
\sigma_L(x,\xi)=a^{ij}(x)\xi_i\xi_j.
$$

Thus the classification is controlled by the quadratic form $a^{ij}\xi_i\xi_j$.

## Elliptic equations

An operator is elliptic, in the scalar case, if

$$
\sigma_L(x,\xi)\ne0
\qquad
\text{for every }\xi\ne0.
$$

For a matrix-valued operator, one asks that the principal symbol be invertible for every nonzero real covector:

$$
\det \sigma_L(x,\xi)\ne0,
\qquad \xi\ne0.
$$

The model example is

$$
L=-\Delta+m^2.
$$

Its principal symbol is

$$
|\xi|^2,
$$

which vanishes only at $\xi=0$. Therefore the operator is elliptic.

Elliptic equations have no real characteristic directions. Informally, disturbances do not propagate along a cone; the solution is constrained globally. This is why elliptic equations naturally ask for boundary data rather than initial data. On a bounded region $\Omega$, a typical Dirichlet problem is

$$
\begin{aligned}
(-\Delta+m^2)u&=f &&\text{in }\Omega,\\
u|_{\partial\Omega}&=g &&\text{on }\partial\Omega.
\end{aligned}
$$

The boundary condition is not merely a way to choose one solution from many. It helps define the operator.

Elliptic operators are also smoothing. Roughly, if $Lu=f$ and the coefficients and boundary are regular enough, then $u$ is two derivatives smoother than $f$ in the interior for a second-order elliptic operator. This is the analytic reason elliptic Green functions have controlled short-distance singularities and why heat-kernel coefficients are local geometric invariants.

### Elliptic equations in QFT

Euclidean free scalar theory uses the positive operator

$$
L_E=-\Delta_E+m^2.
$$

The Euclidean Green function solves

$$
(-\Delta_x+m^2)G_E(x,y)=\delta^{(d)}(x-y).
$$

The Gaussian path integral formally gives

$$
Z[J]\propto (\det L_E)^{-1/2}
\exp\left(\frac12\int d^dx\,d^dy\,J(x)G_E(x,y)J(y)\right),
$$

up to normalization and regularization. The same elliptic operator controls one-loop determinants around instantons, heat-kernel expansions, zeta-regularized determinants, and many Euclidean correlation functions.

Gauge theory adds one classic caveat. The Euclidean Yang–Mills quadratic fluctuation operator before gauge fixing has zero directions from infinitesimal gauge transformations. After choosing a suitable gauge, one obtains an elliptic operator on the physical fluctuation problem plus ghost operators. This is the PDE face of Faddeev–Popov gauge fixing.

## Hyperbolic equations

Hyperbolic equations have characteristic directions. The simplest model is the wave equation

$$
(\partial_t^2-\Delta)u=f.
$$

The principal symbol is

$$
\tau^2-|\boldsymbol\xi|^2.
$$

It vanishes on the cone

$$
\tau^2=|\boldsymbol\xi|^2.
$$

That cone is the local shadow of causal propagation. Singularities and waves can travel along characteristic directions.

For the Klein–Gordon equation in our mostly-minus convention,

$$
(\Box+m^2)\phi=J,
\qquad
\Box=\partial_t^2-\nabla^2,
$$

the mass term does not affect the principal symbol. The characteristic cone is still the light cone.

Hyperbolic equations naturally ask for initial data on a Cauchy surface. For a second-order equation, the data are usually

$$
\phi(0,\mathbf x)=\phi_0(\mathbf x),
\qquad
\partial_t\phi(0,\mathbf x)=\pi_0(\mathbf x).
$$

The solution, when the problem is well posed, is determined in the domain of dependence of the initial surface. This is the PDE version of causality.

### Hyperbolic equations in QFT

The free Lorentzian scalar field satisfies

$$
(\Box+m^2)\phi=0.
$$

For plane waves with the site convention $e^{-ip\cdot x}$,

$$
\phi(x)=e^{-iEt+i\mathbf p\cdot\mathbf x},
$$

one gets

$$
(-E^2+\mathbf p^2+m^2)\phi=0,
$$

so

$$
E^2=\mathbf p^2+m^2.
$$

The propagator denominator is controlled by the same mass shell,

$$
p^2-m^2=0.
$$

But the inverse is not unique. The symbols

$$
\frac1{p^2-m^2},
\qquad
\frac1{p^2-m^2+i\epsilon},
\qquad
\frac1{(p^0+i\epsilon)^2-\mathbf p^2-m^2}
$$

represent different distributions or different pole prescriptions. Retarded, advanced, principal-value, and Feynman inverses solve related equations but answer different physical questions. Classical response wants retarded or advanced kernels. Time-ordered perturbative amplitudes want the Feynman propagator.

The slogan is:

$$
\text{hyperbolic operator} + \text{pole prescription}
\ne
\text{mere algebraic reciprocal}.
$$

## Parabolic equations

Parabolic equations describe heat-like evolution. The model example is

$$
(\partial_s-\Delta)u=0,
\qquad s\ge0.
$$

Here $s$ is not usually physical Lorentzian time in QFT. It is heat time, diffusion time, or Schwinger proper time. The equation is first order in $s$ and elliptic in the spatial variables.

A more operator-theoretic form is

$$
(\partial_s+A)u=0,
$$

where $A$ is a positive elliptic operator. The solution is

$$
u(s)=e^{-sA}u(0).
$$

The kernel

$$
K(s;x,y)=\langle x|e^{-sA}|y\rangle
$$

solves

$$
(\partial_s+A_x)K(s;x,y)=0,
\qquad
K(0;x,y)=\delta(x-y).
$$

Parabolic equations smooth forward in $s$. For the heat equation on $\mathbb R^d$,

$$
K(s;x,y)=\frac1{(4\pi s)^{d/2}}
\exp\left[-\frac{|x-y|^2}{4s}\right],
\qquad s>0.
$$

Even if the initial data are rough, the solution becomes smooth for positive $s$. This smoothing is why heat kernels are so good at exposing ultraviolet structure: small $s$ probes short distances, while positive $s$ regularizes high eigenvalues.

### Parabolic equations in QFT

The heat kernel appears in functional determinants through the formal identity

$$
\log\det A
=
\operatorname{Tr}\log A
=
-\int_0^\infty\frac{ds}{s}\operatorname{Tr}e^{-sA},
$$

with regularization understood. Small $s$ controls UV divergences. Large $s$ is sensitive to zero modes and infrared behavior.

The Schwinger representation of a Euclidean inverse is

$$
A^{-1}=\int_0^\infty ds\,e^{-sA},
$$

again when the spectrum of $A$ is positive and the integral is defined appropriately. This turns an elliptic Green function into an integral over parabolic heat flow.

This is one of the most efficient bridges in QFT:

$$
\text{elliptic operator}
\longrightarrow
\text{heat kernel}
\longrightarrow
\text{determinant, anomaly, effective action}.
$$

## Wick rotation changes type

In Lorentzian signature, the Klein–Gordon operator is hyperbolic:

$$
\Box+m^2=\partial_t^2-\nabla^2+m^2.
$$

After Wick rotation $t=-i\tau$, the Euclidean quadratic operator is elliptic:

$$
L_E=-\partial_\tau^2-\nabla^2+m^2
=-\Delta_E+m^2.
$$

This change of type is the reason Euclidean path integrals often behave like statistical-mechanical partition functions rather than real-time evolution amplitudes.

But this statement has caveats. Analytic continuation is cleanest for static or flat backgrounds and carefully chosen correlation functions. In curved spacetime, finite temperature, nontrivial topology, real-time response, or gauge theories with constraints, Wick rotation may require additional structure. The moral is not “Euclidean equals Lorentzian.” The moral is “Euclidean and Lorentzian problems are related only after specifying the analytic continuation and the state or boundary conditions.”

## Characteristics and singularities

For a scalar operator, the characteristic set is roughly

$$
\operatorname{Char}(L)=\{(x,\xi):\sigma_L(x,\xi)=0,\ \xi\ne0\}.
$$

Elliptic operators have empty real characteristic set. This is why they tend to smooth.

Hyperbolic operators have nonempty characteristic sets. Singularities can propagate along characteristic curves or bicharacteristics. In flat spacetime, these are the light-cone directions for wave equations. In curved spacetime, the principal symbol of a normally hyperbolic operator is controlled by the Lorentzian metric,

$$
\sigma_L(x,\xi)=g^{\mu\nu}(x)\xi_\mu\xi_\nu,
$$

so the characteristic set is the null cone.

Parabolic operators are subtler because the time derivative and spatial derivatives have different orders under parabolic scaling. For the heat equation, the natural scaling is

$$
s\mapsto \lambda^2s,
\qquad
x\mapsto \lambda x.
$$

That scaling is the reason heat kernels have the characteristic prefactor $s^{-d/2}$.

## First-order equations and systems

Not every QFT equation is second order. The Dirac equation is first order:

$$
(i\gamma^\mu\partial_\mu-m)\psi=0.
$$

Its principal symbol is matrix-valued:

$$
\sigma_D(x,\xi)=\gamma^\mu\xi_\mu.
$$

The determinant vanishes on the light cone because the Clifford relation implies the square of the symbol is proportional to $\xi^2$. Thus the Dirac equation is hyperbolic in Lorentzian signature. In Euclidean signature, the Dirac operator is elliptic.

Maxwell and Yang–Mills equations are also systems, and gauge redundancy makes their symbols degenerate. Gauge fixing is not merely algebraic housekeeping; it changes the PDE problem into one with a usable inverse.

## Mixed type and constraints

Real field theories often combine different types. Examples include:

| Situation | PDE behavior |
|---|---|
| Maxwell theory in Coulomb gauge | wave equations plus an elliptic Gauss constraint |
| Euclidean gauge theory before gauge fixing | elliptic-looking but symbol-degenerate |
| Schrödinger equation | first-order time evolution with elliptic spatial Hamiltonian |
| hydrodynamics | hyperbolic, parabolic, or mixed depending on approximation |
| nonlinear equations | type may depend on the solution itself |

The classification is therefore a starting diagnostic, not a verdict from the math police. Still, it prevents a huge number of mistakes. You do not solve the wave equation by imposing arbitrary boundary data on all sides of a spacetime box unless you know exactly which boundary-value problem you mean. You do not invert a gauge operator before dealing with its null directions. You do not treat heat time as if it were unitary time.

## Common pitfalls

**Pitfall 1: Calling every inverse a Green function without a prescription.** For hyperbolic operators, the inverse depends on support or pole prescription. Retarded, advanced, Feynman, and Euclidean kernels are not the same object.

**Pitfall 2: Forgetting that mass terms do not change the principal type.** The Klein–Gordon mass changes dispersion and infrared behavior, but the principal symbol and characteristic cone are the same as for the wave operator.

**Pitfall 3: Thinking elliptic means “time independent.”** Ellipticity is a property of the principal symbol. Euclidean spacetime operators can include a Euclidean time coordinate and still be elliptic.

**Pitfall 4: Treating Wick rotation as automatic.** Analytic continuation needs assumptions about singularities, states, boundary conditions, and backgrounds.

**Pitfall 5: Ignoring gauge degeneracy.** Gauge-invariant field equations often have degenerate symbols. One must fix gauge, quotient gauge directions, or work with gauge-invariant variables before expecting an inverse.

**Pitfall 6: Confusing parabolic smoothing with physical dissipation.** Heat-kernel time is often an auxiliary mathematical parameter. Its smoothing properties are real, but they are not automatically real-time thermalization.

## Exercises

### Exercise 1: Classify three constant-coefficient equations

Classify the following equations by principal type:

$$
(1)\quad u_{xx}+u_{yy}=f,
$$

$$
(2)\quad u_{tt}-u_{xx}=f,
$$

$$
(3)\quad u_t-u_{xx}=0.
$$

<details><summary><strong>Solution</strong></summary>

For $(1)$, the principal symbol is

$$
\xi_x^2+\xi_y^2.
$$

It vanishes only when $\xi=0$, so the equation is elliptic.

For $(2)$, the principal symbol is

$$
\tau^2-\xi^2.
$$

It vanishes on the real cone $\tau=\pm\xi$, so the equation is hyperbolic.

For $(3)$, the equation is first order in $t$ and second order elliptic in $x$. It is the heat equation, so it is parabolic.

</details>

### Exercise 2: The mass term does not change the type

Show that the Klein–Gordon equation

$$
(\partial_t^2-\nabla^2+m^2)\phi=0
$$

has the same principal symbol as the wave equation.

<details><summary><strong>Solution</strong></summary>

The principal symbol only keeps the highest-derivative terms. The mass term $m^2\phi$ has no derivatives, so it is lower order.

The principal part is

$$
\partial_t^2-\nabla^2,
$$

and the principal symbol is

$$
\tau^2-|\boldsymbol\xi|^2.
$$

Thus the characteristic cone is

$$
\tau^2=|\boldsymbol\xi|^2,
$$

independent of $m$.

</details>

### Exercise 3: Euclidean Klein–Gordon is elliptic

Starting from the Euclidean operator

$$
L_E=-\partial_\tau^2-\nabla^2+m^2,
$$

show that it is elliptic.

<details><summary><strong>Solution</strong></summary>

The principal part is

$$
-\partial_\tau^2-\nabla^2.
$$

Up to an overall sign, the principal symbol is

$$
\xi_\tau^2+|\boldsymbol\xi|^2.
$$

This vanishes only if

$$
\xi_\tau=0,
\qquad
\boldsymbol\xi=0.
$$

Therefore the principal symbol is nonzero for every nonzero covector, and the operator is elliptic. The mass term is lower order and does not affect ellipticity.

</details>

### Exercise 4: Heat kernel solves a parabolic equation

Let

$$
K(s;x,y)=\frac1{(4\pi s)^{d/2}}
\exp\left[-\frac{|x-y|^2}{4s}\right]
$$

for $s>0$. Show that

$$
(\partial_s-\Delta_x)K(s;x,y)=0.
$$

<details><summary><strong>Solution</strong></summary>

Set $r^2=|x-y|^2$. Then

$$
\partial_sK=K\left(-\frac d{2s}+\frac{r^2}{4s^2}\right).
$$

Also

$$
\partial_{x_i}K=-\frac{x_i-y_i}{2s}K,
$$

so

$$
\partial_{x_i}^2K=
\left(-\frac1{2s}+\frac{(x_i-y_i)^2}{4s^2}\right)K.
$$

Summing over $i$ gives

$$
\Delta_xK=K\left(-\frac d{2s}+\frac{r^2}{4s^2}\right).
$$

Therefore

$$
\partial_sK=\Delta_xK,
$$

or equivalently

$$
(\partial_s-\Delta_x)K=0.
$$

</details>

### Exercise 5: Gauge degeneracy in Maxwell theory

In Euclidean flat space, consider the quadratic Maxwell action

$$
S[A]=\frac14\int d^dx\,F_{\mu\nu}F_{\mu\nu}.
$$

The quadratic operator on $A_\mu$ is formally

$$
L_{\mu\nu}=-\delta_{\mu\nu}\Delta+\partial_\mu\partial_\nu.
$$

Show that its Fourier symbol has a null direction proportional to $p_\nu$.

<details><summary><strong>Solution</strong></summary>

In Fourier space, $\partial_\mu\mapsto ip_\mu$ up to the convention-dependent sign, and the symbol is proportional to

$$
\sigma_{\mu\nu}(p)=p^2\delta_{\mu\nu}-p_\mu p_\nu.
$$

Acting on $p_\nu$ gives

$$
\sigma_{\mu\nu}(p)p_\nu
=p^2p_\mu-p_\mu p_\nu p_\nu
=p^2p_\mu-p_\mu p^2=0.
$$

Thus the longitudinal direction is a null direction of the symbol. It corresponds to infinitesimal gauge transformations $A_\mu\mapsto A_\mu+\partial_\mu\lambda$. Gauge fixing removes this degeneracy and produces an invertible operator on the appropriate space.

</details>

## References

For PDE classification and principal symbols, see Evans, *Partial Differential Equations*; Folland, *Introduction to Partial Differential Equations*; Taylor, *Partial Differential Equations*; Hörmander, *The Analysis of Linear Partial Differential Operators*; and Courant and Hilbert, *Methods of Mathematical Physics*. For wave equations and hyperbolic operators on Lorentzian manifolds, see Bär, Ginoux, and Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*. For elliptic operators, heat kernels, and determinants in mathematical physics, see Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*; Vassilevich, *Heat Kernel Expansion: User’s Manual*; and Reed and Simon, *Methods of Modern Mathematical Physics*. For QFT usage, compare standard treatments of propagators, Wick rotation, heat kernels, determinants, and gauge fixing in Srednicki, Zee, Weinberg, Coleman, Schwartz, Zinn-Justin, Altland–Simons, Marino, and Burgess.

## Version history

- 2026-06-25: Initial polished draft.
