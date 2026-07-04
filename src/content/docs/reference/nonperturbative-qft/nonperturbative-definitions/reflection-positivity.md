---
title: "Reflection Positivity"
description: "Defines reflection positivity and explains how Euclidean correlation functions reconstruct a positive-norm Hilbert space and a Hamiltonian bounded below."
sidebar:
  label: "Reflection Positivity"
  order: 5
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader; Glimm–Jaffe; Simon; Wilson–Kogut; Schwartz; Zinn-Justin."
topics:
  - reflection positivity
  - Osterwalder–Schrader reconstruction
  - Euclidean QFT
  - Hilbert space reconstruction
  - transfer matrix
  - unitarity
canonicalTopics:
  - nonperturbative-qft
  - euclidean-qft
  - reflection-positivity
  - hilbert-space-reconstruction
  - transfer-matrix
researchStatus:
  established:
    - "Reflection positivity is the Euclidean positivity condition that allows Schwinger functions to reconstruct a positive-norm Hilbert space with Hamiltonian bounded below."
  active:
    - "In gauge theories, chiral theories, real-time observables, finite density, and improved lattice actions, positivity may be subtle, hidden, or only recovered after restricting to physical observables or taking a continuum limit."
---

## Summary

Reflection positivity is the Euclidean condition that replaces Hilbert-space positivity before the Hilbert space has been constructed. Let Euclidean time reflection be

$$
\mathsf R(\tau,\mathbf x)=(-\tau,\mathbf x),
$$

and let $\Theta$ be the corresponding antilinear operation on operators. For every Euclidean observable $F$ built from fields supported at positive Euclidean times, reflection positivity requires

$$
\langle (\Theta F)F\rangle_E\geq0.
$$

More generally, for several positive-time observables $F_i$ and complex numbers $c_i$,

$$
\sum_{i,j}c_i^*c_j\langle(\Theta F_i)F_j\rangle_E\geq0.
$$

This inequality is the seed of the Lorentzian inner product. One defines

$$
(F,G)_{\rm OS}=\langle(\Theta F)G\rangle_E,
$$

then quotients by null vectors and completes. Under the remaining Osterwalder–Schrader conditions, Euclidean time translations become a contraction semigroup $e^{-\tau H}$ with $H\geq0$, and the Euclidean Schwinger functions reconstruct Lorentzian Wightman functions.

The punchline is simple but severe:

$$
\text{Euclidean invariance} + \text{reflection positivity} + \text{locality/regularity}
\quad\Longrightarrow\quad
\text{unitary Lorentzian QFT data}.
$$

Without reflection positivity, Euclidean correlation functions may still be interesting statistical-field-theory data, but they do not automatically define a standard quantum theory with positive probabilities.

## Prerequisites

You should have read [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) and [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/). The lattice version also uses the transfer-matrix intuition from [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/).

This page assumes only basic Euclidean correlators and Hilbert-space language. It does not require a prior course in constructive QFT, although the References section points to theorem-level treatments.

## Core idea

Ordinary Hilbert-space quantum mechanics has an obvious positivity condition:

$$
\langle\psi|\psi\rangle\geq0.
$$

A Euclidean path integral has no explicit $|\psi\rangle$. It gives correlation functions. Reflection positivity tells us how to recognize the hidden Hilbert-space norm inside those correlation functions.

The rule is: build a would-be state by inserting operators only in the positive-time half-space. Reflect the bra insertion into the negative-time half-space and complex conjugate coefficients. Then compute the Euclidean correlator across the reflection plane. The result must be nonnegative.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Reflection positivity pairs an observable in positive Euclidean time with its reflected conjugate across the plane tau equals zero.](/figures/nonperturbative-qft/reflection-positivity-slab.svg)

<figcaption>

Reflection positivity uses the plane $\tau=0$ as a Euclidean mirror. A positive-time insertion $F$ defines a would-be ket. The reflected conjugate $\Theta F$ defines the would-be bra. The Euclidean correlator $\langle(\Theta F)F\rangle_E$ is the proposed norm squared.

</figcaption>
</figure>

The condition is not the same as saying that the functional-integral weight is pointwise positive. A positive measure often makes reflection positivity easier to prove, but it is not enough by itself: the action must couple the two halves of Euclidean time in the right way. Conversely, gauge-fixed or complex-looking formulations may obscure positivity even when the physical theory is unitary.

A useful slogan is

$$
\text{reflection positivity is unitarity before Wick rotation back to real time.}
$$

## Setup and conventions

