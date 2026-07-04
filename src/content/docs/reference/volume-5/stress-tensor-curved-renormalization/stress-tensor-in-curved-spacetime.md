---
title: "Stress Tensor in Curved Spacetime"
description: "A careful introduction to the stress tensor as the metric response of QFT, including conservation, trace, improvements, scalar-field examples, source variations, and quantum renormalization caveats."
sidebar:
  label: "Stress Tensor in Curved Spacetime"
  order: 10
level: Graduate
status: "Polished draft"
source: "Birrell and Davies 1982, chs. 3 and 6; Wald 1994, chs. 2–4; Parker and Toms 2009; Brown and York 1993; de Haro, Skenderis, and Solodukhin 2001"
topics:
  - stress tensor
  - curved spacetime
  - metric variation
  - Ward identities
  - trace anomaly
canonicalTopics:
  - stress-tensor-curved-spacetime
  - metric-variation
  - hilbert-stress-tensor
  - covariant-conservation
  - trace-anomaly
researchStatus:
  established:
    - "The stress tensor is the response of a QFT to the background metric and is the central local operator coupling QFT to gravity."
  active:
    - "In quantum theory, defining composite stress tensors requires renormalization; trace anomalies, contact terms, boundary terms, and state dependence must be handled explicitly."
---

## Summary

The stress tensor is the local operator that tells a quantum field theory how it responds to geometry. In the conventions of this volume, for matter action $S_{\mathrm m}[\Phi,g]$,

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}
\frac{\delta S_{\mathrm m}}{\delta g^{\mu\nu}},
$$

so that

$$
\delta S_{\mathrm m}
=-\frac12\int d^Dx\sqrt{|g|}\,
T_{\mu\nu}\delta g^{\mu\nu}.
$$

If the matter equations of motion hold and the theory is diffeomorphism invariant, then

$$
\nabla^\mu T_{\mu\nu}=0.
$$

This is local covariant conservation. It is not automatically a globally conserved energy. Global charges require Killing vectors, boundary conditions, and sometimes asymptotic structure.

The stress tensor is also the bridge to gravity. In classical general relativity it sources the Einstein equation,

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}
=\kappa_D^2T_{\mu\nu}.
$$

In semiclassical gravity, the source becomes the renormalized expectation value,

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}
=\kappa_D^2\langle T_{\mu\nu}\rangle_{\mathrm{ren}}.
$$

That subscript is doing real work. In QFT, $T_{\mu\nu}$ is a composite operator. Its expectation value is divergent before renormalization, and its finite part depends on state, scheme, and local curvature counterterms.

## Prerequisites

Read [Conventions and Notation](/spacetime-gravity-holography/conventions/), [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/), and [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/) first.

You should know Noether currents in flat spacetime, the action principle, covariant derivatives, and the idea that background fields act as sources for operators.

## Core idea

There are two complementary ways to meet the stress tensor:

| Viewpoint | Stress tensor means |
|---|---|
| Noether viewpoint | Current associated with spacetime translations. |
| Metric-response viewpoint | Operator sourced by the background metric. |

Flat-space translations are not available on a generic curved spacetime. The metric-response definition survives. It is therefore the preferred definition in curved-spacetime QFT, semiclassical gravity, and holography.

The stress tensor is special because the metric is special. The metric determines causal structure, volume, distances, and kinetic terms. Varying with respect to it measures energy density, momentum density, pressure, flux, and the response to strain in spacetime geometry.

The practical slogan is

$$
\text{stress tensor} = \text{metric source response}.
$$

## Setup and conventions

We use mostly-minus signature and the curvature conventions of this volume. The matter action is a diffeomorphism-invariant functional

$$
S_{\mathrm m}[\Phi,g_{\mu\nu},\lambda],
$$

where $\Phi$ denotes dynamical fields and $\lambda$ denotes possible background couplings or sources.

The stress tensor is defined by varying the inverse metric:

$$
T_{\mu\nu}
=-\frac{2}{\sqrt{|g|}}
\frac{\delta S_{\mathrm m}}{\delta g^{\mu\nu}}.
$$

Equivalently,

