---
title: "Algebras and Modules"
description: "Defines algebras and modules as the basic language for multiplication, relations, quotient constructions, and representations in QFT, with examples from operator algebras, universal enveloping algebras, Clifford algebras, gauge representations, and modules of sections."
sidebar:
  label: "Algebras and Modules"
  order: 1
level: Advanced
status: "Polished draft"
source: "Standard references on algebra and representation theory, including Atiyah–Macdonald, Lang, Dummit–Foote, Fulton–Harris, Humphreys, Etingof et al., Weibel, Gelfand–Manin, Mac Lane, Nakahara, Frankel, Weinberg, Srednicki, Schwartz, Zee, and QFT references using operator algebras, Clifford modules, Lie algebra representations, and BRST complexes."
topics:
  - algebra
  - module
  - associative algebra
  - ideal
  - quotient algebra
  - representation
  - universal enveloping algebra
  - Clifford algebra
  - bimodule
  - tensor product over an algebra
canonicalTopics:
  - algebra
  - module
  - associative-algebra
  - ideal
  - quotient-algebra
  - representation
  - universal-enveloping-algebra
  - clifford-algebra
  - bimodule
  - tensor-product-over-algebra
researchStatus:
  established:
    - "Associative algebras, modules, ideals, quotient algebras, and universal enveloping algebras are standard mathematical structures underlying representation theory and many QFT constructions."
    - "Group and Lie algebra representations can be uniformly described as modules over group algebras or universal enveloping algebras; spinor representations are modules over Clifford algebras."
  active:
    - "The organization of QFT observables, defects, generalized symmetries, and boundary conditions by noncommutative, derived, categorical, and higher-categorical algebraic structures remains an active research area."
---

## Summary

An **algebra** is a vector space or module equipped with a multiplication. A **module** is a space on which an algebra acts. That pair of ideas quietly underlies much of QFT:

$$
\text{operators multiply},
\qquad
\text{symmetries act},
\qquad
\text{relations become quotients}.
$$

When a symmetry group acts on a Hilbert space, the Hilbert space is a module over a group algebra. When a Lie algebra acts on fields, the fields are modules over the universal enveloping algebra. When gamma matrices act on spinors, spinors are modules over a Clifford algebra. When functions multiply sections of a vector bundle, the space of sections is a module over the algebra of functions.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Flow diagram showing a free algebra quotiented by relations to form an algebra, the algebra acting on a module, the corresponding representation map into endomorphisms, and the quotient constructions by ideals and submodules.](/figures/math-toolkit/algebra-module-action-flow.svg)

<figcaption>

Algebras encode multiplication and relations. Modules encode actions and representations. Ideals and submodules encode quotient constructions, which are the algebraic version of imposing equations, constraints, or equivalence relations.

</figcaption>
</figure>

The goal of this page is not to turn QFT into abstract algebra soup. The goal is to give a reliable dictionary for phrases like “the fields transform in a representation,” “impose the Clifford relation,” “quotient by exact states,” “the algebra of observables acts on the Hilbert space,” and “compose defects by a tensor product over an algebra.”

:::note[Core slogan]
A representation is a module. A relation is a quotient. A symmetry action is an algebra homomorphism into endomorphisms.
:::

## Prerequisites and conventions

You should know vector spaces, linear maps, tensor products, quotient spaces, and elementary group representations. Helpful nearby pages are [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Tensor Products](/math-toolkit/linear-algebra-tensors/tensor-products/), [Index Notation](/math-toolkit/linear-algebra-tensors/index-notation/), [Exterior Algebra](/math-toolkit/linear-algebra-tensors/exterior-algebra/), [Groups and Algebras](/math-toolkit/groups-representations/groups-and-algebras/), [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/), and [Clifford Algebras](/math-toolkit/clifford-spinors/clifford-algebras/).

Unless stated otherwise, $F$ denotes a field, often $\mathbb R$ or $\mathbb C$. An $F$-algebra means an algebra over $F$. Many definitions also work over a commutative ring $R$, but QFT examples often begin over $\mathbb C$ and then add topology, domains, $*$-operations, or completions later.

This page focuses first on associative algebras. Lie algebras are not associative algebras, but their representations are modules over an associated associative algebra called the universal enveloping algebra.

## Algebras: multiplication with rules

An **associative algebra** $A$ over $F$ is an $F$-vector space with a bilinear multiplication

