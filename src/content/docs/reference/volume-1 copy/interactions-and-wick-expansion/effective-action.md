---
title: "Effective Action"
description: "The quantum effective action as the Legendre transform of W[J]: classical fields, 1PI vertices, inverse exact propagators, effective potentials, and the bridge from connected diagrams to renormalization."
sidebar:
  label: "Effective Action"
  order: 7
---

## Summary

The effective action is the functional that packages **one-particle-irreducible** data. Starting from the normalized source functional

$$
Z[J]=e^{iW[J]},
$$
we define the source-dependent expectation value

$$
\boxed{
\varphi_J(x)=\frac{\delta W[J]}{\delta J(x)}=\langle\phi(x)\rangle_J.
}
$$

The effective action is the Legendre transform

$$
\boxed{
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x),
\qquad
\frac{\delta\Gamma[\varphi]}{\delta\varphi(x)}=-J(x).
}
$$

At zero source, the physical vacuum expectation value satisfies the quantum equation of motion

$$
\boxed{
\left.\frac{\delta\Gamma}{\delta\varphi(x)}\right|_{\varphi=\langle\phi\rangle}=0.
}
$$

The functional Taylor coefficients of $\Gamma$ are the **1PI vertices**. In perturbation theory, connected diagrams can be reconstructed as tree diagrams built from exact propagators and these 1PI vertices. This is the reason $\Gamma$ is often called the **quantum action**: it plays for quantum-corrected amplitudes the role that the classical action plays at tree level.

This page follows the source-functional conventions fixed in [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/). Coleman introduces $\Gamma[\varphi]$ as the generating functional for 1PI Green functions, with $\Gamma=S$ in the tree approximation, and later uses the same object to define the effective potential. Weinberg's external-field formalism gives the standard modern treatment, while Srednicki's “quantum action” chapter develops the same object from the path-integral viewpoint (Coleman 2019, §§32.1–32.2 and §§44.2–44.3; Weinberg 1996, Vol. II, §16.1; Srednicki 2007, §21).

## Prerequisites

You should know [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/), and [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/).

## Core idea

The hierarchy is:

```txt
Z[J]        generates full correlators;
W[J]        generates connected correlators;
Γ[φ]        generates one-particle-irreducible vertices.
```

<figure class="doc-figure" style="--figure-width: 48rem;">

![Effective action as a Legendre transform from connected correlators to 1PI vertices](/figures/foundations/effective-action-legendre-map.svg)

<figcaption>

The logarithm of $Z[J]$ extracts connected diagrams. The Legendre transform from $W[J]$ to $\Gamma[\varphi]$ extracts 1PI data. Connected diagrams are then reconstructed as tree diagrams whose vertices are 1PI vertices and whose internal lines are exact connected propagators.

</figcaption>
</figure>

The conceptual punchline is simple but easy to underuse:

```txt
The classical action gives tree-level vertices.
The effective action gives quantum-corrected proper vertices.
```

The word “effective” here does **not** mean “low-energy EFT” by itself. It means that $\Gamma$ is the action-like object whose stationary points, quadratic kernel, and higher derivatives include quantum corrections.

:::note[Assumptions]
This page treats the effective action in ordinary perturbative QFT, mainly for scalar fields. Gauge theories require gauge fixing and ghosts, and the effective action can depend on gauge choice away from physical observables. Nonperturbatively, Legendre transforms, convexity, phases, and multiple vacua require more care than the perturbative notation suggests.
:::

## From the connected generator to Γ

Start with

$$
Z[J]=e^{iW[J]}.
$$

The first derivative of $W$ defines the source-dependent classical field

$$
\varphi_J(x)=\frac{\delta W[J]}{\delta J(x)}.
$$

The name “classical field” is potentially misleading. It does not mean that quantum fluctuations have been ignored. It means that $\varphi_J(x)$ is an ordinary c-number function: the expectation value of the quantum field in the presence of the source.

The Legendre transform is

$$
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x),
$$

where after the transform $J$ is regarded as a functional of $\varphi$ through

$$
\varphi(x)=\frac{\delta W}{\delta J(x)}.
$$

Varying gives

$$
\delta\Gamma
=\delta W-
\int d^4x\,\delta J(x)\varphi(x)
-
\int d^4x\,J(x)\delta\varphi(x).
$$

