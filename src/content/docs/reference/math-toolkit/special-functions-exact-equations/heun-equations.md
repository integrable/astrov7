---
title: "Heun Equations"
description: "Explains Heun equations for QFT and mathematical physics: four regular singular points, the accessory parameter, local series, monodromy, confluence limits, Heun polynomials, and why many exact spectral problems go beyond hypergeometric functions."
sidebar:
  label: "Heun Equations"
  order: 5
level: Advanced
status: "Polished draft"
source: "Standard references on Heun equations, Fuchsian differential equations, monodromy, special functions, black-hole perturbations, spheroidal functions, isomonodromy, Painleve equations, and exact spectral problems, including Heun, Ince, Ronveaux, Slavyanov–Lay, Maier, NIST DLMF, Olver, Whittaker–Watson, Bender–Orszag, Fiziev, Iorgov–Lisovyy–Teschner, and modern mathematical-physics literature on Seiberg–Witten theory, AGT, and monodromy methods."
topics:
  - Heun equation
  - Fuchsian differential equation
  - regular singular point
  - accessory parameter
  - monodromy
  - confluent Heun equation
  - Heun polynomial
  - spheroidal equation
  - black-hole perturbation theory
  - isomonodromy
canonicalTopics:
  - heun-equation
  - fuchsian-differential-equation
  - regular-singular-point
  - accessory-parameter
  - monodromy
  - confluent-heun-equation
  - heun-polynomial
  - spheroidal-equation
  - black-hole-perturbation-theory
  - isomonodromy
researchStatus:
  established:
    - "The general Heun equation is the canonical second-order Fuchsian equation with four regular singular points and one accessory parameter not fixed by local exponent data."
    - "Its local Frobenius solutions, three-term recurrences, confluence limits, polynomial truncation conditions, and monodromy interpretation are standard, though normalizations differ across references."
  active:
    - "Heun equations remain active in mathematical physics because exact connection formulae, spectral conditions, black-hole quasi-normal modes, isomonodromic tau functions, and gauge-theory correspondences often require nontrivial monodromy or numerical analysis rather than closed elementary formulae."
---

## Summary

The Heun equation is what appears when the hypergeometric equation is almost enough, but one more singular point refuses to go away.

The Gauss hypergeometric equation is the canonical second-order equation with three regular singular points. The general Heun equation is the canonical second-order equation with four regular singular points, conventionally placed at

$$
z=0,\qquad z=1,\qquad z=a,\qquad z=\infty.
$$

A common standard form is

$$
y''+\left(\frac{\gamma}{z}+\frac{\delta}{z-1}+\frac{\epsilon}{z-a}\right)y'
+\frac{\alpha\beta z-q}{z(z-1)(z-a)}y=0,
$$

with the Fuchs relation

$$
\alpha+\beta+1=\gamma+\delta+\epsilon.
$$

The parameter $q$ is the accessory parameter. It does not change the local exponent differences at the four singular points, but it changes the global monodromy and therefore changes the spectral problem. That little $q$ is where a lot of exact solvability goes to hide.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing the Heun equation as the four-regular-singularity extension of the hypergeometric equation, with the accessory parameter, monodromy problem, confluence hierarchy, and QFT applications.](/figures/math-toolkit/heun-singularity-confluence-map.svg)

<figcaption>

The Heun equation is the next Fuchsian step after the hypergeometric equation. Adding a fourth regular singular point introduces an accessory parameter $q$, which controls global monodromy without being fixed by local exponents. Confluent limits merge singular points and produce equations used in black-hole perturbation theory, spheroidal waves, semiclassical spectral problems, and isomonodromy.

</figcaption>
</figure>

Heun functions are not as friendly as ${}_2F_1$. There is no comparably compact universal Euler integral, no small finite set of transformations that solves the global connection problem, and no universal closed-form spectral condition. But precisely for that reason, they are important: they mark the boundary between classical hypergeometric solvability and the modern world of monodromy, accessory parameters, numerical spectra, and isomonodromic deformation.

## Prerequisites

You should know [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/), [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), [Green Functions](/math-toolkit/differential-equations-green-functions/green-functions/), [Schrödinger Operators](/math-toolkit/differential-equations-green-functions/schrodinger-operators/), [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), and [Saddle Points](/math-toolkit/complex-analysis/saddle-points/).

This page uses the standard local form of the general Heun equation. Literature conventions vary: some authors use $Q$ instead of $q$, some move the singular points by a Möbius transformation, and some absorb signs into the numerator. Always check the normal form before comparing parameters.

## The regular singularity viewpoint

A second-order linear ODE

$$
y''+p(z)y'+r(z)y=0
$$

has a regular singular point at $z=z_0$ if

$$
(z-z_0)p(z),\qquad (z-z_0)^2r(z)
$$

