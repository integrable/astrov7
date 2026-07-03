---
title: "Topology of Field Configurations"
description: "Explains how finite-energy or finite-action boundary conditions turn spaces of fields into topological sectors labeled by homotopy classes, fluxes, and characteristic classes."
sidebar:
  label: "Topology of Field Configurations"
  order: 1
level: Advanced
status: "Polished draft"
source: "Srednicki §§92–94; Polyakov Chs. 4 and 6; Coleman on solitons, monopoles, and instantons; Nakahara on homotopy groups and defects; Manton–Sutcliffe; Rajaraman."
topics:
  - field configuration space
  - finite energy boundary conditions
  - topological sectors
  - homotopy classes
  - topological charge
  - solitons
  - instantons
  - gauge bundles
canonicalTopics:
  - topology-of-field-configurations
  - finite-energy-configuration-space
  - topological-sector
  - homotopy-classification
  - topological-charge
researchStatus:
  established:
    - "With fixed boundary conditions and allowed smooth deformations, finite-energy field configurations can split into homotopy classes or gauge-bundle sectors."
    - "Topological charges are invariant under deformations that do not cross singular configurations, change boundary data, or change the allowed gauge quotient."
  active:
    - "Quantum effects, defects, global-form choices, dynamical charged objects, anomalies, and generalized symmetries can refine or change the naive classical classification."
---

## Summary

A field configuration is a whole function, connection, section, or bundle datum on space or spacetime. Once one imposes finite energy, finite action, boundary conditions, and gauge equivalence, the allowed configurations may split into disconnected pieces:

$$
\mathcal C
=\{\text{allowed field configurations}\}/\mathcal G
=\bigsqcup_Q \mathcal C_Q.
$$

The label $Q$ is a **topological charge** when it cannot change under smooth motion inside the allowed configuration space.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing configuration space split into disconnected components labeled by topological charge, with blocked paths between components.](/figures/symmetry-anomalies-topology/topology-of-field-configurations.svg)

<figcaption>

Configuration space can split into components labeled by topological charge. A smooth finite-energy deformation is a path inside the allowed configuration space; changing charge requires crossing a singular field, changing boundary data, passing through infinite energy, or otherwise leaving that space.

</figcaption>
</figure>

The most common pattern is

$$
\text{finite energy}
\Rightarrow
\text{asymptotic vacuum data}
\Rightarrow
\text{map from a sphere into a vacuum manifold}
\Rightarrow
\text{homotopy class}.
$$

For example, in $d$ spatial dimensions, if a scalar field approaches a fixed vacuum at spatial infinity, one may compactify

$$
\mathbb R^d\cup\{\infty\}\simeq S^d.
$$

Then a static finite-energy configuration can define a map

$$
S^d\longrightarrow \mathcal M_{\rm vac},
$$

and its sector may be labeled by an element of $\pi_d(\mathcal M_{\rm vac})$ or a related homotopy set.

Gauge theories add one crucial twist: the invariant topological data is not always the winding of a particular field written in a convenient gauge. It may instead be magnetic flux, a transition function, a principal-bundle class, a Chern number, or a defect linking number. In QFT, topology is always topology **after** specifying the allowed fields, boundary conditions, singularities, and gauge quotient.

## Prerequisites

You should know what a vacuum manifold is from [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) and [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/), and why gauge-equivalent configurations are not distinct physical configurations from [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/) and [Local Versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/).

You should also know the basic role of topological terms from [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) and [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/). The homotopy and bundle language is introduced here only as much as needed for QFT.

## Core idea

Topology enters QFT when the allowed field configurations are not all continuously connected. A deformation

$$
\phi_s(\mathbf x),
\qquad 0\le s\le 1,
$$

is allowed only if every intermediate configuration satisfies the same physical rules: finite energy, the same boundary condition, the same defect prescription, and the same gauge quotient. If no such path connects two configurations, they lie in different sectors.

That is the entire idea. The rest of the subject is learning how to compute the labels.

For scalar order parameters, the labels often come from homotopy groups of the vacuum manifold. For gauge fields, they often come from bundles and characteristic classes. For defects, they often come from maps on small spheres linking the defect. For Euclidean tunneling configurations, they often come from finite-action fields on compactified spacetime.

The slogan is

