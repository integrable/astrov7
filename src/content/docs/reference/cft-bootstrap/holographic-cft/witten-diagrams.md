---
title: "Witten Diagrams"
description: "How AdS bulk perturbation theory computes CFT correlation functions using boundary-to-bulk propagators, bulk vertices, exchange diagrams, and contact diagrams."
sidebar:
  label: "Witten Diagrams"
  order: 3
level: Advanced
status: "Polished draft"
source: "Witten 1998; Gubser, Klebanov, and Polyakov 1998; Freedman et al.; D'Hoker and Freedman; Penedones; holographic bootstrap literature."
topics:
  - Witten diagrams
  - AdS/CFT
  - holographic CFT
  - AdS perturbation theory
  - correlation functions
canonicalTopics:
  - witten-diagrams
  - ads-correlators
  - holographic-perturbation-theory
researchStatus:
  established:
    - "Witten diagrams are the standard perturbative AdS method for computing CFT correlators from bulk actions in the semiclassical large-N regime."
  active:
    - "Current work develops loop-level Witten diagrams, Mellin-space methods, spinning exchange, supersymmetric correlators, celestial and flat-space limits, and bootstrap constraints on AdS amplitudes."
---

## Summary

**Witten diagrams** are the AdS/CFT analogue of Feynman diagrams. They compute boundary CFT correlation functions by integrating bulk interaction vertices over anti-de Sitter spacetime.

A CFT correlator such as

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\mathcal O_4(x_4)\rangle
$$

is computed from a bulk process with four external legs ending on the AdS boundary. The external legs are boundary-to-bulk propagators. Internal lines are bulk-to-bulk propagators. Vertices come from the AdS action.

The basic dictionary is:

| Feynman diagram idea | Witten diagram version |
|---|---|
| external particle leg | boundary insertion of a CFT operator |
| internal propagator | bulk-to-bulk propagator in AdS |
| interaction vertex | integral over an AdS point |
| momentum conservation | AdS isometry and boundary conformal covariance |
| scattering amplitude | CFT correlation function |
| loop expansion | $1/N$ or $1/C_T$ expansion |

The slogan is

$$
\text{Witten diagrams are Feynman diagrams with their external legs glued to the boundary}.
$$

They are not ordinary flat-space amplitudes. They compute CFT correlators, and AdS curvature matters. In Mellin space and flat-space limits, however, they become strikingly amplitude-like.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/) and [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/) first.

You should know the source-response dictionary, single-trace and double-trace operators, generalized free fields, conformal cross-ratios, and the idea that connected large-$N$ correlators are dual to weak bulk interactions.

## Core idea

Start with a bulk action for fields $\Phi_i$ in AdS:

$$
S_{\rm bulk}=S_{\rm free}+S_{\rm int}.
$$

The free part determines two-point functions and propagators. The interaction part determines connected higher-point functions. In the semiclassical limit,

$$
Z_{\rm bulk}[\phi_0]\approx \exp\left(-S_{\rm on-shell}[\phi_0]\right),
$$

and CFT correlators are obtained by differentiating with respect to boundary sources:

$$
\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\rangle
=\frac{\delta^n \log Z_{\rm bulk}[\phi_0]}{\delta \phi_0(x_1)\cdots\delta \phi_0(x_n)}\bigg|_{\phi_0=0}.
$$

Perturbatively, this differentiation produces diagrams. The bulk is integrated over; the boundary points are fixed.

Thus the conceptual chain is

$$
\text{bulk action}
\quad\to\quad
\text{AdS propagators and vertices}
\quad\to\quad
\text{Witten diagrams}
\quad\to\quad
\text{CFT correlators}.
$$

This is why Witten diagrams are the working language of perturbative holography.

## Boundary-to-bulk propagators

A boundary-to-bulk propagator carries a boundary source into the AdS interior. For a scalar field of dimension $\Delta$ in Poincare coordinates,

$$
ds^2=\frac{R^2}{z^2}\left(dz^2+dx^\mu dx_\mu\right),
\qquad z>0,
$$

the Euclidean boundary-to-bulk propagator has the schematic form

$$
K_\Delta(z,x;x_i)
=C_\Delta\left(\frac{z}{z^2+(x-x_i)^2}\right)^\Delta.
$$

Here $x_i$ is the boundary insertion point. The normalization $C_\Delta$ depends on conventions.

