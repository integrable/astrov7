---
title: "Exact Renormalization Group"
description: "Explains exact renormalization group equations as functional identities for cutoff-dependent actions, with Polchinski's equation as the central example."
sidebar:
  label: "Exact Renormalization Group"
  order: 8
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Polchinski 1984; Wegner and Houghton 1973; Zinn-Justin 2021; Weinberg Vol. II ch. 18; Burgess chs. 2–3; Rosten 2012."
topics:
  - exact renormalization group
  - Polchinski equation
  - Wilsonian effective action
  - cutoff flow
  - functional differential equations
  - theory space
canonicalTopics:
  - exact-renormalization-group
  - polchinski-equation
  - wilsonian-flow-equation
  - cutoff-effective-action
researchStatus:
  established:
    - "Exact RG equations are exact functional identities expressing cutoff independence of long-distance physics; practical predictions require projections, truncations, expansions, or special solvable limits."
  active:
    - "Exact RG methods remain active in mathematical RG, critical phenomena, gauge theories, gravity-inspired asymptotic-safety programs, and nonperturbative truncation schemes."
---

## Summary

An **exact renormalization group equation** is a differential equation for a cutoff-dependent action that preserves the same long-distance physics while the cutoff is changed. It is exact in the sense that, before approximation, it is equivalent to the original path integral with a different division between already-integrated and still-explicit degrees of freedom.

In Euclidean scalar field theory, a standard form is Polchinski's equation for the interaction part $S^I_\Lambda[\phi]$ of a Wilsonian action:

$$
\partial_\ell S^I_\Lambda
=
\frac12\frac{\delta S^I_\Lambda}{\delta\phi}\cdot \dot C_\Lambda\cdot
\frac{\delta S^I_\Lambda}{\delta\phi}
-
\frac12\operatorname{Tr}\left(\dot C_\Lambda
\frac{\delta^2 S^I_\Lambda}{\delta\phi\,\delta\phi}\right),
\qquad
\ell=\log\frac{\Lambda_0}{\Lambda}.
$$

Here $\Lambda$ is a Wilsonian cutoff, $\ell$ increases toward the infrared, and $\dot C_\Lambda\equiv\partial_\ell C_\Lambda$ is a smooth shell propagator. The first term glues together two interaction vertices through the shell kernel. The second term contracts two legs of one vertex through the shell kernel. Together they encode the infinitesimal effect of integrating out a momentum shell.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Exact RG map from a cutoff-dependent path integral to partition-function invariance, total functional derivatives, exact functional flow, and projected beta functions](/figures/renormalization-rg-eft/exact-rg-equation-map.svg)

<figcaption>

An exact RG equation is a functional identity before approximation. Moving the cutoff is compensated by a change of the cutoff action $S_\Lambda$, often expressible as a total functional derivative in the path integral. Ordinary beta functions appear only after choosing coordinates and projecting the functional flow onto an operator basis.

</figcaption>
</figure>

