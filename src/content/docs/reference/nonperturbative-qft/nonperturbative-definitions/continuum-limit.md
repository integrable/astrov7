---
title: "Continuum Limit"
description: "Explains how a regulated lattice or cutoff theory becomes a continuum QFT by tuning toward a critical surface while holding physical observables fixed."
sidebar:
  label: "Continuum Limit"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut; Zinn-Justin; Srednicki §82; Schwartz §23.6 and §25.5."
topics:
  - continuum limit
  - critical surface
  - renormalized trajectory
  - universality
  - correlation length
  - lattice artifacts
  - asymptotic freedom
canonicalTopics:
  - continuum-limit
  - renormalization-group
  - critical-surface
  - universality
  - lattice-qft
researchStatus:
  established:
    - "The continuum limit of a local regulated theory is controlled by renormalization-group behavior near fixed points or renormalized trajectories, with physical quantities held fixed as the cutoff is removed."
  active:
    - "Which continuum limits exist for particular strongly coupled, chiral, supersymmetric, gravitational, or sign-problem systems can be a difficult theory-specific question."
---

## Summary

The continuum limit is the process by which a regulated theory with cutoff length $a$ becomes a continuum QFT. It is not the instruction “set $a=0$.” It is a limiting procedure for observables in which bare parameters are tuned with $a$ so that selected physical quantities remain finite.

On a lattice, the essential condition is that the correlation length in lattice units diverges:

$$
\xi_{\mathrm{lat}}=\frac{\xi_{\mathrm{phys}}}{a}\longrightarrow\infty.
$$

Equivalently, for a massive theory with mass gap $M=\xi_{\mathrm{phys}}^{-1}$,

$$
aM\longrightarrow0
\qquad\text{while}\qquad
M\text{ is fixed in physical units}.
$$

A continuum limit therefore requires approaching a critical point, critical surface, or renormalized trajectory of the regulated theory. The physical theory is encoded not in one lattice action at one value of $a$, but in the limiting behavior of a family

$$
S_a(g_0(a))
$$

as $a\to0$. Universality is the reason this is useful: many different microscopic regulators can approach the same long-distance QFT.

## Prerequisites

You should know the [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) and [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/). The conceptual distinction between weak coupling, strong coupling, and nonperturbative definitions is discussed in [Semiclassical versus Strong Coupling](/nonperturbative-qft/what-is-nonperturbative-qft/semiclassical-versus-strong-coupling/).

## Core idea

A continuum limit is a zooming procedure. The lattice spacing $a$ is the ruler. If the correlation length is only a few lattice spacings, then zooming in does not reveal a continuum world; it reveals the regulator. To see continuum physics, long-distance observables must involve many lattice sites:

$$
\xi_{\mathrm{lat}}\gg1.
$$

Removing the cutoff while keeping physics fixed means arranging

$$
a\to0,
\qquad
\xi_{\mathrm{phys}}=a\xi_{\mathrm{lat}}\text{ fixed or infinite}.
$$

Thus $\xi_{\mathrm{lat}}\to\infty$. This is why continuum limits and critical phenomena are inseparable. A continuum QFT is what the regulated system looks like when the microscopic lattice spacing becomes negligible compared with all physical lengths being probed.

## Setup and conventions

Let $a$ be the cutoff length, so the ultraviolet cutoff is of order

$$
\Lambda_{\mathrm{UV}}\sim\frac{1}{a}.
$$

Let $g_i(a)$ denote bare couplings in the regulated action. These may include masses, hopping parameters, gauge couplings, quartic couplings, anisotropies, improvement coefficients, and symmetry-breaking counterterms. A continuum limit is a choice of path $g_i(a)$ in bare-coupling space such that renormalized observables have limits.

For local operators, one usually also needs operator renormalization. A schematic continuum-limit statement is

$$
\lim_{a\to0}
Z_{\mathcal O_1}(a)\cdots Z_{\mathcal O_n}(a)
\left\langle
\mathcal O_{1,a}(x_1)\cdots\mathcal O_{n,a}(x_n)
\right\rangle_{g(a)}
=
\left\langle
\mathcal O_{1,R}(x_1)\cdots\mathcal O_{n,R}(x_n)
\right\rangle.
$$

The equality is meant at separated physical points $x_i$, after subtracting or renormalizing contact singularities and operator mixing when necessary. For many physical quantities, the most robust continuum observables are dimensionless ratios, such as

