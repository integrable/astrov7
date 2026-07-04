---
title: "Free Fermion CFT"
description: "Defines the two-dimensional free Majorana fermion CFT, including its OPEs, stress tensor, central charge, spin sectors, and Ising-model connection."
sidebar:
  label: "Free Fermion CFT"
  order: 9
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Ginsparg 1988; BPZ 1984; Mussardo 2010"
topics:
  - two-dimensional CFT
  - free fermion
  - Majorana fermion
  - Ising CFT
  - spin structures
canonicalTopics:
  - free-majorana-fermion-conformal-field-theory
  - fermion-ope-and-central-charge-one-half
  - neveu-schwarz-and-ramond-sectors
  - free-fermion-and-ising-cft-connection
researchStatus:
  established:
    - "The free Majorana fermion is the canonical fermionic two-dimensional CFT with chiral central charge one-half, fermion OPE ψψ ∼ 1/(z-w), and a direct relation to the Ising universality class."
  active:
    - "Spin-CFT language, fermionic modular invariants, defects, fermionization, bosonization, and categorical descriptions are standard modern refinements beyond the elementary local OPE presentation."
---

## Summary

The free fermion CFT is the two-dimensional conformal field theory of a massless Majorana fermion. In complex coordinates it splits into chiral pieces

$$
\psi(z),
\qquad
\bar\psi(\bar z),
$$

with local OPEs

$$
\psi(z)\psi(w)\sim {1\over z-w},
\qquad
\bar\psi(\bar z)\bar\psi(\bar w)\sim {1\over \bar z-\bar w}.
$$

The holomorphic stress tensor is

$$
T(z)=-{1\over 2}:\psi\partial\psi:(z),
$$

and

$$
T(z)\psi(w)
\sim
{{1\over2}\psi(w)\over (z-w)^2}
+{\partial\psi(w)\over z-w}.
$$

Thus $\psi$ is a chiral primary of weight $h=1/2$. The stress-tensor OPE has central charge

$$
c={1\over2}.
$$

This page explains the free Majorana theory, its Neveu–Schwarz and Ramond sectors, its local operators, and its precise relationship to the critical Ising CFT. The main caveat is global: a fermionic theory depends on spin structure, while the bosonic Ising CFT is obtained after a specific projection or sum over spin-structure data.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

It is useful to have read [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/), because the boson and fermion are the two simplest Gaussian examples and meet through bosonization.

## Core idea

The free fermion is the fermionic Gaussian CFT. Its local OPE is even simpler than the free boson OPE, because the fermion has a power-law two-point function rather than a logarithm. The price is that global data become subtler: fermions require spin structures, and the distinction between a fermionic spin CFT and a bosonic local CFT matters.

<figure class="doc-figure" style="--figure-width: 50rem;">

![The free Majorana fermion has chiral fermion fields, NS and R sectors, a c equals one-half stress tensor, and an Ising CFT relation.](/figures/cft-bootstrap/free-fermion-sectors.svg)

<figcaption>

The local Majorana OPE gives a chiral Virasoro algebra with $c=1/2$. On the circle, the fermion has Neveu–Schwarz and Ramond moding; after the appropriate bosonic projection, the same data organize the Ising primaries $\mathbf 1$, $\epsilon$, and $\sigma$.

</figcaption>
</figure>

The free fermion is therefore both a model and a warning label. Locally, it is just a chiral field of weight $1/2$. Globally, it teaches why boundary conditions around cycles are part of the definition of a fermionic two-dimensional theory.

## Setup and conventions

We use Euclidean complex coordinates. The nonchiral free Majorana action may be written schematically as

$$
S={1\over 2\pi}\int d^2z\,
\left(\psi\bar\partial\psi+\bar\psi\partial\bar\psi\right),
$$

up to convention-dependent factors that do not affect the OPE normalization fixed below. The equations of motion are

$$
\bar\partial\psi=0,
\qquad
\partial\bar\psi=0.
$$

Thus $\psi$ is holomorphic and $\bar\psi$ is antiholomorphic. We normalize the chiral two-point functions by

$$
\langle \psi(z)\psi(w)\rangle={1\over z-w},
\qquad
\langle \bar\psi(\bar z)\bar\psi(\bar w)\rangle={1\over \bar z-\bar w}.
$$

The fields anticommute. Radial ordering must therefore include fermion signs. In a product such as $\psi(z)\psi(w)$, exchanging the two insertions changes the sign of the operator product, and the singular kernel changes sign as well:

$$
{1\over z-w}=-{1\over w-z}.
$$

This is exactly what the OPE needs for consistency.

## Theory data

| Object | Formula | Meaning |
|---|---|---|
| Chiral field | $\psi(z)$ | Majorana fermion of weight $1/2$. |
| OPE | $\psi(z)\psi(w)\sim 1/(z-w)$ | Fermionic short-distance singularity. |
| Stress tensor | $T=-{1\over2}:\psi\partial\psi:$ | Free-fermion Virasoro generator. |
| Central charge | $c=1/2$ | One real chiral Majorana degree of freedom. |
| Energy operator | $\epsilon\sim i\psi\bar\psi$ | Local scalar of weights $(1/2,1/2)$. |
| NS modes | $r\in\mathbb Z+1/2$ | Antiperiodic fermion on the circle. |
| R modes | $r\in\mathbb Z$ | Periodic fermion and zero-mode sector. |
| Ising spin field | $\sigma$ | Twist field of weights $(1/16,1/16)$ in the bosonic Ising CFT. |

The antiholomorphic sector has the same data with bars. A full nonchiral Majorana theory has $c=\bar c=1/2$.

## Stress tensor and central charge

The stress tensor is

$$
T(z)=-{1\over2}:\psi\partial\psi:(z).
$$

Using

$$
\psi(z)\psi(w)\sim {1\over z-w},
\qquad
\partial\psi(z)\psi(w)\sim -{1\over (z-w)^2},
$$

one obtains

$$
T(z)\psi(w)
\sim
{{1\over2}\psi(w)\over (z-w)^2}
+{\partial\psi(w)\over z-w}.
$$

So $\psi$ is a chiral primary of weight $h=1/2$. The double Wick contractions in $T(z)T(w)$ give

$$
T(z)T(w)
\sim
{1/4\over (z-w)^4}
+{2T(w)\over (z-w)^2}
+{\partial T(w)\over z-w}.
$$

The coefficient of $(z-w)^{-4}$ is $c/2$, hence

$$
c={1\over2}.
$$

This is the smallest central charge in the unitary Virasoro minimal series.

## Modes on the circle

In radial quantization a chiral fermion has expansion

$$
\psi(z)=\sum_r \psi_r z^{-r-1/2}.
$$

The OPE implies the Clifford algebra

$$
\{\psi_r,\psi_s\}=\delta_{r+s,0}.
$$

The allowed values of $r$ depend on the boundary condition of the cylinder field around the spatial circle. Under $z=e^w$, the cylinder field is $\psi_{\rm cyl}(w)=z^{1/2}\psi(z)$, so

$$
\psi_{\rm cyl}(w)=\sum_r\psi_r e^{-rw}.
$$

The sector table is therefore

| Sector | Cylinder boundary condition | Modes | Basic interpretation |
|---|---|---|---|
| Neveu–Schwarz | $\psi_{\rm cyl}(\sigma+2\pi)=-\psi_{\rm cyl}(\sigma)$ | $r\in\mathbb Z+1/2$ | Antiperiodic fermion; no zero mode. |
| Ramond | $\psi_{\rm cyl}(\sigma+2\pi)=+\psi_{\rm cyl}(\sigma)$ | $r\in\mathbb Z$ | Periodic fermion; has a zero mode $\psi_0$. |

The NS vacuum is the ordinary identity-sector vacuum. The Ramond sector contains fermion zero modes and corresponds, in the bosonic Ising language, to twist fields with chiral weight

$$
h={1\over 16}.
$$

The most important lesson is not the number $1/16$ by itself. It is that local OPEs do not determine all global sectors unless one also specifies how fields behave around nontrivial cycles or branch points.

## Fermion parity and locality

The free Majorana theory has a fermion-parity symmetry

$$
(-1)^F:
\psi\mapsto -\psi,
\qquad
\bar\psi\mapsto -\bar\psi.
$$

Operators split into parity-even and parity-odd classes. The scalar

$$
\epsilon(z,\bar z)=i\psi(z)\bar\psi(\bar z)
$$

is parity even and has weights

$$
(h,\bar h)=\left({1\over2},{1\over2}\right).
$$

The chiral fermions $\psi$ and $\bar\psi$ are fermionic operators. They are local in a spin theory, where correlation functions depend on a spin structure. They are not ordinary bosonic local operators in a purely bosonic CFT.

