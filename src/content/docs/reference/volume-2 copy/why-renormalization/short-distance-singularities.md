---
title: "Short-Distance Singularities"
description: "Why local quantum fields become singular at coincident points, and why ultraviolet divergences are the momentum-space form of the same fact."
sidebar:
  label: "Short-Distance Singularities"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§13–18 and 27–29; Coleman, Dilatations; Weinberg Vol. I ch. 12; Schwartz chs. 15–23; Zinn-Justin, renormalization and short-distance expansion chapters."
topics:
  - short-distance singularities
  - ultraviolet divergences
  - operator-valued distributions
  - composite operators
  - point splitting
  - operator product expansion
canonicalTopics:
  - ultraviolet-divergence
  - short-distance-singularity
  - composite-operator-renormalization
  - operator-product-expansion
researchStatus:
  established:
    - "Local quantum fields are singular as operator-valued distributions, and coincident products require a definition or renormalization."
  active:
    - "The same basic issue has refined modern forms in rigorous QFT, curved-spacetime QFT, defect QFT, generalized symmetries, and nonperturbative CFT."
---

## Summary

The first reason renormalization appears is brutally simple: **local quantum fields are too singular to multiply at the same point without further definition**.

A free scalar field already shows the problem. In Euclidean signature, the two-point function in $d$ spacetime dimensions is

$$
G_E(x)
=\int\frac{d^d p}{(2\pi)^d}\frac{e^{ip\cdot x}}{p^2+m^2}.
$$

At distances much shorter than the Compton wavelength, $|x|\ll m^{-1}$, its leading behavior for $d>2$ is

$$
G_E(x)
\sim
\frac{\Gamma(d/2-1)}{4\pi^{d/2}}\frac{1}{|x|^{d-2}}.
$$

In four dimensions this becomes

$$
G_E(x)\sim \frac{1}{4\pi^2 x^2}.
$$

So the limit $x\to0$ is not a harmless value of an ordinary function. It is singular. Loop ultraviolet divergences are the momentum-space shadow of this same short-distance singularity.

The conceptual chain is

$$
\text{local fields}
\longrightarrow
\text{singular coincident products}
\longrightarrow
\text{UV-sensitive loop integrals}
\longrightarrow
\text{renormalized local operators and parameters}.
$$

:::note[The key mental switch]
Do not think of a quantum field $\phi(x)$ as an ordinary random variable attached to a point. A local field is an operator-valued distribution. It becomes an honest operator only after smearing against a suitable test function.
:::

## Prerequisites

You should know the volume [Conventions and Notation](/renormalization-rg-eft/conventions/) and the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/). It helps to know the Feynman propagator and basic Fourier-transform conventions, but the main point of this page is conceptual rather than computational.

The Euclidean formulas below are used only to display short-distance behavior cleanly. Lorentzian correlation functions have additional $i\epsilon$ and time-ordering structure, but the ultraviolet singularity is the same local issue.

## Core idea

In classical field theory, one often writes expressions such as

$$
\phi(x)^2,
\qquad
\phi(x)^4,
\qquad
\partial_\mu\phi(x)\partial^\mu\phi(x)
$$

as if a field were simply a function. In quantum field theory this notation is useful, but it hides a warning label. Quantum fields fluctuate at arbitrarily short wavelengths unless a regulator or microscopic completion cuts them off. Because of those fluctuations, the product of fields at the same point is generally singular.

A safer expression is a smeared field,

$$
\phi(f)=\int d^d x\,f(x)\phi(x),
$$

where $f(x)$ is a smooth function of compact support or otherwise sufficiently well behaved. The smearing has a physical interpretation: no measurement resolves an exact mathematical point. The sharper the smearing, the more ultraviolet fluctuations the observable samples.

The singularity is not a mistake made by perturbation theory. It is already present in the free theory. Interactions make the bookkeeping harder, but they do not invent the basic problem.

## Setup and conventions

We use the mostly-minus Lorentzian convention of the site, but this page mostly displays Euclidean short-distance formulas. The Euclidean scalar propagator is

