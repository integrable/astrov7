---
title: "Color Factors"
description: "How non-Abelian group theory enters perturbative amplitudes through generators, structure constants, Casimirs, trace normalizations, color sums, and color decompositions."
sidebar:
  label: "Color Factors"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–73; Schwartz chs. 25–27; Weinberg Vol. II ch. 15; Coleman chs. 36–37 and 47"
topics:
  - color algebra
  - non-Abelian gauge theory
  - Casimir invariants
  - color decomposition
  - color sums
canonicalTopics:
  - color-factors
  - casimir-invariants
  - dynkin-index
  - color-decomposition
  - color-flow
researchStatus:
  established:
    - "Color factors in perturbative gauge theory are fixed by the Lie algebra representation data and by the chosen generator normalization."
  active:
    - "Efficient color bases, color-kinematics representations, and automated color reduction remain active computational topics for high-multiplicity and multi-loop amplitudes."
---

## Summary

Color factors are the group-theory part of non-Abelian perturbative amplitudes. The kinematic part knows about momenta, spin, helicity, and propagators; the color part knows about generators, structure constants, representation matrices, traces, and Casimirs.

In qft.org conventions the gauge generators are Hermitian,

$$
[T^a,T^b]=if^{abc}T^c,
$$

and matter in a representation $R$ couples through matrices $T_R^a$. We normalize them by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T_R\delta^{ab},
\qquad
T_R^aT_R^a=C_R\mathbf 1_R.
$$

The constants $T_R$ and $C_R$ are not the same object. The first is the trace normalization, often called the Dynkin index of $R$; the second is the quadratic Casimir eigenvalue in $R$. They are related by

$$
d_R C_R=d_G T_R,
$$

where $d_R$ is the dimension of the representation and $d_G$ is the dimension of the adjoint representation.

For $SU(N)$ with fundamental generators normalized by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$,

$$
T_F=\frac12,
\qquad
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

For QCD, $N=3$, so

$$
T_F=\frac12,
\qquad
C_F=\frac43,
\qquad
C_A=3.
$$

These three numbers appear almost everywhere in perturbative QCD: quark self-energies carry $C_F$, gluon and ghost loops carry $C_A$, and closed quark loops carry $T_F n_f$.

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Color algebra turns non-Abelian vertices and contractions into generator traces, Casimirs, and color decompositions](/figures/perturbative-qft/color-factors.svg)

<figcaption>

Color factors are the non-Abelian bookkeeping carried by the diagram. A quark–gluon vertex contributes a generator, a gluon self-interaction contributes a structure constant, loop contractions produce Casimirs, and Fierz identities turn adjoint exchange into color-flow structures.

</figcaption>
</figure>

## Prerequisites

You should know [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/), and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/). The only group theory assumed here is finite-dimensional matrix algebra: commutators, traces, and representation matrices.

## Core idea

A non-Abelian amplitude is a tensor in the color indices of the external particles. A gluon external leg carries an adjoint index $a$, a fundamental quark carries an index $i$, and an antiquark carries the corresponding dual index. The amplitude is therefore not just a number:

$$
\mathcal M
=\mathcal M^{a_1\cdots a_m}{}_{i_1\cdots}^{\phantom{i_1\cdots}j_1\cdots}.
$$

The Feynman rules build this tensor from two elementary ingredients:

$$
\text{matter vertex: }(T_R^a)_i{}^j,
\qquad
\text{gauge-boson vertex: }f^{abc}.
$$

Every internal color index is summed. After the sums are done, the diagram contributes a color tensor multiplying a Lorentz-kinematic expression.

A common schematic form is

$$
\mathcal M
=\sum_\alpha C_\alpha\,A_\alpha,
$$

where $C_\alpha$ are color tensors and $A_\alpha$ are partial amplitudes. The choice of basis is not unique. Trace bases, color-flow bases, multiplet bases, and color-ordered bases are all different ways of organizing the same tensor.

