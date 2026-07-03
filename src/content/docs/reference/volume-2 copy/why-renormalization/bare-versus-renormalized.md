---
title: "Bare versus Renormalized"
description: "The difference between bare parameters, renormalized parameters, counterterms, running couplings, and physical observables."
sidebar:
  label: "Bare versus Renormalized"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§27–29; Coleman, Renormalization and Symmetry and Dilatations; Weinberg Vol. I ch. 12; Weinberg Vol. II ch. 18; Schwartz chs. 18–23; Zinn-Justin, renormalization chapters; Burgess 2020 chs. 2–3."
topics:
  - bare parameters
  - renormalized parameters
  - counterterms
  - renormalization schemes
  - running couplings
  - physical observables
canonicalTopics:
  - bare-parameter
  - renormalized-parameter
  - counterterm
  - renormalization-scheme
  - beta-function
researchStatus:
  established:
    - "Bare parameters belong to a regulated definition of a theory, while renormalized parameters are scheme-dependent coordinates used to express physical predictions."
  active:
    - "The interpretation of bare parameters is especially subtle in naturalness, lattice field theory, asymptotic safety, chiral gauge theories, quantum gravity EFT, and nonperturbative continuum limits."
---

## Summary

A bare parameter is not usually a directly measured number. A renormalized parameter is not automatically a directly measured number either. A physical observable is what an experiment or a well-defined theoretical measurement extracts.

The three should be kept separate:

| Object | Lives in | Depends on | Typical example |
|---|---|---|---|
| bare parameter | regulated Lagrangian | regulator and cutoff convention | $m_0^2$, $\lambda_0$, $e_0$ |
| renormalized parameter | chosen scheme at scale $\mu$ | scheme and $\mu$ | $m^2(\mu)$, $\lambda(\mu)$, $e(\mu)$ |
| physical observable | measurement or invariant definition | physical scales and states | pole mass, cross section, decay rate |

A useful schematic map is

$$
\{g_0,\Lambda\}
\quad\stackrel{\text{renormalization at }\mu}{\longleftrightarrow}\quad
\{g(\mu)\}
\quad\stackrel{\text{calculation}}{\longrightarrow}\quad
\{\text{observables}\}.
$$

The bare parameters and the renormalized parameters are coordinates. Observables are the coordinate-independent targets.

<figure class="doc-figure" style="--figure-width: 45rem; --caption-width: 55rem;">

![A schematic map from a bare regulated theory to renormalized coordinates, local counterterms, and physical observables](/figures/renormalization-rg-eft/bare-renormalized-observable-map.svg)

<figcaption>

A bare regulated theory can be rewritten in terms of renormalized coordinates and local counterterms. The split depends on the scheme and the scale $\mu$; properly defined observables are independent of arbitrary regulator and subtraction choices.

</figcaption>
</figure>

:::note[Do not romanticize bare parameters]
The word “bare” sounds more fundamental than “renormalized,” but in continuum perturbation theory bare parameters are often regulator-dependent bookkeeping devices. In a Wilsonian theory with a physical finite cutoff, cutoff-scale couplings can have physical meaning as part of a microscopic or effective description. Context matters.
:::

## Prerequisites

You should have read [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/). The main point from that page is that UV divergences multiply local operators. This page explains how the coefficients of those local operators are split into bare parameters, renormalized parameters, and counterterms.

You should also know the volume [Conventions and Notation](/renormalization-rg-eft/conventions/), especially the definition

$$
\beta_g(g)\equiv \left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

## Core idea

Start with a regulated theory. Its Lagrangian is written in terms of bare fields and bare parameters:

$$
\mathcal L_0=\mathcal L_0(\phi_0,g_0;\text{regulator}).
$$

The regulator might be a hard cutoff $\Lambda$, a lattice spacing $a$, Pauli–Villars fields, dimensional regularization with $d=4-2\epsilon$, or something else.

A renormalized calculation rewrites the same bare Lagrangian in terms of renormalized fields and renormalized parameters:

$$
\mathcal L_0
=\mathcal L_{\text{ren}}(\phi,g(\mu),\mu)
+\mathcal L_{\text{ct}}(\phi,g(\mu),\mu;\text{regulator}).
$$

The split is not unique. The counterterms cancel regulator dependence from loops. Their finite parts depend on the renormalization scheme.

The physical prediction is not $g_0$ and not $g(\mu)$ alone. It is a properly defined observable computed after the parameters have been fixed by measurement, matching, or boundary conditions.

## Setup and conventions

