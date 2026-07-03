---
title: "Current Conservation in Correlation Functions"
description: "Explains why conserved currents are conserved only away from operator insertions, derives the contact-term form of current conservation, and prepares the operator and path-integral Ward identities."
sidebar:
  label: "Current Conservation in Correlators"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §22 and §§67–68; Coleman lectures on current algebra and Ward identities; Weinberg Vol. I on symmetry generators; Schwartz chapters on path-integral Ward identities."
topics:
  - current conservation
  - correlation functions
  - Ward identities
  - contact terms
  - conserved charges
  - operator insertions
canonicalTopics:
  - current-conservation-in-correlators
  - contact-term-ward-identity
  - local-ward-identity
  - integrated-ward-identity
researchStatus:
  established:
    - "For an exact nonanomalous continuous symmetry, current conservation inside correlation functions is a distributional statement: the divergence vanishes away from insertions and has contact terms at charged insertions."
  active:
    - "In interacting QFT, contact terms are scheme-dependent local data tied to composite-operator renormalization, background-field counterterms, anomalies, boundaries, defects, and current algebra extensions."
---

## Summary

The equation

$$
\partial_\mu j_a^\mu(x)=0
$$

is true but incomplete inside correlation functions.

If

$$
\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n),
$$

then the current is conserved away from the insertion points:

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0,
\qquad
x\neq x_k.
$$

As a distribution, however, the divergence can have delta functions at the insertions. With the convention

$$
\delta_a\mathcal O=i[Q_a,\mathcal O],
$$

the nonanomalous local Ward identity is

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

This formula is the precise QFT version of a simple picture: the current is conserved unless its charge surface crosses a charged operator. When it crosses, the operator transforms.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A Euclidean region containing operator insertions, with current conservation in the bulk and contact terms on small spheres around the insertions.](/figures/symmetry-anomalies-topology/current-contact-terms-surface.svg)

<figcaption>

Inside a correlator, current conservation is distributional. Away from insertions, $\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0$. Small spheres around insertions detect contact terms, and the integrated identity says that the boundary flux equals the symmetry variation of the insertions inside the region.

</figcaption>
</figure>

## Prerequisites

Read [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/) first. We use the charge convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+\alpha^a\delta_a\mathcal O+O(\alpha^2),
$$

so

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

You should also remember from [Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/) that different current representatives can differ by contact terms or boundary terms even when their separated-point conservation law agrees.

## Core idea

Conservation in QFT is not only an equation of local operators. It is also a statement about distributions.

A local operator equation such as

$$
\partial_\mu j^\mu(x)=0
$$

means that the divergence vanishes at points where the operator is inserted by itself, or away from coincident singularities. But correlation functions are singular when operators collide. Therefore applying $\partial_\mu$ to

$$
\langle j^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
$$

can produce terms supported at

$$
x=x_k.
$$

Those terms are contact terms. They are not optional corrections to current conservation. They are the mechanism by which the current generates the symmetry action on inserted operators.

The core slogan is

$$
\text{current conservation away from insertions}
\quad+
\text{contact terms at insertions}
\quad=
\text{Ward identity}.
$$

## Setup and conventions

Let $j_a^\mu$ be a renormalized current for an exact nonanomalous continuous internal symmetry. Let

$$
\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
$$

be a product of local operators. We write correlators without always displaying time ordering. The formula below should be read as the appropriate correlator in the chosen formalism:

- Wightman correlators have operator-ordering domains and singularities on light cones.
- Lorentzian time-ordered correlators get contact terms from differentiating time-ordering step functions.
- Euclidean correlators are distributions with singularities at coincident insertion points.
- Path-integral correlators require a measure and a regulator, which can add anomalies or scheme-dependent local terms.

For the nonanomalous internal symmetry and away from coincident insertions, we have

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0.
$$

As a distribution, the local Ward identity is

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

