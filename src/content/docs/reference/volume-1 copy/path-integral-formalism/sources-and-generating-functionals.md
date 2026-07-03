---
title: "Sources and Generating Functionals"
description: "External sources, Z[J] and W[J], full and connected correlation functions, functional differentiation, interaction expansions, Schwinger–Dyson and Ward identities, vacuum-bubble cancellation, and the first Legendre-transform preview of the effective action."
sidebar:
  label: "Sources and Generating Functionals"
  order: 4
---

## Summary

A source is a classical probe coupled linearly to a quantum field. For a real scalar field,

$$
S_J[\phi]=S[\phi]+\int d^4x\,J(x)\phi(x).
$$

The normalized source functional is

$$
\boxed{
Z[J]
=\frac{\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^4x\,J\phi\right)}
{\int\mathcal D\phi\,e^{iS[\phi]}}
}
\qquad
Z[0]=1.
$$

Functional derivatives of $Z[J]$ insert fields:

$$
\boxed{
G_n(x_1,\ldots,x_n)
=\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle
=\left.\frac{1}{i^n}
\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
}
$$

The logarithm of $Z[J]$ generates the connected correlators. With qft.org's Lorentzian convention,

$$
\boxed{
Z[J]=e^{iW[J]},
\qquad
G_n^{\mathrm c}(x_1,\ldots,x_n)
=\left.i^{1-n}\frac{\delta^n W[J]}
{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
}
$$

This page makes explicit the source calculus that was used implicitly in [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/). Coleman phrases the central result as $Z[J]=e^{iW[J]}$, with $Z[J]$ generating full Green functions and $W[J]$ generating connected Green functions; the normalization $Z[0]=1$ removes vacuum-to-vacuum graphs (Coleman 2019, ch. 32). Srednicki and Weinberg use the same source-functional machinery as the compact route from path integrals to Feynman rules, renormalized correlators, and effective actions (Srednicki 2007, §§8–9, 21, 29; Weinberg 1995, Vol. I, §§9.1–9.4; Weinberg 1996, Vol. II, §16.1).

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), [Finite-Dimensional Gaussians](/foundations/path-integral-formalism/finite-dimensional-gaussians/), and [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/).

## Core idea

A source is a handle on the field. Instead of computing every correlation function separately, introduce $J(x)$, compute one functional $Z[J]$, and obtain correlators by differentiating with respect to $J$.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Source functional hierarchy from Z to W and Γ](/figures/foundations/source-functional-hierarchy.svg)

<figcaption>

The source $J$ couples linearly to $\phi$. The functional $Z[J]$ generates full time-ordered correlators. Its logarithm $W[J]$ generates connected correlators. The Legendre transform to $\Gamma[\varphi]$ reorganizes the same information into one-particle-irreducible vertices; this last step is only previewed here.

</figcaption>
</figure>

The hierarchy is:

| Object | What it generates | Informal role |
|---|---|---|
| $Z[J]$ | full correlators | all moments |
| $W[J]$ | connected correlators | cumulants |
| $\Gamma[\varphi]$ | one-particle-irreducible vertices | quantum action |

The analogy with probability theory is useful but imperfect. In probability theory, a moment-generating function gives moments and its logarithm gives cumulants. In Lorentzian QFT, phases and factors of $i$ enter, and the correlators are time-ordered vacuum expectation values rather than ordinary random-variable moments.

## Sources are probes, not new quantum fields

For a real scalar field, the source-deformed action is

$$
S_J[\phi]
=S[\phi]+\int d^4x\,J(x)\phi(x).
$$

The source $J(x)$ is usually a c-number function: it is not integrated over, not quantized, and not an additional dynamical field. It is a probe that lets us measure the response of the vacuum to field insertions.

In the operator language, one may think schematically of adding a source-dependent interaction Hamiltonian. In the path-integral language, one adds the term $i\int J\phi$ to the exponent. The source is set to zero after differentiation unless one is studying a genuine external-background problem.

