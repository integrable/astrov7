---
title: "Interaction Picture"
description: "The split of a QFT Hamiltonian into a solvable free part and an interacting part, interaction-picture fields and states, the interaction Hamiltonian, and the setup for perturbation theory."
sidebar:
  label: "Interaction Picture"
  order: 1
---

## Summary

The interaction picture is the operator-language bridge between free fields and interacting dynamics. One writes the Hamiltonian as

$$
H=H_0+H_{\rm int},
$$

lets operators evolve with the solvable free Hamiltonian $H_0$, and lets states evolve with the interaction Hamiltonian transformed into the free theory:

$$
\boxed{
\mathcal O_I(t)=e^{iH_0(t-t_0)}\mathcal O_S e^{-iH_0(t-t_0)},
\qquad
H_I(t)=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}.
}
$$

The interaction-picture evolution operator obeys

$$
\boxed{
i\frac{\partial}{\partial t}U_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
}
$$

This is the starting point for Dyson's series, Wick's theorem, and Feynman diagrams. The free theory supplies propagators and external particle states; the interaction Hamiltonian supplies vertices. Coleman presents this route explicitly before deriving Dyson's formula, and Weinberg uses the same interaction-picture framework to derive perturbative Feynman rules while keeping Lorentz covariance and cluster decomposition visible (Coleman 2019, ch. 7; Weinberg 1995, Vol. I, §§3.5 and 6.1).

## Prerequisites

You should know [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Normal Ordering](/foundations/canonical-quantization/normal-ordering/), [Free Field Summary](/foundations/free-fields/free-field-summary/), [States, Operators, and the Vacuum](/foundations/correlators-and-propagators/states-operators-vacuum/), and [Time Ordering](/foundations/correlators-and-propagators/time-ordering/).

## Core idea

The interaction picture separates two jobs that are mixed together in the full Heisenberg picture:

```txt
free propagation:        handled exactly by H₀;
interaction events:      handled perturbatively by H_int.
```

<figure class="doc-figure" style="--figure-width: 48rem;">

![The interaction picture splits free evolution from interaction evolution](/figures/foundations/interaction-picture-split.svg)

<figcaption>

In the interaction picture, $H_0$ evolves fields and creates the free propagators, while $H_{\rm int}$ evolves states through $U_I$ and creates perturbative vertices. Combining the two gives time-ordered correlators and, after the scattering formalism is added, $S$-matrix amplitudes.

</figcaption>
</figure>

This is not just convenient notation. It is why the perturbative expansion is organized around free-field correlators. Free fields have known commutators, known mode expansions, and known Wick contractions. The interacting theory is then built as a controlled formal expansion around that solvable core.

:::note[Assumptions]
This page works in ordinary perturbative QFT with a chosen free Hamiltonian $H_0$, a stable free vacuum used as the starting point, and an interaction switched on perturbatively. In rigorous infinite-volume QFT, the relation between free and interacting Hilbert spaces is subtle; Haag's theorem warns that the interaction picture is not a literal globally valid equivalence of free and interacting fields. Perturbative QFT handles this by using regulators, renormalization, and asymptotic in/out states.
:::

## Three pictures

For a time-independent Hamiltonian, the Schrödinger and Heisenberg pictures are related by moving time evolution between states and operators.

In the Schrödinger picture,

$$
i\frac{d}{dt}|\psi(t)\rangle_S=H|\psi(t)\rangle_S,
\qquad
\mathcal O_S\text{ is time-independent}
$$

unless the operator has explicit time dependence.

In the Heisenberg picture,

$$
|\psi\rangle_H=|\psi(t_0)\rangle_S,
\qquad
\mathcal O_H(t)=e^{iH(t-t_0)}\mathcal O_S e^{-iH(t-t_0)}.
$$

The interaction picture sits between them. Split

$$
H=H_0+H_{\rm int}.
$$

Then define

$$
\boxed{
|\psi(t)\rangle_I=e^{iH_0(t-t_0)}|\psi(t)\rangle_S,
}
$$

and

$$
\boxed{
\mathcal O_I(t)=e^{iH_0(t-t_0)}\mathcal O_S e^{-iH_0(t-t_0)}.
}
$$

Thus interaction-picture operators evolve as though the theory were free:

$$
i\frac{d}{dt}\mathcal O_I(t)=[\mathcal O_I(t),H_0]
$$

for operators with no explicit time dependence. States carry the remaining interacting evolution.

## Interaction-picture Hamiltonian

Differentiate the interaction-picture state:

$$
|\psi(t)\rangle_I=e^{iH_0(t-t_0)}|\psi(t)\rangle_S.
$$

Using

$$
i\frac{d}{dt}|\psi(t)\rangle_S=(H_0+H_{\rm int})|\psi(t)\rangle_S,
$$

