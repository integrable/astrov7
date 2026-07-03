---
title: "One-Loop Matching"
description: "How one-loop full-theory effects are separated from EFT loops to determine Wilson coefficients without double counting infrared physics."
sidebar:
  label: "One-Loop Matching"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, RG methods and gauge-theory renormalization; Schwartz 2014, renormalized perturbation theory, nonrenormalizable theories, RG, and EFT applications; Burgess 2020, power counting and matching; Manohar EFT lectures."
topics:
  - one-loop matching
  - Wilson coefficients
  - threshold corrections
  - method of regions
  - operator mixing
  - EFT loops
canonicalTopics:
  - one-loop-matching
  - eft-threshold-matching
  - hard-soft-separation
researchStatus:
  established:
    - "One-loop matching is the standard perturbative procedure for extracting short-distance Wilson coefficients after subtracting the long-distance contributions reproduced by EFT loops."
  active:
    - "Automation of one-loop and multi-loop matching, treatment of evanescent operators, gauge-invariant matching, and basis conversion remain active topics in modern EFT infrastructure."
---

## Summary

**One-loop matching** fixes Wilson coefficients at the first quantum-correction order. The essential idea is simple:

$$
\text{Wilson coefficient at one loop}
=\text{full-theory one-loop result}
-\text{EFT one-loop result},
$$

projected onto the chosen local operator basis.

The subtraction is not cosmetic. Full-theory loop diagrams contain both short-distance information from loop momenta $k\sim M$ and long-distance information from loop momenta $k\sim Q$. The EFT is built precisely to reproduce the long-distance part. Matching should therefore keep only the short-distance remainder in the Wilson coefficients.

At order $\hbar$, the matching equation has the schematic form

$$
\mathcal A_{\text{full}}^{(1)}
=\sum_i C_i^{(1)}\mathcal A_i^{\text{tree}}
+\sum_i C_i^{(0)}\mathcal A_i^{\text{EFT},(1)}.
$$

After the tree-level coefficients $C_i^{(0)}$ are known, this equation determines $C_i^{(1)}$.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![One-loop matching subtracts the EFT long-distance loop contribution from the expanded full-theory loop result, leaving a local hard remainder that fixes Wilson coefficients.](/figures/renormalization-rg-eft/one-loop-matching-subtraction.svg)

<figcaption>

One-loop matching separates hard and soft loop momentum regions. The EFT reproduces the soft region by its own loops. The Wilson coefficient receives the hard local remainder, expanded in powers of $Q/M$ and projected onto the chosen operator basis.

</figcaption>
</figure>

The most important practical warning is:

$$
\text{Do not put long-distance physics into }C_i(\mu).
$$

Wilson coefficients are short-distance objects. Long-distance matrix elements belong inside the EFT.

## Prerequisites

You should know [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), and [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/).

