---
title: "Normal Ordering"
description: "Normal-ordered products of free fields, vacuum-energy subtraction, contractions, Wick expansion, and the caveats behind the colon notation."
sidebar:
  label: "Normal Ordering"
  order: 5
---

## Summary

Normal ordering is a definition of composite operators built from free fields after a vacuum and a creation-annihilation split have been chosen. For bosonic oscillators,

$$
:a^\dagger a:=a^\dagger a,
\qquad
:aa^\dagger:=a^\dagger a.
$$

For a free real scalar field,

$$
\phi(x)=\phi_+(x)+\phi_-(x),
$$

where $\phi_+$ contains annihilation operators and $\phi_-$ contains creation operators. The normal-ordered product is obtained by placing all creation parts to the left of all annihilation parts:

$$
:\phi(x)\phi(y):
=\phi_-(x)\phi_-(y)+\phi_-(x)\phi_+(y)
+\phi_-(y)\phi_+(x)+\phi_+(x)\phi_+(y).
$$

The ordinary product differs from the normal-ordered product by a c-number contraction:

$$
\boxed{
\phi(x)\phi(y)=:\phi(x)\phi(y):+\langle0|\phi(x)\phi(y)|0\rangle.
}
$$

For the free scalar Hamiltonian,

$$
H=\int d\mu(p)\,E_{\mathbf p}a^\dagger(\mathbf p)a(\mathbf p)+E_0,
$$

where $E_0$ is the formal zero-point energy. Per unit volume,

$$
\frac{E_0}{V}=\frac12\int\frac{d^3\mathbf p}{(2\pi)^3}E_{\mathbf p}.
$$

The normal-ordered Hamiltonian is

$$
\boxed{
:H:=\int d\mu(p)\,E_{\mathbf p}a^\dagger(\mathbf p)a(\mathbf p).
}
$$

Normal ordering is indispensable for clean free-field bookkeeping, but it is not magic. It removes particular vacuum c-numbers relative to a chosen vacuum; it does not by itself renormalize an interacting QFT, solve the cosmological constant problem, or define composite operators nonperturbatively. Coleman introduces normal ordering exactly at this point in canonical scalar quantization, after deriving the divergent zero-point energy; Wick's theorem later turns time-ordered products into normal-ordered products plus contractions (Coleman 2019, §§4.5 and 8.2; Weinberg 1995, Vol. I, §6.1; Srednicki 2007, §§3 and 9).

## Prerequisites

You should know [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/), [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), and [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/). We use the conventions fixed in [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, natural units, and covariant on-shell measure.

## Core idea

A free field is a sum of creation and annihilation pieces. Normal ordering chooses the product in which the creation pieces stand to the left and the annihilation pieces stand to the right. Since annihilation operators kill the vacuum on the right and creation operators kill the vacuum on the left, vacuum expectation values of nontrivial normal-ordered products vanish.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Normal ordering separates free-field products into normal products and contractions](/figures/foundations/normal-ordering-contractions.svg)

<figcaption>

For a free scalar field, split $\phi=\phi_++\phi_-$ into annihilation and creation parts. Normal ordering places all creation parts to the left. The difference between an ordinary product and a normal-ordered product is a contraction, here the Wightman two-point function $\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle$.

</figcaption>
</figure>

The practical gain is enormous: normal-ordered operators have simple matrix elements between Fock states, and Wick's theorem says that perturbation theory can be reduced to normal-ordered products plus contractions. This is the algebraic engine behind Feynman diagrams.

:::note[Assumptions]
Normal ordering on this page is defined relative to the free-field vacuum. The definition depends on the choice of creation and annihilation operators. In curved spacetime, time-dependent backgrounds, thermal states, or interacting theories without a preferred particle basis, there may be no unique vacuum relative to which this definition is natural.
:::

## Creation and annihilation split

For the free real scalar field,

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

with

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}},
\qquad
p^0=E_{\mathbf p}>0.
$$

Define

$$
\phi_+(x)=\int d\mu(p)\,a(\mathbf p)e^{-ip\cdot x},
$$

and

$$
\phi_-(x)=\int d\mu(p)\,a^\dagger(\mathbf p)e^{ip\cdot x}.
$$

Thus

$$
\phi(x)=\phi_+(x)+\phi_-(x).
$$

The plus subscript denotes the positive-frequency annihilation part, not electric charge. The minus subscript denotes the negative-frequency creation part. Some books use different notation; the concept is the split into annihilators and creators.

The vacuum obeys

