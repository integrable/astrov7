---
title: "QED Lagrangian"
description: "Collects the gauge-invariant and gauge-fixed forms of the QED Lagrangian, including photon dynamics, charged matter, source currents, equations of motion, and counterterm structure."
sidebar:
  label: "QED Lagrangian"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§57–68; Schwartz Chs. 8–21; Coleman lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, and QED renormalization; Weinberg Vol. I QED chapters."
topics:
  - QED Lagrangian
  - Abelian gauge theory
  - gauge fixing
  - electromagnetic current
  - counterterms
canonicalTopics:
  - qed-lagrangian
  - quantum-electrodynamics
  - gauge-fixed-action
  - electromagnetic-current
researchStatus:
  established:
    - "The local gauge-invariant and covariantly gauge-fixed QED Lagrangians are standard textbook structures, with convention-dependent signs fixed by the choice of covariant derivative."
  active:
    - "The interpretation of charged asymptotic states, infrared-safe observables, and high-order precision expansions remains an active interface between formal QFT and phenomenology."
---

## Summary

The QED Lagrangian is the local field-theory expression that combines Maxwell dynamics with charged matter. For one Dirac fermion of charge $q$, the gauge-invariant Lagrangian is

$$
\mathcal L_{\mathrm{QED}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

Equivalently,

$$
\mathcal L_{\mathrm{QED}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-j^\mu A_\mu,
$$

with electromagnetic source current

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

For the electron, $q=-e$ with $e>0$, so

$$
\mathcal L_{e\gamma}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi_e(i\gamma^\mu\partial_\mu-m_e)\psi_e
+eA_\mu\bar\psi_e\gamma^\mu\psi_e.
$$

This page collects the gauge-invariant form, source-current form, equations of motion, allowed matter terms, gauge-fixing extension, and counterterm structure. Later pages derive the photon propagator, Feynman rules, Ward–Takahashi identity, vacuum polarization, and running electric charge from this starting point.

<figure class="doc-figure" style="--figure-width: 47rem;">

![Architecture of the QED Lagrangian and its gauge-fixed perturbative form.](/figures/gauge-theories-standard-model/qed-lagrangian-architecture.svg)

<figcaption>

The gauge-invariant QED Lagrangian contains photon dynamics and charged matter. Perturbative calculations add gauge fixing to invert the photon kinetic operator; Ward–Takahashi identities then ensure that physical quantities do not depend on the gauge parameter $\xi$.

</figcaption>
</figure>

## Prerequisites

You should know [Maxwell Theory as Gauge Theory](/gauge-theories-standard-model/qed/maxwell-theory-as-gauge-theory/), [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/), and [Spinor QED](/gauge-theories-standard-model/qed/spinor-qed/). You should also know the Abelian convention in [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/):

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\lambda}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\lambda.
$$

This page assumes familiarity with the free Dirac and complex scalar Lagrangians, but it recalls the necessary formulas. Gauge fixing is introduced here only enough to state the gauge-fixed Lagrangian; the next pages derive the photon propagator and vertex rules carefully.

## Core idea

There are two useful ways to read the QED Lagrangian.

The first is the **covariant-derivative form**:

$$
\partial_\mu\quad\longrightarrow\quad D_\mu=\partial_\mu+iqA_\mu.
$$

This form makes gauge invariance nearly automatic. Charged matter terms are obtained by replacing ordinary derivatives with covariant derivatives and adding the Maxwell kinetic term.

The second is the **source-current form**:

$$
\mathcal L_{\mathrm{matter}}(D)
=
\mathcal L_{\mathrm{matter}}(\partial)-j^\mu A_\mu+\cdots,
$$

where $j^\mu$ is the electromagnetic current. The dots are absent for minimally coupled spinor QED, but present for scalar QED because scalar kinetic terms generate an $A_\mu A^\mu\phi^\dagger\phi$ seagull term.

The covariant-derivative form is the safest way to preserve gauge invariance. The source-current form is the quickest way to identify vertices, equations of motion, and the physical meaning of $A_\mu$ as the field coupled to electric charge.

## Setup and conventions

We work in four-dimensional Minkowski spacetime with mostly-minus metric. The Abelian field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

The pure Maxwell Lagrangian is

$$
\mathcal L_{\mathrm{Maxwell}}
=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

A field of charge $q$ transforms as

$$
\Phi\mapsto e^{-iq\lambda}\Phi,
$$

where $\Phi$ may be a scalar or spinor field. Its covariant derivative is

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi.
$$

Often we write

$$
q=eQ,
$$

where $e>0$ and $Q$ is dimensionless. In that language,

$$
D_\mu=\partial_\mu+ieQA_\mu.
$$

The electron has $Q=-1$, so the electron covariant derivative is

$$
D_\mu\psi_e=(\partial_\mu-ieA_\mu)\psi_e.
$$

## Minimal spinor QED

The minimal QED Lagrangian for a single Dirac fermion of charge $q$ is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Expanding the covariant derivative gives

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi.
$$

Define

$$
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

Then

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-j^\mu A_\mu.
$$

This formula is the most compact way to remember the source convention:

$$
\text{QED couples } A_\mu \text{ to the electromagnetic current by } -j^\mu A_\mu.
$$

For the electron, $j_e^\mu=-e\bar\psi_e\gamma^\mu\psi_e$, and hence

$$
-j_e^\mu A_\mu=+eA_\mu\bar\psi_e\gamma^\mu\psi_e.
$$

## Multiple charged fermions

For several Dirac fermions $\psi_f$ with charges $q_f=eQ_f$, the Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\sum_f\bar\psi_f(i\gamma^\mu D_\mu^{(f)}-m_f)\psi_f,
$$

where

$$
D_\mu^{(f)}=\partial_\mu+iq_fA_\mu.
$$

The total current is

$$
j^\mu=\sum_f q_f\bar\psi_f\gamma^\mu\psi_f.
$$

The interaction is

$$
\mathcal L_{\mathrm{int}}=-A_\mu\sum_f q_f\bar\psi_f\gamma^\mu\psi_f.
$$

In QED as an isolated theory, the $q_f$ are allowed charge labels. In the Standard Model, the electric charges of quarks and leptons come from electroweak quantum numbers after symmetry breaking, with

$$
Q=T^3+Y.
$$

Thus QED is the low-energy Abelian gauge theory of electric charge, while the origin of the charge assignments is explained later by electroweak theory.

## Including charged scalars

If the theory also contains a complex scalar $\phi$ of charge $q_s$, the scalar part is

$$
\mathcal L_\phi
=(D_\mu\phi)^\dagger D^\mu\phi
-m^2\phi^\dagger\phi
-V(\phi^\dagger\phi),
$$

where

$$
D_\mu\phi=(\partial_\mu+iq_sA_\mu)\phi.
$$

Expanding gives

$$
(D_\mu\phi)^\dagger D^\mu\phi
=
\partial_\mu\phi^\dagger\partial^\mu\phi
-j_{0,s}^\mu A_\mu
+q_s^2A_\mu A^\mu\phi^\dagger\phi,
$$

where

$$
j_{0,s}^\mu
=iq_s\left(\phi^\dagger\partial^\mu\phi-(\partial^\mu\phi^\dagger)\phi\right).
$$

The full scalar source current obtained by varying the action with respect to $A_\mu$ is

$$
j_s^\mu
=iq_s\left(\phi^\dagger D^\mu\phi-(D^\mu\phi)^\dagger\phi\right).
$$

This includes the $A^\mu\phi^\dagger\phi$ contribution. That is why the scalar-QED Lagrangian produces both a one-photon scalar vertex and a two-photon seagull vertex.

A general Abelian gauge theory with spinor and scalar charged matter can be written schematically as

$$
\mathcal L
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\sum_f\bar\psi_f(i\gamma^\mu D_\mu^{(f)}-m_f)\psi_f
+\sum_s(D_\mu\phi_s)^\dagger D^\mu\phi_s
-V(\phi_s^\dagger\phi_s).
$$

Minimal QED usually means the special case with the photon and one or more charged Dirac fields, especially electrons.

## Equations of motion

For one Dirac fermion, varying the action with respect to $\bar\psi$ gives

$$
(i\gamma^\mu D_\mu-m)\psi=0.
$$

Varying with respect to $A_\mu$ gives

$$
\partial_\nu F^{\nu\mu}=j^\mu,
\qquad
j^\mu=q\bar\psi\gamma^\mu\psi.
$$

In components, this is the relativistic form of Maxwell's equations with electric charge and current as sources. Since $F^{\nu\mu}$ is antisymmetric,

$$
\partial_\mu\partial_\nu F^{\nu\mu}=0,
$$

so the Maxwell equation implies

$$
\partial_\mu j^\mu=0.
$$

The Dirac equation also implies current conservation, as shown on the Spinor QED page. Gauge invariance and the matter equations are therefore mutually consistent: the gauge field can couple only to a conserved source.

For scalar QED, the Maxwell equation has the same form,

$$
\partial_\nu F^{\nu\mu}=j_s^\mu,
$$

but the scalar current contains covariant derivatives:

$$
j_s^\mu=iq_s\left(\phi^\dagger D^\mu\phi-(D^\mu\phi)^\dagger\phi\right).
$$

The appearance of $D^\mu$ rather than $\partial^\mu$ is not pedantry; it is the equation-of-motion version of the scalar seagull interaction.

## Gauge fixing and the perturbative Lagrangian

The gauge-invariant Maxwell kinetic term has a zero mode: configurations differing by

$$
A_\mu\mapsto A_\mu+\partial_\mu\lambda
$$

represent the same physical gauge-field configuration. As a result, the photon kinetic operator cannot be inverted directly to obtain a propagator. Perturbation theory therefore adds a gauge-fixing term.

The standard covariant gauge-fixed Lagrangian is

$$
\mathcal L_\xi
=
\mathcal L_{\mathrm{QED}}
-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

The parameter $\xi$ labels the gauge choice. Important special cases are

$$
\xi=1 \quad \text{Feynman gauge},
\qquad
\xi\to 0 \quad \text{Landau gauge}.
$$

The gauge-fixed Lagrangian is not invariant under arbitrary local gauge transformations, because gauge fixing deliberately chooses one representative from each gauge orbit. The physical content is nevertheless unchanged: gauge-invariant observables and properly defined S-matrix elements do not depend on $\xi$.

For Abelian QED, the Faddeev–Popov determinant in a covariant gauge is independent of $A_\mu$. If one introduces ghost fields anyway, they are free and decouple from the photon and matter fields:

$$
\mathcal L_{\mathrm{ghost}}=\bar c(-\partial^2)c
$$

up to an overall sign convention for Grassmann scalar ghosts. In non-Abelian Yang–Mills theory, this statement fails dramatically: ghosts interact with gauge bosons and are essential for unitarity and renormalization in covariant gauges.

## The photon kinetic operator

It is useful to see why the gauge-fixing term is needed. The quadratic photon part of the gauge-invariant Lagrangian can be written, after integrating by parts, as

$$
\mathcal L_{A,2}
=\frac12A_\mu\left(\eta^{\mu\nu}\partial^2-\partial^\mu\partial^\nu\right)A_\nu.
$$

The operator

$$
\eta^{\mu\nu}\partial^2-\partial^\mu\partial^\nu
$$

annihilates pure-gauge modes $A_\nu=\partial_\nu\lambda$, so it has no inverse on the full vector-field space. Adding

$$
-\frac{1}{2\xi}(\partial\cdot A)^2
$$

changes the quadratic operator to

$$
\eta^{\mu\nu}\partial^2-\left(1-\frac1\xi\right)\partial^\mu\partial^\nu.
$$

This operator is invertible after an $i\epsilon$ prescription is included. The next page turns this into the covariant-gauge photon propagator.

## Feynman-rule preview

The gauge-fixed QED Lagrangian immediately suggests the basic perturbative ingredients.

For a Dirac fermion of charge $q$,

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon},
$$

