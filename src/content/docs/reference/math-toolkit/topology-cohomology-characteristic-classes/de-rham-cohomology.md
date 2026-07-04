---
title: "de Rham Cohomology"
description: "Defines de Rham cohomology as closed differential forms modulo exact forms and explains periods, Stokes’ theorem, integral refinements, and QFT applications."
sidebar:
  label: "de Rham Cohomology"
  order: 5
level: Advanced
status: "Polished draft"
source: "Standard differential topology and mathematical physics references, including Nakahara, Frankel, Bott–Tu, Hatcher, Eguchi–Gilkey–Hanson, and geometry-based QFT treatments of fluxes, theta terms, and anomalies."
topics:
  - de Rham cohomology
  - differential forms
  - closed forms
  - exact forms
  - periods
  - Stokes theorem
  - Poincare lemma
  - flux quantization
  - theta terms
  - characteristic classes
canonicalTopics:
  - de-rham-cohomology
  - closed-form
  - exact-form
  - period
  - stokes-theorem
  - poincare-lemma
  - flux
  - theta-term
  - characteristic-class
researchStatus:
  established:
    - "De Rham cohomology is the standard real cohomology theory of smooth manifolds, identifying closed differential forms modulo exact forms and pairing them with homology cycles by integration."
  active:
    - "QFT often requires refinements beyond de Rham cohomology, including integral cohomology, differential cohomology, equivariant cohomology, torsion, spin structures, generalized cohomology, and cobordism."
---

## Summary

De Rham cohomology is the cohomology theory built from differential forms. A $p$-form $\omega$ is **closed** if

$$
d\omega=0,
$$

and **exact** if

$$
\omega=d\alpha
$$

for some $(p-1)$-form $\alpha$. Since $d^2=0$, every exact form is closed. The $p$th de Rham cohomology group is

$$
H^p_{\mathrm{dR}}(M)=\frac{\{\omega\in\Omega^p(M):d\omega=0\}}
{\{d\alpha:\alpha\in\Omega^{p-1}(M)\}}.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Diagram showing differential forms, closed forms, exact forms, de Rham classes, periods over cycles, Stokes' theorem, and QFT uses such as fluxes, theta terms, anomalies, and charges.](/figures/math-toolkit/de-rham-cohomology-flow.svg)

<figcaption>

De Rham cohomology keeps the global part of a closed form after quotienting by exact forms. Its most physical observable is a period $\int_{\Sigma_p}\omega$ over a closed $p$-cycle.

</figcaption>
</figure>

The slogan is

$$
\text{closed forms modulo exact forms measure global fluxes}.
$$

De Rham cohomology turns local calculus into global topology. Locally, a closed form is exact by the Poincaré lemma. Globally, it may fail to be exact, and that failure is measured by periods over cycles. This is why a field strength may satisfy $dF=0$ but still have nonzero magnetic flux, why theta terms can depend only on topological sectors, and why characteristic forms built from curvature can represent global bundle data.

The main caveat is that de Rham cohomology uses real coefficients. It sees continuous periods but misses torsion. Flux quantization, discrete theta angles, spin structures, global anomalies, and many modern QFT refinements require integral, differential, equivariant, or generalized cohomology.

## Prerequisites

Read [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) for wedge products and exterior derivatives, and [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) for orientation and Stokes’ theorem.

Read [Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) for cycles, boundaries, cochains, and the pairing between homology and cohomology. Read [Degree of a Map](/math-toolkit/topology-cohomology-characteristic-classes/degree-of-a-map/) for a first major application of de Rham classes to topological charges.

For gauge-theory motivation, read [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/).

## Core idea

The exterior derivative

$$
d:\Omega^p(M)\to\Omega^{p+1}(M)
$$

satisfies

$$
d^2=0.
$$

This simple identity creates a cochain complex:

$$
0\longrightarrow \Omega^0(M)
\xrightarrow{d}\Omega^1(M)
\xrightarrow{d}\Omega^2(M)
\xrightarrow{d}\cdots.
$$

At degree $p$, there are two distinguished spaces:

$$
Z^p(M)=\ker\left(d:\Omega^p(M)\to\Omega^{p+1}(M)\right),
$$

