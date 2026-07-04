---
title: "Riemann Surfaces"
description: "Explains Riemann surfaces as one-complex-dimensional manifolds, including charts, branched covers, compactification, meromorphic functions, cycles, periods, genus, Riemann–Hurwitz, and QFT applications to branch cuts, worldsheets, spectral curves, and elliptic Feynman integrals."
sidebar:
  label: "Riemann Surfaces"
  order: 8
level: Graduate
status: "Polished draft"
source: "Standard references on Riemann surfaces, algebraic curves, complex analysis, CFT, string theory, spectral curves, and mathematical physics, including Forster, Farkas–Kra, Miranda, Griffiths–Harris, Ahlfors–Sario, Donaldson, Nakahara, Frankel, Polchinski, Di Francesco–Mathieu–Sénéchal, D'Hoker–Phong, Ginsparg, Weinberg, Srednicki, Schwartz, Zee, Zinn-Justin, and modern references on elliptic and higher-genus structures in amplitudes and QFT."
topics:
  - Riemann surfaces
  - complex manifolds
  - branched covers
  - branch points
  - meromorphic functions
  - divisors
  - cycles
  - periods
  - genus
  - Riemann–Hurwitz formula
  - algebraic curves
  - spectral curves
  - moduli
canonicalTopics:
  - riemann-surface
  - complex-manifold
  - branched-cover
  - branch-point
  - meromorphic-function
  - divisor
  - cycle
  - period
  - genus
  - riemann-hurwitz-formula
  - algebraic-curve
  - spectral-curve
  - moduli
researchStatus:
  established:
    - "Riemann surfaces are the natural global setting for one-complex-dimensional analytic geometry, multivalued functions, meromorphic differentials, periods, two-dimensional CFT, and string worldsheets."
    - "Branch cuts and sheets can be replaced by a smooth complex curve on which the relevant functions become single-valued."
  active:
    - "Modern QFT uses Riemann surfaces and algebraic curves in conformal blocks, modular bootstrap, Seiberg–Witten theory, integrability, string perturbation theory, elliptic Feynman integrals, resurgence, and spectral-curve methods."
---

## Summary

A Riemann surface is a one-complex-dimensional manifold. Locally it looks like an open set in $\mathbb C$, and its coordinate changes are holomorphic. Globally it can have topology, punctures, handles, branch points, cycles, and moduli.

The physicist’s quickest way into the subject is this:

$$
\text{multivalued function on the plane}
\quad\leadsto\quad
\text{single-valued function on a Riemann surface}.
$$

For example, $\sqrt z$ is multivalued on the punctured plane, but it becomes a perfectly good meromorphic function on the curve

$$
y^2=z.
$$

The variable $y$ is the square root. The curve, not one arbitrary cut plane, is the natural object.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing two cut sheets glued into a Riemann surface with cycles and a branched cover of the Riemann sphere.](/figures/math-toolkit/riemann-surface-cuts-cycles.svg)

<figcaption>

A Riemann surface turns cuts and sheets into geometry. Branch cuts are choices of drawing; branch points, cycles, genus, meromorphic differentials, and periods are the invariant data. This is why the same language appears in scattering sheets, string worldsheets, finite-temperature CFT, spectral curves, and elliptic Feynman integrals.

</figcaption>
</figure>

In QFT, Riemann surfaces appear in two related ways. First, analytic functions of momenta or cross-ratios often live on multi-sheeted surfaces; physical and unphysical sheets encode thresholds and resonance poles. Second, two-dimensional theories and string perturbation theory are literally formulated on Riemann surfaces, where operator insertions are punctures and path integrals depend on complex structure.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), and [Conformal Maps](/math-toolkit/complex-analysis/conformal-maps/). The topology pages [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) and [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) are helpful for cycles and periods.

## Definition

A Riemann surface $\Sigma$ is a Hausdorff, second-countable topological space equipped with an atlas of charts

$$
\varphi_i:U_i\to V_i\subset\mathbb C
$$

such that on overlaps $U_i\cap U_j$, the transition functions

$$
\varphi_i\circ\varphi_j^{-1}:\varphi_j(U_i\cap U_j)\to\varphi_i(U_i\cap U_j)
$$

are holomorphic.

This is the one-complex-dimensional version of a complex manifold. It is also a two-real-dimensional oriented smooth manifold, but with extra structure: it knows which real coordinate changes come from holomorphic maps.

Basic examples are:

| Surface | Description | Typical role |
|---|---|---|
| $\mathbb C$ | Complex plane | Local coordinate patch. |
| $\mathbb C^\times$ | Punctured plane | Radial quantization and logarithmic cover. |
| $\mathbb{CP}^1$ | Riemann sphere | Tree-level worldsheet, meromorphic functions, global conformal maps. |
| $\mathbb C/\Lambda$ | Torus | Finite-temperature CFT, genus-one worldsheets, elliptic functions. |
| $y^2=P(z)$ | Hyperelliptic curve | Branch cuts, spectral curves, elliptic and higher-genus periods. |

The Riemann sphere is

$$
\mathbb{CP}^1=\mathbb C\cup\{\infty\}.
$$

A coordinate near infinity is

$$
\zeta=\frac{1}{z}.
$$

A torus is obtained by quotienting the plane by a lattice

$$
\Lambda=\mathbb Z+\tau\mathbb Z,
\qquad \operatorname{Im}\tau>0,
$$

so

$$
E_\tau=\mathbb C/\Lambda.
$$

The complex number $\tau$ is the modular parameter. Different $\tau$ values can describe equivalent tori if they are related by a modular transformation.

## From branch cuts to geometry

The function

$$
y=\sqrt{z-a}
$$

has two local values away from $z=a$. Drawing a branch cut from $a$ to infinity lets us choose one value on a cut plane. But that cut is not unique. Instead, introduce the curve

$$
y^2=z-a.
$$

A point on the curve is a pair $(z,y)$ satisfying the equation. For each $z\neq a$, there are two points:

$$
(z,+\sqrt{z-a}),
\qquad
(z,-\sqrt{z-a}).
$$

At $z=a$, the two branches meet. The projection

$$
\pi:\Sigma\to\mathbb{CP}^1,
\qquad
\pi(z,y)=z,
$$

is a branched cover. Near a branch point, a local coordinate $t$ on $\Sigma$ often satisfies

$$
z-a=t^e,
$$

where $e$ is the ramification index. For a square-root branch point, $e=2$.

This viewpoint replaces “crossing a cut changes sign” by a clean geometric statement: analytic continuation along a path lifts to a path on $\Sigma$, and the endpoint may lie on a different sheet of the projection.

## Meromorphic functions and differentials

A meromorphic function on a Riemann surface is holomorphic except for poles. It is the right global version of a rational or algebraic function. On the sphere, every meromorphic function is rational in $z$.

A meromorphic one-form is locally

$$
\omega=f(z)\,dz,
$$

with $f$ meromorphic. Under a holomorphic coordinate change $w=f_0(z)$,

$$
g(w)\,dw=g(f_0(z))f_0'(z)\,dz,
$$

so the expression transforms covariantly.

Periods are integrals of one-forms over cycles:

$$
\oint_\gamma \omega.
$$

They are everywhere in physics. They appear in classical action variables, Aharonov–Bohm phases, compact-boson winding sectors, Seiberg–Witten periods, finite-gap integrable systems, and elliptic Feynman integrals.

## Genus, cycles, and periods

A compact connected oriented surface is classified topologically by its genus $g$, the number of handles. Its Euler characteristic is

$$
\chi(\Sigma)=2-2g.
$$

For genus $g$, the first homology group has rank $2g$:

$$
H_1(\Sigma,\mathbb Z)\cong\mathbb Z^{2g}.
$$

One chooses a canonical basis of cycles

$$
A_1,\dots,A_g,
\qquad
B_1,\dots,B_g,
$$

with intersection pairing

$$
A_i\cdot A_j=0,
\qquad
B_i\cdot B_j=0,
\qquad
A_i\cdot B_j=\delta_{ij}.
$$

The space of holomorphic one-forms on a compact genus-$g$ Riemann surface has complex dimension $g$. Choose a normalized basis $\omega_i$ satisfying

$$
\oint_{A_i}\omega_j=\delta_{ij}.
$$

The period matrix is

$$
\Omega_{ij}=\oint_{B_i}\omega_j.
$$

For genus one, this reduces to the familiar modular parameter $\tau$. For higher genus, the period matrix controls theta functions and much of the analytic data of the surface.

## Riemann–Hurwitz formula

Branched covers give a practical way to compute genus. Let

$$
\pi:\Sigma\to X
$$

be a degree-$d$ holomorphic map between compact Riemann surfaces. If $e_p$ is the ramification index at $p\in\Sigma$, then the Riemann–Hurwitz formula says

$$
2-2g_\Sigma
=d(2-2g_X)-\sum_{p\in\Sigma}(e_p-1).
$$

