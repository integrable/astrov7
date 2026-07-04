---
title: "BCFW Recursion"
description: "How complex momentum shifts reconstruct tree-level scattering amplitudes from their factorization poles."
sidebar:
  label: "BCFW Recursion"
  order: 5
level: Advanced
status: "Polished draft"
source: "Britto, Cachazo, Feng, and Witten; Elvang and Huang; Dixon; Schwartz ch. 27."
topics:
  - BCFW recursion
  - complex momenta
  - factorization
  - tree amplitudes
  - on-shell methods
canonicalTopics:
  - bcfw-recursion
  - complex-momentum-shifts
  - tree-level-recursion
  - on-shell-factorization
  - boundary-terms
researchStatus:
  established:
    - "BCFW recursion is a standard tree-level on-shell method for many massless gauge-theory and gravity amplitudes when the shifted amplitude has suitable large-complex-momentum behavior."
  active:
    - "Extensions and variants remain important in massive amplitudes, EFT amplitudes, loop integrands, curved backgrounds, celestial amplitudes, and positive-geometry approaches."
---

## Summary

BCFW recursion reconstructs a tree-level amplitude from lower-point on-shell amplitudes. The idea is to deform two external momenta by a complex parameter $z$, study the amplitude $A_n(z)$ as a meromorphic function, and use Cauchy's theorem to recover $A_n(0)$ from its factorization poles.

For a massless color-ordered amplitude, choose two legs $i$ and $j$ and make a complex shift such as

$$
\hat\lambda_i(z)=\lambda_i+z\lambda_j,
\qquad
\hat{\tilde\lambda}_j(z)=\tilde\lambda_j-z\tilde\lambda_i,
$$

with all other spinors unchanged. Then $\hat p_i(z)^2=\hat p_j(z)^2=0$ and total momentum remains conserved. If $A_n(z)$ vanishes as $z\to\infty$, Cauchy's theorem gives

$$
A_n(0)
=
\sum_{\text{channels }I}\sum_h
A_L(z_I)\frac{i}{P_I^2}A_R(z_I).
$$

Here $P_I(z_I)^2=0$, so the internal momentum is on shell at the pole, and the sum over $h$ runs over the helicities of the intermediate particle.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![BCFW recursion reconstructs a tree amplitude from complex poles and lower-point factorization](/figures/perturbative-qft/bcfw-recursion.svg)

<figcaption>

BCFW recursion shifts two external legs, views the amplitude as a meromorphic function of $z$, and reconstructs $A_n(0)$ from its factorization poles. Each pole corresponds to an internal momentum becoming on shell, so the residue is a product of lower-point on-shell amplitudes.

</figcaption>
</figure>

This is one of the cleanest examples of the modern on-shell philosophy. Instead of summing off-shell diagrams, one uses analyticity, locality, unitarity, and lower-point on-shell amplitudes. For Yang–Mills theory, the recursion reduces many complicated tree amplitudes to a controlled assembly of three-point building blocks.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/), and [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/). For the S-matrix logic behind factorization, review [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/) and [Threshold Behavior](/perturbative-qft/unitarity-analyticity-dispersion/threshold-behavior/).

## Core idea

Tree amplitudes are rational functions of spinor products. Their singularities occur when internal momenta go on shell. Near such a pole, locality and unitarity force the amplitude to factorize into lower-point amplitudes.

BCFW recursion packages this into one complex-variable argument:

```txt
complex shift
  → meromorphic amplitude A(z)
  → residues at factorization poles
  → lower-point amplitudes
  → original amplitude A(0).
```

The trick is to choose the shift so that no boundary term at infinity appears. When that works, the tree amplitude is determined entirely by its finite factorization poles.

This is a pleasantly radical claim. It says that, for a large class of amplitudes, the bulk of Feynman-diagram labor was bookkeeping for analytic structure that the amplitude already knew.

## Setup and conventions

We use all-outgoing momenta and the spinor-helicity conventions of the previous pages. For massless momenta,

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}.
$$

We write $A_n$ for color-ordered tree amplitudes with the momentum-conserving delta function and coupling stripped. BCFW recursion can also be applied to color-dressed amplitudes, gravity amplitudes, and amplitudes with massive legs, but the cleanest first version is color-ordered Yang–Mills theory.

## The complex shift

Pick two external legs $i$ and $j$. A common holomorphic-antiholomorphic shift is