$$
\mu:A\times A\to A,
\qquad
(a,b)\mapsto ab,
$$

such that

$$
(ab)c=a(bc)
$$

for all $a,b,c\in A$. A **unital** algebra has an element $1_A\in A$ satisfying

$$
1_A a=a=a1_A.
$$

A **commutative** algebra satisfies

$$
ab=ba.
$$

Most operator algebras in quantum theory are not commutative. That is not an inconvenience; it is the point. Quantum mechanics begins with the failure of position and momentum to commute,

$$
[x,p]=i.
$$

In field theory, noncommutativity appears in operator products, canonical commutation relations, Clifford algebras, matrix-valued gauge fields, Wilson-line algebras, and many defect fusion algebras.

An associative unital algebra can equivalently be described by a linear map

$$
\mu:A\otimes_F A\to A
$$

and a unit map

$$
\eta:F\to A,
\qquad
\eta(1)=1_A,
$$

obeying associativity and unit diagrams. The diagram language is useful because it generalizes smoothly to tensor categories and algebra objects, but the basic meaning is simply “multiply consistently.”

## First examples

| Algebra | Multiplication | QFT use |
|---|---|---|
| $F[x]$ | Polynomial multiplication | Generators, characteristic polynomials, simple coordinate rings |
| $C^\infty(M)$ | Pointwise multiplication | Scalar functions on spacetime or target space |
| $\operatorname{Mat}_n(F)$ | Matrix multiplication | Internal degrees of freedom, gauge representations, finite operator algebras |
| $\operatorname{End}_F(V)$ | Composition of linear maps | Operators acting on a vector space $V$ |
| $F[G]$ | Linear extension of group multiplication | Group representations as modules |
| $U(\mathfrak g)$ | Multiplication generated by Lie algebra elements | Lie algebra representations as modules |
| $\operatorname{Cl}(V,g)$ | Clifford multiplication | Gamma matrices and spinor modules |
| $\Lambda^\bullet V^*$ | Wedge product | Differential forms and fermionic sign bookkeeping |
| Differential operators on $M$ | Composition | Ward identities, differential equations, symmetry generators |

The table hides one important point: different algebra structures can live on the same underlying vector space. A vector space alone does not tell you how to multiply its elements. The multiplication is extra data.

For example, $\mathbb C^n$ can be made into a commutative algebra with componentwise multiplication,

$$
(z_1,\ldots,z_n)(w_1,\ldots,w_n)=(z_1w_1,\ldots,z_nw_n),
$$

or it can be the underlying vector space of a cyclic group algebra if a basis is chosen and multiplied cyclically. Same vector space size, different algebraic physics.

## Homomorphisms

An algebra homomorphism between unital algebras is a linear map

$$
\phi:A\to B
$$

such that

$$
\phi(ab)=\phi(a)\phi(b),
\qquad
\phi(1_A)=1_B.
$$

Homomorphisms preserve multiplication. This is why a representation of an algebra $A$ on a vector space $M$ is an algebra homomorphism

$$
\rho:A\to\operatorname{End}_F(M).
$$

The algebra $A$ contains abstract operations. The endomorphism algebra $\operatorname{End}_F(M)$ contains actual linear maps on $M$. The representation tells you how the abstract operation acts in that concrete space.

This one sentence covers many familiar cases:

$$
\begin{array}{ccl}
\text{group representation} &:& G\to GL(M),\\
\text{Lie algebra representation} &:& \mathfrak g\to\operatorname{End}(M),\\
\text{associative algebra representation} &:& A\to\operatorname{End}(M),\\
\text{Clifford representation} &:& \operatorname{Cl}(V,g)\to\operatorname{End}(S).
\end{array}
$$

The first two fit the last two after building the correct algebra from $G$ or $\mathfrak g$.

## Ideals and quotient algebras

A **left ideal** $I\subset A$ is a subspace such that

$$
aI\subset I
\qquad\text{for all }a\in A.
$$

A **right ideal** satisfies $Ia\subset I$. A **two-sided ideal** satisfies both.

Two-sided ideals are the ideals by which we can quotient an algebra. If $I$ is two-sided, the quotient vector space

$$
A/I
$$

inherits multiplication by

$$
(a+I)(b+I)=ab+I.
$$

