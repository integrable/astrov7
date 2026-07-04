---
title: "Minimal Subtraction"
description: "How minimal subtraction and MS-bar define renormalized parameters by subtracting only epsilon-pole parts in dimensional regularization."
sidebar:
  label: "Minimal Subtraction"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20 and 27–28; Coleman 2019, chs. 15–16 and 25; Weinberg 1995, Vol. I, ch. 12 and Vol. II, §18.6; Schwartz 2014, chs. 18–23; Zinn-Justin 2021, ch. 10"
topics:
  - minimal subtraction
  - MS-bar scheme
  - dimensional regularization
  - renormalization schemes
  - beta functions
canonicalTopics:
  - minimal-subtraction
  - msbar-scheme
  - pole-subtraction
  - renormalization-scale
  - mass-independent-scheme
researchStatus:
  established:
    - "Minimal subtraction and MS-bar are standard dimensional-regularization schemes: counterterms subtract only epsilon-pole parts, leaving finite terms to define scale-dependent renormalized parameters."
  active:
    - "Modern precision applications require careful MS-bar matching, scheme conversion, evanescent operators, threshold treatments, and infrared-safe definitions in gauge theories and EFTs."
---

## Summary

**Minimal subtraction** is a renormalization scheme designed for dimensional regularization. A regulated loop integral is expanded around

$$
d=4-2\epsilon,
$$

and ultraviolet divergences appear as poles in $\epsilon$. Minimal subtraction removes the pole part and no more.

For a Laurent expansion

$$
F(\epsilon)=\frac{f_{-2}}{\epsilon^2}+\frac{f_{-1}}{\epsilon}+f_0+f_1\epsilon+\cdots,
$$

the minimal-subtraction operation removes

$$
K_{\rm MS}[F]
=
\frac{f_{-2}}{\epsilon^2}+\frac{f_{-1}}{\epsilon}.
$$

The closely related $\overline{\mathrm{MS}}$ scheme subtracts the ubiquitous combination

$$
\frac{1}{\overline\epsilon}
\equiv
\frac{1}{\epsilon}-\gamma_E+\ln4\pi
$$

rather than a bare $1/\epsilon$. Equivalently, $\overline{\mathrm{MS}}$ packages the constants $\gamma_E$ and $\ln4\pi$ into the definition of the renormalization scale.

Minimal subtraction is not a physical measurement prescription. It does not define masses as pole masses or couplings as values of amplitudes at specified momenta. It defines a clean, algebraic coordinate system on renormalized perturbation theory. Its great advantage is that beta functions and anomalous dimensions can be read efficiently from pole coefficients.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Flow chart showing dimensional regularization producing a Laurent series, pole projection, minimal-subtraction counterterms, finite remainders, and renormalization-scale dependence](/figures/perturbative-qft/minimal-subtraction-flow.svg)

<figcaption>

Minimal subtraction is a pole-projection scheme. Dimensional regularization turns ultraviolet divergences into Laurent poles. The MS or $\overline{\mathrm{MS}}$ counterterm subtracts the pole part, while finite logarithms remain and generate renormalization-scale dependence.

</figcaption>
</figure>

## Prerequisites

You should know [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/), [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/), [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/), [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), and [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/).

For the origin of the $1/\overline\epsilon$ combination, review the logarithmic integral in [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/).

## Core idea

A physical renormalization scheme fixes counterterms by demanding that selected observables or Green functions take selected finite values. Minimal subtraction fixes counterterms by a simpler rule:

$$
\text{counterterms cancel the pole part of dimensionally regularized loop diagrams.}
$$

That is all. No finite condition is imposed. If a loop diagram contains

$$
\frac{A}{\epsilon}+B+O(\epsilon),
$$

minimal subtraction removes $A/\epsilon$ and leaves $B$. In $\overline{\mathrm{MS}}$, the subtracted object is usually written as $A/\overline\epsilon$ and the finite remainder is correspondingly shifted by constants.

This rule is austere, but that austerity is useful. The counterterms become local algebraic pole subtractions, and the renormalization scale $\mu$ carries the information about how the renormalized parameters must run.

The slogan is

$$
\text{MS defines parameters by pole subtraction, not by direct measurement.}
$$

Physical predictions still require matching MS parameters to measured quantities. The scheme is a coordinate system, not an observable.

## Setup and conventions

We use qft.org mostly-minus conventions and dimensional regularization with

