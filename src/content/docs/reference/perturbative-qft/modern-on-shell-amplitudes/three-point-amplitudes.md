---
title: "Three-Point Amplitudes"
description: "How complex massless three-point kinematics and little-group scaling fix the elementary on-shell amplitudes used in factorization and recursion."
sidebar:
  label: "Three-Point Amplitudes"
  order: 2
level: Advanced
status: "Polished draft"
source: "Dixon; Mangano and Parke; Elvang and Huang; Schwartz ch. 27; Srednicki §50"
topics:
  - three-point amplitudes
  - spinor-helicity formalism
  - little-group scaling
  - massless kinematics
  - on-shell recursion
canonicalTopics:
  - three-point-amplitudes
  - massless-three-point-kinematics
  - holomorphic-three-point-amplitudes
  - anti-holomorphic-three-point-amplitudes
researchStatus:
  established:
    - "Massless three-point amplitudes in four-dimensional complex kinematics are fixed by Lorentz invariance, little-group scaling, locality assumptions, and mass dimension up to coupling constants."
  active:
    - "Modern work extends three-point classification to massive spinor-helicity variables, higher dimensions, supersymmetric on-shell superspaces, celestial bases, and effective higher-spin interactions."
---

## Summary

Three-point amplitudes are the atoms of the on-shell approach to scattering. In ordinary Feynman rules, a three-point interaction is a vertex. In modern amplitude language, the corresponding object is an on-shell three-particle amplitude constrained by kinematics, Lorentz invariance, and little-group scaling.

For three massless external momenta with all particles outgoing,

$$
p_i^2=0,
\qquad
p_1+p_2+p_3=0,
$$

every two-particle invariant vanishes:

$$
s_{12}=s_{23}=s_{31}=0.
$$

With real Lorentzian momenta this is too degenerate to show much structure. After complexifying momenta, however, there are two useful branches:

$$
[12]=[23]=[31]=0
\quad\text{with angle brackets allowed,}
$$

or

$$
\langle12\rangle=\langle23\rangle=\langle31\rangle=0
\quad\text{with square brackets allowed.}
$$

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![Massless three-point kinematics splits into holomorphic and anti-holomorphic branches](/figures/perturbative-qft/three-point-amplitudes.svg)

<figcaption>

Complex massless three-point kinematics splits into two branches. The holomorphic branch uses angle brackets and supports amplitudes such as $A_3(1^-,2^-,3^+)$; the anti-holomorphic branch uses square brackets and supports the conjugate helicity configuration.

</figcaption>
</figure>

This branch structure is not a technical nuisance. It is the reason three-point amplitudes can be nonzero and still be compatible with massless on-shell kinematics. These amplitudes are the building blocks in factorization, BCFW recursion, generalized unitarity, double-copy constructions, and many compact tree-level formulas.

## Prerequisites

You should know [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), [Helicity Amplitudes Preview](/perturbative-qft/tree-level-scattering/helicity-amplitudes-preview/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/). For the role of three-point amplitudes in analytic structure, review [Threshold Behavior](/perturbative-qft/unitarity-analyticity-dispersion/threshold-behavior/) and [S-Matrix Bootstrap Preview](/perturbative-qft/unitarity-analyticity-dispersion/s-matrix-bootstrap-preview/).

## Core idea

A massless three-point amplitude is unusually rigid. Once the helicities are fixed, little-group scaling almost determines the spinor-bracket dependence.

The rigidity comes from three facts:

| Input | Consequence |
|---|---|
| $p_i^2=0$ | each momentum factorizes as $p_i=\lambda_i\tilde\lambda_i$ |
| $p_1+p_2+p_3=0$ | all $s_{ij}$ vanish |
| complex kinematics | either all square brackets vanish or all angle brackets vanish |
| little-group scaling | the powers of brackets are fixed by helicities |
| mass dimension | the remaining freedom is the coupling dimension |

Thus a three-point amplitude is not an arbitrary polynomial. It is a homogeneous function with prescribed weights under

