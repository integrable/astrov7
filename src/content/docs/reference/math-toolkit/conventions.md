---
title: "Mathematical Conventions"
description: "Mathematical notation and normalization conventions for analysis, distributions, functional derivatives, geometry, topology, Lie algebras, Clifford algebras, and operators in the Mathematical Toolkit volume."
sidebar:
  label: "Conventions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Consistent with the site-wide conventions page and standard conventions in QFT, geometry, topology, and mathematical physics references."
topics:
  - mathematical conventions
  - distributions
  - Fourier transforms
  - functional derivatives
  - differential forms
  - Lie algebras
  - Clifford algebras
canonicalTopics:
  - mathematical-conventions
  - qft-conventions
  - distributions
  - differential-geometry
researchStatus:
  established:
    - "The conventions fixed here are standard mathematical and physical normalizations, with explicit translations where common sources differ."
  active:
    - "Some conventions become delicate in chiral dimensional regularization, Euclidean continuation of spinors, infinite-dimensional determinants, and rigorous operator domains."
---

## Summary

This page fixes the mathematical conventions used in the Mathematical Toolkit volume. It is the local companion to the site-wide conventions page: the spacetime default remains mostly-minus metric, natural units, and plane waves $e^{-ip\cdot x}$, while this page records the mathematical notation needed for distributions, functional derivatives, differential forms, bundles, Lie algebras, Clifford algebras, determinants, and operators.

The most important default choices are:

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
c=\hbar=1,
\qquad
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p)
$$

for Lorentzian spacetime Fourier transforms. Euclidean and spatial Fourier transforms use the positive phase in the inverse transform, as explained below.

Conventions are not deep physics, but inconsistent conventions create fake paradoxes. The same symbol can mean a function, distribution, operator, differential form, section of a bundle, regulated determinant, or formal asymptotic series. This page tries to make those types visible before they are used in serious QFT arguments.

## Prerequisites

You should be comfortable with basic linear algebra, multivariable calculus, and the idea of Fourier transforms. Differential forms, distributions, bundles, Lie algebras, and Clifford algebras are summarized here only as conventions; their conceptual explanations belong to the relevant chapters.

The site-wide conventions page fixes the spacetime metric, state normalization, propagators, spinor conventions, path-integral normalization, and Euclidean continuation. This page does not replace it. It extends it into the mathematical notation used across this volume.

## Core idea

Every formula in QFT has two layers:

| Layer | Typical question |
|---|---|
| Physical object | Is this a field, state, observable, symmetry, current, amplitude, or partition function? |
| Mathematical type | Is this a function, distribution, operator, form, section, representation, determinant, or formal series? |

Many mistakes come from answering only the first question. For example, a propagator may be physically a two-point function, but mathematically it is often a distributional kernel. A gauge field may be physically a force carrier, but geometrically it is a connection. A path integral may be physically a sum over histories, but mathematically it may be a finite-dimensional Gaussian model, a lattice measure, a formal perturbation series, or a rigorously constructed Euclidean measure depending on context.

The default rule is simple: when a convention affects a sign, normalization, orientation, trace, pole prescription, or domain, the page using it should say so before relying on it.

## Setup and conventions

Unless a page says otherwise:

- spacetime is four-dimensional Minkowski space with mostly-minus metric when Lorentzian QFT formulas are being discussed;
- $d$ denotes the dimension of the space being integrated over, which may be Euclidean dimension, spacetime dimension, or a dimensionally regulated value depending on context;
- repeated upper-lower index pairs are summed;
- all manifolds are smooth and second countable when differential geometry is used;
- all vector bundles are smooth complex vector bundles unless a real bundle is explicitly named;
- compact Lie groups are represented with Hermitian generators in physics formulas;
- operator equalities involving unbounded operators are understood on a common dense domain, or distributionally, unless a rigorous page states stronger hypotheses.

The symbol $i$ is the imaginary unit. Roman indices such as $i,j,k$ often denote spatial or Euclidean coordinates; early-alphabet Latin indices such as $a,b,c$ often denote Lie algebra or internal indices. A page should override this explicitly when the notation changes.

