---
title: "Feynman Propagator"
description: "The Feynman propagator as a time-ordered two-point function, an inverse kinetic operator, and a boundary prescription in the complex energy plane."
sidebar:
  label: "Feynman Propagator"
  order: 5
---

## Summary

The Feynman propagator is the time-ordered two-point function of a free field. For the real scalar field, with qft.org's mostly-minus convention,

$$
\boxed{
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle
=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

It satisfies

$$
\boxed{
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
}
$$

So the Feynman propagator is two things at once: an operator-theoretic vacuum correlator and, up to the factor of $i$, an inverse of the Klein–Gordon operator. The little $i\epsilon$ tells us which inverse. Without it, the symbol $1/(p^2-m^2)$ is not a complete distributional prescription.

This page is the hinge between the previous operator pages and the coming path-integral and perturbative pages. Coleman describes the scalar and Dirac Feynman propagators as the inverse of the free wave operator with a pole prescription, and later obtains the same object from the free generating functional; Srednicki derives the free scalar propagator from the Gaussian path integral and the epsilon trick; Weinberg computes propagators from time-ordered products and uses them in the general Feynman rules (Coleman 2019, chs. 10, 21, and 28; Srednicki 2007, §§8 and 43; Weinberg 1995, Vol. I, §§6.1–6.2 and 9.2–9.4).

## Prerequisites

You should know [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Core idea

The Feynman propagator is not merely a Green function chosen for mathematical convenience. It is the Green function selected by the vacuum and by time ordering.

For a free scalar field, let

$$
z=x-y.
$$

The Wightman function is

$$
\Delta^+(z)=\langle0|\phi(x)\phi(y)|0\rangle.
$$

Time ordering gives

$$
\boxed{
D_F(z)
=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
}
$$

Thus positive-frequency modes propagate forward in time and negative-frequency modes propagate backward in time. In momentum space this same statement is encoded by moving the two energy poles to opposite sides of the real axis.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Feynman pole prescription in the complex energy plane](/figures/foundations/feynman-pole-prescription.svg)

<figcaption>

For $D_F(z)$, the pole at $p^0=+E_{\mathbf p}$ is shifted below the real axis and the pole at $p^0=-E_{\mathbf p}$ is shifted above it. Closing the contour below for $z^0>0$ picks the positive-energy pole; closing above for $z^0<0$ picks the negative-energy pole.

</figcaption>
</figure>

:::note[Assumptions]
This page treats free fields in the usual Minkowski vacuum. In interacting QFT, the exact two-point function has a spectral representation rather than a single free pole. In gauge theories, propagators also require gauge fixing and gauge-dependent propagators are not observables by themselves.
:::

## Definition from time ordering

For a real scalar field,

$$
D_F(z)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle.
$$

Using the definition of time ordering,

$$
D_F(z)=
\theta(z^0)\langle0|\phi(x)\phi(y)|0\rangle
+\theta(-z^0)\langle0|\phi(y)\phi(x)|0\rangle.
$$

Therefore

$$
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
$$

For the free scalar,

$$
\Delta^+(z)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}e^{-ip\cdot z},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

So

$$
D_F(z)=
\theta(z^0)\int d\mu(p)e^{-ip\cdot z}
+\theta(-z^0)\int d\mu(p)e^{ip\cdot z}.
$$

This is the most transparent operator formula. The four-dimensional formula is more compact, but it hides the time-ordering origin.

## Momentum-space form

The compact form is

$$
\boxed{
D_F(z)=\int\frac{d^4p}{(2\pi)^4}
\frac{i\,e^{-ip\cdot z}}{p^2-m^2+i\epsilon}.
}
$$

To see why, write

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2.
$$

The denominator

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon
$$

has poles at

$$
p^0=+E_{\mathbf p}-i\epsilon,
\qquad
p^0=-E_{\mathbf p}+i\epsilon,
$$

where the symbol $\epsilon$ is always understood as a positive infinitesimal, with harmless rescalings absorbed into its name.

