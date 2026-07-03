---
title: "Gravitational Effective Field Theory"
description: "General relativity as a low-energy effective field theory with diffeomorphism invariance, curvature expansion, graviton loops, and controlled quantum corrections."
sidebar:
  label: "Gravitational Effective Field Theory"
  order: 90
level: Advanced
status: "Polished draft"
source: "Donoghue 1994; Burgess 2020; Weinberg 1979 and Quantum Theory of Fields; Donoghue, Golowich, and Holstein; effective action and background-field literature."
topics:
  - gravitational EFT
  - quantum gravity
  - curvature expansion
  - diffeomorphism invariance
  - graviton loops
  - nonrenormalizable theories
canonicalTopics:
  - gravitational-effective-field-theory
  - quantum-gravity-as-eft
  - general-relativity-effective-field-theory
researchStatus:
  established:
    - "General relativity coupled to matter is a predictive low-energy EFT: diffeomorphism invariance fixes the operator expansion, and low-energy quantum corrections are organized by powers of energy over the Planck scale and curvature radii."
  active:
    - "High-precision post-Newtonian EFTs, cosmological EFTs, black-hole EFTs, positivity constraints, infrared issues, and ultraviolet completions of gravity remain active research areas."
---

## Summary

**Gravitational effective field theory** is the statement that general relativity can be treated as a quantum field theory at energies well below the Planck scale. It is not perturbatively renormalizable in the old sense, but it is a perfectly good low-energy EFT. The Lagrangian contains every local diffeomorphism-invariant operator built from the metric, matter fields, covariant derivatives, and curvature tensors:

$$
S_{\text{grav EFT}}
=\int d^4x\,\sqrt{-g}\left[
-\Lambda_{\text{cc}}
+\frac{M_{\text{Pl}}^2}{2}R
+c_1 R^2
+c_2 R_{\mu\nu}R^{\mu\nu}
+c_3 R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\cdots
\right]
+S_{\text{matter}}.
$$

The precise signs depend on curvature conventions; this page follows the mostly-minus convention of the volume and states only convention-insensitive lessons unless signs matter. The reduced Planck mass is

$$
M_{\text{Pl}}^2=\frac{1}{8\pi G}.
$$

The expansion is controlled by small dimensionless ratios such as

$$
\frac{E}{M_{\text{Pl}}},
\qquad
\frac{E}{M},
\qquad
\frac{R}{M^2},
\qquad
\frac{1}{M L},
$$

where $E$ is a characteristic energy, $M$ is a heavy threshold, $R$ denotes a curvature scale, and $L$ is a macroscopic length.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![Gravitational EFT workflow from diffeomorphism invariance and low-energy fields to curvature expansion, loops, counterterms, nonanalytic long-distance terms, and observables.](/figures/renormalization-rg-eft/gravitational-eft-curvature-expansion.svg)

<figcaption>

Gravitational EFT organizes quantum gravity at low energies. Diffeomorphism invariance fixes the allowed local curvature operators; loops generate higher-curvature counterterms; analytic short-distance pieces are absorbed into Wilson coefficients, while nonanalytic long-distance terms give model-independent low-energy quantum corrections.

</figcaption>
</figure>

The main conceptual point is simple: **nonrenormalizable does not mean unusable**. It means that more local operators are needed as one asks for higher precision or higher energy.

## Prerequisites

You should know [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), and the Wilsonian view of irrelevant operators. You should also know the basic geometric objects of general relativity: metric, connection, curvature, covariant derivative, and stress tensor.

The page uses $g_{\mu\nu}$ for the metric and $g$ for its determinant. Around a background $\bar g_{\mu\nu}$ we write

$$
g_{\mu\nu}=\bar g_{\mu\nu}+\kappa h_{\mu\nu},
\qquad
\kappa^2=32\pi G=\frac{4}{M_{\text{Pl}}^2}.
$$

The field $h_{\mu\nu}$ is the graviton fluctuation in perturbation theory. The decomposition is background dependent; the EFT itself is diffeomorphism invariant.

## Core idea

The Einstein–Hilbert action is

$$
S_{\text{EH}}=\frac{M_{\text{Pl}}^2}{2}\int d^4x\sqrt{-g}\,R.
$$

By itself, it is not closed under quantum loops. Graviton and matter loops generate divergences proportional to higher-curvature operators such as

$$
R^2,
\qquad
R_{\mu\nu}R^{\mu\nu},
\qquad
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma},
\qquad
R\Box R,
\qquad
R^3,
$$

and so on. In old language, this is a failure of perturbative renormalizability. In EFT language, it is exactly what should happen: every term compatible with the symmetries must be included, ordered by power counting.

