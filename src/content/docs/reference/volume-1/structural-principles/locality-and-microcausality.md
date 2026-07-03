---
title: "Locality and Microcausality"
description: "Spacelike separation, local algebras of observables, graded commutativity, free-field checks, causal response, and the distinction between correlations and signals."
sidebar:
  label: "Locality and Microcausality"
  order: 1
---

## Summary

**Locality** is the idea that observables can be associated with bounded spacetime regions. **Microcausality** is the corresponding quantum statement: observables localized in spacelike separated regions commute.

If $R_1$ and $R_2$ are spacetime regions such that every point of $R_1$ is spacelike separated from every point of $R_2$, then

$$
\boxed{[O_1,O_2]=0,
\qquad
O_1\in\mathcal A(R_1),\quad O_2\in\mathcal A(R_2).}
$$

Here $\mathcal A(R)$ denotes the algebra of observables localized in the region $R$. For elementary fields, the pointlike version is usually written schematically as

$$
\boxed{[\phi_a(x),\phi_b(y)]=0
\quad\text{if}\quad (x-y)^2<0}
$$

for bosonic fields, and as a graded version for fermionic fields:

$$
\boxed{[F_1(x),F_2(y)]_{\mathrm{gr}}=0
\quad\text{if}\quad (x-y)^2<0.}
$$

The graded commutator is

$$
[A,B]_{\mathrm{gr}}
=AB-(-1)^{|A||B|}BA,
$$

where $|A|=0$ for an even operator and $|A|=1$ for an odd fermionic operator. Physical bosonic observables are even, so their graded commutator is an ordinary commutator.

This condition is not the claim that all correlations vanish outside the light cone. Vacuum correlators can be nonzero at spacelike separation. The claim is sharper and more operational: local operations in spacelike separated regions cannot affect one another’s measurement outcomes through operator noncommutativity. Coleman presents this as the basic way a relativistic quantum theory avoids superluminal signaling: observables measurable in spacelike separated regions must commute (Coleman 2019, ch. 3). Weinberg builds causal quantum fields precisely so that Lorentz invariance, cluster decomposition, antiparticles, and local commutativity fit together (Weinberg 1995, Vol. I, ch. 5). Srednicki’s free scalar construction makes the same point through the Pauli–Jordan commutator and the spin–statistics theorem (Srednicki 2007, §§3–4).

<figure class="doc-figure" style="--figure-width: 54rem;">

![Locality and microcausality map](/figures/foundations/locality-microcausality-map.svg)

<figcaption>

Microcausality assigns commuting observable algebras to spacelike separated regions. Correlations may exist across spacelike separation, but retarded response and local measurement influence vanish outside the light cone.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Normalizations](/foundations/conventions-and-normalizations/), [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/), [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/), [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/), [Klein–Gordon Field](/foundations/free-fields/klein-gordon-field/), [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/), [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/), [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/), and [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/).

:::note[Conventions]
We use the qft.org default mostly-minus metric,

$$
x^2=(x^0)^2-\mathbf x^2.
$$

Thus $x$ and $y$ are spacelike separated when

$$
(x-y)^2<0.
$$

When it is useful to emphasize spacelike separation of regions, we write

$$
R_1\perp R_2.
$$

Fields are operator-valued distributions, so the mathematically clean statements use smeared fields such as

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
$$

where $f$ is a smooth test function with compact support.
:::

:::note[Assumptions]
The clean form of microcausality assumes a relativistic QFT with a fixed causal structure, local observables, a positive-energy vacuum, and a Hilbert-space interpretation. Gauge-fixed descriptions, nonlocal effective actions, curved backgrounds without global Poincaré symmetry, finite-density states, open systems, and nonrelativistic field theories may require modified formulations. The principle is not discarded there, but it must be stated in the correct language.
:::

## Locality versus microcausality

The word **locality** is used in several related ways. They should not be blurred together.

A Lagrangian is local when it is an integral of a density depending on fields and finitely many derivatives at the same spacetime point:

$$
S=\int d^4x\,\mathcal L(\Phi(x),\partial\Phi(x),\ldots).
$$

An observable is local when it can be measured, at least ideally, inside a bounded spacetime region. A local scalar density such as $\phi^2(x)$, after smearing over a small region, is the prototype.

Microcausality is the operator statement that local observables in spacelike separated regions commute:

$$
R_1\perp R_2
\quad\Longrightarrow\quad
[\mathcal A(R_1),\mathcal A(R_2)]=0.
$$

These ideas are related but not identical. A local-looking classical action does not automatically define a healthy quantum theory. A nonlocal field redefinition can make a local theory look nonlocal. Gauge fixing can introduce instantaneous-looking terms that cancel in gauge-invariant observables. The structural principle is about the algebra of physical local observables, not merely about appearances in one set of variables.

## Why commutativity is the causal condition

In quantum mechanics, noncommuting observables interfere with one another’s measurement statistics. If two observers in spacelike separated regions could measure noncommuting observables, then the choice to measure one observable could alter the statistics of the other without any light-speed signal connecting the regions. That would make the phrase “spacelike separated experiment” meaningless.

So a relativistic quantum theory needs more structure than ordinary quantum mechanics. It must say which observables are available in which spacetime regions. The causal condition is then simple:

$$
\boxed{
\text{spacelike separated measurements must be order-independent.}
}
$$

Order-independence is exactly commutativity for bosonic observables:

$$
O_1O_2=O_2O_1.
$$

This does not mean that a local observer can measure every Hermitian operator on the full Hilbert space. That would be much too much. A local observer can measure only operators belonging to the algebra of their region.

This is one of the conceptual reasons fields enter so naturally. Fields give us a way to build operators localized in regions:

$$
O_f=\int d^4x\,f(x)\mathcal O(x),
\qquad
\operatorname{supp}f\subset R.
$$

The support of $f$ says where the operation lives.

## The free scalar field check

For the real free scalar field,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

where $\Delta$ is the Pauli–Jordan function. It satisfies the Klein–Gordon equation in each argument and is fixed by the equal-time canonical commutators.

To see why it vanishes at spacelike separation, use two facts.

First, the commutator is Lorentz invariant for a scalar field:

$$
[\phi(\Lambda x),\phi(\Lambda y)]
= [\phi(x),\phi(y)]
$$

up to the corresponding unitary implementation of the Lorentz transformation.

Second, if $z=x-y$ is spacelike, there is a Lorentz frame in which

$$
z^0=0.
$$

In that frame, the equal-time canonical relation gives

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0.
$$

Therefore

$$
\boxed{
[\phi(x),\phi(y)]=0
\quad\text{for}\quad (x-y)^2<0.
}
$$

That is the simplest demonstration of microcausality in a free scalar theory. The same logic underlies the causal support of $\Delta(x)$: the commutator has support only on and inside the light cone.

## Fermions and graded locality

For fermionic fields, the elementary fields themselves are odd operators. The local condition is therefore graded:

$$
\{\psi_\alpha(x),\psi_\beta(y)\}=0,
\qquad
\{\psi_\alpha(x),\bar\psi_\beta(y)\}=0,
\qquad
(x-y)^2<0.
$$

This is not a statement that physical measurements anticommute. Physical observables are even combinations, such as

$$
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu\psi,
\qquad
F_{\mu\nu}F^{\mu\nu},
$$

and even local observables commute at spacelike separation.

This is one reason the spin–statistics theorem is not cosmetic. If integer-spin fields were quantized with anticommutators, or half-integer-spin fields with commutators, the basic local algebra would fail in a relativistic theory with positive energy and a stable vacuum.

## Correlations are not signals

A common beginner trap is to confuse three different objects:

$$
\langle 0|\phi(x)\phi(y)|0\rangle,
\qquad
[\phi(x),\phi(y)],
\qquad
\langle 0|T\phi(x)\phi(y)|0\rangle.
$$

The Wightman function

$$
\langle 0|\phi(x)\phi(y)|0\rangle
$$

can be nonzero for spacelike separation. That reflects vacuum correlations. It does not imply a signal.

The commutator

$$
[\phi(x),\phi(y)]
$$

controls the response of one local observable to a perturbation by another. This vanishes at spacelike separation.

The Feynman propagator

$$
i\Delta_F(x-y)=\langle 0|T\phi(x)\phi(y)|0\rangle
$$

also need not vanish outside the light cone. It is a time-ordered Green function with a boundary prescription. It is not the amplitude for a classical particle to travel from $y$ to $x$, and it is not the causal response function.

The causal response function is the retarded propagator. With qft.org’s convention $[\phi(x),\phi(y)]=i\Delta(x-y)$,