For $z^0>0$, the factor $e^{-ip^0z^0}$ decays in the lower half-plane, so the contour closes below and picks the pole at $+E_{\mathbf p}-i\epsilon$. This gives

$$
\theta(z^0)\int d\mu(p)e^{-ip\cdot z}.
$$

For $z^0<0$, the contour closes above and picks the pole at $-E_{\mathbf p}+i\epsilon$. This gives

$$
\theta(-z^0)\int d\mu(p)e^{ip\cdot z}.
$$

Together they reproduce the time-ordered expression.

## Green-function equation

Act with the Klein–Gordon operator on the four-dimensional integral:

$$
(\Box+m^2)e^{-ip\cdot z}=(-p^2+m^2)e^{-ip\cdot z}.
$$

Therefore

$$
\begin{aligned}
(\Box+m^2)D_F(z)
&=\int\frac{d^4p}{(2\pi)^4}
\frac{i(-p^2+m^2)e^{-ip\cdot z}}{p^2-m^2+i\epsilon} \\
&=-i\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot z}
\end{aligned}
$$

in the distributional limit $\epsilon\to0^+$. Hence

$$
\boxed{
(\Box+m^2)D_F(z)=-i\delta^{(4)}(z).
}
$$

This factor of $-i$ is not a mistake. qft.org's $D_F$ includes the factor of $i$ used in Feynman rules. The classical Green function for

$$
(\Box+m^2)G(z)=\delta^{(4)}(z)
$$

would be $G(z)=iD_F(z)$ if it used the same boundary prescription. For causal response, however, one usually uses the retarded Green function, not the Feynman one.

## Inverse kinetic operator

The free scalar action can be written, after integrating by parts, as

$$
S_0[\phi]
=-\frac12\int d^4x\,\phi(x)(\Box+m^2)\phi(x).
$$

In momentum space the quadratic operator is proportional to

$$
p^2-m^2.
$$

The propagator is the inverse of that quadratic operator with a boundary condition:

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

This is why free propagators appear automatically when Gaussian path integrals are completed to a square. In qft.org's source convention,

$$
Z_0[J]=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
$$

and functional derivatives of $Z_0[J]$ produce time-ordered correlators.

## Dirac and vector examples

For the Dirac field,

$$
S_F(z)=\langle0|T\{\psi(x)\overline\psi(y)\}|0\rangle
=\int\frac{d^4p}{(2\pi)^4}
\frac{i(p\!\!/+m)e^{-ip\cdot z}}{p^2-m^2+i\epsilon}.
$$

Equivalently,

$$
\boxed{
S_F(p)=\frac{i}{p\!\!/-m+i\epsilon}
}
$$

as a distributional shorthand. More explicitly, multiplying numerator and denominator gives the displayed form with $i(p\!\!/+m)/(p^2-m^2+i\epsilon)$. It satisfies

$$
(i\gamma^\mu\partial_\mu-m)S_F(z)=i\delta^{(4)}(z).
$$

For gauge fields, the free inverse requires gauge fixing. In Feynman gauge for the Abelian gauge field,

$$
D_F^{\mu\nu}(p)=\frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}.
$$

The pole prescription is the same kind of vacuum boundary condition, but gauge-dependent numerator structure must not be confused with physical polarizations.

## What the Feynman propagator means

The Feynman propagator is excellent for perturbation theory because interactions in the Dyson expansion are time ordered. Wick's theorem then turns time-ordered products of free fields into normal-ordered products plus contractions, and the scalar contraction is exactly $D_F$.

It is less good as a literal causal-response function. The Feynman propagator generally does **not** vanish at spacelike separation. That is not a violation of causality. Causality is controlled by commutators and retarded response functions. In the free scalar theory,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and $\Delta(z)=0$ for spacelike $z$. The retarded response function is built from this commutator, not from $D_F$.

A safe slogan:

```txt
Feynman propagator: vacuum time ordering and perturbation theory.
Retarded propagator: causal response to sources.
Pauli–Jordan function: commutator and microcausality.
```

## Example: recovering the Wightman pieces