The essential point is practical: color algebra is not decorative. It decides which diagrams interfere, which terms survive color averaging, how amplitudes simplify at large $N$, and which constants appear in beta functions, anomalous dimensions, splitting kernels, and infrared factorization.

## Setup and conventions

We use the qft.org gauge-theory conventions

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators. For the fundamental representation of $SU(N)$ we write $T^a$ without a representation subscript and choose

$$
\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}.
$$

The adjoint representation has dimension

$$
d_G=N^2-1
\qquad\text{for }SU(N),
$$

and its generators may be written as

$$
(T_A^a)_{bc}=-if^{abc},
$$

so that

$$
\operatorname{tr}_A(T_A^aT_A^b)=C_A\delta^{ab}.
$$

Different books sometimes choose $\operatorname{tr}(T^aT^b)=\delta^{ab}$ instead. That convention doubles all $T_R$ values and rescales the matrices relative to $g$. Physical amplitudes do not change, but quoted color constants do. This page uses the standard particle-physics $SU(N)$ normalization $T_F=1/2$.

## The basic invariants

The trace normalization $T_R$ is defined by

$$
\operatorname{tr}_R(T_R^aT_R^b)=T_R\delta^{ab}.
$$

The quadratic Casimir $C_R$ is defined by

$$
\sum_a T_R^aT_R^a=C_R\mathbf 1_R.
$$

Taking the trace of the Casimir relation gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_R\operatorname{tr}_R\mathbf 1_R=C_R d_R.
$$

On the other hand, summing the trace-normalization equation over $a=b$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=T_R\delta^{aa}=T_R d_G.
$$

Therefore

$$
{d_R C_R=d_G T_R.}
$$

For the fundamental representation $F$ of $SU(N)$, $d_F=N$ and $d_G=N^2-1$. With $T_F=1/2$, this gives

$$
C_F=\frac{d_G T_F}{d_F}=\frac{N^2-1}{2N}.
$$

For the adjoint representation, $R=A$, $d_R=d_G$, so $C_A=T_A$. For $SU(N)$,

$$
{C_A=N.}
$$

The standard values are:

| Gauge theory | $T_F$ | $C_F$ | $C_A$ | $d_G$ |
|---|---:|---:|---:|---:|
| $SU(N)$ | $1/2$ | $(N^2-1)/(2N)$ | $N$ | $N^2-1$ |
| QCD, $SU(3)$ | $1/2$ | $4/3$ | $3$ | $8$ |
| $SU(2)$ fundamental | $1/2$ | $3/4$ | $2$ | $3$ |

## Color factors from common diagrams

### Quark self-energy

The color factor for the one-loop quark self-energy is

$$
(T^aT^a)_i{}^j=C_F\delta_i{}^j.
$$

Thus the loop correction is proportional to $C_F$. This is the first place many students meet the difference between QED and QCD: the diagram looks photon-like, but the color algebra has inserted a nontrivial Casimir.

### Gluon self-energy from gauge and ghost loops

The color contraction in a gluon or ghost loop has the form

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

This is the adjoint Casimir. It is responsible for the characteristic non-Abelian contribution to the Yang–Mills beta function. Matter loops instead produce

$$
\operatorname{tr}_R(T_R^aT_R^b)=T_R\delta^{ab},
$$

and for $n_f$ Dirac fermions in the fundamental representation this appears as $T_F n_f$.

### Quark–antiquark annihilation into gluons

A quark line emitting two gluons with adjoint labels $a$ and $b$ carries ordered products of generators:

$$
(T^aT^b)_i{}^j,
\qquad
(T^bT^a)_i{}^j.
$$

The order matters because the generators do not commute. Their commutator is

$$
[T^a,T^b]=if^{abc}T^c,
$$

which is exactly the color structure that also appears in the three-gluon vertex. This is why diagrams that look unrelated kinematically can be tied together by gauge invariance and color algebra.

### Pure-gluon amplitudes

