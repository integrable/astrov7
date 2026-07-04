---
title: "What Is Open in Four Dimensions?"
description: "A status-aware guide to why constructing interacting continuum QFTs in four spacetime dimensions remains difficult."
sidebar:
  label: "Open in Four Dimensions"
  order: 12
level: Research
status: "Polished draft"
source: "Jaffe–Witten Yang–Mills problem statement; Aizenman–Duminil-Copin marginal triviality; Balaban lattice gauge RG; Lüscher chiral lattice gauge theory."
topics:
  - constructive QFT
  - four-dimensional QFT
  - Yang–Mills mass gap
  - triviality
  - chiral gauge theories
canonicalTopics:
  - constructive-quantum-field-theory
  - four-dimensional-quantum-field-theory
  - yang-mills-existence-and-mass-gap
  - triviality
researchStatus:
  established:
    - "Finite-cutoff four-dimensional lattice models are rigorous, and several strong partial results constrain possible continuum limits."
  active:
    - "A nontrivial interacting four-dimensional continuum QFT satisfying standard axioms is not known in the physically central Yang–Mills sense; the Clay Yang–Mills existence and mass gap problem remains open."
---

## Summary

Four spacetime dimensions are the physical dimension for the Standard Model and the borderline dimension for many constructive questions. In $d<4$, scalar polynomial interactions are often superrenormalizable. In $d=4$, the same interactions become marginal; logarithmic flows, triviality questions, and gauge-theory ultraviolet behavior become central.

The dimensional reason is visible in the scalar quartic coupling:

$$
[\lambda_{\phi^4}]=4-d.
$$

Thus $\phi^4$ is relevant below four dimensions, marginal in four dimensions, and irrelevant above four dimensions. Marginality is not automatically good or bad. It means power counting alone does not decide the continuum limit. The sign and higher terms of the beta function, positivity, global estimates, and infrared behavior become decisive.

The main constructive open problem in four dimensions is not whether one can write down a finite lattice action. One can. The problem is whether the cutoff can be removed while producing nontrivial Schwinger functions satisfying Euclidean axioms, or equivalently a Lorentzian QFT satisfying Wightman-like requirements. For pure nonabelian Yang–Mills, one also asks for a mass gap.

## Prerequisites

You should know [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/), [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/), [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). Familiarity with basic nonabelian gauge theory is helpful, but this page focuses on status rather than gauge-theory calculations.

## Core idea

In four dimensions, the two easiest ways to construct QFTs pull against each other.

One route starts from weakly coupled ultraviolet behavior. This is promising for asymptotically free gauge theories: the bare coupling becomes small at short distance. But constructive control must still handle gauge redundancy, large fields, topology, positivity, and the infrared mass gap.

The other route starts from positive Euclidean statistical models. This works beautifully in many scalar examples, but four-dimensional scalar $\phi^4$ lies at its upper critical dimension. The continuum scaling limit is expected, and in important critical settings proved, to be Gaussian rather than interacting.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A four-dimensional constructive status map with scalar φ⁴, Yang–Mills, chiral gauge theories, and CFT/SUSY examples around the central dimension d=4.](/figures/rigorous-qft/four-dimensional-open-problems-map.svg)

<figcaption>

Four dimensions are not one problem. Scalar theories face marginal triviality; pure Yang–Mills has favorable ultraviolet behavior but an open existence-plus-mass-gap problem; chiral gauge theories add anomaly and regulator questions; many exact or bootstrap-controlled theories lack a full constructive existence theorem in the strict sense used here.

</figcaption>
</figure>

## Setup and conventions

We discuss Euclidean four-dimensional models intended to reconstruct Lorentzian QFTs. A satisfactory constructive result should produce Schwinger functions, local observables, or a net of algebras satisfying appropriate versions of positivity, locality, covariance, and spectrum conditions.

The phrase four-dimensional QFT is ambiguous. It may mean any of the following:

| Meaning | Typical status |
|---|---|
| Finite lattice theory | Usually fully rigorous. |
| Perturbatively renormalized theory | Rigorous order by order in many frameworks, but not a nonperturbative construction. |
| Cutoff effective field theory | Mathematically meaningful with a finite cutoff and physically predictive below that cutoff. |
| Continuum scaling limit | Requires proof as $a\to0$ or $\Lambda_{\rm UV}\to\infty$. |
| Axiomatic Lorentzian QFT | Requires Hilbert space, locality, spectrum, fields or observables, and often scattering or mass-gap information. |

