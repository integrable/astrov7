---
title: "Spectral Sequences Preview"
description: "A QFT-oriented preview of spectral sequences as staged cohomology computations for filtered complexes, double complexes, perturbative differentials, BRST bicomplexes, descent equations, equivariant cohomology, and anomaly or obstruction problems."
sidebar:
  label: "Spectral Sequences Preview"
  order: 5
level: Research
status: "Polished draft"
source: "Standard references on algebraic topology, homological algebra, filtered complexes, double complexes, BRST methods, equivariant cohomology, and mathematical physics, including McCleary, Weibel, Bott–Tu, Gelfand–Manin, Hatcher, Mac Lane, Deligne–Morgan, Henneaux–Teitelboim, Nakahara, Frankel, and modern references on BV–BRST theory, localization, and anomaly descent."
topics:
  - spectral sequence
  - filtered complex
  - double complex
  - associated graded
  - filtration
  - page
  - differential
  - convergence
  - extension problem
  - BRST bicomplex
  - descent equations
  - equivariant cohomology
canonicalTopics:
  - spectral-sequence
  - filtered-complex
  - double-complex
  - associated-graded
  - filtration
  - spectral-sequence-page
  - spectral-sequence-differential
  - convergence
  - extension-problem
  - brst-bicomplex
  - descent-equation
  - equivariant-cohomology
researchStatus:
  established:
    - "Spectral sequences are standard tools for computing cohomology of filtered complexes, double complexes, fiber bundles, equivariant complexes, and algebraic-topological constructions."
    - "In physics, spectral-sequence logic appears in BRST bicomplexes, descent equations, constrained systems, equivariant localization, perturbative cohomology, and anomaly computations."
  active:
    - "Spectral sequences and their derived/higher variants remain active tools in BV–BRST theory, factorization algebras, generalized symmetries, topological phases, and modern anomaly classification."
---

## Summary

A **spectral sequence** is a systematic way to compute cohomology in stages. It appears when the complex has extra structure, usually a filtration or a bigrading, so that the differential can be studied piece by piece.

The cartoon is

$$
E_0\Longrightarrow E_1\Longrightarrow E_2\Longrightarrow\cdots\Longrightarrow E_\infty,
$$

where each page $E_r$ has a differential $d_r$, and the next page is its cohomology:

$$
E_{r+1}=H(E_r,d_r).
$$

Under good convergence hypotheses, the limiting page $E_\infty$ is not usually the cohomology itself, but the **associated graded** of the cohomology:

$$
E_\infty^{p,q}\simeq
\operatorname{gr}_F^p H^{p+q}(C,d).
$$

That last sentence is the part people forget. Tiny footgun; very popular model.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Diagram showing a filtered complex producing spectral sequence pages E0, E1, E2, and E infinity, with differentials d0, d1, and d2 on a bidegree grid and convergence to the associated graded of cohomology.](/figures/math-toolkit/spectral-sequence-page-flow.svg)

<figcaption>

A spectral sequence computes cohomology page by page. Each differential $d_r$ removes classes that fail at the next level of approximation. The limiting page $E_\infty$ records the associated graded pieces of the desired cohomology; extension data may still be needed to reconstruct the full answer.

</figcaption>
</figure>

For QFT readers, spectral sequences are useful because many important differentials split into simpler parts:

$$
D=d_0+d_1+d_2+\cdots.
$$

One first computes $H(d_0)$, then asks which classes survive $d_1$, then which survive $d_2$, and so on. This is the disciplined version of “solve the easiest constraint first, then add corrections.”

:::note[Core slogan]
A spectral sequence is a controlled approximation scheme for cohomology. It is perturbation theory for square-zero differentials, with bookkeeping strict enough to survive contact with signs.
:::

## Prerequisites and conventions

You should know [Chain Complexes](/math-toolkit/algebraic-categorical-language/chain-complexes/), [Cohomology](/math-toolkit/algebraic-categorical-language/cohomology/), and [Graded Algebras](/math-toolkit/algebraic-categorical-language/graded-algebras/). Helpful nearby pages include [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/), [Čech Cohomology Preview](/math-toolkit/topology-cohomology-characteristic-classes/cech-cohomology-preview/), [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/), and the localization pages that will appear in the supersymmetry and geometry volumes.

This page uses cohomological grading. A filtered cochain complex has

