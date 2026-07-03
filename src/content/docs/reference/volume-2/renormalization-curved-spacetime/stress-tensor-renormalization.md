---
title: "Stress-Tensor Renormalization"
description: "How the stress tensor is defined as a metric response, why it is a composite operator, and how local curvature counterterms make its expectation value finite in curved spacetime."
sidebar:
  label: "Stress-Tensor Renormalization"
  order: 10
level: Advanced
status: "Polished draft"
source: "Birrell and Davies; Wald; Parker and Toms; Fulling; Christensen; DeWitt; Duff; Coleman 1985; Weinberg 1995; Zinn-Justin 2021."
topics:
  - stress tensor
  - composite operator renormalization
  - QFT in curved spacetime
  - curvature counterterms
  - trace anomaly
  - semiclassical gravity
canonicalTopics:
  - stress-tensor-renormalization
  - renormalized-stress-tensor
  - curved-spacetime-renormalization
researchStatus:
  established:
    - "The renormalized expectation value of the stress tensor in curved spacetime is obtained by metric variation of a renormalized effective action and is ambiguous only up to local conserved curvature tensors fixed by finite counterterm choices."
  active:
    - "Interacting gauge theories, non-Hadamard states, boundaries, real-time nonequilibrium settings, dynamical quantum gravity, and de Sitter observables require extra care beyond the local UV structure explained here."
---

## Summary

The stress tensor is the response of a quantum field theory to a change of metric. In this volume’s mostly-minus Lorentzian convention, this page uses

$$
\delta S_{\text{matter}}
=\frac12\int d^d x\sqrt{-g}\,T_{\mu\nu}\,\delta g^{\mu\nu},
\qquad
T_{\mu\nu}=\frac{2}{\sqrt{-g}}\frac{\delta S_{\text{matter}}}{\delta g^{\mu\nu}}.
$$

Some general-relativity and curved-spacetime books vary with respect to $g_{\mu\nu}$ instead of $g^{\mu\nu}$, or choose the opposite sign in the matter action. When comparing sources, translate this definition first.

Quantum mechanically, $T_{\mu\nu}$ is a composite operator. For example, a scalar stress tensor contains products such as $\partial_\mu\phi(x)\partial_\nu\phi(x)$ at the same point. These products are singular before renormalization. In curved spacetime, locality and covariance imply that the singular pieces are canceled by local counterterms built from the metric.

The central object is the renormalized effective action

$$
W_{\text{ren}}[g,J]
=\lim_{\text{regulator removed}}\left(W_{\text{reg}}[g,J]+S_{\text{ct}}[g,J]\right),
$$

and the renormalized expectation value is

$$
\langle T_{\mu\nu}(x)\rangle_{\text{ren}}
=\frac{2}{\sqrt{-g(x)}}\frac{\delta W_{\text{ren}}}{\delta g^{\mu\nu}(x)}.
$$

The ultraviolet-divergent part is local and state-independent. The finite nonlocal part depends on the state, boundary conditions, and global geometry.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 58rem;">

![Stress-tensor renormalization map](/figures/renormalization-rg-eft/stress-tensor-renormalization-map.svg)

<figcaption>

Stress-tensor renormalization is best organized through the effective action. The regulated functional contains local UV divergences. Covariant counterterms remove them. Metric variation of the renormalized functional gives a finite $\langle T_{\mu\nu}\rangle_{\text{ren}}$, subject to diffeomorphism Ward identities, trace anomalies, scheme-dependent local curvature shifts, and state-dependent nonlocal contributions.

</figcaption>
</figure>

## Prerequisites

You should know [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/), [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/), and [Local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/).

You also need the basic geometric facts that $g_{\mu\nu}$ defines $\sqrt{-g}$, covariant derivatives $\nabla_\mu$, and curvature tensors $R^\rho{}_{\sigma\mu\nu}$, $R_{\mu\nu}$, and $R$. No detailed general-relativity dynamics is assumed.

## Core idea

In flat spacetime, the stress tensor is often introduced through Noether’s theorem for translations. That construction is useful, but it hides two facts that become essential in curved spacetime.

First, stress tensors are not unique before extra choices are made. One may add improvement terms, total derivatives, or terms proportional to equations of motion without changing flat-space conserved charges in simple situations. Coupling the theory to a background metric makes these choices precise: choose a generally covariant action, then vary with respect to $g_{\mu\nu}$.

Second, the stress tensor is a local composite operator. Composite operators generally require their own renormalization. A schematic product

