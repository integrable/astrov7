---
title: "Large-N Yang–Mills"
description: "Explains the ’t Hooft large-N limit of Yang–Mills theory, including planar dominance, glueball and meson scaling, baryons, theta dependence, and confinement caveats."
sidebar:
  label: "Large-N Yang–Mills"
  order: 7
level: Advanced
status: "Polished draft"
source: "’t Hooft; Witten; Coleman; Polyakov; Shifman; Mariño; large-N QCD literature."
topics:
  - large-N Yang–Mills
  - QCD at large N
  - planar limit
  - glueballs
  - mesons
  - baryons
  - confinement
  - theta dependence
  - topological susceptibility
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - large-n-yang-mills
  - planar-diagrams
  - confinement
  - qcd
  - theta-vacua
researchStatus:
  established:
    - "The ’t Hooft limit organizes Yang–Mills theory and QCD by powers of 1/N, with planar gluon diagrams dominant and hadronic couplings obeying robust scaling rules."
  active:
    - "Large-N Yang–Mills is a controlled organizing limit, but it is not an analytic solution of four-dimensional confinement or the Yang–Mills mass-gap problem."
---

## Summary

**Large-N Yang–Mills** studies the sequence of gauge theories with gauge group $SU(N)$ or $U(N)$ in the limit

$$
N\to\infty,
\qquad
\lambda=g^2N\text{ fixed},
$$

where $\lambda$ is the ’t Hooft coupling. In this limit, adjoint Feynman diagrams organize by topology. Planar diagrams dominate, handles are suppressed by $1/N^2$, and fundamental-quark loops are suppressed by $1/N$ when the number of flavors $N_f$ is held fixed.

The leading consequences are simple enough to fit on a napkin but deep enough to shape modern QFT:

$$
\begin{array}{c|c}
\text{quantity} & \text{large-}N\text{ scaling} \\
\hline
\text{pure-glue vacuum energy} & O(N^2) \\
\text{glueball masses} & O(1) \\
\text{glueball widths} & O(1/N^2) \\
\text{meson masses, fixed }N_f & O(1) \\
\text{meson decay constants} & O(\sqrt N) \\
\text{meson widths} & O(1/N) \\
\text{baryon masses} & O(N) \\
\text{string tension} & O(1)
\end{array}
$$

These scalings do not solve QCD. They explain why QCD at large $N$ resembles a weakly coupled theory of infinitely many narrow color-singlet particles, even though the microscopic gauge theory can be strongly coupled.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Large-N Yang–Mills hierarchy: 't Hooft limit, planar glue, quark boundaries, glueballs, mesons, baryons, theta dependence, and string interpretation.](/figures/nonperturbative-qft/large-n-yang-mills-hierarchy.svg)

<figcaption>

In the ’t Hooft limit, $\lambda=g^2N$ is held fixed. Pure-glue diagrams form a genus expansion with string coupling $g_s\sim1/N$. Fundamental quarks add boundaries suppressed by $1/N$. The result is a controlled hierarchy of vacuum, glueball, meson, baryon, and theta-dependent observables.

</figcaption>
</figure>

The correct attitude is: large $N$ is not a proof of confinement, but it is one of the sharpest available organizing limits for confining gauge theory.

## Prerequisites

Read [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/), [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/), and [Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) first. For confinement background, read [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/), [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/), and [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/).

For QCD context, see [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/), [Glueballs](/nonperturbative-qft/strongly-coupled-gauge-theories/glueballs/), and [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/).

## Core idea

Yang–Mills theory has no small coupling in the infrared, but it has a hidden bookkeeping parameter if one considers a family of theories with gauge group $SU(N)$. The key is to scale the microscopic gauge coupling so that

$$
\lambda=g^2N
$$

is fixed. This keeps planar diagrams finite as $N\to\infty$.

In double-line notation, every adjoint gluon propagator carries two color lines. Closed color faces give powers of $N$, while propagators and vertices carry powers chosen so that the answer depends on the topology of the ribbon graph. A connected pure-glue vacuum graph of genus $h$ scales as

$$
N^{2-2h}.
$$

Thus the $N=\infty$ theory sums all planar diagrams. The $1/N$ expansion is a topological expansion:

$$
\log Z
=
N^2F_0(\lambda)+F_1(\lambda)+\frac1{N^2}F_2(\lambda)+\cdots.
$$

This is why large-$N$ Yang–Mills is often described as string-like. A handle costs $1/N^2$, so the effective string coupling behaves like

$$
g_s\sim \frac1N.
$$

## Setup and conventions

Take pure Euclidean Yang–Mills with gauge group $SU(N)$ and fundamental generators normalized by

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

The action can be written as

$$
S_{\rm YM}
=\frac1{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
=\frac{N}{2\lambda}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu}.
$$

