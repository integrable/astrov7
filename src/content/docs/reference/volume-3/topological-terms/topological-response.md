---
title: "Topological Response"
description: "Explains how background topological terms encode universal response, anomaly inflow, edge physics, and quantized transport in gapped quantum field theories and phases of matter."
sidebar:
  label: "Topological Response"
  order: 7
level: Advanced
status: "Polished draft"
source: "Chern–Simons and theta-response literature; Wen; Witten; Qi–Hughes–Zhang; Gaiotto–Kapustin–Seiberg–Willett; Altland–Simons Ch. 8; standard SPT and anomaly-inflow references."
topics:
  - topological response
  - background fields
  - quantum Hall response
  - theta response
  - BF response
  - anomaly inflow
  - symmetry protected phases
canonicalTopics:
  - topological-response
  - background-effective-action
  - quantum-hall-response
  - theta-response
  - anomaly-inflow
  - spt-response
researchStatus:
  established:
    - "Topological response terms in background fields encode robust, often quantized, low-energy response data of gapped phases and QFTs."
    - "Boundary variation of a bulk topological response action is the standard anomaly-inflow explanation for anomalous edge or boundary theories."
  active:
    - "Modern refinements include interacting crystalline response, higher-form and non-invertible symmetry response, spin/Pin and cobordism classifications, torsion responses, and nonperturbative boundary classifications."
---

## Summary

A topological response action is the part of a low-energy generating functional that depends on background fields only through global, metric-independent, or quantized topological data. If a gapped QFT is coupled to nondynamical background fields $A$, $g_{\mu\nu}$, spin connection $\omega$, higher-form backgrounds, or crystalline/geometric backgrounds, then at energies far below the gap its generating functional often has a piece

$$
Z[A,g,\ldots]
\approx
\exp\left(iW_{\mathrm{top}}[A,g,\ldots]\right)
\times
\text{nonuniversal local terms}.
$$

The topological part $W_{\mathrm{top}}$ encodes robust response: Hall conductivity, magnetoelectric response, mixed symmetry response, anomaly inflow, edge anomalies, and sometimes the invertible topological phase represented by the bulk.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing a gapped QFT coupled to background fields, integration of massive modes, a topological response functional, functional derivatives giving currents, examples including Chern–Simons Hall response, theta response, BF response, and boundary anomaly inflow.](/figures/symmetry-anomalies-topology/topological-response-flow.svg)

<figcaption>

Topological response is read from the background-field generating functional. Varying $W_{\mathrm{top}}$ gives currents and response coefficients; checking large gauge transformations and boundaries reveals quantization and anomaly inflow.

</figcaption>
</figure>

The word “response” is doing work. The background fields are probes. They are not summed over unless one decides to gauge the corresponding symmetry. A response term says how the QFT reacts to a background, not that the background has become dynamical.

## Prerequisites

Read [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/), [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/), and [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) first.

It is also useful to know [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/), because topological response and anomaly inflow are two sides of the same background-field coin.

## Core idea

A gapped theory has no low-energy propagating modes in the bulk. That does not mean its low-energy generating functional is zero. It can still contain local background terms. The most robust ones are topological.

The prototype is the three-dimensional Chern–Simons response to a background $U(1)$ field:

$$
W_{\mathrm{top}}[A]=\frac{\nu}{4\pi}\int_{M_3}A\wedge dA.
$$

Varying this response gives

$$
J=\frac{\delta W_{\mathrm{top}}}{\delta A}
\quad\Longrightarrow\quad
j^\mu=\frac{\nu}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

Thus an electric field produces a transverse current. In units with $e=\hbar=1$, this is the Hall response. The coefficient $\nu$ is not just another Taylor-series coefficient. On a closed manifold and for properly normalized compact backgrounds, large gauge transformations quantize or otherwise constrain it.

The general pattern is

$$
\text{gapped phase} + \text{background fields}
\quad\leadsto\quad
\text{topological action for backgrounds}.
$$

