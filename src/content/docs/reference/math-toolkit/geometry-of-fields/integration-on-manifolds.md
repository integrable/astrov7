---
title: "Integration on Manifolds"
description: "Explains how differential forms are integrated over oriented manifolds and submanifolds, including pullbacks, boundary orientation, Stokes’ theorem, densities, and QFT applications."
sidebar:
  label: "Integration on Manifolds"
  order: 3
level: Graduate
status: "Polished draft"
source: "Standard geometry-for-physics references, including Nakahara, Frankel, Bott–Tu, Lee, and QFT treatments of actions, charges, fluxes, and topological terms."
topics:
  - integration on manifolds
  - orientation
  - pullbacks
  - Stokes theorem
  - manifolds with boundary
  - densities
  - volume forms
  - fluxes and charges
  - topological terms
canonicalTopics:
  - integration-of-differential-forms
  - oriented-manifolds
  - pullback-integration
  - manifolds-with-boundary
  - stokes-theorem
  - volume-forms
  - densities
  - de-rham-currents-preview
researchStatus:
  established:
    - "Integration of differential forms over oriented manifolds, the pullback definition of submanifold integrals, and Stokes’ theorem are standard foundations of differential geometry and geometric field theory."
  active:
    - "Modern QFT often extends these ideas to singular chains, distributional forms, stacks, orbifolds, defects, and generalized cohomology; this page treats the smooth finite-dimensional case and flags the QFT extensions without replacing them."
---

## Summary

Integration on a manifold is not “ordinary multiple integration plus fancy notation.” The geometric integral is a pairing between a differential form and an oriented domain of the same dimension:

$$
\int_{\Sigma^p}\omega,
\qquad
\omega\in\Omega^p(M),
$$

where $\Sigma^p$ is an oriented $p$-dimensional submanifold, chain, or integration domain. The form supplies the quantity to be measured; the orientation supplies the sign convention; a parameterization supplies a temporary coordinate description.

The clean definition is by pullback. If

$$
X:U\subset\mathbb R^p\to \Sigma\subset M
$$

is an orientation-preserving parameterization, then

$$
\int_\Sigma \omega
=
\int_U X^*\omega.
$$

The right-hand side is an ordinary integral over $U\subset\mathbb R^p$. The left-hand side is the coordinate-independent object. Changing coordinates on $U$ changes the components and the Jacobian in opposite ways, which is exactly why forms are the natural objects to integrate.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Diagram of an oriented manifold, an oriented submanifold, a parameter domain, the pullback definition of integration, and Stokes’ theorem as a boundary identity.](/figures/math-toolkit/integration-orientation-stokes.svg)

<figcaption>

Integration of forms is defined by pullback to a parameter domain. Orientation fixes the sign. Stokes’ theorem relates a bulk integral of $d\alpha$ to a boundary integral of $\alpha$, and is the geometric reason boundary terms, fluxes, and conserved charges appear everywhere in QFT.

</figcaption>
</figure>

The central theorem is Stokes’ theorem:

$$
\int_W d\alpha=\int_{\partial W}\alpha,
$$

where $W$ is an oriented manifold with boundary and $\partial W$ has the induced boundary orientation. This single formula contains the fundamental theorem of calculus, Green’s theorem, the divergence theorem, and the usual integration-by-parts identity. In field theory, it is the source of boundary terms in the action, conservation of charges, flux quantization formulas, and topological terms such as $\int F\wedge F$.

## Prerequisites

You should have read [Manifolds](/math-toolkit/geometry-of-fields/manifolds/) and [Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/). You should also be comfortable with multivariable change of variables, determinants, and the exterior derivative.

This page uses the sign and notation conventions fixed in [Mathematical Conventions](/math-toolkit/conventions/). No Riemannian or Lorentzian metric is assumed unless explicitly introduced. That point matters: differential forms can be integrated before one chooses a metric.

## Core idea

The core idea is type matching:

$$
\text{a }p\text{-form integrates over a }p\text{-dimensional oriented domain.}
$$