:::note[Assumptions]
This page uses a single real scalar field to keep notation readable. Multiple fields require indices; fermionic fields require Grassmann sources; gauge fields require gauge fixing and ghosts before source differentiation is meaningful. Composite-operator sources need additional renormalization.
:::

The normalized Lorentzian functional is

$$
Z[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^4x\,J\phi\right),
\qquad
\mathcal N=\int\mathcal D\phi\,e^{iS[\phi]}.
$$

The normalization makes

$$
Z[0]=1.
$$

That one innocent-looking equation is doing real work: it removes disconnected vacuum bubbles from normalized correlators.

## Full correlators from Z

Differentiating $Z[J]$ inserts fields because

$$
\frac{\delta}{\delta J(x)}
\exp\left(i\int d^4z\,J(z)\phi(z)\right)
=i\phi(x)
\exp\left(i\int d^4z\,J(z)\phi(z)\right).
$$

Therefore

$$
\frac{\delta Z[J]}{\delta J(x)}
=i\,\langle\phi(x)\rangle_J Z[J],
$$

where

$$
\langle\mathcal O\rangle_J
=\frac{\int\mathcal D\phi\,\mathcal O[\phi]
\exp\left(iS[\phi]+i\int J\phi\right)}
{\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int J\phi\right)}.
$$

At $J=0$, using $Z[0]=1$,

$$
\left.\frac{1}{i}\frac{\delta Z[J]}{\delta J(x)}\right|_{J=0}
=\langle0|\phi(x)|0\rangle.
$$

Similarly,

$$
\boxed{
\left.\frac{1}{i^n}\frac{\delta^nZ[J]}
{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}
=\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle.
}
$$

The time ordering is not something added afterward. It is built into the Lorentzian vacuum path integral through the same boundary prescription that defines the Feynman propagator.

For example,

$$
G_2(x,y)
=\langle0|T\{\phi(x)\phi(y)\}|0\rangle
=\left.\frac{1}{i^2}\frac{\delta^2Z[J]}{\delta J(x)\delta J(y)}\right|_{J=0}.
$$

The four-point function is

$$
G_4(x_1,x_2,x_3,x_4)
=\left.\frac{1}{i^4}\frac{\delta^4Z[J]}{\delta J(x_1)\delta J(x_2)\delta J(x_3)\delta J(x_4)}\right|_{J=0}.
$$

This is a full correlator. It includes both connected and disconnected contributions.

## Connected correlators from W

Define

$$
\boxed{Z[J]=e^{iW[J]}.}
$$

Equivalently,

$$
W[J]=-i\log Z[J].
$$

The logarithm selects connected correlators. In diagram language, this is the statement that the exponential of the sum of connected diagrams is the sum of all diagrams. In probability language, $W$ is the QFT analogue of the cumulant-generating functional.

Expanding $iW[J]$ around $J=0$ gives

$$
\boxed{
iW[J]
=\sum_{n=1}^{\infty}\frac{i^n}{n!}
\int d^4x_1\cdots d^4x_n\,
J(x_1)\cdots J(x_n)
G_n^{\mathrm c}(x_1,\ldots,x_n).
}
$$

Thus

$$
G_n^{\mathrm c}(x_1,\ldots,x_n)
=\left.\frac{1}{i^n}
\frac{\delta^n(iW[J])}
{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}
=\left.i^{1-n}
\frac{\delta^nW[J]}
{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

The first derivative gives the one-point function:

$$
\boxed{
\frac{\delta W[J]}{\delta J(x)}=\langle\phi(x)\rangle_J.
}
$$

The second derivative gives the connected two-point function, up to the Lorentzian factor:

$$
\boxed{
G_2^{\mathrm c}(x,y)
=-i\left.\frac{\delta^2W[J]}{\delta J(x)\delta J(y)}\right|_{J=0}.
}
$$

More generally, when signs feel slippery, go back to the expansion of $iW[J]$. It is the cleanest way to recover every factor of $i$.

## Free scalar example

For the free real scalar field,

$$
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right].
$$

Therefore

$$
iW_0[J]
=-\frac12\int J D_F J,
$$

or

$$
\boxed{
W_0[J]
=\frac{i}{2}\int d^4x\,d^4y\,J(x)D_F(x-y)J(y).
}
$$