## Sets, maps, and vector spaces

We write $x\in X$ for an element of a set and $f:X\to Y$ for a map. The identity map on $X$ is $\operatorname{id}_X$. Composition is written $g\circ f$, meaning first $f$ and then $g$.

Vector spaces are over $\mathbb R$ or $\mathbb C$. If the field matters, it will be stated. The dual vector space is $V^*$. For $\alpha\in V^*$ and $v\in V$, the pairing is written

$$
\langle \alpha,v\rangle=\alpha(v).
$$

The tensor product is $V\otimes W$. For vector spaces with bases $e_i$ and $f_a$, a tensor $T\in V\otimes W$ has components $T^{ia}$ in the basis $e_i\otimes f_a$.

Complexification of a real vector space $V$ is

$$
V_\mathbb C=V\otimes_\mathbb R\mathbb C.
$$

This notation matters for real fields, Majorana conditions, Euclidean continuation, and real versus complex representations.

## Indices and tensors

Parentheses and brackets denote symmetrization and antisymmetrization with unit weight:

$$
T_{(\mu\nu)}=\frac12(T_{\mu\nu}+T_{\nu\mu}),
\qquad
T_{[\mu\nu]}=\frac12(T_{\mu\nu}-T_{\nu\mu}).
$$

For three indices,

$$
T_{[\mu\nu\rho]}
=\frac{1}{3!}\sum_{\sigma\in S_3}\operatorname{sgn}(\sigma)
T_{\sigma(\mu)\sigma(\nu)\sigma(\rho)}.
$$

The Kronecker delta is $\delta^i{}_j$. The generalized antisymmetric Kronecker delta is

$$
\delta^{\mu_1\cdots\mu_k}_{\nu_1\cdots\nu_k}
=k!\,\delta^{[\mu_1}{}_{\nu_1}\cdots\delta^{\mu_k]}{}_{\nu_k}.
$$

Indices are raised and lowered using the metric or bilinear form explicitly appropriate to the problem. On Minkowski spacetime,

$$
V_\mu=\eta_{\mu\nu}V^\nu,
\qquad
V^\mu=\eta^{\mu\nu}V_\nu.
$$

On an abstract vector bundle with fiber metric $h$, the same visual operation may mean $v_i=h_{ij}v^j$. A page using several metrics should name them; using the same letter $g$ for every metric is traditional, not merciful.

## Fourier transforms

For Lorentzian spacetime, the default transform is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
\qquad
\int_p=\int\frac{d^4p}{(2\pi)^4}.
$$

With $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$,

$$
e^{-ip\cdot x}=e^{-ip^0t+i\mathbf p\cdot\mathbf x},
\qquad
i\partial_\mu e^{-ip\cdot x}=p_\mu e^{-ip\cdot x}.
$$

For Euclidean $d$-dimensional analysis and spatial Fourier transforms, the default convention is

$$
f(x)=\int_k e^{ik\cdot x}\widehat f(k),
\qquad
\widehat f(k)=\int d^dx\,e^{-ik\cdot x}f(x),
\qquad
\int_k=\int\frac{d^dk}{(2\pi)^d}.
$$

Then

$$
\partial_j f(x)=\int_k ik_j e^{ik\cdot x}\widehat f(k),
\qquad
\int_k e^{ik\cdot(x-y)}=\delta^{(d)}(x-y).
$$

The two conventions are compatible: the Lorentzian convention is adapted to positive-energy plane waves $e^{-ip\cdot x}$, while the Euclidean convention is adapted to the standard inverse transform used in analysis and spatial momentum integrals.

For convolution in Euclidean or spatial variables,

$$
(f*g)(x)=\int d^dy\,f(x-y)g(y),
\qquad
\widehat{f*g}(k)=\widehat f(k)\widehat g(k).
$$

A page must state any nonstandard convention, especially if all factors of $2\pi$ are split symmetrically between the transform and inverse transform.

## Distributions

A distribution $T$ is written as a pairing with a test function $\varphi$:

$$
\langle T,\varphi\rangle.
$$

If $T$ is represented by an ordinary locally integrable function $f$, then