$$
\text{topological sector}
=\text{connected component of the allowed configuration space}.
$$

One should add three footnotes immediately. First, the configuration space can be singular or stratified, not a smooth manifold. Second, quantum theory can sum over sectors rather than choose one. Third, not every classical topological distinction survives unchanged after dynamical charged objects, boundaries, anomalies, or gauge identifications are included.

## Setup and conventions

Let $\Sigma$ be a spatial slice. For relativistic examples, one often takes

$$
\Sigma=\mathbb R^d
$$

with boundary conditions at spatial infinity. A static scalar configuration is a map

$$
\phi:\Sigma\to\mathcal T,
$$

where $\mathcal T$ is the target space of field values. If the theory has potential $V(\phi)$, the classical vacuum manifold is

$$
\mathcal M_{\rm vac}=\{\phi\in\mathcal T:V(\phi)=0\}
$$

or, more generally, the space of lowest-energy constant configurations modulo any gauge redundancy.

For a gauge theory, a configuration includes a connection $A$ and matter fields. The physical configuration space is schematically

$$
\mathcal C
=\{(A,\phi,\ldots)\text{ satisfying boundary and regularity conditions}\}/\mathcal G_{\rm allowed}.
$$

The phrase $\mathcal G_{\rm allowed}$ matters. Depending on boundary conditions, gauge transformations that approach the identity at infinity, gauge transformations that approach a constant global transformation, and large gauge transformations may play different roles. A careless quotient can erase or create fake sectors.

In Euclidean tunneling problems, the relevant space is often not static configurations on $\mathbb R^d$ but finite-action configurations on Euclidean spacetime. For Yang–Mills instantons in four Euclidean dimensions, one studies connections on compactified $\mathbb R^4\simeq S^4$ or, equivalently, finite-action gauge fields whose behavior at infinity determines a bundle class.

## Configuration space is the real object

Students often first meet topology through pictures of a kink, vortex, or monopole. That is useful, but the deeper object is the configuration space.

For a single particle moving on a circle, the configuration space is $S^1$. For a field, the configuration space is infinite-dimensional: every point of $\mathcal C$ is an entire field configuration. A path in $\mathcal C$ is a continuous one-parameter family of configurations.

Two configurations $\phi_0$ and $\phi_1$ lie in the same connected component if there exists a path

$$
\phi_s\in\mathcal C,
\qquad \phi_{s=0}=\phi_0,
\qquad \phi_{s=1}=\phi_1.
$$

If no such path exists, then $\phi_0$ and $\phi_1$ lie in different sectors.

This definition deliberately hides no physics. Whether a path is allowed depends on the problem:

- Does finite energy have to hold throughout the path?
- Are singular configurations allowed?
- Are defects inserted and held fixed?
- Are gauge transformations at infinity quotiented or treated as global symmetries?
- Are boundary conditions fixed or allowed to change?
- Are we classifying classical configurations, quantum states, or path-integral histories?

Changing any of these rules can change the topology of $\mathcal C$.

## Finite energy turns infinity into data

Consider a relativistic scalar field with static energy

$$
E[\phi]=\int_{\mathbb R^d} d^d x\,
\left[\frac12 |\nabla\phi|^2+V(\phi)\right],
$$

where $V\ge0$ and $V=0$ on $\mathcal M_{\rm vac}$. Finite energy requires the energy density to vanish at spatial infinity, so

$$
\nabla\phi\to0,
\qquad
V(\phi)\to0,
\qquad |\mathbf x|\to\infty.
$$

Thus the field approaches the vacuum manifold:

$$
\phi(\mathbf x)\to\phi_\infty(\hat{\mathbf x})\in\mathcal M_{\rm vac}.
$$

If the approach is independent of direction, then all of spatial infinity is identified to one point and

$$
\mathbb R^d\cup\{\infty\}\simeq S^d.
$$

The configuration is then a based or unbased map

$$
S^d\to \mathcal M_{\rm vac},
$$

depending on whether the value at infinity is fixed.

If the field at infinity depends on direction, then the boundary sphere itself carries data:

$$
\phi_\infty:S^{d-1}_\infty\to\mathcal M_{\rm vac}.
$$

