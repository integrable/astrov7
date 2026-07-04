---
title: "Celestial Amplitudes Preview"
description: "A conceptual preview of celestial amplitudes, the conformal primary basis, Mellin transforms of flat-space amplitudes, and the link to asymptotic symmetries."
sidebar:
  label: "Celestial Amplitudes Preview"
  order: 11
level: Advanced
status: "Polished draft"
source: "Pasterski, Shao, and Strominger 2017; Pasterski and Shao 2017; Pasterski 2021; Strominger infrared lectures; celestial holography reviews."
topics:
  - celestial amplitudes
  - celestial holography
  - Mellin transform
  - asymptotic symmetries
  - soft theorems
canonicalTopics:
  - celestial-amplitudes
  - conformal-primary-basis
  - flat-space-holography
  - asymptotic-symmetry
researchStatus:
  established:
    - "The celestial transform is a well-defined change of basis for many flat-space scattering amplitudes, and Lorentz symmetry acts as two-dimensional global conformal symmetry on the celestial sphere."
  active:
    - "The interpretation of celestial amplitudes as observables of a complete celestial CFT, especially including loops, infrared effects, massive particles, and gravity, remains an active research program."
---

## Summary

Celestial amplitudes rewrite flat-space scattering amplitudes in a basis adapted to the Lorentz group. For massless four-dimensional scattering, an external null momentum can be parametrized by an energy $\omega>0$ and a point $(z,\bar z)$ on the celestial sphere. A Mellin transform over each external energy trades energy eigenstates for boost-weight eigenstates:

$$
\widetilde{\mathcal A}_n(\Delta_i,J_i,z_i,\bar z_i)
=
\prod_{i=1}^n
\int_0^\infty d\omega_i\,\omega_i^{\Delta_i-1}
\mathcal A_n(\eta_i\omega_i q_i,J_i).
$$

Here $\eta_i=+1$ or $-1$ distinguishes outgoing and incoming momenta, $J_i$ is helicity, and $q_i=q(z_i,\bar z_i)$ is a null direction. In this basis, the four-dimensional Lorentz group $SL(2,\mathbb C)$ acts as the global conformal group of the two-dimensional celestial sphere.

The result looks like a two-dimensional conformal correlator:

$$
\widetilde{\mathcal A}_n
\sim
\left\langle
\mathcal O_{\Delta_1,J_1}(z_1,\bar z_1)
\cdots
\mathcal O_{\Delta_n,J_n}(z_n,\bar z_n)
\right\rangle_{\rm celestial}.
$$

That notation is useful, but it should not be overread. Celestial amplitudes are first a change of basis for scattering states. The stronger claim that they define a complete ordinary two-dimensional CFT is subtle and still under active development.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 52rem;">

![Momentum-space amplitudes are Mellin transformed into celestial amplitudes on the sphere](/figures/perturbative-qft/celestial-amplitudes-preview.svg)

<figcaption>

Celestial amplitudes trade the energy variables of massless scattering states for conformal dimensions $\Delta_i$. The remaining null directions are points $(z_i,\bar z_i)$ on the celestial sphere. Lorentz transformations act as global conformal transformations on this sphere, while soft theorems become Ward-identity-like statements for celestial currents.

</figcaption>
</figure>

This page previews the dictionary: momentum basis to conformal primary basis, soft theorems to celestial currents, and flat-space scattering to a holographic-looking object on the sphere at null infinity.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Soft Limits](/perturbative-qft/modern-on-shell-amplitudes/soft-limits/), [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/), [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/), and [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/). From CFT, the relevant background is two-dimensional global conformal covariance, primary operators, and conformal weights.

## Core idea

Ordinary scattering amplitudes are usually written in a momentum basis. For each massless external particle in four dimensions, one specifies an energy $\omega$ and a point on the celestial sphere. The point gives the direction of the null momentum.

Celestial amplitudes keep the direction but Mellin transform the energy. Energy eigenstates are replaced by boost eigenstates. The resulting external labels look like conformal data:

| Momentum-space language | Celestial language |
|---|---|
| energy $\omega$ | conformal dimension $\Delta$ |
| helicity $J$ | spin $J=h-\bar h$ |
| null direction $q(z,\bar z)$ | insertion point on the celestial sphere |
| Lorentz covariance | global conformal covariance |
| soft theorem | current or Ward identity |
| infrared structure | celestial operator mixing and singularities |

