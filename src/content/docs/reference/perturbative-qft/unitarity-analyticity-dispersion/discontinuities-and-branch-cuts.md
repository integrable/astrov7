---
title: "Discontinuities and Branch Cuts"
description: "Analytic structure of scattering amplitudes: boundary values, discontinuities, thresholds, branch cuts, spectral densities, and the link to unitarity cuts."
sidebar:
  label: "Discontinuities and Branch Cuts"
  order: 3
level: Graduate
status: "Polished draft"
source: "Landau 1959; Cutkosky 1960; Eden et al.; Weinberg Vol. I; Schwartz ch. 24; Srednicki §§13 and 20"
topics:
  - analytic structure
  - discontinuities
  - branch cuts
  - thresholds
  - dispersion relations
  - unitarity
canonicalTopics:
  - discontinuities
  - branch-cuts
  - analytic-structure-of-amplitudes
  - thresholds
researchStatus:
  established:
    - "Poles, thresholds, branch cuts, and discontinuities are standard analytic features of perturbative amplitudes and exact correlation functions under the usual assumptions of locality, unitarity, and spectral positivity."
  active:
    - "Modern work uses analytic structure in amplitude bootstrap, dispersion relations, positivity bounds, finite-density response, Landau-singularity analysis, and multi-loop integral classification."
---

## Summary

Scattering amplitudes and momentum-space correlators are not arbitrary functions of kinematic invariants. They are boundary values of analytic functions with singularities controlled by locality, unitarity, causality, and spectrum.

The most common singular structures are:

| Analytic feature | Physical interpretation |
|---|---|
| pole | stable one-particle state or bound state, depending on the sheet and channel |
| branch point | opening of a continuum of intermediate states, usually a threshold |
| branch cut | a chosen line connecting branch points or extending to infinity |
| discontinuity | jump between the two sides of a cut |
| second-sheet pole | resonance or unstable state in many scattering problems |

For an amplitude or integral $F(s)$ with a cut along the real $s$ axis, the discontinuity is

$$
\operatorname{Disc}_sF(s)
\equiv F(s+i0)-F(s-i0).
$$

If $F$ is real analytic in the relevant region, then on the cut

$$
\operatorname{Disc}_sF(s)=2i\operatorname{Im}F(s+i0).
$$

<figure class="doc-figure" style="--figure-width: 38rem; --caption-width: 52rem;">

![A branch cut has two boundary values whose jump is the discontinuity](/figures/perturbative-qft/discontinuities-and-branch-cuts.svg)

<figcaption>

A physical branch point, such as a threshold $s_{\rm th}$, produces two boundary values $F(s+i0)$ and $F(s-i0)$ on the cut. Their difference is the discontinuity. The exact path chosen for the cut is conventional; the branch point, monodromy, and discontinuity are the invariant analytic data.

</figcaption>
</figure>

Cutkosky rules compute these discontinuities diagrammatically. Dispersion relations use them in the opposite direction: under suitable assumptions, the amplitude can be reconstructed from its discontinuities up to subtraction constants.

## Prerequisites

You should know [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/), [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/), and [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/).

For the phase-space side of the story, review [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/).

## Core idea

A loop amplitude is an analytic function until the integration contour is trapped between singularities. When internal propagators can go on shell in a way compatible with momentum conservation, the contour is pinched. The amplitude then develops a singularity as a function of external kinematics.

For ordinary two-particle thresholds, this produces a branch point. The amplitude is single-valued only after one specifies a Riemann sheet. On the physical sheet, the Feynman $+i0$ prescription tells us which boundary value is reached from physical scattering kinematics.

The discontinuity across the cut measures the failure of the two boundary values to agree. In unitary QFT, that jump is not mysterious: it is controlled by physical intermediate states.

The analytic chain is:

1. a threshold opens;
2. intermediate states can go on shell;
3. the loop develops a branch cut;
4. the discontinuity equals a cut phase-space integral.

This is the analytic form of the same physics expressed diagrammatically by Cutkosky rules.

## Setup and conventions

We discuss amplitudes as functions of a complex Mandelstam invariant $s$, with other invariants held fixed when necessary. The discontinuity across an $s$-channel cut is