are analytic at $z_0$. Near a regular singular point, the Frobenius method gives local solutions of the form

$$
y(z)=(z-z_0)^s\sum_{n=0}^\infty c_n(z-z_0)^n,
\qquad c_0\ne0.
$$

The allowed exponents $s$ are the roots of an indicial equation. If the exponent difference is an integer, logarithms may appear.

For the general Heun equation,

$$
y''+\left(\frac{\gamma}{z}+\frac{\delta}{z-1}+\frac{\epsilon}{z-a}\right)y'
+\frac{\alpha\beta z-q}{z(z-1)(z-a)}y=0,
$$

one obtains local exponents

$$
\begin{array}{c|cccc}
&0&1&a&\infty\\
\hline
\text{exponents}&0&0&0&\alpha\\
&1-\gamma&1-\delta&1-\epsilon&\beta
\end{array}
$$

with

$$
\alpha+\beta+1=\gamma+\delta+\epsilon.
$$

Compare this with the hypergeometric equation. With three singular points, the exponent data essentially determine the equation up to equivalence. With four singular points, they do not. The leftover freedom is the accessory parameter $q$.

## What the accessory parameter does

The local exponents tell you the eigenvalues of monodromy matrices around each singular point, but not the full global representation of the fundamental group. For the four-punctured sphere, there is genuine moduli: loops around different singular points can be glued together in inequivalent ways while preserving the same local exponent differences.

That global freedom is encoded by $q$. In physics terms, $q$ often becomes an eigenvalue or a separation constant. Boundary conditions at two different singular points then quantize $q$.

This is why Heun equations appear in spectral problems. A local regularity condition near $z=0$ determines a local solution. A second condition, such as regularity at $z=1$, normalizability at infinity, or ingoing behavior at a horizon, is generally satisfied only for special values of $q$ or of another parameter such as frequency.

The accessory parameter is the mathematical source of the spectral equation.

## Local series and the three-term recurrence

A local Heun function around $z=0$ is usually denoted

$$
\operatorname{Hl}(a,q;\alpha,\beta,\gamma,\delta;z),
$$

with normalization

$$
\operatorname{Hl}(a,q;\alpha,\beta,\gamma,\delta;0)=1,
$$

and with

$$
\epsilon=\alpha+\beta+1-\gamma-\delta.
$$

Write

$$
y(z)=\sum_{n=0}^\infty c_n z^n,
\qquad c_0=1.
$$

Substituting into the equation gives a three-term recurrence of the form

$$
A_n c_{n+1}+B_n c_n+C_n c_{n-1}=0,
\qquad n\ge0,
$$

with $c_{-1}=0$. One convenient convention is

$$
a(n+1)(n+\gamma)c_{n+1}
-\Big[n\big((n+\gamma+\delta-1)a+n+\gamma+\epsilon-1\big)+q\Big]c_n
+(n+\alpha-1)(n+\beta-1)c_{n-1}=0.
$$

Check signs before using this recurrence with another reference. The recurrence is tied to the precise normal form and to whether the numerator is written as $\alpha\beta z-q$ or $q-\alpha\beta z$.

The important conceptual point is the three-term nature of the recurrence. Hypergeometric coefficients have a simple two-term ratio. Heun coefficients generally do not. This is one reason Heun functions are harder: the coefficients are not controlled by a single rational ratio.

## Hypergeometric as the rigid case

The hypergeometric equation has three regular singular points. The Heun equation has four. If one singular point is removed or made apparent in a special way, Heun solutions can reduce to hypergeometric functions.

A singular point is called apparent if local solutions have no actual branch monodromy there, even though the coefficients of the equation are singular. Apparent singularities are subtle: they can be present in the differential equation but invisible in the multivaluedness of solutions.

Special parameter choices can make a Heun equation reducible to hypergeometric functions, but this is not generic. In practice, whenever a derivation produces a Heun equation, one should not expect a hidden ${}_2F_1$ answer unless a symmetry or truncation explains it.

That is the “almost but not quite” feeling students often get: the equation looks only mildly more complicated than hypergeometric, but the global theory is qualitatively richer.

## Confluent Heun equations

Confluence means merging singular points while scaling parameters so that a meaningful limit remains. When regular singularities collide, one typically obtains irregular singularities.

The hierarchy is commonly summarized as

$$
\text{general Heun}
\longrightarrow
\text{confluent Heun}
\longrightarrow
\text{double-confluent, biconfluent, triconfluent variants}.
$$

Different confluence patterns give different normal forms. The confluent Heun equation appears when two regular singular points merge, leaving two regular singularities and one irregular singularity. More severe confluences produce equations with fewer regular singular points and stronger irregular behavior.

This hierarchy is not just taxonomy. Irregular singularities are where asymptotics, Stokes phenomena, and semiclassical boundary conditions enter. In physics, that is exactly where scattering, tunneling, quasi-normal modes, and decay conditions live.

