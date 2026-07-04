---
title: "Euclidean Invariance"
description: "Explains Euclidean covariance of Schwinger functions, how to state it distributionally, and why it becomes Poincaré covariance after Osterwalder–Schrader reconstruction."
sidebar:
  label: "Euclidean Invariance"
  order: 5
level: Graduate
status: "Polished draft"
source: "Schwinger; Symanzik; Osterwalder–Schrader; Glimm–Jaffe; Simon."
topics:
  - Euclidean invariance
  - Schwinger functions
  - Osterwalder–Schrader axioms
  - Poincaré covariance
  - analytic continuation
canonicalTopics:
  - euclidean-invariance
  - osterwalder-schrader-qft
  - euclidean-quantum-field-theory
researchStatus:
  established:
    - "Euclidean invariance of suitable Schwinger functions is one of the Osterwalder–Schrader inputs that reconstruct Poincaré covariance in Lorentzian signature."
  active:
    - "For spinorial, gauge-fixed, curved-space, finite-temperature, and boundary theories, the correct replacement or weakening of Euclidean invariance depends on the framework."
---

## Summary

Euclidean invariance is the statement that Schwinger functions do not depend on where a Euclidean configuration is placed or how it is rotated. For a scalar field on $\mathbb R^d$, the Euclidean group is

$$
E(d)=\mathbb R^d\rtimes O(d),
\qquad
x\mapsto gx=Rx+a,
$$

and covariance means

$$
S_n(gx_1,\ldots,gx_n)=S_n(x_1,\ldots,x_n)
$$

in the sense of distributions.

This looks like an ordinary symmetry condition, but in the Osterwalder–Schrader framework it has a sharper role. Together with reflection positivity and the other OS assumptions, Euclidean translations and rotations become the positive-energy representation of the Poincaré group after reconstruction.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Euclidean transformations preserve scalar Schwinger functions](/figures/rigorous-qft/euclidean-invariance-action.svg)

<figcaption>

For scalar Schwinger functions, moving the whole Euclidean configuration by $g=(R,a)\in E(d)$ leaves the distribution unchanged. For fields with spin or tensor indices, the same statement includes representation matrices acting on the indices.

</figcaption>
</figure>

The main caveat is that Euclidean invariance is not enough. A Euclidean-invariant family of distributions can still fail to define a unitary Lorentzian QFT. The missing condition is reflection positivity, and the constructive problem is to prove all axioms for the desired continuum limit.

## Prerequisites

Read [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/), and [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) first. The Lorentzian comparison uses [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) and [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/).

This page treats flat Euclidean space and scalar Schwinger functions first. Spin, gauge symmetry, curved backgrounds, and finite-temperature compact Euclidean time are mentioned only as caveats.

## Logical status

| Item | Status |
|---|---|
| Page type | Definition and bridge page. |
| Framework | Scalar Osterwalder–Schrader QFT on flat $\mathbb R^d$. |
| Main symmetry | Euclidean translations and rotations, $E(d)=\mathbb R^d\rtimes O(d)$. |
| Main output | Distributional covariance conditions and their role in reconstructing Poincaré covariance. |
| Main caveat | Euclidean invariance does not imply reflection positivity or existence of a continuum model. |

## Core idea

Euclidean QFT replaces Minkowski spacetime by $\mathbb R^d$ with positive-definite metric. The symmetry group preserving this metric is the Euclidean group. If $S_n$ is an ordinary scalar function away from coincident points, Euclidean invariance says that $S_n$ is unchanged under simultaneous Euclidean transformations of all insertions.

For example, translation invariance gives

$$
S_n(x_1+a,\ldots,x_n+a)=S_n(x_1,\ldots,x_n),
$$

so $S_n$ depends only on relative positions. Rotation invariance gives

$$
S_n(Rx_1,\ldots,Rx_n)=S_n(x_1,\ldots,x_n),
\qquad R\in O(d).
$$

For a two-point scalar function, these two conditions force the ordinary-function form

$$
S_2(x,y)=C(x-y),
\qquad
C(Rz)=C(z).
$$

Thus, away from singularities and assuming enough regularity,

$$
S_2(x,y)=F(|x-y|).
$$

In rigorous QFT, however, the displayed equations are shorthand. Schwinger functions are distributions, so the invariant statement must be made after smearing.

