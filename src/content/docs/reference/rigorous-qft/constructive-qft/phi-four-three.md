---
title: "φ⁴₃ Theory"
description: "Explains the three-dimensional constructive quartic scalar field model, its superrenormalizable counterterms, multiscale difficulty, and theorem status."
sidebar:
  label: "φ⁴₃ Theory"
  order: 6
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe φ⁴₃; Feldman–Osterwalder; Magnen–Sénéor; Brydges–Fröhlich–Sokal; modern stochastic quantization."
topics:
  - phi four three
  - constructive QFT
  - mass renormalization
  - stochastic quantization
  - Euclidean measures
  - superrenormalizable QFT
canonicalTopics:
  - constructive-quantum-field-theory
  - phi-four-three-model
  - euclidean-quantum-field-theory
  - rigorous-renormalization
  - stochastic-quantization
researchStatus:
  established:
    - 'The $\phi^4_3$ model is a rigorously constructed interacting scalar theory in three Euclidean dimensions in important constructive frameworks, including weak-coupling Wightman constructions and modern Euclidean/SPDE constructions.'
  active:
    - "The full phase diagram, critical scaling theory, uniqueness issues in some infinite-volume constructions, and relations among different constructions remain more delicate than the basic existence of renormalized limits."
---

## Summary

The $\phi^4_3$ model is the three-dimensional Euclidean quartic scalar field theory. After Osterwalder–Schrader reconstruction, it corresponds to a $2+1$-dimensional Lorentzian QFT. It is still superrenormalizable, but it is much harder than $\phi^4_2$ because Wick ordering alone does not finish the renormalization.

The formal Euclidean action is

$$
S(\phi)
=
\int
\left(
\frac12|\nabla\phi|^2
+\frac12m^2\phi^2
+\lambda\phi^4
\right)d^3x,
\qquad \lambda>0.
$$

A cutoff definition must add counterterms. Schematically one studies measures of the form

$$
d\nu_{\Lambda,\epsilon}(\phi)
=
Z_{\Lambda,\epsilon}^{-1}
\exp\left[-\int_\Lambda
\left(
\lambda:\!\phi_\epsilon^4\!:
+\frac12 r_\epsilon:\!\phi_\epsilon^2\!:
\right)d^3x\right]d\mu_C(\phi),
$$

where $C=(-\Delta+m^2)^{-1}$ and $r_\epsilon$ is a cutoff-dependent mass counterterm. If one does not first Wick-order the quartic, the same renormalization appears as both a linearly divergent tadpole subtraction and a logarithmically divergent second-order mass subtraction. The exact constants depend on the regulator and normalization scheme.

The model is historically important because it is the first scalar construction where the mild $P(\phi)_2$ story is no longer enough. It forces multiscale estimates, renormalized Hamiltonians, cluster expansions, or modern singular-SPDE methods. It is also the prototype for the modern $\Phi^4_3$ stochastic quantization equation.

## Prerequisites

You should know [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/), [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). You should also be comfortable with the idea that a field may have negative regularity and that local nonlinearities of random distributions require renormalization.

## Core idea

Moving from two to three Euclidean dimensions changes the singularity class. In three dimensions, the massive covariance behaves at short distance like

$$
C(x)
\sim
\frac{1}{4\pi|x|}
\qquad (x\to0).
$$

For a mollified field,

$$
c_\epsilon
=
\mathbb E[\phi_\epsilon(x)^2]
\sim
\frac{A}{\epsilon}+O(1),
$$

with regulator-dependent $A>0$. Thus local powers are more singular than in two dimensions. Wick ordering subtracts the most immediate self-contractions, but diagrams with two interaction vertices still produce a logarithmic mass divergence.

<figure class="doc-figure" style="--figure-width: 48rem;">

![φ⁴₃ renormalization map](/figures/rigorous-qft/phi-four-three-renormalization-map.svg)

<figcaption>

