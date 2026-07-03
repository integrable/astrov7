---
title: "Abelian Higgs Model"
description: "Explains the simplest Higgs mechanism: a charged complex scalar in a U(1) gauge theory reorganizes one angular scalar mode into the longitudinal polarization of a massive vector boson."
sidebar:
  label: "Abelian Higgs Model"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–85; Schwartz Ch. 28; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II spontaneously broken gauge theory chapters."
topics:
  - Abelian Higgs model
  - Higgs mechanism
  - spontaneous symmetry breaking
  - massive vector bosons
  - Goldstone modes
canonicalTopics:
  - abelian-higgs-model
  - higgs-mechanism
  - goldstone-mode
  - massive-vector-boson
  - gauge-invariant-mass-generation
researchStatus:
  established:
    - "In the Abelian Higgs model, one charged complex scalar and one U(1) gauge field reorganize into one massive vector field and one physical scalar excitation in the Higgs phase."
  active:
    - "Beyond perturbation theory, the relation between Higgs and confinement descriptions, vortices, compact gauge groups, and phase diagnostics requires care and is treated in later nonperturbative chapters."
---

## Summary

The Abelian Higgs model is the cleanest laboratory for the Higgs mechanism. Start with a $U(1)$ gauge field $A_\mu$ and a charged complex scalar field $\phi$. With the volume convention

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\phi\mapsto e^{-iq\alpha(x)}\phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

the standard Abelian Higgs Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\phi)^*(D^\mu\phi)
-V(\phi),
$$

with

$$
V(\phi)=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2,
\qquad
\mu^2>0,
\qquad
\lambda>0.
$$

The vacuum satisfies

$$
|\phi|^2=\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

If we write

$$
\phi(x)=\frac{v+\rho(x)}{\sqrt2}e^{i\theta(x)/v},
$$

then the combination

$$
B_\mu
=
A_\mu+\frac{1}{qv}\partial_\mu\theta
$$

is gauge invariant, and the scalar kinetic term becomes

$$
|D_\mu\phi|^2
=
\frac12(\partial_\mu\rho)^2
+\frac12q^2(v+\rho)^2B_\mu B^\mu.
$$

Thus the gauge boson mass is

$$
m_A=qv,
$$

while the radial scalar has tree-level mass

$$
m_\rho^2=2\lambda v^2.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Abelian Higgs degree-of-freedom flow](/figures/gauge-theories-standard-model/abelian-higgs-degree-flow.svg)

<figcaption>

The Abelian Higgs mechanism preserves the number of physical modes while changing their organization. The angular scalar is a gauge direction; it supplies the longitudinal polarization of the massive vector, while the radial field remains as a physical scalar.

</figcaption>
</figure>

The slogan “the gauge boson eats the Goldstone boson” is useful, but only if read as a statement about variables. Gauge symmetry is redundancy; it is not literally destroyed. What changes is the spectrum of gauge-invariant excitations: a massless vector plus a charged scalar becomes a massive vector plus a neutral scalar.

## Prerequisites

You should know [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/), [Gauge Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/), and the QED chapter through [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/). The covariant-derivative sign convention is fixed in [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/).

It also helps to know the basic global-symmetry story: a complex scalar with a Mexican-hat potential has a radial mode and an angular Goldstone mode. The Abelian Higgs model begins with the same potential, but the angular mode is gauge, not a physical massless particle.

## Core idea

A massless vector field in four dimensions has two physical polarizations. A massive vector field has three. The Abelian Higgs mechanism explains where the third polarization comes from without writing an explicit Proca mass term by hand.

Before expanding around the vacuum, the field content is:

| Field | Local field variables | Perturbative physical modes before the Higgs reorganization |
|---|---:|---:|
| $A_\mu$ | 4 components minus gauge redundancy and constraints | 2 massless vector polarizations |
| complex $\phi$ | 2 real scalar fields | 2 scalar modes |

After expanding in the Higgs phase, the convenient variables are:

| Field | Meaning | Perturbative physical modes |
|---|---|---:|
| $B_\mu$ | gauge-invariant massive vector combination | 3 massive vector polarizations |
| $\rho$ | radial scalar fluctuation | 1 scalar mode |

The number of physical modes is unchanged:

$$
2+2=3+1.
$$

The Higgs mechanism is therefore not magic mass creation. It is a gauge-invariant reorganization of degrees of freedom.

The reason this matters for the Standard Model is that the same logic gives masses to $W^\pm$ and $Z$ while leaving the photon massless. The Abelian model has only one broken gauge generator, so all the bookkeeping fits on one page. Nice little toy model, big career.

