---
title: "Current Matrix Elements"
description: "How conserved and nonconserved current matrix elements are decomposed into form factors, constrained by Ward identities, and normalized by charges."
sidebar:
  label: "Current Matrix Elements"
  order: 4
level: Graduate
status: "Polished draft"
source: "Weinberg, Vols. I–II; Srednicki, scattering and spinor chapters; Coleman, current algebra and LSZ lectures; Schwartz, QED, Ward identities, unitarity, and form-factor discussions."
topics:
  - currents
  - matrix elements
  - form factors
  - Ward identities
  - charge normalization
canonicalTopics:
  - current-matrix-elements
  - current-form-factors
  - ward-identities-for-matrix-elements
  - charge-normalization
researchStatus:
  established:
    - "Lorentz decomposition of current matrix elements, Ward-identity constraints, and charge normalization are standard tools in QFT, particle physics, and hadron physics."
  active:
    - "Nonperturbative hadronic current matrix elements, lattice extractions, generalized parton distributions, gravitational form factors, and precision electroweak current matrix elements remain active research areas."
---

## Summary

A **current matrix element** is a form factor of a current operator. For a current $J^\mu(x)$ and one-particle states, the basic object is

$$
\langle p',s'|J^\mu(0)|p,s\rangle.
$$

Symmetry turns this matrix element into a small number of scalar functions of invariant momentum transfer. Those scalar functions are the current form factors. For a spinless particle of equal initial and final mass, a conserved vector current has the simple form

