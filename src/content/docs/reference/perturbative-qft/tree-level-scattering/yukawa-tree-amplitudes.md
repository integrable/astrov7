---
title: "Yukawa Tree Amplitudes"
description: "A worked guide to tree-level amplitudes in Yukawa theory, including scalar exchange, fermion exchange, external spinors, identical-fermion signs, and spin-summed checks."
sidebar:
  label: "Yukawa Tree Amplitudes"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§41–48; Coleman 2019, chs. 10–12 and 21; Weinberg 1995, Vol. I, chs. 5–6; Schwartz 2014, chs. 7 and 10–13"
topics:
  - Yukawa theory
  - tree amplitudes
  - fermion scattering
  - scalar exchange
  - spin sums
canonicalTopics:
  - yukawa-tree-amplitudes
  - scalar-mediated-scattering
  - fermion-exchange-diagrams
  - external-spinor-rules
researchStatus:
  established:
    - "Tree-level Yukawa amplitudes are standard textbook applications of Dirac external spinors, scalar and fermion propagators, and LSZ-reduced Feynman rules."
  active:
    - "The same tree structures become subtler in chiral gauge theories, spontaneously broken theories, infrared-sensitive massless limits, bound-state problems, and precision observables; those refinements belong to later pages."
---

## Summary

A **Yukawa interaction** couples a scalar field to a fermion bilinear. For a real scalar $\phi$ and a Dirac fermion $\psi$, the simplest model is

$$
\mathcal L
=
\overline\psi(i\gamma^\mu\partial_\mu-M)\psi
+\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m_\phi^2\phi^2
-g\phi\overline\psi\psi.
$$

The Yukawa vertex is

$$
{\phi\overline\psi\psi\text{ vertex:}\quad -ig.}
$$

Together with the scalar and fermion propagators,

$$
\frac{i}{k^2-m_\phi^2+i\epsilon},
\qquad
\frac{i(k\!\!\!/+M)}{k^2-M^2+i\epsilon},
$$

this vertex gives the first spin-dependent tree amplitudes in QFT. For example, for two distinguishable fermions $\psi_a$ and $\psi_b$ exchanging a scalar,

$$
\mathcal M_t
=
-g_ag_b\,
\frac{[\overline u_a(p_3)u_a(p_1)]
[\overline u_b(p_4)u_b(p_2)]}
{t-m_\phi^2+i\epsilon}.
$$

For scalar–fermion scattering,

$$
\mathcal M_{\psi\phi\to\psi\phi}
=
-g^2\overline u(p_3)
\left[
\frac{(p_1+p_2)\!\!\!/+M}{s-M^2+i\epsilon}
+
\frac{(p_1-p_4)\!\!\!/+M}{u-M^2+i\epsilon}
\right]
u(p_1).
$$

The new lesson, compared with scalar tree amplitudes, is not the topology of the diagrams. It is the **fermion-line bookkeeping**: external spinors, ordered gamma-matrix strings, spin sums, and signs from exchanging identical fermions.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Yukawa vertex, scalar exchange, and fermion exchange diagrams](/figures/perturbative-qft/yukawa-tree-amplitudes.svg)

<figcaption>

Yukawa tree amplitudes are built from the local $\phi\overline\psi\psi$ vertex. A scalar propagator mediates fermion–fermion scattering through bilinears such as $\overline u_3u_1$, while scalar–fermion scattering uses an internal fermion propagator and therefore an ordered spinor numerator such as $(p_1+p_2)\!\!\!/+M$.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [External Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/).

For the spinor algebra used below, it is helpful to review the Dirac-field and spinor-technology pages in the Foundations volume.

## Core idea

Yukawa theory is the first tree-level laboratory where amplitudes are no longer just rational functions of $s,t,u$. They also depend on spinor wavefunctions.

The basic dictionary is:

| Object | Momentum-space factor |
|---|---:|
| scalar propagator carrying $k$ | $\displaystyle \frac{i}{k^2-m_\phi^2+i\epsilon}$ |
| fermion propagator carrying $k$ | $\displaystyle \frac{i(k\!\!\!/+M)}{k^2-M^2+i\epsilon}$ |
| Yukawa vertex from $-g\phi\overline\psi\psi$ | $-ig$ |
| incoming fermion | $u_s(p)$ |
| outgoing fermion | $\overline u_s(p)$ |
| incoming antifermion | $\overline v_s(p)$ |
| outgoing antifermion | $v_s(p)$ |