At tree level, pure-gluon amplitudes can be expanded in traces of fundamental generators:

$$
\mathcal M_n^{\rm tree}(1,2,\ldots,n)
=
g^{n-2}\sum_{\sigma\in S_n/Z_n}
\operatorname{tr}
\left(T^{a_{\sigma(1)}}\cdots T^{a_{\sigma(n)}}\right)
A_n(\sigma(1),\ldots,\sigma(n)).
$$

The objects $A_n$ are color-ordered partial amplitudes. They contain no color matrices; they know only about a fixed cyclic ordering of the external gluons. Loop amplitudes require additional trace structures, including multi-trace terms.

For one quark–antiquark pair and $n-2$ gluons, a typical tree-level decomposition is

$$
\mathcal M_n^{\rm tree}
=
g^{n-2}\sum_{\sigma\in S_{n-2}}
\left(T^{a_{\sigma(3)}}\cdots T^{a_{\sigma(n)}}\right)_i{}^j
A_n(1_q,\sigma(3),\ldots,\sigma(n),2_{\bar q}).
$$

This form is the gateway to color ordering, spinor-helicity methods, and modern amplitude technology.

## The Fierz identity and color flow

For the fundamental representation of $SU(N)$ with $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$, the completeness relation for traceless Hermitian matrices gives

$$
\sum_a (T^a)_i{}^j(T^a)_k{}^\ell
=
\frac12
\left(
\delta_i{}^\ell\delta_k{}^j
-
\frac1N\delta_i{}^j\delta_k{}^\ell
\right).
$$

The first term is the color-flow term: an adjoint index behaves like a fundamental index and an antifundamental index flowing in opposite directions. The second term subtracts the trace part, because $SU(N)$ generators are traceless. For $U(N)$, that subtraction would be absent.

This identity explains the double-line representation. A gluon in the adjoint of $SU(N)$ can be drawn as a pair of fundamental color lines, but with a singlet component removed. In the large-$N$ limit, the first term dominates many counting arguments, while the $1/N$ term supplies subleading corrections.

## Color sums and color averaging

A scattering amplitude with external colored particles is not directly observed as a fixed color tensor. In perturbative collider-style calculations one usually sums over final colors and averages over initial colors:

$$
\overline{\sum}|\mathcal M|^2
=
\frac{1}{d_{\rm initial}}
\sum_{\text{colors, spins}}
|\mathcal M|^2.
$$

The denominator $d_{\rm initial}$ includes the number of initial color states, and sometimes spin states too depending on notation. For example, an initial quark in the fundamental of $SU(3)$ has $3$ color states; an initial gluon has $8$.

The color algebra in $|\mathcal M|^2$ can mix different color structures. If

$$
\mathcal M=\sum_\alpha C_\alpha A_\alpha,
$$

then

$$
\sum_{\rm colors}|\mathcal M|^2
=
\sum_{\alpha,\beta}
A_\alpha A_\beta^*
\sum_{\rm colors}C_\alpha C_\beta^*.
$$

The matrix

$$
S_{\alpha\beta}=\sum_{\rm colors}C_\alpha C_\beta^*
$$

is the color metric in the chosen color basis. A basis that is convenient for writing amplitudes is not always orthonormal for squaring them. This is one reason automated amplitude programs spend serious time on color reduction.

## Color-charge operators

For infrared factorization and soft-gluon physics, it is often cleaner to use color-charge operators $\mathbf T_i^a$ acting on the color index of external leg $i$. For a quark leg, $\mathbf T_i^a$ acts as a fundamental generator. For an antiquark leg, it acts as the negative transpose. For a gluon leg, it acts in the adjoint representation.

Gauge invariance of a color-singlet amplitude implies color conservation:

$$
\sum_i \mathbf T_i^a\,\mathcal M=0.
$$

Dot products of color charges are defined by

$$
\mathbf T_i\cdot\mathbf T_j
\equiv
\sum_a \mathbf T_i^a\mathbf T_j^a.
$$