$$
a(\mathbf p)|0\rangle=0,
\qquad
\langle0|a^\dagger(\mathbf p)=0.
$$

Therefore

$$
\phi_+(x)|0\rangle=0,
\qquad
\langle0|\phi_-(x)=0.
$$

## Definition for bosonic free fields

For a product of free bosonic fields, normal ordering means: expand each field into creation and annihilation parts and write every creation operator to the left of every annihilation operator. For one oscillator,

$$
:a^\dagger a:=a^\dagger a,
\qquad
:aa^\dagger:=a^\dagger a,
$$

and

$$
:a a:=aa,
\qquad
:a^\dagger a^\dagger:=a^\dagger a^\dagger.
$$

For the scalar field,

$$
:\phi(x)\phi(y):
=\phi_-(x)\phi_-(y)+\phi_-(x)\phi_+(y)
+\phi_-(y)\phi_+(x)+\phi_+(x)\phi_+(y).
$$

Compare this with the ordinary product:

$$
\phi(x)\phi(y)
=\phi_-(x)\phi_-(y)+\phi_-(x)\phi_+(y)
+\phi_+(x)\phi_-(y)+\phi_+(x)\phi_+(y).
$$

Only the third term differs. The difference is

$$
\phi_+(x)\phi_-(y)-\phi_-(y)\phi_+(x)
=[\phi_+(x),\phi_-(y)].
$$

This commutator is a c-number:

$$
[\phi_+(x),\phi_-(y)]
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

The right-hand side is the positive-frequency Wightman function,

$$
\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle.
$$

So

$$
\boxed{
\phi(x)\phi(y)=:\phi(x)\phi(y):+\Delta^+(x-y).
}
$$

This is the simplest example of a contraction.

## Vacuum expectation values

For any nonempty normal-ordered product of free bosonic fields,

$$
\boxed{
\langle0|:\phi(x_1)\cdots\phi(x_n):|0\rangle=0.
}
$$

The reason is simple. After normal ordering, every term either contains an annihilation operator on the far right or a creation operator on the far left. Such a term gives zero between vacuum states.

For example,

$$
\langle0|:\phi(x)\phi(y):|0\rangle=0,
$$

whereas

$$
\langle0|\phi(x)\phi(y)|0\rangle=\Delta^+(x-y).
$$

This distinction is the point of the notation. Normal ordering subtracts the vacuum self-contractions that appear in ordinary products of free fields.

## Hamiltonian and zero-point energy

The free scalar Hamiltonian is

$$
H=\frac12\int d^3\mathbf x\,
\left[\pi^2+(\nabla\phi)^2+m^2\phi^2\right].
$$

Substituting the mode expansion gives

$$
H=\frac12\int d\mu(p)\,E_{\mathbf p}
\left[a^\dagger(\mathbf p)a(\mathbf p)+a(\mathbf p)a^\dagger(\mathbf p)\right].
$$

Using

