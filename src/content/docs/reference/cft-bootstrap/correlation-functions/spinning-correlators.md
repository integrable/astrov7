---
title: "Spinning Correlators"
description: "Explains how conformal symmetry constrains correlation functions of operators with spin using polarization vectors, tensor structures, conservation, and Ward identities."
sidebar:
  label: "Spinning Correlators"
  order: 6
level: Graduate
status: "Polished draft"
source: "Osborn and Petkou 1994; Costa, Penedones, Poland, and Rychkov 2011; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - spinning operators
  - tensor structures
  - correlation functions
  - conformal bootstrap
canonicalTopics:
  - spinning-correlators
  - tensor-structures
  - symmetric-traceless-operators
  - spinning-bootstrap
researchStatus:
  established:
    - "Correlation functions of spinning primaries are fixed by conformal covariance up to finitely many tensor structures and functions of cross ratios."
    - "Conservation laws, permutation symmetries, parity, and Ward identities reduce the allowed tensor structures and impose physical normalization constraints."
  active:
    - "Efficient bases for spinning tensor structures, spinning conformal blocks, Lorentzian inversion formulas with spin, and large mixed-correlator bootstrap systems remain active research tools."
---

## Summary

Spinning correlators are correlation functions involving operators with spacetime indices: vectors, currents, stress tensors, fermions, and higher-spin symmetric traceless tensors. They contain two kinds of information at once:

1. the same position dependence and cross-ratio dependence that scalar correlators have;
2. tensor structures that tell the indices how to transform.

For a symmetric traceless spin-$\ell$ primary, it is convenient to hide the indices in a null auxiliary polarization vector $s^\mu$:

$$
\mathcal O_{\Delta,\ell}(x,s)
=
\mathcal O_{\mu_1\cdots\mu_\ell}(x)
 s^{\mu_1}\cdots s^{\mu_\ell},
\qquad s^2=0.
$$

The condition $s^2=0$ discards traces. In this notation, the two-point function of a spin-$\ell$ primary has the compact form

$$
\langle \mathcal O_{\Delta,\ell}(x_1,s_1)
\mathcal O_{\Delta,\ell}(x_2,s_2)\rangle
=
\frac{C_{\mathcal O}\,H_{12}^{\ell}}{(x_{12}^2)^\Delta},
$$

where

$$
H_{12}=s_1^\mu I_{\mu\nu}(x_{12})s_2^\nu,
\qquad
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

The real new feature appears at three and four points. Instead of one scalar coefficient, there may be several independent tensor structures. A spinning three-point function is a finite sum,

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\sum_a \lambda_{123}^{(a)}\,
\text{structure}_a(x_i,s_i),
$$

and a spinning four-point function is a finite sum of tensor structures multiplied by functions of $u$ and $v$.

:::note[One line to remember]
Scalar correlators ask what function of cross ratios appears. Spinning correlators also ask which tensor structures are allowed.
:::

## Prerequisites

You should know [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/), and [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/).

This page focuses on bosonic symmetric traceless tensor operators in flat Euclidean space. Fermions, mixed-symmetry tensors, supersymmetric multiplets, and defect tensors use the same philosophy, but require additional representation-theory bookkeeping.

## Core idea

A scalar primary transforms simply under a conformal transformation $x\mapsto x'$:

$$
\phi'(x')=\Omega(x)^\Delta \phi(x),
$$

up to active/passive convention. A spin-$\ell$ primary also rotates its indices by the local orthogonal matrix induced by the conformal map. In components, a symmetric traceless tensor obeys schematically

$$
\mathcal O'_{\mu_1\cdots\mu_\ell}(x')
=
\Omega(x)^\Delta
R_{\mu_1}^{\ \nu_1}(x)\cdots R_{\mu_\ell}^{\ \nu_\ell}(x)
\mathcal O_{\nu_1\cdots\nu_\ell}(x),
$$

where $R(x)$ is the local rotation/reflection part of the Jacobian.

This is the source of tensor structures. A spinning correlator must carry the correct tensor representation at each insertion point and must still be invariant under the global conformal group. The answer is therefore built from conformally covariant index contractions.

