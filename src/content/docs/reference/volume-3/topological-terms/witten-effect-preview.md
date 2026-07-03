---
title: "Witten Effect: Preview"
description: "Explains how a four-dimensional theta term shifts the electric charge lattice of magnetic monopoles and dyons."
sidebar:
  label: "Witten Effect: Preview"
  order: 10
level: Advanced
status: "Polished draft"
source: "Witten 1979; Coleman on monopoles and instantons; Srednicki §§92–94; Polyakov Ch. 6; modern generalized-symmetry and topological-response references."
topics:
  - Witten effect
  - theta terms
  - magnetic monopoles
  - dyons
  - electric-magnetic charge lattice
  - large gauge transformations
  - topological response
canonicalTopics:
  - witten-effect
  - dyons
  - theta-term
  - magnetic-monopole
  - electric-magnetic-charge-lattice
researchStatus:
  established:
    - "In four-dimensional compact electrodynamics or a gauge theory Higgsed to a compact U(1), a theta term shifts the electric charge assigned to magnetic sectors."
    - "The charge lattice is invariant under theta periodicity once one also relabels the integer electric quantum number."
  active:
    - "Modern uses connect the Witten effect to higher-form symmetries, global-form choices, time-reversal anomalies at theta equals pi, topological insulators, and duality-covariant descriptions of charge lattices."
---

## Summary

The Witten effect says that a magnetic monopole in a four-dimensional theory with a theta term is generically also electrically charged. In a compact $U(1)$ normalization where magnetic flux is integral,

$$
\frac{1}{2\pi}\int_{S^2}F=m\in\mathbb Z,
$$

the electric charge lattice is shifted to

$$
\frac{q_e}{e}=n+\frac{\theta}{2\pi}m,
\qquad n,m\in\mathbb Z,
$$

up to the sign convention for the theta term. Thus a pure monopole at $\theta=0$ becomes a dyon at $\theta\ne0$.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram comparing the electric-magnetic charge lattice at theta equals zero with the shifted dyon lattice at nonzero theta.](/figures/symmetry-anomalies-topology/witten-effect-charge-lattice.svg)

<figcaption>

The Witten effect is a statement about the global charge lattice, not just about a classical equation of motion. Turning on $\theta$ shears the lattice of electric and magnetic charges; the monopole line $m=1$ is shifted by $\theta/2\pi$ in electric charge.

</figcaption>
</figure>

The effect is one of the cleanest places where a total derivative becomes physical. Without magnetic sources, $F\wedge F=d(A\wedge F)$ for abelian gauge fields and does not change local Maxwell equations. With monopoles, compactness, nontrivial bundles, or boundaries, the same term changes the identification of electric charge.

## Prerequisites

Read [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/), [Quantization of Couplings](/symmetry-anomalies-topology/topological-terms/quantization-of-couplings/), and [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) first.

