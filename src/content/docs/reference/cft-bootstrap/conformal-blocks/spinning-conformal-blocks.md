---
title: "Spinning Conformal Blocks"
description: "Explains conformal blocks for correlators with spin, including tensor structures, matrix-valued blocks, conservation constraints, and bootstrap positivity."
sidebar:
  label: "Spinning Blocks"
  order: 6
level: Graduate
status: "Polished draft"
source: "Costa–Penedones–Poland–Rychkov 2011; Costa et al. 2016; Karateev–Kravchuk–Simmons-Duffin 2018; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - spinning conformal blocks
  - tensor structures
  - conformal blocks
  - mixed correlators
  - conserved currents
  - bootstrap positivity
canonicalTopics:
  - spinning-conformal-blocks
  - tensor-structures
  - conformal-blocks
  - mixed-correlator-bootstrap
  - spinning-bootstrap
researchStatus:
  established:
    - "Spinning conformal blocks decompose four-point functions with external tensor, spinor, or conserved operators into contributions of exchanged conformal multiplets and their tensor structures."
    - "The main new feature relative to scalar external operators is that a single exchanged primary can contribute through several three-point tensor structures and several four-point tensor structures."
  active:
    - "Efficient computation of spinning blocks for high-spin, mixed-symmetry, defect, supersymmetric, and high-precision bootstrap systems remains an active technical area."
---

## Summary

A **spinning conformal block** is the contribution of one exchanged conformal multiplet to a four-point function in which at least one external operator carries spin, or in which one keeps the full tensor-structure information of spinning exchange. The slogan is the same as for scalar blocks,

$$
\text{block} = \text{one conformal multiplet exchanged in one OPE channel},
$$

but the bookkeeping is richer. A scalar four-point function has a single tensor structure. A four-point function of currents, stress tensors, spinors, or mixed scalar-tensor operators usually has many tensor structures. The block is therefore not just a single scalar function of $u,v$; it is a collection of functions that multiply a basis of four-point tensor structures.

Schematically,

$$
\vec{\mathcal G}(u,v)
=
\sum_{\mathcal O}
\sum_{p,q}
\lambda_{12\mathcal O}^{(p)}
\lambda_{34\mathcal O}^{(q)}
\vec G_{\mathcal O}^{\,pq}(u,v).
$$

Here $p$ labels the independent tensor structures in the three-point function $\langle\mathcal O_1\mathcal O_2\mathcal O\rangle$, $q$ labels those in $\langle\mathcal O_3\mathcal O_4\mathcal O\rangle$, and $\vec G_{\mathcal O}^{\,pq}$ is a vector over four-point tensor structures. In identical or reflection-positive systems, these coefficients often assemble into positive semidefinite matrices, which is why spinning blocks are indispensable for current, stress-tensor, fermion, and mixed-correlator bootstrap problems.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A spinning conformal block has left three-point tensor structures, a projected exchanged multiplet, right three-point tensor structures, and a vector of four-point tensor structures.](/figures/cft-bootstrap/spinning-block-tensor-structures.svg)

<figcaption>

Spinning blocks keep track of more than the exchanged dimension and spin. The left and right OPEs can each have several three-point tensor structures, and the four-point function itself has a tensor-structure basis. For a fixed exchanged multiplet, the block is naturally a vector or matrix of functions of $u,v$.

</figcaption>
</figure>

## Prerequisites

You should know [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), and the [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/). The page assumes Euclidean CFT conventions from [Conventions and Notation](/cft-bootstrap/conventions/).

## Core idea

Scalar external operators hide a lot of structure. If $\phi_i$ are scalars, the OPE

$$
\phi_1\times\phi_2
$$

can exchange a spin-$\ell$ symmetric-traceless operator, but the three-point function $\langle\phi_1\phi_2\mathcal O_{\Delta,\ell}\rangle$ has at most one parity-even tensor structure. Therefore a scalar block is essentially one function per exchanged primary representation.