$$
\langle p'|J^\mu(0)|p\rangle
=
(p'+p)^\mu F(q^2),
\qquad
q=p'-p.
$$

For a spin-$1/2$ particle and the electromagnetic current, the standard parity-even decomposition is

$$
\langle p',s'|J^\mu(0)|p,s\rangle
=
\overline u(p',s')
\left[
\gamma^\mu F_1(q^2)
+
\frac{i\sigma^{\mu\nu}q_\nu}{2m}F_2(q^2)
\right]
u(p,s),
$$

where $F_1$ and $F_2$ are the Dirac and Pauli form factors.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![A current matrix element is constrained by Lorentz symmetry and Ward identities into a finite set of form factors](/figures/perturbative-qft/current-matrix-elements.svg)

<figcaption>

A current insertion between physical states is constrained by Lorentz symmetry, current conservation, and charge normalization. The remaining invariant information is encoded in form factors such as $F(q^2)$ for scalar states or $F_1(q^2)$ and $F_2(q^2)$ for spin-$1/2$ states.

</figcaption>
</figure>

Current matrix elements are where local symmetries meet measurable structure. They encode electric charge, magnetic moments, weak charges, axial couplings, hadron structure, parton distributions in limiting kinematics, stress-tensor responses, and EFT Wilson-coefficient matrix elements.

## Prerequisites

You should know [Form Factors](/perturbative-qft/form-factors-composite-operators/form-factors/), [Operator Renormalization Preview](/perturbative-qft/form-factors-composite-operators/operator-renormalization-preview/), [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/), [External Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), and [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) for massless-helicity applications.

## Core idea

A current is a local operator with a spacetime index and usually a symmetry interpretation. Its matrix element is a local probe of a physical state. The hard part is not writing down the matrix element; the hard part is separating what is forced by symmetry from what contains dynamics.

The workflow is:

```txt
choose the current and external states
  → list all Lorentz-covariant tensor structures
  → impose current conservation or Ward identities
  → impose discrete symmetries and hermiticity if relevant
  → choose a minimal form-factor basis
  → fix normalization at special kinematic points when possible
```

The scalar functions left over after this process are the form factors. They are where the dynamics lives.

A current matrix element is therefore not a random vector-valued function. It is a symmetry-controlled object with a finite tensor basis and physically meaningful scalar coefficients.

## Setup and conventions

Let

$$
q=p'-p,
\qquad
P=p'+p.
$$

For equal-mass external states,

$$
q\cdot P=p'^2-p^2=0.
$$

A conserved current obeys

$$
\partial_\mu J^\mu=0,
$$

up to anomalies, explicit symmetry breaking, contact terms, or equations of motion. Between separated on-shell external states this gives the Ward-identity constraint

$$
q_\mu\langle f|J^\mu(0)|i\rangle=0.
$$

This equation should be read with care. In correlation functions, Ward identities usually include contact terms. In matrix elements between distinct on-shell states, the contact terms have already been reduced into charge actions or external-state constraints.

## Scalar current matrix element

For equal-mass spinless states and a vector current, Lorentz covariance allows

$$
\langle p'|J^\mu(0)|p\rangle
=
P^\mu F(q^2)+q^\mu G(q^2).
$$

If the current is conserved, then

$$
0=q_\mu\langle p'|J^\mu(0)|p\rangle
=(q\cdot P)F(q^2)+q^2G(q^2).
$$

For equal masses, $q\cdot P=0$. Away from $q^2=0$, current conservation therefore sets $G(q^2)=0$. The standard conserved-current decomposition is

$$
\langle p'|J^\mu(0)|p\rangle
=P^\mu F(q^2).
$$

The normalization at zero momentum transfer is fixed by the charge. If

$$
Q=\int d^3\mathbf x\,J^0(t,\mathbf x)
$$

acts on the one-particle state with charge $Q_\phi$, then

$$
F(0)=Q_\phi.
$$

For an electromagnetic current and a unit-charged scalar, $F(0)=1$.

At small spacelike momentum transfer $Q^2=-q^2>0$, one often writes

$$
F(-Q^2)=Q_\phi\left[1-\frac{Q^2}{6}\langle r^2\rangle+\cdots\right],
$$

which defines the mean-square charge radius when a nonrelativistic spatial interpretation is appropriate. The sign looks different if one expands in $q^2$ instead of $Q^2$.

## Spin-one-half electromagnetic current

For a massive spin-$1/2$ particle, Lorentz covariance, parity, and current conservation give the standard electromagnetic decomposition

$$
\langle p',s'|J^\mu(0)|p,s\rangle
=
\overline u(p',s')
\left[
\gamma^\mu F_1(q^2)
+
\frac{i\sigma^{\mu\nu}q_\nu}{2m}F_2(q^2)
\right]
u(p,s),
$$

where

$$
\sigma^{\mu\nu}=\frac{i}{2}[\gamma^\mu,\gamma^\nu].
$$

The two functions have direct low-momentum interpretations:

| Form factor | Meaning at $q^2=0$ |
|---|---|
| $F_1(0)$ | electric charge in units of the chosen current normalization |
| $F_2(0)$ | anomalous magnetic moment contribution |

For the electron in QED, the zero-momentum normalization depends on how the current is defined. If one uses the number current

$$
J^\mu=\overline\psi\gamma^\mu\psi,
$$

then $F_1(0)=1$ for the electron field. If one instead uses the physical electric current

$$
j^\mu=-e\overline\psi\gamma^\mu\psi,
$$

the zero-momentum matrix element carries the charge $-e$. Many particle-physics conventions factor out the electric charge from the vertex and quote a dimensionless $F_1(0)=1$. Always check whether the factor $e$ and the sign of the charge are included in the current or in the external coupling.

The Pauli form factor $F_2(0)$ gives the anomalous part of the magnetic moment. At tree level in minimal Dirac QED, $F_2(0)=0$. Loop corrections generate the famous anomalous magnetic moment.

## Ward identity check

For the spin-$1/2$ current above, current conservation follows directly on shell. Contract with $q_\mu$. Using $q\!\!\!/\equiv\gamma^\mu q_\mu$ and similarly for $p\!\!\!/$,

$$
q_\mu\gamma^\mu=q\!\!\!/=p'\!\!\!/-p\!\!\!/,
$$

while

$$
q_\mu\sigma^{\mu\nu}q_\nu=0
$$

because $\sigma^{\mu\nu}$ is antisymmetric and $q_\mu q_\nu$ is symmetric. Therefore

$$
q_\mu\langle p'|J^\mu(0)|p\rangle
=
\overline u(p') (p'\!\!\!/-p\!\!\!/) F_1(q^2)u(p).
$$

Using the free on-shell Dirac equations for the external spinors,

$$
\overline u(p')(p'\!\!\!/-m)=0,
\qquad
(p\!\!\!/-m)u(p)=0,
$$

the contraction vanishes. This is the matrix-element version of the Ward identity.

Off shell, the stronger vertex Ward–Takahashi identity relates the current vertex to inverse propagators. Schematically,

$$
q_\mu\Gamma^\mu(p+q,p)
=S^{-1}(p+q)-S^{-1}(p),
$$

with charge factors and sign conventions depending on the definition of the current. On shell, the inverse propagators vanish on external wave functions, reducing the identity to current conservation for the matrix element.

## Axial and weak currents

Not all currents are conserved. For a Dirac field, the vector and axial currents are

$$
J_V^\mu=\overline\psi\gamma^\mu\psi,
\qquad
J_A^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

The vector current is conserved when it is associated with an exact global $U(1)$ symmetry. The axial current is more delicate. It can be explicitly broken by masses and quantum mechanically broken by anomalies. Therefore axial-current matrix elements can contain additional structures and different normalization conditions.

For nucleon matrix elements, a common axial-current decomposition is schematically

$$
\langle p'|J_A^\mu(0)|p\rangle
=
\overline u(p')
\left[
\gamma^\mu\gamma^5 G_A(q^2)
+q^\mu\gamma^5 G_P(q^2)
\right]
u(p),
$$

where $G_A$ is the axial form factor and $G_P$ is an induced pseudoscalar form factor. The detailed normalization depends on flavor generators and current conventions.

The lesson is broader than this example: once a current is not exactly conserved, longitudinal structures are no longer automatically removed.

## Hermiticity and discrete symmetries

If $J^\mu$ is Hermitian, matrix elements obey reality relations. For identical stable states, these often imply that form factors are real below the first physical threshold in the appropriate kinematic region. Above threshold, form factors generally acquire imaginary parts because intermediate states can go on shell.

Discrete symmetries further restrict the tensor basis. Parity forbids some structures and allows others. Time reversal can impose additional constraints. Charge conjugation controls which currents connect which particle and antiparticle states.

These constraints are not decorative. They prevent overcounting. A good form-factor decomposition contains all allowed structures and no redundant ones.

## Charges and normalization

The most important special point is often $q=0$. If $J^\mu$ is the conserved current for an exact symmetry, then

$$
Q=\int d^3\mathbf x\,J^0(t,\mathbf x)
$$

acts on one-particle states as the symmetry generator. For a state $|p,a\rangle$ in a representation of the symmetry,

$$
Q^A|p,a\rangle=(T^A)_{ba}|p,b\rangle.
$$

This fixes the zero-momentum-transfer normalization of the corresponding current matrix element. For Abelian charge, this reduces to $F(0)=Q$ after the kinematic normalization is factored out.

If the current is not conserved, or if the operator is a renormalized composite current not tied to an exact symmetry, there may be no such fixed normalization. One must then define the current by a renormalization condition, a lattice normalization, an EFT matching condition, or a symmetry convention.

## Perturbative versus nonperturbative matrix elements

For elementary particles in weakly coupled QED or electroweak theory, current matrix elements can be computed perturbatively. The electron form factors are the classic example.

For hadrons, current matrix elements are generally nonperturbative at low momentum transfer. They are extracted from experiment, lattice QCD, dispersion relations, chiral EFT, sum rules, or phenomenological parameterizations. Perturbative QCD becomes useful in appropriate high-energy or factorized regimes, but the low-energy form factors are not ordinary small-coupling series.

The definition of the matrix element is the same in both cases. What changes is the method used to compute or constrain the scalar functions.

## Current matrix elements and LSZ

To compute a current matrix element perturbatively, start with a Green function with one current insertion,

$$
\langle0|T\{J^\mu(x)\Phi_1(x_1)\cdots\Phi_n(x_n)\}|0\rangle,
$$

then apply LSZ to the external particle fields. The current insertion is not an external particle leg. It is the local operator whose matrix element is being extracted.

In QED, the amputated current insertion between fermion legs is the vertex function $\Gamma^\mu$. On shell, after multiplying by external spinors and residues, it becomes the physical current matrix element. The Ward identity constrains $\Gamma^\mu$ before the on-shell limit and constrains the form factors after the on-shell limit.

## Common pitfalls

**Forgetting the charge convention.** Some authors include the electric charge in $J^\mu$; others define a unit-normalized current and attach $e$ in the coupling. This changes $F_1(0)$ signs and factors.

**Using current conservation off shell as if there were no contact terms.** Ward identities for correlators include contact terms. The simple equation $q_\mu\langle J^\mu\rangle=0$ is the separated-point or on-shell matrix-element version.

**Keeping redundant tensor structures.** Lorentz covariance gives a spanning set, not automatically a minimal independent basis. Use on-shell equations, current conservation, Schouten identities, Gordon identities, and discrete symmetries to reduce the basis.

**Assuming every current is protected.** Exactly conserved symmetry currents are protected after normalization. Nonconserved currents, anomalous currents, and effective currents can renormalize.

**Confusing timelike and spacelike momentum transfer.** Form factors have different analytic behavior in spacelike scattering and timelike production regions. Thresholds and imaginary parts matter.

**Treating hadronic form factors as perturbative at all scales.** Low-energy hadronic current matrix elements are nonperturbative even though the current itself is a local QFT operator.

## Relations to other pages

- [Form Factors](/perturbative-qft/form-factors-composite-operators/form-factors/) introduces local-operator matrix elements in general.
- [Composite Operator Insertions](/perturbative-qft/form-factors-composite-operators/composite-operator-insertions/) explains how current insertions arise from source derivatives.
- [Operator Renormalization Preview](/perturbative-qft/form-factors-composite-operators/operator-renormalization-preview/) explains when current-like operators do or do not require renormalization.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) gives the perturbative identity behind charge renormalization and current conservation.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how finite matrix elements are defined after wavefunction, parameter, and operator renormalization.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) explains why form factors develop imaginary parts above physical thresholds.
- The detailed hadronic and lattice-current story belongs in the Gauge Theories and Standard Model, Nonperturbative QFT, and Matter/Statistical Physics volumes.

