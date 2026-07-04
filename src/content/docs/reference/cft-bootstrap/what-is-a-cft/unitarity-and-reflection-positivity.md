---
title: "Unitarity and Reflection Positivity"
description: "Explains the Hilbert-space positivity conditions behind unitary CFTs, their Euclidean reflection-positivity form, and their role in conformal bootstrap constraints."
sidebar:
  label: "Unitarity and Reflection Positivity"
  order: 5
level: Graduate
status: "Polished draft"
source: "Osterwalder–Schrader 1973; Mack 1977; Minwalla 1998; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - unitarity
  - reflection positivity
  - radial quantization
  - unitarity bounds
  - positive OPE coefficients
  - conformal bootstrap
  - Hilbert space
  - Euclidean CFT
canonicalTopics:
  - unitarity-and-reflection-positivity
  - reflection-positivity
  - unitarity-bounds
  - positive-ope-data
  - bootstrap-positivity
researchStatus:
  established:
    - "In a unitary CFT, the Hilbert space has positive norm, local operators obey positivity constraints, and conformal representations satisfy unitarity bounds."
    - "In Euclidean signature, Hilbert-space positivity is encoded by reflection positivity, which is the positivity axiom used by Euclidean bootstrap arguments."
  active:
    - "Many important CFTs are nonunitary, logarithmic, gauge-fixed, or analytically continued, so crossing symmetry can survive even when positivity constraints must be modified or removed."
---

## Summary

Unitarity is the statement that quantum probabilities are positive and conserved. In a CFT, it implies that states created by local operators have nonnegative norm. In Euclidean language the same idea appears as **reflection positivity**.

For a Euclidean reflection $\theta$ that sends

$$
\theta(\tau,\mathbf x)=(-\tau,\mathbf x),
$$

reflection positivity says that any collection of operators inserted at positive Euclidean time must obey

$$
\sum_{i,j}a_i^*a_j
\left\langle
\Theta\mathcal O_i(x_i)\,\mathcal O_j(x_j)
\right\rangle
\ge 0,
\qquad
\tau_i,\tau_j>0.
$$

Here $\Theta$ reflects the insertion, acts anti-linearly on coefficients, and includes the appropriate spin transformation. For scalar Hermitian operators, the schematic meaning is simple:

$$
\langle \Psi|\Psi\rangle\ge 0.
$$

Reflection positivity is one of the reasons the conformal bootstrap becomes a convex problem. With orthonormal two-point functions, coefficients in an identical-scalar conformal-block expansion take the form

$$
\lambda_{\phi\phi\mathcal O}^2\ge 0.
$$

That innocent-looking square is dynamite. It is what lets one exclude spectra by finding positive linear functionals.

## Prerequisites

You should know [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/) and [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/). You should also be comfortable with Euclidean correlation functions, Hermitian conjugation, and the idea that local operators create states in radial quantization.

The representation-theoretic derivation of the unitarity bounds is developed later in [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/). This page gives the conceptual and practical version needed before the bootstrap chapters.

## Core idea

In Lorentzian quantum mechanics, unitarity means time evolution preserves inner products:

$$
U(t)^\dagger U(t)=1.
$$

In quantum field theory, this is not enough by itself. The state space must also have positive norm after constraints, gauge redundancies, and null states are treated correctly:

$$
\langle \Psi|\Psi\rangle\ge 0.
$$

In a CFT, local operators create states. In radial quantization,

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle.
$$

Unitarity therefore becomes a statement about local operator correlation functions. For a scalar primary normalized by

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=\frac{C_\mathcal O}{|x|^{2\Delta}},
$$

positive norm requires

$$
C_\mathcal O>0
$$

for a nonzero Hermitian operator in a unitary theory.

The same positivity propagates to descendants. Requiring all descendants to have nonnegative norm gives lower bounds on scaling dimensions. These are the unitarity bounds.

## Setup and conventions

This page uses Euclidean notation unless explicitly discussing Lorentzian evolution. The coordinate $\tau$ is Euclidean time, and $\theta$ denotes reflection through the plane $\tau=0$:

$$
\theta x=(-\tau,\mathbf x).
$$

For scalar Hermitian operators, the reflection operation is schematically

$$
\Theta\mathcal O(\tau,\mathbf x)
=
\mathcal O(-\tau,\mathbf x).
$$

For spinning operators, $\Theta$ also acts on tensor or spinor indices by the reflection matrix and complex conjugates coefficients. Those details matter in precision formulas, but the scalar case already shows the main idea.

