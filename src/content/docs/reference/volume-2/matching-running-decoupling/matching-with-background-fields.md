---
title: "Matching with Background Fields"
description: "How background-field methods determine EFT Wilson coefficients while preserving gauge covariance, locality, and symmetry constraints."
sidebar:
  label: "Background-Field Matching"
  order: 7
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, external-field and RG methods; Schwartz 2014, effective actions and background fields; Srednicki 2007, renormalization and EFT chapters; Burgess 2020, effective actions, matching, and symmetries."
topics:
  - background-field method
  - EFT matching
  - Wilson coefficients
  - effective action
  - covariant derivative expansion
  - heat kernel
canonicalTopics:
  - background-field-matching
  - effective-action-matching
  - covariant-operator-matching
researchStatus:
  established:
    - "Background-field matching is a standard method for extracting local EFT Wilson coefficients while keeping symmetries manifest."
  active:
    - "Automated covariant matching, Hilbert-series-informed bases, evanescent operators, gauge fixing, and multi-loop threshold matching remain active technical areas."
---

## Summary

**Background-field matching** determines Wilson coefficients by comparing the full theory and the EFT in the presence of classical background fields. Instead of matching one chosen scattering process at a time, one matches a local effective action functional.

The schematic matching condition is

$$
\Gamma_{\text{full}}[B]
=
\Gamma_{\text{EFT}}[B;C_i(\mu),\mu]
+O\left(\frac{D^{N+1}}{M^{N+1}}\right),
$$

where $B$ denotes background gauge fields, metric fields, external sources, light classical fields, or any other nondynamical fields used to probe the theory. The symbol $D$ reminds us that the expansion is not only in ordinary momenta but in **covariant derivatives** and local background tensors.

Background-field matching is powerful because it keeps the local symmetry structure visible. Gauge invariance, Lorentz invariance, flavor symmetry, chiral symmetry, diffeomorphism covariance, and spurion symmetries can be preserved term by term in the local expansion. Instead of discovering gauge-invariant combinations after a pile of diagrams, one can often compute directly in a basis of gauge-covariant local operators.

The tradeoff is that the method is off shell. Off-shell functionals know about redundant operators, field redefinitions, gauge choices, and contact terms. A background-field calculation is therefore not a substitute for understanding the operator basis. It is a precise way to populate that basis.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![Background-field matching map from full theory with heavy fields through the one-loop effective action to covariant local operators and Wilson coefficients](/figures/renormalization-rg-eft/background-field-matching-map.svg)

<figcaption>

Background-field matching compares functionals rather than individual amplitudes. Heavy fields are integrated out in the presence of slowly varying backgrounds; the resulting nonlocal functional is expanded into local covariant operators whose coefficients are the EFT Wilson coefficients.

</figcaption>
</figure>

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [One-Loop Matching](/renormalization-rg-eft/matching-running-decoupling/one-loop-matching/), [Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/), and [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/).

It is also helpful to know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/).

## Core idea

A background field is a classical probe inserted into the theory. It can be a gauge field coupled to a current, a metric coupled to the stress tensor, a source coupled to a composite operator, or a slowly varying classical light field. One computes how heavy degrees of freedom respond to that probe. At distances much longer than the heavy Compton wavelength, that response must be local.

Suppose the full theory contains light fields $\phi$, heavy fields $\Phi$, and background fields $B$. The path integral is schematically

$$
e^{i\Gamma_{\text{full}}[\phi,B]}
=
\int \mathcal D\Phi\,
\exp\left(iS_{\text{full}}[\phi,\Phi,B]\right),
$$

where the integral over $\Phi$ is performed while keeping $\phi$ and $B$ fixed. For external momenta and background variations much smaller than $M$, the answer admits a local expansion,

$$
\Gamma_{\text{full}}[\phi,B]
=
\int d^d x\,
\sum_i C_i(M,\mu)\mathcal O_i(\phi,B,D)
+\text{nonlocal light-field contributions}.
$$

The EFT is built with the same light fields and backgrounds,

$$
S_{\text{EFT}}[\phi,B]
=
\int d^d x\,
\sum_i C_i(\mu)\mathcal O_i(\phi,B,D).
$$