we find

$$
\begin{aligned}
i\frac{d}{dt}|\psi(t)\rangle_I
&= -H_0e^{iH_0(t-t_0)}|\psi(t)\rangle_S
+e^{iH_0(t-t_0)}H|\psi(t)\rangle_S \\
&=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}|\psi(t)\rangle_I.
\end{aligned}
$$

Therefore

$$
\boxed{
i\frac{d}{dt}|\psi(t)\rangle_I=H_I(t)|\psi(t)\rangle_I,
\qquad
H_I(t)=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}.
}
$$

This is the key formula. The interaction Hamiltonian becomes explicitly time-dependent because it is written in terms of free fields.

## Interaction-picture evolution operator

Define $U_I(t,t')$ by

$$
|\psi(t)\rangle_I=U_I(t,t')|\psi(t')\rangle_I.
$$

Then

$$
\boxed{
i\frac{\partial}{\partial t}U_I(t,t')=H_I(t)U_I(t,t'),
\qquad
U_I(t',t')=1.
}
$$

It also obeys the composition law

$$
\boxed{
U_I(t_2,t_1)U_I(t_1,t_0)=U_I(t_2,t_0)
}
$$

and, if $H_I(t)$ is Hermitian,

$$
\boxed{
U_I(t,t')^{-1}=U_I(t',t)=U_I(t,t')^\dagger.
}
$$

For time-independent $H$ and $H_0$,

$$
\boxed{
U_I(t,t')=e^{iH_0(t-t_0)}e^{-iH(t-t')}e^{-iH_0(t'-t_0)}
}
$$

up to the arbitrary reference time $t_0$. With $t_0=0$, this is the form used in many textbook derivations, including Coleman's derivation of $U_I$ and Dyson's formula (Coleman 2019, ch. 7).

## Field-theory split

For a scalar theory, the Lagrangian is often written as

$$
\mathcal L
=\mathcal L_0+\mathcal L_{\rm int},
$$

with

$$
\mathcal L_0
=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2.
$$

A common example is

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4.
$$

For non-derivative scalar interactions, the interaction Hamiltonian density is

$$
\boxed{
\mathcal H_I=-\mathcal L_{\rm int}.
}
$$

So for the quartic scalar example,

$$
\mathcal H_I=\frac{\lambda}{4!}\phi_I^4.
$$

The corresponding interaction Hamiltonian is

$$
\boxed{
H_I(t)=\int d^3x\,\mathcal H_I(t,\mathbf x)
=\int d^3x\,\frac{\lambda}{4!}\phi_I(t,\mathbf x)^4.
}
$$

Here $\phi_I$ is the free interaction-picture scalar field. Its mode expansion, canonical commutators, and propagator are those of the free Klein–Gordon field.

:::caution[Derivative interactions need the Hamiltonian]
The shortcut $\mathcal H_I=-\mathcal L_{\rm int}$ is not automatic. It is true for many simple non-derivative interactions, but derivative interactions, constrained systems, and gauge theories require the Hamiltonian analysis. Weinberg emphasizes this point in the canonical formalism: the Lagrangian is often the cleanest way to see symmetries, but the interaction-picture Hamiltonian is what appears in Dyson evolution (Weinberg 1995, Vol. I, §§7.1–7.6).
:::

## Free fields and vertices

The practical split is:

| Piece | Evolves | Provides |
|---|---|---|
| $H_0$ | interaction-picture operators | free equations, mode expansions, propagators |
| $H_I(t)$ | interaction-picture states | perturbative insertions, vertices, scattering |

For the quartic scalar theory,

$$
H_I(t)=\frac{\lambda}{4!}\int d^3x\,\phi_I(t,\mathbf x)^4.
$$

Expanding $U_I$ in powers of $H_I$ will insert products of free fields into vacuum expectation values. Wick's theorem then rewrites those products as sums of contractions. This is the operator route from a Lagrangian term to a Feynman vertex.

In the path-integral language, the same split appears as

$$
e^{iS}=e^{iS_0}e^{iS_{\rm int}},
$$

so interactions are expanded around a Gaussian free integral. The interaction picture is the operator analogue of that Gaussian expansion.

## Scattering interpretation

For scattering, one is interested in states that behave as free multiparticle states at very early and very late times. Formally,

$$
\boxed{
S=U_I(+\infty,-\infty)
}
$$

with an implicit adiabatic switching or $i\epsilon$ prescription. The free Hamiltonian $H_0$ defines the asymptotic particles; the interaction Hamiltonian evolves them through the collision region.

This is why the interaction picture is so naturally paired with Fock space. The free Fock basis is not the whole physical story, but it is the language in which perturbative scattering is organized.

## Vacuum and source caveats

The free vacuum $|0\rangle$ and the interacting vacuum $|\Omega\rangle$ need not be the same. For correlation functions, the perturbative operator formula has the schematic form

$$
\boxed{
\langle\Omega|T\{\mathcal O_H(x_1)\cdots\mathcal O_H(x_n)\}|\Omega\rangle
=
\frac{
\langle0|T\{\mathcal O_I(x_1)\cdots\mathcal O_I(x_n)
\exp[-i\int dt\,H_I(t)]\}|0\rangle
}{
\langle0|T\{\exp[-i\int dt\,H_I(t)]\}|0\rangle
}.
}
$$

The denominator removes vacuum bubbles. In the path integral, this is the normalization $Z[0]=1$. In diagram language, it is why connected correlators and connected vacuum diagrams receive special treatment.

Coleman's source-functional derivation uses Dyson's formula in precisely this spirit: an external source can be treated as an interaction, and expanding the time-ordered exponential generates vacuum expectation values of time-ordered Heisenberg fields (Coleman 2019, ch. 13).

## Operator, path-integral, and structural views

The same idea has three useful translations.

| Viewpoint | Statement |
|---|---|
| Operator | Split $H=H_0+H_{\rm int}$ and evolve with $U_I$. |
| Path integral | Split $S=S_0+S_{\rm int}$ and expand $e^{iS_{\rm int}}$ around the Gaussian. |
| Structural | The free theory fixes asymptotic particles and propagators; interactions deform correlators and scattering amplitudes. |

A good perturbative calculation keeps these views aligned. If a sign or normalization differs between them, the mismatch usually comes from a convention for $H_I$, $\mathcal L_{\rm int}$, Fourier transforms, or source insertions.

## Common pitfalls

### Confusing free and interacting fields

Interaction-picture fields are free fields. They satisfy free equations of motion. The interaction is not hidden inside their time dependence; it is in $U_I$.

### Forgetting the sign between Hamiltonian and Lagrangian interactions

For a simple scalar potential, $\mathcal H_I=-\mathcal L_{\rm int}$. Thus

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4
\quad\Rightarrow\quad
H_I=\int d^3x\,\frac{\lambda}{4!}\phi_I^4.
$$

This sign is one source of the familiar vertex factor $-i\lambda$.

### Treating the interaction picture as rigorous without qualification

Perturbation theory uses the interaction picture as a regulated formal expansion. In infinite volume, the exact interacting theory is not generally unitarily equivalent to the free theory.

### Dropping vacuum normalization

For vacuum correlators, disconnected vacuum bubbles cancel only after dividing by the vacuum-to-vacuum factor. Forgetting this denominator clutters correlators with diagrams that do not touch the operator insertions.

### Assuming the split is unique

The split $H=H_0+H_{\rm int}$ is a choice. Counterterms, external sources, mass shifts, background fields, and effective interactions can be assigned to either side in different calculational schemes, as long as the full theory is treated consistently.

## Relation to other topics

- [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/) explains why the free Hamiltonian is exactly solvable.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) supplies the free scalar mode expansion used in interaction-picture perturbation theory.
- [Time Ordering](/foundations/correlators-and-propagators/time-ordering/) defines the operation that appears in Dyson evolution.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) is the contraction of two free interaction-picture scalar fields.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) gives the path-integral version of the same source-insertion logic.
- [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) solves the interaction-picture evolution equation.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) converts the resulting time-ordered free-field products into contractions.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) turns the contraction expansion into diagrammatic rules.