$$
G_E(x)=\int\frac{d^d p}{(2\pi)^d}\frac{e^{ip\cdot x}}{p^2+m^2}.
$$

The ultraviolet region is the large-momentum region $|p|\to\infty$. The corresponding position-space limit is the short-distance limit $x\to0$. These are Fourier-dual ways of seeing the same physics.

We write $\Lambda$ for a hard UV cutoff when one is useful, and $\mu$ for a renormalization scale. A cutoff $\Lambda$ controls which short wavelengths are explicitly present. A renormalization scale $\mu$ labels a subtraction convention. They are not the same object.

## The free scalar already diverges

Set $m=0$ for the leading short-distance behavior. For $d>2$,

$$
G_E(x)
=\int\frac{d^d p}{(2\pi)^d}\frac{e^{ip\cdot x}}{p^2}
=\frac{\Gamma(d/2-1)}{4\pi^{d/2}}\frac{1}{|x|^{d-2}}.
$$

This formula is one of the cleanest places to see why QFT is not quantum mechanics with infinitely many ordinary variables. As $x\to0$, the correlation function diverges. The vacuum fluctuation

$$
\langle0|\phi(x)^2|0\rangle
$$

would require evaluating $G_E(0)$, which is not finite.

With a hard cutoff in four Euclidean dimensions,

$$
G_{E,\Lambda}(0)
=\int_{|p|<\Lambda}\frac{d^4p}{(2\pi)^4}\frac{1}{p^2+m^2}
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2+m^2}{m^2}
\right].
$$

The leading term grows like $\Lambda^2$. The logarithmic term remembers the mass scale. If one uses dimensional regularization instead, the same object is expressed in a different dialect, with poles and logarithms rather than an explicit power of a hard cutoff.

The lesson is not that the cutoff formula is more real. The lesson is that coincident local products ask the theory for arbitrarily short-distance information.

## Fields are distributions, not point observables

The phrase “operator-valued distribution” sounds like a legal disclaimer, but it is a useful one. A distribution is not defined by its value at a point. It is defined by how it acts under integration against smooth test functions.

The basic two-point function is therefore best thought of as a distribution $G(x-y)$ satisfying

$$
(-\partial^2+m^2)G_E(x-y)=\delta^{(d)}(x-y)
$$

in Euclidean signature. Its singularity at $x=y$ is precisely what allows it to be the inverse of a differential operator.

This is why expressions such as $\delta^{(d)}(0)$ or $G(0)$ are not mysterious new physical constants. They are warnings that we tried to evaluate a distribution outside its domain of definition.

Smearing makes this explicit. Define

$$
\phi(f)=\int d^d x\,f(x)\phi(x).
$$

Then

$$
\langle \phi(f)\phi(f)\rangle
=\int d^d x\,d^d y\,f(x)G_E(x-y)f(y).
$$

For smooth $f$, this can be finite even though $G_E(x-y)$ is singular at $x=y$. But if $f$ becomes sharply localized, the integral increasingly probes the singularity.

## Composite operators need definitions

A composite operator is an operator built from products of fields at the same point, for example

$$
\phi^2(x),
\qquad
\phi^4(x),
\qquad
T_{\mu\nu}(x),
\qquad
\bar\psi(x)\gamma^\mu\psi(x).
$$

The notation is indispensable, but the definition is not automatic. In a free scalar theory, a simple point-splitting definition of the renormalized operator $\phi^2$ is

$$
[\phi^2]_R(x)
=\lim_{y\to x}
\left[
\phi(x)\phi(y)-G_{\text{sing}}(x-y)
\right],
$$

where $G_{\text{sing}}$ is the singular part of the two-point function in the chosen convention. In four Euclidean dimensions, the leading subtraction contains

$$
G_{\text{sing}}(x-y)\sim \frac{1}{4\pi^2|x-y|^2}.
$$

This formula is schematic as an operator definition, but it captures the idea: define the product at the same point by first separating the points, subtracting the universal singular part, and then taking the limit.

