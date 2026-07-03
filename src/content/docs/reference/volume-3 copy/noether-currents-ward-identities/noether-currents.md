---
title: "Noether Currents"
description: "Derives Noether currents from continuous symmetries, explains their conservation law, and fixes the charge-generating convention used in Ward identities."
sidebar:
  label: "Noether Currents"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman lectures on symmetries and conservation laws; Srednicki §22; Weinberg Vol. I on symmetry generators; Schwartz chapters on Noether's theorem and Ward identities."
topics:
  - Noether currents
  - continuous symmetry
  - conserved charges
  - local variation
  - Ward identities
canonicalTopics:
  - noether-current
  - continuous-symmetry-current
  - conserved-current
  - current-conservation
researchStatus:
  established:
    - "For an exact nonanomalous continuous symmetry, the classical Noether construction gives a locally conserved current on the equations of motion, up to standard improvement and equation-of-motion ambiguities."
  active:
    - "In quantum field theory, the sharp object is often a renormalized current operator or a background-field response; anomalies, boundaries, defects, and generalized symmetries refine the naive classical current story."
---

## Summary

A continuous symmetry has an infinitesimal parameter. Noether's construction asks a wonderfully diagnostic question: what happens if that parameter is allowed to depend on spacetime?

For fields $\Phi^I$ with infinitesimal symmetry variation $\delta_a\Phi^I$, the variation of a local Lagrangian can be written as

$$
\delta\mathcal L
=\mathcal E_I\delta\Phi^I+\partial_\mu\theta^\mu(\delta\Phi),
$$

where $\mathcal E_I=0$ are the Euler–Lagrange equations and $\theta^\mu$ is the boundary term produced by varying the fields. If the transformation is a symmetry, the Lagrangian changes at most by a total derivative,

$$
\delta_a\mathcal L=\partial_\mu K_a^\mu.
$$

The Noether current in the convention of this volume is

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu.
$$

It obeys

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I,
$$

so it is conserved on the classical equations of motion:

$$
\partial_\mu j_a^\mu=0.
$$

In quantum field theory this equation is only the first sentence. The current becomes an operator; products of operators require renormalization; Ward identities contain contact terms; and a classically conserved current can fail quantum mechanically through an anomaly. Still, Noether currents are the doorway through which continuous symmetry enters local QFT.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A schematic map showing how a constant continuous symmetry is localized to a spacetime-dependent parameter, producing the Noether current, current conservation, charges, and Ward identities.](/figures/symmetry-anomalies-topology/noether-current-localization.svg)

<figcaption>

Noether's diagnostic move is to localize the symmetry parameter. The coefficient of $\partial_\mu\alpha^a(x)$ is the current $j_a^\mu$. On shell, $\partial_\mu j_a^\mu=0$; after quantization, the same current produces charges and Ward identities, with contact terms at insertions.

</figcaption>
</figure>

## Prerequisites

You should know the [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the charge convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O],
$$

and the Ordinary Global Symmetries chapter through [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/).

You should be comfortable with classical field variations, Euler–Lagrange equations, integration by parts, and the idea that a current integrated over a time slice gives a charge. Ward identities, anomalies, and background fields are previewed here but developed later.

## Core idea

The core idea is that continuous symmetry can be tested locally.

Suppose an action $S[\Phi]$ is invariant under a constant infinitesimal transformation

$$
\delta\Phi^I=\alpha^a\delta_a\Phi^I,
\qquad
\partial_\mu\alpha^a=0.
$$

Now deliberately break the rule and let $\alpha^a$ depend on $x$. The transformation is no longer a symmetry, and the action changes by terms proportional to derivatives of the parameter:

$$
\delta_{\alpha(x)}S
=\int d^dx\,(\partial_\mu\alpha^a)j_a^\mu
+\text{equation-of-motion terms}
+\text{boundary terms}.
$$

That coefficient $j_a^\mu$ is the Noether current. Integrating by parts gives

$$
\delta_{\alpha(x)}S
=-\int d^dx\,\alpha^a\partial_\mu j_a^\mu
+\text{equation-of-motion terms}
+\text{boundary terms}.
$$

