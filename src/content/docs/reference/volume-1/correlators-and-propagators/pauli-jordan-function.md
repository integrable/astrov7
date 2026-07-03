---
title: "Pauli–Jordan Function"
description: "The scalar commutator function, its relation to Wightman functions, its equal-time initial data, and why it vanishes at spacelike separation."
sidebar:
  label: "Pauli–Jordan Function"
  order: 4
---

## Summary

The Pauli–Jordan function is the distribution that appears in the free scalar field commutator:

$$
\boxed{
[\phi(x),\phi(y)]=i\Delta(x-y).
}
$$

With qft.org conventions,

$$
\boxed{
 i\Delta(z)=\Delta^+(z)-\Delta^+(-z)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{-ip\cdot z}-e^{ip\cdot z}\right).
}
$$

The most important fact is

$$
\boxed{
\Delta(z)=0\quad\text{for}\quad z^2<0.
}
$$

So free scalar fields commute at spacelike separation. This is the simplest explicit realization of microcausality in relativistic QFT.

The Pauli–Jordan function is not the Feynman propagator. It is the **commutator kernel**. It carries causal support, equal-time canonical data, and the raw material from which retarded and advanced response functions are built. The Feynman propagator is a time-ordered Green function; the Pauli–Jordan function is a homogeneous on-shell distribution.

Coleman derives the scalar commutator by subtracting the two Wightman orderings and uses Lorentz invariance to show it vanishes at spacelike separation; Weinberg uses causal fields and commutators as part of the general construction of relativistic QFT; Srednicki uses the same commutator structure in scalar quantization and in the spectral representation (Coleman 2019, ch. 3; Weinberg 1995, Vol. I, §§5.2 and 10.7; Srednicki 2007, §§3 and 13).

## Prerequisites

You should know [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), and [Free Field Summary](/foundations/free-fields/free-field-summary/).

## Core idea

A Wightman function can be nonzero outside the light cone. Causality is saved because nature cares about whether local operations commute, not whether individual vacuum correlations vanish.

The scalar commutator is the difference between the two operator orderings:

$$
\langle0|\phi(x)\phi(y)|0\rangle
-
\langle0|\phi(y)\phi(x)|0\rangle.
$$

For spacelike separation, Lorentz invariance forces the two orderings to agree. Their difference vanishes.

<figure class="doc-figure" style="--figure-width: 43rem;">

![The Pauli–Jordan function is the difference of Wightman orderings and has causal support](/figures/foundations/pauli-jordan-causal-cancellation.svg)

<figcaption>

The Pauli–Jordan function is the difference between the positive-frequency Wightman function and the reversed ordering. The cancellation outside the light cone gives $\Delta(z)=0$ for spacelike $z$, while timelike separations can have nonzero commutator support.

</figcaption>
</figure>

This cancellation is one of the prettiest little tricks in QFT: the vacuum may be correlated across spacelike separations, but local observables still commute there.

:::note[Assumptions]
This page treats the free real scalar field in flat spacetime. In interacting QFT, microcausality is a structural locality condition on local fields or observables. In gauge theories, it must be phrased carefully because gauge-dependent fields may not themselves be physical local observables.
:::

## Definition

Let

$$
z=x-y.
$$

For the free real scalar field,

$$
[\phi(x),\phi(y)]
=\int d\mu(p)\left(e^{-ip\cdot z}-e^{ip\cdot z}\right).
$$

We define $\Delta$ by

$$
\boxed{
[\phi(x),\phi(y)]=i\Delta(z).
}
$$

Equivalently,

$$
\boxed{
 i\Delta(z)=\Delta^+(z)-\Delta^-(z),
\qquad
\Delta^-(z)=\Delta^+(-z).
}
$$

With this convention, $\Delta$ is real and antisymmetric:

$$
\Delta(z)^*=\Delta(z),
\qquad
\Delta(-z)=-\Delta(z).
$$

