---
title: "Conformal Data"
description: "Explains the spectrum, spins, symmetry representations, two-point normalizations, OPE coefficients, and consistency conditions that define a local conformal field theory."
sidebar:
  label: "Conformal Data"
  order: 3
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - conformal data
  - primary operators
  - scaling dimensions
  - spin
  - OPE coefficients
  - operator product expansion
  - crossing symmetry
  - bootstrap
canonicalTopics:
  - conformal-data
  - cft-data
  - local-operator-spectrum
  - ope-coefficients
  - crossing-consistency
researchStatus:
  established:
    - "In a local CFT, separated-point correlation functions are determined by the spectrum of primary operators, their representation labels, and their OPE coefficients, subject to consistency conditions."
    - "With orthonormal two-point functions, scalar three-point coefficients and scalar OPE coefficients are the same numbers."
  active:
    - "Classifying all consistent CFT data in dimensions greater than two is a major open-ended research program pursued through analytic, numerical, algebraic, and geometric methods."
---

## Summary

The conformal data of a local CFT is the information needed to reconstruct its separated-point local correlation functions. In the conventions of this volume, the slogan is

$$
\text{CFT data}
=
\left\{
\Delta_i,\rho_i,\lambda_{ijk}
\right\}
\quad
\text{plus global-symmetry labels and special protected data}.
$$

Here $\Delta_i$ are scaling dimensions, $\rho_i$ are spin and internal-symmetry representations, and $\lambda_{ijk}$ are OPE coefficients in a chosen two-point normalization. More explicitly, a local CFT contains primary operators $\mathcal O_i$, their descendants, and an operator product expansion

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_k
\lambda_{ijk}
|x|^{\Delta_k-\Delta_i-\Delta_j}
\left(\mathcal O_k(0)+\text{descendants}\right),
$$

with tensor structures and spin dependence included when the operators are not scalars.

The bootstrap philosophy is that CFT data is not arbitrary. It must obey conformal symmetry, locality, crossing symmetry, unitarity or reflection positivity when assumed, global-symmetry selection rules, Ward identities, and sometimes modular, boundary, defect, or anomaly constraints.

:::note[The central shift]
In a massive scattering theory, the central objects are particles and the $S$-matrix. In a CFT, the central objects are local operators and their OPE. The spectrum is not a list of masses; it is a list of scaling dimensions, spins, and symmetry representations.
:::

## Prerequisites

You should have read [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/) and the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/). You should know what primary and descendant operators are at a basic level, though their representation theory is developed later in [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/).

This page uses scalar formulas as the cleanest entry point. Spinning operators, conserved currents, stress tensors, supersymmetric multiplets, defects, and two-dimensional Virasoro representations add important refinements, but the same idea remains: a CFT is encoded by consistent operator data.

## Core idea

A conformal field theory is not specified by a Hamiltonian in the same way as a finite-dimensional quantum system, and it need not be specified by a Lagrangian. The intrinsic local specification is its operator algebra.

The local operator product expansion says that when two local operators approach each other, their product can be replaced inside correlation functions by a sum of local operators at one point:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x,\partial)\mathcal O_k(0).
$$

Conformal symmetry fixes the position dependence of $C_{ij}{}^k$ in terms of scaling dimensions, spin, and tensor structures. The remaining constants are OPE coefficients. These constants are the structure constants of the local operator algebra.

This is why CFT data is often compared to group-theory data. A Lie algebra is specified by generators and structure constants. A CFT local operator algebra is specified by operators, representation labels, and OPE coefficients, with infinitely many consistency conditions.

The bootstrap question is:

$$
\text{Which abstract CFT data define a consistent quantum field theory?}
$$

That question makes sense even when no microscopic Lagrangian is known.

## Setup and conventions

This page uses flat Euclidean $\mathbb R^d$ at separated points. Scalar primary two-point functions are normalized as

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}
$$

