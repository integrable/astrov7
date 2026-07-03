---
title: "Dimensional Transmutation"
description: "Explains how RG running trades a dimensionless coupling for a physical scale, with asymptotic freedom, Landau poles, trace anomalies, and scheme dependence."
sidebar:
  label: "Dimensional Transmutation"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations and Asymptotic Freedom; Srednicki §§28–29 and gauge-theory beta-function sections; Schwartz chs. 23 and 26; Weinberg Vol. II ch. 18; Wilson and Kogut 1974; Zinn-Justin 2021."
topics:
  - dimensional transmutation
  - RG-invariant scales
  - asymptotic freedom
  - Landau poles
  - scale anomaly
  - Lambda QCD
canonicalTopics:
  - dimensional-transmutation
  - rg-invariant-scale
  - lambda-parameter
  - asymptotic-freedom
  - scale-anomaly
researchStatus:
  established:
    - "Dimensional transmutation is the standard RG mechanism by which a classically dimensionless coupling can be traded for a dynamically generated dimensionful scale."
  active:
    - "The precise nonperturbative relation between RG-invariant scales and physical masses, condensates, string tensions, or finite-density scales is theory dependent and often requires lattice, bootstrap, semiclassical, or exact methods."
---

## Summary

**Dimensional transmutation** is the RG mechanism by which a dimensionless coupling is traded for a dimensionful scale.

In a classically scale-invariant theory with one marginal coupling $g$, the RG equation

$$
\frac{dg}{d\log\mu}=\beta(g)
$$

can be integrated to define an RG-invariant scale

$$
\Lambda
=
\mu\exp\left[-\int^{g(\mu)}\frac{dg'}{\beta(g')}\right],
$$

up to a convention-dependent multiplicative constant. The arbitrary renormalization scale $\mu$ has disappeared from $\Lambda$ once the running coupling $g(\mu)$ is specified.

For an asymptotically free theory with

$$
\beta(g)=-b_0g^3+O(g^5),
\qquad b_0>0,
$$

this becomes, at leading order,

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

Thus a small dimensionless coupling at high energy secretly encodes an exponentially lower scale. In QCD-like theories this scale is the ancestor of confinement scales, hadron masses, condensates, and string tensions, although the numerical coefficients relating these observables to $\Lambda$ are nonperturbative.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Dimensional transmutation map showing a dimensionless coupling at a reference scale running into an RG-invariant scale Lambda](/figures/renormalization-rg-eft/dimensional-transmutation-scale.svg)

<figcaption>

Dimensional transmutation trades the boundary datum $g(\mu_0)$ for an RG-invariant scale $\Lambda$. In an asymptotically free theory, $g(\mu)$ is small at high energy and grows toward the infrared; the scale $\Lambda$ marks where the perturbative running coupling becomes order one, not where the one-loop formula should be trusted quantitatively.

</figcaption>
</figure>

The phenomenon is not magic and not numerology. One measured dimensionless coupling at one scale is equivalent, through RG flow, to one measured dimensionful scale. The word transmutation means that the parameter used to label the theory has changed its form.

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

For examples, it is useful to know the one-loop signs of QED and Yang–Mills beta functions from [Conventions and Notation](/renormalization-rg-eft/conventions/) and the general logic of [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/).

## Core idea

A classical four-dimensional Yang–Mills theory without masses has a dimensionless coupling and no intrinsic length scale. The classical action is schematically

$$
S=-\frac{1}{4g^2}\int d^4x\,F^a_{\mu\nu}F^{a\mu\nu}.
$$

There is no mass parameter in this formula. Classically, rescaling all lengths changes no dimensionful input because there is none.

Quantum mechanically, the renormalized coupling depends on the scale at which it is defined:

$$
g=g(\mu).
$$

If the coupling runs, then specifying $g$ at one scale is equivalent to specifying the scale where the running reaches some reference value. That reference scale is $\Lambda$.

A slogan that is actually useful is

$$
\text{one dimensionless boundary condition} \quad\longleftrightarrow\quad \text{one dimensionful RG-invariant scale}.
$$

In an asymptotically free theory, the dimensionless coupling becomes small as $\mu\to\infty$. The theory looks nearly scale invariant at short distances. Yet the RG trajectory remembers a scale $\Lambda$, and dimensionful infrared observables can be proportional to it.

## Setup and conventions

Let $g(\mu)$ be a dimensionless coupling satisfying

$$
\frac{dg}{d\log\mu}=\beta(g).
$$

Assume for the moment that there are no masses or other dimensionful couplings. The RG trajectory is determined by one integration constant. To find it, separate variables:

