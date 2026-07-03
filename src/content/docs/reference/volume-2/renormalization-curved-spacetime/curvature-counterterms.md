---
title: "Curvature Counterterms"
description: "The local gravitational counterterms required by renormalization in curved backgrounds, including cosmological, Einstein–Hilbert, quadratic-curvature, boundary, and EFT terms."
sidebar:
  label: "Curvature Counterterms"
  order: 30
level: Advanced
status: "Polished draft"
source: "Birrell and Davies; Parker and Toms; Wald; Fulling; DeWitt; Christensen; Donoghue; Burgess 2020; Weinberg 1995; Zinn-Justin 2021."
topics:
  - curvature counterterms
  - curved spacetime
  - heat kernel
  - gravitational effective action
  - trace anomaly
  - gravitational EFT
canonicalTopics:
  - curvature-counterterms
  - gravitational-counterterms
  - curved-spacetime-renormalization
  - gravitational-eft
researchStatus:
  established:
    - "Locality and diffeomorphism covariance require all local curvature invariants allowed by symmetries to appear as counterterms in the generating functional when QFT is placed on a curved background."
  active:
    - "Boundaries, defects, gauge backgrounds, nonlocal infrared terms, dynamical gravity, Lorentzian states, and cosmological observables add important subtleties beyond the local bulk counterterm basis."
---

## Summary

Curvature counterterms are local metric terms added to the bare or regulated generating functional so that quantum field theory in a curved background has finite stress-tensor correlators and a finite effective action. In flat spacetime, short-distance divergences force counterterms such as $\delta m^2\phi^2$ and $\delta\lambda\phi^4$. In curved spacetime, the metric itself is a source, so locality and diffeomorphism covariance allow local counterterms built from curvature.

In four dimensions, the local gravitational part of the action has the schematic derivative expansion

$$
S_{\text{grav,loc}}[g]
=\int d^4x\sqrt{-g}\left(
 c_0
+c_1 R
+c_2 R^2
+c_3 R_{\mu\nu}R^{\mu\nu}
+c_4 R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right),
$$

or equivalently a basis involving

$$
C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma},
\qquad
E_4,
\qquad
R^2,
\qquad
\Box R.
$$

The coefficients include divergent pieces, finite scheme choices, and — if gravity is dynamical — physical EFT Wilson coefficients. The rule is simple but powerful:

$$
\text{curved background}+
\text{UV locality}
\Longrightarrow
\text{local curvature counterterms}.
$$

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 58rem;">

![Curvature counterterm basis by derivative order](/figures/renormalization-rg-eft/curvature-counterterm-basis.svg)

<figcaption>

Curvature counterterms form a derivative expansion of local diffeomorphism-invariant metric functionals. Zeroth order gives the cosmological term, two derivatives give the Einstein–Hilbert term, four derivatives give quadratic-curvature terms such as $C^2$, $E_4$, and $R^2$, and higher orders give the gravitational EFT tower.

</figcaption>
</figure>

## Prerequisites

You should know [Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/), [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Power Counting and Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/), and [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/).

You also need the geometric meaning of $R^\rho{}_{\sigma\mu\nu}$, $R_{\mu\nu}$, $R$, $\sqrt{-g}$, covariant derivatives, and integration by parts on a manifold. This page uses those objects as tools rather than teaching differential geometry from scratch.

## Core idea

When the metric is a background source, the generating functional is a functional of $g_{\mu\nu}$:

$$
W[g,J].
$$

Renormalization of this functional must respect locality and diffeomorphism covariance. Therefore its UV-sensitive part must be a sum of local scalar densities built from the background fields. If the only background is the metric, the counterterms are local curvature invariants.

This is not a statement about quantum gravity being fundamental. Even for a free scalar field on a fixed classical curved spacetime, one-loop determinants generate divergences proportional to

$$
\int\sqrt g,
\qquad
\int\sqrt g\,R,
\qquad
\int\sqrt g\,R^2,
\qquad
\int\sqrt g\,R_{\mu\nu}R^{\mu\nu},
\qquad
\int\sqrt g\,R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}.
$$