In interacting theories the situation becomes richer. Composite operators can mix:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Operators with the same symmetries and compatible dimensions can appear in the renormalization of one another. The singularity has structure; it is not just “subtract infinity and hope.”

## Singularities become local terms

Why does this matter for renormalization of Lagrangians? Because the Lagrangian itself is built from local composite operators.

For example, in scalar theory one writes

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

Each term is local. When loop corrections force us to define or redefine these local products, the necessary changes also take the form of local operators:

$$
\delta\mathcal L
=\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4+\cdots.
$$

The ellipsis may include higher-dimension operators such as $\phi^6$, $(\partial\phi)^2\phi^2$, or $\partial^2\phi\partial^2\phi$, depending on the theory and the desired accuracy.

This is the first hint of the EFT viewpoint. If short-distance physics is not resolved, its low-energy imprint is captured by local operators consistent with the symmetries.

## Momentum-space version: ultraviolet divergences

The same singularity can be seen in momentum space. The short-distance limit $x\to0$ corresponds to integrating over arbitrarily large momenta. For example,

$$
G_E(0)=\int\frac{d^d p}{(2\pi)^d}\frac{1}{p^2+m^2}.
$$

At large $p$, the integrand behaves as $1/p^2$. In $d$ dimensions the measure contributes $p^{d-1}dp$, so the large-$p$ behavior is

$$
\int^\infty dp\,p^{d-3}.
$$

This diverges for $d\ge2$ and logarithmically at $d=2$ in the massless counting. In four dimensions it diverges quadratically with a hard cutoff.

Loop diagrams are more elaborate versions of the same phenomenon. Internal loop momenta are not fixed by external kinematics. If the integral samples arbitrarily large internal momenta, the result can depend on how the theory is defined at short distances.

The next page explains the crucial extra fact: **because the underlying theory is local, the ultraviolet-sensitive part of a loop is local in the external fields**.

## Two dimensions and logarithms

In $d=2$, the massless scalar two-point function is logarithmic rather than power-law:

$$
G_E(x)\sim -\frac{1}{2\pi}\log(\mu |x|).
$$

The scale $\mu$ appears because the logarithm needs a dimensionless argument. This is a tiny preview of renormalization-group thinking: once logarithms appear, a reference scale must be chosen, and changing that scale changes the parameters used to describe the same physics.

Logarithms are especially important because they are the perturbative footprints of scale dependence. A logarithm such as

$$
\log\frac{Q^2}{\mu^2}
$$

is harmless at one fixed scale but becomes large when widely separated scales are present. Renormalization group equations are the systematic response to this problem.

## The operator product viewpoint

The operator product expansion packages short-distance singularities into a powerful local statement. As $x\to0$,

$$
\mathcal O_A(x)\mathcal O_B(0)
\sim
\sum_C C_{AB}{}^C(x,\mu)\,\mathcal O_C(0,\mu).
$$

The coefficient functions $C_{AB}{}^C$ contain the short-distance singular dependence on $x$. The operators $\mathcal O_C$ are local operators at the expansion point. This formula says that when two local probes approach each other, their product can be replaced, inside correlation functions, by a sum of local probes.

This is the cleanest conceptual bridge from short-distance singularities to renormalization. The singularity is not arbitrary. It is organized by local operators and constrained by symmetries.

For a free scalar in four dimensions, Wick's theorem gives a simple example:

$$
\phi(x)\phi(0)
=G_E(x)\mathbf 1+{:}\phi(x)\phi(0){:}.
$$

As $x\to0$,

$$
\phi(x)\phi(0)
\sim
\frac{1}{4\pi^2x^2}\mathbf 1
+[\phi^2](0)+x^\mu[\phi\partial_\mu\phi](0)+\cdots.
$$

The identity operator carries the leading singular coefficient. Less singular terms define or involve local composite operators.

## What is universal and what is not

