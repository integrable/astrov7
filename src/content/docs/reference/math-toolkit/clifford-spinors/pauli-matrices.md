---
title: "Pauli Matrices"
description: "Defines the Pauli matrices and derives their algebra, trace identities, spin-one-half rotations, Bloch-vector map, and two-component spinor conventions used in QFT."
sidebar:
  label: "Pauli Matrices"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard quantum mechanics, angular momentum, Lie group, and QFT spinor references, including Sakurai, Hall, Georgi, Weinberg, Srednicki, Schwartz, Zee, and two-component spinor reviews."
topics:
  - Pauli matrices
  - spin one half
  - SU(2)
  - Clifford algebra
  - Bloch sphere
  - two-component spinors
  - sigma matrices
canonicalTopics:
  - pauli-matrices
  - spin-one-half
  - su2-generators
  - two-component-spinors
  - bloch-vector
  - sigma-matrix-identities
researchStatus:
  established:
    - "The Pauli-matrix algebra, trace identities, spin-one-half representation of SU(2), and two-component sigma-matrix conventions are textbook-standard."
  active:
    - "Pauli and two-component spinor technology remains central in spinor-helicity amplitudes, quantum information, condensed matter, Majorana systems, and geometric formulations of spin structures."
---

## Summary

The Pauli matrices are

$$
\sigma_1=\begin{pmatrix}0&1\\1&0\end{pmatrix},
\qquad
\sigma_2=\begin{pmatrix}0&-i\\ i&0\end{pmatrix},
\qquad
\sigma_3=\begin{pmatrix}1&0\\0&-1\end{pmatrix}.
$$

They are the smallest nontrivial matrices that simultaneously do three jobs in QFT:

1. they generate spin one half through $J_i=\sigma_i/2$;
2. they represent the Euclidean Clifford relation $\{\sigma_i,\sigma_j\}=2\delta_{ij}\mathbf 1$;
3. they bridge two-component spinors, vectors, and Lorentz-covariant sigma matrices.

Their multiplication rule is the whole game:

$$
\sigma_i\sigma_j
=
\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k.
$$

From it follow the commutator, anticommutator, trace identities, spin rotations, Bloch sphere, and the first examples of Fierz-like completeness identities.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Diagram showing Pauli matrices, their multiplication identity, spin-one-half generators, SU(2) rotations, and the map from spinors to Bloch vectors.](/figures/math-toolkit/pauli-matrix-bloch-flow.svg)

<figcaption>

The Pauli matrices are simultaneously a basis for $2\times2$ matrices, a representation of the Clifford relation, and the spin-one-half generators of $SU(2)$. A normalized two-component spinor $\chi$ defines a pure-state density matrix $\rho=\frac12(\mathbf 1+\mathbf n\cdot\boldsymbol\sigma)$, so spinors double-cover ordinary vector rotations.

</figcaption>
</figure>

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/) page, the chapter overview [Clifford Algebras and Spinors](/math-toolkit/clifford-spinors/), and the group-theory page [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/). The page [SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/) is useful for the Lorentzian interpretation, but it is not required for the first pass.

## Core idea

The Pauli matrices are not just three useful matrices. They are the meeting point of three structures:

| Structure | Pauli-matrix form | QFT use |
|---|---|---|
| Matrix basis | $M=a_0\mathbf 1+a_i\sigma_i$ | decomposing $2\times2$ spinor tensors |
| Clifford relation | $\{\sigma_i,\sigma_j\}=2\delta_{ij}\mathbf 1$ | square roots of quadratic forms |
| Lie algebra | $[\sigma_i/2,\sigma_j/2]=i\epsilon_{ijk}\sigma_k/2$ | spin-one-half representation of $SU(2)$ |

This is why the same three matrices appear in elementary spin, Weyl spinors, Lorentz transformations, density matrices, spinor-helicity variables, nonrelativistic fermions, topological matter, and supersymmetry. The matrices are tiny; their empire is not.

## Setup and conventions

We use

$$
\epsilon_{123}=+1,
$$

and repeated spatial indices $i,j,k=1,2,3$ are summed when this is clear. The $2\times2$ identity matrix is written $\mathbf 1$.

The Pauli matrices are Hermitian,

