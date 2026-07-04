---
title: "P(φ)₂ Models"
description: "Explains the constructive Euclidean definition of two-dimensional polynomial scalar field models using Gaussian reference measures, Wick ordering, cutoff removal, and OS reconstruction."
sidebar:
  label: "P(φ)₂ Models"
  order: 4
level: Advanced
status: "Polished draft"
source: "Simon P(φ)₂; Glimm–Jaffe functional integrals; Guerra–Rosen–Simon statistical mechanics; Glimm–Jaffe–Spencer particle structure."
topics:
  - P(phi)2 models
  - constructive QFT
  - Wick ordering
  - Euclidean measures
  - scalar field theory
canonicalTopics:
  - constructive-quantum-field-theory
  - p-phi-two-models
  - euclidean-quantum-field-theory
  - wick-ordering
researchStatus:
  established:
    - 'The $P(\phi)_2$ family is one of the classic rigorous constructions of interacting relativistic quantum field theories in two spacetime dimensions.'
  active:
    - "The detailed phase structure, particle content, and scaling behavior depend on the potential and parameter regime; these are stronger questions than bare existence of the Euclidean measure."
---

## Summary

The $P(\phi)_2$ models are two-dimensional scalar quantum field theories with polynomial interaction. The notation means:

$$
P(\phi)_2
=
\text{polynomial interaction }P(\phi)
\text{ in two Euclidean dimensions}.
$$

After Osterwalder–Schrader reconstruction, two Euclidean dimensions correspond to one time and one space dimension in Lorentzian signature.

The rough formal expression is

$$
\frac1Z
\int \mathcal D\phi\,
\exp\left[-\int_{\mathbb R^2}
\left(\frac12|\nabla\phi|^2+\frac12m^2\phi^2+P(\phi)\right)d^2x
\right]\mathcal O(\phi).
$$

The constructive definition replaces this slogan by a precise measure. One starts with the massive Gaussian free-field measure $\mu_C$, introduces finite-volume and ultraviolet cutoffs, Wick-orders the polynomial, proves convergence, takes limits, and verifies the Euclidean axioms.

For a polynomial

$$
P(X)=\sum_{n=0}^{2N}a_nX^n
$$

with positive leading coefficient and suitable lower-boundedness, the finite-cutoff interaction is schematically

$$
V_{\Lambda,\epsilon}(\phi)
=
\int_\Lambda :\!P(\phi_\epsilon(x))\!:\,d^2x,
$$

and the finite-volume measure is

$$
d\mu_{\Lambda,\epsilon}(\phi)
=
Z_{\Lambda,\epsilon}^{-1}
\exp[-V_{\Lambda,\epsilon}(\phi)]\,d\mu_C(\phi).
$$

The theorem-level achievement is that this can be made into an actual interacting continuum QFT in two dimensions, not merely a formal perturbation series.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/). Wick ordering is motivated here but will also be used in later pages on $\phi^4_2$ and $\phi^4_3$.

## Core idea

The two-dimensional scalar free field is too singular to substitute into a polynomial pointwise. In particular,

$$
\mathbb E[\phi(x)^2]
$$

is infinite when interpreted naively. The interaction $P(\phi(x))$ therefore needs renormalization before it can appear in an exponential density.

In two dimensions, the necessary ultraviolet renormalization for polynomial scalar interactions is captured by Wick ordering with respect to the free covariance. This makes $P(\phi)_2$ the first major family of interacting continuum QFTs where the path-integral story can be turned into a full construction.

<figure class="doc-figure" style="--figure-width: 46rem;">

![P phi two construction](/figures/rigorous-qft/p-phi-two-construction.svg)

<figcaption>

The constructive pipeline for $P(\phi)_2$ starts from the free Gaussian measure, introduces cutoffs and Wick ordering, proves convergence of the finite-volume measures or their moments, takes ultraviolet and thermodynamic limits, and then uses the resulting Schwinger functions as input for OS reconstruction.

</figcaption>
</figure>

The key distinction is this:

