---
title: "Axiomatic QFT Preview"
description: "A concept-first preview of Wightman, Osterwalder–Schrader, Haag–Kastler, constructive, and algebraic viewpoints on quantum field theory."
sidebar:
  label: "Axiomatic QFT Preview"
  order: 8
---

## Summary

Axiomatic QFT asks a blunt question:

$$
\boxed{\text{Which structural assumptions are actually needed for QFT?}}
$$

The answer is not one unique list. There are several complementary languages:

- **Wightman QFT** starts with Lorentzian fields as operator-valued distributions and states axioms for their vacuum correlation functions.
- **Osterwalder–Schrader QFT** starts with Euclidean correlation functions and asks when they reconstruct a unitary Lorentzian theory.
- **Haag–Kastler algebraic QFT** starts with local algebras of observables assigned to spacetime regions.
- **Constructive QFT** tries to prove that nontrivial examples satisfying such axioms actually exist.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Three axiomatic viewpoints on QFT: Wightman fields, Osterwalder–Schrader Euclidean functions, and Haag–Kastler local algebras](/figures/foundations/axiomatic-qft-frameworks.svg)

<figcaption>

Three major axiomatic viewpoints package the same structural constraints in different primitives. Wightman QFT starts from Lorentzian fields, Osterwalder–Schrader QFT starts from Euclidean correlators, and Haag–Kastler QFT starts from local observable algebras.

</figcaption>
</figure>

This page is deliberately a preview. It does not prove the reconstruction theorems, classify sectors, or build interacting models. It explains what the axioms are trying to capture and how they relate to the foundation pages already written: locality, unitarity, spectral condition, cluster decomposition, reflection positivity, analyticity, and superselection.

The site-wide plan gives theorem-first material a separate home in Mathematical and Rigorous QFT, including Wightman axioms, Osterwalder–Schrader axioms, Haag–Kastler nets, DHR theory, constructive QFT, perturbative algebraic QFT, and open problems. Foundations should prepare readers for that material without pretending that a rigorous framework is just another notation for Feynman diagrams.

## Prerequisites

You should know [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/), [Unitarity](/foundations/structural-principles/unitarity/), [Spectral Condition](/foundations/structural-principles/spectral-condition/), [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/), [Reflection Positivity](/foundations/structural-principles/reflection-positivity/), [Analyticity and Causality](/foundations/structural-principles/analyticity-and-causality/), [Superselection Sectors](/foundations/structural-principles/superselection-sectors/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/), and [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/).

:::note[Assumptions]
The standard axioms are usually stated for relativistic QFT on Minkowski or Euclidean space, with a positive Hilbert space, local fields or observables, Poincaré or Euclidean covariance, a stable vacuum, and positive energy. Gauge theories require care: gauge-fixed fields need not live in a positive physical Hilbert space, and the local observable algebra is usually gauge invariant. Curved-spacetime QFT, thermal QFT, finite density, defects, boundaries, and nonrelativistic systems need modified axiomatic frameworks.
:::

## Why axioms are useful

Axioms are not there to make QFT look fancier. They perform three jobs.

First, they separate **principles** from **models**. Locality, positive energy, Hilbert-space positivity, and covariance are not properties of a particular Lagrangian term; they are structural claims about the theory.

Second, they expose hidden assumptions. Perturbation theory often manipulates formal fields, divergent products, gauge-fixed variables, and path-integral measures. Axiomatic frameworks ask which of those manipulations correspond to well-defined operators, distributions, states, or algebras.

Third, they make no-go theorems and reconstruction theorems possible. Spin-statistics, CPT, Wightman reconstruction, Osterwalder–Schrader reconstruction, and DHR superselection theory are all examples where a small set of assumptions has large consequences.

This is why axiomatic QFT is not opposed to physics. It is the part of physics that asks which assumptions are doing the work.

## Wightman viewpoint

The Wightman framework begins with fields on Minkowski spacetime. The fields are not ordinary operators at points. They are **operator-valued distributions**. Instead of writing $\phi(x)$ as a well-defined operator for each point $x$, one smears with a test function $f$:

$$
\phi(f)=\int d^4x\, f(x)\phi(x).
$$

The basic vacuum correlation functions are the Wightman functions

$$
W_n(x_1,\ldots,x_n)
=\langle\Omega|\phi_1(x_1)\cdots\phi_n(x_n)|\Omega\rangle.
$$

A schematic Wightman package includes:

| Axiom-type condition | Physical meaning |
|---|---|
| Hilbert-space positivity | probabilities and norms are nonnegative |
| unique invariant vacuum | there is a stable Poincaré-invariant ground state |
| Poincaré covariance | fields transform correctly under spacetime symmetries |
| spectral condition | energy-momentum lies in the closed forward cone |
| locality | spacelike-separated bosonic fields commute, with graded variants for fermions |
| fields as distributions | pointlike fields are singular and must be smeared |
| cyclicity of the vacuum | local fields acting on the vacuum generate a dense set of states |

The Wightman functions then carry the theory. Their support, analyticity, positivity, and symmetry properties encode the Hilbert space, fields, and vacuum.

A major theorem says roughly: if a collection of distributions $W_n$ satisfies the Wightman conditions, then one can reconstruct a Hilbert space, vacuum, fields, and Poincaré representation whose vacuum correlators are those $W_n$. The proof uses a GNS-like construction: build formal states by applying fields to the vacuum, define inner products from the Wightman functions, quotient null states, and complete.

For Foundations, the important lesson is:

$$
\boxed{\text{correlators are not just outputs; with the right positivity, they can define the theory}.}
$$

## Osterwalder–Schrader viewpoint

Many QFT calculations are easier in Euclidean signature. But not every Euclidean statistical system reconstructs a unitary Lorentzian QFT. Osterwalder–Schrader axioms answer the question:

$$
\boxed{\text{When do Euclidean correlators come from a Lorentzian quantum theory?}}
$$

The Euclidean correlation functions are often called Schwinger functions:

$$
S_n(x_1,\ldots,x_n)
=\langle\phi_E(x_1)\cdots\phi_E(x_n)\rangle_E.
$$

A schematic OS package includes:

| Euclidean condition | Lorentzian role |
|---|---|
| Euclidean covariance | Poincaré covariance after continuation |
| permutation symmetry | bosonic locality and Euclidean exchange symmetry |
| reflection positivity | positive Hilbert-space inner product |
| regularity/growth bounds | distributional control |
| cluster property | vacuum uniqueness and independence at large separation |

The distinctive condition is **reflection positivity**. Split Euclidean time as $\tau>0$ and $\tau<0$, and let $\Theta$ reflect $\tau\mapsto-\tau$ with the appropriate action on fields. For a functional $F$ of fields supported at positive Euclidean time, one requires

$$
\langle(\Theta F)F\rangle_E\ge0.
$$

This is the Euclidean ancestor of Hilbert-space positivity. Without it, a Euclidean path integral may be perfectly meaningful as a statistical integral but fail to define a unitary Lorentzian QFT.

The OS reconstruction theorem then builds a Hilbert space from positive-time Euclidean functionals, with inner product

$$
\langle F,G\rangle_{\rm OS}=\langle(\Theta F)G\rangle_E.
$$

Time translations in Euclidean time become a positive semigroup, whose generator becomes the Lorentzian Hamiltonian after reconstruction.

This is why the Euclidean pages in Foundations emphasized that Wick rotation is not just a formal substitution. It is a bridge that needs positivity and analytic control.

## Haag–Kastler viewpoint

Algebraic QFT changes the starting point. Instead of beginning with fields, it begins with **local observables**.

To each suitable spacetime region $\mathcal O$, assign an algebra

$$
\mathcal O\longmapsto\mathcal A(\mathcal O).
$$

Here $\mathcal A(\mathcal O)$ is the algebra of observables measurable inside the region $\mathcal O$. The typical Haag–Kastler conditions include:

| Algebraic condition | Meaning |
|---|---|
| isotony | if $\mathcal O_1\subset\mathcal O_2$, then $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$ |
| locality | spacelike-separated observable algebras commute |
| covariance | spacetime symmetries move regions and algebras compatibly |
| vacuum representation | a distinguished representation has a vacuum and positive energy |
| additivity | larger regions are generated by smaller-region algebras |
| time-slice property | observables in a thin time-slice determine the causal development |

This viewpoint is especially powerful for gauge theories and superselection sectors. Gauge-dependent fields may be useful computationally, but the physical observables are gauge invariant. Algebraic QFT can focus on the observable net first and treat charged fields or sectors as representation-theoretic data.

In this language, a superselection sector is not merely a subspace. It is often an inequivalent representation of the observable net. The vacuum representation describes the neutral sector. Charged sectors are representations that look locally like the vacuum in appropriate ways but differ globally, for example by charge or boundary flux. The Doplicher–Haag–Roberts program turns this idea into a precise theory of sectors and statistics under suitable assumptions.

For Foundations, the key message is:

$$
\boxed{\text{fields are useful, but local observables are often more invariantly defined}.}
$$

## Constructive viewpoint

Axioms are only useful if there are theories that satisfy them. Constructive QFT asks for actual constructions of interacting QFTs, not just formal perturbation series.

The general challenge is hard because quantum fields are singular, interactions require renormalization, and path-integral measures in continuum field theory are rarely honest finite-dimensional measures. Constructive methods use cutoffs, estimates, cluster expansions, correlation inequalities, reflection positivity, and renormalization-group control to take continuum limits.

Important rigorous constructions exist in low-dimensional models, such as variants of $P(\phi)_2$, sine-Gordon, Gross–Neveu-type models, and other superrenormalizable theories. Four-dimensional interacting continuum gauge theory with a mass gap is a much harder problem; the rigorous construction of four-dimensional Yang–Mills theory with a mass gap is famously one of the Clay Millennium Prize Problems.

This should calibrate expectations. A perturbative QFT can be extraordinarily predictive without already being a fully constructed mathematical object. Conversely, a rigorous construction may answer existence questions without being the fastest way to compute collider amplitudes.

## How the frameworks translate

The three major languages highlight different data.

| Physical idea | Wightman language | OS language | Algebraic language |
|---|---|---|---|
| locality | spacelike commutators vanish | permutation symmetry plus reconstruction | spacelike algebras commute |
| positive energy | spectrum of translations in forward cone | Euclidean time semigroup after reconstruction | positive-energy representation |
| unitarity | positive Hilbert space | reflection positivity | *-representations on Hilbert space |
| fields | operator-valued distributions | Euclidean random fields/correlators | optional coordinatization of observable net |
| vacuum | invariant cyclic vector | cluster behavior and reconstructed vacuum | vacuum state/representation |
| sectors | representations of field/observable algebra | boundary conditions and reconstructed sectors | inequivalent representations of the net |

No single column is “the real one.” They are different ways of packaging the same structural demands.

## Example: the free scalar field

The free scalar field is the safest model for seeing all three viewpoints.

In the Wightman framework, its two-point function is

$$
W_2(x-y)=\langle\Omega|\phi(x)\phi(y)|\Omega\rangle
=\int\frac{d^3p}{(2\pi)^3 2E_{\mathbf p}}
 e^{-ip\cdot(x-y)}.
$$

The on-shell measure has positive-energy support, so the spectral condition is manifest. The commutator

$$
[\phi(x),\phi(y)]=i\Delta(x-y)
$$

vanishes at spacelike separation, so locality holds.

In the Euclidean framework, the two-point Schwinger function is

$$
S_2(x)=\int\frac{d^4p_E}{(2\pi)^4}
\frac{e^{ip_E\cdot x}}{p_E^2+m^2}.
$$

It is Euclidean invariant and reflection positive. Reflection positivity is the nontrivial statement that this Euclidean covariance data reconstructs a positive Lorentzian Hilbert space, not a ghost theory.

In algebraic QFT, one can assign to each region the algebra generated by smeared fields supported in that region, or more carefully by bounded functions of those smeared fields. Locality follows from the vanishing of the commutator for spacelike-separated supports.