The $\phi^4_3$ ultraviolet problem contains both the local Wick-ordering subtraction and a further mass renormalization. The linearly divergent tadpole is removed by normal ordering or an equivalent mass counterterm; the logarithmic second-order divergence requires an additional cutoff-dependent quadratic term.

</figcaption>
</figure>

The model is still below the critical dimension four. Power counting says it should be constructible, but the construction is no longer just "define Wick powers and exponentiate." One must control how renormalized local counterterms behave across scales.

## Setup and conventions

Work in Euclidean $\mathbb R^3$. Let

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0,
$$

and let $\mu_C$ be the massive Gaussian free-field measure. Let $\phi_\epsilon$ be a mollified or lattice-regularized field.

A common schematic cutoff measure is

$$
d\nu_{\Lambda,\epsilon}
\propto
\exp[-V_{\Lambda,\epsilon}(\phi)]d\mu_C(\phi),
$$

with

$$
V_{\Lambda,\epsilon}(\phi)
=
\int_\Lambda
\left(
\lambda:\!\phi_\epsilon^4\!:
+\frac12 r_\epsilon:\!\phi_\epsilon^2\!:
+E_\epsilon
\right)d^3x.
$$

The constant $E_\epsilon$ contributes to the normalization, while $r_\epsilon$ tunes the mass. One can equivalently write an un-Wick-ordered cutoff action with explicit mass and vacuum-energy counterterms. The two languages differ by finite choices and by how the divergent pieces are grouped.

A useful power-counting table is:

| Quantity | Dimension in $d=3$ |
|---|---:|
| field $\phi$ | $1/2$ |
| mass $m$ | $1$ |
| quartic coupling $\lambda$ | $1$ |
| $\phi^2$ coupling | $2$ |
| vacuum energy density | $3$ |

The positive dimension of $\lambda$ means the theory is superrenormalizable. The hard part is not an infinite tower of counterterms; it is proving the controlled limit of the finitely renormalized model.

## Why normal ordering is not enough

In two dimensions, normal ordering the polynomial is the main ultraviolet renormalization. In three dimensions, normal ordering removes the tadpole-type divergence but leaves a further mass divergence from second-order effects.

In perturbative language, the two relevant divergent structures are:

| Divergence | Informal origin | Counterterm type |
|---|---|---|
| tadpole | one contraction inside $\phi^4$ | mass and vacuum-energy subtraction |
| sunset or double-contraction effect | two quartic vertices at short distance | additional mass renormalization |

With a cutoff $\epsilon$, the mass counterterm has the schematic form

$$
r_\epsilon
=
r_{\mathrm{phys}}
+c_1(\mathrm{scheme})\lambda\epsilon^{-1}
+c_2(\mathrm{scheme})\lambda^2\log\frac1\epsilon
+O(1),
$$

if written before Wick ordering. In a Wick-ordered scheme the $\lambda\epsilon^{-1}$ part is absorbed into $:\phi^4:$, but the logarithmic $\lambda^2\log(1/\epsilon)$ mass adjustment remains. The constants and signs depend on the exact action normalization and regulator, so a convention-free page should not pretend they are universal numbers.

The universal message is:

$$
\phi^4_3
\text{ needs a tuned quadratic counterterm in addition to Wick ordering.}
$$

## Constructive routes

There are several rigorous routes to the model. They do not all prove identical auxiliary statements, but they target the same kind of renormalized continuum object.

### Hamiltonian constructive route

Early work constructs an interacting Hamiltonian with the $:\!\phi^4\!:$ interaction in three dimensions, proves lower bounds or positivity after renormalization, removes cutoffs in finite or infinite volume under suitable assumptions, and then verifies Wightman-type properties in regimes such as weak coupling.

This route emphasizes:

| Object | Role |
|---|---|
| renormalized Hamiltonian | Generates time evolution. |
| lower bound | Prevents the energy from running to $-\infty$. |
| mass gap | Gives control over long-distance behavior in weak-coupling regimes. |
| Wightman axioms | Verify the resulting Lorentzian QFT data. |

