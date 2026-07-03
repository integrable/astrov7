---
title: "Modified Minimal Subtraction"
description: "How the MS-bar scheme removes the universal gamma_E and log 4 pi constants of dimensional regularization, defines standard running parameters, and organizes RG calculations."
sidebar:
  label: "MS-bar Scheme"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§27–29; Schwartz chs. 18–23 and appendix B; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Coleman, renormalization lectures; Zinn-Justin, renormalization chapters."
topics:
  - modified minimal subtraction
  - MS-bar scheme
  - dimensional regularization
  - renormalization scale
  - running parameters
  - scheme conversion
canonicalTopics:
  - msbar-scheme
  - modified-minimal-subtraction
  - renormalization-scale
  - mass-independent-renormalization
researchStatus:
  established:
    - "The MS-bar scheme is the standard modified minimal-subtraction scheme used with dimensional regularization in perturbative QFT, gauge theory, and EFT."
  active:
    - "High-order scheme conversions, evanescent operators, gamma-five prescriptions, heavy-threshold matching, and precision definitions of running Standard Model parameters remain technically active."
---

## Summary

The **MS-bar scheme**, written $\overline{\mathrm{MS}}$, is the most widely used refinement of minimal subtraction. In dimensional regularization near four spacetime dimensions,

$$
d=4-2\epsilon,
$$

loop integrals naturally produce the combination

