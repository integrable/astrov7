---
title: "Differential Forms"
description: "Defines differential forms as antisymmetric covariant tensor fields, explains wedge products, exterior derivatives, pullbacks, integration, Stokes’ theorem, Hodge stars, and their use in QFT."
sidebar:
  label: "Differential Forms"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard geometry-for-physics references, including Nakahara, Frankel, Bott–Tu, Schutz, and QFT treatments of gauge fields, currents, and topological terms."
topics:
  - differential forms
  - exterior algebra
  - wedge product
  - exterior derivative
  - pullback
  - integration
  - Stokes theorem
  - Hodge star
  - gauge fields
canonicalTopics:
  - differential-forms
  - exterior-algebra
  - wedge-product
  - exterior-derivative
  - pullback-of-forms
  - integration-of-forms
  - stokes-theorem
  - hodge-star
researchStatus:
  established:
    - "Differential forms, wedge products, exterior derivatives, pullbacks, integration of forms, and Stokes’ theorem are standard tools in differential geometry and modern field theory."
  active:
    - "Modern QFT uses differential forms in refined settings involving generalized symmetries, higher-form gauge fields, differential cohomology, anomalies, defects, and topological phases."
---

## Summary

Differential forms are the objects that integrate naturally. A one-form integrates over a curve, a two-form over a surface, and a $d$-form over a $d$-dimensional spacetime. They are antisymmetric covariant tensor fields, but that description undersells them: forms come with a product $\wedge$, a metric-independent derivative $d$, a natural pullback to submanifolds, and the master identity

$$
\int_W d\omega=\int_{\partial W}\omega.
$$

That identity is Stokes’ theorem. It contains the fundamental theorem of calculus, Green’s theorem, the divergence theorem, and many QFT boundary manipulations as special cases.

A $p$-form on a smooth manifold $M$ is a smooth section

$$
\omega\in\Omega^p(M)=\Gamma(\Lambda^pT^*M).
$$

In local coordinates,

$$
\omega
=
\frac1{p!}\omega_{\mu_1\cdots\mu_p}(x)
\,dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p},
$$

where the components are antisymmetric in their indices. The wedge product is graded-commutative,

$$
\alpha\wedge\beta=(-1)^{pq}\beta\wedge\alpha,
\qquad
\alpha\in\Omega^p(M),\quad\beta\in\Omega^q(M).
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flow diagram showing p-forms, local wedge expressions, pullback to an oriented submanifold, integration, exterior derivative, d squared equals zero, Stokes theorem, and QFT uses.](/figures/math-toolkit/differential-forms-integration-flow.svg)

<figcaption>

Differential forms combine algebra and integration. A $p$-form $\omega$ can be pulled back to an oriented $p$-dimensional submanifold $\Sigma^p$ and integrated. The exterior derivative $d$ raises degree by one, obeys $d^2=0$, and is related to boundary terms by Stokes’ theorem.

</figcaption>
</figure>

In QFT, forms are everywhere: gauge potentials are one-forms, field strengths are two-forms, conserved currents are often best viewed as closed $(d-1)$-forms, topological terms are built from wedge products of curvature forms, and Wilson lines are integrals of connections along curves.

## Prerequisites

Read [Manifolds](/math-toolkit/geometry-of-fields/manifolds/) first. You should know what tangent and cotangent spaces are, what a smooth map is, and why coordinates are local descriptions rather than the object itself. The page [Mathematical Conventions](/math-toolkit/conventions/) fixes the site’s spacetime and sign conventions.

This page introduces the form language needed later for integration on manifolds, Lie derivatives, bundles, connections and curvature, gauge fields as connections, characteristic classes, anomalies, and topological terms.

## Core idea

A $p$-form is something you feed $p$ tangent vectors, and it returns a number, antisymmetrically:

$$
\omega_p:T_pM\times\cdots\times T_pM\to\mathbb R.
$$

Antisymmetrically means that swapping two arguments flips the sign:

