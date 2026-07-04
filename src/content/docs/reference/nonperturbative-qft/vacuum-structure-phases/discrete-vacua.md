---
title: "Discrete Vacua"
description: "Explains finite sets of symmetry-related vacua, source selection, domain walls, tunneling, explicit bias, and common distinctions from topological degeneracy."
sidebar:
  label: "Discrete Vacua"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman; Srednicki; Schwartz; Weinberg; Zinn-Justin; Shifman; Fradkin; Altland–Simons."
topics:
  - discrete vacua
  - domain walls
  - spontaneous symmetry breaking
  - finite volume
  - tunneling
  - Ising phases
  - false vacua
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - discrete-vacua
  - domain-walls
  - spontaneous-symmetry-breaking
researchStatus:
  established:
    - "Discrete broken symmetries give a finite set of pure infinite-volume vacua and no Goldstone bosons; domain walls are the characteristic extended excitations separating the vacua."
  active:
    - "In modern gauge and condensed-matter systems, finite vacuum degeneracies can also arise from topology, higher-form symmetries, anomalies, or boundary conditions, so local order-parameter language must be checked case by case."
---

## Summary

**Discrete vacua** are a finite or countable set of pure vacuum states that cannot be continuously deformed into one another by changing a zero-mode along a flat direction. The cleanest case is spontaneous breaking of a finite global symmetry. For a broken $\mathbb Z_2$ symmetry, the two pure vacua obey

$$
\langle\phi\rangle_+=+v_R,
\qquad
\langle\phi\rangle_-=-v_R,
$$

and the symmetry exchanges them.

Unlike continuous symmetry breaking, discrete symmetry breaking produces no Goldstone bosons. Its characteristic long-distance objects are **domain walls**. A domain wall is a finite-tension configuration interpolating between different vacua at spatial infinity:

$$
\phi(x_\perp\to-\infty)=\phi_-,
\qquad
\phi(x_\perp\to+\infty)=\phi_+.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![A discrete double-well potential has two pure vacua, a domain-wall profile, and localized wall energy.](/figures/nonperturbative-qft/discrete-vacua-domain-wall.svg)

<figcaption>

A broken $\mathbb Z_2$ theory has two pure vacua and a finite-tension wall between them. The potential shows the endpoints, the spatial profile interpolates between vacua at $x_\perp=\pm\infty$, and the wall energy is localized near the core.

</figcaption>
</figure>

Discrete vacua are the simplest laboratory for several nonperturbative themes: finite-volume tunneling, source selection, superselection sectors, domain walls, explicit bias, false vacua, and the difference between a pure broken state and a symmetric mixture.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), and [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/). The finite-volume subtleties use [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/).

No detailed soliton technology is assumed. The page uses a scalar double-well model as the basic example.

## Core idea

A continuous broken symmetry gives a vacuum manifold with tangent directions. A discrete broken symmetry gives isolated vacua. That simple difference changes the physics.

| Feature | Continuous broken symmetry | Discrete broken symmetry |
|---|---|---|
| Vacuum set from symmetry | Positive-dimensional orbit $G/H$ | Finite orbit $G/H$ |
| Infinitesimal broken generators | Yes | No |
| Goldstone bosons | Usually yes, under standard assumptions | No |
| Typical extended object | Vortices, textures, strings, depending on topology | Domain walls |
| Finite-volume effect | Rotor-like or tunneling effects | Exponentially small tunneling splitting |

The absence of Goldstone bosons does not make discrete symmetry breaking less real. It makes it cleaner in some ways: the vacua are isolated, the wall tension is nonzero, and the order parameter can jump discontinuously as a source crosses zero in the infinite-volume limit.

## Setup and conventions

We use the conventions of [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). A spatial coordinate perpendicular to a wall is denoted $x_\perp$. The spatial volume regulator is $\Sigma_L$ with volume $V_L$.

The canonical scalar example is a real field with exact $\mathbb Z_2$ symmetry,

$$
\phi\mapsto-\phi,
$$

and classical potential

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
\qquad \lambda>0.
$$

The tree-level minima are at $\phi=\pm v$. The exact quantum VEVs are written $\pm v_R$ because renormalization and fluctuations shift the naive classical value.

For static configurations depending only on $x_\perp$, the energy per unit wall area is

