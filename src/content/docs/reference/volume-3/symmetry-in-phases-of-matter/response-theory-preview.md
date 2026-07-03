---
title: "Response Theory: Preview"
description: "Preview of background-field response, Kubo formulas, topological response actions, anomaly inflow, and phase diagnostics in matter."
sidebar:
  label: "Response Theory: Preview"
  order: 8
level: Advanced
status: "Polished draft"
source: "Altland–Simons Chs. 7–10; Wen; Fradkin; Qi–Hughes–Zhang; topological response and generalized-symmetry literature."
topics:
  - response theory
  - linear response
  - topological response
  - background fields
  - SPT phases
  - anomalies
canonicalTopics:
  - response-theory
  - topological-response
  - background-field-response
  - kubo-formula
  - anomaly-response
researchStatus:
  established:
    - "Linear response, Kubo formulas, effective actions for background fields, and Chern–Simons/BF/theta response terms are standard tools for diagnosing phases of matter."
  active:
    - "The complete response-theory language for fracton phases, subsystem symmetries, non-invertible symmetries, and strongly interacting gapless phases is still developing."
---

## Summary

Response theory asks a wonderfully practical question:

$$
\text{What does a phase do when we gently probe it?}
$$

The probes are background fields: electromagnetic fields, spin connections, metrics, crystalline strain fields, background gauge fields for internal symmetries, and higher-form backgrounds. The answers are currents, stresses, susceptibilities, conductivities, Hall responses, anomaly inflow phases, and topological terms.

In the QFT language, response theory is encoded by the generating functional

$$
Z[A,g,\ldots]=e^{iW[A,g,\ldots]},
$$

where $A$ is a background gauge field, $g_{\mu\nu}$ is a background metric, and the ellipsis denotes other sources. Functional derivatives produce expectation values:

$$
\langle j^\mu(x)\rangle_A=\frac{\delta W[A]}{\delta A_\mu(x)},
$$

and second derivatives produce linear-response kernels:

$$
G^{\mu\nu}_{jj}(x,y)
=\frac{\delta \langle j^\mu(x)\rangle_A}{\delta A_\nu(y)}
=\frac{\delta^2 W[A]}{\delta A_\mu(x)\delta A_\nu(y)}.
$$

In ordinary phases, these kernels encode transport and susceptibilities. In topological phases, the low-energy response may contain terms that are metric independent and quantized. For example, in $2+1$ dimensions,

$$
S_{\mathrm{CS}}[A]
=
\frac{k}{4\pi}\int A\wedge dA
$$

implies a Hall response. In $3+1$ dimensions,

$$
S_\theta[A]
=
\frac{\theta}{8\pi^2}\int F\wedge F
$$

encodes magnetoelectric response. BF terms, gravitational Chern–Simons terms, discrete Dijkgraaf–Witten actions, and higher-form response terms extend the same idea.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Diagram showing a phase coupled to background fields, with functional derivatives producing currents and topological terms encoding quantized responses.](/figures/symmetry-anomalies-topology/response-theory-background-couplings.svg)

<figcaption>

Response theory turns a phase into a functional of background fields. Ordinary derivatives of $W[A,g,\ldots]$ give currents, stresses, and Kubo formulas; topological terms in $W$ diagnose quantized Hall, BF, theta, SPT, and anomaly responses.

</figcaption>
</figure>

This page is a preview. Its job is to connect the phase-of-matter chapter to background fields, topological terms, anomalies, and generalized symmetries. Full derivations live in the linear-response, topological-field-theory, anomaly, and condensed-matter chapters.

## Prerequisites

You should know [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), [Topological Terms](/symmetry-anomalies-topology/topological-terms/), [Symmetry-Protected Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-protected-topological-phases/), [Symmetry-Enriched Topological Phases](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/symmetry-enriched-topological-phases/), and [Anomaly–Boundary Correspondence](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/anomaly-boundary-correspondence/).

You should also be comfortable with the idea that a background field is not integrated over. It is a source used to measure the theory.

## Core idea

A phase of matter is not only described by its excitations. It is also described by how it responds to probes.

