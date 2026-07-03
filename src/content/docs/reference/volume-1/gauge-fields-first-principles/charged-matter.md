---
title: "Charged Matter"
description: "Charged scalar and spinor matter coupled to an Abelian gauge field: local phase covariance, covariant derivatives, minimal coupling, currents, scalar QED, spinor QED, and the bridge to non-Abelian gauge theory."
sidebar:
  label: "Charged Matter"
  order: 3
---

## Summary

A **charged matter field** is a field whose phase, or more generally whose internal orientation, transforms under a gauge redundancy. For an Abelian gauge field, qft.org uses

$$
\boxed{
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
}
$$

and the covariant derivative

$$
\boxed{D_\mu=\partial_\mu+iqA_\mu.}
$$

Then

$$
\boxed{D_\mu\Phi\mapsto e^{-iq\alpha(x)}D_\mu\Phi.}
$$

This is the small but crucial mechanism behind minimal coupling. The ordinary derivative of a locally phase-rotated field produces an unwanted derivative of the phase, while the gauge field shifts in exactly the way needed to cancel it. Coleman presents this as the central reason for introducing the covariant derivative in electrodynamics: localizing the phase symmetry forces the derivative to be repaired by the vector potential (Coleman 2019, ch. 27). Srednicki's scalar electrodynamics makes the same structure explicit: replacing ordinary derivatives by covariant derivatives gives the gauge-invariant scalar QED Lagrangian and produces both one-photon and two-photon scalar vertices (Srednicki 2007, §61). Weinberg's general gauge-theory treatment emphasizes that matter fields couple according to their representation of the gauge group; neutral fields are simply in the trivial representation (Weinberg 1995, Vol. I, ch. 8; Weinberg 1996, Vol. II, §15.1).

<figure class="doc-figure" style="--figure-width: 54rem;">

![Charged matter and the covariant derivative](/figures/foundations/charged-matter-covariant-derivative.svg)

<figcaption>

Promoting a global phase to a local phase makes the ordinary derivative fail by an extra $\partial_\mu\alpha$ term. The gauge potential shifts by the same derivative, so $D_\mu=\partial_\mu+iqA_\mu$ transforms covariantly. Scalar and Dirac matter then couple to $A_\mu$ through gauge-invariant local terms.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/), [Dirac Field](/foundations/free-fields/dirac-field/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

:::note[Conventions]
For Abelian gauge theory, qft.org uses

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

For a field of charge $-q$, use the opposite sign:

$$
D_\mu\Phi^\dagger=(\partial_\mu-iqA_\mu)\Phi^\dagger.
$$

Many books use $D_\mu=\partial_\mu-iqA_\mu$ together with $A_\mu\mapsto A_\mu-\partial_\mu\alpha$. The sign is conventional; consistency is not.
:::

:::note[Scope]
This page treats Abelian charged matter. It introduces scalar QED and spinor QED as local gauge theories, but it does not do loop calculations, QED renormalization, infrared physics, photon LSZ, or the full Standard Model. Those belong later.
:::

## From global phase to local phase

Start with a complex scalar field with global phase symmetry,

$$
\Phi(x)\mapsto e^{-iq\alpha_0}\Phi(x),
$$

where $\alpha_0$ is constant. The free Lagrangian

$$
\mathcal L_0
=\partial_\mu\Phi^\dagger\partial^\mu\Phi-m^2\Phi^\dagger\Phi
$$

is invariant because each $\Phi$ is paired with a $\Phi^\dagger$, and the derivative does not see a constant phase.

Now try to let the phase depend on spacetime:

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x).
$$

The derivative transforms as

$$
\partial_\mu\Phi
\mapsto
\partial_\mu\left(e^{-iq\alpha}\Phi\right)
=e^{-iq\alpha}\left(\partial_\mu\Phi-iq(\partial_\mu\alpha)\Phi\right).
$$

The extra term is the whole issue:

$$
-iq(\partial_\mu\alpha)\Phi.
$$

The ordinary derivative compares the field at nearby points. But if the phase convention can be chosen independently at nearby points, an ordinary subtraction compares quantities expressed in different local phase frames. The gauge field supplies the missing rule for comparing phases at neighboring points.

