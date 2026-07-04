---
title: "Counterterm Diagrams Preview"
description: "How counterterm vertices enter perturbative diagrams, cancel local ultraviolet divergences, and prepare the transition from bare perturbation theory to renormalized perturbation theory."
sidebar:
  label: "Counterterm Diagrams"
  order: 9
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14, 16–19, and 27; Coleman 2019, chs. 9, 15, 16, and 25; Weinberg 1995, Vol. I, chs. 10 and 12; Schwartz 2014, chs. 15–19; Zinn-Justin 2021, chs. 8–10"
topics:
  - counterterm diagrams
  - counterterms
  - renormalized perturbation theory
  - ultraviolet divergences
  - self-energy
  - vertex corrections
canonicalTopics:
  - counterterm-diagrams
  - counterterm-vertices
  - renormalized-perturbation-theory-preview
  - ultraviolet-divergence-cancellation
researchStatus:
  established:
    - "Counterterm diagrams and the organization of renormalized perturbation theory are textbook-standard in perturbative QFT."
  active:
    - "Gauge theories, composite operators, effective field theories, curved backgrounds, and nonperturbative definitions add structural constraints that are treated in later volumes."
---

## Summary

A **counterterm diagram** is an ordinary Feynman diagram containing at least one vertex from the counterterm part of the Lagrangian. Counterterms are introduced by splitting bare parameters into renormalized parameters plus corrections:

$$
\mathcal L_{\mathrm{bare}}
=\mathcal L_{\mathrm{ren}}+\mathcal L_{\mathrm{ct}}.
$$

For scalar $\phi^4$ theory, a standard renormalized split is

$$
\mathcal L_{\mathrm{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

with counterterm Lagrangian

$$
\mathcal L_{\mathrm{ct}}
=\frac12\delta Z_\phi\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

The corresponding counterterm vertices are local. In momentum space, the two-point counterterm insertion is

$$
{i(\delta Z_\phi p^2-\delta m^2),}
$$

and the four-point counterterm vertex is

$$
{-i\delta\lambda.}
$$

This page is a preview. Its job is to explain what counterterm diagrams are, why they are drawn, how their factors are read from $\mathcal L_{\mathrm{ct}}$, and how they fit into the diagrammatic expansion. The full logic of renormalization conditions, schemes, running couplings, operator mixing, and gauge-theory constraints belongs to later chapters.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), and the Foundations page [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/).

The [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) and [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/) chapters develop the full machinery later.

## Core idea

Loop diagrams often contain ultraviolet divergences. In a local QFT, the divergent parts that can be absorbed into parameters have the form of local operators. Counterterms are those local operators, written as extra vertices and fixed order by order.

The diagrammatic workflow is:

1. write the bare Lagrangian in terms of renormalized parameters plus counterterms;
2. derive ordinary vertices from $\mathcal L_{\mathrm{ren}}$ and counterterm vertices from $\mathcal L_{\mathrm{ct}}$;
3. compute loop diagrams and counterterm diagrams at the same perturbative order;
4. choose the counterterms according to a renormalization prescription;
5. check that renormalized amplitudes or Green functions are finite and satisfy the chosen normalization conditions.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Counterterm insertions cancel local parts of loop corrections in two-point and four-point functions](/figures/perturbative-qft/counterterm-diagram-preview.svg)

<figcaption>

Counterterm diagrams are local vertices inserted at the same order as loop diagrams. The two-point counterterm cancels local mass and kinetic divergences in self-energies; the four-point counterterm cancels local coupling divergences in vertex corrections.

</figcaption>
</figure>

A counterterm is not a new force or a hidden particle. It is bookkeeping for the relation between bare quantities and the parameters used to describe physical measurements.

## Setup and conventions

We use the qft.org mostly-minus convention and write plane waves as $e^{-ip\cdot x}$. The scalar propagator is

