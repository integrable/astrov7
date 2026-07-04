---
title: "BPS Bounds"
description: "Explains Bogomolny–Prasad–Sommerfield bounds, square-completion arguments, first-order soliton equations, and why BPS saturation is powerful but not automatic."
sidebar:
  label: "BPS Bounds"
  order: 8
level: Advanced
status: "Polished draft"
source: "Srednicki, sec. 92; Shifman, chs. 3 and 11; Coleman; Manton and Sutcliffe."
topics:
  - BPS bounds
  - Bogomolnyi equations
  - solitons
  - central charges
  - first-order equations
  - supersymmetric solitons
  - topological charges
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - bps-bounds
  - bogomolnyi-equations
  - supersymmetric-solitons
researchStatus:
  established:
    - "Bogomolnyi square completions and supersymmetric central-charge bounds are standard tools for identifying protected solitons and first-order soliton equations."
  active:
    - "BPS spectra, wall crossing, defect moduli spaces, BPS operator algebras, and strong-coupling realizations of BPS objects are active and theory-dependent."
---

## Summary

A **BPS bound** is a lower bound on the energy, mass, or tension of a soliton in terms of a charge measured at infinity. The basic form is

$$
E\ge |Z|,
$$

where $Z$ is a topological charge, magnetic charge, central charge, or boundary term. A configuration that reaches the bound is called **BPS**. In classical soliton language, BPS saturation usually means that the second-order Euler–Lagrange equations reduce to first-order equations.

The mechanism is simple and beautiful: rewrite the energy as a sum of nonnegative squares plus a boundary term,

$$
E
=
\int d^n x\,\sum_A \frac12\mathcal S_A^2
+Z.
$$

Then $E\ge Z$ for that orientation of the charge, and the invariant statement is usually $E\ge |Z|$. Saturation requires

$$
\mathcal S_A=0
\qquad\text{for all }A,
$$

which are the **Bogomolnyi equations**. These first-order equations are usually much easier than the full second-order field equations and often expose moduli, no-force conditions, and protected masses.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic flow from a static energy functional to square completion, a boundary charge, first-order BPS equations, and protected soliton data.](/figures/nonperturbative-qft/bps-bound-square-completion.svg)

<figcaption>

A BPS argument rewrites a static energy functional as positive squares plus a boundary or central-charge term. Saturation sets the squares to zero. The result is a first-order system whose solutions automatically solve the second-order equations under the stated assumptions.

</figcaption>
</figure>

The word “BPS” has two related uses. In nonsupersymmetric classical field theory it often means “a soliton saturating a Bogomolnyi bound.” In supersymmetric QFT it means more: a state or defect saturates a bound in the supersymmetry algebra and preserves some nonzero supercharges. The two meanings overlap for many supersymmetric solitons, but they are not identical.

## Prerequisites

You should know [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/).

You do not need supersymmetry for the first half of this page. The final sections use the supersymmetry algebra only schematically, as motivation for why BPS saturation is unusually rigid in quantum theory.

## Core idea

Most static solitons solve nonlinear second-order equations. A generic energy functional has the schematic form

$$
E[\Phi]
=
\int d^n x\,
\left[
\frac12(\nabla\Phi)^2+V(\Phi)+\cdots
\right].
$$

Solving the full equations directly is usually hard. But in special theories, or at special values of couplings, the energy can be reorganized as

$$
E[\Phi]
=
\int d^n x\,\sum_A \frac12\left(\mathcal F_A[\Phi]\right)^2
+Z[\Phi|_\infty].
$$

The first term is nonnegative. The second term depends only on boundary data or conserved charges. Therefore, inside a fixed topological sector,

$$
E[\Phi]\ge Z.
$$

If the charge can have either sign, choose the orientation that gives a positive boundary term and write

$$
E[\Phi]\ge |Z|.
$$

Saturation is possible only when every square vanishes:

$$
\mathcal F_A[\Phi]=0.
$$

These first-order equations are not a random trick. They say that the configuration takes the shortest possible route, in the energy geometry of the theory, between the boundary data forced by its charge.

