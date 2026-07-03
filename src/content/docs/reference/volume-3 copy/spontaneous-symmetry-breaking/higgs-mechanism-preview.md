---
title: "Higgs Mechanism Preview"
description: "Explains how gauge fields acquire massive vector degrees of freedom in a Higgs phase without treating gauge redundancy as an ordinary broken global symmetry."
sidebar:
  label: "Higgs Mechanism"
  order: 10
level: Graduate
status: "Polished draft"
source: "Coleman on secret symmetry and gauge fields; Srednicki §§84–87; Schwartz Ch. 28; Weinberg Vol. II on broken gauge theories; Zee on the Anderson–Higgs mechanism."
topics:
  - Higgs mechanism
  - gauge redundancy
  - spontaneous symmetry breaking
  - Goldstone modes
  - Abelian Higgs model
  - gauge fixing
  - massive vector bosons
  - Elitzur theorem
canonicalTopics:
  - higgs-mechanism
  - gauge-redundancy
  - abelian-higgs-model
  - massive-vector-boson
  - eaten-goldstone-mode
  - elitzur-theorem
researchStatus:
  established:
    - "In a weakly coupled Higgs description, Goldstone fields associated with gauge directions combine with gauge fields to form massive vector particles; no physical massless Goldstone boson remains for a purely gauged broken direction."
    - "Local gauge redundancy is not a physical global symmetry and should not be described as spontaneously broken in the same sense as an ordinary global symmetry."
  active:
    - "Gauge-invariant diagnostics of Higgs, confinement, screening, generalized symmetries, boundaries, and lattice phase structure remain an important bridge between perturbative language and nonperturbative definitions."
---

## Summary

The **Higgs mechanism** is what happens when the Goldstone story is applied to a direction that has been gauged. For an ordinary global symmetry, spontaneous breaking gives a physical massless Goldstone mode. For a gauge redundancy, the would-be Goldstone field is not an independent physical particle. It becomes the longitudinal polarization of a massive gauge boson.

The slogan is

$$
\text{massless gauge field} + \text{would-be Goldstone}
\quad\longrightarrow\quad
\text{massive gauge field}.
$$

In four spacetime dimensions this is a degree-of-freedom count:

$$
2+1=3.
$$

A massless spin-one particle has two physical polarizations. A massive spin-one particle has three. The missing third polarization is supplied by the scalar phase that would have been a Goldstone boson if the symmetry had been global.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic Higgs-mechanism map. A gauge field and scalar phase combine into the gauge-invariant massive vector field, while the radial scalar remains as the Higgs excitation. The figure also contrasts gauge-fixed language with gauge-invariant physical content.](/figures/symmetry-anomalies-topology/higgs-mechanism-mass-bookkeeping.svg)

<figcaption>

In the Abelian Higgs model, the scalar phase $\pi$ and gauge field $A_\mu$ enter through the gauge-invariant combination $B_\mu=A_\mu-\partial_\mu\pi/(qv)$. The phase is not a physical massless Goldstone boson; it supplies the longitudinal polarization of a massive vector. The radial field $h$ remains as a scalar excitation.

</figcaption>
</figure>

The main warning is conceptual. It is common shorthand to say that a gauge symmetry is “spontaneously broken.” The shorthand is useful in perturbation theory, but it is not literally the same as breaking a physical global symmetry. A gauge symmetry is a redundancy of description. Physical statements must be phrased in gauge-invariant terms: spectra, correlation functions of gauge-invariant operators, screening behavior, line operators, boundary charges, and response to background fields.

## Prerequisites

Read [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/), [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/), [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/), and [Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) first.

For the gauge side, review [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/). The next chapter, [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/), turns the conceptual distinction into a systematic quantization framework.

## Core idea

A global symmetry maps one physical state to another physical state. If the vacuum is not invariant, there are physically distinct symmetry-related vacua. For a continuous internal symmetry, this produces Goldstone modes.

