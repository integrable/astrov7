---
title: "φ⁴ Theory: One-Loop Four-Point Amplitude"
description: "A reproducible one-loop calculation of the four-point amplitude in real φ⁴ theory, including s-, t-, and u-channel bubbles, counterterms, and the threshold branch cut."
sidebar:
  label: "φ⁴ One-Loop Four-Point"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20; Coleman 2019, chs. 15–16 and 25; Schwartz 2014, chs. 15–19."
topics:
  - φ⁴ theory
  - one-loop amplitudes
  - dimensional regularization
  - counterterms
canonicalTopics:
  - phi-four-theory
  - one-loop-four-point-amplitude
  - coupling-renormalization
  - model-calculation-library
researchStatus:
  established:
    - "The one-loop four-point amplitude in φ⁴ theory is a textbook-standard example of how logarithmic ultraviolet divergences are absorbed into coupling renormalization."
  active:
    - "The same calculation remains a useful benchmark for scheme dependence, threshold analytic structure, finite-temperature generalizations, lattice matching, and numerical loop-integral workflows."
---

## Summary

The first loop correction to $2\to2$ scattering in real $\phi^4$ theory is the sum of three bubble diagrams and one quartic counterterm. With

$$
\mathcal L
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
+\mathcal L_{\rm ct},
$$

the one-loop four-point amplitude has the form

$$
i\mathcal M
=
-i\lambda
+\frac{(-i\lambda)^2}{2}\,[B(s)+B(t)+B(u)]
-i\delta\lambda
+O(\lambda^3),
$$

where $B(x)$ is the scalar bubble integral in the channel with invariant $x$. In dimensional regularization with $d=4-2\epsilon$,

$$
B(x)
=
-\frac{i}{16\pi^2}
\left[
\Delta_{\overline{\mathrm{MS}}}
-\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)x-i\epsilon}{\mu^2}
\right)
\right]
+O(\epsilon),
$$

with

$$
\Delta_{\overline{\mathrm{MS}}}
=\frac{1}{\epsilon}-\gamma_E+\log 4\pi.
$$

The $\overline{\mathrm{MS}}$ counterterm

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\Delta_{\overline{\mathrm{MS}}}
+O(\lambda^3)
$$

removes the one-loop divergence, leaving

$$
\mathcal M_{\overline{\mathrm{MS}}}(s,t,u)
=
-\lambda(\mu)
-\frac{\lambda(\mu)^2}{32\pi^2}
\sum_{x=s,t,u}
\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)x-i\epsilon}{\mu^2}
\right)
+O(\lambda^3).
$$

This page keeps the full mass dependence. The massless limit is useful, but it hides the physical threshold at $x=4m^2$.

## Prerequisites

You should know [φ⁴ Theory: 2→2 Scattering](/perturbative-qft/model-calculation-library/phi-four-two-to-two-scattering/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/), and [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/). The analytic interpretation uses [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) and [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/).

## Core idea

At order $\lambda^2$, two quartic vertices can be connected by two internal scalar propagators. There are three inequivalent ways to pair the external legs into a bubble channel: $s$, $t$, and $u$. Each bubble has symmetry factor $1/2$, and the quartic counterterm cancels the ultraviolet divergence common to the three channels.

<figure class="doc-figure" style="--figure-width: 43rem; --caption-width: 54rem;">

![One-loop four-point amplitude in real phi-four theory](/figures/perturbative-qft/phi-four-one-loop-four-point.svg)

<figcaption>

The one-loop four-point amplitude in real $\phi^4$ theory is the sum of $s$-, $t$-, and $u$-channel bubbles plus the local quartic counterterm. The bubble diagrams know about thresholds and branch cuts; the counterterm is local and removes the ultraviolet divergence.

</figcaption>
</figure>

This is the model calculation where several ideas meet for the first time: loop momentum integration, channel dependence, symmetry factors, local counterterms, scheme dependence, running coupling, and the optical-theorem interpretation of imaginary parts.

## Setup and conventions

We use

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4
+\mathcal L_{\rm ct},
$$

with counterterms written as

$$
\mathcal L_{\rm ct}
=
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

The external particles have equal mass,

$$
p_i^2=m^2,
$$

and

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2.
$$

The amplitude convention is

$$
S_{fi}^{\rm conn}
=i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

Thus a diagrammatic contribution is a contribution to $i\mathcal M$.

At one loop in four-dimensional $\phi^4$ theory, the tadpole self-energy is momentum independent. Thus $\delta Z$ does not enter the four-point scattering amplitude at this order through LSZ residues. The mass counterterm is important for expressing the answer in a chosen mass scheme, but the direct one-loop four-point ultraviolet divergence is removed by $\delta\lambda$.

## The three bubble channels

The $s$-channel bubble carries total momentum

$$
P_s=p_1+p_2,
\qquad
P_s^2=s.
$$

