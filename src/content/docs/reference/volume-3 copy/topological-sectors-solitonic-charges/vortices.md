---
title: "Vortices"
description: "Explains vortices as codimension-two topological defects, including winding number, global vortices, Abelian Higgs flux tubes, flux quantization, BPS vortices, and QFT caveats."
sidebar:
  label: "Vortices"
  order: 4
level: Advanced
status: "Polished draft"
source: "Srednicki §92; Polyakov Chs. 4–6; Nakahara Ch. 4; Altland–Simons Ch. 8; Manton–Sutcliffe; Rajaraman; Tong TASI soliton notes."
topics:
  - vortices
  - topological defects
  - winding number
  - Abelian Higgs model
  - flux quantization
  - Nielsen–Olesen vortex
  - global vortex
  - BPS vortex
canonicalTopics:
  - vortex
  - codimension-two-defect
  - abelian-higgs-vortex
  - flux-quantization
  - vortex-winding-number
researchStatus:
  established:
    - "Classical vortices in scalar and Higgs theories are codimension-two defects whose first-pass topological charge is a winding number on a linking circle."
    - "In a compact Abelian Higgs theory with a unit-charge condensate, finite-energy vortex sectors carry quantized magnetic flux."
  active:
    - "Quantum vortices remain central in modern work on dualities, confinement mechanisms, superconductivity, cosmic strings, non-Abelian strings, generalized symmetries, and topological phases."
---

## Summary

A vortex is a codimension-two topological defect. In three spatial dimensions it is a string-like object; in two spatial dimensions it is a point-like defect. The diagnostic is always the same: take a small circle linking the defect. If the field winds nontrivially around the vacuum manifold as one goes around that circle, the defect cannot be removed by a smooth finite-energy deformation.

For the simplest complex scalar with vacuum manifold $S^1$, the vortex number is

$$
n={1\over 2\pi}\oint_{S^1_{\rm link}} d\alpha,
\qquad
\phi\simeq v e^{i\alpha}.
$$

This is the prototype of the slogan

$$
\text{vortex charge}
=\text{winding of a linking circle}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a vortex linking circle, its map to a vacuum circle, and the conversion of winding into quantized flux in a gauged vortex.](/figures/symmetry-anomalies-topology/vortex-winding-flux-map.svg)

<figcaption>

A vortex is detected by a circle surrounding its core. For a global $U(1)$ order parameter, the phase winding produces a long-range Goldstone gradient. If the $U(1)$ is gauged, the gauge field can screen that gradient and the same integer becomes magnetic flux.

</figcaption>
</figure>

There are two basic species.

A **global vortex** occurs when the winding is in a physical global order parameter. It has a long-range Goldstone tail. In two spatial dimensions its energy grows logarithmically with system size.

A **local vortex** or **gauge vortex** occurs when the winding is in a Higgs field charged under a compact gauge field. The gauge field cancels the phase gradient at infinity. The result is a finite-tension magnetic flux tube, often called the Abelian Higgs vortex or Nielsen–Olesen vortex.

This distinction is physically decisive: it determines whether the vortex is a logarithmically costly global defect, a finite-tension string, a confining flux tube, a superconducting flux line, a cosmic string candidate, or an operator insertion in a lower-dimensional QFT.

## Prerequisites

You should know the boundary-map viewpoint from [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/), the homotopy dictionary from [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), and the degree/winding formulas from [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/).

For the Higgs version, you should also know [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), and the [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/).

## Core idea

A vortex is a defect whose transverse space contains a circle.

Let $\Sigma$ be a spatial slice of dimension $d$, and let the vortex have spatial dimension $p=d-2$. A small sphere linking a codimension-two defect is

$$
S^{d-p-1}=S^1.
$$

If the finite-energy condition forces the field to land in a vacuum manifold $\mathcal M_{\rm vac}$ on that circle, the boundary data define a map

$$
\phi_{\rm link}:S^1\to \mathcal M_{\rm vac}.
$$

The first-pass topological classification is therefore

$$
[\phi_{\rm link}]\in \pi_1(\mathcal M_{\rm vac}).
$$

