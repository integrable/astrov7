---
title: "Chain Complexes"
description: "Explains chain and cochain complexes, differentials with square zero, cycles, boundaries, cohomology, exact sequences, degree conventions, and QFT examples from de Rham theory, BRST quantization, descent equations, constraints, and physical states."
sidebar:
  label: "Chain Complexes"
  order: 3
level: Advanced
status: "Polished draft"
source: "Standard references on homological algebra, algebraic topology, differential geometry, BRST and BV methods, gauge theory, and mathematical physics, including Weibel, Gelfand–Manin, Bott–Tu, Hatcher, Mac Lane, Nakahara, Frankel, Deligne–Morgan, Weinberg, Srednicki, Schwartz, Zinn-Justin, and modern references on cohomological and derived methods in QFT."
topics:
  - chain complex
  - cochain complex
  - differential
  - cohomology
  - cycles
  - boundaries
  - exact sequence
  - de Rham complex
  - BRST complex
  - descent equations
  - physical state cohomology
canonicalTopics:
  - chain-complex
  - cochain-complex
  - differential
  - cohomology
  - cycle
  - boundary
  - exact-sequence
  - de-rham-complex
  - brst-complex
  - descent-equation
  - physical-state-cohomology
researchStatus:
  established:
    - "Chain and cochain complexes, exactness, and cohomology are standard tools in algebraic topology, differential geometry, gauge theory, BRST quantization, anomaly descent, and cohomological field theory."
    - "The condition d^2=0 implies im d is contained in ker d, making cohomology a well-defined quotient of closed elements by exact elements."
  active:
    - "Derived and homotopical enhancements of complexes organize modern BV–BRST theory, factorization algebras, deformation theory, shifted symplectic geometry, and higher-categorical formulations of QFT."
---

## Summary

A **complex** is a sequence of spaces connected by maps whose consecutive composition is zero. In cochain notation,

$$
\cdots
\xrightarrow{d^{n-2}}
C^{n-1}
\xrightarrow{d^{n-1}}
C^n
\xrightarrow{d^n}
C^{n+1}
\xrightarrow{d^{n+1}}
\cdots,
\qquad
 d^{n+1}d^n=0.
$$

The condition $d^2=0$ has a huge consequence:

$$
\operatorname{im}d^{n-1}\subset \ker d^n.
$$

So we can form **cohomology**,

$$
H^n(C)=\frac{\ker d^n}{\operatorname{im}d^{n-1}}.
$$

In words: cohomology is closed data modulo exact data. This is the algebraic skeleton behind de Rham cohomology, Čech cohomology, BRST physical states, gauge-invariant observables modulo gauge-trivial observables, descent equations for anomalies, and many localization arguments.

<figure class="doc-figure" style="--figure-width: 43rem;">

![Flow diagram showing a cochain complex C^{n-1} to C^n to C^{n+1}, the condition d squared equals zero, exact elements, closed elements, cohomology as a quotient, and examples from BRST, de Rham, Čech, and physical states.](/figures/math-toolkit/chain-complex-cohomology-flow.svg)

<figcaption>

A complex turns a square-zero map into information. Since every exact element is closed, the quotient $H^n(C)=\ker d^n/\operatorname{im}d^{n-1}$ measures the closed elements that are not merely exact. In QFT this pattern appears in forms, gauge fixing, BRST cohomology, descent equations, and physical-state constructions.

</figcaption>
</figure>

:::note[Core slogan]
A complex is a machine for distinguishing physical, geometric, or invariant data from data that is pure gauge, exact, or trivial.
:::

## Prerequisites and conventions

You should know quotient vector spaces, kernels, images, and [Graded Algebras](/math-toolkit/algebraic-categorical-language/graded-algebras/). Helpful background pages include [Vector Spaces and Duals](/math-toolkit/linear-algebra-tensors/vector-spaces-and-duals/), [Algebras and Modules](/math-toolkit/algebraic-categorical-language/algebras-and-modules/), [Exterior Algebra](/math-toolkit/linear-algebra-tensors/exterior-algebra/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), and [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/).

This page mostly uses **cochain** conventions, where the differential raises degree:

$$
d:C^n\to C^{n+1}.
$$

Some fields use **chain** conventions, where the differential lowers degree:

$$
\partial:C_n\to C_{n-1}.
$$

The mathematics is the same after reversing arrows and replacing cohomology by homology. Because QFT often uses de Rham forms, BRST charge, ghost number, and cohomological degree, the cochain convention is the natural default here.

## Complexes from square-zero maps

A cochain complex consists of graded vector spaces or modules $C^n$ and degree-$+1$ maps

$$
d^n:C^n\to C^{n+1}
$$

such that

$$
d^{n+1}\circ d^n=0
$$

for every $n$. When the degree is clear, this is abbreviated as

$$
d^2=0.
$$

The elements of $C^n$ are called **$n$-cochains**. An element $x\in C^n$ is **closed** if

$$
dx=0.
$$

The closed elements form the kernel

$$
Z^n(C)=\ker d^n.
$$

An element $x\in C^n$ is **exact** if there exists $y\in C^{n-1}$ such that

$$
x=dy.
$$

The exact elements form the image

$$
B^n(C)=\operatorname{im}d^{n-1}.
$$

Since $d^2=0$, every exact element is closed:

$$
x=dy
\quad\Longrightarrow\quad
 dx=d^2y=0.
$$

Thus

$$
B^n(C)\subset Z^n(C).
$$

This inclusion is the entire reason cohomology exists.

## Cohomology

The $n$th cohomology of a cochain complex is

$$
H^n(C)=Z^n(C)/B^n(C)
=\frac{\ker d^n}{\operatorname{im}d^{n-1}}.
$$

Elements of $H^n(C)$ are equivalence classes of closed $n$-cochains. Two closed cochains $x,x'\in Z^n(C)$ represent the same cohomology class if they differ by an exact element:

$$
x' = x + dy.
$$

The class of $x$ is often written

$$
[x]\in H^n(C).
$$

Cohomology is therefore not the space of all solutions to $dx=0$. It is the space of solutions modulo the trivial solutions that are themselves $d$ of something.

This “closed modulo exact” structure is the algebraic twin of gauge theory:

$$
\text{physical/invariant condition}
\quad\text{modulo}\quad
\text{gauge/trivial redundancy}.
$$

That is why complexes appear almost everywhere once QFT is written carefully.

## The de Rham complex

The de Rham complex is

$$
0\to\Omega^0(M)
\xrightarrow{d}
\Omega^1(M)
\xrightarrow{d}
\Omega^2(M)
\xrightarrow{d}
\cdots
\xrightarrow{d}
\Omega^{\dim M}(M)
\to 0.
$$

Here $C^n=\Omega^n(M)$ and $d$ is the exterior derivative. The condition $d^2=0$ follows from the symmetry of mixed partial derivatives and the antisymmetry of the wedge product.

Closed forms satisfy

$$
d\omega=0.
$$

Exact forms are of the form

$$
\omega=d\alpha.
$$

The de Rham cohomology group is

$$
H^n_{\mathrm{dR}}(M)=\frac{\ker(d:\Omega^n(M)\to\Omega^{n+1}(M))}{\operatorname{im}(d:\Omega^{n-1}(M)\to\Omega^n(M))}.
$$

In field theory, de Rham cohomology enters through flux quantization, topological terms, characteristic classes, descent relations, Wess–Zumino terms, Chern–Simons forms, and obstructions to global gauge choices.

## Chain complexes and homology

A **chain complex** uses maps that lower degree:

$$
\cdots
\xrightarrow{\partial_{n+2}}
C_{n+1}
\xrightarrow{\partial_{n+1}}
C_n
\xrightarrow{\partial_n}
C_{n-1}
\xrightarrow{\partial_{n-1}}
\cdots,
\qquad
\partial_n\partial_{n+1}=0.
$$

The $n$-cycles are

$$
Z_n(C)=\ker\partial_n,
$$

and the $n$-boundaries are

$$
B_n(C)=\operatorname{im}\partial_{n+1}.
$$

The $n$th homology is

$$
H_n(C)=Z_n(C)/B_n(C).
$$

Geometrically, the boundary of a boundary is zero:

$$
\partial^2=0.
$$

This is the chain-level origin of homology. It is why closed loops that bound disks are homologically trivial, while closed loops wrapping a hole may represent nontrivial classes.

