---
title: "Instanton Number"
description: "Explains instanton number as a Euclidean topological charge, including Yang–Mills Pontryagin number, Chern–Simons number, theta weights, self-duality bounds, BPST instantons, and sigma-model analogues."
sidebar:
  label: "Instanton Number"
  order: 6
level: Advanced
status: "Polished draft"
source: "Srednicki §93; Polyakov Chs. 4 and 6; Coleman on instantons and false vacuum decay; Nakahara Chs. 1, 9, and 11; Frankel on Chern classes and Chern–Weil theory; Tong TASI soliton notes."
topics:
  - instantons
  - instanton number
  - Pontryagin number
  - theta vacua
  - Chern–Simons number
  - self-duality
  - Euclidean saddles
  - Yang–Mills topology
canonicalTopics:
  - instanton-number
  - pontryagin-number
  - yang-mills-instanton
  - theta-vacuum
  - euclidean-saddle
  - chern-simons-number
researchStatus:
  established:
    - "In four-dimensional Yang–Mills theory, finite-action Euclidean gauge fields are split into sectors labeled by the integer Pontryagin number when the bundle and trace normalization are fixed."
    - "Self-dual and anti-self-dual configurations saturate the standard Euclidean Yang–Mills action bound in a fixed instanton sector."
  active:
    - "Instanton calculus remains subtle in strongly coupled theories because large instantons, zero modes, confinement, finite temperature, and global-form choices can change the meaning and usefulness of semiclassical sector sums."
---

## Summary

An instanton number is a topological charge of a Euclidean field configuration. In four-dimensional Yang–Mills theory it is the integer

$$
k={1\over 8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F),
$$

using the normalization

$$
\operatorname{tr}(T^aT^b)={1\over2}\delta^{ab}
$$

for Hermitian generators and the volume convention $\int\operatorname{tr}(F\wedge F)=8\pi^2 k$. In components on oriented Euclidean $\mathbb R^4$,

$$
k={1\over 32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^a_{\mu\nu}
={1\over 64\pi^2}\int d^4x\,\epsilon^{\mu\nu\rho\sigma}F^a_{\mu\nu}F^a_{\rho\sigma},
\qquad
\widetilde F^a_{\mu\nu}={1\over2}\epsilon_{\mu\nu\rho\sigma}F^a_{\rho\sigma}.
$$

The same integer appears in several disguises:

- as the second Chern number of a gauge bundle,
- as a winding number of a pure gauge at infinity,
- as the change in Chern–Simons number between early and late Euclidean time,
- as the coefficient that multiplies the theta angle in the sector weight $e^{i\theta k}$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram connecting finite-action Euclidean gauge fields, Pontryagin number, Chern–Simons number, self-duality, and theta-sector weights.](/figures/symmetry-anomalies-topology/instanton-number-sector-map.svg)

<figcaption>

Instanton number packages several equivalent global facts. A finite-action Euclidean gauge field defines a topological sector $k$. The same $k$ is computed by $\int\operatorname{tr}(F\wedge F)$, by a winding number at infinity, or by the jump of Chern–Simons number across Euclidean time.

</figcaption>
</figure>

Instantons are not particles sitting in space. They are finite-action events in Euclidean spacetime. They contribute to path integrals, tunneling amplitudes, theta dependence, anomalous processes, and semiclassical approximations that have no Taylor expansion around the trivial vacuum.

## Prerequisites

