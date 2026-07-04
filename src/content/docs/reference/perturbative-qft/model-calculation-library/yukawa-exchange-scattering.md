---
title: "Yukawa Exchange Scattering"
description: "A complete tree-level calculation of distinguishable fermion scattering by scalar exchange, including the amplitude, spin average, cross section, and nonrelativistic Yukawa potential."
sidebar:
  label: "Yukawa Exchange Scattering"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman 2019, chs. 10–12 and 21; Srednicki 2007, §§45–48 and Yukawa-theory examples; Schwartz 2014, chs. 5, 7, and 13."
topics:
  - Yukawa theory
  - scalar exchange
  - tree-level scattering
  - model calculations
canonicalTopics:
  - yukawa-theory
  - scalar-exchange-amplitudes
  - spin-averaged-cross-sections
  - model-calculation-library
researchStatus:
  established:
    - "Tree-level scalar exchange between Dirac fermions is a textbook-standard model calculation and the relativistic origin of the Yukawa potential."
  active:
    - "The same scalar-exchange structure reappears in nuclear models, Higgs-mediated amplitudes, dark-sector simplified models, and effective potentials, where spin, flavor, and finite-width effects can matter."
---

## Summary

Yukawa theory is the simplest setting where fermions scatter by exchanging a boson. For two distinguishable Dirac fields $\psi$ and $\chi$ coupled to a real scalar $\phi$,

$$
\mathcal L
=\overline\psi(i\gamma^\mu\partial_\mu-m_\psi)\psi
+\overline\chi(i\gamma^\mu\partial_\mu-m_\chi)\chi
+\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12\mu^2\phi^2
-g_\psi\phi\overline\psi\psi
-g_\chi\phi\overline\chi\chi,
$$

the tree-level process

$$
\psi(p_1)+\chi(p_2)\to\psi(p_3)+\chi(p_4)
$$

is mediated by a single $t$-channel scalar propagator. With

$$
q=p_1-p_3=p_4-p_2,
\qquad t=q^2,
$$

the amplitude is

$$
\mathcal M_t
=
\frac{g_\psi g_\chi}{\mu^2-t-i\epsilon}
\left[\overline u_\psi(p_3)u_\psi(p_1)\right]
\left[\overline u_\chi(p_4)u_\chi(p_2)\right].
$$

A useful spin-averaged check is

$$
\overline{|\mathcal M_t|^2}
=
\frac{(g_\psi g_\chi)^2}{(\mu^2-t)^2}
(4m_\psi^2-t)(4m_\chi^2-t).
$$

In the nonrelativistic limit, scalar exchange produces the Yukawa potential

$$
V(r)=-\frac{g_\psi g_\chi}{4\pi}\frac{e^{-\mu r}}{r}.
$$

This sign is not a typo: same-sign scalar charges attract, unlike same-sign electric charges.

## Prerequisites

You should know [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/), [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/). For the spinor background, review [Dirac Field](/foundations/free-fields/dirac-field/).

## Core idea

A Yukawa vertex converts a scalar field into a scalar fermion bilinear. At tree level, scattering between two fermion lines is therefore just

$$
\text{fermion current}\times\text{scalar propagator}\times\text{fermion current},
$$

where the “current” is now the Lorentz scalar bilinear $\overline u(p')u(p)$ rather than the QED vector current $\overline u(p')\gamma^\mu u(p)$.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 54rem;">

![Tree-level Yukawa exchange scattering](/figures/perturbative-qft/yukawa-exchange-scattering.svg)

<figcaption>

Tree-level distinguishable-fermion scattering by scalar exchange. The exchanged scalar carries $q=p_1-p_3$ and contributes $i/(t-\mu^2+i\epsilon)$. The nonrelativistic limit turns the same diagram into the attractive Yukawa potential $V(r)=-g_\psi g_\chi e^{-\mu r}/(4\pi r)$.

</figcaption>
</figure>

This calculation is the clean bridge between relativistic Feynman rules and the older language of potentials. It also teaches a useful warning: a propagator denominator is not automatically a force law. The force law emerges only after taking the nonrelativistic limit and matching to Born scattering.

## Setup and conventions

We take two distinguishable Dirac fields so that no exchange antisymmetrization is needed. Their masses are

$$
m_\psi,
\qquad
m_\chi,
$$

and the exchanged scalar has mass $\mu$. The process is

$$
\psi(p_1,s_1)+\chi(p_2,s_2)\to\psi(p_3,s_3)+\chi(p_4,s_4),
$$

with all external particles on shell:

$$
p_1^2=p_3^2=m_\psi^2,
\qquad
p_2^2=p_4^2=m_\chi^2.
$$

The momentum transfer is

