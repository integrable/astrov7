---
title: "Klein–Gordon Field"
description: "The free spin-zero relativistic field: real and complex scalar fields, Klein–Gordon equation, mode expansions, commutators, conserved charge, and propagator conventions."
sidebar:
  label: "Klein–Gordon Field"
  order: 1
---

## Summary

The Klein–Gordon field is the free relativistic field of spin zero. In qft.org conventions, the real scalar Lagrangian is

$$
\mathcal L_0=\frac12\partial_\mu\phi\,\partial^\mu\phi-\frac12m^2\phi^2,
$$

and its equation of motion is

$$
\boxed{(\Box+m^2)\phi=0.}
$$

A plane wave $e^{-ip\cdot x}$ solves this equation when

$$
p^2=m^2,
\qquad
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The quantized real field has the mode expansion

$$
\boxed{
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
\qquad
 d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
}
$$

The field is Hermitian, so it describes a neutral, self-conjugate spin-zero particle. A complex Klein–Gordon field instead has two independent oscillator species,

$$
\Phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and describes charged spin-zero particles and antiparticles. The scalar Feynman propagator is

$$
\boxed{
D_F(x-y)
=\langle0|T\phi(x)\phi(y)|0\rangle
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

It satisfies

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

Srednicki treats the spin-zero field as the first full example of canonical QFT; Coleman constructs the scalar field from relativistic causality; Weinberg places scalar fields inside the general construction of causal quantum fields and the canonical formalism (Srednicki 2007, §§1–5 and 8; Coleman 2019, chs. 3–4; Weinberg 1995, Vol. I, §§5.1–5.2, 6.2, and 7.1–7.2).

## Prerequisites

You should know [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Normal Ordering](/foundations/canonical-quantization/normal-ordering/), and [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/). We use the conventions fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$, and scalar propagator denominator $p^2-m^2+i\epsilon$.

## Core idea

The Klein–Gordon field is the scalar reference object for the whole Foundations section. It is simultaneously:

- the simplest Lorentz-invariant field equation;
- the simplest example of a relativistic operator-valued field;
- the prototype for particle creation and annihilation;
- the denominator that later reappears in scalar propagators, loop integrals, and path integrals.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Klein–Gordon field map from Lagrangian to modes, commutators, propagators, and Fock space](/figures/foundations/kg-free-field-map.svg)

<figcaption>

The free Klein–Gordon field is controlled by one scalar kinetic operator. The Lagrangian gives $K=\Box+m^2$; plane waves obey $p^2=m^2$; canonical quantization turns the modes into ladder operators; the commutator encodes causal support; and the Feynman propagator is the time-ordered inverse of $K$.

</figcaption>
</figure>

This page is deliberately reference-like. The earlier scalar pages explained how to get here. This page collects the free-field facts you will keep reusing.

:::note[Assumptions]
This page treats free scalar fields on flat Minkowski spacetime. The operator fields are distributions, so products at the same spacetime point require regulation or interpretation. Interactions, renormalization, composite operators, and curved backgrounds are not part of this page.
:::

## Definitions

The real Klein–Gordon field is a Hermitian scalar field,

$$
\phi(x)^\dagger=\phi(x),
$$

with free action

$$
S_0[\phi]=\int d^4x\,
\left[\frac12\partial_\mu\phi\,\partial^\mu\phi-\frac12m^2\phi^2\right].
$$

The complex Klein–Gordon field is a complex scalar field $\Phi(x)$ with independent conjugate $\Phi^\dagger(x)$ and action

$$
S_0[\Phi,\Phi^\dagger]=\int d^4x\,
\left[\partial_\mu\Phi^\dagger\partial^\mu\Phi-m^2\Phi^\dagger\Phi\right].
$$

The word “scalar” means that under a proper Lorentz transformation $x\mapsto \Lambda x$,

$$
\phi'(x')=\phi(x),
\qquad
\Phi'(x')=\Phi(x).
$$

A scalar field has no Lorentz index and no spinor index. It may still carry internal labels, such as charge or flavor.

## Real scalar field

Varying the real scalar action gives

$$
\delta S_0
=\int d^4x\,\left[-(\Box+m^2)\phi\right]\delta\phi
+\text{boundary term}.
$$

With boundary variations set to zero, stationarity gives

$$
(\Box+m^2)\phi=0.
$$

Using $e^{-ip\cdot x}$ and qft.org's mostly-minus metric,

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}.
$$

Therefore the equation of motion imposes

$$
-p^2+m^2=0,
$$

or

$$
p^2=m^2.
$$

The real quantum field is expanded as

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
\qquad
p^0=E_{\mathbf p}>0.
$$

The oscillator algebra is

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

with all $[a,a]$ and $[a^\dagger,a^\dagger]$ commutators zero. The vacuum is defined by

