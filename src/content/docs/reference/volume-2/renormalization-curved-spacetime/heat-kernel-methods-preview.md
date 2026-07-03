---
title: "Heat-Kernel Methods Preview"
description: "A preview of heat-kernel and Schwinger–DeWitt methods for extracting one-loop divergences, local curvature counterterms, trace anomalies, and EFT coefficients in curved spacetime."
sidebar:
  label: "Heat-Kernel Methods Preview"
  order: 50
level: Advanced
status: "Polished draft"
source: "DeWitt; Seeley; Gilkey; Vassilevich; Birrell and Davies; Parker and Toms; Avramidi; Barvinsky and Vilkovisky; Zinn-Justin 2021."
topics:
  - heat kernel
  - Schwinger proper time
  - Seeley-DeWitt coefficients
  - one-loop determinants
  - curvature counterterms
  - trace anomaly
canonicalTopics:
  - heat-kernel-methods
  - seeley-dewitt-coefficients
  - one-loop-determinants
  - curved-spacetime-renormalization
researchStatus:
  established:
    - "Short-time heat-kernel expansions are a standard and systematic way to compute local one-loop UV divergences and curvature counterterms for Laplace-type operators."
  active:
    - "Nonlocal form factors, Lorentzian prescriptions, boundaries, zero modes, gauge theories, higher-spin fields, singular spaces, and nonminimal operators require extensions beyond the simplest local bulk expansion."
---

## Summary

Heat-kernel methods turn one-loop determinants into local geometric data. If a Euclidean quadratic fluctuation operator is a positive Laplace-type operator $\Delta$, then the one-loop contribution contains

$$
\operatorname{Tr}\log\Delta.
$$

The Schwinger proper-time representation rewrites this as

$$
\operatorname{Tr}\log\Delta
=-\int_0^\infty\frac{ds}{s}\operatorname{Tr}e^{-s\Delta},
$$

up to an additive constant and regularization choices. The operator

$$
K(s)=e^{-s\Delta}
$$

is the heat kernel. Its short-time expansion has the form

$$
\operatorname{Tr}e^{-s\Delta}
\sim
\frac{1}{(4\pi s)^{d/2}}
\sum_{n=0}^{\infty}s^n\int d^d x\sqrt g\,\operatorname{tr}a_{2n}(x),
\qquad s\to0^+.
$$

The coefficients $a_{2n}(x)$ are local curvature invariants built from the metric, the bundle connection, and the lower-derivative terms in $\Delta$. In four dimensions, $a_0$, $a_2$, and $a_4$ control the local UV divergences of a massive one-loop determinant. The coefficient $a_4$ is especially important for logarithmic divergences and trace anomalies.

The key slogan is:

$$
\text{UV divergences of one-loop determinants}
\quad\Longleftrightarrow\quad
\text{short-time heat-kernel coefficients}.
$$

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Heat-kernel coefficient tower mapping a Laplace-type operator to short-time coefficients and local counterterms](/figures/renormalization-rg-eft/heat-kernel-expansion-map.svg)

<figcaption>

Heat-kernel methods convert a one-loop determinant into a proper-time integral. The UV region is $s\to0$, where the short-time expansion produces local coefficients $a_0$, $a_2$, $a_4$, and higher terms. These coefficients determine the local counterterm tower and, in even dimensions, anomaly data.

</figcaption>
</figure>

## Prerequisites

You should know [Effective Action in Curved Spacetime](/renormalization-rg-eft/renormalization-curved-spacetime/effective-action-in-curved-spacetime/), [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/), [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/), [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), and [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/).

Mathematically, you should be comfortable with eigenfunction expansions, Gaussian path integrals, covariant derivatives, curvature tensors, and the idea of an asymptotic expansion. This page is a preview: it explains the logic and the main formulas, not the full derivation of every coefficient.

## Core idea

The heat equation associated with a differential operator $\Delta$ is

$$
\left(\frac{\partial}{\partial s}+\Delta_x\right)K(s;x,y)=0,
\qquad
K(0;x,y)=\frac{\delta^{(d)}(x-y)}{\sqrt g}.
$$