Matching fixes $C_i(\mu)$ by requiring the two descriptions to generate the same low-energy responses to $B$.

The most compact slogan is

$$
\text{background fields turn many amplitudes into one covariant functional comparison.}
$$

## Setup and conventions

We use the mostly-minus conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). When formulas are written in Euclidean signature, the page says so explicitly. Covariant derivatives are written as $D_\mu$. Their commutator defines the field strength acting on the representation of the field being differentiated:

$$
[D_\mu,D_\nu]=iG_{\mu\nu},
$$

where $G_{\mu\nu}$ may contain gauge curvature, spin curvature, flavor background curvature, or a combination depending on context. Some books use the opposite sign convention. The physical matching coefficients are unchanged once the same convention is used consistently.

A general EFT term has the form

$$
\mathcal L_{\text{EFT}}
\supset
C_i(\mu)\mathcal O_i(\phi,B,D),
$$

where the local operator may contain:

| Ingredient | Examples |
|---|---|
| light dynamical fields | $\phi$, $\psi$, $A_\mu$ if the gauge field remains dynamical |
| background fields | external gauge fields, metric $g_{\mu\nu}$, spurions, classical sources |
| covariant derivatives | $D_\mu\phi$, $D_\mu F_{\rho\sigma}$ |
| local curvatures | $F_{\mu\nu}$, $G_{\mu\nu}$, $R_{\mu\nu\rho\sigma}$ |
| symmetry-breaking spurions | masses, Yukawa matrices, chemical potentials |

The word **background** does not mean unphysical. It means that in the calculation the field is held fixed rather than integrated over. A background electromagnetic field used to compute an Euler–Heisenberg term, a background metric used to compute curvature counterterms, and a background flavor gauge field used to track currents are all physical probes of the theory.

## Why background fields help

A diagrammatic amplitude calculation is often forced to reconstruct symmetry from components. For example, one might compute separate four-gauge-boson amplitudes with many Lorentz and group structures, then infer which gauge-invariant operators generated them.

A background-field calculation starts from the symmetry-covariant object. If the background is a gauge field, then the local expansion is built from $F_{\mu\nu}$ and $D_\mu$. If the background is a metric, it is built from curvature tensors and covariant derivatives. If a mass matrix is treated as a spurion, the expansion is organized by its transformation properties.

This is useful because matching is not just arithmetic. It is projection onto a constrained operator basis:

$$
\Gamma_{\text{local}}
=
\int d^d x\,
\left(
C_1\mathcal O_1+C_2\mathcal O_2+\cdots
\right).
$$

The background-field method makes the projection more transparent. Symmetry-forbidden terms never appear. Operators related by integration by parts, Bianchi identities, equations of motion, or field redefinitions can be identified before coefficients are quoted.

The method is especially useful for:

- gauge theories, where maintaining background gauge invariance avoids gauge-noninvariant intermediate clutter;
- gravitational EFT, where curvature invariants are more natural than graviton amplitudes for many questions;
- chiral and flavor EFTs, where external sources encode currents and Ward identities;
- universal one-loop effective actions, where functional determinants generate many Wilson coefficients at once;
- EFTs with large operator bases, where component amplitudes become a maze with tasteful lighting but still a maze.

## Backgrounds, sources, and classical fields

It is helpful to distinguish three related uses of background fields.

First, a **source** $J$ couples to an operator:

$$
S\longrightarrow S+\int d^d x\,J_a(x)\mathcal O^a(x).
$$

Functional derivatives with respect to $J$ generate correlation functions of $\mathcal O^a$.

Second, a **background gauge field** $B_\mu$ couples to a current:

$$
S\longrightarrow S+\int d^d x\,B_\mu^A(x)J_A^\mu(x)+\cdots.
$$

The ellipsis is important. If $B_\mu$ is a genuine gauge background, coupling it consistently often requires replacing ordinary derivatives by covariant derivatives, not merely adding a linear source.

Third, a **background classical light field** is a configuration of a field that remains in the EFT. One holds it fixed during the matching calculation to extract local terms in the EFT action.

These uses overlap. A background gauge field is a source for a current, but it also transforms as a connection. A background metric is a source for the stress tensor, but it also defines covariant derivatives, curvature tensors, and volume measure. The extra geometric structure is precisely why background matching is powerful.