For spinning external operators, the same exchanged primary may couple in several independent ways. For example, the three-point function of two currents and a spin-$\ell$ operator may have several parity-even structures and, in some dimensions, parity-odd structures. The four-point function of four currents also has many tensor structures. A single exchanged multiplet must say how each left structure talks to each right structure and how the answer decomposes into four-point structures.

That is why spinning blocks are best thought of as **representation-theoretic kernels**:

$$
\text{left tensor structure}
\quad\longrightarrow\quad
\text{exchanged conformal multiplet}
\quad\longrightarrow\quad
\text{right tensor structure}.
$$

They are still fixed by conformal symmetry. The hard part is choosing a basis and computing the resulting functions without drowning in indices.

## Setup and conventions

Let $\mathcal O_i$ be primary operators with dimensions $\Delta_i$ and Lorentz representations $r_i$ of $SO(d)$ or $Spin(d)$. We suppress explicit tensor indices by contracting them with polarization variables $\zeta_i$. For symmetric-traceless tensors this is often a null polarization vector $z_i$ satisfying $z_i^2=0$; for spinors one uses spinor polarizations.

A four-point function can be written as

$$
\langle
\mathcal O_1(x_1,\zeta_1)
\mathcal O_2(x_2,\zeta_2)
\mathcal O_3(x_3,\zeta_3)
\mathcal O_4(x_4,\zeta_4)
\rangle
=
K_4(x_i)
\sum_{I=1}^{N_4}
\mathcal T_I(x_i,\zeta_i)\,
\mathcal G_I(u,v),
$$

where $K_4$ is a conventional scalar prefactor, $\mathcal T_I$ are conformally invariant four-point tensor structures, and $\mathcal G_I(u,v)$ are scalar functions of the cross-ratios.

Now insert the OPE in the $12\to34$ channel. If the exchanged primary is $\mathcal O$ in representation $r$, the left three-point function has a finite basis

$$
\langle\mathcal O_1\mathcal O_2\mathcal O\rangle
=
\sum_{p=1}^{N_{12\mathcal O}}
\lambda_{12\mathcal O}^{(p)}\,
\mathcal T_{12\mathcal O}^{(p)}.
$$

Similarly,

$$
\langle\mathcal O_3\mathcal O_4\mathcal O\rangle
=
\sum_{q=1}^{N_{34\mathcal O}}
\lambda_{34\mathcal O}^{(q)}\,
\mathcal T_{34\mathcal O}^{(q)}.
$$

The conformal block decomposition then has the form

$$
\mathcal G_I(u,v)
=
\sum_{\mathcal O}
\sum_{p=1}^{N_{12\mathcal O}}
\sum_{q=1}^{N_{34\mathcal O}}
\lambda_{12\mathcal O}^{(p)}
\lambda_{34\mathcal O}^{(q)}
G_{I,\mathcal O}^{pq}(u,v).
$$

The functions $G_{I,\mathcal O}^{pq}$ are the spinning conformal blocks in this tensor-structure basis.

:::note[What “spin” means here]
In bootstrap language, “spinning block” usually means a block for external spinning operators, not merely a scalar four-point block with spin-$\ell$ exchange. Scalar conformal blocks already allow spinning exchanged primaries. Spinning blocks are needed when tensor structures cannot be factored away.
:::

## Tensor structures are part of the data

The tensor structures in a three-point function are kinematic. The coefficients multiplying them are dynamical CFT data. Thus a spinning three-point function is not specified by one number unless symmetry leaves only one structure.

For example, for a scalar $\phi$, a conserved current $J_\mu$, and a spin-$\ell$ operator $\mathcal O_{\Delta,\ell}$, the number of independent structures depends on dimension, parity, conservation, and the representation of $\mathcal O$. Conservation may remove some structures or impose linear relations among their coefficients.

A useful way to organize this is:

| Object | Fixed by symmetry? | Dynamical? |
|---|---:|---:|
| Which tensor structures are allowed | yes | no |
| Coefficients $\lambda^{(p)}$ multiplying them | no | yes |
| Differential constraints from conservation | yes | no |
| Numerical value of conserved-current normalization | no | yes |
| Ward-fixed relation between a charge and a current OPE coefficient | yes, after normalization | partly convention-dependent |

