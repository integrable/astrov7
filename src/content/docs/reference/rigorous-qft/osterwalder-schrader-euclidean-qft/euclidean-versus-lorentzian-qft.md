---
title: "Euclidean versus Lorentzian QFT"
description: "Compares Euclidean and Lorentzian formulations of QFT and explains exactly what Osterwalder–Schrader reconstruction does and does not identify."
sidebar:
  label: "Euclidean vs. Lorentzian"
  order: 9
level: Advanced
status: "Polished draft"
source: "Schwinger; Osterwalder–Schrader; Wightman; Nelson; Glimm–Jaffe; Simon."
topics:
  - Euclidean QFT
  - Lorentzian QFT
  - Wick rotation
  - reflection positivity
  - analytic continuation
canonicalTopics:
  - euclidean-quantum-field-theory
  - lorentzian-quantum-field-theory
  - osterwalder-schrader-qft
researchStatus:
  established:
    - "Under Osterwalder–Schrader hypotheses, Euclidean Schwinger functions reconstruct a Lorentzian Wightman theory with positive energy."
  active:
    - "Extracting Lorentzian real-time observables from approximate Euclidean data is generally ill-conditioned, and gauge-theoretic settings require additional care."
---

## Summary

Euclidean and Lorentzian QFT are not merely the same formulas written with different signs. They are two different languages for encoding a quantum field theory. Lorentzian QFT makes time evolution, causality, commutators, scattering, and unitary representations visible. Euclidean QFT makes decay, probability measures, statistical mechanics, constructive methods, and lattice regularization visible.

The rigorous bridge is the Osterwalder–Schrader theorem. A family of Euclidean Schwinger functions satisfying suitable regularity, covariance, symmetry, reflection positivity, and clustering hypotheses reconstructs a Lorentzian Wightman QFT. Conversely, a Wightman theory with the usual analyticity properties gives Euclidean Schwinger functions by analytic continuation to imaginary time.

The core equivalence is therefore conditional:

$$
\text{Euclidean QFT}
\simeq
\text{Lorentzian QFT}
\qquad
\text{only after positivity and analyticity are imposed.}
$$

Without reflection positivity, Euclidean correlation functions may have no positive-norm Hilbert space behind them. Without spectral support and analyticity, the symbol $t=-i\tau$ is not a theorem. This page is a comparison map: it explains which structures match, which structures do not, and why the Euclidean formalism is powerful precisely because it is not just Lorentzian QFT with $i$ removed.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Comparison between Euclidean and Lorentzian QFT data](/figures/rigorous-qft/euclidean-lorentzian-dictionary.svg)

<figcaption>

Euclidean and Lorentzian data emphasize different structures. Osterwalder–Schrader reconstruction is a theorem-level bridge, not a formal instruction to substitute $t=-i\tau$ in every expression.

</figcaption>
</figure>

## Prerequisites

Read [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/), [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/), [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/), and [Wick Rotation: Rigorous View](/rigorous-qft/osterwalder-schrader-euclidean-qft/wick-rotation-rigorous-view/). For the Lorentzian side, use [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) and [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/).

The free scalar field is the best running example. The page [Gaussian Free Field](/rigorous-qft/osterwalder-schrader-euclidean-qft/gaussian-free-field/) gives the Euclidean version, and the Wightman chapter gives the Lorentzian axiomatic language.

## Core idea

A Lorentzian theory is adapted to real time. It has a Hilbert space $\mathcal H$, a vacuum vector $\Omega$, a unitary representation of spacetime translations, and operator-valued distributions $\phi(f)$. Its time evolution is

$$
U(t)=e^{-itH}.
$$

A Euclidean theory is adapted to imaginary time. Its correlation functions are distributions $S_n$ on $\mathbb R^d$, often obtained as moments of a probability measure on generalized fields. Positive Euclidean time translations become

$$
T(\tau)=e^{-\tau H},
\qquad \tau\ge 0,
$$

a contraction semigroup after reconstruction.

The difference between $e^{-itH}$ and $e^{-\tau H}$ is not cosmetic. The first is oscillatory and unitary. The second is decaying and positivity-preserving in many examples. The Euclidean side is therefore closer to probability and statistical mechanics, while the Lorentzian side is closer to quantum dynamics and causal propagation.

The slogan is

