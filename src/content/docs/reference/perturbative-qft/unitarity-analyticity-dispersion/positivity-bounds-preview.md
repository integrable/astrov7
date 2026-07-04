---
title: "Positivity Bounds Preview"
description: "A first look at how analyticity, unitarity, crossing, and dispersion relations constrain low-energy EFT coefficients."
sidebar:
  label: "Positivity Bounds Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Adams et al. 2006; standard S-matrix analyticity and dispersion-relation texts; modern EFT positivity-bound reviews."
topics:
  - positivity bounds
  - dispersion relations
  - effective field theory
  - analyticity
  - unitarity
canonicalTopics:
  - positivity-bounds
  - forward-limit-dispersion-relations
  - eft-wilson-coefficient-constraints
  - s-matrix-consistency
researchStatus:
  established:
    - "Forward-limit positivity bounds for gapped, Lorentz-invariant, unitary, analytic, crossing-symmetric theories are standard consequences of dispersion relations and the optical theorem."
  active:
    - "Modern positivity bounds include nonforward bounds, spinning particles, massless limits, gravity subtleties, loops, finite-energy improvements, curved backgrounds, and numerical bootstrap-style implementations."
---

## Summary

**Positivity bounds** are constraints on low-energy effective field theory coefficients that follow from high-level consistency of the ultraviolet theory. The basic logic is:

$$
\text{analyticity}
+\text{unitarity}
+\text{crossing}
+\text{polynomial boundedness}
\quad\Longrightarrow\quad
\text{positive dispersion integrals}.
$$

For a simple gapped theory of identical massive scalars, the forward elastic amplitude can be written as a crossing-even function of

$$
\nu=s-2m^2,
\qquad t=0,
\qquad u=4m^2-s.
$$

Under suitable assumptions and after subtracting possible poles, a twice-subtracted forward dispersion relation gives a schematic result of the form

$$
\left.\frac{d^2\mathcal M(\nu,0)}{d\nu^2}\right|_{\nu=0}
=\frac{4}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\,\operatorname{Im}\mathcal M(\nu',0)>0.
$$

The right-hand side is positive because the optical theorem relates $\operatorname{Im}\mathcal M(s,0)$ to a total cross section. Therefore the coefficient of the corresponding low-energy $\nu^2$ term must be positive.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![Logic of a forward-limit positivity bound](/figures/perturbative-qft/positivity-bounds-preview.svg)

<figcaption>

A forward-limit positivity bound turns ultraviolet consistency assumptions into an infrared constraint. Analyticity gives a contour relation, unitarity makes the discontinuity positive, crossing pairs the two cuts, and the low-energy expansion reads off signs of EFT coefficients.

</figcaption>
</figure>

This page is a preview, not a full treatment. Its job is to explain the cleanest scalar forward-limit argument and the assumptions behind it. The most important lesson is not that every coefficient is positive. The lesson is sharper: **some low-energy coefficients are weighted averages of positive total cross sections, provided the amplitude satisfies the required analyticity and high-energy assumptions.**

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/), [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/), [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/), [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/), and [Threshold Behavior](/perturbative-qft/unitarity-analyticity-dispersion/threshold-behavior/).

For the EFT interpretation, review the pages on renormalized amplitudes and the broader Renormalization, RG, and EFT volume when using these bounds beyond the simplest scalar example.

## Core idea

A low-energy EFT amplitude has an expansion in powers of momenta:

$$
\mathcal M_{\mathrm{EFT}}(s,t)
=\mathcal M_{\mathrm{light}}(s,t)
+\sum_i c_i\,\mathcal O_i(s,t).
$$

The coefficients $c_i$ summarize short-distance physics that has been integrated out. Positivity bounds ask whether an arbitrary choice of $c_i$ could come from a standard ultraviolet completion.

The answer is no. Under the assumptions of Lorentz invariance, unitarity, causality/analyticity, crossing symmetry, a mass gap, and suitable high-energy boundedness, some combinations of the $c_i$ are not free. They must be positive, or must lie inside a convex allowed region.

The simplest bound is a forward-limit bound. It says that a coefficient in the low-energy expansion is equal to a positive integral over the imaginary part of the forward amplitude. By the optical theorem, that imaginary part is proportional to a total cross section.

