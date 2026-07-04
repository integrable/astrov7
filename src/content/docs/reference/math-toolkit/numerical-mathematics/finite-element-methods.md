---
title: "Finite-Element Methods"
description: "A QFT-oriented guide to finite-element discretization, weak forms, Galerkin projection, stiffness and mass matrices, boundary conditions, error estimates, and field-theory applications on irregular domains."
sidebar:
  label: "Finite-Element Methods"
  order: 3
level: Graduate
status: "Polished draft"
source: "Finite-element numerical analysis, variational methods, Sobolev-space weak formulations, elliptic and wave PDEs, lattice and continuum field-theory discretizations, and geometric discretization ideas."
topics:
  - finite elements
  - weak forms
  - Galerkin methods
  - stiffness matrices
  - mass matrices
  - boundary conditions
  - variational discretization
  - numerical field theory
canonicalTopics:
  - finite-element-methods
  - weak-formulation
  - galerkin-projection
  - stiffness-and-mass-matrices
  - variational-discretization
researchStatus:
  established:
    - "Weak formulations, Galerkin projection, element assembly, stiffness and mass matrices, standard interpolation error estimates, and finite-element eigenvalue problems are mature parts of numerical analysis."
  active:
    - "Structure-preserving finite elements, gauge-covariant discretizations, adaptive meshes, finite elements on curved manifolds, finite-element exterior calculus, and high-order field-theory solvers remain active computational and mathematical-physics topics."
---

## Summary

Finite-element methods approximate fields by simple local functions on a mesh. Instead of replacing derivatives by differences at grid points, one first rewrites the continuum problem in **weak form**, chooses a finite-dimensional trial space, and solves the resulting matrix problem.

For a scalar elliptic equation on a domain $\Omega$,

$$
-\nabla\cdot(a(x)\nabla u(x))+m^2(x)u(x)=f(x),
$$

the finite-element workflow is:

```txt
strong differential equation
  → weak variational equation
  → finite-dimensional function space
  → sparse stiffness and mass matrices
  → approximate field, spectrum, or Green function
```

The weak form is obtained by multiplying by a test function $v$ and integrating by parts. For Dirichlet boundary conditions, the standard form is

$$
a(u,v)=\ell(v),
$$

with

$$
a(u,v)=\int_\Omega d^dx\,
\left[a(x)\nabla u\cdot\nabla v+m^2(x)uv\right],
$$

and

$$
\ell(v)=\int_\Omega d^dx\,f v.
$$

The finite-element approximation chooses basis functions $\varphi_i$ and writes

$$
u_h(x)=\sum_i u_i\varphi_i(x).
$$

The weak equation becomes a matrix equation

$$
K_{ij}u_j=F_i,
$$

where

$$
K_{ij}=a(\varphi_j,\varphi_i),
\qquad
F_i=\ell(\varphi_i).
$$

For QFT, the point is bigger than PDE solving. A finite-element discretization is a **variational regulator**. It turns quadratic actions into finite-dimensional Gaussian integrals, inverse operators into matrix inverses, spectra into generalized eigenvalue problems, and irregular boundaries or curved domains into manageable computations.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Finite-element workflow from continuum PDE to weak form, finite space, matrix problem, quadratic action, and propagator.](/figures/math-toolkit/finite-element-weak-form-flow.svg)

<figcaption>

Finite elements start from the weak or variational form. The same bilinear form that defines the classical boundary-value problem also defines the quadratic action $S_h=\frac12u^TKu-J^Tu$ and the finite-dimensional propagator $G_h=K^{-1}$.

</figcaption>
</figure>

## Prerequisites

You should know multivariable calculus, integration by parts, basic linear algebra, and the idea of a boundary-value problem. The pages on finite differences, spectral methods, Green functions, Sobolev spaces, and variational derivatives are useful background, but this page is self-contained enough to read first.

We use real scalar fields for the main examples. Complex fields, spinors, gauge fields, and constrained systems require additional structure, discussed near the end.