$$
\begin{array}{c}
\text{Lorentzian QFT records time evolution directly,}\\
\text{Euclidean QFT records its imaginary-time shadow.}
\end{array}
$$

A shadow can contain all information if the projection is controlled. That control is exactly the role of analyticity and reflection positivity.

## Setup and conventions

We use $d$ for the total number of spacetime dimensions. Lorentzian spacetime is $\mathbb R^{1,d-1}$ with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,\ldots,-1),
$$

while Euclidean space is $\mathbb R^d$ with positive metric

$$
\delta_{\mu\nu}=\operatorname{diag}(1,1,\ldots,1).
$$

Lorentzian coordinates are

$$
x=(t,\mathbf x),
\qquad
p\cdot x=p^0t-\mathbf p\cdot\mathbf x.
$$

Euclidean coordinates are

$$
x_E=(\tau,\mathbf x),
\qquad
p_E\cdot x_E=p_0\tau+\mathbf p\cdot\mathbf x.
$$

The informal substitution is

$$
t=-i\tau,
\qquad
p^0=i p_0,
$$

but the rigorous meaning is analytic continuation of correlation distributions. The Euclidean norm is

$$
p_E^2=p_0^2+\mathbf p^2,
$$

whereas the Lorentzian norm is

$$
p^2=(p^0)^2-\mathbf p^2.
$$

For a free massive scalar, the Euclidean covariance and Lorentzian Feynman propagator are related by analytic continuation of boundary values:

$$
C_m(p_E)=\frac{1}{p_E^2+m^2},
\qquad
D_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The $i\epsilon$ is part of the Lorentzian distribution. It cannot be recovered from the Euclidean denominator by ordinary algebra alone; it records which boundary value of an analytic function is being used.

## The comparison table

| Structure | Euclidean formulation | Lorentzian formulation |
|---|---|---|
| Geometry | Riemannian space $\mathbb R^d$. | Minkowski spacetime $\mathbb R^{1,d-1}$. |
| Symmetry | Euclidean group $E(d)=\mathbb R^d\rtimes O(d)$. | Poincaré group $\mathbb R^d\rtimes O(1,d-1)$. |
| Basic correlators | Symmetric Schwinger distributions $S_n(x_1,\ldots,x_n)$. | Ordered Wightman distributions $W_n(x_1,\ldots,x_n)$. |
| Positivity | Reflection positivity. | Hilbert-space positivity. |
| Time evolution | Semigroup $e^{-\tau H}$ for $\tau\ge0$. | Unitary group $e^{-itH}$ for $t\in\mathbb R$. |
| Energy condition | Reconstructed $H\ge0$. | Spectral condition $\operatorname{spec}P\subset\overline V_+$. |
| Locality | Encoded indirectly by Euclidean symmetry plus OS reconstruction. | Microcausality: fields commute or anticommute at spacelike separation. |
| Natural constructions | Measures, Gaussian fields, Gibbs weights, lattice limits. | Hilbert spaces, operator algebras, scattering, causal propagation. |
| Main danger | A Euclidean measure may fail reflection positivity. | Operator products and real-time path integrals are singular. |

The table should not be read as a declaration that one side is more fundamental. In constructive work, the Euclidean side is often the one that can be built. In scattering theory, locality, or real-time response, the Lorentzian side is often the one that states the desired physics.

## What OS reconstruction identifies

Suppose one has a family of Euclidean distributions

$$
S_n(x_1,\ldots,x_n),
\qquad x_i\in\mathbb R^d,
$$

satisfying the OS hypotheses. Then reconstruction builds:

1. a Hilbert space $\mathcal H$;
2. a vacuum vector $\Omega$;
3. a positive Hamiltonian $H$ and a unitary representation of the Poincaré group;
4. Lorentzian Wightman distributions $W_n$;
5. operator-valued distributions whose vacuum expectation values are the $W_n$.

The reconstructed Hilbert space is not the vector space of all Euclidean random-field functionals. It is a quotient-completion of positive-time functionals under the OS inner product

$$
\langle F,G\rangle_{\mathrm{OS}}
=
\mathbb E_E[(\Theta F)G],
$$

where $\Theta$ reflects Euclidean time. Null vectors are divided out. This quotient is why reflection positivity is exactly the right positivity condition.

