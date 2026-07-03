---
title: "Wess–Zumino Terms"
description: "Defines Wess–Zumino terms as extension-dependent topological action terms whose exponentiated action is well defined by quantized periods and whose variation is local."
sidebar:
  label: "Wess–Zumino Terms"
  order: 3
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry; Witten, Global Aspects of Current Algebra; Zee; Altland–Simons Ch. 8; standard Wess–Zumino and sigma-model references."
topics:
  - Wess Zumino terms
  - topological terms
  - sigma models
  - quantized periods
  - anomaly matching
  - Berry phases
  - extension manifolds
canonicalTopics:
  - wess-zumino-terms
  - extension-action
  - quantized-periods
  - anomaly-matching
  - sigma-model-topological-terms
researchStatus:
  established:
    - "A Wess–Zumino term is a topological action term whose variation is local on spacetime but whose definition often uses an extension of the fields to one higher dimension."
    - "The coefficient of a Wess–Zumino term is quantized when different extensions differ by closed cycles whose periods must leave the exponentiated action invariant."
  active:
    - "Modern work refines Wess–Zumino terms using global anomaly data, differential cohomology, generalized symmetries, defects, spin and Pin structures, and symmetry TFT."
---

## Summary

A Wess–Zumino term is a topological term that is local in its variation but often nonlocal in how one writes the action. The typical setup is a field

$$
\phi:X_d\longrightarrow \mathcal M,
$$

where $X_d$ is spacetime and $\mathcal M$ is a target space. Suppose $H_{d+1}$ is a closed $(d+1)$-form on $\mathcal M$ with quantized periods. Choose a $(d+1)$-manifold $B_{d+1}$ whose boundary is spacetime,

$$
\partial B_{d+1}=X_d,
$$

and extend the field to

$$
\widetilde\phi:B_{d+1}\longrightarrow \mathcal M.
$$

Then the Wess–Zumino action has the schematic form

$$
S_{\mathrm{WZ}}=k\int_{B_{d+1}}\widetilde\phi^{\,*}H_{d+1}.
$$

The punchline is that $S_{\mathrm{WZ}}$ is allowed even when there is no globally defined $d$-dimensional Lagrangian density on $X_d$. Its variation depends only on boundary data on $X_d$, and the ambiguity in choosing $B_{d+1}$ is harmless if it changes $S_{\mathrm{WZ}}$ by $2\pi\mathbb Z$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a spacetime boundary X with two possible extension manifolds B and B prime; their difference is a closed cycle whose integral quantizes the Wess–Zumino term.](/figures/symmetry-anomalies-topology/wess-zumino-extension-ambiguity.svg)

<figcaption>

A Wess–Zumino term is computed by extending the field from $X_d$ to a filling $B_{d+1}$. Two fillings differ by a closed $(d+1)$-cycle. The exponentiated action is well defined when $k\int H_{d+1}$ over every such closed cycle lies in $2\pi\mathbb Z$.

</figcaption>
</figure>

Wess–Zumino terms are the natural language for Berry phases, sigma-model topology, anomaly matching, chiral Lagrangians, and boundary actions for inflow. The next page, [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/), develops the current-algebra and chiral-symmetry version in detail.

## Prerequisites

Read [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/) first. You should be comfortable with differential forms, Stokes’ theorem, winding number, theta terms, and the idea that a quantum action is defined by $e^{iS}$, not just by $S$ modulo nothing.

You should also know the basic idea of [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/): a UV anomaly must be reproduced in the IR, sometimes by massless fields, sometimes by topological order, and sometimes by a Wess–Zumino term.

## Core idea

A Wess–Zumino term sits between three notions that students often keep separate:

$$
\text{topology}\quad +\quad \text{local variation}\quad +\quad \text{quantized quantum phase}.
$$

The action may not be the integral of an ordinary globally defined $d$-form Lagrangian on spacetime. Instead, it is defined using a closed $(d+1)$-form $H_{d+1}$ on a target or background-field space. Locally one may write

$$
H_{d+1}=dB_d,
$$

so that

$$
S_{\mathrm{WZ}}=k\int_{X_d}\phi^*B_d
$$

in one patch. But if $B_d$ is not globally defined, the globally meaningful object is the exponentiated extension integral.

