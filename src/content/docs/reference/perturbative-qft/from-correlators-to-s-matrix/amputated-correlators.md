---
title: "Amputated Correlators"
description: "How external propagator factors are removed from connected Green functions, and how amputated kernels differ from 1PI vertices and on-shell amplitudes."
sidebar:
  label: "Amputated Correlators"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§5, 10, and 13–21; Coleman 2019, chs. 13–16 and 32; Weinberg 1995, Vol. I, §§6.3 and 10.3; Schwartz 2014, chs. 6–7 and 19"
topics:
  - amputated correlators
  - connected Green functions
  - external propagators
  - LSZ reduction
  - 1PI vertices
canonicalTopics:
  - amputated-correlators
  - connected-amputated-kernels
  - external-leg-amputation
  - off-shell-kernels
researchStatus:
  established:
    - "External-leg amputation of connected Green functions is standard perturbative QFT technology and is the off-shell operation underlying LSZ reduction."
  active:
    - "In gauge theories, unstable-particle schemes, bound-state problems, and automated higher-order calculations, the precise choice of fields, residues, gauges, and renormalization schemes remains a practical source of care."
---

## Summary

An **amputated correlator** is a connected Green function with its external propagator factors removed. For a scalar connected momentum-space Green function, the schematic relation is

$$
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n)
=
\left[\prod_{a=1}^n \widetilde G_2(p_a)\right]
\widetilde G^{\mathrm{amp}}_{n,\mathrm{conn}}(p_1,\ldots,p_n),
$$

so that

$$
\widetilde G^{\mathrm{amp}}_{n,\mathrm{conn}}(p_1,\ldots,p_n)
=
\left[\prod_{a=1}^n \widetilde G_2^{-1}(p_a)\right]
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n)
$$

for exact scalar amputation, with the overall momentum-conservation delta function stripped.

Amputation is not the same thing as LSZ reduction. Amputation removes external two-point functions. LSZ then takes the external momenta on shell and multiplies by the correct one-particle residue factors. In a scalar theory with one-particle pole residue $Z_a$,

$$
i\mathcal M
=
\lim_{p_a^2\to m_a^2}
\left[\prod_{a=1}^n Z_a^{1/2}\right]
\widetilde G^{\mathrm{amp}}_{n,\mathrm{conn}}(p_1,\ldots,p_n),
$$

when the amputation uses the exact external two-point functions.

This page explains the off-shell amputation operation, distinguishes free and exact amputation, and separates amputated connected kernels from one-particle-irreducible vertices. That last distinction is small-looking and extremely good at ambushing calculations.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/), and [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/).

## Core idea

A connected Green function includes propagation from each external operator insertion into the interacting part of the diagram. A scattering amplitude does not include those external propagators. Amputation removes the external propagation and exposes the kernel to which external states will later be attached.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A connected Green function becomes an amputated connected kernel after inverse two-point functions remove external propagators](/figures/perturbative-qft/amputated-correlator-dictionary.svg)

<figcaption>

Amputation is an off-shell operation: multiply by inverse two-point functions on external legs. LSZ adds the residue factors and the on-shell limit needed to turn the amputated kernel into the physical amplitude.

</figcaption>
</figure>

The hierarchy is:

| Object | External propagators? | On shell? | Physical amplitude? |
|---|---:|---:|---:|
| connected Green function | yes | no | no |
| amputated connected correlator | no | usually no | no |
| LSZ amplitude $i\mathcal M$ | no | yes | yes, for allowed asymptotic states |

Amputation is therefore a middle layer. It is what Feynman diagrams usually compute when one says “the diagram contributes to $i\mathcal M$,” but by itself it is still a Green-function object unless the LSZ conditions are imposed.

## Setup and conventions

We use the qft.org mostly-minus metric and Fourier convention

$$
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p).
$$

For scalar correlators, the reduced connected Green function is defined by stripping the total delta function:

$$
\int \prod_{a=1}^n d^4x_a\,
 e^{i\sum_a p_a\cdot x_a}
G_{n,\mathrm{conn}}(x_1,\ldots,x_n)
=
(2\pi)^4\delta^{(4)}\!\left(\sum_a p_a\right)
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n).
$$

The exact scalar two-point function is denoted

$$
\widetilde G_2(p)
=
\int d^4x\,e^{ip\cdot x}\langle0|T\phi(x)\phi(0)|0\rangle.
$$