Those terms must be available as counterterms if $\langle T_{\mu\nu}\rangle$ and its correlation functions are to be finite after metric variation.

The conceptual leap is modest but important:

$$
\text{renormalizing }W[g]
\quad\text{is stronger than}\quad
\text{renormalizing flat-space amplitudes}.
$$

Flat-space amplitudes may not see every curvature counterterm because many curvature invariants vanish when $g_{\mu\nu}=\eta_{\mu\nu}$. But the stress tensor and its correlators do see them through variations around flat space.

## Setup and conventions

This page treats the metric as a classical source unless otherwise stated. In Lorentzian signature, the local gravitational terms are written schematically as

$$
S_{\text{loc}}[g]
=\int d^d x\sqrt{-g}\,\mathcal L_{\text{loc}}(g).
$$

In Euclidean signature, replace $\sqrt{-g}$ by $\sqrt g$ and the action conventions accordingly. Since different gravity references choose different signs for the Einstein–Hilbert term and Riemann tensor, this page focuses on the invariant operator content rather than signs in the gravitational equations of motion.

The stress tensor is obtained by variation:

$$
\langle T_{\mu\nu}(x)\rangle
=\frac{2}{\sqrt{-g(x)}}\frac{\delta W_{\text{ren}}}{\delta g^{\mu\nu}(x)}
$$

in the Lorentzian convention used in this volume. Therefore adding a finite local counterterm shifts $\langle T_{\mu\nu}\rangle$ by a local conserved curvature tensor. This is a local scheme ambiguity, not an inconsistency.

## Derivative expansion of local metric terms

Curvature carries two derivatives of the metric. The local gravitational action is therefore naturally organized by derivative order.

| Derivative order | Local terms in four dimensions | Interpretation |
|---:|---|---|
| 0 | $\int\sqrt{-g}$ | cosmological term, vacuum energy counterterm |
| 2 | $\int\sqrt{-g}R$ | Einstein–Hilbert term, Newton constant counterterm |
| 4 | $\int\sqrt{-g}R^2$, $\int\sqrt{-g}R_{\mu\nu}R^{\mu\nu}$, $\int\sqrt{-g}R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}$ | quadratic-curvature counterterms, trace anomaly data, higher-derivative gravity terms |
| 6 and higher | $R^3$, $R\nabla^2R$, $\nabla R\nabla R$, and more | gravitational EFT tower |

The first two terms are familiar from classical gravity. The four-derivative terms are forced by quantum matter in curved spacetime. Higher-derivative terms are expected in gravitational EFT and are suppressed by appropriate powers of the heavy scale when the derivative expansion is valid.

Power counting says the coefficient of a local operator of dimension $\Delta$ in $d$ dimensions has mass dimension $d-\Delta$. In four dimensions,

$$
[R]=2,
\qquad
[R^2]=4,
\qquad
[R^3]=6.
$$

Thus the coefficients of $R^2$ terms are dimensionless in four dimensions, while $R^3$ terms are suppressed by inverse mass squared in an EFT expansion.

## Quadratic-curvature bases in four dimensions

At four derivatives, one can use the basis

$$
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma},
\qquad
R_{\mu\nu}R^{\mu\nu},
\qquad
R^2.
$$

For anomaly and CFT applications, it is often better to use

$$
C^2,
\qquad
E_4,
\qquad
R^2,
$$

where

$$
C^2
= C_{\mu\nu\rho\sigma}C^{\mu\nu\rho\sigma}
=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-2R_{\mu\nu}R^{\mu\nu}
+\frac13R^2,
$$

and

$$
E_4
=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2.
$$

On a compact boundaryless four-manifold,

$$
\int d^4x\sqrt g\,E_4=32\pi^2\chi(M),
$$

where $\chi(M)$ is the Euler characteristic, in the standard normalization. Therefore the integral of $E_4$ is topological in strictly four dimensions. This does not mean the Euler density is irrelevant: it appears in trace anomalies and in dimensional regularization, where pole terms near $d=4$ can leave finite effects.

The total derivative

$$
\Box R=\nabla_\mu\nabla^\mu R
$$