$$
d\log\mu=\frac{dg}{\beta(g)}.
$$

Integrating gives

$$
\log\mu-\int^g\frac{dg'}{\beta(g')}=\text{constant}.
$$

Exponentiating, one defines an RG-invariant scale

$$
\Lambda
=
\mu\exp\left[-\int^{g(\mu)}\frac{dg'}{\beta(g')}\right].
$$

The lower limit of the integral is a convention. Changing it multiplies $\Lambda$ by a constant. That constant is part of the definition of the scheme-dependent Lambda parameter.

The invariant statement is not the numerical value of $\Lambda$ by itself. It is the relation among physical quantities after the same convention is used consistently.

:::note[The scale $\mu$ is arbitrary; the scale $\Lambda$ is not]
The renormalization scale $\mu$ is a bookkeeping scale. The combination $\Lambda$ is independent of $\mu$ along an RG trajectory. Its normalization depends on the scheme, but once the scheme is fixed, $\Lambda$ is a real label of the trajectory.
:::

## One-loop asymptotic freedom

Suppose

$$
\beta(g)=-b_0g^3,
\qquad b_0>0.
$$

Then

$$
\frac{dg}{d\log\mu}=-b_0g^3.
$$

Separating variables,

$$
\int\frac{dg}{g^3}=-b_0\int d\log\mu.
$$

Since

$$
\int\frac{dg}{g^3}=-\frac{1}{2g^2},
$$

we obtain

$$
\frac{1}{2g^2(\mu)}=b_0\log\frac{\mu}{\Lambda}.
$$

Equivalently,

$$
g^2(\mu)=\frac{1}{2b_0\log(\mu/\Lambda)}.
$$

Solving for $\Lambda$ gives

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

This formula contains the characteristic exponential hierarchy. If $g(\mu)$ is moderately small, the scale $\Lambda$ can be exponentially smaller than $\mu$.

That is why asymptotic freedom is so powerful: a weakly coupled ultraviolet description can generate a strong infrared scale without inserting a small mass by hand.

## Higher-loop Lambda parameters

At two loops, write

$$
\beta(g)=-b_0g^3-b_1g^5+O(g^7).
$$

The RG-invariant scale can be written asymptotically as

$$
\Lambda
=
\mu\,
\exp\left[-\frac{1}{2b_0g^2(\mu)}\right]
\left(b_0g^2(\mu)\right)^{-b_1/(2b_0^2)}
\left[1+O(g^2(\mu))\right].
$$

The leading exponential is universal under ordinary coupling redefinitions. The power prefactor uses the two-loop coefficient. The bracketed terms depend on higher beta-function coefficients and therefore on scheme choices.

Different schemes define different Lambda parameters:

$$
\Lambda_{\overline{\mathrm{MS}}},
\qquad
\Lambda_{\mathrm{MOM}},
\qquad
\Lambda_{\mathrm{lattice}},
\qquad
\ldots
$$

They differ by finite multiplicative constants when they describe the same RG trajectory:

$$
\Lambda'=C\Lambda.
$$

The constant $C$ is calculable if the finite scheme conversion is known. Physical dimensionless ratios are independent of this convention.

## What is being transmuted?

The input data of a massless one-coupling theory can be labeled in two equivalent ways:

$$
\text{choose }g(\mu_0)
\qquad\Longleftrightarrow\qquad
\text{choose }\Lambda.
$$

The left side uses a dimensionless coupling at an arbitrary reference scale. The right side uses an RG-invariant dimensionful scale. The theory did not gain an additional parameter. It changed coordinates on its parameter space.

This is why dimensional transmutation is sometimes summarized as "a dimensionless coupling becomes a scale." That phrase is fine as a mnemonic, but it can mislead. The coupling does not literally turn into a particle mass. Rather, the integration constant of the RG flow can be represented either by a dimensionless number at a chosen scale or by a scale at which the running has a chosen reference behavior.

If the theory has no other dimensionful parameters, any physical mass $M$ must take the form

$$
M=c_M\Lambda,
$$

where $c_M$ is a pure number. Likewise a string tension would scale as

$$
\sigma=c_\sigma\Lambda^2,
$$

and a condensate of an operator of dimension $\Delta$ would scale as

$$
\langle\mathcal O\rangle=c_\mathcal O\Lambda^\Delta.
$$

The constants $c_M$, $c_\sigma$, and $c_\mathcal O$ are generally nonperturbative. The RG tells us the scaling form, not the full spectrum.

## QCD as the canonical example