$$
\hat\lambda_i(z)=\lambda_i+z\lambda_j,
\qquad
\hat{\tilde\lambda}_j(z)=\tilde\lambda_j-z\tilde\lambda_i,
$$

with

$$
\hat{\tilde\lambda}_i(z)=\tilde\lambda_i,
\qquad
\hat\lambda_j(z)=\lambda_j.
$$

The shifted momenta are

$$
\hat p_i(z)=p_i+zq,
\qquad
\hat p_j(z)=p_j-zq,
\qquad
q_{\alpha\dot\alpha}=\lambda_{j,\alpha}\tilde\lambda_{i,\dot\alpha}.
$$

Since

$$
q^2=0,
\qquad
q\cdot p_i=0,
\qquad
q\cdot p_j=0,
$$

both shifted external momenta remain on shell:

$$
\hat p_i(z)^2=0,
\qquad
\hat p_j(z)^2=0.
$$

Momentum conservation is also unchanged because the two shifts cancel.

This deformation is not a physical scattering process. It is an analytic probe of the physical amplitude. We move into complex kinematics, learn the residues, and return to $z=0$.

## Cauchy's theorem

The shifted amplitude is a rational function $A_n(z)$ at tree level. Consider

$$
\frac{A_n(z)}{z}.
$$

If $A_n(z)$ has no pole at infinity, then the sum of all residues on the Riemann sphere vanishes:

$$
\operatorname*{Res}_{z=0}\frac{A_n(z)}{z}
+
\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A_n(z)}{z}=0.
$$

The residue at $z=0$ is the physical amplitude:

$$
\operatorname*{Res}_{z=0}\frac{A_n(z)}{z}=A_n(0).
$$

Therefore

$$
A_n(0)
=-\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A_n(z)}{z},
$$

provided the boundary contribution at infinity vanishes.

If the boundary contribution does not vanish, the recursion is incomplete. One must either choose a better shift or compute the boundary term. This caveat is not fine print; it is the difference between a theorem and wishful chalkboard jazz.

## Factorization poles

The finite poles of $A_n(z)$ occur when some shifted internal momentum goes on shell. For a channel $I$, write

$$
P_I(z)=P_I+zq
$$

if the set $I$ contains leg $i$ but not leg $j$. The pole is determined by

$$
P_I(z_I)^2=0.
$$

Since $q^2=0$,

$$
P_I(z)^2=P_I^2+2zq\cdot P_I,
$$

so

$$
z_I=-\frac{P_I^2}{2q\cdot P_I}.
$$

Near this value, the tree amplitude factorizes:

$$
A_n(z)
\sim
\sum_h
A_L(z_I)
\frac{i}{P_I(z)^2}
A_R(z_I).
$$

Because

$$
P_I(z)^2=2q\cdot P_I\,(z-z_I),
$$

the residue of $A_n(z)/z$ at $z_I$ produces the usual propagator denominator $1/P_I^2$ after the small algebra is done. The recursion formula becomes

$$
A_n(0)
=
\sum_{I,h}
A_L(\hat p(z_I),-\hat P_I^{-h})
\frac{i}{P_I^2}
A_R(\hat P_I^h,\hat p(z_I)).
$$

For color-ordered amplitudes, the channel sum is over partitions compatible with the cyclic ordering, with shifted legs $i$ and $j$ on opposite sides of the factorization channel.

## Boundary behavior

The recursion formula is useful only when the shifted amplitude is well behaved at large $z$. In Yang–Mills theory, many choices of shifted legs give

$$
A_n(z)\to0
\qquad (z\to\infty),
$$

so the boundary term vanishes. Which shifts are good depends on helicities, adjacency, theory, and sometimes the representation of the amplitude.

The rough physical reason is gauge-theoretic cancellation. Individual Feynman diagrams often grow with $z$, but gauge invariance and the structure of Yang–Mills interactions can make the sum fall. Gravity amplitudes can fall even faster for good shifts, reflecting the double-copy-like structure of gravitational interactions.

In effective field theories with higher-derivative interactions, boundary terms are common. That is not a failure of complex analysis. It means the amplitude contains contact information not determined by ordinary factorization alone.

## Four-point example

Consider the color-ordered Yang–Mills amplitude

$$
A_4(1^-,2^-,3^+,4^+).
$$

With an appropriate BCFW shift, the only contributing channel is the one that splits the ordering into a left three-point amplitude and a right three-point amplitude:

$$
A_4(1^-,2^-,3^+,4^+)
=
A_3(\hat1^-,2^-,-\hat P^+)
\frac{i}{s_{12}}
A_3(\hat P^-,3^+,\hat4^+).
$$