$$
\sigma_i^\dagger=\sigma_i,
$$

traceless,

$$
\operatorname{tr}\sigma_i=0,
$$

and have determinant

$$
\det\sigma_i=-1.
$$

They obey

$$
\sigma_i^2=\mathbf 1,
$$

so each $\sigma_i$ has eigenvalues $+1$ and $-1$.

For later two-component Lorentz notation, this page uses the mostly-minus convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1).
$$

A convenient matrix convention is

$$
\sigma^\mu=(\mathbf 1,\sigma^1,\sigma^2,\sigma^3),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^1,-\sigma^2,-\sigma^3),
$$

so that

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu
=
2\eta^{\mu\nu}\mathbf 1.
$$

This page mostly works in matrix notation. Dotted and undotted spinor indices are introduced only lightly; later spinor pages will make the index conventions explicit.

## The matrices as observables

Each Pauli matrix is Hermitian, so it can represent an observable in a two-state quantum system. The eigenvectors of $\sigma_3$ are usually written

$$
|+\rangle=\begin{pmatrix}1\\0\end{pmatrix},
\qquad
|-\rangle=\begin{pmatrix}0\\1\end{pmatrix},
$$

with

$$
\sigma_3|+\rangle=|+\rangle,
\qquad
\sigma_3|-\rangle=-|-\rangle.
$$

The other Pauli matrices measure spin along the $x$ and $y$ axes in the same representation. For a unit vector $\mathbf n$, define

$$
\sigma_{\mathbf n}=\mathbf n\cdot\boldsymbol\sigma=n_i\sigma_i.
$$

Using the Pauli algebra, one finds

$$
\sigma_{\mathbf n}^2=\mathbf 1.
$$

Therefore $\sigma_{\mathbf n}$ also has eigenvalues $\pm1$. The physical spin operator is usually

$$
S_i=\frac{\hbar}{2}\sigma_i,
$$

or, in units with $\hbar=1$,

$$
S_i=\frac12\sigma_i.
$$

That factor of $1/2$ is where spin one half actually enters. The Pauli matrices themselves have eigenvalues $\pm1$; the spin observables have eigenvalues $\pm1/2$ in natural units.

## Multiplication table

Direct multiplication gives

$$
\sigma_1\sigma_2=i\sigma_3,
\qquad
\sigma_2\sigma_3=i\sigma_1,
\qquad
\sigma_3\sigma_1=i\sigma_2.
$$

Reversing the order changes the sign of the $i$ term:

$$
\sigma_2\sigma_1=-i\sigma_3,
\qquad
\sigma_3\sigma_2=-i\sigma_1,
\qquad
\sigma_1\sigma_3=-i\sigma_2.
$$

Together with $\sigma_i^2=\mathbf 1$, these identities combine into

$$
\sigma_i\sigma_j
=
\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k.
$$

Taking the symmetric and antisymmetric parts gives

$$
\{\sigma_i,\sigma_j\}=2\delta_{ij}\mathbf 1,
$$

and

$$
[\sigma_i,\sigma_j]=2i\epsilon_{ijk}\sigma_k.
$$

The anticommutator is the Clifford-algebra part. The commutator is the Lie-algebra part. One set of matrices, two different structures.

## Spin one half and SU(2)

Define

$$
J_i=\frac12\sigma_i.
$$

Then

$$
[J_i,J_j]
=
\frac14[\sigma_i,\sigma_j]
=
i\epsilon_{ijk}J_k.
$$

Thus the $J_i$ give the fundamental spin-one-half representation of $\mathfrak{su}(2)$. A rotation by angle $\theta$ around a unit vector $\mathbf n$ is represented on a spinor by

$$
U(\mathbf n,\theta)
=
\exp\left(-i\theta\,\mathbf n\cdot\mathbf J\right)
=
\exp\left(-\frac{i\theta}{2}\mathbf n\cdot\boldsymbol\sigma\right).
$$

Since

$$
(\mathbf n\cdot\boldsymbol\sigma)^2=\mathbf 1,
$$

all higher powers collapse, giving

$$
U(\mathbf n,\theta)
=
\cos\frac{\theta}{2}\,\mathbf 1
-i\sin\frac{\theta}{2}\,\mathbf n\cdot\boldsymbol\sigma.
$$