For an $SU(N_c)$ gauge theory with $N_f$ Dirac fermions in the fundamental representation, the one-loop gauge coupling beta function is

$$
\beta_g
=-\frac{g^3}{16\pi^2}
\left(\frac{11}{3}N_c-\frac{2}{3}N_f\right)+O(g^5).
$$

When

$$
N_f<\frac{11}{2}N_c,
$$

the coefficient is negative and the theory is asymptotically free. Defining

$$
b_0=\frac{11N_c-2N_f}{48\pi^2},
$$

the leading Lambda parameter is

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

In real QCD, quark masses are also present, so the theory is not a pure one-parameter massless theory. Nevertheless, $\Lambda_{\mathrm{QCD}}$ captures the central fact that the strong interaction can be weak at high energy and strong at hadronic scales.

Perturbation theory can show how $g_s(\mu)$ runs at high scales and how a scale parameter is defined. It cannot by itself compute the proton mass, the string tension, or the confinement spectrum from first principles. Those require nonperturbative methods such as lattice gauge theory, effective theories, large-N reasoning, or other strong-coupling tools.

## Landau scales

Dimensional transmutation is not only an asymptotic-freedom story. If

$$
\beta(g)=+b_0g^3,
\qquad b_0>0,
$$

then the one-loop solution is

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}-2b_0\log\frac{\mu}{\mu_0}.
$$

The coupling grows toward the ultraviolet and formally diverges at

$$
\Lambda_L
=
\mu_0\exp\left[\frac{1}{2b_0g^2(\mu_0)}\right].
$$

This is a **Landau scale**. It is also an RG-invariant scale, but its interpretation is different. In QED-like perturbation theory, the formal Landau pole suggests that the theory cannot be a complete weakly coupled continuum theory to arbitrarily high energies without new physics, a fixed point, or some other modification.

So dimensional transmutation can produce either:

| Beta-function sign | Running behavior | Emergent scale |
|---|---|---|
| $\beta(g)=-b_0g^3$ | weak in UV, strong in IR | infrared strong scale $\Lambda$ |
| $\beta(g)=+b_0g^3$ | weak in IR, strong in UV | ultraviolet Landau scale $\Lambda_L$ |

The same mathematics describes both. The physics is very different.

## Trace anomaly and scale breaking

Classically scale-invariant theories often have a stress-tensor trace that vanishes after improvement:

$$
T^\mu{}_{\mu}=0.
$$

Quantum mechanically, running couplings produce a trace anomaly. Schematically, for couplings multiplying local operators,

$$
T^\mu{}_{\mu}
=\sum_i\beta^i(g)\mathcal O_i
+\text{mass terms}
+\text{contact and curvature terms}.
$$

For a gauge theory written with the kinetic term

$$
\mathcal L=-\frac{1}{4g^2}F^a_{\mu\nu}F^{a\mu\nu},
$$

one commonly writes the flat-space gauge contribution schematically as

$$
T^\mu{}_{\mu}
=\frac{\beta(g)}{2g^3}F^a_{\mu\nu}F^{a\mu\nu}+\cdots,
$$

with the precise sign and normalization tied to the convention for placing $g$ in the gauge kinetic term.

The important point is independent of notation: if the beta function is nonzero, scale invariance is anomalous. The generated scale $\Lambda$ is the RG-invariant memory of that anomaly.

:::caution[Anomaly does not mean inconsistency]
The scale anomaly is not a gauge anomaly. It does not make the theory inconsistent. It says that a classical scaling symmetry fails to survive quantization because the renormalized theory requires a scale-dependent definition of its parameters.
:::

## Coleman–Weinberg mechanism

Dimensional transmutation also appears in perturbative symmetry breaking. In the Coleman–Weinberg mechanism, a classically scale-invariant theory with scalar fields can develop an effective potential whose minimum occurs at a nonzero field value,

$$
\langle\phi\rangle=v.
$$

The scale $v$ is not inserted as a mass in the classical Lagrangian. It is selected by running couplings and logarithms in the quantum effective potential.

A schematic RG-improved effective potential has the form

$$
V_{\text{eff}}(\phi)
=\frac{1}{4}\lambda(\mu)\phi^4+\text{loop corrections involving }\log\frac{\phi}{\mu}.
$$

Choosing $\mu\sim\phi$ and running the couplings turns the minimization problem into a statement about the scale where the couplings satisfy a particular relation. Again, a dimensionless boundary condition has become a dimensionful scale.

This mechanism is more delicate than the asymptotically free example because scalar potentials must be stable and radiative corrections must be controlled. The concept is the same; the model-building constraints are more severe.

## Scheme dependence of Lambda

