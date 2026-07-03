---
title: "Exact RG Equations"
description: "Exact RG equations as functional identities expressing cutoff independence, with Polchinski and Wetterich equations as the two main archetypes."
sidebar:
  label: "Exact RG Equations"
  order: 1
level: Advanced
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Wetterich 1993; Morris; Zinn-Justin 2021; Berges, Tetradis, and Wetterich; Rosten; Burgess 2020."
topics:
  - exact renormalization group
  - Wilsonian action
  - Polchinski equation
  - Wetterich equation
  - functional RG
  - cutoff independence
canonicalTopics:
  - exact-rg-equations
  - polchinski-equation
  - wetterich-equation
  - functional-renormalization-group
researchStatus:
  established:
    - "Exact RG equations are exact functional identities that encode how a scale-dependent action or effective action changes as the regulator scale changes while the underlying physics is held fixed."
  active:
    - "Their nonperturbative usefulness depends on truncations, regulator choices, symmetry constraints, and convergence diagnostics, which remain active methodological research topics."
---

## Summary

An **exact RG equation** is a functional differential equation that describes how a scale-dependent description of a QFT changes when the regulator scale is changed. The word exact is important but dangerous: the equation is exact under its assumptions; practical solutions usually are not.

The two archetypes are:

$$
\text{Wilsonian flow:}\qquad S_\Lambda[\phi]
\quad\text{changes as high modes are integrated out},
$$

and

$$
\text{effective-average-action flow:}\qquad \Gamma_k[\varphi]
\quad\text{changes as fluctuations with momenta near }k\text{ are released}.
$$

A common Polchinski-type equation for the interaction part $S^I_\Lambda$ of a Euclidean scalar Wilsonian action is

$$
-\Lambda\frac{\partial S^I_\Lambda}{\partial\Lambda}
=\frac12\frac{\delta S^I_\Lambda}{\delta\phi}\cdot \dot C_\Lambda\cdot\frac{\delta S^I_\Lambda}{\delta\phi}
-\frac12\operatorname{Tr}\!\left(\dot C_\Lambda\frac{\delta^2 S^I_\Lambda}{\delta\phi\,\delta\phi}\right),
$$

up to convention-dependent vacuum terms. Here $C_\Lambda$ is a regulated propagator and $\dot C_\Lambda\equiv -\Lambda\partial_\Lambda C_\Lambda$.

A common Wetterich-type equation for the effective average action is

$$
\partial_t\Gamma_k[\varphi]
=\frac12\operatorname{Tr}\!\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}\partial_t R_k
\right],
\qquad t\equiv\log k.
$$

Both equations encode the same broad idea: physics should not depend on an arbitrary separation scale. What changes is the coordinate system used to describe that invariance.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 56rem;">

![Exact RG equation workflow from cutoff-independent physics to regulator kernel, functional flow, infinite operator tower, truncation, beta functions, and universal data.](/figures/renormalization-rg-eft/advanced-exact-rg-equation-map.svg)

<figcaption>

An exact RG equation starts from cutoff-independent physics and turns a change of regulator scale into a functional flow. The exact flow lives on an infinite-dimensional space of actions or effective actions. Practical calculations project it to a finite ansatz; universal quantities must survive changes of regulator and truncation.

</figcaption>
</figure>

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/). You should also be comfortable with Euclidean path integrals, Gaussian integration, functional derivatives, and the idea that a QFT can be expanded in a basis of local operators.

This page uses Euclidean notation for the functional equations. Lorentzian factors of $i$ are not the point here; the point is the scale dependence of regulated functional integrals.

## Core idea

The renormalization group begins with a split between degrees of freedom we keep explicit and degrees of freedom we hide inside effective couplings. If that split is arbitrary, then changing the split should not change the underlying long-distance physics.

An exact RG equation expresses this requirement infinitesimally. Instead of integrating out a large momentum shell once and rewriting the action, one changes a cutoff or regulator smoothly and demands that the partition function, connected correlators, or low-energy observables remain invariant. The result is a functional flow equation.

In ordinary coupling language, an RG equation looks like

$$
\frac{d g^i}{dt}=\beta^i(g).
$$

An exact RG equation is the same idea before truncating to finitely many couplings:

$$
\partial_t S_t[\phi]=\mathcal F[S_t],
$$

or

$$
\partial_t\Gamma_t[\varphi]=\mathcal G[\Gamma_t].
$$

The symbols $\mathcal F$ and $\mathcal G$ are nonlinear functional differential operators. Once you expand $S_t$ or $\Gamma_t$ in an operator basis, their components become beta functions, anomalous dimensions, and flow equations for infinitely many couplings.

:::note[Exactness lives before projection]
The full functional equation can be exact. The moment you restrict to

$$
S_\Lambda=\int d^d x\left[V_\Lambda(\phi)+\frac12Z_\Lambda(\phi)(\partial\phi)^2+\cdots\right]
$$

and discard the dots, you have made an approximation. That approximation may be excellent, but it is no longer exact.
:::

## Setup and conventions

Work with a Euclidean scalar field for concreteness. A UV-regulated Gaussian measure can be described by a cutoff propagator

$$
C_\Lambda(p)=\frac{K(p^2/\Lambda^2)}{p^2+m^2},
$$

where $K(y)$ is a smooth cutoff profile. One typically wants

$$
K(y)\approx 1\quad (y\ll 1),
\qquad
K(y)\to 0\quad (y\gg 1).
$$

The Wilsonian action at scale $\Lambda$ is written schematically as

$$
S_\Lambda[\phi]
=\frac12\phi\cdot C_\Lambda^{-1}\cdot\phi+S^I_\Lambda[\phi],
$$

where the dot notation means integration over momenta or positions:

$$
A\cdot B\equiv \int\frac{d^d p}{(2\pi)^d}A(p)B(-p).
$$

The scale derivative is often written using

$$
t\equiv\log\Lambda,
\qquad
\dot C_\Lambda\equiv -\Lambda\partial_\Lambda C_\Lambda.
$$

Different authors choose different signs and different RG times. Always identify whether the flow parameter increases toward the UV or toward the IR before comparing equations.

## What is being held fixed?

Every RG equation has a hidden phrase: **while the underlying physics is held fixed**. In perturbative renormalization, beta functions are defined by changing $\mu$ while bare quantities are held fixed. In Wilsonian RG, one changes the cutoff and adjusts the action so that low-energy predictions remain unchanged.

For a Wilsonian action, the schematic requirement is

$$
Z=\int\mathcal D\phi\,e^{-S_\Lambda[\phi]}
\quad\text{is independent of }\Lambda,
$$

at least for observables below the cutoff and after source terms are handled consistently. Infinitesimally,

$$
\Lambda\frac{dZ}{d\Lambda}=0.
$$

The nontrivial content is to choose a change of $S_\Lambda$ that compensates for the change in the Gaussian measure or regulator.

A useful way to remember the logic is

$$
\text{change regulator}
+\text{change action}
=\text{same low-energy physics}.
$$

The exact RG equation is the differential form of this statement.

## Total derivatives in field space

Why do exact RG equations have functional derivatives? Because changing a cutoff can often be represented as a total derivative in field space. The integral of a total derivative vanishes under suitable boundary assumptions:

$$
\int\mathcal D\phi\,
\frac{\delta}{\delta\phi}\cdot\Psi[\phi] = 0.
$$

Therefore a flow of the Boltzmann weight of the form

$$
\partial_t e^{-S_t[\phi]}
=\frac{\delta}{\delta\phi}\cdot\Psi_t[\phi]e^{-S_t[\phi]}
$$

leaves the partition function invariant. Different choices of $\Psi_t$ correspond to different RG schemes, cutoff profiles, and field redefinitions. This is one reason exact RG equations are not unique.

This total-derivative viewpoint also explains why redundant operators and field redefinitions are always nearby. Some flow directions correspond to changing variables rather than changing physics. A good exact RG treatment must keep track of which deformations are physical and which are coordinate artifacts.

## The Polchinski equation

The Polchinski equation is a Wilsonian exact RG equation for the interaction part $S^I_\Lambda$ of a cutoff action. In one common Euclidean convention,

$$
S_\Lambda[\phi]
=\frac12\phi\cdot C_\Lambda^{-1}\cdot\phi+S^I_\Lambda[\phi],
$$