Now differentiate:

$$
\frac{\delta^2W_0[J]}{\delta J(x)\delta J(y)}
=iD_F(x-y).
$$

Thus

$$
G_2^{\mathrm c}(x,y)
=-i\frac{\delta^2W_0}{\delta J(x)\delta J(y)}
=D_F(x-y).
$$

Since $W_0[J]$ is quadratic in $J$, all connected correlators with $n>2$ vanish:

$$
G_{n>2,0}^{\mathrm c}=0.
$$

The full four-point function does not vanish, because $Z_0=e^{iW_0}$ contains products of the quadratic connected piece. Differentiating $Z_0[J]$ four times gives

$$
\boxed{
G_{4,0}(x_1,x_2,x_3,x_4)
=D_F(x_1-x_2)D_F(x_3-x_4)
+D_F(x_1-x_3)D_F(x_2-x_4)
+D_F(x_1-x_4)D_F(x_2-x_3).
}
$$

That is Wick's theorem for the free scalar field.

## Adding interactions by differentiation

Suppose

$$
S[\phi]=S_0[\phi]+S_{\mathrm{int}}[\phi].
$$

For a polynomial interaction, powers of $\phi(x)$ inside $S_{\mathrm{int}}$ can be represented by source derivatives:

$$
\phi(x)\longrightarrow \frac{1}{i}\frac{\delta}{\delta J(x)}.
$$

Thus the interacting generating functional can be written formally as

$$
\boxed{
Z[J]
=\frac{1}{\mathcal N}
\exp\left(iS_{\mathrm{int}}\!\left[\frac1i\frac{\delta}{\delta J}\right]\right)
Z_0[J],
}
$$

where $\mathcal N$ is chosen so that $Z[0]=1$.

For example, in scalar $\phi^4$ theory,

$$
S_{\mathrm{int}}[\phi]
=-\frac{\lambda}{4!}\int d^4x\,\phi^4(x).
$$

Then

$$
Z[J]
=\frac{1}{\mathcal N}
\exp\left[-i\frac{\lambda}{4!}\int d^4x\,
\left(\frac1i\frac{\delta}{\delta J(x)}\right)^4\right]Z_0[J].
$$

Expanding the exponential in powers of $\lambda$ produces the perturbative expansion. The Gaussian $Z_0[J]$ supplies propagators, and the interaction exponential supplies vertices.

This is where Feynman diagrams first become an efficient notation rather than a mysterious new ontology. A diagram records which source derivatives hit which factors in the Gaussian exponential.

## Vacuum bubbles and normalization

Without normalization, the source-free path integral contains vacuum-to-vacuum diagrams. These diagrams have no external legs. They multiply every correlation function by the same vacuum factor.

The normalized definition

$$
Z[J]
=\frac{\int\mathcal D\phi\,e^{iS+i\int J\phi}}
{\int\mathcal D\phi\,e^{iS}}
$$

sets

$$
Z[0]=1.
$$

This cancels the vacuum bubbles that are disconnected from the source insertions.

A useful slogan:

```txt
Z[J] contains all source-attached diagrams after vacuum normalization.
W[J] contains only connected source-attached diagrams.
```

The two statements are related, but not identical. Normalization removes vacuum bubbles. Taking the logarithm removes disconnected products of source-attached pieces.


## Functional identities from changes of variables

The same source functional also knows the quantum equations of motion. Formally, make an infinitesimal change of integration variable,

$$
\phi(x)\to\phi(x)+\delta\phi(x),
$$

and assume for the moment that the measure is invariant. Then

$$
0=\int\mathcal D\phi\,\frac{\delta}{\delta\phi(x)}
\exp\left(iS[\phi]+i\int J\phi\right),
$$

so

$$
\left\langle\frac{\delta S}{\delta\phi(x)}+J(x)\right\rangle_J=0.
$$

Equivalently, as a differential equation for the generating functional,

$$
\boxed{
\left[
\frac{\delta S}{\delta\phi(x)}\bigg|_{\phi\to(1/i)\delta/\delta J}
+J(x)
\right]Z[J]=0.
}
$$