## Heun polynomials

A Heun series may truncate to a polynomial under special conditions. A necessary condition is usually that one of the exponent parameters is a nonpositive integer, for example

$$
\alpha=-N,
\qquad N\in\mathbb Z_{\ge0}.
$$

But unlike the hypergeometric case, this is not enough. One also needs a determinant condition on the accessory parameter $q$ so that the recurrence terminates consistently:

$$
\Delta_{N+1}(q)=0.
$$

Thus Heun polynomial solutions occur at discrete values of $q$. This is the finite-dimensional shadow of the general spectral problem.

This extra condition is a perfect diagnostic of the difference between hypergeometric and Heun behavior. For ${}_2F_1$, $a=-N$ terminates the two-term recurrence automatically. For Heun, the three-term recurrence needs one more constraint.

## Physical sources of Heun equations

Heun equations appear whenever a separated ODE has four singular points or a confluent version of that structure. Common sources include:

- angular and radial spheroidal equations;
- wave equations in black-hole backgrounds;
- Coulomb–Stark and related quantum-mechanical spectral problems;
- finite-gap and semiclassical Schrödinger problems;
- perturbations in rotating or charged geometries;
- exact WKB and monodromy calculations;
- Seiberg–Witten and AGT-related spectral/ODE correspondences.

The exact list depends on the field. The common mechanism is stable: separation of variables produces a second-order ODE whose singularity structure has gone beyond the hypergeometric class.

In black-hole perturbation theory, for example, regular singular points often correspond to horizons and asymptotic endpoints after a change of variables. Boundary conditions such as ingoing at the horizon and outgoing at infinity become connection problems between singular points. The allowed frequencies are then encoded in monodromy or connection data.

## Monodromy and connection problems

Let $y_1,y_2$ be a local basis of solutions near a base point. Analytic continuation around a singularity transforms the basis by a matrix

$$
\begin{pmatrix}y_1\\ y_2\end{pmatrix}
\longmapsto
M_i
\begin{pmatrix}y_1\\ y_2\end{pmatrix}.
$$

For four singular points, the monodromy matrices satisfy

$$
M_0M_1M_aM_\infty=1,
$$

up to convention for loop order. The local exponents determine the eigenvalues of $M_i$, but not all relative orientations of these matrices. The accessory parameter $q$ controls that missing global information.

Connection problems ask how a solution normalized near one singular point decomposes into a basis normalized near another. In hypergeometric theory, connection coefficients are gamma-function combinations. In Heun theory, there is no comparably universal closed formula. One often uses continued fractions, numerical integration, monodromy methods, Fredholm determinants, or isomonodromic tau functions.

This is where Heun functions connect to modern exact methods. The hard part is not writing the local equation. The hard part is global analytic continuation.

## Relation to isomonodromy and Painleve equations

If the position $a$ of the fourth singularity is varied while monodromy data are held fixed, the accessory parameter must vary with $a$. The resulting deformation problem is isomonodromic.

For rank-two Fuchsian systems on the four-punctured sphere, this deformation is governed by the Painleve VI equation. Confluent limits of the singularity pattern lead to confluent Painleve equations. This is one of the bridges between Heun equations, exact WKB, two-dimensional CFT, Seiberg–Witten theory, and black-hole spectral problems.

For this page, the important lesson is modest: Heun equations are not just “harder hypergeometric functions.” They are gateways into monodromy geometry.

## Numerical and asymptotic practice

In practical calculations, one rarely evaluates a Heun function by a single formula across the whole plane. Instead one combines methods:

1. Use local Frobenius series near regular singular points.
2. Use analytic continuation by overlapping disks or numerical ODE integration.
3. Use continued fractions for spectral conditions when a three-term recurrence is stable.
4. Use asymptotic or WKB expansions near irregular singular points.
5. Use monodromy or tau-function methods when global exact structure matters.

The method should be chosen by the physics question. A quasi-normal-mode problem, a bound-state problem, and a Euclidean regularity problem may have the same local Heun equation but different boundary conditions and therefore different useful representations.

## Common pitfalls

The first mistake is assuming that the local Heun function determines the global answer. It determines one local solution. Boundary conditions elsewhere are a separate connection problem.

The second mistake is ignoring the accessory parameter. Local exponent data do not determine $q$. In many physics problems, $q$ is exactly the eigenvalue or separation constant being solved for.

The third mistake is mixing normal forms. Heun notation is less standardized than hypergeometric notation. The same-looking parameter tuple can mean different equations in different software packages or references.

The fourth mistake is expecting hypergeometric-style gamma-function connection coefficients. They occur in special reducible cases, not generically.

The fifth mistake is treating irregular singularities in confluent equations as ordinary singular points. Irregular singularities carry Stokes data, and Stokes sectors matter for boundary conditions.