### Euclidean constructive route

A Euclidean construction studies the cutoff Gibbs measures and their Schwinger functions. It uses multiscale analysis, cluster expansions, correlation estimates, and renormalized perturbative bounds to take the ultraviolet and volume limits.

This route emphasizes:

$$
\text{cutoff Euclidean measure}
\longrightarrow
\text{renormalized Schwinger functions}
\longrightarrow
\text{OS/Wightman data}.
$$

The measure-theoretic object is harder than in $P(\phi)_2$ because the interaction is more singular relative to the Gaussian free field.

### Stochastic quantization route

The dynamic $\Phi^4_3$ equation is a singular stochastic PDE of the form

$$
\partial_t\Phi
=
\Delta\Phi
-m^2\Phi
-\lambda\Phi^3
+\text{counterterm}\cdot\Phi
+\xi,
$$

where $\xi$ is space-time white noise. This equation is not classically meaningful without renormalization. Regularity structures, paracontrolled distributions, and related PDE methods give a rigorous meaning to the renormalized dynamics and connect invariant measures of the dynamics to Euclidean $\Phi^4_3$ measures.

This route is conceptually modern because it does not merely prove a static measure exists. It also constructs Markov dynamics whose invariant measure is the Euclidean field measure, at least in the settings covered by the theorems.

## What is actually constructed

Depending on the theorem, the output may be one of the following.

| Output | Meaning |
|---|---|
| finite-volume Wightman theory | A Lorentzian QFT in a spatially finite or controlled-volume setting. |
| weak-coupling massive theory | A theory with Wightman axioms and mass gap for sufficiently small coupling. |
| infinite-volume Euclidean measure | A probability measure or subsequential limit on distributions over $\mathbb R^3$. |
| dynamic $\Phi^4_3$ process | A renormalized Markov process with a Euclidean invariant measure. |
| Schwinger functions | Euclidean correlation functions satisfying some or all OS properties. |

A page about rigorous QFT should not collapse these outputs into one vague phrase. "The $\phi^4_3$ model exists" is meaningful only after specifying which construction, which volume, which parameter regime, and which axioms are verified.

## Comparison with φ⁴₂ and φ⁴₄

The three-dimensional theory sits between the clean success of $\phi^4_2$ and the four-dimensional difficulties of $\phi^4_4$.

| Model | Coupling dimension | Constructive status | Main lesson |
|---|---:|---|---|
| $\phi^4_2$ | $2$ | Classic constructive success. | Wick ordering controls the UV problem. |
| $\phi^4_3$ | $1$ | Constructed in important rigorous frameworks. | Additional mass renormalization and multiscale control are needed. |
| $\phi^4_4$ | $0$ | Believed or known in many settings to suffer triviality rather than give a non-Gaussian continuum scalar theory. | Marginality and logarithmic flow dominate. |

This table is only a first-pass orientation. Four-dimensional scalar triviality is a major topic in its own right, and the statement depends on the exact limiting procedure and class of models.

## The role of the mass parameter

The mass parameter is not simply a number inserted after the theory is built. In $\phi^4_3$ it is part of the renormalized definition. One chooses a cutoff-dependent bare mass so that a finite physical parameter remains after the cutoff is removed.

Schematic relation:

$$
m^2_{\mathrm{bare}}(\epsilon)
=
m^2_{\mathrm{ren}}
+\delta m^2(\epsilon),
$$

where

$$
\delta m^2(\epsilon)
\text{ diverges as }\epsilon\downarrow0.
$$

Changing the finite part of this subtraction moves the theory through its parameter space. Near a critical value, one expects long-distance behavior related to the three-dimensional Ising universality class. Proving the exact critical scaling theory is much stronger than constructing a massive renormalized model.

## Common pitfalls

**Saying "normal ordering defines $\phi^4_3$" without qualification.** Normal ordering is necessary but not sufficient. A further mass renormalization is needed.

