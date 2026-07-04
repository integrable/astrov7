---
title: "Graded Algebras"
description: "Explains graded vector spaces, graded algebras, Koszul signs, graded commutators, differential graded algebras, and the sign conventions behind fermions, forms, ghosts, and BRST-style constructions in QFT."
sidebar:
  label: "Graded Algebras"
  order: 2
level: Advanced
status: "Polished draft"
source: "Standard references on algebra, homological algebra, superalgebra, differential forms, BRST methods, and QFT sign conventions, including Weibel, Mac Lane, Deligne–Morgan, Manin, Gelfand–Manin, Nakahara, Frankel, Weinberg, Srednicki, Schwartz, Zee, Henneaux–Teitelboim, and modern mathematical-physics references on graded and differential graded structures."
topics:
  - graded vector space
  - graded algebra
  - super vector space
  - Koszul sign rule
  - graded commutator
  - graded derivation
  - differential graded algebra
  - ghost number
  - fermion parity
  - supertrace
canonicalTopics:
  - graded-vector-space
  - graded-algebra
  - super-vector-space
  - koszul-sign-rule
  - graded-commutator
  - graded-derivation
  - differential-graded-algebra
  - ghost-number
  - fermion-parity
  - supertrace
researchStatus:
  established:
    - "Graded vector spaces, graded algebras, Koszul signs, graded commutators, and differential graded algebras are standard mathematical structures used throughout geometry, topology, BRST theory, supersymmetry, and QFT."
    - "Exterior algebras, Grassmann algebras, de Rham complexes, Clifford algebras, ghost systems, and fermionic Fock spaces are all naturally graded or supergraded structures."
  active:
    - "Derived, higher, and factorization-style versions of graded algebraic structures remain active tools in modern mathematical QFT, deformation theory, supersymmetric field theory, and the study of extended operators."
---

## Summary

A **graded algebra** is an algebra whose elements carry degrees, and whose multiplication remembers those degrees. The simplest slogan is

$$
A=\bigoplus_{n\in \mathbb Z} A^n,
\qquad
A^p A^q\subseteq A^{p+q}.
$$

A homogeneous element $a\in A^p$ has degree $|a|=p$. If $b\in A^q$, then $ab$ has degree $p+q$. That small piece of bookkeeping is the source of the sign rules behind differential forms, Grassmann variables, fermions, ghosts, BRST complexes, and supersymmetry.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flow diagram showing a graded algebra decomposed into homogeneous pieces, degree-preserving multiplication, Koszul signs from swapping factors, graded tensor products, differentials, and graded brackets.](/figures/math-toolkit/graded-algebra-sign-flow.svg)

<figcaption>

A grading turns multiplication into sign-sensitive multiplication. The Koszul rule says that moving homogeneous objects past each other costs a sign determined by their degrees. This is the algebraic origin of the signs in forms, Grassmann variables, ghosts, fermions, and BRST-style calculations.

</figcaption>
</figure>

The point is not that every QFT calculation should be written in abstract graded language. The point is that many QFT signs are not arbitrary. They are the shadow of one rule:

$$
\text{moving degree }p\text{ past degree }q
\quad\leadsto\quad
(-1)^{pq}.
$$

Once you see that rule, a lot of sign folklore becomes plain algebra.

:::note[Core slogan]
A grading is a type system for signs. A homogeneous factor carries a degree, and the Koszul rule tells you what happens when factors are permuted.
:::

## Prerequisites and conventions

You should know vector spaces, tensor products, algebras, modules, and exterior algebra. Helpful nearby pages are [Algebras and Modules](/math-toolkit/algebraic-categorical-language/algebras-and-modules/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), [Symmetrization and Antisymmetrization](/math-toolkit/linear-algebra-tensors/symmetrization-and-antisymmetrization/), [Exterior Algebra](/math-toolkit/linear-algebra-tensors/exterior-algebra/), [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), and [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/).

Unless otherwise stated, degrees are integer degrees and $A^p$ denotes the degree-$p$ part. A **super** object means a $\mathbb Z_2$-graded object,