when the operators are real, scalar, and orthonormal. If operators have the same dimension and quantum numbers, one first diagonalizes the two-point matrix. If operators are complex, one pairs an operator with its conjugate:

$$
\langle \mathcal O_i(x)\mathcal O_j^\dagger(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

For scalar primaries, the three-point function is

$$
\langle
\mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)
\rangle
=
\frac{\lambda_{ijk}}
{x_{12}^{\Delta_i+\Delta_j-\Delta_k}
 x_{13}^{\Delta_i+\Delta_k-\Delta_j}
 x_{23}^{\Delta_j+\Delta_k-\Delta_i}}.
$$

With the two-point convention above, the same number $\lambda_{ijk}$ appears as the leading scalar OPE coefficient:

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\lambda_{ijk}
|x|^{\Delta_k-\Delta_i-\Delta_j}
\mathcal O_k(0).
$$

This equality is a convention, not a law of nature. Rescaling an operator changes its OPE coefficients.

## What counts as data?

A practical list of local CFT data contains:

| Datum | Meaning |
|---|---|
| $\mathbf 1$ | The identity operator, with $\Delta=0$. |
| $\mathcal O_i$ | A basis of primary local operators. |
| $\Delta_i$ | Scaling dimension of $\mathcal O_i$. |
| $\rho_i$ | Spin representation under rotations or the Lorentz group. |
| $R_i$ | Representation under global symmetries, when present. |
| $\lambda_{ijk}^{(a)}$ | OPE coefficients, including tensor-structure label $a$ when needed. |
| $C_T$ | Stress-tensor two-point normalization. |
| $C_J$ | Conserved-current two-point normalization for a chosen current normalization. |
| central charges | Special anomaly or Virasoro data, depending on dimension and context. |
| selection rules | Which OPE coefficients vanish by symmetry, spin, parity, charge, or other constraints. |

The minimal scalar shorthand

$$
\{\Delta_i,\lambda_{ijk}\}
$$

is useful but incomplete. It suppresses spin, tensor structures, global symmetry, degeneracies, conserved currents, stress tensors, defects, and anomalies.

For many bootstrap problems, the input is a deliberately small slice of the full data. For example, the identical-scalar bootstrap may use the four-point function of one scalar $\phi$ and constrain the operators appearing in $\phi\times\phi$. That is not the whole CFT; it is a projection of the CFT data onto one OPE channel.

## Primaries, descendants, and why only primaries are listed

In a conformal theory, local operators organize into conformal multiplets. A primary operator $\mathcal O$ is annihilated by special conformal transformations at the origin:

$$
[K_\mu,\mathcal O(0)]=0.
$$

Descendants are obtained by acting with translations:

$$
P_{\mu_1}\cdots P_{\mu_n}\mathcal O(0)
\quad\leftrightarrow\quad
\partial_{\mu_1}\cdots\partial_{\mu_n}\mathcal O(0).
$$

The full local operator spectrum includes primaries and descendants. But once the primary data is known, the descendant contributions are fixed by conformal symmetry. This is why CFT data is normally listed in terms of primary operators.

For example, when a primary $\mathcal O_k$ appears in the OPE of $\mathcal O_i$ and $\mathcal O_j$, the full OPE also contains derivatives of $\mathcal O_k$:

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}
\left[
\mathcal O_k(0)
+
a_1 x^\mu\partial_\mu\mathcal O_k(0)
+\cdots
\right],
$$

where the coefficients of the descendants are fixed by conformal symmetry in terms of the dimensions and spins. The only new dynamical number is $\lambda_{ijk}$, together with tensor-structure labels when present.

This is the origin of conformal blocks. A conformal block is the total contribution of one primary and all of its descendants to a four-point function.

## Identity, stress tensor, and currents

Some operators are present or constrained in every ordinary local CFT.