also appears in local formulas. On a closed manifold its integral is a boundary term, but its local contribution to the trace can be shifted by finite $R^2$ counterterms.

## Heat-kernel origin

A standard way to see curvature counterterms is to integrate out a free field. For a real Euclidean scalar with quadratic operator

$$
\Delta=-\nabla^2+\xi R+m^2,
$$

the one-loop effective action is formally

$$
W_{1\text{-loop}}=\frac12\log\det\Delta.
$$

The heat-kernel representation writes

$$
\log\det\Delta
=-\int_0^\infty\frac{ds}{s}\,\operatorname{Tr}e^{-s\Delta}
$$

up to regularization conventions. At small proper time,

$$
\operatorname{Tr}e^{-s\Delta}
\sim
\frac{1}{(4\pi s)^{d/2}}
\sum_{n=0}^\infty s^n\int d^d x\sqrt g\,a_n(x).
$$

The small-$s$ region is the ultraviolet. The coefficients $a_n(x)$ are local curvature invariants. In four dimensions, the logarithmic divergence is controlled by $a_2(x)$.

For a massless scalar, up to total derivatives and convention-dependent signs, the four-dimensional logarithmic divergence contains

$$
W_{\text{div}}
\propto
\frac{1}{(4\pi)^2\epsilon}
\int d^4x\sqrt g\left[
\frac{1}{180}R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-\frac{1}{180}R_{\mu\nu}R^{\mu\nu}
+\frac12\left(\xi-\frac16\right)^2R^2
\right]
$$

plus total derivatives. The exact coefficient convention depends on the definition of $\epsilon$, the operator sign, and Euclidean versus Lorentzian normalization. The structural point is robust: the divergence is local and quadratic in curvature.

For a conformally coupled scalar, $\xi=1/6$ in four dimensions, the $R^2$ term in this expression disappears up to total derivatives, but $C^2$ and $E_4$ anomaly data remain.

## Stress-tensor shifts from finite counterterms

Finite curvature counterterms are not just harmless decorations. They shift the local definition of the renormalized stress tensor.

For example, adding

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

shifts

$$
\langle T_{\mu\nu}\rangle_{\text{ren}}
\longrightarrow
\langle T_{\mu\nu}\rangle_{\text{ren}}
+\alpha\,H_{\mu\nu}^{(R^2)},
$$

where $H_{\mu\nu}^{(R^2)}$ is the local conserved tensor obtained by metric variation of $\int\sqrt g R^2$. One convenient form is

$$
H_{\mu\nu}^{(R^2)}
=2RR_{\mu\nu}
-\frac12g_{\mu\nu}R^2
-2\nabla_\mu\nabla_\nu R
+2g_{\mu\nu}\Box R,
$$

up to the overall sign convention used in defining $T_{\mu\nu}$. Its covariant divergence vanishes by diffeomorphism invariance of the counterterm.

This is the curved-spacetime analog of scheme dependence. The nonlocal finite response and anomaly coefficients such as $a$ and $c$ carry invariant information, while certain local pieces depend on finite counterterm choices.

## Boundary counterterms

If spacetime has a boundary, the local counterterm story is incomplete unless boundary terms are included. The Einstein–Hilbert term requires the Gibbons–Hawking–York boundary term for a well-defined metric variational principle,

$$
S_{\text{GHY}}\sim\int_{\partial M}d^{d-1}x\sqrt{|h|}\,K,
$$

where $h_{ab}$ is the induced boundary metric and $K$ is the trace of the extrinsic curvature.

Quadratic-curvature terms also have boundary companions built from intrinsic boundary curvature, extrinsic curvature, and normal derivatives. In QFT with physical boundaries or defects, additional localized counterterms can appear:

$$
\int_{\partial M}\sqrt{|h|}\,1,
\qquad
\int_{\partial M}\sqrt{|h|}\,K,
\qquad
\int_{\partial M}\sqrt{|h|}\,\mathcal R[h],
\qquad
\int_{\partial M}\sqrt{|h|}\,K^2,
\qquad
\cdots.
$$

This page focuses on bulk counterterms. Boundary anomalies and defect counterterms are their own subject.

## Counterterms versus physical gravitational EFT terms

