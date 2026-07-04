---
title: "Faddeev–Popov Ghosts in Diagrams"
description: "How the Faddeev–Popov determinant becomes ghost fields, ghost propagators, ghost-gluon vertices, and ghost loops in non-Abelian perturbation theory."
sidebar:
  label: "Faddeev–Popov Ghosts"
  order: 2
level: Graduate
status: "Polished draft"
source: "Faddeev and Popov 1967; Weinberg Vol. II ch. 15; Srednicki §§69–72; Schwartz ch. 26; Coleman chs. 31 and 47"
topics:
  - Faddeev–Popov ghosts
  - ghost diagrams
  - non-Abelian gauge theory
  - BRST preview
canonicalTopics:
  - faddeev-popov-ghosts-in-diagrams
  - ghost-propagators
  - ghost-gluon-vertices
researchStatus:
  established:
    - "Faddeev–Popov ghost fields are the standard perturbative representation of the gauge-fixing determinant in non-Abelian gauge theory."
  active:
    - "The perturbative ghost formalism is cleanly organized by BRST symmetry; global gauge-fixing issues, Gribov regions, and nonperturbative gauge-fixed formulations require later pages."
---

## Summary

Faddeev–Popov ghosts are not extra physical particles. They are anticommuting scalar fields introduced to represent the determinant that appears when the gauge redundancy of a non-Abelian gauge theory is fixed.

For the covariant gauge condition

$$
G^a[A]=\partial_\mu A^{a\mu},
$$

the Faddeev–Popov operator is

$$
M^{ab}=\partial^\mu D_\mu^{ab},
$$

so the determinant is

$$
\Delta_{\rm FP}[A]=\det(\partial^\mu D_\mu).
$$

Using Grassmann fields $c^a$ and $\bar c^a$, this determinant is written inside the path integral as

$$
\Delta_{\rm FP}[A]
=\int\mathcal D\bar c\,\mathcal D c\,
\exp\left\{i\int d^4x\,\mathcal L_{\rm gh}\right\},
$$

with

$$
\mathcal L_{\rm gh}
=\partial^\mu\bar c^a(D_\mu c)^a
=\partial^\mu\bar c^a\partial_\mu c^a
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

Ghosts run only on internal lines in physical calculations. Their loops carry a minus sign because the fields are Grassmann odd, and those ghost loops are essential for unitarity, gauge-parameter cancellation, and the transversality structure of gauge-boson self-energies.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![The Faddeev–Popov determinant becomes ghost propagators, ghost-gluon vertices, and ghost loops](/figures/perturbative-qft/faddeev-popov-ghosts-diagrams.svg)

<figcaption>

In a non-Abelian covariant gauge, the operator $M=\partial\cdot D$ depends on the gauge field. Representing $\det M$ by Grassmann fields gives a ghost propagator, a ghost-gluon vertex, and closed ghost loops with an extra minus sign. These diagrams cancel unphysical gauge-polarization effects in gauge-invariant quantities.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), and [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/). From Foundations, review [Grassmann Variables](/foundations/path-integral-formalism/grassmann-variables/) and [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/).

## Core idea

Gauge fixing removes redundant integration over gauge orbits, but it changes variables in the path integral. The Jacobian of that change of variables is the Faddeev–Popov determinant. In an Abelian theory with a linear covariant gauge, this determinant does not depend on the gauge field and can be absorbed into normalization. In a non-Abelian theory, the determinant depends on $A_\mu^a$, so it contributes to perturbation theory.

A determinant of an ordinary bosonic operator can be represented by a Gaussian integral over anticommuting variables:

$$
\det M
=\int d\bar c\,dc\,
\exp(i\bar c M c)
$$

up to normalization and convention-dependent factors. In field theory this becomes a functional integral over ghost fields.

Ghost fields are strange only if you try to interpret them as particles. The right interpretation is more modest:

```txt
Faddeev–Popov determinant → Grassmann scalar fields → internal diagrammatic bookkeeping.
```

They are scalar under Lorentz transformations but anticommute. They carry gauge-adjoint indices. They have no physical external one-particle states in the gauge-invariant S-matrix.