This is the practical value of BPS bounds. They turn a variational lower bound into a differential equation and often turn a difficult nonlinear problem into a controlled moduli problem.

## Setup and conventions

We use the mostly-minus metric and write static energies with positive spatial-gradient terms. Exact numerical coefficients in a BPS bound are convention-dependent because authors normalize fields, covariant derivatives, gauge couplings, and topological charges differently.

The safe structure is

$$
\text{energy or tension}
=
\text{positive squares}
+
\text{boundary charge}.
$$

A **topological charge** is insensitive to smooth changes of the fields that preserve the boundary conditions. A **central charge** is a charge appearing on the right-hand side of a supersymmetry algebra. A **BPS equation** is a first-order equation whose solutions saturate the relevant bound.

| Symbol | Meaning |
|---|---|
| $E$ | Energy of a localized soliton |
| $T$ | Tension of an extended object, such as a wall or string |
| $Z$ | Boundary, topological, or central charge |
| $n$ | Integer winding, flux, or magnetic charge |
| $\mathcal M$ | Moduli space of BPS solutions |
| $\mathcal S_A$ | Square-completion expression set to zero by BPS equations |

When the soliton is extended, replace “energy” by energy per unit worldvolume. A vortex line has tension, and a domain wall has tension per unit area.

## The kink prototype

The cleanest example is a real scalar field in one spatial dimension. Suppose the potential can be written as

$$
V(\phi)=\frac12\left(\frac{dW}{d\phi}\right)^2.
$$

The static energy is

$$
E
=
\int dx\,
\left[
\frac12\left(\frac{d\phi}{dx}\right)^2
+
\frac12\left(\frac{dW}{d\phi}\right)^2
\right].
$$

Complete the square:

$$
E
=
\int dx\,
\frac12\left(\frac{d\phi}{dx}\mp\frac{dW}{d\phi}\right)^2
\pm
\int dx\,\frac{d\phi}{dx}\frac{dW}{d\phi}.
$$

The second term is a total derivative,

$$
\int dx\,\frac{d\phi}{dx}\frac{dW}{d\phi}
=
\int dx\,\frac{dW}{dx}
=
W(\phi(+\infty))-W(\phi(-\infty)).
$$

Therefore

$$
E\ge
\left|
W(\phi(+\infty))-W(\phi(-\infty))
\right|.
$$

The bound is saturated by

$$
\frac{d\phi}{dx}=\pm\frac{dW}{d\phi},
$$

with the sign chosen to match the direction of interpolation between vacua.

This example contains the whole plot. The soliton is forced by boundary data, the energy is bounded by a boundary term, and the optimal profile obeys a first-order gradient-flow equation.

## Vortices and the critical coupling

The Abelian Higgs vortex gives a codimension-two example. In the conventions of the [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/) page, the static tension at the Bogomolnyi point $\lambda=e^2$ can be written as

$$
T
=
\int d^2x
\left[
|D_1\phi\pm iD_2\phi|^2
+
\frac12\left(B\mp e(v^2-|\phi|^2)\right)^2
\right]
\pm e v^2\int d^2x\,B.
$$

Flux quantization gives

$$
e\int d^2x\,B=2\pi n,
$$

so

$$
T\ge 2\pi v^2|n|.
$$

The BPS vortex equations are

$$
(D_1\pm iD_2)\phi=0,
\qquad
B=\pm e(v^2-|\phi|^2).
$$

At this special coupling, vortices with the same sign of winding exert no static force on one another in the BPS approximation. That is not a purely topological statement. It follows from the equality of scalar and gauge-mediated forces at the critical coupling.

Away from the Bogomolnyi point, the topological charge still exists, but the square completion no longer gives first-order equations saturating the same linear bound. Multi-vortex forces appear.

## Monopoles and magnetic charge

The ’t Hooft–Polyakov monopole has a BPS limit in the Georgi–Glashow model. Let the adjoint scalar have asymptotic magnitude $v$ and gauge coupling $g$. In the limit where the scalar potential is removed while the boundary condition $|\phi|\to v$ is kept, the static energy is