$$
\delta S_{\mathrm m}
=-\frac12\int d^Dx\sqrt{|g|}\,
T_{\mu\nu}\delta g^{\mu\nu}.
$$

If instead one varies $g_{\mu\nu}$, then

$$
\delta g^{\mu\nu}
=-g^{\mu\rho}g^{\nu\sigma}\delta g_{\rho\sigma},
$$

so

$$
\delta S_{\mathrm m}
=\frac12\int d^Dx\sqrt{|g|}\,
T^{\mu\nu}\delta g_{\mu\nu}.
$$

Many sign disagreements in the literature are just this distinction wearing a fake mustache.

## Diffeomorphism Ward identity

Let $\xi^\mu$ be an infinitesimal vector field. Under the corresponding diffeomorphism,

$$
\delta_\xi g^{\mu\nu}
=-(\nabla^\mu\xi^\nu+\nabla^\nu\xi^\mu),
$$

and the matter fields transform by their Lie derivatives. If the matter equations of motion hold, the field variations do not contribute. The metric variation gives

$$
\delta_\xi S_{\mathrm m}
=\int d^Dx\sqrt{|g|}\,T_{\mu\nu}\nabla^\mu\xi^\nu.
$$

Integrating by parts,

$$
\delta_\xi S_{\mathrm m}
=-\int d^Dx\sqrt{|g|}\,
(\nabla^\mu T_{\mu\nu})\xi^\nu
+\text{boundary term}.
$$

Diffeomorphism invariance for arbitrary $\xi^\nu$ implies

$$
\nabla^\mu T_{\mu\nu}=0
$$

when the equations of motion and boundary conditions hold.

This identity is local. It says stress-energy does not disappear inside an infinitesimal spacetime volume. A conserved integrated energy requires more structure, typically a timelike Killing vector.

## Charges from Killing vectors

If $\xi^\mu$ is a Killing vector,

$$
\nabla_{(\mu}\xi_{\nu)}=0,
$$

then

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu
$$

is a conserved current:

$$
\nabla_\mu J^\mu=0.
$$

On a spacelike hypersurface $\Sigma$ with future-directed unit normal $n^\mu$, the corresponding charge is

$$
Q_\xi[\Sigma]
=\int_\Sigma d\Sigma\,n_\mu T^\mu{}_{\nu}\xi^\nu.
$$

If no flux escapes through boundaries, this charge is independent of $\Sigma$. For a timelike Killing vector this is energy; for a rotational Killing vector this is angular momentum.

The existence of $T_{\mu\nu}$ is local and generic. The existence of $Q_\xi$ is global and conditional.

## Scalar-field example

For a real scalar field with action

$$
S_\phi
=\frac12\int d^Dx\sqrt{|g|}\,
\left(
 g^{\mu\nu}\nabla_\mu\phi\nabla_\nu\phi
-(m^2+\xi R)\phi^2
\right),
$$

the stress tensor is

$$
T_{\mu\nu}=T_{\mu\nu}^{\mathrm{min}}+T_{\mu\nu}^{(\xi)},
$$

where

$$
T_{\mu\nu}^{\mathrm{min}}
=\nabla_\mu\phi\nabla_\nu\phi
-\frac12 g_{\mu\nu}
\left(\nabla_\rho\phi\nabla^\rho\phi-m^2\phi^2\right),
$$

and

$$
T_{\mu\nu}^{(\xi)}
=\xi\left(
G_{\mu\nu}\phi^2
+g_{\mu\nu}\Box_g\phi^2
-\nabla_\mu\nabla_\nu\phi^2
\right).
$$

The equation of motion is

$$
(\Box_g+m^2+\xi R)\phi=0.
$$

Using this equation and the Bianchi identity, one finds

$$
\nabla^\mu T_{\mu\nu}=0.
$$

For $m=0$ and

$$
\xi=\xi_c=\frac{D-2}{4(D-1)},
$$

the classical scalar theory is Weyl invariant, and the trace vanishes on shell:

$$
T^\mu{}_{\mu}=0.
$$

Quantum mechanically, the renormalized trace need not vanish because of the trace anomaly.

## Improvement terms