The identity operator $\mathbf 1$ appears in the OPE of any operator with its conjugate. In an orthonormal scalar basis,

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{\delta_{ij}}{|x|^{2\Delta_i}}\mathbf 1.
$$

A local CFT with spacetime symmetry has a stress tensor $T_{\mu\nu}$. It is conserved,

$$
\partial^\mu T_{\mu\nu}=0,
$$

and at a conformal fixed point it can be chosen traceless at separated points in flat space:

$$
T^\mu{}_{\mu}=0.
$$

The stress tensor is a spin-two primary in dimensions $d>2$ with protected dimension

$$
\Delta_T=d.
$$

Its two-point function is normalized by $C_T$. Ward identities relate OPE coefficients involving $T_{\mu\nu}$ to the dimensions and spin of the operators it acts on. Thus not every coefficient involving the stress tensor is independent.

If the CFT has a continuous global symmetry, it has a conserved current $J_\mu^a$ with protected dimension

$$
\Delta_J=d-1.
$$

The current OPE encodes charges and current-algebra data. Its normalization is meaningful only after the charge normalization is fixed.

In two dimensions, the stress tensor splits into holomorphic and antiholomorphic components, and the central charge $c$ becomes one of the defining pieces of CFT data:

$$
T(z)T(0)
\sim
\frac{c/2}{z^4}
+\frac{2T(0)}{z^2}
+\frac{\partial T(0)}{z}
+\cdots.
$$

This is the first place where the two-dimensional story becomes richer than the finite-dimensional global conformal story.

## OPE coefficients and normalization dependence

OPE coefficients are basis-dependent. If a scalar primary is rescaled,

$$
\mathcal O_i\mapsto a_i\mathcal O_i,
$$

then its two-point function rescales by $a_i^2$, and the three-point coefficient rescales by

$$
\lambda_{ijk}\mapsto a_i a_j a_k\,\lambda_{ijk}.
$$

After imposing orthonormal two-point functions, the remaining sign choices for real scalar operators still matter. If

$$
\mathcal O_i\mapsto -\mathcal O_i,
$$

then every OPE coefficient containing one copy of $\mathcal O_i$ changes sign. Products such as $\lambda_{\phi\phi\mathcal O}^2$ are invariant under this sign flip.

This is why many identical-scalar bootstrap equations involve squared OPE coefficients. In a unitary theory, for identical real scalars,

$$
\lambda_{\phi\phi\mathcal O}^2\geq 0
$$

in a basis where two-point functions have positive norm.

For spinning operators, OPE coefficients also depend on the chosen tensor-structure basis. A statement like “the OPE coefficient of two vectors and a spin-two operator” is incomplete until the tensor structures have been specified.

## Conformal data reconstructs correlators

The OPE is not merely an asymptotic mnemonic. In a unitary Euclidean CFT, it converges inside correlation functions in an appropriate radial domain. This is the deep reason conformal data is enough.

For a scalar four-point function, apply the OPE to points $x_1$ and $x_2$:

$$
\mathcal O_i(x_1)\mathcal O_j(x_2)
\sim
\sum_{\mathcal O}
\lambda_{ij\mathcal O}
\left(\mathcal O+\text{descendants}\right).
$$

Then

$$
\langle
\mathcal O_i(x_1)\mathcal O_j(x_2)
\mathcal O_k(x_3)\mathcal O_l(x_4)
\rangle
=
\sum_{\mathcal O}
\lambda_{ij\mathcal O}\lambda_{kl\mathcal O}
G_{\mathcal O}(u,v),
$$

where $G_{\mathcal O}(u,v)$ is the conformal block for the exchanged primary $\mathcal O$, with spin and external dimensions suppressed. The cross-ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The block is kinematic. The dimensions, spins, and OPE coefficients are dynamical. Thus the four-point function is reconstructed from CFT data.

Higher-point functions can be reconstructed by repeated OPEs. Consistency requires that different ways of applying the OPE give the same answer.

