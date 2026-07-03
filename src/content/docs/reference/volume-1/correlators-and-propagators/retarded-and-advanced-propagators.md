---
title: "Retarded and Advanced Propagators"
description: "Causal response functions built from the Pauli–Jordan commutator, their support, Green-function equations, and momentum-space pole prescriptions."
sidebar:
  label: "Retarded and Advanced Propagators"
  order: 6
---

## Summary

The retarded and advanced propagators are the causal Green functions for the Klein–Gordon operator. With qft.org's convention

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

define $z=x-y$ and

$$
\boxed{
G_R(z)=i\theta(z^0)[\phi(x),\phi(y)]=-\theta(z^0)\Delta(z),
}
$$

$$
\boxed{
G_A(z)=-i\theta(-z^0)[\phi(x),\phi(y)]=\theta(-z^0)\Delta(z).
}
$$

They satisfy the same inhomogeneous equation,

$$
\boxed{
(\Box+m^2)G_R(z)=\delta^{(4)}(z),
\qquad
(\Box+m^2)G_A(z)=\delta^{(4)}(z),
}
$$

but impose opposite boundary conditions. $G_R$ has support only in the future light cone. $G_A$ has support only in the past light cone.

These are not the Feynman propagator. The Feynman propagator is the time-ordered vacuum two-point function and is adapted to perturbation theory. The retarded propagator is the response of a field to a source after the source acts.

This distinction is standard but easy to blur. Coleman repeatedly emphasizes propagators as inverses of wave operators with different pole prescriptions; Zee gives a compact discussion of advanced and retarded pole placements; Srednicki and Weinberg use causal commutators, Green functions, and spectral representations to separate response, time ordering, and Hilbert-space positivity (Coleman 2019, chs. 10, 21, 28, and 30; Zee 2010, ch. I.3 and ch. III.8; Srednicki 2007, §§3, 8, and 13; Weinberg 1995, Vol. I, §§5.2, 6.2, and 10.7).

## Prerequisites

You should know [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Conventions and Normalizations](/foundations/conventions-and-normalizations/).

## Core idea

A Green function is an inverse plus a boundary condition. The retarded and advanced propagators invert the same operator as the Feynman propagator, but they answer a different physical question.

For a source $J(x)$ coupled to a scalar field, the classical sourced equation is

$$
(\Box+m^2)\phi(x)=J(x).
$$

The retarded solution is

$$
\phi_R(x)=\int d^4y\,G_R(x-y)J(y),
$$

so $\phi_R(x)$ depends only on sources in the causal past of $x$. The advanced solution,

$$
\phi_A(x)=\int d^4y\,G_A(x-y)J(y),
$$

depends only on sources in the causal future of $x$. Advanced Green functions are less common as physical initial-value solutions, but they are extremely useful in identities, radiation theory, and comparisons of boundary conditions.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Retarded and advanced propagators have different support and pole prescriptions](/figures/foundations/retarded-advanced-poles.svg)

<figcaption>

The retarded and advanced propagators solve the same differential equation but impose opposite time boundary conditions. Retarded propagation has future support and both energy poles below the real axis; advanced propagation has past support and both poles above the real axis.

</figcaption>
</figure>

:::note[Assumptions]
This page treats the free scalar field in flat Minkowski spacetime. In interacting QFT, retarded correlators are still defined by commutators and encode causal linear response, but exact propagators are no longer single free-particle denominators. In gauge theories, physical response functions should be built from gauge-invariant observables or from properly gauge-fixed fields with the usual caution.
:::

## Definition from the commutator

The Pauli–Jordan function is defined by

$$
[\phi(x),\phi(y)]=i\Delta(x-y).
$$

With $z=x-y$, qft.org uses

$$
\boxed{
G_R(z)=i\theta(z^0)[\phi(x),\phi(y)]=-\theta(z^0)\Delta(z),
}
$$

and

$$
\boxed{
G_A(z)=-i\theta(-z^0)[\phi(x),\phi(y)]=\theta(-z^0)\Delta(z).
}
$$

The factors of $i$ are chosen so that both $G_R$ and $G_A$ solve

$$
(\Box+m^2)G(z)=\delta^{(4)}(z).
$$

Different books put signs in different places by defining the Pauli–Jordan function with the opposite sign. The invariant content is support, pole placement, and the response equation.

## Support

The Pauli–Jordan function vanishes outside the light cone:

