---
title: "Isomonodromy Preview"
description: "Introduces isomonodromic deformations for QFT: linear systems, monodromy and Stokes data, zero-curvature equations, Schlesinger equations, Painlevé equations, tau functions, Fredholm determinants, and links to CFT, matrix models, and exact WKB."
sidebar:
  label: "Isomonodromy Preview"
  order: 10
level: Advanced
status: "Polished draft"
source: "Standard references on isomonodromic deformations, monodromy-preserving equations, Schlesinger systems, Painlevé equations, Jimbo–Miwa–Ueno tau functions, Riemann–Hilbert problems, Fredholm determinants, exact WKB, integrable QFT, random matrices, and CFT/gauge-theory correspondences."
topics:
  - isomonodromy
  - monodromy
  - Stokes data
  - linear differential equation
  - Schlesinger equation
  - Painleve equation
  - tau function
  - Riemann-Hilbert problem
  - Fredholm determinant
  - exact WKB
  - conformal block
  - integrable QFT
canonicalTopics:
  - isomonodromy
  - monodromy
  - stokes-data
  - linear-differential-equation
  - schlesinger-equation
  - painleve-equation
  - tau-function
  - riemann-hilbert-problem
  - fredholm-determinant
  - exact-wkb
  - conformal-block
  - integrable-qft
researchStatus:
  established:
    - "Isomonodromic deformation equations describe deformations of linear differential systems that preserve monodromy and Stokes data; in rank two and low-complexity cases they produce the Painlevé equations."
    - "For Fuchsian systems, the Schlesinger equations are the standard monodromy-preserving deformation equations, and their tau functions are defined by a closed Hamiltonian one-form."
  active:
    - "The detailed dictionary among isomonodromic tau functions, conformal blocks, exact WKB, Fredholm determinants, topological strings, and supersymmetric gauge theories is an active research interface."
---

## Summary

Isomonodromy is the study of **deforming a linear differential equation while keeping its analytic-continuation data fixed**. A typical local system is

$$
\partial_z\Psi(z;t)=A(z;t)\Psi(z;t),
$$

where $z$ is the spectral or complex coordinate, $t$ is a deformation parameter, and $A(z;t)$ has singularities. Solutions analytically continued around the singularities transform by monodromy matrices; near irregular singularities they also carry Stokes data. An **isomonodromic deformation** changes $A$ and the singularity positions but leaves that monodromy/Stokes data unchanged, up to the natural overall conjugations.

That simple sentence hides a useful trick. Linear equations know about analytic continuation; nonlinear equations appear when one asks how the linear equation may move without changing that analytic continuation. This is why Painlevé equations, Fredholm determinants, exact two-dimensional Ising correlators, random-matrix distributions, Riemann–Hilbert problems, conformal blocks, and supersymmetric gauge-theory partition functions keep meeting in the same suspicious alley.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a linear differential system, singular points, fixed monodromy and Stokes data, deformation equations, zero curvature, nonlinear equations, and tau functions.](/figures/math-toolkit/isomonodromy-deformation-flow.svg)

<figcaption>

Isomonodromy starts with a linear differential system and asks for deformations that keep monodromy and Stokes data fixed. The compatibility of the $z$-equation and deformation equation gives a zero-curvature equation. In special cases this becomes the Schlesinger system or one of the Painlevé equations; the associated tau function packages Hamiltonians, determinants, and exact correlation functions.

</figcaption>
</figure>

This page is a preview, not a full course. Its goal is to explain the dictionary well enough that later pages on exact WKB, conformal blocks, integrable QFT, Fredholm determinants, and matrix models can say “isomonodromy” without dropping readers into a trapdoor.

## Prerequisites