Since the original transformation with constant $\alpha^a$ was a symmetry, the nonzero response to local $\alpha^a(x)$ measures how symmetry is transported through spacetime. Conservation says that, on shell, symmetry charge cannot disappear in the bulk.

The slogan is

$$
\text{localize the symmetry parameter}
\quad\Longrightarrow\quad
\text{read off the current}.
$$

:::note[Convention-sensitive source note]
Some books define the current with the opposite sign, because they write the local variation as $-\int(\partial_\mu\alpha)j^\mu$ or use the inverse field transformation in the path integral. This page uses the convention fixed in this volume:

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu,
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

With this choice, integrating the Ward identity across a time slice reproduces the charge action on operator insertions.
:::

## Setup and conventions

Let the action be local:

$$
S[\Phi]=\int d^dx\,\mathcal L(\Phi,\partial\Phi),
$$

or, more generally, a local functional with finitely many derivatives. A general variation has the form

$$
\delta S
=\int d^dx\,\mathcal E_I\delta\Phi^I
+\int d^dx\,\partial_\mu\theta^\mu(\delta\Phi).
$$

For a first-derivative Lagrangian,

$$
\theta^\mu(\delta\Phi)
=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\delta\Phi^I.
$$

The Euler–Lagrange expression is

$$
\mathcal E_I
=\frac{\partial\mathcal L}{\partial\Phi^I}
-\partial_\mu
\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}.
$$

A continuous transformation labelled by $a$ is a symmetry when

$$
\delta_a\mathcal L=\partial_\mu K_a^\mu
$$

for some local expression $K_a^\mu$. The special case $K_a^\mu=0$ is strict invariance of the Lagrangian density. Allowing a total derivative is essential: translations, Lorentz transformations, Wess–Zumino terms, and topological terms often produce total derivatives rather than literal zero.

We work mostly in Lorentzian signature with mostly-minus metric. Repeated field labels $I$ are summed or integrated in the usual DeWitt sense. Unless otherwise stated, boundary terms at spatial infinity are assumed to vanish. Pages on boundaries, defects, and large gauge transformations will relax that assumption.

## The variational identity

Start from the identity

$$
\delta_a\mathcal L
=\mathcal E_I\delta_a\Phi^I
+\partial_\mu\theta^\mu(\delta_a\Phi).
$$

If the transformation is a symmetry,

$$
\delta_a\mathcal L=\partial_\mu K_a^\mu.
$$

Subtracting gives

$$
0
=\mathcal E_I\delta_a\Phi^I
+\partial_\mu
\bigl(\theta^\mu(\delta_a\Phi)-K_a^\mu\bigr).
$$

This identifies

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu
$$

and hence

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I.
$$

On solutions of the classical field equations, $\mathcal E_I=0$, so

$$
\partial_\mu j_a^\mu=0.
$$

This derivation is intentionally local. It does not require expanding fields in modes, choosing a Hilbert space, or quantizing the theory. Those steps are needed to define the charge operator and its action on states, but the current itself is already visible in the classical variational calculus.

### Why the equations of motion appear

The conservation law is not usually an identity off shell. It is a consequence of both symmetry and dynamics. The current satisfies

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I,
$$

so current conservation holds when the equations of motion hold. This matters in the path integral because fields inside the integral are not restricted to classical solutions. The off-shell version is exactly what becomes a Schwinger–Dyson or Ward identity.

A useful way to say this is:

$$
\text{symmetry of the action}
+
\text{field equations}
=
\text{conserved current}.
$$

A conserved current is therefore not just a kinematic decoration. It is a local bridge between symmetry and time evolution.

## Localizing the parameter

The most efficient way to remember the current is to promote the constant parameter to a function. Write

$$
\delta_{\alpha(x)}\Phi^I(x)
=\alpha^a(x)\delta_a\Phi^I(x).
$$

For a transformation with no derivatives of the parameter in $\delta_a\Phi^I$, the local variation of the Lagrangian becomes