## The covariant derivative

Introduce a gauge potential $A_\mu$ that shifts as

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Define

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi.
$$

Then

$$
\begin{aligned}
D_\mu'\Phi'
&=(\partial_\mu+iqA_\mu+iq\partial_\mu\alpha)
\left(e^{-iq\alpha}\Phi\right) \\
&=e^{-iq\alpha}\partial_\mu\Phi
-iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi
+iqA_\mu e^{-iq\alpha}\Phi
+iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi \\
&=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\Phi.
\end{aligned}
$$

So

$$
\boxed{D_\mu'\Phi'=e^{-iq\alpha}D_\mu\Phi.}
$$

That is what “covariant” means here: $D_\mu\Phi$ transforms in the same way as $\Phi$.

For a neutral field, $q=0$, so $D_\mu=\partial_\mu$. Neutral fields do not couple minimally to this Abelian gauge field. They can still couple through gauge-invariant composite operators, such as $F_{\mu\nu}F^{\mu\nu}$ or magnetic-moment operators, but those are not minimal charge couplings.

## Scalar QED

The Abelian gauge theory of a charged complex scalar is usually called **scalar QED**. With qft.org conventions, a standard Lagrangian is

$$
\boxed{
\mathcal L_\text{scalar QED}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+(D_\mu\Phi)^\dagger D^\mu\Phi
-m^2\Phi^\dagger\Phi
-\frac{\lambda}{4}(\Phi^\dagger\Phi)^2.
}
$$

The scalar kinetic term is gauge invariant because

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
\mapsto
(e^{+iq\alpha}D_\mu\Phi^\dagger)
(e^{-iq\alpha}D^\mu\Phi)
=(D_\mu\Phi)^\dagger D^\mu\Phi.
$$

The mass and quartic terms are also invariant because $\Phi^\dagger\Phi$ is invariant:

$$
\Phi^\dagger\Phi
\mapsto
(e^{+iq\alpha}\Phi^\dagger)(e^{-iq\alpha}\Phi)
=\Phi^\dagger\Phi.
$$

Expanding the scalar kinetic term gives

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
=\partial_\mu\Phi^\dagger\partial^\mu\Phi
+iqA_\mu\left[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi\right]
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
$$

It is useful to define the free scalar current

$$
j^\mu_\text{free}
=iq\left[\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right].
$$

Then the interaction terms include

$$
\mathcal L_\text{int}
=-A_\mu j^\mu_\text{free}
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
$$

The second term is the famous **seagull** or two-photon scalar vertex. It is not optional decoration. It is forced by gauge invariance because the scalar kinetic term is quadratic in the covariant derivative. Srednicki highlights precisely this feature in scalar electrodynamics: the current depends explicitly on the gauge field, and that dependence is essential for gauge invariance (Srednicki 2007, §61).

## Spinor QED

For a charged Dirac field,

$$
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{+iq\alpha}.
$$

The minimally coupled Lagrangian is

$$
\boxed{
\mathcal L_\text{spinor QED}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi.
}
$$

Expanding the covariant derivative,

$$
\overline\psi i\gamma^\mu D_\mu\psi
=\overline\psi i\gamma^\mu\partial_\mu\psi
-qA_\mu\overline\psi\gamma^\mu\psi.
$$

Thus

$$
\mathcal L_\text{int}=-A_\mu j^\mu,
\qquad
\boxed{j^\mu=q\overline\psi\gamma^\mu\psi.}
$$

Unlike scalar QED, spinor QED has no minimal two-photon contact term in the Dirac Lagrangian. The reason is simple: the Dirac kinetic term is first order in derivatives, so it is first order in $D_\mu$. Scalar matter has a second-order kinetic term, so it produces both linear and quadratic powers of $A_\mu$.

That distinction matters in perturbation theory. Spinor QED has the familiar electron-photon vertex. Scalar QED has a scalar-scalar-photon vertex and a scalar-scalar-two-photon vertex. Both are part of the same local-gauge package.

## The matter current

The electromagnetic current is obtained by varying the matter action with respect to $A_\mu$:

$$
\delta\mathcal L_\text{matter}=-j^\mu\delta A_\mu.
$$

