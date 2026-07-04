---
title: "Non-Abelian Tree Amplitudes"
description: "A worked guide to tree-level amplitudes in non-Abelian gauge theory, including color factors, gluon self-interactions, quark scattering, color ordering, and Ward-identity checks."
sidebar:
  label: "Non-Abelian Tree Amplitudes"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§69–72 and §81; Weinberg, Vol. II, chs. 15–17; Coleman 2019, chs. 46–47; Schwartz 2014, chs. 25–27"
topics:
  - non-Abelian gauge theory
  - Yang–Mills theory
  - tree amplitudes
  - color factors
  - gluon self-interactions
  - Ward identities
canonicalTopics:
  - non-abelian-tree-amplitudes
  - yang-mills-tree-amplitudes
  - color-factors-in-scattering
  - gluon-self-interactions
  - color-ordering-preview
researchStatus:
  established:
    - "Tree-level non-Abelian gauge-theory amplitudes, their color factors, and their gauge-invariance checks are standard consequences of Yang–Mills perturbation theory."
  active:
    - "Modern amplitude methods reorganize these same tree amplitudes using color ordering, recursion, color–kinematics duality, and double-copy structures; those refinements belong to later pages."
---

## Summary

Non-Abelian tree amplitudes are the first place where gauge theory stops looking like many independent copies of QED. A gluon couples to colored matter, but it also carries color itself. Consequently, gluons interact with gluons already at tree level.

For a Yang–Mills theory with Hermitian generators

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

the quark–gluon vertex in qft.org conventions is

$$
{\text{quark–gluon vertex:}\quad -ig\gamma^\mu T^a,}
$$

and the Feynman-gauge gluon propagator is

$$
\text{gluon propagator:}\quad
\frac{-i\eta_{\mu\nu}\delta^{ab}}{k^2+i\epsilon}.
$$

The simplest non-Abelian amplitude is quark scattering by single-gluon exchange,

$$
q_i(p_1)+q'_k(p_2)\to q_j(p_3)+q'_l(p_4),
$$

where the flavors are distinct. With $t=(p_1-p_3)^2$,

$$
\mathcal M_t
=
\frac{g^2}{t+i\epsilon}
\left[\overline u(p_3)\gamma^\mu u(p_1)\right]
\left[\overline u(p_4)\gamma_\mu u(p_2)\right]
(T^a)_{ji}(T^a)_{lk}.
$$

The formula looks like QED photon exchange, but the color factor is a matrix structure, not a number. In processes with several gluons, the order of color matrices matters, and separate diagrams are usually not gauge invariant by themselves.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Tree-level non-Abelian amplitudes: quark-gluon vertex, gluon self-interactions, and color flow](/figures/perturbative-qft/non-abelian-tree-amplitudes.svg)

<figcaption>

Non-Abelian tree amplitudes combine ordinary spinor and polarization kinematics with color algebra. The quark–gluon vertex carries a generator $T^a$, while the three- and four-gluon vertices carry structure constants $f^{abc}$. Gluon self-interactions are the diagrammatic signature that the gauge bosons themselves are charged under the gauge group.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/). The next page, [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), explains how to sum over external gluon polarizations in squared amplitudes.

For background on gauge redundancy and Yang–Mills fields, review the corresponding pages in the Foundations and Gauge Theories volumes.

## Core idea

A non-Abelian amplitude has two intertwined pieces:

$$
\text{amplitude}
=
\text{color algebra}
\times
\text{Lorentz/spin/helicity kinematics}.
$$

In QED the photon is neutral, so tree amplitudes are built from charged currents connected by photon propagators. In Yang–Mills theory the gauge bosons also carry the gauge charge. The covariant derivative and field strength are nonlinear, and this nonlinearity produces three-gluon and four-gluon vertices.

The new habits are:

| Habit | Why it matters |
|---|---|
| Keep color indices explicit until the end. | Color matrices do not commute. |
| Sum diagrams before checking gauge invariance. | Ward identities usually hold only for gauge-invariant sets of diagrams. |
| Distinguish full color-dressed amplitudes from color-ordered partial amplitudes. | Color decomposition separates algebra from kinematics. |
| Average over initial colors and physical polarizations only when computing probabilities. | The amplitude itself is color- and polarization-resolved. |
| Do not add ghost external states. | Ghosts cancel unphysical internal gauge modes, but they are not asymptotic particles. |

At tree level, this page uses the full color-dressed rules. Later pages reorganize the same information into color ordering, spinor-helicity variables, on-shell recursion, and unitarity methods.

## Setup and conventions

We use the qft.org mostly-minus metric and amplitude convention

$$
\langle f|iT|i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The gauge algebra has Hermitian generators,

$$
[T^a,T^b]=if^{abc}T^c,
$$

and for the fundamental representation of $SU(N)$ we use

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

Useful invariants are

$$
T^aT^a=C_F\mathbf 1,
\qquad
f^{acd}f^{bcd}=C_A\delta^{ab},
$$

with

$$
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N
\qquad
\text{for }SU(N).
$$

The covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
$$

so

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a,
$$

with

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

The matter Lagrangian is

$$
\mathcal L_\psi
=
\overline\psi(i\gamma^\mu D_\mu-m)\psi,
$$

and the Yang–Mills kinetic term is

$$
\mathcal L_{\rm YM}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}.
$$

Expanding the matter term gives

$$
\mathcal L_{\psi,\rm int}
=
-g\overline\psi\gamma^\mu A_\mu^aT^a\psi,
$$

hence the quark–gluon vertex is

$$
{-ig\gamma^\mu T^a.}
$$

In Feynman gauge, the gluon propagator is

$$
\frac{-i\eta_{\mu\nu}\delta^{ab}}{k^2+i\epsilon}.
$$

The three-gluon vertex, with all momenta incoming and labels $(a,\mu,p)$, $(b,\nu,q)$, $(c,\rho,r)$, is

$$
V^{abc}_{\mu\nu\rho}(p,q,r)
=
gf^{abc}
\left[
\eta_{\mu\nu}(p-q)_\rho
+\eta_{\nu\rho}(q-r)_\mu
+\eta_{\rho\mu}(r-p)_\nu
\right].
$$

The four-gluon vertex is proportional to $-ig^2$ times two metric tensors and two structure constants. It contributes already to $gg\to gg$. The exact index expression is easy to mistype and should always be checked against the convention for $F_{\mu\nu}^a$ before importing formulas from another source.

:::note[Convention warning]
Some books use $D_\mu=\partial_\mu-igA_\mu^aT^a$. That flips the sign of the quark–gluon vertex and the odd-gluon vertices relative to the convention above. Physical amplitudes are unchanged if all rules are translated together.
:::

## Color algebra at tree level

Color factors are not decorations. They decide which processes exist and how probabilities scale with $N$.

For fundamental $SU(N)$ generators,

$$
(T^a)_{ij}(T^a)_{kl}
=
\frac12\left(
\delta_{il}\delta_{jk}
-\frac1N\delta_{ij}\delta_{kl}
\right).
$$

This identity is the color analogue of resolving a product into exchange channels. In quark scattering it says that single-gluon exchange can reshuffle color between the two fermion lines, with a subtraction that removes the singlet part because $SU(N)$ generators are traceless.

For adjoint indices,

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

In QCD, $N=3$, so

$$
C_F=\frac43,
\qquad
C_A=3.
$$

These constants are everywhere in non-Abelian perturbation theory: tree-level color sums, one-loop beta functions, soft-gluon radiation, splitting functions, and large-$N$ counting.

## Distinguishable quark scattering

Consider two distinct quark flavors,

$$
q_i(p_1,s_1)+q'_k(p_2,s_2)\to q_j(p_3,s_3)+q'_l(p_4,s_4).
$$

