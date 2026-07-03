---
title: "Monopoles"
description: "Explains magnetic monopoles as topological solitons and bundle defects, including Dirac monopoles, ’t Hooft–Polyakov monopoles, magnetic charge, exact homotopy sequences, and BPS bounds."
sidebar:
  label: "Monopoles"
  order: 5
level: Advanced
status: "Polished draft"
source: "Srednicki §92; Polyakov Ch. 6; Nakahara Chs. 1 and 4; Frankel on bundles and Chern classes; Manton–Sutcliffe; Rajaraman; Tong TASI soliton notes."
topics:
  - monopoles
  - magnetic charge
  - topological solitons
  - Dirac quantization
  - t Hooft Polyakov monopole
  - Higgs fields
  - Chern class
  - exact homotopy sequence
canonicalTopics:
  - magnetic-monopole
  - dirac-monopole
  - thooft-polyakov-monopole
  - monopole-charge
  - magnetic-flux-quantization
researchStatus:
  established:
    - "Magnetic monopoles can be described either as singular Abelian bundle data or as smooth finite-energy solitons in non-Abelian gauge theories broken to an Abelian subgroup."
    - 'For symmetry breaking $G\to H$, classical smooth monopole sectors are controlled by $\pi_2(G/H)$, equivalently by suitable magnetic flux data in the unbroken gauge group.'
  active:
    - "Monopoles remain central in confinement mechanisms, supersymmetric duality, Coulomb-branch physics, three-dimensional disorder operators, global-form questions, and generalized symmetry."
---

## Summary

A monopole is a configuration or operator carrying magnetic charge. In classical electromagnetism, a monopole would be a source of magnetic flux. In QFT, monopoles appear in two closely related but conceptually different ways.

A **Dirac monopole** is a singular Abelian configuration, better understood as a nontrivial $U(1)$ bundle over the sphere surrounding the monopole. Its magnetic charge is the first Chern number

$$
m={1\over 2\pi}\int_{S^2_\infty} F\in\mathbb Z
$$

in the unit-charge normalization.

A **’t Hooft–Polyakov monopole** is a smooth finite-energy soliton in a non-Abelian gauge theory with an adjoint Higgs field. At spatial infinity, the Higgs field defines a map

$$
\hat\Phi:S^2_\infty\to G/H,
$$

and the monopole charge is the homotopy class

$$
[\hat\Phi]\in \pi_2(G/H).
$$

For the standard breaking

$$
SU(2)\to U(1),
\qquad
G/H\simeq S^2,
$$

one gets

$$
\pi_2(S^2)=\mathbb Z.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a sphere at infinity around a monopole, the Higgs hedgehog map to a vacuum sphere, and the equivalent magnetic flux language.](/figures/symmetry-anomalies-topology/monopole-hedgehog-flux-map.svg)

<figcaption>

A smooth non-Abelian monopole has two equivalent asymptotic descriptions. The Higgs field winds on $S^2_\infty$, and the unbroken $U(1)$ gauge field carries magnetic flux. The same integer appears as a degree, a Chern class, and a magnetic charge.

</figcaption>
</figure>

Monopoles are where homotopy, bundles, gauge symmetry, and dynamics finally shake hands. Vortices are seen by circles; monopoles are seen by spheres.

## Prerequisites

You should know the configuration-space logic of [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/), the defect dictionary of [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), and the degree formulas in [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/).

The gauge-theory prerequisites are [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/), [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/), and [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/).

## Core idea

A monopole in three spatial dimensions is a codimension-three object. A small sphere surrounding it is

$$
S^2_\infty.
$$

If finite energy forces the fields at infinity to land in a vacuum manifold $\mathcal M_{\rm vac}$, the monopole is detected by a map

$$
S^2_\infty\to \mathcal M_{\rm vac}.
$$

The first-pass classification is

$$
\pi_2(\mathcal M_{\rm vac}).
$$