For scalar matter,

$$
\boxed{
j^\mu_\text{scalar}
=iq\left[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi\right].
}
$$

This is the gauge-covariant version of the free complex-scalar current. Notice that it contains $A_\mu$ through the covariant derivatives. Equivalently,

$$
j^\mu_\text{scalar}
=iq\left[\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right]
-2q^2A^\mu\Phi^\dagger\Phi.
$$

The source equation for the gauge field is then

$$
\boxed{\partial_\nu F^{\nu\mu}=j^\mu.}
$$

For spinor matter,

$$
\boxed{j^\mu_\text{spinor}=q\overline\psi\gamma^\mu\psi.}
$$

For several charged fields, the total source is the sum of the currents:

$$
\partial_\nu F^{\nu\mu}=\sum_a j_a^\mu.
$$

Taking the divergence of the Maxwell equation gives

$$
\partial_\mu j^\mu
=\partial_\mu\partial_\nu F^{\nu\mu}=0,
$$

because $F^{\nu\mu}$ is antisymmetric. Conversely, gauge invariance of the coupling $-A_\mu j^\mu$ requires current conservation for external sources. These two facts are the same consistency condition viewed from opposite sides.

## Field strength from commutators

The covariant derivative also knows about the electromagnetic field strength. Acting on a field of charge $q$,

$$
[D_\mu,D_\nu]\Phi
=iq(\partial_\mu A_\nu-\partial_\nu A_\mu)\Phi.
$$

Therefore

$$
\boxed{[D_\mu,D_\nu]\Phi=iqF_{\mu\nu}\Phi.}
$$

This is the Abelian version of the curvature formula. The gauge potential defines parallel comparison of charged phases; the field strength measures the failure of that comparison to be path independent.

If $F_{\mu\nu}=0$ on a simply connected patch, then locally $A_\mu=\partial_\mu\alpha$ and the connection is pure gauge. If $F_{\mu\nu}\neq0$, no gauge transformation can remove $A_\mu$ everywhere on the patch.

## Minimal coupling is not only a mnemonic

In elementary courses, minimal coupling is often introduced as the replacement

$$
p_\mu\to p_\mu-qA_\mu.
$$

That mnemonic is useful, but the field-theory statement is sharper:

$$
\boxed{\partial_\mu\quad\text{is replaced by}\quad D_\mu=\partial_\mu+iqA_\mu\quad\text{on a field of charge }q.}
$$

The reason is not merely analogy with classical mechanics. The reason is local gauge covariance.

This also clarifies what minimal coupling does **not** say. Gauge invariance allows additional local interactions, for example

$$
F_{\mu\nu}F^{\mu\nu}\Phi^\dagger\Phi,
\qquad
\overline\psi\sigma^{\mu\nu}\psi F_{\mu\nu},
$$

with appropriate powers of a heavy scale if one is doing effective field theory. These are gauge invariant, but they are not part of the minimal derivative replacement. Minimal coupling gives the lowest-derivative, representation-theoretic coupling to the gauge potential.

## Charge assignments and allowed terms

A local interaction term must have total gauge charge zero.

For example, suppose

$$
\phi\mapsto e^{-iq_\phi\alpha}\phi,
\qquad
\psi\mapsto e^{-iq_\psi\alpha}\psi,
\qquad
\chi\mapsto e^{-iq_\chi\alpha}\chi.
$$

The Yukawa-like term

$$
y\phi\,\overline\psi\chi
$$

transforms as

$$
y\phi\,\overline\psi\chi
\mapsto
\exp[-i(q_\phi+q_\chi-q_\psi)\alpha]
\,y\phi\,\overline\psi\chi.
$$

So it is gauge invariant only if

$$
\boxed{q_\phi+q_\chi-q_\psi=0.}
$$

This simple bookkeeping becomes powerful in the Standard Model. Gauge charges decide which mass terms and Yukawa couplings are allowed. A term can be perfectly Lorentz invariant and still be forbidden because its gauge charge does not vanish.

## Gauge-covariant is not gauge-invariant

A charged field is gauge-covariant:

$$
\Phi\mapsto e^{-iq\alpha}\Phi.
$$