You should know [Ordinary Differential Equations](/math-toolkit/differential-equations-green-functions/ordinary-differential-equations/), [Analytic Functions](/math-toolkit/complex-analysis/analytic-functions/), [Residues and Contours](/math-toolkit/complex-analysis/residues-and-contours/), [Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/), [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/), [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/), [Hypergeometric Functions](/math-toolkit/special-functions-exact-equations/hypergeometric-functions/), [Heun Equations](/math-toolkit/special-functions-exact-equations/heun-equations/), and [Painlevé Equations](/math-toolkit/special-functions-exact-equations/painleve-equations/).

It also helps to have seen [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Spectral Density](/math-toolkit/functional-analysis-spectral-theory/spectral-density/), and [Saddle Points](/math-toolkit/complex-analysis/saddle-points/). Those pages explain why determinants, spectra, and steepest-descent paths keep appearing near isomonodromic tau functions.

## Core idea

A scalar ODE such as the hypergeometric equation has singular points. If a solution is analytically continued around one of them, it may come back as a linear combination of the original basis of solutions. For a vector-valued system

$$
\partial_z\Psi=A(z)\Psi,
$$

this continuation is encoded by matrices. Choose a base point and a fundamental matrix solution $\Psi(z)$. If $\gamma_i$ is a loop around the $i$th singular point, analytic continuation gives

$$
\Psi(z)\longmapsto \Psi(z)M_i.
$$

The matrices $M_i$ are the **monodromy matrices**. They depend on choices: changing the basis of solutions conjugates all $M_i$ simultaneously. The invariant information is therefore not the raw list of matrices but the monodromy representation up to equivalence, together with local exponent and Stokes data when needed.

Now allow the singularities or coefficients to depend on deformation parameters $t$. Generically, moving a pole changes the monodromy. Isomonodromy asks for the special motion where the monodromy stays fixed. The deformation is then constrained by an auxiliary equation

$$
\partial_t\Psi=B(z;t)\Psi.
$$

The two equations are compatible only if mixed partial derivatives agree:

$$
\partial_t\partial_z\Psi=\partial_z\partial_t\Psi.
$$

Substituting the two linear systems gives the zero-curvature equation

$$
\partial_t A-\partial_z B+[A,B]=0.
$$

This is the whole mechanism in one line. Linear analytic-continuation data become nonlinear deformation equations through compatibility.

## Setup and conventions

This page uses right monodromy convention

$$
\Psi\mapsto \Psi M_\gamma
$$

for a fundamental solution matrix. Some authors use left monodromy or transpose conventions. This changes formulas by conjugation or reversal of multiplication order, not the underlying geometry.

For a Fuchsian system on the Riemann sphere we write

$$
\partial_z\Psi=A(z)\Psi,
\qquad
A(z)=\sum_{i=1}^n {A_i\over z-a_i},
$$

where $a_i$ are regular singular points and $A_i$ are residue matrices. Regular singular means that local solutions have power-law and logarithmic behavior, not exponential growth of the type produced by irregular singularities.

The sum of residues controls the singularity at infinity. On the sphere one usually imposes

$$
A_\infty=-\sum_{i=1}^n A_i.
$$

The local eigenvalues of $A_i$ determine local exponents modulo integer subtleties and resonance. The full monodromy matrices contain more than local exponents: they also encode how local solution bases are connected globally.

For irregular singularities, monodromy matrices are not enough. One must also include **Stokes matrices**, which record how asymptotic expansions jump across Stokes rays. In exact WKB language, this is where analytic continuation meets wall-crossing-like behavior. The slogans are mercifully short; the bookkeeping is not.

## From monodromy preservation to zero curvature

Suppose $\Psi$ obeys two linear equations,

$$
\partial_z\Psi=A(z;t)\Psi,
\qquad
\partial_t\Psi=B(z;t)\Psi.
$$

Then

$$
\partial_t\partial_z\Psi
=(\partial_t A)\Psi+A\partial_t\Psi
=(\partial_t A+AB)\Psi,
$$

while

$$
\partial_z\partial_t\Psi
=(\partial_z B)\Psi+B\partial_z\Psi
=(\partial_z B+BA)\Psi.
$$