A gauge transformation changes variables inside a redundant description. Two field configurations related by an allowed gauge transformation represent the same physical configuration, unless the transformation has nontrivial boundary action or topological content. Therefore the phrase “breaking a local gauge symmetry” cannot mean the same thing as ordinary global spontaneous symmetry breaking.

The Higgs mechanism is the gauge-invariant fact that a theory with scalar fields and gauge fields can have a phase in which some gauge bosons are massive while the theory remains gauge consistent and local.

The simplest cartoon is

$$
\phi(x)=\frac{v+h(x)}{\sqrt2}e^{i\pi(x)/v}.
$$

For a global $U(1)$ symmetry, $\pi$ is the Goldstone field. For a local $U(1)$ gauge redundancy, the phase $\pi$ can be moved into the gauge field. The physical low-energy vector is not $A_\mu$ alone but the gauge-invariant combination

$$
B_\mu=A_\mu-\frac{1}{qv}\partial_\mu\pi.
$$

The Lagrangian then contains

$$
\frac12q^2v^2B_\mu B^\mu,
$$

which is a mass term for a physical vector excitation.

## Setup and conventions

We use the volume conventions: mostly-minus metric, $e^{-ip\cdot x}$ plane waves, Hermitian generators, and covariant derivatives of the form

$$
D_\mu=\partial_\mu-iqA_\mu
$$

for an Abelian field of charge $q$. Under a local gauge transformation with parameter $\alpha(x)$,

$$
\phi\longrightarrow e^{iq\alpha}\phi,
\qquad
A_\mu\longrightarrow A_\mu+\partial_\mu\alpha.
$$

With

$$
\phi=\frac{v+h}{\sqrt2}e^{i\pi/v},
$$

the fields transform as

$$
\pi\longrightarrow \pi+qv\alpha,
\qquad
h\longrightarrow h,
\qquad
A_\mu\longrightarrow A_\mu+\partial_\mu\alpha.
$$

Therefore

$$
B_\mu\equiv A_\mu-\frac{1}{qv}\partial_\mu\pi
$$

is gauge invariant.

:::note[Convention-sensitive source note]
The sign in $B_\mu=A_\mu-\partial_\mu\pi/(qv)$ follows from $D_\mu=\partial_\mu-iqA_\mu$ and $A_\mu\to A_\mu+\partial_\mu\alpha$. If one uses $D_\mu=\partial_\mu+iqA_\mu$ or the opposite gauge-transformation sign, the displayed $B_\mu$ changes sign accordingly. The invariant statement is that the scalar phase and gauge field appear in the covariant combination $\partial_\mu\pi-qvA_\mu$.
:::

## Abelian model

The standard Abelian Higgs model is

$$
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\phi)^*(D^\mu\phi)-V(\phi),
$$

with

$$
V(\phi)=\lambda\left(|\phi|^2-\frac{v^2}{2}\right)^2,
\qquad \lambda>0.
$$

If the $U(1)$ were global, the minima would form a circle and the phase around that circle would be a massless Goldstone mode. With the $U(1)$ gauged, points on that circle related by a local phase rotation are not distinct physical vacua.

Write

$$
\phi=\frac{v+h}{\sqrt2}e^{i\pi/v}.
$$

Then

$$
D_\mu\phi
=\frac{e^{i\pi/v}}{\sqrt2}
\left[\partial_\mu h+i(v+h)\left(\frac{\partial_\mu\pi}{v}-qA_\mu\right)\right].
$$

The kinetic term contains

$$
(D_\mu\phi)^*(D^\mu\phi)
=\frac12\partial_\mu h\partial^\mu h
+\frac12(v+h)^2\left(qA_\mu-\frac{\partial_\mu\pi}{v}\right)
\left(qA^\mu-\frac{\partial^\mu\pi}{v}\right).
$$

Using $B_\mu=A_\mu-\partial_\mu\pi/(qv)$, the leading quadratic terms are

