---
title: "Two-Dimensional CFT"
description: "Chapter overview for two-dimensional conformal field theory in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Sénéchal 1997; Ginsparg 1988; Cardy 1996; Rychkov 2016"
topics:
  - two-dimensional CFT
  - holomorphic symmetry
  - complex coordinates
  - Virasoro symmetry
  - radial quantization
canonicalTopics:
  - two-dimensional-conformal-field-theory
  - holomorphic-factorization
  - local-conformal-symmetry
  - two-dimensional-radial-quantization
researchStatus:
  established:
    - "Two-dimensional CFT is controlled by local holomorphic and antiholomorphic conformal transformations, leading to an infinite-dimensional enhancement of global conformal symmetry."
  active:
    - "Modern work extends the classic framework to logarithmic CFTs, nonunitary theories, defects, boundaries, higher-genus constraints, modular bootstrap, and categorical structures."
---

Two-Dimensional CFT is the chapter in the CFT and Bootstrap volume where conformal symmetry becomes radically more powerful. In $d\geq3$, the conformal group is finite-dimensional. In two Euclidean dimensions, local conformal maps are holomorphic or antiholomorphic functions, so the local symmetry algebra becomes infinite-dimensional.

This chapter explains the special two-dimensional language before the Virasoro chapter uses it in full force. The main characters are complex coordinates, holomorphic and antiholomorphic sectors, local conformal transformations, the stress tensor, radial quantization on the plane, the cylinder map, and the first universal examples: the free boson, the free fermion, and the compact boson.

The guiding slogan is

$$
\text{two-dimensional CFT}
=
\text{global CFT}
+
\text{holomorphic factorization}
+
\text{local conformal symmetry}.
$$

The slogan is useful, but a little dangerous. Not every two-dimensional CFT factorizes into independent left and right theories, and not every statement about local holomorphic transformations is a statement about a globally well-defined transformation on an arbitrary Riemann surface. This chapter keeps those distinctions visible.

## Prerequisites

You should know the volume [Conventions and Notation](/cft-bootstrap/conventions/), the overview [What Is a CFT?](/cft-bootstrap/what-is-a-cft/), and the basic chapters on [Conformal Symmetry](/cft-bootstrap/conformal-symmetry/), [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/), [Correlation Functions](/cft-bootstrap/correlation-functions/), [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/), and [Conformal Blocks](/cft-bootstrap/conformal-blocks/).

For a first pass, you do not need string theory, modular invariance, affine Lie algebras, vertex operator algebras, or minimal models. Those appear later. You should be comfortable with complex analysis at the level of holomorphic functions, residues, Laurent series, and contour deformation.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/) | The dictionary between $(x^1,x^2)$ and $(z,\bar z)$, including derivatives, metric factors, orientation, and tensor components. |
| 2 | [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/) | Why holomorphic maps are locally conformal, how they act on primaries, and where global subtleties enter. |
| 3 | [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) | The separation into left-moving and right-moving data, and the caveats that prevent overusing the slogan. |
| 4 | [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) | The holomorphic stress tensor, antiholomorphic stress tensor, conservation, tracelessness, and central-charge preview. |
| 5 | [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) | How states on circles, Laurent modes, and operator insertions at the origin become the natural Hilbert-space language. |
| 6 | [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/) | The exponential map from the cylinder to the plane and the origin of finite-size energies and Schwarzian terms. |
| 7 | [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) | The two-dimensional OPE as a Laurent expansion organized by left and right weights. |
| 8 | [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/) | The canonical Gaussian CFT, vertex operators, currents, and the simplest playground for compactification. |
| 9 | [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) | Majorana and Dirac fermions, spin structures, sectors, and the Ising-model gateway. |
| 10 | [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/) | Momentum and winding sectors, T-duality preview, current algebra, and the simplest continuous family of CFTs. |
| 11 | [Orbifolds Preview](/cft-bootstrap/two-dimensional-cft/orbifolds-preview/) | How discrete quotients produce new sectors, twisted operators, and modular-invariance constraints. |
| 12 | [Logarithmic CFT Preview](/cft-bootstrap/two-dimensional-cft/logarithmic-cft-preview/) | Why nonsemisimple operator mixing can produce logarithms in correlators and where the usual unitary intuition fails. |

After this path, you should be able to translate ordinary Euclidean two-dimensional formulas into complex notation, recognize left and right conformal weights, use the basic stress-tensor Ward identity, and understand why two dimensions deserve their own chapter before Virasoro symmetry is introduced systematically.

## Landmarks

The first landmark is the complex coordinate dictionary

$$
z=x^1+ix^2,
\qquad
\bar z=x^1-ix^2,
\qquad
\partial=\frac12(\partial_1-i\partial_2),
\qquad
\bar\partial=\frac12(\partial_1+i\partial_2).
$$

In these coordinates the flat Euclidean metric is

$$
ds^2=(dx^1)^2+(dx^2)^2=dz\,d\bar z,
$$

and the scalar Laplacian is

