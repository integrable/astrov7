---
title: "Stiefel–Whitney Classes"
description: "Defines Stiefel–Whitney classes of real vector bundles and explains their role as mod-2 obstruction data for orientation, spin structures, fermions, and global anomaly terms."
sidebar:
  label: "Stiefel–Whitney Classes"
  order: 9
level: Advanced
status: "Polished draft"
source: "Standard references on characteristic classes and topology for physicists, including Milnor–Stasheff, Bott–Tu, Nakahara, Frankel, Kirby–Taylor, Freed–Moore, and QFT treatments of spin structures, global anomalies, and fermionic path integrals."
topics:
  - Stiefel-Whitney classes
  - real vector bundles
  - orientation obstruction
  - spin obstruction
  - Spinᶜ structures
  - mod-2 cohomology
  - fermion path integrals
  - global anomalies
  - characteristic numbers
  - topology of QFT backgrounds
canonicalTopics:
  - stiefel-whitney-class
  - real-vector-bundle
  - orientation-obstruction
  - spin-obstruction
  - spin-c-structure
  - mod-2-cohomology
  - fermion-path-integral
  - global-anomaly
  - characteristic-number
  - qft-background-topology
researchStatus:
  established:
    - "Stiefel–Whitney classes are standard mod-2 characteristic classes of real vector bundles; $w_1$ detects orientability and $w_2$ detects the obstruction to a spin lift."
  active:
    - "Modern QFT uses Stiefel–Whitney classes in refined anomaly formulas, Pin and Spinᶜ backgrounds, fermionic symmetry-protected phases, generalized-symmetry backgrounds, and cobordism classifications."
---

## Summary

Stiefel–Whitney classes are characteristic classes of real vector bundles. For a rank-$r$ real bundle

$$
E\to M,
$$

they are cohomology classes with mod-$2$ coefficients:

$$
w_k(E)\in H^k(M;\mathbb Z_2),\qquad k=0,1,\ldots,r.
$$

They are assembled into the total Stiefel–Whitney class

$$
w(E)=1+w_1(E)+w_2(E)+\cdots+w_r(E).
$$

The first two classes are the ones every QFT reader should recognize immediately:

$$
w_1(E)=0
\quad\Longleftrightarrow\quad
E\text{ is orientable},
$$

and, for an oriented bundle,

$$
w_2(E)=0
\quad\Longleftrightarrow\quad
E\text{ admits a spin lift}.
$$

For $E=TM$, this is the basic topological obstruction to defining ordinary spinor fields globally on spacetime.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing a real vector bundle, transition functions valued in O(r), Stiefel-Whitney classes, obstruction tests w1=0, w2=0, and W3=beta(w2)=0, followed by orientation, Spin, and Spinᶜ lifts, QFT uses, and reductions relating Stiefel-Whitney classes to Chern and Euler classes.](/figures/math-toolkit/stiefel-whitney-obstruction-ladder.svg)

<figcaption>

Stiefel–Whitney classes are mod-$2$ global data. The first class asks whether orientation can be chosen consistently. The second asks whether an oriented frame bundle can be lifted to a spin bundle. The integral Bockstein $W_3=\beta(w_2)$ controls the basic $\operatorname{Spin}^c$ obstruction.

</figcaption>
</figure>

The slogan is

$$
\text{Stiefel–Whitney classes detect mod-2 global obstructions}.
$$

They do not come from ordinary real-valued curvature forms. That is exactly why they matter: they see sign, orientation, and fermion-consistency data that de Rham cohomology can miss.

## Prerequisites

Read [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/) for the general idea of assigning cohomology classes to bundles. Read [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for cycles, cocycles, and coefficients, and [de Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/) for why real differential forms do not see all integral or mod-$2$ data.

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) for transition functions, [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/) for the spin-lift problem, and [Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) for the analytic side of fermions on curved spaces.

The previous page, [Chern Classes](/math-toolkit/topology-cohomology-characteristic-classes/chern-classes/), explains the complex-bundle classes whose mod-$2$ reductions are related to Stiefel–Whitney classes.

## Core idea

A real rank-$r$ vector bundle is locally trivial:

$$
E|_{U_i}\simeq U_i\times \mathbb R^r.
$$

After choosing a fiber metric, its transition functions may be taken to have values in the orthogonal group:

$$
g_{ij}:U_i\cap U_j\to O(r).
$$

The group $O(r)$ has disconnected components. A transition function can preserve or reverse orientation. Even if all transition functions are orientation-preserving, there may be a further obstruction to lifting them through the double cover