Equating the two expressions gives

$$
\partial_t A-\partial_z B+[A,B]=0.
$$

This looks like a flatness condition for a connection on the product space with coordinates $(z,t)$:

$$
\nabla=d-A\,dz-B\,dt.
$$

The condition says that the extended connection is flat in the $(z,t)$ directions. The deformation is therefore parallel transport in parameter space compatible with parallel transport in the $z$-plane. This is why isomonodromy is geometrically close to flat connections, holonomy, Wilson lines, and the Riemann–Hilbert correspondence.

A useful mnemonic is:

$$
\text{linear system}+\text{fixed monodromy}
\quad\Longrightarrow\quad
\text{nonlinear deformation equation}.
$$

The reverse problem is just as important. Given monodromy data, construct a linear system realizing them. That is a Riemann–Hilbert problem. Isomonodromy studies how the solution of that problem changes when the singularity positions or formal types move.

## Fuchsian systems and Schlesinger equations

For the Fuchsian system

$$
A(z)=\sum_{i=1}^n {A_i\over z-a_i},
$$

let the pole locations $a_i$ be deformation parameters. The monodromy-preserving deformation equations are the **Schlesinger equations**:

$$
{\partial A_i\over\partial a_j}={ [A_i,A_j]\over a_i-a_j},
\qquad i\ne j,
$$

and

$$
{\partial A_i\over\partial a_i}
=-\sum_{j\ne i}{ [A_i,A_j]\over a_i-a_j}.
$$

These equations say that the residues $A_i$ cannot remain fixed if the poles move. The residues must rotate against each other by commutators so that the global monodromy representation stays fixed.

One way to see the form of the equations is to take the deformation equation associated with moving $a_j$ as

$$
{\partial\Psi\over\partial a_j}=-{A_j\over z-a_j}\Psi.
$$

Compatibility with $\partial_z\Psi=A(z)\Psi$ then produces the Schlesinger equations after matching residues at each pole. This is a clean derivation because the only possible singularities are simple poles at the $a_i$.

The equations preserve conjugacy classes of the residues. For example,

$$
{\partial\over\partial a_j}\operatorname{tr}(A_i^k)=0
$$

for $i\ne j$, since differentiating gives a trace of a commutator. Thus local exponents are fixed while the global connection varies. That is exactly what monodromy preservation should do.

## Painlevé equations from low-dimensional isomonodromy

Painlevé equations are the most famous nonlinear shadows of isomonodromy. The cleanest slogan is:

> Painlevé VI is the isomonodromic deformation equation for a rank-two Fuchsian system on the four-punctured sphere.

Put the punctures at

$$
0,\quad x,\quad 1,\quad \infty
$$

where $x$ is the cross-ratio and hence the deformation parameter. The Schlesinger equations for the residues can be reduced to a second-order nonlinear ODE for a scalar coordinate $y(x)$, often interpreted as the location of an apparent singularity in an associated scalar equation. That ODE is $P_{\rm VI}$.

The lower Painlevé equations arise by confluence. Singularities collide; regular singularities become irregular singularities; monodromy matrices are supplemented by Stokes data. Roughly:

$$
P_{\rm VI}\to P_{\rm V}\to P_{\rm III},
\qquad
P_{\rm VI}\to P_{\rm V}\to P_{\rm IV}\to P_{\rm II}\to P_{\rm I},
$$

with several branches and degenerations. The precise confluence diagram depends on the classification used, but the important physical idea is stable: simpler Painlevé equations often encode more singular scaling limits of the original monodromy problem.

This is why Painlevé equations show up in scaling limits. A system near a critical point often collapses complicated microscopic data into a universal monodromy/Stokes problem. The resulting nonlinear equation is not arbitrary; it is one of the special equations surviving the collapse.

## Apparent singularities

An **apparent singularity** is a singularity of an auxiliary scalar equation whose local monodromy is trivial. It is visible in the differential equation but invisible in the monodromy representation.

