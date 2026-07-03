---
title: "Polyakov Loop"
description: "Defines the Polyakov loop as a thermal Wilson line and explains its role as the finite-temperature center-symmetry order parameter in pure gauge theory."
sidebar:
  label: "Polyakov Loop"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §82; Polyakov, Gauge Fields and Strings, Chs. 5 and 7; Schwartz Chs. 25–26; Gaiotto–Kapustin–Seiberg–Willett 2015."
topics:
  - Polyakov loop
  - deconfinement
  - finite temperature
  - center symmetry
  - thermal Wilson line
canonicalTopics:
  - polyakov-loop
  - deconfinement
  - finite-temperature-gauge-theory
  - center-symmetry
  - static-quark-free-energy
researchStatus:
  established:
    - "In pure gauge theory, the renormalized Polyakov loop is the standard order parameter for spontaneous breaking of thermal center symmetry and hence for deconfinement."
  active:
    - "With dynamical fundamental matter, the center symmetry is explicitly broken and the Polyakov loop becomes a useful diagnostic rather than an exact order parameter."
---

## Summary

The **Polyakov loop** is a Wilson line that wraps the Euclidean thermal circle. At temperature $T=1/\beta$, Euclidean time is periodic,

$$
\tau\sim \tau+\beta,
$$

and the Polyakov loop in representation $R$ at spatial position $\mathbf x$ is

$$
P_R(\mathbf x)
=
\frac{1}{d_R}\operatorname{tr}_R\,\mathcal P
\exp\left[-ig\int_0^\beta d\tau\, A_0(\tau,\mathbf x)\right].
$$

In pure $SU(N)$ gauge theory, $P_R$ transforms under the thermal center symmetry as

$$
P_R(\mathbf x)\mapsto z^{k_R}P_R(\mathbf x),
\qquad z\in\mathbb Z_N,
$$

where $k_R$ is the $N$-ality of $R$. Therefore the fundamental Polyakov loop is an order parameter for deconfinement in pure gauge theory:

$$
\langle P_{\mathbf N}\rangle=0
\quad\text{center unbroken, confined phase},
$$

while

$$
\langle P_{\mathbf N}\rangle_{\rm ren}\ne0
\quad\text{center broken, deconfined phase}.
$$

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![The Polyakov loop is a thermal Wilson line wrapping the Euclidean time circle. It is charged under the thermal center symmetry, and its expectation value diagnoses whether the center is unbroken or spontaneously broken in pure gauge theory.](/figures/gauge-theories-standard-model/polyakov-loop-thermal-circle.svg)

<figcaption>

The Polyakov loop $P_R(\mathbf x)$ wraps the Euclidean time circle $S^1_\beta$. A center-twisted gauge transformation multiplies it by $z^{k_R}$. In pure gauge theory, $\langle P_{\mathbf N}\rangle=0$ in the center-unbroken confined phase, while a nonzero renormalized expectation value in a chosen center sector signals deconfinement.

</figcaption>
</figure>

## Prerequisites

You should know [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) and [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/). The finite-temperature interpretation uses the Euclidean thermal circle, but no detailed thermal-field-theory machinery is needed for a first pass.

The main idea is simple: the Wilson line that usually runs along a contour in spacetime can wrap the compact Euclidean time direction. Once it does, it behaves like a local operator in the spatial theory.

## Core idea

At zero temperature, a large rectangular Wilson loop measures the energy of an external charge–anticharge pair. At finite temperature, a Wilson line can wind around the Euclidean time circle. Such a line is the worldline of a static external charge that exists for the full thermal time interval.

The expectation value of a renormalized Polyakov loop has the form

$$
\langle P_R(\mathbf x)\rangle_{\rm ren}
=
e^{-\beta F_R},
$$

where $F_R$ is the free energy cost of inserting a single static external source in representation $R$.