You should also be comfortable with [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

## Core idea

Tree-level matching says that a heavy exchange becomes local at low energy. One-loop matching says that a heavy loop also becomes local after subtracting the low-energy loop physics that the EFT already contains.

Let the Wilson coefficients be expanded as

$$
C_i=C_i^{(0)}+\frac{1}{16\pi^2}C_i^{(1)}+O\left(\frac{1}{(16\pi^2)^2}\right).
$$

The full and EFT amplitudes are similarly expanded:

$$
\mathcal A=\mathcal A^{(0)}+\frac{1}{16\pi^2}\mathcal A^{(1)}+
\cdots.
$$

At tree level,

$$
\mathcal A_{\text{full}}^{(0)}
=\sum_i C_i^{(0)}\mathcal A_i^{\text{tree}}.
$$

At one loop,

$$
\mathcal A_{\text{full}}^{(1)}
=\sum_i C_i^{(1)}\mathcal A_i^{\text{tree}}
+\sum_i C_i^{(0)}\mathcal A_i^{\text{EFT},(1)}.
$$

Therefore

$$
\sum_i C_i^{(1)}\mathcal A_i^{\text{tree}}
=
\mathcal A_{\text{full}}^{(1)}
-
\sum_i C_i^{(0)}\mathcal A_i^{\text{EFT},(1)}.
$$

The right-hand side is local after expansion in $Q/M$, because the EFT loop subtracts the nonlocal low-energy behavior. This local remainder is then decomposed into the chosen operator basis.

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, $d=4-2\epsilon$ in dimensional regularization, and $\beta_g=\mu\,dg/d\mu$ at fixed bare parameters. We use $M$ for a heavy mass, $Q$ for a low-energy scale, and $\mu_M\sim M$ for the matching scale.

A one-loop matching calculation should specify:

| Choice | Why it matters |
|---|---|
| Matching quantity | Amplitude, Green function, effective action, or background-field functional. |
| Operator basis | Determines the displayed Wilson coefficients. |
| Renormalization scheme | Finite parts of $C_i(\mu)$ are scheme dependent. |
| IR regulator | Full and EFT calculations must treat long-distance singularities identically. |
| Gauge choice or gauge-covariant method | Individual off-shell quantities may be gauge dependent. |
| Treatment of evanescent operators | Operators vanishing in four dimensions can affect finite one-loop matching. |

The last item is easy to underestimate. In dimensional regularization, algebra done in $d=4-2\epsilon$ can produce operators that vanish as $\epsilon\to0$ but multiply $1/\epsilon$ poles. Their product can leave finite contributions. In precision EFT matching, evanescent operators are not decorative gremlins. They are bookkeeping with teeth.

## The one-loop matching equation

Suppose the EFT is

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_i C_i\mathcal O_i.
$$

Choose external light states and project onto a set of independent low-energy structures $P_a$. The expanded full-theory one-loop amplitude can be written as

$$
\mathcal A_{\text{full}}^{(1)}
=\sum_a F_a^{(1)}(M,\mu,Q)P_a.
$$

The EFT one-loop amplitude from already-matched lower-order coefficients is

$$
\mathcal A_{\text{EFT, known}}^{(1)}
=\sum_a E_a^{(1)}(\mu,Q)P_a.
$$

Then the matching remainder is

$$
\Delta\mathcal A^{(1)}
=\mathcal A_{\text{full}}^{(1)}-\mathcal A_{\text{EFT, known}}^{(1)}.
$$

After expanding in $Q/M$, this must be a local polynomial in external momenta and light masses:

$$
\Delta\mathcal A^{(1)}
=\sum_i C_i^{(1)}(\mu_M)\mathcal A_i^{\text{tree}}
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

The nonanalytic pieces in $Q$, such as $\log(-Q^2)$, thresholds from light particles, or light-particle branch cuts, must cancel between the full and EFT sides. If they do not cancel, something is wrong: the EFT field content, IR regulator, tree-level matching, or expansion has been mishandled.

## Hard and soft regions

A useful mental model is the method of regions. A full-theory loop integral with a heavy mass $M$ and light scale $Q$ receives contributions from different momentum regions:

$$
I_{\text{full}}(Q,M)
=I_{\text{hard}}(k\sim M)+I_{\text{soft}}(k\sim Q).
$$

The hard region can be expanded in $Q/M$ under the integral. It produces local terms:

$$
I_{\text{hard}}
=a_0+a_2\frac{Q^2}{M^2}+a_4\frac{Q^4}{M^4}+\cdots.
$$

The soft region contains the long-distance nonanalytic dependence that the EFT reproduces:

$$
I_{\text{soft}}
\sim \log\frac{-Q^2}{\mu^2},
\qquad
\sqrt{1-\frac{4m^2}{Q^2}},
\qquad
\text{and other low-energy structures.}
$$

Matching removes the soft part from the coefficient. Therefore

$$
C_i^{(1)}
\quad\text{knows about }M\text{ and short-distance physics, not about unresolved IR dynamics.}
$$

This is why one-loop matching is often described as extracting the hard part of the full-theory loop.

## A practical workflow

A reliable one-loop matching calculation goes like this.

| Step | Task | Check |
|---:|---|---|
| 1 | Choose the EFT fields and operator basis through the desired order. | Every symmetry-allowed operator at that order is either included or shown redundant. |
| 2 | Compute tree-level matching. | Lower-order coefficients $C_i^{(0)}$ are fixed. |
| 3 | Compute the renormalized full-theory one-loop quantity. | UV divergences are subtracted in a stated scheme. |
| 4 | Expand the full-theory result for $Q\ll M$. | Do not expand across thresholds or outside the EFT domain. |
| 5 | Compute EFT one-loop diagrams using $C_i^{(0)}$. | Use the same IR regulator and scheme conventions. |
| 6 | Subtract EFT loops from full loops. | Nonlocal light-scale dependence cancels. |
| 7 | Project the local remainder onto the basis. | Solve for $C_i^{(1)}(\mu_M)$. |
| 8 | Check RG consistency. | Matching-scale dependence cancels against running to the computed order. |

Skipping step 5 is the classic mistake. If the EFT has loops at the same order, the full-theory loop is not automatically the Wilson coefficient. Part of it is long-distance physics that belongs to EFT matrix elements.

## Example: one-loop threshold correction from a heavy scalar

Consider two real scalars: a light field $\phi$ and a heavy field $H$ with

$$
V(\phi,H)
=\frac12m^2\phi^2
+\frac12M^2H^2
+\frac{\lambda}{4!}\phi^4
+\frac{\kappa}{4}\phi^2H^2
+\cdots,
$$

where $m\ll M$. Below $M$, the EFT contains only $\phi$:

$$
V_{\text{EFT}}(\phi)
=\frac12m_{\text{EFT}}^2\phi^2
+\frac{\lambda_{\text{EFT}}}{4!}\phi^4
+\sum_{n\ge 3}\frac{c_{2n}}{M^{2n-4}}\phi^{2n}+
\cdots.
$$

At one loop, integrating out $H$ gives the heavy-field contribution to the effective potential

$$
\Delta V_H^{(1)}
=\frac{1}{64\pi^2}M_H^4(\phi)
\left[
\log\frac{M_H^2(\phi)}{\mu^2}-\frac32
\right]
$$

in $\overline{\mathrm{MS}}$, where

$$
M_H^2(\phi)=M^2+\frac{\kappa}{2}\phi^2.
$$

Expanding in $\phi^2/M^2$, the quartic term is

$$
\Delta V_H^{(1)}
\supset
\frac{\kappa^2}{256\pi^2}
\log\frac{M^2}{\mu^2}\,\phi^4.
$$

Since $V\supset \lambda\phi^4/4!$, this corresponds to the threshold contribution

$$
\Delta\lambda_{\text{EFT}}(\mu)
=\frac{3\kappa^2}{32\pi^2}\log\frac{M^2}{\mu^2}
$$

with these normalizations. The finite constant part depends on the precise scheme and definitions. Choosing $\mu=M$ removes the large logarithm in this simple example.

This calculation illustrates several general lessons:

1. a heavy loop shifts light couplings;
2. the shift depends on the subtraction scheme;
3. matching near $\mu=M$ avoids large logarithms;
4. running below $M$ is then performed in the EFT without the heavy field.

## Example: matching with light loops present

The previous effective-potential example had no light-particle IR subtlety in the displayed quartic threshold term. Many important EFT calculations are less polite.

Suppose a full-theory amplitude has the low-energy expansion

$$
\mathcal A_{\text{full}}^{(1)}
=\alpha\log\frac{-Q^2}{\mu^2}
+B\log\frac{M^2}{\mu^2}
+D
+O\left(\frac{Q^2}{M^2}\right),
$$

where the first logarithm comes from light degrees of freedom. The EFT one-loop amplitude from lower-order operators gives

$$
\mathcal A_{\text{EFT, known}}^{(1)}
=\alpha\log\frac{-Q^2}{\mu^2}
+E.
$$

The matching remainder is

$$
\Delta\mathcal A^{(1)}
=B\log\frac{M^2}{\mu^2}+D-E.
$$

This local quantity fixes the one-loop Wilson coefficient. The light logarithm cancels. If the Wilson coefficient still contains $\log(-Q^2)$, the matching has accidentally swallowed long-distance physics.

## Infrared regulators and the zero-momentum trick

A common shortcut is to set external momenta and light masses to zero during matching. This can be efficient in dimensional regularization because many EFT loop integrals become scaleless and vanish:

$$
\int\frac{d^d k}{(2\pi)^d}\frac{1}{(k^2)^n}=0.
$$

Then the one-loop coefficient can sometimes be read directly from the expanded full-theory diagrams.

This trick is legal only when used with care. A scaleless integral in dimensional regularization often represents a cancellation between UV and IR poles. If the full-theory calculation has an IR divergence, the EFT side must reproduce the same IR divergence. Setting everything to zero can hide this cancellation.

A safer statement is:

$$
\text{IR singularities may be simplified, but they must match.}
$$

If an off-shell momentum, small light mass, or analytic regulator is used to regulate the IR, use the same regulator on both sides. Wilson coefficients must not depend on the arbitrary IR regulator.

## Scheme dependence and finite parts

One-loop Wilson coefficients are scheme dependent. If one changes the subtraction scheme or operator basis,

$$
C_i(\mu)\longrightarrow C_i'(\mu),
$$

then the matrix elements change oppositely so that

$$
\sum_i C_i(\mu)\langle\mathcal O_i(\mu)\rangle
=
\sum_i C_i'(\mu)\langle\mathcal O_i'(\mu)\rangle
$$

for physical quantities at the computed order.

This is not a loophole; it is a consistency condition. The coefficient by itself is not an observable. A quoted one-loop matching result should always include:

| Ingredient | Example |
|---|---|
| Scheme | MS, $\overline{\mathrm{MS}}$, on-shell, momentum subtraction. |
| Scale | $C_i(\mu_M)$, often with $\mu_M\sim M$. |
| Basis | Warsaw basis, SILH basis, chiral basis, custom basis, or model basis. |
| Evanescent convention | Needed in many four-fermion and gauge-theory calculations. |
| Normalization | Operator factors, generators, $4!$, spinor conventions, color factors. |

Without those labels, a one-loop coefficient is a lonely number in search of a theory.

## Gauge theories and background fields

In gauge theories, one-loop matching is especially delicate because off-shell Green functions and intermediate diagrams can be gauge dependent. There are three common strategies.

First, match gauge-invariant on-shell amplitudes. This keeps the physics clear but may not expose all operators efficiently.

Second, use the background-field method. This often keeps gauge covariance manifest in the effective action and is excellent for matching gauge kinetic terms and covariant derivative operators.

Third, compute in a fixed gauge and verify that the final gauge-invariant Wilson coefficients are gauge independent after including all diagrams, counterterms, and basis reductions.

The wrong strategy is to compute a gauge-dependent off-shell object, identify pieces of it with Wilson coefficients, and forget that the object was gauge dependent. That road leads to a small swamp with a surprisingly large number of papers in it.

## RG consistency check

Matching at $\mu_M$ is not the end. The Wilson coefficients evolve below the threshold:

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j.
$$

A physical amplitude should not depend on the arbitrary matching scale once matching and running are combined to the same order. Schematically,

$$
\frac{d}{d\log\mu_M}
\left[
C_i(\mu_M)U^i{}_j(Q,\mu_M)
\langle\mathcal O_j(Q)\rangle
\right]=0
$$

up to higher-order terms.

This gives a powerful check. Logarithms of $M/\mu_M$ in one-loop matching must combine with RG evolution so that changing $\mu_M$ only changes terms beyond the claimed accuracy.

In practice, RG consistency often catches missing factors of $2$, wrong anomalous-dimension signs, forgotten wavefunction counterterms, and basis-transformation errors. The calculation may look offended, but it needed the supervision.

## Common pitfalls

**Equating the full one-loop amplitude with a Wilson coefficient.** The EFT loop contribution must be subtracted when it appears at the same order.

**Letting IR logarithms enter Wilson coefficients.** A coefficient containing $\log Q$ usually signals that long-distance physics was not separated correctly.

**Using different IR regulators in the full theory and EFT.** IR dependence cancels only if both sides are regulated consistently.

**Forgetting lower-order insertions in EFT loops.** One-loop EFT diagrams with tree-level Wilson coefficients often contribute to the matching equation.

**Ignoring evanescent operators.** In dimensional regularization, evanescent structures can affect finite one-loop matching through pole times epsilon effects.

**Matching outside the EFT domain.** Do not expand through a heavy threshold or near a resonance and expect a local EFT to behave.

**Comparing finite parts across schemes.** One-loop finite terms are not universal unless the scheme, basis, and normalization are specified.

## Relations to other pages

This page follows [Tree-Level Matching](/renormalization-rg-eft/matching-running-decoupling/tree-level-matching/) and prepares the ground for [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) and [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/). The conceptual split between short-distance coefficients and low-energy matrix elements was introduced in [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

The technical ingredients come from [Dimensional Regularization](/renormalization-rg-eft/regularization-counterterms/dimensional-regularization/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

## Research status

The framework of one-loop matching is standard and mature. What remains active is the frontier of complicated implementation: multi-loop matching, automated matching of large EFT bases, SMEFT and HEFT threshold calculations, evanescent-operator schemes, nontrivial flavor structures, background-field automation, gravitational EFT matching, nonperturbative matching, and matching in theories with multiple nearly degenerate thresholds.

In phenomenological EFTs, one-loop matching is often where formal correctness meets software reality. A result is only trustworthy if the scheme, basis, gauge treatment, normalization, and RG checks are documented well enough for another calculation to reproduce it.

## Exercises

### Exercise 1: Derive the one-loop matching equation

Let

$$
C_i=C_i^{(0)}+\frac{1}{16\pi^2}C_i^{(1)}+
\cdots
$$

and let the EFT amplitude be

$$
\mathcal A_{\text{EFT}}
=\sum_i C_i\left(\mathcal A_i^{\text{tree}}
+\frac{1}{16\pi^2}\mathcal A_i^{(1)}+
\cdots\right).
$$

Derive the one-loop matching equation.

<details><summary><strong>Solution</strong></summary>

Expand the EFT amplitude through one loop:

$$
\mathcal A_{\text{EFT}}^{(0)}
=\sum_i C_i^{(0)}\mathcal A_i^{\text{tree}},
$$

and

$$
\mathcal A_{\text{EFT}}^{(1)}
=\sum_i C_i^{(1)}\mathcal A_i^{\text{tree}}
+\sum_i C_i^{(0)}\mathcal A_i^{(1)}.
$$

Matching requires $\mathcal A_{\text{full}}^{(1)}=\mathcal A_{\text{EFT}}^{(1)}$, so

$$
\sum_i C_i^{(1)}\mathcal A_i^{\text{tree}}
=
\mathcal A_{\text{full}}^{(1)}
-\sum_i C_i^{(0)}\mathcal A_i^{(1)}.
$$

The right-hand side is then expanded in $Q/M$ and projected onto the operator basis to solve for $C_i^{(1)}$.

</details>

### Exercise 2: Heavy-scalar threshold correction

For a heavy real scalar with field-dependent mass

$$
M_H^2(\phi)=M^2+\frac{\kappa}{2}\phi^2,
$$

use

$$
\Delta V_H^{(1)}
=\frac{1}{64\pi^2}M_H^4(\phi)
\left[
\log\frac{M_H^2(\phi)}{\mu^2}-\frac32
\right]
$$

to find the coefficient of $\phi^4$.

<details><summary><strong>Solution</strong></summary>

Define

$$
x=\frac{\kappa\phi^2}{2M^2},
\qquad
L=\log\frac{M^2}{\mu^2}.
$$

Then

$$
M_H^4=M^4(1+x)^2=M^4(1+2x+x^2),
$$

and

$$
\log\frac{M_H^2}{\mu^2}=L+\log(1+x)
=L+x-\frac{x^2}{2}+O(x^3).
$$

The coefficient of $x^2$ in

$$
(1+2x+x^2)\left(L+x-\frac{x^2}{2}-\frac32\right)
$$

is

$$
L.
$$

Therefore

$$
\Delta V_H^{(1)}\supset
\frac{M^4}{64\pi^2}x^2L
=\frac{\kappa^2}{256\pi^2}
\log\frac{M^2}{\mu^2}\,\phi^4.
$$

If $V\supset \lambda\phi^4/4!$, then this corresponds to

$$
\Delta\lambda
=\frac{3\kappa^2}{32\pi^2}\log\frac{M^2}{\mu^2}
$$

with the normalizations used in the page.

</details>

### Exercise 3: Identifying an IR mismatch

Suppose a proposed Wilson coefficient contains

$$
C(\mu)=c_0+c_1\log\frac{-Q^2}{\mu^2}+c_2\log\frac{M^2}{\mu^2}.
$$

Explain why the term proportional to $\log(-Q^2/\mu^2)$ is suspicious.

<details><summary><strong>Solution</strong></summary>

A Wilson coefficient should encode short-distance physics associated with the heavy scale $M$ and the matching scale $\mu$. A logarithm of the low-energy external momentum $Q$ is nonlocal from the EFT point of view and usually comes from light degrees of freedom.

Therefore the term

$$
c_1\log\frac{-Q^2}{\mu^2}
$$

should be reproduced by EFT loops or matrix elements, not stored in $C(\mu)$. Its presence suggests that the EFT loop contribution was not subtracted, that the IR regulator was used inconsistently, or that the matching quantity was not expanded correctly.

The logarithm $\log(M^2/\mu^2)$ is different: it is short-distance threshold dependence and can appear in the coefficient.

</details>

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters on power counting, exact RG, matching, and relativistic applications.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalized perturbation theory, nonrenormalizable theories, RG, effective actions, heavy-quark EFT, and SCET.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the discussion of RG methods, minimal subtraction, and nonrenormalizable interactions.
- Aneesh V. Manohar, EFT lecture notes, for practical one-loop matching, operator bases, and anomalous-dimension conventions.
- Howard Georgi, EFT lectures and reviews, for the physical separation of short-distance coefficients from long-distance matrix elements.

## Version history

- 2026-06-18: First polished draft. Added one-loop matching equation, hard-soft separation, heavy-scalar threshold example, IR-regulator cautions, scheme-dependence discussion, RG consistency check, and exercises.
