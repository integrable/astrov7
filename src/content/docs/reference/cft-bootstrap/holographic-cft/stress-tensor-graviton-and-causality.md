---
title: "Stress Tensor, Graviton, and Causality"
description: "How the CFT stress tensor encodes the AdS graviton, Newton coupling, Ward identities, stress-tensor exchange, conformal collider bounds, Regge behavior, and causality constraints on bulk gravity."
sidebar:
  label: "Stress Tensor, Graviton, and Causality"
  order: 7
level: Advanced
status: "Polished draft"
source: "Maldacena; Gubser, Klebanov, and Polyakov; Witten; Hofman and Maldacena; Camanho, Edelstein, Maldacena, and Zhiboedov; Caron-Huot; holographic causality literature."
topics:
  - stress tensor
  - graviton
  - holographic CFT
  - causality
  - conformal collider bounds
canonicalTopics:
  - stress-tensor-graviton-and-causality
  - holographic-stress-tensor
  - causality-bounds-in-ads-cft
researchStatus:
  established:
    - "In AdS/CFT, the CFT stress tensor is dual to the bulk graviton, and its normalization controls the effective Newton coupling."
    - "Lorentzian causality, conformal collider bounds, and Regge behavior impose strong constraints on stress-tensor couplings and higher-derivative bulk gravity."
  active:
    - "Current research sharpens causality and positivity constraints on gravitational EFTs, finite-gap corrections, spinning correlators, black-hole scattering, and bootstrap bounds on holographic stress-tensor data."
---

## Summary

The **CFT stress tensor** is the operator that knows about spacetime, energy, momentum, and response to geometry. In holographic CFT, it is dual to the **bulk graviton**:

$$
T_{\mu\nu}
\quad\Longleftrightarrow\quad
h_{MN}\text{ or }g_{MN}.
$$

This is one of the deepest entries in the AdS/CFT dictionary. The stress tensor is not merely another operator. Its conservation, Ward identities, and OPEs encode gravitational dynamics in the bulk.

The normalization of the stress-tensor two-point function,

$$
C_T,
$$

controls the effective Newton coupling:

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N},
$$

up to dimension-dependent normalization conventions.

Stress-tensor exchange controls universal large-spin forces between double-trace states. Stress-tensor three-point functions encode higher-derivative gravitational couplings. Lorentzian causality and conformal collider bounds constrain those couplings.

The slogan is

$$
\text{the stress tensor is the CFT shadow of gravity}.
$$

This page explains the stress-tensor/graviton dictionary and why causality makes gravity in AdS highly constrained.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/), [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), and [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/) first.

You should also know [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), and [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/).

## Core idea

The stress tensor is defined by varying the CFT with respect to a background metric:

$$
T_{\mu\nu}(x)=\frac{2}{\sqrt g}\frac{\delta S_{\rm CFT}}{\delta g^{\mu\nu}(x)}
$$

in Euclidean conventions, up to sign conventions.

In AdS/CFT, the boundary metric is the boundary value of the bulk metric. Therefore a source for $T_{\mu\nu}$ is a boundary condition for the graviton:

$$
g_{\mu\nu}^{\rm boundary}(x)
\quad\leftrightarrow\quad
\text{source for }T_{\mu\nu}(x).
$$

Differentiating the bulk gravitational partition function with respect to the boundary metric gives stress-tensor correlators:

$$
\langle T_{\mu_1\nu_1}(x_1)\cdots T_{\mu_n\nu_n}(x_n)\rangle.
$$

Thus the CFT stress-tensor sector is the boundary description of bulk gravitational perturbation theory.

## Stress tensor basics

In a flat-space CFT, the stress tensor obeys

$$
\partial^\mu T_{\mu\nu}=0,
$$

and conformal invariance implies it can be chosen traceless:

$$
T^\mu_{\ \mu}=0,
$$

up to anomalies in even-dimensional curved backgrounds.

As a conformal primary-like conserved current, the stress tensor has protected dimension and spin

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

Its twist is

$$
\tau_T=\Delta_T-\ell_T=d-2.
$$

This twist is important in analytic bootstrap: stress-tensor exchange contributes universal large-spin corrections of order

$$
J^{-(d-2)}.
$$

