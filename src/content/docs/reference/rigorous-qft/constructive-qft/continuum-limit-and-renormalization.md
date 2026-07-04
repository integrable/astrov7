---
title: "Continuum Limit and Renormalization"
description: "A constructive account of how cutoff Euclidean field theories are tuned, renormalized, and proved to converge to continuum quantum field theories."
sidebar:
  label: "Continuum Limit"
  order: 11
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut renormalization group; Glimm–Jaffe constructive QFT; Rivasseau constructive renormalization; Osterwalder–Schrader reconstruction."
topics:
  - constructive QFT
  - continuum limit
  - renormalization
  - scaling limits
  - Wilsonian RG
canonicalTopics:
  - constructive-quantum-field-theory
  - continuum-limit
  - renormalization
  - scaling-limit
researchStatus:
  established:
    - "For many low-dimensional scalar and fermionic models, cutoff removal can be proved after suitable renormalization and estimates."
  active:
    - "Four-dimensional interacting continuum limits require model-specific control; the physically central gauge-theory cases remain open in the strongest axiomatic sense."
---

## Summary

A continuum limit is the operation that turns a regularized QFT into a continuum QFT. In constructive QFT this is not a slogan. One starts with a finite-volume, ultraviolet-cutoff model, tunes the bare parameters as the cutoff is removed, proves uniform estimates, and shows that the Schwinger functions converge as distributions.

In a scalar lattice notation, the schematic target is

$$
S_n(x_1,
\ldots,x_n)
=
\lim_{a\to0}\lim_{L\to\infty}
Z_a^{-n/2}
\left\langle
\phi_a(x_1^{(a)})\cdots\phi_a(x_n^{(a)})
\right\rangle_{a,L}.
$$

Here $a$ is the ultraviolet length cutoff, $L$ is an infrared volume cutoff, $Z_a$ is a field-strength normalization, and the bare mass and coupling hidden in the expectation usually depend on $a$. The limit is meaningful only after specifying what is kept fixed: a physical mass, a renormalized coupling, selected correlation-function normalizations, or a point on a critical scaling surface.

This page explains the constructive version of renormalization: not just subtracting divergent graphs, but proving that a nonperturbative continuum object exists and has the intended properties.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/), and [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/). [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains what Euclidean limits must satisfy to reconstruct a Lorentzian theory.

## Core idea

The continuum limit is a double demand. First, the regularized model must not blow up as the cutoff is removed. Second, the limit must not collapse to a trivial object unless that is the intended answer.

The physics word for the required tuning is renormalization. The mathematical word is often convergence: convergence of measures, moments, Schwinger functions, effective actions, or RG trajectories. Constructively, one does not assume that counterterms work because perturbation theory suggests them. One proves estimates uniform in the cutoff.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A constructive continuum-limit pipeline from cutoff models to tuned parameters, uniform estimates, continuum Schwinger functions, and axiom checks.](/figures/rigorous-qft/continuum-limit-renormalization-map.svg)

<figcaption>

A continuum construction tunes bare data while the lattice spacing $a$ goes to zero. The proof has two coupled sides: critical or RG scaling keeps physical quantities finite, and uniform estimates make the limiting Schwinger functions into actual mathematical objects.

</figcaption>
</figure>

## Setup and conventions

We work in Euclidean signature. The cutoff may be a lattice spacing $a$, a momentum cutoff $\Lambda_{\rm UV}$, a field mollifier, a finite-mode projection, or a combination of these. The volume cutoff is denoted $L$ or $\Lambda_{\rm vol}$, depending on context.

A cutoff theory produces finite-dimensional or otherwise well-defined Schwinger functions

$$
S_{n,a,L}(x_1,\ldots,x_n)
=
\langle \phi_a(x_1)\cdots\phi_a(x_n)\rangle_{a,L}.
$$

The continuum limit asks for distributions $S_n$ such that, for test functions $f_1,
\ldots,f_n$,

