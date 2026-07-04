---
title: "Scaling Limits"
description: "Explains scaling limits of cutoff quantum field theories as convergence of rescaled observables, Schwinger functions, measures, or local algebras."
sidebar:
  label: "Scaling Limits"
  order: 3
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Kadanoff; Osterwalder–Schrader; Buchholz–Verch; constructive RG literature"
topics:
  - scaling limits
  - continuum limits
  - critical phenomena
  - rigorous renormalization
canonicalTopics:
  - scaling-limits
  - rigorous-renormalization
  - constructive-qft
researchStatus:
  established:
    - "Scaling limits can be formulated as convergence of rescaled correlation functions, measures, or nets of local observables."
  active:
    - "For many physically central interacting four-dimensional theories, proving existence, uniqueness, and nontriviality of a scaling limit remains open."
---

## Summary

A scaling limit is the limit of a family of cutoff theories after distances, fields, and couplings have been rescaled so that a finite macroscopic theory remains. It is the mathematical version of the slogan

$$
\text{continuum QFT}
=\lim_{a\to 0}
\text{properly rescaled cutoff theory at scale }a.
$$

Here $a$ may be a lattice spacing, ultraviolet cutoff length, mollifier scale, or inverse momentum cutoff. The word “properly” is the entire problem. One must usually tune relevant couplings, multiply fields by renormalization factors, take infinite-volume limits in the right order, and prove convergence in a topology appropriate to correlation functions, probability measures, or local algebras.

For Euclidean scalar models, a common formulation is convergence of smeared fields. Given cutoff fields $\phi_a$ on $a\mathbb Z^d$ or on a regularized continuum, define

$$
\Phi_a(f)
=Z_a^{1/2}a^d\sum_{x\in a\mathbb Z^d}
f(x)\phi_a(x),
$$

or the analogous continuum integral. A scaling limit is a collection of random distributions $\Phi$ such that, for suitable test functions,

$$
\lim_{a\to 0}
\mathbb E_a\!\left[
\Phi_a(f_1)\cdots\Phi_a(f_n)
\right]
=
\mathbb E\!\left[
\Phi(f_1)\cdots\Phi(f_n)
\right].
$$

The limit is a QFT only after additional positivity, covariance, locality, and regularity properties are verified. A convergent sequence of numbers is not automatically a quantum field theory.

## Prerequisites

Read [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/) and [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) first. You should also know [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/), [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/), and [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/).

The page uses Euclidean notation by default. Lorentzian theories can be obtained from Euclidean scaling limits only when the required Osterwalder–Schrader hypotheses hold.

## Core idea

A cutoff theory has microscopic length $a$. A continuum limit asks what remains when $a\to 0$. A scaling limit asks a more precise question: choose observables whose physical size is held fixed while their microscopic description uses more and more degrees of freedom, and ask whether their joint laws converge.

The simplest mental picture is a microscope with adjustable magnification. If a lattice spacing is $a$, then a physical ball of radius $R$ contains roughly $(R/a)^d$ lattice sites. As $a\to 0$, the microscopic description becomes infinite-dimensional inside any fixed macroscopic region. A scaling limit is the statement that the large number of microscopic variables has a stable continuum description.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Scaling-limit window](/figures/rigorous-qft/scaling-limit-window.svg)

<figcaption>

A scaling limit holds a physical observation window fixed while the cutoff $a$ is removed. Couplings are tuned, fields are rescaled, and correlation functions are required to converge as distributions.

</figcaption>
</figure>

This is not the same as merely taking a large box. There are at least three limiting operations that are often intertwined:

| Limit | Informal meaning | What can go wrong |
|---|---|---|
| Thermodynamic limit | Volume $\Lambda\nearrow\mathbb R^d$ at fixed cutoff. | Infinite volume may not exist or may depend on boundary conditions. |
| Continuum cutoff removal | $a\to 0$ at fixed physical normalization. | Observables may diverge, vanish, or become trivial. |
| Critical scaling limit | $a\to 0$ while correlation length in lattice units diverges. | Relevant couplings must be tuned; the limit may be Gaussian or nonexistent. |

The renormalization group exists because these limits are delicate. It supplies coordinates in which divergence, convergence, and universality can be separated.

