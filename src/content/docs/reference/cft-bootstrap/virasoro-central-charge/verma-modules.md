---
title: "Verma Modules"
description: "Defines Virasoro Verma modules, their descendant bases, characters, Gram matrices, and the quotient logic leading to irreducible modules."
sidebar:
  label: "Verma Modules"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Ginsparg 1988; Kac 1979; Feigin and Fuchs 1984"
topics:
  - Virasoro modules
  - Verma modules
  - descendant states
  - characters
  - null vectors
canonicalTopics:
  - virasoro-verma-modules
  - descendant-module-bases
  - virasoro-characters
researchStatus:
  established:
    - "Virasoro Verma modules are the universal freely generated highest-weight modules used to organize descendants and detect null states in two-dimensional CFT."
  active:
    - "Applications to logarithmic CFT, nonsemisimple representation categories, boundary conditions, and vertex operator algebras often require refinements beyond irreducible highest-weight quotients."
---

## Summary

A Virasoro Verma module $V(c,h)$ is the freely generated highest-weight module built from a state $|h\rangle$ satisfying

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

It consists of all finite linear combinations of ordered descendants

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad
n_1\ge n_2\ge\cdots\ge n_k\ge 1.
$$

At level $N=n_1+\cdots+n_k$, the generic number of basis states is the partition number $p(N)$. The level-counting generating function is

$$
\sum_{N=0}^{\infty}p(N)q^N
=
\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

Verma modules are deliberately too large. When a descendant is itself highest-weight, it generates a submodule. The physical irreducible module is obtained by quotienting such submodules. This quotienting is the algebraic origin of null states, minimal-model characters, and differential equations for correlators.

## Prerequisites

You should know [Virasoro Algebra](/cft-bootstrap/virasoro-central-charge/virasoro-algebra/), [Virasoro Generators](/cft-bootstrap/virasoro-central-charge/virasoro-generators/), [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/), [Radial Quantization in 2D](/cft-bootstrap/two-dimensional-cft/radial-quantization-in-2d/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

## Core idea

A Verma module is the universal answer to the question:

> What descendants can be generated from a Virasoro primary if we impose only the Virasoro commutation relations and no further relations?

The answer is: all ordered strings of negative modes. That makes $V(c,h)$ easy to count and easy to manipulate. It is also why Verma modules are the right starting point for representation theory.

But CFT Hilbert spaces are not usually raw Verma modules. A raw Verma module may contain states of zero norm, negative norm, or descendants that should be identified with zero. The physical representation is usually an irreducible quotient.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A Verma module contains all descendants generated from a highest-weight state. Singular descendants generate submodules; quotienting removes null submodules to produce an irreducible module.](/figures/cft-bootstrap/verma-module-quotient.svg)

<figcaption>

A Verma module $V(c,h)$ is freely generated from $|h\rangle$. If a descendant $|\chi\rangle$ is also highest-weight, it generates a submodule that must be quotient out in the irreducible representation.

</figcaption>
</figure>

## Setup and conventions

We use

$$
[L_m,L_n]
=
(m-n)L_{m+n}
+
\frac{c}{12}m(m^2-1)\delta_{m+n,0}.
$$

A highest-weight vector obeys

$$
L_0|h\rangle=h|h\rangle,
\qquad
L_n|h\rangle=0\quad n>0.
$$

The Verma module $V(c,h)$ is spanned by states

$$
L_{-n_1}L_{-n_2}\cdots L_{-n_k}|h\rangle,
\qquad n_1\ge n_2\ge\cdots\ge n_k\ge 1.
$$

The ordered basis follows from a Poincaré–Birkhoff–Witt type statement: the lowering modes $L_{-n}$ generate the negative part of the Virasoro algebra, and commutators can be used to put every monomial into ordered form.

## Levels and partition counting

The level is

$$
N=n_1+\cdots+n_k.
$$

At level $N$, the descendant has $L_0$ eigenvalue $h+N$. The first few levels are

