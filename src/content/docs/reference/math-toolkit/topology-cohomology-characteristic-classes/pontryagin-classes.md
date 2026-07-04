---
title: "Pontryagin Classes"
description: "Defines Pontryagin classes of real vector bundles, derives their Chern–Weil representatives, and explains their role in signatures, gravitational theta terms, anomalies, and index formulas."
sidebar:
  label: "Pontryagin Classes"
  order: 10
level: Advanced
status: "Polished draft"
source: "Standard references on characteristic classes and Chern–Weil theory, including Milnor–Stasheff, Bott–Tu, Nakahara, Frankel, Eguchi–Gilkey–Hanson, and QFT treatments of gravitational anomalies, instantons, and index theory."
topics:
  - Pontryagin classes
  - real vector bundles
  - Chern-Weil theory
  - Pontryagin forms
  - tangent bundle topology
  - signature theorem
  - A-hat genus
  - gravitational theta terms
  - anomaly polynomials
  - index theorem
canonicalTopics:
  - pontryagin-class
  - real-vector-bundle
  - chern-weil-theory
  - pontryagin-form
  - tangent-bundle-topology
  - signature-theorem
  - a-hat-genus
  - gravitational-theta-term
  - anomaly-polynomial
  - index-theorem
researchStatus:
  established:
    - "Pontryagin classes are standard integral characteristic classes of real vector bundles; their real cohomology representatives are Chern–Weil polynomials in curvature."
  active:
    - "Modern QFT often uses refinements of Pontryagin data in differential cohomology, equivariant cohomology, anomaly inflow, Dai–Freed theory, and cobordism-sensitive global anomaly formulas."
---

## Summary

Pontryagin classes are characteristic classes of real vector bundles. For a real rank-$r$ bundle

$$
E\to M,
$$

they are cohomology classes

$$
p_k(E)\in H^{4k}(M;\mathbb Z),\qquad k=0,1,2,\ldots,
$$

assembled into the total Pontryagin class

$$
p(E)=1+p_1(E)+p_2(E)+\cdots .
$$

The important degrees are multiples of four. That simple fact is why Pontryagin classes appear in four-dimensional instanton physics, gravitational theta terms, anomaly polynomials, and index theorems. If Chern classes are the characteristic classes native to complex bundles, Pontryagin classes are the characteristic classes native to real bundles after one remembers that real vector spaces can be complexified.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram showing a real vector bundle, a connection, curvature, Chern-Weil forms, Pontryagin classes, characteristic numbers, and QFT uses including gravitational theta terms, signature, A-hat genus, and anomaly polynomials.](/figures/math-toolkit/pontryagin-class-flow.svg)

<figcaption>

Pontryagin classes begin with a real bundle but become calculable after choosing a connection. The curvature representative changes when the connection changes, while the cohomology class and its characteristic numbers do not.

</figcaption>
</figure>

For QFT, the main representatives are curvature polynomials such as

$$
p_1(E)_\mathbb R=-\frac{1}{8\pi^2}\operatorname{tr}(\Omega\wedge\Omega),
$$

where $\Omega$ is the curvature of an orthogonal connection and $\operatorname{tr}$ is the trace in the defining real representation. The minus sign is a convention tied to the standard normalization

$$
p_k(E)=(-1)^k c_{2k}(E_\mathbb C),
$$

where $E_\mathbb C=E\otimes_\mathbb R\mathbb C$ is the complexification.

The slogan is

$$
\text{Pontryagin classes are the even Chern classes of a real bundle after complexification, with signs fixed so the roots square positively.}
$$

They are simultaneously topological invariants and local curvature densities. This double life is exactly what makes them useful in index theory and anomalies.

## Prerequisites