Because $\Lambda$ is defined using a coupling coordinate, its numerical normalization is scheme dependent.

Let a one-loop asymptotically free coupling be redefined by

$$
g'=g+a g^3+O(g^5).
$$

At small coupling,

$$
\frac{1}{g^2}=\frac{1}{g'^2}+2a+O(g'^2).
$$

Using the one-loop expression

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2}\right],
$$

we find

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g'^2}\right]
\exp\left[-\frac{a}{b_0}\right]
\left[1+O(g'^2)\right].
$$

Thus the primed convention's Lambda parameter differs by a constant:

$$
\Lambda'=e^{a/b_0}\Lambda.
$$

This does not make dimensional transmutation unphysical. It says that $\Lambda$ is a scheme-labeled reference scale, like $\Lambda_{\overline{\mathrm{MS}}}$. Once the scheme is fixed, physical quantities can be quoted in terms of it; when schemes change, the conversion factor must change too.

## Relation to dimensional regularization

Dimensional regularization introduces a scale $\mu$ so that couplings remain dimensionless away from four dimensions. This sometimes makes dimensional transmutation sound like a trick caused by the regulator. That is not right.

The scale $\mu$ is arbitrary. It appears because we need a convention for defining renormalized couplings. The RG-invariant scale $\Lambda$ is built from $\mu$ and $g(\mu)$ in such a way that the arbitrary choice cancels:

$$
\mu\frac{d\Lambda}{d\mu}=0.
$$

A hard cutoff, lattice regulator, momentum-subtraction scheme, or dimensional-regularization scheme can all describe the same phenomenon. They may define different numerical Lambda parameters, but the emergence of a physical scale from RG running is not an artifact of dimensional regularization.

## Common pitfalls

**Thinking that $\mu$ is the generated scale.** The scale $\mu$ is arbitrary. The generated RG-invariant scale is $\Lambda$, constructed from $\mu$ and the running coupling.

**Thinking that dimensional transmutation adds a new parameter.** It does not. It trades the coupling value $g(\mu_0)$ for an equivalent scale $\Lambda$.

**Trusting the one-loop formula at $\mu\sim\Lambda$.** The one-loop formula identifies the scale where perturbation theory becomes unreliable. It does not accurately describe the strongly coupled region.

**Treating $\Lambda$ as scheme independent.** Its normalization depends on the scheme. Physical ratios computed consistently do not.

**Confusing a Landau pole with a particle threshold.** A Landau pole is a scale where a perturbative running coupling formally diverges. It is not automatically a physical particle mass.

**Assuming every generated scale implies confinement.** Dimensional transmutation creates a scale. What the theory does at that scale depends on dynamics: confinement, chiral symmetry breaking, conformality, mass generation, or breakdown of the effective description are different possibilities.

## Relations to other pages

[Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) derives the running-coupling solutions used here. [Asymptotic Freedom](/renormalization-rg-eft/renormalization-group-equations/asymptotic-freedom/) will develop the ultraviolet-weak case in gauge theories. [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/) will focus on the ultraviolet-strong case.

[Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/) explains why different Lambda parameters differ by finite constants. [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/) explains how the same RG equations resum large logarithms.

Later, [QCD Running Coupling](/renormalization-rg-eft/gauge-theories-and-rg/qcd-running-coupling/) and [Confinement Scale and Dimensional Transmutation](/renormalization-rg-eft/gauge-theories-and-rg/confinement-scale-and-dimensional-transmutation/) will apply this logic to non-Abelian gauge theory in more detail. [Wilson–Fisher Fixed Point](/renormalization-rg-eft/fixed-points-critical-phenomena/wilson-fisher-fixed-point/) gives a different RG story: instead of generating a mass scale from asymptotic freedom, the RG flow approaches a scale-invariant fixed point.

## Research status

The perturbative RG mechanism of dimensional transmutation is established and central to modern QFT. Its canonical examples include asymptotically free gauge theories, Coleman–Weinberg symmetry breaking, and Landau-scale diagnostics of theories with positive beta functions.

The hard questions begin after the scale is generated. In QCD-like theories, relating $\Lambda$ quantitatively to the hadron spectrum, string tension, condensates, topology, and finite-temperature scales is nonperturbative. In beyond-Standard-Model and condensed-matter settings, dimensional transmutation can create hierarchies, but stability, naturalness, vacuum structure, and strong dynamics must be analyzed model by model.

## Exercises

### Exercise 1: Derive the asymptotically free Lambda scale

Assume

$$
\frac{dg}{d\log\mu}=-b_0g^3,
\qquad b_0>0.
$$

Derive

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^3}=-b_0d\log\mu.
$$

Integrate:

$$
-\frac{1}{2g^2}=-b_0\log\mu+C.
$$

Rearrange the integration constant by writing

$$
\frac{1}{2g^2(\mu)}=b_0\log\frac{\mu}{\Lambda}.
$$

Then

$$
\log\frac{\mu}{\Lambda}=\frac{1}{2b_0g^2(\mu)},
$$

so

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2(\mu)}\right].
$$