$$
\langle T_f,\varphi\rangle=\int d^dx\,f(x)\varphi(x).
$$

The delta distribution is normalized by

$$
\langle \delta_y,\varphi\rangle=\varphi(y),
\qquad
\int d^dx\,\delta^{(d)}(x-y)\varphi(x)=\varphi(y).
$$

The derivative of a distribution is defined by integration by parts:

$$
\langle \partial_i T,\varphi\rangle=-\langle T,\partial_i\varphi\rangle.
$$

In particular,

$$
\int d^dx\,\partial_i\delta^{(d)}(x-y)\varphi(x)
=-\partial_i\varphi(y).
$$

The Cauchy principal value distribution is denoted

$$
\operatorname{PV}\frac{1}{x}.
$$

The standard one-dimensional boundary-value identity is

$$
\frac{1}{x\pm i0}=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
$$

This identity is one of the basic bridges between complex analysis, causality, spectral density, and pole prescriptions.

## Functional derivatives

For an ordinary bosonic field $\phi^a(x)$, the functional derivative is normalized by

$$
\frac{\delta \phi^a(x)}{\delta \phi^b(y)}=\delta^a{}_b\,\delta^{(d)}(x-y).
$$

For a functional $F[\phi]$, the variation is written

$$
\delta F
=\int d^dx\,\frac{\delta F}{\delta\phi^a(x)}\,\delta\phi^a(x)
$$

for commuting variations. Thus, if

$$
F[\phi]=\frac12\int d^dx\,d^dy\,\phi(x)K(x,y)\phi(y),
$$

and $K(x,y)=K(y,x)$, then

$$
\frac{\delta F}{\delta\phi(z)}=\int d^dy\,K(z,y)\phi(y).
$$

For a local action

$$
S[\phi]=\int d^dx\,\mathcal L(\phi,\partial_\mu\phi),
$$

the Euler–Lagrange functional derivative is

$$
\frac{\delta S}{\delta\phi^a}
=\frac{\partial\mathcal L}{\partial\phi^a}
-\partial_\mu\left(\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^a)}\right).
$$

If higher derivatives occur in the Lagrangian density, the signs alternate:

$$
\frac{\delta S}{\delta\phi^a}
=\frac{\partial\mathcal L}{\partial\phi^a}
-\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^a)}
+\partial_\mu\partial_\nu\frac{\partial\mathcal L}{\partial(\partial_\mu\partial_\nu\phi^a)}-\cdots.
$$

For Grassmann-odd fields and sources, left and right derivatives differ by signs. Pages using fermionic functional derivatives will state the left/right convention before deriving signs. The default Berezin-integral pages use left derivatives for source differentiation unless a formula explicitly displays a right derivative.

## Measures and path-integral notation

Finite-dimensional integrals use ordinary measures such as $d^nx$, $d^nz$, or $d\mu(x)$. Infinite-dimensional measures are written formally as $\mathcal D\phi$, $\mathcal D\psi\,\mathcal D\overline\psi$, or $\mathcal DA$.

The notation $\mathcal D\phi$ does not by itself define a measure. Depending on context, it may mean:

| Notation | Possible meaning |
|---|---|
| $\mathcal D\phi$ in a Gaussian derivation | A formal continuum limit of finite-dimensional Gaussian integrals. |
| $\mathcal D\phi$ in perturbation theory | A mnemonic for Wick contractions and Feynman rules. |
| $\mathcal D\phi$ on a lattice | A genuine finite-dimensional product measure before the continuum limit. |
| $\mathcal D\phi$ in constructive or Euclidean QFT | A probability measure or generalized measure whose existence is part of the problem. |

Measure normalizations may cancel from normalized correlators, but they can matter for determinants, anomalies, localization, finite-temperature partition functions, and gravitational or curved-space applications.

## Differential forms

A $k$-form on a smooth manifold $M$ is written

$$
\omega=\frac{1}{k!}\omega_{\mu_1\cdots\mu_k}\,
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_k}.
$$

The exterior derivative is

$$
d\omega
=\frac{1}{k!}\partial_\nu\omega_{\mu_1\cdots\mu_k}\,
 dx^\nu\wedge dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_k}.
