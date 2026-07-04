---
title: "Unitarity Bounds"
description: "Derives the lower bounds on scaling dimensions in unitary CFTs from positivity of descendant norms in radial quantization."
sidebar:
  label: "Unitarity Bounds"
  order: 8
level: Graduate
status: "Polished draft"
source: "Mack 1977; Minwalla 1998; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - unitarity bounds
  - radial quantization
  - reflection positivity
  - conformal multiplets
  - null descendants
  - conserved currents
canonicalTopics:
  - unitarity-bounds
  - conformal-representation-theory
  - descendant-norms
  - shortening-conditions
  - reflection-positivity
researchStatus:
  established:
    - 'For unitary CFTs in $d\ge3$, scalar primaries obey $\Delta\ge(d-2)/2$ except for the identity, while symmetric-traceless spin-$\ell\ge1$ primaries obey $\Delta\ge\ell+d-2$.'
    - 'Saturation of a unitarity bound produces a null descendant, giving a shortening condition such as a free equation of motion or a conservation law.'
  active:
    - "The standard local-operator bounds are established; active work extends positivity constraints to spinning correlators, defects, supersymmetry, Lorentzian energy conditions, and numerical bootstrap systems."
---

## Summary

Unitarity bounds are lower bounds on the scaling dimensions of primary operators in a unitary CFT. They come from one simple demand: every state in radial quantization must have nonnegative norm.

A primary state satisfies

$$
D|\mathcal O\rangle=\Delta|\mathcal O\rangle,
\qquad
K_\mu|\mathcal O\rangle=0.
$$

Descendants are obtained by acting with $P_\mu$. Since radial Hermitian conjugation gives

$$
P_\mu^\dagger=K_\mu,
$$

the norm of every descendant can be computed using the conformal algebra. Positivity of those norms imposes lower bounds on $\Delta$.

For the most common representations in $d\ge3$:

| Primary type | Unitarity bound | Saturation means |
|---|---:|---|
| scalar, non-identity | $\Delta\ge\dfrac{d-2}{2}$ | free scalar equation $\partial^2\mathcal O=0$ |
| spinor | $\Delta\ge\dfrac{d-1}{2}$ | free Dirac equation |
| symmetric-traceless spin $\ell\ge1$ | $\Delta\ge\ell+d-2$ | conservation equation $\partial\cdot\mathcal O=0$ |

The identity operator is a special scalar with $\Delta=0$ and no nonzero descendants.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Unitarity bounds arise because descendant norms are computed from P dagger equals K and must be nonnegative.](/figures/cft-bootstrap/unitarity-bound-shortening.svg)

<figcaption>

In a unitary CFT, descendant norms are computed using $P_\mu^\dagger=K_\mu$. Below the bound a descendant has negative norm. At the bound a descendant becomes null, and the conformal multiplet shortens.

</figcaption>
</figure>

Unitarity bounds are one of the first places where the operator formalism becomes predictive. They tell us, before solving any dynamics, which operator dimensions are impossible in a unitary CFT.

## Prerequisites

You should know [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), [Scaling Dimensions and Spin](/cft-bootstrap/operators-states-radial-quantization/scaling-dimensions-and-spin/), and [Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/).

The derivations below use the radial-quantization commutators

$$
[D,P_\mu]=P_\mu,
\qquad
[D,K_\mu]=-K_\mu,
\qquad
[K_\mu,P_\nu]=2\delta_{\mu\nu}D-2M_{\mu\nu}.
$$

They also assume a positive-definite Hilbert-space inner product. Nonunitary CFTs, ghost sectors before imposing constraints, and logarithmic CFTs require separate treatment.

## Core idea

A conformal multiplet is generated from a primary by acting with $P_\mu$:

$$
|\mathcal O\rangle,
\qquad
P_\mu|\mathcal O\rangle,
\qquad
P_\mu P_\nu|\mathcal O\rangle,
\qquad
\ldots
$$

