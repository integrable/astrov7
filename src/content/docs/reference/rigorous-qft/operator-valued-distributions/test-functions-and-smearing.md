---
title: "Test Functions and Smearing"
description: "Defines the test-function spaces and smeared fields used to turn distributional quantum fields into operator-valued objects."
sidebar:
  label: "Test Functions and Smearing"
  order: 2
level: Graduate
status: "Polished draft"
source: "Schwartz; Reed–Simon; Streater–Wightman; Haag; Hollands–Wald; Rejzner."
topics:
  - test functions
  - smearing
  - supports
  - Wightman fields
  - distribution theory
canonicalTopics:
  - test-functions
  - smearing
  - operator-valued-distribution
researchStatus:
  established:
    - "Smearing fields with smooth test functions is the standard way to formulate pointlike fields as operator-valued distributions."
    - "Support properties of test functions give the precise smeared form of locality and microcausality."
  active:
    - "In gauge theory, curved spacetime, and perturbative interacting QFT, the correct test objects are often sections, densities, local functionals, or cohomological observables rather than scalar functions alone."
---

## Summary

Smearing is the operation that turns a distributional field into an operator. Instead of trying to use $\phi(x)$ as an operator at a point, one chooses a smooth test function $f$ and defines

$$
\phi(f)=\langle \phi,f\rangle
=\int d^dx\,\phi(x)f(x).
$$

The integral sign is notation. The actual definition is the pairing between an operator-valued distribution and a test function.

The two most common test-function spaces are

$$
\mathcal D(M)=C_c^\infty(M),
\qquad
\mathcal S(\mathbb R^d),
$$

where $C_c^\infty(M)$ consists of compactly supported smooth functions and $\mathcal S(\mathbb R^d)$ consists of rapidly decaying smooth functions. Compact support is ideal for locality. Schwartz functions are ideal for Fourier analysis and Wightman tempered distributions on Minkowski space.

Smearing also makes locality precise:

$$
[\phi(f),\psi(g)]_\pm=0
\quad\text{if}\quad
\operatorname{supp}f
\quad\text{and}\quad
\operatorname{supp}g
\quad\text{are spacelike separated}.
$$

<figure class="doc-figure" style="--figure-width: 40rem;">

![Spacelike separated smearing supports](/figures/rigorous-qft/spacelike-smearing-locality.svg)

<figcaption>

Locality for fields is most cleanly stated after smearing: if every point of $\operatorname{supp}f$ is spacelike to every point of $\operatorname{supp}g$, the smeared commutator or anticommutator vanishes.

</figcaption>
</figure>

## Prerequisites

Read [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) first. You should be comfortable with smooth functions, Fourier transforms, supports, and the idea that a distribution is a continuous linear functional on a space of test functions.

This page uses the site-wide mostly-minus convention and Fourier convention from [Conventions and Logical Status](/rigorous-qft/conventions/).

## Core idea

A distribution is not defined by its value at a point. It is defined by how it acts on test functions. The same principle applies to quantum fields. The field symbol $\phi(x)$ is a useful kernel notation, but the object controlled by the axioms is $\phi(f)$.

A test function does three jobs at once.

| Role | What it controls | Why it matters in QFT |
|---|---|---|
| Smoothness | No sharp jumps or point probes. | Distributions can act on it. |
| Support or decay | Where the probe is localized. | Locality and Fourier estimates become meaningful. |
| Topology | What convergence of probes means. | Continuity of fields and correlators can be stated. |

The topology is not decorative. Saying that $\phi$ is a distribution means that $f\mapsto\phi(f)$ behaves continuously with respect to the chosen test-function topology after taking matrix elements.

## Setup and conventions

On Minkowski space $\mathbb R^d$, the default Wightman choice is often the Schwartz space $\mathcal S(\mathbb R^d)$. A function $f$ lies in $\mathcal S(\mathbb R^d)$ if $f$ is smooth and every polynomially weighted derivative is bounded:

$$
\sup_{x\in\mathbb R^d}
|x^\alpha\partial^\beta f(x)|<\infty
\quad\text{for all multiindices}\quad
\alpha,\beta.
$$

The dual space $\mathcal S'(\mathbb R^d)$ is the space of tempered distributions. Tempered distributions are well adapted to Fourier transforms.

On a general smooth spacetime $M$, especially in algebraic or curved-spacetime QFT, the natural scalar test-function space is

$$
\mathcal D(M)=C_c^\infty(M),
$$

with dual $\mathcal D'(M)$. Compact support lets one assign a field to a bounded spacetime region and state locality by support separation.

For fields with indices or internal structure, test functions should be replaced by compactly supported smooth sections of the appropriate dual bundle, often with density factors included. For example, a vector field $A_\mu$ is naturally smeared against a compactly supported test vector density or one-form, depending on convention.

## The smeared field as an operator-valued distribution

Let $\mathcal H$ be a Hilbert space and $\mathcal D\subset\mathcal H$ a dense invariant domain. A scalar operator-valued distribution is a linear map

$$
f\longmapsto \phi(f)
$$

from a test-function space to operators on $\mathcal D$ such that, for all $\Psi,\Phi\in\mathcal D$,

$$
f\longmapsto
\langle\Psi,\phi(f)\Phi\rangle
$$

is an ordinary scalar distribution.

This is a weak definition: the field is tested through matrix elements. That is the right level of generality because smeared fields are usually unbounded. One should not silently assume that $\phi(f)$ is bounded or defined on all Hilbert-space vectors.

For a real scalar field, one commonly imposes the domain adjoint relation

$$
\langle \Psi,\phi(f)\Phi\rangle
=
\langle \phi(\overline f)\Psi,\Phi\rangle,
$$

whenever the vectors lie in the common domain. Equivalently, one writes

$$
\phi(f)^\dagger\supset \phi(\overline f).
$$

For real $f$, this says that $\phi(f)$ is symmetric on the domain. Essential self-adjointness is a separate theorem or model-dependent fact.

## Support and localization

The support of a test function $f$ is the closure of the set where $f$ is nonzero:

$$
\operatorname{supp}f
=
\overline{\{x:f(x)\ne0\}}.
$$

If $\operatorname{supp}f\subset\mathcal O$, then $\phi(f)$ is localized in the spacetime region $\mathcal O$. This gives a rigorous version of the informal phrase "field in a region."

Two supports $K_1,K_2\subset\mathbb R^d$ are spacelike separated if every pair of points $x\in K_1$, $y\in K_2$ is spacelike separated:

$$
(x-y)^2<0
\quad\text{for all}\quad
x\in K_1,
\ y\in K_2.
$$

The Wightman locality condition for bosonic scalar fields can then be stated as

$$
[\phi(f),\phi(g)]=0
\quad\text{if}\quad
\operatorname{supp}f
\text{ and }
\operatorname{supp}g
\text{ are spacelike separated}.
$$

For fermionic fields, the corresponding statement uses anticommutators for odd fields.

This support language is one reason $C_c^\infty$ is so important. A Schwartz function is excellent for momentum-space estimates, but it usually has support everywhere. Compact support is the cleanest language for strict localization.

## Derivatives move onto the test function

Distributional derivatives are defined by integration by parts. If $\partial_\mu\phi$ is the derivative field, then

$$
(\partial_\mu\phi)(f)
=
-\phi(\partial_\mu f),
$$

assuming the coordinate volume form is fixed and boundary terms vanish because $f$ is compactly supported or rapidly decaying.

This identity is more than notation. It says that differentiated fields can be defined even when the field itself has no pointwise derivative. The derivative acts on the smooth probe, not on a nonexistent pointwise operator.

For example, the Klein–Gordon equation for a free scalar field can be written distributionally as

