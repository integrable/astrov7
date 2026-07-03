---
title: "Reflection Positivity"
description: "The Euclidean positivity condition behind Hilbert-space reconstruction, positive norm, positive energy, transfer matrices, spectral representations, and Lorentzian unitarity."
sidebar:
  label: "Reflection Positivity"
  order: 5
---

## Summary

**Reflection positivity** is the Euclidean condition that remembers the positivity of the Lorentzian Hilbert-space inner product.

Euclidean correlation functions do not directly show real-time unitarity. They are functions of Euclidean time $\tau$, not matrix elements evolved by $e^{-iHt}$. To recover a Lorentzian QFT from Euclidean data, the Euclidean theory must know how to form positive norms. The key move is to reflect Euclidean time,

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x),
$$

and compare an observable supported at positive Euclidean time with its reflected copy. For any functional $F$ built from fields with support in the half-space $\tau>0$, reflection positivity says schematically

$$
\boxed{
\langle F,F\rangle_{\rm OS}
:=\big\langle (\Theta F)F\big\rangle_E\ge0.
}
$$

Here $\Theta$ is an antilinear reflection operation: it reflects Euclidean time and complex-conjugates coefficients. The expression $\langle(\Theta F)F\rangle_E$ is the Euclidean candidate for the Lorentzian norm $\langle\Psi_F|\Psi_F\rangle$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Reflection positivity and Euclidean reconstruction](/figures/foundations/reflection-positivity-map.svg)

<figcaption>

Reflection positivity turns Euclidean half-space functionals into a positive semidefinite inner product. After quotienting null states, Euclidean time translations become $e^{-\tau H}$ with $H\ge0$, giving the Hilbert-space starting point for Lorentzian reconstruction.

</figcaption>
</figure>

This condition is one of the Osterwalder–Schrader reconstruction conditions. Weinberg lists the Osterwalder–Schrader axioms as smoothness, Euclidean covariance, reflection positivity, permutation symmetry, and cluster decomposition (Weinberg 1995, Vol. I, §9 references). The point for Foundations is not to prove the full reconstruction theorem. It is to understand the physical lesson:

```txt
A Euclidean functional integral is not automatically a unitary Lorentzian QFT.
Reflection positivity is the positivity test it must pass.
```

## Prerequisites

You should know [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/), [Wightman Functions](/foundations/correlators-and-propagators/wightman-functions/), [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/), [Spectral Condition](/foundations/structural-principles/spectral-condition/), and [Unitarity](/foundations/structural-principles/unitarity/).

:::note[Conventions]
We write Euclidean spacetime points as

$$
x=(\tau,\mathbf x),
\qquad
\theta x=(-\tau,\mathbf x).
$$

Euclidean correlation functions are Schwinger functions,

$$
S_n(x_1,\ldots,x_n)=\langle \phi(x_1)\cdots\phi(x_n)\rangle_E.
$$

For a real scalar field, the free two-point Schwinger function is

$$
S_2(x-y)
=\int\frac{d^4p_E}{(2\pi)^4}\frac{e^{ip_E\cdot(x-y)}}{p_E^2+m^2}
=\int\frac{d^3p}{(2\pi)^3}\frac{e^{-E_{\mathbf p}|\tau_x-\tau_y|+i\mathbf p\cdot(\mathbf x-\mathbf y)}}{2E_{\mathbf p}}.
$$
:::

:::note[Assumptions]
The clean scalar statement assumes Euclidean invariance, translation invariance, reflection symmetry, suitable regularity of the Schwinger functions, and fields or test functions supported away from coincident-point singularities. Gauge theories and fermions require modified reflection operations and physical-state restrictions. Reflection positivity alone is not the full Osterwalder–Schrader theorem.
:::

## Why a reflection appears

In Lorentzian QFT, a positive norm looks like

$$
\langle \Psi|\Psi\rangle\ge0.
$$

If $|\Psi\rangle$ is created from the vacuum by an operator inserted at positive time, then its bra is not created by the same operator at the same time. The bra is created by the adjoint operator on the other side of the time-reflection operation.

A simple operator example makes the point. Let