The term “Wess–Zumino” is used in several nearby ways in the literature. In this chapter we use it broadly for action terms whose defining properties are:

1. the action is topological or quasi-topological;
2. the local variation is a $d$-dimensional integral over $X_d$;
3. the action is most naturally defined through an extension or patching construction;
4. quantum consistency imposes a period quantization condition.

This broad definition includes the Berry phase of a spin, the Wess–Zumino term in nonlinear sigma models, and the Wess–Zumino–Witten term for chiral Lagrangians.

## Setup and conventions

Let $X_d$ be a closed oriented spacetime for the moment. If $X_d$ has boundary, one must specify boundary conditions and possible boundary degrees of freedom separately.

Let

$$
\phi:X_d\to\mathcal M
$$

be a bosonic field valued in a target manifold $\mathcal M$. Let $H_{d+1}$ be a closed form,

$$
dH_{d+1}=0.
$$

If $\phi$ extends to $B_{d+1}$ with $\partial B_{d+1}=X_d$, define

$$
S_{\mathrm{WZ}}[\phi]=k\int_{B_{d+1}}\widetilde\phi^{\,*}H_{d+1}.
$$

The coefficient $k$ is not an arbitrary decoration. It must be chosen so that $e^{iS_{\mathrm{WZ}}}$ is independent of the extension. If $B$ and $B'$ are two choices, gluing $B$ to $-B'$ gives a closed $(d+1)$-manifold

