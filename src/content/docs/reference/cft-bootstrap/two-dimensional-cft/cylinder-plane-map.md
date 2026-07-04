---
title: "Cylinder–Plane Map"
description: "Explains the map between the complex plane and the cylinder in two-dimensional CFT, including primary fields, stress tensors, Casimir energy, and finite-size spectra."
sidebar:
  label: "Cylinder–Plane Map"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Ginsparg 1988; Cardy 1987; Polchinski 1998"
topics:
  - two-dimensional CFT
  - cylinder-plane map
  - radial quantization
  - stress tensor
  - finite-size spectrum
canonicalTopics:
  - cylinder-plane-map-in-two-dimensional-cft
  - conformal-transformation-of-primary-fields
  - schwarzian-derivative-and-cylinder-casimir-energy
  - finite-size-spectrum-of-two-dimensional-cfts
researchStatus:
  established:
    - "The exponential map from the cylinder to the punctured plane is a standard exact conformal map, and the stress-tensor Schwarzian term gives the universal cylinder Casimir shift."
  active:
    - "Spin structures, defects, boundaries, logarithmic modules, nonunitary sectors, and curved-background anomalies require refinements beyond the elementary plane-cylinder dictionary."
---

## Summary

The cylinder–plane map is the basic coordinate change behind radial quantization in two-dimensional CFT. Write

$$
w=\tau+i\sigma,
\qquad
\sigma\sim\sigma+2\pi,
\qquad
z=e^w.
$$

Then the Euclidean cylinder $\mathbb R_\tau\times S^1_\sigma$ maps to the punctured complex plane $\mathbb C^\times$. Constant-$\tau$ circles on the cylinder become circles around the origin in the plane, so cylinder time ordering becomes radial ordering.

For a primary field of weights $(h,\bar h)$,

$$
\phi_{\rm cyl}(w,\bar w)
=
\left({dz\over dw}\right)^h
\left({d\bar z\over d\bar w}\right)^{\bar h}
\phi_{\rm plane}(z,\bar z)
=
z^h\bar z^{\bar h}\phi_{\rm plane}(z,\bar z).
$$

The stress tensor has an extra Schwarzian term. In the convention used here,

$$
T_{\rm cyl}(w)=z^2T_{\rm plane}(z)-{c\over 24},
\qquad
\bar T_{\rm cyl}(\bar w)=\bar z^2\bar T_{\rm plane}(\bar z)-{\bar c\over 24}.
$$

That small-looking $-c/24$ is not a cosmetic correction. It is the universal Casimir energy of a chiral CFT on a circle. It is why the cylinder Hamiltonian is

$$
H_{\rm cyl}=L_0+\bar L_0-{c+\bar c\over 24}
$$

when the circle has circumference $2\pi$.

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), and [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/).

It is useful to have seen the general [Cylinder Picture](/cft-bootstrap/operators-states-radial-quantization/cylinder-picture/) and [State-Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), because this page explains why the two-dimensional version is unusually explicit.

## Core idea

The punctured plane is a cylinder because the logarithm separates a complex number into radius and angle:

$$
z=re^{i\sigma},
\qquad
w=\log z=\log r+i\sigma.
$$

Thus

$$
\tau=\log r,
\qquad
\sigma=\arg z.
$$

The origin of the plane is not a point of the cylinder. It is the infinite past $\tau\to-\infty$. Infinity on the plane is the infinite future $\tau\to+\infty$.

<figure class="doc-figure" style="--figure-width: 48rem;">

![The logarithm maps the punctured complex plane to a Euclidean cylinder.](/figures/cft-bootstrap/cylinder-plane-map-2d.svg)

<figcaption>

The map $w=\log z$ turns circles $|z|=e^\tau$ into constant-time slices on the cylinder. The angular coordinate $\sigma$ is periodic, so the vertical sides of the strip are identified.

</figcaption>
</figure>

This map does three jobs at once. It turns radial quantization into ordinary Euclidean time evolution; it converts local scaling dimensions on the plane into energy eigenvalues on the cylinder; and it makes finite-size physics universal, because a CFT on a circle has energies controlled by $L_0$, $\bar L_0$, and the central charge.

The map is so useful because it trades a local question near $z=0$ for spectral information on a compact spatial circle.

## Setup and conventions

We work in Euclidean signature. The plane coordinates are $z,\bar z$, and the cylinder coordinates are

$$
w=\tau+i\sigma,
\qquad
\bar w=\tau-i\sigma,
\qquad
\sigma\sim\sigma+2\pi.
$$

