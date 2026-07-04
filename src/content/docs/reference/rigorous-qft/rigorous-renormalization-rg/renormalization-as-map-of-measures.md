---
title: "Renormalization as a Map of Measures"
description: "Explains Wilsonian renormalization as an exact transformation of cutoff Euclidean measures, with pushforwards, Gaussian integration, rescaling, and fixed points."
sidebar:
  label: "RG as Measures"
  order: 1
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Glimm–Jaffe; Brydges; Polchinski"
topics:
  - renormalization group
  - Euclidean measures
  - constructive QFT
  - Wilsonian effective action
canonicalTopics:
  - rigorous-renormalization
  - euclidean-qft
  - measure-theoretic-rg
researchStatus:
  established:
    - "At finite cutoff, Wilsonian renormalization can be formulated as an exact transformation of probability measures or normalized densities."
  active:
    - "The difficult part is proving that an interacting family of cutoff measures has a nontrivial continuum limit after tuning relevant parameters."
---

## Summary

Renormalization can be read as a statement about **measures**, not only about counterterms. A cutoff Euclidean field theory gives a probability measure, or at least a normalized finite-dimensional approximation to one,

$$
d\nu_\Lambda(\phi)
= Z_\Lambda^{-1} e^{-V_\Lambda(\phi)}\,d\mu_{C_\Lambda}(\phi),
$$

where $d\mu_{C_\Lambda}$ is a Gaussian reference measure with cutoff covariance $C_\Lambda$. A Wilsonian RG step removes some short-distance degrees of freedom, rescales the remaining field, and produces a new measure

$$
\nu_\Lambda \longmapsto \mathcal R_b\nu_\Lambda .
$$

At finite cutoff this is an exact operation. The approximations enter later, when one tries to describe the transformed measure using a small list of local couplings.

The conceptual shift is important. Counterterms are not arbitrary repairs added after infinities appear. They are coordinates on a family of cutoff measures chosen so that observables have a limit as the cutoff is removed. In constructive QFT, this limit is a theorem to be proved. In perturbative QFT, it is usually proved order by order in formal power series. In Wilsonian physics, it is organized by flow near fixed points.

:::note[Main slogan]
A rigorous RG step is an exact identity for expectations of coarse observables:

$$
\int F(\psi)\,d(\mathcal R_b\nu)(\psi)
=
\int F(S_bB\phi)\,d\nu(\phi).
$$

Here $B$ is a blocking or projection map and $S_b$ rescales lengths and fields.
:::

## Prerequisites

You should know the Euclidean measure viewpoint from [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), the Gaussian examples in [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) and [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), and the cutoff language in [Ultraviolet Cutoffs](/rigorous-qft/path-integrals-as-measures/ultraviolet-cutoffs/). The companion page [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) explains the constructive-QFT target.

## Core idea

A cutoff QFT has only finitely many or controllably many degrees of freedom. For example, one may work on a finite lattice, in a finite-dimensional space of Fourier modes, or with a smooth ultraviolet cutoff. In that setting, the expression

$$
Z_\Lambda(J)
=
\int e^{\langle J,\phi\rangle} d\nu_\Lambda(\phi)
$$

is an honest integral. Renormalization asks whether there is a coordinated family of such measures, indexed by cutoffs, whose large-scale observables stabilize.

The operation called “integrating out high modes” is one way to compare these measures. It is not a metaphor at finite cutoff. It is a pushforward or conditional expectation. If the original field is split into a low-frequency field and a fluctuation,

$$
\phi = \phi_< + \zeta,
$$

then the high fluctuation $\zeta$ is integrated against its Gaussian law. The result is a new effective density for $\phi_<$. After rescaling the remaining field back to a standard cutoff, one gets a map on measures.

The RG is therefore a dynamical system, but its phase space is not just a finite-dimensional list of couplings. Its natural phase space is a space of measures, actions, or interactions. The familiar beta functions are finite-dimensional coordinates on this much larger map.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Renormalization as a map of measures](/figures/rigorous-qft/renormalization-map-of-measures.svg)

<figcaption>

A Wilsonian step can be written as an exact transformation of cutoff measures. The map first coarse-grains, then rescales, and finally rewrites the resulting law in effective-action coordinates.

</figcaption>
</figure>

## Setup and conventions

We use Euclidean signature in this page. A cutoff field space will be denoted by $E_\Lambda$. It may be finite-dimensional, such as fields on a finite lattice, or a regularized subspace of distributions. The cutoff measure has the schematic form

$$
d\nu_\Lambda(\phi)
= Z_\Lambda^{-1} e^{-V_\Lambda(\phi)}\,d\mu_{C_\Lambda}(\phi),
$$

where:

| Symbol | Meaning |
|---|---|
| $d\mu_{C_\Lambda}$ | centered Gaussian reference measure with covariance $C_\Lambda$ |
| $V_\Lambda$ | interaction, often local before RG and nonlocal after an exact step |
| $Z_\Lambda$ | normalization constant |
| $\Lambda$ | ultraviolet cutoff, lattice scale, or inverse short-distance scale |
| $\nu_\Lambda$ | normalized cutoff probability measure |

The phrase “density with respect to a Gaussian measure” is literal only after a reference measure has been chosen. In infinite dimensions, two Gaussian measures with different covariance may be mutually singular. Rigorous arguments avoid ambiguity by staying at finite cutoff, by using compatible Gaussian decompositions, or by working with characteristic functionals and projective limits.

## Coarse-graining as pushforward

Let

$$
B:E_\Lambda\longrightarrow E_{\Lambda/b}
$$

be a blocking map. For a lattice scalar field, $B$ might average the field over blocks of side length $b$. For a Fourier cutoff, $B$ might discard modes with momenta between $\Lambda/b$ and $\Lambda$.

The pushforward measure $B_*\nu_\Lambda$ is defined by

$$
(B_*\nu_\Lambda)(A)=\nu_\Lambda(B^{-1}A)
$$

for measurable sets $A\subset E_{\Lambda/b}$. Equivalently, for every bounded measurable observable $F$ of the coarse field,

$$
\int_{E_{\Lambda/b}}F(\psi)\,d(B_*\nu_\Lambda)(\psi)
=
\int_{E_\Lambda}F(B\phi)\,d\nu_\Lambda(\phi).
$$

This identity is the cleanest definition of an exact RG step. It says that the transformed measure reproduces the expectations of all observables that only see the blocked field.

After blocking, one usually rescales lengths and fields so that the cutoff returns to its original numerical value. If $S_b$ denotes this rescaling, define

$$
\mathcal R_b\nu_\Lambda=(S_bB)_*\nu_\Lambda.
$$

For a scalar field near a Gaussian fixed point in $d$ Euclidean dimensions, the engineering rescaling is

$$
(S_b\psi)(x)
= b^{\Delta_\phi}\psi(bx),
\qquad
\Delta_\phi=\frac{d-2}{2},
$$

possibly modified by an anomalous dimension at an interacting fixed point.

## Gaussian integration formula

For many rigorous constructions, the RG step is written using a Gaussian covariance decomposition. Suppose

$$
C=C_<+\Gamma,
$$

with $C_<$ and $\Gamma$ positive covariances. A Gaussian field with covariance $C$ can be represented in law as

$$
\phi_< + \zeta,
\qquad
\phi_<\sim \mu_{C_<},
\qquad
\zeta\sim\mu_\Gamma,
$$

with $\phi_<$ and $\zeta$ independent. If the original measure is

$$
d\nu(\phi)=Z^{-1}e^{-V(\phi)}\,d\mu_C(\phi),
$$

then integrating out the fluctuation gives an effective interaction $V'$ defined up to an additive constant by

$$
\begin{aligned}
e^{-V'(\phi_<)}
&= \frac{1}{Z_{\mathrm{step}}}
\int e^{-V(\phi_<+\zeta)}\,d\mu_\Gamma(\zeta), \\
d\nu'(\phi_<)
&= Z'^{-1}e^{-V'(\phi_<)}\,d\mu_{C_<}(\phi_<).
\end{aligned}
$$

This formula is exact. It is also the source of the main difficulty: even if $V$ is a simple local polynomial, $V'$ is generally a complicated nonlocal functional. Rigorous Wilsonian RG is the art of finding coordinates in which the important part of $V'$ is finite-dimensional and the remaining part is controlled.

### Example: Gaussian measures remain Gaussian

If $\nu=\mu_C$ is Gaussian and $A:E\to F$ is linear, then

$$
A_*\mu_C=\mu_{ACA^*}.
$$

Indeed, the characteristic functional of $A_*\mu_C$ is

$$
\begin{aligned}
\int e^{i\langle f,\psi\rangle}\,d(A_*\mu_C)(\psi)
&=\int e^{i\langle f,A\phi\rangle}\,d\mu_C(\phi)\\
&=\exp\left(-\frac12\langle A^*f,CA^*f\rangle\right)\\
&=\exp\left(-\frac12\langle f,ACA^*f\rangle\right).
\end{aligned}
$$

Thus the Gaussian fixed point is mathematically transparent: blocking and rescaling send a Gaussian measure to another Gaussian measure. Interactions are hard because they generate new terms at every scale.

## Actions are coordinates, not the measure itself

Physicists often write RG as a map on actions,

$$
S\longmapsto S'.
$$

This is useful but slightly coordinate-dependent. The measure is the invariant object. An action is a logarithm of a density relative to a reference measure:

$$
d\nu = Z^{-1}e^{-S}\,D\phi.
$$

In finite dimensions, this is harmless. In infinite dimensions, there is no translation-invariant Lebesgue measure $D\phi$ on the field space. A mathematically safer version is

$$
d\nu = Z^{-1}e^{-V}\,d\mu_C,
$$

where $d\mu_C$ supplies the Gaussian free-field part. Changing the covariance $C$, the normalization, or the field parametrization changes the interaction $V$ even when the underlying measure is the same.

This is why different exact RG equations can describe the same physics. Polchinski-type equations, Wegner–Houghton equations, Wetterich-type equations, and block-spin transformations use different coordinates on spaces of cutoff theories. Their universal fixed-point data should agree when the approximations are controlled.

## Fixed points and scaling fields

A fixed point of the normalized RG map is a measure $\nu_*$ satisfying

$$
\mathcal R_b\nu_* = \nu_*.
$$

The Gaussian free field is the basic example. Interacting fixed points, such as the Wilson–Fisher fixed point in dimensions below four, are much more difficult to construct rigorously.

Near a fixed point, one studies the linearized map. If $u$ is a coordinate on the space of perturbations, the linearized RG has the schematic form

$$
u_{n+1}=D\mathcal R_{\nu_*}\,\nu_n + O(\nu_n^2).
$$

Directions are classified by their eigenvalues under coarse-graining:

| Direction | RG behavior | Physical meaning |
|---|---|---|
| relevant | grows under flow to the infrared | must be tuned to reach a critical surface |
| marginal | neither grows nor decays at engineering level | requires nonlinear analysis |
| irrelevant | decays under flow to the infrared | affects short-distance details but not leading long-distance physics |

In measure language, tuning a relevant coupling means choosing a family of microscopic measures so that the sequence of renormalized measures remains near a desired fixed point for many scales.

## What renormalization proves

For a constructive continuum limit, one wants more than finite perturbative coefficients. A typical theorem has the following shape.

**Theorem schema.** For cutoffs $\Lambda$ and volumes $L$, choose bare parameters $g_\Lambda,m^2_\Lambda,z_\Lambda,\ldots$ in a specified way. Then the measures

$$
\nu_{\Lambda,L}
$$

have Schwinger functions that converge, after removing the volume and cutoff regulators, to distributions satisfying a chosen set of axioms or reconstruction hypotheses.

The RG proof strategy is to show that after each scale step,

$$
\mathcal R^n\nu_{\Lambda,L}
$$

stays inside a controlled domain of measures or interactions. Relevant couplings are tuned, marginal couplings are tracked, and irrelevant remainders are bounded by contraction estimates.

This is the point at which the word “rigorous” becomes expensive. The exact one-step identity is easy. The uniform control of infinitely many generated interactions across infinitely many scales is hard.

## Common pitfalls

**Mistaking a formal path integral for a measure.** The expression $e^{-S[\phi]}D\phi$ is not automatically a measure. It becomes a measure only after a field space, a sigma-algebra, a reference measure or projective construction, and a normalization procedure are specified.

**Thinking that RG is literally a group.** Coarse-graining loses microscopic information. The transformation is usually a semigroup, not an invertible group action. The name survives historically because scale transformations are invertible before coarse-graining is added.

**Identifying the effective action with the microscopic action.** Even if the microscopic action is local and polynomial, the exact effective action after one step generally contains nonlocal and infinitely many higher-order terms. Locality reappears as an approximation or theorem at long distances.

**Confusing bare parameters with observables.** Bare masses and couplings are coordinates used to define cutoff measures. Physical quantities are limits of correlation functions, scattering data when available, critical exponents, or other regulator-independent observables.

## Relations to other pages

The measure-theoretic viewpoint is developed from [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Cylinder Measures](/rigorous-qft/path-integrals-as-measures/cylinder-measures/), and [Minlos Theorem: Preview](/rigorous-qft/path-integrals-as-measures/minlos-theorem-preview/). The constructive target is described in [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) and [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/). The next page, [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/), explains how this exact map becomes a proof method.

## Research status

At finite cutoff, the measure-map formulation is settled mathematics: pushforwards, conditional expectations, Gaussian decompositions, and finite-dimensional integrals are standard objects.

For super-renormalizable low-dimensional models, constructive methods prove nontrivial continuum limits in important examples. For four-dimensional interacting scalar models, the main issue is not defining a cutoff measure but proving whether a nontrivial continuum limit exists; the expected answer for pure $\phi^4_4$ is tied to triviality. For four-dimensional Yang–Mills theory, the existence and mass-gap problem remains open.