The gravitational EFT action is therefore not just Einstein–Hilbert. It is

$$
S_{\text{EFT}}=S_{\text{EH}}+S_{\text{local higher curvature}}+S_{\text{matter}}+S_{\text{boundary}}+\cdots.
$$

At low energy, the Einstein–Hilbert term dominates because it has the fewest derivatives. Higher-curvature terms are suppressed by more powers of the small scale.

The practical slogan is

$$
\text{general relativity is the leading term in the derivative expansion of quantum gravity}.
$$

## Why gravity looks nonrenormalizable

The gravitational coupling has negative mass dimension. From

$$
\kappa^2=32\pi G,
$$

one finds

$$
[\kappa]=-1.
$$

Expanding around flat spacetime,

$$
g_{\mu\nu}=\eta_{\mu\nu}+\kappa h_{\mu\nu},
$$

the Einstein–Hilbert action produces an infinite series of graviton self-interactions. Each interaction carries derivatives and powers of $\kappa$. Loop diagrams therefore generate divergences with more derivatives than the original action.

A schematic amplitude at energy $E$ has the form

$$
\mathcal A
\sim E^2\left[
1
+a_1\frac{E^2}{M_{\text{Pl}}^2}
+a_2\frac{E^4}{M_{\text{Pl}}^4}
+\cdots
\right],
$$

where the coefficients contain loops, Wilson coefficients, and process-dependent factors. The exact powers depend on the observable, but the lesson is robust: low-energy gravity is predictive because each higher order is suppressed.

## The curvature expansion

Diffeomorphism invariance restricts the local action to scalar densities. In four dimensions, the first few purely gravitational terms are

$$
\sqrt{-g},
\qquad
\sqrt{-g}R,
\qquad
\sqrt{-g}R^2,
\qquad
\sqrt{-g}R_{\mu\nu}R^{\mu\nu},
\qquad
\sqrt{-g}R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma},
\qquad
\ldots
$$

The first term is the cosmological constant term. The second is the Einstein–Hilbert term. The curvature-squared terms contain four derivatives of the metric. Higher terms contain more curvatures or covariant derivatives:

$$
R^3,
\qquad
R\Box R,
\qquad
R_{\mu\nu}\Box R^{\mu\nu},
\qquad
\ldots
$$

In four dimensions, the Gauss–Bonnet density

$$
E_4=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2
$$

is a total derivative on a compact manifold without boundary. This means one can trade one curvature-squared operator for the others in many local perturbative calculations. Boundary terms and topology require care.

## Matter couplings

Matter fields couple to gravity through the metric and covariant derivatives. The matter action may include nonminimal couplings such as

$$
\int d^4x\sqrt{-g}\,\xi R\phi^2
$$

for a scalar field. In EFT, this term is not exotic; it is allowed by diffeomorphism invariance and should be included unless a symmetry forbids it.

When heavy matter of mass $M$ is integrated out, it generates local curvature operators:

$$
\Delta S_{\text{eff}}
=\int d^4x\sqrt{-g}\left[
\Delta\Lambda_{\text{cc}}
+\Delta M_{\text{Pl}}^2 R
+\Delta c_1 R^2
+\Delta c_2 R_{\mu\nu}R^{\mu\nu}
+\cdots
\right].
$$

At energies much below $M$, the heavy field does not need to appear as a particle. Its effects are encoded in Wilson coefficients.

This is the same logic as every other EFT. Gravity is unusual because the metric is universal and the leading interaction is fixed by diffeomorphism invariance, but the Wilsonian logic is not unusual.

## Analytic and nonanalytic terms

A central distinction in gravitational EFT is between analytic local terms and nonanalytic long-distance terms.

Short-distance physics contributes analytic expansions in momenta, such as

$$
q^2,
\qquad
q^4,
\qquad
q^6,
\qquad
\ldots
$$

These are represented by local operators and their coefficients depend on unknown UV physics.

Massless propagation produces nonanalytic terms, such as

$$
q^2\log(-q^2),
\qquad
\sqrt{-q^2},
\qquad
\log(-q^2),
$$

with the precise form depending on the process and signature. These nonanalytic terms encode long-distance propagation and cannot be mimicked by local counterterms. That is why low-energy quantum gravity can make universal predictions despite unknown short-distance coefficients.

In position space, nonanalytic momentum dependence becomes long-range corrections. Analytic terms become contact terms or short-range contributions.

## Quantum corrections are small, not absent

For scattering at center-of-mass energy $E$, the gravitational loop expansion is controlled by powers of

$$
\frac{E^2}{16\pi^2M_{\text{Pl}}^2}.
$$

