---
title: "Cohomology"
description: "Explains cohomology as closed data modulo exact data, with induced maps, quasi-isomorphisms, exact sequences, products, pairings, and QFT examples from de Rham theory, BRST quantization, anomalies, localization, conserved currents, and deformation problems."
sidebar:
  label: "Cohomology"
  order: 4
level: Advanced
status: "Polished draft"
source: "Standard references on algebraic topology, homological algebra, differential geometry, BRST methods, deformation theory, anomalies, and mathematical physics, including Bott–Tu, Hatcher, Weibel, Gelfand–Manin, Mac Lane, Nakahara, Frankel, Henneaux–Teitelboim, Weinberg, Srednicki, Schwartz, Zinn-Justin, and modern references on cohomological and derived methods in QFT."
topics:
  - cohomology
  - cohomology class
  - exact element
  - closed element
  - quasi-isomorphism
  - chain map
  - exact sequence
  - long exact sequence
  - de Rham cohomology
  - BRST cohomology
  - descent equations
  - anomaly
  - localization
canonicalTopics:
  - cohomology
  - cohomology-class
  - exact-element
  - closed-element
  - quasi-isomorphism
  - chain-map
  - exact-sequence
  - long-exact-sequence
  - de-rham-cohomology
  - brst-cohomology
  - descent-equation
  - anomaly
  - localization
researchStatus:
  established:
    - "Cohomology as closed elements modulo exact elements is a standard construction in algebraic topology, differential geometry, homological algebra, BRST quantization, anomaly descent, and cohomological field theory."
    - "Chain maps induce maps on cohomology, homotopic maps induce the same map on cohomology, and quasi-isomorphisms preserve cohomological information."
  active:
    - "Derived, factorization, and higher-categorical versions of cohomology continue to organize modern BV–BRST theory, deformation quantization, extended operators, anomalies, and mathematical formulations of QFT."
---

## Summary

Cohomology is the construction

$$
H^n(C,d)=\frac{\ker(d:C^n\to C^{n+1})}{\operatorname{im}(d:C^{n-1}\to C^n)}.
$$

In words: **cohomology is closed data modulo exact data**.

That phrase sounds modest, but it is one of the main algebraic patterns in QFT. A gauge-invariant observable is often a closed object. A gauge-trivial observable is often an exact object. A physical state in BRST quantization is closed under the BRST charge, modulo states that are BRST-exact. A conserved current defines a cohomology class only after improvements and trivial currents have been removed. An anomaly is an obstruction class: it matters precisely because it cannot be written away as an exact counterterm.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Diagram showing cohomology as closed representatives modulo exact shifts, with a differential from C^{n-1} to C^n to C^{n+1}, an exact subspace inside the closed subspace, and QFT examples including de Rham classes, BRST states, anomalies, and localization.](/figures/math-toolkit/cohomology-quotient-flow.svg)

<figcaption>

Cohomology extracts the part of a closed condition that survives exact redefinitions. The same quotient pattern appears in de Rham forms, BRST physical states, anomaly descent, supersymmetric localization, conserved currents, and deformation problems.

</figcaption>
</figure>

The point is not to worship quotients. The point is to stop confusing three different things:

$$
\text{closed},
\qquad
\text{exact},
\qquad
\text{nontrivial in cohomology}.
$$

A closed object solves an equation. An exact object is a trivial solution of that equation. A nonzero cohomology class is a solution that cannot be trivialized.

:::note[Core slogan]
Cohomology is the algebra of “solves the constraint” modulo “is pure convention, pure gauge, or pure improvement.”
:::

## Prerequisites and conventions

You should know [Chain Complexes](/math-toolkit/algebraic-categorical-language/chain-complexes/), quotient vector spaces, kernels, images, and the basic language of [Graded Algebras](/math-toolkit/algebraic-categorical-language/graded-algebras/). Useful nearby pages include [Exterior Algebra](/math-toolkit/linear-algebra-tensors/exterior-algebra/), [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/), [De Rham Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/de-rham-cohomology/), [Čech Cohomology Preview](/math-toolkit/topology-cohomology-characteristic-classes/cech-cohomology-preview/), and [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/).

This page uses cochain conventions by default:

$$
d:C^n\to C^{n+1},
\qquad
 d^2=0.
$$