The useful strategy is:

$$
\text{write indices with polarizations}
\quad\longrightarrow\quad
\text{build covariant blocks}
\quad\longrightarrow\quad
\text{impose symmetry and conservation}.
$$

This page explains that strategy without requiring the full embedding-space formalism.

## Setup and conventions

We work in Euclidean $\mathbb R^d$ with

$$
x_{ij}^\mu=x_i^\mu-x_j^\mu,
\qquad
x_{ij}^2=x_{ij}\cdot x_{ij}.
$$

Spinning operators are packaged with auxiliary polarization vectors $s_i^\mu$. These polarizations are not physical fields. They are bookkeeping devices for tensor indices. The notation $s_i$ is deliberately used instead of $z_i$ to avoid confusion with the cross-ratio variables $z,\bar z$.

For a symmetric traceless tensor,

$$
\mathcal O(x,s)=
\mathcal O_{\mu_1\cdots\mu_\ell}(x)s^{\mu_1}\cdots s^{\mu_\ell}
$$

is homogeneous of degree $\ell$ in $s$:

$$
\mathcal O(x,\alpha s)=\alpha^\ell \mathcal O(x,s).
$$

Tracelessness is encoded by working modulo terms proportional to $s^2$, or equivalently by imposing $s^2=0$ after contractions are formed. If one needs explicit components, one expands the polynomial and projects onto the symmetric traceless part.

The spin-$\ell$ representation discussed here is the representation of $SO(d)$ carried by a rank-$\ell$ symmetric traceless tensor. In $d=3$, this corresponds to ordinary integer spin $\ell$. In higher dimensions, it is one family among many possible $SO(d)$ representations.

## Two-point functions with spin

The inversion tensor

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}
$$

is the basic object that transports vector indices between two points in a conformally covariant way. It satisfies

$$
I_{\mu\rho}(x)I_{\rho\nu}(x)=\delta_{\mu\nu},
\qquad
I_{\mu\nu}(\lambda x)=I_{\mu\nu}(x).
$$

For a vector primary $J_\mu$ of dimension $\Delta$, conformal covariance fixes

$$
\langle J_\mu(x)J_\nu(0)\rangle
=\frac{C_J}{(x^2)^\Delta}I_{\mu\nu}(x),
$$

up to normalization and internal-symmetry indices.

For a symmetric traceless spin-$\ell$ primary,

$$
\langle \mathcal O_{\Delta,\ell}(x_1,s_1)
\mathcal O_{\Delta,\ell}(x_2,s_2)\rangle
=
\frac{C_{\mathcal O}}{(x_{12}^2)^\Delta}
\left(s_1\cdot I(x_{12})\cdot s_2\right)^\ell.
$$

In component notation this is the symmetric traceless projection of $\ell$ inversion tensors. The polarization-vector notation is not a trick; it is just the shortest clean way to write the unique tensor structure.

Two primaries with different scaling dimensions have vanishing two-point function in a diagonal basis. Two primaries with the same quantum numbers may have a nontrivial positive matrix of two-point coefficients, which one usually diagonalizes and normalizes before quoting CFT data.

:::note[Normalization choice]
A common bootstrap convention is to choose an orthonormal basis of nonconserved primary operators, so that $C_{\mathcal O}=1$. Conserved currents and the stress tensor are often kept with physical normalizations fixed by Ward identities, in which case their two-point coefficients $C_J$ and $C_T$ become meaningful CFT data.
:::

## Three-point tensor structures

At three points, spinning correlators are fixed up to finitely many constants. The constants are OPE coefficients, but now there can be more than one OPE coefficient for the same ordered triple of primary operators.

A convenient physical-space basis uses the two building blocks

$$
H_{ij}=s_i\cdot I(x_{ij})\cdot s_j
=
s_i\cdot s_j
-2\frac{(s_i\cdot x_{ij})(s_j\cdot x_{ij})}{x_{ij}^2},
$$

and

$$
V_{i,jk}=\frac{s_i\cdot x_{ij}}{x_{ij}^2}
-\frac{s_i\cdot x_{ik}}{x_{ik}^2}.
$$

