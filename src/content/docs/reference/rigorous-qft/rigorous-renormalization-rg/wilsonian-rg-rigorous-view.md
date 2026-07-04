---
title: "Wilsonian RG: Rigorous View"
description: "Explains the rigorous Wilsonian renormalization group as a scale-by-scale integration scheme with covariance decompositions, local coordinates, irrelevant remainders, and stability estimates."
sidebar:
  label: "Wilsonian RG"
  order: 2
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Polchinski; Brydges; Bauerschmidt–Brydges–Slade"
topics:
  - Wilsonian renormalization group
  - exact RG
  - constructive renormalization
  - irrelevant operators
canonicalTopics:
  - wilsonian-rg
  - rigorous-renormalization
  - constructive-qft
researchStatus:
  established:
    - "Wilsonian RG can be formulated as an exact iterative integration of fluctuation fields at finite cutoff."
  active:
    - "Controlling the irrelevant remainder uniformly across scales is the central technical difficulty in rigorous applications."
---

## Summary

The Wilsonian RG is the scale-by-scale version of the measure map described in [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/). It starts from a cutoff theory, decomposes the covariance into scale pieces,

$$
C_N = C_1+C_2+\cdots+C_N,
$$

and integrates one fluctuation field at a time. If $Z_j(\phi)$ denotes the effective density after the first $j$ integrations, the exact step has the schematic form

$$
Z_{j+1}(\phi)
=\mathbb E_{C_{j+1}}
\bigl[Z_j(\phi+\zeta)\bigr].
$$

The step is exact. The hard part is rewriting $Z_{j+1}$ in useful coordinates and proving estimates on those coordinates.

In physics, one often summarizes this process by beta functions for finitely many couplings. In rigorous RG, that finite-dimensional flow is only the visible part. A complete step also contains an infinite-dimensional remainder, because integrating out a scale generates every interaction allowed by the cutoff. A proof must show that the local relevant and marginal coordinates are tracked accurately while the nonlocal or irrelevant remainder stays small.

:::note[Main distinction]
A perturbative Wilsonian calculation computes the flow of selected couplings. A rigorous Wilsonian argument also proves that all omitted terms are controlled in a norm strong enough to survive the next scale step.
:::

## Prerequisites