</details>

### Exercise 2: Show that Lambda is RG invariant

Using the one-loop asymptotically free beta function, verify directly that

$$
\mu\frac{d}{d\mu}\left[\mu\exp\left(-\frac{1}{2b_0g^2(\mu)}\right)\right]=0.
$$

<details><summary><strong>Solution</strong></summary>

Let

$$
\Lambda=\mu\exp\left(-\frac{1}{2b_0g^2}\right).
$$

Take a logarithm:

$$
\log\Lambda=\log\mu-\frac{1}{2b_0g^2}.
$$

Differentiate with respect to $\log\mu$:

$$
\frac{d\log\Lambda}{d\log\mu}
=1-\frac{1}{2b_0}\frac{d(g^{-2})}{d\log\mu}.
$$

Since

$$
\frac{d(g^{-2})}{d\log\mu}
=-2g^{-3}\frac{dg}{d\log\mu}
=-2g^{-3}(-b_0g^3)=2b_0,
$$

we obtain

$$
\frac{d\log\Lambda}{d\log\mu}=1-1=0.
$$

Thus $\Lambda$ is RG invariant at this order.

</details>

### Exercise 3: Landau scale

Assume

$$
\frac{dg}{d\log\mu}=+b_0g^3,
\qquad b_0>0.
$$

Given $g(\mu_0)$, find the scale where the one-loop running coupling formally diverges.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^3}=b_0d\log\mu.
$$

Integrating between $\mu_0$ and $\mu$ gives

$$
-\frac{1}{2g^2(\mu)}+\frac{1}{2g^2(\mu_0)}=b_0\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
\frac{1}{g^2(\mu)}
=
\frac{1}{g^2(\mu_0)}-2b_0\log\frac{\mu}{\mu_0}.
$$

The coupling diverges when the right-hand side vanishes:

$$
0=\frac{1}{g^2(\mu_0)}-2b_0\log\frac{\Lambda_L}{\mu_0}.
$$

Thus

$$
\Lambda_L
=\mu_0\exp\left[\frac{1}{2b_0g^2(\mu_0)}\right].
$$

</details>

### Exercise 4: Scheme rescaling of Lambda

Let an asymptotically free coupling be redefined by

$$
g'=g+a g^3+O(g^5).
$$

Using the one-loop Lambda formula, show that the Lambda parameters in the two schemes differ by a multiplicative constant.

<details><summary><strong>Solution</strong></summary>

Invert the finite redefinition at small coupling:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2a g'^4+O(g'^6),
$$

and hence

$$
\frac{1}{g^2}=\frac{1}{g'^2}+2a+O(g'^2).
$$

The unprimed Lambda parameter is

$$
\Lambda=\mu\exp\left[-\frac{1}{2b_0g^2}\right].
$$

Substituting gives

$$
\Lambda
=
\mu\exp\left[-\frac{1}{2b_0g'^2}\right]
\exp\left[-\frac{a}{b_0}\right]
\left[1+O(g'^2)\right].
$$

If the primed scheme defines

$$
\Lambda'=\mu\exp\left[-\frac{1}{2b_0g'^2}\right]
$$

at this order, then

$$
\Lambda'=e^{a/b_0}\Lambda.
$$

The scale normalization is scheme dependent, but only by a constant conversion factor.

</details>

## References

- Sidney Coleman, "Dilatations" and "Asymptotic Freedom" in *Aspects of Symmetry*, for scale anomalies, RG equations, and the physical meaning of asymptotic freedom.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on the renormalization group, effective field theory, and gauge-theory beta functions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on the renormalization group, Yang–Mills running, and nonrenormalizable theories.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, asymptotic behavior, fixed points, and minimal subtraction.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for the modern scale-based RG viewpoint.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for dimensional transmutation, RG equations, critical phenomena, and the relation between particle-physics and statistical-field-theory uses of RG.

## Version history

- 2026-06-17: First polished draft. Added one-loop and higher-loop Lambda parameters, QCD and Landau-scale examples, trace-anomaly interpretation, scheme-dependence of Lambda parameters, Coleman–Weinberg comments, and exercises with solutions.