This is well defined exactly because $I$ is two-sided. If you change $a$ by an element of $I$, or $b$ by an element of $I$, the product changes by an element of $I$.

In physics language, quotienting is how relations become exact statements. A free algebra has too many words. A quotient algebra imposes equations among words.

## Generators and relations

Let $F\langle x_1,\ldots,x_n\rangle$ be the free associative algebra generated by noncommuting symbols $x_i$. Its elements are finite linear combinations of words such as

$$
x_2x_1x_2x_2.
$$

If we want to impose relations $r_\alpha=0$, we form the two-sided ideal generated by the $r_\alpha$ and define

$$
A=F\langle x_1,\ldots,x_n\rangle/(r_\alpha).
$$

Examples are everywhere.

The exterior algebra is generated by $V^*$ with relations

$$
\alpha\beta+\beta\alpha=0.
$$

The Clifford algebra $\operatorname{Cl}(V,g)$ is generated by $V$ with relations

$$
vw+wv=2g(v,w)1.
$$

The universal enveloping algebra $U(\mathfrak g)$ is generated by $\mathfrak g$ with relations

$$
XY-YX=[X,Y].
$$

In each case, the quotient construction says: start with all possible products, then identify products that should be equal because of the physics or geometry.

## Modules: spaces acted on by algebras

Let $A$ be an associative unital algebra over $F$. A **left $A$-module** is an $F$-vector space $M$ with an action

$$
A\times M\to M,
\qquad
(a,m)\mapsto a\cdot m,
$$

such that

$$
(ab)\cdot m=a\cdot(b\cdot m),
\qquad
1_A\cdot m=m,
$$

and the action is linear in $a$ and $m$.

Equivalently, an $A$-module is a representation

$$
\rho:A\to\operatorname{End}_F(M),
\qquad
\rho(a)m=a\cdot m.
$$

This equivalence is the reason algebraists say “module” where physicists often say “representation.” The terminology shifts because algebraists allow $A$ to be a general ring or algebra, not just a group or Lie algebra.

A **right module** has an action

$$
M\times A\to M,
\qquad
(m,a)\mapsto m\cdot a,
$$

with

$$
(m\cdot a)\cdot b=m\cdot(ab).
$$

For noncommutative algebras, left and right modules are not the same notion.

## Submodules, quotients, and irreducibility

A **submodule** $N\subset M$ is a subspace stable under the action of $A$:

$$
a\cdot n\in N
\qquad
\text{for all }a\in A,
\quad n\in N.
$$

If $N$ is a submodule, the quotient vector space $M/N$ becomes an $A$-module by

$$
a\cdot(m+N)=a\cdot m+N.
$$

A nonzero module $M$ is **simple** or **irreducible** if it has no submodules except $0$ and $M$. A module is **semisimple** if it is a direct sum of simple modules.

In many introductory QFT examples, representations are semisimple: angular momentum decomposes into irreducible $SU(2)$ representations, compact group representations behave nicely, and finite-dimensional representations over $\mathbb C$ often split cleanly. But nonsemisimple modules are not exotic nonsense. They appear in logarithmic CFT, indecomposable representations, Jordan blocks, boundary problems, and systems with nilpotent operators.

A useful warning:

$$
\text{irreducible}\quad\neq\quad\text{diagonalizable}.
$$

Those are different ideas. Reducibility concerns invariant subspaces. Diagonalizability concerns whether a particular operator has enough eigenvectors.

## Worked example: group representations as modules

Let $G$ be a group. The group algebra $F[G]$ consists of finite sums

$$
\sum_{g\in G} c_g g,
\qquad c_g\in F,
$$

with multiplication extended linearly from the group multiplication:

$$
\left(\sum_g c_g g\right)
\left(\sum_h d_h h\right)
=
\sum_{g,h}c_gd_h(gh).
$$

A representation of $G$ on $M$ is a map

$$
R:G\to GL(M)
$$

such that $R(gh)=R(g)R(h)$. This extends linearly to

$$
\rho:F[G]\to\operatorname{End}(M),
\qquad
\rho\left(\sum_g c_g g\right)=\sum_g c_g R(g).
$$

So $M$ is an $F[G]$-module.

Conversely, if $M$ is an $F[G]$-module, then each $g\in G\subset F[G]$ acts invertibly on $M$, because $g^{-1}$ is its inverse. Thus the module determines a group representation.