## Setup and conventions

We use the mostly-minus metric and the Abelian convention

$$
D_\mu\phi=(\partial_\mu+iqA_\mu)\phi,
$$

with

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The finite gauge transformation is

$$
\phi(x)\mapsto \phi'(x)=e^{-iq\alpha(x)}\phi(x),
\qquad
A_\mu(x)\mapsto A'_\mu(x)=A_\mu(x)+\partial_\mu\alpha(x).
$$

Then

$$
D'_\mu\phi'=e^{-iq\alpha}D_\mu\phi,
$$

so $(D_\mu\phi)^*D^\mu\phi$ is gauge invariant.

The Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\phi)^*D^\mu\phi
+\mu^2\phi^*\phi
-\lambda(\phi^*\phi)^2.
$$

Equivalently, $\mathcal L=-\frac14F^2+|D\phi|^2-V$ with

$$
V(\phi)=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2.
$$

Because $\lambda>0$, the potential is bounded below. Because $\mu^2>0$, the origin is unstable and the classical minima form a circle,

$$
\phi^*\phi=\frac{\mu^2}{2\lambda}\equiv\frac{v^2}{2}.
$$

A representative vacuum is

$$
\phi_0=\frac{v}{\sqrt2},
\qquad
A_\mu=0.
$$

Calling this a “choice of vacuum direction” is a convenient perturbative phrase. In a gauge theory, points on the vacuum circle are related by gauge transformations, so the angle is not a gauge-invariant order parameter.

## Global model first: the Goldstone mode

It is useful to compare with the ungauged model. Set $q=0$ and write

$$
\phi(x)=\frac{v+\rho(x)}{\sqrt2}e^{i\theta(x)/v}.
$$

Then

$$
\partial_\mu\phi
=
\frac{e^{i\theta/v}}{\sqrt2}
\left[\partial_\mu\rho+i\frac{v+\rho}{v}\partial_\mu\theta\right],
$$

so

$$
|\partial_\mu\phi|^2
=
\frac12(\partial_\mu\rho)^2
+\frac12\left(1+\frac{\rho}{v}\right)^2(\partial_\mu\theta)^2.
$$

The potential depends only on $\rho$:

$$
V
=
-\frac{\mu^2}{2}(v+\rho)^2
+\frac{\lambda}{4}(v+\rho)^4.
$$

Using $v^2=\mu^2/\lambda$, the quadratic term in $\rho$ is

$$
V(\rho)=V(v)+\frac12(2\lambda v^2)\rho^2+\cdots,
$$

so

$$
m_\rho^2=2\lambda v^2.
$$

There is no $\theta^2$ term. In the global theory, $\theta$ is the massless Goldstone boson of the spontaneously broken global $U(1)$ symmetry.

This is the reference picture many students have in mind. The gauged theory differs in exactly one decisive way: changing $\theta(x)$ locally can be undone by changing $A_\mu(x)$.

## Polar variables and the gauge-invariant vector

Now restore $q\neq0$. In polar variables,

$$
\phi(x)=\frac{v+\rho(x)}{\sqrt2}e^{i\theta(x)/v}.
$$

Under a gauge transformation,

$$
\phi\mapsto e^{-iq\alpha}\phi,
$$

so the angular variable transforms as

$$
\theta(x)\mapsto \theta'(x)=\theta(x)-qv\alpha(x).
$$

The gauge field transforms as

$$
A_\mu\mapsto A'_\mu=A_\mu+\partial_\mu\alpha.
$$

Therefore the combination

$$
B_\mu=A_\mu+\frac{1}{qv}\partial_\mu\theta
$$

is invariant:

$$
B'_\mu
=
A_\mu+\partial_\mu\alpha
+\frac{1}{qv}\partial_\mu(\theta-qv\alpha)
=
B_\mu.
$$

The covariant derivative becomes

$$
D_\mu\phi
=
\frac{e^{i\theta/v}}{\sqrt2}
\left[\partial_\mu\rho+iq(v+\rho)B_\mu\right].
$$

Hence

$$
(D_\mu\phi)^*D^\mu\phi
=
\frac12(\partial_\mu\rho)(\partial^\mu\rho)
+\frac12q^2(v+\rho)^2B_\mu B^\mu.
$$

The term quadratic in $B_\mu$ is

$$
\frac12q^2v^2B_\mu B^\mu,
$$

which is the mass term for a vector boson of mass

$$
m_A=qv.
$$