A one-form integrates along a curve. A two-form integrates over a surface. A $d$-form integrates over a $d$-dimensional spacetime or Euclidean manifold. The form degree must match the dimension of the integration domain.

This is different from integrating a scalar function. On an oriented $d$-manifold $M$, a scalar function $f$ is not by itself a $d$-form. To integrate $f$, one needs extra structure, usually a volume form $\mu$:

$$
\int_M f\,\mu.
$$

If a metric $g$ is chosen, the canonical metric volume form in local coordinates is

$$
\operatorname{vol}_g=\sqrt{|g|}\,dx^1\wedge\cdots\wedge dx^d,
\qquad
|g|=|\det g_{\mu\nu}|.
$$

Then a familiar action integral such as

$$
S=\int_M d^d x\,\sqrt{|g|}\,\mathcal L
$$

is really

$$
S=\int_M \mathcal L\,\operatorname{vol}_g.
$$

The first notation is convenient. The second notation is honest about what is being integrated.

## Orientation

An orientation on a $d$-dimensional real vector space is a choice of which ordered bases are positively oriented. Two bases have the same orientation if the change-of-basis matrix between them has positive determinant.

An orientation on a smooth $d$-manifold $M$ is a smoothly varying choice of orientation of every tangent space $T_pM$. Equivalently, it is an atlas whose transition maps have positive Jacobian determinants on overlaps. Another equivalent description is the existence of a nowhere-vanishing top form, considered up to multiplication by a positive function.

In local oriented coordinates $(x^1,\ldots,x^d)$, the coordinate top form

$$
dx^1\wedge\cdots\wedge dx^d
$$

is positive. Reversing the orientation reverses every integral of a top form:

$$
\int_{-M}\omega=-\int_M\omega.
$$

The minus sign is not decoration. In QFT it controls the sign of boundary terms, the orientation of Wilson lines and defects, the sign of fluxes, and the sign of topological charges.

An orientation is extra structure. Some manifolds, such as the Möbius strip or real projective plane $\mathbb{RP}^2$, are not orientable. On nonorientable manifolds, ordinary top forms cannot be globally integrated over the whole manifold in the same way. One then uses densities or twisted forms. This distinction becomes important in QFTs with orientation-reversing symmetries, parity, time reversal, and unoriented worldsheets.

## Integrating top forms in coordinates

Let $M$ be an oriented $d$-manifold and let $\omega\in\Omega^d(M)$ be compactly supported in one oriented coordinate chart. In that chart,

$$
\omega=f(x)\,dx^1\wedge\cdots\wedge dx^d.
$$

The integral is defined by

$$
\int_M\omega=\int_{\varphi(U)\subset\mathbb R^d} f(x)\,d^d x.
$$

This formula is independent of oriented coordinate changes. If $y=y(x)$ is another oriented coordinate system, then

$$
dy^1\wedge\cdots\wedge dy^d
=\n\det\left(\frac{\partial y}{\partial x}\right)
 dx^1\wedge\cdots\wedge dx^d.
$$

The usual change-of-variables theorem supplies the inverse determinant in the measure. The two factors cancel in exactly the right way.

For forms supported in multiple charts, one uses a partition of unity. Choose smooth functions $\rho_a$ subordinate to coordinate patches $U_a$, with

$$
0\le \rho_a\le 1,
\qquad
\sum_a \rho_a=1
$$

on the support of $\omega$. Then define

$$
\int_M\omega=\sum_a\int_{U_a}\rho_a\omega.
$$

The result is independent of the chosen partition. This is the precise version of the physicist’s phrase “integrate locally and patch the answer together.”

For noncompact manifolds, one needs convergence conditions. Compact support is the safest assumption. In QFT, many integrals are not absolutely convergent and require regularization, boundary conditions, or distributional interpretation. That is a physical issue on top of the geometric definition.

## Pullback and submanifold integrals

Let $\Sigma$ be an oriented $p$-dimensional submanifold of $M$, and let $i:\Sigma\hookrightarrow M$ be the inclusion. If $\omega\in\Omega^p(M)$, the integral over $\Sigma$ is

