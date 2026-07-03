---
title: "Dyson Series"
description: "The formal time-ordered exponential solution of interaction-picture evolution, its ordered-integral expansion, relation to perturbative Green functions, unitarity, and the first bridge to Wick expansion."
sidebar:
  label: "Dyson Series"
  order: 2
---

## Summary

The Dyson series solves the interaction-picture evolution equation

$$
i\frac{\partial}{\partial t}U_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
$$

Because $H_I(t_1)$ and $H_I(t_2)$ need not commute, the solution is not an ordinary exponential. It is a time-ordered exponential:

$$
\boxed{
U_I(t,t_0)
=T\exp\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right].
}
$$

Expanded in powers of the interaction,

$$
\boxed{
U_I(t,t_0)
=\sum_{n=0}^{\infty}\frac{(-i)^n}{n!}
\int_{t_0}^{t}dt_1\cdots dt_n\,
T\{H_I(t_1)\cdots H_I(t_n)\}.
}
$$

This formula is the algebraic engine of perturbative QFT. Insert a local interaction Hamiltonian, expand the exponential, and then use Wick's theorem to evaluate free-field time-ordered products. Coleman derives this formula immediately after introducing the interaction picture, while Weinberg uses Dyson's perturbative expansion as the basis for the covariant Feynman rules (Coleman 2019, ch. 7; Weinberg 1995, Vol. I, §§3.5 and 6.1).

## Prerequisites

You should know [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/), [Time Ordering](/foundations/correlators-and-propagators/time-ordering/), [Normal Ordering](/foundations/canonical-quantization/normal-ordering/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), and [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/).

## Core idea

The differential equation for $U_I$ is first order, so it can be written as an integral equation:

$$
\boxed{
U_I(t,t_0)
=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
}
$$

Now substitute the same equation for $U_I(t_1,t_0)$, and repeat. This iteration produces nested time integrals:

$$
\begin{aligned}
U_I(t,t_0)
&=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)\\
&\quad+(-i)^2\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,
H_I(t_1)H_I(t_2)+\cdots.
\end{aligned}
$$

The nesting forces later times to appear on the left. Time ordering is precisely the notation that packages all these nested regions into a symmetric expression.

<figure class="doc-figure" style="--figure-width: 42rem;">

![At second order, time ordering turns an ordered triangle into a symmetric square integral](/figures/foundations/dyson-time-ordering-simplex.svg)

<figcaption>

At second order, the ordered integration region $t_1>t_2$ is one triangle inside the square $[t_0,t]^2$. The time-ordering symbol supplies the correct operator order in both triangles, allowing the ordered integral to be written as $\frac{1}{2!}\int dt_1dt_2\,T\{H_I(t_1)H_I(t_2)\}$.

</figcaption>
</figure>

This is the small miracle behind the compact notation. The factor $1/n!$ compensates for integrating over all $n!$ possible orderings of the times.

## Integral equation

Start from

$$
i\partial_tU_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
$$

Equivalently,

$$
\partial_tU_I(t,t_0)=-iH_I(t)U_I(t,t_0).
$$

Integrating from $t_0$ to $t$ gives

$$
U_I(t,t_0)-1
=-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0),
$$

so

$$
\boxed{
U_I(t,t_0)
=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
}
$$

This integral equation is exact. The Dyson series is obtained by iterating it.

## Ordered expansion

The first substitution gives

$$
\begin{aligned}
U_I(t,t_0)
&=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)\\
&\quad+(-i)^2\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,
H_I(t_1)H_I(t_2)U_I(t_2,t_0).
\end{aligned}
$$

Repeating this process yields

$$
\boxed{
U_I(t,t_0)
=1+\sum_{n=1}^{\infty}(-i)^n
\int_{t_0}^{t}dt_1
\int_{t_0}^{t_1}dt_2
\cdots
\int_{t_0}^{t_{n-1}}dt_n\,
H_I(t_1)H_I(t_2)\cdots H_I(t_n).
}
$$

The integration limits enforce

$$
t_1>t_2>\cdots>t_n.
$$

That is why the operators appear in the written order $H_I(t_1)H_I(t_2)\cdots H_I(t_n)$.

## Time-ordered form

The same ordered expansion can be written over the full $n$-dimensional cube:

$$
\boxed{
U_I(t,t_0)
=\sum_{n=0}^{\infty}
\frac{(-i)^n}{n!}
\int_{t_0}^{t}dt_1\cdots dt_n\,
T\{H_I(t_1)\cdots H_I(t_n)\}.
}
$$

