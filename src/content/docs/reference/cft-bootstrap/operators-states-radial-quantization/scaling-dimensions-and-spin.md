---
title: "Scaling Dimensions and Spin"
description: "Explains how scaling dimensions and spin label local operators in a conformal field theory, how these labels appear in correlation functions, and how unitarity constrains them."
sidebar:
  label: "Scaling Dimensions and Spin"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Minwalla 1998"
topics:
  - scaling dimensions
  - spin
  - conformal representations
  - local operators
  - unitarity bounds
  - anomalous dimensions
  - two-dimensional CFT
canonicalTopics:
  - scaling-dimensions
  - spin-representations
  - operator-quantum-numbers
  - conformal-representation-labels
  - unitarity-bounds
researchStatus:
  established:
    - 'Primary local operators in a CFT are labeled by their scaling dimension and by a representation of the rotation group, together with any internal global-symmetry representation.'
    - 'In radial quantization, the scaling dimension is the eigenvalue of the cylinder Hamiltonian $D$, while spin is the representation carried under rotations of the spatial sphere.'
  active:
    - "The general representation theory is standard; active work concerns precise spectra in interacting CFTs, spinning operators, mixed-symmetry representations, defects, supersymmetric shortening, and nonunitary or logarithmic generalizations."
---

## Summary

Scaling dimensions and spin are the basic quantum numbers of local operators in a conformal field theory. A primary operator $\mathcal O_a$ is labeled by

$$
D|\mathcal O_a\rangle=\Delta|\mathcal O_a\rangle,
\qquad
M_{\mu\nu}|\mathcal O_a\rangle=(\Sigma_{\mu\nu})_a{}^b|\mathcal O_b\rangle,
$$

where $D$ is the dilatation generator, $M_{\mu\nu}$ are rotation generators, $\Delta$ is the scaling dimension, and $a$ packages the spin indices. In radial quantization, $D$ is the Hamiltonian on the cylinder $\mathbb R\times S^{d-1}$, so $\Delta$ is literally an energy eigenvalue in that Hilbert space.

For a scalar primary, the two-point function is fixed up to normalization:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

For spinning operators, the power $|x|^{-2\Delta}$ is still controlled by the scaling dimension, while the numerator is fixed by the spin representation and by inversion tensors. Thus $\Delta$ controls radial falloff; spin controls angular structure.

In two dimensions, the same information is often recorded as holomorphic and antiholomorphic weights:

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The bootstrap treats $\Delta$ and spin not as decoration, but as unknown dynamical data. The spectrum of scaling dimensions and spins is part of the CFT data.

:::note[The slogan]
Masses label particles in a massive QFT. Scaling dimensions and spin label local operators in a CFT.
:::

## Prerequisites

You should know the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/), the distinction between [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), and the representation language introduced in [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/). The pages [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/) and [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/) explain why $D$ grades operators and why $P_\mu$ raises the scaling dimension.

This page uses Euclidean CFT notation. Lorentzian continuation changes the interpretation of rotations and causal ordering, but not the basic idea that local operators are labeled by dimensions and spin representations.

## Core idea

A conformal field theory has no intrinsic mass scale. That does not mean it has no quantum numbers. Instead of labeling local excitations by masses, one labels local operators by how they transform under the conformal group.

The most important labels are:

| Label | Meaning | Where it appears |
|---|---|---|
| $\Delta$ | eigenvalue of $D$ on the state created by the operator | power laws, cylinder energies, OPE exponents |
| spin | representation of $SO(d)$ or $\operatorname{Spin}(d)$ | tensor structures, selection rules, conformal blocks |
| global representation | representation of internal symmetries | OPE channels, crossing equations, current multiplets |

The pair $(\Delta,\text{spin})$ is the CFT analogue of $(m,s)$ for particles. A particle mass determines time evolution in flat-space scattering. A scaling dimension determines radial evolution in a CFT.

