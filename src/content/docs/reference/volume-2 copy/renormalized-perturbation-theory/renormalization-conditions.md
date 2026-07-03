---
title: "Renormalization Conditions"
description: "How finite counterterms are fixed by defining renormalized masses, couplings, fields, and composite quantities through conditions on Green functions or amplitudes."
sidebar:
  label: "Renormalization Conditions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§27–29; Schwartz chs. 18–19; Weinberg Vol. I ch. 12; Zinn-Justin, renormalization chapters."
topics:
  - renormalization conditions
  - counterterms
  - renormalized parameters
  - on-shell renormalization
  - momentum subtraction
  - minimal subtraction
canonicalTopics:
  - renormalization-conditions
  - renormalized-perturbation-theory
  - finite-counterterms
  - physical-inputs
researchStatus:
  established:
    - "Renormalization conditions fix the finite parts of counterterms and thereby define the renormalized parameters used in perturbation theory."
  active:
    - "Choosing practical conditions remains subtle in gauge theories, unstable-particle processes, chiral theories, EFT matching, nonperturbative definitions, and automated high-order calculations."
---

## Summary

A **renormalization condition** is a rule that says what a renormalized parameter means. It fixes the finite parts of counterterms by imposing conditions on renormalized Green functions, 1PI vertices, amplitudes, pole locations, residues, or low-energy coefficients.

The counterterms have two jobs:

$$
\text{counterterms}
=\text{UV cancellation}+\text{definition of renormalized coordinates}.
$$

The first job is forced by locality and short-distance singularities. The second job is a convention. A mass can mean a pole mass, a running mass in $\overline{\mathrm{MS}}$, a Euclidean momentum-subtraction mass, or another carefully defined quantity. A coupling can mean a coefficient in a Lagrangian, a value of a 1PI vertex at a chosen point, a low-energy scattering observable, or a Wilson coefficient in an EFT. These definitions are related, but they are not identical.

For a stable scalar particle, an on-shell convention might define the renormalized mass and field normalization by requiring the full propagator to have a pole at $p^2=m^2$ with unit residue:

$$
G_R(p)\underset{p^2\to m^2}{=}
\frac{i}{p^2-m^2+i\epsilon}+\text{regular}.
$$

For a coupling in scalar $\phi^4$ theory, a momentum-subtraction convention might define $\lambda(\mu)$ by requiring the Euclidean 1PI four-point vertex at a symmetric subtraction point to equal $\lambda(\mu)$:

$$
\Gamma^{(4)}_{E,R}\big|_{\text{sym},\mu}=\lambda(\mu).
$$

Minimal subtraction instead defines the parameters by subtracting only pole terms in dimensional regularization. That is less directly physical, but it is often the cleanest coordinate system for RG calculations.

:::note[The slogan]
A divergence tells you that a local parameter must be defined. A renormalization condition tells you how that parameter is defined.
:::

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/). For the conceptual background, review [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/) and [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/).