$$
\omega_p(\ldots,X_i,\ldots,X_j,\ldots)
=
-\omega_p(\ldots,X_j,\ldots,X_i,\ldots).
$$

If two arguments are equal, the value is zero. This is why a two-form measures oriented area rather than two independent line elements, and why a top-form measures oriented volume.

The geometric magic is that $p$-forms are exactly the objects that integrate over $p$-dimensional oriented manifolds. You do not need a metric to integrate a $p$-form over a $p$-dimensional oriented submanifold. You need orientation and smoothness. A metric becomes necessary only when you want to turn vectors into covectors, define lengths and angles, or use the Hodge star.

This leads to the QFT slogan:

$$
\text{forms know how to pull back, wedge, differentiate, and integrate.}
$$

That is why they are the native language of flux, holonomy, topological terms, descent equations, Wess–Zumino terms, Chern–Simons terms, theta terms, generalized symmetries, and anomaly inflow.

## Exterior algebra at one point

At a point $p\in M$, a $p$-form is an element of $\Lambda^pT_p^*M$, the $p$th exterior power of the cotangent space. If $\dim M=d$, then

$$
\Lambda^pT_p^*M=0
\qquad\text{for }p>d.
$$

A zero-form is just a function:

$$
\Omega^0(M)=C^\infty(M).
$$

A one-form has local expression

$$
\alpha=\alpha_\mu dx^\mu.
$$

A two-form has local expression

$$
\omega=\frac12\omega_{\mu\nu}dx^\mu\wedge dx^\nu,
\qquad
\omega_{\mu\nu}=-\omega_{\nu\mu}.
$$

The factor $1/2$ prevents double-counting because the antisymmetric components already contain both $\mu\nu$ and $\nu\mu$. More generally,

$$
\omega
=
\frac1{p!}\omega_{\mu_1\cdots\mu_p}
\,dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p}.
$$

The basis one-forms satisfy

$$
dx^\mu\wedge dx^\nu=-dx^\nu\wedge dx^\mu,
\qquad
 dx^\mu\wedge dx^\mu=0.
$$

If $\alpha$ is a $p$-form and $\beta$ is a $q$-form, then $\alpha\wedge\beta$ is a $(p+q)$-form. If $p+q>d$, it vanishes on a $d$-dimensional manifold.

## Wedge product

The wedge product is bilinear, associative, and graded-commutative:

$$
\alpha\wedge(\beta\wedge\gamma)=(\alpha\wedge\beta)\wedge\gamma,
$$

$$
\alpha\wedge\beta=(-1)^{pq}\beta\wedge\alpha,
\qquad
\alpha\in\Omega^p(M),\quad\beta\in\Omega^q(M).
$$

For two one-forms

$$
\alpha=\alpha_\mu dx^\mu,
\qquad
\beta=\beta_\nu dx^\nu,
$$

the wedge product is

$$
\alpha\wedge\beta
=
\alpha_\mu\beta_\nu dx^\mu\wedge dx^\nu
=
\frac12(\alpha_\mu\beta_\nu-\alpha_\nu\beta_\mu)dx^\mu\wedge dx^\nu.
$$

Only the antisymmetric part contributes. This is the same antisymmetry that appears in field strengths such as

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

and angular-momentum-like area elements.

A useful warning: if $\alpha$ is an odd-degree form, then

$$
\alpha\wedge\alpha=0.
$$

If $\alpha$ is even-degree, this conclusion does not follow. For example, a two-form $F$ can have

$$
F\wedge F\neq 0
$$

in four dimensions. This is why theta terms and instanton densities exist.

## Exterior derivative

The exterior derivative is a linear map

$$
d:\Omega^p(M)\to\Omega^{p+1}(M)
$$

with three defining properties:

$$
d^2=0,
$$

$$
d(\alpha\wedge\beta)=d\alpha\wedge\beta+(-1)^p\alpha\wedge d\beta,
\qquad
\alpha\in\Omega^p(M),
$$

