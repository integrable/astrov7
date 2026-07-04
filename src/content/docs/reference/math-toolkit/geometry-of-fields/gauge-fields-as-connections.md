---
title: "Gauge Fields as Connections"
description: "Builds the dictionary between local Yang–Mills gauge potentials and global connections on principal bundles, including matter bundles, curvature, gauge transformations, Wilson loops, actions, and global gauge data."
sidebar:
  label: "Gauge Fields as Connections"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard geometry and gauge-theory references, including Nakahara, Frankel, Kobayashi–Nomizu, Eguchi–Gilkey–Hanson, Polyakov, Srednicki, Weinberg, and Schwartz."
topics:
  - gauge fields
  - connections
  - principal bundles
  - associated bundles
  - Yang–Mills theory
  - covariant derivative
  - field strength
  - gauge transformations
  - Wilson loops
  - global gauge group
canonicalTopics:
  - gauge-fields-as-connections
  - principal-g-bundle
  - associated-vector-bundle
  - gauge-potential
  - field-strength
  - yang-mills-connection
  - gauge-transformation
  - adjoint-bundle
  - wilson-loop
researchStatus:
  established:
    - "Classical gauge fields are precisely connections on principal bundles, and their field strengths are curvature forms; this is the standard geometric foundation of Yang–Mills theory."
  active:
    - "Modern QFT refines this dictionary using global forms of gauge groups, higher bundles, differential cohomology, generalized symmetry backgrounds, defects, stacks, and nonperturbative path-integral sectors."
---

## Summary

A gauge field is a connection on a principal bundle. The local symbols

$$
A_\mu^a(x)
$$

are components of a connection in a chosen local trivialization. The field strength

$$
F_{\mu\nu}^a(x)
$$

is the corresponding curvature. Matter fields are sections of associated bundles, and the covariant derivative is the derivative induced by the connection.

The dictionary is

$$
\boxed{\text{gauge potential} = \text{local connection form}},
\qquad
\boxed{\text{field strength} = \text{curvature}}.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Dictionary diagram connecting principal bundles, local sections, connection forms, curvature forms, associated bundles, matter fields, covariant derivatives, field strengths, gauge transformations, and Wilson observables.](/figures/math-toolkit/gauge-fields-connection-dictionary.svg)

<figcaption>

The gauge-field dictionary. A principal bundle $P\to M$ carries a connection $\omega$. A local section $s_i$ turns it into a local connection form $\mathcal A_i=s_i^*\omega$. In physics normalization, $\mathcal A=igA^aT^a$, so the induced derivative is $D=d+igA^aT_R^a$ and the curvature is $D^2=igF^aT_R^a$.

</figcaption>
</figure>

This page uses the site’s default compact-gauge-group convention:

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
D=d+igA^aT^a,
$$

with Hermitian generators $T^a$. The corresponding mathematical connection form is anti-Hermitian:

$$
\mathcal A=igA^aT^a.
$$

Its curvature is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=igF^aT^a,
$$

where

$$
F^a=dA^a-\frac g2 f^{abc}A^b\wedge A^c.
$$

In components,

$$
F^a_{\mu\nu}
=\partial_\mu A^a_\nu-\partial_\nu A^a_\mu-gf^{abc}A^b_\mu A^c_\nu.
$$

Many QFT texts use $D=d-igA^aT^a$, which flips the sign of the non-Abelian term. That is fine; mixing the two conventions is where the goblin lives.

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), and [Holonomy](/math-toolkit/geometry-of-fields/holonomy/) first. You should also know the compact Lie group conventions in [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) and [Mathematical Conventions](/math-toolkit/conventions/).

The purpose of this page is not to quantize Yang–Mills theory. It is to explain the classical geometric object that later becomes a path-integral variable, a source of Wilson loops, and the background for charged matter.

## Core idea

In elementary notation, a non-Abelian gauge field looks like a collection of one-forms

$$
A^a=A_\mu^a dx^\mu
$$

labeled by Lie algebra indices. The package

$$
A=A^aT^a
$$

looks like a Lie-algebra-valued one-form on spacetime.

That statement is only globally true if the gauge bundle is trivial and a global trivialization has been chosen. In general, there is no single globally defined $A$ on all of $M$. Instead, one has local connection forms $A_i$ on patches $U_i$, related on overlaps by gauge transformation laws. The global object is the connection on a principal $G$-bundle.

The geometry says:

$$
\text{local gauge potentials are local representatives of one global connection.}
$$

This is the same kind of statement as saying that coordinate components of a vector are local representatives of one global vector field. Except here the transformation law is affine, not tensorial, because a connection is not a tensor.

## Principal bundle first

Let

$$
\pi:P\to M
$$

be a principal $G$-bundle. The base $M$ is spacetime or a Euclidean spacetime manifold. The total space $P$ stores possible internal frames. The group $G$ acts freely and transitively on each fiber from the right.

A local trivialization can be encoded by a local section

$$
s_i:U_i\to P.
$$

Choosing $s_i$ is the geometric version of choosing a gauge on the patch $U_i$. It identifies the bundle over $U_i$ with $U_i\times G$.

On an overlap $U_i\cap U_j$, two local sections are related by a transition function

$$
s_j(x)=s_i(x)g_{ij}(x).
$$

The maps

$$
g_{ij}:U_i\cap U_j\to G
$$

are part of the global gauge-bundle data. If all transition functions can be removed by redefining local sections, the bundle is globally trivial. If not, there are topological sectors that cannot be seen in one coordinate patch.

## A connection on a principal bundle

A principal connection can be defined as a Lie-algebra-valued one-form

$$
\omega\in\Omega^1(P,\mathfrak g)
$$

satisfying the two principal-connection conditions:

$$
\omega(\xi_P)=\xi,
\qquad
R_g^*\omega=\operatorname{Ad}_{g^{-1}}\omega.
$$

Here $\xi_P$ is the vertical vector field generated by $\xi\in\mathfrak g$, and $R_g$ is the right action of $g\in G$ on $P$.

A local section $s_i:U_i\to P$ pulls the global connection back to a local one-form on $U_i$:

$$
\mathcal A_i=s_i^*\omega\in\Omega^1(U_i,\mathfrak g).
$$

This $\mathcal A_i$ is the mathematical connection form that physicists write locally as

$$
\mathcal A_i=igA_i^aT^a.
$$

The global connection $\omega$ is invariantly defined on $P$. The one-form $\mathcal A_i$ is a local representative on $U_i$.

## Gauge transformations from changing local sections

A gauge transformation is, locally, a change of section. Let

$$
s_i'(x)=s_i(x)h(x)
$$

for a smooth map $h:U_i\to G$. The pulled-back connection form changes as

$$
\mathcal A_i'
=h^{-1}\mathcal A_i h+h^{-1}dh.
$$

This is the origin of the inhomogeneous gauge transformation law.

In physics notation, using $\mathcal A=igA^aT^a$, this becomes

$$
A'=h^{-1}Ah-\frac{i}{g}h^{-1}dh
$$

when $A=A^aT^a$ is Hermitian-matrix-valued. If a text uses the opposite covariant-derivative convention, the sign of the derivative term changes.

The inhomogeneous term means $A$ is not a tensor. The difference of two connections *is* tensorial. If $\mathcal A$ and $\mathcal A'$ are two connection forms written in the same local frame, then

$$
\mathcal A'-\mathcal A
$$

transforms as an adjoint-valued one-form under a change of frame.

That fact is why background-field expansions are usually written as

$$
\mathcal A=\overline{\mathcal A}+a,
$$

where the fluctuation $a$ is an adjoint-bundle-valued one-form.

## Curvature as field strength

The curvature of the principal connection is the horizontal equivariant two-form

$$
\Omega=d\omega+\frac12[\omega,\omega]
$$

on $P$. In a local section, this becomes

$$
\mathcal F_i=s_i^*\Omega
=d\mathcal A_i+\mathcal A_i\wedge\mathcal A_i.
$$

Under a change of section,

$$
\mathcal F_i'=h^{-1}\mathcal F_i h.
$$

Unlike the connection form, the curvature transforms tensorially. This is why expressions such as

$$
\operatorname{tr}(\mathcal F\wedge *\mathcal F)
$$

can be globally meaningful after taking an invariant trace.

In the site convention,

$$
\mathcal F=igF^aT^a.
$$

Thus

$$
F^a=dA^a-\frac g2 f^{abc}A^b\wedge A^c.
$$

The Abelian limit is recovered by setting $f^{abc}=0$:

$$
F=dA.
$$

The non-Abelian term is not an optional interaction pasted onto electromagnetism. It is the $\mathcal A\wedge\mathcal A$ part of curvature.