The theorem also tells us what the reconstructed Lorentzian theory is allowed to forget. Different Euclidean descriptions can produce equivalent Lorentzian theories after null spaces and completions are taken. Conversely, some Euclidean objects that look natural as probability measures do not survive as positive-norm quantum states.

## What OS reconstruction does not identify

OS reconstruction does not say that every Euclidean action defines a QFT. The notation

$$
d\mu(\phi)\stackrel{?}{=}\frac{1}{Z}e^{-S_E[\phi]}D\phi
$$

is only a mnemonic until one specifies a measure or a limiting procedure and proves the OS properties.

It also does not say that every Lorentzian observable is easy to compute from Euclidean data. Analytic continuation from imaginary time to real time can be severely ill-conditioned. If a Euclidean two-point function has a spectral representation

$$
G_E(\tau)=\int_0^\infty e^{-\omega\tau}\,d\rho(\omega),
\qquad \tau>0,
$$

then the corresponding real-time Wightman function is formally

$$
G^+(t)=\int_0^\infty e^{-i\omega t}\,d\rho(\omega).
$$

The same spectral measure $\rho$ controls both. But recovering $\rho$ from approximate values of $G_E(\tau)$ is an inverse Laplace-transform problem, and small Euclidean errors can become large real-time errors.

Finally, OS reconstruction does not automatically solve gauge theory. Gauge fixing, ghosts, indefinite metric spaces, BRST cohomology, and gauge-invariant observables all change the positivity story. Lattice gauge actions can satisfy reflection positivity before gauge fixing, but gauge-dependent continuum correlators require more delicate interpretation.

## Free scalar dictionary

For the free massive scalar field, the dictionary is completely explicit. The Lorentzian positive-frequency two-point function is

$$
W_2(t,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{-i\omega_{\mathbf p}t+i\mathbf p\cdot\mathbf x}}
{2\omega_{\mathbf p}},
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

The Euclidean covariance is

$$
C_m(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}|\tau|}}
{2\omega_{\mathbf p}}.
$$

For $\tau>0$, one has the analytic-continuation relation

$$
C_m(\tau,\mathbf x)=W_2(-i\tau,\mathbf x).
$$

For multiple insertions, Euclidean ordering in $\tau$ selects the Lorentzian Wightman ordering. If

$$
\tau_1>\tau_2>\cdots>\tau_n,
$$

then the Schwinger function is obtained by evaluating the analytic continuation of

$$
\langle\Omega,
\phi(t_1,\mathbf x_1)\cdots\phi(t_n,\mathbf x_n)
\Omega\rangle
$$

at $t_j=-i\tau_j$, with the appropriate ordering domain. The full symmetric Euclidean distribution is assembled from these ordered pieces.

The Feynman propagator is a different but related Lorentzian object. It is time ordered:

$$
D_F(x-y)=
\langle\Omega,
T\{\phi(x)\phi(y)\}\Omega\rangle.
$$

The Euclidean covariance corresponds to the imaginary-time-ordered version. This is why path-integral calculations so naturally produce Feynman propagators after analytic continuation.

## Causality versus reflection positivity

Lorentzian locality is causal. For bosonic scalar fields, microcausality says

$$
[\phi(x),\phi(y)]=0
\qquad
\text{if }(x-y)^2<0.
$$

This statement uses the light cone and has no direct Euclidean analogue because Euclidean space has no causal order. In Euclidean signature every nonzero direction has positive length, so there are no timelike, spacelike, or lightlike separations.

Instead, the Euclidean framework encodes the possibility of returning to a causal theory through reflection positivity and analytic continuation. Roughly:

$$
\begin{array}{c}
\text{Euclidean symmetry + reflection positivity + regularity}\\
\Longrightarrow\\
\text{Lorentzian spectral condition and locality after reconstruction.}
\end{array}
$$

This is one reason reflection positivity is not an optional technical condition. It is the Euclidean remnant of Hilbert-space positivity, positive energy, and causal Lorentzian structure.

## Thermal and statistical interpretations

Euclidean time also appears in ordinary quantum statistical mechanics. For a Hamiltonian $H$, the thermal partition function is

$$
Z(\beta)=\operatorname{Tr}e^{-\beta H}.
$$

This makes Euclidean time periodic with period $\beta$ for bosonic observables. In finite-temperature QFT, Euclidean correlation functions live on

$$
S^1_\beta\times\mathbb R^{d-1},
$$