The conventions are those of [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, $\hbar=c=1$, dimensional regularization with $d=4-2\epsilon$ when used, and

$$
\frac{1}{\bar\epsilon}\equiv \frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

## Core idea

A regulated loop calculation does not by itself define the renormalized parameters. Suppose a one-loop self-energy produces a local divergent contribution proportional to $\phi^2$. Locality tells us that a mass counterterm is allowed and needed, but locality does not tell us whether the finite mass parameter should equal a pole mass, a Euclidean subtraction mass, or an $\overline{\mathrm{MS}}$ running mass.

That extra choice is the renormalization condition.

In practice, a renormalization condition is imposed on a finite renormalized quantity. Examples include:

| Quantity being defined | Typical condition |
|---|---|
| field normalization | residue of a pole, derivative of a two-point function, or canonical normalization at a subtraction point |
| mass | location of a pole, zero of a Euclidean inverse propagator, or running parameter in a subtraction scheme |
| coupling | value of an amputated vertex or scattering amplitude at a chosen kinematic point |
| composite operator normalization | value of a matrix element or correlation function with an operator insertion |
| Wilson coefficient | matching equality between a full theory and an EFT at a chosen scale |

The number of independent conditions should match the number of independent renormalized parameters being defined. Too few conditions leave finite ambiguity. Too many conditions overconstrain the theory unless a symmetry or identity makes some conditions dependent.

Renormalization conditions are not merely a beginner's crutch. They are the operational bridge between Lagrangian symbols and measured input numbers.

## Setup and conventions

Let the renormalized action be written as

$$
S_0=S_{\text{ren}}+S_{\text{ct}}.
$$

For real scalar $\phi^4$ theory in $d=4-2\epsilon$, we use the template

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

The coefficients $\delta Z$, $\delta m^2$, and $\delta\lambda$ are expanded order by order:

$$
\delta Z=\sum_{L\ge 1}\delta Z^{(L)},
\qquad
\delta m^2=\sum_{L\ge 1}\delta m^{2(L)},
\qquad
\delta\lambda=\sum_{L\ge 1}\delta\lambda^{(L)}.
$$

At a given loop order, the divergent parts of these quantities are chosen to cancel regulator dependence. The finite parts are chosen by the renormalization conditions.

It is useful to separate three objects:

$$
\text{bare parameter}
\qquad
\text{renormalized parameter}
\qquad
\text{observable input}.
$$

The bare parameter belongs to the regulated definition of the theory. The renormalized parameter belongs to a scheme. The observable input is a measured or otherwise specified physical number. A renormalization condition is the rule that relates the middle object to a calculable Green function or observable.

## What conditions actually fix

Counterterms are local polynomials in external momenta, fields, masses, and couplings. Therefore they can only change the local part of a Green function. A renormalization condition fixes exactly those local ambiguities.

For a scalar two-point function, the local counterterm structure through two derivatives is

$$
C_2(p^2)=c_0+c_1(p^2-m^2).
$$

The coefficient $c_0$ shifts the mass definition. The coefficient $c_1$ shifts the field normalization. A loop correction can contain a complicated nonlocal finite function of $p^2$, but the counterterm can only alter the local polynomial part.

For a four-point function in a renormalizable scalar theory, the leading local four-field counterterm is a constant in momentum space:

$$
C_4=c_4.
$$

That constant shifts the definition of the quartic coupling. In an EFT, higher-derivative four-field counterterms also appear, such as

$$
(\partial_\mu\phi\partial^\mu\phi)\phi^2,
\qquad
(\partial_\mu\phi\partial^\mu\phi)^2,
$$

and their coefficients are fixed by additional conditions or by matching.

A good renormalization condition asks the counterterm to do only what it can do: adjust local pieces. It cannot remove a branch cut, a threshold logarithm, a unitarity cut, or a nonanalytic dependence on external momenta. Those are physical or long-distance features of the amplitude.

## Two-point conditions

Let the full renormalized scalar propagator be written near the one-particle region as

$$
G_R(p)=\frac{i}{\mathcal D_R^{-1}(p^2)+i\epsilon},
$$

where $\mathcal D_R^{-1}$ is the renormalized inverse denominator. At tree level,

$$
\mathcal D_{R,\text{tree}}^{-1}(p^2)=p^2-m^2.
$$

Loop and counterterm corrections change this to

$$
\mathcal D_R^{-1}(p^2)
=p^2-m^2+\Delta_R(p^2),
$$

where $\Delta_R$ denotes the total self-energy correction in this convention, including loop and counterterm pieces.

A pole-mass condition for a stable particle sets

$$
\mathcal D_R^{-1}(m^2)=0.
$$

A unit-residue field-normalization condition sets

$$
\left.\frac{d\mathcal D_R^{-1}}{dp^2}\right|_{p^2=m^2}=1.
$$

Equivalently,

$$
\Delta_R(m^2)=0,
\qquad
\Delta_R'(m^2)=0.
$$

These two conditions fix the finite mass counterterm and the finite wavefunction counterterm.

The physical content is simple: the parameter $m$ in the Lagrangian is defined to be the pole mass, and the interpolating field is normalized so that the pole has residue one. In this convention, LSZ external-leg factors are simplified.

There are several caveats. Pole conditions are not ideal for massless particles with infrared singularities. They are not directly applicable to confined particles, which do not appear as isolated poles in gauge-invariant scattering states. They require extra care for unstable particles, whose pole is complex. They can also hide large logarithms when a process involves scales far from the particle mass.

## A clean algebraic toy version

Suppose the one-loop correction to the inverse propagator before finite renormalization is

$$
\Delta_{\text{loop}}(p^2)=A+B(p^2-m^2)+F(p^2),
$$

where $A$ and $B$ may contain divergent pieces, while $F(p^2)$ is a nonlocal function normalized for convenience so that its Taylor expansion begins at quadratic order around $p^2=m^2$:

$$
F(m^2)=0,
\qquad
F'(m^2)=0.
$$

The local two-point counterterm contributes

$$
\Delta_{\text{ct}}(p^2)=a+b(p^2-m^2).
$$

The renormalized correction is

$$
\Delta_R(p^2)=A+a+(B+b)(p^2-m^2)+F(p^2).
$$

The on-shell conditions $\Delta_R(m^2)=0$ and $\Delta_R'(m^2)=0$ give

$$
a=-A,
\qquad
b=-B.
$$

This little calculation is almost embarrassingly simple, but it captures the mechanism. The counterterm cancels the local Taylor coefficients selected by the renormalization condition. The nonlocal part $F(p^2)$ remains. It is not a nuisance; it is the actual momentum dependence predicted by the theory.

## Four-point conditions

For scalar $\phi^4$ theory, the renormalized quartic coupling can be defined from a four-point function. In Euclidean notation, write the 1PI effective action as

$$
\Gamma_E[\phi]
=\sum_{n=0}^{\infty}\frac{1}{n!}
\int\prod_{a=1}^n\frac{d^d p_a}{(2\pi)^d}
(2\pi)^d\delta^{(d)}\!\left(\sum_a p_a\right)
\Gamma^{(n)}_{E,R}(p_1,\ldots,p_n)
\phi(p_1)\cdots\phi(p_n).
$$

At tree level, in the convention used here,

$$
\Gamma^{(4)}_{E,\text{tree}}=\lambda.
$$

A momentum-subtraction definition of the coupling chooses a Euclidean subtraction point and imposes

$$
\Gamma^{(4)}_{E,R}(p_1,p_2,p_3,p_4)\big|_{\text{subtraction point}}=\lambda(\mu).
$$

A common choice is a symmetric Euclidean point. The details of the symmetric point are less important than the principle: all invariants are chosen away from thresholds and exceptional momenta, so the subtraction is infrared safe and treats the channels symmetrically.

In Lorentzian scattering language, one can instead define a coupling from an amputated scattering amplitude at specified kinematics. That definition is closer to measurement, but it may be less convenient for loop calculations because thresholds and imaginary parts must be handled carefully.

## Momentum-subtraction conditions

Momentum subtraction, often abbreviated MOM, defines renormalized parameters by imposing conditions on Green functions at a chosen Euclidean momentum scale $\mu$.

For a scalar two-point function, one might impose

$$
\Gamma_{E,R}^{(2)}(p_E^2=\mu^2)=\mu^2+m^2(\mu),
$$

and

$$
\left.\frac{d\Gamma_{E,R}^{(2)}}{dp_E^2}\right|_{p_E^2=\mu^2}=1.
$$

For a quartic coupling,

$$
\Gamma_{E,R}^{(4)}\big|_{\text{sym},\mu}=\lambda(\mu).
$$

These are genuine renormalization conditions. They define the running quantities $m^2(\mu)$ and $\lambda(\mu)$ in terms of Euclidean correlation functions at the scale $\mu$.

Momentum subtraction has several advantages:

- it is operational and intuitive;
- it works naturally with Euclidean correlation functions;
- it makes the subtraction scale visibly tied to the momentum at which a Green function is normalized;
- it is useful for comparing perturbative calculations with nonperturbative or lattice definitions.

It also has disadvantages. It can be algebraically messier than minimal subtraction, especially in gauge theories and multi-loop calculations. It may introduce gauge-dependent definitions if imposed on gauge-dependent Green functions. It is also usually mass-dependent, so beta functions can contain mass ratios such as $m^2/\mu^2$.

## On-shell conditions

On-shell renormalization defines parameters using physical pole data and low-energy amplitudes. For a stable scalar particle, the conditions are

$$
G_R(p)\underset{p^2\to m_{\text{phys}}^2}{=}
\frac{i}{p^2-m_{\text{phys}}^2+i\epsilon}+\text{regular}.
$$

For QED, an on-shell scheme commonly defines the electron mass from the electron pole, the field normalization from residues, and the electric charge from a low-momentum electromagnetic process such as the Thomson limit.

The appeal is obvious: the parameters are close to directly measured quantities. The price is also real: on-shell conditions are often awkward for high-energy processes, massless particles, unstable particles, and theories where the fundamental fields are not asymptotic states.

On-shell schemes are excellent when the physical pole structure is the central object. They are not universal magic.

## Minimal-subtraction conditions

Minimal subtraction is sometimes described as though it had no renormalization conditions. That is misleading. Minimal subtraction has a condition; it is just not a condition imposed at a physical momentum point.

In dimensional regularization, MS defines the counterterms by subtracting only poles in $\epsilon$. The $\overline{\mathrm{MS}}$ scheme subtracts the common combination

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

Thus a typical renormalization factor has the form

$$
Z_g^{\overline{\mathrm{MS}}}
=1+\sum_{L\ge 1}\sum_{k=1}^{L}\frac{Z_{g,Lk}}{\epsilon^k}.
$$

There are no additional finite terms in $Z_g^{\overline{\mathrm{MS}}}$, apart from the conventional $\gamma_E$ and $\log4\pi$ packaging. That rule defines the scheme.

Minimal subtraction is powerful because it is mass-independent and algebraically efficient. It tends to produce simple beta functions and is the standard language for high-order perturbation theory. But the parameters it defines are not directly measured observables. They must be related to physical inputs by separate matching or conversion formulas.

## Conditions and measured inputs

A theory with $N$ independent renormalized parameters requires $N$ independent input conditions. These inputs may be physical observables, convenient reference quantities, or matching data.

For example, a simple scalar theory with parameters $m^2$ and $\lambda$ could be fixed by:

| Scheme style | Possible inputs |
|---|---|
| on-shell | pole mass and a scattering amplitude at specified physical kinematics |
| Euclidean MOM | two-point and four-point 1PI vertices at Euclidean subtraction points |
| minimal subtraction | $m^2(\mu)$ and $\lambda(\mu)$ quoted at a reference scale, with conversion to observables supplied separately |
| EFT matching | a low-energy mass plus Wilson coefficients fixed by matching to a full theory or data |

The renormalized parameter is not self-measuring. A statement such as $\lambda=0.3$ is incomplete until the scheme and scale are specified.

This is especially important in precision physics. A mass quoted as a pole mass, an $\overline{\mathrm{MS}}$ mass, a threshold mass, or a lattice mass is not the same number. A coupling quoted at $\mu=m_Z$ is not the same coordinate as the same coupling at $\mu=2\,\mathrm{GeV}$.

## Conditions in theories with symmetry

Symmetries constrain which renormalization conditions are allowed and which counterterms are independent. For example, a Ward identity may relate a vertex renormalization to a field renormalization. In such a case, imposing independent finite conditions on both quantities can accidentally violate the identity unless the conditions are chosen compatibly.

The safest rule is:

$$
\text{renormalize in a way that preserves the identities you need, or track their restoration explicitly.}
$$

In gauge theories, this often means using gauge-invariant regulators when possible, using BRST-compatible schemes, or imposing renormalization conditions on gauge-invariant quantities. Gauge-dependent Green functions can be useful, but their scheme definitions must not be mistaken for direct observables.

For composite operators, symmetries also determine operator mixing. If operators $\mathcal O_a$ mix,

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

then renormalization conditions must fix a matrix, not just a number. The conditions should respect quantum numbers, equations of motion, total derivatives, and any gauge or global symmetry constraints.

## Exceptional momenta and infrared traps

A subtraction point is called exceptional if some partial sum of external momenta vanishes. For example, in a four-point function with external momenta $p_1,p_2,p_3,p_4$, the condition

$$
p_1+p_2=0
$$

can create infrared sensitivity in some massless theories. This does not mean the UV subtraction is wrong in principle, but it can entangle UV renormalization with IR physics.

A symmetric Euclidean subtraction point avoids many of these problems by keeping all channels away from zero momentum and physical thresholds. This is why Euclidean momentum-subtraction schemes are often phrased with symmetric nonexceptional kinematics.

The moral is not that all physical conditions are bad. The moral is that a renormalization condition should be chosen with its infrared environment in mind.

## Worked example: fixing a local two-point ambiguity

Consider a one-loop two-point function whose regulated loop correction can be decomposed near a chosen subtraction point $p^2=p_*^2$ as

$$
\Delta_{\text{loop}}(p^2)=A_*+B_*(p^2-p_*^2)+R_*(p^2),
$$

with

$$
R_*(p_*^2)=0,
\qquad
R_*'(p_*^2)=0.
$$

The local two-point counterterm contributes

$$
\Delta_{\text{ct}}(p^2)=a_*+b_*(p^2-p_*^2).
$$

A momentum-subtraction condition that removes the loop correction and its first derivative at $p_*^2$ imposes

$$
\Delta_R(p_*^2)=0,
\qquad
\Delta_R'(p_*^2)=0.
$$

Thus

$$
a_*=-A_*,
\qquad
b_*=-B_*.
$$

The renormalized correction is then

$$
\Delta_R(p^2)=R_*(p^2).
$$

Changing the subtraction point changes which local Taylor terms are removed. The two resulting Green functions differ by local finite counterterms, not by nonlocal physics.

## Common pitfalls

**Thinking that a renormalization condition is a physical law.** A condition defines a parameter. The physical laws are expressed by scheme-independent relations among observables.

**Forgetting finite parts.** Canceling $1/\epsilon$ poles is not enough to define a physical mass or coupling. The finite part decides what the renormalized parameter means.

**Overconstraining the theory.** You cannot impose arbitrary independent conditions on every Green function. Counterterms only provide a finite number of local adjustable coefficients in a renormalizable theory.

**Using on-shell conditions in an infrared-unsafe setting.** Massless particles, thresholds, and confined degrees of freedom require care. A beautiful condition in one problem can be a disaster in another.

**Confusing field normalization with an observable.** The residue of an interpolating field can be convenient, but field normalizations are not usually direct observables. S-matrix elements and gauge-invariant correlation functions are the safer physical objects.

**Comparing parameters without the scheme and scale.** A mass or coupling quoted without its definition is only half a statement.

## Relations to other pages

[Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/) explains how the bare Lagrangian is split into renormalized terms and counterterms. This page explains how the finite pieces of those counterterms are fixed.

[Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/) compares the major styles of finite counterterm choice: minimal subtraction, modified minimal subtraction, momentum subtraction, on-shell schemes, and finite scheme transformations.

[Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/) gives the conceptual distinction between Lagrangian symbols and measured quantities. [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/) explains why the Green functions being conditioned require renormalization in the first place.

Later pages on wavefunction, mass, coupling, Green-function, and S-matrix renormalization apply these conditions in specific calculations.

## Research status

The basic logic of renormalization conditions is settled. It is part of the standard perturbative construction of QFT.

The subtle work lies in choosing conditions that are efficient, symmetry-compatible, and physically useful in complicated settings. Examples include gauge theories with unstable particles, high-order electroweak calculations, chiral gauge theories, EFT operator bases, heavy-particle thresholds, lattice-to-continuum matching, and nonperturbative definitions of running couplings.

In modern research, the phrase "renormalization condition" often appears as part of a larger workflow: define a scheme, compute conversion factors, match across thresholds, run with RG equations, estimate truncation uncertainty, and finally express results in terms of physical inputs.

## Exercises

### Exercise 1: Two conditions for two local coefficients

Let

$$
\Delta_R(p^2)=\Delta_{\text{loop}}(p^2)+a+b(p^2-m^2),
$$

where $a$ and $b$ are counterterm coefficients. Show that the on-shell-style conditions

$$
\Delta_R(m^2)=0,
\qquad
\Delta_R'(m^2)=0
$$

fix $a$ and $b$ in terms of the loop correction.

<details><summary><strong>Solution</strong></summary>

Evaluating at $p^2=m^2$ gives

$$
0=\Delta_R(m^2)=\Delta_{\text{loop}}(m^2)+a,
$$

so

$$
a=-\Delta_{\text{loop}}(m^2).
$$

Differentiating gives

$$
\Delta_R'(p^2)=\Delta_{\text{loop}}'(p^2)+b.
$$

Therefore

$$
0=\Delta_R'(m^2)=\Delta_{\text{loop}}'(m^2)+b,
$$

so

$$
b=-\Delta_{\text{loop}}'(m^2).
$$

The two local counterterm coefficients remove the value and slope of the loop correction at the chosen point.

</details>

### Exercise 2: Why a coupling condition needs kinematics

Explain why the statement "define $\lambda$ to be the four-point function" is incomplete in an interacting theory.

<details><summary><strong>Solution</strong></summary>

The four-point function depends on the external momenta. In a Lorentz-invariant scalar theory it depends on invariants such as $s,t,u$, or on Euclidean analogues. Loop corrections contain nontrivial functions of these invariants, including logarithms and threshold structures. A single number $\lambda$ can only be defined by specifying a particular kinematic point or a particular low-energy expansion coefficient. Thus a complete condition must say something like

$$
\Gamma^{(4)}_{E,R}\big|_{\text{sym},\mu}=\lambda(\mu),
$$

or define $\lambda$ from a specified scattering amplitude at specified physical kinematics.

</details>

### Exercise 3: Scheme conversion from two definitions

Suppose two definitions of a dimensionless coupling are related at small coupling by

$$
g'=g+a g^3+O(g^5).
$$

If a physical observable has the expansion

$$
\mathcal O=g^2+c g^4+O(g^6),
$$

rewrite it in terms of $g'$ through order $g'^4$.

<details><summary><strong>Solution</strong></summary>

Invert the coupling relation:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2a g'^4+O(g'^6),
$$

and

$$
g^4=g'^4+O(g'^6).
$$

Therefore

$$
\mathcal O=g'^2+(c-2a)g'^4+O(g'^6).
$$

The coefficient of the perturbative expansion changes because the coordinate on coupling space changed. The observable did not change.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on divergences, counterterms, and renormalization.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry."
- Mark Srednicki, *Quantum Field Theory*, especially the sections on other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters on mass renormalization and renormalized perturbation theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization and normalization conditions for correlation functions.

## Version history

- 2026-06-17: First polished draft. Introduced renormalization conditions as finite counterterm definitions, with two-point, four-point, on-shell, momentum-subtraction, and minimal-subtraction examples.
