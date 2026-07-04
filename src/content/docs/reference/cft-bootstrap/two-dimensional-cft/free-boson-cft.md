---
title: "Free Boson CFT"
description: "Defines the two-dimensional free boson conformal field theory, including its current, stress tensor, central charge, vertex operators, and compactification preview."
sidebar:
  label: "Free Boson CFT"
  order: 8
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Ginsparg 1988; Polchinski 1998"
topics:
  - two-dimensional CFT
  - free boson
  - vertex operators
  - current algebra
  - compact boson
canonicalTopics:
  - free-boson-conformal-field-theory
  - gaussian-model-in-two-dimensional-cft
  - vertex-operators-and-charge-neutrality
  - u1-current-algebra-and-central-charge
researchStatus:
  established:
    - "The free boson is the canonical exactly solvable two-dimensional CFT with central charge one, current algebra, logarithmic scalar propagator, and vertex-operator spectrum."
  active:
    - "Compactification, orbifolds, boundaries, defects, lattice vertex algebras, and noncompact target-space subtleties are standard refinements developed on later pages."
---

## Summary

The free boson CFT is the two-dimensional conformal field theory of a massless scalar field $X(z,\bar z)$. In the normalization used here,

$$
S={1\over 4\pi}\int d^2z\,\partial X\,\bar\partial X,
\qquad
X(z,\bar z)X(0)\sim -\log |z|^2.
$$

The equation of motion is

$$
\partial\bar\partial X=0,
$$

so locally

$$
X(z,\bar z)=X_L(z)+X_R(\bar z).
$$

The field $X$ itself has a logarithmic two-point function, so it is not an ordinary primary with a power-law two-point function. The clean local conformal operators are its derivatives and its normal-ordered exponentials. The holomorphic current

$$
J(z)=i\partial X_L(z)
$$

has OPE

$$
J(z)J(w)\sim {1\over (z-w)^2},
$$

and the stress tensor is

$$
T(z)={1\over 2}:J(z)J(z):=-{1\over 2}:\partial X_L\partial X_L:(z).
$$

The chiral central charge is $c=1$. A nonchiral diagonal free boson is usually called a $c=1$ CFT, meaning $c=\bar c=1$.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

It is also useful to know [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) and [Current OPE](/cft-bootstrap/operator-product-expansion/current-ope/), because the free boson is the cleanest example of a conserved $U(1)$ current algebra.

## Core idea

The free boson is simple in the way a harmonic oscillator is simple: it is exactly solvable, but it already contains much of the architecture of two-dimensional CFT. It has a Gaussian action, chiral currents, a Virasoro stress tensor, vertex operators, charge-neutrality constraints, and a nontrivial compactified family.

<figure class="doc-figure" style="--figure-width: 50rem;">

![The free boson produces chiral currents, the stress tensor, vertex operators, and compactification data.](/figures/cft-bootstrap/free-boson-data-flow.svg)

<figcaption>

The Gaussian field $X$ has logarithmic correlations. Its derivatives are local chiral currents, the current squares give the stress tensor with $c=1$, and exponentials of $X$ give vertex operators. Compactifying $X$ discretizes the zero-mode data into momentum and winding sectors.

</figcaption>
</figure>

The practical slogan is

$$
\text{free boson}
\quad\Longrightarrow\quad
U(1)\text{ current algebra }+\text{ vertex operators}.
$$

That slogan hides the main subtlety: the local OPEs are fixed by the logarithm, but the full theory also needs global data such as zero modes, compactification radius, winding sectors, and locality of the allowed vertex lattice.

## Setup and conventions

We work in Euclidean complex coordinates with

$$
\partial={1\over 2}(\partial_1-i\partial_2),
\qquad
\bar\partial={1\over 2}(\partial_1+i\partial_2).
$$

The normalization is chosen so that

$$
X_L(z)X_L(w)\sim -\log(z-w),
\qquad
X_R(\bar z)X_R(\bar w)\sim -\log(\bar z-\bar w),
$$

with no singular OPE between $X_L$ and $X_R$. Therefore

