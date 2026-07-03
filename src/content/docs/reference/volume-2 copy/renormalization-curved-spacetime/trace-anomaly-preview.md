---
title: "Trace Anomaly Preview"
description: "How a classically traceless stress tensor acquires a local quantum trace from renormalization, beta functions, and curvature invariants."
sidebar:
  label: "Trace Anomaly Preview"
  order: 20
level: Advanced
status: "Polished draft"
source: "Coleman 1985, Dilatations; Duff 1994; Birrell and Davies; Parker and Toms; Wald; Christensen; Brown and Ottewill; Osborn; Weinberg 1995; Zinn-Justin 2021."
topics:
  - trace anomaly
  - Weyl anomaly
  - stress tensor
  - curvature invariants
  - local renormalization group
  - curved spacetime
canonicalTopics:
  - trace-anomaly
  - weyl-anomaly
  - curved-spacetime-renormalization
  - local-rg
researchStatus:
  established:
    - 'In even spacetime dimensions, renormalized quantum field theories can have local Weyl anomalies; in four dimensions the standard curvature terms are built from $C^2$, the Euler density $E_4$, and a scheme-dependent $\Box R$ term, together with beta-function contributions from running couplings.'
  active:
    - "Trace anomalies with boundaries, defects, gauge backgrounds, supersymmetry, nonconformal states, nonequilibrium systems, de Sitter observables, and dynamical gravity require additional structure beyond this preview."
---

## Summary

A trace anomaly is the statement that a stress tensor that is classically traceless can acquire a nonzero quantum trace after renormalization. The cleanest version appears when a classically Weyl-invariant theory is placed on a curved background metric. Classically, a Weyl transformation rescales the metric locally,

$$
g_{\mu\nu}(x)\longrightarrow e^{2\sigma(x)}g_{\mu\nu}(x),
$$

and a conformal theory has

$$
T^\mu{}_{\mu}=0
$$

up to equations of motion and explicit relevant deformations. Quantum mechanically, the renormalized generating functional cannot always respect Weyl invariance while also remaining local, finite, and diffeomorphism covariant. The result is a local anomalous trace.

In four spacetime dimensions, the standard schematic form is

$$
\langle T^\mu{}_{\mu}\rangle
=\sum_i\beta^i\langle[\mathcal O_i]\rangle
+\frac{1}{(4\pi)^2}
\left(c\,C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma}
-a\,E_4
+b\,\Box R\right)
+\text{explicit breaking terms}.
$$

Here $C_{\mu\nu\rho\sigma}$ is the Weyl tensor, $E_4$ is the Euler density, the coefficients $a$ and $c$ are physical CFT data in a four-dimensional conformal field theory, and $b$ is scheme dependent because it can be shifted by a finite local $R^2$ counterterm. The precise signs of $a$ and $c$ vary across the literature; this page uses the displayed formula as its definition of the signs.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 58rem;">

![Trace anomaly map](/figures/renormalization-rg-eft/trace-anomaly-weyl-map.svg)

<figcaption>

The trace anomaly is a local remnant of trying to preserve finiteness, locality, diffeomorphism covariance, and Weyl symmetry simultaneously. Renormalization introduces a scale or subtraction convention. Running couplings produce $\beta^i[\mathcal O_i]$ terms, while curved backgrounds allow local curvature terms such as $C^2$, $E_4$, and $\Box R$.

</figcaption>
</figure>

## Prerequisites

You should know [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/), and [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/). It also helps to know that the stress tensor is defined by variation of the generating functional with respect to the metric.

This page is a preview. It gives the conceptual and algebraic skeleton. It does not prove the full classification of Weyl anomalies or derive all coefficients by heat-kernel methods.

## Core idea

A classical scale-invariant theory says that rescaling lengths does not change the physics. A classical Weyl-invariant theory says something stronger: one may rescale the metric locally and compensate by rescaling fields.

Renormalization disturbs this ideal in two ways.

First, if dimensionless couplings run, then the trace records that running. The trace contains beta-function terms,

$$
T^\mu{}_{\mu}\sim \beta^i[\mathcal O_i].
$$

This statement is already visible in flat spacetime. If the coupling changes with the renormalization scale $\mu$, then a dilation can be compensated by changing $\mu$, and the response is controlled by beta functions.