This is why celestial amplitudes are a natural meeting point for scattering amplitudes, asymptotic symmetries, infrared physics, and holography in asymptotically flat spacetime.

## Setup and conventions

For a massless four-momentum in four dimensions, write

$$
p^\mu=\eta\,\omega\,q^\mu(z,\bar z),
\qquad \omega>0,
\qquad \eta=\pm1.
$$

A convenient null direction is

$$
q^\mu(z,\bar z)
=
\left(
1+z\bar z,
 z+\bar z,
-i(z-\bar z),
1-z\bar z
\right),
$$

up to an overall normalization convention. With the mostly-minus metric, $q^2=0$.

For a particle of helicity $J$, the celestial conformal weights are

$$
h=\frac{\Delta+J}{2},
\qquad
\bar h=\frac{\Delta-J}{2}.
$$

The conformal dimension is $\Delta=h+\bar h$, and the two-dimensional spin is $J=h-\bar h$.

The massless celestial transform of an amplitude is the product of Mellin transforms over external energies:

$$
\widetilde{\mathcal A}_n(\Delta_i,J_i,z_i,\bar z_i)
=
\prod_{i=1}^n
\int_0^\infty d\omega_i\,\omega_i^{\Delta_i-1}
\mathcal A_n(\eta_i\omega_i q_i,J_i).
$$

A more precise treatment tracks wavefunction normalizations, in/out prescriptions, regulator factors, little-group phases, and whether the momentum-conservation delta function is included or stripped. Those choices affect detailed formulas, not the central idea.

## Conformal primary wavefunctions

The celestial transform can be understood at the level of external wavefunctions. For a massless scalar, a conformal primary wavefunction can be written schematically as

$$
\Phi_\Delta^\pm(X;z,\bar z)
=
\int_0^\infty d\omega\,\omega^{\Delta-1}
\exp\left[\pm i\omega q(z,\bar z)\cdot X-\epsilon\omega\right].
$$

The sign distinguishes outgoing and incoming wave behavior. The regulator $\epsilon>0$ controls the oscillatory integral.

A Lorentz transformation acts on the sphere as a Möbius transformation,

$$
z\mapsto z'=\frac{az+b}{cz+d},
\qquad ad-bc=1,
$$

and the conformal primary wavefunction transforms as a two-dimensional primary with weights determined by $\Delta$ and spin.

Thus scattering amplitudes between conformal primary external states transform like correlators of primary operators on the celestial sphere.

## Lorentz symmetry becomes global conformal symmetry

The four-dimensional proper Lorentz group is locally $SL(2,\mathbb C)$. This is also the global conformal group acting on the Riemann sphere. Therefore, in celestial variables, Lorentz covariance becomes the statement that

$$
\widetilde{\mathcal A}_n
\mapsto
\prod_i
(cz_i+d)^{-2h_i}
(\bar c\bar z_i+\bar d)^{-2\bar h_i}
\widetilde{\mathcal A}_n,
$$

up to standard convention choices for incoming and outgoing states.

This is the cleanest part of the celestial dictionary. The full four-dimensional Poincaré group is richer. Translations do not act as ordinary two-dimensional conformal transformations; in the celestial basis, they shift conformal dimensions or act through difference operators. This is one reason celestial amplitudes are not simply ordinary compact Euclidean CFT correlators.

## Soft theorems as Ward identities

Soft theorems are among the strongest motivations for celestial amplitudes. In momentum space, a soft photon, gluon, or graviton factorizes from an amplitude when its energy goes to zero:

$$
\mathcal A_{n+1}(q;1,\ldots,n)
\sim
S(q)\,\mathcal A_n(1,\ldots,n).
$$

In the celestial basis, the soft limit corresponds to special values or poles in the conformal dimension of the soft operator. The leading soft photon theorem becomes a current-algebra-like Ward identity on the celestial sphere. Soft graviton theorems are related to BMS symmetry, supertranslations, and related currents.

The bridge is:

| Soft-scattering statement | Celestial interpretation |
|---|---|
| leading soft photon theorem | celestial current Ward identity |
| leading soft gluon theorem | non-Abelian current-like insertion, with color-ordering caveats |
| leading soft graviton theorem | supertranslation Ward identity |
| subleading soft graviton theorem | celestial stress-tensor-like structures in suitable formulations |
| memory effects | asymptotic charge transitions |

The precise dictionary depends on theory, dimension, infrared regulator, and boundary conditions. But the guiding idea is stable: asymptotic symmetries of flat spacetime become symmetry structures of the celestial description.