The three-point amplitudes are fixed by little-group scaling. Substituting them and using the on-shell value of the shifted spinors gives

$$
A_4(1^-,2^-,3^+,4^+)
=
i\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\langle34\rangle\langle41\rangle}.
$$

This is the four-point Parke–Taylor amplitude. The computation illustrates the broader pattern: BCFW recursion reduces higher-point amplitudes to lower-point amplitudes, and eventually to complex three-point amplitudes.

## Why three-point amplitudes are enough

The recursion bottoms out at three points because two-point scattering amplitudes are not ordinary interaction amplitudes. The nonzero massless three-point amplitudes require complex kinematics, exactly as described on the [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) page.

Thus BCFW recursion builds real physical tree amplitudes from complex three-point seeds. The intermediate steps live in complex momentum space, but the final amplitude at $z=0$ is the desired physical rational function.

This is a good example of a recurring theme in modern QFT: the shortest route to a real answer often goes through complex space. Physics has a mild but persistent fondness for detours.

## Locality and unitarity in the recursion

BCFW recursion makes two structural principles explicit.

First, locality appears through simple poles. Tree amplitudes have poles when an internal propagator goes on shell:

$$
P^2\to0.
$$

Second, unitarity appears through factorization. The residue at such a pole is a product of lower-point amplitudes summed over intermediate physical states.

The recursion says that, if there is no boundary term, these ingredients determine the amplitude. In that sense, BCFW recursion is a constructive version of the slogan:

```txt
Tree amplitudes = locality + on-shell factorization + good behavior at infinity.
```

The good-behavior condition is the subtle part. It encodes information about the theory's high-energy behavior under the chosen complex shift.

## Color-ordered recursion

For an ordered amplitude $A_n(1,2,\ldots,n)$, choose shifted legs $i$ and $j$. The BCFW sum runs over cyclic intervals that separate $i$ from $j$. A typical term has the form

$$
A_L(\ldots,\hat i,\ldots,-\hat P^{-h})
\frac{i}{P^2}
A_R(\hat P^h,\ldots,\hat j,\ldots).
$$

The lower-point amplitudes preserve the cyclic order inherited from the parent amplitude. This is why BCFW recursion is especially tidy for color-ordered amplitudes: the allowed poles are already planar, so the partitions are easy to list.

For color-dressed amplitudes, the same physical factorization exists, but the bookkeeping includes color sums and more channel structures. Color ordering is the clean notebook; color dressing is the full invoice.

## Common pitfalls

**Thinking the shifted momenta are physical.** The shift is an analytic device. Intermediate momenta are complex; the physical amplitude is recovered at $z=0$.

**Forgetting the boundary term.** BCFW recursion requires suitable behavior at infinity. If $A_n(z)$ does not vanish, factorization poles alone are not enough.

**Summing the wrong channels.** For color-ordered amplitudes, only cyclically compatible partitions appear. Do not insert nonplanar poles into one ordered amplitude.

**Using real three-point intuition.** Massless three-point amplitudes vanish or become degenerate for real Lorentzian momenta. BCFW recursion relies on complex three-point kinematics.

**Dropping helicity sums.** The internal state is on shell and physical. Sum over allowed helicities or particle species in the theory.

**Confusing BCFW with loop unitarity.** BCFW is primarily a tree-level recursion. Generalized unitarity uses on-shell cuts to construct loop integrands and integrals. The philosophies are related, but the technical objects differ.

## Relations to other pages

- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) defines the variables used for complex shifts.
- [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) gives the lower-point seeds of the recursion.
- [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) explains why the BCFW channel sum is planar for partial amplitudes.
- [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) discusses analytic structure beyond tree-level rational functions.
- [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) and [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) develop the loop-level on-shell cousin of factorization.
- [S-Matrix Bootstrap Preview](/perturbative-qft/unitarity-analyticity-dispersion/s-matrix-bootstrap-preview/) places recursion in the broader program of determining amplitudes from consistency conditions.

## Research status

**Established:** BCFW recursion is a standard and rigorously understood tree-level method for amplitudes with appropriate complex-shift behavior, especially in Yang–Mills theory and gravity.

**Active:** Extensions to massive particles, EFTs, loop integrands, amplitudes in curved backgrounds, celestial variables, and positive-geometry formulations are active research areas.

**Speculative:** The basic recursion is not speculative. Broader claims that all QFT dynamics should be reformulated purely in on-shell geometric terms are powerful but theory-dependent and still developing.