$$
\int_\Sigma \omega
\equiv
\int_\Sigma i^*\omega.
$$

The right-hand side means that $\omega$ is first restricted to vectors tangent to $\Sigma$. Components normal to $\Sigma$ do not contribute.

In a local parameterization

$$
X:U\subset\mathbb R^p\to M,
$$

the pullback of a one-form is

$$
X^*(A_\mu(x)dx^\mu)
=
A_\mu(X(u))\frac{\partial X^\mu}{\partial u^a}du^a.
$$

For a $p$-form

$$
\omega=\frac1{p!}\omega_{\mu_1\cdots\mu_p}(x)
 dx^{\mu_1}\wedge\cdots\wedge dx^{\mu_p},
$$

the pullback is

$$
X^*\omega
=
\frac1{p!}\omega_{\mu_1\cdots\mu_p}(X(u))
\frac{\partial X^{\mu_1}}{\partial u^{a_1}}\cdots
\frac{\partial X^{\mu_p}}{\partial u^{a_p}}
 du^{a_1}\wedge\cdots\wedge du^{a_p}.
$$

Because the wedge product antisymmetrizes the indices, this contains the correct Jacobian minors automatically.

This is the geometric meaning of many physics integrals:

$$
\int_\gamma A,
\qquad
\int_\Sigma F,
\qquad
\int_M F\wedge F,
\qquad
\int_M \phi^*\omega_N.
$$

A Wilson line uses the pullback of a gauge connection to a curve. A magnetic flux uses the pullback of a two-form field strength to a surface. A theta term integrates a top form over spacetime. A sigma-model topological term often pulls back a form from a target manifold to spacetime.

## Curves, surfaces, and spacetime regions

For a curve $\gamma:[a,b]\to M$ and a one-form $A=A_\mu dx^\mu$,

$$
\int_\gamma A
=
\int_a^b A_\mu(\gamma(t))\frac{d\gamma^\mu}{dt}\,dt.
$$

Reversing the orientation of the curve reverses the sign:

$$
\int_{-\gamma}A=-\int_\gamma A.
$$

For an oriented surface $\Sigma$ parameterized by $(u,v)$ and a two-form

$$
F=\frac12 F_{\mu\nu}dx^\mu\wedge dx^\nu,
$$

the surface integral is

$$
\int_\Sigma F
=
\int du\,dv\,
F_{\mu\nu}(X(u,v))
\frac{\partial X^\mu}{\partial u}
\frac{\partial X^\nu}{\partial v}.
$$

The antisymmetry of $F_{\mu\nu}$ ensures that swapping $u$ and $v$ changes the sign, as an oriented surface integral should.

For a $d$-dimensional spacetime region $M$, a Lagrangian density written geometrically is a top form. In flat coordinates one often writes

$$
S=\int d^d x\,\mathcal L.
$$

On an oriented manifold, this shorthand really means a chosen top form

$$
\mathcal L\,dx^1\wedge\cdots\wedge dx^d
$$

in a coordinate chart, or more invariantly $\mathcal L\operatorname{vol}_g$ if a metric volume form is part of the setup.

## Manifolds with boundary

A manifold with boundary is locally modeled either on $\mathbb R^d$ or on the half-space

$$
\mathbb H^d=\{(x^1,\ldots,x^d)\in\mathbb R^d\mid x^d\ge 0\}.
$$

The boundary $\partial M$ consists of points locally modeled on $x^d=0$. It is a $(d-1)$-dimensional manifold.

If $M$ is oriented, then $\partial M$ receives an induced orientation. The standard convention is **outward normal first**. In words: a basis $(v_1,\ldots,v_{d-1})$ of $T_p\partial M$ is positively oriented if

$$
(n_{\mathrm{out}},v_1,\ldots,v_{d-1})
$$

is a positively oriented basis of $T_pM$, where $n_{\mathrm{out}}$ points outward.