This sounds contradictory until one remembers that converting a first-order matrix system into a scalar higher-order equation often introduces extra singular points. Some are bookkeeping artifacts. Their positions become dynamical variables, and the condition that their monodromy remain trivial imposes nonlinear equations.

In the four-punctured rank-two case, the apparent singularity coordinate is one way to obtain the Painlevé VI variable $y(x)$. The puncture location $x$ moves; the monodromy data are fixed; the apparent singularity position $y(x)$ responds. The nonlinear Painlevé equation is the rule for that response.

This is a useful conceptual bridge to QFT. An auxiliary linear problem may contain spectral-parameter singularities that are not physical insertions. Their motion still controls physical objects such as correlators or determinants because it is tied to the consistency of the analytic structure.

## Tau functions

Isomonodromic deformation equations are Hamiltonian systems. Their Hamiltonians are packaged by a tau function. For Fuchsian Schlesinger systems, the isomonodromic tau function is characterized locally by

$$
{\partial\over\partial a_i}\log\tau
=\sum_{j\ne i}{\operatorname{tr}(A_iA_j)\over a_i-a_j},
$$

up to normalization. Equivalently, $d\log\tau$ is a closed one-form on the isomonodromic deformation space.

The word “tau” is used in many nearby subjects: integrable hierarchies, matrix models, KP/Toda theory, Fredholm determinants, and CFT. These tau functions are not automatically identical by vocabulary alone. In the cases relevant to QFT, the power of isomonodromy is that these meanings often become literally related.

For example, certain Fredholm determinants obey differential identities that identify them as isomonodromic tau functions. Scaling limits of random matrices give Painlevé tau functions. Some two-dimensional Ising correlation functions are expressible through Painlevé tau functions. CFT conformal blocks can provide expansions of isomonodromic tau functions in monodromy channels. The same object is seen from several coordinate systems: determinant, correlator, monodromy problem, and nonlinear ODE.

A useful way to remember the tau function is:

$$
\text{isomonodromic equation} = \text{equation of motion},
\qquad
\tau = \text{generating function for its Hamiltonians}.
$$

In physics language, $\log\tau$ often behaves like a free energy, effective action, or determinant. But that analogy should be checked in each problem; tau functions are not automatically thermodynamic partition functions.

## Riemann–Hilbert viewpoint

The Riemann–Hilbert problem asks for a piecewise analytic function with prescribed jumps or monodromy. In a typical matrix formulation, one seeks $Y(z)$ analytic away from contours such that

$$
Y_+(z)=Y_-(z)J(z)
$$

on the contour, with prescribed normalization and singular behavior. The jump matrices $J(z)$ encode monodromy or Stokes data.

This viewpoint is powerful because it reverses the usual ODE problem. Instead of starting with coefficients and computing monodromy, one starts with monodromy data and reconstructs the differential equation. Isomonodromy then becomes the statement that the jump data are fixed while the contour endpoints, singularity locations, or asymptotic parameters move.

In QFT and statistical mechanics, Riemann–Hilbert problems often arise from integrable kernels, form-factor resummations, orthogonal polynomials, and steepest-descent analysis. The nonlinear differential equation enters after one studies how the Riemann–Hilbert solution varies with the physical scale.

The advantage is that asymptotics become geometric. Large-distance, high-energy, or double-scaling limits can often be studied by deforming contours and matching local parametrices. That is why isomonodromy is not just an exact-solution curiosity; it is a method for extracting controlled asymptotics.

## Stokes data and exact WKB

For a regular singularity, monodromy matrices record how local solutions transform around loops. For an irregular singularity, local solutions have exponential asymptotics, schematically

$$
\Psi(z)\sim \widehat\Psi(z)\exp Q(z),
$$

where $\widehat\Psi$ may be a formal divergent series. The dominant exponential changes from sector to sector in the complex plane. Across Stokes rays, the asymptotic expansion jumps by Stokes matrices.