$$
\partial X_L(z)\partial X_L(w)\sim -{1\over (z-w)^2}.
$$

With

$$
J(z)=i\partial X_L(z),
$$

the current OPE becomes

$$
J(z)J(w)\sim {1\over (z-w)^2}.
$$

This is the level-one abelian current normalization used below. Other books absorb factors of $2$, $\pi$, $\alpha'$, or the radius into $X$. Always compare the logarithm in $XX$ before comparing vertex dimensions.

## Theory data

| Object | Formula | Meaning |
|---|---|---|
| Action | $S={1\over 4\pi}\int d^2z\,\partial X\bar\partial X$ | Gaussian fixed point. |
| Equation of motion | $\partial\bar\partial X=0$ | Local chiral splitting. |
| Scalar OPE | $X(z,\bar z)X(0)\sim -\log |z|^2$ | Logarithmic field, not an ordinary primary. |
| Current | $J=i\partial X_L$ | Holomorphic $U(1)$ current. |
| Stress tensor | $T={1\over 2}:JJ:$ | Sugawara form for $U(1)$ level one. |
| Central charge | $c=1$ | One real chiral bosonic degree of freedom. |
| Chiral vertex | $V_\alpha(z)=:e^{i\alpha X_L(z)}:$ | Primary of weight $h=\alpha^2/2$. |
| Full vertex | $V_{p_L,p_R}=:e^{ip_LX_L+ip_RX_R}:$ | Primary of weights $(p_L^2/2,p_R^2/2)$. |

The noncompact theory has continuous momentum labels. The compactified theory replaces those labels by a lattice of allowed left- and right-moving momenta.

## Current, stress tensor, and central charge

The current OPE follows by differentiating the logarithm:

$$
\partial X_L(z)\partial X_L(w)\sim -{1\over (z-w)^2},
\qquad
J(z)J(w)\sim {1\over (z-w)^2}.
$$

The stress tensor is

$$
T(z)={1\over 2}:J(z)J(z):.
$$

Using Wick contractions,

$$
T(z)J(w)
\sim
{J(w)\over (z-w)^2}+{\partial J(w)\over z-w}.
$$

Thus $J$ is a holomorphic primary of weight $1$. The stress-tensor OPE is

$$
T(z)T(w)
\sim
{1/2\over (z-w)^4}
+{2T(w)\over (z-w)^2}
+{\partial T(w)\over z-w},
$$

so the Virasoro central charge is $c=1$.

The same construction in the antiholomorphic sector gives $\bar J=i\bar\partial X_R$ and $\bar c=1$.

## Vertex operators

The free boson has exponential primary fields. For a chiral vertex operator

$$
V_\alpha(z)=:e^{i\alpha X_L(z)}:,
$$

Wick contraction gives

$$
V_\alpha(z)V_\beta(w)
\sim
(z-w)^{\alpha\beta}:e^{i\alpha X_L(z)+i\beta X_L(w)}:.
$$

The stress tensor OPE is

$$
T(z)V_\alpha(w)
\sim
{\alpha^2/2\over (z-w)^2}V_\alpha(w)
+{\partial V_\alpha(w)\over z-w}.
$$

Therefore

$$
h_\alpha={\alpha^2\over 2}.
$$

For a full vertex operator

$$
V_{p_L,p_R}(z,\bar z)=:e^{ip_LX_L(z)+ip_RX_R(\bar z)}:,
$$

one has

$$
(h,\bar h)=\left({p_L^2\over 2},{p_R^2\over 2}\right),
\qquad
\Delta={p_L^2+p_R^2\over 2},
\qquad
s={p_L^2-p_R^2\over 2}.
$$

The OPE of two such vertices is

$$
V_{p_L,p_R}(z,\bar z)V_{q_L,q_R}(0)
\sim
z^{p_Lq_L}\bar z^{p_Rq_R}
V_{p_L+q_L,p_R+q_R}(0)+\cdots.
$$