and

$$
-\Lambda\frac{\partial S^I_\Lambda}{\partial\Lambda}
=\frac12\frac{\delta S^I_\Lambda}{\delta\phi}\cdot \dot C_\Lambda\cdot\frac{\delta S^I_\Lambda}{\delta\phi}
-\frac12\operatorname{Tr}\!\left(\dot C_\Lambda\frac{\delta^2 S^I_\Lambda}{\delta\phi\,\delta\phi}\right),
$$

where

$$
\dot C_\Lambda\equiv -\Lambda\partial_\Lambda C_\Lambda.
$$

The first term is often called the classical term. It is quadratic in the first functional derivative of the interaction action. Diagrammatically it joins two vertices with one differentiated cutoff propagator.

The second term is often called the quantum term. It contains a second functional derivative and corresponds to closing two legs of a vertex with one differentiated cutoff propagator.

The equation resembles a one-loop formula, but that resemblance can mislead. The equation is exact because the vertices appearing inside it are vertices of the full Wilsonian interaction action, not only bare vertices at a fixed order.

## Perturbation theory from the exact equation

To recover ordinary beta functions, expand $S^I_\Lambda$ in local operators. For example, in a scalar theory near four dimensions,

$$
S^I_\Lambda=\int d^d x\left[
\frac12 g_2(\Lambda)\phi^2
+\frac{1}{4!}g_4(\Lambda)\phi^4
+\frac{1}{6!}g_6(\Lambda)\phi^6
+c_{2,2}(\Lambda)\phi^2(\partial\phi)^2
+\cdots
\right].
$$

Substituting this expansion into the exact equation and projecting onto each local operator gives infinitely many beta functions:

$$
\Lambda\frac{d g_i}{d\Lambda}=\beta_i(g_2,g_4,g_6,c_{2,2},\ldots).
$$

Perturbative renormalizability emerges when only a finite set of couplings is needed to remove regulator dependence for predictions at a chosen accuracy. EFT emerges when the infinite tower is retained but organized by powers of $Q/M$ or $Q/\Lambda$.

This is why exact RG equations are conceptually powerful: they make the infinite-dimensional nature of theory space explicit, then show how familiar finite beta-function systems arise by projection.

## The Wetterich equation

The Wetterich equation is an exact flow equation for the **effective average action** $\Gamma_k[\varphi]$. It is built by adding an infrared regulator to the path integral:

$$
\Delta S_k[\phi]=\frac12\phi\cdot R_k\cdot\phi.
$$

The regulator $R_k(p)$ suppresses low-momentum fluctuations with $p^2\lesssim k^2$ while leaving high-momentum fluctuations mostly unchanged. One defines a scale-dependent generating functional and performs a modified Legendre transform. The result is $\Gamma_k[\varphi]$.

The exact flow equation is

$$
\partial_t\Gamma_k[\varphi]
=\frac12\operatorname{Tr}\!\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}\partial_t R_k
\right],
\qquad t=\log k.
$$

Here

$$
\Gamma_k^{(2)}[\varphi]
\equiv
\frac{\delta^2\Gamma_k}{\delta\varphi\,\delta\varphi}
$$

is the exact inverse propagator in the background field $\varphi$. The trace includes momentum integration and internal indices.

The form is compact:

$$
\partial_t\Gamma_k
=\frac12\operatorname{Tr}\left[
\text{full regulated propagator}\times\partial_t\text{regulator}
\right].
$$

Again the equation looks one-loop-like, but it is exact because the propagator contains $\Gamma_k^{(2)}$, not a bare quadratic operator.

## Boundary conditions for functional flow

The effective average action interpolates between two useful limits. At a high UV scale $k=\Lambda_0$, one often chooses

$$
\Gamma_{k=\Lambda_0}\approx S_{\Lambda_0},
$$

if the regulator suppresses nearly all fluctuations. At $k\to 0$, the regulator is removed and

$$
\Gamma_{k\to 0}=\Gamma,
$$

where $\Gamma$ is the ordinary one-particle-irreducible effective action.

Thus the flow is often described as

$$
S_{\Lambda_0}
\longrightarrow
\Gamma_k
\longrightarrow
\Gamma.
$$