$$
\operatorname{Spin}(r)\to SO(r).
$$

Stiefel–Whitney classes package these obstructions in mod-$2$ cohomology.

The classes are natural:

$$
w_k(f^*E)=f^*w_k(E)
$$

for every smooth map $f:N\to M$. They obey the Whitney product formula:

$$
w(E\oplus F)=w(E)w(F).
$$

The product is the cup product in $H^*(M;\mathbb Z_2)$. Because coefficients are mod $2$, signs disappear:

$$
a\smile b=b\smile a
$$

for degree reasons that would produce signs over $\mathbb Z$ or $\mathbb R$. Mod-$2$ arithmetic is delightfully blunt. It is also merciless: $-1=+1$.

## Axioms and normalization

The Stiefel–Whitney classes are characterized by a small set of properties.

First,

$$
w_0(E)=1,
$$

and

$$
w_k(E)=0\qquad\text{for }k>\operatorname{rank}(E).
$$

Second, they are natural under pullback:

$$
w(f^*E)=f^*w(E).
$$

Third, they obey Whitney multiplication:

$$
w(E\oplus F)=w(E)w(F).
$$

Fourth, the tautological real line bundle

$$
\gamma^1\to \mathbb{RP}^\infty
$$

has

$$
w_1(\gamma^1)=a,
$$

where

$$
a\in H^1(\mathbb{RP}^\infty;\mathbb Z_2)
$$

is the standard generator.

These axioms make Stiefel–Whitney classes computable without introducing a connection. This is good, because for mod-$2$ classes there is no ordinary Chern–Weil real differential-form representative analogous to $\operatorname{tr}(F\wedge F)$.

## The first class: orientation

The first Stiefel–Whitney class

$$
w_1(E)\in H^1(M;\mathbb Z_2)
$$

is the obstruction to orienting $E$.

Geometrically, the determinant of the transition functions gives

$$
\det g_{ij}:U_i\cap U_j\to \{\pm1\}\cong \mathbb Z_2.
$$

These signs form a Čech one-cocycle. Its cohomology class is $w_1(E)$.

If $w_1(E)=0$, the signs can be removed by changing local trivializations. Equivalently, the structure group reduces from

$$
O(r)
$$

to

$$
SO(r).
$$

If $w_1(E)\neq0$, transporting a local orientation around some loop reverses it. This is what happens for the Möbius line bundle over $S^1$.

For spacetime, orientability means

$$
w_1(TM)=0.
$$

On a nonorientable manifold, ordinary integration of top forms and ordinary chiral spinor structures require modification. Physics on unoriented backgrounds usually involves Pin structures, orientation local systems, or additional symmetry data.

## The second class: spin obstruction

Assume now that $E$ is oriented, so $w_1(E)=0$ and the frame bundle has structure group $SO(r)$. A spin structure is a lift of the oriented frame bundle through the double cover

$$
\operatorname{Spin}(r)\to SO(r).
$$

The obstruction to such a lift is

$$
w_2(E)\in H^2(M;\mathbb Z_2).
$$

Thus

$$
E\text{ admits a spin structure}
\quad\Longleftrightarrow\quad
w_1(E)=0\text{ and }w_2(E)=0.
$$

For $E=TM$, this is the topological condition for defining ordinary spinor fields globally on $M$:

$$
M\text{ is spin}
\quad\Longleftrightarrow\quad
w_1(TM)=0,
\quad
w_2(TM)=0.
$$

If a spin structure exists, it is not necessarily unique. The set of spin structures is a torsor for

$$
H^1(M;\mathbb Z_2).
$$

A torsor is like a group with no preferred origin. Once you choose one spin structure, every class in $H^1(M;\mathbb Z_2)$ shifts it to another.

This is why a circle has two spin structures. It is also why spin structures are summed over in many two-dimensional fermionic path integrals.

## Spinᶜ structures and the class W₃

Sometimes $w_2(TM)$ is nonzero, but fermions can still be defined if they are charged under a $U(1)$ gauge field. The relevant structure is $\operatorname{Spin}^c$.

For an oriented bundle $E$, the obstruction to a $\operatorname{Spin}^c$ structure is the integral Bockstein of $w_2(E)$:

$$
W_3(E)=\beta(w_2(E))\in H^3(M;\mathbb Z),
$$

where $\beta$ comes from the short exact sequence

$$
0\to \mathbb Z\xrightarrow{\times 2}\mathbb Z\to\mathbb Z_2\to 0.
$$

A $\operatorname{Spin}^c$ structure exists if and only if