This page is about the last two meanings.

## Why four dimensions are different

### Marginality

Power counting says that $\phi^4$ is marginal in four dimensions and Yang–Mills is also marginal at the classical level. Quantum corrections decide whether the marginal interaction is marginally irrelevant, marginally relevant, or asymptotically free.

For scalar $\phi^4_4$ with positive coupling, the standard expectation is marginal triviality: after removing the cutoff while keeping physical quantities finite, the interaction disappears. For nonabelian Yang–Mills, the one-loop beta function has the opposite sign: the coupling decreases at high energy. That is the ultraviolet hope behind QCD-like theories.

### Ultraviolet control is not infrared control

Asymptotic freedom helps at short distances. The mass gap is a long-distance statement. A proof of four-dimensional Yang–Mills must control both ends at once: ultraviolet cutoff removal and infrared spectral behavior.

The two requirements are logically independent. One can have a good ultraviolet perturbation theory without a proof of confinement or a mass gap. One can also have strong-coupling lattice estimates at fixed lattice spacing without a continuum limit.

### Gauge redundancy

Gauge fields are not ordinary scalar fields. Gauge-dependent variables are redundant, gauge fixing can obscure positivity, and Gribov-type issues complicate global descriptions. The Clay formulation asks for gauge-invariant local fields corresponding to polynomials in the curvature and its covariant derivatives, not just a formal integral over vector potentials.

### Fermions and chirality

Vector-like lattice gauge theories such as lattice QCD have powerful nonperturbative regularizations. Chiral gauge theories are subtler. Fermion doubling, anomalies, global topological obstructions, and the definition of the fermion measure all matter. Exact lattice chiral symmetry and Ginsparg–Wilson ideas solved important parts of the problem, especially for anomaly-free Abelian cases, but a full general constructive continuum Standard Model remains beyond the scope of current theorem-level QFT.

## Model-by-model status

| Theory | What is rigorous | What remains open or subtle |
|---|---|---|
| Free fields in $d=4$ | Wightman and OS constructions are standard. | Interactions are absent. |
| $\phi^4_4$ with positive coupling | Finite-cutoff models are rigorous; strong triviality results exist, including Gaussian scaling limits in important critical settings. | A non-Gaussian positive-coupling continuum limit is not known and is generally not expected. |
| QED$_4$ | Perturbation theory and cutoff formulations are extremely successful physically. | A nontrivial all-scale continuum theory with nonzero charge is obstructed by Landau-pole/triviality expectations. |
| Pure Yang–Mills$_4$ | Lattice gauge theory at finite cutoff is rigorous; perturbative asymptotic freedom is established; many partial RG constructions exist. | Continuum existence with Wightman/OS-level axioms and a mass gap remains open. |
| QCD-like vector gauge theories | Lattice formulation gives a finite-cutoff nonperturbative definition used in simulations. | Continuum construction with full mathematical control of all axioms, confinement, and spectrum is not complete. |
| Chiral gauge theories | Major lattice progress exists for exact chiral symmetry and anomaly-free Abelian constructions. | General nonabelian chiral gauge theories and the full Standard Model remain delicate as constructive continuum objects. |
| Four-dimensional CFTs and supersymmetric theories | Bootstrap constraints, protected quantities, localization, and dualities give precise data in many cases. | These methods usually do not by themselves constitute a constructive Wightman or OS existence theorem. |

The table is not a judgment of physical usefulness. The Standard Model is extraordinarily successful as physics. The table records what is known in the strict constructive sense.

## What would count as a solution?

A four-dimensional constructive theorem should state its regulator, observables, topology of convergence, and axioms. For pure Yang–Mills, a minimal theorem-level target would include:

1. a sequence of finite-cutoff gauge-invariant models;
2. gauge-invariant Schwinger functions with ultraviolet limits;
3. Euclidean invariance and reflection positivity in the limit;
4. reconstruction of a Hilbert space or local observable algebra;
5. nontriviality;
6. a positive mass gap.

For scalar models, replace gauge-invariant curvature observables by scalar fields or Wick polynomials and replace the mass-gap requirement by the desired spectral or clustering property. For chiral gauge theories, add anomaly cancellation, a well-defined fermion measure, locality, and gauge invariance.

## Partial results and what they teach