For $s>0$, the kernel $K(s;x,y)$ smears a delta function over a geodesic distance of order $\sqrt s$. Therefore small $s$ probes very short distances. UV divergences in a one-loop determinant are precisely short-distance divergences, so they appear as singularities of the proper-time integral near $s=0$.

The magic is that the short-distance expansion is local. At distances much shorter than the curvature radius, the heat kernel can only depend on local invariants built from the metric, the bundle curvature, and the potential terms in the operator. This gives a systematic geometric expansion.

In flat space, the heat kernel of $-\partial^2$ is

$$
K_0(s;x,y)=\frac{1}{(4\pi s)^{d/2}}\exp\left[-\frac{(x-y)^2}{4s}\right].
$$

On a curved manifold, the leading singularity is still the same local Gaussian, corrected by curvature. The coefficients of those corrections are the Seeley–DeWitt coefficients.

## Laplace-type operators

The cleanest heat-kernel formulas apply to Laplace-type operators. In this page, a Laplace-type operator has the form

$$
\Delta=-\left(g^{\mu\nu}D_\mu D_\nu+E\right),
$$

where $D_\mu$ is a covariant derivative acting on some vector bundle and $E$ is an endomorphism of that bundle. The bundle curvature is

$$
\Omega_{\mu\nu}=[D_\mu,D_\nu].
$$

For a scalar operator commonly written as

$$
\Delta=-\nabla^2+X,
$$

this convention corresponds to

$$
E=-X.
$$

For example, if

$$
\Delta=-\nabla^2+m^2+\xi R,
$$

one usually factors out $e^{-sm^2}$ and takes

$$
E=-\xi R.
$$

Different references choose different signs for $E$. This is not a physics issue, but it is a very efficient way to lose a minus sign. Always identify the operator convention before copying heat-kernel coefficients.

## The short-time expansion

For a smooth compact manifold without boundary, the traced heat kernel has the asymptotic expansion

$$
\operatorname{Tr}e^{-s\Delta}
\sim
\frac{1}{(4\pi s)^{d/2}}
\sum_{n=0}^\infty s^n A_{2n},
$$

where

$$
A_{2n}=\int d^d x\sqrt g\,\operatorname{tr}a_{2n}(x).
$$

The trace $\operatorname{tr}$ is over internal indices of the bundle on which $\Delta$ acts. The first coefficients for

$$
\Delta=-\left(g^{\mu\nu}D_\mu D_\nu+E\right)
$$

are

$$
a_0=\mathbf 1,
$$

and

$$
a_2=E+\frac16R\mathbf 1.
$$

The four-derivative coefficient is

$$
\begin{aligned}
a_4={}&
\frac{1}{360}\left(5R^2-2R_{\mu\nu}R^{\mu\nu}+2R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}\right)\mathbf 1
+\frac16 R E
+\frac12 E^2 \\
&+\frac{1}{12}\Omega_{\mu\nu}\Omega^{\mu\nu}
+\frac16\Box E
+\frac{1}{30}\Box R\,\mathbf 1.
\end{aligned}
$$

The total-derivative terms $\Box E$ and $\Box R$ can matter locally, with boundaries, or in trace-anomaly formulas, even though their integrals vanish on compact manifolds without boundary.

For a scalar operator $\Delta=-\nabla^2+\xi R$ with the above convention $E=-\xi R$, the second coefficient is

$$
a_2=\left(\frac16-\xi\right)R.
$$

This explains why the conformal coupling $\xi=1/6$ in four dimensions has special status for the $R$ term in a massless scalar determinant.

## From heat kernel to divergences

Consider a massive real scalar in four Euclidean dimensions,

$$
\Gamma_E^{(1)}=\frac12\operatorname{Tr}\log(\Delta+m^2)
=-\frac12\int_0^\infty\frac{ds}{s}\,e^{-sm^2}\operatorname{Tr}e^{-s\Delta}.
$$

Insert the heat-kernel expansion:

$$
\Gamma_E^{(1)}
\sim
-\frac12\frac{1}{(4\pi)^2}
\sum_{n=0}^\infty A_{2n}\int_0^\infty ds\,s^{n-3}e^{-sm^2}.
$$

The UV divergence comes from $s\to0$. In $d=4$:

| Coefficient | Proper-time behavior | Local term generated |
|---|---|---|
| $a_0$ | $s^{-3}$ in $ds$ integrand | cosmological term, $m^4\int\sqrt g$ |
| $a_2$ | $s^{-2}$ in $ds$ integrand | Einstein–Hilbert term, $m^2\int\sqrt g R$ plus source terms |
| $a_4$ | $s^{-1}$ in $ds$ integrand | logarithmic curvature-squared counterterms |
| $a_6$ and higher | finite for massive fields at one loop in four dimensions | higher-derivative finite EFT terms, suppressed by powers of $m$ |

With a hard proper-time cutoff $s\ge 1/\Lambda^2$, the first terms scale as powers and logarithms of $\Lambda$. In dimensional regularization, the logarithmic divergence appears as a pole, and massive terms combine with gamma functions to produce poles multiplying $m^4a_0$, $m^2a_2$, and $a_4$.

Thus in four dimensions, the local divergent part has the schematic form

$$
\Gamma_{\text{div}}^{(1)}
\sim
\frac{1}{(4\pi)^2}\frac{1}{\epsilon}
\int d^4x\sqrt g\,\operatorname{tr}\left(
\frac12m^4a_0-m^2a_2+a_4
\right),
$$

up to convention-dependent signs, overall factors, and whether $\Delta$ or $\Delta+m^2$ is used in the definition of $a_{2n}$. The invariant lesson is that only local invariants appear in the UV divergence.

## Why even-dimensional anomalies appear

In an even-dimensional classically Weyl-invariant theory, the logarithmic divergence is tied to the coefficient $a_d$. For $d=4$, this is $a_4$; for $d=2$, it is $a_2$; for $d=6$, it is $a_6$.

Renormalization introduces a scale $\mu$. Under a Weyl transformation, the logarithmic scale dependence cannot always be removed by a Weyl-invariant local counterterm. The leftover Weyl variation is the trace anomaly.

For example, in four dimensions, the coefficient $a_4$ contains curvature-squared terms. After organizing them into the Weyl tensor squared, Euler density, and total derivatives, one obtains the familiar schematic structure

$$
\langle T^\mu{}_\mu\rangle
=\frac{1}{(4\pi)^2}
\left(cC_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma}-aE_4+b\Box R\right).
$$

Heat-kernel coefficients therefore make the locality of the anomaly manifest. They do not, by themselves, explain every deep property of anomaly coefficients, but they give an efficient computation of the local density for free and one-loop systems.

## Worked example: conformally coupled scalar

For a real scalar in four dimensions,

$$
\Delta=-\nabla^2+\xi R.
$$

Using the convention

$$
\Delta=-\left(\nabla^2+E\right),
\qquad E=-\xi R,
$$

and no bundle curvature, $\Omega_{\mu\nu}=0$, the coefficient $a_2$ is

$$
a_2=\left(\frac16-\xi\right)R.
$$

For conformal coupling,

$$
\xi=\frac16,
$$

so $a_2=0$ when the mass is absent. This matches the idea that no scale-two local term is generated by a massless conformally coupled scalar in the simplest setting.

The coefficient $a_4$ is nonzero. It contains curvature-squared terms, and after removing scheme-dependent total derivatives and organizing the answer into conformal invariants, it gives the scalar contribution to the four-dimensional trace anomaly.

The moral is subtle but important:

$$
\text{conformal coupling removes the wrong lower-dimensional term, not the anomaly.}
$$

The anomaly is a logarithmic effect associated with the dimension-four coefficient $a_4$.

## Worked example: gauge or spinor fields

Fields with spin or gauge indices fit the same Laplace-type template after choosing the correct bundle and operator.

For a Dirac operator $\mathcal D=i\gamma^\mu\nabla_\mu$ in Euclidean signature, one squares it to obtain a Laplace-type operator. Schematically,

$$
\mathcal D^2=-\nabla^2+\frac14R
$$

up to sign and Euclidean gamma-matrix conventions. The spin connection contributes a bundle curvature

$$
\Omega_{\mu\nu}=\frac14R_{\mu\nu ab}\gamma^{ab}
$$

for spinors. Plugging $E$ and $\Omega_{\mu\nu}$ into $a_4$ gives curvature-squared terms and hence the spinor contribution to the trace anomaly.

