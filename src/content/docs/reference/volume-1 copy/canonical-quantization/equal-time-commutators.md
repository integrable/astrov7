---
title: "Equal-Time Commutators"
description: "How the scalar equal-time canonical algebra determines the Pauli–Jordan commutator, causal support, retarded propagation, and the distinction between commutators and propagators."
sidebar:
  label: "Equal-Time Commutators"
  order: 6
---

## Summary

The canonical algebra is imposed at equal time:

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0,
\qquad
[\pi(t,\mathbf x),\pi(t,\mathbf y)]=0,
$$

and

$$
\boxed{
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
}
$$

For the free real scalar field, these equal-time relations determine the commutator at arbitrary spacetime separation:

$$
\boxed{
[\phi(x),\phi(y)]=i\Delta(x-y),
}
$$

where, in qft.org's convention,

$$
\boxed{
 i\Delta(z)
=\int d\mu(p)\,
\left(e^{-ip\cdot z}-e^{ip\cdot z}\right),
\qquad z=x-y.
}
$$

The Pauli–Jordan function $\Delta(z)$ obeys the Klein–Gordon equation in each argument and has equal-time initial data

$$
\Delta(0,\mathbf r)=0,
\qquad
\partial_t\Delta(t,\mathbf r)\big|_{t=0}=-\delta^{(3)}(\mathbf r).
$$

Its most important structural property is microcausality:

$$
\boxed{
[\phi(x),\phi(y)]=0
\quad\text{when}\quad
(x-y)^2<0.
}
$$

So spacelike-separated scalar field operators commute. This is not the statement that the Feynman propagator vanishes outside the light cone. It does not. Causality is carried by commutators and retarded response functions, not by the time-ordered two-point function alone.

Weinberg derives the equal-time canonical algebra from causal free fields in his general canonical formalism; Coleman uses the scalar commutator function to check canonical commutators and causal support; Srednicki derives the same equal-time relations directly from scalar mode quantization (Weinberg 1995, Vol. I, §§5.2 and 7.1; Coleman 2019, chs. 3–4 and 26; Srednicki 2007, §3).

## Prerequisites

You should know [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), and [Normal Ordering](/foundations/canonical-quantization/normal-ordering/). We use the conventions of [Conventions and Normalizations](/foundations/conventions-and-normalizations/): mostly-minus metric, $p\cdot x=p^0t-\mathbf p\cdot\mathbf x$, and

$$
d\mu(p)=\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}.
$$

## Core idea

The page [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) explained the initial algebra on a time slice. This page asks what that algebra becomes after time evolution.

For a free scalar field, the answer is exact: the field commutator is the Pauli–Jordan function. Its equal-time values reproduce the canonical algebra, and its support enforces relativistic causality.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Equal-time canonical data propagate into the Pauli–Jordan commutator with light-cone support](/figures/foundations/equal-time-commutator-support.svg)

<figcaption>

The equal-time canonical algebra gives initial data for the Pauli–Jordan commutator. Lorentz invariance and the Klein–Gordon equation propagate that data so that the field commutator vanishes at spacelike separation, while it can be nonzero inside the light cone.

</figcaption>
</figure>

This is the first place where the operator formalism visibly knows about causal structure. The equal-time commutator has a delta function on the initial slice. The full spacetime commutator has light-cone support.

:::note[Assumptions]
This page treats free scalar fields in flat Minkowski spacetime. The interacting generalization of microcausality is a structural assumption or theorem of a properly defined local QFT, not something obtained by inserting the free Pauli–Jordan function into an interacting field. Gauge fields and constrained systems require extra care.
:::

## From the mode expansion

The real scalar field has expansion

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

with

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

and all $[a,a]$ and $[a^\dagger,a^\dagger]$ commutators zero. Then

$$
\begin{aligned}
[\phi(x),\phi(y)]
&=\int d\mu(p)d\mu(q)
\left[
 a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x},
 a(\mathbf q)e^{-iq\cdot y}+a^\dagger(\mathbf q)e^{iq\cdot y}
\right] \\
&=\int d\mu(p)\,
\left(e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}\right).
\end{aligned}
$$

Define $\Delta$ by

$$
[\phi(x),\phi(y)]=i\Delta(x-y).
$$

Thus

$$
i\Delta(z)=\int d\mu(p)\,
\left(e^{-ip\cdot z}-e^{ip\cdot z}\right).
$$

Because both exponentials are on shell,