$$
\Delta(z)=0\qquad(z^2<0).
$$

Therefore

$$
G_R(z)=-\theta(z^0)\Delta(z)
$$

can be nonzero only if

$$
z^0\ge0,
\qquad
z^2\ge0.
$$

That is the future light cone, including the boundary.

Similarly,

$$
G_A(z)=\theta(-z^0)\Delta(z)
$$

can be nonzero only if

$$
z^0\le0,
\qquad
z^2\ge0.
$$

That is the past light cone.

This is the cleanest place to see the word “causal” in propagator language. The Feynman propagator knows about the vacuum. The retarded propagator knows about causal influence.

## Green-function equation

The Pauli–Jordan function is homogeneous:

$$
(\Box+m^2)\Delta(z)=0
$$

as a distribution. Multiplying by a step function creates a contact term at $z^0=0$.

Use the equal-time initial data from the Pauli–Jordan page:

$$
\Delta(0,\mathbf r)=0,
\qquad
\partial_t\Delta(t,\mathbf r)|_{t=0}=-\delta^{(3)}(\mathbf r).
$$

Now compute

$$
G_R(t,\mathbf r)=-\theta(t)\Delta(t,\mathbf r).
$$

The operator $\Box+m^2$ acting on the step function gives a delta-function contribution. Since $\Delta(0,\mathbf r)=0$, the $\delta'(t)$ term vanishes. The remaining term gives

$$
(\Box+m^2)G_R(t,\mathbf r)
=-\delta(t)\partial_t\Delta(t,\mathbf r)|_{t=0}
=\delta(t)\delta^{(3)}(\mathbf r).
$$

Thus

$$
\boxed{
(\Box+m^2)G_R(z)=\delta^{(4)}(z).
}
$$

The same reasoning gives

$$
\boxed{
(\Box+m^2)G_A(z)=\delta^{(4)}(z).
}
$$

## Momentum-space prescriptions

Let

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

With the Fourier convention

$$
G(z)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot z}\widetilde G(p),
$$

the retarded and advanced scalar Green functions are

$$
\boxed{
\widetilde G_R(p)=
-\frac{1}{(p^0+i\epsilon)^2-E_{\mathbf p}^2}
}
$$

and

$$
\boxed{
\widetilde G_A(p)=
-\frac{1}{(p^0-i\epsilon)^2-E_{\mathbf p}^2}.
}
$$

Equivalently, up to harmless rescaling of $\epsilon$,

$$
\widetilde G_R(p)=
-\frac{1}{p^2-m^2+i\epsilon p^0},
\qquad
\widetilde G_A(p)=
-\frac{1}{p^2-m^2-i\epsilon p^0}.
$$

The pole locations are:

| Green function | Pole locations | Support |
|---|---|---|
| $G_R$ | $p^0=\pm E_{\mathbf p}-i\epsilon$ | future light cone |
| $G_A$ | $p^0=\pm E_{\mathbf p}+i\epsilon$ | past light cone |
| $D_F$ | $+E_{\mathbf p}-i\epsilon$, $-E_{\mathbf p}+i\epsilon$ | vacuum time ordering |

The retarded propagator has both poles below the real $p^0$ axis. For $z^0<0$, close the contour in the upper half-plane; there are no poles, so $G_R(z)=0$. For $z^0>0$, close below and pick both poles.

The advanced propagator has both poles above the real axis. The same contour logic gives $G_A(z)=0$ for $z^0>0$.

## Relation to the Pauli–Jordan function

Because

$$
G_R(z)=-\theta(z^0)\Delta(z),
\qquad
G_A(z)=\theta(-z^0)\Delta(z),
$$

we have

$$
\boxed{
G_R(z)-G_A(z)=-\Delta(z).
}
$$

Equivalently,

$$
\Delta(z)=G_A(z)-G_R(z).
$$

This identity says that the homogeneous commutator is the difference between two inhomogeneous Green functions with different boundary conditions. The delta-function sources cancel in the difference:

$$
(\Box+m^2)(G_A-G_R)=0.
$$

That is exactly what the Pauli–Jordan function must satisfy.

## Relation to the Feynman propagator

The Feynman propagator is

$$
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
$$

The retarded propagator is

$$
G_R(z)=-\theta(z^0)\left(\Delta^+(z)-\Delta^+(-z)\right)/i.
$$

They are made from the same free-field ingredients, but assembled for different purposes.