and on functions it agrees with the ordinary differential,

$$
df=\partial_\mu f\,dx^\mu.
$$

In coordinates, for

$$
\omega=\frac1{p!}\omega_{\mu_1\cdots\mu_p}dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p},
$$

one has

$$
d\omega
=
\frac1{p!}\partial_\nu\omega_{\mu_1\cdots\mu_p}
\,dx^\nu\wedge dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p}.
$$

Equivalently, with antisymmetrization brackets normalized with unit weight,

$$
(d\omega)_{\mu_0\mu_1\cdots\mu_p}
=
(p+1)\partial_{[\mu_0}\omega_{\mu_1\cdots\mu_p]}.
$$

The identity $d^2=0$ is the coordinate-free form of “mixed partial derivatives commute,” but it carries much more structure. It is the reason exact forms are closed, the reason Bianchi identities are automatic for abelian field strengths, and the algebraic engine behind de Rham cohomology.

A form is **closed** if

$$
d\omega=0.
$$

It is **exact** if there exists a form $\eta$ such that

$$
\omega=d\eta.
$$

Every exact form is closed because $d^2=0$. The converse can fail globally. That failure is topology.

## Pullback of forms

If $F:N\to M$ is a smooth map, then every form on $M$ pulls back to a form on $N$:

$$
F^*:\Omega^p(M)\to\Omega^p(N).
$$

The pullback is defined by feeding pushed-forward vectors into the original form:

$$
(F^*\omega)_q(X_1,\ldots,X_p)
=
\omega_{F(q)}(F_*X_1,\ldots,F_*X_p).
$$

In coordinates, if $x^\mu=x^\mu(\sigma)$ describes the map, then

$$
F^*(dx^\mu)=\frac{\partial x^\mu}{\partial\sigma^a}d\sigma^a.
$$

For a one-form $A=A_\mu(x)dx^\mu$, the pullback along a curve $x^\mu=x^\mu(t)$ is

$$
F^*A=A_\mu(x(t))\frac{dx^\mu}{dt}dt.
$$

Therefore the line integral is

$$
\int_\gamma A=\int dt\,A_\mu(x(t))\dot x^\mu(t).
$$

This is the geometric content of the coupling of a charged point particle to a background gauge potential.

Pullback is also why forms are perfect for branes and defects. If a $p$-dimensional worldvolume $\Sigma$ is embedded in spacetime by

$$
X:\Sigma\to M,
$$

then a spacetime $p$-form $C$ couples by

$$
\int_\Sigma X^*C.
$$

The notation often suppresses the $X^*$, but the pullback is what is actually happening.

## Integration of forms

A $p$-form can be integrated over an oriented $p$-dimensional manifold or submanifold. If $\Sigma$ has local coordinates $\sigma^1,\ldots,\sigma^p$ and $X:\Sigma\to M$ is its inclusion or embedding, then

$$
\int_\Sigma \omega
=
\int X^*\omega.
$$

In coordinates,

$$
X^*\omega
=
\frac1{p!}\omega_{\mu_1\cdots\mu_p}(X(\sigma))
\frac{\partial X^{\mu_1}}{\partial\sigma^{a_1}}\cdots
\frac{\partial X^{\mu_p}}{\partial\sigma^{a_p}}
\,d\sigma^{a_1}\wedge\cdots\wedge d\sigma^{a_p}.
$$

This expression contains the Jacobian factors automatically. No metric is needed. Orientation fixes the sign of the integral.

Some examples:

| Form degree | Integrated over | Typical QFT use |
|---:|---|---|
| $0$ | points | local operator values |
| $1$ | curves | Wilson lines, Berry phases, point-particle couplings |
| $2$ | surfaces | fluxes, surface operators, string couplings |
| $d-1$ | spatial slices or linking surfaces | charges and conserved currents |
| $d$ | spacetime | action terms, topological densities |