In a pure confining phase, an isolated fundamental source cannot exist with finite free energy. The center symmetry is unbroken, and the charged operator $P_{\mathbf N}$ has vanishing expectation value.

In a deconfined phase, the thermal medium can support an isolated fundamental color source with finite free energy. The center symmetry is spontaneously broken in the thermodynamic limit, and the renormalized Polyakov loop is nonzero in a chosen center sector.

That is the finite-temperature version of the Wilson-loop confinement story.

## Setup and conventions

We work in Euclidean signature at temperature

$$
T=\frac{1}{\beta}.
$$

Bosonic gauge fields are periodic along the thermal circle:

$$
A_\mu(\tau+\beta,\mathbf x)=A_\mu(\tau,\mathbf x).
$$

The Polyakov line is the path-ordered holonomy around this circle:

$$
U(\mathbf x)
=
\mathcal P
\exp\left[-ig\int_0^\beta d\tau\, A_0(\tau,\mathbf x)\right].
$$

The normalized Polyakov loop in representation $R$ is

$$
P_R(\mathbf x)=\frac{1}{d_R}\operatorname{tr}_R U_R(\mathbf x).
$$

The sign in the exponent follows the Wilson-line convention used earlier in this chapter. Many references use the opposite sign because they define the covariant derivative or Euclidean gauge field differently. The symmetry and free-energy statements are independent of this sign convention.

## Gauge transformations and the center

Under a gauge transformation $h(\tau,\mathbf x)$ using the endpoint convention of the Wilson-loop page, the thermal holonomy transforms as

$$
U(\mathbf x)
\mapsto
h(\beta,\mathbf x)^{-1}U(\mathbf x)h(0,\mathbf x).
$$

If $h$ is strictly periodic,

$$
h(\beta,\mathbf x)=h(0,\mathbf x),
$$

then the trace is gauge invariant.

In a pure $SU(N)$ gauge theory, however, gauge transformations that are periodic only up to a center element also preserve the periodicity of all adjoint fields:

$$
h(\beta,\mathbf x)=z^{-1}h(0,\mathbf x),
\qquad z\in\mathbb Z_N.
$$

Because adjoint fields do not see $z$, this is a legitimate global transformation of the thermal theory. The Polyakov loop in representation $R$ transforms by

$$
P_R(\mathbf x)
\mapsto
z^{k_R}P_R(\mathbf x).
$$

Thus the fundamental Polyakov loop is charged under the thermal center symmetry. In an unbroken center-symmetric thermal state, symmetry implies

$$
\langle P_{\mathbf N}\rangle=0.
$$

If the center symmetry is spontaneously broken, the system chooses one of the $N$ center sectors, and the renormalized fundamental Polyakov loop can be nonzero.

## From one-form symmetry to thermal symmetry

The zero-temperature pure gauge theory has an electric center one-form symmetry

$$
\mathbb Z_N^{(1)}.
$$

When Euclidean time is compactified on $S^1_\beta$, a line wrapping the thermal circle becomes pointlike from the spatial point of view. Correspondingly, part of the four-dimensional one-form symmetry becomes an ordinary zero-form center symmetry of the three-dimensional thermal theory.

This is the conceptual reason the Polyakov loop is an order parameter. It is charged under the ordinary thermal center symmetry that descends from the four-dimensional center one-form symmetry.

The slogan is

$$
\text{thermal Wilson line wrapping }S^1_\beta
\quad\longrightarrow\quad
\text{local order parameter for center symmetry}.
$$

## Static-source free energy

The thermal partition function is

$$
Z=\operatorname{Tr}e^{-\beta H}.
$$

Inserting a Polyakov loop creates the worldline of an infinitely heavy external source. The ratio of the partition function with the source to the ordinary partition function gives

$$
\langle P_R\rangle_{\rm ren}
=
\frac{Z_R}{Z}
=
e^{-\beta F_R}.
$$

Therefore

$$
F_R=-T\log\langle P_R\rangle_{\rm ren}.
$$

If