$$
\text{writing }P(\phi)
\text{ is formal};
\qquad
\text{constructing }:\!P(\phi)\!:
\text{ as a limit is mathematical data}.
$$

## Setup and conventions

Work on Euclidean $\mathbb R^2$ with coordinates $x=(\tau,y)$ and free covariance

$$
C=(-\Delta+m^2)^{-1},
\qquad m>0.
$$

Let $\mu_C$ be the corresponding massive Gaussian measure on $\mathcal S'(\mathbb R^2)$. Let $\rho_\epsilon$ be a mollifier and define

$$
\phi_\epsilon(x)
=
\phi(\rho_\epsilon(x-\cdot)).
$$

Let $\Lambda\subset\mathbb R^2$ be a bounded region. For the first pass, take $\Lambda$ to be a box symmetric under Euclidean time reflection, because reflection positivity must be preserved in the limit.

A typical polynomial potential is

$$
P(X)=a_{2N}X^{2N}+a_{2N-1}X^{2N-1}+\cdots+a_0,
\qquad a_{2N}>0.
$$

The positivity of the leading coefficient is not a decorative assumption. It is what prevents the exponential weight from being uncontrollably large in the wrong direction. More refined hypotheses appear in the full constructive theorems, but boundedness from below is the guiding principle.

## What the subscript ₂ means

The subscript in $P(\phi)_2$ refers to the total Euclidean dimension, not to the power of $\phi$. Thus:

| Notation | Meaning |
|---|---|
| $P(\phi)_2$ | Any suitable polynomial interaction in two Euclidean dimensions. |
| $\phi^4_2$ | The special case $P(\phi)=\lambda\phi^4$ plus lower-order terms. |
| two Euclidean dimensions | Reconstructs a Lorentzian theory in $1+1$ dimensions. |
| polynomial degree | Determined by $P$, independent of the subscript. |

This notation is historically standard in constructive QFT. It is easy to misread if one first encounters it through the physics notation for powers of fields.

## The cutoff interaction

For fixed $\epsilon>0$, the mollified field $\phi_\epsilon(x)$ is an ordinary Gaussian random variable. One can define the Wick-ordered monomials by Hermite polynomials. In particular,

$$
:\!\phi_\epsilon^2\!:(x)
=
\phi_\epsilon(x)^2-c_\epsilon,
$$

and

$$
:\!\phi_\epsilon^4\!:(x)
=
\phi_\epsilon(x)^4
-6c_\epsilon\phi_\epsilon(x)^2
+3c_\epsilon^2,
$$

where

$$
c_\epsilon
=
\mathbb E_{\mu_C}[\phi_\epsilon(x)^2].
$$

In two dimensions,

$$
c_\epsilon
\sim
\frac{1}{2\pi}\log\frac1\epsilon
+O(1)
$$

for standard radial mollifiers. The logarithmic divergence is exactly what Wick ordering subtracts.

For a polynomial $P$, define

$$
:\!P(\phi_\epsilon(x))\!:
=
\sum_{n=0}^{2N}a_n:\!\phi_\epsilon(x)^n\!:.
$$

Then the cutoff potential is

$$
V_{\Lambda,\epsilon}(\phi)
=
\int_\Lambda :\!P(\phi_\epsilon(x))\!:\,d^2x.
$$

The finite-cutoff measure is

$$
d\mu_{\Lambda,\epsilon}(\phi)
=
Z_{\Lambda,\epsilon}^{-1}
\exp[-V_{\Lambda,\epsilon}(\phi)]\,d\mu_C(\phi),
$$

where

$$
Z_{\Lambda,\epsilon}
=
\int \exp[-V_{\Lambda,\epsilon}(\phi)]\,d\mu_C(\phi).
$$

For fixed $\Lambda$ and $\epsilon$, this is an honest probability measure. The constructive problem is what happens as $\epsilon\downarrow0$ and $\Lambda\uparrow\mathbb R^2$.

## Example: the Wick quartic

The formal quartic interaction