For an adjoint Higgs field breaking a gauge group $G$ to a subgroup $H$, the vacuum manifold is

$$
\mathcal M_{\rm vac}=G/H.
$$

Thus smooth classical monopoles are labeled by

$$
\pi_2(G/H).
$$

This is the homotopy side. The gauge-field side says that the unbroken gauge group $H$ can have nontrivial magnetic flux through $S^2_\infty$. For the standard $SU(2)\to U(1)$ monopole, these are the same integer.

## Setup and conventions

For a compact $U(1)$ gauge field normalized so that the minimal Wilson line is

$$
\exp\!\left(i\oint A\right),
$$

the magnetic flux through a closed two-surface satisfies

$$
\int_{S^2} F\in 2\pi\mathbb Z
$$

when all charged matter is globally well-defined. We write

$$
m={1\over 2\pi}\int_{S^2}F.
$$

If a text uses an electric charge $q$ in

$$
D=d-iqA,
$$

then Dirac quantization is usually written as

$$
q\int_{S^2}F\in 2\pi\mathbb Z.
$$

:::note[Convention-sensitive source note]
The factors of $2$, $2\pi$, $4\pi$, $q$, and $g$ in monopole formulas vary dramatically across the literature. This page uses the differential-form normalization $m=(2\pi)^{-1}\int F$. In particle-physics conventions one often writes magnetic field flux as $4\pi g_m$ and quantization as $qg_m\in {1\over2}\mathbb Z$ or $qg_m\in 2\pi\mathbb Z$, depending on rationalized units. Always identify the Wilson-line phase convention first.
:::

## Dirac monopole as a U(1) bundle

The magnetic field of a point monopole is locally radial. In ordinary vector notation one writes schematically

$$
\mathbf B(\mathbf r)=g_m {\mathbf r\over r^3}.
$$

This suggests a flux through a sphere:

$$
\int_{S^2}\mathbf B\cdot d\mathbf S=4\pi g_m.
$$

But the vector potential $A$ cannot be globally smooth on the whole sphere if the flux is nonzero. Instead, cover $S^2$ by northern and southern patches. A common choice is

$$
A_N=m(1-\cos\theta)d\varphi,
\qquad
A_S=-m(1+\cos\theta)d\varphi
$$

up to normalization choices. On the overlap near the equator,

$$
A_N-A_S=2m\,d\varphi.
$$

For the transition function to be single-valued on charged fields, the gauge transformation around the equator must close. This gives an integrality condition. In the unit-charge normalization it is exactly

$$
{1\over 2\pi}\int_{S^2}F\in\mathbb Z.
$$

The apparent Dirac string in a one-patch vector potential is not a physical singularity. It is a gauge artifact of trying to describe a nontrivial bundle with one coordinate chart.

That last sentence is the whole lesson. Monopoles are not merely unusual magnetic fields. They are global gauge-bundle data.

## Smooth monopoles from non-Abelian Higgs fields

Dirac monopoles are singular if treated as configurations of ordinary Maxwell theory on $\mathbb R^3$. The ’t Hooft–Polyakov monopole resolves the singularity by embedding the Abelian magnetic field into a non-Abelian gauge theory with a Higgs field.

Consider an $SU(2)$ gauge theory with an adjoint scalar $\Phi=\Phi^a T^a$. The potential forces

$$
|\Phi|\to v
$$

at spatial infinity. The unbroken group is the stabilizer of the Higgs direction:

$$
SU(2)\to U(1).
$$

The vacuum manifold is

$$
SU(2)/U(1)\simeq S^2.
$$

A unit monopole has asymptotic “hedgehog” behavior

$$
\hat\Phi^a(\mathbf r)
={\Phi^a\over |\Phi|}
\longrightarrow
{r^a\over r}.
$$

This map

$$
\hat\Phi:S^2_\infty\to S^2
$$

has degree one.

