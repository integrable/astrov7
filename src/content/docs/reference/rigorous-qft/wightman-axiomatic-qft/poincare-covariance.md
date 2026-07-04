---
title: "Poincaré Covariance"
description: "Explains how spacetime symmetry is represented on states, fields, test functions, and Wightman functions in the Wightman framework."
sidebar:
  label: "Poincaré Covariance"
  order: 3
level: Graduate
status: "Polished draft"
source: "Wigner; Bargmann; Wightman; Streater–Wightman; Weinberg; Haag."
topics:
  - Poincaré covariance
  - Wightman fields
  - unitary representations
  - Lorentz symmetry
  - Wightman functions
canonicalTopics:
  - poincare-covariance
  - wightman-axioms
  - relativistic-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Poincaré covariance in Wightman QFT is formulated by a strongly continuous unitary representation on the Hilbert space together with an intertwining law for smeared fields."
    - "For point fields with spin, covariance requires finite-dimensional Lorentz representation matrices in addition to the unitary representation on states."
  active:
    - "Massless representations, gauge potentials, infrared sectors, and curved-spacetime generalizations require careful modifications of the simplest Wightman covariance picture."
---

## Summary

Poincaré covariance is the statement that spacetime symmetry is implemented consistently on all parts of a Wightman theory: spacetime points, test functions, Hilbert-space states, fields, and vacuum correlation functions.

For a Poincaré transformation

$$
g=(a,\Lambda),
\qquad
x\mapsto gx=\Lambda x+a,
$$

the Wightman framework uses a strongly continuous unitary representation $U(g)$ on the Hilbert space and a field covariance law. For scalar fields, in the convention used here,

$$
U(g)\phi(f)U(g)^{-1}=\phi(f_g),
\qquad
f_g(x)=f(g^{-1}x).
$$

For fields with spin or tensor indices, one inserts a finite-dimensional Lorentz representation:

$$
U(g)\phi_i(f)U(g)^{-1}
=
\sum_j S_i{}^j(\Lambda^{-1})\phi_j(f_g).
$$

The important point is that covariance is not a slogan saying that formulas “look Lorentz invariant.” It is an intertwining condition between geometry and Hilbert-space operators.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Poincaré covariance as a commutative square](/figures/rigorous-qft/poincare-covariance-square.svg)

<figcaption>

Poincaré covariance says that transforming states by $U(g)$ and transforming test functions by pullback are compatible: $U(g)\phi(f)U(g)^{-1}=\phi(f_g)$. For non-scalar fields, the component representation $S(\Lambda)$ is included as well.

</figcaption>
</figure>

## Prerequisites