They appear in soft anomalous dimensions, eikonal factors, and Wilson-line descriptions of infrared physics. The same color algebra that starts as a generator on a quark line later becomes an operator acting on the color space of an entire scattering process.

## Common pitfalls

**Confusing $T_R$ and $T^a_R$.** The notation is regrettably similar. $T_R^a$ is a generator matrix. $T_R$ without an adjoint index is the trace normalization of the representation.

**Confusing $T_R$ and $C_R$.** The trace normalization and quadratic Casimir are related, but not equal in general. For the $SU(N)$ fundamental representation, $T_F=1/2$ while $C_F=(N^2-1)/(2N)$.

**Dropping generator order.** Along a quark line, $T^aT^b$ and $T^bT^a$ are different. Their difference is controlled by $if^{abc}T^c$.

**Forgetting color averaging.** A squared amplitude for a physical unpolarized, color-unobserved process usually includes sums over final colors and averages over initial colors.

**Thinking color decomposition is unique.** Trace, color-flow, multiplet, and color-ordered bases are different representations of the same color tensor. A beautiful basis for one purpose may be clunky for another.

**Mixing generator normalizations across sources.** If one source uses $\operatorname{tr}(T^aT^b)=\delta^{ab}$ and another uses $\frac12\delta^{ab}$, the quoted values of $T_F$, $C_F$, and vertex conventions must be translated together.

## Relations to other pages

- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) gives the vertices whose color factors are reduced here.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) uses these factors in explicit tree amplitudes.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) is the Abelian limit where the noncommuting color algebra disappears.
- [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) explains why ghost loops carry adjoint color factors.
- Later infrared-factorization pages use color-charge operators $\mathbf T_i^a$ rather than fixed generator strings.
- Later on-shell-amplitudes pages develop trace bases and color-ordered partial amplitudes in more detail.

## Research status

- **Established:** The generator identities, Casimirs, trace normalizations, and color decompositions on this page are standard algebraic consequences of compact Lie algebra representation theory and perturbative Yang–Mills Feynman rules.
- **Active:** Efficient color bases for high-multiplicity amplitudes, multi-loop color reduction, color-kinematics duality, and color organization in parton showers remain active computational and conceptual areas.
- **Convention-dependent:** Numerical values such as $T_F=1/2$ depend on generator normalization. Physical predictions do not depend on that choice once $g$ and the generators are normalized consistently.

## Exercises

### Exercise 1: Trace normalization versus Casimir

Prove that

$$
d_R C_R=d_G T_R.
$$

<details>
<summary><strong>Solution</strong></summary>

Start from the Casimir definition

$$
T_R^aT_R^a=C_R\mathbf 1_R.
$$

Take the trace over the representation $R$:

$$
\operatorname{tr}_R(T_R^aT_R^a)=C_R\operatorname{tr}_R\mathbf 1_R=C_R d_R.
$$

But the trace normalization gives

$$
\operatorname{tr}_R(T_R^aT_R^b)=T_R\delta^{ab}.
$$

Setting $a=b$ and summing over $a$ gives

$$
\operatorname{tr}_R(T_R^aT_R^a)=T_R\delta^{aa}=T_R d_G.
$$

Equating the two expressions gives

$$
d_R C_R=d_G T_R.
$$

</details>

### Exercise 2: Fundamental Casimir of SU(N)

Using $T_F=1/2$, $d_F=N$, and $d_G=N^2-1$, derive $C_F$ for the fundamental representation of $SU(N)$.

<details>
<summary><strong>Solution</strong></summary>

Use the result from Exercise 1:

$$
d_F C_F=d_G T_F.
$$

Substitute

$$
d_F=N,
\qquad
d_G=N^2-1,
\qquad
T_F=\frac12.
$$

Then

$$
N C_F=\frac{N^2-1}{2},
$$

so