Start with

$$
D_F(t,\mathbf r)=\int\frac{d^3\mathbf p}{(2\pi)^3}
\int\frac{dp^0}{2\pi}
\frac{i e^{-ip^0t+i\mathbf p\cdot\mathbf r}}
{(p^0)^2-E_{\mathbf p}^2+i\epsilon}.
$$

For $t>0$, close below. The pole at $p^0=E_{\mathbf p}-i\epsilon$ contributes, giving

$$
D_F(t,\mathbf r)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
 e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf r}
=\Delta^+(t,\mathbf r).
$$

For $t<0$, close above. The pole at $p^0=-E_{\mathbf p}+i\epsilon$ contributes, giving

$$
D_F(t,\mathbf r)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
 e^{iE_{\mathbf p}t-i\mathbf p\cdot\mathbf r}
=\Delta^+(-t,-\mathbf r).
$$

That is precisely the time-ordered answer.

## Common pitfalls

### Treating iε as optional

The pole prescription is part of the definition of the distribution. Dropping it is like writing a differential equation without boundary conditions.

### Confusing Feynman and retarded propagation

The Feynman propagator is adapted to vacuum perturbation theory. The retarded propagator is adapted to causal response. Both invert the same differential operator, but they impose different boundary conditions.

### Thinking spacelike nonzero means causality violation

$D_F(z)$ can be nonzero for spacelike $z$. The commutator vanishes there. Local operations at spacelike separation cannot influence one another.

### Forgetting the factor of i

Some books call $i/(p^2-m^2+i\epsilon)$ the propagator. Others reserve “Green function” for $1/(p^2-m^2+i\epsilon)$ or use mostly-plus conventions. Always check the metric, Fourier transform, and factor of $i$ together.

## Relation to other topics

- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) defines the operator ordering that produces $D_F$.
- [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) supplies the non-time-ordered pieces that are assembled into $D_F$.
- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) explains why spacelike nonzero Feynman propagation does not violate microcausality.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) compares the Feynman prescription with causal response prescriptions.
- [i epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) will give a fuller contour and distributional comparison.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) will derive the same object from a Gaussian functional integral.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) will identify the Feynman propagator as the basic contraction.

## Research status

- **Established:** The free scalar Feynman propagator, its pole prescription, and its role as a Wick contraction are textbook-standard.
- **Subtle:** In interacting QFT, the exact two-point function has renormalized poles, branch cuts, and spectral densities; the free formula is the starting point, not the whole story.
- **Out of scope here:** Full LSZ reduction, loop corrections to propagators, finite-temperature real-time contours, and gauge-dependent propagator subtleties beyond the free-field summary.

## Exercises

### Exercise 1: Time-ordered form

Starting from

$$
D_F(z)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle,
$$

show that

$$
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
T\{\phi(x)\phi(y)\}
=\theta(x^0-y^0)\phi(x)\phi(y)
+\theta(y^0-x^0)\phi(y)\phi(x).
$$

Taking the vacuum expectation value and writing $z=x-y$ gives

$$
D_F(z)=\theta(z^0)\langle0|\phi(x)\phi(y)|0\rangle
+\theta(-z^0)\langle0|\phi(y)\phi(x)|0\rangle.
$$

The first expectation value is $\Delta^+(z)$ and the second is $\Delta^+(y-x)=\Delta^+(-z)$. Therefore

$$
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
$$

</details>

### Exercise 2: Green-function equation

Use the momentum-space expression

$$
D_F(z)=\int\frac{d^4p}{(2\pi)^4}\frac{i e^{-ip\cdot z}}{p^2-m^2+i\epsilon}
$$

to show that

$$
(\Box+m^2)D_F(z)=-i\delta^{(4)}(z).
$$

<details>
<summary><strong>Solution</strong></summary>

Since

$$
(\Box+m^2)e^{-ip\cdot z}=(-p^2+m^2)e^{-ip\cdot z},
$$

we have

