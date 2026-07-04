---
title: "State–Operator Correspondence"
description: "Explains how local operator insertions create states on spheres in radial quantization and why this correspondence underlies spectra, inner products, OPE convergence, and bootstrap positivity."
sidebar:
  label: "State–Operator Correspondence"
  order: 5
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019; Pappadopulo et al. 2012"
topics:
  - state-operator correspondence
  - radial quantization
  - local operators
  - Hilbert space on spheres
  - reflection positivity
  - operator product expansion
canonicalTopics:
  - state-operator-correspondence
  - radial-quantization
  - local-operator-spectrum
  - hilbert-space-on-spheres
  - ope-convergence
researchStatus:
  established:
    - 'In Euclidean radial quantization, a local operator inserted at the origin creates a state on $S^{d-1}$, and every finite-energy local state is represented by a local operator.'
    - 'The state–operator correspondence turns two-point functions into inner products and the OPE into a Hilbert-space completeness expansion.'
  active:
    - "The basic correspondence is standard; active refinements concern defects, boundaries, nonunitary theories, continuous spectra, Lorentzian reconstruction, and algebraic formulations of local operator spaces."
---

## Summary

The state–operator correspondence is the statement that a local operator in a CFT is equivalent to a state on a sphere surrounding the insertion. In radial quantization, the basic map is

$$
\mathcal O(0)
\quad\longmapsto\quad
|\mathcal O\rangle=\mathcal O(0)|0\rangle
\in\mathcal H(S^{d-1}).
$$

The inverse direction is equally important: a finite-energy state on $S^{d-1}$ can be represented by a local operator at the origin. Thus the CFT local-operator spectrum is a Hilbert-space spectrum in disguise.

For an operator of scaling dimension $\Delta$,

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
$$

so the scaling dimension is the energy of the corresponding state on the cylinder $\mathbb R\times S^{d-1}$. Descendants are ordinary excited states in the same conformal multiplet:

$$
P_{\mu_1}\cdots P_{\mu_n}|\mathcal O\rangle
\quad\longleftrightarrow\quad
\partial_{\mu_1}\cdots\partial_{\mu_n}\mathcal O(0).
$$

<figure class="doc-figure" style="--figure-width: 43rem;">

![A local insertion at the origin prepares a ket on the surrounding sphere; an insertion at infinity prepares the dual bra.](/figures/cft-bootstrap/state-operator-correspondence.svg)

<figcaption>

The inside of a sphere prepares a ket, the outside prepares a bra, and the full correlation function is their inner product. Under the cylinder map, the origin is the far past and infinity is the far future.

</figcaption>
</figure>

This page explains why the correspondence is true, how bra states and inner products are computed, and why the correspondence is the hidden Hilbert-space engine behind unitarity bounds, the OPE, conformal blocks, and bootstrap positivity.

:::note[The slogan]
A local operator is a state on the sphere. A correlation function is an amplitude between states prepared by path integrals.
:::

## Prerequisites

You should know the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/), the chapter overview [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/), and the construction in [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/). The pages [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/) explain the quantum numbers carried by the corresponding states.

This page uses Euclidean signature unless stated otherwise. Lorentzian continuation is essential for causality and real-time physics, but the state–operator correspondence is most transparent in Euclidean radial quantization.

## Core idea

In ordinary canonical quantization, a path integral over a region of spacetime prepares a state on the boundary of that region. Radial quantization uses the same principle with spherical boundaries.

Take a ball $B_R$ of radius $R$ centered at the origin. The path integral over $B_R$ prepares a ket in the Hilbert space on the boundary sphere $S_R^{d-1}$. With no insertion, it prepares the vacuum. With a local operator inserted at the origin, it prepares

$$
|\mathcal O;R\rangle.
$$

Changing $R$ is Euclidean time evolution in the radial time coordinate

$$
\tau=\log r.
$$

After transporting the state to the unit sphere, we write

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

The inverse statement follows from locality and scale invariance. If a state is prepared on a tiny sphere around the origin, an observer outside the sphere cannot resolve the detailed interior preparation. Its effect on exterior correlation functions can be replaced by a sum of local insertions at the center. At a conformal fixed point, this expansion is organized by scaling dimensions and spin. That is the state-to-operator direction.

## Setup and conventions

Write flat Euclidean coordinates as

$$
x^\mu=r n^\mu,
\qquad
r>0,
\qquad
n\in S^{d-1},
\qquad
\tau=\log r.
$$

The cylinder Hilbert space is

$$
\mathcal H(S^{d-1}),
$$

and the radial Hamiltonian is the dilatation generator:

$$
H_{\rm cyl}=D.
$$

The vacuum is conformally invariant,

$$
D|0\rangle=0,
\qquad
P_\mu|0\rangle=0,
\qquad
K_\mu|0\rangle=0,
\qquad
M_{\mu\nu}|0\rangle=0,
$$

so the identity operator maps to the vacuum:

$$
\mathbf 1
\quad\longleftrightarrow\quad
|0\rangle.
$$

For a scalar scaling operator,

$$
[D,\mathcal O(x)]
=
\left(x^\mu\partial_\mu+\Delta\right)\mathcal O(x).
$$

At the origin this gives

$$
D\,\mathcal O(0)|0\rangle
=
\Delta\,\mathcal O(0)|0\rangle.
$$

For spinning operators, $\Delta$ is still the eigenvalue of $D$, while the spin indices transform under the rotation group $SO(d)$ on the sphere.

## Operators to states

The operator-to-state map is direct:

$$
\mathcal O(0)\mapsto |\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

A primary operator creates a primary state. At the origin the primary condition is

$$
[K_\mu,\mathcal O(0)]=0,
$$

or equivalently

$$
K_\mu|\mathcal O\rangle=0.
$$

Descendants are obtained by acting with translations:

$$
[P_\mu,\mathcal O(0)]=\partial_\mu\mathcal O(0).
$$

Thus

$$
P_\mu|\mathcal O\rangle
=
\partial_\mu\mathcal O(0)|0\rangle.
$$

Repeated actions of $P_\mu$ create higher-level descendants.

A displaced insertion creates a superposition of descendants. Translation invariance gives

$$
\mathcal O(x)|0\rangle
=
e^{x\cdot P}\mathcal O(0)|0\rangle,
$$

so

$$
\mathcal O(x)|0\rangle
=
\sum_{n=0}^{\infty}
\frac{x^{\mu_1}\cdots x^{\mu_n}}{n!}
P_{\mu_1}\cdots P_{\mu_n}
|\mathcal O\rangle.
$$

This is why Taylor expansion in position becomes descendant expansion in radial quantization.

## States to operators

Now start with a state $|\Psi\rangle$ on a small sphere $S_\epsilon^{d-1}$. Ask how it affects all correlation functions outside the sphere. Locality says that the entire interior can be replaced by local data at the origin. In a CFT, these local data can be expanded in scaling operators:

$$
|\Psi\rangle
=
\sum_A c_A|\mathcal O_A\rangle.
$$

Here $A$ runs over a basis of local operators, including primaries and descendants. The coefficients depend on the state and on normalization conventions.

This is a completeness statement. It is not saying that a generic state is represented by a single operator. A generic state is a superposition of local-operator states. Energy eigenstates correspond to operators with definite scaling dimension. Primary energy eigenstates are the lowest-weight states in conformal multiplets.

## Bra states and insertion at infinity

The ket is created by an insertion at the origin. The corresponding bra is created by the conjugate insertion at infinity.

For a scalar primary, define

$$
\langle\mathcal O|
=
\lim_{x\to\infty}|x|^{2\Delta}
\langle 0|\mathcal O(x).
$$

The factor $|x|^{2\Delta}$ removes the decay of the two-point function. With the standard scalar normalization

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{G_{ij}}{|x|^{2\Delta_i}}
\qquad
\text{when }\Delta_i=\Delta_j,
$$

the inner product is

$$
\langle \mathcal O_i|\mathcal O_j\rangle=G_{ij}.
$$

For spinning primaries, the definition of the bra also contains the appropriate inversion tensor acting on indices. This is developed in [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/).

The inner product is therefore a two-point function. In a unitary CFT, reflection positivity implies that this Gram matrix is positive semidefinite. After quotienting null states, it is positive definite.

## Two-point functions as norms

Suppose a scalar primary is normalized as

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
=
\frac{1}{|x|^{2\Delta}}.
$$

Then

$$
\langle\mathcal O|\mathcal O\rangle
=
\lim_{x\to\infty}|x|^{2\Delta}
\langle\mathcal O(x)\mathcal O(0)\rangle
=
1.
$$

Descendant norms are also fixed by correlation functions and the conformal algebra. For a scalar primary,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Using $K_\mu|\mathcal O\rangle=0$ and

$$
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}
$$

in Euclidean conventions, the scalar spin term vanishes and

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=
2\Delta\,\delta_{\mu\nu}
\langle\mathcal O|\mathcal O\rangle.
$$

Positivity begins to constrain $\Delta$ already at level one, and sharper constraints arise from higher descendants and spinning representations. This is the representation-theoretic origin of unitarity bounds.