$$
\mathcal L_{\rm quad}
=-\frac14F_{\mu\nu}(B)F^{\mu\nu}(B)
+\frac12q^2v^2B_\mu B^\mu
+\frac12\partial_\mu h\partial^\mu h
-\frac12(2\lambda v^2)h^2.
$$

Thus

$$
m_A^2=q^2v^2,
\qquad
m_h^2=2\lambda v^2.
$$

The phase field $\pi$ has disappeared from the gauge-invariant spectrum as an independent scalar. It has become the longitudinal polarization of the massive vector $B_\mu$.

## Where the Goldstone boson went

The Goldstone theorem assumed a physical global symmetry generated by a charge that acts nontrivially on local gauge-invariant operators. A pure gauge redundancy is not such a symmetry.

In the Abelian Higgs model, the gauge-fixed perturbative language may appear to contain a massless scalar $\pi$ before gauge fixing. But that field is gauge-dependent. It is not a gauge-invariant local particle.

The covariant-derivative term gives the clean answer:

$$
\frac12(v+h)^2\left(qA_\mu-\frac{\partial_\mu\pi}{v}\right)^2.
$$

This term says that long-wavelength changes of the phase can be compensated by the gauge field. Instead of an energetically cheap global rotation, the theory has a massive vector response.

This is also the field-theory version of the Anderson mechanism in superconductors. The would-be superfluid phase mode is not seen as a neutral massless Goldstone boson after coupling to electromagnetism. The electromagnetic field is screened; the photon acquires an effective mass in the medium, and the Meissner effect appears.

:::caution[Do not overread the gauge-fixed picture]
In a fixed gauge, one often writes $\langle\phi\rangle=v/\sqrt2$ and says that the gauge symmetry is broken. This is a calculational shorthand. The gauge-fixed field $\phi$ is not itself a gauge-invariant local observable. Gauge-invariant statements involve objects such as $\phi^\dagger\phi$, massive vector poles in gauge-invariant channels, screening lengths, line operators, and boundary charges.
:::

## Degree-of-freedom bookkeeping

The degree count is one of the best sanity checks.

In four spacetime dimensions, before the Higgs mechanism in the weakly coupled description:

| Field | Physical degrees of freedom |
|---|---:|
| massless gauge field $A_\mu$ | 2 |
| complex scalar $\phi$ | 2 |
| total | 4 |

After reorganizing around the Higgs phase:

| Field | Physical degrees of freedom |
|---|---:|
| massive vector $B_\mu$ | 3 |
| real scalar $h$ | 1 |
| total | 4 |

Nothing vanished. The variables reorganized.

This is why the phrase “the Goldstone is eaten” is useful but slightly cartoonish. A particle did not literally consume another particle. Rather, the physical field variables reorganized so that the scalar phase is part of the massive vector excitation.

## Gauge fixing and the same physics

Different gauges distribute the same physical degrees of freedom differently.

In **unitary gauge**, one uses a gauge transformation to set

$$
\pi=0.
$$

The Lagrangian displays a massive vector field directly. This makes the physical spectrum intuitive but can obscure ultraviolet power counting.

In **$R_\xi$ gauges**, one keeps $\pi$ in the Lagrangian and chooses a gauge-fixing term designed to cancel the quadratic mixing between $A_\mu$ and $\pi$. Schematically,

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}\left(\partial_\mu A^\mu+\text{sign}\cdot\xi m_A\pi\right)^2,
$$

where the displayed sign depends on the convention for $D_\mu$ and the gauge-fixing functional. In these gauges, $\pi$ appears as a gauge-dependent scalar with mass proportional to $\xi m_A^2$, and ghosts also appear in the quantized theory. Physical observables do not depend on $\xi$.

The point is not that one gauge is morally correct. The point is that the physical Higgs mechanism is independent of the gauge used to compute it.

## Non-Abelian pattern

For a non-Abelian gauge group $G$ with scalar fields in some representation, choose a weak-coupling scalar background $v$. The subgroup that leaves $v$ fixed is called $H$:

$$
H=\{g\in G\mid g\cdot v=v\}.
$$

Perturbatively, gauge bosons associated with generators that do not preserve $v$ acquire masses. Gauge bosons associated with generators of $H$ remain massless, unless further dynamics gives them a mass gap.

The mass matrix has the schematic form

$$
(M^2)_{ab}\sim g^2(T_av)^\dagger(T_bv),
$$

with representation and normalization factors depending on the scalar kinetic term. If $T_av=0$, the corresponding generator lies in the stabilizer and the gauge boson is massless at this stage. If $T_av\ne0$, that gauge direction participates in the Higgs mechanism.

The number of would-be Goldstone fields is locally

$$
\dim G-\dim H.
$$

These fields supply the longitudinal polarizations of the gauge bosons associated with $G/H$.

This is the perturbative meaning of the familiar phrase

$$
G\longrightarrow H.
$$

It does **not** mean that the local gauge redundancy $G$ was a physical global symmetry that literally broke. It means that the weakly coupled field variables are organized around a scalar background whose stabilizer is $H$, and the resulting spectrum contains massive vectors for the directions in $G/H$.

## Standard Model orientation

In the electroweak theory, one often writes

$$
SU(2)_L\times U(1)_Y\longrightarrow U(1)_{\rm em}.
$$

This notation summarizes the weakly coupled Higgs organization of the gauge boson spectrum. Three gauge boson combinations become massive: $W^+$, $W^-$, and $Z$. One combination remains massless: the photon.

Gauge-invariantly, the physical statements are that there are massive vector particles with the interactions of $W^\pm$ and $Z$, a massless electromagnetic gauge field in the low-energy description, a scalar Higgs excitation, and a consistent gauge theory whose quantization requires gauge fixing, ghosts, and anomaly cancellation.

## Elitzur’s theorem and physical order parameters

Elitzur’s theorem says, roughly, that a local gauge symmetry cannot be spontaneously broken by the expectation value of a local gauge-variant operator in a gauge-invariant formulation. For example,

$$
\langle\phi(x)\rangle=0
$$

in an unfixed gauge-invariant path integral, even in a Higgs phase.

This does not mean the Higgs mechanism is fake. It means the diagnostic was gauge-variant. Better diagnostics include gauge-invariant composite operators, screening lengths, Wilson and ’t Hooft line behavior, boundary charges, and background-field responses.

In some gauge theories with matter in fundamental representations, the Higgs and confinement regions may be analytically connected in the full lattice phase diagram. This is not a contradiction. The perturbative Higgs description can still be excellent in one region, while gauge-invariant diagnostics decide whether there is a sharp phase distinction.

## Higgs, Stueckelberg, and Proca masses

It is useful to compare three ways a vector can be massive.

A **Proca mass** writes

$$
\mathcal L_{\rm Proca}
=-\frac14F_{\mu\nu}F^{\mu\nu}+\frac12m^2A_\mu A^\mu.
$$

For an ordinary Abelian gauge field, this term is not gauge invariant.

A **Stueckelberg mass** writes

$$
\mathcal L_{\rm St}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12m^2\left(A_\mu-\frac1m\partial_\mu\sigma\right)^2,
$$

with

$$
A_\mu\to A_\mu+\partial_\mu\alpha,
\qquad
\sigma\to\sigma+m\alpha.
$$

The Stueckelberg scalar $\sigma$ makes the mass term gauge invariant. This is the Higgs mechanism without the radial Higgs excitation, at least in the simplest Abelian effective theory.

A **Higgs mass** arises from a scalar with a radial mode and a potential. At low energies below the radial mass, the Abelian Higgs model can reduce to a Stueckelberg-like description for the phase and vector.

## Common pitfalls

**“Gauge symmetry is spontaneously broken just like a global symmetry.”** Gauge symmetry is a redundancy. Gauge-fixed perturbation theory can use symmetry-breaking language, but physical claims must be gauge-invariant.