Topological response therefore turns symmetry and topology into measurable transport, boundary anomalies, and robust phases.

## Setup and conventions

Let $\mathcal T$ be a QFT with a global symmetry. Couple it to background fields collectively denoted $\mathcal A$. These may include:

$$
\mathcal A=(A_1,B_2,g_{\mu\nu},\omega,\ldots),
$$

where $A_1$ is an ordinary background gauge field, $B_2$ is a higher-form background, $g_{\mu\nu}$ is the metric, and $\omega$ is the spin connection.

The generating functional is

$$
Z[\mathcal A]=e^{iW[\mathcal A]}.
$$

A current is obtained by functional differentiation. For an ordinary $U(1)$ background field,

$$
\delta W[A]=\int d^dx\, J^\mu\delta A_\mu.
$$

In differential-form notation, if $A$ is a one-form and $J$ is the Hodge-dual current $(d-1)$-form, then

$$
\delta W[A]=\int \delta A\wedge *J.
$$

The topological response is the part of $W$ that remains meaningful after ignoring nonuniversal, symmetry-allowed local terms suppressed by the gap or dependent on microscopic details.

:::note[Convention-sensitive source note]
This page uses Lorentzian phases $e^{iW}$ and mostly-minus spacetime conventions inherited from the volume. In Euclidean condensed-matter references, the same response terms are often written in the Euclidean effective action with extra factors of $i$. The quantized coefficient and variation are the invariant content.
:::

## Background response versus dynamical gauge theory

A response action is a functional of background fields. It is not automatically a gauge theory. The distinction is:

$$
\begin{array}{c|c|c}
\text{background response} & \text{dynamical gauge theory} & \text{operation} \\
\hline
Z[A] & \int \mathcal D A\,Z[A] & \text{sum over }A\text{ only in the second case} \\
\text{probe symmetry} & \text{gauge symmetry/redundancy} & \text{different operator algebra} \\
\text{currents from }\delta W/\delta A & \text{Gauss law constraints} & \text{different Hilbert space}
\end{array}
$$

This distinction prevents a common confusion. The same Chern–Simons expression

$$
\frac{k}{4\pi}\int A\wedge dA
$$

can be:

1. a background response term for a global $U(1)$ symmetry, or
2. a dynamical Chern–Simons gauge theory.

The formula is the same. The theory is not.

## Hall response from a Chern–Simons term

In $2+1$ dimensions, a background electromagnetic field $A$ can appear through

$$
W_{\mathrm{Hall}}[A]
=\frac{\nu}{4\pi}\int_{M_3}A\wedge dA.
$$

In components,

$$
W_{\mathrm{Hall}}
=\frac{\nu}{8\pi}\int d^3x\,\epsilon^{\mu\nu\rho}A_\mu F_{\nu\rho}.
$$

Varying gives

$$
\delta W_{\mathrm{Hall}}
=\frac{\nu}{2\pi}\int \delta A\wedge dA,
$$

so

$$
J=\frac{\nu}{2\pi}dA.
$$

In components,

$$
j^\mu=\frac{\nu}{4\pi}\epsilon^{\mu\nu\rho}F_{\nu\rho}
=\frac{\nu}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

Taking spatial components with $E_j=F_{j0}$ gives a transverse current:

$$
j^i=\frac{\nu}{2\pi}\epsilon^{ij}E_j.
$$

Restoring ordinary units gives

$$
\sigma_{xy}=\nu\frac{e^2}{h}.
$$

For an integer quantum Hall state, $\nu\in\mathbb Z$. For a fractional quantum Hall state, the response to the external background can have fractional $\nu$, but the full low-energy theory usually includes internal dynamical Chern–Simons gauge fields. The background response alone does not contain all anyon data.

## K-matrix response

A useful abelian topological order in $2+1$ dimensions has internal dynamical gauge fields $a^I$ and background electromagnetic field $A$:

$$
S[a,A]
=\frac{1}{4\pi}\int K_{IJ}a^I\wedge da^J
+\frac{1}{2\pi}\int q_I A\wedge da^I.
$$

Here $K$ is an integral symmetric matrix and $q_I$ is an integer charge vector. Integrating out the internal fields at long distances gives the electromagnetic response

$$
W_{\mathrm{eff}}[A]
=\frac{\nu}{4\pi}\int A\wedge dA,
\qquad
\nu=q^T K^{-1}q.
$$

This formula is a workhorse. It also teaches a conceptual lesson: the observable Hall response $\nu$ is only one piece of the topological data. The full $K$-matrix also knows quasiparticle charges, braiding, ground-state degeneracy, and which line operators are local.

## Theta response in four dimensions

In $3+1$ dimensions, the electromagnetic theta response is

$$
W_\theta[A]
=\frac{\theta}{8\pi^2}\int_{M_4}F\wedge F,
\qquad
F=dA.
$$

Locally,

$$
F\wedge F=d(A\wedge dA)
$$

for an abelian gauge field. On a closed manifold, the integral is controlled by global flux sectors. On a manifold with boundary or an interface where $\theta$ changes, it reduces to a Chern–Simons response on the boundary:

$$
\frac{\theta}{8\pi^2}\int_{M_4}F\wedge F
=\frac{\theta}{8\pi^2}\int_{\partial M_4}A\wedge dA
$$

when $\theta$ is constant and the bundle is trivial enough for this expression to be written globally.

If time reversal or parity sends

$$
F\wedge F\longmapsto -F\wedge F,
$$

then $\theta$ is sent to $-\theta$. With periodicity $\theta\sim\theta+2\pi$, the symmetry-preserving values are often

$$
\theta=0,
\pi
\quad\operatorname{mod}2\pi,
$$

subject to global and spin-structure caveats. This is the field-theoretic backbone of magnetoelectric response in three-dimensional topological insulators.

:::note[Source note]
The coefficient of the electromagnetic theta term is convention-sensitive because authors distribute factors of $e$, $2\pi$, and $1/2$ differently between $F\wedge F$, $F_{\mu\nu}\widetilde F^{\mu\nu}$, and the definition of minimal electric charge. The normalization here is adapted to compact $U(1)$ backgrounds with minimal charge one.
:::

## BF response

BF terms can also be response terms. For example, suppose $A_1$ and $B_2$ are background fields for ordinary and one-form symmetries in four dimensions. A response term

$$
W_{\mathrm{BF}}[A,B]
=\frac{k}{2\pi}\int_{M_4}B_2\wedge dA_1
$$

encodes a mixed response between particle-like and string-like probes. Varying with respect to $A$ and $B$ gives dual currents:

$$
\delta W_{\mathrm{BF}}
=\frac{k}{2\pi}\int \delta B\wedge dA
-\frac{k}{2\pi}\int dB\wedge\delta A
+\text{boundary term}.
$$

Thus the current sourced by one background is the field strength of the other. This is the response-action version of the linking-pairing story in [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/).

When $A$ and $B$ are dynamical instead, the same term defines a BF topological gauge theory. Again, background versus dynamical is not a footnote. It is the definition of the problem.

## Gravitational and thermal response

Topological response is not only electromagnetic. In $2+1$ dimensions, a gravitational Chern–Simons term has the schematic form

$$
W_{\mathrm{grav}}[\omega]
=\frac{c}{96\pi}\int \operatorname{tr}\left(\omega\wedge d\omega+\frac{2}{3}\omega\wedge\omega\wedge\omega\right),
$$

where $\omega$ is the spin connection and $c$ is related to the chiral central charge of boundary modes.

This term is subtler than the electromagnetic Chern–Simons response. It depends on framing and gravitational background data, and its coefficient is constrained by the global definition of the theory. Physically, it is tied to thermal Hall response and edge energy transport.