## Research status

- **Established:** Lorentz decompositions, Ward identities, charge normalization, and perturbative current form factors are standard tools in QFT.
- **Nonperturbative:** Hadronic electromagnetic, axial, scalar, and stress-tensor matrix elements require nonperturbative input at low energies.
- **Active:** Precision form factors, lattice-current renormalization, generalized parton distributions, gravitational form factors, flavor-changing currents, and EFT matching for currents remain active research areas.
- **Convention-dependent:** Signs and normalizations depend on whether coupling constants are included in the current, how states are normalized, and which form-factor basis is chosen.

## Exercises

### Exercise 1: Scalar current conservation

For equal-mass scalar states, start from

$$
\langle p'|J^\mu(0)|p\rangle
=P^\mu F(q^2)+q^\mu G(q^2),
\qquad
P=p'+p,
\qquad
q=p'-p.
$$

Use current conservation to show that $G(q^2)=0$ away from $q^2=0$.

<details>
<summary><strong>Solution</strong></summary>

Current conservation gives

$$
0=q_\mu\langle p'|J^\mu(0)|p\rangle
=(q\cdot P)F(q^2)+q^2G(q^2).
$$

For equal masses,

$$
q\cdot P=(p'-p)\cdot(p'+p)=p'^2-p^2=m^2-m^2=0.
$$