This derivation is the most transparent version of the Abelian Higgs mechanism. The angular field has not disappeared mysteriously. It appears inside the gauge-invariant massive vector field $B_\mu$.

## Unitary gauge

Unitary gauge sets

$$
\theta(x)=0.
$$

Then

$$
\phi(x)=\frac{v+\rho(x)}{\sqrt2},
\qquad
B_\mu=A_\mu.
$$

The Lagrangian becomes

$$
\mathcal L_{\rm unitary}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12q^2(v+\rho)^2A_\mu A^\mu
+\frac12(\partial_\mu\rho)^2
-V(\rho).
$$

Expanding the vector part gives

$$
\frac12q^2(v+\rho)^2A_\mu A^\mu
=
\frac12m_A^2A_\mu A^\mu
+q^2v\rho A_\mu A^\mu
+\frac12q^2\rho^2A_\mu A^\mu.
$$

So unitary gauge makes the physical spectrum easy to read:

$$
\boxed{m_A=qv,\qquad m_\rho^2=2\lambda v^2.}
$$

It also shows the interactions between the Higgs scalar and the massive vector. The term $\rho A_\mu A^\mu$ is the Abelian prototype of the Standard Model $hWW$ and $hZZ$ couplings.

Unitary gauge is conceptually clean for counting physical particles, but it is not usually the nicest gauge for loop calculations. At high momentum, the massive vector propagator behaves worse than in covariant gauges. For perturbative renormalization, it is often better to keep the would-be Goldstone field explicit.

## Cartesian variables and the mixing term

To see why gauge fixing matters in perturbation theory, use Cartesian variables,

$$
\phi(x)=\frac{1}{\sqrt2}\bigl(v+h(x)+i\chi(x)\bigr).
$$

At quadratic order,

$$
D_\mu\phi
=\frac{1}{\sqrt2}
\left[\partial_\mu h+i\partial_\mu\chi+iqvA_\mu+\cdots\right].
$$

Thus the quadratic part of $|D\phi|^2$ contains

$$
\frac12(\partial_\mu h)^2
+\frac12(\partial_\mu\chi)^2
+qvA_\mu\partial^\mu\chi
+\frac12q^2v^2A_\mu A^\mu.
$$

The field $\chi$ is the would-be Goldstone mode. The mixing term

$$
qvA_\mu\partial^\mu\chi
$$

is the Cartesian-variable version of “the vector is trying to eat the angular scalar.” If one integrates by parts, it becomes

$$
-qv\chi\,\partial_\mu A^\mu,
$$

up to a boundary term.

A common covariant gauge-fixing choice is the $R_\xi$ gauge

$$
\mathcal L_{\rm gf}
=
-\frac{1}{2\xi}\left(\partial_\mu A^\mu-\xi qv\chi\right)^2.
$$

The cross term in $\mathcal L_{\rm gf}$ cancels the $A$–$\chi$ mixing after integration by parts. The would-be Goldstone field then has gauge-dependent mass

$$
m_\chi^2=\xi m_A^2.
$$

This is not a physical mass. It is a gauge-dependent bookkeeping device. The physical spectrum has a massive vector and a radial scalar; the $\chi$ field appears in covariant gauges so that propagators and Ward/BRST identities behave well.

Special choices include:

| Gauge | Choice | What it is good for |
|---|---|---|
| Landau gauge | $\xi=0$ | keeps the Goldstone massless in perturbation theory and often simplifies identities |
| Feynman–'t Hooft gauge | $\xi=1$ | gives equal vector and Goldstone gauge masses, simplifying many loop calculations |
| Unitary gauge | effectively removes $\chi$ | displays the physical spectrum but obscures power counting |

Do not confuse these gauges with different theories. They are different coordinate systems on the same gauge-redundant description.

## Why this is not a Proca theory by hand

A massive Abelian vector field can be described by the Proca Lagrangian

$$
\mathcal L_{\rm Proca}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12m^2A_\mu A^\mu.
$$

For a free vector field, this is perfectly sensible. But the Abelian Higgs model is more than a Proca mass term. It gives a gauge-invariant ultraviolet description in which the vector mass arises from a scalar kinetic term. This matters because:

1. The theory has a controlled high-energy scalar sector.
2. The vector mass is tied to scalar couplings.
3. Gauge fixing and BRST structure can be made explicit.
4. The same mechanism generalizes to non-Abelian theories, where explicit mass terms would clash badly with gauge consistency.

In the Abelian model alone, one might think the Higgs construction is overkill. In the Standard Model, it is the difference between a predictive gauge theory and a pile of broken rules wearing a trench coat.

## Gauge-invariant interpretation