For gauge fields, the story is more complicated because one must include gauge fixing and ghost determinants. The physical one-loop effective action is not the determinant of the gauge-field operator alone; ghosts and constraints are part of the answer. Heat-kernel methods remain powerful, but the input operator must be the full gauge-fixed quadratic fluctuation system.

## Boundary and zero-mode caveats

The formulas above are the clean bulk formulas for smooth manifolds without boundary. Boundaries change the expansion. Boundary terms appear with half-integer powers of $s$ and depend on boundary conditions. For example, Dirichlet, Neumann, Robin, and mixed boundary conditions produce different boundary heat-kernel coefficients.

Zero modes also require care. If $\Delta$ has zero eigenvalues, then $\log\det\Delta$ is not defined without separating the zero modes. One often writes

$$
\det{}'\Delta
$$

for the determinant over nonzero modes. The zero-mode integration is then handled separately, usually by collective-coordinate methods or by treating exact symmetries carefully.

Negative modes signal instability or saddle-point directions. They are common around tunneling configurations and gravitational instantons. A Euclidean determinant formula alone does not tell the whole physical story; one must also specify the contour and interpretation.

## Local expansion versus nonlocal effective action

The short-time heat-kernel expansion computes local UV data. It is not the full effective action. The exact determinant contains global and nonlocal information, including thresholds, long-distance logarithms, topology, boundary conditions, and state dependence.

For heavy fields, the local expansion is often enough at low energies:

$$
\Gamma_{\text{heavy}}[g]
=\int\sqrt g\left(
 c_0m^4+c_1m^2R+c_2R^2+c_3R_{\mu\nu}R^{\mu\nu}+\frac{c_4}{m^2}R^3+\cdots
\right).
$$

For massless fields, nonlocal terms such as

$$
R\log\frac{-\Box}{\mu^2}R
$$

are essential. The local heat-kernel coefficients determine the logarithmic scale dependence, but the full nonlocal form factor requires more than the short-time expansion. Covariant perturbation theory and spectral methods extend the heat-kernel idea to those nonlocal terms.

## Common pitfalls

**Copying coefficients without checking conventions.** The sign of $E$, the definition of the Riemann tensor, whether $m^2$ is factored out, and the normalization of the determinant all matter.

**Thinking $a_4$ is always the whole finite answer.** The coefficient $a_4$ controls local logarithmic UV data in four dimensions. It does not determine all finite nonlocal terms.

**Forgetting ghosts.** Gauge fields require gauge fixing and ghost determinants. Heat-kernel methods do not exempt you from gauge theory bookkeeping.

**Ignoring zero modes.** Determinants over operators with zero modes must be primed and supplemented by a separate treatment of collective coordinates or exact symmetries.

**Using Euclidean determinants as causal response functions.** Heat-kernel computations are usually Euclidean and local. Lorentzian causal response needs a Green-function prescription or Schwinger–Keldysh formulation.

**Treating boundary terms as optional.** If the manifold has a boundary, boundary heat-kernel coefficients and boundary counterterms are part of the renormalization problem.

## Relations to other pages

[Effective Action in Curved Spacetime](/renormalization-rg-eft/renormalization-curved-spacetime/effective-action-in-curved-spacetime/) explains the functional that contains the determinant. [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/) classifies the local invariants produced by $a_0$, $a_2$, and $a_4$. [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/) explains how logarithmic coefficients become Weyl anomalies.

The same technology also appears in [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/), [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/), [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/), and later pages on anomalies, index theory, and localization.

## Research status

The local bulk heat-kernel expansion for Laplace-type operators is a mature tool. It is used in curved-spacetime QFT, gravitational EFT, anomalies, spectral geometry, finite-temperature field theory, and one-loop matching.

Active refinements include nonminimal operators, higher-spin fields, manifolds with boundaries or defects, singular spaces and cones, Lorentzian heat kernels, nonequilibrium settings, nonlocal covariant perturbation theory, and efficient symbolic computation of high-order coefficients.

The conceptual boundary is that heat-kernel asymptotics is local. It explains UV counterterms beautifully, but it is not a substitute for understanding the global spectrum, the state, the contour, or the infrared physics.