This is why spinning blocks and spinning correlators should always be discussed together. A block basis without a corresponding three-point-structure convention is an index jungle with excellent camouflage.

## Projector definition

The clean definition uses a projector onto the conformal multiplet of the exchanged primary. Let $\mathcal P_{\Delta,r}$ denote the projector onto the multiplet generated by a primary of dimension $\Delta$ and Lorentz representation $r$. Then the contribution of this multiplet to the four-point function is

$$
\langle
\mathcal O_3\mathcal O_4
\mid
\mathcal P_{\Delta,r}
\mid
\mathcal O_1\mathcal O_2
\rangle.
$$

Expanding this matrix element in tensor-structure bases gives

$$
\langle
\mathcal O_3\mathcal O_4
\mid
\mathcal P_{\Delta,r}
\mid
\mathcal O_1\mathcal O_2
\rangle
=
K_4
\sum_{I,p,q}
\lambda_{12\mathcal O}^{(p)}
\lambda_{34\mathcal O}^{(q)}
\mathcal T_I\,
G_{I,\Delta,r}^{pq}(u,v).
$$

This formula mirrors the scalar case. The only new ingredients are the indices $I,p,q$. The exchanged multiplet is still one conformal multiplet. Its descendants are still fixed by symmetry. The spin just makes the external overlap with that multiplet multi-component.

## Differential-operator construction

One powerful way to compute spinning blocks is to obtain them from simpler blocks by applying conformally covariant differential operators. The idea is easiest to state for symmetric-traceless exchange. Many spinning three-point tensor structures can be generated by acting on scalar-scalar-spin structures:

$$
\mathcal T_{12\mathcal O}^{(p)}
=
\mathcal D_{12}^{(p)}\,
\mathcal T_{\phi_1\phi_2\mathcal O},
$$

where $\mathcal D_{12}^{(p)}$ acts on the positions and polarizations of points $1$ and $2$. Similarly,

$$
\mathcal T_{34\mathcal O}^{(q)}
=
\mathcal D_{34}^{(q)}\,
\mathcal T_{\phi_3\phi_4\mathcal O}.
$$

Because these operators act on the external points, they commute with the internal sum over descendants in the exchanged multiplet in the appropriate sense. Thus the corresponding block can be obtained schematically as

$$
K_4
\sum_I \mathcal T_I G_{I,\Delta,r}^{pq}(u,v)
=
\mathcal D_{12}^{(p)}\mathcal D_{34}^{(q)}
\left(K_4'\,g_{\Delta,r}^{\mathrm{seed}}(u,v)\right).
$$

The seed block is a simpler block from which a whole family can be generated. More modern weight-shifting operators systematize this idea: they shift dimensions and representations while preserving conformal covariance. Conceptually, they let one recycle scalar-block technology instead of rebuilding every spinning block from scratch.

## Casimir equations become systems

A scalar conformal block solves a scalar differential equation,

$$
\mathcal C_{12}g_{\Delta,\ell}(u,v)
=
C_{\Delta,\ell}g_{\Delta,\ell}(u,v).
$$

For spinning correlators, the Casimir operator acts on the tensor structures as well as on the cross-ratio dependence. Therefore the block vector obeys a coupled system:

$$
\sum_J
\mathcal C_{IJ}\,G_J(u,v)
=
C_{\Delta,r}G_I(u,v).
$$

The matrix differential operator $\mathcal C_{IJ}$ depends on the tensor-structure basis. This is not a new physical principle; it is the same statement that the exchanged multiplet is an irreducible representation. But it does mean that basis choices, conservation constraints, and numerical stability matter more than in the scalar case.

Radial coordinates remain useful. The radial expansion becomes a sum over descendant states with angular tensor structures, and the coefficients are fixed recursively. For high-precision work, one often combines radial expansions, pole recursions, and differential-operator methods.

## Conservation constraints

Conserved currents and stress tensors are the most important spinning operators in applications. They also come with differential constraints:

$$
\partial^\mu J_\mu=0,
\qquad
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

In embedding or polarization notation, these become linear differential equations on correlators. They have two effects.

First, they reduce the number of independent tensor structures. A general spin-one primary has more possible structures than a conserved current. Conservation removes the structures that are incompatible with shortening.

Second, Ward identities can fix some OPE coefficients in terms of charges or dimensions. For example, once the two-point normalization of $J_\mu$ is chosen, the coefficient of $J_\mu$ in the OPE of a charged operator with its conjugate is fixed by the charge. Once the physical stress tensor normalization is chosen, the $\mathcal O\mathcal O T$ coefficient is fixed by the scaling dimension of $\mathcal O$.

This is a common source of mistakes: conservation is not just a condition on the exchanged spectrum. It also constrains the allowed tensor structures and coefficients.

## Matrix positivity in unitary bootstrap

For identical real scalars, the bootstrap often contains coefficients of the form

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

Spinning and mixed-correlator bootstrap systems replace this scalar square by a positive semidefinite matrix. Suppose the same exchanged operator $\mathcal O$ appears in several OPEs among a set of external operators. Collect its OPE coefficients into a vector

$$
\vec\lambda_{\mathcal O}
=
(\lambda_1,\lambda_2,\ldots).
$$

Then its contribution has the schematic form

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}
\cdot
\vec G_{\mathcal O}(u,v).
$$

