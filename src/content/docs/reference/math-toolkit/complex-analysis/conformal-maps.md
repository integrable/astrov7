---
title: "Conformal Maps"
description: "Explains conformal maps as holomorphic local coordinate changes, including angle preservation, metric rescaling, Laplace-equation covariance, Möbius transformations, plane–cylinder maps, primary-field transformation laws, and common QFT uses."
sidebar:
  label: "Conformal Maps"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard references on complex analysis, conformal mapping, two-dimensional CFT, boundary value problems, and QFT analytic structure, including Ahlfors, Stein–Shakarchi, Conway, Nehari, Needham, Polchinski, Di Francesco–Mathieu–Sénéchal, Cardy, Ginsparg, Weinberg, Srednicki, Schwartz, Zee, and mathematical-physics treatments of harmonic functions and conformal covariance."
topics:
  - conformal maps
  - holomorphic functions
  - Cauchy–Riemann equations
  - metric rescaling
  - Möbius transformations
  - upper half-plane
  - unit disk
  - plane-cylinder map
  - primary fields
  - stress tensor
  - Schwarzian derivative
  - boundary value problems
canonicalTopics:
  - conformal-map
  - holomorphic-function
  - cauchy-riemann-equations
  - metric-rescaling
  - mobius-transformation
  - upper-half-plane
  - unit-disk
  - plane-cylinder-map
  - primary-field
  - stress-tensor
  - schwarzian-derivative
  - boundary-value-problem
researchStatus:
  established:
    - "Conformal maps are standard tools in complex analysis, electrostatics, fluid flow, two-dimensional boundary value problems, string worldsheets, radial quantization, and two-dimensional conformal field theory."
    - "In two dimensions, holomorphic coordinate changes locally rescale the metric and preserve oriented angles wherever the derivative is nonzero."
  active:
    - "Modern uses include boundary CFT, interfaces and defects, conformal bootstrap kinematics, entanglement calculations, uniformization, celestial amplitudes, and analytic continuation on moduli spaces."
---

## Summary

A conformal map is a coordinate change that preserves angles. In one complex dimension, the cleanest source of conformal maps is holomorphic functions with nonzero derivative. If

$$
w=f(z),
\qquad f'(z_0)\neq0,
$$

then near $z_0$ the map acts on small displacements by

$$
\delta w=f'(z_0)\delta z.
$$

Multiplication by the complex number $f'(z_0)$ is a rotation by $\arg f'(z_0)$ and a scaling by $|f'(z_0)|$. Therefore infinitesimal angles are preserved, while lengths and areas are generally rescaled.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing an upper half-plane mapped to a disk and the local action of a conformal map as rotation plus scaling.](/figures/math-toolkit/conformal-map-domain-flow.svg)

<figcaption>

A holomorphic map with $f'(z)\neq0$ is locally a rotation and a scale transformation. Globally, the same map can turn a difficult boundary-value problem into an easier one, such as the upper half-plane into the disk. In QFT, the map must be accompanied by transformation rules for fields and, for the stress tensor, possible anomaly terms.

</figcaption>
</figure>

The QFT reason to care is simple: in two dimensions, many field equations, correlation functions, and boundary problems are almost invariant under conformal maps. The word “almost” is doing real work. Classical equations may transform covariantly, but quantum correlation functions also know about scaling dimensions, spin, central charge, zero modes, regulators, and boundary conditions.

## Prerequisites

You should know [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/). For operator-theoretic language, [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/) and [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/) are helpful.

The next page, [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), explains what happens when conformal charts are glued together to make a global complex curve.

## Local definition

Let $U,V\subset\mathbb C$ be open sets. A map

$$
f:U\to V
$$

is a conformal map at $z_0\in U$ if it preserves oriented angles between tangent vectors at $z_0$. A holomorphic function with $f'(z_0)\neq0$ is conformal at $z_0$. A biholomorphism is a holomorphic bijection with holomorphic inverse; equivalently, it is a global conformal equivalence of domains.

Write

$$
f(z)=u(x,y)+iv(x,y),
\qquad z=x+iy.
$$

The Cauchy–Riemann equations are

$$
u_x=v_y,
\qquad
u_y=-v_x.
$$

The real Jacobian matrix is therefore

$$
Df=
\begin{pmatrix}
 u_x & u_y\\
 v_x & v_y