$$
\delta_{\alpha(x)}\mathcal L
=\partial_\mu(\alpha^aK_a^\mu)
+(\partial_\mu\alpha^a)j_a^\mu.
$$

After dropping the total derivative,

$$
\delta_{\alpha(x)}S
=\int d^dx\,(\partial_\mu\alpha^a)j_a^\mu.
$$

Equivalently, after integrating by parts,

$$
\delta_{\alpha(x)}S
=-\int d^dx\,\alpha^a\partial_\mu j_a^\mu,
$$

again up to boundary terms and equation-of-motion terms depending on how the local variation is organized.

This formula is the seed of the path-integral Ward identity. In a change of variables, the variation of the action supplies the current divergence, while the variation of inserted operators supplies contact terms.

:::caution[Do not confuse localizing a global symmetry with gauging it]
Letting $\alpha$ depend on $x$ is a diagnostic trick. It does not mean the theory has a gauge redundancy. A global symmetry has a physical charge. A gauge redundancy identifies configurations and comes with constraints, gauge fixing, ghosts, or BRST structure. The Background Fields and Gauging chapter explains the upgrade from this diagnostic to genuine background gauge fields.
:::

## Canonical formula for first-derivative Lagrangians

For

$$
\mathcal L=\mathcal L(\Phi^I,\partial_\mu\Phi^I),
$$

the current is

$$
j_a^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\delta_a\Phi^I-K_a^\mu.
$$

This is often called the canonical Noether current. It is the formula most students first learn, and it is good enough for many model calculations.

But it is not the final word. The current can change when the Lagrangian is shifted by a total derivative, when the transformation law is modified by a term proportional to the equations of motion, when one adds an identically conserved improvement term, when composite operators are renormalized, when background-field counterterms are changed, or when boundaries and nontrivial topology make surface terms physical.

The next page is devoted to these ambiguities. The punchline is not that Noether's theorem is unreliable. The punchline is that a **current representative** is not the same thing as the underlying **symmetry**.

## Example: complex scalar phase symmetry

Consider a complex scalar field in $d$ dimensions,

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi
-V(\phi^\dagger\phi).
$$

It has a $U(1)$ symmetry. In the convention of this volume, take the infinitesimal variation to be

$$
\delta\phi=i\phi,
\qquad
\delta\phi^\dagger=-i\phi^\dagger.
$$

The Lagrangian is strictly invariant, so $K^\mu=0$. The canonical current is

$$
j^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\delta\phi
+\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}\delta\phi^\dagger.
$$

Since

$$
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}=\partial^\mu\phi^\dagger,
\qquad
\frac{\partial\mathcal L}{\partial(\partial_\mu\phi^\dagger)}=\partial^\mu\phi,
$$

we find

$$
j^\mu
=i(\partial^\mu\phi^\dagger)\phi
-i(\partial^\mu\phi)\phi^\dagger.
$$

Equivalently,

$$
j^\mu
=i\phi\partial^\mu\phi^\dagger
-i\phi^\dagger\partial^\mu\phi.
$$

Using the equations of motion,

$$
(\Box+m^2)\phi+\frac{\partial V}{\partial\phi^\dagger}=0,
\qquad
(\Box+m^2)\phi^\dagger+\frac{\partial V}{\partial\phi}=0,
$$

one checks that

$$
\partial_\mu j^\mu=0.
$$

The conserved charge is

$$
Q=\int d^{d-1}\mathbf x\, j^0(t,\mathbf x),
$$

assuming fields fall off fast enough at spatial infinity. With canonical equal-time commutators, this charge generates the phase rotation in the convention

$$
\delta\phi=i[Q,\phi]=i\phi.
$$

:::note[Background-field sign note]
If the same $U(1)$ is coupled to a background gauge field through $D_\mu=\partial_\mu-iA_\mu$, the linear source term may be written with the opposite sign depending on whether one defines $S[A]=S+\int A_\mu j^\mu$ or $S[A]=S-\int A_\mu j^\mu$. The Background Fields and Gauging chapter will treat this as a source convention. The current on this page is the charge-generating Noether current.
:::