| Level | Basis states in a generic Verma module | Count |
|---:|---|---:|
| $0$ | $|h\rangle$ | $1$ |
| $1$ | $L_{-1}|h\rangle$ | $1$ |
| $2$ | $L_{-2}|h\rangle$, $L_{-1}^2|h\rangle$ | $2$ |
| $3$ | $L_{-3}|h\rangle$, $L_{-2}L_{-1}|h\rangle$, $L_{-1}^3|h\rangle$ | $3$ |
| $4$ | $L_{-4}|h\rangle$, $L_{-3}L_{-1}|h\rangle$, $L_{-2}^2|h\rangle$, $L_{-2}L_{-1}^2|h\rangle$, $L_{-1}^4|h\rangle$ | $5$ |

The count is the number $p(N)$ of partitions of $N$:

$$
\sum_{N=0}^{\infty}p(N)q^N
=
1+q+2q^2+3q^3+5q^4+\cdots
=
\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

This simple generating function is one of the reasons Verma modules are computationally useful.

## Characters

The unnormalized level-counting character is

$$
\operatorname{ch}_{\mathrm{level}}V(c,h)
=
q^h\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

On the cylinder, one usually traces $q^{L_0-c/24}$. The corresponding chiral character is

$$
\chi_{V(c,h)}(q)
=
\operatorname{Tr}_{V(c,h)}q^{L_0-c/24}
=
q^{h-c/24}\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

Using Dedekind's eta function,

$$
\eta(q)=q^{1/24}\prod_{n=1}^{\infty}(1-q^n),
$$

this can be written as

$$
\chi_{V(c,h)}(q)
=
\frac{q^{h-(c-1)/24}}{\eta(q)}.
$$

This formula is for a generic Verma module. If null submodules are quotient out, the character changes.

## Singular vectors and submodules

A singular vector is a descendant $|\chi\rangle$ satisfying

$$
L_n|\chi\rangle=0\quad n>0,
\qquad
L_0|\chi\rangle=(h+N)|\chi\rangle
$$

for some positive level $N$. In other words, $|\chi\rangle$ is both a descendant of $|h\rangle$ and a highest-weight state in its own right.

If such a vector exists, then acting on it with all lowering modes generates a submodule:

$$
U(\mathrm{Vir}_{-})|\chi\rangle\subset V(c,h).
$$

Generically this submodule behaves like a Verma module with highest weight $h+N$:

$$
U(\mathrm{Vir}_{-})|\chi\rangle\simeq V(c,h+N),
$$

though further null vectors can appear inside it.

The irreducible module is obtained by quotienting the maximal proper submodule:

$$
L(c,h)=\frac{V(c,h)}{\text{maximal proper submodule}}.
$$

This is not just mathematical housecleaning. Quotienting null states removes redundant operators and produces the finite or nearly finite structures seen in rational CFT.

## First examples of singular vectors

At level $1$, the only candidate is

$$
L_{-1}|h\rangle.
$$

It is singular if

$$
L_1L_{-1}|h\rangle=0.
$$

Since

$$
L_1L_{-1}|h\rangle=2h|h\rangle,
$$

there is a level-one singular vector when

$$
h=0.
$$

This is the identity-module relation $\partial\mathbf 1=0$.

At level $2$, a general descendant is

$$
|\chi_2\rangle=(L_{-2}+aL_{-1}^2)|h\rangle.
$$

The condition $L_1|\chi_2\rangle=0$ gives

$$
a=-\frac{3}{2(2h+1)}.
$$

The condition $L_2|\chi_2\rangle=0$ then gives

$$
16h^2+2(c-5)h+c=0.
$$

When this relation between $c$ and $h$ holds, the level-two descendant is singular:

$$
\left(L_{-2}-\frac{3}{2(2h+1)}L_{-1}^2\right)|h\rangle.
$$

This is the representation-theoretic seed of the second-order BPZ differential equations that appear in minimal models and related degenerate-field computations.

## Gram matrices and null states

A Verma module has a natural contravariant bilinear form fixed by

$$
\langle h|h\rangle=1,
\qquad
L_n^\dagger=L_{-n}
$$

in a unitary setting. At each level, this gives a Gram matrix. Level $1$ gives