$$
\frac{M_1}{M_2},
\qquad
\frac{\sqrt\sigma}{M},
\qquad
L M,
$$

where $M_i$ are masses, $\sigma$ is a string tension, and $L$ is a physical box size.

## Why criticality is necessary

Consider a lattice two-point function at large separation, measured in lattice units:

$$
C(n)\sim e^{-n/\xi_{\mathrm{lat}}}.
$$

The physical separation is $r=an$, so the same correlator can be written

$$
C(r)\sim e^{-r/\xi_{\mathrm{phys}}},
\qquad
\xi_{\mathrm{phys}}=a\xi_{\mathrm{lat}}.
$$

If $\xi_{\mathrm{lat}}$ stays finite as $a\to0$, then $\xi_{\mathrm{phys}}\to0$. Every finite physical separation is infinitely far away in units of the correlation length, and the continuum limit is either trivial or singular. To keep a nonzero physical correlation length, one must tune to a point where

$$
\xi_{\mathrm{lat}}\to\infty.
$$

That is the defining signature of a critical point or critical surface.

For a massless continuum theory, the physical correlation length is infinite. For a massive continuum theory, the usual Wilsonian picture is that the theory is a relevant deformation of a critical theory. First one approaches the critical surface closely enough to remove the cutoff; then the finite physical mass scale is set by the relevant deformation.

## Critical surfaces and relevant directions

Near a fixed point, the renormalization group classifies perturbations by scaling exponents. Write small deviations from a fixed-point action as

$$
S=S_*+\sum_i u_i\int d^dx\,\mathcal O_i(x).
$$

Under a coarse-graining by a factor $b>1$, the leading behavior is

$$
u_i\mapsto b^{y_i}u_i.
$$

The sign of $y_i$ determines the role of the perturbation.

| Type | Scaling exponent | Meaning for continuum limits |
|---|---:|---|
| Relevant | $y_i>0$ | Must be tuned or used as a physical deformation. |
| Marginal | $y_i=0$ at linear order | Requires beta functions beyond linear order. |
| Irrelevant | $y_i<0$ | Dies at long distances; controls lattice artifacts. |

The critical surface is the set of bare couplings for which all relevant deformations away from the desired fixed point have been tuned to zero. A massive continuum theory is obtained by moving away from that surface in a controlled relevant direction while still sending $a\to0$.

<figure class="doc-figure" style="--figure-width: 40rem;">

![A renormalization-group picture of the continuum limit near a critical surface.](/figures/nonperturbative-qft/continuum-limit-rg-flow.svg)

<figcaption>

A continuum limit is obtained by tuning the bare lattice action toward a critical surface or renormalized trajectory. Irrelevant deformations flow away from microscopic details, while relevant directions set physical scales such as masses.

</figcaption>
</figure>

## A free scalar check

The free massive scalar field is the cleanest check. On a lattice the propagator is

$$
G_a(p)=\frac{1}{\widehat p^{\,2}+M^2},
\qquad
\widehat p^{\,2}=\frac4{a^2}\sum_\mu\sin^2\left(\frac{ap_\mu}{2}\right).
$$

At fixed physical momentum $p$,

$$
\widehat p^{\,2}=p^2+O(a^2p^4),
$$

so

$$
G_a(p)\to\frac{1}{p^2+M^2}.
$$

In lattice units the mass is $aM$. The continuum limit keeps $M$ fixed while $aM\to0$. The correlation length in lattice units is therefore

$$
\xi_{\mathrm{lat}}\sim\frac{1}{aM}\to\infty.
$$

This example is almost too easy because the critical point is the Gaussian massless theory. Interacting theories have the same logic, but tuning and operator renormalization become nontrivial.

## Interacting scalar example

For a scalar theory with a tunable mass parameter $r$, the critical point occurs at some $r=r_c$, not necessarily at the naive classical value. Near criticality,

$$
\xi_{\mathrm{lat}}\sim |r-r_c|^{-\nu},
$$

where $\nu$ is a critical exponent. A massive continuum limit with physical mass $M$ requires

$$
M\sim \frac{1}{a\xi_{\mathrm{lat}}}
$$

held fixed. Thus the tuning must have the form

$$
|r(a)-r_c|\sim (aM)^{1/\nu}.
$$

This formula captures the practical meaning of renormalization in a lattice definition. The bare parameter $r(a)$ is not itself a physical mass. It is a cutoff-dependent coordinate on theory space that must be adjusted so that the renormalized mass is finite.