$$
E
=
\int d^3x\,
\left[
\frac12 B_i^aB_i^a
+
\frac12(D_i\phi)^a(D_i\phi)^a
\right].
$$

Completing the square gives

$$
E
=
\frac12\int d^3x\,
\left(B_i^a\mp(D_i\phi)^a\right)^2
\pm
\int d^3x\,B_i^a(D_i\phi)^a.
$$

The cross-term becomes a surface integral at spatial infinity, and for magnetic charge $n$ gives

$$
E\ge \frac{4\pi v}{g}|n|.
$$

The first-order monopole equations are

$$
B_i^a=\pm(D_i\phi)^a.
$$

For $n=1$, the BPS monopole mass is

$$
M_{\rm BPS}=\frac{4\pi v}{g}.
$$

This formula is one reason monopoles are a favorite BPS example: the soliton mass is determined by asymptotic magnetic data rather than by the full detailed core profile.

## Domain walls and gradient flow

For a scalar domain wall depending on one coordinate $z$, suppose the potential is expressible as

$$
V(\phi)=\frac12G^{ab}(\phi)\partial_aW\partial_bW,
$$

where $G_{ab}$ is a positive target-space metric. The wall tension is

$$
T
=
\int dz\,
\left[
\frac12G_{ab}\frac{d\phi^a}{dz}\frac{d\phi^b}{dz}
+V(\phi)
\right].
$$

The square completion yields, for an orientation with $W_f>W_i$,

$$
T
=
\int dz\,
\frac12G_{ab}
\left(
\frac{d\phi^a}{dz}-G^{ac}\partial_cW
\right)
\left(
\frac{d\phi^b}{dz}-G^{bd}\partial_dW
\right)
+
W_f-W_i.
$$

Hence

$$
T\ge |W_f-W_i|,
$$

and a saturated wall obeys

$$
\frac{d\phi^a}{dz}=G^{ab}\partial_bW.
$$

In supersymmetric theories, this formula becomes richer: $W$ is the superpotential, $W_f-W_i$ contributes to a central charge, and the wall preserves part of the supersymmetry when the bound is saturated.

## BPS bounds from supersymmetry

In a supersymmetric theory, BPS bounds can be read from positivity of the Hilbert-space norm. Schematically, suppose the algebra contains

$$
\{Q,Q^\dagger\}\sim H-|Z|.
$$

Since the left side is a positive operator, any state obeys

$$
M\ge |Z|.
$$

A state saturates the bound when some linear combination of supercharges annihilates it:

$$
Q_{\rm preserved}|{\rm BPS}\rangle=0.
$$

This is the algebraic reason BPS objects are special. They sit in shortened supermultiplets. Their masses or tensions can be related to charges protected by symmetry and holomorphy, rather than being arbitrary dynamical quantities.

The classical square-completion and the supersymmetry algebra are two sides of the same phenomenon when the soliton lives in a supersymmetric theory. The square completion gives the first-order field equations; the algebra explains why saturation implies unbroken supercharges and protected quantum numbers.

:::caution[BPS is not a magic word]
A BPS formula is only as good as its assumptions. You must specify the theory, boundary conditions, charge normalization, coupling limit, and whether quantum corrections modify the charge. Some BPS masses are exact; others receive controlled anomaly or coupling-renormalization corrections.
:::

## What BPS saturation buys you

BPS saturation is valuable because it adds structure beyond ordinary stability.

| Feature | Consequence |
|---|---|
| First-order equations | Easier construction of explicit or numerical solutions. |
| Energy equals charge | Mass or tension fixed by asymptotic data. |
| No-force conditions | Multi-soliton separation can become a modulus. |
| Zero modes | Moduli spaces often have controlled geometry. |
| Preserved supersymmetry | States may lie in shortened multiplets. |
| Protected quantities | Some masses, tensions, indices, and degeneracies survive quantum corrections. |