This is tiny for ordinary particle physics energies. The smallness does not mean the quantum theory is meaningless. It means quantum gravity effects are extremely suppressed in low-energy scattering.

Near strong curvature or near the Planck scale, the expansion can fail. The EFT itself tells you when not to trust it:

$$
E\sim M_{\text{Pl}},
\qquad
R\sim M_{\text{Pl}}^2,
\qquad
L\sim M_{\text{Pl}}^{-1}.
$$

At that point, infinitely many higher-dimension operators can become important, and a UV completion or nonperturbative definition is needed.

## Background-field method

Perturbative gravitational EFT is usually organized with the background-field method. One writes

$$
g_{\mu\nu}=\bar g_{\mu\nu}+\kappa h_{\mu\nu},
$$

fixes gauge for the fluctuation $h_{\mu\nu}$, and computes the effective action as a functional of the background $\bar g_{\mu\nu}$.

The advantage is that background diffeomorphism invariance is manifest. The counterterms then appear as covariant curvature invariants:

$$
\Gamma[\bar g]
=\int d^4x\sqrt{-\bar g}\left[
-\Lambda_{\text{cc}}
+\frac{M_{\text{Pl}}^2}{2}\bar R
+c_1\bar R^2
+c_2\bar R_{\mu\nu}\bar R^{\mu\nu}
+\cdots
\right].
$$

Gauge fixing and ghosts are still required, but the final renormalized effective action respects the background symmetry.

## Power counting

A compact way to count gravitational EFT orders is to assign two derivatives to each curvature:

$$
R\sim \partial^2 g.
$$

Thus:

| Term | Derivative order | Role |
|---|---:|---|
| $\Lambda_{\text{cc}}$ | 0 | vacuum energy, background curvature |
| $M_{\text{Pl}}^2 R$ | 2 | classical general relativity |
| $R^2$, $R_{\mu\nu}R^{\mu\nu}$ | 4 | leading local higher-curvature corrections |
| $R^3$, $R\Box R$ | 6 | next curvature corrections |
| higher terms | $8$ and above | increasingly suppressed at low curvature |

In a process with characteristic length $L$, curvature scales as

$$
R\sim \frac{1}{L^2}.
$$

The ratio of a curvature-squared correction to the Einstein–Hilbert term is roughly

$$
\frac{R^2}{M_{\text{Pl}}^2 R}\sim \frac{1}{M_{\text{Pl}}^2L^2}.
$$

This is tiny when $L\gg M_{\text{Pl}}^{-1}$ unless the dimensionless coefficient is unusually large because of other thresholds.

## Boundaries and total derivatives

Gravity is sensitive to boundaries. The Einstein–Hilbert action contains second derivatives of the metric, so a well-posed variational principle with fixed boundary metric requires a boundary term, the Gibbons–Hawking–York term. Higher-curvature operators also require appropriate boundary terms if the spacetime has boundaries or if one wants a precise variational problem.

For local scattering around flat spacetime, boundary terms are often invisible. For black holes, cosmology, AdS/CFT, finite regions, or entanglement calculations, they can be essential.

The lesson for EFT is simple: local bulk operators are not the whole story when boundaries are part of the physics.

## What gravitational EFT does not solve

Gravitational EFT does not provide a UV-complete theory of quantum gravity. It does not by itself resolve singularities, explain black-hole microstates, define all Planckian scattering amplitudes, or determine the infinite list of Wilson coefficients from first principles.

What it does provide is still enormous:

- a controlled low-energy quantum theory of gravitons and matter;
- a systematic expansion of corrections to general relativity;
- a clean separation of long-distance universal effects from short-distance unknowns;
- a framework for post-Newtonian, black-hole, cosmological, and semiclassical calculations;
- a consistency language for comparing candidate UV completions.

Calling it merely "nonrenormalizable" misses the point. The modern question is not whether every divergence can be absorbed into finitely many constants. The question is what precision is being requested at what energy.

## Common pitfalls

**Saying quantum gravity cannot be treated with QFT.** It can be treated as a low-energy EFT. What fails is extrapolating the same finite-parameter perturbative theory to arbitrarily high energy.

**Confusing the Planck scale with every gravitational scale.** Large classical gravitational effects can occur at low curvature, for example around macroscopic bodies. Quantum gravitational loop effects are controlled by different parameters.

**Dropping all higher-curvature terms.** They are suppressed, not forbidden. If the calculation asks for the corresponding precision, they must be included.

**Treating analytic and nonanalytic terms the same way.** Analytic momentum dependence can be shifted into local Wilson coefficients. Nonanalytic terms from massless propagation encode long-distance physics and can be universal.