## Example: spacetime translations and the stress tensor

Spacetime translations are continuous symmetries too. Under an infinitesimal active translation by a constant vector $a^\nu$, a scalar field varies as

$$
\delta_a\phi=a^\nu\partial_\nu\phi.
$$

The Lagrangian changes by a total derivative,

$$
\delta_a\mathcal L=a^\nu\partial_\nu\mathcal L
=\partial_\mu(a^\nu\delta^\mu{}_\nu\mathcal L).
$$

The corresponding Noether current has one index for the current and one for the translation generator. For a first-derivative scalar theory,

$$
T^\mu{}_\nu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi
-\delta^\mu{}_\nu\mathcal L.
$$

This is the canonical stress tensor. Its conservation law is

$$
\partial_\mu T^\mu{}_\nu=0.
$$

The conserved charges are energy and momentum,

$$
P_\nu=\int d^{d-1}\mathbf x\,T^0{}_\nu.
$$

Stress tensors have especially important improvement ambiguities: the canonical stress tensor need not be symmetric, gauge invariant, or traceless even when a better representative exists. Those issues are not a failure of Noether's theorem; they are a reminder that currents are defined up to local equivalence.

## From currents to charges

Given a conserved current, define the charge on a constant-time slice by

$$
Q_a(t)=\int_{\mathbb R^{d-1}}d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

Differentiate with respect to time:

$$
\frac{dQ_a}{dt}
=\int d^{d-1}\mathbf x\,\partial_0j_a^0
=-\int d^{d-1}\mathbf x\,\partial_i j_a^i.
$$

Using Gauss's theorem,

$$
\frac{dQ_a}{dt}
=-\int_{\partial \mathbb R^{d-1}}dS_i\,j_a^i.
$$

If the flux through spatial infinity vanishes, then

$$
\frac{dQ_a}{dt}=0.
$$

This is the global conservation law. It is weaker than the local conservation law: local conservation says charge cannot be created or destroyed at a point; global conservation says the total amount does not change when no charge flows through the boundary.

Boundary conditions are not a minor footnote. In systems with edges, defects, horizons, asymptotic symmetries, or topological sectors, the boundary term can be the physics.

## From currents to Ward identities

The same current has a second job. Insert it into correlation functions. Away from other operator insertions, current conservation suggests

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0.
$$

But this is incomplete. If

$$
\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n),
$$

then the current can collide with an insertion and produce a contact term. In the convention of this volume, the nonanomalous local Ward identity is

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{k=1}^n\delta^{(d)}(x-x_k)
\langle
\mathcal O_1(x_1)\cdots
\delta_a\mathcal O_k(x_k)
\cdots
\mathcal O_n(x_n)
\rangle.
$$

This formula says something very concrete. The current is conserved unless it crosses a charged operator. When it crosses, the operator transforms.

The next pages derive this identity in operator and path-integral language. The current page prepares the object; the Ward identity pages explain how it acts inside correlation functions.

## Differential-form viewpoint

In $d$ dimensions, the Hodge dual of an ordinary current is a $(d-1)$-form:

$$
J_a=\star j_a.
$$

Current conservation becomes

$$
dJ_a=0.
$$

The charge on a spatial slice $\Sigma_{d-1}$ is

$$
Q_a(\Sigma)=\int_{\Sigma_{d-1}}J_a.
$$

If $dJ_a=0$, this integral is invariant under deformations of $\Sigma$ that do not cross charged insertions and do not pick up boundary terms. This is the bridge from Noether currents to the topological-operator picture of symmetry: a conserved current can be integrated over a codimension-one surface, and the result depends only on how that surface links charged operators.

For ordinary zero-form symmetries, this surface is codimension one. For higher-form symmetries, the current has a different degree and the charged objects are extended operators. That generalization appears later, but the seed is already here.

## What Noether's theorem does not say

Noether's theorem is powerful, but it does not automatically answer every symmetry question in QFT.