## Setup and conventions

We use QFT.org's mostly-minus convention and the non-Abelian definitions

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
D_\mu=\partial_\mu+igA_\mu^aT^a,
$$

so

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

The adjoint derivative acting on ghosts is

$$
(D_\mu c)^a
=\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

For the covariant gauge condition

$$
G^a[A]=\partial_\mu A^{a\mu},
$$

the Faddeev–Popov operator is

$$
M^{ab}=\partial^\mu D_\mu^{ab}.
$$

We take the ghost Lagrangian density to be

$$
\mathcal L_{\rm gh}
=\partial^\mu\bar c^a(D_\mu c)^a.
$$

Equivalently, after expanding the adjoint covariant derivative,

$$
\mathcal L_{\rm gh}
=\partial^\mu\bar c^a\partial_\mu c^a
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

Different books sometimes place the derivative on $c$ rather than $\bar c$, reverse ghost-arrow conventions, or use the opposite sign convention for the gauge coupling. Those changes alter the displayed vertex sign but not physical amplitudes.

## From determinant to ghost action

Start from the gauge-fixed Yang–Mills path integral in covariant gauge:

$$
Z=\int\mathcal D A\,
\Delta_{\rm FP}[A]
\exp\left\{
i\int d^4x\left(
\mathcal L_{\rm YM}
-\frac{1}{2\xi}(\partial\cdot A^a)^2
\right)
\right\}.
$$

The determinant is

$$
\Delta_{\rm FP}[A]=\det(\partial^\mu D_\mu).
$$

Represent it by anticommuting fields:

$$
\det(\partial^\mu D_\mu)
=\int\mathcal D\bar c\,\mathcal D c\,
\exp\left[
i\int d^4x\,\partial^\mu\bar c^a(D_\mu c)^a
\right].
$$

The field-independent part gives the ghost kinetic term,

$$
\mathcal L_{\rm gh,0}
=\partial^\mu\bar c^a\partial_\mu c^a,
$$

while the field-dependent part gives the ghost-gluon interaction,

$$
\mathcal L_{\rm gh,int}
=-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

That is the whole origin of ghost diagrams. No new physical postulate has been added.

## Ghost Feynman rules in covariant gauge

With the conventions above, the basic ghost rules are as follows.

| Diagrammatic object | Rule |
|---|---|
| Ghost propagator carrying momentum $p$ | $\displaystyle \frac{i\delta^{ab}}{p^2+i\epsilon}$ |
| Ghost-gluon vertex with incoming antighost momentum $p$ | $\displaystyle -g f^{abc}p^\mu$ |
| Closed ghost loop | extra factor $-1$ |

The vertex convention means that the derivative in

$$
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c
$$

acts on the antighost field. If a page chooses the ghost arrow or incoming momentum differently, the sign attached to the displayed vertex may move. The invariant content is the combination of vertex conventions, ghost-arrow direction, color factors, and closed-loop sign.

Ghost lines are usually drawn as dashed lines with arrows. The arrow is not a spin arrow and not a physical trajectory. It records the order of $c$ and $\bar c$ fields, just as a fermion arrow records spinor-index flow and charge-flow conventions.

## Why ghost loops are required

A covariant gauge-field propagator contains unphysical components. Gauge invariance says those components cannot appear in physical answers. In Abelian QED, current conservation is enough to make the cancellation visible in many amplitudes. In non-Abelian gauge theory, gauge bosons themselves carry charge and interact with each other, so the cancellation is distributed across several classes of diagrams.

Ghost loops are part of that cancellation. At one loop, the gluon self-energy receives contributions from

```txt
gluon loop
four-gluon tadpole
ghost loop
matter loops, if matter is present.
```

The ghost loop removes the contribution of unphysical gauge-polarization modes. Without it, the one-loop answer would not satisfy the correct Ward or Slavnov–Taylor structure, and the theory would not renormalize consistently as a gauge theory.

For a ghost loop contribution to the gauge-boson two-point function, the schematic tensor numerator is