Work in Euclidean spacetime with coordinates

$$
x=(\tau,\mathbf x),
\qquad
\tau\in\mathbb R.
$$

The positive-time region is

$$
\mathbb R^d_+=\{(\tau,\mathbf x):\tau>0\},
$$

and the time reflection is

$$
\mathsf R x=(-\tau,\mathbf x).
$$

Let $\mathcal A_+$ be the algebra generated by Euclidean fields smeared with test functions supported in $\tau>0$. For a real scalar field, the reflection operation acts as

$$
\Theta\phi(\tau,\mathbf x)=\phi(-\tau,\mathbf x),
\qquad
\Theta(cF)=c^*\Theta F.
$$

The complex conjugation is essential. In Lorentzian signature, time reversal is antiunitary. Reflection positivity is its Euclidean shadow.

For fields with spin, vector indices, gauge indices, or fermion parity, $\Theta$ can include additional signs, matrices, reversals of operator order, or graded operations. This page states the scalar version first because it displays the structure with minimum baggage. The conceptual condition is the same: the reflected insertion must represent the adjoint bra of the positive-time ket.

## The reflection-positivity condition

For every $F\in\mathcal A_+$,

$$
\boxed{\langle(\Theta F)F\rangle_E\geq0.}
$$

The boxed formula is the whole page in one line. A more flexible equivalent statement is that the matrix

$$
M_{ij}=\langle(\Theta F_i)F_j\rangle_E
$$

must be positive semidefinite for every finite list $F_i\in\mathcal A_+$.

To see why this is a norm condition, define

$$
(F,G)_{\rm OS}=\langle(\Theta F)G\rangle_E.
$$

Reflection positivity says

$$
(F,F)_{\rm OS}\geq0.
$$

There may be nonzero $F$ with $(F,F)_{\rm OS}=0$. These are null vectors, just as gauge redundancies or equation-of-motion relations can create null states in intermediate descriptions. Define

$$
\mathcal N=\{F\in\mathcal A_+:(F,F)_{\rm OS}=0\}.
$$

The reconstructed Hilbert space is the completion of

$$
\mathcal H_{\rm OS}=\overline{\mathcal A_+/\mathcal N}
$$

with respect to the inner product $(\cdot,\cdot)_{\rm OS}$.

This is the conceptual heart of Euclidean QFT: a Hilbert space can be reconstructed from half-space correlation functions.

## Free scalar check

The free massive Euclidean scalar two-point function in $d=D+1$ dimensions is

$$
G_E(\tau,\mathbf x)
=\int\frac{d^D\mathbf p}{(2\pi)^D}\frac{1}{2\omega_{\mathbf p}}
 e^{-\omega_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x},
\qquad
\omega_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Take a linear positive-time observable

$$
F=\sum_j c_j\phi(\tau_j,\mathbf x_j),
\qquad
\tau_j>0.
$$

For a real scalar,

$$
\Theta F=\sum_i c_i^*\phi(-\tau_i,\mathbf x_i).
$$

Then

$$
\langle(\Theta F)F\rangle_E
=\sum_{i,j}c_i^*c_j
G_E(\tau_i+\tau_j,\mathbf x_i-\mathbf x_j).
$$

Using the spectral representation of $G_E$,

$$
\begin{aligned}
\langle(\Theta F)F\rangle_E
&=\int\frac{d^D\mathbf p}{(2\pi)^D}\frac{1}{2\omega_{\mathbf p}}
\sum_{i,j}c_i^*c_j
 e^{-\omega_{\mathbf p}(\tau_i+\tau_j)}
 e^{i\mathbf p\cdot(\mathbf x_i-\mathbf x_j)} \\
&=\int\frac{d^D\mathbf p}{(2\pi)^D}\frac{1}{2\omega_{\mathbf p}}
\left|\sum_j c_j e^{-\omega_{\mathbf p}\tau_j-i\mathbf p\cdot\mathbf x_j}\right|^2
\geq0.
\end{aligned}
$$

This calculation is worth remembering. Reflection positivity is not mysterious in the free theory: it is the positivity of the spectral density $1/(2\omega_{\mathbf p})$ and the damping factor $e^{-\omega\tau}$.

The same idea generalizes. The Euclidean two-point function of a unitary Lorentzian theory has a Källén–Lehmann-type representation with positive spectral density. Positive spectral weights are exactly what make the reflected norm nonnegative.

## Reconstruction in words