$$
\int S_{n,a,L}\,f_1\otimes\cdots\otimes f_n
\longrightarrow
\int S_n\,f_1\otimes\cdots\otimes f_n.
$$

The order of limits matters. Many constructions first take the infinite-volume limit at fixed cutoff, then remove the ultraviolet cutoff. Others use multiscale methods that interlace the two. A theorem should say which limit is being taken and in which topology.

The symbol $Z_a$ denotes field renormalization in a broad sense. In a lattice scaling limit, it may include powers of $a$ from the scaling dimension. In perturbative notation, one often writes a bare field as $\phi_0=Z^{1/2}\phi_R$, so $\phi_R=Z^{-1/2}\phi_0$. The page uses $Z_a^{-1/2}\phi_a$ for the renormalized field.

## The two cutoff problems

There are two separate cutoffs, and they solve different fake problems.

The infrared cutoff makes the system finite. A field in finite volume has a well-defined partition function or finite-dimensional approximation. Removing the infrared cutoff means proving that local observables converge as the volume grows:

$$
\lim_{L\to\infty}
\langle A\rangle_{a,L}
=
\langle A\rangle_a.
$$

This is a thermodynamic limit. It can fail because of phase coexistence, boundary-condition dependence, or massless infrared divergences.

The ultraviolet cutoff removes short distances. Removing it means proving that the theory has a limit as $a\to0$ or $\Lambda_{\rm UV}\to\infty$. This is much harder in continuum QFT because the field becomes more singular at short distance. The most common constructive obstruction is that naive moments diverge unless the interaction and fields are renormalized.

For a massive model, the desired order of magnitude is

$$
\xi_{\rm lat}(a)\sim \frac{1}{a m_R},
$$

where $\xi_{\rm lat}$ is the correlation length measured in lattice units and $m_R$ is a fixed physical mass. Thus a continuum limit is also a critical limit: the lattice correlation length must diverge in lattice units.

## Tuning bare parameters

Suppose a lattice statistical model has a critical point $g_c$ and a correlation-length exponent $\nu$:

$$
\xi_{\rm lat}(g)
\sim
C|g-g_c|^{-\nu}.
$$

To keep a physical mass $m_R$ fixed as $a\to0$, one chooses

$$
|g(a)-g_c|
\sim
(Ca m_R)^{1/\nu}.
$$

This is the statistical-mechanical form of renormalization. The bare coupling approaches a critical surface so that macroscopic distances survive the $a\to0$ limit.

In field-theory notation, the same idea appears as cutoff-dependent bare parameters:

$$
m_0^2=m_0^2(a),
\qquad
\lambda_0=\lambda_0(a),
\qquad
\phi_R=Z_a^{-1/2}\phi_a.
$$

For superrenormalizable models, such as $P(\phi)_2$ and $\phi^4_3$, only finitely many divergent counterterms are needed. In $\phi^4_3$, the mass counterterm is not optional; without it, the sequence does not have the intended finite limit. In renormalizable four-dimensional models, marginal couplings run logarithmically. In asymptotically free theories, the bare coupling tends to zero at short distance while nontrivial physics may remain at long distance.

At one-loop level, an asymptotically free coupling has the schematic behavior

$$
g_0(a)^2
\sim
\frac{1}{2b_0\log(1/(a\mu))},
\qquad b_0>0.
$$

This formula is not a construction by itself. It is a guide to where the constructive estimates should be centered.

## Renormalization as a constructive proof

A constructive continuum proof usually has several layers.

| Layer | What must be proved |
|---|---|
| Stability | The cutoff interaction does not drive the measure or partition function out of control. |
| Uniform estimates | Moments, cumulants, effective actions, or polymer activities are bounded independently of the cutoff. |
| Tuning | Bare parameters can be chosen so renormalized observables stay fixed. |
| Compactness or convergence | A subsequential or full limit of Schwinger functions exists as distributions. |
| Axiom verification | Euclidean invariance, symmetry, reflection positivity, clustering, and OS regularity survive the limit. |
| Nontriviality | The limit is not merely the free Gaussian theory unless the theorem is a triviality theorem. |

