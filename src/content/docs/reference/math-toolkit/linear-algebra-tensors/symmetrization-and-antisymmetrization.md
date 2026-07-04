---
title: "Symmetrization and Antisymmetrization"
description: "Explains symmetric and antisymmetric tensor projections, unit-weight index brackets, permutation projectors, dimensions of symmetric and exterior powers, Young-symmetry warnings, and QFT applications to bosons, fermions, forms, field strengths, and spin tensors."
sidebar:
  label: "Symmetrization and Antisymmetrization"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard references on multilinear algebra, tensor symmetries, representation theory of symmetric groups, differential forms, spinor conventions, and QFT notation, including Frankel, Nakahara, Fulton–Harris, Weinberg, Srednicki, Schwartz, Zee, and standard mathematical physics usage."
topics:
  - symmetrization
  - antisymmetrization
  - tensor symmetries
  - permutation group
  - symmetric tensors
  - alternating tensors
  - exterior powers
  - Young projectors
  - bosons and fermions
  - QFT notation
canonicalTopics:
  - symmetrization
  - antisymmetrization
  - tensor-symmetry
  - symmetric-group-action
  - symmetric-tensor
  - alternating-tensor
  - exterior-power
  - young-projector
  - bosonic-symmetry
  - fermionic-antisymmetry
researchStatus:
  established:
    - "Symmetrization and antisymmetrization are projection operations associated with the trivial and sign representations of the symmetric group acting on tensor slots."
    - "Unit-weight parentheses and brackets are a common convention in relativity, differential geometry, and QFT; wedge-product component formulas must then carry explicit factorial factors."
    - "Fully symmetric and fully antisymmetric tensors are only two of the possible irreducible tensor symmetries for rank three and higher."
  active:
    - "In modern QFT, tensor symmetries are refined by grading, gauge constraints, differential identities, BRST complexes, higher-spin gauge symmetries, and categorical or operadic formulations of local operators."
---

## Summary

Symmetrization and antisymmetrization are projection operations on tensor slots. For a two-index covariant tensor $T_{ij}$, the symmetric and antisymmetric parts are

$$
T_{(ij)}=\frac12(T_{ij}+T_{ji}),
\qquad
T_{[ij]}=\frac12(T_{ij}-T_{ji}).
$$

Thus

$$
T_{ij}=T_{(ij)}+T_{[ij]}.
$$

The parentheses mean “average over permutations with plus signs.” The square brackets mean “average over permutations with the sign of the permutation.” This page uses **unit-weight** brackets: the factor $1/r!$ is included in $T_{(i_1\dots i_r)}$ and $T_{[i_1\dots i_r]}$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing tensor slots acted on by the permutation group, then projected to symmetric and alternating subspaces, with QFT applications to bosons, stress tensors, forms, field strengths, and mixed Young symmetry.](/figures/math-toolkit/symmetrization-projector-flow.svg)

<figcaption>

Symmetrization and antisymmetrization are projectors built from the action of the permutation group on tensor slots. They produce the fully symmetric and fully alternating sectors. In rank three and above there are also mixed Young-symmetry sectors; “not symmetric” does not mean “antisymmetric.”

</figcaption>
</figure>

For QFT, these operations are not decorative notation. They encode Bose symmetry, Fermi antisymmetry, differential forms, field strengths, spin tensors, stress tensors, curvature identities, and the index symmetries of local operators. They also prevent a very common mistake: confusing an antisymmetric tensor with a generic tensor that merely happens not to be symmetric.

## Prerequisites

You should know [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), and [Index Notation](/math-toolkit/linear-algebra-tensors/index-notation/). The page [Bilinear Forms and Metrics](/math-toolkit/linear-algebra-tensors/bilinear-forms-and-metrics/) explains how metrics and invariant tensors raise, lower, and contract indices.

