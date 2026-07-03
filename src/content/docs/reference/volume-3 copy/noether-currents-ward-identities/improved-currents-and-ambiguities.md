---
title: "Improved Currents and Ambiguities"
description: "Explains why Noether currents are not unique, which improvements leave charges unchanged, and which ambiguities matter for contact terms, stress tensors, backgrounds, and boundaries."
sidebar:
  label: "Improved Currents"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman lectures on conserved-current non-uniqueness; Srednicki §22; Weinberg Vol. I and II on currents, stress tensors, and gauge-theory identities; standard QFT background-field formalism."
topics:
  - improved currents
  - current ambiguities
  - Noether currents
  - stress tensor improvement
  - contact terms
  - background fields
canonicalTopics:
  - current-improvement
  - noether-current-ambiguity
  - stress-tensor-improvement
  - equation-of-motion-operator
researchStatus:
  established:
    - "Noether currents are defined only up to identically conserved improvements, equation-of-motion terms, total-derivative convention choices, and renormalization-scheme choices."
  active:
    - "In modern QFT, the physically useful current representative can depend on background fields, boundary conditions, anomaly scheme, operator-renormalization scheme, and the generalized-symmetry framework being used."
---

## Summary

Noether's theorem gives a current. It does **not** give a unique current.

If $j^\mu$ is conserved, then so is

$$
j'^\mu=j^\mu+\partial_\nu B^{\mu\nu},
\qquad
B^{\mu\nu}=-B^{\nu\mu},
$$

because

$$
\partial_\mu\partial_\nu B^{\mu\nu}=0
$$

identically. This is the simplest and most important **improvement ambiguity**.

There are more. Currents can also change by terms proportional to the equations of motion, by changing the Lagrangian by a total derivative, by redefining the symmetry transformation by a trivial symmetry, by choosing a different renormalized composite-operator basis, or by adding local counterterms to a background-field generating functional.

The right lesson is not “currents are fake.” The right lesson is:

$$
\text{symmetry}
\quad\neq\quad
\text{a unique local formula for }j^\mu.
$$

A current is a representative of a symmetry. The invariant content is usually found in the charge action, Ward identities, background-field response, surface operators, anomaly class, or boundary flux — and even those require hypotheses.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic map of current representatives related by improvements, equation-of-motion terms, total derivatives, operator mixing, and counterterms, with invariants and caveats listed below.](/figures/symmetry-anomalies-topology/current-ambiguity-map.svg)

<figcaption>

A Noether current is a representative inside an equivalence class. Improvements often preserve charges and separated-point conservation, but contact terms, boundaries, background-field couplings, stress tensors, and anomalies can distinguish representatives.

</figcaption>
</figure>

## Prerequisites

Read [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/) first. You should know the convention

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu,
\qquad
Q_a=\int d^{d-1}\mathbf x\,j_a^0,
$$

and you should be comfortable with integration by parts and Gauss's theorem.

You do not need renormalization theory, anomaly theory, or BRST yet. This page previews all three only to explain why current ambiguities are not a pedantic classical footnote.

## Core idea

The current is local data. The symmetry is global and structural data. Local representatives are rarely unique.

The simplest reason is algebraic. If $B^{\mu\nu}$ is antisymmetric, then

$$
\partial_\mu\partial_\nu B^{\mu\nu}
=\frac12\partial_\mu\partial_\nu
\left(B^{\mu\nu}+B^{\nu\mu}\right)=0.
$$

Therefore

$$
j^\mu\mapsto j^\mu+\partial_\nu B^{\mu\nu}
$$

does not change the conservation law:

$$
\partial_\mu j^\mu=0
\quad\Longrightarrow\quad
\partial_\mu j'^\mu=0.
$$

For a spatial charge,

$$
Q'=\int d^{d-1}\mathbf x\,j'^0
=Q+\int d^{d-1}\mathbf x\,\partial_i B^{0i}.
$$

If the boundary integral vanishes, then

$$
Q'=Q.
$$