There is one tree diagram: $t$-channel gluon exchange. Let

$$
q=p_1-p_3=p_4-p_2,
\qquad
q^2=t.
$$

The diagram gives

$$
\begin{aligned}
i\mathcal M_t
&=
\left[\overline u(p_3)(-ig\gamma^\mu T^a)u(p_1)\right]
\frac{-i\eta_{\mu\nu}\delta^{ab}}{t+i\epsilon}
\left[\overline u(p_4)(-ig\gamma^\nu T^b)u(p_2)\right] \\
&=
i\frac{g^2}{t+i\epsilon}
\left[\overline u(p_3)\gamma^\mu u(p_1)\right]
\left[\overline u(p_4)\gamma_\mu u(p_2)\right]
(T^a)_{ji}(T^a)_{lk}.
\end{aligned}
$$

Therefore

$$
\mathcal M_t
=
\frac{g^2}{t+i\epsilon}
J_1^\mu J_{2\mu}
(T^a)_{ji}(T^a)_{lk},
$$

where

$$
J_1^\mu=\overline u(p_3)\gamma^\mu u(p_1),
\qquad
J_2^\mu=\overline u(p_4)\gamma^\mu u(p_2).
$$

The kinematic structure is the same as photon exchange. The difference is the color matrix product.

For later cross-section calculations, one often needs the color average and sum

$$
\frac{1}{N^2}
\sum_{i,j,k,l}
\left|(T^a)_{ji}(T^a)_{lk}\right|^2
=
\frac{N^2-1}{4N^2}.
$$

For $SU(3)$, this is $2/9$.

## Identical quarks

For identical quark flavors,

$$
q_i(p_1)+q_k(p_2)\to q_j(p_3)+q_l(p_4),
$$

there are two diagrams. One connects $1\to3$ and $2\to4$ through $t$-channel exchange. The other connects $1\to4$ and $2\to3$ through $u$-channel exchange. Because the external fermions are identical, the two assignments enter with a relative minus sign:

$$
\mathcal M_{qq\to qq}
=
\mathcal M_t-\mathcal M_u.
$$

The $u$-channel term uses

$$
u=(p_1-p_4)^2,
$$

and color factor

$$
(T^a)_{li}(T^a)_{jk}
$$

if the spinor current assignments are $1\to4$ and $2\to3$.

This is the same fermion-exchange sign that appears in QED or Yukawa theory, but now the $t$- and $u$-channel color factors are different. The interference between them is physically important.

## Quark-antiquark annihilation into gluons

The process

$$
q\overline q\to gg
$$

is the first simple scattering process where non-Abelian self-interactions are impossible to ignore. There are three tree diagrams:

1. a quark-exchange diagram with one ordering of the two emitted gluons;
2. a quark-exchange diagram with the opposite ordering;
3. an $s$-channel gluon diagram using the three-gluon vertex.

The full amplitude can be written in color-decomposed form as

$$
\mathcal M(1_q,2_{\overline q},3_g,4_g)
=
g^2\left[
(T^{a_3}T^{a_4})_{i_1\overline i_2}
A(1,3,4,2)
+
(T^{a_4}T^{a_3})_{i_1\overline i_2}
A(1,4,3,2)
\right].
$$

Here $A(1,3,4,2)$ and $A(1,4,3,2)$ are color-ordered partial amplitudes. They contain spinor wavefunctions, polarization vectors, and propagator denominators. The three-gluon diagram is hidden inside this compact basis: its color factor $f^{a_3a_4c}T^c$ has been rewritten using

$$
[T^{a_3},T^{a_4}]=if^{a_3a_4c}T^c.
$$

This is the first taste of color ordering. It is not merely a notational trick. It separates the noncommuting color matrices from kinematic subamplitudes with fixed cyclic order.

## Pure-gluon amplitudes

Pure Yang–Mills theory has no matter fields, but it still scatters because of the three- and four-gluon vertices. The process

