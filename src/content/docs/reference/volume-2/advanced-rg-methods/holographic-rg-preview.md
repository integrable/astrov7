---
title: "Holographic RG Preview"
description: "A preview of holographic renormalization group ideas: radial evolution as scale, Hamilton–Jacobi flow, counterterms, Wilsonian cutoffs, double-trace running, and caveats."
sidebar:
  label: "Holographic RG Preview"
  order: 90
level: Advanced
status: "Polished draft"
source: "de Boer, Verlinde, and Verlinde 2000; Skenderis 2002; Freedman, Gubser, Pilch, and Warner 1999; Balasubramanian and Kraus 1999; Heemskerk and Polchinski 2011; Faulkner, Liu, and Rangamani 2011; Papadimitriou 2016"
topics:
  - holographic RG
  - AdS/CFT
  - radial evolution
  - holographic renormalization
  - Hamilton–Jacobi equation
  - Wilsonian holographic RG
  - double-trace flows
canonicalTopics:
  - holographic-renormalization-group
  - holographic-renormalization
  - radial-hamiltonian-flow
  - ads-cft-rg
researchStatus:
  established:
    - "In gauge/gravity duality, the radial direction of an asymptotically AdS geometry is related to energy scale in the boundary QFT; holographic renormalization systematically removes cutoff divergences using local boundary counterterms."
  active:
    - "A fully universal identification between radial evolution and Wilsonian RG is subtle; scheme dependence, gauge choices, multi-trace flows, real-time geometries, emergent bulk locality, and non-AdS generalizations remain active research topics."
---

## Summary

The holographic renormalization group is the idea that the extra radial direction in a gravitational dual geometrizes scale. In an asymptotically anti-de Sitter spacetime, the boundary lies at high energy, and moving inward roughly corresponds to flowing toward the infrared.

In its cleanest form, the slogan is

$$
\text{boundary energy scale}
\quad\longleftrightarrow\quad
\text{bulk radial position}.
$$

But the slogan hides several different constructions:

| Construction | Boundary meaning | Bulk operation |
|---|---|---|
| Holographic renormalization | remove UV divergences of CFT generating functionals | add local counterterms near the AdS boundary |
| Radial Hamilton–Jacobi flow | Callan–Symanzik-like identities | solve radial evolution constraints |
| Domain-wall flows | RG flows between fixed points | classical scalar-gravity solutions |
| Wilsonian holographic RG | integrate out UV degrees of freedom | cut the bulk at finite radius and evolve boundary data |
| Multi-trace flow | running boundary conditions | radial evolution of mixed boundary data |

This page is a preview. It explains what is robust, what is convention-dependent, and what can go wrong when “radial direction equals RG scale” is treated too literally.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 56rem;">

![Holographic RG radial flow map](/figures/renormalization-rg-eft/holographic-rg-radial-flow.svg)

<figcaption>

In an asymptotically AdS dual, the near-boundary region represents ultraviolet boundary data. Introducing a cutoff surface, adding local counterterms, and evolving inward organize the same physics in scale-dependent language. The radial coordinate is related to RG scale, but the precise map is scheme- and gauge-dependent.

</figcaption>
</figure>

## Prerequisites

You should know [running couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Callan–Symanzik equations](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), [local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/), [effective actions](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), and [holographic RG’s neighboring monotonicity ideas](/renormalization-rg-eft/advanced-rg-methods/c-theorem-f-theorem-a-theorem-preview/).

It also helps to know the AdS/CFT dictionary at the level of sources, one-point functions, and bulk fields. Full holography belongs in the Spacetime, Gravity, and Holography volume. This page only explains the RG-facing part of the dictionary.

## Setup and conventions

This page uses the standard asymptotically AdS radial convention in which the conformal boundary lies at $z=0$ and a cutoff surface lies at $z=\epsilon$. The boundary field theory has dimension $d$, the bulk has dimension $d+1$, and the AdS radius is $L$. The field-theory energy scale is written schematically as $\mu\sim1/z$ near the boundary.

Bulk formulas are written in Euclidean signature when discussing holographic renormalization. Lorentzian applications require the usual real-time boundary conditions and are not the focus of this preview.

## Core idea

In ordinary Wilsonian RG, one introduces a scale $\mu$ or cutoff $\Lambda$ and asks how the description changes when high-energy modes are removed. In holography, a bulk radial coordinate can play a similar organizing role.

For pure AdS in Poincare coordinates,

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+\eta_{\mu\nu}dx^\mu dx^\nu\right),
$$

with the boundary at $z\to0$. Under the scaling