Conservation is what makes the dual bulk field massless. A conserved spin-two boundary current maps to a massless spin-two field in AdS: the graviton.

## The two-point function and Newton's constant

Conformal symmetry fixes the stress-tensor two-point function up to one coefficient:

$$
\langle T_{\mu\nu}(x)T_{\rho\sigma}(0)\rangle
=C_T\frac{\mathcal I_{\mu\nu,\rho\sigma}(x)}{x^{2d}},
$$

where $\mathcal I_{\mu\nu,\rho\sigma}(x)$ is a fixed tensor structure.

The coefficient $C_T$ measures the number of degrees of freedom that carry stress-energy. Holographically,

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}.
$$

Thus large $C_T$ means

$$
G_N/R_{\rm AdS}^{d-1}\ll1,
$$

so bulk gravitational loops are suppressed.

This is why holographic CFTs usually have large central charge. Weakly coupled bulk gravity requires many boundary degrees of freedom.

The exact proportionality depends on the normalization of $T_{\mu\nu}$, the AdS radius convention, and the gravitational action. The scaling with $G_N^{-1}$ is the essential physics.

## Ward identities

The stress tensor obeys Ward identities. These express the fact that translations, rotations, scale transformations, and special conformal transformations act on correlation functions.

For example, the OPE of the stress tensor with a scalar primary $\mathcal O$ contains universal terms fixed by symmetry:

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
\text{known singular terms determined by }\Delta_{\mathcal O}
+\cdots .
$$

Equivalently, the three-point function

$$
\langle T_{\mu\nu}\mathcal O\mathcal O\rangle
$$

is fixed up to the scalar dimension and the normalization conventions.

In the bulk, this is the statement that every field couples universally to gravity through the metric. The scalar's energy gravitates because the CFT stress tensor acts universally on operators.

Ward identities are the CFT version of the equivalence principle, with all the necessary caveats about normalization and background geometry.

## Graviton exchange

In a holographic four-point function of scalar operators,

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle,
$$

the stress tensor can appear in the crossed channel. In AdS, this is graviton exchange.

At large spin, stress-tensor exchange shifts double-trace dimensions:

$$
[\mathcal O\mathcal O]_{n,\ell},
\qquad
\Delta_{n,\ell}=2\Delta_{\mathcal O}+2n+\ell+\gamma_{n,\ell}.
$$

The stress-tensor contribution scales as

$$
\gamma_{n,\ell}^{(T)}\sim -\frac{\text{const}}{J^{d-2}}.
$$

The negative sign in standard identical-scalar holographic situations is interpreted as gravitational attraction. The coefficient is controlled by the scalar dimension and $C_T$.

In the bulk picture, the double-trace operator is a two-particle state in AdS. Graviton exchange produces a binding energy. In the CFT picture, crossing and Ward identities force a universal large-spin anomalous dimension.

## Stress-tensor three-point functions

The stress-tensor three-point function

$$
\langle TTT\rangle
$$

contains information about the bulk gravitational action beyond the two-point normalization. In a general CFT, conformal symmetry allows finitely many tensor structures. Their coefficients encode stress-tensor self-interactions.

In a holographic CFT, these structures map to bulk gravitational couplings such as:

- Einstein-Hilbert gravity;
- curvature-squared corrections;
- curvature-cubed corrections;
- parity-odd gravitational terms in appropriate dimensions;
- matter-loop corrections at subleading large $N$.

A simple Einstein gravity dual predicts a special point in the space of allowed stress-tensor three-point data. Higher-derivative gravity moves away from that point.

But not every movement is allowed. Lorentzian causality imposes strong constraints.

## Conformal collider bounds

Conformal collider physics studies energy flux measured at null infinity after creating a state with a local operator. For a stress-tensor insertion, one studies states such as

$$
T_{\mu\nu}|0\rangle
$$

and asks whether the measured energy flux is positive in every direction.

The averaged null energy condition implies positivity constraints on stress-tensor three-point coefficients. These are **conformal collider bounds**.

The logic is:

$$
\text{positive energy flux}
\quad\Rightarrow\quad
\text{bounds on }\langle TTT\rangle.
$$

In holography, these bounds constrain higher-derivative gravitational couplings. If a correction would make a graviton or other excitation experience a time advance, it is not allowed unless new states enter at or below the dangerous scale.