In radial quantization, Hermitian conjugation is implemented by inversion. For a scalar primary of dimension $\Delta$,

$$
\mathcal O(x)^\dagger
=|x|^{-2\Delta}\mathcal O\left(\frac{x}{|x|^2}\right),
$$

with spin factors for spinning primaries. This is the radial version of reflection positivity.

## Lorentzian unitarity

In Lorentzian signature, a unitary QFT has a Hilbert space $\mathcal H$ with positive inner product. Time evolution is generated by a self-adjoint Hamiltonian:

$$
U(t)=e^{-iHt},
\qquad
H=H^\dagger.
$$

Then

$$
U(t)^\dagger U(t)=1.
$$

For a CFT, the conformal algebra is represented by operators with compatible adjointness relations. In radial quantization, dilatations play the role of the Hamiltonian on the cylinder:

$$
H_{\mathrm{cyl}}=D.
$$

Scaling dimensions are cylinder energies:

$$
D|\mathcal O\rangle=\Delta_\mathcal O|\mathcal O\rangle.
$$

Thus unitarity implies strong constraints on dimensions. The spectrum of $D$ must be bounded below, the identity has $\Delta=0$, and nontrivial local operators have dimensions compatible with positive descendant norms.

## Euclidean reflection positivity

Euclidean correlation functions do not show time evolution by a unitary operator directly. Instead, positivity is encoded by reflection positivity.

Let $\mathcal A_+$ be a finite linear combination of products of operators inserted at positive Euclidean time:

$$
\mathcal A_+
=
\sum_i a_i\mathcal O_{i,1}(x_{i,1})\cdots \mathcal O_{i,n_i}(x_{i,n_i}),
\qquad
\tau_{i,k}>0.
$$

Reflection positivity states

$$
\langle (\Theta\mathcal A_+)\mathcal A_+\rangle\ge 0.
$$

This is the Euclidean version of $\langle \Psi|\Psi\rangle\ge0$. The reflected operator creates the bra, and the unreflected operator creates the ket.

For a single scalar operator,

$$
\mathcal A_+=a\mathcal O(\tau,\mathbf x),
\qquad \tau>0,
$$

so positivity gives

$$
|a|^2
\langle \mathcal O(-\tau,\mathbf x)\mathcal O(\tau,\mathbf x)\rangle
\ge0.
$$

If

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=\frac{C_\mathcal O}{|x|^{2\Delta}},
$$

then this requires $C_\mathcal O\ge0$, with equality only for a null operator.

## Radial quantization and inversion

For CFT, radial quantization is often more natural than reflection across a flat Euclidean-time slice. Put the origin at the insertion point and use radius as Euclidean time:

$$
|x|=e^\tau.
$$

The map from the punctured plane to the cylinder is

$$
x^\mu=e^\tau n^\mu,
\qquad n^\mu n_\mu=1.
$$

The conjugate of an insertion inside the unit sphere is an insertion outside the unit sphere, related by inversion:

$$
x^\mu\mapsto \frac{x^\mu}{|x|^2}.
$$

For a scalar primary,

$$
|\mathcal O\rangle=\mathcal O(0)|0\rangle,
$$

and the bra is obtained by sending the conjugate operator to infinity:

$$
\langle \mathcal O|
=\lim_{x\to\infty}|x|^{2\Delta}\langle 0|\mathcal O(x).
$$

Therefore

$$
\langle \mathcal O|\mathcal O\rangle
=\lim_{x\to\infty}|x|^{2\Delta}
\langle \mathcal O(x)\mathcal O(0)\rangle.
$$

With the standard two-point normalization this gives

$$
\langle \mathcal O|\mathcal O\rangle=1.
$$

This is why orthonormal two-point functions are not just cosmetic. They are Hilbert-space normalizations.

## Positivity of OPE coefficients in scalar bootstrap

Consider a unitary CFT and a Hermitian scalar primary $\phi$ with

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{|x|^{2\Delta_\phi}}.
$$

The OPE has the schematic form

$$
\phi\times\phi
\sim
\mathbf 1+
\sum_\mathcal O \lambda_{\phi\phi\mathcal O}\mathcal O.
$$

For a four-point function of identical scalars, each exchanged primary contributes with coefficient

$$
\lambda_{\phi\phi\mathcal O}^2.
$$

In a unitary theory with an orthonormal basis of exchanged operators, this is nonnegative:

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

The conformal-block decomposition therefore has the structure

