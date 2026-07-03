---
title: "Ising Model to Field Theory"
description: "How the nearest-neighbor Ising model becomes a local scalar Landau–Ginzburg field theory near criticality."
sidebar:
  label: "Ising Model to Field Theory"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§1–8 and 10; Zinn-Justin 2021, critical phenomena chapters; Altland and Simons 2023, ch. 6; Polyakov 1987, chs. 1–3."
topics:
  - Ising model
  - coarse graining
  - block spins
  - Landau-Ginzburg theory
  - Ising universality class
  - continuum limit
canonicalTopics:
  - ising-model
  - ising-universality-class
  - landau-ginzburg-wilson-field-theory
researchStatus:
  established:
    - "The continuum description of the short-range Ising critical point is the scalar Landau–Ginzburg–Wilson field theory with one real order parameter and Z₂ symmetry."
  active:
    - "Precise critical data, boundary and defect universality, long-range Ising variants, disordered Ising systems, and quantum Ising transitions remain active research areas."
---

## Summary

The nearest-neighbor Ising model is

$$
H[\{s_i\}]
=-J\sum_{\langle ij\rangle}s_i s_j
-h\sum_i s_i,
\qquad
s_i=\pm1.
$$

Near its continuous transition, this lattice spin model is described at long distances by a scalar Euclidean field theory,

$$
\mathcal H[\phi]
=
\int d^d x\left[
\frac12 Z(\nabla\phi)^2
+\frac12 r\phi^2
+\frac{u}{4!}\phi^4
-h_R\phi
+\cdots
\right],
$$

where $\phi(x)$ is a coarse-grained magnetization field. At zero magnetic field, the microscopic spin-flip symmetry

$$
s_i\mapsto -s_i
$$

becomes the field symmetry

$$
\phi(x)\mapsto -\phi(x).
$$

The important statement is not that one can calculate the exact continuum coefficients $Z$, $r$, and $u$ by staring hard enough at the lattice Hamiltonian. The important statement is that, when the correlation length satisfies $\xi\gg a$, where $a$ is the lattice spacing, the long-distance physics is controlled by a local field theory with the same symmetry and relevant perturbations.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 54rem;">

![A short-range Ising lattice model is coarse-grained into a local scalar Landau-Ginzburg field theory and then into the Ising universality class.](/figures/renormalization-rg-eft/ising-to-field-theory-pipeline.svg)

<figcaption>

A short-range Ising model flows, after coarse graining, to a local order-parameter field theory. Microscopic constants determine nonuniversal coordinates such as $Z$, $r$, $u$, and $h_R$, but the critical exponents and scaling functions are controlled by the Ising fixed point and its relevant perturbations.

</figcaption>
</figure>

## Prerequisites

You should know [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/), [Blocking and Coarse Graining](/renormalization-rg-eft/wilsonian-renormalization/blocking-and-coarse-graining/), [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), and [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/). This page is the canonical bridge from lattice statistical mechanics to continuum scalar field theory.

## Core idea

The Ising model contains microscopic variables $s_i=\pm1$ on lattice sites. A continuum field theory contains a smooth variable $\phi(x)$. These are not the same object. The bridge is **coarse graining**.

Choose a block size $b$ satisfying

$$
a\ll b\ll \xi,
$$

where $a$ is the lattice spacing and $\xi$ is the correlation length. Define a block magnetization, schematically,

$$
\phi_B(x)
\propto
\frac{1}{b^d}\sum_{i\in B(x)}s_i.
$$

The block variable is no longer restricted to $\pm1$. It can fluctuate continuously because it averages many spins. When neighboring blocks have similar magnetization, the field varies slowly and a derivative expansion becomes possible.

The resulting continuum description is organized by three inputs:

| Input | Consequence |
|---|---|
| Short-range microscopic interactions | local field functional |
| Spin-flip symmetry at $h=0$ | only even powers of $\phi$ at zero field |
| Diverging correlation length | continuum scaling limit |

The Ising-to-field-theory map is therefore not a microscopic identity. It is an infrared statement.

## Setup and conventions

We use $d$ for the spatial dimension of the statistical system and $a$ for the lattice spacing. The microscopic spins are denoted $s_i=\pm1$. The dimensionless lattice couplings are

$$
K=\frac{J}{T},
\qquad
h=\frac{H}{T},
$$

with $k_B=1$. The continuum field $\phi(x)$ is a coarse-grained representative of the spin-odd order parameter. Its normalization is not universal.

The continuum action is Euclidean,

$$
Z=\int\mathcal D\phi\,e^{-S_E[\phi]},
$$

and is valid only for wavelengths long compared with the lattice spacing.


## The lattice model

On a $d$-dimensional lattice, the ferromagnetic nearest-neighbor Ising Hamiltonian is