It is not gauge-invariant. Local gauge-invariant operators include

$$
\Phi^\dagger\Phi,
\qquad
(D_\mu\Phi)^\dagger D^\mu\Phi,
\qquad
\overline\psi\psi,
\qquad
F_{\mu\nu}F^{\mu\nu}.
$$

This matters conceptually. In a gauge theory with dynamical photons, a bare local charged field is not itself a physical gauge-invariant observable. In perturbation theory one often works with gauge-fixed charged fields, and that is perfectly useful, but physical charged states carry electromagnetic fields with them. This subtlety reappears in infrared physics, Wilson lines, dressed operators, and the construction of asymptotic states.

A bilocal gauge-invariant object can be made by inserting a Wilson line between charged fields. Schematically,

$$
\Phi^\dagger(x)
\exp\left[-iq\int_y^x A_\mu dz^\mu\right]
\Phi(y)
$$

is invariant under small Abelian gauge transformations, provided the path and endpoint conventions are fixed. The Wilson line is the finite version of the covariant derivative's local comparison rule.

## Operator and path-integral faces

In the Hamiltonian formalism, charged matter appears as the source in Gauss's law:

$$
\nabla\cdot\mathbf E=\rho.
$$

The charge density $\rho=j^0$ is not an optional addition; it is part of the constraint that defines physical states. A charged excitation changes the electric flux required by Gauss's law.

In the path integral, charged matter enters through the gauge-invariant action

$$
S[A,\Phi]=\int d^4x\left[-\frac14F_{\mu\nu}F^{\mu\nu}+(D_\mu\Phi)^\dagger D^\mu\Phi-V(\Phi^\dagger\Phi)\right],
$$

or through the spinor action

$$
S[A,\psi]=\int d^4x\left[-\frac14F_{\mu\nu}F^{\mu\nu}+\overline\psi(i\gamma^\mu D_\mu-m)\psi\right].
$$

Changing variables by a local gauge transformation gives Ward identities. In perturbation theory, these identities relate vertices, propagators, and counterterms. In QED they are responsible for relations such as equality of charge and wavefunction renormalization factors in suitable notation. That is the quantum afterlife of the elementary cancellation in $D_\mu\Phi$.

## Non-Abelian preview

The Abelian story generalizes. If a matter field belongs to a representation $R$ of a non-Abelian group $G$, then the covariant derivative has the schematic form

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a,
$$

where $T_R^a$ are the generators in representation $R$. A field in the trivial representation has $T_R^a=0$ and is neutral under that gauge group.

The slogan is:

$$
\boxed{\text{matter fields couple to gauge bosons according to their gauge representation.}}
$$

For electromagnetism, the representation is labeled by electric charge. For Yang–Mills theory, it may be the fundamental, adjoint, or another representation. The next pages explain why gauge fixing is necessary and how the non-Abelian version differs from Maxwell theory.

## Common pitfalls

**Mistaking gauge charge for an ordinary label.** Charge is a representation label of the gauge group. Fields with different charges transform differently, and the covariant derivative must know the charge.

**Forgetting the scalar seagull term.** In scalar QED, replacing $\partial$ by $D$ generates both one-photon and two-photon scalar couplings. Dropping the two-photon term breaks gauge invariance.

**Calling every gauge-covariant field observable.** Charged fields are useful variables, especially after gauge fixing, but local gauge-invariant observables must be invariant along gauge orbits.

**Mixing sign conventions.** If you change $D_\mu=\partial_\mu+iqA_\mu$ to $D_\mu=\partial_\mu-iqA_\mu$, the transformations of $A_\mu$ and the sign of $q$ must change consistently.

**Thinking minimal coupling is the most general coupling.** It is the lowest-derivative covariant derivative coupling. Effective field theory allows additional gauge-invariant operators.

## Relation to other topics

- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explains why local gauge transformations are redundancies rather than ordinary physical symmetries.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) gives the Abelian gauge-field action and equations before matter is made dynamical.
- [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/) explains the global-charge side of the same current.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) derives the quantum identities that follow from current conservation and gauge symmetry.
- [Scalar QED](/foundations/foundational-models/scalar-qed/) will use this machinery as a full model page.
- [QED Preview](/foundations/foundational-models/qed-preview/) will connect spinor QED to scattering, renormalization, and precision tests.