$$

It satisfies

$$
d^2=0,
\qquad
d(\alpha\wedge\beta)=d\alpha\wedge\beta+(-1)^p\alpha\wedge d\beta
$$

when $\alpha$ is a $p$-form.

The interior product with a vector field $X$ is $\iota_X$. If

$$
X=X^\mu\partial_\mu,
\qquad
\omega=\frac{1}{k!}\omega_{\mu_1\cdots\mu_k}dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_k},
$$

then

$$
\iota_X\omega
=\frac{1}{(k-1)!}X^\nu\omega_{\nu\mu_2\cdots\mu_k}
 dx^{\mu_2}\wedge\cdots\wedge dx^{\mu_k}.
$$

The Lie derivative of forms is defined by Cartan's formula:

$$
\mathcal L_X=d\iota_X+\iota_Xd.
$$

If $M$ is oriented, Stokes' theorem is written

$$
\int_M d\omega=\int_{\partial M}\omega,
$$

where $\partial M$ has the boundary orientation induced by $M$.

## Orientations, epsilon symbols, and Hodge star

The Lorentzian spacetime epsilon convention inherited from the site-wide conventions is

$$
\epsilon^{0123}=+1,
\qquad
\epsilon_{0123}=-1
$$

for mostly-minus metric. In Euclidean oriented coordinates,

$$
\epsilon^{12\cdots d}=+1.
$$

On an oriented pseudo-Riemannian $d$-manifold, the Hodge star is defined by

$$
\alpha\wedge *\beta=\langle\alpha,\beta\rangle\,\operatorname{vol}_g
$$

for forms of the same degree. With $s$ minus signs in the metric signature,

$$
*^2\omega=(-1)^{k(d-k)+s}\omega
$$

on $k$-forms. Thus in Euclidean signature $s=0$, while in four-dimensional mostly-minus Lorentzian signature $s=3$ and $*^2=-1$ on two-forms.

A page involving self-dual forms, instantons, Maxwell theory, or $F\widetilde F$ must state whether the formula is Lorentzian or Euclidean. This is one of the places where copying a formula from a different signature is a tiny sign grenade.

## Manifolds, bundles, and sections

The tangent bundle of $M$ is $TM$, and the cotangent bundle is $T^*M$. A vector bundle is written $E\to M$. Its smooth sections are

$$
\Gamma(M,E).
$$

A field may be an ordinary function $\phi:M\to\mathbb R$, a section $\phi\in\Gamma(M,E)$, a connection on a principal bundle, a spinor section, or a distributional section. Pages should identify the type when it matters.

The pullback of a function, form, or bundle by a map $f:M\to N$ is written $f^*$. The pushforward of a vector field, when defined, is written $f_*$. The notation $df$ may mean the differential map $TM\to TN$ or the exterior derivative of a function depending on context; when both appear, pages should disambiguate.

## Connections and curvature

For an affine connection on $TM$, covariant derivatives are written $\nabla_\mu$. The Riemann tensor convention is

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma
$$

for torsion-free coordinate bases. In components,

$$
R^\rho{}_{\sigma\mu\nu}
=\partial_\mu\Gamma^\rho_{\nu\sigma}
-\partial_\nu\Gamma^\rho_{\mu\sigma}
+\Gamma^\rho_{\mu\lambda}\Gamma^\lambda_{\nu\sigma}
-\Gamma^\rho_{\nu\lambda}\Gamma^\lambda_{\mu\sigma}.
$$

The Ricci tensor and scalar curvature are

$$
R_{\mu\nu}=R^\rho{}_{\mu\rho\nu},
\qquad
R=g^{\mu\nu}R_{\mu\nu}.
$$

Some geometry and relativity sources use the opposite sign for $R^\rho{}_{\sigma\mu\nu}$. Curvature-sign translations should be done at the level of the commutator definition, not by trusting a memory of which author uses which sign.

For gauge theory in physics notation, compact-group generators are Hermitian:

$$
[T^a,T^b]=if^{abc}T^c.
$$

The default matter covariant derivative is

$$
D=d+igA^aT^a,
$$