$$
d:C^n\to C^{n+1},
\qquad d^2=0.
$$

For a first-quadrant cohomological spectral sequence, the common convention is

$$
d_r:E_r^{p,q}\to E_r^{p+r,q-r+1}.
$$

Other books use different indexing conventions. Always check whether the author uses increasing or decreasing filtrations, homological or cohomological grading, and whether the first meaningful page is called $E_0$, $E_1$, or $E_2$.

## Why spectral sequences exist

Suppose you want to compute

$$
H(C,d).
$$

If $C$ is small, just compute the kernel and quotient by the image. No spectral sequence needed. Spectral sequences earn their keep when $C$ has an internal hierarchy.

Typical hierarchies are:

| Structure | What it means | QFT-shaped example |
|---|---|---|
| filtration | $C$ is organized by nested subspaces $F^pC$ | antifield number, derivative order, operator dimension, perturbative order |
| bigrading | $C=\bigoplus C^{p,q}$ | form degree plus ghost number, vertical plus horizontal degree |
| split differential | $d=d_0+d_1+\cdots$ | free plus interacting BRST differential, Koszul–Tate plus longitudinal differential |
| double complex | two differentials $d'$ and $d''$ with $d'^2=d''^2=d'd''+d''d'=0$ | BRST descent with $s$ and spacetime $d$ |

The goal is to replace a hard cohomology problem by a sequence of easier ones. The price is bookkeeping.

## Filtered complexes

A decreasing filtration on a cochain complex $C$ is a nested sequence

$$
\cdots\supseteq F^p C\supseteq F^{p+1}C\supseteq\cdots
$$

such that

$$
d(F^p C)\subseteq F^p C.
$$

This means the differential preserves the filtration. The associated graded pieces are

$$
\operatorname{gr}_F^p C
=\frac{F^pC}{F^{p+1}C}.
$$

The zeroth page is often

$$
E_0^{p,q}=\operatorname{gr}_F^p C^{p+q}.
$$

The differential induced by $d$ on this associated graded object is called $d_0$. Then

$$
E_1^{p,q}=H^{p,q}(E_0,d_0).
$$

The next differential $d_1$ is induced by the part of $d$ that changes filtration by one step. Then

$$
E_2=H(E_1,d_1).
$$

Continuing this process gives pages $E_r$ and differentials $d_r$.

The formal construction is more delicate than this summary, but the intuition is accurate: each page keeps classes that survived the previous approximations, and each new differential tests the next obstruction to lifting those classes to genuine cocycles of the full differential.

## What the pages mean

A class on the $E_0$ page is an element of the associated graded complex. It is an approximation to an actual cochain, where lower filtration corrections are temporarily ignored.

A class on the $E_1$ page is closed under the leading differential $d_0$, modulo $d_0$-exact terms.

A class on the $E_2$ page is a $d_0$-cohomology class that also survives the first correction $d_1$.

More generally, a class on $E_r$ has survived all previous tests:

$$
d_0,
\quad d_1,
\quad\ldots,
\quad d_{r-1}.
$$

The differential $d_r$ is the next obstruction. If $d_r[x]\ne0$, then $[x]$ dies on the next page. If $[x]$ is hit by $d_r$ from another class, then it also dies. What remains is

$$
E_{r+1}=\frac{\ker d_r}{\operatorname{im}d_r}.
$$

So spectral sequence pages are successive survival reports. Very bureaucratic, but in a good way.

## Convergence and associated graded cohomology

If the spectral sequence converges, it converges to a filtered version of the desired cohomology. More precisely, if $H^n(C)$ inherits a filtration $F^pH^n(C)$, then

$$
E_\infty^{p,n-p}
\simeq
\frac{F^pH^n(C)}{F^{p+1}H^n(C)}.
$$

The right-hand side is an associated graded piece.

This means that $E_\infty$ tells you the layers of $H$, not always how the layers glue together. Reconstructing $H$ from its associated graded may require solving extension problems.

For vector spaces over a field, extension issues are often harmless at the level of dimensions:

$$
\dim H^n(C)=\sum_p \dim E_\infty^{p,n-p}
$$

under finite-dimensional convergence assumptions. But for abelian groups, rings, modules, products, torsion, or filtered algebras, the extension data can be real information.

## Double complexes

A double complex is a bigraded object

$$
C^{p,q}
$$

with two differentials, usually called horizontal and vertical:

$$
d_h:C^{p,q}\to C^{p+1,q},
\qquad
 d_v:C^{p,q}\to C^{p,q+1},
$$

satisfying

$$
d_h^2=0,
\qquad
 d_v^2=0,
\qquad
 d_h d_v+d_v d_h=0.
$$

The total complex is

$$
\operatorname{Tot}^n C=\bigoplus_{p+q=n}C^{p,q},
$$

with total differential

$$
D=d_h+d_v.
$$

The anticommutation condition ensures

$$
D^2=0.
$$

A double complex produces spectral sequences by filtering the total complex by rows or columns. One route computes vertical cohomology first, then horizontal cohomology on the result. The other computes horizontal cohomology first, then vertical cohomology.

This is why one often hears statements like

$$
E_1^{p,q}=H_v^q(C^{p,\bullet}),
\qquad
E_2^{p,q}=H_h^p(H_v^q(C)).
$$

That means: first compute vertical cohomology, then compute horizontal cohomology of the vertical cohomology classes.

## A perturbative differential viewpoint

A particularly QFT-friendly picture is a differential split by degree:

$$
D=d_0+d_1+d_2+\cdots.
$$

The condition $D^2=0$ implies a hierarchy:

$$
d_0^2=0,
$$

$$
d_0d_1+d_1d_0=0,
$$

$$
d_1^2+d_0d_2+d_2d_0=0,
$$

and so on.

First compute

$$
E_1=H(d_0).
$$

The relation $d_0d_1+d_1d_0=0$ says that $d_1$ sends $d_0$-closed objects to $d_0$-closed objects and sends $d_0$-exact objects to $d_0$-exact objects. Therefore $d_1$ induces a differential on $H(d_0)$.

The next page is

$$
E_2=H(E_1,d_1).
$$

The higher differentials encode the corrections needed when a class can be made closed order by order. This is the algebraic skeleton behind many “start from free theory, add interactions, track which classes survive” arguments.

## BRST bicomplexes

BRST and BV formalisms often have more than one useful grading. A common split is

$$
s=\delta+\gamma+
\text{higher terms},
$$

where $\delta$ is the Koszul–Tate differential implementing equations of motion and constraints, while $\gamma$ is the longitudinal differential along gauge orbits. The precise names and degrees depend on the formulation.

The spectral-sequence strategy is:

1. Compute cohomology of the easiest piece, often $H(\delta)$.
2. Let the next piece, often $\gamma$, act on that cohomology.
3. Continue through higher pages if needed.

This is not cosmetic. It separates equations of motion, gauge equivalences, ghost number, and local form degree in a way that makes local BRST cohomology computable.

For anomaly descent, one often combines the BRST differential $s$ with the spacetime exterior derivative $d$:

$$
D=s+d.
$$

The descent equations are then components of the single equation

$$
D\Omega=0
$$

at fixed total degree. A bicomplex or filtered-complex viewpoint keeps track of which obstructions are $s$-exact, $d$-exact, or genuinely nontrivial.

## Equivariant cohomology and localization

Equivariant cohomology also has spectral-sequence shadows. In the Cartan model for a compact Lie group $G$ acting on a manifold $M$, one studies

$$
\left(S(\mathfrak g^*)\otimes\Omega^\bullet(M)\right)^G
$$

with the equivariant differential

$$
d_G=d-\iota_{\xi^a}u_a,
$$

schematically. Here the $u_a$ are polynomial variables and $\iota_{\xi^a}$ contracts with vector fields generated by the Lie algebra action. Different gradings count form degree and polynomial degree.

Localization formulas can be viewed, in part, as exploiting special features of equivariant cohomology. Spectral sequences are not always the shortest route to the localization formula, but they explain why filtered and graded structures naturally accompany equivariant arguments.

## A tiny toy example

Let $D=d_0+d_1$ with

$$
d_0^2=0,
\qquad
 d_0d_1+d_1d_0=0,
\qquad
 d_1^2=0.
$$

Suppose $x$ is $d_0$-closed:

$$
d_0x=0.
$$

Then

$$
d_0(d_1x)=-d_1(d_0x)=0,
$$

so $d_1x$ is also $d_0$-closed. If $x$ is changed by a $d_0$-exact term,

$$
x\mapsto x+d_0y,
$$

then

$$
d_1(x+d_0y)=d_1x+d_1d_0y
=d_1x-d_0d_1y.
$$