The object $H_{ij}$ contracts one index at point $i$ with one index at point $j$. The object $V_{i,jk}$ gives one index at point $i$ by comparing the directions from $x_i$ to $x_j$ and $x_k$.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Tensor structures for spinning three-point functions](/figures/cft-bootstrap/spinning-three-point-structures.svg)

<figcaption>

Spinning three-point structures are built from covariant contractions. The edge objects $H_{ij}$ pair polarizations at two points, while $V_{i,jk}$ attaches the polarization at $x_i$ to the two directions from $x_i$ toward the other insertions.

</figcaption>
</figure>

For three symmetric traceless tensors of spins $\ell_1,\ell_2,\ell_3$, parity-even structures can be built from monomials

$$
V_{1,23}^{m_1}V_{2,31}^{m_2}V_{3,12}^{m_3}
H_{12}^{n_{12}}H_{13}^{n_{13}}H_{23}^{n_{23}},
$$

with nonnegative integers satisfying

$$
\begin{aligned}
m_1+n_{12}+n_{13}&=\ell_1,\\
m_2+n_{12}+n_{23}&=\ell_2,\\
m_3+n_{13}+n_{23}&=\ell_3.
\end{aligned}
$$

The powers of $x_{ij}$ multiplying these structures are fixed by scale covariance. The remaining coefficients are the independent OPE coefficients.

For example, for two scalar primaries and one spin-$\ell$ symmetric traceless primary,

$$
\langle \phi_1(x_1)\phi_2(x_2)\mathcal O_{\Delta,\ell}(x_3,s)\rangle
=
\lambda_{12\mathcal O}
\frac{V_{3,12}^\ell}
{x_{12}^{\Delta_1+\Delta_2-\Delta+\ell}
 x_{13}^{\Delta_1+\Delta-\Delta_2-\ell}
 x_{23}^{\Delta_2+\Delta-\Delta_1-\ell}},
$$

where $x_{ij}=|x_i-x_j|$. There is one parity-even structure. If $\phi_1=\phi_2$ are identical bosonic scalars, exchange symmetry forces $\lambda_{\phi\phi\mathcal O}=0$ for odd $\ell$.

This is the first practical place where students should stop and smile: the statement “only even spin appears in the OPE of identical scalars” is not a mysterious dynamical fact. It is Bose symmetry plus the transformation of $V_{3,12}$ under $1\leftrightarrow 2$.

## Parity-odd structures and dimension-specific identities

The structures above are parity even. In some dimensions, extra structures can be built using the Levi-Civita tensor. For example, in three dimensions a parity-odd three-point structure can involve

$$
\varepsilon_{\mu\nu\rho}s_i^\mu s_j^\nu x_{kl}^\rho.
$$

Such structures are essential in parity-violating CFTs, including Chern–Simons–matter theories.

There is also a reverse effect: in low dimensions, some apparently different parity-even structures become linearly dependent because of Schouten identities. The number of independent tensor structures is therefore dimension-dependent.

This is one reason modern spinning-bootstrap papers are careful about the basis. A basis that is clean in generic $d$ may be redundant in $d=3$, and a basis adapted to $d=3$ may hide the analytic dependence on $d$.

## Four-point spinning correlators

For scalar four-point functions, conformal symmetry leaves functions of $u$ and $v$. For spinning four-point functions, it leaves a vector of functions:

$$
\langle \mathcal O_1(x_1,s_1)\mathcal O_2(x_2,s_2)
\mathcal O_3(x_3,s_3)\mathcal O_4(x_4,s_4)\rangle
=
\sum_A Q_A(x_i,s_i)\,\mathcal G_A(u,v).
$$

Here $Q_A$ are independent tensor structures and $\mathcal G_A(u,v)$ are dynamical functions. The label $A$ can be thought of as a basis index in the space of allowed structures.

The OPE decomposes the vector of functions into spinning conformal blocks:

$$
\mathcal G_A(u,v)
=
\sum_{\mathcal O}\sum_{a,b}
\lambda_{12\mathcal O}^{(a)}
\lambda_{34\mathcal O}^{(b)}
G_{\Delta,\rho,A}^{ab}(u,v).
$$

