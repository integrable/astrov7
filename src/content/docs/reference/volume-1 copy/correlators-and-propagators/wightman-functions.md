---
title: "Wightman Functions"
description: "Non-time-ordered vacuum correlation functions, positive-energy support, free scalar examples, positivity, and the relation to commutators and spectral representations."
sidebar:
  label: "Wightman Functions"
  order: 3
---

## Summary

Wightman functions are vacuum expectation values of local operators in their written order:

$$
W_n(x_1,\ldots,x_n)
=\langle0|\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle.
$$

They are **not** time ordered. That tiny negative sentence is the whole point. A Wightman function remembers the order of operators, the Hilbert-space spectrum inserted between them, and the positive-energy condition on intermediate states.

For the free real scalar field, the basic two-point Wightman function is

$$
\boxed{
\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle
=\int \frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}\,e^{-ip\cdot(x-y)}.
}
$$

The reversed ordering is

$$
\Delta^-(x-y)\equiv \Delta^+(y-x)=\Delta^+(-(x-y)).
$$

Their difference gives the field commutator. Their time-ordered combination gives the Feynman propagator. Their spectral decomposition gives the first clean look at what kinds of physical states an operator can create from the vacuum.

Coleman's scalar-field construction introduces $\Delta^+$ directly from the positive-frequency and negative-frequency parts of the free scalar field and then uses $\Delta^+(x-y)-\Delta^+(y-x)$ to prove spacelike commutativity; Weinberg treats vacuum matrix elements and spectral functions as the nonperturbative data behind propagators; Srednicki uses the same two-point functions in the scalar theory, LSZ, and the Lehmann–Källén representation (Coleman 2019, chs. 3 and 13; Weinberg 1995, Vol. I, §§5.2, 6.4, and 10.7; Srednicki 2007, §§3, 5, and 13).

## Prerequisites

You should know [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), and [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/).

## Core idea

In an operator product,

$$
\langle0|A(x)B(y)|0\rangle,
$$

the operator on the right acts first. Thus $B(y)$ creates a state from the vacuum, and $A(x)$ tests its overlap with the vacuum from the left. If we insert a complete set of momentum eigenstates between the two operators, we get

$$
\langle0|A(x)B(y)|0\rangle
=\sum_n e^{-ip_n\cdot(x-y)}
\langle0|A(0)|n\rangle\langle n|B(0)|0\rangle,
$$

with the schematic sum replaced by integrals over continuous momenta in infinite volume.

This formula already explains why Wightman functions are so informative:

- the exponential knows the four-momentum of the intermediate state;
- the matrix elements know which states the operators can create;
- the vacuum and spectral condition enforce positive energy;
- the written operator order decides which intermediate states appear.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Wightman two-point functions keep operator order and have positive-energy support](/figures/foundations/wightman-positive-energy-support.svg)

<figcaption>

A two-point Wightman function keeps the written operator order. For a free scalar field, $\Delta^+(z)$ has Fourier support on the positive-energy mass shell, equivalently $\theta(p^0)\delta(p^2-m^2)$.

</figcaption>
</figure>

The Feynman propagator, by contrast, changes the written order depending on the time coordinates. That makes it ideal for perturbation theory, but it hides some Hilbert-space information that is explicit in Wightman functions.

:::note[Assumptions]
This page assumes a stable Poincaré-invariant vacuum in flat Minkowski spacetime. In axiomatic QFT, Wightman functions are primary objects satisfying precise conditions: covariance, locality, spectral support, positivity, and regularity as distributions. Here we use that viewpoint as guidance, but keep the treatment at the working graduate-QFT level.
:::

## Definition

For local operators $\mathcal O_i(x_i)$, the $n$-point Wightman function is

$$
\boxed{
W_n(x_1,\ldots,x_n)
=\langle0|\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)|0\rangle.
}
$$

The order is exactly the order written. No time-ordering symbol is present.

For a single scalar field,

$$
W_n(x_1,\ldots,x_n)
=\langle0|\phi(x_1)\cdots\phi(x_n)|0\rangle.
$$

For two possibly different operators,

$$
W_{AB}(x-y)=\langle0|A(x)B(y)|0\rangle,
$$

where translation invariance lets us write the answer as a function of $x-y$.

Operator order matters. In general,

$$
W_{AB}(x-y)\neq W_{BA}(y-x).
$$

For Hermitian $A$ and $B$,

$$
\left(W_{AB}(x-y)\right)^*
= W_{BA}(y-x).
$$