## The functional matching equation

The cleanest statement of background-field matching uses generating functionals. Let $B$ denote all background probes and let $\phi$ denote light classical fields. The full theory gives

$$
e^{i\Gamma_{\text{full}}[\phi,B]}
=
\int \mathcal D\Phi\,
\exp\left(iS_{\text{full}}[\phi,\Phi,B]\right).
$$

The EFT gives

$$
e^{i\Gamma_{\text{EFT}}[\phi,B]}
=
\int_{\text{light loops}}\mathcal D\varphi\,
\exp\left(iS_{\text{EFT}}[\phi+\varphi,B;C_i]\right).
$$

The matching condition is

$$
\Gamma_{\text{full}}[\phi,B]
-
\Gamma_{\text{EFT loops}}[\phi,B]
=
S_{\text{EFT, local}}[\phi,B;C_i]
$$

through the desired order in $1/M$, loops, and light couplings. The left-hand side is local after the common infrared physics has been subtracted. The right-hand side is then expanded in the chosen operator basis.

At tree level this reduces to substituting the heavy classical solution. At one loop it includes functional determinants. At higher loop order it becomes more elaborate, but the logic remains the same: remove the shared low-energy part and keep the local short-distance remainder.

## Tree-level background matching

Suppose a heavy scalar $H$ of mass $M$ couples linearly to a light local source $J(\phi,B)$:

$$
\mathcal L
=\mathcal L_{\text{light}}[\phi,B]
+\frac12 H(-D^2-M^2)H
-HJ(\phi,B),
$$

where $D_\mu$ is covariant with respect to the background symmetries. The classical equation for $H$ is

$$
(-D^2-M^2)H=J.
$$

For slowly varying backgrounds,

$$
H
=-\frac{1}{M^2}\left(1-\frac{D^2}{M^2}+\frac{D^4}{M^4}-\cdots\right)J.
$$

Substituting back into the action gives the local EFT expansion

$$
\Delta\mathcal L_{\text{EFT}}
=
\frac{1}{2M^2}J^2
-
\frac{1}{2M^4}J D^2J
+
\frac{1}{2M^6}J D^4J
+\cdots,
$$

up to signs that depend on the precise Lorentzian or Euclidean quadratic-operator convention. The structure is the main point: the inverse heavy kinetic operator becomes a covariant derivative expansion.

After integration by parts, the second term can also be written as

$$
- J D^2 J
\simeq
(D_\mu J)(D^\mu J),
$$

where $\simeq$ means equality up to total derivatives and convention-dependent boundary terms. This is the background-field version of expanding a heavy propagator in powers of $p^2/M^2$.

## One-loop background matching

At one loop, integrating out a heavy field typically produces a functional determinant. For a real bosonic heavy fluctuation with quadratic operator $\Delta_H$, one obtains schematically

$$
\Delta\Gamma^{(1)}
=\frac{i}{2}\operatorname{Tr}\log \Delta_H.
$$

For a Dirac fermion,

$$
\Delta\Gamma^{(1)}
=-i\operatorname{Tr}\log \Delta_\psi,
$$

where the minus sign comes from Grassmann integration. In Euclidean signature these become the familiar determinant contributions to $S_E$ with corresponding sign changes.

The heavy operator often has the Laplace-type form

$$
\Delta_H=-D^2-M^2-U(x),
$$

where $U(x)$ is a local matrix built from light fields, background fields, and spurions. The trace log is nonlocal in general, but for background variations with $D/M\ll1$ it has a local asymptotic expansion:

$$
\operatorname{Tr}\log(-D^2-M^2-U)
\sim
\int d^d x\,
\sum_{n\ge0}\frac{1}{M^{n-d}}\,a_n(U,G_{\mu\nu},D_\mu,\ldots).
$$

The coefficients $a_n$ are local covariant invariants. In heat-kernel language they are Seeley–DeWitt coefficients. In diagram language they are the low-momentum expansion of heavy loops with background insertions.

## Heat-kernel intuition

In Euclidean signature, the determinant of a positive operator can be represented as

$$
\operatorname{Tr}\log \Delta
=-\int_0^\infty\frac{ds}{s}\operatorname{Tr}\,e^{-s\Delta}
+\text{constant}.
$$

