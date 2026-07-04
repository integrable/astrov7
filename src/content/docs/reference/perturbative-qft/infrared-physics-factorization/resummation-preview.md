---
title: "Resummation Preview"
description: "A first guide to resummation: why large logarithms appear in multi-scale observables and how renormalization-group evolution sums them."
sidebar:
  label: "Resummation Preview"
  order: 10
level: Graduate
status: "Polished draft"
source: "Collins–Soper–Sterman; Sterman; Catani–Trentadue; Korchemsky–Radyushkin; SCET review literature; Schwartz chs. 20, 23, 32, and 36"
topics:
  - resummation
  - Sudakov logarithms
  - renormalization group
  - factorization
  - cusp anomalous dimension
canonicalTopics:
  - logarithmic-resummation
  - sudakov-resummation
  - rg-evolution-in-factorization
  - fixed-order-matching
researchStatus:
  established:
    - "Large logarithms in many factorized observables can be summed systematically using evolution equations for hard, jet, beam, soft, and parton-distribution functions."
  active:
    - "Modern precision resummation includes non-global logarithms, rapidity evolution, subleading-power logarithms, jet grooming, multi-scale observables, and matching to high-order fixed-order calculations."
---

## Summary

**Resummation** is the systematic summing of large logarithmic terms that appear when an observable depends on widely separated scales. A fixed-order expansion may contain terms like

$$
\alpha_s^n L^m,
\qquad
L=\ln\frac{Q}{q},
\qquad
m\le 2n
$$

for a Sudakov observable with $Q\gg q$. Even when $\alpha_s(Q)$ is small, the product $\alpha_s L^2$ can be order one. Then a calculation truncated at one or two loops is not organized by small terms.

Resummation reorganizes the answer. Instead of expanding only in powers of $\alpha_s$, one uses factorization and renormalization-group evolution to sum towers of logarithms:

$$
\sigma
\sim
H(Q,\mu_H)\,
U_H(\mu_H,\mu)\,
J(\mu_J)\,
U_J(\mu_J,\mu)\,
S(\mu_S)\,
U_S(\mu_S,\mu).
$$

Here each function is evaluated at a natural scale where its logarithms are small, and the evolution factors $U_i$ move the pieces to a common scale. The evolution factors exponentiate anomalous dimensions, including the cusp anomalous dimension that controls many double logarithms.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Resummation evaluates hard, jet, and soft functions at their natural scales and evolves them to a common scale before matching to fixed order](/figures/perturbative-qft/resummation-preview.svg)

<figcaption>

Fixed-order perturbation theory produces logarithms of ratios such as $Q/q$. Factorization separates the scales. Resummation evaluates each piece at a natural scale and uses RG evolution to move the pieces to a common scale. Matching then restores fixed-order terms that are not enhanced in the singular limit.

</figcaption>
</figure>

This page is a preview. It explains the conceptual architecture of resummation and the minimal equations behind it. A full treatment requires distribution theory, scale choices, anomalous dimensions, rapidity evolution, matching schemes, nonperturbative effects, and process-specific factorization theorems.

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/), [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), and [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/).

## Core idea

Large logarithms are not mysterious. They are bookkeeping evidence that a calculation is trying to describe more than one physical scale using one perturbative expansion.

Suppose an observable depends on a hard scale $Q$ and a much smaller measured scale $q$. Loop and phase-space integrals can probe the entire range between them:

$$
\int_q^Q \frac{d\mu}{\mu}
=
\ln\frac{Q}{q}.
$$

If a soft and a collinear logarithm overlap, one loop can produce a double logarithm. Higher orders then produce towers of logarithms. A schematic fixed-order expansion may look like

$$
\sigma
=
\sigma_0
\left[
1
+
\alpha_s(c_{12}L^2+c_{11}L+c_{10})
+
\alpha_s^2(c_{24}L^4+c_{23}L^3+\cdots)
+\cdots
\right].
$$

For $L$ modest, this is fine. For $L$ large, it is a terrible way to organize the answer. The point of resummation is to rewrite the series so the logarithms are summed to all orders.

## Setup and conventions