$$
[a(\mathbf p),a^\dagger(\mathbf p')]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p'),
$$

this becomes

$$
H=\int d\mu(p)\,E_{\mathbf p}a^\dagger(\mathbf p)a(\mathbf p)+E_0,
$$

where $E_0$ is the formal zero-point energy. Its infinite-volume density is

$$
\frac{E_0}{V}=\frac12\int\frac{d^3\mathbf p}{(2\pi)^3}E_{\mathbf p}.
$$

The integral diverges at large momentum. In a finite periodic box, the same statement is

$$
E_0=\frac12\sum_{\mathbf k}E_{\mathbf k}.
$$

Normal ordering removes this c-number from the free Hamiltonian:

$$
:H:=H-E_0
=\int d\mu(p)\,E_{\mathbf p}a^\dagger(\mathbf p)a(\mathbf p).
$$

Then

$$
:H:|0\rangle=0,
$$

and

$$
:H:a^\dagger(\mathbf p)|0\rangle
=E_{\mathbf p}a^\dagger(\mathbf p)|0\rangle.
$$

This is the useful particle-counting Hamiltonian in flat-space free-field theory.

:::caution[Vacuum energy is not always disposable]
In ordinary flat-space scattering, shifting $H$ by a constant changes no transition amplitudes between states with fixed total time evolution. With dynamical gravity, a constant shift of energy density changes the cosmological constant. Normal ordering is therefore a convention for a specified QFT context, not a universal proof that vacuum energy is physically meaningless.
:::

## Local composite operators

Products of fields at the same point are singular. A normal-ordered composite such as

$$
:\phi^2(x):
$$

is defined by subtracting the free-field self-contraction:

$$
\boxed{
:\phi^2(x):=\lim_{y\to x}
\left[\phi(x)\phi(y)-\Delta^+(x-y)\right].
}
$$

Similarly,

$$
:\phi^4(x):
$$

subtracts all self-contractions internal to the four fields. More explicitly,

$$
\phi^4
=:\phi^4:+6\Delta^+(0):\phi^2:+3[\Delta^+(0)]^2
$$

as a formal shorthand. The symbol $\Delta^+(0)$ is divergent; the point of the expression is to display which self-contractions are being subtracted in the free theory.

This is why normal ordering is useful in writing interaction Hamiltonians such as

$$
H_I(t)=\int d^3\mathbf x\,\frac{\lambda}{4!}:\phi^4(t,\mathbf x):.
$$

It removes tadpole-like self-contractions already present in the free vacuum convention. In interacting QFT, further renormalization is still required.

## Wick contractions

For two free scalar fields, define the contraction by

$$
\operatorname{contr}[\phi(x),\phi(y)]
:=\langle0|T\phi(x)\phi(y)|0\rangle
=D_F(x-y).
$$

Here $\operatorname{contr}[\phi(x),\phi(y)]$ is only a compact notation for “the contraction of the two fields”; later pages can introduce graphical contraction marks.

Equivalently,

$$
T\{\phi(x)\phi(y)\}
=:\phi(x)\phi(y):+D_F(x-y).
$$

For more fields, Wick's theorem states that the time-ordered product equals the normal-ordered product plus all possible contractions:

$$
T\{\phi_1\cdots\phi_n\}
=:\phi_1\cdots\phi_n:
+\text{all single contractions}
+\text{all double contractions}+\cdots.
$$

Here each $\phi_i$ abbreviates a free field at a labeled spacetime point. This theorem is the algebraic reason that perturbation theory can be represented by Feynman diagrams. Normal-ordered products carry external uncontracted fields; contractions become propagators.

## Fermionic sign preview

For fermions, normal ordering also moves creation operators to the left and annihilation operators to the right, but each interchange of fermionic operators contributes a minus sign. For example, if $b$ and $b^\dagger$ are fermionic ladder operators with

$$
\{b,b^\dagger\}=1,
$$

then

$$
:bb^\dagger:=-b^\dagger b.
$$

The minus sign is not decoration. It is what makes Wick's theorem work for fermions and what turns fermionic contractions into anticommutators rather than commutators. The full fermionic canonical construction comes later.

## Normal ordering is not a verb on equations

The colon notation defines a new product. It is not an operation one may safely apply to both sides of an already true equation.

For one oscillator,

$$
aa^\dagger=a^\dagger a+1.
$$

If one tried to “normal-order both sides,” one would write the nonsense

$$
:aa^\dagger: \,=\, :a^\dagger a+1:,
$$

and might conclude

$$
a^\dagger a=a^\dagger a+1.
$$

The mistake is treating normal ordering as a linear operation on equations rather than as part of the definition of an expression. The expressions $aa^\dagger$ and $:aa^\dagger:$ are different products, just as a dot product and a cross product are different products.

A safe way to say it is:

$$
:aa^\dagger:
\quad\text{is defined to mean}\quad
a^\dagger a.
$$

It is not the ordinary product $aa^\dagger$ with a cosmetic pair of punctuation marks.

## Dependence on the vacuum

Normal ordering depends on the split into creation and annihilation operators, which depends on a vacuum. In Minkowski-space free-field theory this split is canonical enough for most purposes: positive-frequency modes annihilate the Poincaré-invariant vacuum.

In a time-dependent background, an expanding universe, a thermal state, or a strongly interacting theory, the preferred split may be absent or context-dependent. Then the question “normal ordered with respect to what?” is not pedantry; it is the question.

This is one reason modern QFT often treats composite operators through renormalization conditions, operator product expansions, or algebraic definitions rather than relying only on normal ordering.

## What normal ordering does not do

Normal ordering removes vacuum contractions relative to a free reference vacuum. It does not remove all ultraviolet divergences. For example, in an interacting $\phi^4$ theory, loop diagrams still generate divergent corrections to masses, couplings, and composite operators. Those divergences require regularization and renormalization.

Normal ordering also does not preserve every symmetry automatically. In theories with nontrivial currents, gauge constraints, or anomalies, composite operators may require a regulator that respects the relevant symmetry. A badly chosen subtraction can hide or break the structure one is trying to study.

Finally, normal ordering does not make local fields into ordinary functions. Fields remain operator-valued distributions, and products at the same point require a definition.

## Common pitfalls

### Treating the colon as punctuation

The colons change the product. The expression $:aa^\dagger:$ is not the same operator as $aa^\dagger$.

### Forgetting the chosen vacuum

Normal ordering is relative to a creation-annihilation split. Change the vacuum and the normal-ordered composite can change by c-number and lower-operator terms.

### Believing the vacuum energy has been explained away

Normal ordering sets the free-field vacuum energy to zero in a chosen flat-space convention. It does not explain the observed cosmological constant or its smallness.

### Using bosonic signs for fermions

For fermions, moving operators past each other produces minus signs. Forgetting those signs ruins Wick's theorem.

### Confusing normal ordering with renormalization

Normal ordering is one kind of subtraction. Renormalization is the broader procedure of defining finite parameters and composite operators in a theory with ultraviolet sensitivity.

## Relation to other topics

- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) introduced the divergent zero-point term in the scalar Hamiltonian.
- [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) uses normal ordering to define charge and Hamiltonian operators with the expected vacuum eigenvalues.
- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) uses the same creation-annihilation split to compute causal field commutators.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) will compare normal ordering with time ordering.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) will turn this page into the main perturbative algorithm.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) will interpret contractions as propagator lines.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) will explain why normal ordering is not the end of renormalization.