The primary itself can be normalized to have positive norm. The descendants are then not optional. If the representation is present in a unitary CFT, all of these descendant states must also have nonnegative norm.

Because $P_\mu^\dagger=K_\mu$, descendant norms reduce to matrix elements of commutators. For example,

$$
\langle P_\mu\mathcal O|P_\nu\mathcal O\rangle
=\langle\mathcal O|K_\mu P_\nu|\mathcal O\rangle.
$$

Since $K_\mu|\mathcal O\rangle=0$, this becomes

$$
\langle\mathcal O|[K_\mu,P_\nu]|\mathcal O\rangle.
$$

That expression depends only on $\Delta$ and the $SO(d)$ representation of $\mathcal O$. A negative eigenvalue in this descendant Gram matrix would be a negative-norm state. Therefore it is forbidden.

This is the representation-theoretic meaning of a unitarity bound.

## Setup and conventions

Let $\mathcal O$ be a primary transforming in an irreducible representation $\rho$ of the rotation group $SO(d)$, or its double cover when spinors are present. The state is

$$
|\mathcal O,a\rangle,
$$

where $a$ labels components in the spin representation. The defining primary conditions are

$$
K_\mu|\mathcal O,a\rangle=0,
\qquad
D|\mathcal O,a\rangle=\Delta|\mathcal O,a\rangle.
$$

The rotation generators act by matrices $\Sigma_{\mu\nu}^{(\rho)}$:

$$
M_{\mu\nu}|\mathcal O,a\rangle
=(\Sigma_{\mu\nu}^{(\rho)})_a{}^b|\mathcal O,b\rangle.
$$

At level one, the descendants transform in

$$
\text{vector}\otimes \rho.
$$

Different irreducible pieces of this tensor product can have different norms. The unitarity bound is the strongest condition obtained by requiring every piece to have nonnegative norm.

For symmetric-traceless tensors, the tight condition comes from the divergence descendant. For scalars, the tight condition comes one level later, from $P^2|\mathcal O\rangle$.

## Scalar primaries

Let $\mathcal O$ be a scalar primary. At level one,

$$
P_\mu|\mathcal O\rangle
$$

is a vector descendant. Its norm is

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=\sum_\mu\langle\mathcal O|K_\mu P_\mu|\mathcal O\rangle.
$$

Using $K_\mu|\mathcal O\rangle=0$ and $M_{\mu\nu}|\mathcal O\rangle=0$, we find

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=2d\Delta\,\langle\mathcal O|\mathcal O\rangle.
$$

Thus level-one positivity gives only

$$
\Delta\ge0.
$$

The sharper scalar bound comes from the level-two scalar descendant

$$
P^2|\mathcal O\rangle
\equiv P_\mu P_\mu|\mathcal O\rangle.
$$

A standard conformal-algebra computation gives

$$
\|P^2|\mathcal O\rangle\|^2
=8d\Delta\left(\Delta-\frac{d-2}{2}\right)
\langle\mathcal O|\mathcal O\rangle.
$$

For a non-identity scalar primary in a unitary theory, $\Delta>0$. Positivity then implies

$$
\Delta\ge\frac{d-2}{2}.
$$

At equality,

$$
P^2|\mathcal O\rangle=0,
$$

which is the state version of the operator equation

$$
\partial^2\mathcal O=0.
$$

Thus a scalar saturating the bound behaves like a free scalar field. This is not a vague analogy: the null descendant is precisely the free equation of motion in the conformal multiplet.

:::note[The identity exception]
The identity operator has $\Delta=0$ and all translation descendants vanish because $\partial_\mu\mathbf 1=0$. It is not constrained by the non-identity scalar bound.
:::

## Symmetric-traceless spin

Let $\mathcal O_{\mu_1\cdots\mu_\ell}$ be a symmetric-traceless primary with spin $\ell\ge1$. At level one, the descendants decompose schematically as

$$
P\otimes \mathcal O_\ell
\sim
\mathcal O_{\ell+1}
\oplus
\mathcal O_{\ell}
\oplus
\mathcal O_{\ell-1}.
$$

