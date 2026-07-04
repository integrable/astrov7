---
title: "Logarithmic CFT Preview"
description: "Preview of logarithmic conformal field theories, where dilatations can act non-diagonalizably and correlation functions can contain logarithms."
sidebar:
  label: "Logarithmic CFT Preview"
  order: 12
level: Advanced
status: "Polished draft"
source: "Gurarie 1993; Di Francesco–Mathieu–Sénéchal 1997; Gaberdiel 2003; Flohr 2003"
topics:
  - two-dimensional CFT
  - logarithmic CFT
  - Virasoro representations
  - nonunitary CFT
  - indecomposable modules
canonicalTopics:
  - logarithmic-cft
  - indecomposable-representations
  - virasoro-representation-theory
researchStatus:
  established:
    - "Logarithmic conformal field theories are established examples of conformal theories whose symmetry representations need not decompose into ordinary highest-weight irreducibles."
  active:
    - "The systematic classification, modular behavior, tensor-categorical structure, and higher-dimensional analogues of logarithmic theories remain active research areas."
---

## Summary

A **logarithmic conformal field theory** is a conformal field theory in which the dilatation operator can act non-diagonalizably on some sectors. In ordinary diagonal CFT language, local operators have definite scaling dimensions and correlators are built from powers such as $|x|^{-2\Delta}$. In a logarithmic CFT, some operators form Jordan blocks, and correlators can contain powers times logarithms.

The simplest rank-two logarithmic pair consists of operators $C$ and $D$ with the same chiral weight $h$ and

$$
L_0 |C\rangle = h |C\rangle,
\qquad
L_0 |D\rangle = h |D\rangle + |C\rangle.
$$

Equivalently, in this two-dimensional subspace,

$$
L_0 = h\mathbf 1 + N,
\qquad
N^2=0,
\qquad
N|D\rangle=|C\rangle,
\qquad
N|C\rangle=0.
$$

This nilpotent part is the source of logarithms. A standard two-point normalization is

$$
\langle C(z)C(0)\rangle=0,
\qquad
\langle C(z)D(0)\rangle=\frac{b}{z^{2h}},
$$

and

$$
\langle D(z)D(0)\rangle=\frac{a-2b\log(\mu z)}{z^{2h}}.
$$

The scale $\mu$ only makes the logarithm dimensionless; changing it can be absorbed into the constant $a$. The coefficient $b$ is the invariant logarithmic coupling of the rank-two pair.

This page is a preview. The main two-dimensional CFT spine develops the semisimple Virasoro examples first. Logarithmic theories are indispensable for percolation, polymers, ghost systems, symplectic fermions, some disorder problems, and many nonunitary statistical systems, but they require extra care because the usual positive-definite Hilbert-space intuition breaks.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A logarithmic pair as a rank-two Jordan block for $L_0$.](/figures/cft-bootstrap/logarithmic-jordan-pair.svg)

<figcaption>

A rank-two logarithmic pair. The nilpotent part of $L_0$ maps $D$ to $C$, so scaling transformations mix $D$ with $C$ and produce logarithms in correlators.

</figcaption>
</figure>

## Prerequisites

