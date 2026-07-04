---
title: "Cross Ratios"
description: "Derives conformal cross ratios for four-point functions, explains the variables u, v, z, and z-bar, and records their OPE limits and crossing transformations."
sidebar:
  label: "Cross Ratios"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Dolan and Osborn 2004; Rychkov 2016; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - cross ratios
  - four-point functions
  - conformal frames
  - crossing symmetry
canonicalTopics:
  - conformal-cross-ratios
  - four-point-kinematics
  - crossing-transformations
  - ope-limits
researchStatus:
  established:
    - "For four separated points in a flat Euclidean CFT with d at least two, conformal invariance leaves two independent scalar invariants, conventionally written as u and v or as z and z-bar."
    - "Cross ratios are kinematic variables; all dynamical information in scalar four-point functions is contained in functions of these variables."
  active:
    - "Lorentzian continuation, branch structure, Regge limits, lightcone limits, and multi-point generalizations of cross-ratio kinematics are active tools in analytic bootstrap and conformal collider physics."
---

## Summary

Cross ratios are the dimensionless conformal invariants of point configurations. For two or three separated scalar insertions in flat space, conformal symmetry removes all position dependence except the overall covariant powers fixed by dimensions. For four insertions, two invariant variables remain.

For four points $x_i$ in Euclidean $\mathbb R^d$, $d\geq 2$, the standard cross ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2},
\qquad x_{ij}^2=(x_i-x_j)^2.
$$

The first variable is a scalar cross ratio. It is not a component of a vector, even though the letter $u$ is also used elsewhere for other objects.

The same information is often packaged as $z,\bar z$:

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

In Euclidean signature, $z$ and $\bar z$ are complex conjugates for a generic configuration. In Lorentzian signature, they are better treated as independent variables after choosing an operator ordering and an $i\epsilon$ prescription.

:::note[Why cross ratios matter]
A scalar four-point function is not a number fixed by symmetry. It is a function of $u$ and $v$. The OPE gives different series expansions of this same function in different limits, and crossing symmetry says that all of those expansions describe one correlator.
:::

## Prerequisites

You should know [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/), [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/), and [Finite Conformal Transformations](/cft-bootstrap/conformal-symmetry/finite-conformal-transformations/).

This page uses flat Euclidean space unless stated otherwise. The Lorentzian comments are meant to prevent misreadings, not to replace a full discussion of Lorentzian CFT.

## Core idea

A conformal transformation preserves angles but may rescale lengths by a position-dependent factor. Ordinary distances $x_{ij}^2$ are therefore not conformal invariants. Ratios of products of squared distances can nevertheless be arranged so that every local scale factor cancels.

The first nontrivial case is four points. Conformal symmetry can place three generic points at convenient positions. The fourth point still has invariant shape data. Those two real shape variables are $u$ and $v$, or equivalently $z$ and $\bar z$.

A useful slogan is

$$
\text{four points modulo conformal transformations}
\quad\Longleftrightarrow\quad
\text{two cross ratios}.
$$

The statement is kinematic. It does not assume a Lagrangian, weak coupling, a large-$N$ limit, or a particular spectrum.

## Setup and conventions

Write

$$
x_{ij}^{\mu}=x_i^\mu-x_j^\mu,
\qquad
x_{ij}^2=x_{ij}\cdot x_{ij}.
$$

In Euclidean signature $x_{ij}^2\geq 0$, with equality only at coincident points. We assume separated insertions unless discussing limits.

The standard cross ratios are

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Equivalently, one introduces $z,\bar z$ by

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

With these conventions, an identical scalar four-point function is written as

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2)^{\Delta_\phi}(x_{34}^2)^{\Delta_\phi}}.
$$

Another choice of prefactor gives another function related to $\mathcal G$ by a known power of $u$ and $v$. The invariant content is the same.

## Why the ratios are conformal invariants

Translations and rotations leave each $x_{ij}^2$ unchanged. A constant dilatation $x^\mu\mapsto \lambda x^\mu$ sends

$$
x_{ij}^2\mapsto \lambda^2 x_{ij}^2,
$$