$$
\lambda_i\mapsto t_i\lambda_i,
\qquad
\tilde\lambda_i\mapsto t_i^{-1}\tilde\lambda_i.
$$

For a particle of helicity $h_i$, the amplitude must scale as

$$
\mathcal A_3(\ldots,i^{h_i},\ldots)
\mapsto
 t_i^{-2h_i}\mathcal A_3(\ldots,i^{h_i},\ldots).
$$

At three points, this single rule nearly writes the answer for you. It is one of those rare moments when linear algebra politely does the physics homework.

## Setup and conventions

We use the spinor-helicity conventions of the previous page. In particular,

$$
p_{i,\alpha\dot\alpha}
=\lambda_{i,\alpha}\tilde\lambda_{i,\dot\alpha},
\qquad
\langle ij\rangle[ji]=2p_i\cdot p_j.
$$

All external momenta are taken outgoing. We write $A_n$ for color-ordered or color-stripped partial amplitudes when color factors have been removed, and $\mathcal A_n$ or $\mathcal M_n$ for color-dressed amplitudes depending on context.

The formulas below fix the kinematic dependence. Overall factors of $i$, signs, and powers of a coupling such as $g$ or $\kappa$ depend on the amplitude normalization and on whether the coupling is included inside $A_3$.

## Three-point massless kinematics

Start from

$$
p_1+p_2+p_3=0.
$$

Squaring this equation and using $p_i^2=0$ gives

$$
(p_1+p_2)^2=p_3^2=0,
$$

so

$$
s_{12}=2p_1\cdot p_2=0.
$$

The same argument gives

$$
s_{23}=s_{31}=0.
$$

In spinor-helicity variables,

$$
s_{ij}=\langle ij\rangle[ji].
$$

Therefore

$$
\langle12\rangle[21]
=
\langle23\rangle[32]
=
\langle31\rangle[13]
=0.
$$

For real Lorentzian momenta, the angle and square brackets are related by complex conjugation up to phases. If the product vanishes, both factors vanish. The result is a collinear, degenerate configuration.

For complex momenta, $\lambda$ and $\tilde\lambda$ are independent. Then the vanishing of every product can be achieved in two nontrivial ways.

On the holomorphic branch,

$$
[12]=[23]=[31]=0,
$$

so the right-handed spinors are proportional:

$$
\tilde\lambda_1\propto\tilde\lambda_2\propto\tilde\lambda_3.
$$

The angle brackets may remain nonzero. On the anti-holomorphic branch,

$$
\langle12\rangle=\langle23\rangle=\langle31\rangle=0,
$$

so the left-handed spinors are proportional, while square brackets may remain nonzero.

These are not two different physical theories. They are two analytic branches of the same complexified on-shell kinematics.

## The holomorphic solution

Suppose the amplitude is supported on the branch where the square brackets vanish. Then the nonzero spinor invariants are angle brackets, so try

$$
A_3^{\rm H}(1^{h_1},2^{h_2},3^{h_3})
=
 g_{\rm H}\,
\langle12\rangle^a
\langle23\rangle^b
\langle31\rangle^c.
$$

Little-group scaling fixes the exponents. Since leg $1$ appears in $\langle12\rangle$ and $\langle31\rangle$,

$$
a+c=-2h_1.
$$

Similarly,

$$
a+b=-2h_2,
\qquad
b+c=-2h_3.
$$

Solving gives

$$
a=h_3-h_1-h_2,
\qquad
b=h_1-h_2-h_3,
\qquad
c=h_2-h_3-h_1.
$$

Thus

$$
A_3^{\rm H}
=
g_{\rm H}
\langle12\rangle^{h_3-h_1-h_2}
\langle23\rangle^{h_1-h_2-h_3}
\langle31\rangle^{h_2-h_3-h_1}.
$$

This formula should be read as a homogeneous rational function on the holomorphic three-point branch. Negative exponents are not automatically a disaster; familiar gauge-theory amplitudes have them. The corresponding singular-looking denominators are part of the spinor-helicity representation of local gauge interactions.