It does not say that every conserved current comes from a manifest transformation of elementary fields. Emergent symmetries, dual descriptions, topological currents, and accidental symmetries can make the field-level action obscure.

It does not say that the current is unique. Improvements and operator mixing are real.

It does not guarantee that the charge exists as an operator on Hilbert space. Infrared divergences, massless modes, spontaneous symmetry breaking, boundary flux, and gauge constraints can obstruct the naive integral.

It does not guarantee that quantization preserves the conservation law. A regulator or path-integral measure can produce an anomaly.

It does not turn gauge redundancy into physical symmetry. Gauge transformations with compact support are redundancies, while global transformations and boundary transformations require separate analysis.

A mature QFT use of Noether's theorem keeps all of these caveats visible without losing the central lesson: continuous symmetry leaves a local trace.

## Common pitfalls

**Dropping the total derivative too early.** If $\delta\mathcal L=\partial_\mu K^\mu$, then $K^\mu$ contributes to the current. Forgetting it gives the wrong answer for translations and for many topological or Wess–Zumino-type terms.

**Confusing on-shell and off-shell identities.** The classical conservation law usually uses the equations of motion. In a path integral, off-shell field configurations contribute, and the same formula becomes a Ward identity with Schwinger–Dyson terms and contact terms.

**Treating $j^\mu$ as unique.** The current can be shifted by $\partial_\nu B^{[\mu\nu]}$ without changing its conservation law. Such shifts often leave charges unchanged but can change local representatives and background-field couplings.

**Forgetting boundary flux.** The step from $\partial_\mu j^\mu=0$ to $dQ/dt=0$ assumes that $\int_{\partial\Sigma}j^i dS_i=0$. Boundaries and asymptotic regions are exactly where many interesting symmetries live.

**Assuming discrete symmetries have ordinary Noether currents.** Noether currents require infinitesimal continuous parameters. Discrete symmetries can have selection rules and topological defects, but not ordinary infinitesimal Noether currents.

**Calling gauge transformations symmetries without qualification.** Global transformations act on physical states. Gauge transformations usually identify redundant descriptions. The difference becomes sharp in the Gauge Redundancy and BRST chapter.

## Relations to other pages

This page follows [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), and [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/). Those pages explain what a symmetry does; this page explains the local current it produces when the symmetry is continuous.

The next page, [Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/), explains why the formula above gives a representative, not a unique object.

The later pages on conserved charges, current conservation in correlation functions, operator Ward identities, path-integral Ward identities, and contact terms build the full QFT meaning of $j_a^\mu$.

The Background Fields and Gauging chapter will reinterpret currents as responses to nondynamical sources. The Anomalies chapter will explain how current conservation can fail while remaining tightly constrained by locality and consistency.

## Research status

The classical Noether construction is completely established. Its basic form is one of the foundations of field theory.

The subtle parts are not doubts about Noether's theorem. They are refinements required by quantum field theory: renormalized composite currents, local counterterms, contact terms, anomaly schemes, boundary charges, topological sectors, and non-Lagrangian symmetries.

In modern research, currents are often only one presentation of symmetry. The same symmetry may be described by background fields, topological defects, higher-form charge operators, symmetry TFT data, or category-valued fusion rules. The Noether current remains the first and most concrete case.

## Exercises

### Exercise 1: Derive the current from a total-derivative symmetry

Let

$$
\delta_a\mathcal L=\partial_\mu K_a^\mu
$$

and

$$
\delta_a\mathcal L
=\mathcal E_I\delta_a\Phi^I
+\partial_\mu\theta^\mu(\delta_a\Phi).
$$

Show that

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu
$$

satisfies

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I.
$$

<details><summary><strong>Solution</strong></summary>

Subtract the two expressions for $\delta_a\mathcal L$:

$$
\mathcal E_I\delta_a\Phi^I
+\partial_\mu\theta^\mu(\delta_a\Phi)
-\partial_\mu K_a^\mu=0.
$$

Group the total derivative terms:

$$
\mathcal E_I\delta_a\Phi^I
+\partial_\mu
\bigl(\theta^\mu(\delta_a\Phi)-K_a^\mu\bigr)=0.
$$