The degree may be form degree, ghost number, cohomological degree, total degree, or another grading. When the degree is not important, we simply write $C$ for the whole complex and $H(C,d)$ for its cohomology.

## From equations to quotient spaces

Let

$$
\cdots\to C^{n-1}\xrightarrow{d}C^n\xrightarrow{d}C^{n+1}\to\cdots
$$

be a cochain complex. The equation

$$
dx=0,
\qquad x\in C^n,
$$

selects the closed elements

$$
Z^n(C)=\ker(d:C^n\to C^{n+1}).
$$

The elements of the form

$$
x=dy,
\qquad y\in C^{n-1},
$$

are exact:

$$
B^n(C)=\operatorname{im}(d:C^{n-1}\to C^n).
$$

Since $d^2=0$, every exact element is closed:

$$
B^n(C)\subseteq Z^n(C).
$$

Therefore the quotient

$$
H^n(C)=Z^n(C)/B^n(C)
$$

is defined. A class is written

$$
[x]\in H^n(C).
$$

If $x$ and $x'$ are two closed elements, then

$$
[x]=[x']
$$

precisely when there exists $y\in C^{n-1}$ such that

$$
x'=x+dy.
$$

So a cohomology class is not a particular element. It is an equivalence class of representatives.

This is the source of a useful but slightly dangerous phrase: “choose a representative.” Representatives are convenient for computation, but cohomology classes are what survive changes of representative.

## What the quotient means in QFT

The abstract quotient becomes physical whenever two descriptions should be identified.

In de Rham theory, a closed form $\omega$ satisfies

$$
d\omega=0.
$$

If

$$
\omega\sim \omega+d\alpha,
$$

then integrals over closed cycles are unchanged:

$$
\int_\Sigma (\omega+d\alpha)=\int_\Sigma \omega+\int_{\partial\Sigma}\alpha
=\int_\Sigma \omega
\qquad (\partial\Sigma=\varnothing).
$$

Thus de Rham cohomology remembers periods and topological charges, not arbitrary local potentials.

In BRST quantization, the BRST charge $Q$ satisfies

$$
Q^2=0.
$$

Physical states are often defined by

$$
Q|\psi\rangle=0,
$$

with the equivalence relation

$$
|\psi\rangle\sim |\psi\rangle+Q|\chi\rangle.
$$

So the physical state space is a cohomology:

$$
\mathcal H_{\mathrm{phys}}\simeq H_Q.
$$

The exact states are not merely inconvenient. They are precisely the states that should not be counted as new physical states.

In supersymmetric localization, one often chooses a nilpotent or square-zero-up-to-symmetry supercharge $Q$. Observables in the $Q$-cohomology have correlation functions insensitive to $Q$-exact deformations:

$$
S\longmapsto S+t\,Q V.
$$

Under suitable assumptions on the measure and boundary behavior in field space,

$$
\frac{d}{dt}\langle\mathcal O\rangle_t
=-\langle \mathcal O\,QV\rangle_t
=0
$$

for $Q\mathcal O=0$. That is the practical engine behind localization: exact deformations change representatives, not cohomology classes.

In anomaly theory, cohomology separates removable local terms from genuine obstructions. If an anomalous variation can be written as the variation of a local counterterm, it is cohomologically trivial. If it cannot, it is a real anomaly.

Tiny quotient, enormous consequences. Classic mathematical physics move.

## The zeroth cohomology

The group $H^0$ is often the easiest way to understand a complex.

For a cochain complex beginning at degree $0$,

$$
0\to C^0\xrightarrow{d}C^1\xrightarrow{d}C^2\to\cdots,
$$

there is no incoming map to $C^0$, so

$$
H^0(C)=\ker(d:C^0\to C^1).
$$

There are no exact degree-zero elements unless the complex has negative degrees.

For the de Rham complex on a connected manifold $M$,

$$
H^0_{\mathrm{dR}}(M)
=\{f\in C^\infty(M):df=0\}
\simeq \mathbb R.
$$

So $H^0$ counts locally constant functions. More generally, if $M$ has $k$ connected components,

$$
H^0_{\mathrm{dR}}(M)\simeq \mathbb R^k.
$$

In symmetry problems, $H^0$ often means invariants. If $Q$ is a nilpotent differential acting on observables, then

$$
H^0_Q
$$

may be the space of degree-zero observables that are invariant under $Q$, modulo degree-zero exact redundancies if negative-degree objects exist.

## First cohomology and deformations

The first cohomology often measures inequivalent first-order deformations.

A schematic deformation problem has an object $\Phi$ and a differential $d_\Phi$ that linearizes the equivalence relation around it. A first-order deformation $\delta\Phi$ is allowed if it satisfies a linearized equation

$$
d_\Phi(\delta\Phi)=0.
$$

But if $\delta\Phi=d_\Phi\epsilon$, then the deformation is induced by an infinitesimal redundancy, such as a gauge transformation or field redefinition. Inequivalent infinitesimal deformations are therefore classes in

$$
H^1(d_\Phi).
$$

This is a schema, not a theorem by itself. The precise complex depends on the problem. But the pattern is stable: closed means “allowed to first order,” exact means “trivial to first order,” and cohomology means “really new to first order.”

The next cohomology group often controls obstructions. A first-order deformation may fail at second order by a term that is closed. If that obstruction is exact, it can be removed by a correction. If it defines a nonzero class in $H^2$, the deformation stops. This is why deformation theory and QFT keep producing phrases like “the obstruction lives in cohomology.”

## Chain maps and induced maps

A map of complexes

$$
f:(C,d_C)\to(D,d_D)
$$

is a degree-preserving map satisfying

$$
f d_C=d_D f.
$$

This condition says that $f$ sends closed elements to closed elements:

$$
d_C x=0
\quad\Longrightarrow\quad
 d_D f(x)=f(d_Cx)=0,
$$

and exact elements to exact elements:

$$
x=d_Cy
\quad\Longrightarrow\quad
 f(x)=f(d_Cy)=d_Df(y).
$$

Therefore $f$ induces a map on cohomology,

$$
H^n(f):H^n(C)\to H^n(D),
\qquad
[x]\mapsto[f(x)].
$$

This is one of the main reasons cohomology is robust: it is not just a set of groups. It is functorial. Compatible maps before cohomology become maps after cohomology.

In QFT, this matters whenever one compares two presentations of the same theory, two gauges, two regulators, two equivalent complexes, or two descriptions related by a field redefinition. The map should respect the differential before it deserves to descend to physical or cohomological data.

## Homotopies and quasi-isomorphisms

Two chain maps $f,g:C\to D$ are homotopic if their difference is $d$-exact as a map. In cochain notation, this means there is a degree-$-1$ map

$$
h:C^n\to D^{n-1}
$$

such that

$$
f-g=d_Dh+h d_C.
$$

If $x$ is closed, then

$$
(f-g)(x)=d_Dh(x)+h(d_Cx)=d_Dh(x),
$$

so $f(x)$ and $g(x)$ differ by an exact element. Hence homotopic maps induce the same map on cohomology:

$$
H(f)=H(g).
$$

A chain map $f:C\to D$ is a **quasi-isomorphism** if it induces an isomorphism on cohomology:

$$
H^n(f):H^n(C)\xrightarrow{\sim}H^n(D)
$$

for all $n$.

A quasi-isomorphism need not be an isomorphism of complexes. It may throw away contractible or acyclic pieces while preserving cohomology. This is exactly why quasi-isomorphisms are the correct equivalences in much of homological algebra and derived QFT language.

Physics translation: two descriptions may have different auxiliary fields, ghosts, gauge-fixing data, or off-shell variables, while having the same physical cohomology. The auxiliary junk is not false; it is acyclic.

## Acyclic pairs and the doublet lemma

A small but powerful example is a $Q$-doublet. Suppose $u$ and $v$ satisfy

$$
Q u=v,
\qquad
Qv=0.
$$

Then $v$ is closed, but also exact:

$$
v=Qu.
$$

The pair $(u,v)$ contributes no cohomology if it appears as an isolated contractible pair. More generally, a complex of the form

$$
0\to \mathbb F u\xrightarrow{Q}\mathbb F v\to 0
$$

with $Qu=v$ is acyclic:

$$
H=0.
$$

This simple fact underlies a lot of “unphysical variables do not contribute” arguments in BRST theory and supersymmetric localization. Gauge-fixing multiplets, auxiliary variables, and paired bosonic/fermionic fluctuations often form exact pairs. Their determinants may matter, but their cohomological classes do not.

## Exact sequences and connecting maps

A short exact sequence of complexes is a sequence

$$
0\to A\xrightarrow{i}B\xrightarrow{p}C\to0
$$

such that each degree is exact:

$$
0\to A^n\xrightarrow{i}B^n\xrightarrow{p}C^n\to0,
$$

and the maps commute with the differentials.

This produces a long exact sequence in cohomology:

$$
\cdots\to
H^n(A)\xrightarrow{i_*}
H^n(B)\xrightarrow{p_*}
H^n(C)\xrightarrow{\delta}
H^{n+1}(A)\to\cdots.
$$

The connecting map $\delta$ is often where obstructions live. Given a closed class $[c]\in H^n(C)$, lift $c$ to some $b\in B^n$ with $p(b)=c$. Since $c$ is closed,

$$
p(db)=d p(b)=dc=0.
$$

Exactness says $db$ comes from an element of $A^{n+1}$:

$$
db=i(a).
$$

The class $[a]\in H^{n+1}(A)$ is $\delta[c]$. If $\delta[c]\ne0$, the class in $C$ cannot be lifted to a closed class in $B$.

This is the clean algebraic version of a common physics statement: “there is an obstruction to lifting the symmetry, observable, deformation, or background.”

## Products in cohomology

If $C$ is a differential graded algebra, then it has a product and a differential satisfying a graded Leibniz rule:

$$
d(ab)=(da)b+(-1)^{|a|}a(db).
$$

If $a$ and $b$ are closed, then

$$
d(ab)=0.
$$

If $a$ is shifted by an exact element, $a\mapsto a+d\alpha$, then

$$
(a+d\alpha)b=ab+d(\alpha b)
$$

provided $b$ is closed, up to the sign dictated by the graded Leibniz rule. Therefore the product descends to cohomology:

$$
[a][b]=[ab].
$$

For the de Rham complex, this gives the wedge product on de Rham cohomology:

$$
[\omega]\wedge[\eta]=[\omega\wedge\eta].
$$

The same idea appears in the product of BRST cohomology classes, the OPE of topological observables, and the cup product in topological classifications.

Products in cohomology often remember more than dimensions of cohomology groups. The graded ring structure can distinguish spaces or theories with the same Betti numbers. In QFT language, the product tells you how protected operators multiply, not just how many of them exist.

## Pairings and observables

Cohomology becomes observable when paired with dual data.

For de Rham cohomology, a closed $p$-form $\omega$ can be paired with a closed $p$-cycle $\Sigma$:

$$
\langle [\omega],[\Sigma]\rangle
=\int_\Sigma\omega.
$$

This is well-defined because exact shifts integrate to zero over closed cycles:

$$
\int_\Sigma d\alpha=\int_{\partial\Sigma}\alpha=0.
$$

This is the geometric prototype of many QFT observables. A topological charge pairs a cohomology class with a cycle. A Wilson line pairs a connection with a loop through holonomy. A background field pairs with a conserved current. An anomaly polynomial pairs characteristic classes with spacetime cycles.

The general moral is simple: if an observable depends only on a cohomology class, then it should not change under exact redefinitions.

## Cohomology of symmetries and currents

Conserved currents also have a cohomological flavor. A conserved current $j^\mu$ satisfies

$$
\partial_\mu j^\mu=0.
$$

In differential-form language on a $d$-dimensional spacetime, the Hodge dual

$$
\star j
$$

is a closed $(d-1)$-form:

$$
d\star j=0.
$$

The associated charge over a spatial slice $\Sigma$ is

$$
Q_\Sigma=\int_\Sigma\star j.
$$

If the current is improved by an exact term,

$$
\star j\longmapsto \star j+d\Lambda,
$$

then the charge on a closed slice changes by

$$
\int_\Sigma d\Lambda=\int_{\partial\Sigma}\Lambda.
$$

For $\partial\Sigma=\varnothing$, the charge is unchanged. So charges are naturally insensitive to improvement terms. Again: closed modulo exact.

For higher-form symmetries, the same structure becomes even more literal. A conserved $(q+1)$-form current can be written as a closed form whose integrals over linking cycles define topological operators. Exact redefinitions are improvement terms.

## BRST cohomology of observables

Let $Q$ be the BRST differential. An operator $\mathcal O$ is BRST-closed if

$$
Q\mathcal O=0.
$$

It is BRST-exact if

$$
\mathcal O=Q\mathcal V.
$$

Correlation functions of exact observables vanish under suitable assumptions:

$$
\langle Q\mathcal V\rangle=0.
$$

More generally, insertion of a $Q$-exact operator into correlators of $Q$-closed operators should vanish if the measure is $Q$-invariant and there are no boundary contributions in field space. Therefore the physical observables are classes

$$
[\mathcal O]\in H_Q.
$$

This statement is powerful but not automatic magic. Boundary terms, zero modes, anomalies in the measure, and noncompact field spaces can spoil naive $Q$-exact decoupling. Good cohomological arguments always state the hypotheses under which exact terms decouple.

## Descent and anomalies

Anomaly descent uses cohomology twice: once for spacetime forms and once for gauge or BRST variation.

A schematic descent sequence has forms $I_{d+2}$, $I_{d+1}^{(0)}$, and $I_d^{(1)}$ satisfying

$$
I_{d+2}=d I_{d+1}^{(0)},
$$

and

$$
s I_{d+1}^{(0)}+d I_d^{(1)}=0,
$$

where $s$ is a BRST differential. The local anomaly is represented by $I_d^{(1)}$. Changing local counterterms shifts representatives by exact or $s$-exact terms. The anomaly is meaningful only as a cohomology class.

This is why “the anomaly polynomial” and “the anomaly” are related but not identical objects. The polynomial packages a characteristic class in one degree higher; descent extracts a local representative; cohomology tells which part is invariant under allowed redefinitions.

## Local versus global cohomology

A common trap is to compute a local cohomology and assume it is the full answer.

On a contractible patch, the Poincaré lemma says every closed de Rham form of positive degree is locally exact. But global topology can still make a closed form non-exact globally. For example, on the circle $S^1$, the form $d\theta$ is closed, but not globally exact as the derivative of a single-valued function:

$$
\int_{S^1} d\theta=2\pi\ne0.
$$

Local exactness does not kill global periods.

The same warning applies in QFT. A current may be locally improved away but still carry global charge. A gauge field may be locally pure gauge but have nontrivial holonomy. A line bundle may be locally trivial but have nonzero Chern class. A local anomaly calculation may miss global anomalies.

Cohomology is, in part, the art of not mistaking local triviality for global triviality.

## Cohomology and filtration

Many QFT complexes have more than one grading. For example, a BRST complex may have ghost number, antifield number, form degree, and polynomial degree. A descent problem may combine a spacetime differential $d$ and a BRST differential $s$ into a total differential

$$
D=s+d.
$$

If the complex is filtered, one can compute its cohomology in stages. This is the natural entrance to [Spectral Sequences Preview](/math-toolkit/algebraic-categorical-language/spectral-sequences-preview/). The slogan is:

$$
\text{filtered complex}
\quad\leadsto\quad
\text{successive pages of approximate cohomology}
\quad\leadsto\quad
\text{associated graded of }H.
$$

You do not need spectral sequences for every cohomology computation. But when a differential splits into simpler pieces,

$$
d=d_0+d_1+d_2+\cdots,
$$

or when a double complex is present, spectral sequences are the disciplined way to compute without handwaving.

## Common pitfalls

Do not say that cohomology is “the kernel.” The kernel is the space of closed objects. Cohomology is the kernel modulo the image.

Do not say exact elements are zero. They are zero **in cohomology**. As representatives inside the original complex, they may be nonzero and may affect intermediate formulas.

Do not identify a class with a preferred representative unless a gauge, metric, harmonic condition, or normalization has been chosen. On a Riemannian compact manifold, Hodge theory gives harmonic representatives, but that is extra structure.

Do not assume local exactness implies global exactness. The Poincaré lemma is local. Topology lives in the failure to patch local primitives globally.

Do not assume equal cohomology groups imply equal theories. Cohomology may forget products, pairings, filtrations, gradings, operations, or dynamics.

Do not ignore boundary conditions. Cohomology can change when one uses compact support, relative cohomology, boundary conditions, falloff conditions at infinity, or allowed singularities.

Do not treat BRST cohomology as automatically physical without checking nilpotency, gauge fixing, anomalies, inner products, and boundary contributions in field space.

## Exercises

### Exercise 1: Cohomology of a two-term exact pair

Let $C^0=\mathbb F u$, $C^1=\mathbb F v$, and $d u=v$, with $d v=0$. Compute $H^0(C)$ and $H^1(C)$.

<details><summary><strong>Solution</strong></summary>

In degree $0$,

$$
H^0(C)=\ker(d:C^0\to C^1).
$$

Since $du=v\ne0$, the kernel is zero, so

$$
H^0(C)=0.
$$

In degree $1$,

$$
H^1(C)=\ker(d:C^1\to0)/\operatorname{im}(d:C^0\to C^1).
$$

The kernel is all of $C^1=\mathbb F v$, and the image is also all of $C^1$, because $du=v$. Therefore

$$
H^1(C)=0.
$$

This is the simplest acyclic doublet.

</details>

### Exercise 2: Closed one-forms on the circle

Let $\theta$ be the angular coordinate on $S^1$. Show that $d\theta$ is closed but not exact as a globally defined one-form on $S^1$.

<details><summary><strong>Solution</strong></summary>

Since $d^2=0$,

$$
d(d\theta)=0,
$$

so $d\theta$ is closed.

If $d\theta=df$ for a globally defined smooth function $f:S^1\to\mathbb R$, then integrating around the circle would give

$$
\int_{S^1}d\theta=\int_{S^1}df=0,
$$

because the integral of an exact one-form over a closed loop vanishes. But

$$
\int_{S^1}d\theta=2\pi.
$$

Therefore $d\theta$ is not exact globally. It represents a nonzero class in $H^1_{\mathrm{dR}}(S^1)$.

</details>

### Exercise 3: Induced maps on cohomology

Let $f:(C,d_C)\to(D,d_D)$ be a chain map, so $f d_C=d_D f$. Prove that $[x]\mapsto[f(x)]$ is well-defined on cohomology.

<details><summary><strong>Solution</strong></summary>

First, if $x$ is closed, then

$$
d_D f(x)=f(d_Cx)=f(0)=0,
$$

so $f(x)$ is closed.

Second, suppose $x$ and $x'$ represent the same cohomology class. Then

$$
x'=x+d_Cy
$$

for some $y$. Applying $f$ gives

$$
f(x')=f(x)+f(d_Cy)=f(x)+d_Df(y).
$$

Thus $f(x')$ and $f(x)$ differ by an exact element in $D$, so they represent the same cohomology class. Therefore the induced map

$$
H(f):[x]\mapsto[f(x)]
$$

is well-defined.

</details>

### Exercise 4: Exactness and lifting obstruction

Suppose

$$
0\to A\xrightarrow{i}B\xrightarrow{p}C\to0
$$

is a short exact sequence of complexes. Let $c\in C^n$ be closed and choose $b\in B^n$ with $p(b)=c$. Explain why $db$ determines a class in $H^{n+1}(A)$.

<details><summary><strong>Solution</strong></summary>

Since $p$ is a chain map,

$$
p(db)=d p(b)=dc=0.
$$

Exactness at $B^{n+1}$ says that $\ker p=\operatorname{im}i$, so there is an $a\in A^{n+1}$ such that

$$
i(a)=db.
$$

Now

$$
i(da)=d i(a)=d(db)=0.
$$

Because $i$ is injective, $da=0$. Hence $a$ is closed and defines a class

$$
[a]\in H^{n+1}(A).
$$

One can also check that changing the lift $b$ changes $a$ only by an exact element, so this class is independent of choices. It is the connecting homomorphism applied to $[c]$.

</details>

## Further reading

For algebraic topology and ordinary cohomology, see Hatcher, Bott–Tu, and May. For homological algebra, see Weibel, Mac Lane, and Gelfand–Manin. For geometry and physics applications, see Nakahara and Frankel. For BRST and BV cohomology, see Henneaux–Teitelboim and the local BRST cohomology literature. For QFT contexts, standard discussions of gauge fixing, ghosts, anomalies, localization, and topological field theory in Weinberg, Srednicki, Schwartz, Zinn-Justin, and related texts provide the physics side of the same quotient idea.

## Version history

- 2026-06-26: Initial polished draft. Introduced cohomology classes, functoriality, quasi-isomorphisms, exact sequences, products, pairings, BRST examples, anomaly descent, pitfalls, and exercises.