$$
d=4-2\epsilon.
$$

For scalar $\phi^4$ theory, the renormalized interaction is written

$$
\mathcal L_{\rm int}
=
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

so $\lambda$ is dimensionless near four dimensions. The counterterm is

$$
\mathcal L_{\rm ct}
\supset
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4,
$$

with counterterm vertex

$$
{\mathcal V_{4,\rm ct}=-i\mu^{2\epsilon}\delta\lambda.}
$$

For two-point functions we use

$$
\mathcal L_{\rm ct}^{(2)}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2,
$$

so the scalar self-energy counterterm is

$$
\Sigma_{\rm ct}(p^2)=\delta m^2-\delta Z\,p^2.
$$

The notation $\rm MS$ means pure minimal subtraction of $1/\epsilon$ poles. The notation $\overline{\mathrm{MS}}$ means the modified minimal-subtraction convention that subtracts $1/\overline\epsilon$ combinations. Most high-energy calculations called “MS-bar” use the latter.

## Pole projection

Let a dimensionally regulated quantity have the Laurent expansion

$$
F(\epsilon)=\sum_{n=-N}^{\infty}f_n\epsilon^n.
$$

Define the pole part

$$
K_{\rm MS}[F]
\equiv
\sum_{n=-N}^{-1}f_n\epsilon^n.
$$

Then the minimally subtracted finite part is

$$
F_{\rm MS}
=
\lim_{\epsilon\to0}\left(F(\epsilon)-K_{\rm MS}[F]\right).
$$

In actual Feynman diagrams, this formula is applied to local ultraviolet pole parts of 1PI amplitudes, not indiscriminately to every singular expression one writes down. Infrared poles require separate physical treatment; they are not removed by ultraviolet renormalization.

For $\overline{\mathrm{MS}}$, one packages the constants that appear in Euclidean loop integrals by using

$$
\frac{1}{\overline\epsilon}
=
\frac{1}{\epsilon}-\gamma_E+
\ln4\pi.
$$

At one loop, saying “subtract $1/\overline\epsilon$” is unambiguous. At higher loops, one must consistently define the measure and scale convention, for example by using the $\overline{\mathrm{MS}}$ scale

$$
\overline\mu^2=4\pi e^{-\gamma_E}\mu^2.
$$

Different books distribute these constants differently. The physics is unchanged after scheme conversion.

## MS versus MS-bar

The distinction between MS and $\overline{\mathrm{MS}}$ is finite, not physical. Consider the standard logarithmic Euclidean integral

$$
\mu^{2\epsilon}
\int\frac{d^d k_E}{(2\pi)^d}
\frac{1}{(k_E^2+\Delta)^2}
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\overline\epsilon}
-
\ln\frac{\Delta}{\mu^2}
+O(\epsilon)
\right].
$$

Pure MS subtracts only $1/\epsilon$. The finite remainder then contains $-\gamma_E+\ln4\pi$ constants. The $\overline{\mathrm{MS}}$ convention subtracts $1/\overline\epsilon$, leaving the cleaner expression

$$
-\frac{1}{16\pi^2}
\ln\frac{\Delta}{\mu^2}
$$

for this integral's finite logarithmic part.

This is why $\overline{\mathrm{MS}}$ is usually the practical choice. It does not make a prediction more physical. It makes formulas shorter and scheme conversions standardized.

## What is subtracted and what remains

Minimal subtraction removes local ultraviolet poles. It does not remove finite terms, branch cuts, thresholds, or nonlocal momentum dependence.

A typical one-loop vertex correction has the schematic form

$$
\mathcal V^{(1)}(s)
=
\frac{A}{\overline\epsilon}
+
A\ln\frac{\mu^2}{m^2-sx(1-x)-i\epsilon}
+
\text{finite polynomial pieces}.
$$

The pole $A/\overline\epsilon$ is local. It is canceled by a local counterterm. The logarithm is not local in external momenta. It remains in the renormalized amplitude, where it encodes thresholds, scale dependence, and physical analytic structure.

That distinction is the sanity check for counterterms:

$$
\text{counterterms cancel local UV poles; they do not erase nonlocal physics.}
$$

A counterterm that tried to cancel an arbitrary function of $s$, $t$, and $u$ would not be a local term in the Lagrangian.

## Example: the φ⁴ coupling counterterm

In real scalar $\phi^4$ theory,

$$
\mathcal L_{\rm int}
=
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