## Why finite elements matter in QFT

Finite differences are natural on rectangular lattices. Spectral methods are natural on simple domains with smooth fields. Finite elements are natural when the geometry itself is part of the problem.

They are useful when you face:

| Problem | Why finite elements help |
|---|---|
| irregular boundaries | meshes conform to the boundary |
| curved domains | elements approximate the geometry locally |
| spatially varying coefficients | coefficients are integrated element by element |
| elliptic operators | weak forms give symmetric positive matrices |
| constrained variational problems | trial spaces can encode constraints and boundary data |
| eigenvalue problems | stiffness and mass matrices give controlled Galerkin spectra |
| local refinement | meshes can be refined near defects, boundaries, or singularities |

In QFT language, finite elements are most attractive for Euclidean problems, spectra, instanton fluctuations, finite-volume modes, boundary effects, curved backgrounds, and classical solutions around which one later quantizes.

They are not a free lunch. Translation invariance is usually lost, momentum-space formulas become less convenient, and preserving gauge symmetry or fermion structure takes care.

## Strong form and weak form

Consider the boundary-value problem

$$
Lu=f,
\qquad
L=-\nabla\cdot(a\nabla)+m^2,
$$

on a domain $\Omega$. Suppose, for now, that $u$ satisfies homogeneous Dirichlet boundary conditions,

$$
u|_{\partial\Omega}=0.
$$

The strong form demands enough differentiability that $Lu$ is defined pointwise. The weak form asks only that derivatives exist in an integrated sense.

Multiply by a test function $v$ with $v|_{\partial\Omega}=0$:

$$
\int_\Omega d^dx\,v\left[-\nabla\cdot(a\nabla u)+m^2u\right]
=\int_\Omega d^dx\,vf.
$$

Integrating by parts gives

$$
\int_\Omega d^dx\,a\nabla v\cdot\nabla u
+
\int_\Omega d^dx\,m^2vu
=\int_\Omega d^dx\,vf,
$$

because the boundary term vanishes for Dirichlet test functions. Thus the weak problem is:

> Find $u$ in the allowed function space such that
>
> $$
> a(u,v)=\ell(v)
> $$
>
> for all allowed test functions $v$.

This changes the differentiability requirement. Instead of needing second derivatives of $u$ pointwise, we only need first derivatives of $u$ and $v$ to be square-integrable. This is why Sobolev spaces appear naturally: for the basic scalar elliptic problem, the natural space is $H^1_0(\Omega)$.

## The Galerkin idea

The weak problem is still infinite-dimensional. The finite-element approximation chooses a finite-dimensional subspace

$$
V_h\subset V,
$$

where $h$ measures the mesh size. Then one solves:

> Find $u_h\in V_h$ such that
>
> $$
> a(u_h,v_h)=\ell(v_h)
> $$
>
> for all $v_h\in V_h$.

Choose a basis $\{\varphi_i\}_{i=1}^N$ for $V_h$ and write

$$
u_h=\sum_{j=1}^N u_j\varphi_j.
$$

Testing against $v_h=\varphi_i$ gives

$$
\sum_j a(\varphi_j,\varphi_i)u_j=\ell(\varphi_i).
$$

Define

$$
K_{ij}=a(\varphi_j,\varphi_i),
\qquad
F_i=\ell(\varphi_i),
$$

and obtain

$$
Ku=F.
$$

This is Galerkin projection: the residual $Lu_h-f$ is not forced to vanish pointwise; it is forced to be orthogonal to the finite test space.

## Meshes and basis functions

A mesh divides $\Omega$ into small cells called elements. In one dimension, elements are intervals. In two dimensions, they are often triangles or quadrilaterals. In three dimensions, tetrahedra and hexahedra are common.

The simplest finite elements are continuous piecewise-linear functions. In one dimension with nodes $x_i$, the basis function $\varphi_i$ is the hat function satisfying

