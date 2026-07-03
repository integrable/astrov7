---
title: "Matching Correlation Functions"
description: "How to determine Wilson coefficients by equating low-energy Green functions or generating functionals in a full theory and its EFT."
sidebar:
  label: "Matching Correlation Functions"
  order: 5
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I and II, renormalization and effective actions; Schwartz 2014, path integrals, renormalized perturbation theory, and EFT chapters; Burgess 2020, effective actions, matching, redundant interactions, and power counting."
topics:
  - correlation-function matching
  - generating functionals
  - Wilson coefficients
  - off-shell matching
  - contact terms
  - background fields
canonicalTopics:
  - matching-correlation-functions
  - eft-generating-functionals
  - wilson-coefficients
researchStatus:
  established:
    - "Matching correlation functions is a standard way to determine EFT Wilson coefficients by equating low-energy Green functions or source functionals after consistent renormalization."
  active:
    - "Gauge-invariant off-shell matching, background-field matching, evanescent operators, field redefinitions, and automated multi-operator matching remain active technical areas."
---

## Summary

**Correlation-function matching** determines EFT Wilson coefficients by demanding that a full theory and its low-energy EFT give the same Green functions for light fields and external sources at momenta below the heavy scale. It is the source-functional version of matching.

The schematic condition is

$$
G^{(n)}_{\text{full}}(p_a;M)
=
G^{(n)}_{\text{EFT}}(p_a;C_i(\mu),\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right),
\qquad Q\ll M,
$$

where $M$ is the heavy scale, $Q$ denotes typical external momenta and light masses, and the equality is understood after using the same infrared regulator, the same normalization conventions for light fields and sources, and a specified operator basis.

The cleanest formulation uses generating functionals. Couple sources $J_a$ to light operators $\mathcal O_a$, integrate out heavy fields in the full theory, and compare the resulting low-energy functional with the EFT generating functional:

$$
W_{\text{full}}[J]
=
W_{\text{EFT}}[J;C_i(\mu),\mu]
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right)
$$

for source variations with support at low momentum. Functional derivatives with respect to $J_a$ then give matching conditions for any desired correlator.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Correlation-function matching as a source-functional workflow: compare the full-theory generating functional for light sources with the EFT generating functional, expand the hard part locally, and read Wilson coefficients.](/figures/renormalization-rg-eft/correlator-matching-generating-functional.svg)

<figcaption>

Correlation-function matching compares source functionals, not isolated diagrams in a vacuum. Heavy fields and hard loop momenta generate local operators; light-field nonanalyticities must be reproduced by the EFT side and therefore do not belong inside Wilson coefficients.

</figcaption>
</figure>

Correlation-function matching is especially useful when the object of interest is naturally off shell: current correlators, stress-tensor correlators, background-field effective actions, vacuum polarization functions, operator mixing, or EFTs for response functions. On-shell $S$-matrix matching is often simpler for scattering observables; correlation matching is broader but demands more care with field redefinitions, contact terms, and gauge dependence.

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/), and [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/).

For the correlator language, it is useful to know [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/).

## Core idea

A full theory and its EFT need not have the same fields at all scales. They must have the same low-energy answers for the same low-energy questions. Correlation-function matching implements this principle by asking the same source-defined question in two descriptions.

Suppose the full theory contains light fields $\phi$, heavy fields $H$, and external sources $J_a$ coupled to light-sector operators $\mathcal O_a$:

$$
Z_{\text{full}}[J]
=
\int \mathcal D\phi\,\mathcal D H\,
\exp\left(iS_{\text{full}}[\phi,H]+i\int d^d x\,J_a\mathcal O_a\right).
$$

At energies $Q\ll M$, the heavy fields cannot propagate as resolved long-distance degrees of freedom. Their virtual effects can be represented by local operators built from the light fields and sources:

$$
Z_{\text{EFT}}[J]
=
\int \mathcal D\phi\,
\exp\left(iS_{\text{EFT}}[\phi;J,C_i(\mu)]\right).
$$

The matching condition is

$$
Z_{\text{full}}[J]
=
Z_{\text{EFT}}[J]
$$

up to the desired order in $Q/M$ and perturbation theory, after expanding the full-theory answer for low external momenta. Equivalently, one may match the connected generating functional

$$
W[J]=-i\log Z[J]
$$

or the one-particle-irreducible effective action

$$
\Gamma[\varphi;J].
$$

Each choice has advantages. Matching $Z$ or $W$ keeps the relation to correlators direct. Matching $\Gamma$ often makes locality and one-particle-irreducible structures more transparent. Matching on-shell amplitudes avoids some off-shell ambiguities. The physics is the same when the calculation is complete and the operator basis is handled consistently.

## Setup and conventions

This page uses the conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, $d=4-2\epsilon$ in dimensional regularization, and

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

We use the following notation:

| Symbol | Meaning |
|---|---|
| $M$ | heavy mass or threshold scale |
| $Q$ | typical light external momentum or mass |
| $\mu_M$ | matching scale, usually chosen near $M$ |
| $J_a$ | external sources coupled to light operators |
| $G^{(n)}$ | time-ordered Green function or momentum-space correlator |
| $C_i(\mu)$ | Wilson coefficients in the EFT |
| $\mathcal O_i$ | local EFT operators built from light fields and sources |

The word **correlator** is context dependent. It may mean a bare Green function, a renormalized Green function, a connected correlator, a 1PI vertex function, or a current correlator with contact terms. A matching page must say which object is being matched.

For most EFT matching calculations, the safe rule is:

$$
\text{match renormalized objects in a specified scheme.}
$$

If bare quantities are used as an intermediate device, the page should still explain how the renormalized Wilson coefficients are extracted.

## Why match correlators?

On-shell amplitudes are often the most economical way to determine physical Wilson coefficients. Correlation functions are useful when the EFT is meant to reproduce more structure than scattering amplitudes alone.

Examples include:

| Matching object | Why correlator matching is natural |
|---|---|
| Vacuum polarization | The two-point current correlator defines running charges, response functions, and threshold corrections. |
| Stress-tensor correlators | Coupling to a background metric organizes curvature counterterms and gravitational EFT coefficients. |
| Flavor-changing weak Hamiltonians | Time-ordered current products match onto local four-fermion operators. |
| Background-field effective actions | Gauge-invariant source backgrounds make the local operator expansion manifest. |
| Composite-operator bases | Operator insertions and contact terms determine mixing matrices. |
| Condensed-matter response EFTs | Sources are physical probes: electromagnetic fields, strain, temperature gradients, and chemical potentials. |

The correlator viewpoint says: do not match only a number; match a functional response.

If $J$ is a source for a current $J^\mu_{\text{phys}}$, then

$$
\frac{\delta^2 W[A]}{\delta A_\mu(x)\delta A_\nu(y)}
$$

is a current-current correlator. Integrating out a heavy charged particle changes the low-energy effective action for $A_\mu$ by local terms such as

$$
\Delta\mathcal L_{\text{EFT}}
\supset
c_1 F_{\mu\nu}F^{\mu\nu}
+\frac{c_2}{M^2}F_{\mu\nu}\Box F^{\mu\nu}
+\frac{c_3}{M^4}(F_{\mu\nu}F^{\mu\nu})^2
+\cdots.
$$

Those coefficients are most directly read from low-momentum correlators of the source field or current.

## Matching connected Green functions

Let $G^{(n)}$ denote a renormalized connected correlator of light fields or source-coupled operators. In momentum space, strip the overall momentum-conservation delta function and write

$$
G^{(n)}(p_1,\ldots,p_n)
=
(2\pi)^d\delta^{(d)}\!\left(\sum_a p_a\right)
\,\widetilde G^{(n)}(p_1,\ldots,p_n).
$$