A top-degree form on a $d$-manifold can be integrated over all of $M$ if $M$ is oriented and suitable convergence or compact-support conditions hold. A Lagrangian written as a $d$-form is therefore coordinate-invariant by construction.

## Stokes theorem

For an oriented manifold $W$ with boundary $\partial W$, Stokes’ theorem says

$$
\int_W d\omega=\int_{\partial W}\omega.
$$

The orientation on $\partial W$ is induced from the orientation on $W$. This sign convention is not optional; it is part of the theorem.

Many familiar identities are special cases. If $W=[a,b]$ and $\omega=f$ is a zero-form, then

$$
\int_a^b df=f(b)-f(a).
$$

In vector calculus, Stokes’ theorem and the divergence theorem are coordinate expressions of the same differential-form statement after choosing a metric to translate vectors into forms.

In QFT, Stokes’ theorem is the geometric skeleton behind integration by parts. If a variation produces a total derivative, it becomes a boundary term. If a current form $J$ is closed,

$$
dJ=0,
$$

then the charge

$$
Q_\Sigma=\int_\Sigma J
$$

is invariant under smooth deformations of $\Sigma$ that do not cross operator insertions or boundaries. That is the differential-form version of charge conservation.

## Metric dependence and the Hodge star

The exterior derivative $d$, wedge product $\wedge$, and pullback are defined without a metric. The Hodge star is different. On an oriented $d$-dimensional manifold with metric $g$, the Hodge star maps

$$
\star:\Omega^p(M)\to\Omega^{d-p}(M).
$$

It is defined so that for $p$-forms $\alpha$ and $\beta$,

$$
\alpha\wedge\star\beta=(\alpha,\beta)_g\operatorname{vol}_g,
$$

where $(\alpha,\beta)_g$ is the metric-induced inner product on $p$-forms and $\operatorname{vol}_g$ is the metric volume form.

The Hodge star is what lets a kinetic term pair a form with itself:

$$
\int_M F\wedge\star F.
$$

It is also what converts a one-form current $j^\flat$ into a conserved $(d-1)$-form

$$
J=\star j^\flat.
$$

In Lorentzian signature, signs involving $\star\star$ depend on both the degree and the signature. This is one reason Euclidean and Lorentzian conventions must be tracked carefully.

For the site’s mostly-minus Lorentzian convention in four dimensions, the Maxwell action can be written schematically as

$$
S=-\frac12\int_M F\wedge\star F,
$$

which corresponds locally to

$$
S=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}
$$

in flat spacetime. The precise sign of related formulas depends on whether the page is working Lorentzian or Euclidean.

## Gauge fields in form notation

For an abelian gauge field, the gauge potential is a one-form

$$
A=A_\mu dx^\mu,
$$

and the field strength is the two-form

$$
F=dA.
$$

In components,

$$
F=\frac12F_{\mu\nu}dx^\mu\wedge dx^\nu,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The identity

$$
dF=d^2A=0
$$

is the abelian Bianchi identity.

For a nonabelian gauge field, the gauge potential is Lie-algebra-valued:

$$
A=A_\mu^a T_a dx^\mu.
$$

The curvature is

$$
F=dA+A\wedge A.
$$

Here $A\wedge A$ includes both the wedge product of forms and the matrix or Lie-algebra product of the generators. It is not zero in general, even though $A$ is a one-form, because the matrix coefficients need not commute.

In components,

$$
F_{\mu\nu}
=
\partial_\mu A_\nu-\partial_\nu A_\mu+[A_\mu,A_\nu].
$$

The nonabelian Bianchi identity is

$$
D_AF=0,
$$

where $D_A$ is the exterior covariant derivative. This is a preview of the connections and curvature page; the form notation already shows why the formula is compact.

## Currents and charges

A conserved vector current $j^\mu$ in $d$ spacetime dimensions is often written as

$$
\partial_\mu j^\mu=0.
$$

In form language, use the metric to form the one-form