That is the pattern for defects. For a line defect in three spatial dimensions, a small circle linking the line sees a map $S^1\to\mathcal M_{\rm vac}$. For a point defect in three spatial dimensions, a small sphere around the point sees a map $S^2\to\mathcal M_{\rm vac}$.

## Compactification of space and spacetime

There are two compactifications that appear constantly.

The first is **spatial compactification**. For static finite-energy solitons in $d$ spatial dimensions, one often obtains

$$
\Sigma=\mathbb R^d\quad\leadsto\quad S^d.
$$

This classifies particle-like textures in $d$ dimensions by maps $S^d\to\mathcal M$.

Examples include:

$$
\begin{array}{c|c|c}
\text{spatial dimension} & \text{map} & \text{typical object} \\
\hline
1 & S^1\to\mathcal M & \text{periodic winding, sometimes kinks with care} \\
2 & S^2\to\mathcal M & \text{sigma-model lumps} \\
3 & S^3\to\mathcal M & \text{Skyrmions and textures}
\end{array}
$$

The second is **Euclidean spacetime compactification**. For finite-action instantons in $D$ Euclidean dimensions, one often obtains

$$
\mathbb R^D\cup\{\infty\}\simeq S^D.
$$

For Yang–Mills theory in four Euclidean dimensions, finite action requires $F\to0$ at infinity, so the connection becomes pure gauge there. The behavior at infinity is encoded by a transition function

$$
g:S^3_\infty\to G,
$$

and the winding of $g$ is the instanton number for simple compact groups such as $SU(N)$.

The compactification step is powerful, but it is not automatic. It depends on the falloff conditions. Long-range fields, charged states, noncompact target spaces, finite density, boundary conditions, and massless gauge fields can make the compactification more subtle.

## Vacuum manifolds and homotopy labels

For spontaneous breaking

$$
G\to H,
$$

the classical vacuum manifold is often

$$
\mathcal M_{\rm vac}=G/H.
$$

Homotopy groups of $G/H$ then organize many classical topological sectors:

$$
\pi_n(G/H).
$$

The common dictionary is:

$$
\begin{array}{c|c|c}
\text{homotopy data} & \text{geometric situation} & \text{typical object} \\
\hline
\pi_0(\mathcal M_{\rm vac}) & \text{disconnected vacua} & \text{domain walls} \\
\pi_1(\mathcal M_{\rm vac}) & \text{loops around codimension-two defects} & \text{vortices, strings} \\
\pi_2(\mathcal M_{\rm vac}) & \text{spheres around codimension-three defects} & \text{monopoles} \\
\pi_3(\mathcal M_{\rm vac}) & \text{compactified three-space maps} & \text{Skyrmions, textures}
\end{array}
$$

This table is a guide, not a law of nature. The actual classification can involve relative homotopy groups, quotient stacks, bundle data, global-form choices, spin structures, or higher-form gauge fields.

The key point is that topology lives in the pair

$$
(\text{domain},\text{target}),
$$

not in the target alone. The same vacuum manifold can support different objects in different spacetime dimensions or with different defect codimensions.

## Defect linking spheres

A defect is often classified by looking at a sphere that links it. Suppose space has dimension $d$ and a defect has spatial dimension $p$. Then its codimension is

$$
\operatorname{codim}=d-p.
$$

A small sphere linking the defect has dimension

$$
k=d-p-1.
$$

If the fields away from the defect lie near $\mathcal M_{\rm vac}$, the defect carries data

$$
S^k_{\rm link}\to\mathcal M_{\rm vac},
$$

so the basic homotopy group is

$$
\pi_k(\mathcal M_{\rm vac}).
$$

This gives the familiar cases in three spatial dimensions:

$$
\begin{array}{c|c|c|c}
\text{object} & p & S^k_{\rm link} & \text{charge} \\
\hline
\text{domain wall} & 2 & S^0 & \pi_0(\mathcal M_{\rm vac}) \\
\text{vortex line} & 1 & S^1 & \pi_1(\mathcal M_{\rm vac}) \\
\text{monopole} & 0 & S^2 & \pi_2(\mathcal M_{\rm vac})
\end{array}
$$

The linking sphere viewpoint is the ancestor of the modern topological-operator viewpoint. A charge can be measured on a sphere surrounding the object; moving the sphere without crossing charged objects does not change the answer.

## Gauge fields and bundle data

