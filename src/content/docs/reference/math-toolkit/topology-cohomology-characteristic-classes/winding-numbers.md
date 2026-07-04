---
title: "Winding Numbers"
description: "Explains winding numbers as integer-valued topological charges for maps into circles, spheres, and compact groups, with applications to vortices, kinks, flux quantization, and large gauge transformations."
sidebar:
  label: "Winding Numbers"
  order: 3
level: Advanced
status: "Polished draft"
source: "Standard topology and field-theory references, including Nakahara, Frankel, Coleman, Polyakov, Weinberg, Schwartz, and soliton/gauge-theory treatments of vortices, kinks, monopoles, and instantons."
topics:
  - winding numbers
  - degree
  - homotopy
  - cohomology
  - vortices
  - kinks
  - flux quantization
  - large gauge transformations
  - topological charge
canonicalTopics:
  - winding-number
  - degree-of-a-map
  - topological-charge
  - vortex
  - kink
  - flux-quantization
  - large-gauge-transformation
  - instanton-number
researchStatus:
  established:
    - "Winding numbers are standard integer-valued homotopy and cohomology invariants for maps such as $S^1\to S^1$, $S^d\to S^d$, and $S^3\to SU(N)$, and they label many classical topological sectors in field theory."
  active:
    - "In full quantum gauge theories, naive winding labels can be refined by global form of the gauge group, allowed line operators, defects, anomalies, torsion, cobordism, and generalized symmetry data."
---

## Summary

A winding number counts how many times one space wraps around another. The simplest case is a map

$$
f:S^1\to S^1.
$$

If $f(e^{i\theta})=e^{in\theta}$, the winding number is $n$. More invariantly,

$$
\operatorname{wind}(f)=\frac{1}{2\pi i}\oint_{S^1} f^{-1}df
=\frac{1}{2\pi}\oint_{S^1}d\varphi,
$$

where locally $f=e^{i\varphi}$.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Diagram showing a map from a domain circle to a target circle, pullback of the angle form, the winding integral, the homotopy class, and QFT interpretations.](/figures/math-toolkit/winding-number-map.svg)

<figcaption>

A winding number is the period of a pulled-back angular form. For $f:S^1_x\to S^1_\phi$, the integer $n=(2\pi)^{-1}\oint d\varphi$ is both a homotopy class in $\pi_1(S^1)$ and a normalized cohomology pairing.

</figcaption>
</figure>

Winding numbers appear whenever finite-energy boundary conditions turn a field configuration into a map between compact spaces. They label vortices, kinks, sigma-model sectors, large gauge transformations, Chern–Simons shifts, and instanton-related transition functions.

The main warning is that winding is a topological label of a map, not automatically a gauge-invariant observable or a dynamically stable object. Physics still asks which maps are allowed, which are gauge equivalent, and which survive quantum effects.

## Prerequisites