$$
\nabla^2=4\partial\bar\partial.
$$

The second landmark is the local form of conformal maps. A holomorphic change of coordinate

$$
w=f(z),
\qquad
\bar w=\bar f(\bar z),
$$

rescales the metric by

$$
dw\,d\bar w=|f'(z)|^2dz\,d\bar z.
$$

Thus it preserves angles while allowing a position-dependent scale factor.

The third landmark is the weight decomposition. A two-dimensional primary has left and right weights $(h,\bar h)$, with

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

The fourth landmark is the holomorphic stress tensor. Away from contact terms and anomalies, conservation and tracelessness imply

$$
\bar\partial T(z)=0,
\qquad
\partial\bar T(\bar z)=0.
$$

This is the seed of the Virasoro algebra. The modes

$$
T(z)=\sum_{n\in\mathbb Z}\frac{L_n}{z^{n+2}}
$$

are not merely a convenient basis; they are the generators of local conformal transformations in radial quantization.

The fifth landmark is the plane-cylinder map

$$
z=e^w,
\qquad
w=\tau+i\sigma.
$$

Radial evolution on the plane becomes time evolution on the cylinder. This is why scaling dimensions become cylinder energies and why finite-size spectra are a direct diagnostic of CFT data.

## Common confusions

**Confusing local and global conformal transformations.** Locally, any holomorphic function with nonzero derivative is conformal. Globally on the Riemann sphere, the nonsingular one-to-one conformal maps are only Möbius transformations. Virasoro symmetry is local and infinitesimal; global conformal symmetry is much smaller.

**Treating $z$ and $\bar z$ as always independent.** In Euclidean signature, $\bar z$ is the complex conjugate of $z$ in the standard real slice. In Lorentzian continuation, left and right light-cone variables are often treated independently. Both viewpoints are useful, but they are not the same statement.

**Thinking holomorphic factorization means every correlator is a product.** Some chiral building blocks factorize, and many rational CFT constructions exploit this beautifully. A full local correlator usually combines holomorphic and antiholomorphic pieces so that it is single-valued and physically acceptable.

**Identifying global blocks with Virasoro blocks.** A global block sums descendants generated by the finite-dimensional $SL(2)$ subalgebra. A Virasoro block sums all descendants generated by the full Virasoro algebra. The distinction is not cosmetic.

**Forgetting the central charge.** In two dimensions the stress tensor does not simply transform as an ordinary tensor under a general holomorphic map. The Schwarzian term and the central charge are indispensable, especially on the cylinder and on curved backgrounds.

**Importing higher-dimensional intuition too aggressively.** In $d\geq3$, conformal symmetry fixes far less. In two dimensions, the infinite-dimensional local algebra, contour methods, and representation theory reorganize the whole subject.

## Boundaries

This chapter develops the two-dimensional coordinate, operator, and example language needed for the rest of the volume. It is not the full Virasoro chapter. The algebra

$$
[L_m,L_n]=(m-n)L_{m+n}+\frac{c}{12}m(m^2-1)\delta_{m+n,0}
$$

appears here as a preview, but its representation theory belongs in [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/).

Minimal models, Kac tables, null-vector differential equations, fusion rules, and rational CFT belong in [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/). Affine current algebras and WZW models belong in [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/). Modular invariance and the modular bootstrap belong in [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/).

This chapter also does not try to classify two-dimensional CFTs. Classification is subtle: even compact unitary examples are much richer than the first free-field models suggest, and noncompact, logarithmic, nonunitary, supersymmetric, and boundary theories require extra care.

## Where to go next

After this chapter, go to [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) if you want the representation theory behind local conformal symmetry. Go to [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/) if you want exact solvable unitary and nonunitary models. Go to [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) if you want nonabelian symmetry, affine Lie algebras, and nonabelian bosonization.

For bootstrap applications, return to [Conformal Blocks](/cft-bootstrap/conformal-blocks/) and compare global blocks, Virasoro blocks, and modular constraints. For statistical physics, connect the free boson, free fermion, Ising CFT, compact boson, and Potts models to [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/).

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*. Standard detailed reference for two-dimensional CFT, including complex coordinates, radial quantization, Virasoro symmetry, minimal models, and modular invariance.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures. A compact and influential introduction to two-dimensional CFT methods.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*. Useful for the statistical-physics route into two-dimensional conformal invariance and finite-size scaling.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory,” *Nuclear Physics B* **241** (1984). Foundational paper on two-dimensional conformal symmetry and the conformal bootstrap.
- P. H. Ginsparg and G. W. Moore, “Lectures on 2D Gravity and 2D String Theory.” Useful for readers heading toward worldsheet and gravitational applications.
- J. Polchinski, *String Theory*, Vol. 1. Standard physics reference for two-dimensional CFT in the string-worldsheet setting.

## Version history

- **2026-06-28:** Replaced the scaffold with a polished chapter overview for the Two-Dimensional CFT chapter, including prerequisites, reading path, landmarks, boundaries, references, and next routes.