At large distance, only the unbroken $U(1)$ gauge field remains massless. The gauge-invariant electromagnetic field can be written schematically as

$$
\mathcal F_{\mu\nu}
=\hat\Phi^a F^a_{\mu\nu}
-{1\over g}\epsilon^{abc}\hat\Phi^a
D_\mu\hat\Phi^b D_\nu\hat\Phi^c,
$$

where $g$ is the non-Abelian gauge coupling in a common particle-physics normalization. This object reduces asymptotically to the magnetic field of a Dirac monopole in the unbroken $U(1)$, but the full non-Abelian fields are smooth at the origin.

## Homotopy sequence and the role of the unbroken group

For a symmetry breaking pattern

$$
G\to H,
$$

there is a fibration

$$
H\longrightarrow G\longrightarrow G/H.
$$

The long exact sequence in homotopy contains

$$
\pi_2(G)\to \pi_2(G/H)\to \pi_1(H)\to \pi_1(G).
$$

For compact connected Lie groups, often

$$
\pi_2(G)=0.
$$

Then monopole charges fit into

$$
\pi_2(G/H)
\simeq
\ker\!\left[\pi_1(H)\to\pi_1(G)\right].
$$

If $G$ is simply connected, this simplifies to

$$
\pi_2(G/H)\simeq \pi_1(H).
$$

For

$$
SU(2)\to U(1),
$$

we get

$$
\pi_2(SU(2)/U(1))
\simeq
\pi_1(U(1))
=\mathbb Z.
$$

This formula explains why monopoles are controlled by the unbroken gauge group as much as by the vacuum manifold. Magnetic charge is a statement about how the residual gauge bundle twists over the sphere at infinity.

## Finite energy and the monopole core

The static energy in a Yang–Mills–Higgs theory has the schematic form

$$
E=\int d^3x\left[
{1\over 2g^2}(B_i^a)^2
+{1\over 2}(D_i\Phi^a)^2
+V(\Phi)
\right],
$$

with normalization choices suppressed. Finite energy requires

$$
V(\Phi)\to0,
\qquad
D_i\Phi\to0,
\qquad
B_i\to0
\quad \text{fast enough locally, modulo magnetic flux}.
$$

The first condition sends $\Phi$ to the vacuum manifold at infinity. The second condition makes the Higgs direction covariantly constant at infinity. The third permits a $1/r^2$ magnetic field whose integrated flux over $S^2$ is nonzero.

At the core, the Higgs field leaves the vacuum manifold. For the hedgehog solution,

$$
\Phi^a\sim r^a
\quad \text{near } r=0,
$$

so that $\Phi=0$ at the origin. This removes the singularity of the Abelian Dirac monopole. The non-Abelian gauge fields also smooth out the would-be divergent magnetic energy.

The core is therefore not a dispensable technical detail. It is how a smooth field configuration realizes a nontrivial sphere map.

## BPS monopoles

In the Prasad–Sommerfield or BPS limit, the scalar potential is taken to zero while keeping the symmetry-breaking scale fixed. The energy can be completed into squares:

$$
E
={1\over 2g^2}\int d^3x\,(B_i^a\mp D_i\Phi^a)^2
\pm {1\over g^2}\int d^3x\,\partial_i(\Phi^a B_i^a),
$$

again up to convention-dependent normalization of $\Phi$ and $g$.

The boundary term is proportional to the magnetic charge. In common $SU(2)$ conventions the bound is

$$
M\ge {4\pi v\over g}|m|.
$$

BPS monopoles satisfy the first-order equations

$$
B_i^a=D_i\Phi^a
$$

or the same equation with the opposite sign for antimonopoles.

These equations are much more than an energy trick. They reveal a rich moduli space of multi-monopole solutions. In supersymmetric theories, BPS monopoles become protected states and play a starring role in electric–magnetic duality.

## Dyons and theta angles