This page treats finite-dimensional algebraic tensor products. Infinite-dimensional Hilbert-space symmetrization, Fock-space completion, and operator-valued distributions need additional analysis, but the algebraic projector formulas here are the finite-dimensional skeleton of those constructions.

## The two-slot decomposition

Let $V$ be a vector space over a field of characteristic zero, usually $\mathbb R$ or $\mathbb C$. A covariant two-tensor is an element

$$
T\in V^*\otimes V^*.
$$

Given two vectors $v,w\in V$, define

$$
T_{\mathrm{sym}}(v,w)=\frac12\bigl(T(v,w)+T(w,v)\bigr),
$$

and

$$
T_{\mathrm{alt}}(v,w)=\frac12\bigl(T(v,w)-T(w,v)\bigr).
$$

Then

$$
T=T_{\mathrm{sym}}+T_{\mathrm{alt}}.
$$

The symmetric part obeys

$$
T_{\mathrm{sym}}(v,w)=T_{\mathrm{sym}}(w,v),
$$

while the antisymmetric part obeys

$$
T_{\mathrm{alt}}(v,w)=-T_{\mathrm{alt}}(w,v).
$$

In components, with $T=T_{ij}\varepsilon^i\otimes\varepsilon^j$,

$$
T_{(ij)}=\frac12(T_{ij}+T_{ji}),
\qquad
T_{[ij]}=\frac12(T_{ij}-T_{ji}).
$$

A useful way to say this is

$$
V^*\otimes V^*\cong \operatorname{Sym}^2V^*\oplus\Lambda^2V^*.
$$

The first summand contains symmetric bilinear forms. The second contains alternating bilinear forms.

This two-slot decomposition is special. For two indices, the only irreducible permutation symmetries are symmetric and antisymmetric. For three or more indices, there are mixed symmetries too.

## Parentheses and brackets

For any tensor expression with repeated slots of the same kind, parentheses denote symmetrization:

$$
T_{(i_1\dots i_r)}
=\frac1{r!}\sum_{\sigma\in S_r}
T_{i_{\sigma(1)}\dots i_{\sigma(r)}}.
$$

Square brackets denote antisymmetrization:

$$
T_{[i_1\dots i_r]}
=\frac1{r!}\sum_{\sigma\in S_r}
\operatorname{sgn}(\sigma)
T_{i_{\sigma(1)}\dots i_{\sigma(r)}}.
$$

The group $S_r$ is the permutation group on $r$ letters. The sign $\operatorname{sgn}(\sigma)$ is $+1$ for even permutations and $-1$ for odd permutations.

For three indices,

$$
T_{(ijk)}=\frac16\bigl(
T_{ijk}+T_{ikj}+T_{jik}+T_{jki}+T_{kij}+T_{kji}
\bigr),
$$

and

$$
T_{[ijk]}=\frac16\bigl(
T_{ijk}+T_{jki}+T_{kij}-T_{ikj}-T_{kji}-T_{jik}
\bigr).
$$

The order of terms in the antisymmetric expression is not important, as long as the signs are the signs of the corresponding permutations.

:::note[Unit-weight convention]
This page uses unit-weight symmetrization and antisymmetrization. Thus $T_{[ij]}=\frac12(T_{ij}-T_{ji})$, not $T_{ij}-T_{ji}$. With this convention,

$$
2\partial_{[\mu}A_{\nu]}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$
:::

Some books use unnormalized brackets. That convention is not wrong, but it changes every factorial downstream. The safest habit is to state the convention once and then carry factors explicitly.

## Symmetrizing only some indices

Often only a subset of indices is symmetrized. For example,

$$
T_{i(jk)}=\frac12(T_{ijk}+T_{ikj}),
$$

while

$$
T_{[ij]k}=\frac12(T_{ijk}-T_{jik}).
$$

The untouched indices stay where they are. Parentheses and brackets bind only the indices inside them.

Vertical bars exclude an index from symmetrization. For example,