So an improvement can change the local current density without changing the charge. Tiny-looking? Sure. This tiny-looking fact is behind the Belinfante stress tensor, conformal stress-tensor improvements, scheme dependence of local current correlators, and several anomaly-current distinctions.

## Setup and conventions

We use the conventions of the previous page. A Noether current representative satisfies

$$
\partial_\mu j_a^\mu=-\mathcal E_I\delta_a\Phi^I.
$$

On shell,

$$
\partial_\mu j_a^\mu=0.
$$

An **improvement** is a local shift that does not change the conservation equation, at least after using the same equations of motion:

$$
j_a^\mu\longrightarrow j_a^\mu+\Delta j_a^\mu.
$$

The most common improvement is

$$
\Delta j_a^\mu=\partial_\nu B_a^{\mu\nu},
\qquad
B_a^{\mu\nu}=-B_a^{\nu\mu}.
$$

In differential-form language, with $J_a=\star j_a$, the improvement is

$$
J_a\longrightarrow J_a+d\Lambda_a,
$$

where $\Lambda_a$ is a $(d-2)$-form. Then

$$
dJ_a=0
\quad\Longrightarrow\quad
d(J_a+d\Lambda_a)=0.
$$

This is often the cleanest way to remember what is going on: adding an exact form does not change integrals over closed homologous surfaces, but it can change boundary terms.

:::note[Source note]
Coleman's QFT lectures emphasize early that conserved currents are not uniquely defined. Modern treatments often repackage the same fact as freedom to choose a current representative, a stress-tensor improvement, or a local counterterm in the generating functional. The formulas below keep the classical and quantum versions visibly connected.
:::

## Identically conserved improvements

Let

$$
j'^\mu=j^\mu+\partial_\nu B^{\mu\nu},
\qquad
B^{\mu\nu}=-B^{\nu\mu}.
$$

Then

$$
\partial_\mu j'^\mu
=\partial_\mu j^\mu+\partial_\mu\partial_\nu B^{\mu\nu}.
$$

Since derivatives commute and $B^{\mu\nu}$ is antisymmetric,

$$
\partial_\mu\partial_\nu B^{\mu\nu}=0.
$$

Thus

$$
\partial_\mu j'^\mu=\partial_\mu j^\mu.
$$

If $j^\mu$ is conserved, so is $j'^\mu$. If $j^\mu$ is conserved only on shell, then $j'^\mu$ is conserved on shell with the same equations of motion.

### Effect on the charge

The charge shift is

$$
\Delta Q
=\int_\Sigma d^{d-1}\mathbf x\,\partial_iB^{0i}.
$$

For $\Sigma=\mathbb R^{d-1}$, this is

$$
\Delta Q
=\int_{\partial\Sigma}dS_i\,B^{0i}.
$$

If $B^{0i}$ falls off sufficiently fast, $\Delta Q=0$. If not, the improvement changes a boundary charge.

This is the first warning that “same current up to improvement” depends on boundary conditions. On a compact spatial slice without boundary, exact improvements do not change the charge. On a space with boundary, an edge, an asymptotic region, a defect, or a puncture, they can.

### Effect on surface operators

In differential-form notation,

$$
Q(\Sigma)=\int_\Sigma J.
$$

An improvement $J\to J+d\Lambda$ changes

$$
Q(\Sigma)\to Q(\Sigma)+\int_\Sigma d\Lambda
=Q(\Sigma)+\int_{\partial\Sigma}\Lambda.
$$

For a closed surface $\partial\Sigma=0$, the charge does not change. If $\Sigma$ ends on a boundary or surrounds an excised defect, the improvement can contribute. This is why surface terms become real physics in theories with boundaries, defects, asymptotic symmetries, or extended operators.

## Equation-of-motion terms

A second ambiguity comes from adding terms proportional to the equations of motion.

Suppose

$$
\Delta j^\mu=M^{\mu I}\mathcal E_I
$$

for some local operator $M^{\mu I}$, possibly with derivatives arranged so that indices and statistics are correct. Classically, this vanishes on shell. Therefore it does not change the on-shell conservation law.