This is a beautiful example of a CFT positivity statement becoming a bulk causality statement.

## Regge causality

The Lorentzian Regge limit probes high-energy scattering. In holographic CFTs, this corresponds to high-energy scattering in AdS, often dominated by graviton exchange.

If a correlator grows too quickly in the Regge limit, the bulk interpretation can violate causality. Higher-derivative terms in the gravitational action can create such dangerous growth.

The schematic lesson is

$$
\text{too-large higher-derivative graviton coupling}
\quad\Rightarrow\quad
\text{causality problem unless new higher-spin states appear}.
$$

This is why the higher-spin gap and gravitational EFT coefficients are linked. A large gap to higher-spin states forces higher-derivative corrections to be small. If corrections are large, the gap cannot be arbitrarily large.

In CFT language, Regge boundedness controls Lorentzian inversion formulas and constrains the analytic behavior of stress-tensor correlators.

## Shockwaves and time delay

A vivid bulk diagnostic uses shockwave scattering. Send a high-energy particle through a gravitational shockwave in AdS. A healthy theory should produce a time delay, not a time advance.

The time delay condition constrains the signs and sizes of higher-derivative interactions. For example, curvature-cubed or Weyl-tensor interactions can modify graviton propagation through a shockwave. If they produce a time advance for some polarization, causality is endangered.

The CFT translation is that stress-tensor correlators must obey Lorentzian positivity and boundedness conditions.

The chain is

$$
\text{CFT stress-tensor correlator}
\quad\leftrightarrow\quad
\text{bulk graviton scattering}
\quad\leftrightarrow\quad
\text{causal time delay}.
$$

This is one of the clearest ways bootstrap constraints become quantum-gravity constraints.

## Higher-spin gap and gravity

The stress tensor has spin two. A theory with many light higher-spin single-trace operators behaves very differently from Einstein gravity.

A large higher-spin gap means

$$
\Delta_{\rm gap}^{\rm HS}\gg1.
$$

This suppresses stringy or higher-spin corrections and allows an Einstein-like bulk EFT over a large energy range.

Causality ties the size of higher-derivative gravitational couplings to this gap. Schematically,

$$
\text{higher-derivative correction}
\lesssim
\text{powers of }(\Delta_{\rm gap}^{\rm HS})^{-1}.
$$

The exact powers depend on the interaction and dimension. The robust message is that weakly curved Einstein gravity is not just large $C_T$. It is large $C_T$ plus a large higher-spin gap plus causality-compatible stress-tensor data.

## Chaos and the graviton

In thermal holographic CFTs, stress-tensor exchange is tied to quantum chaos. Out-of-time-order correlators can grow as

$$
F(t)\sim 1-\epsilon e^{\lambda_L t}+\cdots .
$$

Einstein gravity near a black-hole horizon gives maximal chaos:

$$
\lambda_L=\frac{2\pi}{\beta}.
$$

This growth is controlled by gravitational shockwave scattering. In CFT language, it is a Lorentzian Regge phenomenon involving stress-tensor dynamics.

Stringy corrections and finite higher-spin gap effects can reduce the effective Regge intercept and lower the chaos exponent. Thus chaos provides another diagnostic of whether the bulk is Einstein-like, stringy, or higher-spin-like.

## Numerical bootstrap connections

The stress tensor also plays a central role in numerical bootstrap. Bounds on $C_T$, assumptions about the uniqueness of the stress tensor, and mixed-correlator constraints all help identify CFTs.

In a holographic target, one may look for:

| Numerical datum | Holographic expectation |
|---|---|
| large $C_T$ | weak bulk gravity |
| unique spin-two conserved operator | one graviton |
| large higher-spin gap | Einstein-like low-energy bulk |
| stress-tensor OPE coefficients | bulk gravitational couplings |
| large-spin double-trace tails | graviton and light-field exchange |
| Regge-compatible spectrum | causal bulk behavior |

Numerics is usually strongest at low spin and low dimension. Analytic causality controls high-energy and Lorentzian regimes. The two views are complementary.

## Common pitfalls

**Do not say every stress tensor means a weak graviton.** Every local CFT has a stress tensor; only special large-$C_T$ sparse CFTs have a weakly coupled bulk graviton.