## Setup and conventions

Let $a>0$ denote a short-distance cutoff. A family of cutoff Euclidean theories may be described by probability measures

$$
\mu_a
\quad\text{on fields}\quad
\phi_a,
$$

or by finite-dimensional distributions of local observables. The expectation with respect to $\mu_a$ is written $\mathbb E_a$.

A local microscopic field $\phi_a(x)$ rarely has a finite pointwise limit. Instead one smears and rescales. In the lattice notation,

$$
\Phi_a(f)
=Z_a^{1/2}a^d
\sum_{x\in a\mathbb Z^d}f(x)\phi_a(x),
\qquad f\in C_c^\infty(\mathbb R^d).
$$

The factor $a^d$ converts a sum into an integral. The factor $Z_a^{1/2}$ is a field-strength renormalization or scaling normalization. In statistical mechanics notation one often writes

$$
Z_a^{1/2}\sim a^{-\Delta_\phi},
$$

so that the scaled field behaves like an operator of scaling dimension $\Delta_\phi$.

For composite fields one needs separate normalizations and subtractions. A cutoff monomial such as $\phi_a(x)^2$ may require a definition like

$$
:\!\phi_a^2\!:(x)
=
\phi_a(x)^2-\mathbb E_a[\phi_a(x)^2]
$$

in a Gaussian or perturbative setting, and more elaborate renormalization in interacting settings. The notation $:\!\cdots\!:$ should be read as a construction, not a decoration.

## Scaling limits of correlation functions

The most common Euclidean definition uses correlation functions as distributions. Define the cutoff $n$-point Schwinger functional

$$
S_{n,a}(f_1,\ldots,f_n)
=
\mathbb E_a\!\left[
\Phi_a(f_1)\cdots\Phi_a(f_n)
\right].
$$

A scaling limit of these fields is a family of distributions $S_n$ such that

$$
S_{n,a}(f_1,\ldots,f_n)
\longrightarrow
S_n(f_1,\ldots,f_n)
$$

for all test functions in a specified class. In a strong version, the convergence is joint convergence of random distributions; in a weaker version, only moments converge.

For translation-invariant scalar theories, one often writes unsmeared notation,

$$
\lim_{a\to 0}
Z_a^{n/2}
\left\langle
\phi_a(x_1)\cdots\phi_a(x_n)
\right\rangle_a
=
\left\langle
\phi(x_1)\cdots\phi(x_n)
\right\rangle,
$$

but this is shorthand. The honest statement is distributional away from coincident points, or fully distributional after composite-field renormalization.

A useful diagnostic is the two-point function. Suppose that at criticality the lattice two-point function has asymptotic behavior

$$
\left\langle \phi_x\phi_y\right\rangle
\sim
\frac{C}{|x-y|^{2\Delta_\phi}}
\qquad |x-y|\to\infty.
$$

Writing $x=X/a$ and $y=Y/a$, one obtains

$$
\left\langle \phi_{X/a}\phi_{Y/a}\right\rangle
\sim
C\,a^{2\Delta_\phi}|X-Y|^{-2\Delta_\phi}.
$$

Thus a nonzero continuum two-point function requires the rescaled field

$$
\Phi_a(X)\sim a^{-\Delta_\phi}\phi_{X/a}.
$$

This heuristic is one of the simplest ways anomalous dimensions enter scaling limits.

## Critical tuning and correlation length

Away from criticality, a lattice model often has a finite correlation length $\xi_{\mathrm{lat}}$ in lattice units. If $a\to 0$ while $\xi_{\mathrm{lat}}$ stays bounded, the physical correlation length

$$
\xi_{\mathrm{phys}}=a\,\xi_{\mathrm{lat}}
$$

goes to zero. The limiting theory is usually trivial at macroscopic distances. To obtain a continuum theory with finite or infinite physical correlation length, one must tune couplings $g(a)$ so that

$$
\xi_{\mathrm{lat}}(g(a))\to\infty.
$$

Two common regimes are:

| Regime | Scaling requirement | Typical limit |
|---|---|---|
| Massive continuum limit | $a\xi_{\mathrm{lat}}(g(a))\to m^{-1}$ | Nonzero mass scale remains. |
| Critical continuum limit | $a\xi_{\mathrm{lat}}(g(a))\to\infty$ | Scale-invariant or conformal candidate. |