The map from the cylinder to the plane is

$$
z=e^w,
\qquad
\bar z=e^{\bar w}.
$$

The inverse map is locally

$$
w=\log z,
\qquad
\bar w=\log\bar z.
$$

It is only local because $\log z$ is multivalued. The cylinder remembers this multivaluedness as the periodic identification $\sigma\sim\sigma+2\pi$.

The flat plane metric is

$$
ds^2=dz\,d\bar z.
$$

Using $dz=e^w dw=z\,dw$, one finds

$$
ds^2=e^{w+\bar w}dw\,d\bar w
=e^{2\tau}(d\tau^2+d\sigma^2).
$$

Thus the pullback of the flat plane metric is Weyl equivalent to the flat cylinder metric:

$$
ds^2_{\rm plane}=e^{2\tau}ds^2_{\rm cyl},
\qquad
 ds^2_{\rm cyl}=d\tau^2+d\sigma^2.
$$

A classical conformal theory does not care about this Weyl factor. A quantum CFT cares only through controlled anomaly terms, whose local remnant in the holomorphic stress tensor is the Schwarzian derivative.

## Primary fields on the cylinder

Let $\phi$ be a primary field of weights $(h,\bar h)$. Under a holomorphic coordinate change $z=z(w)$, the cylinder field is defined by

$$
\phi_{\rm cyl}(w,\bar w)
=
\left({dz\over dw}\right)^h
\left({d\bar z\over d\bar w}\right)^{\bar h}
\phi_{\rm plane}(z,\bar z).
$$

For $z=e^w$ this gives

$$
\phi_{\rm cyl}(w,\bar w)
=
e^{hw+\bar h\bar w}\phi_{\rm plane}(e^w,e^{\bar w}).
$$

In terms of dimension and spin,

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h,
$$

this factor is

$$
e^{hw+\bar h\bar w}=e^{\Delta\tau+is\sigma}.
$$

The factor $e^{\Delta\tau}$ is what turns a power-law plane correlator into an exponential cylinder correlator. The factor $e^{is\sigma}$ tracks spin around the circle.

:::note[Field versus coordinate expression]
The symbol $\phi_{\rm cyl}$ denotes the same physical local operator described in cylinder coordinates, including the primary Jacobian factor. If one merely writes $\phi_{\rm plane}(e^w,e^{\bar w})$ without the Jacobian, one is pulling back a scalar function, not transforming a primary field.
:::

## Two-point functions on the cylinder

Suppose a scalar primary is normalized on the plane by

$$
\langle \phi(z_1,\bar z_1)\phi(z_2,\bar z_2)\rangle_{\rm plane}
=
{1\over z_{12}^{2h}\bar z_{12}^{2\bar h}},
\qquad
z_{12}=z_1-z_2.
$$

Transforming both insertions to the cylinder gives

$$
\langle \phi(w_1,\bar w_1)\phi(w_2,\bar w_2)\rangle_{\rm cyl}
=
{e^{h(w_1+w_2)+\bar h(\bar w_1+\bar w_2)}
\over
(e^{w_1}-e^{w_2})^{2h}(e^{\bar w_1}-e^{\bar w_2})^{2\bar h}}.
$$

Using

$$
e^{w_1}-e^{w_2}=e^{(w_1+w_2)/2}2\sinh {w_{12}\over 2},
$$

one obtains

$$
\langle \phi(w_1,\bar w_1)\phi(w_2,\bar w_2)\rangle_{\rm cyl}
=
{1\over
\left(2\sinh {w_{12}\over 2}\right)^{2h}
\left(2\sinh {\bar w_{12}\over 2}\right)^{2\bar h}}.
$$

At equal cylinder time, $w_{12}=i\sigma_{12}$, so the correlator becomes a power of $\sin(\sigma_{12}/2)$. For a spinless primary with $h=\bar h=\Delta/2$,

$$
\langle \phi(\sigma_1)\phi(\sigma_2)\rangle_{\rm cyl}
\propto
{1\over \left|2\sin {\sigma_{12}\over 2}\right|^{2\Delta}},
$$

up to the phase convention implicit in ordering and analytic continuation.

This formula is the simplest bridge between scale-invariant power laws on the plane and finite-size correlators on a circle.

## Stress tensor transformation

The holomorphic stress tensor is not a primary. Under a holomorphic change of coordinate $z=z(w)$ it transforms as

$$
T_{\rm cyl}(w)
=
\left({dz\over dw}\right)^2T_{\rm plane}(z)
+{c\over 12}\{z,w\},
$$