Thus $d_1x$ changes by a $d_0$-exact term. So $d_1$ defines a map on $H(d_0)$:

$$
[d_1]:H(d_0)\to H(d_0).
$$

This is the first nontrivial spectral-sequence differential. The second page is

$$
E_2=\frac{\ker([d_1]:H(d_0)\to H(d_0))}{\operatorname{im}([d_1]:H(d_0)\to H(d_0))}.
$$

In the simplest cases the sequence stops here. In more complicated filtered complexes, higher differentials appear because solving $Dx=0$ requires adding correction terms at several filtration levels.

## How to read a spectral sequence in practice

When you meet a spectral sequence in a QFT or mathematical-physics paper, ask five questions.

First, what is the target?

$$
\text{What cohomology is being computed?}
$$

Second, what is the filtration or bigrading?

$$
\text{What do }p\text{ and }q\text{ count?}
$$

Third, what is the first page that the author actually computes?

$$
E_0,
\quad E_1,
\quad\text{or}\quad E_2?
$$

Fourth, what are the differentials?

$$
d_r:E_r^{p,q}\to E_r^{p+r,q-r+1}
$$

in the chosen convention.

Fifth, what does convergence mean in this problem?

$$
E_\infty\Rightarrow H
\quad\text{or only}\quad
E_\infty\simeq\operatorname{gr}H?
$$

If you can answer those five questions, the spectral sequence has stopped being a wall of indices and started being a calculation.

## Common QFT patterns

### Solve constraints before gauge equivalences

In constrained systems, one often separates equations imposing constraints from gauge equivalences generated by constraints. A spectral sequence can compute the physical cohomology by first removing variables paired by one differential, then computing the residual gauge-invariant classes.

### Compute local BRST cohomology by antifield number

Local BRST cohomology often uses a filtration by antifield number. The first differential captures equations of motion and Noether identities. Later differentials incorporate gauge transformations and higher structure. This is one reason antifield number is not just a decoration; it is a computational filtration.

### Organize descent equations by form degree and ghost number

An anomaly in $d$ dimensions may be represented by a local $d$-form of ghost number $1$. Descent relates it to forms of different ghost number and form degree. The bicomplex with differentials $s$ and $d$ organizes which representatives are physically equivalent.

### Track perturbative corrections to protected operators

If a protected operator is closed under a leading differential but receives quantum corrections, a filtered complex can track whether the class survives. Higher differentials are the algebraic version of “the obstruction appears at this order.”

### Compute topological data from a skeletal filtration

In topology and phases of matter, one often filters a space by skeleta. The resulting spectral sequence computes generalized cohomology data stage by stage. This is one route to classifications involving characteristic classes, symmetry-protected phases, and anomaly inflow. The details belong elsewhere; the moral is that filtrations turn geometry into pages.

## Collapse and extension problems

A spectral sequence **collapses** at page $r$ if all later differentials vanish:

$$
E_r\simeq E_{r+1}\simeq\cdots\simeq E_\infty.
$$

Collapse is excellent news, but it is not always the end of the problem. If the target is an associated graded object, one may still need to solve extension problems to reconstruct the filtered object.

For example, suppose the associated graded pieces suggest two $\mathbb Z_2$ layers. The final group might be

$$
\mathbb Z_2\oplus\mathbb Z_2
$$

or it might be

$$
\mathbb Z_4.
$$

Both have associated graded pieces built from $\mathbb Z_2$ layers under suitable filtrations. The spectral sequence page alone may not distinguish them.

Over vector spaces, this issue is often invisible if one only counts dimensions. Over integral cohomology, torsion, module structures, ring structures, or categories, it can matter a lot.

## Common pitfalls

Do not call every staged computation a spectral sequence. A real spectral sequence has pages, differentials, and a target with convergence data.

Do not assume $E_2$ is the answer. Sometimes $E_2=E_\infty$; often it is not.

Do not forget that $E_\infty$ is usually the associated graded of the answer, not automatically the answer itself.

Do not mix homological and cohomological indexing conventions. In cohomology, a common differential is

$$
d_r:E_r^{p,q}\to E_r^{p+r,q-r+1}.
$$

In homology, arrows often point the other way. Sign and index mishaps here are impressively easy.

Do not ignore convergence assumptions. Infinite filtrations, nonbounded complexes, completion issues, and non-Hausdorff filtrations can all produce trouble.

