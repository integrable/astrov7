---
title: "Spinor-Helicity Formalism"
description: "The massless four-dimensional spinor-helicity variables, little-group weights, angle and square brackets, polarization vectors, and first amplitude examples."
sidebar:
  label: "Spinor-Helicity Formalism"
  order: 1
level: Advanced
status: "Polished draft"
source: "Dixon; Mangano and Parke; Elvang and Huang; Schwartz ch. 27; Srednicki §50."
topics:
  - spinor-helicity formalism
  - massless amplitudes
  - little group
  - helicity amplitudes
  - on-shell methods
canonicalTopics:
  - spinor-helicity-formalism
  - massless-four-dimensional-kinematics
  - little-group-scaling
  - helicity-amplitudes
researchStatus:
  established:
    - "Four-dimensional spinor-helicity variables are standard tools for massless scattering amplitudes in gauge theory, gravity, and related theories."
  active:
    - "Modern research extends spinor-helicity ideas to massive particles, higher dimensions, twistor geometry, celestial amplitudes, double copy, and positive-geometry formulations."
---

## Summary

The **spinor-helicity formalism** is a way to write massless four-dimensional scattering amplitudes directly in terms of spinors associated with the external momenta. For a null momentum,

$$
p^2=0,
$$

the bispinor matrix

$$
p_{\alpha\dot\alpha}
$$

has rank one, so it factorizes as

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}.
$$

The two spinors are not unique. They have a little-group redundancy,

$$
\lambda_\alpha\mapsto t\lambda_\alpha,
\qquad
\tilde\lambda_{\dot\alpha}\mapsto t^{-1}\tilde\lambda_{\dot\alpha},
$$

which leaves $p_{\alpha\dot\alpha}$ unchanged. An amplitude with external helicity $h_i$ must scale as

$$
\mathcal A_n(\ldots,i^{h_i},\ldots)
\mapsto
 t_i^{-2h_i}\mathcal A_n(\ldots,i^{h_i},\ldots).
$$

<figure class="doc-figure" style="--figure-width: 46rem; --caption-width: 55rem;">

![Spinor-helicity variables turn a null momentum into a pair of spinors](/figures/perturbative-qft/spinor-helicity-formalism.svg)

<figcaption>

A null momentum is a rank-one bispinor, so it factorizes into spinor-helicity variables. The leftover little-group rescaling fixes the homogeneous weight of each external leg, while Lorentz-invariant brackets build compact amplitudes.

</figcaption>
</figure>

Spinor-helicity variables make massless amplitudes short because they solve many kinematic constraints before dynamics enters. Momentum conservation, Lorentz invariance, helicity weights, gauge invariance, and factorization become algebraic statements about brackets. This is why a multi-page Feynman-diagram result can sometimes collapse to one line.

## Prerequisites

You should know [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), [Helicity Amplitudes Preview](/perturbative-qft/tree-level-scattering/helicity-amplitudes-preview/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), and [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/).

For spinor background, review the Foundations pages on Dirac, Weyl, and Majorana spinors and the Mathematical Toolkit pages on Clifford algebras and spinors.

## Core idea

Ordinary Feynman rules keep Lorentz covariance manifest by using four-vectors, gamma matrices, and polarization vectors. For massless four-dimensional scattering, this is often a clumsy language. The physical states are labeled by helicity, not by arbitrary Lorentz components.

Spinor-helicity variables use the fact that a null four-vector is equivalent to a rank-one $2\times2$ matrix. The rank-one condition lets us write the momentum as a product of a left-handed spinor and a right-handed spinor. The amplitude is then built from the antisymmetric spinor contractions

$$
\langle ij\rangle,
\qquad
[ij].
$$

These brackets know about both Lorentz invariance and helicity. The formalism is not merely notation. It is a coordinate system adapted to the on-shell massless degrees of freedom.

The core dictionary is:

| Four-vector language | Spinor-helicity language |
|---|---|
| $p_i^2=0$ | $p_{i,\alpha\dot\alpha}=\lambda_{i,\alpha}\tilde\lambda_{i,\dot\alpha}$ |
| Lorentz invariants | $\langle ij\rangle$ and $[ij]$ |
| helicity | little-group weight |
| gauge choice for polarization | reference spinor choice |
| Ward identity | independence of reference spinors |
| compact amplitudes | homogeneous rational functions of brackets |