$$
a(\mathbf p)|0\rangle=0.
$$

The one-particle state is

$$
|\mathbf p\rangle=a^\dagger(\mathbf p)|0\rangle,
$$

with normalization

$$
\langle\mathbf p|\mathbf q\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

After normal ordering, the energy and momentum operators are

$$
:H:=\int d\mu(p)\,E_{\mathbf p}a^\dagger(\mathbf p)a(\mathbf p),
$$

and

$$
\mathbf P=\int d\mu(p)\,\mathbf p\,a^\dagger(\mathbf p)a(\mathbf p).
$$

Thus $a^\dagger(\mathbf p)$ creates a particle with energy $E_{\mathbf p}$ and momentum $\mathbf p$.

## Complex scalar field

The free complex scalar equation is

$$
(\Box+m^2)\Phi=0,
\qquad
(\Box+m^2)\Phi^\dagger=0.
$$

The mode expansion is

$$
\Phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and

$$
\Phi^\dagger(x)=\int d\mu(p)\,
\left[a^\dagger(\mathbf p)e^{ip\cdot x}+b(\mathbf p)e^{-ip\cdot x}\right].
$$

The nonzero oscillator commutators are

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

and

$$
[b(\mathbf p),b^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

The normal-ordered Hamiltonian is

$$
:H:=\int d\mu(p)\,E_{\mathbf p}
\left[a^\dagger(\mathbf p)a(\mathbf p)+b^\dagger(\mathbf p)b(\mathbf p)\right].
$$

For the phase convention

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
\Phi^\dagger\mapsto e^{iq\alpha}\Phi^\dagger,
$$

the Noether current is

$$
j^\mu=iq\,\Phi^\dagger\overleftrightarrow{\partial^\mu}\Phi
=iq\left(\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right),
$$

and the normal-ordered charge is

$$
\boxed{
Q=q\int d\mu(p)\,
\left[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)\right].
}
$$

So $a^\dagger$ creates a particle of charge $+q$, while $b^\dagger$ creates an antiparticle of charge $-q$. The antiparticle is not a negative-energy excitation; it is a positive-energy excitation in the conjugate charge sector.

## Green functions and commutators

The positive-frequency Wightman function of the real scalar field is