and the photon–fermion vertex is

$$
-iq\gamma^\mu.
$$

The covariant-gauge photon propagator is derived on the Photon Propagator page, but the result is

$$
D_{\mu\nu}(k)
=\frac{-i}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

For scalar QED, the Lagrangian gives a one-photon scalar vertex and a two-photon seagull vertex. These are collected on the QED Vertices page because the momentum routing and all-incoming conventions deserve a dedicated place.

## What terms are allowed?

The minimal QED Lagrangian is not just a pretty guess. It is the most general local, Lorentz-invariant, power-counting renormalizable Lagrangian for a photon and a vectorlike charged Dirac fermion, assuming parity is not explicitly violated and no additional light fields are included.

The allowed dimension-four or lower terms are:

| Term | Allowed? | Comment |
|---|---|---|
| $-\frac14F_{\mu\nu}F^{\mu\nu}$ | yes | Photon kinetic term. |
| $\bar\psi i\gamma^\mu D_\mu\psi$ | yes | Gauge-invariant Dirac kinetic term. |
| $m\bar\psi\psi$ | yes | Allowed for vectorlike QED. |
| $F_{\mu\nu}\widetilde F^{\mu\nu}$ | total derivative | Usually omitted in ordinary QED on topologically trivial backgrounds. |
| $A_\mu A^\mu$ | no | Photon mass term violates the local $U(1)$ gauge redundancy. |
| $A_\mu\bar\psi\gamma^\mu\psi$ with arbitrary coefficient | fixed | Its coefficient is fixed by the charge in $D_\mu$. |
| $(\bar\psi\psi)^2$ | nonrenormalizable in four dimensions | Dimension six; appears in EFT, not minimal QED. |
| $\bar\psi\sigma^{\mu\nu}\psi F_{\mu\nu}$ | nonrenormalizable in four dimensions | Magnetic dipole operator, dimension five. |

