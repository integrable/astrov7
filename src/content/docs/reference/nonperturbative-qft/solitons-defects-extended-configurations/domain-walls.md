---
title: "Domain Walls"
description: "Explains domain walls as finite-tension codimension-one defects separating distinct vacua, including their profile, tension, zero mode, and worldvolume dynamics."
sidebar:
  label: "Domain Walls"
  order: 3
level: Graduate
status: "Polished draft"
source: "Shifman, ch. 2 and sec. 11.4; Coleman, 'Classical lumps and their quantum descendants'; Srednicki, ch. 92."
topics:
  - domain walls
  - codimension-one defects
  - wall tension
  - degenerate vacua
  - Bogomolnyi bound
  - worldvolume effective theory
  - junctions
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - domain-walls
  - topological-defects
researchStatus:
  established:
    - "Classical domain walls are finite-tension codimension-one configurations interpolating between distinct degenerate vacua, with a translational zero mode and a low-energy worldvolume description."
  active:
    - "Domain walls in strongly coupled gauge theories, supersymmetric theories, cosmology, condensed matter, and theories with generalized symmetries can carry rich localized degrees of freedom and model-dependent junction dynamics."
---

## Summary

A **domain wall** is a codimension-one defect separating two spatial regions that approach different vacua. If the vacua are exactly degenerate, a flat static wall can have finite tension. In $3+1$ dimensions, a planar wall extended in the $x$ and $y$ directions has a profile in the transverse coordinate $z$,

$$
\phi(z\to -\infty)=\phi_-,
\qquad
\phi(z\to +\infty)=\phi_+,
\qquad
\phi_-\neq\phi_+,
$$

and tension

$$
T
=
\int_{-\infty}^{\infty}dz
\left[
\frac12\left(\frac{d\phi}{dz}\right)^2+V(\phi)
\right].
$$

For the double-well theory

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac{\lambda}{4}(\phi^2-v^2)^2,
$$

the wall profile is the lifted kink,

$$
\phi_w(z;Z)
=
v\tanh\frac{m(z-Z)}{2},
\qquad
m^2=2\lambda v^2,
$$

and the tension is

$$
T
=
\frac{2}{3}m v^2
=
\frac{2\sqrt2}{3}\sqrt\lambda\,v^3.
$$

The formula is the same as the kink mass because the wall is a kink in the transverse direction, repeated at every point of its worldvolume. The physical distinction is dimensional: the $1+1$-dimensional kink is a particle, while the $3+1$-dimensional domain wall is an extended object with energy proportional to area.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A domain wall as a codimension-one interface separating two vacua, together with its transverse field profile and localized energy density.](/figures/nonperturbative-qft/domain-wall-tension-profile.svg)

<figcaption>

A domain wall is a finite-tension codimension-one interface. For a flat wall, the field depends only on the transverse coordinate $z$. The tension $T$ is the energy per unit worldvolume, obtained by integrating the localized energy density across the wall core.

</figcaption>
</figure>

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

## Core idea

A domain wall is the codimension-one version of a kink. The transverse space is one-dimensional, so the boundary at transverse infinity is

$$
S^0_\infty=\{-\infty,+\infty\}.
$$

Finite tension forces the fields on each side of the wall to approach vacuum data. If the two sides approach different disconnected vacua, the wall cannot simply fade away in infinite volume while preserving those asymptotic boundary conditions.

The difference from a kink is not the local profile but the number of directions along the object. In $d$ spatial dimensions, a codimension-one wall has $d-1$ spatial worldvolume directions. Its total energy in infinite space is infinite, but the physically meaningful quantity is the tension:

$$
T=\frac{E}{\text{wall area}}.
$$

This distinction is more than bookkeeping. Domain walls have low-energy excitations that move along the wall, can bend, can form networks and junctions, and can support localized fields. The wall is a lower-dimensional system embedded in the original QFT.

## Setup and conventions

Let spacetime dimension be $D=d+1$. A flat static wall will be taken to extend along

$$
x^\alpha=(t,x^1,\ldots,x^{d-1}),
$$

with transverse coordinate

$$
z=x^d.
$$

