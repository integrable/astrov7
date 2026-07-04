---
title: "Amplituhedron Preview"
description: "A conceptual preview of the amplituhedron, positive geometries, canonical forms, and their role in planar N=4 super Yang–Mills amplitudes."
sidebar:
  label: "Amplituhedron Preview"
  order: 10
level: Advanced
status: "Polished draft"
source: "Arkani-Hamed et al. 2012; Arkani-Hamed and Trnka 2013; Arkani-Hamed, Bai, and Lam 2017; modern amplitudes reviews."
topics:
  - amplituhedron
  - positive geometry
  - positive Grassmannian
  - planar amplitudes
  - canonical forms
canonicalTopics:
  - amplituhedron
  - positive-geometry
  - canonical-forms
  - planar-n4-sym-amplitudes
researchStatus:
  established:
    - "The positive Grassmannian, on-shell diagrams, and canonical forms are established tools in the study of planar amplitudes, especially in N=4 super Yang–Mills theory."
  active:
    - "The amplituhedron program remains active, especially for loop geometries, triangulations, positive geometries beyond planar N=4 super Yang–Mills theory, and possible lessons about spacetime locality."
---

## Summary

The amplituhedron is a positive geometric object whose canonical differential form encodes scattering-amplitude data in planar $N=4$ super Yang–Mills theory. It is one of the clearest examples of a modern amplitudes theme: the final answer often has a global structure that is almost invisible term by term in Feynman diagrams.

The rough slogan is

$$
\text{planar amplitude or loop integrand}
\quad \longleftrightarrow \quad
\Omega(\mathcal A),
$$

where $\mathcal A$ is a positive geometry and $\Omega(\mathcal A)$ is its canonical form. This slogan is deliberately compressed. The original amplituhedron most directly describes tree amplitudes and loop **integrands** in planar $N=4$ super Yang–Mills theory, not arbitrary Standard Model amplitudes and not automatically integrated loop observables.

The conceptual punchline is striking. In the amplituhedron picture, locality and unitarity are not imposed diagram by diagram. They appear through the boundary structure of a positive geometry: facets give physical poles, residues give factorization, and loop boundaries encode cuts.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 52rem;">

![Flow from positive Grassmannian data to the amplituhedron canonical form](/figures/perturbative-qft/amplituhedron-preview.svg)

<figcaption>

The amplituhedron reorganizes planar amplitude data. Positive cells in the Grassmannian, often represented by BCFW cells or on-shell diagrams, are mapped to a positive geometry. The canonical form $\Omega(\mathcal A)$ has logarithmic boundary singularities whose residues reproduce physical factorization, cuts, and related amplitude data.

</figcaption>
</figure>

This page is a preview. It explains what the amplituhedron is trying to do, which assumptions enter, what the central mathematical objects are, and where the caveats live.

## Prerequisites

You should know the pages on [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/), [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/), and [On-Shell Diagrams Preview](/perturbative-qft/modern-on-shell-amplitudes/on-shell-diagrams-preview/).

The mathematical background is the positive Grassmannian, projective geometry, and differential forms. This page gives the minimum vocabulary needed for a first pass.

## Core idea

A Feynman-diagram expansion computes an amplitude as a sum of local terms. Each term has a clear spacetime origin, but gauge invariance, hidden symmetries, and spurious-pole cancellation often appear only after summing many diagrams.

The amplituhedron asks for a different organization. Instead of starting with local spacetime diagrams, one starts with a positive geometry and asks for its canonical form. The amplitude is then read from that form.

For an ordinary polygon, a canonical form has logarithmic singularities on the edges. A triangulation computes the same form by summing triangle forms. The internal diagonal of a triangulation is not a boundary of the polygon, so the pole associated with that diagonal cancels between adjacent triangles. This is the toy-model version of a familiar amplitude miracle: spurious singularities appear in intermediate representations and cancel in the final answer.

For amplitudes, the analogy becomes richer:

| Geometry language | Amplitude language |
|---|---|
| boundary | singular limit |
| facet | physical pole or cut condition |
| canonical form | amplitude form or loop integrand |
| triangulation | BCFW-like representation |
| cancellation of internal boundaries | cancellation of spurious poles |
| residue on a boundary | factorized lower-point data |