In flat spacetime, a stress tensor obtained by Noether's theorem is not unique. One can add improvement terms that preserve conservation and charges under suitable boundary conditions.

For a scalar field, the flat-space improvement has the schematic form

$$
\Delta T_{\mu\nu}
=\xi\left(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu\right)\phi^2.
$$

In curved spacetime this improvement is not cosmetic: it is tied to the curvature coupling $\xi R\phi^2$. The conformal value $\xi_c$ is what makes the massless scalar stress tensor traceless classically.

The lesson is that the stress tensor is not just a conserved current. It is also a response to background geometry, and that response remembers which curvature couplings were included in the action.

## Trace and Weyl transformations

A Weyl transformation rescales the metric locally:

$$
g_{\mu\nu}\to e^{2\sigma(x)}g_{\mu\nu}.
$$

For an infinitesimal Weyl transformation,

$$
\delta g_{\mu\nu}=2\sigma g_{\mu\nu},
\qquad
\delta g^{\mu\nu}=-2\sigma g^{\mu\nu}.
$$

Using the stress-tensor definition,

$$
\delta_\sigma S_{\mathrm m}
=\int d^Dx\sqrt{|g|}\,\sigma T^\mu{}_{\mu},
$$

up to field variations. Therefore the trace measures the response to local changes of scale.

Classically, a Weyl-invariant theory has

$$
T^\mu{}_{\mu}=0
$$

on shell. Quantum mechanically, a classically Weyl-invariant theory can have

$$
\langle T^\mu{}_{\mu}\rangle_{\mathrm{ren}}\neq0.
$$

The right-hand side is built from local curvature invariants and beta-function terms. This is the trace anomaly, developed in detail on the later [Trace Anomaly](/spacetime-gravity-holography/stress-tensor-curved-renormalization/trace-anomaly/) page.

## Generating functionals and insertions

In Lorentzian signature, define

$$
Z[g,J]=\int\mathcal D\Phi\,
\exp\left(iS[\Phi;g,J]\right).
$$

With the conventions of this volume,

$$
\langle T_{\mu\nu}(x)\rangle
=\frac{2i}{\sqrt{|g|}}
\frac{\delta\log Z[g]}{\delta g^{\mu\nu}(x)}.
$$

Higher metric variations generate stress-tensor correlation functions. For example, a second variation gives a two-point function plus contact terms. Those contact terms are not optional clutter; they encode the fact that the operator itself depends on the metric.

In Euclidean signature,

$$
Z_E[g,J]=\int\mathcal D\Phi\,e^{-S_E[\Phi;g,J]},
$$

and

$$
\langle T_{ij}(x)\rangle_E
=\frac{2}{\sqrt{g}}
\frac{\delta\log Z_E[g]}{\delta g^{ij}(x)}.
$$

Euclidean sign conventions vary across references, so pages using Euclidean stress tensors will state the convention being used.

## Quantum stress tensors need renormalization

The classical formula for $T_{\mu\nu}$ is a local product of fields at the same point. In quantum theory, such products are singular. For example,

$$
\langle\widehat\phi(x)^2\rangle
$$

is already divergent in the vacuum of a free field. The stress tensor contains derivatives and products of fields, so it is more singular still.

A renormalized stress tensor is defined by a prescription such as point-splitting, Hadamard subtraction, heat-kernel subtraction, zeta-function methods, or effective-action counterterms. Any acceptable prescription must preserve the local Ward identities, including

$$
\nabla^\mu\langle T_{\mu\nu}\rangle_{\mathrm{ren}}=0
$$

when there are no diffeomorphism anomalies.

Renormalization permits finite local curvature ambiguities. In four dimensions, adding local gravitational counterterms such as

$$
\int d^4x\sqrt{|g|}\,R^2,
\qquad
\int d^4x\sqrt{|g|}\,R_{\mu\nu}R^{\mu\nu},
\qquad
\int d^4x\sqrt{|g|}\,R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
$$

changes the finite stress tensor by local conserved curvature tensors. This is the curved-spacetime version of scheme dependence.

## Boundary stress tensors

When the spacetime has a boundary, the stress tensor has a boundary cousin. In gravity, varying the on-shell gravitational action with respect to the induced boundary metric gives the Brown–York tensor:

$$
T^{ij}_{\mathrm{BY}}
=\frac{2}{\sqrt{|h|}}
\frac{\delta S_{\mathrm{grav,on\ shell}}}{\delta h_{ij}},
$$

up to the sign conventions for the normal and whether one varies $h_{ij}$ or $h^{ij}$.

In asymptotically AdS spacetimes, this tensor diverges and must be renormalized by adding local boundary counterterms. The resulting holographic stress tensor is one of the main entries of the AdS/CFT dictionary.

This page is primarily about the QFT stress tensor on a background metric. Boundary and holographic stress tensors get their own dedicated pages because the normal orientation, counterterms, and variational principle deserve careful treatment.

## Common pitfalls

**Confusing covariant conservation with global energy conservation.** The equation $\nabla^\mu T_{\mu\nu}=0$ is local. A conserved energy needs a timelike Killing vector or appropriate asymptotic symmetry.

**Forgetting which metric was varied.** Varying $g^{\mu\nu}$ and varying $g_{\mu\nu}$ differ by a sign and index factors.

**Using the canonical Noether tensor in curved spacetime without improvement.** The metric-response tensor is the natural object that couples to gravity. Canonical tensors may need symmetrization or improvement.

**Assuming tracelessness survives quantization.** Weyl-invariant classical theories can have trace anomalies on curved backgrounds.

**Ignoring contact terms in stress-tensor correlators.** Multiple metric variations act both on the path integral weight and on the definition of $T_{\mu\nu}$ itself.

**Treating $\langle T_{\mu\nu}\rangle$ as finite before renormalization.** It is a composite operator expectation value and requires subtraction.

**Forgetting boundary terms.** Boundaries affect both conservation laws and variational definitions. Flux through a boundary changes the charge in a region.

## Relations to other pages

This page begins the Stress Tensor and Curved-Space Renormalization chapter. It supplies the metric-response definition used later in point-splitting, Hadamard states, heat-kernel methods, trace anomalies, curvature counterterms, and semiclassical gravity.

The [Killing Vectors and Conserved Quantities](/spacetime-gravity-holography/spacetime-gravity-toolkit/killing-vectors-and-conserved-quantities/) page explains how a conserved stress tensor produces charges when the spacetime has symmetries. The [Scalar Fields in Curved Spacetime](/spacetime-gravity-holography/qft-in-curved-spacetime/scalar-fields-in-curved-spacetime/) page gives the scalar example used here. The semiclassical Einstein equation uses $\langle T_{\mu\nu}\rangle_{\mathrm{ren}}$ as its source.

## Research status

The classical stress tensor as a metric variation is standard. The Ward identities following from diffeomorphism and Weyl transformations are also standard.

The active and delicate part is quantum. Defining $\widehat T_{\mu\nu}$ as a renormalized local operator on general curved backgrounds requires a prescription, and different prescriptions can differ by local conserved curvature terms. In semiclassical gravity and holography, these scheme choices are not just formal; they affect how one identifies vacuum energy, anomalies, boundary stress tensors, and backreaction.

## Exercises

### Exercise 1: Conservation from diffeomorphism invariance

Assume the matter equations of motion hold and

$$
\delta S_m
=-\frac12\int d^Dx\sqrt{|g|}\,T_{\mu\nu}\delta g^{\mu\nu}.
$$

Use

$$
\delta_\xi g^{\mu\nu}=-(\nabla^\mu\xi^\nu+\nabla^\nu\xi^\mu)
$$

to show that diffeomorphism invariance implies $\nabla^\mu T_{\mu\nu}=0$.

<details><summary><strong>Solution</strong></summary>

Substitute the metric variation:

$$
\delta_\xi S_m
=\int d^Dx\sqrt{|g|}\,T_{\mu\nu}\nabla^\mu\xi^\nu,
$$

where symmetry of $T_{\mu\nu}$ has been used. Integrating by parts gives

$$
\delta_\xi S_m
=-\int d^Dx\sqrt{|g|}\,
(\nabla^\mu T_{\mu\nu})\xi^\nu
+\text{boundary term}.
$$