A compact comparison:

| Object | Built from | Solves | Physical role |
|---|---|---|---|
| $D_F$ | time-ordered vacuum product | $(\Box+m^2)D_F=-i\delta$ | perturbation theory |
| $G_R$ | future commutator | $(\Box+m^2)G_R=\delta$ | causal response |
| $G_A$ | past commutator | $(\Box+m^2)G_A=\delta$ | advanced response |
| $\Delta$ | commutator | homogeneous | microcausality |

## Example: response to a localized source

Suppose a source $J(y)$ is supported near $y=0$. The retarded solution is

$$
\phi_R(x)=\int d^4y\,G_R(x-y)J(y).
$$

If $x$ is outside the future light cone of the source region, then $x-y$ is either spacelike or has negative time component for every $y$ in the source. Therefore

$$
G_R(x-y)=0
$$

throughout the integration region, and

$$
\phi_R(x)=0.
$$

This is the causal-response statement in its most operational form: a source cannot produce a retarded field outside its future light cone.

## Common pitfalls

### Calling every propagator a probability amplitude

Retarded and advanced propagators are Green functions for response. The Feynman propagator is a vacuum time-ordered correlator. None is a probability by itself.

### Using the Feynman prescription for response

For a classical source with initial conditions, use the retarded Green function. The Feynman propagator imposes vacuum boundary conditions, not ordinary causal initial-value boundary conditions.

### Forgetting the light-cone part of support

The step function alone is not the whole story. $\theta(z^0)$ restricts the time direction, while the Pauli–Jordan function restricts support to the light cone and timelike interior.

### Losing the sign convention

With qft.org's convention $[\phi(x),\phi(y)]=i\Delta(x-y)$ and $\partial_t\Delta|_{t=0}=-\delta^{(3)}$, the retarded Green function is $G_R=-\theta\Delta$. If your source defines $\Delta$ with the opposite sign, the displayed formula changes but the response equation does not.

## Relation to other topics

- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) supplies the commutator kernel used to build $G_R$ and $G_A$.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) gives the time-ordered vacuum Green function with the Feynman pole prescription.
- [i epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) will compare Feynman, retarded, advanced, and principal-value prescriptions systematically.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) will replace the free pole by a spectral density in interacting QFT.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will state the general locality principle behind the vanishing of spacelike commutators.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) will distinguish time-ordered vacuum generating functionals from real-time response functionals.

## Research status

- **Established:** Retarded and advanced Green functions for free relativistic fields are textbook-standard causal response kernels.
- **Subtle:** In interacting and thermal QFT, real-time response functions require careful spectral, analytic, and boundary-condition control.
- **Out of scope here:** Schwinger–Keldysh contours, KMS relations, causal perturbation theory, curved-spacetime fundamental solutions, and BRST treatments of gauge-field response.

## Exercises

### Exercise 1: Future support

Use

$$
G_R(z)=-\theta(z^0)\Delta(z)
$$

and $\Delta(z)=0$ for spacelike $z$ to show that $G_R(z)$ can be nonzero only in or on the future light cone.

<details>
<summary><strong>Solution</strong></summary>

The factor $\theta(z^0)$ vanishes for $z^0<0$. The Pauli–Jordan function vanishes for $z^2<0$. Therefore $G_R(z)$ can be nonzero only when both conditions fail:

$$
z^0\ge0,
\qquad
z^2\ge0.
$$

That is the future light cone, including its boundary.

</details>

### Exercise 2: Retarded Green equation

Given

$$
\Delta(0,\mathbf r)=0,
\qquad
\partial_t\Delta(t,\mathbf r)|_{t=0}=-\delta^{(3)}(\mathbf r),
$$

show that

$$
G_R(t,\mathbf r)=-\theta(t)\Delta(t,\mathbf r)
$$

satisfies

$$
(\Box+m^2)G_R(t,\mathbf r)=\delta^{(4)}(t,\mathbf r).
$$

<details>
<summary><strong>Solution</strong></summary>

For $t\neq0$, $\Delta$ solves the homogeneous Klein–Gordon equation, so only derivatives of $\theta(t)$ can contribute. Since $\Delta(0,\mathbf r)=0$,

$$
\partial_t\bigl[\theta(t)\Delta(t,\mathbf r)\bigr]
=\theta(t)\partial_t\Delta(t,\mathbf r),
$$

and hence

