---
title: "iε Prescription"
description: "The infinitesimal pole prescription that turns formal inverse wave operators into Feynman, retarded, advanced, or principal-value distributions."
sidebar:
  label: "iε Prescription"
  order: 7
---

## Summary

The symbol $i\epsilon$ is the small-looking notation that carries a large piece of physics. It tells us how to define singular momentum-space denominators as distributions, which contour to use in the complex energy plane, and which boundary condition is imposed on the Green function.

For the free scalar field, qft.org's default Feynman propagator is

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon},
\qquad \epsilon>0.
$$

The retarded and advanced Green functions invert the same Klein–Gordon operator, but use different prescriptions:

$$
\widetilde G_R(p)=-\frac{1}{(p^0+i\epsilon)^2-E_{\mathbf p}^2},
\qquad
\widetilde G_A(p)=-\frac{1}{(p^0-i\epsilon)^2-E_{\mathbf p}^2}.
$$

These are not interchangeable. The Feynman prescription is adapted to vacuum time-ordered perturbation theory. The retarded prescription is adapted to causal response. The advanced prescription is the opposite time boundary condition. The principal-value prescription gives a time-symmetric inverse but does not by itself select vacuum propagation or causal response.

Coleman treats propagators as inverse wave operators whose denominators need prescriptions, and his problem set explicitly asks the reader to show that the time-ordered scalar two-point function is a Klein–Gordon Green function. Srednicki derives the $i\epsilon$ denominator from the free-field path integral and develops the Lehmann–Källén form of the exact propagator. Weinberg emphasizes that propagators and their analytic structure are consequences of time ordering, causality, and the spectral condition (Coleman 2019, chs. 10, 13, 15, 21, and 28; Srednicki 2007, §§8 and 13; Weinberg 1995, Vol. I, §§6.2, 9.2–9.4, and 10.7).

## Prerequisites

You should know [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/), [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Core idea

A differential operator usually has many inverses. The difference between two inverses is a solution of the homogeneous equation.

For the Klein–Gordon operator, the formal momentum-space inverse contains

$$
\frac{1}{p^2-m^2}.
$$

But this expression is singular on the mass shell $p^2=m^2$. The symbol alone does not define a distribution. To know what integral means, we must say how test functions pass around the pole. That missing information is exactly what the prescription supplies.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Comparison of Feynman, retarded, and advanced pole prescriptions](/figures/foundations/i-epsilon-prescriptions.svg)

<figcaption>

For fixed spatial momentum, the pole locations in the complex $p^0$ plane determine the Green function. The Feynman prescription puts the positive-energy pole below and the negative-energy pole above; the retarded prescription puts both below; the advanced prescription puts both above.

</figcaption>
</figure>

:::note[Assumptions]
This page uses flat Minkowski spacetime, the usual vacuum, qft.org's mostly-minus metric, and Fourier convention $e^{-ip\cdot x}$. The same ideas apply more broadly, but signs move when a different metric or Fourier convention is chosen.
:::

## Distribution identity

The basic identity is one-dimensional:

$$
\boxed{
\frac{1}{x\pm i0}
=\operatorname{PV}\frac{1}{x}\mp i\pi\delta(x).
}
$$

Here $\operatorname{PV}$ denotes the Cauchy principal value. The notation $i0$ means the limit $i\epsilon$ with $\epsilon\to0^+$ after integration against a test function.

Multiplying by $i$ gives

$$
\frac{i}{x+i0}
=i\operatorname{PV}\frac{1}{x}+\pi\delta(x),
$$

and

$$
\frac{i}{x-i0}
=i\operatorname{PV}\frac{1}{x}-\pi\delta(x).
$$

So the infinitesimal imaginary part is not just a convergence trick. It fixes the delta-function part of the distribution.

For a scalar denominator,

$$
\boxed{
\frac{1}{p^2-m^2+i0}
=\operatorname{PV}\frac{1}{p^2-m^2}
-i\pi\delta(p^2-m^2).
}
$$

Equivalently,

$$
\boxed{
\frac{i}{p^2-m^2+i0}
=i\operatorname{PV}\frac{1}{p^2-m^2}
+\pi\delta(p^2-m^2).
}
$$

This identity is often the quickest way to separate “on-shell” and “off-shell” parts of a propagator.

## Two energy poles

For fixed spatial momentum,

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2,
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The Feynman denominator

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon
$$

has poles at

$$
p^0=+E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

Equivalently,