$$
\varphi_i(x_j)=\delta_{ij}.
$$

It is linear on each neighboring interval and zero outside the two intervals adjacent to $x_i$.

In higher dimensions, piecewise-linear basis functions are defined similarly on simplices. They equal $1$ at one vertex, $0$ at the other vertices, and vary linearly inside each element.

More generally, finite elements can use piecewise polynomials of degree $p$:

$$
V_h=\{v_h:\ v_h|_T\in\mathbb P_p(T)\text{ for each element }T\}.
$$

Increasing $p$ gives higher-order elements. Refining the mesh decreases $h$. Both are routes to convergence.

## Local element matrices

The practical power of finite elements comes from locality. Basis functions have small support, so most matrix entries vanish. The global stiffness matrix is assembled from element matrices.

For the one-dimensional operator

$$
L=-\frac{d^2}{dx^2}+m^2
$$

on a uniform interval element $e=[x_i,x_{i+1}]$ of length $h$, the two local linear basis functions are

$$
\varphi_1(x)=\frac{x_{i+1}-x}{h},
\qquad
\varphi_2(x)=\frac{x-x_i}{h}.
$$

The derivative part gives the local stiffness matrix

$$
K_e^{(\partial)}
=\frac1h
\begin{pmatrix}
1&-1\\
-1&1
\end{pmatrix}.
$$

The mass term uses the local mass matrix

$$
M_e
=\int_{x_i}^{x_{i+1}}dx\,
\begin{pmatrix}
\varphi_1\varphi_1&\varphi_1\varphi_2\\
\varphi_2\varphi_1&\varphi_2\varphi_2
\end{pmatrix}
=
\frac h6
\begin{pmatrix}
2&1\\
1&2
\end{pmatrix}.
$$

Thus

$$
K_e=K_e^{(\partial)}+m^2M_e.
$$

Each element contributes to the entries associated with its two endpoints. Assembly adds all overlapping element contributions into the global matrix.

## Mass matrices are not optional

Finite differences often identify grid values with coordinate components and use the ordinary Euclidean dot product. Finite elements separate the coefficient vector from the inner product on functions.

For basis functions $\varphi_i$, the $L^2$ inner product is represented by the mass matrix

$$
M_{ij}=\int_\Omega d^dx\,\varphi_i\varphi_j.
$$

Therefore, the discretized inner product is

$$
\langle u_h,v_h\rangle_{L^2}
=u_iM_{ij}v_j.
$$

This matters in eigenvalue problems. The continuum equation

$$
Lu=\lambda u
$$

becomes the generalized eigenvalue problem

$$
Ku=\lambda Mu.
$$

Writing $Ku=\lambda u$ is usually wrong unless a special orthonormal basis or mass-lumped approximation has been chosen.

In QFT, the same point appears in Gaussian integrals. The coordinate measure, the action matrix, and the inner product inherited from the function space are related but not identical pieces of data. Hiding the mass matrix is a classic way to lose factors of $h$.

## Boundary conditions

Boundary conditions are part of the finite-element problem, not afterthoughts.

### Dirichlet conditions

A Dirichlet condition fixes the field value on the boundary:

$$
u|_{\partial\Omega}=g.
$$

For homogeneous Dirichlet conditions, $g=0$, one chooses a trial space whose functions vanish on the boundary. In matrix terms, boundary degrees of freedom are removed or fixed.

For nonhomogeneous Dirichlet data, write

$$
u=w+\tilde u,
$$

where $w$ matches the boundary value and $\tilde u$ vanishes on the boundary. Then solve for $\tilde u$.

### Neumann conditions

A Neumann condition fixes the normal flux:

$$
a\nabla u\cdot n=q
\qquad\text{on }\partial\Omega.
$$

When deriving the weak form, the boundary term is

$$
-\int_{\partial\Omega}dS\,v\,a\nabla u\cdot n.
$$

Depending on the sign convention for outward normal and operator definition, this contributes a boundary linear functional. The important point is that Neumann data enters naturally in the weak form; it is not imposed by deleting nodes.

