---
title: "Faddeev–Popov Ghosts"
description: "Derives Faddeev–Popov ghosts from the gauge-fixing determinant and explains their statistics, interactions, BRST role, and physical interpretation."
sidebar:
  label: "Faddeev–Popov Ghosts"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.5–15.7; Coleman, Lectures Ch. 31; standard Yang–Mills and BRST treatments."
topics:
  - Faddeev-Popov ghosts
  - ghost fields
  - gauge fixing determinant
  - BRST symmetry
  - ghost number
  - Yang-Mills perturbation theory
canonicalTopics:
  - faddeev-popov-ghost
  - ghost-action
  - ghost-number
  - brst-symmetry
  - faddeev-popov-determinant
researchStatus:
  established:
    - "Faddeev–Popov ghosts are Grassmann-odd fields that exponentiate the gauge-orbit Jacobian in gauge-fixed path integrals."
    - "In non-Abelian covariant gauges ghosts are essential for unitarity, locality, renormalizability, and Slavnov–Taylor identities, though they are not physical external particles."
  active:
    - "The status of ghost and BRST descriptions beyond perturbation theory is subtle in the presence of Gribov copies, boundaries, and non-Lagrangian generalized gauge structures."
---

## Summary

Faddeev–Popov ghosts are not spooky extra particles hiding in a gauge theory. They are anticommuting fields that represent the determinant produced by gauge fixing. In non-Abelian gauge theory, the Faddeev–Popov determinant depends on the gauge field, so it contributes interaction vertices. Those vertices are encoded by ghost fields.

For a gauge condition $\mathcal F^a[A]=0$, the gauge-fixed path integral contains

$$
\Delta_{\mathcal F}[A]
=\det M[A],
\qquad
M^{ab}(x,y;A)
=\left.\frac{\delta\mathcal F^a[A^\alpha](x)}{\delta\alpha^b(y)}\right|_{\alpha=0}.
$$

A determinant of a bosonic operator can be written using Grassmann variables:

$$
\det M
=\int\mathcal D\bar c\,\mathcal D c\,
\exp\left(i\int d^4x\,\bar c^a M^{ab}c^b\right),
$$

up to convention-dependent signs and normalizations. The fields $c^a$ and $\bar c^a$ are the Faddeev–Popov ghost and antighost.

<figure class="doc-figure" style="--figure-width: 52rem;">

![The Faddeev–Popov determinant as a gauge-orbit Jacobian represented by ghost and antighost fields, leading to ghost propagators and ghost-gauge interactions.](/figures/symmetry-anomalies-topology/faddeev-popov-ghost-determinant.svg)

<figcaption>

The Faddeev–Popov determinant is the Jacobian for slicing gauge orbits. Exponentiating it introduces Grassmann-odd ghost fields $c$ and $\bar c$. In Abelian linear gauges the determinant is field-independent; in non-Abelian gauges it produces ghost-gauge interactions.

</figcaption>
</figure>

Ghosts are Lorentz scalars but Grassmann odd. This does not violate the spin-statistics theorem because they are not physical asymptotic particles. They are bookkeeping fields inside a gauge-fixed, redundant description. Their real job is to cancel unphysical gauge-boson contributions and to make BRST symmetry local and manifest.

## Prerequisites

Read [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/) first. You should understand the Faddeev–Popov insertion, the covariant gauge condition $\partial^\mu A_\mu^a=0$, and why non-Abelian gauge fixing produces a field-dependent determinant.

You should also be familiar with Grassmann Gaussian integrals from path-integral QFT, at least at the level of the identity that fermionic Gaussian integration gives a determinant rather than an inverse determinant.

## Core idea

The Faddeev–Popov determinant is a Jacobian. Ghost fields are an efficient representation of that Jacobian.

For ordinary commuting variables,

$$
\int d^n x\,\exp\left(\frac{i}{2}x^TAx\right)
\propto (\det A)^{-1/2}.
$$

For Grassmann variables,

$$
\int d\bar\theta_n\,d\theta_n\cdots d\bar\theta_1\,d\theta_1\,
\exp\left(i\bar\theta_i M_{ij}\theta_j\right)
\propto \det M.
$$

The determinant appears in the numerator, not the denominator. That is exactly what gauge fixing needs. Therefore one writes

$$
\Delta_{\mathcal F}[A]
=\det M[A]
=\int\mathcal D\bar c\,\mathcal D c\,e^{iS_{\rm gh}[A,\bar c,c]}.
$$