Why does this work? The cube decomposes into $n!$ ordered regions, one for each permutation of the times. On each region, $T$ rearranges the Hamiltonians so that the latest time stands leftmost. If the Hamiltonian is bosonic, as an interaction Hamiltonian must be in an ordinary theory, no extra fermion sign arises from permuting whole $H_I$ factors.

At second order,

$$
\begin{aligned}
&\frac{1}{2!}\int_{t_0}^{t}dt_1dt_2\,
T\{H_I(t_1)H_I(t_2)\}\\
&=\frac12\int_{t_0}^{t}dt_1dt_2\,
\Big[
\theta(t_1-t_2)H_I(t_1)H_I(t_2)
+\theta(t_2-t_1)H_I(t_2)H_I(t_1)
\Big].
\end{aligned}
$$

The two terms are equal after relabeling $t_1\leftrightarrow t_2$. Therefore

$$
\frac{1}{2!}\int dt_1dt_2\,T\{H_I(t_1)H_I(t_2)\}
=\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,H_I(t_1)H_I(t_2).
$$

## Compact notation

The formal notation

$$
T\exp\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right]
$$

means exactly the time-ordered series above. It is not an ordinary exponential unless

$$
[H_I(t_1),H_I(t_2)]=0
\qquad\text{for all }t_1,t_2.
$$

If all $H_I(t)$ commute, then time ordering becomes irrelevant and

$$
U_I(t,t_0)=\exp\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right].
$$

QFT is almost never that simple. Local fields at different times generally do not commute, so time ordering is essential.

## Local QFT form

For a local interaction,

$$
H_I(t)=\int d^3x\,\mathcal H_I(t,\mathbf x).
$$

Then

$$
\int dt\,H_I(t)=\int d^4x\,\mathcal H_I(x).
$$

For simple non-derivative interactions,

$$
\mathcal H_I=-\mathcal L_{\rm int},
$$

so

$$
-i\int dt\,H_I(t)
=-i\int d^4x\,\mathcal H_I(x)
=i\int d^4x\,\mathcal L_{\rm int}(x).
$$

Thus the $S$-matrix is often written as

$$
\boxed{
S
=T\exp\left[-i\int d^4x\,\mathcal H_I(x)\right]
=
T\exp\left[i\int d^4x\,\mathcal L_{\rm int}(x)\right]
}
$$

for such interactions. For example, in $\phi^4$ theory,

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi_I^4,
\qquad
\mathcal H_I=\frac{\lambda}{4!}\phi_I^4,
$$

so

$$
S
=T\exp\left[-i\frac{\lambda}{4!}\int d^4x\,\phi_I(x)^4\right].
$$

The first-order vertex factor is therefore $-i\lambda$ once the four identical fields are contracted with four external or internal scalar lines.

:::caution[Use the Hamiltonian when necessary]
The expression $T\exp[i\int\mathcal L_{\rm int}]$ is a useful shortcut, not the definition. The definition in the interaction picture uses $H_I(t)$. Derivative interactions, constrained variables, gauge fixing, and fermionic first-order actions can all require more care.
:::

## First few terms for scalar theory

For quartic scalar theory,

$$
H_I(t)=\frac{\lambda}{4!}\int d^3x\,\phi_I(t,\mathbf x)^4.
$$

Then

$$
S
=1+S^{(1)}+S^{(2)}+\cdots
$$

with

$$
\boxed{
S^{(1)}
=-i\frac{\lambda}{4!}\int d^4x\,\phi_I(x)^4,
}
$$

and

$$
\boxed{
S^{(2)}
=\frac{(-i)^2}{2!}
\left(\frac{\lambda}{4!}\right)^2
\int d^4x\,d^4y\,
T\{\phi_I(x)^4\phi_I(y)^4\}.
}
$$

This is not yet a Feynman diagram. It becomes one after applying Wick's theorem. Wick's theorem turns the time-ordered product of free fields into a sum over normal-ordered products and contractions, and each contraction is a Feynman propagator.

## Vacuum expectation values

The Dyson series also gives perturbative correlators. Schematically,

$$
\boxed{
\langle\Omega|T\{\mathcal O_H(x_1)\cdots\mathcal O_H(x_n)\}|\Omega\rangle
=
\frac{
\langle0|T\{\mathcal O_I(x_1)\cdots\mathcal O_I(x_n)S\}|0\rangle
}{
\langle0|S|0\rangle
}.
}
$$

Here $|\Omega\rangle$ is the interacting vacuum, $|0\rangle$ is the free vacuum, and

$$
S=T\exp\left[-i\int dt\,H_I(t)\right].
$$

The denominator cancels vacuum bubbles. This is the operator counterpart of the normalized path integral

$$
Z[0]=1.
$$