$$
(\Box_z+m^2)\Delta(z)=0
$$

as a distribution.

The function $\Delta$ is real and antisymmetric:

$$
\Delta(-z)=-\Delta(z).
$$

Therefore

$$
[\phi(y),\phi(x)]=-[\phi(x),\phi(y)],
$$

as it must.

## Equal-time initial data

Set $z=(t,\mathbf r)$. At equal time, $t=0$, one has

$$
i\Delta(0,\mathbf r)
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{i\mathbf p\cdot\mathbf r}-e^{-i\mathbf p\cdot\mathbf r}\right).
$$

The integrand is odd under $\mathbf p\mapsto-\mathbf p$, so

$$
\Delta(0,\mathbf r)=0.
$$

Thus

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0.
$$

Now differentiate with respect to the first time argument:

$$
\partial_{x^0}[\phi(x),\phi(y)]
=[\dot\phi(x),\phi(y)]
=[\pi(x),\phi(y)].
$$

Using the integral expression at $x^0=y^0$ gives

$$
[\pi(t,\mathbf x),\phi(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Equivalently,

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Differentiating with respect to both times gives

$$
[\pi(t,\mathbf x),\pi(t,\mathbf y)]=0.
$$

So the arbitrary-time commutator reproduces the equal-time canonical algebra exactly.

In terms of $\Delta$, the initial data are

$$
\Delta(0,\mathbf r)=0,
$$

and

$$
\partial_t\Delta(t,\mathbf r)\big|_{t=0}
=-\delta^{(3)}(\mathbf r).
$$

The minus sign comes from the convention $[\phi(x),\phi(y)]=i\Delta(x-y)$ together with $p\cdot x=E_{\mathbf p}t-\mathbf p\cdot\mathbf x$. Some books define the Pauli–Jordan function with the opposite sign.

## Why the commutator vanishes at spacelike separation

The integral expression for $\Delta(z)$ is Lorentz invariant. For a scalar field, the commutator $[\phi(x),\phi(y)]$ transforms as a scalar distribution.

If $z=x-y$ is spacelike, then there exists an inertial frame in which

$$
z^0=0.
$$

In that frame,

$$
\Delta(z)=\Delta(0,\mathbf z)=0.
$$

Since $\Delta$ is Lorentz invariant, it must vanish in every frame:

$$
\boxed{
\Delta(z)=0\quad\text{for}\quad z^2<0.
}
$$

Therefore

$$
[\phi(x),\phi(y)]=0
\quad\text{for spacelike}\quad x-y.
$$

This is microcausality for the free scalar field. It says that local scalar field operators commute at spacelike separation, so their order cannot affect spacelike-separated measurements.

This proof is wonderfully short because it uses three ingredients at once:

- the equal-time canonical algebra;
- Lorentz invariance;
- the scalar transformation law for $\phi$.

Drop any of these ingredients and the conclusion is no longer automatic.

## What vanishes and what does not

The commutator vanishes outside the light cone. The Wightman function does not:

$$
\Delta^+(x-y)=\langle0|\phi(x)\phi(y)|0\rangle
=\int d\mu(p)\,e^{-ip\cdot(x-y)}.
$$

The Feynman propagator also does not vanish at spacelike separation:

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle.
$$

This is a major source of student confusion. The Feynman propagator is not a classical causal response function. It is a time-ordered vacuum two-point function. Causality is encoded in the cancellation between the two Wightman orderings inside the commutator:

$$
[\phi(x),\phi(y)]
=\langle0|\phi(x)\phi(y)|0\rangle
-\langle0|\phi(y)\phi(x)|0\rangle
$$

for the free scalar field.

At spacelike separation, the two terms can each be nonzero, but their difference vanishes.

## Retarded and advanced response

A causal response function can be built from the commutator. With our sign convention, define

$$
G_R(x-y)=i\theta(x^0-y^0)[\phi(x),\phi(y)]
=-\theta(x^0-y^0)\Delta(x-y).
$$

Then $G_R$ vanishes unless $x$ is in or on the future light cone of $y$. It is the retarded Green function, up to the sign convention used for the kinetic operator:

$$
(\Box_x+m^2)G_R(x-y)=\delta^{(4)}(x-y).
$$

Similarly, the advanced response is supported in the past light cone.

The Feynman propagator instead solves the same differential equation with Feynman boundary conditions:

$$
(\Box_x+m^2)D_F(x-y)=\text{contact term},
$$

where the precise factor of $i$ depends on whether one defines $D_F$ as $\langle T\phi\phi\rangle$, $i\Delta_F$, or $\Delta_F$. The support and boundary condition are the real point: retarded and advanced propagators are causal response functions; the Feynman propagator is the object adapted to perturbative vacuum amplitudes.

## Derivative commutators

Since

$$
\pi(x)=\dot\phi(x),
$$

derivative commutators are obtained by differentiating the Pauli–Jordan function:

$$
[\pi(x),\phi(y)]
=\partial_{x^0}[\phi(x),\phi(y)]
=i\partial_{x^0}\Delta(x-y),
$$

$$
[\phi(x),\pi(y)]
=\partial_{y^0}[\phi(x),\phi(y)]
=-i\partial_{x^0}\Delta(x-y),
$$

and

$$
[\pi(x),\pi(y)]
=\partial_{x^0}\partial_{y^0}[\phi(x),\phi(y)].
$$

At equal time this gives

$$
[\pi(t,\mathbf x),\phi(t,\mathbf y)]
=-i\delta^{(3)}(\mathbf x-\mathbf y),
$$

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
[\pi(t,\mathbf x),\pi(t,\mathbf y)]=0.
$$

For non-equal times, these derivative commutators generally have support inside or on the light cone, just like $\Delta$ and its derivatives.

## Complex scalar field

For the free complex scalar field,

$$
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and

$$
\Phi^\dagger(x)=\int d\mu(p)
\left[a^\dagger(\mathbf p)e^{ip\cdot x}+b(\mathbf p)e^{-ip\cdot x}\right].
$$

The nonzero field commutator is

$$
[\Phi(x),\Phi^\dagger(y)]=i\Delta(x-y),
$$

while

$$
[\Phi(x),\Phi(y)]=0,
\qquad
[\Phi^\dagger(x),\Phi^\dagger(y)]=0.
$$

The canonical momenta are

$$
\Pi_\Phi=\dot\Phi^\dagger,
\qquad
\Pi_{\Phi^\dagger}=\dot\Phi.
$$

At equal time,

$$
[\Phi(t,\mathbf x),\Pi_\Phi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

and

$$
[\Phi^\dagger(t,\mathbf x),\Pi_{\Phi^\dagger}(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y),
$$

with the other elementary commutators zero.

The microcausality statement is the same: charged scalar fields commute with their adjoints at spacelike separation because $\Delta$ vanishes there.

## Fermions and gauge fields

For fermions, the basic canonical relations are anticommutators, not commutators. Schematically,

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y).
$$

The locality statement is also graded: fermionic fields anticommute at spacelike separation, while physical bosonic observables built from fermion bilinears commute at spacelike separation.

Gauge fields require additional caution. Some components are constrained or gauge-dependent, so naive equal-time commutators among all components are not correct. One must fix gauge, reduce to physical variables, or use Dirac brackets. The gauge-invariant local observables, such as field strengths, obey the appropriate locality properties.

## Fields are distributions

The formulas above are written at sharp spacetime points, but quantum fields are operator-valued distributions. More honestly, one should smear them:

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
$$

with a test function $f$. Then commutators such as

$$
[\phi(f),\phi(g)]
$$

are well-defined when $f$ and $g$ are suitable test functions. The distributional delta functions and light-cone singularities are not bugs; they are the local-field version of having infinitely many degrees of freedom.

This caveat becomes essential for products at the same point, such as $\phi^2(x)$ or $T_{\mu\nu}(x)$. Normal ordering is one way to define some free-field composite operators, but interacting composite operators require renormalization.

## Common pitfalls

### Pitfall 1: Replacing equal-time with four-dimensional delta functions

The canonical algebra is not

$$
[\phi(x),\pi(y)]=i\delta^{(4)}(x-y).
$$

It is an equal-time relation on a Cauchy slice:

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

### Pitfall 2: Thinking the Feynman propagator must vanish outside the light cone

It need not. Microcausality is a statement about commutators, not about individual Wightman functions or the Feynman propagator.

### Pitfall 3: Forgetting sign conventions for the Pauli–Jordan function

Some books define $\Delta$ by $[\phi(x),\phi(y)]=i\Delta(x-y)$; others define it with the opposite sign or absorb factors of $i$ into the propagator. Always check the convention before comparing formulas.

### Pitfall 4: Applying unconstrained scalar commutators to gauge fields

Gauge theories have constraints. Their canonical brackets are not obtained by imposing scalar-field commutators on every component of $A_\mu$.

## Relation to other topics

- [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) explains the initial equal-time algebra.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) derives the scalar mode expansion and oscillator algebra used here.
- [Normal Ordering](/foundations/canonical-quantization/normal-ordering/) uses the same creation-annihilation split to define vacuum-subtracted products.
- [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/) will package the scalar field, equations of motion, and propagator summary.
- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) will give a fuller propagator-focused treatment.
- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) will state the interacting structural principle.