With boundary conditions that remove the boundary term, diffeomorphism invariance gives $\delta_\xi S_m=0$ for arbitrary $\xi^\nu$. Therefore

$$
\nabla^\mu T_{\mu\nu}=0.
$$

</details>

### Exercise 2: Energy density of a minimally coupled scalar

For the flat-space scalar Lagrangian

$$
\mathcal L=(1/2)\partial_\rho\phi\partial^\rho\phi
-(1/2)m^2\phi^2,
$$

show that

$$
T_{00}=\frac12\dot\phi^2+\frac12(\nabla\phi)^2+\frac12m^2\phi^2.
$$

<details><summary><strong>Solution</strong></summary>

For minimal coupling,

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi-\eta_{\mu\nu}\mathcal L.
$$

In mostly-minus signature,

$$
\partial_\rho\phi\partial^\rho\phi
=\dot\phi^2-(\nabla\phi)^2,
$$

so

$$
\mathcal L=(1/2)\dot\phi^2
-(1/2)(\nabla\phi)^2
-(1/2)m^2\phi^2.
$$

Since $\eta_{00}=1$,

$$
T_{00}=\dot\phi^2-\mathcal L
=\frac12\dot\phi^2+\frac12(\nabla\phi)^2+\frac12m^2\phi^2.
$$

</details>

### Exercise 3: Killing current from the stress tensor

Let $\xi^\mu$ be a Killing vector and $T_{\mu\nu}$ symmetric and conserved. Show that

$$
J^\mu=T^\mu{}_{\nu}\xi^\nu
$$

is conserved.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\nabla_\mu J^\mu
=(\nabla_\mu T^\mu{}_{\nu})\xi^\nu
+T^{\mu\nu}\nabla_\mu\xi_\nu.
$$

The first term vanishes by stress-tensor conservation. The second term vanishes because $T^{\mu\nu}$ is symmetric and the Killing equation implies

$$
\nabla_{(\mu}\xi_{\nu)}=0.
$$

Thus

$$
T^{\mu\nu}\nabla_\mu\xi_\nu
=T^{\mu\nu}\nabla_{(\mu}\xi_{\nu)}=0,
$$

and $\nabla_\mu J^\mu=0$.

</details>

### Exercise 4: Trace as Weyl response

Use

$$
\delta g^{\mu\nu}=-2\sigma g^{\mu\nu}
$$

in the metric variation formula to show that

$$
\delta_\sigma S_m
=\int d^Dx\sqrt{|g|}\,\sigma T^\mu{}_{\mu}.
$$

<details><summary><strong>Solution</strong></summary>

Start from

$$
\delta S_m
=-\frac12\int d^Dx\sqrt{|g|}\,T_{\mu\nu}\delta g^{\mu\nu}.
$$

For an infinitesimal Weyl transformation,

$$
\delta g^{\mu\nu}=-2\sigma g^{\mu\nu}.
$$

Therefore

$$
\delta_\sigma S_m
=-\frac12\int d^Dx\sqrt{|g|}\,T_{\mu\nu}(-2\sigma g^{\mu\nu})
=\int d^Dx\sqrt{|g|}\,\sigma T^\mu{}_{\mu}.
$$

Thus the trace is the source response to local Weyl rescaling.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, Cambridge University Press, 1982.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, University of Chicago Press, 1994.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 2009.
- S. A. Fulling, *Aspects of Quantum Field Theory in Curved Spacetime*, Cambridge University Press, 1989.
- J. D. Brown and J. W. York, “Quasilocal energy and conserved charges derived from the gravitational action,” *Physical Review D* **47** (1993) 1407.
- S. de Haro, K. Skenderis, and S. N. Solodukhin, “Holographic reconstruction of spacetime and renormalization in the AdS/CFT correspondence,” *Communications in Mathematical Physics* **217** (2001) 595.
- M. Duff, “Twenty years of the Weyl anomaly,” *Classical and Quantum Gravity* **11** (1994) 1387.

## Version history

- 2026-07-02: Added a polished first page on the curved-spacetime stress tensor, metric variation, Ward identities, trace, and quantum renormalization caveats.
