---
title: "Fiber Bundles"
description: "Defines fiber bundles, local trivializations, transition functions, sections, vector bundles, principal bundles, associated bundles, and their role as the global language of fields and gauge theory."
sidebar:
  label: "Fiber Bundles"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard geometry-for-physics references, including Nakahara, Frankel, Steenrod, Kobayashi–Nomizu, and QFT treatments of gauge fields, matter bundles, monopoles, and instantons."
topics:
  - fiber bundles
  - vector bundles
  - principal bundles
  - associated bundles
  - sections
  - transition functions
  - gauge transformations
  - local trivializations
  - fields as sections
canonicalTopics:
  - fiber-bundle
  - vector-bundle
  - principal-bundle
  - associated-bundle
  - section-of-a-bundle
  - transition-function
  - local-trivialization
  - gauge-trivialization
researchStatus:
  established:
    - "Smooth fiber bundles, vector bundles, principal bundles, associated bundles, transition functions, and sections are standard geometric structures underlying modern gauge theory and field theory."
  active:
    - "Modern QFT often refines ordinary bundle language using higher bundles, gerbes, differential cohomology, stacky quotients, defects, generalized symmetries, and global forms of gauge groups."
---

## Summary

A fiber bundle is a space that looks locally like a product but may be globally twisted. The base is the space of points, usually spacetime or a spatial manifold. The fiber is the kind of object attached to each point: a vector space, a group, a sphere, a projective space, a spinor module, or some other geometric space. The bundle remembers how these fibers are glued from patch to patch.

The basic data are a smooth map

$$
\pi:E\to M,
$$

where $M$ is the base, $E$ is the total space, and the fiber over $x\in M$ is

$$
E_x=\pi^{-1}(x).
$$

Locally, on a patch $U\subset M$, a fiber bundle has a trivialization

$$
\pi^{-1}(U)\cong U\times F,
$$

but on an overlap $U_i\cap U_j$ two local product descriptions can be related by a nontrivial transition function

$$
g_{ij}:U_i\cap U_j\to G.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![Diagram showing a base manifold covered by patches, fibers above points, local product trivializations, transition functions on overlaps, cocycle compatibility, associated bundles, and fields as sections.](/figures/math-toolkit/fiber-bundle-local-trivializations.svg)

<figcaption>

A fiber bundle is locally $U\times F$ but globally glued by transition functions $g_{ij}$. A field is often a section $s:M\to E$, meaning that it chooses one point in the fiber above each base point. Gauge theory is the case where the gluing data are not optional bookkeeping but part of the physical specification of the theory.

</figcaption>
</figure>

A field configuration is often a section

$$
s:M\to E,
\qquad
\pi\circ s=\operatorname{id}_M.
$$

This sentence quietly contains a lot of QFT. A scalar field is a section of a trivial line bundle. A charged field is a section of a vector bundle associated to a principal gauge bundle. A spinor field is a section of a spinor bundle, which exists only when the manifold admits the necessary spin structure. A gauge field is not itself just a global one-form in general; it is a connection on a principal bundle.

The point of bundle language is not to make local calculations harder. It is to say exactly what the local formulas are formulas *for*.

## Prerequisites

Read [Manifolds](/math-toolkit/geometry-of-fields/manifolds/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/), and [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/) first. You should also know the basic group language in [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/).

This page prepares for [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), holonomy, gauge fields as connections, characteristic classes, spin structures, Dirac operators, anomalies, instantons, monopoles, and global forms of gauge theory.

## Core idea

The slogan is:

$$
\text{a bundle is a continuously varying family of spaces over a base.}
$$

For every point $x\in M$, the fiber $E_x$ is the space of possible internal values at $x$. In local coordinates and a local frame, this can look completely ordinary. A charged scalar might look like a complex-valued function $\phi(x)$. A spinor might look like a column vector $\psi_\alpha(x)$. A Yang–Mills gauge potential might look like a Lie-algebra-valued one-form $A_\mu^a(x)T^a dx^\mu$.

The trap is that those are local descriptions. On a second patch, the same field may be represented by different components, related by a transition function. The geometric object is not the list of local functions separately. It is the local functions plus their gluing rules.

The important distinction is:

$$
\text{locally trivial}\neq\text{globally trivial}.
$$