## Distributional nature of celestial amplitudes

Celestial amplitudes often behave more like distributions than ordinary smooth CFT correlators.

One reason is momentum conservation. A four-point massless amplitude contains

$$
\delta^{(4)}\!\left(\sum_i \eta_i\omega_i q_i\right),
$$

which constrains the energies and celestial positions. After Mellin transformation, this can produce delta functions or singular support in celestial cross-ratios.

Another reason is scale invariance. If an amplitude is homogeneous under a common rescaling of all energies, the Mellin transform can produce delta functions enforcing constraints on sums of dimensions.

This distributional behavior is not a defect. It is telling us that flat-space scattering is being represented in a basis with boost weights rather than energies. But it is a warning: not every intuition from ordinary two-dimensional Euclidean CFT applies automatically.

## Massive particles and loops

The cleanest celestial formulas are for massless four-dimensional scattering. Massive particles can also be treated, but the geometry changes. Massive momenta are naturally parametrized by points in hyperbolic space rather than just points on the celestial sphere plus an energy. The resulting celestial objects still transform covariantly, but the dictionary is less elementary.

Loops bring additional complications. Momentum-space loop amplitudes have branch cuts, infrared divergences, anomalous dimensions, and regulator dependence. After Mellin transformation, these features become celestial singularities, operator mixing, and deformations of the celestial correlator structure. Some behavior is universal, especially in gauge theory and gravity, but a complete all-purpose celestial loop dictionary is still an active subject.

A practical summary:

```txt
Tree-level massless amplitudes:
  cleanest celestial laboratory.

Soft theorems and asymptotic symmetries:
  strongest conceptual bridge.

Loops and IR divergences:
  important but subtle.

Massive particles:
  possible, but the basis is less minimal.

Full flat-space holographic dual:
  not yet a finished theory.
```

## What celestial amplitudes are good for

Celestial amplitudes make structures visible that are less obvious in ordinary momentum space. They make Lorentz covariance look like two-dimensional conformal covariance. They turn soft theorems into Ward identities. They connect flat-space scattering to the geometry of null infinity. They give a natural language for asymptotic symmetries, memory effects, and possible flat-space holography.

They also create new questions. What are the operator algebras of the celestial theory? What is the Hilbert space? How do translations, unitarity, locality, and cluster decomposition appear? How are loops and infrared-safe observables represented? Is there a nonperturbative celestial description of quantum gravity in asymptotically flat spacetime?

Those questions are why the subject is exciting. They are also why this page is a preview rather than a finished dictionary.

## Common pitfalls

**Thinking the celestial transform changes the physics.** It is first a change of basis for scattering states. The physics is in the amplitude; the celestial transform reorganizes it.

**Treating celestial amplitudes as ordinary textbook CFT correlators.** They transform conformally under Lorentz transformations, but they can be distributional, nonstandard, and sensitive to translations and infrared structure.

**Forgetting the role of energy integrals.** The Mellin transform over $\omega$ is the move that creates conformal dimensions. Without it, one merely has momentum directions on a sphere.

**Ignoring infrared issues.** Gauge theory and gravity have soft and collinear structure. Celestial amplitudes do not make IR divergences disappear; they translate them into celestial language.

**Confusing the celestial sphere with a physical detector screen.** The sphere labels null directions at infinity. Actual detectors measure finite-resolution energy and angle bins, not exact celestial primary insertions.

## Relations to other pages

- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) gives the massless variables related to celestial coordinates.
- [Soft Limits](/perturbative-qft/modern-on-shell-amplitudes/soft-limits/) explains the amplitude limits that become celestial current insertions.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) and [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) provide concrete soft-factor examples.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) explains why universal soft and collinear structures are natural.
- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) are needed for loop-level analytic structure.
- [CFT and Bootstrap](/cft-bootstrap/) is the natural home for conformal correlators, conformal blocks, and crossing.

## Research status

**Established.** The conformal primary basis and Mellin transform of massless amplitudes give objects that transform covariantly under the Lorentz group as two-dimensional conformal correlators.

**Active.** The interpretation of celestial amplitudes as a complete celestial CFT, the treatment of loops and infrared divergences, the role of translations, massive states, operator algebras, and nonperturbative gravitational physics are active research topics.

**Speculative.** A full flat-space holographic dual written purely as a celestial theory is a compelling long-term goal, not yet a completed framework comparable in precision to standard AdS/CFT examples.

