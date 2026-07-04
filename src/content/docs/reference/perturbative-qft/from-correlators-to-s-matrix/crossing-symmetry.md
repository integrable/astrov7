---
title: "Crossing Symmetry"
description: "How scattering amplitudes in different physical channels arise as analytic continuations of one LSZ-reduced amplitude with external particles crossed to antiparticles."
sidebar:
  label: "Crossing Symmetry"
  order: 7
level: Graduate
status: "Polished draft"
source: "Weinberg 1995, Vol. I, chs. 3 and 6; Coleman 2019, ch. 11; Srednicki 2007, §§5 and 10; Schwartz 2014, chs. 6–7 and 24; Zee 2010, ch. II.8"
topics:
  - crossing symmetry
  - analytic continuation
  - scattering amplitudes
  - antiparticles
  - Mandelstam variables
canonicalTopics:
  - crossing-symmetry
  - crossed-channels
  - analytic-amplitudes
  - all-incoming-convention
researchStatus:
  established:
    - "Crossing symmetry is a textbook consequence of locality, Lorentz invariance, spectral assumptions, and the LSZ relation between correlators and S-matrix elements in ordinary relativistic QFT."
  active:
    - "Massless gauge theories, infraparticles, unstable particles, bound states, curved backgrounds, and nonperturbative S-matrix programs require more careful versions of crossing than the stable-particle perturbative formulae used here."
---

## Summary

**Crossing symmetry** says that amplitudes for apparently different scattering processes are boundary values of the same analytic amplitude. Moving an external particle from the final state to the initial state turns it into the corresponding antiparticle and reverses the sign of its four-momentum in the analytic continuation.

For example, a four-point process may be packaged into an all-incoming analytic amplitude

$$
\mathcal A_{ab\bar c\bar d}(q_1,q_2,q_3,q_4),
\qquad
q_1+q_2+q_3+q_4=0.
$$

The physical process

$$
a(p_1)+b(p_2)\to c(p_3)+d(p_4)
$$

is obtained from the boundary value with

$$
(q_1,q_2,q_3,q_4)=(p_1,p_2,-p_3,-p_4).
$$

The crossed process

$$
a(p_1)+\bar c(p_3)\to \bar b(p_2)+d(p_4)
$$

is a different physical region of the same analytic object. In terms of Mandelstam variables, crossing exchanges which variable plays the role of the center-of-mass energy squared.

<figure class="doc-figure" style="--figure-width: 55rem; --caption-width: 55rem;">

![Crossing symmetry maps one analytic LSZ amplitude to different physical channel regions](/figures/perturbative-qft/crossing-symmetry-map.svg)

<figcaption>

Crossing relates different physical regions of the same analytic amplitude. The $s$-, $t$-, and $u$-channel processes are not usually the same real experiment; they are different boundary values reached by analytic continuation and by crossing external particles to antiparticles.

</figcaption>
</figure>

## Prerequisites

You should know [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), and [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/).

## Core idea

The S-matrix is obtained from time-ordered correlation functions by LSZ reduction. Those correlators are not tied to one scattering interpretation. Their Fourier transforms define analytic functions of complex external momenta, with poles and cuts fixed by the spectrum. Different scattering processes are obtained by approaching different real physical regions of the same analytic function.

The mnemonic is simple:

| Operation | Physical meaning |
|---|---|
| outgoing particle $c(p)$ | incoming antiparticle $\bar c(-p)$ in all-incoming notation |
| incoming antiparticle $\bar c(p)$ | outgoing particle $c(-p)$ in all-incoming notation |
| exchange $s$ and $t$ | move from an $s$-channel physical region to a $t$-channel physical region |
| exchange $s$ and $u$ | move from an $s$-channel physical region to a $u$-channel physical region |

The subtle word is **analytic**. Crossing is not the statement that two experiments at the same real momenta have equal amplitudes. It is the statement that their amplitudes are analytic continuations of one another, with the correct particle–antiparticle replacement and the correct boundary-value prescription around singularities.

## Setup and conventions

We use the qft.org conventions: mostly-minus metric, covariantly normalized external states, and

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

For a physical $2\to2$ process,

$$
a(p_1)+b(p_2)\to c(p_3)+d(p_4),
$$