Here

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}
$$

with the sign of $\epsilon^{0123}$ fixed in the volume conventions. The term $F_{\mu\nu}\widetilde F^{\mu\nu}$ can matter in theories with boundaries, compact gauge fields, monopoles, or nontrivial topology, but it does not affect ordinary perturbative QED in flat spacetime.

## Counterterm form

Renormalized perturbation theory splits the Lagrangian into a renormalized part plus counterterms. For one Dirac fermion, a convenient schematic form is

$$
\mathcal L
=
\mathcal L_{\mathrm{ren}}+\mathcal L_{\mathrm{ct}},
$$

where

$$
\mathcal L_{\mathrm{ren}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
-qA_\mu\bar\psi\gamma^\mu\psi
-\frac{1}{2\xi}(\partial\cdot A)^2.
$$

The counterterms have the same local structures:

$$
\mathcal L_{\mathrm{ct}}
=
-\frac14\delta Z_3F_{\mu\nu}F^{\mu\nu}
+\delta Z_2\bar\psi i\gamma^\mu\partial_\mu\psi
-\delta m\bar\psi\psi
-\delta q\,A_\mu\bar\psi\gamma^\mu\psi
+\cdots.
$$

The dots include scheme-dependent ways of writing the same counterterms, gauge-fixing renormalization, and possible counterterms for additional fields. The Ward–Takahashi identity relates the fermion wavefunction and vertex counterterms. In common multiplicative notation this is often expressed as

$$
Z_1=Z_2,
$$

with the precise identification depending on how the bare and renormalized charges are parameterized. The important point for this page is structural: renormalization does not add arbitrary non-gauge-invariant operators to QED. The counterterms are constrained by gauge symmetry.

## Why the Lagrangian is not the observable

The QED Lagrangian is the starting point for calculations, not itself a directly measured object. Several changes leave the physics unchanged or only repackage it:

- adding a total derivative;
- choosing a different gauge-fixing parameter $\xi$;
- rescaling the gauge field and compensating by redefining the charge;
- performing local field redefinitions;
- choosing a different renormalization scheme;
- organizing perturbation theory with different counterterm conventions.

This is why one should not memorize the QED Lagrangian as a sacred incantation. The invariant content is the gauge redundancy, the matter representation and charge assignments, the local operator content, and the rule that physical observables must be independent of gauge-fixing choices.

That said, the Lagrangian is still extremely powerful. It gives equations of motion, canonical momenta, currents, propagators, vertices, Ward identities, and counterterms from one compact expression. A good Lagrangian is not the whole theory, but it is an unusually efficient table of contents.

## Common pitfalls

**Using the wrong sign for the electron coupling.** In this volume, the electron has $q=-e$ and $D_\mu=\partial_\mu-ieA_\mu$. Therefore the interaction term is $+eA_\mu\bar\psi_e\gamma^\mu\psi_e$ and the vertex is $+ie\gamma^\mu$.

**Forgetting that scalar QED has more than $-jA$.** The scalar kinetic term also contains $q^2A^2\phi^\dagger\phi$. The source-current form must be handled carefully for scalars because the full current contains $A_\mu$ through the covariant derivative.

**Calling gauge fixing a physical interaction.** The term $-(\partial\cdot A)^2/(2\xi)$ is added to make perturbation theory possible. It is not a new force, and physical quantities must not depend on $\xi$.

**Adding a photon mass by hand.** A term $\frac12m_A^2A_\mu A^\mu$ is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$. Massive vector theories and Higgs phases are real subjects, but they are not ordinary unbroken QED.

**Thinking Abelian ghosts always matter.** In covariantly gauge-fixed QED, Faddeev–Popov ghosts decouple because the determinant is field independent. This is not true in Yang–Mills theory.

**Mistaking charge conservation for a separate assumption.** Gauge consistency requires the source coupled to $A_\mu$ to be conserved. In the Lagrangian formulation, current conservation follows from the matter equations and the gauge symmetry.

## Relations to other pages

This page consolidates the ingredients introduced separately in Maxwell Theory as Gauge Theory, Scalar QED, and Spinor QED. The next two pages use the gauge-fixed Lagrangian to derive [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/) and the [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/).

The QED Vertices page will turn the interaction terms into a consistent set of momentum-space Feynman rules. The Ward–Takahashi Identity page will show how the gauge symmetry of the Lagrangian constrains Green functions and renormalization. Vacuum Polarization and Running Electric Charge will then show how charged matter modifies the photon two-point function and makes the effective electric charge scale dependent.

The Yang–Mills chapter repeats this story with one crucial change: the gauge field itself carries non-Abelian charge. That single change produces gauge-boson self-interactions, interacting ghosts, asymptotic freedom, confinement, and most of the drama of the strong interactions.

## Research status

The QED Lagrangian and its gauge-fixed perturbative forms are settled foundations of quantum field theory. What remains active is not the local expression itself but its high-precision use and its infrared interpretation: inclusive observables, dressed charged states, asymptotic symmetries, and multi-loop calculations are still research-level topics.

As an effective field theory, QED also admits higher-dimension operators suppressed by heavy scales. These encode magnetic moments, polarizabilities, four-fermion interactions, and effects of particles that have been integrated out. The minimal Lagrangian on this page is therefore the leading part of a broader EFT expansion.

## Exercises

### Exercise 1: Derive Maxwell's equation from the source form

Starting from

$$
\mathcal L[A]
=-\frac14F_{\mu\nu}F^{\mu\nu}-j^\mu A_\mu,
$$

where $j^\mu$ is treated as independent of $A_\mu$, derive

$$
\partial_\nu F^{\nu\mu}=j^\mu.
$$

<details><summary><strong>Solution</strong></summary>

The variation of the Maxwell term is

$$
\delta\left(-\frac14F_{\mu\nu}F^{\mu\nu}\right)
=-\frac12F^{\mu\nu}\delta F_{\mu\nu}.
$$

Since

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu,
$$

antisymmetry gives

$$
-\frac12F^{\mu\nu}\delta F_{\mu\nu}
=-F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

Integrating by parts,

$$
\delta S=\int d^4x\,(\partial_\mu F^{\mu\nu}-j^\nu)\delta A_\nu.
$$

The Euler–Lagrange equation is therefore

$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$

Relabeling dummy indices gives the advertised form.

</details>

### Exercise 2: Why a photon mass is forbidden in QED

Show that

$$
\frac12m_A^2A_\mu A^\mu
$$

is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$ unless $m_A=0$ or the transformation is restricted.

<details><summary><strong>Solution</strong></summary>

Under the gauge transformation,

$$
A_\mu A^\mu
\mapsto
(A_\mu+\partial_\mu\lambda)(A^\mu+\partial^\mu\lambda).
$$

Thus

$$
\delta(A_\mu A^\mu)
=2A^\mu\partial_\mu\lambda+(\partial_\mu\lambda)(\partial^\mu\lambda).
$$

For arbitrary local $\lambda(x)$ this is not a total derivative and does not vanish. Therefore a Proca mass term is incompatible with the unbroken local $U(1)$ gauge redundancy of QED. A photon can acquire an effective mass in a medium or in a Higgs phase, but that is different physics.

</details>

### Exercise 3: Decoupling of Abelian ghosts

In Lorenz gauge, take the gauge-fixing function to be

$$
G[A]=\partial_\mu A^\mu.
$$

Under $A_\mu\mapsto A_\mu+\partial_\mu\lambda$, show that the Faddeev–Popov operator is independent of $A_\mu$.

<details><summary><strong>Solution</strong></summary>

The transformed gauge-fixing function is

$$
G[A^\lambda]=\partial_\mu(A^\mu+\partial^\mu\lambda)
=\partial_\mu A^\mu+\partial^2\lambda.
$$

Therefore

$$
\frac{\delta G[A^\lambda](x)}{\delta\lambda(y)}
=\partial_x^2\delta^{(4)}(x-y).
$$

This operator contains no $A_\mu$. The determinant can be represented by ghost fields, but the ghosts have only a free quadratic action and no coupling to photons or charged matter. In non-Abelian gauge theory the corresponding operator contains the covariant derivative and depends on the gauge field.

</details>

### Exercise 4: Dimension counting

Using $[\mathcal L]=4$ in four dimensions, show that $[A_\mu]=1$, $[\psi]=3/2$, and $[q]=0$.

<details><summary><strong>Solution</strong></summary>

From the Maxwell term,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

so $[F]=1+[A]$. The term $F_{\mu\nu}F^{\mu\nu}$ has dimension four, hence

$$
2(1+[A])=4,
$$

which gives $[A]=1$.

From the Dirac kinetic term,

$$
\bar\psi i\gamma^\mu\partial_\mu\psi,
$$

we get

$$
2[\psi]+1=4,
$$

so $[\psi]=3/2$.

The interaction $qA_\mu\bar\psi\gamma^\mu\psi$ has dimension

$$
[q]+1+\frac32+\frac32=[q]+4.
$$

Since the Lagrangian has dimension four, $[q]=0$. Electric charge is dimensionless in four-dimensional QED.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§57–68, for photon path integrals, spinor and scalar electrodynamics, loop corrections, beta functions, and Ward identities.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8–21, for QED Lagrangians, scalar and spinor QED, path integrals, Ward–Takahashi identities, vacuum polarization, mass renormalization, counterterms, and infrared divergences.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, QED renormalization, and famous QED results.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic treatment of QED, renormalization, gauge invariance, and infrared structure.
- Zee, *Quantum Field Theory in a Nutshell*, for a compact and physically motivated perspective on gauge invariance and QED.

## Version history

- **2026-06-17:** Initial polished draft of the QED Lagrangian page.