## Exercises

### Exercise 1: Identify the UV-divergent coefficients in four dimensions

Using

$$
\operatorname{Tr}e^{-s\Delta}
\sim
\frac{1}{(4\pi s)^2}\left(A_0+sA_2+s^2A_4+s^3A_6+\cdots\right),
$$

show which terms can diverge in

$$
\int_0^\infty\frac{ds}{s}e^{-sm^2}\operatorname{Tr}e^{-s\Delta}
$$

as $s\to0$.

<details><summary><strong>Solution</strong></summary>

Insert the expansion. The terms behave near $s=0$ as

$$
\frac{ds}{s}\frac{1}{s^2}s^n
=ds\,s^{n-3}.
$$

The integral $\int_0 ds\,s^{n-3}$ diverges if $n-3\le -1$, or $n\le2$. Thus $A_0$, $A_2$, and $A_4$ can diverge in four dimensions. Terms beginning with $A_6$ are UV finite in this one-loop massive determinant.

</details>

### Exercise 2: Scalar $a_2$ coefficient

For

$$
\Delta=-\nabla^2+\xi R,
$$

use the convention

$$
\Delta=-\left(\nabla^2+E\right)
$$

to find $E$ and $a_2$.

<details><summary><strong>Solution</strong></summary>

Comparing

$$
-\nabla^2+\xi R
$$

with

$$
-\left(\nabla^2+E\right)=-\nabla^2-E,
$$

we find

$$
E=-\xi R.
$$

The general coefficient is

$$
a_2=E+\frac16R,
$$

so

$$
a_2=\left(\frac16-\xi\right)R.
$$

For $\xi=1/6$, this coefficient vanishes.

</details>

### Exercise 3: Why $a_4$ gives logarithmic divergences in four dimensions

Explain why $a_4$ is associated with logarithmic divergences in four dimensions, while $a_0$ and $a_2$ are associated with power divergences in a proper-time cutoff.

<details><summary><strong>Solution</strong></summary>

With a proper-time cutoff $s\ge1/\Lambda^2$, the relevant terms behave as

$$
A_0\int_{1/\Lambda^2}ds\,s^{-3}\sim A_0\Lambda^4,
$$

$$
A_2\int_{1/\Lambda^2}ds\,s^{-2}\sim A_2\Lambda^2,
$$

and

$$
A_4\int_{1/\Lambda^2}ds\,s^{-1}\sim A_4\log\Lambda^2.
$$

Thus $a_0$ and $a_2$ produce power divergences, while $a_4$ produces the logarithmic divergence in four dimensions.

</details>

### Exercise 4: Bundle curvature term

Suppose a field carries an internal gauge connection $A_\mu$, so that

$$
D_\mu=\nabla_\mu+A_\mu.
$$

What local invariant involving the bundle curvature appears in $a_4$?

<details><summary><strong>Solution</strong></summary>

The bundle curvature is

$$
\Omega_{\mu\nu}=[D_\mu,D_\nu].
$$

The coefficient $a_4$ contains

$$
\frac{1}{12}\Omega_{\mu\nu}\Omega^{\mu\nu}.
$$

After tracing over internal indices, this gives the local invariant

$$
\operatorname{tr}\Omega_{\mu\nu}\Omega^{\mu\nu}.
$$

For an ordinary gauge bundle, this is the heat-kernel origin of gauge-field kinetic counterterms and beta-function contributions in background-field computations.

</details>

## References

- B. S. DeWitt, *The Dynamical Theory of Groups and Fields*, and related Schwinger–DeWitt work.
- R. T. Seeley, papers on complex powers of elliptic operators.
- P. B. Gilkey, *Invariance Theory, the Heat Equation, and the Atiyah–Singer Index Theorem*.
- D. V. Vassilevich, "Heat Kernel Expansion: User's Manual."
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*.
- I. G. Avramidi, *Heat Kernel and Quantum Gravity*.
- A. O. Barvinsky and G. A. Vilkovisky, work on covariant perturbation theory.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional determinants and renormalization.

## Version history

- 2026-06-19: First polished draft. Added Laplace-type conventions, Seeley–DeWitt coefficients, divergence extraction, anomaly connection, examples, caveats, and exercises.