called closed $p$-forms, and

$$
B^p(M)=\operatorname{im}\left(d:\Omega^{p-1}(M)\to\Omega^p(M)\right),
$$

called exact $p$-forms. Since $d^2=0$,

$$
B^p(M)\subset Z^p(M).
$$

De Rham cohomology is the quotient

$$
H^p_{\mathrm{dR}}(M)=Z^p(M)/B^p(M).
$$

Two closed forms represent the same de Rham class if they differ by an exact form:

$$
\omega\sim\omega+d\alpha.
$$

This quotient is not some abstract bureaucratic move. It is forced by Stokes’ theorem. If $\Sigma_p$ is a closed $p$-cycle, meaning $\partial\Sigma_p=0$, then

$$
\int_{\Sigma_p}(\omega+d\alpha)=\int_{\Sigma_p}\omega+\int_{\Sigma_p}d\alpha
=\int_{\Sigma_p}\omega+\int_{\partial\Sigma_p}\alpha
=\int_{\Sigma_p}\omega.
$$

So exact changes do not affect periods over closed cycles. De Rham classes are exactly the data that such periods can detect.

## Setup and conventions

Let $M$ be a smooth manifold. The vector space of smooth $p$-forms is denoted

$$
\Omega^p(M).
$$

The de Rham cohomology groups are real vector spaces:

$$
H^p_{\mathrm{dR}}(M)
$$

uses coefficients in $\mathbb R$. When $M$ has several connected components, $H^0_{\mathrm{dR}}(M)$ has one copy of $\mathbb R$ for each connected component.

If $M$ is compact, oriented, and $n$-dimensional, integration over $M$ pairs top-degree de Rham classes with the fundamental class:

$$
H^n_{\mathrm{dR}}(M)\times H_n(M;\mathbb R)\to\mathbb R,
\qquad
([\omega],[M])\mapsto \int_M\omega.
$$

More generally, a closed $p$-form $\omega$ pairs with a $p$-cycle $\Sigma$ by

$$
\langle[\omega],[\Sigma]\rangle=\int_\Sigma\omega.
$$

The notation $[\omega]$ means the de Rham cohomology class of a closed form, not its pointwise value.

## Stokes’ theorem and why exact forms vanish on cycles

Stokes’ theorem says that for a compact oriented $(p+1)$-chain $C$,

$$
\int_C d\alpha=\int_{\partial C}\alpha.
$$

If $\Sigma$ is a closed $p$-cycle, then $\partial\Sigma=0$. Therefore, for any exact $p$-form $d\alpha$,

$$
\int_\Sigma d\alpha=\int_{\partial\Sigma}\alpha=0.
$$

This explains why exact forms are invisible to periods over closed cycles.

Conversely, on a compact oriented manifold, the de Rham theorem says that periods over cycles detect de Rham cohomology classes. More precisely,

$$
H^p_{\mathrm{dR}}(M)\simeq H^p(M;\mathbb R).
$$

Thus de Rham cohomology is not a new kind of topology separate from singular or cellular cohomology. It is the smooth differential-form model of real cohomology.

This is the clean source of a common QFT pattern:

$$
\text{local density} \quad \longrightarrow \quad \text{closed form} \quad \longrightarrow \quad \text{global period}.
$$

The local density may look like ordinary calculus, but the quantization or topological invariance comes from the cohomology class and the integration cycle.

## The Poincaré lemma

The Poincaré lemma says that on a contractible open set $U$, every closed form of positive degree is exact:

$$
d\omega=0\quad\Longrightarrow\quad \omega=d\alpha
\qquad \text{on }U,
\quad p>0.
$$

Physically, this means that de Rham cohomology is global. Locally there is no obstruction to writing a closed field strength as a derivative of a potential. Globally, the potentials may fail to patch into a single globally defined form.

The magnetic monopole is the canonical example. On $S^2$ surrounding a monopole, the field strength $F$ is a closed two-form:

$$
dF=0
$$

away from the monopole. Locally, $F=dA$ on northern and southern patches. But if

$$
\int_{S^2}F\ne0,
$$