Positive geometry is therefore not decorative. It packages the analytic structure of amplitudes into a global object.

## Setup and conventions

The original amplituhedron is formulated for planar color-ordered amplitudes in four-dimensional $N=4$ super Yang–Mills theory. The natural variables are **momentum twistors** $Z_i$, which make dual conformal symmetry natural and turn planar kinematic constraints into projective geometry.

There is a convention worth flagging. In amplitude language, an $N^k\mathrm{MHV}$ amplitude has $k+2$ negative-helicity gluons in a gluonic component. In the amplituhedron literature, the same $k$ labels the relevant Grassmannian degree. Thus MHV corresponds to $k=0$, NMHV to $k=1$, and so on.

At tree level, the amplituhedron is the image of the positive Grassmannian under a positive linear map:

$$
\mathcal A_{n,k,4}(Z)
=
\left\{
Y=CZ\in G(k,k+4)
\;\middle|\;
C\in G_{\ge0}(k,n)
\right\}.
$$

Here $n$ is the number of external particles, $G_{\ge0}(k,n)$ is the totally nonnegative part of the Grassmannian, $C$ represents a positive $k$-plane, and $Y=CZ$ is the image $k$-plane in $G(k,k+4)$. The subscript $4$ records that the physical amplituhedron for four-dimensional scattering has $m=4$ in the more general notation $\mathcal A_{n,k,m}$.

For loop integrands, the geometry is enlarged by adding loop variables, often represented by lines in momentum-twistor space. The loop amplituhedron is a geometry for the **integrand** before integration. Integrated loop amplitudes require regulators, contours, analytic continuation, and infrared-safe definitions.

## Positive Grassmannian

The Grassmannian $G(k,n)$ is the space of $k$-planes in an $n$-dimensional vector space. A point can be represented by a full-rank $k\times n$ matrix $C$, with the identification

$$
C\sim gC,
\qquad g\in GL(k).
$$

The Plücker coordinates are the $k\times k$ minors of $C$. The positive Grassmannian $G_{>0}(k,n)$ is the region where all ordered maximal minors are positive. Its closure $G_{\ge0}(k,n)$ allows some minors to vanish.

This positivity is not probability positivity. It is a real-algebraic condition on minors. Its importance for amplitudes is that many on-shell diagrams naturally parametrize cells of $G_{\ge0}(k,n)$, and their forms are products of $d\log$ factors in positive coordinates.

The positive Grassmannian already organizes on-shell diagrams, BCFW bridges, Yangian-invariant leading singularities, and many relations among different on-shell representations. The amplituhedron is the next step: rather than treating cells merely as computational pieces, it views them as pieces of a single positive geometry.

## Canonical forms

A positive geometry $\mathcal P$ comes with a canonical form $\Omega(\mathcal P)$. This form is characterized recursively by its singularities:

1. it has only logarithmic singularities on the boundaries of $\mathcal P$;
2. the residue on each boundary is the canonical form of that boundary;
3. the form has no poles on artificial internal boundaries introduced by a triangulation.

For the interval $[a,b]$, a canonical one-form is

$$
\Omega([a,b])
=
d\log\frac{x-a}{b-x},
$$

up to orientation. Its only singularities are at the endpoints. For a polygon, the canonical two-form has logarithmic singularities on the edges. If one computes it by triangulating the polygon, poles on internal diagonals cancel.

This is the geometric model for spurious-pole cancellation in amplitudes. A BCFW representation may contain poles that do not correspond to physical factorization channels. The final amplitude does not. In positive-geometry language, those poles are artifacts of a chosen triangulation, not boundaries of the underlying geometry.

## From cells to amplitudes

On-shell diagrams in planar $N=4$ super Yang–Mills theory are associated with cells of the positive Grassmannian. Each cell has positive coordinates $\alpha_a>0$ and a form of the schematic type

$$
\prod_a d\log \alpha_a.
$$