$$
\Sigma_{d+1}=B\cup_{X_d}(-B').
$$

The ambiguity is

$$
\Delta S_{\mathrm{WZ}}
=k\int_{\Sigma_{d+1}}\widehat\phi^{\,*}H_{d+1}.
$$

The exponentiated action is well defined if

$$
\exp\left(i k\int_{\Sigma_{d+1}}\widehat\phi^{\,*}H_{d+1}\right)=1
$$

for all allowed closed cycles. Equivalently,

$$
k\int_{\Sigma_{d+1}}\widehat\phi^{\,*}H_{d+1}\in 2\pi\mathbb Z.
$$

This is the Wess–Zumino quantization condition.

:::note[Convention-sensitive source note]
Some authors absorb $2\pi$ into the normalization of $H_{d+1}$ and then say that $k\in\mathbb Z$. Others normalize $H_{d+1}$ as a differential form with ordinary geometric periods and put the $2\pi$ in the coefficient. The invariant statement is always about $e^{iS}$.
:::

## Why the variation is local

At first sight the extension formula looks suspicious: how can a $d$-dimensional QFT depend on arbitrary data in one higher dimension? The answer is that the variation with fixed boundary field depends only on $X_d$.

Let $\phi_s$ be a family of fields and let $V$ be the vector field on $\mathcal M$ generated by the variation. Using Cartan’s formula,

$$
\mathcal L_V H=i_V dH+d(i_VH)=d(i_VH),
$$

because $dH=0$. Therefore

$$
\delta S_{\mathrm{WZ}}
=k\int_{B_{d+1}}d\left(\widetilde\phi^{\,*}i_VH_{d+1}\right)
=k\int_{X_d}\phi^*(i_VH_{d+1}).
$$

So the variation is a local $d$-dimensional integral. The action needs the extension; the equations of motion and Ward-identity variation do not.

This is the main technical reason Wess–Zumino terms are allowed in local QFT. They are not arbitrary nonlocal functionals. They are globally subtle functionals with local variations.

## A zero-plus-one dimensional example: spin Berry phase

The cleanest example is a quantum spin. The classical direction of the spin is a unit vector

$$
\mathbf n(t)\in S^2.
$$

The Berry term can be written locally on $S^2$ as

$$
S_B=s\int dt\,(1-\cos\theta)\dot\varphi,
$$

in a patch that excludes the south pole. This expression uses a local monopole potential on $S^2$. Globally, the better definition uses a disk $D$ whose boundary is the time circle and an extension $\widetilde{\mathbf n}:D\to S^2$:

$$
S_B=s\int_D \widetilde{\mathbf n}^{\,*}\omega_{S^2},
$$

where

$$
\omega_{S^2}=\sin\theta\,d\theta\wedge d\varphi
$$

is the area form on the unit sphere. Two extensions differ by a map from a closed sphere to $S^2$, so

$$
\Delta S_B=s\int_{S^2}\omega_{S^2}=4\pi s
$$

for one unit of wrapping. Requiring $e^{iS_B}$ to be independent of the extension gives

$$
e^{i4\pi s}=1,
$$

or

$$
2s\in\mathbb Z.
$$

The quantization of spin is therefore visible as the Wess–Zumino quantization condition for the Berry phase.

This example is small enough to hold in one hand and deep enough to remember forever: a local vector potential is not global, the curvature is global, and the quantum phase is well defined only when the period is quantized.

## Sigma-model Wess–Zumino terms

In a nonlinear sigma model, the field is a map

$$
\phi:X_d\to\mathcal M.
$$

The ordinary kinetic term depends on a metric on $\mathcal M$:

$$
S_{\mathrm{kin}}=\frac{1}{2g^2}\int_{X_d}G_{ij}(\phi)d\phi^i\wedge *d\phi^j.
$$

A Wess–Zumino term instead depends on a closed $(d+1)$-form $H_{d+1}$ on $\mathcal M$:

$$
S_{\mathrm{WZ}}=k\int_{B_{d+1}}\widetilde\phi^{\,*}H_{d+1}.
$$

The kinetic term uses the metric and affects local propagation directly. The Wess–Zumino term uses topology and affects phases, symplectic structure, anomalies, and sometimes the statistics or quantum numbers of solitons.

For $d=2$, $H_3$ is a closed three-form on the target. Such terms are central in two-dimensional sigma models, string worldsheet actions with $B$-fields, and WZW models. For $d=4$, a five-form on a group manifold produces the Wess–Zumino–Witten term in chiral perturbation theory.

## Relation to anomalies

Wess–Zumino terms are often forced by anomaly matching. Suppose a microscopic theory has a global symmetry $G$ with an anomaly. At low energies, the symmetry is spontaneously broken,

$$
G\longrightarrow H,
$$

and the massless fields are Goldstone modes valued in $G/H$. The ordinary sigma-model kinetic term cannot reproduce an anomaly, because it is strictly invariant. A Wess–Zumino term can reproduce the anomalous variation.

The schematic statement is

$$
\delta_\lambda S_{\mathrm{WZ}}=\mathcal A_\lambda,
$$

where $\mathcal A_\lambda$ is the same anomaly functional obtained in the UV. Thus the IR Goldstone theory matches the UV anomaly even if there are no massless fermions.

This is not a small correction. In QCD-like theories, the Wess–Zumino–Witten term is responsible for anomaly-matching effects such as anomalous pion interactions. More generally, Wess–Zumino terms encode how a symmetry acts projectively, anomalously, or through inflow on the low-energy degrees of freedom.

## Wess–Zumino versus theta versus Chern–Simons

The names overlap, so it helps to compare.

| Term | Typical definition | Main global issue | Typical use |
|---|---|---|---|
| Theta term | $\theta\int_X\omega_d$ | quantized sectors on $X$ | instanton weights, CP phases |
| Wess–Zumino term | $k\int_B H_{d+1}$ with $\partial B=X$ | extension independence | Berry phases, anomaly matching |
| Chern–Simons term | $k\int_X\operatorname{CS}_{2n+1}(A)$ | large gauge transformations | topological gauge theory, response, inflow |
| Wess–Zumino–Witten term | WZ term plus symmetry/current-algebra structure | quantization and anomalous variation | chiral Lagrangians, current algebra |

A theta term is integrated over spacetime and often uses a closed top-degree form. A Wess–Zumino term is integrated over a filling. A Chern–Simons term is integrated over spacetime but is naturally a descendant of a one-higher-dimensional characteristic class. In practice these are relatives, not strangers.

## Local potentials and patching

If $H_{d+1}$ is closed, then locally one can write

$$
H_{d+1}=dB_d.
$$

In that patch,

$$
S_{\mathrm{WZ}}=k\int_{X_d}\phi^*B_d.
$$

But on overlaps of patches,

$$
B_d^{(a)}-B_d^{(b)}=d\Lambda_{d-1}^{(ab)}
$$

up to possible higher cocycle data. The local actions differ by boundary or overlap terms. The global Wess–Zumino term is the consistent way to glue these local expressions.

This is the same logic as a charged particle moving in the field of a magnetic monopole. The vector potential exists patchwise; the magnetic field is global; the wavefunction glues consistently only when the flux is quantized.

## Gauging and obstruction

If a symmetry acts on $\mathcal M$, one may ask whether the Wess–Zumino term can be coupled to background gauge fields for that symmetry. Sometimes it can, after adding background-dependent counterterms. Sometimes it cannot. Failure to gauge the Wess–Zumino term is precisely an anomaly.

Operationally, gauging asks for a background-dependent extension

$$
S_{\mathrm{WZ}}[\phi,A]
$$

such that

$$
S_{\mathrm{WZ}}[\phi^g,A^g]=S_{\mathrm{WZ}}[\phi,A]
\quad\text{mod }2\pi\mathbb Z.
$$

If no such functional exists, the symmetry has a ’t Hooft anomaly. If the variation equals a known UV anomaly, the Wess–Zumino term is doing anomaly matching rather than anomaly cancellation.

This is a common source of confusion. An anomalous variation of the IR Wess–Zumino term is not a bug; it may be exactly what is required to reproduce the UV anomaly.

## Boundaries and inflow

When $X_d$ itself has a boundary, a Wess–Zumino term requires extra care. The extension picture already used a filling $B_{d+1}$ with boundary $X_d$. If $X_d$ has a boundary, then the filling has corners, and the variation can leave uncanceled terms on $\partial X_d$.

There are several possible fates:

- impose boundary conditions that make the boundary variation vanish;
- add boundary degrees of freedom;
- add a boundary counterterm;
- interpret the theory as living on the boundary of an invertible bulk theory;
- accept that the boundary condition breaks the symmetry.

This is the same menu seen in anomaly inflow. Wess–Zumino terms often provide the low-energy boundary action required so that the combined bulk-boundary system is consistent.

## Common pitfalls

**Thinking the extension is extra physical spacetime.** The filling $B_{d+1}$ is usually an auxiliary device for defining the action. Physical observables must be independent of the choice of filling, up to $2\pi$ phases.

**Forgetting quantization.** The coefficient is not arbitrary when different extensions exist. Quantized periods are the difference between a well-defined quantum action and a multivalued expression.

**Demanding a global local Lagrangian density.** Wess–Zumino terms are local in their variation, not necessarily in the sense of a single globally defined $d$-form density.

**Confusing invariance with anomaly matching.** A Wess–Zumino term may transform anomalously under a global symmetry. That anomalous transformation can be required by ’t Hooft anomaly matching.

**Ignoring normalization conventions.** Numerical coefficients in Wess–Zumino–Witten terms depend on trace normalization and Euclidean/Lorentzian conventions. The invariant check is extension independence of $e^{iS}$ and matching of the anomaly.

## Relations to other pages

- [Total Derivatives That Matter](/symmetry-anomalies-topology/topological-terms/total-derivatives-that-matter/) gives the general warning that local exactness is not global triviality.
- [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/) specializes this page to current algebra and chiral Lagrangians.
- [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) explains why Wess–Zumino terms are often forced in the IR.
- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) gives the bulk-boundary viewpoint on anomalous variations.
- [Nonlinear Sigma Models: Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/) explains the kinetic and geometric part of sigma models; Wess–Zumino terms add topological phase data.
- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) develops another descendant-type topological action with quantized coefficient.

