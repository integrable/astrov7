---
title: "φ⁴ Theory: 2→2 Scattering"
description: "A complete tree-level calculation of identical scalar 2→2 scattering in real φ⁴ theory, from the quartic vertex to the cross section."
sidebar:
  label: "φ⁴ 2→2 Scattering"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§10–11; Coleman 2019, chs. 10–12; Schwartz 2014, chs. 5 and 7."
topics:
  - φ⁴ theory
  - tree-level scattering
  - cross sections
  - model calculations
canonicalTopics:
  - phi-four-theory
  - scalar-tree-amplitudes
  - two-to-two-scattering
  - model-calculation-library
researchStatus:
  established:
    - "The tree-level scalar 2→2 amplitude and its phase-space conversion to a cross section are textbook-standard consequences of the quartic Feynman rule and relativistic normalization."
  active:
    - "Higher-order corrections require renormalization, threshold analytic structure, and eventually infrared or multiparticle issues in more complicated theories."
---

## Summary

Real $\phi^4$ theory is the cleanest model in which a local interaction immediately becomes a measurable scattering amplitude. With

$$
\mathcal L
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

the tree-level four-scalar vertex is $-i\lambda$. For identical scalar scattering,

$$
\phi(p_1)+\phi(p_2)\to\phi(p_3)+\phi(p_4),
$$

the connected tree-level $S$-matrix element is

$$
\langle p_3p_4|S|p_1p_2\rangle_{\rm conn}
=i(2\pi)^4\delta^{(4)}(p_1+p_2-p_3-p_4)\mathcal M_{\rm tree},
$$

with

$$
\mathcal M_{\rm tree}=-\lambda.
$$

For equal masses in the center-of-momentum frame, and with the identical-particle factor included in the final-state phase space,

$$
\frac{d\sigma}{d\Omega}
=\frac{\lambda^2}{128\pi^2s},
\qquad
\sigma_{\rm tot}=\frac{\lambda^2}{32\pi s}.
$$

The factor $1/2!$ in the cross section is not a correction to the amplitude. It is a phase-space factor that prevents double counting the two indistinguishable final particles.

## Prerequisites

You should know the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), the definition of the invariant amplitude in [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), scalar Feynman rules from [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), and the kinematics in [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/). For the last step, use [Lorentz-Invariant Phase Space](/perturbative-qft/phase-space-cross-sections-decays/lorentz-invariant-phase-space/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/).

## Core idea

The interaction $-\lambda\phi^4/4!$ creates one local vertex with four scalar legs. At first order in $\lambda$, all four external particles meet at that one point. There is no internal propagator, no loop integral, and no channel denominator.

<figure class="doc-figure" style="--figure-width: 31rem; --caption-width: 48rem;">

![Tree-level 2-to-2 scattering in real phi-four theory](/figures/perturbative-qft/phi-four-two-to-two-scattering.svg)

<figcaption>

At tree level in real $\phi^4$ theory, identical scalar $2\to2$ scattering is a single contact diagram. The amplitude is $\mathcal M_{\rm tree}=-\lambda$ in the QFT.org $S=1+i(2\pi)^4\delta^{(4)}\mathcal M$ convention. The identical-particle factor belongs in final-state phase space, not in the vertex.

</figcaption>
</figure>

This page is deliberately humble. It is a small calculation, but it fixes the habits that every larger calculation uses: specify the Lagrangian, assign external momenta, write the amplitude with the site convention, square it, include flux and phase space, and only then discuss physical cross sections.

## Setup and conventions

We use the real scalar theory

$$
\mathcal L
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The external particles are identical scalar particles of mass $m$. We take

$$
p_1+p_2\to p_3+p_4,
\qquad
p_i^2=m^2.
$$

The Mandelstam invariants are

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

and equal masses imply

$$
s+t+u=4m^2.
$$

The connected $S$-matrix element is normalized as

$$
S_{fi}^{\rm conn}
=i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}.
$$

Thus a Feynman diagram contributes to $i\mathcal M$, not directly to $\mathcal M$.

## Vertex factor from the Lagrangian

The interaction action is

$$
S_{\rm int}=-\int d^4x\,\frac{\lambda}{4!}\phi(x)^4.
$$

At first order in the Dyson or path-integral expansion, the interaction contributes

$$
iS_{\rm int}
=-i\frac{\lambda}{4!}\int d^4x\,\phi(x)^4.
$$

For a four-point process, the four fields at the interaction point can be attached to four labeled external fields in $4!$ ways. That combinatoric factor cancels the $1/4!$ in the Lagrangian. The remaining local momentum-space vertex is

$$
-i\lambda.
$$

Therefore the tree-level connected diagram gives

$$
i\mathcal M_{\rm tree}=-i\lambda,
$$

so

$$
\mathcal M_{\rm tree}=-\lambda.
$$