The matching condition is

$$
\widetilde G^{(n)}_{\text{full}}(p_a;M,\mu)
=
\widetilde G^{(n)}_{\text{EFT}}(p_a;C_i(\mu),\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

At tree level, this reduces to expanding heavy propagators in powers of $p/M$. At loop level, the matching must separate hard and soft momentum regions:

$$
\widetilde G_{\text{full}}
=
\widetilde G_{\text{hard}}
+
\widetilde G_{\text{soft}}.
$$

The EFT reproduces the soft part. The hard part is local and becomes Wilson coefficients:

$$
\widetilde G_{\text{hard}}
=
\sum_i C_i(\mu)\,\widetilde G_i^{\text{local}}.
$$

This is the same hard-minus-EFT logic as one-loop matching, but expressed in the language of Green functions rather than amplitudes.

## Matching 1PI functions

Connected correlators include tree-level propagation through light fields. Sometimes it is cleaner to match 1PI vertex functions. Let $\Gamma^{(n)}$ denote a renormalized 1PI vertex with $n$ external light fields or sources. Then matching takes the form

$$
\Gamma^{(n)}_{\text{full}}(p_a;M)
=
\Gamma^{(n)}_{\text{EFT}}(p_a;C_i(\mu),\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

This approach has a useful feature: local operators in the EFT contribute directly to 1PI vertices. For example, an operator

$$
\Delta\mathcal L
=
\frac{C}{M^2}\phi^2\partial_\mu\phi\partial^\mu\phi
$$

produces a polynomial four-point 1PI vertex. Matching 1PI four-point functions therefore directly determines $C$, up to basis choices and integrations by parts.

However, 1PI matching also has hazards. The notion of being 1PI depends on the field variables and on which degrees of freedom are explicit. If the EFT has fewer fields than the full theory, a graph that is one-particle reducible in the full theory can become local and 1PI in the EFT after a heavy line is contracted. That is not a contradiction. It is the point of integrating out the heavy field.

## Matching with sources and backgrounds

A powerful variant of correlator matching couples the theory to background fields. Instead of matching individual correlators one by one, one matches the local effective action for backgrounds.

For a background gauge field $A_\mu$, one writes

$$
e^{iW[A]}
=
\int \mathcal D\Phi\,
\exp\left(iS[\Phi,A]\right).
$$

At low momenta, the full-theory answer has a local expansion

$$
W_{\text{full}}[A]
=
\int d^d x\left[
-\frac14 Z_F F_{\mu\nu}F^{\mu\nu}
+\frac{a}{M^2}D_\rho F_{\mu\nu}D^\rho F^{\mu\nu}
+\frac{b}{M^4}(F_{\mu\nu}F^{\mu\nu})^2
+\cdots
\right]
+W_{\text{nonlocal, light}}[A].
$$

The local heavy contribution fixes EFT coefficients. The nonlocal light contribution must be reproduced by light fields in the EFT and therefore should not be counted as a Wilson coefficient.

Background-field matching is especially attractive in gauge theories because it can preserve gauge covariance at every step. Rather than matching gauge-dependent off-shell Green functions of gauge potentials, one can match gauge-invariant or background-gauge-covariant functionals built from $F_{\mu\nu}$, covariant derivatives, and matter backgrounds.

The same logic applies to a background metric $g_{\mu\nu}$. Integrating out heavy fields generates curvature terms such as

$$
\Delta\mathcal L
=
\sqrt{-g}\left[
\Delta\Lambda
+\Delta M_{\text{Pl}}^2 R
+a R^2
+b R_{\mu\nu}R^{\mu\nu}
+c R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right],
$$

with coefficients determined by stress-tensor and metric correlators.

## Contact terms are not optional

Correlation functions of local operators contain contact terms. These are terms supported when insertion points coincide, such as

$$
\delta^{(d)}(x-y),
\qquad
\partial_\mu\delta^{(d)}(x-y),
\qquad
\Box\delta^{(d)}(x-y).
$$

In momentum space, contact terms are polynomials in external momenta. That is exactly the same analytic structure as local EFT operators.

This means contact terms are not noise. They are often where Wilson coefficients live.

For example, if a current-current correlator has the low-momentum expansion

$$
\Pi(p^2)
=
\Pi(0)+p^2\Pi'(0)+O(p^4),
$$

then the terms $\Pi(0)$ and $p^2\Pi'(0)$ correspond to local terms in the background effective action. Nonanalytic pieces such as $p^2\log(-p^2)$ reflect light propagation and are not threshold coefficients unless generated by a heavy-only hard region.

A common mistake is to throw away all polynomial terms because they look scheme dependent. It is true that individual contact terms are often scheme or basis dependent. But EFT Wilson coefficients are precisely scheme- and basis-dependent coordinates whose combinations with matrix elements give scheme-independent predictions.

## Off-shell ambiguity and field redefinitions

Correlation-function matching is more sensitive to field definitions than $S$-matrix matching. If the light field is redefined locally,

$$
\phi
\longrightarrow
\phi+\frac{a}{M^2}\Box\phi+\frac{b}{M^2}\phi^3+
\cdots,
$$

then off-shell Green functions change. On-shell amplitudes do not change, provided the transformation is local and invertible and the usual assumptions hold.

The resulting difference is represented in the EFT by redundant operators, often proportional to the light-field equations of motion. For example,

$$
\mathcal O_{\text{EOM}}
=
F(\phi)\frac{\delta S}{\delta\phi}
$$

can change off-shell correlators and contact terms while leaving on-shell amplitudes unchanged up to external-leg and source subtleties.

Therefore correlation-function matching must specify the field basis. Two calculations can produce different Wilson coefficients for redundant operators and still predict the same observables.

The safe workflow is:

| Step | Question |
|---:|---|
| 1 | Which fields and sources define the correlator? |
| 2 | Which field redefinitions have been used? |
| 3 | Which EOM operators have been removed? |
| 4 | Are contact terms being retained or subtracted? |
| 5 | Which combinations of coefficients enter observables? |

If those choices are not stated, the phrase "matching Green functions" is underspecified.

## Gauge theories and off-shell matching

Gauge theories add another layer of care. Ordinary off-shell Green functions of gauge potentials are gauge dependent. Matching them can still be valid if both sides use the same gauge fixing and the final results are converted into gauge-invariant Wilson coefficients, but this is a delicate way to live.

Better options include:

| Method | Advantage |
|---|---|
| Match on-shell amplitudes | Avoids many gauge-dependent off-shell artifacts. |
| Use background-field gauge | Preserves manifest background gauge covariance. |
| Match gauge-invariant correlators | Uses currents, field strengths, Wilson lines, or physical sources. |
| Use BRST-invariant operator bases | Controls unphysical operators and gauge-fixing dependence. |

A useful warning sign is a Wilson coefficient of a gauge-invariant operator that depends on a gauge-fixing parameter. That dependence must cancel after including all operators, field redefinitions, and matrix elements at the same order. If it does not, the matching calculation is incomplete or the projection is wrong.

Gauge-variant operators can appear as intermediate bookkeeping devices. They are not automatically wrong, but they must not be mistaken for physical Wilson coefficients unless the formalism explains how they cancel or are quotiented out.

## A toy example: heavy scalar exchange in a four-point correlator

Consider a light scalar $\phi$ and a heavy scalar $H$ with interaction

$$
\mathcal L_{\text{int}}=-\frac{g}{2}H\phi^2.
$$

At tree level, the connected four-point correlator of $\phi$ receives a heavy-exchange contribution. In momentum space, the $s$-channel part contains

$$
\widetilde G^{(4)}_{\text{full}}
\supset
\frac{(-ig)^2 i}{(p_1+p_2)^2-M^2+i\epsilon}
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon},
$$

up to conventions and the other exchange channels.

At low energy, $(p_1+p_2)^2\ll M^2$, the heavy propagator expands as

$$
\frac{i}{s-M^2+i\epsilon}
=
-\frac{i}{M^2}\left(1+\frac{s}{M^2}+O\left(\frac{s^2}{M^4}\right)\right).
$$

The EFT therefore contains local interactions such as

$$
\Delta\mathcal L_{\text{EFT}}
=
\frac{g^2}{8M^2}\phi^4
+\frac{g^2}{8M^4}\phi^2\Box\phi^2
+\cdots,
$$

with signs depending on the starting convention for the interaction and integration by parts. The correlator matching determines the same Wilson coefficients as amplitude matching, but it also keeps the external propagators and possible contact terms visible.

If one amputates the external light propagators and goes on shell, the same calculation becomes $S$-matrix matching. If one keeps the correlator off shell, operators proportional to $\Box\phi+m^2\phi$ remain visible and basis choices matter.

## A current-product example

Many EFTs are naturally derived by matching products of currents. The classic weak-interaction logic has the schematic form

$$
T\{J_\mu(x)J_\nu(0)\}
\quad\longrightarrow\quad
\sum_i C_i(x)\mathcal O_i(0)
$$

at separations $|x|\sim 1/M_W$ much shorter than the external hadronic scale. In momentum space, this becomes a local expansion of the current-current correlator or amplitude.

At tree level, exchange of a heavy vector boson produces a four-fermion interaction:

$$
\mathcal L_{\text{EFT}}
\supset
-\frac{G_F}{\sqrt2}
(\bar\psi_1\gamma^\mu(1-\gamma^5)\psi_2)
(\bar\psi_3\gamma_\mu(1-\gamma^5)\psi_4).
$$

At loop level, short-distance QCD and electroweak corrections modify the Wilson coefficients and mix operators. The physical low-energy amplitude is then a product of short-distance Wilson coefficients and long-distance matrix elements:

$$
\langle f|T\{J J\}|i\rangle
=
\sum_i C_i(\mu)\langle f|\mathcal O_i(\mu)|i\rangle.
$$

Correlation-function matching is the natural language for this factorization because it makes the operator insertion explicit before choosing particular external states.

## Infrared matching and regulators

Matching is about short-distance coefficients. Infrared physics should cancel between the full theory and the EFT when both contain the same light degrees of freedom.

A typical one-loop matching difference has the form

$$
\Delta G
=
G_{\text{full}}^{(1)}-G_{\text{EFT}}^{(1)}.
$$

Both terms may contain infrared divergences or nonanalytic light-scale dependence:

$$
\log m_{\text{IR}}^2,
\qquad
\log(-p^2),
\qquad
\frac{1}{\epsilon_{\text{IR}}}.
$$

These pieces must cancel in $\Delta G$ if the EFT contains the correct light fields and interactions. The remaining difference is local:

$$
\Delta G
=
\sum_k a_k(\mu,M)p^{2k}.
$$

Those coefficients $a_k$ determine Wilson coefficients.

This is why it is often useful to choose a convenient infrared regulator: small light masses, off-shell Euclidean momenta, dimensional regularization, or external kinematics away from thresholds. The regulator is allowed to be artificial, but it must be used consistently on both sides.

## Matching local functionals

When all external momenta are small compared with $M$, the hard part of the full-theory generating functional is local:

$$
W_{\text{hard}}[J]
=
\int d^d x\,\mathcal L_{\text{local}}(J,\partial J,\phi,\partial\phi,\ldots).
$$

The local functional can be expanded as

$$
\mathcal L_{\text{local}}
=
\sum_i C_i(\mu)\mathcal O_i.
$$

This is the most compact version of correlation matching. Rather than extracting $C_i$ from many individual correlators, compute the local part of the full-theory effective action in a background field and read off the coefficients.

For example, integrating out a heavy fermion in a background gauge field produces a low-energy determinant

$$
-i\log\det(iD\!\!\!/-M),
$$

where $D\!\!\!/\equiv\gamma^\mu D_\mu$. Its derivative expansion yields local gauge-invariant terms. In this volume we write slash notation as $D\!\!\!/$ because KaTeX does not support the usual slashed command.

The same idea underlies heat-kernel matching, covariant derivative expansion, and background-field matching. Those techniques are not different physics; they are efficient ways to compute the same local functional.

## What correlator matching can and cannot determine

Correlation-function matching can determine all Wilson coefficients that affect the chosen set of correlators, including coefficients of off-shell and source-dependent operators. But it can miss coefficients that do not contribute to the chosen probes.

For example:

| Chosen correlator | What it can determine | What it may miss |
|---|---|---|
| Two-point function of $\phi$ | kinetic, mass, and higher-derivative two-field terms | four-field interactions |
| Four-point function of $\phi$ | contact interactions and derivative four-field terms | operators vanishing for that flavor or spin channel |
| Current-current correlator | gauge kinetic and source-response terms | matter operators not coupled to the source |
| Background metric correlators | curvature and stress-tensor response terms | non-gravitational operators without metric dependence |
| On-shell projected correlators | physical amplitude combinations | redundant operators and off-shell contact terms |

A serious matching calculation chooses enough independent correlators to determine the desired operator basis. Overcomplete matching is often a good idea: redundant checks catch basis mistakes.

## Common pitfalls

**Matching unrenormalized objects without saying so.** Bare correlators can be useful intermediate devices, but Wilson coefficients used in predictions are renormalized scheme-dependent quantities.

**Forgetting contact terms.** Polynomial momentum terms are local EFT information. Throwing them away can throw away the Wilson coefficient.

**Treating off-shell coefficients as observables.** Off-shell Green functions depend on field variables, gauges, and source definitions. Observables depend on invariant combinations.

**Double counting light loops.** The long-distance part of a full-theory loop is reproduced by EFT loops. It should not be included again in Wilson coefficients.

**Matching too few correlators.** One correlator may not distinguish all operators in a basis, especially when equations of motion, integration by parts, symmetries, and flavor identities create degeneracies.

**Ignoring operator normalization.** A factor of $2$, a symmetry factor, a source normalization, or a current convention can move directly into the Wilson coefficient.

**Assuming gauge-dependent Green functions are physical.** Gauge-fixed off-shell matching is possible, but gauge-invariant conclusions require a controlled projection onto physical or BRST-invariant data.

## Relations to other pages

This page is the off-shell companion to [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/). On-shell matching is usually cleaner for scattering amplitudes and automatically quotients many redundant operators. Correlator matching is broader and better suited to response functions, background fields, composite operators, and contact terms.

It also connects directly to [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), and [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

Later pages on [Matching with Background Fields](/renormalization-rg-eft/matching-running-decoupling/matching-with-background-fields/) and model calculations will turn the source-functional viewpoint into explicit computations.

## Research status

The conceptual framework of correlation-function matching is established. It is part of the standard EFT toolkit and underlies weak Hamiltonians, heavy-particle decoupling, background-field effective actions, current correlators, and response EFTs.

The active frontier is not the basic principle but the infrastructure: automating high-dimensional operator bases, preserving gauge covariance, handling evanescent operators in dimensional regularization, tracking redundant operators, and converting between off-shell and on-shell bases without losing finite terms.

In modern precision EFT, the hard part is rarely "what is matching?" The hard part is proving that a large calculation really matched the same objects on both sides.

## Exercises

### Exercise 1: Contact terms from a local operator

Let the EFT contain

$$
\Delta S=\int d^d x\,\frac{c}{2M^2}J(x)\Box J(x),
$$

where $J(x)$ is a classical source. Compute the contribution to the two-point functional derivative

$$
\frac{\delta^2 \Delta S}{\delta J(x)\delta J(y)}.
$$

What does it look like in momentum space?

<details><summary><strong>Solution</strong></summary>

Integrating by parts if desired, keep the expression as written. Varying once gives

$$
\delta\Delta S
=
\frac{c}{2M^2}\int d^d x\left[\delta J\Box J+J\Box\delta J\right]
=
\frac{c}{M^2}\int d^d x\,\delta J\Box J,
$$

after integrating by parts and dropping boundary terms. Therefore

$$
\frac{\delta\Delta S}{\delta J(x)}
=
\frac{c}{M^2}\Box J(x),
$$

and

$$
\frac{\delta^2\Delta S}{\delta J(x)\delta J(y)}
=
\frac{c}{M^2}\Box_x\delta^{(d)}(x-y).
$$

In momentum space this is a polynomial contact term proportional to

$$
-\frac{c}{M^2}p^2,
$$

up to the Fourier-sign convention. This is exactly the kind of analytic momentum dependence that local EFT operators produce.

</details>

### Exercise 2: Heavy exchange in a correlator

For the toy interaction $\mathcal L_{\text{int}}=-gH\phi^2/2$, show that the low-energy expansion of the heavy exchange contribution to the four-point function is reproduced by local four-field operators.

<details><summary><strong>Solution</strong></summary>

The heavy propagator in the $s$ channel is

$$
\frac{i}{s-M^2+i\epsilon}.
$$

At $s\ll M^2$,

$$
\frac{i}{s-M^2+i\epsilon}
=
-\frac{i}{M^2}
\left(1+\frac{s}{M^2}+O\left(\frac{s^2}{M^4}\right)\right).
$$

Multiplying by the two vertices gives a polynomial series in $s/M^2$. The leading term is reproduced by a local $\phi^4$ operator. The next term is reproduced by a derivative four-field operator such as $\phi^2\Box\phi^2$, up to integrations by parts and equations of motion. The $t$ and $u$ channels give the corresponding permutations. Thus a nonlocal resolved heavy propagator becomes a local tower when expanded at low momentum.

</details>

### Exercise 3: Why the soft part cancels

Suppose a full theory and its EFT contain the same light particles below $M$. A one-loop full-theory correlator contains a light-particle logarithm $A\log(-p^2/\mu^2)$ and a heavy local term $B\log(M^2/\mu^2)$. The EFT loop contains the same $A\log(-p^2/\mu^2)$. What remains in the matching coefficient?

<details><summary><strong>Solution</strong></summary>

The matching difference is

$$
G^{(1)}_{\text{full}}-G^{(1)}_{\text{EFT}}.
$$

The light logarithm cancels:

$$
A\log\frac{-p^2}{\mu^2}
-
A\log\frac{-p^2}{\mu^2}
=
0.
$$

The remaining short-distance term is

$$
B\log\frac{M^2}{\mu^2}
$$

plus any finite local constants and polynomial terms. These local terms determine the Wilson coefficient in the chosen scheme. If the light logarithm did not cancel, the EFT would not be reproducing the correct long-distance physics.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I and Vol. II, for renormalized Green functions, effective actions, and RG methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for generating functionals, renormalized perturbation theory, nonrenormalizable theories, and EFT examples.
- C. P. Burgess, *Introduction to Effective Field Theory*, for effective actions, Wilsonian logic, power counting, redundant interactions, and matching.
- Aneesh V. Manohar, EFT lecture notes and reviews, for practical matching, operator bases, and dimensional-regularization EFT workflows.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for correlation functions, composite operators, short-distance expansions, and RG structure.

## Version history

- 2026-06-18: First polished draft. Added source-functional matching, connected and 1PI matching, contact-term discussion, background-field viewpoint, off-shell ambiguities, gauge-theory cautions, and exercises.