## Setup and conventions

Write a Euclidean point as

$$
x=(\tau,\mathbf x)\in\mathbb R\times\mathbb R^{d-1}.
$$

The Euclidean inner product is

$$
x\cdot_E y=\tau\sigma+\mathbf x\cdot\mathbf y,
\qquad
|x|^2=x\cdot_E x.
$$

The Euclidean group element $g=(a,R)$ acts by

$$
g x=Rx+a,
\qquad
R\in O(d),\quad a\in\mathbb R^d.
$$

For a test function $f\in\mathcal S((\mathbb R^d)^n)$, define the pulled-back test function

$$
(g\cdot f)(x_1,\ldots,x_n)
=
f(g^{-1}x_1,\ldots,g^{-1}x_n).
$$

A scalar Schwinger distribution is Euclidean invariant when

$$
\langle S_n,g\cdot f\rangle
=
\langle S_n,f\rangle
$$

for every test function $f$ and every $g\in E(d)$. This is the clean distributional version of

$$
S_n(gx_1,\ldots,gx_n)=S_n(x_1,\ldots,x_n).
$$

The determinant of $R$ is $\pm1$, but $d^dx$ is preserved in absolute value. For scalar bosonic Schwinger functions on flat space, no orientation choice is needed unless pseudoscalar or parity-odd insertions are present.

## Distributional covariance

The pointwise formula for $S_n$ can be misleading because the most important singularities occur at coincident points. For instance, the free Euclidean scalar covariance in $d\ge2$ has a short-distance singularity and should be treated as a distribution.

Distributional covariance says that the value of the distribution on a test configuration is unchanged when the test configuration is moved oppositely. For one distribution $S\in\mathcal S'((\mathbb R^d)^n)$, the transformed distribution $gS$ is defined by

$$
\langle gS,f\rangle
=
\langle S,g^{-1}\cdot f\rangle.
$$

Invariance is the fixed-point condition

$$
gS_n=S_n.
$$

This matters in renormalized theories. Local counterterms supported on diagonals, such as derivatives of delta functions at coincident points, must also transform covariantly. A formula that is invariant away from coincident points may still fail to define an invariant distribution until its extension to the diagonal is chosen correctly.

## Fields with indices

For tensor or spin fields, Euclidean invariance becomes covariance. Suppose fields carry indices $\alpha$ and transform in a finite-dimensional representation $D(R)$. Then the $n$-point Schwinger distribution has components

$$
S_{\alpha_1\ldots\alpha_n}(x_1,\ldots,x_n)
=
\langle\phi_{\alpha_1}(x_1)\cdots
\phi_{\alpha_n}(x_n)\rangle_E.
$$

The scalar equation is replaced by

$$
\begin{aligned}
&S_{\alpha_1\ldots\alpha_n}(Rx_1+a,\ldots,Rx_n+a)
\\
&\quad=
D(R)_{\alpha_1}{}^{\beta_1}\cdots
D(R)_{\alpha_n}{}^{\beta_n}
S_{\beta_1\ldots\beta_n}(x_1,\ldots,x_n).
\end{aligned}
$$

For spinorial fields one normally works with the double cover $\operatorname{Spin}(d)$ rather than $SO(d)$ itself. Fermionic Schwinger functions also carry graded symmetry signs. Gauge theories add another layer: gauge-variant fields in a gauge-fixed presentation need not obey a positivity-friendly covariance statement, while gauge-invariant observables should transform geometrically.

The scalar case is therefore the clean model, not the universal template.

## Consequences for two-point functions

Translation invariance implies that a scalar two-point Schwinger function has the form

$$
S_2(x,y)=C(x-y)
$$

as a distribution. Rotation invariance implies $C(Rz)=C(z)$. In momentum space this becomes

$$
\widetilde C(Rp)=\widetilde C(p).
$$

For the massive free scalar field,

$$
\widetilde C(p)=\frac{1}{p_E^2+m^2},
\qquad
p_E^2=p_0^2+\mathbf p^2,
$$

so the position-space covariance is

$$
C(x)=
\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot_E x}}{p_E^2+m^2}.
$$

The denominator depends only on $p_E^2$, and the measure is rotation invariant, so $C(Rx)=C(x)$.

