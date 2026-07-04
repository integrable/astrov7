---
title: "Čech Cohomology Preview"
description: "Introduces Čech cohomology as the bookkeeping of local patching data and explains how transition functions, gauge transformations, bundles, gerbes, and fluxes arise from overlaps."
sidebar:
  label: "Čech Cohomology Preview"
  order: 6
level: Advanced
status: "Polished draft"
source: "Standard topology, sheaf cohomology, and gauge-geometry references, including Bott–Tu, Hatcher, Nakahara, Frankel, Brylinski, and physics treatments of bundles, monopoles, gerbes, and differential cohomology."
topics:
  - Cech cohomology
  - open covers
  - cocycles
  - coboundaries
  - transition functions
  - line bundles
  - principal bundles
  - gauge transformations
  - gerbes
  - differential cohomology
canonicalTopics:
  - cech-cohomology
  - open-cover
  - cocycle
  - coboundary
  - transition-function
  - line-bundle
  - principal-bundle
  - gauge-transformation
  - gerbe
  - differential-cohomology
researchStatus:
  established:
    - "Čech cohomology is a standard way to encode global topological data by local data on an open cover and compatibility conditions on overlaps."
  active:
    - "Modern QFT often needs refined versions: sheaf cohomology, Deligne cohomology, differential cohomology, higher stacks, equivariant refinements, and generalized cohomology."
---

## Summary

Čech cohomology is the topology of **patching**. Instead of describing a global object all at once, one covers a manifold $M$ by open sets

$$
\mathcal U=\{U_i\}_{i\in I},
$$

describes local data on each $U_i$, and then records how those local descriptions are glued on overlaps

$$
U_{ij}=U_i\cap U_j,
\qquad
U_{ijk}=U_i\cap U_j\cap U_k,
\qquad \ldots
$$

The first place this becomes unavoidable in QFT is gauge theory. A gauge potential may be defined only locally. On overlaps, two local potentials are related by a gauge transformation. On triple overlaps, those gauge transformations must satisfy a compatibility condition. The compatibility class is global topology hiding in local notation.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing an open cover, local data on patches, overlap transition functions, triple-overlap cocycles, changes of trivialization, a Čech cohomology class, and QFT uses such as bundles, fluxes, spin lifts, and gerbes.](/figures/math-toolkit/cech-cohomology-patching.svg)

<figcaption>

Čech cohomology turns local patching rules into global classes. For bundles, the basic data are transition functions $g_{ij}$ on overlaps, with a cocycle condition on triple overlaps and an equivalence relation from changing local trivializations.

</figcaption>
</figure>

The slogan is

$$
\text{local data} + \text{overlap consistency} \quad \Longrightarrow \quad \text{global topology}.
$$