Some textbooks define the Pauli–Jordan function with the opposite sign, or call $i\Delta$ itself the commutator function. The physics is unchanged, but signs in retarded propagators and equal-time derivatives move around. Keep your convention on a short leash.

## Momentum-space form

Using the four-dimensional on-shell measure,

$$
\Delta^+(z)
=\int\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2)e^{-ip\cdot z},
$$

we get

$$
\boxed{
 i\Delta(z)
=\int\frac{d^4p}{(2\pi)^3}\operatorname{sgn}(p^0)\delta(p^2-m^2)e^{-ip\cdot z}.
}
$$

Thus the Pauli–Jordan function is an on-shell distribution. In the Fourier convention

$$
i\Delta(z)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot z}\,\widetilde{i\Delta}(p),
$$

one has

$$
\boxed{
\widetilde{i\Delta}(p)=2\pi\operatorname{sgn}(p^0)\delta(p^2-m^2).
}
$$

This differs sharply from the Feynman propagator,

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon},
$$

which is an off-shell Green function with a pole prescription.

## Klein–Gordon equation

Because every mode in $\Delta$ is on shell,

$$
(\Box+m^2)\Delta(z)=0
$$

as a distribution away from contact terms—and in fact as a homogeneous distribution. The commutator function does not invert the Klein–Gordon operator.

By contrast, the Feynman propagator satisfies

$$
(\Box+m^2)D_F(z)=-i\delta^{(4)}(z)
$$

with qft.org's convention.

So the distinction is:

| Object | Momentum-space support | Equation |
|---|---|---|
| $\Delta^+(z)$ | positive mass shell | homogeneous |
| $i\Delta(z)$ | both mass-shell branches with sign | homogeneous |
| $D_F(z)$ | off shell with Feynman poles | Green function |
| $G_R(z)$ | off shell with retarded poles | causal Green function |

## Equal-time initial data

At equal time, $z=(0,\mathbf r)$,

$$
i\Delta(0,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{i\mathbf p\cdot\mathbf r}-e^{-i\mathbf p\cdot\mathbf r}\right)=0.
$$

Therefore

$$
\boxed{
\Delta(0,\mathbf r)=0.
}
$$

Now differentiate with respect to $z^0=t$:

$$
\partial_t i\Delta(t,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(-iE_{\mathbf p}e^{-ip\cdot z}-iE_{\mathbf p}e^{ip\cdot z}\right).
$$

At $t=0$ this becomes

$$
\partial_t i\Delta(t,\mathbf r)\big|_{t=0}
=-i\int\frac{d^3\mathbf p}{(2\pi)^3}e^{i\mathbf p\cdot\mathbf r}
=-i\delta^{(3)}(\mathbf r),
$$

so

$$
\boxed{
\partial_t\Delta(t,\mathbf r)\big|_{t=0}
=-\delta^{(3)}(\mathbf r).
}
$$

These two initial conditions reproduce the canonical equal-time algebra:

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0,
$$

and

$$
[\dot\phi(t,\mathbf x),\phi(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Equivalently,

$$
[\phi(t,\mathbf x),\dot\phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

## Why it vanishes outside the light cone

The integral defining $i\Delta(z)$ is Lorentz invariant. If $z$ is spacelike, there is a Lorentz frame in which

$$
z=(0,\mathbf r).
$$

In that frame,

$$
\Delta(0,\mathbf r)=0.
$$

Since $\Delta$ is a Lorentz scalar distribution,

$$
\boxed{
\Delta(z)=0\quad(z^2<0).
}
$$

This proof is deliberately short. It uses exactly the ingredients that matter:

```txt
canonical equal-time data
+ Lorentz invariance
+ local scalar field transformation
= spacelike commutativity.
```

For the free scalar field,

$$
[\phi(x),\phi(y)]=0
\qquad ((x-y)^2<0).
$$

This is microcausality.

## Explicit support in four dimensions

In four spacetime dimensions, the Pauli–Jordan function can be written explicitly in terms of light-cone and inside-cone pieces. With the qft.org sign convention,

$$
\boxed{
\Delta(z)=
-\frac{\operatorname{sgn}(z^0)}{2\pi}\delta(z^2)
+\frac{m\operatorname{sgn}(z^0)}{4\pi\sqrt{z^2}}\theta(z^2)J_1(m\sqrt{z^2}).
}
$$

This formula is distributional. The first term lives on the light cone. The second term lives inside the light cone and vanishes in the massless limit. Thus:

- for a massless scalar in four dimensions, the commutator has support on the light cone;
- for a massive scalar, it also has support inside the light cone;
- in both cases, it vanishes for spacelike $z^2<0$.

The inside-cone tail for massive fields is not a violation of causality. Timelike separated events can influence each other.

## Retarded and advanced functions

The Pauli–Jordan function becomes a causal response function after multiplication by a step function. With the qft.org convention,

$$
\boxed{
G_R(z)=i\theta(z^0)[\phi(z),\phi(0)]=-\theta(z^0)\Delta(z).
}
$$

This has support only in the future light cone:

$$
G_R(z)=0\quad\text{unless}\quad z^0\ge0\quad\text{and}\quad z^2\ge0.
$$

Similarly,

$$
\boxed{
G_A(z)=-i\theta(-z^0)[\phi(z),\phi(0)]=\theta(-z^0)\Delta(z)
}
$$

has support only in the past light cone.

The step functions are what turn the homogeneous commutator distribution into Green functions with contact terms. The detailed pole prescriptions are developed in [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) and [i epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/).

## Relation to the Feynman propagator

The scalar Feynman propagator is

$$
D_F(z)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle,
\qquad z=x-y.
$$

In terms of Wightman functions,

$$
\boxed{
D_F(z)=\theta(z^0)\Delta^+(z)+\theta(-z^0)\Delta^+(-z).
}
$$

The Pauli–Jordan function is instead

$$
\boxed{
i\Delta(z)=\Delta^+(z)-\Delta^+(-z).
}
$$

So the same two Wightman orderings produce different objects:

```txt
time-ordered sum with step functions  → Feynman propagator
ordinary difference of orderings       → Pauli–Jordan commutator
step-function commutator               → retarded or advanced response
```

This is why the Feynman propagator can be nonzero outside the light cone without violating causality. Causality is controlled by $\Delta$, $G_R$, and commutators of local observables.

## Complex scalar field

For the free complex scalar field,

$$
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

one finds

$$
\boxed{
[\Phi(x),\Phi^\dagger(y)]=i\Delta(x-y),
}
$$

while

$$
[\Phi(x),\Phi(y)]=0,
\qquad
[\Phi^\dagger(x),\Phi^\dagger(y)]=0.
$$

At spacelike separation, $\Delta(x-y)=0$, so the charged scalar field and its adjoint commute there. The same Pauli–Jordan kernel governs particle and antiparticle scalar modes.

## Fermions and graded locality

For fermions, the analogous statement uses anticommutators of the basic fields. Schematically,

$$
\{\psi_\alpha(x),\overline\psi_\beta(y)\}
$$

is built from spinor differential operators acting on the scalar Pauli–Jordan function. The locality statement is graded: fermionic fields anticommute at spacelike separation, while bosonic observables such as fermion bilinears commute at spacelike separation.

The scalar Pauli–Jordan function is therefore the simplest member of a wider family: free-field commutator or anticommutator kernels are built from on-shell spectral data and vanish outside the light cone in the appropriate graded sense.

## Common pitfalls

### Confusing the commutator with the Feynman propagator

The Pauli–Jordan function is on shell and homogeneous. The Feynman propagator is off shell and inverts the kinetic operator with the Feynman boundary prescription.

### Thinking every causal object must vanish inside the light cone

Causality requires vanishing outside the light cone. A massive field's commutator can be nonzero inside the light cone.

### Thinking spacelike vacuum correlations violate causality

$\Delta^+(z)$ can be nonzero for spacelike $z$. The commutator $\Delta^+(z)-\Delta^+(-z)$ vanishes there.

### Losing the sign convention

With qft.org conventions,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
\qquad
\partial_t\Delta(t,\mathbf r)|_{t=0}=-\delta^{(3)}(\mathbf r).
$$

Other books may define $\Delta$ with the opposite sign.

### Applying scalar formulas directly to gauge fields

Gauge fields have constraints and gauge redundancy. The right locality statements are about gauge-invariant observables, reduced physical variables, or properly gauge-fixed fields with the bracket structure understood.

## Relation to other topics

- [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) defines $\Delta^+$ and the reversed ordering used here.
- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) derives the canonical initial data for $\Delta$.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) explains the time-ordered combination that produces the Feynman propagator.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) will develop the inverse-operator and pole-prescription viewpoint.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) will build causal response functions from $\Delta$.
- [i epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) will compare Feynman, retarded, and advanced pole displacements.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) will generalize the on-shell spectral support beyond the free theory.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will state the interacting locality principle.