$$
G_R(x-y)=-\theta(x^0-y^0)\Delta(x-y).
$$

For a local relativistic free field,

$$
G_R(x-y)=0
\quad\text{unless}\quad
x\in J^+(y),
$$

where $J^+(y)$ is the future causal cone of $y$.

## Local operators and smearing

Strictly speaking, $\phi(x)$ is not an ordinary operator at a point. It is an operator-valued distribution. Products such as $\phi^2(x)$ require renormalization, and even the field itself is best tested against smooth functions:

$$
\phi(f)=\int d^4x\,f(x)\phi(x).
$$

The smeared form of microcausality is

$$
[\phi(f),\phi(g)]=0
$$

when the supports of $f$ and $g$ are spacelike separated. For fermions one uses the graded commutator.

This is not pedantry. Smearing is what makes the region dependence explicit. It also prevents one from mistaking singular short-distance behavior for a violation of causality. Local QFT can have ultraviolet singularities as $x\to y$ while still satisfying exact spacelike commutativity for separated supports.

## Interactions and locality

In perturbation theory, local interactions are built from local products of fields:

$$
\mathcal L_I(x)
=-\frac\lambda{4!}\phi^4(x),
\qquad
\mathcal L_I(x)=-g\bar\psi(x)\psi(x)\phi(x),
$$

or their gauge-covariant analogues. The Dyson expansion then inserts time-ordered products of local densities:

$$
S=T\exp\left(i\int d^4x\,\mathcal L_I(x)\right).
$$

The locality of the densities is what lets one organize perturbation theory in terms of local vertices, local counterterms, and causal analytic structure. After renormalization, the theory must still be expressible in terms of local operators if it is to remain an ordinary local QFT.

The phrase “local counterterm” is not just a technical convenience. It is the perturbative shadow of the same principle: short-distance singularities may be absorbed into local terms because the theory’s ultraviolet structure is local.

## Gauge theories

Gauge theories require care because the gauge potential $A_\mu$ is not itself a gauge-invariant observable. Depending on the gauge, intermediate formulas may contain instantaneous-looking terms. Coulomb gauge is the classic example: an instantaneous Coulomb interaction appears, but physical gauge-invariant quantities still respect relativistic causality.

The safest statement is about gauge-invariant or BRST-invariant local observables, such as

$$
F_{\mu\nu}(x),
\qquad
\bar\psi(x)\gamma^\mu\psi(x),
\qquad
\operatorname{tr}F_{\mu\nu}(x)F^{\mu\nu}(x).
$$

Charged operators in gauge theory can be subtle because Gauss’s law ties charge to long-range electric flux. A gauge-invariant charged operator usually requires some dressing, and that dressing may be nonlocal. This is not a contradiction. It says that “local charged particle operator” is often the wrong object. The local observables are neutral gauge-invariant densities; charged sectors are a more global story.

## Path-integral viewpoint

The path integral makes locality visible through the action:

$$
Z[J]=\int\mathcal D\Phi\,
\exp\left(i\int d^4x\,[\mathcal L(\Phi,\partial\Phi)+J(x)\mathcal O(x)]\right).
$$

A source $J(x)$ couples locally to an operator $\mathcal O(x)$. Functional differentiation with respect to sources supported in separated regions gives correlation functions of localized insertions.

But the path integral by itself does not automatically prove microcausality. One still needs the Lorentzian contour and boundary prescription, or a reconstruction theorem from Euclidean data. In Euclidean QFT, locality plus reflection positivity, symmetry, and suitable regularity conditions are what allow reconstruction of a unitary Lorentzian theory with local commutativity.

So the operator and path-integral languages complement each other:

| Language | Locality appears as |
| --- | --- |
| Operator | commuting local algebras at spacelike separation |
| Canonical | equal-time commutators plus Lorentz covariance |
| Path integral | local action, local sources, local counterterms |
| Euclidean | reflection-positive local Schwinger functions |
| Gauge theory | local gauge-invariant or BRST-closed observables |

## What microcausality does not say

Microcausality does not say that particles cannot be discussed outside the light cone. Particles are asymptotic excitations; locality is about observables and operator algebras.

It does not say that the Feynman propagator vanishes outside the light cone. It does not.

It does not say that entanglement is absent between spacelike separated regions. Vacuum entanglement is a defining feature of local QFT.

It does not say that a nonlocal-looking gauge-fixed formula is unphysical. One must check gauge-invariant or BRST-invariant observables.

