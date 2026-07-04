---
title: "Compact Boson"
description: "Momentum, winding, radius dependence, T-duality, and enhanced symmetry in the compact free-boson CFT."
sidebar:
  label: "Compact Boson"
  order: 10
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Sénéchal 1997; Ginsparg 1988; Polchinski 1998"
topics:
  - two-dimensional CFT
  - compact boson
  - vertex operators
  - momentum and winding
  - T-duality
  - current algebra
canonicalTopics:
  - compact-boson-cft
  - c-equals-one-cfts
  - t-duality
researchStatus:
  established:
    - "The compact boson is the canonical one-parameter family of unitary two-dimensional CFTs with central charge one."
    - "Its local spectrum is organized by momentum and winding quantum numbers, with a T-duality identifying equivalent radius conventions."
  active:
    - "The compact boson is also a gateway to modern questions about duality, generalized symmetries, boundary CFT, orbifolds, and rational points of the c = 1 moduli space."
---

## Summary

The compact boson is the free scalar CFT in which the field is angular rather than real-valued:

$$
X\sim X+2\pi R.
$$

This single identification changes the theory dramatically. The noncompact boson has continuous momentum. The compact boson has quantized momentum and winding sectors:

$$
X(\sigma+2\pi,\tau)=X(\sigma,\tau)+2\pi mR,
\qquad n,m\in\mathbb Z.
$$

In the conventions of this page, the left- and right-moving momenta are

$$
p_L=\frac nR+\frac{mR}{2},
\qquad
p_R=\frac nR-\frac{mR}{2},
$$

and the primary vertex operator

$$
V_{n,m}(z,\bar z)=:\!\exp\big(i p_L X_L(z)+i p_R X_R(\bar z)\big)\!:
$$

has conformal weights

$$
h_{n,m}=\frac{p_L^2}{2},
\qquad
\bar h_{n,m}=\frac{p_R^2}{2}.
$$

The radius $R$ is an exactly marginal parameter, but it is not a naive coordinate on the space of theories. The spectra at $R$ and $2/R$ are equivalent after exchanging momentum and winding. This is the simplest CFT form of **T-duality**.

<figure class="doc-figure" style="--figure-width: 36rem;">

![Momentum and winding lattice of the compact boson.](/figures/cft-bootstrap/compact-boson-momentum-winding.svg)

<figcaption>

The compact boson spectrum is a lattice in the $(p_L,p_R)$ plane. Momentum shifts move along the diagonal direction, winding shifts move along the anti-diagonal direction, and T-duality exchanges the two primitive directions.

</figcaption>
</figure>

## Prerequisites

You should know the free boson page, especially the OPE

$$
X_L(z)X_L(w)\sim -\log(z-w),
\qquad
X_R(\bar z)X_R(\bar w)\sim -\log(\bar z-\bar w),
$$

the stress tensor

$$
T(z)=-\frac12:\!\partial X_L\partial X_L\!:
$$

and the vertex-operator rule $:\!e^{i\alpha X_L}\!:$ has holomorphic weight $\alpha^2/2$. It is also useful to know the [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/) and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

## Core idea

The noncompact free boson is too large for many two-dimensional applications: it has a continuous spectrum of vertex operators $e^{ipX}$. Compactification replaces the target line by a circle, forcing the spectrum to be discrete.

The circle target has two kinds of quantum number.

| Quantum number | Physical meaning | Where it appears |
|---|---|---|
| $n$ | momentum around the target circle | $p=n/R$ |
| $m$ | winding of the field around the target circle | $X(\sigma+2\pi)-X(\sigma)=2\pi mR$ |

The surprise is that a local operator sees both at once. The compact boson is not just a free particle on a circle. In two-dimensional CFT, the field splits into chiral pieces,

$$
X(z,\bar z)=X_L(z)+X_R(\bar z),
$$

and momentum plus winding combine into different left- and right-moving momenta.

The radius $R$ controls the relative cost of momentum and winding:

$$
\text{large }R:
\quad \frac nR\text{ is cheap, }\frac{mR}{2}\text{ is costly},
$$

while

$$
\text{small }R:
\quad \frac nR\text{ is costly, }\frac{mR}{2}\text{ is cheap}.
$$

T-duality says these two descriptions are the same physics after the labels are exchanged.

## Setup and conventions

We use the free-boson normalization

$$
X_L(z)X_L(w)\sim -\log(z-w),
\qquad
X_R(\bar z)X_R(\bar w)\sim -\log(\bar z-\bar w),
$$

