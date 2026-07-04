---
title: "Effective Potential and Convexity"
description: "Explains the exact effective potential as a Legendre transform, why it is convex, and how this is reconciled with the familiar nonconvex loop potential."
sidebar:
  label: "Effective Potential"
  order: 6
level: Graduate
status: "Polished draft"
source: "Coleman; Weinberg; Srednicki; Schwartz; Zinn-Justin; Shifman."
topics:
  - effective potential
  - convexity
  - Legendre transform
  - spontaneous symmetry breaking
  - Maxwell construction
  - metastability
  - Wilsonian effective action
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - effective-potential
  - convexity
  - spontaneous-symmetry-breaking
researchStatus:
  established:
    - "The exact one-particle-irreducible effective potential defined by a Legendre transform is convex; nonconvex loop potentials are local semiclassical approximations or Wilsonian coarse-grained objects, not the final exact potential."
  active:
    - "Gauge-invariant formulations, functional renormalization-group treatments, real-time metastability, and strongly coupled phase diagnostics remain active contexts where effective-potential language must be used carefully."
---

## Summary

The **effective potential** is the constant-field part of the one-particle-irreducible effective action. It is the object whose derivative is the source needed to hold a field expectation value fixed. In Euclidean conventions, for a constant source $h$ and constant expectation value $\bar\phi$, the exact effective potential is the Legendre transform

$$
V_{\rm eff}(\bar\phi)=\frac{1}{\beta V}\,\Gamma[\bar\phi]
=\text{Legendre transform of }w(h),
$$

where

$$
w(h)=\frac{1}{\beta V}\log Z[h]
$$

is the source-dependent free-energy generator. More explicitly, with the source convention used in this chapter,

$$
V_{\rm eff}(\bar\phi)=\operatorname{sup}_{h}\left(h\bar\phi-w(h)\right),
\qquad
\frac{dV_{\rm eff}}{d\bar\phi}=h.
$$

The important theorem is simple and frequently forgotten:

$$
\text{the exact Legendre-transform effective potential is convex.}
$$

This does **not** mean that the familiar double-well picture is useless. It means that the familiar nonconvex tree-level or one-loop potential is not the exact zero-momentum Legendre-transform potential. It is a local saddle-point or coarse-grained description that can be the right tool for masses, barriers, tunneling estimates, radiative symmetry breaking, and metastability.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A local nonconvex potential becomes an exact convex effective potential with a flat coexistence region after the Legendre transform and infinite-volume limit.](/figures/nonperturbative-qft/effective-potential-convexity.svg)

<figcaption>

A nonconvex semiclassical potential can have two local minima and a barrier. The exact source free energy develops a cusp at a first-order coexistence point, and its Legendre transform gives a convex effective potential. In a broken $\mathbb Z_2$ phase, the interval $-v_R\le \bar\phi\le v_R$ is a coexistence region, not a new continuum of pure homogeneous vacua.

</figcaption>
</figure>