A monopole can also carry electric charge. Such an object is called a dyon. In a theory with a theta term, the Witten effect shifts the electric charge of a monopole by an amount proportional to $\theta$:

$$
Q_{\rm electric}
\sim n_e+{\theta\over 2\pi}n_m,
$$

with normalization depending on the electric-charge lattice. This is developed in [Witten Effect: Preview](/symmetry-anomalies-topology/topological-terms/witten-effect-preview/).

The important conceptual point is that monopole charge is part of a lattice of electric and magnetic charges. The allowed lattice depends on the global form of the gauge group and on which line operators are genuine. That is why monopoles belong simultaneously to topology, gauge theory, and generalized symmetry.

## Monopoles as operators in lower dimensions

In three spacetime dimensions, a “monopole” is often not a particle in space but a local disorder operator. Inserting a monopole operator at a point imposes magnetic flux through a small surrounding $S^2$ in Euclidean spacetime:

$$
{1\over 2\pi}\int_{S^2_{\rm link}}F=m.
$$

This is the same linking-sphere logic, with Euclidean spacetime replacing physical space. Such monopole operators are crucial in three-dimensional gauge theories, bosonization dualities, Coulomb branches, and confinement mechanisms.

So the word “monopole” can mean a particle-like soliton, a singular background, a disorder operator, or a state created by radial quantization. The unifying datum is magnetic flux through a linking two-sphere.

## Common pitfalls

**“A Dirac string is a physical string attached to the monopole.”**

Not in pure Dirac monopole theory. The string is a gauge artifact of using one patch. What is physical is the nontrivial bundle and its magnetic flux.

**“A non-Abelian monopole is singular because its long-distance field looks like a Dirac monopole.”**

The long-distance unbroken $U(1)$ field looks Abelian and monopolar, but the full Higgs and non-Abelian gauge fields are smooth at the core.

**“Monopoles are classified only by $\pi_2(G/H)$.”**

That is the first-pass smooth classical classification. The full quantum theory also depends on global form, allowed line operators, matter representations, theta angles, boundaries, and whether monopoles can be screened or confined.

**“Magnetic charge is just a number measured by $\nabla\cdot\mathbf B$.”**

In gauge theory, magnetic charge is more robustly a flux or bundle class on $S^2_\infty$. The local divergence equation is a coordinate-dependent shadow of global topology.

**“All gauge groups with the same Lie algebra have the same monopoles.”**

No. The global form of the gauge group changes the allowed electric and magnetic charge lattices. $SU(2)$ and $SO(3)$ share a Lie algebra but differ globally.

## Relations to other pages

Monopoles are the codimension-three entry in [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/). They are the natural next step after [Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/) because the linking sphere changes from $S^1$ to $S^2$.

They connect to [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/), where monopole-like singularities define magnetic line operators. They connect to [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) because magnetic flux conservation is naturally expressed in generalized-symmetry language.

They also prepare for [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) and [Theta Vacua: Preview](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/theta-vacua-preview/), since monopoles and instantons are two classic ways topology enters gauge theory.

## Exercises

### Exercise 1: Dirac quantization from patching

Let $A_N$ and $A_S$ be gauge potentials on northern and southern patches of $S^2$ with

$$
A_N-A_S=n\,d\varphi
$$

on the equatorial overlap. Show that a unit-charge field is single-valued only if $n\in\mathbb Z$, and compute the flux.

<details><summary><strong>Solution</strong></summary>

On the overlap, the two potentials differ by a gauge transformation

$$
A_N=A_S+d\lambda,
\qquad
\lambda=n\varphi.
$$

A unit-charge field transforms as

$$
\psi_N=e^{i\lambda}\psi_S.
$$

As $\varphi\to\varphi+2\pi$, single-valuedness requires

$$
e^{i n(\varphi+2\pi)}=e^{in\varphi},
$$

so

$$
e^{2\pi i n}=1,
\qquad
n\in\mathbb Z.
$$

The flux is

