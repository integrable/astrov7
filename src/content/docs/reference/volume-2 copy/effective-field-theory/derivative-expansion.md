---
title: "Derivative Expansion"
description: "How local effective field theories organize low-energy effects as a controlled expansion in derivatives, momenta, and inverse heavy scales."
sidebar:
  label: "Derivative Expansion"
  order: 3
level: Graduate
status: "Polished draft"
source: "Weinberg 1979; Polchinski 1984; Burgess 2020, chs. 1–3; Georgi EFT lectures; Schwartz 2014, chs. 21–23 and 33."
topics:
  - effective field theory
  - derivative expansion
  - local operators
  - heavy-particle exchange
  - multipole expansion
  - Wilson coefficients
canonicalTopics:
  - derivative-expansion
  - local-operator-expansion
  - low-energy-expansion
researchStatus:
  established:
    - "The derivative expansion is the standard way a local EFT organizes effects of unresolved short-distance physics when external momenta are small compared with a breakdown scale."
  active:
    - "Derivative expansions remain subtle in systems with gapless modes, nonlocal observables, boundaries, hydrodynamic modes, nonrelativistic thresholds, long-range forces, and amplitudes with multiple correlated momentum regions."
---

## Summary

The derivative expansion is the local low-energy expansion of an effective field theory. If a process probes momenta $Q$ much smaller than a heavy scale or breakdown scale $M$, then unresolved short-distance physics appears as a series of local operators with increasing numbers of derivatives:

$$
\frac{1}{M^2-p^2}
=
\frac{1}{M^2}
+
\frac{p^2}{M^4}
+
\frac{p^4}{M^6}
+
\cdots,
\qquad |p^2|\ll M^2.
$$

In a Lagrangian, powers of $p$ become derivatives. The schematic EFT form is

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{leading}}
+
\sum_{n\ge 1}\frac{1}{M^n}\sum_a C_{n,a}(\mu)\mathcal O_{n,a}.
$$

The operators $\mathcal O_{n,a}$ are local expressions built from light fields and derivatives. Symmetries decide which operators may appear. Redundancies decide which operators are independent. Power counting decides how many of them are needed for a desired accuracy.

:::note[Derivative expansion in one line]
A derivative expansion is valid when the part of an amplitude or observable produced by unresolved short-distance physics is analytic in the small external momenta after all light degrees of freedom have been kept explicit.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/) and [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/). You should also be comfortable with [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

For the Wilsonian origin of the expansion, see [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/). For the next step, read [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/).

## Core idea

A low-energy experiment has finite resolution. It can distinguish long-distance propagation of light particles, but it cannot resolve details at distances much shorter than $Q^{-1}$. If some physics lives at a scale $M\gg Q$, then its effects are seen through an expansion in $Q/M$.

The prototype is heavy-particle exchange. Suppose a heavy field of mass $M$ mediates a process with momentum transfer $p$. At low momentum,

$$
\mathcal A_{\text{full}}(p)
\propto
\frac{1}{M^2-p^2}
=
\frac{1}{M^2}\sum_{n=0}^{\infty}\left(\frac{p^2}{M^2}\right)^n.
$$

The full theory has a nonlocal propagator. The EFT replaces it by a tower of local interactions:

$$
\mathcal A_{\text{EFT}}(p)
\propto
\frac{1}{M^2}
+
\frac{p^2}{M^4}
+
\frac{p^4}{M^6}
+
\cdots.
$$

In position space, $p^2$ becomes a differential operator. Thus the derivative expansion is not decoration. It is how a local low-energy theory remembers short-distance propagation.

The slogan is

$$
\text{unresolved heavy propagation}
\quad\longrightarrow\quad
\text{local operators with more derivatives}.
$$

## Setup and conventions

We work with the scale hierarchy

$$
Q\ll M,
$$

where $Q$ denotes the typical external momentum, energy, inverse distance, light mass, temperature, or gradient scale relevant to the observable. The scale $M$ denotes a heavy mass, threshold, cutoff of validity, inverse microscopic length, resonance scale, or other breakdown scale.

The expansion parameter is written schematically as

$$
\varepsilon\equiv \frac{Q}{M}.
$$

When gauge fields are present, ordinary derivatives in local operators should be replaced by covariant derivatives where appropriate:

$$
\partial_\mu\longrightarrow D_\mu.
$$

The commutator of covariant derivatives produces field strengths,

$$
[D_\mu,D_\nu]\sim F_{\mu\nu},
$$

with group-theory and coupling constants depending on the convention. Thus a gauge-covariant derivative expansion is not merely a list of $D_\mu$ insertions. It also includes operators built from field strengths and covariant derivatives of field strengths.

We use the mostly-minus spacetime conventions fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/). The derivative expansion itself is usually most transparent in Euclidean momentum space or in amplitudes after analytic continuation; pages will state the signature when signs matter.