## Crossing and associativity

The OPE can be applied in different channels. For a four-point function of identical scalars $\phi$, one may pair $(12)(34)$ or $(14)(23)$. Consistency requires equality of the resulting decompositions.

A standard schematic crossing equation is

$$
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v)
=
\left(\frac{u}{v}\right)^{\Delta_\phi}
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(v,u).
$$

This equation is associativity of the operator algebra in analytic clothing. In two-dimensional rational CFT, this idea becomes a highly structured algebraic system involving fusion, braiding, modular data, and chiral blocks. In higher-dimensional numerical bootstrap, it becomes a convex optimization problem after imposing positivity and truncating the space of derivatives.

Crossing is the reason conformal data is constrained rather than arbitrary. A random list of dimensions and OPE coefficients will almost never satisfy crossing.

## Global symmetries and selection rules

If the CFT has a global symmetry group $G$, local operators transform in representations of $G$. The OPE must respect representation theory:

$$
R_i\otimes R_j
\supset R_k
$$

for $\lambda_{ijk}$ to be nonzero.

For a $\mathbb Z_2$ symmetry, operators are even or odd. In an Ising-like CFT,

$$
\sigma \text{ is odd},
\qquad
\epsilon \text{ is even}.
$$

The OPE obeys

$$
\sigma\times\sigma=\text{even operators},
\qquad
\sigma\times\epsilon=\text{odd operators},
\qquad
\epsilon\times\epsilon=\text{even operators}.
$$

For a continuous group such as $O(N)$, the OPE decomposes into singlet, symmetric traceless, antisymmetric, and other representation sectors depending on the external operators. Bootstrap equations are then vector equations, one component for each tensor structure or representation channel.

Selection rules can also come from parity, charge conjugation, time reversal, supersymmetry, higher-form symmetries, gauge-invariant operator constraints, or topological defect fusion rules.

## What about a Lagrangian?

A Lagrangian is one way to produce or approximate CFT data. It is not the definition of the data.

For a weakly coupled fixed point, perturbation theory may compute dimensions and OPE coefficients. For the Wilson–Fisher fixed point, the epsilon expansion gives CFT data order by order in $\epsilon$. For large-$N$ vector models, the $1/N$ expansion does something similar. For supersymmetric CFTs, protected data may be obtained from representation theory, anomalies, indices, localization, or chiral algebras.

But many CFTs are known or conjectured without a simple Lagrangian. The bootstrap viewpoint treats their data directly. One does not ask first, “What is the action?” One asks, “What spectra and OPE coefficients can consistently exist?”

This change of emphasis is a feature, not a bug. It is what lets the conformal bootstrap constrain strongly coupled theories that are otherwise hard to define.

## Examples

### Generalized free scalar

A generalized free scalar $\phi$ is defined by Wick-like correlators with arbitrary scaling dimension $\Delta_\phi$, subject to unitarity constraints. Its two-point function is

$$
\langle \phi(x)\phi(0)\rangle=\frac1{|x|^{2\Delta_\phi}}.
$$

The four-point function is a sum of disconnected pairings. The OPE contains double-trace-like operators schematically of the form

$$
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi,
$$

with approximate dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

This example is useful because it shows that conformal symmetry and crossing can be satisfied without a conventional finite-particle interpretation. It is also the zeroth-order language of many large-$N$ CFTs.

### Two-dimensional Ising CFT

The critical two-dimensional Ising CFT has three primary operators in its simplest Virasoro minimal-model description:

$$
\mathbf 1,\qquad
\sigma,\qquad
\epsilon,
$$

with dimensions

$$
\Delta_{\mathbf 1}=0,
\qquad
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1.
$$

Its fusion rules are

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
\qquad
\sigma\times\epsilon=\sigma,
\qquad
\epsilon\times\epsilon=\mathbf 1.
$$