Near a stable one-particle pole,

$$
\widetilde G_2(p)
\xrightarrow{p^2\to m^2}
\frac{iZ}{p^2-m^2+i\epsilon}+\text{regular}.
$$

At tree level in a theory whose quadratic term is canonically normalized, the free propagator is

$$
D_0(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

The distinction between $D_0(p)$ and $\widetilde G_2(p)$ is the distinction between **free amputation** and **exact amputation**.

## Free amputation

In ordinary perturbative diagrammatics, one often amputates external legs by multiplying by the inverse free propagator,

$$
D_0^{-1}(p)=\frac{p^2-m^2+i\epsilon}{i}.
$$

For scalar external legs,

$$
\widetilde G^{\mathrm{amp},0}_{n,\mathrm{conn}}
=
\left[\prod_{a=1}^n D_0^{-1}(p_a)\right]
\widetilde G_{n,\mathrm{conn}}.
$$

The superscript $0$ reminds us that the external legs were removed using the free propagator. This is the rule students first learn: if a connected diagram for a Green function has external propagators, erase those external propagators to get the amputated diagram.

Free amputation is perfect at tree level when the external propagators are free. Beyond tree level, external self-energy insertions modify the pole position and residue. A renormalized perturbation scheme can make the practical rules look tree-like again, but only after the mass and field-strength renormalization conditions have been fixed.

## Exact amputation

The exact definition uses the full connected two-point function:

$$
\widetilde G^{\mathrm{amp}}_{n,\mathrm{conn}}(p_1,\ldots,p_n)
=
\left[\prod_{a=1}^n \widetilde G_2^{-1}(p_a)\right]
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n).
$$

This definition removes the exact external propagation, including self-energy corrections. Near the one-particle pole,

$$
\widetilde G_2^{-1}(p)
\xrightarrow{p^2\to m^2}
\frac{p^2-m^2}{iZ},
$$

so the LSZ formula can be written as

$$
 i\mathcal M
 =
 \lim_{p_a^2\to m_a^2}
 \left[\prod_{a=1}^n Z_a^{1/2}\right]
 \widetilde G^{\mathrm{amp}}_{n,\mathrm{conn}}(p_1,\ldots,p_n).
$$

This formula makes the meaning of $Z_a$ transparent. Exact amputation removes $Z_a$ in the denominator, and LSZ restores one factor of $\sqrt{Z_a}$ per external particle because each local field has overlap $\sqrt{Z_a}$ with the one-particle state.

:::tip[Free versus exact amputation]
Free amputation is the convenient perturbative diagram rule. Exact amputation is the clean conceptual definition. In renormalized perturbation theory, the two are related by counterterms and field-strength renormalization.
:::

## Example: φ⁴ contact correlator

In real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4,
$$

the tree-level connected four-point Green function is

$$
\widetilde G^{\mathrm{tree}}_{4,\mathrm{conn}}(p_1,p_2,p_3,p_4)
=
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon},
$$

with the overall delta function stripped. Free amputation gives

$$
\begin{aligned}
\widetilde G^{\mathrm{amp},0,\mathrm{tree}}_{4,\mathrm{conn}}
&=
\left[\prod_{a=1}^4\frac{p_a^2-m^2+i\epsilon}{i}\right]
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\\
&=-i\lambda.
\end{aligned}
$$

For this simple tree diagram, the amputated connected correlator is already the object usually called $i\mathcal M$ after applying the physical momentum signs and putting external momenta on shell.

## Amputated connected does not mean 1PI

A connected amputated correlator can still contain internal propagators that make it one-particle reducible. This is one of the most useful distinctions in perturbative QFT.

Consider scalar cubic theory with

$$
\mathcal L_{\mathrm{int}}=-\frac{g}{3!}\phi^3.
$$

The tree-level $s$-channel contribution to the four-point function has two cubic vertices connected by one internal line. After amputating only the external legs, the reduced kernel is

$$
\widetilde G^{\mathrm{amp}}_{4,\mathrm{conn},s}
=
(-ig)^2\frac{i}{(p_1+p_2)^2-m^2+i\epsilon},
$$

in all-incoming notation with the appropriate assignment of momenta. This object is connected and amputated, but it is **not** one-particle irreducible: cutting the internal propagator disconnects the graph.

