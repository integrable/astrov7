---
title: "Gravitational EFT Preview"
description: "A preview of general relativity as a low-energy effective field theory: curvature expansion, graviton power counting, local counterterms, nonanalytic long-distance predictions, and the limits of perturbative quantum gravity."
sidebar:
  label: "Gravitational EFT Preview"
  order: 60
level: Advanced
status: "Polished draft"
source: "Weinberg 1995; Donoghue 1994; Burgess 2020, ch. 10; Birrell and Davies; Parker and Toms; Donoghue and Menezes; Bjerrum-Bohr, Donoghue, and Holstein."
topics:
  - gravitational effective field theory
  - quantum gravity as EFT
  - curvature expansion
  - graviton power counting
  - nonanalytic amplitudes
  - curvature counterterms
canonicalTopics:
  - gravitational-eft
  - effective-field-theory-of-general-relativity
  - curved-spacetime-renormalization
  - quantum-gravity-low-energy-expansion
researchStatus:
  established:
    - "General relativity coupled to matter is a predictive low-energy effective field theory. Perturbative nonrenormalizability means that new local curvature counterterms enter at higher orders, not that low-energy quantum-gravity calculations are meaningless."
  active:
    - "The ultraviolet completion of gravity, black-hole information, nonperturbative definitions, cosmological observables, positivity bounds, infrared subtleties, and the interface with holography remain active research areas."
---

## Summary

General relativity is not perturbatively renormalizable in the old sense: loop diagrams require new local counterterms with more derivatives. As an effective field theory, that fact is not a catastrophe. It is the expected statement that a low-energy theory must include every local interaction allowed by its symmetries, ordered by powers of momentum and curvature.

At energies well below the Planck scale, and at distances large compared with any unknown microscopic scale of gravity, the gravitational action is organized as

$$
S_{\text{grav}}
=
\int d^4x\sqrt{-g}
\left[
-\Lambda_{\text{cc}}
+\frac{M_{\text{Pl}}^2}{2}R
+c_1R^2
+c_2R_{\mu\nu}R^{\mu\nu}
+c_3R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
+\frac{d_i}{M^2}\mathcal R^3
+\cdots
\right]
+S_{\text{matter}},
$$

where $M_{\text{Pl}}=(8\pi G)^{-1/2}$ is the reduced Planck mass and $\mathcal R^3$ denotes cubic curvature invariants schematically. The coefficients $c_i,d_i,\ldots$ are Wilson coefficients. Some absorb loop divergences, some encode heavy short-distance physics, and some can be shifted by field redefinitions, topological identities, or changes of basis.

The low-energy expansion is controlled by dimensionless ratios such as

$$
\frac{E}{M_{\text{Pl}}},
\qquad
\frac{E}{M},
\qquad
\frac{\ell_{\text{Pl}}}{L},
\qquad
\frac{|R|}{M^2},
$$

where $E$ is a typical momentum, $M$ is a heavy threshold, $L$ is a macroscopic length or curvature radius, and $R$ is the Ricci scalar. Local unknowns are absorbed into Wilson coefficients. Nonlocal long-distance terms from massless propagation, such as $q^2\log(-q^2)$ in amplitudes, are not removable by local counterterms and can give genuine low-energy predictions.

The short version is:

$$
\text{gravity is nonrenormalizable as a fundamental perturbative theory}
\quad\text{but}\quad
\text{predictive as a low-energy EFT}.
$$

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Gravitational EFT map from diffeomorphism invariance and Einstein-Hilbert gravity to curvature counterterms, graviton loops, nonanalytic long-distance terms, and low-energy predictions](/figures/renormalization-rg-eft/gravitational-eft-low-energy-map.svg)

<figcaption>

Gravitational EFT separates three kinds of information: diffeomorphism invariance fixes the allowed local curvature terms, loops determine counterterms and long-distance nonanalytic structures, and observables are computed within a controlled expansion in energy and curvature.

</figcaption>
</figure>

## Prerequisites

You should know [Curvature Counterterms](/renormalization-rg-eft/renormalization-curved-spacetime/curvature-counterterms/), [Effective Action in Curved Spacetime](/renormalization-rg-eft/renormalization-curved-spacetime/effective-action-in-curved-spacetime/), [Heat-Kernel Methods Preview](/renormalization-rg-eft/renormalization-curved-spacetime/heat-kernel-methods-preview/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/), and [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/).