Scalar triviality results teach that not every formally renormalizable interaction leads to a nontrivial continuum theory. Aizenman's work in dimensions greater than four and Fröhlich's results around $d\geq4$ showed the strength of triviality mechanisms. The later Aizenman–Duminil-Copin theorem proved Gaussian scaling limits for critical four-dimensional Ising-type and $\phi^4_4$ models in a precise setting. This is a major positive theorem: it identifies the continuum limit rather than merely failing to construct an interacting one.

Gauge-theory RG work, including Balaban's program and later expository developments, shows how much structure is needed even before the full mass-gap problem is addressed. Small-field analysis, large-field control, gauge fixing, background fields, and cluster expansions all become intertwined.

Lüscher's lattice chiral gauge theory work shows that some no-go intuitions can be bypassed when the assumptions are changed correctly. The Nielsen–Ninomiya obstruction is real under its hypotheses, but the Ginsparg–Wilson relation realizes chiral symmetry in a lattice-modified way. This is exactly the kind of status-aware lesson rigorous QFT should preserve: no-go theorems are statements about assumptions, not slogans.

## Common pitfalls

**Finite lattice does not mean solved continuum.** A finite lattice gauge theory is a well-defined mathematical object. The open problem is to take the cutoff away while preserving locality, positivity, covariance, and nontrivial dynamics.

**Asymptotic freedom is not the mass gap.** Asymptotic freedom controls the ultraviolet running of the coupling. A mass gap is a statement about the spectrum above the vacuum. A complete four-dimensional Yang–Mills proof must bridge both.

**Triviality is not uselessness.** A triviality theorem does not say that cutoff scalar field theory is physically worthless. It says that a specified all-scale continuum limit is Gaussian. Effective field theories with finite cutoffs can still be predictive and important.

**Perturbative renormalizability is not constructive existence.** The Standard Model is perturbatively renormalizable in the usual sense. That does not automatically provide a nonperturbative construction satisfying axioms.

**Exact formulas are not automatically constructions.** Supersymmetric localization, duality, and bootstrap constraints can give extraordinary exact data. A constructive theorem still needs a definition of the theory and control of the relevant limits.

**Gauge fields are not the only observables.** In a rigorous gauge theory, local gauge-invariant observables and Wilson-loop-type objects are usually safer than the gauge potential itself. Demanding pointwise gauge potentials as ordinary random variables is the wrong problem.

## Relations to other pages

[Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) explains the cutoff-removal problem abstractly. [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) shows how constructive renormalization already becomes nontrivial below four dimensions. [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) and [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/) provide tools behind many partial scalar results.

Later pages in the Open Problems and No-Go Theorems chapter should separate the broader topics: Yang–Mills existence and mass gap, triviality problems, rigorous chiral gauge theories, and confinement as a mathematical problem. This page is the constructive-QFT bridge to those more specialized open-problem pages.

## Research status

The strongest conservative statement is this: four-dimensional finite-cutoff QFT is abundant, four-dimensional perturbation theory is highly developed, and four-dimensional lattice simulation is a powerful science, but fully constructive interacting continuum QFT in the physically central sense remains open.

There are two opposite lessons. Scalar $\phi^4_4$ suggests that some formal interactions disappear in the continuum limit. Pure nonabelian Yang–Mills suggests that asymptotic freedom may allow a nontrivial continuum gauge theory, but the mathematical proof must also establish a mass gap. Both lessons are central to why four dimensions occupy a special place in rigorous QFT.

## Exercises

### Exercise 1: Upper critical dimension of $\phi^4$

Use $[\phi]=(d-2)/2$ to compute the mass dimension of $\lambda$ in $\int d^dx\,\lambda\phi^4$. What happens at $d=4$?

<details>
<summary><strong>Solution</strong></summary>

The action is dimensionless, so

$$
[\lambda]+4[\phi]-d=0.
$$

With $[\phi]=(d-2)/2$,

$$
[\lambda]=4-d.
$$

At $d=4$, $\lambda$ is classically marginal. Quantum corrections decide the actual scaling behavior.

</details>

### Exercise 2: Asymptotic freedom is ultraviolet

Suppose a coupling satisfies

$$
\mu\frac{dg}{d\mu}=-b_0g^3,
\qquad b_0>0.
$$

Solve the leading running and explain why this does not by itself prove a mass gap.

<details>
<summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^3}=-b_0\frac{d\mu}{\mu}.
$$

Integrating gives

$$
\frac{1}{g(\mu)^2}
=2b_0\log(\mu/\Lambda)
$$