A 1PI vertex is a building block. A connected amputated correlator is the full connected kernel assembled from 1PI vertices and internal exact propagators. For two-point functions, this distinction becomes the familiar relation between the exact propagator and the self-energy. For four-point and higher functions, it becomes a tree expansion in 1PI vertices using exact internal lines.

The rough map is:

| Object | Meaning |
|---|---|
| Connected Green function | all connected external propagation included |
| Amputated connected correlator | connected scattering kernel with external propagation removed |
| 1PI vertex | irreducible kernel that cannot be disconnected by cutting one internal line |
| Effective action $\Gamma$ | generating functional for 1PI vertices |

Do not call every amputated diagram a vertex. Some amputated diagrams still contain internal propagators, thresholds, poles, and reducible structure.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A connected amputated four-point kernel decomposes into a direct 1PI vertex plus one-particle-reducible exchange terms built from 1PI three-point vertices and an exact propagator](/figures/perturbative-qft/amputated-vs-1pi.svg)

<figcaption>

A connected amputated correlator is generally assembled from 1PI vertices connected by exact internal propagators. External legs are removed in every term; internal propagators remain when they connect lower-point 1PI vertices.

</figcaption>
</figure>

## Fields with indices and mixing

For multiple fields, spinor fields, gauge fields, or fields with internal indices, the two-point function is a matrix in field labels and index space. Amputation means multiplying by the inverse two-point matrix on each external leg.

For fields $\Phi_A$, write schematically

$$
\widetilde G_{2,AB}(p)
=
\int d^4x\,e^{ip\cdot x}
\langle0|T\Phi_A(x)\Phi_B(0)|0\rangle.
$$

Then the amputated connected correlator has the form

$$
\widetilde G^{\mathrm{amp}}_{A_1\cdots A_n}
=
\prod_{a=1}^n
\left[\widetilde G_2^{-1}(p_a)\right]_{A_aB_a}
\widetilde G_{B_1\cdots B_n,\mathrm{conn}},
$$

with repeated field and index labels summed or integrated as appropriate. For Dirac fields, the inverse propagator carries spinor indices. For vector fields, it carries Lorentz and gauge-fixing structure. For mixing fields, such as neutral scalars with the same quantum numbers, the pole residues are vectors or matrices selecting the physical mass eigenstates.

This is where notation gets heavy, but the idea remains simple: remove the external two-point response appropriate to the field inserted at that leg.

## Practical workflow

For ordinary scalar perturbative calculations, the working procedure is:

1. draw connected diagrams for the desired Green function;
2. include external propagators if computing the correlator;
3. remove external propagators if computing an amputated kernel;
4. keep internal propagators, including propagators that make the diagram reducible;
5. include symmetry factors, signs, counterterm insertions, and loop integrals;
6. apply LSZ only after the correct external residues and on-shell limits are specified.

For tree-level scattering in canonically normalized scalar theories, this reduces to the familiar shortcut: draw only diagrams with external legs attached to vertices, but do not include propagator factors for the external legs. For loop-level scattering, the shortcut is safe only after the renormalization conditions and external-leg corrections are under control.

## Common pitfalls

**Calling an amputated connected diagram 1PI.** Amputation removes external legs; 1PI is a statement about internal connectivity. A tree-level exchange diagram is amputated after external legs are removed, but it is still one-particle reducible.

**Using free amputation when exact amputation is intended.** Multiplying by $D_0^{-1}$ removes free external propagators. Multiplying by $G_2^{-1}$ removes exact external propagators. The difference matters precisely where self-energy corrections and wave-function renormalization matter.

**Putting legs on shell too early.** Amputated correlators are often useful off shell. Taking the on-shell limit before canceling external poles can hide the pole extraction and create meaningless zero-times-infinity expressions.

**Forgetting field mixing.** If several fields have the same quantum numbers, the propagator is a matrix and physical particles are associated with pole eigenvectors. Scalar single-field notation is a training wheel, not the full story.

**Treating off-shell amputated Green functions as observables.** Off-shell amputated kernels can depend on field definitions, gauges, and schemes. The S-matrix amplitude obtained after LSZ is the physical object when the assumptions of scattering theory apply.

## Relations to other pages

- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains how amputated correlators become on-shell amplitudes.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the normalization of $i\mathcal M$ after amputation and LSZ.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the practical diagram rules that usually output amputated scalar kernels.
- [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) explains why amputation is normally applied to the connected part when computing connected amplitudes.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) defines the irreducible vertices that build connected amputated correlators.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) explains how counterterm insertions modify external propagators, residues, and amputated kernels in renormalized perturbation theory.