So, under mild finiteness assumptions, saying “representation of $G$” and saying “module over $F[G]$” are two views of the same structure.

## Worked example: Lie algebra representations as modules

A Lie algebra representation is a linear map

$$
\rho:\mathfrak g\to\operatorname{End}(M)
$$

such that

$$
\rho([X,Y])=[\rho(X),\rho(Y)].
$$

The universal enveloping algebra $U(\mathfrak g)$ is defined by

$$
U(\mathfrak g)=T(\mathfrak g)\big/\left(XY-YX-[X,Y]\right),
$$

where $T(\mathfrak g)$ is the tensor algebra. The representation $\rho$ extends uniquely to an associative algebra homomorphism

$$
U(\mathfrak g)\to\operatorname{End}(M).
$$

Thus every Lie algebra representation is a $U(\mathfrak g)$-module.

This is not just formal elegance. It explains why products of generators, Casimir operators, highest-weight modules, Verma modules, and descendants in CFT all belong to the same algebraic machine.

For example, if $\mathfrak g=\mathfrak{su}(2)_\mathbb C$, the quadratic Casimir

$$
C=J_1^2+J_2^2+J_3^2
$$

is an element of $U(\mathfrak g)$. On an irreducible spin-$j$ module, it acts by the scalar $j(j+1)$ in the usual normalization.

## Worked example: Clifford modules and gamma matrices

Let $(V,g)$ be a vector space with a nondegenerate bilinear form. The Clifford algebra is generated by $V$ with relation

$$
vw+wv=2g(v,w)1.
$$

A Clifford module is a vector space $S$ with an algebra homomorphism

$$
\operatorname{Cl}(V,g)\to\operatorname{End}(S).
$$

Choosing a basis $e_a$ of $V$, the images

$$
\gamma_a=\rho(e_a)
$$

satisfy

$$
\gamma_a\gamma_b+\gamma_b\gamma_a=2g_{ab}1_S.
$$

In Lorentzian QFT, the spinor space is a module over the relevant Clifford algebra. The gamma matrices are not the Clifford algebra itself; they are a representation of it on a chosen spinor module. This distinction is a great antidote to gamma-matrix fog.

## Modules over function algebras

Let $M$ be a smooth manifold. The smooth functions $C^\infty(M)$ form a commutative algebra under pointwise multiplication. If $E\to M$ is a vector bundle, its smooth sections $\Gamma(E)$ form a module over $C^\infty(M)$:

$$
(f\cdot s)(x)=f(x)s(x),
\qquad
f\in C^\infty(M),
\quad s\in\Gamma(E).
$$

This example is one reason modules are more flexible than vector spaces. The space of sections is not merely a vector space over $\mathbb R$ or $\mathbb C$; it remembers locality on $M$ through multiplication by functions.

For compact smooth manifolds, a vector bundle can be recovered from its module of sections by the Serre–Swan theorem: vector bundles correspond to finitely generated projective modules over $C^\infty(M)$. The theorem belongs to geometry, but the moral is already useful:

$$
\text{geometric fields can be encoded as modules over functions.}
$$

Gauge theory fits naturally into this language. A matter field is often a section of an associated vector bundle, and local gauge transformations act fiberwise. Algebraically, one studies modules of sections equipped with compatible actions of functions, gauge algebras, and differential operators.

## Free, projective, and finite modules

A module is **free** if it has a basis, meaning it is isomorphic to a direct sum of copies of the algebra:

$$
M\cong A^{\oplus n}.
$$

A module is **finitely generated** if finitely many elements generate it under the $A$-action.

A module $P$ is **projective** if it is a direct summand of a free module:

$$
P\oplus Q\cong A^{\oplus n}
$$

for some module $Q$. Projective modules are the algebraic shadow of vector bundles. A nontrivial vector bundle may not have a global frame, so its section module need not be free, but it is often projective.

This is the algebraic version of a familiar geometry lesson: local triviality does not imply global triviality. You can locally choose a basis of sections, but topology may prevent a global basis.

## Bimodules and tensor products over an algebra

If $A$ and $B$ are algebras, an **$(A,B)$-bimodule** $M$ is a vector space with a left $A$-action and a right $B$-action that commute:

$$
(a\cdot m)\cdot b=a\cdot(m\cdot b).
$$