$$
\langle P_{\mathbf N}\rangle=0,
$$

then the free energy of an isolated fundamental source is infinite. If

$$
\langle P_{\mathbf N}\rangle_{\rm ren}\ne0,
$$

then the free energy is finite.

This interpretation is the finite-temperature analog of the static-potential extraction from rectangular Wilson loops. The Polyakov loop does not measure the potential between two sources by itself; it measures the free energy of a single static source.

## Polyakov-loop correlators

A pair of Polyakov loops measures the free energy of a static source and antisource separated by

$$
r=|\mathbf x-\mathbf y|.
$$

Schematically,

$$
\langle P_R(\mathbf x)P_R^\dagger(\mathbf y)\rangle_{\rm ren}
\sim
e^{-\beta F_{R\bar R}(r,T)}.
$$

At low temperature in a confining pure gauge theory, this pair free energy grows with $r$ at large separation, reflecting an electric flux tube. At high temperature, color-electric fields are screened, and the free energy approaches a finite value at large $r$.

The correlator is often more robust than the one-point function in finite volume. In finite volume, spontaneous symmetry breaking is washed out unless one selects a center sector or takes the thermodynamic limit carefully.

## Confinement and deconfinement in pure gauge theory

For pure $SU(N)$ gauge theory, the thermal center symmetry is exact. The Polyakov loop gives a sharp order parameter:

| Phase | Center symmetry | Fundamental Polyakov loop | Static source |
|---|---|---|---|
| Confined | Unbroken | $\langle P_{\mathbf N}\rangle=0$ | Infinite free energy. |
| Deconfined | Spontaneously broken | $\langle P_{\mathbf N}\rangle_{\rm ren}\ne0$ in a sector | Finite free energy. |

The word “deconfined” here has a precise pure-gauge meaning: the thermal medium no longer imposes infinite free energy on a single fundamental external probe. It does not mean that the high-temperature theory is literally a gas of free gluons at all scales. Interactions, magnetic screening, and nonperturbative effects remain important.

The nature of the transition depends on the gauge group and spacetime dimension. For four-dimensional pure $SU(3)$ gauge theory, lattice studies find a first-order deconfinement transition. For $SU(2)$, the transition is second order and related to the three-dimensional Ising universality class. These details belong to the finite-temperature and lattice chapters; the symmetry logic is what matters here.

## What changes with dynamical quarks

If the theory contains dynamical fundamental quarks, the center symmetry is explicitly broken. The boundary condition for fundamental fermions is antiperiodic around the thermal circle,

$$
\psi(\tau+\beta,\mathbf x)=-\psi(\tau,\mathbf x),
$$

and a gauge transformation periodic only up to $z\ne1$ changes this boundary condition by a center phase. Thus it is not a symmetry.

Consequently,

$$
\langle P_{\mathbf N}\rangle
$$

is not required to vanish at low temperature. The Polyakov loop can still be small, and it remains a valuable diagnostic of crossover behavior, but it is not an exact order parameter.

This is the finite-temperature counterpart of string breaking. With dynamical fundamental matter, an isolated external fundamental source can be screened by quarks from the medium. The sharp center-symmetry distinction between confined and deconfined phases is replaced by a more nuanced physical crossover unless other symmetries or limits provide a sharp transition.

## Renormalization of the Polyakov loop

The bare Polyakov loop contains the ultraviolet self-energy of an infinitely heavy static source. On a lattice with spacing $a$, this produces a multiplicative renormalization of the form

$$
P_R^{\rm bare}\sim e^{-\beta\delta m_R(a)}P_R^{\rm ren},
$$

where $\delta m_R(a)$ diverges as $a\to0$.

Thus the absolute value of a bare Polyakov loop is regulator-dependent. The symmetry statement

$$
P_R\mapsto z^{k_R}P_R
$$

and the vanishing or nonvanishing of the properly renormalized order parameter in pure gauge theory are physical. Numerical comparisons of Polyakov-loop expectation values require a specified renormalization convention.