The warning label is worth keeping on the bottle: gravitational response coefficients can be harder to read directly from local Lagrangians than electromagnetic ones. They often require careful treatment of spin structure, framing, boundary conditions, and contact terms in stress-tensor correlators.

## Response, SPT phases, and invertible field theories

For a symmetry-protected topological phase, the bulk has no intrinsic topological order, but its background-field response is nontrivial. In modern language, an SPT phase is often represented at low energy by an invertible topological field theory depending on background fields.

Stacking phases corresponds to adding response actions:

$$
W_{\mathrm{top}}^{(1\oplus 2)}[\mathcal A]
= W_{\mathrm{top}}^{(1)}[\mathcal A]+W_{\mathrm{top}}^{(2)}[\mathcal A]
\quad\operatorname{mod}2\pi.
$$

A trivial phase has a response action removable by a local counterterm compatible with the symmetry and global definition. A nontrivial SPT response cannot be removed without either breaking the symmetry or changing the allowed background dependence.

This is the bridge to anomaly inflow. The boundary of a nontrivial SPT phase cannot generally be a standalone trivial symmetric gapped theory. It must realize the boundary anomaly somehow: gapless modes, symmetry breaking, topological order, or a relative boundary condition.

## Boundary variation and anomaly inflow

Consider the Chern–Simons response on a three-manifold with boundary:

$$
W[A]=\frac{\nu}{4\pi}\int_{M_3}A\wedge dA.
$$

Under a background gauge transformation $A\mapsto A+d\lambda$,

$$
\delta_\lambda W
=\frac{\nu}{4\pi}\int_{M_3}d\lambda\wedge dA
=\frac{\nu}{4\pi}\int_{\partial M_3}\lambda\,dA.
$$

Thus the bulk response is not gauge invariant by itself on a manifold with boundary. This is not a failure of the bulk. It is a prediction: the boundary theory must have an anomalous variation canceling this term, or the boundary condition must remove the variation.

This is anomaly inflow in its simplest response-theory form:

$$
\delta W_{\mathrm{bulk}}+\delta W_{\mathrm{boundary}}=0.
$$

The same logic applies to theta terms, BF terms, gravitational Chern–Simons terms, and higher-form response actions.

## Counterterms and scheme dependence

A response action is defined modulo local counterterms. This matters. Suppose the generating functional contains

$$
W[A]=\frac{\nu}{4\pi}\int A\wedge dA+\cdots.
$$

If the counterterm

$$
\frac{n}{4\pi}\int A\wedge dA
$$

is allowed, then $\nu$ is only meaningful modulo $n$ in the corresponding classification. If the counterterm is forbidden by time reversal, spin structure, microscopic charge assignments, or boundary conditions, then the same coefficient may become a sharper invariant.

This is why response classifications are never only local differential-form classifications. One must specify:

1. the symmetry group and its global form;
2. the allowed background bundles;
3. whether spacetime is oriented, spin, spin${}_c$, Pin, or something else;
4. which local counterterms are allowed;
5. whether the system has a boundary;
6. whether the response is required to be bosonic or fermionic.

The phrase “topological response” is compact, but the data behind it are not small.

## Quantization and large transformations

Topological response coefficients are often quantized because the exponentiated generating functional must be well defined:

$$
e^{iW_{\mathrm{top}}[\mathcal A]}.
$$

If a large gauge transformation changes the response action by

$$
\Delta W_{\mathrm{top}}=2\pi n\alpha,
\qquad n\in\mathbb Z,
$$

then gauge invariance requires

$$
e^{i\Delta W_{\mathrm{top}}}=1.
$$

This gives a quantization condition on $\alpha$.

However, quantization can look different in different contexts. Integer quantum Hall response has an integer coefficient for a bosonic or fermionic system with appropriate microscopic charge normalization. Fractional quantum Hall response can have fractional electromagnetic response because the low-energy theory includes internal topological order. Fermionic SPT phases can have response terms that are well defined only on spin or spin${}_c$ manifolds.

The practical rule is:

$$
\text{do the large-transformation check on the actual background fields of the actual theory.}
$$