with periodic or antiperiodic boundary conditions depending on statistics.

The OS framework in this chapter is primarily the zero-temperature flat-space reconstruction story. Finite-temperature Euclidean QFT has its own reconstruction and KMS condition. The basic moral remains the same: Euclidean time is powerful because it turns unitary time evolution into decaying or trace-class objects, but the price is that real-time information becomes indirect.

## Gauge-theory caveats

Gauge theories are a major source of confusion in this comparison. A gauge-invariant Euclidean lattice theory can be reflection positive, and Wilson-loop expectations may have good Euclidean meaning. But common continuum gauge-fixed propagators often live in an indefinite or BRST-graded setting before one passes to physical observables.

Thus one should distinguish:

| Object | Positivity status |
|---|---|
| Gauge-invariant Euclidean observables, before gauge fixing | Can satisfy reflection positivity in suitable regularizations. |
| Gauge-fixed elementary fields | May violate positivity or live in an indefinite auxiliary space. |
| Physical Hilbert space | Expected to be recovered by constraints, quotient, or BRST cohomology. |
| Perturbative ghosts | Not physical positive-norm particles. |

This does not make Euclidean gauge theory invalid. It means that the OS positivity question should be asked for the physical observable algebra or for a formulation where the relevant positivity statement is actually true.

## How to use the dictionary in practice

When reading or writing a Euclidean QFT claim, ask five questions.

| Question | What it protects against |
|---|---|
| What are the Euclidean distributions or measure? | Confusing formal path integrals with constructed objects. |
| Is reflection positivity known? | Reconstructing a non-positive Hilbert space. |
| What is the analytic continuation domain? | Treating $t=-i\tau$ as algebra rather than analysis. |
| Which Lorentzian correlator is meant? | Confusing Wightman, time-ordered, retarded, and advanced functions. |
| Are the observables gauge invariant? | Applying positivity to auxiliary gauge-fixed fields. |

For perturbative scalar computations, these questions often have standard answers. For nonperturbative gauge theory, real-time response, finite density, or numerical analytic continuation, they become central.

## Common pitfalls

**Pitfall: “Euclidean QFT is just statistical mechanics.”** Euclidean scalar field theory often resembles statistical mechanics, but OS reflection positivity and analytic continuation are extra structures if one wants a Lorentzian quantum theory.

**Pitfall: “Every Euclidean action has a Lorentzian theory.”** A local-looking action does not automatically define a measure, a continuum limit, or reflection-positive Schwinger functions.

**Pitfall: “The Euclidean propagator determines real time by substituting $\tau=it$.”** Exact analytic functions may be continued, but numerical or approximate Euclidean data rarely determine real-time behavior stably.

**Pitfall: “Euclidean permutation symmetry contradicts Lorentzian noncommutativity.”** Euclidean Schwinger functions are symmetric distributions. Lorentzian Wightman functions are ordered boundary values. The difference is carried by analytic continuation and boundary prescriptions.

**Pitfall: “Gauge-fixed positivity violations prove the theory is unphysical.”** Gauge-fixed fields can live in auxiliary indefinite spaces. Physical positivity is a statement about gauge-invariant states or the physical quotient.

## Relations to other pages

This page closes the conceptual loop between the Wightman and Osterwalder–Schrader chapters. The page [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) introduces Lorentzian vacuum expectation distributions; [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/) introduces their Euclidean counterparts; [OS Reconstruction Theorem](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-reconstruction-theorem/) explains the theorem-level bridge.

The next page, [Markov Property Preview](/rigorous-qft/osterwalder-schrader-euclidean-qft/markov-property-preview/), explains a different Euclidean feature: local conditional independence and gluing. It is especially important for constructive QFT and probabilistic models.

Later chapters will revisit the same distinction in algebraic QFT, constructive QFT, path integrals as measures, lattice-continuum limits, perturbative algebraic QFT, and gauge theory.

## Research status

The equivalence between suitable Euclidean Schwinger functions and Lorentzian Wightman theories is a theorem of axiomatic QFT. It is one of the cleanest rigorous bridges between probability-like Euclidean methods and Hilbert-space relativistic QFT.

The hard part is construction. In low-dimensional scalar models, Euclidean constructive methods have produced nontrivial examples satisfying the needed properties. In four-dimensional non-Abelian gauge theory, the corresponding continuum construction with mass gap remains a major open problem.