Every smooth bundle is trivial over sufficiently small patches. A bundle is globally trivial only if those patches can be glued so that the entire total space is globally isomorphic to $M\times F$. The failure of this to happen is what produces winding numbers, monopole charge, instanton number, nontrivial Wilson line sectors, spin-structure dependence, and many other global effects.

Bundles are how QFT says: local physics can be ordinary while global physics is not.

## Fiber bundle data

A smooth fiber bundle with typical fiber $F$ consists of smooth manifolds $E$ and $M$ together with a smooth surjective map

$$
\pi:E\to M
$$

such that every point $x\in M$ has an open neighborhood $U$ for which there is a diffeomorphism

$$
\varphi_U:\pi^{-1}(U)\to U\times F
$$

compatible with projection to $U$:

$$
\operatorname{pr}_1\circ\varphi_U=\pi.
$$

This compatibility says that if $p\in E$ lies over $x$, then the local product chart sends it to

$$
\varphi_U(p)=(x,f)
$$

for some $f\in F$. The first coordinate is fixed by the base point. The second coordinate is the local fiber coordinate.

The standard words are:

| Object | Meaning |
|---|---|
| $M$ | base manifold |
| $E$ | total space |
| $F$ | typical fiber |
| $\pi:E\to M$ | projection |
| $E_x=\pi^{-1}(x)$ | fiber over $x$ |
| $\varphi_U$ | local trivialization |
| $s:M\to E$ | section, if $\pi\circ s=\operatorname{id}_M$ |

The local product $U\times F$ is not extra structure attached once and for all. It is a choice of coordinates on the bundle over a patch. Different choices are related by transition functions.

## Transition functions

Let $\{U_i\}$ be an open cover of $M$. Suppose each $U_i$ has a local trivialization

$$
\varphi_i:\pi^{-1}(U_i)\to U_i\times F.
$$

On an overlap $U_i\cap U_j$, there are two product descriptions of the same bundle point. The transition map is

$$
\varphi_i\circ\varphi_j^{-1}:(U_i\cap U_j)\times F\to (U_i\cap U_j)\times F.
$$

For a bundle with structure group $G$ acting on the fiber $F$ from the left, this transition map has the form

$$
\varphi_i\circ\varphi_j^{-1}(x,f)=(x,g_{ij}(x)f),
$$

where

$$
g_{ij}:U_i\cap U_j\to G.
$$

The maps $g_{ij}$ must obey the cocycle conditions

$$
g_{ii}=e,
\qquad
g_{ij}=g_{ji}^{-1},
\qquad
g_{ij}g_{jk}=g_{ik}
$$

on triple overlaps $U_i\cap U_j\cap U_k$.

The last equation is not decorative. It says that changing from chart $k$ to chart $j$ and then from chart $j$ to chart $i$ gives the same result as changing directly from chart $k$ to chart $i$. Without this compatibility, the local pieces do not glue to a well-defined bundle.

Changing local trivializations changes the transition functions by local redefinitions. If $h_i:U_i\to G$ changes the trivialization on $U_i$, then the transition functions are modified by a coboundary-like rule, schematically

$$
g_{ij}\mapsto h_i g_{ij}h_j^{-1}.
$$

The equivalence class of the gluing data is the bundle. Individual transition functions are not invariant; their global obstruction data can be.

## Sections

A section of a bundle $\pi:E\to M$ is a smooth map

$$
s:M\to E
$$

such that

$$
\pi(s(x))=x.
$$

It chooses one point in each fiber. In a local trivialization, the section is represented by a function

$$
s_i:U_i\to F.
$$

On an overlap, the local representatives must satisfy

$$
s_i(x)=g_{ij}(x)s_j(x).
$$

A field is often exactly such a section. When a textbook writes a field as a function $\phi(x)$, it is usually working in a global trivialization, or on a local patch where a trivialization has been chosen. This is fine for perturbation theory around trivial backgrounds. It is not fine when global sectors matter.

For vector bundles, there is always a zero section, because every vector space has a distinguished zero. But a vector bundle may fail to have a global frame. A global frame is a set of everywhere independent sections; having one is equivalent to trivializing the vector bundle.

For a principal bundle, a global section is even stronger: a principal $G$-bundle is trivial if and only if it admits a global section. This is one of the cleanest ways to see why gauge fixing can fail globally.