A superfluid responds to a background $U(1)$ field through stiffness. An integer quantum Hall state responds through a quantized Hall conductivity. A topological insulator responds through a theta term. A symmetry-protected topological phase responds through a background-field action that may be trivial in the bulk without boundary, but whose boundary variation reveals an anomaly. A topologically ordered phase responds both through topological terms and through anyon data not captured by response alone.

The response-theory workflow is:

1. Choose a symmetry or spacetime structure to probe.
2. Couple the phase to the corresponding background field.
3. Integrate out gapped microscopic degrees of freedom.
4. Expand the effective action at low frequency and long wavelength.
5. Identify ordinary response coefficients and topological terms.
6. Check quantization, gauge invariance, boundary variation, and anomaly inflow.

In formulas,

$$
e^{iW_{\mathrm{eff}}[A,g,\ldots]}
=
\int \mathcal D\Phi\,e^{iS[\Phi;A,g,\ldots]}.
$$

The resulting $W_{\mathrm{eff}}$ is the response action. In a gapped phase, its deep-infrared part is often local up to topological sectors:

$$
W_{\mathrm{eff}}=W_{\mathrm{top}}+W_{\mathrm{nonuniv}}.
$$

Here $W_{\mathrm{top}}$ contains quantized or robust response data, while $W_{\mathrm{nonuniv}}$ contains metric-dependent and material-dependent coefficients.

## Linear response

Linear response studies the first-order reaction of a system to a weak perturbation. If a background gauge field couples as

$$
\Delta S=\int d^dx\,A_\mu j^\mu,
$$

then, to first order,

$$
\langle j^\mu(x)\rangle_A
=
\langle j^\mu(x)\rangle_0
+
\int d^dy\,G^{\mu\nu}_{R}(x,y)A_\nu(y)+O(A^2),
$$

where $G_R$ is the retarded current-current correlator in Lorentzian signature.

For spatial conductivity,

$$
\langle j^i(\omega,\mathbf k)\rangle
=
\sigma^{ij}(\omega,\mathbf k)E_j(\omega,\mathbf k).
$$

The Kubo formula relates $\sigma^{ij}$ to a retarded correlator. In a simple translationally invariant setting,

$$
\sigma^{ij}(\omega)
=
\frac{1}{i\omega}
G^{ij}_{R}(\omega,\mathbf k=0)
$$

up to diamagnetic/contact terms and convention-dependent subtractions.

:::note[Source note: contact terms]
Conductivity formulas are notoriously sensitive to contact terms, order of limits, and whether one differentiates with respect to $A_i$ or $E_i$. The invariant statement is that transport coefficients come from the properly defined retarded response of currents to sources.
:::

Linear response is not automatically topological. Ordinary compressibility, susceptibility, viscosity, and longitudinal conductivity depend on microscopic dynamics. Topological response is special because some coefficients are quantized or protected.

## Topological response actions

A topological response action is a background-field action whose coefficient is robust under symmetry-preserving deformations. The simplest examples are Chern–Simons, BF, and theta terms.

In $2+1$ dimensions, an Abelian Chern–Simons response

$$
S_{\mathrm{CS}}[A]
=
\frac{k}{4\pi}\int A\wedge dA
$$

gives

$$
j^\mu
=
\frac{\delta S_{\mathrm{CS}}}{\delta A_\mu}
=
\frac{k}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

In components,

$$
j^i=\frac{k}{2\pi}\epsilon^{ij}E_j
$$

with the convention-dependent sign fixed by orientation. Thus $k$ controls the Hall response. In electron units, one usually restores factors of $e^2/h$.

In $3+1$ dimensions, the theta response

$$
S_\theta[A]=\frac{\theta}{8\pi^2}\int F\wedge F
$$

is a total derivative on a closed manifold for ordinary electromagnetic fields. It still matters in the presence of boundaries, interfaces, monopoles, or nontrivial bundles. Time-reversal symmetry can quantize $\theta$ to $0$ or $\pi$ modulo $2\pi$ in suitable topological insulator settings.

BF theory gives another common response:

$$
S_{\mathrm{BF}}=\frac{N}{2\pi}\int B\wedge dA.
$$

Depending on dimension and interpretation, this can describe finite gauge theory, mutual statistics, higher-form symmetry response, or topological order.

## Response versus topological order

Topological response is powerful, but it is not a complete invariant of a phase.

Two phases can have the same electromagnetic Hall response but different anyon content. A topologically ordered phase has intrinsic long-range entanglement, ground-state degeneracy on nontrivial spatial manifolds, nontrivial line or surface operators, and often anyonic excitations. Some of this information is visible in a TQFT, but not necessarily in a response functional for only the ordinary electromagnetic background.

For SPT phases, the situation is different. An SPT has no intrinsic topological order in the bulk. Its robust data can often be encoded by a response action for background fields, possibly with additional spacetime structures such as orientation, spin, Pin structure, crystalline data, or higher-form backgrounds.

A useful diagnostic table is:

| Phase type | Response theory sees | Response theory may miss |
|---|---|---|
| Landau ordered phase | Order-parameter susceptibility, stiffness, Goldstone response | Full defect spectrum and strong-coupling dynamics |
| SPT phase | Quantized background-field action and anomalous boundary | Nonuniversal edge dynamics |
| SET phase | Symmetry fractionalization after coupling to backgrounds | Full anyon category without additional probes |
| Intrinsic topological order | TQFT response to some backgrounds, braiding with probes | Complete topological order if only ordinary backgrounds are used |
| Gapless phase | Current correlators and transport | Universal data may require full CFT or hydrodynamic description |

The moral: response is a window, not the whole house.

## Background fields for internal symmetry

For a global symmetry $G$, a background gauge field $A$ lets us ask how the phase responds to symmetry flux.

For continuous $G$, $A$ is an ordinary connection. For finite $G$, $A$ is better thought of as a flat bundle or cocycle. For higher-form symmetry, the background field has higher degree. For example, a one-form symmetry couples to a two-form background $B$.

The background-field partition function

$$
Z[A]
$$

must be gauge invariant if the symmetry is nonanomalous and the theory is defined absolutely. If instead

$$
Z[A+\delta_\lambda A]=e^{i\mathcal A[\lambda,A]}Z[A],
$$

then $\mathcal A$ is anomaly data. A response action in one higher dimension can cancel this variation by inflow.

This is why response theory and anomalies are inseparable in modern QFT. A topological response that is perfectly gauge invariant in the bulk may become anomalous on a boundary.

## Gravitational and thermal response

The stress tensor is sourced by the metric:

$$
\delta W[g]
=
\frac12\int d^dx\,\sqrt{|g|}\,
\langle T^{\mu\nu}\rangle\,\delta g_{\mu\nu}
$$

up to sign conventions. Spinful systems can also couple to a background vielbein and spin connection.

Gravitational response includes energy-momentum transport, Hall viscosity, thermal Hall response, and gravitational anomaly inflow. In $2+1$ dimensions, a gravitational Chern–Simons term is related to chiral edge central charge, though interpreting it as a strictly quantized bulk response requires care about framing, torsion, and boundary data.

Thermal response is subtle. Temperature is not simply a background gauge field for energy. Still, Euclidean time circles, Luttinger gravitational potentials, vielbein sources, and Keldysh methods give controlled ways to compute thermal transport. The clean modern attitude is to treat energy, momentum, and heat response through stress-tensor and geometry-based sources, then specify the physical transport limit carefully.

## Higher-form and generalized response

Higher-form symmetries have background fields of higher degree. A one-form symmetry background is a two-form field $B_2$. A $q$-form symmetry background is a $(q+1)$-form field $B_{q+1}$.

A simple schematic coupling is

$$
S\mapsto S+\int B_{q+1}\wedge {*}J_{q+1}.
$$

Response to $B_{q+1}$ diagnoses extended charged objects. In gauge theories and topological phases, this can encode line-operator charges, center symmetry, discrete gauge structure, and mixed anomalies.

For example, a BF response can be interpreted as a mixed response between a zero-form and higher-form background, or between electric and magnetic generalized symmetries. More exotic phases may require subsystem, crystalline, or non-invertible background data; those frameworks are still less standardized.