Reflection positivity is one of the Osterwalder–Schrader conditions. Together with Euclidean invariance, symmetry of Schwinger functions, regularity, and clustering assumptions, it allows one to reconstruct Lorentzian QFT data.

The reconstruction proceeds conceptually as follows.

| Step | Euclidean input | Reconstructed object |
|---:|---|---|
| 1 | Positive-time operator algebra $\mathcal A_+$ | Dense set of would-be states. |
| 2 | Inner product $\langle(\Theta F)G\rangle_E$ | Positive Hilbert space after quotienting null states. |
| 3 | Euclidean time translations by $t>0$ | Semigroup $e^{-tH}$. |
| 4 | Positivity and continuity of the semigroup | Self-adjoint Hamiltonian with $H\geq0$. |
| 5 | Euclidean spatial symmetries | Momentum and rotation generators. |
| 6 | Analytic continuation of Schwinger functions | Lorentzian Wightman functions. |

The phrase “semigroup” matters. Euclidean time translations in the positive direction act as damping operators:

$$
T(t)=e^{-tH},
\qquad t\geq0.
$$

One does not get a unitary group in Euclidean time. The Lorentzian unitary evolution appears after analytic continuation:

$$
e^{-tH}\quad\longrightarrow\quad e^{-i t H}.
$$

Reflection positivity is what makes the same $H$ positive and self-adjoint on a positive-norm Hilbert space.

## Transfer matrix version

On a Euclidean lattice, reflection positivity is closely related to the existence of a positive transfer matrix. Suppose Euclidean time is discretized with spacing $a_\tau$. A transfer matrix $T$ evolves fields by one time step:

$$
T\sim e^{-a_\tau H}.
$$

If $T$ is a positive self-adjoint operator on a Hilbert space, then $H$ can be defined by

$$
H=-\frac{1}{a_\tau}\log T,
$$

with spectrum bounded below after the usual normalization of the vacuum energy.

In the path-integral language, reflection positivity is the Euclidean correlation-function expression of this transfer-matrix positivity. It says that cutting the lattice along a time-reflection plane and gluing a configuration to its reflected conjugate produces a nonnegative norm.

For standard scalar lattice actions with nearest-neighbor positive kinetic couplings, reflection positivity is usually manifest. The Wilson plaquette action for lattice gauge theory also has a reflection-positive transfer-matrix formulation under standard assumptions. But not every lattice action preserves reflection positivity at finite cutoff. Some improved actions use extended time-like couplings that can violate positivity at distances of order the lattice spacing. Such violations may disappear in the continuum limit, but they are not invisible if one is extracting short-distance spectral data.

## Reflection positivity versus pointwise positivity

It is tempting to think that reflection positivity follows from

$$
e^{-S_E[\Phi]}\geq0.
$$

That is too quick. Pointwise positivity of the measure is helpful, but reflection positivity is a structural condition on how the action couples positive and negative Euclidean times.

A schematic sufficient pattern is an action decomposed as

$$
S_E=B+\Theta B-\sum_\alpha C_\alpha\Theta C_\alpha,
$$

with appropriate real coefficients and positive pairing across the reflection plane. Then the Boltzmann weight can often be expanded so that $\langle(\Theta F)F\rangle_E$ becomes a sum of absolute squares.

But positivity of the weight alone does not guarantee this factorization. Conversely, some formulations of perfectly unitary theories contain auxiliary fields, gauge-fixing ghosts, or complex phases that obscure positivity before one restricts to physical observables.

The right lesson is:

$$
\text{positive measure is not the definition of unitarity; reflection positivity is the Euclidean test for it.}
$$

## Spectral representation and positive residues

Reflection positivity is closely related to positive spectral density. For a scalar operator $\mathcal O$, a unitary Lorentzian theory gives a Euclidean two-point function of the form

$$
G_E(p_E^2)=\int_0^\infty d\mu^2\,\frac{\rho(\mu^2)}{p_E^2+\mu^2},
\qquad
\rho(\mu^2)\geq0.
$$

The positivity of $\rho$ is the statement that intermediate states have nonnegative norm:

$$
\rho(\mu^2)\sim \sum_n |\langle0|\mathcal O|n\rangle|^2\delta(\mu^2-m_n^2)
$$

in a schematic notation.

If a Euclidean two-point function has a pole with negative residue, it cannot be the two-point function of a positive-norm scalar operator in a unitary theory. This is one way ghosts show up. For example, a propagator that decomposes as

$$
\frac{1}{p_E^2+m_1^2}-\frac{1}{p_E^2+m_2^2}
$$