The stripped diagram gives $i\mathcal M$. Thus two Yukawa vertices and one scalar propagator give

$$
(-ig_a)(-ig_b)\frac{i}{t-m_\phi^2+i\epsilon}
=
-i g_ag_b\frac{1}{t-m_\phi^2+i\epsilon},
$$

so the corresponding contribution to $\mathcal M$ has the coefficient

$$
-g_ag_b\frac{1}{t-m_\phi^2+i\epsilon}.
$$

The scalar line does not carry spinor indices. The spinor dependence sits in the external bilinears attached to each fermion line.

## Setup and conventions

We use the qft.org mostly-minus metric and amplitude convention

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The basic Yukawa model is

$$
\mathcal L
=
\overline\psi(i\gamma^\mu\partial_\mu-M)\psi
+\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m_\phi^2\phi^2
-g\phi\overline\psi\psi.
$$

For several fermion species,

$$
\mathcal L_{\rm int}
=-\sum_a g_a\phi\overline\psi_a\psi_a.
$$

External fermions are on shell,

$$
p^2=M^2,
\qquad
(p\!\!\!/-M)u_s(p)=0,
\qquad
\overline u_s(p)(p\!\!\!/-M)=0.
$$

For antifermions,

$$
(p\!\!\!/+M)v_s(p)=0,
\qquad
\overline v_s(p)(p\!\!\!/+M)=0.
$$

The spin sums are

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+M,
\qquad
\sum_s v_s(p)\overline v_s(p)=p\!\!\!/-M.
$$

We use the common normalization

$$
\overline u_s(p)u_{s'}(p)=2M\delta_{ss'},
\qquad
\overline v_s(p)v_{s'}(p)=-2M\delta_{ss'}.
$$

:::note[About signs]
For processes with no identical external fermions, the formulas below follow directly from following each fermion line and multiplying the factors in order. For identical external fermions, there are additional minus signs from exchanging fermionic creation operators or, equivalently, from permuting external fermion fields in Wick contractions. Those signs are physical because they affect interference.
:::

## External spinors as amputated wavefunctions

In scalar theory, a tree amplitude often looks like a product of coupling constants and propagator denominators. In Yukawa theory, each open fermion line becomes a spinor chain.

For a fermion line that enters with momentum $p_1$ and leaves with momentum $p_3$, a scalar Yukawa vertex gives

$$
\overline u(p_3)u(p_1).
$$

For a line involving an incoming antifermion with momentum $p_2$ and an outgoing antifermion with momentum $p_4$, the corresponding scalar bilinear is conventionally written

$$
\overline v(p_2)v(p_4),
$$

because fermion flow runs opposite to the physical antifermion arrow.

For a line containing an internal fermion propagator, the factors multiply in the order encountered along the fermion line. For example,

$$
\overline u(p_3)
\frac{i(q\!\!\!/+M)}{q^2-M^2+i\epsilon}
u(p_1)
$$

is not a scalar propagator times a number; it is a matrix numerator sandwiched between external spinors.

## Scalar exchange between distinguishable fermions

Consider

$$
\psi_a(p_1)+\psi_b(p_2)\to\psi_a(p_3)+\psi_b(p_4),
$$

where the species $a$ and $b$ are distinguishable. The scalar carries momentum

$$
q=p_1-p_3=p_4-p_2,
\qquad
q^2=t.
$$

The tree diagram gives

$$
i\mathcal M_t
=
[\overline u_a(p_3)(-ig_a)u_a(p_1)]
\frac{i}{t-m_\phi^2+i\epsilon}
[\overline u_b(p_4)(-ig_b)u_b(p_2)].
$$

Therefore

$$
\mathcal M_t
=
-g_ag_b\,
\frac{[\overline u_a(p_3)u_a(p_1)]
[\overline u_b(p_4)u_b(p_2)]}
{t-m_\phi^2+i\epsilon}.
$$

This is the relativistic ancestor of the Yukawa potential. In the nonrelativistic limit,