BCFW recursion can be viewed as a decomposition into such cells. The amplituhedron map pushes these cell forms forward to the target geometry. When the images cover the relevant region without overlap except on boundaries, the sum of cell forms gives the canonical form of the amplituhedron.

This picture explains several otherwise mysterious facts:

| Fact in amplitude calculations | Geometric explanation |
|---|---|
| BCFW terms are individually nonlocal-looking | a triangulation introduces internal boundaries |
| spurious poles cancel | internal-boundary residues cancel between adjacent cells |
| physical poles factorize | true facets have lower-dimensional residues |
| unitarity cuts are special boundaries | loop variables hit boundaries of the loop geometry |
| hidden symmetries become simpler | positivity and projective geometry expose them |

Feynman diagrams are not wrong. They are a local spacetime expansion. The amplituhedron is a different coordinate system on the same perturbative data, adapted to positivity, on-shellness, and hidden structure.

## Locality and unitarity as boundary data

In standard perturbative QFT, locality is built into the Lagrangian and Feynman rules. Unitarity is then checked through cutting equations, factorization, and the optical theorem. The amplituhedron reverses the emphasis.

The geometry is defined without starting from spacetime-local Feynman diagrams. Nevertheless, the canonical form has singular boundaries whose residues reproduce the expected factorization and cut behavior. Locality and unitarity appear as consequences of boundary structure.

That statement should be read carefully. It does **not** mean that locality and unitarity are false, optional, or experimentally irrelevant. It means that in this representation of a special class of amplitudes, they are not the most primitive organizational principle.

## Tree level versus loop level

At tree level, the amplituhedron encodes rational amplitude data. The canonical form has logarithmic singularities on boundaries corresponding to physical poles. BCFW cells provide natural triangulations.

At loop level, the geometry encodes the loop integrand. This is powerful because many properties of planar $N=4$ super Yang–Mills loop integrands are simpler than properties of integrated functions. But the integrated amplitude depends on regulators, contours, infrared behavior, analytic continuation, and function spaces such as polylogarithms and elliptic generalizations.

A safe memory hook is:

```txt
loop amplituhedron:
  organizes loop integrands;

integrated amplitude:
  requires integration, regularization, and analytic continuation.
```

## What the amplituhedron is good for

The amplituhedron is useful in at least four ways.

First, it reveals hidden simplicity. Long sums of diagrams can be reinterpreted as decompositions of one geometric object.

Second, it clarifies spurious singularities. They are not physical boundaries of the geometry.

Third, it reorganizes unitarity. Cuts and factorization become boundary statements rather than separate diagrammatic checks.

Fourth, it points toward a broader question: can scattering theory be formulated from positivity, singularity structure, and consistency rather than from a local Lagrangian as the starting point?

That last question is exciting, but it is not settled. The amplituhedron is a powerful window into special amplitudes, not yet a universal replacement for QFT.

## Common pitfalls

**Thinking the amplituhedron computes all amplitudes.** The original amplituhedron is tied to planar $N=4$ super Yang–Mills theory. Extensions and cousins exist, but the general Standard Model is not simply inside the amplituhedron.

**Forgetting the word integrand.** Loop-level amplituhedron geometry describes loop integrands. Integrated loop amplitudes involve additional analytic and infrared structure.

**Confusing positive geometry with probability.** Positivity here means positivity of minors, coordinates, or semialgebraic regions. It is not Born-rule positivity.

**Taking “locality is emergent” out of scope.** Here it means spacetime locality is not the primitive organizing input of the representation. It does not mean locality has disappeared from physics.

**Ignoring planarity.** Momentum twistors and the original amplituhedron rely heavily on planar ordering. Nonplanar amplitudes are much less understood in this language.

## Relations to other pages

- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) supplies the massless four-dimensional language used by modern amplitude methods.
- [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) explains the on-shell building blocks that underlie BCFW and on-shell diagrams.
- [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) explains the planar ordering used here.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) gives recursive decompositions that become triangulations in positive geometry.
- [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/) explains cuts and leading singularities, which appear as boundary data.
- [On-Shell Diagrams Preview](/perturbative-qft/modern-on-shell-amplitudes/on-shell-diagrams-preview/) introduces the bridge between diagrams and cells of the positive Grassmannian.