Therefore

$$
q^2G(q^2)=0.
$$

For $q^2\neq0$, this implies

$$
G(q^2)=0.
$$

At $q^2=0$, the decomposition may require separate care because longitudinal terms can be hidden by kinematic singularities or contact terms.

</details>

### Exercise 2: Ward identity for the spinor decomposition

Show that the spin-$1/2$ electromagnetic decomposition

$$
\overline u(p')
\left[
\gamma^\mu F_1(q^2)
+
\frac{i\sigma^{\mu\nu}q_\nu}{2m}F_2(q^2)
\right]
u(p)
$$

is conserved between on-shell spinors.

<details>
<summary><strong>Solution</strong></summary>

Contract with $q_\mu$. The Pauli term vanishes because

$$
q_\mu\sigma^{\mu\nu}q_\nu=0,
$$

since $\sigma^{\mu\nu}$ is antisymmetric and $q_\mu q_\nu$ is symmetric.

The remaining term is

$$
\overline u(p')q\!\!\!/F_1(q^2)u(p)
=
\overline u(p')(p'\!\!\!/-p\!\!\!/)F_1(q^2)u(p).
$$

Using the on-shell Dirac equations,

$$
\overline u(p')p'\!\!\!/=m\overline u(p'),
\qquad
p\!\!\!/u(p)=m u(p),
$$

we get

$$
\overline u(p')(p'\!\!\!/-p\!\!\!/)u(p)
=m\overline u(p')u(p)-m\overline u(p')u(p)=0.
$$

Thus the matrix element is conserved on shell.

</details>

### Exercise 3: Charge radius sign

Let $Q^2=-q^2>0$ be spacelike momentum transfer and suppose

$$
F(-Q^2)=1-\frac{Q^2}{6}\langle r^2\rangle+O(Q^4).
$$

Rewrite the same expansion in terms of $q^2$ near $q^2=0$.

<details>
<summary><strong>Solution</strong></summary>

Since $Q^2=-q^2$, substitute into the expansion:

$$
F(q^2)=1-\frac{(-q^2)}{6}\langle r^2\rangle+O((q^2)^2).
$$

Therefore

$$
F(q^2)=1+\frac{q^2}{6}\langle r^2\rangle+O((q^2)^2).
$$

Equivalently,

$$
\langle r^2\rangle=6\left.\frac{dF(q^2)}{dq^2}\right|_{q^2=0}
=-6\left.\frac{dF(-Q^2)}{dQ^2}\right|_{Q^2=0}.
$$

The sign confusion comes from switching between timelike $q^2$ and spacelike $Q^2$ variables.

</details>

### Exercise 4: Why a nonconserved current has more structures

Explain why the scalar decomposition

$$
\langle p'|J^\mu(0)|p\rangle
=P^\mu F(q^2)+q^\mu G(q^2)
$$

cannot generally be reduced to one form factor if $J^\mu$ is not conserved.

<details>
<summary><strong>Solution</strong></summary>

The reduction to one form factor used current conservation:

$$
q_\mu\langle p'|J^\mu(0)|p\rangle=0.
$$

If the current is not conserved, then the divergence is not zero. It may be proportional to an explicit breaking term, a mass term, an anomaly, or another operator matrix element. Therefore the equation that set $q^2G(q^2)$ to zero is absent. Lorentz covariance alone allows both $P^\mu$ and $q^\mu$, so both scalar functions are needed unless another symmetry or kinematic condition removes one of them.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for scattering theory, current matrix elements, and Lorentz-covariant state normalization; Vol. II, for currents, operator methods, and applications to strong and electroweak interactions.
- M. Srednicki, *Quantum Field Theory*, for LSZ, spinor matrix elements, QED form factors, and current-normalization conventions.
- S. Coleman, *Lectures on Quantum Field Theory*, especially current algebra, LSZ, and symmetry-current discussions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for QED Ward identities, electromagnetic form factors, and Standard Model current examples.
- J. D. Bjorken and S. D. Drell, *Relativistic Quantum Fields*, for classic current matrix element decompositions and spinor technology.
- J. C. Collins, *Renormalization*, for current operators, operator renormalization, and matrix elements in factorized observables.

## Version history

- **2026-06-13:** Initial polished draft. Added the current-matrix-element figure and fixed the current-conservation checks for scalar and spin-$1/2$ external states.