This mirrors the perimeter divergence of ordinary Wilson loops. Extended external probes carry ultraviolet self-energies; the long-distance physics is extracted after controlling those local contributions.

## Relation to ordinary Wilson loops

A rectangular Wilson loop with large Euclidean time extent $T$ extracts a zero-temperature static potential:

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)}.
$$

A Polyakov-loop correlator at finite temperature extracts a static pair free energy:

$$
\langle P(\mathbf x)P^\dagger(\mathbf y)\rangle
\sim e^{-\beta F_{q\bar q}(r,T)}.
$$

The symbols look similar but the limits are different. In the Wilson-loop potential, the Euclidean time size of the rectangle is taken large. In the Polyakov-loop correlator, the time direction is compact with fixed circumference $\beta$.

The Polyakov loop is therefore not merely “a Wilson loop with a funny shape.” It is a Wilson loop whose shape is forced by the thermal geometry, and that makes it an order parameter for thermal center symmetry.

## Common pitfalls

**The Polyakov loop is not the same as Polyakov’s book.** The name refers to the thermal Wilson line observable. Polyakov’s work also covers many other gauge-theory and string ideas.

**A nonzero Polyakov loop requires a center sector.** In finite volume, the expectation value of a symmetry-charged operator vanishes unless the symmetry is explicitly broken or a sector is selected. Spontaneous breaking is a thermodynamic-limit statement.

**The bare value is not universal.** The Polyakov loop requires multiplicative renormalization because a static external source has ultraviolet self-energy.

**With dynamical quarks it is not an exact order parameter.** Fundamental matter explicitly breaks center symmetry. The Polyakov loop remains useful, but its nonzero value no longer proves spontaneous center breaking.

**Deconfinement is not free theory.** Above a deconfinement transition, the system can still be strongly interacting, especially near the transition. The Polyakov loop diagnoses the fate of center symmetry and static fundamental probes.

**Do not confuse temporal and spatial Wilson loops.** At finite temperature, spatial Wilson loops can still show area-law behavior related to magnetic screening, even when the temporal Polyakov loop indicates deconfinement.

## Relations to other pages

This page is the finite-temperature continuation of [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/). It also uses the Wilson-line definition from [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/) and the line-renormalization caveats from [Area Law and Perimeter Law](/gauge-theories-standard-model/wilson-loops-confinement/area-law-and-perimeter-law/).

The QCD chapter will revisit the Polyakov loop in the presence of dynamical quarks, where it is no longer an exact order parameter. The finite-temperature and nonperturbative QFT volumes develop the lattice and thermal-field-theory details.

## Research status

The Polyakov loop is an established order parameter for deconfinement in pure gauge theories. Its transformation under center symmetry and its static-source free-energy interpretation are standard.

For full QCD with dynamical quarks, the situation is subtler. Center symmetry is explicitly broken, so the Polyakov loop is a diagnostic rather than an exact order parameter. Understanding the interplay among deconfinement, chiral symmetry restoration, screening, and transport is an active nonperturbative and phenomenological subject.

## Exercises

### Exercise 1: Center transformation of the Polyakov loop

Let $h(\beta,\mathbf x)=z^{-1}h(0,\mathbf x)$ with $z\in\mathbb Z_N$. Show that $P_R(\mathbf x)\mapsto z^{k_R}P_R(\mathbf x)$.

<details><summary><strong>Solution</strong></summary>

The holonomy transforms as

$$
U_R(\mathbf x)
\mapsto
R(h(\beta,\mathbf x))^{-1}U_R(\mathbf x)R(h(0,\mathbf x)).
$$

Using

$$
h(\beta,\mathbf x)=z^{-1}h(0,\mathbf x),
$$

we get

$$
U_R\mapsto R(h(0))^{-1}R(z)U_RR(h(0)).
$$