## Asymptotically free gauge theory

Pure Yang–Mills theory and QCD-like vectorlike gauge theories provide a different but equally important pattern. The continuum limit is approached at weak bare lattice coupling,

$$
g_0(a)\to0,
$$

while the infrared theory can still be strongly coupled and confining. At one loop,

$$
a\frac{dg_0}{da}=b_0g_0^3+O(g_0^5),
\qquad b_0>0,
$$

which integrates to the dimensional-transmutation relation

$$
\Lambda
\sim
\frac1a\exp\!\left[-\frac{1}{2b_0g_0^2(a)}\right]
\times\text{higher-loop factors}.
$$

Keeping $\Lambda$, a string tension $\sqrt\sigma$, or a hadron mass fixed as $a\to0$ requires tuning $g_0(a)$ logarithmically toward zero. This is the subtle punchline: the continuum limit of an asymptotically free lattice gauge theory sits at weak bare coupling, even though the long-distance physics can be nonperturbative.

This also explains why confinement cannot be seen in any finite Taylor series in $g_0^2$. Physical infrared scales behave like

$$
\Lambda\sim \frac1a e^{-1/(2b_0g_0^2)}\times\cdots,
$$

which is nonanalytic at $g_0=0$.

## Universality and lattice artifacts

Two different lattice actions can define the same continuum QFT if they flow to the same fixed point with the same relevant couplings and global data. Their microscopic actions may differ by many irrelevant operators:

$$
S_a'=S_a+\sum_j c_j(a)a^{\Delta_j-d}\int d^dx\,\mathcal O_j(x),
\qquad \Delta_j>d.
$$

These terms vanish at long distances but leave finite-$a$ artifacts. A typical continuum extrapolation has the schematic form

$$
Q(a)=Q(0)+c_1a^p+c_2a^{p+1}+\cdots,
$$

where $p$ depends on the lattice action, symmetries, and improvement scheme. The art of improved actions is to remove leading irrelevant operators so that $p$ is larger.

Universality is powerful, but not unconditional. The regulator must preserve or correctly reproduce the desired symmetries, anomalies, relevant deformations, and global definition data. A lattice action in the wrong universality class does not become right merely because $a$ is small.

## Practical continuum-limit checks

A continuum extrapolation should pass several checks.

| Check | What it tests |
|---|---|
| Scale separation | $a\ll \xi_{\mathrm{phys}}$, or equivalently $\xi_{\mathrm{lat}}\gg1$. |
| Finite-volume control | $L$ is large compared with the longest physical correlation length, unless finite-size scaling is the object of study. |
| Dimensionless-ratio stability | Ratios such as $M_1/M_2$ approach stable limits. |
| Symmetry restoration | Rotational or Lorentz-violating observables vanish with powers of $a$. |
| Artifact scaling | Data at several lattice spacings fit the expected $a^p$ corrections. |
| Operator renormalization | Composite operators are matched or renormalized before continuum comparison. |

One lattice spacing is never a continuum extrapolation. It can be useful evidence, but the phrase “continuum limit” means behavior under cutoff removal.

## Common pitfalls

**Identifying the continuum limit with a single fine lattice.** A small lattice spacing is not itself a continuum limit. The continuum limit is a controlled statement about a sequence of regulated theories and observables as $a\to0$.

**Holding bare couplings fixed.** Bare couplings are coordinates tied to the cutoff. Except in special cases, fixed bare parameters do not keep physical masses, correlation lengths, or scattering data fixed as the cutoff changes.

**Forgetting operator renormalization.** Even if the action has a good continuum limit, local composite operators may mix, require multiplicative renormalization, or require additive subtraction. The continuum limit of correlation functions is a statement about renormalized operators.

**Thinking irrelevant means unimportant at finite lattice spacing.** Irrelevant operators vanish in the continuum limit, but they control lattice artifacts. They are exactly why different discretizations approach the same answer at different speeds.

**Assuming universality fixes global data.** Local long-distance dynamics may be universal while global choices still differ: gauge-group global form, allowed line operators, spin structures, theta angles, boundary conditions, and anomaly realization can change the continuum theory.

## Relations to other pages