The leading short-distance structure is often highly constrained. In a free massless theory, the coefficient of $1/x^{d-2}$ is fixed by normalization. In an interacting theory near a fixed point, two-point functions behave like

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac{C}{|x|^{2\Delta}},
$$

where $\Delta$ is the full scaling dimension. The exponent is physical at a fixed point.

Away from fixed points, the detailed subtraction of singular terms depends on scheme. A point-splitting subtraction, a hard cutoff, dimensional regularization, and a lattice regulator can assign different finite parts to the same composite operator. This is not a contradiction. It means that defining a local composite operator requires a convention, and different conventions are related by local redefinitions.

For example, two definitions of $[\phi^2]_R$ can differ by a multiple of the identity and, in interacting theories, by other local operators with the same quantum numbers:

$$
[\phi^2]'_R=[\phi^2]_R+a(\mu)\mathbf1+b(\mu)m^2\mathbf1+\cdots.
$$

Physical predictions are obtained only after the operator definition and its coefficient in the action or observable are specified together.

## Common pitfalls

**Treating fields as ordinary functions.** The notation $\phi(x)$ is compact, but local quantum fields are distributions. Coincident products require definitions.

**Thinking divergences require interactions.** Free fields already have singular two-point functions at coincident points. Interactions turn this into a systematic renormalization problem.

**Confusing UV and IR singularities.** Short-distance singularities are ultraviolet. Long-distance or massless singularities are infrared. They can coexist, especially in massless theories, but they have different meanings.

**Believing normal ordering solves renormalization.** Normal ordering removes some contractions in some free-field-based schemes. It does not by itself define all composite operators in all interacting theories or preserve every desired symmetry.

**Thinking the subtraction is unique.** Local finite counterterms are part of the definition of a scheme. The non-uniqueness is not a bug; it is the reason renormalized parameters and operator normalizations must be stated.

**Interpreting the cutoff as automatically physical.** A cutoff can represent microscopic physics, as in a lattice model, or it can be only a regulator. The interpretation depends on the problem.

## Relations to other pages

This page explains why short-distance singularities exist. [Loops and Locality](/renormalization-rg-eft/why-renormalization/loops-and-locality/) explains why loop divergences generated by those singularities are local in the external fields.

The Regularization and Counterterms chapter turns this conceptual point into concrete schemes. Renormalized Perturbation Theory explains how counterterms enter diagrams and renormalization conditions. The Local Operators and OPE chapter develops composite-operator renormalization, operator mixing, anomalous dimensions, and the OPE in more detail.

For calculation technology, compare this page with the Perturbative QFT pages on loop expansion, dimensional regularization, one-loop integrals, and counterterm insertions. Those pages evaluate the integrals; this page explains why the singularities are there before the machinery begins.

## Research status

The basic statement that local quantum fields have singular short-distance products is established. It is one of the structural facts behind perturbative renormalization, composite-operator renormalization, OPEs, and Wilsonian EFT.

Active and more refined versions appear in several places: rigorous construction of operator products, curved-spacetime renormalization of composite operators such as $T_{\mu\nu}$, defect and boundary operator expansions, nonperturbative CFT definitions of local operator algebras, and algebraic descriptions of local observables. The graduate-level message on this page is stable; the frontier is in making the same message precise in increasingly general settings.

## Exercises

### Exercise 1: Short-distance behavior of the massless scalar

Use the standard Fourier transform

$$
\int\frac{d^d p}{(2\pi)^d}\frac{e^{ip\cdot x}}{p^2}
=\frac{\Gamma(d/2-1)}{4\pi^{d/2}}\frac{1}{|x|^{d-2}}
$$

for $d>2$. Verify the four-dimensional result.

<details><summary><strong>Solution</strong></summary>

Set $d=4$. Then

$$
\Gamma(d/2-1)=\Gamma(1)=1,
\qquad
4\pi^{d/2}=4\pi^2,
\qquad
|x|^{d-2}=|x|^2.
$$

Therefore

$$
G_E(x)=\frac{1}{4\pi^2x^2}.
$$

The divergence as $x\to0$ is the short-distance singularity of the four-dimensional scalar field.

