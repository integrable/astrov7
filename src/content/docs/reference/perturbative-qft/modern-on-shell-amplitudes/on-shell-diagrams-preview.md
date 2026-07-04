---
title: "On-Shell Diagrams Preview"
description: "A preview of on-shell diagrams as graphs built from three-point amplitudes, leading singularities, and positive-geometry data."
sidebar:
  label: "On-Shell Diagrams Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Britto, Cachazo, Feng, and Witten; Arkani-Hamed, Cachazo, Cheung, and Kaplan; Arkani-Hamed et al.; Elvang and Huang."
topics:
  - on-shell diagrams
  - leading singularities
  - positive Grassmannian
  - BCFW bridges
  - modern amplitudes
canonicalTopics:
  - on-shell-diagrams
  - positive-grassmannian-preview
  - leading-singularities
  - bcfw-bridges
  - yangian-invariants-preview
researchStatus:
  established:
    - "On-shell diagrams are a standard organizing language for tree recursion and leading singularities, especially in planar maximally supersymmetric Yang–Mills theory."
  active:
    - "Connections among on-shell diagrams, positive geometry, loop integrands, amplituhedra, cluster algebras, form factors, curved backgrounds, and less supersymmetric theories remain active research directions."
---

## Summary

On-shell diagrams are graphs made by gluing on-shell three-point amplitudes. They look like Feynman diagrams, but their meaning is different. Their vertices are not off-shell Lagrangian vertices; they are physical complex-kinematic three-point amplitudes. Their internal lines are on-shell state sums. Their purpose is to organize factorization, BCFW recursion, leading singularities, and, in special planar theories, positive geometry.

The basic ingredients are the two massless three-point amplitudes

$$
A_3(1^-,2^-,3^+)
=
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle},
\qquad
A_3(1^+,2^+,3^-)
=
\frac{[12]^3}{[23][31]}.
$$

On-shell diagrams glue these atoms together along on-shell legs. Schematically,

$$
\text{gluing}
\sim
\sum_h\int d\Pi_\ell\,
A_L(\ldots,\ell^h)A_R((-\ell)^{-h},\ldots),
$$

or, in supersymmetric notation, by integrating over the on-shell superspace of the internal line.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![On-shell diagrams are built from three-point amplitudes and organize recursion, leading singularities, and planar positive geometry](/figures/perturbative-qft/on-shell-diagrams-preview.svg)

<figcaption>

On-shell diagrams glue three-point MHV and anti-MHV amplitudes along on-shell internal legs. In planar maximally supersymmetric Yang–Mills theory, these diagrams organize BCFW recursion terms, leading singularities, and cells of the positive Grassmannian.

</figcaption>
</figure>

This page is a preview. The main lesson is not that every amplitude should be drawn this way. The lesson is that, in some theories, locality, unitarity, helicity, and positivity can replace much of the off-shell diagrammatic machinery.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/), and [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/). For analytic background, review [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/).

## Core idea

Ordinary Feynman diagrams use off-shell propagators and vertices from a Lagrangian. On-shell diagrams use on-shell amplitudes as their elementary vertices. Internal lines are glued by summing over physical states and imposing on-shell kinematics.

The shift in viewpoint is:

```txt
Feynman diagram:
  off-shell vertices + propagators + gauge redundancy

on-shell diagram:
  on-shell three-point amplitudes + physical state sums + factorization
```

At tree level, on-shell diagrams give a graphical form of BCFW recursion. At loop level, they encode leading singularities: maximal residues obtained by cutting enough propagators to localize loop variables.

In planar $\mathcal N=4$ super-Yang–Mills theory, the language becomes much richer. On-shell diagrams correspond to cells of the positive Grassmannian, and the same data can be encoded by decorated permutations, BCFW bridges, boundary measurements, and differential forms with logarithmic singularities.

That last sentence sounds like a wizard left the chalkboard unsupervised. The point of this preview is to make the entrance less foggy.

## Setup and conventions

We work with massless external particles and complexified kinematics. Three-point amplitudes vanish for real Lorentzian momenta with nonzero energies, but they are nonzero and fundamental for complex momenta. This is the same setting used in BCFW recursion.

We use color-ordered amplitudes when discussing Yang–Mills examples. In supersymmetric examples, it is convenient to collect the particles of $\mathcal N=4$ super-Yang–Mills into an on-shell superfield and write superamplitudes. The full superspace formalism is not needed for the first pass, but it explains why on-shell diagrams are especially clean in that theory.

A black or white trivalent vertex often denotes one of the two three-point superamplitudes. Conventions vary by author. What matters physically is that the two vertices represent the two complex three-point kinematic branches:

| Branch | Nonzero spinor products | Representative amplitude |
|---|---|---|
| MHV | angle brackets | $A_3(1^-,2^-,3^+)$ |
| anti-MHV | square brackets | $A_3(1^+,2^+,3^-)$ |

Some papers reverse the black/white naming convention. Always check the local convention before importing a diagram.

## Three-point atoms

The massless three-point amplitudes are fixed by little-group covariance and mass dimension. For Yang–Mills theory, the nonzero helicity amplitudes are

$$
A_3(1^-,2^-,3^+)
=
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle},
$$

and

$$
A_3(1^+,2^+,3^-)
=
\frac{[12]^3}{[23][31]}.
$$

These formulas live on different complex three-point branches. Momentum conservation implies either

$$
[12]=[23]=[31]=0
$$

or

$$
\langle12\rangle=\langle23\rangle=\langle31\rangle=0.
$$

So the angle-bracket amplitude and the square-bracket amplitude are not two ordinary real-kinematic processes. They are two complex on-shell building blocks. On-shell diagrams are built by gluing these blocks consistently.

## Gluing internal lines

To glue two on-shell amplitudes across an internal leg, identify the momentum flowing out of one subamplitude with minus the momentum flowing out of the other. Then sum over the physical internal states.

For a nonsupersymmetric theory, the schematic gluing operation is

$$
\sum_h\int d\Pi_\ell\,
A_L(\ldots,\ell^h)A_R((-\ell)^{-h},\ldots).
$$

For a supersymmetric theory, the helicity sum is replaced by an integral over Grassmann variables. A common schematic notation is

$$
\int d^{\mathcal N}\eta_\ell\,
\mathcal A_L(\ldots,\ell,\eta_\ell)
\mathcal A_R(-\ell,\eta_\ell,\ldots).
$$

The on-shell diagram records this gluing pattern. It does not contain off-shell propagators. If a propagator appears in a BCFW term, it comes from the factorization channel that joins the two on-shell subamplitudes, not from an off-shell Lagrangian vertex expansion.

## BCFW bridges

A BCFW bridge is a graphical operation that connects two external legs of an on-shell diagram and introduces one complex deformation parameter. It is the diagrammatic avatar of the BCFW shift.

At tree level, repeated BCFW bridges build higher-point on-shell diagrams from three-point atoms. Each BCFW term corresponds to a factorization channel,

$$
A_n
=
\sum_{I,h}
A_L(\hat z_I)
\frac{i}{P_I^2}
A_R(\hat z_I),
$$

provided the shifted amplitude has no boundary term at infinity. On-shell diagrams turn the product

$$
A_L\frac{i}{P_I^2}A_R
$$

into a graph assembled from smaller on-shell graphs.

The bridge operation is especially natural in planar color-ordered amplitudes. Planarity fixes the allowed channels and preserves the cyclic ordering of external legs.

## Leading singularities

At loop level, on-shell diagrams most directly represent leading singularities. A leading singularity is a maximal residue of a loop integrand: enough propagators are placed on shell, and enough contour residues are taken, to localize all loop variables.

For a one-loop box in four dimensions, the quadruple cut is the basic example. The box coefficient is obtained from a product of four tree amplitudes evaluated on the cut solutions. In an on-shell diagram, those four tree amplitudes are further decomposed into three-point atoms when possible.

Thus the hierarchy is:

```txt
loop amplitude
  → generalized cuts
  → leading singularities
  → on-shell diagrams built from three-point amplitudes.
```

In planar $\mathcal N=4$ super-Yang–Mills theory, leading singularities are Yangian invariants and have a beautiful combinatorial and geometric classification. In a generic QFT, leading singularities are still useful, but they are not usually the whole story.

## Positive Grassmannian preview

The Grassmannian $G(k,n)$ is the space of $k$-planes in $n$ dimensions. A point in $G(k,n)$ can be represented by a $k\times n$ matrix $C$, modulo row operations:

$$
C\sim gC,
\qquad g\in GL(k).
$$

The positive Grassmannian $G_+(k,n)$ is the region where all ordered maximal minors are nonnegative. In planar $\mathcal N=4$ super-Yang–Mills theory, on-shell diagrams label positroid cells inside $G_+(k,n)$.

The rough dictionary is:

| On-shell diagram data | Grassmannian data |
|---|---|
| External legs | Columns of $C$ |
| MHV degree | $k$ |
| BCFW bridges | Cell coordinates |
| Reductions and boundaries | Vanishing minors |
| Decorated permutation | Cell label |
| Leading singularity | Differential form on a cell |