You should also be comfortable with classical general relativity at the level of the Einstein–Hilbert action, curvature tensors, covariant derivatives, and gauge redundancy. This page is a preview; a later gravity volume should give the full quantization and amplitude technology.

## Core idea

The old slogan says that quantum general relativity is nonrenormalizable. The EFT slogan says something sharper:

$$
\text{nonrenormalizable}
\quad\not\Rightarrow\quad
\text{nonpredictive}.
$$

The Einstein–Hilbert interaction contains a coupling with negative mass dimension. Expanding around flat spacetime,

$$
g_{\mu\nu}=\eta_{\mu\nu}+\frac{2}{M_{\text{Pl}}}h_{\mu\nu},
$$

each additional graviton interaction brings powers of $1/M_{\text{Pl}}$ and derivatives. Loop diagrams therefore generate divergences requiring higher-derivative curvature counterterms. That is the nonrenormalizability.

But EFT never promised that the leading operator would be the whole theory. It says: write all local operators allowed by the symmetries, order them by scaling, and compute to a fixed accuracy. At any fixed order in $E/M_{\text{Pl}}$, only finitely many terms contribute.

:::note[The useful mental switch]
Do not ask whether the Einstein–Hilbert action alone is closed under renormalization. It is not. Ask whether the diffeomorphism-invariant derivative expansion is closed under renormalization order by order. It is.
:::

## The derivative expansion

Diffeomorphism invariance says that local gravitational terms are scalar densities built from curvature tensors, covariant derivatives, matter fields, and the volume element. Ignoring boundaries for the moment, the first layers are

| Derivative order | Examples | Role |
|---:|---|---|
| 0 | $\sqrt{-g}\,\Lambda_{\text{cc}}$ | vacuum energy, cosmological constant |
| 2 | $\sqrt{-g}\,M_{\text{Pl}}^2R$ | Einstein gravity |
| 4 | $\sqrt{-g}\,R^2$, $\sqrt{-g}\,R_{\mu\nu}R^{\mu\nu}$, $\sqrt{-g}\,R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}$ | curvature-squared counterterms and corrections |
| 6 | $\sqrt{-g}\,R^3$, $\sqrt{-g}\,R\nabla^2R$, etc. | higher-accuracy EFT data |

In four dimensions, the Euler density

$$
E_4
=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2
$$

is topological up to boundary terms. This reduces the number of independent local curvature-squared terms in many applications. Equations of motion and field redefinitions can reduce the basis further for on-shell observables.

## Power counting

In four dimensions,

$$
[G]=-2,
\qquad
[M_{\text{Pl}}]=1,
\qquad
[h_{\mu\nu}]=1.
$$

Graviton interactions from the Einstein–Hilbert term are derivative interactions. A rough way to remember the scaling is:

$$
\text{each loop of massless gravitons costs}
\quad
\frac{E^2}{16\pi^2M_{\text{Pl}}^2},
$$

while a curvature-squared insertion contributes powers of $E^2/M_{\text{Pl}}^2$ or $E^2/M^2$, depending on how its coefficient is normalized and which heavy scale generated it.

A low-energy amplitude has the schematic structure

$$
\mathcal A(E)
=\mathcal A_{\text{EH,tree}}(E)
\left[
1
+a\frac{E^2}{M^2}
+b\frac{E^2}{16\pi^2M_{\text{Pl}}^2}\log\frac{-E^2}{\mu^2}
+O\left(\frac{E^4}{M^4}\right)
\right].
$$

The analytic term proportional to $a$ is local Wilson-coefficient data. The logarithm is a nonlocal low-energy loop effect. This analytic/nonanalytic distinction is one of the cleanest ways to see why gravitational EFT predicts more than it parametrizes.

## Local counterterms and famous loop facts

The counterterms allowed by gravitational EFT are exactly the local curvature invariants allowed by diffeomorphism invariance. In four-dimensional pure Einstein gravity, the on-shell one-loop divergence vanishes after using the equations of motion and topological identities. With matter, one-loop curvature-squared counterterms are generally required. Pure gravity has a genuine two-loop divergence requiring a cubic-curvature counterterm.