This is an unusually compact example because Virasoro symmetry is extremely powerful. Higher-dimensional CFTs generally have infinitely many primary operators even in a single OPE channel.

### Three-dimensional Ising CFT

The three-dimensional Ising CFT has no known exact closed-form solution. Its low-lying data includes a $\mathbb Z_2$-odd scalar $\sigma$, a $\mathbb Z_2$-even scalar $\epsilon$, the stress tensor $T_{\mu\nu}$, and infinitely many other operators.

The modern numerical bootstrap constrains this data with high precision by imposing crossing, unitarity, and assumptions about gaps in selected sectors. The result is not just a pair of critical exponents but a growing map of operator dimensions, OPE coefficients, and current or stress-tensor normalizations.

This example is the canonical reminder that CFT data is a nonperturbative object. It can be sharply constrained even when no exact solution is known.

## Common pitfalls

**Mistake 1: “CFT data means only critical exponents.”** Critical exponents are derived from a few operator dimensions. Full CFT data also includes spin, global-symmetry representations, OPE coefficients, current and stress-tensor normalizations, and consistency relations.

**Mistake 2: “The OPE coefficient is absolute.”** It depends on operator normalization and tensor-structure conventions. Always state the two-point normalization.

**Mistake 3: “Descendants are additional independent data.”** Descendants are part of the operator spectrum, but their OPE contributions are fixed by conformal symmetry once primary data is known.

**Mistake 4: “All operators in a Lagrangian are primaries.”** Operators can mix, differ by equations of motion, be descendants, or require renormalization. The CFT primary basis is a fixed-point basis, not a naive list of bare monomials.

**Mistake 5: “Crossing is one equation.”** Crossing is an infinite family of functional constraints, often decomposed into spin, representation, parity, tensor-structure, and channel equations.

**Mistake 6: “A bootstrap bound is automatically a full solution.”** A bound constrains possible data. A solution requires enough information to reconstruct consistent correlators, and ideally all correlators. Islands and extremal spectra can be extraordinarily informative, but their assumptions must be stated.

## Relations to other pages

This page completes the opening triangle of the chapter: [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/), [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/), and Conformal Data.