For a hyperelliptic curve

$$
y^2=\prod_{i=1}^{2g+2}(z-e_i),
$$

with distinct branch points $e_i$, the projection to the $z$-sphere has degree $d=2$. Each branch point has $e_p=2$, so each contributes $1$. Since $X=\mathbb{CP}^1$ has $g_X=0$,

$$
2-2g_\Sigma
=2\cdot2-(2g+2)
=2-2g.
$$

Thus the curve has genus $g$. In particular,

$$
y^2=(z-e_1)(z-e_2)(z-e_3)(z-e_4)
$$

is genus one: an elliptic curve.

## Punctures, marked points, and boundaries

A puncture is a point removed from a Riemann surface. A marked point is a distinguished point that is still part of the surface. A boundary is a real one-dimensional edge of a surface with boundary. These are different objects.

In CFT, local operator insertions are usually modeled as marked points or punctures with chosen local coordinates. Near an insertion at $z_i$, one expands fields in powers of

$$
\xi_i=z-z_i.
$$

The operator product expansion is a local statement near colliding punctures. Moduli spaces of punctured Riemann surfaces organize how insertion points and complex structures vary.

For boundary CFT, the surface can have a physical boundary, such as the upper half-plane or disk. The doubling trick sometimes replaces a boundary problem by a problem on a doubled closed surface, but the boundary condition remains physical data; it is not erased by the doubling.

## Compactification and points at infinity

Many surfaces are noncompact at first sight but become compact after adding points. The complex plane compactifies to the Riemann sphere by adding one point:

$$
\mathbb C\cup\{\infty\}=\mathbb{CP}^1.
$$

The punctured plane $\mathbb C^\times$ compactifies by adding two points, $0$ and $\infty$.

For algebraic curves, compactification can introduce points at infinity and sometimes singularities. A smooth compact Riemann surface associated with an algebraic equation may require resolving singular points. In physics language: an equation is not always the same as the smooth curve it intends to describe. Degenerations, nodes, cusps, and pinched cycles are often physically important, especially in string perturbation theory, moduli spaces, and elliptic Feynman integrals.

## Riemann surfaces in QFT

Riemann surfaces enter QFT in several recurring patterns.

### Analytic structure and scattering sheets

A propagator, correlator, or amplitude often depends on a complex energy or invariant such as $s$. Thresholds create branch cuts. Continuing around a branch point moves the amplitude to another sheet. Stable particles appear as poles on the physical sheet; resonances usually appear as poles on unphysical sheets reached by analytic continuation through cuts.

This is exactly the language of Riemann surfaces, though many QFT calculations draw only a few sheets explicitly.

### Two-dimensional CFT

A two-dimensional Euclidean CFT naturally lives on Riemann surfaces. The sphere describes genus-zero correlation functions. The torus describes finite temperature and one-loop string worldsheets. Higher genus surfaces describe more complicated path integrals and conformal blocks.

The partition function on a torus depends on

$$
\tau\in\mathbb H
$$

but should transform consistently under

$$
\tau\mapsto\frac{a\tau+b}{c\tau+d},
\qquad
\begin{pmatrix}a&b\\c&d\end{pmatrix}\in SL(2,\mathbb Z).
$$

This is modular invariance, one of the central consistency conditions in two-dimensional CFT and string theory.

### Spectral curves

Many integrable QFTs, large-$N$ matrix models, Seiberg–Witten theories, and semiclassical systems are organized by spectral curves. The curve packages branch points, cycles, and periods into a single geometric object. Physical quantities such as central charges, effective couplings, actions, and densities of states can become period integrals.

A schematic example is

$$
y^2=P(z),
$$

where branch cuts encode a distribution of eigenvalues or classical turning points, and periods of $y\,dz$ encode actions or charges.

### Elliptic and higher-genus Feynman integrals

Many one-loop integrals reduce to logarithms and dilogarithms, whose analytic structure can be handled on genus-zero surfaces. Starting at higher loops, some diagrams involve elliptic curves. Then the natural functions are not ordinary polylogarithms but elliptic polylogarithms and period integrals on genus-one curves.

This is one reason modern amplitudes literature talks about curves, periods, and motives. The hard part of the integral is not merely a complicated formula; it is a different underlying geometry.

## Riemann sheet versus Riemann surface

A Riemann sheet is one branch of a multivalued function after making cuts. A Riemann surface is the full glued object containing all sheets, with a complex structure.