The conceptual payoff is huge. Convexity explains why the exact effective potential seems to “erase” the barrier between degenerate vacua, while semiclassics and false-vacuum decay still need local nonconvex potentials. The tension dissolves once one asks which object is being computed.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), and [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/). The pages [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) and [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explain the source and limit conventions used below.

No detailed loop calculation is assumed. The one-loop formula appears only to identify which approximation is being discussed.

## Core idea

The phrase “the effective potential” is overloaded. A lot of confusion comes from using one phrase for several related but different objects.

| Object | Definition | Convex? | Main use |
|---|---|---:|---|
| Classical potential | Potential term in the bare or renormalized Lagrangian. | Not necessarily | Classical vacua and tree-level saddles. |
| Loop-expanded 1PI potential | Saddle expansion of the effective action around a background field. | Not necessarily at finite loop order | Radiative corrections, local masses, metastable branches. |
| Wilsonian potential | Potential in an action where modes above a scale $k$ have been integrated out. | Not necessarily | Coarse-grained physics at finite resolution. |
| Exact 1PI potential | Legendre transform of the exact source generator. | Yes | Equation of state and infinite-volume phase coexistence. |
| Constrained potential | Free-energy cost of imposing an averaged field value. | Convex after full thermodynamic limit | Phase coexistence, large deviations, lattice diagnostics. |

The exact effective potential is best viewed as an **equation of state**. Its derivative is the external source required to maintain a chosen expectation value:

$$
\frac{dV_{\rm eff}}{d\bar\phi}=h.
$$

At $h=0$, the stationary points of the exact potential are physical zero-source phases. If the theory has a unique symmetric vacuum, this looks like the familiar statement that the vacuum minimizes $V_{\rm eff}$. If the theory has several coexisting phases, the exact $V_{\rm eff}$ is still convex and may contain flat regions.

## Setup and conventions

We use the conventions of [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). Let $\phi(x)$ be a renormalized scalar operator or order-parameter field. In a finite Euclidean box of spacetime volume $\beta V_L$, introduce a source $J(x)$ by

$$
Z_{\beta,L}[J]
=\int \mathcal D\Phi\,
\exp\left[-S_E[\Phi]+\int d^dx\,J(x)\phi(x)\right].
$$

Define

$$
W_{\beta,L}[J]=\log Z_{\beta,L}[J],
\qquad
\bar\phi_J(x)=\frac{\delta W_{\beta,L}}{\delta J(x)}.
$$

The Euclidean 1PI effective action is the Legendre transform

$$
\Gamma_{\beta,L}[\bar\phi]
=\operatorname{sup}_J\left\{
\int d^dx\,J(x)\bar\phi(x)-W_{\beta,L}[J]
\right\}.
$$

Where the source-field map is invertible, this gives

$$
\frac{\delta \Gamma}{\delta \bar\phi(x)}=J(x).
$$

For a constant source $J(x)=h$ and a translation-invariant expectation value $\bar\phi(x)=\bar\phi$, define

$$
w_{\beta,L}(h)=\frac{1}{\beta V_L}W_{\beta,L}[h],
\qquad
V_{{\rm eff},\beta,L}(\bar\phi)=\frac{1}{\beta V_L}\Gamma_{\beta,L}[\bar\phi].
$$

The infinite-volume effective potential is obtained after the thermodynamic and zero-temperature limits, when they exist:

$$
V_{\rm eff}(\bar\phi)
=\lim_{L\to\infty}\lim_{\beta\to\infty}
V_{{\rm eff},\beta,L}(\bar\phi).
$$

Different pages sometimes subtract the vacuum energy so that the minimum value of $V_{\rm eff}$ is zero. This page leaves additive constants arbitrary. Only differences, derivatives, and convexity are meaningful.

## Convexity from source fluctuations

The convexity of $W[J]$ follows from positivity of fluctuations. For any real test function $f(x)$,

$$
\int d^dx\,d^dy\,
 f(x)\frac{\delta^2 W}{\delta J(x)\delta J(y)}f(y)
=
\left\langle
\left(\int d^dx\,f(x)\phi(x)\right)^2
\right\rangle_c
\ge0.
$$

Thus $W[J]$ is a convex functional of $J$. A Legendre transform of a convex functional is convex, so $\Gamma[\bar\phi]$ is convex as a functional of $\bar\phi$.

For constant fields, the statement reduces to elementary thermodynamics. Let

$$
\bar\phi(h)=\frac{dw(h)}{dh}.
$$

Then

$$
\frac{d\bar\phi}{dh}
=\frac{d^2w}{dh^2}
=\frac{1}{\beta V_L}
\left\langle
\left(\int d^dx\,\phi(x)\right)^2
\right\rangle_c
\ge0.
$$

Where the relation between $h$ and $\bar\phi$ is differentiable and invertible,

$$
\frac{d^2V_{\rm eff}}{d\bar\phi^2}
=\frac{dh}{d\bar\phi}
=\left(\frac{d\bar\phi}{dh}\right)^{-1}
\ge0.
$$

This is the zero-momentum version of the more general relation

$$
\Gamma^{(2)}=(W^{(2)})^{-1},
$$

with the inverse understood on the space of fluctuations for which the Legendre transform is nonsingular. Convexity is therefore not a perturbative accident. It is built into the definition of the exact 1PI effective action.

## Broken phases and the Maxwell construction

Consider a broken $\mathbb Z_2$ phase with pure vacua satisfying

$$
\langle\phi\rangle_+=+v_R,
\qquad
\langle\phi\rangle_-=-v_R.
$$

A source $h$ coupled as $+h\int\phi$ selects one vacuum or the other. In the infinite-volume limit,

$$
\lim_{h\downarrow0}\bar\phi(h)=+v_R,
\qquad
\lim_{h\uparrow0}\bar\phi(h)=-v_R.
$$

Equivalently, the source generator $w(h)$ has a cusp at $h=0$. Near coexistence,

$$
w(h)=w(0)+v_R|h|+\cdots,
$$

where the omitted terms depend on the susceptibilities inside each phase. The Legendre transform of the cusp contains a flat segment:

$$
V_{\rm eff}(\bar\phi)=V_{\rm min}
\qquad
\text{for}\qquad
-v_R\le\bar\phi\le v_R.
$$

This is the field-theory version of the Maxwell construction. It is exactly analogous to the flat part of a thermodynamic free energy at phase coexistence.

The flat segment should not be overinterpreted. The endpoints $\bar\phi=\pm v_R$ correspond to pure broken vacua. A point with $|\bar\phi|<v_R$ is usually a mixed or phase-separated configuration in the infinite-volume limit, not a new pure homogeneous vacuum. In a very large box, one can realize an average value between $-v_R$ and $+v_R$ by occupying a fraction of space with the $+$ phase and the rest with the $-$ phase. The domain-wall cost scales like area, while the volume scales like volume, so the wall contribution to the **energy density** vanishes as $L\to\infty$.

This is why exact convexity and spontaneous symmetry breaking are compatible. The exact potential is convex because it sees all possible phase mixtures. A chosen pure broken vacuum is selected by a source or boundary condition before the infinite-volume limit is completed.

## Why the loop potential can be nonconvex

The familiar one-loop expression has the schematic Euclidean form

$$
V_{\rm 1-loop}(\varphi)
=V_{\rm cl}(\varphi)
+\frac12\int\frac{d^dp}{(2\pi)^d}\,
\log\left[p^2+M^2(\varphi)\right]
+V_{\rm ct}(\varphi),
$$

where

$$
M^2(\varphi)=\frac{d^2V_{\rm cl}}{d\varphi^2}
$$

in the simplest one-scalar example, and $V_{\rm ct}$ denotes counterterms. This formula is obtained by expanding the path integral around a **single homogeneous background** and integrating Gaussian fluctuations. It is a saddle-point approximation, not the full Legendre transform of the exact theory.

In a double-well model, the tree-level and low-order loop potentials are nonconvex between the wells. That nonconvexity is not a contradiction. It says that the chosen homogeneous background is locally unstable in the spinodal region. The exact path integral also contains large domains, interfaces, tunneling effects, and infrared fluctuations that are invisible in a naive local expansion around one unstable homogeneous configuration.

The low-order loop potential remains useful because it answers a different question: what is the local semiclassical energy density near a chosen field configuration before phase coexistence has been fully accounted for? That is the right question when estimating local masses, identifying approximate minima, studying radiative symmetry breaking, or preparing a bounce calculation for false-vacuum decay.

A good mental model is:

$$
\text{loop potential} = \text{local chart},
\qquad
\text{exact convex potential} = \text{global thermodynamic envelope}.
$$

Both are useful. They are not the same object.

## Masses, susceptibilities, and the flat region

In a simple unbroken phase, the curvature of the exact effective potential at its minimum is the inverse zero-momentum susceptibility:

$$
V_{\rm eff}''(v_R)=\chi^{-1},
\qquad
\chi=\int d^dx\,\langle\phi(x)\phi(0)\rangle_c.
$$

For a relativistic scalar with a stable isolated particle and standard normalization, this is closely related to the inverse zero-momentum propagator. In weak coupling one often says, loosely, that the curvature gives the mass squared.

In a broken phase with a flat coexistence region, that slogan needs care. Inside the interval

$$
-v_R<\bar\phi<v_R,
$$

the exact convex potential has zero curvature. This does **not** mean the radial particle in either pure vacuum is massless. It means the zero-momentum constrained average can be changed by changing the proportions of coexisting phases at no cost in energy density.

The physical mass spectrum of a pure phase is extracted from connected correlation functions in that selected phase, or from the local effective action expanded around an endpoint such as $\bar\phi=+v_R$. It is not extracted from the curvature of the convex envelope in the middle of a coexistence interval.

For continuous symmetry breaking, a related but distinct phenomenon occurs. The exact potential is flat along symmetry directions because all points on the symmetry orbit have the same energy density. Those tangent directions are Goldstone directions under the usual hypotheses. But even there, one must distinguish tangent Goldstone directions from radial massive fluctuations and from phase coexistence between disconnected vacua.

## Wilsonian potentials and finite resolution

The Wilsonian effective action at a scale $k$ integrates out modes with momenta above $k$ but leaves lower-momentum modes dynamical. Its potential is often denoted $U_k(\varphi)$. Unlike the exact $k=0$ 1PI potential, $U_k$ need not be convex.

This is not a bug. A finite-$k$ Wilsonian potential describes physics at finite resolution. At that resolution the system has not yet used arbitrarily long-wavelength domains to convexify the potential. As $k$ is lowered, long-distance fluctuations increasingly flatten unstable regions. In many functional-renormalization-group descriptions, convexity emerges only in the final $k\to0$ limit.

This distinction is one reason effective-potential plots in research papers can look different while all being legitimate. A paper may be plotting a tree-level potential, a renormalized one-loop potential, a Wilsonian coarse-grained potential, a constrained lattice potential, or the exact 1PI Legendre-transform potential. The caption had better say which one. When it does not, small chaos goblin enters the room.

## Gauge and coordinate dependence

Effective potentials are especially delicate in gauge theories. A gauge-fixed potential for a gauge-variant scalar background can be useful for calculations, but it is not itself a gauge-invariant observable. Away from extrema, the shape of the gauge-fixed effective potential can depend on the gauge-fixing parameter and on the field coordinates.

The safe statements are more limited:

- values of the effective action at corresponding physical extrema are gauge independent;
- spectra, transition rates, latent heats, and properly defined response functions must be gauge invariant;
- gauge-variant VEVs are not physical order parameters by themselves;
- gauge-invariant composites, line operators, spectra, and symmetry realization carry the phase information.

For example, the gauge-fixed Higgs-field effective potential is a powerful perturbative tool. But the nonperturbative distinction between Higgs, confinement, and Coulomb-like behavior should be phrased in terms of gauge-invariant diagnostics whenever possible.

Field redefinitions also matter. The exact effective action is a functional of chosen variables, and the ordinary potential $V_{\rm eff}(\bar\phi)$ is only the constant-field part in those variables. The physics is not “the shape of a plotted curve” by itself; the physics is encoded in the full effective action, its extrema, its correlation functions, and its response to sources.

## Metastability and false vacua

A common worry is: if the exact effective potential is convex, where did the barrier for false-vacuum decay go?

The answer is that false-vacuum decay is not computed from the flat convex envelope. It is computed from a local semiclassical effective action appropriate to the metastable branch. The bounce is an inhomogeneous saddle of the Euclidean action. It knows about gradient energy, wall tension, and the local barrier separating the false vacuum from the true one.

The exact infinite-volume static effective potential answers a different thermodynamic question: what is the minimal energy density compatible with a fixed spatially averaged field? Once arbitrarily large bubbles and phase-separated configurations are allowed, the convex envelope wins as an energy-density statement.

Thus:

$$
\text{convexity does not eliminate metastability; it changes which potential answers which question.}
$$

The page on false vacua later in this chapter will use this distinction repeatedly.

## Common pitfalls

**Calling every loop-corrected potential “the” effective potential.** The exact 1PI potential is convex. A nonconvex loop potential is a local approximation or a coarse-grained object. Useful, yes. Exact Legendre-transform potential, no.

**Interpreting the flat segment as many pure vacua.** In a broken $\mathbb Z_2$ theory, the flat segment between $-v_R$ and $+v_R$ represents phase coexistence or mixed states. The pure homogeneous broken vacua are the endpoints.

**Reading the radial mass from the middle of the flat region.** The curvature inside a coexistence interval is not the radial particle mass. The spectrum is extracted in a selected pure phase from correlation functions or from the local branch near an endpoint.

**Forgetting the source.** The effective potential is an equation of state: $dV_{\rm eff}/d\bar\phi=h$. Without specifying the source convention, signs and physical interpretation become slippery.

**Confusing Wilsonian and 1PI potentials.** A Wilsonian potential at finite scale $k$ need not be convex. The exact 1PI potential at $k=0$ is convex.

**Using gauge-dependent shapes as physical phase diagrams.** Gauge-fixed potentials can guide calculations, but physical statements require gauge-invariant observables or gauge-independent quantities at extrema.

## Relations to other pages

- [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains source selection and one-point functions.
- [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/) explains why several pure vacua can coexist in infinite volume.
- [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) gives the simplest setting for the Maxwell-construction flat region.
- [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) explains symmetry orbits, pure phases, and Goldstone directions.
- [Moduli Spaces Preview](/nonperturbative-qft/vacuum-structure-phases/moduli-spaces-preview/) explains genuine continuous families of vacua, where flat directions are not merely coexistence intervals.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains why local potentials are only one kind of phase diagnostic.

## Research status

The convexity of the exact Legendre-transform effective potential is textbook-standard. The reconciliation between convexity and spontaneous symmetry breaking through phase coexistence is also standard, though it is often underemphasized in first courses.

Active work concerns how best to use effective-potential language in gauge theories, finite-temperature transitions, nonequilibrium dynamics, strongly coupled theories, functional renormalization, and lattice simulations. In these settings, the main challenge is rarely the formal convexity theorem itself; it is choosing the right gauge-invariant or coarse-grained object for the physical question.

## Exercises

### Exercise 1: Convexity from a variance

Let

$$
w(h)=\frac{1}{\beta V}\log Z(h),
\qquad
Z(h)=\operatorname{Tr}\exp[-\beta H+\beta h O],
$$

where $O$ is a Hermitian spatial average of an order parameter. Show that $w''(h)\ge0$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate once:

$$
w'(h)=\langle O\rangle_h.
$$

Differentiating again gives the connected fluctuation,

$$
w''(h)=\beta\left(\langle O^2\rangle_h-\langle O\rangle_h^2\right).
$$

The variance of a Hermitian operator is nonnegative, so

$$
w''(h)\ge0.
$$

With field-theory normalization, $O$ may be an integrated operator divided by volume; the same argument gives the susceptibility per unit volume.

</details>

### Exercise 2: Legendre transform of a cusp

Suppose near $h=0$ the infinite-volume source generator is

$$
w(h)=w_0+v|h|.
$$

Compute

$$
V(\bar\phi)=\operatorname{sup}_h\left(h\bar\phi-w(h)\right)
$$

for $|\bar\phi|\le v$.

<details>
<summary><strong>Solution</strong></summary>

For $h>0$,

$$
h\bar\phi-w(h)=h(\bar\phi-v)-w_0.
$$

For $h<0$,

$$
h\bar\phi-w(h)=h(\bar\phi+v)-w_0.
$$

If $|\bar\phi|\le v$, both expressions are maximized at $h=0$. Therefore

$$
V(\bar\phi)=-w_0
\qquad
\text{for}\qquad
-v\le\bar\phi\le v.
$$

The Legendre transform is flat on the interval between the one-sided derivatives of $w(h)$ at the cusp.

</details>

### Exercise 3: Curvature and susceptibility

Assume $w(h)$ is twice differentiable and strictly convex near some source $h_0$, with

$$
\bar\phi=\frac{dw}{dh}.
$$

Show that

$$
\frac{d^2V_{\rm eff}}{d\bar\phi^2}=\chi^{-1},
\qquad
\chi=\frac{d\bar\phi}{dh}.
$$

<details>
<summary><strong>Solution</strong></summary>

The Legendre transform gives

$$
V_{\rm eff}(\bar\phi)=h\bar\phi-w(h),
$$

where $h$ is chosen so that $\bar\phi=w'(h)$. Differentiating,

$$
\frac{dV_{\rm eff}}{d\bar\phi}
=h+\bar\phi\frac{dh}{d\bar\phi}
-w'(h)\frac{dh}{d\bar\phi}
=h.
$$

Differentiating again gives

$$
\frac{d^2V_{\rm eff}}{d\bar\phi^2}
=\frac{dh}{d\bar\phi}
=\left(\frac{d\bar\phi}{dh}\right)^{-1}
=\chi^{-1}.
$$

</details>

### Exercise 4: Why a barrier can still matter

In one paragraph, explain why the exact convex effective potential does not make false-vacuum decay impossible.

<details>
<summary><strong>Solution</strong></summary>

False-vacuum decay is controlled by an inhomogeneous Euclidean saddle, the bounce, computed using a local effective action for the metastable branch. The exact convex potential instead gives the minimal static energy density for a fixed spatial average after all phase-separated configurations are allowed. These are different variational problems. Convexity removes the barrier from the zero-momentum thermodynamic envelope, not from the local semiclassical dynamics relevant to nucleating a bubble.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially “Secret symmetry” for the effective potential and “The fate of the false vacuum” for metastability.
- M. Srednicki, *Quantum Field Theory*, chapter on the quantum action and chapters on spontaneous symmetry breaking.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on vacuum expectation values, path integrals, and spontaneous symmetry breaking.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean sources, effective actions, order parameters, and convexity.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for effective actions, symmetry realization, and vacuum structure.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters on phases, false-vacuum decay, and nonperturbative gauge dynamics.
- R. Jackiw, “Functional evaluation of the effective potential,” for a classic treatment of the loop effective potential.
- J. Iliopoulos, C. Itzykson, and A. Martin, “Functional methods and perturbation theory,” for early effective-action technology.

## Version history

- **2026-06-26:** Initial polished draft.
