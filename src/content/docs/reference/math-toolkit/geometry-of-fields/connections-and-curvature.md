---
title: "Connections and Curvature"
description: "Defines connections as covariant differentiation and horizontal transport on bundles, derives curvature, gauge transformation laws, Bianchi identities, holonomy, and the physics convention for gauge fields."
sidebar:
  label: "Connections and Curvature"
  order: 6
level: Graduate
status: "Polished draft"
source: "Standard differential geometry and gauge theory references, including Nakahara, Frankel, Kobayashi–Nomizu, Eguchi–Gilkey–Hanson, and QFT treatments of Yang–Mills fields, Wilson lines, and instantons."
topics:
  - connections
  - curvature
  - covariant derivative
  - parallel transport
  - holonomy
  - gauge fields
  - principal connections
  - Bianchi identity
  - Wilson lines
canonicalTopics:
  - connection-on-a-bundle
  - curvature-form
  - covariant-derivative
  - principal-connection
  - parallel-transport
  - holonomy
  - bianchi-identity
  - gauge-field-strength
researchStatus:
  established:
    - "Connections, curvature, parallel transport, holonomy, gauge transformation laws, and Bianchi identities are standard geometric foundations of gauge theory and field theory on bundles."
  active:
    - "Modern QFT extends this language to higher connections, differential cohomology, generalized global symmetry backgrounds, nontrivial defects, and gauge fields on singular or stratified spaces."
---

## Summary

A connection is a rule for comparing fibers at nearby points. Equivalently, it is a covariant derivative, a rule for parallel transport, or a choice of horizontal directions in the total space of a bundle. Curvature measures the failure of parallel transport to be path-independent.

For a vector bundle, a connection is a map

$$
\nabla:\Gamma(E)\to \Gamma(T^*M\otimes E)
$$

satisfying the Leibniz rule

$$
\nabla(fs)=df\otimes s+f\nabla s.
$$

In a local frame, it looks like

$$
\nabla=d+\mathcal A,
$$

where $\mathcal A$ is a matrix-valued or Lie-algebra-valued one-form. The curvature is

$$
\mathcal F=\nabla^2=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Diagram showing connection, horizontal lift, parallel transport, holonomy, curvature, the square of the covariant derivative, Bianchi identity, gauge transformation of the connection, tensorial curvature transformation, and physics convention.](/figures/math-toolkit/connection-curvature-holonomy.svg)

<figcaption>

A connection gives parallel transport and covariant differentiation. Its curvature measures the infinitesimal holonomy around a small loop and the failure of covariant derivatives to commute. Unlike the local connection form $\mathcal A$, the curvature transforms tensorially.

</figcaption>
</figure>

This page uses the mathematical connection form $\mathcal A$ for the clean bundle formulas. The site’s physics convention for compact gauge groups uses Hermitian generators $T^a$ and

$$
D=d+igA^aT^a,
\qquad
\mathcal A=igA^aT^a.
$$

With this translation,

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=igF^aT^a.
$$

## Prerequisites

Read [Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) first. You should also know [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) and [Lie Groups and Lie Algebras](/math-toolkit/groups-representations/lie-groups-and-lie-algebras/). The page [Mathematical Conventions](/math-toolkit/conventions/) fixes the physics normalization for compact Lie algebra generators and gauge field strengths.

The goal here is not yet to quantize gauge theory. The goal is to understand what a gauge field *is* before it becomes an integration variable in a path integral.

## Core idea

A section $s$ of a bundle assigns an element $s(x)\in E_x$ to each point $x\in M$. If $x$ and $x+dx$ are nearby, then $s(x)$ and $s(x+dx)$ live in different fibers. There is no canonical way to subtract them unless the bundle has extra structure.

A connection supplies that extra structure. It says which elements of nearby fibers should count as “the same to first order.” Once this comparison rule is chosen, one can define a covariant derivative.

