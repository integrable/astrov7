---
title: "Scale Invariance"
description: "Explains scale transformations, scaling dimensions, power-law correlation functions, stress-tensor traces, and the relation between scale invariance and RG fixed points."
sidebar:
  label: "Scale Invariance"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman 1985, Dilatations; Wilson and Kogut 1974; Zinn-Justin 2021; Weinberg 1996, ch. 18; Cardy 1996."
topics:
  - scale invariance
  - dilatations
  - scaling dimensions
  - power-law correlators
  - stress tensor trace
  - RG fixed points
canonicalTopics:
  - scale-invariance
  - scaling-dimensions
  - dilatation-symmetry
  - rg-fixed-points
researchStatus:
  established:
    - "At an RG fixed point, local operators can be organized by scaling dimensions, and their correlation functions obey scale-covariant power-law behavior up to contact terms and operator mixing."
  active:
    - "The precise conditions under which scale invariance enhances to conformal invariance, especially outside standard unitary relativistic settings, remain an important conceptual boundary between RG and CFT."
---

## Summary

A theory is **scale invariant** when changing the unit of length can be compensated by transforming its fields and operators. For a scalar local operator $\mathcal O$ with scaling dimension $\Delta$, the finite scale transformation is written

$$
x\longmapsto x'=b x,
\qquad
\mathcal O'(x')=b^{-\Delta}\mathcal O(x),
\qquad b>0.
$$

If the vacuum and the theory are scale invariant, correlation functions obey

$$
\left\langle
\mathcal O_1(bx_1)\cdots \mathcal O_n(bx_n)
\right\rangle
=
 b^{-\sum_a\Delta_a}
\left\langle
\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)
\right\rangle,
$$

for scalar scaling operators, away from contact terms. In particular, a rotationally invariant Euclidean two-point function has the power-law form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
=
\frac{C_{\mathcal O}}{|x|^{2\Delta}}.
$$

Scale invariance is the first visible signature of an RG fixed point. At a fixed point, $\beta^i(g_*)=0$, there is no running dimensionless coupling to introduce a preferred scale. Away from a fixed point, relevant perturbations introduce scales such as a mass $m$ or a correlation length $\xi$.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Scale invariance as RG fixed point data: a dilation is compensated by operator scaling, giving power-law fixed-point correlators](/figures/renormalization-rg-eft/scale-invariance-fixed-point-map.svg)

<figcaption>

At an RG fixed point, changing the ruler is compensated by scaling local operators. Correlators then obey power laws, and the slope on log–log axes measures the scaling dimension. Relevant deformations, discussed below, are what end this ideal scaling regime by introducing physical scales such as $\xi$.

</figcaption>
</figure>

:::note[Scope of this page]
This page explains scale invariance as the RG language of fixed points and critical behavior. The stronger conformal symmetry of many fixed points is introduced only as a boundary marker; its full representation theory, Ward identities, conformal blocks, and bootstrap constraints belong in the CFT and Bootstrap volume.
:::

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

It also helps to remember the Callan–Symanzik equation, because it is the renormalized-perturbation-theory shadow of scale invariance and its breaking.

## Core idea

Scale invariance is not the statement that a formula contains no dimensionful symbols. It is the statement that the physics has no preferred ruler.

A free massless scalar field in flat spacetime is scale invariant. A massive scalar field is not, because the Compton wavelength $m^{-1}$ is a distinguished length scale. A theory with a running dimensionless coupling is not exactly scale invariant either, because the coupling changes when the renormalization scale changes. A critical statistical system at a second-order phase transition is scale invariant at distances large compared with the microscopic lattice spacing and small compared with any finite-size or detuning scale.

The RG viewpoint packages these examples into one sentence:

$$
\text{scale invariance is the local physics of a fixed point.}
$$

At a fixed point, scale transformations act on operators rather than on dimensionless couplings. Away from a fixed point, the flow of couplings tells us how scale invariance is broken.

## Setup and conventions

We use the conventions of this volume. For critical phenomena, Euclidean notation is usually the cleanest. Distances are written $|x|$, and correlation functions are ordinary Euclidean vacuum or statistical expectation values. Lorentzian statements are obtained by analytic continuation or by working at spacelike separation, with the same scaling dimensions.

A scale factor $b>0$ acts as

$$
x^\mu\mapsto x'^\mu=b x^\mu.
$$

A scalar scaling operator $\mathcal O$ of dimension $\Delta$ transforms as

