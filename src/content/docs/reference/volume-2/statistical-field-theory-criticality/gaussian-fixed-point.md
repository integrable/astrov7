---
title: "Gaussian Fixed Point"
description: "The free-field fixed point as the organizing center for engineering dimensions, mean-field criticality, and the upper critical dimension."
sidebar:
  label: "Gaussian Fixed Point"
  order: 5
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974, §§3–5 and 10–12; Zinn-Justin 2021, critical phenomena chapters; Coleman 1985, Dilatations; Schwartz 2014, chs. 21–23; Altland and Simons 2023, ch. 6."
topics:
  - Gaussian fixed point
  - free field theory
  - engineering dimensions
  - mean-field criticality
  - upper critical dimension
  - relevant operators
canonicalTopics:
  - gaussian-fixed-point
  - engineering-dimensions
  - mean-field-criticality
  - upper-critical-dimension
researchStatus:
  established:
    - "The Gaussian fixed point is exactly solvable and controls free-field scaling, perturbative RG near upper critical dimensions, and mean-field critical behavior above the upper critical dimension."
  active:
    - "Modern work still uses Gaussian fixed points as controlled endpoints for long-range interactions, disorder, Lifshitz points, multicritical theories, functional RG truncations, and bootstrap perturbation theory."
---

## Summary

The **Gaussian fixed point** is the free-field fixed point. For a scalar order parameter in Euclidean statistical notation it is described by

$$
S_*[\phi]=\frac12\int d^d x\,(\nabla\phi)^2,
$$

or, for an $O(N)$ order parameter,

$$
S_*[\boldsymbol\phi]
=\frac12\int d^d x\,\partial_i\phi^a\partial_i\phi^a,
\qquad a=1,\ldots,N.
$$

At this fixed point, correlation functions are exactly computable. The momentum-space two-point function is

$$
\langle \phi^a(p)\phi^b(-p)\rangle_*=\frac{\delta^{ab}}{p^2},
$$

and the field has scaling dimension

$$
\Delta_\phi^{(0)}=\frac{d-2}{2}.
$$

The Gaussian fixed point is not merely the boring theory with no interactions. It is the reference point from which one reads off engineering dimensions, relevant and irrelevant perturbations, the upper critical dimension of $\phi^4$ theory, the origin of mean-field exponents, and the first step in the epsilon expansion.

:::note[Why the Gaussian fixed point matters]
A free theory can be a fixed point of a nontrivial RG flow. It can control universal behavior near criticality, organize perturbation theory, and determine which interactions are worth keeping. “Free” does not mean “physically irrelevant.”
:::

## Prerequisites

You should know [Landau–Ginzburg Theory](/renormalization-rg-eft/statistical-field-theory-criticality/landau-ginzburg-theory/), [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/). The companion page [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/) explains how the Gaussian fixed point is deformed into an interacting fixed point below four dimensions.

## Core idea

A fixed point is scale invariant. The Gaussian fixed point is the simplest one because the action is quadratic. The path integral is a Gaussian integral, all higher correlation functions follow from Wick's theorem, and the scaling dimensions of composite operators are obtained by adding the dimensions of fields and derivatives.

For the critical scalar theory,

$$
S_*[\phi]=\frac12\int d^d x\,(\nabla\phi)^2,
$$

the rescaling

$$
x\to b x
$$

leaves the action invariant if

$$
\phi(x)\to b^{-\Delta_\phi^{(0)}}\phi(b^{-1}x),
\qquad
\Delta_\phi^{(0)}=\frac{d-2}{2}.
$$

Once this number is known, every local perturbation can be power-counted. If the action is perturbed by

$$
\delta S=g_i\int d^d x\,\mathcal O_i(x),
$$

then the engineering RG eigenvalue of $g_i$ at the Gaussian fixed point is

$$
y_i=d-\Delta_i^{(0)}.
$$

Relevant perturbations have $y_i>0$, irrelevant perturbations have $y_i<0$, and marginal perturbations have $y_i=0$. At the Gaussian fixed point, this is just dimensional analysis. The magic is that dimensional analysis becomes the first approximation to RG geometry.

## Setup and conventions

This page uses Euclidean statistical-field-theory notation,

$$
Z=\int\mathcal D\phi\,e^{-S[\phi]}.
$$

The critical Gaussian action is massless. A mass deformation is written as

$$
\delta S_r=\frac12 r\int d^d x\,\phi^2.
$$

For thermal critical phenomena, $r$ is proportional to the distance from the critical temperature after nonuniversal normalization:

$$
r\propto T-T_c.
$$