**Treating counterterm constants as universal.** The coefficients of divergent counterterms depend on the regulator and normalization. The universal statement is the finite list of allowed counterterm structures and the existence of a renormalized limit.

**Confusing the static measure with the stochastic dynamics.** Stochastic quantization constructs a Markov process whose invariant measure is related to the Euclidean field. The process and the measure are different objects, even though they are deeply connected.

**Assuming all construction theorems prove the same axioms.** Some results prove Wightman axioms and a mass gap in weak-coupling regimes. Others prove tightness, reflection positivity, non-Gaussianity, and parts of the OS framework for broad parameter ranges. Read the theorem statement.

**Thinking three dimensions are only a small modification of two dimensions.** The singularity of the field changes qualitatively. The three-dimensional model is the first quartic scalar model where multiscale renormalization becomes visibly unavoidable.

**Mistaking criticality for massive construction.** The massive model can be rigorously constructed without solving the critical scaling limit. The critical point is an infrared and universality problem.

## Relations to other pages

This page follows [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/) and should be read as the first serious escalation in constructive scalar QFT. It relies on [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) for the free field and on [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) for the probabilistic interpretation of Schwinger functions.

The next constructive pages should turn to sine-Gordon theory and then to the tools behind these examples: cluster expansions, correlation inequalities, and continuum limit methods. The modern SPDE view will reappear in the Probability, SPDEs, and Stochastic Quantization chapter.

## Research status

The $\phi^4_3$ theory is a major established constructive success, but its status is more nuanced than the two-dimensional model. Classical results construct weakly coupled massive theories satisfying Wightman axioms and a mass gap. Modern singular-SPDE and PDE approaches provide new Euclidean and dynamical constructions, including broad statements about tightness, non-Gaussianity, reflection positivity, and Dyson–Schwinger relations.

Open or delicate directions include uniqueness and phase selection in some infinite-volume regimes, the exact relation among construction schemes, critical scaling limits, and the complete comparison with lattice universality. These questions make $\phi^4_3$ a bridge between classical constructive QFT and current probability/PDE methods.

## Exercises

### Exercise 1: Power counting in three dimensions

Use $[\phi]=(d-2)/2$ to compute the mass dimension of $\lambda$ in $\lambda\phi^4$ for $d=3$. What does this say about renormalizability?

<details><summary><strong>Solution</strong></summary>

For $d=3$,

$$
[\phi]=\frac{3-2}{2}=\frac12.
$$

The interaction density $\lambda\phi^4$ must have dimension $3$, so

$$
[\lambda]+4[\phi]=3.
$$

Therefore

$$
[\lambda]+2=3,
\qquad
[\lambda]=1.
$$

The positive mass dimension of $\lambda$ means that the quartic interaction is superrenormalizable. Only finitely many counterterm structures are needed, but nontrivial estimates are still required to prove the continuum limit.

</details>

### Exercise 2: Why a quadratic counterterm is natural

Explain why the only nontrivial local counterterm beyond vacuum energy in scalar $\phi^4_3$ is expected to be quadratic, not another quartic counterterm.

<details><summary><strong>Solution</strong></summary>

Power counting shows that the quartic coupling has positive dimension. Divergences become less severe as more external legs are kept. The superficially divergent local structures are therefore low-degree polynomials in the field: a constant term and a $\phi^2$ term. The quartic coupling itself does not require an infinite divergent coupling renormalization in the same way a marginal four-dimensional interaction would.

This is the superrenormalizable pattern: finitely many relevant counterterms absorb all ultraviolet divergences.

</details>

### Exercise 3: Static versus dynamic construction

State the difference between constructing the Euclidean $\Phi^4_3$ measure and constructing the stochastic quantization dynamics.

<details><summary><strong>Solution</strong></summary>

A Euclidean measure is a probability law on spatial distributions. Its moments are Schwinger functions. Constructing it gives static Euclidean QFT data.