$$
\mathcal O'(x')=b^{-\Delta}\mathcal O(x).
$$

Equivalently, for an invariant state,

$$
\langle \mathcal O_1(bx_1)\cdots \mathcal O_n(bx_n)\rangle
=
 b^{-\sum_a\Delta_a}
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

For operators with spin, the transformation includes the corresponding rotation or Lorentz representation. This page focuses on scalar operators because they display the RG content with the least notation.

The scaling dimension is decomposed schematically as

$$
\Delta_{\mathcal O}
=
\Delta^{\text{eng}}_{\mathcal O}+\gamma_{\mathcal O},
$$

where $\Delta^{\text{eng}}$ is the engineering dimension and $\gamma$ is the anomalous part. At a fixed point, $\Delta$ is the physical scaling exponent that appears in power-law correlators.

## Scale transformations and local operators

A local operator is not just a function of position. It also has a scaling rule. The finite transformation

$$
\mathcal O'(x')=b^{-\Delta}\mathcal O(x)
$$

means that measuring the same operator after all lengths have been stretched by $b$ gives a factor $b^{-\Delta}$.

Infinitesimally, write $b=e^s$ with $s$ small. Then

$$
x^\mu\mapsto x^\mu+s x^\mu+O(s^2).
$$

For a scalar scaling operator, the infinitesimal transformation is generated by the differential operator

$$
\delta_s\mathcal O(x)
=
-s\left(x^\mu\partial_\mu+\Delta\right)\mathcal O(x),
$$

up to the active-versus-passive sign convention for symmetry transformations. The important invariant content is the combination

$$
x^\mu\partial_\mu+\Delta.
$$

This is the local operator version of the statement that scaling is not merely a coordinate transformation. Operators themselves carry weights.

### Scaling operators and mixing

In an interacting theory, the operators that have simple scaling laws are usually not the naive monomials written in the microscopic Lagrangian. They are eigenvectors of the anomalous-dimension matrix at the fixed point.

Suppose a set of operators $\mathcal O_a$ mix under renormalization. Near a fixed point, the scaling operators are linear combinations

$$
\widehat{\mathcal O}_A=v_A{}^a\mathcal O_a
$$

chosen so that

$$
\widehat{\mathcal O}_A(x)\mapsto b^{-\Delta_A}\widehat{\mathcal O}_A(b^{-1}x)
$$

in the appropriate active notation. The numbers $\Delta_A$ are eigenvalues of the dilation operator, not necessarily engineering dimensions of simple monomials.

This is why anomalous dimensions are not small bookkeeping corrections in principle. They are part of the data of the fixed point.

## Two-point functions and power laws

Scale invariance determines the distance dependence of scalar two-point functions up to a constant and possible mixing among operators of equal dimension.

Let

$$
G(x)=\langle \mathcal O(x)\mathcal O(0)\rangle
$$

for a scalar operator of dimension $\Delta$. Translation and rotation invariance imply

$$
G(x)=G(|x|).
$$

Scale invariance gives

$$
G(bx)=b^{-2\Delta}G(x).
$$

Set $r=|x|$ and choose $b=1/r$ relative to a reference unit. Then

$$
G(r)=\frac{C_{\mathcal O}}{r^{2\Delta}}.
$$

Thus scale invariance converts the absence of a length scale into a power law. Exponential decay would require a scale:

$$
G(r)\sim e^{-r/\xi},
$$

so it cannot describe an exactly scale-invariant theory with finite nonzero $\xi$.

For two scalar scaling operators with dimensions $\Delta_1$ and $\Delta_2$, scale invariance alone permits

$$
\langle \mathcal O_1(x)\mathcal O_2(0)\rangle
\propto
\frac{1}{|x|^{\Delta_1+\Delta_2}}.
$$

Additional assumptions, such as conformal invariance and diagonalization of operators, usually imply that the two-point function vanishes unless the dimensions and other quantum numbers match. That stronger statement is conformal data, not scale invariance alone.

## Scale invariance from the renormalization group

In renormalized perturbation theory, a correlator depends on the renormalization scale $\mu$, couplings $g^i(\mu)$, masses, and coordinates. For a massless theory with scalar operator insertions, the schematic Callan–Symanzik equation is

$$
\left(
\mu\frac{\partial}{\partial\mu}
+
\beta^i(g)\frac{\partial}{\partial g^i}
+
\sum_a\gamma_a(g)
\right)
G_R(x_1,\ldots,x_n;g,\mu)=0,
$$