## Matter fields as sections of associated bundles

Let $R:G\to GL(V_R)$ be a representation. The associated vector bundle is

$$
E_R=P\times_R V_R.
$$

A matter field in representation $R$ is a section

$$
\psi\in\Gamma(M,E_R).
$$

In a local section $s_i$, it is represented by a function

$$
\psi_i:U_i\to V_R.
$$

On overlaps, the local representatives transform according to the representation. With the convention used here,

$$
\psi_i=R(g_{ij})\psi_j
$$

for transition functions $g_{ij}$ relating the local sections.

The connection on $P$ induces a covariant derivative on every associated bundle:

$$
D\psi_i=d\psi_i+\mathcal A_{i,R}\psi_i.
$$

In physics notation,

$$
D\psi_i=d\psi_i+igA_i^aT_R^a\psi_i.
$$

Thus the same principal connection tells every charged representation how to differentiate. The representation changes the matrices $T_R^a$, not the underlying gauge field.

## The adjoint bundle

The adjoint bundle is

$$
\operatorname{ad}(P)=P\times_{\operatorname{Ad}}\mathfrak g.
$$

Curvature is naturally an adjoint-bundle-valued two-form:

$$
\mathcal F\in\Omega^2(M,\operatorname{ad}(P)).
$$

The difference between two connections is an adjoint-bundle-valued one-form:

$$
a\in\Omega^1(M,\operatorname{ad}(P)).
$$

This distinction is important. A connection is not itself a section of $T^*M\otimes\operatorname{ad}(P)$ in a canonical way, because the space of connections is affine. Once a reference connection is chosen, differences from it are ordinary adjoint-valued one-forms.

This is the geometric reason that perturbative gauge theory expands around a background connection. The fluctuation is tensorial; the background plus fluctuation is a connection.

## Local Yang–Mills formulas

In a local trivialization, write

$$
A=A_\mu^aT^a dx^\mu.
$$

The covariant derivative in representation $R$ is

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a.
$$

The commutator gives

$$
[D_\mu,D_\nu]=igF^a_{\mu\nu}T_R^a,
$$

with

$$
F^a_{\mu\nu}
=\partial_\mu A^a_\nu-\partial_\nu A^a_\mu-gf^{abc}A^b_\mu A^c_\nu.
$$

The Bianchi identity is

$$
D\mathcal F=0.
$$

In components, this is

$$
D_{[\mu}F_{\nu\rho]}=0,
$$

with the gauge-covariant derivative acting in the adjoint representation.

These are not merely analogies with differential geometry. They are differential geometry.

## Yang–Mills action

On a metric spacetime, the Hodge star converts the curvature two-form into a form that can be integrated. In four-dimensional Lorentzian signature, the common physics action is

$$
S_{\text{YM}}
=-\frac14\int d^4x\,F^a_{\mu\nu}F^{a\mu\nu}.
$$

With Hermitian generators normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

this can be written as

$$
S_{\text{YM}}=-\int_M\operatorname{tr}(F\wedge *F),
$$

where $F=F^aT^a$ is the Hermitian-matrix-valued field strength.

In the anti-Hermitian mathematical convention $\mathcal F=igF$, the coupling placement changes. A common geometric convention absorbs the coupling into the connection and writes a prefactor proportional to $1/g^2$. These are bookkeeping choices, not different physics. The action and covariant derivative must be translated together.

The equations of motion without matter can be written compactly as

$$
D*F=0
$$

in the appropriate convention. With a matter current, the right-hand side is a current valued in the adjoint bundle.

## Topological terms and characteristic forms

Gauge curvature also builds topological densities. In four Euclidean dimensions, the instanton density is built from

$$
\operatorname{tr}(F\wedge F)
$$

or, in anti-Hermitian notation, from

$$
\operatorname{tr}(\mathcal F\wedge\mathcal F)
$$

with a convention-dependent sign and normalization. The integral is related to a characteristic class when the bundle and trace normalization are chosen correctly.

This is where the global bundle viewpoint stops being optional. A formula such as

$$
\int_M\operatorname{tr}(F\wedge F)
$$

can distinguish topological sectors of gauge fields. If one treats $A_\mu^a$ as a globally defined collection of functions on a single trivial bundle, those sectors disappear by assumption.

Later topology pages should give the precise Chern–Weil normalizations. The point here is simpler: characteristic classes are built from curvature of connections on bundles.

## Holonomy and Wilson observables