$$
\partial_\mu\phi(x)\partial_\nu\phi(x)
$$

is not defined by simply multiplying two operator-valued distributions at the same point. In correlation functions, its short-distance singularities must be subtracted locally.

Curved spacetime exposes the correct subtraction language. Since the background metric is a source, the allowed UV counterterms are the local scalar functionals of the metric and other sources. In four spacetime dimensions, the gravitational part of the counterterm action includes terms of the schematic form

$$
S_{\text{ct}}[g]
=\int d^4x\sqrt{-g}\left(
\delta\Lambda
+\delta\kappa R
+\delta\alpha R^2
+\delta\beta R_{\mu\nu}R^{\mu\nu}
+\delta\gamma R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right).
$$

In four dimensions, one often trades this basis for combinations involving the Weyl tensor squared $C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma}$, the Euler density $E_4$, $R^2$, and total derivatives. The choice is a basis choice, not a new physical principle.

## Setup and conventions

This page treats the metric as a classical source. The matter fields are quantized; the metric is not, unless explicitly stated otherwise. The generating functional is

$$
Z[g,J]=\int\mathcal D\Phi\,\exp\left(iS[\Phi;g,J]\right),
\qquad
W[g,J]=-i\log Z[g,J]
$$

in Lorentzian signature. Euclidean formulas replace $iS$ by $-S_E$ and use $W_E=-\log Z_E$. Signs in the definition of $T_{\mu\nu}$ should be translated when switching signatures.

With the Lorentzian convention stated above,

$$
\langle T_{\mu\nu}(x)\rangle
=\frac{2}{\sqrt{-g(x)}}\frac{\delta W[g,J]}{\delta g^{\mu\nu}(x)}.
$$

If the theory is diffeomorphism invariant and there is no diffeomorphism anomaly, then the renormalized expectation value obeys

$$
\nabla^\mu\langle T_{\mu\nu}\rangle_{\text{ren}}
+\sum_i \langle\mathcal O_i\rangle_{\text{ren}}\nabla_\nu J_i=0.
$$

With constant sources, or no other sources, this reduces to

$$
\nabla^\mu\langle T_{\mu\nu}\rangle_{\text{ren}}=0.
$$

The trace is more subtle. If the classical theory is Weyl invariant, one might expect $T^\mu{}_{\mu}=0$. After renormalization, the quantum expectation value can contain local curvature terms:

$$
\langle T^\mu{}_{\mu}\rangle_{\text{ren}}
=\text{beta-function terms}+\text{curvature anomaly terms}.
$$

The trace anomaly is not a failure of stress-tensor renormalization. It is one of its outputs.

## The stress tensor as a metric response

Let $S[\Phi;g]$ be a generally covariant matter action. The stress tensor is the coefficient of a metric variation. For a minimally coupled real scalar in mostly-minus signature,

$$
S=\int d^d x\sqrt{-g}\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-\frac12m^2\phi^2
\right],
$$

the metric variation gives

$$
T_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi
-g_{\mu\nu}\left(\frac12 g^{\rho\sigma}\partial_\rho\phi\partial_\sigma\phi-\frac12m^2\phi^2\right).
$$

If the scalar also has curvature coupling,

$$
S\supset \int d^d x\sqrt{-g}\left(-\frac12\xi R\phi^2\right),
$$

then $T_{\mu\nu}$ receives improvement terms involving $R_{\mu\nu}$, $R$, $\nabla_\mu\nabla_\nu\phi^2$, and $\Box\phi^2$. In flat spacetime and for a massless scalar, the improvement term reduces to the familiar local expression

$$
\Delta T_{\mu\nu}
=\xi\left(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu\right)\phi^2.
$$

The conformal value in $d$ dimensions is

$$
\xi_c=\frac{d-2}{4(d-1)}.
$$

At $m=0$ and $\xi=\xi_c$, the classical stress tensor is traceless on shell in flat spacetime. Quantum mechanically, its trace can still acquire an anomaly.

:::note[Why the metric definition is preferred]
The Noether stress tensor, the Belinfante-improved stress tensor, and the Hilbert stress tensor often agree up to improvements and equations of motion. In curved spacetime, the metric variation definition is the clean one because it fixes contact terms and makes Ward identities visible.
:::

## Why the expectation value diverges

Even in a free theory, the stress tensor contains products of fields at the same point. In a Gaussian state, Wick’s theorem reduces the expectation value to derivatives of the two-point function. For a scalar,

