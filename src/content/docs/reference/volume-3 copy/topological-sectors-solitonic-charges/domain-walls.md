---
title: "Domain Walls"
description: "Explains domain walls as codimension-one solitons separating disconnected vacua, including kink profiles, wall tension, pi-zero classification, junctions, boundaries, and anomaly/inflow caveats."
sidebar:
  label: "Domain Walls"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §92; Coleman on spontaneous symmetry breaking, kinks, and false vacuum decay; Polyakov Chs. 4–6; Nakahara Ch. 4; Altland–Simons Chs. 5 and 8; Manton–Sutcliffe; Rajaraman."
topics:
  - domain walls
  - kinks
  - disconnected vacua
  - topological solitons
  - wall tension
  - spontaneous symmetry breaking
  - pi-zero classification
  - anomaly inflow
canonicalTopics:
  - domain-wall
  - kink-soliton
  - pi-zero-vacuum-manifold
  - wall-tension
  - topological-sector
researchStatus:
  established:
    - "Domain walls are codimension-one finite-tension configurations separating distinct disconnected components of the vacuum space."
    - "In simple scalar theories with two degenerate vacua, the wall charge is fixed by the asymptotic vacua and cannot change under smooth finite-energy time evolution."
  active:
    - "Modern uses of domain walls often involve additional wall degrees of freedom, anomaly inflow, higher-form symmetry, confinement, duality interfaces, or cosmological stability questions."
---

## Summary

A domain wall is a codimension-one soliton separating two distinct vacua. In a relativistic theory with spatial dimension $D$, a static wall has $D-1$ spatial directions along the wall and one transverse coordinate $x_\perp$. Far from the wall, the fields approach different vacua:

$$
\Phi(x_\perp\to -\infty)=v_-,
\qquad
\Phi(x_\perp\to +\infty)=v_+.
$$

The basic topological input is not $\pi_1$ or $\pi_2$, but

$$
\pi_0(\mathcal V),
$$

where $\mathcal V$ is the vacuum space. If $v_-$ and $v_+$ lie in different connected components of $\mathcal V$, no smooth finite-energy deformation can remove the wall while keeping the boundary conditions fixed.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing disconnected vacua, a kink profile, and a codimension-one wall separating two spatial regions.](/figures/symmetry-anomalies-topology/domain-wall-vacuum-kink.svg)

<figcaption>

A domain wall is the field-theory interpolation between disconnected vacua. In one spatial dimension it is a kink. In higher dimensions the kink profile is extended along the wall worldvolume and localized only in the transverse direction.

</figcaption>
</figure>

The simplest example is the real scalar theory with a spontaneously broken $\mathbb Z_2$ symmetry,

$$
V(\phi)={\lambda\over 4}(\phi^2-v^2)^2.
$$

The two vacua are $\phi=\pm v$. The static kink profile is

$$
\phi_{\rm kink}(x)=v\tanh\left({mx\over 2}\right),
\qquad
m^2=V''(v)=2\lambda v^2.
$$

In $1+1$ dimensions this is a particlelike soliton. In $3+1$ dimensions the same transverse profile, extended along two spatial directions, is a domain wall with tension

$$
T={2mv^2\over 3}={2\sqrt{2\lambda}\over 3}v^3.
$$

Domain walls are the most literal topological solitons: a wall is where one vacuum stops and another begins.

## Prerequisites

You should know [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/), [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/), and [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/).

Useful nearby pages include [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/), [Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/), [Anomalies and Boundaries](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-boundaries/), and [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/).

## Core idea

The finite-energy condition for a static configuration is a boundary condition. For scalar fields with potential $V(\Phi)$, the energy density contains

$$
\mathcal E={1\over2}|\nabla\Phi|^2+V(\Phi).
$$

To have finite energy per wall area, the transverse limits must approach minima of $V$:

$$
\Phi(x_\perp\to\pm\infty)\in\mathcal V.
$$

A wall is forced if these two limiting vacua lie in different connected components of $\mathcal V$. The wall is not classified by the detailed path the field takes through field space. It is classified first by the pair of components at infinity:

$$
[\Phi(-\infty)],\ [\Phi(+\infty)]\in \pi_0(\mathcal V).
$$

The field must leave the vacuum manifold inside the wall core. That costs gradient and potential energy. The finite energy per unit area is the wall tension,

$$
T=\int_{-\infty}^{+\infty}dx_\perp\,
\left[{1\over2}\left({d\Phi\over dx_\perp}\right)^2+V(\Phi)-V_{\rm vac}\right].
$$