## Exercises

### Exercise 1: The shift preserves the mass shell

Using

$$
\hat\lambda_i= \lambda_i+z\lambda_j,
\qquad
\hat{\tilde\lambda}_j= \tilde\lambda_j-z\tilde\lambda_i,
$$

show that $\hat p_i^2=\hat p_j^2=0$.

<details>
<summary><strong>Solution</strong></summary>

A massless momentum written as

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}
$$

has zero determinant, hence $p^2=0$. Under the shift,

$$
\hat p_i=(\lambda_i+z\lambda_j)\tilde\lambda_i,
\qquad
\hat p_j=\lambda_j(\tilde\lambda_j-z\tilde\lambda_i).
$$

Each is still an outer product of one undotted and one dotted spinor. Therefore each still has zero determinant:

$$
\hat p_i^2=\hat p_j^2=0.
$$

</details>

### Exercise 2: Momentum conservation

Show that the same shift preserves total momentum.

<details>
<summary><strong>Solution</strong></summary>

The shifted momenta are

$$
\hat p_i=p_i+zq,
\qquad
\hat p_j=p_j-zq,
$$

where

$$
q_{\alpha\dot\alpha}=\lambda_{j,\alpha}\tilde\lambda_{i,\dot\alpha}.
$$

Thus

$$
\hat p_i+\hat p_j=p_i+p_j.
$$

All other momenta are unchanged, so the total momentum is unchanged.

</details>

### Exercise 3: Pole location

Let $P_I(z)=P_I+zq$ with $q^2=0$. Derive the value of $z$ where $P_I(z)^2=0$.

<details>
<summary><strong>Solution</strong></summary>

We have

$$
P_I(z)^2=(P_I+zq)^2=P_I^2+2zq\cdot P_I,
$$

since $q^2=0$. Setting this equal to zero gives

$$
z_I=-\frac{P_I^2}{2q\cdot P_I}.
$$

This is the complex value at which the internal momentum in channel $I$ becomes on shell.

</details>

### Exercise 4: Cauchy's theorem and the recursion sign

Assume $A(z)\to0$ at infinity. Show that

$$
A(0)=-\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A(z)}{z}.
$$

<details>
<summary><strong>Solution</strong></summary>

The meromorphic function $A(z)/z$ has poles at $z=0$ and at the finite factorization poles $z_I$. Since there is no pole at infinity, the sum of residues on the Riemann sphere is zero:

$$
\operatorname*{Res}_{z=0}\frac{A(z)}{z}
+
\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A(z)}{z}=0.
$$

The first residue is

$$
\operatorname*{Res}_{z=0}\frac{A(z)}{z}=A(0).
$$

Therefore

$$
A(0)=-\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A(z)}{z}.
$$

</details>

### Exercise 5: What a boundary term means

Suppose $A(z)$ approaches a nonzero constant as $z\to\infty$. What changes in the recursion formula?

<details>
<summary><strong>Solution</strong></summary>

If $A(z)$ does not vanish at infinity, then $A(z)/z$ has a pole at infinity. The residue theorem gives

$$
A(0)
=-\sum_{z_I}\operatorname*{Res}_{z=z_I}\frac{A(z)}{z}
-\operatorname*{Res}_{z=\infty}\frac{A(z)}{z}.
$$

The finite factorization poles no longer determine the full amplitude by themselves. The extra term is called a boundary contribution. It often corresponds to contact-term information not visible in ordinary factorization channels.

</details>

## References

- R. Britto, F. Cachazo, and B. Feng, “New Recursion Relations for Tree Amplitudes of Gluons,” *Nuclear Physics B* **715** (2005), for the original recursion relation.
- R. Britto, F. Cachazo, B. Feng, and E. Witten, “Direct Proof of Tree-Level Recursion Relation in Yang–Mills Theory,” *Physical Review Letters* **94** (2005), for the complex-analysis proof.
- E. Witten, “Perturbative Gauge Theory as a String Theory in Twistor Space,” *Communications in Mathematical Physics* **252** (2004), for the twistor-space context that catalyzed the modern recursion era.
- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” in *QCD and Beyond*, for a classic review of helicity and recursion ideas.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a modern systematic treatment of BCFW recursion.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for a graduate-level introduction to spinor helicity, color ordering, complex momenta, and on-shell recursion.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, emphasizing complex shifts, factorization poles, boundary terms, and the relation to color-ordered amplitudes.
