---
title: "Phi-Four One-Loop Renormalization"
description: "A complete one-loop renormalization benchmark in real scalar phi-four theory: tadpoles, four-point bubbles, local counterterms, and MS-bar renormalized Green functions."
sidebar:
  label: "Phi-Four One-Loop Renormalization"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–18 and 27–29; Coleman 2019, chs. 15–16; Schwartz 2014, chs. 18–23; Zinn-Justin 2021, chs. 10–13."
topics:
  - phi-four theory
  - one-loop renormalization
  - counterterms
  - dimensional regularization
  - MS-bar scheme
  - one-particle-irreducible functions
canonicalTopics:
  - phi-four-one-loop-renormalization
  - scalar-field-renormalization
  - one-loop-counterterms
researchStatus:
  established:
    - "One-loop renormalization of real scalar phi-four theory is a standard benchmark calculation in perturbative QFT and critical phenomena."
  active:
    - "Higher-loop coefficients, resummation, nonperturbative definitions, and precision critical exponents belong to later calculation and critical-phenomena pages."
---

## Summary

Real scalar $\phi^4$ theory is the cleanest laboratory for perturbative renormalization. It has one field, one quartic interaction, no spin, no gauge redundancy, and no infrared subtleties when $m^2>0$. Yet at one loop it already shows the whole local-counterterm mechanism:

$$
\text{loop UV sensitivity}
\quad\longrightarrow\quad
\text{local }\phi^2\text{ and }\phi^4\text{ counterterms}
\quad\longrightarrow\quad
\text{finite renormalized Green functions}.
$$

We study the theory

$$
\mathcal L_{\text{ren}}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

using dimensional regularization with

$$
d=4-2\epsilon,
\qquad
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log4\pi.
$$

At one loop in $\overline{\mathrm{MS}}$ the required local counterterms are

$$
\delta Z=0+O(\lambda^2),
\qquad
\delta m^2=
\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^2),
\qquad
\delta\lambda=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^3),
$$

with the convention that the counterterm Lagrangian is

$$
\mathcal L_{\text{ct}}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

The result says something more important than "infinities cancel." It says that the short-distance part of the one-loop two-point and four-point functions has the same local form as terms already allowed in the Lagrangian.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![One-loop phi-four renormalization map showing tadpole and bubble divergences becoming local mass and coupling counterterms](/figures/renormalization-rg-eft/phi-four-one-loop-renormalization-map.svg)

<figcaption>

At one loop, real $\phi^4$ theory has a divergent two-point tadpole and divergent four-point bubble diagrams in the $s$, $t$, and $u$ channels. Their ultraviolet parts are polynomial in the external momenta at this order, so they are canceled by local counterterms $\delta m^2\phi^2$ and $\delta\lambda\phi^4$. There is no one-loop wavefunction counterterm because the one-loop two-point divergence is momentum-independent.

</figcaption>
</figure>

:::note[What is being calculated]
This page computes the one-loop UV-divergent parts of the renormalized one-particle-irreducible two-point and four-point functions. The next page extracts the beta function from the same coupling counterterm.
:::

## Prerequisites

You should know [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), and [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/). The loop integrals used here are the standard one-loop tadpole and bubble integrals; the point of this page is not integral technology but renormalization bookkeeping.

We use the volume conventions:

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare fixed}},
\qquad
 d=4-2\epsilon.
$$

Because the divergent parts are local and insensitive to thresholds, we often write the loop integrals after Wick rotation in Euclidean form. When comparing signs with another source, first check whether the source quotes the self-energy, the 1PI vertex, the effective action, or the counterterm Lagrangian. These differ by conventional factors of $i$ and minus signs.

## Setup: the renormalized Lagrangian

The bare Lagrangian is written as a renormalized Lagrangian plus counterterms:

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}.
$$

For one real scalar field,

$$
\mathcal L_{\text{ren}}
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

The factor $\mu^{2\epsilon}$ keeps $\lambda$ dimensionless in $d=4-2\epsilon$. The same convention was used in the volume conventions page. If one instead writes $d=4-\tilde\epsilon$, every pole coefficient involving $\epsilon$ is translated by $\tilde\epsilon=2\epsilon$.

The corresponding bare-field notation is

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=m^2+\delta m^2+\cdots,
\qquad
\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda+\cdots),
$$