At $\theta=2\pi$,

$$
U(\mathbf n,2\pi)=-\mathbf 1,
$$

while at $\theta=4\pi$,

$$
U(\mathbf n,4\pi)=+\mathbf 1.
$$

That is the visible algebraic sign of the double cover

$$
SU(2)\longrightarrow SO(3).
$$

The associated rotation of ordinary vectors is obtained by conjugating Pauli-vector matrices:

$$
U(\mathbf n,\theta)\, (\mathbf a\cdot\boldsymbol\sigma)\,U(\mathbf n,\theta)^\dagger
=
(R\mathbf a)\cdot\boldsymbol\sigma,
$$

where $R\in SO(3)$ is the ordinary rotation by angle $\theta$ around $\mathbf n$. Both $U$ and $-U$ give the same $R$.

## Basis of two-by-two matrices

The four matrices

$$
\mathbf 1,
\qquad
\sigma_1,
\qquad
\sigma_2,
\qquad
\sigma_3
$$

form a basis of the complex vector space of $2\times2$ complex matrices. Any matrix $M$ can be written uniquely as

$$
M=a_0\mathbf 1+a_i\sigma_i.
$$

The coefficients are extracted by traces:

$$
a_0=\frac12\operatorname{tr}M,
\qquad
a_i=\frac12\operatorname{tr}(\sigma_iM).
$$

For Hermitian $M$, all $a_0,a_i$ are real. In particular, any Hermitian $2\times2$ matrix can be viewed as a scalar plus a vector.

This basis gives the completeness identity

$$
\sum_{i=1}^3(\sigma_i)_\alpha{}^\beta(\sigma_i)_\gamma{}^\delta
=
2\delta_\alpha{}^\delta\delta_\gamma{}^\beta
-
\delta_\alpha{}^\beta\delta_\gamma{}^\delta.
$$

This is the $2\times2$ ancestor of many Fierz identities. It says that the identity matrix and Pauli matrices form a complete basis for matrices acting on two-component spinors.

## Trace identities

The basic traces are

$$
\operatorname{tr}\mathbf 1=2,
\qquad
\operatorname{tr}\sigma_i=0,
\qquad
\operatorname{tr}(\sigma_i\sigma_j)=2\delta_{ij}.
$$

Using the multiplication formula,

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k)
=2i\epsilon_{ijk}.
$$

For four Pauli matrices,

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k\sigma_\ell)
=
2(\delta_{ij}\delta_{k\ell}
-\delta_{ik}\delta_{j\ell}
+\delta_{i\ell}\delta_{jk}).
$$

The signs in this last identity are a useful test of whether your $\epsilon_{ijk}$ convention and multiplication order are consistent.

A very useful product identity is

$$
(\mathbf a\cdot\boldsymbol\sigma)(\mathbf b\cdot\boldsymbol\sigma)
=
(\mathbf a\cdot\mathbf b)\mathbf 1
+i(\mathbf a\times\mathbf b)\cdot\boldsymbol\sigma.
$$

It follows immediately from $\sigma_i\sigma_j=\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k$.

## Bloch vectors and density matrices

Let $\chi$ be a normalized two-component spinor,

$$
\chi^\dagger\chi=1.
$$

The rank-one density matrix

$$
\rho=\chi\chi^\dagger
$$

is Hermitian, has trace $1$, and obeys $\rho^2=\rho$. Since $\mathbf 1$ and $\sigma_i$ form a basis, write

$$
\rho=\frac12(\mathbf 1+n_i\sigma_i),
$$

where

$$
n_i=\chi^\dagger\sigma_i\chi.
$$

The condition $\rho^2=\rho$ implies

$$
|\mathbf n|=1.
$$

So a normalized spinor, up to an overall phase, determines a point on the unit sphere. This is the Bloch sphere.

The phrase “up to an overall phase” matters. The spinors $\chi$ and $e^{i\alpha}\chi$ give the same density matrix and the same Bloch vector. In particular, the Bloch sphere is not the whole two-component spinor space; it is the space of rays in a two-dimensional Hilbert space.

Under an $SU(2)$ transformation,

$$
\chi\mapsto U\chi,
$$

the density matrix transforms by

$$
\rho\mapsto U\rho U^\dagger.
$$

