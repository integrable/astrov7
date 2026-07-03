---
title: "Renormalized Lagrangian"
description: "How a regulated bare Lagrangian is rewritten as renormalized terms plus local counterterms for perturbative calculations."
sidebar:
  label: "Renormalized Lagrangian"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§18–29; Schwartz chs. 18–23; Weinberg Vol. I ch. 12; Zinn-Justin, renormalization chapters."
topics:
  - renormalized Lagrangian
  - bare Lagrangian
  - counterterm Lagrangian
  - field renormalization
  - parameter renormalization
canonicalTopics:
  - renormalized-lagrangian
  - counterterm-lagrangian
  - bare-and-renormalized-parameters
  - renormalized-perturbation-theory
researchStatus:
  established:
    - "Rewriting a regulated bare Lagrangian as a renormalized Lagrangian plus local counterterms is the standard organization of perturbative renormalization."
  active:
    - "Bookkeeping becomes more delicate in gauge theories, EFTs with large operator bases, chiral theories, unstable-particle schemes, curved backgrounds, and automated multi-loop calculations."
---

## Summary

A **renormalized Lagrangian** is the part of a regulated bare Lagrangian written in terms of renormalized fields and renormalized parameters. The remaining local terms form the **counterterm Lagrangian**. In symbols,

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}.
$$

This equation is the workbench of renormalized perturbation theory. The left side is the regulated bare theory. The right side is a calculational split: $\mathcal L_{\text{ren}}$ gives the ordinary propagators and interaction vertices, while $\mathcal L_{\text{ct}}$ gives additional vertices whose coefficients are chosen order by order to cancel regulator dependence and implement a renormalization scheme.

For scalar $\phi^4$ theory in $d=4-2\epsilon$, a standard convention is

$$
\mathcal L_0
=\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-\frac12 Z_{m^2}m^2\phi^2
-\frac{\mu^{2\epsilon}Z_\lambda\lambda}{4!}\phi^4.
$$

Writing

$$
Z_\phi=1+\delta Z,
\qquad
Z_{m^2}m^2=m^2+\delta m^2,
\qquad
Z_\lambda\lambda=\lambda+\delta\lambda,
$$

gives

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

The split is not unique. Its non-uniqueness is exactly the freedom to choose a renormalization scheme.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![A bare regulated Lagrangian is rewritten as a renormalized Lagrangian plus a counterterm Lagrangian; ordinary vertices and counterterm vertices combine to produce finite renormalized amplitudes](/figures/renormalization-rg-eft/renormalized-lagrangian-split.svg)

<figcaption>

A renormalized Lagrangian is a calculational split of the regulated local theory. Ordinary vertices from $\mathcal L_{\text{ren}}$ and counterterm vertices from $\mathcal L_{\text{ct}}$ combine to produce finite scheme-defined Green functions and amplitudes.

</figcaption>
</figure>

## Prerequisites

You should know [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/). You should also keep [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/) nearby, since this page is the first place where that distinction becomes a routine calculation tool.