## Vector bundles

A vector bundle is a fiber bundle whose typical fiber is a vector space $V$, and whose transition functions are linear transformations:

$$
g_{ij}(x)\in GL(V).
$$

A rank-$r$ real vector bundle has fiber $\mathbb R^r$; a rank-$r$ complex vector bundle has fiber $\mathbb C^r$.

A local frame over $U_i$ is a basis of sections

$$
e_{i,1},\ldots,e_{i,r}
$$

for the fibers over $U_i$. A section $\psi$ can be expanded as

$$
\psi=\psi_i^a e_{i,a}.
$$

On an overlap, the local component columns are related by a transition matrix:

$$
\psi_i=g_{ij}\psi_j.
$$

Here $\psi_i$ and $\psi_j$ are not two different physical fields. They are two local component descriptions of one global section.

Important examples include:

| Vector bundle | Sections |
|---|---|
| trivial line bundle $M\times\mathbb R$ | real scalar fields |
| trivial complex line bundle $M\times\mathbb C$ | complex scalar fields in a chosen global trivialization |
| tangent bundle $TM$ | vector fields |
| cotangent bundle $T^*M$ | one-forms |
| exterior-power bundle $\Lambda^pT^*M$ | differential $p$-forms |
| spinor bundle $S\to M$ | spinor fields, when a spin structure exists |
| associated vector bundle $P\times_\rho V$ | matter fields in representation $\rho$ |

The tangent and cotangent bundles are not optional notation. They are the reason vector fields and one-forms have coordinate transformation laws. The spinor bundle is similarly the reason spinor fields have Lorentz or spin transition functions.

## Principal bundles

A principal $G$-bundle is the geometric home of gauge theory. It is a fiber bundle

$$
\pi:P\to M
$$

with a free right action of a Lie group $G$,

$$
P\times G\to P,
\qquad
(p,g)\mapsto pg,
$$

such that each fiber $P_x$ is a $G$-torsor. A $G$-torsor is like a copy of $G$ without a preferred identity element. Given two points $p,q\in P_x$, there is a unique $g\in G$ such that

$$
q=pg.
$$

But no point in $P_x$ is distinguished as “the identity” unless one chooses it. That is exactly what a local gauge choice does.

A local section

$$
\sigma_i:U_i\to P
$$

chooses one point in each principal fiber over $U_i$. On overlaps, two local sections are related by transition functions:

$$
\sigma_j(x)=\sigma_i(x)g_{ij}(x).
$$

This is the principal-bundle version of choosing gauges on patches. A local gauge is not the gauge field. It is a local choice of representatives in the principal bundle.

A principal bundle is trivial if it is globally isomorphic to

$$
M\times G.
$$

Equivalently, it admits a global section. Many important gauge configurations cannot be described using a single global gauge section. Dirac monopoles and Yang–Mills instantons are the standard warning signs.

## Associated bundles

Matter fields do not usually take values in the principal bundle itself. Instead, the principal bundle acts through a representation.

Let $\rho:G\to GL(V)$ be a representation. The associated vector bundle is

$$
E=P\times_\rho V.
$$

It is built from $P\times V$ by identifying

$$
(p,v)\sim(pg,\rho(g^{-1})v).
$$

With the local-section convention

$$
\sigma_j=\sigma_i g_{ij},
$$

a section of $P\times_\rho V$ is represented by local functions $\psi_i:U_i\to V$ obeying

$$
\psi_i=\rho(g_{ij})\psi_j.
$$

This is the precise geometric meaning of “a field in representation $\rho$.”

Two associated bundles appear constantly:

$$
P\times_\rho V
\qquad\text{and}\qquad
\operatorname{ad}P=P\times_{\operatorname{Ad}}\mathfrak g.
$$

The first is where matter fields live. The second is the adjoint bundle. Infinitesimal gauge transformations, non-Abelian curvatures, and gauge-covariant currents are naturally valued in $\operatorname{ad}P$.

## Gauge transformations as changes of trivialization

In local calculations, a gauge transformation often appears as a function

$$
h_i:U_i\to G.
$$

Geometrically, this can mean a change of local section

$$
\sigma_i\mapsto \sigma_i' = \sigma_i h_i.
$$

For an associated matter field, the local components change as