$$
\overline u(p')u(p)\simeq 2M,
\qquad
 t\simeq-\mathbf q^2,
$$

so

$$
\mathcal M_t
\simeq
\frac{4M_aM_b g_ag_b}{\mathbf q^2+m_\phi^2}.
$$

Using the Born relation

$$
\widetilde V(\mathbf q)=-\frac{\mathcal M}{4M_aM_b},
$$

gives

$$
\widetilde V(\mathbf q)
=-\frac{g_ag_b}{\mathbf q^2+m_\phi^2},
$$

and hence

$$
V(r)=-\frac{g_ag_b}{4\pi}\frac{e^{-m_\phi r}}{r}.
$$

For $g_ag_b>0$, the force is attractive. That sign is a useful check: scalar exchange attracts like Yukawa charges, unlike photon exchange between like electric charges.

## Spin-summed scalar exchange

The distinguishable-fermion exchange amplitude is also a good place to practice spin sums. Average over two initial spin states for each fermion and sum over final spins. If the two fermions scatter elastically with masses $M_a$ and $M_b$, then

$$
\overline{|\mathcal M_t|^2}
=
\frac{g_a^2g_b^2}{(t-m_\phi^2)^2}
\frac14
\operatorname{tr}[(p_3\!\!\!/+M_a)(p_1\!\!\!/+M_a)]
\operatorname{tr}[(p_4\!\!\!/+M_b)(p_2\!\!\!/+M_b)].
$$

Using

$$
\operatorname{tr}[(a\!\!\!/+M)(b\!\!\!/+M)]
=4(a\cdot b+M^2),
$$

and

$$
t=(p_1-p_3)^2=2M_a^2-2p_1\cdot p_3,
$$

we find

$$
\operatorname{tr}[(p_3\!\!\!/+M_a)(p_1\!\!\!/+M_a)]
=2(4M_a^2-t).
$$

Thus

$$
\overline{|\mathcal M_t|^2}
=
\frac{g_a^2g_b^2(4M_a^2-t)(4M_b^2-t)}
{(t-m_\phi^2)^2}.
$$

This formula assumes distinguishable fermion species and ignores the infinitesimal $i\epsilon$ away from poles. For identical fermions, interference with the exchange diagram must be included before squaring.

## Identical fermion scattering

Now consider

$$
\psi(p_1)+\psi(p_2)\to\psi(p_3)+\psi(p_4)
$$

with identical external fermions. There are two scalar-exchange contractions: a direct $t$-channel graph and an exchange $u$-channel graph. With the external spinor ordering used here,

$$
\begin{aligned}
\mathcal M_{\psi\psi\to\psi\psi}
&=
-g^2\frac{[\overline u(p_3)u(p_1)][\overline u(p_4)u(p_2)]}
{t-m_\phi^2+i\epsilon}
\\
&\quad
+g^2\frac{[\overline u(p_4)u(p_1)][\overline u(p_3)u(p_2)]}
{u-m_\phi^2+i\epsilon}.
\end{aligned}
$$

The relative plus sign in the second line is not a new vertex rule. The raw $u$-channel scalar exchange would again carry the coefficient $-g^2/(u-m_\phi^2)$. The additional minus sign comes from exchanging identical external fermions, so the displayed term has the opposite sign relative to the direct term.

This is the Yukawa analogue of the exchange term in Møller scattering. The minus sign is the diagrammatic shadow of antisymmetry of the two-fermion state.

## Fermion-antifermion scattering

For

$$
\psi(p_1)+\overline\psi(p_2)\to\psi(p_3)+\overline\psi(p_4),
$$

there is a scattering-channel scalar exchange and, for the same fermion species, an annihilation-channel scalar exchange.

The $t$-channel exchange gives

$$
\mathcal M_t
=
-g^2
\frac{[\overline u(p_3)u(p_1)][\overline v(p_2)v(p_4)]}
{t-m_\phi^2+i\epsilon}.
$$

The $s$-channel annihilation graph gives

$$
\mathcal M_s
=
-g^2
\frac{[\overline v(p_2)u(p_1)][\overline u(p_3)v(p_4)]}
{s-m_\phi^2+i\epsilon},
$$

up to the global external-fermion ordering convention used to define the matrix element. The spin-summed cross section is insensitive to an overall common sign, but not to relative signs between interfering diagrams.

## Scalar–fermion scattering

Now consider

$$
\psi(p_1)+\phi(p_2)\to\psi(p_3)+\phi(p_4).
$$

The intermediate particle is a fermion, so the numerator is a Dirac matrix. There are two tree diagrams.

In the $s$ channel,

$$
q_s=p_1+p_2,
\qquad
q_s^2=s,
$$

and

$$
i\mathcal M_s
=(-ig)^2\overline u(p_3)
\frac{i(q_s\!\!\!/+M)}{s-M^2+i\epsilon}u(p_1).
$$

Therefore

$$
\mathcal M_s
=
-g^2\overline u(p_3)
\frac{(p_1+p_2)\!\!\!/+M}{s-M^2+i\epsilon}u(p_1).
$$

In the crossed $u$ channel,

$$
q_u=p_1-p_4=p_3-p_2,
\qquad
q_u^2=u,
$$

so

$$
\mathcal M_u
=
-g^2\overline u(p_3)
\frac{(p_1-p_4)\!\!\!/+M}{u-M^2+i\epsilon}u(p_1).
$$

The full tree amplitude is

$$
\mathcal M_{\psi\phi\to\psi\phi}
=
-g^2\overline u(p_3)
\left[
\frac{(p_1+p_2)\!\!\!/+M}{s-M^2+i\epsilon}
+
\frac{(p_1-p_4)\!\!\!/+M}{u-M^2+i\epsilon}
\right]u(p_1).
$$

This formula is the scalar-Yukawa cousin of Compton scattering in QED. The difference is that scalar external legs contribute no polarization vectors and no gamma matrices at the vertices.

## Crossing viewpoint

The same Yukawa vertex generates many related processes:

$$
\psi\psi\to\psi\psi,
\qquad
\psi\overline\psi\to\psi\overline\psi,
\qquad
\psi\phi\to\psi\phi,
\qquad
\psi\overline\psi\to\phi\phi.
$$

They are related by crossing, but the spinors do not cross by simply changing $p\to-p$ inside a scalar formula. Crossing a fermion to the other side of the reaction also changes whether the external wavefunction is a $u$, $\overline u$, $v$, or $\overline v$ spinor, and it may introduce fermion-ordering signs.

A practical rule is: do crossing at the level of external states and spinor wavefunctions, not by treating fermion amplitudes as scalar functions with labels erased.

This is one reason tree-level Yukawa theory is pedagogically useful: it is simple enough to compute by hand, but already honest about the spinor bookkeeping used in QED, weak interactions, and QCD.

## Common pitfalls

**Writing $\mathcal M=-ig$ for a Yukawa vertex.** A diagram contributes to $i\mathcal M$. The vertex factor is $-ig$, so a one-vertex contribution would correspond to a real coefficient $-g$ in $\mathcal M$, after stripping the overall $i$.

**Dropping the order of spinor matrices.** Fermion propagator numerators and gamma matrices are matrices. The order along a fermion line matters.

**Forgetting identical-fermion exchange signs.** Two diagrams related by exchanging identical external fermions interfere with a relative minus sign. This is not optional antisymmetrization added after the fact; it is already present in the Wick-contraction algebra.

**Using scalar crossing rules for fermions.** Crossing a fermion changes external spinor type. A crossed outgoing fermion becomes an incoming antifermion with a $v$-type wavefunction, not a $u$ spinor with negative energy.

**Confusing the mediator mass with the external fermion mass.** In scalar exchange, the pole denominator is $t-m_\phi^2$. In scalar–fermion scattering, the exchanged fermion pole is $s-M^2$ or $u-M^2$.

**Interpreting an off-shell internal fermion as a physical particle.** The internal propagator momentum is fixed by external kinematics, but it is not generally on shell. It is an algebraic variable inside the amplitude, not an observed intermediate particle.

## Relations to other pages

- [Scalar Tree Amplitudes](/perturbative-qft/tree-level-scattering/scalar-tree-amplitudes/) gives the spinless contact and exchange calculations that this page generalizes.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) fixes the $s,t,u$ conventions used in the exchange denominators.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains how propagators, vertices, and total delta functions are assigned.
- [External Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/) explains why external spinors appear after LSZ amputation.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains how related processes are analytically connected.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) adds vector currents, photon polarizations, and Ward-identity checks.
- Later pages on phase space and spin averaging turn these amplitudes into cross sections and decay rates.