This preview does not prove the dictionary. The important point is that on-shell diagrams are not just convenient drawings. In special theories, they are coordinates on a positive geometric object whose boundaries encode physical factorization.

## What is special about planar maximally supersymmetric Yang–Mills theory

On-shell diagrams work in their most elegant form for planar $\mathcal N=4$ super-Yang–Mills theory. Several miracles align:

```txt
massless particles;
color ordering and planarity;
strong supersymmetry;
dual conformal symmetry;
Yangian symmetry;
logarithmic singularity structure;
positive Grassmannian geometry.
```

Outside that setting, pieces of the story survive. Three-point amplitudes still exist. BCFW recursion often works. Generalized unitarity is broadly useful. Leading singularities remain meaningful. But the full positive-Grassmannian and amplituhedron story is not a universal replacement for Feynman diagrams in arbitrary QFT.

This is a good place for intellectual hygiene. On-shell diagrams are a precise tool in the settings where their assumptions hold. They are not a decorative way to redraw every perturbative calculation.

## Worked example: four-point factorization as an on-shell diagram

The four-gluon MHV amplitude

$$
A_4(1^-,2^-,3^+,4^+)
=
\frac{\langle12\rangle^4}{\langle12\rangle\langle23\rangle\langle34\rangle\langle41\rangle}
$$

can be reconstructed from two three-point amplitudes using a BCFW shift. One factorization channel has the schematic form

$$
A_4
=
A_3(\hat1^-,2^-,-\hat P^+)
\frac{i}{P_{12}^2}
A_3(\hat P^-,3^+,\hat4^+),
$$

with shifted momenta evaluated at the pole $\hat P^2=0$. The on-shell diagram is simply two three-point vertices glued along the internal on-shell state, together with the BCFW bridge data that tells us how the shift reaches the pole.

The final expression is the Parke–Taylor amplitude. The important conceptual point is that the result is assembled from on-shell three-point amplitudes and factorization, rather than from the ordinary three-gluon and four-gluon Feynman vertices.

## Common pitfalls

**Thinking on-shell diagrams are Feynman diagrams.** Feynman diagrams are off-shell terms in a Lagrangian expansion. On-shell diagrams are built from on-shell amplitudes and state sums.

**Forgetting complex kinematics.** Massless three-point amplitudes require complex momenta. If you insist on real Lorentzian three-point scattering, the building blocks collapse.

**Importing black and white conventions without checking.** Different authors assign black and white vertices to MHV and anti-MHV branches differently.

**Assuming the positive Grassmannian applies to every theory.** The positive-Grassmannian classification is special, especially to planar $\mathcal N=4$ super-Yang–Mills theory. Generic QFTs do not inherit the whole structure.

**Confusing leading singularities with full amplitudes.** Leading singularities are powerful data, but full amplitudes also require integration, regularization, boundary information, and sometimes terms invisible to chosen cuts.

**Ignoring orientation and little-group weights.** Glued internal lines require consistent momentum orientation, helicity flow, and little-group scaling.

## Relations to other pages

- [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) gives the atoms used in on-shell diagrams.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) explains the recursive construction that on-shell diagrams draw.
- [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/) connects on-shell diagrams to leading singularities and loop cuts.
- [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) explains why planar ordering is so useful.
- [S-Matrix Bootstrap Preview](/perturbative-qft/unitarity-analyticity-dispersion/s-matrix-bootstrap-preview/) gives a broader view of amplitudes constrained without a Lagrangian.
- [Positivity Bounds Preview](/perturbative-qft/unitarity-analyticity-dispersion/positivity-bounds-preview/) is a different use of analyticity, unitarity, and positivity.

## Research status

**Established.** On-shell diagrams are a standard language for BCFW terms, leading singularities, and planar $\mathcal N=4$ super-Yang–Mills amplitudes. Their relation to the positive Grassmannian is a central result of modern amplitude theory.

**Active.** Current research explores on-shell diagram generalizations, amplituhedron geometry, nonplanar structures, form factors, loop-level positive geometries, cluster algebra connections, effective theories, gravity, and celestial or curved-spacetime analogues.

**Speculative or setting-dependent.** The strongest geometric claims are not universal across all QFTs. When leaving planar maximally supersymmetric Yang–Mills theory, one must recheck which pieces of the on-shell-diagram story survive.

## Exercises

### Exercise 1: little-group weight of a three-point amplitude

Check that

$$
A_3(1^-,2^-,3^+)
=
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle}
$$

has the correct little-group scaling for helicities $(-,-,+)$.

<details>
<summary><strong>Solution</strong></summary>