## The anti-holomorphic solution

On the branch where angle brackets vanish, try instead

$$
A_3^{\overline{\rm H}}(1^{h_1},2^{h_2},3^{h_3})
=
 g_{\overline{\rm H}}\,
[12]^a[23]^b[31]^c.
$$

Square brackets scale oppositely to angle brackets. The little-group equations are

$$
a+c=2h_1,
\qquad
a+b=2h_2,
\qquad
b+c=2h_3.
$$

Therefore

$$
a=h_1+h_2-h_3,
\qquad
b=-h_1+h_2+h_3,
\qquad
c=h_1-h_2+h_3.
$$

The anti-holomorphic three-point amplitude is

$$
A_3^{\overline{\rm H}}
=
g_{\overline{\rm H}}
[12]^{h_1+h_2-h_3}
[23]^{-h_1+h_2+h_3}
[31]^{h_1-h_2+h_3}.
$$

For a parity-invariant theory, holomorphic and anti-holomorphic couplings are related between opposite-helicity amplitudes. For a chiral theory or for a theory with parity-violating interactions, they need not be paired so simply.

## Standard examples

### Scalar cubic interaction

For three scalars, $h_1=h_2=h_3=0$. Both formulas reduce to a constant:

$$
A_3(1^0,2^0,3^0)=g.
$$

This is the on-shell version of a local cubic scalar interaction. There is no little-group weight to carry, so no brackets are needed.

### Yang–Mills three-gluon amplitudes

For color-ordered Yang–Mills amplitudes, the two nonzero helicity structures with dimensionless coupling are

$$
A_3(1^-,2^-,3^+)
=
 g\,
\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle},
$$

and

$$
A_3(1^+,2^+,3^-)
=
 g\,
\frac{[12]^3}{[23][31]}.
$$

The first is holomorphic and the second is anti-holomorphic. Configurations with all helicities equal require higher-derivative interactions, such as operators schematically of type $F^3$ in an effective theory, rather than ordinary Yang–Mills.

### Gravity three-point amplitudes

For gravitons, the same logic gives

$$
M_3(1^{-2},2^{-2},3^{+2})
=
\kappa\,
\frac{\langle12\rangle^6}{\langle23\rangle^2\langle31\rangle^2},
$$

and

$$
M_3(1^{+2},2^{+2},3^{-2})
=
\kappa\,
\frac{[12]^6}{[23]^2[31]^2}.
$$

These are the squares of the corresponding Yang–Mills kinematic structures, with the replacement of the gauge coupling by the gravitational coupling. This is the first glimpse of the double-copy idea, although the full double-copy story is much deeper than squaring a three-point formula.

### Higher-derivative amplitudes

Effective interactions produce other helicity structures. For example, a self-dual or anti-self-dual cubic gauge-field operator can produce all-minus or all-plus amplitudes of the schematic form

$$
A_3(1^-,2^-,3^-)
\propto
\langle12\rangle\langle23\rangle\langle31\rangle,
$$

and

$$
A_3(1^+,2^+,3^+)
\propto
[12][23][31].
$$

These have more powers of momentum and therefore come with dimensionful EFT coefficients. Little-group scaling allows them; the Lagrangian tells you whether the theory actually contains the corresponding operator.

## Mass dimension and coupling dimension

In four spacetime dimensions, an $n$-point amplitude has mass dimension

$$
[\mathcal A_n]=4-n
$$

when the $S$-matrix delta function is stripped off. Thus a three-point amplitude has dimension one.

Angle and square brackets each have mass dimension one. The holomorphic formula has total bracket dimension

$$
a+b+c=-(h_1+h_2+h_3),
$$

so the coupling has dimension

$$
[g_{\rm H}]=1+h_1+h_2+h_3.
$$

The anti-holomorphic formula has bracket dimension

$$
a+b+c=h_1+h_2+h_3,
$$

so

$$
[g_{\overline{\rm H}}]=1-h_1-h_2-h_3.
$$