$$
A=A^{\bar 0}\oplus A^{\bar 1}.
$$

For sign formulas, degrees may be reduced modulo $2$ whenever only parity matters. In other words, $(-1)^{|a||b|}$ depends only on $|a|\bmod 2$ and $|b|\bmod 2$.

## Graded vector spaces

A **$\mathbb Z$-graded vector space** is a vector space decomposed as

$$
V=\bigoplus_{n\in\mathbb Z} V^n.
$$

An element $v\in V^n$ is called **homogeneous of degree $n$**, and we write

$$
|v|=n.
$$

A general element $v\in V$ is a finite sum of homogeneous pieces,

$$
v=\sum_n v_n,
\qquad
v_n\in V^n.
$$

Most sign formulas are first stated for homogeneous elements and then extended linearly. That phrase is not decoration. It prevents a common mistake: the degree $|v|$ is defined only for homogeneous $v$ unless extra data is supplied.

The degree-zero part $V^0$ is not automatically the “physical part.” It is merely the subspace of degree zero. In QFT, the physical subspace might be ghost number zero, BRST cohomology at degree zero, gauge-invariant states, even-parity states, or something else. The grading gives a coordinate system for a calculation; physics tells you which part to keep.

## Graded algebras

A **graded algebra** is a graded vector space

$$
A=\bigoplus_{n\in\mathbb Z} A^n
$$

with a multiplication satisfying

$$
A^p A^q\subseteq A^{p+q}.
$$

Equivalently, the multiplication map

$$
\mu:A\otimes A\to A
$$

has degree zero. If $a\in A^p$ and $b\in A^q$, then

$$
|ab|=|a|+|b|.
$$

Examples are everywhere.

| Graded algebra | Degree | Multiplication | QFT role |
|---|---:|---|---|
| $\Lambda^\bullet V^*$ | Form degree | Wedge product | Differential forms, integration, Chern classes |
| Grassmann algebra | Number of generators modulo $2$ or total degree | Anticommuting product | Fermionic path integrals |
| De Rham algebra $\Omega^\bullet(M)$ | Form degree | Wedge product | Geometry, gauge fields, characteristic classes |
| Fermionic Fock space operators | Fermion parity | Operator product | Canonical fermions |
| BRST fields and ghosts | Ghost number and parity | Operator or functional product | Gauge fixing and cohomology |
| Clifford algebra | Parity | Clifford product | Gamma matrices and spinors |
| Supersymmetry algebra | Fermion parity | Graded bracket | Supercharges and spacetime symmetries |

A graded algebra may be associative, commutative in a graded sense, neither, or both in special cases. The grading does not replace algebraic structure; it refines it.

## Super vector spaces and parity

A **super vector space** is a $\mathbb Z_2$-graded vector space

$$
V=V^{\bar 0}\oplus V^{\bar 1}.
$$

Elements of $V^{\bar 0}$ are **even**, and elements of $V^{\bar 1}$ are **odd**. The parity of a homogeneous element is denoted $|v|\in\{0,1\}$.

This is the right language for bosonic versus fermionic signs. In the simplest bookkeeping:

$$
|\text{bosonic object}|=0,
\qquad
|\text{fermionic object}|=1.
$$

But be careful: “fermion” can mean several nearby things. A Dirac field is odd as an operator-valued distribution in a fermionic algebra; a classical spinor wavefunction in a first-quantized equation is often treated as an ordinary commuting spinor; a Grassmann-valued spinor in a path integral is odd in the Grassmann algebra. The algebraic parity belongs to the object in its chosen formalism, not to the word “spinor” in isolation.

## The Koszul sign rule

The **Koszul sign rule** says that when two homogeneous graded objects of degrees $|a|$ and $|b|$ are interchanged, one inserts the sign

$$
(-1)^{|a||b|}.
$$

In a graded-commutative algebra, this becomes

$$
ab=(-1)^{|a||b|}ba.
$$

Thus two even objects commute, an even and an odd object commute, and two odd objects anticommute.

For differential forms,