Different constructive programs emphasize different layers. Cluster expansions give convergence and exponential clustering in a suitable region. Correlation inequalities give monotonicity, phase information, and domination estimates. Multiscale RG tracks how local interactions change under successive integrations of short-distance fluctuations.

The key point is that counterterms are not the proof. Counterterms are part of the definition of the approximating sequence. The proof is the uniform control of that sequence.

## Examples and status

| Model | Dimension | Continuum-limit status in this chapter |
|---|---:|---|
| $P(\phi)_2$ | 2 | Constructed by Euclidean methods for broad polynomial interactions bounded below. |
| $\phi^4_2$ | 2 | Constructed; phase structure and correlation inequalities are available. |
| $\phi^4_3$ | 3 | Constructed in weak-coupling regimes after mass and vacuum-energy renormalization. |
| Sine-Gordon | 2 | Constructed in parameter regimes using Wick-ordered exponentials and Coulomb-gas methods. |
| Gross–Neveu | 2 | Constructive fermionic RG gives asymptotically free control in suitable formulations. |
| $\phi^4_4$ | 4 | Expected to be trivial in the positive-coupling continuum limit; strong rigorous triviality results exist in critical settings. |
| Yang–Mills | 4 | Finite lattice theory is rigorous; continuum existence plus mass gap remains a major open problem. |

This table is deliberately conservative. Perturbative renormalizability, numerical evidence, and physical success are not the same as a constructive continuum theorem.

## Nontriviality

A sequence of Schwinger functions may converge, but to the wrong object. The free Gaussian field is a common limiting attractor. A nontrivial scalar limit should have connected Schwinger functions beyond the two-point function:

$$
S_4^T\neq0
$$

for some test-function insertions. In scattering language one may ask for a non-identity $S$-matrix, but constructive Euclidean theories often state nontriviality directly in terms of Schwinger functions, spectra, or phases.

Triviality theorems are not failures of mathematics. They are theorems about what a given scaling limit can be. If a four-dimensional scalar lattice theory has only Gaussian scaling limits under specified hypotheses, that is a sharp constructive result, not an absence of result.

## Common pitfalls

**Taking $a\to0$ without tuning.** A generic sequence of bare parameters usually gives either a divergent theory or a massive theory whose physical correlation length shrinks to zero. Continuum limits require approaching a critical surface or an ultraviolet fixed point.

**Confusing perturbative renormalizability with construction.** Perturbation theory can identify counterterms order by order. A constructive proof must control the full cutoff sequence, not just each coefficient in a formal expansion.

**Forgetting field renormalization.** Even when correlation lengths are tuned correctly, point fields may need a normalization $Z_a^{-1/2}$ before their correlations converge to nonzero distributions.

**Calling every lattice model a QFT.** A finite lattice model is rigorous, but it is not yet a continuum QFT. The hard step is the limit in which the lattice spacing disappears while physical quantities remain finite.

**Equating Borel summability with all nonperturbative information.** Borel summability is powerful when proved with uniqueness and suitable analyticity hypotheses. By itself, a formal Borel transform does not replace a construction of the underlying Euclidean measure or Schwinger functions.

## Relations to other pages

[Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) gives the overall proof strategy. [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) shows why mass renormalization becomes a real cutoff-removal issue. [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) and [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/) describe two proof technologies used to obtain uniform estimates.