$$
\partial_t^2\bigl[\theta(t)\Delta(t,\mathbf r)\bigr]
=\delta(t)\partial_t\Delta(0,\mathbf r)+\theta(t)\partial_t^2\Delta(t,\mathbf r).
$$

Therefore

$$
(\Box+m^2)G_R
=-\delta(t)\partial_t\Delta(0,\mathbf r)
=\delta(t)\delta^{(3)}(\mathbf r).
$$

Thus

$$
(\Box+m^2)G_R=\delta^{(4)}(z).
$$

</details>

### Exercise 3: Retarded pole locations

Show that

$$
\widetilde G_R(p)=-\frac{1}{(p^0+i\epsilon)^2-E_{\mathbf p}^2}
$$

has both poles below the real $p^0$ axis.

<details>
<summary><strong>Solution</strong></summary>

The poles satisfy

$$
(p^0+i\epsilon)^2-E_{\mathbf p}^2=0.
$$

Thus

$$
p^0+i\epsilon=\pm E_{\mathbf p},
$$

so

$$
p^0=+E_{\mathbf p}-i\epsilon,
\qquad
p^0=-E_{\mathbf p}-i\epsilon.
$$

Both have negative imaginary part. Therefore both poles lie below the real axis.

</details>

### Exercise 4: Difference of advanced and retarded functions

Using the definitions of $G_R$ and $G_A$, show that

$$
\Delta(z)=G_A(z)-G_R(z).
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
G_R(z)=-\theta(z^0)\Delta(z),
\qquad
G_A(z)=\theta(-z^0)\Delta(z).
$$

Then

$$
G_A(z)-G_R(z)
=\theta(-z^0)\Delta(z)+\theta(z^0)\Delta(z).
$$

For separated points, $\theta(z^0)+\theta(-z^0)=1$. Hence

$$
G_A(z)-G_R(z)=\Delta(z).
$$

At $z^0=0$, the identity is understood distributionally with the usual half-step convention; the contact ambiguity does not alter the commutator distribution.

</details>

### Exercise 5: Source response

Let $J(y)$ be supported in a compact spacetime region $S$. Show that the retarded solution

$$
\phi_R(x)=\int d^4y\,G_R(x-y)J(y)
$$

vanishes if $x$ is outside the causal future of $S$.

<details>
<summary><strong>Solution</strong></summary>

If $x$ is outside the causal future of $S$, then for every $y\in S$, the separation $x-y$ is either spacelike or has negative time component. In either case,

$$
G_R(x-y)=0.
$$

Therefore every point in the integrand vanishes, and

$$
\phi_R(x)=0.
$$

</details>

## Sources and further reading

### Primary references

- P. Jordan and W. Pauli, “Zur Quantenelektrodynamik ladungsfreier Felder,” *Zeitschrift für Physik* **47** (1928), for the early commutator-function treatment of free quantum fields.
- J. Schwinger, “On Gauge Invariance and Vacuum Polarization,” *Physical Review* **82** (1951), for causal and source-response ideas in field theory.
- R. Kubo, “Statistical-Mechanical Theory of Irreversible Processes,” *Journal of the Physical Society of Japan* **12** (1957), for the linear-response viewpoint in which retarded commutators are central.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3, 10, 21, 28, and 30, for commutators, Green functions, pole prescriptions, and functional-integral propagators.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.2, 6.2, 9.2–9.4, and 10.7, for causal fields, propagators, and spectral functions.
- M. Srednicki, *Quantum Field Theory*, §§3, 8, 13, and 43, for scalar commutators, Feynman propagators, and Green functions from path integrals.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.3 and III.8, for pole prescriptions and the physical distinction between Feynman, retarded, and advanced propagation.
- M. Le Bellac, *Thermal Field Theory*, chs. 2–3, for retarded correlators and response functions in real-time finite-temperature field theory.

### For a first pass

- Peskin and Schroeder, §2.3.
- Srednicki, §3 and §8.
- Zee, ch. I.3.

### For mathematical precision

- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for causal distributions and Green functions.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for locality, spectral support, and distributional correlation functions.
- R. Haag, *Local Quantum Physics*, for causal localization and operator-algebraic response.

## Version history

- **2026-05-23:** Initial qft.org page on retarded and advanced scalar propagators, causal support, Green-function equations, pole prescriptions, relation to the Pauli–Jordan function, and distinction from the Feynman propagator.