The conventions are those of [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, $\hbar=c=1$, dimensional regularization with $d=4-2\epsilon$ when used, and

$$
\frac{1}{\bar\epsilon}\equiv \frac{1}{\epsilon}-\gamma_E+\log(4\pi).
$$

## Core idea

The bare Lagrangian is the regulated local expression that defines the perturbative theory before renormalization. For example,

$$
\mathcal L_0
=\frac12\partial_\mu\phi_0\partial^\mu\phi_0
-\frac12m_0^2\phi_0^2
-\frac{\lambda_0}{4!}\phi_0^4
$$

is written in terms of bare quantities $\phi_0,m_0^2,\lambda_0$. Loop calculations using this Lagrangian produce regulator-dependent expressions. The point of renormalized perturbation theory is to trade the bare quantities for renormalized quantities plus counterterms.

The replacement has the schematic form

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=m_0^2(m^2,\lambda,\epsilon),
\qquad
\lambda_0=\mu^{2\epsilon}\lambda_0(\lambda,\epsilon).
$$

After this change of variables, the same bare theory can be written as

$$
\mathcal L_0(\phi_0,m_0^2,\lambda_0)
=\mathcal L_{\text{ren}}(\phi,m^2,\lambda,\mu)
+\mathcal L_{\text{ct}}(\phi,\delta Z,\delta m^2,\delta\lambda,\mu).
$$

This is not a physical decomposition into "real interactions" and "fake interactions." It is a bookkeeping decomposition. The counterterm vertices are as much a part of the perturbative calculation as loop vertices. The final prediction only has meaning after both are included.

:::note[The basic mental model]
Use $\mathcal L_{\text{ren}}$ to draw the ordinary diagrams. Use $\mathcal L_{\text{ct}}$ to draw local counterterm diagrams. Choose the counterterms so that the sum is finite and satisfies the chosen renormalization conditions.
:::

## Setup and conventions

We work with local Lagrangians and ordinary perturbation theory. The bare regulated theory is written as

$$
S_0=\int d^d x\,\mathcal L_0.
$$

For a set of fields $\Phi^A$ and couplings $g^i$, the general pattern is

$$
\Phi_0^A=(Z^{1/2})^A{}_B\Phi^B,
\qquad
 g_0^i=\mu^{\kappa_i\epsilon}F^i(g,\epsilon),
$$

where $\kappa_i$ is fixed by dimensional analysis. The functions $F^i$ contain poles in $\epsilon$ in minimal-subtraction-like schemes, and may also contain finite parts in other schemes.

The action is then expanded as

$$
S_0=S_{\text{ren}}+S_{\text{ct}}.
$$

In perturbation theory, $S_{\text{ren}}$ defines the free propagators and ordinary interaction vertices. $S_{\text{ct}}$ is treated perturbatively. Its coefficients are expanded in loops:

$$
\delta Z=\delta Z^{(1)}+\delta Z^{(2)}+\cdots,
\qquad
\delta\lambda=\delta\lambda^{(1)}+\delta\lambda^{(2)}+\cdots.
$$

Here $\delta Z^{(L)}$ and $\delta\lambda^{(L)}$ are of $L$-loop order. This notation is useful even when the expansion parameter is not written explicitly.

Different books distribute factors of $Z_\phi$ differently among $Z_{m^2}$ and $Z_\lambda$. That is convention, not physics. What matters is the full relation between the bare regulated Lagrangian and the renormalized one.

## The scalar template

The simplest useful template is real scalar $\phi^4$ theory. Start with

$$
\mathcal L_0
=\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-\frac12 Z_{m^2}m^2\phi^2
-\frac{\mu^{2\epsilon}Z_\lambda\lambda}{4!}\phi^4.
$$

The notation is chosen so that $\phi,m^2,\lambda$ are renormalized quantities. The constants $Z_\phi,Z_{m^2},Z_\lambda$ are adjusted so that finite renormalized Green functions are obtained in the chosen scheme.

Now define

$$
Z_\phi=1+\delta Z,
\qquad
Z_{m^2}m^2=m^2+\delta m^2,
\qquad
Z_\lambda\lambda=\lambda+\delta\lambda.
$$

Then

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

The renormalized kinetic term is normalized canonically. That is a choice of field normalization. The mass term and quartic interaction are written using the renormalized parameters that will be fixed by some rule: physical pole conditions, momentum-subtraction conditions, minimal subtraction, or another scheme.

One can also write the same information in bare-field notation:

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=\frac{Z_{m^2}}{Z_\phi}m^2,
\qquad
\lambda_0=\mu^{2\epsilon}\frac{Z_\lambda}{Z_\phi^2}\lambda.
$$

This form makes clear that the original bare symbols are not discarded. They are expressed in terms of renormalized coordinates and regulator-dependent conversion factors.

## Counterterm vertices

Counterterms are local operators, so they enter Feynman diagrams as local vertices. In the scalar example, the quadratic counterterms give a two-point insertion. In momentum space the corresponding rule is

$$
i\left(\delta Z\,p^2-\delta m^2\right),
$$

with momentum $p$ flowing through the insertion. The quartic counterterm gives a four-point vertex

$$
-i\mu^{2\epsilon}\delta\lambda.
$$

Thus the renormalized two-point 1PI function has the schematic form

$$
\Gamma_R^{(2)}(p^2)
=p^2-m^2
+\Pi_{\text{loops}}(p^2)
+\delta Z\,p^2-\delta m^2,
$$

where $\Pi_{\text{loops}}$ denotes loop corrections in the chosen convention. The renormalized four-point 1PI function has the schematic form

$$
\Gamma_R^{(4)}
=-\mu^{2\epsilon}\lambda
+\Gamma_{\text{loops}}^{(4)}
-\mu^{2\epsilon}\delta\lambda.
$$

These formulas are schematic because different authors include different factors of $i$ in the definitions of $\Gamma^{(n)}$ and amplitudes. The structural point is convention independent: loop graphs and counterterm graphs must be summed at the same perturbative order.

## Loop-order bookkeeping

Counterterms are determined recursively. At one loop, include one-loop diagrams from $\mathcal L_{\text{ren}}$ and the one-loop parts of the counterterms:

$$
\text{one-loop renormalized answer}
=\text{one-loop graphs}+\text{one-loop counterterms}.
$$

At two loops, include genuine two-loop diagrams, diagrams with one insertion of a one-loop counterterm, and the two-loop counterterms:

$$
\text{two-loop renormalized answer}
=\text{two-loop graphs}
+\text{one-loop graphs with }\delta^{(1)}\text{ insertions}
+\text{two-loop counterterms}.
$$

This recursive structure is one reason locality is so powerful. The divergences left after lower-order subtractions are again local, so they can be canceled by counterterms of the same local form allowed by the theory.

A common beginner mistake is to compute a loop graph, write down a counterterm that cancels it, and then forget that the counterterm is a vertex in higher-order diagrams. Counterterms are not one-time erasers. They are part of the Lagrangian used in the perturbative expansion.

## What is held fixed?

The bare Lagrangian is the object held fixed when deriving renormalization group equations. For a dimensionless coupling,

$$
\beta_g=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare}}.
$$