The exchanged primary $\mathcal O$ has dimension $\Delta$ and an $SO(d)$ representation $\rho$. The labels $a,b$ run over independent three-point tensor structures in

$$
\langle \mathcal O_1\mathcal O_2\mathcal O\rangle,
\qquad
\langle \mathcal O_3\mathcal O_4\mathcal O\rangle.
$$

Thus spinning bootstrap equations are not just scalar equations with extra decorations. They are vector or matrix equations. This is why mixed-correlator and spinning bootstrap computations are powerful but technically demanding.

## Conservation and shortening

Conserved currents are spinning primaries with null descendants. A symmetric traceless conserved spin-$\ell$ current satisfies

$$
\partial^{\mu_1}J_{\mu_1\cdots\mu_\ell}=0,
\qquad
\Delta_J=d-2+\ell,
\qquad \ell\geq 1.
$$

For $\ell=1$, this gives a global-symmetry current of dimension $d-1$. For $\ell=2$, it gives the stress tensor of dimension $d$.

Conservation imposes differential equations on correlators away from coincident points. For example,

$$
\partial_{x_i}\cdot D_{s_i}
\langle J(x_i,s_i)\mathcal O_2\cdots\mathcal O_n\rangle=0,
\qquad x_i\ne x_j,
$$

where $D_s$ denotes the symmetric-traceless projection derivative that converts one polarization index back into a tensor index. The exact form of $D_s$ is a technical convenience; the conceptual statement is simple: the divergence of a conserved current must vanish except at contact points.

Conservation can reduce the number of independent tensor structures. It can also fix some coefficients by Ward identities. The stress tensor is the most important example: its coupling to two scalar primaries of equal dimension is fixed by the scalar dimension and the normalization of $T_{\mu\nu}$.

## Permutation symmetry

Identical operators impose additional constraints. Suppose a correlator contains two identical spin-$\ell$ bosonic primaries. Exchanging the two insertions must leave the correlator invariant:

$$
(x_i,s_i)\leftrightarrow (x_j,s_j).
$$

This can relate tensor-structure coefficients or force them to vanish. For fermionic operators, exchange includes the usual minus sign. For operators in nontrivial global-symmetry representations, permutation symmetry also acts on internal indices.

This sounds like bookkeeping, and it is. But it is not optional bookkeeping. Missing a permutation constraint is one of the easiest ways to write a bootstrap equation for a theory that cannot exist.

## A practical workflow

A clean spinning-correlator calculation usually follows this sequence.

| Step | Question | Output |
|---:|---|---|
| 1 | What are the spacetime and internal representations of the external operators? | Allowed index types and global-symmetry tensors. |
| 2 | What covariant tensor structures exist before conservation? | A basis $Q_A$ or three-point structures $a$. |
| 3 | Are there parity-odd structures? | Extra structures involving $\varepsilon$ tensors, if allowed. |
| 4 | Are there dimension-specific identities? | A nonredundant basis in the desired dimension. |
| 5 | Are any operators conserved or shortened? | Differential constraints and fewer coefficients. |
| 6 | Are any operators identical? | Permutation constraints and selection rules. |
| 7 | What normalization is being used? | Physical OPE coefficients and positive two-point metrics. |

When this workflow is followed, tensor structures become a controlled finite-dimensional linear-algebra problem rather than a swamp. A swamp with indices, alas, but still a swamp with a map.

## Common pitfalls

**Confusing polarizations with physical vectors.** The auxiliary vector $s^\mu$ is not a new operator or background field. It only packages indices.

**Forgetting traces.** If $s^2\ne0$ is used carelessly, trace pieces reappear and the correlator no longer describes a symmetric traceless primary.

**Counting structures before imposing conservation.** Current and stress-tensor correlators generally have fewer independent coefficients than unconserved vector and spin-two correlators.

**Assuming all spinning structures are parity even.** In three-dimensional parity-violating CFTs, parity-odd tensor structures are often physical.

**Treating scalar positivity as automatic for spinning systems.** In a spinning or mixed system, OPE coefficients can form matrices. Positivity is then matrix positivity with respect to the two-point inner product, not just positivity of a single number.