$$
H[\{s_i\}]
=-J\sum_{\langle ij\rangle}s_i s_j
-h\sum_i s_i,
\qquad J>0.
$$

The partition function is

$$
Z_{\text{Ising}}
=
\sum_{\{s_i=\pm1\}}e^{-\beta H[\{s_i\}]},
\qquad
\beta=\frac{1}{k_B T}.
$$

At $h=0$, the Hamiltonian is invariant under the global transformation

$$
s_i\mapsto -s_i
\quad\text{for all }i.
$$

The magnetization per site is

$$
m=\frac{1}{N}\sum_i\langle s_i\rangle.
$$

In the disordered phase, $m=0$. In the ordered phase, the infinite-volume system can choose $m>0$ or $m<0$. The phase transition separates these regimes.

For dimensions $d\ge2$, the ferromagnetic Ising model has a finite-temperature transition. In $d=1$ with short-range interactions, there is no finite-temperature transition: domain walls cost finite energy and their entropy destroys long-range order at any nonzero temperature.

## The continuum field

The coarse field $\phi(x)$ represents local magnetization density. One can think of it as a smoothed version of the lattice spin configuration:

$$
\phi(x)
\sim
\sum_i W_b(x-x_i)s_i,
$$

where $W_b$ is a smooth averaging kernel of width $b$. The precise choice of $W_b$ is not universal. Different kernels give different coordinates on the same long-distance theory.

Because $\phi$ is an average over many spins, it is a real continuous variable. Because the microscopic model at $h=0$ has spin-flip symmetry, the effective functional must be invariant under

$$
\phi\to -\phi.
$$

Because the microscopic interactions are short-ranged, the long-distance functional is local:

$$
\mathcal H[\phi]
=
\int d^d x\,\mathcal L_{\text{eff}}(\phi,\nabla\phi,\nabla^2\phi,\ldots).
$$

Expanding in powers of $\phi$ and derivatives gives the scalar Landau–Ginzburg form.

## Why the functional is local

Locality is the crucial assumption. A short-range lattice Hamiltonian couples nearby spins. After coarse graining, nearby blocks couple more strongly than distant blocks. If correlations are smooth on the block scale, the interaction between neighboring blocks can be expanded in derivatives.

The leading derivative term is

$$
\frac12 Z(\nabla\phi)^2.
$$

Terms with more derivatives, such as

$$
(\nabla^2\phi)^2,
\qquad
\phi^2(\nabla\phi)^2,
\qquad
(\nabla\phi)^4,
$$

are allowed by symmetry but are usually less relevant near the ordinary Ising fixed point. They belong in the ellipsis.

The local potential contains all local powers allowed by the symmetry. At zero magnetic field,

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4+\frac{v}{6!}\phi^6+\cdots.
$$

Turning on $h$ permits odd terms. The leading one is the source term

$$
-h_R\phi.
$$

The subscript on $h_R$ reminds us that the continuum source is a renormalized scaling-field coordinate, not necessarily the microscopic magnetic field with its original normalization.

## Temperature and magnetic field as scaling directions

Near the Ising fixed point, the two most important relevant perturbations are:

| Lattice knob | Continuum perturbation | Symmetry |
|---|---|---|
| temperature deviation $T-T_c$ | energy-like operator, represented first by $\phi^2$ | even under $\phi\to-\phi$ |
| magnetic field $h$ | spin-like operator, represented first by $\phi$ | odd under $\phi\to-\phi$ |

In the simplest Landau–Ginzburg coordinates, one writes

$$
r\propto T-T_c,
\qquad
h_R\propto h.
$$

This is correct as a leading schematic statement. More precisely, $r$ and $h_R$ are analytic coordinates along the relevant scaling directions. They can contain nonuniversal normalization factors and analytic mixing with other microscopic parameters, subject to symmetry.

At criticality, both relevant perturbations are tuned to zero:

$$
r=r_c,
\qquad
h_R=0,
$$

where in a convenient renormalized coordinate one often shifts $r_c$ to zero. On the lattice, this corresponds to tuning the temperature to $T_c$ and setting the magnetic field to zero.

## A schematic derivation by block spins

A useful mental derivation proceeds in three steps.

First, divide the lattice into blocks and define block spins or block magnetizations. A block magnetization can take many values, not just $\pm1$. Its distribution is approximately smooth when the block contains many microscopic sites.

Second, write an effective probability distribution for the block magnetization field. Because the original interactions are short-ranged, the distribution is approximately exponential in a local functional:

$$
P[\phi]\propto e^{-\mathcal H[\phi]}.
$$

Third, expand the local functional in powers of fields and gradients. Symmetry forces the zero-field functional to be even under $\phi\to-\phi$:

$$
\mathcal H[\phi]
=
\int d^d x\left[
\frac12 Z(\nabla\phi)^2
+\frac12 r\phi^2
+\frac{u}{4!}\phi^4
+\frac{v}{6!}\phi^6
+\cdots
\right].
$$

The continuum limit keeps only the terms needed to reach the desired accuracy in the RG expansion. For universal leading critical behavior in the ordinary short-range Ising class below four dimensions, the $\phi^4$ truncation captures the relevant structure.

:::caution[Not an equality of partition functions]
The expression

$$
Z_{\text{Ising}}\approx \int \mathcal D\phi\,e^{-\mathcal H[\phi]}
$$

is not an exact identity with the displayed finite polynomial functional. It is an effective description in the scaling regime. The omitted terms are real; the RG tells us why they do not change the leading universal critical behavior.
:::

## Hubbard–Stratonovich viewpoint

For some lattice models, one can make the bridge more algebraic by introducing an auxiliary field. Schematically, an interaction quadratic in spins can be rewritten by a Gaussian integral over a field. For a positive kernel $K$, one uses a finite-dimensional version of

$$
\exp\left(\frac12 s_i K_{ij}s_j\right)
\propto
\int d\phi\,
\exp\left[-\frac12\phi_i K^{-1}_{ij}\phi_j+\phi_i s_i\right].
$$

After summing over $s_i=\pm1$, one obtains an effective action for $\phi_i$. Expanding slowly varying fields near small momentum leads to a local continuum functional.

This derivation is useful because it shows how an apparently discrete problem can be rewritten in terms of continuous fields. But one should not overinterpret the auxiliary field. The physical reason the continuum theory works is still scale separation and universality.

## Universality class

The Ising universality class is not a single lattice Hamiltonian. It is a basin of attraction in theory space. A system belongs to the ordinary short-range Ising universality class when its critical long-distance theory has:

- one real scalar order parameter;
- a $Z_2$ symmetry at zero field;
- short-range interactions;
- no additional gapless modes or constraints that change the infrared fixed point;
- no relevant perturbations left untuned except the desired temperature and magnetic-field directions.

Examples include uniaxial ferromagnets, binary fluid mixtures, lattice gases, and liquid–gas transitions after appropriate identification of the order parameter and scaling fields.

The long-distance critical data are universal: exponents, operator dimensions, scaling functions after normalization, and amplitude ratios. The critical temperature, microscopic magnetization normalization, and nonuniversal metric factors are not universal.

## Dimensions and fixed points

The behavior depends strongly on dimension.

| Dimension | Long-distance story |
|---:|---|
| $d=1$ | no finite-temperature transition for short-range ferromagnetic Ising interactions |
| $d=2$ | exactly solved lattice model; critical point described by the two-dimensional Ising CFT |
| $d=3$ | nontrivial Wilson–Fisher Ising fixed point; precision data from bootstrap, Monte Carlo, field theory, and experiments |
| $d=4$ | upper critical dimension; mean-field behavior with logarithmic corrections |
| $d>4$ | Gaussian fixed point controls leading exponents; dangerously irrelevant variables can affect some finite-size and scaling details |

The same Landau–Ginzburg functional appears in all these discussions, but the infrared fixed point and fluctuation physics depend on $d$.

## Correlation functions

The lattice spin two-point function is

$$
G_{ij}=\langle s_i s_j\rangle-\langle s_i\rangle\langle s_j\rangle.
$$

In the continuum theory, the corresponding long-distance object is

$$
G(x)=\langle \phi(x)\phi(0)\rangle
-\langle \phi\rangle^2.
$$

Away from criticality, the connected correlator decays exponentially,

$$
G(x)\sim e^{-|x|/\xi}
\times \text{power-law prefactor}.
$$

At criticality, it decays as a power law,

$$
G(x)\sim \frac{1}{|x|^{d-2+\eta}},
$$

where $\eta$ is the anomalous dimension exponent of the spin field. In mean-field theory, $\eta=0$. At the interacting Ising fixed point below four dimensions, $\eta$ is nonzero.

## What the field theory forgets

The continuum field theory forgets many microscopic facts:

- the exact lattice geometry;
- whether the microscopic variables are spins, occupations, or molecular identities;
- the exact value of $J$;
- the details of the block-spin kernel;
- most higher-order local operators.

It does **not** forget everything. It remembers:

- spatial dimension;
- locality or long-range character;
- internal symmetry;
- number of order-parameter components;
- conserved quantities or constraints;
- relevant perturbations;
- topological defects when they are infrared-important.

Universality is selective forgetfulness, not amnesia with a physics degree.

## Common pitfalls

**A single spin is not the field $\phi(x)$.** The field is a coarse-grained magnetization variable.

**The continuum theory is not exact at the lattice scale.** It describes distances large compared with $a$, especially near $\xi\gg a$.