In quantum theory, equation-of-motion operators are subtler. In separated-point correlators they often vanish or reduce to contact terms. But at coincident points they can matter. A schematic Schwinger–Dyson identity says

$$
\left\langle \mathcal E_I(x)\mathcal X\right\rangle
\sim
i\left\langle \frac{\delta\mathcal X}{\delta\Phi^I(x)}\right\rangle
$$

in Lorentzian conventions, up to the usual regulator and contact-term qualifications. Thus an equation-of-motion improvement can change contact terms in Ward identities even when it does not change separated-point conservation.

This is one of the reasons contact terms deserve their own page. “Zero by the equations of motion” is not the same as “zero inside every distributional identity.”

:::caution[Equation-of-motion terms are not always disposable]
Dropping equation-of-motion operators is safe for many on-shell classical calculations and some separated-point quantum correlators. It is not automatically safe in local Ward identities, operator product expansions, composite-operator renormalization, or background-field response.
:::

## Total derivatives in the Lagrangian

Noether currents also change if we change the Lagrangian by a total derivative:

$$
\mathcal L\longrightarrow \mathcal L+\partial_\mu Y^\mu.
$$

The action changes only by a boundary term, so the bulk equations of motion are the same. But the variational boundary term changes:

$$
\theta^\mu\longrightarrow \theta^\mu+\delta Y^\mu.
$$

If the symmetry variation is $\delta_a$, the total-derivative term in $\delta_a\mathcal L$ also changes:

$$
K_a^\mu\longrightarrow K_a^\mu+\delta_aY^\mu.
$$

Naively this seems to leave

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu
$$

unchanged. Often it does. But when $Y^\mu$ depends on spacetime explicitly, when transformations act on background structures, when the symmetry is spacetime rather than internal, or when boundary conditions are part of the problem, total derivatives can shift the current by an improvement or boundary current.

This is why the phrase “up to a total derivative” is safe only after the boundary problem has been stated.

## Trivial symmetries

There is another classical ambiguity hiding in the phrase “the transformation law.” Some transformations vanish on shell or are proportional to the equations of motion. These are sometimes called **trivial symmetries**.

Schematic example:

$$
\delta_{\mathrm{triv}}\Phi^I
=A^{IJ}\mathcal E_J,
$$

where $A^{IJ}$ is antisymmetric in the appropriate graded DeWitt sense. Then

$$
\mathcal E_I\delta_{\mathrm{triv}}\Phi^I
=\mathcal E_I A^{IJ}\mathcal E_J=0
$$

up to signs and total derivatives, so the action is invariant for a formal reason. Such a transformation does not usually generate a new physical symmetry. Its Noether current is correspondingly an improvement or an equation-of-motion current.

This ambiguity becomes systematic in gauge theory and BRST/BV language. There, one distinguishes physical symmetries from redundancies and trivial transformations by cohomology. That is why the later gauge chapter is called Gauge Redundancy and BRST rather than “more symmetries.”

## Stress tensor improvements

The stress tensor is the most famous improved current.

The canonical stress tensor from translations is

$$
T^\mu{}_\nu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\partial_\nu\Phi^I
-\delta^\mu{}_\nu\mathcal L.
$$

It is conserved on shell:

$$
\partial_\mu T^\mu{}_\nu=0.
$$

But it may fail to be symmetric, gauge invariant, or suitably traceless. For Lorentz-invariant theories, one can often add the divergence of a spin-current expression to form the Belinfante–Rosenfeld tensor. Schematically,

$$
T_{\mathrm B}^{\mu\nu}
=T_{\mathrm{can}}^{\mu\nu}+\partial_\rho X^{\rho\mu\nu},
$$

with $X^{\rho\mu\nu}$ antisymmetric in the first two indices in a way that preserves conservation. The improved tensor is symmetric in many standard theories and is the one naturally coupled to a background metric.

For a scalar theory in $d$ dimensions, another common improvement is

$$
T_{\mu\nu}\longrightarrow
T_{\mu\nu}
+\xi\left(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu\right)\phi^2.
$$

