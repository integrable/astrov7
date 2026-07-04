---
title: "Identity Operator in the OPE"
description: "Explains the identity channel in the operator product expansion, its normalization, its role in factorization, and why bootstrap equations usually isolate it before imposing positivity."
sidebar:
  label: "Identity Operator"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Rychkov 2016; Simmons-Duffin 2017; Poland et al. 2019"
topics:
  - conformal field theory
  - operator product expansion
  - identity operator
  - identity block
  - cluster decomposition
  - crossing symmetry
canonicalTopics:
  - identity-operator-in-ope
  - identity-channel
  - conformal-data
  - bootstrap-equations
researchStatus:
  established:
    - "In an ordinary unitary CFT with a unique vacuum, the identity is the unique spin-zero dimension-zero local operator and is the unit of the local operator algebra."
    - "The identity contribution to the OPE is fixed by the two-point-function normalization and is not independent CFT data."
  active:
    - "In theories with topological sectors, boundaries, defects, generalized symmetries, or nonunitary features, the practical notion of a vacuum channel can require extra care."
---

## Summary

The identity operator $\mathbf 1$ is the unit of the local operator algebra. Its defining property is simple:

$$
\mathbf 1(x)\mathcal O(0)=\mathcal O(0),
\qquad
\langle \mathbf 1\,\mathcal X\rangle=\langle \mathcal X\rangle.
$$

In the OPE, the identity is the **vacuum channel**. If two operators can fuse to the vacuum, then their product contains a singular c-number term multiplying $\mathbf 1$. For scalar primaries with two-point metric $G_{ij}$,

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{G_{ij}}{|x|^{\Delta_i+\Delta_j}}\,\mathbf 1.
$$

When the two-point function is nonzero, conformal invariance forces the two dimensions to match, so this is equivalently $G_{ij}/|x|^{2\Delta_i}$. This term is fixed by the two-point function. It is not a dynamical structure constant to be fitted separately. In a unit-normalized identical-scalar bootstrap problem, the identity block is the term $1$ in the four-point function.

The identity channel is often the least glamorous part of the OPE. It is also the part that prevents many mistakes. It controls disconnected contributions, leading short-distance singularities, cluster decomposition, and the inhomogeneous term in the bootstrap equation.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Two nearby operators are replaced by the identity channel in an OPE.](/figures/cft-bootstrap/identity-operator-ope.svg)

<figcaption>

The identity channel is the part of the OPE in which a nearby pair of operators fuses to the vacuum. Inside any larger correlator, this contribution leaves the other insertions untouched and multiplies them by the two-point singularity.

</figcaption>
</figure>

## Prerequisites

You should know the basic OPE statement from [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), the role of OPE coefficients from [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), and the interpretation of the OPE as a convergent radial-quantization expansion from [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/). It also helps to know [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/) and [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/).

## Core idea

The OPE is a multiplication law for local operators,

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_k C_{ij}^{\ \ k}(x,\partial)\mathcal O_k(0).
$$

The identity operator is the operator $\mathcal O_k=\mathbf 1$. Since $\mathbf 1$ has scaling dimension zero, spin zero, and no internal charge, its coefficient can appear only when the product $\mathcal O_i\mathcal O_j$ contains the trivial representation of every symmetry.

If it appears, the identity term is determined by the two-point function because all non-identity one-point functions vanish in flat space:

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
C_{ij}^{\ \ \mathbf 1}(x)\langle \mathbf 1\rangle.
$$

Thus the identity coefficient is not a new entry in the list of CFT data. It is part of the normalization convention for the operator basis.

:::note[The identity is universal, not optional]
A CFT with local operators has an identity operator. What can vanish is the **identity channel** in a particular OPE, because charges, spin, or representation theory may forbid the product from fusing to the vacuum.
:::

## Setup and conventions

We work in Euclidean flat space unless stated otherwise. Local scalar primaries are denoted by $\mathcal O_i$, with scaling dimensions $\Delta_i$. Their two-point functions are written

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{G_{ij}\,\delta_{\Delta_i\Delta_j}}{|x|^{2\Delta_i}},
$$

where $G_{ij}$ is the two-point metric on the space of scalar primaries with the same quantum numbers. In a real orthonormal basis, $G_{ij}=\delta_{ij}$.