This is why the operator spectrum is usually written schematically as

$$
\left\{\mathcal O_i,\Delta_i,\rho_i\right\},
$$

where $\rho_i$ is a spacetime-spin representation, usually together with a global-symmetry representation that is left implicit in this notation.

## Setup and conventions

We work on flat Euclidean $\mathbb R^d$ unless stated otherwise. The conformal algebra contains rotations $M_{\mu\nu}$, translations $P_\mu$, special conformal transformations $K_\mu$, and dilatations $D$. In the convention used in this volume,

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu.
$$

A primary state satisfies

$$
K_\mu|\mathcal O_a\rangle=0,
$$

and has definite dimension and spin:

$$
D|\mathcal O_a\rangle=\Delta|\mathcal O_a\rangle,
$$

$$
M_{\mu\nu}|\mathcal O_a\rangle=(\Sigma_{\mu\nu})_a{}^b|\mathcal O_b\rangle.
$$

The matrices $\Sigma_{\mu\nu}$ define a representation of the rotation algebra. For a scalar, $\Sigma_{\mu\nu}=0$. For a vector, they are the usual vector-representation matrices. For a spinor, one works with the double cover $\operatorname{Spin}(d)$.

A descendant at level $n$ has dimension $\Delta+n$:

$$
D P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
=(\Delta+n)P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle,
$$

as long as the descendant is not set to zero by a null relation or conservation law.

## Scaling dimensions

The scaling dimension $\Delta$ is defined by the action of dilatations. For a scalar primary,

$$
x^\mu\mapsto x'^\mu=\lambda x^\mu
$$

acts as

$$
\mathcal O'(x')=\lambda^{-\Delta}\mathcal O(x).
$$

Equivalently, the infinitesimal action is

$$
[D,\mathcal O(x)]
=\left(x\cdot\partial+\Delta\right)\mathcal O(x)
$$

up to the global sign convention used for active versus passive transformations. The invariant content is that $D$ measures the power with which the operator scales.

For a spinning primary, the dilatation part is the same:

$$
\mathcal O'_a(x')=\lambda^{-\Delta}\mathcal O_a(x),
$$

while rotations act on the index $a$.

Scaling dimensions are observable CFT data. They control the leading behavior of correlation functions, the relevance of deformations, the eigenvalues of the cylinder Hamiltonian, and the exponents in OPE limits.

### Classical dimensions and anomalous dimensions

In a Lagrangian description, an operator often has an engineering dimension inherited from the free-field kinetic terms. At an interacting fixed point, the scaling dimension is generally

$$
\Delta=\Delta_{\rm classical}+\gamma,
$$

where $\gamma$ is an anomalous dimension. This formula is useful perturbatively, but the exact scaling dimension is the eigenvalue of $D$, not the classical dimension plus a decoration.

For example, in a free scalar CFT in $d>2$,

$$
\Delta_\phi=\frac{d-2}{2}.
$$

At the Wilson–Fisher fixed point, the field analogous to $\phi$ has

$$
\Delta_\phi=\frac{d-2+\eta}{2},
$$

where $\eta$ is the anomalous-dimension critical exponent. The operator is not less “the same kind of object” because $\Delta$ moved. Its exact scaling dimension is what the fixed point says it is.

### Relevance of scalar deformations

If a scalar primary $\mathcal O$ is used to deform a $d$-dimensional CFT by

$$
S\mapsto S+g\int d^d x\,\mathcal O(x),
$$

then the coupling has dimension

$$
[g]=d-\Delta.
$$

Thus, at the undeformed fixed point,

| Condition | Name | First interpretation |
|---|---|---|
| $\Delta<d$ | relevant | grows toward the infrared |
| $\Delta=d$ | marginal | needs higher-order information |
| $\Delta>d$ | irrelevant | suppressed toward the infrared |