$$
\frac{i}{(p^0)^2-E_{\mathbf p}^2+i0}
=\frac{i}{2E_{\mathbf p}}
\left(
\frac{1}{p^0-E_{\mathbf p}+i0}
-
\frac{1}{p^0+E_{\mathbf p}-i0}
\right).
$$

The opposite signs on the two poles encode the time-ordered vacuum condition:

```txt
positive-energy modes propagate forward in time;
negative-energy modes propagate backward in time.
```

That slogan should not be taken too literally as a statement about particles traveling backward through a detector. It is a compact way to describe how the two Wightman orderings are assembled into a time-ordered vacuum correlator.

## Feynman prescription

The scalar Feynman propagator is

$$
D_F(z)=\int\frac{d^4p}{(2\pi)^4}
\frac{i e^{-ip\cdot z}}{p^2-m^2+i0}.
$$

For $z^0>0$, the factor $e^{-ip^0 z^0}$ decays when $p^0$ is continued into the lower half-plane. Closing the contour below picks the pole

$$
p^0=+E_{\mathbf p}-i0.
$$

This produces the positive-frequency Wightman function,

$$
\Delta^+(z)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}e^{-ip\cdot z}.
$$

For $z^0<0$, the contour closes above and picks

$$
p^0=-E_{\mathbf p}+i0,
$$

which produces $\Delta^+(-z)$. Hence

$$
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
$$

The $i\epsilon$ prescription is therefore the compact momentum-space encoding of time ordering.

## Retarded and advanced prescriptions

The retarded Green function is

$$
\widetilde G_R(p)
=-\frac{1}{(p^0+i0)^2-E_{\mathbf p}^2}.
$$

Its poles are

$$
p^0=+E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}-i0.
$$

Both poles lie below the real axis. Therefore, for $z^0<0$, the contour closes above and encloses no poles. This is why

$$
G_R(z)=0\qquad(z^0<0).
$$

The advanced Green function is

$$
\widetilde G_A(p)
=-\frac{1}{(p^0-i0)^2-E_{\mathbf p}^2},
$$

with poles

$$
p^0=+E_{\mathbf p}+i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

Both poles lie above the real axis. Therefore

$$
G_A(z)=0\qquad(z^0>0).
$$

Up to a harmless rescaling of $\epsilon$, these can also be written as

$$
\widetilde G_R(p)=-\frac{1}{p^2-m^2+i\epsilon p^0},
\qquad
\widetilde G_A(p)=-\frac{1}{p^2-m^2-i\epsilon p^0}.
$$

The factor $p^0$ is what moves both poles to the same half-plane.

## Principal value

The principal-value Green function is the time-symmetric inverse

$$
\widetilde G_{\operatorname{PV}}(p)
=-\operatorname{PV}\frac{1}{p^2-m^2}.
$$

It is related to the retarded and advanced Green functions by

$$
\boxed{
G_{\operatorname{PV}}=\frac12(G_R+G_A)
}
$$

for the scalar response normalization used here.

This prescription is useful in classical radiation theory and in algebraic manipulations, but it is not the vacuum time-ordered propagator. It also is not a causal response function by itself: averaging retarded and advanced solutions mixes future and past boundary data.

## Boundary conditions and homogeneous solutions

Suppose $G_1$ and $G_2$ both solve

$$
(\Box+m^2)G_i(z)=\delta^{(4)}(z).
$$

Then their difference obeys

$$
(\Box+m^2)(G_1-G_2)=0.
$$

So different prescriptions differ by homogeneous solutions. For example,

$$
G_A(z)-G_R(z)=\Delta(z),
$$

with qft.org's convention for the Pauli–Jordan function. The right-hand side satisfies the homogeneous Klein–Gordon equation and carries the causal commutator data.

This is the clean conceptual lesson:

```txt
operator inverse + boundary condition = Green function.
```

The $i\epsilon$ is the boundary condition written in momentum space.

## Wick rotation

The Feynman prescription is also what makes Wick rotation well defined. A formal rotation of $p^0$ into the imaginary direction is meaningless unless the contour knows how to avoid the poles.

In the scalar integral

$$
\int\frac{dp^0}{2\pi}\frac{i}{(p^0)^2-E_{\mathbf p}^2+i0},
$$

the Feynman prescription places one pole below and one pole above the real axis. The contour can be rotated without crossing either pole, giving the Euclidean denominator

$$
\frac{1}{p_E^2+m^2}
$$

up to the conventional factors associated with $p^0=i p_E^0$ and $d^4p=i d^4p_E$. This is the analytic bridge between Lorentzian time-ordered correlators and Euclidean Gaussian functional integrals.