Gauge theories require more care because gauge-related configurations are physically identical. A scalar field winding that looks nontrivial before quotienting may be pure gauge after quotienting. Conversely, a gauge field that looks locally trivial can carry nontrivial global bundle data.

The simplest example is magnetic flux in compact $U(1)$ gauge theory. Locally one writes $F=dA$, but globally $A$ may not be a single one-form on the whole sphere. Magnetic charge is measured by

$$
\frac{1}{2\pi}\int_{S^2}F\in\mathbb Z.
$$

This integer is not the winding of a globally defined scalar. It is the first Chern number of a line bundle over $S^2$.

For nonabelian Yang–Mills instantons in four Euclidean dimensions, with Hermitian generators normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

the instanton number is conventionally

$$
k=\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

on a closed four-manifold or with suitable finite-action boundary conditions.

:::note[Convention-sensitive source note]
The sign and normalization of $k$ depend on the orientation of $M_4$, the convention for Hermitian versus anti-Hermitian gauge fields, and the trace normalization. This volume usually uses Hermitian generators and $D=d-iA$, so $F=dA-iA\wedge A$. Whenever an instanton-number formula is used in a calculation, restate the trace and orientation conventions.
:::

A useful diagnostic is this: if the proposed topological number can be changed by a gauge transformation that is allowed as a redundancy, it is not a physical sector label. If it changes under a transformation that is instead a global or asymptotic symmetry, then the transformation may relate different charged sectors rather than identify them.

## Topological charge as an integral

Many topological charges can be written as integrals of differential forms. For a two-dimensional $O(3)$ sigma model with unit vector field

$$
\mathbf n(x,y)\in S^2,
\qquad \mathbf n\cdot\mathbf n=1,
$$

the winding number of a finite-energy map $S^2\to S^2$ is

$$
Q=\frac{1}{4\pi}\int d^2x\,
\mathbf n\cdot(\partial_x\mathbf n\times\partial_y\mathbf n)
\in\mathbb Z.
$$

For a Skyrme field $U(\mathbf x)\in SU(2)$ with $\mathbb R^3$ compactified to $S^3$, the winding number can be written

$$
B=\frac{1}{24\pi^2}\int_{\mathbb R^3}
\operatorname{tr}\!\bigl((U^{-1}dU)^3\bigr)
\in\mathbb Z,
$$

up to sign conventions for orientation and trace.

For Yang–Mills instantons, the charge is the second Chern number:

$$
k=\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F).
$$

These formulas look like ordinary integrals, but their integrality is not a miracle of calculus. It comes from global topology: the integrand is the pullback of a normalized volume form or characteristic class.

## Topological currents

Some topological charges can be packaged into identically conserved currents. In $1+1$ dimensions, for a real scalar field with two vacua at $\phi=\pm v$, one may define

$$
j^\mu_{\rm top}=\frac{1}{2v}\epsilon^{\mu\nu}\partial_\nu\phi.
$$

This current obeys

$$
\partial_\mu j^\mu_{\rm top}=0
$$

identically, not by the equations of motion. Its charge is

$$
Q_{\rm top}=\int dx\, j^0_{\rm top}
=\frac{\phi(+\infty)-\phi(-\infty)}{2v}.
$$

A kink has $Q_{\rm top}=1$, an antikink has $Q_{\rm top}=-1$, and a configuration returning to the same vacuum has $Q_{\rm top}=0$.

In gauge theory, the Bianchi identity similarly gives magnetic-flux conservation in the absence of magnetic defects:

$$
dF=0.
$$

In four spacetime dimensions, the corresponding magnetic one-form symmetry current is essentially $F/2\pi$ when the gauge field is compact and no magnetic charges are dynamical. This is the modern generalized-symmetry version of an old topological conservation law.

Topological currents can be exact locally and still have nonzero charges because the fields are not globally trivial or because the integration surface surrounds a defect.

## What topology protects

Topology protects against continuous unwinding inside a specified configuration space. If a sector label $Q$ is well-defined, then a smooth finite-energy path cannot change $Q$.

This gives a strong kinematic statement:

$$
Q[\phi_s]=\text{constant along every allowed path }\phi_s.
$$

But it is not the same as full dynamical stability. A topologically nontrivial configuration can still fail to be a stable finite-energy particle for several reasons.

