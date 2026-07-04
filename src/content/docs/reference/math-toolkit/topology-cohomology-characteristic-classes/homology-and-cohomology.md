---
title: "Homology and Cohomology"
description: "Defines homology and cohomology, explains cycles, boundaries, cocycles, periods, and why these structures encode charges, fluxes, defects, and topological terms in QFT."
sidebar:
  label: "Homology and Cohomology"
  order: 2
level: Advanced
status: "Polished draft"
source: "Standard algebraic topology and geometry references for physicists, including Hatcher, Bott–Tu, Nakahara, Frankel, and QFT treatments of defects, gauge fields, and topological terms."
topics:
  - homology
  - cohomology
  - chains
  - cycles
  - differential forms
  - periods
  - de Rham cohomology
  - conserved charges
  - flux quantization
  - Poincaré duality
canonicalTopics:
  - homology
  - cohomology
  - chains-and-cycles
  - de-rham-cohomology
  - periods
  - topological-charge
  - flux-quantization
  - poincare-duality
researchStatus:
  established:
    - "Homology and cohomology are standard topological invariants; in QFT they provide the natural language for cycles, fluxes, conserved charges, topological terms, and many global sectors."
  active:
    - "Modern QFT often requires refined versions, including torsion, differential cohomology, generalized cohomology, equivariant cohomology, relative cohomology, and higher-categorical or cobordism refinements."
---

## Summary

Homology and cohomology are two complementary ways to turn the intuitive word “hole” into computable algebra. Homology studies cycles modulo boundaries. Cohomology studies cocycles modulo coboundaries. In the differential-form language used throughout field theory, cohomology is the statement that closed forms are physically meaningful only up to exact forms when they are integrated over closed cycles.

The core definitions are

$$
H_k(M)=\frac{\ker(\partial:C_k\to C_{k-1})}{\operatorname{im}(\partial:C_{k+1}\to C_k)},
\qquad
H^k(M)=\frac{\ker(\delta:C^k\to C^{k+1})}{\operatorname{im}(\delta:C^{k-1}\to C^k)}.
$$

In de Rham form, the second formula becomes

$$
H^k_{\mathrm{dR}}(M)=\frac{\{\omega\in\Omega^k(M):d\omega=0\}}{\{\omega=d\alpha:\alpha\in\Omega^{k-1}(M)\}}.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Diagram showing chains, boundary complexes, homology, differential forms, cohomology, and the period pairing that produces charges.](/figures/math-toolkit/homology-cohomology-duality.svg)

<figcaption>

Homology organizes cycles modulo boundaries. Cohomology organizes closed probes modulo exact probes. Their pairing, $\langle[\omega],[\Sigma]\rangle=\int_\Sigma\omega$, is the basic mechanism behind periods, fluxes, winding numbers, topological charges, and many theta terms.

</figcaption>
</figure>

The QFT slogan is

$$
\text{charges are cohomology classes evaluated on homology classes}.
$$

That slogan covers ordinary conserved charges, magnetic flux, winding number, theta terms, linking observables, brane currents, and the first layer of characteristic classes. It is not the whole story, because torsion and differential refinements matter in many quantum theories. But it is the right entry point.

## Prerequisites

Read [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) first if you want the map-based classification of defects. This page shifts from maps to cycles and forms.

For the differential-form side, read [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For gauge-theory applications, read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/).

The page uses $M$ for a smooth manifold unless otherwise stated. Homology groups are often taken with integer coefficients, $H_k(M;\mathbb Z)$, because integer periods and torsion are physically important. De Rham cohomology uses real coefficients and therefore sees only the real, nontorsion part.

## Core idea

A $k$-dimensional cycle is a closed $k$-dimensional object: a loop, a closed surface, a closed hypersurface, or a formal sum of such objects. A boundary is a cycle that is itself the boundary of something one dimension higher. Homology declares two cycles equivalent if their difference is a boundary.