$$
x^\mu\to b x^\mu,
\qquad
z\to b z,
$$

the metric is invariant. Thus $z$ transforms like a length scale, and the rough energy relation is

$$
\mu\sim \frac{1}{z}.
$$

Equivalently, using a radial coordinate $r$ with

$$
ds^2=dr^2+e^{2A(r)}\eta_{\mu\nu}dx^\mu dx^\nu,
$$

one often identifies

$$
\mu\sim e^{A(r)}.
$$

Near the boundary, $A(r)\sim r/L$, so $r\to\infty$ corresponds to the ultraviolet. Moving inward corresponds roughly to decreasing the boundary energy scale.

:::caution[The slogan is not a theorem by itself]
The radial coordinate is gauge-dependent: different choices of radial slicing correspond to different ways of organizing boundary scale. Physical statements must be phrased in invariant quantities such as renormalized correlation functions, anomaly coefficients, sources, vevs, and regularity conditions.
:::

## Holographic renormalization

The basic holographic generating functional is semiclassically

$$
Z_{\text{QFT}}[J]
\simeq
\exp\left(-S_{\text{bulk,on-shell}}[\phi\to J]\right)
$$

in Euclidean signature. The boundary value of a bulk field $\phi$ acts as a source $J$ for a boundary operator $\mathcal O$.

For a scalar field of mass $m$ in $\mathrm{AdS}_{d+1}$,

$$
m^2L^2=\Delta(\Delta-d),
$$

and near the boundary $z\to0$ the solution behaves as

$$
\phi(z,x)
=z^{d-\Delta}\phi_{(0)}(x)
+z^\Delta\phi_{(2\Delta-d)}(x)
+\cdots.
$$

For standard quantization, $\phi_{(0)}$ is the source for an operator of dimension $\Delta$. The subleading coefficient is related to the expectation value $\langle\mathcal O\rangle$, after counterterms and scheme choices are handled.

The on-shell bulk action diverges as the boundary cutoff $z=\epsilon$ is removed. Holographic renormalization adds local counterterms on the cutoff surface:

$$
S_{\text{ren}}
=\lim_{\epsilon\to0}
\left[
S_{\text{bulk}}^{z\ge\epsilon}
+S_{\text{GHY}}^{z=\epsilon}
+S_{\text{ct}}^{z=\epsilon}
\right].
$$

The counterterms are local functionals of the induced metric and boundary fields:

$$
S_{\text{ct}}=\int_{z=\epsilon} d^d x\sqrt{\gamma}\left[
\frac{c_0}{L}+c_1 L R[\gamma]+c_\phi \phi^2+\cdots
\right],
$$

with the precise terms depending on dimension, fields, and boundary conditions.

This is the closest holographic analog of ordinary UV renormalization: divergences are local near the boundary and are canceled by local counterterms.

## The radial Hamilton–Jacobi viewpoint

Treat the radial coordinate as a time variable. The induced metric $\gamma_{ij}$ and boundary values of bulk fields are configuration variables. Their radial derivatives define canonical momenta. The on-shell action $S_{\text{on-shell}}[\gamma,\phi;r_c]$ satisfies a Hamilton–Jacobi equation.

Schematically,

$$
\partial_{r_c}S+H\left[\gamma,\phi,
\frac{\delta S}{\delta\gamma},
\frac{\delta S}{\delta\phi}
\right]=0.
$$

In gravity, radial diffeomorphism invariance also imposes Hamiltonian and momentum constraints. These constraints become boundary Ward identities. In particular:

| Bulk constraint | Boundary interpretation |
|---|---|
| radial Hamiltonian constraint | trace identity, Weyl anomaly, beta-function structure |
| momentum constraint | stress-tensor conservation and diffeomorphism Ward identity |
| gauge constraint | current conservation or anomaly structure |

The local part of the Hamilton–Jacobi functional generates counterterms. The nonlocal finite part generates renormalized correlation functions.

This is why holographic RG is naturally close to the [local renormalization group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/): sources become spacetime-dependent boundary fields, and Weyl transformations become radial rescalings.

## Domain-wall flows and beta functions

A common holographic model of RG flow uses gravity coupled to scalar fields:

$$
S=\frac{1}{2\kappa^2}\int d^{d+1}x\sqrt{g}\left[
R-\frac12G_{ab}(\phi)\partial_M\phi^a\partial^M\phi^b-V(\phi)
\right].
$$

A Poincare-invariant domain wall has

$$
ds^2=dr^2+e^{2A(r)}\eta_{\mu\nu}dx^\mu dx^\nu,
\qquad
\phi^a=\phi^a(r).
$$