$$
\operatorname{Disc}_sF(s)=F(s+i0)-F(s-i0).
$$

The symbol $i0$ is the infinitesimal version of the Feynman prescription. It is not decoration. It tells us from which side of a singularity the physical boundary value is approached.

A function is called real analytic in a region if

$$
F(s^*)=F(s)^*.
$$

When this condition holds near a real cut, the lower-edge value is the complex conjugate of the upper-edge value:

$$
F(s-i0)=F(s+i0)^*.
$$

Then

$$
\operatorname{Disc}_sF(s)=2i\operatorname{Im}F(s+i0).
$$

This relation is common, but it has assumptions. It can fail in regions where additional complex parameters, unstable-particle prescriptions, or nontrivial sheet choices are being used.

## Poles versus cuts

A simple pole has the local form

$$
F(s)\sim \frac{R}{s-m^2}.
$$

For a two-point function or scattering amplitude, a pole on the physical sheet below the lowest continuum threshold usually signals a stable one-particle state or bound state. The residue $R$ encodes the coupling of the operator or scattering channel to that state.

A branch point is different. Near a two-particle threshold, an amplitude often behaves schematically like

$$
F(s)\sim A+B\sqrt{s-s_{\rm th}}+\cdots,
$$

or like a logarithm, depending on dimension and observable. Going around $s_{\rm th}$ changes the value of the square root or logarithm. That is why a branch cut must be chosen to make a single-valued branch of the function.

The cut is a convention. The branch point is not. One may draw the cut from $s_{\rm th}$ to $+\infty$ along the real axis, but another path could be chosen. Physical amplitudes care about the boundary values and discontinuities, not about the artist's chosen line on the complex plane.

## Thresholds and phase space

The simplest physical branch point is a normal threshold. Suppose a channel with total momentum $P$ can produce particles with masses $m_1,\dots,m_n$. The threshold is

$$
P^2\ge \left(\sum_{a=1}^n m_a\right)^2.
$$

For two particles, the threshold is

$$
s_{\rm th}=(m_1+m_2)^2.
$$

The two-body phase-space factor contains

$$
\lambda^{1/2}(s,m_1^2,m_2^2),
$$

where

$$
\lambda(s,m_1^2,m_2^2)
=
\big(s-(m_1+m_2)^2\big)
\big(s-(m_1-m_2)^2\big).
$$

Near $s=(m_1+m_2)^2$, this behaves like

$$
\lambda^{1/2}(s,m_1^2,m_2^2)
\propto
\sqrt{s-(m_1+m_2)^2}.
$$

That square root is the local source of the branch point in many one-loop amplitudes. The physical interpretation is just phase space: below threshold, the intermediate state cannot be on shell; above threshold, it can.

## Example: the equal-mass bubble

For an equal-mass scalar bubble, the two-particle cut begins at

$$
s=4m^2.
$$

The cut phase-space factor contains

$$
\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2).
$$

Therefore the bubble discontinuity has the schematic form

$$
\operatorname{Disc}_s B(s)
\propto
 i\sqrt{1-\frac{4m^2}{s}}\,\theta(s-4m^2),
$$

with the proportionality constant and sign depending on the exact normalization of $B$. The important facts are independent of that normalization: the discontinuity vanishes below $4m^2$, turns on above $4m^2$, and has square-root branch behavior at threshold.

A massless bubble is even simpler analytically. Its finite part often contains a logarithm of the form

$$
\log\frac{-s-i0}{\mu^2}.
$$

For real $s>0$,

$$
\log(-s-i0)=\log s-i\pi,
\qquad
\log(-s+i0)=\log s+i\pi.
$$

Thus

$$
\operatorname{Disc}_s\log(-s-i0)=-2\pi i.
$$

This tiny identity is the seed of many larger discontinuity calculations.

## Discontinuities from unitarity

The optical theorem says that the imaginary part of a forward amplitude is a sum over physical intermediate states. More generally, unitarity relates discontinuities of amplitudes to products of lower-order amplitudes integrated over on-shell phase space.

For a channel carrying total momentum $P$, the schematic form is

$$
\operatorname{Disc}\mathcal M
\sim
 i\sum_X\int d\Pi_X\,