Read [Characteristic Classes](/math-toolkit/topology-cohomology-characteristic-classes/characteristic-classes/) for the general idea of assigning cohomology classes to bundles. Read [Chern Classes](/math-toolkit/topology-cohomology-characteristic-classes/chern-classes/) for Chern–Weil representatives of complex bundles and [Stiefel–Whitney Classes](/math-toolkit/topology-cohomology-characteristic-classes/stiefel-whitney-classes/) for mod-$2$ obstruction classes.

For the geometric input, read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/), [Connections and Curvature](/math-toolkit/geometry-of-fields/connections-and-curvature/), [Riemannian and Lorentzian Geometry](/math-toolkit/geometry-of-fields/riemannian-and-lorentzian-geometry/), and [Spin Structures](/math-toolkit/geometry-of-fields/spin-structures/). The next page, [Index Theorems](/math-toolkit/topology-cohomology-characteristic-classes/index-theorems/), explains why Pontryagin classes enter the index of Dirac-type operators.

## Core idea

A real vector bundle $E\to M$ has transition functions valued in $GL(r,\mathbb R)$, or in $O(r)$ after choosing a fiber metric. Its complexification

$$
E_\mathbb C=E\otimes_\mathbb R\mathbb C
$$

is a complex vector bundle. We can therefore take Chern classes of $E_\mathbb C$. For a real bundle, the odd Chern classes of the complexification are two-torsion, so they vanish after passing to real cohomology. The even Chern classes survive, and the Pontryagin classes are defined by

$$
p_k(E)=(-1)^k c_{2k}(E_\mathbb C).
$$

Equivalently, if the formal Chern roots of $E_\mathbb C$ come in pairs

$$
\pm x_1,\ldots,\pm x_m,
$$

then

$$
c(E_\mathbb C)=\prod_{j=1}^m (1+x_j)(1-x_j)
=\prod_{j=1}^m(1-x_j^2),
$$

while

$$
p(E)=\prod_{j=1}^m(1+x_j^2).
$$

The quantities $x_j^2$ are the Pontryagin roots. This is a formal device, but an extremely useful one. It lets you manipulate Pontryagin classes as if they were symmetric polynomials.

The classes are natural under pullback:

$$
p_k(f^*E)=f^*p_k(E)
$$

for every smooth map $f:N\to M$. They also obey the Whitney product formula:

$$
p(E\oplus F)=p(E)p(F).
$$

These two properties are the reason Pontryagin classes behave well under restricting a gauge or tangent bundle to a submanifold, decomposing a normal bundle, or comparing two phases across an interface.

## Chern–Weil representative

Let $E\to M$ be a real rank-$r$ vector bundle with a fiber metric and an orthogonal connection. In a local orthonormal frame, the connection is an $\mathfrak{so}(r)$-valued one-form

$$
\omega=(\omega^a{}_b),
$$

and its curvature is

$$
\Omega=d\omega+\omega\wedge\omega.
$$

Under a change of local frame, $\Omega$ transforms by conjugation. Therefore invariant polynomials in $\Omega$ define global differential forms.

The first Pontryagin form is

$$
p_1(\Omega)=-\frac{1}{8\pi^2}\operatorname{tr}(\Omega\wedge\Omega).
$$

This form is closed:

$$
dp_1(\Omega)=0.
$$

If we change the connection, $p_1(\Omega)$ changes by an exact form. Thus its de Rham cohomology class is independent of the connection:

$$
[p_1(\Omega)] = p_1(E)_\mathbb R\in H^4(M;\mathbb R).
$$

The same story holds for higher Pontryagin forms. One convenient way to package them is through the determinant formula

$$
p(\Omega)=\det\!\left(1-\frac{\Omega}{2\pi}\right),
$$

understood through the formal skew-eigenvalue pairs of $\Omega$. More invariantly, after complexifying the curvature, use the Chern–Weil expression for $c(E_\mathbb C)$ and define $p_k=(-1)^k c_{2k}(E_\mathbb C)$.

For many QFT formulas, only the first two components are needed. In the defining real representation,