so that

$$
T(z)=-\frac12:\!\partial X_L\partial X_L\!:,
\qquad
\bar T(\bar z)=-\frac12:\!\bar\partial X_R\bar\partial X_R\!:,
\qquad
c=\bar c=1.
$$

The compactification is

$$
X\equiv X+2\pi R.
$$

A local operator must be compatible with this identification. A purely electric vertex $e^{ipX}$ is single-valued only if

$$
pR\in\mathbb Z,
\qquad
p=\frac nR,
\qquad n\in\mathbb Z.
$$

On the spatial circle of the cylinder, compactness also permits winding sectors,

$$
X(\sigma+2\pi,\tau)=X(\sigma,\tau)+2\pi mR,
\qquad m\in\mathbb Z.
$$

:::note[Radius conventions]
Different CFT and string-theory sources absorb factors of $2$ or $\alpha'$ into the definition of $R$. In this page the self-dual radius is $R=\sqrt2$ because the duality is $R\leftrightarrow 2/R$. A source with self-dual radius $R=1$ is usually using a rescaled radius.
:::

## Momentum and winding

The compact boson has chiral zero modes. The allowed left- and right-moving momenta are

$$
p_L=\frac nR+\frac{mR}{2},
\qquad
p_R=\frac nR-\frac{mR}{2}.
$$

The corresponding primary is

$$
V_{n,m}(z,\bar z)=:\!\exp\big(i p_L X_L(z)+i p_R X_R(\bar z)\big)\!:.
$$

Its conformal weights are

$$
h_{n,m}=\frac12\left(\frac nR+\frac{mR}{2}\right)^2,
\qquad
\bar h_{n,m}=\frac12\left(\frac nR-\frac{mR}{2}\right)^2.
$$

The scaling dimension and spin are therefore

$$
\Delta_{n,m}=h_{n,m}+\bar h_{n,m}
=\frac{n^2}{R^2}+\frac{m^2R^2}{4},
$$

and

$$
s_{n,m}=h_{n,m}-\bar h_{n,m}=nm.
$$

The integer spin is not an accident. Locality of a bosonic CFT requires local operators to be mutually single-valued up to allowed statistics phases. Since $n,m\in\mathbb Z$, each $V_{n,m}$ has integral Lorentz spin. This is one of the quiet consistency checks that compactification got the spectrum right.

Descendants are obtained by acting with oscillator modes, or equivalently by multiplying by derivatives such as $\partial X$, $\bar\partial X$, $\partial^2X$, and normal-ordered products. A general descendant above $V_{n,m}$ has

$$
h=\frac{p_L^2}{2}+N,
\qquad
\bar h=\frac{p_R^2}{2}+\bar N,
\qquad
N,\bar N\in\mathbb Z_{\ge 0}.
$$

## The operator algebra

The vertex operators multiply by adding momentum and winding:

$$
V_{n,m}(z,\bar z)V_{n',m'}(0,0)
\sim
z^{p_Lp'_L}\bar z^{p_Rp'_R}V_{n+n',m+m'}(0,0)+\cdots.
$$

Equivalently, the charge lattice is additive:

$$
(n,m)+(n',m')=(n+n',m+m').
$$

The exponent controlling monodromy is

$$
p_Lp'_L-p_Rp'_R=nm'+mn'.
$$

This is an integer for all integer charges. The compact boson therefore packages locality into a lattice condition: the allowed charge lattice must be integral with respect to the left-right spin pairing.

A correlator of vertex primaries on the sphere vanishes unless both total momentum and total winding vanish:

$$
\sum_i n_i=0,
\qquad
\sum_i m_i=0.
$$

For purely electric operators this is the usual charge-neutrality rule. Winding neutrality is the analogous statement for vortex insertions.

## Torus partition function

The torus partition function is the oscillator contribution times the momentum-winding lattice sum:

$$
Z_R(\tau,\bar\tau)
=\frac{1}{|\eta(\tau)|^2}
\sum_{n,m\in\mathbb Z}
q^{p_L^2/2}\bar q^{p_R^2/2},
\qquad
q=e^{2\pi i\tau}.
$$

The factor $|\eta(\tau)|^{-2}$ comes from the left- and right-moving oscillator descendants. The lattice sum comes from the primaries $V_{n,m}$.

This formula is the fast way to remember the whole theory. It contains:

- the primary spectrum,
- the oscillator descendants,
- the radius dependence,
- modular consistency,
- and the T-duality identification.