In a Witten diagram, each external scalar operator insertion contributes one factor

$$
K_{\Delta_i}(z,x;x_i)
$$

attached to a bulk vertex. This is the AdS version of an external leg.

The boundary-to-bulk propagator solves the free bulk equation of motion and has the correct near-boundary behavior to source the CFT operator.

## Bulk-to-bulk propagators

Internal lines are bulk-to-bulk propagators. A scalar bulk-to-bulk propagator $G_\Delta(X,Y)$ solves

$$
\left(\nabla_X^2-m^2\right)G_\Delta(X,Y)
=\frac{1}{\sqrt g}\delta^{d+1}(X-Y),
$$

with boundary conditions appropriate to the dual operator dimension $\Delta$.

Here $X$ and $Y$ are bulk points. The mass is related to the CFT dimension by

$$
m^2R^2=\Delta(\Delta-d).
$$

A bulk-to-bulk propagator represents the exchange of a single bulk field. In the CFT, this corresponds to the exchange of a single-trace primary and its conformal descendants.

For spinful fields, the propagator carries tensor or spinor indices and gauge redundancies. The conceptual role is the same, but the bookkeeping gets louder.

## Contact diagrams

The simplest connected four-point Witten diagram comes from a quartic contact interaction:

$$
S_{\rm int}\supset g_4\int_{\rm AdS} d^{d+1}X\sqrt g\,\Phi_1\Phi_2\Phi_3\Phi_4.
$$

The corresponding contact diagram is

$$
\mathcal A_{\rm contact}(x_i)
=g_4\int_{\rm AdS} d^{d+1}X\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)K_{\Delta_3}(X;x_3)K_{\Delta_4}(X;x_4).
$$

This integral gives a conformally covariant four-point function. After factoring out the fixed position dependence, it determines a function of cross-ratios.

Contact diagrams are important because they encode local AdS interactions. In Mellin space, a non-derivative contact diagram gives a constant Mellin amplitude, while derivative contact interactions give polynomials.

Thus:

$$
\text{local AdS contact interaction}
\quad\leftrightarrow\quad
\text{polynomial Mellin amplitude}.
$$

## Exchange diagrams

An exchange diagram has two bulk vertices connected by a bulk-to-bulk propagator. For a scalar exchange in a four-point function, the schematic expression is

$$
\mathcal A_{\rm exchange}(x_i)
=g_{12X}g_{34X}
\int dX\sqrt g\int dY\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)
G_{\Delta_X}(X,Y)
K_{\Delta_3}(Y;x_3)K_{\Delta_4}(Y;x_4).
$$

The exchanged bulk field is dual to a CFT primary $\mathcal X$. The cubic couplings are dual to OPE coefficients:

$$
g_{12X}\quad\leftrightarrow\quad \lambda_{12X},
\qquad
 g_{34X}\quad\leftrightarrow\quad \lambda_{34X}.
$$

In the CFT conformal block expansion, the exchange diagram contains the conformal block of $\mathcal X$ in one channel plus additional double-trace contributions. This is one reason exchange Witten diagrams are closely related to Polyakov blocks.

## Three-point functions

A cubic bulk interaction

$$
S_{\rm int}\supset g_{123}\int_{\rm AdS} d^{d+1}X\sqrt g\,\Phi_1\Phi_2\Phi_3
$$

computes a CFT three-point function:

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=g_{123}\int_{\rm AdS} d^{d+1}X\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)K_{\Delta_3}(X;x_3).
$$

Conformal symmetry fixes the position dependence:

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=\frac{\lambda_{123}}{x_{12}^{\Delta_1+\Delta_2-\Delta_3}x_{23}^{\Delta_2+\Delta_3-\Delta_1}x_{31}^{\Delta_3+\Delta_1-\Delta_2}}.
$$

The Witten diagram determines the coefficient $\lambda_{123}$ in terms of the bulk coupling and normalization conventions.

This is the most direct demonstration that CFT OPE coefficients are bulk interaction strengths.

## Four-point functions and cross-ratios

A scalar four-point function has the form

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=\text{fixed prefactor}\times \mathcal G(u,v),
$$

where

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

Witten diagrams compute the dynamical function $\mathcal G(u,v)$. Contact diagrams contribute regular crossing-compatible functions. Exchange diagrams contribute channel singularities associated with single-trace exchange.

