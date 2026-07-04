---
title: "Ising CFT"
description: "The exact two-dimensional conformal field theory of the critical Ising model, including its primary fields, fusion algebra, spin and energy operators, and benchmark correlators."
sidebar:
  label: "Ising CFT"
  order: 2
level: Graduate
status: "Polished draft"
source: "Belavin, Polyakov, and Zamolodchikov 1984; Di Francesco, Mathieu, and Senechal; Cardy; standard minimal-model literature."
topics:
  - Ising CFT
  - minimal models
  - rational CFT
  - fusion rules
  - spin fields
  - free Majorana fermion
canonicalTopics:
  - ising-cft
  - minimal-model-m-3-4
  - rational-cft-data
researchStatus:
  established:
    - "The critical two-dimensional Ising model is exactly described by the unitary Virasoro minimal model M(3,4) with central charge c=1/2 and three scalar primary fields in the diagonal bosonic theory."
  active:
    - "Modern work uses the Ising CFT as a benchmark for conformal bootstrap, tensor-network, lattice, boundary, defect, and entanglement methods rather than as an unsettled theory."
---

## Summary

The **Ising CFT** is the conformal field theory of the two-dimensional critical Ising universality class. It is the unitary Virasoro minimal model

$$
\mathcal M(3,4),
\qquad
c=\frac12.
$$

In the diagonal bosonic theory there are three scalar Virasoro primary fields:

| Field | Kac label | Weights | Dimension | Spin | $ℤ_2$ parity |
|---|---:|---:|---:|---:|---:|
| $\mathbf 1$ | $(1,1)$ | $(0,0)$ | $0$ | $0$ | even |
| $\sigma$ | $(1,2)$ | $(1/16,1/16)$ | $1/8$ | $0$ | odd |
| $\epsilon$ | $(2,1)$ | $(1/2,1/2)$ | $1$ | $0$ | even |

The field $\sigma$ is the continuum spin operator. The field $\epsilon$ is the continuum energy-density operator. With unit-normalized two-point functions, the fusion rules are

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
\qquad
\sigma\times\epsilon=\sigma,
\qquad
\epsilon\times\epsilon=\mathbf 1.
$$

This page records the CFT data, operator dictionary, basic OPEs, free-fermion realization, and benchmark four-spin correlator. The Ising CFT is small enough to solve exactly but rich enough to teach almost every structural idea in two-dimensional CFT: minimal models, fusion, conformal blocks, modular invariance, locality, spin fields, and relevant deformations.

## Prerequisites

Read [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/), [Null States](/cft-bootstrap/virasoro-central-charge/null-states/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) first. It also helps to know [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) and the distinction between [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/).

The page uses the CFT normalization conventions of [Conventions and Notation](/cft-bootstrap/conventions/): scalar two-point functions are unit normalized unless stated otherwise, and diagonal two-dimensional fields have weights $(h,\bar h)$ with dimension $\Delta=h+\bar h$ and spin $J=h-\bar h$.

## Core idea

The Ising CFT is the smallest nontrivial unitary minimal model. Its smallness is not a lack of structure. It is exactly why it is useful.

The theory has a finite set of primary fields, so its OPE closes as a finite fusion algebra. But the Virasoro symmetry still generates infinitely many descendants, and four-point functions still decompose into nontrivial conformal blocks. The theory is therefore a perfect laboratory for the slogan

$$
\text{CFT data}
\quad\Longrightarrow\quad
\text{all local correlators}.
$$

The complete diagonal Ising CFT data are, schematically,

$$
\left\{c=\frac12;
\ \Delta_\sigma=\frac18,
\ \Delta_\epsilon=1;
\ C_{\sigma\sigma\epsilon}=\frac12;
\ \text{fusion rules}\right\}.
$$

Everything else is constrained by Virasoro symmetry, crossing, locality, and normalization choices.

## Setup and conventions

We work on the Euclidean complex plane with coordinates $z,\bar z$. A scalar primary $\mathcal O$ with weights $(h,h)$ has

$$
\langle \mathcal O(z,\bar z)\mathcal O(0)\rangle
=\frac{1}{|z|^{4h}}
=\frac{1}{|z|^{2\Delta}}.
$$

For the diagonal Ising primaries, this gives

$$
\langle \sigma(z,\bar z)\sigma(0)\rangle
=\frac{1}{|z|^{1/4}},
\qquad
\langle \epsilon(z,\bar z)\epsilon(0)\rangle
=\frac{1}{|z|^2}.
$$

The identity has the vacuum expectation value

$$
\langle \mathbf 1\rangle=1.
$$

The global spin-flip symmetry is a $ℤ_2$ symmetry. The spin field $\sigma$ is odd, while $\mathbf 1$ and $\epsilon$ are even. Correlation functions with an odd number of $\sigma$ insertions vanish.