Retarded and advanced functions have different analytic domains. They are not obtained by the same Euclidean rotation as the vacuum Feynman propagator.

## Not a UV regulator

The $i\epsilon$ does not make a divergent loop integral finite at large momentum. It moves poles and defines distributions. Ultraviolet divergences require a regulator such as a cutoff, dimensional regularization, Pauli–Villars fields, lattice regularization, or another scheme.

A useful separation:

| Symbol | What it controls | What it does not control |
|---|---|---|
| $i\epsilon$ | poles, contours, boundary conditions | ultraviolet growth |
| UV regulator | short-distance divergences | vacuum boundary condition |
| IR regulator | long-distance or soft singularities | pole prescription by itself |

This distinction becomes essential in loop calculations. A loop integral may need both a pole prescription and a UV regulator.

## Common pitfalls

### Dropping ε too early

The limit $\epsilon\to0^+$ is taken after integration. Dropping $i\epsilon$ before doing contour or distributional manipulations loses the boundary condition.

### Calling ε a physical width

A physical unstable particle has a width such as $\Gamma$, and its pole is displaced by dynamics. The infinitesimal $\epsilon$ is not that width. It is a prescription for stable-particle propagators and exact correlators.

### Using Feynman propagation for classical response

For a source with ordinary causal initial conditions, use the retarded Green function. The Feynman propagator is the object that appears in vacuum time-ordered perturbation theory.

### Forgetting the Fourier convention

With $e^{-ip\cdot x}$ and mostly-minus metric, the formulas above hold as written. Changing to $e^{+ip\cdot x}$ or mostly-plus conventions moves signs. Always translate metric, Fourier phase, and differential operator together.

### Confusing poles and particles

A free propagator has a simple pole at $p^2=m^2$. An interacting exact two-point function has poles, cuts, and spectral density. A pole prescription is needed in both cases, but the analytic structure is richer than the free denominator.

## Relation to other topics

- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) derives the time-ordered scalar propagator and its Feynman pole placement.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) compares causal response functions with the Feynman propagator.
- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) shows how differences of Green functions become homogeneous commutator functions.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) shows how the same prescription applies to every mass value in an exact spectral density.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) will explain how the $i\epsilon$ deformation makes the Lorentzian Gaussian integral well defined.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) will revisit Wick rotation and reflection positivity.

## Research status

- **Established:** The distributional identities, Feynman/retarded/advanced prescriptions, and contour interpretations are textbook-standard.
- **Subtle:** In gauge theories, finite-temperature QFT, curved spacetime, and non-equilibrium systems, pole prescriptions must be combined with gauge fixing, thermal boundary conditions, or real-time contour choices.
- **Out of scope here:** Landau singularities, Cutkosky rules, Schwinger–Keldysh contours, resonance poles on unphysical sheets, and microlocal spectral conditions.

## Exercises

### Exercise 1: Distribution identity

Use the known limit

$$
\lim_{\epsilon\to0^+}\frac{\epsilon}{x^2+\epsilon^2}=\pi\delta(x)
$$

to derive

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Write

$$
\frac{1}{x+i\epsilon}
=\frac{x-i\epsilon}{x^2+\epsilon^2}
=\frac{x}{x^2+\epsilon^2}
-i\frac{\epsilon}{x^2+\epsilon^2}.
$$

As a distribution,

$$
\frac{x}{x^2+\epsilon^2}\to \operatorname{PV}\frac{1}{x},
$$

while

$$
\frac{\epsilon}{x^2+\epsilon^2}\to \pi\delta(x).
$$

Therefore

$$
\frac{1}{x+i0}=\operatorname{PV}\frac{1}{x}-i\pi\delta(x).
$$

</details>

### Exercise 2: Feynman pole locations

Show that

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon=0
$$

puts the positive-energy pole below the real axis and the negative-energy pole above it.

<details>
<summary><strong>Solution</strong></summary>

The poles obey

$$
(p^0)^2=E_{\mathbf p}^2-i\epsilon.
$$

For small $\epsilon$,

$$
\sqrt{E_{\mathbf p}^2-i\epsilon}
=E_{\mathbf p}-\frac{i\epsilon}{2E_{\mathbf p}}+O(\epsilon^2).
$$

Thus

$$
p^0=+E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}+i0.
$$

The positive-energy pole lies below the real axis and the negative-energy pole lies above it.

</details>

### Exercise 3: Retarded support from poles

Use