the one-loop four-point vertex receives fish diagrams in the $s$, $t$, and $u$ channels. With the conventions of [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/), the divergent part is

$$
\mathcal V^{(1)}_{4,\rm div}
=
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

The coupling counterterm contributes

$$
\mathcal V_{4,\rm ct}=-i\delta\lambda.
$$

Cancellation of the pole gives

$$
-i\delta\lambda
+
i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}=0,
$$

so the $\overline{\mathrm{MS}}$ counterterm is

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
+O(\lambda^3).
$$

No subtraction point such as $s_*$ is chosen. No demand is made that the four-point function equal $-i\lambda$ at a particular physical momentum. The finite part of the loop correction stays in the renormalized vertex.

With the alternative convention $d=4-\epsilon_4$, the same pole is often written as

$$
\delta\lambda
=
\frac{3\lambda^2}{16\pi^2}\frac{1}{\epsilon_4}
+O(\lambda^3),
$$

because $\epsilon_4=2\epsilon$.

## Running from bare independence

Minimal subtraction makes the renormalization group especially transparent. The bare coupling is independent of the arbitrary scale $\mu$:

$$
\mu\frac{d\lambda_0}{d\mu}=0.
$$

For the one-loop scalar example, suppressing the finite $\overline{\mathrm{MS}}$ constants and writing the pole coefficient as

$$
a=\frac{3}{32\pi^2},
$$

the bare coupling has the form

$$
\lambda_0
=
\mu^{2\epsilon}
\left[\lambda+\frac{a\lambda^2}{\epsilon}+O(\lambda^3)\right].
$$

The $d$-dimensional beta function is defined at fixed bare coupling:

$$
\beta_\lambda^{(d)}
\equiv
\mu\frac{d\lambda}{d\mu}\bigg|_{\lambda_0}.
$$

Solving order by order gives

$$
\beta_\lambda^{(d)}
=
-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

Therefore, in four dimensions,

$$
\beta_\lambda
=
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

The pole coefficient knows the running. This is one reason MS schemes are so efficient in multi-loop renormalization.

## Masses and fields in MS schemes

Minimal subtraction applies to all counterterms, not only couplings. For the scalar two-point function,

$$
\Sigma_{\rm ren}(p^2)
=
\Sigma_{\rm loop}(p^2)+\delta m^2-\delta Zp^2.
$$

An MS rule fixes

$$
\delta m^2=\text{pole part needed to cancel masslike UV poles},
$$

and

$$
\delta Z=\text{pole part needed to cancel the coefficient of }p^2\text{ UV poles}.
$$

This does **not** generally put the propagator pole at $p^2=m^2$. It also does **not** make the pole residue equal to one. Those are on-shell conditions, not MS conditions.

For example, in four-dimensional $\phi^4$ theory the one-loop tadpole self-energy is momentum independent. Hence

$$
\delta Z^{(1)}_{\overline{\mathrm{MS}}}=0
$$

in that model, while $\delta m^{2(1)}$ is nonzero. Momentum-dependent field-strength renormalization first appears at higher loop order in $\phi^4$ theory, but it appears already at one loop in many other theories, such as Yukawa theory and QED.

## Mass-independent character

In a renormalizable theory, MS and $\overline{\mathrm{MS}}$ are often called **mass-independent schemes**. The beta functions for dimensionless couplings depend only on dimensionless couplings, not on ratios such as $m^2/\mu^2$.

The reason is structural. Minimal subtraction looks only at ultraviolet pole coefficients. For logarithmic UV poles in a renormalizable theory, the pole part of a dimensionless coupling counterterm is local and independent of infrared mass scales. Masses can enter mass counterterms and anomalous dimensions, but they do not appear in the beta function of a dimensionless coupling in the same way a physical threshold scheme would.

This is both a feature and a warning. Heavy particles do not automatically decouple from MS beta functions at $\mu$ below their mass. Decoupling is implemented by matching to an effective theory at a threshold and then running in the lower-energy theory.

## Scheme changes

Two renormalization schemes can differ by finite redefinitions. For one coupling,

$$
\lambda'=\lambda+c\lambda^2+O(\lambda^3).
$$

The beta functions are related by the chain rule:

$$
\beta_{\lambda'}(\lambda')
=
\frac{d\lambda'}{d\lambda}\,\beta_\lambda(\lambda).
$$

This is why the first nonzero beta-function coefficient of a single marginal coupling is often scheme independent, while higher coefficients can depend on the scheme. In theories with several couplings, masses, thresholds, gauge parameters, and operator mixing, scheme transformations become matrix-valued bookkeeping rather than a one-line redefinition.

A scheme change is not a change of physics. It is a change of coordinates. The danger is mixing coordinates: using an MS coupling in one part of a calculation and an on-shell coupling in another without converting between them.

## Why MS is useful

Minimal subtraction is popular because it is efficient, local, and symmetry-friendly.

It is efficient because one does not need to evaluate every finite part to determine counterterms and RG functions. Pole coefficients are enough.

It is local because the subtracted pieces are exactly the local UV singularities that counterterm Lagrangians are built to absorb.

It is symmetry-friendly because dimensional regularization preserves Lorentz covariance and momentum-shift invariance, and it is usually compatible with gauge identities when chiral and evanescent subtleties are handled correctly.

The price is that MS parameters are abstract. A mass $m(\mu)$ in $\overline{\mathrm{MS}}$ is generally not the pole mass. A coupling $g(\mu)$ is generally not an immediately measured charge. To compare to experiment, one computes a physical observable in the same scheme and solves for the MS parameters, or matches between schemes.

## Common pitfalls

**Thinking MS means “throw away all infinities.”** Minimal subtraction removes ultraviolet pole parts from renormalized quantities using local counterterms. It does not license arbitrary deletion of divergent or inconvenient terms.

**Confusing MS and $\overline{\mathrm{MS}}$.** The difference is finite, but finite differences matter when comparing published formulas. Check whether the scale is $\mu$, $\overline\mu$, or another convention.

**Treating MS parameters as direct observables.** A $\overline{\mathrm{MS}}$ mass or coupling is a scheme-dependent running parameter. It must be related to observables by a calculation.

**Forgetting heavy-threshold matching.** In a mass-independent scheme, heavy fields do not automatically disappear from beta functions at low scales. Effective theories implement decoupling through matching.

**Subtracting infrared poles as if they were ultraviolet counterterms.** Dimensional regularization regulates both UV and IR singularities. Minimal subtraction in a renormalization scheme subtracts UV poles. Infrared poles cancel only in appropriate inclusive observables or factorize into physical long-distance objects.

**Assuming finite parts are unimportant.** Finite parts are where many physical logarithms, thresholds, and scheme conversions live. MS makes counterterms simple; it does not make finite physics optional.

## Relations to other pages

- [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) explains where $1/\epsilon$ and $1/\overline\epsilon$ come from.
- [Counterterm Lagrangian](/perturbative-qft/renormalized-perturbation-theory/counterterm-lagrangian/) explains how pole subtractions appear as local vertices.
- [Renormalization Conditions](/perturbative-qft/renormalized-perturbation-theory/renormalization-conditions/) compares physical subtraction conditions with scheme definitions.
- [On-Shell Scheme](/perturbative-qft/renormalized-perturbation-theory/on-shell-scheme/) contrasts MS with a physical pole-and-residue scheme.
- [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/) explains the field-strength counterterm and anomalous dimension.
- [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/) derives the scalar one-loop coupling counterterm used above.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how counterterms enter diagrams at fixed loop order.

## Research status

- **Established:** MS and $\overline{\mathrm{MS}}$ are standard perturbative schemes. Their definitions, relation to dimensional regularization, and use in beta-function calculations are textbook material.
- **Active:** Precision applications require careful scheme conversion, threshold matching, evanescent-operator treatments, chiral prescriptions, unstable-particle schemes, and separation of UV and IR pole structures.
- **Speculative:** The scheme itself is not speculative. What can be subtle is interpreting MS parameters in theories where the perturbative degrees of freedom are not physical asymptotic states.

## Exercises

### Exercise 1: MS and MS-bar finite parts

Suppose a one-loop integral gives

$$
F(\epsilon)
=
\frac{1}{16\pi^2}
\left[
\frac{1}{\epsilon}-\gamma_E+
\ln4\pi-
\ln\frac{\Delta}{\mu^2}
\right]
+O(\epsilon).
$$

Find the finite remainder in pure MS and in $\overline{\mathrm{MS}}$.

<details>
<summary><strong>Solution</strong></summary>

Pure MS subtracts only

$$
\frac{1}{16\pi^2}\frac{1}{\epsilon}.
$$

Therefore

$$
F_{\rm MS}
=
\frac{1}{16\pi^2}
\left[
-
\gamma_E+
\ln4\pi-
\ln\frac{\Delta}{\mu^2}
\right].
$$

The $\overline{\mathrm{MS}}$ scheme subtracts

$$
\frac{1}{16\pi^2}\frac{1}{\overline\epsilon}
=
\frac{1}{16\pi^2}
\left(\frac{1}{\epsilon}-\gamma_E+
\ln4\pi\right),
$$

so

$$
F_{\overline{\mathrm{MS}}}
=
-
\frac{1}{16\pi^2}
\ln\frac{\Delta}{\mu^2}.
$$

</details>

### Exercise 2: The φ⁴ MS-bar counterterm

Using

$$
\mathcal V^{(1)}_{4,\rm div}
=
 i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}