This makes the Wetterich equation especially useful for nonperturbative approximations to effective potentials, phase diagrams, critical exponents, and many-body systems. It is not restricted to perturbation theory, but its accuracy is only as good as the truncation used to solve it.

## Polchinski versus Wetterich

The Polchinski and Wetterich equations are not the same equation written with different symbols. They are different functional coordinates on RG physics.

| Feature | Polchinski-type flow | Wetterich-type flow |
|---|---|---|
| Flowing object | Wilsonian interaction action $S^I_\Lambda$ | Effective average action $\Gamma_k$ |
| Regulator role | UV or Wilsonian cutoff in the propagator | IR suppressor $R_k$ in the path integral |
| Endpoint intuition | Integrate out high modes into $S_\Lambda$ | Release fluctuations gradually into $\Gamma_k$ |
| Common use | Perturbative renormalization, Wilsonian theory space, ERG proofs | Nonperturbative truncations, critical exponents, phase diagrams |
| Equation character | Functional differential equation for an action | Functional trace equation for a Legendre effective action |

In sufficiently careful formulations, Wilsonian and Legendre flows can be related. The important lesson for readers is not that one is "the real RG" and the other is decoration. The important lesson is that RG can be represented in multiple functional coordinate systems.

## Fixed points and eigenoperators

An exact RG equation becomes especially powerful near fixed points. After introducing dimensionless fields and coordinates, a fixed point is a scale-independent solution

$$
\partial_t S_* = 0
$$

or

$$
\partial_t\Gamma_* = 0.
$$

Perturb around it:

$$
S_t=S_*+\sum_i u_i(t)\mathcal V_i.
$$

Linearizing the exact RG equation gives an eigenvalue problem:

$$
\partial_t u_i=\lambda_i u_i+\text{nonlinear terms}.
$$

The eigenoperators $\mathcal V_i$ are the scaling perturbations. Their eigenvalues determine relevant, irrelevant, and marginal directions. This is the functional version of the linearized RG flow discussed in [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/).

The value of exact RG here is conceptual and practical. Conceptually, it makes fixed points actual functionals, not just zeros of a few perturbative beta functions. Practically, truncations of the functional equation can estimate nonperturbative critical exponents.

## Local potential approximation

A common first truncation of the Wetterich equation for a scalar theory is the **local potential approximation**. One assumes

$$
\Gamma_k[\varphi]
=\int d^d x\left[
\frac12(\partial\varphi)^2+V_k(\varphi)
\right].
$$

Then $\Gamma_k^{(2)}+R_k$ becomes, for constant background field,

$$
p^2+R_k(p)+V_k''(\varphi).
$$

The Wetterich equation reduces to a flow for the potential:

$$
\partial_t V_k(\varphi)
=\frac12\int\frac{d^d p}{(2\pi)^d}
\frac{\partial_t R_k(p)}{p^2+R_k(p)+V_k''(\varphi)}.
$$

This equation is much simpler than the full functional flow, but it is also a truncation. Including a field-dependent wavefunction factor gives the next level:

$$
\Gamma_k[\varphi]
=\int d^d x\left[
\frac12Z_k(\varphi)(\partial\varphi)^2+V_k(\varphi)+O(\partial^4)
\right].
$$

The derivative expansion is useful when long-wavelength physics dominates. It can fail or need refinement when momentum dependence, gauge symmetry, fermions, topological terms, or nonlocal structures are essential.

## How beta functions are extracted

To extract beta functions from a functional equation:

1. Choose a truncation or operator basis.
2. Insert it into the functional flow equation.
3. Expand both sides in fields, derivatives, and symmetry structures.
4. Match coefficients of independent operators.
5. Convert to dimensionless couplings.
6. Check regulator, basis, and truncation dependence.

For example, if

$$
V_k(\varphi)=\frac12m_k^2\varphi^2+\frac{\lambda_k}{4!}\varphi^4+\cdots,
$$

then expanding the potential flow in powers of $\varphi$ gives flow equations for $m_k^2$, $\lambda_k$, and higher couplings. Dimensionless variables such as

$$
\tilde m^2=\frac{m_k^2}{k^2},
\qquad
\tilde\lambda=k^{d-4}\lambda_k
$$