$$
p_1(\Omega)=-\frac{1}{8\pi^2}\operatorname{tr}\Omega^2,
$$

and

$$
p_2(\Omega)=\frac{1}{128\pi^4}\left((\operatorname{tr}\Omega^2)^2-2\operatorname{tr}\Omega^4\right),
$$

where wedge products are implicit:

$$
\operatorname{tr}\Omega^2=\operatorname{tr}(\Omega\wedge\Omega),
\qquad
\operatorname{tr}\Omega^4=\operatorname{tr}(\Omega\wedge\Omega\wedge\Omega\wedge\Omega).
$$

:::caution[Trace normalization]
Physics papers often write curvature terms as $\operatorname{Tr}R\wedge R$, $\operatorname{tr}R\wedge R$, or $\operatorname{tr}_{\mathbf v}R\wedge R$ with different normalizations. This page uses $\operatorname{tr}$ for the defining real representation of $SO(r)$. Converting to another representation changes numerical coefficients.
:::

## The tangent bundle and gravitational curvature

For a Riemannian or Lorentzian manifold $M$, the most important real bundle is the tangent bundle

$$
TM\to M.
$$

After choosing a metric, the Levi-Civita connection gives a curvature two-form

$$
R^a{}_b.
$$

The Pontryagin classes

$$
p_k(TM)
$$

are independent of the metric, even though their curvature representatives are built from the metric connection. In local orthonormal frames,

$$
p_1(TM)_\mathbb R=-\frac{1}{8\pi^2}\operatorname{tr}(R\wedge R).
$$

In QFT this expression often appears in gravitational theta terms and anomaly polynomials. For a compact oriented four-manifold $M_4$, the integral

$$
\int_{M_4} p_1(TM)
$$

is a topological number. The Hirzebruch signature theorem says

$$
\sigma(M_4)=\frac{1}{3}\int_{M_4}p_1(TM),
$$

where $\sigma(M_4)$ is the signature of the intersection form on $H^2(M_4;\mathbb R)$.

So the gravitational density $\operatorname{tr}(R\wedge R)$ is not merely a local curvature invariant. Its integral is tied to the topology of the four-manifold:

$$
\int_{M_4}\operatorname{tr}(R\wedge R)=-8\pi^2\int_{M_4}p_1(TM)
=-24\pi^2\sigma(M_4).
$$

The sign follows the convention for $p_1$ above. If your curvature convention differs by $R\mapsto -R$, then $p_1$ is unchanged because it is quadratic. If your trace convention differs, the coefficient changes.

## Pontryagin classes versus Chern classes

A complex vector bundle $E\to M$ can be regarded as a real bundle $E_\mathbb R\to M$ by forgetting multiplication by $i$. The Pontryagin classes of $E_\mathbb R$ are determined by the Chern classes of $E$, but one must keep the standard signs straight.

The complexification of the underlying real bundle is

$$
E_\mathbb R\otimes_\mathbb R\mathbb C\simeq E\oplus \overline E.
$$

Using Chern roots $y_1,\ldots,y_r$ for $E$,

$$
c(E\oplus\overline E)=c(E)c(\overline E)
=\prod_i(1+y_i)(1-y_i)
=\prod_i(1-y_i^2).
$$

Since $p_k(E_\mathbb R)=(-1)^k c_{2k}(E\oplus\overline E)$, the total Pontryagin class is

$$
p(E_\mathbb R)=\prod_i(1+y_i^2).
$$

This gives

$$
p_1(E_\mathbb R)=c_1(E)^2-2c_2(E),
$$

and

$$
p_2(E_\mathbb R)=c_2(E)^2-2c_1(E)c_3(E)+2c_4(E).
$$

For a complex line bundle $L$,

$$
p_1(L_\mathbb R)=c_1(L)^2.
$$

This formula is often the fastest way to move between electromagnetic flux data and real-bundle topology. A $U(1)$ line bundle with first Chern class $c_1(L)$ has an underlying real two-plane bundle whose first Pontryagin class is the square of the flux class.