For spinning operators, the same idea holds, but the identity coefficient must multiply the correct two-point tensor structure. For a symmetric traceless spin-$\ell$ primary $\mathcal O_{\mu_1\cdots\mu_\ell}$, the identity term in $\mathcal O(x)\mathcal O(0)$ reproduces the full spin-$\ell$ two-point tensor structure, not just a scalar power law.

The vacuum expectation value is normalized as

$$
\langle \mathbf 1\rangle=1.
$$

## The identity as the unit operator

The identity operator has two related meanings.

First, it is the unit for operator multiplication:

$$
\mathbf 1\times \mathcal O_i=\mathcal O_i.
$$

Second, under the state–operator correspondence it is the vacuum state:

$$
\mathbf 1(0)|0\rangle=|0\rangle.
$$

In a unitary CFT on the cylinder $\mathbb R_\tau\times S^{d-1}$, the dilatation generator is the Hamiltonian. The identity state has energy zero. For a scalar primary, the unitarity bound says $\Delta\ge 0$, and a scalar with $\Delta=0$ has a null derivative descendant. In an irreducible theory with a unique vacuum, this means that the only dimension-zero scalar local operator is $\mathbf 1$.

This is the cleanest setting used in most bootstrap applications. If a theory decomposes into superselection sectors, or if topological local operators are present, then the algebra can contain additional dimension-zero projectors. In that case one should first decompose the theory into sectors before using the phrase “the identity channel” too casually.

## Extracting the identity coefficient

Take the OPE of two scalar primaries inside their two-point function:

$$
\mathcal O_i(x)\mathcal O_j(0)
=
C_{ij}^{\ \ \mathbf 1}(x)\mathbf 1
+
\sum_{k\ne \mathbf 1}C_{ij}^{\ \ k}(x,\partial)\mathcal O_k(0).
$$

Taking the vacuum expectation value gives

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
C_{ij}^{\ \ \mathbf 1}(x),
$$

because flat-space one-point functions of non-identity primaries vanish. Therefore

$$
C_{ij}^{\ \ \mathbf 1}(x)
=
\frac{G_{ij}\,\delta_{\Delta_i\Delta_j}}{|x|^{2\Delta_i}}.
$$

Equivalently, if one writes the scalar-primary part of the OPE as

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_k \lambda_{ijk}\,|x|^{\Delta_k-\Delta_i-\Delta_j}
\bigl(\mathcal O_k(0)+\text{descendants}\bigr),
$$

then the identity has $\Delta_k=0$ and

$$
\lambda_{ij\mathbf 1}=G_{ij}
$$

in the same two-point normalization. If the operators are unit-normalized and real,

$$
\lambda_{ij\mathbf 1}=\delta_{ij}.
$$

This is why the identity coefficient is usually not listed as independent CFT data.

## Selection rules for the identity channel

The identity is a singlet under spacetime rotations and all internal symmetries. Therefore it appears only if the product of the two operators contains a singlet.

Examples:

| Product | Identity channel? | Reason |
|---|---|---|
| $\phi\times\phi$ for a real unit-normalized scalar | yes | The product is neutral and spinless. |
| $\mathcal O_q\times\mathcal O_q$ for charge $q\ne0$ | usually no | The product has charge $2q$. |
| $\mathcal O_q^\dagger\times\mathcal O_q$ | yes if unit-normalized | The product is neutral. |
| $J_\mu^a\times J_\nu^b$ | yes in the $\delta^{ab}$ channel | The currents can fuse to the singlet. |
| $\phi_i\times\phi_j$ in an $O(N)$ vector CFT | yes in the trace channel | $\mathbf N\otimes\mathbf N$ contains a singlet. |

For an $O(N)$ vector primary $\phi_i$, one often writes

$$
\phi_i(x)\phi_j(0)
\supset
\frac{\delta_{ij}}{|x|^{2\Delta_\phi}}\mathbf 1.
$$

The identity is not in the symmetric traceless channel or the antisymmetric channel. It is in the singlet channel only.

## Identity channel inside a larger correlator

The OPE is a statement inside correlation functions. If $|x|$ is much smaller than the distance from $0$ to all other insertions, then

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\mathcal X\rangle
=
\frac{G_{ij}}{|x|^{\Delta_i+\Delta_j}}\langle \mathcal X\rangle
+
\text{non-identity contributions},
$$

provided the identity is allowed. Here $\mathcal X$ denotes a product of other operators placed outside the OPE convergence sphere.

This formula is the local version of factorization. When two operators annihilate into the vacuum, the remaining insertions do not know the detailed identity of the small pair; they only see the coefficient multiplying $\mathbf 1$.