The ghost fields have no independent classical counterpart. They are born from the measure.

## Setup and conventions

Use the same non-Abelian convention as the previous page:

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
\qquad
D_\mu=\partial_\mu+igA_\mu.
$$

For matter transforming as $\psi\mapsto U^{-1}\psi$, the gauge field transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

With $U=1+ig\alpha+O(\alpha^2)$,

$$
\delta_\alpha A_\mu=\mathcal D_\mu\alpha
=\partial_\mu\alpha+ig[A_\mu,\alpha].
$$

For Lorenz gauge,

$$
\mathcal F^a[A]=\partial^\mu A_\mu^a,
$$

the Faddeev–Popov operator is

$$
M^{ab}[A]=\partial^\mu\mathcal D_\mu^{ab}.
$$

A common Lorentzian ghost Lagrangian is

$$
\mathcal L_{\rm gh}
=-\bar c^a\,\partial^\mu\mathcal D_\mu^{ab}c^b.
$$

Equivalently, after integrating by parts and ignoring boundary terms, the interaction may be written schematically as

$$
\mathcal L_{\rm gh}
=\partial^\mu\bar c^a\,\mathcal D_\mu^{ab}c^b.
$$

These forms differ by integrations by parts and sign conventions for $M$.

:::note[Convention-sensitive source note]
The ghost action is tied to the definitions of $D_\mu$, $A_\mu^U$, $\mathcal F[A]$, and the Lorentzian phase $e^{iS}$. Many sources write $\mathcal L_{\rm gh}=\bar c^a\partial^\mu D_\mu^{ab}c^b$ or $-\partial^\mu\bar c^aD_\mu^{ab}c^b$. The safest invariant statement is that ghost integration represents $\det(\delta\mathcal F[A^\alpha]/\delta\alpha)$.
:::

## Derivation from the determinant

Start from the gauge-fixed path integral

$$
Z
=\int\mathcal D A\,\Delta_{\mathcal F}[A]\,\delta[\mathcal F[A]]\,e^{iS[A]}.
$$

For a covariant $R_\xi$ gauge, replace the sharp delta-functional by a Gaussian average to obtain

$$
Z
=\int\mathcal D A\,\Delta_{\mathcal F}[A]
\exp\left(iS[A]+i\int d^4x\,\mathcal L_{\rm gf}\right),
$$

with

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2.
$$

Now write

$$
\Delta_{\mathcal F}[A]
=\det M[A]
=\int\mathcal D\bar c\,\mathcal D c\,
\exp\left(i\int d^4x\,\bar c^a M^{ab}[A]c^b\right)
$$

up to the sign convention already noted. Then

$$
Z
=\int\mathcal D A\,\mathcal D\bar c\,\mathcal D c\,
\exp\left(i\int d^4x\,\mathcal L_{\rm gf+gh+YM}\right),
$$

where

$$
\mathcal L_{\rm gf+gh+YM}
=\mathcal L_{\rm YM}+\mathcal L_{\rm gf}+\mathcal L_{\rm gh}.
$$

This is the practical starting point for covariant perturbation theory in Yang–Mills theory.

## Abelian versus non-Abelian ghosts

In Abelian gauge theory with Lorenz gauge,

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
\mathcal F[A]=\partial^\mu A_\mu,
$$

so

$$
M=\Box.
$$

The determinant $\det\Box$ does not depend on $A_\mu$. If no other fields couple to the ghost, the ghost path integral is just an overall constant. Abelian Faddeev–Popov ghosts decouple in ordinary linear covariant gauges.

In non-Abelian gauge theory,

$$
M^{ab}[A]=\partial^\mu\mathcal D_\mu^{ab}
$$

contains $A_\mu$. Therefore the determinant changes from configuration to configuration, and the ghost fields interact with gauge fields.

Expanding the ghost Lagrangian gives a free part plus an interaction:

$$
\mathcal L_{\rm gh}
= -\bar c^a\Box c^a
+\text{ghost–gauge interaction}.
$$

In a common integrated-by-parts form, the interaction is proportional to

$$
g f^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c,
$$

up to the sign convention for the adjoint covariant derivative.

This single vertex is enough to generate ghost loops. In Yang–Mills perturbation theory those loops are essential: they cancel the contributions of unphysical gauge polarizations in precisely the way required by gauge invariance.

## What kind of fields are ghosts?

Faddeev–Popov ghosts have unusual properties:

| Property | Ghost $c^a$ and antighost $\bar c^a$ |
|---|---|
| Lorentz spin | scalar |
| Statistics | Grassmann odd |
| Gauge representation | adjoint |
| Physical external states? | no |
| Ghost number | $\operatorname{gh}(c)=+1$, $\operatorname{gh}(\bar c)=-1$ |
| Origin | Faddeev–Popov determinant |

The phrase “scalar fermion” is sometimes used, but it can mislead. Ghosts are not physical spin-zero fermionic particles. They are anticommuting scalar fields in a gauge-fixed auxiliary description.

Their wrong-looking spin-statistics assignment is allowed because ghosts are not in the physical Hilbert space. Physical states are selected by constraints or, in covariant language, by BRST cohomology. Ghosts can run in internal lines, but they do not appear as incoming or outgoing particles in physical scattering processes.

## Ghost number

The ghost action in ordinary Yang–Mills gauges has a global grading called ghost number:

$$
\operatorname{gh}(c)=+1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(A_\mu)=0.
$$

The gauge-fixed action has total ghost number zero. This grading becomes central in BRST theory because the BRST differential raises ghost number by one:

$$
\operatorname{gh}(s\mathcal O)=\operatorname{gh}(\mathcal O)+1.
$$

Physical gauge-invariant operators usually live at ghost number zero in BRST cohomology. Anomalies, gauge-fixing fermions, and descent equations also carry ghost-number bookkeeping.

## Ghost loops and the cancellation of unphysical modes

Covariant gauge fixing keeps four components of $A_\mu$ in intermediate formulas. A massless vector particle has only two physical transverse polarizations. Something must cancel the unphysical longitudinal and timelike pieces in gauge-invariant observables.

In non-Abelian gauge theory, ghost loops provide part of this cancellation. For example, the one-loop gauge-boson self-energy receives contributions from:

$$
\text{gauge-boson loop}
\quad+
\text{ghost loop}
\quad+
\text{matter loops, if present}.
$$

The ghost loop has a minus sign from Grassmann integration. It is not optional. Without it, the self-energy is not transverse in the way required by gauge invariance, and the resulting perturbation theory fails.

Said differently:

$$
\text{ghosts cancel gauge-coordinate artifacts, not real particles.}
$$

This is why ghosts do not decouple in non-Abelian covariant gauges even though they are not observable.

## Relation to BRST symmetry

Ghosts become conceptually clean in BRST language. Replace the infinitesimal gauge parameter $\alpha$ by a Grassmann-odd field $c$. Then the gauge transformation becomes part of a fermionic transformation $s$:

$$
sA_\mu=\mathcal D_\mu c.
$$

The ghost transforms into its own nonlinear gauge-algebra product:

$$
sc=-\frac{ig}{2}[c,c],
$$

or in components, with convention-dependent signs,

$$
sc^a\propto f^{abc}c^b c^c.
$$

Introduce an auxiliary Nakanishi–Lautrup field $B^a$ and set

$$
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

Then the gauge-fixing and ghost terms can be written as a BRST variation:

$$
\mathcal L_{\rm gf}+\mathcal L_{\rm gh}
=s\Psi
$$

for an appropriate gauge-fixing fermion $\Psi$. For Lorenz-type gauges, a typical choice is schematically

$$
\Psi=\bar c^a\left(\partial^\mu A_\mu^a+\frac{\xi}{2}B^a\right).
$$

After eliminating $B^a$, one recovers the familiar $R_\xi$ gauge-fixing term and ghost action.

The nilpotence condition

$$
s^2=0
$$

encodes the closure of the gauge algebra. Physical operators are BRST-closed modulo BRST-exact operators:

$$
s\mathcal O=0,
\qquad
\mathcal O\sim\mathcal O+s\Lambda.
$$

That is the cohomological replacement for imposing gauge invariance after gauge fixing.

## Ghosts are not Pauli–Villars regulators

Ghosts are sometimes confused with regulator fields because both can have unfamiliar signs. They are different objects.

Pauli–Villars fields are introduced to regulate ultraviolet divergences. Their masses and signs are chosen so that loop integrals become finite, and they are removed or decoupled after renormalization.

Faddeev–Popov ghosts are introduced to represent the gauge-fixing determinant. They remain part of the gauge-fixed formulation at every scale. In non-Abelian gauge theory they are required even after the theory has been renormalized.

A quick diagnostic is:

$$
\text{regulator field} \rightarrow \text{controls UV behavior},
\qquad
\text{ghost field} \rightarrow \text{controls gauge-orbit overcounting}.
$$

## Ghosts in different gauges

Ghost visibility depends on gauge choice.

In Abelian covariant gauges, ghosts decouple because the determinant is field-independent. In non-Abelian covariant gauges, ghosts interact.

In axial gauges, the Faddeev–Popov determinant is often independent of $A_\mu$, so ghosts can decouple perturbatively. However, axial gauges introduce other complications, such as prescriptions for $1/(n\cdot p)$ poles and subtle boundary or residual gauge issues.

In background-field gauges, ghosts couple to both background and quantum gauge fields in a way that preserves background gauge covariance. This is one reason background-field gauge is powerful for beta-function calculations and effective actions.

In non-linear gauges, even Abelian theories can produce field-dependent determinants. Decoupling is therefore a statement about a gauge choice, not an intrinsic statement that “Abelian ghosts never exist.” In standard linear QED gauges, they simply do not affect observables.

## Why the determinant is Grassmann, not bosonic

It is tempting to exponentiate a determinant using ordinary commuting fields. But a commuting Gaussian gives an inverse determinant. For a finite-dimensional bosonic variable $\phi$,

$$
\int d^n\phi\,\exp\left(\frac{i}{2}\phi^T M\phi\right)
\propto (\det M)^{-1/2}.
$$

For complex Grassmann variables,

$$
\int d\bar c\,dc\,\exp(i\bar c M c)
\propto \det M.
$$

The Faddeev–Popov factor is $\det M$, so the auxiliary fields must be Grassmann odd. This is the whole algebraic reason ghosts anticommute.

## Common pitfalls

**Pitfall: thinking ghosts are physical particles.** They are internal fields in a gauge-fixed redundant description. Physical external states are selected by gauge constraints or BRST cohomology.

**Pitfall: saying ghosts exist only to cancel infinities.** They are not regulators. They represent the gauge-fixing determinant.

**Pitfall: forgetting ghosts in non-Abelian covariant gauges.** Dropping them breaks Ward/Slavnov–Taylor identities and gives wrong loop amplitudes.

**Pitfall: assuming Abelian ghosts are impossible.** In ordinary linear Abelian gauges they decouple. In unusual non-linear gauge choices, field-dependent determinants can be represented by ghosts, though physical results remain gauge-independent.

**Pitfall: treating ghost number as physical charge.** Ghost number is a grading of the gauge-fixed formalism. It is not an ordinary global symmetry of physical particles.

**Pitfall: ignoring boundary conditions.** Ghost zero modes and residual gauge transformations are tied to gauge fixing. Boundaries and topological sectors can make the determinant singular or require special treatment.

## Relations to other pages

This page follows [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/) and prepares for [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/). The BRST page explains why ghost fields are not just a calculational trick but part of a cohomological formulation of gauge-fixed QFT.

This page also connects to [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/): a gauge anomaly is precisely a failure of the quantum measure to respect the gauge symmetry needed for consistent BRST invariance. [Physical State Space](/symmetry-anomalies-topology/gauge-redundancy-brst/physical-state-space/) will explain why ghosts are excluded from physical external states.

In the Gauge Theories and Standard Model volume, ghosts reappear in Yang–Mills Feynman rules, QCD loop calculations, beta functions, Slavnov–Taylor identities, and background-field gauge.

## Research status

Faddeev–Popov ghosts are established perturbative technology. They are indispensable in covariant quantization of non-Abelian gauge theories and are part of the standard proof structure for renormalizability and gauge invariance.

The nonperturbative global story is subtler. Gribov copies obstruct a naive global Faddeev–Popov slice. Boundaries can turn would-be gauge parameters into physical edge data. Modern generalized symmetry and topological field theory often reformulate ghost-free or cohomological aspects of gauge constraints in ways that go beyond the simplest perturbative picture.

## Exercises

### Exercise 1. Grassmann determinant in one dimension

Let $\bar c$ and $c$ be Grassmann variables. Show that

$$
\int d\bar c\,dc\,e^{\bar c M c}=M
$$

up to the chosen ordering convention for $d\bar c\,dc$.

<details><summary><strong>Solution</strong></summary>

Since Grassmann variables square to zero,

$$
e^{\bar c M c}=1+\bar c M c.
$$