For the interval $[a,b]$, this gives

$$
\partial [a,b]=\{b\}-\{a\}.
$$

Then Stokes’ theorem becomes

$$
\int_a^b df=f(b)-f(a),
$$

the fundamental theorem of calculus.

For a Lorentzian spacetime slab bounded by initial and final Cauchy surfaces, the induced orientation is responsible for the familiar sign difference between final and initial data. This is why symplectic forms and conserved charges often appear as “final minus initial” quantities.

## Stokes’ theorem

Let $W$ be an oriented $p$-dimensional manifold with boundary, and let $\alpha\in\Omega^{p-1}(W)$ be smooth with suitable support. Stokes’ theorem says

$$
\int_W d\alpha=\int_{\partial W}\alpha.
$$

This is the master integration-by-parts identity. It is coordinate-free, metric-independent, and local in the sense that it can be proved in coordinate patches.

Several familiar theorems are special cases:

| Choice of form | Domain | Stokes’ theorem becomes |
|---|---|---|
| $0$-form $f$ | interval $[a,b]$ | fundamental theorem of calculus |
| $1$-form $Pdx+Qdy$ | region in $\mathbb R^2$ | Green’s theorem |
| $1$-form $A$ | surface $\Sigma$ | $\int_\Sigma dA=\int_{\partial\Sigma}A$ |
| $(d-1)$-form $\alpha=\iota_X\operatorname{vol}$ | region in $\mathbb R^d$ | divergence theorem |

For a one-form gauge potential $A$ and field strength $F=dA$ in an abelian theory,

$$
\int_\Sigma F=\int_{\partial\Sigma}A
$$

whenever $A$ is globally defined on $\Sigma$. If $A$ is not globally defined, this formula must be patched carefully; the obstruction is precisely where flux quantization and bundle topology enter.

## Integration by parts for forms

The ordinary integration-by-parts sign is built into Stokes’ theorem. For $\alpha\in\Omega^p(M)$ and $\beta\in\Omega^q(M)$,

$$
d(\alpha\wedge\beta)
=d\alpha\wedge\beta+(-1)^p\alpha\wedge d\beta.
$$

If $p+q=d-1$, Stokes’ theorem gives

$$
\int_M d\alpha\wedge\beta
+(-1)^p\int_M \alpha\wedge d\beta
=
\int_{\partial M}\alpha\wedge\beta.
$$

Thus, when the boundary term vanishes,

$$
\int_M d\alpha\wedge\beta
=(-1)^{p+1}\int_M \alpha\wedge d\beta.
$$

This sign is one of the easiest places to make a mistake. The exterior derivative has degree $+1$, so it picks up signs when moved past a $p$-form.

In variational problems, this is the geometric source of bulk Euler–Lagrange equations plus boundary terms. If the variation produces

$$
\delta L=E\,\delta\phi+d\Theta(\phi,\delta\phi),
$$

then integrating over $M$ gives

$$
\delta S
=
\int_M E\,\delta\phi+
\int_{\partial M}\Theta(\phi,\delta\phi).
$$

The bulk term gives equations of motion. The boundary term determines which boundary conditions make the variational problem well posed and which surface charges must be added.

## Volume forms and metric dependence

A volume form is a nowhere-vanishing top form. On an oriented manifold, a volume form $\mu$ allows one to integrate scalar functions:

$$
\int_M f\,\mu.
$$

A metric $g$ supplies a canonical volume form. In a coordinate chart,

$$
\operatorname{vol}_g=\sqrt{|\det g|}\,dx^1\wedge\cdots\wedge dx^d.
$$

For a Euclidean metric, $\det g>0$. For a Lorentzian metric in mostly-minus convention, $\det g<0$ in four dimensions, so the absolute value keeps the volume density real:

$$
\sqrt{|g|}=\sqrt{|\det g_{\mu\nu}|}.
$$

The volume form depends on both the metric and the orientation. A metric alone gives a positive density; an oriented metric gives a volume form. This distinction is usually suppressed in physics notation, but it matters on nonorientable manifolds and under orientation-reversing transformations.