$$
gg\to gg
$$

receives tree contributions from

$$
s\text{-channel},
\qquad
t\text{-channel},
\qquad
u\text{-channel},
\qquad
\text{four-gluon contact}.
$$

No single one of these diagrams is a physical observable. Gauge invariance belongs to the sum.

For $n$ external gluons in the fundamental trace basis, a standard tree-level decomposition is

$$
\mathcal M_n^{\rm tree}(1^{a_1},\ldots,n^{a_n})
=
g^{n-2}
\sum_{\sigma\in S_n/Z_n}
\operatorname{tr}
\left(T^{a_{\sigma(1)}}\cdots T^{a_{\sigma(n)}}\right)
A_n^{\rm tree}(\sigma(1),\ldots,\sigma(n)).
$$

The trace contains color. The partial amplitude $A_n^{\rm tree}$ contains kinematics. For a fixed cyclic ordering, only poles compatible with that ordering appear. This structure is one reason modern amplitude methods are so efficient for gluon scattering.

At the level of this chapter, the practical lesson is simpler:

```txt
Draw all Yang–Mills tree diagrams.
Assign both color and Lorentz factors.
Only then check Ward identities and square the amplitude.
```

## Ward identities at tree level

External gluons have physical transverse polarizations. If a color-dressed tree amplitude is written as

$$
\mathcal M=\epsilon_\mu(k)\mathcal A^\mu(k),
$$

then gauge invariance requires

$$
{k_\mu\mathcal A^\mu(k)=0}
$$

for an external gluon after all diagrams in the gauge-invariant set have been summed.

This statement is the non-Abelian analogue of the QED Ward identity. The difference is that non-Abelian gauge invariance often uses cancellations between matter diagrams and gluon self-interaction diagrams.

For example, in $q\overline q\to gg$, replacing the polarization of one final gluon by its momentum does not annihilate each quark-exchange diagram separately. The unwanted terms cancel only after the two quark-ordering diagrams and the $s$-channel three-gluon diagram are combined with their correct color factors.

:::tip[The fastest tree-level gauge check]
For an external photon or gluon, replace one polarization vector by the corresponding momentum. A correct gauge-invariant tree amplitude should vanish. If it does not, suspect a missing diagram, a wrong color ordering, a sign error in the three-gluon vertex, or a reversed fermion-line convention.
:::

## Abelian limit

A useful sanity check is the Abelian limit. Set

$$
f^{abc}\to0,
$$

and replace the generators by commuting charges. Then the three- and four-gluon vertices disappear. Color ordering collapses because matrices commute. Quark exchange by a gauge boson becomes ordinary QED-like current exchange.

This does not mean QED is literally $SU(N)$ with $N=1$ in all respects. It means that the non-Abelian complications are precisely the noncommutativity of the gauge algebra and the adjoint charge carried by the gauge bosons.

## Squaring amplitudes

Tree amplitudes are usually computed with fixed colors and fixed spins or polarizations. Cross sections require sums over final states and averages over initial states. For an unpolarized, color-averaged process, the structure is

$$
\overline{|\mathcal M|^2}
=
\frac{1}{\text{initial spins}}
\frac{1}{\text{initial colors}}
\sum_{\text{spins, colors}}
|\mathcal M|^2.
$$

For QCD with $SU(3)$:

| External particle | Initial-state average factor |
|---|---:|
| quark spin | $1/2$ |
| quark color | $1/3$ |
| gluon physical polarization | $1/2$ |
| gluon color | $1/8$ |

The spinor sums and polarization sums are independent of the color sums, but all must be applied consistently. The next page develops the polarization and spin-sum technology needed to turn tree amplitudes into cross sections.

## Common pitfalls

**Forgetting gluon self-interactions.** Non-Abelian gauge bosons carry charge. Processes such as $q\overline q\to gg$ and $gg\to gg$ require three- and four-gluon diagrams.