This formula is one of the first places where locality constrains allowed charges. If the powers of $z$ and $\bar z$ produce nontrivial monodromy under $z\mapsto e^{2\pi i}z$, then the chosen set of vertex operators is not a mutually local bosonic operator algebra.

## Zero modes and charge neutrality

The free boson action has a shift symmetry

$$
X\mapsto X+a.
$$

For the noncompact theory, the path integral includes integration over the constant zero mode. A correlator of full vertices is nonzero only when the total charge vanishes:

$$
\left\langle \prod_{i=1}^n :e^{ik_iX(z_i,\bar z_i)}: \right\rangle\ne0
\quad\Longrightarrow\quad
\sum_i k_i=0.
$$

For charge-neutral nonchiral vertices in the noncompact theory,

$$
\left\langle \prod_{i=1}^n :e^{ik_iX(z_i,\bar z_i)}: \right\rangle
=
\prod_{i<j}|z_i-z_j|^{2k_ik_j},
\qquad
\sum_i k_i=0,
$$

up to the normalization of the zero-mode volume. If $\sum_i k_i\ne0$, the zero-mode integral kills the correlator.

## Compactification preview

The same local action supports an important one-parameter family of full CFTs. If

$$
X\sim X+2\pi R,
$$

then the scalar is compact. Momentum is quantized, winding sectors are allowed, and the left-right momenta lie on a lattice. In a common convention compatible with the normalization above, one writes schematically

$$
p_L={n\over R}+wR,
\qquad
p_R={n\over R}-wR,
\qquad
n,w\in\mathbb Z,
$$

with

$$
h={p_L^2\over 2},
\qquad
\bar h={p_R^2\over 2}.
$$

The precise radius convention is famously easy to shift by factors of $\sqrt2$ or $\alpha'$. The invariant content is simpler than the notation: compactification turns the continuum of zero-mode momenta into a momentum–winding lattice, and T-duality identifies equivalent radii after the appropriate convention translation.

## Checks

| Check | Result |
|---|---|
| Current OPE | $J(z)J(w)\sim 1/(z-w)^2$ |
| Current weight | $T(z)J(w)\sim J/(z-w)^2+\partial J/(z-w)$ |
| Central charge | The fourth-order pole in $T(z)T(w)$ is $1/(2(z-w)^4)$, hence $c=1$. |
| Vertex weight | $V_\alpha$ has $h=\alpha^2/2$. |
| Charge conservation | Vertex correlators vanish unless total zero-mode charge is conserved. |

The fastest diagnostic for convention mismatch is the chiral vertex two-point function. In these conventions,

$$
\langle V_\alpha(z)V_{-\alpha}(0)\rangle={1\over z^{\alpha^2}},
$$

which means $2h=\alpha^2$.

## Common pitfalls

**Treating $X$ as an ordinary primary.** The field $X$ has a logarithmic two-point function, not a power-law two-point function. The derivatives $\partial X$, $\bar\partial X$ and the normal-ordered exponentials are the clean conformal operators.

**Forgetting the zero mode.** Wick contractions of exponentials produce the distance factors, but the constant mode imposes charge neutrality. A formula for vertex correlators without the neutrality condition is missing part of the path integral.

**Comparing radii without comparing normalizations.** The compact-boson radius depends on how the action, propagator, and target-space periodicity are normalized. Before comparing $R$, compare the OPE $XX\sim -\log|z|^2$ and the dimension formula for $e^{ikX}$.

**Confusing chiral and full locality.** A chiral vertex can have branch cuts with another chiral vertex. A full local operator must have compatible left and right monodromies so that taking one insertion around another gives an allowed statistics phase.

**Thinking free means small.** The free boson has infinitely many vertex operators and, in the noncompact theory, a continuous spectrum. It is exactly solvable, not finite.

## Relations to other pages

- [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) supplies the contour/OPE technology used to read off current and Virasoro algebras.
- [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) explains why the $TT$ OPE coefficient is the central charge.
- [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) gives the left-right language used for $X_L$ and $X_R$.
- [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) gives the parallel fermionic Gaussian model and its Ising connection.
- [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/) develops momentum, winding, radius, modular invariance, and T-duality.
- [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) generalizes the abelian current algebra to nonabelian affine symmetry.