For modern rigorous RG, the active problem is to build coordinate systems and norms strong enough to control the irrelevant directions while still flexible enough to treat realistic fields, symmetries, gauge constraints, and continuum limits.

## Exercises

### Exercise 1

Let $B:E\to F$ be a measurable map and $\nu$ a probability measure on $E$. Show that $B_*\nu$ is normalized and that

$$
\int_F F_0(\psi)\,d(B_*\nu)(\psi)
=
\int_E F_0(B\phi)\,d\nu(\phi)
$$

for every bounded measurable function $F_0$.

<details><summary><strong>Solution</strong></summary>

Normalization follows from

$$
(B_*\nu)(F)=\nu(B^{-1}F)=\nu(E)=1.
$$

The expectation identity is first true for indicator functions $F_0=\mathbf 1_A$ by definition:

$$
\int_F \mathbf 1_A(\psi)\,d(B_*\nu)(\psi)
=(B_*\nu)(A)
=\nu(B^{-1}A)
=\int_E \mathbf 1_A(B\phi)\,d\nu(\phi).
$$

Linearity extends it to simple functions, and bounded measurable functions follow by uniform approximation or the standard monotone-class argument.

</details>

### Exercise 2

Suppose $\phi_<\sim\mu_{C_<}$ and $\zeta\sim\mu_\Gamma$ are independent centered Gaussian fields. Show that $\phi_<+\zeta$ has covariance $C_<+\Gamma$.

<details><summary><strong>Solution</strong></summary>

For test functions $f$ and $g$,

$$
\begin{aligned}
\mathbb E\bigl[\langle f,\phi_<+\zeta\rangle
\langle g,\phi_<+\zeta\rangle\bigr]
&=\mathbb E\langle f,\phi_<\rangle\langle g,\phi_<\rangle
 +\mathbb E\langle f,\zeta\rangle\langle g,\zeta\rangle \\
&\quad +\mathbb E\langle f,\phi_<\rangle\langle g,\zeta\rangle
 +\mathbb E\langle f,\zeta\rangle\langle g,\phi_<\rangle .
\end{aligned}
$$

The cross terms vanish because the fields are independent and centered. The two remaining terms are $\langle f,C_<g\rangle$ and $\langle f,\Gamma g\rangle$, so the covariance is $C_<+\Gamma$.

</details>

### Exercise 3

In one finite-dimensional variable, let

$$
d\nu(x)=Z^{-1}e^{-\lambda x^4}\,d\mu_\sigma(x),
$$

where $d\mu_\sigma$ is the centered Gaussian law of variance $\sigma$. Split $x=y+\zeta$ with $\zeta$ Gaussian of variance $\gamma$. Write the exact effective interaction for $y$.

<details><summary><strong>Solution</strong></summary>

The effective interaction is defined, up to an additive constant, by

$$
e^{-V'(y)}=\frac{1}{Z_{\mathrm{step}}}
\int_{\mathbb R} e^{-\lambda (y+\zeta)^4}\,d\mu_\gamma(\zeta).
$$

Equivalently,

$$
V'(y)= -\log \mathbb E_\gamma
\left[e^{-\lambda (y+\zeta)^4}\right]
+\text{constant}.
$$

This formula is exact. Expanding the logarithm in powers of $\lambda$ produces a polynomial plus higher corrections. Even this one-variable example shows why exact RG does not merely keep the original monomial $x^4$.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–199. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- K. G. Wilson, “Renormalization Group and Critical Phenomena. I. Renormalization Group and the Kadanoff Scaling Picture,” *Physical Review B* **4** (1971) 3174–3183. [doi:10.1103/PhysRevB.4.3174](https://doi.org/10.1103/PhysRevB.4.3174).
- L. P. Kadanoff, “Scaling Laws for Ising Models Near $T_c$,” *Physics Physique Fizika* **2** (1966) 263–272. [doi:10.1103/PhysicsPhysiqueFizika.2.263](https://doi.org/10.1103/PhysicsPhysiqueFizika.2.263).
- F. J. Wegner and A. Houghton, “Renormalization Group Equation for Critical Phenomena,” *Physical Review A* **8** (1973) 401–412. [doi:10.1103/PhysRevA.8.401](https://doi.org/10.1103/PhysRevA.8.401).
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295. [doi:10.1016/0550-3213(84)90287-6](https://doi.org/10.1016/0550-3213(84)90287-6).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 2nd ed. (1987). [doi:10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- D. C. Brydges, “Lectures on the Renormalisation Group,” lecture notes. [PDF](https://personal.math.ubc.ca/~db5d/Seminars/PCMILectures/lectures.pdf).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).

## Version history

- 2026-06-30: First polished draft. Introduced finite-cutoff measures, pushforwards, Gaussian integration, fixed points, and the distinction between measures and action coordinates.