In RG language, $g(a)$ must approach the critical surface. Relevant directions are the couplings that must be tuned. Irrelevant directions may affect lattice-scale details but should disappear from the universal scaling limit if the RG estimates are strong enough.

This is why “continuum limit” and “critical point” are not synonyms. One may construct a massive continuum QFT by tuning toward a critical point while keeping a finite renormalized mass. Conversely, a statistical critical point may have a scaling limit that is not yet proved to satisfy the full axioms expected of a relativistic QFT.

## Scaling limit as an RG trajectory

Let $\mathcal R_b$ be an RG transformation that coarse-grains by a factor $b>1$ and rescales back to the original unit lattice. A fixed point satisfies

$$
\mathcal R_b(\mu_*)=\mu_*.
$$

A scaling limit is controlled by the behavior of $\mathcal R_b^k(\mu_a)$ for large $k$. If the cutoff is $a=b^{-N}$, then probing a fixed physical scale corresponds to applying roughly $N$ RG steps. A nontrivial scaling limit requires that the sequence of effective theories approaches a controlled trajectory near a fixed point or renormalized trajectory.

The schematic relation is

$$
\text{cutoff family }\mu_{a,g(a)}
\xrightarrow{\;\mathcal R_b^{\log_b(1/a)}\;}
\text{finite macroscopic law}.
$$

Near a fixed point, the RG decomposes perturbations into relevant, marginal, and irrelevant directions. The next page develops this classification. For scaling limits, the practical consequence is simple:

| Direction | Scaling-limit role |
|---|---|
| Relevant | Must be tuned as $a\to 0$ to avoid running away. |
| Irrelevant | Should be forgotten in the limit, up to corrections to scaling. |
| Marginal | Requires nonlinear analysis; may generate logarithms. |

A rigorous proof must turn this table into estimates. It is not enough to say that irrelevant terms shrink by dimensional analysis. One must choose a norm in which the exact remainder shrinks after the generated local terms have been extracted.

## Scaling limits of measures

Correlation-function convergence is often the most economical formulation, but it is not the only one. If the fields are random distributions, one can ask for convergence in law

$$
\Phi_a\Rightarrow \Phi
$$

in a distribution space such as $\mathcal S'(\mathbb R^d)$ or $\mathcal D'(\mathbb R^d)$, possibly after restricting to finite volumes and then taking volume limits. This is stronger than pointwise convergence of moments when it includes tightness.

A typical measure-level proof has three parts.

First, prove tightness or compactness for the sequence of laws. This prevents mass from escaping to infinity in distribution space.

Second, identify all subsequential limits by their correlation functions, Markov property, symmetries, Schwinger–Dyson equations, or RG fixed-point equation.

Third, prove uniqueness of the limit or classify the possible limits. Without uniqueness, a model may have several scaling limits depending on boundary conditions, phases, or tuning paths.

Measure convergence is natural in constructive QFT and probability. It also makes clear why formal path integrals are insufficient: a density written as $e^{-S}$ must define a family of probability measures before there is a measure to converge.

## Scaling limits of local algebras

In algebraic QFT, the fundamental objects are local algebras rather than random fields. A net assigns an algebra $\mathcal A(O)$ to each spacetime region $O$. A scaling limit then asks how the net behaves under shrinking regions.

Very schematically, one studies families of observables

$$
\lambda\longmapsto A_\lambda,
\qquad A_\lambda\in\mathcal A(\lambda O),
$$

as $\lambda\to 0$. The scaling algebra collects such families with suitable continuity and boundedness conditions. States on the original theory induce states on the scaling algebra, and limiting states describe possible short-distance theories.

This approach has two advantages.

First, it does not require a preferred field coordinate. Local observables are primary, and fields can be recovered as affiliated or pointlike objects when possible.

Second, it makes non-uniqueness visible. A theory may have several scaling-limit states. This is not a failure of the definition; it is information about the short-distance structure.

The algebraic scaling-limit language is especially useful for comparing rigorous Lorentzian QFT with the Euclidean measure language. Both are trying to answer the same question: what remains of the theory when one zooms into arbitrarily small distances?