## Exercises

### Exercise 1: Verify that the celestial direction is null

Using the mostly-minus metric, show that

$$
q^\mu(z,\bar z)
=
(1+z\bar z,
 z+\bar z,
-i(z-\bar z),
1-z\bar z)
$$

satisfies $q^2=0$.

<details>
<summary><strong>Solution</strong></summary>

Write $z=x+iy$, so $z\bar z=x^2+y^2$. Then

$$
q^0=1+x^2+y^2,
\qquad
q^1=2x,
\qquad
q^2=2y,
\qquad
q^3=1-x^2-y^2.
$$

With the mostly-minus metric,

$$
q^2=(q^0)^2-(q^1)^2-(q^2)^2-(q^3)^2.
$$

Let $r^2=x^2+y^2$. Then

$$
(q^0)^2-(q^3)^2
=(1+r^2)^2-(1-r^2)^2
=4r^2.
$$

Also

$$
(q^1)^2+(q^2)^2=4x^2+4y^2=4r^2.
$$

Therefore $q^2=4r^2-4r^2=0$.

</details>

### Exercise 2: Conformal weights and helicity

A celestial operator has dimension $\Delta$ and helicity $J$. Show that

$$
h=\frac{\Delta+J}{2},
\qquad
\bar h=\frac{\Delta-J}{2}
$$

implies $\Delta=h+\bar h$ and $J=h-\bar h$.

<details>
<summary><strong>Solution</strong></summary>

Add the two equations:

$$
h+\bar h
=\frac{\Delta+J}{2}+\frac{\Delta-J}{2}
=\Delta.
$$

Subtract them:

$$
h-\bar h
=\frac{\Delta+J}{2}-\frac{\Delta-J}{2}
=J.
$$

Thus the two-dimensional conformal spin is the four-dimensional helicity label.

</details>

### Exercise 3: A basic Mellin integral

Evaluate

$$
I(\Delta,\epsilon)=\int_0^\infty d\omega\,\omega^{\Delta-1}e^{-\epsilon\omega},
\qquad \epsilon>0.
$$

<details>
<summary><strong>Solution</strong></summary>

Set $u=\epsilon\omega$. Then $d\omega=du/\epsilon$ and $\omega^{\Delta-1}=u^{\Delta-1}\epsilon^{-(\Delta-1)}$. Hence

$$
I(\Delta,\epsilon)
=\epsilon^{-\Delta}\int_0^\infty du\,u^{\Delta-1}e^{-u}
=\epsilon^{-\Delta}\Gamma(\Delta).
$$

This is the elementary analytic structure behind conformal primary wavefunctions: the Mellin transform turns scaling in energy into dependence on a dimension-like parameter $\Delta$.

</details>

### Exercise 4: Soft behavior and a pole in dimension

Suppose an extra soft photon contributes a factor proportional to $\omega^{-1}$ as $\omega\to0$. Show why the soft region of its Mellin transform has a pole near $\Delta=1$.

<details>
<summary><strong>Solution</strong></summary>

The soft part of the Mellin transform behaves like

$$
\int_0^\Lambda d\omega\,\omega^{\Delta-1}\omega^{-1}
=
\int_0^\Lambda d\omega\,\omega^{\Delta-2}.
$$

For $\Delta\ne1$ this gives

$$
\frac{\Lambda^{\Delta-1}}{\Delta-1}.
$$

Thus the leading soft behavior produces a pole at $\Delta=1$. This is the elementary reason soft theorems are naturally associated with special celestial operator dimensions and current-like insertions.

</details>

## References

- S. Pasterski, S.-H. Shao, and A. Strominger, “Flat Space Amplitudes and Conformal Symmetry of the Celestial Sphere.”
- S. Pasterski and S.-H. Shao, “A Conformal Basis for Flat Space Amplitudes.”
- S. Pasterski, “Lectures on Celestial Amplitudes.”
- A. Strominger, *Lectures on the Infrared Structure of Gravity and Gauge Theory*.
- A.-M. Raclariu and related celestial-holography reviews, for broader context and open problems.
- Recent papers on celestial Mellin amplitudes, split representations, loops, and marginal deformations, for current research directions.

## Version history

- **2026-06-13:** Initial advanced preview page. The page emphasizes the massless four-dimensional celestial transform, Lorentz-as-conformal covariance, and soft-theorem dictionary; detailed loop-level, massive-particle, and nonperturbative celestial holography are left for later pages.