First, the energy functional may have no finite-size minimum in the sector. Derrick’s theorem and its relatives often show that scalar solitons in more than one spatial dimension shrink or expand unless extra terms, gauge fields, time dependence, or constraints intervene.

Second, opposite charges can annihilate. A kink and antikink together have total charge zero and can decay to radiation if dynamics allows.

Third, a defect can end on another defect or on a boundary if the allowed configuration space includes that endpoint.

Fourth, quantum tunneling can mix sectors if the sectors are connected by finite-action Euclidean configurations. This is the logic behind theta vacua.

Fifth, dynamical charged objects can screen or violate a classical topological conservation law. For example, if magnetic monopoles are dynamical, magnetic flux through a sphere need not be conserved in the same way as in pure compact electrodynamics without monopole worldlines.

The safe statement is:

$$
\text{topology constrains dynamics; it does not replace dynamics}.
$$

## A library of first examples

The following table gives the most common prototypes. Later pages unpack them one by one.

| Object | Field-theoretic setting | Topological data | Typical charge |
|---|---|---|---|
| Kink | $1+1$ scalar with disconnected vacua | endpoints at $x=\pm\infty$ | $\pi_0(\mathcal M_{\rm vac})$ data |
| Domain wall | disconnected vacua in higher dimensions | map from linking $S^0$ | jump between components |
| Global vortex | broken $U(1)$ global symmetry | phase map $S^1\to U(1)$ | winding number $n\in\mathbb Z$ |
| Abrikosov–Nielsen–Olesen vortex | Abelian Higgs theory | magnetic flux and scalar winding | $\frac{1}{2\pi}\int F\in\mathbb Z$ |
| ’t Hooft–Polyakov monopole | $SU(2)\to U(1)$ Higgs phase | map $S^2_\infty\to S^2$ | magnetic charge $\in\mathbb Z$ |
| Sigma-model lump | $2d$ sigma model | map $S^2\to S^2$ or similar | degree of map |
| Skyrmion | chiral or sigma-model field in $3d$ | map $S^3\to SU(2)$ | winding / baryon number |
| Yang–Mills instanton | Euclidean $4d$ gauge theory | bundle over $S^4$ or $S^3_\infty\to G$ | $\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F)$ |
| Theta sector | quantum gauge theory with sectors $Q$ | superposition weighted by $e^{i\theta Q}$ | theta angle conjugate to $Q$ |

The table deliberately mixes solitons, defects, and instantons. The unifying point is not their dimension or dynamics. The unifying point is that field configurations have global data.

## Topological sectors in the path integral

In quantum theory, one often sums over sectors:

$$
Z=\sum_Q Z_Q.
$$

If the theory has a theta angle conjugate to $Q$, the sum becomes

$$
Z(\theta)=\sum_Q e^{i\theta Q}Z_Q
$$

in Lorentzian conventions, or with corresponding Euclidean weights after Wick rotation.

This formula is the abstract version of theta vacua in Yang–Mills theory and of many sigma-model theta terms. It says that a topological sector label can become a quantum interference phase.

The same structure also explains why total derivatives matter. If

$$
Q=\int dK
$$

is an integer on each sector, adding

$$
S_\theta=\theta Q
$$

does not change the local Euler–Lagrange equation inside a sector but changes the relative phase between sectors. That is physical whenever the quantum theory sums over those sectors or allows tunneling between classical vacua.

## Gauge quotient subtleties

A common trap is to classify fields before dividing by gauge transformations. The safer order is:

1. specify the fields and their allowed singularities;
2. impose finite-energy or finite-action boundary conditions;
3. specify which gauge transformations are redundancies;
4. form the quotient configuration space;
5. classify its connected components or bundle sectors.

For example, in a Higgs theory with gauge group $G$ broken to $H$, one often sees monopoles classified by

$$
\pi_2(G/H).
$$

But this statement assumes a particular global form of $G$, a particular spectrum of allowed matter, and a particular treatment of gauge transformations at infinity. More invariantly, monopole charges are magnetic charges compatible with the unbroken gauge group and with the allowed line operators.

Similarly, in Yang–Mills theory, a finite-action connection on $\mathbb R^4$ approaches a pure gauge at infinity:

$$
A\to i\, g^{-1}dg
$$

up to convention. The map $g:S^3_\infty\to G$ has winding number. But under a large gauge transformation, the Chern–Simons functional at infinity can shift by an integer. The instanton number is the gauge-invariant bundle datum; the boundary winding is one useful representative of it.

This is why topology and gauge theory are inseparable from global choices. The Lie algebra alone is often not enough.

## Common pitfalls

**Confusing field space with vacuum manifold.**  The vacuum manifold $\mathcal M_{\rm vac}$ is a finite-dimensional target of asymptotic values. The configuration space $\mathcal C$ is the infinite-dimensional space of fields on space, modulo gauge equivalence. Topological sectors are components of $\mathcal C$, often computed using maps into $\mathcal M_{\rm vac}$.

**Forgetting the boundary condition.**  The same local Lagrangian can have different sectors on $\mathbb R^d$, on a torus, on a manifold with boundary, or with different asymptotic falloff. Topology is not independent of the boundary problem.

**Classifying gauge artifacts.**  A winding number written in a gauge-fixed variable may not be gauge-invariant. Check whether allowed gauge transformations can change it.

**Thinking every integer integral is topological.**  Some integer-looking quantities are quantized by boundary conditions or equations of motion only in special limits. A genuine topological charge is invariant under smooth allowed deformations, not just quantized for a special ansatz.

**Ignoring singularities.**  Topological charge can change if fields pass through singular configurations. Whether that is allowed depends on the theory. A global vortex has a core where the order parameter leaves the vacuum manifold; a monopole can be smooth only because the Higgs field and gauge field behave appropriately near the origin.

**Treating classical classification as final.**  Quantum effects can lift moduli, generate tunneling, attach fermion zero modes, induce anomalies, or change which line and defect operators are allowed.

## Relations to other pages

This page prepares [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/), [Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/), [Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/), and [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/).

It relies conceptually on [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/) and [Nonlinear Sigma Models: Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/). It relies technically on [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/), [Quantization of Couplings](/symmetry-anomalies-topology/topological-terms/quantization-of-couplings/), and [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/).

Later, [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) will reinterpret many topological charges as charges measured by operators on linking spheres. [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) will explain when topological charge conservation is a higher-form symmetry.

## Research status

The classical topology of kinks, vortices, monopoles, sigma-model lumps, Skyrmions, and Yang–Mills instantons is mature. The basic homotopy classifications and characteristic-class formulas are standard tools.

What remains subtle is not the elementary classification itself but its exact role in a full quantum theory. Important refinements include:

- global form of the gauge group and allowed line operators;
- dynamical charged objects that screen or break higher-form symmetries;
- fermion zero modes attached to solitons and instantons;
- anomaly inflow on defects;
- theta-angle periodicity and time-reversal anomalies;
- boundary conditions and edge degrees of freedom;
- non-invertible and categorical symmetry structures;
- lattice or UV-complete definitions of continuum sectors;
- cobordism refinements of fermionic and reflection-protected sectors.

A good working attitude is: compute the classical topological sectors first, then ask which of them survive the quantum definition of the theory.

## Exercises

### Exercise 1: Kink charge in a double-well model

Let $\phi(x)$ be a real scalar field in one spatial dimension with vacua at $\phi=\pm v$. Finite energy requires $\phi(\pm\infty)\in\{+v,-v\}$. Define

$$
Q=\frac{\phi(+\infty)-\phi(-\infty)}{2v}.
$$

What values can $Q$ take? Which sectors contain a kink and an antikink?

<details><summary><strong>Solution</strong></summary>

Since each endpoint is either $+v$ or $-v$, the possible values are

$$
Q\in\{-1,0,1\}.
$$

If

$$
\phi(-\infty)=-v,
\qquad \phi(+\infty)=+v,
$$

then $Q=1$; this is the kink sector. If

$$
\phi(-\infty)=+v,
\qquad \phi(+\infty)=-v,
$$

then $Q=-1$; this is the antikink sector. If both endpoints are the same, then $Q=0$.

The charge cannot change under a smooth finite-energy deformation with fixed vacua at infinity, because changing it would require changing at least one endpoint.

</details>

### Exercise 2: Vortex winding from the phase at infinity