Taking the trace removes the conjugation by $R(h(0))$. Since $R(z)=z^{k_R}\mathbf 1_R$,

$$
P_R\mapsto z^{k_R}P_R.
$$

</details>

### Exercise 2: Static-source free energy

Assume $\langle P_R\rangle_{\rm ren}=e^{-\beta F_R}$. What happens to $F_R$ if $\langle P_R\rangle=0$?

<details><summary><strong>Solution</strong></summary>

Taking the logarithm gives

$$
F_R=-T\log\langle P_R\rangle_{\rm ren}.
$$

If the expectation value vanishes exactly, then

$$
\log\langle P_R\rangle_{\rm ren}\to -\infty,
$$

so

$$
F_R\to +\infty.
$$

For a fundamental source in pure gauge theory, this is the statement that an isolated fundamental color source has infinite free energy in the center-unbroken confined phase.

</details>

### Exercise 3: Why adjoint matter preserves the thermal center

Why does a gauge transformation periodic up to $z^{-1}\in\mathbb Z_N$ preserve adjoint fields but not fundamental fields?

<details><summary><strong>Solution</strong></summary>

In the endpoint convention used in this chapter, an adjoint field transforms as

$$
\Phi\mapsto h^{-1}\Phi h.
$$

If $h(\beta)=z^{-1}h(0)$, then

$$
\Phi(\beta)
\mapsto h(\beta)^{-1}\Phi(\beta)h(\beta)
=h(0)^{-1}z\Phi(\beta)z^{-1}h(0)
=h(0)^{-1}\Phi(\beta)h(0),
$$

because $z$ is central. Thus the adjoint field boundary condition is unchanged.

A fundamental field transforms as

$$
\psi\mapsto h^{-1}\psi.
$$

Then $h(\beta)=z^{-1}h(0)$ changes an antiperiodic thermal boundary condition into

$$
\psi'(\beta)=-z\,\psi'(0),
$$

rather than $\psi'(\beta)=-\psi'(0)$. Unless $z=1$, the fundamental boundary condition is changed. Therefore the center transformation is not a symmetry when dynamical fundamental fields are present.

</details>

### Exercise 4: Polyakov correlator and pair free energy

Given

$$
\langle P(\mathbf x)P^\dagger(\mathbf y)\rangle
\sim e^{-\beta F_{q\bar q}(r,T)},
$$

what is $F_{q\bar q}$ in terms of the correlator?

<details><summary><strong>Solution</strong></summary>

Take the logarithm:

$$
\log\langle P(\mathbf x)P^\dagger(\mathbf y)\rangle
\sim -\beta F_{q\bar q}(r,T).
$$

Since $T=1/\beta$,

$$
F_{q\bar q}(r,T)
=
-T\log\langle P(\mathbf x)P^\dagger(\mathbf y)\rangle
$$

up to the same renormalization and normalization choices used in defining the Polyakov loops.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, confinement, and thermal line diagnostics.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Wilson lines, lattice gauge theory, and Yang–Mills running.
- Polyakov, *Gauge Fields and Strings*, Chs. 5 and 7, for confinement criteria, phase factors, and loop dynamics.

### Deeper references

- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for the relation between four-dimensional one-form center symmetry and the finite-temperature Polyakov-loop order parameter.
- Svetitsky and Yaffe, “Critical Behavior at Finite-Temperature Confinement Transitions,” for the relation between deconfinement transitions and lower-dimensional spin models.
- McLerran and Svetitsky, “A Monte Carlo Study of SU(2) Yang–Mills Theory at Finite Temperature,” for classic lattice use of the Polyakov loop.
- Greensite, *An Introduction to the Confinement Problem*, for center symmetry, Polyakov loops, and finite-temperature deconfinement diagnostics.

## Version history

- **2026-06-18:** Initial polished draft. Added Polyakov-loop definition, center transformation, free-energy interpretation, correlators, renormalization, dynamical-quark caveats, and exercises.