\end{pmatrix}
=
\begin{pmatrix}
 u_x & -v_x\\
 v_x & u_x
\end{pmatrix}.
$$

This is exactly a scale times a rotation. Its determinant is

$$
\det Df=u_x^2+v_x^2=|f'(z)|^2.
$$

If $f'(z)\neq0$, the local area element transforms as

$$
d^2w=|f'(z)|^2d^2z.
$$

The flat metric transforms as

$$
|dw|^2=|f'(z)|^2|dz|^2.
$$

Thus a holomorphic coordinate change is conformal because it rescales the metric by a positive function:

$$
ds_w^2=\Omega(z)^2 ds_z^2,
\qquad
\Omega(z)=|f'(z)|.
$$

That is the entire local story. The global story is about domains, boundaries, branch points, punctures, and topology.

## Critical points are not conformal points

The condition $f'(z_0)\neq0$ is essential. The map

$$
w=z^n
$$

has

$$
f'(z)=nz^{n-1}.
$$

At $z=0$, the derivative vanishes for $n>1$. A small angle $\alpha$ at the origin is multiplied to $n\alpha$, so the map is not conformal there. The origin is a branch point for the inverse relation

$$
z=w^{1/n}.
$$

Away from $0$, however, $z^n$ is locally conformal. This distinction is everywhere in QFT: a coordinate change can be locally conformal on a punctured surface while having physically important ramification at special points.

## Laplace equation and two-dimensional boundary problems

In two real dimensions, conformal maps are especially useful because the scalar Laplace equation is conformally covariant. If $w=f(z)$ is holomorphic with $f'\neq0$, and if

$$
\widetilde\phi(w,\bar w)=\phi(z,\bar z),
\qquad w=f(z),
$$

then

$$
\Delta_z \phi(z,\bar z)=|f'(z)|^2\Delta_w\widetilde\phi(w,\bar w).
$$

Therefore

$$
\Delta_z\phi=0
\qquad\Longleftrightarrow\qquad
\Delta_w\widetilde\phi=0.
$$

This is why conformal maps solve many two-dimensional electrostatics, fluid-flow, heat-kernel, and free-field problems. A hard domain in the $z$-plane can sometimes be mapped to a disk, half-plane, strip, or annulus where the Green function is known.

For the free massless scalar in two Euclidean dimensions,

$$
S[\phi]=\frac{1}{4\pi}\int d^2z\,\partial\phi\,\bar\partial\phi,
$$

with

$$
\partial=\frac{1}{2}(\partial_x-i\partial_y),
\qquad
\bar\partial=\frac{1}{2}(\partial_x+i\partial_y),
$$

the classical action is invariant under conformal coordinate changes, up to boundary and zero-mode issues. The miracle is dimension-specific: in $d$ real dimensions, the Dirichlet energy scales as

$$
\int d^dx\,|\nabla\phi|^2
\longmapsto
\int d^dx\,\Omega^{d-2}|\nabla\phi|^2.
$$

Only for $d=2$ does the power $d-2$ vanish. Tiny exponent, huge consequences.

## The disk and half-plane

The upper half-plane

$$
\mathbb H=\{z\in\mathbb C: \operatorname{Im}z>0\}
$$

and the unit disk

$$
\mathbb D=\{w\in\mathbb C: |w|<1\}
$$

are conformally equivalent. A standard map is

$$
w=\frac{z-i}{z+i}.
$$

Its inverse is

$$
z=i\frac{1+w}{1-w}.
$$

Check the boundary: if $z=x\in\mathbb R$, then

$$
\left|\frac{x-i}{x+i}\right|=1.
$$

Thus the real axis maps to the unit circle. The point $z=i$ maps to $w=0$. The point $z=\infty$ maps to $w=1$.

This map is the archetype of a conformal trick: boundary conditions on a line become boundary conditions on a circle, and symmetries become more visible. In boundary CFT, the upper half-plane is often the natural home for a planar boundary, while the disk is the natural home for radial quantization with a boundary.

## Möbius transformations

A Möbius transformation is

$$
w=\frac{az+b}{cz+d},
\qquad ad-bc\neq0.
$$

Multiplying all coefficients by the same nonzero number does not change the map, so the natural parameter group is projective. On the Riemann sphere $\mathbb{CP}^1=\mathbb C\cup\{\infty\}$, Möbius transformations are precisely the biholomorphic automorphisms.

Their derivative is