For an ordinary function $f:M\to\mathbb R$, the derivative $df$ is intrinsic because all values live in the same vector space $\mathbb R$. For a bundle section $s\in\Gamma(E)$, the ordinary expression $ds$ is meaningful only after choosing a local trivialization. The connection-corrected object

$$
\nabla s
$$

is globally meaningful.

The physics slogan is:

$$
\text{a gauge field is a connection; its field strength is curvature.}
$$

That sentence is often the shortest path from local Yang–Mills formulas to global gauge theory.

## Three faces of a connection

A connection can be introduced in three equivalent ways, each useful in a different calculation.

| Face | What it does | Typical notation |
|---|---|---|
| covariant derivative | differentiates sections | $\nabla=d+\mathcal A$ |
| horizontal distribution | splits tangent directions in $P$ into vertical and horizontal parts | $TP=H P\oplus V P$ |
| parallel transport | moves fiber elements along paths | $\mathcal P\exp(-\int_\gamma\mathcal A)$ |

The covariant-derivative view is best for local calculations. The horizontal-distribution view is the cleanest principal-bundle definition. The parallel-transport view is closest to Wilson lines and holonomy.

A healthy gauge-theory brain can move among all three. That is annoying for a week and then unbelievably useful.

## Connections on vector bundles

Let $E\to M$ be a vector bundle. A connection is a linear map

$$
\nabla:\Gamma(E)\to\Gamma(T^*M\otimes E)
$$

satisfying

$$
\nabla(fs)=df\otimes s+f\nabla s
$$

for any smooth function $f$ and section $s$.

In a local frame $e_a$, a section is written

$$
s=s^a e_a.
$$

A connection is specified locally by a matrix-valued one-form

$$
\mathcal A^a{}_b.
$$

The covariant derivative is

$$
\nabla s
=
(ds^a+\mathcal A^a{}_b s^b)e_a.
$$

In column notation,

$$
\nabla s=d s+\mathcal A s.
$$

If $X$ is a vector field, the covariant derivative along $X$ is

$$
\nabla_Xs=\iota_X\nabla s.
$$

In components,

$$
\nabla_\mu s=\partial_\mu s+\mathcal A_\mu s.
$$

The one-form $\mathcal A$ is not itself a tensor. It depends on the local frame. The covariant derivative $\nabla$ is the geometric object.

## Change of frame

Suppose two local frames on an overlap are related so that the section components obey

$$
s_i=g_{ij}s_j.
$$

Write

$$
\nabla_i=d+\mathcal A_i,
\qquad
\nabla_j=d+\mathcal A_j.
$$

Compatibility of the covariant derivative means

$$
\nabla_i s_i=g_{ij}\nabla_j s_j.
$$

Substituting $s_i=g_{ij}s_j$ gives

$$
d(g_{ij}s_j)+\mathcal A_i g_{ij}s_j
= g_{ij}(ds_j+\mathcal A_j s_j).
$$

Since this must hold for all $s_j$,

$$
\mathcal A_i
=
g_{ij}\mathcal A_j g_{ij}^{-1}-dg_{ij}\,g_{ij}^{-1}.
$$

Equivalently,

$$
\mathcal A_j
=
g_{ij}^{-1}\mathcal A_i g_{ij}+g_{ij}^{-1}dg_{ij}.
$$

This is the geometric origin of the gauge transformation law for a gauge potential. The inhomogeneous term is not a bug. It is exactly what lets a derivative of locally transformed components become a globally defined covariant derivative.

## Principal connections

Let $P\to M$ be a principal $G$-bundle. A principal connection can be defined as a Lie-algebra-valued one-form

$$
\omega\in\Omega^1(P,\mathfrak g)
$$

on the total space $P$ satisfying two conditions.

First, it reproduces the generator on vertical vectors. If $\xi\in\mathfrak g$ and $\xi_P$ is the corresponding fundamental vertical vector field, then

$$
\omega(\xi_P)=\xi.
$$