This is a useful diagnostic. A dimensionless coupling usually corresponds to a renormalizable interaction in four dimensions. A coupling with negative mass dimension signals a higher-derivative or gravitational interaction. A coupling with positive mass dimension signals a super-renormalizable interaction.

## Why three-point amplitudes matter

Three-point amplitudes are not directly measured as ordinary real scattering events for massless particles in flat space. Their importance is structural.

When an $n$-point amplitude factorizes on a pole, it behaves schematically as

$$
A_n
\xrightarrow{P^2\to0}
\sum_h
A_L(\ldots,P^h)\,
\frac{i}{P^2}\,
A_R((-P)^{-h},\ldots),
$$

where the sum runs over physical helicities of the intermediate on-shell state. If one side of the factorization has only three legs, the residue is controlled by a three-point amplitude.

This is why three-point amplitudes are the seeds of recursive constructions. Once the allowed three-point seeds are known, locality and factorization strongly constrain higher-point amplitudes. In favorable theories, this almost replaces Feynman diagrams.

## Common pitfalls

**Trying to use real three-point kinematics too literally.** Real massless three-point kinematics is degenerate. The useful nonzero amplitudes live naturally on complexified kinematics and then enter real scattering through residues and analytic continuation.

**Forgetting which branch you are on.** An expression built from angle brackets belongs to the holomorphic branch; one built from square brackets belongs to the anti-holomorphic branch. Mixing them at three points usually means you have left the special three-point support.

**Confusing color-ordered amplitudes with full amplitudes.** The compact Yang–Mills formulas above are kinematic partial amplitudes. The full gluon amplitude also contains color factors.

**Assuming little-group scaling proves an interaction exists.** Little-group scaling gives allowed kinematic structures. Dynamics, locality, gauge invariance, and the chosen Lagrangian decide which couplings are present.

**Treating negative bracket powers as ordinary poles in real phase space.** At three points, the branch structure is special. Apparent denominators should be interpreted inside complex on-shell kinematics and factorization, not as a physical three-particle singularity in real scattering.

**Forgetting coupling dimensions.** The all-plus and all-minus gauge amplitudes are allowed by little-group scaling, but they correspond to higher-derivative EFT operators, not to the ordinary Yang–Mills Lagrangian.

## Relations to other pages

- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) introduces the bracket conventions and little-group weights used here.
- [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/) explains how the color factors are stripped from non-Abelian amplitudes before writing compact partial amplitudes.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) gives the Lagrangian route to the three-gluon vertex.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) shows the conventional color-dressed tree-level view.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) and [Discontinuities and Branch Cuts](/perturbative-qft/unitarity-analyticity-dispersion/discontinuities-and-branch-cuts/) explain why residues and analytic continuation are central in scattering theory.
- Later pages on color-ordered amplitudes and BCFW recursion use these three-point amplitudes as inputs.

## Research status

- **Established:** The branch structure of complex massless three-point kinematics and the little-group classification of four-dimensional three-point amplitudes are standard tools in modern scattering amplitudes.
- **Active:** Massive three-point amplitudes, higher-spin constraints, supersymmetric three-point superamplitudes, curved-background generalizations, and celestial transforms remain active topics.
- **Speculative:** The basic classification on this page is not speculative. Some broader attempts to derive allowed theories primarily from three-point data and consistency are research programs with theory-dependent assumptions.

## Exercises

### Exercise 1: Vanishing invariants

Show that three massless outgoing momenta satisfying $p_1+p_2+p_3=0$ obey $s_{12}=s_{23}=s_{31}=0$.

<details>
<summary><strong>Solution</strong></summary>

Using momentum conservation,

$$
p_1+p_2=-p_3.
$$

Squaring gives

$$
(p_1+p_2)^2=p_3^2.
$$

Since all particles are massless, $p_3^2=0$. Therefore

$$
s_{12}=(p_1+p_2)^2=0.
$$

The same argument with cyclic relabeling gives $s_{23}=0$ and $s_{31}=0$.

</details>

### Exercise 2: Solve the little-group equations