The Hodge star also depends on the metric and orientation. If $\alpha$ is a $p$-form, then $\star\alpha$ is a $(d-p)$-form, and

$$
\alpha\wedge\star\beta
$$

is a top form that can be integrated. Kinetic terms such as

$$
\frac12\int_M d\phi\wedge\star d\phi,
\qquad
\frac12\int_M F\wedge\star F
$$

therefore require a metric. By contrast, topological terms such as

$$
\int_M F\wedge F
$$

are defined without the Hodge star and do not require a metric, though they still require orientation and global bundle data.

## Densities versus forms

A density is an object that can be integrated without choosing an orientation. In local coordinates, a density looks like

$$
\rho(x)|d^d x|,
$$

and transforms with the absolute value of the Jacobian determinant. A top form transforms with the signed determinant.

This is why $\sqrt{|g|}\,d^d x$ is often called a volume density. On an oriented patch one may identify it with the volume form

$$
\sqrt{|g|}\,dx^1\wedge\cdots\wedge dx^d,
$$

but the identification uses the orientation.

In QFT, the word “density” appears in several related but distinct ways: Lagrangian density, Hamiltonian density, charge density, probability density, path-integral measure density. Not all of these are the same geometric object. A Lagrangian density suitable for integration over spacetime should ultimately define a top form or a density. A charge density on a Cauchy slice should combine with the slice volume element to define a charge.

The safe rule is:

$$
\text{before integrating, identify the top form or density.}
$$

That one sentence prevents a surprising number of fake sign and Jacobian problems.

## Currents and conserved charges

In $d$ spacetime dimensions, a conserved ordinary current is often written as a vector field or one-form $J=J_\mu dx^\mu$. With a metric and Hodge star, it can be represented by a $(d-1)$-form

$$
j=\star J.
$$

Current conservation becomes

$$
dj=0.
$$

If $\Sigma$ is a Cauchy hypersurface, the charge is

$$
Q_\Sigma=\int_\Sigma j.
$$

If $\Sigma_1$ and $\Sigma_2$ are homologous hypersurfaces bounding a region $W$, then

$$
\Sigma_2-\Sigma_1=\partial W.
$$

Using Stokes’ theorem,

$$
Q_{\Sigma_2}-Q_{\Sigma_1}
=
\int_{\partial W}j
=
\int_W dj
=0.
$$

Thus $Q_\Sigma$ is independent of the choice of Cauchy surface, provided no current leaks through other boundaries and no operator insertions or defects act as sources.

This is the form-language version of charge conservation. It also generalizes directly to higher-form symmetries: a conserved $(d-q-1)$-form current integrates over codimension-$(q+1)$ cycles to produce topological charge operators.

## Delta forms and Poincaré duals as a preview

Sometimes one wants to rewrite an integral over a submanifold as an integral over the ambient manifold. Formally, for an oriented submanifold $\Sigma^p\subset M^d$, one introduces a distributional $(d-p)$-form $\delta_\Sigma$ such that

$$
\int_M \omega\wedge\delta_\Sigma
=
\int_\Sigma \omega
$$

for suitable $p$-forms $\omega$. This $\delta_\Sigma$ is a de Rham current, or a distributional representative of the Poincaré dual of $\Sigma$.

This language is extremely useful for defects, branes, Wilson lines, magnetic sources, and anomaly inflow. For example, a point charge in three-dimensional space can be represented by a delta-form source. A domain wall can be represented by a delta-form supported on a hypersurface.

This page will not develop de Rham currents rigorously. The important message for now is that the formula above is not mysterious: it is the distributional extension of the ordinary pairing between forms and integration domains.

## QFT dictionary

