---
title: "Minimal Subtraction"
description: "How MS and modified MS subtract dimensional-regularization poles, define running parameters, and make renormalization group equations efficient."
sidebar:
  label: "Minimal Subtraction"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§27–29; Schwartz chs. 18–23 and appendix B; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Coleman, renormalization lectures; Zinn-Justin, renormalization chapters."
topics:
  - minimal subtraction
  - modified minimal subtraction
  - dimensional regularization
  - beta functions
  - renormalization scale
  - mass-independent schemes
canonicalTopics:
  - minimal-subtraction
  - msbar-scheme
  - dimensional-regularization
  - beta-functions-from-counterterms
researchStatus:
  established:
    - "MS and modified MS are standard dimensional-regularization schemes that define renormalized parameters by subtracting pole parts rather than by imposing physical on-shell conditions."
  active:
    - "High-order computations, EFT matching, evanescent operators, gamma-five prescriptions, threshold conversions, and precision scheme transformations remain technically active."
---

## Summary

**Minimal subtraction**, or **MS**, is the renormalization scheme in dimensional regularization that subtracts only the poles in the regulator $\epsilon$. The modified scheme $\overline{\mathrm{MS}}$ subtracts the common combination

$$
\frac{1}{\bar\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log(4\pi),
$$

where $d=4-2\epsilon$. In either case, the defining rule is deliberately austere:

$$
\text{subtract the pole part, and do not use physical kinematic conditions to choose finite terms.}
$$

This makes MS and $\overline{\mathrm{MS}}$ less physically transparent than an on-shell scheme, but much more efficient for many modern calculations. They are local, algebraic, compatible with dimensional regularization, well adapted to gauge theories, and especially useful for deriving beta functions, anomalous dimensions, EFT running, and operator mixing.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Dimensional regularization produces pole parts; minimal subtraction removes local poles and leaves finite logarithms whose mu dependence is governed by beta functions](/figures/renormalization-rg-eft/minimal-subtraction-pole-map.svg)

<figcaption>

Minimal subtraction extracts local pole parts from dimensionally regulated loop integrals. The pole pieces define counterterms; the remaining finite logarithms carry $\mu$ dependence; requiring bare quantities to be independent of $\mu$ gives beta functions and anomalous dimensions.

</figcaption>
</figure>

The practical slogan is:

$$
\text{MS turns ultraviolet renormalization into pole bookkeeping.}
$$

:::note[MS is a scheme, not a regulator]
Dimensional regularization is the regulator. MS and $\overline{\mathrm{MS}}$ are subtraction schemes used after dimensional regularization has made the loop integrals meaningful.
:::

## Prerequisites

You should know [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), and [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/). The comparison scheme is [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/).

We use

$$
d=4-2\epsilon,
\qquad
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

The renormalization scale $\mu$ is introduced so that renormalized couplings keep their conventional four-dimensional engineering dimensions.

## Core idea

A dimensionally regulated loop integral is a meromorphic function of $\epsilon$. Ultraviolet divergences appear as poles at $\epsilon=0$. For example,

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

MS subtracts the $1/\epsilon$ pole part. $\overline{\mathrm{MS}}$ subtracts $1/\bar\epsilon$. The finite logarithm remains.

Why is this enough? Because ultraviolet divergences in local QFT are local. Their pole parts can be canceled by local counterterms in the Lagrangian. The finite nonlocal terms, such as logarithms and threshold functions, are not counterterm mistakes; they are physical loop effects.

The scheme does not ask that a propagator have a pole at a particular mass, or that a vertex equal a measured coupling at a physical momentum. It defines parameters by a purely short-distance subtraction rule. Physical interpretation comes later, through conversion to observables.

## Setup and conventions

Let $g$ denote a dimensionless renormalized coupling in four dimensions. In $d=4-2\epsilon$, the corresponding bare coupling is written schematically as

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
$$

where $\kappa$ is fixed by dimensional analysis. For a gauge or Yukawa coupling, often $\kappa=1$. For a scalar quartic coupling in the convention $d=4-2\epsilon$, often $\kappa=2$.

In an MS-type scheme,

$$
Z_g(g,\epsilon)
=1+\sum_{L\ge1}\sum_{k=1}^{L}\frac{Z_{g,Lk}(g)}{\epsilon^k}.
$$

There are no finite pieces in $Z_g$ beyond those implied by the chosen definition of $\mu$ or $\bar\mu$. This is the defining simplicity of MS.

For fields and masses one similarly writes

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=Z_{m^2}m^2,
$$

with $Z$ factors containing only pole terms in MS-type schemes.

The renormalized parameters $g(\mu)$, $m(\mu)$, and fields $\phi(\mu)$ are not directly measured objects. They are scheme-defined coordinates at the scale $\mu$.