Thus even when $A=B=\phi$ is a real scalar field, $\Delta^+(z)$ is not generally a real symmetric function. It is a distribution whose complex conjugate is the reversed ordering.

## Free scalar two-point function

Use the qft.org scalar mode expansion

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

where

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The vacuum obeys

$$
a(\mathbf p)|0\rangle=0.
$$

Then the only nonzero term in $\langle0|\phi(x)\phi(y)|0\rangle$ comes from $a(\mathbf p)$ in the first field and $a^\dagger(\mathbf q)$ in the second field:

$$
\begin{aligned}
\langle0|\phi(x)\phi(y)|0\rangle
&=\int d\mu(p)d\mu(q)\,
 e^{-ip\cdot x}e^{iq\cdot y}
\langle0|a(\mathbf p)a^\dagger(\mathbf q)|0\rangle \\
&=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
\end{aligned}
$$

So

$$
\boxed{
\Delta^+(z)=\int d\mu(p)\,e^{-ip\cdot z}.
}
$$

The reversed ordering is

$$
\boxed{
\Delta^-(z)=\Delta^+(-z)=\int d\mu(p)\,e^{ip\cdot z}.
}
$$

Here $\Delta^+$ and $\Delta^-$ are names for the positive-frequency and negative-frequency Wightman functions. They are not positive and negative parts of a probability.

## Four-dimensional form

The on-shell measure can be written in a manifestly Lorentz-invariant form:

$$
\int d\mu(p)\,f(p)
=\int\frac{d^4p}{(2\pi)^3}\,\theta(p^0)\delta(p^2-m^2)f(p).
$$

Therefore

$$
\boxed{
\Delta^+(z)
=\int\frac{d^4p}{(2\pi)^3}\,
\theta(p^0)\delta(p^2-m^2)e^{-ip\cdot z}.
}
$$

If the Fourier transform convention is

$$
\Delta^+(z)=\int\frac{d^4p}{(2\pi)^4}\,
 e^{-ip\cdot z}\,\widetilde{\Delta}^+(p),
$$

then

$$
\boxed{
\widetilde{\Delta}^+(p)=2\pi\theta(p^0)\delta(p^2-m^2).
}
$$

This is a crucial distinction from the Feynman propagator. The Wightman function is supported **on shell** in momentum space. The Feynman propagator is an off-shell Green function with poles at the mass shell.

## Positive-energy support

The free formula has support only on $p^0=+E_{\mathbf p}$. The interacting version has the same structural feature: its Fourier transform has support only where the intermediate states can have physical four-momentum.

For a scalar operator $\mathcal O$ in a stable relativistic vacuum, the two-point Wightman function has the spectral form

$$
\boxed{
\langle0|\mathcal O(x)\mathcal O(0)|0\rangle
=\int_0^\infty dM^2\,\rho_{\mathcal O}(M^2)
\int\frac{d^4p}{(2\pi)^3}\,
\theta(p^0)\delta(p^2-M^2)e^{-ip\cdot x}.
}
$$

The spectral density $\rho_{\mathcal O}(M^2)$ is nonnegative for Hermitian $\mathcal O$ in a unitary theory. A one-particle state gives a delta-function contribution to $\rho_{\mathcal O}$; multiparticle states give a continuum. This is the Wightman-function version of the [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/).

## Homogeneous equation, not Green equation

The free Wightman function is built only from on-shell modes. Therefore

$$
(\Box+m^2)\Delta^+(z)=0
$$

as a distribution.

This differs from the Feynman propagator, which obeys

$$
(\Box+m^2)D_F(z)=-i\delta^{(4)}(z)
$$

with qft.org's convention $D_F(p)=i/(p^2-m^2+i\epsilon)$.

The slogan is:

```txt
Wightman function: on-shell vacuum correlation.
Feynman propagator: Green function with boundary prescription.
```

This is one of those places where using the single word “propagator” for every two-point object does real damage. The objects are related, but they answer different questions.

## Relation to the commutator

For a real scalar field,

$$
[\phi(x),\phi(y)]
=\langle0|[\phi(x),\phi(y)]|0\rangle
$$

because the commutator is a c-number distribution in the free theory. Using $z=x-y$,

$$
\begin{aligned}
\langle0|[\phi(x),\phi(y)]|0\rangle
&=\langle0|\phi(x)\phi(y)|0\rangle
 -\langle0|\phi(y)\phi(x)|0\rangle \\