The most restrictive component is the spin-$\ell-1$ divergence descendant

$$
P^{\mu_1}|\mathcal O_{\mu_1\mu_2\cdots\mu_\ell}\rangle.
$$

Its norm is proportional to

$$
\Delta-\ell-d+2.
$$

Therefore positivity gives

$$
\Delta\ge\ell+d-2,\qquad \ell\ge1.
$$

At equality, the divergence descendant is null:

$$
P^{\mu_1}|\mathcal O_{\mu_1\mu_2\cdots\mu_\ell}\rangle=0.
$$

In operator language,

$$
\partial^{\mu_1}\mathcal O_{\mu_1\mu_2\cdots\mu_\ell}=0.
$$

Thus saturation means conservation.

Important cases are:

| Operator | Spin | Bound | Saturation |
|---|---:|---:|---|
| global symmetry current $J_\mu$ | $1$ | $\Delta\ge d-1$ | $\partial^\mu J_\mu=0$ |
| stress tensor $T_{\mu\nu}$ | $2$ | $\Delta\ge d$ | $\partial^\mu T_{\mu\nu}=0$ |
| higher-spin current $J_{\mu_1\cdots\mu_\ell}$ | $\ell$ | $\Delta\ge\ell+d-2$ | conserved higher-spin current |

The stress tensor of a local CFT has exactly $\Delta=d$ because it is conserved and generates spacetime symmetries. A global current has exactly $\Delta=d-1$ when it is conserved.

## Spinors

For the smallest spinor representation in $d\ge3$, the unitarity bound is

$$
\Delta\ge\frac{d-1}{2}.
$$

At equality, the gamma-trace descendant is null:

$$
\gamma^\mu P_\mu|\psi\rangle=0,
$$

or, in operator language,

$$
\gamma^\mu\partial_\mu\psi=0.
$$

This is the conformal free-fermion equation. As with the free scalar, saturation is a shortening condition.

The detailed classification of spinor and mixed-symmetry tensor bounds depends on the representation theory of $SO(d)$ or $Spin(d)$. The table above covers the representations most often used in introductory bootstrap and CFT applications.

## Two-dimensional comments

In two dimensions, global conformal symmetry factorizes into holomorphic and antiholomorphic parts. A primary is labeled by

$$
(h,\bar h),
\qquad
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

Global positivity gives

$$
h\ge0,
\qquad
\bar h\ge0.
$$

For the full Virasoro algebra, unitarity is more restrictive. The Virasoro descendant Gram matrices depend on the central charge $c$, and their positivity leads to the familiar unitary minimal-model series for $0<c<1$ and the broader $c\ge1$ unitary range with appropriate highest weights. That richer story belongs to [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) and [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/).

The lesson for this chapter is simple: the global bounds are the first layer; extended symmetry can impose more.

## What saturation means

A state with zero norm is called **null**. In a positive-definite Hilbert space, a null state is orthogonal to every state and must be quotiented out. Therefore saturation of a unitarity bound does not merely put an operator at a special numerical value of $\Delta$. It changes the representation.

The multiplet becomes shorter:

$$
\text{long multiplet}
\quad\xrightarrow{\Delta\to\Delta_\ast}\quad
\text{short multiplet}+\text{null submodule}.
$$

For scalars, the null descendant is $P^2|\mathcal O\rangle$, giving a free equation. For spin-$1$ currents, the null descendant is $P^\mu|J_\mu\rangle$, giving current conservation. For spin-$2$, it gives stress-tensor conservation.

This is why conservation laws and equations of motion are naturally described as shortening conditions in CFT.

## Free theories and higher-spin currents

A free scalar in $d>2$ has

$$
\Delta_\phi=\frac{d-2}{2},
$$

so it saturates the scalar bound. A free fermion has

$$
\Delta_\psi=\frac{d-1}{2},
$$

so it saturates the spinor bound.

Free CFTs also contain infinitely many conserved higher-spin currents. For example, schematically,