## Research status

**Established.** The positive Grassmannian, on-shell diagrams, BCFW cells, and canonical forms are standard parts of modern amplitude theory. The amplituhedron gives a precise and highly nontrivial geometric framework for planar $N=4$ super Yang–Mills tree amplitudes and loop integrands.

**Active.** Loop amplituhedra, triangulations, boundary stratifications, relation to cluster algebras, momentum-space positive geometries, nonplanar generalizations, and geometries for less supersymmetric theories remain active research topics.

**Speculative.** The broader idea that spacetime locality and quantum mechanics may emerge from deeper positive-geometric principles is inspiring but not yet a complete formulation of QFT or quantum gravity.

## Exercises

### Exercise 1: Canonical form of an interval

Show that

$$
\Omega=d\log\frac{x-a}{b-x}
$$

has only endpoint singularities on the interval $[a,b]$.

<details>
<summary><strong>Solution</strong></summary>

Using $d\log f=df/f$,

$$
\Omega
=d\log(x-a)-d\log(b-x)
=\frac{dx}{x-a}+\frac{dx}{b-x}.
$$

Thus the only poles are at $x=a$ and $x=b$. There is no pole in the interior of the interval. The residue signs depend on orientation, but the logarithmic endpoint structure is the important point.

</details>

### Exercise 2: Dimension of the tree amplituhedron

For generic positive external data, why does the tree amplituhedron $\mathcal A_{n,k,4}$ have dimension $4k$?

<details>
<summary><strong>Solution</strong></summary>

The target space is $G(k,k+4)$, the space of $k$-planes in a $(k+4)$-dimensional vector space. The dimension of a Grassmannian is

$$
\dim G(k,N)=k(N-k).
$$

With $N=k+4$,

$$
\dim G(k,k+4)=k[(k+4)-k]=4k.
$$

For generic positive external data, the amplituhedron image fills a $4k$-dimensional region in this target.

</details>

### Exercise 3: Spurious poles from a triangulated polygon

A quadrilateral can be triangulated by drawing one diagonal. Explain why the diagonal can appear as a pole in individual triangle canonical forms but cannot appear as a pole of the quadrilateral canonical form.

<details>
<summary><strong>Solution</strong></summary>

The diagonal is not a boundary of the quadrilateral. It is an internal boundary introduced by the triangulation. Each triangle has the diagonal as one of its edges, so each triangle canonical form can have a logarithmic singularity there.

The two triangles induce opposite orientations on the shared diagonal. When the two triangle forms are added, the residues on the shared diagonal cancel. The final form has poles only on the true external edges of the quadrilateral.

</details>

### Exercise 4: MHV degree convention

In the common amplituhedron convention, what value of $k$ corresponds to an MHV amplitude? What about an NMHV amplitude?

<details>
<summary><strong>Solution</strong></summary>

An $N^k\mathrm{MHV}$ amplitude has $k$ units of helicity degree beyond MHV. Therefore

$$
\mathrm{MHV}: k=0,
\qquad
\mathrm{NMHV}: k=1.
$$

This differs from simply counting negative-helicity gluons: an MHV gluon component has two negative-helicity gluons.

</details>

## References

- N. Arkani-Hamed, J. L. Bourjaily, F. Cachazo, A. B. Goncharov, A. Postnikov, and J. Trnka, “Scattering Amplitudes and the Positive Grassmannian.”
- N. Arkani-Hamed and J. Trnka, “The Amplituhedron.”
- N. Arkani-Hamed and J. Trnka, “Into the Amplituhedron.”
- N. Arkani-Hamed, Y. Bai, and T. Lam, “Positive Geometries and Canonical Forms.”
- J. L. Bourjaily, *Scattering Amplitudes in Gauge Theory and Gravity*.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*.

## Version history

- **2026-06-13:** Initial advanced preview page. Scope restricted to the conceptual structure of the amplituhedron and its relation to positive geometry; detailed momentum-twistor derivations, loop amplituhedra, and nonplanar questions are left for later pages.