Second, even at a fixed point where $\beta^i=0$, curved spacetime supplies local curvature invariants with the correct dimension to appear in the trace. These terms are not optional once the metric is a source. They are the curved-spacetime analog of local counterterms, but their finite Weyl variation can survive after the regulator is removed.

The practical slogan is

$$
\text{classical Weyl invariance}+
\text{renormalization}+
\text{curved background}
\Longrightarrow
\text{local trace anomaly}.
$$

The word local is essential. The anomalous trace is a local curvature expression and local operator expression. It is not the whole nonlocal effective action, and it is not a direct substitute for state-dependent physics such as particle creation or thermal radiation.

## Setup and conventions

It is clearest to discuss Weyl variations in Euclidean signature. Let

$$
Z[g,J]=e^{-W[g,J]}
$$

be the Euclidean generating functional. We define the stress tensor by

$$
\delta W
=\frac12\int d^d x\sqrt g\,\langle T_{\mu\nu}\rangle\,\delta g^{\mu\nu}.
$$

For an infinitesimal Weyl transformation

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu},
\qquad
\delta_\sigma g^{\mu\nu}=-2\sigma g^{\mu\nu},
$$

we get

$$
\delta_\sigma W
=-\int d^d x\sqrt g\,\sigma\,\langle T^\mu{}_{\mu}\rangle.
$$

The anomaly is therefore the local functional $\mathcal A$ defined by

$$
\delta_\sigma W_{\text{ren}}
=-\int d^d x\sqrt g\,\sigma\,\mathcal A,
\qquad
\mathcal A=\langle T^\mu{}_{\mu}\rangle_{\text{ren}}.
$$

In Lorentzian signature, the same local terms appear after the usual continuation, but factors of $i$ and sign conventions in $W$ change. This page quotes local anomaly formulas without tying them to a particular Lorentzian phase convention.

## Classical Weyl invariance and improvement

A massless scalar with minimal coupling is scale invariant in flat spacetime, but its naive stress tensor is not traceless in general dimension. The improved scalar action in curved spacetime is

$$
S=\frac12\int d^d x\sqrt g\left(
 g^{\mu\nu}\nabla_\mu\phi\nabla_\nu\phi
+\xi_c R\phi^2
\right),
\qquad
\xi_c=\frac{d-2}{4(d-1)}.
$$

In Euclidean signature this action is invariant under

$$
g_{\mu\nu}\to e^{2\sigma}g_{\mu\nu},
\qquad
\phi\to e^{-(d-2)\sigma/2}\phi,
$$

up to boundary terms. The corresponding stress tensor is traceless on shell,

$$
T^\mu{}_{\mu}=0,
$$

for $m=0$ and $\xi=\xi_c$.

The important lesson is that the trace anomaly is not caused by forgetting the improvement term. Improvement fixes the classical stress tensor. The anomaly remains after the properly improved operator is renormalized.

:::note[Scale versus Weyl]
Scale invariance uses a constant rescaling. Weyl invariance uses a spacetime-dependent rescaling of the metric. In flat-space unitary relativistic QFTs, scale invariance often enhances to conformal invariance under additional assumptions, but the relation is subtle. Curved-space Weyl anomalies are the sharpest way to keep track of the local obstruction.
:::

## Flat-space beta-function terms

Before adding curvature, the trace already knows about running couplings. Suppose the renormalized action contains

$$
S\supset\int d^d x\,g^i(\mu)\,[\mathcal O_i](x).
$$

The renormalized generating functional is independent of the arbitrary scale $\mu$ when bare data are held fixed. The Callan–Symanzik logic gives

$$
\left(\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\cdots
\right)W=0.
$$

A Weyl rescaling is locally a change of length scale. Therefore the trace contains

$$
\langle T^\mu{}_{\mu}\rangle
\supset \beta^i\langle[\mathcal O_i]\rangle,
$$

up to sign conventions for the source coupling. More generally, if a coupling $g^i$ has classical mass dimension $d-\Delta_i$, then the trace also contains the explicit breaking term

$$
(d-\Delta_i)g^i\langle[\mathcal O_i]\rangle.
$$

