---
title: "Conformal Anomaly in 2D"
description: "Explains the two-dimensional conformal anomaly, its relation to the central charge, the Schwarzian derivative, the Polyakov action, and cylinder vacuum energy."
sidebar:
  label: "Conformal Anomaly in 2D"
  order: 10
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997, Ch. 5; Polyakov 1981; Ginsparg 1988; Cardy 1986"
topics:
  - conformal anomaly
  - Weyl anomaly
  - trace anomaly
  - central charge
  - Schwarzian derivative
  - Polyakov action
canonicalTopics:
  - two-dimensional-conformal-anomaly
  - central-charge
  - trace-anomaly
researchStatus:
  established:
    - "The two-dimensional Weyl anomaly is an exact quantum statement controlled by the central charge of the CFT."
    - "The same central charge appears in the stress-tensor OPE, Virasoro central term, Schwarzian transformation, and cylinder vacuum energy."
  active:
    - "The anomaly viewpoint remains central in modern work on entanglement, boundaries, defects, gravitational anomalies, and nonsemisimple or nonunitary theories."
---

## Summary

A classical two-dimensional conformal field theory has a traceless stress tensor,

$$
T^a{}_{a}=0,
$$

but quantization on a curved background generally produces a Weyl anomaly. With the physical stress-tensor normalization fixed below, a nonchiral CFT with $c_L=c_R=c$ obeys

$$
\langle T^a{}_{a}\rangle_{\mathrm{phys}}=-\frac{c}{24\pi}R.
$$

More generally,

$$
\langle T^a{}_{a}\rangle_{\mathrm{phys}}=-\frac{c_L+c_R}{48\pi}R.
$$

The coefficient is the central charge $c$ that also appears in the holomorphic stress-tensor OPE

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

This is one of the best pieces of bookkeeping in all of two-dimensional CFT: the same number $c$ controls the $TT$ OPE, the trace anomaly, the Schwarzian transformation of $T$, the cylinder vacuum energy, the Cardy density of states, and many finite-size effects.

The anomaly is not a small breaking caused by an imperfect regulator. It is an unavoidable quantum effect once the theory has nonzero central charge and is coupled to a background metric. In flat space, holomorphic conformal symmetry remains powerful; on curved surfaces, the anomaly tells us exactly how the partition function responds to changes of scale.

## Prerequisites

You should know [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/), [Central Charge](/cft-bootstrap/virasoro-central-charge/central-charge/), [Stress Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/), and [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/).

Readers who want the geometric background should know what a Weyl rescaling is:

$$
g_{ab}\mapsto e^{2\sigma(x)}g_{ab}.
$$

No detailed differential geometry is needed beyond the scalar curvature $R$ and the fact that in two dimensions every metric is locally conformally flat.

## Core idea

Classically, conformal invariance means invariance under local rescalings of the metric. If the theory is coupled to a background metric $g_{ab}$, the generating functional should satisfy

$$
Z[e^{2\sigma}g]=Z[g].
$$

Equivalently, the stress tensor should be traceless:

$$
T^a{}_{a}=0.
$$

Quantum mechanically this can fail even when local correlation functions on the plane still obey conformal Ward identities. The functional integral measure cannot always be chosen to preserve Weyl invariance. For a nonchiral CFT with $c_L=c_R=c$, the resulting anomaly is local and universal:

$$
\langle T^a{}_{a}\rangle_{\mathrm{phys}}=-\frac{c}{24\pi}R.
$$

For independent chiral central charges, replace $c$ by $(c_L+c_R)/2$ in this Weyl-anomaly formula.

The phrase “conformal anomaly” is slightly treacherous. In flat space, where $R=0$, there is no trace anomaly in ordinary separated-point correlators. The anomaly reveals itself when the theory is placed on curved space, when coordinates are changed nontrivially, or when one compares the plane and the cylinder.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A dictionary relating flat-space central charge, Weyl curvature response, Schwarzian transformation, and cylinder vacuum energy.](/figures/cft-bootstrap/two-dimensional-conformal-anomaly.svg)

<figcaption>