For an $O(N)$ theory, replace $\phi^2$ by $\boldsymbol\phi^2=\phi^a\phi^a$ and impose $O(N)$ invariance unless a symmetry-breaking perturbation is explicitly introduced.

We use the statistical convention

$$
\epsilon=4-d
$$

when discussing the upper critical dimension. This is not the same convention as high-energy dimensional regularization with $d=4-2\epsilon$.

## The exact two-point function

In momentum space, the Gaussian action is

$$
S_*[\phi]=\frac12\int\frac{d^d p}{(2\pi)^d}\,p^2\phi(p)\phi(-p).
$$

The inverse of the quadratic kernel is the propagator:

$$
G(p)=\frac{1}{p^2}.
$$

Fourier transforming gives, for $d>2$,

$$
G(x)=\langle\phi(x)\phi(0)\rangle_*
=\frac{\Gamma(d/2-1)}{4\pi^{d/2}}\frac{1}{|x|^{d-2}}.
$$

A scalar primary-like two-point function at a scale-invariant point has the form

$$
\langle\phi(x)\phi(0)\rangle\sim \frac{1}{|x|^{2\Delta_\phi}}.
$$

Therefore the Gaussian field dimension is

$$
2\Delta_\phi^{(0)}=d-2,
\qquad
\Delta_\phi^{(0)}=\frac{d-2}{2}.
$$

The anomalous dimension at the Gaussian fixed point is zero:

$$
\eta=0.
$$

This statement is exact at the fixed point. Interactions can change it only by moving to a different fixed point.

## Wick theorem and composite operators

Because the theory is Gaussian, all correlation functions are generated from the two-point function. For example,

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle_*
=G_{12}G_{34}+G_{13}G_{24}+G_{14}G_{23},
$$

where

$$
G_{ij}=G(x_i-x_j).
$$

Composite operators are subtler than products of fields at the same point, because coincident fields require renormalization. For engineering power counting, however, one starts with the free-field dimensions:

$$
\Delta_{\partial^k\phi^n}^{(0)}=k+n\frac{d-2}{2},
$$

before subtracting descendants, total derivatives, equations-of-motion operators, and trace pieces.

Some important scalar perturbations in a $Z_2$-symmetric one-component theory are:

| Operator | Gaussian dimension | Coupling eigenvalue $y=d-\Delta$ | Interpretation |
|---|---:|---:|---|
| $\phi$ | $(d-2)/2$ | $(d+2)/2$ | magnetic field perturbation |
| $\phi^2$ | $d-2$ | $2$ | temperature or mass perturbation |
| $\phi^4$ | $2(d-2)$ | $4-d$ | interaction stabilizing the order parameter |
| $\phi^6$ | $3(d-2)$ | $6-2d$ | leading higher even potential term |
| $(\nabla\phi)^2$ | $d$ | $0$ | redundant normalization of the kinetic term |

The row for $(\nabla\phi)^2$ deserves care. Changing its coefficient is usually a field normalization choice, not a new physical scaling direction. In a properly reduced theory space, one fixes the kinetic normalization or quotients by redundant directions.

## Relevant perturbations and the critical surface

The mass deformation

$$
\frac12 r\int d^d x\,\phi^2
$$

has eigenvalue

$$
y_t=2.
$$

Under infrared coarse graining with scale factor $b$,

$$
r(b)=b^2 r.
$$

Thus $r$ is relevant. To stay at the critical point, one must tune it to zero. In a microscopic system, this tuning is the adjustment of temperature to $T_c$.

The correlation length exponent at the Gaussian fixed point is therefore

$$
\nu_{\text{G}}=\frac{1}{y_t}=\frac12.
$$

This is the origin of the mean-field value $\nu=1/2$. It is not guessed from a polynomial potential; it is the inverse RG eigenvalue of the relevant temperature perturbation.

The magnetic field $h$ couples to $\phi$:

$$
\delta S_h=-h\int d^d x\,\phi.
$$

Its eigenvalue is

$$
y_h=d-\Delta_\phi^{(0)}=\frac{d+2}{2}.
$$

This determines how external fields scale near the Gaussian critical point.

## Upper critical dimension

The quartic coupling has eigenvalue

$$
y_u=4-d.
$$

Thus:

| Dimension | Status of $\phi^4$ at the Gaussian fixed point | Consequence |
|---:|---|---|
| $d>4$ | irrelevant | Gaussian fixed point controls leading critical behavior. |
| $d=4$ | marginal | logarithmic corrections appear. |
| $d<4$ | relevant | the Gaussian fixed point is unstable toward an interacting fixed point. |