The slogan is:

$$
\text{low-energy Wilson coefficient}
=\text{weighted integral over physical cross sections}.
$$

When the weight is positive, the coefficient has a sign.

## Setup and conventions

We use qft.org scattering conventions. Consider elastic scattering of identical scalar particles of mass $m$,

$$
\phi\phi\to\phi\phi,
$$

with amplitude

$$
\mathcal M(s,t).
$$

The Mandelstam variables obey

$$
s+t+u=4m^2.
$$

In the forward limit,

$$
t=0,
\qquad
\nu=s-2m^2,
\qquad
\nu=0\text{ at the crossing-symmetric point}.
$$

Crossing symmetry for identical scalars implies

$$
\mathcal M(\nu,0)=\mathcal M(-\nu,0),
$$

up to the usual caveats about analytic continuation and possible pole subtractions.

The physical $s$-channel cut begins at

$$
s=4m^2,
\qquad
\nu=2m^2.
$$

By crossing, there is a corresponding $u$-channel cut beginning at

$$
\nu=-2m^2.
$$

For the cleanest argument, assume no massless exchange and no singularity at $t=0$. If there are known light poles, subtract them before applying the positivity argument to the remaining analytic part.

## Forward dispersion relation

Let

$$
F(\nu)=\mathcal M(\nu,0)
$$

after subtracting possible pole terms. Suppose $F(\nu)$ is analytic in the complex $\nu$ plane except for the right- and left-hand cuts, and suppose it is sufficiently bounded at large $|\nu|$ that a twice-subtracted dispersion relation exists.

Because $F$ is crossing-even,

$$
F(\nu)=F(-\nu).
$$

A convenient schematic form of the twice-subtracted dispersion relation is