### Robin conditions

A Robin condition combines field and normal derivative:

$$
a\nabla u\cdot n+\kappa u=q.
$$

It contributes a boundary bilinear term

$$
\int_{\partial\Omega}dS\,\kappa uv
$$

and a boundary source term. Robin conditions are common in spectral problems, heat kernels, and effective boundary actions.

## Finite elements as a field-theory regulator

Consider a Euclidean scalar action

$$
S[\phi]
=\frac12\int_\Omega d^dx\,
\left[a(x)\nabla\phi\cdot\nabla\phi+m^2(x)\phi^2\right]
-
\int_\Omega d^dx\,J\phi.
$$

Approximate

$$
\phi_h(x)=\sum_i \phi_i\varphi_i(x).
$$

Then the discretized action is

$$
S_h(\phi)
=\frac12\phi_iK_{ij}\phi_j-J_i\phi_i,
$$

where

$$
K_{ij}=\int_\Omega d^dx\,
\left[a\nabla\varphi_i\cdot\nabla\varphi_j+m^2\varphi_i\varphi_j\right],
$$

and

$$
J_i=\int_\Omega d^dx\,J(x)\varphi_i(x).
$$

The finite-dimensional Gaussian integral gives

$$
Z_h[J]
=Z_h[0]\exp\!\left(\frac12J_i(K^{-1})_{ij}J_j\right),
$$

assuming $K$ is positive definite after boundary conditions and zero modes are handled.

The finite-element Green function is

$$
G_h(x,y)
=\sum_{i,j}\varphi_i(x)(K^{-1})_{ij}\varphi_j(y).
$$

This is not the same object as the continuum Green function sampled at nodes. It is the Green function of the projected finite-dimensional theory.

## The variational meaning of the approximation

For symmetric positive elliptic problems, the finite-element solution is often the best approximation in the energy norm. Define

$$
\|w\|_a^2=a(w,w).
$$

If $u$ is the exact weak solution and $u_h\in V_h$ is the Galerkin solution, then Galerkin orthogonality says

$$
a(u-u_h,v_h)=0
\qquad\text{for all }v_h\in V_h.
$$

This implies the best-approximation property

$$
\|u-u_h\|_a
\le
\|u-v_h\|_a
\qquad\text{for all }v_h\in V_h,
$$

for the simplest symmetric coercive case. More generally, Céa’s lemma gives a constant depending on the continuity and coercivity of the bilinear form.

For a QFT reader, the moral is clean: finite elements approximate the variational problem directly. They do not merely approximate the differential equation pointwise.

## Error estimates

For piecewise polynomials of degree $p$ on a sufficiently regular mesh, one expects estimates of the schematic form

$$
\|u-u_h\|_{H^1}
\lesssim
h^p\|u\|_{H^{p+1}},
$$

and, under additional regularity assumptions,

$$
\|u-u_h\|_{L^2}
\lesssim
h^{p+1}\|u\|_{H^{p+1}}.
$$

These estimates say three things.

First, higher-order elements help only if the true solution is smooth enough. Second, mesh refinement helps only if the mesh quality remains controlled. Third, singularities, corners, defects, and discontinuous coefficients can reduce the convergence rate.

This is where adaptive finite elements shine. If the solution is smooth almost everywhere but singular near a boundary corner, vortex core, defect insertion, or interface, one refines the mesh locally instead of wasting degrees of freedom everywhere.

## Mesh quality and conditioning

Bad meshes produce bad numerics. Long, thin, nearly degenerate elements can make matrices ill-conditioned and destroy interpolation quality.

For elliptic problems, the condition number of the stiffness matrix often grows as the mesh is refined. A rough scaling is

$$
\kappa(K)\sim h^{-2},
$$

for simple second-order operators. This affects iterative solvers and numerical stability.