Let $Q$ be a hard scale and $q\ll Q$ a measured or veto scale. Examples include a small event shape, a jet mass, a transverse momentum much smaller than an invariant mass, or an energy veto.

The important quantity is the logarithm

$$
L=\ln\frac{Q}{q}.
$$

Fixed-order perturbation theory is reliable when both $\alpha_s$ and the products $\alpha_s L^2$, $\alpha_s L$, and their higher-order analogues are small. Resummation is needed when

$$
\alpha_s L^2\sim 1
$$

or, for single-logarithmic observables,

$$
\alpha_s L\sim 1.
$$

This page uses QCD language, but the structure is more general. Sudakov resummation appears in QED, electroweak theory, non-Abelian gauge theory, EFT matching, threshold limits, transverse-momentum spectra, and many jet observables.

## Where the logarithms come from

A soft emission with energy $\omega$ can produce

$$
\int_q^Q \frac{d\omega}{\omega}
=
\ln\frac{Q}{q}.
$$

A collinear emission with angle $\theta$ can produce

$$
\int_{\theta_{\min}^2}^{1}\frac{d\theta^2}{\theta^2}
=
\ln\frac{1}{\theta_{\min}^2}.
$$

When an observable is sensitive to both soft and collinear regions, the one-emission phase space contains a double-logarithmic region:

$$
\int \frac{d\omega}{\omega}
\int \frac{d\theta^2}{\theta^2}
\sim
L^2.
$$

This is the origin of the simplest Sudakov logarithms. The real and virtual contributions cancel in fully inclusive observables. In exclusive or nearly exclusive observables, the measurement prevents complete cancellation. The surviving logarithms are physical: they express the probability of not emitting radiation that would move the event out of the measured region.

## Sudakov suppression

A classic resummed structure is the Sudakov form factor. In a simple fixed-coupling cartoon, the probability of no resolved emission above a resolution scale behaves like

$$
\Delta(Q,q)
\sim
\exp\!\left[
-\frac{\alpha_s C_i}{\pi}L^2
\right],
\qquad
L=\ln\frac{Q}{q}.
$$

The sign is important. If real radiation above the resolution scale is vetoed, the exclusive probability is suppressed. The exponent is the integrated unresolved-emission probability.

This cartoon hides running coupling, non-cusp anomalous dimensions, color mixing, recoil, measurement dependence, and matching. But it captures the central idea: logarithms exponentiate because unresolved emissions are approximately independent in the leading soft-collinear limit, while virtual corrections enforce probability conservation.

## RG evolution in factorized formulas

Factorization turns resummation into renormalization-group evolution. Suppose an observable factorizes schematically as

$$
\sigma=H(Q,\mu)\,J(q,\mu)\,S(q,\mu).
$$

Each factor satisfies an evolution equation,

$$
\mu\frac{dF_i}{d\mu}
=
\gamma_i(\mu)F_i,
$$

or a convolutional version of this equation. The solution is

$$
F_i(\mu)
=
U_i(\mu_i,\mu)F_i(\mu_i),
$$

with