$$
{C_F=\frac{N^2-1}{2N}.}
$$

For $N=3$, this gives $C_F=4/3$.

</details>

### Exercise 3: Quark self-energy color factor

Show that the color factor of the one-loop quark self-energy in an $SU(N)$ gauge theory is $C_F\delta_i{}^j$.

<details>
<summary><strong>Solution</strong></summary>

The quark emits and reabsorbs an internal gluon. The two quark–gluon vertices contribute one generator each, with the internal gluon adjoint index summed:

$$
(T^a)_i{}^k(T^a)_k{}^j=(T^aT^a)_i{}^j.
$$

By the definition of the quadratic Casimir in the fundamental representation,

$$
T^aT^a=C_F\mathbf 1_F.
$$

Therefore

$$
(T^aT^a)_i{}^j=C_F\delta_i{}^j.
$$

</details>

### Exercise 4: The SU(N) Fierz identity

Assume the fundamental generators of $SU(N)$ are traceless and normalized by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. Show that

$$
\sum_a (T^a)_i{}^j(T^a)_k{}^\ell
=
\frac12
\left(
\delta_i{}^\ell\delta_k{}^j
-
\frac1N\delta_i{}^j\delta_k{}^\ell
\right).
$$

<details>
<summary><strong>Solution</strong></summary>

The matrices $T^a$ form an orthonormal basis of traceless Hermitian $N\times N$ matrices with inner product $\operatorname{tr}(AB)$. To complete them to a basis of all Hermitian matrices, add the normalized identity

$$
T^0=\frac{1}{\sqrt{2N}}\mathbf 1.
$$

The completeness relation for the full $U(N)$ basis is

$$
\sum_{A=0}^{N^2-1}(T^A)_i{}^j(T^A)_k{}^\ell
=\frac12\delta_i{}^\ell\delta_k{}^j.
$$

Subtract the identity contribution:

$$
(T^0)_i{}^j(T^0)_k{}^\ell
=\frac{1}{2N}\delta_i{}^j\delta_k{}^\ell.
$$

Thus the $SU(N)$ generators alone satisfy

$$
\sum_a (T^a)_i{}^j(T^a)_k{}^\ell
=\frac12\delta_i{}^\ell\delta_k{}^j
-\frac{1}{2N}\delta_i{}^j\delta_k{}^\ell,
$$

which is the desired identity.

</details>

### Exercise 5: Color conservation for a singlet amplitude

Let $\mathcal M$ be a color-singlet amplitude with external color charges $\mathbf T_i^a$. Explain why

$$
\sum_i\mathbf T_i^a\mathcal M=0.
$$

<details>
<summary><strong>Solution</strong></summary>

A global gauge transformation acts on every external color index. Its infinitesimal generator is the sum of the generators acting on each external leg:

$$
\mathbf T_{\rm total}^a=\sum_i\mathbf T_i^a.
$$

If the full amplitude is a color singlet, it is invariant under this global transformation. Therefore the total generator annihilates the amplitude:

$$
\mathbf T_{\rm total}^a\mathcal M=0.
$$

Equivalently,

$$
\sum_i\mathbf T_i^a\mathcal M=0.
$$

This identity is the color-space version of charge conservation.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§69–73, for non-Abelian gauge theory, group representations, Feynman rules, and the Yang–Mills beta function.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 25–27, for Yang–Mills theory, color factors, gluon scattering, and color ordering.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 15, for non-Abelian gauge theories, ghosts, and gauge-theory perturbation theory.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 36–37 and 47, for $SU(3)$ representation methods and non-Abelian gauge-field Feynman rules.
- Lance J. Dixon, “Calculating Scattering Amplitudes Efficiently,” for color decomposition and color-ordered amplitudes in perturbative gauge theory.

## Version history

- **2026-06-13:** Initial polished draft. Fixes qft.org color-factor conventions, $SU(N)$ invariants, Fierz identity, common diagram color factors, color sums, and color-space notation.