Combining classical and quantum scale dependence gives the schematic formula

$$
\langle T^\mu{}_{\mu}\rangle
=\sum_i\left[(d-\Delta_i)g^i+\beta^i\right]
\langle[\mathcal O_i]\rangle
+\text{curvature anomaly terms}.
$$

At a conformal fixed point with no relevant deformations, the beta-function terms vanish. The curvature anomaly can remain.

## Gauge-theory example

A common flat-space example is a massless gauge theory. If the coupling is placed in front of the kinetic term,

$$
\mathcal L=-\frac{1}{4g^2}F^a_{\mu\nu}F^{a\mu\nu},
$$

then the trace contains

$$
T^\mu{}_{\mu}
=\frac{\beta_g}{2g^3}
[F^a_{\rho\sigma}F^{a\rho\sigma}]
$$

in this normalization. If instead the kinetic term is written with canonical normalization and $g$ appears in the covariant derivative and vertices, the same physics is written with a different-looking coefficient. The invariant statement is that the trace is proportional to the beta function multiplying the operator generated by differentiating the action with respect to the coupling.

This is why asymptotically free Yang–Mills theory can be classically scale invariant but quantum mechanically generate a scale. The trace anomaly is one local face of dimensional transmutation.

## Curvature terms in four dimensions

In four spacetime dimensions, the local curvature terms with the right dimension are built from four derivatives of the metric. A convenient basis uses the Weyl tensor squared,

$$
C^2\equiv C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma},
$$

the Euler density,

$$
E_4
=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2,
$$

and the total derivative $\Box R$. The anomaly of a four-dimensional CFT is conventionally written

$$
\langle T^\mu{}_{\mu}\rangle
=\frac{1}{(4\pi)^2}
\left(c C^2-a E_4+b\Box R\right).
$$

The coefficients $a$ and $c$ are central charges in four-dimensional CFT. They appear in correlation functions of the stress tensor and in universal parts of the generating functional. The coefficient $b$ is not universal, because adding a finite counterterm

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

shifts the anomaly by a multiple of $\Box R$.

The Euler density deserves a comment. On a compact boundaryless four-manifold,

$$
\int d^4x\sqrt g\,E_4
$$

is topological. Its metric variation vanishes in strictly four dimensions. Nevertheless, the $aE_4$ term in the anomaly is physical. In dimensional regularization, a pole multiplying an evanescent Weyl variation can leave a finite four-dimensional anomaly. This is one of those moments where treating $d=4-2\epsilon$ too casually creates confusion.

## Two dimensions as the cleanest example

In two dimensions, the curvature invariant with two derivatives is simply $R$. A two-dimensional CFT has a trace anomaly proportional to the scalar curvature,

$$
\langle T^\mu{}_{\mu}\rangle
= -\frac{c}{24\pi}R
$$

in a common Euclidean convention. Some sources use the opposite sign because they define $T_{\mu\nu}$ or $W$ with the opposite sign. The coefficient $c$ is the Virasoro central charge.

This two-dimensional formula is the baby version of the four-dimensional story. A theory can be locally conformal in flat space and still respond anomalously to curved geometry. In two dimensions the anomaly controls the Weyl variation of the effective action and leads to the nonlocal Polyakov action,

$$
W_{\text{anom}}[g]
\sim
\int d^2x\sqrt g\,R\frac{1}{\Box}R,
$$

whose Weyl variation is local. This is a recurring theme: the anomaly is local even when the effective action that integrates it is nonlocal.

## Scheme dependence and finite counterterms

Not every term in the trace anomaly is equally invariant. A finite local counterterm can change the trace by a local Weyl variation. For example, in four dimensions,

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

implies

$$
\delta_\sigma\Delta W
=-12\alpha\int d^4x\sqrt g\,\sigma\Box R
$$

on a boundaryless manifold. Therefore

$$
\Delta\langle T^\mu{}_{\mu}\rangle
=12\alpha\Box R.
$$

The $\Box R$ coefficient is a convention. It is still useful, because a chosen scheme may require it, but it is not universal CFT data in the same way as $a$ and $c$.

By contrast, no finite local counterterm in four dimensions can remove the $C^2$ and $E_4$ anomaly terms in a unitary CFT. Those encode genuine local Weyl non-invariance.