The no-force statement is especially important. If two BPS solitons with aligned charges saturate a linear bound,

$$
M_{1+2}=M_1+M_2,
$$

then static separation may cost no energy at leading order. This is why BPS multi-monopoles and BPS vortices often have moduli spaces whose coordinates include relative positions.

But be careful: no force is not guaranteed for all BPS-looking systems. The charges must be mutually compatible, the preserved supersymmetries must align, and the relevant moduli must remain normalizable.

## Central charges and phases

In supersymmetric theories with several charges, the bound often depends on a complex or vector-valued central charge. A common schematic form is

$$
M\ge |Z(\Gamma)|,
$$

where $\Gamma$ is an electric, magnetic, flavor, or topological charge vector. The phase of $Z$ matters. Two BPS objects with charges $\Gamma_1$ and $\Gamma_2$ satisfy

$$
|Z(\Gamma_1+\Gamma_2)|\le |Z(\Gamma_1)|+|Z(\Gamma_2)|.
$$

Equality holds when the complex numbers $Z(\Gamma_1)$ and $Z(\Gamma_2)$ have the same phase. When phases align, marginal binding and wall-crossing phenomena can occur. When phases do not align, a combined object may or may not exist as a stable BPS state.

This is one reason the word “BPS” becomes a research subject rather than merely a square-completion trick. In strongly coupled supersymmetric theories, the spectrum of BPS states can jump across walls of marginal stability while protected indices remain better behaved.

This page is only a preview of that story. The present chapter uses BPS bounds mainly to organize solitons and their moduli. The full technology belongs in the supersymmetry, duality, and integrability volumes.

## Common pitfalls

**BPS does not mean every solution is first-order.** The BPS equations imply the second-order equations under the stated assumptions. The converse is usually false. Non-BPS solitons can solve the equations of motion without saturating any bound.

**Topological stability is not the same as BPS saturation.** A soliton can be topologically stable but non-BPS. Its energy is then above the topological lower bound and depends on the detailed dynamics.

**The coupling must be special.** The Abelian Higgs vortex is BPS only at the critical coupling. Away from that point, vortices still exist, but the first-order equations and no-force property are lost.

**The boundary term must be finite and fixed.** A square completion is useful only when the leftover term is controlled by boundary conditions or conserved charges. Otherwise it is not a physical lower bound inside a sector.

**Gauge directions are not physical moduli.** BPS equations often have families of solutions, but pure gauge changes must be quotiented out. This becomes crucial for monopoles, vortices, instantons, and surface defects.

**Quantum exactness is not automatic.** In supersymmetric theories, BPS saturation often protects masses or tensions, but one must know whether the central charge itself is renormalized or anomalous. “BPS” is a powerful constraint, not a license to skip the quantum theory.

## Relations to other pages

This page summarizes a theme already visible in [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), and [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/). Those pages give the concrete field configurations; this page isolates the shared bound-and-first-order-equation logic.

It also connects directly to [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/). The next page, [Moduli-Space Dynamics](/nonperturbative-qft/solitons-defects-extended-configurations/moduli-space-dynamics-preview/), explains what happens when the BPS solution has continuous collective coordinates and is allowed to move slowly.

Later chapters will reuse BPS logic for instantons, monopole-instantons, confinement mechanisms on compactified spaces, and supersymmetric exact results.

## Research status

The classical Bogomolnyi bounds for kinks, vortices, monopoles, and many domain walls are established textbook material. The relation between BPS saturation, first-order equations, zero modes, and moduli spaces is also standard.

The supersymmetric BPS story is deeper. In many theories, BPS masses, tensions, indices, and protected degeneracies can be computed beyond ordinary perturbation theory. In strongly coupled theories, however, determining the full BPS spectrum, understanding wall crossing, constructing defect moduli spaces, and including singular defects or boundary conditions are active problems.

For the purposes of this volume, the stable lesson is simple: a BPS bound is one of the cleanest bridges between topology, energy minimization, and quantum protection.

## Exercises

