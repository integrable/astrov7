---
title: "Time Ordering"
description: "Time-ordered products, fermion signs, contact terms, and the relation between Wightman functions, Feynman propagators, and perturbative Green functions."
sidebar:
  label: "Time Ordering"
  order: 2
---

## Summary

Time ordering is the operation that writes operators from latest time to earliest time. For two bosonic operators,

$$
T\{A(x)B(y)\}
=\theta(x^0-y^0)A(x)B(y)
+\theta(y^0-x^0)B(y)A(x).
$$

For fermionic operators, each interchange of two odd fermionic operators contributes a minus sign. Thus, for two fermionic operators,

$$
T\{\psi(x)\chi(y)\}
=\theta(x^0-y^0)\psi(x)\chi(y)
-\theta(y^0-x^0)\chi(y)\psi(x).
$$

Time-ordered vacuum expectation values are the Green functions of perturbative QFT:

$$
G_n(x_1,\ldots,x_n)
=\langle0|T\{\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\}|0\rangle.
$$

For a free scalar field,

$$
\boxed{
D_F(x-y)
=\langle0|T\{\phi(x)\phi(y)\}|0\rangle
}
$$

is the Feynman propagator. Time ordering is indispensable because Dyson's perturbative expansion is a time-ordered exponential, and Wick's theorem converts time-ordered products of free fields into normal-ordered products plus contractions.

This page is the bridge from operator quantization to propagators and perturbation theory. Coleman introduces the Schrödinger, Heisenberg, and interaction pictures before Dyson's formula and Wick diagrams; Weinberg derives time-ordered products in perturbation theory and then computes propagators from them; Srednicki uses time-ordered Green functions as the central objects connecting canonical quantization, path integrals, and LSZ (Coleman 2019, chs. 7, 8, and 13; Weinberg 1995, Vol. I, §§3.5, 6.1, 6.2, and 9.2; Srednicki 2007, §§5, 8, 9, and 13).

## Prerequisites

You should know [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/), [Normal Ordering](/foundations/canonical-quantization/normal-ordering/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), and [Free Field Summary](/foundations/free-fields/free-field-summary/).

## Core idea

Operator products in QFT do not generally commute. A time-ordered product chooses a canonical order: later insertions stand to the left.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Time ordering places later operators to the left and adds signs for fermionic interchanges](/figures/foundations/time-ordering-axis.svg)

<figcaption>

Time ordering sorts operators by their time coordinates. For bosonic operators, reordering introduces no sign. For fermionic operators, each interchange of two odd fermionic operators contributes a minus sign. The vacuum expectation value of the resulting ordered product is a time-ordered Green function.

</figcaption>
</figure>

Time ordering is not a statement that a particle literally travels first to one point and then to another. It is an ordering prescription on operator products.

:::note[Assumptions]
The definition uses a chosen Lorentz frame's time coordinate. For local relativistic fields, spacelike-separated bosonic operators commute and spacelike-separated fermionic operators anticommute, so the apparent frame dependence of ordering at spacelike separation does not spoil Lorentz covariance of physical time-ordered correlators. Equal-time products and composite operators can require contact-term prescriptions.
:::

## Definition for two operators

For two homogeneous operators $A$ and $B$, define their Grassmann parity by

$$
|A|=0\quad\text{for bosonic/even operators},
\qquad
|A|=1\quad\text{for fermionic/odd operators}.
$$

Then

$$
\boxed{
T\{A(x)B(y)\}
=\theta(x^0-y^0)A(x)B(y)
+(-1)^{|A||B|}\theta(y^0-x^0)B(y)A(x).
}
$$

So:

- two bosonic operators reorder with a plus sign;
- one bosonic and one fermionic operator reorder with a plus sign;
- two fermionic operators reorder with a minus sign.

In practice, most textbook formulas use this rule silently. The sign is not optional decoration; it is what makes fermionic Wick contractions and fermion-loop signs come out correctly.

## Definition for many operators

For several operators, $T$ sorts them by decreasing time coordinate:

$$
T\{\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\}
=\epsilon(\sigma)\,
\mathcal O_{\sigma(1)}(x_{\sigma(1)})\cdots
\mathcal O_{\sigma(n)}(x_{\sigma(n)}),
$$

when

$$
x^0_{\sigma(1)}>x^0_{\sigma(2)}>\cdots>x^0_{\sigma(n)}.
$$

The sign $\epsilon(\sigma)$ is the sign from moving odd fermionic operators past one another. Equivalently, it is $(-1)^N$, where $N$ is the number of interchanges of fermionic operators needed to reach the time-ordered arrangement.