A separate practical problem is analytic continuation from data. Even when a Euclidean theory is correct, reconstructing spectral densities or real-time correlators from approximate Euclidean data is usually ill-conditioned. This is a mathematical fact about inverse Laplace transforms, not merely a numerical inconvenience.

## Exercises

### Exercise 1: Euclidean decay from positive energy

Let $H\ge0$ be self-adjoint. Show that $e^{-\tau H}$ is a contraction for $\tau\ge0$.

<details><summary><strong>Solution</strong></summary>

By the spectral theorem,

$$
H=\int_0^\infty \lambda\,dE_\lambda.
$$

Thus

$$
e^{-\tau H}=\int_0^\infty e^{-\tau\lambda}\,dE_\lambda.
$$

For $\tau\ge0$, one has $0\le e^{-\tau\lambda}\le1$. Therefore

$$
\|e^{-\tau H}\|
=\sup_{\lambda\in\operatorname{spec}H}e^{-\tau\lambda}
\le1.
$$

This is the operator-theoretic origin of Euclidean decay.

</details>

### Exercise 2: The free two-point Wick rotation

Starting from

$$
W_2(t,\mathbf x)=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{-i\omega_{\mathbf p}t+i\mathbf p\cdot\mathbf x}}
{2\omega_{\mathbf p}},
$$

show that $W_2(-i\tau,\mathbf x)=C_m(\tau,\mathbf x)$ for $\tau>0$.

<details><summary><strong>Solution</strong></summary>

Substitute $t=-i\tau$:

$$
e^{-i\omega_{\mathbf p}t}
=e^{-i\omega_{\mathbf p}(-i\tau)}
=e^{-\omega_{\mathbf p}\tau}.
$$

Therefore

$$
W_2(-i\tau,\mathbf x)=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{i\mathbf p\cdot\mathbf x}e^{-\omega_{\mathbf p}\tau}}
{2\omega_{\mathbf p}}.
$$

For $\tau>0$, this is exactly the positive-time Euclidean covariance $C_m(\tau,\mathbf x)$.

</details>

### Exercise 3: Euclidean symmetry versus Lorentzian ordering

Explain why the symmetry

$$
S_2(x_1,x_2)=S_2(x_2,x_1)
$$

for the Euclidean free scalar does not imply

$$
W_2(x_1,x_2)=W_2(x_2,x_1)
$$

for Lorentzian points.

<details><summary><strong>Solution</strong></summary>

Euclidean Schwinger functions are symmetric because the corresponding generalized random variables commute in the Euclidean probability description. Lorentzian Wightman functions are ordered vacuum expectation values of noncommuting operator-valued distributions:

$$
W_2(x_1,x_2)=\langle\Omega,\phi(x_1)\phi(x_2)\Omega\rangle.
$$

The two orderings are different boundary values of analytic functions. They agree at spacelike separation for bosonic fields because of locality, but not generally at timelike separation.

</details>

### Exercise 4: Why reflection positivity is not ordinary positivity

Let $F$ be a polynomial functional of fields supported at positive Euclidean times. Why is the condition

$$
\mathbb E_E[(\Theta F)F]\ge0
$$

not the same as saying that $\mathbb E_E[F^2]\ge0$?

<details><summary><strong>Solution</strong></summary>

The expression $\mathbb E_E[F^2]\ge0$ is ordinary positivity of a classical probability measure when $F$ is real. Reflection positivity instead pairs $F$ with its reflected version $\Theta F$, where $\Theta$ sends positive Euclidean time to negative Euclidean time. This is the quadratic form that becomes the Lorentzian Hilbert-space inner product after quotienting by null vectors. It tests compatibility with quantum time evolution, not merely positivity of a Euclidean random variable.

</details>

## References

- J. Schwinger, "On the Euclidean Structure of Relativistic Field Theory," *Proceedings of the National Academy of Sciences* **44** (1958), 956–965. DOI: [10.1073/pnas.44.9.956](https://doi.org/10.1073/pnas.44.9.956).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press, 2000.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- B. Simon, *The $P(\phi)_2$ Euclidean (Quantum) Field Theory*, Princeton University Press, 1974.
- F. Strocchi, *An Introduction to Non-Perturbative Foundations of Quantum Field Theory*, Oxford University Press, 2013.

## Version history

- **2026-06-28:** Initial polished draft.