Given a connection, parallel transport along a path $\gamma$ gives

$$
U_R(\gamma)=\mathcal P\exp\left(-\int_\gamma\mathcal A_R\right).
$$

For a closed loop $C$, the Wilson loop is

$$
W_R(C)=\operatorname{tr}_R U_R(C).
$$

The trace is gauge invariant because changing local section conjugates the holonomy. This is why Wilson loops are natural observables in gauge theory.

The representation $R$ matters. Which Wilson loops are genuine line operators can depend on the global form of the gauge group, not just on the Lie algebra. For example, theories with Lie algebra $\mathfrak{su}(N)$ but different global gauge groups can allow different line operators and different topological sectors.

## Abelian gauge theory as line-bundle geometry

For $G=U(1)$, principal $U(1)$-bundles correspond to complex line bundles. A charged field is a section of a power of that line bundle, depending on its charge.

In local patches, the connection is a one-form $\mathcal A_i$. On overlaps,

$$
\mathcal A_i=\mathcal A_j+g_{ij}^{-1}dg_{ij}
$$

because $U(1)$ is Abelian. If

$$
g_{ij}=e^{i\chi_{ij}},
$$

then

$$
g_{ij}^{-1}dg_{ij}=i\,d\chi_{ij}.
$$

The curvature

$$
\mathcal F=d\mathcal A_i
$$

agrees on overlaps, so it is globally defined.

Magnetic flux quantization is a global statement about the line bundle. Locally $F=dA$ may look unremarkable, but the integral of curvature over a closed two-cycle can be quantized. This is the geometric core of Dirac monopoles and first Chern classes.

## Non-Abelian gauge theory

For non-Abelian $G$, transition functions do not commute, path ordering is necessary, and curvature includes the quadratic term

$$
\mathcal A\wedge\mathcal A.
$$

Local gauge potentials on overlaps are related by

$$
\mathcal A_i
=g_{ij}\mathcal A_j g_{ij}^{-1}-dg_{ij}\,g_{ij}^{-1}
$$

or by the equivalent inverse convention, depending on whether one writes the change from $j$ to $i$ or from $i$ to $j$. The important invariant statement is that the curvature transforms by conjugation and the covariant derivative maps local matter fields consistently across overlaps.

Non-Abelian gauge theory also has bundle topology. Instantons, magnetic monopoles, center vortices, and nontrivial Wilson line sectors are not visible if one only studies small fluctuations around the trivial bundle.

## Gauge transformations versus global symmetries

A gauge transformation is an automorphism of the bundle covering the identity map on $M$. It changes the local description of the same geometric field configuration. In ordinary gauge theory, configurations related by gauge transformations represent the same physical configuration.

This is different from a global symmetry acting faithfully on physical states or operators. The distinction becomes subtle because gauge theories can have global symmetries built from their center, topology, line operators, or boundary behavior. But the local gauge redundancy itself is not a physical symmetry that produces distinct states.

The geometric version is clean:

$$
\text{gauge transformations are changes of bundle frame, not motions in spacetime.}
$$

Boundary conditions can complicate this statement. A gauge transformation that does not approach the identity at a boundary may act as a genuine global symmetry on boundary data. That refinement belongs to later pages on charges, constraints, and asymptotic symmetries.

## Global form of the gauge group

The Lie algebra does not determine the full gauge theory. Groups with the same Lie algebra can have different centers, different allowed bundles, and different representations. For example, $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ share the same Lie algebra but have different line operators and bundle sectors.

Local perturbation theory mostly sees the Lie algebra. Nonperturbative physics can see the global group.

A complete specification of a gauge theory therefore includes more than

$$
\mathfrak g
$$

and a Lagrangian density. It also includes the global gauge group, matter representations, allowed bundles, line operators, theta angles or discrete topological terms when present, and boundary conditions.

That sounds like fine print until it decides the answer.

## Gauge fixing and the path integral

The classical configuration space of gauge fields is the space of connections modulo gauge transformations:

$$
\mathcal A(P)/\mathcal G(P),
$$

schematically. The path integral over gauge fields is therefore not an ordinary integral over all local components $A_\mu^a$ without redundancy. It must handle the quotient by gauge transformations.

Gauge fixing chooses a representative from each gauge orbit, at least locally and perturbatively. Faddeev–Popov determinants, BRST symmetry, ghosts, Gribov ambiguities, and background-field gauges are all refinements of this basic quotient problem.

