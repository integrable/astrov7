---
title: "Mellin-Space Blocks Preview"
description: "Preview of how Mellin space reorganizes conformal four-point functions, conformal blocks, and OPE data into a meromorphic amplitude-like representation."
sidebar:
  label: "Mellin-Space Blocks Preview"
  order: 10
level: Advanced
status: "Polished draft"
source: "Mack 2009; Penedones 2011; Fitzpatrick, Kaplan, Penedones, Raju, van Rees 2011; Paulos 2011; Costa et al. 2012; Poland, Rychkov, Vichi 2019"
topics:
  - conformal blocks
  - Mellin space
  - operator product expansion
  - AdS/CFT
  - large-N CFT
canonicalTopics:
  - mellin-space-conformal-blocks
  - conformal-partial-waves
  - holographic-cft
researchStatus:
  established:
    - "Mellin representations of scalar conformal correlators and their pole interpretation in terms of exchanged CFT operators are standard tools in conformal bootstrap and holographic CFT."
  active:
    - "Efficient Mellin-space methods for spinning correlators, loop-level AdS amplitudes, flat-space limits, and nonperturbative bootstrap applications remain active."
---

## Summary

Mellin space is a transform of conformal correlators that makes a CFT four-point function look unexpectedly close to a scattering amplitude. Instead of treating the reduced correlator $\mathcal G(u,v)$ directly as a function of cross-ratios, one writes it as an inverse Mellin integral with a meromorphic object $M(s,t)$:

$$
\mathcal G(u,v)
=
\int_{\mathcal C}\frac{ds\,dt}{(4\pi i)^2}
\,u^{s/2}v^{-(s+t)/2}
\Gamma_{\Delta_\phi}(s,t)M(s,t).
$$

The Mellin variables $s,t,u_M$ obey $s+t+u_M=4\Delta_\phi$ for four identical scalar operators of dimension $\Delta_\phi$. The notation $u_M$ is deliberately different from the cross-ratio $u$. The gamma-factor $\Gamma_{\Delta_\phi}(s,t)$ is a convention-dependent product of gamma functions fixed by external dimensions.

The main reason Mellin space is useful is that exchanged operators become poles. Roughly,

$$
M(s,t)\sim
\sum_{m=0}^{\infty}
\frac{Q_{m,\ell}(t)}{s-\tau_{\mathcal O}-2m},
\qquad
\tau_{\mathcal O}=\Delta_{\mathcal O}-\ell,
$$

where $\tau_{\mathcal O}$ is the twist of the exchanged primary and $Q_{m,\ell}(t)$ is a polynomial encoding spin and descendant structure. This is the Mellin-space version of the statement that the OPE decomposes a four-point function into conformal multiplets.

This page is a preview. It explains the dictionary and the intuition, not the full technology of Mellin amplitudes, Mack polynomials, analytic continuation, or loop-level holographic correlators.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Mellin-space dictionary](/figures/cft-bootstrap/mellin-space-dictionary.svg)

<figcaption>

The Mellin transform reorganizes a position-space four-point function into a meromorphic object $M(s,t)$. Operator exchange gives poles, residues encode spin, and low-degree polynomials are the Mellin-space avatar of local contact interactions.

</figcaption>
</figure>

## Prerequisites

You should know the scalar four-point function from [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), the meaning of cross-ratios from [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/), the OPE from [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), and the block decomposition from [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/).

For this preview, it is enough to be comfortable with complex contour integrals, gamma functions, and the idea that a meromorphic function is controlled by its poles and residues. The relation to AdS contact and exchange diagrams is useful but not required.

## Core idea

Position-space conformal blocks are natural for symmetry and numerical bootstrap. Mellin space is natural for analytic structure.

The analogy with scattering amplitudes is not exact, but it is powerful:

| Scattering amplitude language | Mellin-space CFT language |
|---|---|
| Mandelstam variables $s,t,u$ | Mellin variables $s,t,u_M$ constrained by external dimensions |
| particle exchange poles | primary-operator exchange poles |
| residues carry spin | residues are Mack-polynomial structures |
| contact interactions | polynomial Mellin amplitudes |
| factorization | OPE factorization |
| crossing of external legs | permutation constraints on $M(s,t)$ |