The CFT expansion of a holographic four-point function contains:

1. single-trace exchange data, from exchanged bulk fields;
2. double-trace data, from two-particle states;
3. anomalous dimensions, from interactions;
4. OPE coefficient corrections, from the same interactions;
5. possible contact-term ambiguities.

This is why four-point Witten diagrams are central in holographic bootstrap.

## Conformal blocks and exchange

A single-channel conformal block isolates one primary and its descendants. An exchange Witten diagram is not identical to one conformal block. It contains the desired single-trace block plus extra double-trace contributions needed by the full AdS integral.

Schematically,

$$
\mathcal W_{\Delta,\ell}^{(s)}
=G_{\Delta,\ell}^{(s)}
+\sum_{n,\ell'} c_{n,\ell'}G_{\Delta_{n,\ell'},\ell'}^{(s)}.
$$

The extra terms are double-trace contributions. They are not mistakes. They reflect the fact that a bulk exchange diagram is a full correlator contribution, not a projection onto one conformal family.

Geodesic Witten diagrams were introduced to isolate conformal blocks more directly by restricting integrations to geodesics. Ordinary Witten diagrams compute AdS interaction contributions; geodesic Witten diagrams are more block-like.

The distinction saves many headaches.

## Mellin-space form

Mellin space makes Witten diagrams look particularly simple.

A contact diagram gives a polynomial Mellin amplitude:

$$
M_{\rm contact}(s,t)=\text{polynomial in }s,t.
$$

An exchange diagram gives a meromorphic Mellin amplitude:

$$
M_{\rm exchange}(s,t)=\sum_{m=0}^{\infty}\frac{R_m(t)}{s-(\Delta-\ell+2m)}+\text{polynomial ambiguity}.
$$

The poles correspond to the exchanged primary and descendants. The polynomial ambiguity corresponds to contact terms.

This is why Mellin amplitudes are so useful in holographic CFT. They turn Witten diagrams into amplitude-like objects:

$$
\text{contact}=\text{polynomial},
\qquad
\text{exchange}=\text{poles plus polynomial ambiguity}.
$$

The Gamma factors in the Mellin representation still matter. Mellin amplitudes are not literally flat-space amplitudes until a controlled flat-space limit is taken.

## Tree diagrams and large N

Tree-level Witten diagrams compute the leading connected correlators in a large-$N$ expansion:

$$
\mathcal G(u,v)=\mathcal G_{\rm GFF}(u,v)+N^{-p}\mathcal G^{(1)}(u,v)+\cdots .
$$

The disconnected generalized-free part gives the leading double-trace spectrum. Tree-level connected Witten diagrams shift double-trace dimensions and OPE coefficients:

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+N^{-p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

In bulk language, $\gamma_{n,\ell}^{(1)}$ is the interaction energy of a two-particle state. In boundary language, it is required by crossing at first subleading order.

Thus Witten diagrams are the computational bridge between AdS interactions and CFT anomalous dimensions.

## Loop diagrams

Loop Witten diagrams appear at higher orders in the large-$N$ expansion. They are harder than tree diagrams for the same reasons loops are hard in flat-space QFT, plus some AdS-specific spice.

At loop level one must handle:

- bulk integration over internal vertices;
- sums over AdS normal modes;
- UV divergences and counterterms;
- double-trace and multi-trace cuts;
- contact-term ambiguities;
- possible mixing among degenerate multi-particle states.

Lorentzian inversion and double discontinuities are powerful because loop-level dDisc data are often determined by lower-order anomalous dimensions and OPE coefficients. This resembles unitarity methods in scattering amplitudes.

The loop slogan is

$$
\text{bulk loops}\quad\leftrightarrow\quad\text{higher-order }1/N\text{ corrections to CFT data}.
$$

## Normalization caveats

Witten diagrams are normalization-sensitive. To compare formulas across papers, one must track:

| Choice | Affects |
|---|---|
| normalization of CFT two-point functions | OPE coefficients |
| normalization of bulk kinetic terms | propagators and couplings |
| boundary-to-bulk propagator constants | correlator coefficients |
| AdS radius convention | mass-dimension relation and coupling dimensions |
| Euclidean versus Lorentzian signature | factors of $i$ and contour choices |
| field redefinitions | contact terms and derivative interactions |

The physics is invariant, but the symbols are not. A Witten diagram coefficient without conventions is a decorative number.

## Common pitfalls

**Do not confuse Witten diagrams with flat-space Feynman diagrams.** Witten diagrams compute CFT correlators, not ordinary S-matrix elements.

**Do not forget to integrate over AdS vertices.** Bulk interaction points are integrated; boundary insertion points are fixed.

**Do not identify an exchange Witten diagram with a single conformal block.** It contains the exchanged single-trace block plus double-trace contributions.

**Do not ignore contact ambiguities.** Exchange diagrams can be shifted by local contact terms.

**Do not compare OPE coefficients without normalizing two-point functions.** Coupling-to-OPE maps depend on conventions.

**Do not assume tree level is exact.** Tree diagrams are leading connected large-$N$ data; loops give further corrections.

**Do not forget gauge redundancies for spin-one and spin-two fields.** Currents and stress tensors require Ward identities and gauge fixing.

## Relations to other pages

This page follows [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/) and prepares [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/) and [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/).

It connects back to [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/), and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/).

For stress tensor and graviton exchange, see [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/) once available.

## Research status

Tree-level Witten diagrams are established technology for computing holographic CFT correlators. Their relation to conformal blocks, Mellin amplitudes, and large-$N$ double-trace data is standard.

Active research focuses on loop Witten diagrams, spinning exchange, supersymmetric correlators, Mellin-space recursion and dispersion methods, AdS unitarity cuts, flat-space limits, and using bootstrap constraints to classify allowed AdS interactions.

## Exercises

### Exercise 1

What is the Witten-diagram expression for a scalar quartic contact interaction?

<details><summary><strong>Solution</strong></summary>

For

$$
S_{\rm int}\supset g_4\int d^{d+1}X\sqrt g\,\Phi_1\Phi_2\Phi_3\Phi_4,
$$

the four-point contact contribution is

$$
\mathcal A_{\rm contact}(x_i)
=g_4\int_{\rm AdS} d^{d+1}X\sqrt g\,
\prod_{i=1}^4 K_{\Delta_i}(X;x_i).
$$

</details>

### Exercise 2

Why is an exchange Witten diagram not the same as a single conformal block?

<details><summary><strong>Solution</strong></summary>

A conformal block isolates one primary and its descendants in a chosen OPE channel. An exchange Witten diagram is a full AdS correlator contribution. Its conformal block decomposition contains the exchanged single-trace block plus additional double-trace blocks. Those double-trace terms are required by the AdS integral and crossing-compatible structure.

</details>

### Exercise 3

What does a non-derivative AdS contact interaction look like in Mellin space?

<details><summary><strong>Solution</strong></summary>

A non-derivative contact interaction gives a constant Mellin amplitude, up to normalization and convention-dependent Gamma factors in the full Mellin representation. Derivative contact interactions give polynomials in the Mellin variables.

</details>

### Exercise 4

How does a bulk cubic coupling appear in the CFT?

<details><summary><strong>Solution</strong></summary>

A bulk cubic coupling

$$
g_{123}\Phi_1\Phi_2\Phi_3
$$

contributes to the CFT three-point function coefficient

$$
\lambda_{123}.
$$

The exact proportionality depends on the normalization of bulk fields, propagators, and CFT two-point functions.

</details>

### Exercise 5

What CFT data are shifted by a tree-level connected four-point Witten diagram?

<details><summary><strong>Solution</strong></summary>

At leading connected order in large $N$, a tree-level Witten diagram shifts double-trace dimensions and OPE coefficients. For example,

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+N^{-p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

The anomalous dimension is the AdS interaction energy of the corresponding two-particle state.

</details>

## References

- E. Witten, “Anti de Sitter space and holography,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, “Gauge theory correlators from non-critical string theory,” *Physics Letters B* **428** (1998).
- D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, “Correlation functions in the CFT(d)/AdS(d+1) correspondence,” *Nuclear Physics B* **546** (1999).
- E. D'Hoker and D. Z. Freedman, “Supersymmetric gauge theories and the AdS/CFT correspondence,” 2002.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.

## Version history

- 2026-07-01: First polished draft. Added boundary-to-bulk and bulk-to-bulk propagators, contact and exchange diagrams, three- and four-point functions, conformal-block and Mellin interpretations, tree and loop large-$N$ roles, caveats, exercises, and references.
