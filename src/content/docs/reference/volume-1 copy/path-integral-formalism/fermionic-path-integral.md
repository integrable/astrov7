---
title: "Fermionic Path Integral"
description: "Grassmann functional integrals for Dirac and Majorana fields, fermion determinants, propagators, sources, Euclidean continuation, closed-loop signs, and zero modes."
sidebar:
  label: "Fermionic Path Integral"
  order: 7
---

## Summary

The fermionic path integral is the functional-integral version of fermionic canonical quantization. For a free Dirac field, introduce independent Grassmann-valued spinor fields

$$
\psi_\alpha(x),
\qquad
\bar\psi_\alpha(x),
$$

and Grassmann sources

$$
\eta_\alpha(x),
\qquad
\bar\eta_\alpha(x).
$$

With qft.org's mostly-minus Lorentzian conventions, define

$$
K=i\gamma^\mu\partial_\mu-m+i\epsilon.
$$

The normalized free generating functional is

$$
\boxed{
Z_0[\eta,\bar\eta]
=\frac{
\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left\{i\int d^4x\,[\bar\psi K\psi+
\bar\eta\psi+\bar\psi\eta]\right\}}
{\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left\{i\int d^4x\,\bar\psi K\psi\right\}}
=\exp\left[-\int d^4x\,d^4y\;\bar\eta(x)S_F(x-y)\eta(y)\right].
}
$$

Here

$$
\boxed{
S_F(x-y)=\int\frac{d^4p}{(2\pi)^4}
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}
}
$$

is the usual time-ordered Dirac propagator. It satisfies

$$
\boxed{
(i\gamma^\mu\partial_\mu-m)S_F(x-y)=i\delta^{(4)}(x-y)\mathbf 1.
}
$$

The finite-dimensional reason this works is the Grassmann Gaussian identity

$$
\int[d\bar\psi\,d\psi]\,
\exp(-\bar\psi A\psi+\bar\xi\psi+\bar\psi\xi)
=\det A\,\exp(\bar\xi A^{-1}\xi).
$$

After regularization, $A$ becomes the quadratic Dirac kernel, including the Lorentzian factor of $i$ when appropriate. The determinant gives vacuum and background-field effects; the inverse operator gives the fermion propagator; and the anticommuting sources generate the signs in fermionic Wick contractions.

Srednicki develops the Dirac and Majorana source functionals using Grassmann variables, Coleman derives the finite-dimensional Grassmann Gaussian determinant in his functional-integral treatment, Zee stresses that the determinant must appear in the numerator rather than denominator, and Weinberg gives a canonical-to-path-integral derivation using anticommuting c-numbers (Srednicki 2007, §§43–44; Coleman 2019, §29.1; Zee 2010, ch. II.5; Weinberg 1995, Vol. I, §9.5).

## Prerequisites

You should know [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/), [Dirac Field](/foundations/free-fields/dirac-field/), [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), and [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/).

## Core idea

A fermionic path integral is a Grassmann Gaussian at every spacetime point and spinor component.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Fermionic path integral map from quadratic form to determinant and propagator](/figures/foundations/fermionic-path-integral-map.svg)

<figcaption>

The quadratic Dirac operator $K$ appears in two complementary outputs. The vacuum Grassmann integral gives a determinant, while the source-dependent Gaussian gives the inverse kernel. With qft.org's propagator convention, $S_F=iK^{-1}$.

</figcaption>
</figure>

The operator statement is

$$
S_{F,\alpha\beta}(x-y)
=\langle0|T\{\psi_\alpha(x)\bar\psi_\beta(y)\}|0\rangle.
$$

The path-integral statement is that the same object comes from source derivatives of $Z_0[\eta,\bar\eta]$.

The structural chain is:

```txt
fermionic statistics
  → Grassmann fields and sources
  → determinant from vacuum integration
  → inverse Dirac operator from source derivatives
  → minus signs for closed fermion loops
```

The path integral is not a probability measure over ordinary spinor-valued functions. It is an algebraic representation of fermionic time-ordered correlation functions.