This page is a preview because full Čech theory quickly becomes sheaf cohomology. For many QFT purposes, though, the working idea is simple: gauge fields, line bundles, spin structures, gerbes, flux quantization, and anomaly backgrounds are often best understood by asking what data live on patches, overlaps, triple overlaps, and higher intersections.

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) for local trivializations and transition functions. Read [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) for the gauge-theory dictionary, and [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for closed forms modulo exact forms.

You should also know the basic language of [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/): cochains, cocycles, coboundaries, and the idea that cohomology is a quotient of closed-like objects by exact-like objects.

For the next step after this page, read [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/), where the patching data of bundles becomes cohomology classes measured by curvature.

## Core idea

Suppose a global object is easy to describe locally but hard, or impossible, to describe with a single global formula. A Čech description starts by choosing an open cover

$$
M=\bigcup_i U_i.
$$

A local field, section, gauge potential, phase choice, or trivialization is specified on each patch. The nontrivial information appears on overlaps. If $U_i$ and $U_j$ both describe the same object, then their local descriptions must be related by transition data on

$$
U_{ij}=U_i\cap U_j.
$$

For a vector bundle or principal bundle, this transition data is a map

$$
g_{ij}:U_{ij}\to G,
$$

where $G$ is the structure group. On a triple overlap $U_{ijk}$, going from patch $i$ to $j$, then $j$ to $k$, then $k$ back to $i$ must give the identity:

$$
g_{ij}g_{jk}g_{ki}=1.
$$

This is the **cocycle condition**.

Different choices of local trivialization should describe the same global bundle. If $h_i:U_i\to G$ changes the local trivialization on $U_i$, then, with the convention used here,

$$
g_{ij}\sim g'_{ij}=h_i g_{ij} h_j^{-1}.
$$

This is the **coboundary equivalence**. A Čech cohomology class is precisely what remains after imposing overlap consistency and quotienting by local redefinitions.

For Abelian coefficients, this literally forms a cohomology group. For non-Abelian transition functions, the degree-one object is usually a pointed set rather than a group. That annoyance is not pedantry; it is why non-Abelian bundles are subtler than line bundles.

## Open covers and intersections

Let $\mathcal U=\{U_i\}$ be an open cover of $M$. For indices $i_0,\ldots,i_p$, define the multiple intersection

$$
U_{i_0\cdots i_p}=U_{i_0}\cap\cdots\cap U_{i_p}.
$$

Čech $p$-cochains are assignments of data to $p$-fold overlaps, meaning intersections of $p+1$ open sets. The shift by one is annoying at first and then becomes natural:

| degree | where the data live | typical meaning |
|---:|---|---|
| $0$ | $U_i$ | local choices, local gauges, local functions |
| $1$ | $U_{ij}$ | transition functions, differences of local potentials |
| $2$ | $U_{ijk}$ | gerbe cocycles, obstruction data, associativity defects |
| $p$ | $U_{i_0\cdots i_p}$ | higher patching data |

For an Abelian coefficient group $A$, a Čech $p$-cochain may be written additively as

$$
c_{i_0\cdots i_p}\in A(U_{i_0\cdots i_p}),
$$

where $A(U)$ means the allowed coefficient data on $U$. If $A$ is the constant group $\mathbb Z$, then $A(U)$ is locally constant integer-valued functions. If $A$ is the sheaf of smooth $U(1)$-valued functions, then $A(U)=C^\infty(U,U(1))$.

The cover is often taken to be a **good cover**, meaning every nonempty finite intersection $U_{i_0\cdots i_p}$ is contractible. Good covers are valuable because they separate local analysis from global topology. On a contractible patch, bundles are trivial and closed forms are exact; therefore any surviving obstruction must come from how the patches glue.

## The Čech coboundary

For Abelian coefficients written additively, the Čech coboundary is

$$
(\delta c)_{i_0\cdots i_{p+1}}
=\sum_{r=0}^{p+1}(-1)^r c_{i_0\cdots \widehat{i_r}\cdots i_{p+1}},
$$

where the hat means the index is omitted. This operator satisfies

$$
\delta^2=0.
$$

Therefore one defines

$$
\check Z^p(\mathcal U,A)=\ker\left(\delta:C^p(\mathcal U,A)\to C^{p+1}(\mathcal U,A)\right),
$$

$$
\check B^p(\mathcal U,A)=\operatorname{im}\left(\delta:C^{p-1}(\mathcal U,A)\to C^p(\mathcal U,A)\right),
$$

and

$$
\check H^p(\mathcal U,A)=\frac{\check Z^p(\mathcal U,A)}{\check B^p(\mathcal U,A)}.
$$

A $p$-cocycle is a cochain satisfying $\delta c=0$. A $p$-coboundary is a cochain of the form $c=\delta b$. The quotient says that a globally meaningful class is a consistent overlap assignment modulo changes of lower-degree local choices.

This mirrors de Rham cohomology:

$$
\text{closed forms modulo exact forms}
\quad\longleftrightarrow\quad
\text{Čech cocycles modulo Čech coboundaries}.
$$

The two languages often compute the same real cohomology when the cover is good, but they remember different features. De Rham forms are excellent for curvature and local densities. Čech cocycles are excellent for patching, integral data, and transition functions.

## Degree zero: locally constant data

Start with the simplest case: a $0$-cochain assigns data $c_i$ to each open set $U_i$. Its coboundary is a $1$-cochain on overlaps:

$$
(\delta c)_{ij}=c_j-c_i.
$$

A $0$-cocycle satisfies

$$
c_i=c_j
$$

on every nonempty overlap $U_{ij}$. Thus the local data agree across overlaps and define a global object. For constant coefficients, $\check H^0(M,A)$ is the group of locally constant $A$-valued functions on $M$. If $M$ is connected, this is just $A$.

This is the baby version of patching. Degree zero asks whether local constants actually glue to a global constant. Higher degrees ask whether overlap data glue consistently, and whether they can be removed by redefining local data.

## Degree one: transition functions and line bundles

The first genuinely geometric degree is degree one. Let $L\to M$ be a complex line bundle. Choose a local trivialization on each $U_i$. On an overlap $U_{ij}$, the two trivializations differ by a nowhere-zero complex function. For a Hermitian line bundle, one may take

$$
g_{ij}:U_{ij}\to U(1).
$$

These functions obey

$$
g_{ii}=1,
\qquad
g_{ji}=g_{ij}^{-1},
\qquad
\text{and}\qquad
g_{ij}g_{jk}g_{ki}=1
$$

on triple overlaps.

The last equation is the cocycle condition. It says that if a local representative $s_i$ is related to $s_j$ by

$$
s_i=g_{ij}s_j,
$$

then going around a triple overlap returns the same local vector:

$$
s_i=g_{ij}s_j=g_{ij}g_{jk}s_k=g_{ij}g_{jk}g_{ki}s_i.
$$

Now change the trivialization on each patch by $h_i:U_i\to U(1)$. Then

$$
g_{ij}\sim g'_{ij}=h_i g_{ij}h_j^{-1}.
$$

This is the coboundary equivalence. Therefore line bundles are classified, in this language, by $U(1)$-valued Čech one-cocycles modulo zero-cochains.

For principal $G$-bundles, the same story uses transition functions $g_{ij}:U_{ij}\to G$. If $G$ is non-Abelian, the cocycle condition still makes sense, but the quotient is no longer an Abelian cohomology group. It is the non-Abelian Čech classification of principal bundles.

## Gauge transformations as coboundaries

Čech cohomology clarifies a sentence physicists say all the time: “This is just a gauge transformation.”

A gauge transformation is not merely a function on one global patch. On a nontrivial bundle, it is local data compatible with the transition functions. If we are comparing two descriptions of the same bundle, changing local trivializations by $h_i$ changes transition functions by

$$
g_{ij}\mapsto h_i g_{ij}h_j^{-1}.
$$

This change does not change the bundle class. It is a coboundary-type redefinition.

For Abelian $U(1)$ transition functions written multiplicatively, if

$$
g_{ij}=e^{i\lambda_{ij}},
$$

then changing local phases $h_i=e^{i\alpha_i}$ gives

$$
\lambda_{ij}\mapsto \lambda_{ij}+\alpha_i-\alpha_j
$$

up to integer multiples of $2\pi$. This is the Čech version of the gauge transformation of phases.

The word “just” hides a lot. A local gauge transformation may remove local data, but a nontrivial Čech class cannot be removed by any collection of local redefinitions. That is how a monopole can have no global nonsingular vector potential even though each patch looks harmless.

## The Dirac monopole as patching data

The Dirac monopole on $S^2$ is the classic example. Cover $S^2$ by a northern patch $U_N$ and a southern patch $U_S$. Each patch admits a local vector potential. On the overlap, an annulus around the equator, the two potentials differ by a gauge transformation.

In one common geometric normalization, the transition function is

$$
g_{NS}(\phi)=e^{in\phi},
\qquad n\in\mathbb Z,
$$

where $\phi$ is the azimuthal angle on the equator. Single-valuedness requires

$$
g_{NS}(\phi+2\pi)=g_{NS}(\phi),
$$

so $n$ must be an integer. The integer $n$ is the first Chern number of the line bundle:

$$
\frac{1}{2\pi}\int_{S^2}F=n,
$$

up to the sign convention relating the geometric connection to the physics gauge potential.

This is one of the cleanest examples of the Čech–de Rham bridge:

$$
\text{transition function winding on }U_N\cap U_S
\quad\longleftrightarrow\quad
\text{curvature flux through }S^2.
$$

The local potentials do not make the topology disappear. They move it into the overlap function.

## Čech–de Rham dictionary

The de Rham description and the Čech description are two complementary coordinate systems on the same global phenomenon.

In de Rham language, a closed form represents a class:

$$
[\omega]\in H^p_{\mathrm{dR}}(M).
$$

In Čech language, local primitives and their differences on overlaps form a cocycle. For example, suppose a closed one-form $\omega$ is locally exact on a good cover:

$$
\omega|_{U_i}=df_i.
$$

On overlaps,

$$
d(f_j-f_i)=0,
$$

so

$$
f_j-f_i
$$

is locally constant on $U_{ij}$. These constants form a Čech one-cocycle with coefficients in $\mathbb R$. Its class is another representation of the same real cohomology class as $\omega$.

For a $U(1)$ gauge field, local connection one-forms $A_i$ satisfy on overlaps

$$
A_i=A_j+\text{gauge transformation term}.
$$

The curvature

$$
F_i=dA_i
$$

agrees across overlaps and therefore defines a global two-form $F$. The transition functions remember the integral periods of $F$, while the curvature form supplies a de Rham representative of the corresponding real class.

A rough dictionary is:

| Čech data | de Rham data | physics reading |
|---|---|---|
| local functions $f_i$ | global closed one-form $\omega$ | phases, holonomies |
| transition functions $g_{ij}$ | curvature two-form $F$ | line bundles, magnetic flux |
| two-cocycles on triple overlaps | closed three-form $H$ | gerbes, $B$-fields |
| higher cocycles | higher field strengths | higher-form gauge backgrounds |

The word “rough” matters. Integral periods, torsion, and differential refinements are invisible to plain real de Rham cohomology. Čech methods are often the doorway to those refinements.

## Higher patching and gerbes

Line bundles use transition functions on double overlaps:

$$
g_{ij}:U_{ij}\to U(1).
$$

Gerbes shift the story up by one degree. A $U(1)$ gerbe has local two-form potentials $B_i$ on patches, one-form gauge transformations $\Lambda_{ij}$ on double overlaps, and $U(1)$-valued functions $g_{ijk}$ on triple overlaps. The triple-overlap data obey a cocycle condition on quadruple overlaps.

Schematically,

$$
B_i-B_j=d\Lambda_{ij},
$$

$$
\Lambda_{ij}+\Lambda_{jk}+\Lambda_{ki}=g_{ijk}^{-1}dg_{ijk}\quad\text{up to convention-dependent factors},
$$

and

$$
(\delta g)_{ijkl}=1.
$$

The curvature is a global closed three-form

$$
H=dB_i,
$$

with quantized periods in the properly normalized theory. This is the patching language behind Kalb–Ramond fields, Wess–Zumino terms, higher-form gauge fields, and many anomaly-inflow constructions.

Again, the important idea is not the exact sign in the displayed convention. The important idea is the ladder:

$$
\text{patch data}\to\text{overlap data}\to\text{higher-overlap data}\to\text{global class}.
$$

## Good covers and why refinements matter

On a good cover, Čech cohomology with constant coefficients computes ordinary cohomology:

$$
\check H^p(\mathcal U,A)\simeq H^p(M;A)
$$

for suitable coefficient groups $A$. This is why good covers are so useful: they let one compute topology using combinatorics of overlaps.

But QFT frequently needs more than ordinary cohomology. Here are common refinements:

| refinement | why QFT cares |
|---|---|
| sheaf cohomology | local-to-global problems for functions, sections, holomorphic data, gauge transformations |
| integral cohomology | flux quantization, Chern classes, theta periodicity |
| differential cohomology | simultaneous tracking of integral classes, differential forms, and holonomies |
| Deligne cohomology | geometric model for line bundles, gerbes, connections, and higher gauge fields |
| equivariant cohomology | symmetry backgrounds, localization, gauging global symmetries |
| non-Abelian cohomology | principal $G$-bundles and their transition functions |
| higher stacks | higher bundles, fields with gauge-for-gauge redundancy, modern global backgrounds |

The practical lesson is simple: if a field is locally described by potentials and gauge transformations, then the globally correct object is usually not the potential alone. It is a differential cohomology-type object containing a characteristic class, a curvature form, and holonomy data.

## QFT examples

**Line bundles and charged fields.** A charged scalar field in a background $U(1)$ gauge field is not globally just a complex-valued function. It is a section of a line bundle. The transition functions of the line bundle tell local wavefunctions how to transform across patch overlaps.

**Magnetic monopoles.** A monopole background cannot be described by one smooth vector potential on all of $S^2$. The Čech transition function on the equator has integer winding, and the curvature has quantized flux.

**Theta terms.** Terms such as

$$
\int_M F\wedge F
$$

are often written using curvature forms, but their quantization and periodicity depend on the integral characteristic class represented by that curvature expression.

**Spin structures.** A spin structure is a lift of the oriented orthonormal frame bundle from $SO(n)$ to $Spin(n)$. In Čech language, one asks whether $SO(n)$ transition functions can be lifted consistently to $Spin(n)$ transition functions. The obstruction is the second Stiefel–Whitney class.

**Gerbes and higher-form gauge fields.** A two-form gauge potential $B$ is locally a two-form, but globally it is described by higher patching data. Its field strength $H$ is a global closed three-form with quantized periods in properly normalized theories.

**Anomaly inflow.** Many anomaly formulas are most compactly written using characteristic forms. The global consistency of anomaly cancellation, however, depends on integral or differential refinements. Čech language keeps track of the patching data that local differential forms alone can miss.

## Common pitfalls

**Thinking every local potential is a global form.** A gauge potential $A_i$ may exist only on $U_i$. The curvature may glue to a global form even when the potential does not.

**Confusing a representative with a class.** A set of transition functions $g_{ij}$ is a representative. Changing trivializations changes $g_{ij}$ but not the bundle class.

**Forgetting triple overlaps.** Pairwise gluing is not enough. A bundle is not specified by arbitrary functions on double overlaps; they must satisfy a cocycle condition on triple overlaps.

**Treating non-Abelian degree-one Čech data as an Abelian group.** Principal $G$-bundles for non-Abelian $G$ are classified by non-Abelian one-cocycles modulo equivalence, but this classification is not generally a cohomology group.

**Using de Rham cohomology when torsion matters.** De Rham cohomology uses real coefficients and cannot see torsion. Discrete fluxes, spin structures, some global anomalies, and finite-group backgrounds require integral, mod-$n$, or generalized refinements.

**Ignoring the cover.** Čech cocycles are written relative to a cover. The invariant object is obtained after passing to refinements, good covers, or sheaf cohomology. A bad cover can obscure the topology.

**Mixing sign conventions for gauge transformations.** Whether $A_i=A_j+d\lambda_{ij}$ or $A_i=A_j-d\lambda_{ij}$ depends on whether the covariant derivative is $d+iA$ or $d-iA$. The Čech class is invariant; the displayed local formula must match the convention.

## Exercises

### Exercise 1: Check that the Čech coboundary squares to zero

For an Abelian coefficient group written additively, show that

$$
\delta^2=0.
$$

<details><summary><strong>Solution</strong></summary>

Let $c$ be a $p$-cochain. Then

$$
(\delta c)_{i_0\cdots i_{p+1}}
=\sum_{r=0}^{p+1}(-1)^r c_{i_0\cdots \widehat{i_r}\cdots i_{p+1}}.
$$

Applying $\delta$ again gives a double alternating sum in which two indices are omitted. Every term omitting indices $i_r$ and $i_s$ appears exactly twice: once omitting $i_r$ first and $i_s$ second, and once in the opposite order. The two appearances have opposite signs. Therefore all terms cancel in pairs:

$$
\delta^2 c=0.
$$

This is the Čech analogue of $d^2=0$ for differential forms.

</details>

### Exercise 2: Transition functions under a change of trivialization

Suppose local representatives satisfy

$$
s_i=g_{ij}s_j
$$

on $U_{ij}$. Define new local representatives by

$$
s_i'=h_i s_i,
$$

where $h_i:U_i\to G$. Show that the transition functions become

$$
g'_{ij}=h_i g_{ij}h_j^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

We need $s_i'=g'_{ij}s_j'$. Using the definitions,

$$
s_i'=h_i s_i=h_i g_{ij}s_j.
$$

Since $s_j'=h_j s_j$, we have

$$
s_j=h_j^{-1}s_j'.
$$

Thus

$$
s_i'=h_i g_{ij}h_j^{-1}s_j'.
$$

Therefore

$$
g'_{ij}=h_i g_{ij}h_j^{-1}.
$$

For Abelian $G$, this reduces to multiplying $g_{ij}$ by a Čech coboundary.

</details>

### Exercise 3: A transition function on the equator

Let $S^2$ be covered by northern and southern patches. On their overlap, suppose a $U(1)$ line bundle has transition function

$$
g_{NS}(\phi)=e^{in\phi}.
$$

Show that single-valuedness requires $n\in\mathbb Z$, and compute the winding number of $g_{NS}:S^1\to U(1)$.

<details><summary><strong>Solution</strong></summary>

The angle $\phi$ and $\phi+2\pi$ describe the same point on the equator. Therefore

$$
g_{NS}(\phi+2\pi)=g_{NS}(\phi)
$$

requires

$$
e^{in(\phi+2\pi)}=e^{in\phi},
$$

or

$$
e^{2\pi i n}=1.
$$

Hence

$$
n\in\mathbb Z.
$$

The winding number is

$$
\frac{1}{2\pi i}\oint_{S^1}g_{NS}^{-1}dg_{NS}
=\frac{1}{2\pi i}\int_0^{2\pi} e^{-in\phi}(in e^{in\phi})\,d\phi
=n.
$$

This integer is the Čech transition-function version of the monopole charge.

</details>

### Exercise 4: Local primitives of a closed one-form

Let $\omega$ be a closed one-form on $M$, and let $\mathcal U$ be a good cover. Suppose

$$
\omega|_{U_i}=df_i.
$$

Show that $f_j-f_i$ is locally constant on $U_{ij}$ and satisfies the Čech one-cocycle condition.

<details><summary><strong>Solution</strong></summary>

On $U_{ij}$,

$$
d(f_j-f_i)=df_j-df_i=\omega-\omega=0.
$$

Thus $f_j-f_i$ is locally constant on each connected component of $U_{ij}$.

On a triple overlap,

$$
(f_j-f_i)+(f_k-f_j)+(f_i-f_k)=0.
$$

Therefore the collection

$$
c_{ij}=f_j-f_i
$$

is a Čech one-cocycle with locally constant real coefficients.

</details>

## Relations to other pages

This page is the patching-data companion to [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/). De Rham cohomology emphasizes closed differential forms and periods; Čech cohomology emphasizes local data, overlaps, and transition functions.

The geometry background is in [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/). The spin-geometry application is in [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/).

The next page, [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/), explains how the global classes encoded by patching data can be represented by curvature polynomials and used in QFT.

## Research status

The basic Čech description of bundles, cohomology, and local-to-global patching is established. The active and delicate part in QFT is choosing the correct refinement for the problem at hand. Ordinary Čech cohomology may be insufficient when the theory includes differential-form gauge fields, higher-form symmetries, finite-group backgrounds, spin or Pin structures, torsion, defects, boundaries, stacks, or anomaly inflow.

A safe rule is: if a formula involves local gauge potentials, transition functions, holonomies, or quantized periods, ask whether the correct mathematical object is a bundle with connection, a gerbe with connection, or a differential cohomology class rather than just a differential form.

## References

- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. Standard reference for the Čech–de Rham relationship, good covers, and differential-form models of topology.
- A. Hatcher, *Algebraic Topology*. Useful background on ordinary cohomology, good covers, and the relation between geometric pictures and algebraic invariants.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented reference for bundles, transition functions, monopoles, characteristic classes, and gauge fields.
- T. Frankel, *The Geometry of Physics*. Geometric reference for forms, bundles, gauge fields, and the physical meaning of patching data.
- J.-L. Brylinski, *Loop Spaces, Characteristic Classes and Geometric Quantization*. Reference for gerbes, Deligne cohomology, line bundles with connection, and holonomy refinements.
- D. S. Freed, *Classical Chern–Simons Theory, Part 1*. A useful entry point for differential cohomology ideas in gauge theory and topological terms.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, *Generalized Global Symmetries*. Modern physics motivation for higher-form backgrounds and higher-codimension operators.

## Version history

- **2026-06-25:** Initial polished draft. Introduced Čech cochains, cocycles, coboundaries, good covers, transition functions, gauge transformations as coboundaries, the Dirac monopole, the Čech–de Rham bridge, gerbes, QFT examples, common pitfalls, and exercises.