Equivalently,

$$
\mathbf n\mapsto R\mathbf n,
$$

where $R\in SO(3)$ is the vector rotation associated with $U$. Again, $U$ and $-U$ give the same rotation of $\mathbf n$.

## Pauli matrices as Clifford matrices

The anticommutator identity

$$
\{\sigma_i,\sigma_j\}=2\delta_{ij}\mathbf 1
$$

means that the Pauli matrices give a representation of the Euclidean Clifford relation. For any vector $\mathbf v\in\mathbb R^3$,

$$
(\mathbf v\cdot\boldsymbol\sigma)^2=|\mathbf v|^2\mathbf 1.
$$

That is exactly the Clifford idea: linearize the quadratic form. Instead of representing a vector by numbers alone, represent it by a matrix whose square is the squared length.

There is a subtle algebra point hiding here. The three Pauli matrices generate the full matrix algebra $M_2(\mathbb C)$, which has complex dimension $4$. The full complex Clifford algebra $Cl_3(\mathbb C)$ has complex dimension $8$ and is isomorphic to two copies of $M_2(\mathbb C)$. The usual Pauli matrices therefore give one irreducible representation of $Cl_3(\mathbb C)$, not a faithful identification of the full algebra with $M_2(\mathbb C)$.

For most QFT calculations, the representation is what is needed: the matrices satisfy the required anticommutation relation. When global Clifford-algebra structure matters, later pages will say so explicitly.

## Lorentz bridge

The Pauli matrices also package Minkowski vectors into Hermitian $2\times2$ matrices. Given a real four-vector $x^\mu=(x^0,\mathbf x)$, define

$$
X=x^0\mathbf 1+x^i\sigma_i.
$$

Then

$$
\det X=(x^0)^2-\mathbf x^2.
$$

The determinant is the mostly-minus Minkowski norm. If $A\in SL(2,\mathbb C)$, then

$$
X\mapsto AXA^\dagger
$$

preserves $\det X$ because $\det A=1$. This gives the double cover

$$
SL(2,\mathbb C)\to SO^+(1,3).
$$

For later two-component spinor notation, one introduces

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i).
$$

Then

$$
\sigma^\mu\bar\sigma^\nu+\sigma^\nu\bar\sigma^\mu
=2\eta^{\mu\nu}\mathbf 1,
$$

and

$$
\operatorname{tr}(\sigma^\mu\bar\sigma^\nu)=2\eta^{\mu\nu}.
$$

This is the two-component version of the gamma-matrix Clifford relation. In a chiral basis, the four-dimensional Dirac matrices can be built from $\sigma^\mu$ and $\bar\sigma^\mu$ by placing them in off-diagonal blocks.

## From Pauli matrices to gamma matrices

In four-dimensional mostly-minus conventions, a common chiral representation of the gamma matrices is

$$
\gamma^\mu=
\begin{pmatrix}
0&\sigma^\mu\\
\bar\sigma^\mu&0
\end{pmatrix}.
$$

Using the sigma-matrix identity above, one checks

$$
\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}\mathbf 1_4.
$$

This formula is not meant to replace the later gamma-matrix conventions page. It explains why Pauli matrices show up inside relativistic fermion theory: they are the two-component blocks from which Weyl and Dirac spinors are assembled.

In this basis, a Dirac spinor is often written schematically as

$$
\Psi=\begin{pmatrix}\psi_\alpha\\ \bar\chi^{\dot\alpha}\end{pmatrix},
$$

where $\psi_\alpha$ and $\bar\chi^{\dot\alpha}$ transform in conjugate two-component spinor representations. The dotted and undotted index conventions are not decoration; they encode the two inequivalent Weyl representations of the Lorentz group.

## Common pitfalls

**Forgetting the factor of one half.** The Pauli matrices obey $[\sigma_i,\sigma_j]=2i\epsilon_{ijk}\sigma_k$. The spin-one-half generators are $J_i=\sigma_i/2$, so $[J_i,J_j]=i\epsilon_{ijk}J_k$.

**Confusing spinor rotations with vector rotations.** A $2\pi$ rotation gives $-\mathbf 1$ on a spinor but $+\mathbf 1$ on a vector. The map $SU(2)\to SO(3)$ is two-to-one, so $U$ and $-U$ represent the same vector rotation.