$$
W_3(E)=0.
$$

Equivalently, $w_2(E)$ must be the mod-$2$ reduction of an integral class:

$$
w_2(E)=c_1(L)\bmod 2
$$

for some complex line bundle $L$.

Physically, this means the obstruction to defining an ordinary spinor can be compensated by the topology of a $U(1)$ bundle. Charged fermions on a non-spin manifold are often really spin-c fermions.

## Higher Stiefel–Whitney classes

The classes

$$
w_k(E),\qquad k\ge3,
$$

contain further mod-$2$ information about the real bundle. They appear in characteristic numbers

$$
\int_M w_{i_1}(E)w_{i_2}(E)\cdots w_{i_s}(E)\in\mathbb Z_2,
$$

where

$$
i_1+i_2+\cdots+i_s=\dim M.
$$

These are Stiefel–Whitney numbers. They are cobordism invariants of manifolds when $E=TM$.

In QFT, higher Stiefel–Whitney classes appear in mod-$2$ topological actions and global anomaly formulas. A schematic example of a fermionic topological term is

$$
\pi i\int_M w_i\,w_j,
$$

where the integral is mod $2$. The exponential

$$
\exp\left(\pi i\int_M w_iw_j\right)
$$

is therefore a sign.

That sign can be the whole physical effect.

## Relation to Chern and Euler classes

If $E\to M$ is a complex vector bundle and $E_\mathbb R$ is the underlying real bundle, then

$$
w(E_\mathbb R)=c(E)\bmod 2.
$$

Thus

$$
w_{2k}(E_\mathbb R)=c_k(E)\bmod 2,
$$

and

$$
w_{2k+1}(E_\mathbb R)=0.
$$

For a complex manifold $X$,

$$
w_2(TX_\mathbb R)=c_1(TX)\bmod 2.
$$

This gives a fast spin test for complex manifolds: if $c_1(TX)$ is even, then $X$ is spin; if $c_1(TX)$ is odd, it is not.

For an oriented real rank-$r$ vector bundle $E$, the top Stiefel–Whitney class is the mod-$2$ reduction of the Euler class:

$$
w_r(E)=e(E)\bmod 2.
$$

For $E=TM$ on a compact oriented $r$-manifold,

$$
\int_M w_r(TM)=\chi(M)\bmod 2.
$$

So the top Stiefel–Whitney class counts the Euler number modulo $2$.

There are also relations to Pontryagin classes. For example,

$$
p_k(E)\bmod 2=w_{2k}(E)^2.
$$

This relation becomes useful when comparing integral gravitational characteristic classes with mod-$2$ anomaly data.

## Examples

### The Möbius line bundle

Let $L\to S^1$ be the Möbius real line bundle. Going once around the circle reverses the orientation of the fiber. Therefore

$$
w_1(L)\neq0\in H^1(S^1;\mathbb Z_2).
$$

A trivial real line bundle has $w_1=0$. Thus $w_1$ distinguishes the two real line bundles over $S^1$.

### Oriented surfaces

Let $\Sigma_g$ be a closed oriented surface of genus $g$. Since it is oriented,

$$
w_1(T\Sigma_g)=0.
$$

The second class is the Euler class modulo $2$:

$$
w_2(T\Sigma_g)=e(T\Sigma_g)\bmod 2.
$$

Integrating gives

$$
\int_{\Sigma_g}w_2(T\Sigma_g)=\chi(\Sigma_g)\bmod 2=(2-2g)\bmod 2=0.
$$

In fact every closed oriented surface is spin. The number of spin structures is

$$
|H^1(\Sigma_g;\mathbb Z_2)|=2^{2g}.
$$

### Complex projective space

For complex projective space, one has

$$
c_1(T\mathbb{CP}^n)=(n+1)h,
$$

where

$$
h\in H^2(\mathbb{CP}^n;\mathbb Z)
$$

is the hyperplane class. Therefore

$$
w_2(T\mathbb{CP}^n)=(n+1)h\bmod 2.
$$

So $\mathbb{CP}^n$ is spin exactly when $n$ is odd. In particular,

$$
\mathbb{CP}^1\cong S^2
$$

is spin, while $\mathbb{CP}^2$ is not.

### Real projective space

Let

$$
a\in H^1(\mathbb{RP}^n;\mathbb Z_2)
$$

be the generator. The tangent bundle satisfies

$$
w(T\mathbb{RP}^n)=(1+a)^{n+1}.
$$

The first class is

$$
w_1(T\mathbb{RP}^n)=(n+1)a.
$$