## Analyticity and why locality matters

The derivative expansion assumes analyticity in small external momenta after the light fields have been kept. A function analytic near $p=0$ admits a Taylor expansion:

$$
F(p)=F(0)+p_\mu\left.\frac{\partial F}{\partial p_\mu}\right|_{p=0}
+
\frac12p_\mu p_\nu
\left.\frac{\partial^2F}{\partial p_\mu\partial p_\nu}\right|_{p=0}
+
\cdots.
$$

In position space this becomes a sum of local terms with increasing derivatives. This is the mathematical reason local EFT works.

Nonanalytic dependence is different. Terms like

$$
\log(-p^2),
\qquad
\sqrt{-p^2},
\qquad
\frac{1}{p^2},
\qquad
\frac{1}{v\cdot p+i\epsilon}
$$

usually signal light propagation, thresholds, long-range forces, or special kinematic regions. They should not be hidden inside a derivative expansion. The correct EFT must keep the modes responsible for these nonanalyticities explicit, or else use a specialized expansion adapted to the relevant region.

This is why a derivative expansion is not the same as blindly Taylor expanding every amplitude. One expands only the short-distance part.

## Heavy exchange as a local tower

Consider a light scalar $\phi$ interacting with a heavy scalar $H$ through a cubic coupling. A simple full-theory exchange amplitude has the form

$$
\mathcal A_{\text{full}}(s)
=
-\frac{g^2}{M^2-s},
$$

where $s$ is a Mandelstam invariant and $s\ll M^2$. Expanding gives

$$
\mathcal A_{\text{full}}(s)
=
-\frac{g^2}{M^2}
-\frac{g^2s}{M^4}
-\frac{g^2s^2}{M^6}
+O\left(\frac{s^3}{M^8}\right).
$$

The EFT reproduces this with contact operators. Schematically,

$$
\mathcal L_{\text{EFT}}
\supset
-\frac{g^2}{8M^2}\phi^4
+
\frac{g^2}{8M^4}\phi^2\Box\phi^2
+
\cdots,
$$

up to signs and normalization conventions fixed by the precise full-theory Lagrangian. The first operator produces a momentum-independent contact interaction. The next one produces a term proportional to external invariants. Higher terms produce higher powers of $s/M^2$, $t/M^2$, and $u/M^2$.

The important point is independent of the toy model:

$$
\text{one heavy propagator}
\quad\leadsto\quad
\text{infinitely many local EFT operators}.
$$

The infinite tower is not a problem because a fixed accuracy requires only finitely many terms.

## Derivatives versus fields

A derivative expansion is an expansion in variation over spacetime, not necessarily an expansion in the number of fields. These are related but distinct organizations.

For example, a scalar EFT might contain both

$$
V(\phi)=\frac12m^2\phi^2+\frac{\lambda}{4!}\phi^4+\frac{c_6}{M^2}\phi^6+\cdots
$$

and derivative interactions such as

$$
\frac{c_{\partial}}{M^2}\phi^2\partial_\mu\phi\,\partial^\mu\phi.
$$

The first expansion is in powers of fields. The second is in powers of derivatives. Which one is primary depends on the physics. Near a vacuum with small fluctuations, both field powers and derivatives may be ordered. In a nonlinear sigma model, the fields may be angular coordinates on a manifold and need not be small globally, while derivatives are still small. In hydrodynamics, the variables are not small, but gradients are.

So the phrase derivative expansion should be heard literally:

$$
\partial_\mu\sim Q,
\qquad
\frac{\partial}{M}\sim \varepsilon.
$$

It does not automatically mean $\phi/M$ is small.

## Covariant derivative expansion

When symmetries are gauged, the derivative expansion must be expressed in gauge-covariant objects. If $D_\mu$ is a covariant derivative, then local gauge-invariant operators are built from fields, $D_\mu$, and field strengths.

A typical tower may include terms like

$$
\phi^\dagger\phi,
\qquad
(D_\mu\phi)^\dagger D^\mu\phi,
\qquad
(\phi^\dagger\phi)^2,
\qquad
F_{\mu\nu}F^{\mu\nu},
\qquad
\frac{1}{M^2}(\phi^\dagger\phi)F_{\mu\nu}F^{\mu\nu},
\qquad
\frac{1}{M^2}(D_\mu F^{\mu\nu})(D^\rho F_{\rho\nu}).
$$

Not all such operators are independent. Integration by parts, Bianchi identities, algebraic identities, and equations of motion can relate them. This is why operator-basis construction is a separate step after writing all symmetry-allowed local expressions.

