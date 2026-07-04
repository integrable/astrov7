---
title: "Three-State Potts CFT"
description: "The c=4/5 rational CFT describing the critical three-state Potts model, including its minimal-model origin, D4 modular invariant, primary sectors, and benchmark exponents."
sidebar:
  label: "Three-State Potts CFT"
  order: 11
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Zamolodchikov and Fateev; Di Francesco, Mathieu, and Senechal chs. 7, 10, 12; standard Potts and parafermion literature."
topics:
  - three-state Potts model
  - rational CFT
  - minimal models
  - parafermions
  - modular invariants
canonicalTopics:
  - three-state-potts-cft
  - minimal-model-m-5-6
  - z3-parafermion-cft
researchStatus:
  established:
    - "The critical two-dimensional three-state Potts model is described by a c=4/5 rational CFT, equivalently the D4 modular invariant of the Virasoro minimal model M(5,6) or the Z3 parafermion CFT."
  active:
    - "The model remains a benchmark for non-diagonal modular invariants, parafermion symmetry, boundary conditions, lattice-to-CFT dictionaries, and categorical descriptions of rational CFT."
---

## Summary

The **three-state Potts CFT** is the exact conformal field theory of the two-dimensional critical three-state Potts universality class. Its central charge is

$$
c=\frac45.
$$

It can be described in two closely related ways:

$$
\text{three-state Potts CFT}
\simeq
\text{the }D_4\text{ modular invariant of }\mathcal M(5,6)
\simeq
\mathbb Z_3\text{ parafermion CFT}.
$$

This distinction matters. The Virasoro minimal model $\mathcal M(5,6)$ has a finite Kac table, but the Potts model is not the diagonal $A$-series modular invariant. It uses a non-diagonal modular invariant and is more naturally organized by an extended chiral algebra.

The leading physical operators are the spin fields $\sigma,\sigma^\dagger$ and the energy field $\epsilon$, with dimensions

$$
\Delta_\sigma=\Delta_{\sigma^\dagger}=\frac{2}{15},
\qquad
\Delta_\epsilon=\frac45.
$$

These dimensions give the familiar exact critical exponents of the two-dimensional three-state Potts model.

## Prerequisites

Read [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/), and [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) first.

The most important warning is that this page uses both Virasoro language and extended-algebra language. A single Potts sector can contain more than one Virasoro character.

## Core idea

The ordinary Ising CFT is the diagonal minimal model $\mathcal M(3,4)$. The tricritical Ising CFT is the diagonal minimal model $\mathcal M(4,5)$. The three-state Potts CFT is subtler: it is related to $\mathcal M(5,6)$, but the physically important Potts modular invariant is non-diagonal.

The unitary minimal model $\mathcal M(5,6)$ has

$$
c=1-\frac{6}{5\cdot6}=\frac45.
$$

The diagonal $A$-series minimal model has ten Virasoro primary families. The critical Potts model instead uses the $D_4$ modular invariant, which groups Virasoro characters into extended sectors. This is the first point where many students realize that

$$
\text{Kac table}\ne\text{full local CFT}.
$$

A local CFT also needs a modular invariant, and different modular invariants can produce different physical theories from the same chiral data.

## Setup and conventions

The minimal-model weights for $\mathcal M(5,6)$ are

$$
h_{r,s}=\frac{(6r-5s)^2-1}{120},
\qquad
1\le r\le4,
\qquad
1\le s\le5,
$$

with field identification

$$
(r,s)\sim(5-r,6-s).
$$

Some useful weights are

| Label | Weight |
|---:|---:|
| $(1,1)$ | $0$ |
| $(1,3)$ | $2/3$ |
| $(1,5)$ | $3$ |
| $(2,1)$ | $2/5$ |
| $(2,3)$ | $1/15$ |
| $(2,5)$ | $7/5$ |

A diagonal scalar built from a Virasoro representation of weight $h$ has dimension

$$
\Delta=2h.
$$

The Potts CFT has a global $\mathbb Z_3$ spin-rotation symmetry, and also a charge-conjugation symmetry exchanging the two nontrivial $\mathbb Z_3$ charges.

## The D4 modular invariant

The Potts partition function can be written in Virasoro characters as

$$
Z_{\rm Potts}
=|\chi_{1,1}+\chi_{1,5}|^2
+|\chi_{2,1}+\chi_{2,5}|^2
+2|\chi_{1,3}|^2
+2|\chi_{2,3}|^2.
$$

This formula is the cleanest way to see the non-diagonal nature of the theory. The vacuum sector is not just $\chi_{1,1}$. It is the extended-algebra sector

$$
\chi_{1,1}+\chi_{1,5}.
$$

The field of weight $h=3$ in that sector is part of the extended chiral algebra. This is related to the $W_3$ organization of the Potts CFT.

The multiplicity-two terms are also important. They encode pairs of fields carrying conjugate $\mathbb Z_3$ charges.

## Primary sectors

In the extended Potts organization, one commonly displays six sectors:

| Sector | Leading Virasoro weight | Dimension | $\mathbb Z_3$ charge | Interpretation |
|---|---:|---:|---:|---|
| $\mathbf 1$ | $0$ | $0$ | $0$ | vacuum sector |
| $\epsilon$ | $2/5$ | $4/5$ | $0$ | energy operator |
| $\sigma$ | $1/15$ | $2/15$ | $1$ | spin operator |
| $\sigma^\dagger$ | $1/15$ | $2/15$ | $2$ | conjugate spin operator |
| $\psi$ | $2/3$ | $4/3$ | $2$ | parafermion-related sector |
| $\psi^\dagger$ | $2/3$ | $4/3$ | $1$ | conjugate parafermion-related sector |

The notation $\psi,\psi^\dagger$ is conventional but deserves care. In parafermion language there are chiral fields of weight $2/3$. In the local bosonic torus partition function, the displayed sectors are organized so that locality is respected by the full left-right theory.

The most important fields for critical exponents are $\sigma$ and $\epsilon$.

## Lattice dictionary

The three-state Potts model has lattice spins taking values in

$$
\{1,\omega,\omega^2\},
\qquad
\omega=e^{2\pi i/3}.
$$

At the critical point, the leading continuum spin operator is

$$
\sigma,
$$

with dimension

$$
\Delta_\sigma=\frac{2}{15}.
$$

The leading thermal perturbation is

$$
\epsilon,
$$

with dimension

$$
\Delta_\epsilon=\frac45.
$$

The continuum scaling expansion of a microscopic lattice spin has the schematic form

$$
s_i\sim A_\sigma a^{\Delta_\sigma}\sigma(x)+\cdots,
$$

where $a$ is the lattice spacing and $A_\sigma$ is nonuniversal. The deviation from the critical temperature couples to

$$
\int d^2x\,\epsilon(x).
$$

The important point is the same as in the Ising case: the lattice model supplies one microscopic realization, but the CFT data describe the universal long-distance fixed point.

## Critical exponents

The spin two-point function scales as

$$
\langle \sigma(x)\sigma^\dagger(0)\rangle
\sim
\frac{1}{|x|^{2\Delta_\sigma}}
=\frac{1}{|x|^{4/15}}.
$$

In two-dimensional statistical-mechanics notation, this gives

$$
\eta=2\Delta_\sigma=\frac{4}{15}.
$$

The thermal RG eigenvalue is

$$
y_t=2-\Delta_\epsilon
=2-\frac45
=\frac65,
$$

so

$$
\nu=\frac1{y_t}=\frac56.
$$

The magnetic RG eigenvalue is

$$
y_h=2-\Delta_\sigma
=2-\frac{2}{15}
=\frac{28}{15}.
$$

From these, one obtains the familiar exponents

$$
\beta=\nu\Delta_\sigma=\frac{1}{9},
\qquad
\alpha=2-2\nu=\frac13,
\qquad
\delta=\frac{y_h}{2-y_h}=14.
$$

This is a clean demonstration of how CFT operator dimensions become measurable critical exponents.

## Fusion and charge selection

The $\mathbb Z_3$ charge imposes immediate selection rules. A correlator on the plane can be nonzero only if the total $\mathbb Z_3$ charge is zero modulo three.

For example,

$$
\langle \sigma\sigma\sigma\rangle
$$

is allowed by $\mathbb Z_3$, while

$$
\langle \sigma\sigma\epsilon\rangle
$$

is not. Meanwhile

$$
\langle \sigma\sigma^\dagger\epsilon\rangle
$$

is allowed.

Selected extended fusion rules have the schematic form

$$
\sigma\times\sigma^\dagger=\mathbf 1+\epsilon,
$$

and

$$
\epsilon\times\epsilon=\mathbf 1+\epsilon.
$$

The full fusion algebra also involves the $\psi$ and $\psi^\dagger$ sectors. For detailed computations, use the rational-CFT fusion rules or the Verlinde formula with the extended modular data rather than guessing from charge conservation alone.

## Parafermion viewpoint

The same CFT is the $\mathbb Z_3$ parafermion theory. More generally, the $\mathbb Z_k$ parafermion CFT has central charge

$$
c=\frac{2(k-1)}{k+2}.
$$

For $k=3$,

$$
c=\frac{2(2)}{5}=\frac45.
$$

This perspective explains why the Potts CFT has fractional-spin chiral parafermionic structures and an extended chiral algebra. It also connects the model to the coset

$$
\frac{SU(2)_3}{U(1)}.
$$

The parafermion formulation is especially useful for current algebra, coset CFTs, and certain statistical models. The minimal-model formulation is often more convenient for Kac-table and Virasoro computations. They describe the same critical theory, organized differently.

## Relevant deformations

The leading symmetry-preserving thermal deformation is

$$
S_{\rm CFT}\longrightarrow S_{\rm CFT}+t\int d^2x\,\epsilon(x).
$$

Since

$$
\Delta_\epsilon=\frac45<2,
$$