$$
(\Box+m^2)D_F(z)=\int\frac{d^4p}{(2\pi)^4}
\frac{i(-p^2+m^2)e^{-ip\cdot z}}{p^2-m^2+i\epsilon}.
$$

In the distributional limit $\epsilon\to0^+$,

$$
\frac{-p^2+m^2}{p^2-m^2+i\epsilon}\to -1.
$$

Thus

$$
(\Box+m^2)D_F(z)=-i\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot z}
=-i\delta^{(4)}(z).
$$

</details>

### Exercise 3: Pole locations

Show that the denominator

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon
$$

places the positive-energy pole below the real axis and the negative-energy pole above it.

<details>
<summary><strong>Solution</strong></summary>

The poles obey

$$
(p^0)^2-E_{\mathbf p}^2+i\epsilon=0.
$$

For small $\epsilon$,

$$
p^0\approx \pm\sqrt{E_{\mathbf p}^2-i\epsilon}
\approx \pm\left(E_{\mathbf p}-\frac{i\epsilon}{2E_{\mathbf p}}\right).
$$

Hence

$$
p^0\approx +E_{\mathbf p}-i0^+,
\qquad
p^0\approx -E_{\mathbf p}+i0^+.
$$

The positive-energy pole is below the real axis; the negative-energy pole is above it.

</details>

### Exercise 4: Dirac inverse

Verify that

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}
$$

is the Feynman inverse of the free Dirac operator.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
(p\!\!/-m)(p\!\!/+m)=p\!\!/^{\,2}-m^2=p^2-m^2,
$$

where $p\!\!/^{\,2}=p^2$ follows from the Clifford algebra. Therefore

$$
(p\!\!/-m)S_F(p)
=(p\!\!/-m)\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}
\to i
$$

as a distribution away from the pole, with the pole defined by the Feynman prescription. In position space this is

$$
(i\gamma^\mu\partial_\mu-m)S_F(z)=i\delta^{(4)}(z).
$$

</details>

### Exercise 5: Not a causal response function

Explain why the statement

$$
D_F(z)\neq0\quad\text{for some spacelike }z
$$

does not violate relativistic causality.

<details>
<summary><strong>Solution</strong></summary>

Causality concerns whether local operations can influence one another. In operator language this is controlled by commutators at spacelike separation, not by individual vacuum correlations.

For the free scalar field,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and

$$
\Delta(z)=0\qquad(z^2<0).
$$

The Feynman propagator is a time-ordered vacuum expectation value, not a response kernel. It can be nonzero outside the light cone while the commutator and the retarded response vanish there.

</details>

## Sources and further reading

### Primary references

- R. P. Feynman, “The Theory of Positrons,” *Physical Review* **76** (1949), for the propagator boundary prescription behind the spacetime diagrammatic method.
- R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* **76** (1949), for the spacetime propagator viewpoint in perturbative QED.
- J. Schwinger, “On Quantum-Electrodynamics and the Magnetic Moment of the Electron,” *Physical Review* **73** (1948), for an independent operator-based development of covariant QED.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 10, 21, and 28, for scalar, Dirac, and functional-integral propagators.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§6.1–6.2 and 9.2–9.4, for time-ordered products, propagator calculation, and path-integral methods.
- M. Srednicki, *Quantum Field Theory*, §§8, 13, 42, and 43, for free scalar and fermion propagators and the path-integral derivation.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.3–2.4, for the scalar Feynman propagator and microcausality.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.3–I.7, for a compact physical account of fields, propagators, and diagrams.

### For a first pass

- Srednicki, §§8 and 9.
- Peskin and Schroeder, §2.4.
- Coleman, ch. 10.

### For mathematical precision

- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for distributional Green functions and causal prescriptions.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the relation between Wightman functions, time-ordered products, and locality.
- R. Haag, *Local Quantum Physics*, for the algebraic view in which time-ordered functions are secondary to local operator structure.

## Version history

- **2026-05-23:** Initial qft.org page on the Feynman propagator, time ordering, inverse kinetic operators, pole placement, Dirac and gauge examples, and the distinction from causal response.