**Do not ignore normalization.** $C_T$, Newton's constant, OPE coefficients, and conformal collider parameters are convention-sensitive.

**Do not treat higher-derivative gravity as arbitrary.** Causality and Regge boundedness strongly constrain it.

**Do not assume large $C_T$ implies a large higher-spin gap.** These are distinct conditions.

**Do not identify all negative anomalous dimensions with gravity.** Other attractive exchanges can also produce negative shifts.

**Do not forget matter fields.** Bulk gravity interacts with all light fields, but stress-tensor exchange is only one part of a full correlator.

**Do not extrapolate shockwave intuition outside its regime.** It is a high-energy semiclassical diagnostic, not a replacement for the full CFT.

## Relations to other pages

This page follows [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/) and prepares [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) and [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/).

It connects to [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/), [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), and [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/).

For later constraints on gravity, see [Bootstrap Constraints on Holography](/cft-bootstrap/holographic-cft/bootstrap-constraints-on-holography/) once available.

## Research status

The stress-tensor/graviton dictionary is established. The relation between $C_T$ and the bulk Newton coupling, the role of stress-tensor exchange in large-spin anomalous dimensions, and the use of conformal collider bounds and Regge causality are standard tools in holographic CFT.

Active research sharpens bounds on gravitational EFT coefficients, finite higher-spin-gap corrections, spinning correlator bootstrap, black-hole chaos, causality in curved backgrounds, and numerical constraints on stress-tensor data in candidate holographic CFTs.

## Exercises

### Exercise 1

What is the bulk dual of the CFT stress tensor?

<details><summary><strong>Solution</strong></summary>

The stress tensor $T_{\mu\nu}$ is dual to the bulk metric $g_{MN}$, or equivalently to metric fluctuations $h_{MN}$ around an AdS background. Since $T_{\mu\nu}$ is conserved and has spin two, the dual field is a massless spin-two graviton.

</details>

### Exercise 2

How does $C_T$ scale with the bulk Newton constant?

<details><summary><strong>Solution</strong></summary>

Up to dimension-dependent constants and normalization conventions,

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}.
$$

Large $C_T$ therefore means small Newton coupling in AdS units and suppressed bulk gravitational loops.

</details>

### Exercise 3

Why does stress-tensor exchange give a large-spin correction of order $J^{-(d-2)}$?

<details><summary><strong>Solution</strong></summary>

The stress tensor has dimension $d$ and spin $2$, so its twist is

$$
\tau_T=d-2.
$$

In large-spin perturbation theory, exchange of an operator with twist $\tau$ produces corrections scaling as $J^{-\tau}$. Therefore stress-tensor exchange gives corrections of order

$$
J^{-(d-2)}.
$$

</details>

### Exercise 4

What do conformal collider bounds constrain?

<details><summary><strong>Solution</strong></summary>

They constrain coefficients in stress-tensor and current three-point functions by requiring positive energy flux in states created by local operators. In holography, these constraints become bounds on higher-derivative gravitational and gauge-field couplings.

</details>

### Exercise 5

Why do large higher-derivative gravitational corrections imply new states cannot be too far away?

<details><summary><strong>Solution</strong></summary>

Large higher-derivative corrections can produce bad Regge growth or time advances in high-energy scattering. To restore causality, new higher-spin or stringy states must enter at or below the scale where the EFT would fail. In CFT language, the higher-spin gap cannot remain arbitrarily large if such corrections are large.

</details>

## References

- J. Maldacena, “The Large N Limit of Superconformal Field Theories and Supergravity,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, “Gauge theory correlators from non-critical string theory,” *Physics Letters B* **428** (1998).
- E. Witten, “Anti de Sitter space and holography,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- D. M. Hofman and J. Maldacena, “Conformal collider physics: Energy and charge correlations,” *Journal of High Energy Physics* **2008**.
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- J. Maldacena, S. H. Shenker, and D. Stanford, “A bound on chaos,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-07-01: First polished draft. Added stress-tensor/graviton dictionary, $C_T$ and Newton-coupling relation, Ward identities, graviton exchange, stress-tensor three-point data, conformal collider bounds, Regge causality, shockwave diagnostics, higher-spin-gap constraints, chaos connections, exercises, and references.