The phrase "at fixed bare parameters" means that $g_0$ is not changed while $\mu$ and $g(\mu)$ are varied. This is possible because the same bare regulated theory can be described using different renormalized coordinates at different $\mu$.

For example,

$$
\lambda_0=\mu^{2\epsilon}Z_\lambda(\lambda,\epsilon)\lambda
$$

is independent of $\mu$ when the bare theory is fixed. Differentiating this equation with respect to $\mu$ gives the beta function. The counterterm Lagrangian is therefore not just a cancellation device; it is the place where the dependence of renormalized parameters on $\mu$ is encoded.

This also explains why $\mu$ is not a physical cutoff. Changing $\mu$ changes the coordinates used to describe the same regulated bare theory. Changing a Wilsonian cutoff $\Lambda$ changes which modes are explicit. The two ideas are related but not identical.

## Minimal subtraction as a first example

In dimensional regularization, ultraviolet logarithmic divergences appear as poles in $\epsilon$. A minimal-subtraction scheme chooses counterterms that remove only pole parts. In $\overline{\mathrm{MS}}$, the common combination

$$
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log(4\pi)
$$

is subtracted instead.

For scalar $\phi^4$ theory in the normalization above, the one-loop $\overline{\mathrm{MS}}$ counterterms have the form

$$
\delta Z=O(\lambda^2),
\qquad
\delta m^2=\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^2),
\qquad
\delta\lambda=\frac{3\lambda^2}{16\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^3).
$$

The precise signs and factors depend on the convention used for defining the 1PI functions and counterterm symbols, but the pattern is robust: the two-point function fixes mass and field counterterms, while the four-point function fixes the quartic counterterm.

The fact that $\delta Z$ begins at $O(\lambda^2)$ in four-dimensional $\phi^4$ theory is special. It happens because the one-loop self-energy is momentum independent. In Yukawa theory, QED, and Yang–Mills theory, field-strength renormalization already appears at one loop.

## Renormalization conditions

The counterterms are not fully specified by the demand that divergences disappear. Their finite parts must also be chosen. A **renormalization condition** is the rule that does this.

An on-shell mass condition for a stable scalar particle might require that the inverse propagator vanish at the physical pole:

$$
\Gamma_R^{(2)}(p^2=m_{\text{phys}}^2)=0.
$$

A residue condition might require

$$
\left.\frac{d\Gamma_R^{(2)}}{dp^2}\right|_{p^2=m_{\text{phys}}^2}=1.
$$