The added term is identically conserved:

$$
\partial^\mu
\left[
\left(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu\right)\phi^2
\right]=0.
$$

For a massless scalar, choosing

$$
\xi=\frac{d-2}{4(d-1)}
$$

gives the standard conformal improvement, making the stress tensor traceless on shell.

:::note[Convention-sensitive source note]
Some references write the scalar stress-tensor improvement with the opposite sign, depending on whether the stress tensor is defined by $\delta S/\delta g_{\mu\nu}$ or $\delta S/\delta g^{\mu\nu}$ and on metric signature. The sign above is chosen so that the added flat-space tensor is $\xi(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu)\phi^2$ in mostly-minus conventions.
:::

## Internal currents versus stress tensors

Internal-symmetry currents and stress tensors share the same improvement logic, but stress tensors have extra structure.

An internal current has one spacetime index and one symmetry label:

$$
j_a^\mu.
$$

A stress tensor has two spacetime indices:

$$
T^\mu{}_\nu.
$$

For internal symmetries, the central question is usually whether the charge

$$
Q_a=\int_\Sigma \star j_a
$$

generates the correct transformation. For stress tensors, the corresponding charges generate translations, rotations, boosts, and sometimes scale or conformal transformations. That means symmetry of $T_{\mu\nu}$, trace properties, and coupling to geometry become physically meaningful.

This is why the stress tensor is not merely “one more Noether current.” It is the current for spacetime symmetry, and spacetime symmetry is tied to geometry.

## Renormalized current operators

In quantum field theory, currents are composite operators. Composite operators require renormalization.

A bare current formula such as

$$
j^\mu_{\mathrm{bare}}=\frac{\partial\mathcal L}{\partial(\partial_\mu\Phi^I)}\delta\Phi^I
$$

does not automatically define a finite operator at coincident points. A renormalized current may take the form

$$
[j^\mu]_{\mathrm R}
=Z_j j^\mu_{\mathrm{bare}}
+\sum_n c_n \mathcal O_n^\mu
+\partial_\nu B^{\mu\nu}_{\mathrm R}
+\text{equation-of-motion terms},
$$

where the $\mathcal O_n^\mu$ have the same quantum numbers and dimension allowed by the renormalization scheme.

For exact internal symmetries, Ward identities often protect the normalization of the conserved current. For example, a current that generates a compact symmetry has quantized charge assignments, so arbitrary multiplicative renormalization would be inconsistent. But local correlators involving currents can still have contact-term and scheme ambiguities.

The practical rule is:

$$
\text{charges are usually more invariant than local current representatives}.
$$

But even charges require control of domains, boundary conditions, infrared behavior, and gauge constraints.

## Background fields and scheme dependence

A clean modern way to define a current is to couple the theory to a background field $A_\mu^a$ and differentiate the generating functional:

$$
\langle j_a^\mu(x)\rangle_A
=\frac{\delta W[A]}{\delta A_\mu^a(x)}.
$$

This definition is powerful because it packages current correlators and Ward identities into background gauge invariance. But it also exposes a new ambiguity: one can add local counterterms to $W[A]$.

If

$$
W[A]\longrightarrow W[A]+W_{\mathrm{ct}}[A],
$$

then

$$
\langle j_a^\mu(x)\rangle_A
\longrightarrow
\langle j_a^\mu(x)\rangle_A
+\frac{\delta W_{\mathrm{ct}}[A]}{\delta A_\mu^a(x)}.
$$

The extra term is local in the background field. It changes contact terms and sometimes changes the distinction between different current conventions.

In anomaly theory this becomes especially important. The distinction between **consistent currents** and **covariant currents** is a choice of representative related by a local polynomial in background fields. The anomaly class is invariant; the current representative is not.

## Boundaries and edge terms

On a closed spatial slice, many improvements integrate to zero. With a boundary, they do not.

Suppose

$$
j'^\mu=j^\mu+\partial_\nu B^{\mu\nu}.
$$

Then