$$
\phi((\Box+m^2)f)=0
\quad\text{for all test functions}\quad f,
$$

up to the sign conventions induced by moving derivatives between the distribution and the test function. This is the rigorous version of $(\Box+m^2)\phi=0$.

## Fourier-space smearing

With the convention

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^dx\,e^{ip\cdot x}f(x),
$$

Schwartz functions remain Schwartz under Fourier transform. This is why they are so convenient for Wightman theory.

For the free scalar field, the on-shell part of a test function is

$$
f_+(\mathbf p)
=
\widetilde f(E_{\mathbf p},\mathbf p),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The one-particle norm of a smeared field applied to the vacuum is controlled by

$$
\|\phi(f)\Omega\|^2
=
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
\,|f_+(\mathbf p)|^2,
$$

up to harmless convention choices. Since $f_+$ decays rapidly, the integral is finite. Replacing $f$ by a delta function would remove this decay and reintroduce the ultraviolet divergence.

## Delta sequences and the point-field limit

One often approximates a point by a family of test functions $\rho_\epsilon$ with shrinking support or width:

$$
\rho_{\epsilon,x_0}(x)
=
\epsilon^{-d}\rho\!\left(\frac{x-x_0}{\epsilon}\right),
\qquad
\int d^dx\,\rho(x)=1.
$$

As $\epsilon\to0$, $\rho_{\epsilon,x_0}$ converges to $\delta_{x_0}$ as a distribution. But this does **not** imply that $\phi(\rho_{\epsilon,x_0})$ converges to an operator. In typical QFTs, the norm of $\phi(\rho_{\epsilon,x_0})\Omega$ diverges as the probe becomes infinitely sharp.

Thus a point field is not usually the limit of honest operators in Hilbert-space norm. It is a distributional kernel for smeared fields and correlation functions.

## Which test-function space should a page use?

Use the following defaults unless a page says otherwise.

| Situation | Default test objects | Reason |
|---|---|---|
| Wightman fields on $\mathbb R^d$ | $\mathcal S(\mathbb R^d)$ | Tempered distributions and Fourier transforms. |
| Locality statements | $C_c^\infty(\mathbb R^d)$ or compactly supported sections | Supports encode spacetime localization. |
| Curved spacetime | $C_c^\infty(M)$ or compactly supported sections/densities | No global Fourier transform is available. |
| Euclidean random fields | Test functions in $C_c^\infty$ or $\mathcal S$, depending on construction | Correlators are random distributions. |
| Gauge fields | Test sections modulo gauge or BRST/BV-compatible test objects | Gauge redundancy changes the observable content. |

The choice of test space is part of the definition. Changing it can change continuity, locality, infrared behavior, and the class of allowed distributions.

## Common pitfalls

**Using a delta function as a test function.** The delta distribution is not a smooth test function. It can be used to write kernels, but substituting $f=\delta_x$ into $\phi(f)$ is usually not a legitimate operator construction.

**Forgetting the topology.** A distribution is continuous with respect to a specific test-function topology. Merely saying "linear functional on smooth functions" is not enough.

**Confusing compact support with rapid decay.** Compact support is best for exact locality. Rapid decay is best for Fourier analysis. Both are useful, but they are not the same condition.

**Assuming smearing makes operators bounded.** Smeared fields are typically unbounded. Domain questions begin after smearing, not before it.

**Ignoring bundle type.** Spinor, vector, tensor, and gauge fields should be smeared with test objects of the correct dual type. A scalar test function is not always the right object.

## Relations to other pages

- [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/) explains the conceptual reason smearing is necessary.
- [Conventions and Logical Status](/rigorous-qft/conventions/) fixes distribution and support notation.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) refines support by tracking cotangent directions of singularities.
- Later pages on domains of unbounded operators and two-point functions as distributions use this page's smeared-field notation.

## Research status

