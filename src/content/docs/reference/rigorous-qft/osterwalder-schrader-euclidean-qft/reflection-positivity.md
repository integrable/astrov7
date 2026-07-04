---
title: "Reflection Positivity"
description: "Explains reflection positivity as the Euclidean replacement for Hilbert-space positivity, proves it for the free scalar covariance, and warns how regulators and gauge fixing can violate it."
sidebar:
  label: "Reflection Positivity"
  order: 4
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader; Nelson; Glimm–Jaffe; Fröhlich–Israel–Lieb–Simon."
topics:
  - reflection positivity
  - Osterwalder–Schrader positivity
  - Euclidean QFT
  - Hilbert-space reconstruction
  - free scalar field
canonicalTopics:
  - reflection-positivity
  - osterwalder-schrader-axioms
  - euclidean-quantum-field-theory
researchStatus:
  established:
    - "Reflection positivity is the precise Euclidean positivity condition that reconstructs a positive Hilbert space and positive Hamiltonian in the Osterwalder–Schrader framework."
  active:
    - "For gauge-fixed, fermionic, complex, and regulated theories, the physically correct form of reflection positivity can be subtle and formulation-dependent."
---

## Summary

Reflection positivity is the Euclidean condition that becomes Hilbert-space positivity after reconstruction. Choose Euclidean time $\tau$ and reflect it by

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x).
$$

For a scalar Schwinger family, the condition says that every positive-time observable $F$ has nonnegative reflected expectation:

$$
\langle F,F\rangle_{\mathrm{OS}}
=
\langle \Theta F\,F\rangle_E
\ge0.
$$

In two-point form, with $f$ supported in $\tau>0$, this becomes

$$
\int_{\tau,\sigma>0}
\overline{f(\tau,\mathbf x)}
C_E(-\tau-\sigma,\mathbf x-\mathbf y)
 f(\sigma,\mathbf y)
\,d\tau\,d\sigma\,d^{d-1}\mathbf x\,d^{d-1}\mathbf y
\ge0.
$$

This is not the same as pointwise positivity of $C_E(x)$, nor even ordinary positive definiteness on all Euclidean test functions. It is positivity after reflecting the bra across the Euclidean time-zero plane.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Positive-time functions and their reflected partners in reflection positivity](/figures/rigorous-qft/reflection-positivity-half-space.svg)

<figcaption>

Reflection positivity pairs a positive-time test object $F$ with its reflected conjugate $\Theta F$. The time-zero plane is the cut from which the Hilbert space is reconstructed; positive Euclidean time becomes ket data, and reflected negative Euclidean time becomes bra data.

</figcaption>
</figure>

## Prerequisites