The partition function is invariant under the modular transformations of the torus. The $T$ transformation checks spin integrality. The $S$ transformation exchanges the two cycles of the torus and, after Poisson resummation, mixes momentum and winding.

## T-duality

With the above convention,

$$
R\longleftrightarrow \frac{2}{R}
$$

is a duality. Under

$$
R'=\frac{2}{R},
\qquad
n'=m,
\qquad
m'=n,
$$

one finds

$$
p'_L=p_L,
\qquad
p'_R=-p_R.
$$

The sign flip of $p_R$ is harmless: it is implemented by $X_R\mapsto -X_R$ and leaves the full spectrum and partition function unchanged. Thus the compact-boson moduli space is not the half-line $R>0$ but the half-line modulo the reflection $R\sim 2/R$.

The self-dual radius is

$$
R=\sqrt2.
$$

At this point, the theory has extra chiral currents. In the holomorphic sector, the operators

$$
J^3(z)=\frac{i}{\sqrt2}\partial X_L(z),
\qquad
J^\pm(z)=:\!e^{\pm i\sqrt2 X_L(z)}\!:
$$

have weight one and generate an affine $SU(2)_1$ current algebra. The antiholomorphic sector has an independent copy. This enhanced symmetry is one reason the self-dual radius is a crossroads for bosonization, WZW models, orbifolds, and rational CFT.

## The radius as an exactly marginal deformation

The operator

$$
\partial X_L\bar\partial X_R
$$

has weights $(1,1)$. Perturbing by it changes the radius:

$$
S_R\longrightarrow S_R+\lambda\int d^2z\,\partial X_L\bar\partial X_R.
$$

In the compact boson this deformation is exactly marginal. Moving along the $c=1$ circle line changes dimensions continuously, for example

$$
\Delta_{1,0}=\frac{1}{R^2},
\qquad
\Delta_{0,1}=\frac{R^2}{4}.
$$

At generic radius the theory has infinitely many primaries and is not rational. At special rational radii, the charge lattice aligns with an extended chiral algebra, and the theory can become rational with finitely many primaries relative to that extended algebra.

## Physical interpretations

The compact boson appears in several languages.

| Language | Meaning of the compact boson |
|---|---|
| 2D CFT | A one-parameter family of $c=1$ theories. |
| Statistical physics | The continuum theory behind Gaussian models, height models, and the critical Ashkin–Teller line. |
| Condensed matter | The bosonized description of Luttinger liquids and gapless one-dimensional systems. |
| String worldsheet theory | A compact target-space coordinate with momentum and winding. |
| Current algebra | At special radii, an enhanced affine symmetry such as $SU(2)_1$. |

The same formulas are reused in all of these settings. What changes is the interpretation of $R$, the allowed operator set, and whether one studies the whole closed CFT, a boundary CFT, or a chiral edge theory.

## Common pitfalls

**The compact boson is not the noncompact boson with periodic notation.** Compactness changes the Hilbert space by quantizing momentum and adding winding sectors.

**The radius convention is not universal.** Always check whether the author uses $R\leftrightarrow 1/R$ or $R\leftrightarrow 2/R$. The physics is the same after rescaling $X$ and $R$.

**T-duality is not merely dimensional analysis.** It exchanges distinct quantum numbers: momentum and winding. The large-radius and small-radius descriptions are equivalent because the operator spectra match.

**Purely electric vertex operators do not exhaust the local operator spectrum.** Winding operators are essential in the compact theory. On the plane they look like vortex operators; on the cylinder they are states in winding sectors.

**The radius is not always a physical modulus after further projections.** Orbifolding, extending the chiral algebra, adding boundary conditions, or choosing a non-diagonal modular invariant can identify or restrict parts of the radius line.

## Relations to other pages

- [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/) gives the noncompact starting point.
- [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) explains the contour/OPE technology used for vertex operators.
- [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) explains the fermionic side of bosonization.
- [Orbifolds Preview](/cft-bootstrap/two-dimensional-cft/orbifolds-preview/) explains what happens when a finite symmetry, such as $X\mapsto -X$, is gauged.
- [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) will develop the enhanced symmetry at special radii.
- [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) will use torus partition functions as bootstrap constraints.

## Research status

The compact boson is a solved and foundational CFT. Its operator spectrum, OPE, partition function, boundary conditions, and dualities are standard.