## Minimal-model data

The unitary minimal series is often written as

$$
\mathcal M(m,m+1),
\qquad
c=1-\frac{6}{m(m+1)},
\qquad
m=3,4,5,\ldots .
$$

The Ising CFT is the $m=3$ member, so

$$
c=1-\frac{6}{3\cdot4}=\frac12.
$$

Equivalently, it is $\mathcal M(p,p')=\mathcal M(3,4)$ with Kac weights

$$
h_{r,s}
=\frac{(p'r-ps)^2-(p'-p)^2}{4pp'}
=\frac{(4r-3s)^2-1}{48}.
$$

The allowed Kac labels are

$$
r=1,2,
\qquad
s=1,2,3,
$$

with field identification

$$
(r,s)\sim(p-r,p'-s)=(3-r,4-s).
$$

This leaves three primaries:

| Representative | Weight | Common name |
|---:|---:|---|
| $(1,1)$ | $0$ | identity $\mathbf 1$ |
| $(1,2)$ | $1/16$ | spin field $\sigma$ |
| $(2,1)$ | $1/2$ | energy field $\epsilon$ |

The diagonal modular invariant pairs each chiral representation with its antiholomorphic copy:

$$
Z_{\rm Ising}(\tau,\bar\tau)
=|\chi_0(\tau)|^2
+|\chi_{1/2}(\tau)|^2
+|\chi_{1/16}(\tau)|^2.
$$

This is the local bosonic Ising CFT. The chiral Majorana fermion is a chiral building block; the full spin CFT has additional spin-structure subtleties discussed below.

## Operator dictionary

The lattice Ising model has spins $s_i=\pm1$ and nearest-neighbor energy density $s_i s_j$. At the critical point, the leading continuum operators are

| Lattice object | Continuum operator | Dimension | Meaning |
|---|---|---:|---|
| spin $s_i$ | $\sigma$ | $1/8$ | order parameter |
| local energy deviation | $\epsilon$ | $1$ | thermal perturbation |
| identity contribution | $\mathbf 1$ | $0$ | vacuum channel |

The continuum statement is not that the lattice spin is exactly $\sigma$ at finite lattice spacing. Rather, the long-distance expansion has the form

$$
s_i
\sim
A_\sigma a^{\Delta_\sigma}\sigma(x)
+\text{less relevant operators},
$$

where $a$ is the lattice spacing and $A_\sigma$ is nonuniversal. Similarly, the deviation from the critical temperature couples to $\epsilon$:

$$
S_{\rm CFT}
\longrightarrow
S_{\rm CFT}+t\int d^2x\,\epsilon(x)+\cdots .
$$

Here $t$ is a thermal scaling field, not literally the microscopic temperature itself. The magnetic field couples to $\sigma$:

$$
S_{\rm CFT}
\longrightarrow
S_{\rm CFT}+h\int d^2x\,\sigma(x)+\cdots .
$$

These two relevant deformations lead away from the critical fixed point.

## Fusion algebra

The Ising fusion rules are

$$
\mathbf 1\times \mathcal O=\mathcal O,
$$

$$
\sigma\times\sigma=\mathbf 1+\epsilon,
$$

$$
\sigma\times\epsilon=\sigma,
$$

$$
\epsilon\times\epsilon=\mathbf 1.
$$

The fusion algebra is not the same thing as an OPE with fixed coefficients. Fusion says which conformal families may appear. The OPE says how they appear, including coefficients and descendant contributions.

With the two-point normalization above, the leading scalar OPEs are

$$
\sigma(z,\bar z)\sigma(0)
\sim
\frac{1}{|z|^{1/4}}
\left(
\mathbf 1+\frac12 |z|\,\epsilon(0)+\cdots
\right),
$$

$$
\sigma(z,\bar z)\epsilon(0)
\sim
\frac{1}{2|z|}\,\sigma(0)+\cdots,
$$

and

$$
\epsilon(z,\bar z)\epsilon(0)
\sim
\frac{1}{|z|^2}\,\mathbf 1+\cdots .
$$

Thus

$$
C_{\sigma\sigma\epsilon}=C_{\sigma\epsilon\sigma}=\frac12,
\qquad
C_{\epsilon\epsilon\epsilon}=0.
$$

The vanishing of $C_{\epsilon\epsilon\epsilon}$ is not a generic minimal-model fact. It is a special consequence of the Ising fusion rule $\epsilon\times\epsilon=\mathbf 1$.

## Four-spin correlator

A useful benchmark is the four-spin function. Put the insertions at $\infty,1,z,0$ and define

$$
\langle \sigma(\infty)\sigma(1)\sigma(z,\bar z)\sigma(0)\rangle
=\mathcal G_{\sigma\sigma\sigma\sigma}(z,\bar z).
$$

The two Virasoro conformal blocks in the $\sigma\times\sigma$ channel are the identity block and the $\epsilon$ block:

$$
\mathcal F_{\mathbf 1}(z)
=\frac{1}{\sqrt 2}\,[z(1-z)]^{-1/8}
\sqrt{1+\sqrt{1-z}},
$$

$$
\mathcal F_\epsilon(z)
=\frac{1}{\sqrt 2}\,[z(1-z)]^{-1/8}
\sqrt{1-\sqrt{1-z}}.
$$

For the diagonal local theory,

$$
\mathcal G_{\sigma\sigma\sigma\sigma}(z,\bar z)
=|\mathcal F_{\mathbf 1}(z)|^2+|\mathcal F_\epsilon(z)|^2.
$$

As $z\to0$,

$$
\mathcal F_{\mathbf 1}(z)\sim z^{-1/8},
\qquad
\mathcal F_\epsilon(z)\sim \frac12 z^{3/8}.
$$

Therefore

$$
\mathcal G_{\sigma\sigma\sigma\sigma}(z,\bar z)
\sim
|z|^{-1/4}
\left(1+\frac14 |z|^2+\cdots\right),
$$

which agrees with $C_{\sigma\sigma\epsilon}=1/2$ after using the unit-normalized $\epsilon$ two-point function.

This is a wonderful check because it ties together fusion rules, null-vector differential equations, conformal blocks, OPE coefficients, and crossing symmetry in a single formula.

## Free Majorana realization

The Ising CFT also has a free Majorana fermion realization. The chiral fermion satisfies

$$
\psi(z)\psi(w)\sim\frac{1}{z-w},
$$

with stress tensor

$$
T(z)=-\frac12 :\psi\partial\psi:(z),
\qquad
c=\frac12.
$$

The full nonchiral energy operator is, up to convention-dependent phases,

$$
\epsilon(z,\bar z)\sim i\psi(z)\bar\psi(\bar z).
$$

The spin field $\sigma$ is not a polynomial in the fermion. It is a twist field for the fermion: taking $\psi$ around $\sigma$ changes the fermion boundary condition. This is why the Ising CFT is simultaneously elementary and subtle. The stress tensor and energy operator are simple in fermion variables, while the spin operator is nonlocal with respect to the fermion.

There is also a disorder field $\mu$ with the same weights as $\sigma$ in the nonchiral Ising model. Depending on whether one studies the bosonic spin theory, the fermionic theory, or a theory with explicit spin structure, the status of $\sigma$, $\mu$, and fermion lines must be stated carefully. On the plane in the diagonal bosonic Ising CFT, the three scalar primary families are $\mathbf 1$, $\sigma$, and $\epsilon$.

## Critical exponents

The Ising CFT dimensions reproduce the exact two-dimensional Ising critical exponents. The spin two-point function behaves as

$$
\langle \sigma(x)\sigma(0)\rangle\sim \frac{1}{|x|^{2\Delta_\sigma}}
=\frac{1}{|x|^{1/4}}.
$$

In statistical-mechanics notation, this gives

$$
\eta=2\Delta_\sigma=\frac14.
$$

The thermal deformation has dimension $\Delta_\epsilon=1$, so the RG eigenvalue of the temperature perturbation is

$$
y_t=2-\Delta_\epsilon=1,
$$

and therefore

$$
\nu=\frac1{y_t}=1.
$$

The magnetic RG eigenvalue is

$$
y_h=2-\Delta_\sigma=\frac{15}{8}.
$$

The point is not merely that CFT reproduces exponents. It explains why exponents are tied to operator dimensions at the fixed point.

## Modular and boundary previews

On a torus, the diagonal Ising partition function is

$$
Z_{\rm Ising}
=|\chi_0|^2+|\chi_{1/2}|^2+|\chi_{1/16}|^2.
$$

The three characters are closed under modular transformations. This is the rational-CFT reason the Ising model has finitely many primary families.

On a surface with boundary, the Ising CFT has famous conformal boundary conditions usually called fixed $+$, fixed $-$, and free. Boundary-condition-changing operators and boundary fusion rules are a major reason the Ising model remains a central example in boundary CFT. Those details belong in the Boundary, Defect, and Interface CFT volume path.

## Common pitfalls

**Do not confuse the chiral Majorana theory with the diagonal bosonic Ising CFT.** The chiral Majorana fermion has $c=1/2$ and is a chiral building block. The local diagonal Ising CFT pairs left and right sectors and has scalar primaries $\mathbf 1$, $\sigma$, and $\epsilon$.

**Do not treat fusion coefficients as OPE coefficients.** Fusion coefficients are nonnegative integers telling you which families can appear. OPE coefficients depend on normalization and contain dynamical information.

**Do not forget the spin-field twist nature.** The spin field $\sigma$ is not simply the fermion. It changes fermion boundary conditions.

**Do not identify lattice operators with continuum primaries without nonuniversal factors.** The continuum limit relates them by scaling expansions, not equality at finite lattice spacing.

**Do not assume all Ising-looking theories have the same operator content.** Fermionic versions, spin theories, disorder variables, and boundary conditions can change which operators are genuine local operators.

## Relations to other pages

This page is the first detailed model page in the Minimal Models and Rational CFT chapter. It relies on [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) for the Kac-table construction and on [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) for the representation theory.

The four-spin correlator is a concrete example of [Global versus Virasoro Blocks](/cft-bootstrap/conformal-blocks/global-versus-virasoro-blocks/) and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/). The free-fermion realization links back to [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/).

Later pages on [Kac Table](/cft-bootstrap/minimal-models-rational-cft/kac-table/), [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) generalize the structures seen here.

## Research status

The local operator content, correlators, fusion rules, modular invariant, boundary conditions, and free-fermion realization of the Ising CFT are established. The Ising CFT is now used as a calibration theory: if a proposed CFT method cannot reproduce the Ising data, something is probably wrong.

Active research uses the Ising CFT in less elementary settings: defects, interfaces, entanglement, tensor networks, fermionic spin structures, categorical symmetries, anyon constructions, and numerical-bootstrap benchmarks. These are not revisions of the basic Ising solution; they are new uses of a solved theory.

## Exercises

### Exercise 1

Use the minimal-model formula

$$
h_{r,s}=\frac{(4r-3s)^2-1}{48}
$$

for $\mathcal M(3,4)$ to compute the weights of $(1,1)$, $(1,2)$, and $(2,1)$.

<details><summary><strong>Solution</strong></summary>

For $(1,1)$,

$$
h_{1,1}=\frac{(4-3)^2-1}{48}=0.
$$

For $(1,2)$,

$$
h_{1,2}=\frac{(4-6)^2-1}{48}=\frac{3}{48}=\frac{1}{16}.
$$

For $(2,1)$,

$$
h_{2,1}=\frac{(8-3)^2-1}{48}=\frac{24}{48}=\frac12.
$$

Thus the diagonal fields have dimensions $0$, $1/8$, and $1$.

</details>

### Exercise 2

Using $\Delta_\sigma=1/8$ and $\Delta_\epsilon=1$, determine the leading powers in the OPE terms $\sigma\times\sigma\to\mathbf 1$ and $\sigma\times\sigma\to\epsilon$.

<details><summary><strong>Solution</strong></summary>

For scalar primaries, a term $\mathcal O_k$ in $\mathcal O_i(x)\mathcal O_j(0)$ has the leading power

$$
|x|^{\Delta_k-\Delta_i-\Delta_j}\mathcal O_k(0).
$$

For the identity channel,

$$
\Delta_{\mathbf 1}-2\Delta_\sigma
=0-\frac14=-\frac14,
$$

so the term is $|x|^{-1/4}\mathbf 1$.

For the $\epsilon$ channel,

$$
\Delta_\epsilon-2\Delta_\sigma
=1-\frac14=\frac34,
$$

so the term is proportional to $|x|^{3/4}\epsilon(0)$. Written by factoring out the identity singularity, this is

$$
|x|^{-1/4}\left(1+C_{\sigma\sigma\epsilon}|x|\epsilon(0)+\cdots\right).
$$

</details>

### Exercise 3

Explain why $\langle \sigma\sigma\epsilon\rangle$ can be nonzero but $\langle \sigma\epsilon\epsilon\rangle$ must vanish.

<details><summary><strong>Solution</strong></summary>

The Ising model has a spin-flip $ℤ_2$ symmetry. The spin field $\sigma$ is odd, while $\epsilon$ is even. A correlator with an odd number of $\sigma$ insertions is odd under the symmetry and must vanish.

The correlator $\langle \sigma\sigma\epsilon\rangle$ contains two odd fields, so it is even and can be nonzero. The correlator $\langle \sigma\epsilon\epsilon\rangle$ contains one odd field, so it is odd and must vanish.

</details>

## References

- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, "Infinite conformal symmetry in two-dimensional quantum field theory," *Nuclear Physics B* **241** (1984).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.
- P. Ginsparg, "Applied Conformal Field Theory," Les Houches lectures, 1988.
- J. L. Cardy, "Conformal Invariance and Statistical Mechanics," Les Houches lectures, 1988.

## Version history

- 2026-06-28: First polished draft. Added Ising minimal-model data, fusion rules, OPE normalizations, four-spin conformal blocks, free-Majorana realization, critical exponents, exercises, and references.