### Exercise 1: Kink square completion

Let

$$
E=\int dx\,\left[\frac12(\phi')^2+\frac12(W')^2\right],
$$

where $W'=dW/d\phi$. Show that

$$
E\ge |W(\phi(+\infty))-W(\phi(-\infty))|.
$$

<details><summary><strong>Solution</strong></summary>

Complete the square:

$$
E
=
\int dx\,\frac12(\phi'\mp W')^2
\pm\int dx\,\phi'W'.
$$

Since

$$
\phi'W'=\frac{dW}{dx},
$$

we get

$$
E
=
\int dx\,\frac12(\phi'\mp W')^2
\pm[W(+\infty)-W(-\infty)].
$$

The square is nonnegative. Choosing the sign so that the boundary contribution is positive gives

$$
E\ge |W(+\infty)-W(-\infty)|.
$$

The bound is saturated when

$$
\phi'=\pm W'.
$$

</details>

### Exercise 2: First-order implies second-order

For the same one-field kink system, show that any solution of

$$
\phi'=W'(\phi)
$$

solves the static Euler–Lagrange equation

$$
\phi''=W'W''.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the first-order equation with respect to $x$:

$$
\phi''=\frac{d}{dx}W'(\phi)=W''(\phi)\phi'.
$$

Using $\phi'=W'(\phi)$ again gives

$$
\phi''=W''(\phi)W'(\phi),
$$

which is precisely the static equation of motion for

$$
V(\phi)=\frac12(W')^2.
$$

</details>

### Exercise 3: Vortex tension from flux

At the Abelian Higgs Bogomolnyi point, suppose

$$
T
=
\int d^2x\,\left(\text{nonnegative squares}\right)
+e v^2\int d^2x\,B
$$

for positive winding. If

$$
e\int d^2x\,B=2\pi n,
$$

find the BPS tension.

<details><summary><strong>Solution</strong></summary>

The squares are nonnegative, so

$$
T\ge e v^2\int d^2x\,B.
$$

Using flux quantization,

$$
T\ge 2\pi v^2 n.
$$

For a BPS vortex the squares vanish, so

$$
T_{\rm BPS}=2\pi v^2 n
$$

for $n>0$. For arbitrary sign,

$$
T_{\rm BPS}=2\pi v^2|n|.
$$

</details>

### Exercise 4: Positivity and a supersymmetric bound

Suppose a supersymmetric quantum theory has a Hermitian operator combination $\mathcal Q$ obeying

$$
\{\mathcal Q,\mathcal Q^\dagger\}=2(M-|Z|)
$$

on one-particle states of mass $M$. Use positivity of the Hilbert-space norm to show that $M\ge |Z|$.

<details><summary><strong>Solution</strong></summary>

For any state $|\psi\rangle$,

$$
\langle\psi|\{\mathcal Q,\mathcal Q^\dagger\}|\psi\rangle
=
\|\mathcal Q^\dagger|\psi\rangle\|^2+\|\mathcal Q|\psi\rangle\|^2
\ge0.
$$

On the specified one-particle state this equals

$$
2(M-|Z|)\langle\psi|\psi\rangle.
$$

For a nonzero state, $\langle\psi|\psi\rangle>0$, so

$$
M-|Z|\ge0,
$$

or $M\ge |Z|$. Saturation means the positive norm vanishes, so the relevant supercharge combination annihilates the state.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, sec. 92, for solitons, monopoles, the Bogomolny bound, and the BPS monopole solution.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chs. 3 and 11, for vortices, central charges, supersymmetric kinks, domain walls, flux tubes, and BPS monopoles.
- S. Coleman, *Aspects of Symmetry*, for the semiclassical and soliton background behind many of these arguments.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for a broad systematic treatment of topological solitons, BPS equations, and moduli spaces.
- E. Bogomolny, M. Prasad, and C. Sommerfield, for the original monopole bound and solution literature behind the term BPS.

## Version history

- **2026-06-27:** Initial polished preview page, added after Q-Balls in the solitons and defects chapter.