## From finite variables to fields

Regulate spacetime, spinor, and internal labels into one finite index

$$
I=(x,\alpha,a,\ldots).
$$

A Dirac field becomes finitely many Grassmann pairs

$$
\psi_I,
\qquad
\bar\psi_I.
$$

A free quadratic action becomes

$$
\bar\psi_IK_{IJ}\psi_J.
$$

The finite Gaussian gives

$$
\int[d\bar\psi\,d\psi]e^{-\bar\psi K\psi}=\det K,
$$

and, after normalization,

$$
\langle\psi_I\bar\psi_J\rangle=(K^{-1})_{IJ},
$$

up to the sign convention fixed by the source derivative order. The continuum notation

$$
\int\mathcal D\bar\psi\,\mathcal D\psi
$$

is shorthand for the regulated limit. The finite-dimensional formula is the honest algebraic object; the continuum functional integral inherits its meaning from a regulator.

## Lorentzian Dirac Gaussian

The free Dirac action is

$$
S_0[\psi,\bar\psi]
=\int d^4x\,\bar\psi(x)(i\gamma^\mu\partial_\mu-m+i\epsilon)\psi(x).
$$

The source action is

$$
S_{\mathrm{src}}
=\int d^4x\,[\bar\eta(x)\psi(x)+\bar\psi(x)\eta(x)].
$$

Here $\eta$ and $\bar\eta$ are Grassmann-valued sources. They anticommute with each other and with the integration variables.

The normalized Lorentzian functional integral is

$$
Z_0[\eta,\bar\eta]
=\frac{
\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\{iS_0+iS_{\mathrm{src}}\}}
{\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\{iS_0\}}.
$$

Using the finite Grassmann source Gaussian gives

$$
\boxed{
Z_0[\eta,\bar\eta]
=\exp\left[-\int d^4x\,d^4y\,
\bar\eta(x)S_F(x-y)\eta(y)\right].
}
$$

The Dirac propagator is