[OS Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explain what must be verified after Schwinger functions are constructed. The next page, [What Is Open in Four Dimensions?](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/), explains why cutoff removal is especially difficult in the physically central dimension.

## Research status

The constructive continuum limit is well understood for several two- and three-dimensional models. In those examples, the combination of Euclidean measures, Wick ordering, counterterms, cluster expansions, correlation inequalities, and multiscale RG produces actual continuum objects.

The four-dimensional situation is different. Scalar $\phi^4_4$ is marginal and is now strongly constrained by triviality results in critical scaling limits. Pure nonabelian Yang–Mills is asymptotically free, which is favorable in the ultraviolet, but the full continuum construction and mass gap remain open. This is why four-dimensional constructive QFT is not just a harder version of the two-dimensional story; it has qualitatively different obstructions.

## Exercises

### Exercise 1: Tune a lattice correlation length

Suppose $\xi_{\rm lat}(g)\sim C|g-g_c|^{-\nu}$. Find the scaling of $g(a)-g_c$ needed to keep $a\xi_{\rm lat}=m_R^{-1}$ fixed.

<details>
<summary><strong>Solution</strong></summary>

The condition is

$$
a C|g(a)-g_c|^{-\nu}=m_R^{-1}.
$$

Solving gives

$$
|g(a)-g_c|
\sim
(Ca m_R)^{1/\nu}.
$$

Thus the bare coupling approaches the critical value as a power of the lattice spacing.

</details>

### Exercise 2: Why a field-strength factor is needed

At criticality, suppose a lattice field satisfies

$$
\langle \phi_0\phi_n\rangle\sim |n|^{-2\Delta}.
$$

Set $x=an$. What power of $a$ should multiply $\phi_n$ so that the continuum two-point function scales as $|x|^{-2\Delta}$?

<details>
<summary><strong>Solution</strong></summary>

Since $|n|=|x|/a$,

$$
\langle \phi_0\phi_n\rangle
\sim
\left(\frac{|x|}{a}\right)^{-2\Delta}
=
a^{2\Delta}|x|^{-2\Delta}.
$$

Define the continuum field by $\phi_R(x)=a^{-\Delta}\phi_n$. Then

$$
\langle \phi_R(0)\phi_R(x)\rangle
\sim
|x|^{-2\Delta}.
$$

This is the scaling-limit version of field-strength renormalization.

</details>

### Exercise 3: Relevant, marginal, irrelevant

For the Euclidean scalar interaction $\int d^dx\,\lambda\phi^4$, use the free-field dimension $[\phi]=(d-2)/2$ to compute $[\lambda]$.

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless, so

$$
[\lambda]+4[\phi]-d=0.
$$

Using $[\phi]=(d-2)/2$ gives

$$
[\lambda]
=d-4\frac{d-2}{2}
=4-d.
$$

Thus $\phi^4$ is relevant for $d<4$, marginal for $d=4$, and irrelevant by power counting for $d>4$.

</details>

### Exercise 4: Perturbative counterterms versus constructive estimates

Explain in one paragraph why knowing the one-loop mass counterterm of $\phi^4_3$ is not the same as constructing $\phi^4_3$.

<details>
<summary><strong>Solution</strong></summary>

The one-loop counterterm identifies a divergent contribution that must be subtracted in perturbation theory. A construction must show much more: the cutoff measures or Schwinger functions exist for each cutoff, the chosen counterterms keep the full nonperturbative sequence uniformly controlled, the ultraviolet and infinite-volume limits converge as distributions, the limiting functions satisfy OS-type axioms, and the limit is nontrivial. Perturbation theory suggests the subtraction; constructive estimates prove that it works beyond formal power series.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Kenneth G. Wilson and John Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), 75–200. DOI: [10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).

### Deeper references

- Giovanni Gallavotti, "Renormalization Theory and Ultraviolet Stability for Scalar Fields via Renormalization Group Methods," *Reviews of Modern Physics* **57** (1985), 471–562. DOI: [10.1103/RevModPhys.57.471](https://doi.org/10.1103/RevModPhys.57.471).
- Arthur Jaffe, "Constructive Quantum Field Theory," in *Mathematical Physics 2000*, Imperial College Press, 2000. PDF: [arthurjaffe.com/Assets/pdf/CQFT.pdf](https://www.arthurjaffe.com/Assets/pdf/CQFT.pdf).
- Vincent Rivasseau, "Constructive Renormalization Theory," arXiv: [math-ph/9902023](https://arxiv.org/abs/math-ph/9902023).
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. DOI: [10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).

## Version history

- **2026-06-30:** Initial page on constructive cutoff removal and renormalization.