The ’t Hooft limit is

$$
N\to\infty,
\qquad
\lambda=g^2N\text{ fixed},
\qquad
\Lambda_{\rm YM}\text{ fixed}.
$$

For QCD-like theories with fundamental quarks, the default large-$N$ limit in this page holds

$$
N_f=O(1)
$$

as $N\to\infty$. This is not the Veneziano limit. In the Veneziano limit, $N_f/N$ is held fixed and quark loops are no longer suppressed in the same way.

We use normalized single-trace gluonic operators such as

$$
\mathcal O_G(x)=\frac1N\operatorname{tr}F_{\mu\nu}F_{\mu\nu}(x),
$$

and mesonic bilinears such as

$$
\mathcal O_M(x)=\bar q_i(x)\Gamma q^i(x),
$$

with color summed. Different conventions for the normalization of $\mathcal O_M$ shift powers of $N$ in correlators, but not physical statements such as $f_\pi\sim\sqrt N$ and meson widths $\Gamma_M\sim1/N$.

## Pure glue: vacuum, glueballs, and factorization

The pure-glue vacuum energy density scales like the number of adjoint degrees of freedom:

$$
\mathcal E_{\rm vac}=O(N^2).
$$

Normalized gluonic single-trace operators have factorized correlators:

$$
\langle \mathcal O_G(x)\mathcal O_G(y)\rangle_c
=O\!\left(\frac1{N^2}\right).
$$

This does not mean the glueball two-point function vanishes. To extract a canonically normalized glueball field, one rescales the operator so that the connected two-point function is $O(1)$. With this normalization, glueball masses are

$$
M_G=O(1),
$$

while glueball interactions are suppressed. A three-glueball coupling scales as

$$
g_{GGG}=O\!\left(\frac1N\right),
$$

and a glueball decay width scales as

$$
\Gamma_G=O\!\left(\frac1{N^2}\right).
$$

Thus the $N=\infty$ confining theory, if it exists with a mass gap, has infinitely narrow stable glueballs. The large-$N$ theory is interacting at the microscopic level but weakly coupled in the color-singlet glueball sector.

## Fundamental quarks and mesons

Now add $N_f$ fundamental quark flavors with $N_f$ fixed as $N\to\infty$. A closed quark loop carries one color trace rather than the two-index adjoint topology of a gluon surface. In the ribbon-graph picture, quark loops are boundaries. Each boundary costs one power of $1/N$ relative to the pure-glue planar vacuum.

Consequences:

$$
\text{quark-loop effects in the vacuum}=O(N)
\quad\text{instead of}\quad O(N^2).
$$

At leading order, the sea-quark backreaction on pure-glue dynamics is suppressed. This is the large-$N$ origin of the intuition behind quenched approximations, though real $N=3$ QCD is not literally quenched.

Meson two-point functions are dominated by a single quark loop with planar gluons attached. The standard scalings are

$$
M_M=O(1),
\qquad
f_M=O(\sqrt N),
\qquad
n\text{-meson amplitude}\sim N^{1-n/2}.
$$

For example, the three-meson coupling scales as

$$
g_{MMM}=O\!\left(\frac1{\sqrt N}\right),
$$

so meson decay widths scale as

$$
\Gamma_M=O\!\left(\frac1N\right).
$$

At $N=\infty$, mesons are stable, noninteracting particles with finite masses. This is a caricature of real hadron physics, but a recognizable one.

## Baryons as large-N solitons

A baryon in $SU(N)$ QCD contains $N$ fundamental quarks in a color singlet. Its mass therefore scales as

$$
M_B=O(N).
$$

This makes baryons heavy at large $N$. Their behavior resembles solitons more than ordinary elementary particles: the mass is large, collective coordinates become useful, and spin-flavor symmetries emerge in appropriate limits.

A useful mnemonic is

$$
\text{mesons and glueballs}: M=O(1),
\qquad
\text{baryons}: M=O(N).
$$

This hierarchy is one reason large-$N$ QCD gives a unified qualitative picture of mesons, glueballs, and baryons even without solving confinement.

## Confinement and string tension

If pure Yang–Mills confines at large $N$, the Wilson-loop area law takes the form

$$
\langle W(C)\rangle
\sim
\exp[-\sigma A(C)+\cdots],
$$

with

$$
\sigma=O(1).
$$

The string tension remains finite as $N\to\infty$ because the dynamically generated scale is fixed:

$$
\sigma\sim \Lambda_{\rm YM}^2.
$$

The large-$N$ expansion then suggests a weakly coupled string theory of flux tubes. The dictionary is schematic:

$$
\text{planar gluon diagrams}
\leftrightarrow
\text{worldsheets of genus }0,
\qquad
\frac1{N^2}
\leftrightarrow
\text{closed-string loop correction}.
$$

