---
title: "Maxwell Field"
description: "The free massless spin-one gauge field: field strength, gauge redundancy, Maxwell equations, physical polarizations, Coulomb and Lorenz gauges, photon propagators, and coupling to conserved currents."
sidebar:
  label: "Maxwell Field"
  order: 5
---

## Summary

The Maxwell field is the free massless spin-one field. Its basic variable is a gauge potential $A_\mu(x)$, but the local gauge-invariant field strength is

$$
\boxed{F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.}
$$

The source-free Maxwell Lagrangian is

$$
\boxed{\mathcal L_\text{Maxwell}=-\frac14F_{\mu\nu}F^{\mu\nu}.}
$$

With qft.org's mostly-minus convention and

$$
E^i=F^{i0},
\qquad
F^{ij}=-\epsilon^{ijk}B^k,
$$

this is

$$
\mathcal L_\text{Maxwell}=\frac12(\mathbf E^2-\mathbf B^2).
$$

The Euler–Lagrange equations are

$$
\boxed{\partial_\mu F^{\mu\nu}=0,}
$$

and the definition $F=dA$ gives the Bianchi identity

$$
\boxed{\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0.}
$$

The potential has the gauge redundancy

$$
\boxed{A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).}
$$

This is not an ordinary physical symmetry relating different states. It relates different descriptions of the same electromagnetic field configuration. The gauge redundancy removes the unphysical polarizations, leaving two physical photon helicities,

$$
\lambda=+1,
\qquad
\lambda=-1.
$$

A gauge-fixed propagator is useful for perturbation theory. In Feynman gauge,

$$
\boxed{
D_F^{\mu\nu}(p)=\frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}.
}
$$

Gauge-dependent propagators are not observables. Physical amplitudes are gauge independent when gauge invariance and current conservation are respected. Weinberg emphasizes that a massless helicity-one field cannot be represented by a true Lorentz four-vector without gauge redundancy; Coleman develops Maxwell theory as the massless limit of a vector field coupled to a conserved current; Srednicki treats Maxwell's equations, Coulomb-gauge photon quantization, LSZ for photons, and the photon path integral as the spin-one entry point (Weinberg 1995, Vol. I, §§5.3, 5.9, and 8.1–8.6; Coleman 2019, chs. 26–31; Srednicki 2007, §§54–57).

## Prerequisites

You should know [Constraints](/foundations/classical-field-theory/constraints/), [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/), [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/). We use the qft.org default convention $D_\mu=\partial_\mu+iqA_\mu$ for an Abelian field of charge $q$.

## Core idea

The Maxwell field is the first place where the slogan "a field is a collection of oscillators" needs a serious qualifier. The vector potential $A_\mu$ has four spacetime components, but a massless spin-one particle has only two physical helicities. The mismatch is not a bug. It is what gauge redundancy is for.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Gauge redundancy of the Maxwell potential and the two physical photon helicities](/figures/foundations/maxwell-gauge-redundancy.svg)

<figcaption>

The Maxwell potential has four components, but configurations related by $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ describe the same field strength. After gauge fixing and constraints, the physical one-particle states are the two transverse helicities $\lambda=\pm1$.

</figcaption>
</figure>

A massive vector field has three spin polarizations. A massless vector field has two. The missing mode is not removed by wishful thinking; it is removed because local gauge redundancy makes part of $A_\mu$ descriptive rather than physical.

:::note[Assumptions]
This page treats free Abelian Maxwell theory on flat Minkowski spacetime. Interacting QED, Faddeev–Popov gauge fixing, BRST symmetry, non-Abelian gauge fields, and renormalization are only previewed. The full gauge-theory architecture belongs in the later Gauge Fields and Symmetry sections.
:::

## Field strength and equations

The Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

It is antisymmetric:

$$
F_{\mu\nu}=-F_{\nu\mu}.
$$

The Maxwell action is

$$
S[A]=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

Varying the potential gives

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu.
$$

Using antisymmetry,

$$
\delta S
=-\frac12\int d^4x\,F^{\mu\nu}\delta F_{\mu\nu}
=-\int d^4x\,F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

Integrating by parts gives

$$
\delta S
=\int d^4x\,(\partial_\mu F^{\mu\nu})\delta A_\nu
+\text{boundary term}.
$$

For variations that vanish at the boundary, stationarity implies

$$
\partial_\mu F^{\mu\nu}=0.
$$

The other pair of Maxwell equations follows from the definition of $F$:

$$
\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0.
$$

In differential-form notation, this is simply

$$
F=dA,
\qquad
dF=0.
$$

The equations of motion are

$$
d{*F}=0
$$

in source-free flat spacetime, with the usual metric-signature care in the Hodge star.

## Gauge redundancy

The transformation

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

leaves the field strength invariant:

$$
F_{\mu\nu}\mapsto
\partial_\mu(A_\nu+\partial_\nu\alpha)
-\partial_\nu(A_\mu+\partial_\mu\alpha)
=F_{\mu\nu}.
$$

Therefore the Maxwell action is gauge invariant.

This has two related but distinct meanings:

1. $F_{\mu\nu}$ is a gauge-invariant local field strength.
2. $A_\mu$ contains unphysical descriptive information.

The second point is the one that matters for quantization. If two potentials differ by a pure gradient, they represent the same electromagnetic field. Counting all four components of $A_\mu$ as physical would overcount states.

Gauge redundancy is not an ordinary global symmetry. A global symmetry takes a physical configuration to another physical configuration, often with a different charge. A gauge transformation changes the representative used for the same physical configuration.

## Maxwell equations in three-vector form

With the definitions fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/),

$$
E^i=F^{i0},
\qquad
F^{ij}=-\epsilon^{ijk}B^k,
$$

the source-free equations become

$$
\nabla\cdot\mathbf E=0,
\qquad
\nabla\times\mathbf B-\partial_t\mathbf E=0,
$$

and

$$
\nabla\cdot\mathbf B=0,
\qquad
\nabla\times\mathbf E+\partial_t\mathbf B=0.
$$

The first pair comes from $\partial_\mu F^{\mu\nu}=0$. The second pair comes from the Bianchi identity. In the presence of an external current and coupling

$$
\mathcal L_\text{int}=-j_\mu A^\mu,
$$

the equations are

$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$

Taking the divergence gives

$$
\partial_\nu j^\nu=\partial_\nu\partial_\mu F^{\mu\nu}=0,
$$

because $\partial_\nu\partial_\mu$ is symmetric while $F^{\mu\nu}$ is antisymmetric. Thus a consistent coupling of a Maxwell field to a source requires a conserved current.

## Lorenz and Coulomb gauges

A gauge choice selects one representative from each gauge orbit, at least locally and up to residual gauge transformations.

The Lorenz gauge condition is

$$
\partial_\mu A^\mu=0.
$$

Do not autocorrect the spelling: this is the Lorenz gauge, named after Ludvig Lorenz, not the Lorentz gauge.

In Lorenz gauge, the source-free Maxwell equations become

$$
\Box A^\nu=0.
$$

This looks like four massless wave equations, but it still does not describe four physical photon polarizations. The gauge condition removes one combination, and residual gauge transformations with

$$
\Box\alpha=0
$$

remain.

The Coulomb gauge condition is

$$
\nabla\cdot\mathbf A=0.
$$

It makes the physical transverse degrees of freedom more explicit. In the absence of sources, one can also set $A^0=0$ after using the constraint. Then only the transverse vector potential propagates:

$$
\nabla\cdot\mathbf A_T=0,
\qquad
(\partial_t^2-\nabla^2)\mathbf A_T=0.
$$

Coulomb gauge is physically transparent but not manifestly Lorentz covariant. Lorenz and covariant gauges keep Lorentz covariance visible but introduce unphysical components that must cancel from gauge-invariant quantities. This tradeoff is a recurring theme in gauge theory.

## Physical polarizations

For a plane wave

$$
A_\mu(x)=\varepsilon_\mu(k)e^{-ik\cdot x},
$$

the source-free equations imply

$$
k^2\varepsilon^\nu-k^\nu(k\cdot\varepsilon)=0.
$$

For a nonzero physical wave, the massless dispersion relation is

$$
k^2=0,
\qquad
k^0=|\mathbf k|.
$$

In Lorenz gauge,

$$
k\cdot\varepsilon=0.
$$

Gauge transformations shift the polarization by

$$
\varepsilon_\mu\mapsto \varepsilon_\mu-i k_\mu \alpha_0
$$

for a plane-wave gauge parameter. Thus polarizations proportional to $k_\mu$ are pure gauge.

Choose momentum along the $z$-axis,

$$
k^\mu=(\omega,0,0,\omega).
$$

A convenient basis for the physical transverse polarizations is

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0).
$$

The helicity basis is