The same central charge $c$ appears as the fourth-order pole in the $TT$ OPE, the Virasoro central term, the curved-space Weyl anomaly, the Schwarzian shift of $T$, and the cylinder vacuum energy.

</figcaption>
</figure>

## Setup and conventions

There are two stress-tensor normalizations in common use.

The holomorphic CFT-normalized stress tensor $T(z)$ is the one appearing in the OPE

$$
T(z)T(w)
\sim
\frac{c/2}{(z-w)^4}
+
\frac{2T(w)}{(z-w)^2}
+
\frac{\partial T(w)}{z-w}.
$$

The physical metric stress tensor is defined from the Euclidean generating functional

$$
W[g]\equiv -\log Z[g]
$$

by

$$
\delta W[g]
=\frac12\int d^2x\sqrt g\,\langle T^{\mathrm{phys}}_{ab}\rangle\delta g^{ab}.
$$

For an infinitesimal Weyl rescaling $g_{ab}\to e^{2\delta\sigma}g_{ab}$,

$$
\delta g^{ab}=-2\delta\sigma\,g^{ab},
$$

so

$$
\delta_\sigma W[g]
=-\int d^2x\sqrt g\,\delta\sigma\,\langle T^a{}_{a}\rangle_{\mathrm{phys}}.
$$

With this convention, the Weyl anomaly for a nonchiral theory is

$$
\delta_\sigma W[g]
=\frac{c}{24\pi}\int d^2x\sqrt g\,\delta\sigma R,
$$

or equivalently

$$
\langle T^a{}_{a}\rangle_{\mathrm{phys}}=-\frac{c}{24\pi}R.
$$

For a chiral theory, the Weyl anomaly uses $(c_L+c_R)/2$ in place of $c$. The difference $c_L-c_R$ controls the gravitational anomaly rather than the Weyl anomaly.

Different books may use $\log Z$ instead of $W=-\log Z$, or may define the stress tensor with different factors of $2\pi$. The invariant content is the coefficient of the Weyl response; once the convention above is fixed, the signs and $24\pi$ are not negotiable.

## The trace anomaly

In flat complex coordinates, conservation and tracelessness imply

$$
\bar\partial T(z)=0,
\qquad
\partial \bar T(\bar z)=0,
$$

away from insertions. On a curved background, the trace is no longer zero. The anomaly says

$$
\langle T^a{}_{a}\rangle_{\mathrm{phys}}=-\frac{c}{24\pi}R.
$$

This formula has several important features.

First, the anomaly is proportional to curvature. On the flat plane, $R=0$, so separated-point flat-space correlators still look conformal.

Second, it is proportional to $c$. A tensor product of two CFTs has central charge

$$
c=c_1+c_2,
$$

and the anomaly adds accordingly.

Third, it is local. The response to an infinitesimal Weyl transformation is the integral of a local curvature scalar. This is why $c$ is a robust observable.

Fourth, it is universal up to convention. Local counterterms may shift some scheme-dependent curvature contact terms in more complicated settings, but the coefficient of the two-dimensional Weyl anomaly is fixed.

## Finite Weyl transformations

Let

$$
g_{ab}=e^{2\sigma}\hat g_{ab}.
$$

In our $W=-\log Z$ convention, the anomaly integrates to the Liouville-type functional

$$
W[e^{2\sigma}\hat g]-W[\hat g]
=\frac{c}{24\pi}\int d^2x\sqrt{\hat g}
\left(
\hat g^{ab}\partial_a\sigma\partial_b\sigma+\hat R\sigma
\right)
$$

up to Weyl-invariant and topological terms. This expression is often the most practical way to compute how a CFT partition function changes under a Weyl rescaling.

The corresponding nonlocal metric functional is the Polyakov action. In common conventions it is written schematically as

$$
W_{\mathrm{anom}}[g]
\propto
\int d^2x\sqrt g\,R\frac{1}{\Box}R,
$$

with the overall sign depending on whether one writes $W$ or $\log Z$. The key point is not the sign in isolation; it is that no local Weyl-invariant action can reproduce the anomaly. The inverse Laplacian is the footprint of integrating out massless degrees of freedom.

