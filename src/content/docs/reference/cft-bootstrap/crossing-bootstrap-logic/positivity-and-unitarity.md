---
title: "Positivity and Unitarity"
description: "Why reflection positivity and unitarity make OPE coefficients, two-point coefficients, and mixed-correlator matrices positive in conformal bootstrap equations."
sidebar:
  label: "Positivity and Unitarity"
  order: 4
level: Graduate
status: "Polished draft"
source: "Mack 1977; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Hartman et al. 2017"
topics:
  - unitarity
  - reflection positivity
  - OPE coefficient positivity
  - unitarity bounds
  - positive semidefinite matrices
  - linear functionals
canonicalTopics:
  - positivity-and-unitarity
  - reflection-positivity
  - unitarity-bounds
  - semidefinite-positivity
researchStatus:
  established:
    - "In Euclidean unitary CFTs, reflection positivity gives a positive inner product on states created by local operators, leading to positive two-point metrics and nonnegative OPE coefficient squares in identical-correlator bootstrap equations."
    - "For mixed-correlator systems, the same Hilbert-space positivity becomes positive semidefiniteness of OPE coefficient matrices."
  active:
    - "Bootstrap methods continue to extend positivity ideas to spinning correlators, stress-tensor collider bounds, Lorentzian functionals, defects, nonunitary theories, and rigorous numerical certificates."
---

## Summary

Positivity is the ingredient that turns crossing symmetry from a hard functional identity into a powerful exclusion machine. Conformal symmetry gives the blocks. Crossing says that different block sums agree. Unitarity says that many coefficients in those sums are nonnegative.

For an identical scalar primary $\phi$ in a unitary CFT,

$$
\mathcal G(U,V)
=
1+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(U,V),
\qquad
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

The nonnegativity is not a convention. It is the statement that the exchanged primary creates a positive-norm state and that the coefficient is the square of a real matrix element in a reflection-positive normalization.

In mixed-correlator bootstrap, positivity becomes matrix positivity. If an operator $\mathcal O$ appears in several OPEs, its coefficients form a vector $\vec\lambda_{\mathcal O}$ and contribute

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}\succeq0.
$$

This page explains where these signs come from, how they enter bootstrap equations, and where they can fail.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Reflection positivity and bootstrap positivity](/figures/cft-bootstrap/reflection-positivity-bootstrap.svg)

<figcaption>

Reflection positivity defines a Hilbert-space inner product from Euclidean correlators. In a conformal-block expansion, the same positivity appears as nonnegative OPE weights or positive semidefinite coefficient matrices.

</figcaption>
</figure>

## Prerequisites

You should know [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/), [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/), [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), and [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/).

This page focuses on positivity in ordinary local CFT bootstrap. Supersymmetric shortening, defect reflection positivity, and conformal collider positivity get their own later pages.

## Core idea

The bootstrap uses three related positivity statements.

| Positivity statement | Formula | Bootstrap role |
|---|---|---|
| Positive norms | $\langle \Psi\mid\Psi\rangle\ge0$ | Excludes negative-norm states and gives unitarity bounds. |
| Positive OPE weights | $\lambda_{\phi\phi\mathcal O}^2\ge0$ | Turns identical-scalar crossing into a positive-cone problem. |
| Positive matrices | $\vec\lambda\vec\lambda^{\,T}\succeq0$ | Turns mixed correlators into semidefinite programs. |

Without positivity, crossing is still true, but it is much less sharp. One can no longer separate a positive cone from the identity vector, because the coefficients may have arbitrary signs or phases.

The deepest origin of these inequalities is the same in all cases: Euclidean reflection positivity is the path-integral version of Hilbert-space unitarity.

## Setup and conventions

We work in Euclidean signature unless stated otherwise. Let $\Theta$ be reflection through a quantization surface, combined with Hermitian conjugation and whatever internal conjugation is required. Reflection positivity says that for any finite linear combination $A$ of operators supported on one side of the reflection surface,