has a negative spectral contribution. Such a field may still appear as a gauge artifact or auxiliary variable, but it cannot represent an ordinary physical positive-norm particle.

This is why reflection positivity is often a sharper diagnostic than Euclidean convergence. A Euclidean integral can converge and still describe a nonunitary theory.

## Gauge theories and ghosts

Gauge theory requires care because the local gauge potential contains redundant variables. Reflection positivity is most naturally stated for gauge-invariant observables or for a formulation with a physical Hilbert space.

In a gauge-fixed continuum path integral, Faddeev–Popov ghosts are Grassmann scalar fields with the wrong spin-statistics relation. The gauge-fixed enlarged state space is not a positive physical Hilbert space. This does not mean Yang–Mills theory is nonunitary. It means positivity is recovered only after imposing the gauge constraints or BRST cohomology and restricting to physical observables.

Lattice gauge theory provides a cleaner nonperturbative route. Link variables are group-valued, gauge-invariant Wilson loops are direct observables, and standard reflection-positive gauge actions admit a transfer-matrix interpretation. Still, the global form of the gauge group, allowed line operators, boundary conditions, and topological sectors remain part of the definition.

The practical warning is simple: do not test reflection positivity on arbitrary gauge-dependent fields and conclude too much. Ask which Hilbert space and which observables are meant to be physical.

## Fermions

Fermions require a graded version of the construction. The reflection operation includes complex conjugation, reversal of order, and a spinor transformation chosen so that the reflected insertion represents the adjoint state. Schematically,

$$
\Theta\psi(\tau,\mathbf x)
\sim \bar\psi(-\tau,\mathbf x)\,R,
$$

where $R$ is a matrix depending on gamma-matrix conventions and the chosen reflection. The precise formula is convention-dependent.

The main point is not the particular matrix; it is the structure. Fermionic reflection positivity is a condition on the Grassmann integral or fermion determinant/Pfaffian ensuring that the reconstructed physical fermion states have positive norm and a Hamiltonian bounded below.

This is one reason lattice fermions are technically subtle. Doublers, Wilson terms, staggered fermions, domain-wall fermions, overlap fermions, and chiral gauge theories all interact with positivity, locality, chirality, and the transfer matrix in different ways.

## Complex actions and sign problems

A complex Euclidean weight makes positivity non-manifest. Important examples include theta terms, real-time contours, finite-density formulations, Chern–Simons terms in Euclidean signature, and systems with sign-changing fermion determinants.

A complex weight does not automatically prove that the target Lorentzian theory is nonunitary. Sometimes the complex phase is required by the physics, and a Hilbert-space definition exists by other means. But it does mean that the Euclidean path integral is no longer an ordinary probability measure, and reflection positivity cannot be assumed from measure positivity.

For Monte Carlo methods, this is disastrous because importance sampling wants a nonnegative weight. For foundations, the issue is slightly different: one must ask whether the Euclidean correlation functions satisfy the Osterwalder–Schrader positivity condition, perhaps after restricting to physical observables, pairing sectors properly, or using another definition.

A useful separation is:

| Issue | Meaning |
|---|---|
| Sign problem | The Euclidean weight is not usable as a positive probability measure for direct sampling. |
| Failure of reflection positivity | The Euclidean correlators do not reconstruct a positive-norm Hilbert space in the proposed variables. |
| Hidden positivity | The physical Hilbert space may still be positive after constraints, projection, or a different representation. |

These are related but not identical.

## What reflection positivity does not prove by itself

Reflection positivity is necessary for Euclidean reconstruction, but it is not the whole definition of QFT. One also needs other conditions, such as:

- Euclidean invariance or the appropriate lattice symmetries before the continuum limit;
- symmetry of Schwinger functions under permutations, with fermionic grading when relevant;
- locality or Euclidean locality properties;
- regularity or temperedness conditions so correlators are distributions of the right kind;
- clustering or uniqueness assumptions if one wants a unique vacuum;
- a controlled continuum and infinite-volume limit.

Reflection positivity is the positivity pillar. It does not replace locality, the spectrum condition, or the need to define the theory in the first place.

In particular, a finite lattice model may be perfectly reflection positive at nonzero lattice spacing but flow to a trivial continuum theory. Positivity tells you the Hilbert space is healthy; it does not guarantee interesting dynamics.

## Common pitfalls

**Confusing reflection positivity with Euclidean convergence.** A Gaussian integral can converge while its analytic continuation contains negative-norm states. Positive convergence is not the same as unitary quantum mechanics.