Since

$$
\delta W=\int d^4x\,\varphi(x)\delta J(x),
$$

the first two terms cancel, leaving

$$
\boxed{
\delta\Gamma=-\int d^4x\,J(x)\delta\varphi(x),
\qquad
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
}
$$

At zero source,

$$
J=0,
$$

so the vacuum expectation value is determined by

$$
\boxed{
\frac{\delta\Gamma}{\delta\varphi}=0.
}
$$

This is the quantum-corrected version of the classical field equation $\delta S/\delta\phi=0$.

## Why one-particle irreducible diagrams matter

A connected diagram is **one-particle irreducible**, or 1PI, if it cannot be disconnected by cutting a single internal line. The phrase is historical: the internal line is a particle propagator in perturbation theory, so a diagram reducible by cutting one line is “one-particle reducible.”

For example, in a scalar theory:

```txt
single quartic vertex:
  connected and 1PI;

two cubic vertices joined by one internal line:
  connected but not 1PI;

vacuum bubble disconnected from external insertions:
  not part of a connected source-attached correlator.
```

The importance of 1PI diagrams is that they are the irreducible building blocks of connected diagrams. A connected diagram can contain chains of self-energy insertions, vertices connected by full propagators, and more elaborate tree structures. If you collapse every maximal 1PI subdiagram to a vertex, what remains is a tree.

That statement is the diagrammatic content of the Legendre transform.

## Vertices from Γ

Expand the effective action around a chosen background $v$, often the vacuum expectation value:

$$
\varphi(x)=v+\eta(x).
$$

Then

$$
\Gamma[v+\eta]
=\Gamma[v]
+\sum_{n=1}^{\infty}\frac1{n!}
\int d^4x_1\cdots d^4x_n\,
\Gamma^{(n)}(x_1,\ldots,x_n)\eta(x_1)\cdots\eta(x_n).
$$

The kernels are functional derivatives:

$$
\boxed{
\Gamma^{(n)}(x_1,\ldots,x_n)
=\left.
\frac{\delta^n\Gamma}{\delta\varphi(x_1)\cdots\delta\varphi(x_n)}
\right|_{\varphi=v}.
}
$$

In momentum space, using qft.org's Fourier convention,

$$
\Gamma[\eta]
=\Gamma[v]
+\sum_{n=1}^{\infty}\frac1{n!}
\int_{p_1}\cdots\int_{p_n}
(2\pi)^4\delta^{(4)}(p_1+\cdots+p_n)
\Gamma^{(n)}(p_1,\ldots,p_n)
\eta(p_1)\cdots\eta(p_n).
$$

The Feynman-rule vertex associated with the proper $n$-point function is

$$
\boxed{\text{1PI vertex factor}=i\Gamma^{(n)}.}
$$

This convention matches the classical tree-level rule. For instance, if

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

then at tree level

$$
\Gamma^{(4)}=-\lambda,
\qquad
\text{vertex factor}=i\Gamma^{(4)}=-i\lambda.
$$

## The two-point kernel is the inverse exact propagator

The connected two-point function is generated by $W$:

$$
G_2^{\rm c}(x,y)
=-i\frac{\delta^2 W}{\delta J(x)\delta J(y)}.
$$

Differentiating

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x)
$$

with respect to $J(y)$ gives

$$
\int d^4z\,
\frac{\delta^2\Gamma}{\delta\varphi(x)\delta\varphi(z)}
\frac{\delta^2W}{\delta J(z)\delta J(y)}
=-\delta^{(4)}(x-y).
$$

Since

$$
\frac{\delta^2W}{\delta J(z)\delta J(y)}=iG_2^{\rm c}(z,y),
$$

we obtain

$$
\boxed{
\int d^4z\,\Gamma^{(2)}(x,z)G_2^{\rm c}(z,y)=i\delta^{(4)}(x-y).
}
$$

For a translation-invariant vacuum this becomes, in momentum space,

$$
\boxed{
\Gamma^{(2)}(p)G_2^{\rm c}(p)=i.
}
$$

Thus the exact connected propagator is the inverse of the exact quadratic kernel in $\Gamma$:

$$
\boxed{
G_2^{\rm c}(p)=\frac{i}{\Gamma^{(2)}(p)+i\epsilon}.
}
$$

For a free scalar field,

$$
\Gamma_0=S_0,
\qquad
\Gamma_0^{(2)}(p)=p^2-m^2,
$$

so

$$
G_{2,0}^{\rm c}(p)=\frac{i}{p^2-m^2+i\epsilon}=D_F(p).
$$

In an interacting theory, $\Gamma^{(2)}$ contains self-energy corrections. The pole of $G_2^{\rm c}$ determines the physical mass, and the pole residue determines the field-strength factor used in LSZ reduction.

## Connected diagrams as trees made from Γ

The Legendre transform removes the one-particle-reducible redundancy from connected diagrams. Equivalently, once $\Gamma$ is known, connected correlators can be generated by solving

$$
\frac{\delta\Gamma[\varphi]}{\delta\varphi(x)}=-J(x)
$$

for $\varphi$ as a functional of $J$, and then using

$$
W[J]=\Gamma[\varphi]+\int d^4x\,J(x)\varphi(x).
$$

Diagrammatically, this reconstruction uses **tree diagrams** whose vertices are $\Gamma^{(n)}$ and whose internal lines are the exact connected propagator. No new loops are added in this reconstruction; the loops have already been absorbed into the proper vertices of $\Gamma$.

This is the “marvelous property” of the effective action: it turns the full connected expansion into a classical-looking tree problem, but with quantum-corrected ingredients.

## Classical limit and loop expansion

At tree level,

$$
\boxed{\Gamma[\varphi]=S[\varphi].}
$$

Beyond tree level,

$$
\Gamma[\varphi]=S[\varphi]+\Gamma_{\rm 1-loop}[\varphi]+\Gamma_{\rm 2-loop}[\varphi]+\cdots.
$$

For a bosonic theory expanded around a background $\varphi$, the one-loop term has the schematic Lorentzian form

$$
\boxed{
\Gamma_{\rm 1-loop}[\varphi]
=\frac{i}{2}\operatorname{Tr}\log\left(S^{(2)}[\varphi]+i\epsilon\right),
}
$$

up to field-independent constants, regularization, counterterms, zero modes, and phase conventions. In Euclidean signature the corresponding expression is usually written as

$$
\boxed{
\Gamma_{E,\rm 1-loop}[\varphi]
=\frac12\operatorname{Tr}\log S_E^{(2)}[\varphi].
}
$$

Fermions contribute with the opposite determinant power, and gauge theories require gauge fixing and ghosts before the trace-log formula is meaningful.

This formula should not be read as a substitute for renormalization. The trace is ultraviolet divergent in continuum QFT and must be regulated. The point here is structural: $\Gamma$ is the natural home for loop-corrected equations of motion, masses, and proper vertices.

## Effective potential

For a constant scalar background,

$$
\varphi(x)=\varphi_0,
$$

translation invariance lets us define the effective potential by

$$
\boxed{
\Gamma[\varphi_0]=-
\left(\int d^4x\right)V_{\rm eff}(\varphi_0).
}
$$

The minus sign is the Lorentzian convention: for a constant field, the classical action contains $-\int d^4x\,V(\varphi_0)$.

At tree level,

$$
V_{\rm eff}(\varphi)=V_{\rm classical}(\varphi).
$$

Loop corrections modify it:

$$
V_{\rm eff}(\varphi)
=V_{\rm classical}(\varphi)+V_{\rm 1-loop}(\varphi)+V_{\rm 2-loop}(\varphi)+\cdots.
$$

Stationary points obey

$$
\boxed{
\frac{dV_{\rm eff}}{d\varphi}=0,
}
$$

for homogeneous vacua. Expanding $\Gamma$ around such a stationary point gives the quantum-corrected masses and couplings.

This is where the effective action becomes conceptually dangerous in a useful way. A classical potential may suggest one vacuum structure, while loop corrections can shift masses, move minima, or even change whether a symmetry is broken. That story belongs mostly to symmetry breaking and renormalization, but the machine starts here.

## Operator, path-integral, and structural views

