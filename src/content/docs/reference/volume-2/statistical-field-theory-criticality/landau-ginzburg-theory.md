---
title: "Landau–Ginzburg Theory"
description: "How local order-parameter functionals turn symmetry, locality, and scale separation into a continuum field theory for critical phenomena."
sidebar:
  label: "Landau–Ginzburg Theory"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§1–8 and 10–12; Zinn-Justin 2021, critical phenomena and field-integral chapters; Altland and Simons 2023, ch. 6; Schwartz 2014, ch. 23."
topics:
  - Landau-Ginzburg theory
  - order parameters
  - statistical field theory
  - critical phenomena
  - mean-field theory
  - universality
canonicalTopics:
  - landau-ginzburg-theory
  - statistical-field-theory
  - critical-phenomena
researchStatus:
  established:
    - "Landau–Ginzburg functionals are the standard continuum starting point for many second-order transitions with local interactions and identifiable order parameters."
  active:
    - "The Landau–Ginzburg paradigm has important extensions and limitations, especially for topological order, gauge constraints, deconfined criticality, long-range interactions, disordered systems, and nonequilibrium transitions."
---

## Summary

**Landau–Ginzburg theory** is the local continuum field theory of an order parameter. It begins with a coarse variable, such as the magnetization density of an Ising magnet, and writes the most general local functional compatible with symmetries and locality. For a single real scalar order parameter with $Z_2$ symmetry at zero external field, the standard Euclidean statistical weight is

$$
\mathcal Z=\int \mathcal D\phi\,e^{-\mathcal H[\phi]},
$$

with

$$
\mathcal H[\phi]
=
\int d^d x\left[
\frac12 Z(\nabla\phi)^2
+\frac12 r\phi^2
+\frac{u}{4!}\phi^4
-h\phi
+\cdots
\right].
$$

Here $d$ is the number of spatial dimensions of the statistical system, $\phi(x)$ is the coarse-grained order-parameter field, $r$ tunes the transition, $u$ stabilizes the functional, $h$ is the source conjugate to the order parameter, and the ellipsis denotes higher powers and derivatives allowed by the symmetries.

The point is not that every magnet secretly contains a fundamental elementary scalar particle. The point is sharper: when the correlation length is much larger than the microscopic spacing, long-distance observables cannot see most microscopic details. They see a local field theory organized by symmetry, dimension, and RG relevance.

:::note[Statistical versus Lorentzian notation]
This chapter mostly uses **Euclidean statistical** notation. The functional $\mathcal H$ is a dimensionless effective Hamiltonian or free-energy functional in the Boltzmann weight $e^{-\mathcal H}$. It plays the same structural role as a Euclidean action. This is not the Lorentzian action $S$ appearing in $e^{iS}$.
:::

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 54rem;">

![Two Landau-Ginzburg quartic potentials: a single symmetric minimum for positive r and a double well for negative r.](/figures/renormalization-rg-eft/landau-ginzburg-double-well.svg)

<figcaption>

The local potential captures the mean-field phase structure. For $r>0$ the symmetric saddle $\phi=0$ is stable. For $r<0$ and $u>0$, two symmetry-related minima appear. RG fluctuations decide when this saddle-point picture gives the true critical exponents.

</figcaption>
</figure>

## Prerequisites

You should know the ideas of [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/), and [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/). The page [Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/) gives the most important concrete example.

## Core idea

A continuous phase transition has a diverging correlation length,

$$
\xi\to\infty.
$$

If the microscopic spacing is $a$, then near the critical point there is a large scaling window

$$
a\ll \xi.
$$

This separation is what makes a continuum field description possible. The microscopic variables may be atoms, spins, dimers, lattice fields, superconducting phases, or density fluctuations. The long-distance theory only remembers the slowly varying order parameter and the symmetries it must obey.

The Landau–Ginzburg prescription is:

1. identify an order parameter $\phi$;
2. write the most general local functional of $\phi$ and its derivatives consistent with the symmetries;
3. order terms by relevance or power counting;
4. study the saddle points, fluctuations, and RG flow.

The slogan is

$$
\text{microscopic model}
\quad\longrightarrow\quad
\text{coarse order parameter}
\quad\longrightarrow\quad
\text{local field theory}
\quad\longrightarrow\quad
\text{universal long-distance data}.
$$