An isomonodromic deformation with irregular singularities preserves not just ordinary monodromy but the full generalized monodromy data: formal exponents, connection matrices, and Stokes matrices. This is the doorway to exact WKB and resurgence.

In exact WKB, one studies differential equations with a small parameter, often written $\hbar$, and tracks how WKB periods, Borel sums, and Stokes jumps change. Isomonodromy provides one of the cleanest languages for this because the Stokes data are the invariant analytic-continuation data. Moving in parameter space while preserving them produces nonlinear equations and tau functions.

This is also why isomonodromy appears near Seiberg–Witten geometry, quantum curves, topological strings, and supersymmetric gauge theory. There, periods, spectral curves, Stokes graphs, and instanton expansions are not separate gadgets; they are different views of the same analytic continuation problem.

## QFT appearances

**Two-dimensional Ising model.** Scaling limits of spin and disorder correlators in the massive Ising model can be expressed through Painlevé equations, especially forms related to $P_{\rm III}$. The conceptual reason is that the correlation problem has enough integrable structure to reduce to a monodromy-preserving deformation.

**Random matrices and Fredholm determinants.** Gap probabilities and edge distributions are often Fredholm determinants of integrable kernels. Their logarithmic derivatives satisfy Painlevé equations or related isomonodromic systems. The Tracy–Widom distributions are the most famous entry point, but the phenomenon is broader.

**Integrable QFT.** Form-factor expansions and exact correlation functions in two-dimensional integrable theories can lead to determinants or Riemann–Hilbert problems whose deformation equations are isomonodromic. Isomonodromy is one of the bridges between exact S-matrix data and spacetime correlators.

**CFT conformal blocks.** Four-point conformal blocks, especially on the sphere, are naturally tied to monodromy problems. In the semiclassical limit, conformal blocks solve accessory-parameter problems. In more exact correspondences, isomonodromic tau functions can be expanded in terms of conformal blocks, with monodromy data playing the role of intermediate-channel data.

**Supersymmetric gauge theory.** Through AGT-type correspondences and Nekrasov partition functions, isomonodromic tau functions connect to four-dimensional supersymmetric gauge theories. In this language, Coulomb moduli, masses, instanton counting parameters, and duality frames become part of a monodromy/tau-function dictionary.

**Black holes and wave equations.** Certain wave equations in black-hole backgrounds reduce to Heun-type or confluent Heun-type equations. Monodromy methods and isomonodromic deformations help organize connection coefficients, quasinormal-mode conditions, and accessory parameters. This is a lively interface, so local conventions matter a lot.

## Worked example: compatibility gives Schlesinger in miniature

Take a Fuchsian system

$$
\partial_z\Psi=\left(\sum_{i=1}^n {A_i\over z-a_i}\right)\Psi
$$

and deform one pole $a_j$ by

$$
\partial_{a_j}\Psi=-{A_j\over z-a_j}\Psi.
$$

Set

$$
A(z)=\sum_i {A_i\over z-a_i},
\qquad
B_j(z)=-{A_j\over z-a_j}.
$$

Compatibility gives

$$
\partial_{a_j}A-\partial_zB_j+[A,B_j]=0.
$$

For $i\ne j$, the residue at $z=a_i$ is

$$
{\partial_{a_j}A_i\over z-a_i}
+{[A_i,-A_j]\over (z-a_i)(z-a_j)}.
$$

Near $z=a_i$,

$$
{1\over (z-a_i)(z-a_j)}
={1\over a_i-a_j}{1\over z-a_i}+\text{regular at }a_i.
$$

Thus the coefficient of $(z-a_i)^{-1}$ vanishes only if

$$
\partial_{a_j}A_i={ [A_i,A_j]\over a_i-a_j}.
$$

The residue at $z=a_j$ then gives

$$
\partial_{a_j}A_j=-\sum_{i\ne j}{ [A_j,A_i]\over a_j-a_i}.
$$