The cochain convention is often better for forms and BRST charges; the chain convention is often better for cycles, integration domains, and defects. Pairing the two gives the homology–cohomology pairing:

$$
\langle [\omega],[\Sigma]\rangle=\int_\Sigma \omega.
$$

This is meaningful because exact shifts integrate to zero on closed cycles, by Stokes' theorem.

## Exactness

A complex is **exact at** $C^n$ if

$$
\operatorname{im}d^{n-1}=\ker d^n.
$$

Equivalently,

$$
H^n(C)=0.
$$

Exactness says that every closed element is already exact. No cohomology survives at that degree.

A sequence

$$
0\to A\xrightarrow{f}B\xrightarrow{g}C\to 0
$$

is a **short exact sequence** if it is exact at $A$, $B$, and $C$. This means:

$$
f\text{ is injective},
\qquad
\operatorname{im}f=\ker g,
\qquad
 g\text{ is surjective}.
$$

Short exact sequences express controlled extensions. The object $B$ contains a subobject behaving like $A$, and the quotient behaves like $C$:

$$
C\cong B/f(A).
$$

In QFT and geometry, exact sequences often encode constraints, gauge redundancies, boundary data, long exact sequences in cohomology, anomaly obstructions, and the difference between local and global solutions.

## Maps of complexes

A **cochain map** $F:C^\bullet\to D^\bullet$ is a collection of maps

$$
F^n:C^n\to D^n
$$

such that the square commutes:

$$
F^{n+1}d_C^n=d_D^nF^n.
$$

In compact notation,

$$
Fd_C=d_DF.
$$

This condition says that $F$ sends closed elements to closed elements and exact elements to exact elements. Therefore $F$ induces a map on cohomology:

$$
H^n(F):H^n(C)\to H^n(D),
\qquad
[x]\mapsto [F x].
$$

This is one of the main reasons complexes are useful. A map that respects the differential descends automatically to the quotient by exact data.

A **quasi-isomorphism** is a cochain map that induces an isomorphism on cohomology:

$$
H^n(F):H^n(C)\xrightarrow{\sim}H^n(D)
$$

for every $n$. Quasi-isomorphic complexes may have very different numbers of fields or auxiliary variables, but the same cohomological content. This idea becomes central in derived and BV–BRST formulations.

## Homotopies of complex maps

Two cochain maps $F,G:C^\bullet\to D^\bullet$ are **chain homotopic** if there are maps

$$
h^n:C^n\to D^{n-1}
$$

such that

$$
F-G=d_D h+h d_C.
$$

A chain homotopy is an algebraic certificate that $F$ and $G$ induce the same map on cohomology. Indeed, if $x$ is closed, then

$$
(F-G)x=d_D(hx)+h(d_Cx)=d_D(hx),
$$

so $Fx$ and $Gx$ differ by an exact element. Therefore

$$
[F x]=[G x]
$$

in cohomology.

This is the algebraic template for many “different choices give the same physical answer” statements. Gauge choices, local trivializations, contracting homotopies, and choices of representatives often differ by exact terms that disappear in cohomology.

## Double complexes

A **double complex** has two degrees and two differentials, often drawn as a grid:

$$
C^{p,q},
\qquad
 d_h:C^{p,q}\to C^{p+1,q},
\qquad
 d_v:C^{p,q}\to C^{p,q+1}.
$$

One usually requires

$$
d_h^2=0,
\qquad
 d_v^2=0,
\qquad
 d_h d_v+d_v d_h=0.
$$

Then the total differential

$$
D=d_h+d_v
$$

satisfies

$$
D^2=0.
$$

Double complexes appear naturally when two types of structure coexist: Čech degree and de Rham degree, ghost number and form degree, antifield number and ghost number, or spacetime degree and internal cohomological degree. Spectral sequences are a systematic way to compute the cohomology of such total complexes by peeling off one direction at a time.

The point is not that every QFT reader should adore spectral sequences on sight. The point is that many “descent” and “local-to-global” calculations are double-complex calculations in informal clothing.

## BRST complexes

In gauge theory, constraints and gauge redundancies make the naive state space too large. BRST quantization introduces an odd operator $Q$ satisfying

$$
Q^2=0.
$$

States or operators are assigned ghost number, and $Q$ raises ghost number by one:

$$
Q:\mathcal H^n\to\mathcal H^{n+1}.
$$

The BRST complex is

$$
\cdots\to\mathcal H^{-1}\xrightarrow{Q}\mathcal H^0\xrightarrow{Q}\mathcal H^1\xrightarrow{Q}\cdots.
$$

Physical states are often identified with ghost-number-zero cohomology:

$$
\mathcal H_{\mathrm{phys}}
\cong H^0_Q(\mathcal H)
=\frac{\ker(Q:\mathcal H^0\to\mathcal H^1)}{\operatorname{im}(Q:\mathcal H^{-1}\to\mathcal H^0)}.
$$

This says:

- $Q\psi=0$ imposes the physical or gauge-invariant condition.
- $\psi\sim\psi+Q\chi$ identifies states differing by pure gauge or null data.

That is the slogan “physical equals closed modulo exact” in its most common QFT form.

## Observables and BRST cohomology

The same logic applies to observables. If $Q$ acts on operators by a graded commutator,

$$
Q\mathcal O=[Q,\mathcal O\},
$$

then a BRST-invariant observable satisfies

$$
Q\mathcal O=0.
$$

A BRST-exact observable has the form

$$
\mathcal O=Q\mathcal V.
$$

In correlation functions of BRST-closed insertions, BRST-exact insertions often decouple, assuming no boundary terms, anomalies, or measure subtleties intervene. Formally, one expects

$$
\langle Q\mathcal V\rangle=0.
$$

This is why BRST cohomology classifies physical observables rather than merely invariant-looking representatives.

The caveat is important: exactness can fail to decouple if the path-integral measure is anomalous, if the field space has boundaries, or if the regularization breaks the symmetry. Cohomology is the right grammar, but analysis still decides whether the formal manipulations are legal.

## Descent equations

Descent equations are a beautiful example of a double complex. Suppose $s$ is a BRST differential and $d$ is the exterior derivative. The anomaly or topological density often appears in a chain of equations like

$$
s\omega_d^{(g)}+d\omega_{d-1}^{(g+1)}=0,
$$

$$
s\omega_{d-1}^{(g+1)}+d\omega_{d-2}^{(g+2)}=0,
$$

and so on. Here the subscript is form degree and the superscript is ghost number.

The total degree may be form degree plus ghost number, and the total differential may be

$$
D=s+d
$$

with signs chosen so that

$$
D^2=0.
$$

Anomaly descent, characteristic classes, Chern–Simons forms, and Wess–Zumino consistency conditions all fit this square-zero pattern.

## Constraints and complexes

Complexes also appear behind constrained systems. If a constraint generates a gauge redundancy, then simply imposing the constraint is not enough; one must also quotient by the transformations it generates. The BRST complex packages both steps into cohomology.

In a very schematic classical picture, first-class constraints $G_a$ generate gauge transformations. Ghosts $c^a$ are introduced, and a BRST charge $Q$ is constructed so that

$$
\{Q,Q\}=0
$$

with the graded Poisson bracket. Gauge-invariant functions modulo gauge-trivial functions are then encoded by $Q$-cohomology.

The detailed construction depends on the constraint algebra, possible structure functions, reducibility, and regularity assumptions. The important toolkit point is that the complex is not decoration; it is the algebraic mechanism that keeps “impose constraints” and “divide by gauge” compatible.

## Exact, closed, gauge-trivial: a dictionary

| Complex language | De Rham example | BRST example | Gauge-theory intuition |
|---|---|---|---|
| cochain | $p$-form $\omega$ | state or operator $\mathcal O$ | candidate datum |
| differential | exterior derivative $d$ | BRST operator $Q$ | gauge/invariance test |
| closed | $d\omega=0$ | $Q\mathcal O=0$ | invariant or conserved |
| exact | $\omega=d\alpha$ | $\mathcal O=Q\mathcal V$ | trivial or pure gauge |
| cohomology | closed forms modulo exact forms | BRST-closed modulo BRST-exact | physical data |

The dictionary is powerful, but it is not a proof that every gauge problem is automatically solved by writing $Q^2=0$. One still needs the correct space of fields, boundary conditions, functional-analytic domain, and anomaly-free regularization.

## A worked finite-dimensional example

Consider the cochain complex