Similarly,

$$
P_t=p_1-p_3,
\qquad
P_t^2=t,
$$

and

$$
P_u=p_1-p_4,
\qquad
P_u^2=u.
$$

Define the scalar bubble integral

$$
B(P^2)
\equiv
\mu^{2\epsilon}
\int\frac{d^d\ell}{(2\pi)^d}\,
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon}.
$$

Then the one-loop bubble contribution is

$$
i\mathcal M_{\rm bub}
=
\frac{(-i\lambda)^2}{2}
\left[
B(s)+B(t)+B(u)
\right].
$$

The factor $1/2$ is the symmetry factor of each bubble. It can be viewed as the automorphism that exchanges the two internal lines connecting the same pair of quartic vertices.

## Feynman parameter evaluation

Use the Feynman-parameter identity

$$
\frac{1}{AB}
=
\int_0^1 da\,\frac{1}{[aA+(1-a)B]^2}.
$$

With

$$
A=\ell^2-m^2+i\epsilon,
\qquad
B=(\ell+P)^2-m^2+i\epsilon,
$$

the denominator becomes

$$
aA+(1-a)B
=
(\ell+(1-a)P)^2
-\left[m^2-a(1-a)P^2\right]+i\epsilon.
$$

After the shift

$$
k=\ell+(1-a)P,
$$

we get

$$
B(P^2)
=
-\mu^{2\epsilon}\int_0^1 da
\int\frac{d^dk}{(2\pi)^d}
\frac{1}{\left[k^2-\Delta(a,P^2)+i\epsilon\right]^2},
$$

where

$$
\Delta(a,P^2)=m^2-a(1-a)P^2.
$$

The standard dimensionally regularized integral gives

$$
\mu^{2\epsilon}
\int\frac{d^dk}{(2\pi)^d}
\frac{1}{[k^2-\Delta+i\epsilon]^2}
=
\frac{i}{16\pi^2}
\left[
\Delta_{\overline{\mathrm{MS}}}
-\log\!\left(\frac{\Delta-i\epsilon}{\mu^2}\right)
\right]
+O(\epsilon).
$$

Therefore

$$
B(P^2)
=
-\frac{i}{16\pi^2}
\left[
\Delta_{\overline{\mathrm{MS}}}
-\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)P^2-i\epsilon}{\mu^2}
\right)
\right]
+O(\epsilon).
$$

This expression is compact, keeps the threshold structure visible, and is usually the best form for a first one-loop calculation.

## The unrenormalized amplitude

Substituting the bubble integral into the diagrammatic expression gives

$$
\mathcal M
=
-\lambda
+\frac{\lambda^2}{32\pi^2}
\sum_{x=s,t,u}
\left[
\Delta_{\overline{\mathrm{MS}}}
-\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)x-i\epsilon}{\mu^2}
\right)
\right]
-\delta\lambda
+O(\lambda^3).
$$

The divergent part is

$$
\mathcal M_{\rm div}
=
\frac{3\lambda^2}{32\pi^2}
\Delta_{\overline{\mathrm{MS}}}
-\delta\lambda.
$$

Thus the local counterterm required in $\overline{\mathrm{MS}}$ is

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}
\Delta_{\overline{\mathrm{MS}}}
+O(\lambda^3).
$$

This is the first concrete sign that the quartic coupling must be renormalized.

## The renormalized result in MS-bar

After subtracting the pole and associated $\overline{\mathrm{MS}}$ constants, the renormalized one-loop amplitude is

$$
\mathcal M_{\overline{\mathrm{MS}}}(s,t,u)
=
-\lambda(\mu)
-\frac{\lambda(\mu)^2}{32\pi^2}
\sum_{x=s,t,u}
\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)x-i\epsilon}{\mu^2}
\right)
+O(\lambda^3).
$$

The explicit $\mu$-dependence in the logarithms is compensated by the implicit $\mu$-dependence of $\lambda(\mu)$. Requiring the amplitude to be independent of $\mu$ at order $\lambda^2$ gives

$$
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}
+O(\lambda^3).
$$

This is the one-loop beta function of four-dimensional real $\phi^4$ theory.

## Thresholds and imaginary parts

The Feynman-parameter denominator

$$
m^2-a(1-a)x-i\epsilon
$$

can become negative for real $x>4m^2$. This happens because $a(1-a)\le 1/4$. Therefore the bubble has a branch point at

$$
x=4m^2.
$$

For $x>4m^2$, define

$$
\beta_x=\sqrt{1-\frac{4m^2}{x}}.
$$

The interval in Feynman-parameter space where the logarithm crosses the negative real axis has length $\beta_x$. Since

$$
\log(-|A|-i\epsilon)=\log|A|-i\pi,
$$

the channel contribution develops an imaginary part