$$
\boxed{
S_F(x-y)
=\int\frac{d^4p}{(2\pi)^4}
\frac{i(p\!\!/+m)e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
}
$$

Equivalently,

$$
S_F(p)=\frac{i}{p\!\!/-m+i\epsilon}
=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

The shorthand is distributional: the $i\epsilon$ prescription belongs to the pole in $p^2-m^2$.

Because

$$
(i\gamma^\mu\partial_\mu-m)S_F(x-y)=i\delta^{(4)}(x-y)\mathbf 1,
$$

the strict inverse kernel of $K=i\gamma^\mu\partial_\mu-m$ is $S_F/i$. The conventional Feynman propagator includes the extra factor of $i$, just as the scalar Feynman propagator does.

## Source derivatives and signs

Because the sources are Grassmann odd, derivative order matters. One consistent convention is to use a left derivative with respect to $\bar\eta$ and a right derivative with respect to $\eta$:

$$
\boxed{
\langle0|T\{\psi_\alpha(x)\bar\psi_\beta(y)\}|0\rangle
=
\left.
\frac{\delta^L}{i\delta\bar\eta_\alpha(x)}
Z_0[\eta,\bar\eta]
\frac{\overleftarrow{\delta}^{\,R}}{i\delta\eta_\beta(y)}
\right|_{\eta=\bar\eta=0}
=S_{F,\alpha\beta}(x-y).
}
$$

The factors of $i$ come from the source term $i\int(\bar\eta\psi+\bar\psi\eta)$ in the exponent. The derivative order and left/right convention are part of the definition.

For more insertions,

$$
\langle0|T\{\psi_1\bar\psi_1\cdots\psi_n\bar\psi_n\}|0\rangle
$$

is a signed sum over pairings. The signs are exactly the signs produced by differentiating the Grassmann source exponential.

## Fermion determinants

Before normalization, the free Gaussian gives a determinant:

$$
\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left[i\int d^4x\,\bar\psi K\psi\right]
\propto\det(iK).
$$

In an empty flat-space free theory, this determinant cancels from normalized correlators. In a background field, it can be the main object. For example, if the Dirac operator depends on a background gauge field,

$$
K[A]=i\gamma^\mu D_\mu[A]-m,
$$

then integrating out the fermion produces

$$
\boxed{
\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left[i\int d^4x\,\bar\psi K[A]\psi\right]
\propto \det(iK[A]).
}
$$

Equivalently,

$$
\det(iK[A])=\exp\operatorname{Tr}\log(iK[A]).
$$

The trace includes spacetime, spinor, and internal indices. Expanding the trace-log gives closed fermion loops in the background.

A useful schematic expansion is

$$
\operatorname{Tr}\log(K_0+V)
=\operatorname{Tr}\log K_0
+\operatorname{Tr}\log(1+K_0^{-1}V).
$$

The second term expands as

$$
\operatorname{Tr}(K_0^{-1}V)
-\frac12\operatorname{Tr}(K_0^{-1}V K_0^{-1}V)+\cdots.
$$

This is the loop expansion in background-field language.

## Closed-loop minus signs

Closed fermion loops carry an extra minus sign relative to boson loops. There are two equivalent ways to see this.

In the operator formalism, closing a fermion line requires reordering fermionic operators, producing a sign from anticommutation.

In the path-integral formalism, the sign is encoded in Grassmann integration and the determinant. Schematically, a bosonic Gaussian gives

$$
(\det A)^{-1/2}=\exp\left[-\frac12\operatorname{Tr}\log A\right],
$$

whereas a Dirac Grassmann Gaussian gives

$$
\det K=\exp\operatorname{Tr}\log K.
$$

When translated into the usual perturbative Feynman rules with an overall $iS$ expansion, this determinant structure is responsible for the closed-fermion-loop sign.

The moral: the famous minus sign is not an extra decoration added after drawing diagrams. It is already in the Grassmann algebra.

## Euclidean fermions

After Wick rotation, the free Euclidean Dirac action is often written

$$
S_{E,0}=\int d^4x_E\,\bar\psi D_E\psi,
$$

with one common convention

$$
D_E=\gamma_E^a\partial_a+m,
\qquad
\{\gamma_E^a,\gamma_E^b\}=2\delta^{ab}.
$$

The Euclidean source functional is

$$
\boxed{
Z_{E,0}[\eta,\bar\eta]
=\frac{
\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left[-\int\bar\psi D_E\psi+
\int(\bar\eta\psi+\bar\psi\eta)\right]}
{\int\mathcal D\bar\psi\,\mathcal D\psi\,
\exp\left[-\int\bar\psi D_E\psi\right]}
=\exp\left[\int d^4x_Ed^4y_E\,\bar\eta(x)D_E^{-1}(x,y)\eta(y)\right].
}
$$

Before normalization,

$$
\int\mathcal D\bar\psi\,\mathcal D\psi\,
e^{-\int\bar\psi D_E\psi}=\det D_E
$$

up to a convention-dependent overall sign. Euclidean determinants are central in lattice QCD, anomaly calculations, finite-temperature field theory, and effective actions.

:::note[Reflection positivity]
Euclidean fermions require more care than Euclidean scalar fields. Spinor conjugation, time reflection, and Grassmann integration interact. Writing $e^{-S_E}$ is not by itself a proof that the Euclidean theory reconstructs a unitary Lorentzian theory.
:::

## Majorana fields and Pfaffians

A Dirac integral uses independent pairs $\psi$ and $\bar\psi$, so the finite Gaussian gives a determinant.

A Majorana fermion has half as many independent Grassmann components. Its quadratic form can be written schematically as

$$
\frac12\Psi^T A\Psi,
$$

where $A$ is antisymmetric in the combined spinor, spacetime, and internal indices. The finite-dimensional real Grassmann Gaussian gives

$$
\boxed{
\int\mathcal D\Psi\,
\exp\left(\frac12\Psi^T A\Psi\right)
=\operatorname{pf}(A),
}
$$

with

$$
\operatorname{pf}(A)^2=\det A.
$$

In continuum language, a Majorana path integral produces a Pfaffian. Its sign can be physically important in topological and lattice contexts.

## Zero modes

If the fermion operator has a zero mode, then

$$
\det K=0.
$$

This does not mean the theory is meaningless. It means the plain Gaussian with no insertions vanishes because the Berezin integral over the zero-mode variable is unsaturated.

For one zero-mode Grassmann pair $\eta_0,\bar\eta_0$,

$$
\int d\eta_0d\bar\eta_0\,1=0,
$$

but

$$
\int d\eta_0d\bar\eta_0\,\bar\eta_0\eta_0=1.
$$

Correlation functions can be nonzero only if the operator insertions supply enough fermionic factors to soak up the zero modes. This mechanism becomes essential in instanton physics and anomaly calculations.

## Ghost fields preview

Grassmann fields are not always spinor fields. Gauge fixing in non-Abelian gauge theory produces Faddeev–Popov ghost fields: Lorentz-scalar fields with Grassmann statistics. Their job is to represent a determinant from gauge fixing.

This does not violate the spin-statistics theorem because ghosts are not physical external particles in the Hilbert-space spectrum. They are auxiliary fields inside gauge-fixed path integrals.

## Interactions

For a Yukawa interaction

$$
\mathcal L_{\mathrm{int}}=-g\phi\bar\psi\psi,
$$

the full source functional can be written formally as an interaction operator acting on free source functionals:

$$
Z[J,\eta,\bar\eta]
=\exp\left[i\int d^4x\,\mathcal L_{\mathrm{int}}
\left(\frac1i\frac{\delta}{\delta J},
\frac{\delta}{i\delta\bar\eta},
\frac{\delta}{i\delta\eta}
\right)\right]
Z_{0,\phi}[J]Z_{0,\psi}[\eta,\bar\eta].
$$

The fermionic derivative ordering must be fixed before this formula is used. Once that is done, expanding the exponential gives the usual fermion propagators, Yukawa vertices, and closed-loop signs.

## Three lenses

### Operator lens

Fermions are quantized with anticommutators. The time-ordered Dirac propagator is the vacuum expectation value

$$
S_F(x-y)=\langle0|T\{\psi(x)\bar\psi(y)\}|0\rangle.
$$

### Path-integral lens

Fermions are represented by Grassmann-valued integration variables. The free Gaussian gives

```txt
determinant of the Dirac operator
inverse of the Dirac operator
```

from the same finite algebraic identity.

### Structural lens

The determinant records the effect of virtual fermions on backgrounds. The inverse kernel records propagation. The signs enforce statistics. The same formalism later feeds directly into anomalies, gauge fixing, instantons, and effective actions.

## Common pitfalls

### Treating ψ and ψ̄ as complex conjugates inside the integral

In the path integral, $\psi$ and $\bar\psi$ are independent Grassmann variables. The bar is notation chosen to match Lorentz-covariant spinor bilinears.

### Forgetting derivative order

Fermionic source derivatives are odd operations. Changing their order changes signs. A correct convention must specify left/right derivatives or otherwise make the ordering unambiguous.

### Dropping determinants too quickly

For normalized flat-space correlators in a free theory, the determinant cancels. In background fields, curved spacetime, finite temperature, and gauge theories, the determinant is often the point.

### Confusing the strict inverse with the propagator

The Dirac operator satisfies

$$
(i\gamma^\mu\partial_\mu-m)S_F=i\delta.
$$

So $S_F/i$ is the strict inverse kernel, while $S_F$ is the conventional time-ordered propagator.

### Ignoring zero modes

If the fermion operator has zero modes, the Gaussian determinant vanishes and nonzero correlation functions require insertions that soak up the zero modes.

### Forgetting that ghosts are not physical fermions

Faddeev–Popov ghosts are Grassmann fields, but they are Lorentz scalars and do not represent physical asymptotic fermions.

## Relation to other topics

- [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) gives the finite-dimensional algebra used here.
- [Dirac Field](/foundations/free-fields/dirac-field/) derives the same propagator from canonical quantization.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) fixes the $i\epsilon$ convention and propagator normalization.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) explains the bosonic source-functional hierarchy that this page extends.
- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) supplies the Wick-rotation context for Euclidean determinants.
- [Spinor Bilinears](/foundations/free-fields/spinor-bilinears/) classifies local fermion operators appearing in sources and interactions.
- Later pages on gauge fixing, BRST, anomalies, instantons, and the Standard Model will repeatedly use fermion determinants and Grassmann variables.