&=\Delta^+(z)-\Delta^+(-z).
\end{aligned}
$$

With our convention,

$$
\boxed{
[\phi(x),\phi(y)]=i\Delta(x-y),
\qquad
 i\Delta(z)=\Delta^+(z)-\Delta^+(-z).
}
$$

The individual Wightman functions do not vanish at spacelike separation. Their difference does. This is the core mechanism behind free-field microcausality.

## Spacelike separation

For spacelike $z$, there is a proper Lorentz transformation and spatial rotation that maps $z$ to $-z$. Since $\Delta^+(z)$ is Lorentz invariant for a scalar field,

$$
\Delta^+(z)=\Delta^+(-z)
\qquad (z^2<0).
$$

Therefore

$$
\Delta(z)=0
\qquad (z^2<0).
$$

But this does **not** say

$$
\Delta^+(z)=0
\qquad (z^2<0).
$$

In fact, at equal time,

$$
\Delta^+(0,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}e^{i\mathbf p\cdot\mathbf r},
$$

which is generally nonzero as a distribution/function away from the origin. The cancellation appears only after subtracting the reversed ordering.

:::caution[Microcausality is not absence of vacuum correlations]
Vacuum correlations can extend outside the light cone. Causality is protected because commutators of local observables vanish at spacelike separation, not because every individual vacuum two-point function vanishes there.
:::

## Positivity

For a Hermitian scalar field, define a smeared state

$$
|\Psi_f\rangle=\int d^4x\,f(x)\phi(x)|0\rangle.
$$

Then

$$
\begin{aligned}
\langle\Psi_f|\Psi_f\rangle
&=\int d^4x\,d^4y\,f^*(x)f(y)
\langle0|\phi(x)\phi(y)|0\rangle \\
&=\int d^4x\,d^4y\,f^*(x)f(y)\Delta^+(x-y) \\
&\ge 0.
\end{aligned}
$$

This is Wightman positivity in its simplest form. It is not an optional nicety. Without positivity, the Hilbert-space interpretation collapses.

In momentum space for the free scalar,

$$
\langle\Psi_f|\Psi_f\rangle
=\int d\mu(p)\,|\widetilde f(p)|^2\ge0,
$$

where $\widetilde f(p)$ is evaluated on the positive-energy mass shell.

## Complex scalar fields

For the complex scalar field,

$$
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and

$$
\Phi^\dagger(x)=\int d\mu(p)
\left[a^\dagger(\mathbf p)e^{ip\cdot x}+b(\mathbf p)e^{-ip\cdot x}\right].
$$

The nonzero two-point Wightman functions include

$$
\boxed{
\langle0|\Phi(x)\Phi^\dagger(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)},
}
$$

and