\mathcal M_L(i\to X)\mathcal M_R(f\to X)^*.
$$

The exact factor of $i$ and the sign depend on the convention for $\mathcal M$ and for the discontinuity. The invariant statement is that the jump across the cut is fixed by on-shell intermediate states.

This explains why discontinuities are easier than full amplitudes. A loop integral may be hard, but its discontinuity often collapses to phase space times simpler amplitudes.

## Spectral densities

In two-point functions, discontinuities are often packaged as spectral densities. For a scalar two-point function $G(p^2)$, one commonly defines

$$
\rho(s)=\frac{1}{2\pi i}\operatorname{Disc}_s G(s).
$$

When the correlator has a positive Hilbert-space spectral representation, $\rho(s)$ is nonnegative for suitable operators. The Källén–Lehmann representation is the canonical example:

$$
G(p^2)=\int_0^\infty ds\,\frac{i\rho(s)}{p^2-s+i0}.
$$

A stable particle appears as a delta function in $\rho(s)$. A multiparticle continuum appears as support over an interval. In the complex plane, the delta function produces a pole, while the continuum produces a branch cut.

This is one of the cleanest ways to remember the difference: a discrete state produces a pole, while a continuum of states produces a branch cut.

## Riemann sheets and resonances

A branch cut means the amplitude has multiple sheets. Crossing the cut analytically takes us from one sheet to another.

Stable particles and bound states can appear as poles on the physical sheet, usually below threshold. Unstable resonances usually appear as poles on an unphysical sheet reached by analytic continuation through a branch cut.

For a resonance near invariant mass $M$, the pole location often has the form

$$
s_{\rm pole}\approx M^2-iM\Gamma,
$$

where $\Gamma$ is the width. This is not usually a physical-sheet pole. On the real axis, the same physics appears as rapid phase variation and a Breit–Wigner-like peak.

This distinction is more than vocabulary. Treating a resonance pole as an ordinary stable-particle pole on the physical sheet leads to wrong analytic continuations and wrong unitarity statements.

## Normal and anomalous thresholds

Normal thresholds occur when ordinary intermediate particles in a channel go on shell. They are the thresholds most directly visible in phase space.

Feynman integrals can also have more subtle singularities. Landau's equations characterize possible singularities by asking whether internal propagators can go on shell and whether the loop-momentum integration contour is pinched. In a scalar graph with internal momenta $q_j$, the Landau conditions are schematically

$$
\alpha_j(q_j^2-m_j^2)=0,
$$

and for each independent loop,

$$
\sum_{j\in \text{loop}}\alpha_j q_j^\mu=0,
$$

with parameters $\alpha_j$ not all zero. Physical-region singularities require additional positivity and kinematic conditions.

An anomalous threshold is a singularity not equal to a simple lowest multiparticle threshold in the obvious channel. These occur when a more complicated on-shell configuration pinches the contour. They are not beginner folklore, but they matter in precision analytic continuation and multi-loop integral studies.

## Dispersion relations

Discontinuities are useful because analyticity lets us reconstruct functions from their jumps. Suppose $F(s)$ is analytic in the complex $s$ plane except for a cut beginning at $s_{\rm th}$, and suppose its growth at infinity is controlled. Then Cauchy's theorem gives a dispersion relation.

With enough subtractions, a typical form is

$$
F(s)=P_N(s)
+
\frac{s^N}{2\pi i}
\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}_{s'}F(s')}{(s')^N(s'-s)}.
$$

Equivalently, when real analyticity holds,

$$
F(s)=P_N(s)
+
\frac{s^N}{\pi}
\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{(s')^N(s'-s)}.
$$

The polynomial $P_N(s)$ contains subtraction constants. Physically, these are low-energy parameters not fixed by the discontinuity alone.

Dispersion relations are a bridge between local analytic data and global constraints. They underlie sum rules, positivity bounds, spectral representations, and many modern bootstrap arguments.

## Multiple variables and channel cuts

Real scattering amplitudes depend on several invariants. A $2\to2$ amplitude can be viewed as

$$
\mathcal M(s,t),
$$

with $u$ fixed by the masses and momentum conservation. The amplitude may have cuts in $s$, $t$, and $u$ channels.