where the ellipses remind us that different authors distribute counterterms between $Z$ factors in slightly different ways. At this order, the unambiguous content is the local counterterm vertices displayed above.

## Feynman rules and symmetry factors

The renormalized propagator is

$$
\frac{i}{p^2-m^2+i0},
$$

and the renormalized four-point vertex is

$$
-i\mu^{2\epsilon}\lambda.
$$

The counterterm vertices are

$$
i\delta Z\,p^2-i\delta m^2
$$

for the two-point insertion, and

$$
-i\mu^{2\epsilon}\delta\lambda
$$

for the four-point insertion.

The one-loop diagrams we need are:

| Object | Diagram | Symmetry factor | Counterterm needed |
|---|---|---:|---|
| 1PI two-point function | tadpole | $1/2$ | $\delta m^2$ |
| 1PI two-point function | momentum-dependent self-energy | none at one loop | no $\delta Z$ at one loop |
| 1PI four-point function | bubble in $s,t,u$ channels | $1/2$ per channel | $\delta\lambda$ |

The factor $1/2$ in the tadpole and bubble diagrams is the usual identical-line symmetry factor. The four-point correction has three channels because a real scalar with a $\phi^4$ interaction does not distinguish the $s$, $t$, and $u$ pairings.

## The two-point function

The one-loop tadpole correction to the two-point 1PI function is momentum-independent. In Euclidean notation, the basic integral is

$$
I_1(m^2)
=
\mu^{2\epsilon}
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{\ell_E^2+m^2}.
$$

Using the dimensional-regularization master formula,

$$
\mu^{2\epsilon}
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+\Delta)^\alpha}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
\Delta^{d/2-\alpha},
$$

with $\alpha=1$ and $d=4-2\epsilon$, we obtain

$$
I_1(m^2)
=
\frac{m^2}{16\pi^2}
\left[-\frac{1}{\bar\epsilon}
+\log\frac{m^2}{\mu^2}-1+O(\epsilon)\right].
$$

The sign of this Euclidean integral is sometimes surprising the first time one sees it. Dimensional regularization is analytic continuation, not a positive cutoff integral. A hard cutoff tadpole is positive and quadratically divergent; dimensional regularization hides the power divergence and displays the logarithmic short-distance part as a pole.

The one-loop two-point contribution has the structure

$$
\Gamma^{(2)}_{\text{1-loop}}(p^2)
\supset
\frac{\lambda}{2}I_1(m^2),
$$

up to the overall sign convention used for the Euclidean or Lorentzian 1PI vertex. The divergent local part is therefore proportional to

$$
\frac{\lambda}{2}I_1(m^2)\Big|_{\text{pole}}
=
-\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}.
$$

The counterterm is chosen with the opposite sign in the renormalized two-point vertex. With the counterterm convention stated in the summary, this gives

$$
\delta m^2
=
\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}
+O(\lambda^2).
$$

At this loop order the tadpole has no dependence on the external momentum $p$. Therefore no divergent contribution proportional to $p^2$ appears, and

$$
\delta Z=0+O(\lambda^2).
$$

This is a useful first check. A local momentum-independent self-energy can renormalize the mass but not the kinetic term.

:::tip[Why no wavefunction renormalization yet?]
Wavefunction renormalization requires a divergent term proportional to $p^2\phi^2$, or equivalently a divergent $p^2$ dependence in the two-point 1PI function. The one-loop $\phi^4$ tadpole has no external momentum running through the loop. The first divergent wavefunction renormalization in this theory appears at two loops.
:::

## The four-point function

The one-loop four-point function receives bubble contributions in the $s$, $t$, and $u$ channels. For the $s$ channel, define

$$
s=(p_1+p_2)^2,
$$

with all external momenta treated consistently according to the page convention. The scalar bubble integral can be written after Feynman parametrization as

$$
I_2(s)
=
\mu^{2\epsilon}
\int_0^1 dx
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{\left[\ell_E^2+\Delta_s(x)\right]^2},
$$

where, after continuation to Euclidean form,

$$
\Delta_s(x)=m^2+x(1-x)(-s-i0)
$$

in a Lorentzian scattering convention. The ultraviolet pole is independent of the external momentum and of the mass:

$$
I_2(s)\Big|_{\text{pole}}
=
\frac{1}{16\pi^2}\frac{1}{\bar\epsilon}.
$$

Each channel carries a symmetry factor $1/2$. Therefore the divergent part of the one-loop four-point 1PI function has the form

$$
\Gamma^{(4)}_{\text{1-loop}}\Big|_{\text{pole}}
\propto
3\times \frac{\lambda^2}{2}\frac{1}{16\pi^2}\frac{1}{\bar\epsilon}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon},
$$

again up to the overall sign convention for the 1PI vertex. The local counterterm that cancels this divergence is

$$
\delta\lambda
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}
+O(\lambda^3)
$$

in the counterterm-Lagrangian convention used on this page.

The important structural fact is that the ultraviolet part is independent of $s$, $t$, and $u$. It is local. The finite part contains logarithms such as

$$
\log\frac{m^2+x(1-x)(-s-i0)}{\mu^2},
$$

which are not local polynomials in the external momenta. Those finite nonlocal pieces are not canceled by counterterms; they are part of the renormalized momentum dependence of the four-point function.

## The one-loop renormalized 1PI functions

Putting the pieces together, the renormalized two-point 1PI function has the schematic form

$$
\Gamma_R^{(2)}(p^2)
=
 p^2-m^2
+\Gamma^{(2)}_{\text{1-loop, finite}}(p^2;m^2,\lambda,\mu)
+O(\lambda^2),
$$

where the one-loop finite part is momentum-independent in $\phi^4$ theory. In an MS-like scheme, the renormalized mass is not automatically the physical pole mass. It is a scheme-dependent coordinate. To obtain the physical pole, one solves

$$
\Gamma_R^{(2)}(p^2=m_{\text{pole}}^2)=0
$$

with the appropriate Lorentzian continuation.

Similarly, the renormalized four-point 1PI function has the schematic form

$$
\Gamma_R^{(4)}(s,t,u)
=
-\lambda
+\Gamma^{(4)}_{\text{1-loop, finite}}(s,t,u;m^2,\lambda,\mu)
+O(\lambda^3),
$$

where the finite one-loop part contains the three channel functions. In a minimal-subtraction scheme, $\lambda(\mu)$ is defined by the subtraction rule, not by setting $\Gamma_R^{(4)}$ equal to a measured value at a fixed external momentum. A momentum-subtraction scheme would instead choose a reference kinematic point and absorb a different finite part into the coupling.

## Counterterms in compact form

The one-loop $\overline{\mathrm{MS}}$ counterterm Lagrangian is

$$
\mathcal L_{\text{ct}}^{(1)}
=
-
\frac12
\left(
\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}
\right)\phi^2
-
\frac{\mu^{2\epsilon}}{4!}
\left(
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}
\right)\phi^4
+O(\lambda^2\phi^2,\lambda^3\phi^4).
$$

There is no one-loop kinetic counterterm:

$$
\mathcal L_{\text{ct}}^{(1)}\not\supset \frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi.
$$

In bare-parameter language, this is equivalently summarized as

$$
\phi_0=\phi+O(\lambda^2),
$$

$$
m_0^2
=
 m^2
+
\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}
+O(\lambda^2),
$$

and

$$
\lambda_0
=
\mu^{2\epsilon}
\left[
\lambda
+
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}
+O(\lambda^3)
\right],
$$

if one defines $\lambda_0$ as the coefficient that appears in the bare interaction and records the counterterm coefficient with the same sign as in the bare action. Some RG derivations instead write the pole in $\lambda_0$ with the opposite sign by absorbing the counterterm into the definition of the renormalized 1PI vertex. The next page states the beta-function derivation in a sign-explicit way so that no physics depends on this bookkeeping choice.

## Locality check

The entire calculation can be audited by asking what the divergent part looks like as a function of external momenta.

For the tadpole,

$$
\Gamma^{(2)}_{\text{div}}(p^2)=A m^2,
$$

where $A$ is a divergent constant. This has the same form as the local operator $\phi^2$.

For the one-loop four-point function,

$$
\Gamma^{(4)}_{\text{div}}(s,t,u)=B\lambda^2,
$$

where $B$ is a divergent constant. This has the same form as the local operator $\phi^4$.

There is no divergent term of the form

$$
C p^2
$$