It does not say that every effective interaction written with inverse derivatives is forbidden. Some nonlocal terms arise after integrating out fields and are valid as effective descriptions, but a fundamental local completion must restore causal local dynamics at the appropriate scale.

## Common pitfalls

**Pitfall 1: Treating spacelike correlations as superluminal signals.** Nonzero spacelike two-point functions are correlations, not response functions. Signaling is controlled by commutators and retarded functions.

**Pitfall 2: Asking whether the Feynman propagator is causal.** The Feynman propagator has the causal pole prescription needed for perturbation theory, but it is not the retarded response function.

**Pitfall 3: Forgetting fermionic grading.** Fermion fields anticommute at spacelike separation. Even observables made from them commute.

**Pitfall 4: Using point fields too literally.** Point fields are distributions. Localized observables should be smeared over regions.

**Pitfall 5: Confusing locality of a Lagrangian with microcausality.** A local Lagrangian is a route to microcausality in well-defined relativistic QFTs, but the structural condition is about observable algebras.

**Pitfall 6: Ignoring gauge subtleties.** Gauge potentials, ghost fields, and gauge-fixed variables are not always physical local observables. The causal statement belongs to gauge-invariant or BRST-invariant quantities.

## Relation to other topics

- [Equal-Time Commutators](/foundations/canonical-quantization/equal-time-commutators/) derives the scalar commutator and the Pauli–Jordan function.
- [Pauli–Jordan Function](/foundations/correlators-and-propagators/pauli-jordan-function/) gives the explicit causal commutator function.
- [Retarded and Advanced Propagators](/foundations/correlators-and-propagators/retarded-and-advanced-propagators/) separates causal response from time-ordered propagation.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) explains why the Feynman Green function need not vanish at spacelike separation.
- [Spin–Statistics Theorem](/foundations/symmetry-and-spacetime/spin-statistics/) uses locality as one of the structural assumptions behind the commutator-versus-anticommutator assignment.
- [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/) also relies on local relativistic field structure.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) and [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) explain why locality in gauge theory should be stated for physical observables.
- Later pages on unitarity, spectral condition, cluster decomposition, reflection positivity, analyticity, and axiomatic QFT will refine the structural assumptions used here.

## Research status

- **Established:** Microcausality, graded locality, retarded causal support, and the scalar Pauli–Jordan commutator are textbook-standard parts of local relativistic QFT.
- **Subtle:** Gauge theories, charged sectors, infrared dressings, curved spacetime, finite-density backgrounds, and effective nonlocal actions require careful statements of what counts as a local observable.
- **Active:** Algebraic QFT, perturbative algebraic QFT, celestial/infrared questions, quantum information in QFT, and locality in quantum gravity continue to sharpen what “locality” should mean beyond ordinary flat-spacetime QFT.

## Exercises

### Exercise 1: Spacelike scalar commutator

Let $\phi(x)$ be a Lorentz-scalar free field satisfying

$$
[\phi(t,\mathbf x),\phi(t,\mathbf y)]=0.
$$

Assume the commutator $[\phi(x),\phi(y)]$ is a Lorentz-invariant distribution depending only on $x-y$. Show that it vanishes for spacelike separated $x$ and $y$.

<details>
<summary><strong>Solution</strong></summary>

Let $z=x-y$. If $z^2<0$, then there exists a Lorentz frame in which $z^0=0$. In that frame,

$$
x^0=y^0,
$$

so the equal-time commutator gives

$$
[\phi(x),\phi(y)]=0.
$$

Because the commutator is Lorentz invariant, if it vanishes in one Lorentz frame, it vanishes in every Lorentz frame. Hence

$$
[\phi(x),\phi(y)]=0
\qquad (x-y)^2<0.
$$

</details>

### Exercise 2: Retarded response

For a scalar field, define the retarded propagator with qft.org’s convention

$$
G_R(x-y)=-\theta(x^0-y^0)\Delta(x-y),
$$

where $[\phi(x),\phi(y)]=i\Delta(x-y)$ and $\Delta(z)=0$ for spacelike $z$. Show that $G_R(x-y)$ vanishes unless $x$ lies in the future causal cone of $y$.

<details>
<summary><strong>Solution</strong></summary>

There are two ways for $G_R(x-y)$ to vanish.

If $x^0<y^0$, then