An $s$-channel discontinuity is computed with $t$ fixed. A $t$-channel discontinuity is a different analytic operation. Crossing symmetry relates these regions, but it does not let us ignore which variable is being analytically continued.

This is a common source of mistakes. Saying “the amplitude has an imaginary part” is less precise than saying “the amplitude has an $s$-channel discontinuity across the physical cut beginning at $s_{\rm th}$.”

## Euclidean versus Lorentzian kinematics

Euclidean loop integrals are often real and smooth in regions where Lorentzian amplitudes have cuts. The cuts appear when we analytically continue external invariants to physical Lorentzian values.

This is why Euclidean calculations are so useful and also why they require care. A Euclidean correlator may define an analytic function, but physical rates depend on boundary values and discontinuities after continuation.

For response functions, the distinction between Euclidean, retarded, advanced, and Feynman correlators is essential. Different $i0$ prescriptions select different boundary values of related analytic functions.

## Common pitfalls

**Thinking the branch cut itself is physical.** Branch points and discontinuities carry invariant information. The drawn path of the cut is a convention used to pick a branch.

**Forgetting the side of the cut.** $F(s+i0)$ and $F(s-i0)$ are different boundary values. The physical Feynman amplitude chooses a side.

**Replacing every discontinuity by $2i\operatorname{Im}$ without checking real analyticity.** The relation is common but not automatic in every analytic continuation problem.

**Confusing poles and resonances.** A stable particle is a physical-sheet pole below threshold. A resonance is typically a pole on another sheet.

**Ignoring channel labels.** $s$-, $t$-, and $u$-channel discontinuities are different analytic operations.

**Assuming every branch point is a normal threshold.** Landau singularities include more subtle pinch configurations and anomalous thresholds.

**Treating Euclidean smoothness as Lorentzian smoothness.** Cuts appear after analytic continuation to physical kinematics.

## Relations to other pages

- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) gives the diagrammatic calculation of discontinuities.
- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) explains the forward unitarity relation behind physical discontinuities.
- [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) explains the contour-pinch conditions for possible Feynman-integral singularities.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) gives the simplest threshold branch cut explicitly.
- [Two-Body Phase Space](/perturbative-qft/phase-space-cross-sections-decays/two-body-phase-space/) derives the square-root threshold behavior that appears in discontinuities.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) relates different channel descriptions of the same analytic amplitude.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) develops the pole-plus-continuum picture for two-point functions.

## Research status

- **Established:** The relation between singularities, thresholds, discontinuities, and unitarity is a standard part of perturbative QFT and scattering theory.
- **Active:** Analytic structure remains central in modern amplitude bootstrap, positivity bounds, multi-loop integral bases, finite-density and thermal response, resonance physics, and nonperturbative S-matrix programs.
- **Subtle:** Full analytic structure in several complex variables, gauge theories with massless particles, unstable particles, confinement, cosmological observables, and nonperturbative amplitudes requires additional hypotheses beyond simple one-variable textbook pictures.

## Exercises

### Exercise 1: Discontinuity of a logarithm

For real $s>0$, compute

$$
\operatorname{Disc}_s\log(-s-i0).
$$

<details>
<summary><strong>Solution</strong></summary>

For $s>0$,

$$
-s-i0
$$

lies just below the negative real axis, while

$$
-s+i0
$$

lies just above it. With the standard branch of the logarithm,

$$
\log(-s-i0)=\log s-i\pi,
$$

and

$$
\log(-s+i0)=\log s+i\pi.
$$

Therefore

$$
\operatorname{Disc}_s\log(-s-i0)
=
(\log s-i\pi)-(\log s+i\pi)
=-2\pi i.
$$

</details>

### Exercise 2: Real analyticity and imaginary parts

Assume $F(s-i0)=F(s+i0)^*$ on a real cut. Show that

$$
\operatorname{Disc}_sF(s)=2i\operatorname{Im}F(s+i0).
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
\operatorname{Disc}_sF(s)=F(s+i0)-F(s-i0).
$$

Using the assumption,

$$
F(s-i0)=F(s+i0)^*.
$$

Thus

$$
\operatorname{Disc}_sF(s)
=F(s+i0)-F(s+i0)^*.
$$