For a broken $U(1)$ symmetry,

$$
\mathcal M_{\rm vac}\simeq S^1,
\qquad
\pi_1(S^1)=\mathbb Z.
$$

The integer is the winding number. The vortex core is where the vacuum description fails. For a complex scalar, the field must pass through $\phi=0$ somewhere inside the linking circle if the winding is nonzero. Equivalently, the field cannot unwind while remaining everywhere on the vacuum circle.

## Setup and conventions

We use the volume convention that a unit-charge scalar coupled to a compact $U(1)$ gauge field has

$$
D_\mu\phi=(\partial_\mu-iA_\mu)\phi,
\qquad
\exp\!\left(i\oint A\right)
$$

as the minimal Wilson phase. With this normalization, flux quantization is naturally written

$$
\int F\in 2\pi\mathbb Z.
$$

When comparing to texts that write $D_\mu=\partial_\mu-iqA_\mu$, the same statement becomes

$$
q\int F\in 2\pi\mathbb Z,
\qquad
\Phi_B={2\pi n\over q}.
$$

:::note[Convention-sensitive source note]
Vortex flux formulas are notation-sensitive because authors distribute the charge between the covariant derivative, the gauge field, and the gauge kinetic term. This page uses the compact gauge-field normalization in which the minimal charge is one and $\int F=2\pi n$. If you use $D=d-iqA$, insert a factor of $1/q$ in the flux.
:::

For static configurations in the plane transverse to the vortex, write polar coordinates

$$
(r,\theta),
\qquad
0\le \theta<2\pi.
$$

A unit-winding scalar profile has asymptotic form

$$
\phi(r,\theta)\longrightarrow v e^{i\theta}
\qquad r\to\infty.
$$

More generally,

$$
\phi(r,\theta)\longrightarrow v e^{in\theta},
\qquad n\in\mathbb Z.
$$

The integer $n$ is the vortex number.

## Global U(1) vortex

Start with a relativistic complex scalar field with Lagrangian

$$
\mathcal L
=\partial_\mu\phi^*\partial^\mu\phi
-{\lambda\over 2}(|\phi|^2-v^2)^2.
$$

The vacuum manifold is

$$
|\phi|=v,
\qquad
\mathcal M_{\rm vac}\simeq S^1.
$$

For a static configuration in two spatial dimensions, the energy is

$$
E=\int d^2x\left(|\nabla\phi|^2+{\lambda\over 2}(|\phi|^2-v^2)^2\right).
$$

A winding-$n$ ansatz is

$$
\phi(r,\theta)=f(r)e^{in\theta},
\qquad
f(0)=0,
\qquad
f(\infty)=v.
$$

The boundary condition $f(0)=0$ is not optional for $n\ne0$. Smoothness near the origin forces the phase to become meaningless at the core. If $f$ stayed nonzero everywhere, the phase map on the linking circle could not be filled in by a smooth disk.

At large $r$, the radial profile is nearly $v$, so the angular gradient gives

$$
|\nabla\phi|^2
\simeq v^2 |\nabla(n\theta)|^2
={v^2 n^2\over r^2}.
$$

Therefore the energy in a disk of radius $R$ has a logarithmic tail,

$$
E(R)
\sim \int_a^R 2\pi r\,dr\,{v^2 n^2\over r^2}
=2\pi v^2 n^2\log {R\over a},
$$

up to convention-dependent factors of $2$ depending on whether the kinetic term is written $|\partial\phi|^2$ or ${1\over2}|\partial\phi|^2$ for real components. The physical point is robust: an isolated global vortex has a long-range Goldstone gradient and logarithmically divergent energy per unit length.

In a finite system this is perfectly meaningful. In an infinite system an isolated global vortex is too expensive, but vortex–antivortex pairs can have finite energy at large separation up to a logarithmic interaction. This logarithmic interaction is the seed of Berezinskii–Kosterlitz–Thouless physics in two-dimensional systems.

## Local vortex in the Abelian Higgs model