$$
U_i(\mu_i,\mu)
=
\exp\!\left[
\int_{\mu_i}^{\mu}\frac{d\mu'}{\mu'}\,
\gamma_i(\mu')
\right]
$$

when the anomalous dimension is an ordinary number. For matrices or distributions, this exponential becomes path ordering or convolutional evolution.

The natural scale $\mu_i$ is chosen to minimize logarithms in $F_i(\mu_i)$. A hard function is naturally evaluated at $\mu_H\sim Q$. A jet function might prefer $\mu_J\sim Q\sqrt{V}$. A soft function might prefer $\mu_S\sim QV$. The evolution factors carry the logarithms between these scales.

The physical observable is independent of the common scale $\mu$ up to truncation errors:

$$
\mu\frac{d}{d\mu}
\left[
H(\mu)J(\mu)S(\mu)
\right]
=0.
$$

Thus the anomalous dimensions obey a consistency condition. In the simplest multiplicative case,

$$
\gamma_H+\gamma_J+\gamma_S=0.
$$

## Cusp anomalous dimension

Many double logarithms in gauge theory are controlled by the **cusp anomalous dimension**. It appears when Wilson lines meet at a cusp, or when a hard process creates charged particles moving in different directions. In lightlike limits, the cusp anomalous dimension multiplies logarithms of scale ratios.

A typical anomalous dimension has the schematic form

$$
\gamma_H(Q,\mu)
=
\Gamma_{\rm cusp}(\alpha_s)\,
\ln\frac{Q^2}{\mu^2}
+
\gamma_H^{\rm noncusp}(\alpha_s).
$$

The same structure appears with opposite signs in jet and soft anomalous dimensions so that the physical prediction is scale independent.

Why does the cusp anomalous dimension appear so often? Because soft and collinear radiation is controlled by Wilson lines, and energetic particles changing direction create cusps in Wilson-line configurations. The ultraviolet renormalization of these Wilson-line cusps is the infrared logarithm of the scattering amplitude. That sentence is doing a lot of work, but it is the right mental hook.

## Logarithmic accuracy

Resummed predictions are labeled by logarithmic accuracy. The labels depend slightly on the observable and convention, but the common hierarchy is:

| Label | Rough meaning |
|---|---|
| LL | Leading logarithmic tower. |
| NLL | Next-to-leading logarithmic tower. |
| NNLL | Next-to-next-to-leading logarithmic tower. |
| N$^k$LL | $k$ steps beyond leading logarithms. |

For a cumulative Sudakov observable, one often writes

$$
\Sigma(V)
=
C(\alpha_s)
\exp\!\left[
L\,g_1(\alpha_s L)
+
g_2(\alpha_s L)
+
\alpha_s g_3(\alpha_s L)
+
\cdots
\right].
$$

The function $g_1$ resums leading logarithms, $g_2$ next-to-leading logarithms, and so on. The prefactor $C(\alpha_s)$ contains non-logarithmic matching corrections.

This notation is useful, but dangerous if treated too mechanically. A complete claim of accuracy must specify the factorization theorem, anomalous dimensions, fixed-order matching, running coupling order, observable definition, scale choices, and whether logarithms are global, non-global, rapidity, threshold, or transverse-momentum logarithms.

## Matching to fixed order

A resummed result is designed to be accurate in a singular limit, such as $V\to0$. A fixed-order calculation is designed to be accurate away from that limit. A practical prediction combines both.

A common additive matching formula is

$$
\sigma_{\rm matched}
=
\sigma_{\rm resum}
+
\left[
\sigma_{\rm fixed}
-
\sigma_{\rm resum}\big|_{\rm expanded\ to\ fixed\ order}
\right].
$$

The bracket adds the nonsingular fixed-order terms while avoiding double counting of the logarithmically enhanced terms already contained in the resummed result.

Multiplicative matching and profile-scale methods are also common. The details matter in precision work, but the principle is simple: resummation controls the singular region, fixed order controls the hard region, and matching blends them.

## Threshold, transverse-momentum, and event-shape examples

Different observables generate different kinds of logarithms.

**Threshold logarithms** occur when partonic radiation is forced to be soft near an endpoint. In Mellin space they often become logarithms of the Mellin variable $N$.

**Transverse-momentum logarithms** occur when a color-singlet final state of mass $Q$ is measured with transverse momentum $q_T\ll Q$. Resummation is often done in impact-parameter space.

**Event-shape logarithms** occur when a final state is forced into a nearly exclusive geometry, such as two narrow jets. Thrust, jet mass, and angularities are standard examples.

**Jet-veto logarithms** occur when emissions above a veto scale are forbidden. The veto creates Sudakov suppression.

**Non-global logarithms** occur when the observable restricts radiation in only part of phase space. They are not captured by the simplest independent hard-jet-soft RG evolution.

The shared theme is scale separation. The technical machinery differs because the measurement differs.

## Profile scales and turning off resummation

Resummation should not remain active where there is no large logarithm. For an event shape $V$, the hierarchy may be strong at small $V$, mild at intermediate $V$, and absent at large $V$.

A profile scale is a smooth scale choice that behaves like the natural resummation scale in the singular region but returns to an ordinary fixed-order scale away from it. Schematically,

$$
\mu_S(V)\sim QV
\quad (V\ll1),
\qquad
\mu_S(V)\sim Q
\quad (V\sim1).
$$

This avoids artificially resumming logarithms where the factorized singular approximation is not the dominant physics.

## Resummation versus exponentiation

Exponentiation is a mechanism. Resummation is the organized prediction.

Some logarithms exponentiate directly because of independent emissions or Wilson-line exponentiation. Others are resummed by solving evolution equations. Some observables involve matrix evolution in color space. Some require rapidity evolution. Some involve non-global logarithms governed by nonlinear evolution equations. Some power-suppressed logarithms do not fit the simplest exponentiation patterns.

So it is safer to say:

```txt
resummation = all-order organization of logarithmic terms;
exponentiation = one common way that organization appears.
```

## Common pitfalls

**Resumming without a factorization theorem.** A logarithmic pattern at low orders is not enough. One needs to know which modes, functions, and anomalous dimensions control the logarithms.

**Using one scale for all functions.** If $H$, $J$, and $S$ have different natural scales, evaluating all of them at $\mu\sim Q$ can leave large logarithms in the lower-scale functions.

**Forgetting matching.** A resummed singular approximation misses nonsingular fixed-order information. Precision predictions need matching.

**Trusting resummation outside its region.** A Sudakov formula derived for $V\ll1$ should be turned off or matched as $V$ becomes order one.

**Confusing LL labels across communities.** Logarithmic counting differs between event shapes, threshold resummation, transverse-momentum resummation, and amplitude-level resummation. Always specify the convention.

**Ignoring nonperturbative scales.** If the soft scale approaches $\Lambda_{\rm QCD}$, purely perturbative evolution is no longer enough.

**Treating scale variation as a theorem.** Varying scales estimates perturbative uncertainty. It is useful, not magic. It may miss missing structures such as power corrections or non-global logarithms.

## Relations to other pages

- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) explains the hard, jet, soft, beam, and measurement ingredients resummation evolves.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) explain the singular regions that generate logarithms.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains why measurements decide which logarithms survive.
- [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) gives the simpler single-scale RG equation underlying the multi-scale version here.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) explains why anomalous dimensions and logarithms are especially transparent in dimensional regularization and MS-like schemes.
- [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) and [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) give the Wilson-line intuition behind Sudakov logarithms.