For a four-point function of a unit-normalized identical scalar $\phi$,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\,g(u,v),
$$

where $u$ and $v$ are the standard cross-ratios. The identity contribution in the $12\to34$ channel is

$$
g(u,v)
=
1+\sum_{\mathcal O\ne \mathbf 1}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v).
$$

The $1$ is the identity block.

## Identity block and crossing

Crossing symmetry says that the same four-point function can be expanded in different OPE channels. For identical scalars,

$$
v^{\Delta_\phi}g(u,v)=u^{\Delta_\phi}g(v,u).
$$

Separating the identity in each channel gives the standard bootstrap form

$$
v^{\Delta_\phi}-u^{\Delta_\phi}
+
\sum_{\mathcal O\ne\mathbf 1}\lambda_{\phi\phi\mathcal O}^2
\left[
 v^{\Delta_\phi}G_{\Delta,\ell}(u,v)
-u^{\Delta_\phi}G_{\Delta,\ell}(v,u)
\right]
=
0.
$$

This equation is inhomogeneous because the identity is present. Numerically, this is crucial. The identity term is the fixed vector that the positive sum of non-identity conformal blocks must cancel.

A common slogan is:

$$
\text{crossing} = \text{identity mismatch} + \text{non-identity compensation}.
$$

That sounds almost too cute, but it is a useful mental model. Bootstrap bounds are possible because unitarity makes the non-identity coefficients nonnegative in reflection-positive channels, while the identity contribution is fixed.

## Example: free scalar field

Let $\varphi$ be a canonically normalized free scalar in $d>2$ Euclidean dimensions with

$$
\langle \varphi(x)\varphi(0)\rangle
=
\frac{1}{|x|^{d-2}}.
$$

Then Wick's theorem gives, schematically,

$$
\varphi(x)\varphi(0)
=
\frac{1}{|x|^{d-2}}\mathbf 1
+
:\!\varphi^2\!:(0)
+
x^\mu:\!\partial_\mu\varphi\,\varphi\!:(0)
+
\cdots.
$$

The first term is the identity contribution. The rest of the expansion records local operators built from the normal-ordered product and its descendants.

For the four-point function,

$$
\langle \varphi_1\varphi_2\varphi_3\varphi_4\rangle
=
\langle \varphi_1\varphi_2\rangle\langle \varphi_3\varphi_4\rangle
+
\langle \varphi_1\varphi_3\rangle\langle \varphi_2\varphi_4\rangle
+
\langle \varphi_1\varphi_4\rangle\langle \varphi_2\varphi_3\rangle.
$$

The first term is the identity contribution in the $12\to34$ channel. The other two terms are not “mistakes”; they are the same correlator viewed through other pairings and other OPE channels.

## Connected correlators subtract the identity channel

In many QFT computations one studies connected correlators. For a four-point function,

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle_{\mathrm{conn}}
=
\langle \phi_1\phi_2\phi_3\phi_4\rangle
-
\langle \phi_1\phi_2\rangle\langle \phi_3\phi_4\rangle
-
\text{two more pairings}.
$$

This subtraction removes disconnected identity exchanges. It does **not** remove the identity operator from the theory, and it does not mean the OPE lacks an identity term. It means the connected correlator has been engineered to vanish when the insertions factorize into disconnected vacuum pieces.

In bootstrap equations one usually works with the full correlator, isolates the identity block explicitly, and then imposes positivity on the remaining operator sum.

## Identity, vacuum, and cluster decomposition

The identity operator is the local operator corresponding to the vacuum state. Cluster decomposition says that widely separated neutral operator groups factorize:

$$
\langle A(x)B(0)\rangle
\longrightarrow
\langle A\rangle\langle B\rangle
\qquad |x|\to\infty.
$$

In radial quantization, this happens because the identity state is the lowest-energy state propagating through a long cylinder. The next corrections come from the lowest-dimension non-identity operators with the right quantum numbers.

This is the large-distance cousin of the short-distance identity channel. In both cases, the vacuum is the simplest intermediate state.

## Common pitfalls

**Forgetting symmetry selection rules.** Charged operators do not usually fuse to the identity unless their charges cancel.

**Treating the identity coefficient as independent data.** Once the two-point normalization is chosen, $\lambda_{ij\mathbf 1}$ is fixed.

**Removing the identity twice.** If you work with connected correlators, identity pieces may already be subtracted. If you then use a bootstrap equation that has also isolated the identity, check what object is actually being expanded.