Let a complex scalar field in two spatial dimensions have vacuum manifold $U(1)$. At large radius, write

$$
\phi(r,\varphi)\simeq v e^{i\alpha(\varphi)}.
$$

Show that the integer

$$
n=\frac{1}{2\pi}\int_0^{2\pi}d\varphi\,\frac{d\alpha}{d\varphi}
$$

labels the winding of the boundary map $S^1_\infty\to U(1)$.

<details><summary><strong>Solution</strong></summary>

The phase at infinity defines a continuous map from the angular circle to the vacuum circle:

$$
S^1_\infty\to U(1),
\qquad
\varphi\mapsto e^{i\alpha(\varphi)}.
$$

Single-valuedness requires

$$
e^{i\alpha(2\pi)}=e^{i\alpha(0)},
$$

so

$$
\alpha(2\pi)-\alpha(0)=2\pi n
$$

for some $n\in\mathbb Z$. Therefore

$$
\frac{1}{2\pi}\int_0^{2\pi}d\varphi\,\frac{d\alpha}{d\varphi}
=\frac{\alpha(2\pi)-\alpha(0)}{2\pi}=n.
$$

This integer is the degree of the map $S^1\to S^1$, namely an element of $\pi_1(U(1))\simeq\mathbb Z$.

</details>

### Exercise 3: A topological current that is conserved without equations of motion

For the $1+1$ dimensional scalar kink setup, define

$$
j^\mu_{\rm top}=\frac{1}{2v}\epsilon^{\mu\nu}\partial_\nu\phi.
$$

Show that $\partial_\mu j^\mu_{\rm top}=0$ identically.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu_{\rm top}
=\frac{1}{2v}\epsilon^{\mu\nu}\partial_\mu\partial_\nu\phi.
$$

The tensor $\epsilon^{\mu\nu}$ is antisymmetric in $\mu$ and $\nu$, while $\partial_\mu\partial_\nu\phi$ is symmetric for smooth fields. Their contraction vanishes:

$$
\epsilon^{\mu\nu}\partial_\mu\partial_\nu\phi=0.
$$

No Euler–Lagrange equation was used. The conservation law is topological or kinematic.

</details>

### Exercise 4: Why a total derivative can give an integer

Let $U(\mathbf x):S^3\to SU(2)$ be a smooth map. The three-form

$$
\omega_3=\frac{1}{24\pi^2}\operatorname{tr}\bigl((U^{-1}dU)^3\bigr)
$$

is normalized so that

$$
B=\int_{S^3}\omega_3\in\mathbb Z.
$$

Why is it misleading to say that $B$ must vanish because locally closed forms are locally exact?

<details><summary><strong>Solution</strong></summary>

Local exactness does not imply global exactness. A closed form can fail to be globally exact when the domain has nontrivial cohomology. The integral

$$
\int_{S^3}\omega_3
$$

pairs a cohomology class on $SU(2)\simeq S^3$ with the fundamental class of the domain $S^3$. It measures the degree of the map $U:S^3\to S^3$.

Equivalently, even if one writes local potentials for $\omega_3$ on patches, the patching data contributes globally. This is the same reason Chern–Simons forms and theta terms can affect physics even when their densities are locally total derivatives.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§92–94. Solitons, monopoles, instantons, and theta vacua.
- S. Coleman, *Aspects of Symmetry*. Magnetic monopoles, instantons, and semiclassical viewpoints.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4 and 6. Compact gauge fields, instantons, and topology of gauge fields.
- R. Rajaraman, *Solitons and Instantons*. Classic detailed treatment of kinks, vortices, monopoles, instantons, and collective coordinates.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Comprehensive modern reference for solitons and topology.
- M. Nakahara, *Geometry, Topology and Physics*. Homotopy groups, defects, magnetic monopoles, instantons, bundles, and characteristic classes.
- T. Frankel, *The Geometry of Physics*. Differential forms, bundles, characteristic classes, and gauge-field topology.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Ch. 8. Homotopy, theta terms, Wess–Zumino terms, and topological field theory in matter systems.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Friendly lecture notes with many standard examples.

## Version history

- 2026-06-18: First polished draft. Added finite-energy configuration-space definition, compactification logic, homotopy and gauge-bundle classification, examples, topological currents, path-integral sectors, pitfalls, exercises, and references.