## Exercises

### Exercise 1: Derive the interaction Hamiltonian

Starting from

$$
|\psi(t)\rangle_I=e^{iH_0(t-t_0)}|\psi(t)\rangle_S,
$$

and

$$
i\frac{d}{dt}|\psi(t)\rangle_S=(H_0+H_{\rm int})|\psi(t)\rangle_S,
$$

show that

$$
i\frac{d}{dt}|\psi(t)\rangle_I=H_I(t)|\psi(t)\rangle_I,
$$

where

$$
H_I(t)=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate the definition:

$$
\frac{d}{dt}|\psi(t)\rangle_I
=iH_0e^{iH_0(t-t_0)}|\psi(t)\rangle_S
+e^{iH_0(t-t_0)}\frac{d}{dt}|\psi(t)\rangle_S.
$$

Multiply by $i$:

$$
i\frac{d}{dt}|\psi(t)\rangle_I
=-H_0e^{iH_0(t-t_0)}|\psi(t)\rangle_S
+e^{iH_0(t-t_0)}H|\psi(t)\rangle_S.
$$

Since $H=H_0+H_{\rm int}$ and $H_0$ commutes with $e^{iH_0(t-t_0)}$, the $H_0$ terms cancel. Thus

$$
i\frac{d}{dt}|\psi(t)\rangle_I
=e^{iH_0(t-t_0)}H_{\rm int}|\psi(t)\rangle_S.
$$