You should know [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/), [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/), [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), and [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

Useful gauge-theory background includes [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/), and [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/).

## Core idea

A soliton is usually a static finite-energy configuration in space. An instanton is a finite-action configuration in Euclidean spacetime. The difference is not cosmetic. Solitons label states or sectors of a Hilbert space. Instantons contribute to transitions, tunneling amplitudes, and Euclidean correlation functions.

For four-dimensional Yang–Mills theory, Euclidean finite action requires

$$
S_E={1\over g^2}\int_{\mathbb R^4}\operatorname{tr}(F\wedge *F)<\infty.
$$

Thus the field strength must approach zero at infinity:

$$
F\to 0\qquad |x|\to\infty.
$$

The gauge field at infinity is therefore pure gauge. Since infinity in $\mathbb R^4$ is an $S^3$, this gives a map

$$
S^3_\infty\to G.
$$

For $G=SU(N)$ with $N\ge2$,

$$
\pi_3(SU(N))=\mathbb Z.
$$

The instanton number is this integer, written in gauge-invariant form as an integral of $\operatorname{tr}(F\wedge F)$.

:::note[Convention-sensitive source note]
The sign of $k$ depends on the orientation of Euclidean spacetime, the definition of $\epsilon^{\mu\nu\rho\sigma}$, whether generators are Hermitian or anti-Hermitian, and whether $F=dA-iA\wedge A$ or $F=dA+A\wedge A$ is used. This page uses the volume convention $D=d-iA$, $F=dA-iA\wedge A$, $\epsilon^{1234}=+1$ in Euclidean coordinates, and $\operatorname{tr}(T^aT^b)={1\over2}\delta^{ab}$.
:::

## The standard gauge-theory formula

Let $M_4$ be a closed oriented Euclidean four-manifold, or let $M_4=\mathbb R^4$ with fields approaching pure gauge fast enough at infinity. For a compact simple gauge group and a fixed trace normalization, define

$$
k={1\over 8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F).
$$

For an $SU(N)$ bundle with the fundamental trace, $k$ is an integer. Geometrically it is the second Chern number,

$$
k=\int_{M_4} c_2(E)
$$

up to the sign convention relating $c_2$ to $\operatorname{tr}(F\wedge F)$. Physically it is the label of the topological sector in the Euclidean path integral.

The component form follows from

$$
F={1\over2}F^a_{\mu\nu}T^a dx^\mu\wedge dx^\nu,
$$

so that

$$
\operatorname{tr}(F\wedge F)
={1\over8}F^a_{\mu\nu}F^a_{\rho\sigma}\epsilon^{\mu\nu\rho\sigma}d^4x.
$$

Therefore

$$
k={1\over32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^a_{\mu\nu},
\qquad
\widetilde F^a_{\mu\nu}={1\over2}\epsilon_{\mu\nu\rho\sigma}F^a_{\rho\sigma}.
$$

In Lorentzian signature one usually writes the same density as $F\widetilde F$, but the theta term then appears in the Lorentzian action rather than in the Euclidean action. Do not translate signs by vibes. Translate from the path-integral weight.

## The action bound and self-duality

The Euclidean Yang–Mills action is nonnegative:

$$
S_E={1\over g^2}\int\operatorname{tr}(F\wedge *F).
$$

Use the identity

$$
\int\operatorname{tr}\bigl((F\mp *F)\wedge *(F\mp *F)\bigr)\ge0.
$$

Since $*=+1$ on two-forms in Euclidean four-space, this gives

$$
\int\operatorname{tr}(F\wedge *F)
\ge
\left|\int\operatorname{tr}(F\wedge F)\right|.
$$

Thus

$$
S_E\ge {8\pi^2\over g^2}|k|.
$$

The bound is saturated when

$$
F=*F
$$

for $k>0$, or

$$
F=-*F
$$

for $k<0$, with the sign subject to the orientation convention. A self-dual solution is called an instanton; an anti-self-dual solution is called an anti-instanton.

This is the four-dimensional cousin of the Bogomolny trick for monopoles and vortices. The square gives the equations. The leftover surface or characteristic-class term gives the topological lower bound.

## The BPST instanton

The basic $SU(2)$ instanton on $\mathbb R^4$ has

$$
k=1,
\qquad
S_E={8\pi^2\over g^2}.
$$

It is localized in Euclidean spacetime and has collective coordinates:

$$
x_0^\mu\quad\text{position},
\qquad
\rho>0\quad\text{size},
\qquad
\text{global gauge orientation}.
$$

The size modulus $\rho$ is a special classical feature of pure four-dimensional Yang–Mills theory: the classical action is scale invariant. Quantum mechanically, the running coupling makes different sizes contribute with different weights. In asymptotically free theories, small instantons can be treated semiclassically. Large instantons are usually where perturbation theory shrugs and quietly leaves the room.

For $SU(N)$, an $SU(2)$ instanton can be embedded into an $SU(2)$ subgroup of $SU(N)$. More general instanton moduli spaces are described by ADHM data, which becomes important in supersymmetric gauge theory, localization, and exact results.

## Chern–Simons number and tunneling

The four-form $\operatorname{tr}(F\wedge F)$ is locally exact. With the present Hermitian convention,

$$
\operatorname{tr}(F\wedge F)=d\omega_3(A),
$$

where

$$
\omega_3(A)=\operatorname{tr}\left(A\wedge dA-{2i\over3}A\wedge A\wedge A\right).
$$

On a spatial slice $\Sigma_3$, define the Chern–Simons number

$$
N_{\rm CS}(A)={1\over8\pi^2}\int_{\Sigma_3}\omega_3(A),
$$

again modulo convention-dependent signs and integer shifts. Under a large gauge transformation, $N_{\rm CS}$ shifts by an integer.

If the Euclidean spacetime is approximately $\mathbb R_\tau\times \Sigma_3$, and the fields approach pure gauge at $\tau=\pm\infty$, then

$$
k=N_{\rm CS}(+\infty)-N_{\rm CS}(-\infty).
$$

This is the tunneling interpretation: instantons connect vacua whose Chern–Simons numbers differ by an integer.

The word “vacua” here is a little dangerous. The different pure-gauge configurations are gauge-equivalent under large gauge transformations, but quantum wavefunctionals may transform by a phase. This is where theta vacua enter.

## Theta angles and sector weights

Because the Euclidean path integral splits into instanton sectors, one may weight the sector $k$ by

$$
e^{i\theta k}.
$$

Equivalently, add the topological term

$$
S_\theta^{\rm E}=-i\theta k
$$

to the Euclidean exponent $e^{-S_E}$. The full Euclidean weight is then

$$
e^{-S_E+i\theta k}.
$$

In Lorentzian signature this is usually described by adding

$$
S_\theta^{\rm L}=\theta k
$$

to the action, or in density language by a multiple of

$$
F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The periodicity

$$
\theta\sim\theta+2\pi
$$

follows when $k\in\mathbb Z$ and all allowed bundles obey the standard integer quantization. Global-form choices, fractional instantons on special manifolds, background fields, and spin structures can refine this statement. That is why theta periodicity is a global question, not just a coefficient in a Lagrangian.

## Instantons and anomalous symmetry violation

Instanton number is tied to chiral anomalies. For a Dirac fermion in a representation $R$, the Euclidean Dirac operator in an instanton background has zero modes controlled by an index theorem. Schematically,

$$
\operatorname{index}(D\!\!\!/) = n_+ - n_- \propto T(R)k.
$$

Here $T(R)$ is the Dynkin index of the representation. For one fundamental Dirac fermion in an $SU(N)$ instanton with the usual normalization, the result gives the familiar zero-mode counting behind the ’t Hooft vertex.

The physical lesson is simple: a symmetry current that looks conserved perturbatively can fail to be conserved in backgrounds with nonzero instanton number. This is the semiclassical face of the anomaly.

:::note[Why the index formula is only schematic here]
The exact index formula depends on whether one counts Weyl or Dirac zero modes, on the representation normalization, and on Euclidean chirality conventions. The anomaly pages fix these normalizations in detail. This page only needs the structural fact: instanton number controls fermion zero modes and anomalous selection rules.
:::

## Sigma-model instantons and lumps

Instanton number is not only a Yang–Mills idea. A Euclidean sigma model may also have finite-action sectors labeled by homotopy.

For the two-dimensional $O(3)$ nonlinear sigma model, the field is a unit vector

$$
\mathbf n(x)\in S^2.
$$

Finite action compactifies Euclidean space to $S^2$, so configurations are maps

$$
S^2\to S^2.
$$

They are labeled by

$$
\pi_2(S^2)=\mathbb Z.
$$

The topological charge is

$$
Q={1\over4\pi}\int d^2x\,\mathbf n\cdot(\partial_1\mathbf n\times \partial_2\mathbf n).
$$

These are often called lumps or sigma-model instantons. The same pattern appears repeatedly: finite action supplies boundary conditions, boundary conditions compactify the domain, and topology labels sectors.

## Instantons versus solitons

The following distinction saves a lot of headaches.

A **soliton** is a localized finite-energy configuration in space. It represents a state, excitation, defect, or superselection sector. Monopoles, vortices, domain walls, and Skyrmions are examples.

An **instanton** is a localized finite-action configuration in Euclidean spacetime. It represents a tunneling event or nonperturbative saddle in a path integral.

This is why instanton number is a spacetime integral while monopole charge is a spatial flux. Mixing the two is one of the classic “I know the formulas but not the movie” mistakes.

## Common pitfalls

### Thinking F wedge F is irrelevant because it is locally exact

Locally,

$$
\operatorname{tr}(F\wedge F)=d\omega_3(A).
$$

Globally, its integral can be an integer. Local exactness does not imply global triviality when gauge fields live on nontrivial bundles or when boundary data carries winding.

### Forgetting the trace normalization

The same symbol $\operatorname{tr}$ can differ by a factor of two, the dual Coxeter number, or a representation index. Instanton number is integer only after the trace normalization and allowed bundle classes are fixed.

### Treating instantons as real-time classical solutions

Instantons solve Euclidean equations of motion. Their real-time interpretation is tunneling, anomalous transition, or saddle contribution, not a classical particle trajectory in Minkowski spacetime.

### Assuming semiclassical instanton calculus is always reliable

The factor

$$
e^{-8\pi^2/g^2}
$$

looks small at weak coupling. But instantons have sizes, zero modes, determinants, and interactions. In strongly coupled regimes or in theories with dangerous large instantons, the semiclassical expansion may stop being controlled.

## Relations to nearby pages

[Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) explains why sector weights $e^{i\theta k}$ are physical even when the density is locally a total derivative.

[Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) explains why large gauge transformations shift Chern–Simons number and enforce theta periodicity.

[Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/) and [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/) explain how $F\widetilde F$ appears in anomalous Ward identities.

[Skyrmions: Preview](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/skyrmions-preview/) explains a spatial $\pi_3$ soliton whose charge resembles the winding-number part of instanton topology, but lives in a different physical role.

## Research status

Instanton number itself is a settled topological invariant. The subtleties are in how instantons contribute to a given quantum theory.

In weakly coupled semiclassical regimes, instantons provide controlled nonperturbative corrections. In supersymmetric theories, instanton calculus can compute protected quantities and is tied to moduli spaces, ADHM construction, and localization. In QCD-like theories, instantons are physically important for chiral symmetry and theta dependence, but isolated-instanton approximations compete with confinement-scale dynamics.

Modern work also studies fractional instantons, calorons, monopole-instantons, resurgence, compactification, anomalies, and generalized global symmetries. The integer $k$ is the kindergarten door. The building behind it is pleasantly enormous.

## Exercises

### Exercise 1: The action bound

Assume Euclidean four-dimensional Yang–Mills theory with

$$
S_E={1\over g^2}\int\operatorname{tr}(F\wedge *F),
\qquad
k={1\over8\pi^2}\int\operatorname{tr}(F\wedge F).
$$

Show that

$$
S_E\ge {8\pi^2\over g^2}|k|.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
0\le \int\operatorname{tr}\bigl((F\mp *F)\wedge *(F\mp *F)\bigr).
$$

Because $*^2=1$ on two-forms in Euclidean four dimensions, expanding gives

$$
0\le 2\int\operatorname{tr}(F\wedge *F)\mp 2\int\operatorname{tr}(F\wedge F).
$$

Therefore

$$
\int\operatorname{tr}(F\wedge *F)\ge \pm\int\operatorname{tr}(F\wedge F).
$$

Choose the sign so that the right-hand side is positive. Then

$$
\int\operatorname{tr}(F\wedge *F)
\ge
\left|\int\operatorname{tr}(F\wedge F)\right|
=8\pi^2|k|.
$$

Multiplying by $1/g^2$ gives

$$
S_E\ge {8\pi^2\over g^2}|k|.
$$

</details>

### Exercise 2: Chern–Simons jump

Suppose $M_4=[\tau_i,\tau_f]\times \Sigma_3$ and

$$
\operatorname{tr}(F\wedge F)=d\omega_3(A).
$$

Show that, up to orientation conventions,

$$
k=N_{\rm CS}(\tau_f)-N_{\rm CS}(\tau_i).
$$

<details><summary><strong>Solution</strong></summary>

By Stokes’s theorem,

$$
\int_{M_4}\operatorname{tr}(F\wedge F)
=
\int_{M_4}d\omega_3(A)
=
\int_{\partial M_4}\omega_3(A).
$$

The boundary consists of the final and initial spatial slices with opposite induced orientations:

$$
\partial M_4=\Sigma_{\tau_f}\sqcup(-\Sigma_{\tau_i}).
$$

Thus

$$
{1\over8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)
=
{1\over8\pi^2}\int_{\Sigma_{\tau_f}}\omega_3(A)
-
{1\over8\pi^2}\int_{\Sigma_{\tau_i}}\omega_3(A).
$$

With

$$
N_{\rm CS}(\tau)={1\over8\pi^2}\int_{\Sigma_\tau}\omega_3(A),
$$

this is exactly

$$
k=N_{\rm CS}(\tau_f)-N_{\rm CS}(\tau_i).
$$

</details>

### Exercise 3: Theta periodicity

Assume all allowed sectors have $k\in\mathbb Z$. Show that the sector weight $e^{i\theta k}$ is invariant under $\theta\to\theta+2\pi$.

<details><summary><strong>Solution</strong></summary>

Under the shift,

$$
e^{i\theta k}\to e^{i(\theta+2\pi)k}=e^{i\theta k}e^{2\pi i k}.
$$

Since $k\in\mathbb Z$,

$$
e^{2\pi i k}=1.
$$

Therefore

$$
e^{i(\theta+2\pi)k}=e^{i\theta k}.
$$

This is the basic theta periodicity. It can be refined when the allowed topological charges are fractional in the presence of background fields or different global forms.

</details>

### Exercise 4: Sigma-model lump charge

For a map $\mathbf n:S^2\to S^2$, explain why

$$
Q={1\over4\pi}\int d^2x\,\mathbf n\cdot(\partial_1\mathbf n\times\partial_2\mathbf n)
$$

is an integer when $\mathbf n$ is smooth and approaches a constant at infinity.

<details><summary><strong>Solution</strong></summary>

Finite action compactifies the domain $\mathbb R^2$ to $S^2$. The field is therefore a smooth map

$$
\mathbf n:S^2\to S^2.
$$

The two-form

$$
{1\over4\pi}\mathbf n\cdot(d\mathbf n\times d\mathbf n)
$$

is the pullback of the normalized area form on the target sphere. Its integral is the degree of the map. Since

$$
\deg(\mathbf n)\in\mathbb Z,
$$

we get

$$
Q\in\mathbb Z.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §93. Instantons and theta vacua.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4 and 6. Instantons in Abelian systems and topology of gauge fields.
- S. Coleman, *Aspects of Symmetry*. Instantons, tunneling, and semiclassical reasoning.
- M. Nakahara, *Geometry, Topology and Physics*, Chs. 1, 9, and 11. Instantons, characteristic classes, and Chern–Weil theory.
- T. Frankel, *The Geometry of Physics*. Differential forms, Chern classes, Yang–Mills topology, and instanton winding.
- A. Belavin, A. Polyakov, A. Schwartz, and Y. Tyupkin, “Pseudoparticle solutions of the Yang–Mills equations,” *Physics Letters B* **59** (1975) 85–87.
- G. ’t Hooft, “Symmetry breaking through Bell–Jackiw anomalies,” *Physical Review Letters* **37** (1976) 8–11.
- D. Tong, *TASI Lectures on Solitons*, arXiv:hep-th/0509216. Pedagogical treatment of instantons, monopoles, vortices, and domain walls.

## Version history

- 2026-06-18: First polished draft. Added Pontryagin number, action bound, BPST instanton, Chern–Simons number, theta weights, anomaly/zero-mode bridge, sigma-model instantons, exercises, and references.