**Treating color factors as numbers too early.** Color matrices do not commute. The order $T^aT^b$ is not the same as $T^bT^a$.

**Checking gauge invariance diagram by diagram.** In non-Abelian theory, individual diagrams are usually gauge-dependent. Ward identities constrain the sum of a gauge-invariant set.

**Confusing color-dressed and color-ordered amplitudes.** A partial amplitude has a fixed color ordering. The physical color-dressed amplitude is a sum over color structures.

**Averaging over final states.** Final spins, colors, and polarizations are summed, not averaged. Initial unresolved quantum numbers are averaged.

**Adding external ghosts.** Ghosts are not physical asymptotic states. They appear in internal loops and in gauge-fixing identities, not as external particles in ordinary scattering experiments.

## Relations to other pages

- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) gives the Abelian baseline for current exchange and Ward identities.
- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains how to sum over external gluon polarizations in squared amplitudes.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) develops the general rule that every vertex, propagator, and external leg contributes a factor.
- [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/) fixes the $s,t,u$ notation used for tree-level scattering.
- [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/) develops gauge fixing, ghosts, Ward identities, Slavnov–Taylor identities, and Yang–Mills Feynman rules in greater depth.
- [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/) reorganizes tree amplitudes using helicity, color ordering, recursion, and generalized factorization.

## Research status

Tree-level Yang–Mills amplitudes are completely standard. Their conventional Feynman-diagram derivation is textbook material, and their gauge invariance follows from the gauge-fixed Yang–Mills construction.

The active research frontier is not whether these amplitudes are correct. It is how best to reorganize them. Color ordering, spinor-helicity variables, BCFW recursion, Cachazo–He–Yuan formulas, color–kinematics duality, positive geometry, and double-copy relations reveal structures that are hidden in the ordinary diagram expansion.

## Exercises

### Exercise 1: Current conservation on a quark line

Let