## Research status

**Established:** Resummation using factorization and RG evolution is a standard tool in perturbative QCD, QED, electroweak Sudakov logarithms, threshold physics, transverse-momentum spectra, event shapes, jet vetoes, and many precision collider observables.

**Active:** Current work pushes to higher logarithmic accuracy, more differential measurements, non-global observables, rapidity logarithms, subleading-power logarithms, massive particles, jet grooming, parton showers matched to resummation, and robust uncertainty estimates.

**Speculative:** Resummation-inspired exponentiation ideas are sometimes proposed beyond regimes where a factorization theorem is known. They may be useful, but their status should be distinguished from systematic logarithmic resummation.

## Exercises

### Exercise 1: When does fixed order break down?

Let $\alpha_s=0.1$ and $L=\ln(Q/q)$. Estimate the value of $L$ for which $\alpha_s L^2\sim1$.

<details>
<summary><strong>Solution</strong></summary>

The condition is

$$
0.1\,L^2\sim1.
$$

Thus

$$
L^2\sim10,
\qquad
L\sim\sqrt{10}\approx3.2.
$$

This corresponds to

$$
\frac{Q}{q}\sim e^{3.2}\approx25.
$$

So even a scale hierarchy of a few tens can make double logarithms order one. That is why resummation is not just for absurdly huge scale separations.

</details>

### Exercise 2: Expanding a Sudakov cartoon

Consider the fixed-coupling Sudakov factor

$$
\Delta(Q,q)=\exp[-aL^2],
\qquad
a=\frac{\alpha_s C_i}{\pi}.
$$

Expand it through order $\alpha_s$.

<details>
<summary><strong>Solution</strong></summary>