The outer product

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}
$$

is positive semidefinite in a unitary theory with reflection-positive normalization. This is the linear-algebra heart of mixed-correlator and spinning numerical bootstrap. The semidefinite program is not magic; it is the computational expression of Hilbert-space positivity applied to multiplets and tensor structures.

## Example: current four-point functions

A four-point function of conserved currents,

$$
\langle J_\mu(x_1)J_\nu(x_2)J_\rho(x_3)J_\sigma(x_4)\rangle,
$$

has several tensor structures. In the $JJ\to JJ$ OPE channel, the exchanged operators are organized by spin, parity, internal-symmetry representation, and conservation properties. The identity contributes a disconnected structure fixed by $\langle JJ\rangle$. The stress tensor contributes with coefficients related to current-stress-tensor three-point data. Other spin-even and spin-odd operators contribute with coefficients not fixed by Ward identities.

A bootstrap equation for $\langle JJJJ\rangle$ therefore constrains much more than scalar dimensions. It can constrain current central charges, stress-tensor central charges, parity-odd data in three dimensions, and gaps in sectors that scalars cannot see efficiently.

The same logic applies to $\langle TTTT\rangle$, but the tensor-structure space is larger and conservation is more demanding. The reward is correspondingly large: stress-tensor correlators probe universal energy-flow and causality data.

## Common pitfalls

**Mistaking exchange spin for spinning blocks.** A scalar four-point function with spin-$\ell$ exchange still uses scalar external blocks. Spinning blocks are needed when external indices or tensor structures are nontrivial.

**Ignoring basis dependence.** Individual functions $G_{I}^{pq}$ depend on the tensor-structure basis. Physical statements cannot depend on that basis. Good calculations track how OPE coefficients transform when the basis changes.

**Forgetting conservation.** A generic spin-one primary and a conserved current are not the same representation. Conservation removes structures and imposes Ward identities.

**Assuming all coefficients are positive numbers.** In spinning and mixed systems, positivity usually means positive semidefinite matrices, not nonnegative scalar coefficients.

**Treating parity-odd structures as optional decoration.** In odd spacetime dimensions, parity-odd tensor structures can be physically important. Dropping them is an assumption, not a theorem.

## Relations to other pages

- [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/) introduces the tensor structures that spinning blocks use.
- [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) explains the most important conserved spin-two example.
- [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) gives the projector interpretation.
- [Recursion Relations](/cft-bootstrap/conformal-blocks/recursion-relations/) explains radial and pole-recursion methods that also generalize to spinning systems.
- [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) uses the matrix-positivity structure introduced here.

## Research status

The conceptual definition of spinning blocks is settled: they are conformal-multiplet contributions to spinning four-point functions, resolved into tensor-structure bases. The practical frontier is computational. Efficient bases, conservation-compatible structures, weight-shifting formulas, radial recursions, pole recursions, and software pipelines determine which spinning bootstrap problems are tractable at high precision.