The perturbative expansion often begins by choosing a vacuum representative, such as $\phi_0=v/\sqrt2$. That language is useful, but it can be misleading. The field $\phi$ is charged, so $\langle\phi\rangle$ is not gauge invariant. Strictly speaking, a local gauge-variant operator cannot serve as a physical order parameter.

What is gauge invariant?

One simple gauge-invariant scalar is

$$
\phi^*\phi=\frac12(v+\rho)^2.
$$

The vector combination $B_\mu$ is gauge invariant in the polar parametrization away from zeros of $\phi$. The spectrum contains a massive spin-one excitation that can be described by $B_\mu$ perturbatively.

There are also extended and nonlocal observables, such as Wilson lines and vortex operators, that become important in nonperturbative discussions. In compact Abelian Higgs models, vortices are central. In lattice gauge theory, the distinction between Higgs-like and confinement-like regimes can be more subtle than the perturbative cartoon suggests.

For this page, the working regime is the weakly coupled continuum Higgs phase, expanded around a nonzero scalar modulus. In that regime, the perturbative statement “one Goldstone mode is eaten” is precise and extremely useful.

## Limiting cases

Several limits are worth keeping straight.

### The global limit

If $q\to0$ while keeping $v$ fixed, the gauge field decouples and the angular field becomes a physical Goldstone boson. The massive vector mass

$$
m_A=qv
$$

vanishes, but the physics is not just a smooth relabeling of the Higgs phase. The local redundancy has disappeared, so the angular mode becomes physical.

### The symmetric point

If the potential has $\mu^2<0$ in the convention

$$
V=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2,
$$

then the minimum is at $\phi=0$. The gauge boson remains massless, and the scalar is an ordinary charged scalar. No Higgs reorganization occurs.

### The heavy-radial limit

If $\lambda\to\infty$ with $v$ fixed, the radial mode becomes heavy:

$$
m_\rho^2=2\lambda v^2\to\infty.
$$

At energies well below $m_\rho$, the scalar modulus is approximately frozen and the low-energy theory is a massive vector theory with gauge-invariant origin. This limit is useful but can hide the physics that restores good high-energy behavior.

### The high-energy limit

At energies much larger than $m_A$, amplitudes involving longitudinal vector bosons are often controlled by the would-be Goldstone mode. This is the Abelian preview of the Goldstone equivalence theorem, which becomes essential for $W_L$ and $Z_L$ scattering in the Standard Model.

## Common pitfalls

**Saying that gauge symmetry is spontaneously broken as if it were an ordinary global symmetry.** Gauge symmetry is redundancy. The Higgs phase reorganizes the spectrum; it does not literally violate a physical symmetry generated by a gauge charge.

**Thinking the Goldstone boson vanished.** The angular variable is still present in gauges that keep it explicit. It is reorganized into the longitudinal polarization of the massive vector field.

**Forgetting the scalar charge in the vector mass.** With $D_\mu=\partial_\mu+iqA_\mu$, the mass is $m_A=qv$. If the scalar has charge $nq$, the mass changes accordingly.

**Confusing the radial mass with the vector mass.** The vector mass is $qv$; the radial mass is $\sqrt{2\lambda}\,v$. They are controlled by different couplings.

**Treating unitary gauge as the only physical description.** It displays the physical spectrum, but covariant gauges are often better for calculations. Gauge-independent observables cannot depend on $\xi$.

**Using the global Goldstone theorem without checking the symmetry.** The theorem applies to physical global symmetries. A local gauge redundancy does not imply a physical massless scalar.

**Ignoring zeros of $\phi$ in the polar parametrization.** The variables $\rho,\theta$ are clean near a vacuum with $|\phi|\neq0$, but vortex configurations pass through $\phi=0$ and require more care.

## Relations to other pages

This page is the local model for the Higgs Sector chapter. It feeds directly into [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/), where the same counting is done for several generators.

It also prepares [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/), where the scalar is not just a charged field under one $U(1)$ but a doublet under $SU(2)_L$ with hypercharge $Y=1/2$.

For the earlier conceptual background, see [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) and [Global Versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/). For the quantum gauge-fixing side, see [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/) and [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/).

For nonperturbative physics beyond the perturbative Higgs mechanism, the Wilson Loops, Phases, and Confinement chapter explains why line operators and phase diagnostics are more subtle than local field expectation values.

## Research status

The perturbative Abelian Higgs mechanism is settled textbook physics. Its equations, degree-of-freedom counting, and gauge-fixing descriptions are standard.