You should know the [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) and the Hilbert-space field data from [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/). The smearing convention is reviewed in [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

A first course in special relativity and QFT is enough for the main ideas. Representation theory of the Lorentz group is helpful for spinor and vector fields, but the page explains where the representation matrices enter.

## Core idea

A relativistic QFT should not depend on which inertial frame labels the same physical situation. In a Hilbert-space theory, this means spacetime transformations must be represented by unitary operators on states:

$$
U(g):\mathcal H\to\mathcal H.
$$

A field is covariant if transforming the state and then measuring the field is equivalent to transforming the spacetime argument and field components. For a scalar field in point-kernel notation,

$$
U(g)\phi(x)U(g)^{-1}
=\phi(gx).
$$

Since $\phi(x)$ is only kernel notation, the precise statement is the smeared one:

$$
U(g)\phi(f)U(g)^{-1}=\phi(f_g),
\qquad
f_g(x)=f(g^{-1}x).
$$

Covariance therefore has two sides:

$$
\text{geometry of spacetime probes}
\quad\longleftrightarrow\quad
\text{unitary action on quantum states}.
$$

The Wightman axioms make this relation exact.

## Setup and conventions

Let

$$
\mathcal P_+^\uparrow
=\mathbb R^d\rtimes SO^+(1,d-1)
$$

be the proper orthochronous Poincaré group. An element is written

$$
g=(a,\Lambda),
$$

with $a\in\mathbb R^d$ and $\Lambda\in SO^+(1,d-1)$. It acts on spacetime by

$$
gx=\Lambda x+a.
$$

The group law is

$$
(a,\Lambda)(b,M)
=
(a+\Lambda b,\Lambda M).
$$

For spinor fields, one usually replaces $SO^+(1,d-1)$ by its spin cover. In four dimensions this is $SL(2,\mathbb C)$ for the Lorentz part. This replacement is not cosmetic: half-integer spin fields are representations of the spin cover, not honest tensor representations of the Lorentz group.

The page uses the same active convention as the Wightman axioms page:

$$
U(g)\phi_i(x)U(g)^{-1}
=\sum_j S_i{}^j(\Lambda^{-1})\phi_j(gx).
$$

Many books instead write an equivalent formula with $U(g)^{-1}\phi_i(x)U(g)$ and $g^{-1}x$. Both are fine. Mixing them is the source of many wrong inverse matrices.

## Strong continuity and generators

The representation

$$
U:\mathcal P_+^\uparrow\to\mathcal U(\mathcal H)
$$

is required to be strongly continuous. This means that for each fixed vector $\Psi\in\mathcal H$, the map

$$
g\mapsto U(g)\Psi
$$

is continuous in the Hilbert-space norm.

Strong continuity is the hypothesis that lets one use Stone's theorem for one-parameter subgroups. For translations,

$$
U(a,I)=e^{ia^\mu P_\mu},
$$

where the $P_\mu$ are self-adjoint energy-momentum generators. With the mostly-minus metric and the plane-wave convention $e^{-ip\cdot x}$, a momentum eigenstate satisfies formally

$$
U(a,I)|p\rangle=e^{ia\cdot p}|p\rangle.
$$

The Wightman spectral condition is a separate axiom:

$$
\operatorname{Spec}(P)\subset\overline V_+.
$$

Poincaré covariance says translations and Lorentz transformations are represented consistently. Positive energy says which part of the joint translation spectrum is physically allowed. Both are needed.

For Lorentz transformations, one-parameter subgroups give self-adjoint generators $M_{\mu\nu}$, at least at the Lie-algebra level on suitable domains. Formally,

$$
U(0,\Lambda(\omega))
=\exp\!
\left(\frac{i}{2}\omega^{\mu\nu}M_{\mu\nu}\right),
$$

with $\omega^{\mu\nu}=-\omega^{\nu\mu}$. The precise domain statements for unbounded generators are part of representation theory and are usually not expanded in the Wightman axioms.

## Covariance of scalar fields

For a scalar field, the point-kernel covariance law is

$$
U(g)\phi(x)U(g)^{-1}=\phi(gx).
$$

Smearing both sides gives the rigorous formula. Starting from

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

one obtains

$$
\begin{aligned}
U(g)\phi(f)U(g)^{-1}
&=\int d^dx\,f(x)\phi(gx) \\
&=\int d^dy\,f(g^{-1}y)\phi(y) \\
&=\phi(f_g),
\end{aligned}
$$

where $y=gx$ and the proper Lorentz transformation has determinant $1$.

The support transforms geometrically:

$$
\operatorname{supp}(f_g)=g\operatorname{supp}(f).
$$

This is why covariance is compatible with smeared locality. If two test functions have spacelike separated supports, their transformed supports are still spacelike separated.

## Fields with spin or tensor indices

A scalar field has no component index. A vector, spinor, or tensor field does. A component field transforms both by moving its spacetime argument and by rotating or boosting its components.

For a finite-dimensional Lorentz representation $S(\Lambda)$, the covariance law is schematically

$$
U(g)\phi_i(x)U(g)^{-1}
=
\sum_j S_i{}^j(\Lambda^{-1})\phi_j(gx).
$$

Examples in four dimensions include:

| Field type | Typical component transformation |
|---|---|
| Scalar $\phi$ | No matrix factor. |
| Vector $A_\mu$ | Lorentz matrix on the vector index. |
| Dirac spinor $\psi_\alpha$ | Spin representation $S(\Lambda)$ on spinor indices. |
| Tensor $T_{\mu\nu}$ | One Lorentz matrix for each index. |

For a covariant vector field in the same active convention, one may write

$$
U(g)A_\mu(x)U(g)^{-1}
=
(\Lambda^{-1})^\nu{}_\mu A_\nu(gx),
$$

with index placement determined by the metric convention. For a Dirac field,

$$
U(g)\psi(x)U(g)^{-1}
=S(\Lambda^{-1})\psi(gx).
$$

These finite-dimensional matrices are not unitary for boosts in the ordinary finite-dimensional inner product. That is not a contradiction. The Hilbert-space operator $U(g)$ is unitary; the component matrix $S(\Lambda)$ tells how field labels transform.

## Covariance of Wightman functions

For a scalar field, vacuum invariance plus field covariance gives

$$
W_n(gx_1,\ldots,gx_n)
=
W_n(x_1,\ldots,x_n).
$$

Indeed,

$$
\begin{aligned}
W_n(x_1,\ldots,x_n)
&=\langle\Omega,
\phi(x_1)\cdots\phi(x_n)
\Omega\rangle \\
&=\langle\Omega,
U(g)\phi(x_1)\cdots\phi(x_n)U(g)^{-1}
\Omega\rangle \\
&=\langle\Omega,
\phi(gx_1)\cdots\phi(gx_n)
\Omega\rangle.
\end{aligned}
$$

For fields with spin, the same derivation gives the appropriate tensor or spinor covariance law for the components of $W_{i_1\cdots i_n}$.

Translation invariance is the special case $g=(a,I)$:

$$
W_n(x_1+a,\ldots,x_n+a)
=
W_n(x_1,\ldots,x_n).
$$

Thus a two-point function depends only on the difference:

$$
W_2(x,y)=W_2(x-y,0)
$$

or, more commonly,

$$
W_2(x,y)=W_2(x-y),
$$

where the second expression suppresses the redundant argument. For higher $n$, translation invariance reduces the number of independent spacetime variables from $n$ to $n-1$.

## Momentum-space consequences

Translation covariance and the spectral condition are often easiest to see in momentum space. Translation invariance of $W_n$ implies total momentum conservation. Schematically,

$$
\widetilde W_n(p_1,\ldots,p_n)
\propto
\delta^{(d)}(p_1+\cdots+p_n).
$$

The spectral condition gives further restrictions on partial sums of momenta. For example, for the scalar two-point function,

$$
\widetilde W_2(p)
$$

is supported in the closed future cone. In a free massive scalar theory this support is the positive mass shell:

$$
p^2=m^2,
\qquad
p^0\ge0.
$$

These support properties are the analytic engine behind many structural results. The spectral condition plus covariance leads to analyticity domains for Wightman functions, and those analyticity properties are used in the CPT and spin–statistics theorems.

## What covariance does not say

Poincaré covariance is not the same as locality. A nonlocal theory can be Poincaré covariant. Locality is the additional statement that spacelike separated field insertions commute or graded-commute.

Poincaré covariance is not the same as positive energy. One can write unitary representations with spectra not contained in the future cone. The spectral condition rules those out.

Poincaré covariance is not the same as gauge invariance. A covariant gauge potential may transform with extra gauge terms or live in an indefinite-metric auxiliary space. Gauge-invariant observables and physical Hilbert spaces require additional structure.

Poincaré covariance is also not available on a general curved spacetime. There the replacement is local covariance: a QFT is organized as a functor assigning algebras to globally hyperbolic spacetimes and embeddings, rather than as a single Hilbert-space representation of the Poincaré group.

## Common pitfalls

**Forgetting the inverse.** The test function transforms by pullback:

$$
f_g(x)=f(g^{-1}x).
$$

This inverse is what makes supports move forward by $g$.

**Confusing unitary and finite-dimensional Lorentz representations.** The Hilbert-space representation $U(g)$ is unitary. The finite-dimensional spinor or vector matrix $S(\Lambda)$ need not be unitary for boosts.

**Treating covariance as a pointwise statement only.** Point formulas are kernel notation. The rigorous Wightman statement is about smeared fields on $\mathcal D$.

**Assuming covariance proves the spectrum condition.** It does not. Positive energy is an independent physical input.

**Ignoring the spin cover.** Spinor fields transform under the spin cover of the Lorentz group. Writing only $SO^+(1,3)$ hides an essential double-valued structure.

## Relations to other pages

[Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) states covariance as one axiom among Hilbert-space positivity, spectral condition, locality, and cyclicity.

[Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/) explains the data on which $U(g)$ and $\phi_i(f)$ act.

Later pages on the spectral condition, locality, Wightman functions, CPT, and spin–statistics use Poincaré covariance as a standing hypothesis.

For curved spacetimes, the later locally covariant QFT chapter replaces global Poincaré symmetry by functorial covariance under spacetime embeddings.

## Research status

**Established.** Poincaré covariance via strongly continuous unitary representations is a foundational part of Wigner particle theory and Wightman QFT. Its compatibility with locality and positive energy underlies the major structural theorems of axiomatic QFT.

**Subtle.** Massless particles, gauge potentials, charged sectors, and infrared representations can make the relation between point fields, particles, and Hilbert-space covariance more delicate than the scalar massive example suggests.

**Beyond this framework.** In curved spacetime or nonrelativistic many-body systems, global Poincaré covariance is replaced by other covariance principles. The Wightman formulation is specifically a Minkowski-spacetime framework.

## Exercises

### Exercise 1: Support of a transformed test function

Let $f_g(x)=f(g^{-1}x)$ with $gx=\Lambda x+a$. Show that

$$
\operatorname{supp}(f_g)=g\operatorname{supp}(f).
$$

<details>
<summary><strong>Solution</strong></summary>

The function $f_g$ is nonzero at $x$ exactly when $f(g^{-1}x)$ is nonzero. This means $g^{-1}x$ lies in $\operatorname{supp}(f)$, or equivalently

$$
x\in g\operatorname{supp}(f).
$$

Taking closures gives the support statement:

$$
\operatorname{supp}(f_g)=g\operatorname{supp}(f).
$$

</details>

### Exercise 2: Smeared covariance from point covariance

Assume the scalar point-kernel formula

$$
U(g)\phi(x)U(g)^{-1}=\phi(gx).
$$

Derive the smeared formula

$$
U(g)\phi(f)U(g)^{-1}=\phi(f_g).
$$

<details>
<summary><strong>Solution</strong></summary>

Using the distributional notation

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

we compute

$$
\begin{aligned}
U(g)\phi(f)U(g)^{-1}
&=\int d^dx\,f(x)U(g)\phi(x)U(g)^{-1} \\
&=\int d^dx\,f(x)\phi(gx).
\end{aligned}
$$

Set $y=gx$. Proper orthochronous Poincaré transformations preserve the spacetime volume, so $d^dy=d^dx$. Therefore

$$
\int d^dx\,f(x)\phi(gx)
=\int d^dy\,f(g^{-1}y)\phi(y)
=\phi(f_g).
$$

</details>

### Exercise 3: Translation invariance of the two-point function

Suppose $U(a,I)\Omega=\Omega$ and

$$
U(a,I)\phi(x)U(a,I)^{-1}=\phi(x+a).
$$

Show that the scalar two-point Wightman function depends only on $x-y$.

<details>
<summary><strong>Solution</strong></summary>

Translation invariance gives

$$
W_2(x+a,y+a)=W_2(x,y)
$$

for all translations $a$. Choose $a=-y$. Then

$$
W_2(x,y)=W_2(x-y,0).
$$

Thus the two-point function is a distribution of one spacetime difference. It is customary to write this as $W_2(x-y)$, with the second argument suppressed.

</details>

### Exercise 4: Why finite-dimensional boost matrices need not be unitary

The Dirac spinor matrix $S(\Lambda)$ is finite-dimensional and is not unitary for a generic Lorentz boost. Why does this not contradict the unitarity of Poincaré symmetry in QFT?

<details>
<summary><strong>Solution</strong></summary>

There are two different representations. The operator

$$
U(g):\mathcal H\to\mathcal H
$$

acts on physical Hilbert-space states and is unitary. The matrix $S(\Lambda)$ acts on field components, such as spinor indices, and expresses how the field label changes under a Lorentz transformation. Finite-dimensional nontrivial Lorentz representations are generally not unitary for boosts. This is compatible with Hilbert-space unitarity because $S(\Lambda)$ is not the inner-product-preserving operator on the state space.

</details>

### Exercise 5: Covariance is not locality

Give an example of a statement that is Poincaré covariant in form but does not by itself imply locality.

<details>
<summary><strong>Solution</strong></summary>

A two-point kernel of the form

$$
K(x-y)
$$

can be Lorentz invariant if $K$ depends only on Lorentz-invariant data such as $(x-y)^2$ and a time-orientation prescription. This covariance says how the kernel transforms under spacetime symmetries. It does not imply that commutators vanish at spacelike separation. Locality is a separate support or commutator condition, such as

$$
[\phi(f),\phi(g)]=0
$$

for spacelike separated supports.

</details>

## References

- E. P. Wigner, "On Unitary Representations of the Inhomogeneous Lorentz Group," *Annals of Mathematics* **40** (1939), 149–204. DOI: [10.2307/1968551](https://doi.org/10.2307/1968551).
- V. Bargmann, "On Unitary Ray Representations of Continuous Groups," *Annals of Mathematics* **59** (1954), 1–46. DOI: [10.2307/1969831](https://doi.org/10.2307/1969831).
- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- S. Weinberg, *The Quantum Theory of Fields, Volume I: Foundations*, Cambridge University Press, 1995.
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).

## Version history

- **2026-06-28:** Initial polished draft for the Wightman and Axiomatic QFT chapter.