so all powers of $\lambda$ cancel in $u$ and $v$.

The only non-obvious generator to check is inversion,

$$
x^\mu\mapsto x'^\mu=\frac{x^\mu}{x^2}.
$$

For separated nonzero points,

$$
(x_i'-x_j')^2=\frac{x_{ij}^2}{x_i^2x_j^2}.
$$

Therefore

$$
u'=
\frac{
\left(x_{12}^2/(x_1^2x_2^2)\right)
\left(x_{34}^2/(x_3^2x_4^2)\right)
}{
\left(x_{13}^2/(x_1^2x_3^2)\right)
\left(x_{24}^2/(x_2^2x_4^2)\right)
}
=u,
$$

and similarly $v'=v$. Since the finite conformal group is generated by translations, rotations, dilatations, and special conformal transformations, and a special conformal transformation is inversion–translation–inversion, $u$ and $v$ are conformally invariant.

This calculation also explains why individual distances are not invariant. Under a general conformal transformation, each point carries its own Weyl factor. Cross ratios are the combinations in which those factors cancel point by point.

## Counting the invariants

For $n$ generic points in $d$ dimensions, the raw number of coordinates is $nd$. The connected conformal group in $d\geq 3$ has dimension

$$
\frac{(d+1)(d+2)}{2}.
$$

This simple subtraction must be used with care when $n$ is small, because a generic configuration may have a stabilizer. For four generic points in $d\geq 2$, the correct result is two scalar invariants. A geometric way to see this is more useful than the dimension count: conformal transformations can put three points at $0$, $1$, and $\infty$, while the fourth point remains at a complex coordinate $z$ in a two-plane.

Thus a conformal frame can be chosen as

$$
x_1=0,
\qquad
x_3=e_1,
\qquad
x_4=\infty,
\qquad
x_2=z_1 e_1+z_2 e_2.
$$

Package the two coordinates of $x_2$ as

$$
z=z_1+i z_2,
\qquad
\bar z=z_1-i z_2.
$$

Then the two real invariants are equivalently $z_1,z_2$ or $z,\bar z$.

## The variables z and z-bar

The relation between the two parametrizations is

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

Conversely, in Euclidean signature,

$$
\operatorname{Re} z=\frac{1+u-v}{2},
\qquad
(\operatorname{Im} z)^2=u-\frac{(1+u-v)^2}{4}.
$$

Therefore a Euclidean four-point configuration satisfies

$$
(1+u-v)^2\leq 4u,
\qquad u\geq 0.
$$

The boundary of this domain corresponds to four points that can be put on a line or circle, so that $z=\bar z$ is real. The common interval $0<z<1$ describes the Euclidean ordering in which the OPE channel $x_1\to x_2$ is naturally approached by $z\to 0$.

In two-dimensional CFT, $z$ and $\bar z$ are literally the holomorphic and antiholomorphic coordinates of the insertions after using the global conformal group. In higher dimensions they are still useful because any four points can be brought into a two-plane by conformal transformations and rotations.

## OPE limits

Cross ratios are most useful because OPE limits are simple regions in cross-ratio space.

| Limit | Geometric meaning | Cross-ratio behavior | Frame behavior |
|---|---|---|---|
| $x_1\to x_2$ | $12\to 34$ channel | $u\to 0$, $v\to 1$ | $z,\bar z\to 0$ |
| $x_1\to x_4$ | $14\to 23$ channel | $v\to 0$, $u\to 1$ | $z,\bar z\to 1$ |
| $x_1\to x_3$ | $13\to 24$ channel | $u,v\to\infty$ with fixed ratio | $z,\bar z\to\infty$ |

For identical scalar operators, the $12\to 34$ OPE expansion is often written schematically as

$$
\mathcal G(u,v)
=
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2 G_{\Delta,\ell}(u,v).
$$

The small-$z$ behavior of a conformal block knows the dimension and spin of the exchanged primary. In a scalar exchange channel, the leading power is controlled by the dimension of the exchanged operator. This is the bridge from geometric kinematics to spectral information.

## Crossing transformations