| Integral | Geometric type | Typical QFT meaning |
|---|---|---|
| $\int_\gamma A$ | one-form over curve | Wilson line phase in an abelian gauge field, before path ordering in nonabelian theory |
| $\int_\Sigma F$ | two-form over surface | magnetic flux or field-strength flux |
| $\int_M \mathcal L\operatorname{vol}_g$ | scalar times metric volume form | ordinary action on a metric background |
| $\int_M F\wedge\star F$ | top form built using metric | Maxwell or Yang–Mills kinetic term, up to trace and normalization |
| $\int_M F\wedge F$ | top form without metric | theta term or instanton-number density in four dimensions |
| $\int_\Sigma j$ | conserved $(d-1)$-form over hypersurface | conserved charge |
| $\int_M d\Theta$ | exact top form | boundary contribution to action or variation |
| $\int_W H$ with $dH=0$ | closed top-degree pullback | Wess–Zumino or sigma-model topological term, when globally well defined |

The table hides many physical refinements: nonabelian traces, quantization conditions, spin structures, anomalies, boundary degrees of freedom, and regularization. But it correctly displays the underlying geometric types.

## Common pitfalls

**Integrating a scalar without a volume form.** A scalar function is not automatically integrable on a manifold. One must choose a volume form, a density, or a measure.

**Forgetting orientation.** Reversing a curve, surface, spacetime region, or boundary reverses signs. This matters for charges, fluxes, Wilson lines, and boundary terms.

**Confusing $d^d x$ with a coordinate-free object.** The expression $d^d x$ is shorthand. In geometric notation the object is usually $dx^1\wedge\cdots\wedge dx^d$, $\sqrt{|g|}\,dx^1\wedge\cdots\wedge dx^d$, or a density.

**Using Stokes’ theorem when the form is not globally defined.** If a gauge potential $A$ exists only patchwise, the formula $\int_\Sigma dA=\int_{\partial\Sigma}A$ must include transition data. This is exactly where topology enters.

**Dropping boundary terms too quickly.** A boundary term may vanish for compact support, but not for asymptotic boundaries, defects, horizons, interfaces, or finite spatial boxes. In gauge theory and gravity, boundary terms often become charges.

**Ignoring convergence.** Smooth geometry defines the local integral. Noncompact QFT integrals may still diverge in the infrared or ultraviolet and require physical regularization.

**Mixing forms and densities.** Forms require orientation; densities do not. The distinction is easy to miss in coordinates because both may be written with a symbol that looks like $d^d x$.

## Worked example: the line integral of a one-form

Let $M=\mathbb R^2\setminus\{0\}$ and let

$$
A=\frac{-y\,dx+x\,dy}{x^2+y^2}.
$$

On the unit circle parameterized by

$$
\gamma(\theta)=(\cos\theta,\sin\theta),
\qquad
0\le \theta\le 2\pi,
$$

the pullbacks are

$$
\gamma^*dx=-\sin\theta\,d\theta,
\qquad
\gamma^*dy=\cos\theta\,d\theta.
$$

Therefore

$$
\gamma^*A
=
\frac{-\sin\theta(-\sin\theta)+\cos\theta(\cos\theta)}{1}d\theta
=d\theta.
$$

Thus

$$
\int_{S^1}A=\int_0^{2\pi}d\theta=2\pi.
$$

The one-form $A$ is locally $d\theta$, but it is not the exterior derivative of a globally single-valued function on $\mathbb R^2\setminus\{0\}$. This is the simplest model of a closed form with a nonzero period.

## Worked example: Stokes and a boundary term

Let $M=[t_i,t_f]\times\Sigma$ and let $j$ be a closed $(d-1)$-form, $dj=0$. The boundary of $M$ has the orientation

$$
\partial M=\Sigma_{t_f}-\Sigma_{t_i}+[t_i,t_f]\times\partial\Sigma.
$$

If there is no flux through the spatial boundary, then

$$
\int_{[t_i,t_f]\times\partial\Sigma}j=0.
$$

Stokes’ theorem gives

$$
0=\int_M dj=\int_{\partial M}j
=\int_{\Sigma_{t_f}}j-\int_{\Sigma_{t_i}}j.
$$

Hence

$$
Q(t_f)=Q(t_i),
\qquad
Q(t)=\int_{\Sigma_t}j.
$$