Do not assume a collapsed spectral sequence preserves products, brackets, or pairings unless the multiplicative or structured version has been specified.

Do not use spectral sequences to hide a simple computation. If a direct kernel/image calculation fits on three lines, do that. Fancy machinery is wonderful; gratuitous fancy machinery is just academic fog machine.

## Exercises

### Exercise 1: The first induced differential

Let $D=d_0+d_1$, where $d_0^2=0$ and $d_0d_1+d_1d_0=0$. Prove that $d_1$ induces a well-defined map on $H(d_0)$.

<details><summary><strong>Solution</strong></summary>

If $x$ is $d_0$-closed, then

$$
d_0(d_1x)=-d_1(d_0x)=0,
$$

so $d_1x$ is $d_0$-closed.

If $x$ is changed by a $d_0$-exact term,

$$
x\mapsto x+d_0y,
$$

then

$$
d_1(x+d_0y)=d_1x+d_1d_0y
=d_1x-d_0d_1y.
$$

Thus $d_1x$ changes by a $d_0$-exact term. Therefore

$$
[x]\mapsto[d_1x]
$$

is well-defined on $H(d_0)$.

</details>

### Exercise 2: Double complex total differential

Let $d_h^2=d_v^2=0$ and $d_hd_v+d_vd_h=0$. Show that $D=d_h+d_v$ satisfies $D^2=0$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
D^2=(d_h+d_v)^2
=d_h^2+d_hd_v+d_vd_h+d_v^2.
$$

Using the assumptions,

$$
d_h^2=0,
\qquad
 d_v^2=0,
\qquad
 d_hd_v+d_vd_h=0.
$$

Therefore

$$
D^2=0.
$$

This is why a double complex gives a total complex.

</details>

### Exercise 3: Why $E_\infty$ may not be the full answer

Suppose a filtered abelian group $H$ has

$$
0\subset F^1H\subset F^0H=H
$$

with

$$
F^1H\simeq\mathbb Z_2,
\qquad
F^0H/F^1H\simeq\mathbb Z_2.
$$

Give two possible groups $H$ with these associated graded pieces.

<details><summary><strong>Solution</strong></summary>

One possibility is

$$
H=\mathbb Z_2\oplus\mathbb Z_2,
$$

with $F^1H$ equal to one direct summand. Then

$$
F^1H\simeq\mathbb Z_2,
\qquad
H/F^1H\simeq\mathbb Z_2.
$$

Another possibility is

$$
H=\mathbb Z_4,
$$

with

$$
F^1H=2\mathbb Z_4\simeq\mathbb Z_2.
$$

Then

$$
H/F^1H\simeq\mathbb Z_4/2\mathbb Z_4\simeq\mathbb Z_2.
$$

Thus the associated graded pieces alone do not determine the extension.

</details>

### Exercise 4: A collapsed two-column sequence over a field

Suppose a finite-dimensional spectral sequence over a field has only two nonzero columns, $p=0$ and $p=1$, and all possible higher differentials vanish for degree reasons after $E_2$. What can you say about $\dim H^n$ if the sequence converges to $H$?

<details><summary><strong>Solution</strong></summary>

If all higher differentials vanish after $E_2$, then

$$
E_2=E_\infty.
$$

For a convergent finite-dimensional spectral sequence over a field, the dimensions of the associated graded pieces add to the dimension of the filtered vector space. Therefore

$$
\dim H^n
=\sum_{p+q=n}\dim E_\infty^{p,q}
=\dim E_2^{0,n}+\dim E_2^{1,n-1}.
$$

Over a field, there is no hidden group extension issue at the level of vector-space dimension, although product or filtration data may still matter.

</details>

## Further reading

For spectral sequences in algebraic topology, see McCleary, Bott–Tu, Hatcher, and May. For homological algebra, see Weibel, Gelfand–Manin, and Mac Lane. For applications to differential geometry and equivariant cohomology, see Bott–Tu, Nakahara, Frankel, and localization references. For BRST, BV, and local cohomology applications in gauge theory and anomalies, see Henneaux–Teitelboim and the local BRST cohomology literature.

## Version history

- 2026-06-26: Initial polished draft. Introduced filtered complexes, pages, differentials, convergence, associated graded targets, double complexes, BRST bicomplexes, descent equations, equivariant examples, pitfalls, and exercises.