$$
Q'=Q+\int_{\partial\Sigma}dS_i\,B^{0i}.
$$

If $\partial\Sigma$ is a physical boundary, this extra term can be an edge charge. It may have to be included for the symmetry generator to be differentiable, for the variational principle to be well-defined, or for the algebra of charges to close.

This is not rare. It appears in gauge theory, gravity, Chern–Simons theory, Wess–Zumino–Witten models, asymptotic symmetries, and defect systems. In such settings, improvements are not merely cosmetic. They decide what lives at the edge.

The safe statement is therefore:

$$
j^\mu\sim j^\mu+\partial_\nu B^{\mu\nu}
$$

only after specifying which surfaces, boundary conditions, and charged defects are allowed.

## Example: improving a shift current by hand

For a free massless scalar,

$$
\mathcal L=\frac12\partial_\mu\phi\partial^\mu\phi,
$$

the shift symmetry $\delta\phi=1$ has current

$$
j^\mu=\partial^\mu\phi.
$$

Now choose an antisymmetric local tensor $B^{\mu\nu}=-B^{\nu\mu}$ and define

$$
j'^\mu=\partial^\mu\phi+\partial_\nu B^{\mu\nu}.
$$

The divergence is

$$
\partial_\mu j'^\mu
=\Box\phi+\partial_\mu\partial_\nu B^{\mu\nu}
=\Box\phi.
$$

So the improved current is conserved on the same equation of motion, $\Box\phi=0$.

If $B^{0i}$ vanishes fast enough at spatial infinity, $Q'=Q$. But if space has a boundary and $B^{0i}$ is nonzero there, the improved current changes the boundary charge. This toy example is almost too simple, which is why it is useful: the entire improvement mechanism is already visible.

## Example: conformal scalar stress tensor

Consider a massless real scalar in $d>2$ dimensions. The canonical stress tensor is

$$
T_{\mu\nu}^{\mathrm{can}}
=\partial_\mu\phi\partial_\nu\phi
-\frac12\eta_{\mu\nu}\partial_\rho\phi\partial^\rho\phi.
$$

Its trace is

$$
T_{\mathrm{can}\,\mu}^{\mu}
=\left(1-\frac d2\right)\partial_\rho\phi\partial^\rho\phi.
$$

Using the equation of motion $\Box\phi=0$, this is not zero as a local expression, but

$$
\partial_\rho\phi\partial^\rho\phi
=\frac12\Box\phi^2
$$

on shell. Therefore an improvement proportional to

$$
\left(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu\right)\phi^2
$$

can cancel the trace. With

$$
\xi=\frac{d-2}{4(d-1)},
$$

the improved stress tensor has vanishing trace on shell:

$$
T^\mu{}_\mu=0.
$$

This is why the conformal scalar requires an improved stress tensor. The symmetry was not missing; the canonical representative was not the best representative.

## What is invariant?

Several quantities are more invariant than a current formula, but each has hypotheses.

| Object | What is usually invariant | What can still change |
|---|---|---|
| Local conservation equation | $\partial_\mu j^\mu=0$ away from insertions | Contact terms and anomalies |
| Charge on a closed surface | $\int_\Sigma \star j$ | Boundary terms, defects, infrared issues |
| Action on operators | $\delta\mathcal O=i[Q,\mathcal O]$ | Domains, spontaneous breaking, gauge constraints |
| Separated-point correlators | Noncoincident singularity-free data | Contact terms and scheme-dependent local terms |
| Background response | Gauge-invariant structure of $W[A]$ | Local counterterms and current scheme |
| Anomaly class | Cohomology class or inflow theory | Representative, consistent versus covariant current |
| Stress-tensor charges | Poincaré generators | Local tensor representative, trace improvement, boundary charges |

The table is the mature version of the slogan “currents are not unique.” Not everything changes. But the thing that remains invariant is often not the bare current density.

## Common pitfalls

**Thinking improvement means unimportant.** Improvements are often unimportant for closed-surface charges, but they can be crucial for stress tensors, boundaries, defects, conformal symmetry, and background-field correlators.