The use of smooth test functions and smeared operator-valued distributions is a settled part of Wightman and algebraic QFT. In curved-spacetime QFT, compactly supported test sections are essential because global momentum-space methods are unavailable.

The active questions concern richer test objects and richer notions of locality: local functionals in perturbative algebraic QFT, gauge-invariant or BRST/BV cohomological observables in gauge theories, boundary-supported observables, defects, extended operators, and distributional products constrained by wavefront sets.

## Exercises

### Exercise 1: Derivative sign

Let $T$ be a scalar distribution on $\mathbb R^d$. Show that the derivative distribution satisfies

$$
\langle \partial_\mu T,f\rangle
=-\langle T,\partial_\mu f\rangle.
$$

Use this to explain the formula $(\partial_\mu\phi)(f)=-\phi(\partial_\mu f)$.

<details>
<summary><strong>Solution</strong></summary>

For an ordinary smooth function $T(x)$ with sufficient decay,

$$
\int d^dx\,(\partial_\mu T)f
=-\int d^dx\,T(\partial_\mu f),
$$

because the boundary term vanishes. The distributional definition preserves this integration-by-parts identity. An operator-valued distribution is tested through matrix elements, so the same formula holds after replacing $T$ by $\phi$.

</details>

### Exercise 2: Compact support and locality

Why is $C_c^\infty(M)$ better suited than $\mathcal S(\mathbb R^d)$ for stating exact spacelike separation of two smeared fields?

<details>
<summary><strong>Solution</strong></summary>

A generic Schwartz function decays rapidly but is nonzero everywhere, so its support is all of spacetime. Exact spacelike separation of supports is therefore hard or impossible to express with generic Schwartz functions. Compactly supported test functions can be chosen inside bounded spacetime regions, making the condition "every point of one support is spacelike to every point of the other" precise.

</details>

### Exercise 3: Delta functions are not test functions

Let $\rho_{\epsilon,x_0}$ be a smooth approximate identity converging to $\delta_{x_0}$. Explain why convergence of $\rho_{\epsilon,x_0}$ to $\delta_{x_0}$ as distributions does not imply convergence of $\phi(\rho_{\epsilon,x_0})$ as operators.

<details>
<summary><strong>Solution</strong></summary>

The field $\phi$ is continuous on a chosen test-function space, not on arbitrary distributional limits. The sequence $\rho_{\epsilon,x_0}$ becomes increasingly sharp and does not converge to a test function in the test-function topology. In typical QFTs, ultraviolet fluctuations make $\|\phi(\rho_{\epsilon,x_0})\Omega\|$ diverge as $\epsilon\to0$.

</details>

### Exercise 4: Choosing the right test object

A conserved current $j^\mu(x)$ is formally coupled to a background one-form $A_\mu(x)$ by $\int j^\mu A_\mu$. What kind of test object should smear $j^\mu$?

<details>
<summary><strong>Solution</strong></summary>

The current has a vector index, so it should be smeared against a compactly supported covector or one-form density, depending on the geometric convention. The pairing should contract indices and include the volume density. On a curved spacetime or in a coordinate-invariant formulation, this bundle type matters.

</details>

## References

- L. Schwartz, *Théorie des distributions*, Hermann, 1950–1951.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- A. S. Wightman, "How It Was Learned that Quantized Fields Are Operator-Valued Distributions," *Fortschritte der Physik* **44** (1996), 143–178. DOI: [10.1002/prop.2190440204](https://doi.org/10.1002/prop.2190440204).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- S. Hollands and R. M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. DOI: [10.1016/j.physrep.2015.02.001](https://doi.org/10.1016/j.physrep.2015.02.001), arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).
- K. Fredenhagen and K. Rejzner, "Perturbative Algebraic Quantum Field Theory," arXiv: [1208.1428](https://arxiv.org/abs/1208.1428).

## Version history

- **2026-06-28:** Initial polished draft for the Operator-Valued Distributions chapter.