Second, it is equivariant under the right action of $G$:

$$
R_g^*\omega=\operatorname{Ad}_{g^{-1}}\omega.
$$

The kernel of $\omega$ defines the horizontal subspace:

$$
H_pP=\ker\omega_p\subset T_pP.
$$

The vertical directions move along the gauge orbit inside one fiber. The horizontal directions say how to lift motion in the base $M$ up into the principal bundle.

Given a local section $\sigma_i:U_i\to P$, the local gauge potential is the pullback

$$
\mathcal A_i=\sigma_i^*\omega\in\Omega^1(U_i,\mathfrak g).
$$

If local sections are related by

$$
\sigma_j=\sigma_i g_{ij},
$$

then the local connection forms obey

$$
\mathcal A_j
=
g_{ij}^{-1}\mathcal A_i g_{ij}+g_{ij}^{-1}dg_{ij}.
$$

This is the principal-bundle version of the same transformation law above.

## Associated-bundle covariant derivative

Let $E=P\times_\rho V$ be the vector bundle associated to a representation

$$
\rho:G\to GL(V).
$$

The Lie algebra representation is

$$
\rho_*:\mathfrak g\to\operatorname{End}(V).
$$

A principal connection $\omega$ induces a covariant derivative on $E$. In a local gauge, if the matter field is represented by $\psi_i:U_i\to V$, then

$$
\nabla\psi_i=d\psi_i+\rho_*(\mathcal A_i)\psi_i.
$$

For compact gauge groups in physics notation, this becomes

$$
D\psi=d\psi+igA^aT_R^a\psi.
$$

The covariant derivative is what allows local derivatives of charged fields to transform like charged fields:

$$
D\psi\quad\text{transforms in the same representation as}\quad \psi.
$$

This is the entire local mechanism behind minimal coupling.

## Curvature

The curvature of a connection is the obstruction to covariant derivatives commuting. In local form, for

$$
\nabla=d+\mathcal A,
$$

the curvature two-form is

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

For an associated-bundle section,

$$
\nabla^2\psi=\rho_*(\mathcal F)\psi.
$$

In components,

$$
[\nabla_\mu,\nabla_\nu]\psi
=\rho_*(\mathcal F_{\mu\nu})\psi.
$$

If $\mathcal A$ is matrix-valued, the product in $\mathcal A\wedge\mathcal A$ includes matrix multiplication:

$$
(\mathcal A\wedge\mathcal A)^a{}_b
=
\mathcal A^a{}_c\wedge\mathcal A^c{}_b.
$$

For an Abelian connection, the algebra commutes and the quadratic term vanishes in the usual scalar representation, so locally

$$
\mathcal F=d\mathcal A.
$$

For a non-Abelian connection, the quadratic term is essential. It is the geometric reason Yang–Mills gauge fields self-interact.

## Curvature transforms tensorially

Under a change of local frame,

$$
\mathcal A_i
=
g_{ij}\mathcal A_jg_{ij}^{-1}-dg_{ij}g_{ij}^{-1},
$$

the curvature transforms as

$$
\mathcal F_i=g_{ij}\mathcal F_jg_{ij}^{-1}.
$$

There is no inhomogeneous derivative term. This is why curvature is tensorial while the connection is not.

For an associated field,

$$
\nabla_i^2\psi_i
=
\rho_*(\mathcal F_i)\psi_i
$$

transforms in the same way as $\psi_i$. In physics language, $F_{\mu\nu}$ is gauge-covariant, while $A_\mu$ is not.

This is also why local expressions such as $\operatorname{tr}(\mathcal F\wedge *\mathcal F)$ and $\operatorname{tr}(\mathcal F\wedge\mathcal F)$ can define global gauge-invariant action terms.

## Bianchi identity

Define the exterior covariant derivative on adjoint-valued forms by

$$
D\alpha=d\alpha+[\mathcal A,\alpha].
$$

The curvature satisfies the Bianchi identity

