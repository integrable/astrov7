---
title: "Painlevé Equations"
description: "Explains Painlevé equations for QFT and mathematical physics: movable singularities, the six canonical equations, confluence, Hamiltonian and tau-function forms, isomonodromy, monodromy data, matrix models, Ising correlators, integrable QFT, and CFT/gauge-theory applications."
sidebar:
  label: "Painlevé Equations"
  order: 9
level: Advanced
status: "Polished draft"
source: "Standard references on Painlevé equations, nonlinear special functions, movable singularities, isomonodromic deformations, tau functions, random matrices, integrable QFT, Ising correlators, and CFT/gauge-theory correspondences, including Painlevé, Gambier, Ince, Okamoto, Jimbo–Miwa–Ueno, Fokas–Its–Kapaev–Novokshenov, Forrester–Witte, Tracy–Widom, McCoy–Wu, Palmer, Its–Izergin–Korepin–Slavnov, Iorgov–Lisovyy–Teschner, Gamayun–Iorgov–Lisovyy, Gavrylenko–Lisovyy, Bonelli–Lisovyy–Maruyoshi–Sciarappa–Tanzini, NIST DLMF, and modern literature on isomonodromy, exact WKB, Fredholm determinants, topological strings, and Seiberg–Witten theory."
topics:
  - Painleve equation
  - Painleve property
  - movable singularity
  - nonlinear ordinary differential equation
  - isomonodromy
  - tau function
  - monodromy data
  - confluence
  - random matrix theory
  - integrable QFT
  - Ising model
  - Fredholm determinant
canonicalTopics:
  - painleve-equation
  - painleve-property
  - movable-singularity
  - nonlinear-ordinary-differential-equation
  - isomonodromy
  - tau-function
  - monodromy-data
  - confluence
  - random-matrix-theory
  - integrable-qft
  - ising-model
  - fredholm-determinant
researchStatus:
  established:
    - "The six Painlevé equations are canonical nonlinear second-order ODEs with the Painlevé property: movable singularities of their solutions are poles rather than branch points or essential singularities."
    - "Painlevé equations arise as isomonodromic deformation equations for auxiliary linear systems; their tau functions encode Hamiltonians, Fredholm determinants, and exact correlation functions in many integrable problems."
  active:
    - "Connections among Painlevé tau functions, conformal blocks, resurgence, exact WKB, Fredholm determinants, random matrices, topological strings, and four-dimensional supersymmetric gauge theories remain active research areas."
---

## Summary

Painlevé equations are nonlinear special functions. They play for certain nonlinear ODEs the role that Bessel, hypergeometric, and Heun functions play for linear ODEs. The point is not that their solutions are elementary. They usually are not. The point is that the equations are rigid enough to have a controlled singularity theory, monodromy interpretation, tau functions, and deep appearances in exact QFT.

The basic organizing principle is the **Painlevé property**:

> the only movable singularities of the solution are poles.

A singularity is **movable** if its location depends on the initial conditions. Fixed singularities are built into the equation. Movable branch points are usually a sign that a nonlinear ODE has chaotic analytic continuation. Painlevé equations avoid that disaster. They are nonlinear, but not feral.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing nonlinear ODEs with the Painlevé property, the six Painlevé families, auxiliary linear systems, isomonodromy, tau functions, and QFT applications.](/figures/math-toolkit/painleve-isomonodromy-flow.svg)

<figcaption>

Painlevé equations can be read from two complementary directions. As nonlinear ODEs, they are the canonical second-order equations whose movable singularities are only poles. As isomonodromic deformation equations, they arise from linear systems whose singularities move while monodromy data remain fixed. Their tau functions package exact correlators, Fredholm determinants, matrix-model scaling limits, and CFT/gauge-theory monodromy data.

</figcaption>
</figure>

In QFT, Painlevé equations appear when a problem is exact enough to be rigid but too nonlinear to reduce to classical special functions. Examples include scaling correlators in the two-dimensional Ising model, gap probabilities and Fredholm determinants in random matrix theory, integrable QFT form-factor sums, double-scaling limits of matrix models, and isomonodromic descriptions of conformal blocks and supersymmetric gauge theory.

## Prerequisites and conventions

You should know [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Saddle Points](/math-toolkit/complex-analysis/saddle-points/), [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/), [Heun Equations](/math-toolkit/special-functions-exact-equations/heun-equations/), and [Modular Forms](/math-toolkit/special-functions-exact-equations/modular-forms/).

There are many normalizations of the Painlevé equations. This page uses a standard common normalization for the six equations. When comparing to a paper, expect rescalings of the independent variable, dependent variable, and parameters. Painlevé equations are sturdy; their notation is made of wet cardboard.