$$
\lambda\int_\Lambda \phi(x)^4\,d^2x
$$

is replaced by

$$
\lambda\int_\Lambda :\!\phi_\epsilon(x)^4\!:\,d^2x.
$$

Using the formula above,

$$
\lambda:\!\phi_\epsilon^4\!:
=
\lambda\phi_\epsilon^4
-6\lambda c_\epsilon\phi_\epsilon^2
+3\lambda c_\epsilon^2.
$$

The second term is the familiar mass-counterterm pattern, and the last term is a vacuum-energy counterterm. In two dimensions these Wick subtractions are enough to define the ultraviolet limit of the local quartic interaction in finite volume.

This does not mean that the theory is physically trivial. It means that the ultraviolet renormalization is mild enough that the interacting measure can be controlled directly.

## Ultraviolet limit in finite volume

For a fixed bounded $\Lambda$, the goal is to define

$$
V_\Lambda(\phi)
=
\lim_{\epsilon\downarrow0}V_{\Lambda,\epsilon}(\phi)
$$

in a function space such as $L^p(d\mu_C)$. The corresponding densities

$$
\exp[-V_{\Lambda,\epsilon}]
$$

must also converge strongly enough to define a limiting finite-volume measure

$$
d\mu_\Lambda(\phi)
=
Z_\Lambda^{-1}
\exp[-V_\Lambda(\phi)]\,d\mu_C(\phi).
$$

This step is where Gaussian hypercontractivity, Nelson-type estimates, and stability bounds enter. The informal reason the construction works is that Wick powers of the two-dimensional free field are still controllable after smearing is removed. The formal reason is a package of estimates that bound the exponential of the renormalized local polynomial.

The finite-volume Schwinger functions are then

$$
S_{n,\Lambda}(f_1,
\ldots,f_n)
=
\int \phi(f_1)\cdots\phi(f_n)\,d\mu_\Lambda(\phi).
$$

## Thermodynamic limit

The next step is to let the volume grow:

$$
\Lambda\uparrow\mathbb R^2.
$$

One usually studies convergence of Schwinger functions with compactly supported test functions:

$$
S_n(f_1,
\ldots,f_n)
=
\lim_{\Lambda\uparrow\mathbb R^2}
S_{n,\Lambda}(f_1,
\ldots,f_n).
$$

This limit is not merely a technicality. Infinite-volume limits can depend on boundary conditions or on the way external fields are removed. This is how phase structure enters the constructive theory.

For convex or weakly coupled situations, one may get a unique translation-invariant state with clustering. For double-well potentials or strong-coupling regimes, multiple phases and symmetry breaking can occur. Thus the phrase "the $P(\phi)_2$ model" should be read with parameter and state data in mind.

## What the construction proves

A mature $P(\phi)_2$ construction can establish several kinds of statements, with different strengths.

| Claim | Meaning |
|---|---|
| Finite-volume existence | $d\mu_\Lambda$ exists after the UV cutoff is removed. |
| Infinite-volume Schwinger functions | Limits of $S_{n,\Lambda}$ exist for compactly supported test functions. |
| Euclidean covariance | The limiting Schwinger functions are invariant under translations and rotations. |
| Reflection positivity | The Euclidean theory reconstructs a positive Hilbert-space inner product. |
| Wightman reconstruction | The Schwinger functions give Lorentzian Wightman fields. |
| Clustering | Distant observables factorize in a selected vacuum or phase. |
| Mass gap | Correlations decay exponentially, or the Hamiltonian spectrum has a gap. |
| Particle structure | There is an isolated one-particle mass shell and scattering theory can be studied. |

These are not all automatic consequences of the same estimate. For example, existence of a Euclidean measure is weaker than a detailed theorem about one-particle states.

The classic Glimm–Jaffe–Spencer particle-structure theorem is a stronger result for weakly coupled $P(\phi)_2$ models: it verifies Wightman axioms and identifies isolated low-lying mass spectrum under suitable assumptions. The Guerra–Rosen–Simon work emphasizes the Euclidean model as a classical statistical mechanical system. Both perspectives are part of the constructive story.