$$
\langle \Theta A\, A\rangle\ge0.
$$

In radial quantization, the analogous statement is that an operator insertion inside the unit sphere creates a state

$$
\mathcal O(0)\lvert 0\rangle,
$$

and the conjugate bra is obtained by inversion and Hermitian conjugation. The two-point function gives the norm matrix. For scalar primaries, one can choose a basis with

$$
\langle \mathcal O_a(x)\mathcal O_b(0)\rangle
=
\frac{\delta_{ab}}{(x^2)^{\Delta_a}}
$$

for real neutral operators. More generally, there is a positive two-point metric $g_{ab}$.

A bootstrap equation should use a basis in which the relevant positivity is manifest. Otherwise the same physics is present but harder to see.

## From reflection positivity to a Hilbert space

Pick a set of Euclidean operator combinations $A_i$ supported in the positive half-space. Reflection positivity says that the matrix

$$
G_{ij}=\langle \Theta A_i\, A_j\rangle
$$

is positive semidefinite:

$$
\sum_{i,j}c_i^*G_{ij}c_j
=
\left\langle
\Theta\left(\sum_i c_iA_i\right)
\left(\sum_j c_jA_j\right)
\right\rangle
\ge0.
$$

After quotienting null states and completing the space, $G_{ij}$ becomes the Hilbert-space inner product. This is the Osterwalder–Schrader route from Euclidean correlators to Lorentzian unitarity.

For CFT, radial quantization packages this construction geometrically. The radial time is

$$
\tau=\log r,
$$

and dilatations act as the Hamiltonian on the cylinder. The positivity of norms in this Hilbert space gives immediate constraints on dimensions, spins, and OPE data.

## Positive two-point coefficients

A primary operator creates a state. Its two-point function is the norm of that state. Therefore the coefficient of a physical two-point function must be positive after choosing a real basis of operators.

For conserved currents and the stress tensor, this gives

$$
C_J>0,
\qquad
C_T>0
$$

in a nontrivial unitary CFT, with the precise normalization depending on the convention for current and stress-tensor two-point functions.

The positivity of $C_T$ is not the same as the averaged null energy condition or conformal collider bounds. Those are stronger Lorentzian positivity constraints on energy flux. But $C_T>0$ is the basic Hilbert-space norm statement: the stress tensor is a physical spin-two operator, not a negative-norm ghost.

## Why identical-scalar OPE coefficients are squared

Consider the four-point function of an identical real scalar $\phi$. In radial quantization, put two operators inside a sphere and two conjugate operators outside. Insert a complete set of states between the pair:

$$
\mathbf 1_{\mathcal H}
=
\sum_{\mathcal O,\alpha}
\lvert \mathcal O,\alpha\rangle
\langle \mathcal O,\alpha\rvert,
$$

where $\alpha$ labels descendants and possible degeneracies. The contribution of a primary multiplet has the schematic form

$$
\sum_{\alpha}
\left|
\langle \mathcal O,\alpha\mid \phi\phi\rangle
\right|^2
\times
\text{known kinematics}.
$$

After summing descendants, the known kinematics become the conformal block. For a nondegenerate primary in a real normalization, the primary coefficient is

$$
p_{\mathcal O}=\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This is the positivity used in the identical scalar bootstrap equation.

The statement is basis-dependent in appearance but invariant in content. If several primaries share the same quantum numbers and dimensions, the contribution is the sum of squares in an orthonormal basis. It remains nonnegative.

## Matrix positivity in mixed correlators

Now suppose there are several external scalar pairs, such as $\sigma\sigma$ and $\epsilon\epsilon$. A primary $\mathcal O$ may appear in both OPEs. Define the coefficient vector

$$
\vec\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

The exchanged multiplet contributes an outer product

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}^2 &
\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}\lambda_{\sigma\sigma\mathcal O} &
\lambda_{\epsilon\epsilon\mathcal O}^2
\end{pmatrix}.
$$