$$
\varepsilon_\pm^\mu
=\frac{1}{\sqrt2}(0,1,\pm i,0),
$$

up to phase conventions. These describe the two photon helicities,

$$
h=+1,
\qquad
h=-1.
$$

A common source of confusion is to say "a photon is a vector particle, so it should have three spin states." That is true for a massive spin-one particle. A massless helicity-one particle has two physical helicities. The Lorentz-covariant potential $A_\mu$ is not a literal four-state particle wavefunction.

## Canonical picture

The canonical momentum conjugate to $A_i$ is essentially the electric field. With the above conventions,

$$
\Pi^i=\frac{\partial\mathcal L}{\partial \dot A_i}=-F^{0i}=E^i,
$$

up to the index-placement convention used for spatial components. The momentum conjugate to $A_0$ vanishes:

$$
\Pi^0=0.
$$

This is a primary constraint. The preservation of this constraint gives Gauss's law,

$$
\nabla\cdot\mathbf E=0
$$

in the source-free theory. In the presence of charge density, it becomes

$$
\nabla\cdot\mathbf E=\rho.
$$

Thus $A_0$ is not an independent propagating oscillator. It enforces a constraint.

In Coulomb gauge, the equal-time commutator is transverse:

$$
[A_i^T(t,\mathbf x),E_j^T(t,\mathbf y)]
=i\left(\delta_{ij}-\frac{\partial_i\partial_j}{\nabla^2}\right)
\delta^{(3)}(\mathbf x-\mathbf y).
$$

The projector

$$
P_{ij}^T=\delta_{ij}-\frac{\partial_i\partial_j}{\nabla^2}
$$

removes the longitudinal part. This is the canonical algebra of the two physical photon degrees of freedom.

## Mode expansion

In a physical transverse gauge, the photon field can be expanded schematically as

$$
A_i(x)=\sum_{\lambda=\pm}
\int\frac{d^3\mathbf k}{(2\pi)^3\sqrt{2|\mathbf k|}}
\left[
\varepsilon_i^{(\lambda)}(\mathbf k)a_\lambda(\mathbf k)e^{-ik\cdot x}
+\varepsilon_i^{(\lambda)*}(\mathbf k)a_\lambda^\dagger(\mathbf k)e^{ik\cdot x}
\right],
$$

with

$$
k^0=|\mathbf k|,
\qquad
\mathbf k\cdot\boldsymbol\varepsilon^{(\lambda)}(\mathbf k)=0.
$$

The physical oscillator algebra is