$$
\Delta^+(x-y)
\equiv \langle0|\phi(x)\phi(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

The field commutator is

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

where

$$
i\Delta(x-y)
=\Delta^+(x-y)-\Delta^+(y-x).
$$

The Pauli–Jordan function $\Delta$ solves the homogeneous Klein–Gordon equation in each argument and vanishes for spacelike separation:

$$
\Delta(x-y)=0
\qquad\text{if}\qquad
(x-y)^2<0.
$$

This is the free scalar realization of microcausality:

$$
[\phi(x),\phi(y)]=0
\qquad\text{for spacelike }x-y.
$$

For the complex scalar field,

$$
[\Phi(x),\Phi(y)]=0,
\qquad
[\Phi^\dagger(x),\Phi^\dagger(y)]=0,
$$

and

$$
[\Phi(x),\Phi^\dagger(y)]=i\Delta(x-y).
$$

The nonzero Wightman functions are

$$
\langle0|\Phi(x)\Phi^\dagger(y)|0\rangle=\Delta^+(x-y),
$$

and

$$
\langle0|\Phi^\dagger(x)\Phi(y)|0\rangle=\Delta^+(x-y),
$$

while

$$
\langle0|\Phi(x)\Phi(y)|0\rangle=0,
\qquad
\langle0|\Phi^\dagger(x)\Phi^\dagger(y)|0\rangle=0.
$$

Those zeros express charge conservation in the free vacuum.

## Feynman propagator

The scalar Feynman propagator is the time-ordered vacuum two-point function:

$$
D_F(x-y)=\langle0|T\phi(x)\phi(y)|0\rangle.
$$

In terms of Wightman functions,

$$
D_F(x-y)
=\theta(x^0-y^0)\Delta^+(x-y)
+\theta(y^0-x^0)\Delta^+(y-x).
$$

In momentum space,

$$
D_F(x-y)
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ prescription specifies how the two poles in $p^0$ are displaced:

$$
p^0=+E_{\mathbf p}-i\epsilon,
\qquad
p^0=-E_{\mathbf p}+i\epsilon,
$$

schematically. This is not the same object as the retarded Green function. The Feynman propagator is adapted to vacuum perturbation theory; retarded and advanced Green functions are adapted to causal response.

Applying the Klein–Gordon operator gives

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

The factor of $-i$ is a convention consequence of defining $D_F$ as $\langle T\phi\phi\rangle$ while the momentum-space internal scalar line is $i/(p^2-m^2+i\epsilon)$.

For the complex scalar field, the charged propagators are

$$
\langle0|T\Phi(x)\Phi^\dagger(y)|0\rangle=D_F(x-y),
$$

and

$$
\langle0|T\Phi^\dagger(x)\Phi(y)|0\rangle=D_F(x-y),
$$

while $\langle T\Phi\Phi\rangle$ and $\langle T\Phi^\dagger\Phi^\dagger\rangle$ vanish in the charge-conserving vacuum.

## Reference table

| Object | Real scalar | Complex scalar |
|---|---|---|
| Field condition | $\phi^\dagger=\phi$ | $\Phi$ and $\Phi^\dagger$ independent |
| Free equation | $(\Box+m^2)\phi=0$ | $(\Box+m^2)\Phi=0$ |
| Particle content | one neutral species | particle and antiparticle |
| Internal symmetry | none generically | global $U(1)$ phase rotation |
| Charge | no independent charge | $Q=q(N_a-N_b)$ |
| Propagator denominator | $p^2-m^2+i\epsilon$ | same |
| Mass dimension in four dimensions | $1$ | $1$ |
| Spin | $0$ | $0$ |

## Massless limit

When $m=0$, the equation becomes

$$
\Box\phi=0.
$$

The massless scalar has dispersion relation

$$
E_{\mathbf p}=|\mathbf p|.
$$

Classically, the massless free scalar also has a shift symmetry

$$
\phi\mapsto \phi+c
$$

if no potential is present. In quantum field theory, massless scalars have additional infrared subtleties, especially in low spacetime dimensions and in theories with derivative couplings. The massless limit is therefore not always interchangeable with setting $m=0$ at the end of a calculation.

## Common pitfalls

**Reading the Klein–Gordon equation as a single-particle probability equation.** The free equation is perfectly good as a field equation. The old single-particle interpretation is where the probability-density trouble appears.

**Calling the $e^{ip\cdot x}$ term a negative-energy particle.** In the quantum field, that term is the creation part. The created state has positive energy $E_{\mathbf p}$.

**Forgetting that complex means two real fields.** A free complex scalar has twice the real scalar's oscillator content and, before normal ordering, twice its zero-point energy.

**Mixing up Green functions.** Wightman functions, commutator functions, Feynman propagators, and retarded propagators are related, but they answer different questions.

**Dropping the $i\epsilon$.** The denominator $p^2-m^2$ alone does not define a distribution. The prescription is part of the definition of the Feynman propagator.

## Relation to other topics

- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) derives the real scalar mode expansion and oscillator algebra.
- [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) derives the charged particle-antiparticle Fock space.
- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) explains the Pauli–Jordan function and scalar microcausality.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) will define time-ordered products systematically.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) will focus on the $i\epsilon$ prescription and inverse-operator viewpoint.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) will rederive the same free propagator from a Gaussian functional integral.
- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) will perturb this free theory by adding interactions such as $\phi^3$ or $\phi^4$.

## Research status

- **Established:** The free real and complex Klein–Gordon fields, mode expansions, canonical commutators, charge operator, and Feynman propagator are textbook-standard.
- **Subtle:** Products of fields at coincident points require regularization. Interacting scalar fields require renormalization and, beyond perturbation theory, careful construction.
- **Out of scope here:** Interacting scalar QFT, spontaneous symmetry breaking, Källén–Lehmann spectral representation, and Euclidean reconstruction.

## Exercises

### Exercise 1: Derive the Klein–Gordon equation

Starting from

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2,
$$

show that the Euler–Lagrange equation is $(\Box+m^2)\phi=0$.

<details>
<summary><strong>Solution</strong></summary>

The Euler–Lagrange equation is

$$
\partial_\mu\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}
-\frac{\partial\mathcal L}{\partial\phi}=0.
$$

Here

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi,
\qquad
\frac{\partial\mathcal L}{\partial\phi}=-m^2\phi.
$$

Therefore

$$
\partial_\mu\partial^\mu\phi+m^2\phi=0,
$$

or

$$
(\Box+m^2)\phi=0.
$$

</details>

### Exercise 2: Check the mass shell

Use $\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}$ to show that a plane wave solves the Klein–Gordon equation exactly when $p^2=m^2$.

<details>
<summary><strong>Solution</strong></summary>

Substitute $\phi(x)=e^{-ip\cdot x}$ into the equation:

$$
(\Box+m^2)e^{-ip\cdot x}=(-p^2+m^2)e^{-ip\cdot x}.
$$

This vanishes if and only if

$$
p^2=m^2.
$$

For a positive-energy massive mode, this gives

$$
p^0=E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

</details>

### Exercise 3: Verify the propagator equation

Show that

$$
D_F(x)=\int\frac{d^4p}{(2\pi)^4}\frac{i e^{-ip\cdot x}}{p^2-m^2+i\epsilon}
$$