$$
J_{\mu_1\cdots\mu_\ell}
\sim
\phi\,\partial_{(\mu_1}\cdots\partial_{\mu_\ell)}\phi+\cdots
$$

has

$$
\Delta=\ell+d-2,
$$

and saturates the spin-$\ell$ bound. In interacting CFTs with $d>2$, the presence of an infinite tower of exactly conserved higher-spin currents is highly constraining and usually signals a free or generalized-free structure under appropriate assumptions. This is one reason higher-spin symmetry is a powerful diagnostic.

## Bootstrap significance

Unitarity bounds enter the conformal bootstrap in two ways.

First, they restrict the allowed operator spectrum. When writing a four-point function as a sum over conformal blocks, exchanged primaries must obey the appropriate bound for their spin and representation. A proposed spectrum containing a scalar with

$$
0<\Delta<\frac{d-2}{2}
$$

in a unitary $d\ge3$ CFT is immediately impossible.

Second, unitarity makes certain OPE contributions positive. For identical real scalar operators, the conformal-block decomposition has coefficients of the form

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This positivity is what turns crossing symmetry into a convex optimization problem in the numerical bootstrap. Without unitarity, crossing remains true but loses much of its inequality power.

Thus unitarity bounds are not just a representation-theory curiosity. They are part of the basic reason the bootstrap can exclude theories.

## Common pitfalls

**Applying the scalar bound to the identity.** The identity has $\Delta=0$ and is allowed. The bound $\Delta\ge(d-2)/2$ is for non-identity scalar primaries in $d>2$.

**Confusing engineering dimension with scaling dimension.** Unitarity bounds constrain exact CFT dimensions, not classical engineering dimensions away from a fixed point.

**Forgetting spin dependence.** A spin-$\ell$ primary has a different lower bound from a scalar. In $d\ge3$, symmetric-traceless spin $\ell\ge1$ requires $\Delta\ge\ell+d-2$.

**Thinking saturation is generic.** Saturating a bound is special. It produces a null descendant and usually a conservation law or free equation. Generic interacting operators lie strictly above the bound.

**Keeping null descendants as ordinary states.** In a unitary theory, null states are quotiented out. Including them as independent states overcounts the multiplet and corrupts conformal block decompositions.

**Using Euclidean group unitarity instead of radial Hilbert-space unitarity.** The relevant positivity is the Hilbert-space positivity obtained by radial quantization, not unitarity of representations of the noncompact Euclidean conformal group in the naive sense.

**Assuming nonunitary models obey the bounds.** They need not. Nonunitary CFTs can be extremely useful, especially in statistical physics, but they do not have a positive-definite radial Hilbert space.

## Relations to other pages

[Hermitian Conjugation in Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/hermitian-conjugation-in-radial-quantization/) explains why $P_\mu^\dagger=K_\mu$, the key input for descendant norms.

[Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) explains how descendants organize into multiplets and why null descendants form submodules.

[Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/) develops the saturation cases for currents, stress tensors, and shortening.

[Correlation Functions](/cft-bootstrap/correlation-functions/) uses unitarity bounds when listing allowed exchanged operators and positivity of two-point normalizations.

[Conformal Blocks](/cft-bootstrap/conformal-blocks/) uses the long or short multiplet structure to determine which descendants contribute to a block.

[Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) uses unitarity bounds and positive OPE coefficients as core assumptions in numerical bounds.

## Research status

The standard unitarity bounds for local primary operators are established. They can be derived from radial-quantization descendant norms, from positive-energy representations of the Lorentzian conformal group, or from positivity properties of two-point functions after analytic continuation.

Active work concerns stronger or more specialized positivity constraints. Examples include conformal collider bounds from averaged null energy, supersymmetric shortening and BPS bounds, defect and boundary unitarity bounds, mixed-symmetry tensor representations, and numerical bootstrap implementations for spinning systems.

The pages in this introductory chapter use only the standard local-operator bounds needed for ordinary CFT and bootstrap calculations.

## Exercises

### Exercise 1: Level-one scalar positivity

