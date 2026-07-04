---
title: "Tricritical Ising CFT"
description: "The c=7/10 minimal model describing the tricritical Ising universality class, including its six primaries, relevant deformations, fusion data, and supersymmetry preview."
sidebar:
  label: "Tricritical Ising CFT"
  order: 3
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Friedan, Qiu, and Shenker; Zamolodchikov; Di Francesco, Mathieu, and Senechal; standard minimal-model literature."
topics:
  - tricritical Ising CFT
  - minimal models
  - rational CFT
  - relevant deformations
  - Kac table
  - supersymmetry preview
canonicalTopics:
  - tricritical-ising-cft
  - minimal-model-m-4-5
  - rational-cft-data
researchStatus:
  established:
    - "The tricritical Ising CFT is the unitary Virasoro minimal model M(4,5) with central charge c=7/10 and six scalar primaries in the diagonal bosonic theory."
  active:
    - "The model remains a benchmark for supersymmetric, boundary, defect, integrable-deformation, lattice, and bootstrap methods."
---

## Summary

The **tricritical Ising CFT** is the conformal field theory of the two-dimensional tricritical Ising universality class. It is the next unitary minimal model after the Ising CFT:

$$
\mathcal M(4,5),
\qquad
c=\frac{7}{10}.
$$

In the diagonal bosonic theory, it has six scalar Virasoro primary fields:

| Field | Kac label | Weights | Dimension | $ℤ_2$ parity | Common role |
|---|---:|---:|---:|---:|---|
| $\mathbf 1$ | $(1,1)$ | $(0,0)$ | $0$ | even | identity |
| $\epsilon$ | $(1,2)$ | $(1/10,1/10)$ | $1/5$ | even | leading thermal operator |
| $\epsilon'$ | $(1,3)$ | $(3/5,3/5)$ | $6/5$ | even | subleading thermal operator |
| $\epsilon''$ | $(1,4)$ | $(3/2,3/2)$ | $3$ | even | leading irrelevant even scalar |
| $\sigma$ | $(2,2)$ | $(3/80,3/80)$ | $3/40$ | odd | leading spin operator |
| $\sigma'$ | $(2,1)$ | $(7/16,7/16)$ | $7/8$ | odd | subleading spin operator |

The Ising CFT has one relevant even scalar, $\epsilon$. The tricritical Ising CFT has two relevant even scalars, $\epsilon$ and $\epsilon'$, which is why it describes a tricritical point rather than an ordinary critical point. It is also the first nontrivial example where the Virasoro minimal-model story meets emergent two-dimensional supersymmetry.

## Prerequisites

Read [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/), [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/), and [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) first.

You should also be comfortable with the convention that a diagonal scalar field with weights $(h,h)$ has scaling dimension

$$
\Delta=2h.
$$

## Core idea

A tricritical point occurs when an ordinary critical point is made more delicate by tuning an additional relevant parameter. In the lattice tricritical Ising model, one can think schematically of an Ising-like system with vacancies or a Blume–Capel-type tuning. At the tricritical point, both a thermal direction and an additional even direction must be tuned.

The CFT expression of that statement is simple:

$$
\mathcal M(4,5)
\quad\text{has two relevant even scalar primaries:}\quad
\epsilon,\ \epsilon'.
$$

The leading spin field is also more relevant than in the ordinary Ising CFT:

$$
\Delta_\sigma=\frac{3}{40},
\qquad
\Delta_\epsilon=\frac15.
$$

Thus the tricritical Ising CFT is not just “Ising with different numbers.” It is a different fixed point with a larger finite operator algebra, more relevant perturbations, and richer representation theory.

## Setup and conventions

We use the unitary minimal-model notation

$$
\mathcal M(m,m+1),
\qquad
c=1-\frac{6}{m(m+1)}.
$$

The tricritical Ising model is $m=4$, hence

$$
c=1-\frac{6}{4\cdot5}=\frac{7}{10}.
$$

Equivalently, write $p=4$ and $p'=5$. The Kac weights are