## Worked example: why termination needs two conditions

Consider the local series recurrence

$$
A_n c_{n+1}+B_n c_n+C_n c_{n-1}=0.
$$

For a polynomial of degree $N$, we need

$$
c_{N+1}=c_{N+2}=\cdots=0.
$$

A parameter choice such as $\alpha=-N$ can make the upward recurrence compatible with $C_{N+1}=0$, removing the source term that would force higher coefficients. But $c_{N+1}$ itself is determined by all previous coefficients and by $q$. Therefore one also needs

$$
c_{N+1}(q)=0.
$$

Since $c_{N+1}$ is a polynomial or rational function of $q$ in standard normalizations, this becomes a finite determinant condition. The resulting special values of $q$ give Heun polynomial solutions.

This is the simplest way to see the spectral character of the accessory parameter.

## Exercises

### Exercise 1: Find the exponents at zero

For the general Heun equation

$$
y''+\left(\frac{\gamma}{z}+\frac{\delta}{z-1}+\frac{\epsilon}{z-a}\right)y'
+\frac{\alpha\beta z-q}{z(z-1)(z-a)}y=0,
$$

derive the exponents at $z=0$.

<details><summary><strong>Solution</strong></summary>

Near $z=0$, the most singular parts are

$$
y''+\frac{\gamma}{z}y'+\text{less singular terms}=0.
$$

Use $y=z^s$. Then

$$
y'=s z^{s-1},
\qquad
 y''=s(s-1)z^{s-2}.
$$

The leading terms give

$$
\big[s(s-1)+\gamma s\big]z^{s-2}=0.
$$

Thus

$$
s(s+\gamma-1)=0,
$$

so the exponents are

$$
s=0,
\qquad
s=1-\gamma.
$$

</details>

### Exercise 2: Why is $q$ not local exponent data?

Show from the same indicial calculation at $z=0$ that the accessory parameter $q$ does not enter the local exponents.

<details><summary><strong>Solution</strong></summary>

Near $z=0$,

$$
\frac{\alpha\beta z-q}{z(z-1)(z-a)}
\sim
\frac{-q}{a z}+O(1).
$$

Multiplying this by $y=z^s$ gives a term of order $z^{s-1}$. The leading terms in the indicial equation are of order $z^{s-2}$ and come from $y''+\gamma y'/z$. Therefore $q$ does not enter the indicial equation. It affects the recurrence coefficients and global monodromy, not the local exponents.

</details>

### Exercise 3: Compare coefficient recurrences

Explain why hypergeometric series coefficients obey a two-term recurrence while Heun coefficients generically obey a three-term recurrence.

<details><summary><strong>Solution</strong></summary>

For ${}_2F_1$, the coefficient ratio is explicitly rational:

$$
\frac{A_{n+1}}{A_n}
=\frac{(n+a)(n+b)}{(n+c)(n+1)}.
$$

Thus each coefficient is determined directly from the previous one. This is a two-term recurrence.

For the Heun equation, substitution of $y=\sum c_n z^n$ produces

$$
A_n c_{n+1}+B_n c_n+C_n c_{n-1}=0.
$$

Thus $c_{n+1}$ depends on both $c_n$ and $c_{n-1}$. This extra memory is tied to the extra singular point and accessory parameter.

</details>

### Exercise 4: Apparent singularity intuition

What does it mean for a singular point of an ODE to be apparent?

<details><summary><strong>Solution</strong></summary>

An apparent singularity is a singularity of the differential equation coefficients around which the actual solutions have trivial monodromy. Locally the equation looks singular, but analytic continuation of the solution basis around the point produces no branch mixing or nontrivial phase, up to a basis choice. Apparent singularities often arise when an equation has been written in a form with extra singular points that do not represent genuine multivaluedness of the solutions.

</details>

## Related pages

For the three-singularity model, see [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/). For the ODE and spectral background, see [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Sturm–Liouville Theory](/math-toolkit/differential-equations-green-functions/sturm-liouville-theory/), and [Schrödinger Operators](/math-toolkit/differential-equations-green-functions/schrodinger-operators/). For the analytic continuation and global geometry, see [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), and [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/).

## References and further reading

Classic mathematical references include Ince, Whittaker and Watson, Ronveaux’s edited volume on Heun equations, Slavyanov and Lay, Maier’s work on transformations, Olver, and the NIST Digital Library of Mathematical Functions. For physics applications, see literature on spheroidal functions, black-hole perturbation theory, exact WKB, Seiberg–Witten theory, AGT-type correspondences, and isomonodromic deformation.

## Version history

- 2026-06-26: First polished draft. Added general Heun normal form, singularity and exponent data, accessory parameter discussion, local recurrence, confluence hierarchy, polynomial truncation, monodromy viewpoint, QFT applications, pitfalls, and exercises with solutions.