$$
[a_\lambda(\mathbf k),a_{\lambda'}^\dagger(\mathbf q)]
=(2\pi)^3\delta_{\lambda\lambda'}\delta^{(3)}(\mathbf k-\mathbf q),
$$

with all other commutators zero, if the $1/\sqrt{2|\mathbf k|}$ normalization is used. Equivalently, one can use the invariant measure $d\mu(k)$ and relativistically normalized oscillators. The choice is bookkeeping; the physical content is the same.

The photon number operator in the free theory is

$$
N=\sum_{\lambda=\pm}\int\frac{d^3\mathbf k}{(2\pi)^3}
\,a_\lambda^\dagger(\mathbf k)a_\lambda(\mathbf k)
$$

in this normalization.

## Propagators and gauge fixing

The Maxwell kinetic operator is not invertible until gauge redundancy is fixed. This is why the photon propagator is not unique.

A common covariant gauge-fixed Lagrangian is

$$
\mathcal L_\xi
=-\frac14F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

The corresponding momentum-space propagator is

$$
\boxed{
D_F^{\mu\nu}(p)
=\frac{-i}{p^2+i\epsilon}
\left[
\eta^{\mu\nu}-(1-\xi)\frac{p^\mu p^\nu}{p^2+i\epsilon}
\right].
}
$$

Special cases include:

| Gauge | Parameter | Propagator |
| --- | --- | --- |
| Feynman gauge | $\xi=1$ | $D_F^{\mu\nu}(p)=-i\eta^{\mu\nu}/(p^2+i\epsilon)$ |
| Landau gauge | $\xi=0$ | transverse covariant propagator |

The $\xi$ dependence is gauge dependence. It cancels from physical amplitudes when the photon couples to a conserved current.

For a current-current exchange amplitude, the gauge-dependent piece gives a contribution proportional to

$$
j_\mu(p)p^\mu\,p^\nu j'_\nu(-p).
$$

If

$$
p_\mu j^\mu(p)=0,
\qquad
p_\nu j'^\nu(-p)=0,
$$

then this contribution vanishes. This is the simplest perturbative glimpse of why current conservation and gauge invariance go hand in hand.

## Coupling to charged fields

For a field of charge $q$, qft.org uses

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

The local gauge transformation is

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

Then

$$
D_\mu\psi\mapsto e^{-iq\alpha(x)}D_\mu\psi.
$$

For a Dirac field of charge $q$, the gauge-invariant matter Lagrangian is

$$
\mathcal L=\overline\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding gives

$$
\mathcal L
=\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\overline\psi\gamma^\mu\psi.
$$

Thus the current is

$$
j^\mu=q\overline\psi\gamma^\mu\psi,
$$

and the interaction is

$$
\mathcal L_\text{int}=-A_\mu j^\mu.
$$

Gauge invariance of the action requires the current coupled to $A_\mu$ to be conserved. In quantum theory this statement becomes the starting point for Ward identities.

## Stress tensor and scale behavior

The symmetric gauge-invariant stress tensor of the Maxwell field is

$$
T^{\mu\nu}
=-F^{\mu\rho}F^\nu_{\ \rho}
+\frac14\eta^{\mu\nu}F_{\rho\sigma}F^{\rho\sigma}.
$$

With mostly-minus conventions, this gives positive energy density

$$
T^{00}=\frac12(\mathbf E^2+\mathbf B^2).
$$

The trace in four spacetime dimensions is

$$
T^\mu_{\ \mu}=0
$$

classically. This tracelessness is a classical statement. In interacting quantum gauge theories, trace anomalies can appear after regularization and renormalization. That belongs in later pages, not in the free Maxwell field page.

## Why a photon mass is not a small detail

Adding a mass term

$$
\frac12m^2A_\mu A^\mu
$$

to the Maxwell Lagrangian is not gauge invariant. It changes the theory qualitatively. The field now has three physical polarizations rather than two, and the longitudinal mode is no longer pure gauge. That massive theory is the [Proca Field](/foundations/free-fields/proca-field/).

The massless limit of a massive vector field is subtle. In amplitudes coupled to conserved currents, longitudinal contributions can decouple in a smooth way. But as a theory of fields and constraints, Maxwell theory is not obtained by merely erasing $m$ from every Proca formula. Gauge redundancy appears at $m=0$ and changes the bookkeeping of physical states.

## Common pitfalls

**Pitfall 1: Treating gauge symmetry as an ordinary physical symmetry.** Gauge transformations do not produce new physical states. They identify redundant descriptions.

**Pitfall 2: Counting four photon polarizations.** The four components of $A_\mu$ are not four physical oscillators. The free photon has two helicities.

**Pitfall 3: Confusing Lorenz gauge with Lorentz invariance.** Lorenz gauge is the condition $\partial_\mu A^\mu=0$. Lorentz invariance is spacetime symmetry. The names are annoyingly close. Physics does enjoy these little ambushes.

**Pitfall 4: Thinking the propagator is an observable.** The photon propagator depends on gauge fixing. Gauge-invariant observables and properly computed S-matrix elements do not.

**Pitfall 5: Ignoring current conservation.** Coupling a massless gauge field directly to a nonconserved current is inconsistent with gauge invariance.

## Relation to other pages

- [Proca Field](/foundations/free-fields/proca-field/) compares Maxwell theory with the massive spin-one field.
- [Polarizations](/foundations/free-fields/polarizations/) will collect polarization vectors, spin sums, and little-group interpretation.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) will make the conceptual distinction between redundancy and physical symmetry precise.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) will revisit this field as the prototype of Abelian gauge theory with charged matter.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) will explain how gauge invariance constrains correlation functions and amplitudes.

## Research status

The free Maxwell field is textbook-standard and stable. Subtleties begin when one quantizes gauge fields covariantly, includes charged matter, regulates the theory, or considers global/topological sectors. Those subtleties are real, but the local free-field formulas on this page are the stable starting point.

## Exercises

### Exercise 1

Show explicitly that $F_{\mu\nu}$ is invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$.

### Exercise 2

Derive the source-free Maxwell equations from

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

### Exercise 3

Starting from $\partial_\mu F^{\mu\nu}=j^\nu$, prove that current conservation $\partial_\nu j^\nu=0$ follows automatically.

### Exercise 4

For $k^\mu=(\omega,0,0,\omega)$, verify that