$$
D\mathcal F=0.
$$

In local form,

$$
d\mathcal F+\mathcal A\wedge\mathcal F-\mathcal F\wedge\mathcal A=0.
$$

This follows directly from

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A
$$

and $d^2=0$.

In Abelian gauge theory, this reduces to

$$
dF=0,
$$

which is the geometric form of the homogeneous Maxwell equations. In non-Abelian gauge theory, it is the identity

$$
D_{[\mu}F_{\nu\rho]}=0.
$$

The Bianchi identity is not an equation of motion. It is a structural identity following from the definition of curvature.

## Parallel transport and holonomy

Let $\gamma:[0,1]\to M$ be a path. A connection defines parallel transport along $\gamma$. In a local trivialization, a section $\psi(t)$ along the path is parallel if

$$
\frac{d\psi}{dt}+\mathcal A_\mu(\gamma(t))\dot\gamma^\mu(t)\psi=0.
$$

The solution is

$$
\psi(1)=U_\gamma\psi(0),
$$

where

$$
U_\gamma=\mathcal P\exp\left(-\int_\gamma\mathcal A\right).
$$

The symbol $\mathcal P$ means path ordering. It is necessary when the matrices $\mathcal A_\mu$ at different points do not commute.

For a closed loop $\gamma$, the conjugacy class of $U_\gamma$ is the holonomy around the loop. In a representation $R$, the Wilson loop is

$$
W_R(\gamma)=\operatorname{tr}_R\,\mathcal P\exp\left(-\int_\gamma\mathcal A\right).
$$

In physics notation, with $\mathcal A=igA^aT^a$,

$$
W_R(\gamma)=\operatorname{tr}_R\,\mathcal P\exp\left(-ig\int_\gamma A^aT_R^a\right)
$$

with the sign following the convention $D=d+igA^aT^a$.

Curvature is infinitesimal holonomy. Around a very small loop bounding an area element, the holonomy differs from the identity by a term proportional to $\mathcal F$ evaluated on that area. Flat connections have zero local curvature, but they can still have nontrivial holonomy around noncontractible loops.

That last sentence is a common source of delicious trouble.

## Physics convention for compact gauge groups

The mathematical formulas above use a Lie-algebra-valued connection $\mathcal A$. For compact gauge groups in the site’s physics convention, generators are Hermitian:

$$
[T^a,T^b]=if^{abc}T^c.
$$

The matter covariant derivative is

$$
D=d+igA^aT^a.
$$

Thus

$$
\mathcal A=igA^aT^a.
$$

The curvature is defined by

$$
D^2=igF^aT^a,
$$

so

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=igF^aT^a.
$$

Expanding gives

$$
F^a=dA^a-\frac{g}{2}f^{abc}A^b\wedge A^c.
$$

In components,

$$
F^a_{\mu\nu}
=
\partial_\mu A^a_\nu-\partial_\nu A^a_\mu
-gf^{abc}A^b_\mu A^c_\nu.
$$

This sign is convention-dependent because some authors use anti-Hermitian generators or define $D=d-igA^aT^a$. The invariant statement is the compact one:

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

When signs become confusing, translate back to $\mathcal A$ and only then return to physics notation.

## Abelian example: electromagnetism

For $G=U(1)$, the Lie algebra is Abelian. Locally the gauge potential is a one-form

$$
A=A_\mu dx^\mu.
$$

The field strength is

$$
F=dA.
$$

In components,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The Bianchi identity is

$$
dF=0.
$$

On a topologically nontrivial bundle, $F$ can be a globally defined closed two-form even when no single global one-form $A$ exists. This is the geometric resolution of the Dirac monopole: the magnetic field strength is global, while the vector potential is patchwise.

For a monopole of integer charge $n$ on $S^2$, one can choose local potentials on northern and southern patches whose curvatures agree on the overlap and define

$$
\frac{1}{2\pi}\int_{S^2}F=n.
$$