Permuting the four operator insertions changes the way the same configuration is described by cross ratios. For $z$, the anharmonic group gives six possible images:

$$
z,
\qquad
1-z,
\qquad
\frac{1}{z},
\qquad
\frac{1}{1-z},
\qquad
\frac{z}{z-1},
\qquad
\frac{z-1}{z}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Six anharmonic images of the four-point cross ratio](/figures/cft-bootstrap/cross-ratio-crossing-maps.svg)

<figcaption>

Permuting four points acts on the conformal-frame coordinate $z$ by six fractional-linear transformations. These are the kinematic transformations behind crossing equations in different OPE channels.

</figcaption>
</figure>

For $u,v$, some especially common permutations are

| Permutation | Action on $u,v$ | Action on $z$ |
|---|---|---|
| $1\leftrightarrow 3$ | $(u,v)\mapsto (v,u)$ | $z\mapsto 1-z$ |
| $1\leftrightarrow 2$ | $(u,v)\mapsto (u/v,1/v)$ | $z\mapsto z/(z-1)$ |
| $1\leftrightarrow 4$ | $(u,v)\mapsto (1/u,v/u)$ | $z\mapsto 1/z$ |

The exact crossing equation also depends on operator labels and on the prefactor convention chosen for the correlator. The cross-ratio transformation is only the kinematic part.

For identical scalars with

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{\mathcal G(u,v)}{(x_{12}^2)^\Delta(x_{34}^2)^\Delta},
$$

the exchange $x_1\leftrightarrow x_3$ gives

$$
v^{\Delta}\mathcal G(u,v)=u^{\Delta}\mathcal G(v,u).
$$

This is the simplest crossing equation. It is simple enough to fit on one line and strong enough to launch the numerical bootstrap.

## Euclidean and Lorentzian domains

In Euclidean signature, $z$ and $\bar z$ are complex conjugates away from special configurations. Euclidean correlators are single-valued functions on the appropriate configuration space, up to the expected singularities when points collide.

In Lorentzian signature, the same algebraic definitions are used but the analytic structure becomes essential. The variables $z$ and $\bar z$ can become independent real variables in suitable causal regions, and different operator orderings are obtained by continuing around branch points with an $i\epsilon$ prescription.

This distinction matters in lightcone and Regge limits. For example, the lightcone limit can hold one of $z,\bar z$ small while the other remains finite. That is invisible if one insists too strongly on the Euclidean relation $\bar z=z^*$.

## More than four points

For $n>4$, there are more conformal invariants. One can build them from ratios of squared distances, but the number and the algebraic relations among them depend on $n$ and $d$. Multi-point cross ratios are useful in conformal perturbation theory, higher-point bootstrap problems, Regge physics, and AdS Witten diagrams.

This volume introduces four-point cross ratios first because they are the minimal variables needed for the ordinary conformal bootstrap. Higher-point kinematics should be learned after the reader is comfortable with four-point OPE channels and conformal blocks.

## Spinning operators and defects

For spinning correlators, $u$ and $v$ still describe the scalar position dependence, but they do not describe the whole correlator. Polarization vectors, spinor variables, or embedding-space auxiliary variables introduce tensor structures. A spinning four-point function has the schematic form

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\sum_a \mathcal T_a(x_i,\text{polarizations})\,\mathcal G_a(u,v),
$$

where $\mathcal T_a$ are conformally covariant tensor structures and $\mathcal G_a$ are scalar functions of cross ratios.

Defect CFTs also have cross ratios, but the preserved conformal group is smaller. A bulk two-point function in the presence of a planar defect can already have nontrivial cross-ratio dependence. The rule is the same: fewer symmetries leave more invariant shape data.

## Common pitfalls

Do not confuse cross ratios with OPE coefficients. Cross ratios describe where operators are inserted; OPE coefficients describe the theory.

Do not assume $z$ and $\bar z$ are always complex conjugates. That is a Euclidean statement. Lorentzian correlators require analytic continuation and operator-ordering data.

Do not forget the prefactor convention. Different books define $\mathcal G(u,v)$ with different powers of $x_{ij}^2$. The crossing equation changes by known powers of $u$ and $v$.