$$
\operatorname{Im}\mathcal M_x
=
\frac{\lambda^2}{32\pi}\beta_x
\qquad (x>4m^2).
$$

For physical $2\to2$ scattering above threshold, the $s$-channel imaginary part is the one directly associated with the two-particle intermediate state. The $t$ and $u$ channel branch cuts are the crossed-channel versions of the same analytic structure.

## Optical-theorem check

At order $\lambda^2$, unitarity relates the imaginary part of the one-loop forward amplitude to the tree amplitude squared integrated over two-particle phase space. Schematically,

$$
2\,\operatorname{Im}\mathcal M^{(1)}_{2\to2}
=
\int d\Pi_2\,|\mathcal M_{\rm tree}|^2
$$

with the appropriate identical-particle counting and normalization conventions.

For the $s$-channel cut, the result above gives

$$
2\,\operatorname{Im}\mathcal M_s^{(1)}
=
\frac{\lambda^2}{16\pi}
\sqrt{1-\frac{4m^2}{s}},
$$

which is the expected two-particle phase-space factor in this normalization. This is a useful sign check: the imaginary part is not an accident of the logarithm; it is the perturbative imprint of probability conservation.

## Scheme dependence and physical meaning

The finite part of the amplitude depends on how the renormalized coupling is defined. In $\overline{\mathrm{MS}}$, $\lambda(\mu)$ is defined by subtracting poles and fixed constants, not by measuring a specific scattering process at a specific energy. In an on-shell or momentum-subtraction scheme, one could instead impose a condition such as

$$
\mathcal M(s_0,t_0,u_0)=-\lambda_{\rm phys}
$$

at a chosen kinematic point. The counterterm would then include a finite part, and the displayed formula would change by a finite redefinition of $\lambda$.

The physical amplitude, expressed in terms of physical inputs and evaluated consistently to a fixed order, is scheme-independent up to higher-order corrections. The bookkeeping changes; the prediction does not.

## Mass and wavefunction comments

This page focuses on the one-loop four-point coupling renormalization. In the same theory, the one-loop two-point tadpole shifts the mass. If the amplitude is written in terms of a physical pole mass rather than a Lagrangian mass, the mass counterterm affects how $m$ is interpreted inside the logarithms.

Wavefunction renormalization does not contribute at one loop in four-dimensional $\phi^4$ theory because the one-loop self-energy is momentum independent. The first momentum-dependent field-strength renormalization appears at two loops. This is one reason $\phi^4$ theory is friendly: the one-loop four-point calculation isolates coupling renormalization cleanly.

## Common pitfalls

**Losing the sign of the bubble integral.** The two propagators contribute $i^2=-1$. If $B(P^2)$ includes the propagator factors, then it carries an overall $-i$ times the usual logarithmic bracket.

**Forgetting the factor $1/2$.** Each one-loop bubble has a symmetry factor $1/2$. Dropping it doubles the beta function.

**Subtracting only one channel.** The divergence appears in all three channels. The total one-loop divergence is proportional to $3\lambda^2$.

**Calling the counterterm optional.** The counterterm is required if the continuum limit is to be expressed in terms of finite renormalized parameters.

**Confusing MS-bar with an observable definition.** $\lambda(\mu)$ in $\overline{\mathrm{MS}}$ is a scheme-dependent parameter. It becomes physical only after it is related to a measured quantity or matching condition.

**Ignoring the threshold.** The logarithm knows when two internal particles can go on shell. The branch cut at $x=4m^2$ is not a technical nuisance; it is the analytic signature of real intermediate states.

## Relations to other pages

- [φ⁴ Theory: 2→2 Scattering](/perturbative-qft/model-calculation-library/phi-four-two-to-two-scattering/) gives the tree-level baseline.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) derives the scalar bubble technology used here.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) explains the parameter identity and momentum shift.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) explains the subtraction convention.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) places $\delta\lambda$ and the beta function in the general framework.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) explains the analytic structure behind the logarithm.
- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) explains the cut interpretation of the imaginary part.

## Research status

- **Established:** The bubble diagrams, counterterm subtraction, and one-loop beta function are standard textbook results.
- **Active:** The same amplitude remains a useful controlled example for numerical loop integration, lattice matching, finite-volume studies, threshold expansions, and pedagogical comparisons between schemes.
- **Convention-dependent:** The displayed signs assume the QFT.org $S=1+i(2\pi)^4\delta^{(4)}\mathcal M$ convention and the interaction $-\lambda\phi^4/4!$.

## Exercises

### Exercise 1: Bubble symmetry factor

Explain why the one-loop four-point bubble in $\phi^4$ theory has symmetry factor $1/2$.

<details>
<summary><strong>Solution</strong></summary>

The two internal lines connect the same pair of quartic vertices. Exchanging those two internal lines leaves the graph unchanged while keeping the external attachments fixed. This nontrivial automorphism has order $2$, so the graph contribution is divided by $2$.