**Testing the wrong variables.** Gauge-fixed ghosts, auxiliary fields, and gauge-dependent fields need not be positive physical operators. Reflection positivity should be interpreted in the physical sector or in a formulation where the transfer matrix acts on the physical Hilbert space.

**Ignoring the anti-linearity of reflection.** The operation $\Theta$ complex conjugates coefficients. Without anti-linearity, the expression $\langle(\Theta F)F\rangle_E$ is not a norm candidate.

**Assuming every Euclidean statistical model is a Lorentzian QFT.** Many Euclidean models are excellent statistical systems but do not reconstruct a unitary relativistic quantum theory.

**Assuming improved lattice actions are automatically harmless.** Some improvements can violate reflection positivity at finite lattice spacing. This may be acceptable for long-distance continuum physics, but it matters when extracting spectral data near the cutoff.

**Thinking Wick rotation alone proves unitarity.** Analytic continuation relates Euclidean and Lorentzian correlators only after the Euclidean data satisfy the right positivity and regularity conditions.

## Relations to other pages

[Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) introduces Schwinger functions and explains why Euclidean time evolution is damping rather than oscillatory.

[Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains the box and transfer-matrix setting where reflection positivity is easiest to visualize.

[Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) explains how finite lattice actions can define transfer matrices and why lattice symmetries and positivity matter.

[Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/) explains why a positive regulated theory still needs a controlled $a\to0$ limit to define a continuum QFT.

Later pages on gauge theory, confinement, sign problems, constructive QFT, and algebraic QFT will reuse reflection positivity as the bridge between Euclidean calculations and Lorentzian unitarity.

## Research status

**Established.** Reflection positivity is a standard part of the Osterwalder–Schrader reconstruction framework. It is the Euclidean condition that makes the reconstructed inner product positive and the Hamiltonian bounded below.

**Established.** Standard free scalar theories, many ferromagnetic spin systems, nearest-neighbor scalar lattice theories, and Wilson-type lattice gauge actions satisfy reflection positivity under suitable assumptions.

**Subtle.** Gauge-fixed formulations, fermions, chiral gauge theories, topological terms, real-time contours, finite density, and improved lattice actions can hide or violate positivity in ways that require careful interpretation.

**Active.** In numerical and constructive work, positivity remains a practical diagnostic. It affects which lattice actions have clean spectral interpretations, which Euclidean data can be analytically continued, and how one separates physical nonunitarity from artifacts of variables or regulators.

## Exercises

### Exercise 1: Free scalar reflection positivity

Let

$$
F=\sum_j c_j\phi(\tau_j,\mathbf x_j),
\qquad \tau_j>0,
$$

for a free massive scalar. Use

$$
G_E(\tau,\mathbf x)
=\int\frac{d^D\mathbf p}{(2\pi)^D}\frac{1}{2\omega_{\mathbf p}}
 e^{-\omega_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x}
$$

to show $\langle(\Theta F)F\rangle_E\geq0$.

<details><summary><strong>Solution</strong></summary>

For a real scalar,

$$
\Theta F=\sum_i c_i^*\phi(-\tau_i,\mathbf x_i).
$$

Therefore

$$
\langle(\Theta F)F\rangle_E
=\sum_{i,j}c_i^*c_jG_E(\tau_i+\tau_j,\mathbf x_i-\mathbf x_j).
$$

Substitute the integral representation:

$$
\langle(\Theta F)F\rangle_E
=\int\frac{d^D\mathbf p}{(2\pi)^D}\frac{1}{2\omega_{\mathbf p}}
\sum_{i,j}c_i^*c_j
 e^{-\omega_{\mathbf p}(\tau_i+\tau_j)}
 e^{i\mathbf p\cdot(\mathbf x_i-\mathbf x_j)}.
$$

The sum is an absolute square:

$$
\sum_{i,j}c_i^*c_j
 e^{-\omega_{\mathbf p}(\tau_i+\tau_j)}
 e^{i\mathbf p\cdot(\mathbf x_i-\mathbf x_j)}
=
\left|\sum_j c_j e^{-\omega_{\mathbf p}\tau_j-i\mathbf p\cdot\mathbf x_j}\right|^2.
$$

Since $1/(2\omega_{\mathbf p})>0$, the integral is nonnegative.

</details>

### Exercise 2: Negative residue

Consider a Euclidean two-point function

$$
G_E(p)=\frac{1}{p^2+m_1^2}-\frac{1}{p^2+m_2^2},
\qquad m_2>m_1>0.
$$

Why is this incompatible with an ordinary positive-norm scalar operator?

<details><summary><strong>Solution</strong></summary>

A positive-norm scalar operator in a unitary theory has a Källén–Lehmann representation

$$
G_E(p)=\int_0^\infty d\mu^2\frac{\rho(\mu^2)}{p^2+\mu^2},
\qquad \rho(\mu^2)\geq0.
$$

The proposed correlator corresponds to spectral density

$$
\rho(\mu^2)=\delta(\mu^2-m_1^2)-\delta(\mu^2-m_2^2),
$$

which has a negative contribution. That negative residue would correspond to an intermediate state with negative norm, or to a nonphysical auxiliary/gauge artifact. It cannot be the two-point function of an ordinary physical scalar operator in a positive Hilbert space.

</details>

### Exercise 3: Constructing the OS inner product

Let $\mathcal A_+$ be the algebra of positive-time observables and define

$$
(F,G)_{\rm OS}=\langle(\Theta F)G\rangle_E.
$$

Why must one quotient by null vectors before calling this a Hilbert space?

<details><summary><strong>Solution</strong></summary>

Reflection positivity implies

$$
(F,F)_{\rm OS}\geq0,
$$

but it may allow nonzero $F$ with

$$
(F,F)_{\rm OS}=0.
$$

A Hilbert-space norm must satisfy $\|F\|=0$ only for the zero vector. Therefore all null vectors must be identified with zero. Define

$$
\mathcal N=\{F\in\mathcal A_+:(F,F)_{\rm OS}=0\}.
$$

The physical pre-Hilbert space is $\mathcal A_+/\mathcal N$. Completing it in the induced norm gives the reconstructed Hilbert space.

</details>

### Exercise 4: Why anti-linearity matters

Suppose $\Theta$ did not complex conjugate coefficients. Take $F=c\mathcal O$ for a positive-time observable $\mathcal O$. What goes wrong with interpreting $\langle(\Theta F)F\rangle_E$ as a norm?

<details><summary><strong>Solution</strong></summary>

A norm should scale as

$$
\|c\mathcal O\|^2=|c|^2\|\mathcal O\|^2.
$$

If $\Theta$ were linear rather than antilinear, then

$$
\Theta(c\mathcal O)=c\Theta\mathcal O,
$$

and the proposed norm would scale like

$$
\langle(\Theta(c\mathcal O))(c\mathcal O)\rangle_E
=c^2\langle(\Theta\mathcal O)\mathcal O\rangle_E,
$$

not $|c|^2$ times the original. This can be complex or negative depending on $c$. Anti-linearity fixes the scaling:

$$
\Theta(c\mathcal O)=c^*\Theta\mathcal O,
$$

so the norm scales as $|c|^2$.

</details>

### Exercise 5: Transfer matrix intuition

Explain why a positive self-adjoint transfer matrix $T$ suggests a Hamiltonian bounded below.

<details><summary><strong>Solution</strong></summary>

If $T$ is positive and self-adjoint, its eigenvalues are real and nonnegative. For Euclidean time spacing $a_\tau$, write

$$
T=e^{-a_\tau H}.
$$

On an eigenstate of $T$ with eigenvalue $\lambda>0$,

$$
E=-\frac{1}{a_\tau}\log\lambda.
$$

After normalizing the largest eigenvalue of $T$ to correspond to the vacuum energy, the energies are bounded below. This is the lattice version of Euclidean time evolution being a damping semigroup generated by a Hamiltonian $H\geq0$.

Zero eigenvalues require domain care, but the basic spectral intuition is that positivity of the transfer matrix prevents negative-norm time evolution.

</details>

## References

### Standard first pass

- K. Osterwalder and R. Schrader, original papers on Euclidean reconstruction and reflection positivity.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive QFT and the role of positivity.
- B. Simon, *The $P(\phi)_2$ Euclidean Quantum Field Theory*, for a classic mathematical treatment of Euclidean methods.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for a physics-facing discussion of reflection positivity and the $i\epsilon$ prescription.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean field integrals, transfer matrices, and statistical-mechanics/QFT connections.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the transfer-matrix bridge between statistical systems and quantum Hamiltonians.
- I. Montvay and G. Münster, *Quantum Fields on a Lattice*, for reflection positivity and transfer matrices in lattice field theory.
- R. Haag, *Local Quantum Physics*, for the operator-algebraic side of positivity, locality, and states.

## Version history

- **2026-06-26:** Initial polished page.