The scalar profiles describe running couplings or expectation values in the boundary theory. A natural holographic beta function is

$$
\beta^a(\phi)
\equiv
\frac{d\phi^a}{d\log\mu}
=\frac{d\phi^a/dr}{dA/dr}.
$$

At an AdS critical point of the potential, $\phi^a=\phi_*^a$ and $A(r)\sim r/L$. This corresponds to a conformal fixed point in the boundary theory.

Near such a fixed point, scalar masses determine operator dimensions:

$$
m_a^2L^2=\Delta_a(\Delta_a-d).
$$

A relevant deformation with $\Delta_a<d$ corresponds to a bulk scalar mode whose source grows toward the interior. An irrelevant deformation corresponds to a mode that is dangerous to turn on near the UV boundary, because it spoils the asymptotic AdS boundary condition unless treated carefully.

## Wilsonian holographic RG

Holographic renormalization removes the UV cutoff and defines finite boundary observables. Wilsonian holographic RG instead keeps a finite radial cutoff $z=z_c$ and asks what effective boundary data live on that cutoff surface.

The bulk path integral can be split at the cutoff:

$$
Z[J]
=\int \mathcal D\varphi_c\,
\Psi_{\mathrm{UV}}[J,\varphi_c;z_c]
\Psi_{\mathrm{IR}}[\varphi_c;z_c].
$$

Here $\varphi_c$ is the field value on the cutoff surface. The UV wavefunctional integrates over the region from the asymptotic boundary to $z_c$. The IR wavefunctional integrates over the interior. Moving $z_c$ changes the split but not the full $Z[J]$.

This is close in spirit to Wilsonian RG: one integrates out the outer radial region and obtains a cutoff-dependent functional for the remaining degrees of freedom. However, the relation to ordinary momentum-shell RG is subtle. A radial cutoff is not a sharp boundary-momentum cutoff. Bulk locality mixes radial and boundary momentum in a way controlled by the geometry and the equations of motion.

The practical Wilsonian holographic RG is especially useful for multi-trace operators, transport in black-brane backgrounds, and radial flow of response functions.

## Double-trace running

A simple and important example is a double-trace deformation

$$
\delta S_{\text{QFT}}=\frac{f}{2}\int d^d x\,\mathcal O^2.
$$

At large $N$, double-trace couplings have controlled beta functions. Holographically, they correspond to mixed boundary conditions relating the leading and subleading scalar coefficients.

In a schematic normalization, if

$$
\phi(z,x)=z^{d-\Delta}\alpha(x)+z^\Delta\beta(x)+\cdots,
$$

then a double-trace deformation imposes a boundary relation of the form

$$
\beta=f\alpha+\text{source terms}.
$$

Changing the radial cutoff changes the relation between $\alpha$ and $\beta$, so $f$ runs. This example makes the holographic RG concrete: boundary couplings are encoded in boundary conditions, and radial evolution changes those boundary conditions.

For dimensions in the alternate-quantization window,

$$
-\frac{d^2}{4}<m^2L^2<-\frac{d^2}{4}+1,
$$

both quantizations are allowed, and double-trace flow can interpolate between them. This is one of the cleanest cases where holographic RG flow and field-theory RG flow can be matched explicitly.

## Holographic counterterms and scheme dependence

Holographic counterterms are local terms on the cutoff surface. Their divergent parts are fixed by cancellation of divergences. Their finite local parts are scheme choices.

This parallels ordinary QFT:

| Ordinary renormalization | Holographic renormalization |
|---|---|
| UV regulator | radial cutoff $z=\epsilon$ |
| local counterterms | local boundary counterterms |
| renormalized generating functional | finite on-shell action |
| scheme dependence | finite local boundary terms |
| Callan–Symanzik equation | radial Hamilton–Jacobi/Weyl identity |
| anomaly | logarithmic counterterm coefficient |

For example, in even boundary dimensions, logarithmic divergences in the on-shell action encode conformal anomalies. The coefficient of a logarithmic cutoff term is universal up to anomaly-scheme subtleties.

Finite counterterms shift contact terms and local pieces of correlation functions. They should not change separated-point universal data or physical response functions once the scheme is specified.

## The holographic c-function idea

For domain-wall geometries satisfying suitable energy conditions, one can often define a geometric quantity that decreases along radial flow and matches central-charge-like data at AdS fixed points.

For metrics of the form

$$
ds^2=dr^2+e^{2A(r)}dx_d^2,
$$

a schematic c-function is

