---
title: "Generalized Unitarity"
description: "How loop amplitudes and loop integrands are reconstructed from products of on-shell tree amplitudes across multiple cuts."
sidebar:
  label: "Generalized Unitarity"
  order: 6
level: Advanced
status: "Polished draft"
source: "Bern, Dixon, Dunbar, and Kosower; Britto, Cachazo, Feng; Elvang and Huang; Dixon; Schwartz ch. 27."
topics:
  - generalized unitarity
  - loop amplitudes
  - unitarity cuts
  - leading singularities
  - integrand reconstruction
canonicalTopics:
  - generalized-unitarity
  - loop-integrand-cuts
  - leading-singularity-methods
  - cut-constructibility
  - amplitude-reconstruction
researchStatus:
  established:
    - "Generalized unitarity is a standard method for reconstructing many loop amplitudes and loop integrands from products of lower-loop or tree-level on-shell amplitudes."
  active:
    - "Modern implementations use integrand bases, finite-field reconstruction, color-kinematics representations, multi-loop cuts, and analytic or numerical unitarity; the optimal form of an integrand is problem-dependent."
---

## Summary

Generalized unitarity is the loop-level extension of the idea that singularities of an amplitude know about physical intermediate states. Instead of computing every loop diagram from off-shell Feynman rules and simplifying afterward, one asks what the loop integrand must reduce to when selected internal propagators are placed on shell.

For a cut $C$, the basic statement is

$$
\left.\mathcal I_n^{(L)}\right|_C
=
\sum_{\text{internal states}}
\prod_{v\in C} A_v^{\rm tree},
$$

with the obvious generalization when one side of the cut contains lower-loop amplitudes. The right-hand side is made entirely of on-shell objects. The left-hand side is the candidate loop integrand restricted to the same on-shell conditions.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Generalized unitarity matches cuts of loop integrands to products of tree amplitudes](/figures/perturbative-qft/generalized-unitarity.svg)

<figcaption>

Generalized unitarity determines loop integrands by matching their cuts. When propagators are put on shell, the loop integrand factorizes into a sum over products of tree amplitudes, with sums over the internal particle states crossing the cut.

</figcaption>
</figure>

The method is especially powerful because tree amplitudes are often much simpler than loop diagrams. In gauge theory, generalized unitarity can expose cancellations that are almost invisible diagram by diagram. In modern amplitude computations it is one of the main bridges between tree-level on-shell methods, loop-integral reduction, and precision scattering calculations.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/), [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/), [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/), and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/).

## Core idea

A loop amplitude is constrained by what happens when internal particles become physical. Ordinary unitarity relates the imaginary part of an amplitude to a sum over intermediate states. Generalized unitarity sharpens this into a reconstruction method: impose several on-shell conditions simultaneously and demand that the loop integrand have the correct factorization on every such cut.

The slogan is

```txt
loop information = compatible collection of on-shell cuts.
```

This is stronger than checking one two-particle discontinuity. A two-particle cut sees only one channel. A triple cut, quadruple cut, or maximal cut sees more of the integrand. At one loop in four dimensions, a quadruple cut can freeze the loop momentum to isolated complex solutions. At higher loops, maximal and near-maximal cuts organize the numerator data of many-loop integrands.

The method has two complementary forms.

| Form | What is reconstructed | Typical use |
|---|---|---|
| Integral-level unitarity | coefficients of a chosen integral basis | one-loop amplitudes, cut-constructible parts |
| Integrand-level unitarity | numerator functions before integration | multi-loop amplitudes, local integrands, finite-field workflows |

Both forms use the same physical principle. The difference is whether one matches after reducing to master integrals or before integration.

## Setup and conventions

Use the scattering conventions fixed in this volume. External momenta are outgoing unless stated otherwise. A loop propagator denominator will be written schematically as

$$
D_a(\ell)=q_a(\ell)^2-m_a^2+i\epsilon,
$$

where $q_a(\ell)$ is a linear combination of loop and external momenta. A cut sets selected denominators on shell. At the level of discontinuities, this is represented by replacing propagators with on-shell delta functions. At the level of complexified integrands, one often writes the cut conditions simply as

$$
D_{a_1}=D_{a_2}=\cdots=D_{a_r}=0.
$$

The two languages are closely related but not identical. Delta-function cuts compute physical discontinuities in specified channels. Complex generalized cuts are algebraic probes of the integrand and may use complex loop momenta.

For clarity, this page mostly discusses color-ordered massless amplitudes. The logic applies more broadly, but massive particles, nonplanar color structures, dimensional regularization, and infrared subtraction introduce additional bookkeeping.

## From ordinary cuts to generalized cuts

Start with a one-loop amplitude whose integrand is a rational function of a loop momentum $\ell$:

$$
A_n^{1\text{-loop}}
=
\int \frac{d^D\ell}{(2\pi)^D}\,\mathcal I_n(\ell).
$$

An ordinary two-particle cut in a channel with momentum $P$ places two internal momenta on shell:

$$
\ell^2=0,
\qquad
(\ell-P)^2=0
$$

for massless internal particles. On this cut, the amplitude factorizes into a product of two tree amplitudes, summed over internal helicities or particle species:

$$
\left.\mathcal I_n(\ell)\right|_{\ell^2=(\ell-P)^2=0}
=
\sum_{h_1,h_2}
A_L^{\rm tree}(\ldots,\ell^{h_1},(P-\ell)^{h_2})
A_R^{\rm tree}((-\ell)^{-h_1},(\ell-P)^{-h_2},\ldots).
$$

This is already useful: any proposed integrand must pass this test. Generalized unitarity then imposes more on-shell conditions. A triple cut sets three propagators on shell. A quadruple cut sets four. A maximal cut sets as many propagators as possible.

Each extra cut condition removes more ambiguity. In four-dimensional one-loop calculations, a quadruple cut of a box topology typically leaves isolated loop-momentum solutions. That is why box coefficients can often be read directly from products of four tree amplitudes.

## One-loop integral basis viewpoint

At one loop, many massless amplitudes can be expressed as

$$
A_n^{1\text{-loop}}
=
\sum_i c_i I_i
+R,
$$

where $I_i$ are scalar box, triangle, and bubble integrals, and $R$ denotes possible rational terms not visible to strictly four-dimensional cuts. In supersymmetric theories, the basis can be much smaller. In general gauge theories, rational terms require care.

The coefficient $c_i$ is determined by matching cuts. For example, if a particular cut isolates one basis integral, then the product of trees on that cut determines the corresponding coefficient. If several basis integrals share the same cut, one must use additional cuts, subtraction terms, or a systematic reduction algorithm.

A simple one-loop workflow is:

```txt
choose integral basis
  → compute products of trees on cuts
  → match cuts to basis integrals
  → solve for coefficients
  → add rational or D-dimensional information when needed.
```

This is not merely a faster way to do Feynman diagrams. It reorganizes the calculation around physical factorization channels and exposes cancellations before integration.

## Quadruple cuts and leading singularities

For a four-dimensional one-loop box with four propagators, the quadruple cut imposes

$$
D_1(\ell)=D_2(\ell)=D_3(\ell)=D_4(\ell)=0.
$$

These are four equations for the four components of $\ell$. For generic external kinematics, the solutions are isolated and complex. The cut coefficient is obtained by evaluating the product of four tree amplitudes on those solutions, with the appropriate Jacobian and state sum.

Schematically,

$$
c_{\rm box}
\sim
\sum_{\ell_*}
\sum_{\rm states}
A_1^{\rm tree}(\ell_*)A_2^{\rm tree}(\ell_*)A_3^{\rm tree}(\ell_*)A_4^{\rm tree}(\ell_*).
$$

The residue on a maximal cut is called a leading singularity. Leading singularities are useful far beyond one-loop boxes. In planar $\mathcal N=4$ super-Yang–Mills theory, they connect generalized unitarity to on-shell diagrams, Grassmannian residues, and positive geometry. In less supersymmetric theories, they still provide powerful probes of integrand structure, but they may not determine every term by themselves.

## Integrand-level reconstruction

At higher loop order, one often writes an ansatz for the integrand:

$$
\mathcal I_n^{(L)}
=
\sum_{\Gamma}
\frac{N_\Gamma(\ell_1,\ldots,\ell_L)}{\prod_{a\in\Gamma}D_a}.
$$

The sum runs over graph topologies $\Gamma$, and $N_\Gamma$ are numerator functions. The numerator may contain dot products of loop momenta with external momenta, irreducible scalar products, spinor products, color factors, and sometimes contact terms corresponding to collapsed propagators.

Generalized unitarity determines the unknown coefficients in the numerators by matching many cuts:

$$
\left.\sum_{\Gamma}
\frac{N_\Gamma}{\prod_{a\in\Gamma}D_a}\right|_C
=
\sum_{\text{states}}\prod_{v\in C} A_v^{\rm tree}.
$$

A practical computation repeats this for enough cuts to fix the ansatz. Modern implementations often evaluate the cuts over finite fields and reconstruct rational functions of the kinematic variables. The physics is old-school unitarity; the engineering is very twenty-first century.

## Four-dimensional versus D-dimensional cuts

A common beginner trap is to assume that four-dimensional cuts always determine the full dimensionally regulated amplitude. They do not.

In dimensional regularization, the loop momentum lives in

$$
D=4-2\epsilon
$$

dimensions. Terms proportional to the extra-dimensional components of loop momentum can integrate to finite rational contributions. A four-dimensional cut can miss them because it sets those components to zero from the start.