$$
\boxed{
\langle0|\Phi^\dagger(x)\Phi(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
}
$$

The first corresponds to the particle oscillator $a,a^\dagger$; the second corresponds to the antiparticle oscillator $b,b^\dagger$.

Charge conservation gives

$$
\langle0|\Phi(x)\Phi(y)|0\rangle=0,
\qquad
\langle0|\Phi^\dagger(x)\Phi^\dagger(y)|0\rangle=0.
$$

The operator product must carry total charge zero to have a nonzero vacuum expectation value in a charge-neutral vacuum.

## Fermionic Wightman functions

For a Dirac field, the basic unordered two-point functions are spinor-valued distributions such as

$$
\langle0|\psi_\alpha(x)\overline\psi_\beta(y)|0\rangle,
$$

and

$$
\langle0|\overline\psi_\beta(y)\psi_\alpha(x)|0\rangle.
$$

The time-ordered Dirac propagator combines these with a minus sign in the reversed-time term, because fermion fields are odd operators. The unordered Wightman functions themselves are still the primitive vacuum matrix elements. Their spinor numerators encode the Dirac equation and spin sums; their support remains on positive-energy mass shells for the appropriate particle or antiparticle states.

This is why fermion propagators look like scalar propagators multiplied by $(p\!\!/+m)$ in momentum space: the spinor Wightman functions carry the same spectral support plus spinor completeness data.

## Analytic continuation preview

The positive-energy condition has a powerful analytic consequence. Because all intermediate energies are nonnegative, Wightman functions are boundary values of analytic functions when the spacetime arguments are continued to suitable complex domains. This is a major theme in rigorous QFT and underlies the relation between Lorentzian Wightman functions and Euclidean Schwinger functions.

This page will not develop the theorem. The practical message is modest:

```txt
positive-energy support is not just a sign convention;
it controls analytic structure.
```

The later pages on [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) and [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) will return to this point.

## Common pitfalls

### Treating Wightman functions as time ordered

A Wightman function keeps the written operator order. It does not sort operators by time. If you silently insert a $T$, you have changed the object.

### Expecting spacelike Wightman functions to vanish

They generally do not vanish at spacelike separation. The commutator vanishes because the two orderings cancel.

### Forgetting positive-energy support

$\Delta^+$ is not a generic Fourier transform. Its momentum-space support is on the positive-energy mass shell.

### Calling Wightman functions Green functions

The free scalar Wightman function solves the homogeneous Klein–Gordon equation. The Feynman, retarded, and advanced propagators are Green functions with contact terms and boundary prescriptions.

### Confusing positivity with pointwise positivity

Wightman positivity means smeared quadratic forms are nonnegative. It does not mean $\Delta^+(x)$ is a positive real number at every spacetime point.

### Ignoring gauge subtleties

Gauge-dependent fields can have unphysical components and indefinite metric structures depending on gauge choice. In gauge theory, the cleanest Wightman functions are usually built from gauge-invariant local operators or from properly gauge-fixed fields with the corresponding constraints understood.

## Relation to other topics

- [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/) introduces vacuum expectation values and complete-state insertions.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) explains how time-ordered Green functions are built from Wightman orderings.
- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) studies the commutator $i\Delta=\Delta^+-\Delta^-$ and causal support.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) will turn Wightman functions into the time-ordered scalar Green function.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) will build causal response functions from the commutator.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) will develop the interacting spectral density systematically.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will state the interacting locality principle.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) will explain the Euclidean continuation of correlation functions.

## Research status

- **Established:** Wightman functions, positive-energy support, free scalar two-point functions, and Wightman positivity are textbook-standard.
- **Subtle:** Interacting Wightman functions are distributions, not ordinary functions; products at coincident points require renormalization; gauge theories require care with unphysical degrees of freedom.
- **Out of scope here:** The full Wightman axioms, reconstruction theorem, edge-of-the-wedge theorem, Osterwalder–Schrader reconstruction, algebraic QFT, and constructive existence questions.

## Exercises

### Exercise 1: Derive the free scalar Wightman function

Starting from

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

show that

$$
\langle0|\phi(x)\phi(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the product:

$$
\phi(x)\phi(y)=\int d\mu(p)d\mu(q)\,
\left[a_p e^{-ipx}+a_p^\dagger e^{ipx}\right]
\left[a_q e^{-iqy}+a_q^\dagger e^{iqy}\right].
$$

In the vacuum expectation value, all terms vanish except the one with $a_p a_q^\dagger$:

$$
\langle0|a_p a_q^\dagger|0\rangle
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

Therefore

$$
\begin{aligned}
\langle0|\phi(x)\phi(y)|0\rangle
&=\int d\mu(p)d\mu(q)\,
 e^{-ip\cdot x}e^{iq\cdot y}
 (2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q) \\
&=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
\end{aligned}
$$

</details>

### Exercise 2: Convert to four-dimensional form

Show that

$$
\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}f(E_{\mathbf p},\mathbf p)
=\int\frac{d^4p}{(2\pi)^3}\theta(p^0)\delta(p^2-m^2)f(p).
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
p^2-m^2=(p^0)^2-E_{\mathbf p}^2.
$$

Then

$$
\delta((p^0)^2-E_{\mathbf p}^2)
=\frac{1}{2E_{\mathbf p}}
\left[\delta(p^0-E_{\mathbf p})+\delta(p^0+E_{\mathbf p})\right].
$$

Multiplying by $\theta(p^0)$ keeps only the positive-energy root:

$$
\theta(p^0)\delta(p^2-m^2)
=\frac{1}{2E_{\mathbf p}}\delta(p^0-E_{\mathbf p}).
$$

Integrating over $p^0$ gives the desired result.

</details>

### Exercise 3: Show Wightman positivity

Let

$$
|\Psi_f\rangle=\int d^4x\,f(x)\phi(x)|0\rangle.
$$

Show that

$$
\int d^4x\,d^4y\,f^*(x)f(y)\Delta^+(x-y)\ge0.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute the norm:

$$
\begin{aligned}
\langle\Psi_f|\Psi_f\rangle
&=\int d^4x\,d^4y\,f^*(x)f(y)
\langle0|\phi(x)\phi(y)|0\rangle \\
&=\int d^4x\,d^4y\,f^*(x)f(y)\Delta^+(x-y).
\end{aligned}
$$

A Hilbert-space norm is nonnegative, so the quadratic form is nonnegative.

For the free scalar field, the same result is visible in momentum space:

$$
\langle\Psi_f|\Psi_f\rangle
=\int d\mu(p)\,|\widetilde f(p)|^2\ge0.
$$

</details>

### Exercise 4: Wightman functions at spacelike separation

Use Lorentz invariance to show that

$$
\Delta^+(z)=\Delta^+(-z)
$$

for spacelike $z$. Explain why this does not imply $\Delta^+(z)=0$.

<details>
<summary><strong>Solution</strong></summary>

If $z$ is spacelike, there is a Lorentz frame in which $z=(0,\mathbf r)$. A spatial rotation by $\pi$ maps $\mathbf r$ to $-\mathbf r$, so $z$ can be mapped to $-z$ by a proper Lorentz transformation. Since $\Delta^+$ is a scalar distribution,

$$
\Delta^+(z)=\Delta^+(-z).
$$

But equality to the reversed argument is not equality to zero. At equal time,

$$
\Delta^+(0,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}e^{i\mathbf p\cdot\mathbf r},
$$

which is generally nonzero. The commutator vanishes because it is the difference

$$
\Delta^+(z)-\Delta^+(-z),
$$

not because each term vanishes.

</details>

### Exercise 5: Selection rule for a charged operator

Let the vacuum obey $Q|0\rangle=0$, and suppose $[Q,\mathcal O]=q\mathcal O$. Show that

$$
\langle0|\mathcal O(x)|0\rangle=0
$$

if $q\neq0$.

<details>
<summary><strong>Solution</strong></summary>

Take the vacuum expectation value of the commutator:

$$
\langle0|[Q,\mathcal O(x)]|0\rangle
=\langle0|Q\mathcal O(x)|0\rangle-\langle0|\mathcal O(x)Q|0\rangle=0.
$$

But the commutator is $q\mathcal O(x)$, so

$$
q\langle0|\mathcal O(x)|0\rangle=0.
$$

If $q\neq0$, the one-point function vanishes.

</details>

### Exercise 6: Homogeneous equation

Show that the free scalar Wightman function obeys

$$
(\Box+m^2)\Delta^+(z)=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\Delta^+(z)=\int d\mu(p)\,e^{-ip\cdot z},
$$

with $p^2=m^2$ on the support of $d\mu(p)$. Acting with $\Box+m^2$ gives

$$
(\Box+m^2)e^{-ip\cdot z}=(-p^2+m^2)e^{-ip\cdot z}=0.
$$

Since every mode is on shell, the whole integral obeys the homogeneous Klein–Gordon equation.

</details>

## Sources and further reading

### Primary references

- A. S. Wightman, “Quantum Field Theory in Terms of Vacuum Expectation Values,” *Physical Review* **101** (1956), for the vacuum-expectation-value formulation of relativistic QFT.
- H. Lehmann, “Über Eigenschaften von Ausbreitungsfunktionen und Renormierungskonstanten quantisierter Felder,” *Nuovo Cimento* **11** (1954), for the spectral representation behind exact two-point functions.
- H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* **1** (1955), for the connection between Green functions and scattering amplitudes.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 13 and 15, for Heisenberg-field Green functions and LSZ.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.1, 6.2, and 10.7, for causal fields, propagators, and the Källén–Lehmann spectral representation.
- M. Srednicki, *Quantum Field Theory*, §§3, 8, and 13, for free scalar correlators, path-integral Green functions, and the Lehmann–Källén representation.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.3–2.4 and §7.1, for scalar two-point functions and spectral representation.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9, for a compact physical account of vacuum contractions and propagators.

### For a first pass

- Srednicki, §3.
- Peskin and Schroeder, §2.3.
- Coleman, §13.4.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for Wightman functions, locality, spectral condition, and reconstruction.
- R. Haag, *Local Quantum Physics*, for the algebraic viewpoint on states, fields, and local observables.
- K. Fredenhagen and K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, for modern distributional and microlocal methods.

## Version history

- **2026-05-23:** Initial qft.org page on Wightman functions, positive-energy support, Hilbert-space positivity, spectral decomposition, spacelike correlations, and relation to commutators and time ordering.