**Treating the Bloch vector as the spinor.** A normalized spinor has an overall phase that the Bloch vector does not see. The Bloch sphere describes rays, not all normalized spinors with phase.

**Calling every Pauli identity a Clifford identity.** The anticommutator is the Clifford relation. The commutator is the $\mathfrak{su}(2)$ Lie algebra. Both are true, but they play different roles.

**Comparing two-component formulas without translating signs.** The definitions of $\sigma^\mu$, $\bar\sigma^\mu$, $\epsilon_{\alpha\beta}$, and metric signature differ across books. Always check which equation the matrices are supposed to satisfy.

## Relations to other pages

- [Clifford Algebras and Spinors](/math-toolkit/clifford-spinors/) explains where this page sits in the spinor chapter.
- [SU(2) and Angular Momentum](/math-toolkit/groups-representations/su2-and-angular-momentum/) derives the representation-theory side of spin one half.
- [SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/) explains why $SL(2,\mathbb C)$ acts on Hermitian $2\times2$ matrices as Lorentz transformations.
- [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) gives the general relation between infinitesimal generators and group exponentials.
- [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) uses closely related trace and completeness logic for non-Abelian group generators.

## Research status

The identities on this page are established textbook material. Their importance is not that the formulas are controversial; it is that they are reused everywhere. In modern QFT, Pauli-matrix technology feeds directly into Weyl spinors, spinor-helicity amplitudes, Majorana fermions, condensed-matter two-band Hamiltonians, quantum information, and spin-structure questions.

The active research is not about whether $\sigma_i\sigma_j=\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k$. It is about the structures built on top of that identity: global spin and pin structures, fermionic topological phases, exact amplitude variables, defects carrying spinor quantum numbers, and real-time spin dynamics in many-body systems.

## Exercises

### Exercise 1: Verify the multiplication identity

Compute $\sigma_1\sigma_2$, $\sigma_2\sigma_3$, and $\sigma_3\sigma_1$ directly from the matrices, and use the result to justify

$$
\sigma_i\sigma_j=\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k.
$$

<details><summary><strong>Solution</strong></summary>

Direct multiplication gives

$$
\sigma_1\sigma_2=
\begin{pmatrix}0&1\\1&0\end{pmatrix}
\begin{pmatrix}0&-i\\ i&0\end{pmatrix}
=
\begin{pmatrix}i&0\\0&-i\end{pmatrix}
=i\sigma_3.
$$

Similarly,

$$
\sigma_2\sigma_3=i\sigma_1,
\qquad
\sigma_3\sigma_1=i\sigma_2.
$$

When $i=j$, one has $\sigma_i^2=\mathbf 1$. When $i\neq j$, the product is $i\epsilon_{ijk}\sigma_k$. Combining both cases gives

$$
\sigma_i\sigma_j=\delta_{ij}\mathbf 1+i\epsilon_{ijk}\sigma_k.
$$

</details>

### Exercise 2: Derive the spin-one-half rotation formula

Let $\mathbf n$ be a unit vector. Show that

$$
\exp\left(-\frac{i\theta}{2}\mathbf n\cdot\boldsymbol\sigma\right)
=
\cos\frac{\theta}{2}\,\mathbf 1
-i\sin\frac{\theta}{2}\,\mathbf n\cdot\boldsymbol\sigma.
$$

<details><summary><strong>Solution</strong></summary>

Since $|\mathbf n|=1$,

$$
(\mathbf n\cdot\boldsymbol\sigma)^2=\mathbf 1.
$$

Therefore even powers give $\mathbf 1$ and odd powers give $\mathbf n\cdot\boldsymbol\sigma$. Expanding the exponential,

$$
\exp\left(-\frac{i\theta}{2}\mathbf n\cdot\boldsymbol\sigma\right)
=
\sum_{m=0}^\infty\frac{(-i\theta/2)^{2m}}{(2m)!}\mathbf 1
+
\sum_{m=0}^\infty\frac{(-i\theta/2)^{2m+1}}{(2m+1)!}\mathbf n\cdot\boldsymbol\sigma.
$$

The first series is $\cos(\theta/2)$ and the second is $-i\sin(\theta/2)$, so the result follows.

