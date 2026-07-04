---
title: "Dispersion Relations"
description: "How analyticity reconstructs amplitudes and correlators from their discontinuities, poles, and subtraction constants."
sidebar:
  label: "Dispersion Relations"
  order: 4
level: Graduate
status: "Polished draft"
source: "Eden et al.; Weinberg Vol. I ch. 3; Coleman ch. 12; Srednicki §§13, 20, and 25; Schwartz ch. 24"
topics:
  - dispersion relations
  - analyticity
  - discontinuities
  - spectral representations
  - unitarity
  - subtraction constants
canonicalTopics:
  - dispersion-relations
  - analytic-s-matrix
  - spectral-reconstruction
  - cauchy-representation
researchStatus:
  established:
    - "Dispersion relations are standard consequences of complex analyticity, unitarity, and suitable high-energy boundedness assumptions."
  active:
    - "Modern uses include positivity bounds, amplitude bootstrap methods, precision hadron physics, causal response theory, and careful treatments of massless thresholds and subtractions."
---

## Summary

A **dispersion relation** reconstructs an analytic amplitude or correlator from its singularity data. The basic idea is Cauchy's theorem: if a function is analytic away from cuts and poles, then its value at one point can be written as a contour integral around the singularities.

For a one-variable amplitude $F(s)$ with a right-hand cut beginning at $s_{\rm th}$ and no relevant pole terms, the simplest unsubtracted form is