| Viewpoint | Statement |
|---|---|
| Operator | $W[J]$ generates connected vacuum expectation values in the presence of sources. |
| Path integral | $\Gamma[\varphi]$ is the Legendre transform of $W[J]$ and equals $S$ plus loop corrections. |
| Diagrammatic | $\Gamma$ generates 1PI vertices; connected diagrams are trees built from 1PI vertices and exact propagators. |
| Structural | Stationary points of $\Gamma$ give quantum-corrected vacua and field equations. |

The effective action is therefore a meeting point of three languages: response theory, diagrammatics, and variational principles.

## Common pitfalls

### Confusing connected and one-particle irreducible

Every 1PI diagram with external legs is connected, but not every connected diagram is 1PI. Two cubic vertices joined by one internal line give a connected exchange diagram, but cutting the internal line disconnects it.

### Thinking the classical field is classical physics

The field $\varphi=\delta W/\delta J$ is a c-number expectation value. It can include all quantum effects. The word “classical” here means “not operator-valued,” not “tree-level.”

### Assuming Γ is always local

The classical action is usually local. The exact effective action is generally nonlocal. A local derivative expansion,

$$
\Gamma[\varphi]
=\int d^4x\left[-V_{\rm eff}(\varphi)+\frac12Z_{\rm eff}(\varphi)\partial_\mu\varphi\partial^\mu\varphi+\cdots\right],
$$

is an approximation valid under appropriate low-momentum or slowly varying conditions.

### Forgetting gauge dependence

In gauge theories, the off-shell effective action and effective potential can depend on gauge choice. Physical quantities extracted correctly from them do not. This is one reason gauge-theory effective actions require more discipline than scalar examples suggest.

### Treating the Legendre transform as automatic

Perturbatively, the transform is usually formal and useful. Nonperturbatively, convexity, multiple vacua, unstable directions, and infrared effects can complicate the map between $J$ and $\varphi$.

### Calling any action effective

The phrase “effective action” is overloaded. Here it means the 1PI quantum effective action $\Gamma[\varphi]$. In effective field theory, one also writes low-energy Wilsonian effective actions. They are related ideas, but they are not identical objects.

## Relations to nearby pages

- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) introduces $Z[J]$, $W[J]$, and the Legendre-transform preview.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains why $W[J]$ generates connected diagrams.
- [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) explains the saddle-point and determinant origin of the loop expansion.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explains how connected correlators and amputated diagrams become scattering amplitudes.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) will explain why loop corrections in $\Gamma$ require regularization and renormalization.

## Research status

The perturbative 1PI effective action is textbook-standard QFT. It is one of the central tools of renormalization, Ward identities, spontaneous symmetry breaking, background-field methods, and effective field theory. Nonperturbatively, the exact effective action is subtler: questions of convexity, gauge dependence, regulator dependence, and existence of the continuum theory are real mathematical issues rather than cosmetic details.

## Exercises

### Exercise 1: Derive the Legendre identity

Starting from

$$
\Gamma[\varphi]=W[J]-\int d^4x\,J(x)\varphi(x),
\qquad
\varphi(x)=\frac{\delta W}{\delta J(x)},
$$

show that

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Vary $\Gamma$:

$$
\delta\Gamma
=\delta W-\int d^4x\,\delta J(x)\varphi(x)-\int d^4x\,J(x)\delta\varphi(x).
$$

Using

$$
\delta W=\int d^4x\,\frac{\delta W}{\delta J(x)}\delta J(x)
=\int d^4x\,\varphi(x)\delta J(x),
$$

the first two terms cancel. Therefore

$$
\delta\Gamma=-\int d^4x\,J(x)\delta\varphi(x),
$$

so

$$
\boxed{\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).}
$$

</details>

### Exercise 2: Inverse two-point relation

Use the Legendre transform to show that

$$
\int d^4z\,\Gamma^{(2)}(x,z)G_2^{\rm c}(z,y)=i\delta^{(4)}(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate

$$
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x)
$$

with respect to $J(y)$:

$$
\int d^4z\,
\frac{\delta^2\Gamma}{\delta\varphi(x)\delta\varphi(z)}
\frac{\delta\varphi(z)}{\delta J(y)}
=-\delta^{(4)}(x-y).
$$

Since