This is charge conservation expressed without choosing coordinates on spacetime.

## Exercises

### Exercise 1: Orientation reversal

Let $\gamma:[0,1]\to M$ be an oriented curve and let $A$ be a one-form. Define the reversed curve by

$$
\bar\gamma(t)=\gamma(1-t).
$$

Show that

$$
\int_{\bar\gamma}A=-\int_\gamma A.
$$

<details><summary><strong>Solution</strong></summary>

By pullback,

$$
\int_{\bar\gamma}A
=\int_0^1 A_\mu(\gamma(1-t))\frac{d\gamma^\mu(1-t)}{dt}\,dt.
$$

Since

$$
\frac{d\gamma^\mu(1-t)}{dt}=-\dot\gamma^\mu(1-t),
$$

we get

$$
\int_{\bar\gamma}A
=-\int_0^1 A_\mu(\gamma(1-t))\dot\gamma^\mu(1-t)\,dt.
$$

Let $s=1-t$. Then $dt=-ds$, and the limits change from $t=0,1$ to $s=1,0$. Hence

$$
\int_{\bar\gamma}A
=-\int_0^1 A_\mu(\gamma(s))\dot\gamma^\mu(s)\,ds
=-\int_\gamma A.
$$

</details>

### Exercise 2: Pull back a two-form to a surface

Let

$$
F=dx\wedge dy
$$

on $\mathbb R^3$, and let $\Sigma$ be parameterized by

$$
X(u,v)=(u,v,h(u,v))
$$

with the orientation $du\wedge dv>0$. Compute $X^*F$ and $\int_\Sigma F$ over a domain $D$ in the $(u,v)$ plane.

<details><summary><strong>Solution</strong></summary>

The pullbacks of the coordinate one-forms are

$$
X^*dx=du,
\qquad
X^*dy=dv.
$$

Therefore

$$
X^*F=X^*(dx\wedge dy)=du\wedge dv.
$$

Thus

$$
\int_\Sigma F=\int_D du\,dv.
$$

The answer is the signed projected area onto the $xy$-plane. The height function $h(u,v)$ does not enter because $F=dx\wedge dy$ measures the $xy$-oriented flux component.

</details>

### Exercise 3: Stokes on an annulus

Let $A=f(r)d\theta$ on the annulus

$$
R_1\le r\le R_2
$$

in the plane, with the standard orientation $dr\wedge d\theta$. Compute both sides of

$$
\int_W dA=\int_{\partial W}A.
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
dA=f'(r)dr\wedge d\theta.
$$

Therefore

$$
\int_W dA
=\int_{R_1}^{R_2}dr\int_0^{2\pi}d\theta\,f'(r)
=2\pi\bigl(f(R_2)-f(R_1)\bigr).
$$

The boundary has two circles. The outer boundary has orientation $d\theta>0$, while the inner boundary has the opposite orientation because of the outward-normal-first convention. Thus

$$
\int_{\partial W}A
=\int_{r=R_2}f(R_2)d\theta-
\int_{r=R_1}f(R_1)d\theta
=2\pi\bigl(f(R_2)-f(R_1)\bigr).
$$

The two sides agree.

</details>

### Exercise 4: Charge conservation from a closed current form

Let $j$ be a closed $(d-1)$-form on a spacetime region $W$ whose boundary is

$$
\partial W=\Sigma_2-\Sigma_1+B.
$$

Assume $\int_B j=0$. Show that

$$
\int_{\Sigma_2}j=\int_{\Sigma_1}j.
$$

<details><summary><strong>Solution</strong></summary>

Since $dj=0$, Stokes’ theorem gives

$$
0=\int_W dj=\int_{\partial W}j.
$$

Using the boundary decomposition,

$$
\int_{\partial W}j
=\int_{\Sigma_2}j-\int_{\Sigma_1}j+\int_B j.
$$

The assumption $\int_B j=0$ gives

$$
0=\int_{\Sigma_2}j-\int_{\Sigma_1}j,
$$