where $\gamma_a$ are anomalous-dimension contributions for the inserted operators. At a fixed point,

$$
\beta^i(g_*)=0.
$$

Then the only remaining scale dependence is the operator scaling itself. The correlators can be written as homogeneous functions of the separations, with dimensions corrected by anomalous dimensions evaluated at $g_*$.

This is the renormalized version of the fixed-point idea:

$$
\text{fixed point}
\quad\Longrightarrow\quad
\text{no running coupling}
\quad\Longrightarrow\quad
\text{power-law correlators}.
$$

The converse requires care. Observing approximate power laws over a finite window suggests proximity to a fixed point, but does not prove exact scale invariance. Finite-size effects, crossover, walking behavior, and slow RG flow can imitate scaling over a limited range.

## Trace of the stress tensor

Scale transformations are generated by the dilation current. In a local relativistic theory, the canonical form is

$$
D^\mu=x_\nu T^{\mu\nu}-V^\mu,
$$

where $T^{\mu\nu}$ is the stress tensor and $V^\mu$ is a possible virial current. Conservation of the dilation current gives

$$
\partial_\mu D^\mu=0.
$$

Using stress-tensor conservation, this implies schematically

$$
T^\mu{}_{\mu}=\partial_\mu V^\mu.
$$

If the virial term can be removed by improving the stress tensor, then one can choose an improved stress tensor satisfying

$$
T^\mu{}_{\mu}=0
$$

away from anomalies, contact terms, and explicit sources.

In a renormalized QFT, the trace often records the breaking of scale invariance:

$$
T^\mu{}_{\mu}
=
\beta^i(g)\mathcal O_i
+
\text{mass terms}
+
\text{curvature or contact terms}.
$$

This formula is schematic but extremely useful. It says that beta functions are not merely bookkeeping devices. They measure a local obstruction to scale invariance.

At a fixed point in flat space with all relevant deformations tuned away,

$$
\beta^i(g_*)=0,
$$

so the beta-function contribution to the trace vanishes. If no virial obstruction remains, the fixed point is conformal.

## Relevant deformations and finite correlation length

Critical systems are rarely exactly at the fixed point. Instead, one starts near the fixed point and perturbs it:

$$
S=S_*+t\int d^d x\,\mathcal O_t(x)+\cdots.
$$

If $\mathcal O_t$ has scaling dimension $\Delta_t$, then the coupling $t$ has RG eigenvalue

$$
y_t=d-\Delta_t.
$$

For $y_t>0$, this is a relevant perturbation. It grows toward the infrared and creates a finite correlation length. The scaling estimate is

$$
\xi\sim |t|^{-1/y_t}.
$$

The correlation length exponent is therefore

$$
\nu=\frac{1}{y_t}
$$

when $t$ is the temperature-like scaling field.

This is the bridge from scale invariance to critical phenomena. Exact scale invariance gives infinite correlation length. A small relevant perturbation cuts off the scale-invariant regime at a large but finite $\xi$.

The schematic behavior of a two-point function is then

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac{1}{|x|^{2\Delta}}
F\!\left(\frac{|x|}{\xi}\right),
$$

where $F(u)$ approaches a constant for $u\ll1$ and decays rapidly for $u\gg1$ in a massive phase. The fixed point controls the short-distance-to-intermediate scaling window; the relevant deformation controls how the system exits that window.

## Examples

### Free massless scalar field

In $d$ Euclidean dimensions, the free massless scalar has action

$$
S=\frac12\int d^d x\,\partial_\mu\phi\,\partial^\mu\phi.
$$

The engineering dimension of $\phi$ is

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The two-point function behaves as

$$
\langle \phi(x)\phi(0)\rangle
\propto
\frac{1}{|x|^{d-2}}
=
\frac{1}{|x|^{2\Delta_\phi}}.
$$

Adding a mass term

$$
\frac12m^2\phi^2
$$

breaks scale invariance and introduces the length $m^{-1}$.

### Wilson–Fisher fixed point

The scalar $\phi^4$ theory near four dimensions has an interacting fixed point for $d=4-\epsilon$ and positive small $\epsilon$. At that point, the field dimension is not exactly the engineering value. It takes the form

$$
\Delta_\phi=\frac{d-2+\eta}{2},
$$

where $\eta$ is the anomalous-dimension critical exponent.

The spin-field two-point function at criticality behaves as

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