Preconditioning is therefore part of the method, not an optional performance trick. Multigrid, domain decomposition, incomplete factorization, and algebraic preconditioners can decide whether a large finite-element QFT computation is practical.

## Relation to finite differences

On a uniform one-dimensional mesh with piecewise-linear elements, the stiffness matrix for $-d^2/dx^2$ resembles the standard second-difference matrix:

$$
\frac1h
\begin{pmatrix}
2&-1&0&\cdots\\
-1&2&-1&\cdots\\
0&-1&2&\cdots\\
\vdots&\vdots&\vdots&\ddots
\end{pmatrix}.
$$

Finite differences and finite elements can therefore look similar in simple cases. The conceptual difference is that finite differences begin with pointwise derivatives, while finite elements begin with weak forms and finite-dimensional function spaces.

This distinction becomes decisive on irregular domains, curved backgrounds, variable coefficients, and problems where boundary terms are physically important.

## Relation to spectral methods

Spectral methods use global basis functions. Finite elements use local basis functions.

| Feature | Spectral methods | Finite elements |
|---|---|---|
| basis support | global | local |
| matrices | often dense | often sparse |
| best for | smooth fields on simple domains | complex geometry and local refinement |
| convergence | potentially exponential for analytic fields | algebraic in $h$, high order in $p$ |
| boundary geometry | can be awkward | natural with fitted meshes |
| singularities | globally damaging | can be localized by mesh refinement |

High-order finite elements blur the distinction. The $hp$ finite-element method combines local mesh refinement with high-degree polynomials and can achieve very fast convergence for piecewise-analytic solutions.

## Gauge fields and geometry

Gauge fields require more care than scalar fields. A naive componentwise finite-element discretization can break gauge invariance or introduce spurious modes.

There are several strategies.

For charged scalar fields coupled to a background connection $A$, replace ordinary derivatives by covariant derivatives:

$$
D\phi=(d+iA)\phi,
$$

and discretize the weak form

$$
\int_\Omega (D\phi)^*\cdot(D\psi).
$$

For dynamical gauge fields, one must decide whether the fundamental variables are continuum-like differential forms, lattice link variables, or discrete cochains. Finite-element exterior calculus and discrete exterior calculus provide structure-preserving spaces that mimic

$$
d^2=0
$$

and preserve exact sequences. This is important because gauge redundancy is not a numerical nuisance; it is part of the physical phase space.

A rough dictionary is:

| Continuum object | Structure-preserving discretization idea |
|---|---|
| scalar field | nodal finite elements |
| one-form gauge potential | edge elements or cochains |
| field strength | face variables or exterior derivative of edge variables |
| Bianchi identity | discrete $d^2=0$ |
| gauge transformation | exact discrete form |

The details depend strongly on the theory. The safe rule is: if a continuum identity removes unphysical modes, the discretization must know about that identity.

## Fermions and finite elements

Fermions introduce another set of issues. Discretizing the Dirac operator on a mesh can produce analogs of fermion doubling, spurious modes, or broken chiral structure. On curved manifolds one also needs spin structures, frames, and spin connections.

A finite-element treatment of fermions may be useful for background-field spectral problems, Dirac operators on curved domains, or numerical eigenmodes. But for lattice gauge theory, specialized fermion discretizations such as Wilson, staggered, domain-wall, and overlap fermions are designed to handle deep constraints that a naive finite-element Dirac operator may not respect.

The finite-element moral still applies: write the variational problem honestly, choose spaces compatible with the operator, and check which symmetries survive at finite cutoff.

## Nonlinear field equations

Many classical field equations in QFT are nonlinear. A Euclidean bounce, vortex, monopole, soliton, or saddle configuration may solve

$$
\frac{\delta S}{\delta\phi}=0
$$

with nonlinear terms. Finite elements handle this by discretizing the action or weak equation and solving nonlinear algebraic equations.

For example, for

$$
S[\phi]=\int_\Omega d^dx\,
\left[\frac12|\nabla\phi|^2+V(\phi)\right],
$$