satisfies

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Acting on the exponential gives

$$
(\Box+m^2)e^{-ip\cdot x}=(-p^2+m^2)e^{-ip\cdot x}=-(p^2-m^2)e^{-ip\cdot x}.
$$

Thus

$$
(\Box+m^2)D_F(x)
=\int\frac{d^4p}{(2\pi)^4}\frac{-i(p^2-m^2)e^{-ip\cdot x}}{p^2-m^2+i\epsilon}.
$$

As a distribution, the ratio tends to $1$ away from the pole, with the prescription defining the singular part. Therefore

$$
(\Box+m^2)D_F(x)
=-i\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}
=-i\delta^{(4)}(x).
$$

</details>

### Exercise 4: Charge of a complex scalar quantum

Given

$$
Q=q\int d\mu(p)\,[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)],
$$

show that $a^\dagger(\mathbf q)|0\rangle$ has charge $+q$ and $b^\dagger(\mathbf q)|0\rangle$ has charge $-q$.

<details>
<summary><strong>Solution</strong></summary>

Using the oscillator algebra,

$$
[Q,a^\dagger(\mathbf q)]=q a^\dagger(\mathbf q),
\qquad
[Q,b^\dagger(\mathbf q)]=-q b^\dagger(\mathbf q).
$$

Since $Q|0\rangle=0$,

$$
Q a^\dagger(\mathbf q)|0\rangle
=[Q,a^\dagger(\mathbf q)]|0\rangle
=q a^\dagger(\mathbf q)|0\rangle,
$$

and

$$
Q b^\dagger(\mathbf q)|0\rangle
=[Q,b^\dagger(\mathbf q)]|0\rangle
=-q b^\dagger(\mathbf q)|0\rangle.
$$

</details>

### Exercise 5: Mass dimension of the scalar field

In $d$ spacetime dimensions, show that the free scalar has mass dimension

$$
[\phi]=\frac{d-2}{2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless and

$$
S=\int d^dx\,\mathcal L.
$$

Since $[d^dx]=-d$, the Lagrangian density has dimension $d$. The kinetic term has dimension

$$
[\partial_\mu\phi\partial^\mu\phi]=2+2[\phi].
$$

Therefore

$$
2+2[\phi]=d,
$$

so

$$
[\phi]=\frac{d-2}{2}.
$$

In four dimensions, $[\phi]=1$.

</details>

### Exercise 6: Wightman function solves the homogeneous equation

Show that

$$
\Delta^+(x)=\int d\mu(p)\,e^{-ip\cdot x}
$$

satisfies $(\Box+m^2)\Delta^+(x)=0$ for $x\ne0$.

<details>
<summary><strong>Solution</strong></summary>

Every mode in the integral is on shell:

$$
p^2=m^2.
$$

Therefore

$$
(\Box+m^2)e^{-ip\cdot x}=(-p^2+m^2)e^{-ip\cdot x}=0.
$$

Acting mode by mode gives

$$
(\Box+m^2)\Delta^+(x)=0
$$

away from possible distributional singularities at coincident points.

</details>

## References

### Primary references

- O. Klein, “Quantentheorie und fünfdimensionale Relativitätstheorie,” *Zeitschrift für Physik* **37** (1926), for early appearances of the relativistic scalar wave equation.
- W. Gordon, “Der Comptoneffekt nach der Schrödingerschen Theorie,” *Zeitschrift für Physik* **40** (1926), for another early use of the equation now called Klein–Gordon.
- W. Pauli and V. Weisskopf, “Über die Quantisierung der skalaren relativistischen Wellengleichung,” *Helvetica Physica Acta* **7** (1934), for interpreting the scalar relativistic wave equation as a quantum field theory.

### Standard textbook treatments

- M. Srednicki, *Quantum Field Theory*, §§1–5 and 8, for the scalar field, canonical quantization, propagators, and path-integral viewpoint.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3–4 and 13, for the scalar field, causality, normal ordering, and Green functions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.1–5.2, 6.2, and 7.1–7.2, for scalar fields as causal fields, propagators, and canonical variables.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.3, I.8, and Appendix A, for the scalar field, canonical quantization, and Gaussian propagator logic.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, ch. 2, for the standard graduate introduction to the real and complex scalar field.

### For a first pass

- Srednicki, §§1–5.
- Coleman, chs. 3–4.
- Peskin and Schroeder, §§2.1–2.3.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for scalar fields as operator-valued distributions.
- R. Haag, *Local Quantum Physics*, for the structural role and limitations of field operators in local quantum physics.

## Version history

- **2026-05-22:** Initial qft.org free-field reference page for the real and complex Klein–Gordon fields, propagators, commutators, charge, and exercises.