Thus $\mathbb{RP}^n$ is orientable precisely when $n$ is odd. The second class is

$$
w_2(T\mathbb{RP}^n)=\binom{n+1}{2}a^2,
$$

reduced mod $2$. This gives a quick family of examples where orientability and spin are separate questions.

## QFT applications

### Fermions on spacetime

A fermion field is not just a function with spinor indices. Globally, it is a section of a spinor bundle. To define that bundle, the tangent bundle must admit a spin structure:

$$
w_1(TM)=0,
\qquad
w_2(TM)=0.
$$

If $w_2(TM)\neq0$, an uncharged ordinary spinor field is not globally defined. Depending on the theory, the correct replacement may be a spin-c fermion, a Pin fermion, or a theory that is simply not defined on that background.

### Gauge-bundle lifts

The same obstruction logic applies to internal bundles. Suppose a gauge bundle has structure group $SO(N)$, but some field transforms in a representation of $\operatorname{Spin}(N)$ that does not descend to $SO(N)$. Then the $SO(N)$ bundle must lift to a $\operatorname{Spin}(N)$ bundle. The obstruction is

$$
w_2(E_{SO(N)}).
$$

This is one reason the global form of the gauge group matters. The Lie algebra alone does not determine all allowed bundles or all allowed charged objects.

### Mod-2 anomalies

Some global anomalies are signs, not phases continuously connected to $1$. They are naturally measured by mod-$2$ index theory and Stiefel–Whitney classes. Terms such as

$$
\int_M w_2w_3,
\qquad
\int_M w_1^4,
\qquad
\int_M w_2^2
$$

can appear in anomaly inflow or topological response actions, depending on dimension and symmetry structure.

The details belong to the symmetry and anomaly volumes. The toolkit lesson is that these expressions are meaningful because Stiefel–Whitney classes live in mod-$2$ cohomology, and their top-degree products can be integrated to give elements of $\mathbb Z_2$.

### Spin versus spin structure

A common QFT shortcut is to say “the theory needs spin.” More precisely, there are two layers.

First, the background must admit a spin structure:

$$
w_1(TM)=w_2(TM)=0.
$$

Second, one must choose a spin structure. Different choices can change the fermion partition function, especially in low dimensions.

Existence is an obstruction problem. Choice is extra background data. Mixing these up causes endless small disasters.

## What Stiefel–Whitney classes do not do

Stiefel–Whitney classes do not replace Chern or Pontryagin classes. They are mod-$2$ reductions or mod-$2$ invariants, so they can miss integral information. For example, two complex line bundles with first Chern classes differing by an even class have the same underlying $w_2$.

They are also not ordinary curvature forms. A real connection has curvature, and one can build Pontryagin forms from it, but Stiefel–Whitney classes are not represented by real-valued differential forms in the same way. They live in cohomology with $\mathbb Z_2$ coefficients.

Finally, $w_2=0$ does not specify a spin structure. It only says that spin structures exist. The set of choices is controlled by $H^1(M;\mathbb Z_2)$.

## Common pitfalls

**Do not try to integrate $w_i$ as a differential form.** Stiefel–Whitney classes live in $H^i(M;\mathbb Z_2)$. Their top-degree products pair with the mod-$2$ fundamental class to give elements of $\mathbb Z_2$.

**Orientable does not mean spin.** Orientability is $w_1=0$. Spin requires $w_2=0$ as well.

**Spin does not mean unique spin structure.** If spin structures exist, they form a torsor for $H^1(M;\mathbb Z_2)$.

**A complex vector bundle has real Stiefel–Whitney data.** Forgetting the complex structure gives a real bundle, and its Stiefel–Whitney classes are the mod-$2$ reduction of the Chern classes.

**The tangent bundle is not the only bundle with $w_2$.** Gauge bundles can also have nontrivial $w_2$, controlling whether they lift to simply connected covers and which charged fields are globally allowed.

**Do not confuse $w_2$ with $W_3$.** The class $w_2$ is mod $2$. The class $W_3=\beta(w_2)$ is integral torsion and controls the basic spin-c obstruction.

## Exercises

### Exercise 1: The Möbius line squared

Let $L\to S^1$ be the Möbius real line bundle. Show that the rank-two bundle

$$
L\oplus L
$$

is orientable.

<details><summary><strong>Solution</strong></summary>

The first Stiefel–Whitney class satisfies the Whitney product formula. For first classes, this gives

$$
w_1(E\oplus F)=w_1(E)+w_1(F).
$$