## Research status

- **Established:** The free scalar Pauli–Jordan function, its equal-time data, and spacelike vanishing are textbook-standard.
- **Subtle:** In interacting QFT, local commutativity is a structural condition on fields or observables; in gauge theory, gauge-dependent fields require care.
- **Out of scope here:** Full axiomatic locality, causal perturbation theory, curved-spacetime commutator functions, and algebraic-QFT formulations of causal support.

## Exercises

### Exercise 1: Difference of Wightman orderings

Using

$$
\Delta^+(z)=\langle0|\phi(x)\phi(y)|0\rangle,
\qquad z=x-y,
$$

show that

$$
\langle0|[\phi(x),\phi(y)]|0\rangle
=\Delta^+(z)-\Delta^+(-z).
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
[\phi(x),\phi(y)]=\phi(x)\phi(y)-\phi(y)\phi(x).
$$

Taking the vacuum expectation value gives

$$
\langle0|[\phi(x),\phi(y)]|0\rangle
=\langle0|\phi(x)\phi(y)|0\rangle
-\langle0|\phi(y)\phi(x)|0\rangle.
$$

The first term is $\Delta^+(x-y)=\Delta^+(z)$. The second is $\Delta^+(y-x)=\Delta^+(-z)$. Thus

$$
\langle0|[\phi(x),\phi(y)]|0\rangle
=\Delta^+(z)-\Delta^+(-z).
$$

For the free scalar field, the commutator is a c-number distribution, so this is also the operator commutator.

</details>

### Exercise 2: Equal-time value

Show directly from

$$
i\Delta(t,\mathbf r)=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf r}
-e^{iE_{\mathbf p}t-i\mathbf p\cdot\mathbf r}\right)
$$

that

$$
\Delta(0,\mathbf r)=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Set $t=0$:

$$
i\Delta(0,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{i\mathbf p\cdot\mathbf r}-e^{-i\mathbf p\cdot\mathbf r}\right).
$$

The integrand is odd under $\mathbf p\mapsto-\mathbf p$, while the measure is even. Therefore the integral vanishes:

$$
i\Delta(0,\mathbf r)=0.
$$

Hence

$$
\Delta(0,\mathbf r)=0.
$$

</details>

### Exercise 3: Equal-time derivative

Using the same integral, show that