For square roots, the surface may have finitely many sheets. For logarithms, the surface has infinitely many sheets. For elliptic functions, the natural surface is a torus. For generic amplitudes with many thresholds, the full analytic structure can be vastly more complicated than the two-sheet cartoon.

The practical rule is:

$$
\text{use sheets for local bookkeeping, use surfaces for invariant structure.}
$$

## Common pitfalls

**A cut is not part of the invariant surface.** It is a choice used to draw or compute with a branch. Moving the cut changes the picture, not the analytic object.

**A Riemann surface is not necessarily embedded in three-dimensional space.** The common drawings are metaphors. The definition is by complex charts and holomorphic transition functions.

**The genus is global data.** It cannot be read from one local coordinate patch. Branch points and gluing determine it.

**A puncture is not a boundary.** A puncture is a missing point; a boundary is a real edge. They support different physical data.

**The physical sheet is a convention plus a boundary condition.** In scattering theory, “physical sheet” means the sheet reached from the physical boundary values with the chosen $i0$ prescription. The words do not make sense without the prescription.

**A singular algebraic equation is not automatically a smooth Riemann surface.** Singularities may need resolution, and degenerations can change cycles and periods.

## Exercises

### Exercise 1: Square root as a single-valued function

Consider the curve

$$
\Sigma=\{(z,y)\in\mathbb C^2:y^2=z\}.
$$

Show that $y$ is a single-valued holomorphic function on $\Sigma$, even though $\sqrt z$ is multivalued as a function of $z$ on $\mathbb C^\times$.

<details><summary><strong>Solution</strong></summary>

A point of $\Sigma$ is not just a value of $z$; it is a pair $(z,y)$ satisfying $y^2=z$. The function

$$
Y:\Sigma\to\mathbb C,
\qquad
Y(z,y)=y
$$

assigns exactly one complex number to each point of $\Sigma$. It is holomorphic because it is the restriction of the coordinate function $y$ on $\mathbb C^2$.

For a fixed nonzero $z$, there are two points of $\Sigma$:

$$
(z,+\sqrt z),
\qquad
(z,-\sqrt z).
$$

The multivaluedness has not disappeared by choosing one value; it has been geometrized into two points lying above the same $z$.

</details>

### Exercise 2: Genus of a four-branch-point double cover

Use Riemann–Hurwitz to show that

$$
y^2=(z-e_1)(z-e_2)(z-e_3)(z-e_4)
$$

with distinct $e_i$ is genus one after compactification.

<details><summary><strong>Solution</strong></summary>

The projection

$$
\pi(z,y)=z
$$

is a degree-$2$ map to $\mathbb{CP}^1$. The base has genus $0$, so

$$
2-2g_\Sigma=2(2)-\sum_p(e_p-1).
$$

There are four simple branch points, each with ramification index $e_p=2$, so each contributes $1$ to the sum. Thus

$$
2-2g_\Sigma=4-4=0.
$$

Therefore

$$
g_\Sigma=1.
$$

The compact smooth curve is a torus, also called an elliptic curve.

</details>

### Exercise 3: Periods on a torus

Let

$$
E_\tau=\mathbb C/(\mathbb Z+\tau\mathbb Z),
\qquad \operatorname{Im}\tau>0.
$$

Let $\omega=dz$. Compute the periods of $\omega$ over the cycles represented by $z\mapsto z+1$ and $z\mapsto z+\tau$.

<details><summary><strong>Solution</strong></summary>

The $A$-cycle is represented by the path from $0$ to $1$. Therefore

$$
\oint_A dz=\int_0^1 dz=1.
$$

The $B$-cycle is represented by the path from $0$ to $\tau$. Therefore

$$
\oint_B dz=\int_0^\tau dz=\tau.
$$

Thus the normalized holomorphic one-form has periods $(1,\tau)$, and the genus-one period matrix is simply $\tau$.

</details>

## References

For Riemann surfaces, see Forster, Farkas–Kra, Miranda, Ahlfors–Sario, Donaldson, and Griffiths–Harris. For geometry and topology aimed at physicists, see Nakahara and Frankel. For CFT and string applications, see Di Francesco–Mathieu–Sénéchal, Ginsparg, Polchinski, and D’Hoker–Phong. For QFT analytic structure and sheets, standard QFT texts such as Weinberg, Srednicki, Schwartz, Zee, and Zinn-Justin are useful. For modern uses in amplitudes and spectral curves, see current literature on elliptic Feynman integrals, Seiberg–Witten theory, integrability, and resurgence.

## Version history

- 2026-06-26: First polished draft.