This famous sequence is often misread. It does not say gravity is almost renormalizable. It says the EFT basis behaves exactly as expected: higher loops and higher precision activate higher-derivative local operators.

For curved-spacetime QFT on a fixed background, the same logic appears even before the metric is dynamical. Matter loops generate local terms such as

$$
\int d^4x\sqrt{-g}\,R^2,
\qquad
\int d^4x\sqrt{-g}\,R_{\mu\nu}R^{\mu\nu},
\qquad
\int d^4x\sqrt{-g}\,\Box R.
$$

Once gravity is dynamical, these terms are part of the gravitational action itself.

## Nonlocal low-energy terms

The renormalized effective action is not only a local curvature expansion. Massless fields generate nonlocal terms. Schematically,

$$
\Gamma[g]
=
\Gamma_{\text{local}}[g;\mu]
+\int d^4x\sqrt{-g}\,
R\log\left(\frac{-\nabla^2}{\mu^2}\right)R
+\cdots.
$$

The tensor structure is suppressed here, but the message is precise. Local counterterms change analytic momentum dependence. They cannot remove branch cuts and logarithms produced by massless propagation. In position space, these nonanalytic terms give long-distance tails rather than contact terms.

That is why gravitational EFT can predict some quantum corrections to long-distance observables even when the local Wilson coefficients are unknown.

## Example: quantum corrections to Newtonian scattering

For two heavy scalar sources scattering gravitationally, the low-momentum amplitude contains analytic pieces and nonanalytic pieces. Analytic terms are polynomial in $q^2$ and can be shifted by local counterterms or short-distance source structure. Nonanalytic terms include structures such as

$$
\sqrt{-q^2},
\qquad
q^2\log(-q^2),
$$

which encode long-distance classical and quantum effects after Fourier transformation. In one common potential convention, the large-distance potential has the schematic form

$$
V(r)
=-\frac{Gm_1m_2}{r}
\left[
1
+O\left(\frac{G(m_1+m_2)}{r}\right)
+O\left(\frac{G}{r^2}\right)
+\cdots
\right].
$$

The first correction is classical post-Newtonian physics. The second is quantum, suppressed by $\ell_{\text{Pl}}^2/r^2$. It is too small to measure in ordinary gravity, but it is conceptually important: quantum gravity has low-energy predictions without knowing its UV completion.

## Relation to other gravitational EFTs

Several EFTs appear under the gravitational umbrella.

| EFT | Degrees of freedom | Typical use |
|---|---|---|
| Graviton EFT | metric fluctuations and light matter | low-energy quantum gravity amplitudes |
| Curved-background EFT | quantum matter on fixed $g_{\mu\nu}$ | stress tensor, anomalies, cosmology, Hawking-like settings |
| Worldline EFT | compact objects plus long-wavelength gravity | binaries, tidal response, radiation reaction |
| Inflationary EFT | Goldstone or metric perturbations around cosmological backgrounds | primordial correlators and slow-roll corrections |
| Holographic EFT | radial gravity dynamics and boundary sources | strongly coupled RG flows and response functions |

These are not contradictory. They are different low-energy descriptions adapted to different scale separations.

## Common pitfalls

**Saying nonrenormalizable means useless.** It means infinitely many counterterms are needed for arbitrary precision at arbitrary energy. It does not prevent fixed-order low-energy predictions.

**Confusing the Planck scale with the only possible EFT cutoff.** New heavy particles, compact-object radii, string scales, Kaluza–Klein scales, or strong-coupling scales may appear below $M_{\text{Pl}}$.

**Treating the potential as the only observable.** Gravitational potentials are useful in nonrelativistic limits but can be gauge- and convention-sensitive. Scattering amplitudes, asymptotic observables, and relational quantities require careful definitions.

**Forgetting the cosmological constant.** The vacuum-energy term is the lowest-derivative gravitational operator. Its observed smallness is a naturalness problem, not something automatically solved by EFT bookkeeping.

**Thinking local curvature terms are optional.** They are required by the EFT expansion and by renormalization of quantum fields in curved spacetime.

## Relations to other pages