Coleman's source-functional discussion makes the same point in another language: treating a source as an interaction and expanding Dyson's formula identifies Green functions with vacuum expectation values of time-ordered Heisenberg fields (Coleman 2019, ch. 13).

## Relation to generating functionals

The path-integral expansion

$$
Z[J]=\frac{1}{\mathcal N}\int\mathcal D\phi\,
e^{iS_0[\phi]}e^{iS_{\rm int}[\phi]}e^{i\int J\phi}
$$

is the functional-integral version of the Dyson expansion. The dictionary is:

| Operator language | Path-integral language |
|---|---|
| $U_I$ or $S$ | $e^{iS_{\rm int}}$ |
| free interaction-picture fields | Gaussian free field variables |
| time ordering | Feynman boundary prescription |
| Wick contractions | Gaussian pairings |
| vacuum bubble denominator | normalization by $Z[0]$ |

The two languages are not identical in derivation, but they produce the same perturbative expansion when the same convention and regulator choices are used.

## Unitarity and anti-time ordering

If $H_I(t)$ is Hermitian, then $U_I$ is unitary. The adjoint is written with anti-time ordering:

$$
\boxed{
U_I(t,t_0)^\dagger
=\overline T\exp\left[+i\int_{t_0}^{t}dt'\,H_I(t')\right],
}
$$

where $\overline T$ orders earlier times to the left. This is important in probability conservation and in later derivations of the optical theorem.

At the level of the $S$-matrix,

$$
S^\dagger S=1.
$$

Perturbatively, this equality relates imaginary parts of loop amplitudes to sums over real intermediate states. That is the beginning of unitarity cuts and the optical theorem, which belong to the later scattering section.

## Adiabatic switching and convergence

The formal expression

$$
S=U_I(+\infty,-\infty)
$$

needs a prescription. A common one is to replace the interaction by

$$
H_I(t)\to e^{-\epsilon |t|}H_I(t),
\qquad
\epsilon>0,
$$

and then take $\epsilon\to0^+$ after the calculation. This adiabatic switching is closely related to the $i\epsilon$ prescription in propagators and to the selection of the interacting vacuum.

In practice, perturbative QFT also uses regulators for ultraviolet divergences and infrared prescriptions for long-distance effects. Dyson's series gives the formal expansion; renormalization and scattering theory explain how to extract finite physical quantities from it.

## Common pitfalls

### Using an ordinary exponential

The expression $\exp[-i\int H_I dt]$ is correct only when the Hamiltonians commute at different times. In QFT they generally do not, so the time-ordering symbol is not optional.

### Losing the factorial

The factor $1/n!$ appears only after writing the ordered simplex as a full hypercube with time ordering. In the nested-integral form, there is no $1/n!$.

### Forgetting the sign from the interaction Lagrangian

For non-derivative scalar interactions, $-i\int H_I=i\int\mathcal L_{\rm int}$. A minus sign error here changes the vertex rule.

### Confusing vacuum bubbles with connected physics

Vacuum bubbles appear in $\langle0|S|0\rangle$. They cancel in normalized correlators but contribute to vacuum energy and the generating functional for connected vacuum diagrams.

### Ignoring switching prescriptions

The limits $+\infty$ and $-\infty$ are not innocent. The $i\epsilon$ or adiabatic prescription tells the perturbation series which vacuum and boundary conditions are meant.

## Relation to other topics

- [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/) derives the evolution equation that the Dyson series solves.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) defines the ordering operation used in the compact exponential.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) is the contraction produced by applying Wick's theorem to the Dyson expansion.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) gives the path-integral version of the same expansion.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) is the next operator step: it evaluates the time-ordered free-field products.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) turns the combinatorics of the Dyson-Wick expansion into pictures.
- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) will apply the expansion to $\phi^3$ and $\phi^4$ vertices.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains the cancellation of vacuum bubbles and the exponentiation of connected diagrams.

## Exercises

### Exercise 1: Derive the integral equation

Starting from

$$
i\partial_tU_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1,
$$

derive

$$
U_I(t,t_0)
=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
$$

<details>
<summary><strong>Solution</strong></summary>

Rewrite the differential equation as

$$
\partial_tU_I(t,t_0)=-iH_I(t)U_I(t,t_0).
$$

Integrate both sides from $t_0$ to $t$:

$$
U_I(t,t_0)-U_I(t_0,t_0)
=-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
$$

Since $U_I(t_0,t_0)=1$,

$$
U_I(t,t_0)
=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
$$

</details>

### Exercise 2: Second-order term

Use the integral equation once to show that the second-order contribution is

$$
U_I^{(2)}(t,t_0)
=(-i)^2\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,
H_I(t_1)H_I(t_2).
$$

<details>
<summary><strong>Solution</strong></summary>

The integral equation is