$$
T_{[\mu|\rho|\nu]}
=\frac12(T_{\mu\rho\nu}-T_{\nu\rho\mu}).
$$

This notation is useful when an index sits between the ones being antisymmetrized. A common differential-geometry example is a covariant exterior derivative with connection terms, where one wants to antisymmetrize spacetime-form indices but not an internal or frame index.

## Projectors from permutations

Let $S_r$ act on $V^{\otimes r}$ by permuting tensor factors:

$$
\rho(\sigma)(v_1\otimes\cdots\otimes v_r)
= v_{\sigma^{-1}(1)}\otimes\cdots\otimes v_{\sigma^{-1}(r)}.
$$

The inverse in this formula is a convention chosen so that $\rho(\sigma\tau)=\rho(\sigma)\rho(\tau)$. Nothing physical depends on this choice if one is consistent.

The symmetric and alternating projectors are

$$
P_{\mathrm{sym}}=\frac1{r!}\sum_{\sigma\in S_r}\rho(\sigma),
$$

and

$$
P_{\mathrm{alt}}=\frac1{r!}\sum_{\sigma\in S_r}\operatorname{sgn}(\sigma)\rho(\sigma).
$$

They obey

$$
P_{\mathrm{sym}}^2=P_{\mathrm{sym}},
\qquad
P_{\mathrm{alt}}^2=P_{\mathrm{alt}}.
$$

Their images are

$$
\operatorname{im}P_{\mathrm{sym}}=\operatorname{Sym}^r V,
\qquad
\operatorname{im}P_{\mathrm{alt}}=\Lambda^r V.
$$

The first is the $r$th symmetric power. The second is the $r$th exterior power.

For $r=2$, these two projectors add to the identity:

$$
P_{\mathrm{sym}}+P_{\mathrm{alt}}=1.
$$

For $r\ge3$, they do not. There are additional projectors associated with other irreducible representations of $S_r$, usually organized by Young diagrams. That fact is the algebra behind mixed-symmetry tensors such as the Riemann tensor and higher-spin fields.

## Dimensions of symmetric and alternating powers

Let $\dim V=n$. Then

$$
\dim\operatorname{Sym}^r V={n+r-1\choose r},
$$

because a symmetric basis tensor is determined by a multiset of $r$ basis labels chosen from $n$ labels.

The exterior power has dimension

$$
\dim\Lambda^r V={n\choose r},
$$

because an antisymmetric basis tensor is determined by an ordered increasing set of $r$ distinct basis labels.

In particular,

$$
\Lambda^r V=0
\qquad\text{for }r>n.
$$

This is the algebraic reason why there are no nonzero $(n+1)$-forms on an $n$-dimensional manifold.

For $r=2$,

$$
\dim\operatorname{Sym}^2V=\frac{n(n+1)}2,
\qquad
\dim\Lambda^2V=\frac{n(n-1)}2.
$$

These add to $n^2=\dim(V\otimes V)$, as they should.

## Symmetric tensors

A tensor $T\in V^{\otimes r}$ is fully symmetric if

$$
\rho(\sigma)T=T
\qquad
\text{for all }\sigma\in S_r.
$$

In components,

$$
T_{i_1\dots i_r}=T_{i_{\sigma(1)}\dots i_{\sigma(r)}}.
$$

Symmetric tensors appear whenever the order of slots is physically irrelevant without signs. Examples include:

| Object | Symmetry | Reason |
|---|---|---|
| Metric $g_{ij}$ | $g_{ij}=g_{ji}$ | distances come from a symmetric bilinear form |
| Stress tensor $T_{\mu\nu}$ after improvement | often symmetric | couples to metric variation |
| Bosonic two-particle wavefunction | $\psi(x_1,x_2)=\psi(x_2,x_1)$ | identical bosons |
| Scalar-field monomial $\phi^i\phi^j$ | symmetric in $i,j$ for commuting fields | products commute at equal classical level |
| Higher-spin field $h_{\mu_1\dots\mu_s}$ | often fully symmetric | Fronsdal-type massless higher-spin fields |