$$
\partial_t\Delta(t,\mathbf r)\big|_{t=0}=-\delta^{(3)}(\mathbf r).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\partial_t i\Delta(t,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(-iE_{\mathbf p}e^{-iE_{\mathbf p}t+i\mathbf p\cdot\mathbf r}
-iE_{\mathbf p}e^{iE_{\mathbf p}t-i\mathbf p\cdot\mathbf r}\right).
$$

At $t=0$,

$$
\partial_t i\Delta(t,\mathbf r)|_{t=0}
=-\frac{i}{2}\int\frac{d^3\mathbf p}{(2\pi)^3}
\left(e^{i\mathbf p\cdot\mathbf r}+e^{-i\mathbf p\cdot\mathbf r}\right).
$$

The two terms give the same delta function, so

$$
\partial_t i\Delta(t,\mathbf r)|_{t=0}
=-i\delta^{(3)}(\mathbf r).
$$

Dividing by $i$ gives

$$
\partial_t\Delta(t,\mathbf r)|_{t=0}
=-\delta^{(3)}(\mathbf r).
$$

</details>

### Exercise 4: Spacelike vanishing

Use Lorentz invariance and the equal-time result to show that

$$
\Delta(z)=0
$$

for spacelike $z$.

<details>
<summary><strong>Solution</strong></summary>

If $z$ is spacelike, there exists an inertial frame in which $z=(0,\mathbf r)$. In that frame, the equal-time result gives

$$
\Delta(0,\mathbf r)=0.
$$

The Pauli–Jordan function is Lorentz invariant for a scalar field. Therefore its value in every Lorentz frame is the same as its value in the equal-time frame. Hence

$$
\Delta(z)=0
\qquad(z^2<0).
$$

</details>

### Exercise 5: Retarded support

Define

$$
G_R(z)=-\theta(z^0)\Delta(z).
$$

Explain why $G_R(z)$ vanishes unless $z$ lies in or on the future light cone.

<details>
<summary><strong>Solution</strong></summary>

There are two factors:

$$
G_R(z)=-\theta(z^0)\Delta(z).
$$

The step function $\theta(z^0)$ kills all points with $z^0<0$. The Pauli–Jordan function kills all spacelike points with $z^2<0$. Therefore $G_R$ can be nonzero only when

$$
z^0\ge0
$$

and

$$
z^2\ge0.
$$

That is the future light cone, including the light-cone boundary.

</details>

### Exercise 6: Massless support

For $m=0$ in four spacetime dimensions, the explicit formula reduces to

$$
\Delta(z)=-\frac{\operatorname{sgn}(z^0)}{2\pi}\delta(z^2).
$$

Where is this distribution supported?

<details>
<summary><strong>Solution</strong></summary>

The delta function $\delta(z^2)$ has support where

$$
z^2=0.
$$

These are the future and past light cones. The factor $\operatorname{sgn}(z^0)$ changes the sign between the future and past cones, but it does not enlarge the support. Therefore the massless four-dimensional Pauli–Jordan function is supported on the light cone.

</details>

## Sources and further reading

### Primary references

- P. Jordan and W. Pauli, “Zur Quantenelektrodynamik ladungsfreier Felder,” *Zeitschrift für Physik* **47** (1928), for the early commutator-function formulation of free quantum fields.
- W. Pauli and V. Weisskopf, “Über die Quantisierung der skalaren relativistischen Wellengleichung,” *Helvetica Physica Acta* **7** (1934), for scalar-field quantization and the field-theoretic interpretation of the Klein–Gordon equation.
- H. Lehmann, “Über Eigenschaften von Ausbreitungsfunktionen und Renormierungskonstanten quantisierter Felder,” *Nuovo Cimento* **11** (1954), for the spectral representation that generalizes free two-point functions.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3, 4, and 13, for scalar field construction, causal commutators, and Green functions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.1–5.2, 6.2, and 10.7, for causal fields, propagators, and spectral representations.
- M. Srednicki, *Quantum Field Theory*, §§3, 8, and 13, for scalar field quantization, commutators, path-integral Green functions, and spectral representation.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §2.3, for the Pauli–Jordan function and microcausality in the scalar theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9, for the physical relation between vacuum contractions, field quantization, and propagators.

### For a first pass

- Srednicki, §3.
- Peskin and Schroeder, §2.3.
- Coleman, ch. 3.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for locality, spectral condition, and the Wightman framework.
- R. Haag, *Local Quantum Physics*, for the algebraic formulation of locality and causal commutation.
- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for causal propagation and distributional Green functions.

## Version history

- **2026-05-23:** Initial qft.org page on the Pauli–Jordan function, scalar commutator, causal support, equal-time data, retarded and advanced functions, and the distinction from the Feynman propagator.