$$
D_0(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The running example is real scalar $\phi^4$ theory in four spacetime dimensions. The bare Lagrangian may be written as

$$
\mathcal L_{\mathrm{bare}}
=\frac12 Z_\phi\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12(m^2+\delta m^2)\phi^2
-\frac{\lambda+\delta\lambda}{4!}\phi^4,
$$

where

$$
Z_\phi=1+\delta Z_\phi.
$$

Equivalently,

$$
\mathcal L_{\mathrm{bare}}
=\mathcal L_{\mathrm{ren}}+\mathcal L_{\mathrm{ct}},
$$

with

$$
\mathcal L_{\mathrm{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\mathrm{ct}}
=\frac12\delta Z_\phi\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

The parameters $\delta Z_\phi$, $\delta m^2$, and $\delta\lambda$ are expanded order by order:

$$
\delta Z_\phi=\delta Z_\phi^{(1)}+\delta Z_\phi^{(2)}+\cdots,
$$

with similar expansions for $\delta m^2$ and $\delta\lambda$. The superscript labels perturbative order, not necessarily the number of loops in a single graph. For example, a lower-order counterterm can appear inside a higher-loop diagram to cancel a subdivergence.

## Reading counterterm vertices from the Lagrangian

Counterterm vertices are read from $\mathcal L_{\mathrm{ct}}$ exactly as ordinary interaction vertices are read from $\mathcal L_{\mathrm{int}}$.

For the two-point counterterm, Fourier transform the quadratic part:

$$
\frac12\delta Z_\phi\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2.
$$

With momentum $p$ flowing through the insertion, the vertex factor is

$$
\text{two-point counterterm:}\qquad
 i(\delta Z_\phi p^2-\delta m^2).
$$

The $\delta Z_\phi p^2$ term corrects the kinetic normalization; the $\delta m^2$ term corrects the mass parameter.

For the quartic counterterm,

$$
-\frac{\delta\lambda}{4!}\phi^4
$$

gives

$$
\text{four-point counterterm:}\qquad -i\delta\lambda.
$$

The $4!$ in the Lagrangian cancels the Wick-contraction multiplicity for four identical scalar legs, just as it does for the ordinary quartic vertex $-i\lambda$.

A compact table is:

| Counterterm operator | Vertex factor | Typical role |
|---|---:|---|
| $\frac12\delta Z_\phi\,\partial_\mu\phi\partial^\mu\phi$ | $i\delta Z_\phi p^2$ | kinetic or wavefunction renormalization |
| $-\frac12\delta m^2\phi^2$ | $-i\delta m^2$ | mass renormalization |
| $-\frac{\delta\lambda}{4!}\phi^4$ | $-i\delta\lambda$ | coupling renormalization |

For other theories, the same rule applies: every allowed local counterterm operator gives a local Feynman rule with the same field content, index structure, and momentum dependence as the operator.

## Why counterterms are local

The most important conceptual point is locality. A counterterm Lagrangian is a sum of local operators:

$$
\mathcal L_{\mathrm{ct}}
=\sum_i \delta c_i\,\mathcal O_i(x).
$$

In momentum space, local operators give polynomial dependence on external momenta. For example, a two-point counterterm can produce constants and powers of $p^2$, while a four-point non-derivative counterterm produces a constant vertex.

This means counterterms can cancel local ultraviolet divergences such as

$$
A\Lambda^2+B m^2\log\Lambda+C p^2\log\Lambda,
$$

or, in dimensional regularization, pole terms such as

$$
\frac{A m^2+B p^2}{\epsilon}.
$$

They cannot cancel arbitrary nonlocal dependence such as branch cuts, threshold logarithms, or imaginary parts required by unitarity. Those nonlocal pieces are part of the physical analytic structure of the amplitude.

This is a feature, not a bug. Renormalization removes regulator artifacts that can be absorbed into local parameters; it does not erase the genuine long-distance or on-shell content of loop diagrams.

## Example: two-point function

Let the loop contribution to the amputated scalar two-point function be written as a self-energy insertion

$$
-i\Sigma_{\mathrm{loop}}(p^2).
$$

The counterterm insertion contributes

$$
i(\delta Z_\phi p^2-\delta m^2).
$$

Thus the renormalized 1PI two-point insertion at this order has the form

$$
-i\Sigma_{\mathrm{ren}}(p^2)
= -i\Sigma_{\mathrm{loop}}(p^2)
+i(\delta Z_\phi p^2-\delta m^2).
$$

Equivalently,

$$
\Sigma_{\mathrm{ren}}(p^2)
=\Sigma_{\mathrm{loop}}(p^2)
-\delta Z_\phi p^2+\delta m^2.
$$

The counterterms are chosen so that $\Sigma_{\mathrm{ren}}$ satisfies the chosen renormalization conditions. In an on-shell-style scheme, one often imposes conditions at the physical pole, such as fixing the pole position and residue. In a minimal-subtraction-style scheme, one subtracts only divergent pole terms. The diagrammatic vertex is the same; the value assigned to the counterterm differs by scheme.

In four-dimensional $\phi^4$ theory, the one-loop tadpole produces a mass-type divergence. Momentum-dependent wavefunction renormalization first appears at higher order in this particular model, but it appears already at one loop in many other theories, such as Yukawa theory and gauge theories.

## Example: four-point function

The ordinary quartic vertex is

$$
-i\lambda.
$$

At one loop, the scalar four-point 1PI function receives bubble corrections in the $s$-, $t$-, and $u$-channels. The counterterm vertex contributes

$$
-i\delta\lambda.
$$

So the schematic one-loop renormalized proper four-point function is

$$
\Gamma_4^{\mathrm{ren}}
= -i\lambda
+\Gamma_{4,\mathrm{loop}}^{(1)}
-i\delta\lambda^{(1)}.
$$

The divergent local part of $\Gamma_{4,\mathrm{loop}}^{(1)}$ is canceled by $-i\delta\lambda^{(1)}$. The remaining finite part depends on external kinematics through variables such as $s$, $t$, and $u$. That dependence cannot be mimicked by a non-derivative local counterterm, and it should not be canceled.

This is the first place where the phrase "renormalized coupling" becomes operational. The symbol $\lambda$ is not automatically the same thing as a bare microscopic coefficient. It is the parameter after a convention has been chosen for how to separate the measured or renormalized coupling from loop corrections.

## Perturbative ordering

Counterterm diagrams are not optional after the loop calculation. They are part of the perturbative expansion.

Suppose a one-loop graph contributes at order $\lambda^2$. Then $\delta\lambda^{(1)}$ is also order $\lambda^2$ and must be included in the same order for the four-point function.

At the next order, new effects appear:

| Perturbative ingredient | Why it appears |
|---|---|
| genuine two-loop diagrams | new loop corrections at the target order |
| one-loop diagrams with one lower-order counterterm insertion | cancellation of subdivergences |
| new second-order counterterms | cancellation of remaining overall local divergences |

This hierarchy is the diagrammatic shadow of renormalization to all orders. A high-loop graph may contain divergent subgraphs. Lower-order counterterms must be inserted into those subgraphs before the remaining overall divergence is subtracted.

The full BPHZ and modern renormalization story is more systematic than this preview. The important lesson here is simple: counterterm diagrams are not decorations. They are required terms in the expansion once the theory is written in renormalized variables.

## Scheme dependence and physical dependence

Counterterms are not unique numbers until a renormalization prescription is chosen. Different schemes choose different finite parts.

For example:

| Scheme style | What the counterterms do |
|---|---|
| cutoff scheme | cancel cutoff-dependent pieces and possibly satisfy physical normalization conditions |
| minimal subtraction | cancel only pole terms in dimensional regularization |
| modified minimal subtraction | cancel pole terms plus standard constants such as $\log 4\pi-\gamma_E$ |
| on-shell scheme | fix masses and residues directly at physical poles |

The finite value of a Green function at an off-shell kinematic point may depend on scheme. Properly defined observables do not depend on the arbitrary split between bare parameters, renormalized parameters, and counterterms.

:::caution[Do not subtract the physics]
A local counterterm can remove a local polynomial divergence. It cannot remove a physical branch cut or threshold imaginary part without destroying the analytic structure required by unitarity.
:::

## Common pitfalls

**Treating counterterms as an afterthought.** In renormalized perturbation theory, counterterm diagrams are part of the Feynman rules. Leaving them out gives regulator-dependent intermediate answers and usually violates the chosen renormalization conditions.

**Canceling nonlocal loop structure.** Counterterms are local. They can cancel polynomial or local divergent pieces, not physical logarithms, cuts, or threshold behavior that encode propagation of real intermediate states.

**Mixing bare and renormalized parameters.** Once the Lagrangian is split into $\mathcal L_{\mathrm{ren}}+\mathcal L_{\mathrm{ct}}$, diagrams must be organized in terms of the renormalized parameters and the counterterm expansion. Mixing the split halfway through a calculation is a recipe for double counting.

**Using forbidden counterterms.** Counterterms must respect the symmetries and redundancies imposed on the renormalized theory, unless the regulator or theory has an anomaly. In gauge theories this becomes a severe constraint, expressed through Ward or Slavnov–Taylor identities.

**Forgetting lower-order counterterm insertions in higher-loop graphs.** Higher-order calculations need both new loop diagrams and lower-order counterterm insertions. The latter cancel subdivergences inside larger diagrams.

## Relations to other pages

- [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/) explains how ordinary and counterterm vertices are read from a Lagrangian.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) defines the self-energy and proper-vertex functions to which counterterms contribute.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the momentum-space normalization used for counterterm insertions.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains why the factorials in counterterm operators produce the simple vertex factors shown here.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) motivates why loop integrals can require local subtractions.
- [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) develops the regulators and loop integrals whose divergences counterterms cancel.
- [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/) is the natural next chapter for renormalization conditions, schemes, and renormalized amplitudes.