This is not just classical dimensional analysis. The exponent $\eta$ is a dynamical output of the interacting fixed point.

### Asymptotic freedom

An asymptotically free gauge theory is not generally scale invariant at finite energy. Its coupling runs:

$$
\mu\frac{dg}{d\mu}=\beta(g),
\qquad
\beta(g)<0\text{ at weak coupling}.
$$

However, if $g(\mu)\to0$ as $\mu\to\infty$, the ultraviolet limit approaches the Gaussian fixed point. Short-distance correlators can show approximate scaling corrected by logarithms. Dimensional transmutation introduces a physical scale such as $\Lambda_{\mathrm{QCD}}$, so the full quantum theory is not scale invariant at all distances.

## Scale versus conformal invariance

Scale invariance says the theory is invariant under uniform rescalings of distance. Conformal invariance says it is invariant under local angle-preserving transformations, or equivalently under translations, rotations or Lorentz transformations, dilatations, and special conformal transformations in flat space.

The implication

$$
\text{conformal invariance}\quad\Longrightarrow\quad\text{scale invariance}
$$

is immediate. The reverse implication is subtler.

In many familiar unitary relativistic QFTs, scale invariance is expected or known under additional assumptions to enhance to conformal invariance. In two dimensions this enhancement is especially powerful. In higher dimensions, the relation depends on assumptions about unitarity, discreteness of the spectrum, existence and properties of the stress tensor, and the virial current.

For this volume, the practical rule is:

$$
\text{RG fixed point}
\quad\leadsto\quad
\text{scale-invariant QFT},
$$

and in most standard relativistic critical examples one then studies the fixed point as a CFT. But the logical distinction matters. Scale invariance is the RG statement; conformal invariance is a stronger symmetry statement.

## What scale invariance does not mean

Scale invariance does not mean that every quantity is dimensionless. Operators have dimensions. Couplings to relevant operators have dimensions. Correlators carry dimensions. The statement is that all scale dependence is fixed by transformation laws, not by a preferred external length.

Scale invariance also does not mean that the microscopic lattice spacing is absent in a literal statistical system. A lattice model at criticality still has a lattice spacing $a$. The continuum scaling description emerges for distances

$$
a\ll |x|\ll L,
$$

where $L$ is the system size or another infrared cutoff. The fixed point describes the universal middle, not the exact atomic details.

Finally, scale invariance does not mean that all observables are power laws at all distances in every regulator. Contact terms, boundaries, finite size, finite temperature, and relevant deformations all introduce additional structure.

## Common pitfalls

**Confusing absence of a mass term with scale invariance.** A classically massless theory can acquire running couplings and dimensional transmutation. Then scale invariance is broken quantum mechanically.

**Using engineering dimensions at an interacting fixed point.** Interacting fixed points generally have anomalous dimensions. The power in a correlation function is the full scaling dimension, not just the engineering one.

**Thinking a finite scaling window proves an exact fixed point.** Approximate power laws can arise from crossover, walking RG, finite-size effects, or a wide but finite hierarchy of scales.

**Forgetting operator mixing.** The objects with definite scaling dimensions are eigenoperators. Simple Lagrangian monomials need not be eigenoperators.

**Treating scale and conformal invariance as interchangeable.** They often travel together in important QFT examples, but they are logically distinct.

**Calling a dimensionful coupling a violation by itself.** A relevant coupling can be present as a deformation of a fixed point. The fixed point is scale invariant; the deformed theory is not.

## Relations to other pages

This page is the entry point to [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) and [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), where scaling dimensions become eigenvalues of the RG flow near $g_*$. It also prepares [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), where the exponent $\nu$ comes from a relevant RG eigenvalue and $\eta$ from the scaling of the fundamental field.