## Research status

- **Established:** Free Dirac and Majorana Grassmann path integrals, source differentiation, determinants, Pfaffians, and closed-loop signs are standard textbook material.
- **Active:** Chiral fermion regulators, lattice fermions, Pfaffian signs, sign problems, anomaly phases, and fermion determinants in topological backgrounds remain technically active.
- **Speculative:** None.

## Exercises

### Exercise 1: Finite-dimensional Dirac analogue

Let $\psi_i,\bar\psi_i$ be $N$ Grassmann pairs and let $K$ be an invertible matrix. Show that

$$
Z[\eta,\bar\eta]
=\frac{\int[d\bar\psi d\psi]\,
\exp(-\bar\psi K\psi+\bar\eta\psi+\bar\psi\eta)}
{\int[d\bar\psi d\psi]e^{-\bar\psi K\psi}}
$$

is

$$
Z[\eta,\bar\eta]=\exp(\bar\eta K^{-1}\eta).
$$

<details>
<summary><strong>Solution</strong></summary>

Complete the square:

$$
-\bar\psi K\psi+\bar\eta\psi+\bar\psi\eta
=-(\bar\psi-\bar\eta K^{-1})K(\psi-K^{-1}\eta)+\bar\eta K^{-1}\eta.
$$

The Berezin measure is translation invariant, so the shifted Gaussian gives the same determinant as the denominator. Therefore