This example is mathematically tame compared with interacting four-dimensional QFT, but it shows the shape of the general story.

## Gauge theories and why observables matter

Gauge theories force extra care. A gauge-fixed potential $A_\mu$ can be useful, but it may not be an operator on a positive physical Hilbert space. Ghost fields are essential in covariant perturbation theory, but they are not physical observables. BRST cohomology identifies physical states and operators in the gauge-fixed formalism.

Algebraic language is therefore attractive: start with gauge-invariant local observables, such as field strengths, Wilson loops, currents, or local gauge-invariant composites. Charged sectors then appear as representations of the observable algebra rather than as local gauge-variant fields.

This is also why the distinction between local fields and local observables matters for superselection. A charged field may be an excellent interpolating field, but the observable algebra may still preserve charge sectors.

## Common pitfalls

**Pitfall 1: Thinking fields at points are honest operators.** They are distributions. Smeared fields are the objects that have a chance to be operators.

**Pitfall 2: Treating Euclidean path integrals as automatically unitary.** Reflection positivity is the missing condition. Without it, Wick rotation may produce a Euclidean model but not a unitary Lorentzian QFT.

**Pitfall 3: Assuming gauge-fixed fields are physical observables.** Gauge-fixed variables can be computationally essential while not belonging to the physical observable algebra.

**Pitfall 4: Confusing perturbative consistency with constructive existence.** Perturbation theory can satisfy formal Ward identities and unitarity order by order without already giving a fully constructed continuum measure.

**Pitfall 5: Treating axiomatic QFT as irrelevant to physics.** CPT, spin-statistics, spectral representations, superselection, and analyticity are all places where axiomatic assumptions become physical constraints.

**Pitfall 6: Importing theorem-level statements without their hypotheses.** Many rigorous theorems assume positivity, locality, spectrum condition, vacuum uniqueness, or mass gap. Changing gauge, state, boundary condition, or spacetime can change the theorem.

## Relation to other topics