we define

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2.
$$

For external masses $p_i^2=m_i^2$,

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

We use the standard letter $u$ for the third Mandelstam invariant. The symbol has nothing to do with a Dirac spinor $u(p,s)$.

## All-incoming notation

Crossing is cleanest when every external momentum is written as incoming. For the physical process

$$
a(p_1)+b(p_2)\to c(p_3)+d(p_4),
$$

the all-incoming momentum assignment is

$$
q_1=p_1,
\qquad
q_2=p_2,
\qquad
q_3=-p_3,
\qquad
q_4=-p_4.
$$

The outgoing particles $c$ and $d$ appear as incoming antiparticles $\bar c$ and $\bar d$ in the analytic amplitude:

$$
\mathcal M(a b\to c d)
=
\mathcal A(a(q_1),b(q_2),\bar c(q_3),\bar d(q_4))
\bigg|_{q=(p_1,p_2,-p_3,-p_4)}.
$$

For self-conjugate particles, such as a real scalar, the antiparticle label is the same particle label. The crossing operation then looks like only a momentum reversal, but the underlying rule is still particle to antiparticle.

For spin, polarization, charge, color, and flavor labels, crossing also transforms the external wavefunction factor. A crossed outgoing fermion does not remain the same spinor factor with a minus sign casually inserted. The detailed spinor and polarization rules are best handled by deriving the amplitude from LSZ or by using a consistent all-incoming Feynman-rule convention.

## Crossed channels

For equal-mass elastic scattering,

$$
1+2\to3+4,
\qquad
m_1=m_2=m_3=m_4=m,
$$

the Mandelstam variables obey

$$
s+t+u=4m^2.
$$

The ordinary $s$-channel physical region has

$$
s\ge 4m^2,
$$

because $s$ is the square of the total incoming energy. In the center-of-mass frame,

$$
t=-2|\mathbf p|^2(1-\cos\theta),
\qquad
u=-2|\mathbf p|^2(1+\cos\theta),
$$

so $t$ and $u$ are nonpositive for physical elastic scattering.

The crossed $t$-channel process treats $t$ as the physical center-of-mass energy squared. For example,

$$
1+\bar3\to\bar2+4
$$

has physical threshold

$$
t\ge 4m^2
$$

for equal masses. That is not the same real kinematic region as the original $s$-channel experiment. Crossing continues the analytic amplitude from one region to the other.

This is why drawings of $s$-, $t$-, and $u$-channel diagrams are useful but can also mislead. The diagram topology may suggest a simple relabeling. The actual statement involves analytic continuation through a complex kinematic domain with poles and branch cuts.

## Example: scalar tree amplitudes

Consider real scalar theory with cubic interaction

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3.
$$

The tree-level four-point amplitude is

$$
i\mathcal M_{\rm tree}
=
(-ig)^2
\left[
\frac{i}{s-m^2+i\epsilon}
+
\frac{i}{t-m^2+i\epsilon}
+
\frac{i}{u-m^2+i\epsilon}
\right].
$$

Therefore

$$
\mathcal M_{\rm tree}(s,t,u)
=
-g^2
\left[
\frac{1}{s-m^2+i\epsilon}
+
\frac{1}{t-m^2+i\epsilon}
+
\frac{1}{u-m^2+i\epsilon}
\right].
$$

For identical real scalars, crossing is especially visible: the same formula is symmetric under permutations of $s$, $t$, and $u$. The pole at $s=m^2$ is interpreted as exchange of an intermediate particle in the $s$ channel. The same analytic pole appears as a crossed-channel pole when viewed in the $t$ or $u$ physical region.

For a quartic interaction

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

the tree-level amplitude is simply

$$
\mathcal M_{\rm tree}=-\lambda,
$$

which is crossing symmetric in the most boring possible way. That example is good for checking signs, but too featureless to teach analytic structure.

## Why locality matters

Crossing is not an arbitrary convention imposed on amplitudes. In local relativistic QFT, spacelike-separated fields commute or anticommute, and correlation functions have controlled analytic domains. The LSZ formula then relates the pole behavior of those correlation functions to scattering amplitudes.

The rough chain is