The sign matters if this amplitude interferes with other amplitudes. For the leading total cross section by itself, only $|\mathcal M|^2=\lambda^2$ appears.

## Why there are no s-, t-, or u-channel diagrams at this order

The words “$s$ channel,” “$t$ channel,” and “$u$ channel” refer to ways momentum can flow through internal lines. The tree-level $\phi^4$ contact diagram has no internal line, so it is symmetric in the external legs without being a sum of three channel diagrams.

This is different from cubic scalar theory, Yukawa theory, or QED. In those theories, tree-level $2\to2$ scattering can involve exchange propagators such as

$$
\frac{i}{s-m^2+i\epsilon},
\qquad
\frac{i}{t-m^2+i\epsilon},
\qquad
\frac{i}{u-m^2+i\epsilon}.
$$

In $\phi^4$ theory those denominators first appear in loop corrections, not in the leading contact amplitude.

## From amplitude to differential cross section

For a two-particle initial state, the invariant cross-section formula is

$$
d\sigma
=\frac{1}{F}\,|\mathcal M|^2\,d\Pi_2,
$$

where

$$
F=4\sqrt{(p_1\cdot p_2)^2-m_1^2m_2^2}
$$

is the invariant flux factor and $d\Pi_2$ is two-body Lorentz-invariant phase space. For identical final particles, we include

$$
\frac{1}{2!}
$$

in the final-state phase-space integral. This division is a statement about counting final states, not about the strength of the interaction.

In the center-of-momentum frame,

$$
\frac{d\sigma}{d\Omega}
=\frac{1}{S_f}\frac{|\mathcal M|^2}{64\pi^2s}\frac{|\mathbf p_f|}{|\mathbf p_i|},
$$

where $S_f$ is the final-state symmetry factor. For this process,

$$
S_f=2!,
\qquad
|\mathbf p_f|=|\mathbf p_i|,
\qquad
|\mathcal M|^2=\lambda^2.
$$

Therefore

$$
\frac{d\sigma}{d\Omega}
=\frac{\lambda^2}{128\pi^2s}.
$$

Integrating over the full solid angle gives

$$
\sigma_{\rm tot}
=\int d\Omega\,\frac{\lambda^2}{128\pi^2s}
=\frac{\lambda^2}{32\pi s}.
$$

This formula treats the two final particles as an unordered pair. Equivalently, one may omit the $1/2!$ and integrate only over a hemisphere. The two methods agree if used consistently.

## Center-of-momentum kinematics

For equal masses in the center-of-momentum frame,

$$
p_1=(E,0,0,p),
\qquad
p_2=(E,0,0,-p),
$$

and

$$
p_3=(E,p\sin\theta,0,p\cos\theta),
\qquad
p_4=(E,-p\sin\theta,0,-p\cos\theta).
$$

Then

$$
s=4E^2,
\qquad
p=\sqrt{\frac{s}{4}-m^2},
$$

and

$$
t=-2p^2(1-\cos\theta),
\qquad
u=-2p^2(1+\cos\theta).
$$

The tree-level amplitude is independent of $\theta$, so the angular distribution is isotropic in the center-of-momentum frame.

## Checks on the result

### Dimensional analysis

In four spacetime dimensions, $\lambda$ is dimensionless. The cross section must have mass dimension $-2$. Since $s$ has dimension $2$,

$$
\sigma_{\rm tot}\sim \frac{\lambda^2}{s}
$$

has the correct dimension.

### Crossing symmetry

The same contact amplitude is obtained by crossing external legs. Since the vertex is local and has no internal momentum dependence, the tree amplitude is the same analytic constant in the $s$, $t$, and $u$ descriptions.

### Perturbative unitarity

For a constant high-energy scalar amplitude, the $s$-wave partial amplitude is roughly

$$
a_0=\frac{1}{32\pi}\int_{-1}^{1}d\cos\theta\,\mathcal M
=-\frac{\lambda}{16\pi}
$$

in the common non-identical normalization. Tree-level perturbative unitarity then suggests

$$
|\operatorname{Re}a_0|\lesssim \frac12,
\qquad
|\lambda|\lesssim 8\pi.
$$

This is not a sharp nonperturbative theorem about $\phi^4$ theory. It is a warning that tree perturbation theory is not trustworthy when the dimensionless coupling is too large.

## Common pitfalls

**Putting the identical-particle factor into the amplitude.** The quartic vertex is $-i\lambda$. The final-state $1/2!$ enters the phase-space integral for indistinguishable final particles.

**Double-counting the angular integral.** Either integrate over the full sphere and divide by $2!$, or integrate over one representative half of phase space. Do not do both.

**Calling the contact diagram an s-channel diagram.** At tree level in $\phi^4$ theory there is no internal momentum channel. Channel-dependent bubble diagrams appear at one loop.