A momentum-subtraction condition for a four-point function might define the renormalized coupling at a Euclidean subtraction point:

$$
\Gamma_R^{(4)}(p_i)\big|_{p_i\text{ at subtraction point}}
=-\lambda.
$$

Minimal subtraction instead fixes finite parts by refusing to subtract them. This is less directly physical but often far more efficient, especially for RG equations and gauge-theory calculations.

The renormalized Lagrangian by itself therefore does not define the scheme. The scheme is defined by the Lagrangian, the regulator, and the rule for the counterterms.

## Multiple fields and matrices

When several fields carry the same quantum numbers, field renormalization can be matrix-valued:

$$
\Phi_0^A=(Z^{1/2})^A{}_B\Phi^B.
$$

Mass terms and couplings can also mix. For scalar fields $\Phi^A$, the quadratic terms may be written

$$
\mathcal L_{\text{quad}}
=\frac12 Z_{AB}\partial_\mu\Phi^A\partial^\mu\Phi^B
-\frac12 M^2_{AB}\Phi^A\Phi^B.
$$

Renormalization then includes diagonalization, field redefinitions, mixing angles, and possibly nontrivial residue matrices. Similar issues appear in flavor physics, neutrino mixing, neutral gauge boson mixing, composite-operator bases, and EFT Wilson-coefficient bases.

The single-field formulas are therefore templates, not the whole story. The mature version of the statement is:

$$
\text{renormalization is local reparametrization in the space of fields and couplings.}
$$

## Gauge-theory caveats

In gauge theories, the renormalized Lagrangian must respect gauge-fixed identities such as Ward, Slavnov–Taylor, or BRST identities. This constrains the allowed counterterms. For example, in QED the Ward identity relates vertex and fermion wavefunction renormalization in common conventions. In non-Abelian gauge theory, the counterterms must fit the gauge-fixed Yang–Mills structure, including ghost and gauge-fixing terms.

This is why gauge-theory renormalization is not merely scalar renormalization with more indices. The local counterterm logic still applies, but the allowed local terms are restricted by symmetry and cohomology. Later pages in Gauge Theories and RG handle this carefully.

There is also an infrared caveat. Renormalized perturbation theory removes UV regulator dependence. It does not automatically make massless scattering amplitudes infrared finite. Soft and collinear divergences require inclusive observables, factorization, or other infrared-sensitive definitions.

## Common pitfalls

**Thinking the counterterm Lagrangian is optional.** Once loops are included, $\mathcal L_{\text{ct}}$ is part of the perturbative definition. Omitting it gives regulator-dependent answers.

**Thinking the split is unique.** The equation $\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}$ depends on the chosen renormalized coordinates. Different schemes split the same bare theory differently.

**Treating $Z$ factors as observables.** A $Z$ factor depends on the field normalization, regulator, and scheme. Pole residues can be physical in suitable situations, but generic $Z$ factors are not measured directly.

**Forgetting counterterm insertions at higher loops.** Lower-order counterterms appear inside higher-order diagrams. They are vertices, not annotations in the margin.

**Calling minimal subtraction a measurement.** Minimal subtraction defines parameters cleanly, but those parameters must still be related to measured quantities by a calculation.

**Confusing UV and IR problems.** A UV counterterm can make a Green function UV finite while an amplitude still has infrared divergences.

## Relations to other pages

This page turns the local-counterterm idea from [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) into the standard perturbative bookkeeping device. The next page, [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/), explains how finite parts are fixed.

[Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/) and [$\overline{\mathrm{MS}}$ Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/) specialize this framework to dimensional regularization. [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) expands the meaning of $Z_\phi$. [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/) treats the parameter relations systematically.

The [Renormalization Group Equations](/renormalization-rg-eft/renormalization-group-equations/) chapter begins from the fact that bare quantities do not depend on the arbitrary scale $\mu$. The [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) chapter generalizes the same split to an infinite tower of local operators organized by power counting.

## Research status

The basic renormalized-Lagrangian framework is settled textbook material. It is one of the most tested pieces of perturbative QFT, from simple scalar examples to precision electroweak and QCD calculations.