## Movable singularities

Consider a first-order ODE

$$
{dy\over dx}=y^2.
$$

Its solution is

$$
y(x)=-{1\over x-x_0},
$$

where $x_0$ depends on the initial condition. Thus $x_0$ is a movable singularity. It is a pole, so it is allowed by the Painlevé property.

Now consider

$$
{dy\over dx}=y^3.
$$

A solution is

$$
y(x)=\pm {1\over\sqrt{-2(x-x_0)}}.
$$

The singularity at $x_0$ is movable and branch-like. Analytic continuation around $x_0$ changes the branch of the solution. This violates the Painlevé property.

For nonlinear equations, the Painlevé property is a strong global analytic constraint. It says that the multivaluedness of solutions is controlled by fixed singularities of the equation, not by arbitrary movable branch points generated by initial data.

## The six Painlevé equations

The six canonical Painlevé equations are usually denoted

$$
P_{\rm I},P_{\rm II},P_{\rm III},P_{\rm IV},P_{\rm V},P_{\rm VI}.
$$

They form a hierarchy related by confluence: singular points of an associated linear system collide, and regular singularities turn into irregular singularities. The most general case is $P_{\rm VI}$; the simpler-looking equations are often limits of it.

### First Painlevé equation

The first Painlevé equation is

$$
P_{\rm I}:\qquad
y''=6y^2+x.
$$

It has no free parameter in this normalization. It appears in double-scaling limits of matrix models and in the local description of certain critical phenomena. It is also the classic example where a deceptively small nonlinear equation contains a very nontrivial global analytic story.

### Second Painlevé equation

The second Painlevé equation is

$$
P_{\rm II}:\qquad
y''=2y^3+xy+\alpha.
$$

It appears in edge-scaling limits of random matrix theory, in Tracy–Widom distributions, in certain integrable kernels, and in exact asymptotic problems. Special values of $\alpha$ admit solutions related to Airy functions or rational functions, but the generic solution is a genuine Painlevé transcendent.

### Third Painlevé equation

One common form of the third Painlevé equation is

$$
P_{\rm III}:\qquad
y''={y'^2\over y}-{y'\over x}+{\alpha y^2+\beta\over x}+\gamma y^3+{\delta\over y}.
$$

The family has important degenerations, often denoted by types such as $P_{\rm III}(D_6)$, $P_{\rm III}(D_7)$, and $P_{\rm III}(D_8)$ in the isomonodromy literature. In physics, $P_{\rm III}$ and its sigma forms occur in scaling limits of the two-dimensional Ising model and in integrable QFT correlation functions.

### Fourth Painlevé equation

A common normalization of the fourth Painlevé equation is

$$
P_{\rm IV}:\qquad
y''={y'^2\over2y}+{3\over2}y^3+4xy^2+2(x^2-\alpha)y+{\beta\over y}.
$$

It appears in special function limits, random matrix ensembles, and problems with parabolic-cylinder or harmonic-oscillator ancestry.

### Fifth Painlevé equation

A common form of the fifth Painlevé equation is

$$
P_{\rm V}:\qquad
y''=\left({1\over2y}+{1\over y-1}\right)y'^2-{y'\over x}
+{(y-1)^2\over x^2}\left(\alpha y+{\beta\over y}\right)
+{\gamma y\over x}+{\delta y(y+1)\over y-1}.
$$

It appears in confluence limits of $P_{\rm VI}$, in Fredholm determinant problems, in finite-size scaling functions, and in monodromy problems with one fewer regular singularity but more irregular data.

### Sixth Painlevé equation

The sixth Painlevé equation is the most general member of the family. One standard form is

$$
\begin{aligned}
P_{\rm VI}:\qquad
y''={1\over2}\left({1\over y}+{1\over y-1}+{1\over y-x}\right)y'^2
&-\left({1\over x}+{1\over x-1}+{1\over y-x}\right)y'\\
&+{y(y-1)(y-x)\over x^2(x-1)^2}
\left[\alpha+{\beta x\over y^2}+{\gamma(x-1)\over (y-1)^2}+{\delta x(x-1)\over (y-x)^2}\right].
\end{aligned}
$$

It is tied to isomonodromic deformations of a rank-two Fuchsian system on the four-punctured sphere. The independent variable $x$ is the moving puncture or cross-ratio. This is why $P_{\rm VI}$ sits so close to Heun equations, conformal blocks, four-point functions, and monodromy methods.

## Why poles appear

The Painlevé property is not magic; it can be glimpsed by dominant balance. For $P_{\rm I}$, suppose a movable singularity occurs at $x=x_0$ and try