Read [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/) first. You should also know the Euclidean two-point function from [Euclidean Correlation Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/euclidean-correlation-functions/) and the distributional language from [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

Only scalar bosonic fields are treated in detail here. Fermions require graded signs and a compatible antilinear reflection; gauge theories are usually formulated in terms of gauge-invariant observables or lattice measures before positivity is visible.

## Logical status

| Item | Status |
|---|---|
| Page type | Concept, calculation, and diagnostic page. |
| Main object | The OS inner product $\langle F,F\rangle_{\mathrm{OS}}$. |
| Main example | The massive free scalar Euclidean covariance. |
| Main theorem-level role | Produces a positive Hilbert space and positive Hamiltonian after reconstruction. |
| Main warning | Reflection positivity is easily destroyed by wrong signs, higher-derivative regulators, or gauge fixing. |

## Core idea

In ordinary quantum mechanics, a Euclidean correlator of two operators has the form

$$
\langle\Omega|A^\dagger e^{-\tau H}A|\Omega\rangle,
\qquad
\tau>0.
$$

If $H\ge0$, then $e^{-\tau H}$ is a positive contraction semigroup, and the expression is nonnegative when it is interpreted as a norm square in the enlarged Hilbert-space construction.

Reflection positivity abstracts this fact without assuming the Hilbert space at the start. Euclidean time is cut at $\tau=0$. A functional $F$ made from fields at positive Euclidean times is treated as a candidate ket. Its reflected conjugate $\Theta F$ lives at negative Euclidean times and is treated as the corresponding bra. The Euclidean expectation of their product is declared to be the candidate inner product:

$$
\langle F,G\rangle_{\mathrm{OS}}
=
\langle \Theta F\,G\rangle_E.
$$

The axiom is simply that this candidate inner product is positive semidefinite. The reconstructed Hilbert space is then

$$
\mathcal H=
\overline{\mathcal A_+/\mathcal N},
\qquad
\mathcal N=\{F:\langle F,F\rangle_{\mathrm{OS}}=0\}.
$$

Thus reflection positivity is the Euclidean replacement for the statement that probabilities and norms are nonnegative.

## The two-point condition

Let $C_E(x-y)$ be a Euclidean two-point function for a translation-invariant scalar theory. For one-particle test functions $f$ supported in $\tau>0$, the two-point reflection-positivity condition is

$$
Q(f)
=
\int
\overline{f(x)}C_E(\theta x-y)f(y)
\,d^dx\,d^dy
\ge0,
\qquad
\operatorname{supp}f\subset\mathbb R^d_+.
$$

In coordinates this is

$$
Q(f)
=
\int_{\tau,\sigma>0}
\overline{f(\tau,\mathbf x)}
C_E(-\tau-\sigma,\mathbf x-\mathbf y)
 f(\sigma,\mathbf y)
\,d\tau\,d\sigma\,d^{d-1}\mathbf x\,d^{d-1}\mathbf y.
$$

The appearance of $-\tau-\sigma$ is the whole point. The reflected point $\theta x$ lies at negative Euclidean time, while $y$ lies at positive Euclidean time. The kernel sees the separation from a bra insertion to a ket insertion.

For full interacting Schwinger functions, the same idea is applied to finite sums of monomials in fields. If

$$
F=
\sum_n \phi(f_n)
$$

is shorthand for a finite positive-time polynomial of smeared fields, then reflection positivity says

$$
\langle \Theta F\,F\rangle_E\ge0.
$$

The two-point condition is necessary but not sufficient for a non-Gaussian theory. In a Gaussian theory it is enough, because all higher Schwinger functions are built from the covariance by Wick's rule.

## Free scalar calculation

For the massive free scalar field, the Euclidean covariance is

$$
C_E(\tau,\mathbf x)
=
\int\frac{dp_0\,d^{d-1}\mathbf p}{(2\pi)^d}
\frac{e^{ip_0\tau+i\mathbf p\cdot\mathbf x}}
{p_0^2+\omega_{\mathbf p}^2},
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Integrating over $p_0$ gives

$$
C_E(\tau,\mathbf x)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{-\omega_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x}}
{2\omega_{\mathbf p}}.
$$

Now take $f$ supported in $\tau>0$. Since $\tau,\sigma>0$,

$$
C_E(-\tau-\sigma,\mathbf x-\mathbf y)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{e^{-\omega_{\mathbf p}(\tau+\sigma)}
 e^{i\mathbf p\cdot(\mathbf x-\mathbf y)}}
{2\omega_{\mathbf p}}.
$$

Substituting into $Q(f)$ gives

$$
Q(f)
=
\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}
\frac{1}{2\omega_{\mathbf p}}
\left|
\int_0^\infty d\tau\int d^{d-1}\mathbf x\,
 e^{-\omega_{\mathbf p}\tau-i\mathbf p\cdot\mathbf x}
 f(\tau,\mathbf x)
\right|^2.
$$

This is manifestly nonnegative. Therefore the free massive scalar covariance is reflection positive.

The calculation also explains why the Euclidean propagator knows about positive energy. The exponential $e^{-\omega_{\mathbf p}\tau}$ is the Euclidean time-evolution factor associated with a state of energy $\omega_{\mathbf p}>0$.

## Spectral representation test

The free scalar calculation generalizes. A translation-invariant scalar two-point function with Källén–Lehmann type representation

$$
\widetilde C_E(p_0,\mathbf p)
=
\int_0^\infty
\frac{d\rho(\mu^2)}
{p_0^2+\mathbf p^2+\mu^2},
\qquad
 d\rho(\mu^2)\ge0,
$$

is reflection positive. Each mass $\mu$ contributes a nonnegative free-scalar term, and a positive measure preserves positivity.

This gives a practical diagnostic:

$$
\text{positive spectral measure}
\quad\Longrightarrow\quad
\text{two-point reflection positivity}.
$$

It also gives a way to spot failures. A propagator with negative spectral weight is not the covariance of a positive-norm scalar particle. For example, the Pauli–Villars-type difference

$$
\frac{1}{p^2+m^2}-\frac{1}{p^2+M^2}
$$