$$
q=p_1-p_3=p_4-p_2,
\qquad
q^2=t.
$$

The Feynman rules needed here are

$$
\text{$\psi\psi\phi$ vertex: }-ig_\psi,
\qquad
\text{$\chi\chi\phi$ vertex: }-ig_\chi,
$$

and

$$
\text{scalar propagator: }\frac{i}{q^2-\mu^2+i\epsilon}.
$$

External fermions contribute $u$ spinors for incoming particles and $\overline u$ spinors for outgoing particles.

## Tree-level amplitude

Applying the rules gives

$$
\begin{aligned}
i\mathcal M_t
&=
\left[\overline u_\psi(p_3,s_3)(-ig_\psi)u_\psi(p_1,s_1)\right]
\frac{i}{t-\mu^2+i\epsilon}
\left[\overline u_\chi(p_4,s_4)(-ig_\chi)u_\chi(p_2,s_2)\right] \\
&=
-i\frac{g_\psi g_\chi}{t-\mu^2+i\epsilon}
\left[\overline u_\psi(p_3,s_3)u_\psi(p_1,s_1)\right]
\left[\overline u_\chi(p_4,s_4)u_\chi(p_2,s_2)\right].
\end{aligned}
$$

Therefore

$$
\mathcal M_t
=
\frac{g_\psi g_\chi}{\mu^2-t-i\epsilon}
\left[\overline u_\psi(p_3,s_3)u_\psi(p_1,s_1)\right]
\left[\overline u_\chi(p_4,s_4)u_\chi(p_2,s_2)\right].
$$

For ordinary spacelike momentum transfer, $t<0$, so the denominator is positive for a massive exchanged scalar.

## Spin average

For unpolarized scattering, average over the two spins of each incoming fermion and sum over final spins:

$$
\overline{|\mathcal M_t|^2}
=
\frac{1}{4}\sum_{s_1,s_2,s_3,s_4}|\mathcal M_t|^2.
$$

Using

$$
\sum_s u(p,s)\overline u(p,s)=p\!\!\!/+m,
$$

the spin sums become traces:

$$
\overline{|\mathcal M_t|^2}
=
\frac{(g_\psi g_\chi)^2}{(\mu^2-t)^2}
\frac14
\operatorname{tr}\left[(p_3\!\!\!/+m_\psi)(p_1\!\!\!/+m_\psi)\right]
\operatorname{tr}\left[(p_4\!\!\!/+m_\chi)(p_2\!\!\!/+m_\chi)\right].
$$

The trace identity

$$
\operatorname{tr}\left[(a\!\!\!/+m)(b\!\!\!/+m)\right]
=4(a\cdot b+m^2)
$$

gives

$$
\overline{|\mathcal M_t|^2}
=
\frac{4(g_\psi g_\chi)^2}{(\mu^2-t)^2}
(p_1\cdot p_3+m_\psi^2)(p_2\cdot p_4+m_\chi^2).
$$

Since

$$
p_1\cdot p_3=m_\psi^2-\frac{t}{2},
\qquad
p_2\cdot p_4=m_\chi^2-\frac{t}{2},
$$

we get the compact invariant result

$$
\overline{|\mathcal M_t|^2}
=
\frac{(g_\psi g_\chi)^2}{(\mu^2-t)^2}
(4m_\psi^2-t)(4m_\chi^2-t).
$$

This is a good place to check dimensions. In four dimensions, $g_\psi$ and $g_\chi$ are dimensionless, and $\overline{|\mathcal M|^2}$ is dimensionless.

## Center-of-momentum cross section

The two-body formula gives

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}\frac{|\mathbf p_f|}{|\mathbf p_i|}
\overline{|\mathcal M_t|^2}.
$$

For elastic two-body scattering with the same particle masses before and after the collision,

$$
|\mathbf p_f|=|\mathbf p_i|,
$$

so

$$
\frac{d\sigma}{d\Omega}
=
\frac{(g_\psi g_\chi)^2}{64\pi^2s}
\frac{(4m_\psi^2-t)(4m_\chi^2-t)}{(\mu^2-t)^2}.
$$

In the center-of-momentum frame, the momentum transfer is

$$
t=-2|\mathbf p|^2(1-\cos\theta)
=-4|\mathbf p|^2\sin^2\frac{\theta}{2}.
$$

The exchanged scalar therefore enhances forward scattering when $\mu$ is small. If $\mu\neq0$, the forward limit is finite; if $\mu=0$, the familiar long-range singularity appears.

## Nonrelativistic limit and the Yukawa potential

For small three-momenta compared with the fermion masses,