$$
\psi_i\mapsto \psi_i'=\rho(h_i^{-1})\psi_i
$$

if the underlying global section is kept fixed and only the trivialization is changed.

This is the passive convention: the geometric field stays the same, the local description changes. Many physics formulas use an active convention, where the field is transformed while the local frame is held fixed. These two descriptions are related by inverses. Bundle language keeps you honest about which one you are using.

A useful rule of thumb:

$$
\text{transition functions glue patches; gauge transformations change representatives.}
$$

Neither is by itself an observable. Gauge-invariant or gauge-covariant global data are the meaningful objects.

## Trivial bundles and nontrivial bundles

The simplest bundle is the product bundle

$$
E=M\times F,
\qquad
\pi(x,f)=x.
$$

A global section is just a map

$$
s:M\to F,
$$

written as $s(x)=(x,\phi(x))$. This is the setting silently used in many first calculations with scalar fields.

A nontrivial bundle is locally a product but not globally a product. The standard classroom example is the Möbius band as a real line bundle over $S^1$. Locally it looks like an interval times a line. Globally, one loop around the base flips the fiber by $-1$.

A more QFT-relevant example is a complex line bundle over $S^2$ described by two patches, north and south, with transition function on the equatorial overlap

$$
g_{NS}(\varphi)=e^{in\varphi},
\qquad
n\in\mathbb Z.
$$

The integer $n$ is the winding number of the transition function. With a compatible connection, this becomes the Dirac monopole line bundle whose first Chern number is $n$.

For a non-Abelian gauge theory, different principal $G$-bundles over the same spacetime can define different topological sectors of the path integral. Perturbation theory around $A=0$ usually sees only the trivial bundle. Instanton sums, monopole sectors, theta angles, and global one-form symmetries do not allow this luxury.

## Pullback bundles

Given a bundle

$$
\pi:E\to M
$$

and a smooth map

$$
f:N\to M,
$$

the pullback bundle $f^*E\to N$ has fiber

$$
(f^*E)_y=E_{f(y)}.
$$

Concretely,

$$
f^*E=\{(y,e)\in N\times E\mid f(y)=\pi(e)\}.
$$

Pullback bundles are everywhere in field theory even when not named. If a particle worldline $\gamma:I\to M$ moves through a gauge background, the relevant bundle along the particle is $\gamma^*E\to I$. If a boundary $\iota:\partial M\hookrightarrow M$ inherits a background field, the boundary bundle is $\iota^*E$. If a sigma model field $\phi:\Sigma\to X$ maps a worldsheet into a target manifold, target bundles such as $TX$ are pulled back to $\Sigma$ as $\phi^*TX$.

This is one of the reasons notation such as $D_\mu\phi$ can hide geometry: the derivative often acts on a section of a pulled-back bundle, not merely on a function.

## The QFT dictionary

Bundle language appears in QFT in several layers.

| QFT object | Bundle language |
|---|---|
| real scalar field | section of a real line bundle, often trivial |
| charged scalar or fermion | section of an associated vector bundle |
| gauge choice | local section of a principal bundle |
| gauge transformation | change of local trivialization or automorphism of a principal bundle |
| gauge field | connection on a principal bundle |
| field strength | curvature of a connection |
| Wilson line | parallel transport in a representation |
| spinor field | section of a spinor bundle |
| vielbein or frame field | section or soldering data related to a frame bundle |
| instanton sector | nontrivial principal-bundle topology plus connection data |
| monopole charge | topology of a $U(1)$ bundle over surrounding $S^2$ |
| theta term | integral of characteristic form built from curvature |

The punchline is that a gauge theory is not fully specified by its Lie algebra. One also needs the global form of the gauge group and the allowed bundles. The local Lie algebra controls perturbative gluon vertices. The global bundle data control line operators, magnetic sectors, one-form symmetries, and topological terms.

## Worked example: local charged field on a two-patch cover

Let $P\to M$ be a principal $U(1)$ bundle with two local sections $\sigma_N$ and $\sigma_S$ over patches $U_N$ and $U_S$. Suppose on the overlap

$$
\sigma_S=\sigma_N e^{in\varphi}.
$$

Let the charged field have charge $q=1$, so the representation is

$$
\rho(e^{i\alpha})=e^{i\alpha}.
$$