The stochastic quantization dynamics is a Markov process whose state at each stochastic time is a spatial distribution. Its invariant measure is expected to be the Euclidean field measure. Constructing the dynamics therefore gives both a time-dependent singular SPDE and, when invariant measures are controlled, another route to the static Euclidean QFT.

</details>

## References

### Standard first pass

- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. DOI: [10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).

### Classical constructive references

- James Glimm, "Boson Fields with the $:\!\phi^4\!:$ Interaction in Three Dimensions," *Communications in Mathematical Physics* **10** (1968), 1–47. DOI: [10.1007/BF01654131](https://doi.org/10.1007/BF01654131).
- James Glimm and Arthur Jaffe, "Positivity of the $\phi^4_3$ Hamiltonian," *Fortschritte der Physik* **21** (1973), 327–376. DOI: [10.1002/prop.19730210702](https://doi.org/10.1002/prop.19730210702).
- Joel S. Feldman and Konrad Osterwalder, "The Wightman Axioms and the Mass Gap for Weakly Coupled $(\phi^4)_3$ Quantum Field Theories," *Annals of Physics* **97** (1976), 80–135. DOI: [10.1016/0003-4916(76)90223-2](https://doi.org/10.1016/0003-4916(76)90223-2).
- Jacques Magnen and Roland Sénéor, "The Infinite Volume Limit of the $\phi^4_3$ Model," *Annales de l'Institut Henri Poincaré A* **24** (1976), 95–159. [Numdam](https://www.numdam.org/item/AIHPA_1976__24_2_95_0/).
- Jacques Magnen and Roland Sénéor, "Phase Space Cell Expansion and Borel Summability for the Euclidean $\phi^4_3$ Theory," *Communications in Mathematical Physics* **56** (1977), 237–276. DOI: [10.1007/BF01614211](https://doi.org/10.1007/BF01614211).
- David C. Brydges, Jürg Fröhlich, and Alan D. Sokal, "A New Proof of the Existence and Nontriviality of the Continuum $\phi^4_2$ and $\phi^4_3$ Quantum Field Theories," *Communications in Mathematical Physics* **91** (1983), 141–186. DOI: [10.1007/BF01211157](https://doi.org/10.1007/BF01211157).

### Modern stochastic and PDE references

- Martin Hairer, "A Theory of Regularity Structures," *Inventiones Mathematicae* **198** (2014), 269–504. DOI: [10.1007/s00222-014-0505-4](https://doi.org/10.1007/s00222-014-0505-4). arXiv: [1303.5113](https://arxiv.org/abs/1303.5113).
- Martin Hairer, "Regularity Structures and the Dynamical $\Phi^4_3$ Model," *Current Developments in Mathematics* **2014**, 1–49. arXiv: [1508.05261](https://arxiv.org/abs/1508.05261).
- Jean-Christophe Mourrat and Hendrik Weber, "The Dynamic $\Phi^4_3$ Model Comes Down from Infinity," *Communications in Mathematical Physics* **356** (2017), 673–753. DOI: [10.1007/s00220-017-2997-4](https://doi.org/10.1007/s00220-017-2997-4). arXiv: [1601.01234](https://arxiv.org/abs/1601.01234).
- Massimiliano Gubinelli and Martina Hofmanová, "A PDE Construction of the Euclidean $\Phi^4_3$ Quantum Field Theory," *Communications in Mathematical Physics* **384** (2021), 1–75. DOI: [10.1007/s00220-021-04022-0](https://doi.org/10.1007/s00220-021-04022-0). arXiv: [1810.01700](https://arxiv.org/abs/1810.01700).
- Nikolay Barashkov and Massimiliano Gubinelli, "The $\Phi^4_3$ Measure via Girsanov's Theorem," *Electronic Journal of Probability* **26** (2021), article 81. DOI: [10.1214/21-EJP635](https://doi.org/10.1214/21-EJP635). arXiv: [2004.01513](https://arxiv.org/abs/2004.01513).

## Version history

- **2026-06-29:** Initial page created.