$$
j^\flat=j_\mu dx^\mu,
$$

and then define the $(d-1)$-form

$$
J=\star j^\flat.
$$

Conservation becomes

$$
dJ=0.
$$

The charge on a spatial slice $\Sigma$ is

$$
Q_\Sigma=\int_\Sigma J.
$$

If $\Sigma_1$ and $\Sigma_2$ bound a spacetime region $W$, and no charged insertions or fluxes cross the region, Stokes’ theorem gives

$$
Q_{\Sigma_2}-Q_{\Sigma_1}=\int_{\partial W}J=\int_W dJ=0,
$$

up to the orientation convention on the boundary. Conservation is therefore a homological statement: the charge depends only on the deformation class of the slice, as long as no sources are crossed.

This viewpoint generalizes beautifully. Higher-form symmetries are naturally expressed by closed forms integrated over higher-codimension surfaces. The ordinary continuity equation is only the first example.

## Closed versus exact

Because $d^2=0$, every exact form is closed. But a closed form need not be exact. The obstruction is measured by de Rham cohomology:

$$
H^p_{\mathrm{dR}}(M)=\frac{\ker(d:\Omega^p\to\Omega^{p+1})}{\operatorname{im}(d:\Omega^{p-1}\to\Omega^p)}.
$$

The local Poincaré lemma says that on a small enough contractible patch, every closed form is exact. Thus the failure of closed to imply exact is global.

This is not abstract fluff. If $F$ is an abelian field strength with

$$
dF=0,
$$

then locally $F=dA$. Globally, there may be no single gauge potential $A$ defined everywhere. Magnetic monopoles, flux sectors, theta terms, Berry phases, and Aharonov–Bohm effects all exploit the difference between local potentials and global form data.

The later topology and characteristic-class pages develop this systematically. For now, remember the practical test: integrals of closed forms over closed cycles can detect global information.

## QFT dictionary

Differential forms condense many standard QFT expressions:

| Physics object | Form notation | Comments |
|---|---|---|
| Abelian gauge potential | $A\in\Omega^1(M)$ | locally $A=A_\mu dx^\mu$ |
| Abelian field strength | $F=dA\in\Omega^2(M)$ | $dF=0$ automatically |
| Nonabelian connection | $A\in\Omega^1(M,\mathfrak g)$ | local representative of a connection |
| Nonabelian curvature | $F=dA+A\wedge A$ | components include $[A_\mu,A_\nu]$ |
| Wilson line | $\operatorname{tr}\,P\exp\int_\gamma A$ | path ordering for nonabelian $A$ |
| Charge current | $J=\star j^\flat\in\Omega^{d-1}(M)$ | conservation is $dJ=0$ |
| Maxwell action | $-\frac12\int F\wedge\star F$ | metric enters through $\star$ |
| Theta term in four dimensions | $\int F\wedge F$ or $\int\operatorname{tr}(F\wedge F)$ | metric-independent density |
| Chern–Simons term in three dimensions | $\int\operatorname{tr}(A\wedge dA+\frac23A\wedge A\wedge A)$ | gauge-invariant only with qualifications |
| Wess–Zumino coupling | $\int_\Sigma X^*C$ | pullback to a worldvolume |

Do not memorize this table as isolated notation. The point is structural: form degree matches integration dimension, $d$ encodes boundary terms and Bianchi identities, and $\star$ marks where the metric has entered.

## Common pitfalls

**A form is not the same thing as a vector field.** A one-form is a covector field. A metric can identify vectors and covectors, but the identification is extra structure.

**The symbol $dx^\mu$ is a basis one-form.** It is not a tiny number by itself. In integrals, notation inherited from calculus can obscure the fact that $dx^\mu$ is a covector basis element.

**The wedge product is antisymmetric and graded.** The sign is not optional. Moving a $p$-form past a $q$-form gives $(-1)^{pq}$.