$$
y\sim a(x-x_0)^p.
$$

The dominant terms in

$$
y''=6y^2+x
$$

are $y''$ and $6y^2$. Balancing powers gives

$$
p-2=2p,
\qquad
p=-2.
$$

Balancing coefficients gives

$$
a p(p-1)=6a^2.
$$

With $p=-2$,

$$
6a=6a^2,
$$

so $a=1$ for a nonzero pole. Thus the local leading behavior is

$$
y\sim {1\over(x-x_0)^2}.
$$

This does not prove the full Painlevé property, but it shows the local mechanism: the dominant nonlinear balance wants poles rather than branch points.

## Hamiltonian forms and tau functions

Painlevé equations often admit Hamiltonian formulations. Schematically, one introduces canonical variables $q(t),p(t)$ and a Hamiltonian $H(q,p,t)$ such that

$$
{dq\over dt}={\partial H\over\partial p},
\qquad
{dp\over dt}=-{\partial H\over\partial q}.
$$

Eliminating $p$ gives a Painlevé equation for $q(t)$. The associated tau function is defined, up to normalization and convention-dependent shifts, by

$$
{d\over dt}\log\tau(t)=H(t).
$$

In isomonodromy, $\tau$ is more fundamental than any single solution $y(t)$. It is the object that often equals a Fredholm determinant, a correlation function, a matrix-model partition function, or a conformal-block expansion after choosing monodromy data.

This is the same recurring QFT pattern as before:

$$
\text{differential equation for fields}
\quad\longrightarrow\quad
\text{generating functional or determinant}.
$$

Painlevé tau functions are nonlinear cousins of spectral determinants.

## Isomonodromy in one page

Painlevé equations become much less mysterious when viewed as compatibility conditions of linear systems. Consider an auxiliary wavefunction $\Psi(z;x)$ obeying

$$
\partial_z\Psi=A(z;x)\Psi,
$$

and

$$
\partial_x\Psi=B(z;x)\Psi.
$$

Compatibility requires

$$
\partial_x A-\partial_z B+[A,B]=0.
$$

If $A(z;x)$ has singularities in the $z$-plane, analytic continuation of $\Psi$ around those singularities defines monodromy data. An isomonodromic deformation moves the singularities while preserving the monodromy data. The nonlinear deformation equations for the singularity positions and residues are Painlevé equations or their higher-dimensional generalizations.

For $P_{\rm VI}$, the standard picture is a rank-two Fuchsian system with singularities at

$$
z=0,
\qquad
z=1,
\qquad
z=x,
\qquad
z=\infty.
$$

Moving $x$ while preserving monodromy gives $P_{\rm VI}$. When singularities collide, confluence produces lower Painlevé equations and irregular singularities. Ordinary monodromy data are then supplemented or replaced by Stokes data.

## Relationship with hypergeometric and Heun equations

Hypergeometric and Heun equations are linear second-order ODEs. Painlevé equations are nonlinear second-order ODEs. The bridge is monodromy.

The hypergeometric equation is the canonical linear equation with three regular singular points. Its monodromy is rigid: local exponent data almost fix the global monodromy. The Heun equation has four regular singular points and an accessory parameter. Its monodromy is no longer fixed by local exponent data.

Painlevé VI appears when the four-point Heun-type monodromy problem is allowed to deform while preserving monodromy. Roughly:

$$
\text{four regular singular points}
\quad\Longrightarrow\quad
\text{Heun accessory parameter},
$$

while

$$
\text{moving one singular point with monodromy fixed}
\quad\Longrightarrow\quad
P_{\rm VI}.
$$

That is why Painlevé VI, Heun equations, four-point conformal blocks, and accessory parameters constantly bump into each other in mathematical physics. Same party, different entrances.

## QFT appearances

### Two-dimensional Ising model

The two-dimensional Ising model is one of the great laboratories for Painlevé equations. Certain spin–spin correlation functions and their scaling limits can be expressed through Painlevé equations or associated sigma forms. On the lattice, one encounters $P_{\rm VI}$-type structures; in scaling limits, $P_{\rm III}$ appears prominently.

The conceptual lesson is simple: exact solvability plus nontrivial scaling does not always lead to elementary functions. It can lead to nonlinear special functions.

### Integrable QFT

In integrable QFT, form-factor expansions, Fredholm determinants, and correlation functions often satisfy nonlinear differential equations. Painlevé equations appear when the integrable structure is strong enough to close the hierarchy into a finite nonlinear ODE.

This is especially common in two dimensions, where factorized scattering, Riemann–Hilbert methods, and isomonodromy are unusually powerful.