Assume a holomorphic three-point amplitude has the form

$$
A_3=g\langle12\rangle^a\langle23\rangle^b\langle31\rangle^c.
$$

Derive the exponents in terms of helicities $h_1,h_2,h_3$.

<details>
<summary><strong>Solution</strong></summary>

Under little-group scaling, leg $1$ appears in $\langle12\rangle$ and $\langle31\rangle$, so

$$
a+c=-2h_1.
$$

Similarly,

$$
a+b=-2h_2,
\qquad
b+c=-2h_3.
$$

Adding the first two equations and subtracting the third gives

$$
2a=-2h_1-2h_2+2h_3,
$$

so

$$
a=h_3-h_1-h_2.
$$

The other two are obtained cyclically:

$$
b=h_1-h_2-h_3,
\qquad
c=h_2-h_3-h_1.
$$

</details>

### Exercise 3: Check the Yang–Mills weights

Verify that

$$
A_3(1^-,2^-,3^+)
=
 g\frac{\langle12\rangle^3}{\langle23\rangle\langle31\rangle}
$$

has the correct little-group weights.

<details>
<summary><strong>Solution</strong></summary>

For leg $1$, the numerator gives $t_1^3$ and the denominator gives one power of $t_1$ from $\langle31\rangle$. The net weight is $t_1^2$, matching $h_1=-1$.

For leg $2$, the numerator gives $t_2^3$ and the denominator gives one power from $\langle23\rangle$. The net weight is $t_2^2$, matching $h_2=-1$.

For leg $3$, the numerator gives no power. The denominator gives $t_3^2$, so the net weight is $t_3^{-2}$, matching $h_3=+1$.

</details>

### Exercise 4: Coupling dimension of gravity

Use mass dimension to show that the three-graviton amplitude

$$
M_3(1^{-2},2^{-2},3^{+2})
=
\kappa
\frac{\langle12\rangle^6}{\langle23\rangle^2\langle31\rangle^2}
$$

requires $[\kappa]=-1$ in four dimensions.

<details>
<summary><strong>Solution</strong></summary>

Each spinor bracket has mass dimension one. The bracket factor has dimension

$$
6-2-2=2.
$$

A three-point amplitude in four dimensions has dimension one. Therefore

$$
[\kappa]+2=1,
$$

so

$$
[\kappa]=-1.
$$

This agrees with the gravitational coupling in four dimensions.

</details>

### Exercise 5: All-minus gauge amplitude

Use little-group scaling to find the holomorphic all-minus three-gluon structure.

<details>
<summary><strong>Solution</strong></summary>

Set

$$
h_1=h_2=h_3=-1.
$$

For the holomorphic exponents,

$$
a=h_3-h_1-h_2=-1+1+1=1,
$$

and similarly $b=c=1$. Therefore

$$
A_3(1^-,2^-,3^-)
\propto
\langle12\rangle\langle23\rangle\langle31\rangle.
$$

This is not the ordinary Yang–Mills three-gluon amplitude with dimensionless coupling. It has bracket dimension three, so its coefficient has dimension $-2$ in four dimensions. It corresponds to a higher-derivative EFT interaction.

</details>

## References

- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” for spinor-helicity methods, color ordering, and compact tree amplitudes.
- M. L. Mangano and S. J. Parke, “Multiparton Amplitudes in Gauge Theories,” for classic color-decomposition and helicity-amplitude technology.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a systematic treatment of three-point amplitudes, little-group scaling, and recursion.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for gluon amplitudes and spinor-helicity methods in a QFT textbook.
- M. Srednicki, *Quantum Field Theory*, §50, for massless particles and spinor-helicity conventions.
- P. Benincasa and F. Cachazo, “Consistency Conditions on the S-Matrix of Massless Particles,” for an on-shell consistency perspective on massless interactions.

## Version history

- **2026-06-13:** Initial polished page. Establishes complex three-point kinematic branches, little-group classification, standard Yang–Mills and gravity examples, coupling-dimension checks, and factorization motivation.