$$
\frac{1}{\bar\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

Minimal subtraction, or MS, subtracts only pole terms in $1/\epsilon$. Modified minimal subtraction, or $\overline{\mathrm{MS}}$, subtracts pole terms in the combination $1/\bar\epsilon$. Equivalently, one may absorb the constants $\log(4\pi)-\gamma_E$ into a modified renormalization scale.

The point of $\overline{\mathrm{MS}}$ is not deep metaphysics. It is the best kind of boring convention: it removes constants that dimensional regularization produces everywhere, leaving cleaner logarithms, cleaner counterterms, and especially clean renormalization group equations.

The practical rule is:

$$
\text{in }\overline{\mathrm{MS}},\text{ subtract the local pole part in }\frac{1}{\bar\epsilon}\text{ and no finite physical normalization condition.}
$$

:::note[Terminology]
Many authors use the symbol $\mu$ for the $\overline{\mathrm{MS}}$ scale after absorbing $4\pi e^{-\gamma_E}$. Other authors distinguish $\mu$ from $\bar\mu$. This page first displays the distinction, then uses $\mu$ as the renormalization scale of the chosen scheme unless the distinction matters.
:::

## Prerequisites

You should know [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/), and [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/). The comparison with directly physical conditions is in [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/).

We use the volume conventions

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log(4\pi),
$$

and write dimensional regularization near four dimensions as $d=4-2\epsilon$.

## Core idea

Dimensional regularization is elegant because it preserves translation invariance, Lorentz covariance, and usually gauge symmetry better than a hard momentum cutoff. Its bookkeeping cost is that the angular volume in $d$ dimensions and the gamma functions in loop integrals produce the same finite constants over and over:

$$
\gamma_E,
\qquad
\log(4\pi).
$$

For example, a basic Euclidean logarithmic integral gives

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+\log(4\pi)
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

The combination in brackets is naturally

$$
\frac{1}{\bar\epsilon}-\log\frac{\Delta}{\mu^2}+O(\epsilon).
$$

The $\overline{\mathrm{MS}}$ prescription subtracts $1/\bar\epsilon$. After subtraction, the finite logarithm is simply

$$
-\log\frac{\Delta}{\mu^2}.
$$

If instead one subtracts only $1/\epsilon$, the answer contains the extra finite constant $-\gamma_E+\log(4\pi)$. That is not wrong. It is just a less convenient coordinate choice.

## Setup and conventions

Let $g$ denote a dimensionless coupling in four spacetime dimensions. In $d=4-2\epsilon$, it is convenient to write a bare coupling as

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
$$

where $\kappa$ is determined by engineering dimension. For a gauge or Yukawa coupling, $\kappa=1$ in common conventions. For a scalar quartic coupling, $\kappa=2$.

In an MS-type scheme, the renormalization factor has only poles:

$$
Z_g(g,\epsilon)
=1+\sum_{L\ge1}\sum_{k=1}^{L}\frac{Z_{g,Lk}(g)}{\epsilon^k}.
$$

In $\overline{\mathrm{MS}}$, the same statement is made after using the modified scale or, equivalently, after subtracting the combination $1/\bar\epsilon$. The field and mass factors are written similarly:

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=Z_{m^2}m^2.
$$

A page using $\overline{\mathrm{MS}}$ should specify whether $\mu$ denotes the original dimensional-regularization scale or the modified scale. This site usually uses $\mu$ for the final renormalization scale after the scheme is fixed, and displays $\bar\mu$ only when comparing conventions.

## The modified scale

The constants can be absorbed into the scale definition

$$
\bar\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

Then

$$
\frac{1}{\epsilon}-\gamma_E+\log(4\pi)+\log\frac{\mu^2}{\Delta}
=
\frac{1}{\epsilon}+\log\frac{\bar\mu^2}{\Delta}.
$$

So there are two equivalent ways to describe $\overline{\mathrm{MS}}$:

| Description | What one writes |
|---|---|
| Subtract the modified pole | subtract $1/\bar\epsilon$ and keep $\mu$ |
| Use the modified scale | rewrite in terms of $\bar\mu$ and subtract $1/\epsilon$ |

The two descriptions are the same convention expressed in different notation. What matters is not the letter on the scale; what matters is which finite constants have been included in the subtraction.

This is why literature comparisons are occasionally annoying. One author's $\mu$ may be another author's $\bar\mu$. Before comparing constants in finite one-loop answers, identify the scale convention.

## MS versus MS-bar

MS and $\overline{\mathrm{MS}}$ differ by a finite local scheme change. A one-loop renormalized Green function might look like

$$
\Gamma_R^{\mathrm{MS}}(Q)
=A\log\frac{\mu_{\mathrm{MS}}^2}{Q^2}
+A(\log4\pi-\gamma_E)+B,
$$

while the $\overline{\mathrm{MS}}$ version is

$$
\Gamma_R^{\overline{\mathrm{MS}}}(Q)
=A\log\frac{\mu_{\overline{\mathrm{MS}}}^2}{Q^2}+B.
$$

These are not different predictions. They are different definitions of the renormalized parameter and scale. Choosing

$$
\mu_{\overline{\mathrm{MS}}}^2=4\pi e^{-\gamma_E}\mu_{\mathrm{MS}}^2
$$

maps the logarithms into each other.

At higher orders, a finite scheme change can be more than a rescaling of $\mu$. For several couplings, it can be a nonlinear coordinate transformation on coupling space:

$$
g^{\prime i}=g^i+a^i{}_{jk}g^jg^k+\cdots.
$$

Beta functions then transform as vector fields:

$$
\beta^{\prime i}(g')=
\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

The labels MS and $\overline{\mathrm{MS}}$ therefore name coordinates, not separate physical worlds.

## Why MS-bar is everywhere

The $\overline{\mathrm{MS}}$ scheme is popular because it is **mass independent** and algebraic. In a mass-independent scheme, counterterms depend on masses only through dimensionless couplings and operator coefficients in the way fixed by the theory's interactions; the subtraction rule itself is tied to ultraviolet pole parts, not to thresholds such as $p^2=m^2$.

This has several advantages:

| Advantage | Why it matters |
|---|---|
| Simple beta functions | Pole coefficients determine RG functions efficiently. |
| Clean high-energy limits | Heavy physical thresholds do not enter every subtraction condition. |
| Gauge-theory compatibility | Dimensional regularization plus $\overline{\mathrm{MS}}$ usually preserves gauge identities efficiently. |
| EFT usefulness | Matching and running can be separated cleanly. |
| Multi-loop practicality | Algebraic pole subtraction scales better than imposing physical conditions graph by graph. |

The cost is interpretation. A running $\overline{\mathrm{MS}}$ mass or coupling is not itself an observable. It becomes meaningful through a prescription for extracting observables or through conversion to another scheme.

## Example: a logarithmic integral

Start from

$$
J(\Delta)
=\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}.
$$

Using the standard Euclidean master integral,

$$
J(\Delta)
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

Expand the pieces:

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
$$

and

$$
\mu^{2\epsilon}(4\pi)^\epsilon\Delta^{-\epsilon}
=1+\epsilon\left(\log4\pi+\log\frac{\mu^2}{\Delta}\right)+O(\epsilon^2).
$$

Then

$$
J(\Delta)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\bar\epsilon}
-\log\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

The $\overline{\mathrm{MS}}$ subtraction removes the first term and leaves

$$
J_R^{\overline{\mathrm{MS}}}(\Delta)
=-\frac{1}{16\pi^2}\log\frac{\Delta}{\mu^2}.
$$

The minus sign is not the important part. The important part is that the result depends on $\Delta$ only through the logarithm of a physical scale divided by a renormalization scale.

## Running parameters in MS-bar

Because bare quantities do not depend on the arbitrary renormalization scale,

$$
\mu\frac{d}{d\mu}g_0=0.
$$

But $g_0$ is written in terms of $g(\mu)$, $\mu$, and pole counterterms. Therefore $g(\mu)$ must run. The beta function is defined as

$$
\beta_g(g)=\left.\mu\frac{dg}{d\mu}\right|_{g_0}.
$$