For any complex number $z$,

$$
z-z^*=2i\operatorname{Im}z.
$$

Taking $z=F(s+i0)$ gives

$$
\operatorname{Disc}_sF(s)=2i\operatorname{Im}F(s+i0).
$$

</details>

### Exercise 3: Square-root threshold behavior

Show that near the two-particle threshold $s_{\rm th}=(m_1+m_2)^2$,

$$
\lambda^{1/2}(s,m_1^2,m_2^2)
$$

is proportional to $\sqrt{s-s_{\rm th}}$.

<details>
<summary><strong>Solution</strong></summary>

The Källén function factorizes as

$$
\lambda(s,m_1^2,m_2^2)
=
\big(s-(m_1+m_2)^2\big)
\big(s-(m_1-m_2)^2\big).
$$

Let

$$
s_{\rm th}=(m_1+m_2)^2.
$$

Near threshold, write $s=s_{\rm th}+\varepsilon$. Then

$$
\lambda(s,m_1^2,m_2^2)
=\varepsilon\left[s_{\rm th}-(m_1-m_2)^2+O(\varepsilon)\right].
$$

But

$$
s_{\rm th}-(m_1-m_2)^2=(m_1+m_2)^2-(m_1-m_2)^2=4m_1m_2.
$$

Thus, for nonzero masses,

$$
\lambda(s,m_1^2,m_2^2)=4m_1m_2\varepsilon+O(\varepsilon^2),
$$

and

$$
\lambda^{1/2}(s,m_1^2,m_2^2)
\propto \sqrt{s-s_{\rm th}}.
$$

</details>

### Exercise 4: A once-subtracted dispersion relation

Suppose $F(s)$ is analytic except for a cut from $s_{\rm th}$ to $\infty$ and grows too fast for an unsubtracted dispersion relation but slowly enough after one subtraction. Write a once-subtracted dispersion relation at $s=0$.

<details>
<summary><strong>Solution</strong></summary>

A once-subtracted dispersion relation has the form

$$
F(s)=F(0)+\frac{s}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}_{s'}F(s')}{s'(s'-s)}.
$$

If real analyticity holds, then

$$
\operatorname{Disc}_{s'}F(s')=2i\operatorname{Im}F(s'+i0),
$$

so the same relation becomes

$$
F(s)=F(0)+\frac{s}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{s'(s'-s)}.
$$

The subtraction constant $F(0)$ is not fixed by the discontinuity.

</details>

### Exercise 5: Pole or cut?

Explain why a stable one-particle state gives a pole in a two-point function, while a two-particle continuum gives a branch cut.

<details>
<summary><strong>Solution</strong></summary>

In a spectral representation, a stable one-particle state contributes a delta function to the spectral density,

$$
\rho(s)\supset Z\delta(s-m^2).
$$

Inserted into

$$
G(p^2)=\int_0^\infty ds\,\frac{i\rho(s)}{p^2-s+i0},
$$

this gives

$$
G(p^2)\supset \frac{iZ}{p^2-m^2+i0},
$$

which is a pole.

A two-particle continuum contributes spectral weight over an interval, beginning at threshold. The integral over a continuous range of $s$ produces a function with a branch cut along that interval. Thus discrete spectral support gives poles, while continuous spectral support gives cuts.

</details>

## References

- L. D. Landau, “On analytic properties of vertex parts in quantum field theory,” *Nuclear Physics* **13** (1959), for the Landau equations and singularity analysis.
- R. E. Cutkosky, “Singularities and discontinuities of Feynman amplitudes,” *Journal of Mathematical Physics* **1** (1960), for cutting rules.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for classic analytic S-matrix structure.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for unitarity, analyticity, scattering theory, and resonances.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for optical theorem, spectral decomposition, polology, and analytic structure.
- M. Srednicki, *Quantum Field Theory*, §§13 and 20, for spectral representation and loop-level branch cuts.

## Version history

- **2026-06-13:** Initial QFT.org page. Added definitions of discontinuities, threshold and phase-space branch behavior, logarithmic example, spectral-density interpretation, Riemann-sheet and resonance discussion, Landau-equation preview, dispersion-relation form, and solved exercises.