Now gauge the $U(1)$. A convenient normalization is

$$
\mathcal L
=-{1\over 4e^2}F_{\mu\nu}F^{\mu\nu}
+|D_\mu\phi|^2
-{\lambda\over 2}(|\phi|^2-v^2)^2,
\qquad
D_\mu=\partial_\mu-iA_\mu.
$$

For a static string along the $z$-axis, the transverse energy per unit length is

$$
T=\int d^2x\left[
{1\over 2e^2}B^2
+|D_i\phi|^2
+{\lambda\over 2}(|\phi|^2-v^2)^2
\right],
\qquad
B=F_{12}.
$$

Finite energy requires

$$
|\phi|\to v,
\qquad
D_i\phi\to0,
\qquad
B\to0
\qquad r\to\infty.
$$

For

$$
\phi\to v e^{in\theta},
$$

the condition $D_\theta\phi\to0$ gives

$$
(\partial_\theta-iA_\theta)\phi\to0
\quad\Longrightarrow\quad
A_\theta\to n.
$$

Equivalently,

$$
\oint_{S^1_\infty} A=2\pi n.
$$

By Stokes's theorem, the magnetic flux through the transverse plane is

$$
\Phi_B=\int_{\mathbb R^2} F
=\oint_{S^1_\infty}A
=2\pi n.
$$

So the vortex winding has become quantized magnetic flux.

This is the Abelian Higgs vortex. In particle-physics language it is the Nielsen–Olesen string. In condensed-matter language it is the Abrikosov flux line of a type-II superconductor. In the dual-superconductor picture of confinement, closely related flux tubes are responsible for linearly confining electric charges. The same topological mechanism therefore appears in several distinct physical regimes.

## Why the gauge field makes the tension finite

For a global vortex, the large-distance angular gradient is physical:

$$
\partial_i\alpha\sim {n\over r}.
$$

For a local vortex, the physical gradient is the covariant one:

$$
D_i\phi\sim i(\partial_i\alpha-A_i)\phi.
$$

At infinity the gauge field can approach a pure gauge,

$$
A_i\sim \partial_i\alpha,
$$

so that

$$
D_i\phi\to0.
$$

The magnetic field

$$
B=\partial_1A_2-\partial_2A_1
$$

is localized near the core, where the gauge field interpolates between regularity at $r=0$ and the asymptotic pure gauge. The vortex tension is finite because there is no long-range Goldstone tail. The gauge field ate the Goldstone mode, and the vortex remembers the winding as magnetic flux.

This is one of the cleanest places to see why gauge redundancy changes the topology problem. The phase winding by itself is not a gauge-invariant local observable, but the holonomy and flux are.

## A standard radial ansatz

For a straight Abelian Higgs vortex of winding $n$, use

$$
\phi(r,\theta)=v f(r)e^{in\theta},
\qquad
A=n a(r)d\theta.
$$

Regularity and finite energy require

$$
f(0)=0,
\qquad
a(0)=0,
\qquad
f(\infty)=1,
\qquad
a(\infty)=1.
$$

The magnetic field is

$$
F=dA=n a'(r)\,dr\wedge d\theta.
$$

The flux is then

$$
\int F
=\int_0^{2\pi}\!d\theta\int_0^\infty\!dr\, n a'(r)
=2\pi n[a(\infty)-a(0)]
=2\pi n.
$$

Notice the logic: the core regularity condition and the infinity condition together force the flux.

## BPS vortices

At the critical coupling

$$
\lambda=e^2,
$$

with the normalization above, the Abelian Higgs energy can be written as a sum of squares plus a topological term:

$$
T
=\int d^2x\left[
{1\over 2e^2}\left(B\mp e^2(v^2-|\phi|^2)\right)^2
+\left| (D_1\pm iD_2)\phi\right|^2
\right]
\pm v^2\int F.
$$

Therefore

$$
T\ge 2\pi v^2 |n|.
$$

Configurations saturating the bound obey the first-order vortex equations

$$
(D_1\pm iD_2)\phi=0,
\qquad
B=\pm e^2(v^2-|\phi|^2).
$$