$$
\langle \phi\phi\phi\phi\rangle
=
\text{kinematic prefactor}
\times
\sum_\mathcal O
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v).
$$

Crossing symmetry says that different OPE channel decompositions of the same four-point function agree. Positivity says the coefficients in the expansion are nonnegative. Together, these two facts turn consistency into a powerful exclusion machine.

:::note[Why bootstrap bounds exist]
Crossing alone is an equation. Crossing plus positivity is an inequality problem. Inequalities let us prove that whole regions of hypothetical CFT data are impossible.
:::

## Unitarity bounds

Positive norm for all descendants implies lower bounds on scaling dimensions.

For a non-identity scalar primary in $d>2$,

$$
\Delta\ge \frac{d-2}{2}.
$$

For a symmetric traceless spin-$\ell$ primary with $\ell\ge1$,

$$
\Delta\ge \ell+d-2.
$$

These are the standard bosonic unitarity bounds for ordinary local operators in dimensions $d>2$.

The meaning of equality is important.

For a scalar, equality gives a free-field equation of motion. If

$$
\Delta=\frac{d-2}{2},
$$

then the descendant $\partial^2\mathcal O$ is null and is set to zero in the irreducible unitary representation:

$$
\partial^2\mathcal O=0.
$$

For spin $\ell\ge1$, equality means the divergence descendant is null:

$$
\partial^{\mu_1}\mathcal O_{\mu_1\cdots\mu_\ell}=0.
$$

Thus conserved currents sit at unitarity thresholds. A spin-one conserved current has

$$
\Delta_J=d-1,
$$

and the stress tensor has

$$
\Delta_T=d.
$$

The unitarity bound is therefore not merely a numerical inequality. It explains why conserved currents and stress tensors are short multiplets.

## Two-dimensional comments

In two-dimensional CFT, dimensions are written in terms of holomorphic and antiholomorphic weights:

$$
\Delta=h+\bar h,
\qquad
s=h-\bar h.
$$

Global conformal unitarity requires

$$
h\ge0,
\qquad
\bar h\ge0
$$

for nontrivial states, with the identity at $h=\bar h=0$. Full Virasoro unitarity is stronger. For example, unitary minimal models with central charge $c<1$ occur only at discrete values

$$
c=1-\frac{6}{m(m+1)},
\qquad
m=3,4,5,\ldots.
$$

This is one of the places where two-dimensional CFT is much more rigid than higher-dimensional global conformal symmetry alone.

## Reflection positivity versus reality

Reflection positivity is stronger than saying that correlators are real. A real function can still fail to define a positive Hilbert-space norm.

For example, suppose a scalar two-point function had the form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=-\frac{1}{|x|^{2\Delta}}.
$$

It is real and conformally covariant, but the state $\mathcal O(0)|0\rangle$ has negative norm. A unitary theory cannot contain such an operator as a physical Hermitian operator.

Similarly, crossing-symmetric formal expressions may fail positivity. Such objects can still be useful in nonunitary statistical mechanics, gauge-fixed descriptions, ghosts, logarithmic CFTs, or analytic continuations, but they do not obey the same bootstrap inequalities.

## Gauge theories and physical positivity

Gauge-fixed Lagrangians often contain ghosts or negative-norm auxiliary states. This does not mean the physical theory is nonunitary. It means the gauge-fixed state space is not the physical Hilbert space.

Physical unitarity is imposed after quotienting by gauge redundancy or BRST-exact states. Local gauge-invariant operators should have positive correlators in a unitary theory. Gauge-dependent fields need not.

For bootstrap purposes, this is why one usually bootstraps gauge-invariant local operators: scalars, currents, stress tensors, monopole operators, meson operators, baryon operators, or other genuine local observables. Positivity applies to the physical operator algebra, not to arbitrary gauge-fixed variables.

## Nonunitary CFTs

Not every CFT is unitary. Important examples include:

| Context | What changes |
|---|---|
| Yang–Lee edge singularity | The CFT is nonunitary; some dimensions and OPE data violate unitary positivity. |
| Ghost systems in 2D CFT | Negative-norm states appear before imposing physical constraints. |
| Logarithmic CFT | Dilatations may act non-diagonalizably; two-point functions can have logarithms. |
| Replica limits | Analytic continuation in replica number can produce nonunitary effective theories. |
| Gauge-fixed descriptions | Auxiliary state spaces may be indefinite even when the physical theory is unitary. |

Crossing symmetry, conformal covariance, and OPE associativity can still make sense in nonunitary theories. What fails is the use of positive Hilbert-space norms and nonnegative squared OPE coefficients.