For a heavy Laplace-type operator

$$
\Delta=-D^2+M^2+U,
$$

one expands the heat kernel at small proper time:

$$
\operatorname{Tr}\,e^{-s\Delta}
\sim
\frac{e^{-sM^2}}{(4\pi s)^{d/2}}
\int d^d x\,\operatorname{tr}\left[
1-sU+s^2\left(\frac12U^2+\frac{1}{12}G_{\mu\nu}G^{\mu\nu}+\cdots\right)+\cdots
\right].
$$

The trace `tr` is over internal indices, not spacetime integration. The ellipses include curvature terms if spacetime is curved, derivative terms such as $D^2U$, and higher local invariants.

This formula is not meant to replace careful scheme-dependent matching. Its value is conceptual: it shows why one-loop background-field matching produces a tower of local covariant operators.

## Covariant derivative expansion

The covariant derivative expansion is the background-field version of Taylor expanding in small momenta. The difference is that one never breaks covariance by replacing $D_\mu$ with an ordinary momentum too early.

A symbolic derivative expansion has the form

$$
\Delta\mathcal L_{\text{EFT}}
=
A_0M^d
+A_1M^{d-2}\operatorname{tr}U
+A_2M^{d-4}\operatorname{tr}\left(U^2,G_{\mu\nu}G^{\mu\nu},D^2U\right)
+\cdots.
$$

After integration by parts and operator-basis reduction, this becomes

$$
\Delta\mathcal L_{\text{EFT}}
=
\sum_i C_i(M,\mu)\mathcal O_i.
$$

The terms proportional to $M^d$ and $M^{d-2}$ may renormalize vacuum energy, scalar masses, or relevant operators. Terms of order $M^0$ may renormalize marginal couplings. Terms suppressed by powers of $M$ are higher-dimension EFT operators.

The hierarchy is therefore:

$$
\text{heavy determinant}
\longrightarrow
\text{covariant local invariants}
\longrightarrow
\text{basis reduction}
\longrightarrow
\text{Wilson coefficients}.
$$

## Gauge theories and background-field gauge

In a gauge theory, one often splits the gauge field into a background part and a quantum fluctuation:

$$
A_\mu=\bar A_\mu+a_\mu.
$$

The background-field method chooses gauge fixing so that the effective action remains invariant under gauge transformations of $\bar A_\mu$. A common background gauge-fixing term is schematically

$$
\mathcal L_{\text{gf}}
=-\frac{1}{2\xi}\left(\bar D^\mu a_\mu\right)^2,
$$

where $\bar D_\mu$ is covariant with respect to the background gauge field. Ghost fields and gauge fluctuations then contribute determinants whose sum is background-gauge invariant.

This is not cosmetic. Background gauge invariance constrains the effective action to be built from objects such as

$$
\operatorname{tr}\bar F_{\mu\nu}\bar F^{\mu\nu},
\qquad
\operatorname{tr}\bar F_{\mu}{}^{\nu}\bar F_{\nu}{}^{\rho}\bar F_{\rho}{}^{\mu},
\qquad
\operatorname{tr}(\bar D_\rho\bar F_{\mu\nu})(\bar D^\rho\bar F^{\mu\nu}).
$$

The quantum effective action may still depend on the gauge-fixing parameter away from physical quantities. But the background gauge symmetry organizes the answer and makes many Ward identities automatic.

## Example: heavy charged matter and gauge kinetic terms

A heavy charged field contributes to the low-energy gauge effective action. At momenta $Q\ll M$, its vacuum polarization has an expansion

$$
\Pi(q^2)
=
\Pi(0)+q^2\Pi'(0)+O\left(\frac{q^4}{M^4}\right).
$$

In background-field language, this corresponds to local terms such as

$$
\Delta\mathcal L_{\text{EFT}}
\supset
-\frac14\Delta Z_F F_{\mu\nu}F^{\mu\nu}
+\frac{c}{M^2}(\partial_\rho F_{\mu\nu})(\partial^\rho F^{\mu\nu})
+\cdots.
$$

For a non-Abelian gauge field, ordinary derivatives are replaced by covariant derivatives and the operator basis contains multiple gauge-invariant structures. The coefficient $\Delta Z_F$ is a threshold correction to the gauge coupling. The higher-derivative terms encode the finite-size low-energy response of the heavy charged field.