For interacting scalar theories, Euclidean invariance constrains the tensorial structure and dependence on distances but does not determine the functions. Dynamics still lives in the allowed invariant distributions.

## Time reflection and the positive-time cut

The OS framework chooses a Euclidean time coordinate and the reflection

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

This reflection is an element of $O(d)$, so Euclidean invariance implies

$$
S_n(\theta x_1,\ldots,\theta x_n)
=
S_n(x_1,\ldots,x_n)
$$

for scalar fields. But reflection invariance is not reflection positivity.

Reflection invariance is a symmetry equation. Reflection positivity is the inequality

$$
\langle\Theta F\,F\rangle_E\ge0
$$

for positive-time Euclidean observables $F$. The first says the distribution is unchanged by a reflection. The second says that a reflected bra paired with a positive-time ket gives a nonnegative norm square.

This distinction is one of the most common sources of confusion in Euclidean QFT.

## From Euclidean invariance to Poincaré covariance

After OS reconstruction, not every Euclidean transformation acts in the same way.

Spatial translations and spatial rotations preserve the positive-time half-space. They therefore act directly on the reconstructed Hilbert space by unitary operators. Positive Euclidean time translations preserve the half-space only as a semigroup, giving

$$
T(\tau)=e^{-\tau H},
\qquad
\tau\ge0,
$$

with $H\ge0$ after reflection positivity.

Euclidean rotations mixing $\tau$ with a spatial coordinate do not preserve the positive-time half-space globally. They are not simply unitary rotations on the reconstructed Hilbert space. Instead, their analytic continuation gives Lorentz boosts.

In the $(\tau,x^1)$ plane, a Euclidean rotation is

$$
\begin{pmatrix}
\tau'\\ x^{1\prime}
\end{pmatrix}
=
\begin{pmatrix}
\cos\alpha&-\sin\alpha\\
\sin\alpha&\cos\alpha
\end{pmatrix}
\begin{pmatrix}
\tau\\ x^1
\end{pmatrix}.
$$

With $t=-i\tau$ and $\alpha=i\eta$, this becomes a Lorentz boost with rapidity $\eta$. This is the geometric reason that Euclidean $O(d)$ covariance is the Euclidean shadow of Lorentz covariance.

The actual theorem is not the slogan "rotate the angle to imaginary values". The theorem requires the OS axioms, analytic continuation, and the reconstructed Hilbert-space representation.

## How to check Euclidean invariance

For a proposed Schwinger family, the practical checks are:

| Object | Check |
|---|---|
| Position-space distributions | Test against $f$ and verify $\langle S_n,g\cdot f\rangle=\langle S_n,f\rangle$. |
| Momentum-space two-point functions | Verify dependence on $p_E^2$ for scalar fields. |
| Momentum-space $n$-point functions | Verify momentum conservation and rotation-covariant dependence on scalar products $p_i\cdot_E p_j$. |
| Local counterterms | Verify that extensions to coincident diagonals are invariant or covariant. |
| Indexed fields | Include the correct $O(d)$, $SO(d)$, or $\operatorname{Spin}(d)$ representation matrices. |
| Regulated theories | Check whether the regulator preserves the relevant Euclidean subgroup. |

A lattice regulator, for example, usually preserves only a discrete subgroup of $E(d)$ at nonzero lattice spacing. Full Euclidean invariance is expected only in the continuum scaling limit, and proving that restoration can be a serious part of the construction.

## Common pitfalls

**Confusing Euclidean invariance with reflection positivity.** Invariance is an equality. Reflection positivity is an inequality that produces a Hilbert-space inner product.

**Forgetting distributional extensions.** Invariance away from coincident points does not automatically determine a covariant extension to coincident points.

**Using scalar formulas for spin fields.** Vector, tensor, and spinor Schwinger functions transform with representation matrices.

**Assuming a regulator preserves the continuum symmetry.** Momentum cutoffs, lattice cutoffs, gauge choices, and higher-derivative regulators can preserve, break, or obscure Euclidean invariance.

**Treating Euclidean rotations as Lorentz transformations before reconstruction.** The continuation from $O(d)$ to the Lorentz group is part of the OS/Wightman analytic structure, not a purely formal change of letters.