then reveal fixed points and scaling exponents.

The exact equation itself does not decide which truncation is faithful. That decision is a physics and numerics problem.

## Regulator dependence and universality

Exact RG equations contain regulator choices. The cutoff profile $K$ in a Polchinski-type equation or the shape function in $R_k$ for a Wetterich-type equation affects intermediate expressions. In the full untruncated equation, physical observables should not depend on these choices.

In a truncation, regulator dependence is a diagnostic. If a claimed universal exponent or physical prediction changes wildly under reasonable regulator changes, the truncation is not controlled.

Universal data include, when properly extracted,

$$
\eta,
\qquad
\nu,
\qquad
\omega,
\qquad
\text{critical exponent ratios},
$$

fixed-point scaling dimensions, and physical long-distance observables. Nonuniversal data include coordinates of fixed points in a chosen coupling basis, regulator-dependent couplings, and many intermediate beta-function coefficients outside universal regimes.

## Symmetries and exact RG

A useful exact RG equation should preserve the symmetries needed by the theory, or else make their restoration explicit. For scalar theories this is often straightforward. For gauge theories it is harder.

Gauge theories create a tension: a momentum cutoff usually breaks gauge invariance, but gauge invariance is not optional. Possible strategies include:

- use a regulator compatible with gauge identities when possible;
- use background-field methods to preserve background gauge invariance;
- formulate modified Ward or Slavnov–Taylor identities together with the flow;
- restore symmetry with local counterterms if no anomaly obstructs it;
- use gauge-invariant ERG constructions, at the cost of technical complexity.

This is why functional RG calculations in gauge theories must be read with special attention to gauge fixing, ghosts, regulator choices, Ward identities, and physical observable checks.

## Common pitfalls

**Thinking exact means nonperturbatively solved.** The equation is exact. The ansatz is usually not.

**Forgetting field rescaling.** Fixed points require dimensionless variables. If one studies dimensionful couplings without rescaling fields and coordinates, canonical scaling is hidden or misread.

**Comparing flows with opposite RG time conventions.** Some authors use $t=\log k$; others use an IR time increasing as $k$ decreases. Signs of eigenvalues and beta functions then change.

**Treating regulator-dependent numbers as observables.** Fixed-point coordinates and nonuniversal couplings can move under scheme changes. Critical exponents and scaling dimensions are the real tests.

**Assuming a local derivative expansion always works.** Some physics is intrinsically nonlocal in momentum space, especially near Fermi surfaces, in gauge theories, or in systems with competing soft modes.

**Ignoring redundant operators.** Functional flows include coordinate directions generated by field redefinitions. Physical theory space is a quotient, not the raw space of all action coefficients.

## Relations to other pages

This page extends [Exact Renormalization Group](/renormalization-rg-eft/wilsonian-renormalization/exact-renormalization-group/) from the Wilsonian chapter. The present page focuses on the advanced functional-equation viewpoint and prepares the specialized pages on the [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/) and [Wetterich Equation](/renormalization-rg-eft/advanced-rg-methods/wetterich-equation/).