## Why two dimensions are special

The singularity of the free field worsens with dimension. The massive covariance behaves near coincident points as

$$
C_m(x)
\sim
\begin{cases}
-\dfrac{1}{2\pi}\log |x|, & d=2,\\
\dfrac{\text{const.}}{|x|^{d-2}}, & d\ge3.
\end{cases}
$$

The logarithmic divergence in two dimensions is mild enough that Wick ordering controls polynomial interactions. In three dimensions, $\phi^4_3$ is still constructible, but it requires additional counterterms and deeper multiscale estimates. In four dimensions, the scalar $\phi^4_4$ continuum-limit problem is tied to triviality rather than to a straightforward extension of $P(\phi)_2$ methods.

Thus $P(\phi)_2$ is not a toy because it is useless. It is a toy because it is the first place where the full rigorous nonperturbative logic can be seen without every technical complication appearing at once.

## Relation to Hamiltonian constructions

The Euclidean measure is not the only way to approach $P(\phi)_2$. There is also a Hamiltonian viewpoint in which one constructs an interacting Hamiltonian on a Fock space by defining Wick-ordered spatially cutoff interactions, proving self-adjointness and lower bounds, and then removing cutoffs.

The Euclidean and Hamiltonian approaches are deeply connected. The Euclidean measure packages vacuum expectation values and reflection positivity. The Hamiltonian approach packages time evolution and spectral questions more directly. In successful constructions they describe the same underlying theory.

For learners, the Euclidean measure route is often clearer because it separates the construction into probabilistic steps:

$$
\text{Gaussian measure}
\longrightarrow
\text{Wick interaction}
\longrightarrow
\text{Schwinger functions}
\longrightarrow
\text{Hilbert space}.
$$

## Common pitfalls

**Do not confuse $P(\phi)_2$ with $\phi^2$.** The subscript is the spacetime dimension. The polynomial $P$ may contain $\phi^4$, $\phi^6$, or other powers.

**Do not skip Wick ordering.** The two-dimensional free field is not pointwise defined. Wick ordering is not optional decoration; it is part of the ultraviolet definition.

**Do not assume finite volume is the final theory.** A finite-volume interacting measure is only a regulated object. The infinite-volume limit carries phase information and is needed for a translation-invariant continuum QFT.

**Do not treat all theorem-level properties as equivalent.** Existence, OS positivity, clustering, mass gap, and particle structure are different claims. A page or paper should say which one it proves.

**Do not overgeneralize to four dimensions.** The success of $P(\phi)_2$ is historically and conceptually important, but it does not solve the four-dimensional constructive problem.

## Relations to other pages

[Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/) supplies the reference measure $\mu_C$ and the Wick polynomials used in this construction.

[Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/) explains the general measure-theoretic interpretation of Schwinger functions.