**“The Higgs mechanism violates Goldstone’s theorem.”** Goldstone’s theorem assumed a physical global symmetry. A gauged direction does not produce a physical Goldstone boson; the would-be Goldstone mode becomes a vector polarization.

**“The field expectation value is the observable.”** In an unfixed gauge, $\langle\phi\rangle$ is not a gauge-invariant local observable. The scalar excitation, vector mass, screening behavior, and gauge-invariant correlators are physical.

**“Unitary gauge proves the Goldstone field is absent.”** Unitary gauge hides the scalar phase by using gauge redundancy. Other gauges display the phase as an unphysical gauge-dependent field. The absence of a physical Goldstone boson is gauge-invariant; the disappearance of a variable is gauge choice.

**“Every massive vector mass is a Higgs mass.”** Proca, Stueckelberg, dynamical mass generation, confinement, thermal screening, and Higgs masses are conceptually different.

**“A Higgs phase is always sharply distinct from confinement.”** Not always. The answer depends on the gauge group, matter representation, global symmetries, line operators, and allowed probes.

## Relations to other pages

- [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) explains what would happen for an ordinary global symmetry.
- [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) explains why gauging changes the meaning of the symmetry.
- [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) describes gauging as summing over background fields.
- [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/) develops the language needed to quantize gauge theories without confusing redundancy with physical symmetry.
- The Gauge Theories and Standard Model volume will treat electroweak symmetry breaking, Higgs phenomenology, gauge fixing, ghosts, and renormalization in full detail.
- The Higher-Form and Generalized Symmetries chapter will provide sharper order parameters for confinement, screening, and Higgs-like phases using line operators and higher-form symmetry.

## Research status

The perturbative Higgs mechanism is established textbook physics and is part of the Standard Model. The gauge-invariant interpretation is also settled: local gauge redundancy is not an ordinary physical symmetry that breaks in the same sense as a global symmetry.

Active and subtle areas include nonperturbative phase diagrams, the relation between Higgs and confinement regions, line-operator diagnostics, boundary symmetries, generalized symmetries, Higgs phases in topologically ordered systems, and strongly coupled Higgs sectors.

## Exercises

### Exercise 1: Gauge-invariant vector combination

Let

$$
\phi=\frac{v+h}{\sqrt2}e^{i\pi/v},
\qquad
D_\mu=\partial_\mu-iqA_\mu,
$$

and

$$
\phi\to e^{iq\alpha}\phi,
\qquad
A_\mu\to A_\mu+\partial_\mu\alpha.
$$

Show that

$$
B_\mu=A_\mu-\frac{1}{qv}\partial_\mu\pi
$$

is gauge invariant.

<details><summary><strong>Solution</strong></summary>

The scalar phase transforms as

$$
\frac{\pi}{v}\to\frac{\pi}{v}+q\alpha,
$$

so

$$
\pi\to\pi+qv\alpha.
$$

Therefore

$$
\partial_\mu\pi\to\partial_\mu\pi+qv\partial_\mu\alpha.
$$

Then

$$
B_\mu\to A_\mu+\partial_\mu\alpha
-\frac{1}{qv}(\partial_\mu\pi+qv\partial_\mu\alpha)
=B_\mu.
$$

</details>

### Exercise 2: Vector and scalar masses

For

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}+|D_\mu\phi|^2
-\lambda\left(|\phi|^2-\frac{v^2}{2}\right)^2,
$$

with $D_\mu=\partial_\mu-iqA_\mu$ and $\phi=(v+h)e^{i\pi/v}/\sqrt2$, find $m_A^2$ and $m_h^2$.

<details><summary><strong>Solution</strong></summary>

The scalar kinetic term contains

$$
\frac12(v+h)^2\left(qA_\mu-\frac{\partial_\mu\pi}{v}\right)^2.
$$

At quadratic order this gives

$$
\frac12q^2v^2B_\mu B^\mu,
$$

so

$$
m_A^2=q^2v^2.
$$

For the radial field,

$$
|\phi|^2=\frac{(v+h)^2}{2}.
$$

