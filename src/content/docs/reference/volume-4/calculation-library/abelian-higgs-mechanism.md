---
title: "Abelian Higgs Mechanism"
description: "A worked calculation of the Abelian Higgs mechanism: vacuum expansion, gauge-invariant vector field, masses, R_xi gauge, and degree-of-freedom counting."
sidebar:
  label: "Abelian Higgs Mechanism"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§84–85; Schwartz §28.3–28.4; Coleman, Secret Symmetry; Burgess §7.2.4."
topics:
  - Abelian Higgs model
  - Higgs mechanism
  - spontaneous gauge-symmetry breaking
  - Goldstone modes
  - gauge boson mass
  - R_xi gauge
canonicalTopics:
  - abelian-higgs-mechanism
  - higgs-mechanism
  - massive-vector-boson
  - goldstone-mode-in-gauge-theory
researchStatus:
  established:
    - "The Abelian Higgs model is the simplest complete calculation showing how a gauge field acquires a mass without explicitly breaking gauge invariance."
  active:
    - "Nonperturbative questions about vortices, phases, global structure, and the precise distinction between Higgs and confinement regimes require additional tools beyond this local perturbative calculation."
---

## Summary

This page derives the Higgs mechanism in the simplest gauge theory with a complex scalar field. The model is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\phi)^\dagger D^\mu\phi
-V(\phi),
\qquad
D_\mu=\partial_\mu+iqA_\mu,
$$

with

$$
V(\phi)=-\mu^2|\phi|^2+\lambda |\phi|^4,
\qquad
\mu^2>0,
\qquad
\lambda>0.
$$

The vacuum has

$$
|\phi|=\frac{v}{\sqrt2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

After expanding around the vacuum, the spectrum contains

$$
m_A=|q|v,
\qquad
m_h^2=2\lambda v^2=2\mu^2.
$$

The phase field that would have been a Goldstone boson for a broken global $U(1)$ does not appear as a physical massless scalar. It becomes the longitudinal polarization of the massive vector field.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Abelian Higgs calculation flow](/figures/gauge-theories-standard-model/abelian-higgs-calculation-flow.svg)

<figcaption>

The Abelian Higgs mechanism reorganizes the two real components of a charged scalar and the two transverse photon polarizations into one real Higgs scalar and one massive vector with three physical polarizations.

</figcaption>
</figure>

The word “mechanism” is doing useful work here. Gauge invariance is not broken as a redundancy. What changes is the most convenient set of variables and the spectrum around a chosen vacuum.

## Setup and gauge convention

We use the volume convention

$$
D_\mu=\partial_\mu+iqA_\mu.
$$

A local $U(1)$ gauge transformation is therefore

$$
\phi(x)\mapsto e^{-iq\alpha(x)}\phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

Then

$$
D_\mu\phi\mapsto e^{-iq\alpha}D_\mu\phi,
$$

and the Lagrangian is gauge invariant.

The scalar potential is minimized when

$$
0=\frac{\partial V}{\partial |\phi|}
=
-2\mu^2|\phi|+4\lambda |\phi|^3.
$$

Besides the unstable point $\phi=0$, the circle of minima is

$$
|\phi|^2=\frac{\mu^2}{2\lambda}.
$$

It is convenient to write