Therefore, with

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu,
$$

we obtain

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I.
$$

On shell, $\mathcal E_I=0$, so the current is conserved.

</details>

### Exercise 2: Shift symmetry of a massless scalar

Consider a real massless scalar with

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi.
$$

The theory has a shift symmetry

$$
\delta\phi=\epsilon.
$$

Find the Noether current and verify its conservation on shell.

<details><summary><strong>Solution</strong></summary>

For the infinitesimal transformation with unit parameter, $\delta\phi=1$. The Lagrangian is strictly invariant because it depends only on derivatives of $\phi$, so $K^\mu=0$. The canonical current is

$$
j^\mu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\delta\phi
=\partial^\mu\phi.
$$

Its divergence is

$$
\partial_\mu j^\mu=\Box\phi.
$$

The equation of motion is $\Box\phi=0$, so the current is conserved on shell.

</details>

### Exercise 3: Translation current for a scalar field

For

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi-V(\phi),
$$

use the translation variation

$$
\delta_\nu\phi=\partial_\nu\phi
$$

and

$$
K_\nu^\mu=\delta^\mu{}_\nu\mathcal L
$$

to derive the canonical stress tensor $T^\mu{}_\nu$.

<details><summary><strong>Solution</strong></summary>

The boundary term for a first-derivative scalar Lagrangian is

$$
\theta^\mu(\delta_\nu\phi)
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi
=\partial^\mu\phi\partial_\nu\phi.
$$

The Noether current associated with translation in the $\nu$ direction is

$$
T^\mu{}_\nu
=\theta^\mu(\delta_\nu\phi)-K_\nu^\mu
=\partial^\mu\phi\partial_\nu\phi
-\delta^\mu{}_\nu\mathcal L.
$$

The conservation law $\partial_\mu T^\mu{}_\nu=0$ follows from the scalar equation of motion and spacetime-translation invariance.

</details>

### Exercise 4: Local parameter and integration by parts

Assume

$$
\delta_{\alpha(x)}S
=\int d^dx\,(\partial_\mu\alpha)j^\mu.
$$

Show that for compactly supported $\alpha(x)$ this is equivalent to

$$
\delta_{\alpha(x)}S
=-\int d^dx\,\alpha\partial_\mu j^\mu.
$$

Why does the argument fail if $\alpha$ is not compactly supported and boundary flux is nonzero?

<details><summary><strong>Solution</strong></summary>

Integrate by parts:

$$
\int d^dx\,(\partial_\mu\alpha)j^\mu
=\int d^dx\,\partial_\mu(\alpha j^\mu)
-\int d^dx\,\alpha\partial_\mu j^\mu.
$$

If $\alpha$ has compact support, the total derivative integrates to zero. Hence

$$
\delta_{\alpha(x)}S
=-\int d^dx\,\alpha\partial_\mu j^\mu.
$$

If $\alpha$ does not vanish at the boundary, the surface term

$$
\int_{\partial M} \alpha j^\mu d\Sigma_\mu
$$

may be nonzero. In that case the transformation can carry charge through the boundary or act as an asymptotic symmetry. Boundary terms must then be treated as part of the physical data.

</details>

## References

- Emmy Noether, “Invariante Variationsprobleme.” The original theorem relating continuous variational symmetries and conservation laws.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters on spacetime and internal symmetries. Clear operator-oriented treatment of conserved currents and their non-uniqueness.
- Sidney Coleman, *Aspects of Symmetry*, especially “Dilatations,” “Soft Pions,” and “Renormalization and Symmetry.” Classic uses of currents and Ward identities in QFT.
- Mark Srednicki, *Quantum Field Theory*, §22. Compact treatment of continuous symmetries and conserved currents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I. Symmetries, generators, and the relation between quantum transformations and field operators.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*. Pedagogical derivations of Noether's theorem, path-integral identities, and Ward–Takahashi identities.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*. Standard perturbative reference for Noether currents and Ward identities.

## Version history

- **2026-06-17:** Initial polished page on Noether currents.