where the Schwarzian derivative is

$$
\{z,w\}
=
{z'''\over z'}-{3\over 2}\left({z''\over z'}\right)^2.
$$

For $z=e^w$,

$$
z'=z,
\qquad
z''=z,
\qquad
z'''=z,
$$

so

$$
\{e^w,w\}=1-{3\over 2}=-{1\over 2}.
$$

Therefore

$$
T_{\rm cyl}(w)=z^2T_{\rm plane}(z)-{c\over 24}.
$$

Similarly,

$$
\bar T_{\rm cyl}(\bar w)=\bar z^2\bar T_{\rm plane}(\bar z)-{\bar c\over 24}.
$$

If the plane vacuum has

$$
\langle T_{\rm plane}\rangle=0,
\qquad
\langle \bar T_{\rm plane}\rangle=0,
$$

then the cylinder vacuum has

$$
\langle T_{\rm cyl}\rangle=-{c\over 24},
\qquad
\langle \bar T_{\rm cyl}\rangle=-{\bar c\over 24}.
$$

This is the cylinder Casimir energy density in CFT normalization. It is universal because it is fixed by the central charge.

## Cylinder Hamiltonian and momentum

On the plane, the Virasoro modes are

$$
L_n={1\over 2\pi i}\oint dz\,z^{n+1}T(z),
\qquad
\bar L_n={1\over 2\pi i}\oint d\bar z\,\bar z^{n+1}\bar T(\bar z).
$$

The cylinder Hamiltonian for circumference $2\pi$ is

$$
H_{\rm cyl}=L_0+\bar L_0-{c+\bar c\over 24},
$$

and the momentum around the circle is

$$
P_{\rm cyl}=L_0-\bar L_0-{c-\bar c\over 24}.
$$

For a parity-invariant CFT with $c=\bar c$,

$$
P_{\rm cyl}=L_0-\bar L_0.
$$

A state created by a primary of weights $(h,\bar h)$ has cylinder energy and momentum

$$
E=h+\bar h-{c+\bar c\over 24},
\qquad
P=h-\bar h-{c-\bar c\over 24}.
$$

A descendant state created by $L_{-n}$ or $\bar L_{-n}$ has energy raised by $n$ in the corresponding chiral sector. Thus a general state in the conformal family has

$$
E=h+N+\bar h+\bar N-{c+\bar c\over 24},
$$

where $N$ and $\bar N$ are nonnegative integers, modulo null-state quotients and degeneracies.

This is the cleanest reason that two-dimensional CFT spectra on a circle are organized by characters.

## General circumference

If the spatial circle has circumference $L$, use

$$
z=\exp\left({2\pi w\over L}\right),
\qquad
w=\tau+i x,
\qquad
x\sim x+L.
$$

Then

$$
H_L={2\pi\over L}\left(L_0+\bar L_0-{c+\bar c\over 24}\right),
$$

and, for $c=\bar c$,

$$
P_L={2\pi\over L}(L_0-\bar L_0).
$$

For a state corresponding to a primary and descendants,

$$
E_L={2\pi\over L}\left(\Delta+N+\bar N-{c+\bar c\over 24}\right).
$$

For a unitary CFT with $c=\bar c$, the ground-state energy on a circle is

$$
E_0(L)=-{\pi c\over 6L}.
$$

This formula is widely used in finite-size scaling: measuring the $1/L$ correction to the ground-state energy gives the central charge.

:::caution[The energy zero is not arbitrary here]
In ordinary quantum mechanics one can often shift the Hamiltonian by a constant without much drama. In 2D CFT on a cylinder, the $-c/12$ shift in $H_{\rm cyl}$ is fixed relative to the plane vacuum by conformal covariance and the Schwarzian derivative. Moving it around without saying so will break modular formulas and finite-size spectra.
:::

## Thermal and spatial cylinders

There are two common cylinders.

A **spatial cylinder** has Euclidean time $\tau\in\mathbb R$ and a spatial circle $x\sim x+L$. This is the geometry used for the Hilbert-space spectrum:

$$
\text{spatial cylinder:}
\qquad
\mathbb R_\tau\times S^1_L.
$$

A **thermal cylinder** has Euclidean time compactified with period $\beta$:

$$
\text{thermal cylinder:}
\qquad
S^1_\beta\times\mathbb R_x.
$$

Locally the formulas are the same after exchanging which coordinate is periodic. Globally they encode different traces. The spatial cylinder gives time evolution on a circle. The thermal cylinder gives a thermal density matrix.

For a primary two-point function on a thermal line with inverse temperature $\beta$, a standard map is

$$
z=\exp\left({2\pi w\over \beta}\right),
\qquad
w=x+i\tau_E,
\qquad
\tau_E\sim\tau_E+\beta.
$$

This yields

$$
\langle \phi(w_1)\phi(w_2)\rangle_\beta
\propto
\left({\pi/\beta\over \sinh {\pi w_{12}\over \beta}}\right)^{2h}
\left({\pi/\beta\over \sinh {\pi \bar w_{12}\over \beta}}\right)^{2\bar h}.
$$

After analytic continuation to Lorentzian time, this formula produces thermal real-time correlators with the expected light-cone singularities and KMS periodicity.

## The map and the state-operator correspondence

The state-operator correspondence says that a local operator at the origin prepares a state on a small circle around the origin:

$$
\mathcal O(0)|0\rangle
\longleftrightarrow
|\mathcal O\rangle.
$$

Under $z=e^w$, the small circle $|z|=e^\tau$ with $\tau\to-\infty$ is an early-time circle on the cylinder. If $\mathcal O$ is a primary of weights $(h,\bar h)$, then

$$
L_0|\mathcal O\rangle=h|\mathcal O\rangle,
\qquad
\bar L_0|\mathcal O\rangle=\bar h|\mathcal O\rangle.
$$

Cylinder time evolution gives

$$
e^{-\tau H_{\rm cyl}}|\mathcal O\rangle
=
e^{-\tau(h+\bar h-(c+\bar c)/24)}|\mathcal O\rangle
$$

for a primary state on a circumference-$2\pi$ cylinder. Descendants add nonnegative integer energy.

This is why the OPE on the plane is a spectral decomposition on the cylinder. Insert two operators, map to the cylinder, and insert a complete set of states between their cylinder times. The resulting sum over states is the conformal-family decomposition of the OPE.

## Vacuum, identity, and Casimir shift

On the plane, the identity operator corresponds to the vacuum state $|0\rangle_{\rm plane}$ with

$$
L_0|0\rangle_{\rm plane}=0,
\qquad
\bar L_0|0\rangle_{\rm plane}=0.
$$

On the cylinder, the same state has energy

$$
E_0=-{c+\bar c\over 24}.
$$

For $c=\bar c$, this is $E_0=-c/12$ on a circle of circumference $2\pi$, or $E_0(L)=-\pi c/(6L)$ on circumference $L$.

This shift is sometimes described as the Casimir energy of the CFT. It is also the reason that torus partition functions are written with

$$
q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24},
$$