The same local term can play several roles depending on context.

If the metric is only a fixed source, curvature counterterms are part of the definition of the renormalized generating functional $W[g]$. Their finite pieces encode scheme choices for local stress-tensor terms.

If gravity is dynamical, the coefficients of the same terms become gravitational EFT parameters. The action has the form

$$
S_{\text{gravity EFT}}
=\int d^4x\sqrt{-g}\left[
\frac{M_{\text{Pl}}^2}{2}R
-\Lambda
+\alpha R^2
+\beta R_{\mu\nu}R^{\mu\nu}
+\gamma C^2
+\frac{d_1}{M^2}R^3
+\cdots
\right].
$$

The higher-curvature terms are not signs that the EFT has failed. They are the expected local Wilson coefficients. Predictivity comes from truncating the derivative expansion at a desired accuracy in powers of curvature or momentum over the heavy scale.

:::note[The same term, three meanings]
A term such as $R_{\mu\nu}R^{\mu\nu}$ can be a divergent counterterm, a finite scheme choice in a background-source functional, or a physical Wilson coefficient in gravitational EFT. The formula is the same; the interpretation depends on what is being held fixed and what is being measured.
:::

## Relation to trace anomalies

Curvature counterterms and trace anomalies are two sides of the same local structure. Pole terms in dimensional regularization can leave finite Weyl variations after the regulator is removed. Finite counterterms can shift scheme-dependent anomaly terms.

For example,

$$
\Delta W=\alpha\int d^4x\sqrt g\,R^2
$$

shifts the trace by

$$
\Delta\langle T^\mu{}_{\mu}\rangle=12\alpha\Box R
$$

with the conventions used in [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/). This is why the $\Box R$ anomaly coefficient is not universal.

By contrast, the $aE_4$ and $cC^2$ terms in a four-dimensional CFT are not removable by finite local counterterms. They encode genuine Weyl-anomaly data.

## Common pitfalls

**Thinking flat-space renormalization is enough.** Flat-space amplitudes do not reveal all metric-source counterterms. If you vary the metric, curvature terms are part of the same renormalization problem.

**Calling curvature counterterms quantum gravity.** They are required even for quantum matter on a nondynamical classical metric. Dynamical quantum gravity is a further step.

**Dropping total derivatives too early.** Total derivatives may matter with boundaries, defects, nontrivial topology, or local anomaly formulas. On a closed manifold they may integrate away, but local Ward identities can still see them.

**Confusing topological with irrelevant.** The integral of $E_4$ is topological in four dimensions on closed manifolds, but the Euler density appears in trace anomalies and in dimensional regularization.

**Treating finite local ambiguity as a mistake.** Local finite counterterms are scheme choices. A well-posed physical question either fixes them by convention or asks for quantities insensitive to them.

## Relations to other pages

[Stress-Tensor Renormalization](/renormalization-rg-eft/renormalization-curved-spacetime/stress-tensor-renormalization/) explains why metric variation makes these counterterms observable as local stress-tensor shifts. [Trace Anomaly Preview](/renormalization-rg-eft/renormalization-curved-spacetime/trace-anomaly-preview/) explains which Weyl variations of these local terms survive as anomalous traces. [Heat-Kernel Methods Preview](/renormalization-rg-eft/renormalization-curved-spacetime/heat-kernel-methods-preview/) will develop the efficient machinery for extracting the coefficients. [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/) treats the same terms as EFT Wilson coefficients for dynamical gravity.

## Research status

The local bulk counterterm basis through four derivatives is standard. Heat-kernel methods provide a systematic algorithm for computing one-loop divergences for Laplace-type operators, and more general methods exist for gauge fields, fermions, and higher-spin fields.

Active complications include boundaries, corners, defects, nonminimal operators, gauge fixing and ghosts, Lorentzian real-time states, interacting theories, curved backgrounds with horizons, de Sitter observables, and matching local counterterms to measurable gravitational EFT coefficients. These topics do not alter the local principle; they enrich the list of allowed local terms and the interpretation of finite pieces.

## Exercises

### Exercise 1: Change basis at four derivatives

Using