$$
\frac{dw}{dz}=\frac{ad-bc}{(cz+d)^2}.
$$

They map generalized circles to generalized circles, where a generalized circle means either an ordinary circle or a line. The upper half-plane is preserved by the real subgroup

$$
w=\frac{az+b}{cz+d},
\qquad
\begin{pmatrix}a&b\\ c&d\end{pmatrix}\in PSL(2,\mathbb R).
$$

The cross-ratio

$$
[z_1,z_2;z_3,z_4]
=
\frac{(z_1-z_3)(z_2-z_4)}{(z_1-z_4)(z_2-z_3)}
$$

is invariant under Möbius transformations. This is why four-point functions in CFT depend on cross-ratios: global conformal symmetry can move three points to convenient locations, but it cannot remove all invariant data once four points are present.

## Plane, cylinder, and radial quantization

The exponential map

$$
z=e^w,
\qquad w=\tau+i\sigma,
$$

turns the cylinder coordinate $w$ into the punctured plane. If $\sigma\sim\sigma+2\pi$, then

$$
z=e^{\tau+i\sigma}
$$

is single-valued. Constant $\tau$ circles become circles of fixed radius in the $z$-plane; increasing $\tau$ moves radially outward. Thus translations in $\tau$ become dilatations in the plane.

For a cylinder with spatial circumference $L$, use

$$
z=e^{2\pi w/L}.
$$

The derivative is

$$
\frac{dz}{dw}=\frac{2\pi}{L}e^{2\pi w/L}=\frac{2\pi}{L}z.
$$

In two-dimensional CFT, this map converts plane correlators into thermal or finite-size cylinder correlators. For a scalar primary of weights $(h,\bar h)$,

$$
\mathcal O_w(w,\bar w)
=
\left(\frac{dz}{dw}\right)^h
\left(\frac{d\bar z}{d\bar w}\right)^{\bar h}
\mathcal O_z(z,\bar z).
$$

For a spinless primary with total dimension

$$
\Delta=h+\bar h,
$$

the two-point function on the plane

$$
\langle \mathcal O(z_1,\bar z_1)\mathcal O(z_2,\bar z_2)\rangle
=\frac{1}{z_{12}^{2h}\bar z_{12}^{2\bar h}}
$$

maps to the cylinder expression

$$
\langle \mathcal O(w_1,\bar w_1)\mathcal O(w_2,\bar w_2)\rangle
=
\left(\frac{\pi/L}{\sinh\frac{\pi w_{12}}{L}}\right)^{2h}
\left(\frac{\pi/L}{\sinh\frac{\pi \bar w_{12}}{L}}\right)^{2\bar h},
$$

up to the usual choice of Euclidean cylinder conventions and phases. This formula is one of the fastest ways to see how power laws on the plane become exponential falloff along a cylinder.

## Transformation of primary fields

A primary field is defined by its simple transformation law under local conformal maps. In complex coordinates, a primary field of weights $(h,\bar h)$ satisfies

$$
\mathcal O(z,\bar z)
\mapsto
\left(\frac{dw}{dz}\right)^h
\left(\frac{d\bar w}{d\bar z}\right)^{\bar h}
\mathcal O(w,\bar w),
\qquad w=f(z).
$$

Equivalently, if one rewrites the same operator in the new coordinate $w$, then

$$
\mathcal O_w(w,\bar w)
=
\left(\frac{dz}{dw}\right)^h
\left(\frac{d\bar z}{d\bar w}\right)^{\bar h}
\mathcal O_z(z,\bar z).
$$

The scaling dimension and spin are

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

This is the operational meaning of conformal weights: they tell you exactly which powers of the local scale-and-rotation factor appear when the coordinate is changed.

Descendants are not primary in this simple sense. Derivatives of primaries acquire extra terms because derivatives also hit the coordinate-dependent Jacobian factors. The stress tensor is even more interesting.

## Stress tensor and the Schwarzian derivative

The holomorphic stress tensor $T(z)$ is not a primary operator in a quantum CFT with central charge $c$. Under a holomorphic coordinate change $w=f(z)$, the standard convention is

$$
T(z)=\left(\frac{dw}{dz}\right)^2 T(w)+\frac{c}{12}\{w,z\},
$$

where