This distinction is why one must say carefully what is meant by “the free fermion CFT.” There are two closely related viewpoints:

| Viewpoint | What is local | What data are needed |
|---|---|---|
| Fermionic spin CFT | Fermion operators such as $\psi$ are allowed. | A spin structure on the surface. |
| Bosonic Ising CFT | Bosonic local operators such as $\mathbf 1$, $\epsilon$, $\sigma$ are local. | Modular-invariant bosonic projection/sum over spin data. |

Both viewpoints are useful. Problems arise only when one silently switches between them.

## Ising connection

The critical Ising model is the most famous physical realization of the $c=1/2$ CFT. Its diagonal bosonic local operator spectrum contains the three Virasoro primaries

| Field | Weights | Common interpretation |
|---|---:|---|
| $\mathbf 1$ | $(0,0)$ | Identity. |
| $\epsilon$ | $(1/2,1/2)$ | Energy-density operator. |
| $\sigma$ | $(1/16,1/16)$ | Spin/order operator. |

The fusion rules are

$$
\epsilon\times\epsilon=\mathbf 1,
\qquad
\epsilon\times\sigma=\sigma,
\qquad
\sigma\times\sigma=\mathbf 1+\epsilon.
$$

The fermion description makes the energy operator simple:

$$
\epsilon\sim i\psi\bar\psi.
$$

The spin field $\sigma$ is not a polynomial in $\psi$ and $\bar\psi$. It is a twist field: taking the fermion around $\sigma$ changes the fermion boundary condition. That branch-cut effect is the local field theory avatar of the order/disorder structure of the Ising model.

## Bosonization preview

Two real Majorana fermions are equivalent to one complex Dirac fermion. A complex Dirac fermion has total central charge

$$
c=1.
$$

This matches the free boson. Locally one may write chiral bosonization formulas of the form

$$
\psi_{\rm Dirac}(z)\sim :e^{i\varphi(z)}:,
\qquad
\psi_{\rm Dirac}^{\dagger}(z)\sim :e^{-i\varphi(z)}:,
$$

with $\varphi(z)\varphi(w)\sim -\log(z-w)$. This is a local OPE dictionary, not automatically a complete statement about Hilbert spaces on arbitrary Riemann surfaces. To make bosonization global, one must track charge lattices, spin structures, and fermion parity.

## Checks

| Check | Result |
|---|---|
| Fermion weight | $T(z)\psi(w)\sim {1\over2}\psi/(z-w)^2+\partial\psi/(z-w)$ |
| Central charge | $T(z)T(w)$ has fourth-order coefficient $1/4$, hence $c=1/2$. |
| Energy dimension | $\epsilon=i\psi\bar\psi$ has $(h,\bar h)=(1/2,1/2)$. |
| Fermion modes | NS: half-integers; R: integers. |
| Ising twist field | Ramond twist has $h=\bar h=1/16$ in the diagonal Ising theory. |

A practical sign check is the OPE $\partial\psi(z)\psi(w)\sim -1/(z-w)^2$. Missing this minus sign often flips the stress-tensor normalization.

## Common pitfalls

**Ignoring spin structure.** Fermion partition functions and correlators on a circle or torus depend on boundary conditions. A statement about the free fermion on the plane may not immediately determine the modular-invariant theory on the torus.

**Equating the spin CFT and bosonic Ising CFT without qualification.** The local OPEs are closely related, but the lists of local operators and the global data differ. The bosonic Ising CFT is not simply the theory where the chiral fermion $\psi$ is an ordinary bosonic local field.

**Forgetting fermion signs in radial ordering.** Fermion OPEs are compatible with anticommutation only when radial ordering includes the correct signs. Treating $\psi$ like a commuting field gives wrong contour and mode algebra signs.

**Calling $\sigma$ a fermion bilinear.** The spin field $\sigma$ has weight $(1/16,1/16)$ and changes fermion boundary conditions. It is a twist field, not a polynomial in $\psi$ and $\bar\psi$.

**Counting central charge twice.** In 2D CFT it is common to call the nonchiral Ising model a $c=1/2$ theory, meaning $c=\bar c=1/2$. Cylinder energies and anomalies must use the left and right central charges in the appropriate combination.

## Relations to other pages