It also helps to know the distinction between background and dynamical gauge fields from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and the large-gauge viewpoint from [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

## Core idea

A theta term can shift the momentum conjugate to the gauge field. Gauss law then measures not only the electric flux but also a piece proportional to magnetic flux. Therefore a sector with magnetic charge carries an induced electric charge.

For a state with magnetic charge $m$, the allowed electric charges are not simply integers. They are affine-shifted integers:

$$
\frac{q_e}{e}\in \mathbb Z+\frac{\theta}{2\pi}m.
$$

This is the Witten effect.

At $\theta=0$, a unit monopole can have $q_e/e\in\mathbb Z$. At $\theta=\pi$, a unit monopole has half-odd-integer electric charge in this convention:

$$
\frac{q_e}{e}\in \mathbb Z+\frac{1}{2}.
$$

That half-charge is not a cute arithmetic accident. It is the visible footprint of the theta term in the spectrum of charged line or particle sectors.

## Setup and conventions

We use a compact abelian gauge field $A$ with curvature $F=dA$. The normalization is chosen so that Wilson lines have integer charge,

$$
W_n(\gamma)=\exp\!\left(i n\int_\gamma A\right),
\qquad n\in\mathbb Z,
$$

and magnetic flux obeys

$$
\frac{1}{2\pi}\int_{S^2}F=m\in\mathbb Z.
$$

The four-dimensional action has the schematic Lorentzian form

$$
S[A]
=\int_{M_4}\left(
-\frac{1}{2e^2}F\wedge *F
+\frac{\theta}{8\pi^2}F\wedge F
\right)+S_{\mathrm{sources}}.
$$

With the orientation and canonical-sign convention used on this page, the dyon lattice is written as

$$
\boxed{\frac{q_e}{e}=n+\frac{\theta}{2\pi}m.}
$$

:::note[Convention-sensitive source note]
Many references write the Witten-effect formula with the opposite sign, $q_e/e=n-\theta m/2\pi$. This is usually not a physical disagreement; it comes from reversing the sign of the theta term, the orientation convention for $F\wedge F$, or the sign assigned to magnetic charge. The invariant content is the $\theta$-dependent affine shift of the electric charge lattice by magnetic charge.
:::

For a nonabelian gauge theory broken to $U(1)$, this $U(1)$ is the long-distance gauge group seen by the monopole. The microscopic nonabelian theory determines which magnetic charges exist, which electric charges are allowed, and which global form of the gauge group is being used.

## Charge lattices before theta

In ordinary compact electrodynamics, electric and magnetic charges form a lattice. A convenient dimensionless labeling is

$$
(n,m)\in\mathbb Z\oplus\mathbb Z,
$$

where $n$ labels electric charge and $m$ labels magnetic charge. The Dirac pairing between two dyons is

$$
\langle (n,m),(n',m')\rangle=n m'-n'm.
$$

The Dirac quantization condition says that this pairing must be integral. In the simplest normalization it is automatically integral for integer pairs.

Without theta, the physical charge lattice can be drawn as a square lattice in the $(q_e/e,m)$ plane:

$$
\frac{q_e}{e}=n,
\qquad m\in\mathbb Z.
$$

A pure monopole is the point $(0,1)$.

## The theta term shears the lattice

After adding the theta term, the same integer lattice of quantum labels $(n,m)$ is embedded differently into the physical charge plane:

$$
(n,m)\longmapsto
\left(\frac{q_e}{e},m\right)
=\left(n+\frac{\theta}{2\pi}m,m\right).
$$

This is a shear transformation. It leaves the magnetic charge unchanged and shifts electric charge by an amount proportional to magnetic charge.

For $m=0$, nothing happens:

$$
\frac{q_e}{e}=n.
$$

Purely electric particles do not acquire magnetic charge from the theta term. For $m\ne0$, however, every magnetic sector is shifted.

The unit monopole sector becomes

$$
\frac{q_e}{e}=n+\frac{\theta}{2\pi}.
$$

At a generic theta angle, there may be no state in the unit magnetic sector with zero electric charge.

## Canonical derivation from Gauss law

The simplest derivation is canonical. In temporal gauge, the momentum conjugate to the spatial gauge field is not just proportional to the electric field. It is shifted by the magnetic field:

$$
\Pi^i
=\frac{1}{e^2}E^i-\frac{\theta}{4\pi^2}B^i
$$

in the sign convention used here.

Gauss law quantizes the generator of compact gauge transformations. On a sphere surrounding a particle or monopole,

$$
\int_{S^2}\Pi^i dS_i\in\mathbb Z.
$$

The magnetic flux through the same sphere is

$$
\int_{S^2}B^i dS_i=2\pi m.
$$

Therefore the electric flux contribution differs from the integer Gauss-law generator by a theta-dependent magnetic-flux term. Rewriting the result in units of the minimal electric charge gives

$$
\frac{q_e}{e}=n+\frac{\theta}{2\pi}m.
$$

The point is not that the monopole core has secretly become electrically charged by magic. The point is that the conserved generator measured at infinity contains a topological magnetic-flux contribution once $\theta$ is nonzero.

## Path-integral derivation by source coupling

The same physics appears in the path integral. The theta term is locally a total derivative for abelian fields:

$$
F\wedge F=d(A\wedge F).
$$

If $A$ is globally smooth and there are no magnetic defects or boundaries, this term does not affect local equations. A monopole line is different. Around the line, $A$ cannot be represented globally by one nonsingular one-form. One must use patches, or equivalently allow a magnetic defect.

The theta term then has a boundary-like contribution localized by the magnetic defect. For a monopole worldline $L_m$, the effective coupling contains a term proportional to

$$
\frac{\theta m}{2\pi}\int_{L_m}A.
$$

But $\int_L A$ is precisely the coupling of electric charge to the gauge field. Thus the monopole line behaves as if it has electric charge

$$
\Delta\!\left(\frac{q_e}{e}\right)=\frac{\theta m}{2\pi}.
$$

This derivation is morally identical to anomaly inflow: a bulk topological term is harmless in smooth patches, but a defect turns the total derivative into physical lower-dimensional data.

## Periodicity and relabeling

The formula seems to threaten $2\pi$ periodicity, because

$$
\frac{q_e}{e}=n+\frac{\theta}{2\pi}m
$$

changes under $\theta\mapsto\theta+2\pi$:

$$
\frac{q_e}{e}\longmapsto n+m+\frac{\theta}{2\pi}m.
$$

But $n$ is an integer label. The spectrum is unchanged if we relabel

$$
n\longmapsto n-m.
$$

So the charge lattice as an unlabeled set is periodic:

$$
\mathcal L_{\theta+2\pi}=\mathcal L_\theta.
$$

The page [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) explains the same phenomenon from the sector-sum and large-gauge viewpoints. Here the same periodicity is visible in the dyon spectrum.

## CP and time reversal at special theta angles

The theta term is odd under CP and under time reversal in ordinary four-dimensional electrodynamics, because $F\wedge F$ is proportional to $\mathbf E\cdot\mathbf B$ in components. Therefore generic $\theta$ breaks these symmetries.

The special values are

$$
\theta=0,
\qquad
\theta=\pi
\quad\text{mod }2\pi.
$$

At $\theta=0$, the charge lattice is symmetric in the obvious way. At $\theta=\pi$, CP or time reversal must be accompanied by the nontrivial $2\pi$ periodic identification of the charge lattice. In the unit magnetic sector, electric charges are half-integer:

$$
\frac{q_e}{e}\in\mathbb Z+\frac{1}{2}.
$$

This is why theta equals pi is often a place where discrete symmetry, monopoles, and anomalies collide. In nonabelian Yang–Mills theories, the analogous point can carry mixed anomalies involving time reversal and one-form center symmetry. In condensed-matter language, the same half-charge phenomenon is central to the electromagnetic response of three-dimensional topological insulators.

## Nonabelian monopoles and Higgsing

The original setting is often a nonabelian gauge theory spontaneously broken to an abelian subgroup. A classic example is

$$
SU(2)\longrightarrow U(1)
$$

by an adjoint Higgs field. The theory contains smooth ’t Hooft–Polyakov monopoles. Far away from the monopole core, the fields look abelian, so the long-distance theta term induces the same charge shift.

The nonabelian embedding matters in three ways.

First, it determines the magnetic charge lattice. A monopole charge is not just an arbitrary $U(1)$ flux; it is constrained by how the $U(1)$ sits inside the original gauge group.

Second, it determines the allowed electric charges. If the microscopic gauge group is $SU(2)$ rather than $SO(3)=SU(2)/\mathbb Z_2$, the allowed line operators and charge lattice differ.

Third, it determines how theta periodicity acts. Changing the global form of the gauge group can refine the naive statement $\theta\sim\theta+2\pi$ and can introduce discrete theta angles.

This is one of the earliest places where the modern phrase “global form matters” becomes unavoidable.

## Higher-form symmetry viewpoint

In pure compact electrodynamics, electric and magnetic one-form symmetries organize Wilson and ’t Hooft line operators. The Witten effect says that the theta term mixes their charge assignments.

A Wilson line is electrically charged. An ’t Hooft line is magnetically charged. In a theta background, an ’t Hooft line is more naturally a dyonic line: it carries both magnetic and induced electric charge.

Schematically,

$$
T_m
\quad\longrightarrow\quad
T_m W_{\theta m/2\pi}.
$$

For generic $\theta$, the displayed expression is symbolic because Wilson-line charges must obey quantization. The precise statement is that the allowed line lattice is sheared. At rational theta, one can sometimes describe this by attaching ordinary Wilson lines after choosing a normalization; at irrational theta, the lattice viewpoint is safer.

This is the clean modern formulation: theta changes the embedding of the abstract charge lattice into electric and magnetic response data.

## Boundary response and topological insulators

On a manifold with boundary,

$$
\int_{M_4}F\wedge F
=\int_{\partial M_4}A\wedge dA
$$

locally for abelian fields. Thus a bulk theta term induces a boundary Chern–Simons response unless boundary degrees of freedom cancel it.

At $\theta=\pi$, this is the effective-field-theory description of the electromagnetic response of a time-reversal-invariant topological insulator, with important spin-structure and fermionic subtleties. A magnetic monopole inserted into the bulk carries half-integer electric charge. That is the condensed-matter avatar of the same Witten-effect formula.

The boundary story is subtle because a half-level Chern–Simons term is not a standalone bosonic three-dimensional theory on an arbitrary manifold. It must be interpreted with spin structure, boundary fermions, or bulk inflow. The eta-invariant page following this one explains the refined language.

## What this effect teaches

The Witten effect is useful because it compresses several big lessons into one formula.

First, a total derivative can change the quantum theory.

Second, the physical spectrum depends on the global charge lattice, not just the local equations of motion.

Third, theta periodicity may act by relabeling sectors rather than by leaving every label fixed.

Fourth, monopoles expose global data that purely electric perturbation theory cannot see.

Finally, topological response is not only about effective actions. It also changes the quantum numbers of defects and particles.

## Common pitfalls

**Calling the theta term irrelevant because it is a total derivative.** Locally, yes. Globally, no. Monopoles, boundaries, instantons, and nontrivial bundles are exactly where total derivatives become measurable.

**Forgetting the sign convention.** The sign of the induced electric charge depends on the sign of $S_\theta$, orientation, and the magnetic-charge convention. The robust statement is the affine shift proportional to $\theta m/2\pi$.

**Thinking the monopole must have a singular core.** The effect applies cleanly to smooth ’t Hooft–Polyakov monopoles. A singular Dirac monopole is a useful long-distance idealization, not a necessity.

**Confusing the integer label with the measured charge.** The integer $n$ labels the compact gauge generator. The measured electric charge in a magnetic sector is shifted when $\theta\ne0$.

**Assuming theta periodicity fixes every state label.** Periodicity often returns the same spectrum after relabeling. That relabeling is part of the physics.

## Relations to other pages

[Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) introduces the sector weights that make $\theta$ physical. [Periodicity and Large Gauge Transformations](/symmetry-anomalies-topology/topological-terms/periodicity-and-large-gauge-transformations/) explains why $\theta$ is angular. [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/) places the Witten effect next to Hall response, BF response, and SPT response.

The effect will reappear in [Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/), [Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/), [Anomalies and Boundaries](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-boundaries/), and [Eta Invariants: Preview](/symmetry-anomalies-topology/topological-terms/eta-invariants-preview/).

## Research status

The basic Witten effect is established. It is a standard result of four-dimensional gauge theory with theta terms and magnetic monopoles.

Active uses are broader. Modern research uses Witten-effect logic in generalized global symmetry, electromagnetic duality, global-form-dependent line lattices, time-reversal anomalies at $\theta=\pi$, topological insulator response, spin-TQFT refinements, and duality-covariant descriptions of abelian gauge theories.

The main caution is not whether the effect exists. It is how precisely to formulate charge quantization in a theory with a given global gauge group, matter spectrum, spin structure, boundary condition, and allowed line-operator lattice.

## Exercises

### Exercise 1: Theta periodicity of the dyon lattice

Let

$$
\mathcal L_\theta
=\left\{\left(n+\frac{\theta}{2\pi}m,m\right): n,m\in\mathbb Z\right\}.
$$

Show that $\mathcal L_{\theta+2\pi}=\mathcal L_\theta$ as a set.

<details><summary><strong>Solution</strong></summary>

At $\theta+2\pi$,

$$
\left(n+\frac{\theta+2\pi}{2\pi}m,m\right)
=\left(n+m+\frac{\theta}{2\pi}m,m\right).
$$

Since $n$ runs over all integers, so does $n+m$ for fixed integer $m$. Therefore the set of points is unchanged. The labels have changed, but the charge lattice has not.

</details>

### Exercise 2: Half-charge at theta equals pi

For a unit monopole $m=1$, list the allowed electric charges at $\theta=0$ and $\theta=\pi$ in units of $e$.

<details><summary><strong>Solution</strong></summary>

At $\theta=0$,

$$
\frac{q_e}{e}=n,
\qquad n\in\mathbb Z.
$$

At $\theta=\pi$,

$$
\frac{q_e}{e}=n+\frac{1}{2},
\qquad n\in\mathbb Z.
$$

Thus a unit magnetic sector carries half-odd-integer electric charge at $\theta=\pi$ in this convention.

</details>

### Exercise 3: Dirac pairing is unchanged

Define the abstract charge labels by $(n,m)$ and $(n',m')$. Show that the Dirac pairing

$$
\langle (n,m),(n',m')\rangle=n m'-n'm
$$

is independent of $\theta$, even though the physical electric coordinate is shifted.

<details><summary><strong>Solution</strong></summary>

The theta term changes the embedding of the integer lattice into the physical electric coordinate,

$$
q/e=n+\frac{\theta}{2\pi}m.
$$

It does not change the abstract integer labels $(n,m)$ that enter the Dirac pairing. Equivalently, if one writes the pairing using physical electric coordinates $x=n+\alpha m$ and $x'=n'+\alpha m'$ with $\alpha=\theta/2\pi$, then

$$
xm'-x'm
=(n+\alpha m)m'-(n'+\alpha m')m
=nm'-n'm.
$$

The $\alpha mm'$ terms cancel.

</details>

### Exercise 4: Boundary Chern–Simons term

Assume $F=dA$ globally on a patch. Show that

$$
F\wedge F=d(A\wedge dA).
$$

What does this suggest when spacetime has a boundary?

<details><summary><strong>Solution</strong></summary>

Since $F=dA$ and $dF=d^2A=0$,

$$
d(A\wedge dA)=dA\wedge dA-A\wedge d^2A=F\wedge F.
$$

Therefore

$$
\int_{M_4}F\wedge F=\int_{\partial M_4}A\wedge dA
$$

when the patching assumptions are harmless. A four-dimensional theta term can induce a three-dimensional Chern–Simons response on a boundary. Globally, this statement must be refined by quantization, spin structure, and anomaly inflow.

</details>

## References

- E. Witten, “Dyons of Charge $e\theta/2\pi$,” *Physics Letters B* **86** (1979) 283.
- S. Coleman, “The Uses of Instantons,” in *Aspects of Symmetry*, Cambridge University Press.
- M. Srednicki, *Quantum Field Theory*, §§92–94.
- A. M. Polyakov, *Gauge Fields and Strings*, Ch. 6.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- E. Witten, “Fermion Path Integrals And Topological Phases,” arXiv:1508.04715.

## Version history

- 2026-06-18: First polished draft. Added the charge-lattice formulation, canonical Gauss-law derivation, theta-periodicity relabeling, CP/time-reversal discussion, and boundary-response bridge.