## Research status

The local free boson, its $c=1$ stress tensor, its $U(1)$ current algebra, and its vertex-operator OPEs are textbook-standard. The delicate parts are global rather than local: zero modes, target-space compactification, spin structures after fermionization, modular invariance, boundary conditions, defects, orbifolds, and noncompact spectra.

The compact boson remains a useful laboratory for modern themes because it contains T-duality, enhanced current algebra at special radii, rational versus irrational spectra, orbifold constructions, and bridges to vertex operator algebras.

## Exercises

### Exercise 1: Derive the current OPE

Starting from

$$
X_L(z)X_L(w)\sim -\log(z-w),
$$

show that $J=i\partial X_L$ satisfies

$$
J(z)J(w)\sim {1\over (z-w)^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the logarithm with respect to $z$ and $w$:

$$
\partial X_L(z)\partial X_L(w)\sim -{1\over (z-w)^2}.
$$

Multiplying by $i^2=-1$ gives

$$
J(z)J(w)=i\partial X_L(z)i\partial X_L(w)\sim {1\over (z-w)^2}.
$$

</details>

### Exercise 2: Check the vertex dimension

Use Wick contractions to show that the chiral vertex $V_\alpha=:e^{i\alpha X_L}:$ has conformal weight $h=\alpha^2/2$.

<details>
<summary><strong>Solution</strong></summary>

The stress tensor is $T=-{1\over2}:\partial X_L\partial X_L:$. Since

$$
\partial X_L(z)V_\alpha(w)\sim -{i\alpha\over z-w}V_\alpha(w),
$$

the double contraction gives

$$
-{1\over2}\left(-{i\alpha\over z-w}\right)^2V_\alpha(w)
={\alpha^2/2\over (z-w)^2}V_\alpha(w).
$$

The single contractions combine to $\partial V_\alpha/(z-w)$, so $h=\alpha^2/2$.

</details>

### Exercise 3: Explain charge neutrality

Why does a noncompact-boson correlator of vertices vanish unless $\sum_i k_i=0$?

<details>
<summary><strong>Solution</strong></summary>

Write $X=X_0+X'$ where $X_0$ is the constant zero mode. The action does not depend on $X_0$, while the product of vertices contains

$$
e^{iX_0\sum_i k_i}.
$$

The zero-mode integral is proportional to

$$
\int_{-\infty}^{\infty}dX_0\,e^{iX_0\sum_i k_i},
$$

which gives a delta function enforcing $\sum_i k_i=0$.

</details>

### Exercise 4: Read the central charge

Assume $T={1\over2}:JJ:$ and $J(z)J(w)\sim 1/(z-w)^2$. Show that the fourth-order pole in $T(z)T(w)$ is $1/(2(z-w)^4)$.

<details>
<summary><strong>Solution</strong></summary>

The fourth-order pole comes from contracting both currents in the first $T$ with both currents in the second $T$. There are two pairings. The coefficient is

$$
{1\over2}\cdot {1\over2}\cdot 2\cdot {1\over (z-w)^4}
={1\over 2(z-w)^4}.
$$

Since the Virasoro OPE has $c/2$ multiplying $(z-w)^{-4}$, this gives $c=1$.

</details>

## References

### Standard first pass

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters on free fields, operator formalism, compact bosons, and modular invariance.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, for a concise free-boson and compactification introduction.
- J. Polchinski, *String Theory*, Volume 1, for the worldsheet free boson, vertex operators, and compactification conventions.

### Deeper references

- P. Goddard and D. Olive, *Kac–Moody and Virasoro Algebras in Relation to Quantum Physics*, for the current-algebra viewpoint.
- G. Moore and N. Seiberg, papers on rational conformal field theory, for the role of compact bosons in the broader RCFT landscape.

## Version history

- **2026-06-28:** Initial polished draft for the Two-Dimensional CFT chapter.