$$
\langle T_{\mu\nu}(x)\rangle
\sim
\lim_{x'\to x}
D_{\mu\nu}(x,x')G(x,x'),
$$

where $D_{\mu\nu}(x,x')$ is a differential operator and

$$
G(x,x')=\langle\phi(x)\phi(x')\rangle.
$$

The coincidence limit $x'\to x$ is singular. Locally, every sufficiently smooth spacetime looks approximately flat, so the leading singularities are the same kind of ultraviolet singularities already present in flat spacetime. Curvature adds subleading local terms built from $R_{\mu\nu\rho\sigma}$ and its derivatives.

A useful way to say this is:

$$
\text{UV singularity of }\langle T_{\mu\nu}\rangle
=\text{local covariant tensor built from }g_{\mu\nu}\text{ and sources}.
$$

This is why local counterterms are enough. The singular part cannot know about the global topology, the late-time state, or boundary conditions far away, except through local boundary counterterms if boundaries are present.

## Effective-action renormalization

The cleanest definition of the renormalized stress tensor uses the effective action. Start with a regulated functional

$$
W_{\text{reg}}[g,J].
$$

Its UV divergences are local functionals of the sources:

$$
W_{\text{reg}}[g,J]
=W_{\text{nonlocal, finite}}[g,J]
+W_{\text{local, div}}[g,J].
$$

Choose local counterterms

$$
S_{\text{ct}}[g,J]=-W_{\text{local, div}}[g,J]+S_{\text{finite local}}[g,J],
$$

and define

$$
W_{\text{ren}}[g,J]
=\lim_{\text{regulator removed}}
\left(W_{\text{reg}}[g,J]+S_{\text{ct}}[g,J]\right).
$$

Then

$$
\langle T_{\mu\nu}\rangle_{\text{ren}}
=\frac{2}{\sqrt{-g}}\frac{\delta W_{\text{ren}}}{\delta g^{\mu\nu}}.
$$

This definition has several advantages:

| Feature | Why it matters |
|---|---|
| Locality | Divergences are canceled by local terms. |
| Covariance | Counterterms can be chosen as diffeomorphism-invariant functionals. |
| Ward identities | Metric variation gives stress-tensor conservation relations. |
| Scheme visibility | Finite local counterterms show the allowed ambiguities explicitly. |
| State separation | Nonlocal finite pieces remain as physical state-dependent data. |

The stress tensor is therefore not renormalized by subtracting a single infinite number. It is renormalized by defining a finite source functional and differentiating it.

## Curvature counterterms in four dimensions

In four spacetime dimensions, the local gravitational counterterms through four derivatives are

$$
S_{\text{grav}}
=\int d^4x\sqrt{-g}\left[
-\Lambda
+\frac{1}{16\pi G}R
+\alpha R^2
+\beta R_{\mu\nu}R^{\mu\nu}
+\gamma R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right].
$$

The dots include higher-derivative terms and matter-source terms. The first two terms renormalize the cosmological constant and Newton constant. The four-derivative terms are needed even if gravity is only a background source, because matter loops in curved spacetime generate divergences with four derivatives of the metric.

A commonly used basis is

$$
C^2
\equiv C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma},
$$

$$
E_4
\equiv
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2,
$$

along with $R^2$ and $\Box R$ terms. In four dimensions, the integral of $E_4$ is topological on a compact manifold without boundary, but its dimensional-regularization role and boundary contributions still require care.

Varying finite local terms shifts the renormalized stress tensor by local conserved curvature tensors. For example,

$$
\Delta W_{\text{ren}}=a\int d^4x\sqrt{-g}\,R^2
$$

implies

$$
\Delta\langle T_{\mu\nu}\rangle
=\frac{2a}{\sqrt{-g}}\frac{\delta}{\delta g^{\mu\nu}}
\int d^4x\sqrt{-g}\,R^2.
$$

This shift is not a mistake. It is the curved-spacetime analog of scheme dependence.

## Point-splitting and Hadamard subtraction

The effective-action definition is conceptually clean, but in curved-spacetime calculations one often uses point-splitting. Replace the singular product at $x$ by a bilocal expression at $x$ and $x'$:

$$
T_{\mu\nu}(x)
\quad\leadsto\quad
D_{\mu\nu}(x,x')\phi(x)\phi(x').
$$

Then subtract a local singular parametrix before taking $x'\to x$:

$$
\langle T_{\mu\nu}(x)\rangle_{\text{ren}}
=\lim_{x'\to x}
D_{\mu\nu}(x,x')\left[G(x,x')-G_{\text{sing}}(x,x')\right]
+\text{local curvature terms}.
$$

For physically admissible states in curved spacetime, the short-distance singularity has Hadamard form. In four dimensions, the scalar two-point singularity has the schematic structure

$$
G_{\text{sing}}(x,x')
\sim
\frac{U(x,x')}{\sigma(x,x')}
+V(x,x')\log\left(\mu^2\sigma(x,x')\right),
$$

where $\sigma(x,x')$ is one half the squared geodesic distance and $U,V$ are local geometric biscalars. The subtraction is local and covariant; the remaining finite piece depends on the state.

The phrase “Hadamard state” means, roughly, a state whose short-distance singularity has the universal local form required for a sensible stress tensor. This condition replaces the flat-spacetime habit of choosing a preferred vacuum.

## Heat-kernel viewpoint

For a free bosonic field governed by a second-order differential operator $\Delta$, the Euclidean one-loop effective action is schematically

$$
W_E=\frac12\log\det\Delta.
$$

Using the proper-time representation,

$$
W_E=-\frac12\int_0^\infty \frac{ds}{s}\operatorname{Tr}e^{-s\Delta},
$$

up to regulator conventions. The ultraviolet region is $s\to0$. The heat kernel has an asymptotic expansion

$$
\operatorname{Tr}e^{-s\Delta}
\sim
\frac{1}{(4\pi s)^{d/2}}
\sum_{n=0}^{\infty}s^n\int d^d x\sqrt{g}\,a_n(x).
$$

The coefficients $a_n(x)$ are local curvature invariants and source-dependent local terms. In $d=4$, logarithmic divergences are governed by $a_2(x)$. This is the technical reason curvature counterterms appear with exactly the local forms listed above.

For fermions, gauge fields, ghosts, and constrained systems, the operator and trace acquire signs, indices, and gauge-fixing structure. The organizing logic remains the same: the small-$s$ heat-kernel coefficients encode local UV divergences.

## Ward identities and conservation

If the regulator and counterterms preserve diffeomorphism invariance, then $W_{\text{ren}}[g,J]$ is invariant under infinitesimal diffeomorphisms. With no other sources, this gives

$$
\nabla^\mu\langle T_{\mu\nu}\rangle_{\text{ren}}=0.
$$

With sources $J_i(x)$ coupled to operators $\mathcal O_i(x)$,

$$
W[g,J]
ightarrow W[g+\mathcal L_\xi g,J+\mathcal L_\xi J]
$$

implies

$$
\nabla^\mu\langle T_{\mu\nu}\rangle_{\text{ren}}
+\sum_i\langle\mathcal O_i\rangle_{\text{ren}}\nabla_\nu J_i=0
$$

for scalar sources. More general sources, such as background gauge fields, add the corresponding current-force terms.

This identity is non-negotiable if diffeomorphism symmetry is non-anomalous. A proposed stress-tensor subtraction that violates conservation is not a legitimate covariant renormalization prescription unless a genuine gravitational anomaly is present.

## Trace anomaly

For a classically Weyl-invariant theory, one expects

$$
T^\mu{}_{\mu}=0
$$

up to equations of motion. Quantum renormalization can break this expectation even when diffeomorphism invariance is preserved.

In four dimensions, the trace anomaly of a conformal field theory has the schematic form

$$
\langle T^\mu{}_{\mu}\rangle
=\frac{1}{16\pi^2}\left(
 c\,C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma}
-a\,E_4
+b\,\Box R
\right),
$$

with convention-dependent signs in the literature. The coefficients $a$ and $c$ are physical CFT data. The coefficient $b$ is scheme-dependent because it can be shifted by a finite local $R^2$ counterterm.

For a general interacting QFT with running couplings, the trace also contains beta-function terms:

$$
\langle T^\mu{}_{\mu}\rangle
=\beta^i\langle\mathcal O_i\rangle
+\text{curvature anomaly terms}
+\text{mass terms}.
$$

Thus trace anomalies connect stress-tensor renormalization to the renormalization group. They are not a separate species of magic.

## Semiclassical gravity

If the metric is treated dynamically at long distances, the renormalized stress tensor appears in the semiclassical Einstein equation,

$$
G_{\mu\nu}+\Lambda g_{\mu\nu}
+\text{higher-curvature terms}
=8\pi G\,\langle T_{\mu\nu}\rangle_{\text{ren}}.
$$

This equation only makes sense after the gravitational couplings on the left-hand side have been renormalized. Matter loops shift $\Lambda$, $G$, and higher-curvature coefficients. The higher-curvature terms are not exotic additions; they are exactly the counterterms required by the source functional.

The equation is also state-dependent. The local UV subtraction is universal, but the finite value of $\langle T_{\mu\nu}\rangle_{\text{ren}}$ depends on whether the state is vacuum-like, thermal, cosmological, black-hole, nonequilibrium, or otherwise.

:::caution[Do not overread semiclassical gravity]
The semiclassical equation is an EFT equation for expectation values in an appropriate regime. It is not a complete theory of quantum gravity and does not by itself describe all metric fluctuations or measurement questions.
:::

## Local ambiguity and physical observables

Finite local counterterms produce local changes in $\langle T_{\mu\nu}\rangle$. This means that a single local value of the stress tensor is not always a scheme-independent observable. The ambiguity is controlled, however. It is local, covariant, and conserved.

Physical quantities are obtained after specifying the renormalization convention or by comparing quantities insensitive to the local ambiguity. Examples include:

| Quantity | What must be specified |
|---|---|
| Vacuum energy density | cosmological constant renormalization convention |
| Casimir energy | geometry, boundary conditions, subtraction convention |
| Trace anomaly coefficients | convention for curvature basis and total derivatives |
| Semiclassical backreaction | renormalized $\Lambda$, $G$, and higher-curvature couplings |
| Energy flux at infinity | state and asymptotic definition of particles or observers |

This is the curved-spacetime version of a familiar lesson: renormalized local quantities depend on conventions, while properly defined physical comparisons do not.

## Flat-spacetime limit

In flat spacetime, all curvature counterterms vanish or reduce to constants. One might think curved-spacetime renormalization is irrelevant for ordinary QFT. That misses the point.

Coupling to $g_{\mu\nu}$ is the natural way to define $T_{\mu\nu}$ and its contact terms. Even if one ultimately sets

$$
g_{\mu\nu}=\eta_{\mu\nu},
$$

metric variation keeps track of how stress tensors appear inside correlation functions:

$$
\langle T_{\mu\nu}(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=\frac{2}{\sqrt{-g(x)}}
\frac{\delta}{\delta g^{\mu\nu}(x)}
\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle_g
\bigg|_{g=\eta}.
$$

This is especially important for Ward identities, conformal theories, trace anomalies, energy conditions, entanglement calculations, and transport coefficients.

## Common pitfalls

**Using the Noether tensor when the Hilbert tensor is needed.** The Noether tensor is useful for conserved charges in flat spacetime. Metric response, trace anomalies, and curved-background Ward identities require the Hilbert tensor or a precisely related improved tensor.

**Subtracting the flat divergence and forgetting curvature.** Flat-space subtraction removes only the leading local singularity. Curved spacetime generates curvature-dependent local divergences that must also be subtracted.

**Treating $\langle T_{\mu\nu}\rangle$ as purely local.** The divergent part is local. The finite physical part can be nonlocal and state-dependent.

**Confusing trace anomaly with non-conservation.** In ordinary even-dimensional CFTs without gravitational anomalies, the trace can be anomalous while covariant conservation remains true.

**Calling scheme dependence arbitrariness.** Finite local counterterms give controlled local shifts. They do not allow arbitrary nonlocal changes or violations of Ward identities.

**Forgetting boundary counterterms.** If the spacetime has a boundary, local boundary invariants must also be included. Bulk counterterms alone are not the full story.

## Relations to other pages

This page is the curved-spacetime continuation of [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/) and [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/). The metric is simply a source for a particularly important composite operator.

It prepares [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/), where the trace of $\langle T_{\mu\nu}\rangle$ becomes an RG diagnostic, and [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/), where the local geometric terms are classified.

It also connects to [Local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/), where spacetime-dependent sources and Weyl transformations organize trace identities, and to [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/), where the same curvature terms are interpreted as EFT Wilson coefficients for gravity.

## Research status

The local ultraviolet structure of stress-tensor renormalization in smooth curved backgrounds is established. Covariant counterterms, point-splitting, heat-kernel coefficients, effective actions, and trace anomalies are standard tools.

Important subtleties remain active in broader settings: interacting gauge theories on curved manifolds, chiral and gravitational anomalies, boundaries and defects, non-Hadamard states, real-time nonequilibrium spacetimes, de Sitter observables, black-hole backreaction, and the transition from semiclassical gravity to a full quantum theory of geometry.

The right status summary is:

$$
\text{local UV renormalization is understood; global state-dependent physics can be hard.}
$$

## Exercises

### Exercise 1: Check the metric-variation sign

For the minimally coupled scalar action

$$
S=\int d^d x\sqrt{-g}\left[
\frac12 g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
-\frac12m^2\phi^2
\right],
$$

using

$$
\delta\sqrt{-g}=-\frac12\sqrt{-g}\,g_{\mu\nu}\delta g^{\mu\nu},
$$

show that the definition

$$
\delta S=\frac12\int d^d x\sqrt{-g}\,T_{\mu\nu}\delta g^{\mu\nu}
$$

gives

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L.
$$

<details><summary><strong>Solution</strong></summary>

The variation of the Lagrangian density with respect to the inverse metric is

$$
\delta\mathcal L
=\frac12\partial_\mu\phi\partial_\nu\phi\,\delta g^{\mu\nu}.
$$

The variation of the volume element contributes

$$
\delta\sqrt{-g}\,\mathcal L
=-\frac12\sqrt{-g}\,g_{\mu\nu}\mathcal L\,\delta g^{\mu\nu}.
$$

Therefore

$$
\delta S
=\frac12\int d^d x\sqrt{-g}\left(
\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L
\right)\delta g^{\mu\nu}.
$$

Comparing with the defining variation gives

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi-g_{\mu\nu}\mathcal L.
$$

For $g_{\mu\nu}=\eta_{\mu\nu}$, the $00$ component is positive for ordinary scalar excitations.

</details>

### Exercise 2: Why curvature counterterms have four derivatives

In four dimensions, show by dimensional analysis that $R^2$ and $R_{\mu\nu}R^{\mu\nu}$ can appear as logarithmic counterterms in the effective action of a dimensionless one-loop determinant.

<details><summary><strong>Solution</strong></summary>

In natural units,

$$
[d^4x]=-4,
\qquad
[\sqrt{-g}]=0,
\qquad
[R]=2.
$$

Therefore

$$
\left[\int d^4x\sqrt{-g}\,R^2\right]
=-4+4=0,
$$

and similarly

$$
\left[\int d^4x\sqrt{-g}\,R_{\mu\nu}R^{\mu\nu}\right]=0.
$$

Dimensionless local functionals can multiply logarithmic divergences in four dimensions. This is why four-derivative curvature invariants appear in the logarithmically divergent part of the one-loop effective action.

</details>

### Exercise 3: Scheme dependence from a finite local counterterm

Suppose two renormalization schemes differ by

$$
\Delta W=a\int d^4x\sqrt{-g}\,R^2.
$$

Show that the corresponding stress tensors differ by a local conserved curvature tensor, assuming no boundary terms contribute.

<details><summary><strong>Solution</strong></summary>

The shift in the stress tensor is

$$
\Delta\langle T_{\mu\nu}\rangle
=\frac{2a}{\sqrt{-g}}\frac{\delta}{\delta g^{\mu\nu}}
\int d^4x\sqrt{-g}\,R^2.
$$

This expression is local because it is obtained by varying a local functional of the metric. It is covariant because the functional is diffeomorphism invariant. Under an infinitesimal diffeomorphism, the variation of the functional vanishes. The corresponding Noether identity implies

$$
\nabla^\mu\Delta\langle T_{\mu\nu}\rangle=0,
$$

up to boundary contributions. Thus the scheme change is local and conserved.

</details>

## References

- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, for the standard physics treatment of point-splitting, stress tensors, and trace anomalies.
- R. M. Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, for the local-covariant definition of the renormalized stress tensor and the axiomatic constraints on its ambiguity.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, for effective-action and renormalization methods.
- S. M. Christensen, classic papers on stress-tensor renormalization and point splitting in curved spacetime.
- B. S. DeWitt, *The Dynamical Theory of Groups and Fields*, for heat-kernel and proper-time methods.
- M. J. Duff, "Twenty years of the Weyl anomaly," for trace-anomaly conventions and coefficient dictionaries.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on dilatations and Callan–Symanzik equations, for the flat-space RG and anomaly intuition.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I and II, for renormalization, effective actions, and EFT perspective.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods and the relation between local UV structure and renormalization.

## Version history

- 2026-06-19: First polished draft. Defined the stress tensor as metric response, explained curved-spacetime composite-operator renormalization, curvature counterterms, Ward identities, trace anomaly structure, and local scheme dependence.