The first arrow is approximate and model-dependent. The last arrow is universal.

## Setup and conventions

This page uses Euclidean statistical-field-theory conventions. The partition function is written as

$$
Z=\int\mathcal D\phi\,e^{-S_E[\phi]},
$$

and the dimension $d$ is the number of spatial dimensions of the statistical system. The Landau–Ginzburg functional is often also denoted $\mathcal H[\phi]$ when it is interpreted as an effective Hamiltonian divided by temperature.

For the scalar Ising-like case, $\phi$ is odd under the spin-flip symmetry,

$$
\phi\mapsto -\phi,
$$

and the source $h$ is odd as well. The coefficient $r$ is the temperature-like relevant perturbation; near the transition it is proportional to a reduced temperature $t=(T-T_c)/T_c$, up to nonuniversal normalization.


## Order parameters

An order parameter is a long-wavelength variable that distinguishes phases. It is not necessarily the only low-energy variable, and it is not always sufficient, but it is the right starting point for the Landau–Ginzburg–Wilson description of many ordinary continuous transitions.

Common examples are:

| System | Order parameter | Symmetry |
|---|---|---|
| Ising magnet | real scalar magnetization $\phi$ | $\phi\to-\phi$ at $h=0$ |
| XY magnet or superfluid | complex scalar $\Psi=|\Psi|e^{i\theta}$ | $U(1)$ |
| Heisenberg magnet | vector $\boldsymbol\phi$ | $O(3)$ or $SO(3)$ |
| Liquid–gas transition | density deviation $\phi=\rho-\rho_c$ | no exact $Z_2$ microscopically |
| Nematic liquid crystal | traceless tensor $Q_{ij}$ | rotations plus director identification |

The order parameter determines the allowed local terms. For a real Ising order parameter at zero magnetic field, the symmetry is

$$
\phi\mapsto -\phi.
$$

Therefore the local functional cannot contain odd powers such as $\phi^3$ or $\phi(\nabla\phi)^2$. Turning on a magnetic field $h$ explicitly breaks the symmetry and adds a term $-h\phi$.

## The local functional

The simplest scalar Landau–Ginzburg functional is

$$
\mathcal H[\phi]
=
\int d^d x\left[
\frac12 Z(\nabla\phi)^2
+V(\phi)
\right],
$$

where the local potential is expanded as

$$
V(\phi)=
\frac12 r\phi^2+\frac{u}{4!}\phi^4-h\phi+\cdots.
$$

The gradient term penalizes rapid spatial variation. The potential determines which uniform order-parameter values are favored. Higher-derivative and higher-power terms are allowed unless forbidden by symmetry, but they are less important at long distances near the ordinary Wilson–Fisher fixed point.

The coefficient $Z$ is often set to one by rescaling $\phi$, but it is useful to keep it visible when discussing correlation lengths and normalization. The coefficient $u$ should be positive in the simple quartic truncation so that the functional is bounded below. If $u<0$, one must include stabilizing terms such as $\phi^6$, and the transition may become first order.

:::tip[The ellipsis is not laziness]
The ellipsis is part of the theory. It means "all other local terms compatible with the symmetries." The reason the displayed terms dominate is not that the others are illegal; it is that RG relevance makes most of them less important in the scaling limit.
:::

## Mean-field theory as the saddle point

The mean-field approximation keeps only uniform configurations. Set $\phi(x)=\phi_0$ and minimize

$$
V(\phi_0)=
\frac12 r\phi_0^2+\frac{u}{4!}\phi_0^4-h\phi_0.
$$

At $h=0$, the stationary condition is

$$
\frac{dV}{d\phi_0}
=r\phi_0+\frac{u}{6}\phi_0^3=0.
$$

Thus

$$
\phi_0=0
\qquad\text{or}\qquad
\phi_0^2=-\frac{6r}{u}.
$$

For $u>0$:

- if $r>0$, the stable minimum is $\phi_0=0$;
- if $r<0$, the stable minima are

$$
\phi_0=\pm\sqrt{-\frac{6r}{u}}.
$$

This is the standard spontaneous breaking of $Z_2$: the functional is symmetric, but a chosen ordered state is not.

Near a thermal transition, one often writes schematically

$$
r\propto T-T_c.
$$

More precisely, $r$ is an analytic coordinate near the temperature-like scaling field. It need not be exactly proportional to $T-T_c$ away from the critical point.

