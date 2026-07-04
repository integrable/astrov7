---
title: "Wightman and Axiomatic QFT"
description: "Chapter overview for Wightman axioms, Hilbert-space fields, covariance, spectral positivity, locality, vacuum cyclicity, Wightman functions, reconstruction, spin–statistics, CPT, and analytic continuation in rigorous QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Jost; Haag; Glimm–Jaffe; Pauli; Lüders–Zumino; Burgoyne."
topics:
  - Wightman axioms
  - axiomatic QFT
  - Hilbert-space QFT
  - operator-valued distributions
  - reconstruction theorem
  - spin–statistics theorem
  - CPT theorem
  - Jost points
canonicalTopics:
  - wightman-axioms
  - axiomatic-quantum-field-theory
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "The Wightman framework is a standard theorem-level formulation of relativistic QFT on Minkowski spacetime using Hilbert spaces, positive energy, operator-valued distributions, covariance, locality, vacuum cyclicity, and vacuum correlation functions."
  active:
    - "Constructing physically central four-dimensional interacting gauge theories within Wightman-type hypotheses remains a major open problem, and several modern frameworks modify or reorganize the point-field perspective."
---

Wightman and Axiomatic QFT is the chapter in the Mathematical and Rigorous QFT volume where Lorentzian quantum field theory becomes a theorem-level object. It starts with Hilbert-space states, unitary spacetime symmetries, a vacuum, and operator-valued distributions, then imposes positivity, spectral support, covariance, locality, and cyclicity.

The chapter is not a construction manual for every model. It is the cleanest place to learn what it would mean for a relativistic QFT on Minkowski spacetime to satisfy precise axioms strong enough to imply structural theorems such as reconstruction, Reeh–Schlieder, CPT, spin–statistics, and analyticity properties.

Read this chapter when you want to understand what the symbols $\mathcal H$, $\Omega$, $U(a,\Lambda)$, $\phi(f)$, $\operatorname{Spec}(P)\subset\overline V_+$, and $W_n$ mean before using them in theorems.

$$
\text{Wightman QFT}
=
\text{positive-energy local fields on a Hilbert space}.
$$

## Prerequisites

You should know the smearing and domain language from the [Operator-Valued Distributions](/rigorous-qft/operator-valued-distributions/) chapter, especially [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/), and [Domains of Unbounded Operators](/rigorous-qft/operator-valued-distributions/domains-of-unbounded-operators/).

A standard first course in QFT is enough for the physics motivation: Hilbert space, vacuum, fields, Poincaré symmetry, particles, locality, and correlation functions.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) | The full axiomatic package and what each assumption is meant to control. |
| 2 | [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/) | The positive Hilbert space, common dense domain, vacuum, field polynomials, and Wightman functions as matrix elements. |
| 3 | [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) | The precise relation between spacetime transformations, unitary state transformations, smeared fields, and covariant correlators. |
| 4 | [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) | The positive-energy cone condition, its momentum-space support form, and its role in analyticity. |
| 5 | [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) | The smeared graded-commutator form of spacelike locality and what microcausality does and does not say. |
| 6 | [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) | The invariant vacuum, global cyclicity of field polynomials, and the Reeh–Schlieder local cyclicity theorem. |
| 7 | [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) | Vacuum correlation distributions and their covariance, spectral support, locality, positivity, and reconstruction role. |
| 8 | [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) | The GNS-type construction that recovers Hilbert space, vacuum, fields, positive energy, covariance, and locality from suitable $W_n$. |
| 9 | [Spin–Statistics Theorem](/rigorous-qft/wightman-axiomatic-qft/spin-statistics-theorem/) | The structural theorem tying Lorentz spin parity to Bose/Fermi graded locality under the Wightman assumptions. |
| 10 | [CPT Theorem](/rigorous-qft/wightman-axiomatic-qft/cpt-theorem/) | The antiunitary combined spacetime-reflection theorem forced by locality, covariance, spectrum, and positivity. |
| 11 | [Jost Points and Analyticity Preview](/rigorous-qft/wightman-axiomatic-qft/jost-points-and-analyticity-preview/) | The tube-domain analytic geometry behind CPT, spin–statistics, and related structural results. |

After this path, you should be able to distinguish a Wightman axiom, a Wightman-function condition, a reconstruction theorem, and a structural consequence.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\mathcal H,\Omega$ | Positive Hilbert space and invariant vacuum. | Positivity, cyclicity, reconstruction. |
| $\phi_i(f):\mathcal D\to\mathcal D$ | Smeared operator-valued distribution on a common dense domain. | Locality, Wightman functions, structural theorems. |
| $U(a,\Lambda)$ | Strongly continuous unitary representation of spacetime symmetries. | Covariance and the spectral condition. |
| $\operatorname{Spec}(P)\subset\overline V_+$ | Positive-energy condition for the joint translation spectrum. | Tube analyticity, CPT, spin–statistics. |
| $[\phi_i(f),\phi_j(g)]_\gamma=0$ | Local graded commutativity for spacelike separated supports. | Microcausality, spin–statistics, weak locality. |
| $W_n$ | Vacuum $n$-point distribution. | Positivity, locality, reconstruction, analyticity. |
| $\langle F,G\rangle_0=\underline W(F^*G)$ | Reconstruction inner product on field-polynomial test-function sequences. | Wightman reconstruction theorem. |
| $(-1)^{2(j+k)}$ | Spin parity of a Lorentz representation $(j,k)$. | Spin–statistics theorem. |
| $\Theta$ | Antiunitary CPT operator. | CPT theorem and discrete spacetime symmetries. |
| $\mathcal T^-_{n-1}$ and Jost points | Tube analyticity and its real spacelike boundary configurations. | CPT, spin–statistics, crossing-type analytic arguments. |