**Expecting Euclidean invariance to determine dynamics.** It strongly constrains correlation functions, but many inequivalent invariant Schwinger families can exist.

## Relations to other pages

[Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) lists Euclidean covariance as one item in the full axiom package. [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) explains the positivity condition that Euclidean invariance cannot replace. [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains how Euclidean covariance becomes Poincaré covariance.

From the Lorentzian side, [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) gives the Wightman version of the same symmetry principle.

## Research status

For scalar models in the OS framework, Euclidean invariance is a standard and settled axiom. In constructive work, the hard issue is proving that a limiting Schwinger family exists and retains the symmetry after removing cutoffs.

Several important variants require more care. Lattice theories may only have discrete rotational symmetry before the continuum limit. Gauge-fixed theories may hide positivity and covariance. Fermionic theories require graded transformation laws. Curved-space and finite-temperature theories replace global Euclidean invariance by covariance under the relevant geometric symmetries.

## Exercises

### Exercise 1. Translation and rotation invariance of a two-point function

Assume $S_2(x,y)$ is an ordinary scalar function on $\mathbb R^d\times\mathbb R^d$, away from coincident points. Show that translation invariance and rotation invariance imply

$$
S_2(x,y)=F(|x-y|)
$$

for some one-variable function $F$, at least on each connected region where the ordinary function is defined.

<details><summary><strong>Solution</strong></summary>

Translation invariance gives

$$
S_2(x+a,y+a)=S_2(x,y).
$$

Choose $a=-y$. Then

$$
S_2(x,y)=S_2(x-y,0).
$$

Define $C(z)=S_2(z,0)$. Rotation invariance gives

$$
C(Rz)=S_2(Rz,0)=S_2(Rz,R0)=S_2(z,0)=C(z).
$$

The rotation group acts transitively on spheres $|z|=r$, so $C(z)$ depends only on $|z|$. Thus $C(z)=F(|z|)$ and $S_2(x,y)=F(|x-y|)$.

</details>

### Exercise 2. Free covariance in momentum space

Let

$$
C(x)=
\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot_E x}}{p_E^2+m^2}.
$$

Show that $C(Rx)=C(x)$ for $R\in O(d)$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
C(Rx)=
\int\frac{d^dp}{(2\pi)^d}
\frac{e^{ip\cdot_E Rx}}{p_E^2+m^2}.
$$

Since $R$ is orthogonal, $p\cdot_E Rx=(R^{-1}p)\cdot_E x$ and $p_E^2=(R^{-1}p)_E^2$. Change variables $q=R^{-1}p$. The Euclidean measure is unchanged, $d^dp=d^dq$. Hence

$$
C(Rx)=
\int\frac{d^dq}{(2\pi)^d}
\frac{e^{iq\cdot_E x}}{q_E^2+m^2}
=C(x).
$$

</details>

### Exercise 3. Why positive Euclidean time gives a semigroup

Explain why translations by $\tau\ge0$ in the Euclidean time direction act as a semigroup, not a full group, on positive-time test functions.

<details><summary><strong>Solution</strong></summary>

A positive-time test function is supported in $\tau>0$. If we translate it forward by $s\ge0$, its support remains in $\tau>0$. Therefore forward Euclidean time translations act on the positive-time algebra.

A negative translation can move support across the time-zero plane. It is not defined on the positive-time algebra without restricting the support or changing the domain. Thus the directly reconstructed time evolution is a semigroup $T(s)$ for $s\ge0$.

Reflection positivity then makes this semigroup a contraction semigroup on the Hilbert space, and the reconstruction theorem writes it as $T(s)=e^{-sH}$ with $H\ge0$.

</details>

## References

- J. Schwinger, "On the Euclidean Structure of Relativistic Field Theory," *Proceedings of the National Academy of Sciences* **44** (1958), 956–965. DOI: [10.1073/pnas.44.9.956](https://doi.org/10.1073/pnas.44.9.956).
- K. Symanzik, "Euclidean Quantum Field Theory. I. Equations for a Scalar Model," *Journal of Mathematical Physics* **7** (1966), 510–525. DOI: [10.1063/1.1704960](https://doi.org/10.1063/1.1704960).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.

## Version history

- **2026-06-28:** Initial polished draft.