$$
C^2=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-2R_{\mu\nu}R^{\mu\nu}
+\frac13R^2
$$

and

$$
E_4=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2,
$$

solve for $R_{\mu\nu}R^{\mu\nu}$ and $R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}$ in terms of $C^2$, $E_4$, and $R^2$.

<details><summary><strong>Solution</strong></summary>

Subtract the two equations:

$$
C^2-E_4
=2R_{\mu\nu}R^{\mu\nu}-\frac23R^2.
$$

Therefore

$$
R_{\mu\nu}R^{\mu\nu}
=\frac12(C^2-E_4)+\frac13R^2.
$$

Substitute this into the expression for $C^2$:

$$
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
=C^2+2R_{\mu\nu}R^{\mu\nu}-\frac13R^2.
$$

This gives

$$
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
=2C^2-E_4+\frac13R^2.
$$

Thus the quadratic-curvature basis can be exchanged for the $C^2$, $E_4$, $R^2$ basis.

</details>

### Exercise 2: Dimensions of curvature operators

In four dimensions, show that the coefficients of $R^2$ and $R_{\mu\nu}R^{\mu\nu}$ are dimensionless, while a coefficient multiplying $R^3$ has mass dimension $-2$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless and

$$
[d^4x]=-4,
\qquad
[\sqrt{-g}]=0,
\qquad
[R]=2.
$$

Therefore $R^2$ and $R_{\mu\nu}R^{\mu\nu}$ have dimension $4$, so their coefficients have dimension $4-4=0$. The operator $R^3$ has dimension $6$, so its coefficient has dimension $4-6=-2$. In an EFT, such a coefficient is naturally written as $d/M^2$ with dimensionless $d$.

</details>

### Exercise 3: Conservation of a counterterm stress tensor

Let

$$
H_{\mu\nu}=\frac{2}{\sqrt g}\frac{\delta}{\delta g^{\mu\nu}}
\int d^4x\sqrt g\,R^2.
$$

Explain why $\nabla^\mu H_{\mu\nu}=0$ without doing the full variation.

<details><summary><strong>Solution</strong></summary>

The functional

$$
\int d^4x\sqrt g\,R^2
$$

is invariant under diffeomorphisms. Under an infinitesimal diffeomorphism generated by $\xi^\mu$,

$$
\delta g^{\mu\nu}= -\nabla^\mu\xi^\nu-\nabla^\nu\xi^\mu.
$$

Diffeomorphism invariance gives

$$
0=\delta S
=\frac12\int d^4x\sqrt g\,H_{\mu\nu}\delta g^{\mu\nu}
=-\int d^4x\sqrt g\,H_{\mu\nu}\nabla^\mu\xi^\nu.
$$

Integrating by parts and assuming no boundary contribution yields

$$
0=\int d^4x\sqrt g\,(\nabla^\mu H_{\mu\nu})\xi^\nu.
$$

Since $\xi^\nu$ is arbitrary,

$$
\nabla^\mu H_{\mu\nu}=0.
$$

This argument works for any diffeomorphism-invariant local counterterm.

</details>

## References

- Birrell and Davies, *Quantum Fields in Curved Space*, for standard curvature counterterms, stress tensors, and trace anomalies.
- Parker and Toms, *Quantum Field Theory in Curved Spacetime*, for heat-kernel and effective-action methods.
- Wald, *Quantum Field Theory in Curved Spacetime and Black Hole Thermodynamics*, for local covariance and renormalized stress tensors.
- Christensen, classic work on stress-tensor renormalization and point splitting.
- DeWitt, heat-kernel methods and the local expansion of effective actions.
- Donoghue, papers and reviews on general relativity as an effective field theory.
- Burgess, *Introduction to Effective Field Theory*, for EFT logic applied across particle, condensed matter, and gravitational examples.
- Weinberg, *The Quantum Theory of Fields*, for effective actions, renormalization, and gravity as EFT.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean functional methods and RG logic.

## Version history

- 2026-06-19: First polished draft. Added derivative-order organization, four-dimensional curvature bases, heat-kernel origin, scheme dependence, boundary caveats, and exercises.