## Relation to the local renormalization group

The local RG promotes couplings to spacetime-dependent sources,

$$
g^i\longrightarrow g^i(x),
$$

and studies local Weyl transformations together with compensating motion in coupling space. The schematic local RG equation is

$$
\left(
\Delta_\sigma^{\text{Weyl}}
-\int d^d x\sqrt g\,\sigma\beta^i\frac{\delta}{\delta g^i(x)}
+\cdots
\right)W
=\mathcal A_\sigma.
$$

The anomaly functional $\mathcal A_\sigma$ is local and constrained by Wess–Zumino consistency:

$$
[\Delta_{\sigma_1},\Delta_{\sigma_2}]W=0.
$$

This consistency condition is not just formal elegance. It severely restricts possible anomaly terms and underlies deep results such as RG monotonicity theorems in special dimensions.

## What the anomaly is not

The trace anomaly is not an ordinary failure of energy-momentum conservation. If diffeomorphism symmetry is non-anomalous, then

$$
\nabla^\mu\langle T_{\mu\nu}\rangle=0
$$

still holds, possibly with source terms if background sources vary. The trace anomaly concerns Weyl symmetry, not translations or diffeomorphisms.

The trace anomaly is also not the same as a nonzero trace caused by mass. A massive scalar has a classical contribution such as

$$
T^\mu{}_{\mu}\supset m^2\phi^2,
$$

up to improvement conventions. That is explicit breaking. The anomaly is the residual trace that remains after classically Weyl-invariant terms have been renormalized.

Finally, the trace anomaly is not itself a thermal or state-dependent effect. The anomaly is local and fixed by the theory and background sources. The expectation value $\langle T_{\mu\nu}\rangle$ can also contain state-dependent finite pieces, but those are distinct from the local anomaly.

## Common pitfalls

**Using a non-improved stress tensor and calling the result an anomaly.** First improve the classical stress tensor when the theory admits improvement. The trace anomaly is what remains after the correct classical symmetry has been implemented.

**Treating $\Box R$ as universal data.** The coefficient of $\Box R$ can be shifted by a finite local $R^2$ counterterm. It is a scheme choice, not a central charge.

**Confusing beta-function terms with fixed-point anomaly coefficients.** Away from a fixed point, $\beta^i[\mathcal O_i]$ terms are part of the trace. At a fixed point, they vanish, but curvature anomaly terms can remain.

**Forgetting sources.** If couplings, background gauge fields, or masses are spacetime-dependent, the trace and diffeomorphism Ward identities acquire source-dependent terms.

**Thinking the anomaly is nonlocal because the anomaly action is nonlocal.** The anomaly itself is local. The functional whose Weyl variation gives the anomaly may be nonlocal.

## Relations to other pages

[Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/) explains why $T_{\mu\nu}$ requires local UV subtraction. [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/) explains the local gravitational terms whose Weyl variations and pole residues produce anomaly terms. [Local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/) gives the general source-functional viewpoint. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) explains the flat-space scale-generation side. [Confinement Scale and Dimensional Transmutation](/renormalization-rg-eft/gauge-theories-and-rg/confinement-scale-and-dimensional-transmutation/) connects this to asymptotically free gauge theory.

## Research status

The basic trace anomaly formulas in two and four dimensions are established. The classification of Weyl anomalies using local cohomology is also mature in standard settings.

Active research appears when extra structures are present: boundaries, corners, defects, entangling surfaces, supersymmetry, higher-form backgrounds, parity-odd terms, nonrelativistic scaling, hydrodynamics, de Sitter space, and dynamical gravity. In these settings, the same principles apply — locality, covariance, Wess–Zumino consistency — but the allowed anomaly terms and physical interpretation become richer.

## Exercises

### Exercise 1: Weyl variation of $R^2$

In four Euclidean dimensions, use

$$
\delta_\sigma\sqrt g=4\sigma\sqrt g,
\qquad
\delta_\sigma R=-2\sigma R-6\Box\sigma
$$

for an infinitesimal Weyl transformation. Show that, on a boundaryless manifold,

$$
\delta_\sigma\int d^4x\sqrt g\,R^2
=-12\int d^4x\sqrt g\,\sigma\Box R.
$$