## MS and modified MS

The original minimal-subtraction prescription is:

$$
\text{MS: subtract the coefficients of }\frac{1}{\epsilon^k}.
$$

Modified minimal subtraction is:

$$
\overline{\mathrm{MS}}:
\text{ subtract the same poles together with }-\,\gamma_E+\log(4\pi)
\text{ factors in the standard combination.}
$$

Equivalently, one can absorb those constants into a modified scale. A common relation is

$$
\bar\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

Conventions differ about whether formulas are written with $\mu$ or $\bar\mu$. The content is the same once the convention is stated.

The advantage of $\overline{\mathrm{MS}}$ is practical. Dimensional-regularization integrals naturally produce the combination

$$
\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

Subtracting this combination prevents harmless constants from contaminating every finite result. That is why $\overline{\mathrm{MS}}$ is the default scheme in much of perturbative QCD, electroweak precision theory, and EFT.

## What the subtraction removes

Consider a regulated one-loop contribution to a Green function of the form

$$
\Gamma_{\text{loop}}(p_i)
=\frac{A(p_i)}{\epsilon}+F(p_i,\mu)+O(\epsilon),
$$

where $A(p_i)$ is a polynomial in external momenta and masses compatible with locality and symmetries. The MS counterterm is

$$
\Gamma_{\text{ct}}^{\mathrm{MS}}(p_i)=-\frac{A(p_i)}{\epsilon}.
$$

The renormalized result is

$$
\Gamma_R^{\mathrm{MS}}(p_i)=F(p_i,\mu).
$$

In $\overline{\mathrm{MS}}$, the counterterm includes the $-\gamma_E+\log4\pi$ pieces that accompany the pole. The finite result differs by a finite local term. That difference is a scheme change.

The subtraction removes local ultraviolet sensitivity. It does not remove physical nonlocal dependence. Terms such as

$$
\log\frac{-p^2-i\epsilon}{\mu^2},
\qquad
\sqrt{1-\frac{4m^2}{s}},
\qquad
\log\frac{1+\sqrt{1-4m^2/s}}{1-\sqrt{1-4m^2/s}}
$$

are not eliminated by local counterterms. They encode long-distance propagation, thresholds, and branch cuts.

## Why the scale remains

Dimensional regularization introduces $\mu$ to keep couplings dimensionally comparable as $d$ changes. After subtracting poles, finite answers still contain $\mu$. For example,

$$
\Gamma_R(p)
\sim
g(\mu)
+cg^2(\mu)\log\frac{\mu^2}{-p^2-i\epsilon}
+\cdots.
$$

This does not mean that a physical observable depends on an arbitrary scale. It means that the explicit $\mu$ dependence in loop logarithms must cancel the implicit $\mu$ dependence of renormalized parameters, order by order:

$$
\mu\frac{d}{d\mu}\mathcal O_{\text{phys}}=0.
$$

This cancellation is the origin of renormalization group equations in MS-type schemes. The scale $\mu$ is not a physical cutoff. It is a label for the renormalized coordinate system.

## Beta functions from pole coefficients

The beta function follows from the statement that bare parameters do not depend on $\mu$. Suppose

$$
g_0=\mu^{\kappa\epsilon}
\left[g+\frac{a_1(g)}{\epsilon}+\frac{a_2(g)}{\epsilon^2}+\cdots\right].
$$

At fixed $g_0$,

$$
0=\mu\frac{d g_0}{d\mu}.
$$

This determines

$$
\beta_g(g)\equiv \left.\mu\frac{dg}{d\mu}\right|_{g_0}.
$$

The finite four-dimensional beta function is determined by the simple-pole coefficient:

$$
\beta_g(g)=\kappa\left(g\frac{d}{dg}-1\right)a_1(g),
\qquad \epsilon\to0,
$$

with the conventions used above. Higher poles are not independent; their coefficients are constrained by consistency of the RG equation.

This result is one reason MS is so efficient. To obtain beta functions, one does not need the full finite part of every amplitude. The pole part contains the RG data.

:::tip[Do not memorize without conventions]
The precise beta-function formula depends on whether the bare coupling is written as $g_0=\mu^{\kappa\epsilon}Z_g g$, $g_0^2=\mu^{2\kappa\epsilon}Z_{g^2}g^2$, or with another normalization. The invariant rule is always: differentiate the bare parameter at fixed bare theory.
:::

## Example: scalar φ-four theory

Use the four-dimensional interaction convention

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4.
$$

In $d=4-2\epsilon$, write

$$
\mathcal L_{\text{int}}=-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4.
$$

With this convention, the one-loop four-point divergence in $\lambda\phi^4$ theory gives a bare coupling of the schematic form