**Using equations of motion inside contact terms.** Equation-of-motion operators can vanish at separated points while producing contact terms at coincident points. Ward identities are distributional statements, not just pointwise equations.

**Assuming the canonical stress tensor is the physical stress tensor.** The canonical tensor may fail to be symmetric, gauge invariant, or traceless. The tensor coupled to a background metric is often an improved one.

**Forgetting the boundary term in the charge.** If $Q$ changes by $\int_{\partial\Sigma}\Lambda$, the improvement is physical whenever $\partial\Sigma$ is physical.

**Confusing scheme dependence with arbitrariness.** Local counterterms change current representatives and contact terms, but not arbitrary physics. Scheme-independent quantities must be identified carefully.

**Expecting anomalies to disappear by improving the current.** Some apparent anomaly expressions move between current conservation and background variation under scheme changes. The anomaly class, when nontrivial, cannot be removed by a local improvement.

## Relations to other pages

This page refines [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/). It explains why that page's current formula is a representative rather than a unique answer.

The next pages on conserved charges and current conservation in correlation functions will use these ambiguities repeatedly. The charge page will ask when improvement terms vanish. The contact-term page will explain how equation-of-motion and counterterm ambiguities appear in local Ward identities.

The Background Fields and Gauging chapter will make scheme dependence sharper by defining currents as derivatives of $W[A]$. The Anomalies chapter will use the same language to distinguish anomaly representatives and current representatives.

The Spontaneous Symmetry Breaking chapter will use currents whose charges may fail to annihilate the vacuum or may be ill-defined because of infrared behavior. The Gauge Redundancy and BRST chapter will reinterpret trivial symmetries and equation-of-motion currents cohomologically.

## Research status

The classical improvement freedom is settled and textbook-standard. It is part of the basic language of field theory.

The active, research-level issues concern the contexts in which current representatives carry additional structure: boundaries, defects, generalized symmetries, anomaly inflow, curved-space QFT, hydrodynamic effective actions, non-Lagrangian theories, and categorical symmetry. In those settings, one often does not ask “what is the current?” in isolation. One asks which current representative is compatible with the chosen background fields, boundary conditions, counterterms, and operator algebra.

## Exercises

### Exercise 1: Prove that the improvement is identically conserved

Let $B^{\mu\nu}=-B^{\nu\mu}$. Prove that

$$
\partial_\mu\partial_\nu B^{\mu\nu}=0.
$$

<details><summary><strong>Solution</strong></summary>

Use the symmetry of commuting derivatives and the antisymmetry of $B$:

$$
\partial_\mu\partial_\nu B^{\mu\nu}
=\frac12\partial_\mu\partial_\nu
\left(B^{\mu\nu}+B^{\nu\mu}\right).
$$

But

$$
B^{\nu\mu}=-B^{\mu\nu},
$$

so the expression in parentheses vanishes. Hence

$$
\partial_\mu\partial_\nu B^{\mu\nu}=0.
$$

</details>

### Exercise 2: Compute the charge shift

Let

$$
j'^\mu=j^\mu+\partial_\nu B^{\mu\nu}.
$$

On a constant-time slice $\Sigma$, show that

$$
Q'-Q=\int_{\partial\Sigma}dS_i\,B^{0i}.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
Q'-Q
=\int_\Sigma d^{d-1}\mathbf x\,\partial_\nu B^{0\nu}.
$$

Since $B^{00}=0$ by antisymmetry,

$$
\partial_\nu B^{0\nu}=\partial_iB^{0i}.
$$

Therefore

$$
Q'-Q
=\int_\Sigma d^{d-1}\mathbf x\,\partial_iB^{0i}
=\int_{\partial\Sigma}dS_i\,B^{0i}.
$$

If the boundary term vanishes, the charges agree.

</details>

### Exercise 3: Conservation of the scalar stress-tensor improvement

Show that

$$
\Delta T_{\mu\nu}
=\xi(\eta_{\mu\nu}\Box-\partial_\mu\partial_\nu)\phi^2
$$