for an integration scale $\Lambda$. Thus $g(\mu)\to0$ as $\mu\to\infty$, which is ultraviolet control. A mass gap is an infrared spectral statement about the lowest excitation above the vacuum. The running coupling formula does not construct the Hilbert space or prove the spectrum has a positive gap.

</details>

### Exercise 3: Triviality and connected four-point functions

Why is the vanishing of the connected four-point function a sign of Gaussianity?

<details>
<summary><strong>Solution</strong></summary>

For a Gaussian field, Wick's theorem expresses every $n$-point function as a sum over products of two-point functions. Equivalently, all connected cumulants beyond the second vanish. Thus a scaling limit in which connected four-point functions vanish, together with analogous higher connected functions, is Gaussian or generalized Gaussian depending on the two-point structure.

</details>

### Exercise 4: Finite lattice versus continuum theorem

Give two properties that a finite lattice Yang–Mills model has automatically and two properties that still require a continuum-limit theorem.

<details>
<summary><strong>Solution</strong></summary>

At finite lattice spacing and finite volume, the lattice measure is finite-dimensional, and gauge-invariant Wilson-loop observables are well-defined. What is not automatic is the existence of a nontrivial limit as $a\to0$ and $L\to\infty$, nor the recovery of continuum Euclidean invariance, reflection positivity, local gauge-invariant fields, Wightman/OS-type axioms, and a positive mass gap.

</details>

## References

### Standard first pass

- Arthur Jaffe and Edward Witten, "Quantum Yang–Mills Theory," Clay Mathematics Institute Millennium Problem statement. PDF: [claymath.org/wp-content/uploads/2022/06/yangmills.pdf](https://www.claymath.org/wp-content/uploads/2022/06/yangmills.pdf).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Kenneth G. Wilson and John Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), 75–200. DOI: [10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).

### Scalar triviality

- Michael Aizenman, "Proof of the Triviality of $\phi^4_d$ Field Theory and Some Mean-Field Features of Ising Models for $d>4$," *Physical Review Letters* **47** (1981), 1–4. DOI: [10.1103/PhysRevLett.47.1](https://doi.org/10.1103/PhysRevLett.47.1).
- Jürg Fröhlich, "On the Triviality of $\lambda\phi^4_d$ Theories and the Approach to the Critical Point in $d\geq4$ Dimensions," *Nuclear Physics B* **200** (1982), 281–296. DOI: [10.1016/0550-3213(82)90088-8](https://doi.org/10.1016/0550-3213(82)90088-8).
- Michael Aizenman and Hugo Duminil-Copin, "Marginal Triviality of the Scaling Limits of Critical 4D Ising and $\phi^4_4$ Models," *Annals of Mathematics* **194** (2021), 163–235. DOI: [10.4007/annals.2021.194.1.3](https://doi.org/10.4007/annals.2021.194.1.3), arXiv: [1912.07973](https://arxiv.org/abs/1912.07973). Corrigendum DOI: [10.4007/annals.2024.199.1.7](https://doi.org/10.4007/annals.2024.199.1.7).

### Gauge and chiral gauge theory

- Tadeusz Balaban, "Renormalization Group Approach to Lattice Gauge Field Theories. I. Generation of Effective Actions in a Small Field Approximation and a Coupling Constant Renormalization in Four Dimensions," *Communications in Mathematical Physics* **109** (1987), 249–301. DOI: [10.1007/BF01215223](https://doi.org/10.1007/BF01215223).
- Tadeusz Balaban, "Renormalization Group Approach to Lattice Gauge Field Theories. II. Cluster Expansions," *Communications in Mathematical Physics* **116** (1988), 1–22. DOI: [10.1007/BF01239022](https://doi.org/10.1007/BF01239022).
- Jacques Magnen, Vincent Rivasseau, and Roland Sénéor, "Construction of YM$_4$ with an Infrared Cutoff," *Communications in Mathematical Physics* **155** (1993), 325–383. DOI: [10.1007/BF02097397](https://doi.org/10.1007/BF02097397).
- Martin Lüscher, "Abelian Chiral Gauge Theories on the Lattice with Exact Gauge Invariance," *Nuclear Physics B* **549** (1999), 295–334. DOI: [10.1016/S0550-3213(99)00115-7](https://doi.org/10.1016/S0550-3213(99)00115-7), arXiv: [hep-lat/9811032](https://arxiv.org/abs/hep-lat/9811032).

## Version history

- **2026-06-30:** Initial status-aware page on open constructive problems in four dimensions.