$$
\alpha\wedge\beta=(-1)^{pq}\beta\wedge\alpha,
\qquad
\alpha\in\Omega^p(M),\quad \beta\in\Omega^q(M).
$$

For Grassmann generators,

$$
\theta_i\theta_j=-\theta_j\theta_i,
$$

because both generators have odd degree. For a bosonic scalar $\phi$ and a Grassmann variable $\theta$,

$$
\phi\theta=\theta\phi,
$$

because $|\phi|=0$.

The rule should be read operationally. If a sign appears because two symbols cross in the course of a manipulation, ask what their degrees are. If no crossing occurs, do not invent a sign.

## Tensor products of graded algebras

The Koszul rule becomes essential when multiplying tensor products. If $A$ and $B$ are graded algebras, their graded tensor product has multiplication

$$
(a\otimes b)(a'\otimes b')
= (-1)^{|b||a'|} aa'\otimes bb'
$$

for homogeneous $a,a'\in A$ and $b,b'\in B$.

The sign appears because $b$ must move past $a'$ before the $A$-factors and $B$-factors can be multiplied:

$$
a\otimes b\otimes a'\otimes b'
\longmapsto
(-1)^{|b||a'|}a\otimes a'\otimes b\otimes b'.
$$

This formula is the source of many signs in products of forms, products of ghost systems, tensor products of complexes, and multi-particle fermionic constructions. It is also why a tensor product of two differential graded algebras is not multiplied by the naive ungraded formula.

## Graded linear maps

A linear map $f:V\to W$ between graded vector spaces has **degree $k$** if

$$
f(V^n)\subseteq W^{n+k}.
$$

Degree-zero maps preserve degree. Degree-one maps raise degree by one. A differential in a cochain complex is a degree-one map. A boundary operator in a chain complex is often written as degree $-1$.

For homogeneous linear maps, the graded tensor product convention is

$$
(f\otimes g)(v\otimes w)
= (-1)^{|g||v|} f(v)\otimes g(w).
$$

Again, the sign appears because the map $g$ must pass the element $v$ before acting on $w$. Some physics texts suppress this sign by using a convention where maps are not themselves moved past elements. That can be fine locally, but a global sign convention must say which rule is being used.

## Graded derivations

A homogeneous linear map $D:A\to A$ of degree $|D|$ is a **graded derivation** if

$$
D(ab)=D(a)b+(-1)^{|D||a|}aD(b)
$$

for homogeneous $a,b\in A$.

This is the graded Leibniz rule. It is the reason the exterior derivative obeys

$$
d(\alpha\wedge\beta)=d\alpha\wedge\beta+(-1)^p\alpha\wedge d\beta,
\qquad
\alpha\in\Omega^p(M),
$$

because $|d|=1$.

The same pattern appears for BRST differentials, Chevalley–Eilenberg differentials, supersymmetry variations, and BV differentials. The sign is not a convention you can ignore without consequence: it is required for $D$ to be compatible with graded multiplication.

## Graded commutators

For homogeneous elements $a,b$ in an associative graded algebra, the **graded commutator** is

$$
[a,b]_{\mathrm{gr}}=ab-(-1)^{|a||b|}ba.
$$

If both elements are even, this is the ordinary commutator. If both are odd, this is the anticommutator:

$$
[a,b]_{\mathrm{gr}}=ab+ba.
$$

This is why supersymmetry algebras use both commutators and anticommutators. It is not that physicists randomly alternate brackets; they are using one graded bracket.

The graded commutator obeys graded antisymmetry,

$$
[a,b]_{\mathrm{gr}}
=-(-1)^{|a||b|}[b,a]_{\mathrm{gr}},
$$

and a graded Jacobi identity,

$$
(-1)^{|a||c|}[a,[b,c]_{\mathrm{gr}}]_{\mathrm{gr}}
+(-1)^{|b||a|}[b,[c,a]_{\mathrm{gr}}]_{\mathrm{gr}}
+(-1)^{|c||b|}[c,[a,b]_{\mathrm{gr}}]_{\mathrm{gr}}
=0.
$$

A **Lie superalgebra** is a $\mathbb Z_2$-graded vector space with a bracket obeying these graded identities. The basic supersymmetry relation schematically has the form

$$
\{Q_\alpha,\bar Q_{\dot\beta}\}\sim P_{\alpha\dot\beta},
$$

because $Q$ and $\bar Q$ are odd.

## Graded commutative does not mean commutative

A graded algebra is **graded commutative** if

$$
ab=(-1)^{|a||b|}ba.
$$

This does not mean $ab=ba$. Odd elements anticommute. Differential forms are the canonical example: a one-form $dx$ satisfies

$$
dx\wedge dx=0
$$

because

$$
dx\wedge dx=-dx\wedge dx.
$$

Over a field of characteristic not equal to $2$, this implies $2dx\wedge dx=0$ and hence $dx\wedge dx=0$.

The phrase “supercommutative” usually means $\mathbb Z_2$-graded commutative. Grassmann algebras are supercommutative. Clifford algebras are not: their odd generators obey

$$
v w+w v=2g(v,w),
$$

so they fail to anticommute exactly when the metric pairing is nonzero. Clifford algebras are naturally $\mathbb Z_2$-graded, but not supercommutative.

## Differential graded algebras

A **differential graded algebra**, often abbreviated DGA, is a graded algebra $A$ equipped with a degree-one derivation

$$
d:A^n\to A^{n+1}
$$

such that

$$
d^2=0.
$$

The de Rham algebra is the model example:

$$
(\Omega^\bullet(M),\wedge,d).
$$

The conditions are exactly the familiar ones:

$$
d^2=0,
\qquad
 d(\alpha\wedge\beta)=d\alpha\wedge\beta+(-1)^{|\alpha|}\alpha\wedge d\beta.
$$

In QFT, DGAs and their relatives appear whenever a nilpotent operator is compatible with multiplication. If $Q$ is a BRST operator, then one typically wants

$$
Q^2=0,
\qquad
Q(\mathcal O_1\mathcal O_2)
=Q\mathcal O_1\,\mathcal O_2+(-1)^{|\mathcal O_1|}\mathcal O_1\,Q\mathcal O_2,
$$

for homogeneous operators. Then BRST-closed operators form a subalgebra, and BRST-exact operators form an ideal inside it, so the cohomology inherits a product. This is one of the most important reasons graded algebra matters in gauge theory.

The next page, [Chain Complexes](/math-toolkit/algebraic-categorical-language/chain-complexes/), develops the algebra of $d^2=0$ and explains why cohomology is the natural quotient.

## Ghost number, fermion parity, and total degree

QFT often carries more than one grading. A gauge-fixed theory may have fermion parity, ghost number, form degree, and sometimes cohomological degree. A local operator might therefore have a multi-degree such as

$$
(|\mathcal O|_{\mathrm{parity}},\operatorname{gh}(\mathcal O),\deg_{\mathrm{form}}(\mathcal O)).
$$

Which degree controls signs? Usually parity controls signs. Ghost number may agree with parity modulo $2$ for Faddeev–Popov ghosts, but it is not logically the same data. Form degree controls wedge signs. In a topological twist, the relevant sign may come from a total degree,

$$
|\mathcal O|_{\mathrm{tot}}
= |\mathcal O|_{\mathrm{form}}+|\mathcal O|_{\mathrm{ghost}}
\pmod 2.
$$

The only safe rule is to state the grading and the sign convention. “Degree” by itself is not enough when several gradings are present.

## Graded modules

If $A$ is a graded algebra, a **graded left $A$-module** is a graded vector space

$$
M=\bigoplus_n M^n
$$

with an action satisfying

$$
A^p M^q\subseteq M^{p+q}.
$$

For example, differential forms form a graded module over functions:

$$
C^\infty(M)\cdot\Omega^p(M)\subseteq \Omega^p(M),
$$

because functions have degree zero. Spinor-valued differential forms form a graded module over $\Omega^\bullet(M)$. BRST state spaces are often graded modules over ghost algebras. Spaces of local operators may be graded modules over symmetry algebras or chiral algebras.

A degree-$k$ map of graded modules shifts degree by $k$. In homological language, such maps are not “bad”; they are simply maps with nonzero degree. In QFT, supercharges, BRST charges, and exterior derivatives are important precisely because they shift degree.

## Supertrace and graded dimension

For a finite-dimensional super vector space

$$
V=V^{\bar 0}\oplus V^{\bar 1},
$$

the **superdimension** is

$$
\operatorname{sdim}V=\dim V^{\bar 0}-\dim V^{\bar 1}.
$$

For an even endomorphism $T:V\to V$, the **supertrace** is

$$
\operatorname{str}T=
\operatorname{tr}\left(T\big|_{V^{\bar 0}}\right)
-
\operatorname{tr}\left(T\big|_{V^{\bar 1}}\right).
$$

This minus sign is the algebraic ancestor of cancellations between bosonic and fermionic degrees of freedom in indices. The Witten index, Dirac index, elliptic genera, and many localization formulas can be viewed as refined supertraces:

$$
\operatorname{Tr}_{\mathcal H}((-1)^F e^{-\beta H}\cdots).
$$

The supertrace has the graded cyclicity property

$$
\operatorname{str}(AB)=(-1)^{|A||B|}\operatorname{str}(BA)
$$

for homogeneous endomorphisms when the expression is defined. This is another place where moving objects in a circle costs a Koszul sign.

## How this shows up in QFT

In fermionic path integrals, fields are Grassmann-valued. The basic Gaussian integral produces determinants or Pfaffians with signs that depend on the order of variables. Those signs are not optional; they follow from the odd parity of the Grassmann generators.

In gauge fixing, ghosts are typically Grassmann odd even when they correspond to bosonic gauge symmetries. The ghost number grading tracks how many ghost-like variables appear, while fermion parity controls signs in products and commutators.

In BRST quantization, the BRST charge $Q$ is odd and carries ghost number $+1$. Thus it is natural to write

$$
Q^2=0,
\qquad
|Q|=1,
\qquad
\operatorname{gh}(Q)=1.
$$

Physical states or operators are then described by cohomology at an appropriate ghost number.

In differential geometry, the de Rham differential $d$ is odd with respect to form degree. Curvature forms, characteristic classes, Chern–Simons forms, anomaly polynomials, and descent equations all use wedge signs controlled by form degree.

In supersymmetry, supercharges are odd generators. The bracket of two odd generators is an anticommutator, and the bracket of an even generator with an odd generator is an ordinary commutator. One graded bracket covers both.

## Common pitfalls

A very common mistake is to say “odd objects anticommute” without specifying the product. Odd elements anticommute in a graded-commutative algebra. Odd operators in a general graded associative algebra need not anticommute. The Clifford relation is the classic warning sign.

Another mistake is to assign degrees to nonhomogeneous elements. If $a=a_0+a_1$ with $a_0$ even and $a_1$ odd, then $|a|$ is not defined unless one explicitly chooses a convention or decomposes the calculation by parity.

A third mistake is to confuse ghost number with fermion parity. They are related in many examples, but not identical as concepts. The sign in a product is controlled by the parity used in the graded tensor category or superalgebra structure, not by the name of the grading.

A fourth mistake is to forget the tensor-product sign. The product

$$
(a\otimes b)(a'\otimes b')=aa'\otimes bb'
$$

is the ungraded formula. For graded algebras, the correct formula includes

$$
(-1)^{|b||a'|}.
$$

A fifth mistake is to treat a graded commutator as a typographical shortcut. It is a different bracket with different symmetry and Jacobi rules.

## Exercises

### Exercise 1: Exterior signs

Let $\alpha\in\Omega^2(M)$ and $\beta\in\Omega^3(M)$. What is the relation between $\alpha\wedge\beta$ and $\beta\wedge\alpha$?

<details><summary><strong>Solution</strong></summary>

The wedge product is graded commutative:

$$
\alpha\wedge\beta=(-1)^{2\cdot 3}\beta\wedge\alpha.
$$

Since $2\cdot 3=6$ is even,

$$
\alpha\wedge\beta=\beta\wedge\alpha.
$$

A two-form and a three-form commute under the wedge product even though one of the degrees is odd. The sign depends on the product of the degrees, not on whether either degree individually is odd.

</details>

### Exercise 2: Graded tensor product sign

Let $a,a'\in A$ and $b,b'\in B$ be homogeneous elements of graded algebras with

$$
|a|=1,
\qquad
|a'|=1,
\qquad
|b|=1,
\qquad
|b'|=0.
$$

Compute $(a\otimes b)(a'\otimes b')$ in the graded tensor product algebra $A\otimes B$.

<details><summary><strong>Solution</strong></summary>

The graded tensor product multiplication is

$$
(a\otimes b)(a'\otimes b')
= (-1)^{|b||a'|}aa'\otimes bb'.
$$

Here $|b||a'|=1\cdot 1=1$, so

$$
(a\otimes b)(a'\otimes b')=-aa'\otimes bb'.
$$

The degree of $b'$ does not enter this particular sign because the only crossing needed is $b$ past $a'$.

</details>

### Exercise 3: Graded derivation

Let $D$ be a degree-one derivation of a graded algebra $A$. If $a$ is homogeneous of degree $p$, show that

$$
D(a^2)=D(a)a+(-1)^p aD(a).
$$

What happens if $p$ is odd and $A$ is graded commutative?

<details><summary><strong>Solution</strong></summary>

The graded Leibniz rule gives

$$
D(a^2)=D(aa)=D(a)a+(-1)^{|D||a|}aD(a).
$$

Since $|D|=1$ and $|a|=p$,

$$
D(a^2)=D(a)a+(-1)^p aD(a).
$$

If $p$ is odd and $A$ is graded commutative, then $a^2=0$ over characteristic not equal to $2$, so $D(a^2)=0$. The formula is consistent because $D(a)$ has degree $p+1$, hence

$$
D(a)a=(-1)^{(p+1)p}aD(a)=aD(a)
$$

when $p$ is odd, since $(p+1)p$ is even. Therefore

$$
D(a)a-aD(a)=0.
$$

</details>

### Exercise 4: Graded commutator cases

Let $a,b$ be homogeneous elements. Compute the graded commutator when both are even, when $a$ is even and $b$ is odd, and when both are odd.

<details><summary><strong>Solution</strong></summary>

The graded commutator is

$$
[a,b]_{\mathrm{gr}}=ab-(-1)^{|a||b|}ba.
$$

If both are even, $|a||b|=0$, so

$$
[a,b]_{\mathrm{gr}}=ab-ba.
$$

If $a$ is even and $b$ is odd, again $|a||b|=0$, so

$$
[a,b]_{\mathrm{gr}}=ab-ba.
$$

If both are odd, $|a||b|=1$, so

$$
[a,b]_{\mathrm{gr}}=ab+ba.
$$

Thus the graded commutator becomes an anticommutator only for two odd elements.

</details>

## References and further reading

For algebraic foundations, see standard texts on algebra and homological algebra, especially treatments of graded algebras, tensor products, and chain complexes. For geometry-facing examples, differential forms and de Rham cohomology are the cleanest entry point. For QFT-facing examples, compare discussions of Grassmann algebras, fermionic path integrals, Clifford algebras, BRST symmetry, supersymmetry algebras, and ghost number in standard quantum field theory and mathematical-physics references.

Good next pages are [Chain Complexes](/math-toolkit/algebraic-categorical-language/chain-complexes/), [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/), [Grassmann Algebra](/math-toolkit/functional-integrals-determinants/grassmann-algebra/), [Berezin Integration](/math-toolkit/functional-integrals-determinants/berezin-integration/), [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/), and later the planned pages on Cohomology and Tensor Categories.

## Version history

- 2026-06-26: First polished draft. Introduces graded vector spaces, graded algebras, Koszul signs, graded tensor products, graded commutators, DGAs, ghost number, supertrace, common pitfalls, and worked exercises.