this perturbation is relevant. It drives the theory away from the critical point toward ordered or disordered massive phases depending on the sign of $t$.

Magnetic perturbations couple to the charged spin fields:

$$
S_{\rm CFT}\longrightarrow
S_{\rm CFT}+h\int d^2x\,\sigma(x)+\bar h\int d^2x\,\sigma^\dagger(x)+\cdots .
$$

These perturbations break the $\mathbb Z_3$ symmetry. The exact massive deformations of the Potts CFT are an important bridge to integrable QFT, but the fixed-point data alone already explain the universal scaling powers.

## Common pitfalls

**Do not call the Potts CFT the diagonal minimal model without qualification.** It uses the $D_4$ modular invariant of $\mathcal M(5,6)$, not the diagonal $A$-series invariant.

**Do not confuse the Kac table with the full local spectrum.** The Kac table gives chiral Virasoro representations. The local CFT also needs a modular invariant and left-right pairing.

**Do not ignore the extended chiral algebra.** The Potts theory is naturally organized by an extended algebra, often described using $W_3$ or $\mathbb Z_3$ parafermion language.

**Do not identify fusion rules with charge conservation alone.** Charge conservation is necessary, but Virasoro null states and rational-CFT fusion further restrict allowed channels.

**Do not treat lattice fields as exactly equal to continuum fields.** Lattice observables flow to continuum primaries plus less relevant corrections with nonuniversal coefficients.

**Do not overstate locality of chiral parafermions.** Chiral parafermion fields have fractional spin and require careful distinction from full local operators.

## Relations to other pages

This page follows [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) and [Tricritical Ising CFT](/cft-bootstrap/minimal-models-rational-cft/tricritical-ising-cft/) as the next major model example. It uses [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/), and [Verlinde Formula Preview](/cft-bootstrap/minimal-models-rational-cft/verlinde-formula-preview/).

It also prepares [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) through the parafermion and coset viewpoint, and it connects to later pages on statistical models and boundary CFT.

## Research status

The critical three-state Potts CFT is exactly solved as a rational CFT. Its central charge, modular invariant, operator dimensions, critical exponents, and parafermion description are established.

Active uses include boundary and defect classification, non-invertible and categorical symmetry, lattice-to-CFT numerics, integrable perturbations, tensor-network benchmarks, and modular-bootstrap examples. These are modern applications of a solved model, not uncertainties about the basic fixed point.

## Exercises

### Exercise 1

Compute the central charge of $\mathcal M(5,6)$.

<details><summary><strong>Solution</strong></summary>

For the unitary minimal model $\mathcal M(m,m+1)$ with $m=5$,

$$
c=1-\frac{6}{m(m+1)}
=1-\frac{6}{5\cdot6}
=1-\frac15
=\frac45.
$$

</details>

### Exercise 2

Use

$$
h_{r,s}=\frac{(6r-5s)^2-1}{120}
$$

to compute $h_{2,3}$ and $h_{2,1}$.

<details><summary><strong>Solution</strong></summary>

For $(2,3)$,

$$
h_{2,3}=\frac{(12-15)^2-1}{120}
=\frac{9-1}{120}
=\frac{1}{15}.
$$

For $(2,1)$,

$$
h_{2,1}=\frac{(12-5)^2-1}{120}
=\frac{49-1}{120}
=\frac25.
$$

Thus the corresponding diagonal dimensions are $2/15$ and $4/5$.

</details>

### Exercise 3

Derive $\nu=5/6$ from $\Delta_\epsilon=4/5$.

<details><summary><strong>Solution</strong></summary>

The RG eigenvalue of the thermal perturbation in two dimensions is

$$
y_t=2-\Delta_\epsilon=2-\frac45=\frac65.
$$

The correlation-length exponent is

$$
\nu=\frac1{y_t}=\frac56.
$$

</details>

### Exercise 4

Why does the term $2|\chi_{2,3}|^2$ in the Potts partition function naturally suggest two conjugate spin sectors?

<details><summary><strong>Solution</strong></summary>

The representation $(2,3)$ has weight $h=1/15$, giving the leading spin dimension $\Delta=2/15$. The coefficient $2$ means that two copies of this diagonal Virasoro sector appear in the full local theory. These are naturally identified with the two nontrivial $\mathbb Z_3$ charge sectors, represented by $\sigma$ and $\sigma^\dagger$.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- A. B. Zamolodchikov and V. A. Fateev, “Nonlocal parafermion currents in two-dimensional conformal quantum field theory and self-dual critical points in $Z_N$ symmetric statistical systems,” *Soviet Physics JETP* **62** (1985).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- R. J. Baxter, *Exactly Solved Models in Statistical Mechanics*, Academic Press, 1982.
- J. L. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.

## Version history

- 2026-06-30: First polished draft. Added the $c=4/5$ identification, $D_4$ modular invariant, primary sectors, lattice dictionary, critical exponents, parafermion viewpoint, deformations, exercises, and references.