**The $\phi^4$ theory is not chosen because higher powers are impossible.** Higher powers are allowed but usually irrelevant for leading Ising criticality below four dimensions.

**The coefficient $r$ is not literally temperature.** It is a continuum coordinate along the temperature-like scaling direction.

**The Ising universality class is not all $Z_2$ systems.** Long-range interactions, disorder, extra soft modes, gauge constraints, or nonequilibrium dynamics can change the universality class.

**Mean-field exponents are not the three-dimensional Ising exponents.** Mean-field theory is controlled by the Gaussian fixed point. The three-dimensional short-range Ising transition is controlled by an interacting fixed point.

## Relations to other pages

[Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/) gives the continuum functional itself. [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) studies its saddle approximation. [Gaussian Fixed Point](/renormalization-rg-eft/statistical-field-theory-criticality/gaussian-fixed-point/) explains the free critical theory and upper critical dimension. [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) and [Epsilon Expansion](/renormalization-rg-eft/fixed-points-critical-phenomena/epsilon-expansion/) explain the interacting fixed point. [Universality Classes](/renormalization-rg-eft/fixed-points-critical-phenomena/universality-classes/) places the Ising class among other universality classes.

## Research status

The continuum description of the short-range Ising critical point by a scalar $\mathbb Z_2$ field theory is established. In two dimensions the critical theory is exactly solvable; in three dimensions the Ising fixed point is known to high precision through conformal bootstrap, Monte Carlo, and resummed field-theory methods.

Active research includes rigorous scaling limits, boundary and defect criticality, long-range Ising models, disordered systems, quantum Ising criticality, nonequilibrium variants, and the precise relation between lattice operators and continuum scaling operators.

## Exercises

### Exercise 1: Symmetry of the continuum action

At $h=0$, show that spin-flip symmetry forbids a cubic term in the Ising Landau–Ginzburg functional.

<details><summary><strong>Solution</strong></summary>

The microscopic symmetry is

$$
s_i\to -s_i.
$$

The coarse field transforms in the same way:

$$
\phi(x)\to -\phi(x).
$$

A cubic term transforms as

$$
\int d^d x\,\phi^3\to
-\int d^d x\,\phi^3.
$$

It is not invariant, so it is forbidden when the $Z_2$ symmetry is exact. A magnetic field breaks this symmetry and permits odd terms, beginning with $-h_R\phi$.

</details>

### Exercise 2: Why $\phi$ is continuous

Let a block contain $N_B$ spins and define

$$
\phi_B=\frac{1}{N_B}\sum_{i\in B}s_i.
$$

What values can $\phi_B$ take, and why does it become approximately continuous for large $N_B$?

<details><summary><strong>Solution</strong></summary>

If $n_+$ spins are $+1$ and $n_-$ spins are $-1$, then

$$
N_B=n_++n_-,
\qquad
\sum_{i\in B}s_i=n_+-n_-.
$$

Therefore

$$
\phi_B=\frac{n_+-n_-}{N_B}
=\frac{2n_+}{N_B}-1.
$$

The allowed values are spaced by

$$
\Delta\phi_B=\frac{2}{N_B}.
$$

For large blocks, $N_B\gg1$, this spacing is small, so the block magnetization can be treated as approximately continuous.

</details>

### Exercise 3: Relevance of $\phi^6$ near the Gaussian fixed point

At the Gaussian fixed point in $d$ dimensions, show that the coupling $v$ in $v\phi^6$ has engineering dimension $6-2d$. What does this imply at $d=3$?

<details><summary><strong>Solution</strong></summary>

At the Gaussian fixed point,

$$
[\phi]=\frac{d-2}{2}.
$$

Thus

$$
[\phi^6]=6\frac{d-2}{2}=3d-6.
$$

The coupling has dimension

$$
[v]=d-(3d-6)=6-2d.
$$

At $d=3$,

$$
[v]=0.
$$

So $\phi^6$ is marginal by Gaussian power counting in three dimensions. At the interacting Ising fixed point, its actual relevance must be determined by the full scaling dimension, not by Gaussian engineering dimension alone. For the ordinary three-dimensional Ising fixed point, the leading $Z_2$-even relevant direction is temperature-like; higher even operators are not independent relevant tunings for the ordinary critical point.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the systematic relation between lattice/statistical models, field integrals, and RG.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the renormalization-group treatment of ferromagnetic transitions.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the early chapters relating statistical mechanics, Ising-type systems, strong-coupling expansions, and field-theory reasoning.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a concise treatment of scaling fields and Ising universality.

## Version history

- 2026-06-18: First polished draft. Added the coarse-graining route from the nearest-neighbor Ising model to scalar Landau–Ginzburg field theory and the Ising universality class.