We write bare quantities with a subscript $0$:

$$
\phi_0,
\qquad
m_0^2,
\qquad
\lambda_0,
\qquad
g_0.
$$

Renormalized quantities are usually written without a subscript, with their scale dependence shown explicitly when useful:

$$
\phi,
\qquad
m^2(\mu),
\qquad
\lambda(\mu),
\qquad
g(\mu).
$$

In dimensional regularization near four dimensions, we use

$$
d=4-2\epsilon.
$$

The renormalization scale $\mu$ is introduced so that renormalized couplings can keep their usual four-dimensional dimensions. For example, in scalar $\phi^4$ theory one writes schematically

$$
\lambda_0=\mu^{2\epsilon}Z_\lambda(\lambda,\epsilon)\lambda.
$$

For fields,

$$
\phi_0=Z_\phi^{1/2}\phi.
$$

The precise $Z$ factors depend on the theory, regulator, and scheme.

## A scalar example

Consider a real scalar theory in four dimensions:

$$
\mathcal L_0
=\frac12\partial_\mu\phi_0\partial^\mu\phi_0
-\frac12m_0^2\phi_0^2
-\frac{\lambda_0}{4!}\phi_0^4.
$$

Introduce a renormalized field and renormalized parameters:

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=m^2+\delta m^2\quad\text{schematically},
\qquad
\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda)\quad\text{schematically}.
$$

Then the same bare Lagrangian can be written as

$$
\mathcal L_0
=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}},
$$

where

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

This split is a choice of coordinates. The bare Lagrangian on the left is the regulated object. The renormalized Lagrangian contains the parameters one wants to use in predictions. The counterterm Lagrangian contains the compensating local terms needed to make that choice consistent order by order.

A different scheme changes the finite parts of $\delta Z$, $\delta m^2$, and $\delta\lambda$. It does not change the bare Lagrangian or the final physical prediction, if the calculation is done exactly.

## Bare does not mean measured

It is tempting to imagine a bare coupling as the value one would measure with an infinitely powerful microscope. This picture is usually misleading.

In a cutoff calculation, a bare parameter may depend on the cutoff in order to keep a physical observable fixed. For example, a scalar mass parameter can schematically behave like

$$
m_0^2(\Lambda)=m_{\text{phys}}^2-c\lambda\Lambda^2+\cdots,
$$

where the dots include logarithmic and finite terms depending on the scheme and on how the physical mass is defined. This formula is not a statement that an experiment directly observes a huge negative bare mass. It is a relation between a cutoff-dependent parameter and a low-energy definition.

In dimensional regularization, the same relation may involve poles:

$$
m_0^2=Z_{m^2}(\lambda,\epsilon)m^2(\mu).
$$

The pole is not a measured infinity. It is the dimensional-regularization language for local UV sensitivity.

The bare parameter is useful because it is held fixed when defining RG flow:

$$
\left.\mu\frac{d}{d\mu}g_0\right|_{\text{bare}}=0.
$$

But usefulness is not the same as direct observability.

## Renormalized does not mean physical

A renormalized parameter is finite, but finite does not mean physical.

In the $\overline{\mathrm{MS}}$ scheme, a coupling $g(\mu)$ is defined by subtracting pole terms and a standard finite combination involving $\gamma_E$ and $\log4\pi$. That definition is clean and extremely useful, but no detector directly reads out “the $\overline{\mathrm{MS}}$ coupling at $\mu=173\,\mathrm{GeV}$.”

A physical quantity is defined through an observable procedure. Examples include:

$$
\text{pole position of a stable particle propagator},
\qquad
\text{cross section at specified kinematics},
\qquad
\text{decay rate},
\qquad
\text{energy splitting},
\qquad
\text{correlation length}.
$$

Some renormalization schemes are designed to make parameters coincide with physical quantities. In an on-shell scheme, a mass can be defined by the propagator pole and a charge by a particular scattering normalization. Even then, the parameter is physical only because a renormalization condition tied it to an observable.

Other schemes prioritize algebraic simplicity, symmetry, and high-order calculations. Minimal subtraction is usually not the most directly physical scheme, but it is often the most efficient language for RG and EFT.

## Counterterms are not fake interactions

Counterterms are sometimes described as artificial interactions inserted to cancel infinities. That description is not wrong, but it is emotionally unhelpful.

A counterterm is a local operator whose coefficient is chosen so that the renormalized parameter means what the chosen scheme says it means. Since loop diagrams generate local UV-sensitive pieces, the bare Lagrangian must include local coefficients that absorb that sensitivity.