$$
\int_{S^2}F=\oint_{\rm equator}(A_N-A_S)=\int_0^{2\pi} n\,d\varphi=2\pi n.
$$

Thus $(2\pi)^{-1}\int F=n$.

</details>

### Exercise 2: Monopoles from the exact sequence

Use the homotopy sequence for

$$
U(1)\to SU(2)\to SU(2)/U(1)
$$

to show that

$$
\pi_2(SU(2)/U(1))\simeq\mathbb Z.
$$

<details><summary><strong>Solution</strong></summary>

The relevant part of the long exact sequence is

$$
\pi_2(SU(2))\to\pi_2(SU(2)/U(1))\to\pi_1(U(1))\to\pi_1(SU(2)).
$$

Since

$$
\pi_2(SU(2))=0,
\qquad
\pi_1(SU(2))=0,
\qquad
\pi_1(U(1))=\mathbb Z,
$$

exactness gives an isomorphism

$$
\pi_2(SU(2)/U(1))\simeq\pi_1(U(1))=\mathbb Z.
$$

Since $SU(2)/U(1)\simeq S^2$, this is also the familiar result $\pi_2(S^2)=\mathbb Z$.

</details>

### Exercise 3: Degree of the hedgehog

Show that the map

$$
\hat\Phi:S^2\to S^2,
\qquad
\hat\Phi(\hat r)=\hat r
$$

has degree one.

<details><summary><strong>Solution</strong></summary>

The map is the identity map on $S^2$. It preserves orientation and sends each point to itself. Therefore it has degree one.

Equivalently, if $\omega$ is the normalized area form on the target sphere with

$$
\int_{S^2}\omega=1,
$$

then

$$
\deg(\hat\Phi)=\int_{S^2}\hat\Phi^*\omega=\int_{S^2}\omega=1.
$$

</details>

### Exercise 4: BPS monopole bound

Assume the energy can be written as

$$
E={1\over 2g^2}\int d^3x\,(B_i^a-D_i\Phi^a)^2
+{1\over g^2}\int d^3x\,\partial_i(\Phi^a B_i^a).
$$

Show why the first-order equation

$$
B_i^a=D_i\Phi^a
$$

saturates the lower bound.

<details><summary><strong>Solution</strong></summary>

The square term is nonnegative. Therefore

$$
E\ge {1\over g^2}\int d^3x\,\partial_i(\Phi^a B_i^a).
$$

The right-hand side is a surface integral at spatial infinity:

$$
{1\over g^2}\int_{S^2_\infty} dS_i\,\Phi^a B_i^a.
$$

It depends only on the asymptotic Higgs direction and magnetic charge. If

$$
B_i^a=D_i\Phi^a,
$$

then the square term vanishes, so the energy equals the surface term. The solution saturates the topological lower bound.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §92. Solitons and monopoles in gauge theory.
- A. M. Polyakov, *Gauge Fields and Strings*, Ch. 6. Topology of gauge fields and instantons in non-Abelian gauge theories.
- M. Nakahara, *Geometry, Topology and Physics*, Chs. 1 and 4. Magnetic monopoles, homotopy groups, and topological defects.
- T. Frankel, *The Geometry of Physics*. Bundles, connections, Chern classes, magnetic monopoles, and instanton winding.
- S. Coleman, *Aspects of Symmetry*. Monopoles, spontaneous symmetry breaking, and semiclassical reasoning.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Detailed treatment of monopoles and moduli spaces.
- R. Rajaraman, *Solitons and Instantons*. Classic introduction to monopoles, instantons, and semiclassical methods.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Pedagogical notes on vortices, monopoles, and soliton moduli.

## Version history

- 2026-06-18: First polished draft. Added Dirac monopoles, bundle patching, ’t Hooft–Polyakov monopoles, exact homotopy sequence, BPS bound, dyons and theta-angle bridge, monopole-operator caveat, exercises, and references.