<details><summary><strong>Solution</strong></summary>

Vary the integrand:

$$
\delta_\sigma(\sqrt g R^2)
=(\delta_\sigma\sqrt g)R^2+2\sqrt g R\delta_\sigma R.
$$

Substituting the variations gives

$$
\delta_\sigma(\sqrt g R^2)
=4\sigma\sqrt g R^2
+2\sqrt g R(-2\sigma R-6\Box\sigma)
=-12\sqrt g R\Box\sigma.
$$

Integrating by parts twice on a boundaryless manifold gives

$$
\int d^4x\sqrt g\,R\Box\sigma
=\int d^4x\sqrt g\,\sigma\Box R.
$$

Therefore

$$
\delta_\sigma\int d^4x\sqrt g\,R^2
=-12\int d^4x\sqrt g\,\sigma\Box R.
$$

This is why a finite $R^2$ counterterm shifts the $\Box R$ part of the trace anomaly.

</details>

### Exercise 2: Beta-function contribution to the gauge trace

Let

$$
\mathcal L=-\frac{1}{4g^2}F^a_{\mu\nu}F^{a\mu\nu}.
$$

Assume the trace contribution from running couplings is

$$
T^\mu{}_{\mu}=\beta_g\frac{\partial\mathcal L}{\partial g}.
$$

Show that

$$
T^\mu{}_{\mu}=\frac{\beta_g}{2g^3}F^a_{\mu\nu}F^{a\mu\nu}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the Lagrangian with respect to $g$:

$$
\frac{\partial}{\partial g}
\left(-\frac{1}{4g^2}F^2\right)
=\frac{1}{2g^3}F^2,
$$

where $F^2=F^a_{\mu\nu}F^{a\mu\nu}$ in this notation. Multiplying by $\beta_g$ gives

$$
T^\mu{}_{\mu}
=\frac{\beta_g}{2g^3}F^a_{\mu\nu}F^{a\mu\nu}.
$$

If the coupling is instead placed in the interaction vertices rather than in front of $F^2$, the displayed coefficient changes form. The invariant content is the beta-function response of the action to a change of coupling convention.

</details>

### Exercise 3: Why no anomaly in odd-dimensional CFTs of this type?

Explain why a local parity-even curvature scalar of Weyl weight $d$ is needed for a standard local Weyl anomaly in $d$ dimensions, and why this makes odd dimensions special.

<details><summary><strong>Solution</strong></summary>

The trace has mass dimension $d$. A purely gravitational local anomaly term must therefore be a scalar built from the metric with $d$ derivatives. Curvatures carry two derivatives, so parity-even scalar curvature polynomials naturally have even total derivative order: $R$ has two derivatives, $R^2$ has four, and so on. In odd $d$, there is no ordinary parity-even scalar curvature polynomial of derivative order $d$ built only from curvatures without introducing additional structures.

This does not mean odd-dimensional CFTs have no universal data. For example, three-dimensional CFTs have a universal sphere free energy. It means the standard local Weyl anomaly of the even-dimensional type is absent on closed manifolds without extra structures such as boundaries or background fields with appropriate parity-odd terms.

</details>

## References

- Coleman, *Aspects of Symmetry*, especially "Dilatations," for the physical relation between broken scale invariance, anomalous dimensions, Callan–Symanzik equations, and OPE scaling.
- Birrell and Davies, *Quantum Fields in Curved Space*, for standard curved-spacetime stress tensors and anomalies.
- Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, for local covariance and stress-tensor renormalization.
- Duff, "Twenty years of the Weyl anomaly," for a broad review of trace-anomaly formulas and conventions.
- Parker and Toms, *Quantum Field Theory in Curved Spacetime*, for heat-kernel and effective-action methods.
- Brown and Ottewill, classic papers on stress tensors and conformal anomalies.
- Osborn, local RG and Weyl consistency conditions.
- Weinberg, *The Quantum Theory of Fields*, for renormalization, anomalies, and curved-background effective actions.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for RG and anomaly logic in Euclidean field theory.

## Version history

- 2026-06-19: First polished draft. Added four-dimensional anomaly structure, scheme dependence of $\Box R$, beta-function terms, local RG connection, and exercises.