If some times are equal, one must specify a convention. For most separated-point correlators the equal-time convention does not matter. It matters when derivatives act on time-ordered products or when composite operators collide.

## Scalar two-point function

For a real scalar field,

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle.
$$

Using the Wightman function

$$
\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle,
$$

we get

$$
\boxed{
D_F(x-y)
=\theta(x^0-y^0)\Delta^+(x-y)
+\theta(y^0-x^0)\Delta^+(y-x).
}
$$

For the free scalar,

$$
\Delta^+(x-y)
=\int d\mu(p)\,e^{-ip\cdot(x-y)},
$$

so

$$
D_F(x-y)
=\theta(x^0-y^0)\int d\mu(p)\,e^{-ip\cdot(x-y)}
+\theta(y^0-x^0)\int d\mu(p)\,e^{ip\cdot(x-y)}.
$$

This formula is not yet the most convenient momentum-space form. The next propagator pages rewrite it as

$$
D_F(x-y)=\int\frac{d^4p}{(2\pi)^4}
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ prescription is the momentum-space way of encoding the time-ordering boundary condition.

## Fermionic two-point function

For the Dirac field, the time-ordered two-point function is

$$
S_F(x-y)
=\langle0|T\{\psi(x)\overline\psi(y)\}|0\rangle.
$$

By the fermionic sign rule,

$$
\boxed{
S_F(x-y)
=\theta(x^0-y^0)\langle0|\psi(x)\overline\psi(y)|0\rangle
-\theta(y^0-x^0)\langle0|\overline\psi(y)\psi(x)|0\rangle.
}
$$

The minus sign is essential. It comes from exchanging two odd fermionic operators. In momentum space, with the qft.org conventions used on the free-field summary page,

$$
S_F(x-y)=\int\frac{d^4p}{(2\pi)^4}
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

Different books sometimes call the object with the factor of $i$ included or excluded “the propagator.” The convention on qft.org is to include the factor of $i$ in the Feynman-rule propagator.

## Why time ordering appears in perturbation theory

In the interaction picture, the time-evolution operator satisfies

$$
i\frac{d}{dt}U_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
$$

The solution is not simply $\exp[-i\int H_I dt]$ if $H_I(t)$ at different times fails to commute with itself. Instead,

$$
\boxed{
U_I(t,t_0)
=T\exp\left[-i\int_{t_0}^t dt'\,H_I(t')\right].
}
$$

Expanding the time-ordered exponential gives the Dyson series:

$$
U_I(t,t_0)
=1+(-i)\int_{t_0}^t dt_1\,H_I(t_1)
+\frac{(-i)^2}{2!}\int_{t_0}^t dt_1dt_2\,
T\{H_I(t_1)H_I(t_2)\}+\cdots.
$$

This is why perturbation theory naturally produces time-ordered products. Wick's theorem then reduces time-ordered products of free fields to contractions.

## Relation to normal ordering and contractions

For a free scalar field, the contraction of $\phi(x)$ with $\phi(y)$ is the time-ordered two-point function:

$$
\text{contraction of }\phi(x)\text{ and }\phi(y)
\equiv
\langle0|T\{\phi(x)\phi(y)\}|0\rangle
=D_F(x-y).
$$

The content is this:

$$
\boxed{
T\{\phi(x)\phi(y)\}
=:\phi(x)\phi(y):+D_F(x-y).
}
$$

For four scalar fields, Wick's theorem says

$$
\begin{aligned}
T\{\phi_1\phi_2\phi_3\phi_4\}
&=:\phi_1\phi_2\phi_3\phi_4:
+\text{all single contractions} \\
&\quad+\text{all double contractions}.
\end{aligned}
$$

Taking the vacuum expectation value kills the normal-ordered remainder and leaves only full contractions. This is the algebraic reason free-field correlators are sums over pairings.

## Contact terms

Time ordering uses step functions. Derivatives of time-ordered products therefore produce delta-function contact terms.