then $F$ cannot equal $dA$ for one globally defined one-form $A$ on all of $S^2$, because Stokes’ theorem would give

$$
\int_{S^2}dA=\int_{\partial S^2}A=0.
$$

So the obstruction is not in the local equation $dF=0$. It is in the global cohomology class $[F]\in H^2_{\mathrm{dR}}(S^2)$.

## Periods

A period of a closed $p$-form $\omega$ is an integral over a closed $p$-cycle:

$$
\int_{\Sigma_p}\omega.
$$

Periods are the observable numbers attached to de Rham classes. If

$$
\omega\to\omega+d\alpha,
$$

then the period over any closed cycle is unchanged.

If $\{\Sigma_i\}$ is a basis of $H_p(M;\mathbb R)$ and $\omega$ is closed, the periods

$$
\int_{\Sigma_i}\omega
$$

are coordinates for the de Rham class $[\omega]$ in the dual basis.

For QFT, periods are everywhere:

$$
\frac{1}{2\pi}\int_{\Sigma_2}F
$$

is a magnetic flux period,

$$
\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)
$$

is an instanton-number-type period after choosing the correct trace normalization and bundle conditions, and

$$
\int_{\Sigma_p} J
$$

can be a conserved topological charge if $J$ is a closed $p$-form or the Hodge dual of a conserved current.

The same formula means different things depending on the coefficient system. De Rham periods are real numbers. Quantized charges require integral periods.

## Examples

### Euclidean space

On $\mathbb R^n$, every closed $p$-form for $p>0$ is exact. Therefore

$$
H^0_{\mathrm{dR}}(\mathbb R^n)\simeq\mathbb R,
\qquad
H^p_{\mathrm{dR}}(\mathbb R^n)=0\quad (p>0).
$$

The first statement says that constant functions are the closed zero-forms on a connected space. The second says that $\mathbb R^n$ has no global holes for closed forms to detect.

### The circle

On $S^1$, the angular one-form $d\theta$ is globally meaningful as a one-form even though $\theta$ is not a globally defined real-valued function. It is closed:

$$
d(d\theta)=0.
$$

It is not exact, because

$$
\int_{S^1}d\theta=2\pi\ne0.
$$

If $d\theta=d\alpha$ for a globally defined function $\alpha$, then the integral over the closed circle would vanish. Therefore

$$
H^1_{\mathrm{dR}}(S^1)\simeq\mathbb R,
$$

with generator represented by

$$
\frac{d\theta}{2\pi}.
$$

This is the de Rham form behind winding numbers.

### The two-sphere

For $S^2$, one has

$$
H^0_{\mathrm{dR}}(S^2)\simeq\mathbb R,
\qquad
H^1_{\mathrm{dR}}(S^2)=0,
\qquad
H^2_{\mathrm{dR}}(S^2)\simeq\mathbb R.
$$

A normalized area form $\Omega$ satisfies

$$
\int_{S^2}\Omega=1.
$$

It represents the generator of $H^2_{\mathrm{dR}}(S^2)$. For a map $n:S^2\to S^2$,

$$
\int_{S^2}n^*\Omega=\deg(n).
$$

This is the de Rham explanation of the $O(3)$ sigma-model topological charge.

### The torus

For the $n$-torus

$$
T^n=\mathbb R^n/2\pi\mathbb Z^n,
$$

the one-forms $d\theta^1,\ldots,d\theta^n$ are closed and not exact. The cohomology ring is the exterior algebra generated by their classes:

$$
H^*_{\mathrm{dR}}(T^n)
\simeq \bigwedge
\left\langle \frac{d\theta^1}{2\pi},\ldots,\frac{d\theta^n}{2\pi}\right\rangle.
$$

For $T^2$,

$$
H^0_{\mathrm{dR}}(T^2)\simeq\mathbb R,
\qquad
H^1_{\mathrm{dR}}(T^2)\simeq\mathbb R^2,
\qquad
H^2_{\mathrm{dR}}(T^2)\simeq\mathbb R.
$$

The one-cycles measure periods of $d\theta^1$ and $d\theta^2$; the two-cycle measures the flux of $d\theta^1\wedge d\theta^2$.

## Cohomology ring and wedge product