## Research status

For free scalar fields, the Pauli–Jordan commutator and its equal-time limits are textbook-standard. For interacting QFT, locality is a foundational axiom or a theorem within particular constructive frameworks. For gauge theories, locality must be stated carefully in terms of gauge-invariant observables or properly gauge-fixed variables.

## Exercises

### Exercise 1: Derive the Pauli–Jordan integral

Starting from

$$
\phi(x)=\int d\mu(p)\,
\left[a(\mathbf p)e^{-ip\cdot x}+a^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

show that

$$
[\phi(x),\phi(y)]
=\int d\mu(p)\,
\left(e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}\right).
$$

<details>
<summary><strong>Solution</strong></summary>

Only the mixed commutators contribute:

$$
[a(\mathbf p),a^\dagger(\mathbf q)]
=(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q),
$$

and

$$
[a^\dagger(\mathbf p),a(\mathbf q)]
=-(2\pi)^3 2E_{\mathbf p}\delta^{(3)}(\mathbf p-\mathbf q).
$$

Thus

$$
\begin{aligned}
[\phi(x),\phi(y)]
&=\int d\mu(p)d\mu(q)\,
\Big(e^{-ip\cdot x}e^{iq\cdot y}[a(\mathbf p),a^\dagger(\mathbf q)] \\
&\hspace{4.8cm}+e^{ip\cdot x}e^{-iq\cdot y}[a^\dagger(\mathbf p),a(\mathbf q)]\Big) \\
&=\int d\mu(p)\,
\left(e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}\right).
\end{aligned}
$$