$$
\text{locality and spectrum}
\quad\Longrightarrow\quad
\text{analyticity of correlators}
\quad\Longrightarrow\quad
\text{analyticity of amplitudes}
\quad\Longrightarrow\quad
\text{crossing between channels}.
$$

Perturbative Feynman diagrams display this structure term by term. A propagator denominator such as

$$
\frac{1}{(p_1+p_2)^2-m^2+i\epsilon}
$$

is the same analytic denominator that can be reinterpreted in a crossed channel after a momentum reversal. The full nonperturbative statement is deeper because it is about the analytic continuation of the complete S-matrix, not just a single graph.

## Boundary values and branch cuts

Physical amplitudes are usually not single-valued functions on the real Mandelstam plane. Thresholds produce branch cuts. For example, a two-particle threshold in the $s$ channel begins at

$$
s=(m_a+m_b)^2.
$$

The physical scattering amplitude is a boundary value approached from the side selected by the $i\epsilon$ prescription. A crossed amplitude may live on a different sheet or a different edge of a cut. Careless crossing across branch cuts is one of the fastest ways to manufacture wrong signs and wrong imaginary parts.

At tree level, where amplitudes are often rational functions, this complication may be hidden. At loop level and nonperturbatively, the distinction between analytic function, branch sheet, and physical boundary value becomes essential.

## Common pitfalls

**Treating crossing as a real-momentum identity.** The crossed process usually lies in a different physical region. Crossing says that the amplitudes are related by analytic continuation, not that two real scattering experiments at the same values of momenta are literally identical.

**Forgetting antiparticles.** Moving a particle from the final state to the initial state changes it into the corresponding antiparticle. For self-conjugate particles this is invisible, which is pedagogically convenient and also a little dangerous.

**Crossing spinors by eye.** Fermion and vector external wavefunctions transform with their own conventions. Use LSZ or a consistent all-incoming rule rather than guessing how $u$, $v$, $\bar u$, $\bar v$, and polarization vectors should be moved across the arrow.

**Ignoring branch cuts.** Above thresholds, amplitudes have imaginary parts and cuts. The crossed amplitude is a boundary value of an analytic continuation, so the side of the cut matters.

**Using crossing where the S-matrix itself is ill-defined.** Charged particles in massless gauge theories and unstable particles require refinements. Inclusive observables, dressed asymptotic states, or pole definitions may replace the naive stable-particle S-matrix.

## Relations to other pages

- [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) explains why scattering amplitudes are extracted from pole residues of time-ordered correlators.
- [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) gives the off-shell objects whose on-shell limits enter the crossing discussion.
- [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains how crossed scalar, spinor, and vector legs carry residue or wavefunction factors.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) shows how momentum flow and all-incoming conventions are assigned diagram by diagram.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the amplitude normalization used in the crossing formulas.

## Research status

For stable particles in ordinary local relativistic QFT, crossing is part of the standard analytic S-matrix package. In perturbation theory it is visible in the analytic dependence of Feynman integrals on external momenta.

The main caveats are physical, not cosmetic. Massless gauge theories have infrared issues with charged asymptotic states. Unstable particles do not appear as ordinary asymptotic states. Bound states and confinement can make the correct asymptotic degrees of freedom very different from the fields in the Lagrangian. Nonperturbative S-matrix programs often take crossing as a central axiom, but the precise hypotheses behind crossing remain important.

## Exercises

### Exercise 1: All-incoming bookkeeping

Write the all-incoming momentum assignment for

$$
a(p_1)+b(p_2)\to c(p_3)+d(p_4).
$$

Then write the all-incoming labels for the crossed process

$$
a(p_1)+\bar c(p_3)\to \bar b(p_2)+d(p_4).
$$

<details>
<summary><strong>Solution</strong></summary>

For the original process,

$$
(q_1,q_2,q_3,q_4)=(p_1,p_2,-p_3,-p_4),
$$

and the analytic labels are

$$
a(q_1),\quad b(q_2),\quad \bar c(q_3),\quad \bar d(q_4).
$$

For the crossed process $a+\bar c\to\bar b+d$, the incoming labels are $a(p_1)$ and $\bar c(p_3)$, while the outgoing labels are $\bar b(p_2)$ and $d(p_4)$. In all-incoming notation this is

