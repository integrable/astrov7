---
title: "Dirac Operators"
description: "Defines Dirac operators on spinor bundles, explains their local formula, square, zero modes, determinants, index, boundary conditions, and role in QFT."
sidebar:
  label: "Dirac Operators"
  order: 11
level: Advanced
status: "Polished draft"
source: "Standard references on spin geometry, heat kernels, index theory, and QFT on curved backgrounds, including Lawson–Michelsohn, Nakahara, Frankel, Gilkey, Berline–Getzler–Vergne, Eguchi–Gilkey–Hanson, Weinberg, and anomaly-focused QFT treatments."
topics:
  - Dirac operator
  - spinor bundle
  - Clifford action
  - spin connection
  - twisted Dirac operator
  - zero modes
  - index theorem
  - fermion determinant
  - heat kernel
  - boundary conditions
canonicalTopics:
  - dirac-operator
  - spinor-bundle
  - clifford-action
  - spin-connection
  - twisted-dirac-operator
  - fermion-zero-mode
  - index-theorem
  - fermion-determinant
  - eta-invariant
researchStatus:
  established:
    - "On a spin manifold, the Dirac operator is the first-order differential operator obtained by composing a spinor covariant derivative with Clifford multiplication; its square is Laplace type and its chiral index is topological in even Euclidean dimension."
  active:
    - "Modern applications require refined global data: boundary conditions, eta invariants, determinant phases, Spin-c or Pin structures, defects, singular backgrounds, and fermionic path integrals on nontrivial manifolds."
---

## Summary

A Dirac operator is the geometric version of the flat-space operator that appears in the Dirac equation. In flat Minkowski space, in the default mostly-minus convention, one writes

$$
(i\gamma^\mu D_\mu-m)\psi=0.
$$

When an abbreviated Dirac notation is useful, we write

$$
D\!\!\!/\equiv \gamma^\mu D_\mu,
\qquad
(iD\!\!\!/-m)\psi=0.
$$

On a curved or topologically nontrivial manifold, this innocent-looking expression is a whole little ecosystem. One needs a spin structure, a spinor bundle, Clifford multiplication, a spin connection, and possibly a gauge connection. The Dirac operator is the composite object that packages all of that into a first-order differential operator on spinor fields.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Flow diagram showing metric, spin structure, gauge connection, spinor bundle, Clifford action, covariant derivative, Dirac operator, zero modes, determinant, and index.](/figures/math-toolkit/dirac-operator-geometric-flow.svg)

<figcaption>

The Dirac operator is local in appearance but global in construction. Its input is a spinor bundle with Clifford action and a compatible connection; its outputs include equations of motion, zero modes, determinants, indices, and anomalies.

</figcaption>
</figure>

The main lesson is simple:

$$
\text{gamma matrices are local algebra; a Dirac operator is global geometry.}
$$

That distinction is exactly what makes Dirac operators central in fermion path integrals, anomalies, instantons, index theorems, supersymmetric localization, and QFT on curved backgrounds.

## Prerequisites

Read [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/), [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/), and [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) first.