$$
T[\phi]
=\int_{-\infty}^{\infty}dx_\perp\,
\left[\frac12\left(\frac{d\phi}{dx_\perp}\right)^2+V(\phi)-V_{\rm min}\right].
$$

A domain-wall tension is the minimum of this functional with boundary conditions in two different vacua.

## Definition

A theory has **discrete vacua** if its pure infinite-volume vacuum states include isolated components

$$
\{\Omega_\alpha\}_{\alpha\in I}
$$

that have the same energy density and are not connected by a continuous zero-energy path inside the vacuum space.

A particularly important case is spontaneous breaking of a finite global symmetry $G$ to $H$. If $\Omega$ is one pure vacuum, then the symmetry orbit is

$$
\{g\Omega\mid g\in G\}\simeq G/H,
$$

and the number of symmetry-related vacua is

$$
|G/H|=\frac{|G|}{|H|}
$$

when $G$ is finite.

For $G=\mathbb Z_N$ broken completely, one commonly labels the vacua by

$$
k=0,1,\ldots,N-1,
$$

with an order parameter behaving schematically as

$$
\langle\mathcal O\rangle_k=v_R e^{2\pi i k/N}.
$$

The generator of $\mathbb Z_N$ maps $k\mapsto k+1$ mod $N$.

## The double-well model

The real scalar double-well model is the universal cartoon for a broken $\mathbb Z_2$ symmetry:

$$
\mathcal L=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac{\lambda}{4}(\phi^2-v^2)^2.
$$

The classical potential has two minima. Expanding around either one gives a massive local fluctuation. For example, around $+v$ write

$$
\phi(x)=v+\eta(x).
$$

The small-fluctuation mass is

$$
m_\eta^2=V''(v)=2\lambda v^2.
$$

There is no massless particle associated with the twofold degeneracy because $\mathbb Z_2$ has no infinitesimal generator. The two vacua are separated by a barrier, not by a flat continuous direction.

At finite volume, the exact lowest states are often symmetric and antisymmetric combinations of localized states. The splitting is schematically

$$
\Delta E_L\sim e^{-cV_L},
\qquad c>0,
$$

for a broken phase. In infinite volume the splitting vanishes, and the localized states become distinct pure vacua.

## Domain walls

A domain wall is a configuration whose two sides approach different vacua. In the $\mathbb Z_2$ scalar example, a static wall perpendicular to the $x$ direction satisfies

$$
\phi(x\to-\infty)=-v,
\qquad
\phi(x\to+\infty)=+v.
$$

The Euler–Lagrange equation for a static wall is

$$
\frac{d^2\phi}{dx^2}=\frac{dV}{d\phi}.
$$

For the double-well potential, a convenient first-order form is

$$
\frac{d\phi}{dx}=\sqrt{2V(\phi)}
=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2),
$$

for the wall increasing from $-v$ to $+v$. The solution is

$$
\phi_{\rm wall}(x)=v\tanh\left(\frac{m_\eta}{2}(x-x_0)\right),
\qquad
m_\eta^2=2\lambda v^2.
$$

The wall tension is

$$
T_{-+}
=\int_{-v}^{+v}d\phi\,\sqrt{2V(\phi)}
=\frac{2\sqrt2}{3}\sqrt\lambda\,v^3
=\frac{m_\eta^3}{3\lambda},
$$

at the classical level for this normalization of $V$.

The center $x_0$ is a collective coordinate: translating the wall costs no energy in infinite volume. This zero mode is not a Goldstone boson of an internal broken symmetry in the bulk; it is the translational mode of a specific extended object.

## Boundary conditions and sectors

Discrete vacua can be selected by sources or by boundary conditions.

A source selection uses

$$
H_L(h)=H_L-h\int_{\Sigma_L}d^{d-1}x\,\phi(x),
$$

with $h>0$ selecting $\Omega_+$ and $h<0$ selecting $\Omega_-$. Boundary selection instead fixes the field or order parameter near spatial infinity, for example

$$
\phi|_{\partial\Sigma_L}\approx +v.
$$

Mixed boundary conditions can force a wall. In one spatial direction,

$$
\phi(x=-L/2)\approx -v,
\qquad
\phi(x=+L/2)\approx +v,
$$

select a sector with at least one interpolating wall.

This is a useful way to see why domain walls are nonperturbative. Around either vacuum, small fluctuations never change the boundary condition at infinity. A wall lives in a different topological or boundary sector of configuration space.