De Rham cohomology has a product induced by the wedge product. If $\omega$ and $\eta$ are closed, then

$$
d(\omega\wedge\eta)=d\omega\wedge\eta+(-1)^{\deg\omega}\omega\wedge d\eta=0.
$$

If either representative changes by an exact form, the product changes by an exact form. Hence wedge product descends to cohomology:

$$
[\omega]\smile[\eta]\quad\text{is represented by}\quad[\omega\wedge\eta].
$$

Physicists often blur the notation and write simply

$$
[\omega][\eta]=[\omega\wedge\eta].
$$

This ring structure is essential for characteristic classes. Expressions like

$$
\operatorname{tr}(F\wedge F),
\qquad
\operatorname{tr}(R\wedge R),
\qquad
F\wedge F\wedge F
$$

are not just forms; under suitable normalizations they represent cohomology classes built by multiplying lower-degree geometric data.

The signs in the wedge product matter. If $\omega$ is a $p$-form and $\eta$ is a $q$-form,

$$
\omega\wedge\eta=(-1)^{pq}\eta\wedge\omega.
$$

This graded commutativity is the de Rham version of the cup-product sign in ordinary cohomology.

## Pullbacks and naturality

A smooth map

$$
f:M\to N
$$

pulls back forms:

$$
f^*:\Omega^p(N)\to\Omega^p(M).
$$

The pullback commutes with the exterior derivative:

$$
d(f^*\omega)=f^*(d\omega).
$$

Therefore closed forms pull back to closed forms, exact forms pull back to exact forms, and $f$ induces a map on de Rham cohomology:

$$
f^*:H^p_{\mathrm{dR}}(N)\to H^p_{\mathrm{dR}}(M).
$$

This is the mechanism behind topological charges of sigma models. A target-space cohomology class $[\Omega]$ pulls back along a field configuration $\phi:M\to X$ to a spacetime cohomology class

$$
\phi^*[\Omega]\in H^p_{\mathrm{dR}}(M).
$$

Integrating over a cycle $\Sigma_p\subset M$ gives

$$
\int_{\Sigma_p}\phi^*\Omega.
$$

If $[\Omega]$ is appropriately normalized as an integral class and $\Sigma_p$ is an integral cycle, the result is quantized.

## de Rham theorem

The de Rham theorem states that for a smooth manifold $M$,

$$
H^p_{\mathrm{dR}}(M)\simeq H^p(M;\mathbb R).
$$

Under this isomorphism, the cohomology class of a closed form is determined by its periods over cycles. The pairing

$$
H^p_{\mathrm{dR}}(M)\times H_p(M;\mathbb R)\to\mathbb R
$$

is

$$
([\omega],[\Sigma])\mapsto\int_\Sigma\omega.
$$

This is why de Rham cohomology is the natural language for continuum field theory. It lets one compute topological data by integrating local differential forms. But it also warns us what is being forgotten: real cohomology does not see torsion.

For example, a space may have torsion cohomology

$$
H^p(M;\mathbb Z)_{\mathrm{tors}}
e0
$$

while

$$
H^p(M;\mathbb R)
$$

misses it entirely. Since many discrete gauge fields, flat bundles, spin structures, and global anomalies are torsion-sensitive, de Rham cohomology is necessary but not sufficient.

## Integral classes and quantization

A closed form $\omega$ represents a real cohomology class. To say that its periods are integral means that

$$
\int_{\Sigma_p}\omega\in\mathbb Z
$$

for every integral $p$-cycle $\Sigma_p$, after the chosen normalization.

Equivalently, $[\omega]$ lies in the image of the map

$$
H^p(M;\mathbb Z)\to H^p(M;\mathbb R).
$$

This is the step from de Rham cohomology to integral cohomology. In gauge theory, this distinction is the difference between writing a closed real two-form and specifying a genuine $U(1)$ field strength.

For a $U(1)$ connection with curvature $F$, the properly normalized flux satisfies

$$
\frac{1}{2\pi}\int_{\Sigma_2}F\in\mathbb Z
$$

for every closed two-cycle $\Sigma_2$, assuming ordinary Dirac quantization. In cohomological terms,