## Setup and conventions

We use qft.org scattering conventions and take all external momenta to be outgoing unless a page says otherwise. The spinor-helicity literature contains many sign conventions. On this page, the bracket convention is

$$
\langle ij\rangle[ji]=2p_i\cdot p_j.
$$

Changing conventions can move signs between square brackets, angle brackets, and momentum invariants. The physics is unchanged, but comparing formulas requires translating this line carefully.

In four dimensions, identify a real momentum with a bispinor,

$$
p_{\alpha\dot\alpha}=p_\mu\sigma^\mu_{\alpha\dot\alpha}.
$$

For a null momentum, the determinant vanishes,

$$
\det(p_{\alpha\dot\alpha})=p^2=0,
$$

so $p_{\alpha\dot\alpha}$ has rank one and may be written as

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}.
$$

For real positive-energy momenta in Lorentzian signature, $\tilde\lambda$ is related to the complex conjugate of $\lambda$ up to convention. In amplitude calculations, it is often better to complexify momenta and treat $\lambda$ and $\tilde\lambda$ as independent complex variables.

## Brackets

The basic Lorentz-invariant contractions are

$$
\langle ij\rangle
=\varepsilon^{\alpha\beta}\lambda_{i,\alpha}\lambda_{j,\beta},
\qquad
[ij]
=\varepsilon^{\dot\alpha\dot\beta}
\tilde\lambda_{i,\dot\alpha}\tilde\lambda_{j,\dot\beta}.
$$

They are antisymmetric:

$$
\langle ij\rangle=-\langle ji\rangle,
\qquad
[ij]=-[ji],
\qquad
\langle ii\rangle=[ii]=0.
$$

The most important identity is the relation to two-particle invariants:

$$
s_{ij}\equiv (p_i+p_j)^2=2p_i\cdot p_j=\langle ij\rangle[ji].
$$

This relation is the workhorse behind compact amplitude formulas. It lets scalar products be traded for spinor brackets, while keeping helicity information visible.

## Little-group scaling

The factorization

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}
$$

is invariant under

$$
\lambda_\alpha\mapsto t\lambda_\alpha,
\qquad
\tilde\lambda_{\dot\alpha}\mapsto t^{-1}\tilde\lambda_{\dot\alpha}.
$$

This is the complexified little group for a massless particle. Physical amplitudes are not invariant under this scaling; they transform with a helicity-dependent weight. For each external particle,

$$
\mathcal A_n(\ldots,i^{h_i},\ldots)
\mapsto
 t_i^{-2h_i}\mathcal A_n(\ldots,i^{h_i},\ldots).
$$

Thus a positive-helicity gluon has weight $t_i^{-2}$, while a negative-helicity gluon has weight $t_i^{2}$. A positive-helicity graviton has weight $t_i^{-4}$, and a negative-helicity graviton has weight $t_i^4$.

Little-group scaling is one of the main reasons spinor-helicity formulas are so constrained. Once you know the helicities and mass dimension, there may be very few possible rational functions of brackets.

## Momentum conservation

For an $n$-point amplitude with all momenta outgoing,

$$
\sum_{i=1}^n p_i^\mu=0.
$$

In spinor variables this becomes

$$
\sum_{i=1}^n \lambda_{i,\alpha}\tilde\lambda_{i,\dot\alpha}=0.
$$

Useful consequences are obtained by contracting this equation with external spinors. For example,

$$
\sum_{i=1}^n \langle q i\rangle [i r]=0
$$

for arbitrary external or reference spinors $q$ and $r$. Many spinor-helicity simplifications are just momentum conservation written in this form.

A second universal identity is the Schouten identity. For two-component spinors,

$$
\langle ab\rangle\lambda_c
+\langle bc\rangle\lambda_a
+\langle ca\rangle\lambda_b=0.
$$

Contracting with a fourth spinor gives

$$
\langle ab\rangle\langle cd\rangle
+\langle bc\rangle\langle ad\rangle
+\langle ca\rangle\langle bd\rangle=0,
$$

with an analogous identity for square brackets. This identity is the two-dimensional linear algebra hiding under many miracle cancellations.

## Polarization vectors

For a massless vector boson with momentum $p$, polarization vectors can be written using a reference spinor $q$. In bispinor notation, a convenient convention is