## Response and anomaly inflow

A boundary theory with an anomaly cannot be consistently coupled to backgrounds on its own. But it can be the boundary of a bulk response action.

The inflow relation is

$$
\delta_\lambda W_{\partial}[A]
+
\delta_\lambda S_{\mathrm{bulk}}[A]
=0.
$$

For an SPT phase, $S_{\mathrm{bulk}}[A]$ is often invertible: it gives a phase, not a sum over intrinsic bulk topological sectors. For intrinsic topological order, the bulk may contain nontrivial anyons or extended excitations, and the response theory is only part of the data.

The practical lesson is:

$$
\text{anomaly of boundary}
=
\text{gauge variation of bulk response}.
$$

This principle applies to chiral edge modes of quantum Hall systems, topological insulator surfaces, SPT boundaries, higher-form anomalies, and many symmetry-TFT constructions.

## Worked examples

### Integer quantum Hall response

The long-distance electromagnetic response of an integer quantum Hall state is

$$
S[A]=\frac{\nu}{4\pi}\int A\wedge dA,
$$

with integer $\nu$ in ideal units. The current is

$$
j^\mu=\frac{\nu}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

This encodes a transverse Hall conductivity and requires chiral boundary modes if the spatial manifold has an edge.

### Topological insulator theta response

A time-reversal-invariant topological insulator in $3+1$ dimensions has electromagnetic response

$$
S_\theta[A]=\frac{\theta}{8\pi^2}\int F\wedge F,
$$

with $\theta=0$ or $\pi$ modulo $2\pi$ in the idealized symmetry-protected setting. An interface where $\theta$ jumps supports a boundary Hall response. If the boundary preserves the symmetry and is gapped, it must usually develop topological order rather than be trivially gapped.

### Superfluid stiffness

A superfluid with broken $U(1)$ symmetry can be described at low energy by a phase field $\varphi$. Coupling to a background $A$ gives

$$
S_{\mathrm{eff}}
=
\frac{\rho_s}{2}\int (d\varphi-A)\wedge {*} (d\varphi-A).
$$

The coefficient $\rho_s$ is a stiffness. It is response data, but not topological response; it varies continuously with microscopic parameters.

### Finite symmetry SPT response

For a finite group $G$, a bosonic SPT in $d$ spacetime dimensions may be described, in a group-cohomology model, by a cocycle action evaluated on a background flat $G$ bundle. The response is invisible to local perturbative fields but visible on nontrivial backgrounds and through anomalous boundaries.

## Common pitfalls

**“Response theory classifies all phases.”** No. Response to a chosen set of backgrounds is a diagnostic, not a complete classification.

**“A topological term is automatically quantized.”** Quantization depends on the allowed backgrounds, manifold structure, gauge group, spin structure, and normalization.

**“A total derivative cannot matter.”** Total derivatives can matter on manifolds with boundary, nontrivial topology, defects, interfaces, or singular field configurations.

**“Thermal response is just electromagnetic response with $A_0$ replaced by temperature.”** Not safely. Energy and heat transport require stress-tensor and geometric source technology, plus careful transport limits.

**“An anomalous boundary is inconsistent.”** It is inconsistent as a standalone theory with the symmetry gauged, but it can be perfectly consistent as the boundary of a bulk that supplies inflow.

**“A response action is the same as a microscopic action.”** It is an effective action for probes after integrating out degrees of freedom, valid in a specified low-energy, long-wavelength regime.

## Relations to other pages

This page closes the Symmetry in Phases of Matter chapter. It connects Landau order to susceptibilities and stiffness, SPT phases to quantized background response, SET phases to symmetry defects and fractionalization, topological order to TQFT response, and anomaly-boundary correspondence to inflow.

For derivations of background-field identities, go to [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/). For topological terms, go to [Topological Terms](/symmetry-anomalies-topology/topological-terms/). For higher-form backgrounds, go to [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/). For topological field theories, go to [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/).

## Research status