For one real scalar field,

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-V(\phi),
$$

and a flat static wall has

$$
\phi=\phi_w(z).
$$

The tension is

$$
T[\phi_w]
=
\int dz
\left[
\frac12\left(\frac{d\phi_w}{dz}\right)^2+V(\phi_w)
\right].
$$

For the double-well model,

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
\qquad
\mathcal M_{\rm vac}=\{-v,+v\}.
$$

The wall boundary conditions are

$$
\phi_w(-\infty)=-v,
\qquad
\phi_w(+\infty)=+v.
$$

The antiwall has the boundary conditions reversed.

## Wall equation and profile

The Euler–Lagrange equation for the static wall is

$$
\frac{d^2\phi_w}{dz^2}=V'(\phi_w).
$$

For the double-well potential this becomes

$$
\frac{d^2\phi_w}{dz^2}
=
\lambda\phi_w(\phi_w^2-v^2).
$$

As for the kink, one may integrate once. The mechanical analogy gives the conserved quantity

$$
\frac12\left(\frac{d\phi_w}{dz}\right)^2-V(\phi_w)=0,
$$

where the constant is zero because $\phi_w'$ and $V$ both vanish as $z\to\pm\infty$. Hence the wall obeys the first-order equation

$$
\frac{d\phi_w}{dz}
=
\sqrt{\frac{\lambda}{2}}(v^2-\phi_w^2)
$$

for the wall from $-v$ to $+v$. The solution is

$$
\phi_w(z;Z)
=
v\tanh\left[\sqrt{\frac{\lambda}{2}}v(z-Z)\right]
=
v\tanh\frac{m(z-Z)}{2}.
$$

The parameter $Z$ is the transverse position of the wall. Choosing $Z$ breaks translations in the transverse direction, while translations along the wall remain unbroken.

The wall thickness is set by the inverse mass of small fluctuations in either vacuum:

$$
\ell\sim m^{-1}.
$$

This is only a parametric statement. Different conventions define the numerical thickness in different ways, for example by the width of the energy-density peak or by the distance over which $\phi$ changes from $-0.9v$ to $+0.9v$.

## Tension and Bogomolnyi bound

If the potential can be written as