A section of the associated line bundle is represented by local functions $\psi_N$ and $\psi_S$ obeying

$$
\psi_N=e^{in\varphi}\psi_S.
$$

There need not be a single globally defined complex function $\psi$ on all of $M$. There is a globally defined section of a line bundle. Locally it looks like a function; globally it knows about the transition function.

This is the right way to read a charged wavefunction in a monopole background. The wavefunction is not multivalued; the attempt to force it into one global function is what creates fake paradoxes.

## Common pitfalls

**“A bundle is just a product with fancy notation.”** Locally, yes. Globally, no. The global gluing is where monopoles, instantons, winding, spin structures, and characteristic classes live.

**“A field is always a function on spacetime.”** Only in a chosen trivialization. More invariantly, many fields are sections of bundles over spacetime.

**“Gauge transformations are physical symmetries in the same sense as global symmetries.”** Gauge transformations are changes of description or redundancies, though global remnants and boundary-acting transformations can have physical content. Bundle language separates gauge redundancy from global symmetry more cleanly than component notation does.

**“A principal bundle has a preferred identity element in each fiber.”** It does not. Each fiber is a $G$-torsor, not canonically the group $G$ itself. Choosing a local identity is choosing a local section.

**“A vector bundle is nontrivial only if it has no global sections.”** Vector bundles always have the zero section. Nontriviality means, among other equivalent tests, that the bundle has no global frame.

**“If $A_\mu$ is not globally defined, the gauge theory is ill-defined.”** Backwards. In a nontrivial gauge background, the local gauge potentials are expected to be patchwise. The global object is the connection on the bundle.

## Exercises

### Exercise 1: The cocycle condition

Let transition functions be defined by

$$
\varphi_i\circ\varphi_j^{-1}(x,f)=(x,g_{ij}(x)f).
$$

Show that consistency on a triple overlap requires

$$
g_{ij}g_{jk}=g_{ik}.
$$

<details><summary><strong>Solution</strong></summary>

Start in chart $k$ with fiber coordinate $f_k$. Changing from $k$ to $j$ gives

$$
f_j=g_{jk}f_k.
$$

Changing from $j$ to $i$ gives

$$
f_i=g_{ij}f_j=g_{ij}g_{jk}f_k.
$$

Changing directly from $k$ to $i$ gives

$$
f_i=g_{ik}f_k.
$$

For the two procedures to agree for every $f_k$, we need

$$
g_{ij}g_{jk}=g_{ik}
$$

on the triple overlap.

</details>

### Exercise 2: A principal bundle with a global section is trivial

Let $P\to M$ be a principal $G$-bundle. Suppose it has a global section $\sigma:M\to P$. Show that

$$
P\cong M\times G.
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
\Phi:M\times G\to P,
\qquad
\Phi(x,g)=\sigma(x)g.
$$

This map lands in the fiber over $x$. Since each fiber $P_x$ is a $G$-torsor, every point $p\in P_x$ can be written uniquely as

$$
p=\sigma(x)g
$$

for a unique $g\in G$. Thus $\Phi$ is bijective fiber by fiber. Smoothness and smoothness of the inverse follow from the smooth principal-bundle structure. Therefore $P$ is isomorphic to the product principal bundle $M\times G$.

Conversely, the product bundle has the global section $x\mapsto (x,e)$, so a principal bundle is trivial if and only if it admits a global section.

</details>

### Exercise 3: Associated-bundle component transformation

Let $P\to M$ be a principal $G$-bundle with local sections satisfying

$$
\sigma_j=\sigma_i g_{ij}.
$$

Using the associated-bundle equivalence

$$
(p,v)\sim(pg,\rho(g^{-1})v),
$$

show that local representatives of a section satisfy

$$
\psi_i=\rho(g_{ij})\psi_j.
$$

<details><summary><strong>Solution</strong></summary>

A section of $P\times_\rho V$ is represented locally by

$$
[\sigma_i(x),\psi_i(x)]
$$

on $U_i$ and

$$
[\sigma_j(x),\psi_j(x)]
$$

on $U_j$. On the overlap, these are the same associated-bundle point. Since

$$
\sigma_j=\sigma_i g_{ij},
$$

we have