If the vacua are exactly degenerate, a planar static wall can be stable. If one vacuum has lower energy, the wall feels pressure and accelerates: the false vacuum wants to disappear. Topology protects against smooth unwinding, not against the fact that one side may be energetically doomed.

## The scalar kink as the basic domain wall

Take a single real scalar field in $1+1$ dimensions with Lagrangian

$$
\mathcal L={1\over2}\partial_\mu\phi\partial^\mu\phi-{\lambda\over4}(\phi^2-v^2)^2.
$$

The static energy is

$$
E=\int dx\left[{1\over2}\left({d\phi\over dx}\right)^2+{\lambda\over4}(\phi^2-v^2)^2\right].
$$

The Euler–Lagrange equation for a static solution is

$$
{d^2\phi\over dx^2}=\lambda\phi(\phi^2-v^2).
$$

The kink solution interpolating from $-v$ to $+v$ is

$$
\phi_{\rm kink}(x)=v\tanh\left({mx\over2}\right),
\qquad
m=\sqrt{2\lambda}\,v.
$$

The anti-kink has the opposite orientation:

$$
\phi_{\rm antikink}(x)=-v\tanh\left({mx\over2}\right).
$$

A convenient topological charge is

$$
Q={\phi(+\infty)-\phi(-\infty)\over 2v}.
$$

For the kink, $Q=1$. For the anti-kink, $Q=-1$. For the vacuum, $Q=0$.

This charge is topological because it depends only on endpoint data. A smooth finite-energy evolution cannot change $\phi(+\infty)$ from $+v$ to $-v$ without changing the boundary condition or creating a region of infinite energy in the ideal infinite-volume limit.

## Tension and the Bogomolny rewriting

For the quartic double-well potential, write

$$
V(\phi)={1\over2}\left({dW\over d\phi}\right)^2,
\qquad
{dW\over d\phi}=\sqrt{\lambda\over2}(v^2-\phi^2).
$$

Then

$$
E=\int dx\left[{1\over2}\left({d\phi\over dx}-{dW\over d\phi}\right)^2+{dW\over dx}\right].
$$

Therefore

$$
E\ge |W(\phi(+\infty))-W(\phi(-\infty))|.
$$

For the kink,

$$
W(\phi)=\sqrt{\lambda\over2}\left(v^2\phi-{\phi^3\over3}\right),
$$

so

$$
T_{\rm kink}=E_{\rm kink}={4\over3}\sqrt{\lambda\over2}v^3={2mv^2\over3}.
$$

The first-order equation

$$
{d\phi\over dx}={dW\over d\phi}
$$

is solved by the kink profile. This first-order rewriting is sometimes called a BPS trick, even when no supersymmetry is present. In supersymmetric theories it can become an actual BPS bound, with the wall tension determined by a central charge.

:::note[Convention-sensitive source note]
Some references use $V={\lambda\over4!}(\phi^2-v^2)^2$ or define the fluctuation mass differently. The formula $\phi=v\tanh(mx/2)$ assumes $V={\lambda\over4}(\phi^2-v^2)^2$ and $m^2=V''(v)=2\lambda v^2$.
:::

## From kink to wall

In $D$ spatial dimensions, choose coordinates

$$
\mathbf x=(x_\perp,\mathbf y),
\qquad
\mathbf y\in\mathbb R^{D-1}.
$$

A planar wall is obtained by the same one-dimensional profile:

$$
\phi(\mathbf x)=\phi_{\rm kink}(x_\perp).
$$

The total energy is infinite in infinite volume because the wall has infinite area. The meaningful intensive quantity is the tension,

$$
T={E\over \operatorname{Area}}.
$$

A curved wall has an effective worldvolume theory. At long distances compared with the wall thickness, the leading action is a Nambu–Goto–type area term,

$$
S_{\rm wall}\approx -T\int d^{D} \xi\,\sqrt{-\det h_{ab}},
$$

where $h_{ab}$ is the induced worldvolume metric. If the wall breaks translations in the transverse direction, it has a position collective coordinate. For a planar wall located at $X(\xi)$, this becomes a massless worldvolume mode in the ideal infinite-wall limit.

Domain walls can also carry additional localized fields. Fermion zero modes, gauge fields, topological field theories, chiral modes, or Goldstone modes can live on the wall, depending on the microscopic theory. In modern QFT, many interesting walls are not just sheets of energy; they are lower-dimensional quantum field theories glued to a bulk.

## Classification by disconnected vacua

For ordinary scalar order parameters, the first diagnostic is

$$
\pi_0(\mathcal V).
$$