These are the **Schwinger–Dyson equations**. They say that the classical equation of motion survives inside quantum correlation functions, but with contact terms when the equation-of-motion insertion collides with other operator insertions.

For the free scalar field,

$$
\frac{\delta S_0}{\delta\phi(x)}=-(\Box+m^2)\phi(x).
$$

The source equation becomes

$$
\left[-(\Box_x+m^2)\frac1i\frac{\delta}{\delta J(x)}+J(x)\right]Z_0[J]=0.
$$

Differentiating once with respect to $J(y)$ and setting $J=0$ gives

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y),
$$

the Green-function equation for the Feynman propagator in qft.org conventions.

If the change of variables is a symmetry transformation, the same reasoning gives Ward identities. The source term is no longer invariant,

$$
\delta\left(\int J_a\phi_a\right)=\int d^4x\,J_a(x)\delta\phi_a(x),
$$

so differentiating the resulting source identity relates current insertions to the transformations of the fields. If the measure is not invariant, an extra Jacobian appears. That is the path-integral doorway to anomalies.

## Classical field and Γ preview

The first derivative of $W[J]$ defines the source-dependent expectation value

$$
\boxed{
\varphi_J(x)=\frac{\delta W[J]}{\delta J(x)}=\langle\phi(x)\rangle_J.
}
$$

This object is often called the classical field, not because it is classical in the sense of ignoring quantum mechanics, but because it is an ordinary c-number field: the expectation value induced by the source.

The next step, used heavily in renormalization and symmetry breaking, is the Legendre transform

$$
\boxed{
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x),
}
$$

where $J$ is regarded as a functional of $\varphi$ through

$$
\varphi(x)=\frac{\delta W}{\delta J(x)}.
$$

Varying gives

$$
\delta\Gamma
=\delta W-\int d^4x\,\delta J\,\varphi-
\int d^4x\,J\,\delta\varphi.
$$

Since

$$
\delta W=\int d^4x\,\varphi(x)\delta J(x),
$$

we get

$$
\boxed{
\frac{\delta\Gamma[\varphi]}{\delta\varphi(x)}=-J(x).
}
$$

At $J=0$, the physical vacuum expectation value satisfies

$$
\left.\frac{\delta\Gamma}{\delta\varphi(x)}\right|_{\varphi=\langle\phi\rangle}=0.
$$

This is the quantum-corrected field equation. The full effective-action story belongs later, but the source calculus has already built the machine.

## Operator and path-integral dictionary

| Operator statement | Source-functional statement |
|---|---|
| insert $\phi(x)$ | differentiate by $J(x)$ |
| full time-ordered correlator | derivative of $Z[J]$ |
| connected correlator | derivative of $W[J]$ |
| vacuum bubble cancellation | normalization $Z[0]=1$ |
| response to external perturbation | $\varphi_J=\delta W/\delta J$ |
| quantum field equation | $\delta\Gamma/\delta\varphi=-J$ |

The dictionary is powerful because it packages infinitely many correlation functions into a few functional identities.

## Common pitfalls

### Treating the source as a dynamical field

The source $J$ is usually not integrated over. It is a probe. If a field is dynamical, it belongs in the action and the measure, not merely in the source term.

### Losing the factors of i

In Lorentzian signature, $Z=e^{iW}$ and source insertions produce factors of $i$. When in doubt, expand $iW[J]$, not $W[J]$ alone.

### Confusing full and connected correlators

Derivatives of $Z$ give full correlators. Derivatives of $W$ give connected correlators. Free theories have vanishing connected correlators above two points, but their full higher-point correlators are not zero.

### Forgetting normalization

Unnormalized functionals contain vacuum bubbles. Normalized functionals set $Z[0]=1$ and remove source-independent vacuum factors.

### Assuming the Legendre transform is always harmless

The transform from $W$ to $\Gamma$ assumes enough convexity or invertibility to solve $\varphi=\delta W/\delta J$ for $J$. In perturbation theory this is usually done formally; nonperturbatively it can require care.