Bimodules appear whenever an object has two compatible boundary actions, two sides, or two algebra labels. In physics, this is the algebraic prototype for interfaces, defects, boundary conditions, and changes of representation category.

If $N$ is a right $A$-module and $M$ is a left $A$-module, their tensor product over $A$ is

$$
N\otimes_A M
=
(N\otimes_F M)\big/\langle n\cdot a\otimes m-n\otimes a\cdot m\rangle.
$$

The relation

$$
n a\otimes m=n\otimes a m
$$

is called the **balanced relation**. It says that an action of $A$ may be moved from the right side of $N$ to the left side of $M$.

This construction is the correct algebraic version of “gluing along an $A$ boundary.” In later categorical language, tensor product over an algebra is one of the basic mechanisms behind composing interfaces and defects.

A very useful special case is

$$
(A/I)\otimes_A M\cong M/IM,
$$

where $I$ is a two-sided ideal. Tensoring with $A/I$ imposes the relations in $I$ on the module.

## Algebra of observables: useful but delicate

It is tempting to say: “The observables of a quantum theory form an algebra acting on the Hilbert space.” That is morally right, and often extremely useful, but three caveats matter.

First, physical operators may be unbounded. Then products and commutators require common dense domains. The slogan must be refined by functional analysis.

Second, local quantum fields are often operator-valued distributions. Products at the same point are singular and require renormalization. The local operator algebra is not just naïve pointwise multiplication.

Third, gauge theory has redundancies. The algebra of gauge-variant fields is not the same as the algebra of physical gauge-invariant observables. BRST language handles this by passing to cohomology, but that is a later page.

Still, the algebraic viewpoint is indispensable. It lets us ask invariant questions:

$$
\text{What multiplies? What acts? What relations hold? What is quotiented out?}
$$

Those questions survive changes of basis, regulator, and notation.

## Common pitfalls

**Calling every vector space a module without specifying the algebra.** A module is always a module over something. The phrase “$M$ is a module” is incomplete until the acting algebra is named.

**Forgetting that noncommutative algebras have left and right modules.** If $A$ is commutative, left and right modules are essentially the same. If $A$ is noncommutative, they are different, and the order of multiplication matters.

**Using quotient algebras without checking two-sidedness.** To form $A/I$ as an algebra, $I$ must be a two-sided ideal. A left ideal gives a quotient module, not generally a quotient algebra.

**Confusing an abstract algebra with a chosen matrix representation.** The Clifford algebra is not the same as a particular set of gamma matrices. The abstract algebra is defined by relations; gamma matrices are its action on a spinor module.

**Assuming every representation decomposes into irreducibles.** Compact Lie group representations over $\mathbb C$ often behave semisimply. General algebras, infinite-dimensional representations, noncompact groups, and logarithmic CFT modules may not.

**Ignoring topology and analysis.** QFT algebras are rarely just finite-dimensional algebra. Operator domains, completions, distributions, locality, and renormalization can matter. Algebra gives the skeleton; analysis gives it a body.

## Exercises

### Exercise 1: A quotient algebra and nilpotent modules

Let

$$
A=F[x]/(x^2).
$$

Show that giving an $A$-module $M$ is equivalent to giving an $F$-vector space $M$ with a linear operator $N:M\to M$ satisfying $N^2=0$.

<details><summary><strong>Solution</strong></summary>

Let $M$ be an $A$-module. The class of $x$ in $A$ acts on $M$ by a linear operator

$$
N(m)=x\cdot m.
$$

Since $x^2=0$ in $A$, we have

$$
N^2m=x\cdot(x\cdot m)=x^2\cdot m=0.
$$

Conversely, suppose $M$ is an $F$-vector space with $N^2=0$. Define the action of a class $a+bx\in A$ by

$$
(a+bx)\cdot m=am+bN m.
$$

This is well defined because every element of $A$ has a unique representative $a+bx$, and the relation $x^2=0$ is respected exactly because $N^2=0$. Thus $A$-modules are the same as vector spaces equipped with a square-zero operator.

</details>

### Exercise 2: Lie algebra representations extend to the enveloping algebra

Let $\rho:\mathfrak g\to\operatorname{End}(M)$ be a Lie algebra representation. Explain why it induces an algebra homomorphism

$$
U(\mathfrak g)\to\operatorname{End}(M).
$$

<details><summary><strong>Solution</strong></summary>