$$
\Pi_{\mu\nu,{\rm gh}}^{ab}(q)
\propto
-\,g^2 f^{acd}f^{bcd}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{\ell_\mu(\ell+q)_\nu}
{(\ell^2+i\epsilon)((\ell+q)^2+i\epsilon)}.
$$

The leading minus sign is the closed ghost-loop sign. The color factor is

$$
f^{acd}f^{bcd}=C_A\delta^{ab},
$$

where $C_A$ is the quadratic Casimir in the adjoint representation. For $SU(N)$ with standard normalization, $C_A=N$.

## Ghosts are not negative-probability particles

The word “ghost” is unfortunately dramatic. Faddeev–Popov ghosts are not observed particles with negative probability. They are fields used inside a gauge-fixed path integral to represent a determinant.

Three facts keep the interpretation straight:

1. Ghosts are Lorentz scalars but Grassmann odd.
2. Ghosts carry gauge-adjoint quantum numbers but do not appear as physical external states.
3. Ghost effects cancel unphysical gauge-field components in gauge-invariant quantities.

The deeper organizing principle is BRST symmetry. In a BRST formulation, gauge fields, ghosts, antighosts, and auxiliary fields form a cohomological structure. Physical states and observables are BRST cohomology classes. This page only needs the diagrammatic shadow of that structure: ghosts are required internal bookkeeping fields in non-Abelian gauge-fixed perturbation theory.

## Abelian versus non-Abelian ghosts

For QED in covariant gauge,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
G[A]=\partial_\mu A^\mu.
$$

Then

$$
M=\partial^2,
$$

which is independent of $A_\mu$. A ghost representation would give

$$
\mathcal L_{\rm gh}^{\rm QED}
=\partial^\mu\bar c\,\partial_\mu c,
$$

with no coupling to the photon. The ghost determinant is just a normalization factor and cancels from ordinary normalized QED correlators.

For Yang–Mills theory,

$$
M^{ab}=\partial^\mu(\delta^{ab}\partial_\mu-gf^{acb}A_\mu^c),
$$

so $M$ depends on $A_\mu^a$. That dependence is exactly the ghost-gluon vertex.

This is why QED students often meet gauge fixing before ghosts, while QCD students cannot avoid ghosts for long. The non-Abelian gauge bosons are charged under the gauge group they mediate, and the gauge-fixing determinant feels that charge.

## Ghost number and arrow conventions

Ghost fields have a useful bookkeeping symmetry called ghost number. Assign

$$
\operatorname{gh}(c)=+1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(A_\mu)=0.
$$

The ghost propagator connects $c$ and $\bar c$, and the ghost-gluon vertex contains one $c$, one $\bar c$, and one gauge field. Ghost number is conserved along the ghost line.

A common convention is to draw ghost arrows in the direction of ghost-number flow. But books differ about whether the arrow points from $c$ to $\bar c$ or from $\bar c$ to $c$. Once a convention is chosen, keep it fixed and let the algebra decide the signs. Diagrammatic ghost signs are bookkeeping, not folklore.

## Common pitfalls

**Putting ghosts on external lines.** Faddeev–Popov ghosts are not physical asymptotic particles. In ordinary physical S-matrix calculations, they appear only internally.

**Forgetting the closed ghost-loop sign.** A closed ghost loop carries an extra factor of $-1$ because the ghost fields anticommute, even though they are Lorentz scalars.

**Using Abelian intuition in Yang–Mills theory.** QED ghosts decouple in ordinary covariant gauges because the determinant is field independent. Non-Abelian ghosts do not decouple.

**Treating the vertex sign as universal without checking conventions.** The ghost-gluon vertex sign depends on the convention for $D_\mu$, the placement of derivatives, all-momenta-incoming conventions, and arrow direction. The combined diagrammatic rules are what matter.

**Thinking ghosts alone prove gauge independence.** Ghosts are necessary, but gauge independence is organized by the full gauge-fixed action, including gauge-fixing terms, ghost terms, counterterms, and BRST or Slavnov–Taylor identities.

## Relations to other pages

- [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) explains the singular kinetic operator and covariant-gauge propagator that force the determinant to appear.
- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) explains why ghost loops enter at the same order as gauge-boson loops.
- [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) gives the general two-point-function language used in gauge-boson polarization tensors.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how ghost, gauge-field, and coupling counterterms enter renormalized perturbation theory.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) introduces the gauge-boson self-interactions whose loop-level consistency requires ghosts.