**The exterior derivative is not the gauge-covariant derivative.** The operator $d$ acts on ordinary forms. Gauge-covariant exterior derivatives include connection terms and depend on the representation.

**The Hodge star requires a metric and orientation.** Expressions involving $\star$ are not purely topological. In particular, $F\wedge\star F$ depends on the metric, while $F\wedge F$ does not.

**A closed form need not be exact.** Locally closed often means locally exact, but global topology can obstruct a single potential. This is the mathematical seed of many topological effects in QFT.

**Do not drop pullbacks.** When integrating a spacetime form over a worldline or worldvolume, one really integrates the pullback. Suppressing the symbol is fine only after the operation is understood.

**Nonabelian $A\wedge A$ is not automatically zero.** The form degree gives a sign, but Lie-algebra or matrix multiplication contributes a commutator.

## Worked example: exterior derivative of a one-form

Let

$$
A=A_\mu dx^\mu.
$$

Then

$$
dA=d(A_\mu)\wedge dx^\mu
=
(\partial_\nu A_\mu dx^\nu)\wedge dx^\mu.
$$

Antisymmetrizing the coefficients,

$$
dA
=
\frac12(\partial_\nu A_\mu-\partial_\mu A_\nu)dx^\nu\wedge dx^\mu.
$$

Renaming dummy indices gives the standard form

$$
dA
=
\frac12(\partial_\mu A_\nu-\partial_\nu A_\mu)dx^\mu\wedge dx^\nu.
$$

Thus for an abelian gauge potential,

$$
F=dA,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The antisymmetry of $F_{\mu\nu}$ is not an extra assumption; it is built into the wedge product.

## Exercises

### Exercise 1: Wedge product of two one-forms

Let

$$
\alpha=a_\mu dx^\mu,
\qquad
\beta=b_\nu dx^\nu.
$$

Show that

$$
\alpha\wedge\beta
=
\frac12(a_\mu b_\nu-a_\nu b_\mu)dx^\mu\wedge dx^\nu.
$$

<details><summary><strong>Solution</strong></summary>

Start with bilinearity:

$$
\alpha\wedge\beta=a_\mu b_\nu dx^\mu\wedge dx^\nu.
$$

Only the antisymmetric part of $a_\mu b_\nu$ contributes because

$$
dx^\nu\wedge dx^\mu=-dx^\mu\wedge dx^\nu.
$$

Therefore

$$
a_\mu b_\nu dx^\mu\wedge dx^\nu
=
\frac12(a_\mu b_\nu-a_\nu b_\mu)dx^\mu\wedge dx^\nu.
$$

The symmetric part cancels.

</details>

### Exercise 2: Prove that $d^2f=0$

For a smooth function $f$, show in coordinates that

$$
d(df)=0.
$$

<details><summary><strong>Solution</strong></summary>

First

$$
df=\partial_\mu f\,dx^\mu.
$$

Taking another exterior derivative gives

$$
d(df)=\partial_\nu\partial_\mu f\,dx^\nu\wedge dx^\mu.
$$

The coefficient $\partial_\nu\partial_\mu f$ is symmetric in $\mu,\nu$ for a smooth function, while $dx^\nu\wedge dx^\mu$ is antisymmetric. Their contraction vanishes:

$$
\partial_\nu\partial_\mu f\,dx^\nu\wedge dx^\mu=0.
$$

Thus $d^2f=0$.

</details>

### Exercise 3: Pull back a one-form to a curve

Let $A=A_\mu(x)dx^\mu$ be a one-form on $M$, and let a curve be described by $x^\mu=x^\mu(t)$. Show that

$$
\int_\gamma A=\int dt\,A_\mu(x(t))\dot x^\mu(t).
$$

<details><summary><strong>Solution</strong></summary>

Let $X:I\to M$ be the map from the parameter interval to the curve, with coordinate expression $x^\mu(t)$. The pullback of the coordinate one-form is

$$
X^*(dx^\mu)=\frac{dx^\mu}{dt}dt.
$$