This distinction is crucial. A nonunitary CFT is not “inconsistent” merely because it violates unitary bootstrap assumptions. It belongs to a different consistency class.

## How positivity powers numerical bootstrap

For identical scalar four-point functions, crossing can be written schematically as

$$
\sum_\mathcal O
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(u,v)=0,
$$

where the identity contribution is included with a fixed coefficient and $F_{\Delta,\ell}$ are crossing-vector functions.

If all coefficients other than the identity are nonnegative, then a linear functional $\alpha$ can rule out a proposed spectrum. Suppose

$$
\alpha(F_{\mathbf 1})>0
$$

and

$$
\alpha(F_{\Delta,\ell})\ge0
$$

for every allowed non-identity operator. Applying $\alpha$ to crossing gives a sum of nonnegative terms that cannot equal zero. The proposed spectrum is excluded.

This is the core logic behind many numerical bootstrap bounds. Semidefinite programming is the industrial-strength version of this positivity argument, especially for mixed correlators and spinning operators.

## Common pitfalls

### Thinking Euclidean means nonunitary

Euclidean CFTs can encode unitary Lorentzian theories. Reflection positivity is the bridge. Without it, Euclidean correlators may not reconstruct a positive Lorentzian Hilbert space.

### Forgetting null states

At the unitarity bound, some descendants have zero norm. A zero-norm descendant is not a new physical state. In an irreducible unitary representation it is quotiented out, producing conservation laws or free equations of motion.

### Applying positivity to gauge-fixed fields

Ghosts and gauge potentials in gauge-fixed descriptions are not physical local observables. Bootstrap positivity should be applied to gauge-invariant operators or to properly defined physical sectors.

### Assuming all CFTs are unitary

Many useful CFTs are nonunitary. They can still have crossing symmetry and OPE associativity. They simply do not obey the positive-coefficient constraints of unitary bootstrap.

### Confusing positive coefficients with positive functions

The statement is not that every conformal block is pointwise positive in every variable convention. The robust statement is Hilbert-space positivity: in a suitable Euclidean OPE configuration with orthonormal exchanged states, coefficients such as $\lambda^2$ are nonnegative.

### Ignoring normalization

The sign and positivity statements assume Hermitian operators and positive two-point normalization. If one uses a non-orthonormal basis, positivity is expressed by positive semidefiniteness of a matrix, not by positivity of each individual coefficient.

## Relations to other pages

This page is the positivity companion to [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) and [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/). The detailed representation theory appears in [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/).

The use of positivity in four-point functions is developed in [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), and [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/). Nonunitary examples belong later in model pages and in discussions of logarithmic CFT, Yang–Lee theory, and replica methods.

## Research status

For ordinary unitary CFTs, the relation among Lorentzian unitarity, Euclidean reflection positivity, positive-norm conformal multiplets, unitarity bounds, and positive OPE-squared coefficients is standard.

Active work often begins where the simple story needs refinement: nonunitary CFTs, logarithmic CFTs, nonlocal observables, defects, gauge-theory sectors, analytic continuation in dimension or parameters, and mixed-correlator positivity with global-symmetry representations. In numerical bootstrap, the main conceptual positivity principles are established, while algorithms for exploiting them efficiently continue to evolve.

## Exercises

### Exercise 1: Positive two-point normalization

Let $\mathcal O$ be a Hermitian scalar primary with

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{C}{|x|^{2\Delta}}.
$$

Use reflection positivity with insertions at $\tau$ and $-\tau$ to show that $C\ge0$.

<details>
<summary><strong>Solution</strong></summary>

Take

$$
\mathcal A_+=a\mathcal O(\tau,\mathbf 0),
\qquad \tau>0.
$$

Reflection positivity gives

$$
\langle (\Theta\mathcal A_+)\mathcal A_+\rangle
=|a|^2
\langle \mathcal O(-\tau,\mathbf 0)\mathcal O(\tau,\mathbf 0)\rangle
\ge0.
$$

The separation between the points is $2\tau$, so

$$
\langle \mathcal O(-\tau,\mathbf 0)\mathcal O(\tau,\mathbf 0)\rangle
=\frac{C}{(2\tau)^{2\Delta}}.
$$

Since $|a|^2\ge0$ and $(2\tau)^{2\Delta}>0$, reflection positivity requires

$$
C\ge0.
$$

For a non-null operator in a unitary theory, $C>0$.

</details>