or in components,

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

The curvature is defined by

$$
D^2=igF^aT^a,
$$

with

$$
F^a=dA^a-\frac{g}{2}f^{abc}A^b\wedge A^c,
$$

or

$$
F^a_{\mu\nu}=\partial_\mu A^a_\nu-\partial_\nu A^a_\mu-gf^{abc}A^b_\mu A^c_\nu.
$$

The common mathematical convention uses an anti-Hermitian connection

$$
\mathcal A=igA^aT^a,
\qquad
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=igF^aT^a.
$$

This translation is harmless if done consistently and catastrophic if done halfway.

## Lie algebra traces and representation data

For compact simple Lie groups in physics normalization,

$$
\operatorname{tr}_R(T_R^aT_R^b)=T(R)\delta^{ab},
\qquad
T_R^aT_R^a=C_2(R)\mathbf 1_R.
$$

The adjoint quadratic Casimir is

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

For $SU(N)$ with fundamental generators normalized by

$$
\operatorname{tr}_F(T^aT^b)=\frac12\delta^{ab},
$$

we use

$$
T(F)=\frac12,
\qquad
C_2(F)=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

Pages involving beta functions, anomalies, current two-point functions, or representation tables must state any deviation from this trace normalization.

## Clifford algebras and spinors

Lorentzian gamma matrices satisfy

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1.
$$

Slash notation is written without unsupported commands:

$$
p\!\!/=\gamma^\mu p_\mu,
\qquad
A\!\!/=\gamma^\mu A_\mu.
$$

The chirality matrix in four-dimensional Lorentzian signature is

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3.
$$

Euclidean Clifford algebras use

$$
\{\gamma_E^i,\gamma_E^j\}=2\delta^{ij}\mathbf 1.
$$

The continuation between Lorentzian and Euclidean spinors is convention-sensitive. Pages that Wick rotate spinors, impose Majorana conditions, or use chiral projectors in dimensional regularization must state their convention locally.

## Operators, domains, and spectra

In finite-dimensional linear algebra, an operator is just a linear map. In quantum theory and analysis, many important operators are unbounded. For an unbounded operator $A$ on a Hilbert space $\mathcal H$, the domain is written

$$
\operatorname{Dom}(A)\subset\mathcal H.
$$

The adjoint $A^\dagger$, the closure $\overline A$, and self-adjointness depend on domains. Symmetric is not the same as self-adjoint:

$$
\langle A\psi,\chi\rangle=\langle\psi,A\chi\rangle
\quad\text{on }\operatorname{Dom}(A)
$$

is weaker than $A=A^\dagger$ as operators with equal domains.

The spectrum of $A$ is $\sigma(A)$. The resolvent is

$$
R_A(z)=(A-z)^{-1},
$$

when it exists as a bounded operator. Spectral densities, Green functions, propagators, and heat kernels are different ways of packaging spectral information, often after analytic continuation or distributional boundary values.

## Determinants and regularization

For a finite-dimensional matrix $M$, $\det M$ has its ordinary meaning. For an infinite-dimensional operator $\mathcal O$, the notation

$$
\det\mathcal O
$$

is formal until a regularization is specified. Common possibilities include cutoff regularization, zeta regularization, heat-kernel regularization, dimensional regularization in perturbation theory, Pauli–Villars regularization, and lattice regularization.

The trace log identity

$$
\log\det M=\operatorname{Tr}\log M
$$

is reliable for finite-dimensional matrices with an appropriate branch of the logarithm. In infinite dimensions it becomes a definition only after regularization.

Dimensional regularization writes

$$
d=4-\epsilon
$$

or sometimes $d=4-2\epsilon$, depending on the perturbative convention. The renormalization scale is denoted $\mu$. Pages using dimensional regularization must state which epsilon convention is in force.

## Common pitfalls

**Treating distributions as functions.** The delta function is not a spike-shaped ordinary function in the formulas on this site. It is a distribution defined by how it acts on test functions. Products such as $\delta(x)^2$ are undefined unless a specific regularization or algebra of generalized functions is introduced.