not simply $q^{L_0}\bar q^{\bar L_0}$.

## Common pitfalls

**Forgetting the primary Jacobian.** The cylinder field is not generally $\phi(e^w,e^{\bar w})$. It includes the factor $(dz/dw)^h(d\bar z/d\bar w)^{\bar h}$.

**Treating the stress tensor as a primary.** The stress tensor is quasi-primary under global conformal maps, but under a general local conformal map it has a Schwarzian term. The cylinder Casimir energy comes from this term.

**Mixing the two cylinders.** A spatial cylinder and a thermal cylinder are locally related but globally different. One organizes a Hilbert-space spectrum; the other organizes a thermal trace.

**Dropping spin phases.** A field with $s=h-\bar h$ acquires phases under $\sigma\to\sigma+2\pi$. For fermions and spin fields, boundary conditions and spin structures matter.

**Confusing the punctured plane with the whole plane.** The exponential map covers $\mathbb C^\times$, not the origin itself. The origin and infinity become asymptotic ends of the cylinder.

**Ignoring the Weyl anomaly.** For primary fields on flat local patches the Weyl factor is easy to handle. For partition functions, stress tensors, curved backgrounds, and finite-size energies, the anomaly is essential.

## Relations to other pages

[Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/) explains the Hilbert-space interpretation of this map. This page focuses on the coordinate transformation, primary Jacobians, stress-tensor Schwarzian term, and finite-size consequences.

[Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/) introduces $T(z)$, $\bar T(\bar z)$, and the $TT$ OPE. The present page uses the stress-tensor transformation law to derive the cylinder shift.

[Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) uses the same radial/cylinder picture to explain why OPEs are convergent expansions inside correlators.

[Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/) derives the mode algebra generated by $T(z)$ and explains why the cylinder shift is tied to central extension.

[Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) uses the torus partition function built from $q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}$.

## Research status

The elementary cylinder–plane map is completely standard. It is one of the most reliable pieces of the two-dimensional CFT toolkit.