$$
h_{r,s}
=\frac{(p'r-ps)^2-(p'-p)^2}{4pp'}
=\frac{(5r-4s)^2-1}{80},
$$

with

$$
r=1,2,3,
\qquad
s=1,2,3,4,
$$

and field identification

$$
(r,s)\sim(p-r,p'-s)=(4-r,5-s).
$$

The diagonal local bosonic theory pairs the same chiral and antiholomorphic representation, so each primary in the table has weights $(h,h)$.

## Kac data

The Kac table before field identification contains twelve labels. The identification leaves six primary families. A convenient representative set is

$$
(1,1),\ (1,2),\ (1,3),\ (1,4),\ (2,2),\ (2,1).
$$

Their weights are

| Representative | Weight $h$ | Diagonal dimension $\Delta=2h$ | Field |
|---:|---:|---:|---|
| $(1,1)$ | $0$ | $0$ | $\mathbf 1$ |
| $(1,2)$ | $1/10$ | $1/5$ | $\epsilon$ |
| $(1,3)$ | $3/5$ | $6/5$ | $\epsilon'$ |
| $(1,4)$ | $3/2$ | $3$ | $\epsilon''$ |
| $(2,2)$ | $3/80$ | $3/40$ | $\sigma$ |
| $(2,1)$ | $7/16$ | $7/8$ | $\sigma'$ |

The field identifications include

$$
(3,4)\sim(1,1),
\qquad
(3,3)\sim(1,2),
\qquad
(3,2)\sim(1,3),
\qquad
(3,1)\sim(1,4),
$$

and

$$
(2,3)\sim(2,2),
\qquad
(2,4)\sim(2,1).
$$

The diagonal torus partition function is

$$
Z_{\rm TCI}(\tau,\bar\tau)
=\sum_{h\in\{0,1/10,3/5,3/2,3/80,7/16\}}
|\chi_h(\tau)|^2.
$$

This is the simplest modular-invariant local bosonic tricritical Ising theory.

## Operator dictionary

The tricritical Ising universality class has a $ℤ_2$ spin-flip symmetry. The even fields are thermal or vacancy-like deformations; the odd fields are magnetic deformations.

| Field | Dimension | Interpretation |
|---|---:|---|
| $\epsilon$ | $1/5$ | leading even thermal operator |
| $\epsilon'$ | $6/5$ | subleading even relevant operator, needed for tricritical tuning |
| $\epsilon''$ | $3$ | irrelevant even scalar |
| $\sigma$ | $3/40$ | leading magnetization operator |
| $\sigma'$ | $7/8$ | subleading magnetization operator |

The deformation space near the fixed point has the schematic form

$$
S_{\rm TCI}
\longrightarrow
S_{\rm TCI}
+t\int d^2x\,\epsilon
+g\int d^2x\,\epsilon'
+h\int d^2x\,\sigma
+h'\int d^2x\,\sigma'
+\cdots .
$$

The even tricritical point requires tuning both $t$ and $g$ to zero. The magnetic perturbations $h$ and $h'$ break the $ℤ_2$ symmetry.

The most important contrast with the ordinary Ising CFT is

| Theory | Central charge | Relevant even scalar fields |
|---|---:|---|
| Ising | $1/2$ | $\epsilon$ |
| Tricritical Ising | $7/10$ | $\epsilon,\epsilon'$ |

This is why the word “tricritical” has operational content: more relevant directions must be controlled.

## Fusion data

The minimal-model fusion rule is

$$
(r,s)\times(r',s')
=\sum_{r''}\sum_{s''}(r'',s''),
$$

where

$$
r''=|r-r'|+1,\ |r-r'|+3,\ldots,
\min(r+r'-1,2p-r-r'-1),
$$

and similarly

$$
s''=|s-s'|+1,\ |s-s'|+3,\ldots,
\min(s+s'-1,2p'-s-s'-1).
$$

After field identification, selected tricritical Ising fusion rules are

$$
\epsilon\times\epsilon=\mathbf 1+\epsilon',
$$

$$
\epsilon\times\epsilon'=\epsilon+\epsilon'',
\qquad
\epsilon\times\epsilon''=\epsilon',
$$

$$
\epsilon'\times\epsilon'=\mathbf 1+\epsilon',
\qquad
\epsilon'\times\epsilon''=\epsilon,
\qquad
\epsilon''\times\epsilon''=\mathbf 1.
$$

For the spin fields,

$$
\sigma\times\sigma
=\mathbf 1+\epsilon+\epsilon'+\epsilon'',
$$

$$
\sigma\times\sigma'
=\epsilon+\epsilon',
$$

$$
\sigma'\times\sigma'
=\mathbf 1+\epsilon''.
$$

The even fields act on the spin fields as

$$
\epsilon\times\sigma=\sigma+\sigma',
\qquad
\epsilon'\times\sigma=\sigma+\sigma',
\qquad
\epsilon''\times\sigma=\sigma,
$$

and

$$
\epsilon\times\sigma'=\sigma,
\qquad
\epsilon'\times\sigma'=\sigma,
\qquad
\epsilon''\times\sigma'=\sigma'.
$$

These rules are a compact way of seeing the richer operator algebra relative to the Ising CFT.

## Relevant directions and exponents

In two dimensions, a scalar perturbation is relevant when

$$
\Delta<2.
$$

Thus the relevant scalar primaries of the tricritical Ising CFT are

$$
\sigma,\quad \sigma',\quad \epsilon,\quad \epsilon'.
$$

The even relevant operators are $\epsilon$ and $\epsilon'$. The odd relevant operators are $\sigma$ and $\sigma'$. The field $\epsilon''$ has $\Delta=3$ and is irrelevant.

The leading thermal exponent associated with $\epsilon$ is

$$
y_t=2-\Delta_\epsilon=2-\frac15=\frac95,
$$

so

$$
\nu=\frac{1}{y_t}=\frac59.
$$

The leading magnetic RG eigenvalue is

$$
y_h=2-\Delta_\sigma
=2-\frac{3}{40}=\frac{77}{40}.
$$

The spin two-point function at tricriticality scales as

$$
\langle \sigma(x)\sigma(0)\rangle
\sim
\frac{1}{|x|^{2\Delta_\sigma}}
=\frac{1}{|x|^{3/20}}.
$$

The subleading even direction $\epsilon'$ has

$$
y_{\epsilon'}=2-\frac65=\frac45.
$$

This extra relevant even direction is the CFT signature of tricritical tuning.

## Supersymmetry preview

The tricritical Ising model is also the first nontrivial unitary minimal model with an $\mathcal N=1$ superconformal interpretation. In that description, the same theory is reorganized by the super-Virasoro algebra rather than only the Virasoro algebra.

This does not mean that every lattice realization visibly has microscopic supersymmetry. The statement is about the infrared fixed point: the long-distance CFT has an enhanced chiral algebra that can be described using supersymmetry.

A useful way to remember the structure is that the stress tensor sits with a spin-$3/2$ supercurrent in the supersymmetric organization. The Virasoro minimal-model data above remain correct, but the representation theory can be repackaged into superconformal multiplets.

Later supersymmetric-CFT pages will treat this carefully. Here the important lesson is modest:

$$
\text{tricritical Ising}
\quad\text{is a Virasoro minimal model and also a basic supersymmetric CFT example.}
$$

## Relation to Landau-Ginzburg intuition

The tricritical Ising point is often motivated by a $ℤ_2$-symmetric Landau-Ginzburg potential with a tuned quartic term, schematically

$$
V(\phi)=r\phi^2+u\phi^4+v\phi^6+\cdots .
$$

At an ordinary Ising critical point, one tunes the mass-like parameter $r$. At a tricritical point, one tunes both $r$ and $u$.

This picture is useful, but the CFT is not the classical potential. The exact fixed point is the minimal model $\mathcal M(4,5)$, and the precise operator dimensions and fusion rules are those of the CFT. Landau-Ginzburg language is a guide to relevant directions and symmetry, not a substitute for the exact conformal data.

## Correlators and blocks

The general scalar three-point function is fixed by conformal symmetry:

$$
\langle \mathcal O_i(z_1,\bar z_1)\mathcal O_j(z_2,\bar z_2)\mathcal O_k(z_3,\bar z_3)\rangle
=\frac{C_{ijk}}{|z_{12}|^{\Delta_i+\Delta_j-\Delta_k}
|z_{23}|^{\Delta_j+\Delta_k-\Delta_i}
|z_{13}|^{\Delta_i+\Delta_k-\Delta_j}}.
$$

The dynamical data are the OPE coefficients $C_{ijk}$ allowed by fusion and $ℤ_2$ parity. For example, $\langle \sigma\sigma\epsilon\rangle$ and $\langle \sigma\sigma\epsilon'\rangle$ can be nonzero, while any correlator with an odd number of $ℤ_2$-odd fields vanishes.

Four-point functions decompose into finitely many Virasoro conformal blocks in each channel. For instance, the $\sigma\times\sigma$ channel contains

$$
\mathbf 1,\quad \epsilon,\quad \epsilon',\quad \epsilon''.
$$

Thus a four-spin correlator is more complicated than in the Ising CFT, where only $\mathbf 1$ and $\epsilon$ appear. The same logic applies: null states imply differential equations for some correlators, fusion tells which blocks can appear, and crossing fixes strong constraints on the allowed combinations.

## Common pitfalls

**Do not confuse tricritical Ising with ordinary Ising.** The central charge, operator dimensions, fusion rules, relevant directions, and physical interpretation are different.

**Do not call every $c=7/10$ appearance “the same microscopic model.”** The CFT describes a universality class. Different lattice models can flow to it.

**Do not forget the second relevant even scalar.** The existence of both $\epsilon$ and $\epsilon'$ is the central tricritical feature.

**Do not identify the Landau-Ginzburg field with a single primary without care.** The continuum order parameter is represented by the leading odd field $\sigma$, but microscopic fields expand into a sum of CFT operators with nonuniversal coefficients.

**Do not treat the supersymmetry preview as a microscopic assumption.** The supersymmetry is an infrared organizational structure of the fixed point.

**Do not use fusion rules as if they were numerical OPE coefficients.** Fusion gives allowed families. OPE coefficients require a normalization convention and additional data.

## Relations to other pages

This page follows [Ising CFT](/cft-bootstrap/minimal-models-rational-cft/ising-cft/) as the next unitary minimal-model example. It uses the construction introduced in [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) and prepares the more systematic pages [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), and [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/).

The null-state and differential-equation machinery belongs to [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) and [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/). The supersymmetry interpretation connects later to Supersymmetric CFT.

## Research status

The tricritical Ising minimal model is exactly solved as a rational CFT. Its central charge, primary spectrum, fusion rules, characters, modular invariant, and many correlators are established.

Active work uses the model as a benchmark and building block: supersymmetric lattice realizations, boundary RG flows, integrable massive deformations, conformal interfaces, entanglement diagnostics, topological and categorical descriptions, and comparisons with numerical conformal bootstrap methods.

## Exercises

### Exercise 1

Compute the central charge of $\mathcal M(4,5)$ using

$$
c=1-\frac{6}{m(m+1)}
$$

with $m=4$.

<details><summary><strong>Solution</strong></summary>

Substituting $m=4$ gives

$$
c=1-\frac{6}{4\cdot5}
=1-\frac{3}{10}
=\frac{7}{10}.
$$

</details>

### Exercise 2

Use

$$
h_{r,s}=\frac{(5r-4s)^2-1}{80}
$$

to compute $h_{1,2}$, $h_{1,3}$, and $h_{2,2}$.

<details><summary><strong>Solution</strong></summary>

For $(1,2)$,

$$
h_{1,2}=\frac{(5-8)^2-1}{80}
=\frac{9-1}{80}=\frac{1}{10}.
$$

For $(1,3)$,

$$
h_{1,3}=\frac{(5-12)^2-1}{80}
=\frac{49-1}{80}=\frac35.
$$

For $(2,2)$,

$$
h_{2,2}=\frac{(10-8)^2-1}{80}
=\frac{4-1}{80}=\frac{3}{80}.
$$

The corresponding diagonal dimensions are $1/5$, $6/5$, and $3/40$.

</details>

### Exercise 3

Use the fusion rule formula to show that

$$
\sigma\times\sigma=\mathbf 1+\epsilon+\epsilon'+\epsilon''.
$$

<details><summary><strong>Solution</strong></summary>

The spin field is $\sigma=(2,2)$. Fuse $(2,2)$ with itself in $\mathcal M(4,5)$.

For the $r$ labels,

$$
r''=|2-2|+1,\ |2-2|+3,\ldots,
\min(2+2-1,2\cdot4-2-2-1),
$$

so

$$
r''=1,3.
$$

For the $s$ labels,

$$
s''=1,3.
$$

Thus the product contains

$$
(1,1),\quad (1,3),\quad (3,1),\quad (3,3).
$$

Using field identification,

$$
(3,1)\sim(1,4)=\epsilon'',
\qquad
(3,3)\sim(1,2)=\epsilon.
$$

Therefore

$$
\sigma\times\sigma=\mathbf 1+\epsilon+\epsilon'+\epsilon''.
$$

</details>

### Exercise 4

Which scalar primaries of the tricritical Ising CFT are relevant in two dimensions?

<details><summary><strong>Solution</strong></summary>

A scalar perturbation is relevant in two dimensions when $\Delta<2$. The dimensions are

$$
\Delta_\sigma=\frac{3}{40},
\quad
\Delta_{\sigma'}=\frac78,
\quad
\Delta_\epsilon=\frac15,
\quad
\Delta_{\epsilon'}=\frac65,
\quad
\Delta_{\epsilon''}=3.
$$

Thus

$$
\sigma,\quad \sigma',\quad \epsilon,\quad \epsilon'
$$

are relevant, while $\epsilon''$ is irrelevant.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, "Infinite conformal symmetry in two-dimensional quantum field theory," *Nuclear Physics B* **241** (1984).
- D. Friedan, Z. Qiu, and S. Shenker, "Conformal invariance, unitarity, and critical exponents in two dimensions," *Physical Review Letters* **52** (1984).
- A. B. Zamolodchikov, "Conformal symmetry and multicritical points in two-dimensional quantum field theory," *Soviet Journal of Nuclear Physics* **44** (1986).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, "Applied Conformal Field Theory," Les Houches lectures, 1988.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.

## Version history

- 2026-06-28: First polished draft. Added tricritical Ising minimal-model data, Kac table, operator dictionary, selected fusion rules, relevant deformations, supersymmetry preview, exercises, and references.