## Relation to Euler and Stiefel–Whitney classes

For an oriented real rank-$2$ bundle $E$, the Euler class is

$$
e(E)\in H^2(M;\mathbb Z).
$$

The bundle is equivalent to a complex line bundle after choosing a compatible rotation by $90^\circ$ in each oriented fiber. Then

$$
p_1(E)=e(E)^2.
$$

For an oriented real rank-$4$ bundle, the Euler class and first Pontryagin class are independent kinds of degree-four information. Roughly speaking, $e(E)$ measures oriented zeroes of a section, while $p_1(E)$ measures the self-dual versus anti-self-dual twisting encoded by the curvature.

Pontryagin classes also reduce mod $2$ to Stiefel–Whitney data:

$$
p_k(E)\bmod 2 = w_{2k}(E)^2.
$$

In particular,

$$
p_1(E)\bmod 2=w_2(E)^2.
$$

This relation is one reason $p_1$ and $w_2$ often appear together in global anomaly formulas and spin-refinement conditions. A real differential form representative of $p_1$ sees only the real cohomology part. The integral class may still carry torsion information that de Rham forms cannot detect.

## Characteristic numbers

If $M$ is a closed oriented $d$-manifold and $P(p_1,p_2,\ldots)$ is a degree-$d$ polynomial in Pontryagin classes, then

$$
\int_M P(p_1(TM),p_2(TM),\ldots)
$$

is a Pontryagin number of $M$.

Examples in low dimensions:

- in dimension $4$,

$$
\int_{M_4}p_1(TM);
$$

- in dimension $8$,

$$
\int_{M_8}p_1(TM)^2,
\qquad
\int_{M_8}p_2(TM);
$$

- in dimension $12$,

$$
\int_{M_{12}}p_1^3,
\qquad
\int_{M_{12}}p_1p_2,
\qquad
\int_{M_{12}}p_3.
$$

Pontryagin numbers are oriented cobordism invariants over rational coefficients. Physically, they are the numbers that can appear when topological terms or anomaly inflow actions are evaluated on closed manifolds.

A useful warning: characteristic numbers require compactness or a boundary prescription. On a noncompact spacetime, the integral of a Pontryagin density can depend on falloff conditions and boundary contributions.

## The L-genus and signature

Pontryagin classes assemble into genera. The Hirzebruch $L$-genus is the multiplicative sequence associated with

$$
\frac{x}{\tanh x}.
$$

In terms of Pontryagin classes,

$$
L(TM)=1+\frac{p_1}{3}+\frac{7p_2-p_1^2}{45}
+\frac{62p_3-13p_1p_2+2p_1^3}{945}+\cdots .
$$

For a closed oriented $4k$-manifold,

$$
\sigma(M)=\int_M L(TM).
$$

In dimension four this reduces to

$$
\sigma(M_4)=\frac{1}{3}\int_{M_4}p_1(TM).
$$

In dimension eight,

$$
\sigma(M_8)=\frac{1}{45}\int_{M_8}\left(7p_2(TM)-p_1(TM)^2\right).
$$

The signature theorem is a prototype of an index theorem: an analytic invariant of a differential operator equals a topological expression built from characteristic classes.

## The A-hat genus and spin geometry

The $\widehat A$-genus is the multiplicative sequence associated with

$$
\frac{x/2}{\sinh(x/2)}.
$$

It begins

$$
\widehat A(TM)=1-\frac{p_1}{24}
+\frac{7p_1^2-4p_2}{5760}
-\frac{31p_1^3-44p_1p_2+16p_3}{967680}+\cdots .
$$

For a closed spin manifold, the index of the chiral Dirac operator is

$$
\operatorname{index}(D^+)=\int_M\widehat A(TM).
$$

More generally, if the Dirac operator is twisted by a complex vector bundle $E$, then