The detailed operator theory appears in [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

Correlation-function consequences appear in [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), and [Spinning Correlators](/cft-bootstrap/correlation-functions/spinning-correlators/).

The OPE is developed in [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), and [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/). The decomposition into conformal blocks begins in [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) and [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/). The constraints on data become explicit in [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/).

## Research status

The basic statement that local CFT correlators are determined by primary spectra and OPE coefficients is established. It is the backbone of both two-dimensional exact CFT and higher-dimensional bootstrap.

What remains open is classification. In two dimensions, rational CFTs, minimal models, WZW models, and vertex-operator-algebra methods provide powerful classification tools in special families. In higher dimensions, the landscape is much less completely charted. Numerical bootstrap, analytic bootstrap, supersymmetry, large-$N$ methods, perturbation theory, lattice simulations, and holography provide complementary windows.

A recurring research theme is to identify small, physically meaningful assumptions that isolate a CFT or a small allowed region of CFT data. The most famous examples are bootstrap islands for the three-dimensional Ising and $O(N)$ universality classes. The dream is not just to bound numbers, but to understand the geometry of theory space.

## Exercises

### Exercise 1: Identity coefficient from two-point normalization

Assume real scalar primaries satisfy

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

Show that the identity contribution to the OPE must be

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{\delta_{ij}}{|x|^{2\Delta_i}}\mathbf 1.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the OPE inside the vacuum expectation value. Since

$$
\langle \mathbf 1\rangle=1
$$

and one-point functions of non-identity primaries vanish in flat space, the identity term must reproduce the two-point function. Therefore its coefficient is

$$
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

This also requires $\Delta_i=\Delta_j$ when $\delta_{ij}\neq 0$, as in an orthonormal basis.

</details>

### Exercise 2: How an OPE coefficient changes under rescaling

Let

$$
\mathcal O_i\mapsto a_i\mathcal O_i.
$$

How does the scalar three-point coefficient $\lambda_{ijk}$ change?

<details>
<summary><strong>Solution</strong></summary>

The three-point function is linear in each operator. Therefore

$$
\langle \mathcal O_i\mathcal O_j\mathcal O_k\rangle
\mapsto
a_i a_j a_k
\langle \mathcal O_i\mathcal O_j\mathcal O_k\rangle.
$$

So

$$
\lambda_{ijk}\mapsto a_i a_j a_k\,\lambda_{ijk}.
$$

This is why OPE coefficients are meaningful only after the operator normalization is fixed.

</details>

### Exercise 3: Selection rule for a Z₂ symmetry

Suppose $\sigma$ is odd and $\epsilon$ is even under a $\mathbb Z_2$ symmetry. Which parity sectors appear in $\sigma\times\sigma$, $\sigma\times\epsilon$, and $\epsilon\times\epsilon$?

<details>
<summary><strong>Solution</strong></summary>

The product parity is the product of the parities:

$$
(-)\times(-)=+,
\qquad
(-)\times(+)=-,
\qquad
(+)\times(+)=+.
$$

Therefore

$$
\sigma\times\sigma
\quad\text{contains only even operators},
$$

$$
\sigma\times\epsilon
\quad\text{contains only odd operators},
$$

and

$$
\epsilon\times\epsilon
\quad\text{contains only even operators}.
$$

</details>

### Exercise 4: From exchanged primary to conformal block

Explain why one exchanged primary contributes more than one local operator term to a four-point function.

<details>
<summary><strong>Solution</strong></summary>

A primary operator comes with all of its descendants:

$$
\mathcal O,\quad
P_\mu\mathcal O,\quad
P_\mu P_\nu\mathcal O,\quad \ldots
$$

In position space these are derivatives of the primary. When $\mathcal O$ appears in an OPE, conformal symmetry fixes the coefficients of all descendant terms in terms of the primary data. The sum of the primary and all descendant contributions to the four-point function is the conformal block.

Thus one exchanged primary corresponds to one conformal multiplet, not just one local monomial.

</details>

### Exercise 5: Why crossing constrains CFT data

For identical scalars, explain in words why the same OPE coefficients appear in different channel decompositions of a four-point function.

<details>
<summary><strong>Solution</strong></summary>

The four-point function

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
$$

is a single function of the insertion points. We may compute it by applying the OPE to the pair $(12)$ and the pair $(34)$, or instead to $(14)$ and $(23)$. Both are just different expansions of the same correlation function.

Because the OPE is part of the operator algebra of the same theory, the dimensions and OPE coefficients used in one channel must be compatible with those used in the other. Equality of the two decompositions is crossing symmetry. A random spectrum and random OPE coefficients will not satisfy this equality.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for two-dimensional CFT, OPEs, conformal families, minimal models, fusion rules, and modular constraints.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Compact reference for higher-dimensional primary operators, correlators, OPE, conformal blocks, and bootstrap.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Pedagogical modern introduction to CFT data and crossing in higher dimensions.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Broad review of CFT data, conformal blocks, numerical methods, and applications.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” arXiv:2311.15844. Review of recent numerical bootstrap software, algorithms, and applications after the 2019 review.
- A. M. Polyakov, “Non-Hamiltonian Approach to Conformal Quantum Field Theory,” *Soviet Physics JETP* **39** (1974). Classic source for the conformal bootstrap idea.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” *Nuclear Physics B* **241** (1984). Foundational paper on two-dimensional conformal symmetry and minimal models.

## Version history

- **2026-06-26:** Initial polished draft explaining spectra, primary data, OPE coefficients, normalization dependence, identity/stress-tensor/current data, reconstruction of correlators, crossing, examples, pitfalls, and exercises.