### Random matrices and Fredholm determinants

Gap probabilities in random matrix theory can often be written as Fredholm determinants

$$
D(s)=\det(1-K_s),
$$

where $K_s$ is an integral operator on an interval depending on a parameter $s$. Logarithmic derivatives of $D(s)$ satisfy Painlevé equations or Painlevé sigma forms. The Tracy–Widom distributions at spectral edges are tied to $P_{\rm II}$.

This matters for QFT because random matrix and Fredholm determinant structures also appear in matrix models, double-scaling limits, topological strings, entanglement spectra, and integrable kernels.

### Matrix models and double scaling

Matrix models near critical points often produce Painlevé equations after double scaling. The classic pure two-dimensional gravity limit is governed by $P_{\rm I}$ in an appropriate normalization. Higher multicritical points produce related hierarchies.

Here Painlevé equations are not just special functions. They are continuum string equations controlling nonperturbative completions and large-order behavior.

### Conformal blocks and gauge theory

Modern isomonodromy reveals a close relationship between Painlevé tau functions and conformal blocks. In one famous case, $P_{\rm VI}$ tau functions can be expanded in terms of $c=1$ Virasoro conformal blocks with coefficients determined by monodromy data. Through gauge/CFT correspondences, similar structures appear in four-dimensional supersymmetric gauge theory, Seiberg–Witten periods, and Nekrasov partition functions.

The safe takeaway is not that every conformal block is a Painlevé tau function. The safe takeaway is that monodromy-preserving deformations provide a bridge among linear ODEs, conformal blocks, gauge-theory partition functions, and nonlinear special functions.

## Sigma forms

Many physical applications do not use $y(x)$ directly. They use a sigma function, often a logarithmic derivative of the tau function. Schematically,

$$
\sigma(x)=x{d\over dx}\log\tau(x)+\text{known shifts}.
$$

The function $\sigma(x)$ satisfies a second-order, second-degree equation called a Painlevé sigma form. These forms are often better adapted to determinants, correlation functions, and boundary conditions.

This is why a paper may say "the correlator satisfies Painlevé III" but then display an equation that does not look exactly like $P_{\rm III}$. It may be using a Hamiltonian or sigma form. Same beast, different antlers.

## Asymptotics and Stokes data

Painlevé transcendents are usually specified not by elementary formulae but by monodromy or asymptotic data. For example, one may specify behavior as $x\to\infty$ along a ray in the complex plane. Different rays may be related by Stokes phenomena.

This is where Painlevé theory meets resurgence and exact WKB. In lower Painlevé equations, irregular singularities appear naturally, and Stokes data become part of the monodromy package. The equation is nonlinear, but its analytic continuation is still organized by linear-system data.

## Common pitfalls

### Calling every nonlinear ODE Painlevé

Most nonlinear ODEs are not Painlevé equations. Painlevé equations are special because of the movable-singularity constraint and the isomonodromy structure.

### Confusing the equation with one solution

A Painlevé equation is a family of solutions labeled by initial or monodromy data. Special solutions may reduce to Airy, Bessel, rational, algebraic, or classical functions, but the generic solution does not.

### Ignoring normalizations

The same Painlevé equation may appear with rescaled variables and shifted parameters. Before comparing formulas, identify the normalization of $x$, $y$, and the parameters.

### Missing sigma and tau forms

Physics papers often use tau functions or sigma functions rather than the canonical dependent variable $y(x)$. If the displayed equation looks unfamiliar, check whether it is a Hamiltonian or logarithmic-derivative form.

### Thinking isomonodromy means monodromy is trivial

Isomonodromy means monodromy data are preserved as a deformation parameter changes. It does not mean the monodromy matrices are identity. Nontrivial monodromy is the whole point.

## Exercises

### Exercise 1: Movable pole versus movable branch point

Solve the two first-order equations

$$
{dy\over dx}=y^2
$$

and

$$
{dy\over dx}=y^3.
$$

Identify the movable singularities and decide which equation has movable branch points.

<details><summary><strong>Solution</strong></summary>

For

$$
{dy\over dx}=y^2,
$$

separate variables:

$$
{dy\over y^2}=dx.
$$

Then

$$
-{1\over y}=x+C,
$$

so

$$
y=-{1\over x-x_0}.
$$

The singularity at $x=x_0$ depends on the integration constant, so it is movable. It is a pole.

For

$$
{dy\over dx}=y^3,
$$

separation gives

$$
{dy\over y^3}=dx,
$$

so

$$
-{1\over2y^2}=x+C.
$$

Thus

$$
y=\pm {1\over\sqrt{-2(x-x_0)}}.
$$