## Research status

- **Established:** The tree-level Yukawa amplitudes on this page are standard perturbative consequences of the Yukawa interaction, Dirac external spinors, and scalar or fermion propagators.
- **Convention-dependent:** Overall signs depend on the interaction-sign convention and on the external-fermion ordering convention. Relative signs between interfering diagrams are physical once those conventions are fixed.
- **Active:** Yukawa interactions remain central in Higgs physics, flavor physics, chiral EFT, finite-density QFT, and beyond-Standard-Model model building. Precision predictions require loop corrections, renormalization, gauge consistency, infrared-safe observables, and often unstable-particle or bound-state treatments.

## Exercises

### Exercise 1: Yukawa vertex sign

Starting from

$$
\mathcal L_{\rm int}=-g\phi\overline\psi\psi,
$$

show that the momentum-space Yukawa vertex is $-ig$ in the conventions of this page.

<details>
<summary><strong>Solution</strong></summary>

In the Lorentzian path-integral expansion, an interaction insertion contributes

$$
i\int d^4x\,\mathcal L_{\rm int}
=
-i g\int d^4x\,\phi\overline\psi\psi.
$$

After Fourier transforming the fields, the integral over $x$ gives the vertex momentum-conservation delta function. The local factor multiplying that delta function is therefore

$$
-ig.
$$