## What a scaling-limit proof must show

A high-quality scaling-limit proof normally contains the following ingredients.

| Ingredient | What it proves |
|---|---|
| Uniform ultraviolet estimates | Smeared fields or observables do not blow up uncontrollably as $a\to 0$. |
| Tightness or compactness | Subsequential continuum limits exist. |
| Identification | Every limit satisfies the intended equations, symmetries, or axioms. |
| Positivity | The limit gives a Hilbert-space theory after reconstruction, when Euclidean. |
| Locality or Markov/local structure | The limit has the intended causal or spatial locality. |
| Nontriviality | The limiting correlations are not all Gaussian or zero unless that is the intended result. |
| Universality | The same limit is obtained for a class of microscopic regularizations. |

Different frameworks emphasize different rows. Constructive field theory often proves Schwinger functions satisfying OS axioms. Probability-oriented scaling limits often prove convergence of random distributions. Algebraic QFT often studies limiting nets or states. Lattice statistical mechanics may first prove conformally invariant or SLE-type limits for selected observables.

## Examples and non-examples

The Gaussian free field is the basic example. A lattice free field with covariance approaching

$$
C=(-\Delta+m^2)^{-1}
$$

has a scaling limit as a Gaussian random distribution. The two-point function determines all higher moments by Wick's theorem. This is why the free field is the standard test case for every definition.

Super-renormalizable two-dimensional scalar models provide interacting constructive examples. In $P(\phi)_2$ models, Wick ordering and estimates produce Euclidean measures whose Schwinger functions satisfy the axioms under suitable hypotheses. These are genuine interacting scaling limits.

The four-dimensional $\phi^4$ story is a warning. Perturbation theory suggests a renormalized continuum limit order by order, but constructive and RG evidence points toward triviality for the pure scalar theory under broad hypotheses. Thus a formal continuum Lagrangian does not by itself establish a nontrivial scaling limit.

Yang–Mills theory in four dimensions is the central open example. Lattice gauge theory gives a powerful regularized formulation, and physics strongly expects a continuum quantum theory with a mass gap in pure non-Abelian Yang–Mills. A complete mathematical construction satisfying the required axioms remains a major open problem.

## Common pitfalls

| Pitfall | Correction |
|---|---|
| “Letting $a\to 0$ automatically gives a continuum field.” | Without rescaling and tuning, fields may diverge, vanish, or converge to a trivial limit. |
| “The scaling limit is a pointwise limit of fields.” | Fields are distributions; the honest limit is usually smeared or distributional. |
| “A divergent correlation length is enough.” | One also needs normalization, tightness, locality, and positivity properties. |
| “A beta function proves the scaling limit.” | A beta function is a coordinate calculation; a proof needs estimates on the full cutoff theory. |
| “Universality means microscopic details never matter.” | Microscopic details can affect relevant tuning, normalization, boundary conditions, and corrections to scaling. |
| “A conformal scaling limit is automatic at criticality.” | Scale and conformal invariance require additional hypotheses and are not automatic in every mathematical setting. |

## Relations to other pages

[Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/) explains the measure-theoretic background. This page adds the RG and critical-scaling viewpoint.

[Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) explains the scale-by-scale integration mechanism that can prove convergence. The present page describes the target of that mechanism.

[Relevant, Irrelevant, and Marginal Directions](/rigorous-qft/rigorous-renormalization-rg/relevant-irrelevant-and-marginal-directions/) explains why only finitely many parameters often need to be tuned in a continuum limit.

[OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains how Euclidean scaling-limit Schwinger functions become a Lorentzian Wightman theory when the OS axioms are satisfied.

[What Is Open in Four Dimensions](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/) records why the physically most important four-dimensional scaling limits remain difficult.

## Research status

**Established.** Scaling limits are a precise mathematical concept in several frameworks: convergence of Schwinger functions, convergence of Euclidean random distributions, convergence of lattice observables, and algebraic scaling limits. Free fields and many low-dimensional interacting models provide rigorous examples.

**Technically mature in selected models.** Constructive and rigorous RG methods can prove scaling behavior and continuum limits for important super-renormalizable and critical models. The technical heart is uniform multiscale control, not formal manipulation of the action.

**Open in central four-dimensional theories.** The existence of nontrivial continuum scaling limits for many physically central four-dimensional interacting QFTs is not known at the level expected by axiomatic or constructive frameworks. Yang–Mills existence and mass gap is the flagship example.

**Framework-dependent.** A Euclidean probability scaling limit, an algebraic scaling limit, and a perturbative renormalized limit are related but not identical statements. A precise page should always say which topology and which observables are converging.

## Exercises

### Exercise 1. Field normalization from the two-point function

Suppose a lattice field $\phi_x$ at criticality satisfies

$$
\langle\phi_x\phi_y\rangle
\sim |x-y|^{-2\Delta}
\qquad |x-y|\to\infty.
$$

Let $X=ax$ and $Y=ay$ be fixed physical points. What scaling of the continuum field $\Phi_a(X)=c_a\phi_{X/a}$ gives a nonzero two-point limit proportional to $|X-Y|^{-2\Delta}$?

<details><summary><strong>Solution</strong></summary>

Since $x-y=(X-Y)/a$,

$$
\langle\phi_{X/a}\phi_{Y/a}\rangle
\sim
\left|\frac{X-Y}{a}\right|^{-2\Delta}
=a^{2\Delta}|X-Y|^{-2\Delta}.
$$

Thus

$$
\langle\Phi_a(X)\Phi_a(Y)\rangle
=c_a^2 a^{2\Delta}|X-Y|^{-2\Delta}.
$$

A finite nonzero limit requires $c_a\sim a^{-\Delta}$.

</details>

### Exercise 2. Thermodynamic limit versus scaling limit

Explain why the thermodynamic limit at fixed lattice spacing does not by itself produce a continuum QFT.

<details><summary><strong>Solution</strong></summary>

The thermodynamic limit sends the volume to infinity while keeping the microscopic spacing $a$ fixed. It removes infrared boundary effects, but it does not remove the ultraviolet cutoff. The resulting theory still has a shortest distance $a$ and correlation functions defined on a lattice or regularized space.

A continuum scaling limit also sends $a\to 0$ and rescales fields and couplings so that finite physical observables converge. Both limits may be needed, but they solve different problems.

</details>

### Exercise 3. Why relevant tuning is necessary

Let a single relevant coupling $t$ transform near a fixed point as

$$
t\longmapsto b^y t,
\qquad y>0.
$$

If the cutoff is $a=b^{-N}$ and one applies $N$ RG steps, how small must $t(a)$ be to remain of order one at macroscopic scale?

<details><summary><strong>Solution</strong></summary>

After $N$ steps,

$$
t_N\approx b^{Ny}t(a).
$$

Since $a=b^{-N}$, we have $b^N=a^{-1}$. Therefore

$$
b^{Ny}=a^{-y}.
$$

To keep $t_N$ of order one, one needs

$$
t(a)=O(a^y).
$$

This is the simplest form of critical tuning. Nonlinear RG modifies the formula by corrections and possible logarithms, but the tuning principle remains.

</details>

## References

- L. P. Kadanoff, “Scaling Laws for Ising Models Near $T_c$,” *Physics Physique Fizika* **2** (1966) 263–272. [doi:10.1103/PhysicsPhysiqueFizika.2.263](https://doi.org/10.1103/PhysicsPhysiqueFizika.2.263).
- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–199. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- D. Buchholz and R. Verch, “Scaling Algebras and Renormalization Group in Algebraic Quantum Field Theory,” *Reviews in Mathematical Physics* **7** (1995) 1195–1240. [doi:10.1142/S0129055X9500044X](https://doi.org/10.1142/S0129055X9500044X), [arXiv:hep-th/9501063](https://arxiv.org/abs/hep-th/9501063).
- D. Buchholz and R. Verch, “Scaling Algebras and Renormalization Group in Algebraic Quantum Field Theory. II. Instructive Examples,” *Reviews in Mathematical Physics* **10** (1998) 775–800. [arXiv:hep-th/9708095](https://arxiv.org/abs/hep-th/9708095).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, 2nd ed., Springer, 1987. [doi:10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

## Version history

- 2026-06-30: First polished draft. Added correlation-function, measure, algebraic, and RG formulations of scaling limits.