That is exactly what Stokes’ theorem wants. If $\omega$ is a closed $k$-form and two cycles differ by a boundary,

$$
\Sigma'-\Sigma=\partial B,
$$

then

$$
\int_{\Sigma'}\omega-\int_\Sigma\omega
=\int_{\partial B}\omega
=\int_B d\omega
=0.
$$

So a closed form does not care about the representative of a homology class. It only cares about the class $[\Sigma]$.

Similarly, if $\omega$ is exact,

$$
\omega=d\alpha,
$$

then on a closed cycle,

$$
\int_\Sigma\omega=\int_\Sigma d\alpha=\int_{\partial\Sigma}\alpha=0.
$$

So exact forms do not define new periods on closed cycles. They are invisible to closed-cycle integrals. This is the heart of cohomology in physics: closed probes modulo exact probes pair naturally with cycles modulo boundaries.

The whole construction is built to make the following expression depend only on topological classes:

$$
([\omega],[\Sigma])\longmapsto \int_\Sigma\omega.
$$

## Chains, cycles, and boundaries

A singular $k$-simplex in $M$ is a continuous map

$$
\sigma:\Delta^k\to M,
$$

where $\Delta^k$ is the standard $k$-simplex. A singular $k$-chain is a finite formal integer linear combination

$$
c=\sum_i n_i\sigma_i,
\qquad n_i\in\mathbb Z.
$$

The group of $k$-chains is denoted $C_k(M;\mathbb Z)$. The boundary map

$$
\partial:C_k(M;\mathbb Z)\to C_{k-1}(M;\mathbb Z)
$$

sends each oriented simplex to the alternating sum of its faces. The key identity is

$$
\partial^2=0.
$$

That identity says that the boundary of a boundary is zero. In pictures: the boundary of a surface is a collection of oriented curves, and the endpoints of those curves cancel. In algebra: the alternating signs in the simplex boundary formula make every codimension-two face appear twice with opposite signs.

Define the group of cycles by

$$
Z_k(M)=\ker\partial
=\{c\in C_k(M):\partial c=0\},
$$

and the group of boundaries by

$$
B_k(M)=\operatorname{im}\partial
=\{c=\partial b:b\in C_{k+1}(M)\}.
$$

Because $\partial^2=0$, every boundary is a cycle:

$$
B_k(M)\subset Z_k(M).
$$

The $k$th homology group is the quotient

$$
H_k(M;\mathbb Z)=Z_k(M)/B_k(M).
$$

A class in $H_k(M;\mathbb Z)$ is therefore a closed $k$-cycle, with the convention that cycles differing by a boundary are the same.

## What homology measures

The first few homology groups have useful physical meanings.

The group $H_0(M;\mathbb Z)$ counts connected components. If $M$ has $r$ path-connected components, then

$$
H_0(M;\mathbb Z)\simeq\mathbb Z^r.
$$

The group $H_1(M;\mathbb Z)$ measures loops modulo loops that bound surfaces. It is the abelianized version of the fundamental group when $M$ is path-connected:

$$
H_1(M;\mathbb Z)\simeq \pi_1(M)_{\mathrm{ab}}.
$$

This is why $H_1$ sees ordinary winding around holes, but it forgets nonabelian ordering information in the fundamental group.

The group $H_2(M;\mathbb Z)$ measures closed surfaces modulo surfaces that bound three-dimensional regions. Magnetic flux through a sphere around a monopole is naturally paired with such a class.

The top homology group of a connected compact orientable $d$-manifold is

$$
H_d(M;\mathbb Z)\simeq\mathbb Z.
$$

Its generator is the fundamental class $[M]$, the oriented manifold itself. Integrals over spacetime, instanton numbers, and topological actions often evaluate cohomology classes on this fundamental class.

For a connected compact nonorientable $d$-manifold, the top homology with integer coefficients vanishes:

$$
H_d(M;\mathbb Z)=0.
$$

But with $\mathbb Z_2$ coefficients there is still a mod-2 fundamental class. This is the first hint that coefficients are not a decorative detail. The coefficients decide which charges can be seen.

## Cochains, cocycles, and coboundaries

A $k$-cochain is a linear functional on $k$-chains. With coefficients in an abelian group $A$,

$$
C^k(M;A)=\operatorname{Hom}(C_k(M;\mathbb Z),A).
$$

The coboundary map

$$
\delta:C^k(M;A)\to C^{k+1}(M;A)
$$

is defined by

$$
(\delta\varphi)(c)=\varphi(\partial c).
$$

Since $\partial^2=0$, one gets

$$
\delta^2=0.
$$

A cocycle is a cochain killed by $\delta$:

$$
Z^k(M;A)=\ker\delta.
$$

A coboundary is a cochain of the form $\delta\lambda$:

$$
B^k(M;A)=\operatorname{im}\delta.
$$

The $k$th cohomology group is

$$
H^k(M;A)=Z^k(M;A)/B^k(M;A).
$$

The pairing between cochains and chains descends to a pairing between cohomology and homology because cocycles vanish on boundaries and coboundaries vanish on cycles.

This is the algebraic version of the differential-form statements from the summary. Differential forms are cochains that can be integrated over smooth chains.

## de Rham cohomology

For a smooth manifold, the exterior derivative gives the complex

$$
0\to\Omega^0(M)\xrightarrow{d}\Omega^1(M)\xrightarrow{d}\Omega^2(M)\xrightarrow{d}\cdots.
$$

The identity $d^2=0$ is the differential-form analogue of $\partial^2=0$. A $k$-form $\omega$ is closed if

$$
d\omega=0,
$$

and exact if

$$
\omega=d\alpha.
$$

The de Rham cohomology is

$$
H^k_{\mathrm{dR}}(M)=\frac{\ker(d:\Omega^k\to\Omega^{k+1})}{\operatorname{im}(d:\Omega^{k-1}\to\Omega^k)}.
$$

The de Rham theorem says that

$$
H^k_{\mathrm{dR}}(M)\simeq H^k(M;\mathbb R).
$$

The isomorphism is given by integration:

$$
\omega\longmapsto\left(\Sigma\mapsto\int_\Sigma\omega\right).
$$

This theorem is one of the great pieces of mathematical infrastructure behind QFT. It says that smooth differential forms can represent real cohomology classes, and their periods over cycles contain topological information.

A warning: de Rham cohomology uses real coefficients. It cannot see torsion. If a class has finite order, it vanishes after tensoring with $\mathbb R$. This is harmless in some perturbative calculations and disastrous in some global questions. Flat bundles, discrete theta angles, spin structures, and global anomalies often live partly or entirely in torsion data.

## Periods and normalization

A period of a closed $k$-form $\omega$ is an integral

$$
\int_\Sigma\omega
$$

over a closed $k$-cycle $\Sigma$. If $[\omega]\in H^k(M;\mathbb R)$ and $[\Sigma]\in H_k(M;\mathbb Z)$, then the period is the pairing

$$
\langle[\omega],[\Sigma]\rangle.
$$

In physics, one often normalizes forms so that their periods are integers. For example, a $U(1)$ gauge field on a line bundle has curvature $F$ satisfying

$$
\frac{1}{2\pi}\int_\Sigma F\in\mathbb Z
$$

for every closed two-cycle $\Sigma$, assuming the charged fields have minimal charge $1$ in the convention $D=d-iA$. The class

$$
\left[\frac{F}{2\pi}\right]
$$

is the real image of the first Chern class.

The factor $2\pi$ is not optional. It is what makes the exponentiated holonomy

$$
\exp\left(i\oint A\right)
$$

well defined and what makes flux quantization compatible with single-valued charged fields.

Topological terms use the same logic. A theta term is often written as

$$
S_\theta=i\theta Q
$$

in Euclidean signature, where $Q$ is an integer-valued topological charge. The periodicity

$$
\theta\sim\theta+2\pi
$$

comes from the integrality of $Q$, not from a small-field perturbative identity.

## Examples

The circle has

$$
H_0(S^1;\mathbb Z)\simeq\mathbb Z,
\qquad
H_1(S^1;\mathbb Z)\simeq\mathbb Z,
$$

and no higher homology. The generator of $H_1$ is the circle itself. In de Rham cohomology, a coordinate $\theta$ is not a globally defined real-valued function on $S^1$, but $d\theta$ is a globally defined closed one-form in the angular sense. With the normalized form

$$
\omega=\frac{d\theta}{2\pi},
$$

one has

$$
\int_{S^1}\omega=1.
$$

The two-sphere has

$$
H_0(S^2;\mathbb Z)\simeq\mathbb Z,
\qquad
H_2(S^2;\mathbb Z)\simeq\mathbb Z,
$$

and $H_1(S^2;\mathbb Z)=0$. A normalized area form $\omega$ satisfies

$$
\int_{S^2}\omega=1.
$$

A magnetic monopole background on $S^2$ has curvature $F$ with

$$
\frac{1}{2\pi}\int_{S^2}F=m\in\mathbb Z.
$$

The two-torus has

$$
H_0(T^2;\mathbb Z)\simeq\mathbb Z,
\qquad
H_1(T^2;\mathbb Z)\simeq\mathbb Z^2,
\qquad
H_2(T^2;\mathbb Z)\simeq\mathbb Z.
$$

If $x,y$ are angular coordinates with period $2\pi$, then

$$
\frac{dx}{2\pi},
\qquad
\frac{dy}{2\pi}
$$

are generators of $H^1(T^2;\mathbb R)$ in the de Rham description. The normalized two-form

$$
\frac{dx\wedge dy}{(2\pi)^2}
$$

has unit period over $T^2$.

The punctured plane

$$
\mathbb R^2\setminus\{0\}
$$

deformation-retracts onto $S^1$, so its $H_1$ is $\mathbb Z$. This is the topological reason a loop around the origin can carry winding or Aharonov–Bohm holonomy.

The punctured three-space

$$
\mathbb R^3\setminus\{0\}
$$

deformation-retracts onto $S^2$, so its $H_2$ is $\mathbb Z$. This is the topological reason a sphere surrounding a monopole is a nontrivial integration cycle.

## Conserved currents as cohomology classes

In $d$ spacetime dimensions, an ordinary conserved current $j^\mu$ obeys

$$
\partial_\mu j^\mu=0.
$$

Using the Hodge star, the associated $(d-1)$-form current is

$$
J=\star j.
$$

Current conservation becomes

$$
dJ=0.
$$

The charge on a spatial slice $\Sigma$ is

$$
Q_\Sigma=\int_\Sigma J.
$$

If $\Sigma$ and $\Sigma'$ are homologous and no charged operators lie between them, then

$$
Q_\Sigma=Q_{\Sigma'}.
$$

This is just Stokes’ theorem. If

$$
\Sigma'-\Sigma=\partial B,
$$

then

$$
Q_{\Sigma'}-Q_\Sigma=\int_{\partial B}J=\int_B dJ=0.
$$

This is the cohomological skeleton of charge conservation. The same idea generalizes to higher-form symmetries: a conserved $p$-form symmetry current is a closed $(d-p-1)$-form, and its charge is measured on a closed codimension-$(p+1)$ cycle.

## Fluxes and gauge fields

Gauge field strengths naturally define cohomology classes when normalized correctly. For a $U(1)$ gauge field with curvature $F=dA$ locally, the Bianchi identity is

$$
dF=0.
$$

Locally this says $F$ is closed. Globally, $A$ may not exist as a single one-form on all of $M$. The curvature $F$ is globally defined, and the periods of $F/2\pi$ over closed two-cycles are integers when the gauge field is a connection on a line bundle with unit electric charge.

Thus the cohomology class

$$
\left[\frac{F}{2\pi}\right]\in H^2(M;\mathbb R)
$$

is the real shadow of an integral class

$$
c_1(L)\in H^2(M;\mathbb Z).
$$

This is why one should be careful with the tempting formula $F=dA$. It is locally true on patches. Globally, nonzero flux through a closed cycle means there is no globally defined smooth potential $A$ on the whole space.

Nonabelian gauge fields have a related but richer story. Invariant polynomials in the curvature, such as

$$
\operatorname{tr}(F\wedge F),
$$

define closed forms. With the right normalization, their periods give characteristic numbers. Those belong to the characteristic-class pages, but the homology–cohomology pairing is already visible here.

## Poincaré duality and delta-form currents

On an oriented compact $d$-manifold, Poincaré duality pairs $k$-cycles with $(d-k)$-cohomology classes. If $\Sigma$ is an oriented closed $k$-dimensional submanifold of $M$, its Poincaré dual is a cohomology class

$$
\operatorname{PD}[\Sigma]\in H^{d-k}(M;\mathbb Z)
$$

characterized by

$$
\int_\Sigma \eta=\int_M \eta\wedge \operatorname{PD}[\Sigma]
$$

for closed $k$-forms $\eta$, up to the standard orientation signs determined by conventions.

Physicists often represent $\operatorname{PD}[\Sigma]$ by a delta-form current $\delta_\Sigma$ supported on $\Sigma$:

$$
\int_M \eta\wedge\delta_\Sigma=\int_\Sigma\eta.
$$

This notation is extremely useful for defects and branes. A Wilson line supported on a curve, a surface operator supported on a surface, or a magnetic defect supported on a submanifold can often be written using such distributional Poincaré dual forms.

The rule of thumb is

$$
\partial\Sigma=0 \quad\Longleftrightarrow\quad d\delta_\Sigma=0
$$

up to orientation conventions. If $\Sigma$ is itself a boundary, then its Poincaré dual is exact. This is again the same dictionary: cycles modulo boundaries become closed currents modulo exact currents.

## Relative homology and boundaries

Many QFT problems do not happen on closed manifolds. There may be a boundary, an asymptotic region, a defect worldvolume removed from spacetime, or boundary conditions imposed on a subspace $A\subset M$.

Relative homology $H_k(M,A)$ studies chains in $M$ whose boundaries are allowed to lie in $A$. This is the right language for a $k$-dimensional object that can end on a boundary or defect. The dual relative cohomology groups encode forms whose restrictions and gauge transformations satisfy matching conditions on $A$.

A simple physical example is an open Wilson line. In a theory with charged matter, a line operator can end on a charged local operator. The line by itself is not a closed cycle; the line plus endpoint data is the physically meaningful relative object.

Another example is a theta term on a manifold with boundary. A closed bulk form that differs by an exact form can change the boundary action by a Chern–Simons-like term. Ignoring relative cohomology here is how one creates fake paradoxes about gauge invariance. The boundary is not a footnote; it bites.

## Torsion and why de Rham forms miss it

A homology class $x\in H_k(M;\mathbb Z)$ is torsion if some nonzero integer multiple vanishes:

$$
nx=0,
\qquad n\ne0.
$$

Real differential forms cannot detect torsion cycles by integration, because

$$
H_k(M;\mathbb Z)\otimes\mathbb R
$$

forgets finite-order information. Yet torsion is physically real. It appears in flat connections, discrete gauge fields, discrete theta angles, spin structures, global anomalies, and phases of fermion determinants.

A flat $U(1)$ connection has $F=0$, so de Rham cohomology sees no curvature flux. But its holonomy around a torsion one-cycle may still be nontrivial. Similarly, a discrete gauge field may have no smooth field-strength representative while still changing the quantum theory.

A useful slogan is

$$
\text{de Rham cohomology sees curvature; integral and finite cohomology also see global quantization and torsion.}
$$

For many perturbative calculations, de Rham cohomology is enough. For global QFT, it often is not.

## Homology versus homotopy

Homotopy classifies maps. Homology classifies cycles. They are related but not interchangeable.

A loop in $M$ defines both an element of $\pi_1(M)$, if based, and an element of $H_1(M;\mathbb Z)$. Passing from $\pi_1$ to $H_1$ abelianizes. This means homology forgets the ordering of noncommuting loops.

For spheres and simple target spaces, homotopy can be the more direct defect classifier. For fluxes, charges, and integration cycles, homology and cohomology are often more natural. Characteristic classes live in cohomology, even when they classify objects that one can also describe by clutching maps and homotopy groups.

A good working rule is:

| Question | Natural first language |
|---|---|
| Can a map $S^n\to X$ be unwound? | Homotopy |
| Is this loop or surface a boundary? | Homology |
| Is this closed form globally exact? | Cohomology |
| Is this flux or theta term quantized? | Integral cohomology |
| Does this flat sector survive with zero curvature? | Torsion or finite cohomology |

## Common pitfalls

A cycle is not the same thing as a homology class. A cycle is a representative. A homology class is the representative modulo boundaries. Many calculations are clean only after checking that the answer does not depend on the representative.

Closed is not the same thing as exact. Every exact form is closed, but a closed form need not be exact globally. This is the whole reason cohomology exists.

A local potential does not imply a global potential. A curvature form can be locally $dA$ on every patch and still represent a nontrivial global cohomology class.

De Rham cohomology does not see torsion. If the question involves discrete gauge fields, spin structures, finite-group symmetry, global anomalies, or flat sectors, real forms may be too coarse.

A conserved current is not automatically a nontrivial cohomology class. If the current is exact, or if the integration cycle is a boundary with no insertions inside, the corresponding charge may vanish. Nontrivial topology and operator insertions both matter.

## Exercises

### Exercise 1: Periods vanish for exact forms

Let $\Sigma$ be a closed $k$-cycle and let $\omega=d\alpha$ be an exact $k$-form. Show that

$$
\int_\Sigma\omega=0.
$$

<details><summary><strong>Solution</strong></summary>

Using Stokes’ theorem,

$$
\int_\Sigma\omega=\int_\Sigma d\alpha=\int_{\partial\Sigma}\alpha.
$$

Since $\Sigma$ is closed,

$$
\partial\Sigma=0.
$$

Therefore

$$
\int_\Sigma\omega=0.
$$

This is why exact forms represent the zero class when integrated over closed cycles.

</details>

### Exercise 2: Homologous cycles give the same period

Let $\omega$ be a closed $k$-form and suppose two $k$-cycles obey

$$
\Sigma'-\Sigma=\partial B.
$$

Show that

$$
\int_{\Sigma'}\omega=\int_\Sigma\omega.
$$

<details><summary><strong>Solution</strong></summary>

Compute the difference:

$$
\int_{\Sigma'}\omega-\int_\Sigma\omega
=\int_{\Sigma'-\Sigma}\omega
=\int_{\partial B}\omega.
$$

By Stokes’ theorem,

$$
\int_{\partial B}\omega=\int_B d\omega.
$$

Since $\omega$ is closed, $d\omega=0$, hence

$$
\int_{\Sigma'}\omega=\int_\Sigma\omega.
$$

So the integral depends only on the homology class $[\Sigma]$ and the cohomology class $[\omega]$.

</details>

### Exercise 3: The two-torus periods

Let $T^2$ have angular coordinates $x,y$ with period $2\pi$. Define

$$
\alpha=\frac{dx}{2\pi},
\qquad
\beta=\frac{dy}{2\pi}.
$$

Let $a$ be the cycle with $x$ varying and $y$ fixed, and let $b$ be the cycle with $y$ varying and $x$ fixed. Compute the periods of $\alpha$ and $\beta$ over $a$ and $b$.

<details><summary><strong>Solution</strong></summary>

On the $a$-cycle, $x$ runs from $0$ to $2\pi$ and $y$ is constant. Therefore

$$
\int_a\alpha=\frac{1}{2\pi}\int_0^{2\pi}dx=1,
\qquad
\int_a\beta=0.
$$

On the $b$-cycle, $y$ runs from $0$ to $2\pi$ and $x$ is constant. Therefore

$$
\int_b\alpha=0,
\qquad
\int_b\beta=\frac{1}{2\pi}\int_0^{2\pi}dy=1.
$$

Thus $\alpha$ and $\beta$ are dual to the two basic one-cycles of the torus.

</details>

### Exercise 4: Monopole flux as a cohomology pairing

Let $F$ be a closed two-form on $\mathbb R^3\setminus\{0\}$ satisfying

$$
\frac{1}{2\pi}\int_{S^2}F=m
$$

on a sphere surrounding the origin. Explain why the same value is obtained on any other sphere surrounding the origin.

<details><summary><strong>Solution</strong></summary>

Any two spheres surrounding the origin represent the same generator of

$$
H_2(\mathbb R^3\setminus\{0\};\mathbb Z)\simeq\mathbb Z.
$$

Equivalently, the region between the two spheres is a three-chain $B$ in the punctured space whose boundary is the difference of the two spheres, with orientation signs:

$$
S^2_2-S^2_1=\partial B.
$$

Since $dF=0$ away from the origin,

$$
\int_{S^2_2}F-\int_{S^2_1}F=\int_{\partial B}F=\int_B dF=0.
$$

So the flux is a pairing of the cohomology class $[F/2\pi]$ with the homology class of the surrounding sphere. It changes only if the sphere crosses a magnetic source or if the background fails to be closed in the region between the spheres.

</details>

## Relations to other pages

This page follows [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) and gives the cycle-and-form language needed for [Winding Numbers](/math-toolkit/topology-cohomology-characteristic-classes/winding-numbers/). Homotopy tells you when a map cannot be unwound; homology and cohomology tell you how to integrate closed forms over nontrivial cycles and obtain invariant numbers.

For the calculus behind the de Rham side, see [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For the gauge-field version, see [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/).

The later characteristic-class pages will use this page constantly. Chern classes, Stiefel–Whitney classes, Pontryagin classes, and index densities are all cohomology classes or refinements of cohomology classes.

## Research status

The definitions and the de Rham theorem are established mathematical foundations. The active frontier in QFT is not whether homology and cohomology exist; it is which refinement of them the quantum theory needs. Integral cohomology is necessary for quantization. Torsion matters for flat sectors and discrete phases. Differential cohomology keeps both curvature and holonomy. Generalized cohomology and cobordism enter modern classifications of anomalies, invertible phases, and global consistency conditions.

A safe workflow is: use de Rham forms for local curvature and perturbative formulas, then check whether the global question requires integer lifts, torsion data, relative groups, or differential refinements.

## References

- A. Hatcher, *Algebraic Topology*. Standard reference for singular homology, cohomology, exact sequences, and the relation to homotopy.
- R. Bott and L. W. Tu, *Differential Forms in Algebraic Topology*. Classic reference for de Rham cohomology, Poincaré duality, and the bridge between forms and topology.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented treatment of homology, cohomology, characteristic classes, monopoles, instantons, and gauge fields.
- T. Frankel, *The Geometry of Physics*. Useful geometric treatment of differential forms, integration, Poincaré duality, bundles, and physical applications.
- S. Coleman, *Aspects of Symmetry*. Useful for solitons, topological conservation laws, and the physical role of global sectors.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for topology in gauge theory, compact gauge fields, vortices, monopoles, instantons, and related QFT effects.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for the QFT side of currents, gauge fields, anomalies, and topological terms.

## Version history

- **2026-06-25:** Initial polished draft. Defined chains, cycles, boundaries, homology, cochains, cohomology, de Rham cohomology, periods, flux quantization, Poincaré dual currents, relative homology, torsion, examples, and QFT applications.