$$
G_1=(2h).
$$

Level $2$, in the ordered basis $L_{-2}|h\rangle$, $L_{-1}^2|h\rangle$, gives

$$
G_2=
\begin{pmatrix}
4h+\frac{c}{2} & 6h \\
6h & 4h(2h+1)
\end{pmatrix}.
$$

A singular vector has zero inner product with all states at the same level and with all descendants outside its submodule. In a unitary theory, zero norm states are quotient out. In nonunitary theories, the bilinear form may be indefinite, and one must distinguish algebraic singular vectors from physical positivity.

The Kac determinant describes exactly when Gram matrices at each level become degenerate. The next pages use this logic to explain [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) and the [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/).

## Verma modules versus conformal families

A conformal family in physics is the set of operators obtained from a primary and all of its descendants. A Verma module is the algebraic model for such a family before quotienting.

For a generic primary,

$$
\text{conformal family}\approx V(c,h)\otimes \bar V(\bar c,\bar h).
$$

For a degenerate primary, this is too large. Null states and their descendants must be removed:

$$
\text{physical family}\approx L(c,h)\otimes \bar L(\bar c,\bar h).
$$

For the identity family, even the first descendant is absent:

$$
L_{-1}|0\rangle=0,
\qquad
\bar L_{-1}|0\rangle=0.
$$

For theories with extended chiral algebras, Virasoro modules may combine into larger modules of the extended algebra.

## How quotienting changes characters

Suppose a Verma module contains one singular vector at level $N$ and no further complications. Then its submodule contributes approximately

$$
q^N\chi_{V(c,h)}(q)
$$

relative to the original highest weight. More precisely, the submodule has highest weight $h+N$, so its Verma character is

$$
\chi_{V(c,h+N)}(q)
=
q^N\chi_{V(c,h)}(q).
$$

The irreducible character is then schematically

$$
\chi_{L(c,h)}(q)
=
\chi_{V(c,h)}(q)-\chi_{V(c,h+N)}(q)
$$

if there is only one embedded submodule and no nested corrections.

Minimal models have a richer pattern of embedded submodules, so their characters are alternating sums. This is the algebraic origin of the familiar minimal-model character formulas.

## Vacuum module

The vacuum module is a special quotient of the $h=0$ Verma module. Because

$$
L_{-1}|0\rangle=0,
$$

the generic level-counting product over all $n\ge 1$ is replaced, before further null quotienting, by a product over $n\ge 2$:

$$
\chi_{\mathrm{vac}}(q)
=
q^{-c/24}\prod_{n=2}^{\infty}\frac{1}{1-q^n}
$$

for a generic vacuum module with no additional null states.

This formula encodes the statement that the stress tensor, created by $L_{-2}|0\rangle$, is the first nontrivial holomorphic vacuum descendant.

## Common pitfalls

Do not treat a Verma module as automatically irreducible. Generic Verma modules are irreducible, but special values of $c$ and $h$ contain singular vectors.

Do not confuse “singular” with “singular function.” A singular vector is a highest-weight descendant inside a module.

Do not forget quotienting. If a null state is present and should be removed, keeping it double-counts operators and gives wrong characters and wrong correlator constraints.

Do not use the generic Verma character for the identity module. The identity has $L_{-1}|0\rangle=0$.

Do not assume every nonunitary representation is useless. Nonunitary Virasoro modules appear in statistical systems, ghosts, logarithmic CFTs, and analytic continuations. They simply do not obey Hilbert-space positivity.

## Relations to other pages

- [Highest-Weight Representations](/cft-bootstrap/virasoro-central-charge/highest-weight-representations/) defines the primary states from which Verma modules are generated.
- [Null States](/cft-bootstrap/virasoro-central-charge/null-states/) explains singular descendants and their consequences for correlators.
- [Kac Determinant Preview](/cft-bootstrap/virasoro-central-charge/kac-determinant-preview/) explains when the Gram matrix degenerates.
- [Virasoro Ward Identities](/cft-bootstrap/virasoro-central-charge/virasoro-ward-identities/) uses descendant structure to constrain correlation functions.
- [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/) uses special irreducible Virasoro modules to build exactly solvable CFTs.
- [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/) develops the character and modular-transformation story further.