## The OPE as completeness

The state–operator correspondence turns the OPE into an ordinary Hilbert-space expansion.

Consider two local operators inside a sphere centered at the origin. They create a state:

$$
\mathcal O_i(x)\mathcal O_j(0)|0\rangle.
$$

Expand this state in a basis of local-operator states:

$$
\mathcal O_i(x)\mathcal O_j(0)|0\rangle
=
\sum_{k,\alpha}
c_{ij}^{k,\alpha}(x)
|\mathcal O_{k,\alpha}\rangle.
$$

Here $k$ labels primaries and $\alpha$ labels descendants in a conformal multiplet. Rewriting this state expansion as an operator statement gives the OPE:

$$
\mathcal O_i(x)\mathcal O_j(0)
=
\sum_k
\lambda_{ijk}
\,\mathcal D_k(x,\partial)
\mathcal O_k(0).
$$

The differential operator $\mathcal D_k$ packages descendant contributions fixed by conformal symmetry. The numbers $\lambda_{ijk}$ are primary OPE coefficients.

This also explains OPE convergence. The expansion converges when there exists a sphere separating the operators being fused from all other insertions. In that case one is just inserting a complete set of states on the separating sphere. The OPE is a radial-quantization spectral expansion, not merely a formal asymptotic series.

## Examples

### Identity operator

The identity operator maps to the vacuum:

$$
|\mathbf 1\rangle=\mathbf 1(0)|0\rangle=|0\rangle.
$$

Its scaling dimension and spin are

$$
\Delta_{\mathbf 1}=0,
\qquad
\ell_{\mathbf 1}=0.
$$

The identity contribution in an OPE is the vacuum component of the state prepared by nearby operators.

### Free scalar

For a free scalar in $d>2$,

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The state

$$
|\phi\rangle=\phi(0)|0\rangle
$$

is a primary state. Its descendants include

$$
P_\mu|\phi\rangle
\quad\longleftrightarrow\quad
\partial_\mu\phi(0)|0\rangle.
$$

The equation of motion

$$
\partial^2\phi=0
$$

says that the descendant $P^2|\phi\rangle$ is null. The free scalar multiplet is therefore short.

### Conserved current

A conserved current $J_\mu$ in $d$ dimensions has

$$
\Delta_J=d-1.
$$

The state $J_\mu(0)|0\rangle$ is a vector primary state. Conservation,

$$
\partial^\mu J_\mu=0,
$$

removes one descendant. Again, a conservation law is a null-state condition in radial quantization.

### Stress tensor

The stress tensor creates a spin-two state with

$$
\Delta_T=d.
$$

Conservation and tracelessness give

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_\mu=0.
$$

The stress tensor is universal because it creates the state associated with infinitesimal spacetime transformations. Its Ward identities encode conformal symmetry in correlation functions.

## Why the correspondence matters for bootstrap

The conformal bootstrap studies the consistency of local operator multiplication. The state–operator correspondence gives each piece a Hilbert-space meaning.

| CFT object | Hilbert-space meaning |
|---|---|
| primary operator $\mathcal O$ | lowest-energy state in a conformal multiplet |
| scaling dimension $\Delta$ | cylinder energy |
| spin | angular momentum on $S^{d-1}$ |
| descendant | excited state obtained by $P_\mu$ |
| two-point coefficient | inner-product convention |
| OPE coefficient $\lambda_{ijk}$ | matrix element between cylinder states |
| unitarity bound | positivity of descendant norms |
| conformal block | propagation of one conformal multiplet |

This dictionary is why bootstrap equations have positivity properties. They are spectral decompositions of Hilbert-space amplitudes.

## Common pitfalls

**The state is not a scattering state.** The state $|\mathcal O\rangle$ lives on $S^{d-1}$ in radial quantization. It is not an asymptotic particle state, and a generic CFT has no ordinary flat-space $S$-matrix.

**The state is not literally at a point.** The operator is inserted at a point, but the state lives on a surrounding sphere.

**Not every operator is primary.** Every local operator corresponds to a state. Only lowest-weight states correspond to primaries. Descendants correspond to higher-energy states in the same conformal multiplet.

**Null states must be quotiented.** Equations of motion and conservation laws can make descendants null. In a unitary theory they are removed from the physical Hilbert space.

**Spinning bras need inversion tensors.** The scalar formula for insertion at infinity is not the whole story for spin.

**Continuous spectra require care.** Many bootstrap discussions assume a discrete spectrum on the cylinder. Noncompact CFTs and some logarithmic theories may require generalized state spaces.