$$
C(r)\propto \frac{1}{[A'(r)]^{d-1}}.
$$

Einstein equations plus a null-energy condition often imply monotonic behavior. At an AdS fixed point, $A'(r)=1/L$, so

$$
C_*\propto \frac{L^{d-1}}{G_N}.
$$

This is proportional to the number of degrees of freedom of the dual large-$N$ CFT, such as central charges in even dimensions or sphere-free-energy-like quantities in odd dimensions.

This is a powerful intuition, but it should not be confused with a fully general field-theoretic monotonicity theorem. It relies on holographic assumptions: classical gravity, energy conditions, appropriate boundary conditions, and a controlled bulk dual.

## Example: relevant scalar deformation

Consider a CFT deformed by a relevant scalar operator:

$$
S_{\text{QFT}}=S_{\text{CFT}}+\lambda\int d^d x\,\mathcal O(x),
\qquad
\Delta<d.
$$

The dual bulk scalar has mass

$$
m^2L^2=\Delta(\Delta-d).
$$

Near the boundary,

$$
\phi(z)=\lambda z^{d-\Delta}+v z^\Delta+\cdots.
$$

The coefficient $\lambda$ is the source. The coefficient $v$ is related to $\langle\mathcal O\rangle$. As $z$ increases into the bulk, the source term becomes more important relative to the UV scaling, reflecting the fact that a relevant deformation grows toward the infrared.

If the solution approaches another AdS region in the interior, the field theory flows to another CFT. If the geometry caps off smoothly or develops a horizon, the infrared may be gapped, confining, thermal, or otherwise nonconformal depending on the geometry.

## Example: radial flow of a response function

In many holographic transport calculations, one perturbs a black-brane geometry and studies a radial canonical momentum. For a bulk fluctuation $a_x(r,\omega)$, define a radial response

$$
\Pi(r,\omega)=\frac{\delta S}{\delta\partial_r a_x(r,-\omega)}.
$$

A conductivity-like quantity can be written schematically as

$$
\sigma(r,\omega)=\frac{\Pi(r,\omega)}{i\omega a_x(r,\omega)}.
$$

The bulk equations imply a first-order radial flow equation for $\sigma(r,\omega)$. At zero frequency, regularity at the horizon often fixes the response, and the radial flow may become trivial, allowing a boundary transport coefficient to be computed from horizon data.

This is not Wilsonian RG in the narrow textbook sense. It is a scale-organized radial evolution of response functions. Still, it is one of the most useful practical descendants of holographic RG thinking.

## Boundaries

This page does not teach AdS/CFT from scratch, holographic entanglement, black-hole thermodynamics, string theory, numerical relativity, or the full fluid/gravity correspondence. Those belong in the Spacetime, Gravity, and Holography volume.

It also does not assert that every RG flow has a classical gravitational dual. Holographic RG is a special, extremely powerful realization of RG for theories with suitable large-$N$, strong-coupling, sparse-spectrum, or semiclassical-bulk structure.

## Common pitfalls

**Taking radial position too literally as momentum cutoff.** A finite radial cutoff is not exactly a sharp field-theory momentum cutoff. It is a geometric scale separator whose field-theory interpretation is scheme-dependent.

**Forgetting gauge dependence of the radial coordinate.** The coordinate $z$ or $r$ is not itself an observable. Different radial slicings can represent different RG schemes.

**Confusing sources and vevs.** The leading and subleading coefficients in a near-boundary expansion have source and expectation-value interpretations only after choosing quantization, counterterms, and boundary conditions.

**Ignoring finite counterterms.** Holographic renormalization has scheme dependence just like ordinary renormalization. Finite local terms can shift contact terms.

**Calling every radial flow a beta function.** Some radial evolution equations describe response functions, canonical momenta, or boundary conditions rather than couplings in a Wilsonian action.

**Assuming all field theories have holographic duals.** Holography is a special structure, not a generic property of every QFT.

## Relations to other pages

This page connects [Local Renormalization Group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/), [c-, F-, and a-Theorem Preview](/renormalization-rg-eft/advanced-rg-methods/c-theorem-f-theorem-a-theorem-preview/), [Nonperturbative RG Preview](/renormalization-rg-eft/advanced-rg-methods/nonperturbative-rg-preview/), [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/), and [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/).

It points outward to CFT and Bootstrap for operator dimensions and CFT data; to Spacetime, Gravity, and Holography for the full AdS/CFT dictionary; to Gauge Theories and RG for large-$N$ gauge-theory examples; and to Renormalization in Curved Spacetime for stress-tensor counterterms and trace anomalies.

## Research status

Holographic renormalization is a mature and precise technology. Radial Hamilton–Jacobi methods, boundary counterterms, stress-tensor extraction, and one-point functions are standard parts of the gauge/gravity dictionary.

The more Wilsonian interpretation is subtler and remains an active conceptual area. Important live questions include:

- how to define Wilsonian cutoffs and effective actions in a manifestly covariant bulk way;
- how bulk locality emerges from boundary RG structure;
- how multi-trace flows and alternate quantization encode boundary theory data;
- how holographic RG works outside asymptotically AdS spacetimes;
- how radial flow interacts with real-time horizons, chaos, transport, and entanglement wedges;
- how to interpret RG flow when the bulk contains dynamical gravity and no fixed boundary metric.

## Exercises

### Exercise 1: Scaling in Poincare AdS

Show that

$$
ds^2=\frac{L^2}{z^2}(dz^2+dx_d^2)
$$

is invariant under $z\to bz$ and $x^\mu\to bx^\mu$.

<details><summary><strong>Solution</strong></summary>

Under the scaling,

$$
dz\to b\,dz,
\qquad
 dx^\mu\to b\,dx^\mu,
\qquad
z^2\to b^2z^2.
$$

Therefore the numerator $dz^2+dx_d^2$ gains a factor $b^2$, while the denominator $z^2$ also gains $b^2$. The factors cancel, so the metric is invariant. This is the geometric reason $z$ behaves like a length scale and $1/z$ like an energy scale.

</details>

### Exercise 2: Source scaling from the near-boundary expansion

For a scalar dual to an operator of dimension $\Delta$, the leading source term is

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+\cdots.
$$

Use scaling to infer the mass dimension of the source $\phi_{(0)}$.

<details><summary><strong>Solution</strong></summary>

The deformation is

$$
\int d^d x\,\phi_{(0)}(x)\mathcal O(x).
$$

Since $[d^d x]=-d$ and $[\mathcal O]=\Delta$, the source must have dimension

$$
[\phi_{(0)}]=d-\Delta.
$$

This matches the power $z^{d-\Delta}$ in the near-boundary expansion: $z$ has dimension of length, so the source coefficient carries the compensating energy dimension.

</details>

### Exercise 3: Holographic beta function for a domain wall

Let $\mu\sim e^{A(r)}$ and let a scalar profile be $\phi(r)$. Show that the natural radial beta function is

$$
\beta(\phi)=\frac{d\phi}{d\log\mu}=\frac{\phi'(r)}{A'(r)}.
$$

<details><summary><strong>Solution</strong></summary>

If $\mu\sim e^{A(r)}$, then

$$
\log\mu=A(r)+\text{constant}.
$$

Therefore

$$
\frac{d\log\mu}{dr}=A'(r).
$$

By the chain rule,

$$
\frac{d\phi}{d\log\mu}
=
\frac{d\phi/dr}{d\log\mu/dr}
=
\frac{\phi'(r)}{A'(r)}.
$$

This defines a natural beta function associated with the radial profile, though its precise interpretation depends on field parametrization and radial gauge.

</details>

## References

- J. de Boer, E. Verlinde, and H. Verlinde, “On the Holographic Renormalization Group,” *Journal of High Energy Physics* **0008** (2000) 003.
- K. Skenderis, “Lecture Notes on Holographic Renormalization,” *Classical and Quantum Gravity* **19** (2002) 5849–5876.
- D. Z. Freedman, S. S. Gubser, K. Pilch, and N. P. Warner, “Renormalization Group Flows from Holography — Supersymmetry and a c-Theorem,” *Advances in Theoretical and Mathematical Physics* **3** (1999) 363–417.
- V. Balasubramanian and P. Kraus, “A Stress Tensor for Anti-de Sitter Gravity,” *Communications in Mathematical Physics* **208** (1999) 413–428.
- I. Heemskerk and J. Polchinski, “Holographic and Wilsonian Renormalization Groups,” *Journal of High Energy Physics* **1106** (2011) 031.
- T. Faulkner, H. Liu, and M. Rangamani, “Integrating Out Geometry: Holographic Wilsonian RG and the Membrane Paradigm,” *Journal of High Energy Physics* **1108** (2011) 051.
- I. Papadimitriou, “Holographic Renormalization as a Canonical Transformation,” *Journal of High Energy Physics* **1011** (2010) 014, and later lecture-note treatments.

## Version history

- 2026-06-19: First polished draft. Added radial-scale dictionary, holographic renormalization, Hamilton–Jacobi flow, domain-wall beta functions, Wilsonian cutoff split, double-trace running, caveats, exercises, and references.