$$
\varepsilon_1^\mu=(0,1,0,0),
\qquad
\varepsilon_2^\mu=(0,0,1,0)
$$

are transverse and spacelike normalized.

### Exercise 5

Show that in Lorenz gauge, the source-free Maxwell equations reduce to $\Box A^\mu=0$.

### Exercise 6

Use the covariant-gauge propagator to show that the gauge-dependent term does not contribute to a current-current exchange amplitude when both currents are conserved.

## Solutions

### Solution 1

Under the gauge transformation,

$$
F_{\mu\nu}\mapsto
\partial_\mu(A_\nu+\partial_\nu\alpha)
-\partial_\nu(A_\mu+\partial_\mu\alpha).
$$

Expanding,

$$
F_{\mu\nu}\mapsto
\partial_\mu A_\nu-\partial_\nu A_\mu
+\partial_\mu\partial_\nu\alpha
-\partial_\nu\partial_\mu\alpha.
$$

Ordinary partial derivatives commute, so the last two terms cancel. Therefore

$$
F_{\mu\nu}\mapsto F_{\mu\nu}.
$$

### Solution 2

Varying the action gives

$$
\delta S
=-\frac12\int d^4x\,F^{\mu\nu}\delta F_{\mu\nu}.
$$

Since

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu,
$$

antisymmetry gives

$$
\delta S=-\int d^4x\,F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

Integrating by parts,

$$
\delta S=\int d^4x\,(\partial_\mu F^{\mu\nu})\delta A_\nu
+\text{boundary term}.
$$

With vanishing boundary variations, stationarity implies

$$
\partial_\mu F^{\mu\nu}=0.
$$

### Solution 3

Take the divergence of the equation of motion:

$$
\partial_\nu j^\nu=\partial_\nu\partial_\mu F^{\mu\nu}.
$$

The operator $\partial_\nu\partial_\mu$ is symmetric under $\mu\leftrightarrow\nu$, while $F^{\mu\nu}$ is antisymmetric. Contracting a symmetric tensor with an antisymmetric tensor gives zero. Hence

$$
\partial_\nu j^\nu=0.
$$

### Solution 4

For $k^\mu=(\omega,0,0,\omega)$ and mostly-minus metric,

$$
k\cdot\varepsilon_1=k^0\varepsilon_1^0-k^3\varepsilon_1^3=0,
$$

and similarly

$$
k\cdot\varepsilon_2=0.
$$

The norms are

$$
\varepsilon_1\cdot\varepsilon_1=-1,
\qquad
\varepsilon_2\cdot\varepsilon_2=-1,
$$

and

$$
\varepsilon_1\cdot\varepsilon_2=0.
$$

They are transverse spacelike polarization vectors.

### Solution 5

Write

$$
\partial_\mu F^{\mu\nu}
=\partial_\mu(\partial^\mu A^\nu-\partial^\nu A^\mu)
=\Box A^\nu-\partial^\nu(\partial_\mu A^\mu).
$$

In Lorenz gauge,

$$
\partial_\mu A^\mu=0.
$$

Therefore the source-free equation becomes

$$
\Box A^\nu=0.
$$

### Solution 6

The covariant-gauge propagator contains the gauge-dependent term

$$
\frac{-i}{p^2+i\epsilon}\left[-(1-\xi)\frac{p^\mu p^\nu}{p^2+i\epsilon}\right].
$$

Inserted between currents, it contributes a factor proportional to

$$
j_\mu(p)p^\mu p^\nu j'_\nu(-p).
$$

If both currents are conserved, then in momentum space

$$
p_\mu j^\mu(p)=0,
\qquad
p_\nu j'^\nu(-p)=0.
$$

The gauge-dependent term therefore vanishes. The remaining amplitude is independent of $\xi$.

## Sources and further reading

### Primary references

- J. C. Maxwell, "A Dynamical Theory of the Electromagnetic Field," *Philosophical Transactions of the Royal Society of London* **155** (1865) 459–512.
- L. Lorenz, "On the identity of the vibrations of light with electrical currents," *Philosophical Magazine* **34** (1867) 287–301.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§54–57.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 27–31.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.3, 5.9, and ch. 8.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9.1–9.4.

### For a first pass

- A. Zee, *Quantum Field Theory in a Nutshell*, parts II–III, especially the discussion of gauge invariance as the massless spin-one organizing principle.

### For mathematical precision

- R. Haag, *Local Quantum Physics*, for the operator-algebraic perspective on fields and observables.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, for constraints and gauge fixing.