The phrase “often symmetric” matters. Canonical stress tensors need not be symmetric before improvement. Composite operators can also have trace subtractions, equations-of-motion redundancies, and gauge redundancies. Symmetry in indices is only one part of the full operator definition.

## Alternating tensors

A tensor $A\in V^{\otimes r}$ is fully antisymmetric, or alternating, if

$$
\rho(\sigma)A=\operatorname{sgn}(\sigma)A
\qquad
\text{for all }\sigma\in S_r.
$$

Equivalently, swapping any two slots changes the sign:

$$
A_{\dots ij\dots}=-A_{\dots ji\dots}.
$$

If two indices are equal, an alternating tensor vanishes:

$$
A_{\dots ii\dots}=0.
$$

Examples include:

| Object | Symmetry | QFT role |
|---|---|---|
| Electromagnetic field strength $F_{\mu\nu}$ | $F_{\mu\nu}=-F_{\nu\mu}$ | curvature of a $U(1)$ connection |
| Differential $p$-form $\omega_{\mu_1\dots\mu_p}$ | fully antisymmetric | coordinate-free integration and Stokes’ theorem |
| Levi-Civita tensor $\epsilon_{\mu_1\dots\mu_n}$ | fully antisymmetric | volume, determinants, duality |
| Spin generator $\gamma^{\mu\nu}$ | antisymmetric in $\mu,\nu$ | Lorentz algebra in spinor representation |
| Fermionic two-particle wavefunction | antisymmetric under particle exchange | Pauli exclusion |

In the unit-weight convention,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
=2\partial_{[\mu}A_{\nu]}.
$$

Likewise, the abelian Bianchi identity is

$$
\partial_{[\lambda}F_{\mu\nu]}=0.
$$

Because the brackets include $1/3!$, this formula says the cyclic antisymmetric sum vanishes; it does not say there is an extra factor of $1/6$ in the physical identity.

## Alternating versus antisymmetric products

There are two related but distinct ideas:

1. An alternating tensor is an object whose slots are antisymmetric.
2. A product of anticommuting variables is an algebraic product whose factors change sign when swapped.

The exterior algebra connects these ideas. If $\theta^1,\dots,\theta^n$ are Grassmann generators, then

$$
\theta^i\theta^j=-\theta^j\theta^i.
$$

Thus products of Grassmann variables behave like wedge products. But in QFT the situation has another layer: fermion **fields** are operator-valued or Grassmann-valued distributions, and their signs come from quantum statistics or path-integral grading, not merely from antisymmetric tensor components.

A safe translation rule is:

$$
\text{antisymmetric tensor slots} \quad\neq\quad \text{fermionic operator ordering},
$$

although both are governed by sign representations of permutations.

For the finite-dimensional Grassmann algebra used in fermionic path integrals, see [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/). For differential forms, see [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/).

## Why wedge formulas have factorials

The exterior product is usually defined so that, for one-forms $\alpha,\beta$,

$$
\alpha\wedge\beta=\alpha\otimes\beta-\beta\otimes\alpha.
$$

Therefore its components are

$$
(\alpha\wedge\beta)_{ij}=\alpha_i\beta_j-\alpha_j\beta_i
=2\alpha_{[i}\beta_{j]}.
$$

For a $p$-form $\alpha$ and a $q$-form $\beta$, the component formula in unit-weight bracket notation is

$$
(\alpha\wedge\beta)_{i_1\dots i_{p+q}}
=\frac{(p+q)!}{p!q!}
\alpha_{[i_1\dots i_p}\beta_{i_{p+1}\dots i_{p+q}]}.
$$

That factorial is not optional. It is the price of using unit-weight antisymmetrization brackets.

This is one of the most common sources of factor errors in gauge theory. For example, if

$$
A=A_\mu dx^\mu,
$$

then