For example, if a loop correction to the two-point function changes the coefficient of $p^2$, then the local operator

$$
\partial_\mu\phi\partial^\mu\phi
$$

must be renormalized. We write this with a field-strength counterterm

$$
\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi.
$$

The split

$$
Z_\phi=1+\delta Z
$$

is conventional. It reflects the choice to normalize the renormalized kinetic term with coefficient $1/2$. Another field rescaling would move factors between $Z_\phi$, couplings, and external-leg conventions.

Counterterms are not new physics added after the fact. They are the local short-distance part of the same regulated theory, expressed in renormalized coordinates.

## What runs and what does not

In renormalized perturbation theory, the bare parameter is independent of the arbitrary scale $\mu$:

$$
\mu\frac{d g_0}{d\mu}=0.
$$

The renormalized parameter $g(\mu)$ changes with $\mu$ so that this remains true:

$$
\beta_g(g)=\left.\mu\frac{dg}{d\mu}\right|_{g_0}.
$$

Thus the renormalized coupling runs. The bare coupling does not run with $\mu$ in this definition.

This does not mean the bare coupling is more physical. It means the bare coupling labels the regulated theory, while $g(\mu)$ is a scale-dependent coordinate used to describe that theory.

A simple one-coupling RG equation is

$$
\mu\frac{dg}{d\mu}=\beta_1 g^2+O(g^3).
$$

To leading order,

$$
\frac{1}{g(\mu_2)}
=\frac{1}{g(\mu_1)}-\beta_1\log\frac{\mu_2}{\mu_1}.
$$

The same physical prediction can be expressed using $g(\mu_1)$ or $g(\mu_2)$, provided the explicit logarithms in the calculation are changed consistently.

## Physical independence of the renormalization scale

Suppose a dimensionless observable depends on a physical scale $Q$, a renormalized coupling $g(\mu)$, and the subtraction scale $\mu$:

$$
F=F\!\left(\frac{Q}{\mu},g(\mu)\right).
$$

The arbitrary scale $\mu$ should not affect the exact observable. Therefore

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta_g\frac{\partial}{\partial g}
\right)F=0
$$

in a simplified massless one-coupling setting.

The first term differentiates explicit $\mu$ dependence, such as logarithms $\log(Q/\mu)$. The second term differentiates implicit $\mu$ dependence through $g(\mu)$.

At finite order in perturbation theory, the cancellation is imperfect because the series has been truncated. The leftover $\mu$ dependence is often used as a rough diagnostic of missing higher-order terms, though it is not a rigorous error bar by itself.

## Bare fields and field normalization

The bare field and the renormalized field are related by

$$
\phi_0=Z_\phi^{1/2}\phi.
$$

This relation is not an observable equation about two particles called “bare $\phi$” and “renormalized $\phi$.” It is a normalization convention for the local field used in correlation functions.

A stable particle mass can be defined by a pole in a two-point function. But the residue of the pole depends on the normalization of the interpolating field. LSZ reduction compensates for this through wavefunction factors, so properly normalized S-matrix elements do not depend on an arbitrary rescaling of $\phi$.

This is why field-strength renormalization is both essential and not directly observable. It is essential because local fields need normalization. It is not directly observable because fields are not themselves detector readouts.

## Fixed bare versus fixed physics

The beta function is defined by varying $\mu$ at fixed bare parameters. This is a mathematical operation inside a regulated description:

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{g_0}.
$$

One can also ask a different question: how must bare parameters change as the cutoff changes while physical long-distance observables are held fixed? That is the Wilsonian continuum-limit question.

These two viewpoints are related but not identical in language:

| Viewpoint | Held fixed | Varied | Flow describes |
|---|---|---|---|
| Renormalized perturbation theory | bare parameters | $\mu$ | scheme dependence of renormalized coordinates |
| Wilsonian cutoff theory | long-distance physics | $\Lambda$ | change of effective action as modes are removed |
| EFT matching | low-energy amplitudes | matching scale and scheme | redistribution between Wilson coefficients and loops |

The danger is to mix sentences from different viewpoints. “The bare coupling does not run” is true in the first row. “Couplings run as the cutoff is lowered” is natural in the second row. They are not contradictory; they are using different flow parameters and different objects.

## Continuum limits and cutoff theories

There are two common meanings of “bare.”

In continuum perturbative renormalization, the bare parameter is a regulator-dependent object used to define a finite renormalized theory. One often formally sends the cutoff to infinity or $\epsilon\to0$ after renormalization.