$$
|\Psi_f\rangle
=\int_{0}^{\infty}d\tau\,d^3x\,f(\tau,\mathbf x)
\,e^{-H\tau}\phi(0,\mathbf x)|0\rangle,
$$

where $H\ge0$ is the Lorentzian Hamiltonian. Then

$$
\langle\Psi_f|\Psi_f\rangle
=\int_{\tau,\tau'>0}d\tau\,d\tau'\,d^3x\,d^3y\,
f(\tau,\mathbf x)^*f(\tau',\mathbf y)
\langle0|\phi(0,\mathbf x)e^{-H(\tau+\tau')}\phi(0,\mathbf y)|0\rangle.
$$

The Euclidean time difference is $-\tau-\tau'$. In Schwinger-function language this is

$$
\int_{\tau,\tau'>0}f(\tau,\mathbf x)^*f(\tau',\mathbf y)
S_2(\theta(\tau,\mathbf x),\tau',\mathbf y)\ge0.
$$

That is reflection positivity in the one-particle sector.

So the reflection is not decorative. It is Euclidean Hermitian conjugation.

```txt
Euclidean reflection + complex conjugation = Lorentzian adjoint.
```

## The general positivity condition

Let $F$ be a polynomial functional of fields supported in the positive-time half-space. For example,

$$
F[\phi]
=\sum_i c_i\,
\phi(x_{i1})\cdots\phi(x_{in_i}),
\qquad
\tau(x_{ik})>0.
$$

For a real scalar field, define

$$
(\Theta F)[\phi]
=\sum_i c_i^*\,
\phi(\theta x_{i1})\cdots\phi(\theta x_{in_i}).
$$

Reflection positivity says

$$
\boxed{
\langle(\Theta F)F\rangle_E\ge0
\qquad \text{for all such }F.
}
$$

Equivalently, for any finite collection of positive-time monomials $F_i$ and complex numbers $c_i$,

$$
\boxed{
\sum_{i,j}c_i^*c_j\,
\langle(\Theta F_i)F_j\rangle_E\ge0.
}
$$

This is a matrix-positivity condition. It says the matrix

$$
M_{ij}=\langle(\Theta F_i)F_j\rangle_E
$$

must be positive semidefinite.

For bosonic scalar Schwinger functions, the condition can be written schematically as

$$
\sum_{i,j}c_i^*c_j\,
S_{n_i+n_j}(\theta x_{i,n_i},\ldots,\theta x_{i,1},y_{j,1},\ldots,y_{j,n_j})\ge0,
$$

where all $x$'s and $y$'s lie at positive Euclidean time. For scalar bosons the ordering is often harmless because Schwinger functions are symmetric, but the reversal matters conceptually: adjoints reverse operator order. For fermions and gauge-fixed fields, the order, signs, and reflection matrices matter.

## The free scalar check

The free massive scalar two-point function is

$$
S_2(\tau,\mathbf x)
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2E_{\mathbf p}}
\exp\left[-E_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x\right],
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Take a positive-time test function $f(\tau,\mathbf x)$. The reflection-positivity expression is

$$
I_f
=\int_{\tau,\tau'>0}d\tau\,d\tau'\,d^3x\,d^3y\,
f(\tau,\mathbf x)^*S_2(-\tau-\tau',\mathbf x-\mathbf y)f(\tau',\mathbf y).
$$

Substitute the momentum representation:

$$
I_f
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2E_{\mathbf p}}
\left|
\int_0^\infty d\tau\int d^3x\,
f(\tau,\mathbf x)
 e^{-E_{\mathbf p}\tau-i\mathbf p\cdot\mathbf x}
\right|^2.
$$

This is manifestly nonnegative:

$$
\boxed{I_f\ge0.}
$$

This calculation is worth remembering. It shows in one line how Euclidean time decay, positive energy, and positive Hilbert-space norm fit together.

## Spectral representation viewpoint

Reflection positivity is closely tied to positivity of the spectral density. A scalar two-point Schwinger function with Källén–Lehmann form has

$$
S_2(x)
=\int_0^\infty d\mu^2\,\rho(\mu^2)\,\Delta_E(x;\mu^2),
$$

where

$$
\Delta_E(x;\mu^2)
=\int\frac{d^4p_E}{(2\pi)^4}\frac{e^{ip_E\cdot x}}{p_E^2+\mu^2}.
$$

If

$$
\rho(\mu^2)\ge0,
$$

then the same free-scalar argument applies after integrating over $\mu^2$ with a positive weight. Thus two-point reflection positivity follows.

Conversely, a Euclidean two-point function with a negative spectral weight is a warning sign. For example, a propagator of the form

$$
\frac{1}{(p_E^2+m^2)(p_E^2+M^2)}
=\frac{1}{M^2-m^2}\left(
\frac{1}{p_E^2+m^2}-\frac{1}{p_E^2+M^2}
\right),
\qquad M>m,
$$

contains a negative contribution in its spectral decomposition. Such a theory may be useful as a regulator or effective intermediate description, but it does not define a standard positive-norm particle spectrum by itself. This is the Euclidean version of the ghost-state problem.

## What gets reconstructed

Reflection positivity allows one to define an inner product on positive-time Euclidean functionals:

$$
(F,G)_{\rm OS}=\langle(\Theta F)G\rangle_E.
$$

The first step is not quite a Hilbert space, because some nonzero functionals may have zero norm. One quotients by the null subspace:

$$
F\sim F+N,
\qquad
(N,N)_{\rm OS}=0,
$$

and then completes the resulting pre-Hilbert space. This is the reconstructed Hilbert space $\mathcal H$.

Euclidean time translation by $a>0$ maps positive-time functionals farther into the positive half-space. On the reconstructed Hilbert space it becomes a contraction semigroup,

$$
T(a)=e^{-aH},
$$

with a self-adjoint positive generator:

$$
\boxed{H\ge0.}
$$

That is how the Euclidean statement recovers the Lorentzian spectral condition. Spatial translations and rotations reconstruct the rest of the Euclidean symmetry action, and analytic continuation gives the Lorentzian Poincaré action under the full Osterwalder–Schrader assumptions.

The punchline is sharp:

```txt
Reflection positivity is the Euclidean path to positive norm and positive energy.
```

## Transfer matrices and lattice intuition

On a Euclidean lattice, reflection positivity is closely related to the existence of a positive transfer matrix. If the lattice time direction has spacing $a$, the partition function often has the form

$$
Z=\operatorname{Tr}T^N,
$$

where $T$ advances the system by one Euclidean time step. If $T$ is positive and self-adjoint, then one can write

$$
T=e^{-aH}
$$

with a self-adjoint Hamiltonian $H$.

This is one reason reflection positivity is not merely axiomatic window dressing. It is the lattice criterion that says the Euclidean statistical system can be interpreted as a quantum system evolving in time.

Nearest-neighbor scalar lattice actions and Wilson-type gauge actions are designed with this structure in mind. But not every lattice action that is local-looking, convergent, or numerically convenient is reflection positive. Higher-derivative improvements, nonlocal regulators, and some smeared or perfect-action constructions can obscure or violate reflection positivity at finite lattice spacing. Sometimes the violation disappears in the continuum limit; sometimes it signals that the Euclidean theory is not the shadow of a unitary Lorentzian theory.

## Relation to unitarity

Reflection positivity is not the same equation as Lorentzian unitarity. Lorentzian unitarity says, for example,

$$
U(t)^\dagger U(t)=1,
\qquad
S^\dagger S=1.
$$

Euclidean time evolution is not unitary; it is a semigroup:

$$
e^{-\tau H}.
$$

That operator damps high-energy states rather than preserving norms. Reflection positivity says that this damping evolution still comes from a positive-norm Hilbert space with $H\ge0$. After analytic continuation $\tau=it$, the same self-adjoint $H$ gives unitary Lorentzian time evolution:

$$
e^{-\tau H}\longrightarrow e^{-iHt}.
$$

So the relation is:

$$
\boxed{
\text{reflection positivity}
\quad\Longrightarrow\quad
\text{positive Euclidean reconstruction}
\quad\Longrightarrow\quad
\text{Lorentzian unitarity, under the OS hypotheses.}
}
$$

The qualification matters. Reflection positivity alone does not prove the whole theory exists as a sensible local relativistic QFT. It is one condition in a package.

## Relation to the spectral condition

The spectral condition says that the Lorentzian translation generators have joint spectrum in the closed future light cone:

$$
P\in\overline V_+.
$$

In Euclidean time, positive energy appears as decay rather than oscillation:

$$
e^{-E\tau},
\qquad E\ge0.
$$

The free-scalar check above is a miniature proof of this relation. The factor

$$
e^{-E_{\mathbf p}(\tau+\tau')}
$$

is what made the reflection-positivity integral into a positive square. If negative-energy modes were present, Euclidean time evolution would not define the same positive semigroup, and reconstruction would fail.

This is why reflection positivity is often described as the Euclidean counterpart of both Hilbert-space positivity and positive energy.

## Gauge fields and fermions

Gauge theories require care because gauge-fixed variables often live in an indefinite or redundant space.

For gauge-invariant Euclidean observables, such as Wilson loops or local gauge-invariant composites, one can ask for reflection positivity directly. For gauge-fixed gauge potentials, the naive two-point function need not be positive in the same way as a scalar two-point function, because unphysical polarizations and ghosts are present. The physical positivity statement is made after imposing constraints or passing to BRST cohomology.

Fermions also require a modified reflection operation. The Euclidean adjoint of a spinor field involves a reflection matrix and a reversal of Grassmann order, not just complex conjugation. In a healthy vectorlike theory, the full bosonic observables obtained after integrating out fermions may still satisfy appropriate positivity properties. But chiral fermions, Pfaffian signs, real chemical potentials, and sign problems can make positivity subtle or false.

The safe slogan is:

```txt
For scalars, reflection positivity is easy to write.
For gauge fields and fermions, it is still essential but less naive.
```

## Common failure modes

A Euclidean model can fail reflection positivity in several common ways.

| Failure mode | What goes wrong |
|---|---|
| Wrong-sign kinetic term | produces negative-norm excitations after reconstruction |
| Negative spectral density | violates two-point positivity |
| Higher-derivative propagator | often decomposes into positive and negative spectral pieces |
| Nonlocal time kernel | may not admit a positive transfer matrix |
| Complex Euclidean action | destroys ordinary positivity of the measure and often reflection positivity |
| Gauge-fixed unphysical fields | positivity holds only after physical projection, if at all |
| Chemical potential | Euclidean action can become complex; this is the sign-problem arena |

Some of these failures are fatal. Others are acceptable if the construction is only a regulator or if positivity is restored in the continuum limit. But the burden is on the construction: convergence and Euclidean symmetry are not enough.

## Reflection positivity is not ordinary positivity of the measure

It is tempting to say: if

$$
e^{-S_E[\phi]}\ge0,
$$

then the theory is positive. That is too weak.

A positive measure implies

$$
\langle |F|^2\rangle_E\ge0.
$$

Reflection positivity asks instead for

$$
\langle(\Theta F)F\rangle_E\ge0,
$$

where $F$ and $\Theta F$ live on opposite sides of the Euclidean time-reflection plane. The condition probes the time structure of the covariance or action, not merely the pointwise sign of the weight.

This distinction is central in lattice field theory and constructive QFT. A Euclidean measure can be honest as a probability measure and still fail to reconstruct a unitary relativistic quantum theory.

## Common pitfalls

**Pitfall 1: “Wick rotation automatically gives a unitary theory.”**  
No. Wick rotation gives Euclidean functions. Reflection positivity and the other reconstruction conditions are what make those functions candidates for a unitary Lorentzian QFT.

**Pitfall 2: “A positive Euclidean action is enough.”**  
No. Positivity of $e^{-S_E}$ is not the same as reflection positivity.

**Pitfall 3: “Reflection positivity means Euclidean time evolution is unitary.”**  
No. Euclidean time evolution is $e^{-\tau H}$, not $e^{-iHt}$. Reflection positivity lets $H$ be reconstructed as a positive self-adjoint Hamiltonian.

**Pitfall 4: “Gauge-field propagators must be positive component by component.”**  
Not in a gauge-fixed redundant description. Positivity is a statement about physical states and gauge-invariant observables, or about BRST cohomology in a gauge-fixed formalism.

**Pitfall 5: “If a regulator violates reflection positivity, the theory is useless.”**  
Not always. Some regulators violate positivity at finite cutoff but are still useful if the continuum limit restores the desired unitary theory. But this must be checked; it is not automatic.

## Relation to nearby pages

- [Euclidean QFT](/foundations/path-integral-formalism/euclidean-qft/) introduces Wick rotation, Schwinger functions, and why Euclidean reconstruction needs extra conditions.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) explains the Källén–Lehmann positivity that appears here as two-point reflection positivity.
- [Spectral Condition](/foundations/structural-principles/spectral-condition/) explains positive energy in Lorentzian signature.
- [Unitarity](/foundations/structural-principles/unitarity/) explains positive-norm time evolution and S-matrix probability conservation.
- [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) explains another Osterwalder–Schrader ingredient: long-distance independence.
- [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/) explains why measures and Jacobians are not innocent details.
- [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) explains why gauge-fixed positivity must be stated on physical cohomology.

## Research status

Reflection positivity is a **standard structural condition** in Euclidean QFT, constructive QFT, lattice field theory, and the Osterwalder–Schrader reconstruction theorem.

In practical physics, the main subtlety is not the scalar free-field condition. It is whether a regulator, lattice action, gauge fixing, fermion determinant, nonlocal effective action, thermal ensemble, chemical potential, or continuum limit preserves enough positivity to reconstruct the desired Lorentzian theory. The principle is stable; verifying it in a specific nonperturbative construction can be highly nontrivial.

## Exercises

### Exercise 1: Free scalar two-point positivity

Let $f(\tau,\mathbf x)$ have support only for $\tau>0$. Using

$$
S_2(\tau,\mathbf x)
=\int\frac{d^3p}{(2\pi)^3}\frac{e^{-E_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x}}{2E_{\mathbf p}},
$$

show that

$$
I_f=\int_{\tau,\tau'>0}f(\tau,\mathbf x)^*S_2(-\tau-\tau',\mathbf x-\mathbf y)f(\tau',\mathbf y)
$$

is nonnegative.

<details>
<summary><strong>Solution</strong></summary>

Substitute the momentum representation. Since $\tau,\tau'>0$,

$$
|(-\tau)-\tau'|=\tau+\tau'.
$$

Therefore

$$
I_f
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2E_{\mathbf p}}
\int_0^\infty d\tau\,d^3x\,f(\tau,\mathbf x)^*e^{-E_{\mathbf p}\tau+i\mathbf p\cdot\mathbf x}
\int_0^\infty d\tau'\,d^3y\,f(\tau',\mathbf y)e^{-E_{\mathbf p}\tau'-i\mathbf p\cdot\mathbf y}.
$$

This is

$$
I_f
=\int\frac{d^3p}{(2\pi)^3}\frac{1}{2E_{\mathbf p}}
\left|\int_0^\infty d\tau\,d^3x\,f(\tau,\mathbf x)e^{-E_{\mathbf p}\tau-i\mathbf p\cdot\mathbf x}\right|^2\ge0.
$$

</details>

### Exercise 2: Positivity matrix for two insertions

Let $x$ and $y$ have positive Euclidean time. Take

$$
F=c_1\phi(x)+c_2\phi(y).
$$

Write the reflection-positivity condition as a two-by-two matrix inequality.

<details>
<summary><strong>Solution</strong></summary>

The reflected functional is

$$
\Theta F=c_1^*\phi(\theta x)+c_2^*\phi(\theta y).
$$

Then

$$
\langle(\Theta F)F\rangle_E
=\sum_{i,j=1}^2 c_i^*c_j S_2(\theta x_i,x_j),
$$

where $x_1=x$ and $x_2=y$. Reflection positivity says the matrix

$$
M_{ij}=S_2(\theta x_i,x_j)
$$

is positive semidefinite:

$$
\begin{pmatrix}
S_2(\theta x,x) & S_2(\theta x,y)\\
S_2(\theta y,x) & S_2(\theta y,y)
\end{pmatrix}\ge0.
$$

Equivalently,

$$
\sum_{i,j=1}^2c_i^*M_{ij}c_j\ge0
$$

for all complex $c_1,c_2$.

</details>

### Exercise 3: Negative spectral weight

Suppose a Euclidean scalar two-point function has the form

$$
S_2(x)=\Delta_E(x;m^2)-\Delta_E(x;M^2),
\qquad M>m.
$$

Explain why this is not reflection positive in the two-point sector.

<details>
<summary><strong>Solution</strong></summary>

For a positive spectral representation, the two-point function should be a nonnegative superposition of free Euclidean propagators:

$$
S_2(x)=\int_0^\infty d\mu^2\,\rho(\mu^2)\Delta_E(x;\mu^2),
\qquad \rho(\mu^2)\ge0.
$$

Here the spectral density is

$$
\rho(\mu^2)=\delta(\mu^2-m^2)-\delta(\mu^2-M^2),
$$

which has a negative part. By choosing test functions whose Laplace-Fourier transform has support concentrated near the mass $M$, the negative contribution can dominate the reflection-positivity integral. Therefore the two-point positivity condition fails.

</details>

### Exercise 4: Why the quotient by null states is needed

Reflection positivity gives

$$
(F,F)_{\rm OS}\ge0.
$$

Why is this only a positive semidefinite form, and why do we quotient by zero-norm functionals?

<details>
<summary><strong>Solution</strong></summary>

A positive semidefinite form can have nonzero vectors or functionals $N$ with

$$
(N,N)_{\rm OS}=0.
$$

Such functionals represent no physical state in the reconstructed Hilbert space. To obtain a genuine inner product, one identifies

$$
F\sim F+N
$$

for every null functional $N$. On equivalence classes, the inner product is positive definite, and completing the space gives the Hilbert space.

This is the same logic used whenever one constructs a physical Hilbert space from a redundant or semidefinite pre-space.

</details>

### Exercise 5: Transfer matrix intuition

Assume a Euclidean lattice theory has a positive self-adjoint transfer matrix $T$ advancing time by one lattice spacing $a$. Show how this gives a self-adjoint Hamiltonian with nonnegative spectrum.

<details>
<summary><strong>Solution</strong></summary>

If $T$ is positive and self-adjoint, the spectral theorem lets us define

$$
H=-\frac{1}{a}\log T
$$

on the subspace where $T$ has positive spectrum. Then

$$
T=e^{-aH}.
$$

If the transfer matrix eigenvalues satisfy $0<\lambda\le1$ after the usual normalization of the vacuum energy, then

$$
E=-\frac{1}{a}\log\lambda\ge0.
$$

Thus Euclidean time evolution by $T$ is generated by a self-adjoint Hamiltonian with nonnegative spectrum.

</details>

### Exercise 6: Positive measure versus reflection positivity

A Euclidean action has $e^{-S_E[\phi]}\ge0$. Does this automatically imply reflection positivity? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. A positive measure implies

$$
\langle |F|^2\rangle_E\ge0.
$$

Reflection positivity asks for a different expression:

$$
\langle(\Theta F)F\rangle_E\ge0,
$$

where $\Theta F$ is the reflected, complex-conjugated functional. This tests whether the Euclidean time structure can be interpreted as a Hilbert-space norm after reconstruction. A positive measure with a nonlocal or higher-derivative time kernel can still fail this test.

</details>

## Sources and further reading

- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” for the original reconstruction conditions and reflection positivity.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §9 references, for the place of the Osterwalder–Schrader axioms in path-integral QFT.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive QFT and Euclidean positivity.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the Lorentzian axiomatic side of the reconstruction story.
- K. G. Wilson, lattice field theory sources, and modern lattice-QFT texts for transfer matrices and reflection positivity at finite lattice spacing.
- B. Simon, *The $P(\phi)_2$ Euclidean Quantum Field Theory*, for a classic constructive example.

## Version history

- **2026-05-23:** Initial qft.org page on reflection positivity, Euclidean half-space functionals, the free scalar check, spectral positivity, Hilbert-space reconstruction, transfer matrices, gauge/fermion caveats, and exercises.