$$
a(p_1),\quad \bar c(p_3),\quad b(-p_2),\quad \bar d(-p_4).
$$

The particle–antiparticle flip occurs for the legs moved between the final and initial sides.

</details>

### Exercise 2: Mandelstam identity

For $2\to2$ scattering with

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

and momentum conservation $p_1+p_2=p_3+p_4$, show that

$$
s+t+u=m_1^2+m_2^2+m_3^2+m_4^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Expand the definitions:

$$
\begin{aligned}
s+t+u
&=(p_1+p_2)^2+(p_1-p_3)^2+(p_1-p_4)^2\\
&=3p_1^2+p_2^2+p_3^2+p_4^2
+2p_1\cdot p_2-2p_1\cdot p_3-2p_1\cdot p_4.
\end{aligned}
$$

Momentum conservation gives

$$
p_2=p_3+p_4-p_1,
$$

so

$$
p_2^2=p_3^2+p_4^2+p_1^2+2p_3\cdot p_4-2p_1\cdot p_3-2p_1\cdot p_4.
$$

A faster route is to use

$$
p_1+p_2-p_3-p_4=0
$$

and square it. Rearranging the resulting dot products gives

$$
s+t+u=p_1^2+p_2^2+p_3^2+p_4^2.
$$

Since $p_i^2=m_i^2$, the identity follows.

</details>

### Exercise 3: Crossing check in cubic scalar theory

Using

$$
\mathcal M_{\rm tree}(s,t,u)
=
-g^2
\left[
\frac{1}{s-m^2+i\epsilon}
+
\frac{1}{t-m^2+i\epsilon}
+
\frac{1}{u-m^2+i\epsilon}
\right],
$$

show that the real scalar tree amplitude is symmetric under $s\leftrightarrow t$ and $s\leftrightarrow u$.

<details>
<summary><strong>Solution</strong></summary>

The expression is a sum of three terms with the same coefficient and the same pole prescription:

$$
\mathcal M_{\rm tree}(s,t,u)
=-g^2\big[F(s)+F(t)+F(u)\big],
\qquad
F(x)=\frac{1}{x-m^2+i\epsilon}.
$$

Permuting $s$, $t$, and $u$ only reorders the three terms. Therefore

$$
\mathcal M_{\rm tree}(s,t,u)=\mathcal M_{\rm tree}(t,s,u)=\mathcal M_{\rm tree}(u,t,s).
$$

This simple symmetry reflects both the identical external particles and the existence of the three exchange diagrams.

</details>

### Exercise 4: Why the crossed region is not the same real region

For equal-mass elastic scattering in the center-of-mass frame, show that

$$
t=-2|\mathbf p|^2(1-\cos\theta).
$$

Explain why this cannot describe a physical $t$-channel two-particle threshold at the same real kinematic point.

<details>
<summary><strong>Solution</strong></summary>

In the center-of-mass frame,

$$
p_1=(E,\mathbf p),
\qquad
p_3=(E,\mathbf p'),
\qquad
|\mathbf p'|=|\mathbf p|.
$$

Then

$$
t=(p_1-p_3)^2=(E-E)^2-(\mathbf p-\mathbf p')^2.
$$

Since

$$
(\mathbf p-\mathbf p')^2=2|\mathbf p|^2(1-\cos\theta),
$$

we get

$$
t=-2|\mathbf p|^2(1-\cos\theta)\le0.
$$

A physical equal-mass $t$-channel two-particle state would require $t\ge4m^2$. Therefore the original real $s$-channel elastic region is not the same real region as the physical $t$ channel. Crossing relates them by analytic continuation.

</details>

## References

### Standard first pass

- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 11 and 14, for crossing, CPT, phase space, and the LSZ formalism.
- Mark Srednicki, *Quantum Field Theory*, §§5 and 10, for LSZ reduction and scattering amplitudes with Feynman rules.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 6–7 and 24, for S-matrix normalization, Feynman rules, and unitarity/analyticity context.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3 and 6, for scattering theory, the S-matrix, Feynman rules, and analytic structure.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. II.8, for crossing as seen in QED processes.
- R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix*, for the classic analytic S-matrix treatment of crossing and singularities.

## Version history

- **2026-06-12:** Initial standardized page.