is identically conserved in flat spacetime:

$$
\partial^\mu\Delta T_{\mu\nu}=0.
$$

<details><summary><strong>Solution</strong></summary>

Compute directly:

$$
\partial^\mu\Delta T_{\mu\nu}
=\xi\left(\partial^\mu\eta_{\mu\nu}\Box\phi^2
-\partial^\mu\partial_\mu\partial_\nu\phi^2\right).
$$

The metric is constant, so

$$
\partial^\mu\eta_{\mu\nu}=\partial_\nu.
$$

Thus

$$
\partial^\mu\Delta T_{\mu\nu}
=\xi\left(\partial_\nu\Box\phi^2-\Box\partial_\nu\phi^2\right).
$$

In flat space, derivatives commute, so the two terms cancel:

$$
\partial_\nu\Box\phi^2=\Box\partial_\nu\phi^2.
$$

Therefore $\partial^\mu\Delta T_{\mu\nu}=0$ identically.

</details>

### Exercise 4: Contact-term warning from an equation of motion

In a path integral for a scalar field, explain schematically why an insertion of $\mathcal E(x)$, the equation of motion operator, can produce contact terms with an operator $\mathcal O(y)$.

<details><summary><strong>Solution</strong></summary>

A Schwinger–Dyson identity follows by changing variables in the path integral:

$$
0=\int D\phi\,\frac{\delta}{\delta\phi(x)}
\left(\mathcal O(y)e^{iS[\phi]}\right).
$$

Expanding the derivative gives

$$
0=\left\langle\frac{\delta\mathcal O(y)}{\delta\phi(x)}\right\rangle
+i\left\langle\mathcal O(y)\frac{\delta S}{\delta\phi(x)}\right\rangle.
$$

The equation of motion operator is $\mathcal E(x)=\delta S/\delta\phi(x)$ up to sign conventions. Thus

$$
\langle\mathcal E(x)\mathcal O(y)\rangle
\sim
i\left\langle\frac{\delta\mathcal O(y)}{\delta\phi(x)}\right\rangle
$$

up to convention-dependent signs. The functional derivative of a local operator at $y$ has support at $x=y$, so it is a contact term. Therefore equation-of-motion operators can vanish away from insertions while contributing to local Ward identities.

</details>

### Exercise 5: Improvement in differential-form notation

Let $J$ be a closed $(d-1)$-form and let $\Lambda$ be a $(d-2)$-form. Show that $J'=J+d\Lambda$ is closed, and show that the charge on a closed surface $\Sigma$ is unchanged.

<details><summary><strong>Solution</strong></summary>

Since $dJ=0$ and $d^2=0$,

$$
dJ'=dJ+d^2\Lambda=0.
$$

The charge changes by

$$
\Delta Q=\int_\Sigma d\Lambda.
$$

By Stokes' theorem,

$$
\Delta Q=\int_{\partial\Sigma}\Lambda.
$$

If $\Sigma$ is closed, $\partial\Sigma=0$, so

$$
\Delta Q=0.
$$

If $\Sigma$ has a boundary, this conclusion need not hold.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the discussion of symmetries and conservation laws. Useful for the basic warning that conserved currents are not uniquely defined.
- Sidney Coleman, *Aspects of Symmetry*. Classic applications of currents, current algebra, scale currents, and improved stress tensors.
- Mark Srednicki, *Quantum Field Theory*, §22. Concise treatment of continuous symmetries and current formulas.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I and Vol. II. Detailed symmetry-generator framework and gauge-theory identities, including stress tensors and background methods.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for composite operators, equations of motion, renormalization, and current insertions in the functional formalism.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*. Pedagogical discussion of Noether currents, stress tensors, Ward–Takahashi identities, and background-field methods.
- Callan, Coleman, and Jackiw, “A New Improved Energy-Momentum Tensor.” Classic reference for stress-tensor improvement in conformal field theory.

## Version history

- **2026-06-17:** Initial polished page on current improvements and ambiguities.