$$
\lambda_0
=\mu^{2\epsilon}
\left[
\lambda+\frac{3\lambda^2}{32\pi^2\epsilon}+O(\lambda^3)
\right]
$$

in MS. Here

$$
a_1(\lambda)=\frac{3\lambda^2}{32\pi^2},
\qquad
\kappa=2.
$$

Therefore

$$
\beta_\lambda
=2\left(\lambda\frac{d}{d\lambda}-1\right)
\frac{3\lambda^2}{32\pi^2}
+O(\lambda^3)
=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

This is the familiar one-loop beta function for the quartic coupling in this normalization.

The calculation illustrates the main point: the coefficient of the local ultraviolet pole determines the leading running. The finite part of the one-loop four-point function is needed for amplitudes, but not for the leading beta function.

## Mass-independent schemes

MS and $\overline{\mathrm{MS}}$ are examples of **mass-independent schemes**. In such schemes, beta functions for dimensionless couplings depend on dimensionless couplings but not explicitly on mass ratios such as $m^2/\mu^2$.

This is extremely useful. It means that the RG equation for a coupling can often be written as

$$
\mu\frac{dg}{d\mu}=\beta_g(g),
$$

rather than

$$
\mu\frac{dg}{d\mu}=\beta_g(g,m^2/\mu^2,\ldots).
$$

The price is that heavy particles do not automatically decouple when $\mu$ drops below their mass. In $\overline{\mathrm{MS}}$, a heavy field may continue to contribute to the beta function unless one constructs an EFT below the threshold and matches parameters at $\mu\sim M$.

Thus the modern workflow is:

$$
\text{match at thresholds}
\quad\longrightarrow\quad
\text{run in each EFT with MS-type RG equations}.
$$

This is one of the main reasons minimal subtraction is central in effective field theory.

## What MS hides

Minimal subtraction is elegant because it ignores power divergences and subtracts only poles. That elegance can also hide physics from beginners.

In dimensional regularization, scaleless integrals vanish:

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2)^\alpha}=0
$$

when no scale is present and the integral is interpreted dimensionally. This vanishing often represents a cancellation between ultraviolet and infrared poles. It is not the same statement as "there is no short-distance sensitivity" in every physical sense.

MS also makes quadratic sensitivity invisible as a power of a hard cutoff. A scalar mass may receive corrections that look like

$$
\delta m^2\sim \frac{\lambda}{16\pi^2}\Lambda^2
$$

in a cutoff language, while dimensional regularization displays pole and logarithmic structures instead. The naturalness question is not answered merely by choosing MS. It is a question about sensitivity to physical heavy thresholds and relevant operators.

The safe lesson is:

$$
\text{MS is a clean subtraction language, not a philosophy of what is real.}
$$

## Scheme conversion

Suppose two schemes define couplings $g$ and $g'$ related by a finite redefinition

$$
g'=g+c g^3+O(g^5).
$$

Their beta functions are related by the chain rule:

$$
\beta_{g'}(g')=\frac{dg'}{dg}\beta_g(g).
$$

If

$$
\beta_g=b_1g^3+b_2g^5+O(g^7),
$$

then the leading coefficient $b_1$ is unchanged by such a finite analytic redefinition. Higher coefficients may change, depending on the theory, coupling normalization, and class of allowed schemes.

This is how one compares MS, $\overline{\mathrm{MS}}$, momentum subtraction, and on-shell definitions. They are not rival physical theories. They are different parameterizations of the same bare or low-energy physics.

## Practical workflow

In a typical MS or $\overline{\mathrm{MS}}$ calculation:

1. Choose a regulator, usually dimensional regularization.
2. Write the most general local counterterms needed by symmetries and power counting.
3. Compute loop diagrams and extract pole parts.
4. Choose MS or $\overline{\mathrm{MS}}$ counterterms to cancel those poles.
5. Derive beta functions and anomalous dimensions from the $Z$ factors.
6. Express observables in terms of renormalized parameters at scale $\mu$.
7. Use RG evolution to choose or relate convenient scales.
8. Convert to physical input parameters when comparing with experiment.

This workflow is why MS-type schemes dominate high-order perturbative QFT. They separate ultraviolet bookkeeping from physical interpretation.

## Common pitfalls

**Thinking MS parameters are directly measured.** A value like $m_{\overline{\mathrm{MS}}}(m)$ or $\alpha_s(M_Z)$ is a scheme-defined quantity inferred from observables. It is not read directly off a detector.

**Forgetting the scale.** A coupling in MS is incomplete unless the scale is specified. Write $g(\mu)$, not just $g$.

**Mistaking $\mu$ for a cutoff.** The scale $\mu$ is not the maximum momentum in a loop. It is the renormalization scale introduced by dimensional continuation and subtraction.

**Assuming heavy particles decouple automatically.** In mass-independent schemes, decoupling is implemented by matching to an EFT below the heavy threshold.

**Interpreting vanishing scaleless integrals too literally.** A scaleless integral can vanish because UV and IR singularities cancel in dimensional regularization. The vanishing answer may hide separate UV and IR structures.

**Comparing beta functions without comparing couplings.** A beta function belongs to a particular definition of the coupling. Scheme conversion is part of the comparison.

## Relations to other pages

[On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/) explains physical pole and amplitude conditions.

[Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) develops field $Z$ factors and anomalous dimensions.

[Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) gives the systematic derivation and interpretation of RG flow.

[Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) explains how field and operator $Z$ factors produce scaling corrections.

[Matching](/renormalization-rg-eft/effective-field-theory/matching/) explains how MS parameters are related across EFT thresholds.

[Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) gives the coordinate-transformation view of RG equations.

## Research status

MS and $\overline{\mathrm{MS}}$ are settled tools. The active work lies in difficult implementations: high-loop QCD and electroweak calculations, multi-scale EFT matching, operator mixing in large bases, evanescent operators, chiral theories in dimensional regularization, $\gamma^5$ prescriptions, threshold masses, lattice-to-continuum matching, and automated renormalization pipelines.

A mature calculation states not only the regulator and scheme but also the operator basis, evanescent-operator convention when relevant, flavor and gauge conventions, threshold prescription, and conversion formulas for physical input parameters.

## Exercises

### Exercise 1: Extract the modified MS finite part

Starting from

$$
J_2(\Delta)=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right],
$$