This analogy is especially sharp in holographic CFTs. Tree-level Witten diagrams in anti-de Sitter space often have Mellin amplitudes that look like ordinary Feynman amplitudes with shifted kinematics. This is one reason Mellin space became a standard language for large-$N$ CFTs and AdS/CFT calculations.

:::caution[Do not overread the analogy]
A Mellin amplitude is not an ordinary flat-space $S$-matrix. The CFT has no asymptotic particle states in the same sense, the variables are conjugate to logarithms of distances, and the gamma factors are part of the representation. The analogy is a guide, not a license to import scattering formulas blindly.
:::

## Setup and conventions

We work in Euclidean signature. For four identical scalar primaries $\phi$ of dimension $\Delta_\phi$, write

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2)^{\Delta_\phi}(x_{34}^2)^{\Delta_\phi}}
\mathcal G(u,v),
$$

where

$$
u
=
\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v
=
\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The displayed equation contains a harmless typography trap: the cross-ratio is $u$, while the third Mellin variable will be called $u_M$. To avoid ambiguity, this page always writes the Mellin constraint as

$$
s+t+u_M=4\Delta_\phi.
$$

A common scalar Mellin representation is

$$
\mathcal G(u,v)
=
\int_{\mathcal C}\frac{ds\,dt}{(4\pi i)^2}
\,u^{s/2}v^{-(s+t)/2}
\Gamma_{\Delta_\phi}(s,t)M(s,t),
$$

with

$$
\Gamma_{\Delta_\phi}(s,t)
=
\Gamma^2\!\left(\Delta_\phi-\frac{s}{2}\right)
\Gamma^2\!\left(\Delta_\phi-\frac{t}{2}\right)
\Gamma^2\!\left(\Delta_\phi-\frac{u_M}{2}\right).
$$

Different sources shift $s,t,u_M$, move pieces between $M$ and $\Gamma_{\Delta_\phi}$, or use $x_{ij}$ rather than $x_{ij}^2$. The invariant content is the pole structure and the crossing relations, not this exact placement of factors.

## The general Mellin representation

For scalar $n$-point functions, the cleanest representation uses Mellin variables $\delta_{ij}=\delta_{ji}$ attached to pairs of points:

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle
=
\int[d\delta]\,M(\delta_{ij})
\prod_{1\le i<j\le n}
\frac{\Gamma(\delta_{ij})}{(x_{ij}^2)^{\delta_{ij}}},
$$

subject to the constraints

$$
\sum_{j\ne i}\delta_{ij}=\Delta_i,
\qquad i=1,\dots,n.
$$

These constraints are exactly what make the integral transform covariant under independent rescalings of each point. For $n$ points there are

$$
\frac{n(n-3)}{2}
$$

independent Mellin variables. This equals the number of independent conformal cross-ratios for scalar $n$-point functions in a generic dimension, at least before low-dimensional degeneracies enter.

For $n=4$, there are two independent Mellin variables. Calling them $s$ and $t$ is more than notation: it invites an amplitude-like organization into $s$-, $t$-, and $u_M$-channel data.

## Why exchanged operators become poles

The OPE says that as $x_1\to x_2$,

$$
\phi(x_1)\phi(x_2)
\sim
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}
\frac{\mathcal D_{12}^{\mathcal O}\mathcal O(x_2)}{(x_{12}^2)^{\Delta_\phi-\Delta_{\mathcal O}/2}},
$$

where $\mathcal D_{12}^{\mathcal O}$ packages descendants and spin indices. In a scalar four-point function, each primary $\mathcal O$ contributes a conformal block.

In Mellin space, the same multiplet appears as a sequence of poles. For an exchanged primary of dimension $\Delta$ and spin $\ell$ in the $12\to34$ channel, the poles occur at

$$
s=\tau+2m,
\qquad
\tau=\Delta-\ell,
\qquad
m=0,1,2,\dots.
$$

The integer $m$ labels descendant levels in a way adapted to the Mellin representation. The residues are polynomials in the transverse Mellin variable, schematically

$$
\operatorname*{Res}_{s=\tau+2m}M(s,t)
\propto
\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,Q_{m,\ell}(t),
$$

where the $Q_{m,\ell}$ are Mack-polynomial structures. The precise normalization depends on the Mellin convention and on the normalization of conformal blocks.