The geometric picture is useful because it separates three issues:

| Layer | Geometric meaning |
|---|---|
| local potential $A_i$ | representative of a connection in a patch |
| gauge transformation | change of local section or bundle automorphism |
| physical gauge field | connection modulo gauge equivalence, with global sector specified |

Most perturbative calculations work inside one chosen trivialization near the trivial bundle. Many nonperturbative questions do not.

## Common pitfalls

**Thinking $A_\mu^a$ is globally defined.** It is globally defined only after choosing a global trivialization of a trivial bundle. In general, gauge potentials are local representatives patched by transition functions.

**Forgetting that a connection is affine.** The difference between two connections is tensorial, but a single connection form is not. This is why the gauge transformation of $A$ has an inhomogeneous term.

**Confusing curvature with connection.** Curvature transforms tensorially and enters local gauge-invariant densities. The connection is needed for parallel transport, covariant derivatives, and Wilson lines.

**Using the Lie algebra as the whole gauge group.** Local formulas see $\mathfrak g$. Line operators, monopoles, instantons, and allowed bundles can depend on the global form of $G$.

**Mixing Hermitian and anti-Hermitian conventions.** Physicists often use Hermitian $T^a$ and write $D=d+igA^aT^a$. Mathematicians often use an anti-Hermitian connection $\mathcal A$. Translate signs and factors of $i$ together.

**Calling gauge redundancy a physical symmetry.** Gauge-equivalent configurations are different descriptions of the same configuration. Physical global symmetries act on gauge-invariant data.

## Exercises

### Exercise 1: Curvature in the site convention

Let

$$
D=d+igA^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

Show that

$$
D^2=igF^aT^a
$$

with

$$
F^a=dA^a-\frac g2 f^{abc}A^b\wedge A^c.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
\mathcal A=igA^aT^a.
$$

Then

$$
D=d+\mathcal A,
\qquad
D^2=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

The first term is

$$
d\mathcal A=ig\,dA^aT^a.
$$

The second term is

$$
\mathcal A\wedge\mathcal A
=(ig)^2A^a\wedge A^bT^aT^b.
$$

Only the commutator contributes because $A^a\wedge A^b$ is antisymmetric in $a,b$:

$$
A^a\wedge A^bT^aT^b
=\frac12A^a\wedge A^b[T^a,T^b]
=\frac i2 f^{abc}A^a\wedge A^bT^c.
$$

Therefore

$$
\mathcal A\wedge\mathcal A
=-\frac{i g^2}{2}f^{abc}A^a\wedge A^bT^c.
$$

Relabeling dummy indices gives

$$
D^2
=ig\left(dA^a-\frac g2f^{abc}A^b\wedge A^c\right)T^a.
$$

Thus

$$
F^a=dA^a-\frac g2 f^{abc}A^b\wedge A^c.
$$

</details>

### Exercise 2: Curvature transforms tensorially

Assume

$$
\mathcal A'=h^{-1}\mathcal A h+h^{-1}dh.
$$

Show that

$$
\mathcal F'=h^{-1}\mathcal Fh.
$$

<details><summary><strong>Solution</strong></summary>

The cleanest proof uses covariant derivatives. Since

$$
D'=d+\mathcal A'
$$

is related to

$$
D=d+\mathcal A
$$

by

$$
D'=h^{-1}Dh,
$$

we square both sides:

$$
(D')^2=h^{-1}D^2h.
$$

But

$$
D^2=\mathcal F,
\qquad
(D')^2=\mathcal F'.
$$

Therefore

$$
\mathcal F'=h^{-1}\mathcal Fh.
$$

This avoids a long expansion of $d(h^{-1}dh)$, although that expansion gives the same result using the Maurer–Cartan identity.

</details>

### Exercise 3: Difference of two connections

Let $\mathcal A_1$ and $\mathcal A_2$ be two local connection forms that transform as

$$
\mathcal A_i' = h^{-1}\mathcal A_i h+h^{-1}dh.
$$

Show that

$$
a=\mathcal A_2-\mathcal A_1
$$

transforms tensorially.

<details><summary><strong>Solution</strong></summary>

Compute

$$
a'=\mathcal A_2'-\mathcal A_1'.
$$

Using the transformation law,

$$
a'
=igl(h^{-1}\mathcal A_2h+h^{-1}dh\bigr)
-igl(h^{-1}\mathcal A_1h+h^{-1}dh\bigr).
$$

The inhomogeneous terms cancel, leaving

$$
a'=h^{-1}(\mathcal A_2-\mathcal A_1)h=h^{-1}ah.
$$

Thus the difference of two connections is an adjoint-valued one-form.

</details>

### Exercise 4: Abelian limit

Take $G=U(1)$. Show that the curvature reduces to

$$
F=dA
$$

and the Wilson loop reduces to an ordinary exponential.

<details><summary><strong>Solution</strong></summary>

For $U(1)$, the Lie algebra is Abelian, so all structure constants vanish:

$$
f^{abc}=0.
$$

Therefore the non-Abelian term in

$$
F^a=dA^a-\frac g2f^{abc}A^b\wedge A^c
$$

disappears. Since there is only one generator, write simply

$$
F=dA.
$$

Likewise, the connection values commute along a path, so path ordering is unnecessary:

$$
U_C=\exp\left(-\oint_C\mathcal A\right).
$$

In charge-$q$ physics notation, this is often written as

$$
\exp\left(-iq\oint_C A\right)
$$

or with the opposite sign depending on the covariant-derivative convention.

</details>

### Exercise 5: Gauge-invariant Yang–Mills density

Let $F=F^aT^a$ transform as

$$
F'=h^{-1}Fh.
$$

Show that $\operatorname{tr}(F\wedge *F)$ is gauge invariant.

<details><summary><strong>Solution</strong></summary>

The Hodge star acts on the form indices and commutes with the internal matrix multiplication, so

$$
*F'=h^{-1}(*F)h.
$$

Then

$$
\operatorname{tr}(F'\wedge *F')
=
\operatorname{tr}\bigl(h^{-1}Fh\wedge h^{-1}(*F)h\bigr).
$$

The group-valued functions multiply in the internal indices, while the wedge product multiplies the form parts. The middle factors combine, and cyclicity of the trace gives

$$
\operatorname{tr}\bigl(h^{-1}F\wedge (*F)h\bigr)
=
\operatorname{tr}(F\wedge *F).
$$

Thus the Yang–Mills density is gauge invariant.

</details>

## Relations to other pages

[Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) gives the general connection theory behind this page. [Holonomy](/math-toolkit/geometry-of-fields/holonomy/) explains Wilson loops as traces of parallel transport. [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) explains transition functions and associated bundles. [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) explain the form notation used in $F\wedge *F$ and $F\wedge F$. [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/) previews the path-integral quotient problem that appears after quantizing gauge fields.

Later pages on Riemannian and Lorentzian geometry, spin structures, Dirac operators, characteristic classes, index theorems, instantons, anomalies, generalized symmetries, and nonperturbative gauge theory should link back here.

## Research status

The equivalence between classical gauge fields and principal-bundle connections is settled. The active issues in QFT arise when this geometry is quantized and globalized: which bundles are summed over, which global form of the gauge group is chosen, which line and surface operators are genuine, how gauge fixing is implemented nonperturbatively, how singular defects are included, and how higher-form or differential-cohomological gauge fields are represented.

The local formula $F=dA+A\wedge A$ is the beginning, not the full specification of a gauge theory.

## References

- M. Nakahara, *Geometry, Topology and Physics*. Standard physics-oriented reference for principal bundles, associated bundles, connections, curvature, monopoles, instantons, and characteristic classes.
- T. Frankel, *The Geometry of Physics*. Clear geometric explanations of differential forms, connections, curvature, gauge fields, and physical examples.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*, Vol. I. Mathematical reference for principal connections and curvature.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, “Gravitation, Gauge Theories and Differential Geometry.” Classic bridge between gauge theory, curvature, topology, and gravity.
- A. M. Polyakov, *Gauge Fields and Strings*. Classic source for Wilson loops, gauge topology, instantons, compact gauge fields, and nonperturbative gauge-theory thinking.
- M. Srednicki, *Quantum Field Theory*, S. Weinberg, *The Quantum Theory of Fields*, Vol. II, and M. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for translating the geometric dictionary into standard Yang–Mills and Standard Model notation.

## Version history

- **2026-06-25:** Initial polished draft. Added principal-bundle dictionary, local connection forms, gauge transformations, matter associated bundles, adjoint bundle, curvature and field-strength conventions, Yang–Mills action, topological terms, Wilson observables, global gauge group comments, gauge fixing context, common pitfalls, exercises, and figure.