$$
|\phi|=\frac{v}{\sqrt2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

At first glance this looks exactly like spontaneous breaking of a global $U(1)$: the set of minima is a circle. The important difference is that points on this circle are gauge-related. Moving around the circle is not moving through distinct physical vacua; it is moving along a redundant coordinate.

## Gauge-invariant variables

Use polar variables

$$
\phi(x)=\frac{v+h(x)}{\sqrt2}\,e^{-i\theta(x)/v}.
$$

Under the gauge transformation above,

$$
\theta(x)\mapsto \theta(x)+qv\alpha(x),
\qquad
h(x)\mapsto h(x).
$$

The combination

$$
B_\mu
=
A_\mu-\frac{1}{qv}\partial_\mu\theta
$$

is gauge invariant:

$$
B_\mu\mapsto
A_\mu+\partial_\mu\alpha
-
\frac{1}{qv}\partial_\mu(\theta+qv\alpha)
=B_\mu.
$$

Now compute the covariant derivative:

$$
D_\mu\phi
=
\frac{e^{-i\theta/v}}{\sqrt2}
\left[
\partial_\mu h
+i(v+h)\left(qA_\mu-\frac1v\partial_\mu\theta\right)
\right].
$$

Using $qA_\mu-(1/v)\partial_\mu\theta=qB_\mu$, this gives

$$
(D_\mu\phi)^\dagger D^\mu\phi
=
\frac12(\partial_\mu h)(\partial^\mu h)
+
\frac12q^2(v+h)^2B_\mu B^\mu.
$$

The field strength is unchanged by the shift $A_\mu\mapsto B_\mu$ because the extra piece is a derivative:

$$
F_{\mu\nu}(A)=\partial_\mu A_\nu-\partial_\nu A_\mu
=
\partial_\mu B_\nu-\partial_\nu B_\mu
=F_{\mu\nu}(B).
$$

So the Lagrangian becomes

$$
\mathcal L
=
-\frac14F_{\mu\nu}(B)F^{\mu\nu}(B)
+
\frac12(\partial h)^2
+
\frac12q^2(v+h)^2B_\mu B^\mu
-V\!\left(\frac{v+h}{\sqrt2}\right).
$$

This is already the Higgs mechanism in its cleanest local form. The gauge-invariant vector field $B_\mu$ has acquired a mass term.

## Scalar mass and vector mass

Expand the potential:

$$
V\!\left(\frac{v+h}{\sqrt2}\right)
=
-\frac{\mu^2}{2}(v+h)^2
+
\frac{\lambda}{4}(v+h)^4.
$$

Using $\mu^2=\lambda v^2$, the linear term vanishes, and the quadratic term is

$$
V
=
V_0+
\lambda v^2h^2+
\lambda v h^3+
\frac{\lambda}{4}h^4.
$$

Since the Lagrangian contains $-V$, the quadratic scalar term is

$$
-\lambda v^2h^2=-\frac12(2\lambda v^2)h^2.
$$

Thus

$$
m_h^2=2\lambda v^2.
$$

The vector mass term comes from

$$
\frac12q^2(v+h)^2B_\mu B^\mu
=
\frac12q^2v^2B_\mu B^\mu
+q^2vhB_\mu B^\mu
+\frac12q^2h^2B_\mu B^\mu.
$$

Therefore

$$
m_A^2=q^2v^2.
$$

The first term is the mass term. The next two terms are the $hBB$ and $hhBB$ interactions. This is one of the nicest features of the Higgs mechanism: the same covariant derivative that creates the vector mass also fixes the Higgs–vector couplings.

## Degree-of-freedom counting

Before expanding around the vacuum, the field content is

| field | physical degrees of freedom |
|---|---:|
| massless Abelian gauge field $A_\mu$ | 2 |
| complex scalar $\phi$ | 2 |
| total | 4 |

After the Higgs mechanism, the local perturbative spectrum is

| field | physical degrees of freedom |
|---|---:|
| massive vector $B_\mu$ | 3 |
| real scalar $h$ | 1 |
| total | 4 |

No degree of freedom vanished. The would-be Goldstone mode supplied the longitudinal polarization of the massive vector.

This is often summarized by saying that the gauge field “eats” the Goldstone boson. Good mental image, slightly cannibalistic, but safe if you remember that nothing physical is lost.

## Unitary gauge

The polar form suggests a particularly direct gauge choice. Choose

$$
\alpha(x)=-\frac{\theta(x)}{qv}.
$$

Then

$$
\theta(x)\mapsto 0,
$$

and

$$
\phi(x)=\frac{v+h(x)}{\sqrt2}.
$$

This is **unitary gauge**. In this gauge the Lagrangian contains only the physical fields $h$ and the massive vector. It makes the spectrum transparent.

The price is that perturbative power counting is less transparent. The massive-vector propagator in unitary gauge has bad-looking high-momentum behavior. Gauge-invariant observables remain well behaved in a renormalizable Higgs model, but actual loop calculations are usually easier in a covariant $R_\xi$ gauge.

## The same calculation in Rξ gauge

For perturbation theory, use the Cartesian expansion

$$
\phi=\frac{1}{\sqrt2}(v+h+i\chi).
$$

To quadratic order,

$$
(D_\mu\phi)^\dagger D^\mu\phi
=
\frac12(\partial h)^2
+
\frac12(\partial\chi)^2
+qv A_\mu\partial^\mu\chi
+
\frac12q^2v^2A_\mu A^\mu
+\cdots.
$$

Let

$$
m_A=qv
$$

for $q>0$; otherwise replace it by $|q|v$ in the final mass formula. The quadratic Lagrangian contains a mixing term

$$
m_A A_\mu\partial^\mu\chi.
$$

After integrating by parts, this is

$$
-m_A\chi\,\partial_\mu A^\mu,
$$

up to a boundary term. The standard $R_\xi$ gauge-fixing term is

$$
\mathcal L_{\rm gf}
=
-\frac{1}{2\xi}\left(\partial_\mu A^\mu-\xi m_A\chi\right)^2.
$$

Its cross term cancels the $A_\mu$–$\chi$ mixing. The quadratic Lagrangian becomes diagonal:

$$
\mathcal L_2
=
-\frac14F_{\mu\nu}F^{\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2
+
\frac12m_A^2A_\mu A^\mu
+
\frac12(\partial h)^2-\frac12m_h^2h^2
+
\frac12(\partial\chi)^2-\frac12\xi m_A^2\chi^2.
$$

The field $\chi$ now appears as a gauge-dependent scalar with mass

$$
m_\chi^2=\xi m_A^2.
$$

It is not a physical particle. Its role is to keep covariance and power counting under control in intermediate calculations. Gauge-independent observables cannot depend on $\xi$.

Common special choices are

| gauge | value of $\xi$ | feature |
|---|---:|---|
| Landau gauge | $\xi=0$ | transverse gauge-field propagator; massless would-be Goldstone in perturbation theory |
| Feynman–'t Hooft gauge | $\xi=1$ | gauge and Goldstone masses match: $m_\chi=m_A$ |
| unitary-gauge limit | $\xi\to\infty$ | would-be Goldstone decouples formally; propagator power counting is less friendly |

## Gauge symmetry is not literally broken

It is common to say that a gauge symmetry is spontaneously broken. In calculations, this phrase is convenient; in interpretation, it is dangerous.

A gauge symmetry is a redundancy in description. Redundancies are not physical symmetries that can be broken in the same sense as a global spin-rotation symmetry in a ferromagnet. What is physical is that the vacuum supports a local perturbative spectrum with massive vector particles.

The cleaner statement is:

> The scalar field has a nonzero gauge-dependent order-parameter-like expectation value in a chosen gauge, and the gauge-invariant spectrum around the Higgs regime contains a massive vector and a scalar Higgs excitation.

For many perturbative Standard Model calculations, the traditional phrase “broken gauge symmetry” is harmless shorthand. For nonperturbative questions about phases, confinement, center symmetry, and line operators, the distinction becomes load-bearing.

## Checks

### Gauge-invariant vector check

The combination

$$
B_\mu=A_\mu-\frac1{qv}\partial_\mu\theta
$$

is invariant under the simultaneous transformation of $A_\mu$ and $\theta$. Therefore the mass term

$$
\frac12q^2v^2B_\mu B^\mu
$$

is gauge invariant even though a naive term $\frac12m^2A_\mu A^\mu$ would not be.

### Global limit check

If $q\to0$, the scalar phase can no longer be absorbed into the gauge field. The model becomes a global $U(1)$ theory with one massive radial mode and one massless Goldstone boson. Correspondingly,

$$
m_A=|q|v\to0.
$$

### Unbroken phase check

If $\mu^2<0$ in the potential written as $V=-\mu^2|\phi|^2+\lambda|\phi|^4$, then the stable minimum is at $\phi=0$. There is no vector mass term, and the gauge field remains massless.

## Common mistakes

**Mistake 1: Treating $\theta$ as a physical Goldstone boson.** In the gauge theory, the phase is gauge-dependent. It is not an additional physical massless particle.

**Mistake 2: Calling $\langle\phi\rangle$ gauge invariant.** The expectation value of a charged field depends on gauge choice. The mass spectrum and gauge-invariant correlation functions are the physical data.

**Mistake 3: Losing the charge $q$.** If the scalar has charge $q$, then $m_A=|q|v$. In the Standard Model, the relevant charges are encoded in the $SU(2)$ and hypercharge generators, not a single scalar $q$.

**Mistake 4: Forgetting the normalization of $v$.** We use $\phi=(v+h)/\sqrt2$ in unitary gauge. With this convention $m_A=|q|v$ and $m_h^2=2\lambda v^2$.

**Mistake 5: Thinking unitary gauge proves renormalizability.** Unitary gauge displays the physical spectrum. Covariant gauges and BRST structure are usually better for proving or organizing renormalizability.

## Exercises

### Exercise 1: Expand the potential

Starting from

$$
V=-\frac{\mu^2}{2}(v+h)^2+\frac{\lambda}{4}(v+h)^4,
\qquad
v^2=\frac{\mu^2}{\lambda},
$$

show that the coefficient of $h^2$ in $V$ is $\lambda v^2$.

<details><summary><strong>Solution</strong></summary>

Expand:

$$
V=
-\frac{\mu^2}{2}(v^2+2vh+h^2)
+\frac{\lambda}{4}(v^4+4v^3h+6v^2h^2+4vh^3+h^4).
$$

The linear coefficient is

$$
-\mu^2v+\lambda v^3=v(-\mu^2+\lambda v^2)=0.
$$

The quadratic coefficient is

$$
-\frac{\mu^2}{2}+\frac{3\lambda v^2}{2}
=
-\frac{\lambda v^2}{2}+\frac{3\lambda v^2}{2}
=\lambda v^2.
$$

Since $\mathcal L$ contains $-V$, this corresponds to

$$
-\lambda v^2h^2=-\frac12(2\lambda v^2)h^2,
$$

so $m_h^2=2\lambda v^2$.

</details>

### Exercise 2: Gauge invariance of Bμ

Verify that

$$
B_\mu=A_\mu-\frac1{qv}\partial_\mu\theta
$$

is invariant under

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
\theta\mapsto\theta+qv\alpha.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the transformed fields:

$$
B_\mu\mapsto
A_\mu+\partial_\mu\alpha
-
\frac1{qv}\partial_\mu(\theta+qv\alpha)
=
A_\mu+\partial_\mu\alpha
-
\frac1{qv}\partial_\mu\theta
-
\partial_\mu\alpha
=B_\mu.
$$

</details>

### Exercise 3: Cancel the Rξ mixing term

Show that the gauge-fixing term

$$
\mathcal L_{\rm gf}
=
-\frac1{2\xi}(\partial_\mu A^\mu-\xi m_A\chi)^2
$$

cancels the quadratic mixing $m_AA_\mu\partial^\mu\chi$ up to a boundary term.

<details><summary><strong>Solution</strong></summary>

The scalar kinetic term contains

$$
m_AA_\mu\partial^\mu\chi.
$$

Integrating by parts gives

$$
m_AA_\mu\partial^\mu\chi
=
-m_A\chi\,\partial_\mu A^\mu
$$

up to a boundary term. Expanding the gauge-fixing term gives

$$
\mathcal L_{\rm gf}
=
-\frac1{2\xi}(\partial\cdot A)^2
+m_A\chi\,\partial\cdot A
-\frac12\xi m_A^2\chi^2.
$$

The cross term cancels the integrated-by-parts mixing.

</details>

## Related pages

- [Abelian Higgs Model](/gauge-theories-standard-model/higgs-sector/abelian-higgs-model/) gives the conceptual introduction to this model.
- [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/) generalizes the degree-of-freedom counting to non-Abelian gauge groups.
- [Goldstone Equivalence Theorem](/gauge-theories-standard-model/higgs-sector/goldstone-equivalence-theorem/) explains why longitudinal vector scattering remembers the would-be Goldstone modes at high energy.
- [Electroweak Gauge-Boson Masses](/gauge-theories-standard-model/calculation-library/electroweak-gauge-boson-masses/) applies the same logic to the Standard Model Higgs doublet.

## References

- Srednicki, *Quantum Field Theory*, §§84–85.
- Schwartz, *Quantum Field Theory and the Standard Model*, §§28.3–28.4.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry.”
- Burgess, *Introduction to Effective Field Theory*, §7.2.4.

## Version history

- **2026-06-19:** Initial polished draft. Derived the Abelian Higgs spectrum using gauge-invariant variables and added the $R_\xi$ gauge diagonalization check.