$$
dA=\frac12(\partial_\mu A_\nu-\partial_\nu A_\mu)dx^\mu\wedge dx^\nu
=\frac12 F_{\mu\nu}dx^\mu\wedge dx^\nu.
$$

The factor $1/2$ is not a mistake. It compensates for the double counting of antisymmetric components in the sum over $\mu,\nu$.

## Symmetrization with metrics and traces

Symmetrizing indices does not automatically remove traces. Suppose $h_{ij}=h_{ji}$ is a symmetric tensor and $g_{ij}$ is a nondegenerate metric. The trace is

$$
h^i{}_i=g^{ij}h_{ij}.
$$

The traceless symmetric part of a two-tensor is not merely $T_{(ij)}$. In $n$ dimensions it is

$$
T_{\langle ij\rangle}
=T_{(ij)}-\frac1n g_{ij}T^k{}_k,
$$

where the angle brackets are often used for symmetric traceless projection. This notation is convention-dependent, so a page should define it before using it.

Symmetric traceless tensors are central in angular momentum, conformal field theory, and operator classification. In $d$-dimensional Euclidean space, spin-$\ell$ primary operators are often represented by symmetric traceless tensors

$$
\mathcal O_{\mu_1\dots\mu_\ell}
=\mathcal O_{(\mu_1\dots\mu_\ell)},
\qquad
\delta^{\mu_1\mu_2}\mathcal O_{\mu_1\dots\mu_\ell}=0.
$$

The symmetry and the trace condition are separate constraints.

## Antisymmetrization with metrics and duality

A metric does not change antisymmetry. If $F_{\mu\nu}=-F_{\nu\mu}$, then

$$
F^{\mu\nu}=g^{\mu\rho}g^{\nu\sigma}F_{\rho\sigma}
$$

also satisfies

$$
F^{\mu\nu}=-F^{\nu\mu}.
$$

In oriented $n$ dimensions, a metric and volume form define the Hodge star, which maps $p$-forms to $(n-p)$-forms. In four-dimensional Lorentzian gauge theory, this gives the dual field strength

$$
(\star F)_{\mu\nu}
=\frac12\epsilon_{\mu\nu\rho\sigma}F^{\rho\sigma}.
$$

The factor $1/2$ again comes from antisymmetric double counting. Whether $\star^2$ gives $+1$ or $-1$ depends on dimension, degree, and metric signature.

## Mixed symmetry is not a footnote

For rank three and higher, the tensor power $V^{\otimes r}$ decomposes into more than the fully symmetric and fully antisymmetric pieces. For example, a rank-three tensor has symmetric, antisymmetric, and mixed-symmetry components.

A simple mixed-symmetry condition is

$$
T_{ij k}=-T_{ji k},
\qquad
T_{[ijk]}=0.
$$

This is neither fully symmetric nor fully antisymmetric. Such patterns are organized by Young diagrams and Young symmetrizers.

The Riemann curvature tensor is the classic physics example. With all indices lowered, it obeys

$$
R_{\mu\nu\rho\sigma}=-R_{\nu\mu\rho\sigma},
\qquad
R_{\mu\nu\rho\sigma}=-R_{\mu\nu\sigma\rho},
$$

$$
R_{\mu\nu\rho\sigma}=R_{\rho\sigma\mu\nu},
\qquad
R_{[\mu\nu\rho]\sigma}=0.
$$

It is antisymmetric in each pair, symmetric under exchange of pairs, and satisfies a cyclic identity. Calling it “antisymmetric” is true but very incomplete. The full symmetry is a Young-symmetry statement.

For the representation-theoretic technology behind this, see [Young Tableaux](/math-toolkit/groups-representations/young-tableaux/).

## Bosons and fermions

For identical particles in ordinary quantum mechanics, the tensor product of one-particle state spaces carries an action of $S_N$ by permuting particle labels. The bosonic $N$-particle space is the symmetric part,

$$
\operatorname{Sym}^N\mathcal H_1,
$$