For the local algebra, see [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/), [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/), and [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/). For determinants and regularization, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Pfaffians](/math-toolkit/functional-integrals-determinants/pfaffians/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat-Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

Let $(M,g)$ be an oriented Riemannian manifold, or an oriented time-oriented Lorentzian manifold, equipped with a spin structure. The spin structure gives a spinor bundle

$$
S\to M.
$$

The metric gives a Clifford action

$$
c:T^*M\to \operatorname{End}(S),
$$

satisfying

$$
c(\alpha)c(\beta)+c(\beta)c(\alpha)=2g^{-1}(\alpha,\beta)\operatorname{id}_S.
$$

In a local orthonormal coframe $e^a$, this says

$$
c(e^a)=\gamma^a,
\qquad
\{\gamma^a,\gamma^b\}=2\eta^{ab}.
$$

A spin connection is a connection $\nabla^S$ on $S$ compatible with the Clifford action. Compatibility means that differentiating a Clifford-multiplied spinor can be done in either order:

$$
\nabla^S_X(c(\alpha)\psi)
=c(\nabla_X\alpha)\psi+c(\alpha)\nabla^S_X\psi.
$$

The Dirac operator is the composition

$$
\Gamma(S)
\xrightarrow{\nabla^S}
\Gamma(T^*M\otimes S)
\xrightarrow{c}
\Gamma(S).
$$

In local orthonormal notation,

$$
D\!\!\!/=\gamma^a\nabla^S_{e_a}.
$$

If $e_a{}^\mu$ is the inverse vielbein, this becomes

$$
D\!\!\!/=\gamma^a e_a{}^\mu\nabla^S_\mu.
$$

This is the abstract definition hiding behind the familiar symbol $\gamma^\mu\nabla_\mu$.

## Local formula

Let $e^a{}_{\mu}$ be a vielbein and $e_a{}^\mu$ its inverse. The curved gamma matrices are

$$
\gamma^\mu(x)=e_a{}^\mu(x)\gamma^a,
$$

so that

$$
\{\gamma^\mu(x),\gamma^\nu(x)\}=2g^{\mu\nu}(x).
$$

With

$$
\gamma^{ab}\equiv \frac12[\gamma^a,\gamma^b],
$$

the spinor covariant derivative is locally

$$
\nabla^S_\mu\psi
=\partial_\mu\psi+\frac14\omega_{\mu ab}\gamma^{ab}\psi,
$$

where $\omega_{\mu ab}$ is the spin connection determined by the vielbein and the Levi–Civita connection.

If the spinor also transforms in a representation $R$ of a gauge group with connection $A=A^I_\mu T_I dx^\mu$, the twisted covariant derivative is

$$
\nabla_\mu\psi
=\partial_\mu\psi+\frac14\omega_{\mu ab}\gamma^{ab}\psi+A^I_\mu T_I\psi.
$$

Different communities put factors of $i$ or the gauge coupling into $A_\mu^I T_I$. The invariant statement is that the gauge connection is added to the spin connection on the tensor-product bundle

$$
S\otimes E_R.
$$

The twisted Dirac operator is

$$
D\!\!\!/_{E_R}=\gamma^a e_a{}^\mu
\left(\partial_\mu+\frac14\omega_{\mu bc}\gamma^{bc}+A^I_\mu T_I\right).
$$

In flat space with trivial spin structure and no gauge field,

$$
D\!\!\!/=\gamma^\mu\partial_\mu.
$$

So the curved formula is not a decorative generalization. It is the same operator with all local trivializations and parallel-transport rules exposed.

## Lorentzian and Euclidean versions

In Lorentzian QFT, the classical Dirac action is usually written

$$
S_\psi=\int_M d^dx\,e\,\bar\psi(iD\!\!\!/-m)\psi,
$$

where

$$
e=|\det e^a{}_{\mu}|=\sqrt{|g|},
\qquad
\bar\psi=\psi^\dagger\gamma^0.
$$

The equation of motion is

$$
(iD\!\!\!/-m)\psi=0.
$$

In Lorentzian signature, the Dirac operator is a hyperbolic first-order operator. Propagators require causal choices: Feynman, retarded, advanced, or other boundary conditions. The symbol $(D\!\!\!/)^{-1}$ is not meaningful until those choices are specified.

In Euclidean signature, the Dirac operator is elliptic on a Riemannian spin manifold. That makes spectral theory, heat kernels, determinants, and index theory available. Many QFT calculations therefore rotate to Euclidean signature, study the elliptic operator, and then analytically continue appropriate observables back to Lorentzian signature.

There is one convention trap worth naming. Mathematicians often choose Clifford multiplication so that the geometric Dirac operator is formally self-adjoint and satisfies a clean Lichnerowicz formula. Physicists often choose Hermitian Euclidean gamma matrices and anti-Hermitian gauge connections, in which case $\gamma^\mu\nabla_\mu$ is formally anti-Hermitian on a compact manifold. These two conventions differ by factors of $i$. The spectrum rotates; the geometry does not.

## Principal symbol and ellipticity

The principal symbol of a first-order differential operator keeps only the coefficient of the highest derivative. For a Riemannian Dirac operator, the principal symbol at a covector $\xi\in T_x^*M$ is, up to the standard Fourier-convention factor of $i$,

$$
\sigma(D\!\!\!/,\xi)=c(\xi).
$$

Since

$$
c(\xi)^2=|\xi|^2\operatorname{id}_S,
$$

the symbol is invertible for $\xi\ne0$. This is why the Euclidean Dirac operator is elliptic.

Ellipticity is the analytic reason one can speak cleanly about a discrete spectrum on compact manifolds, finite-dimensional kernels, heat kernels, zeta regularization, and Fredholm indices. It is also why Euclidean fermion determinants are technically much better behaved than Lorentzian inverse operators.

Lorentzian signature changes this story. If $\xi$ is null, then $c(\xi)^2=0$, so the principal symbol is not invertible. This is not a defect. It is the analytic expression of propagation along light cones.

## The square and the Lichnerowicz formula

The square of a Dirac operator is a second-order operator of Laplace type. Schematically,

$$
(D\!\!\!/)^2=\text{covariant Laplacian}+\text{curvature}.
$$

In a standard Riemannian geometric convention, the Lichnerowicz formula for an untwisted Dirac operator is

$$
D^2=\nabla^*\nabla+\frac14 R,
$$

where $R$ is the scalar curvature and $\nabla^*\nabla$ is the connection Laplacian.

For a Dirac operator twisted by a vector bundle $E$ with curvature $F^E$, the square has the schematic form

$$
D_E^2=\nabla^*\nabla+\frac14R+c(F^E).
$$

In local orthonormal notation, the gauge-curvature contribution is commonly written as

$$
\frac12\gamma^{ab}F^E_{ab},
$$

up to the same convention choices about $i$ and Hermitian versus anti-Hermitian gauge generators.

This formula is everywhere in QFT, usually in disguise. One-loop fermion determinants are often evaluated by replacing a first-order determinant by a determinant of a Laplace-type operator. Heat-kernel coefficients then produce UV divergences, local counterterms, trace anomalies, and index densities.

## Zero modes

A zero mode is a nonzero spinor $\psi$ satisfying

$$
D\!\!\!/\psi=0.
$$

Zero modes are not small corrections. They change the structure of the fermion path integral.

For a Dirac fermion with quadratic Euclidean action

$$
S_F=\int \bar\psi D\!\!\!/\psi,
$$

the formal Grassmann integral gives

$$
\int D\bar\psi\,D\psi\,e^{-S_F}=\det D\!\!\!/.
$$

If $D\!\!\!/$ has zero modes, the determinant vanishes unless the path integral contains enough fermion insertions to soak up the zero-mode Grassmann variables. This mechanism is central in instanton physics and anomaly matching.

For a Majorana fermion, the quadratic form is antisymmetric after choosing the correct real structure, and the path integral gives a Pfaffian rather than an ordinary determinant:

$$
\int D\psi\,e^{-\frac12\psi A\psi}=\operatorname{Pf}(A),
\qquad
\operatorname{Pf}(A)^2=\det A.
$$

This is where signs become physics. A Pfaffian is not merely a positive square root of a determinant; its sign or phase can carry global-anomaly information.

## Chirality and index

In even Euclidean dimension, the spinor bundle splits into chiral parts

$$
S=S^+\oplus S^-,
$$

using the chirality operator $\gamma_*$. For a massless Dirac operator on an even-dimensional spin manifold,

$$
\{D\!\!\!/,\gamma_*\}=0.
$$

Therefore $D\!\!\!/$ maps positive-chirality spinors to negative-chirality spinors and conversely:

$$
D_+:\Gamma(S^+\otimes E)\to \Gamma(S^-\otimes E),
$$

$$
D_-:\Gamma(S^-\otimes E)\to \Gamma(S^+\otimes E).
$$

The index is

$$
\operatorname{ind}D_+
=\dim\ker D_+-\dim\ker D_-.
$$

For compact Euclidean manifolds without boundary, the Atiyah–Singer index theorem gives

$$
\operatorname{ind}D_+
=\int_M \widehat A(TM)\wedge \operatorname{ch}(E),
$$

with the top-degree component understood. This formula is not just a beautiful theorem sitting in a museum. It is the mathematical skeleton behind chiral anomalies, fermion zero modes in instanton backgrounds, and many protected quantities in supersymmetric QFT.

The full derivation belongs with characteristic classes and index theory. Here the important takeaway is:

$$
\text{analytic zero-mode asymmetry}=
\text{topological characteristic-class integral}.
$$

Tiny equality, enormous consequences. A real overachiever.

## Heat kernels and determinants

The Euclidean determinant of a Dirac operator is formally the product of infinitely many eigenvalues. This product is divergent and must be regularized.

A common strategy is to use a Laplace-type operator built from the square of the Dirac operator. If $P$ is positive and elliptic, define its heat kernel trace

$$
K(t)=\operatorname{Tr}(e^{-tP}).
$$

As $t\to0^+$, one has an asymptotic expansion

$$
K(t)\sim \sum_{n\ge0} t^{(n-d)/2}a_n(P).
$$

The coefficients $a_n(P)$ are integrals of local curvature invariants, plus boundary terms if the manifold has boundary. This is why UV divergences in one-loop effective actions are local. Short proper time probes short distance.

For fermions, one often encounters expressions such as

$$
\log\det(D\!\!\!/+m),
$$

or, after pairing eigenvalues,

$$
\frac12\log\det\big((D\!\!\!/)^2+m^2\big).
$$

This second expression captures many magnitude-dependent effects, but it can lose phase information. In odd dimensions, on manifolds with boundary, or in chiral theories, determinant phases and eta invariants can carry anomaly data. So the move from $D\!\!\!/$ to $(D\!\!\!/)^2$ is powerful, but not morally free.

## Boundary conditions

On a manifold with boundary, a Dirac operator is not a complete spectral problem until boundary conditions are specified. The same local differential expression can define different operators depending on the boundary data.

Common boundary conditions include:

| Boundary condition | Rough idea | Where it appears |
|---|---|---|
| MIT bag | Projects spinors using the normal gamma matrix. | Fermions confined to a spatial region. |
| Chiral local | Uses chirality projectors when compatible. | Even-dimensional boundary problems, with caveats. |
| APS | Uses spectral projection of the boundary Dirac operator. | Index theory, anomalies, eta invariants. |
| Periodic or antiperiodic | Chooses a spin structure along a circle. | Thermal QFT, compact spatial cycles, torus partition functions. |

Boundary conditions affect the spectrum, determinant, index, and anomaly inflow. This is not bureaucracy. It is the whole game whenever fermions meet boundaries, defects, orbifolds, or thermal circles.

For example, on a Euclidean thermal circle, physical fermions are usually antiperiodic around the time circle. That is a choice of spin structure. Changing it changes the partition function.

## Dirac operators and anomalies

Anomalies often appear when a classical symmetry fails to preserve the quantum fermion measure. Dirac operators are the measuring device for that failure.

For a chiral fermion, the path integral formally involves the determinant of a chiral Dirac operator

$$
D_+:\Gamma(S^+\otimes E)\to\Gamma(S^-\otimes E).
$$

The phase and transformation law of this determinant line over the space of background fields encode gauge and gravitational anomalies. Infinitesimal anomalies are computed by local index densities. Global anomalies can depend on eta invariants and topology in one higher dimension.

In physics terms, this is why one cannot decide whether a chiral gauge theory is consistent by staring only at the local Lagrangian. The fermion determinant must be globally well-defined over the relevant space of gauge and metric backgrounds.

## Common pitfalls

**A gamma-matrix formula is not automatically a global operator.** The expression $\gamma^\mu\nabla_\mu$ assumes a spinor bundle, a Clifford action, and compatible gluing data.

**Do not forget the spin structure.** A manifold can have a metric and still fail to admit spinors. If it admits spinors, it may admit several inequivalent spin structures.

**Do not square away phases.** Replacing $\det D$ by a determinant of $D^2$ can hide eta invariants, global anomalies, and Pfaffian signs.

**Lorentzian inverses need boundary conditions.** The inverse of $iD\!\!\!/-m$ is not a single object. Feynman, retarded, and advanced propagators solve different problems.

**Zero modes are not regular eigenvalues with value zero.** In a Grassmann integral, zero modes require insertions or collective-coordinate treatment. Ignoring them usually gives the wrong answer.

**Boundary conditions are part of the operator.** Without them, there is no well-defined spectrum, determinant, or index on a manifold with boundary.

## Exercises

### Exercise 1: Square a twisted flat Dirac operator

In flat Euclidean space, let

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
[D_\mu,D_\nu]=iqF_{\mu\nu}.
$$

Show that

$$
(\gamma^\mu D_\mu)^2=D^\mu D_\mu+\frac{iq}{2}\gamma^{\mu\nu}F_{\mu\nu},
$$

where

$$
\gamma^{\mu\nu}=\frac12[\gamma^\mu,\gamma^\nu].
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\gamma^\mu\gamma^\nu
=\frac12\{\gamma^\mu,\gamma^\nu\}+\frac12[\gamma^\mu,\gamma^\nu]
=\delta^{\mu\nu}+\gamma^{\mu\nu}.
$$

Then

$$
(\gamma^\mu D_\mu)^2
=\gamma^\mu\gamma^\nu D_\mu D_\nu
=D^\mu D_\mu+\gamma^{\mu\nu}D_\mu D_\nu.
$$

Since $\gamma^{\mu\nu}$ is antisymmetric,

$$
\gamma^{\mu\nu}D_\mu D_\nu
=\frac12\gamma^{\mu\nu}[D_\mu,D_\nu]
=\frac{iq}{2}\gamma^{\mu\nu}F_{\mu\nu}.
$$

So

$$
(\gamma^\mu D_\mu)^2=D^\mu D_\mu+\frac{iq}{2}\gamma^{\mu\nu}F_{\mu\nu}.
$$

</details>

### Exercise 2: Formal anti-Hermiticity in Euclidean signature

Assume $M$ is compact without boundary, the Euclidean gamma matrices are Hermitian, and the connection is compatible with the Hermitian inner product on spinors. Show schematically that

$$
\int_M \sqrt g\, \psi^\dagger \gamma^\mu\nabla_\mu\chi
=-\int_M \sqrt g\, (\gamma^\mu\nabla_\mu\psi)^\dagger\chi.
$$

<details><summary><strong>Solution</strong></summary>

Because the connection is metric-compatible and spin-compatible,

$$
\nabla_\mu\gamma^\mu=0
$$

in the covariant sense. Integrating the total divergence

$$
\nabla_\mu(\psi^\dagger\gamma^\mu\chi)
$$

over a compact manifold without boundary gives zero. Expanding it gives

$$
0=\int_M\sqrt g\,
\left[(\nabla_\mu\psi)^\dagger\gamma^\mu\chi
+\psi^\dagger\gamma^\mu\nabla_\mu\chi\right].
$$

Using Hermiticity of $\gamma^\mu$ gives the result. With common Euclidean physics conventions, $\gamma^\mu\nabla_\mu$ is therefore formally anti-Hermitian.

</details>

### Exercise 3: Index on a two-dimensional background with flux

Let $M$ be a compact oriented two-dimensional spin manifold and let a charged Dirac fermion couple to a $U(1)$ connection $A$ with flux

$$
\frac{q}{2\pi}\int_M F=N\in\mathbb Z.
$$

What is the index of the chiral Dirac operator coupled to this line bundle?

<details><summary><strong>Solution</strong></summary>

In two dimensions, the $\widehat A$-class has no nontrivial two-form contribution, so the index is the first Chern number of the twisting line bundle:

$$
\operatorname{ind}D_+
=\int_M \operatorname{ch}(L)_2
=\frac{q}{2\pi}\int_M F
=N.
$$

Thus the background flux controls the chirality imbalance of zero modes:

$$
\dim\ker D_+-\dim\ker D_-=N.
$$

The sign depends on the orientation and charge convention.

</details>


### Exercise 4: Why boundary conditions are part of the operator

Let $D=-i\frac{d}{dx}$ on the interval $[0,L]$. Compare the spectra for periodic boundary conditions $\psi(L)=\psi(0)$ and antiperiodic boundary conditions $\psi(L)=-\psi(0)$.

<details><summary><strong>Solution</strong></summary>

For periodic boundary conditions, eigenfunctions are

$$
\psi_n(x)=e^{2\pi i n x/L},
\qquad n\in\mathbb Z,
$$

with eigenvalues

$$
\lambda_n=\frac{2\pi n}{L}.
$$

For antiperiodic boundary conditions,

$$
\psi_n(x)=e^{2\pi i (n+1/2)x/L},
\qquad n\in\mathbb Z,
$$

with eigenvalues

$$
\lambda_n=\frac{2\pi(n+1/2)}{L}.
$$

The differential expression $-i\frac{d}{dx}$ is the same in both cases, but the spectrum is different. The operator as a spectral object includes its domain, and the domain includes boundary conditions.

</details>

### Exercise 5: Gauge twisting changes the square

Let

$$
D\!\!\!/_A=\gamma^\mu(\partial_\mu+A_\mu)
$$

on flat Euclidean space, with constant gamma matrices and matrix-valued connection $A_\mu$. Show that the antisymmetric part of $(D\!\!\!/_A)^2$ contains the curvature $F_{\mu\nu}=[D_\mu,D_\nu]$.

<details><summary><strong>Solution</strong></summary>

Write $D_\mu=\partial_\mu+A_\mu$. Then

$$
(D\!\!\!/_A)^2=\gamma^\mu\gamma^\nu D_\mu D_\nu.
$$

Split the gamma product into symmetric and antisymmetric parts:

$$
\gamma^\mu\gamma^\nu
=\frac12\{\gamma^\mu,\gamma^\nu\}+\frac12[\gamma^\mu,\gamma^\nu].
$$

The symmetric part gives the connection Laplacian. The antisymmetric gamma commutator only sees the antisymmetric part of $D_\mu D_\nu$, so

$$
\frac12[\gamma^\mu,\gamma^\nu]D_\mu D_\nu
=\frac14[\gamma^\mu,\gamma^\nu][D_\mu,D_\nu]
=\frac12\gamma^{\mu\nu}F_{\mu\nu},
$$

where $\gamma^{\mu\nu}=\frac12[\gamma^\mu,\gamma^\nu]$. This is the local origin of the curvature term in the square of a twisted Dirac operator.

</details>

## Relations to other pages

[Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/) explains the global lift needed before spinor bundles exist. [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) fixes the local Clifford conventions used in flat-space formulas. [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) explains the gauge connection that twists charged Dirac operators. [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/) explains the determinant side of integrating out quadratic fermions.

The companion page [Variational Calculus on Manifolds](/math-toolkit/geometry-of-fields/variational-calculus-on-manifolds/) explains how actions such as $\int e\,\overline\psi(iD\!\!\!/-m)\psi$ are varied geometrically, including boundary terms and stress tensors.

Later pages on index theorems, anomalies, instantons, chiral fermions, supersymmetric localization, and QFT on curved backgrounds should link back here.

## Research status

The local and global theory of Dirac operators is mature. The active QFT frontier concerns refined uses: manifolds with boundary or corners, singular spaces, defects, nontrivial symmetry backgrounds, non-spin and nonorientable spaces, eta invariants, global anomalies, lattice discretizations, families of Dirac operators, and interacting fermions where the Dirac operator is only one part of a nonperturbative construction.

## References

- H. B. Lawson and M.-L. Michelsohn, *Spin Geometry*. Standard mathematical reference for spin structures, Clifford modules, and Dirac operators.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented background on spinors, Dirac operators, bundles, monopoles, instantons, and characteristic classes.
- T. Frankel, *The Geometry of Physics*. Geometric intuition for differential forms, bundles, spinors, gauge fields, and the Dirac operator.
- P. B. Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*. Standard reference for heat kernels and index-theoretic formulas.
- N. Berline, E. Getzler, and M. Vergne, *Heat Kernels and Dirac Operators*. Advanced reference connecting Dirac operators, heat kernels, and index theory.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, "Gravitation, gauge theories and differential geometry." Classic physics review of geometry, characteristic classes, anomalies, and index theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II. Useful for spinors, fermion path integrals, gauge backgrounds, and anomalies in QFT language.

## Version history

- **2026-06-25:** Initial polished draft. Added the geometric definition, local formula, Lorentzian/Euclidean comparison, Lichnerowicz formula, zero modes, index, determinants, boundary conditions, anomaly role, and exercises.