For any real vector $v$,

$$
v^T(\vec\lambda\vec\lambda^{\,T})v
=(v\cdot\vec\lambda)^2\ge0.
$$

Thus the coefficient matrix is positive semidefinite. This is the matrix version of $\lambda^2\ge0$.

In a mixed-correlator bootstrap equation, a linear functional $\alpha$ must be chosen so that its action on each matrix-valued crossing block is positive semidefinite:

$$
\alpha[\vec V_{\Delta,\ell}]\succeq0.
$$

This is the mathematical reason semidefinite programming appears naturally.

## Unitarity bounds from descendant norms

Conformal multiplets contain descendants created by translations $P_\mu$. Radial conjugation makes special conformal generators $K_\mu$ adjoint to translations:

$$
P_\mu^\dagger=K_\mu.
$$

Therefore descendant norms are controlled by the conformal algebra. Positivity of all descendant norms imposes lower bounds on primary dimensions.

For $d>2$, the standard bosonic unitarity bounds are

$$
\Delta\ge \frac{d-2}{2}
\qquad
\text{for scalar primaries},
$$

and

$$
\Delta\ge \ell+d-2
\qquad
\text{for symmetric traceless spin }\ell\ge1.
$$

Saturation means shortening. For spin $1$,

$$
\Delta=d-1
$$

corresponds to a conserved current. For spin $2$,

$$
\Delta=d
$$

corresponds to the stress tensor. In general, saturation of the spin-$\ell$ bound gives a conserved current with

$$
\partial^{\mu_1}J_{\mu_1\cdots\mu_\ell}=0.
$$

In two dimensions, the global conformal algebra factorizes, and unitarity is usually expressed as

$$
h\ge0,
\qquad
\bar h\ge0
$$

for states in a unitary highest-weight representation, with stronger Virasoro constraints when the full local conformal algebra is used.

## Positivity and linear functionals

For identical scalar crossing, the equation has the form

$$
F_{\mathbf 1}+
\sum_{\mathcal O\ne\mathbf 1}p_\mathcal O F_\mathcal O=0,
\qquad
p_\mathcal O\ge0.
$$

A linear functional $\alpha$ excludes an assumed spectrum if

$$
\alpha(F_{\mathbf 1})>0,
\qquad
\alpha(F_\mathcal O)\ge0
$$

for every allowed non-identity operator. Applying $\alpha$ gives

$$
0=
\alpha(F_{\mathbf 1})+
\sum_{\mathcal O\ne\mathbf 1}p_\mathcal O\alpha(F_\mathcal O),
$$

but the right side is strictly positive. Contradiction.

The proof is just one line, but it is the entire engine. Crossing supplies the equation. Positivity supplies the sign. The functional supplies the contradiction.

## Charged and complex operators

For charged operators, positivity usually involves conjugate pairs. If $\phi$ carries a global charge, the positive two-point function is between $\phi$ and $\phi^\dagger$:

$$
\langle \phi(x)\phi^\dagger(0)\rangle>0.
$$

The OPE channel $\phi\times\phi^\dagger$ contains the identity and neutral operators. In a reflection-positive setup, the coefficients contributing to the corresponding identical-pair channel can again be written as nonnegative squares or positive matrices.

By contrast, a general correlator of nonidentical operators may involve products such as

$$
\lambda_{12\mathcal O}\lambda_{34\mathcal O},
$$

which are not necessarily nonnegative. Bootstrap positivity is therefore strongest when the correlator system is organized into reflection-positive pairings.

## Spinning correlators and tensor structures

For spinning external operators, a single exchanged primary can contribute through several tensor structures. The OPE data become vectors over tensor-structure labels, and the positivity statement is again matrix positivity.

Schematically,

$$
\lambda_{a,\mathcal O}\lambda_{b,\mathcal O}
$$