## Exercises

### Exercise 1: Covariance of the Abelian derivative

Using

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi'=e^{-iq\alpha}\Phi,
\qquad
A_\mu'=A_\mu+\partial_\mu\alpha,
$$

show that $D_\mu'\Phi'=e^{-iq\alpha}D_\mu\Phi$.

<details>
<summary><strong>Solution</strong></summary>

Compute directly:

$$
\begin{aligned}
D_\mu'\Phi'
&=(\partial_\mu+iqA_\mu+iq\partial_\mu\alpha)e^{-iq\alpha}\Phi \\
&=e^{-iq\alpha}\partial_\mu\Phi
-iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi
+iqA_\mu e^{-iq\alpha}\Phi
+iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi.
\end{aligned}
$$

The two terms proportional to $\partial_\mu\alpha$ cancel, leaving

$$
D_\mu'\Phi'=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\Phi
=e^{-iq\alpha}D_\mu\Phi.
$$

</details>

### Exercise 2: Expand the scalar QED kinetic term

Show that

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
=\partial_\mu\Phi^\dagger\partial^\mu\Phi
+iqA_\mu\left[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi\right]
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
$$

Identify the term linear in $A_\mu$ and the term quadratic in $A_\mu$.

<details>
<summary><strong>Solution</strong></summary>

With qft.org conventions,

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi,
\qquad
(D_\mu\Phi)^\dagger=(\partial_\mu-iqA_\mu)\Phi^\dagger.
$$

Multiplying,

$$
\begin{aligned}
(D_\mu\Phi)^\dagger D^\mu\Phi
&=(\partial_\mu\Phi^\dagger-iqA_\mu\Phi^\dagger)
(\partial^\mu\Phi+iqA^\mu\Phi) \\
&=\partial_\mu\Phi^\dagger\partial^\mu\Phi
+iqA_\mu(\partial^\mu\Phi^\dagger)\Phi
-iqA_\mu\Phi^\dagger\partial^\mu\Phi
+q^2A_\mu A^\mu\Phi^\dagger\Phi.
\end{aligned}
$$

The linear term is

$$
iqA_\mu\left[(\partial^\mu\Phi^\dagger)\Phi-\Phi^\dagger\partial^\mu\Phi\right]
=-A_\mu j^\mu_\text{free},
$$

where

$$
j^\mu_\text{free}=iq\left[\Phi^\dagger\partial^\mu\Phi-(\partial^\mu\Phi^\dagger)\Phi\right].
$$

The quadratic term

$$
q^2A_\mu A^\mu\Phi^\dagger\Phi
$$

is the two-photon scalar contact term.

</details>

### Exercise 3: Current from varying the scalar action

For

$$
\mathcal L_\text{matter}=(D_\mu\Phi)^\dagger D^\mu\Phi-V(\Phi^\dagger\Phi),
$$

show that varying with respect to $A_\mu$ gives

$$
\delta\mathcal L_\text{matter}=-j^\mu\delta A_\mu,
$$

with

$$
j^\mu=iq\left[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi\right].
$$

<details>
<summary><strong>Solution</strong></summary>

The variations are

$$
\delta(D_\mu\Phi)=iq\delta A_\mu\Phi,
\qquad
\delta(D_\mu\Phi)^\dagger=-iq\delta A_\mu\Phi^\dagger.
$$

Therefore

$$
\begin{aligned}
\delta\mathcal L_\text{matter}
&=\delta(D_\mu\Phi)^\dagger D^\mu\Phi
+(D_\mu\Phi)^\dagger\delta(D^\mu\Phi) \\
&=-iq\delta A_\mu\Phi^\dagger D^\mu\Phi
+iq(D^\mu\Phi)^\dagger\delta A_\mu\Phi \\
&=-iq\left[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi\right]\delta A_\mu.
\end{aligned}
$$

Thus

$$
\delta\mathcal L_\text{matter}=-j^\mu\delta A_\mu,
$$

where