Read [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/) first. You should also know the Euclidean measure construction in [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), the role of cutoffs in [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/), and the constructive endpoint in [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

## Core idea

A Wilsonian proof replaces one impossible infinite-dimensional problem by many controlled finite-scale problems.

Instead of trying to define the continuum interacting measure in one step, choose a hierarchy of length scales. At each scale, integrate only the fluctuation field living at that scale. Then rewrite the result as

$$
\text{local coordinates} + \text{irrelevant remainder}.
$$

The local coordinates are the couplings that appear in a small list of local monomials: mass, coupling, field-strength renormalization, vacuum energy, and sometimes symmetry-allowed composite couplings. The irrelevant remainder records everything else. The rigorous claim is not that the remainder is zero. The claim is that it is contractive or summable after choosing the correct norm and after tuning the relevant directions.

This is why Wilson's physical picture is also a proof strategy. Universality comes from contraction in irrelevant directions. Critical tuning comes from the finite number of unstable directions. Nontriviality or triviality is decided by whether a controlled trajectory can be continued as the cutoff is removed.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Scale-by-scale Wilsonian RG](/figures/rigorous-qft/wilsonian-rg-flow.svg)

<figcaption>

A rigorous Wilsonian step integrates one scale of Gaussian fluctuation, extracts a local part, and estimates the remainder. The finite coupling flow is only one coordinate projection of the full exact map.

</figcaption>
</figure>

## Setup and conventions

We work in Euclidean signature with a scalar field for notation. Gauge theories and fermions require additional structure, but the scale logic is similar.

Let $\Lambda_N$ be a finite volume or lattice region at ultraviolet scale $N$. A typical cutoff partition function is written

$$
Z_N
=\int e^{-V_0(\phi)}\,d\mu_{C_N}(\phi),
$$

where $C_N$ has ultraviolet cutoff $N$. A multiscale covariance decomposition writes

$$
C_N=\sum_{j=1}^{N} C_j.
$$

If $\zeta_j$ are independent Gaussian fields with covariances $C_j$, then

$$
\phi\stackrel{\mathrm{law}}{=}
\zeta_1+\zeta_2+\cdots+\zeta_N.
$$

The RG integrates the variables $\zeta_j$ progressively. Depending on convention, $j$ may count from the ultraviolet to the infrared or the reverse. The essential point is that each $C_j$ is localized near one range of distances.

A finite-range decomposition is especially useful in rigorous work: $C_j(x,y)$ vanishes when $x$ and $y$ are separated by much more than the scale $j$. This makes locality estimates possible after each integration.

## The exact one-step map

Define the initial density

$$
Z_0(\phi)=e^{-V_0(\phi)}.
$$

One RG step integrates a fluctuation $\zeta$ with covariance $C_{j+1}$:

$$
Z_{j+1}(\phi)
=\mathbb E_{C_{j+1}}
\left[Z_j(\phi+\zeta)\right].
$$

This identity is exact at finite cutoff. It is often called Gaussian convolution. If one writes $Z_j=e^{-V_j}$, then

$$
V_{j+1}(\phi)
=-\log \mathbb E_{C_{j+1}}
\left[e^{-V_j(\phi+\zeta)}\right]
$$

up to an additive constant. This formula already shows the main complication: the logarithm of an averaged exponential is a cumulant-generating operation. It creates new interactions.

For example, if $V_j$ contains a local $\phi^4$ term, then $V_{j+1}$ contains corrections to $\phi^2$, $\phi^4$, derivative terms, higher powers of $\phi$, and nonlocal terms. Perturbation theory chooses a few of these terms and computes their coefficients. Rigorous RG also bounds the rest.

## Local coordinates and remainders

A typical scalar local coordinate system has the schematic form

$$
V_j(X,\phi)
=\int_X
\left(
\frac12 z_j |\nabla\phi|^2
+\frac12 m_j^2\phi^2
+\frac{g_j}{4!}\phi^4
+e_j
\right)dx,
$$

where $X$ is a region at scale $j$. This local polynomial is not the whole effective interaction. One writes, schematically,

$$
Z_j(\Lambda,\phi)
\approx e^{-V_j(\Lambda,\phi)}\,\bigl(1+K_j(\Lambda,\phi)\bigr),
$$

or more precisely as a polymer expansion involving factors $K_j(X,\phi)$ attached to connected scale-$j$ polymers $X$.

The role of $K_j$ is crucial. It contains the irrelevant, nonlocal, and higher-order information not kept in the local polynomial. The RG step becomes a map

$$
(V_j,K_j)
\longmapsto
(V_{j+1},K_{j+1}).
$$

The extraction of $V_{j+1}$ from the exact output is partly a choice of coordinates. Different extraction schemes give different beta functions away from fixed points, but universal critical data should not depend on this choice once the construction is controlled.

## Scaling and relevance

Near the Gaussian fixed point, relevance can be read from engineering dimensions. In $d$ Euclidean dimensions, the free scalar field has engineering dimension

$$
\Delta_\phi=\frac{d-2}{2}.
$$

A local operator $\mathcal O$ of dimension $\Delta_{\mathcal O}$ coupled as

$$
\int d^dx\,g_{\mathcal O}\mathcal O(x)
$$

has coupling dimension

$$
[g_{\mathcal O}]=d-\Delta_{\mathcal O}.
$$

Under a length rescaling by $b>1$, the linearized coupling scales as

$$
g_{\mathcal O}\longmapsto b^{d-\Delta_{\mathcal O}}g_{\mathcal O}.
$$

This gives the first classification:

| Operator | Coupling dimension | Classification near Gaussian fixed point |
|---|---:|---|
| $1$ | $d$ | relevant, vacuum energy coordinate |
| $\phi^2$ | $2$ | relevant, mass coordinate |
| $(\nabla\phi)^2$ | $0$ | marginal, field normalization coordinate |
| $\phi^4$ | $4-d$ | marginal in $d=4$, relevant in $d<4$, irrelevant in $d>4$ |
| $\phi^6$ | $6-2d$ | marginal in $d=3$, irrelevant in $d>3$ |

This table is not the whole story. Marginal directions are decided by nonlinear terms. At an interacting fixed point, anomalous dimensions modify the scaling dimensions. Still, the table explains why a small number of couplings dominates the long-distance problem.

## What a rigorous RG proof must control

A Wilsonian proof typically has the following architecture.

| Step | Mathematical task | Why it matters |
|---:|---|---|
| 1 | Define finite-volume, finite-cutoff measures. | Avoids undefined path-integral expressions. |
| 2 | Decompose the covariance into scale pieces. | Turns one continuum problem into many scale problems. |
| 3 | Integrate one Gaussian fluctuation field. | Gives the exact RG map. |
| 4 | Extract local coordinates. | Produces the finite-dimensional coupling flow. |
| 5 | Bound the remainder in a scale-sensitive norm. | Prevents generated interactions from accumulating uncontrollably. |
| 6 | Tune relevant parameters. | Keeps the flow near a critical trajectory. |
| 7 | Take volume and cutoff limits. | Produces continuum Schwinger functions or a limiting measure. |

The fifth step is the technical heart. The norm must be strong enough to control large fields, derivatives, combinatorics of polymers, and accumulation over many scales. It must also be weak enough that the RG map is contractive in irrelevant directions.

## Relation to beta functions

The beta function is a coordinate description of how selected couplings change with scale. For example, near four dimensions a scalar quartic coupling has the schematic perturbative form

$$
\beta_g = -\epsilon g + A g^2 + O(g^3),
\qquad \epsilon=4-d,
$$

where $A$ depends on normalization and field content. The competition between the engineering term $-\epsilon g$ and the one-loop term $A g^2$ gives the Wilson–Fisher fixed point in perturbation theory.

The rigorous Wilsonian picture refines this statement. It asks for a controlled map

$$
(g_j,m_j^2,z_j,K_j)
\mapsto
(g_{j+1},m_{j+1}^2,z_{j+1},K_{j+1}),
$$

where the coupling part agrees with the perturbative beta function to the required order and $K_j$ remains bounded. Without the $K_j$ estimate, a beta function is a calculation, not a construction.

## Why locality survives

Exact integration over short modes creates nonlocal terms. Wilsonian locality says that these nonlocalities are weak at long distances when the original theory has local interactions and the covariance decomposition is local in scale.

The heuristic reason is clustering. Short-distance fluctuations can connect nearby points efficiently, but their influence over widely separated regions is suppressed. A finite-range covariance decomposition makes this statement literal: one-scale fluctuation fields only connect points within a bounded multiple of that scale. Polymer expansions then organize the remaining connected effects.

This is the rigorous version of the physicist's statement that integrating out high momenta produces a local effective action expanded in powers of derivatives and fields.

## A small finite-dimensional model

Let $x=y+\zeta$, where $\zeta$ is a centered Gaussian variable. Suppose

$$
V(x)=\frac{m^2}{2}x^2+\frac{g}{4!}x^4.
$$

The exact one-step potential for $y$ is

$$
V'(y)=-\log\mathbb E_\zeta
\left[\exp\left(-\frac{m^2}{2}(y+\zeta)^2
-\frac{g}{4!}(y+\zeta)^4\right)\right]
+\text{constant}.
$$

For small $g$, expanding the logarithm produces a correction to the constant term, a correction to $y^2$, a correction to $y^4$, and higher corrections at order $g^2$ and beyond. In a field theory, the same mechanism occurs at every scale and at every point, with spatial dependence and locality estimates added.

The finite-dimensional model is too simple to prove universality, but it teaches the correct lesson: the Wilsonian map is exact before truncation and approximate only after selecting coordinates.

## Common pitfalls

**Calling every cutoff flow a rigorous RG.** A flow equation can be exact and still not be a rigorous construction of a continuum QFT. The proof also needs existence, estimates, and convergence.

**Dropping irrelevant operators without a norm.** Power counting says irrelevant operators decay at linear order. A proof must show that nonlinear terms, combinatorics, and large-field regions do not make the discarded terms grow.

**Treating marginal directions as decided by dimensional analysis.** Marginal means undecided at engineering level. The sign and structure of nonlinear terms determine whether the direction is marginally relevant, marginally irrelevant, or exactly marginal.

**Confusing Wilsonian and one-particle-irreducible effective actions.** The Wilsonian effective action changes with a cutoff and describes partially integrated fields. The 1PI effective action is a Legendre transform of the connected generating functional. They are related but not identical.

**Expecting one universal beta function away from fixed points.** Coupling flows depend on coordinates and schemes. Universal quantities include critical exponents, scaling dimensions, operator algebra data, and properly normalized continuum observables.

## Relations to other pages

This page supplies the rigorous language behind [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) and the constructive examples in [Phi-Four Two](/rigorous-qft/constructive-qft/phi-four-two/) and [Phi-Four Three](/rigorous-qft/constructive-qft/phi-four-three/). It also explains why [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) and [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/) are not optional technicalities: they are ways to control the remainder left by exact integration.

Later pages in this chapter will turn this viewpoint into more specific tools: scaling limits, relevant and irrelevant directions, fixed points, polymer expansions, multiscale analysis, and renormalization of composite fields.

## Research status

The Wilsonian RG is a mature conceptual framework, and exact finite-cutoff RG identities are standard. Rigorous implementations exist for important constructive and statistical-mechanical models, especially in settings where covariance decompositions, polymer expansions, correlation inequalities, or supersymmetric representations provide sufficient control.

The frontier is not the slogan “integrate out short distances.” The frontier is proving uniform estimates in models with the full complications of continuum spacetime, gauge symmetry, fermions, massless fields, topological sectors, or four-dimensional interacting limits. In four dimensions, scalar $\phi^4$ is expected to be trivial in the continuum limit, while non-Abelian Yang–Mills existence and mass gap remains an open problem.

## Exercises

### Exercise 1

Let $\zeta_1$ and $\zeta_2$ be independent centered Gaussian fields with covariances $C_1$ and $C_2$. Show that integrating them one at a time is the same as integrating their sum.

<details><summary><strong>Solution</strong></summary>

The sum $\zeta_1+\zeta_2$ is centered Gaussian with covariance $C_1+C_2$. For any bounded measurable function $F$,

$$
\mathbb E_{C_1}\mathbb E_{C_2}
F(\phi+\zeta_1+\zeta_2)
=
\mathbb E_{C_1+C_2}F(\phi+\zeta).
$$

This is immediate from characteristic functionals. It is the probabilistic reason why a multiscale covariance decomposition gives an exact iterative integration scheme.

</details>

### Exercise 2

Using $\Delta_\phi=(d-2)/2$, classify $\phi^4$ as relevant, marginal, or irrelevant near the Gaussian fixed point in $d=2,3,4,5$.

<details><summary><strong>Solution</strong></summary>

The operator $\phi^4$ has engineering dimension

$$
\Delta_{\phi^4}=4\Delta_\phi=2(d-2).
$$

The coupling dimension is

$$
[g]=d-2(d-2)=4-d.
$$

Therefore $\phi^4$ is relevant for $d=2,3$, marginal for $d=4$, and irrelevant for $d=5$ near the Gaussian fixed point. Marginality in $d=4$ is only the engineering statement; nonlinear RG decides the actual flow.

</details>

### Exercise 3

Explain why the exact Wilsonian effective action after integrating one scale is generally not a local polynomial, even if the original microscopic action is.

<details><summary><strong>Solution</strong></summary>

The exact step is

$$
V'(\phi)=-\log\mathbb E_C\left[e^{-V(\phi+\zeta)}\right]
+\text{constant}.
$$

The logarithm produces connected cumulants of $V(\phi+\zeta)$. In a field theory, these cumulants connect different spacetime points through the covariance of $\zeta$. Thus the result contains nonlocal terms and arbitrarily high powers of the field. Local polynomial truncations are useful because short-range covariances and power counting make many of these terms irrelevant, not because the exact step preserves polynomial locality.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–199. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- F. J. Wegner and A. Houghton, “Renormalization Group Equation for Critical Phenomena,” *Physical Review A* **8** (1973) 401–412. [doi:10.1103/PhysRevA.8.401](https://doi.org/10.1103/PhysRevA.8.401).
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295. [doi:10.1016/0550-3213(84)90287-6](https://doi.org/10.1016/0550-3213(84)90287-6).
- T. R. Morris, “The Exact Renormalization Group and Approximate Solutions,” *International Journal of Modern Physics A* **9** (1994) 2411–2450. [doi:10.1142/S0217751X94000972](https://doi.org/10.1142/S0217751X94000972), [arXiv:hep-ph/9308265](https://arxiv.org/abs/hep-ph/9308265).
- O. J. Rosten, “Fundamentals of the Exact Renormalization Group,” *Physics Reports* **511** (2012) 177–272. [doi:10.1016/j.physrep.2011.12.003](https://doi.org/10.1016/j.physrep.2011.12.003), [arXiv:1003.1366](https://arxiv.org/abs/1003.1366).
- D. C. Brydges, “Lectures on the Renormalisation Group,” lecture notes. [PDF](https://personal.math.ubc.ca/~db5d/Seminars/PCMILectures/lectures.pdf).
- D. C. Brydges and G. Slade, “A Renormalisation Group Method. V. A Single Renormalisation Group Step.” [arXiv:1403.7256](https://arxiv.org/abs/1403.7256).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).

## Version history

- 2026-06-30: First polished draft. Explained scale decomposition, exact Gaussian integration, local coordinates, irrelevant remainders, and the proof obligations of rigorous Wilsonian RG.