:::note[Exact does not mean solved]
The word exact is slightly dangerous. Exact RG equations are exact identities in theory space. They are usually impossible to solve exactly. Their power is that they organize approximations without hiding the fact that every allowed local operator is generated.
:::

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/), and [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/). The classification of perturbations near fixed points is reviewed in [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

This page uses Euclidean path-integral notation because exact RG equations are cleanest there. The conceptual content is Wilsonian and does not depend on Euclidean signature.

## Core idea

The Wilsonian picture says that a theory at cutoff $\Lambda$ should know everything needed for physics below $\Lambda$, but it should not keep explicit variables for modes above $\Lambda$. If the cutoff is lowered from $\Lambda$ to $\Lambda-d\Lambda$, the modes in the thin shell are integrated out and their effect is absorbed into a new action.

The slogan is

$$
\text{lower the cutoff} \quad + \quad \text{change the action}
\quad = \quad \text{same long-distance physics}.
$$

An exact RG equation makes this slogan differential. It asks for a flow

$$
\Lambda\longmapsto S_\Lambda
$$

such that partition functions and correlation functions of low-momentum observables do not change. Equivalently, changing $\Lambda$ can be represented by a change of coordinates on the path integral, together with a compensating change of the effective action.

This viewpoint is deeper than perturbative cancellation of divergences. The exact RG is a statement about the entire action functional. It does not assume that only a finite list of couplings exists. On the contrary, it tells us that the flow generally generates infinitely many local operators:

$$
S_\Lambda
=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

The practical question is why only a few of these couplings matter at long distances. That answer comes from relevance, irrelevance, fixed points, and universality.

## Setup and conventions

We work with one real scalar field in $d$ Euclidean dimensions. Momentum integrals are abbreviated as

$$
\int_p\equiv\int\frac{d^d p}{(2\pi)^d}.
$$

A dot denotes integration over repeated momentum variables. For example,

$$
A\cdot B
\equiv
\int_p A(p)B(-p),
$$

and

$$
A\cdot C\cdot B
\equiv
\int_p A(p)C(p)B(-p)
$$

when the kernel is translation invariant.

Introduce a smooth cutoff propagator

$$
C_\Lambda(p)=\frac{K(p^2/\Lambda^2)}{p^2+m^2},
$$

where $K(z)$ is close to $1$ for $z\ll1$ and decays rapidly for $z\gg1$. The Wilsonian action is split as

$$
S_\Lambda[\phi]
=
\frac12\phi\cdot C_\Lambda^{-1}\cdot\phi
+S^I_\Lambda[\phi].
$$

The interaction part $S^I_\Lambda$ contains all local and nonlocal terms generated by modes above $\Lambda$. When locality and a derivative expansion are valid, it can be expanded in local operators.

We use the infrared RG time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
\qquad
\partial_\ell=-\Lambda\frac{\partial}{\partial\Lambda}.
$$

Thus $\ell$ increases when the cutoff is lowered. This convention is natural in Wilsonian RG. It is the opposite of the renormalized perturbation theory convention $t=\log\mu$, which increases toward the ultraviolet.

## Why an exact flow equation exists

Consider the regulated generating functional with no sources,

$$
Z
=
\int\mathcal D\phi\,
\exp\left[-\frac12\phi\cdot C_\Lambda^{-1}\cdot\phi-S^I_\Lambda[\phi]\right].
$$

The cutoff propagator $C_\Lambda$ changes as $\Lambda$ changes. If $S^I_\Lambda$ were held fixed, $Z$ would change. The exact RG asks for a compensating $\Lambda$ dependence of $S^I_\Lambda$ so that the full $Z$ stays invariant:

$$
\partial_\ell Z=0.
$$

More generally, low-momentum correlation functions are required to be invariant after the external fields are normalized consistently. This condition can be implemented by writing the cutoff derivative of the integrand as a functional total derivative:

$$
\partial_\ell e^{-S_\Lambda[\phi]}
=
\int_p\frac{\delta}{\delta\phi(p)}
\left[\Psi_\Lambda(p;\phi)e^{-S_\Lambda[\phi]}\right].
$$

If the functional measure has no boundary contribution, the integral of the right-hand side vanishes. Different choices of $\Psi_\Lambda$ give different exact RG schemes. They are different coordinate systems on the same infinite-dimensional space of theories.

This is the conceptual reason exact RG equations are plentiful. The Wegner–Houghton equation, Polchinski equation, Wilsonian flow equations, and functional RG equations are not competing laws of nature. They are different ways of representing the same scale-reorganization principle.

## Polchinski's equation

With the split

$$
S_\Lambda[\phi]
=
\frac12\phi\cdot C_\Lambda^{-1}\cdot\phi+S^I_\Lambda[\phi],
$$

one convenient exact flow is Polchinski's equation:

$$
\partial_\ell S^I_\Lambda
=
\frac12\frac{\delta S^I_\Lambda}{\delta\phi}\cdot \dot C_\Lambda\cdot
\frac{\delta S^I_\Lambda}{\delta\phi}
-
\frac12\operatorname{Tr}\left(\dot C_\Lambda
\frac{\delta^2 S^I_\Lambda}{\delta\phi\,\delta\phi}\right),
$$

where

$$
\dot C_\Lambda\equiv\partial_\ell C_\Lambda=-\Lambda\frac{\partial C_\Lambda}{\partial\Lambda}.
$$

In momentum notation, the first term means

$$
\frac12\int_p
\frac{\delta S^I_\Lambda}{\delta\phi(p)}
\dot C_\Lambda(p)
\frac{\delta S^I_\Lambda}{\delta\phi(-p)}.
$$

The trace term means

$$
\frac12\int_p
\dot C_\Lambda(p)
\frac{\delta^2 S^I_\Lambda}{\delta\phi(p)\delta\phi(-p)},
$$

with the sign shown in the full equation.

The shell kernel $\dot C_\Lambda$ is concentrated near momenta of order $\Lambda$ for a smooth cutoff. Therefore the equation is local in scale: the change in $S^I_\Lambda$ is controlled by the modes being removed near the current cutoff.

:::tip[How to read the two terms]
The term quadratic in $\delta S^I/\delta\phi$ joins two vertices through the shell kernel. The term with $\delta^2S^I/\delta\phi\delta\phi$ contracts two legs of the same vertex through the shell kernel. In diagram language, the equation integrates one shell propagator at a time.
:::

## The tree term and the loop term

The two terms in Polchinski's equation have different diagrammatic meanings.

The first term,

$$
\frac12\frac{\delta S^I}{\delta\phi}\cdot\dot C\cdot\frac{\delta S^I}{\delta\phi},
$$

is often called the **classical** or **tree** term. It is quadratic in the action and resembles the joining of two interaction vertices by one differentiated propagator. It does not mean the resulting physics is only classical. It means the functional equation has the form of a tree-level composition rule once the shell propagator is singled out.

The second term,

$$
-\frac12\operatorname{Tr}\left(\dot C\frac{\delta^2S^I}{\delta\phi\,\delta\phi}\right),
$$

is often called the **quantum** or **loop** term. It differentiates a single vertex twice and closes the two exposed legs with the shell kernel. It is responsible, for example, for tadpole-type contributions when applied to a quartic vertex.

The exact flow is not the same as summing ordinary Feynman diagrams in one step. It is a differential organization of all shell contractions. Ordinary loop diagrams reappear when the flow equation is iterated or projected onto a perturbative expansion in couplings.

## Locality and the derivative expansion

The exact Wilsonian action is an action functional, not merely a finite polynomial. It can contain nonlocal structures if the cutoff is not far below thresholds or if massless degrees of freedom generate long-range effects. Still, when there is a separation of scales and no obstruction from infrared physics, the influence of high-momentum modes on low-momentum observables is local.

Then one writes

$$
S_\Lambda
=
\int d^d x\left[
\frac12 Z_\Lambda(\phi)(\partial_\mu\phi)^2
+U_\Lambda(\phi)
+a_\Lambda(\phi)(\partial_\mu\phi\partial^\mu\phi)^2
+\cdots
\right].
$$

The ellipsis contains every operator allowed by the symmetries. The exact RG equation tells us how the functions $U_\Lambda$, $Z_\Lambda$, $a_\Lambda$, and so on change as the cutoff is lowered.

A derivative expansion is not exact unless all derivative orders are kept. It is nevertheless powerful because irrelevant operators are often suppressed at long distances. The usefulness of the truncation is a physical statement about a regime, not an algebraic property of the equation.

## Dimensionless variables and fixed points

The Wilsonian flow becomes most transparent after rescaling to dimensionless variables. Let

$$
\tilde x=\Lambda x,
$$

and rescale the field according to

$$
\phi(x)=\Lambda^{(d-2+\eta)/2}\widetilde\phi(\tilde x),
$$

where $\eta$ is the anomalous dimension at a fixed point. Couplings become dimensionless combinations

$$
\widetilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i(\Lambda),
$$

where $\Delta_i$ is the scaling dimension of the operator $\mathcal O_i$ near the fixed point.

The flow of the dimensionless couplings has the schematic form

$$
\partial_\ell\widetilde g_i
=(d-\Delta_i)\widetilde g_i+\text{operator mixing and nonlinear terms}.
$$

A fixed point is a cutoff action $S_*$ whose dimensionless form does not change under the complete RG step:

$$
\partial_\ell S_*=0.
$$

At a fixed point, changing the cutoff and rescaling back gives the same theory. This is the Wilsonian meaning of scale invariance.

## From exact equations to beta functions

To extract ordinary beta functions, choose a basis of operators and project the functional equation onto it:

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

Substituting this expansion into the exact RG equation gives a formal infinite system

$$
\partial_\ell g_i=\mathcal B_i(g_1,g_2,\ldots).
$$

The functions $\mathcal B_i$ are Wilsonian beta functions in the IR flow convention. They differ by signs and coordinate choices from the beta functions commonly used in renormalized perturbation theory, but the physical scaling exponents at fixed points agree when computed consistently.

For example, in scalar $\phi^4$ theory near four dimensions, projecting onto the mass term and quartic interaction recovers the familiar flow of the relevant mass parameter and the marginally relevant or irrelevant quartic coupling, depending on the dimension and normalization. Keeping more operators refines the flow and reveals how irrelevant couplings feed into subleading corrections.

The exact RG therefore explains a useful tension:

$$
\text{the exact theory lives in infinite-dimensional theory space,}
$$

but

$$
\text{long-distance universal data are often finite-dimensional.}
$$

That tension is not a bug. It is the reason renormalization is predictive.

## Scheme dependence

Exact RG equations are not unique. A change of cutoff function, blocking kernel, field normalization, or flow variable changes the equation. Even the definition of the Wilsonian action can be changed by quasi-local field redefinitions.

This scheme dependence is expected. Theory space has coordinates, and exact RG equations are vector fields written in those coordinates. A different regulator gives a different coordinate representation of the same physical flow.

Quantities that should not depend on the RG scheme include:

| Object | Scheme status |
|---|---|
| existence of a physical fixed point | invariant, though approximations may obscure it |
| critical exponents | invariant at an exact fixed point |
| universal amplitude ratios | invariant when defined physically |
| irrelevant operator spectrum at a fixed point | invariant up to basis choices |
| individual couplings $g_i(\Lambda)$ | scheme dependent |
| truncated beta functions | scheme dependent beyond protected coefficients |

This is why an exact RG calculation must state both the regulator and the projection scheme if numerical values are quoted.

## Relation to perturbative renormalization

Perturbative renormalization often begins with divergent loop integrals and introduces counterterms. Exact RG begins with a finite cutoff and asks how the action changes as the cutoff changes. The two languages are compatible.

In perturbation theory, logarithmic divergences become beta functions. In Wilsonian RG, the same logarithms arise from accumulating contributions over many infinitesimal momentum shells:

$$
\int_{\Lambda_{\mathrm{IR}}}^{\Lambda_{\mathrm{UV}}}\frac{d\Lambda}{\Lambda}
=\log\frac{\Lambda_{\mathrm{UV}}}{\Lambda_{\mathrm{IR}}}.
$$

The Wilsonian language also sees power-law cutoff dependence directly. Dimensional regularization with minimal subtraction often hides such power sensitivity, but the Wilsonian action remembers which relevant operators must be tuned to approach a critical surface.

In short:

$$
\text{counterterms cancel regulator dependence in a chosen scheme,}
$$

while

$$
\text{exact RG describes how the whole cutoff action changes with scale.}
$$

They are not rivals. They are different views of the same scale dependence.

## Relation to functional RG

Functional RG usually refers to exact flow equations for scale-dependent effective actions, especially the effective average action $\Gamma_k$. The most common equation is the Wetterich equation,

$$
\partial_t\Gamma_k
=
\frac12\operatorname{Tr}\left[
\left(\Gamma_k^{(2)}+R_k\right)^{-1}\partial_t R_k
\right].
$$

Polchinski's equation evolves a Wilsonian action $S_\Lambda$ with a UV cutoff. The Wetterich equation evolves an effective action $\Gamma_k$ with an infrared regulator. They are related conceptually, and in appropriate formulations they are related by Legendre-type transformations, but they are not the same object.

The next page gives a preview of functional RG from the effective-average-action side.

## Common pitfalls

**Thinking exact means numerically exact.** The equation is exact. A finite truncation of it is not.

**Forgetting the rescaling step.** Integrating out modes lowers the cutoff. To identify fixed points and relevance, one must also rescale coordinates and fields.

**Confusing Wilsonian beta functions with MS beta functions.** They describe related physics in different coordinates and often with different flow-time signs.

**Truncating without checking stability.** A truncation is a physical approximation. Good practice checks dependence on regulator shape, field parametrization, operator basis, and truncation order.

**Treating the cutoff action as an observable.** $S_\Lambda$ is a scale-dependent description. Observables are extracted after specifying how external operators and sources are represented.

**Assuming locality automatically.** Locality of the Wilsonian action follows when high-momentum modes are integrated out in a regime with adequate scale separation. Massless thresholds and long-distance singularities can require care.

## Relations to other pages

[Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/) gives the perturbative shell-integration picture that exact RG turns into a functional equation. [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) supplies the geometric language: the exact RG is a vector field on the space of actions. [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) explains why the infinite system can still yield finite predictive data.

The perturbative counterpart is [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/). The effective-action counterpart is [Functional Renormalization Group Preview](/renormalization-rg-eft/wilsonian-renormalization/functional-renormalization-group-preview/). The critical-phenomena use of fixed points continues in the Fixed Points and Critical Phenomena chapter.

## Research status

Exact RG equations are established mathematical and physical tools. Their use as formal identities is standard. Their practical use depends on approximation strategies: derivative expansions, vertex expansions, polynomial truncations, large-$N$ limits, numerical discretizations, and rigorous bounds.

Active work includes improving truncations, controlling regulator dependence, applying functional RG to strongly coupled many-body systems, formulating gauge-invariant flows, connecting exact RG to constructive field theory, and using RG fixed points in asymptotic-safety scenarios. Many applications are powerful but approximation-dependent, so conclusions should be read with the stated truncation in mind.

## Exercises

### Exercise 1: Shell support of the differentiated propagator

Let

$$
C_\Lambda(p)=\frac{K(p^2/\Lambda^2)}{p^2+m^2},
$$

where $K(z)$ is approximately $1$ for $z\ll1$ and rapidly decays for $z\gg1$. Show that

$$
\dot C_\Lambda(p)=-\Lambda\frac{\partial C_\Lambda(p)}{\partial\Lambda}
$$

is concentrated near $p^2\sim\Lambda^2$ if $K$ changes mainly near $z\sim1$.

<details><summary><strong>Solution</strong></summary>

Only the cutoff function depends on $\Lambda$, so

$$
-\Lambda\frac{\partial}{\partial\Lambda}K(p^2/\Lambda^2)
=
2\frac{p^2}{\Lambda^2}K'(p^2/\Lambda^2).
$$

Thus

$$
\dot C_\Lambda(p)=
\frac{2(p^2/\Lambda^2)K'(p^2/\Lambda^2)}{p^2+m^2}.
$$

If $K'(z)$ is appreciable only in the transition region $z\sim1$, then $\dot C_\Lambda(p)$ is appreciable only for $p^2\sim\Lambda^2$. This is why the exact RG equation is local in scale.

</details>

### Exercise 2: A tadpole from the loop term

Take

$$
S^I_\Lambda[\phi]
=\int d^d x\,\frac{u_\Lambda}{4!}\phi^4(x).
$$

Use the loop term in Polchinski's equation to show that a contribution proportional to $\phi^2$ is generated.

<details><summary><strong>Solution</strong></summary>

The second functional derivative of the quartic interaction is

$$
\frac{\delta^2 S^I_\Lambda}{\delta\phi(x)\delta\phi(y)}
=\frac{u_\Lambda}{2}\phi^2(x)\delta^{(d)}(x-y).
$$

Substituting this into

$$
-\frac12\operatorname{Tr}\left(\dot C_\Lambda
\frac{\delta^2 S^I_\Lambda}{\delta\phi\,\delta\phi}\right)
$$

gives

$$
-\frac{u_\Lambda}{4}\dot C_\Lambda(x,x)
\int d^d x\,\phi^2(x),
$$

up to the conventional normalization of the coincident kernel. This is a shell version of a tadpole mass correction. The exact coefficient depends on the cutoff kernel, but the lesson is universal: a quartic interaction generates a quadratic term unless a symmetry forbids it.

</details>

### Exercise 3: Fixed point versus no running couplings

Explain why $\partial_\ell S_*=0$ for the dimensionless action does not imply that all dimensionful couplings in the original action are constant.

<details><summary><strong>Solution</strong></summary>

A Wilsonian fixed point is defined after integrating out modes and rescaling coordinates and fields. Dimensionless couplings are constant at the fixed point. Dimensionful couplings contain explicit powers of the cutoff. If

$$
\widetilde g_i=\Lambda^{\Delta_i-d}g_i
$$

is constant, then

$$
g_i(\Lambda)=\Lambda^{d-\Delta_i}\widetilde g_i.
$$

Unless $\Delta_i=d$, the dimensionful coupling changes with $\Lambda$ even though the dimensionless theory is fixed. The fixed point means scale invariance after measuring all quantities in cutoff units.

</details>

## References

- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- F. J. Wegner and A. Houghton, "Renormalization Group Equation for Critical Phenomena," *Physical Review A* **8** (1973) 401–412.
- J. Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984) 269–295.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, RG equations, and critical phenomena.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, sliding scales, fixed points, and critical phenomena.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the Wilson action, power counting, and exact RG discussion.
- O. J. Rosten, "Fundamentals of the Exact Renormalization Group," *Physics Reports* **511** (2012) 177–272.

## Version history

- 2026-06-17: First polished draft. Added Polchinski-equation conventions, interpretation of exactness, relation to theory space, perturbative beta functions, and functional RG.