[OS Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) and [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explain how the Euclidean $P(\phi)_2$ Schwinger functions become Lorentzian Wightman fields.

Later model pages should specialize this discussion to $\phi^4_2$, $\phi^4_3$, sine-Gordon theory, cluster expansions, and the four-dimensional open problems.

## Research status

The $P(\phi)_2$ models are established constructive QFT successes. They provide rigorous interacting relativistic quantum field theories in two spacetime dimensions, with Euclidean measures, Schwinger functions, reconstruction, and, in important regimes, detailed spectral and particle information.

The subject is still valuable for research because it is a laboratory for questions that reappear in harder theories: phase transitions, symmetry breaking, mass gaps, scattering, correlation inequalities, cluster expansions, Borel summability, and scaling limits. Its lessons are foundational, but they do not remove the need for different methods in $\phi^4_3$, gauge theory, or four-dimensional Yang–Mills.

## Exercises

### Exercise 1

Let $X$ be a centered Gaussian random variable with variance $c_\epsilon$. Show that the Wick-ordered quartic interaction

$$
:\!X^4\!:
=
X^4-6c_\epsilon X^2+3c_\epsilon^2
$$

has zero expectation.

<details><summary><strong>Solution</strong></summary>

For a centered Gaussian variable,

$$
\mathbb E[X^2]=c_\epsilon,
\qquad
\mathbb E[X^4]=3c_\epsilon^2.
$$

Therefore

$$
\mathbb E[:\!X^4\!:]
=
3c_\epsilon^2
-6c_\epsilon^2
+3c_\epsilon^2
=0.
$$

The subtraction removes the Gaussian self-contractions of the local monomial.

</details>

### Exercise 2

Explain why the finite-cutoff measure

$$
d\mu_{\Lambda,\epsilon}
=
Z_{\Lambda,\epsilon}^{-1}e^{-V_{\Lambda,\epsilon}}d\mu_C
$$

is easier to define than the limiting measure $d\mu$ on all of $\mathbb R^2$.

<details><summary><strong>Solution</strong></summary>

For fixed $\epsilon>0$, the field $\phi_\epsilon(x)$ is smooth enough that $:\!P(\phi_\epsilon(x))\!:$ is an ordinary random function of $x$. For bounded $\Lambda$, the integral

$$
V_{\Lambda,\epsilon}
=
\int_\Lambda :\!P(\phi_\epsilon(x))\!:\,d^2x
$$

is a well-defined random variable under suitable stability assumptions on $P$. Thus the exponential weight can be normalized.

The limiting measure requires two harder steps. First, one must prove convergence as $\epsilon\downarrow0$ despite the singularity of the field. Second, one must control the limit as $\Lambda\uparrow\mathbb R^2$, where phase selection and clustering become infinite-volume questions.

</details>

### Exercise 3

For the $\lambda\phi^4_2$ interaction, identify which terms in

$$
\lambda:\!\phi_\epsilon^4\!:
=
\lambda\phi_\epsilon^4
-6\lambda c_\epsilon\phi_\epsilon^2
+3\lambda c_\epsilon^2
$$

look like mass and vacuum-energy counterterms.

<details><summary><strong>Solution</strong></summary>

The term

$$
-6\lambda c_\epsilon\phi_\epsilon^2
$$

has the same field dependence as a quadratic mass term, so it is the mass-counterterm pattern. The term

$$
3\lambda c_\epsilon^2
$$

is independent of the field. When integrated over volume, it shifts the normalization or vacuum energy. The leading term $\lambda\phi_\epsilon^4$ is the bare quartic interaction.

</details>

## References

### Standard first pass

- Barry Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Barry Simon and Raphael Høegh-Krohn, "Hypercontractive Semigroups and Two Dimensional Self-Coupled Bose Fields," *Journal of Functional Analysis* **9** (1972), 121–180. DOI: [10.1016/0022-1236(72)90008-0](https://doi.org/10.1016/0022-1236(72)90008-0).

### Constructive model papers

- Francesco Guerra, Lon Rosen, and Barry Simon, "The $P(\phi)_2$ Euclidean Quantum Field Theory as Classical Statistical Mechanics," *Annals of Mathematics* **101** (1975), 111–189 and 191–259. DOI: [10.2307/1970988](https://doi.org/10.2307/1970988) and [10.2307/1970989](https://doi.org/10.2307/1970989).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "The Wightman Axioms and Particle Structure in the $P(\phi)_2$ Quantum Field Model," *Annals of Mathematics* **100** (1974), 585–632. DOI: [10.2307/1970959](https://doi.org/10.2307/1970959).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "Phase Transitions for $\phi^4_2$ Quantum Fields," *Communications in Mathematical Physics* **45** (1975), 203–216.

### Background and reconstruction

- Edward Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- G. Velo and A. S. Wightman, eds., *Constructive Quantum Field Theory: The 1973 “Ettore Majorana” International School of Mathematical Physics*, Lecture Notes in Physics 25, Springer, 1973. DOI: [10.1007/BFb0113079](https://doi.org/10.1007/BFb0113079).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- Konrad Osterwalder and Robert Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).

## Version history

- **2026-06-29:** Initial page created.