There are several remedies:

| Issue | Remedy |
|---|---|
| Rational terms missed by four-dimensional cuts | use $D$-dimensional unitarity or supplement with known rational reconstruction |
| Scheme dependence in helicity states | state the regularization scheme clearly |
| Massive internal states or EFT operators | include the correct on-shell tree amplitudes and numerator ansatz |
| Infrared divergent amplitudes | separate integrand reconstruction from IR subtraction and observable definition |

The safest sentence is: four-dimensional generalized unitarity is extraordinarily powerful, but the regulated amplitude knows about the regulator.

## Example: scalar bubble cut

Consider a scalar bubble integral with external momentum $P$,

$$
I_2(P^2)
=
\int\frac{d^D\ell}{(2\pi)^D}
\frac{i}{\ell^2+i\epsilon}
\frac{i}{(\ell-P)^2+i\epsilon}.
$$

The two-particle cut sets

$$
\ell^2=0,
\qquad
(\ell-P)^2=0.
$$

In a theory where the two sides of the cut are tree amplitudes $A_L^{\rm tree}$ and $A_R^{\rm tree}$, the cut of the full amplitude contains

$$
\sum_{h_1,h_2}
A_L^{\rm tree}(\ldots,\ell^{h_1},(P-\ell)^{h_2})
A_R^{\rm tree}((-\ell)^{-h_1},(\ell-P)^{-h_2},\ldots).
$$

For a scalar theory the state sum may be trivial. For gauge theory it is essential. If the product of trees is a constant on the cut, then the cut determines the coefficient multiplying the scalar bubble. If the product contains loop-momentum dependence, that dependence must be decomposed into the chosen integral basis or handled at the integrand level.

## Why this works

The method rests on three facts.

First, unitarity says that discontinuities of amplitudes are sums over physical intermediate states. This is the same principle behind the optical theorem and Cutkosky rules.

Second, locality says that singularities occur when propagating internal momenta go on shell. The residue at such a singularity factorizes into lower-point amplitudes.

Third, loop integrands are rational functions before integration. If a rational function has enough matching residues and enough controlled behavior at infinity, it can be reconstructed.

This last sentence hides real work. One must know the allowed denominator structure, choose a sufficiently general numerator ansatz, account for contact terms, and handle possible terms invisible to the chosen cuts. But the conceptual architecture is simple: build the loop from its on-shell shadows.

## Common pitfalls

**Confusing generalized cuts with physical cuts.** A physical two-particle cut computes a discontinuity across a branch cut in a physical channel. A complex maximal cut is an algebraic residue of the integrand. Both are called cuts, but they are not the same operation.

**Assuming all rational terms are visible in four dimensions.** In non-supersymmetric theories, four-dimensional cuts can miss regulator-dependent information that becomes finite after integration.

**Forgetting internal state sums.** A cut line is not just a scalar propagator unless the theory is scalar. Physical on-shell cuts require sums over the physical particles and helicities crossing the cut. If one instead cuts gauge-fixed Feynman diagrams, ghost and unphysical-mode bookkeeping may enter before gauge-invariant cancellations occur.

**Overtrusting a small set of cuts.** Matching a few cuts proves only that the candidate integrand agrees on those cuts. One must use enough cuts, symmetry constraints, power counting, and contact terms to fix the full ansatz.

**Ignoring infrared subtraction.** Generalized unitarity reconstructs amplitudes or integrands. Infrared-safe observables require further real-emission contributions, subtraction methods, or inclusive definitions.

## Relations to other pages

- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) explains the discontinuity-level replacement of propagators by on-shell delta functions.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) develops cuts as probes of loop integrals.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) gives the analytic language behind cut discontinuities.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) supplies many of the tree amplitudes used on the right-hand side of generalized cuts.
- [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) and [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explain what happens after the integrand has been organized into an integral family.
- [On-Shell Diagrams Preview](/perturbative-qft/modern-on-shell-amplitudes/on-shell-diagrams-preview/) connects leading singularities to graphical on-shell building blocks in special theories.

## Research status

**Established:** Generalized unitarity is a standard part of modern perturbative QFT. It is routinely used in analytic and numerical amplitude computations, especially for gauge theories and gravity.

**Active:** Current research develops better integrand bases, finite-field reconstruction, multi-loop nonplanar methods, color-kinematics-satisfying representations, elliptic and more general function spaces after integration, and efficient interfaces with subtraction and phase-space integration.

**Convention-dependent:** The precise form of an integrand depends on loop-momentum routing, integral basis, dimensional-regularization scheme, color decomposition, and whether contact terms are assigned to higher- or lower-propagator topologies.

## Exercises

### Exercise 1: Two-particle cut of a scalar bubble

For the massless scalar bubble

$$
I_2(P^2)=\int\frac{d^D\ell}{(2\pi)^D}
\frac{i}{\ell^2+i\epsilon}\frac{i}{(\ell-P)^2+i\epsilon},
$$

write the two on-shell conditions of the $P$-channel cut and explain why the cut has the kinematics of two massless intermediate particles.

<details>
<summary><strong>Solution</strong></summary>

The two cut propagators are the lines carrying momenta $\ell$ and $\ell-P$. The cut conditions are

$$
\ell^2=0,
\qquad
(\ell-P)^2=0.
$$

These are exactly the mass-shell equations for two massless particles with momenta $\ell$ and $P-\ell$. Momentum conservation across the cut says that the total momentum carried by the two intermediate particles is $P$.

In a physical cut, the propagators are replaced by on-shell phase-space delta functions, so the cut integral is an integral over two-particle phase space. In a complex generalized cut, the same equations are imposed algebraically.

</details>

### Exercise 2: Why a quadruple cut freezes a one-loop box

In four dimensions, a one-loop box has four propagator denominators $D_1,D_2,D_3,D_4$. Explain why imposing $D_i=0$ for all four propagators typically leaves isolated solutions for $\ell$.

<details>
<summary><strong>Solution</strong></summary>

The loop momentum $\ell^\mu$ has four components in four dimensions. The quadruple cut imposes four equations,

$$
D_1(\ell)=D_2(\ell)=D_3(\ell)=D_4(\ell)=0.
$$

For generic external kinematics, four independent equations for four unknowns leave a discrete set of solutions rather than a continuous integration variable. In practice these solutions are usually complex. Evaluating the product of four tree amplitudes on those solutions determines the corresponding leading singularity and, in favorable one-loop cases, the scalar box coefficient.

The word “typically” matters. Degenerate kinematics, masses, Gram determinant zeros, or special numerator structures can require separate treatment.

</details>

### Exercise 3: Four-dimensional cuts and rational terms

Why can a strictly four-dimensional cut miss part of a dimensionally regulated one-loop amplitude in a non-supersymmetric theory?

<details>
<summary><strong>Solution</strong></summary>

In dimensional regularization the loop momentum has $D=4-2\epsilon$ components. One may decompose it as

$$
\ell_D^\mu=\ell_4^\mu+\ell_{-2\epsilon}^\mu.
$$

A strictly four-dimensional cut sets $\ell_{-2\epsilon}=0$. Terms in the numerator proportional to powers of $\ell_{-2\epsilon}^2$ therefore vanish on such cuts. After integration, however, these terms can multiply $1/\epsilon$ ultraviolet or infrared poles and leave finite rational contributions. Thus four-dimensional cut constructibility is not automatic in general theories.

A $D$-dimensional unitarity calculation, or an equivalent rational-term reconstruction, keeps this information.

</details>

### Exercise 4: Internal state sums

In a gluon loop cut in Yang–Mills theory, why is it not enough to multiply two color-ordered tree amplitudes without summing over internal helicities?

<details>
<summary><strong>Solution</strong></summary>

The cut line represents a complete set of physical intermediate states. For a massless gluon in four dimensions, the physical states are the two helicities $h=\pm$. A cut therefore contains

$$
\sum_{h_1,h_2}
A_L(\ldots,\ell_1^{h_1},\ell_2^{h_2})
A_R((-\ell_1)^{-h_1},(-\ell_2)^{-h_2},\ldots).
$$

Without the helicity sum, one would compute only one intermediate polarization configuration, not the unitarity cut of the amplitude. In supersymmetric theories, the helicity sum is often packaged into a Grassmann integral over an internal on-shell supermultiplet.

</details>

## References

- Z. Bern, L. Dixon, D. C. Dunbar, and D. A. Kosower, “One-Loop $n$-Point Gauge Theory Amplitudes, Unitarity and Collinear Limits,” for classic unitarity-based one-loop amplitude technology.
- Z. Bern, L. Dixon, and D. A. Kosower, “Progress in One-Loop QCD Computations,” for a pedagogical account of unitarity methods in gauge theory.
- R. Britto, F. Cachazo, and B. Feng, “Generalized Unitarity and One-Loop Amplitudes in $\mathcal N=4$ Super-Yang–Mills,” for quadruple-cut methods.
- R. Britto, F. Cachazo, B. Feng, and E. Witten, “Direct Proof of Tree-Level Recursion Relation in Yang–Mills Theory,” for the tree-level recursion technology that feeds modern cuts.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a coherent on-shell treatment of cuts, recursion, leading singularities, and loop amplitudes.
- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” for a classic review of helicity methods and unitarity-based computations.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for spinor-helicity and on-shell amplitude methods in a graduate-QFT context.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, emphasizing integrand reconstruction, one-loop cuts, leading singularities, and regulator caveats.