$$
\boxed{Z[\eta,\bar\eta]=\exp(\bar\eta K^{-1}\eta).}
$$

</details>

### Exercise 2: Dirac operator inversion

Verify that

$$
S_F(p)=\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}
$$

satisfies

$$
(p\!\!/-m)S_F(p)=i
$$

away from the pole.

<details>
<summary><strong>Solution</strong></summary>

Use the Clifford algebra:

$$
(p\!\!/-m)(p\!\!/+m)=p\!\!/^{\,2}-m^2=p^2-m^2.
$$

Therefore

$$
(p\!\!/-m)S_F(p)
=(p\!\!/-m)\frac{i(p\!\!/+m)}{p^2-m^2+i\epsilon}
\to i,
$$

with the pole understood distributionally. In position space,

$$
(i\gamma^\mu\partial_\mu-m)S_F(x-y)=i\delta^{(4)}(x-y).
$$

</details>

### Exercise 3: Two-point function from sources

Starting from

$$
Z_0[\eta,\bar\eta]
=\exp[-\bar\eta S_F\eta],
$$

explain why the two-point function is generated by one derivative with respect to $\bar\eta$ and one derivative with respect to $\eta$.

<details>
<summary><strong>Solution</strong></summary>

The source term is

$$
\int(\bar\eta\psi+\bar\psi\eta).
$$

A derivative with respect to $\bar\eta$ inserts $\psi$, while a derivative with respect to $\eta$ inserts $\bar\psi$. Because the sources are Grassmann odd, the derivative order and left/right convention determine the sign. With the convention fixed in the text,

$$
\left.
\frac{\delta^L}{i\delta\bar\eta_\alpha(x)}
Z_0
\frac{\overleftarrow{\delta}^{\,R}}{i\delta\eta_\beta(y)}
\right|_0
=S_{F,\alpha\beta}(x-y).
$$

This reproduces