One can compute the same information from two-point amplitudes, but the background-field result makes gauge covariance visible from the start.

## Example: Euler–Heisenberg as background matching

Consider QED with a heavy electron and photons at energies $Q\ll m_e$. Integrating out the electron gives a photon EFT. The one-loop effective action in a slowly varying electromagnetic background contains

$$
\Delta\mathcal L
\sim
\frac{\alpha^2}{m_e^4}
\left[
(F_{\mu\nu}F^{\mu\nu})^2
+\text{constant}\times(F_{\mu\nu}\widetilde F^{\mu\nu})^2
\right]
+\cdots,
$$

where the precise numerical constants depend on spin and normalization conventions. This is the Euler–Heisenberg interaction. It describes low-energy light-by-light scattering without keeping the electron as a dynamical degree of freedom.

The calculation can be performed by matching four-photon amplitudes. But the background-field computation packages all helicity components into the two Lorentz invariants

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

That packaging is the point of the method.

## Example: external sources in chiral EFT

In chiral perturbation theory, one often introduces external left and right gauge fields $l_\mu$ and $r_\mu$, scalar sources $s$, and pseudoscalar sources $p$. These sources couple to QCD currents and densities. The effective action is built to reproduce the same current correlation functions and Ward identities.

The source fields are then set to physical values. For example, quark masses are included by assigning a background value to the scalar spurion. Electromagnetic interactions are included by choosing appropriate components of $l_\mu$ and $r_\mu$.

This strategy is not a trick for chiral EFT alone. It is a general EFT lesson:

$$
\text{sources expose symmetry constraints on operator coefficients.}
$$

By making the sources transform under the symmetry, one writes the most general EFT action that formally respects the symmetry. Setting the sources to their physical values then implements explicit breaking in a controlled way.

## Matching local functionals versus matching observables

Background-field matching often determines a local functional, not directly a single observable. This has two consequences.

First, it can determine many observables at once. Once the coefficient of $F^4/M^4$ is known, it contributes to photon scattering in any kinematic channel compatible with the EFT.

Second, it can determine coefficients of operators that vanish on shell or appear only in contact terms. Whether those coefficients are physically meaningful depends on the question. Off-shell Green functions can depend on field parametrization, but the $S$-matrix cannot. A background-field result must therefore be reduced to a physical operator basis if the goal is an observable prediction.

The safe workflow is:

$$
\text{compute local functional}
\longrightarrow
\text{reduce by identities and field redefinitions}
\longrightarrow
\text{quote basis-dependent coefficients}
\longrightarrow
\text{check basis-independent observables}.
$$

## Infrared subtraction

If light fields appear in loops, the full theory and EFT share infrared behavior. The background-field method does not eliminate this issue. Matching coefficients are short-distance quantities, so common long-distance contributions must cancel or be subtracted.

At one loop, a typical matching statement is

$$
\Gamma_{\text{match}}^{(1)}
=
\Gamma_{\text{full}}^{(1)}
-
\Gamma_{\text{EFT, light}}^{(1)}.
$$

Only the difference should be projected onto Wilson coefficients. If one takes the full-theory determinant and calls every term a Wilson coefficient, one may accidentally include low-energy logarithms that should instead be generated by EFT loops and RG evolution.

This is especially important in massless theories. Background fields can make calculations elegant, but they do not repeal infrared physics. Cute notation, sadly, has no jurisdiction over soft divergences.

## Operator bases and projection

A background-field calculation usually produces expressions that are not yet in the final operator basis. The reduction step may use:

| Redundancy or identity | What it does |
|---|---|
| integration by parts | moves derivatives between factors |
| Bianchi identities | relates derivative and curvature structures |
| algebraic identities | reduces Lorentz, gauge, or flavor tensors |
| equations of motion | removes redundant directions for on-shell observables |
| field redefinitions | changes coordinates on EFT theory space |
| Fierz identities | reduces fermion operator structures |
| evanescent identities | require care away from integer dimension |

Projection can be done by comparing coefficients of independent background invariants, by evaluating the functional on special backgrounds, or by computing selected amplitudes as checks.