in the two-point function at one loop, so no $(\partial\phi)^2$ counterterm is needed at this order. There is also no divergent four-point term proportional to $s+t+u$ at this order. Such momentum-dependent four-field operators are irrelevant in four dimensions and appear in the EFT tower, not as one-loop renormalizable counterterms of this calculation.

This is the practical meaning of perturbative renormalizability in the simplest model: the divergences generated by the calculation can be absorbed into the finite list of local operators already present in the renormalizable Lagrangian.

## Cutoff comparison

A hard cutoff makes the physical short-distance sensitivity more visually obvious. The tadpole behaves schematically as

$$
\int^{\Lambda}\frac{d^4\ell_E}{(2\pi)^4}\frac{1}{\ell_E^2+m^2}
\sim
\frac{\Lambda^2}{16\pi^2}
-
\frac{m^2}{16\pi^2}\log\frac{\Lambda^2}{m^2}
+\cdots.
$$

Dimensional regularization discards the power divergence in the sense that no $\Lambda^2$ appears; it records the logarithmic local sensitivity as a pole. A Wilsonian EFT interpretation should not conclude that the quadratic sensitivity is unreal. It should conclude that dimensional regularization and minimal subtraction are very efficient for extracting logarithmic running, while a cutoff is more explicit about power sensitivity to heavy thresholds.

The bubble integral behaves schematically as

$$
\int^{\Lambda}\frac{d^4\ell_E}{(2\pi)^4}
\frac{1}{(\ell_E^2+m^2)((\ell_E+p)^2+m^2)}
\sim
\frac{1}{16\pi^2}\log\frac{\Lambda^2}{m^2}+\text{finite momentum dependence}.
$$

The logarithmic divergence is exactly the one that becomes the coupling counterterm and, on the next page, the beta function.

## Common pitfalls

**Forgetting the three channels.** The coefficient $3$ in the one-loop coupling counterterm is not mysterious. It comes from the $s$, $t$, and $u$ bubble diagrams.

**Confusing $\delta m^2$ with a pole-mass shift.** The counterterm cancels regulator dependence in a chosen scheme. The physical pole mass is determined after finite parts and the chosen renormalization condition are included.

**Expecting $\delta Z$ at one loop.** The one-loop tadpole is independent of external momentum. Wavefunction renormalization in $\phi^4$ theory starts at two loops.

**Treating dimensional regularization as a cutoff.** A $1/\epsilon$ pole is not a literal $\Lambda^2$. Dimensional regularization is an analytic regulator. It is excellent for logarithms and MS beta functions, but it hides power divergences.

**Comparing coefficients across coupling normalizations.** This page uses $\lambda\phi^4/4!$. If another source writes $g\phi^4/4$, $g\phi^4$, or $u(\phi^2)^2$ for an $O(N)$ model, the numerical coefficients change.

**Overinterpreting off-shell finite parts.** Off-shell 1PI functions are useful scheme-dependent objects. Physical observables require the appropriate external-state or correlation-function interpretation.

## Relations to other pages

This page is the first worked calculation in the model library. It realizes in one place the ideas developed in [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/).

The next page, [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/), extracts the beta function from the coupling counterterm. The Wilson–Fisher page then uses the same beta function in $d<4$ to produce an interacting critical fixed point.

The same logic reappears with more structure in the Yukawa, QED, and Yang–Mills benchmark calculations. Gauge theories add Ward, Slavnov–Taylor, and BRST constraints; EFT examples add matching conditions and operator bases.

## Research status

The one-loop calculation on this page is fully standard. The active research directions are not in the existence of these one-loop poles, but in what one does beyond them: high-loop scalar critical exponents, resummation of divergent perturbative series, rigorous construction of continuum limits, conformal bootstrap comparisons, nonperturbative functional RG approximations, lattice simulations, and precision matching between schemes.

The conceptual lesson remains foundational: perturbation theory generates local ultraviolet sensitivity, and renormalization organizes that sensitivity into local parameters.

## Exercises

### Exercise 1: Tadpole pole part

Starting from

$$
I_1(m^2)
=
\mu^{2\epsilon}
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{\ell_E^2+m^2},
$$

use the master formula to show that