Do not infer global quantization from a locally similar formula in a different theory.

## Topological response versus topological order

Topological response is not the same thing as topological order.

An invertible SPT phase can have a nontrivial topological response but no intrinsic topological order. It has a unique ground state on closed spatial manifolds, up to short-distance details, and no anyons in the bulk.

A topologically ordered phase has additional long-range entanglement data: nontrivial anyons or extended excitations, ground-state degeneracy on nontrivial manifolds, and a nontrivial algebra of line or surface operators. Its response to background fields is important, but not complete.

For example, the electromagnetic response

$$
\frac{\nu}{4\pi}\int A\wedge dA
$$

does not by itself determine the full fractional quantum Hall order. Different $K$-matrices can sometimes share the same filling fraction $\nu$ but differ in quasiparticle braiding.

A response action is a shadow. Sometimes the shadow is enough to identify the object. Sometimes it is not.

## Common pitfalls

**“The background field is dynamical because it appears in an action.”** No. A background-field action is part of the generating functional. It becomes dynamical only if the path integral sums over it.

**“The Hall coefficient is just a local contact term.”** It is a local term, but large gauge transformations and boundaries can make its coefficient quantized and physically measurable. Local does not mean unphysical.

**“A response term completely classifies a phase.”** It classifies some robust response data. It may miss intrinsic topological order, symmetry fractionalization, non-invertible defect data, or boundary possibilities.

**“If the bulk is gapped, the boundary can always be trivially gapped.”** Not when the bulk response has a nontrivial boundary variation and the symmetry is preserved. The boundary must match the anomaly.

**“Fractional coefficients violate quantization.”** Fractional response can be consistent when internal dynamical topological fields are included, or when the background normalization differs. The complete theory must still be gauge invariant.

**“Topological response is always metric independent.”** Many famous terms are metric independent, but gravitational response uses geometric data and can depend on framing or spin structure. The robust part is topological in a refined sense.

## Relations to other pages

- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) gives the main three-dimensional response example.
- [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/) explains the instanton-sector and magnetoelectric prototype.
- [BF Theory Terms](/symmetry-anomalies-topology/topological-terms/bf-theory-terms/) gives the higher-form and finite-gauge response language.
- [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/) explains the SPT/anomaly dictionary.
- [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) develops the generalized-background version of response.
- [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) later packages response and anomaly data as bulk topological theories.

## Research status

The basic response actions for integer quantum Hall states, Chern–Simons theories, theta terms, BF theories, gravitational Chern–Simons terms, and many SPT phases are established. They are standard tools in high-energy theory, condensed matter, and mathematical physics.

The frontier is the global classification and boundary realization problem. Interactions, fermions, crystalline symmetries, non-invertible symmetries, subsystem symmetries, torsion backgrounds, and generalized higher-form backgrounds can all refine the naive differential-form answer. The modern slogan is not merely “write all topological terms.” It is “write all well-defined invertible background field theories, modulo allowed counterterms.” That is a harder and more interesting problem.

## Exercises

### Exercise 1: Hall current from Chern–Simons response

Let

$$
W[A]=\frac{\nu}{4\pi}\int A\wedge dA
$$

on a closed three-manifold. Show that

$$
J=\frac{\nu}{2\pi}dA
$$

in differential-form notation.

<details><summary><strong>Solution</strong></summary>

Vary the action:

$$
\delta W=\frac{\nu}{4\pi}\int \delta A\wedge dA
+\frac{\nu}{4\pi}\int A\wedge d\delta A.
$$

On a closed manifold,

$$
\int A\wedge d\delta A=\int \delta A\wedge dA,
$$

up to the total derivative $d(A\wedge\delta A)$. Hence

$$
\delta W=\frac{\nu}{2\pi}\int \delta A\wedge dA.
$$

Comparing with $\delta W=\int \delta A\wedge *J$ gives

$$
*J=\frac{\nu}{2\pi}dA.
$$