A good background-field matching page or paper should say which basis is used. It should not leave the reader to guess whether, for example, $D_\mu F^{\mu\nu}$ operators were removed by equations of motion or retained as off-shell source operators.

## Background fields and anomalies

Background fields are also the cleanest way to state many anomalies. If a global symmetry is coupled to a background gauge field, an anomaly appears as an obstruction to making the generating functional invariant under background gauge transformations:

$$
Z[B^g]\neq Z[B].
$$

For ordinary EFT matching, anomaly matching means that the low-energy theory must reproduce the same anomalous variation as the high-energy theory. Sometimes this requires Wess–Zumino terms or topological terms in the EFT.

This page does not develop anomaly theory, but the warning is important: when background fields are used for anomalous symmetries, the effective action may not be strictly invariant. The anomaly is not a mistake in the matching. It is part of what must be matched.

## Background-field matching versus amplitude matching

Background-field matching and amplitude matching are not rivals. They are two projections of the same low-energy equality.

| Method | Natural output | Strength | Caveat |
|---|---|---|---|
| background-field matching | local effective action | preserves covariance and symmetries | off-shell redundancies must be handled |
| correlation-function matching | Green functions and sources | sees contact terms and current insertions | can be gauge- and basis-sensitive |
| S-matrix matching | on-shell amplitudes | focuses on physical scattering data | can miss off-shell/source operators |

A mature EFT calculation often uses more than one method. Background fields produce covariant coefficients; on-shell amplitudes check physical combinations; source correlators verify contact terms and Ward identities.

## A practical checklist

A background-field matching calculation should specify:

1. the full-theory fields and the heavy fields being integrated out;
2. the light fields and background probes retained in the EFT;
3. the gauge fixing for quantum fluctuations, if any;
4. the renormalization scheme and matching scale;
5. the operator basis and redundancy conventions;
6. whether EFT light loops are included or subtracted;
7. how infrared singularities are regulated;
8. how anomalies and symmetry-breaking spurions are treated;
9. how the resulting Wilson coefficients are checked.

The actual algebra may be complicated, but the conceptual contract is simple: same low-energy generating functional, same symmetry response, same local Wilson coefficients after reduction.

## Common pitfalls

**Confusing background fields with external particles.** A background field is a probe in a functional. External particles are asymptotic states. The two are related, but they are not the same object.

**Forgetting EFT loop subtraction.** A full-theory loop contains both short-distance and long-distance information. Matching coefficients should capture only the short-distance part not reproduced by EFT loops.

**Treating off-shell coefficients as observables.** Background-field effective actions depend on field definitions and basis choices. Physical observables do not.

**Breaking gauge covariance during projection.** Expanding in ordinary derivatives and momenta can hide gauge covariance. If the final answer is gauge invariant but the intermediate projection is not, mistakes become easier.

**Ignoring contact terms.** Background sources generate contact terms in correlators. Some are scheme dependent; some are required by Ward identities. Do not throw them away on vibes.

**Quoting a coefficient without a basis.** A Wilson coefficient has meaning only after the operator normalization, redundancy conventions, and scheme are stated.

**Assuming every background symmetry is anomaly free.** An anomalous background variation can be the very thing the EFT must reproduce.

## Relations to other pages

[Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/) explains the source-functional version of matching. [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/) explains the on-shell projection. This page sits between them: it treats background fields as a covariant way to organize local functionals.

[Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/) and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/) explain why off-shell functionals contain basis-dependent directions. [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/) explains how coefficients obtained by background-field matching are evolved to lower scales.

Later gauge-theory and anomaly pages will use background fields systematically to track Ward identities, background gauge invariance, anomaly inflow, and threshold corrections.

## Research status

Background-field matching is established technology. The background-field method, heat-kernel expansion, covariant derivative expansion, and functional determinant methods are standard tools in QFT and EFT.

Active work continues in making the method systematic and automated for large EFT bases, gauge theories with spontaneous symmetry breaking, multi-loop matching, evanescent operators, curved backgrounds, SMEFT and HEFT matching, and simultaneous matching plus running in theories with many thresholds.

The conceptual status is not speculative: background-field matching is just functional matching with carefully chosen probes. The hard part is not believing the method. The hard part is doing it without losing a minus sign, a redundancy, or a scheme convention in the couch cushions.