$$
\operatorname{index}(D_E^+)=\int_M\widehat A(TM)\operatorname{ch}(E).
$$

This is the most common way Pontryagin classes enter fermionic QFT. The tangent-bundle contribution to the index is not built from Chern classes of the gauge bundle; it is built from Pontryagin classes of spacetime.

In four dimensions, the untwisted spin Dirac index is

$$
\operatorname{index}(D^+)=-\frac{1}{24}\int_{M_4}p_1(TM)
=-\frac{\sigma(M_4)}{8}.
$$

For example, a K3 surface has $\sigma=-16$, hence

$$
\operatorname{index}(D^+)=2.
$$

That integer is a zero-mode count with chirality signs. It is not the total number of zero modes.

## Gauge bundles and adjoint bundles

Pontryagin classes also appear for real bundles associated to gauge fields. Let $P\to M$ be a principal $G$-bundle and let $\rho:G\to SO(V)$ be a real orthogonal representation. The associated bundle

$$
E=P\times_\rho V
$$

has Pontryagin classes computed from the curvature in the representation $\rho$.

For nonabelian gauge theory, physicists often start instead with a complex representation and its Chern character. The two descriptions are related, but the trace normalization matters. In four-dimensional gauge theory, a typical topological density is

$$
\operatorname{tr}_R(F\wedge F),
$$

and the corresponding instanton number is normalized so that

$$
k=\int_{M_4}\frac{1}{8\pi^2}\operatorname{tr}_{\mathrm{fund}}(F\wedge F)
$$

is an integer for an $SU(N)$ bundle when $\operatorname{tr}_{\mathrm{fund}}$ uses the standard fundamental normalization. Pontryagin-class formulas for real associated bundles may differ by signs and representation indices.

This is not a contradiction. Characteristic classes are canonical; component formulas inherit the normalization choices of the trace and Lie algebra generators.

## Gravitational theta terms

In four-dimensional gauge theory, a topological term often has the form

$$
S_\theta=\frac{i\theta}{8\pi^2}\int\operatorname{tr}(F\wedge F)
$$

in Euclidean signature. Gravity has an analogous Pontryagin density:

$$
\int_{M_4}\operatorname{tr}(R\wedge R).
$$

Using the convention above,

$$
\int_{M_4}\operatorname{tr}(R\wedge R)=-8\pi^2\int_{M_4}p_1(TM).
$$

A gravitational theta term can therefore be written in terms of $p_1(TM)$. On a closed oriented four-manifold, it is controlled by the signature:

$$
\int_{M_4}p_1(TM)=3\sigma(M_4).
$$

On manifolds with boundary, this simple statement must be supplemented by boundary Chern–Simons terms and, in index-theoretic contexts, eta invariants. This is one of the places where the phrase “topological term” quietly smuggles in boundary conditions. Tiny phrase, big bill.

## Pontryagin classes in anomaly polynomials

Anomaly polynomials package perturbative anomalies of chiral fields in even spacetime dimension $d=2n$ into a closed $(d+2)$-form built from gauge and gravitational characteristic classes. For a chiral fermion coupled to a gauge bundle $E$, the standard index-theoretic expression has the form

$$
I_{2n+2}=\left[\widehat A(TM)\operatorname{ch}(E)\right]_{2n+2}.
$$

The Chern character $\operatorname{ch}(E)$ supplies gauge curvature terms. The $\widehat A$ genus supplies gravitational curvature terms through Pontryagin classes:

$$
\widehat A(TM)=1-\frac{p_1(TM)}{24}+\cdots .
$$

For example, in two-dimensional spacetime, the four-form part contains a term proportional to

$$
-\frac{\operatorname{rank}(E)}{24}p_1(TM).
$$

In four-dimensional spacetime, the six-form part mixes gauge Chern characters with the gravitational class $p_1(TM)$. This is the geometric origin of mixed gauge-gravitational anomalies.