- [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/) gives the parallel Gaussian bosonic example and sets up bosonization.
- [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) explains how singular OPEs produce contour-mode algebras.
- [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) explains the circle quantization in which NS and R sectors are defined.
- [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) develops the $c=1/2$ chiral algebra more systematically.
- [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) places the Ising CFT as the first nontrivial unitary minimal model.
- [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) develops the order, disorder, energy, and fermion descriptions of the critical Ising point.

## Research status

The free Majorana fermion, its stress tensor, its $c=1/2$ central charge, its NS/R mode structure, and its relation to the critical Ising universality class are textbook-standard. The main modern refinements concern global formulations: spin CFTs, fermion parity gauging, Arf invariants, duality defects, boundary conditions, and categorical treatments of Ising-type theories.

For many calculations, the local OPE page-level treatment is enough. For modular invariance, boundary states, defects, or fermionization, one must keep the spin-structure data explicit.

## Exercises

### Exercise 1: Derive the fermion weight

Using

$$
T(z)=-{1\over2}:\psi\partial\psi:(z),
\qquad
\psi(z)\psi(w)\sim {1\over z-w},
$$

show that $\psi$ has conformal weight $1/2$.

<details>
<summary><strong>Solution</strong></summary>

The needed contractions are

$$
\psi(z)\psi(w)\sim {1\over z-w},
\qquad
\partial\psi(z)\psi(w)\sim -{1\over (z-w)^2}.
$$

In the product $-{1\over2}:\psi\partial\psi:(z)\psi(w)$, the double-pole term comes from contracting $\partial\psi(z)$ with $\psi(w)$ and keeping the remaining $\psi(z)$, expanded around $w$. The fermion signs combine so that

$$
T(z)\psi(w)
\sim
{{1\over2}\psi(w)\over (z-w)^2}
+{\partial\psi(w)\over z-w}.
$$

Therefore $h=1/2$.

</details>

### Exercise 2: Read the central charge

The Virasoro OPE has the form

$$
T(z)T(w)
\sim
{c/2\over (z-w)^4}+{2T(w)\over (z-w)^2}+{\partial T(w)\over z-w}.
$$

If the double contractions of $T=-{1\over2}:\psi\partial\psi:$ give $1/(4(z-w)^4)$, what is $c$?

<details>
<summary><strong>Solution</strong></summary>

Compare coefficients:

$$
{c\over2}={1\over4}.
$$

Hence

$$
c={1\over2}.
$$

</details>

### Exercise 3: NS versus R modes

Use the cylinder field

$$
\psi_{\rm cyl}(w)=z^{1/2}\psi(z)=\sum_r\psi_r e^{-rw},
\qquad
z=e^w,
$$

to show that antiperiodic cylinder boundary conditions give half-integer $r$, while periodic cylinder boundary conditions give integer $r$.

<details>
<summary><strong>Solution</strong></summary>

On the cylinder, going once around the spatial circle sends $w\mapsto w+2\pi i$. A mode transforms as

$$
e^{-rw}\mapsto e^{-2\pi ir}e^{-rw}.
$$

For antiperiodic boundary conditions this phase should be $-1$, so $e^{-2\pi ir}=-1$, which gives $r\in\mathbb Z+1/2$. For periodic boundary conditions the phase should be $+1$, so $e^{-2\pi ir}=1$, which gives $r\in\mathbb Z$.

</details>

### Exercise 4: Dimension of the energy operator

Let $\epsilon=i\psi\bar\psi$. Use the weights of $\psi$ and $\bar\psi$ to find the weights and scaling dimension of $\epsilon$.

<details>
<summary><strong>Solution</strong></summary>

The field $\psi$ has weights $(1/2,0)$ and $\bar\psi$ has weights $(0,1/2)$. Therefore their product has

$$
(h,\bar h)=\left({1\over2},{1\over2}\right).
$$

The scaling dimension is

$$
\Delta=h+\bar h=1.
$$

</details>

## References

### Standard first pass

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on free fields, operator formalism, the Ising model, and modular invariance.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, for a concise treatment of free fermions, sectors, and Ising data.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, *Infinite Conformal Symmetry in Two-Dimensional Quantum Field Theory*, for the original minimal-model/bootstrap perspective.

### Deeper references

- G. Mussardo, *Statistical Field Theory*, for the statistical-mechanics route to the Ising fermion.
- E. Witten, notes and papers on fermion path integrals and spin structures, for modern global aspects of fermionic theories.

## Version history

- **2026-06-28:** Initial polished draft for the Two-Dimensional CFT chapter.