$$
\left[\frac{F}{2\pi}\right]
$$

is the image in de Rham cohomology of the first Chern class.

The de Rham class records the real-valued curvature periods. The full line bundle can contain torsion data invisible to $F$ as a real form.

## Gauge potentials and field strengths

A common physics notation writes

$$
F=dA.
$$

This is safe locally. Globally, a gauge field is usually a connection, and $A$ is a local connection one-form. On overlaps of patches,

$$
A_j=A_i+g_{ij}^{-1}dg_{ij}
$$

in the Abelian case up to conventional factors, while the curvature $F$ patches globally.

The Bianchi identity

$$
dF=0
$$

says that $F$ defines a de Rham class. If $F=dA$ globally, then that class is zero. If the class is nonzero, there is no single globally defined potential $A$.

This resolves a common puzzle. A local equation of motion or Bianchi identity can say a form is closed, while topology says it is not exact. The two statements are not in conflict:

$$
\text{closed globally} \ne \text{exact globally}.
$$

The entire Aharonov–Bohm effect, monopole flux, theta-angle story, and Chern-class formalism lives in that inequality. Tiny inequality, suspiciously large career.

## Theta terms and topological actions

A theta term often has the form

$$
S_\theta=i\theta\int_M \omega,
$$

in Euclidean signature, where $\omega$ is a closed top-degree form built from fields or background connections. If

$$
\int_M\omega\in\mathbb Z,
$$

then the path-integral weight

$$
e^{-S_\theta}
$$

is invariant under

$$
\theta\sim\theta+2\pi.
$$

For Yang–Mills theory, the familiar schematic form is

$$
\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F\wedge F)\in\mathbb Z
$$

for appropriate compact four-manifolds, bundles, and trace normalization. That integrality is not a statement about a random de Rham form. It is a statement about an integral characteristic class represented in de Rham cohomology by a curvature polynomial.

This is the typical hierarchy:

$$
\text{curvature expression}
\quad\leadsto\quad
\text{closed de Rham form}
\quad\leadsto\quad
\text{integral cohomology class}
\quad\leadsto\quad
\text{periodic coupling}.
$$

Leaving out the integral-cohomology step is the classic way to get the periodicity wrong.

## Conservation laws from closed forms

Suppose $J$ is a closed $p$-form on spacetime:

$$
dJ=0.
$$

Then for two homologous $p$-cycles $\Sigma$ and $\Sigma'$,