The descent procedure converts the closed anomaly polynomial into local anomalous variations. The polynomial itself is the clean invariant object; the descended local formulas depend on choices of connection and counterterm scheme.

## Worked example: real two-plane bundle

Let $E\to M$ be an oriented real two-plane bundle. The structure group reduces to $SO(2)\simeq U(1)$. Choosing a metric and compatible connection, the curvature is locally

$$
\Omega=\begin{pmatrix}0&-F\\ F&0\end{pmatrix},
$$

where $F$ is an ordinary two-form. Then

$$
\operatorname{tr}(\Omega\wedge\Omega)=-2F\wedge F.
$$

Therefore

$$
p_1(E)=-\frac{1}{8\pi^2}\operatorname{tr}(\Omega\wedge\Omega)
=\frac{1}{4\pi^2}F\wedge F.
$$

The Euler class has representative

$$
e(E)=\frac{F}{2\pi}.
$$

Hence

$$
p_1(E)=e(E)^2.
$$

This is the simplest concrete instance of a Pontryagin class. The real two-plane secretly behaves like a complex line.

## Worked example: a complex bundle regarded as real

Let $E\to M$ be a complex rank-$r$ bundle with Chern roots $y_i$. Its underlying real bundle $E_\mathbb R$ has

$$
p(E_\mathbb R)=\prod_i(1+y_i^2).
$$

Expanding gives

$$
p_1(E_\mathbb R)=\sum_i y_i^2.
$$

But

$$
c_1(E)=\sum_i y_i,
\qquad
c_2(E)=\sum_{i<j}y_iy_j.
$$

Therefore

$$
c_1(E)^2-2c_2(E)
=\left(\sum_i y_i\right)^2-2\sum_{i<j}y_iy_j
=\sum_i y_i^2,
$$

so

$$
p_1(E_\mathbb R)=c_1(E)^2-2c_2(E).
$$

For an $SU(r)$ bundle, $c_1(E)=0$, so

$$
p_1(E_\mathbb R)=-2c_2(E).
$$

This sign is a common place to trip. The minus sign is not a deep mystery; it comes from the convention $p_1=-c_2(E_\mathbb C)$ and from the paired roots of a real bundle.

## Common pitfalls

Do not confuse a Pontryagin form with a Pontryagin class. A connection gives a differential form such as

$$
-\frac{1}{8\pi^2}\operatorname{tr}(\Omega\wedge\Omega),
$$

but the topological object is its cohomology class. Change the connection and the form changes by an exact term.

Do not forget trace normalization. The statement

$$
p_1=-\frac{1}{8\pi^2}\operatorname{tr}\Omega^2
$$

uses the trace in the defining real representation. Gauge theory papers may use a different representation or absorb factors into the definition of $F$.

Do not assume de Rham representatives see everything. Pontryagin classes are integral classes. Differential forms see their images in real cohomology and miss torsion.

Do not confuse $p_1$ with the Euler class. In rank two, $p_1=e^2$. In rank four and above, $p_1$ and $e$ carry different information.

Do not treat boundary terms as optional decorations. On manifolds with boundary, integrals of Pontryagin forms are not purely topological without boundary data.

## Exercises

### Exercise 1: Pontryagin class of an oriented two-plane bundle

Let $E\to M$ be an oriented real two-plane bundle with Euler class $e(E)$. Show that

$$
p_1(E)=e(E)^2.
$$

<details><summary><strong>Solution</strong></summary>

An oriented real two-plane bundle has structure group $SO(2)\simeq U(1)$ and can be regarded as a complex line bundle $L$. Under this identification,

$$
c_1(L)=e(E).
$$

The underlying real bundle of a complex line bundle has

$$
p_1(L_\mathbb R)=c_1(L)^2.
$$

Therefore

$$
p_1(E)=e(E)^2.
$$

Equivalently, using curvature,

$$
\Omega=\begin{pmatrix}0&-F\\ F&0\end{pmatrix}
$$