## Common confusions

**The axioms are not a path integral.** A path integral may motivate a model, but the Wightman data are Hilbert-space and distributional data.

**Point fields are not literal point operators.** The Wightman field is $\phi(f)$, with $f$ a test function. The notation $\phi(x)$ is kernel notation.

**Covariance, spectrum, locality, and cyclicity are distinct.** Covariance says how fields transform. The spectral condition says energy-momentum lies in $\overline V_+$. Locality says spacelike separated fields commute or graded-commute. Cyclicity says fields generate the Hilbert-space sector from the vacuum.

**Microcausality does not mean correlations vanish.** Spacelike vacuum correlations may be nonzero. The commutator or graded commutator is what vanishes.

**Wightman functions are not Feynman propagators.** Wightman functions are ordered vacuum correlators; Feynman correlators are time-ordered combinations of Wightman functions.

**Reconstruction is conditional.** It turns admissible correlation functions into a theory, but it does not magically construct admissible interacting four-dimensional correlation functions.

**Spin–statistics and CPT are not canonical quantization rules.** In the Wightman framework they are theorems, and the hypotheses are part of the claim.

**Jost points are not just any pairwise spacelike configuration.** For more than two insertions, the ordered positive-combination condition is stronger than checking a few pairwise intervals.

**A theorem framework is not an existence theorem.** The axioms state what it means for a theory to exist in this sense. Constructing nontrivial examples is a separate problem.

## Boundaries

This chapter is about Wightman-style point fields on Minkowski spacetime. It does not replace algebraic QFT, which often treats local algebras as more intrinsic than fields. It also does not replace Osterwalder–Schrader Euclidean QFT, where Schwinger functions and reflection positivity are the starting point.

The chapter initially emphasizes scalar and finite-component fields. Gauge theories, charged sectors, infraparticles, and massless long-range forces require additional qualifications.

The chapter also does not teach all of representation theory, functional analysis, distribution theory, or several-complex-variable analytic methods. It introduces the pieces needed to understand the Wightman axioms and their consequences.

## Where to go next

For the distributional foundations behind point fields, return to [Operator-Valued Distributions](/rigorous-qft/operator-valued-distributions/). For a modern analytic tool used later in curved spacetime and perturbative algebraic QFT, read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/).

After this chapter, the Euclidean counterpart is the Osterwalder–Schrader chapter, beginning with Schwinger functions, reflection positivity, and Euclidean reconstruction. Algebraic QFT then recasts locality and covariance in terms of local observable algebras rather than chosen point fields.

## References

### Standard first pass

- A. S. Wightman, "Quantum Field Theory in Terms of Vacuum Expectation Values," *Physical Review* **101** (1956), 860–866. DOI: [10.1103/PhysRev.101.860](https://doi.org/10.1103/PhysRev.101.860).
- W. Pauli, "The Connection Between Spin and Statistics," *Physical Review* **58** (1940), 716–722. DOI: [10.1103/PhysRev.58.716](https://doi.org/10.1103/PhysRev.58.716).
- G. Lüders and B. Zumino, "Connection between Spin and Statistics," *Physical Review* **110** (1958), 1450–1453. DOI: [10.1103/PhysRev.110.1450](https://doi.org/10.1103/PhysRev.110.1450).
- G. Lüders and B. Zumino, "Some Consequences of TCP-Invariance," *Physical Review* **106** (1957), 385–386. DOI: [10.1103/PhysRev.106.385](https://doi.org/10.1103/PhysRev.106.385).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.

### Deeper references

- D. Hall and A. S. Wightman, "A Theorem on Invariant Analytic Functions with Applications to Relativistic Quantum Field Theory," *Matematisk-Fysiske Meddelelser* **31**, no. 5 (1957).
- H. Reeh and S. Schlieder, "Bemerkungen zur Unitäräquivalenz von Lorentzinvarianten Feldern," *Il Nuovo Cimento* **22** (1961), 1051–1068. DOI: [10.1007/BF02787889](https://doi.org/10.1007/BF02787889).
- H.-J. Borchers, "On Structure of the Algebra of Field Operators," *Il Nuovo Cimento* **24** (1962), 214–236. DOI: [10.1007/BF02745645](https://doi.org/10.1007/BF02745645).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

## Version history

- **2026-06-28:** Updated after adding the CPT theorem and Jost-point analyticity preview.
- **2026-06-28:** Updated after adding reconstruction and spin–statistics pages.
- **2026-06-28:** Updated after adding the vacuum cyclicity and Wightman functions pages.
- **2026-06-28:** Updated after adding the spectral condition and locality pages.
- **2026-06-28:** Initial polished overview after the chapter reached three ordinary pages.