- [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) constructs the regulated systems whose limits are studied here.
- [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains the infrared box, boundary conditions, and thermodynamic limits that must be controlled alongside cutoff removal.
- [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) explains the Euclidean correlators whose continuum limits define Schwinger functions.
- [Asymptotic Series and Missing Effects](/nonperturbative-qft/what-is-nonperturbative-qft/asymptotic-series-and-missing-effects/) explains why scales such as $e^{-1/g^2}$ are invisible to ordinary perturbation theory.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) discusses the masses, line operators, and correlation functions used to set and test continuum physics.

## Research status

The renormalization-group logic of continuum limits is established and is one of the central organizing principles of QFT. It underlies lattice QCD, critical phenomena, Wilsonian EFT, continuum statistical field theory, and asymptotically free gauge theory.

The hard questions are theory-specific. Some regulated systems have well-controlled continuum limits with strong numerical and analytic evidence. Others require delicate symmetry protection, nonstandard regulators, or remain conjectural. In particular, chiral gauge theories, real-time finite-density systems, continuum quantum gravity, and some supersymmetric or topological systems need methods beyond the elementary scalar or Wilson-gauge examples on this page.

## Exercises

### Exercise 1: Why the lattice correlation length must diverge

Suppose a lattice two-point function behaves as

$$
C(n)\sim e^{-n/\xi_{\mathrm{lat}}}.
$$

Let $r=an$ and $\xi_{\mathrm{phys}}=a\xi_{\mathrm{lat}}$. Show that keeping $\xi_{\mathrm{phys}}$ fixed and nonzero as $a\to0$ requires $\xi_{\mathrm{lat}}\to\infty$.

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\xi_{\mathrm{lat}}=\frac{\xi_{\mathrm{phys}}}{a}.
$$

If $\xi_{\mathrm{phys}}$ is fixed and $a\to0$, then $\xi_{\mathrm{lat}}\to\infty$. Equivalently, the physical mass $M=1/\xi_{\mathrm{phys}}$ has lattice value $aM=1/\xi_{\mathrm{lat}}$, which must go to zero.

</details>

### Exercise 2: Tuning near a critical point

Assume

$$
\xi_{\mathrm{lat}}\sim |r-r_c|^{-\nu}.
$$

Find how $r(a)-r_c$ must scale with $a$ to keep $M=1/(a\xi_{\mathrm{lat}})$ fixed.

<details>
<summary><strong>Solution</strong></summary>

Keeping $M$ fixed means

$$
\xi_{\mathrm{lat}}\sim \frac{1}{aM}.
$$

Combining this with $\xi_{\mathrm{lat}}\sim |r-r_c|^{-\nu}$ gives

$$
|r(a)-r_c|^{-\nu}\sim \frac{1}{aM},
$$

so

$$
|r(a)-r_c|\sim (aM)^{1/\nu}.
$$

The bare parameter must approach its critical value as the cutoff is removed.

</details>

### Exercise 3: One-loop dimensional transmutation

Solve the one-loop asymptotically free equation

$$
a\frac{dg}{da}=b_0g^3,
\qquad b_0>0,
$$

and show that it implies a scale of the form

$$
\Lambda\sim \frac1a e^{-1/(2b_0g^2(a))}.
$$

<details>
<summary><strong>Solution</strong></summary>

Rewrite the equation as

$$
\frac{dg}{g^3}=b_0\frac{da}{a}.
$$

Since $d(g^{-2})=-2g^{-3}dg$,

$$
-\frac12 d(g^{-2})=b_0 d\log a.
$$

Thus

$$
\frac{1}{2b_0g^2(a)}=-\log a+\text{constant}.
$$

Exponentiating and absorbing the constant into the definition of $\Lambda$ gives

$$
\Lambda\sim \frac1a e^{-1/(2b_0g^2(a))}.
$$

Higher-loop terms multiply this by powers and further corrections, but the essential nonanalytic dependence is already present at one loop.

</details>

## References

### Standard first pass

- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” for the connection between critical phenomena, lattice systems, fixed points, and continuum limits.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the Euclidean field-integral and RG treatment of continuum limits.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the Wilsonian RG and lattice gauge theory discussions.

### Deeper references

- M. Srednicki, *Quantum Field Theory*, section 82, for the lattice strong-coupling argument and the continuum-limit question for confinement.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive continuum limits in Euclidean QFT.
- C. Gattringer and C. B. Lang, *Quantum Chromodynamics on the Lattice*, for practical continuum extrapolation in lattice gauge theory.

## Version history

- **2026-06-25:** Initial polished page.