Covariant derivatives also encode noncommutativity:

$$
D_\mu D_\nu\neq D_\nu D_\mu.
$$

Therefore, moving derivatives around inside gauge-covariant expressions can generate field strengths. A clean EFT basis must keep track of these commutators.

## Multipole expansion as the same idea

The derivative expansion is the field-theory cousin of the multipole expansion. A localized source with size $R$ produces a long-distance potential that can be expanded in moments when the observer is far away:

$$
r\gg R.
$$

The observer first sees total charge, then dipole moment, then quadrupole moment, and so on. The short-distance structure is compressed into coefficients multiplying increasingly derivative-sensitive probes.

In EFT language, the size of the source is $R\sim M^{-1}$ and the probe has wavelength $Q^{-1}$. The expansion parameter is

$$
QR\sim \frac{Q}{M}.
$$

The same logic appears in atomic polarizability, nuclear finite-size effects, gravitational multipoles, worldline EFT, chiral perturbation theory, and hydrodynamics.

## Goldstones and derivative interactions

Goldstone bosons provide a clean case where the derivative expansion is more fundamental than a field-amplitude expansion. For a spontaneously broken continuous symmetry, the Goldstone field parametrizes a vacuum manifold. A constant shift along the vacuum manifold costs no energy, so interactions are constrained to involve derivatives, up to explicit symmetry breaking.

A schematic Goldstone EFT has

$$
\mathcal L
=
\frac{f^2}{2}\partial_\mu\pi\,\partial^\mu\pi
+
L_4(\partial\pi)^4
+
L_4'(\partial^2\pi)^2
+
\cdots,
$$

where the notation is schematic and the actual invariant operators depend on the symmetry-breaking pattern. The expansion is controlled by momenta:

$$
\frac{Q}{4\pi f}
$$

or by a related breakdown scale. The fields may live on a compact target space; the derivatives are what are small.

This is why chiral perturbation theory, nonlinear sigma models, superfluid EFT, and many condensed-matter EFTs are naturally organized as derivative expansions.

## What truncation means

An EFT prediction is never obtained by writing the full infinite tower. One chooses an accuracy and truncates. Suppose an observable has an expansion

$$
\mathcal A(Q)
=
\mathcal A_0(Q)
\left[
1+c_1\frac{Q}{M}
+c_2\left(\frac{Q}{M}\right)^2
+\cdots
\right].
$$

If terms are kept through order $(Q/M)^n$, then the EFT prediction should be quoted with a truncation estimate of order

$$
O\left(\left(\frac{Q}{M}\right)^{n+1}\right),
$$

unless symmetry, loops, accidental cancellations, or special kinematics change the estimate.

The phrase "controlled approximation" means precisely that the neglected terms are parametrically smaller in the regime of use.

## This is the most important part of this page

The derivative expansion is a statement about **short-distance information**. It says:

1. Keep all modes that can propagate over the distances being probed.
2. Expand only the unresolved short-distance part in local operators.
3. Organize the resulting operators by derivatives, symmetries, and redundancies.
4. Truncate only after a power counting tells you the expected error.

A page that expands a heavy propagator but forgets light thresholds is doing Taylor series, not EFT. A page that lists all local operators but gives no ordering principle is doing taxonomy, not prediction. The derivative expansion becomes physics only when paired with a power counting.

## Common pitfalls

**Expanding light propagators.** A massless or nearly massless propagator is long-distance physics. Do not replace $1/p^2$ by local operators in the EFT that is supposed to describe that propagation.

**Confusing derivative order with operator dimension.** More derivatives often mean higher dimension, but fields, spurions, masses, fermions, and symmetry-breaking parameters also count. Power counting decides the actual order.

**Ignoring equations of motion.** Operators with more derivatives may be redundant. Removing them can simplify the basis without changing on-shell observables.

**Forgetting covariant derivatives.** In gauge theories, derivative expansions must respect gauge covariance. Commutators of covariant derivatives generate field strengths.

**Using the expansion beyond its radius of usefulness.** A derivative expansion around $Q=0$ cannot describe a resonance, threshold, or new particle production at $Q\sim M$.

**Assuming coefficients are known.** The derivative expansion tells you the form of local operators. Matching or measurement fixes their coefficients.

**Thinking local means microscopic.** The EFT is local at the resolution being used. It may be the low-energy shadow of a more microscopic nonlocal or strongly coupled process.

## Relations to other pages

[Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/) explains why the allowed local terms must respect the light fields and symmetries. This page explains why those terms are naturally ordered by derivatives when $Q\ll M$.

[Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) turns the derivative expansion into a predictive truncation rule. [Matching](/renormalization-rg-eft/effective-field-theory/matching/) fixes the coefficients of derivative operators by comparing the EFT to a more microscopic description. [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) explains how these coefficients evolve with $\mu$.

The operator-basis subtleties connect to [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/) and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/). The Wilsonian origin connects to [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/).

## Research status

The basic derivative expansion is established and used throughout particle physics, nuclear physics, condensed matter, gravity, hydrodynamics, and cosmology.

Active work often concerns cases where the naive derivative expansion must be refined: soft and collinear modes, Fermi surfaces, nonrelativistic thresholds, near-resonant systems, hydrodynamic fluctuations, open systems, boundaries and defects, long-range forces, cosmological backgrounds, and theories with multiple small parameters.

## Exercises

### Exercise 1: Expanding heavy exchange

A heavy scalar exchange gives the low-energy amplitude

$$
\mathcal A(s)=-\frac{g^2}{M^2-s}.
$$

Expand this amplitude through order $s^2/M^6$. What local EFT terms should reproduce the powers of $s$ schematically?

<details><summary><strong>Solution</strong></summary>

For $s\ll M^2$,

$$
\frac{1}{M^2-s}
=
\frac{1}{M^2}\frac{1}{1-s/M^2}
=
\frac{1}{M^2}\left[1+\frac{s}{M^2}+\frac{s^2}{M^4}+O\left(\frac{s^3}{M^6}\right)\right].
$$

Thus

$$
\mathcal A(s)=
-\frac{g^2}{M^2}
-\frac{g^2s}{M^4}
-\frac{g^2s^2}{M^6}
+O\left(\frac{s^3}{M^8}\right).
$$

The first term is reproduced by a four-field contact operator with no derivatives. The $s$ term is reproduced by four-field operators with two derivatives. The $s^2$ term is reproduced by four-field operators with four derivatives. The exact operator basis depends on field content, symmetries, and whether integration by parts and equations of motion have been used.

</details>

### Exercise 2: Why light exchange is not local

Why is the expansion

$$
\frac{1}{p^2}
\stackrel{?}{=}
\text{local series in }p^2
$$

not a valid derivative expansion around $p=0$?

<details><summary><strong>Solution</strong></summary>

A local derivative expansion corresponds to a Taylor series around small momentum. The function $1/p^2$ is singular at $p=0$, so it has no Taylor expansion there. Physically, this pole is long-distance propagation of a light or massless degree of freedom. The correct EFT must keep the corresponding light field explicit rather than replacing it by contact operators.

</details>

### Exercise 3: Covariant derivatives and field strengths

Suppose an EFT contains a charged field with covariant derivative $D_\mu$. Explain why the order of two covariant derivatives matters and why field-strength operators naturally enter the derivative expansion.

<details><summary><strong>Solution</strong></summary>

Covariant derivatives generally do not commute:

$$
[D_\mu,D_\nu]\sim F_{\mu\nu},
$$

up to couplings and representation matrices. Therefore, an operator containing $D_\mu D_\nu$ is not equivalent to one containing $D_\nu D_\mu$ without additional terms. Reordering derivatives can generate field strengths. A complete gauge-covariant derivative expansion must therefore include both covariant derivatives acting on fields and field-strength tensors, together with their covariant derivatives.

</details>

### Exercise 4: Multipole interpretation

A compact neutral object has size $R$ and is probed by radiation of wavelength $Q^{-1}$ with $QR\ll 1$. What is the EFT expansion parameter, and what kind of local data appear at successive orders?

<details><summary><strong>Solution</strong></summary>

The expansion parameter is

$$
QR\sim \frac{Q}{M},
$$

where $M\sim R^{-1}$ is the inverse size scale. At long distances, the object is described by local worldline or local operator data: total conserved charges, dipole moments, quadrupole moments, polarizabilities, spin-dependent moments, and higher multipoles. Each higher multipole is more sensitive to gradients of the external fields and is suppressed by additional powers of $QR$.

</details>

## References

- Steven Weinberg, "Phenomenological Lagrangians," *Physica A* **96** (1979), for the systematic EFT viewpoint and derivative expansions constrained by symmetry.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984), for the Wilsonian basis of effective Lagrangians.
- Howard Georgi, EFT lectures and reviews, for the practical bottom-up EFT construction rule.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 1–3, for decoupling, low-energy actions, power counting, and matching.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 21–23 and 33, for modern renormalization and EFT examples.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, nonrenormalizable interactions, and critical phenomena.

## Version history

- 2026-06-18: First polished draft. Added heavy-exchange derivation, analyticity criterion, covariant derivative expansion, multipole analogy, Goldstone example, and exercises with solutions.