The Callan–Symanzik viewpoint connects this page back to [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/) and [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/). The Wilsonian viewpoint connects it back to [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

The stronger conformal structure belongs in the CFT and Bootstrap volume. This page deliberately stops before conformal multiplets, state-operator correspondence, conformal blocks, and crossing symmetry.

## Research status

Scale invariance at RG fixed points and the associated power-law behavior of scaling operators are established foundations of modern QFT and statistical physics.

The main live conceptual boundary is not whether fixed points imply scaling behavior; they do. The subtle question is when scale invariance enhances to conformal invariance, and how this works in nonunitary theories, theories with boundaries or defects, long-range interactions, disordered systems, fractonic or subsystem-symmetric systems, and nonrelativistic field theories.

In practice, much current work studies fixed points by combining RG, conformal bootstrap, lattice simulations, large-N expansions, epsilon expansions, supersymmetric exact methods, and numerical conformal methods. Scale invariance is the common meeting point; the tools differ by context.

## Exercises

### Exercise 1: Two-point power law

Let $G(x)=\langle \mathcal O(x)\mathcal O(0)\rangle$ for a scalar scaling operator of dimension $\Delta$ in a translation- and rotation-invariant Euclidean fixed point. Use scale invariance to show that $G(x)=C/|x|^{2\Delta}$.

<details><summary><strong>Solution</strong></summary>

Translation and rotation invariance imply $G(x)=G(r)$ with $r=|x|$. Scale invariance gives

$$
G(br)=b^{-2\Delta}G(r).
$$

Choose $b=1/r$ relative to a fixed reference unit. Then

$$
G(1)=r^{2\Delta}G(r),
$$

so

$$
G(r)=\frac{G(1)}{r^{2\Delta}}.
$$

Writing $C=G(1)$ gives the desired power law.

</details>

### Exercise 2: Correlation length from a relevant perturbation

Consider a fixed point perturbed by $t\int d^d x\,\mathcal O_t$, where $\mathcal O_t$ has scaling dimension $\Delta_t<d$. Define $y_t=d-\Delta_t$. Use scaling to estimate how the correlation length depends on $t$.

<details><summary><strong>Solution</strong></summary>

The coupling $t$ has scaling exponent $y_t=d-\Delta_t$. Under a scale transformation by $b$, it transforms as

$$
t\mapsto t(b)=b^{y_t}t.
$$

The correlation length is the scale at which the dimensionless perturbation becomes order one. Choose $b_*$ such that

$$
b_*^{y_t}|t|\sim1.
$$

Then

$$
b_*\sim |t|^{-1/y_t}.
$$

Since $b_*$ measures the growth of the length scale, the correlation length behaves as

$$
\xi\sim |t|^{-1/y_t}.
$$

Thus $\nu=1/y_t$ for the temperature-like perturbation.

</details>

### Exercise 3: Trace and beta function

Suppose a flat-space theory has one dimensionless coupling $g$ and a trace relation

$$
T^\mu{}_{\mu}=\beta(g)\mathcal O.
$$

What does this imply at a fixed point? What does it imply away from a fixed point?

<details><summary><strong>Solution</strong></summary>

At a fixed point $g_*$,

$$
\beta(g_*)=0.
$$

Therefore the beta-function contribution to the trace vanishes:

$$
T^\mu{}_{\mu}=0
$$

up to possible improvement terms, contact terms, anomalies from backgrounds, and relevant deformations not included in the schematic formula.

Away from a fixed point, $\beta(g)\ne0$, so the trace is nonzero. This means scale invariance is broken by the running of the coupling. The trace relation is the local operator expression of RG flow.

</details>

### Exercise 4: Engineering versus anomalous dimension

In a critical scalar theory, the field two-point function behaves as

$$
\langle \phi(x)\phi(0)\rangle\sim \frac{1}{|x|^{d-2+\eta}}.
$$

Find the scaling dimension $\Delta_\phi$.

<details><summary><strong>Solution</strong></summary>

For a scalar scaling operator,

$$
\langle \phi(x)\phi(0)\rangle\sim\frac{1}{|x|^{2\Delta_\phi}}.
$$

Comparing powers gives

$$
2\Delta_\phi=d-2+\eta.
$$

Thus

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

For a free scalar, $\eta=0$ and this reduces to the engineering dimension $(d-2)/2$.

</details>

## References

- Sidney Coleman, "Dilatations," in *Aspects of Symmetry*, for scale transformations, anomalous dimensions, Callan–Symanzik equations, and the return of scaling in the deep Euclidean region.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for fixed points, RG transformations, and critical phenomena.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for field-theoretic RG, critical exponents, anomalous dimensions, and the connection between particle-physics and statistical-physics renormalization.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, scaling behavior, fixed points, and critical phenomena.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact physics-first treatment of scaling and critical phenomena.
- Joseph Polchinski, "Scale and Conformal Invariance in Quantum Field Theory," *Nuclear Physics B* **303** (1988) 226–236, for a classic analysis of the scale-versus-conformal question.

## Version history

- 2026-06-17: First polished draft. Introduced scale transformations, scaling operators, power-law correlators, stress-tensor trace logic, relevant deformations, and the scale-versus-conformal boundary.