so the charge is independent of the hypersurface:

$$
\int_{\Sigma_2}j=\int_{\Sigma_1}j.
$$

</details>

### Exercise 5: Metric volume under a coordinate change

Let $g_{ij}$ be a Riemannian metric on a two-dimensional coordinate patch with coordinates $x^1,x^2$. Under a coordinate change $y=y(x)$, show that

$$
\sqrt{\det g_y}\,dy^1\wedge dy^2
=
\sqrt{\det g_x}\,dx^1\wedge dx^2
$$

for orientation-preserving changes of coordinates.

<details><summary><strong>Solution</strong></summary>

Let

$$
J^a{}_i=\frac{\partial y^a}{\partial x^i},
\qquad
K^i{}_a=\frac{\partial x^i}{\partial y^a}=J^{-1}{}^i{}_a.
$$

Metric components transform as

$$
(g_y)_{ab}=K^i{}_aK^j{}_b(g_x)_{ij}.
$$

Therefore

$$
\det g_y=(\det K)^2\det g_x.
$$

Taking the square root gives

$$
\sqrt{\det g_y}=|\det K|\sqrt{\det g_x}.
$$

For an orientation-preserving coordinate change, $\det J>0$, so $|\det K|=1/\det J$. Meanwhile

$$
dy^1\wedge dy^2=(\det J)dx^1\wedge dx^2.
$$

Multiplying,

$$
\sqrt{\det g_y}\,dy^1\wedge dy^2
=
\sqrt{\det g_x}\,dx^1\wedge dx^2.
$$

</details>

## Relations to other pages

[Differential Forms](/math-toolkit/geometry-of-fields/differential-forms/) defines the objects integrated here. [Manifolds](/math-toolkit/geometry-of-fields/manifolds/) explains charts, tangent spaces, submanifolds, and boundaries. [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) explains why boundary terms from Stokes’ theorem are essential in variational problems.

The next page, [Lie Derivatives](/math-toolkit/geometry-of-fields/lie-derivatives/), uses flows to describe infinitesimal changes of functions, forms, tensor fields, and geometric background data.

## Research status

For smooth finite-dimensional manifolds, the material on orientation, pullbacks, densities, and Stokes’ theorem is settled. In QFT, the interesting complications usually come from objects outside this smooth compact setting: noncompact spacetime, asymptotic boundaries, singular fields, defects, distributional sources, gauge fields defined only patchwise, anomalous transformations, and infinite-dimensional field spaces.

The safest habit is to separate the geometric identity from the physical assumptions. Stokes’ theorem is exact for the correct geometric objects. Whether a boundary term vanishes, a potential is globally defined, or an integral is finite is a separate physical and analytic question.

## References

- M. Nakahara, *Geometry, Topology and Physics*. Useful for manifolds, forms, integration, Stokes’ theorem, de Rham cohomology, monopoles, instantons, and gauge theory.
- T. Frankel, *The Geometry of Physics*. Especially useful for geometric intuition about line integrals, surface integrals, Stokes’ theorem, forms versus vector calculus, and physical applications.
- R. Bott and L. W. Tu, *Differential Forms in Algebraic Topology*. A standard reference for forms, integration, Stokes’ theorem, partitions of unity, de Rham cohomology, and Poincaré duality.
- J. M. Lee, *Introduction to Smooth Manifolds*. A careful mathematical reference for smooth manifolds, orientations, integration of forms, and manifolds with boundary.
- B. Schutz, *Geometrical Methods of Mathematical Physics*. A compact physics-friendly source for differential forms and integration.
- A. M. Polyakov, *Gauge Fields and Strings*. Useful for seeing form integrals, topological terms, Wilson loops, instantons, and geometric reasoning inside QFT.

## Version history

- **2026-06-25:** Initial polished draft. Added orientation, pullback integration, submanifold integrals, Stokes’ theorem, boundary orientation, densities, metric volume forms, charge conservation, QFT dictionary, worked examples, and exercises.