$$
\{w,z\}
=\frac{w'''(z)}{w'(z)}-\frac{3}{2}\left(\frac{w''(z)}{w'(z)}\right)^2
$$

is the Schwarzian derivative.

The Schwarzian vanishes for Möbius transformations. That is why global conformal transformations act on $T$ as if it had weight $(2,0)$, while general local conformal transformations reveal the central charge.

For the cylinder map

$$
z=e^w,
$$

equivalently $w=\log z$, the Schwarzian term produces the familiar Casimir-energy shift. This is one of the cleanest places where a coordinate transformation remembers quantum regularization.

## Conformal maps are not magic erasers

A conformal map preserves local angles and transforms local equations nicely, but it does not erase all physics. It can change:

| Object | What changes under a conformal map? |
|---|---|
| Lengths | Local scale factor $|f'|$ appears. |
| Areas | Local factor $|f'|^2$ appears. |
| Boundaries | Boundary shape changes; boundary conditions must be transported. |
| Fields | Scaling weights and spin factors appear. |
| Stress tensor | Schwarzian anomaly can appear. |
| Regulators | A uniform cutoff in one coordinate is usually nonuniform in another. |
| Zero modes | Global topology and boundary conditions decide them. |
| Massive theories | Mass terms generally break conformal invariance. |

This is the common trap: one maps a domain beautifully, solves an equation, and forgets that the operator, measure, cutoff, or boundary condition also transformed. The geometry is clean; the physics still keeps receipts.

## Common examples

The most common conformal maps in QFT and mathematical physics are:

| Map | Use |
|---|---|
| $w=(z-i)/(z+i)$ | Upper half-plane to disk. |
| $z=e^w$ | Cylinder to punctured plane; radial quantization. |
| $z=e^{\pi w/L}$ | Strip to upper half-plane. |
| $w=\log z$ | Plane with puncture to cylinder. |
| $w=z^\alpha$ | Wedge opening angles; branch point at $0$. |
| Möbius maps | Move three points on the sphere; preserve cross-ratios. |
| Schwarz–Christoffel maps | Polygonal domains; boundary value problems. |
| Elliptic maps | Annuli, tori, doubly periodic problems. |

The Riemann mapping theorem says every simply connected proper open subset of $\mathbb C$ is biholomorphic to the disk. That theorem is profound, but it does not usually hand you an explicit function. In actual QFT calculations, the few explicit maps above do most of the daily work.

## Conformal maps in higher dimensions

In two real dimensions, local conformal transformations are essentially arbitrary holomorphic or antiholomorphic functions. In $d>2$, conformal transformations are much more rigid. On flat Euclidean space, the local conformal group is generated by translations, rotations, dilatations, and special conformal transformations, giving a finite-dimensional group locally isomorphic to $SO(d+1,1)$.

That difference explains why two-dimensional CFT has infinitely many local conformal symmetries, while higher-dimensional CFTs have a finite global conformal group. The higher-dimensional conformal bootstrap is still powerful, but the mechanism is not “arbitrary holomorphic maps.”

## Common pitfalls

**A holomorphic map is conformal only where its derivative is nonzero.** Branch points, zeros of $f'$, and singularities must be excluded or treated separately.

**A conformal map preserves angles, not distances.** Distances are rescaled by $|f'|$, and areas by $|f'|^2$.

**The boundary condition also transforms.** Dirichlet conditions are easy. Neumann, Robin, gauge, and mixed boundary conditions can acquire normal-derivative and scale factors.

**A map of coordinates is not automatically a symmetry of the quantum theory.** A quantum CFT has conformal covariance, but nonzero central charge, regulators, boundaries, and anomalies can add terms.

**A branch cut is not a conformal boundary.** A branch cut is often a bookkeeping line used to define a branch. A physical boundary is part of the domain or spacetime problem.

**Möbius transformations are not all conformal maps of all domains.** They are all automorphisms of the Riemann sphere, but a general simply connected planar domain usually needs a more complicated map to the disk.

## Quick diagnostic

When using a conformal map in a calculation, ask:

1. Where is $f'(z)=0$ or $\infty$?
2. What happens to the boundary?
3. What is the local scale factor $|f'|$?
4. Are the fields scalars, primaries, tensors, or something else?
5. Does the stress tensor acquire a Schwarzian term?
6. Are there zero modes, punctures, or topology changes?
7. Is the theory actually conformal, or only a massless classical equation is?

This list catches most errors before they calcify into a sign-and-factor archaeology dig.

## Exercises

### Exercise 1: Cauchy–Riemann implies angle preservation

Let $f=u+iv$ be holomorphic near $z_0$, with $f'(z_0)\neq0$. Show that the real Jacobian matrix is a positive scale times a rotation.

<details><summary><strong>Solution</strong></summary>

By the Cauchy–Riemann equations,

$$
u_x=v_y,
\qquad
u_y=-v_x.
$$

Thus

$$
Df=
\begin{pmatrix}
 u_x & u_y\\
 v_x & v_y
\end{pmatrix}
=
\begin{pmatrix}
 u_x & -v_x\\
 v_x & u_x
\end{pmatrix}.
$$

Let

$$
\rho=\sqrt{u_x^2+v_x^2}=|f'(z_0)|.
$$

Since $f'(z_0)\neq0$, $\rho>0$. Choose $\theta$ such that

$$
\cos\theta=\frac{u_x}{\rho},
\qquad
\sin\theta=\frac{v_x}{\rho}.
$$

Then

$$
Df=\rho
\begin{pmatrix}
\cos\theta&-\sin\theta\\
\sin\theta&\cos\theta
\end{pmatrix}.
$$

This is a scale times a rotation, so it preserves oriented angles.

</details>

### Exercise 2: Upper half-plane to disk

Show that

$$
w=\frac{z-i}{z+i}
$$

maps the upper half-plane to the unit disk.

<details><summary><strong>Solution</strong></summary>

Let $z=x+iy$ with $y>0$. Then

$$
|w|^2=
\frac{|z-i|^2}{|z+i|^2}
=
\frac{x^2+(y-1)^2}{x^2+(y+1)^2}.
$$

Since $y>0$,

$$
x^2+(y-1)^2<x^2+(y+1)^2,
$$

so $|w|<1$. If $y=0$, then $|w|=1$, so the boundary real axis maps to the unit circle. The inverse map

$$
z=i\frac{1+w}{1-w}
$$

is holomorphic on the disk and has positive imaginary part there, completing the argument.

</details>

### Exercise 3: Plane two-point function on the cylinder

Let $z=e^{2\pi w/L}$ and let $\mathcal O$ be a holomorphic primary of weight $h$ with plane correlator

$$
\langle \mathcal O(z_1)\mathcal O(z_2)\rangle=\frac{1}{(z_1-z_2)^{2h}}.
$$

Show that the cylinder correlator is

$$
\langle \mathcal O(w_1)\mathcal O(w_2)\rangle
=
\left(\frac{\pi/L}{\sinh(\pi w_{12}/L)}\right)^{2h}.
$$

<details><summary><strong>Solution</strong></summary>

The primary transformation gives

$$
\mathcal O(w)=\left(\frac{dz}{dw}\right)^h\mathcal O(z),
\qquad
\frac{dz}{dw}=\frac{2\pi}{L}z.
$$

Therefore

$$
\langle \mathcal O(w_1)\mathcal O(w_2)\rangle
=
\left(\frac{2\pi}{L}\right)^{2h}
\frac{(z_1z_2)^h}{(z_1-z_2)^{2h}}.
$$

Now

$$
z_1-z_2
=e^{\pi(w_1+w_2)/L}
\left(e^{\pi w_{12}/L}-e^{-\pi w_{12}/L}\right)
=2e^{\pi(w_1+w_2)/L}\sinh\frac{\pi w_{12}}{L},
$$

and

$$
(z_1z_2)^h=e^{2\pi h(w_1+w_2)/L}.
$$

The exponential factors cancel, leaving

$$
\left(\frac{2\pi}{L}\right)^{2h}
\frac{1}{\left(2\sinh(\pi w_{12}/L)\right)^{2h}}
=
\left(\frac{\pi/L}{\sinh(\pi w_{12}/L)}\right)^{2h}.
$$

</details>

## References

For complex analysis and conformal maps, see Ahlfors, Conway, Stein–Shakarchi, Nehari, and Needham. For physical applications to two-dimensional field theory, see Di Francesco–Mathieu–Sénéchal, Ginsparg’s CFT lectures, Cardy’s boundary CFT lectures, Polchinski for worldsheet conformal maps, and standard QFT texts such as Weinberg, Srednicki, Schwartz, Zee, and Zinn-Justin for analytic-continuation and field-theoretic context.

## Version history

- 2026-06-26: First polished draft.