$$
\varepsilon^-_{\alpha\dot\alpha}(p;q)
=\sqrt2\frac{\lambda_{\alpha}\tilde q_{\dot\alpha}}{[p q]},
\qquad
\varepsilon^+_{\alpha\dot\alpha}(p;q)
=\sqrt2\frac{q_{\alpha}\tilde\lambda_{\dot\alpha}}{\langle q p\rangle}.
$$

Here $q$ is not a physical momentum measured in the detector. It is a reference spinor encoding a gauge choice. Changing $q$ shifts $\varepsilon^\mu$ by a term proportional to $p^\mu$, so gauge-invariant amplitudes do not depend on $q$.

The little-group weights are correct:

$$
\varepsilon^-\mapsto t^2\varepsilon^- ,
\qquad
\varepsilon^+\mapsto t^{-2}\varepsilon^+.
$$

This is exactly the weight expected for helicities $h=-1$ and $h=+1$.

The reference-spinor freedom is often the computational jackpot. A clever choice of $q$ can make many polarization contractions vanish before doing any gamma-matrix or Lorentz-index algebra.

## Three-point kinematics

Massless three-point amplitudes are special. With real Lorentzian momenta and all three external particles on shell, momentum conservation forces all invariants to vanish:

$$
s_{12}=s_{23}=s_{31}=0.
$$

For real momenta this usually makes the amplitude kinematically degenerate. But after complexifying momenta, there are two branches:

$$
[12]=[23]=[31]=0
\quad\text{with nonzero angle brackets},
$$

or

$$
\langle12\rangle=\langle23\rangle=\langle31\rangle=0
\quad\text{with nonzero square brackets}.
$$

This is why complex momenta are not a luxury in modern amplitude methods. They allow three-point amplitudes to be nontrivial building blocks for recursion and factorization.

For color-ordered Yang–Mills, little-group scaling fixes the kinematic three-point amplitudes up to an overall coupling convention:

$$
A_3(1^-,2^-,3^+)
\propto
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle},
$$

and

$$
A_3(1^+,2^+,3^-)
\propto
\frac{[12]^3}{[23][31]}.
$$

The first expression lives on the holomorphic branch; the second lives on the anti-holomorphic branch.

## The Parke–Taylor formula

A famous payoff is the tree-level maximally helicity-violating gluon amplitude. In a common color-stripped convention, the kinematic part of the $n$-gluon amplitude with negative-helicity gluons $r$ and $s$ is

$$
A_n^{\mathrm{MHV}}
(1^+,\ldots,r^-,\ldots,s^-,\ldots,n^+)
=
\frac{\langle r s\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle}.
$$

Overall factors of $i$ and powers of the gauge coupling depend on whether one includes them in the color-stripped amplitude. The important point is the kinematic structure: a complicated sum of Feynman diagrams collapses to a single rational function.

Check the little-group weights. For a positive-helicity leg $i$ not equal to $r$ or $s$, the denominator contains two angle brackets involving $i$, so the amplitude scales as $t_i^{-2}$. For a negative-helicity leg $r$, the numerator contributes $t_r^4$ and the denominator contributes $t_r^2$, so the net scaling is $t_r^2$. This matches $t_i^{-2h_i}$ in both cases.

The formula also displays factorization. When adjacent momenta become collinear, an angle bracket in the denominator vanishes, producing the expected singular behavior of a gauge-theory amplitude.

## Why this formalism is powerful

Spinor-helicity variables make several structures manifest at once.

| Structure | Spinor-helicity advantage |
|---|---|
| on-shell kinematics | $p^2=0$ is solved by construction |
| helicity | encoded as little-group weight |
| gauge redundancy | encoded as reference-spinor independence |
| factorization | poles appear as bracket singularities |
| recursion | complex momentum shifts are natural |
| color ordering | cyclic rational functions become visible |
| double copy | gravity amplitudes often look like squared gauge amplitudes |

This does not mean Feynman diagrams become obsolete. Rather, spinor-helicity variables expose the simplicity that Feynman diagrams often hide.

## Real momenta, complex momenta, and signatures

For real momenta in ordinary Lorentzian signature, angle and square brackets are related by complex conjugation for positive-energy particles, up to conventions and phases. In complexified kinematics, $\lambda$ and $\tilde\lambda$ are independent.