**Calling every leading operator the identity.** If the identity channel is forbidden, the leading OPE term is the lowest-dimension non-identity operator allowed by the symmetries.

**Confusing the identity operator with the stress tensor.** Both are universal in local CFTs, but they play different roles. The identity is the unit and has $\Delta=0$. The stress tensor is a conserved spin-two primary with $\Delta=d$ and controls spacetime Ward identities.

## Relations to other pages

- [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) introduces the local replacement idea.
- [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) explains why the identity contribution is the first term in a radial-quantization expansion when it is allowed.
- [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) explains how two-point normalization affects all structure constants.
- [Associativity of OPE](/cft-bootstrap/operator-product-expansion/associativity-of-ope/) shows how identity terms become the fixed inhomogeneous part of crossing equations.
- [Stress Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) treats the next universal singlet operator after the identity in many scalar OPEs.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) later explains why the identity block is simply $1$ in the standard scalar-block normalization.

## Research status

For ordinary unitary CFTs on flat space, the identity channel is completely standard. Its role in OPE convergence, conformal blocks, crossing, and numerical bootstrap equations is settled.

There are subtleties in less ordinary settings. Boundary CFTs have boundary identity operators and bulk-to-boundary identity channels. Defect CFTs have defect identity channels. Topological local operators can behave like projectors onto superselection sectors. Nonunitary theories can violate some Hilbert-space intuitions even when an algebraic identity still exists. These refinements matter, but they are refinements of the same basic idea: the vacuum channel must be separated before the dynamical spectrum is analyzed.

## Exercises

### Exercise 1: Identity coefficient from the two-point function

Let scalar primaries satisfy

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{G_{ij}}{|x|^{2\Delta_i}}\delta_{\Delta_i\Delta_j}.
$$

Use the OPE to determine $C_{ij}^{\ \ \mathbf 1}(x)$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\mathcal O_i(x)\mathcal O_j(0)
=
C_{ij}^{\ \ \mathbf 1}(x)\mathbf 1+\text{non-identity operators}.
$$

Taking the vacuum expectation value kills all non-identity primaries in flat space and leaves $\langle\mathbf 1\rangle=1$. Therefore

$$
C_{ij}^{\ \ \mathbf 1}(x)
=
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{G_{ij}}{|x|^{2\Delta_i}}\delta_{\Delta_i\Delta_j}.
$$

</details>

### Exercise 2: Identity block in the identical-scalar four-point function

For a unit-normalized scalar $\phi$, write

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}g(u,v).
$$

Show that the identity contribution in the $12\to34$ OPE is $g(u,v)\supset 1$.

<details><summary><strong>Solution</strong></summary>

The identity term in the $12$ OPE is

$$
\phi(x_1)\phi(x_2)\supset \frac{1}{x_{12}^{2\Delta_\phi}}\mathbf 1.
$$

Similarly, the remaining two-point function is

$$
\langle \phi(x_3)\phi(x_4)\rangle
=
\frac{1}{x_{34}^{2\Delta_\phi}}.
$$

Thus the identity-channel contribution is

$$
\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}.
$$

Comparing with the definition of $g(u,v)$ gives $g(u,v)\supset 1$.

</details>

### Exercise 3: Charged operators

Let $\mathcal O_q$ have charge $q$ under a $U(1)$ global symmetry. Which OPE can contain the identity: $\mathcal O_q\times\mathcal O_q$ or $\mathcal O_q^\dagger\times\mathcal O_q$?

<details><summary><strong>Solution</strong></summary>

The identity has charge zero. The product $\mathcal O_q\times\mathcal O_q$ has charge $2q$, so it cannot contain the identity unless $2q=0$ in the charge group. The product $\mathcal O_q^\dagger\times\mathcal O_q$ has charge $-q+q=0$, so the identity channel is allowed. If the operators are unit-normalized,

$$
\mathcal O_q^\dagger(x)\mathcal O_q(0)
\supset
\frac{1}{|x|^{2\Delta_q}}\mathbf 1.
$$

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982.
- D. Poland, S. Rychkov, and A. Vichi, “The conformal bootstrap: theory, numerical techniques, and applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405.
- M. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE convergence in conformal field theory,” *Physical Review D* **86** (2012), arXiv:1208.6449.

## Version history

- 2026-06-27: First polished draft. Introduced the identity channel, identity coefficient, identity block, selection rules, connected-correlator caveats, and bootstrap role.