The slogan is:

$$
\text{OPE exchange in position space}
\quad\longleftrightarrow\quad
\text{pole expansion in Mellin space}.
$$

## Mellin blocks and partial waves

A conformal block is the contribution of one primary and all its descendants to a four-point function. A Mellin-space block is the same idea expressed after the Mellin transform.

Very schematically,

$$
M(s,t)
=
\sum_{\mathcal O}\lambda_{12\mathcal O}\lambda_{34\mathcal O}\,
\mathcal M_{\Delta,\ell}(s,t),
$$

where $\mathcal M_{\Delta,\ell}$ is the Mellin-space contribution of the conformal multiplet. This object has the expected exchange poles in the channel being decomposed.

There is a subtlety. In position space, one often distinguishes conformal blocks, conformal partial waves, and shadow-symmetric objects. In Mellin space, this distinction remains. A partial-wave representation can naturally include both an operator and its shadow; a block representation chooses the physical OPE behavior. For a first reading, remember only this:

:::note[Mellin blocks are not new CFT data]
Mellin-space blocks are a different representation of the same conformal-block decomposition. They do not add new operators or new OPE coefficients. They reorganize the same data.
:::

## Contact terms and exchange terms

Mellin space is beautifully adapted to holographic intuition.

A local contact Witten diagram in AdS often gives a polynomial Mellin amplitude. A contact interaction with more derivatives gives a polynomial of higher degree. For example, the schematic AdS interaction

$$
\int_{\mathrm{AdS}}\sqrt g\,\Phi^4
$$

corresponds to a constant Mellin amplitude, up to normalization. Interactions with derivatives, such as

$$
\int_{\mathrm{AdS}}\sqrt g\,(\nabla\Phi)^4,
$$

produce polynomial dependence on $s,t,u_M$.

Exchange Witten diagrams instead produce pole families. If a bulk field dual to a CFT primary $\mathcal O$ is exchanged, the Mellin amplitude has poles at the twists associated with $\mathcal O$ and its descendants.

This is the reason Mellin space is sometimes described as the closest CFT analogue of momentum-space Feynman rules. In a holographic large-$N$ CFT, the resemblance is not cosmetic: locality in AdS becomes a statement about the analytic growth and polynomial behavior of Mellin amplitudes.

## Crossing in Mellin space

For identical scalar operators, crossing says that the same four-point function can be expanded in different OPE channels. In position space one form is

$$
v^{\Delta_\phi}\mathcal G(u,v)
=
u^{\Delta_\phi}\mathcal G(v,u).
$$

In Mellin space, the same statement becomes a permutation constraint on the Mellin amplitude. In a symmetric convention,

$$
M(s,t)=M(t,s)=M(s,u_M)=\cdots,
$$

where the ellipsis means the appropriate external-leg permutations. For nonidentical operators, the relation includes flavor, spin, and ordering data, and the right-hand side may be a different Mellin amplitude for a permuted correlator.

Crossing in Mellin space therefore resembles the crossing of scattering amplitudes: the same meromorphic object must be consistently interpretable in different channels.

## Relation to the flat-space limit

In holographic CFTs with a large AdS radius in bulk units, Mellin amplitudes can approach flat-space scattering amplitudes in an appropriate limit. Roughly,

$$
\text{large dimensions and large Mellin variables}
\quad\longrightarrow\quad
\text{flat-space energy invariants}.
$$

This relation is one of the conceptual bridges between conformal bootstrap, AdS/CFT, and scattering amplitudes. It is also delicate. The precise limit depends on the AdS radius, external dimensions, normalizations, and whether the CFT has a sparse large-$N$ spectrum. The flat-space limit is therefore not part of the default definition of Mellin space; it is an additional structure available in holographic settings.

## Common pitfalls

**Confusing the cross-ratio $u$ with the Mellin variable $u_M$.** They are different objects. The cross-ratio $u$ is built from positions. The Mellin variable $u_M$ is constrained by $s+t+u_M=4\Delta_\phi$ in the identical-scalar convention used here.

**Thinking that the gamma functions are optional decoration.** They are part of the transform. They contain universal kinematic poles and make conformal covariance and OPE limits work correctly.