</details>

### Exercise 2: Equal-time field commutator

Use the integral expression to show that

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

At equal time, $z=x-y=(0,\mathbf x-\mathbf y)$. Then

$$
[\phi(x),\phi(y)]
=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}-e^{-i\mathbf p\cdot(\mathbf x-\mathbf y)}\right).
$$

The second term becomes the first term under $\mathbf p\mapsto-\mathbf p$. Since the measure is invariant under this change of variables, the two terms cancel. Hence

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0.
$$

</details>

### Exercise 3: Equal-time field-momentum commutator

Differentiate the spacetime commutator with respect to $y^0$ and show that

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

<details>
<summary><strong>Solution</strong></summary>

Since $\pi(y)=\partial_{y^0}\phi(y)$,

$$
[\phi(x),\pi(y)]
=\partial_{y^0}[\phi(x),\phi(y)].
$$

Using

$$
[\phi(x),\phi(y)]
=\int d\mu(p)\,
\left(e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}\right),
$$

we get, at $x^0=y^0$,

$$
\partial_{y^0}e^{-ip\cdot(x-y)}=iE_{\mathbf p}e^{i\mathbf p\cdot(\mathbf x-\mathbf y)},
$$

and

$$
\partial_{y^0}e^{ip\cdot(x-y)}=-iE_{\mathbf p}e^{-i\mathbf p\cdot(\mathbf x-\mathbf y)}.
$$

Therefore

$$
\begin{aligned}
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
&=\int\frac{d^3\mathbf p}{(2\pi)^3 2E_{\mathbf p}}
\left(iE_{\mathbf p}e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}
+iE_{\mathbf p}e^{-i\mathbf p\cdot(\mathbf x-\mathbf y)}\right) \\
&=i\int\frac{d^3\mathbf p}{(2\pi)^3}
 e^{i\mathbf p\cdot(\mathbf x-\mathbf y)} \\
&=i\delta^{(3)}(\mathbf x-\mathbf y).
\end{aligned}
$$

In the second line we used the fact that the two exponential terms give the same integral after $\mathbf p\mapsto-\mathbf p$.

</details>

### Exercise 4: Lorentz proof of spacelike vanishing

Assume $\Delta(z)$ is Lorentz invariant and $\Delta(0,\mathbf r)=0$. Show that $\Delta(z)=0$ for every spacelike $z$.