$$
\frac{\delta\varphi(z)}{\delta J(y)}
=\frac{\delta^2W}{\delta J(z)\delta J(y)}
=iG_2^{\rm c}(z,y),
$$

we get

$$
i\int d^4z\,\Gamma^{(2)}(x,z)G_2^{\rm c}(z,y)
=-\delta^{(4)}(x-y).
$$

Equivalently,

$$
\boxed{
\int d^4z\,\Gamma^{(2)}(x,z)G_2^{\rm c}(z,y)=i\delta^{(4)}(x-y),
}
$$

because $1/i=-i$.

</details>

### Exercise 3: Tree-level quartic vertex

For

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

find the tree-level value of $\Gamma^{(4)}$ and the corresponding vertex factor.

<details>
<summary><strong>Solution</strong></summary>

At tree level, $\Gamma=S$. The fourth functional derivative of the interaction action gives

$$
\Gamma^{(4)}=-\lambda.
$$

The Feynman-rule vertex factor is

$$
i\Gamma^{(4)}=-i\lambda.
$$

</details>

### Exercise 4: Connected but not 1PI

Explain why a tree exchange diagram made of two cubic vertices joined by one internal line is connected but not 1PI.

<details>
<summary><strong>Solution</strong></summary>

The graph is connected because every external leg can be reached from every other through the graph. It is not 1PI because cutting the single internal line between the two cubic vertices separates the diagram into two disconnected pieces. A 1PI diagram must remain connected after cutting any single internal line.

</details>

### Exercise 5: Effective potential at tree level

For the classical scalar potential

$$
V(\phi)=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4,
$$

what is $V_{\rm eff}$ at tree level? What condition determines a homogeneous vacuum at this level?

<details>
<summary><strong>Solution</strong></summary>

At tree level,

$$
V_{\rm eff}(\phi)=V(\phi)
=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4.
$$

A homogeneous vacuum satisfies

$$
\frac{dV_{\rm eff}}{d\phi}=0,
$$

so

$$
m^2\phi+\frac{\lambda}{3!}\phi^3=0.
$$

</details>

### Exercise 6: One-loop determinant from a Gaussian

Suppose the action expanded around a background is

$$
S[\varphi+\eta]=S[\varphi]+\frac12\eta K\eta+\cdots.
$$

Ignoring interactions of $\eta$, what determinant appears after integrating over the fluctuation $\eta$?

<details>
<summary><strong>Solution</strong></summary>

The Gaussian fluctuation integral gives schematically

$$
\int\mathcal D\eta\,\exp\left(\frac{i}{2}\eta K\eta\right)
\propto [\det(K+i\epsilon)]^{-1/2}.
$$

Putting this into $e^{i\Gamma}$ gives

$$
i\Gamma[\varphi]
=iS[\varphi]-\frac12\operatorname{Tr}\log(K+i\epsilon)+\cdots,
$$

so

$$
\boxed{
\Gamma_{\rm 1-loop}[\varphi]=\frac{i}{2}\operatorname{Tr}\log(K+i\epsilon),
}
$$

up to field-independent constants and regularization.

</details>

## Sources and further reading

- J. Schwinger, “On the Green's Functions of Quantized Fields. I,” *Proceedings of the National Academy of Sciences* **37** (1951), 452–455.
- G. Jona-Lasinio, “Relativistic Field Theories with Symmetry-Breaking Solutions,” *Nuovo Cimento* **34** (1964), 1790–1795.
- S. Coleman and E. Weinberg, “Radiative Corrections as the Origin of Spontaneous Symmetry Breaking,” *Physical Review D* **7** (1973), 1888–1910.
- Sidney Coleman, *Lectures on Quantum Field Theory*, §§32.1–32.2 and §§44.2–44.3, for the loop expansion, the 1PI generating functional, and the effective potential.
- Mark Srednicki, *Quantum Field Theory*, §21, for the quantum action and its relation to 1PI diagrams.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, §16.1, for the external-field and quantum effective-action formalism.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, §§11.1–11.5, for effective actions and effective potentials in perturbation theory.

## Version history

- **2026-05-23:** Initial qft.org page on the 1PI effective action, Legendre transform, inverse exact propagator, tree reconstruction of connected diagrams, loop expansion, and effective potential.