This classification belongs conceptually to RG flows, but it is recorded here because it is one of the most common uses of $\Delta$. A scalar being marginal by dimension does not automatically mean it is exactly marginal. Quantum corrections may make the deformation marginally relevant or marginally irrelevant unless extra structure prevents it.

## Spin in d dimensions

Spin is the representation carried by the operator under rotations around the insertion point. In Euclidean $d$ dimensions, the relevant group is $SO(d)$, or $\operatorname{Spin}(d)$ for spinor operators.

The most common representation family in bootstrap calculations is the symmetric traceless tensor representation of rank $\ell$:

$$
\mathcal O_{\mu_1\cdots\mu_\ell}(x)
=
\mathcal O_{(\mu_1\cdots\mu_\ell)}(x),
\qquad
\delta^{\mu_i\mu_j}\mathcal O_{\mu_1\cdots\mu_\ell}(x)=0.
$$

Here $\ell=0$ is a scalar, $\ell=1$ is a vector, and $\ell=2$ includes stress-tensor-type operators. In general dimensions there are also antisymmetric tensors, mixed-symmetry tensors, and spinor or tensor-spinor representations.

A compact way to write symmetric traceless tensors is to introduce a null polarization vector $z^\mu$ with $z^2=0$ and define

$$
\mathcal O(x,z)
=\mathcal O_{\mu_1\cdots\mu_\ell}(x)z^{\mu_1}\cdots z^{\mu_\ell}.
$$

The condition $z^2=0$ automatically discards traces. This notation is common in spinning-correlator and conformal-block formulas.

### Spin is not the same as statistics

In a relativistic unitary CFT, spin and statistics are related in the usual way, but they are not the same label. The spin label tells you how an operator transforms under rotations. Statistics tells you about signs under exchange and locality properties.

A scalar operator can be a bosonic composite such as $\phi^2$. A spinor operator can be fermionic. A line or defect operator has its own additional structure. In a local bosonic CFT, local operators usually have integer spin under $2\pi$ rotations, while fermionic CFTs naturally include spinor local operators after choosing spin structure.

### Descendants can carry different spin

A primary has one spin representation, but its descendants generally decompose into many spin representations. If $\mathcal O$ is a scalar primary, its first descendant $\partial_\mu\mathcal O$ is a vector. Its second descendants decompose as

$$
\partial_\mu\partial_\nu\mathcal O
=
\left(\partial_\mu\partial_\nu-
\frac{1}{d}\delta_{\mu\nu}\partial^2\right)\mathcal O
+
\frac{1}{d}\delta_{\mu\nu}\partial^2\mathcal O.
$$

The first term is symmetric traceless spin two; the second is scalar. Both are descendants of the same scalar primary. Therefore, when a table lists a primary of spin zero, it is not claiming that every operator in the multiplet has spin zero.

## Two-dimensional weights

In two-dimensional CFT, local operators are usually labeled by two weights:

$$
(h,\bar h).
$$

For global conformal transformations,

$$
L_0|\mathcal O\rangle=h|\mathcal O\rangle,
\qquad
\bar L_0|\mathcal O\rangle=\bar h|\mathcal O\rangle.
$$

The scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

A scalar has $h=\bar h$. A holomorphic current has $(h,\bar h)=(1,0)$ and therefore $\Delta=1$, $s=1$. The holomorphic stress tensor has $(h,\bar h)=(2,0)$ and therefore $\Delta=2$, $s=2$.

In a local bosonic two-dimensional CFT, mutual locality often requires integer spin for local bosonic operators:

$$
s=h-\bar h\in\mathbb Z.
$$

Fermionic theories and theories with extended objects require the usual refinements involving spin structure, sectors, and locality with respect to a chosen operator algebra.

Two-dimensional CFT also has Virasoro representation theory. A Virasoro primary carries $(h,\bar h)$ and has descendants generated by $L_{-n}$ and $\bar L_{-n}$ for $n>0$. The global labels $\Delta$ and $s$ remain useful, but Virasoro symmetry supplies much more structure than global conformal symmetry alone.