has a negative spectral contribution. It can be useful as a regulator, but it is not itself the propagator of a positive Hilbert-space scalar theory.

Similarly, higher-derivative propagators such as

$$
\frac{1}{(p^2+m^2)(p^2+M^2)}
=
\frac{1}{M^2-m^2}
\left(
\frac{1}{p^2+m^2}
-
\frac{1}{p^2+M^2}
\right)
$$

contain a negative spectral component when decomposed into simple poles. This is the Euclidean shadow of ghost degrees of freedom.

## From positivity to the Hamiltonian

Reflection positivity does more than define a norm. It also makes Euclidean time translations into contractions.

Let $T_a$ translate a positive-time functional forward by $a>0$:

$$
(T_aF)(\tau,\mathbf x)=F(\tau-a,\mathbf x)
$$

where the support remains in positive time. On the reconstructed Hilbert space, these maps form a semigroup:

$$
T_{a+b}=T_aT_b,
\qquad
\|T_a\|\le1.
$$

Under the standard continuity assumptions, the semigroup has a self-adjoint nonnegative generator $H$:

$$
T_a=e^{-aH},
\qquad
H\ge0.
$$

This is the Euclidean origin of the spectral condition. After analytic continuation, $e^{-aH}$ becomes Lorentzian time evolution $e^{-itH}$.

The same logic applies to spatial translations and rotations, producing momentum and angular momentum operators. The full Poincaré representation emerges only after the OS reconstruction theorem, but the seed of positive energy is already visible in reflection positivity.

## Probability positivity versus reflection positivity

A Euclidean functional integral with a positive measure satisfies ordinary probability positivity:

$$
\int |F(\phi)|^2\,d\mu(\phi)\ge0.
$$

Reflection positivity is different:

$$
\int \overline{\Theta F(\phi)}F(\phi)\,d\mu(\phi)\ge0
\qquad
\text{for }F\text{ supported at }\tau>0.
$$

The second condition is stronger and more structured. It uses a reflection of spacetime, not just complex conjugation of a random variable. A positive Euclidean probability measure need not be reflection positive with respect to a given time reflection.

This distinction matters in lattice field theory. A lattice action may define a perfectly good positive statistical-mechanical measure but fail to produce a positive transfer matrix. Reflection positivity is the condition that allows the Euclidean lattice model to be interpreted as a unitary quantum theory after choosing a time direction.

## Gauge fields and fermions

Reflection positivity is cleanest for scalar fields. Gauge and fermion systems require care.

For fermions, reflection includes an antilinear operation on Grassmann variables and spinor indices. The positivity statement is not ordinary positivity of a Grassmann measure. It is a statement about the induced bosonic sesquilinear form on the physical state space.

For gauge theory, positivity is usually most transparent for gauge-invariant observables or in a lattice formulation with a reflection-positive action. Gauge fixing can obscure or violate positivity at the level of gauge-dependent correlators. This does not automatically mean the physical gauge theory is nonunitary. It may mean that unphysical fields, ghosts, or gauge choices have entered the description.

The safe rule is:

$$
\text{positivity of physical Hilbert space}
\neq
\text{positivity of every gauge-fixed Euclidean correlator}.
$$

This is why rigorous treatments of gauge theories often keep careful track of observables, constraints, BRST cohomology, or lattice transfer matrices.

## Common pitfalls

**Mistaking reflection positivity for positivity of the Euclidean action.** A real bounded-below action may define a positive measure, but reflection positivity is an additional structural condition.

**Checking only the two-point function in an interacting theory.** The two-point condition is not enough unless the theory is Gaussian.

**Forgetting the time-zero cut.** The reconstructed Hilbert space depends on a choice of reflection plane. Euclidean invariance then shows that equivalent choices are related.

**Treating regulators as physical theories.** Pauli–Villars and higher-derivative regulators often introduce negative spectral weights. They may be useful calculations, not reflection-positive continuum theories.

**Demanding positivity of gauge-dependent fields.** Physical unitarity is a statement about the physical state space, not necessarily about every auxiliary field in a gauge-fixed formulation.

## Relations to other pages

This page expands the key axiom in [Osterwalder–Schrader Axioms](/rigorous-qft/osterwalder-schrader-euclidean-qft/os-axioms/). It prepares for the OS reconstruction theorem, where the quotient by null vectors and the positive Hamiltonian are constructed systematically.