is a positive semidefinite matrix in the structure labels $a,b$ when the structures are arranged in a reflection-positive basis. Conservation, parity, time reversal, and dimension-specific identities may reduce the basis or impose relations.

The warning is practical: not every convenient tensor basis makes positivity obvious. A good bootstrap setup chooses bases that keep the Hilbert-space inner product visible.

## When positivity fails or changes

Positivity has assumptions. Break the assumptions, and the signs change.

| Situation | What changes |
|---|---|
| Nonunitary CFT | OPE coefficients need not appear with nonnegative weights; negative-norm states may exist. |
| Logarithmic CFT | Two-point metrics can be non-diagonal or nonsemisimple; block decompositions need care. |
| Lorentzian ordering | Wightman functions require branch choices and operator order; Euclidean positivity is not a pointwise sign. |
| Non-reflection-positive statistical model | Euclidean correlators may not reconstruct a unitary Hilbert space. |
| Nonidentical external operators | Products $\lambda_{12\mathcal O}\lambda_{34\mathcal O}$ can have either sign. |
| Bad tensor basis | Positivity exists but is hidden by a non-orthonormal or non-real basis. |
| Gauge-variant operators | Only gauge-invariant physical states should enter a unitary Hilbert-space bootstrap. |

This is why bootstrap papers state whether they assume unitarity, reflection positivity, reality of external operators, and specific symmetry sectors.

## Common pitfalls

| Pitfall | Repair |
|---|---|
| Treating conformal blocks themselves as positive functions everywhere. | Positivity is about OPE weights or matrices in a reflection-positive expansion, not pointwise positivity of every block in every variable. |
| Forgetting the two-point metric. | OPE coefficients with lower indices become physical after raising indices with the positive two-point metric. |
| Assuming positivity in every OPE channel. | Positivity depends on reflection-positive pairings of external operators. |
| Ignoring degeneracies. | Degenerate primaries contribute positive matrices or sums of squares. |
| Confusing unitarity bounds with dynamical gaps. | Unitarity bounds are universal lower bounds; gaps are extra assumptions about a particular theory. |
| Calling a semidefinite matrix positive definite. | Null states and shortening often produce semidefinite, not definite, matrices. |
| Applying unitary bootstrap logic to a nonunitary model without modification. | Nonunitary bootstrap can still use crossing, but the positive-functional exclusion argument changes. |
| Comparing $C_T$ or $C_J$ without conventions. | Their numerical values depend on the normalization of $T$, $J$, and the two-point tensor structures. |

## Relations to other pages

- [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/) introduces the conceptual relation between Euclidean positivity and Lorentzian unitarity.
- [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) explains why $P_\mu^\dagger=K_\mu$.
- [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) derives the dimension bounds from descendant norms.
- [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) explains how two-point normalization affects structure constants.
- [Four-Point Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/four-point-bootstrap/) uses positivity to build concrete gap and OPE coefficient bounds.
- [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) turns positivity into exclusion certificates.
- [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) implements matrix positivity computationally.

## Research status

The Hilbert-space origin of positivity, the unitarity bounds for conformal primaries, and the nonnegativity of identical-scalar OPE weights are standard. They are part of the backbone of higher-dimensional conformal bootstrap.

Active work develops stronger positivity constraints and better ways to use them: matrix positivity in large mixed systems, spinning-correlator positivity, conformal collider inequalities, Lorentzian inversion and dispersive positivity, defect and boundary reflection positivity, rigorous semidefinite certificates, and bootstrap methods for theories where ordinary unitarity is absent or modified.

## Exercises

### Exercise 1: Gram matrix positivity

Let $A_1,\ldots,A_n$ be operator combinations supported on one side of a Euclidean reflection surface. Define

$$
G_{ij}=\langle \Theta A_i A_j\rangle.
$$

Show that reflection positivity implies $G\succeq0$.

<details><summary><strong>Solution</strong></summary>

For arbitrary complex coefficients $c_i$, define