## Correlation functions know the labels

Conformal symmetry fixes two-point functions so strongly that the labels $(\Delta,\text{spin})$ become directly visible.

For scalar primaries in a basis with diagonal two-point functions,

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{C_i\delta_{ij}}{|x|^{2\Delta_i}}
$$

when the operators have distinct quantum numbers and the basis has been orthogonalized. Degenerate operators with the same $\Delta$ and the same spin can mix; then $C_i\delta_{ij}$ is replaced by a positive matrix in a unitary theory.

For vector primaries,

$$
\langle V_\mu(x)V_\nu(0)\rangle
=\frac{C_V I_{\mu\nu}(x)}{|x|^{2\Delta_V}},
$$

where

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}
$$

is the inversion tensor. For a symmetric traceless spin-$\ell$ primary, the two-point function contains the corresponding symmetrized traceless product of $I_{\mu\nu}(x)$, divided by $|x|^{2\Delta}$.

This is the first place where the division of labor becomes clear:

$$
\Delta \quad \text{sets the radial power},
\qquad
\text{spin} \quad \text{sets the angular tensor structure}.
$$

Three-point functions and four-point conformal blocks make the same division more elaborate. Spinning operators allow multiple tensor structures, and each structure can have its own OPE coefficient.

## Common examples

| Operator | Spin | Scaling dimension | Comment |
|---|---:|---:|---|
| Identity $\mathbf 1$ | $0$ | $0$ | Creates the vacuum state. |
| Free scalar $\phi$ in $d>2$ | $0$ | $(d-2)/2$ | Saturates the scalar unitarity bound. |
| Conserved current $J_\mu$ | $1$ | $d-1$ | Conservation makes the multiplet short. |
| Stress tensor $T_{\mu\nu}$ | $2$ | $d$ | Universal in local CFTs with translations. |
| Scalar deformation $\mathcal O$ | $0$ | variable | Relevant, marginal, or irrelevant according to $\Delta$ relative to $d$. |

The current and stress-tensor dimensions are fixed by conservation. For example,

$$
\partial^\mu J_\mu=0
$$

is compatible with scale covariance only if $\Delta_J=d-1$ for a primary conserved current. Similarly,

$$
\partial^\mu T_{\mu\nu}=0
$$

fixes $\Delta_T=d$ for the stress tensor.

## Unitarity bounds

In a unitary CFT, radial quantization gives a Hilbert space with nonnegative norms. Since descendants are obtained by acting with $P_\mu$ and since

$$
P_\mu^\dagger=K_\mu,
$$

the conformal algebra computes descendant norms in terms of $\Delta$ and spin. Requiring these norms to be nonnegative gives lower bounds on $\Delta$.

For $d\ge3$, the most commonly used bounds are:

| Primary representation | Unitarity bound | Saturation means |
|---|---:|---|
| scalar, excluding identity | $\Delta\ge (d-2)/2$ | free-scalar-type equation of motion |
| symmetric traceless spin $\ell\ge1$ | $\Delta\ge \ell+d-2$ | conserved current-type shortening |

Thus a spin-one conserved current has

$$
\Delta_J=d-1,
$$

and a spin-two stress tensor has

$$
\Delta_T=d.
$$

For spinors and mixed-symmetry tensors there are analogous representation-dependent bounds. The exact table is best treated in a dedicated unitarity-bounds page, because the answer depends on the $SO(d)$ representation.

The identity operator is a special scalar with $\Delta=0$. It does not violate the scalar bound because it forms the trivial vacuum multiplet rather than an ordinary nontrivial scalar multiplet.

## Degeneracy and operator mixing

In an interacting CFT, operators with the same spin and global quantum numbers can mix. A Lagrangian composite such as

$$
\phi^4,
\qquad
\phi\partial^2\phi,
\qquad
(\partial_\mu\phi)(\partial^\mu\phi)
$$