$$
\theta(x^0-y^0)=0.
$$

If $x^0>y^0$ but $x-y$ is spacelike, then

$$
\Delta(x-y)=0.
$$

The only remaining possibility is that $x^0\ge y^0$ and $x-y$ is timelike or null. That is precisely the future causal cone of $y$.

</details>

### Exercise 3: Feynman propagator versus commutator

Explain why a nonzero spacelike value of

$$
\langle 0|T\phi(x)\phi(y)|0\rangle
$$

does not violate microcausality.

<details>
<summary><strong>Solution</strong></summary>

Microcausality concerns commutators of local observables:

$$
[\phi(x),\phi(y)]=0
\qquad (x-y)^2<0.
$$

The Feynman propagator is a time-ordered vacuum correlator. It contains information about vacuum correlations and boundary conditions, not directly about the response of one local operation to another. The response is controlled by the commutator, or equivalently by the retarded propagator. Therefore the Feynman propagator can be nonzero at spacelike separation without permitting a signal.

</details>

### Exercise 4: Graded locality and even observables

Let $\psi(x)$ and $\chi(y)$ be fermionic fields with

$$
\{\psi(x),\chi(y)\}=0
$$

at spacelike separation. Explain why even bilinears made from fermions are bosonic local observables.

<details>
<summary><strong>Solution</strong></summary>

A fermionic field has odd Grassmann parity. A product of two fermionic fields has even parity. In the graded commutator,

$$
[A,B]_{\mathrm{gr}}=AB-(-1)^{|A||B|}BA,
$$

an even operator has $|A|=0$. Therefore the graded commutator of two even operators is the ordinary commutator.

Bilinears such as $\bar\psi\psi$ and $\bar\psi\gamma^\mu\psi$ are even. Under the usual locality assumptions, even local bilinears commute with other even local observables at spacelike separation.

</details>

### Exercise 5: Smearing and support

Let

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
\qquad
\phi(g)=\int d^4y\,g(y)\phi(y),
$$

where the supports of $f$ and $g$ are spacelike separated. Use point-field microcausality formally to show that

$$
[\phi(f),\phi(g)]=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
[\phi(f),\phi(g)]
=\int d^4x\,d^4y\,f(x)g(y)[\phi(x),\phi(y)].
$$

Whenever $f(x)g(y)$ is nonzero, $x$ and $y$ lie in spacelike separated supports. Therefore

$$
[\phi(x),\phi(y)]=0
$$

throughout the integration region. Hence the smeared commutator vanishes.

</details>

### Exercise 6: Locality of a composite scalar

Let $O(x)=:\phi^2(x):$ in a free scalar theory. Show formally that

$$
[O(x),\phi(y)]=0
$$

when $x$ and $y$ are spacelike separated.

<details>
<summary><strong>Solution</strong></summary>

Ignoring the short-distance issue that normal products should be treated as distributions, use the identity

$$
[AB,C]=A[B,C]+[A,C]B.
$$

Then

$$
[\phi(x)^2,\phi(y)]
=\phi(x)[\phi(x),\phi(y)]+[\phi(x),\phi(y)]\phi(x).
$$

At spacelike separation,

$$
[\phi(x),\phi(y)]=0,
$$

so both terms vanish. Normal ordering does not change this spacelike commutator. Thus $:\phi^2(x):$ is local with respect to $\phi(y)$.

</details>

## Sources and further reading

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 3, for the operational argument that spacelike separated observables must commute and for the construction of scalar quantum fields satisfying this requirement.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 4–5 and §10.7, for cluster decomposition, causal fields, antiparticles, and the spectral representation.
- M. Srednicki, *Quantum Field Theory*, §§3–4 and §13, for scalar-field commutators, spin–statistics, and the Lehmann–Källén form of the exact propagator.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the Wightman-axiom formulation of locality.
- R. Haag, *Local Quantum Physics*, for the algebraic QFT formulation in terms of local observable algebras.
- M. E. Peskin and D. V. Schroeder, *An Introduction to Quantum Field Theory*, §§2.3–2.4, for the scalar commutator and microcausality in a common particle-physics presentation.
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” for a modern algebraic view of locality in perturbation theory.

## Version history

- **2026-05-23:** Initial qft.org page on locality, local observable algebras, microcausality, graded commutativity, free scalar checks, causal response, gauge subtleties, path-integral interpretation, and exercises.