and the fermionic $N$-particle space is the antisymmetric part,

$$
\Lambda^N\mathcal H_1.
$$

For two one-particle states $\psi,\chi\in\mathcal H_1$,

$$
\psi\otimes\chi+\chi\otimes\psi
$$

is symmetric, while

$$
\psi\otimes\chi-\chi\otimes\psi
$$

is antisymmetric. Normalized states include a factor depending on whether $\psi$ and $\chi$ are equal or orthogonal. The projector normalization is algebraic; Hilbert-space state normalization is analytic and must be handled separately.

In QFT, creation operators implement these symmetries:

$$
[a^\dagger_f,a^\dagger_g]=0
\qquad\text{for bosons},
$$

and

$$
\{b^\dagger_f,b^\dagger_g\}=0
\qquad\text{for fermions}.
$$

The finite-dimensional algebraic statement survives, but the full field theory requires domains, distributions, Fock completion, and locality.

## Symmetric and antisymmetric invariant tensors

Many QFT formulas hide invariant tensors. For $SU(N)$ in the fundamental representation, the Kronecker delta $\delta^i{}_j$ is invariant and pairs the fundamental with the antifundamental. The Levi-Civita tensor

$$
\epsilon_{i_1\dots i_N}
$$

is fully antisymmetric and defines a singlet in $\Lambda^N\mathbb C^N$. This is the algebra behind baryon-like color singlets:

$$
\epsilon_{i_1\dots i_N}q^{i_1}\cdots q^{i_N}.
$$

For $SU(3)$, this is the familiar completely antisymmetric color contraction of three quarks.

The same group can also have symmetric invariant tensors. For $SU(N)$, the adjoint generators satisfy trace identities involving

$$
f^{abc}
\qquad\text{and}\qquad
d^{abc},
$$

where $f^{abc}$ is antisymmetric and $d^{abc}$ is symmetric in common Hermitian-generator conventions. Which normalization is used depends on the trace convention, usually something like

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

Index symmetry tells you which contractions are allowed; normalization tells you the numerical factors.

## Common pitfalls

A generic tensor is not the sum of only its fully symmetric and fully antisymmetric parts when the rank is three or higher. The missing pieces are mixed-symmetry tensors.

Antisymmetrization brackets in this volume are unit-weight. Forgetting the factor $1/r!$ is bad; forgetting that wedge-product components then need factorials is worse, because the error propagates into Maxwell theory, Chern classes, anomalies, and instanton formulas.

Do not symmetrize indices from different spaces. An expression such as $T_{(\mu a)}$ is meaningless unless there is a previously defined vector space in which $\mu$ and $a$ are both labels. A Lorentz index and a gauge index are not interchangeable.

Do not confuse particle exchange symmetry with component antisymmetry. Fermionic signs in QFT are signs from graded operator or path-integral algebra. Antisymmetric tensors provide the finite-dimensional model, not the whole story.

Do not assume that symmetric means traceless. Symmetric traceless projection requires a metric and a trace subtraction.

## Exercises

### Exercise 1: Projector property

Let $P_{\mathrm{sym}}=\frac12(1+\tau)$ and $P_{\mathrm{alt}}=\frac12(1-\tau)$ on $V\otimes V$, where $\tau(v\otimes w)=w\otimes v$. Show that $P_{\mathrm{sym}}^2=P_{\mathrm{sym}}$, $P_{\mathrm{alt}}^2=P_{\mathrm{alt}}$, and $P_{\mathrm{sym}}P_{\mathrm{alt}}=0$.

<details><summary><strong>Solution</strong></summary>

Since $\tau^2=1$,

$$
P_{\mathrm{sym}}^2=\frac14(1+\tau)(1+\tau)
=\frac14(1+2\tau+\tau^2)
=\frac12(1+\tau)=P_{\mathrm{sym}}.
$$

Similarly,