**Forgetting the convention for $\mathcal M$.** The diagram gives $i\mathcal M$. With the QFT.org convention, $-i\lambda$ means $\mathcal M=-\lambda$.

**Mistaking the sign for an observable by itself.** The leading total cross section depends on $|\mathcal M|^2$, but the sign becomes physical through interference with other contributions.

## Relations to other pages

- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) explains the general tree-level scalar rules into which this example fits.
- [Identical Particles](/perturbative-qft/tree-level-scattering/identical-particles/) explains symmetry factors in final-state counting.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) derives the center-of-momentum formula used here.
- [φ⁴ Theory: One-Loop Four-Point Amplitude](/perturbative-qft/model-calculation-library/phi-four-one-loop-four-point/) continues this example to one loop.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) explains why the constant $\lambda$ becomes scale-dependent after loop corrections.

## Research status

- **Established:** The tree-level amplitude and cross section are standard textbook results once the $S$-matrix normalization and final-state counting convention are fixed.
- **Active:** The simple tree result is often used as a benchmark inside more complicated discussions: perturbative unitarity bounds, renormalization, triviality, finite-temperature scattering, and lattice matching.
- **Convention-dependent:** The sign of $\mathcal M$ depends on the $S$-matrix and Lagrangian conventions; the leading cross section does not.

## Exercises

### Exercise 1: The quartic vertex

Starting from

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

show that the four-scalar vertex factor is $-i\lambda$.

<details>
<summary><strong>Solution</strong></summary>

The first-order interaction contribution is

$$
iS_{\rm int}
=-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4.
$$

For a four-point function with labeled external insertions, the four fields at $z$ can be contracted with the four external fields in $4!$ ways. The factor $4!$ cancels the $1/4!$ in the interaction. The remaining local factor is

$$
-i\lambda.
$$

</details>

### Exercise 2: Mandelstam identity

For four equal-mass external particles in $2\to2$ scattering, prove

$$
s+t+u=4m^2.
$$

<details>
<summary><strong>Solution</strong></summary>

Using momentum conservation $p_1+p_2=p_3+p_4$ and $p_i^2=m^2$,

$$
\begin{aligned}
s+t+u
&=(p_1+p_2)^2+(p_1-p_3)^2+(p_1-p_4)^2\\
&=p_1^2+p_2^2+2p_1\cdot p_2
+p_1^2+p_3^2-2p_1\cdot p_3
+p_1^2+p_4^2-2p_1\cdot p_4.
\end{aligned}
$$

Since $p_3+p_4=p_1+p_2$,

$$
2p_1\cdot p_3+2p_1\cdot p_4
=2p_1\cdot(p_1+p_2)
=2m^2+2p_1\cdot p_2.
$$

Substitution leaves

$$
s+t+u=4m^2.
$$

</details>

### Exercise 3: Total cross section with identical final particles

Use

$$
\frac{d\sigma}{d\Omega}
=\frac{1}{2!}\frac{|\mathcal M|^2}{64\pi^2s}
$$

for equal-mass elastic scattering in the center-of-momentum frame and show that

$$
\sigma_{\rm tot}=\frac{\lambda^2}{32\pi s}.
$$

<details>
<summary><strong>Solution</strong></summary>

At tree level, $|\mathcal M|^2=\lambda^2$. Therefore

$$
\frac{d\sigma}{d\Omega}
=\frac{\lambda^2}{128\pi^2s}.
$$

Integrating over the full solid angle gives

$$
\sigma_{\rm tot}
=4\pi\frac{\lambda^2}{128\pi^2s}
=\frac{\lambda^2}{32\pi s}.
$$

</details>

### Exercise 4: Partial-wave estimate

For a constant scalar amplitude $\mathcal M=-\lambda$, compute

$$
a_0=\frac{1}{32\pi}\int_{-1}^{1}d\cos\theta\,\mathcal M.
$$

What crude perturbative unitarity bound follows from $|\operatorname{Re}a_0|\le 1/2$?

<details>
<summary><strong>Solution</strong></summary>

The integral is immediate:

$$
a_0=\frac{1}{32\pi}(2)(-\lambda)
=-\frac{\lambda}{16\pi}.
$$

The condition $|\operatorname{Re}a_0|\le 1/2$ gives

$$
\frac{|\lambda|}{16\pi}\le\frac12,
$$

so

$$
|\lambda|\le 8\pi.
$$

This is a tree-level perturbative estimate, not a substitute for a full unitarity analysis.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§10–11 for scattering amplitudes, Feynman rules, cross sections, and decay rates.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 10–12 for scalar scattering, Mandelstam variables, phase space, and the optical theorem.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 7 for cross sections and Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3 and 6 for scattering theory and covariant Feynman rules.

## Version history

- **2026-06-13:** Initial model-calculation-library page for tree-level $\phi^4$ $2\to2$ scattering in QFT.org conventions.