Now insert

$$
|\psi(t)\rangle_S=e^{-iH_0(t-t_0)}|\psi(t)\rangle_I.
$$

This gives

$$
i\frac{d}{dt}|\psi(t)\rangle_I
=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}|\psi(t)\rangle_I.
$$

Therefore

$$
H_I(t)=e^{iH_0(t-t_0)}H_{\rm int}e^{-iH_0(t-t_0)}.
$$

</details>

### Exercise 2: Free evolution of an operator

Let $\mathcal O_I(t)=e^{iH_0(t-t_0)}\mathcal O_S e^{-iH_0(t-t_0)}$, with no explicit time dependence in $\mathcal O_S$. Show that

$$
i\frac{d}{dt}\mathcal O_I(t)=[\mathcal O_I(t),H_0].
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{d}{dt}\mathcal O_I(t)
=iH_0\mathcal O_I(t)-i\mathcal O_I(t)H_0.
$$

Multiplying by $i$ gives

$$
i\frac{d}{dt}\mathcal O_I(t)
=-H_0\mathcal O_I(t)+\mathcal O_I(t)H_0
=[\mathcal O_I(t),H_0].
$$

The sign follows from the convention $\mathcal O_I=e^{iH_0t}\mathcal O_S e^{-iH_0t}$.

</details>

### Exercise 3: Quartic scalar interaction

For

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

write $H_I(t)$ in the interaction picture, assuming the interaction contains no time derivatives.

<details>
<summary><strong>Solution</strong></summary>

The interaction Lagrangian density is

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4.
$$

For this non-derivative interaction,

$$
\mathcal H_I=-\mathcal L_{\rm int}=\frac{\lambda}{4!}\phi^4.
$$

In the interaction picture the field is the free scalar field $\phi_I$, so

$$
H_I(t)=\int d^3x\,\mathcal H_I(t,\mathbf x)
=\frac{\lambda}{4!}\int d^3x\,\phi_I(t,\mathbf x)^4.
$$

</details>

### Exercise 4: Unitarity of interaction-picture evolution

Assume $H_I(t)$ is Hermitian and $U_I$ satisfies

$$
i\partial_tU_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
$$

Show that $U_I(t,t_0)^\dagger U_I(t,t_0)=1$.

<details>
<summary><strong>Solution</strong></summary>

Let

$$
F(t)=U_I(t,t_0)^\dagger U_I(t,t_0).
$$

The evolution equation gives

$$
\partial_tU_I(t,t_0)=-iH_I(t)U_I(t,t_0).
$$

Taking the adjoint,

$$
\partial_tU_I(t,t_0)^\dagger
=iU_I(t,t_0)^\dagger H_I(t),
$$

because $H_I(t)^\dagger=H_I(t)$. Hence

$$
\begin{aligned}
\partial_tF(t)
&=iU_I^\dagger H_IU_I+U_I^\dagger(-iH_IU_I)\\
&=0.
\end{aligned}
$$

Since $F(t_0)=1$, we have $F(t)=1$ for all $t$.

</details>

### Exercise 5: A source as an interaction

Let a free scalar theory be perturbed by a classical source,

$$
H_I(t)=-\int d^3x\,J(t,\mathbf x)\phi_I(t,\mathbf x).
$$

Write the first-order term in $U_I(+\infty,-\infty)$.

<details>
<summary><strong>Solution</strong></summary>

The first-order term in the interaction-picture evolution is

$$
U_I^{(1)}(+\infty,-\infty)
=-i\int_{-\infty}^{+\infty}dt\,H_I(t).
$$

Substituting the source interaction,

$$
U_I^{(1)}
=-i\int dt\left[-\int d^3x\,J(t,\mathbf x)\phi_I(t,\mathbf x)\right].
$$

Therefore

$$
U_I^{(1)}
=i\int d^4x\,J(x)\phi_I(x).
$$

This is the first term in the expansion of the source factor $\exp[i\int J\phi]$ in the scalar path integral.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 7, 8, and 13. Coleman's treatment is especially useful for the operator derivation of the interaction picture, Dyson's formula, and the source-functional interpretation of time-ordered Green functions.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §§3.5, 6.1, 6.4, 7.1–7.6, and 9.2. Weinberg gives the general interaction-picture perturbative framework and explains how Feynman rules, external sources, canonical variables, and path integrals fit together.
- Mark Srednicki, *Quantum Field Theory*, §§9–10 and §19. Srednicki gives a compact route from the interaction expansion to Feynman rules and perturbation theory.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9. Zee gives a helpful physical account of how interactions disturb the free vacuum and lead to diagrammatic perturbation theory.