Under little-group scaling,

$$
\lambda_i\mapsto t_i\lambda_i,
\qquad
\tilde\lambda_i\mapsto t_i^{-1}\tilde\lambda_i,
$$

a helicity-$h_i$ external leg should scale as $t_i^{-2h_i}$.

The amplitude scales as

$$
\frac{(t_1t_2)^3}{(t_2t_3)(t_3t_1)}
=t_1^2t_2^2t_3^{-2}.
$$

For helicities $h_1=h_2=-1$ and $h_3=+1$, the required scaling is

$$
t_1^{-2(-1)}t_2^{-2(-1)}t_3^{-2(+1)}
=t_1^2t_2^2t_3^{-2}.
$$

The little-group weights match.

</details>

### Exercise 2: why three-point massless kinematics needs complex momenta

Show that real momentum conservation and on-shell conditions force all spinor products to vanish for three massless particles.

<details>
<summary><strong>Solution</strong></summary>

For three massless momenta with

$$
p_1+p_2+p_3=0,
$$

we have

$$
(p_1+p_2)^2=p_3^2=0.
$$

Since $p_1^2=p_2^2=0$, this gives

$$
2p_1\cdot p_2=0.
$$

Similarly, all pairwise dot products vanish. For real Lorentzian null momenta with physical energies, this forces the three momenta to be collinear. Momentum conservation then makes the scattering kinematically degenerate. In spinor variables, the pairwise invariants are

$$
s_{ij}=\langle ij\rangle[ji].
$$

For real momenta, square and angle brackets are related by complex conjugation, so $s_{ij}=0$ forces both branches to degenerate. Complex momenta allow one branch, such as all $[ij]=0$, while the angle brackets remain nonzero.

</details>

### Exercise 3: gluing helicities across an internal line

In the schematic gluing

$$
\sum_h A_L(\ldots,\ell^h)A_R((-\ell)^{-h},\ldots),
$$

why does the helicity label flip between the two subamplitudes?

<details>
<summary><strong>Solution</strong></summary>

The same physical internal particle is outgoing from one subamplitude and outgoing from the other only after reversing the momentum direction on one side. Reversing the momentum direction changes the convention used to label helicity relative to that momentum. Thus a state seen as $\ell^h$ on one side is represented as $(-\ell)^{-h}$ on the other side in an all-outgoing convention. The sum over $h$ then counts each physical intermediate state once.

</details>

### Exercise 4: on-shell diagram versus Feynman diagram

Give two reasons why an on-shell diagram with trivalent vertices is not the same object as a cubic Feynman diagram.

<details>
<summary><strong>Solution</strong></summary>

First, the vertices of an on-shell diagram are physical three-point amplitudes evaluated in complex on-shell kinematics. A cubic Feynman vertex is an off-shell Lagrangian interaction rule and may be gauge dependent.

Second, internal lines in an on-shell diagram represent on-shell state sums or residues. Internal lines in a Feynman diagram are off-shell propagators integrated over unrestricted loop or internal momenta. The two diagrams may look similar, but they encode different mathematical operations.

</details>

### Exercise 5: dimension of a Grassmannian

The complex Grassmannian $G(k,n)$ can be represented by a $k\times n$ matrix modulo $GL(k)$ row transformations. Show that its complex dimension is $k(n-k)$.

<details>
<summary><strong>Solution</strong></summary>

A $k\times n$ matrix has $kn$ complex entries. The row-equivalence group $GL(k)$ has dimension $k^2$. Modding out by this redundancy gives

$$
\dim G(k,n)=kn-k^2=k(n-k).
$$

The positive Grassmannian is a real positive region inside the real Grassmannian, refined further into cells by which ordered maximal minors vanish or remain positive.

</details>

## References

- R. Britto, F. Cachazo, B. Feng, and E. Witten, work on BCFW recursion and on-shell construction of tree amplitudes.
- N. Arkani-Hamed, F. Cachazo, C. Cheung, and J. Kaplan, work connecting scattering amplitudes, leading singularities, and the Grassmannian.
- N. Arkani-Hamed, J. Bourjaily, F. Cachazo, A. Goncharov, A. Postnikov, and J. Trnka, work on on-shell diagrams, the positive Grassmannian, and the amplituhedron program.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a pedagogical introduction to on-shell methods.
- L. J. Dixon, amplitude-review lectures, for spinor-helicity, color ordering, and loop-amplitude context.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for spinor-helicity, color ordering, and on-shell recursion in a QFT textbook setting.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, written as a preview of on-shell diagrams, leading singularities, and the positive-Grassmannian viewpoint.