$$

and the counterterm vertex $\mathcal V_{4,\rm ct}=-i\delta\lambda$, find $\delta\lambda_{\overline{\mathrm{MS}}}$.

<details>
<summary><strong>Solution</strong></summary>

The pole cancellation condition is

$$
-i\delta\lambda
+
i\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}=0.
$$

Thus

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\overline\epsilon}.
$$

</details>

### Exercise 3: One-loop beta function from a pole

Let

$$
\lambda_0
=
\mu^{2\epsilon}
\left[\lambda+\frac{a\lambda^2}{\epsilon}+O(\lambda^3)\right].
$$

Show that

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate at fixed $\lambda_0$:

$$
0=
\mu\frac{d}{d\mu}
\left\{
\mu^{2\epsilon}\left[\lambda+\frac{a\lambda^2}{\epsilon}\right]
\right\}.
$$

Dividing by $\mu^{2\epsilon}$ gives

$$
0=
2\epsilon\left[\lambda+\frac{a\lambda^2}{\epsilon}\right]
+
\beta_\lambda^{(d)}
\left[1+\frac{2a\lambda}{\epsilon}\right]
+O(\lambda^3).
$$

Use the ansatz

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+b\lambda^2+O(\lambda^3).
$$

The term $(2a\lambda/\epsilon)\beta_\lambda^{(d)}$ contributes $-4a\lambda^2$ at this order. Therefore the coefficient of $\lambda^2$ is

$$
2a+b-4a=b-2a.
$$

Setting it to zero gives

$$
b=2a,
$$

so

$$
\beta_\lambda^{(d)}=-2\epsilon\lambda+2a\lambda^2+O(\lambda^3).
$$

</details>

### Exercise 4: Why finite terms cannot be ignored

Two schemes are related by

$$
\lambda'=\lambda+c\lambda^2+O(\lambda^3).
$$

If

$$
\beta_\lambda=b_1\lambda^2+b_2\lambda^3+O(\lambda^4),
$$

show that the coefficient $b_1$ is unchanged in the primed scheme.

<details>
<summary><strong>Solution</strong></summary>

The beta function transforms by the chain rule:

$$
\beta_{\lambda'}
=
\frac{d\lambda'}{d\lambda}\beta_\lambda.
$$

Since

$$
\frac{d\lambda'}{d\lambda}=1+2c\lambda+O(\lambda^2),
$$

we get

$$
\beta_{\lambda'}
=
(1+2c\lambda)(b_1\lambda^2+b_2\lambda^3)+O(\lambda^4).
$$

The leading term is

$$
\beta_{\lambda'}=b_1\lambda^2+O(\lambda^3).
$$

Since $\lambda'=\lambda+O(\lambda^2)$, replacing $\lambda$ by $\lambda'$ in the leading term gives

$$
\beta_{\lambda'}=b_1\lambda'^2+O(\lambda'^3).
$$

Thus the first nonzero coefficient is unchanged. Higher coefficients can change.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§14–20 and §27, for loop counterterms, one-loop amplitudes, and other renormalization schemes.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 25, for counterterm determination and the logic of regularization and renormalization.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12, and Vol. II, §18.6, for renormalization, RG methods, and minimal subtraction.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 18–23 and appendix B, for mass renormalization, counterterms, minimal subtraction, and RG equations.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 10, for dimensional regularization, minimal subtraction, and RG functions.

## Version history

- **2026-06-12:** Initial polished draft. Added MS and $\overline{\mathrm{MS}}$ definitions, pole-projection formulas, scalar $\phi^4$ one-loop counterterm example, beta-function extraction, common pitfalls, solved exercises, and a compact subtraction-flow figure.