$$
I_1(m^2)
=
\frac{m^2}{16\pi^2}
\left[-\frac{1}{\bar\epsilon}+O(\epsilon^0)\right].
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\mu^{2\epsilon}
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+m^2)^\alpha}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{d/2}}
\frac{\Gamma(\alpha-d/2)}{\Gamma(\alpha)}
(m^2)^{d/2-\alpha}.
$$

For $\alpha=1$ and $d=4-2\epsilon$,

$$
I_1(m^2)=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(-1+\epsilon)(m^2)^{1-\epsilon}.
$$

Using

$$
\Gamma(-1+\epsilon)=-\frac{1}{\epsilon}+\gamma_E-1+O(\epsilon),
$$

and expanding the factors $\mu^{2\epsilon}(4\pi)^\epsilon(m^2)^{-\epsilon}$ gives

$$
I_1(m^2)=
\frac{m^2}{16\pi^2}
\left[-\frac{1}{\epsilon}+\gamma_E-\log4\pi+O(\epsilon^0)\right]
=
-\frac{m^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(\epsilon^0).
$$

</details>

### Exercise 2: Bubble pole part

Show that the pole part of

$$
I_2(s)=\mu^{2\epsilon}\int_0^1 dx
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{[\ell_E^2+\Delta_s(x)]^2}
$$

is independent of $s$ and equal to

$$
I_2(s)\Big|_{\text{pole}}=
\frac{1}{16\pi^2}\frac{1}{\bar\epsilon}.
$$

<details><summary><strong>Solution</strong></summary>

For $\alpha=2$ and $d=4-2\epsilon$,

$$
\mu^{2\epsilon}
\int\frac{d^d\ell_E}{(2\pi)^d}
\frac{1}{(\ell_E^2+\Delta)^2}
=
\frac{\mu^{2\epsilon}}{(4\pi)^{2-\epsilon}}
\Gamma(\epsilon)\Delta^{-\epsilon}.
$$

Expanding

$$
\Gamma(\epsilon)=\frac{1}{\epsilon}-\gamma_E+O(\epsilon),
\qquad
\mu^{2\epsilon}(4\pi)^\epsilon\Delta^{-\epsilon}
=1+O(\epsilon),
$$

we get

$$
\frac{1}{16\pi^2}
\frac{1}{\bar\epsilon}+O(\epsilon^0).
$$

The pole is independent of $\Delta$, and therefore independent of the Feynman parameter and the external invariant $s$. The $x$ integral of the pole is just one.

</details>

### Exercise 3: Counting the factor of three

Why does the one-loop four-point counterterm contain $3\lambda^2$ rather than $\lambda^2$?

<details><summary><strong>Solution</strong></summary>

There are three inequivalent ways to pair four external legs into two pairs attached to the two vertices of a bubble diagram. These are the $s$, $t$, and $u$ channels. Each bubble has the same ultraviolet pole and the same symmetry factor $1/2$. Therefore the total pole is three times the pole of a single channel:

$$
3\times \frac{\lambda^2}{2}\frac{1}{16\pi^2}\frac{1}{\bar\epsilon}
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}.
$$

This is the origin of the coefficient in $\delta\lambda$.

</details>

### Exercise 4: Why no derivative counterterm?

Explain why the one-loop tadpole cannot produce a divergent $\partial_\mu\phi\partial^\mu\phi$ counterterm.

<details><summary><strong>Solution</strong></summary>

A kinetic counterterm corresponds in momentum space to a divergent term proportional to $p^2$ in the 1PI two-point function. The one-loop $\phi^4$ two-point diagram is a tadpole. No external momentum flows through the internal loop, so the loop integral is independent of $p$. It can only generate a local term proportional to $\phi^2$, not to $\partial_\mu\phi\partial^\mu\phi$.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially sections on loop corrections, higher-order corrections, other renormalization schemes, the renormalization group, and effective field theory.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on perturbative divergences, counterterms, mass renormalization, and renormalization.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on mass renormalization, renormalized perturbation theory, renormalizability, and the renormalization group.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for scalar field theory, dimensional regularization, $\phi^4$ renormalization, and the statistical-field-theory interpretation.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the classic bridge from $\phi^4$ theory to critical phenomena and Wilsonian RG.

## Version history

- 2026-06-19: First polished draft. Added one-loop tadpole and bubble calculation, counterterm summary, locality checks, cutoff comparison, exercises, and figure.