Therefore

$$
X^*A=A_\mu(x(t))\frac{dx^\mu}{dt}dt.
$$

Integrating over the parameter interval gives

$$
\int_\gamma A=\int_I X^*A=\int dt\,A_\mu(x(t))\dot x^\mu(t).
$$

</details>

### Exercise 4: Abelian Bianchi identity

Let $F=dA$ for an abelian one-form gauge potential $A$. Show that

$$
dF=0.
$$

Write the component version of this identity.

<details><summary><strong>Solution</strong></summary>

Since $F=dA$,

$$
dF=d(dA)=d^2A=0.
$$

In components, with

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

the identity is

$$
\partial_\lambda F_{\mu\nu}
+
\partial_\mu F_{\nu\lambda}
+
\partial_\nu F_{\lambda\mu}=0.
$$

Equivalently,

$$
\partial_{[\lambda}F_{\mu\nu]}=0,
$$

up to the chosen normalization of antisymmetrization brackets.

</details>

### Exercise 5: A closed form that is not exact

On $\mathbb R^2\setminus\{0\}$ define

$$
\omega=\frac{-y\,dx+x\,dy}{x^2+y^2}.
$$

Show that $d\omega=0$ away from the origin. Then restrict to the unit circle and show that

$$
\int_{S^1}\omega=2\pi.
$$

Explain why $\omega$ cannot be exact on $\mathbb R^2\setminus\{0\}$.

<details><summary><strong>Solution</strong></summary>

Write

$$
\omega=Pdx+Qdy,
\qquad
P=\frac{-y}{x^2+y^2},
\qquad
Q=\frac{x}{x^2+y^2}.
$$

Then

$$
d\omega=(\partial_x Q-\partial_y P)dx\wedge dy.
$$

Away from the origin,

$$
\partial_x Q=\frac{y^2-x^2}{(x^2+y^2)^2},
\qquad
\partial_y P=\frac{y^2-x^2}{(x^2+y^2)^2},
$$

so $d\omega=0$.

On the unit circle, set $x=\cos\theta$ and $y=\sin\theta$. Then

$$
dx=-\sin\theta\,d\theta,
\qquad
dy=\cos\theta\,d\theta.
$$

Thus

$$
\omega
=
-\sin\theta(-\sin\theta d\theta)+\cos\theta(\cos\theta d\theta)
=d\theta.
$$

Therefore

$$
\int_{S^1}\omega=\int_0^{2\pi}d\theta=2\pi.
$$

If $\omega$ were exact, $\omega=df$ for some globally defined smooth function $f$. The integral of an exact form over a closed loop would be zero by Stokes’ theorem:

$$
\int_{S^1}df=0.
$$

Since the integral is $2\pi$, $\omega$ is closed but not exact on $\mathbb R^2\setminus\{0\}$.

</details>

## References

- M. Nakahara, *Geometry, Topology and Physics*. Useful for differential forms, integration, de Rham cohomology, gauge fields, monopoles, instantons, and characteristic classes.
- T. Frankel, *The Geometry of Physics*. Especially useful for geometric intuition about forms, integration, Maxwell theory, phase space, gauge fields, and spinors.
- R. Bott and L. W. Tu, *Differential Forms in Algebraic Topology*. A standard reference for forms, Stokes’ theorem, de Rham cohomology, and the topology that forms detect.
- B. Schutz, *Geometrical Methods of Mathematical Physics*. A compact physics-friendly treatment of forms and their relation to vector calculus.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful for seeing forms reappear in gauge theory, topological terms, anomalies, and effective actions.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for gauge fields, Wilson loops, topology, instantons, and the geometric viewpoint in QFT.

## Version history

- **2026-06-25:** Initial polished draft. Defined differential forms, wedge products, exterior derivatives, pullbacks, integration, Stokes’ theorem, Hodge stars, gauge-field notation, currents, and the distinction between closed and exact forms.