$$
\int_\Sigma J=\int_{\Sigma'}J.
$$

Indeed, if $\Sigma'-\Sigma=\partial C$, then

$$
\int_{\Sigma'}J-\int_\Sigma J=\int_{\partial C}J=\int_C dJ=0.
$$

This is the differential-form version of a conserved charge. In $d$ spacetime dimensions, an ordinary conserved current $j^\mu$ can be encoded in a closed $(d-1)$-form

$$
J=\star j,
\qquad dJ=0.
$$

Higher-form symmetries use the same structure but with currents of different form degree. The mathematical statement is just Stokes’ theorem plus closedness.

Topological currents are similar, except $J$ is often built directly from fields and is closed identically, not by equations of motion.

## Boundary conditions and relative de Rham cohomology

If $M$ has boundary, exact forms do not necessarily vanish when integrated over chains with boundary. Stokes’ theorem gives

$$
\int_M d\alpha=\int_{\partial M}\alpha.
$$

So on manifolds with boundary, whether exact shifts are physically irrelevant depends on boundary conditions.

Relative de Rham cohomology is designed for this. Roughly, it studies forms whose boundary behavior is constrained, modulo exact forms compatible with that constraint. In field theory, this is the correct language behind boundary charges, relative theta terms, anomaly inflow with boundary, and Wess–Zumino terms defined by extension.

This page does not develop relative cohomology in full. The operational warning is enough for now:

$$
\text{closed-manifold formulas can acquire boundary terms.}
$$

Whenever a QFT calculation says “up to a total derivative,” ask where the boundary went. Sometimes it went to zero. Sometimes it became the whole point.

## de Rham versus singular cohomology in QFT

De Rham cohomology is excellent for continuum actions because it is represented by differential forms. But QFT often needs several layers of refinement:

| Structure | What it captures | What de Rham sees |
|---|---|---|
| $H^p(M;\mathbb R)$ | real periods | all of it |
| $H^p(M;\mathbb Z)$ | quantized periods and torsion | only the real image |
| differential cohomology | quantized flux plus connection data | curvature and real class |
| equivariant cohomology | symmetry-compatible cohomology | only after forgetting symmetry action |
| generalized cohomology | refined charges and phases | only rough real shadows |
| cobordism | anomaly and invertible-phase data | often only characteristic-number shadows |

This table is not meant to scare you, though it might try. The point is that de Rham cohomology is the first layer. It is usually where the local formula is written. The later layers explain quantization, global choices, and discrete effects.

## Common pitfalls

**Closed does not mean exact.** Locally closed forms are exact, but globally they may have nonzero periods. The difference is precisely what de Rham cohomology measures.

**A local potential is not always a global potential.** Writing $F=dA$ on a patch does not imply that one global $A$ exists. Gauge potentials are often local representatives of a global connection.

**de Rham cohomology uses real coefficients.** It misses torsion. If the physics involves discrete fluxes, spin structures, global anomalies, or finite gauge groups, ordinary de Rham forms are not enough.

**A closed real form is not automatically quantized.** Flux quantization requires an integral class. The factors of $2\pi$ are not decorative; they encode the map from integral cohomology to de Rham cohomology.

**Exact terms can matter on boundaries.** On a closed manifold, the integral of an exact top form vanishes. On a manifold with boundary, it becomes a boundary integral.

**The form representative is not the cohomology class.** Changing a connection or adding an exact form can change the local density while leaving the cohomology class and periods unchanged.

**A topological term need not be metric-independent pointwise.** Some representatives are written using metric-dependent operations, but their integrated cohomology class may be metric-independent after suitable conditions. Check the actual formula.

## Relations to other pages

[Homology and Cohomology](/math-toolkit/topology-cohomology-characteristic-classes/homology-and-cohomology/) gives the cycle/cochain framework that de Rham cohomology realizes with forms.

[Degree of a Map](/math-toolkit/topology-cohomology-characteristic-classes/degree-of-a-map/) uses de Rham classes to compute degree by integrating pulled-back normalized top forms.

[Winding Numbers](/math-toolkit/topology-cohomology-characteristic-classes/winding-numbers/) are periods of pulled-back angular forms.

[Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) supplies the algebra and exterior derivative; [Integration on Manifolds](/math-toolkit/geometry-of-fields/integration-on-manifolds/) supplies Stokes’ theorem and orientations.

[Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/) and [Gauge Fields as Connections](/math-toolkit/geometry-of-fields/gauge-fields-as-connections/) explain how curvature forms become de Rham representatives of characteristic classes after normalization.

[Dirac Operators](/math-toolkit/geometry-of-fields/dirac-operators/) uses characteristic classes and cohomological densities in index-theorem statements.

## Research status

De Rham cohomology itself is a completely standard mathematical tool. Its role as the differential-form model for real cohomology is settled.

The active frontier in QFT is not whether de Rham cohomology is correct; it is how far it must be refined. Modern anomaly theory, generalized symmetries, higher gauge fields, topological phases, and nonperturbative global questions routinely require integral cohomology, torsion, differential cohomology, equivariant refinements, higher bundles, or cobordism.

For practical continuum calculations, however, de Rham cohomology remains the workhorse. It is where most local topological densities first show up before their global quantization is imposed.

## Exercises

### Exercise 1: exact forms have zero periods

Let $\Sigma_p$ be a closed $p$-cycle and let $\omega=d\alpha$ be an exact $p$-form. Show that

$$
\int_{\Sigma_p}\omega=0.
$$

<details>
<summary><strong>Solution</strong></summary>

By Stokes’ theorem,

$$
\int_{\Sigma_p}\omega=\int_{\Sigma_p}d\alpha
=\int_{\partial\Sigma_p}\alpha.
$$

Since $\Sigma_p$ is closed, $\partial\Sigma_p=0$, so

$$
\int_{\Sigma_p}\omega=0.
$$

</details>

### Exercise 2: the angular form on the circle

Show that $d\theta$ represents a nonzero class in $H^1_{\mathrm{dR}}(S^1)$.

<details>
<summary><strong>Solution</strong></summary>

The form $d\theta$ is closed because $d^2=0$. If it were exact, $d\theta=df$ for some globally defined smooth function $f:S^1\to\mathbb R$. Then

$$
\int_{S^1}d\theta=\int_{S^1}df=0
$$

by Stokes’ theorem. But

$$
\int_{S^1}d\theta=2\pi.
$$

Therefore $d\theta$ is closed but not exact, and its class is nonzero. The normalized generator is $d\theta/(2\pi)$.

</details>

### Exercise 3: de Rham class of a sphere area form

Let $\Omega$ be a two-form on $S^2$ with

$$
\int_{S^2}\Omega=1.
$$

Show that $\Omega$ is not exact.

<details>
<summary><strong>Solution</strong></summary>

If $\Omega=d\alpha$ for some globally defined one-form $\alpha$ on $S^2$, then

$$
\int_{S^2}\Omega=\int_{S^2}d\alpha=\int_{\partial S^2}\alpha=0.
$$

But the integral is $1$. Hence $\Omega$ is not exact and represents a nonzero class in $H^2_{\mathrm{dR}}(S^2)$.

</details>

### Exercise 4: cohomology of the two-torus

Let $T^2$ have angular coordinates $\theta^1,\theta^2$. Explain why $d\theta^1$ and $d\theta^2$ represent independent classes in $H^1_{\mathrm{dR}}(T^2)$.

<details>
<summary><strong>Solution</strong></summary>

Let $a$ be the cycle with $\theta^1$ running from $0$ to $2\pi$ and $\theta^2$ fixed, and let $b$ be the cycle with $\theta^2$ running and $\theta^1$ fixed. Then

$$
\int_a d\theta^1=2\pi,
\qquad
\int_a d\theta^2=0,
$$

and

$$
\int_b d\theta^1=0,
\qquad
\int_b d\theta^2=2\pi.
$$

These distinct periods show that the two classes are linearly independent. Normalized generators are $d\theta^1/(2\pi)$ and $d\theta^2/(2\pi)$.

</details>

### Exercise 5: degree from de Rham pairing

Let $f:S^2\to S^2$ and let $\Omega$ be the normalized area form on the target sphere. Show that

$$
\int_{S^2}f^*\Omega
$$

is unchanged under a smooth homotopy of $f$.

<details>
<summary><strong>Solution</strong></summary>

Let $f_t:S^2\to S^2$ be a smooth homotopy. Since $\Omega$ is closed, the cohomology class $[f_t^*\Omega]=f_t^*[\Omega]$ is independent of $t$ because homotopic maps induce the same map on cohomology. Therefore the pairing with the fixed fundamental class $[S^2]$ is constant:

$$
\int_{S^2}f_t^*\Omega
=\langle f_t^*[\Omega],[S^2]\rangle.
$$

This integral is the degree of $f_t$, so it is homotopy invariant.

</details>

## References

- M. Nakahara, *Geometry, Topology and Physics*. Physics-oriented treatment of forms, de Rham cohomology, bundles, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*. Detailed geometric introduction to differential forms, integration, de Rham cohomology, and gauge-field applications.
- R. Bott and L. Tu, *Differential Forms in Algebraic Topology*. Classic reference connecting differential forms to algebraic topology.
- A. Hatcher, *Algebraic Topology*. Standard reference for singular cohomology, de Rham comparison, and related topology.
- T. Eguchi, P. Gilkey, and A. Hanson, “Gravitation, gauge theories and differential geometry.” Classic physics review connecting de Rham forms, characteristic classes, and index theory.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*. Standard mathematical reference for connections, curvature, and characteristic classes.
- D. Freed and G. Moore, works on setting the quantum integrand of M-theory and generalized cohomological refinements. Useful for seeing why de Rham cohomology is only the first layer in quantum field theory.

## Version history

- **2026-06-25:** Initial polished draft. Added definition, Stokes-theorem motivation, examples, periods, integral refinements, QFT uses, pitfalls, and exercises.