In a Wilsonian or lattice theory, the bare parameters at a finite cutoff are the microscopic input parameters of the regulated model:

$$
S_a[\phi]=\sum_i g_i(a)\int d^d x\,\mathcal O_i(x).
$$

Here $a$ is a lattice spacing or short-distance resolution. If the lattice is a physical model of a magnet, fluid, or material, the cutoff-scale parameters may be genuine phenomenological parameters. If the lattice is a regulator for a continuum QFT, the continuum limit requires tuning toward a critical surface as $a\to0$.

The same word “bare” therefore appears in two dialects:

| Dialect | Meaning of bare parameter |
|---|---|
| continuum perturbation theory | regulator-dependent parameter held fixed in RG derivatives |
| Wilsonian/lattice model | coupling defined at the microscopic cutoff scale |

Both dialects are useful. Confusing them creates unnecessary philosophy fog.

## Naturalness preview

Scalar masses make the bare-renormalized distinction especially delicate. With a hard cutoff, a scalar mass relation often contains a term schematically like

$$
m_0^2=m_R^2-c\Lambda^2+\cdots.
$$

It is too quick to say, “Bare quantities are unphysical, so there is no naturalness issue.” It is also too quick to say, “A large cutoff term proves fine-tuning in every scheme.”

The Wilsonian naturalness question is about sensitivity of long-distance relevant operators to short-distance input data. In a cutoff theory, relevant operators must often be tuned to keep long-distance scales small compared with the cutoff. That is a physical structural question about RG flow and hierarchies, not merely a complaint about a bad notation for $m_0^2$.

This volume treats naturalness later in its own chapter. For now, the important point is modest: do not build metaphysics on the word “bare.” Ask which quantities are fixed, which scales are physical, and which definition is being used.

## Common pitfalls

**Bare means true.** Not usually. Bare parameters are parameters of a regulated description. They may be useful, but they are not automatically what nature “really chose.”

**Renormalized means measured.** Not automatically. A renormalized parameter is defined by a scheme. It becomes measured only after a renormalization condition or matching prescription ties it to data.

**The counterterm cancels an infinity by magic.** The counterterm is the local coefficient required because the loop generated a local UV-sensitive term. The cancellation enforces a chosen definition of the renormalized parameter.

**The running coupling changes with time.** RG running is dependence on a scale used to describe processes, not time evolution of a coupling in the laboratory.

**Changing $\mu$ changes the physics.** Exact observables do not depend on the arbitrary renormalization scale. Truncated perturbative answers retain residual scale dependence because omitted higher orders would finish the cancellation.

**A field-strength factor is directly observable.** The normalization of a local interpolating field is conventional. Properly defined observables do not depend on arbitrary field rescalings.

## Relations to other pages

[Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/) explains why counterterms have the form of local operators. This page explains how the coefficients of those operators are split into bare pieces, renormalized pieces, and counterterms.

The next pages in this chapter should clarify physical parameters, regulator dependence, and why renormalization is not only a cure for infinities.

Later chapters make the same distinctions more operational: Regularization and Counterterms defines regulators and subtraction terms; Renormalized Perturbation Theory develops schemes and renormalization conditions; Renormalization Group Equations derives running couplings and anomalous dimensions; Wilsonian Renormalization explains cutoff-dependent effective actions; Effective Field Theory explains matching and Wilson coefficients.

## Research status

The distinction between bare, renormalized, and physical quantities is established textbook QFT. The same distinction remains conceptually important in active research because it controls how we interpret scheme dependence, lattice continuum limits, EFT matching, naturalness, gauge-invariant definitions of masses and couplings, and nonperturbative theories without elementary Lagrangian variables.

## Exercises

### Exercise 1: Derive a beta function from a bare coupling

Let a dimensionless coupling in $d=4-\kappa\epsilon$ dimensions satisfy, to one-loop order,

$$
g_0=\mu^{\kappa\epsilon}\left(g+\frac{a g^2}{\epsilon}\right)+O(g^3).
$$

Assuming $g_0$ is independent of $\mu$, show that

$$
\beta_g=-\kappa\epsilon g+\kappa a g^2+O(g^3).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate at fixed $g_0$:

$$
0=\mu\frac{d g_0}{d\mu}
=\kappa\epsilon\mu^{\kappa\epsilon}\left(g+\frac{a g^2}{\epsilon}\right)
+\mu^{\kappa\epsilon}\beta_g\left(1+\frac{2ag}{\epsilon}\right)+O(g^3).
$$

Assume