Equivalently, in the interaction-picture Dyson expansion, $H_I=-\int d^3\mathbf x\,\mathcal L_{\rm int}$ for this non-derivative interaction, so $-i\int dt\,H_I=i\int d^4x\,\mathcal L_{\rm int}$ gives the same factor.

</details>

### Exercise 2: Distinguishable fermion exchange

For two distinguishable fermions with couplings $g_a$ and $g_b$, derive

$$
\mathcal M_t
=
-g_ag_b\,
\frac{[\overline u_a(p_3)u_a(p_1)]
[\overline u_b(p_4)u_b(p_2)]}
{t-m_\phi^2+i\epsilon}.
$$

<details>
<summary><strong>Solution</strong></summary>

The diagram has two Yukawa vertices and one scalar propagator. The first fermion line gives

$$
\overline u_a(p_3)(-ig_a)u_a(p_1),
$$

and the second gives

$$
\overline u_b(p_4)(-ig_b)u_b(p_2).
$$

The exchanged scalar carries

$$
q=p_1-p_3,
\qquad
q^2=t,
$$

so its propagator is

$$
\frac{i}{t-m_\phi^2+i\epsilon}.
$$

Multiplying gives

$$
i\mathcal M_t
=(-ig_a)(-ig_b)\frac{i}{t-m_\phi^2+i\epsilon}
[\overline u_a(p_3)u_a(p_1)]
[\overline u_b(p_4)u_b(p_2)].
$$

Since $(-ig_a)(-ig_b)i=-ig_ag_b$, we get the stated expression for $\mathcal M_t$.

</details>

### Exercise 3: Spin-summed scalar exchange

Using

$$
\sum_s u_s(p)\overline u_s(p)=p\!\!\!/+M,
$$

show that for distinguishable elastic scattering,