Several current research directions are especially active: stress-tensor and current bootstrap in three dimensions, fermion bootstrap, parity-violating theories, mixed scalar-current-stress systems, superconformal blocks, defect spinning blocks, and spinning blocks in Lorentzian inversion formulas.

## Exercises

### Exercise: Scalar external operators with spinning exchange

Explain why a four-point function of scalar primaries can exchange spin-$\ell$ operators without requiring spinning conformal blocks in the sense of this page.

<details>
<summary><strong>Solution</strong></summary>

The exchanged operator may transform in a nontrivial spin-$\ell$ representation, but the external operators carry no tensor indices. For scalar external operators, conformal symmetry fixes the relevant three-point structures $\langle\phi_1\phi_2\mathcal O_{\Delta,\ell}\rangle$ and $\langle\phi_3\phi_4\mathcal O_{\Delta,\ell}\rangle$ up to at most one coefficient in the parity-even symmetric-traceless case. The four-point function also has a single scalar tensor structure. Therefore the exchanged spin is encoded in a scalar function $g_{\Delta,\ell}(u,v)$, not in a vector or matrix of tensor-structure components.

</details>

### Exercise: Matrix positivity from OPE coefficients

Suppose an exchanged primary $\mathcal O$ appears in two OPEs with real coefficients $\lambda_1$ and $\lambda_2$. Show that the coefficient matrix

$$
M_{ij}=\lambda_i\lambda_j
$$

is positive semidefinite.

<details>
<summary><strong>Solution</strong></summary>

For any real vector $a_i$,

$$
a_iM_{ij}a_j
=
a_i\lambda_i\lambda_j a_j
=
\left(\sum_i a_i\lambda_i\right)^2
\ge0.
$$

Thus $M$ is positive semidefinite. In mixed-correlator bootstrap this simple outer-product fact is what turns crossing into a semidefinite program.

</details>

### Exercise: Conservation reduces structures

Why should a conserved current have fewer independent three-point tensor structures than a generic spin-one primary with the same scaling dimension?

<details>
<summary><strong>Solution</strong></summary>

A generic spin-one primary is constrained only by conformal covariance. A conserved current also obeys

$$
\partial^\mu J_\mu=0,
$$

away from contact terms. Applying this differential equation to a three-point function gives linear relations among the coefficients of conformally allowed tensor structures. Some structures fail the conservation equation and must be absent; others survive only in special combinations. Therefore conservation reduces the independent structure count.

</details>

### Exercise: Basis changes

Let $\mathcal T_I'=A_I{}^J\mathcal T_J$ be a new basis of four-point tensor structures. If

$$
\sum_I\mathcal T_I G_I
=
\sum_I\mathcal T'_I G'_I,
$$

how do the components $G_I$ and $G'_I$ relate?

<details>
<summary><strong>Solution</strong></summary>

Substitute $\mathcal T'_I=A_I{}^J\mathcal T_J$:

$$
\sum_J\mathcal T_J G_J
=
\sum_{I,J}A_I{}^J\mathcal T_J G'_I.
$$

Matching coefficients of $\mathcal T_J$ gives

$$
G_J=\sum_I A_I{}^J G'_I.
$$

Equivalently, in matrix notation $G=A^T G'$, so $G'=(A^T)^{-1}G$ when $A$ is invertible. Individual components are basis-dependent; the full correlator is not.

</details>

## References

- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Correlators,” 2011.
- M. S. Costa, J. Penedones, D. Poland, and S. Rychkov, “Spinning Conformal Blocks,” 2011.
- M. S. Costa, T. Hansen, J. Penedones, and E. Trevisani, “Radial Expansion for Spinning Conformal Blocks,” 2016.
- D. Karateev, P. Kravchuk, and D. Simmons-Duffin, “Weight Shifting Operators and Conformal Blocks,” 2018.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2017.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” 2019.

## Version history

- 2026-06-27: First polished draft. Defines spinning blocks, tensor-structure indices, differential-operator construction, conservation constraints, and matrix positivity for bootstrap use.