## Exercises

### Exercise 1: Tree-level covariant expansion

Let a heavy real scalar $H$ have quadratic operator $-D^2-M^2$ and linear coupling $-HJ$, where $J$ is a background-covariant local expression built from light fields. Solve the classical equation for $H$ as an expansion in $D^2/M^2$ and find the first two local EFT terms.

<details><summary><strong>Solution</strong></summary>

The equation is

$$
(-D^2-M^2)H=J.
$$

Formally,

$$
H=-(M^2+D^2)^{-1}J.
$$

For $D^2/M^2\ll1$,

$$
(M^2+D^2)^{-1}
=\frac1{M^2}\left(1-\frac{D^2}{M^2}+\frac{D^4}{M^4}-\cdots\right).
$$

Thus

$$
H=-\frac{J}{M^2}+\frac{D^2J}{M^4}+O(M^{-6}).
$$

Substituting back gives, up to the sign convention for the original quadratic term,

$$
\Delta\mathcal L_{\text{EFT}}
=\frac{1}{2M^2}J^2-\frac{1}{2M^4}J D^2J+O(M^{-6}).
$$

After integration by parts, the second term can be written as a derivative operator built from $D_\mu J$.

</details>

### Exercise 2: Why the determinant is local at low energy

Explain why a one-loop determinant of a massive field can be expanded in local operators at external momenta $Q\ll M$.

<details><summary><strong>Solution</strong></summary>

Massive propagators have denominators of the form $k^2-M^2$ or, after Wick rotation, $k_E^2+M^2$. If all external momenta and background variations are small compared with $M$, loop integrals are analytic in those external momenta around zero, up to infrared effects from light fields. Analytic dependence in momentum space corresponds to derivatives of delta functions in position space, hence to local operators.

Equivalently, in the heat-kernel representation, the factor $e^{-sM^2}$ suppresses large proper time. The small-$s$ expansion is an expansion in local invariants built from $U$, $G_{\mu\nu}$, covariant derivatives, and curvature. This is the local EFT expansion.

</details>

### Exercise 3: Background gauge covariance

Suppose a non-Abelian gauge field is split as $A_\mu=\bar A_\mu+a_\mu$. Why is a gauge-fixing term of the form $(\bar D^\mu a_\mu)^2$ useful for matching?

<details><summary><strong>Solution</strong></summary>

The derivative $\bar D_\mu$ is covariant with respect to the background gauge field. A gauge-fixing term built from $\bar D^\mu a_\mu$ fixes the quantum fluctuation while preserving covariance under background gauge transformations. As a result, the effective action for $\bar A_\mu$ is organized in background-gauge-invariant operators such as $\operatorname{tr}\bar F_{\mu\nu}\bar F^{\mu\nu}$ and covariant higher-derivative terms. This greatly simplifies the projection onto a gauge-invariant EFT basis.

</details>

### Exercise 4: Off-shell ambiguity

Why can two background-field effective actions differ by an operator proportional to the light-field equation of motion while giving the same ordinary on-shell amplitudes?

<details><summary><strong>Solution</strong></summary>

An operator proportional to the classical equation of motion can be generated or removed by a local field redefinition. Local field redefinitions change off-shell Green functions and the form of the Lagrangian, but they leave the ordinary $S$-matrix invariant when the usual assumptions about locality and invertibility hold. Therefore a background-field effective action, which is off shell, can contain basis-dependent EOM operators even though physical on-shell amplitudes depend only on equivalence classes of operators modulo field redefinitions.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the chapters on external-field methods and renormalization group methods.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on effective actions, background fields, renormalization, and EFT.
- Mark Srednicki, *Quantum Field Theory*, especially the renormalization, RG, and EFT sections.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, matching, power counting, symmetries, and redundant interactions.
- Sidney Coleman, *Aspects of Symmetry*, especially the lectures on renormalization, symmetry, and functional methods.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, background fields, composite operators, and RG organization.

## Version history

- 2026-06-18: First polished draft. Added background-field functional matching, tree-level covariant expansion, one-loop determinant logic, heat-kernel intuition, gauge-theory caveats, anomaly warning, exercises, and figure.