Using $e^x=1+x+O(x^2)$ with $x=-aL^2$,

$$
\Delta(Q,q)
=
1-aL^2+O(a^2L^4).
$$

Substituting $a=\alpha_s C_i/\pi$ gives

$$
\Delta(Q,q)
=
1-\frac{\alpha_s C_i}{\pi}L^2
+
O(\alpha_s^2L^4).
$$

The first term in the exponent reproduces the leading double logarithm at fixed order.

</details>

### Exercise 3: Natural scales in thrust

For thrust in the two-jet limit, take

$$
\mu_H\sim Q,
\qquad
\mu_J\sim Q\sqrt{\tau},
\qquad
\mu_S\sim Q\tau.
$$

If $Q=100\,\mathrm{GeV}$ and $\tau=0.01$, estimate the three scales.

<details>
<summary><strong>Solution</strong></summary>

The hard scale is

$$
\mu_H\sim100\,\mathrm{GeV}.
$$

The jet scale is

$$
\mu_J\sim Q\sqrt{\tau}
=
100\,\mathrm{GeV}\times0.1
=
10\,\mathrm{GeV}.
$$

The soft scale is

$$
\mu_S\sim Q\tau
=
100\,\mathrm{GeV}\times0.01
=
1\,\mathrm{GeV}.
$$

The soft scale is already close to the nonperturbative region, so a purely perturbative prediction may need hadronization or shape-function corrections.

</details>

### Exercise 4: RG consistency

Suppose

$$
\sigma=HJS,
$$

and the anomalous dimensions obey

$$
\gamma_H+\gamma_J+\gamma_S=0.
$$

Show that $\sigma$ is independent of $\mu$ when each factor satisfies $\mu\,dF_i/d\mu=\gamma_iF_i$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate the product:

$$
\mu\frac{d\sigma}{d\mu}
=
(\gamma_H+\gamma_J+\gamma_S)HJS.
$$

Using the consistency condition,

$$
\gamma_H+\gamma_J+\gamma_S=0,
$$

we get

$$
\mu\frac{d\sigma}{d\mu}=0.
$$

In real factorization formulas the product may involve convolutions or matrices, but the cancellation of unphysical scale dependence is the same principle.

</details>

### Exercise 5: Matching without double counting

Explain why the matched formula

$$
\sigma_{\rm matched}
=
\sigma_{\rm resum}
+
\left[
\sigma_{\rm fixed}
-
\sigma_{\rm resum}\big|_{\rm expanded}
\right]
$$

does not double count the logarithmically enhanced fixed-order terms.

<details>
<summary><strong>Solution</strong></summary>

The resummed result contains the logarithmically enhanced terms to all orders. If we simply added the fixed-order result, the logarithmic terms already present in the fixed-order expansion of the resummed result would be counted twice.

The subtraction removes exactly the terms in the resummed result that overlap with the fixed-order calculation. The bracket therefore contributes only the fixed-order information not already captured by the resummed singular terms. This is usually called the nonsingular remainder, though the precise separation can depend on the matching prescription.

</details>

## References

- J. C. Collins, D. E. Soper, and G. Sterman, classic papers on factorization and transverse-momentum resummation.
- G. Sterman, *An Introduction to Quantum Field Theory* and reviews on QCD resummation, for physical explanations of Sudakov logarithms and infrared structure.
- S. Catani and L. Trentadue, classic papers on threshold resummation.
- G. P. Korchemsky and A. V. Radyushkin, classic work on Wilson lines, cusp anomalous dimensions, and Sudakov form factors.
- C. W. Bauer, S. Fleming, D. Pirjol, I. W. Stewart, and collaborators, early SCET papers on factorization and RG resummation.
- T. Becher, A. Broggio, and A. Ferroglia, *Introduction to Soft-Collinear Effective Theory*, for a modern SCET treatment of resummation.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 23, 32, and 36, for infrared divergences, running couplings, jets, factorization, and SCET.

## Version history

- **2026-06-13:** Initial page. Introduces logarithmic resummation, Sudakov suppression, RG evolution in factorized observables, matching to fixed order, and common limitations.