These are the Schlesinger equations. The derivation is not long, but it is the baby version of a deep principle: matching singular parts of a flatness equation produces nonlinear dynamics.

## Common pitfalls

**Fixed monodromy does not mean fixed solution.** The solution matrix $\Psi(z;t)$ changes with $t$. What is preserved is its analytic-continuation representation, up to allowed equivalences.

**Monodromy matrices are basis-dependent.** Changing the fundamental solution by a constant invertible matrix conjugates all monodromy matrices. Physical or geometric data usually live in conjugacy-invariant quantities or in a representation modulo equivalence.

**Local exponents are not the full monodromy data.** Eigenvalues of residues tell part of the local story, but connection matrices and global products matter. Two systems can have the same local exponents and different global monodromy.

**Irregular singularities require Stokes data.** Ordinary monodromy around loops is not enough when asymptotic expansions jump across Stokes sectors. Many QFT applications live precisely in this irregular world.

**A tau function is not automatically a partition function.** In many examples $\tau$ is a determinant, free energy, or partition function. But that identification is an additional theorem or construction, not a consequence of the name.

**Apparent singularities are not physical insertions by default.** They may be auxiliary coordinates introduced by reducing a matrix system to a scalar equation. They can still control physical quantities because the auxiliary problem encodes the analytic structure.

**Confluence is a singular limit.** Sending punctures together is not just setting two variables equal. One must rescale parameters and track how monodromy data turn into Stokes data.

## Relations to other pages

[Heun Equations](/math-toolkit/special-functions-exact-equations/heun-equations/) explains the linear equations that often appear before the isomonodromic deformation is imposed. [Painlevé Equations](/math-toolkit/special-functions-exact-equations/painleve-equations/) explains the nonlinear equations that arise after monodromy preservation.

[Branch Cuts and Riemann Sheets](/math-toolkit/complex-analysis/branch-cuts-and-riemann-sheets/) and [Analytic Continuation](/math-toolkit/complex-analysis/analytic-continuation/) supply the analytic-continuation language behind monodromy. [Riemann Surfaces](/math-toolkit/complex-analysis/riemann-surfaces/) supplies the global stage for punctures, cycles, and periods.

[Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/) provide nearby determinant technology. Isomonodromic tau functions often meet these pages when exact determinants are deformed by masses, intervals, boundary conditions, or spectral parameters.

[Modular Forms](/math-toolkit/special-functions-exact-equations/modular-forms/) is a useful companion because many monodromy problems on tori and punctured surfaces have modular transformations. [Elliptic Functions and Integrals](/math-toolkit/special-functions-exact-equations/elliptic-functions-and-integrals/) supplies the period language that reappears in Seiberg–Witten and exact-WKB applications.

## Research status

The core mathematics of Schlesinger equations, monodromy-preserving deformations, Painlevé equations, Riemann–Hilbert problems, and Jimbo–Miwa–Ueno tau functions is established. The formulas on this page are standard, modulo convention choices about left/right monodromy and tau-function normalization.

The active frontier is the web of identifications. In modern mathematical physics, isomonodromic tau functions connect to conformal blocks, $c=1$ CFT, AGT correspondences, Nekrasov functions, exact WKB, cluster coordinates, topological strings, Fredholm determinants, black-hole perturbation theory, and nonperturbative completions of quantum curves. These relations are not one theorem with one set of hypotheses. They are a constellation of precise correspondences, asymptotic regimes, and still-developing dictionaries.

For this reason, later pages should distinguish carefully between three statements:

$$
\text{same differential equation},
\qquad
\text{same tau function after normalization},
\qquad
\text{same physical observable}.
$$

The first is often easy to verify. The second requires normalization and boundary data. The third requires the physics map.

## Exercises

1. **Derive zero curvature.** Starting from

   $$
   \partial_z\Psi=A\Psi,
   \qquad
   \partial_t\Psi=B\Psi,
   $$

   derive the compatibility condition

   $$
   \partial_tA-\partial_zB+[A,B]=0.
   $$