$$
\overline{|\mathcal M_t|^2}
=
\frac{g_a^2g_b^2(4M_a^2-t)(4M_b^2-t)}
{(t-m_\phi^2)^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

Begin with

$$
\mathcal M_t
=
-g_ag_b\frac{(\overline u_3u_1)(\overline u_4u_2)}{t-m_\phi^2}.
$$

Averaging over two initial spins for each fermion gives a factor $1/4$. Summing over final spins gives

$$
\overline{|\mathcal M_t|^2}
=
\frac{g_a^2g_b^2}{(t-m_\phi^2)^2}\frac14
\operatorname{tr}[(p_3\!\!\!/+M_a)(p_1\!\!\!/+M_a)]
\operatorname{tr}[(p_4\!\!\!/+M_b)(p_2\!\!\!/+M_b)].
$$

The trace identity

$$
\operatorname{tr}[(a\!\!\!/+M)(b\!\!\!/+M)]=4(a\cdot b+M^2)
$$

and elastic kinematics give

$$
p_1\cdot p_3=M_a^2-\frac{t}{2},
\qquad
p_2\cdot p_4=M_b^2-\frac{t}{2}.
$$

Therefore the traces are

$$
2(4M_a^2-t),
\qquad
2(4M_b^2-t),
$$

and the factor $1/4$ cancels the factor $2\cdot2$, giving the result.

</details>

### Exercise 4: Yukawa potential

Use the nonrelativistic limit of scalar exchange to derive

$$
V(r)=-\frac{g_ag_b}{4\pi}\frac{e^{-m_\phi r}}{r}.
$$

<details>
<summary><strong>Solution</strong></summary>

In the nonrelativistic limit,

$$
\overline u(p')u(p)\simeq 2M,
\qquad
 t\simeq-\mathbf q^2.
$$

The exchange amplitude becomes

$$
\mathcal M_t
\simeq
-g_ag_b\frac{(2M_a)(2M_b)}{-\mathbf q^2-m_\phi^2}
=
\frac{4M_aM_b g_ag_b}{\mathbf q^2+m_\phi^2}.
$$

The Born relation is

$$
\widetilde V(\mathbf q)=-\frac{\mathcal M_t}{4M_aM_b},
$$

so

$$
\widetilde V(\mathbf q)
=-\frac{g_ag_b}{\mathbf q^2+m_\phi^2}.
$$

Fourier transforming gives

$$
V(r)=-g_ag_b\int\frac{d^3\mathbf q}{(2\pi)^3}
\frac{e^{i\mathbf q\cdot\mathbf r}}{\mathbf q^2+m_\phi^2}
=-\frac{g_ag_b}{4\pi}\frac{e^{-m_\phi r}}{r}.
$$

</details>

### Exercise 5: Scalar–fermion scattering channels

For

$$
\psi(p_1)+\phi(p_2)\to\psi(p_3)+\phi(p_4),
$$

identify the intermediate fermion momenta in the two tree diagrams and derive the displayed $s$- and $u$-channel amplitude.

<details>
<summary><strong>Solution</strong></summary>

At the first diagram, the incoming fermion absorbs the incoming scalar before emitting the outgoing scalar. The internal fermion momentum is

$$
q_s=p_1+p_2,
\qquad
q_s^2=s.
$$

This gives

$$
\mathcal M_s
=
-g^2\overline u(p_3)
\frac{(p_1+p_2)\!\!\!/+M}{s-M^2+i\epsilon}u(p_1).
$$

In the crossed diagram, the incoming fermion emits the outgoing scalar first. The internal momentum is

$$
q_u=p_1-p_4=p_3-p_2,
\qquad
q_u^2=u.
$$

This gives

$$
\mathcal M_u
=
-g^2\overline u(p_3)
\frac{(p_1-p_4)\!\!\!/+M}{u-M^2+i\epsilon}u(p_1).
$$

Adding the two terms gives

$$
\mathcal M
=
-g^2\overline u(p_3)
\left[
\frac{(p_1+p_2)\!\!\!/+M}{s-M^2+i\epsilon}
+
\frac{(p_1-p_4)\!\!\!/+M}{u-M^2+i\epsilon}
\right]u(p_1).
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§41–48, for LSZ reduction and Feynman rules for spin-one-half fields, spin sums, and spin-averaged cross sections.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 10–12 and 21, for scalar-mediated scattering examples, Mandelstam variables, phase space, and fermion Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 5–6, for causal Dirac fields and the general Feynman-rule derivation.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 7 and 10–13, for Feynman rules, spinors, QED-adjacent examples, and spin sums.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. II.1–II.6 and appendix C, for a compact spinor and Feynman-rule overview.

## Version history

- **2026-06-12:** Initial polished draft. Added scalar-exchange, identical-fermion, fermion-antifermion, scalar–fermion, spin-summed, and nonrelativistic-potential checks, with one compact TikZ figure.