For two operators $A(t)$ and $B(t')$, suppressing spatial labels,

$$
T\{A(t)B(t')\}
=\theta(t-t')A(t)B(t')\pm\theta(t'-t)B(t')A(t).
$$

Differentiating with respect to $t$ gives

$$
\begin{aligned}
\frac{d}{dt}T\{A(t)B(t')\}
&=T\{\dot A(t)B(t')\} \\
&\quad+\delta(t-t')\left[A(t),B(t')\right]_{\pm},
\end{aligned}
$$

where

$$
[A,B]_{\pm}=AB\mp BA
$$

with the upper sign for bosonic time ordering and the graded version for fermionic operators. More invariantly, the contact term is the equal-time graded commutator appropriate to the two operators.

For the scalar Feynman propagator, this contact term is exactly what makes $D_F$ a Green function:

$$
\boxed{
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y)
}
$$

with qft.org's convention $D_F(p)=i/(p^2-m^2+i\epsilon)$.

:::caution[Do not throw away contact terms]
A very common error is to differentiate through a time-ordering symbol as though $T$ were an ordinary constant symbol. The derivative also acts on the step functions. Those delta-function terms are often the whole point: they are what turn propagators into Green functions and what produce Ward identities.
:::

## Lorentz covariance and spacelike separation

Time ordering seems to choose a preferred time coordinate. This is less dangerous than it looks.

If $x-y$ is timelike, all proper Lorentz frames agree on which event is later. If $x-y$ is spacelike, different frames can disagree about the order, but local fields obey microcausality:

$$
[\mathcal O_1(x),\mathcal O_2(y)]=0
\quad\text{for bosonic local operators at spacelike separation},
$$

and fermionic local operators anticommute at spacelike separation in the appropriate graded sense. Therefore reversing the order at spacelike separation changes nothing physically in a local theory.

For scalar fields,

$$
[\phi(x),\phi(y)]=0
\qquad ((x-y)^2<0).
$$

Thus

$$
\phi(x)\phi(y)=\phi(y)\phi(x)
$$

at spacelike separation, and the two possible time orderings agree.

This is also why the Feynman propagator can be Lorentz invariant even though it was defined using $x^0-y^0$.

## Feynman propagator versus causal response

The Feynman propagator is time ordered. The retarded propagator is causal:

$$
D_R(x-y)=i\theta(x^0-y^0)\langle0|[\phi(x),\phi(y)]|0\rangle,
$$

The retarded function vanishes unless $x$ is in or on the future light cone of $y$. The Feynman propagator does not vanish outside the light cone. That is not a violation of causality, because causality is controlled by commutators and retarded response, not by the time-ordered two-point function alone.

The rough division is:

| Object | Definition | Main use |
|---|---|---|
| Wightman function | $\langle0|\phi(x)\phi(y)|0\rangle$ | spectrum, positivity, vacuum structure |
| Pauli–Jordan function | $\langle0|[\phi(x),\phi(y)]|0\rangle$ | microcausality |
| Feynman propagator | $\langle0|T\{\phi(x)\phi(y)\}|0\rangle$ | perturbation theory and Feynman rules |
| Retarded propagator | $i\theta(x^0-y^0)\langle0|[\phi(x),\phi(y)]|0\rangle$ | causal response |

## Example: scalar propagator as a Green function

Let

$$
D_F(x-y)=\theta(x^0-y^0)\Delta^+(x-y)
+\theta(y^0-x^0)\Delta^+(y-x).
$$

Away from $x^0=y^0$, both terms obey the Klein–Gordon equation because each is built from on-shell modes. The only nonzero contribution to $(\Box+m^2)D_F$ comes from differentiating the step functions.

Using the equal-time canonical commutator

$$
[\phi(t,\mathbf x),\dot\phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

one obtains

$$
(\Box_x+m^2)D_F(x-y)=-i\delta(x^0-y^0)\delta^{(3)}(\mathbf x-\mathbf y).
$$

Therefore

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

This is the position-space form of

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

## Path-integral source form

With the qft.org Lorentzian source convention,

$$
Z[J]=\frac{1}{\mathcal N}\int\mathcal D\phi\,
\exp\left\{iS[\phi]+i\int d^4x\,J(x)\phi(x)\right\},
\qquad Z[0]=1.
$$

For the free real scalar field,

$$
\boxed{
Z_0[J]=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right],
}
$$

where $D_F$ includes the factor of $i$ in momentum space:

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

Functional differentiation inserts time-ordered fields:

$$
\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle
=\left.\frac{1}{i^n}
\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

This is the path-integral reason the Feynman propagator appears before the Wightman, retarded, and advanced propagators in many perturbative calculations. Other real-time orderings exist, but they require different contour prescriptions, such as Schwinger–Keldysh contours.

## Common pitfalls

### Forgetting fermion signs

Every interchange of two odd fermionic operators gives a minus sign. Missing this sign corrupts fermion propagators, Wick contractions, and loop signs.

### Treating time ordering as causal propagation

Time ordering is not the same as retarded propagation. The Feynman propagator is the right object for perturbative amplitudes, while the retarded propagator is the right object for causal response.

### Differentiating time-ordered products without contact terms

The derivative of $\theta(t-t')$ is $\delta(t-t')$. These terms are not small or optional; they often encode the canonical algebra.

### Confusing normal ordering and time ordering

Normal ordering moves creation operators left. Time ordering moves later-time operators left. They are different operations. Wick's theorem relates them for free fields.

### Ignoring equal-time ambiguity

At coincident times, time ordering alone is not always enough to define composite products. Local products of fields are distributions and may require regularization or renormalization.

## Relation to other topics

- [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/) defines the vacuum expectation values that time ordering acts on.
- [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/) studies the non-time-ordered correlators inside the time-ordered product.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) develops the scalar time-ordered two-point function as an inverse kinetic operator.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) contrasts time ordering with causal response.
- [i epsilon Prescription](/foundations/correlators-and-propagators/i-epsilon-prescription/) explains how the boundary condition appears in momentum space.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) turns time-ordered products into normal-ordered products plus contractions.
- [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) explains why perturbative evolution is a time-ordered exponential.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) generates time-ordered correlators by differentiating with respect to sources.

## Exercises

### Exercise 1: Two scalar fields

Show that

$$
\langle0|T\{\phi(x)\phi(y)\}|0\rangle
=\theta(x^0-y^0)\Delta^+(x-y)
+\theta(y^0-x^0)\Delta^+(y-x).
$$

<details>
<summary><strong>Solution</strong></summary>

For scalar fields, time ordering gives

$$
T\{\phi(x)\phi(y)\}
=\theta(x^0-y^0)\phi(x)\phi(y)
+\theta(y^0-x^0)\phi(y)\phi(x).
$$

Taking the vacuum expectation value gives

$$
\langle0|T\{\phi(x)\phi(y)\}|0\rangle
=\theta(x^0-y^0)\langle0|\phi(x)\phi(y)|0\rangle
+\theta(y^0-x^0)\langle0|\phi(y)\phi(x)|0\rangle.
$$

By definition,

$$
\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle,
$$

and

$$
\Delta^+(y-x)=\langle0|\phi(y)\phi(x)|0\rangle.
$$

This proves the formula.

</details>

### Exercise 2: Fermion sign

Let $\psi$ and $\chi$ be odd fermionic operators. Write $T\{\psi(x)\chi(y)\}$ explicitly for $x^0>y^0$ and for $y^0>x^0$.

<details>
<summary><strong>Solution</strong></summary>

If $x^0>y^0$, the operators are already in time-ordered order:

$$
T\{\psi(x)\chi(y)\}=\psi(x)\chi(y).
$$

If $y^0>x^0$, the later operator $\chi(y)$ must be moved to the left. Since both operators are fermionic, this interchange gives a minus sign:

$$
T\{\psi(x)\chi(y)\}=-\chi(y)\psi(x).
$$

Equivalently,

$$
T\{\psi(x)\chi(y)\}
=\theta(x^0-y^0)\psi(x)\chi(y)
-\theta(y^0-x^0)\chi(y)\psi(x).
$$

</details>

### Exercise 3: Spacelike frame ambiguity

Suppose $x-y$ is spacelike and $[\phi(x),\phi(y)]=0$. Explain why the scalar time-ordered product does not depend on which Lorentz frame is used to decide whether $x^0>y^0$.

<details>
<summary><strong>Solution</strong></summary>

For spacelike separation, different Lorentz frames can disagree about whether $x^0>y^0$ or $y^0>x^0$. The two possible scalar time orderings are

$$
\phi(x)\phi(y)
$$

and

$$
\phi(y)\phi(x).
$$

Microcausality says

$$
[\phi(x),\phi(y)]=\phi(x)\phi(y)-\phi(y)\phi(x)=0.
$$

Therefore

$$
\phi(x)\phi(y)=\phi(y)\phi(x)
$$

at spacelike separation. The two possible time orderings agree.

</details>

### Exercise 4: Contact term from differentiating a time-ordered product

For bosonic operators $A(t)$ and $B(t')$, show that

$$
\frac{d}{dt}T\{A(t)B(t')\}
=T\{\dot A(t)B(t')\}+\delta(t-t')[A(t),B(t')].
$$

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
T\{A(t)B(t')\}
=\theta(t-t')A(t)B(t')+\theta(t'-t)B(t')A(t).
$$

Differentiate:

$$
\begin{aligned}
\frac{d}{dt}T\{A(t)B(t')\}
&=\delta(t-t')A(t)B(t')+\theta(t-t')\dot A(t)B(t') \\
&\quad-\delta(t'-t)B(t')A(t)+\theta(t'-t)B(t')\dot A(t).
\end{aligned}
$$

Since $\delta(t'-t)=\delta(t-t')$, the delta terms combine into

$$
\delta(t-t')\left[A(t)B(t')-B(t')A(t)\right]
=\delta(t-t')[A(t),B(t')].
$$

The remaining terms are

$$
T\{\dot A(t)B(t')\}.
$$

Thus

$$
\frac{d}{dt}T\{A(t)B(t')\}
=T\{\dot A(t)B(t')\}+\delta(t-t')[A(t),B(t')].
$$

</details>

### Exercise 5: Scalar propagator Green equation

Using

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle,
$$

show that

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y)
$$

for a free scalar field with qft.org conventions.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
D_F(x-y)=\theta(x^0-y^0)\Delta^+(x-y)
+\theta(y^0-x^0)\Delta^+(y-x).
$$

Away from $x^0=y^0$, both Wightman functions obey the Klein–Gordon equation, so $(\Box_x+m^2)D_F$ has support only at equal time.

The contact term comes from differentiating the time-ordering step functions. A compact way to compute it is

$$
\partial_{x^0}D_F(x-y)
=\langle0|T\{\dot\phi(x)\phi(y)\}|0\rangle
+\delta(x^0-y^0)\langle0|[\phi(x),\phi(y)]|0\rangle.
$$

The equal-time field commutator vanishes, so the first derivative has no contact term. Differentiating again gives

$$
\partial_{x^0}^2D_F(x-y)
=\langle0|T\{\ddot\phi(x)\phi(y)\}|0\rangle
+\delta(x^0-y^0)\langle0|[\dot\phi(x),\phi(y)]|0\rangle.
$$

Using

$$
[\dot\phi(t,\mathbf x),\phi(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and the free equation $(\Box+m^2)\phi=0$ inside the time-ordered product, one obtains

$$
(\Box_x+m^2)D_F(x-y)
=-i\delta(x^0-y^0)\delta^{(3)}(\mathbf x-\mathbf y)
=-i\delta^{(4)}(x-y).
$$

</details>

### Exercise 6: Full contraction of four scalar fields

For a free scalar field, compute

$$
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle,
$$

where $\phi_j=\phi(x_j)$, in terms of $D_F(x_i-x_j)$.

<details>
<summary><strong>Solution</strong></summary>

Wick's theorem says that the vacuum expectation value of a time-ordered product of free scalar fields is the sum over all complete pairings. For four fields there are three complete pairings:

$$
(12)(34),\qquad (13)(24),\qquad (14)(23).
$$

Therefore

$$
\begin{aligned}
\langle0|T\{\phi_1\phi_2\phi_3\phi_4\}|0\rangle
&=D_F(x_1-x_2)D_F(x_3-x_4) \\
&\quad+D_F(x_1-x_3)D_F(x_2-x_4) \\
&\quad+D_F(x_1-x_4)D_F(x_2-x_3).
\end{aligned}
$$

There are no minus signs because the scalar field is bosonic.

</details>

## Sources and further reading

### Primary references

- F. J. Dyson, “The Radiation Theories of Tomonaga, Schwinger, and Feynman,” *Physical Review* **75** (1949), for the time-ordered perturbative expansion.
- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), for Wick's theorem and contractions.
- H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* **1** (1955), for the use of time-ordered Green functions in the reduction formula.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 7, 8, and 13, for the Heisenberg and interaction pictures, Dyson's formula, Wick diagrams, and Green functions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§3.5, 6.1, 6.2, and 9.2, for time-ordered products in perturbation theory, Wick's theorem, propagators, and the S-matrix limit.
- M. Srednicki, *Quantum Field Theory*, §§5, 8, 9, and 13, for LSZ, path-integral Green functions, Wick expansion, and spectral representation.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§2.4 and 4.2–4.3, for the standard scalar and fermion time-ordering conventions.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9 and II.5, for a compact physical discussion of Feynman diagrams, canonical quantization, vacuum contractions, and fermion signs.

### For a first pass

- Coleman, §§7.3 and 8.2.
- Srednicki, §9.
- Peskin and Schroeder, §4.2.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the relation between time-ordered products, locality, and Wightman functions.
- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for causal perturbation theory and distributional contact terms.
- K. Fredenhagen and K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, for a modern algebraic treatment of time-ordered products as renormalized multilinear maps.

## Version history

- **2026-05-23:** Initial qft.org page on time-ordered products, fermion signs, Dyson expansion, Wick contractions, contact terms, Lorentz covariance, and the scalar Green-function equation.