**Forgetting gauge dependence.** Off-shell Green functions and intermediate graviton diagrams depend on gauge choices. Physical observables and covariant effective-action statements must be formulated carefully.

**Ignoring the cosmological constant.** The cosmological constant is the leading zero-derivative operator in the gravitational action. It is not an optional afterthought, even if many flat-space calculations set it to zero.

## Relations to other pages

Gravitational EFT is a major example of [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/). It uses [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/). It also connects to [Naturalness and Power Counting](/renormalization-rg-eft/naturalness-power-counting/) through the cosmological constant and scalar-mass hierarchy problems.

The detailed physics of quantum fields on curved backgrounds, stress-tensor renormalization, trace anomalies, black holes, and holography belongs in the spacetime and gravity volumes. This page is the EFT doorway.

## Research status

The EFT treatment of general relativity is established. It gives a systematic low-energy expansion and a clear separation between local Wilson coefficients and nonanalytic long-distance quantum effects. Active research includes high-order post-Newtonian EFT calculations for gravitational waves, worldline EFTs for compact objects, cosmological EFTs, black-hole absorption and tidal response, infrared structure of gravity, positivity and causality constraints, and the relation between low-energy EFT data and possible UV completions.

## Exercises

### Exercise 1: Dimension of Newton's constant

In four spacetime dimensions, use $S_{\text{EH}}=(M_{\text{Pl}}^2/2)\int d^4x\sqrt{-g}R$ to find the mass dimension of $G$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless and

$$
[d^4x]=-4,
\qquad
[R]=2.
$$

Therefore the coefficient of $R$ must have dimension $2$:

$$
[M_{\text{Pl}}^2]=2.
$$

Since $M_{\text{Pl}}^2=1/(8\pi G)$,

$$
[G]=-2.
$$

Equivalently, $[\kappa]=-1$ for $\kappa^2=32\pi G$.

</details>

### Exercise 2: Suppression of curvature-squared terms

Estimate the ratio of a curvature-squared correction $\int\sqrt{-g}\,cR^2$ to the Einstein–Hilbert term on a background with curvature radius $L$.

<details><summary><strong>Solution</strong></summary>

On a background of radius $L$,

$$
R\sim L^{-2}.
$$

The Einstein–Hilbert density scales as

$$
M_{\text{Pl}}^2R\sim M_{\text{Pl}}^2L^{-2},
$$

while the curvature-squared density scales as

$$
cR^2\sim cL^{-4}.
$$

The ratio is

$$
\frac{cR^2}{M_{\text{Pl}}^2R}
\sim \frac{c}{M_{\text{Pl}}^2L^2}.
$$

For dimensionless $c$ of order one, this is small when $L\gg M_{\text{Pl}}^{-1}$.

</details>

### Exercise 3: Why a local counterterm cannot remove a logarithm

Suppose an amplitude contains a term proportional to $q^4\log(-q^2/\mu^2)$. Explain why a local curvature-squared counterterm can change a polynomial $q^4$ contribution but cannot remove the full logarithmic momentum dependence.

<details><summary><strong>Solution</strong></summary>

A local operator with finitely many derivatives gives a polynomial in momentum. A curvature-squared counterterm contributes analytic terms such as

$$
a(\mu)q^4.
$$

It can shift the coefficient of the local $q^4$ term. It cannot produce or cancel the nonanalytic function

$$
q^4\log(-q^2/\mu^2)
$$

for all $q^2$, because the logarithm is not a polynomial. Such logarithms arise from long-distance propagation of massless fields and carry physical scale dependence that is balanced by the running of local coefficients.

</details>

## References

- J. F. Donoghue, "General Relativity as an Effective Field Theory," for the modern low-energy EFT treatment of quantum gravity.
- C. P. Burgess, *Introduction to Effective Field Theory*, for gravitational EFT as a major example of thinking effectively about scale hierarchies.
- S. Weinberg, "Phenomenological Lagrangians," for the general EFT viewpoint and the logic of writing all operators allowed by symmetries.
- S. Weinberg, *The Quantum Theory of Fields*, for effective field theory, gravity, and symmetry-based organization of low-energy interactions.
- J. F. Donoghue, E. Golowich, and B. Holstein, *Dynamics of the Standard Model* and related EFT reviews, for low-energy gravity and effective actions.
- C. P. Burgess, reviews on quantum gravity in everyday life, for accessible power-counting and conceptual discussions.

## Version history

- 2026-06-19: First polished draft. Introduced general relativity as EFT, curvature expansion, matter matching, analytic versus nonanalytic terms, background-field organization, power counting, boundaries, limitations, and common pitfalls.