$$
[\sigma_j,\psi_j]=[\sigma_i g_{ij},\psi_j]
=[\sigma_i,\rho(g_{ij})\psi_j].
$$

Equality with $[\sigma_i,\psi_i]$ gives

$$
\psi_i=\rho(g_{ij})\psi_j.
$$

</details>

### Exercise 4: The Möbius line bundle transition function

Cover $S^1$ by two intervals $U_1,U_2$ whose overlap has two connected components. A real line bundle over $S^1$ can be described by transition functions valued in $GL(1,\mathbb R)=\mathbb R^\times$. Explain why a sign flip on one overlap component gives a nontrivial line bundle.

<details><summary><strong>Solution</strong></summary>

For a real line bundle, transition functions are nonzero real functions. Up to deformation, their essential data are their signs. If all signs can be made positive by changing local trivializations, the bundle is orientable as a line bundle and is trivial over $S^1$.

For the Möbius bundle, going once around the base reverses the fiber direction. In a two-patch description, this reversal appears as an odd number of sign flips in the transition functions around the circle. Local changes of frame can move the sign flip from one overlap component to another, but cannot remove the total reversal. Therefore the line bundle is not globally $S^1\times\mathbb R$.

Equivalently, a nowhere-zero section of a real line bundle would choose a continuous orientation of every fiber. The Möbius band has no such global choice.

</details>

### Exercise 5: Pullback of a tangent bundle along a curve

Let $\gamma:I\to M$ be a smooth curve. Describe the fiber of $\gamma^*TM\to I$ over $t\in I$. Why is this the natural home for a vector field along the curve?

<details><summary><strong>Solution</strong></summary>

By definition,

$$
(\gamma^*TM)_t=T_{\gamma(t)}M.
$$

A section of $\gamma^*TM\to I$ assigns to each $t$ a tangent vector at the point $\gamma(t)$, not a tangent vector at $t$ itself. This is exactly what a vector field along a curve is:

$$
V(t)\in T_{\gamma(t)}M.
$$

The velocity $\dot\gamma(t)$ is one example. Forces, polarization vectors transported along a worldline, and internal vectors parallel transported through a gauge background are all naturally described this way.

</details>

## Relations to other pages

[Manifolds](/math-toolkit/geometry-of-fields/manifolds/) supplies the base spaces. [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) supplies the form language used for connection and curvature forms. [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/) explains the groups that appear as structure groups. [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) explains why the global form of the gauge group matters beyond the Lie algebra.

The next page, [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), adds the differential structure that lets fields be parallel transported and differentiated.

## Research status

Ordinary smooth bundle theory is settled mathematics. In QFT, the active frontier is not whether principal and associated bundles are the right finite-dimensional language; they are. The frontier is that many modern theories require refinements: higher-form gauge fields are described by higher bundles or gerbes, anomalous backgrounds may require differential cohomology, gauge quotients may be stack-like, and global symmetry backgrounds can include nontrivial higher-group or noninvertible data.

For most graduate QFT, however, the ordinary bundle dictionary already pays enormous dividends. It prevents a single local gauge potential from being mistaken for a global object, and it makes topological sectors part of the theory rather than an afterthought.

## References

- M. Nakahara, *Geometry, Topology and Physics*. A physics-oriented route through bundles, connections, characteristic classes, monopoles, instantons, and spinors.
- T. Frankel, *The Geometry of Physics*. Excellent for geometric intuition about tangent bundles, cotangent bundles, differential forms, vector bundles, and gauge fields.
- N. Steenrod, *The Topology of Fibre Bundles*. A classic mathematical source for the foundational bundle language.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*, Vol. I. A standard reference for principal bundles, associated bundles, connections, and curvature.
- J. Milnor and J. Stasheff, *Characteristic Classes*. Standard for vector bundles and characteristic classes.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for seeing bundles, gauge sectors, Wilson loops, and topology as part of QFT reasoning.
- M. Srednicki, *Quantum Field Theory*, and S. Weinberg, *The Quantum Theory of Fields*, Vol. II. Useful for the gauge-theory physics that bundle language organizes.

## Version history

- **2026-06-25:** Initial polished draft. Added fiber bundle definitions, transition functions, cocycles, sections, vector bundles, principal bundles, associated bundles, gauge transformations, pullback bundles, QFT dictionary, examples, common pitfalls, exercises, and figure.