## Research status

Virasoro Verma modules, singular vectors, irreducible quotients, and characters are established tools in two-dimensional CFT.

Current research often uses more elaborate categories of modules: logarithmic modules, relaxed highest-weight modules, modules over vertex operator algebras, defect and boundary modules, and nonsemisimple modular tensor categories. The Verma module remains the entry point, but it is not the end of the story.

## Exercises

### Exercise: Count level-four descendants

List the ordered basis states at level $4$ in a generic Virasoro Verma module.

<details>
<summary><strong>Solution</strong></summary>

The partitions of $4$ are

$$
4,
\qquad
3+1,
\qquad
2+2,
\qquad
2+1+1,
\qquad
1+1+1+1.
$$

Therefore the ordered basis states are

$$
L_{-4}|h\rangle,
\qquad
L_{-3}L_{-1}|h\rangle,
\qquad
L_{-2}^2|h\rangle,
$$

$$
L_{-2}L_{-1}^2|h\rangle,
\qquad
L_{-1}^4|h\rangle.
$$

There are $p(4)=5$ states.

</details>

### Exercise: Derive the Verma character

Show that the level-counting character of a generic Verma module is

$$
q^h\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

<details>
<summary><strong>Solution</strong></summary>

A descendant is specified by how many times each lowering mode $L_{-n}$ appears. Let $k_n\ge 0$ be the occupation number of $L_{-n}$. The level is

$$
N=\sum_{n=1}^{\infty}n k_n.
$$

For a fixed $n$, the contribution is

$$
1+q^n+q^{2n}+\cdots=\frac{1}{1-q^n}.
$$

Multiplying over all $n\ge 1$ gives

$$
\sum_{N=0}^{\infty}p(N)q^N
=
\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

Including the primary weight $h$ gives

$$
q^h\prod_{n=1}^{\infty}\frac{1}{1-q^n}.
$$

</details>

### Exercise: Level-two singular condition

Let

$$
|\chi_2\rangle=(L_{-2}+aL_{-1}^2)|h\rangle.
$$

Impose $L_1|\chi_2\rangle=L_2|\chi_2\rangle=0$ and derive the relation

$$
16h^2+2(c-5)h+c=0.
$$

<details>
<summary><strong>Solution</strong></summary>

The $L_1$ condition gives

$$
L_1L_{-2}|h\rangle=3L_{-1}|h\rangle,
$$

and

$$
L_1L_{-1}^2|h\rangle=2(2h+1)L_{-1}|h\rangle.
$$

Thus

$$
a=-\frac{3}{2(2h+1)}.
$$

The $L_2$ condition gives

$$
L_2L_{-2}|h\rangle=\left(4h+\frac{c}{2}\right)|h\rangle,
$$

and

$$
L_2L_{-1}^2|h\rangle=6h|h\rangle.
$$

Therefore

$$
0=4h+\frac{c}{2}+6ah.
$$

Substituting $a$ gives

$$
0=4h+\frac{c}{2}-\frac{9h}{2h+1}.
$$

Multiplying by $2(2h+1)$ yields

$$
16h^2+2(c-5)h+c=0.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, *Applied Conformal Field Theory*, Les Houches lectures, 1988.
- V. G. Kac, “Contravariant form for infinite-dimensional Lie algebras and superalgebras,” *Lecture Notes in Physics* 94, 441–445, 1979.
- B. L. Feigin and D. B. Fuchs, “Verma modules over the Virasoro algebra,” in *Topology*, Lecture Notes in Mathematics 1060, Springer, 1984.
- A. A. Belavin, A. M. Polyakov, and A. B. Zamolodchikov, “Infinite conformal symmetry in two-dimensional quantum field theory,” *Nuclear Physics B* 241, 333–380, 1984.

## Version history

- 2026-06-28: First polished draft. Defines Virasoro Verma modules, level counting, characters, singular vectors, quotient modules, and first null examples.