<details>
<summary><strong>Solution</strong></summary>

If $z$ is spacelike, then $z^2<0$. There exists a Lorentz frame in which the time component of $z$ vanishes:

$$
z'=(0,\mathbf r').
$$

Since $\Delta$ is Lorentz invariant,

$$
\Delta(z)=\Delta(z').
$$

But $z'$ is an equal-time separation, so

$$
\Delta(z')=\Delta(0,\mathbf r')=0.
$$

Hence

$$
\Delta(z)=0
$$

for spacelike $z$.

</details>

### Exercise 5: Complex scalar commutators

Using the complex scalar expansion, show that

$$
[\Phi(x),\Phi^\dagger(y)]=i\Delta(x-y),
$$

and

$$
[\Phi(x),\Phi(y)]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The expansion is

$$
\Phi(x)=\int d\mu(p)
\left[a(\mathbf p)e^{-ip\cdot x}+b^\dagger(\mathbf p)e^{ip\cdot x}\right],
$$

and

$$
\Phi^\dagger(y)=\int d\mu(q)
\left[a^\dagger(\mathbf q)e^{iq\cdot y}+b(\mathbf q)e^{-iq\cdot y}\right].
$$

The $a$-$a^\dagger$ commutator contributes

$$
\int d\mu(p)e^{-ip\cdot(x-y)},
$$

while the $b^\dagger$-$b$ commutator contributes

$$
-\int d\mu(p)e^{ip\cdot(x-y)}.
$$

Therefore

$$
[\Phi(x),\Phi^\dagger(y)]
=\int d\mu(p)
\left(e^{-ip\cdot(x-y)}-e^{ip\cdot(x-y)}\right)
=i\Delta(x-y).
$$

For $[\Phi(x),\Phi(y)]$, the only possible mixed terms would involve $[a,b^\dagger]$ or $[b^\dagger,a]$, but the two oscillator species commute. Thus

$$
[\Phi(x),\Phi(y)]=0.
$$

</details>

### Exercise 6: Why the Feynman propagator can be nonzero spacelike

Explain why microcausality does not require

$$
D_F(x-y)=0
$$

for spacelike $x-y$.

<details>
<summary><strong>Solution</strong></summary>

Microcausality requires the commutator to vanish:

$$
[\phi(x),\phi(y)]=0
\quad\text{for spacelike}\quad x-y.
$$

The Feynman propagator is a time-ordered vacuum expectation value:

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle.
$$

For spacelike separation, different Lorentz frames can disagree about the time ordering of $x$ and $y$. The causal statement is that swapping the order of the operators makes no difference:

$$
\phi(x)\phi(y)=\phi(y)\phi(x)
$$

at spacelike separation. This requires the difference of the two Wightman functions to vanish, not each Wightman function separately. Thus $D_F$ may be nonzero at spacelike separation without violating causality.

</details>

## References

### Primary references

- W. Pauli and V. Weisskopf, “Über die Quantisierung der skalaren relativistischen Wellengleichung,” *Helvetica Physica Acta* **7** (1934), for the scalar field interpretation of the relativistic wave equation.
- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), for the time-ordered products that later lead to Feynman propagators.
- A. S. Wightman, “Quantum Field Theory in Terms of Vacuum Expectation Values,” *Physical Review* **101** (1956), for the structural role of vacuum correlators and locality.

### Standard textbook treatments

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.2 and 7.1, for causal scalar fields and equal-time canonical variables.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3–4, for the scalar commutator function and canonical commutators; ch. 26 gives an analogous vector-field check.
- M. Srednicki, *Quantum Field Theory*, §3, for the scalar equal-time commutators and oscillator algebra.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §2.3, for the Pauli–Jordan function and microcausality in the scalar theory.
- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, for the causal-commutator viewpoint.

### For a first pass

- Srednicki, §3.
- Coleman, chs. 3–4.
- Peskin and Schroeder, §2.3.

### For mathematical precision

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for locality, fields as distributions, and Wightman functions.
- R. Haag, *Local Quantum Physics*, for the operator-algebraic formulation of locality and causal commutation.
- N. N. Bogoliubov, A. A. Logunov, A. I. Oksak, and I. T. Todorov, *General Principles of Quantum Field Theory*, for a rigorous treatment of relativistic locality.

## Version history

- **2026-05-22:** Initial qft.org page on equal-time commutators, the Pauli–Jordan function, causal support, retarded response, complex scalar commutators, pitfalls, and exercises.