What remains active is not the basic solution, but the way it reappears: as a testbed for generalized symmetries, dualities, topological defects, boundary flows, lattice realizations, and rational versus irrational CFT structure. It is the rare model that is both an exactly solved undergraduate-looking example and a surprisingly durable research playground. Tiny circle, enormous résumé.

## Exercises

### Exercise 1: Check the conformal weights

Using

$$
X_L(z)X_L(w)\sim -\log(z-w),
$$

show that

$$
V_{n,m}=:\!e^{i p_L X_L+i p_R X_R}\!:
$$

has weights $h=p_L^2/2$ and $\bar h=p_R^2/2$.

<details><summary><strong>Solution</strong></summary>

The holomorphic stress tensor is

$$
T(z)=-\frac12:\!\partial X_L\partial X_L\!:.
$$

The contraction is

$$
\partial X_L(z)e^{i p_LX_L(w)}\sim -\frac{i p_L}{z-w}e^{i p_LX_L(w)}.
$$

The double contraction with the two factors of $\partial X_L$ in $T$ gives

$$
T(z)e^{i p_LX_L(w)}\sim
\frac{p_L^2/2}{(z-w)^2}e^{i p_LX_L(w)}
+\frac{1}{z-w}\partial_w e^{i p_LX_L(w)}.
$$

Thus $h=p_L^2/2$. The antiholomorphic calculation gives $\bar h=p_R^2/2$.

</details>

### Exercise 2: Derive the spin

Show that

$$
h_{n,m}-\bar h_{n,m}=nm.
$$

<details><summary><strong>Solution</strong></summary>

Using

$$
p_L=\frac nR+\frac{mR}{2},
\qquad
p_R=\frac nR-\frac{mR}{2},
$$

we get

$$
h-\bar h=\frac12(p_L^2-p_R^2)
=\frac12(p_L-p_R)(p_L+p_R).
$$

But

$$
p_L-p_R=mR,
\qquad
p_L+p_R=\frac{2n}{R}.
$$

Therefore

$$
h-\bar h=\frac12(mR)\left(\frac{2n}{R}\right)=nm.
$$

</details>

### Exercise 3: Verify T-duality of the spectrum

Let $R'=2/R$, $n'=m$, and $m'=n$. Show that the dimensions are unchanged.

<details><summary><strong>Solution</strong></summary>

At the dual radius,

$$
p'_L=\frac{n'}{R'}+\frac{m'R'}{2}
=\frac{m}{2/R}+\frac{n(2/R)}{2}
=\frac{mR}{2}+\frac nR=p_L.
$$

Similarly,

$$
p'_R=\frac{m}{2/R}-\frac{n(2/R)}{2}
=\frac{mR}{2}-\frac nR=-p_R.
$$

Therefore

$$
(p'_L)^2=p_L^2,
\qquad
(p'_R)^2=p_R^2,
$$

so $h$ and $\bar h$ are unchanged. The right-moving momentum flips sign, but the spectrum is the same.

</details>

### Exercise 4: When is a cosine perturbation relevant?

For the purely electric operator

$$
\cos\left(\frac{nX}{R}\right)
=\frac12(V_{n,0}+V_{-n,0}),
$$

find its scaling dimension and determine when it is relevant.

<details><summary><strong>Solution</strong></summary>

For $m=0$,

$$
p_L=p_R=\frac nR.
$$

Thus

$$
\Delta_{n,0}=h+\bar h=\frac{n^2}{2R^2}+\frac{n^2}{2R^2}=\frac{n^2}{R^2}.
$$

A scalar perturbation in two dimensions is relevant when $\Delta<2$. Therefore

$$
\frac{n^2}{R^2}<2
\qquad\Longleftrightarrow\qquad
R>\frac{|n|}{\sqrt2}.
$$

The dual winding cosine has the dual relevance condition, as expected from T-duality.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the free boson, compactified boson, modular invariance, and $c=1$ material.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, for a compact introduction to the $c=1$ boson and radius line.
- J. Polchinski, *String Theory*, Vol. 1, for the string-worldsheet interpretation of momentum, winding, and T-duality.
- P. Goddard and D. Olive, *Kac–Moody and Virasoro Algebras in Relation to Quantum Physics*, for current algebra context.
- A. M. Tsvelik, *Quantum Field Theory in Condensed Matter Physics*, and E. Fradkin, *Field Theories of Condensed Matter Physics*, for condensed-matter uses of compact bosons and bosonization.

## Version history

- 2026-06-28: First polished draft. Fixes compact-boson normalization, momentum-winding spectrum, T-duality convention, enhanced-symmetry point, and exercises.