In an MS-type scheme, the beta function is determined by the pole part of the renormalization constants. This is one of the reasons $\overline{\mathrm{MS}}$ is so efficient: finite physical renormalization conditions do not obscure the relation between UV poles and RG functions.

A typical perturbative expansion has the form

$$
\beta_g=b_1g^3+b_2g^5+O(g^7)
$$

for a gauge or Yukawa coupling. The coefficients $b_1$ and often $b_2$, under standard assumptions in mass-independent gauge-theory schemes, carry universal information. Higher coefficients depend more visibly on the scheme.

For scalar quartic couplings, Yukawa matrices, gauge couplings, masses, and Wilson coefficients, the same principle applies: the $\overline{\mathrm{MS}}$ counterterms encode the running.

## Heavy thresholds and decoupling

A subtle but crucial point: in a mass-independent scheme, heavy particles do not automatically disappear from beta functions when $\mu$ drops below their mass.

Suppose a theory contains a heavy field of mass $M$ and one computes in the full theory using $\overline{\mathrm{MS}}$. The full-theory beta function can still contain the heavy field contribution even for $\mu\ll M$, because the subtraction rule does not know about physical thresholds. Decoupling is restored by matching onto an EFT at a scale near $M$:

$$
\mathcal L_{\text{full}}
\quad\longrightarrow\quad
\mathcal L_{\text{EFT}}
\quad\text{at }\mu\sim M.
$$

The EFT has different fields and different beta functions. Heavy-particle effects below the threshold are encoded in Wilson coefficients and threshold corrections.

This is why the standard precision workflow is:

$$
\text{match near }M,
\qquad
\text{run between scales},
\qquad
\text{compute observables at }Q.
$$

$\overline{\mathrm{MS}}$ is excellent for this workflow, but only if matching is not forgotten.

## Scheme conversion

Suppose two schemes define couplings $g$ and $g'$ by

$$
g'=g+c_1g^3+c_2g^5+\cdots.
$$

Then an observable computed in terms of $g$ can be rewritten in terms of $g'$ by substitution. For example,

$$
\mathcal O=A g^2+B g^4+O(g^6)
$$

becomes