$$
U_I(t,t_0)=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)U_I(t_1,t_0).
$$

To get terms through second order, insert the first-order approximation

$$
U_I(t_1,t_0)
=1-i\int_{t_0}^{t_1}dt_2\,H_I(t_2)+O(H_I^2).
$$

Then

$$
\begin{aligned}
U_I(t,t_0)
&=1-i\int_{t_0}^{t}dt_1\,H_I(t_1)\\
&\quad+(-i)^2\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,
H_I(t_1)H_I(t_2)+O(H_I^3).
\end{aligned}
$$

Thus the second-order term is the ordered double integral.

</details>

### Exercise 3: Ordered triangle versus time-ordered square

Show that

$$
\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,H_I(t_1)H_I(t_2)
=
\frac12\int_{t_0}^{t}dt_1dt_2\,
T\{H_I(t_1)H_I(t_2)\}.
$$

Assume $H_I$ is bosonic.

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
T\{H_I(t_1)H_I(t_2)\}
=\theta(t_1-t_2)H_I(t_1)H_I(t_2)
+\theta(t_2-t_1)H_I(t_2)H_I(t_1).
$$

Therefore

$$
\begin{aligned}
&\frac12\int dt_1dt_2\,T\{H_I(t_1)H_I(t_2)\}\\
&=\frac12\int dt_1dt_2\,\theta(t_1-t_2)H_I(t_1)H_I(t_2)\\
&\quad+\frac12\int dt_1dt_2\,\theta(t_2-t_1)H_I(t_2)H_I(t_1).
\end{aligned}
$$

In the second integral, relabel $t_1\leftrightarrow t_2$. It becomes identical to the first integral. Thus the factor $1/2$ cancels the two equal contributions:

$$
\frac12(\text{first}+\text{second})=\text{first}.
$$

The first integral is exactly

$$
\int_{t_0}^{t}dt_1\int_{t_0}^{t_1}dt_2\,H_I(t_1)H_I(t_2).
$$

</details>

### Exercise 4: Commuting Hamiltonians

Suppose $[H_I(t_1),H_I(t_2)]=0$ for all times. Show that the Dyson series reduces to the ordinary exponential.

<details>
<summary><strong>Solution</strong></summary>

If all $H_I(t)$ commute, time ordering has no effect:

$$
T\{H_I(t_1)\cdots H_I(t_n)\}=H_I(t_1)\cdots H_I(t_n).
$$

The Dyson series becomes

$$
U_I(t,t_0)
=\sum_{n=0}^\infty\frac{(-i)^n}{n!}
\int_{t_0}^{t}dt_1\cdots dt_n\,
H_I(t_1)\cdots H_I(t_n).
$$

Since the factors commute, the multiple integral factorizes:

$$
\int dt_1\cdots dt_n\,H_I(t_1)\cdots H_I(t_n)
=
\left(\int_{t_0}^{t}dt'\,H_I(t')\right)^n.
$$

Thus

$$
U_I(t,t_0)
=\sum_{n=0}^\infty\frac{1}{n!}
\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right]^n
=
\exp\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right].
$$

</details>

### Exercise 5: First scalar vertex factor

For $\mathcal L_{\rm int}=-\lambda\phi^4/4!$, use the first-order Dyson term to explain why the scalar four-point vertex carries a factor $-i\lambda$.

<details>
<summary><strong>Solution</strong></summary>

For this non-derivative interaction,

$$
\mathcal H_I=-\mathcal L_{\rm int}=\frac{\lambda}{4!}\phi_I^4.
$$

The first-order term in $S$ is

$$
S^{(1)}
=-i\int d^4x\,\mathcal H_I(x)
=-i\frac{\lambda}{4!}\int d^4x\,\phi_I(x)^4.
$$

When this term is inserted into a four-point correlator, the four identical fields at the vertex can be contracted with four external fields in $4!$ ways. That combinatoric factor cancels the $1/4!$ in the interaction. The remaining local factor is

$$
-i\lambda.
$$

This is the standard quartic scalar vertex factor in the qft.org conventions.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 7, 8, and 13. Coleman gives the interaction-picture derivation of $U_I$, Dyson's formula, the $S$-matrix setup, and the source-functional use of Dyson expansion.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §§3.5, 6.1, 6.4, and 9.2. Weinberg uses Dyson's series to derive covariant perturbation theory and connects it to off-shell external fields and path integrals.
- Mark Srednicki, *Quantum Field Theory*, §§9–10 and §19. Srednicki's treatment is a concise route from the perturbative expansion to Feynman rules and all-orders perturbation theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9 and Appendix C. Zee gives a physically motivated entry into Feynman diagrams and the perturbative expansion.