This is a powerful intuition, but not a derivation of the QCD string. The effective string describing a long confining flux tube is well supported, while a complete microscopic string dual of ordinary four-dimensional Yang–Mills is not known.

## Theta dependence

Large $N$ also constrains theta dependence. Add the topological term

$$
S_\theta=i\theta Q,
\qquad
Q=\frac1{32\pi^2}\int \operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

The vacuum energy density scales as

$$
E(\theta)=N^2 f\!\left(\frac{\theta}{N}\right)
$$

locally near $\theta=0$, up to the important constraint of $2\pi$ periodicity. A more physical large-$N$ form is multi-branched:

$$
E(\theta)=N^2\min_{k\in\mathbb Z}
 f\!\left(\frac{\theta+2\pi k}{N}\right).
$$

Expanding near $\theta=0$ gives

$$
E(\theta)-E(0)=\frac12\chi_t\theta^2+O\!\left(\frac{\theta^4}{N^2}\right),
$$

so the topological susceptibility is

$$
\chi_t=O(1).
$$

In QCD with light quarks, this scaling underlies the Witten–Veneziano relation and the fact that the $\eta'$ mass is parametrically suppressed:

$$
m_{\eta'}^2=O\!\left(\frac1N\right)
$$

when the chiral limit is taken in the appropriate order.

## What large N predicts and what it assumes

Large-$N$ Yang–Mills gives conditional predictions. It says: **if** the planar theory confines with a mass gap and finite string tension, then the color-singlet spectrum and interactions obey a rigid hierarchy.

It predicts:

- planar dominance of gluon diagrams;
- suppression of quark loops at fixed $N_f$;
- stable glueballs and mesons at $N=\infty$;
- glueball widths of order $1/N^2$;
- meson widths of order $1/N$;
- baryon masses of order $N$;
- finite string tension and mass gap in confining units;
- topological susceptibility of order $N^0$.

It does **not** by itself prove:

- existence of the continuum four-dimensional Yang–Mills theory;
- confinement in that theory;
- a positive mass gap;
- the detailed glueball spectrum;
- a complete QCD string dual;
- quantitative accuracy at $N=3$ for every observable.

Large $N$ is a controlled expansion around a highly nontrivial limiting theory, not a magic wand. Annoying, yes. But physics loves loopholes the way cats love cardboard boxes.

## Relation to the Veneziano limit

This page has used the original ’t Hooft limit with fixed $N_f$. Another important limit is the Veneziano limit,

$$
N\to\infty,
\qquad
\frac{N_f}{N}\text{ fixed},
\qquad
\lambda=g^2N\text{ fixed}.
$$

In that limit, quark loops are not suppressed relative to gluon effects. The Veneziano limit is useful for conformal-window physics, walking dynamics, and theories with many flavors. It has a different large-$N$ counting from the fixed-$N_f$ limit.

So “large-N QCD” is ambiguous until the flavor scaling is specified.

## Common pitfalls

**Pitfall 1: saying large N proves confinement.** It does not. It organizes the theory assuming the large-$N$ confining phase exists.

**Pitfall 2: confusing planar with weak coupling.** Planar diagrams include all powers of the ’t Hooft coupling. The planar theory can be strongly coupled.

**Pitfall 3: forgetting quark-loop assumptions.** Quark loops are suppressed only when $N_f$ is fixed. In the Veneziano limit, they contribute at leading order.

**Pitfall 4: using $SU(3)$ numerology carelessly.** Many large-$N$ predictions work surprisingly well at $N=3$, but the expansion parameter is not tiny. Check observable by observable.

**Pitfall 5: mixing glueball and meson normalizations.** Normalized single-trace gluonic correlators and canonically normalized glueball fields have different powers of $N$. State the normalization before quoting a scaling.

**Pitfall 6: forgetting nonperturbative-in-N effects.** Large-$N$ expansions can miss effects like $e^{-cN}$, metastable branch tunneling, eigenvalue instantons, and other phenomena invisible to all orders in $1/N$.

## Relations to other pages

[Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) derives the topology behind the ’t Hooft limit.

[Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) explains why normalized gauge-invariant observables become classical at large $N$.

[Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) explains the hoped-for object that would encode the planar limit.

[Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) focuses on confinement-specific consequences, while this page gives the broader large-$N$ Yang–Mills and QCD hierarchy.

[CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/) gives a lower-dimensional solvable analogue with mass generation, theta branches, and confinement-like behavior. [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/) states the theorem-level problem that large $N$ does not solve.

[Conformal Window Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/conformal-window-preview/) and [Walking Gauge Theories Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/walking-gauge-theories-preview/) use related but distinct many-flavor limits.

## Research status

**Established.** ’t Hooft counting, planar dominance, factorization, and the large-$N$ scaling of meson and glueball interactions are standard and robust within their assumptions.

**Strong evidence.** Lattice studies and theoretical consistency strongly support the existence of confining large-$N$ Yang–Mills with finite string tension and glueball masses. The large-$N$ limit appears smooth for many observables.

**Open theorem-level problem.** Large $N$ does not provide a rigorous proof of four-dimensional Yang–Mills existence or a mass gap. Those remain separate mathematical problems.

**Research frontier.** The exact planar solution of nonsupersymmetric four-dimensional Yang–Mills is unknown. Holographic duals, volume reduction, resurgence, loop equations, and lattice large-$N$ simulations provide complementary windows, but no complete analytic solution of ordinary Yang–Mills is known.

## Exercises

### Exercise 1: Handle suppression

A connected pure-glue vacuum ribbon graph of genus $h$ scales as $N^{2-2h}$. What is the relative suppression of a genus-one graph compared with a planar graph?

<details>
<summary><strong>Solution</strong></summary>

A planar graph has $h=0$, so it scales as

$$
N^{2}.
$$

A genus-one graph has $h=1$, so it scales as

$$
N^{2-2}=N^0.
$$

The relative suppression is therefore

$$
\frac{N^0}{N^2}=\frac1{N^2}.
$$

</details>

### Exercise 2: Meson decay width

Suppose a three-meson coupling scales as $g_{MMM}\sim N^{-1/2}$. Estimate the scaling of a two-body meson decay width.

<details>
<summary><strong>Solution</strong></summary>

A decay width is proportional to the squared amplitude times phase space. The masses and phase space are $O(1)$ in the large-$N$ limit, while the amplitude scales as

$$
\mathcal A\sim g_{MMM}\sim N^{-1/2}.
$$

Therefore

$$
\Gamma_M\sim |\mathcal A|^2\sim \frac1N.
$$

</details>

### Exercise 3: Topological susceptibility

Assume

$$
E(\theta)=N^2 f(\theta/N)
$$

near $\theta=0$, with $f(x)=f(0)+\frac12 c x^2+O(x^4)$. Show that the topological susceptibility is $O(1)$.

<details>
<summary><strong>Solution</strong></summary>

Substitute the expansion:

$$
E(\theta)-E(0)
=N^2\left[\frac12 c\left(\frac{\theta}{N}\right)^2+O\!\left(\frac{\theta^4}{N^4}\right)\right].
$$

Thus

$$
E(\theta)-E(0)=\frac12 c\theta^2+O\!\left(\frac{\theta^4}{N^2}\right).
$$

The topological susceptibility is

$$
\chi_t=\left.\frac{\partial^2E}{\partial\theta^2}\right|_{\theta=0}=c,
$$

so $\chi_t=O(1)$.

</details>

### Exercise 4: Fixed-flavor versus Veneziano counting

Why are quark loops suppressed in the fixed-$N_f$ ’t Hooft limit but not necessarily in the Veneziano limit?

<details>
<summary><strong>Solution</strong></summary>

With fixed $N_f$, a quark loop contributes one boundary and a finite flavor sum, so it is suppressed by $1/N$ relative to the leading pure-glue vacuum diagrams. In the Veneziano limit, $N_f\sim N$, so the flavor sum can compensate the boundary suppression. Quark loops can then contribute at leading order.

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapters on the $1/N$ expansion in QCD, theta dependence, and large-$N$ matrix models.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapter on confinement and the ’t Hooft limit.
- S. Coleman, *Aspects of Symmetry*, especially the lecture “1/N,” for the physical consequences of large-$N$ chromodynamics.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on loop dynamics, large $N$, and strings/random surfaces.

### Deeper references

- G. ’t Hooft, “A Planar Diagram Theory for Strong Interactions,” for the original planar large-$N$ expansion.
- E. Witten, “Baryons in the 1/N Expansion,” for baryons as large-$N$ solitonic objects and the scaling of hadronic observables.
- E. Witten, “Theta Dependence in the Large N Limit of Four-Dimensional Gauge Theories,” for multi-branch theta dependence.
- G. Veneziano, “Some Aspects of a Unified Approach to Gauge, Dual and Gribov Theories,” for large-$N$ thinking with many flavors and stringy structure.
- B. Lucini and M. Panero, “SU(N) gauge theories at large N,” for lattice evidence and numerical large-$N$ systematics.

## Version history

- **2026-06-27:** Added comparison link to the CP N-minus-one model.
- **2026-06-27:** Initial polished page on the ’t Hooft large-N limit of Yang–Mills theory, including planar dominance, glueball and meson scaling, baryons, theta dependence, confinement assumptions, and common caveats.