gives

$$
p_1(E)=-\frac{1}{8\pi^2}\operatorname{tr}(\Omega\wedge\Omega)
=\frac{F\wedge F}{4\pi^2}
=\left(\frac{F}{2\pi}\right)^2=e(E)^2.
$$

</details>

### Exercise 2: Underlying real bundle of a complex bundle

Let $E$ be a complex rank-$r$ bundle. Use Chern roots to show

$$
p_1(E_\mathbb R)=c_1(E)^2-2c_2(E).
$$

<details><summary><strong>Solution</strong></summary>

Let $y_1,\ldots,y_r$ be the Chern roots of $E$. Then

$$
c_1(E)=\sum_i y_i,
\qquad
c_2(E)=\sum_{i<j}y_iy_j.
$$

The Pontryagin roots of the underlying real bundle are $y_i^2$, so

$$
p_1(E_\mathbb R)=\sum_i y_i^2.
$$

But

$$
\left(\sum_i y_i\right)^2
=\sum_i y_i^2+2\sum_{i<j}y_iy_j.
$$

Therefore

$$
\sum_i y_i^2=c_1(E)^2-2c_2(E),
$$

which proves the formula.

</details>

### Exercise 3: Signature and the first Pontryagin number

Let $M_4$ be a closed oriented four-manifold with signature $\sigma(M_4)$. Use the Hirzebruch signature theorem to compute $\int_{M_4}p_1(TM)$.

<details><summary><strong>Solution</strong></summary>

In four dimensions,

$$
L(TM)=1+\frac{p_1(TM)}{3},
$$

so the degree-four part of the signature theorem gives

$$
\sigma(M_4)=\frac{1}{3}\int_{M_4}p_1(TM).
$$

Hence

$$
\int_{M_4}p_1(TM)=3\sigma(M_4).
$$

For example, if $M_4=\mathbb{CP}^2$, then $\sigma=1$ and

$$
\int_{\mathbb{CP}^2}p_1(T\mathbb{CP}^2)=3.
$$

</details>

### Exercise 4: Dirac index in four dimensions

Let $M_4$ be a closed spin four-manifold. Show that the untwisted chiral Dirac index is

$$
\operatorname{index}(D^+)=-\frac{\sigma(M_4)}{8}.
$$

<details><summary><strong>Solution</strong></summary>

The Atiyah–Singer formula for the untwisted spin Dirac operator is

$$
\operatorname{index}(D^+)=\int_{M_4}\widehat A(TM).
$$

In degree four,

$$
\widehat A(TM)=1-\frac{p_1(TM)}{24}+\cdots,
$$

so

$$
\operatorname{index}(D^+)=-\frac{1}{24}\int_{M_4}p_1(TM).
$$

Using

$$
\int_{M_4}p_1(TM)=3\sigma(M_4),
$$

we get

$$
\operatorname{index}(D^+)=-\frac{\sigma(M_4)}{8}.
$$

For a spin four-manifold, Rokhlin's theorem implies $\sigma(M_4)$ is divisible by $16$, so the result is indeed an integer.

</details>

## References

- Milnor and Stasheff, *Characteristic Classes*.
- Bott and Tu, *Differential Forms in Algebraic Topology*.
- Nakahara, *Geometry, Topology and Physics*.
- Frankel, *The Geometry of Physics*.
- Eguchi, Gilkey, and Hanson, “Gravitation, gauge theories and differential geometry.”
- Alvarez-Gaumé and Witten, “Gravitational anomalies.”
- Bertlmann, *Anomalies in Quantum Field Theory*.
- Freed, *Classical Chern–Simons Theory*, and related notes on determinant lines and anomalies.

## Version history

- 2026-06-25: Initial polished draft. Added definitions, Chern–Weil representatives, tangent-bundle applications, relations to Chern/Euler/Stiefel–Whitney classes, genera, anomaly-polynomial use, examples, and exercises.