**Changing Fourier conventions mid-calculation.** The phase choice and the placement of $(2\pi)^d$ factors determine the signs of derivative operators and delta functions. When comparing sources, translate the transform pair before comparing propagators or Green functions.

**Ignoring boundary terms in variational problems.** The functional derivative only gives the bulk Euler–Lagrange expression after boundary terms are controlled. Gauge theory, gravity, Hamiltonian mechanics, and soliton problems often live or die by these terms.

**Confusing Hermitian and anti-Hermitian gauge conventions.** Physicists often use Hermitian generators and write $D=d+igA^aT^a$. Mathematicians often put the factor of $i$ into the connection. The curvature signs and characteristic-class formulas must be translated together.

**Assuming every symmetric operator is self-adjoint.** Quantum Hamiltonians, Dirac operators, Laplacians on singular spaces, and boundary-value problems require domain choices. A formal integration-by-parts identity is not enough to define unitary time evolution.

**Wick rotating geometry too casually.** Euclidean and Lorentzian signatures differ in Hodge-star signs, spinor reality conditions, gamma-matrix conventions, and positivity properties. Scalar integrals are the easy case, not the general rule.

## Relations to other pages

- [Mathematical Toolkit](/math-toolkit/) explains how this conventions page fits into the volume.
- Analysis, Distributions, and Fourier Methods develops the distribution and Fourier conventions used here.
- Calculus of Variations and Phase Space develops functional derivatives, boundary terms, symplectic forms, and Poisson brackets.
- Geometry of Fields develops forms, manifolds, bundles, connections, curvature, spin structures, and Dirac operators.
- Lie Groups, Lie Algebras, and Representations develops trace normalizations, Casimirs, roots, weights, and representation data.
- Clifford Algebras and Spinors develops gamma matrices, spin groups, bilinears, Fierz identities, and spinorial representations.
- Functional Analysis and Spectral Theory develops operator domains, self-adjointness, spectral measures, trace-class operators, and rigged Hilbert spaces.

## Research status

The conventions on this page are established choices, not research claims. The formulas are standard once the choices are fixed.

The active issues begin when these conventions meet subtle structures: chiral fermions in dimensional regularization, nonperturbative path-integral measures, infinite-dimensional determinants, reflection positivity, Lorentzian versus Euclidean spinors, gauge fixing on spaces with Gribov copies, and operator domains in interacting theories. Later pages should identify which statements are formal, perturbative, regulated, or theorem-level.

## Exercises

### Exercise 1: Distributional derivative

Show that

$$
\partial_x\delta(x-y)=-\partial_y\delta(x-y)
$$

as distributions.

<details>
<summary><strong>Solution</strong></summary>

Test against a smooth compactly supported function $\varphi(x,y)$. For the left-hand side,

$$
\langle \partial_x\delta(x-y),\varphi\rangle
=-\int dx\,\partial_x\varphi(x,x).
$$

For the right-hand side,

$$
\langle -\partial_y\delta(x-y),\varphi\rangle
=\int dy\,\partial_y\varphi(y,y),
$$

where the derivative acts on the second argument before setting the arguments equal. Equivalently, use the identity $\delta(x-y)=\delta(y-x)$ and the chain rule: differentiating the argument with respect to $x$ gives the opposite sign from differentiating with respect to $y$. Thus the two distributions agree.

A quick one-variable check is to let the distribution act on a test function $f(x)$ with $y$ fixed:

$$
\int dx\,\partial_x\delta(x-y)f(x)=-f'(y),
$$

while

$$
\int dx\,[-\partial_y\delta(x-y)]f(x)
=-\partial_y f(y)=-f'(y).
$$

</details>

### Exercise 2: Functional derivative of a kinetic term

Let

$$
S[\phi]=\frac12\int d^dx\,\partial_i\phi\,\partial_i\phi.
$$

Assume boundary terms vanish. Compute $\delta S/\delta\phi(x)$.

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S=\int d^dx\,\partial_i\phi\,\partial_i\delta\phi.
$$

Integrating by parts gives

$$
\delta S=-\int d^dx\,(\partial_i\partial_i\phi)\delta\phi.
$$

Therefore