$$
0\to C^0\xrightarrow{d^0} C^1\xrightarrow{d^1} C^2\to 0
$$

with

$$
C^0=\mathbb R,
\qquad
C^1=\mathbb R^2,
\qquad
C^2=\mathbb R,
$$

and maps

$$
d^0(t)=(t,t),
\qquad
 d^1(x,y)=x-y.
$$

Check that it is a complex:

$$
d^1d^0(t)=d^1(t,t)=t-t=0.
$$

Now compute cohomology.

At degree $0$,

$$
H^0=\ker d^0.
$$

Since $d^0(t)=(t,t)$, the kernel is zero:

$$
H^0=0.
$$

At degree $1$,

$$
\ker d^1=\{(x,y):x-y=0\}=\{(t,t):t\in\mathbb R\}.
$$

But

$$
\operatorname{im}d^0=\{(t,t):t\in\mathbb R\}.
$$

Therefore

$$
H^1=0.
$$

At degree $2$,

$$
H^2=C^2/\operatorname{im}d^1.
$$

The map $d^1(x,y)=x-y$ is surjective, so $\operatorname{im}d^1=\mathbb R$ and

$$
H^2=0.
$$

This complex is exact everywhere. It contains variables and maps, but no cohomological information survives. In physics language, all candidate closed degree-$1$ data is already trivial.

Now change $d^1$ to the zero map while keeping $d^0(t)=(t,t)$. Then

$$
\ker d^1=\mathbb R^2,
\qquad
\operatorname{im}d^0=\{(t,t)\},
$$

so

$$
H^1\cong \mathbb R^2/\operatorname{span}\{(1,1)\}\cong\mathbb R.
$$

One nontrivial cohomology class survives. The quotient remembers the difference between the two components, while forgetting the diagonal exact direction.

## Pairings and representatives

A cohomology class has many representatives. If $x$ is closed, then

$$
x\sim x+dy.
$$

A calculation should not depend on this choice. One way to guarantee independence is to pair cohomology with homology. If $\omega$ and $\omega+d\alpha$ are representatives of the same de Rham class and $\Sigma$ is a closed cycle, then

$$
\int_\Sigma (\omega+d\alpha)
=
\int_\Sigma\omega+
\int_\Sigma d\alpha
=
\int_\Sigma\omega+
\int_{\partial\Sigma}\alpha
=
\int_\Sigma\omega.
$$

Since $\partial\Sigma=0$, the exact shift does not change the answer.

This is the model for many QFT statements: observables depend on cohomology classes, not arbitrary representatives, provided boundary and anomaly terms vanish.

## Local versus global exactness

Many complexes have local exactness but global cohomology. The de Rham complex on a contractible coordinate patch is locally exact in positive degree by the Poincaré lemma: closed forms are locally exact. But globally a closed form may fail to be exact because the manifold has topology.

This is the difference between solving an equation locally and solving it globally. Gauge fields, transition functions, line bundles, magnetic monopoles, theta terms, and anomalies all live in this gap.

A physicist-friendly way to say it is:

$$
\text{local equation}
\neq
\text{global triviality}.
$$

Cohomology measures the obstruction.

## Common pitfalls

### Forgetting that exact implies closed, not conversely

The condition $d^2=0$ guarantees

$$
\operatorname{im}d\subset\ker d.
$$

It does not guarantee equality. Equality is exactness, and failure of equality is precisely cohomology.

### Calling every closed representative physical

In BRST language, physical states are BRST-closed modulo BRST-exact states. A particular closed representative may be convenient, but the physical content is the cohomology class.

### Ignoring domains and boundary conditions

For differential operators in field theory, the spaces $C^n$ matter. Boundary conditions, falloff conditions, singularities, and functional-analytic domains can change kernels, images, and hence cohomology.

### Mixing chain and cochain degrees

Boundary maps lower degree; exterior derivatives and BRST operators usually raise degree. Both are complexes, but arrows point in opposite directions. Do not mix formulas for $H_n$ and $H^n$ without checking degree conventions.

### Treating cohomology as always finite-dimensional

Topological examples often have finite-dimensional cohomology, but complexes of fields or local operators can have infinite-dimensional cohomology. Finiteness requires additional hypotheses.

### Assuming a square-zero operator is automatically anomaly-free