## Research status

The amputation of external legs is standard perturbative QFT technology. The conceptual distinction between connected, amputated, 1PI, and on-shell objects is settled, but practical implementations become delicate in gauge theories, mixed field systems, unstable-particle calculations, bound-state formalisms, and high-order automated amplitude pipelines. In those settings the same idea survives, but the inverse two-point functions, residues, projectors, and physical-state conditions require more structure.

## Exercises

### Exercise 1: Amputate the φ⁴ contact correlator

Given

$$
\widetilde G^{\mathrm{tree}}_{4,\mathrm{conn}}
=
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon},
$$

compute the freely amputated four-point kernel.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
D_0^{-1}(p_a)=\frac{p_a^2-m^2+i\epsilon}{i}.
$$

Then

$$
\begin{aligned}
\widetilde G^{\mathrm{amp},0,\mathrm{tree}}_{4,\mathrm{conn}}
&=
\left[\prod_{a=1}^4D_0^{-1}(p_a)\right]
\widetilde G^{\mathrm{tree}}_{4,\mathrm{conn}}\\
&=
\left[\prod_{a=1}^4\frac{p_a^2-m^2+i\epsilon}{i}\right]
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon}\\
&=-i\lambda.
\end{aligned}
$$

</details>

### Exercise 2: A connected amputated graph that is not 1PI

In scalar $\phi^3$ theory, show that the tree-level exchange graph

$$
(-ig)^2\frac{i}{(p_1+p_2)^2-m^2+i\epsilon}
$$

is connected and amputated but not 1PI.

<details>
<summary><strong>Solution</strong></summary>

The external propagators have already been removed, so the displayed object is amputated with respect to its four external legs. It is connected because there is a path through the graph between any two external legs. But it contains one internal propagator joining the two cubic vertices. Cutting that internal line separates the graph into two pieces, so it is one-particle reducible, not 1PI.

</details>

### Exercise 3: Relate exact amputation to LSZ

Assume

$$
\widetilde G_2(p)\xrightarrow{p^2\to m^2}\frac{iZ}{p^2-m^2+i\epsilon}.
$$

Show that exact amputation followed by multiplication by $Z^{1/2}$ per external leg gives the scalar LSZ external factor.

<details>
<summary><strong>Solution</strong></summary>

Near the pole,

$$
\widetilde G_2^{-1}(p)
\to
\frac{p^2-m^2}{iZ}.
$$

Multiplying by $Z^{1/2}$ gives

$$
Z^{1/2}\widetilde G_2^{-1}(p)
\to
\frac{p^2-m^2}{i\sqrt Z}.
$$

This is exactly the one-leg factor appearing in the scalar momentum-space LSZ formula.

</details>

### Exercise 4: Free and exact amputation at tree level

Explain why free and exact amputation agree at tree level in a canonically normalized scalar theory, but need not agree after loop corrections.

<details>
<summary><strong>Solution</strong></summary>

At tree level, the two-point function is just the free propagator,

$$
\widetilde G_2(p)=D_0(p)=\frac{i}{p^2-m^2+i\epsilon},
$$

so $\widetilde G_2^{-1}=D_0^{-1}$. After loop corrections, the exact two-point function contains self-energy corrections,

$$
\widetilde G_2(p)=\frac{i}{p^2-m^2-\Pi(p^2)+i\epsilon}
$$

schematically. Its pole location and residue need not match the free propagator. Exact amputation removes this corrected two-point function, while free amputation removes only the tree-level propagator. Counterterms and renormalization conditions control how the practical rules are organized.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§5, 10, and 13–21, for LSZ, Feynman rules, exact propagators, self-energies, and the quantum action.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 13–16 and 32, for Green functions, LSZ, renormalized propagators, and 1PI generating functionals.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 6–7 and 19, for LSZ, Feynman rules, and renormalized perturbation theory.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§6.3 and 10.3, for momentum-space rules, external-line factors, propagator poles, and field renormalization.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the functional approach to connected and 1PI generating functionals.
- C. Itzykson and J.-B. Zuber, *Quantum Field Theory*, for a classic treatment of Green functions, amputated functions, and proper vertices.

## Version history

- **2026-06-12:** Initial standardized page for free and exact amputation, connected kernels, and the distinction from 1PI vertices.