If the current is explicitly broken or anomalous, the right-hand side is modified. A useful schematic form is

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=\langle \mathcal B_a(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle,
$$

where $\mathcal B_a$ may be an explicit-breaking operator or an anomaly density, depending on context and convention.

:::note[Convention-sensitive sign note]
The factor $-i$ follows from the convention $\delta_a\mathcal O=i[Q_a,\mathcal O]$ and the Lorentzian path-integral weight $e^{iS}$. In Euclidean conventions, or with $U\mathcal O U^{-1}$ instead of $U^\dagger\mathcal O U$, the displayed $i$ can move. The invariant content is that integrating the divergence over a small region around an insertion gives the infinitesimal symmetry variation of that insertion.
:::

## Why contact terms must be there

Suppose the current is conserved everywhere as an ordinary function inside the correlator:

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0
$$

with no contact terms. Integrate this equation over a spacetime region $R$ containing one charged operator $\mathcal O(y)$ and no other insertions. Gauss' theorem would give

$$
\int_{\partial R}d\Sigma_\mu\,
\langle j_a^\mu(x)\mathcal O(y)\cdots\rangle=0.
$$

But the left-hand side is the infinitesimal charge surface surrounding $\mathcal O(y)$. It should act on $\mathcal O(y)$, not vanish. Therefore the divergence must contain a delta function at $x=y$.

Indeed the local identity gives

$$
\int_R d^dx\,\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

By Gauss' theorem,

$$
\int_{\partial R}d\Sigma_\mu\,
\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

This is the integrated Ward identity. It says a current surface measures the total symmetry variation of the operators it encloses.

## Operator derivation in one paragraph

The full operator derivation is the next page, but the essence is short.

Take a Lorentzian time-ordered correlator with one current insertion. Away from equal times,

$$
\partial_\mu j_a^\mu=0.
$$

However, differentiating the time-ordering symbols produces equal-time commutators. For a single operator $\mathcal O(y)$,

$$
\partial_\mu\langle T\,j_a^\mu(x)\mathcal O(y)\rangle
=\delta(x^0-y^0)
\langle [j_a^0(x),\mathcal O(y)]\rangle
$$

up to terms that vanish by separated-point conservation and up to convention-dependent factors from fermionic grading.

Integrating over $\mathbf x$ gives

$$
\int d^{d-1}\mathbf x\,
\delta(x^0-y^0)
\langle [j_a^0(x),\mathcal O(y)]\rangle
=\delta(x^0-y^0)\langle [Q_a,\mathcal O(y)]\rangle.
$$

Since

$$
[Q_a,\mathcal O]=-i\delta_a\mathcal O,
$$

the contact term is

$$
-i\delta^{(d)}(x-y)\langle\delta_a\mathcal O(y)\rangle.
$$

That is the displayed Ward identity.

## Path-integral derivation in one paragraph

The path-integral derivation is also developed later, but the short version is the fastest way to see the sign.

Under a local change of variables

$$
\Phi^I(x)\mapsto\Phi^I(x)+\alpha^a(x)\delta_a\Phi^I(x),
$$

an exact nonanomalous symmetry gives

$$
\delta S
=\int d^dx\,(\partial_\mu\alpha^a)j_a^\mu
=-\int d^dx\,\alpha^a\partial_\mu j_a^\mu
$$

for compactly supported $\alpha^a$. Changing variables in the path integral gives

$$
0=\langle\delta\mathcal X\rangle+i\langle\delta S\,\mathcal X\rangle.
$$

The variation of the insertions is

$$
\delta\mathcal X
=\sum_k\alpha^a(x_k)\,
\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n.
$$

Since $\alpha^a(x)$ is arbitrary, this implies

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

This derivation also shows where anomalies can enter: the measure may fail to be invariant.

## Separated-point conservation

The Ward identity immediately implies the separated-point statement

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle=0
\qquad
x\neq x_k.
$$

This is often what physicists mean informally when they say “the current is conserved in correlation functions.” The phrase is safe only if one remembers the missing half:

$$
\text{at }x=x_k,
\quad
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
\text{ has contact terms.}
$$

In momentum space, contact terms become polynomials or lower-point terms. Dropping them can make Ward identities appear false. Keeping them is essential for correct normalization of charges, current algebra, anomaly formulas, and background-field response.

## Integrated Ward identities

Let $R$ be a spacetime region whose boundary $\partial R$ does not pass through insertions. Integrating the local identity gives

$$
\int_{\partial R}d\Sigma_\mu\,
\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle
\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n
\rangle.
$$

This is the form closest to the charge picture. A surface integral of $j_a^\mu$ acts on all operators inside the surface.

If $R$ encloses no charged insertions and no anomaly or explicit breaking, then

$$
\int_{\partial R}d\Sigma_\mu\,
\langle j_a^\mu(x)\mathcal X\rangle=0.
$$

If $R$ encloses all insertions in a vacuum correlator and the surface can be pushed to infinity with no boundary contribution, then

$$
\sum_{k=1}^n
\langle
\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n
\rangle=0.
$$

This is the global Ward identity.

For an abelian symmetry with operators of definite charges,

$$
[Q,\mathcal O_{q_k}]=q_k\mathcal O_{q_k},
$$

so

$$
\delta\mathcal O_{q_k}=iq_k\mathcal O_{q_k}.
$$

The global Ward identity becomes

$$
\left(\sum_{k=1}^n q_k\right)
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle=0.
$$

Thus the correlator vanishes unless the total charge is zero, assuming the vacuum and boundary conditions are invariant.

This is how the familiar charge-neutrality selection rule descends from local current conservation.

## Example: U(1) scalar two-point function

For the complex scalar $U(1)$ symmetry,

$$
\delta\phi=i\phi,
\qquad
\delta\phi^\dagger=-i\phi^\dagger.
$$

Take

$$
\mathcal X=\phi(y)\phi^\dagger(z).
$$

The Ward identity gives

$$
\partial_\mu\langle j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=-i\delta^{(d)}(x-y)\langle i\phi(y)\phi^\dagger(z)\rangle
-i\delta^{(d)}(x-z)\langle \phi(y)(-i\phi^\dagger(z))\rangle.
$$

Therefore

$$
\partial_\mu\langle j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=\left[\delta^{(d)}(x-y)-\delta^{(d)}(x-z)\right]
\langle\phi(y)\phi^\dagger(z)\rangle.
$$

The current is conserved for $x\neq y,z$. At $x=y$, it sees charge $+1$. At $x=z$, it sees charge $-1$. The total integrated charge is zero, so the two-point function is allowed.

For

$$
\mathcal X=\phi(y)\phi(z),
$$

the global Ward identity gives total charge $+2$, so in a charge-invariant vacuum

$$
\langle\phi(y)\phi(z)\rangle=0.
$$

## Contact terms and operator products

Contact terms are local distributions supported when points coincide. In $d$ dimensions, the simplest one is

$$
\delta^{(d)}(x-y).
$$

Derivatives of delta functions can also appear:

$$
\partial_\mu\delta^{(d)}(x-y),
\qquad
\partial_\mu\partial_\nu\delta^{(d)}(x-y),
\qquad\ldots
$$

Such terms are common when currents are improved, when stress tensors are involved, or when operators with spin and derivatives appear.

The operator-product expansion packages the same information locally. Near $x=y$, a current and a charged operator can have a singular OPE whose divergence is a delta function. Schematically,

$$
j_a^\mu(x)\mathcal O(y)
\sim
\frac{(x-y)^\mu}{\operatorname{vol}(S^{d-1})|x-y|^d}
\left(-i\delta_a\mathcal O(y)\right)+\cdots.
$$

Using

$$
\partial_\mu\frac{x^\mu}{\operatorname{vol}(S^{d-1})|x|^d}
=\delta^{(d)}(x)
$$

as a distribution, the divergence reproduces the contact term.

This OPE viewpoint is especially important in CFT, current algebra, and two-dimensional QFT.

## Current conservation with other current insertions

If $\mathcal X$ contains another current, the same logic applies, but there can be extra local terms.

For example,

$$
\partial_\mu\langle j_a^\mu(x)j_b^\nu(y)\cdots\rangle
$$

can have contact terms at $x=y$ expressing how $j_b^\nu$ transforms under the symmetry generated by $j_a^\mu$. In a nonabelian symmetry, this includes the adjoint action,

$$
\delta_a j_b^\nu=f_{ab}{}^c j_c^\nu
$$

up to conventions, improvements, and possible Schwinger terms.

In two-dimensional current algebra and anomalous theories, contact terms in current-current correlators are not bookkeeping dirt. They encode central extensions, levels, and anomaly coefficients.

## Explicit breaking

If the transformation is not an exact symmetry, the current conservation equation is modified. Suppose the local variation of the action has the form

$$
\delta S
=\int d^dx\,(\partial_\mu\alpha^a)j_a^\mu
+\int d^dx\,\alpha^a\mathcal B_a.
$$

Then the same path-integral argument gives

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=\langle\mathcal B_a(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

Classically, $\mathcal B_a$ is an explicit-breaking operator. For example, if a mass term breaks an axial symmetry, $\mathcal B_a$ is proportional to the mass and a pseudoscalar bilinear.

This formula is useful because it separates two different effects:

$$
\text{bulk nonconservation}
\quad\text{versus}\quad
\text{contact action on insertions}.
$$

Even a broken current still acts on charged insertions. It is just not conserved in the bulk.

## Anomalous conservation laws

An anomaly has a similar-looking Ward identity but a different meaning. Classically the symmetry exists; quantum mechanically the regulator or measure fails to preserve it. Schematically,

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=\langle\mathcal A_a(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

The anomaly density $\mathcal A_a$ is not an arbitrary violation. It is constrained by locality, background fields, counterterm choices, and Wess–Zumino consistency.

For example, the axial current of a Dirac fermion coupled to a background gauge field has a quantum divergence involving $F\widetilde F$, with coefficients depending on normalization. That belongs to the anomaly chapter. Here the important point is structural: anomalies are bulk terms in the Ward identity, distinct from contact terms due to charged insertions.

## Boundaries and defects

If the spacetime region has a boundary or a defect, current conservation can fail by inflow into lower-dimensional degrees of freedom. A schematic conservation equation might look like

$$
\partial_\mu j_{\mathrm{bulk}}^\mu(x)
=-\delta_{\partial M}(x)\,\partial_\alpha j_{\mathrm{edge}}^\alpha(x)
$$

or more generally include defect-localized operators.

Then the integrated Ward identity says that bulk charge is not conserved alone, but bulk plus boundary charge may be conserved. This is the local form of edge modes, anomaly inflow, and defect symmetry action.

The moral is the same as in the conserved-charge page: a current is not fully specified until the boundary and defect conditions are specified.

## Background-field viewpoint

A clean way to organize contact terms is to couple the current to a background field $A_\mu^a$ and define

$$
\langle j_a^\mu(x)\rangle_A
\sim
\frac{\delta W[A]}{\delta A_\mu^a(x)},
$$

with a sign depending on the source convention. Gauge invariance of the background-field generating functional becomes the Ward identity.

This viewpoint has two advantages.

First, contact terms are no longer mysterious: they come from differentiating local functionals of sources.

Second, anomalies become sharply defined: they are obstructions to making $W[A]$ invariant under background gauge transformations.

The Background Fields and Gauging chapter develops this systematically.

## Common pitfalls

**Saying “$\partial_\mu j^\mu=0$ inside correlators” without contact terms.** This is only true away from insertions. As a distribution, the divergence has delta functions at charged operators.

**Treating contact terms as mistakes.** Contact terms encode the symmetry action. Without them, the current would fail to generate transformations.

**Using separated-point identities to derive integrated selection rules.** Integrated Ward identities depend precisely on the contact terms. Dropping them destroys the selection rule.

**Confusing explicit breaking with contact terms.** Contact terms live at operator insertions and appear even for exact symmetries. Explicit breaking or anomalies produce bulk terms in the divergence.

**Ignoring scheme dependence.** Local contact terms can change under current improvements, operator redefinitions, and background counterterms. Separated-point correlators may be unchanged while local Ward identities shift by local terms.

**Forgetting fermion signs.** If some insertions are fermionic, moving symmetry generators through time-ordered products can produce graded signs. The compact formulas on this page suppress those signs.

**Assuming all Ward identities are nonanomalous.** A classical change of variables can acquire a Jacobian. That is the beginning of the anomaly story, not a small correction.

## Relations to other pages

[Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/) explains how the surface integral of a current gives a charge. This page explains what happens when that surface encloses or crosses operator insertions.

[Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/) gives the current from localizing a continuous symmetry parameter. This page is the correlator-level version of the same localization idea.

[Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/) explains why contact terms can shift even when separated-point conservation is unchanged.

[Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) is the global consequence of the integrated Ward identity in charge-invariant states.

[Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) gives the finite, topological-operator version of the same crossing rule.

The next two pages derive Ward identities in operator and path-integral language. Later pages on contact terms and current algebra repair the local distributional details that are only previewed here.

## Research status

The basic local Ward identity for nonanomalous continuous symmetries is established graduate-level QFT.

What remains subtle in research practice is not the slogan but the local data: which current representative is being used, which contact terms are fixed by a chosen renormalization scheme, which terms can be removed by background counterterms, which terms are anomaly coefficients, and how the identity is modified by boundaries, defects, gauge constraints, spontaneous symmetry breaking, or generalized symmetry.

A good working rule is:

$$
\text{separated-point Ward identities are often universal;}
\qquad
\text{contact terms require a scheme.}
$$

Anomalies are the exception that proves the rule: their local representatives can shift by counterterms, but their cohomology class is physical.

## Exercises

### Exercise 1: Integrated Ward identity from the local one

Starting from

$$
\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle,
$$

integrate over a region $R$ whose boundary avoids all insertions. Derive

$$
\int_{\partial R}d\Sigma_\mu\,\langle j_a^\mu\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Integrate both sides over $R$:

$$
\int_R d^dx\,\partial_\mu\langle j_a^\mu(x)\mathcal X\rangle
=-i\sum_k\int_R d^dx\,\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

The left-hand side becomes a boundary integral by Gauss' theorem:

$$
\int_R d^dx\,\partial_\mu\langle j_a^\mu\mathcal X\rangle
=\int_{\partial R}d\Sigma_\mu\,\langle j_a^\mu\mathcal X\rangle.
$$

The delta function contributes only if $x_k\in R$. Hence

$$
\int_{\partial R}d\Sigma_\mu\,\langle j_a^\mu\mathcal X\rangle
=-i\sum_{x_k\in R}
\langle\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle.
$$

</details>

### Exercise 2: Charge neutrality from the Ward identity

Let $\mathcal O_{q_k}$ have $U(1)$ charge $q_k$, so

$$
\delta\mathcal O_{q_k}=iq_k\mathcal O_{q_k}.
$$

Assume the boundary term at infinity vanishes. Show that

$$
\left(\sum_k q_k\right)
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Integrate the Ward identity over a region enclosing all insertions and push the boundary to infinity. By assumption the boundary integral vanishes, so

$$
0=-i\sum_k
\langle\mathcal O_{q_1}\cdots\delta\mathcal O_{q_k}\cdots\mathcal O_{q_n}\rangle.
$$

Using $\delta\mathcal O_{q_k}=iq_k\mathcal O_{q_k}$ gives

$$
0=-i\sum_k iq_k
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

Since $-i\,i=1$,

$$
0=\left(\sum_k q_k\right)
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

Thus the correlator can be nonzero only if the total charge vanishes, unless the vacuum, boundary conditions, or symmetry assumptions fail.

</details>

### Exercise 3: U(1) two-point contact terms

For $\delta\phi=i\phi$ and $\delta\phi^\dagger=-i\phi^\dagger$, show that

$$
\partial_\mu\langle j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=\left[\delta^{(d)}(x-y)-\delta^{(d)}(x-z)\right]
\langle\phi(y)\phi^\dagger(z)\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Apply the Ward identity:

$$
\partial_\mu\langle j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=-i\delta^{(d)}(x-y)\langle \delta\phi(y)\phi^\dagger(z)\rangle
-i\delta^{(d)}(x-z)\langle \phi(y)\delta\phi^\dagger(z)\rangle.
$$

Substitute

$$
\delta\phi=i\phi,
\qquad
\delta\phi^\dagger=-i\phi^\dagger.
$$

Then

$$
-i\delta(x-y)\langle i\phi(y)\phi^\dagger(z)\rangle
=\delta(x-y)\langle\phi(y)\phi^\dagger(z)\rangle,
$$

and

$$
-i\delta(x-z)\langle\phi(y)(-i\phi^\dagger(z))\rangle
=-\delta(x-z)\langle\phi(y)\phi^\dagger(z)\rangle.
$$

Combining the two terms gives

$$
\partial_\mu\langle j^\mu(x)\phi(y)\phi^\dagger(z)\rangle
=\left[\delta^{(d)}(x-y)-\delta^{(d)}(x-z)\right]
\langle\phi(y)\phi^\dagger(z)\rangle.
$$

</details>

### Exercise 4: Current OPE and delta functions

Use the distributional identity

$$
\partial_\mu\frac{x^\mu}{\operatorname{vol}(S^{d-1})|x|^d}
=\delta^{(d)}(x)
$$

to explain why the OPE

$$
j_a^\mu(x)\mathcal O(0)
\sim
\frac{x^\mu}{\operatorname{vol}(S^{d-1})|x|^d}
\left(-i\delta_a\mathcal O(0)\right)
$$

reproduces the Ward contact term.

<details><summary><strong>Solution</strong></summary>

Take the divergence of the singular term:

$$
\partial_\mu\left[
\frac{x^\mu}{\operatorname{vol}(S^{d-1})|x|^d}
\left(-i\delta_a\mathcal O(0)\right)
\right].
$$

The operator factor is independent of $x$ in this leading term, so

$$
=\left(\partial_\mu\frac{x^\mu}{\operatorname{vol}(S^{d-1})|x|^d}\right)
\left(-i\delta_a\mathcal O(0)\right).
$$

Using the distributional identity gives

$$
=-i\delta^{(d)}(x)\delta_a\mathcal O(0),
$$

which is exactly the contact term in the Ward identity for an insertion at the origin.

</details>

### Exercise 5: Explicit breaking versus contact terms

Suppose

$$
\delta S
=\int d^dx\,(\partial_\mu\alpha)j^\mu
+\int d^dx\,\alpha\mathcal B.
$$

Using a change of variables in the Lorentzian path integral, derive schematically

$$
\partial_\mu\langle j^\mu(x)\mathcal X\rangle
=\langle\mathcal B(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta\mathcal O_k\cdots\mathcal O_n\rangle.
$$

<details><summary><strong>Solution</strong></summary>

The change of variables gives

$$
0=\langle\delta\mathcal X\rangle+i\langle\delta S\,\mathcal X\rangle.
$$

For compactly supported $\alpha$,

$$
\int d^dx\,(\partial_\mu\alpha)j^\mu
=-\int d^dx\,\alpha\partial_\mu j^\mu.
$$

Thus

$$
0=\int d^dx\,\alpha(x)\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta\mathcal O_k\cdots\mathcal O_n\rangle
+i\int d^dx\,\alpha(x)
\left[-\langle\partial_\mu j^\mu(x)\mathcal X\rangle+\langle\mathcal B(x)\mathcal X\rangle\right].
$$

Because $\alpha(x)$ is arbitrary, the integrand must vanish:

$$
\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta\mathcal O_k\cdots\mathcal O_n\rangle
+i\left[-\langle\partial_\mu j^\mu(x)\mathcal X\rangle+\langle\mathcal B(x)\mathcal X\rangle\right]=0.
$$

Solving for the divergence gives

$$
\partial_\mu\langle j^\mu(x)\mathcal X\rangle
=\langle\mathcal B(x)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)
\langle\mathcal O_1\cdots\delta\mathcal O_k\cdots\mathcal O_n\rangle.
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §22 and §§67–68. Useful compact treatment of currents and Ward identities, including perturbative applications.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the symmetry and current-algebra lectures. Clear operator intuition for charges and contact terms.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” “Dilatations,” and “Renormalization and Symmetry.” Classic applications of Ward identities and current algebra.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I. Foundational treatment of symmetry generators and their action on fields and states.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Schwinger–Dyson equations, Ward–Takahashi identities, and anomalies.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for the functional formalism, composite operators, and distributional identities in renormalized QFT.

## Version history

- **2026-06-17:** Initial polished page on current conservation in correlation functions.