Equivalently, with the current represented by its dual form, $J=\frac{\nu}{2\pi}dA$.

</details>

### Exercise 2: Boundary variation of Chern–Simons response

Under $A\mapsto A+d\lambda$, show that

$$
W[A]=\frac{\nu}{4\pi}\int_{M_3}A\wedge dA
$$

changes by a boundary term if $M_3$ has boundary.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta_\lambda W
=\frac{\nu}{4\pi}\int_{M_3}d\lambda\wedge dA.
$$

Since $d^2A=0$,

$$
d\lambda\wedge dA=d(\lambda dA).
$$

Therefore

$$
\delta_\lambda W
=\frac{\nu}{4\pi}\int_{\partial M_3}\lambda dA.
$$

This boundary variation must be canceled by boundary degrees of freedom, removed by boundary conditions, or interpreted as anomaly inflow.

</details>

### Exercise 3: K-matrix filling fraction

For

$$
S[a,A]
=\frac{1}{4\pi}\int K_{IJ}a^I\wedge da^J
+\frac{1}{2\pi}\int q_I A\wedge da^I,
$$

show formally that integrating out $a^I$ gives

$$
\nu=q^T K^{-1}q.
$$

Ignore boundary terms and assume $K$ is invertible.

<details><summary><strong>Solution</strong></summary>

Varying with respect to $a^I$ gives

$$
K_{IJ}da^J+q_I dA=0.
$$

Thus

$$
da^I=-(K^{-1})^{IJ}q_J dA.
$$

At the level of the quadratic action, integrating out $a$ gives the effective background Chern–Simons term

$$
W_{\mathrm{eff}}[A]
=\frac{1}{4\pi}q_I(K^{-1})^{IJ}q_J\int A\wedge dA.
$$

Therefore

$$
\nu=q^T K^{-1}q.
$$

The sign depends on the convention for the source coupling and the orientation convention; the physical response uses one consistent convention throughout.

</details>

### Exercise 4: Theta term at an interface

Let $\theta$ jump from $0$ to $\pi$ across a three-dimensional interface. Explain why the four-dimensional response

$$
\frac{1}{8\pi^2}\int \theta F\wedge F
$$

induces a Chern–Simons-like term on the interface.

<details><summary><strong>Solution</strong></summary>

Locally, for an abelian gauge field,

$$
F\wedge F=d(A\wedge dA).
$$

If $\theta$ is piecewise constant, integration by parts gives an interface contribution where $d\theta$ is localized:

$$
\frac{1}{8\pi^2}\int \theta d(A\wedge dA)
=-\frac{1}{8\pi^2}\int d\theta\wedge A\wedge dA
$$

up to exterior boundary terms. If $\theta$ jumps by $\Delta\theta=\pi$, the interface carries a term proportional to

$$
\frac{\Delta\theta}{8\pi^2}\int_{\text{interface}}A\wedge dA.
$$

This is a half-level Chern–Simons-like response in the minimal normalization. Its standalone meaning depends on spin structure and boundary degrees of freedom; in a full topological-insulator setup it is completed by the anomalous surface theory.

</details>

## References

- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for topological orders, Chern–Simons response, and $K$-matrix theory.
- Edward Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989), for Chern–Simons theory as a TQFT.
- X.-L. Qi, T. L. Hughes, and S.-C. Zhang, “Topological Field Theory of Time-Reversal Invariant Insulators,” *Physical Review B* **78** (2008), for electromagnetic theta response in topological insulators.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015**, for background fields, higher-form symmetries, and anomaly/response language.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for theta, Wess–Zumino, and Chern–Simons response in matter-oriented QFT.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the discussions of quantum Hall fluids, Chern–Simons terms, and topological field theory.
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” for the modern invertible-field-theory viewpoint.
- Edward Witten, “Fermion Path Integrals and Topological Phases,” *Reviews of Modern Physics* **88** (2016), for spin, eta-invariant, and fermionic response refinements.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