## Research status

The basic theory of Wess–Zumino terms, quantized periods, and anomaly matching is established. The refinements remain active because the global definition of the exponentiated action can depend on spin structures, Pin structures, torsion classes, higher-form backgrounds, finite symmetry backgrounds, defects, and global form of symmetry groups.

In modern language, Wess–Zumino terms are often part of a broader anomaly field theory or symmetry-TFT package. The old extension formula remains the best first model, but the fully global object is sometimes better described by differential cohomology, cobordism, or invertible field theory.

## Exercises

### Exercise 1: Extension independence

Let $H_{d+1}$ be closed and suppose its periods obey

$$
\int_\Sigma \widehat\phi^{\,*}H_{d+1}\in 2\pi\mathbb Z
$$

for every allowed closed $(d+1)$-cycle $\Sigma$. Show that $e^{iS_{\mathrm{WZ}}}$ is independent of the extension when $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

Let $B$ and $B'$ be two extensions. Their difference is the closed cycle

$$
\Sigma=B\cup_{X_d}(-B').
$$

The action difference is

$$
\Delta S_{\mathrm{WZ}}=k\int_\Sigma \widehat\phi^{\,*}H_{d+1}.
$$

By assumption,

$$
\int_\Sigma \widehat\phi^{\,*}H_{d+1}=2\pi n,
\qquad n\in\mathbb Z.
$$

Therefore

$$
e^{i\Delta S_{\mathrm{WZ}}}=e^{i2\pi kn}=1
$$

for integer $k$. Hence the exponentiated action does not depend on the extension.

</details>

### Exercise 2: Locality of the variation

Starting from

$$
S_{\mathrm{WZ}}=k\int_B\widetilde\phi^{\,*}H,
\qquad dH=0,
$$

show that the first variation is an integral over $X=\partial B$.

<details><summary><strong>Solution</strong></summary>

Let $V$ be the target-space vector field associated with the variation. The variation of the pulled-back form is the pullback of the Lie derivative:

$$
\delta\left(\widetilde\phi^{\,*}H\right)
=\widetilde\phi^{\,*}(\mathcal L_VH).
$$

By Cartan’s formula and $dH=0$,

$$
\mathcal L_VH=i_VdH+d(i_VH)=d(i_VH).
$$

Thus

$$
\delta S_{\mathrm{WZ}}
=k\int_B d\left(\widetilde\phi^{\,*}i_VH\right)
=k\int_{\partial B}\phi^*(i_VH).
$$

Since $\partial B=X$, the variation is local on spacetime.

</details>

### Exercise 3: Spin quantization from the Berry term

For a spin path $\mathbf n:S^1\to S^2$, define

$$
S_B=s\int_D \widetilde{\mathbf n}^{\,*}\omega_{S^2},
\qquad
\int_{S^2}\omega_{S^2}=4\pi.
$$

Show that extension independence of $e^{iS_B}$ requires $2s\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

Two disks $D$ and $D'$ filling the same loop glue to a sphere. If the glued map wraps $S^2$ once, then

$$
\Delta S_B=s\int_{S^2}\omega_{S^2}=4\pi s.
$$

Requiring

$$
e^{i\Delta S_B}=1
$$

gives

$$
e^{i4\pi s}=1.
$$

Therefore

$$
4\pi s=2\pi n,
\qquad n\in\mathbb Z,
$$

so

$$
2s=n\in\mathbb Z.
$$

This is the usual integer-or-half-integer spin quantization.

</details>

### Exercise 4: Wess–Zumino term versus theta term

Explain in one paragraph why a theta term and a Wess–Zumino term can both be topological but are not the same construction.

<details><summary><strong>Solution</strong></summary>

A theta term is usually written directly as an integral over spacetime,

$$
S_\theta=\theta\int_X\omega_d,
$$

where the integral of $\omega_d$ over $X$ gives a quantized topological charge. A Wess–Zumino term is usually written as an integral over a filling $B$ with $\partial B=X$,

$$
S_{\mathrm{WZ}}=k\int_B H_{d+1}.
$$

The theta term weights sectors of fields on spacetime. The Wess–Zumino term is defined through an extension and is consistent only when different extensions shift the action by $2\pi\mathbb Z$. They are relatives because both define topological phases, but their geometric constructions are different.

</details>

## References

- Julius Wess and Bruno Zumino, “Consequences of anomalous Ward identities,” *Physics Letters B* **37** (1971), for the original anomaly-consistency context.
- Edward Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* **223** (1983), for the global extension and quantization viewpoint on Wess–Zumino–Witten terms.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “The Uses of Instantons,” for current algebra, PCAC, and anomaly-related physical intuition.
- A. Zee, *Quantum Field Theory in a Nutshell*, for physically motivated sigma-model, anomaly, and Wess–Zumino examples.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for Wess–Zumino terms, theta terms, and Chern–Simons terms in topological matter contexts.
- C. P. Burgess, *Introduction to Effective Field Theory*, Ch. 4 and Ch. 8, for nonlinear symmetry realization and anomaly matching in EFT language.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