the finite-element action is

$$
S_h(\phi_i)=\int_\Omega d^dx\,
\left[\frac12\nabla\phi_h\cdot\nabla\phi_h+V(\phi_h)\right].
$$

The discrete saddle equations are

$$
\frac{\partial S_h}{\partial \phi_i}=0.
$$

Newton’s method then requires the Hessian

$$
H_{ij}=\frac{\partial^2 S_h}{\partial\phi_i\partial\phi_j},
$$

which is the fluctuation operator around the numerical saddle. That same Hessian appears in the one-loop determinant. This is a beautiful place where classical numerical analysis and semiclassical QFT shake hands.

## Finite elements and Green functions

Let $K$ be the finite-element stiffness matrix after boundary conditions. The discrete Green function is the matrix inverse

$$
G=K^{-1}.
$$

If the source is represented by coefficients $F_i$, then

$$
u_i=G_{ij}F_j.
$$

For a point source, one must be careful. The continuum delta distribution is not generally represented by a unit vector at a node. The correct finite-element source is its action on basis functions:

$$
F_i=\int_\Omega d^dx\,\delta(x-y)\varphi_i(x)=\varphi_i(y).
$$

Thus a point source at $y$ is represented by the vector of basis functions evaluated at $y$, not necessarily by a Kronecker delta at the nearest node.

This is the finite-element version of a theme repeated throughout QFT: distributions act on test functions.

## Continuum extrapolation

A finite-element answer depends on the mesh. Physical predictions require control of the limit

$$
h\to0,
$$

and sometimes also

$$
p\to\infty.
$$

For a quantity $Q_h$, one often fits

$$
Q_h=Q+c h^\alpha+\cdots,
$$

where $\alpha$ depends on the element order, observable, solution regularity, and geometry. But the exponent should not be guessed blindly. It should be checked by refinement studies.

For QFT applications, this sits alongside finite-volume extrapolation, regulator dependence, and renormalization. The numerical continuum limit and the physical continuum limit are related but not identical pieces of analysis.

## Common pitfalls

### Pitfall 1: confusing the weak and strong equations

The finite-element solution usually does not satisfy the differential equation pointwise. It satisfies the weak equation in a finite-dimensional test space. That is a feature, not a bug.

### Pitfall 2: dropping the mass matrix

The matrix representing the identity operator in coefficient space is usually $M_{ij}=\int\varphi_i\varphi_j$, not $\delta_{ij}$. Forgetting this corrupts eigenvalues, norms, and Gaussian normalizations.

### Pitfall 3: imposing Neumann data like Dirichlet data

Dirichlet conditions restrict the trial space. Neumann conditions usually appear as boundary terms in the weak form. Treating them the same way is a boundary-condition crime scene.

### Pitfall 4: trusting a pretty mesh

A mesh can look reasonable and still contain bad elements. Conditioning, interpolation quality, and convergence should be checked quantitatively.

### Pitfall 5: assuming symmetries survive discretization

Gauge symmetry, chiral symmetry, supersymmetry, rotational invariance, and topological identities may be broken or deformed by the finite-element space. A numerical regulator must be audited like any other regulator.

### Pitfall 6: treating nodal values as field values without qualification

The finite-element function is the whole combination $u_h=\sum_i u_i\varphi_i$. The coefficients $u_i$ are not always literal point values, especially for non-nodal bases, higher-order bases, or form-valued elements.

## Exercises

### Exercise 1: Local stiffness matrix for linear elements

On an interval $[0,h]$, let

$$
\varphi_1(x)=1-\frac{x}{h},
\qquad
\varphi_2(x)=\frac{x}{h}.
$$

Compute the local stiffness matrix

$$
K_{ab}=\int_0^h dx\,\varphi_a'(x)\varphi_b'(x).
$$

<details><summary><strong>Solution</strong></summary>

The derivatives are

$$
\varphi_1'(x)=-\frac1h,
\qquad
\varphi_2'(x)=\frac1h.
$$