This page closes the curved-spacetime chapter by connecting background-field renormalization to dynamical gravity. The detailed EFT application page is [Gravitational Effective Field Theory](/renormalization-rg-eft/major-efts/gravitational-effective-field-theory/), and compact-object applications belong to [Worldline Effective Field Theory](/renormalization-rg-eft/major-efts/worldline-effective-field-theory/).

For general EFT logic, use [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) and [Matching, Running, and Decoupling](/renormalization-rg-eft/matching-running-decoupling/). For black holes, holography, and quantum spacetime questions, the natural home is the Spacetime, Gravity, and Holography volume.

## Research status

Established: perturbative quantum general relativity is a low-energy EFT with controlled predictions below its cutoff. Diffeomorphism invariance fixes the operator basis, while renormalization determines scale dependence and nonlocal loop structures.

Active: precision gravitational scattering, infrared factorization, soft theorems, worldline EFT for binaries, finite-size effects, quantum corrections to black-hole backgrounds, cosmological EFT, and positivity constraints are active.

Speculative: gravitational EFT does not decide the UV completion. Strings, holography, asymptotic safety, causal dynamical triangulations, loop quantum gravity, and other programs make additional claims beyond the EFT regime.

## Exercises

### Exercise 1: Dimension of Newton's constant

In $d$ spacetime dimensions, use

$$
S_{\text{EH}}\sim \frac{1}{G_d}\int d^dx\sqrt{-g}\,R
$$

to find $[G_d]$.

<details><summary><strong>Solution</strong></summary>

The action is dimensionless. Since $[d^dx]=-d$ and $[R]=2$, the integral has dimension $2-d$. Therefore $1/G_d$ must have dimension $d-2$, and

$$
[G_d]=2-d.
$$

In four dimensions, $[G]=-2$.

</details>

### Exercise 2: Analytic versus nonanalytic terms

Why can a local curvature counterterm change a term proportional to $q^4$ in a momentum-space amplitude but not a term proportional to $q^4\log(-q^2)$?

<details><summary><strong>Solution</strong></summary>

A local counterterm contains a finite number of derivatives at a point. In momentum space, it produces a polynomial in external momenta, such as $q^2$, $q^4$, or contractions among external momenta. A logarithm such as $\log(-q^2)$ has a branch cut and cannot be reproduced by a finite polynomial. It reflects propagation over long distances or through massless thresholds, so it is not removable by changing local Wilson coefficients.

</details>

### Exercise 3: Fixed-order predictivity

Suppose an EFT amplitude is organized as

$$
\mathcal A(E)
=A_0E^2+A_1\frac{E^4}{M^2}+A_{\text{loop}}\frac{E^4}{16\pi^2M_{\text{Pl}}^2}\log\frac{-E^2}{\mu^2}+O(E^6).
$$

How many unknown local coefficients are needed to predict the amplitude through order $E^4$?

<details><summary><strong>Solution</strong></summary>

At order $E^4$, one needs the local coefficient or combination of coefficients represented by $A_1$. The logarithmic coefficient $A_{\text{loop}}$ is determined by low-energy loops once the light fields and leading couplings are fixed. Higher-order local coefficients first enter at $O(E^6)$ and are not needed for an $E^4$ prediction.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for the EFT view of renormalization and gravitational interactions.
- John F. Donoghue, "General Relativity as an Effective Field Theory," *Physical Review D* **50** (1994), for the classic formulation of low-energy quantum GR.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the treatment of general relativity as an EFT.
- N. D. Birrell and P. C. W. Davies, *Quantum Fields in Curved Space*, for quantum matter in curved backgrounds.
- L. Parker and D. Toms, *Quantum Field Theory in Curved Spacetime*, for effective actions and curvature counterterms.
- G. 't Hooft and M. Veltman; M. Goroff and A. Sagnotti, for classic loop-divergence results in perturbative quantum gravity.
- N. E. J. Bjerrum-Bohr, J. F. Donoghue, and B. R. Holstein, for long-distance quantum corrections from low-energy gravity.

## Version history

- 2026-06-19: First polished draft. Added curvature expansion, gravitational EFT power counting, local/nonlocal distinction, low-energy predictivity, common pitfalls, exercises, and figure.