You should know [Complex Coordinates](/cft-bootstrap/two-dimensional-cft/complex-coordinates/), [Local Conformal Transformations](/cft-bootstrap/two-dimensional-cft/local-conformal-transformations/), [Stress Tensor in 2D](/cft-bootstrap/two-dimensional-cft/stress-tensor-in-2d/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

For orientation inside the broader volume, it helps to have read [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), and [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/).

## Core idea

The ordinary slogan says that a primary field has a scaling dimension. A logarithmic CFT teaches a more precise lesson: the dilatation operator must act on the space of local states, and it need not always be diagonalizable.

If $L_0$ is diagonalizable, one can choose states $|\mathcal O\rangle$ with

$$
L_0|\mathcal O\rangle = h|\mathcal O\rangle.
$$

Then scaling produces powers. If $L_0$ has a Jordan block, then exponentiating $L_0$ produces powers times polynomials in $\log \lambda$. For the rank-two block above,

$$
e^{aL_0}|D\rangle
= e^{ah}\bigl(|D\rangle+a|C\rangle\bigr).
$$

The logarithm in position-space correlators is the same mathematics in disguise. Since $a=\log \lambda$, scaling does not merely multiply $D$ by a power. It also shifts it by $C$.

:::note[The word “logarithmic”]
The theory is still conformally covariant. The logarithm does not mean that conformal symmetry has failed. It means that conformal symmetry is represented nonsemisimply.
:::

## Setup and conventions

We work on the Euclidean complex plane with

$$
z=x^1+i x^2,
\qquad
\bar z=x^1-i x^2.
$$

For simplicity, the formulas below focus on a chiral rank-two pair. A nonchiral logarithmic pair can have the same phenomenon in the holomorphic sector, the antiholomorphic sector, or both.

The stress-tensor OPEs of a chiral logarithmic pair are

$$
T(z)C(0)
\sim
\frac{h C(0)}{z^2}+\frac{\partial C(0)}{z},
$$

and

$$
T(z)D(0)
\sim
\frac{hD(0)+C(0)}{z^2}+\frac{\partial D(0)}{z}.
$$

The extra $C(0)/z^2$ term says that $D$ is not an eigenoperator of $L_0$. Acting with the contour mode

$$
L_0=\oint_0\frac{dz}{2\pi i}\,zT(z)
$$

reproduces

$$
L_0 |D\rangle = h|D\rangle + |C\rangle.
$$

The rank-two example is not the most general case. Higher-rank Jordan blocks can occur, and logarithmic theories often include indecomposable modules that are not simply one Jordan block at the primary level.

## Why logarithms appear

A quick way to see why logarithms are natural is to imagine two dimensions colliding. Suppose a family of ordinary power laws contains

$$
\frac{1}{z^{2(h+\epsilon)}}
=\frac{1}{z^{2h}}e^{-2\epsilon\log z}.
$$

Expanding near $\epsilon=0$ gives

$$
\frac{1}{z^{2(h+\epsilon)}}
=
\frac{1}{z^{2h}}
\left(1-2\epsilon\log z+O(\epsilon^2)\right).
$$

Thus the derivative of a power law with respect to a scaling dimension is a logarithmic power law:

$$
\lim_{\epsilon\to 0}
\frac{z^{-2(h+\epsilon)}-z^{-2h}}{\epsilon}
=
-2\frac{\log z}{z^{2h}}.
$$

This does not prove that every logarithmic CFT is a collision limit of ordinary CFTs, but it gives the right intuition. Logarithms appear when the scaling problem becomes non-diagonal.

## Two-point functions of a logarithmic pair

The rank-two two-point functions are fixed by conformal covariance up to constants. With the canonical choice

$$
\langle C(z)C(0)\rangle=0,
$$

one obtains

$$
\langle C(z)D(0)\rangle=\frac{b}{z^{2h}},
$$

and

$$
\langle D(z)D(0)\rangle
=
\frac{a-2b\log(\mu z)}{z^{2h}}.
$$

The constant $a$ is not invariant. A change of logarithmic partner,

$$
D\longmapsto D+\alpha C,
$$

changes

$$
a\longmapsto a+2\alpha b,
$$

while $b$ is unchanged. If $b\neq 0$, one can often set $a$ to a convenient value by shifting $D$. The real physical warning is that the two-point “metric” on states is not positive definite. Indeed, $C$ is a null state in the two-point pairing but need not decouple from the theory.

In a nonchiral spinless notation, the same structure often appears as

$$
\langle C(x)D(0)\rangle=\frac{b}{|x|^{2\Delta}},
$$

and

$$
\langle D(x)D(0)\rangle
=
\frac{a-2b\log(\mu |x|)}{|x|^{2\Delta}}.
$$

The logarithm is universal only up to the basis choices just described.

## OPEs and indecomposable modules

In a semisimple rational CFT, a fusion product decomposes into a direct sum of irreducible representations. In a logarithmic CFT, fusion can produce **indecomposable** representations: representations that are not irreducible, but also cannot be split as a direct sum of irreducibles.

Schematically, an OPE may have the form

$$
\mathcal O_i(z)\mathcal O_j(0)
\sim
\cdots
+
\lambda_{ijC}\,z^{h-h_i-h_j}C(0)
+
\lambda_{ijD}\,z^{h-h_i-h_j}
\left(D(0)+\gamma\log z\,C(0)\right)
+\cdots.
$$

The logarithm is not an optional decoration. It is required so that the OPE transforms correctly under $L_0$ when $C$ and $D$ form a Jordan block.

This is why logarithmic theories are a representation-theoretic enlargement of ordinary CFT, not merely a collection of unusual correlators.

## Examples and physical habitats

The best first examples are not unitary particle theories. They usually arise from statistical systems, gauge-fixed systems, or systems with cancellations between bosonic and fermionic degrees of freedom.

| Habitat | What logarithms signal |
|---|---|
| Symplectic fermions | A basic $c=-2$ logarithmic theory with indecomposable Virasoro modules. |
| Logarithmic minimal models | Minimal-model-like spectra can be enlarged by indecomposable modules. |
| Ghost systems | Nonunitary degrees of freedom can produce null states that do not decouple. |
| Percolation and polymers | Critical statistical models with $c=0$ or related nonunitary structure. |
| Disordered systems | Replica or supersymmetric formulations can lead to logarithmic sectors. |
| WZW and supergroup models | Nonsemisimple representation categories naturally appear in some cases. |

The lesson is not that logarithmic CFTs are pathological. The lesson is that “CFT” is broader than “unitary diagonalizable Hilbert space built from irreducible modules.”

## What changes in bootstrap language

The usual bootstrap spine still matters:

$$
\text{OPE} + \text{crossing} + \text{conformal symmetry}.
$$

But several familiar simplifications must be modified.

First, the expansion into conformal blocks can involve logarithmic blocks or derivatives of ordinary blocks with respect to conformal weights. This is the block version of the collision-limit intuition.

Second, OPE coefficients no longer enter only as manifestly nonnegative squares. Ordinary reflection positivity is absent in nonunitary logarithmic theories, so the linear-functional logic of the unitary numerical bootstrap does not apply without major changes.

Third, “fusion rules” may not mean simple multiplicities of irreducible modules. They can encode extensions between modules. A notation that is perfectly adequate for semisimple minimal models may lose information in logarithmic models.

Fourth, modular behavior can require generalized characters, pseudocharacters, or enlarged spaces of torus amplitudes. The phrase “modular invariant partition function” remains meaningful, but it is no longer the whole representation-theoretic story.

## Common pitfalls

**Mistaking logarithms for explicit scale breaking.** A logarithm in a correlator can coexist with exact scale covariance if operators mix under dilatations.

**Assuming every null state decouples.** In a unitary CFT, a zero-norm state decouples from all correlators. In logarithmic theories, null states can pair with logarithmic partners and remain physically visible.

**Treating $D$ as an ordinary primary.** The partner $D$ is not an eigenoperator of $L_0$. Its stress-tensor OPE contains the extra $C/z^2$ term.

**Forgetting basis dependence.** The constant term in $\langle DD\rangle$ changes under $D\to D+\alpha C$. The coefficient of the logarithm is the more invariant datum.

**Using unitary bootstrap positivity blindly.** Logarithmic theories are typically nonunitary in the positive-definite radial-quantization sense. Positivity constraints must be replaced by whatever consistency conditions the theory actually has.

## Relations to other pages

This page extends [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/) by allowing nonsemisimple representations.

The [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/) chapter develops the ordinary Virasoro algebra, highest-weight modules, null states, and Ward identities. Logarithmic CFT reuses the same Virasoro algebra but changes the representation theory.

The [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/) chapter mostly studies semisimple rational examples. Logarithmic theories are a warning that rational-looking modular data and finitely many fields do not automatically imply semisimplicity.

The [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) chapter explains why crossing is the associativity of the OPE. Logarithmic CFT keeps this principle but relaxes the positivity assumptions used in unitary bootstrap applications.

## Research status

Logarithmic CFT is a mature subject in two dimensions, with well-developed examples and a rich representation theory. The best-understood cases include symplectic fermions, triplet models, ghost systems, and logarithmic structures in critical statistical models.

At the same time, logarithmic CFT is not as uniformly packaged as semisimple rational CFT. Classification questions, modular tensor-category analogues, boundary conditions, defects, and higher-dimensional versions remain active. In modern language, the hard part is not merely writing correlators with logarithms; it is controlling the nonsemisimple category of local and extended operators.

For this volume, the practical rule is simple: use ordinary Virasoro and bootstrap pages as the main route, and return to logarithmic CFT when null states, nonunitarity, disorder, percolation, polymers, ghosts, or supergroups force nonsemisimple representation theory onto the stage.

## Exercises

### Exponentiating a Jordan block

Let

$$
L_0=h\mathbf 1+N,
\qquad
N^2=0,
\qquad
N|D\rangle=|C\rangle,
\qquad
N|C\rangle=0.
$$

Show that

$$
e^{aL_0}|D\rangle
=e^{ah}\bigl(|D\rangle+a|C\rangle\bigr).
$$

<details><summary><strong>Solution</strong></summary>

Since $h\mathbf 1$ commutes with $N$,

$$
e^{aL_0}=e^{a(h\mathbf 1+N)}=e^{ah}e^{aN}.
$$

Because $N^2=0$,

$$
e^{aN}=\mathbf 1+aN.
$$

Therefore

$$
e^{aL_0}|D\rangle
=e^{ah}(\mathbf 1+aN)|D\rangle
=e^{ah}\bigl(|D\rangle+a|C\rangle\bigr).
$$

</details>

### Logs from colliding powers

Evaluate

$$
\lim_{\epsilon\to 0}
\frac{|x|^{-2(\Delta+\epsilon)}-|x|^{-2\Delta}}{\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
|x|^{-2(\Delta+\epsilon)}
=|x|^{-2\Delta}e^{-2\epsilon\log |x|}.
$$

Expanding the exponential,

$$
|x|^{-2(\Delta+\epsilon)}
=|x|^{-2\Delta}\left(1-2\epsilon\log |x|+O(\epsilon^2)\right).
$$

Thus

$$
\lim_{\epsilon\to 0}
\frac{|x|^{-2(\Delta+\epsilon)}-|x|^{-2\Delta}}{\epsilon}
=-2|x|^{-2\Delta}\log |x|.
$$

This is the simplest mechanism by which logarithmic power laws arise from degenerating scaling dimensions.

</details>

### Basis dependence of the constant term

Assume

$$
\langle C(z)C(0)\rangle=0,
\qquad
\langle C(z)D(0)\rangle=\frac{b}{z^{2h}},
$$

and

$$
\langle D(z)D(0)\rangle
=\frac{a-2b\log(\mu z)}{z^{2h}}.
$$

Let $D'=D+\alpha C$. Find $\langle D'(z)D'(0)\rangle$.

<details><summary><strong>Solution</strong></summary>

We compute

$$
\langle D'(z)D'(0)\rangle
=
\langle D(z)D(0)\rangle
+\alpha\langle C(z)D(0)\rangle
+\alpha\langle D(z)C(0)\rangle
+\alpha^2\langle C(z)C(0)\rangle.
$$

Using the stated two-point functions gives

$$
\langle D'(z)D'(0)\rangle
=
\frac{a+2\alpha b-2b\log(\mu z)}{z^{2h}}.
$$

So $b$ is unchanged, while

$$
a\longmapsto a+2\alpha b.
$$

</details>

## References

- V. Gurarie, “Logarithmic Operators in Conformal Field Theory,” *Nuclear Physics B* **410** (1993).
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the operator formalism, Virasoro representation theory, free-field examples, and minimal-model chapters.
- M. R. Gaberdiel, “An Algebraic Approach to Logarithmic Conformal Field Theory,” *International Journal of Modern Physics A* **18** (2003).
- M. Flohr, “Bits and Pieces in Logarithmic Conformal Field Theory,” *International Journal of Modern Physics A* **18** (2003).
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, for critical phenomena background and nonunitary statistical systems.

## Version history

- 2026-06-28: First polished draft. Added rank-two logarithmic pairs, two-point functions, stress-tensor OPEs, examples, bootstrap caveats, exercises, and a Jordan-block figure.