$$
\beta_g=-\kappa\epsilon g+b g^2+O(g^3).
$$

Substitute this into the previous equation and keep terms through $g^2$:

$$
0=
\kappa\epsilon g+\kappa a g^2
-\kappa\epsilon g
+b g^2
-2\kappa a g^2
+O(g^3).
$$

Thus

$$
b=\kappa a.
$$

Therefore

$$
\beta_g=-\kappa\epsilon g+\kappa a g^2+O(g^3).
$$

For the common convention $d=4-2\epsilon$, one has $\kappa=2$.

</details>

### Exercise 2: Expand the scalar bare Lagrangian

Let

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
Z_\phi=1+\delta Z,
$$

and write the bare scalar Lagrangian as

$$
\mathcal L_0
=\frac12\partial_\mu\phi_0\partial^\mu\phi_0
-\frac12m_0^2\phi_0^2
-\frac{\lambda_0}{4!}\phi_0^4.
$$

Show schematically how counterterms for the kinetic term, mass term, and quartic term appear.

<details><summary><strong>Solution</strong></summary>

Substituting $\phi_0=Z_\phi^{1/2}\phi$ gives

$$
\mathcal L_0
=\frac12Z_\phi\partial_\mu\phi\partial^\mu\phi
-\frac12m_0^2Z_\phi\phi^2
-\frac{\lambda_0Z_\phi^2}{4!}\phi^4.
$$

Now choose renormalized parameters so that

$$
m_0^2Z_\phi=m^2+\delta m^2,
\qquad
\lambda_0Z_\phi^2=\lambda+\delta\lambda
$$

with any necessary powers of $\mu$ understood in dimensional regularization. Then

$$
\mathcal L_0
=\left[\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4\right]
+
\left[\frac12\delta Z\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4\right].
$$

The first bracket is the renormalized Lagrangian and the second bracket is the counterterm Lagrangian.

</details>

### Exercise 3: Why changing the scale does not change the observable

Suppose a dimensionless observable is

$$
F(Q,\mu,g)=g(\mu)+b g(\mu)^2\log\frac{Q}{\mu}+O(g^3),
$$

and the beta function is

$$
\beta_g=\beta_1g^2+O(g^3).
$$

Find the condition on $b$ for $F$ to be independent of $\mu$ through order $g^2$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\left(\mu\frac{\partial}{\partial\mu}+\beta_g\frac{\partial}{\partial g}\right)F=0+O(g^3).
$$

The explicit derivative gives

$$
\mu\frac{\partial F}{\partial\mu}
=-b g^2+O(g^3),
$$

because

$$
\mu\frac{\partial}{\partial\mu}\log\frac{Q}{\mu}=-1.
$$

The implicit derivative gives

$$
\beta_g\frac{\partial F}{\partial g}
=\beta_1g^2(1+O(g))
=\beta_1g^2+O(g^3).
$$

Thus scale independence through order $g^2$ requires

$$
-b+\beta_1=0,
$$

or

$$
b=\beta_1.
$$

The explicit logarithm and the running coupling cancel each other's $\mu$ dependence.

</details>

### Exercise 4: Scheme change and the first beta coefficient

Let two renormalized couplings be related by a finite redefinition

$$
g'=g+c g^2+O(g^3),
$$

and suppose

$$
\beta_g=b_1g^2+O(g^3).
$$

Show that the leading beta-function coefficient is unchanged in the primed scheme.

<details><summary><strong>Solution</strong></summary>

The beta function transforms as

$$
\beta_{g'}=\frac{dg'}{dg}\beta_g.
$$

Since

$$
\frac{dg'}{dg}=1+2cg+O(g^2),
$$

we find

$$
\beta_{g'}=(1+2cg+O(g^2))(b_1g^2+O(g^3))
=b_1g^2+O(g^3).
$$

To express the result in terms of $g'$, invert the redefinition:

$$
g=g'+O(g'^2).
$$

Therefore

$$
\beta_{g'}=b_1g'^2+O(g'^3).
$$

The leading coefficient is unchanged. Higher coefficients can depend on the allowed form of the scheme change and on the class of schemes being compared.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Renormalization and Symmetry" and "Dilatations."
- Mark Srednicki, *Quantum Field Theory*, especially sections on renormalization schemes, the renormalization group, and effective field theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization and RG.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 2–3.

## Version history

- 2026-06-16: First polished draft. Added conceptual separation between bare parameters, renormalized parameters, counterterms, running couplings, physical observables, Wilsonian cutoff couplings, and scheme dependence.