## Research status

Counterterm diagrams are established textbook technology. In perturbatively renormalizable theories, the required counterterms are constrained by locality, field content, power counting, and symmetries. In effective field theory, one includes all local operators allowed by symmetries, organized by a power-counting expansion.

The subtleties are contextual rather than basic. Gauge theories require symmetry-preserving regularization or compensating identities. Composite operators mix under renormalization. Curved spacetime introduces curvature counterterms. Nonperturbative definitions may reorganize the meaning of bare and renormalized quantities. Those refinements do not change what a counterterm diagram is, but they do change how counterterms are classified and fixed.

## Exercises

### Exercise 1: Derive the two-point counterterm factor

Starting from

$$
\mathcal L_{\mathrm{ct},2}
=\frac12\delta Z_\phi\,\partial_\mu\phi\partial^\mu\phi
-\frac12\delta m^2\phi^2,
$$

show that the momentum-space two-point counterterm insertion is

$$
i(\delta Z_\phi p^2-\delta m^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Write the Fourier transform with the qft.org phase convention. At the vertex, the two momenta are $p$ and $-p$. The derivative term gives a factor $p^2$ after the two derivatives act on the two fields and the momentum-conservation delta function is used. The mass counterterm contributes $-\delta m^2$. Multiplying the quadratic vertex from the action by the usual factor of $i$ gives

$$
i(\delta Z_\phi p^2-\delta m^2).
$$

</details>

### Exercise 2: Identify which counterterms can cancel a divergence

Suppose a regulated scalar self-energy has divergent part

$$
\Sigma_{\mathrm{div}}(p^2)
=A\Lambda^2+B m^2\log\Lambda+C p^2\log\Lambda.
$$

Which scalar two-point counterterms can cancel these terms?

<details>
<summary><strong>Solution</strong></summary>

The $A\Lambda^2$ and $B m^2\log\Lambda$ terms are momentum-independent mass-type divergences, so they can be canceled by $\delta m^2$. The $C p^2\log\Lambda$ term is a kinetic divergence, so it can be canceled by $\delta Z_\phi p^2$. No nonlocal counterterm is needed because the divergent expression is polynomial in $p^2$.

</details>

### Exercise 3: Four-point counterterm counting

Explain why the operator

$$
-\frac{\delta\lambda}{4!}\phi^4
$$

produces the vertex factor $-i\delta\lambda$ for four identical scalar legs.

<details>
<summary><strong>Solution</strong></summary>

At first order in the interaction, the path-integral or Dyson expansion contributes a factor

$$
i\int d^4x\left(-\frac{\delta\lambda}{4!}\phi(x)^4\right).
$$

For four labeled external scalar legs, the four fields at the counterterm vertex can be contracted with the external fields in $4!$ ways. This cancels the $1/4!$ in the Lagrangian. The remaining local vertex factor is

$$
-i\delta\lambda.
$$

</details>

### Exercise 4: Local versus nonlocal subtraction

A one-loop four-point amplitude contains a divergent constant plus a finite term proportional to

$$
\log\left(\frac{-s-i\epsilon}{\mu^2}\right).
$$

Can the quartic counterterm $-\delta\lambda\phi^4/4!$ cancel both pieces?

<details>
<summary><strong>Solution</strong></summary>

No. The quartic counterterm is local and non-derivative, so its momentum-space vertex is a constant. It can cancel a divergent constant part of the loop amplitude. It cannot cancel the nonlocal kinematic dependence $\log[(-s-i\epsilon)/\mu^2]$, which contains physical analytic structure such as branch cuts.

</details>

### Exercise 5: Why lower-order counterterms reappear

At two-loop order, why may a diagram with a one-loop counterterm insertion be required even though the target calculation is two-loop?

<details>
<summary><strong>Solution</strong></summary>

A two-loop graph can contain a divergent one-loop subgraph. The lower-order counterterm cancels this subdivergence inside the larger graph. After all subdivergences have been subtracted, a new two-loop counterterm may still be needed to cancel the remaining overall local divergence. This is the diagrammatic reason lower-order counterterms reappear in higher-order calculations.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§14, 16–19, and 27, for loop corrections, 1PI vertices, all-orders perturbation theory, and renormalization schemes.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 9, 15, 16, and 25, for divergences, counterterms, renormalization, and the BPHZ viewpoint.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15–19, for regulator dependence, mass renormalization, counterterms, and renormalized perturbation theory.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 10 and 12, for renormalization and power counting in a general QFT framework.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 8–10, for ultraviolet divergences, effective field theory, and renormalization theory.
- J. C. Collins, *Renormalization*, for a systematic treatment of counterterms, subtractions, and renormalized perturbation theory.

## Version history

- **2026-06-12:** Initial standardized preview page for counterterm diagrams in the Diagrammatics and Feynman Rules chapter.