$$
\frac{\delta S}{\delta\phi(x)}=-\partial_i\partial_i\phi(x)=-\nabla^2\phi(x).
$$

This is the Euclidean-signature version. In Lorentzian signature the kinetic term and metric signs must be handled with the spacetime convention.

</details>

### Exercise 3: Symmetrization weight

Using the convention of unit-weight antisymmetrization, verify that

$$
\partial_{[\mu}A_{\nu]}=\frac12(\partial_\mu A_\nu-\partial_\nu A_\mu).
$$

Why is the Abelian field strength usually written as $F_{\mu\nu}=2\partial_{[\mu}A_{\nu]}$ rather than $F_{\mu\nu}=\partial_{[\mu}A_{\nu]}$?

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\partial_{[\mu}A_{\nu]}
=\frac12(\partial_\mu A_\nu-\partial_\nu A_\mu).
$$

The standard Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

Therefore

$$
F_{\mu\nu}=2\partial_{[\mu}A_{\nu]}.
$$

The factor of $2$ appears because the bracket convention includes the factor $1/2$. Some authors use unnormalized antisymmetrization; this page does not.

</details>

### Exercise 4: Curvature sign check

With the convention

$$
[\nabla_\mu,\nabla_\nu]V^\rho=R^\rho{}_{\sigma\mu\nu}V^\sigma,
$$

show that a flat connection in coordinates with $\Gamma^\rho_{\mu\nu}=0$ has $R^\rho{}_{\sigma\mu\nu}=0$.

<details>
<summary><strong>Solution</strong></summary>

If $\Gamma^\rho_{\mu\nu}=0$ in the coordinate system under consideration, then $\nabla_\mu=\partial_\mu$ on vector components. Since partial derivatives commute on smooth functions,

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=[\partial_\mu,\partial_\nu]V^\rho=0.
$$

Thus

$$
R^\rho{}_{\sigma\mu\nu}V^\sigma=0
$$

for all vector fields $V$, so

$$
R^\rho{}_{\sigma\mu\nu}=0.
$$

This exercise is trivial, but it fixes the sign convention at the commutator level, which is the safest way to compare curvature formulas.

</details>

### Exercise 5: Physics and mathematics gauge connections

Let the physics covariant derivative be

$$
D=d+igA^aT^a
$$

with Hermitian generators. Define $\mathcal A=igA^aT^a$. Show that

$$
D^2=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

<details>
<summary><strong>Solution</strong></summary>

Act on a field in the chosen representation. Since $D=d+\mathcal A$,

$$
D^2=(d+\mathcal A)(d+\mathcal A)
=d^2+d\mathcal A+\mathcal A\wedge d+\mathcal A\wedge\mathcal A.
$$

As an operator on forms, the cross terms combine into the exterior covariant expression, and $d^2=0$. The resulting curvature two-form is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

With $\mathcal A=igA^aT^a$, this is also

$$
\mathcal F=igF^aT^a,
$$

where

$$
F^a=dA^a-\frac{g}{2}f^{abc}A^b\wedge A^c.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, for Fourier conventions, distributions in propagators, state normalizations, path integrals, gamma matrices, and group theory normalizations.
- A. Zee, *Quantum Field Theory in a Nutshell*, for mostly-minus conventions and physics-first sign checks.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for relativistic normalization, representation theory, Lorentz covariance, gauge theory, and effective actions.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for practical QFT conventions, Standard Model normalization, spinors, regularization, and perturbative checks.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*, for canonical fields, symmetries, functional methods, instantons, large-$N$, and convention-sensitive physics arguments.
- T. Frankel, *The Geometry of Physics*, and M. Nakahara, *Geometry, Topology and Physics*, for differential forms, manifolds, bundles, characteristic classes, and gauge geometry.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field integrals, renormalization, dimensional regularization, and statistical-field-theory conventions.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for Euclidean, many-body, response, topology, and Keldysh-related convention comparisons.

## Version history

- **2026-06-23:** Initial polished draft. Established the local mathematical convention layer for the Mathematical Toolkit volume, consistent with the site-wide metric, Fourier, spinor, path-integral, and Euclidean-continuation conventions.