## Schwarzian derivative

The same anomaly appears when one asks how the stress tensor changes under a finite holomorphic coordinate map $z=z(w)$. In the convention of these pages,

$$
T_{ww}(w)
=\left(\frac{dz}{dw}\right)^2T_{zz}(z(w))
+\frac{c}{12}\{z,w\},
$$

where

$$
\{z,w\}
=
\frac{z^{(3)}(w)}{z'(w)}
-\frac32\left(\frac{z^{(2)}(w)}{z'(w)}\right)^2
$$

is the Schwarzian derivative.

If $T$ were a primary field of weight two, the first term would be the whole answer. The Schwarzian term is the anomaly. It vanishes for Möbius transformations, so $T$ is still quasiprimary under the global conformal group.

For the plane-to-cylinder map

$$
z=e^w,
\qquad
w=\tau+i\theta,
$$

we have

$$
\{e^w,w\}=-\frac12.
$$

Therefore

$$
T_{\mathrm{cyl}}(w)=z^2T_{\mathrm{plane}}(z)-\frac{c}{24}.
$$

This is the origin of the cylinder vacuum-energy shift.

## Cylinder vacuum energy

On a unit-radius cylinder, the Hamiltonian and momentum are

$$
H=L_0+\bar L_0-\frac{c+\bar c}{24},
$$

and

$$
P=L_0-\bar L_0-\frac{c-\bar c}{24}.
$$

For a parity-invariant CFT with $c=\bar c$, the vacuum has

$$
E_0=-\frac{c}{12}.
$$

On a spatial circle of circumference $L$ and velocity $v$, the universal finite-size correction becomes

$$
E_0(L)=e_\infty L-\frac{\pi v c}{6L}+o(L^{-1}),
$$

where $e_\infty$ is a nonuniversal bulk energy density. This formula is widely used to identify the central charge of a critical lattice model from finite-size spectra.

## Weyl anomaly versus gravitational anomaly

The Weyl anomaly is controlled by the sum of left and right central charges. The gravitational anomaly is controlled by their difference.

For a nonchiral theory with $c=\bar c$, there is a Weyl anomaly on curved backgrounds but no gravitational anomaly. For a chiral theory with $c\ne\bar c$, orientation-preserving diffeomorphism invariance itself can be anomalous unless the chiral imbalance is canceled by other sectors.

This distinction is crucial in string theory and chiral edge theories. It is also why one must be careful with phrases like “the central charge of the theory”: sometimes the relevant coefficient is $c+\bar c$, sometimes $c-\bar c$, and sometimes the holomorphic $c$ alone.

## Examples

For a free boson,

$$
c=1.
$$

For a free Majorana fermion,

$$
c=\frac12.
$$

For $N$ free Majorana fermions,

$$
c=\frac N2.
$$

For a $bc$ ghost system with weights $(\lambda,1-\lambda)$,

$$
c=1-3(2\lambda-1)^2.
$$

In the bosonic string, the reparametrization ghosts have $\lambda=2$, hence $c_{bc}=-26$. The cancellation of this ghost central charge by $D$ free coordinate bosons is the usual route to the critical dimension $D=26$.

## Common pitfalls

**Thinking the anomaly means flat-space conformal symmetry failed.** It did not. The anomaly is a curved-background Weyl response and a coordinate-transformation effect. On the plane, $R=0$.

**Forgetting which stress tensor is being normalized.** The $T(z)T(w)$ OPE and the physical trace anomaly use different normalizations unless a page explicitly relates them.

**Confusing $c$ with $c+\bar c$.** Holomorphic formulas use $c$. Nonchiral finite-size and Weyl-anomaly formulas often depend on both sectors.

**Dropping the Schwarzian term.** The Schwarzian is not optional. It is fixed by the Virasoro central extension.

**Trying to remove the anomaly with a local counterterm.** In two dimensions, $\int\sqrt g R$ is topological. It cannot cancel the local Weyl anomaly.

## Relations to other pages

This page completes the Virasoro chapter's central-charge thread. [Stress Tensor OPE](/cft-bootstrap/virasoro-central-charge/stress-tensor-ope/) introduces the fourth-order pole. [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/) turns it into a central term in the algebra. [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) turns it into an anomalous transformation law. This page explains its curved-space meaning.

It also connects to [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/), [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/), [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/), and the later [Modular Bootstrap](/cft-bootstrap/modular-bootstrap/) chapter.

The general anomaly theory belongs in the Symmetry, Anomalies, and Topology volume. This page is the CFT-facing account of the two-dimensional Weyl anomaly and its central-charge normalization.

## Research status

The Weyl anomaly, Schwarzian transformation law, Polyakov action, and cylinder Casimir energy are established, exact pieces of two-dimensional CFT.

Advanced settings require more care: chiral CFTs and gravitational anomalies, theories with boundaries or defects, logarithmic CFTs, noncompact CFTs, nonunitary models, topological sectors, and coupling to dynamical gravity. The central lesson survives: anomaly coefficients are part of the exact universal data of the theory.

## Exercises

### Exercise: Schwarzian for the exponential map

Show that $z=e^w$ has Schwarzian derivative $\{z,w\}=-1/2$, and derive the cylinder shift.

<details>
<summary><strong>Solution</strong></summary>

For $z=e^w$,

$$
z'=z,
\qquad
z^{(2)}=z,
\qquad
z^{(3)}=z.
$$

Therefore

$$
\{z,w\}=\frac{z^{(3)}}{z'}-\frac32\left(\frac{z^{(2)}}{z'}\right)^2
=1-\frac32=-\frac12.
$$

The finite transformation law gives

$$
T_{\mathrm{cyl}}(w)=z^2T_{\mathrm{plane}}(z)+\frac{c}{12}\{e^w,w\}
=z^2T_{\mathrm{plane}}(z)-\frac{c}{24}.
$$

</details>

### Exercise: Trace anomaly from Weyl variation

Use

$$
\delta_\sigma W[g]
=\frac{c}{24\pi}\int d^2x\sqrt g\,\delta\sigma R
$$

and

$$
\delta_\sigma W[g]
=-\int d^2x\sqrt g\,\delta\sigma\langle T^a{}_a\rangle_{\mathrm{phys}}
$$

to derive the trace anomaly.

<details>
<summary><strong>Solution</strong></summary>

Since $\delta\sigma(x)$ is arbitrary, equate the integrands:

$$
-\langle T^a{}_a\rangle_{\mathrm{phys}}=\frac{c}{24\pi}R.
$$

Thus

$$
\langle T^a{}_a\rangle_{\mathrm{phys}}=-\frac{c}{24\pi}R.
$$

</details>

### Exercise: Central charge from finite-size energy

A critical quantum chain has velocity $v$ and ground-state energy

$$
E_0(L)=e_\infty L-\frac{\pi v}{12L}+o(L^{-1}).
$$

Assuming a nonchiral CFT with $c=\bar c$, determine $c$.

<details>
<summary><strong>Solution</strong></summary>

Compare with

$$
E_0(L)=e_\infty L-\frac{\pi v c}{6L}+o(L^{-1}).
$$

The coefficient gives

$$
\frac{c}{6}=\frac{1}{12},
$$

so

$$
c=\frac12.
$$

This is the central charge of the Ising/Majorana universality class.

</details>

## References

- A. M. Polyakov, “Quantum geometry of bosonic strings,” *Physics Letters B* **103** (1981).
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* **241** (1984).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Ch. 5.
- J. L. Cardy, “Effect of boundary conditions on the operator content of two-dimensional conformally invariant theories,” *Nuclear Physics B* **275** (1986).
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- J. Polchinski, *String Theory*, Vol. 1, Ch. 2.

## Version history

- 2026-06-28: First polished draft. Explained the Weyl anomaly, stress-tensor normalizations, Schwarzian transformation, Polyakov action, cylinder vacuum energy, gravitational-anomaly distinction, examples, pitfalls, and exercises.