</details>

### Exercise 2: Cutoff dependence of the coincident propagator

Show that

$$
\int_{|p|<\Lambda}\frac{d^4p}{(2\pi)^4}\frac{1}{p^2+m^2}
=\frac{1}{16\pi^2}
\left[
\Lambda^2-m^2\log\frac{\Lambda^2+m^2}{m^2}
\right].
$$

<details><summary><strong>Solution</strong></summary>

In four Euclidean dimensions, the angular volume of the unit three-sphere is $2\pi^2$. Thus

$$
\int_{|p|<\Lambda}\frac{d^4p}{(2\pi)^4}\frac{1}{p^2+m^2}
=\frac{2\pi^2}{(2\pi)^4}\int_0^\Lambda dp\,\frac{p^3}{p^2+m^2}.
$$

The radial integral is

$$
\int_0^\Lambda dp\,\frac{p^3}{p^2+m^2}
=\frac12\int_0^{\Lambda^2}du\,\frac{u}{u+m^2}
=\frac12\left[\Lambda^2-m^2\log\frac{\Lambda^2+m^2}{m^2}\right].
$$

Since

$$
\frac{2\pi^2}{(2\pi)^4}\cdot\frac12=\frac{1}{16\pi^2},
$$

the stated formula follows.

</details>

### Exercise 3: Why smearing helps

Let $G_E(x)\sim 1/(4\pi^2x^2)$ in four dimensions. Explain why

$$
\int d^4x\,d^4y\,f(x)G_E(x-y)f(y)
$$

can be finite for smooth $f$, even though $G_E(0)$ is divergent.

<details><summary><strong>Solution</strong></summary>

Near $x=y$, write $r=|x-y|$. The singular part behaves like $1/r^2$. The four-dimensional relative volume element behaves like $r^3dr$ times an angular measure. Therefore the local integral near coincidence behaves like

$$
\int_0^{\delta}dr\,r^3\frac{1}{r^2}
=\int_0^{\delta}dr\,r,
$$

which is finite. The distribution is singular at a point, but it can still be integrated against smooth test functions. Trying to evaluate $G_E(0)$ is different: it asks for a point value that the distribution does not possess.

</details>

### Exercise 4: A first OPE from Wick's theorem

For a free scalar, use Wick's theorem to show schematically that

$$
\phi(x)\phi(0)
\sim G_E(x)\mathbf1+[\phi^2](0)+\cdots
$$

as $x\to0$.

<details><summary><strong>Solution</strong></summary>

Wick's theorem gives

$$
\phi(x)\phi(0)=\langle\phi(x)\phi(0)\rangle\mathbf1+{:}\phi(x)\phi(0){:}.
$$

The first term is $G_E(x)\mathbf1$ and contains the singular coefficient. For the normal-ordered part, expand the separated field around the origin:

$$
\phi(x)=\phi(0)+x^\mu\partial_\mu\phi(0)+\frac12x^\mu x^\nu\partial_\mu\partial_\nu\phi(0)+\cdots.
$$

Then

$$
{:}\phi(x)\phi(0){:}
= {:}\phi^2(0){:}+x^\mu{:}\partial_\mu\phi(0)\phi(0){:}+\cdots.
$$

This is the free-field prototype of the OPE: singular coefficient functions multiplying local operators.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Dilatations,” for the connection between short-distance scaling, anomalous dimensions, and the Callan–Symanzik viewpoint.
- Mark Srednicki, *Quantum Field Theory*, especially the chapters on exact propagators, loop corrections, renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the renormalization chapters and the discussion of nonrenormalizable theories.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for a systematic account of renormalization and the modern EFT interpretation.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the discussion of renormalization, composite operators, and short-distance expansions.
- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200, for the Wilsonian relation between critical phenomena, field theory, and scale-dependent descriptions.

## Version history

- 2026-06-16: First polished draft. Introduced coincident singularities, fields as distributions, point splitting, cutoff behavior, composite operators, and the OPE viewpoint.