For the Lorentzian counterpart, see [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/) and [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/). For distributional control of the kernels used here, a later page in the Operator-Valued Distributions chapter will treat two-point functions as distributions.

## Research status

Reflection positivity is a settled theorem-level concept in Euclidean constructive and axiomatic QFT. It is also a powerful tool in statistical mechanics, especially for lattice systems and phase transitions.

The active difficulty is formulation. In gauge theories, fermionic theories, nonlocal effective actions, complex actions, real-time nonequilibrium systems, and sign-problem settings, the correct positivity statement may not look like the scalar formula above. A major diagnostic question for any Euclidean construction is therefore: does it preserve the positivity needed for a physical Hilbert space?

## Exercises

### Exercise 1

Show that the one-dimensional kernel

$$
K(\tau,\sigma)=e^{-m(\tau+\sigma)},
\qquad
\tau,\sigma>0,
\qquad
m>0,
$$

is positive semidefinite.

<details><summary><strong>Solution</strong></summary>

For any test function $f$ on $(0,\infty)$,

$$
\int_0^\infty d\tau\int_0^\infty d\sigma\,
\overline{f(\tau)}e^{-m(\tau+\sigma)}f(\sigma)
=
\left|\int_0^\infty e^{-m\tau}f(\tau)\,d\tau\right|^2.
$$

This is nonnegative. The free scalar calculation is the momentum-space version of this elementary identity.

</details>

### Exercise 2

Use partial fractions to explain why

$$
\frac{1}{(p^2+m^2)(p^2+M^2)}
$$

with $M>m>0$ is not a positive-spectral-measure scalar propagator.

<details><summary><strong>Solution</strong></summary>

Partial fractions give

$$
\frac{1}{(p^2+m^2)(p^2+M^2)}
=
\frac{1}{M^2-m^2}
\left(
\frac{1}{p^2+m^2}
-
\frac{1}{p^2+M^2}
\right).
$$

The second pole has negative coefficient. A positive Källén–Lehmann representation requires nonnegative spectral weights, so this propagator is not the two-point function of a positive-norm scalar field by itself.

</details>

### Exercise 3

Why does reflection positivity imply a quotient construction rather than an immediate Hilbert space?

<details><summary><strong>Solution</strong></summary>

Reflection positivity gives a positive semidefinite sesquilinear form. It may have null vectors: nonzero test-function combinations $F$ for which

$$
\langle F,F\rangle_{\mathrm{OS}}=0.
$$

A Hilbert-space inner product must be positive definite, so one first quotients by the null space $\mathcal N$ and then completes. This is the same logic as in the GNS construction of a Hilbert space from a positive state.

</details>

## References

- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions," *Communications in Mathematical Physics* **31** (1973), 83–112. DOI: [10.1007/BF01645738](https://doi.org/10.1007/BF01645738).
- K. Osterwalder and R. Schrader, "Axioms for Euclidean Green's Functions II," *Communications in Mathematical Physics* **42** (1975), 281–305. DOI: [10.1007/BF01608978](https://doi.org/10.1007/BF01608978).
- E. Nelson, "Construction of Quantum Fields from Markoff Fields," *Journal of Functional Analysis* **12** (1973), 97–112. DOI: [10.1016/0022-1236(73)90091-8](https://doi.org/10.1016/0022-1236(73)90091-8).
- J. Fröhlich, R. Israel, E. H. Lieb, and B. Simon, "Phase Transitions and Reflection Positivity. I. General Theory and Long Range Lattice Models," *Communications in Mathematical Physics* **62** (1978), 1–34. DOI: [10.1007/BF01940327](https://doi.org/10.1007/BF01940327).
- K. Osterwalder and E. Seiler, "Gauge Field Theories on a Lattice," *Annals of Physics* **110** (1978), 440–471. DOI: [10.1016/0003-4916(78)90039-8](https://doi.org/10.1016/0003-4916(78)90039-8).
- A. Jaffe, C. D. Jäkel, and R. E. Martinez II, "Complex Classical Fields: A Framework for Reflection Positivity," *Communications in Mathematical Physics* **329** (2014), 1–28. arXiv: [1201.6003](https://arxiv.org/abs/1201.6003), DOI: [10.1007/s00220-014-2040-y](https://doi.org/10.1007/s00220-014-2040-y).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).

## Version history

- **2026-06-28:** Initial polished draft.