These are the Bogomolny equations. They are important not just because they simplify classical solutions, but because they reveal a moduli-space structure: at BPS coupling, multi-vortex solutions can often be described by collective coordinates, such as the positions of individual vortices.

:::note[Convention-sensitive source note]
The BPS condition is often written with a different factor, such as $\lambda=e^2/2$, because the scalar potential may be normalized as $\lambda(|\phi|^2-v^2)^2$ rather than $\lambda(|\phi|^2-v^2)^2/2$, and the gauge kinetic term may be $-F^2/4$ rather than $-F^2/(4e^2)$. The invariant content is the equality of scalar and vector masses at critical coupling.
:::

## Homotopy classification and gauge refinement

For a global $U(1)$ vortex, the classification is directly

$$
\pi_1(S^1)=\mathbb Z.
$$

For a gauged $U(1)$ vortex, saying “$\pi_1(S^1)$” is useful but incomplete. The vacuum manifold of gauge-equivalent Higgs phases is not a physical space of distinct vacua in the same way. The gauge-invariant statement is instead that the Higgs field defines a winding of the gauge transformation at infinity, or equivalently a principal $U(1)$ bundle/connection with quantized holonomy and flux.

If the Higgs field has charge $q$ rather than unit charge, then the unbroken group can include a finite subgroup. A charge-$q$ condensate leaves a $\mathbb Z_q$ gauge theory at low energies, and vortices can carry flux

$$
\oint A={2\pi n\over q}
$$

in the convention where the underlying minimal electric charge is one. This is the doorway to discrete gauge theory, Aharonov–Bohm phases, and higher-form symmetry.

The moral is:

$$
\text{global vortex: winding of a physical order parameter},
$$

while

$$
\text{gauge vortex: holonomy/flux of a compact gauge field plus Higgs boundary data}.
$$

## Vortices as charged objects for higher-form symmetries

In four-dimensional Abelian Higgs theory, vortex strings are extended line-like excitations in space. They can be charged under a two-form current or, in dual language, can couple to a two-form gauge field. This is one of the bridges from old-fashioned soliton physics to modern generalized symmetry.

In the Higgs phase, electric charges may be screened, but magnetic flux tubes can remain as stable or metastable extended objects depending on the spectrum of allowed monopoles, charged matter, and global form of the gauge group. Once dynamical monopoles are included, vortex strings can end on monopoles. Then the would-be vortex number is no longer absolutely conserved. Topology never works in isolation; it works in the specified QFT.

## Common pitfalls

**“A vortex is just where the field vanishes.”**

The vanishing core is not the definition. It is the consequence of nontrivial winding plus smoothness. A random zero of a complex scalar need not be a topological vortex.

**“The phase winding of a gauge vortex is gauge invariant.”**

Not by itself. The gauge-invariant data are the holonomy, flux, and behavior of charged probes. A gauge can move the phase winding from the Higgs field into the gauge field.

**“Every vortex has finite energy.”**

Global vortices have long-range Goldstone gradients and logarithmic energy per unit length in two transverse dimensions. Gauge vortices can have finite tension because the gauge field screens the gradient.

**“Flux quantization is local.”**

Flux quantization is global. It comes from compactness, single-valued charged fields, transition functions, and the topology of the circle at infinity.

**“A nonzero $\pi_1$ guarantees an absolutely stable vortex in the full quantum theory.”**

It guarantees a classical topological obstruction under a specified set of allowed deformations. Quantum tunneling, endpoints, dynamical charged objects, boundaries, explicit breaking, and changing the global form can modify the conservation law.

## Relations to other pages

Vortices are the codimension-two entry in the defect dictionary of [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/). They are the simplest topological objects controlled by $\pi_1$ and winding number.

They connect directly to [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) and [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) once gauge probes are included. They also foreshadow [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/), because flux tubes and line operators are natural charged extended objects.

In condensed-matter language, vortices are central to superfluidity, superconductivity, and the BKT transition. In gauge theory, they are prototypes for confining strings and flux tubes. In two-dimensional Euclidean QFT, vortices can also appear as instanton-like events in the path integral.