**Ignoring basis dependence.** Individual tensor-structure coefficients depend on the chosen basis. Physical statements should be phrased in basis-independent terms or in a clearly declared basis.

## Relations to other pages

[Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) applies this machinery to the universal spin-two operator. [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) does the same for global-symmetry currents. [Conformal Blocks](/cft-bootstrap/conformal-blocks/) explains how spinning three-point structures become labels on spinning conformal blocks, while [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) explains how matrix positivity enters numerical bootstrap systems.

The embedding-space formalism gives a more systematic way to generate the same structures. It is previewed in [Embedding-Space Formalism](/cft-bootstrap/correlation-functions/embedding-space-formalism-preview/) and developed further in the higher-dimensional CFT and conformal-block chapters.

## Research status

The kinematic classification of spinning two- and three-point functions is established. So is the conceptual role of tensor structures in four-point functions and bootstrap equations.

Several practical issues remain active: choosing numerically stable tensor bases, computing spinning conformal blocks efficiently, handling parity-odd systems, treating mixed-symmetry operators, and deriving Lorentzian inversion formulas with general external spin. These are technical frontiers, not doubts about the underlying conformal covariance.

## Exercises

### Exercise 1: Vector two-point function

Show that the vector two-point function

$$
\langle J_\mu(x)J_\nu(0)\rangle
=\frac{C_J}{(x^2)^\Delta}I_{\mu\nu}(x)
$$

is traceless only in the irrelevant sense that a vector has no trace, but is transverse only for a special value of $\Delta$. Compute $\partial^\mu\langle J_\mu(x)J_\nu(0)\rangle$ away from $x=0$ and find that value.

<details><summary><strong>Solution</strong></summary>

Use

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
$$

A direct derivative gives

$$
\partial^\mu\left[(x^2)^{-\Delta}I_{\mu\nu}(x)\right]
=2(\Delta-d+1)(x^2)^{-\Delta-1}x_\nu.
$$

Thus the two-point function is transverse away from the origin if

$$
\Delta=d-1.
$$

This is the spin-one unitarity-bound saturation value, exactly as expected for a conserved current.

</details>

### Exercise 2: Odd spin in the scalar OPE

Use the scalar–scalar–spin three-point function to show that an odd-spin symmetric traceless primary cannot appear in the OPE of two identical bosonic scalar primaries.

<details><summary><strong>Solution</strong></summary>

For two scalars and a spin-$\ell$ primary at $x_3$, the only parity-even structure is proportional to

$$
V_{3,12}^\ell.
$$

Under exchange $1\leftrightarrow 2$,

$$
V_{3,21}=-V_{3,12}.
$$

The rest of the position dependence is symmetric when the two scalars are identical. Therefore the three-point function changes by $(-1)^\ell$. Bose symmetry requires it to be invariant, so the coefficient must vanish for odd $\ell$.

</details>

### Exercise 3: Counting before and after conservation

Explain why the number of tensor structures in $\langle J_\mu \phi_1\phi_2\rangle$ for a vector primary $J_\mu$ can be larger before imposing conservation than after imposing conservation. Why is this not a contradiction with conformal symmetry?

<details><summary><strong>Solution</strong></summary>

Conformal symmetry classifies covariant structures for a primary vector of dimension $\Delta$. Conservation is an additional shortening condition:

$$
\partial^\mu J_\mu=0,
\qquad \Delta=d-1.
$$

It is not part of being a generic vector primary. Imposing it differentiates the correlator and sets the divergence to zero away from contact points. This gives linear equations for the coefficients of the conformally allowed structures. Some structures are removed or related. There is no contradiction: conservation is extra information about a special representation of the conformal algebra.

</details>

## References

- H. Osborn and A. C. Petkou, “Implications of Conformal Invariance in Field Theories for General Dimensions,” 1994.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Correlators,” 2011.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Blocks,” 2011.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, 2017.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D at least 3 Dimensions*, 2016.

## Version history

- 2026-06-27: First polished draft. Introduced polarization-vector notation, two- and three-point tensor structures, conservation constraints, four-point structure vectors, pitfalls, and exercises.