The integral of the constant term vanishes. The integral of the top Grassmann monomial is fixed by convention. With the convention

$$
\int d\bar c\,dc\,\bar c c=1,
$$

we get

$$
\int d\bar c\,dc\,e^{\bar c M c}=M.
$$

For $n$ pairs of Grassmann variables, the same logic gives $\det M$.

</details>

### Exercise 2. Abelian ghost decoupling

For Lorenz gauge in QED, compute the Faddeev–Popov operator and explain why ghosts do not interact with $A_\mu$.

<details><summary><strong>Solution</strong></summary>

The Abelian gauge transformation is

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

With

$$
\mathcal F[A]=\partial^\mu A_\mu,
$$

we get

$$
\mathcal F[A^\alpha]=\partial^\mu A_\mu+\Box\alpha.
$$

Therefore

$$
M=\Box.
$$

The ghost action is proportional to

$$
\bar c\Box c,
$$

with no $A_\mu$ dependence. The ghost integral is an overall determinant independent of the gauge field, so it cancels from normalized correlators of ordinary fields.

</details>

### Exercise 3. Non-Abelian ghost interaction

For Lorenz gauge in Yang–Mills theory, use

$$
\delta A_\mu=\mathcal D_\mu\alpha
$$

to show that the Faddeev–Popov operator depends on $A_\mu$.

<details><summary><strong>Solution</strong></summary>

Lorenz gauge has

$$
\mathcal F^a[A]=\partial^\mu A_\mu^a.
$$

Under an infinitesimal gauge transformation,

$$
\delta\mathcal F^a[A]
=\partial^\mu(\mathcal D_\mu\alpha)^a.
$$

Thus

$$
M^{ab}[A]=\partial^\mu\mathcal D_\mu^{ab}.
$$

Since

$$
\mathcal D_\mu^{ab}
=\delta^{ab}\partial_\mu+\text{terms proportional to }A_\mu,
$$

the operator $M[A]$ depends on the gauge field. Exponentiating $\det M[A]$ therefore gives ghost-gauge interactions.

</details>

### Exercise 4. Ghost number of the ghost action

Assign

$$
\operatorname{gh}(c)=+1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(A_\mu)=0.
$$

Show that $\bar c^a\partial^\mu\mathcal D_\mu^{ab}c^b$ has ghost number zero.

<details><summary><strong>Solution</strong></summary>

The derivative and gauge field have ghost number zero, so $\partial^\mu\mathcal D_\mu$ has ghost number zero. Therefore

$$
\operatorname{gh}(\bar c^a\partial^\mu\mathcal D_\mu^{ab}c^b)
=\operatorname{gh}(\bar c)+0+\operatorname{gh}(c)
=-1+1=0.
$$

The ghost action preserves total ghost number.

</details>

### Exercise 5. Why a ghost loop has a minus sign

Explain why a closed ghost loop carries a minus sign relative to a closed bosonic scalar loop.

<details><summary><strong>Solution</strong></summary>

Ghosts are Grassmann odd. In perturbation theory, Wick contractions of Grassmann fields require anticommuting the fields past one another to close the loop. This produces the same characteristic minus sign as a closed fermion loop.

The ghost is not a physical fermion, but its path-integral algebra is fermionic. Therefore closed ghost loops carry a minus sign relative to bosonic loops.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§71–74. Non-Abelian gauge path integrals, ghosts, and BRST.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.5–15.7. DeWitt–Faddeev–Popov method, ghost fields, and BRST symmetry.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Ch. 31. The Faddeev–Popov prescription and examples.
- S. Coleman, “Secret Symmetry,” in *Aspects of Symmetry*. Gauge-field Feynman rules and the Faddeev–Popov Ansatz.
- L. D. Faddeev and V. N. Popov, “Feynman diagrams for the Yang–Mills field,” *Physics Letters B* **25** (1967) 29–30.
- C. Becchi, A. Rouet, and R. Stora, “Renormalization of gauge theories,” *Annals of Physics* **98** (1976) 287–321.
- I. V. Tyutin, “Gauge invariance in field theory and statistical physics in operator formalism,” Lebedev preprint FIAN 39 (1975), arXiv:0812.0580.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Constraint and BRST formulation.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional and BRST methods for gauge theory.

## Version history

- 2026-06-17: Initial polished draft. Added determinant derivation, ghost action conventions, Abelian versus non-Abelian comparison, ghost number, BRST preview, gauge-dependence caveats, and exercises with solutions.