Let $|\mathcal O\rangle$ be a scalar primary of dimension $\Delta$ with unit norm. Show that

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2=2d\Delta.
$$

What bound follows?

<details><summary><strong>Solution</strong></summary>

Using $P_\mu^\dagger=K_\mu$,

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2
=\sum_\mu\langle\mathcal O|K_\mu P_\mu|\mathcal O\rangle.
$$

Because $K_\mu|\mathcal O\rangle=0$, this equals

$$
\sum_\mu\langle\mathcal O|[K_\mu,P_\mu]|\mathcal O\rangle.
$$

For a scalar, $M_{\mu\nu}|\mathcal O\rangle=0$, so

$$
[K_\mu,P_\mu]|\mathcal O\rangle=2D|\mathcal O\rangle=2\Delta|\mathcal O\rangle
$$

for each $\mu$. Summing over $d$ values of $\mu$ gives

$$
\sum_\mu\|P_\mu|\mathcal O\rangle\|^2=2d\Delta.
$$

Positivity gives $\Delta\ge0$. The stronger non-identity scalar bound comes from level two.

</details>

### Exercise 2: The scalar level-two bound

Assume the scalar level-two norm is

$$
\|P^2|\mathcal O\rangle\|^2
=8d\Delta\left(\Delta-\frac{d-2}{2}\right)
\langle\mathcal O|\mathcal O\rangle.
$$

Derive the non-identity scalar unitarity bound.

<details><summary><strong>Solution</strong></summary>

In a unitary theory, the norm must be nonnegative. For a non-identity scalar primary, $\Delta>0$. Therefore the factor $8d\Delta$ is positive, and positivity requires

$$
\Delta-\frac{d-2}{2}\ge0.
$$

Thus

$$
\Delta\ge\frac{d-2}{2}.
$$

At equality, $P^2|\mathcal O\rangle$ has zero norm and becomes a null descendant. In operator language this is $\partial^2\mathcal O=0$.

</details>

### Exercise 3: Current conservation from saturation

A spin-one primary $J_\mu$ in $d\ge3$ obeys

$$
\Delta_J\ge d-1.
$$

Explain why $\Delta_J=d-1$ implies a conservation equation.

<details><summary><strong>Solution</strong></summary>

For a spin-one primary, the tight level-one descendant is the divergence descendant

$$
P^\mu|J_\mu\rangle.
$$

Its norm is proportional to

$$
\Delta_J-d+1.
$$

At $\Delta_J=d-1$, this descendant has zero norm. In a unitary theory a zero-norm descendant is null and must be quotiented out. Therefore

$$
P^\mu|J_\mu\rangle=0.
$$

In operator language this is

$$
\partial^\mu J_\mu=0.
$$

So saturation of the spin-one unitarity bound is exactly current conservation.

</details>

### Exercise 4: Bounds in three dimensions

List the bounds for a scalar, a spinor, a spin-one current candidate, and a spin-two stress-tensor candidate in $d=3$.

<details><summary><strong>Solution</strong></summary>

For $d=3$:

$$
\Delta_{\rm scalar}\ge\frac{3-2}{2}=\frac12
$$

for non-identity scalars,

$$
\Delta_{\rm spinor}\ge\frac{3-1}{2}=1,
$$

for the smallest spinor representation,

$$
\Delta_{\ell=1}\ge1+3-2=2,
$$

for a spin-one symmetric-traceless primary, and

$$
\Delta_{\ell=2}\ge2+3-2=3
$$

for a spin-two symmetric-traceless primary. Saturation of the spin-one case gives a conserved current, and saturation of the spin-two case gives a conserved stress tensor.

</details>

## References

- Mack, “All unitary ray representations of the conformal group $SU(2,2)$ with positive energy.”
- Minwalla, “Restrictions imposed by superconformal invariance on quantum field theories.”
- Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*.
- Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap.”
- Poland, Rychkov, and Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications.”
- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, chapters 6 and 7.

## Version history

- 2026-06-27: First polished draft.