Do not treat $u\to 0$ by itself as a complete OPE limit. For the Euclidean $12$ OPE one also has $v\to 1$, usually with $z,\bar z\to 0$.

Do not call every ratio of distances a conformal cross ratio. The pointwise Weyl factors must cancel under inversion.

## Relations to other pages

[Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) uses $u,v,z,\bar z$ to write scalar correlators and crossing equations.

[Conformal Frame](/cft-bootstrap/correlation-functions/conformal-frame/) explains the coordinate choice that makes $z$ and $\bar z$ geometrically transparent.

[OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/) and [OPE Convergence](/cft-bootstrap/operator-product-expansion/ope-convergence/) explain why limits such as $z\to 0$ are not merely formal.

[Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) turns OPE limits in cross-ratio space into special functions labeled by exchanged primary dimension and spin.

[Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) upgrades the kinematic permutation rules on this page into bootstrap equations.

## Research status

The existence and use of four-point cross ratios are settled conformal kinematics. The formulas on this page are standard in global conformal field theory in any $d\geq 2$.

Active work concerns what one does with these variables: Lorentzian analytic continuation, Regge and chaos limits, lightcone bootstrap expansions, multi-point conformal integrals, celestial variables, defect cross ratios, and efficient coordinates for numerical conformal blocks.

## Exercises

### Exercise 1: Inversion invariance

Show that

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2}
$$

is invariant under inversion $x^\mu\mapsto x^\mu/x^2$.

<details><summary><strong>Solution</strong></summary>

Under inversion,

$$
x_{ij}^2\mapsto \frac{x_{ij}^2}{x_i^2x_j^2}.
$$

Therefore

$$
u\mapsto
\frac{
\left(x_{12}^2/(x_1^2x_2^2)\right)
\left(x_{34}^2/(x_3^2x_4^2)\right)
}{
\left(x_{13}^2/(x_1^2x_3^2)\right)
\left(x_{24}^2/(x_2^2x_4^2)\right)
}
=u.
$$

The point-dependent factors cancel once for each insertion.

</details>

### Exercise 2: Euclidean domain

Assume $z=x+iy$ and $\bar z=x-iy$. Starting from

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

show that

$$
x=\frac{1+u-v}{2},
\qquad
(1+u-v)^2\leq 4u.
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
u=x^2+y^2,
\qquad
v=(1-x)^2+y^2.
$$

Subtracting gives

$$
u-v=x^2-(1-x)^2=2x-1,
$$

so

$$
x=\frac{1+u-v}{2}.
$$

Since $y^2\geq 0$,

$$
0\leq y^2=u-x^2
=u-\frac{(1+u-v)^2}{4},
$$

which is equivalent to

$$
(1+u-v)^2\leq 4u.
$$

</details>

### Exercise 3: A crossing map

Using the definitions of $u$ and $v$, show that the permutation $x_1\leftrightarrow x_3$ sends

$$
(u,v)\mapsto (v,u).
$$

<details><summary><strong>Solution</strong></summary>

After exchanging $1$ and $3$,

$$
u'=\frac{x_{32}^2x_{14}^2}{x_{31}^2x_{24}^2}
=\frac{x_{23}^2x_{14}^2}{x_{13}^2x_{24}^2}=v,
$$

and

$$
v'=\frac{x_{34}^2x_{21}^2}{x_{31}^2x_{24}^2}
=\frac{x_{34}^2x_{12}^2}{x_{13}^2x_{24}^2}=u.
$$

Thus the exchange maps $(u,v)$ to $(v,u)$.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, chapters 4–6.
- F. A. Dolan and H. Osborn, “Conformal partial waves and the operator product expansion,” *Nuclear Physics B* **678** (2004).
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D at least 3 Dimensions*, sections on conformal kinematics and four-point functions.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, sections on conformal kinematics and crossing.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” sections II–III.

## Version history

- 2026-06-27: First polished draft. Fixed the $u,v,z,\bar z$ conventions, OPE limits, crossing transformations, Euclidean domain, and Lorentzian caveats.