### Exercise 2: Why OPE coefficients are squared

For identical Hermitian scalars $\phi$, explain why an exchanged scalar $\mathcal O$ appears in $\langle \phi\phi\phi\phi\rangle$ with coefficient $\lambda_{\phi\phi\mathcal O}^2$ rather than an unrelated product.

<details>
<summary><strong>Solution</strong></summary>

In the OPE channel where $(12)$ and $(34)$ are fused, the operator $\mathcal O$ appears once in the OPE of $\phi(x_1)\phi(x_2)$ and once in the OPE of $\phi(x_3)\phi(x_4)$.

For identical Hermitian scalars and an orthonormal exchanged basis, the same real coefficient appears on both sides:

$$
\phi\times\phi\supset \lambda_{\phi\phi\mathcal O}\mathcal O.
$$

Contracting the two exchanged $\mathcal O$ insertions using the normalized two-point function gives the product

$$
\lambda_{\phi\phi\mathcal O}\lambda_{\phi\phi\mathcal O}
=\lambda_{\phi\phi\mathcal O}^2.
$$

In a unitary theory this square is nonnegative.

</details>

### Exercise 3: Saturating the spin-one bound

In $d>2$, the unitarity bound for a spin-one primary is

$$
\Delta\ge d-1.
$$

What is the physical meaning of saturation?

<details>
<summary><strong>Solution</strong></summary>

For a spin-one primary $J_\mu$, the descendant $\partial^\mu J_\mu$ is a scalar descendant. The norm of this descendant is nonnegative in a unitary theory and becomes zero precisely at

$$
\Delta=d-1.
$$

A zero-norm descendant is removed from the irreducible physical representation. Therefore

$$
\partial^\mu J_\mu=0.
$$

So a spin-one primary saturating the unitarity bound is a conserved current.

</details>

### Exercise 4: Free scalar and the scalar bound

The scalar unitarity bound in $d>2$ is

$$
\Delta\ge\frac{d-2}{2}.
$$

Show that the free scalar dimension saturates it and state the corresponding null descendant.

<details>
<summary><strong>Solution</strong></summary>

A free massless scalar in $d>2$ has dimension

$$
\Delta_\phi=\frac{d-2}{2}.
$$

This equals the scalar unitarity bound, so the representation is shortened. The null descendant is the level-two scalar descendant

$$
\partial^2\phi.
$$

Setting it to zero gives the free equation of motion

$$
\partial^2\phi=0.
$$

Thus saturation of the scalar bound corresponds to a free scalar multiplet.

</details>

### Exercise 5: Crossing without positivity

Can a nonunitary CFT satisfy crossing symmetry? Explain why this does not contradict the bootstrap logic.

<details>
<summary><strong>Solution</strong></summary>

Yes. Crossing symmetry follows from OPE associativity and the statement that different OPE decompositions describe the same correlation function. These ideas can make sense even if the Hilbert space has negative-norm states.

What fails in a nonunitary CFT is not necessarily crossing. What fails is positivity. Coefficients that would be nonnegative squares in a unitary theory may have signs or appear in indefinite matrices. Therefore unitary bootstrap exclusion arguments cannot be applied unchanged.

There is no contradiction: crossing is an equation, while reflection positivity supplies inequalities. Nonunitary CFTs can obey the equation while violating the inequalities.

</details>

## References

- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” *Communications in Mathematical Physics* **31** (1973). Foundational source for reflection positivity and Euclidean reconstruction.
- G. Mack, “All Unitary Ray Representations of the Conformal Group SU(2,2) with Positive Energy,” *Communications in Mathematical Physics* **55** (1977). Classic reference for conformal unitarity representations.
- S. Minwalla, “Restrictions Imposed by Superconformal Invariance on Quantum Field Theories,” *Advances in Theoretical and Mathematical Physics* **2** (1998), arXiv:hep-th/9712074. Useful source for unitarity-bound derivations and superconformal extensions.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Pedagogical modern treatment of radial quantization, unitarity bounds, and bootstrap positivity.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Clear explanation of reflection positivity and positive coefficients in conformal-block expansions.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Review of positivity constraints and numerical bootstrap applications.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for unitarity, Virasoro representations, and two-dimensional CFT examples.

## Version history

- **2026-06-27:** Initial polished draft explaining Hilbert-space unitarity, Euclidean reflection positivity, radial quantization, positive two-point norms, positive OPE-squared coefficients, unitarity bounds, nonunitary exceptions, bootstrap implications, pitfalls, and exercises.