- [Locality and Microcausality](/foundations/structural-principles/locality-and-microcausality/) supplies the local commutation condition behind Wightman and Haag–Kastler locality.
- [Spectral Condition](/foundations/structural-principles/spectral-condition/) supplies the positive-energy support used in Wightman analyticity and reconstruction.
- [Reflection Positivity](/foundations/structural-principles/reflection-positivity/) is the key OS condition for reconstructing a positive Lorentzian Hilbert space.
- [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) appears as a vacuum-purity and large-distance independence condition.
- [Analyticity and Causality](/foundations/structural-principles/analyticity-and-causality/) explains how locality and positive energy produce analytic domains.
- [Superselection Sectors](/foundations/structural-principles/superselection-sectors/) is the foundation-level bridge to algebraic representations and DHR theory.
- [Path-Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains why formal functional integrals need regulators, Jacobians, and care.
- Mathematical and Rigorous QFT is the natural home for theorem-first Wightman, OS, Haag–Kastler, constructive, perturbative algebraic, and factorization-algebra treatments.

## Exercises

### Exercise 1: Why fields are smeared

Explain why the product $\phi(x)^2$ at a point is more singular than the smeared expression $\phi(f)^2$.

<details>
<summary><strong>Solution</strong></summary>

A quantum field $\phi(x)$ is an operator-valued distribution. Distributions are defined by their action on test functions, not by ordinary point values. Smearing gives

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
$$

which averages the field over a spacetime region. Point products such as $\phi(x)^2$ multiply distributions at the same point and typically diverge. Renormalized composite operators are carefully defined replacements for such point products.

</details>

### Exercise 2: Wightman positivity

For a scalar field, show that positivity of the Hilbert-space norm implies

$$
\sum_{i,j}\overline{c_i}c_j\,W_2(x_i-x_j)\ge0
$$

for any finite set of complex coefficients $c_i$.

<details>
<summary><strong>Solution</strong></summary>

Consider the state

$$
|\Psi\rangle=\sum_i c_i\phi(x_i)|\Omega\rangle,
$$

formally ignoring smearing. Its norm is

$$
\langle\Psi|\Psi\rangle
=\sum_{i,j}\overline{c_i}c_j
\langle\Omega|\phi(x_i)^\dagger\phi(x_j)|\Omega\rangle.
$$

For a Hermitian scalar field and translation-invariant vacuum this gives the stated positivity condition, up to the conventional ordering of arguments. The rigorous version uses smeared test functions instead of point fields.

</details>

### Exercise 3: Reflection positivity as a Hilbert-space norm

Let $F$ be supported at positive Euclidean time. Explain why the OS condition

$$
\langle(\Theta F)F\rangle_E\ge0
$$

looks like a norm-squared condition after reconstruction.

<details>
<summary><strong>Solution</strong></summary>

The reflection $\Theta$ plays the role of Euclidean time reversal. In reconstruction, a positive-time functional $F$ represents a state. The inner product is defined by reflecting one factor and evaluating the Euclidean correlator:

$$
\langle F,F\rangle_{\rm OS}=\langle(\Theta F)F\rangle_E.
$$

Reflection positivity says this proposed norm is nonnegative. Without it, the reconstructed state space would have negative-norm states or no positive Hilbert-space interpretation.

</details>

### Exercise 4: Haag–Kastler isotony

Suppose $\mathcal O_1\subset\mathcal O_2$. Why should $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$?

<details>
<summary><strong>Solution</strong></summary>

Anything measurable in the smaller region $\mathcal O_1$ is also measurable if one is allowed to use the larger region $\mathcal O_2$. Therefore the algebra of observables localized in $\mathcal O_1$ should be a subalgebra of the algebra localized in $\mathcal O_2$. This monotonicity property is called isotony.

</details>

### Exercise 5: Locality in algebraic language

Let $\mathcal O_1$ and $\mathcal O_2$ be spacelike separated. State the Haag–Kastler locality condition.

<details>
<summary><strong>Solution</strong></summary>

The condition is

$$
[A,B]=0
$$

for all

$$
A\in\mathcal A(\mathcal O_1),
\qquad
B\in\mathcal A(\mathcal O_2).
$$

This is the observable-algebra version of microcausality. It says operations in spacelike-separated regions are compatible and cannot causally disturb each other.

</details>

### Exercise 6: Why gauge theory favors observable algebras

Give one reason the algebraic viewpoint is especially natural for gauge theories.

<details>
<summary><strong>Solution</strong></summary>

Gauge-fixed fields such as $A_\mu$ and ghost fields can be useful in perturbation theory, but they are not necessarily physical gauge-invariant observables on a positive Hilbert space. The algebraic viewpoint starts from the local gauge-invariant observable algebra instead. Charged sectors and gauge-dependent fields can then be treated as representation-theoretic or auxiliary structures rather than as the primitive physical observables.

</details>

## Sources and further reading

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2–5 and §§10.7–10.8, for particles, fields, cluster decomposition, causal fields, spectral representations, and dispersion/analyticity.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 3, 5–6, 13–15, 31–33, and 43, for causality, currents, Green functions, spectral representations, gauge fixing, Ward identities, and spontaneous symmetry breaking.
- M. Srednicki, *Quantum Field Theory*, §§1–5, 13, 22–24, 67–77, and 82–84, for relativistic fields, spin-statistics, LSZ, spectral representations, Ward identities, anomalies, Wilson loops, and gauge-theory examples.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the classic Wightman-axiom treatment.
- R. Haag, *Local Quantum Physics*, for the Haag–Kastler and algebraic QFT framework.
- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's functions,” for the OS axioms and reconstruction theorem.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive QFT and Euclidean methods.
- B. Simon, *The P(φ)₂ Euclidean Quantum Field Theory*, for a classic constructive model.
- H. Araki, *Mathematical Theory of Quantum Fields*, for algebraic and operator-algebraic foundations.
- K. Fredenhagen and K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, for the modern perturbative algebraic viewpoint.

## Version history

- **2026-05-24:** Initial qft.org preview of Wightman, Osterwalder–Schrader, Haag–Kastler, constructive, and algebraic QFT viewpoints, with free-scalar examples, gauge-theory caveats, and exercises.