**Calling every Mellin-space object a block.** Mellin amplitudes, Mellin blocks, Mellin partial waves, Mack polynomials, and Witten-diagram Mellin amplitudes are related but not identical.

**Forgetting normalization dependence.** Moving gamma factors between $M$ and the measure changes the displayed pole bookkeeping. Always compare conventions before comparing residues.

**Assuming Mellin space is best for every bootstrap problem.** Numerical bootstrap usually works directly with derivatives of position-space conformal blocks. Mellin space is especially useful for analytic structure, large-$N$ expansions, holography, and amplitude-like reasoning.

## Relations to other pages

This page sits at the end of the Conformal Blocks chapter. It uses [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/), [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/), and [Conformal Blocks in Higher Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-higher-dimensions/).

The next conceptual step is [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/), where the block decomposition becomes an equation. Mellin-space methods reappear later in [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) and [Holographic CFT](/cft-bootstrap/holographic-cft/).

## Research status

The scalar Mellin representation, the pole interpretation of exchanged operators, and the relation to AdS tree diagrams are established tools.

Active directions include spinning Mellin amplitudes, loop-level holographic correlators, efficient bases for exchange diagrams, dispersive and analytic-functional approaches, celestial and flat-space limits, and the use of Mellin-space growth conditions as diagnostics of bulk locality.

## Exercises

### Counting Mellin variables

Show that the scalar $n$-point Mellin representation has $n(n-3)/2$ independent Mellin variables.

<details><summary><strong>Solution</strong></summary>

There is one symmetric variable $\delta_{ij}$ for each unordered pair of points, so the starting number is

$$
\frac{n(n-1)}{2}.
$$

The constraints are

$$
\sum_{j\ne i}\delta_{ij}=\Delta_i,
\qquad i=1,\dots,n.
$$

For generic external dimensions these are $n$ independent linear constraints. Hence the number of independent variables is

$$
\frac{n(n-1)}{2}-n
=
\frac{n(n-3)}{2}.
$$

For $n=4$, this gives two variables, matching the two cross-ratios $u,v$.

</details>

### Pole positions and twist

Suppose a spin-$\ell$ primary of dimension $\Delta$ appears in the $\phi\times\phi$ OPE. What is the leading $s$-channel Mellin pole in the convention used on this page?

<details><summary><strong>Solution</strong></summary>

The leading pole is at the twist of the exchanged primary,

$$
s=\tau,
\qquad
\tau=\Delta-\ell.
$$

Descendant contributions generate the tower

$$
s=\tau+2m,
\qquad m=0,1,2,\dots.
$$

The precise residues depend on the normalization of Mellin blocks and the placement of gamma functions in the measure.

</details>

### Crossing as a permutation

For identical scalar external operators, explain why Mellin-space crossing should permute $s,t,u_M$.

<details><summary><strong>Solution</strong></summary>

The variables $s,t,u_M$ are tied to pairings of external points, just as Mandelstam variables are tied to pairings of external particles in scattering. Exchanging identical external operators permutes the pairings. Since the position-space correlator is unchanged by such a permutation, the Mellin representation must encode the same invariance by relating the Mellin amplitude at permuted values of $s,t,u_M$. In a symmetric convention this is simply

$$
M(s,t)=M(t,s)=M(s,u_M)=\cdots.
$$

Other conventions can hide part of the permutation in gamma factors or prefactors, but the invariant statement is the same.

</details>

## References

- G. Mack, “D-independent representation of conformal field theories in D dimensions via transformation to auxiliary dual resonance models. Scalar amplitudes,” arXiv:0907.2407.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” arXiv:1011.1485.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” arXiv:1107.1499.
- M. F. Paulos, “Towards Feynman rules for Mellin amplitudes,” arXiv:1107.1504.
- M. S. Costa, V. Gonçalves, and J. Penedones, “Spinning AdS propagators,” arXiv:1404.5625.
- D. Poland, S. Rychkov, and A. Vichi, “The conformal bootstrap: theory, numerical techniques, and applications,” Reviews of Modern Physics 91, 015002 (2019), arXiv:1805.04405.

## Version history

- 2026-06-27: First polished draft. Added Mellin representation, pole dictionary, AdS intuition, crossing remarks, exercises, and figure.