may not itself be an eigenoperator of $D$. The actual CFT primaries are obtained by diagonalizing the dilatation operator within the allowed operator space, while removing descendants and null operators.

This is one reason the bootstrap language is cleaner than a raw Lagrangian basis. The bootstrap starts from the eigenbasis:

$$
D|\mathcal O_i\rangle=\Delta_i|\mathcal O_i\rangle.
$$

The price is that the numbers $\Delta_i$ and OPE coefficients must be determined dynamically.

Degenerate primaries can also have the same $\Delta$ accidentally or because of symmetry. Then the label $\Delta$ alone is not enough. One must include spin, global representation, parity, and any other exact quantum numbers.

## Lorentzian interpretation

The CFT data are often defined in Euclidean signature because reflection positivity and radial quantization are especially clean there. After analytic continuation to Lorentzian signature, the same local operators transform under Lorentz representations, and the same scaling dimensions appear in Wightman functions, commutators, lightcone OPEs, and causal constraints.

The word “spin” can therefore mean slightly different things in different contexts:

| Context | Natural group |
|---|---|
| Euclidean local CFT data | $SO(d)$ or $\operatorname{Spin}(d)$ |
| Lorentzian local tensor notation | $SO(d-1,1)$ or its double cover |
| Radial quantization on $S^{d-1}$ | rotations of the spatial sphere |
| Two-dimensional CFT | $h-\bar h$ |

These descriptions are compatible, but not identical pieces of language. A careful page states which one it is using.

## Practical checklist

When recording a local operator, include the following data.

| Data | Question to ask |
|---|---|
| Scaling dimension | What is the eigenvalue of $D$? |
| Spin representation | Scalar, vector, spinor, symmetric traceless tensor, form, mixed-symmetry tensor? |
| Global representation | Singlet, fundamental, adjoint, charged sector, parity label? |
| Primary or descendant? | Is it annihilated by $K_\mu$ at the origin? |
| Shortening relation | Does a conservation law, equation of motion, or null relation remove descendants? |
| Normalization | What is the two-point coefficient convention? |

For bootstrap work, forgetting any one of these can put an operator in the wrong crossing equation.

## Common pitfalls

**Do not confuse scaling dimension with engineering dimension.** Engineering dimensions are useful near a weakly coupled description. The CFT scaling dimension is the exact eigenvalue of $D$.

**Do not call every spin-$\ell$ operator a symmetric traceless tensor.** Symmetric traceless tensors are common, but spinors, forms, and mixed-symmetry tensors are also local operators in appropriate CFTs.

**Do not confuse spin with level.** A level-$n$ descendant has dimension $\Delta+n$, but its spin depends on how tensor products with $n$ vector derivatives decompose.

**Do not forget the identity exception.** The identity has $\Delta=0$ even in $d>2$, but it is the vacuum multiplet, not an ordinary scalar above the scalar unitarity bound.

**Do not assume marginal means exactly marginal.** A scalar with $\Delta=d$ is marginal at first order. Exact marginality is a stronger dynamical statement.

**Do not use two-dimensional notation in higher dimensions without translation.** The pair $(h,\bar h)$ is special to two-dimensional CFT. In $d>2$, use $\Delta$ and an $SO(d)$ representation.

## Relations to other pages

[Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) defines the states whose labels are $\Delta$ and spin.

[Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) explains how a primary with fixed labels generates a tower of descendants.

[Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) explains why $\Delta$ is an energy on the cylinder and why positivity constrains it.

[Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) develops the representation-dependent lower bounds on $\Delta$.

[Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/) shows explicitly how $\Delta$ and spin determine two-point structures.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) explains how $\Delta$ and spin label exchanged blocks in four-point functions.

## Research status

The use of scaling dimensions and spin as labels of conformal representations is settled. These labels are foundational in two-dimensional CFT, higher-dimensional CFT, conformal perturbation theory, numerical bootstrap, analytic bootstrap, and AdS/CFT.