Read [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) for the map-based classification of sectors, and [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for cycles, periods, and the meaning of normalized integral forms.

For the differential-form calculations, read [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For gauge-theory examples, read [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) and [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/).

This page uses the convention that a $U(1)$ covariant derivative with charge $q$ is

$$
D=d-iqA.
$$

With this convention, finite-energy winding of a charged scalar in a Higgs phase gives magnetic flux $\Phi=2\pi n/q$.

## Core idea

A winding number is an integer-valued invariant of a continuous map. The integer cannot change under a continuous deformation unless the map becomes ill-defined, crosses a singularity, or violates the boundary conditions.

For a map $f:S^1\to S^1$, write

$$
f(e^{i\theta})=e^{i\varphi(\theta)}
$$

locally. The angle $\varphi$ itself need not be a single-valued real function on the circle, but its differential is globally meaningful after pulling back the angular form from the target circle. Since $f(2\pi)=f(0)$, the lift satisfies

$$
\varphi(2\pi)-\varphi(0)=2\pi n
$$

for some integer $n$. Thus

$$
n=\frac{1}{2\pi}\int_0^{2\pi}d\theta\,\frac{d\varphi}{d\theta}.
$$

This is the winding number.

The same object can be written without choosing a branch of the angle. Since

$$
f^{-1}df=i\,d\varphi,
$$

one has

$$
n=\frac{1}{2\pi i}\oint f^{-1}df.
$$

The form

$$
\frac{1}{2\pi i}f^{-1}df
$$

is the pullback of the normalized generator of $H^1(S^1;\mathbb Z)$, viewed in de Rham cohomology. The winding number is its period over the domain circle.

## Why the answer is an integer

There are two standard explanations.

The lifting explanation uses the universal cover

$$
\mathbb R\to S^1,
\qquad
\varphi\mapsto e^{i\varphi}.
$$

A map from a parameterized circle into $S^1$ can be lifted to a continuous function $\varphi$ on the interval $[0,2\pi]$. Since the endpoints represent the same point of the domain circle, the target values must agree in $S^1$:

$$
e^{i\varphi(2\pi)}=e^{i\varphi(0)}.
$$

Therefore

$$
\varphi(2\pi)-\varphi(0)=2\pi n,
\qquad n\in\mathbb Z.
$$

The cohomology explanation says that $d\phi/2\pi$ is the normalized generator of $H^1(S^1;\mathbb Z)$ in real form language. Pulling it back to the domain circle and integrating over the fundamental cycle gives an integer:

$$
\int_{S^1} f^\ast\left(\frac{d\phi}{2\pi}\right)\in\mathbb Z.
$$

Same answer, different mood lighting.

## Homotopy invariance

Let

$$
f_t:S^1\to S^1,
\qquad t\in[0,1],
$$

be a continuous family of smooth maps. If the maps never become ill-defined, then the winding number is constant in $t$.

One way to see this is to use a local lift $\varphi(\theta,t)$ on the interval. The winding number is

$$
n(t)=\frac{1}{2\pi}\int_0^{2\pi}d\theta\,\partial_\theta\varphi(\theta,t).
$$

Differentiating gives

$$
\frac{dn}{dt}=\frac{1}{2\pi}\int_0^{2\pi}d\theta\,\partial_\theta\partial_t\varphi
=\frac{1}{2\pi}\left[\partial_t\varphi(2\pi,t)-\partial_t\varphi(0,t)\right].
$$

The difference $\varphi(2\pi,t)-\varphi(0,t)$ is $2\pi n(t)$ and cannot vary continuously except by staying constant, because it is restricted to integer multiples of $2\pi$. Thus $dn/dt=0$ between singular events.

Equivalently,

$$
\pi_1(S^1)\simeq\mathbb Z,
$$

and the winding number is the isomorphism from the homotopy class of $f$ to an integer.

## Winding of a complex field around a zero

Suppose $\phi$ is a complex scalar field and $C$ is a closed loop on which

$$
\phi\ne0.
$$

Then $\phi/|\phi|$ defines a map

$$
C\to S^1.
$$

Its winding number is

$$
n_C=\frac{1}{2\pi}\oint_C d\arg\phi
=\frac{1}{2\pi i}\oint_C \frac{d\phi}{\phi}.
$$

This integer counts how many times the image of the loop winds around the origin in the complex $\phi$-plane. If $\phi$ is a holomorphic function of a complex coordinate $z$, this becomes the argument principle: the integral counts zeros minus poles inside the contour, with multiplicity.

For field theory, the important point is simpler. A nonzero winding on $C$ forces $\phi$ to vanish somewhere inside any disk bounded by $C$, unless the field is singular or the disk is not actually available in the space. That zero is the core of a vortex-like defect.

Thus winding detects a defect because the phase map cannot be extended smoothly over the disk while remaining in $S^1$.

## Global vortices

Consider a complex scalar field in two spatial dimensions with vacuum manifold

$$
|\phi|=v.
$$

At large radius, finite energy requires

$$
\phi(r,\theta)\to v e^{i\varphi(\theta)}.
$$

This defines a map

$$
S^1_\infty\to S^1_{\mathrm{vac}}.
$$

A winding-$n$ configuration has asymptotic form

$$
\phi(r,\theta)\sim v e^{in\theta}.
$$

The winding number is

$$
n=\frac{1}{2\pi}\oint_{S^1_\infty}d\arg\phi.
$$

If $n\ne0$, the field cannot remain on the vacuum circle everywhere inside the loop. A smooth configuration must have a core where $|\phi|$ departs from $v$, often passing through $\phi=0$.

For a global $U(1)$ theory in two spatial dimensions, the gradient energy behaves logarithmically at large radius. This is not a failure of the winding number. It is a statement about the dynamics of the massless Goldstone mode.

## Gauge vortices and flux quantization

Now let the $U(1)$ symmetry be gauged and let the scalar have charge $q$:

$$
D\phi=(d-iqA)\phi.
$$

Finite energy at large radius requires

$$
D\phi\to0.
$$

For

$$
\phi\sim v e^{in\theta},
$$

this condition gives

$$
(d-iqA)e^{in\theta}\to0.
$$

Equivalently,

$$
n\,d\theta-qA\to0
$$

along the large circle. Therefore

$$
\oint_{S^1_\infty} A=\frac{2\pi n}{q}.
$$

By Stokes’ theorem, the magnetic flux through the plane is

$$
\Phi_B=\int F=\oint_{S^1_\infty}A=\frac{2\pi n}{q}.
$$

This is the basic flux quantization of the Abelian Higgs vortex in these conventions.

The phase winding of $\phi$ alone is gauge-dependent. A gauge transformation can change the apparent phase winding in a patch. The gauge-invariant statement is the combined topology of the Higgs field, the connection, and the magnetic flux. In a good formulation, the integer is encoded in the line bundle and its first Chern class, or in the transition function at infinity.

## Kinks as one-dimensional winding

Winding numbers also appear in one spatial dimension when the field is periodic. In the sine-Gordon model, the field obeys

$$
\varphi\sim\varphi+2\pi,
$$

and finite-energy configurations approach vacua at spatial infinity. Compactifying the spatial line by adding the point at infinity is equivalent to asking for a map into a circle, or more concretely measuring the difference between endpoints:

$$
Q=\frac{1}{2\pi}\int_{-\infty}^{+\infty}dx\,\partial_x\varphi
=\frac{\varphi(+\infty)-\varphi(-\infty)}{2\pi}.
$$

For a kink, $Q=1$. For an antikink, $Q=-1$.

If the target is not periodic but has disconnected vacua, the word winding is less appropriate. Then the charge is better thought of as a domain-wall or kink sector labeled by components of the vacuum set, i.e. by $\pi_0$ rather than $\pi_1$.

## Higher-dimensional winding and degree

The circle example generalizes. A smooth map

$$
n:S^d\to S^d
$$

has an integer degree. In coordinates, if $\omega_{S^d}$ is the normalized volume form on the target sphere,

$$
\int_{S^d}\omega_{S^d}=1,
$$

then

$$
\deg(n)=\int_{S^d} n^\ast\omega_{S^d}\in\mathbb Z.
$$

For $d=2$, writing $n:S^2\to S^2$ as a unit vector field $n^a$ with $a=1,2,3$, this becomes

$$
\deg(n)=\frac{1}{4\pi}\int_{S^2} n\cdot(\partial_\theta n\times\partial_\varphi n)\,d\theta\,d\varphi.
$$

This formula appears in monopoles, sigma-model lumps, skyrmion-like textures, and Berry-curvature calculations. The details depend on which sphere is the domain, which sphere is the target, and how the physical field is normalized.

The future Degree of a Map page will treat this higher-dimensional version systematically. For now, the important point is that winding is not only a one-dimensional idea. It is the low-dimensional face of degree theory.

## Group-valued winding and large gauge transformations

Compact Lie groups have their own winding numbers. For many QFT applications, the key fact is

$$
\pi_3(SU(N))\simeq\mathbb Z,
\qquad N\ge2.
$$

A smooth map

$$
g:S^3\to SU(N)
$$

has winding number

$$
\nu(g)=\frac{1}{24\pi^2}\int_{S^3}\operatorname{tr}\left(g^{-1}dg\right)^3,
$$

with the trace normalization chosen so that this integral is an integer. Some authors include a minus sign or use anti-Hermitian generators; always check the convention.

This integer appears in four-dimensional Yang–Mills theory because gauge transformations at spatial infinity can be maps from $S^3$ into the gauge group. A gauge transformation with nonzero $\nu(g)$ is called a large gauge transformation. It cannot be continuously deformed to the identity.

The same integer controls the shift of Chern–Simons functionals under large gauge transformations. Schematically,

$$
\operatorname{CS}(A^g)=\operatorname{CS}(A)+2\pi\,\nu(g)
$$

in a normalization where the exponentiated action is invariant when the Chern–Simons level is integral. This is one of the cleanest places where topology, quantization, and path-integral phases meet.

## Instanton number as winding at infinity

For an $SU(N)$ gauge field on Euclidean $\mathbb R^4$, finite action requires the field strength to decay at infinity. The connection approaches a pure gauge on the sphere at infinity:

$$
A\to g^{-1}dg
$$

up to convention-dependent signs and factors. The sphere at infinity is $S^3$, so the asymptotic gauge function defines

$$
g:S^3_\infty\to SU(N).
$$

Its winding number labels the instanton sector. In curvature language, the same integer is represented by the second Chern number,

$$
Q=\frac{1}{8\pi^2}\int_{\mathbb R^4}\operatorname{tr}(F\wedge F),
$$

again with trace conventions chosen so that $Q\in\mathbb Z$ for appropriate bundles.

This is a recurring pattern:

$$
\text{winding of transition functions}
\quad\Longleftrightarrow\quad
\text{integral of characteristic forms}.
$$

The homotopy page sees the transition function. The cohomology and characteristic-class pages see the curvature representative.

## Winding currents

In many models, winding number can be written as the integral of an identically conserved topological current. For the sine-Gordon field in $1+1$ dimensions,

$$
j^\mu_{\mathrm{top}}=\frac{1}{2\pi}\epsilon^{\mu\nu}\partial_\nu\varphi.
$$

It is conserved identically:

$$
\partial_\mu j^\mu_{\mathrm{top}}
=\frac{1}{2\pi}\epsilon^{\mu\nu}\partial_\mu\partial_\nu\varphi=0,
$$

assuming $\varphi$ is smooth. The charge is

$$
Q=\int dx\,j^0_{\mathrm{top}}
=\frac{1}{2\pi}\int dx\,\partial_x\varphi.
$$

For a map $n:S^2\to S^2$, the corresponding topological density is proportional to

$$
\epsilon^{ij} n\cdot(\partial_i n\times\partial_j n).
$$

These currents are “topological” because their conservation follows from antisymmetry and smoothness rather than from an Euler–Lagrange equation. Singularities, boundaries, and defects can violate the naive conservation law by allowing winding to enter or leave the region.

## Branch cuts, singularities, and undefined winding

The formula

$$
\frac{1}{2\pi}\oint d\arg\phi
$$

only makes sense if $\phi\ne0$ on the loop. If the loop crosses a zero of $\phi$, the phase is undefined and the winding number of that loop is not defined.

Similarly, a choice of branch cut for $\arg\phi$ is not physical. The phase angle is local data; $d\arg\phi$ and its integral around a closed loop are the invariant data when the map to $S^1$ is well defined.

A winding number can change in time only if something singular happens in spacetime, or if winding flows through a boundary. For example, a vortex–antivortex pair can annihilate because the total winding at infinity is zero. A single vortex cannot simply disappear in a closed system without the field leaving the vacuum manifold somewhere or changing the boundary conditions.

## Gauge dependence and physical winding

In a global symmetry model, the phase of $\phi$ is a physical field coordinate. In a gauge theory, the phase of a charged scalar is partly gauge. Therefore one must be more careful.

A local gauge transformation

$$
\phi\mapsto e^{iq\alpha}\phi,
\qquad
A\mapsto A+d\alpha
$$

can move winding between the scalar phase and the gauge potential. The gauge-invariant information is encoded in holonomy, flux, transition functions, and bundle topology.

This is why the Abelian Higgs vortex is not merely “a scalar winds.” It is a configuration where the scalar, gauge field, and line bundle fit together so that the flux is quantized. The scalar phase is the intuitive picture; the bundle is the invariant object. The bundle is less cuddly, but it pays rent.

## Common examples in QFT

| System | Map or class | Winding formula or label |
|---|---|---|
| Broken global $U(1)$ vortex | $S^1_\infty\to S^1$ | $n=(2\pi)^{-1}\oint d\arg\phi$ |
| Abelian Higgs vortex | line bundle over compactified space | $\int F=2\pi n/q$ |
| Sine-Gordon kink | endpoints in periodic target | $Q=(2\pi)^{-1}\int dx\,\partial_x\varphi$ |
| Sigma-model lump | $S^2\to S^2$ | $\deg(n)=(4\pi)^{-1}\int n\cdot(\partial n\times\partial n)$ |
| Large gauge transformation | $S^3\to SU(N)$ | $\nu(g)=(24\pi^2)^{-1}\int\operatorname{tr}(g^{-1}dg)^3$ |
| Yang–Mills instanton | bundle over $S^4$ or boundary map $S^3\to G$ | $Q=(8\pi^2)^{-1}\int\operatorname{tr}(F\wedge F)$ |

Every entry in the table has convention-dependent normalizations. The invariant statement is that the expression is normalized to give an integer on the generator of the relevant homotopy or cohomology group.

## Common pitfalls

Winding is not the same as angular momentum. A field can wind in internal target space even if nothing is physically rotating in ordinary space.

A nonzero winding number requires the map to be defined on the whole cycle. If the field vanishes on the loop, or if the target coordinate is singular there, the winding integral is not defined.

A phase winding in a gauge theory is not automatically gauge invariant. The physical invariant is usually flux, holonomy, transition-function winding, or a characteristic class.

The integer depends on normalization. Missing a factor of $2\pi$, $q$, $4\pi$, $8\pi^2$, or $24\pi^2$ is not a cosmetic error; it changes whether the answer is actually integral.

Homotopy classification is not dynamical stability. A topological sector can exist while a finite-energy soliton does not, or while the configuration is unstable after additional fields and interactions are included.

## Exercises

### Exercise 1: Winding of the standard map

Let

$$
f_n(e^{i\theta})=e^{in\theta}
$$

with $n\in\mathbb Z$. Compute

$$
\frac{1}{2\pi i}\oint_{S^1} f_n^{-1}df_n.
$$

<details><summary><strong>Solution</strong></summary>

We have

$$
df_n=i n e^{in\theta}d\theta,
\qquad
f_n^{-1}df_n=e^{-in\theta}i n e^{in\theta}d\theta=i n\,d\theta.
$$

Therefore

$$
\frac{1}{2\pi i}\oint f_n^{-1}df_n
=\frac{1}{2\pi i}\int_0^{2\pi} i n\,d\theta
=n.
$$

</details>

### Exercise 2: Homotopy invariance of circle winding

Let $f_t:S^1\to S^1$ be a smooth one-parameter family of maps. Assume a smooth lift $\varphi(\theta,t)$ exists on $[0,2\pi]$ for each $t$, with

$$
f_t(e^{i\theta})=e^{i\varphi(\theta,t)}.
$$

Show that the winding number cannot vary continuously with $t$.

<details><summary><strong>Solution</strong></summary>

The winding number is

$$
n(t)=\frac{\varphi(2\pi,t)-\varphi(0,t)}{2\pi}.
$$

Because $e^{i\varphi(2\pi,t)}=e^{i\varphi(0,t)}$, the numerator must be an integer multiple of $2\pi$:

$$
n(t)\in\mathbb Z.
$$

The family is continuous, so $n(t)$ is a continuous function from a connected interval to $\mathbb Z$. The only continuous such functions are constant. Therefore the winding number cannot change under a smooth homotopy.

</details>

### Exercise 3: Flux of an Abelian Higgs vortex

Use the convention

$$
D=d-iqA.
$$

Suppose that at large radius

$$
\phi\sim v e^{in\theta}
$$

and finite energy requires $D\phi\to0$. Show that the magnetic flux is

$$
\Phi_B=\frac{2\pi n}{q}.
$$

<details><summary><strong>Solution</strong></summary>

At large radius,

$$
D\phi=(d-iqA)(v e^{in\theta})
=iv e^{in\theta}(n\,d\theta-qA).
$$

The condition $D\phi\to0$ gives

$$
qA\to n\,d\theta
$$

along the circle at infinity. Therefore

$$
\oint A=\frac{n}{q}\oint d\theta=\frac{2\pi n}{q}.
$$

By Stokes’ theorem, the magnetic flux is

$$
\Phi_B=\int F=\oint A=\frac{2\pi n}{q}.
$$

</details>

### Exercise 4: A zero inside a loop

Let

$$
\phi(z)=(z-a)^m
$$

with $m$ a positive integer. Let $C$ be a counterclockwise circle centered at the origin, and assume $a$ lies inside $C$. Compute

$$
\frac{1}{2\pi i}\oint_C \frac{d\phi}{\phi}.
$$

<details><summary><strong>Solution</strong></summary>

Since

$$
\phi(z)=(z-a)^m,
$$

we have

$$
\frac{d\phi}{\phi}=m\frac{dz}{z-a}.
$$

Therefore

$$
\frac{1}{2\pi i}\oint_C\frac{d\phi}{\phi}
=\frac{m}{2\pi i}\oint_C\frac{dz}{z-a}.
$$

Because $a$ lies inside $C$ and $C$ is counterclockwise,

$$
\oint_C\frac{dz}{z-a}=2\pi i.
$$

Thus the winding number is

$$
m.
$$

The multiplicity of the zero is the winding of the phase of $\phi$ around the loop.

</details>

## Relations to other pages

This page uses [Homotopy Groups](/math-toolkit/topology-cohomology-characteristic-classes/homotopy-groups/) for the classification $\pi_1(S^1)\simeq\mathbb Z$ and uses [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for the period pairing interpretation of winding integrals.

For the differential-form background, see [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/). For gauge fields and flux quantization, see [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/).

The next natural topics are Degree of a Map, de Rham Cohomology, Characteristic Classes, Chern Classes, and Index Theorems. Those pages generalize the winding-number idea from circles to higher-dimensional cycles, bundles, curvature polynomials, and fermion zero modes.

## Research status

The basic winding numbers described here are established. The subtlety in modern QFT is deciding what the integer labels after all physical equivalences and quantum effects are included. Gauge redundancy, global form of the gauge group, allowed defects, background fields, boundary conditions, anomaly inflow, and generalized symmetries can all refine the naive winding classification.

A safe workflow is: compute the winding of the classical map, identify the gauge-invariant object that carries it, normalize the corresponding cohomology class integrally, and then check whether quantum effects identify, weight, or obstruct the sectors.

## References

- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented discussion of homotopy, winding, monopoles, instantons, gauge bundles, and characteristic classes.
- T. Frankel, *The Geometry of Physics*. Useful for geometric interpretations of degree, forms, bundles, gauge fields, and topological charges.
- S. Coleman, *Aspects of Symmetry*. Classic discussion of solitons, kinks, topological conservation laws, and field-theory sectors.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for vortices, compact gauge fields, monopoles, instantons, and topological effects in QFT.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I and II. Useful for gauge transformations, instantons, anomalies, and QFT conventions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for gauge theory, anomalies, instantons, and the relation between topology and QFT calculations.
- N. Manton and P. Sutcliffe, *Topological Solitons*. Detailed reference for solitons, degree, vortices, monopoles, Skyrmions, and related winding numbers.

## Version history

- **2026-06-25:** Initial polished draft. Explained $S^1\to S^1$ winding, integrality, homotopy invariance, winding around zeros, global and gauge vortices, kink charge, higher-dimensional degree, group-valued winding, instanton number, topological currents, and common pitfalls.