Thus

$$
V=\lambda\left(vh+\frac12h^2\right)^2
=\lambda v^2h^2+O(h^3).
$$

Since the Lagrangian contains $-V$ and a scalar mass term is $-m_h^2h^2/2$, we get

$$
m_h^2=2\lambda v^2.
$$

</details>

### Exercise 3: Degree count in four dimensions

Count the physical degrees of freedom before and after the Abelian Higgs mechanism in four spacetime dimensions.

<details><summary><strong>Solution</strong></summary>

Before reorganizing the fields, a massless gauge boson has two physical transverse polarizations. A complex scalar has two real degrees of freedom. The total is $2+2=4$.

After the Higgs mechanism, the vector is massive and has three physical polarizations. The radial scalar remains as one real scalar. The total is $3+1=4$. The scalar phase became the longitudinal vector polarization.

</details>

### Exercise 4: Non-Abelian stabilizer

Let a scalar background $v$ transform in a representation of $G$. Explain why a generator $T_a$ satisfying $T_av=0$ corresponds to a massless gauge boson at the Higgs-mechanism level.

<details><summary><strong>Solution</strong></summary>

The gauge-boson mass matrix comes from the scalar kinetic term expanded around the background. The relevant piece is schematically

$$
(D_\mu v)^\dagger(D^\mu v)
\sim
 g^2 A_\mu^aA^{\mu b}(T_av)^\dagger(T_bv).
$$

If $T_av=0$, then the gauge field associated with $T_a$ does not appear in this mass term. Such generators preserve the background and form the Lie algebra of the stabilizer $H$. Their gauge bosons remain massless at this stage.

</details>

### Exercise 5: Why a local field expectation value is not enough

Why is $\langle\phi\rangle\ne0$ not a gauge-invariant definition of a Higgs phase?

<details><summary><strong>Solution</strong></summary>

The field $\phi$ is gauge-charged. Under a local gauge transformation it changes by a spacetime-dependent phase or representation matrix. Therefore its expectation value depends on gauge choice. In an unfixed gauge-invariant formulation, Elitzur’s theorem forbids such a local gauge-variant expectation value from serving as a physical order parameter.

A Higgs phase must instead be diagnosed by gauge-invariant information: the spectrum of gauge-invariant operators, massive vector poles, screening lengths, line-operator behavior, boundary charges, or other gauge-invariant responses.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Secret Symmetry: An Introduction to Spontaneous Symmetry Breakdown and Gauge Fields.”
- P. W. Anderson, “Plasmons, Gauge Invariance, and Mass,” *Physical Review* **130** (1963) 439–442.
- F. Englert and R. Brout, “Broken Symmetry and the Mass of Gauge Vector Mesons,” *Physical Review Letters* **13** (1964) 321–323.
- P. W. Higgs, “Broken Symmetries and the Masses of Gauge Bosons,” *Physical Review Letters* **13** (1964) 508–509.
- G. S. Guralnik, C. R. Hagen, and T. W. B. Kibble, “Global Conservation Laws and Massless Particles,” *Physical Review Letters* **13** (1964) 585–587.
- S. Elitzur, “Impossibility of Spontaneously Breaking Local Symmetries,” *Physical Review D* **12** (1975) 3978–3982.
- E. Fradkin and S. H. Shenker, “Phase Diagrams of Lattice Gauge Theories with Higgs Fields,” *Physical Review D* **19** (1979) 3682–3697.
- M. Srednicki, *Quantum Field Theory*, sections on spontaneously broken gauge theory and the Standard Model.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter on spontaneous symmetry breaking.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on spontaneously broken gauge theories.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry breaking and the Anderson–Higgs mechanism.

## Version history

- 2026-06-17: Initial polished draft. Added the gauge-invariant Abelian Higgs derivation, degree-of-freedom bookkeeping, non-Abelian mass-matrix preview, Elitzur-theorem warning, gauge-fixing caveats, and exercises.