## Research status

Faddeev–Popov ghosts are an established part of perturbative non-Abelian gauge theory. They are indispensable in covariant gauges, renormalization, loop calculations, and the proof of gauge-theory consistency through Ward, Slavnov–Taylor, and BRST identities.

The live subtleties are mostly global and nonperturbative: Gribov copies, gauge-fixed configuration space, confinement in gauge-fixed languages, BRST realization beyond perturbation theory, and real-time or finite-density gauge fixing. Those issues refine the formalism; they do not remove the need for ghosts in ordinary perturbative Yang–Mills calculations.

## Exercises

### Exercise 1: Grassmann determinant

For finite-dimensional Grassmann variables, show that

$$
\int d\bar c\,dc\,e^{\bar c M c}=M
$$

for a one-dimensional matrix $M$.

<details>
<summary><strong>Solution</strong></summary>

Since Grassmann variables square to zero,

$$
e^{\bar c M c}=1+\bar c M c.
$$

The Berezin integral selects the coefficient of $\bar c c$ up to the chosen ordering convention. With the convention used in the determinant representation,

$$
\int d\bar c\,dc\,\bar c c=1,
$$

so

$$
\int d\bar c\,dc\,e^{\bar c M c}=M.
$$

For an $n\times n$ matrix, the same expansion selects the fully antisymmetrized product of matrix entries, which is $\det M$.

</details>

### Exercise 2: Why Abelian ghosts decouple

Show that in QED with $G[A]=\partial\cdot A$, the Faddeev–Popov determinant is field independent.

<details>
<summary><strong>Solution</strong></summary>

The Abelian gauge transformation is

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Then

$$
G[A^\alpha]
=\partial_\mu A^\mu+\partial^2\alpha.
$$

Therefore

$$
M(x,y)=\frac{\delta G[A^\alpha](x)}{\delta\alpha(y)}
=\partial_x^2\delta^{(4)}(x-y).
$$

This does not contain $A_\mu$. The determinant $\det\partial^2$ is an overall normalization factor, so the corresponding ghosts have no photon interaction vertex and decouple.

</details>

### Exercise 3: Color factor of the ghost loop

Using the adjoint Casimir definition

$$
f^{acd}f^{bcd}=C_A\delta^{ab},
$$

show that the ghost loop contribution to the gluon two-point function is color diagonal.

<details>
<summary><strong>Solution</strong></summary>

The two ghost-gluon vertices contain one structure constant each. After summing over the internal ghost color indices $c,d$, the color factor has the form

$$
f^{acd}f^{bcd}.
$$

By definition of the adjoint quadratic Casimir,

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

Thus the two-point correction is proportional to $\delta^{ab}$, as required by unbroken global color symmetry in the gauge-fixed perturbative vacuum.

</details>

### Exercise 4: Closed ghost-loop sign

Explain why a closed ghost loop carries a minus sign even though ghosts are Lorentz scalars.

<details>
<summary><strong>Solution</strong></summary>

The minus sign is controlled by statistics, not Lorentz spin. Faddeev–Popov ghost fields are Grassmann odd, so permuting them through one another in Wick contractions produces signs. A closed ghost loop requires a cyclic permutation of anticommuting fields, giving the same kind of extra factor of $-1$ that appears for a closed fermion loop. Ghosts are scalar in Lorentz indices but fermionic in their algebra.

</details>

## References and further reading

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.5–15.7, for the Faddeev–Popov method, ghosts, and BRST symmetry.
- M. Srednicki, *Quantum Field Theory*, §§69–74, for non-Abelian gauge theory, Feynman rules, beta functions, and BRST.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 26, for Yang–Mills Feynman rules, ghosts, and QCD one-loop structure.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 31 and 47, for the Faddeev–Popov prescription and ghost fields in gauge-theory quantization.

## Version history

- **2026-06-13:** Initial polished draft for the Gauge-Theory Perturbation Theory chapter of QFT.org.