This integer is the first Chern number of the line bundle.

## Non-Abelian example: Yang–Mills curvature

For a non-Abelian gauge group, write the local gauge field in physics convention as

$$
A=A^aT^a.
$$

The field strength is

$$
F^a=dA^a-\frac{g}{2}f^{abc}A^b\wedge A^c.
$$

The Yang–Mills kinetic term is built from the gauge-invariant pairing

$$
\operatorname{tr}(F\wedge *F)
$$

or, in components and convention-dependent normalization,

$$
-\frac14 F^a_{\mu\nu}F^{a\mu\nu}.
$$

The non-Abelian Bianchi identity is

$$
DF=0.
$$

The equation of motion in pure Yang–Mills theory is instead

$$
D*F=0
$$

up to normalization and matter currents. The pair

$$
DF=0,
\qquad
D*F=J
$$

is the non-Abelian analogue of Maxwell’s equations, but the first equation is geometric while the second comes from varying the action.

## Geometric example: tangent-bundle connections

Connections are not only for internal gauge groups. A connection on the tangent bundle $TM$ differentiates vector fields. In local coordinates,

$$
\nabla_\mu V^\rho=\partial_\mu V^\rho+\Gamma^\rho{}_{\mu\nu}V^\nu.
$$

The coefficients $\Gamma^\rho{}_{\mu\nu}$ are Christoffel symbols for the Levi-Civita connection when a metric is present and the connection is torsion-free and metric-compatible.

The curvature is the Riemann tensor, defined by

$$
[\nabla_\mu,\nabla_\nu]V^\rho
=R^\rho{}_{\sigma\mu\nu}V^\sigma
$$

for a torsion-free coordinate basis.

This is the same pattern as gauge theory:

$$
\text{connection coefficients }\Gamma
\quad\longrightarrow\quad
\text{curvature }R.
$$

Spin connections and gauge connections are two versions of the same idea, adapted to different bundles.

## Local versus global connection data

A connection on a nontrivial bundle is not a single globally defined $\mathfrak g$-valued one-form on $M$. It is a collection of local one-forms $\mathcal A_i$ glued by

$$
\mathcal A_j=g_{ij}^{-1}\mathcal A_i g_{ij}+g_{ij}^{-1}dg_{ij}.
$$

The curvature forms glue tensorially:

$$
\mathcal F_j=g_{ij}^{-1}\mathcal F_i g_{ij}.
$$

For Abelian $U(1)$, the adjoint action is trivial, so the local curvatures agree as ordinary two-forms:

$$
F_j=F_i.
$$

This is why the electromagnetic field strength can be global even when the vector potential is not.

In a path integral over gauge fields, one should in principle sum or integrate over connections on all allowed principal bundles, not merely over globally defined one-forms on a trivial bundle. In perturbative calculations, one often restricts to the trivial sector and writes $A$ globally. That is a choice of approximation or sector, not the definition of gauge theory in full generality.

## Common pitfalls

**“The connection is a tensor.”** The local connection form $\mathcal A$ is not tensorial; it has an inhomogeneous transformation law. The curvature $\mathcal F$ transforms tensorially.

**“Curvature is just $dA$.”** Only for Abelian gauge theory, or locally after ignoring non-Abelian commutators. In general,

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

**“A flat connection is gauge-equivalent to zero.”** Locally, often yes. Globally, not necessarily. Flat connections can have nontrivial holonomy around noncontractible loops.

**“Gauge choice and gauge field are the same thing.”** A gauge choice is a local section or trivialization. The gauge field is a connection. The local one-form $A$ is the connection expressed in that gauge.

**“The Bianchi identity is a dynamical equation.”** It is not. It follows from the definition of curvature. The Yang–Mills equation $D*F=J$ is dynamical.

**“Different sign conventions for $F_{\mu\nu}$ are harmless.”** They are harmless only when translated consistently through $D$, $F$, Wilson lines, Chern–Simons terms, theta terms, and anomaly formulas. Half-translated conventions are a rite of passage, but not a good one.