### Ignoring composite-operator renormalization

A source coupled to $\phi$ is the simplest case. A source coupled to $\phi^2$, $T_{\mu\nu}$, or a current may require additional counterterms and operator mixing.

## Relation to other topics

- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) explains why the logarithm isolates connected pieces.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) derives the free scalar $Z_0[J]$.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) rewrites the same source calculus with $e^{-S_E}$ rather than $e^{iS}$.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) will turn the Gaussian source derivatives into systematic contractions.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) will develop $\Gamma[\varphi]$ as the generator of one-particle-irreducible diagrams.
- Ward identities will be generated by changing variables in source-dependent path integrals.

## Research status

The source-functional formalism is textbook-standard perturbative QFT. The formal manipulations are reliable inside a regulated theory and underlie the modern treatment of Green functions, effective actions, Ward identities, and renormalization. Nonperturbatively, the existence and differentiability of $Z[J]$, the definition of the measure, and the Legendre transform can become serious mathematical questions.

## Exercises

### Exercise 1: One field insertion

Starting from

$$
Z[J]=\frac{1}{\mathcal N}\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int J\phi\right),
$$

show that

$$
\left.\frac{1}{i}\frac{\delta Z[J]}{\delta J(x)}\right|_{J=0}
=\langle0|\phi(x)|0\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the source exponential:

$$
\frac{\delta}{\delta J(x)}e^{i\int J\phi}
=i\phi(x)e^{i\int J\phi}.
$$

Therefore

$$
\frac{\delta Z[J]}{\delta J(x)}
=\frac{i}{\mathcal N}\int\mathcal D\phi\,\phi(x)
 e^{iS+i\int J\phi}.
$$

Set $J=0$ and use $\mathcal N=\int\mathcal D\phi\,e^{iS}$:

$$
\left.\frac{1}{i}\frac{\delta Z[J]}{\delta J(x)}\right|_{J=0}
=\frac{\int\mathcal D\phi\,\phi(x)e^{iS}}
{\int\mathcal D\phi\,e^{iS}}
=\langle0|\phi(x)|0\rangle.
$$

</details>

### Exercise 2: Connected two-point function

Using $Z[J]=e^{iW[J]}$, show that

$$
G_2^{\mathrm c}(x,y)
=G_2(x,y)-G_1(x)G_1(y)
=-i\left.\frac{\delta^2W[J]}{\delta J(x)\delta J(y)}\right|_{J=0}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate $Z=e^{iW}$ once:

$$
\frac{\delta Z}{\delta J(x)}
=i\frac{\delta W}{\delta J(x)}Z.
$$

Differentiate again:

$$
\frac{\delta^2 Z}{\delta J(x)\delta J(y)}
=\left[i\frac{\delta^2W}{\delta J(x)\delta J(y)}
-\frac{\delta W}{\delta J(x)}\frac{\delta W}{\delta J(y)}\right]Z.
$$

At $J=0$, $Z[0]=1$ and $G_1=\delta W/\delta J$. Since

$$
G_2=\frac{1}{i^2}\frac{\delta^2Z}{\delta J(x)\delta J(y)},
$$

we get

$$
G_2
=-i\frac{\delta^2W}{\delta J(x)\delta J(y)}
+G_1(x)G_1(y).
$$

Thus

$$
G_2^{\mathrm c}=G_2-G_1G_1
=-i\frac{\delta^2W}{\delta J(x)\delta J(y)}.
$$

</details>

### Exercise 3: Free connected four-point function

For the free scalar field, use

$$
W_0[J]=\frac{i}{2}\int J D_F J
$$

to show that the connected four-point function vanishes.

<details>
<summary><strong>Solution</strong></summary>

The free $W_0[J]$ is quadratic in $J$. Therefore any fourth functional derivative is zero:

$$
\frac{\delta^4W_0[J]}{\delta J(x_1)\delta J(x_2)\delta J(x_3)\delta J(x_4)}=0.
$$

Since connected four-point functions are generated by derivatives of $W$, we have

$$
G_{4,0}^{\mathrm c}(x_1,x_2,x_3,x_4)=0.
$$