Examples:

- If $\mathcal V=\{+v,-v\}$, then $\pi_0(\mathcal V)$ has two elements and there are $\mathbb Z_2$ walls.
- If $\mathcal V=S^1$, then $\pi_0(S^1)$ is trivial and there are no stable domain walls from this vacuum manifold, though vortices can appear because $\pi_1(S^1)=\mathbb Z$.
- If $\mathcal V$ has $N$ disconnected vacua, walls may connect different pairs of vacua and can form junctions.

For a domain wall on the line, the sector is often labeled by the ordered pair

$$
(v_-,v_+).
$$

For a wall in higher dimensions, local patches of the wall still have such a transverse label. Globally, wall networks can meet at junctions if several vacua are available. The junction conditions are determined by tension balance and by whatever charges or anomaly data the walls carry.

## Gauge and quotient caveats

A crucial warning: vacua related by a **gauge redundancy** are not distinct physical vacua. If two apparent minima differ only by a gauge transformation that is truly redundant, a wall between them is not a physical domain wall.

However, global form and boundary conditions can make this statement more subtle. A transformation that is pure redundancy in one setting may become a physical global transformation or boundary symmetry in another. This is why domain walls in gauge theories should be described using gauge-invariant order parameters, line operators, background fields, and global-form data rather than only by looking at a classical potential.

Examples of this subtlety include:

- walls between distinct vacua of a discrete global symmetry,
- walls between branches of an effective theta-dependent potential,
- walls carrying Chern–Simons theories or anomaly inflow,
- walls ending on defects when the putative vacua are connected after including additional fields.

The safe rule is simple: first identify the physical vacuum space, not the coordinate space of fields.

## Dynamics: tension, pressure, and decay

A static planar wall between exactly degenerate vacua is a stationary solution. If the vacuum energies differ,

$$
\Delta\varepsilon=\varepsilon_+-\varepsilon_-\ne0,
$$

then the wall feels a pressure

$$
P=\Delta\varepsilon.
$$

The lower-energy vacuum expands. A small explicit breaking of a discrete symmetry therefore turns stable walls into metastable walls.

In cosmology and statistical systems this matters a lot. Exact discrete symmetry breaking can lead to stable wall networks, which are often disastrous cosmologically unless diluted, inflated away, unstable, or otherwise controlled. Approximate discrete symmetry produces walls that eventually collapse.

In quantum field theory, decay of a false vacuum is usually described by Euclidean bounce solutions. A domain wall then appears as the wall of a nucleated bubble: inside is the lower-energy phase, outside is the false vacuum. This is a different use of the same object: the wall is a finite-tension interface, but the topological protection has been replaced by tunneling dynamics.

## Domain walls and anomaly inflow

Domain walls often inherit anomaly data from the bulk. A familiar pattern is:

$$
\text{bulk topological term changes across wall}
\quad\Longrightarrow\quad
\text{wall supports anomaly inflow}.
$$

For example, if an axion-like field $\theta(x)$ changes by $2\pi$ across a wall in a theory with a coupling

$$
{\theta\over 8\pi^2}\operatorname{tr}(F\wedge F),
$$

then integration by parts suggests a Chern–Simons term localized on the wall. Globally, this statement must be treated with the same care as all Chern–Simons and theta-angle statements: large gauge transformations, boundary degrees of freedom, spin structure, and trace normalization can matter.

This is one reason domain walls are central in modern anomaly matching. If a bulk phase has a mixed anomaly or nontrivial SPT response, a symmetric wall or boundary may be forced to carry a lower-dimensional theory, topological order, gapless modes, or symmetry breaking.

## Common pitfalls

Do not confuse a domain wall with any region where a scalar field changes rapidly. A topological wall connects distinct asymptotic vacua or physically distinct phases.

Do not classify walls using gauge-variant field coordinates. Gauge-equivalent minima are not distinct vacua.

Do not say topology guarantees dynamical stability in every sense. Topology protects against smooth unwinding with fixed boundary conditions. It does not prevent walls from moving, radiating, bending, annihilating with anti-walls, or decaying when the assumptions fail.

Do not call every interface a domain wall. A material interface, boundary condition, defect, brane, or duality wall may be mathematically similar, but the word “domain wall” usually signals an interpolation between vacua or phases.

Do not forget finite volume. In finite volume, exact spontaneous symmetry breaking is subtle. The sharp superselection-sector language becomes exact only after the appropriate infinite-volume limit.

## Relations to other pages

Domain walls are the codimension-one entry in the soliton dictionary:

$$
\pi_0(\mathcal V):\text{ domain walls},
\qquad
\pi_1(\mathcal V):\text{ vortices},
\qquad
\pi_2(\mathcal V):\text{ monopoles},
\qquad
\pi_3(\mathcal V):\text{ textures and Skyrmions}.
$$

They connect directly to spontaneous symmetry breaking, false vacuum decay, anomaly inflow, SPT boundaries, duality interfaces, confining strings ending on walls, and topological quantum field theories localized on defects.

In condensed matter language, domain walls are interfaces between ordered domains. In high-energy language, they are solitonic branes. In modern QFT language, they are codimension-one defects that may carry their own operator algebra and anomaly data.

## Research status

The classical domain-wall and kink story is established: finite-energy boundary conditions, disconnected vacua, kink charges, wall tension, and the double-well solution are standard soliton technology. The main convention-dependent pieces are the normalization of the scalar potential, the definition of the fluctuation mass, and the orientation used for the wall charge.

The active directions begin when walls are treated as quantum defects. Important examples include BPS walls, wall junctions, walls carrying Chern–Simons or topological field theories, anomaly inflow on interfaces, domain walls in confining gauge theories, cosmological domain-wall networks, and walls whose worldvolume theory is itself strongly coupled.

## Exercises

### Exercise 1: Kink tension

For

$$
V(\phi)={\lambda\over4}(\phi^2-v^2)^2,
$$

show that

$$
\phi(x)=v\tanh\left({mx\over2}\right),
\qquad
m^2=2\lambda v^2,
$$

solves the static equation of motion and has tension $T=2mv^2/3$.

<details><summary><strong>Solution</strong></summary>

The static equation is

$$
\phi''=\lambda\phi(\phi^2-v^2).
$$

Let $u=mx/2$. Then

$$
\phi'=v{m\over2}\operatorname{sech}^2u,
\qquad
\phi''=-v{m^2\over2}\operatorname{sech}^2u\tanh u.
$$

The right-hand side is

$$
\lambda v\tanh u\,(v^2\tanh^2u-v^2)
=-\lambda v^3\tanh u\operatorname{sech}^2u.
$$

The equation holds because $m^2=2\lambda v^2$.

For the tension, write

$$
V={1\over2}(W')^2,
\qquad
W'=\sqrt{\lambda\over2}(v^2-\phi^2).
$$

The kink obeys $\phi'=W'$, so

$$
T=W(v)-W(-v)
={4\over3}\sqrt{\lambda\over2}v^3
={2mv^2\over3}.
$$

</details>

### Exercise 2: The wall charge is endpoint data

For the $\mathbb Z_2$ kink, define

$$
Q={\phi(+\infty)-\phi(-\infty)\over2v}.
$$

Show that any smooth finite-energy deformation with fixed endpoints preserves $Q$.

<details><summary><strong>Solution</strong></summary>

Finite energy requires $\phi(\pm\infty)$ to be vacua, hence each endpoint is either $+v$ or $-v$. If the endpoints are held fixed, the formula for $Q$ obviously cannot change. More conceptually, the deformation is a homotopy through configurations with the same boundary data. Since the set of vacua has disconnected components, the endpoint cannot move continuously from $+v$ to $-v$ while remaining in the vacuum set.

</details>

### Exercise 3: Pressure on a biased wall

Suppose a small explicit breaking makes the two vacua have energy densities $\varepsilon_+$ and $\varepsilon_-$. Explain why the wall feels pressure $P=\varepsilon_+-\varepsilon_-$.

<details><summary><strong>Solution</strong></summary>

Move a planar wall by a small distance $\Delta x$ over area $A$. The volume of one phase changes by $A\Delta x$ while the other changes by $-A\Delta x$. The energy change is

$$
\Delta E=(\varepsilon_+-\varepsilon_-)A\Delta x.
$$

The force per area is minus the derivative of energy with respect to displacement, so the pressure difference is $P=\Delta\varepsilon$ up to the sign convention for which direction is positive. The lower-energy phase expands.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§30, 32, 84, and 92.
- S. Coleman, *Aspects of Symmetry*, lectures on secret symmetry, solitons, and false vacuum decay.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4–6.
- M. Nakahara, *Geometry, Topology and Physics*, Ch. 4 and the monopole/instanton material in Chs. 1 and 11.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Chs. 5 and 8.
- N. Manton and P. Sutcliffe, *Topological Solitons*.
- R. Rajaraman, *Solitons and Instantons*.

## Version history

- 2026-06-18: First polished draft for the topological sectors and solitonic charges chapter.