## Exercises

### Exercise 1: Derive the connection transformation law

Suppose local section components obey

$$
\psi_i=g_{ij}\psi_j.
$$

Demand that

$$
(d+\mathcal A_i)\psi_i=g_{ij}(d+\mathcal A_j)\psi_j.
$$

Derive

$$
\mathcal A_i=g_{ij}\mathcal A_jg_{ij}^{-1}-dg_{ij}g_{ij}^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

Substitute $\psi_i=g_{ij}\psi_j$:

$$
(d+\mathcal A_i)(g_{ij}\psi_j)
=dg_{ij}\,\psi_j+g_{ij}d\psi_j+
\mathcal A_i g_{ij}\psi_j.
$$

The desired right-hand side is

$$
g_{ij}(d+\mathcal A_j)\psi_j
=g_{ij}d\psi_j+g_{ij}\mathcal A_j\psi_j.
$$

Cancel $g_{ij}d\psi_j$ and require the remaining terms to agree for all $\psi_j$:

$$
dg_{ij}+\mathcal A_i g_{ij}=g_{ij}\mathcal A_j.
$$

Multiplying on the right by $g_{ij}^{-1}$ gives

$$
\mathcal A_i=g_{ij}\mathcal A_jg_{ij}^{-1}-dg_{ij}g_{ij}^{-1}.
$$

</details>

### Exercise 2: Curvature transforms tensorially

Using

$$
\mathcal A'=h^{-1}\mathcal A h+h^{-1}dh,
$$

show that

$$
\mathcal F'=h^{-1}\mathcal Fh.
$$

<details><summary><strong>Solution</strong></summary>

A quick derivation uses the covariant derivative. If

$$
\nabla=d+\mathcal A,
\qquad
\nabla'=d+\mathcal A',
$$

then the transformation law is equivalent to

$$
\nabla'=h^{-1}\nabla h
$$

as an operator on local representatives. Squaring gives