$$
j^\mu=iq\left[\Phi^\dagger D^\mu\Phi-(D^\mu\Phi)^\dagger\Phi\right].
$$

</details>

### Exercise 4: Curvature from covariant derivatives

Show that, on a field of charge $q$,

$$
[D_\mu,D_\nu]\Phi=iqF_{\mu\nu}\Phi.
$$

<details>
<summary><strong>Solution</strong></summary>

Use $D_\mu=\partial_\mu+iqA_\mu$. Then

$$
\begin{aligned}
[D_\mu,D_\nu]\Phi
&=(\partial_\mu+iqA_\mu)(\partial_\nu+iqA_\nu)\Phi
-(\mu\leftrightarrow\nu).
\end{aligned}
$$

The second derivatives cancel because $\partial_\mu\partial_\nu=\partial_\nu\partial_\mu$. The terms quadratic in $A$ cancel because the Abelian fields commute as ordinary functions. The remaining terms are

$$
iq(\partial_\mu A_\nu-\partial_\nu A_\mu)\Phi
=iqF_{\mu\nu}\Phi.
$$

</details>

### Exercise 5: Gauge-invariant monomials

Let $\phi_i$ have Abelian charges $q_i$, so

$$
\phi_i\mapsto e^{-iq_i\alpha}\phi_i.
$$

For a monomial

$$
\mathcal O=\prod_i \phi_i^{n_i}\prod_j (\phi_j^\dagger)^{m_j},
$$

find the condition for $\mathcal O$ to be gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

The fields transform as

$$
\phi_i^{n_i}\mapsto e^{-in_iq_i\alpha}\phi_i^{n_i},
\qquad
(\phi_j^\dagger)^{m_j}\mapsto e^{+im_jq_j\alpha}(\phi_j^\dagger)^{m_j}.
$$

Thus

$$
\mathcal O\mapsto
\exp\left[-i\alpha\left(\sum_i n_iq_i-\sum_jm_jq_j\right)\right]\mathcal O.
$$

The operator is gauge invariant if and only if

$$
\boxed{\sum_i n_iq_i-\sum_jm_jq_j=0.}
$$

</details>

### Exercise 6: Spinor QED current

For

$$
\mathcal L_\text{matter}=\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu,
$$

show that the interaction has the form $-A_\mu j^\mu$, and identify $j^\mu$.

<details>
<summary><strong>Solution</strong></summary>

Expand the covariant derivative:

$$
\overline\psi i\gamma^\mu D_\mu\psi
=\overline\psi i\gamma^\mu\partial_\mu\psi
+\overline\psi i\gamma^\mu(iqA_\mu)\psi.
$$

Since $i(iq)=-q$,

$$
\overline\psi i\gamma^\mu D_\mu\psi
=\overline\psi i\gamma^\mu\partial_\mu\psi
-qA_\mu\overline\psi\gamma^\mu\psi.
$$

Therefore

$$
\mathcal L_\text{int}=-A_\mu j^\mu,
\qquad
\boxed{j^\mu=q\overline\psi\gamma^\mu\psi.}
$$

</details>

## Sources and further reading

- H. Weyl, “Elektron und Gravitation,” *Zeitschrift für Physik* **56** (1929), for the local phase-gauge viewpoint.
- J. Schwinger, “Gauge Invariance and Mass,” *Physical Review* **125** (1962), for a classic gauge-theory perspective on charge and current.
- M. Srednicki, *Quantum Field Theory*, §§58, 61, and 67–68, for spinor electrodynamics, scalar electrodynamics, and QED Ward identities.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 27 and 30, for gauge invariance, minimal coupling, and scalar/spinor electrodynamics.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 8, for electrodynamics, conserved currents, and covariant-gauge quantization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §15.1, for the non-Abelian generalization of gauge-covariant derivatives and matter representations.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. III.4 and IV.5, for an intuitive account of gauge invariance and non-Abelian covariant derivatives.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 9 and 15, for QED, scalar QED, Ward identities, and gauge-theory perturbation theory.

## Version history

- **2026-05-23:** Initial qft.org page on charged matter, covariant derivatives, scalar QED, spinor QED, matter currents, charge assignments, and the non-Abelian preview.