## Research status

This page is textbook-standard material for free fields and perturbation theory around a free vacuum. The caveats are important: interacting composite operators, curved-spacetime vacuum definitions, gauge-invariant regularization, and anomaly-sensitive current definitions require more structure than the elementary colon notation.

## Exercises

### Exercise 1: One oscillator

Let $[a,a^\dagger]=1$. Compute $:aa^\dagger:$ and compare it with $aa^\dagger$.

<details>
<summary><strong>Solution</strong></summary>

By definition, normal ordering places the creation operator on the left:

$$
:aa^\dagger:=a^\dagger a.
$$

The ordinary product satisfies

$$
aa^\dagger=a^\dagger a+[a,a^\dagger]=a^\dagger a+1.
$$

Therefore

$$
aa^\dagger=:aa^\dagger:+1.
$$

The normal-ordered product differs from the ordinary product by the vacuum contraction.

</details>

### Exercise 2: Vacuum expectation of a normal product

Show that

$$
\langle0|:\phi(x)\phi(y):|0\rangle=0
$$

for a free scalar field.

<details>
<summary><strong>Solution</strong></summary>

Using $\phi=\phi_++\phi_-$,

$$
:\phi(x)\phi(y):
=\phi_-(x)\phi_-(y)+\phi_-(x)\phi_+(y)
+\phi_-(y)\phi_+(x)+\phi_+(x)\phi_+(y).
$$

In each term, either a creation operator stands at the far left or an annihilation operator stands at the far right. Since

$$
\langle0|\phi_-(x)=0,
\qquad
\phi_+(x)|0\rangle=0,
$$

every term gives zero between vacuum states. Hence

$$
\langle0|:\phi(x)\phi(y):|0\rangle=0.
$$

</details>

### Exercise 3: The contraction of two scalar fields

Show that

$$
\phi(x)\phi(y)=:\phi(x)\phi(y):+\Delta^+(x-y),
$$

where

$$
\Delta^+(x-y)=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

<details>
<summary><strong>Solution</strong></summary>

The ordinary product and normal-ordered product differ only by the ordering of $\phi_+(x)\phi_-(y)$:

$$
\phi_+(x)\phi_-(y)
=\phi_-(y)\phi_+(x)+[\phi_+(x),\phi_-(y)].
$$

Therefore

$$
\phi(x)\phi(y)=:\phi(x)\phi(y):+[\phi_+(x),\phi_-(y)].
$$

Using the mode expansion and oscillator algebra,

$$
[\phi_+(x),\phi_-(y)]
=\int d\mu(p)\,e^{-ip\cdot x}e^{ip\cdot y}
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

Thus

$$
[\phi_+(x),\phi_-(y)]=\Delta^+(x-y).
$$

</details>

### Exercise 4: Zero-point energy in a finite box

Put a real scalar field in a periodic box so that the normal modes are discrete. Show that the free Hamiltonian has the form

$$
H=\sum_{\mathbf k}E_{\mathbf k}
\left(a^\dagger_{\mathbf k}a_{\mathbf k}+\frac12\right),
$$