$$
(\nabla')^2=h^{-1}\nabla^2h.
$$

Since $\nabla^2=\mathcal F$ and $(\nabla')^2=\mathcal F'$, we obtain

$$
\mathcal F'=h^{-1}\mathcal Fh.
$$

The same result follows by direct expansion of $d\mathcal A'+\mathcal A'\wedge\mathcal A'$ and use of $d(h^{-1})=-h^{-1}(dh)h^{-1}$.

</details>

### Exercise 3: Prove the Bianchi identity

Let

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A.
$$

Show that

$$
D\mathcal F=d\mathcal F+\mathcal A\wedge\mathcal F-\mathcal F\wedge\mathcal A=0.
$$

<details><summary><strong>Solution</strong></summary>

First compute

$$
d\mathcal F=d(\mathcal A\wedge\mathcal A)
=d\mathcal A\wedge\mathcal A-\mathcal A\wedge d\mathcal A,
$$

using $d^2\mathcal A=0$ and the graded Leibniz rule. Next,

$$
\mathcal A\wedge\mathcal F
=\mathcal A\wedge d\mathcal A+\mathcal A\wedge\mathcal A\wedge\mathcal A,
$$

and

$$
\mathcal F\wedge\mathcal A
=d\mathcal A\wedge\mathcal A+\mathcal A\wedge\mathcal A\wedge\mathcal A.
$$

Therefore

$$
d\mathcal F+\mathcal A\wedge\mathcal F-\mathcal F\wedge\mathcal A=0.
$$

</details>

### Exercise 4: Abelian monopole flux

Let $S^2$ have coordinates $(\theta,\varphi)$ away from the poles, and define

$$
F=\frac n2\sin\theta\,d\theta\wedge d\varphi.
$$

Compute

$$
\frac{1}{2\pi}\int_{S^2}F.
$$

<details><summary><strong>Solution</strong></summary>

Using $0\leq\theta\leq\pi$ and $0\leq\varphi<2\pi$,

$$
\int_{S^2}F
=
\frac n2\int_0^\pi\sin\theta\,d\theta\int_0^{2\pi}d\varphi.
$$

Since

$$
\int_0^\pi\sin\theta\,d\theta=2,
$$

we get

$$
\int_{S^2}F
=
\frac n2\cdot 2\cdot 2\pi=2\pi n.
$$

Therefore

$$
\frac{1}{2\pi}\int_{S^2}F=n.
$$

This is the first Chern number in the normalization used here.

</details>

### Exercise 5: Pure gauge curvature

Let

$$
\mathcal A=h^{-1}dh
$$

for a smooth map $h:U\to G$. Show that

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=0.
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
d(h^{-1})=-h^{-1}(dh)h^{-1}.
$$

Then

$$
d\mathcal A=d(h^{-1}dh)=d(h^{-1})\wedge dh
=-h^{-1}dh\wedge h^{-1}dh.
$$

But

$$
\mathcal A\wedge\mathcal A
=h^{-1}dh\wedge h^{-1}dh.
$$

Therefore

$$
\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A=0.
$$

This is the Maurer–Cartan identity. It proves local flatness for a pure gauge connection.

</details>

## Relations to other pages

[Fiber Bundles](/math-toolkit/geometry-of-fields/fiber-bundles/) explains the global bundle data that local connection forms live on. [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) explains the wedge product and exterior derivative used in $\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A$. [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/) gives the flow language behind infinitesimal geometric transformations. [Gauge Group Data](/math-toolkit/groups-representations/gauge-group-data/) explains the Lie algebra, representation, and global group data needed for gauge theory.

Later pages on holonomy, gauge fields as connections, Riemannian and Lorentzian geometry, spin structures, Dirac operators, characteristic classes, index theorems, anomalies, instantons, and Wilson loops should link back here.

## Research status

The ordinary theory of connections and curvature on smooth finite-dimensional bundles is settled. In QFT, the subtleties come from how this smooth geometry is used: summing over topological sectors, quantizing gauge redundancies, treating singular defects, defining higher-form gauge fields, coupling to background bundles for generalized symmetries, and specifying global forms of gauge groups.

A good working habit is to separate local differential geometry from global and quantum questions. The formula $\mathcal F=d\mathcal A+\mathcal A\wedge\mathcal A$ is local and exact. Which bundles are summed over, which Wilson lines are allowed, whether a connection has singularities, and how gauge fixing is performed are additional physical choices.

## References

- M. Nakahara, *Geometry, Topology and Physics*. A standard physics-friendly reference for bundles, connections, curvature, monopoles, instantons, characteristic classes, and spinors.
- T. Frankel, *The Geometry of Physics*. Excellent for geometric intuition about connections, curvature, forms, gauge fields, and physical applications.
- S. Kobayashi and K. Nomizu, *Foundations of Differential Geometry*, Vol. I. A standard mathematical reference for principal connections and curvature.
- T. Eguchi, P. B. Gilkey, and A. J. Hanson, “Gravitation, Gauge Theories and Differential Geometry.” A classic review connecting differential geometry to gauge theory and gravity.
- J. Baez and J. P. Muniain, *Gauge Fields, Knots and Gravity*, and R. Wald, *General Relativity*, are useful complementary sources for gauge fields, holonomy, curvature, and spacetime geometry.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for Wilson loops, gauge topology, instantons, compact gauge fields, and the geometric viewpoint on QFT.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, and M. Srednicki, *Quantum Field Theory*. Useful for translating the geometric connection language into standard non-Abelian gauge theory conventions.

## Version history

- **2026-06-25:** Initial polished draft. Added covariant derivatives, principal connections, associated-bundle derivatives, curvature, transformation laws, Bianchi identity, holonomy, physics convention translation, Abelian and non-Abelian examples, tangent-bundle analogy, common pitfalls, exercises, and figure.