$$
P_{\mathrm{alt}}^2=\frac14(1-\tau)(1-\tau)
=\frac14(1-2\tau+\tau^2)
=\frac12(1-\tau)=P_{\mathrm{alt}}.
$$

Finally,

$$
P_{\mathrm{sym}}P_{\mathrm{alt}}
=\frac14(1+\tau)(1-\tau)
=\frac14(1-\tau^2)=0.
$$

Thus the symmetric and antisymmetric two-tensor sectors are complementary projections.

</details>

### Exercise 2: Dimensions in three dimensions

Let $\dim V=3$. Compute $\dim\operatorname{Sym}^2V$, $\dim\Lambda^2V$, $\dim\operatorname{Sym}^3V$, and $\dim\Lambda^3V$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\dim\operatorname{Sym}^rV={n+r-1\choose r},
\qquad
\dim\Lambda^rV={n\choose r}.
$$

For $n=3$,

$$
\dim\operatorname{Sym}^2V={4\choose2}=6,
\qquad
\dim\Lambda^2V={3\choose2}=3.
$$

Also,

$$
\dim\operatorname{Sym}^3V={5\choose3}=10,
\qquad
\dim\Lambda^3V={3\choose3}=1.
$$

The one-dimensional space $\Lambda^3V$ is the algebraic home of oriented volume elements.

</details>

### Exercise 3: Field strength from antisymmetrization

With unit-weight brackets, show that

$$
2\partial_{[\mu}A_{\nu]}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

Then show that $F_{\mu\nu}=2\partial_{[\mu}A_{\nu]}$ is antisymmetric.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\partial_{[\mu}A_{\nu]}
=\frac12(\partial_\mu A_\nu-\partial_\nu A_\mu).
$$

Multiplying by $2$ gives the desired expression. Therefore

$$
F_{\nu\mu}
=\partial_\nu A_\mu-\partial_\mu A_\nu
=-F_{\mu\nu}.
$$

So $F$ is antisymmetric.

</details>

### Exercise 4: Wedge-product factorial

Let $\alpha$ and $\beta$ be one-forms. Using unit-weight brackets, verify that

$$
(\alpha\wedge\beta)_{ij}=2\alpha_{[i}\beta_{j]}.
$$

<details><summary><strong>Solution</strong></summary>

The wedge product of one-forms is

$$
\alpha\wedge\beta=\alpha\otimes\beta-\beta\otimes\alpha.
$$

Thus

$$
(\alpha\wedge\beta)_{ij}=\alpha_i\beta_j-\beta_i\alpha_j.
$$

Since scalar components commute,

$$
\beta_i\alpha_j=\alpha_j\beta_i.
$$

With unit-weight brackets,

$$
\alpha_{[i}\beta_{j]}
=\frac12(\alpha_i\beta_j-\alpha_j\beta_i).
$$

Therefore

$$
2\alpha_{[i}\beta_{j]}=\alpha_i\beta_j-\alpha_j\beta_i
=(\alpha\wedge\beta)_{ij}.
$$

</details>

## References and further reading

For multilinear algebra and tensor products, see Steven Roman, *Advanced Linear Algebra*; Paul Halmos, *Finite-Dimensional Vector Spaces*; and William Fulton and Joe Harris, *Representation Theory*. For differential forms and exterior algebra in physics language, see Theodore Frankel, *The Geometry of Physics*, and Mikio Nakahara, *Geometry, Topology and Physics*. For QFT uses of symmetric and antisymmetric tensors, see Mark Srednicki, *Quantum Field Theory*; Steven Weinberg, *The Quantum Theory of Fields*, Vol. I; Matthew Schwartz, *Quantum Field Theory and the Standard Model*; and A. Zee, *Quantum Field Theory in a Nutshell*.

## Version history

- 2026-06-26: First polished draft. Defines unit-weight symmetrization and antisymmetrization, permutation projectors, dimensions, QFT examples, mixed-symmetry warnings, and exercises with solutions.