This is why $d_c=4$ is the **upper critical dimension** of short-range scalar $\phi^4$ theory.

Above four dimensions, the Gaussian fixed point controls the critical exponents associated with the disordered critical point. Below four dimensions, the quartic interaction grows under infrared RG and drives the theory toward the Wilson–Fisher fixed point. At exactly four dimensions, the quartic coupling is marginally irrelevant for positive coupling, producing mean-field exponents dressed by logarithms.

## Gaussian fixed point versus mean-field theory

Mean-field theory and the Gaussian fixed point are closely related but not identical.

The Gaussian fixed point is the free critical theory. It gives

$$
\eta=0,
\qquad
\nu=\frac12,
$$

and it supplies engineering dimensions.

Mean-field theory also uses the quartic term

$$
\frac{u}{4!}\phi^4
$$

to stabilize the ordered phase. Above four dimensions, $u$ is irrelevant at the Gaussian fixed point, but it is **dangerously irrelevant** for thermodynamic quantities in the ordered phase. Setting $u=0$ would make the potential unstable when $r<0$. Keeping $u$ gives the mean-field order parameter

$$
|m|\sim \left(\frac{-r}{u}\right)^{1/2},
$$

and hence

$$
\beta_{\text{mag,MF}}=\frac12,
\qquad
\delta_{\text{MF}}=3.
$$

This is why a naive application of hyperscaling to the Gaussian fixed point gives the wrong thermodynamic exponent above the upper critical dimension. Hyperscaling assumes that the singular free energy is controlled only by the correlation length. Above $d_c$, the dangerously irrelevant quartic coupling also enters.

## The Gaussian model as a fixed point, not just a model

A common mistake is to think of the Gaussian theory as merely an exactly soluble example. In RG language it is a point in theory space. Nearby theories are obtained by adding all local perturbations compatible with the symmetries:

$$
S=S_*+\frac12 r\int d^d x\,\phi^2+\frac{u}{4!}\int d^d x\,\phi^4+\frac{v}{6!}\int d^d x\,\phi^6+\frac12 c_4\int d^d x\,(\nabla^2\phi)^2+\cdots.
$$

The Gaussian fixed point tells us which of these perturbations grow and which fade under coarse graining. It is therefore a local coordinate chart on theory space.

This is the logic behind perturbative RG near upper critical dimensions. When an operator is exactly marginal at the Gaussian fixed point, moving slightly away from the dimension where it is marginal makes it weakly relevant or weakly irrelevant. The resulting interacting fixed point can then be studied in powers of the small parameter. The Wilson–Fisher fixed point is the archetype:

$$
d=4-\epsilon,
\qquad
[\phi^4]=d-\epsilon,
\qquad
g_*=O(\epsilon).
$$

## Gaussian exponents and their domain

The Gaussian fixed point gives the following leading critical exponents when it controls the transition:

| Exponent | Gaussian or mean-field value | Origin |
|---|---:|---|
| $\eta$ | $0$ | free propagator $G(p)=1/p^2$ |
| $\nu$ | $1/2$ | mass eigenvalue $y_t=2$ |
| $\gamma$ | $1$ | susceptibility $\chi\sim 1/r$ |
| $\beta_{\text{mag}}$ | $1/2$ | Landau saddle with stabilizing $u\phi^4$ |
| $\delta$ | $3$ | critical isotherm $h\sim u m^3$ |

The first two are directly fixed by the Gaussian critical theory. The last two require the quartic stabilizer and therefore know about dangerous irrelevance above four dimensions.

In dimensions $d>4$, these values are the leading critical exponents for short-range scalar transitions, though finite-size scaling and thermodynamic singularities require care. In $d=4$, logarithmic corrections modify pure power laws. In $d<4$, the Wilson–Fisher fixed point replaces the Gaussian fixed point as the infrared critical theory for the ordinary short-range Ising and $O(N)$ universality classes.

## Common pitfalls

**Thinking Gaussian means no fluctuations.** The Gaussian path integral includes fluctuations exactly. What it lacks are interactions among fluctuations.

**Confusing the Gaussian fixed point with the ordered-phase saddle.** The fixed point is massless and scale invariant. Mean-field ordered phases require a relevant mass deformation and a stabilizing quartic term.

**Applying hyperscaling blindly above four dimensions.** Hyperscaling fails above the upper critical dimension because the quartic coupling is dangerously irrelevant.

**Saying irrelevant means unimportant.** Irrelevant operators fade near the fixed point for many long-distance observables, but they can control stability, amplitudes, finite-size effects, and ordered-phase scaling.