## Explicit breaking and false vacua

Now add a small explicit symmetry-breaking term,

$$
\Delta V(\phi)=-\epsilon\phi.
$$

The two vacua are no longer exactly degenerate. For $\epsilon>0$, the positive vacuum is lower in energy and the negative vacuum is metastable, if the barrier remains. The energy-density difference is approximately

$$
\Delta\varepsilon
\equiv \varepsilon_- - \varepsilon_+
\approx 2\epsilon v
$$

for small $\epsilon$ at the classical level.

A domain wall between the two phases then feels pressure: the lower-energy phase wants to expand. In Euclidean language this is the beginning of false-vacuum decay by bubble nucleation. The wall tension penalizes the bubble surface area, while the energy-density difference rewards the bubble volume. The competition between these two terms produces a critical bubble.

This is one reason discrete vacua are such a good training ground. They connect the same simple picture to symmetry breaking, domain walls, metastability, and instantons.

## Discrete vacua versus topological degeneracy

Not every finite vacuum degeneracy is spontaneous breaking of an ordinary discrete global symmetry.

| Degeneracy type | Typical diagnostic | Example of distinction |
|---|---|---|
| Discrete symmetry breaking | Local order parameter and domain walls | $\mathbb Z_2$ broken scalar theory or ordered Ising phase |
| Topological degeneracy | Dependence on spatial topology and extended operators | Degenerate states on a torus in a topological phase |
| Accidental degeneracy | Lifted by generic allowed perturbations | Fine-tuned quantum-mechanical or field-theoretic degeneracy |
| Theta or flux sectors | Boundary conditions, large gauge transformations, line operators | Gauge theories with nontrivial global structure |

The difference matters because the physics of defects, finite-volume splitting, robustness, and observables is different. A local order parameter distinguishes ordinary broken discrete vacua. A topological degeneracy may be invisible to all local operators and detected only by extended operators or by changing the topology of space.

## Low-dimensional comments

Discrete symmetry breaking is more infrared-stable than continuous symmetry breaking because it has no massless Goldstone direction. For example, a relativistic $1+1$-dimensional quantum Ising field theory can have two broken vacua at zero temperature.

This should not be oversimplified into “discrete symmetries always break in low dimensions.” Thermal fluctuations, dimensionality, long-range interactions, boundary conditions, and the precise limit all matter. In one-dimensional classical systems with short-range interactions at nonzero temperature, domain walls proliferate and destroy long-range order. In quantum systems, the corresponding statement depends on the spacetime dimension and on whether one is at zero or nonzero temperature.

The safe statement is this: discrete symmetry breaking is not forbidden by the same Goldstone-infrared mechanism that forbids continuous internal symmetry breaking in many low-dimensional relativistic settings.

## Common pitfalls

**Looking for a Goldstone boson.** A broken discrete symmetry has no infinitesimal generator and no continuous flat direction. The characteristic excitations are domain walls, kinks, and other defects, not Goldstone particles.

**Using finite-volume eigenstates as broken vacua.** The exact finite-volume ground state may be symmetric. Broken vacua are selected by a source or boundary condition and become stable only after the infinite-volume limit.

**Confusing wall sectors with perturbative excitations.** A domain wall changes the asymptotic vacuum. No finite number of small quanta around one vacuum can produce a configuration with a different vacuum at infinity.

**Calling every finite degeneracy a broken discrete symmetry.** Topological degeneracy, flux sectors, and accidental degeneracy have different diagnostics. Ask whether a local order parameter and domain walls exist.

**Forgetting explicit bias.** A tiny explicit breaking term can turn one vacuum into the true vacuum and the other into a false vacuum. Once the energy densities differ, walls feel pressure and the higher-energy phase can decay.

## Relations to other pages