Equivalently, a direct Wick-contraction count gives twice as many labeled contractions as the unlabeled graph represents. The symmetry factor removes that overcounting.

</details>

### Exercise 2: Feynman parameter denominator

Starting from

$$
\frac{1}{[\ell^2-m^2+i\epsilon][(\ell+P)^2-m^2+i\epsilon]},
$$

show that the Feynman-parameter denominator becomes

$$
[k^2-m^2+a(1-a)P^2+i\epsilon]^2
$$

after a shift of loop momentum.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\frac{1}{AB}=\int_0^1 da\,\frac{1}{[aA+(1-a)B]^2}.
$$

Then

$$
aA+(1-a)B
=
a(\ell^2-m^2+i\epsilon)
+(1-a)((\ell+P)^2-m^2+i\epsilon).
$$

Expanding,

$$
aA+(1-a)B
=
\ell^2+2(1-a)\ell\cdot P+(1-a)P^2-m^2+i\epsilon.
$$

Complete the square with

$$
k=\ell+(1-a)P.
$$

Then

$$
\ell^2+2(1-a)\ell\cdot P+(1-a)P^2
=
k^2+a(1-a)P^2.
$$

Therefore

$$
aA+(1-a)B
=
k^2-m^2+a(1-a)P^2+i\epsilon.
$$

Equivalently,

$$
aA+(1-a)B
=
k^2-\left[m^2-a(1-a)P^2\right]+i\epsilon.
$$

</details>

### Exercise 3: MS-bar counterterm

Using the fact that each of the three channels contributes

$$
\frac{\lambda^2}{32\pi^2}\Delta_{\overline{\mathrm{MS}}}
$$

to $\mathcal M$, find the one-loop $\overline{\mathrm{MS}}$ counterterm $\delta\lambda$.

<details>
<summary><strong>Solution</strong></summary>

The three channels give the divergent contribution

$$
\mathcal M_{\rm div}
=
3\frac{\lambda^2}{32\pi^2}\Delta_{\overline{\mathrm{MS}}}.
$$

The counterterm vertex contributes

$$
\mathcal M_{\rm ct}=-\delta\lambda.
$$

Cancellation requires

$$
\mathcal M_{\rm div}+\mathcal M_{\rm ct}=0,
$$

so

$$
\delta\lambda_{\overline{\mathrm{MS}}}
=
\frac{3\lambda^2}{32\pi^2}\Delta_{\overline{\mathrm{MS}}}.
$$

</details>

### Exercise 4: Beta function from scale independence

Use the renormalized amplitude

$$
\mathcal M
=
-\lambda(\mu)
-\frac{\lambda(\mu)^2}{32\pi^2}
\sum_{x=s,t,u}\int_0^1 da\,
\log\!\left(
\frac{m^2-a(1-a)x-i\epsilon}{\mu^2}
\right)
+O(\lambda^3)
$$

to derive the one-loop beta function.

<details>
<summary><strong>Solution</strong></summary>

At order $\lambda^2$, it is enough to differentiate the first term using

$$
\beta(\lambda)=\mu\frac{d\lambda}{d\mu}
$$

and treat the $\lambda^2$ multiplying the logarithms as constant. Since

$$
\mu\frac{d}{d\mu}\log\!\left(\frac{A}{\mu^2}\right)=-2,
$$

the logarithmic term contributes

$$
-\frac{\lambda^2}{32\pi^2}(3)(-2)
=
\frac{3\lambda^2}{16\pi^2}.
$$

Scale independence gives

$$
0=-\beta(\lambda)+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3),
$$

so

$$
\beta(\lambda)=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

</details>

### Exercise 5: Threshold condition

Show that the bubble integral develops an imaginary part for real $x>4m^2$.

<details>
<summary><strong>Solution</strong></summary>

The logarithm contains

$$
m^2-a(1-a)x-i\epsilon.
$$

For real $a\in[0,1]$, the maximum value of $a(1-a)$ is $1/4$, attained at $a=1/2$. The argument can become negative only if

$$
m^2-\frac{x}{4}<0,
$$

or

$$
x>4m^2.
$$

When this happens, the logarithm crosses the negative real axis on an interval of Feynman-parameter space, producing an imaginary part. The point $x=4m^2$ is therefore the two-particle threshold branch point.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§14–20 for scalar loop corrections, one-loop amplitudes, and all-order perturbation theory.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 15–16 and 25 for one-loop renormalization, counterterms, and regularization.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15–19 for regularization, mass and coupling renormalization, and renormalized perturbation theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6, 10, and 12 for Feynman rules, loop corrections, and renormalization.

## Version history

- **2026-06-13:** Initial model-calculation-library page for the one-loop four-point amplitude in real $\phi^4$ theory.