Quantum corrections can spoil a classical differential. One may have $Q^2=0$ classically but fail to define a nilpotent quantum operator on the regulated theory. This is one way anomalies appear.

## Exercises

### Exercise 1: Cohomology of a two-term complex

Let

$$
0\to V\xrightarrow{f}W\to 0
$$

be a cochain complex with $V$ in degree $0$ and $W$ in degree $1$. Compute $H^0$ and $H^1$.

<details><summary><strong>Solution</strong></summary>

The degree-zero cohomology is

$$
H^0=\ker f.
$$

The degree-one cohomology is

$$
H^1=W/\operatorname{im}f.
$$

There are no other nonzero terms. Thus $H^0$ measures failure of injectivity and $H^1$ measures failure of surjectivity.

</details>

### Exercise 2: Exactness and vanishing cohomology

Show that a cochain complex is exact at $C^n$ if and only if $H^n(C)=0$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
H^n(C)=\ker d^n/\operatorname{im}d^{n-1}.
$$

This quotient is zero exactly when every element of $\ker d^n$ already lies in $\operatorname{im}d^{n-1}$. Since $d^2=0$ always gives $\operatorname{im}d^{n-1}\subset\ker d^n$, this is equivalent to

$$
\operatorname{im}d^{n-1}=\ker d^n,
$$

which is exactness at $C^n$.

</details>

### Exercise 3: A cochain map induces cohomology

Let $F:C^\bullet\to D^\bullet$ satisfy $Fd_C=d_DF$. Show that if $x$ and $x+d_Cy$ represent the same class in $H^n(C)$, then $Fx$ and $F(x+d_Cy)$ represent the same class in $H^n(D)$.

<details><summary><strong>Solution</strong></summary>

We have

$$
F(x+d_Cy)=Fx+Fd_Cy.
$$

Since $F$ is a cochain map,

$$
Fd_Cy=d_DFy.
$$

Therefore

$$
F(x+d_Cy)=Fx+d_D(Fy),
$$

so $F(x+d_Cy)$ differs from $Fx$ by an exact element in $D^n$. Hence the cohomology class is well defined.

</details>

### Exercise 4: Contracting homotopy kills cohomology

Suppose a complex $C^\bullet$ has maps $h^n:C^n\to C^{n-1}$ such that

$$
dh+hd=\operatorname{id}_C.
$$

Show that all cohomology groups vanish.

<details><summary><strong>Solution</strong></summary>

Let $x\in C^n$ be closed, so $dx=0$. Applying the homotopy identity gives

$$
x=(dh+hd)x=d(hx)+h(dx)=d(hx).
$$

Thus every closed element is exact. Therefore

$$
H^n(C)=0
$$

for all $n$.

</details>

### Exercise 5: BRST exact observables

Assume $Q^2=0$ and that expectation values obey $\langle QX\rangle=0$ for appropriate $X$. Show that replacing a BRST-closed observable $\mathcal O$ by $\mathcal O+Q\mathcal V$ does not change its expectation value.

<details><summary><strong>Solution</strong></summary>

Linearity gives

$$
\langle\mathcal O+Q\mathcal V\rangle
=\langle\mathcal O\rangle+\langle Q\mathcal V\rangle.
$$

By assumption, $\langle Q\mathcal V\rangle=0$. Therefore

$$
\langle\mathcal O+Q\mathcal V\rangle=\langle\mathcal O\rangle.
$$

This is the simplest algebraic form of the statement that expectation values depend on BRST cohomology classes. In real QFT calculations, the assumption $\langle QX\rangle=0$ may fail because of anomalies, boundary terms, or regularization choices.

</details>

## Further reading

For homological algebra, standard references include Weibel and Gelfand–Manin. For algebraic topology, Bott–Tu and Hatcher give geometric intuition. For differential forms and de Rham cohomology in physics, see geometry references such as Nakahara and Frankel. For QFT applications, chain complexes appear throughout BRST and BV quantization, anomaly descent, cohomological field theory, topological field theory, and modern factorization-algebra approaches.

## Version history

- 2026-06-26: First polished draft. Introduces chain and cochain complexes, cohomology, exactness, cochain maps, homotopies, double complexes, BRST examples, descent equations, and exercises.