and that normal ordering gives

$$
:H:=\sum_{\mathbf k}E_{\mathbf k}a^\dagger_{\mathbf k}a_{\mathbf k}.
$$

<details>
<summary><strong>Solution</strong></summary>

Each real normal mode is a harmonic oscillator with Hamiltonian

$$
H_{\mathbf k}=E_{\mathbf k}
\left(a^\dagger_{\mathbf k}a_{\mathbf k}+\frac12\right).
$$

Summing over all modes gives

$$
H=\sum_{\mathbf k}E_{\mathbf k}a^\dagger_{\mathbf k}a_{\mathbf k}
+\frac12\sum_{\mathbf k}E_{\mathbf k}.
$$

The second term is a c-number. Normal ordering subtracts it because

$$
:a_{\mathbf k}a^\dagger_{\mathbf k}:=a^\dagger_{\mathbf k}a_{\mathbf k}.
$$

Thus

$$
:H:=\sum_{\mathbf k}E_{\mathbf k}a^\dagger_{\mathbf k}a_{\mathbf k}.
$$

</details>

### Exercise 5: Normal-ordered charge for a complex scalar

Suppose the complex scalar charge before normal ordering contains

$$
Q=q\int d\mu(p)\,
\left[a^\dagger(\mathbf p)a(\mathbf p)-b(\mathbf p)b^\dagger(\mathbf p)\right].
$$

Using the oscillator algebra, show that normal ordering gives

$$
:Q:=q\int d\mu(p)\,
\left[a^\dagger(\mathbf p)a(\mathbf p)-b^\dagger(\mathbf p)b(\mathbf p)\right]
$$

up to a discarded c-number.

<details>
<summary><strong>Solution</strong></summary>

The first term is already normal ordered. For the second term,

$$
b(\mathbf p)b^\dagger(\mathbf p')
=b^\dagger(\mathbf p')b(\mathbf p)
+(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf p').
$$

At coincident momentum labels this produces a formal c-number proportional to $\delta^{(3)}(0)$. Therefore

$$
-bb^\dagger=-b^\dagger b-\text{c-number}.
$$

Normal ordering keeps the operator part and subtracts the vacuum c-number:

$$
:Q:=q\int d\mu(p)\,
\left[a^\dagger a-b^\dagger b\right].
$$

The resulting charge annihilates the vacuum and counts particles and antiparticles with opposite signs.

</details>

### Exercise 6: Why not normal-order equations?

Explain the contradiction in the following invalid argument:

$$
aa^\dagger=a^\dagger a+1
\quad\Rightarrow\quad
:aa^\dagger:=:a^\dagger a+1:.
$$

<details>
<summary><strong>Solution</strong></summary>

The first equation is an equality of ordinary products. The colon expression is not an operation applied to an existing ordinary product; it defines a different product. The expression

$$
:aa^\dagger:
$$

is defined to be $a^\dagger a$, while

$$
:a^\dagger a+1:
$$

is not obtained by applying a valid algebra homomorphism to the right side of the ordinary equation. Treating normal ordering as a map on equations would imply

$$
a^\dagger a=a^\dagger a+1,
$$

which is false. The lesson is that the colons define an expression; they do not license “normal-ordering both sides” of an equation.

</details>

## References

### Primary references

- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), for Wick's theorem.
- F. J. Dyson, “The Radiation Theories of Tomonaga, Schwinger, and Feynman,” *Physical Review* **75** (1949), for the time-ordered perturbative expansion that Wick's theorem makes calculable.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, §§4.5 and 8.2, for the canonical scalar-field motivation for normal ordering and the transition to Wick contractions.
- M. Srednicki, *Quantum Field Theory*, §§3 and 9, for scalar quantization, normal ordering, and Wick's theorem.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §6.1, for Wick's theorem and contractions in the derivation of Feynman rules.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.8 and II.5, for vacuum energy, canonical quantization, and fermionic sign intuition.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.2 and 4.3, for the standard graduate-course presentation.

### For a first pass

- Coleman, §4.5.
- Srednicki, §3.
- Zee, ch. I.8.

### For mathematical precision

- R. Haag, *Local Quantum Physics*, for the conceptual limitations of field products and vacuum-dependent particle language.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for operator-valued distributions and local fields.

## Version history

- **2026-05-22:** Initial qft.org page on normal ordering, vacuum-energy subtraction, contractions, Wick expansion, fermionic signs, and caveats.