The tensor algebra $T(\mathfrak g)$ is free as an associative algebra generated by $\mathfrak g$. Therefore the linear map $\rho:\mathfrak g\to\operatorname{End}(M)$ extends uniquely to an algebra homomorphism

$$
\widetilde\rho:T(\mathfrak g)\to\operatorname{End}(M).
$$

The universal enveloping algebra is the quotient

$$
U(\mathfrak g)=T(\mathfrak g)/\left(XY-YX-[X,Y]\right).
$$

Because $\rho$ is a Lie algebra representation,

$$
\rho(X)\rho(Y)-\rho(Y)\rho(X)-\rho([X,Y])=0.
$$

Thus $\widetilde\rho$ kills the ideal generated by $XY-YX-[X,Y]$, so it descends to the quotient $U(\mathfrak g)$.

</details>

### Exercise 3: Tensoring with a quotient imposes relations

Let $I\subset A$ be a two-sided ideal and let $M$ be a left $A$-module. Show that

$$
(A/I)\otimes_A M\cong M/IM.
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
\Phi:(A/I)\otimes_A M\to M/IM
$$

by

$$
\Phi((a+I)\otimes m)=a\cdot m+IM.
$$

This is well defined because if $a$ changes by an element of $I$, then $a\cdot m$ changes by an element of $IM$. It also respects the balanced relation:

$$
\Phi((a+I)b\otimes m)=ab\cdot m+IM,
$$

while

$$
\Phi((a+I)\otimes b\cdot m)=a\cdot(b\cdot m)+IM=ab\cdot m+IM.
$$

Define the inverse map by

$$
\Psi(m+IM)=(1+I)\otimes m.
$$

If $m$ changes by $i\cdot m'$ with $i\in I$, then

$$
(1+I)\otimes i\cdot m'=(i+I)\otimes m'=0,
$$

so $\Psi$ is well defined. The two maps are inverse to each other.

</details>

### Exercise 4: Clifford modules from gamma matrices

Suppose matrices $\gamma_a\in\operatorname{End}(S)$ obey

$$
\gamma_a\gamma_b+\gamma_b\gamma_a=2g_{ab}1_S.
$$

Show that $S$ is a module over $\operatorname{Cl}(V,g)$, where $\{e_a\}$ is a basis of $V$ with metric components $g_{ab}=g(e_a,e_b)$.

<details><summary><strong>Solution</strong></summary>

The tensor algebra $T(V)$ is freely generated by $V$. Sending each basis vector $e_a$ to $\gamma_a$ defines an algebra homomorphism

$$
T(V)\to\operatorname{End}(S).
$$

The Clifford algebra is the quotient of $T(V)$ by the two-sided ideal generated by

$$
e_a e_b+e_b e_a-2g_{ab}1.
$$

The assumed gamma-matrix relation says that the homomorphism sends each generator of this ideal to zero. Therefore it descends to a homomorphism

$$
\operatorname{Cl}(V,g)\to\operatorname{End}(S).
$$

That homomorphism is precisely a Clifford action, so $S$ is a Clifford module.

</details>

## References

For algebra basics, see Atiyah and Macdonald, *Introduction to Commutative Algebra*; Lang, *Algebra*; Dummit and Foote, *Abstract Algebra*; and Weibel, *An Introduction to Homological Algebra*. For Lie algebras and representations, see Fulton and Harris, *Representation Theory*, and Humphreys, *Introduction to Lie Algebras and Representation Theory*.

For geometry-facing modules and vector bundles, see Nakahara, *Geometry, Topology and Physics*, and Frankel, *The Geometry of Physics*. For QFT examples using symmetry representations, Clifford modules, operator algebras, and path-integral structures, compare standard QFT references such as Weinberg, Srednicki, Schwartz, Zee, and Coleman.

For the categorical direction that follows later in this chapter, see Mac Lane, *Categories for the Working Mathematician*; Etingof, Gelaki, Nikshych, and Ostrik, *Tensor Categories*; Bakalov and Kirillov, *Lectures on Tensor Categories and Modular Functors*; and Costello and Gwilliam, *Factorization Algebras in Quantum Field Theory*.

## Version history

| Date | Status | Notes |
|---|---|---|
| 2026-06-26 | Polished draft | Initial page on algebras, modules, ideals, quotients, representations, enveloping algebras, Clifford modules, modules of sections, and tensor products over an algebra. |