$$
\widetilde G_R(p)=-\frac{1}{(p^0+i0)^2-E_{\mathbf p}^2}
$$

to explain why $G_R(z)=0$ for $z^0<0$.

<details>
<summary><strong>Solution</strong></summary>

The poles satisfy

$$
p^0+i0=\pm E_{\mathbf p},
$$

so

$$
p^0=+E_{\mathbf p}-i0,
\qquad
p^0=-E_{\mathbf p}-i0.
$$

Both poles are below the real axis. For $z^0<0$, the factor $e^{-ip^0z^0}$ decays in the upper half-plane, so the contour closes above. Since there are no poles above, the integral vanishes. Hence $G_R(z)=0$ for $z^0<0$.

</details>

### Exercise 4: Difference of inverses

Suppose $G_1$ and $G_2$ both satisfy

$$
(\Box+m^2)G_i(z)=\delta^{(4)}(z).
$$

Show that $G_1-G_2$ is a solution of the homogeneous Klein–Gordon equation.

<details>
<summary><strong>Solution</strong></summary>

Subtract the two equations:

$$
(\Box+m^2)G_1-(\Box+m^2)G_2
=\delta^{(4)}(z)-\delta^{(4)}(z)=0.
$$

Therefore

$$
(\Box+m^2)(G_1-G_2)=0.
$$

The difference between two Green functions is a homogeneous solution. This is why a prescription is needed to select a unique inverse.

</details>

### Exercise 5: Principal value as average

Using

$$
\frac{1}{x+i0}+\frac{1}{x-i0}=2\operatorname{PV}\frac{1}{x},
$$

explain why the principal-value Green function is the average of retarded and advanced Green functions.

<details>
<summary><strong>Solution</strong></summary>

The retarded and advanced prescriptions put the poles on opposite sides in such a way that their delta-function parts have opposite signs. When averaged, the delta-function parts cancel, leaving only the principal value.

For the scalar response normalization,

$$
\widetilde G_{\operatorname{PV}}(p)
=-\operatorname{PV}\frac{1}{p^2-m^2}
=\frac12\left(\widetilde G_R(p)+\widetilde G_A(p)\right).
$$

Fourier transforming gives

$$
G_{\operatorname{PV}}=\frac12(G_R+G_A).
$$

</details>

### Exercise 6: Why ε is not a UV regulator

Consider the large-momentum behavior of

$$
\int d^4p\,\frac{i}{p^2-m^2+i\epsilon}.
$$

Explain why $i\epsilon$ does not regulate the ultraviolet divergence.

<details>
<summary><strong>Solution</strong></summary>

For large $|p|$,

$$
\frac{i}{p^2-m^2+i\epsilon}\sim \frac{i}{p^2}.
$$

The infinitesimal $i\epsilon$ only matters near the pole $p^2=m^2$. It does not change the large-$p$ scaling. Therefore the ultraviolet behavior of the integral is unchanged. A UV regulator must modify, cut off, or analytically continue the high-momentum region; $i\epsilon$ does not do that.

</details>

## Sources and further reading

### Primary references

- R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* **76** (1949), for the propagator prescription in perturbative QED.
- H. Lehmann, “Über Eigenschaften von Ausbreitungsfunktionen und Renormierungskonstanten quantisierter Felder,” *Nuovo Cimento* **11** (1954), for the spectral representation of exact propagators.
- H. A. Kramers and R. de L. Kronig, original dispersion-relation work, for the broader analytic idea that boundary prescriptions and causality are connected.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 10, 13, 15, 21, and 28, for propagators, Green functions, spectral representation, and functional-integral inverses.
- M. Srednicki, *Quantum Field Theory*, §§8 and 13, for the free path-integral propagator and Lehmann–Källén representation.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§6.2, 9.2–9.4, and 10.7, for Feynman rules, path-integral $i\epsilon$, and spectral representations.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.3–2.4 and §7.1, for scalar propagators and spectral representation.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9 and III.8, for a compact physical discussion of propagators, imaginary parts, and probability.

### For a first pass

- Peskin and Schroeder, §2.3.
- Srednicki, §§8 and 13.
- Coleman, ch. 10.

### For mathematical precision

- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for distributional propagators and causal prescriptions.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the spectral condition and analytic structure of Wightman functions.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. II, for distributional boundary values of resolvents in spectral theory.

## Version history

- **2026-05-23:** Initial qft.org page on the $i\epsilon$ prescription, distributional identities, Feynman, retarded, advanced, and principal-value Green functions, Wick rotation, and common pole-prescription pitfalls.