$$
\overline u(p')u(p)=2m+O(|\mathbf p|^2/m),
$$

and

$$
t\simeq-\mathbf q^2.
$$

The amplitude becomes

$$
\mathcal M_{\rm NR}
\simeq
4m_\psi m_\chi\frac{g_\psi g_\chi}{\mathbf q^2+\mu^2}.
$$

The nonrelativistic Born matching for two heavy particles is

$$
\mathcal M_{\rm NR}=-4m_\psi m_\chi\,\widetilde V(\mathbf q),
$$

so

$$
\widetilde V(\mathbf q)
=-\frac{g_\psi g_\chi}{\mathbf q^2+\mu^2}.
$$

Fourier transforming gives

$$
V(r)
=-g_\psi g_\chi\int\frac{d^3\mathbf q}{(2\pi)^3}
\frac{e^{i\mathbf q\cdot\mathbf r}}{\mathbf q^2+\mu^2}
=-\frac{g_\psi g_\chi}{4\pi}\frac{e^{-\mu r}}{r}.
$$

The range is set by $\mu^{-1}$. A heavier exchanged scalar produces a shorter-range force. In the limit $\mu\to0$, the potential becomes Coulombic in shape but remains attractive for same-sign scalar couplings.

## Useful limits

### Heavy exchanged scalar

When the exchanged scalar is much heavier than the momentum transfer,

$$
|t|\ll\mu^2,
$$

the propagator collapses to a local interaction:

$$
\mathcal M_t
\simeq
\frac{g_\psi g_\chi}{\mu^2}
\left[\overline u_\psi(p_3)u_\psi(p_1)\right]
\left[\overline u_\chi(p_4)u_\chi(p_2)\right].
$$

This is the tree-level matching intuition behind contact four-fermion operators.

### Massless exchanged scalar

When $\mu=0$,

$$
\mathcal M_t
= -\frac{g_\psi g_\chi}{t}
\left[\overline u_\psi(p_3)u_\psi(p_1)\right]
\left[\overline u_\chi(p_4)u_\chi(p_2)\right],
$$

and the center-of-momentum cross section becomes forward singular as $t\to0$. This is not a ultraviolet problem; it is the infrared signature of an infinite-range force.

### Identical fermions

If the two external fermions are the same species, the final state can be obtained in two indistinguishable ways. The tree amplitude then contains both a direct and an exchange term, schematically

$$
\mathcal M_{\rm identical}
=\mathcal M_t-\mathcal M_u,
$$

with a minus sign from exchanging identical fermions. This page avoids that additional bookkeeping by using distinguishable fermions.

## Common pitfalls

**Forgetting the spinor bilinears.** Scalar exchange is not just $g^2/(\mu^2-t)$. The external fermion states supply $\overline u(p')u(p)$ factors.

**Putting the potential sign directly into the propagator.** The attractive sign of the Yukawa potential follows after Born matching. Do not read it off from the scalar propagator alone.

**Confusing scalar exchange with photon exchange.** Same-sign scalar charges attract; same-sign electric charges repel. The difference comes from the Lorentz structure of the exchanged field and the vertex.

**Using identical-particle formulas for distinguishable scattering.** The calculation here has no $u$-channel exchange term and no final-state $1/2!$. Those appear only when the physical final particles are indistinguishable.

**Dropping the exchanged mass in the wrong limit.** Setting $\mu=0$ changes the long-distance physics. It is not a harmless small correction in the forward-scattering region.

## Relations to other pages

- [Yukawa Tree Amplitudes](/perturbative-qft/tree-level-scattering/yukawa-tree-amplitudes/) gives the general tree-level diagrammatics for Yukawa interactions.
- [QED Electron–Muon Scattering](/perturbative-qft/model-calculation-library/qed-electron-muon-scattering/) compares scalar exchange with vector exchange in a closely parallel process.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) explains the cross-section formula used here.
- [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) gives the spin sums used to turn bilinears into traces.
- [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/) and [Self-Energy Diagrams](/perturbative-qft/loop-expansion-regularization/self-energy-diagrams/) are the next steps once scalar exchange is corrected by loops.
- [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/) explains how the couplings and masses in this model are interpreted beyond tree level.

## Research status

- **Established:** The tree-level scalar-exchange amplitude, its spin average, and its nonrelativistic Yukawa-potential limit are standard perturbative QFT results.
- **Active:** Realistic scalar exchange appears inside richer settings: Higgs exchange, nuclear effective theories, dark-sector mediators, finite-density systems, and bound-state calculations.
- **Convention-dependent:** The overall sign of intermediate $i\mathcal M$ expressions follows the interaction-sign convention. The potential sign quoted here follows the Lagrangian and Born-matching conventions used on this page.

## Exercises

### Exercise 1: Trace derivation

Starting from

$$
\overline{|\mathcal M_t|^2}
=
\frac{(g_\psi g_\chi)^2}{(\mu^2-t)^2}
\frac14
\operatorname{tr}\left[(p_3\!\!\!/+m_\psi)(p_1\!\!\!/+m_\psi)\right]
\operatorname{tr}\left[(p_4\!\!\!/+m_\chi)(p_2\!\!\!/+m_\chi)\right],
$$

show that

$$
\overline{|\mathcal M_t|^2}
=
\frac{(g_\psi g_\chi)^2}{(\mu^2-t)^2}
(4m_\psi^2-t)(4m_\chi^2-t).
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\operatorname{tr}\left[(a\!\!\!/+m)(b\!\!\!/+m)\right]
=4(a\cdot b+m^2).
$$

Thus

$$
\overline{|\mathcal M_t|^2}
=
\frac{4(g_\psi g_\chi)^2}{(\mu^2-t)^2}
(p_1\cdot p_3+m_\psi^2)(p_2\cdot p_4+m_\chi^2).
$$

Since

$$
t=(p_1-p_3)^2=2m_\psi^2-2p_1\cdot p_3,
$$

we have

$$
p_1\cdot p_3+m_\psi^2=2m_\psi^2-\frac{t}{2}.
$$

The same argument gives

$$
p_2\cdot p_4+m_\chi^2=2m_\chi^2-\frac{t}{2}.
$$

Multiplying these factors gives the stated expression.

</details>

### Exercise 2: Yukawa potential integral

Show that

$$
\int\frac{d^3\mathbf q}{(2\pi)^3}
\frac{e^{i\mathbf q\cdot\mathbf r}}{\mathbf q^2+\mu^2}
=\frac{e^{-\mu r}}{4\pi r}.
$$

<details>
<summary><strong>Solution</strong></summary>

Choose the $z$ axis along $\mathbf r$. Then

$$
\int d\Omega\,e^{i|\mathbf q|r\cos\theta}
=4\pi\frac{\sin(qr)}{qr}.
$$

The integral becomes

$$
\frac{1}{2\pi^2r}\int_0^\infty dq\,
\frac{q\sin(qr)}{q^2+\mu^2}.
$$

The standard contour integral gives

$$
\int_0^\infty dq\,
\frac{q\sin(qr)}{q^2+\mu^2}
=\frac{\pi}{2}e^{-\mu r},
$$

so the result is

$$
\frac{e^{-\mu r}}{4\pi r}.
$$

</details>

### Exercise 3: Heavy mediator limit

For $|t|\ll\mu^2$, expand the scalar propagator and identify the leading local four-fermion operator.

<details>
<summary><strong>Solution</strong></summary>

The propagator factor in the amplitude is

$$
\frac{g_\psi g_\chi}{\mu^2-t}
=\frac{g_\psi g_\chi}{\mu^2}
\left(1+\frac{t}{\mu^2}+\cdots\right).
$$

The leading amplitude is generated by a local four-fermion operator of the form

$$
\mathcal L_{\rm eff}
\supset
\frac{g_\psi g_\chi}{\mu^2}
(\overline\psi\psi)(\overline\chi\chi),
$$

up to the overall sign convention used when integrating out the scalar field. Higher powers of $t/\mu^2$ correspond to derivative-suppressed operators.

</details>

### Exercise 4: Massless forward singularity

Set $\mu=0$ and show that the cross section is singular as $\theta\to0$ in the center-of-momentum frame.

<details>
<summary><strong>Solution</strong></summary>

In the center-of-momentum frame,

$$
t=-4|\mathbf p|^2\sin^2\frac{\theta}{2}.
$$

For $\mu=0$, the denominator in the spin-averaged amplitude is $t^2$. Therefore the cross section contains

$$
\frac{1}{t^2}
=\frac{1}{16|\mathbf p|^4\sin^4(\theta/2)}.
$$

As $\theta\to0$, this diverges like $\theta^{-4}$.

</details>

## References

- S. Coleman, *Lectures on Quantum Field Theory*, chs. 10–12 and 21, for scalar exchange model calculations, scattering conventions, spinor Feynman rules, and spin averaging.
- M. Srednicki, *Quantum Field Theory*, §§45–48 and the Yukawa-theory loop examples, for Dirac-field Feynman rules, spin sums, and fermion scattering technology.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5, 7, and 13, for cross sections, Feynman rules, and spinor trace methods.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 4–5, for tree-level fermion scattering and the relation between exchange amplitudes and potentials.

## Version history

- **2026-06-13:** Initial model-calculation page for distinguishable fermion scattering by scalar exchange, including the spin-averaged amplitude, cross section, and Yukawa-potential limit.