$$
V(\phi)=\frac12\left(W'(\phi)\right)^2,
$$

then the tension can be rearranged as

$$
T
=
\int dz\,
\frac12\left(\frac{d\phi}{dz}-W'(\phi)\right)^2
+W(\phi(+\infty))-W(\phi(-\infty)).
$$

Therefore

$$
T\ge |\Delta W|,
\qquad
\Delta W=W(\phi_+)-W(\phi_-),
$$

with equality when

$$
\frac{d\phi}{dz}=W'(\phi)
$$

or with the opposite sign for the antiwall.

For the double-well theory, choose

$$
W'(\phi)=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2),
\qquad
W(\phi)=\sqrt{\frac{\lambda}{2}}\left(v^2\phi-\frac{\phi^3}{3}\right).
$$

Then

$$
T
=W(+v)-W(-v)
=
\frac{2\sqrt2}{3}\sqrt\lambda\,v^3
=
\frac{2}{3}mv^2.
$$

This is the energy per unit area in $3+1$ dimensions, per unit length in $2+1$ dimensions, and the particle mass in $1+1$ dimensions.

For several scalar fields $\phi^a$ with target-space metric $G_{ab}$, a common generalization is

$$
V(\phi)=\frac12G^{ab}\partial_aW\partial_bW.
$$

Then a BPS-type wall obeys the gradient-flow equation

$$
\frac{d\phi^a}{dz}=G^{ab}\partial_bW
$$

up to a choice of orientation. This first-order equation is especially important in supersymmetric theories, but the energy-bound logic itself is more general.

## Topological sector and orientation

For a theory with disconnected vacua, a wall sector is labeled by the pair of vacua at the two transverse ends:

$$
(\phi_-,\phi_+).
$$

The wall and antiwall are different orientations:

$$
\text{wall}:\quad \phi_-\to\phi_+,
\qquad
\text{antiwall}:\quad \phi_+\to\phi_-.
$$

In the double-well model, the natural charge per unit area may be written as

$$
Q
=
\frac{\phi(+\infty)-\phi(-\infty)}{2v}.
$$

This is the same formula as for the kink, because the topological data live in the transverse direction. The charge labels the wall orientation, not the wall's position or shape.

A perfectly flat wall is the minimal-tension representative in its sector. A curved wall has more area and therefore more energy. At long wavelengths, its dynamics are governed by its position field, not by changing the internal profile of the core.

## Worldvolume effective theory

A wall breaks translations in the transverse direction. The corresponding zero mode is

$$
\eta_0(z)\propto \frac{d\phi_w}{dz}.
$$

Promoting the wall position to a slowly varying field on the worldvolume,

$$
Z\to Z(x^\alpha),
$$

gives the leading low-energy effective theory of wall bending modes.

For a relativistic wall with no additional light localized fields, the leading action is the Nambu–Goto action

$$
S_{\rm wall}
=
-T\int d^d\xi\,\sqrt{-\det h_{ab}},
$$

where $h_{ab}$ is the induced metric on the wall worldvolume. In static gauge, with one transverse fluctuation $Z(x^\alpha)$, this becomes

$$
S_{\rm wall}
=
-T\int d^d x\,
\sqrt{1-\partial_\alpha Z\,\partial^\alpha Z}.
$$

For small slopes,

$$
S_{\rm wall}
=
-T\int d^d x
\left[
1-\frac12\partial_\alpha Z\,\partial^\alpha Z+O((\partial Z)^4)
\right].
$$

The constant term is the rest energy of the wall, while the next term gives the usual kinetic and gradient terms for $Z$. Thus the transverse position is a massless scalar field living on the wall. This is the Goldstone mode for broken transverse translations.

This effective description assumes that the curvature radius and wavelength along the wall are large compared with the wall thickness:

$$
R_{\rm curvature}\gg \ell,
\qquad
\lambda_{\rm worldvolume}\gg \ell.
$$

At shorter distances, the internal structure of the wall matters.

## Degeneracy, pressure, and instability

A static infinite wall requires equal vacuum energy densities on the two sides. If the vacua are not exactly degenerate, then the wall feels a pressure.

Let

$$
\Delta\epsilon
=
\epsilon_+ -\epsilon_-.
$$

If $
\Delta\epsilon>0$, the $+$ phase has higher energy density. Moving the wall to reduce the volume of the $+$ phase lowers the energy. The pressure on the wall is

$$
p=\Delta\epsilon,
$$

with sign determined by orientation. In the thin-wall approximation, the resulting acceleration is roughly

$$
a\sim \frac{\Delta\epsilon}{T}.
$$

This is the spatial-domain version of false-vacuum decay. A bubble of true vacuum inside false vacuum gains volume energy but pays wall tension. For a spherical bubble of radius $R$ in three spatial dimensions, the energy is schematically

$$
E(R)
\simeq
4\pi R^2T-\frac{4\pi}{3}R^3\Delta\epsilon.
$$

The competition between surface tension and volume energy is the intuition behind thin-wall bounce calculations in false-vacuum decay.

## Multiple vacua, composite walls, and junctions

If a theory has more than two vacua, walls can be labeled by ordered pairs

$$
(i,j),
\qquad
\phi(z\to -\infty)=\phi_i,
\quad
\phi(z\to +\infty)=\phi_j.
$$

A wall between non-neighboring vacua may be elementary or composite. If there is an intermediate vacuum $k$, a candidate composite wall has two separated walls,

$$
(i,j)\sim (i,k)+(k,j).
$$

The stability depends on the tensions. A necessary energetic test is the triangle inequality

$$
T_{ij}\le T_{ik}+T_{kj}.
$$

If the inequality is strict and a direct wall exists, the direct wall is energetically favored over two infinitely separated walls. If equality holds, the separation can become a modulus in a BPS system. If the direct wall has larger tension than the separated pair, it is unstable to splitting.

In two or more dimensions along the wall, several walls can meet at junctions. Mechanical equilibrium at a static junction requires tension-vector balance. If three walls meet, the angles are determined by

$$
\vec T_{12}+\vec T_{23}+\vec T_{31}=0,
$$

where each vector has magnitude equal to the corresponding wall tension and direction normal to the wall segment in the spatial cross-section.

Wall junctions are model-dependent. Topology tells you which asymptotic vacua can appear; dynamics decides which junctions exist and which are stable.

## Localized degrees of freedom

A domain wall can support fields localized near its core. The universal example is the translational zero mode. Other localized modes can appear when additional fields, symmetries, or fermions are present.

Typical examples include:

| Localized mode | Origin | Low-energy interpretation |
|---|---|---|
| Translation mode | Broken transverse translation | Massless scalar $Z(x^\alpha)$ on the wall |
| Internal orientation modes | Broken internal symmetry inside the wall core | Sigma model on a moduli space |
| Fermion zero modes | Yukawa coupling to a wall profile or index-theorem structure | Lower-dimensional fermions on the wall |
| Gauge fields | Gauge dynamics localized by model-dependent mechanisms | Effective gauge theory on the wall |

The existence of localized modes is not guaranteed by the mere presence of a wall. It is a spectral question for the fluctuation operators in the wall background. Still, walls are one of the cleanest ways QFT produces lower-dimensional physics dynamically.

## Domain walls versus interfaces and boundaries

A domain wall is dynamical: its position is a degree of freedom, and it separates two vacua or phases of the same underlying theory. An interface can be nondynamical: it may be imposed by changing couplings or boundary conditions across a fixed hypersurface. A boundary ends spacetime or the material system; a wall lives inside it.

The distinctions can blur. A heavy wall may be treated as a fixed interface. A domain wall separating two phases can support a defect QFT. A boundary condition can be obtained as a limit of a wall whose other side becomes very massive. But conceptually the wall is an object in the Hilbert space or path integral, while an externally imposed boundary is part of the definition of the problem.

## Gauge-theory caveat

When scalar fields are charged under a gauge group, apparent vacua related by a gauge transformation are physically the same. A wall separating gauge-equivalent field values is usually not a physical topological wall.

The correct asymptotic data must be gauge invariant or gauge covariant. In some theories, walls are classified by genuine disconnected gauge-inequivalent vacua, by discrete global symmetries, by theta-angle branches, by anomalies, or by topological order. In other theories, what looks like a wall in a gauge-fixed scalar profile is only a gauge artifact.

A safe diagnostic is this: ask whether the two sides differ by a genuine observable phase, superselection sector, symmetry-breaking pattern, topological order, or boundary condition. If not, the “wall” may be a coordinate choice in field space rather than a physical defect.

## Common pitfalls

**Do not demand finite total energy for an infinite wall.** The total energy diverges with area. The physical quantity is the tension.

**A wall is not just a drawing between two minima.** It is a solution, or at least a stable configuration, of the field equations with specified asymptotic boundary conditions.

**Degeneracy matters.** If the two sides have different vacuum energy densities, the wall feels pressure and accelerates. A static infinite wall is then not an equilibrium solution.

**A topological label does not compute the tension.** The boundary pair says which sector you are in. The tension depends on the action and the actual interpolating profile.

**Gauge-equivalent “vacua” do not define physical walls.** In gauge theories, one must identify genuine gauge-invariant vacuum data.

**The Nambu–Goto action is a long-distance approximation.** It describes bending modes at wavelengths much larger than the wall thickness. It does not replace the microscopic wall core.

## Relations to other pages

This page builds directly on [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/). A kink is a domain wall with no spatial directions along the wall.

The tension calculation uses the same energy-bound logic as [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/) and the same zero-mode logic as [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/).

The pressure and bubble discussion connects to [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) and [False Vacua and Metastability](/nonperturbative-qft/vacuum-structure-phases/false-vacua-and-metastability/). The later instanton chapter will treat the Euclidean bounce calculation more systematically.

## Research status

The classical theory of scalar domain walls, their finite tension, topological boundary conditions, translational zero mode, and long-wavelength Nambu–Goto dynamics are established.

Active and model-dependent topics include wall networks and junctions, domain walls in strongly coupled gauge theories, walls with topological order or anomaly inflow, supersymmetric BPS walls and wall-crossing phenomena, cosmological domain-wall constraints, and real-time dynamics of walls in nonequilibrium settings.

## Exercises

### Exercise 1: Derive the wall tension in the double-well model

For

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
$$

use the first-order wall equation to compute the tension of the wall from $-v$ to $+v$.

<details><summary><strong>Solution</strong></summary>

The first-order equation is

$$
\frac{d\phi}{dz}=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2).
$$

For a solution of this equation,

$$
\frac12(\phi')^2=V(\phi),
$$

so

$$
T=\int dz\left[\frac12(\phi')^2+V(\phi)\right]
=\int dz\,(\phi')^2.
$$

Using $dz=d\phi/\phi'$,

$$
T
=\int_{-v}^{+v}d\phi\,\phi'
=\sqrt{\frac{\lambda}{2}}\int_{-v}^{+v}d\phi\,(v^2-\phi^2).
$$

Therefore

$$
T
=\sqrt{\frac{\lambda}{2}}\frac{4v^3}{3}
=\frac{2\sqrt2}{3}\sqrt\lambda\,v^3
=\frac{2}{3}mv^2.
$$

</details>

### Exercise 2: Show that a pressure difference accelerates a wall

Suppose the vacuum energy density on the right side of a planar wall exceeds that on the left by $\Delta\epsilon>0$. Estimate the force per unit area on the wall and its nonrelativistic acceleration.

<details><summary><strong>Solution</strong></summary>

Moving the wall by a small distance $\delta z$ to the right converts a volume $A\delta z$ of the higher-energy phase into the lower-energy phase. The energy change is

$$
\delta E=-A\Delta\epsilon\,\delta z.
$$

Thus the force per unit area is

$$
\frac{F}{A}=\Delta\epsilon,
$$

directed so as to reduce the higher-energy phase. The wall's inertial mass per unit area is its tension $T$, so the nonrelativistic acceleration estimate is

$$
a\simeq \frac{\Delta\epsilon}{T}.
$$

This estimate is valid only when the wall remains thin compared with the length scales of its motion.

</details>

### Exercise 3: Expand the Nambu–Goto action

Starting from

$$
S=-T\int d^d x\sqrt{1-\partial_\alpha Z\partial^\alpha Z},
$$

expand to quadratic order in $Z$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\sqrt{1-y}=1-\frac12 y+O(y^2),
$$

with

$$
y=\partial_\alpha Z\partial^\alpha Z.
$$

Then

$$
S=-T\int d^d x
\left[1-\frac12\partial_\alpha Z\partial^\alpha Z+O((\partial Z)^4)\right].
$$

The constant term is the rest energy of the wall. The quadratic term is the kinetic action for the transverse Goldstone mode.

</details>

### Exercise 4: Tension balance at a three-wall junction

Three walls with equal tension $T$ meet at a static junction in a two-dimensional spatial cross-section. What are the angles between the walls?

<details><summary><strong>Solution</strong></summary>

Mechanical equilibrium requires

$$
\vec T_1+\vec T_2+\vec T_3=0,
$$

where each vector has magnitude $T$ and points normal to the corresponding wall segment in the cross-section. Three equal vectors sum to zero only when they are separated by angles

$$
\frac{2\pi}{3}.
$$

Thus the walls meet at $120^\circ$ angles in the symmetric case.

</details>

## References

- M. Shifman, *Advanced Topics in Quantum Field Theory*, ch. 2, for kinks and domain walls, including first-order equations, wall junctions, and quantum corrections; sec. 11.4 for supersymmetric domain walls.
- S. Coleman, *Aspects of Symmetry*, “Classical lumps and their quantum descendants,” for the physics of classical lumps, topology, and semiclassical quantization.
- M. Srednicki, *Quantum Field Theory*, ch. 92, for solitons and monopoles in a standard QFT textbook sequence.
- R. Rajaraman, *Solitons and Instantons*, for the classic treatment of kink and wall profiles, stability, and collective coordinates.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for the geometric and dynamical treatment of extended solitons and their moduli.

## Version history

- **2026-06-26:** Initial polished page.