Linear response and Kubo formulas are established. Chern–Simons, BF, theta, gravitational, and SPT response actions are standard tools, though each has convention and manifold-structure subtleties.

Active areas include response theory for fracton phases, subsystem symmetries, crystalline phases, non-invertible symmetry, mixed higher-group structures, interacting gapless phases, and nonequilibrium topological response. The safe research habit is to state which backgrounds are allowed, which structures the spacetime has, which symmetry is being preserved, and whether the claimed response is quantized, protected, approximate, or nonuniversal.

## Exercises

### Exercise 1: Hall current from Chern–Simons response

Let

$$
S[A]=\frac{k}{4\pi}\int d^3x\,\epsilon^{\mu\nu\rho}A_\mu\partial_\nu A_\rho.
$$

Ignoring boundary terms, compute $j^\mu=\delta S/\delta A_\mu$.

<details><summary><strong>Solution</strong></summary>

Varying,

$$
\delta S
=
\frac{k}{4\pi}\int \epsilon^{\mu\nu\rho}
\left(\delta A_\mu\partial_\nu A_\rho
+
A_\mu\partial_\nu\delta A_\rho
\right).
$$

Integrating the second term by parts and relabeling indices gives

$$
\delta S
=
\frac{k}{2\pi}\int d^3x\,
\epsilon^{\mu\nu\rho}\delta A_\mu\partial_\nu A_\rho.
$$

Thus

$$
j^\mu=\frac{k}{2\pi}\epsilon^{\mu\nu\rho}\partial_\nu A_\rho.
$$

In particular, the spatial current is transverse to the electric field, giving Hall response.

</details>

### Exercise 2: Why the theta term is boundary-sensitive

Show that for $F=dA$ in an Abelian theory,

$$
F\wedge F=d(A\wedge F).
$$

Why does this not mean $\int F\wedge F$ is always irrelevant?

<details><summary><strong>Solution</strong></summary>

Since $F=dA$ and $dF=0$,

$$
d(A\wedge F)=dA\wedge F-A\wedge dF=F\wedge F.
$$

It is a total derivative locally. But its integral can matter on manifolds with boundary, in the presence of interfaces where $\theta$ changes, for nontrivial bundles where $A$ is not globally defined, or around singular defects. Total derivatives can carry global and boundary physics.

</details>

### Exercise 3: Source transformation

Suppose $\mathcal O_A$ transforms as $\mathcal O_A\mapsto R_A{}^B\mathcal O_B$. How should a source $J^A$ transform so that $J^A\mathcal O_A$ is invariant?

<details><summary><strong>Solution</strong></summary>

We need

$$
J'^A R_A{}^B=J^B.
$$

Therefore

$$
J'^A=J^B(R^{-1})_B{}^A.
$$

The source transforms in the dual representation.

</details>

### Exercise 4: Response versus classification

Give one reason why electromagnetic response alone does not classify all topological orders.

<details><summary><strong>Solution</strong></summary>

Electromagnetic response only probes how the phase couples to the external electromagnetic background. Two topological orders can have the same Hall conductivity but different anyon content, braiding, fusion rules, or ground-state degeneracy on higher-genus surfaces. To classify intrinsic topological order, one needs the full topological operator and excitation data, not just one background response.

</details>

## References

- Altland and Simons, *Condensed Matter Field Theory*, especially Ch. 7 on response functions and Ch. 8 on topological field theory.
- Wen, *Quantum Field Theory of Many-Body Systems*, for topological order, response, and effective topological field theories.
- Fradkin, *Field Theories of Condensed Matter Physics*, for response, Chern–Simons theory, quantum Hall systems, and gauge-field methods.
- Qi, Hughes, and Zhang, “Topological Field Theory of Time-Reversal Invariant Insulators,” for theta response of topological insulators.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for higher-form backgrounds, gauging, and anomaly response.
- Kapustin and Seiberg, “Coupling a QFT to a TQFT and Duality,” for background-field and TQFT coupling perspectives.

## Version history

- 2026-06-23: Initial polished draft. Added background-field response, Kubo preview, topological response actions, anomaly inflow, higher-form response, examples, pitfalls, and exercises.