what is the $\overline{\mathrm{MS}}$-renormalized value of $J_2$?

<details><summary><strong>Solution</strong></summary>

In $\overline{\mathrm{MS}}$, subtract the $1/\bar\epsilon$ term. Therefore

$$
J_{2,R}^{\overline{\mathrm{MS}}}(\Delta)
=
-\frac{1}{16\pi^2}\log\frac{\Delta}{\mu^2}.
$$

The finite logarithm remains because it is not a local pole. It carries the scale dependence that the RG equation tracks.

</details>

### Exercise 2: Derive the one-loop φ-four beta function from the pole

Assume

$$
\lambda_0
=\mu^{2\epsilon}
\left[
\lambda+\frac{3\lambda^2}{32\pi^2\epsilon}+O(\lambda^3)
\right].
$$

Use

$$
\beta_\lambda=2\left(\lambda\frac{d}{d\lambda}-1\right)a_1(\lambda)
$$

for $\lambda_0=\mu^{2\epsilon}[\lambda+a_1(\lambda)/\epsilon+\cdots]$. Find $\beta_\lambda$ to order $\lambda^2$.

<details><summary><strong>Solution</strong></summary>

Here

$$
a_1(\lambda)=\frac{3\lambda^2}{32\pi^2}.
$$

Then

$$
\lambda\frac{d}{d\lambda}a_1(\lambda)
=\lambda\frac{d}{d\lambda}\frac{3\lambda^2}{32\pi^2}
=\frac{6\lambda^2}{32\pi^2}.
$$

Thus

$$
\left(\lambda\frac{d}{d\lambda}-1\right)a_1(\lambda)
=\frac{3\lambda^2}{32\pi^2}.
$$

Multiplying by $2$ gives

$$
\beta_\lambda
=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

</details>

### Exercise 3: Scheme conversion and the leading beta coefficient

Let

$$
g'=g+c g^3+O(g^5),
$$

and

$$
\beta_g=b_1g^3+O(g^5).
$$

Show that the leading coefficient of $\beta_{g'}$ is also $b_1$.

<details><summary><strong>Solution</strong></summary>

Use the chain rule:

$$
\beta_{g'}=\frac{dg'}{dg}\beta_g.
$$

Since

$$
\frac{dg'}{dg}=1+3c g^2+O(g^4),
$$

we get

$$
\beta_{g'}=(1+3c g^2+O(g^4))(b_1g^3+O(g^5))
=b_1g^3+O(g^5).
$$

Also $g'=g+O(g^3)$ implies $g^3=g'^3+O(g'^5)$. Therefore

$$
\beta_{g'}=b_1g'^3+O(g'^5).
$$

The leading coefficient is unchanged.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially sections on other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23 and appendix B.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization and asymptotic freedom lectures.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on dimensional regularization, renormalization, and RG equations.
- Gerard 't Hooft and Martinus Veltman, classic papers on dimensional regularization and renormalization of gauge theories.

## Version history

- 2026-06-17: First polished draft. Defined MS and $\overline{\mathrm{MS}}$, explained pole subtraction, beta functions from pole coefficients, mass-independent schemes, decoupling caveats, scheme conversion, and practical workflows.