Therefore

$$
K_{11}=\int_0^h dx\,\frac1{h^2}=\frac1h,
$$

$$
K_{22}=\frac1h,
$$

and

$$
K_{12}=K_{21}=\int_0^h dx\,\left(-\frac1h\right)\left(\frac1h\right)=-\frac1h.
$$

Thus

$$
K_e=\frac1h
\begin{pmatrix}
1&-1\\
-1&1
\end{pmatrix}.
$$

</details>

### Exercise 2: Local mass matrix

Using the same basis functions, compute

$$
M_{ab}=\int_0^h dx\,\varphi_a(x)\varphi_b(x).
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
M_{11}=\int_0^h dx\,\left(1-\frac{x}{h}\right)^2=\frac h3,
$$

and

$$
M_{22}=\int_0^h dx\,\left(\frac{x}{h}\right)^2=\frac h3.
$$

The off-diagonal entry is

$$
M_{12}=\int_0^h dx\,\left(1-\frac{x}{h}\right)\frac{x}{h}
=\frac h6.
$$

Therefore

$$
M_e=\frac h6
\begin{pmatrix}
2&1\\
1&2
\end{pmatrix}.
$$

</details>

### Exercise 3: Weak form with a Neumann boundary condition

Let

$$
-u''(x)+m^2u(x)=f(x)
$$

on $[0,L]$, with $u(0)=0$ and $u'(L)=q$. Derive the weak form.

<details><summary><strong>Solution</strong></summary>

Multiply by a test function $v$ with $v(0)=0$:

$$
\int_0^L dx\,v(-u''+m^2u)=\int_0^L dx\,vf.
$$

Integrating the second-derivative term by parts gives

$$
\int_0^L dx\,v(-u'')
=\int_0^L dx\,v'u' - [vu']_0^L.
$$

Since $v(0)=0$ and $u'(L)=q$,

$$
[vu']_0^L=v(L)q.
$$

Thus the weak form is

$$
\int_0^L dx\,(v'u'+m^2vu)
=
\int_0^L dx\,vf+v(L)q,
$$

if the operator and outward-normal convention are taken as above. Different sign conventions for the boundary flux shift the sign of the boundary term, so the normal convention must be stated.

</details>

### Exercise 4: Why eigenvalues need the mass matrix

Let $u_h=\sum_j u_j\varphi_j$ solve the weak eigenvalue equation

$$
a(u_h,v_h)=\lambda\langle u_h,v_h\rangle_{L^2}
$$

for all $v_h\in V_h$. Show that the coefficient vector obeys $Ku=\lambda Mu$.

<details><summary><strong>Solution</strong></summary>

Set $v_h=\varphi_i$. The left side is

$$
a(u_h,\varphi_i)
=\sum_j u_j a(\varphi_j,\varphi_i)
=K_{ij}u_j.
$$

The right side is

$$
\lambda\langle u_h,\varphi_i\rangle_{L^2}
=\lambda\sum_j u_j\int_\Omega d^dx\,\varphi_j\varphi_i
=\lambda M_{ij}u_j.
$$

Therefore

$$
Ku=\lambda Mu.
$$

</details>

## References

- Brenner and Scott, *The Mathematical Theory of Finite Element Methods*.
- Ciarlet, *The Finite Element Method for Elliptic Problems*.
- Ern and Guermond, *Theory and Practice of Finite Elements*.
- Hughes, *The Finite Element Method: Linear Static and Dynamic Finite Element Analysis*.
- Hiptmair, “Finite elements in computational electromagnetism.”
- Arnold, Falk, and Winther, “Finite element exterior calculus.”
- Zienkiewicz, Taylor, and Zhu, *The Finite Element Method*.

## Version history

- **2026-06-27:** First polished draft. Introduces weak forms, Galerkin projection, stiffness and mass matrices, boundary conditions, variational error estimates, Green functions, and QFT applications.