- [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) gives the general state-level definition of broken symmetry.
- [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/) explains finite-volume tunneling and the emergence of infinite-volume sectors.
- [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) explains why different broken vacua are not connected by local finite-energy operators.
- [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains source-selected order parameters.
- [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/) explains why domain walls are semiclassical in weakly coupled examples but not merely perturbative.

## Research status

The basic theory of discrete symmetry breaking, finite-volume tunneling, domain walls, and explicitly biased vacua is textbook-standard. The scalar double-well and Ising universality class remain the cleanest reference examples.

Modern applications are broader. Discrete vacua appear in gauge theories, supersymmetric theories, chiral symmetry breaking, axion potentials, anomaly constraints, topological phases, and condensed-matter systems. In those settings one must distinguish ordinary local order from topological order, higher-form symmetry breaking, anomaly-enforced degeneracy, and boundary-condition sectors.

## Exercises

### Exercise 1: Number of symmetry-related vacua

A finite global symmetry group $G$ is spontaneously broken to a subgroup $H$. Assuming the vacuum orbit is faithful and no extra degeneracies are present, show that the number of symmetry-related vacua is $|G|/|H|$.

<details>
<summary><strong>Solution</strong></summary>

The vacua in the symmetry orbit are labeled by cosets $gH$, because two group elements $g_1$ and $g_2$ produce the same vacuum exactly when $g_2^{-1}g_1\in H$. Thus the orbit is $G/H$. For finite groups, the number of cosets is

$$
|G/H|=\frac{|G|}{|H|}.
$$

</details>

### Exercise 2: Kink profile check

For

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
$$

show that

$$
\phi(x)=v\tanh\left(\frac{m_\eta}{2}x\right),
\qquad m_\eta^2=2\lambda v^2,
$$

solves the static field equation.

<details>
<summary><strong>Solution</strong></summary>

The static equation is

$$
\phi''=\frac{dV}{d\phi}=\lambda\phi(\phi^2-v^2).
$$

Let $a=m_\eta/2=\sqrt{\lambda v^2/2}$ and $\phi=v\tanh(ax)$. Then

$$
\phi'=va\operatorname{sech}^2(ax),
$$

and

$$
\phi''=-2va^2\operatorname{sech}^2(ax)\tanh(ax).
$$

The right-hand side is

$$
\lambda v\tanh(ax)\left(v^2\tanh^2(ax)-v^2\right)
=-\lambda v^3\tanh(ax)\operatorname{sech}^2(ax).
$$

Since $2a^2=\lambda v^2$, the two expressions agree.

</details>

### Exercise 3: Classical wall tension

Using the first-order relation $d\phi/dx=\sqrt{2V(\phi)}$, derive the wall tension

$$
T_{-+}=\int_{-v}^{+v}d\phi\,\sqrt{2V(\phi)}
$$

for the double-well potential and evaluate it.

<details>
<summary><strong>Solution</strong></summary>

For the solution increasing from $-v$ to $+v$,

$$
\sqrt{2V(\phi)}=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2)
$$

inside the interval. Therefore

$$
T_{-+}=\sqrt{\frac{\lambda}{2}}\int_{-v}^{v}d\phi\,(v^2-\phi^2)
=\sqrt{\frac{\lambda}{2}}\left(2v^3-\frac{2v^3}{3}\right)
=\frac{2\sqrt2}{3}\sqrt\lambda\,v^3.
$$

Using $m_\eta^2=2\lambda v^2$, this can also be written as

$$
T_{-+}=\frac{m_\eta^3}{3\lambda}.
$$

</details>

### Exercise 4: Bias and pressure

Add $\Delta V=-\epsilon\phi$ with $\epsilon>0$. Which vacuum is lower in energy, and what is the approximate energy-density difference for small $\epsilon$?

<details>
<summary><strong>Solution</strong></summary>

At the classical minima, the bias contributes

$$
\Delta V(+v)=-\epsilon v,
\qquad
\Delta V(-v)=+\epsilon v.
$$

Therefore the $+v$ vacuum is lower. The energy-density difference between the false $-v$ vacuum and the true $+v$ vacuum is approximately

$$
\varepsilon_- - \varepsilon_+\approx 2\epsilon v.
$$

This difference acts as a pressure favoring expansion of the true-vacuum region.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially the lectures on spontaneous symmetry breakdown and false-vacuum decay.
- M. Srednicki, *Quantum Field Theory*, chapters on spontaneous symmetry breaking, solitons and monopoles, and instantons.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 28.1 for spontaneous breaking of discrete symmetries.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for order parameters, finite-size effects, and phase transitions.

### Deeper references

- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters on phases of gauge theories, kinks and domain walls, and false-vacuum decay.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for symmetry realization and domain-boundary discussions.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for Ising duality, discrete order, domain-wall language, and topological distinctions.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, domain walls, and low-dimensional infrared effects.

## Version history

- **2026-06-26:** Initial polished draft.