Therefore

$$
w_1(L\oplus L)=w_1(L)+w_1(L)=2w_1(L)=0
$$

in mod-$2$ cohomology. Hence $L\oplus L$ is orientable.

Geometrically, going once around the circle reverses each copy of $L$. Reversing both axes in a two-dimensional fiber preserves the orientation of the two-plane.

</details>

### Exercise 2: Spin structures on the circle

How many spin structures does $S^1$ have?

<details><summary><strong>Solution</strong></summary>

The tangent bundle of $S^1$ is trivial, so $S^1$ is spin. The set of spin structures is a torsor for

$$
H^1(S^1;\mathbb Z_2)\cong\mathbb Z_2.
$$

Therefore $S^1$ has two spin structures.

In physics language, these are the two possible fermion boundary conditions around the circle: periodic and antiperiodic, though the precise identification depends on whether the circle is a spatial circle or a Euclidean-time thermal circle.

</details>

### Exercise 3: Why CP² is not spin

Use

$$
c_1(T\mathbb{CP}^n)=(n+1)h
$$

to show that $\mathbb{CP}^2$ is not spin.

<details><summary><strong>Solution</strong></summary>

For a complex manifold,

$$
w_2(TX_\mathbb R)=c_1(TX)\bmod 2.
$$

For $X=\mathbb{CP}^2$,

$$
c_1(T\mathbb{CP}^2)=3h.
$$

Reducing mod $2$ gives

$$
w_2(T\mathbb{CP}^2)=h\neq0
$$

in

$$
H^2(\mathbb{CP}^2;\mathbb Z_2)\cong\mathbb Z_2.
$$

Therefore $\mathbb{CP}^2$ does not admit a spin structure.

</details>

### Exercise 4: Oriented surfaces are spin

Show that every closed oriented surface $\Sigma_g$ admits a spin structure.

<details><summary><strong>Solution</strong></summary>

For an oriented rank-two real vector bundle,

$$
w_2=e\bmod 2.
$$

Taking $E=T\Sigma_g$, the Euler number is

$$
\int_{\Sigma_g}e(T\Sigma_g)=\chi(\Sigma_g)=2-2g.
$$

This is even, so

$$
\int_{\Sigma_g}w_2(T\Sigma_g)=0.
$$

Since

$$
H^2(\Sigma_g;\mathbb Z_2)\cong\mathbb Z_2,
$$

the vanishing of the integral implies

$$
w_2(T\Sigma_g)=0.
$$

The surface is oriented, so $w_1=0$. Hence $\Sigma_g$ is spin.

</details>

### Exercise 5: Underlying real bundle of a complex line bundle

Let $L\to M$ be a complex line bundle and $L_\mathbb R$ its underlying real rank-two bundle. What are $w_1(L_\mathbb R)$ and $w_2(L_\mathbb R)$?

<details><summary><strong>Solution</strong></summary>

A complex line has a canonical orientation as a real two-plane, so

$$
w_1(L_\mathbb R)=0.
$$

Using

$$
w(L_\mathbb R)=c(L)\bmod 2,
$$

and

$$
c(L)=1+c_1(L),
$$

we find

$$
w_2(L_\mathbb R)=c_1(L)\bmod 2.
$$

There are no higher Stiefel–Whitney classes because $L_\mathbb R$ has rank two.

</details>

## References

- J. Milnor and J. Stasheff, *Characteristic Classes*. Standard reference for Stiefel–Whitney classes and their axioms, computations, and characteristic numbers.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. Useful for cohomology, characteristic classes, and relations between topology and differential forms.
- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented reference for homotopy, cohomology, bundles, spin structures, and gauge-theory topology.
- T. Frankel, *The Geometry of Physics*. Geometric reference for forms, bundles, spinors, characteristic classes, and physics examples.
- D. S. Freed and G. W. Moore, works on twisted equivariant matter and fermionic phases. Useful for modern uses of Stiefel–Whitney data in QFT and condensed matter.
- R. Kirby and L. Taylor, work on Pin structures and low-dimensional topology. Useful for unoriented and fermionic-background refinements.
- E. Witten, papers on global anomalies and fermion path integrals. Useful for seeing how mod-$2$ topology enters signs of quantum partition functions.

## Version history

- **2026-06-25:** Initial polished draft. Added the obstruction interpretation of $w_1$, $w_2$, and $W_3$, relations to Chern and Euler classes, QFT applications to fermions and mod-$2$ anomalies, examples, exercises, and the Stiefel–Whitney obstruction-ladder figure.