What remains subtle is not the perturbative mechanism but the global and nonperturbative interpretation of phases. Compactness of the gauge group, vortex sectors, boundary conditions, line operators, and the possible continuity between Higgs and confinement regimes require more than the local Lagrangian expansion. Those topics belong to later chapters on Wilson loops, generalized symmetries, and nonperturbative QFT.

## Exercises

### Exercise 1: Find the scalar and vector masses

Starting from

$$
V(\phi)=-\mu^2\phi^*\phi+\lambda(\phi^*\phi)^2,
$$

show that $v^2=\mu^2/\lambda$, $m_\rho^2=2\lambda v^2$, and $m_A=qv$.

<details><summary><strong>Solution</strong></summary>

The minimum satisfies

$$
0=\frac{\partial V}{\partial(\phi^*\phi)}=-\mu^2+2\lambda\phi^*\phi,
$$

so

$$
\phi^*\phi=\frac{\mu^2}{2\lambda}\equiv\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

Write

$$
\phi=\frac{v+\rho}{\sqrt2}
$$

in unitary gauge. Then

$$
V(\rho)
=-\frac{\mu^2}{2}(v+\rho)^2+\frac{\lambda}{4}(v+\rho)^4.
$$

The second derivative at $\rho=0$ is

$$
\left.\frac{d^2V}{d\rho^2}\right|_{0}
=-\mu^2+3\lambda v^2
=2\lambda v^2.
$$

Thus $m_\rho^2=2\lambda v^2$. The kinetic term gives

$$
|D_\mu\phi|^2\supset \frac12q^2v^2A_\mu A^\mu,
$$

so $m_A^2=q^2v^2$ and $m_A=qv$ for $q>0$.

</details>

### Exercise 2: Check the invariant vector

Under

$$
\theta\mapsto\theta-qv\alpha,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

verify that

$$
B_\mu=A_\mu+\frac{1}{qv}\partial_\mu\theta
$$

is gauge invariant.

<details><summary><strong>Solution</strong></summary>

Substitute the transformed fields:

$$
B'_\mu
=A_\mu+\partial_\mu\alpha
+\frac{1}{qv}\partial_\mu(\theta-qv\alpha).
$$

The last term is

$$
\frac{1}{qv}\partial_\mu\theta-\partial_\mu\alpha.
$$

Therefore

$$
B'_\mu=A_\mu+\frac{1}{qv}\partial_\mu\theta=B_\mu.
$$

</details>

### Exercise 3: Cancel the Goldstone–vector mixing

Using Cartesian variables

$$
\phi=\frac{1}{\sqrt2}(v+h+i\chi),
$$

show that the gauge-fixing term

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial_\mu A^\mu-\xi qv\chi)^2
$$

cancels the quadratic mixing between $A_\mu$ and $\chi$.

<details><summary><strong>Solution</strong></summary>

The scalar kinetic term contains

$$
qvA_\mu\partial^\mu\chi.
$$

Integrating by parts gives

$$
qvA_\mu\partial^\mu\chi
=-qv\chi\,\partial_\mu A^\mu
$$

up to a boundary term. Expanding the gauge-fixing term gives

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial\cdot A)^2
+qv\chi\,\partial\cdot A
-\frac12\xi q^2v^2\chi^2.
$$

The middle term cancels the integrated mixing term. The remaining $\chi$ mass is gauge dependent:

$$
m_\chi^2=\xi q^2v^2=\xi m_A^2.
$$

</details>

### Exercise 4: Count polarizations

Explain why the Higgs phase has the same number of perturbative physical degrees of freedom as the original massless gauge field plus complex scalar.

<details><summary><strong>Solution</strong></summary>

Before the Higgs reorganization, a massless vector in four dimensions has two physical polarizations, and a complex scalar has two real scalar modes. Thus there are

$$
2+2=4
$$

physical modes.

After the Higgs reorganization, the vector is massive and has three polarizations. The radial scalar remains physical and contributes one mode. Thus there are

$$
3+1=4
$$

physical modes. The angular scalar supplies the longitudinal vector polarization.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§84–85, for spontaneous breaking of gauge symmetries and the spontaneously broken Abelian gauge theory.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 28, for spontaneous symmetry breaking and the Higgs mechanism.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for a classic conceptual discussion of Goldstone modes and the Higgs phenomenon.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the general treatment of spontaneously broken gauge theories.

## Version history

- **2026-06-18:** Initial polished draft. Added the polar-variable derivation, $R_\xi$ gauge discussion, gauge-invariant interpretation, exercises, and Abelian Higgs figure.