</details>

### Exercise 3: Recover the Bloch-sphere length

Let $\chi$ be normalized and define

$$
\rho=\chi\chi^\dagger=\frac12(\mathbf 1+n_i\sigma_i).
$$

Use $\rho^2=\rho$ to show $|\mathbf n|=1$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\rho^2
=
\frac14(\mathbf 1+2n_i\sigma_i+n_in_j\sigma_i\sigma_j).
$$

Using

$$
n_in_j\sigma_i\sigma_j=|\mathbf n|^2\mathbf 1
$$

because the antisymmetric term vanishes, we get

$$
\rho^2
=
\frac14\left((1+|\mathbf n|^2)\mathbf 1+2n_i\sigma_i\right).
$$

Since

$$
\rho=\frac12(\mathbf 1+n_i\sigma_i),
$$

matching the identity-matrix coefficient gives

$$
\frac14(1+|\mathbf n|^2)=\frac12,
$$

so

$$
|\mathbf n|^2=1.
$$

</details>

### Exercise 4: Prove the four-Pauli trace

Starting from

$$
\sigma_i\sigma_j=\delta_{ij}\mathbf 1+i\epsilon_{ijm}\sigma_m,
$$

prove

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k\sigma_\ell)
=
2(\delta_{ij}\delta_{k\ell}
-\delta_{ik}\delta_{j\ell}
+\delta_{i\ell}\delta_{jk}).
$$

<details><summary><strong>Solution</strong></summary>

First multiply the first two matrices:

$$
\sigma_i\sigma_j\sigma_k\sigma_\ell
=
(\delta_{ij}\mathbf 1+i\epsilon_{ijm}\sigma_m)\sigma_k\sigma_\ell.
$$

Taking the trace gives

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k\sigma_\ell)
=
\delta_{ij}\operatorname{tr}(\sigma_k\sigma_\ell)
+i\epsilon_{ijm}\operatorname{tr}(\sigma_m\sigma_k\sigma_\ell).
$$

Use

$$
\operatorname{tr}(\sigma_k\sigma_\ell)=2\delta_{k\ell},
\qquad
\operatorname{tr}(\sigma_m\sigma_k\sigma_\ell)=2i\epsilon_{mk\ell}.
$$

Then

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k\sigma_\ell)
=
2\delta_{ij}\delta_{k\ell}
-2\epsilon_{ijm}\epsilon_{mk\ell}.
$$

Using

$$
\epsilon_{ijm}\epsilon_{mk\ell}
=
\delta_{ik}\delta_{j\ell}-\delta_{i\ell}\delta_{jk},
$$

we obtain

$$
\operatorname{tr}(\sigma_i\sigma_j\sigma_k\sigma_\ell)
=
2(\delta_{ij}\delta_{k\ell}
-\delta_{ik}\delta_{j\ell}
+\delta_{i\ell}\delta_{jk}).
$$

As a quick check, take $i=k=1$ and $j=\ell=2$. Then

$$
\operatorname{tr}(\sigma_1\sigma_2\sigma_1\sigma_2)
=\operatorname{tr}((i\sigma_3)(i\sigma_3))
=-2,
$$

which agrees with the formula.

</details>

## References

### Standard first pass

- J. J. Sakurai and J. Napolitano, *Modern Quantum Mechanics*, for spin one half, angular momentum, and Pauli matrices in quantum mechanics.
- B. C. Hall, *Lie Groups, Lie Algebras, and Representations*, for the $SU(2)$ and Lie-algebra viewpoint.
- H. Georgi, *Lie Algebras in Particle Physics*, for compact group and representation conventions used in particle physics.

### QFT references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Lorentz representations and spinor fields.
- M. Srednicki, *Quantum Field Theory*, for two-component spinors, gamma-matrix technology, and spinor-field conventions.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for spinors and Pauli/gamma matrix identities in Standard Model calculations.
- A. Zee, *Quantum Field Theory in a Nutshell*, for a physical route into spinors and fermions.
- H. K. Dreiner, H. E. Haber, and S. P. Martin, “Two-component spinor techniques and Feynman rules,” for detailed two-component spinor identities and conventions.

## Version history

- **2026-06-24:** Initial standardized page.