## Gaussian fluctuations and the correlation length

To study fluctuations in the symmetric phase, keep only quadratic terms:

$$
\mathcal H_2[\phi]
=
\frac12\int d^d x\left[
Z(\nabla\phi)^2+r\phi^2
\right].
$$

In momentum space,

$$
\mathcal H_2[\phi]
=
\frac12\int\frac{d^d k}{(2\pi)^d}
\left(Zk^2+r\right)\phi(k)\phi(-k).
$$

The Gaussian two-point function is therefore

$$
G(k)=\langle \phi(k)\phi(-k)\rangle
=\frac{1}{Zk^2+r}.
$$

Writing

$$
G(k)=\frac{1}{Z}\frac{1}{k^2+\xi^{-2}},
$$

gives the mean-field correlation length

$$
\xi=\sqrt{\frac{Z}{r}}
\qquad (r>0).
$$

As $r\to0^+$, the correlation length diverges. This divergence is what makes the continuum field theory more accurate near the transition.

In position space, at large distance and $r>0$, the Gaussian correlator decays approximately as

$$
G(x)\sim \frac{e^{-|x|/\xi}}{|x|^{(d-1)/2}},
$$

up to normalization and dimension-dependent details. At criticality, the exponential scale disappears and a power law remains.

## Mean-field exponents

Mean-field theory gives a first pass at critical exponents. With the usual notation,

$$
\phi_0\sim (-r)^\beta,
\qquad
\chi\sim r^{-\gamma},
\qquad
\xi\sim r^{-\nu},
\qquad
\phi_0\sim h^{1/\delta}\quad(r=0),
$$

one obtains

$$
\beta=\frac12,
\qquad
\gamma=1,
\qquad
\nu=\frac12,
\qquad
\delta=3,
\qquad
\eta=0.
$$

These exponents are correct above the upper critical dimension, and they are often good qualitative guides. But in dimensions below the upper critical dimension, fluctuations change them. For the ordinary scalar $\phi^4$ transition, the upper critical dimension is

$$
d_c=4.
$$

At $d=4$, the quartic coupling is marginal and logarithmic corrections appear. For $d<4$, the quartic interaction is relevant at the Gaussian fixed point and the long-distance behavior is controlled by the Wilson–Fisher fixed point rather than by the Gaussian theory.

## Power counting and the upper critical dimension

At the Gaussian fixed point, the engineering dimension of a scalar field in $d$ Euclidean dimensions is

$$
[\phi]=\frac{d-2}{2}.
$$

The operator $\phi^4$ has engineering dimension

$$
[\phi^4]=2(d-2),
$$

so its coupling has dimension

$$
[u]=d-2(d-2)=4-d.
$$

Therefore:

| Dimension | Status of $u$ at the Gaussian fixed point |
|---:|---|
| $d>4$ | irrelevant |
| $d=4$ | marginal |
| $d<4$ | relevant |

This is the field-theory origin of the upper critical dimension $d_c=4$ for the scalar $\phi^4$ universality class. Above four dimensions, the Gaussian fixed point controls the transition and mean-field exponents hold. Below four dimensions, fluctuations are strong enough to generate a nontrivial interacting fixed point.

## Why Landau–Ginzburg theory is not just mean-field theory

Students often first meet Landau theory as a saddle-point approximation. That is historically natural but conceptually incomplete. The **Landau–Ginzburg functional** is a field theory. Mean-field theory is only the approximation that ignores nonuniform fluctuations.

The full statistical field theory is

$$
\mathcal Z=\int \mathcal D\phi\,e^{-\mathcal H[\phi]}.
$$

The difference between Landau theory and Landau–Ginzburg–Wilson theory is the difference between minimizing $\mathcal H$ and integrating over $\phi$. The latter includes fluctuations at all wavelengths and is precisely where RG enters.

At long distances, the relevant question is not whether the microscopic derivation gave a particular value of $u$. It is whether the RG flow lands in the basin of attraction of a fixed point. If it does, the critical exponents and scaling functions are universal, while microscopic coefficients only determine nonuniversal normalizations.

## Relation to Euclidean QFT

The scalar Landau–Ginzburg functional is mathematically the Euclidean $\phi^4$ field theory:

$$
\mathcal H[\phi]
=
\int d^d x\left[
\frac12(\nabla\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4\right].
$$

The statistical partition function

$$
\mathcal Z=\int\mathcal D\phi\,e^{-\mathcal H[\phi]}
$$

has the same formal structure as a Euclidean path integral. Correlation functions of the order parameter are Euclidean field-theory correlators:

$$
\langle \phi(x_1)\cdots \phi(x_n)\rangle
=
\frac{1}{\mathcal Z}
\int\mathcal D\phi\,
\phi(x_1)\cdots\phi(x_n)e^{-\mathcal H[\phi]}.
$$

This is why critical phenomena and QFT share the same RG language: both are controlled by locality, scaling, fluctuations, and fixed points.

The difference is interpretive. In a thermal statistical system, $d$ is the spatial dimension and $\mathcal H$ is an effective free-energy functional. In a Euclidean relativistic QFT, $d$ is spacetime dimension and the Euclidean action is obtained by analytic continuation from Lorentzian time.

## Generalizations

### O(N) vector models

For an $N$-component order parameter $\boldsymbol\phi$, the $O(N)$-invariant Landau–Ginzburg functional is

$$
\mathcal H[\boldsymbol\phi]
=
\int d^d x\left[
\frac12(\nabla\boldsymbol\phi)^2
+\frac12 r\boldsymbol\phi^2
+\frac{u}{4!}(\boldsymbol\phi^2)^2
\right].
$$

Special cases include:

| $N$ | Common name | Typical system |
|---:|---|---|
| 1 | Ising | uniaxial magnet, liquid–gas criticality |
| 2 | XY | superfluid or planar magnet |
| 3 | Heisenberg | isotropic magnet |

The $O(N)$ family is a central laboratory for the epsilon expansion, large-$N$ expansion, functional RG, conformal bootstrap, lattice simulations, and critical phenomena.

### Cubic and anisotropic terms

If the microscopic symmetry is smaller than $O(N)$, additional terms may appear. For instance, cubic anisotropy can add operators that distinguish coordinate axes in order-parameter space. Whether such anisotropies matter at long distances is an RG question, not a question answered by symmetry alone.

### Gauge-coupled order parameters

For superconductors, the order parameter is charged under electromagnetism. A schematic Ginzburg–Landau functional is

$$
\mathcal H[\Psi,A]
=
\int d^d x\left[
| (\nabla-iqA)\Psi |^2
+r|\Psi|^2
+u|\Psi|^4
+\frac{1}{4}F_{ij}F_{ij}
\right].
$$

This brings in gauge fields, vortices, and type-I/type-II behavior. It is a major extension, not merely a scalar field theory with a complex field.

## What Landau–Ginzburg theory explains well

Landau–Ginzburg theory explains why many microscopically different systems share the same long-distance behavior. A lattice gas and an Ising magnet can have the same critical exponents because both flow to the same Ising fixed point. The microscopic Hamiltonians differ; the relevant long-distance fields and symmetries agree.

It also explains why only a few parameters must be tuned to reach a critical point. For the Ising universality class, the two most important relevant perturbations are the temperature-like direction and the magnetic-field-like direction. Setting $h=0$ and tuning $r$ to criticality reaches the fixed point.

Finally, it gives a bridge between statistical mechanics and the rest of QFT. The same diagrams, renormalization constants, beta functions, anomalous dimensions, and operator mixing that appear in relativistic QFT appear here in Euclidean statistical form.

## What Landau–Ginzburg theory does not automatically explain

Landau–Ginzburg theory is powerful but not universal in the casual sense. Some phases and transitions are not classified by a local order parameter. Examples include topological phases, certain spin liquids, some gauge-theory confinement transitions, deconfined critical points, and transitions with long-range interactions or quenched disorder.

Even when an order parameter exists, a naive polynomial truncation may fail. The transition may be first order. Additional soft modes may be essential. Gauge constraints may change the infrared theory. Disorder may change the fixed point. In low dimensions, topological defects can dominate, as in the Berezinskii–Kosterlitz–Thouless transition.

The practical lesson is not "always write $\phi^4$." It is:

$$
\text{identify the long-distance fields, symmetries, locality assumptions, and RG-relevant perturbations.}
$$

Landau–Ginzburg theory is the simplest and most important expression of that lesson.

## Common pitfalls

**The order parameter is not necessarily microscopic.** In the Ising model, $\phi(x)$ is a coarse magnetization field, not one lattice spin.

**Mean-field theory is not the whole theory.** The full Landau–Ginzburg field theory includes fluctuations. Mean-field theory is the saddle-point approximation.

**The coefficient $r$ is not exactly the temperature.** Near the transition it is a coordinate along the temperature-like scaling direction.

**Symmetry allows terms; RG ranks them.** The fact that $\phi^6$ is allowed does not mean it controls the ordinary Ising critical point.

**A continuum functional is not valid at all momenta.** It describes the scaling window. It should not be trusted for details at the microscopic cutoff scale.

**Not every transition has a Landau order parameter.** Topological order, gauge constraints, and deconfined criticality require broader tools.

## Relations to other pages

[Ising Model to Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/ising-model-to-field-theory/) explains how the canonical lattice spin model leads to this scalar functional. [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) studies the saddle approximation systematically. [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/) analyzes the free field behind the quadratic functional. [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/) develops the interacting fixed point below four dimensions. The general RG language is developed in [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) and [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/).

## Research status

The Landau–Ginzburg–Wilson framework is established as the standard effective-field-theory description of many continuous transitions with short-range interactions and conventional order parameters. Its mean-field saddle gives a controlled starting point above the upper critical dimension and a useful qualitative guide below it.

The active frontier concerns systems where the minimal order-parameter functional must be enlarged: emergent gauge fields, topological defects, disorder, long-range interactions, nonequilibrium dynamics, quantum critical metals, and transitions where no local gauge-invariant order parameter captures the full critical theory.

## Exercises

### Exercise 1: Minima of the quartic potential

For

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4,
\qquad u>0,
$$

find the minima for $r>0$ and $r<0$.

<details><summary><strong>Solution</strong></summary>

The stationary condition is

$$
\frac{dV}{d\phi}=r\phi+\frac{u}{6}\phi^3=0.
$$

Thus

$$
\phi=0
\qquad\text{or}\qquad
\phi^2=-\frac{6r}{u}.
$$

For $r>0$, only $\phi=0$ is real and it is stable. For $r<0$, $\phi=0$ is unstable and the stable minima are

$$
\phi=\pm\sqrt{-\frac{6r}{u}}.
$$

The two minima are exchanged by the $Z_2$ symmetry.

</details>

### Exercise 2: Gaussian correlation length

Starting from

$$
\mathcal H_2[\phi]
=\frac12\int\frac{d^d k}{(2\pi)^d}(Zk^2+r)\phi(k)\phi(-k),
$$

show that the Gaussian two-point function has correlation length $\xi=\sqrt{Z/r}$ for $r>0$.

<details><summary><strong>Solution</strong></summary>

The inverse of the quadratic kernel is

$$
G(k)=\frac{1}{Zk^2+r}.
$$

Factor out $Z$:

$$
G(k)=\frac{1}{Z}\frac{1}{k^2+r/Z}.
$$

The pole scale is

$$
\xi^{-2}=\frac{r}{Z},
$$

so

$$
\xi=\sqrt{\frac{Z}{r}}.
$$

As $r\to0^+$, $\xi$ diverges.

</details>

### Exercise 3: The upper critical dimension

Use Gaussian dimensions to show that the quartic coupling in $\phi^4$ theory has engineering dimension $4-d$.

<details><summary><strong>Solution</strong></summary>

At the Gaussian fixed point, the gradient term fixes

$$
[\phi]=\frac{d-2}{2}.
$$

Therefore

$$
[\phi^4]=4\cdot\frac{d-2}{2}=2d-4.
$$

Since the Lagrangian density has dimension $d$, the coupling $u$ in $u\phi^4$ has dimension

$$
[u]=d-(2d-4)=4-d.
$$

Thus $u$ is irrelevant for $d>4$, marginal for $d=4$, and relevant for $d<4$.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the field-integral formulation of statistical critical phenomena and the renormalization of $\phi^4$ theories.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the renormalization-group chapter and the Landau–Ginzburg–Wilson treatment of transitions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23, for a particle-physics-oriented route to RG and scalar flows.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact statistical-mechanics treatment of scaling and universality.

## Version history

- 2026-06-18: First polished draft. Introduced Landau–Ginzburg functionals, mean-field theory, Gaussian fluctuations, upper critical dimension, and the relation to Euclidean QFT.