## Relations to other pages

The correspondence is the bridge from [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) to the [Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/). [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) develops the adjoint operation and the precise bra-state construction.

[Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) explain how the state space decomposes into representations. [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) uses descendant norms to constrain dimensions.

Later, [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) and [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) turn the Hilbert-space expansion described here into the technical engine behind conformal blocks and crossing symmetry.

## Research status

The state–operator correspondence is established in ordinary unitary local CFTs. It is one of the basic pillars of the subject and is assumed throughout most conformal bootstrap work.

The active frontier is in refinements and generalizations: boundary and defect CFTs, logarithmic CFTs, nonunitary models, noncompact theories with continuous spectra, gauge theories with subtle operator algebras, Lorentzian reconstruction, and algebraic or rigorous approaches to local operator spaces. These subtleties change the implementation, not the central lesson.

## Exercises

### Exercise 1: identity and vacuum

Show that the identity operator corresponds to the vacuum state and determine its scaling dimension.

<details><summary><strong>Solution</strong></summary>

The state created by the identity is

$$
|\mathbf 1\rangle=\mathbf 1(0)|0\rangle=|0\rangle.
$$

The vacuum is invariant under dilatations,

$$
D|0\rangle=0.
$$

Therefore

$$
D|\mathbf 1\rangle=0,
$$

so the identity has scaling dimension $\Delta_{\mathbf 1}=0$.

</details>

### Exercise 2: a displaced insertion

Let $\mathcal O$ be a scalar primary. Show that $\mathcal O(x)|0\rangle$ is a superposition of descendant states of $\mathcal O(0)|0\rangle$.

<details><summary><strong>Solution</strong></summary>

Translation invariance gives

$$
\mathcal O(x)=e^{x\cdot P}\mathcal O(0)e^{-x\cdot P}.
$$

Since $P_\mu|0\rangle=0$,

$$
\mathcal O(x)|0\rangle=e^{x\cdot P}\mathcal O(0)|0\rangle.
$$

Expanding the exponential,

$$
\mathcal O(x)|0\rangle
=
\sum_{n=0}^{\infty}
\frac{x^{\mu_1}\cdots x^{\mu_n}}{n!}
P_{\mu_1}\cdots P_{\mu_n}
|\mathcal O\rangle.
$$

All terms with $n>0$ are descendants.

</details>

### Exercise 3: norm from a two-point function

Assume

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C}{|x|^{2\Delta}}.
$$

Compute $\langle\mathcal O|\mathcal O\rangle$.

<details><summary><strong>Solution</strong></summary>

Using insertion at infinity,

$$
\langle\mathcal O|
=
\lim_{x\to\infty}|x|^{2\Delta}\langle 0|\mathcal O(x).
$$

Therefore

$$
\langle\mathcal O|\mathcal O\rangle
=
\lim_{x\to\infty}|x|^{2\Delta}
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\lim_{x\to\infty}|x|^{2\Delta}
\frac{C}{|x|^{2\Delta}}
=C.
$$

Thus the two-point normalization is the radial-quantization norm.

</details>

### Exercise 4: OPE convergence from a separating sphere

Explain why the OPE of two operators converges when a sphere separates them from all other insertions.

<details><summary><strong>Solution</strong></summary>

Choose a sphere enclosing the two operators to be fused and excluding all other insertions. The two interior operators prepare a state on that sphere. By completeness, the state can be expanded in cylinder energy eigenstates, equivalently local-operator states at the center.

A state of dimension $\Delta$ propagating from radius $r_{\rm in}$ to radius $r_{\rm out}$ contributes

$$
\left(\frac{r_{\rm in}}{r_{\rm out}}\right)^\Delta.
$$

When the ratio is smaller than one, high-dimension states are suppressed. This is the Hilbert-space reason for OPE convergence in a fixed radial channel.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. See Chapter 6 for radial quantization, the operator formalism, Hermitian conjugation, field-state equivalence, and conformal families.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2017. A modern higher-dimensional introduction to radial quantization, state–operator correspondence, primaries, descendants, and unitarity.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Useful for the Hilbert-space logic behind radial quantization, reflection positivity, and bootstrap positivity.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91**, 015002 (2019), arXiv:1805.04405. See the review of radial quantization, OPE, conformal blocks, and crossing.
- D. Pappadopulo, S. Rychkov, J. Espin, and R. Rattazzi, “OPE Convergence in Conformal Field Theory,” *Physical Review D* **86**, 105043 (2012), arXiv:1208.6449.

## Version history

- 2026-06-27: First polished draft.
