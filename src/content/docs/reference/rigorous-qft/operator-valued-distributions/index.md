---
title: "Operator-Valued Distributions"
description: "Chapter overview for fields as operator-valued distributions, smearing, supports, domains, and distributional correlators in rigorous QFT."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Schwartz; Reed–Simon; Haag; Hollands–Wald."
topics:
  - operator-valued distributions
  - smearing
  - test functions
  - Wightman fields
  - locality
canonicalTopics:
  - operator-valued-distribution
  - rigorous-quantum-field-theory
  - distribution-theory
researchStatus:
  established:
    - "The distributional formulation of pointlike quantum fields is a standard part of Wightman-style rigorous QFT."
  active:
    - "The construction of composite fields, time-ordered products, gauge-invariant observables, and interacting fields requires additional framework-dependent machinery."
---

Operator-Valued Distributions is the chapter in the Mathematical and Rigorous QFT volume where the familiar symbol $\phi(x)$ receives its first theorem-level correction. A quantum field is usually not an operator at a spacetime point. It is an operator-valued distribution that becomes an operator only after smearing against a test function.

This chapter explains why that statement is not pedantry. The singularities of QFT already appear in the free scalar field, in canonical commutation relations, and in the short-distance behavior of two-point functions. Smearing is the mathematical operation that keeps locality, covariance, and Hilbert-space positivity visible without pretending that point fields are ordinary functions.

Read this chapter before the Wightman axioms. The Wightman framework assumes fields are operator-valued distributions; this chapter explains what that means and how to use the notation safely.

$$
\phi(x)\ \text{is kernel notation},
\qquad
\phi(f)=\int d^dx\,\phi(x)f(x)
\ \text{is the operator object}.
$$

## Prerequisites

You should know the distributional notation fixed in [Conventions and Logical Status](/rigorous-qft/conventions/) and the distinction between physics notation and theorem-level claims from [Physics QFT versus Mathematical QFT](/rigorous-qft/what-is-rigorous-qft/physics-qft-versus-mathematical-qft/).

A first course in QFT is enough background for the first pass. The chapter uses the free scalar field, two-point functions, commutators, and the idea of spacelike separation.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) | The conceptual and mathematical reason point fields are too singular to be operators. |
| 2 | [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) | The test-function spaces, support language, derivative rules, and smeared locality statements used throughout rigorous QFT. |

After this path, you should be able to read $\phi(x)$ as distributional kernel notation and $\phi(f)$ as the actual field operator associated with a smooth spacetime probe.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\phi(f)$ | Smeared field operator associated with a test function $f$. | Wightman fields, local observables, free-field examples. |
| $C_c^\infty(M)$ | Smooth compactly supported test functions. | Locality, curved spacetime, algebraic QFT. |
| $\mathcal S(\mathbb R^d)$ | Schwartz test functions. | Tempered distributions, Fourier transforms, Wightman functions. |
| $\operatorname{supp}f$ | Region where the probe is localized. | Microcausality and local nets. |
| $[\phi(f),\psi(g)]_\pm=0$ | Smeared locality for spacelike separated supports. | Wightman axioms, spin–statistics, algebraic locality. |
| $\partial_\mu\phi(f)=-\phi(\partial_\mu f)$ | Distributional derivative rule. | Equations of motion, currents, Ward identities. |
| Point-field limit | A delta sequence need not converge to an operator. | UV singularities, composite fields, renormalization. |

## Common confusions

**Smearing is not optional decoration.** It is part of the definition of a pointlike quantum field in the Wightman sense.

**The delta function is not a test function.** Delta functions help write kernels, but replacing a smooth probe by $\delta_x$ is usually not a valid operator construction.

**Distributional does not mean vague.** Distributions have precise continuity, support, derivative, Fourier-transform, and pullback properties.

**Smearing a field does not define products of fields.** A single smeared field $\phi(f)$ may be well-defined while $\phi(x)^2$, time-ordered products, or composite operators remain singular.

**Smeared does not mean nonlocal in the bad sense.** A compactly supported test function localizes the operator in a definite spacetime region. One can make this region arbitrarily small, but not a point without changing the mathematical type of the object.

## Boundaries

This chapter does not teach all of distribution theory. It introduces only the part needed to understand quantum fields as operator-valued distributions.

It also does not fully solve operator-domain questions. Smeared fields are typically unbounded, so domains, adjoints, and essential self-adjointness require a later page.

The chapter stops before composite fields and renormalization. Normal ordering, Wick powers, time-ordered products, and Epstein–Glaser extension of singular distributions need additional machinery.

## Where to go next

The immediate next page in this chapter should be a page on domains of unbounded operators. That page will explain why smearing fixes point singularities but does not make field operators bounded.

For a modern tool that controls when distributional products are possible, read [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/). For the axiomatic framework that uses smeared fields as input, continue to the Wightman and Axiomatic QFT chapter once its first pages are written.

## References

- L. Schwartz, *Théorie des distributions*, Hermann, 1950–1951.
- L. Gårding and A. S. Wightman, "Fields as Operator-Valued Distributions in Relativistic Quantum Theory," *Arkiv för Fysik* **28** (1964/65), 129–184.
- A. S. Wightman, "How It Was Learned that Quantized Fields Are Operator-Valued Distributions," *Fortschritte der Physik* **44** (1996), 143–178. DOI: [10.1002/prop.2190440204](https://doi.org/10.1002/prop.2190440204).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- S. Hollands and R. M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. DOI: [10.1016/j.physrep.2015.02.001](https://doi.org/10.1016/j.physrep.2015.02.001), arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).

## Version history

- **2026-06-28:** Initial polished overview after the chapter reached two ordinary pages.