**Using Gaussian dimensions at the Wilson–Fisher fixed point.** Below four dimensions, the interacting fixed point changes scaling dimensions. Gaussian power counting is the starting point, not the final answer.

## Relations to other pages

This page sits between [Mean-Field Theory](/renormalization-rg-eft/statistical-field-theory-criticality/mean-field-theory/) and [Wilson–Fisher in Epsilon Expansion](/renormalization-rg-eft/statistical-field-theory-criticality/wilson-fisher-in-epsilon-expansion/). It also connects back to [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/), [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), and [Crossover and Dangerously Irrelevant Operators](/renormalization-rg-eft/fixed-points-critical-phenomena/crossover-and-dangerously-irrelevant-operators/).

Later pages on [Correlation Length](/renormalization-rg-eft/statistical-field-theory-criticality/correlation-length/) and [Finite-Size Scaling](/renormalization-rg-eft/statistical-field-theory-criticality/finite-size-scaling/) will explain how Gaussian and non-Gaussian fixed points control scaling windows in finite systems.

## Research status

The Gaussian fixed point is fully understood as an exactly solvable fixed point. Its modern role is not in doubt. What remains active is the use of Gaussian fixed points as starting points for controlled expansions: epsilon expansions, large-$N$ expansions, long-range interaction expansions, Lifshitz fixed points, multicritical theories, disordered systems, nonequilibrium criticality, and perturbative bootstrap constructions.

The main caution is conceptual rather than technical: the Gaussian fixed point is exact, but its domain of attraction depends on dimension, symmetry, locality, range of interactions, disorder, conservation laws, and dynamical universality class.

## Exercises

### Exercise 1: Field dimension from scale invariance

Show that the Gaussian action

$$
S_*[\phi]=\frac12\int d^d x\,(\nabla\phi)^2
$$

is invariant under $x\to b x$ if $\phi$ has scaling dimension $(d-2)/2$.

<details><summary><strong>Solution</strong></summary>

Let

$$
\phi(x)\to b^{-\Delta}\phi(b^{-1}x).
$$

The measure contributes $b^d$, while each derivative contributes $b^{-1}$ and each field contributes $b^{-\Delta}$. Therefore

$$
\int d^d x\,(\nabla\phi)^2
\to
b^{d-2-2\Delta}
\int d^d x\,(\nabla\phi)^2.
$$

Scale invariance requires

$$
d-2-2\Delta=0,
$$

so

$$
\Delta=\frac{d-2}{2}.
$$

</details>

### Exercise 2: Relevance of phi-four

Using $\Delta_\phi^{(0)}=(d-2)/2$, compute the Gaussian RG eigenvalue of the coupling $u$ multiplying $\phi^4$.

<details><summary><strong>Solution</strong></summary>

The Gaussian engineering dimension of $\phi^4$ is

$$
\Delta_{\phi^4}^{(0)}=4\Delta_\phi^{(0)}=2(d-2).
$$

The coupling eigenvalue is

$$
y_u=d-\Delta_{\phi^4}^{(0)}=d-2(d-2)=4-d.
$$

Thus $u$ is relevant for $d<4$, marginal at $d=4$, and irrelevant for $d>4$.

</details>

### Exercise 3: Correlation length at the Gaussian fixed point

For the massive Gaussian theory,

$$
S=\frac12\int\frac{d^d p}{(2\pi)^d}\,(p^2+r)\phi(p)\phi(-p),
$$

show that the correlation length scales as $\xi\sim r^{-1/2}$ for $r>0$.

<details><summary><strong>Solution</strong></summary>

The propagator is

$$
G(p)=\frac{1}{p^2+r}.
$$

This has inverse mass scale

$$
m=\sqrt r.
$$

In position space, the large-distance correlator decays exponentially as

$$
G(x)\sim e^{-m|x|}
$$

up to a power-law prefactor. Therefore

$$
\xi=m^{-1}=r^{-1/2}.
$$

If $r\propto T-T_c$, then

$$
\xi\sim |T-T_c|^{-1/2},
$$

so $\nu=1/2$.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on Gaussian models, renormalization, and critical exponents.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" for scale transformations, anomalous dimensions, and RG equations.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, RG flow, and Wilsonian RG.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially the chapter on the renormalization group.

## Version history

- 2026-06-18: First polished draft. Added Gaussian scaling dimensions, relevant perturbations, upper-critical-dimension logic, mean-field relation, dangerous-irrelevance caveat, and exercises.