$$
\langle0|T\{\psi_\alpha(x)\bar\psi_\beta(y)\}|0\rangle.
$$

</details>

### Exercise 4: Integrating out a background-coupled fermion

Let

$$
S[\psi,\bar\psi;A]=\int d^4x\,\bar\psi K[A]\psi.
$$

Show formally that integrating out the fermion produces a determinant.

<details>
<summary><strong>Solution</strong></summary>

Regulate the theory so that $K[A]$ becomes a finite matrix. Then the Grassmann Gaussian gives

$$
\int[d\psi d\bar\psi]e^{i\bar\psi K[A]\psi}
\propto\det(iK[A]).
$$

In continuum notation,

$$
\int\mathcal D\bar\psi\mathcal D\psi\,
e^{i\int\bar\psi K[A]\psi}
\propto\det(iK[A])
=\exp\operatorname{Tr}\log(iK[A]).
$$

The trace-log expansion generates closed fermion loops in the background field.

</details>

### Exercise 5: Yukawa vertex from source derivatives

For

$$
\mathcal L_{\mathrm{int}}=-g\phi\bar\psi\psi,
$$

write the formal source-derivative operator that generates perturbation theory from the free scalar and fermion generating functionals.

<details>
<summary><strong>Solution</strong></summary>

Replace fields by derivatives with respect to their sources:

$$
\phi\to\frac1i\frac{\delta}{\delta J},
\qquad
\psi\to\frac{\delta}{i\delta\bar\eta},
\qquad
\bar\psi\to\frac{\delta}{i\delta\eta},
$$

with a fixed left/right convention for the fermionic derivatives. Then

$$
Z[J,\eta,\bar\eta]
=
\exp\left[-ig\int d^4x\,
\frac1i\frac{\delta}{\delta J(x)}
\frac{\delta}{i\delta\eta(x)}
\frac{\delta}{i\delta\bar\eta(x)}
\right]
Z_{0,\phi}[J]Z_{0,\psi}[\eta,\bar\eta],
$$

up to the chosen fermionic derivative order. Expanding the exponential gives the Yukawa perturbation series.

</details>

### Exercise 6: Majorana Pfaffian

Explain why a Majorana path integral gives a Pfaffian rather than a determinant.

<details>
<summary><strong>Solution</strong></summary>

A Dirac integral uses independent pairs $\psi,\bar\psi$ and has quadratic form $\bar\psi K\psi$. Its finite-dimensional Gaussian gives $\det K$.

A Majorana fermion has half as many independent Grassmann components. The quadratic form can be written schematically as

$$
\frac12\Psi^TA\Psi,
$$

where $A$ is antisymmetric. The real Grassmann Gaussian gives

$$
\int d\Psi\,e^{\frac12\Psi^TA\Psi}=\operatorname{pf}(A),
$$

and

$$
\operatorname{pf}(A)^2=\det A.
$$

So the Majorana functional integral is naturally a Pfaffian.

</details>

## Sources and further reading

### Primary references

- F. A. Berezin, *The Method of Second Quantization*, for the algebraic foundation of Grassmann integration.

### Standard textbook treatments

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §9.5, for a canonical derivation of path integrals for fermions.
- M. Srednicki, *Quantum Field Theory*, §§42–44, for the Dirac propagator and fermionic path integrals.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, §29, for functional integration for Fermi fields and extensions of functional-integral methods.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. II.5, for the determinant and vacuum-energy viewpoint.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §9.5, for the common perturbative convention.

### For a first pass

- Read [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) first, then this page.
- Zee, ch. II.5.
- Srednicki, §§43–44.

### For mathematical precision

- Treat the continuum functional integral as a regulated limit. In rigorous or lattice settings, the determinant or Pfaffian is defined only after choosing a regulator, boundary conditions, and a finite-dimensional approximation.

## Version history

- **2026-05-23:** Initial qft.org page on the fermionic path integral, Dirac source functional, fermion determinant, Euclidean fermions, loop signs, Majorana Pfaffians, ghost preview, interactions, and zero modes.