The singularity $x=x_0$ is movable and branch-like. Analytic continuation around it changes the sign of the square root. Therefore this equation has movable branch points.

</details>

### Exercise 2: Dominant balance for first Painlevé

For

$$
y''=6y^2+x,
$$

assume a local singular behavior

$$
y\sim a(x-x_0)^p.
$$

Find $p$ and $a$ for a nonzero dominant balance.

<details><summary><strong>Solution</strong></summary>

Near $x=x_0$, the term $x$ is less singular than $y''$ and $y^2$ if $p<0$. The dominant balance is

$$
y''\sim 6y^2.
$$

Substitute

$$
y\sim a(x-x_0)^p.
$$

Then

$$
y''\sim a p(p-1)(x-x_0)^{p-2},
$$

and

$$
6y^2\sim 6a^2(x-x_0)^{2p}.
$$

Matching powers gives

$$
p-2=2p,
\qquad p=-2.
$$

Matching coefficients gives

$$
a(-2)(-3)=6a^2,
$$

so

$$
6a=6a^2.
$$

For a nonzero singular balance, $a=1$. Thus

$$
y\sim {1\over(x-x_0)^2}.
$$

</details>

### Exercise 3: Compatibility of an auxiliary linear system

Suppose

$$
\partial_z\Psi=A(z,x)\Psi,
\qquad
\partial_x\Psi=B(z,x)\Psi.
$$

Show that equality of mixed derivatives implies

$$
\partial_x A-\partial_z B+[A,B]=0.
$$

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_x\partial_z\Psi
=\partial_x(A\Psi)
=(\partial_x A)\Psi+A\partial_x\Psi
=(\partial_x A)\Psi+AB\Psi.
$$

Similarly,

$$
\partial_z\partial_x\Psi
=\partial_z(B\Psi)
=(\partial_z B)\Psi+B\partial_z\Psi
=(\partial_z B)\Psi+BA\Psi.
$$

Equality of mixed derivatives gives

$$
\left(\partial_x A-\partial_z B+AB-BA\right)\Psi=0.
$$

For a fundamental matrix solution $\Psi$, this implies

$$
\partial_x A-\partial_z B+[A,B]=0.
$$

</details>

### Exercise 4: Why PVI is tied to a cross-ratio

A rank-two Fuchsian system for $P_{\rm VI}$ has singular points at

$$
0,
\qquad 1,
\qquad x,
\qquad \infty.
$$

Explain why $x$ is naturally a cross-ratio parameter.

<details><summary><strong>Solution</strong></summary>

Four marked points on the Riemann sphere are not all removable by a Möbius transformation. A Möbius transformation has enough freedom to send three distinct points to

$$
0,
\qquad 1,
\qquad \infty.
$$

The position of the fourth point is then invariant data. This remaining coordinate is the cross-ratio, conventionally denoted $x$ after fixing the other three points to $0$, $1$, and $\infty$.

Thus a four-punctured sphere has one complex modulus, and $P_{\rm VI}$ describes an isomonodromic deformation as that modulus changes.

</details>

## Related pages

For the linear equations closest to Painlevé VI, see [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/) and [Heun Equations](/math-toolkit/special-functions-exact-equations/heun-equations/). For monodromy, analytic continuation, and surfaces, see [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), and [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/). For exact determinants, see [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/). For torus and conformal-block structures nearby, see [Modular Forms](/math-toolkit/special-functions-exact-equations/modular-forms/).

## References and further reading

For classical Painlevé theory, see Ince, Okamoto, and the NIST Digital Library of Mathematical Functions. For isomonodromy and tau functions, see Jimbo, Miwa, Ueno, Fokas, Its, Kapaev, Novokshenov, and modern reviews on Riemann–Hilbert methods. For Ising-model and integrable-QFT appearances, see McCoy and Wu, Palmer, and the literature on form factors, Fredholm determinants, and integrable kernels. For random matrices and distributions, see Tracy and Widom, Forrester and Witte, and related work on Painlevé sigma forms. For the CFT and gauge-theory interface, see work by Gamayun, Iorgov, Lisovyy, Teschner, Gavrylenko, Bonelli, Maruyoshi, Sciarappa, Tanzini, and collaborators on Painlevé tau functions, conformal blocks, and supersymmetric gauge theory.

## Version history

- **2026-06-26:** Initial polished draft. Added movable singularities, the Painlevé property, the six canonical equations, local pole balance, Hamiltonian and tau-function language, isomonodromy, relation to hypergeometric and Heun equations, QFT applications, sigma forms, asymptotics and Stokes data, common pitfalls, exercises with solutions, and TikZ/SVG figure.