The refinements are not elementary, but they are not optional in advanced applications. Fermions require a choice of spin structure. Compact bosons have zero modes and winding sectors. Defects and boundaries change the Hilbert space. Logarithmic CFTs can make $L_0$ non-diagonal. Nonunitary theories can have unusual vacuum structure. Curved worldsheets and moduli spaces require systematic control of the Weyl anomaly.

For the core graduate path, the safe rule is simple: use the cylinder–plane map for local fields and spectra, but state the global sector whenever the cylinder is used inside a trace.

## Exercises

### Derive the Schwarzian shift

Show that for $z=e^w$,

$$
\{z,w\}=-{1\over 2},
$$

and hence

$$
T_{\rm cyl}(w)=z^2T_{\rm plane}(z)-{c\over 24}.
$$

<details><summary><strong>Solution</strong></summary>

For $z=e^w$,

$$
z'=e^w=z,
\qquad
z''=z,
\qquad
z'''=z.
$$

Therefore

$$
{z'''\over z'}=1,
\qquad
{z''\over z'}=1,
$$

and

$$
\{z,w\}=1-{3\over 2}=-{1\over 2}.
$$

Using

$$
T_{\rm cyl}(w)=\left({dz\over dw}\right)^2T_{\rm plane}(z)+{c\over 12}\{z,w\}
$$

gives

$$
T_{\rm cyl}(w)=z^2T_{\rm plane}(z)-{c\over 24}.
$$

</details>

### Map a plane two-point function

Assume

$$
\langle \phi(z_1,\bar z_1)\phi(z_2,\bar z_2)\rangle
={1\over z_{12}^{2h}\bar z_{12}^{2\bar h}}.
$$

Use $z=e^w$ to show that

$$
\langle \phi(w_1,\bar w_1)\phi(w_2,\bar w_2)\rangle_{\rm cyl}
=
{1\over
\left(2\sinh {w_{12}\over 2}\right)^{2h}
\left(2\sinh {\bar w_{12}\over 2}\right)^{2\bar h}}.
$$

<details><summary><strong>Solution</strong></summary>

A primary field transforms as

$$
\phi_{\rm cyl}(w,\bar w)=e^{hw+\bar h\bar w}\phi_{\rm plane}(e^w,e^{\bar w}).
$$

Thus

$$
\langle \phi_1\phi_2\rangle_{\rm cyl}
=
{e^{h(w_1+w_2)+\bar h(\bar w_1+\bar w_2)}
\over
(e^{w_1}-e^{w_2})^{2h}(e^{\bar w_1}-e^{\bar w_2})^{2\bar h}}.
$$

Since

$$
e^{w_1}-e^{w_2}=e^{(w_1+w_2)/2}2\sinh {w_{12}\over 2},
$$

the exponential factors cancel, leaving the stated formula.

</details>

### Restore the circumference

Starting from the circumference-$2\pi$ Hamiltonian,

$$
H=L_0+\bar L_0-{c+\bar c\over 24},
$$

show that for a spatial circle of circumference $L$,

$$
H_L={2\pi\over L}\left(L_0+\bar L_0-{c+\bar c\over 24}\right).
$$

<details><summary><strong>Solution</strong></summary>

Use the map

$$
z=\exp\left({2\pi w\over L}\right),
\qquad
w=\tau+ix,
\qquad
x\sim x+L.
$$

A translation by $\tau$ on the physical cylinder corresponds to a translation by $2\pi\tau/L$ on the dimensionless cylinder. Therefore the generator scales by $2\pi/L$:

$$
H_L={2\pi\over L}H_{2\pi}
={2\pi\over L}\left(L_0+\bar L_0-{c+\bar c\over 24}\right).
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the operator formalism, conformal mappings, cylinder quantization, and modular-invariance chapters.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, for a compact and practical account of the plane, cylinder, Virasoro modes, and finite-size scaling.
- J. Cardy, *Conformal Invariance and Statistical Mechanics*, for the finite-size and statistical-physics interpretation of the cylinder.
- P. G. O. Freund, *Introduction to Supersymmetry* and standard string-theory references for related cylinder-worldsheet conventions.
- J. Polchinski, *String Theory*, Vol. 1, for the worldsheet version of the plane-cylinder map, normal ordering, and stress-tensor transformation.

## Version history

- 2026-06-28: First polished draft. Fixes the cylinder–plane map, primary-field transformation law, stress-tensor Schwarzian shift, cylinder Hamiltonian, finite-size spectrum, and common global caveats.