The frontiers are not about whether the split works. They are about how to manage it in hard settings: high-loop gauge-theory computations, chiral gauge theories and $\gamma^5$, unstable-particle schemes, EFT operator bases with thousands of terms, automated renormalization pipelines, finite-temperature and real-time formalisms, curved-spacetime counterterms, and nonperturbative definitions of continuum limits.

The philosophical lesson also remains alive: the renormalized Lagrangian is not a microscopic confession from nature. It is a scale- and scheme-dependent coordinate system for extracting finite predictions from local quantum dynamics.

## Exercises

### Exercise 1: Splitting a bare scalar Lagrangian

Start from

$$
\mathcal L_0
=\frac12 Z_\phi(\partial\phi)^2
-\frac12 Z_{m^2}m^2\phi^2
-\frac{\mu^{2\epsilon}Z_\lambda\lambda}{4!}\phi^4.
$$

Use

$$
Z_\phi=1+\delta Z,
\qquad
Z_{m^2}m^2=m^2+\delta m^2,
\qquad
Z_\lambda\lambda=\lambda+\delta\lambda
$$

to derive $\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}$.

<details><summary><strong>Solution</strong></summary>

Substitute the definitions into the bare Lagrangian:

$$
\mathcal L_0
=\frac12(1+\delta Z)(\partial\phi)^2
-\frac12(m^2+\delta m^2)\phi^2
-\frac{\mu^{2\epsilon}(\lambda+\delta\lambda)}{4!}\phi^4.
$$

Separate the terms without deltas from the terms with deltas:

$$
\mathcal L_{\text{ren}}
=\frac12(\partial\phi)^2
-\frac12m^2\phi^2
-\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z(\partial\phi)^2
-\frac12\delta m^2\phi^2
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

This is exactly the desired split.

</details>

### Exercise 2: The two-point counterterm insertion

Using the quadratic counterterm

$$
\mathcal L_{\text{ct},2}
=\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2,
$$

show that the momentum-space two-point insertion is proportional to

$$
i(\delta Z p^2-\delta m^2).
$$

<details><summary><strong>Solution</strong></summary>

Fourier transform the field. A derivative acting on a mode produces a momentum factor. With the mostly-minus convention and momentum $p$ flowing through the two-point insertion, the kinetic counterterm contributes a factor proportional to $\delta Z p^2$, while the mass counterterm contributes $-\delta m^2$.

The Feynman rule is obtained by multiplying the interaction term in the action by $i$. Therefore the two-point counterterm insertion is

$$
i(\delta Z p^2-\delta m^2).
$$

Different sign conventions for defining the self-energy can move this expression into formulas with the opposite sign, but the insertion itself follows from the chosen $\mathcal L_{\text{ct}}$.

</details>

### Exercise 3: Why lower-order counterterms reappear

Suppose $\delta\lambda=\delta\lambda^{(1)}+\delta\lambda^{(2)}+\cdots$. Explain why a two-loop four-point calculation must include both genuine two-loop diagrams and one-loop diagrams with a $\delta\lambda^{(1)}$ insertion.

<details><summary><strong>Solution</strong></summary>

The counterterm $\delta\lambda^{(1)}$ is a vertex in the Lagrangian. Once it has been introduced at one loop, it can appear in higher-order diagrams just like any other vertex.

At two-loop order, there are three kinds of contributions:

$$
\text{genuine two-loop graphs},
\qquad
\text{one-loop graphs with one one-loop counterterm insertion},
\qquad
\text{two-loop counterterm graphs}.
$$

The one-loop counterterm insertion subtracts subdivergences associated with lower-order UV subgraphs. The two-loop counterterm cancels the remaining local overall divergence. This recursive structure is the operational content of perturbative renormalization.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on counterterms, renormalization, and physical perturbation theory.
- Mark Srednicki, *Quantum Field Theory*, sections on higher-order corrections, renormalizability, renormalization schemes, the RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 18–23, especially the discussion of mass renormalization, counterterms, and renormalized perturbation theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for a systematic treatment of renormalization in perturbation theory.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the field-theoretic and statistical-mechanics perspective on renormalization.
- John Collins, *Renormalization*, for a detailed all-orders treatment.

## Version history

- 2026-06-17: First polished draft. Introduced the renormalized-plus-counterterm split, scalar $\phi^4$ template, counterterm vertices, loop-order bookkeeping, minimal-subtraction example, and exercises.