$$
J^\mu=\overline u(p')\gamma^\mu u(p),
\qquad
q=p-p',
$$

with $p^2=p'^2=m^2$. Show that

$$
q_\mu J^\mu=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Use the Dirac equations

$$
p\!\!\!/u(p)=mu(p),
\qquad
\overline u(p')p'\!\!\!/=m\overline u(p').
$$

Then

$$
\begin{aligned}
q_\mu J^\mu
&=\overline u(p')(p\!\!\!/-p'\!\!\!/)u(p) \\
&=\overline u(p')p\!\!\!/u(p)-\overline u(p')p'\!\!\!/u(p) \\
&=m\overline u(p')u(p)-m\overline u(p')u(p) \\
&=0.
\end{aligned}
$$

This is the tree-level current-conservation identity that removes longitudinal gauge-boson terms from quark-current exchange.

</details>

### Exercise 2: Color factor for distinguishable quark scattering

For $SU(N)$ with

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab},
$$

show that the color average and sum for distinct quark scattering is

$$
\frac{1}{N^2}
\sum_{i,j,k,l}
\left|(T^a)_{ji}(T^a)_{lk}\right|^2
=
\frac{N^2-1}{4N^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The color factor is

$$
C_{ji,lk}=(T^a)_{ji}(T^a)_{lk}.
$$

The summed squared factor is

$$
\sum_{i,j,k,l} C_{ji,lk}C_{ji,lk}^*
=
\sum_{a,b}
\left[\sum_{i,j}(T^a)_{ji}(T^b)_{ji}^*\right]
\left[\sum_{k,l}(T^a)_{lk}(T^b)_{lk}^*\right].
$$

Because the generators are Hermitian,

$$
\sum_{i,j}(T^a)_{ji}(T^b)_{ji}^*
=
\operatorname{tr}(T^aT^b)
=
\frac12\delta^{ab}.
$$

Thus

$$
\sum_{i,j,k,l}|C_{ji,lk}|^2
=
\frac14\sum_{a,b}\delta^{ab}\delta^{ab}
=
\frac14(N^2-1).
$$

Averaging over the $N^2$ initial colors gives

$$
\frac{N^2-1}{4N^2}.
$$

For QCD, $N=3$, so the result is $2/9$.

</details>

### Exercise 3: Fundamental completeness relation

Prove the $SU(N)$ identity

$$
(T^a)_{ij}(T^a)_{kl}
=
\frac12\left(\delta_{il}\delta_{jk}-\frac1N\delta_{ij}\delta_{kl}\right).
$$

<details>
<summary><strong>Solution</strong></summary>

The matrices $T^a$ form an orthonormal basis for traceless Hermitian $N\times N$ matrices with inner product

$$
\langle A,B\rangle=\operatorname{tr}(AB).
$$

A complete orthonormal basis for all Hermitian matrices is obtained by adjoining

$$
T^0=\frac{1}{\sqrt{2N}}\mathbf 1,
$$

so that

$$
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB},
\qquad
A,B=0,1,\ldots,N^2-1.
$$

Completeness for all matrices gives

$$
\sum_{A=0}^{N^2-1}(T^A)_{ij}(T^A)_{kl}
=
\frac12\delta_{il}\delta_{jk}.
$$

Subtracting the $A=0$ term,

$$
(T^0)_{ij}(T^0)_{kl}
=
\frac{1}{2N}\delta_{ij}\delta_{kl},
$$

leaves

$$
\sum_{a=1}^{N^2-1}(T^a)_{ij}(T^a)_{kl}
=
\frac12\delta_{il}\delta_{jk}
-\frac{1}{2N}\delta_{ij}\delta_{kl}.
$$

</details>

### Exercise 4: Abelian limit

Explain why the three-gluon and four-gluon vertices vanish in an Abelian gauge theory.

<details>
<summary><strong>Solution</strong></summary>

The nonlinear part of the non-Abelian field strength is proportional to the structure constants:

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

For an Abelian gauge group, the Lie algebra commutator vanishes, so

$$
f^{abc}=0.
$$

Therefore the field strength is linear in $A_\mu$, and the kinetic term $-F_{\mu\nu}F^{\mu\nu}/4$ is quadratic in $A_\mu$. No cubic or quartic gauge-boson self-interaction terms are generated.

</details>

### Exercise 5: Why one diagram is not enough

In $q\overline q\to gg$, why should you not expect either quark-exchange diagram alone to satisfy the external-gluon Ward identity?

<details>
<summary><strong>Solution</strong></summary>

A single quark-exchange diagram contains a fixed ordering of color matrices, such as $T^aT^b$. Replacing one external gluon polarization by its momentum produces terms that collapse adjacent fermion propagators, leaving boundary terms proportional to this ordered color structure.

The second quark-exchange diagram gives a similar contribution with the reversed ordering $T^bT^a$. The difference between the two orderings is

$$
[T^a,T^b]=if^{abc}T^c.
$$

That commutator is precisely the color structure of the $s$-channel diagram with the three-gluon vertex. Only the sum of the two quark-ordering diagrams and the three-gluon diagram has the correct non-Abelian gauge cancellation.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially §§69–72 and §81, for non-Abelian gauge theory, Yang–Mills Feynman rules, and QCD scattering examples.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chs. 15–17, for gauge theory, quantization, and renormalization of non-Abelian gauge theories.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 46–47, for Yang–Mills fields and quantization of non-Abelian gauge theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 25–27, for Yang–Mills theory, QCD Feynman rules, color ordering, and gluon amplitudes.
- Michael Peskin and Daniel Schroeder, *An Introduction to Quantum Field Theory*, chs. 15–17, for QCD amplitudes, color factors, and tree-level parton scattering.

## Version history

- **2026-06-12:** Initial polished draft. Establishes qft.org conventions for color-dressed non-Abelian tree amplitudes, quark scattering, gluon self-interactions, color ordering, and tree-level Ward-identity checks.