$$
F(\nu)=F(0)
+\frac{2\nu^2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'}
\frac{\operatorname{Im}F(\nu')}{\nu'^2-\nu^2},
$$

where

$$
\nu_{\mathrm{th}}=2m^2
$$

for identical scalar scattering. This expression is Cauchy's theorem applied to a function with cuts, with crossing used to combine the two sides.

Expanding around $\nu=0$ gives

$$
F(\nu)=F(0)
+\frac{2\nu^2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu')
+O(\nu^4).
$$

Therefore

$$
F''(0)=\frac{4}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu').
$$

The sign of $F''(0)$ is now controlled by the sign of the imaginary part on the physical cut.

## Positivity from the optical theorem

For forward elastic scattering, the optical theorem relates the imaginary part of the amplitude to the total cross section:

$$
\operatorname{Im}\mathcal M(s,0)
\propto
\text{positive flux factor}\times \sigma_{\mathrm{tot}}(s).
$$

Since

$$
\sigma_{\mathrm{tot}}(s)\ge0,
$$

we have

$$
\operatorname{Im}\mathcal M(s,0)\ge0
$$

on the physical cut, with the conventional positive normalization. Hence

$$
F''(0)>0
$$

unless the relevant total cross section vanishes identically.

This is the simplest positivity bound. It is not a perturbative loop statement. It is a nonperturbative consequence of the analytic S-matrix assumptions used to write the dispersion relation and of the probabilistic interpretation of the cross section.

## EFT interpretation

Suppose the low-energy amplitude near $\nu=0$ has the expansion

$$
F_{\mathrm{EFT}}(\nu)=a_0+a_2\nu^2+a_4\nu^4+\cdots.
$$

Then

$$
a_2=\frac12F''(0).
$$

The forward positivity argument gives

$$
a_2>0.
$$

If the EFT comes from integrating out a heavy particle of mass $M$, one often expects

$$
a_2\sim \frac{c}{M^4}.
$$

The positivity bound then says that the coefficient $c$ of the corresponding four-derivative interaction must have the sign compatible with a positive spectral integral.

A standard scalar EFT example is

$$
\mathcal L_{\mathrm{EFT}}
=\frac12(\partial\phi)^2-\frac12m^2\phi^2
+\frac{c}{\Lambda^4}(\partial_\mu\phi\partial^\mu\phi)^2+\cdots.
$$

At high energies compared with $m$ but below $\Lambda$, the contact interaction contributes schematically

$$
\mathcal M(s,t,u)\supset
\frac{c}{\Lambda^4}\left(s^2+t^2+u^2\right)
$$

up to convention-dependent numerical factors. In the forward crossing-even expansion, the coefficient of $\nu^2$ is proportional to $c/\Lambda^4$. The simple positivity argument therefore implies

$$
c>0
$$

with the chosen normalization, once lower-energy pole contributions have been handled appropriately.

## Why subtractions appear

A dispersion relation follows by integrating around a large contour in the complex plane. If the amplitude vanishes fast enough at infinity, no subtraction is needed. Real amplitudes are usually not that polite.

If $F(\nu)$ grows with energy, one subtracts values or derivatives at a reference point so that the contour integral at infinity vanishes. A twice-subtracted relation is common for forward amplitudes because general boundedness assumptions allow some high-energy growth.

Subtractions have two important consequences.

First, they determine which low-energy coefficients are constrained. A twice-subtracted relation does not fix $F(0)$ by a positive integral. It constrains $F''(0)$ and higher even derivatives.

Second, they make the assumptions visible. Positivity bounds are not simply algebraic statements about EFT Lagrangians. They depend on how the amplitude behaves at high energy.

The Froissart-Martin type intuition is that in a gapped local theory the forward amplitude cannot grow arbitrarily fast. The exact rigorous assumptions are subtle, especially for massless particles and gravity.

## Pole subtractions and light exchange

The cleanest positivity bound assumes that the amplitude is analytic around the crossing-symmetric point after removing the cuts. But light particles can create poles.

For example, if a scalar exchange produces

$$
\mathcal M(s,t)\supset \frac{g^2}{m_\chi^2-s},
$$

then this pole must be treated explicitly. One does not apply the positivity argument to an amplitude with an unaccounted pole inside the contour.

The usual workflow is:

1. identify light degrees of freedom kept in the EFT;
2. subtract their pole contributions from the amplitude;
3. apply the dispersion argument to the remaining analytic heavy contribution;
4. interpret the result as a constraint on Wilson coefficients of local operators.

This is especially important in theories with photons, gluons, gravitons, Goldstone bosons, or light mediators. Otherwise one mistakes known low-energy physics for a violation of positivity.

## Beyond the forward scalar bound

The forward scalar bound is only the entrance. Modern positivity bounds go further in several directions.

| Extension | What changes |
|---|---|
| Nonforward bounds | Keep $t\ne0$ and constrain more EFT structures. |
| Spinning particles | Use polarization states and matrix positivity. |
| Multiple species | Positivity becomes positivity of matrices or convex cones. |
| Loops in EFT | Separate calculable infrared loop effects from Wilson coefficients. |
| Massless particles | Handle soft, collinear, or long-range singularities. |
| Gravity | Forward limit has graviton exchange singularities and weaker boundedness. |
| Improved bounds | Use finite-energy data or known low-energy absorptive parts. |

This page does not derive those refinements. But the conceptual spine remains the same: a low-energy coefficient is related to an integral over discontinuities, and unitarity controls the sign of the absorptive part.

## Physical meaning

A positivity bound is a consistency test. If an EFT coefficient violates a valid positivity bound, then at least one assumption behind the bound must fail.

Possible failures include:

- the theory is not unitary;
- the theory is not Lorentz invariant;
- the amplitude is not analytic in the assumed domain;
- crossing is not applicable in the assumed form;
- the theory has massless long-range exchange that was not subtracted;
- the high-energy growth invalidates the chosen dispersion relation;
- the proposed EFT expansion is being used outside its domain.

This is why positivity bounds are powerful in EFT. They do not require knowing the ultraviolet completion in detail. They use general properties expected of a standard local quantum theory to carve out allowed regions in low-energy parameter space.

The phrase "UV completion" should not be treated as decoration here. Positivity bounds are statements about which EFTs can arise from a consistent ultraviolet theory satisfying the stated assumptions.

## A minimal derivation

Here is the forward-limit derivation in compressed form.

Start with a crossing-even forward amplitude

$$
F(\nu)=F(-\nu),
$$

analytic in the complex $\nu$ plane away from cuts beginning at $\pm\nu_{\mathrm{th}}$. Apply Cauchy's theorem to a suitable twice-subtracted kernel. Deforming the contour onto the cuts gives

$$
F(\nu)-F(0)
=\frac{2\nu^2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'}
\frac{\operatorname{Im}F(\nu')}{\nu'^2-\nu^2}.
$$

For small $\nu$,

$$
\frac{1}{\nu'^2-\nu^2}
=\frac{1}{\nu'^2}
\left(1+\frac{\nu^2}{\nu'^2}+\cdots\right).
$$

Therefore the $\nu^2$ coefficient is

$$
\frac{2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu'),
$$

and the second derivative is positive if the absorptive part is positive.

That is the mathematical engine behind the simplest positivity bound.

## Common pitfalls

**Using positivity without checking the assumptions.** The clean forward bound assumes a mass gap, analyticity, crossing, unitarity, and suitable high-energy boundedness. It is not a sign rule for arbitrary Lagrangians.

**Forgetting pole subtractions.** Known light exchanges must be subtracted before interpreting the remaining analytic part as local Wilson coefficients.

**Applying massive bounds directly to photons or gravitons.** Massless exchange creates forward singularities and infrared subtleties. The simple scalar argument does not transfer without modification.

**Confusing the sign of a Lagrangian coefficient with the sign of an amplitude coefficient.** Different operator bases and integration-by-parts identities can hide the relevant positive combination. Positivity constrains invariant amplitude coefficients, not arbitrary-looking terms in a redundant basis.

**Ignoring loops in the EFT.** Low-energy loops produce known nonanalytic terms and absorptive parts. Bounds on Wilson coefficients require separating these calculable infrared contributions from local short-distance coefficients.

**Treating a preview as the full modern subject.** Current positivity methods include matrix bounds, nonforward bounds, spinning amplitudes, finite-energy improvements, numerical optimization, and special gravity treatments.

## Relations to other pages

- [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/) derives the contour logic used here.
- [Optical Theorem](/perturbative-qft/unitarity-analyticity-dispersion/optical-theorem/) explains why the absorptive part of a forward amplitude is positive.
- [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) gives a complementary channel-by-channel form of unitarity.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) explains how cuts and imaginary parts enter amplitudes.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains why the left- and right-hand cuts are related.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how physical amplitudes are made finite before one studies their analytic properties.
- The Renormalization, RG, and EFT volume is the natural home for full EFT operator-basis and matching applications.
- The Research Frontiers volume is the natural home for modern open problems involving gravitational positivity, non-Lorentzian systems, and numerical S-matrix bootstrap.

## Research status

- **Established:** The scalar forward-limit positivity bound in a gapped, Lorentz-invariant, unitary, analytic, crossing-symmetric theory is a standard dispersion-relation consequence of the optical theorem.
- **Active:** Positivity bounds with spin, massless particles, gravity, loops, nonforward kinematics, curved backgrounds, finite-energy information, and numerical optimization remain active research areas.
- **Speculative:** The basic positivity logic is not speculative. Some proposed extensions to quantum gravity, cosmology, and nonstandard UV behavior depend on assumptions whose status is still debated.

## Exercises

### Exercise 1: Crossing-even expansion

Let $F(\nu)=F(-\nu)$ be analytic near $\nu=0$. Show that its Taylor expansion contains only even powers of $\nu$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
F(\nu)=\sum_{n=0}^\infty a_n\nu^n.
$$

Crossing evenness gives

$$
\sum_{n=0}^\infty a_n\nu^n
=F(\nu)=F(-\nu)=\sum_{n=0}^\infty a_n(-1)^n\nu^n.
$$

Equating coefficients implies

$$
a_n=a_n(-1)^n.
$$

For odd $n$, this gives $a_n=-a_n$, so $a_n=0$. Therefore only even powers appear.

</details>

### Exercise 2: Positivity of the second derivative

Assume

$$
F(\nu)=F(0)
+\frac{2\nu^2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'}
\frac{\operatorname{Im}F(\nu')}{\nu'^2-\nu^2}.
$$

Expand at small $\nu$ and derive

$$
F''(0)=\frac{4}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu').
$$

<details>
<summary><strong>Solution</strong></summary>

For $|\nu|<\nu_{\mathrm{th}}$,

$$
\frac{1}{\nu'^2-\nu^2}
=\frac{1}{\nu'^2}\left(1+\frac{\nu^2}{\nu'^2}+\cdots\right).
$$

Substituting into the dispersion relation gives

$$
F(\nu)=F(0)
+\frac{2\nu^2}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu')
+O(\nu^4).
$$

If

$$
F(\nu)=F(0)+a_2\nu^2+O(\nu^4),
$$

then

$$
F''(0)=2a_2.
$$

Thus

$$
F''(0)=\frac{4}{\pi}\int_{\nu_{\mathrm{th}}}^\infty
\frac{d\nu'}{\nu'^3}\operatorname{Im}F(\nu').
$$

</details>

### Exercise 3: EFT coefficient sign

Suppose the forward low-energy amplitude is

$$
F_{\mathrm{EFT}}(\nu)=a_0+\frac{c}{\Lambda^4}\nu^2+O(\nu^4).
$$

Assuming the forward positivity bound applies, what sign must $c$ have?

<details>
<summary><strong>Solution</strong></summary>

The second derivative is

$$
F_{\mathrm{EFT}}''(0)=\frac{2c}{\Lambda^4}.
$$

The positivity bound gives

$$
F''(0)>0.
$$

Assuming $\Lambda^4>0$, this implies

$$
c>0.
$$

</details>

### Exercise 4: Why massless exchange is dangerous

Explain why a term of the form

$$
\mathcal M(s,t)\supset \frac{g^2s^2}{t}
$$

obstructs the simplest forward-limit positivity argument.

<details>
<summary><strong>Solution</strong></summary>

The forward limit is $t\to0$. The term

$$
\frac{g^2s^2}{t}
$$

is singular in that limit, so the forward amplitude is not a regular analytic function of $\nu$ at fixed $t=0$. The simple dispersion relation assumed an amplitude with a well-defined forward limit after known pole subtractions. A massless exchange pole violates this assumption unless it is subtracted or regulated in a more careful framework.

</details>

### Exercise 5: Pole subtraction

Let

$$
F(\nu)=\frac{g^2}{M^2-\nu}+\frac{g^2}{M^2+\nu}+F_{\mathrm{heavy}}(\nu).
$$

Why should the first two terms be separated before using a positivity argument to constrain local coefficients in $F_{\mathrm{heavy}}$?

<details>
<summary><strong>Solution</strong></summary>

The first two terms are explicit light or resolved exchange poles. They are not local Wilson coefficients from heavier unknown physics. If the dispersion contour encloses or approaches these poles, their residues contribute separately to the contour relation.

To constrain local short-distance coefficients, one should write

$$
F_{\mathrm{heavy}}(\nu)
=F(\nu)-\frac{g^2}{M^2-\nu}-\frac{g^2}{M^2+\nu}
$$

and apply the positivity argument to the analytic remainder, assuming it satisfies the required assumptions. Otherwise the bound would mix known exchange physics with the local EFT coefficients one is trying to constrain.

</details>

## References

- A. Adams, N. Arkani-Hamed, S. Dubovsky, A. Nicolis, and R. Rattazzi, “Causality, Analyticity and an IR Obstruction to UV Completion,” *Journal of High Energy Physics* **0610** (2006) 014.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for S-matrix theory, analyticity assumptions, crossing, unitarity, and dispersion-relation background.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix framework.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the discussion of unitarity, analyticity, and EFT motivation.
- C. de Rham, S. Melville, A. J. Tolley, and S.-Y. Zhou, reviews and papers on positivity bounds for EFTs, especially gravitational and massive-spin applications.
- B. Bellazzini, M. Lewandowski, and J. Serra, and related modern reviews on amplitude positivity and EFT constraints.

## Version history

- **2026-06-13:** Initial polished draft. Added the forward scalar positivity argument, EFT interpretation, assumptions, pole-subtraction caveats, modern extensions, exercises, and a positivity-bound logic figure.