$$
A=\sum_i c_iA_i.
$$

Reflection positivity gives

$$
0\le \langle \Theta A\,A\rangle
=
\sum_{i,j}c_i^*G_{ij}c_j.
$$

Since this quadratic form is nonnegative for every vector $c$, the matrix $G$ is positive semidefinite.

</details>

### Exercise 2: Positivity of an identical-scalar OPE weight

Explain why the coefficient multiplying a nondegenerate primary conformal block in $\langle\phi\phi\phi\phi\rangle$ is nonnegative in a unitary real scalar normalization.

<details><summary><strong>Solution</strong></summary>

In radial quantization, the pair $\phi\phi$ creates a state. Insert a complete orthonormal set of states organized into conformal multiplets. The contribution of a nondegenerate primary multiplet is the square of the matrix element between the pair-created state and the primary state, together with the fixed descendant sum. The primary coefficient is therefore

$$
p_\mathcal O=\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

</details>

### Exercise 3: Matrix positivity from OPE vectors

Let

$$
\vec\lambda=
\begin{pmatrix}\lambda_1\\ \lambda_2\\ \lambda_3\end{pmatrix}.
$$

Show that $M=\vec\lambda\vec\lambda^{\,T}$ is positive semidefinite.

<details><summary><strong>Solution</strong></summary>

For any real vector $v$,

$$
v^TMv
=
v^T\vec\lambda\vec\lambda^{\,T}v
=
(v\cdot\vec\lambda)^2\ge0.
$$

Therefore $M\succeq0$. A sum of such matrices with nonnegative weights is also positive semidefinite.

</details>

### Exercise 4: A functional exclusion proof

Suppose

$$
F_0+\sum_i p_iF_i=0,
\qquad
p_i\ge0.
$$

If a linear functional $\alpha$ obeys $\alpha(F_0)>0$ and $\alpha(F_i)\ge0$ for all $i$, prove that the assumed spectrum is impossible.

<details><summary><strong>Solution</strong></summary>

Apply $\alpha$:

$$
0=\alpha(F_0)+\sum_i p_i\alpha(F_i).
$$

The first term is strictly positive. Every term in the sum is nonnegative because $p_i\ge0$ and $\alpha(F_i)\ge0$. Hence the right side is strictly positive, contradicting equality to zero. The assumptions cannot be realized by a unitary CFT.

</details>

### Exercise 5: Conservation as shortening

Use the spin-$\ell$ unitarity bound

$$
\Delta\ge \ell+d-2
$$

for $\ell\ge1$ to identify the dimensions of a conserved current and the stress tensor.

<details><summary><strong>Solution</strong></summary>

For a spin-one current, $\ell=1$, so saturation gives

$$
\Delta=d-1.
$$

This is the dimension of a conserved global current $J_\mu$ satisfying $\partial^\mu J_\mu=0$.

For a spin-two stress tensor, $\ell=2$, so saturation gives

$$
\Delta=d.
$$

This is the dimension of $T_{\mu\nu}$ satisfying $\partial^\mu T_{\mu\nu}=0$. In both cases, conservation is the null descendant responsible for multiplet shortening.

</details>

## References

- G. Mack, “All unitary ray representations of the conformal group SU(2,2) with positive energy,” 1977.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, lectures on radial quantization, unitarity bounds, and bootstrap positivity.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, sections on reflection positivity, unitarity, and semidefinite programming.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” sections on unitarity constraints, OPE coefficients, conserved currents, and numerical methods.
- T. Hartman, S. Jain, and S. Kundu, “Causality Constraints in Conformal Field Theory,” for Lorentzian positivity and conformal collider-style constraints.

## Version history

- 2026-06-28: First polished draft. Added reflection-positivity setup, positive two-point coefficients, OPE-weight positivity, mixed-correlator matrix positivity, unitarity bounds, functional exclusion logic, caveats, exercises, and a reflection-positivity figure.