## Exercises

### Exercise 1: Winding forces a zero

Let $\phi:D^2\to\mathbb C$ be continuous and nonzero everywhere on the disk. Show that the phase map on the boundary $S^1=\partial D^2$ has winding number zero.

<details><summary><strong>Solution</strong></summary>

If $\phi$ is nonzero everywhere on $D^2$, then

$$
u(x)={\phi(x)\over |\phi(x)|}
$$

defines a continuous map

$$
\nu:D^2\to S^1.
$$

Its restriction to the boundary is the boundary phase map. But any map from $S^1$ that extends to the disk is null-homotopic, because the disk supplies the homotopy that contracts the boundary circle. Therefore the boundary winding is zero. Hence a nonzero boundary winding forces $\phi=0$ somewhere inside the disk.

</details>

### Exercise 2: Flux quantization from finite energy

In the unit-charge Abelian Higgs model, suppose

$$
\phi\to v e^{in\theta},
\qquad
D_\theta\phi\to0
$$

at infinity. Show that

$$
\int F=2\pi n.
$$

<details><summary><strong>Solution</strong></summary>

At infinity,

$$
D_\theta\phi=(\partial_\theta-iA_\theta)\phi
\to i(n-A_\theta)\phi.
$$

Since $|\phi|\to v\ne0$, finite energy requires

$$
A_\theta\to n.
$$

Thus

$$
\oint_{S^1_\infty}A
=\int_0^{2\pi} A_\theta\,d\theta
=2\pi n.
$$

By Stokes's theorem,

$$
\int_{\mathbb R^2}F=\oint_{S^1_\infty}A=2\pi n.
$$

</details>

### Exercise 3: Logarithmic energy of a global vortex

Estimate the large-radius energy of a global vortex with

$$
\phi\simeq v e^{in\theta}
$$

outside a core of radius $a$.

<details><summary><strong>Solution</strong></summary>

At large $r$,

$$
|\nabla\phi|^2\simeq v^2|\nabla(n\theta)|^2={v^2n^2\over r^2}.
$$

The energy between radii $a$ and $R$ is therefore

$$
E(R)
\sim \int_a^R 2\pi r\,dr\,{v^2n^2\over r^2}
=2\pi v^2n^2\log {R\over a}.
$$

The exact coefficient depends on kinetic-term normalization, but the logarithmic growth does not.

</details>

### Exercise 4: BPS tension

Using the BPS completion in this page, show that a positive-flux vortex satisfying

$$
(D_1+iD_2)\phi=0,
\qquad
B=e^2(v^2-|\phi|^2)
$$

has tension

$$
T=2\pi v^2 n.
$$

<details><summary><strong>Solution</strong></summary>

At critical coupling, the energy is a sum of nonnegative squares plus

$$
v^2\int F.
$$

For a solution of the first-order equations, the squares vanish. Thus

$$
T=v^2\int F=v^2(2\pi n)=2\pi v^2n.
$$

For negative flux one chooses the opposite sign and obtains $T=2\pi v^2|n|$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §92. Solitons and monopoles, with the Abelian Higgs vortex as a standard topological defect example.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4–6. Compact Abelian systems, vortices, instantons, and gauge-field topology.
- M. Nakahara, *Geometry, Topology and Physics*, Ch. 4. Homotopy classification of defects, including vortices and monopoles.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8. Homotopy, theta terms, Wess–Zumino terms, Chern–Simons terms, and topological matter examples.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Detailed treatment of vortices, monopoles, Skyrmions, and moduli spaces.
- R. Rajaraman, *Solitons and Instantons*. Classic introduction to kinks, vortices, monopoles, instantons, and semiclassical methods.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Pedagogical notes with a clean discussion of vortices and the Abelian Higgs model.

## Version history

- 2026-06-18: First polished draft. Added global and Abelian Higgs vortices, winding, flux quantization, finite-energy conditions, BPS equations, gauge-normalization caveats, higher-form symmetry bridge, exercises, and references.