$$
\mathcal O=A g'^2+(B-2Ac_1)g'^4+O(g'^6).
$$

The number assigned to the coupling changes, and the coefficients in the perturbative expansion change, but the observable does not when the conversion is done to the same order.

The most common conversion tasks are:

| Conversion | Why one does it |
|---|---|
| $\overline{\mathrm{MS}}$ mass to pole mass | compare short-distance mass parameters to particle poles |
| pole mass to $\overline{\mathrm{MS}}$ mass | avoid infrared sensitivity and improve perturbative behavior |
| on-shell charge to $\overline{\mathrm{MS}}$ charge | run electroweak parameters at high scales |
| full-theory coupling to EFT coupling | integrate out heavy particles |
| operator basis conversion | compare anomalous dimensions and Wilson coefficients across papers |

When comparing papers, a mismatch of scheme can masquerade as a disagreement. The fix is almost never philosophical. It is algebra.

## Gauge theories and MS-bar

In gauge theories, $\overline{\mathrm{MS}}$ is powerful because dimensional regularization and pole subtraction fit naturally with Ward, Slavnov–Taylor, and background-field identities. This does not mean every intermediate $Z$ factor is gauge independent. Field renormalization constants, off-shell Green functions, and some intermediate counterterms can depend on the gauge-fixing parameter.

Physical observables and properly defined gauge-invariant quantities do not depend on the gauge choice. Universal beta-function coefficients are also gauge independent under their usual assumptions.

A common trap is to compute a gauge-dependent off-shell Green function, extract a finite piece, and call it a physical coupling. In $\overline{\mathrm{MS}}$, the running coupling is a scheme-defined coordinate. Its physical use comes from putting it into a consistent calculation of a gauge-invariant observable or matching condition.

## Common pitfalls

**Thinking MS-bar is a regulator.** The regulator is dimensional regularization. $\overline{\mathrm{MS}}$ is the subtraction rule.

**Forgetting which scale is called $\mu$.** Some authors absorb $4\pi e^{-\gamma_E}$ into the scale and still call it $\mu$. Others display $\bar\mu$. Check before comparing finite constants.

**Treating running parameters as directly measured observables.** A running $\overline{\mathrm{MS}}$ coupling is not measured by a single detector readout. It is inferred through a convention-dependent fit or conversion.

**Expecting automatic decoupling.** Heavy particles do not automatically drop out of mass-independent beta functions at low $\mu$. One must match to an EFT.

**Calling finite scheme differences mistakes.** Finite local differences between schemes are often just coordinate transformations. The observable test is whether predictions agree after conversion.

**Ignoring evanescent structures.** In theories with spinor identities, chiral projectors, four-fermion operators, or gamma-five subtleties, operators that vanish in exactly four dimensions can affect finite scheme conversions.

## Relations to other pages

[Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/) introduces pole subtraction broadly. This page isolates the modified scheme used most often in practice.

[On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/) gives the contrast: physical pole and amplitude conditions rather than pole-only subtraction.

[Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) explains how $Z_\phi$, residues, and anomalous dimensions fit into the same scheme logic.

The Renormalization Group Equations chapter will turn the scale dependence of $\overline{\mathrm{MS}}$ parameters into Callan–Symanzik equations, beta functions, running masses, dimensional transmutation, and asymptotic freedom.

The Matching, Running, and Decoupling chapter will explain how $\overline{\mathrm{MS}}$ is used in EFT workflows with heavy thresholds.

## Research status

The basic $\overline{\mathrm{MS}}$ scheme is settled textbook material. Its power comes from being simple, local, and compatible with dimensional regularization.

The active work is not about whether $\overline{\mathrm{MS}}$ exists. It is about using it correctly in hard situations: multi-loop gauge theories, unstable particles, EFT operator bases, evanescent operators, chiral gauge theories, gamma-five prescriptions, threshold matching, infrared factorization, and high-precision Standard Model conversions.

## Exercises

### Exercise 1: The modified scale

Show that the replacement

$$
\bar\mu^2=4\pi e^{-\gamma_E}\mu^2
$$

turns

$$
\frac{1}{\epsilon}-\gamma_E+\log(4\pi)+\log\frac{\mu^2}{\Delta}
$$

into

$$
\frac{1}{\epsilon}+\log\frac{\bar\mu^2}{\Delta}.
$$

<details><summary><strong>Solution</strong></summary>

Taking the logarithm of the scale relation gives

$$
\log\bar\mu^2=\log\mu^2+\log(4\pi)-\gamma_E.
$$

Therefore

$$
\log\frac{\bar\mu^2}{\Delta}
=
\log\frac{\mu^2}{\Delta}+\log(4\pi)-\gamma_E.
$$

Substituting this into the original expression gives the desired result.

</details>

### Exercise 2: MS and MS-bar differ by a finite local term

A regulated one-loop contribution to a local vertex is

$$
\Gamma_{\text{loop}}
=A\left(\frac{1}{\epsilon}-\gamma_E+\log4\pi\right)+F.
$$

Find the renormalized answer in MS and in $\overline{\mathrm{MS}}$. What is their difference?

<details><summary><strong>Solution</strong></summary>

MS subtracts only $A/\epsilon$, so

$$
\Gamma_R^{\mathrm{MS}}
=A(-\gamma_E+\log4\pi)+F.
$$

$\overline{\mathrm{MS}}$ subtracts

$$
A\left(\frac{1}{\epsilon}-\gamma_E+\log4\pi\right),
$$

so

$$
\Gamma_R^{\overline{\mathrm{MS}}}=F.
$$

The difference is the finite local term

$$
\Gamma_R^{\mathrm{MS}}-\Gamma_R^{\overline{\mathrm{MS}}}
=A(-\gamma_E+\log4\pi).
$$

This finite difference is a scheme change, not a physical contradiction.

</details>

### Exercise 3: Scheme conversion in a simple observable

Let

$$
\mathcal O=A g^2+B g^4+O(g^6)
$$

in one scheme, and suppose another scheme uses

$$
g'=g+c g^3+O(g^5).
$$

Rewrite $\mathcal O$ in terms of $g'$ through order $g'^4$.

<details><summary><strong>Solution</strong></summary>

Invert the coupling relation to the needed order:

$$
g=g'-c g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2c g'^4+O(g'^6),
\qquad
g^4=g'^4+O(g'^6).
$$

Therefore

$$
\mathcal O
=A g'^2+(B-2Ac)g'^4+O(g'^6).
$$

The coefficient of the $g'^4$ term changes, but the observable is the same perturbative quantity expressed in a different coordinate.

</details>

### Exercise 4: Why matching is needed for heavy thresholds

In one sentence, explain why a heavy particle of mass $M$ does not automatically decouple from a mass-independent beta function at $\mu\ll M$.

<details><summary><strong>Solution</strong></summary>

A mass-independent subtraction rule removes ultraviolet pole parts without imposing physical threshold conditions, so the beta function belongs to the theory whose field content was used in the subtraction; to remove the heavy particle from low-energy running one must match to an EFT without that field near $\mu\sim M$.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on mass renormalization, renormalized perturbation theory, renormalizability, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for systematic dimensional regularization, minimal subtraction, RG functions, and critical phenomena.
- John C. Collins, *Renormalization*, for a detailed treatment of subtraction schemes and factorization-oriented renormalization.

## Version history

- 2026-06-17: First polished draft. Separated the MS-bar convention from the broader minimal-subtraction page, with emphasis on scale conventions, scheme conversion, mass-independent running, and heavy-threshold matching.