<details><summary><strong>Solution</strong></summary>

Compute mixed derivatives in both orders:

$$
\partial_t\partial_z\Psi
=\partial_t(A\Psi)
=(\partial_tA)\Psi+A(\partial_t\Psi)
=(\partial_tA+AB)\Psi,
$$

and

$$
\partial_z\partial_t\Psi
=\partial_z(B\Psi)
=(\partial_zB)\Psi+B(\partial_z\Psi)
=(\partial_zB+BA)\Psi.
$$

Equality of mixed derivatives for a fundamental solution matrix gives

$$
\partial_tA+AB=\partial_zB+BA,
$$

or

$$
\partial_tA-\partial_zB+[A,B]=0.
$$

</details>

2. **Trace invariants of Schlesinger flow.** For $i\ne j$, use

   $$
   {\partial A_i\over\partial a_j}={ [A_i,A_j]\over a_i-a_j}
   $$

   to show that $\partial_{a_j}\operatorname{tr}(A_i^k)=0$.

<details><summary><strong>Solution</strong></summary>

Differentiate and use cyclicity of trace:

$$
\partial_{a_j}\operatorname{tr}(A_i^k)
=k\operatorname{tr}\left(A_i^{k-1}{\partial A_i\over\partial a_j}\right)
={k\over a_i-a_j}\operatorname{tr}\left(A_i^{k-1}[A_i,A_j]\right).
$$

Since $A_i^{k-1}$ commutes with $A_i$,

$$
\operatorname{tr}\left(A_i^{k-1}[A_i,A_j]\right)
=\operatorname{tr}(A_i^kA_j)-\operatorname{tr}(A_i^{k-1}A_jA_i)=0
$$

by cyclicity. Therefore $\operatorname{tr}(A_i^k)$ is preserved under the deformation of $a_j$.

</details>

3. **Why apparent singularities can move.** Explain why a singularity with trivial local monodromy can still appear as a dynamical variable in a scalar ODE derived from a matrix system.

<details><summary><strong>Solution</strong></summary>

Reducing a first-order matrix system to a scalar higher-order equation may introduce poles in the scalar coefficients that were not singularities of the original connection. If the local monodromy around such a point is trivial, the singularity is apparent: it affects the scalar representation but not the monodromy representation. Its position can still vary because the scalar equation has extra coordinate data beyond the invariant monodromy data. Requiring the singularity to remain apparent under deformation imposes nonlinear equations on its position.

</details>

4. **Regular versus irregular singularities.** In one sentence each, state what extra data are needed at an irregular singularity compared with a regular singularity.

<details><summary><strong>Solution</strong></summary>

At a regular singularity, local monodromy and exponents describe the analytic continuation of local solutions. At an irregular singularity, solutions have sector-dependent exponential asymptotics, so one must add Stokes matrices and formal exponential data to the ordinary monodromy information.

</details>

## References

For classical isomonodromy and Painlevé theory, see Jimbo, Miwa, and Ueno on monodromy-preserving deformations; the book by Iwasaki, Kimura, Shimomura, and Yoshida; and Fokas, Its, Kapaev, and Novokshenov on Painlevé transcendents and Riemann–Hilbert problems.

For QFT and statistical-mechanics appearances, useful anchors include McCoy and Wu on the two-dimensional Ising model; Tracy and Widom on Fredholm determinants and random matrices; Palmer on planar Ising correlations; and the integrable-QFT literature on form factors and Painlevé-type correlation functions.

For conformal-block and gauge-theory connections, useful anchors include the work of Gamayun, Iorgov, and Lisovyy on Painlevé tau functions and conformal blocks; the AGT literature; and modern papers on isomonodromy, exact WKB, quantum curves, and supersymmetric gauge theory.

## Version history

- **2026-06-26:** Initial polished draft. Added the isomonodromy dictionary, Schlesinger equations, tau-function normalization, QFT applications, common pitfalls, and exercises.