</details>

### Exercise 4: Free full four-point function

Use

$$
Z_0[J]=\exp\left[-\frac12\int J D_F J\right]
$$

to derive the free full four-point function.

<details>
<summary><strong>Solution</strong></summary>

Since $Z_0[J]$ is the exponential of a quadratic functional, four derivatives can pair the four sources in three ways. Evaluating at $J=0$ leaves only terms in which every derivative has hit the quadratic exponent exactly once. Therefore

$$
G_{4,0}(x_1,x_2,x_3,x_4)
=D_F(x_1-x_2)D_F(x_3-x_4)
+D_F(x_1-x_3)D_F(x_2-x_4)
+D_F(x_1-x_4)D_F(x_2-x_3).
$$

This is Wick's theorem for four free scalar fields.

</details>

### Exercise 5: First-order φ⁴ expansion

For

$$
S_{\mathrm{int}}[\phi]
=-\frac{\lambda}{4!}\int d^4x\,\phi^4(x),
$$

write $Z[J]$ to first order in $\lambda$ in terms of derivatives acting on $Z_0[J]$.

<details>
<summary><strong>Solution</strong></summary>

Replace

$$
\phi(x)\to \frac1i\frac{\delta}{\delta J(x)}.
$$

Then

$$
Z[J]
=\frac{1}{\mathcal N}
\left[1-i\frac{\lambda}{4!}\int d^4x
\left(\frac1i\frac{\delta}{\delta J(x)}\right)^4
+O(\lambda^2)\right]Z_0[J].
$$

The normalization $\mathcal N$ is chosen so that $Z[0]=1$.

</details>

### Exercise 6: Legendre-transform identity

Let

$$
\varphi(x)=\frac{\delta W[J]}{\delta J(x)},
\qquad
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x).
$$

Show that

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Vary $\Gamma$:

$$
\delta\Gamma
=\delta W-
\int d^4x\,\delta J(x)\varphi(x)-
\int d^4x\,J(x)\delta\varphi(x).
$$

But

$$
\delta W=\int d^4x\,\frac{\delta W}{\delta J(x)}\delta J(x)
=\int d^4x\,\varphi(x)\delta J(x).
$$

The first two terms cancel, so

$$
\delta\Gamma=-\int d^4x\,J(x)\delta\varphi(x).
$$

Therefore

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

</details>

## Sources and further reading

### Primary references

- R. P. Feynman, “Space-Time Approach to Non-Relativistic Quantum Mechanics,” *Reviews of Modern Physics* **20** (1948), for the path-integral formulation.
- E. S. Fradkin, “Application of Functional Methods in Quantum Field Theory and Quantum Statistics,” *Nuclear Physics* **49** (1963), for early systematic functional methods.
- J. Schwinger, “On the Green's Functions of Quantized Fields. I,” *Proceedings of the National Academy of Sciences* **37** (1951), for the source/Green-function viewpoint.

### Standard textbook treatments

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 13, 28, and 32, for Green functions, functional integrals, and the $Z[J]$, $W[J]$, $\Gamma[\varphi]$ hierarchy.
- M. Srednicki, *Quantum Field Theory*, §§8–9 and §21, for scalar path integrals, interaction expansions, and connected/1PI generating functionals.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§9.1–9.4, for path integrals from the canonical formalism; Vol. II, §16.1, for the quantum effective action.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9.1–9.2 and §11.5, for generating functionals and effective actions.
- A. Zee, *Quantum Field Theory in a Nutshell*, appendix A, for the Gaussian identity behind the source functional.

### For a first pass

- Srednicki, §§8–9.
- Peskin and Schroeder, §§9.1–9.2.
- Zee, appendix A.

### For mathematical precision

- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for Euclidean functional integrals and constructive QFT.
- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” for the Euclidean reconstruction framework.
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, for rigorous constructive examples.

## Version history

- **2026-05-23:** Initial qft.org page on external sources, $Z[J]$, $W[J]$, functional differentiation, connected correlators, interaction expansions, vacuum-bubble cancellation, and the first effective-action preview.