The active problems are quantitative and structural. Quantitatively, one wants spectra and OPE coefficients for strongly coupled CFTs such as the 3D Ising CFT, $O(N)$ models, gauge-theory fixed points, and supersymmetric theories. Structurally, one wants efficient bases for spinning operators, precise treatment of mixed-symmetry representations, defect operator spectra, nonunitary spectra, logarithmic mixing, and multiplet recombination along RG flows.

## Exercises

### Exercise 1: Two-point scaling

Suppose a scalar primary has a two-point function

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=F(|x|).
$$

Use scale invariance to show that

$$
F(|x|)=\frac{C}{|x|^{2\Delta}}.
$$

<details><summary><strong>Solution</strong></summary>

Under $x\mapsto \lambda x$, each scalar primary contributes a factor $\lambda^{-\Delta}$. Therefore

$$
F(\lambda |x|)=\lambda^{-2\Delta}F(|x|).
$$

The solutions of this homogeneity equation are

$$
F(|x|)=\frac{C}{|x|^{2\Delta}},
$$

where $C$ is a constant fixed by normalization.

</details>

### Exercise 2: Dimension of descendants

Let $|\mathcal O\rangle$ have dimension $\Delta$. Show that $P_\mu|\mathcal O\rangle$ has dimension $\Delta+1$.

<details><summary><strong>Solution</strong></summary>

Using $[D,P_\mu]=P_\mu$,

$$
D P_\mu|\mathcal O\rangle
=P_\mu D|\mathcal O\rangle+[D,P_\mu]|\mathcal O\rangle
=(\Delta+1)P_\mu|\mathcal O\rangle.
$$

Thus the first descendant has dimension $\Delta+1$, unless it vanishes as a null state.

</details>

### Exercise 3: Two-dimensional weights

A two-dimensional primary has weights $(h,\bar h)=(3/2,1/2)$. Find $\Delta$ and $s$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\Delta=h+\bar h=\frac32+\frac12=2,
$$

and

$$
s=h-\bar h=\frac32-\frac12=1.
$$

The operator has scaling dimension $2$ and spin $1$.

</details>

### Exercise 4: Conserved-current dimension

A spin-one primary current $J_\mu$ in $d$ dimensions obeys

$$
\partial^\mu J_\mu=0.
$$

Use dimensional analysis of the conservation equation to explain why the conserved-current dimension is naturally $\Delta_J=d-1$.

<details><summary><strong>Solution</strong></summary>

The conserved charge is an integral over a spatial sphere or time slice. In ordinary flat-space notation,

$$
Q=\int d^{d-1}x\,J_0.
$$

A dimensionless conserved charge requires

$$
[J_0]=d-1.
$$

In a CFT, the current is a primary vector with scaling dimension equal to its operator dimension, so

$$
\Delta_J=d-1.
$$

Equivalently, in conformal representation theory this is the spin-one unitarity-bound saturation point, where the divergence descendant becomes null.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See the global conformal invariance and operator formalism chapters for dimensions, spin, and two-dimensional weights.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. A standard higher-dimensional introduction to operator dimensions, spin, radial quantization, and unitarity bounds.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Useful for modern bootstrap conventions, radial quantization, and representation-theoretic normalization.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Review of CFT kinematics, unitarity constraints, conformal blocks, and bootstrap applications.
- S. Minwalla, “Restrictions Imposed by Superconformal Invariance on Quantum Field Theories,” *Advances in Theoretical and Mathematical Physics* **2** (1998), arXiv:hep-th/9712074. Standard source for unitarity bounds and shortening logic.

## Version history

- 2026-06-27: First polished draft. Explains scaling dimensions and spin as local-operator quantum numbers, relates them to correlation functions and radial quantization, records common unitarity bounds, and separates higher-dimensional and two-dimensional notation.