This distinction matters. Many exact amplitude statements are first written for complex momenta, then interpreted by analytic continuation. BCFW recursion, three-point building blocks, and factorization proofs all use this complexified viewpoint.

Another useful option is split signature, where $\lambda$ and $\tilde\lambda$ can both be taken real. This is often convenient in twistor-inspired discussions. The physical Lorentzian amplitude is then recovered by analytic continuation.

## Common pitfalls

**Forgetting little-group weights.** A formula with the right mass dimension and poles can still be wrong if it has the wrong homogeneous scaling on an external leg.

**Mixing bracket-sign conventions.** Some sources use $\langle ij\rangle[ij]=2p_i\cdot p_j$ instead of $\langle ij\rangle[ji]=2p_i\cdot p_j$. Translate before comparing signs.

**Treating reference spinors as physical data.** The reference spinor $q$ in a polarization vector is a gauge choice. A gauge-invariant amplitude cannot depend on it.

**Using real three-point intuition too literally.** Nonzero massless three-point amplitudes require complexified kinematics or an analytic continuation. They are still the correct building blocks for factorization.

**Assuming all compact formulas are color-dressed.** Many beautiful formulas are color-ordered or color-stripped. Add color factors and coupling conventions separately.

**Applying four-dimensional identities in other dimensions.** Ordinary spinor-helicity formulas are special to four dimensions. Higher-dimensional on-shell formalisms exist, but the bracket algebra changes.

## Relations to other pages

- [Helicity Amplitudes Preview](/perturbative-qft/tree-level-scattering/helicity-amplitudes-preview/) explains why helicity amplitudes are useful before introducing the full spinor-helicity machinery.
- [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) gives the covariant polarization technology that spinor-helicity variables partially replace.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) and [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) provide the Feynman-diagram route to the same tree amplitudes.
- [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) is the companion page for color structures that are often stripped off in on-shell formulas.
- The next pages in this chapter should develop three-point amplitudes, color decomposition, color-ordered amplitudes, and BCFW recursion.
- The Mathematical Toolkit pages on spinors, Clifford algebras, and spinor-helicity identities provide the background algebra.

## Research status

- **Established:** Spinor-helicity variables are standard for four-dimensional massless amplitudes. Their little-group scaling, bracket algebra, polarization vectors, and use in tree-level gauge-theory amplitudes are textbook material.
- **Active:** Modern work extends the formalism to massive particles, higher dimensions, supersymmetric on-shell superspaces, momentum twistors, celestial amplitudes, positive geometries, and double-copy constructions.
- **Speculative:** The basic formalism is not speculative. Some broader geometric interpretations of amplitudes remain active research areas.

## Exercises

### Exercise 1: Bracket antisymmetry

Using

$$
\langle ij\rangle=\varepsilon^{\alpha\beta}\lambda_{i,\alpha}\lambda_{j,\beta},
$$

show that $\langle ij\rangle=-\langle ji\rangle$ and $\langle ii\rangle=0$.

<details>
<summary><strong>Solution</strong></summary>

Exchange $i$ and $j$:

$$
\langle ji\rangle
=\varepsilon^{\alpha\beta}\lambda_{j,\alpha}\lambda_{i,\beta}.
$$

Relabel the dummy indices $\alpha\leftrightarrow\beta$:

$$
\langle ji\rangle
=\varepsilon^{\beta\alpha}\lambda_{j,\beta}\lambda_{i,\alpha}.
$$

Since $\varepsilon^{\beta\alpha}=-\varepsilon^{\alpha\beta}$ and the spinor components commute for ordinary external kinematics,

$$
\langle ji\rangle=-\varepsilon^{\alpha\beta}\lambda_{i,\alpha}\lambda_{j,\beta}=-\langle ij\rangle.
$$

Setting $i=j$ gives

$$
\langle ii\rangle=-\langle ii\rangle,
$$

so $\langle ii\rangle=0$.

</details>

### Exercise 2: Little-group weight of a bracket

Under

$$
\lambda_i\mapsto t_i\lambda_i,
\qquad
\tilde\lambda_i\mapsto t_i^{-1}\tilde\lambda_i,
$$

find the scaling of $\langle ij\rangle$ and $[ij]$.

<details>
<summary><strong>Solution</strong></summary>

The angle bracket contains one $\lambda_i$ and one $\lambda_j$, so

$$
\langle ij\rangle\mapsto t_i t_j\langle ij\rangle.
$$