$$
F(s)=\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{s'-s}
=\frac{1}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{s'-s},
$$

where the second equality assumes real analyticity on the cut. This formula should be read with care: it requires suitable falloff at infinity and must be supplemented by pole terms, left-hand cuts, or subtractions when those are present.

Dispersion relations are the analytic partner of unitarity. The optical theorem and Cutkosky rules tell us what the discontinuity is; dispersion relations tell us how that discontinuity constrains the full analytic function.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 54rem;">

![A dispersion contour reconstructs a function from its cuts and poles](/figures/perturbative-qft/dispersion-relations.svg)

<figcaption>

A dispersion relation starts from a Cauchy contour around the point $s$ and deforms it onto the singularities: right-hand cuts, left-hand cuts, isolated poles, and sometimes an arc at infinity. If the arc does not vanish, subtractions are needed.

</figcaption>
</figure>

A useful slogan is:

$$
\text{analyticity} + \text{unitarity} + \text{boundedness}
\quad\Longrightarrow\quad
\text{amplitude from discontinuities plus constants}.
$$

The “plus constants” is not an embarrassment. Subtraction constants are often precisely the low-energy parameters, counterterms, polarizabilities, or effective-field-theory coefficients that the analytic relation is designed to constrain.

## Prerequisites

You should know [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/), [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/), and [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/). For scattering applications, review [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/).

For spectral representations, it also helps to know [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) and [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/).

## Core idea

A local, causal, unitary QFT does not produce arbitrary functions of momenta. Its amplitudes have analytic structure. Poles represent isolated one-particle or bound-state contributions. Branch cuts represent multi-particle continua. The discontinuity across a physical cut is fixed by the same intermediate states that appear in the optical theorem.

Dispersion relations use this structure in reverse. Suppose we know where the singularities are and know the discontinuity along the cuts. Then Cauchy's theorem expresses the amplitude elsewhere in terms of those singularities. In practice this turns measured cross sections, spectral densities, or lower-order amplitudes into constraints on amplitudes and effective couplings.

The conceptual chain is:

$$
\text{causality and spectrum}
\quad\Longrightarrow\quad
\text{analyticity},
$$

$$
\text{unitarity}
\quad\Longrightarrow\quad
\text{positive or computable discontinuities},
$$

$$
\text{Cauchy's theorem}
\quad\Longrightarrow\quad
\text{dispersion relation}.
$$

That chain has hypotheses at every arrow. The most common mistakes with dispersion relations come from forgetting one of them.

## Setup and conventions

We study a function $F(s)$ of one complex variable. In a scattering problem, $s$ is usually a Mandelstam invariant and other invariants, such as $t$, are held fixed. This is the setting of fixed-$t$ dispersion relations.

The discontinuity across a cut is

$$
\operatorname{Disc}F(s)=F(s+i0)-F(s-i0).
$$

When $F$ is real analytic near a real cut,

$$
F(s-i0)=F(s+i0)^*,
$$

so

$$
\operatorname{Disc}F(s)=2i\operatorname{Im}F(s+i0).
$$

The phrase “right-hand cut” usually means a physical $s$-channel cut extending from a threshold to $+\infty$. A “left-hand cut” usually comes from crossed-channel physics and may extend to $-\infty$ in the $s$ plane at fixed $t$. The exact endpoint depends on masses and on which variable is held fixed.

## Cauchy's formula and contour deformation

Let $F(z)$ be analytic inside a contour $C$ except for the point $z=s$ and the singularities we will later deform around. Cauchy's formula gives

$$
F(s)=\frac{1}{2\pi i}\oint_C dz\,\frac{F(z)}{z-s}.
$$

Now enlarge and deform the contour. If the large circle at infinity gives no contribution, the contour can be collapsed onto cuts and small circles around isolated poles. For a single right-hand cut, this gives

$$
F(s)=\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{F(s'+i0)-F(s'-i0)}{s'-s}
+\sum_a \frac{R_a}{m_a^2-s}.
$$

The pole term is schematic. If $F$ has an isolated pole at $s=m_a^2$ with local behavior

$$
F(s)\sim \frac{R_a}{m_a^2-s},
$$

then the dispersion representation must include that pole unless it is already included as a delta-function contribution to a spectral density. Which convention is cleaner depends on the problem.

When real analyticity applies on the cut, the same relation becomes

$$
F(s)=\frac{1}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{s'-s}
+\text{pole terms}.
$$

This is the most familiar form. It is also the easiest one to misuse, because it hides the assumptions about the contour at infinity.

## Subtractions

If $F(z)$ does not fall fast enough as $|z|\to\infty$, the large circle does not vanish. Instead of trying to ignore it, subtract the value of the function at a reference point $s_0$.

Apply the unsubtracted relation to

$$
\frac{F(s)-F(s_0)}{s-s_0}.
$$

The result is the once-subtracted dispersion relation

$$
F(s)=F(s_0)
+\frac{s-s_0}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{(s'-s)(s'-s_0)}
+\text{pole terms}.
$$

With real analyticity,

$$
F(s)=F(s_0)
+\frac{s-s_0}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}F(s'+i0)}{(s'-s)(s'-s_0)}
+\text{pole terms}.
$$

After $N$ subtractions, the general structure is

$$
F(s)=P_{N-1}(s)
+\frac{(s-s_0)^N}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{(s'-s)(s'-s_0)^N}
+\text{pole terms},
$$

where $P_{N-1}$ is a polynomial of degree at most $N-1$ fixed by the subtraction constants.

Subtractions improve convergence at high energy. They also cost information: each subtraction introduces a constant that must be fixed by measurement, matching, symmetry, or another physical input.

:::note[Subtractions are not optional decoration]
A dispersion relation with too few subtractions may simply be false. A relation with more subtractions is safer at high energy, but less predictive because it contains more constants.
:::

## Right-hand and left-hand cuts

For a two-to-two amplitude $\mathcal M(s,t)$ at fixed $t$, the analytic structure in $s$ usually contains more than the direct physical $s$-channel cut. Crossed-channel physics appears as left-hand cuts.

A schematic fixed-$t$ relation has the form

$$
\mathcal M(s,t)=P(s,t)
+\frac{1}{\pi}\int_{s_{\rm R}}^\infty ds'\,
\frac{\operatorname{Im}_s\mathcal M(s'+i0,t)}{s'-s}
+\frac{1}{\pi}\int_{-\infty}^{s_{\rm L}} ds'\,
\frac{\operatorname{Im}_s\mathcal M(s'+i0,t)}{s'-s},
$$

with subtractions inserted as needed. The right-hand cut is associated with the direct $s$ channel. The left-hand cut is often the analytic image of $t$- or $u$-channel intermediate states.

This is why dispersion theory and crossing symmetry are inseparable. If one writes only the right-hand cut when a left-hand cut is present, one has not written the full amplitude; one has written a partial reconstruction.

## Spectral representations as dispersion relations

The Källén–Lehmann representation is a dispersion relation for a two-point function. For a scalar operator $\mathcal O$, the momentum-space two-point function has the form

$$
G(q^2)=\int_0^\infty d\mu^2\,
\frac{\rho(\mu^2)}{\mu^2-q^2-i0}
+\text{subtractions},
$$

where the spectral density $\rho(\mu^2)$ is nonnegative in a unitary theory for suitable Hermitian operators.

The discontinuity across the physical cut is

$$
\operatorname{Disc}G(q^2)=2\pi i\rho(q^2)
$$

up to the sign convention used for the denominator. Thus the spectral density is the discontinuity of the two-point function. This is the same analytic logic as for scattering amplitudes, but with a simpler kinematic variable.

In perturbation theory, loop diagrams produce spectral densities through Cutkosky cuts. In nonperturbative QFT, the same representation follows from inserting a complete set of physical states.

## Forward dispersion relations and the optical theorem

The forward elastic amplitude is especially important. For two particles with total invariant mass $s$ and momentum-transfer $t=0$, the optical theorem relates its imaginary part to the total cross section.

With the scattering conventions used in this volume, for $1+2\to1+2$ elastic forward scattering,

$$
\sigma_{\rm tot}(s)=\frac{\operatorname{Im}\mathcal M(s,0)}{\lambda^{1/2}(s,m_1^2,m_2^2)},
$$

where

$$
\lambda(s,m_1^2,m_2^2)
=\big(s-(m_1+m_2)^2\big)\big(s-(m_1-m_2)^2\big).
$$

A forward dispersion relation therefore turns an integral over total cross sections into a statement about the real part or derivatives of the forward amplitude. This is the logic behind many sum rules.

For massless theories or theories with long-range forces, the forward limit can be subtle. Infrared divergences, collinear singularities, and $t$-channel massless exchanges may require inclusive observables, regulators, or modified subtractions.

## Positivity from dispersion relations

When the imaginary part of an amplitude is positive by the optical theorem, dispersion relations can imply positivity constraints on low-energy coefficients.

The cleanest schematic example is a crossing-even forward amplitude after enough subtractions. Expanding around a point $s_0$ in an analytic low-energy region, one finds terms of the form

$$
\left.\frac{d^2\mathcal M}{ds^2}\right|_{s=s_0}
\sim
\frac{2}{\pi}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Im}\mathcal M(s',0)}{(s'-s_0)^3}
+\text{crossed-channel contribution}.
$$

If the crossed-channel contribution has the same sign by crossing and the denominator is positive in the chosen region, unitarity gives a positive result. In an effective field theory, this derivative is a linear combination of Wilson coefficients.

This is the basic origin of many positivity bounds. The details are not automatic: mass gaps, crossing properties, high-energy growth, subtractions, spin, identical-particle symmetries, and infrared behavior all matter.

## Worked example: a logarithmic cut

Consider

$$
F(s)=\log(m^2-s-i0).
$$

This function has a branch cut for $s>m^2$. For $s>m^2$,

$$
m^2-s-i0=-(s-m^2)-i0,
$$

so on the principal branch

$$
F(s+i0)=\log(s-m^2)-i\pi,
\qquad
F(s-i0)=\log(s-m^2)+i\pi.
$$

Therefore

$$
\operatorname{Disc}F(s)=-2\pi i,
\qquad s>m^2.
$$

The logarithm itself does not vanish at infinity, so an unsubtracted dispersion relation for $F$ is not justified. But its derivative

$$
F'(s)=-\frac{1}{m^2-s-i0}
$$

falls as $1/s$, and its discontinuity is the derivative of the discontinuity in the distributional sense. This tiny example captures the general moral: analytic structure alone is not enough; high-energy behavior determines how many subtractions are needed.

## Common pitfalls

**Assuming every analytic function has an unsubtracted dispersion relation.** The arc at infinity must vanish. If it does not, use subtractions.

**Forgetting pole terms.** Bound states and stable particles may appear as isolated poles in addition to continuum cuts.

**Dropping left-hand cuts.** In scattering amplitudes, crossed-channel physics often contributes left-hand cuts in a fixed-$t$ representation.

**Confusing the cut with the physics.** The path of a branch cut is a convention. The branch point, discontinuity, monodromy, and sheet structure are physical analytic data.

**Using positivity outside its assumptions.** Positivity bounds require more than writing a dispersion integral. They require control over crossing, subtractions, analyticity domains, and infrared behavior.

**Ignoring massless exchanges.** A massless $t$-channel pole or long-range force can spoil naive forward-limit arguments.

## Relations to other pages

- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) defines the discontinuities used here.
- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) computes discontinuities diagrammatically.
- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) relates forward discontinuities to total rates.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains why left-hand cuts arise from crossed channels.
- [Källén–Lehmann spectral representations](/foundations/correlators-and-propagators/spectral-representation/) are two-point-function dispersion relations.

## Research status

- **Established:** Dispersion relations are standard consequences of complex analysis once analyticity domains, singularities, and high-energy behavior are specified.
- **Active:** Determining the sharpest assumptions for amplitude positivity, massless theories, gravitational amplitudes, non-forward dispersion relations, and multi-variable analyticity remains an active research area.
- **Convention-dependent:** Overall signs in discontinuities depend on whether one writes denominators as $s'-s-i0$ or $s-s'+i0$, and whether the object is a correlator, $i\mathcal M$, or $\mathcal M$.

## Exercises

### Exercise 1: Unsubtracted relation from Cauchy's theorem

Assume $F(z)$ is analytic in the complex plane except for a cut along $[s_{\rm th},\infty)$ and that $F(z)/z\to0$ on the large circle. Derive

$$
F(s)=\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{s'-s}.
$$

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
F(s)=\frac{1}{2\pi i}\oint_C dz\,\frac{F(z)}{z-s}.
$$

Deform $C$ to a contour running just above and below the cut plus a large circle. The large-circle contribution vanishes by assumption. The upper edge contributes

$$
\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,\frac{F(s'+i0)}{s'-s}.
$$

The lower edge is traversed in the opposite direction, giving

$$
-\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,\frac{F(s'-i0)}{s'-s}.
$$

Adding the two terms gives the stated relation.

</details>

### Exercise 2: Derive the once-subtracted relation

Let $s_0$ lie away from the cut. Apply the unsubtracted relation to

$$
G(s)=\frac{F(s)-F(s_0)}{s-s_0}
$$

to derive the once-subtracted dispersion relation.

<details>
<summary><strong>Solution</strong></summary>

The function $G$ has discontinuity

$$
\operatorname{Disc}G(s')=
\frac{\operatorname{Disc}F(s')}{s'-s_0}.
$$

The unsubtracted relation for $G$ is

$$
G(s)=\frac{1}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{(s'-s)(s'-s_0)}.
$$

Multiplying by $s-s_0$ and adding $F(s_0)$ gives

$$
F(s)=F(s_0)
+\frac{s-s_0}{2\pi i}\int_{s_{\rm th}}^\infty ds'\,
\frac{\operatorname{Disc}F(s')}{(s'-s)(s'-s_0)}.
$$

</details>

### Exercise 3: Discontinuity of a logarithm

For

$$
F(s)=\log(m^2-s-i0),
$$

compute $\operatorname{Disc}F(s)$ for $s>m^2$ on the principal branch.

<details>
<summary><strong>Solution</strong></summary>

For $s>m^2$,

$$
m^2-s-i0=-(s-m^2)-i0,
$$

so

$$
F(s+i0)=\log(s-m^2)-i\pi.
$$

The lower-edge value is

$$
F(s-i0)=\log(s-m^2)+i\pi.
$$

Therefore

$$
\operatorname{Disc}F(s)=F(s+i0)-F(s-i0)=-2\pi i.
$$

The sign would flip if one instead chose $\log(s-m^2+i0)$ as the basic function.

</details>

### Exercise 4: Optical theorem input

Using

$$
2\operatorname{Im}\mathcal M_{i\to i}
=\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}|^2,
$$

and the two-particle initial flux factor $4F$ with

$$
F=\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2},
$$

show that

$$
\sigma_{\rm tot}(s)=
\frac{\operatorname{Im}\mathcal M(s,0)}{\lambda^{1/2}(s,m_1^2,m_2^2)}.
$$

<details>
<summary><strong>Solution</strong></summary>

The total cross section is

$$
\sigma_{\rm tot}=\frac{1}{4F}
\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}|^2.
$$

Using the optical theorem gives

$$
\sigma_{\rm tot}=\frac{1}{4F}\,2\operatorname{Im}\mathcal M(s,0)
=\frac{\operatorname{Im}\mathcal M(s,0)}{2F}.
$$

For two incoming particles,

$$
\lambda(s,m_1^2,m_2^2)=4F^2.
$$

Thus $2F=\lambda^{1/2}(s,m_1^2,m_2^2)$, giving the desired formula.

</details>

## References

- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix treatment.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3, for scattering theory, unitarity, partial waves, and analytic constraints.
- S. Coleman, *Lectures on Quantum Field Theory*, especially the scattering and optical-theorem lectures, for a clear physics-first route into unitarity.
- M. Srednicki, *Quantum Field Theory*, §§13, 20, and 25, for spectral representations, one-loop scattering, and unstable-particle analytic structure.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 24, for implications of unitarity, optical-theorem logic, and analytic structure.
- T. N. Pham and T. N. Truong, and later EFT positivity literature, for examples of dispersion relations constraining low-energy coefficients.

## Version history

- **2026-06-13:** Initial QFT.org page for dispersion relations in the Perturbative QFT and Scattering volume.