For conceptual background, see [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and [Relevant, Irrelevant, and Marginal Operators](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/). For applications to critical phenomena, see [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) and [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/).

For gauge-theory caveats, see [Gauge-Invariant Regularization](/renormalization-rg-eft/gauge-theories-and-rg/gauge-invariant-regularization/), [Ward Identities and Renormalization](/renormalization-rg-eft/gauge-theories-and-rg/ward-identities-and-renormalization/), and [BRST and Renormalization Preview](/renormalization-rg-eft/gauge-theories-and-rg/brst-and-renormalization-preview/).

## Research status

The existence and formal structure of exact RG equations are established. They provide a precise way to encode Wilsonian scale dependence, fixed points, eigenoperators, and regulator independence.

The active frontier is not whether such equations can be written. It is how to use them reliably. Important current questions include: how to design truncations with controlled error estimates, how to preserve gauge and global symmetries, how to extract real-time or finite-density physics, how to treat fermionic and Fermi-surface systems, how to combine functional RG with lattice, bootstrap, Schwinger–Dyson, and machine-learning methods, and how to define scheme-independent diagnostics of convergence.

## Exercises

### Exercise 1: Why the Wetterich equation is one-loop-like but exact

Explain why

$$
\partial_t\Gamma_k
=\frac12\operatorname{Tr}\!\left[(\Gamma_k^{(2)}+R_k)^{-1}\partial_t R_k\right]
$$

looks like a one-loop expression but is not merely a one-loop approximation.

<details><summary><strong>Solution</strong></summary>

A one-loop effective action usually contains a trace of a logarithm or an inverse quadratic fluctuation operator built from the classical action. The Wetterich equation has a similar trace structure, but the inverse operator is

$$
(\Gamma_k^{(2)}+R_k)^{-1},
$$

where $\Gamma_k^{(2)}$ is the second functional derivative of the full scale-dependent effective average action, not the bare quadratic action. Thus all higher interactions that have already been generated by the flow are contained inside $\Gamma_k^{(2)}$. The equation is exact as a functional identity; approximations enter when one truncates $\Gamma_k$.

</details>

### Exercise 2: Dimensionless mass flow

Let a scalar mass parameter satisfy, near the Gaussian fixed point,

$$
k\frac{dm^2}{dk}=0
$$

in dimensionful units. Define $\tilde m^2=m^2/k^2$. Show that

$$
k\frac{d\tilde m^2}{dk}=-2\tilde m^2.
$$

Interpret the sign using $t=\log k$.

<details><summary><strong>Solution</strong></summary>

Differentiate

$$
\tilde m^2=m^2k^{-2}.
$$

Since $k\,dm^2/dk=0$,

$$
k\frac{d\tilde m^2}{dk}
=k\frac{d}{dk}(m^2k^{-2})
=-2m^2k^{-2}
=-2\tilde m^2.
$$

With $t=\log k$, increasing $t$ means moving toward the UV. The negative eigenvalue means the dimensionless mass shrinks toward the UV. Equivalently, it grows toward the IR, so the mass perturbation is relevant in the Wilsonian infrared sense.

</details>

### Exercise 3: Projection from a functional flow

Suppose a functional flow produces a potential equation

$$
\partial_t V_k(\varphi)=A_k+B_k\varphi^2+C_k\varphi^4+O(\varphi^6).
$$

If

$$
V_k(\varphi)=\frac12m_k^2\varphi^2+\frac{\lambda_k}{4!}\varphi^4+O(\varphi^6),
$$

find $\partial_t m_k^2$ and $\partial_t\lambda_k$ in terms of $B_k$ and $C_k$.

<details><summary><strong>Solution</strong></summary>

Differentiate the ansatz:

$$
\partial_t V_k(\varphi)
=\frac12(\partial_t m_k^2)\varphi^2
+\frac{1}{4!}(\partial_t\lambda_k)\varphi^4+\cdots.
$$

Matching coefficients gives

$$
\frac12\partial_t m_k^2=B_k,
\qquad
\frac{1}{4!}\partial_t\lambda_k=C_k.
$$

Therefore

$$
\partial_t m_k^2=2B_k,
\qquad
\partial_t\lambda_k=24C_k.
$$

The constant term $A_k$ is a vacuum-energy flow and does not affect the mass or quartic coupling in this projection.

</details>

## References

- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974), for the modern Wilsonian RG viewpoint and early exact RG ideas.
- J. Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984), for the Polchinski exact RG equation.
- C. Wetterich, "Exact Evolution Equation for the Effective Potential," *Physics Letters B* **301** (1993), for the effective-average-action flow.
- T. R. Morris, reviews on exact renormalization group equations and derivative expansions.
- J. Berges, N. Tetradis, and C. Wetterich, "Non-Perturbative Renormalization Flow in Quantum Field Theory and Statistical Physics," for the functional RG framework and applications.
- O. J. Rosten, "Fundamentals of the Exact Renormalization Group," for a detailed modern perspective on ERG structure.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for RG equations, critical behavior, and functional methods.
- C. P. Burgess, *Introduction to Effective Field Theory*, for Wilsonian logic, effective actions, and exact RG in an EFT-oriented language.

## Version history

- 2026-06-19: First polished draft. Introduced exact RG equations, Polchinski and Wetterich archetypes, projection to beta functions, truncation caveats, and exercises.