The square bracket contains one $\tilde\lambda_i$ and one $\tilde\lambda_j$, so

$$
[ij]\mapsto t_i^{-1}t_j^{-1}[ij].
$$

The product $\langle ij\rangle[ji]$ is invariant, as it must be because it equals $2p_i\cdot p_j$.

</details>

### Exercise 3: Little-group scaling of the Parke–Taylor formula

For

$$
A_n^{\mathrm{MHV}}
=
\frac{\langle r s\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle},
$$

show that a positive-helicity leg has weight $t_i^{-2}$ and a negative-helicity leg has weight $t_i^2$.

<details>
<summary><strong>Solution</strong></summary>

Every leg $i$ appears in exactly two adjacent angle brackets in the cyclic denominator, so the denominator contributes a factor $t_i^2$ for every leg.

If $i$ is a positive-helicity leg, it does not appear in the numerator. Therefore

$$
A_n\mapsto t_i^{-2}A_n,
$$

which is the correct weight for $h_i=+1$.

If $i=r$ or $i=s$ is one of the two negative-helicity legs, the numerator $\langle rs\rangle^4$ contributes $t_i^4$. Combining numerator and denominator gives

$$
A_n\mapsto t_i^{4-2}A_n=t_i^2A_n,
$$

which is the correct weight for $h_i=-1$.

</details>

### Exercise 4: Reference-spinor shift as a gauge transformation

Use the negative-helicity polarization

$$
\varepsilon^-_{\alpha\dot\alpha}(p;q)
=\sqrt2\frac{\lambda_{\alpha}\tilde q_{\dot\alpha}}{[p q]}
$$

to explain why changing $q$ can only affect a gauge-invariant amplitude by a Ward-identity zero.

<details>
<summary><strong>Solution</strong></summary>

The polarization vector is transverse because it contains the same left-handed spinor as the momentum:

$$
p_{\alpha\dot\alpha}=\lambda_\alpha\tilde\lambda_{\dot\alpha}.
$$

A change of reference spinor changes the polarization by another transverse representative plus a term proportional to

$$
\lambda_\alpha\tilde\lambda_{\dot\alpha}=p_{\alpha\dot\alpha}.
$$

In vector notation this is a shift

$$
\varepsilon^\mu\mapsto\varepsilon^\mu+c\,p^\mu.
$$

Gauge invariance says that replacing an external polarization by its momentum gives zero in a physical amplitude. Therefore the reference-spinor dependence cancels from gauge-invariant amplitudes.

</details>

### Exercise 5: Three-point helicity weights

Check that

$$
A_3(1^-,2^-,3^+)
\propto
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle}
$$

has little-group weights appropriate to helicities $(-1,-1,+1)$.

<details>
<summary><strong>Solution</strong></summary>

For leg $1$, the numerator contributes $t_1^3$. The denominator contains $\langle31\rangle$, contributing $t_1$. The net weight is $t_1^2$, appropriate for $h_1=-1$.

For leg $2$, the numerator contributes $t_2^3$. The denominator contains $\langle23\rangle$, contributing $t_2$. The net weight is $t_2^2$, appropriate for $h_2=-1$.

For leg $3$, the numerator contributes no $t_3$. The denominator contains both $\langle23\rangle$ and $\langle31\rangle$, contributing $t_3^2$. The net weight is $t_3^{-2}$, appropriate for $h_3=+1$.

Thus the formula has the correct helicity weights.

</details>

## References

- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” for a classic review of spinor-helicity and amplitude methods.
- M. L. Mangano and S. J. Parke, “Multiparton Amplitudes in Gauge Theories,” for color ordering and spinor-helicity technology in gauge theory.
- S. Parke and T. Taylor, “An Amplitude for $n$-Gluon Scattering,” for the original compact MHV formula.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a systematic modern introduction.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for gluon scattering and spinor-helicity methods in a QFT textbook.
- M. Srednicki, *Quantum Field Theory*, §50, for massless particles and spinor-helicity basics.
- R. Penrose and W. Rindler, *Spinors and Space-Time*, for the deeper spinor geometry behind the formalism.

## Version history

- **2026-06-13:** Initial polished page. Establishes four-dimensional massless spinor-helicity conventions, bracket algebra, little-group weights, polarization vectors, three-point amplitudes, and the Parke–Taylor example.
