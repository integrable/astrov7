---
title: "Yang–Mills Feynman Rules"
description: "A convention-consistent dictionary for covariant-gauge Yang–Mills propagators, matter vertices, ghost vertices, and three- and four-gluon interactions."
sidebar:
  label: "Yang–Mills Rules"
  order: 4
level: Graduate
status: "Polished draft"
source: "Faddeev and Popov 1967; Weinberg Vol. II ch. 15; Srednicki §§69–72; Schwartz chs. 25–26; Coleman ch. 47"
topics:
  - Yang–Mills theory
  - Feynman rules
  - gluon self-interactions
  - ghost vertices
  - color factors
canonicalTopics:
  - yang-mills-feynman-rules
  - gluon-propagator
  - three-gluon-vertex
  - four-gluon-vertex
  - ghost-gluon-vertex
researchStatus:
  established:
    - "Covariant-gauge Yang–Mills Feynman rules are the standard perturbative rules for non-Abelian gauge bosons, ghosts, and matter fields."
  active:
    - "Beyond ordinary perturbation theory, gauge fixing, Gribov regions, lattice definitions, and gauge-invariant nonperturbative observables require additional tools beyond this local weak-field rule dictionary."
---

## Summary

Yang–Mills Feynman rules are the momentum-space rules for perturbation theory in a gauge-fixed non-Abelian gauge theory. Compared with QED, there are three new features:

1. gauge bosons carry gauge charge;
2. the Yang–Mills field strength is nonlinear;
3. covariant gauge fixing produces interacting Faddeev–Popov ghosts.

In qft.org conventions,

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

and

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

The gauge-fixed perturbative Lagrangian is

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2
+\partial^\mu\bar c^a(D_\mu c)^a
+\overline\psi(i\gamma^\mu D_\mu-m)\psi.
$$

From this single line come the gluon propagator, ghost propagator, quark propagator, quark–gluon vertex, ghost–gluon vertex, and the three- and four-gluon vertices. Individual Yang–Mills diagrams are usually gauge dependent. Gauge-invariant amplitudes and observables emerge only after summing the required diagrams, including ghost and counterterm contributions.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![The gauge-fixed Yang–Mills action produces propagators, matter vertices, gluon self-interactions, and ghost interactions](/figures/perturbative-qft/yang-mills-feynman-rules.svg)

<figcaption>

A gauge-fixed Yang–Mills Lagrangian produces more than a photon-like propagator. Non-Abelian field strength generates three- and four-gauge-boson vertices, while the Faddeev–Popov determinant generates ghost propagators and ghost–gluon vertices. The whole rule set, not any single diagram, realizes gauge invariance perturbatively.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/), [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), and [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/). For the scalar and spinor diagrammatic conventions, review [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) and [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/).

## Core idea

Yang–Mills perturbation theory starts from the same diagrammatic logic as scalar theory: split the action into a quadratic part and an interaction part. The quadratic part gives propagators. The interaction part gives vertices. The difference is that gauge redundancy forces a gauge-fixing term, and non-Abelian gauge invariance forces the gauge bosons to interact with themselves.

The whole calculation is controlled by a chain of ideas: non-Abelian gauge symmetry forces a nonlinear field strength and covariant derivative; gauge fixing and the Faddeev–Popov determinant make the perturbative path integral well defined; and the resulting gluon, ghost, and matter rules are tied together by Ward and Slavnov–Taylor identities.

The rules below are written for covariant gauges. They are local weak-field rules around the perturbative vacuum. They are not a gauge-invariant definition of the full nonperturbative theory, and they are not meant to replace Wilson loops, lattice definitions, or BRST cohomology.

## Setup and conventions

We use the qft.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
$$

and the amplitude convention

$$
\langle f|iT|i\rangle
=i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi}.
$$

The gauge algebra has Hermitian generators,

$$
[T^a,T^b]=if^{abc}T^c.
$$

For fundamental $SU(N)$ generators, we use

$$
\operatorname{tr}(T^aT^b)=T_F\delta^{ab},
\qquad
T_F=\frac12.
$$

The standard quadratic Casimirs are

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

The covariant derivative on fundamental matter is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

The adjoint covariant derivative acting on a ghost or adjoint field is

$$
(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

With these conventions,

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

All momenta in vertex rules are taken incoming unless stated otherwise. Changing the convention for $D_\mu$, the sign of $F_{\mu\nu}^a$, or the direction of ghost arrows changes individual displayed signs. The full rule set must be translated together.

## The gauge-fixed Lagrangian

The Yang–Mills Lagrangian with Dirac matter is

$$
\mathcal L_{\rm YM+matter}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
+\overline\psi(i\gamma^\mu D_\mu-m)\psi.
$$

Covariant gauge fixing adds

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial_\mu A^{a\mu})^2.
$$

The Faddeev–Popov determinant is represented by ghost fields,

$$
\mathcal L_{\rm gh}
=
\partial^\mu\bar c^a(D_\mu c)^a
=
\partial^\mu\bar c^a\partial_\mu c^a
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

Putting the pieces together,

$$
\mathcal L
=
\mathcal L_2+\mathcal L_{\rm int},
$$

where $\mathcal L_2$ contains the quadratic terms defining propagators, and $\mathcal L_{\rm int}$ contains the quark–gluon, ghost–gluon, three-gluon, and four-gluon interactions.

The Abelian limit is a useful check. If $f^{abc}=0$, then the three-gluon, four-gluon, and ghost–gluon vertices vanish, and the ghost determinant becomes field independent. What remains is many copies of photon-like gauge fields, plus whatever matter couplings are present.

## Propagators

### Gluon propagator

In a covariant gauge, the gauge-field propagator is

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[
\eta_{\mu\nu}
-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}
\right].
$$

In Feynman gauge, $\xi=1$, this becomes

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\eta_{\mu\nu}\delta^{ab}}{k^2+i\epsilon}.
$$

In Landau gauge, $\xi\to0$, the propagator is transverse in the limiting sense appropriate to the pole prescription.

### Ghost propagator

From

$$
\mathcal L_{\rm gh,0}=\partial^\mu\bar c^a\partial_\mu c^a,
$$

the ghost propagator is

$$
\frac{i\delta^{ab}}{k^2+i\epsilon}.
$$

Ghost fields are Lorentz scalars but Grassmann odd. Therefore closed ghost loops carry an extra factor of $-1$.

### Fermion propagator

For a Dirac fermion of mass $m$ in representation $R$,

$$
S_{ij}(p)
=
\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}\delta_{ij},
$$

where $i,j$ are representation indices. For several flavors, add flavor labels and masses as needed.

## Matter and ghost vertices

### Quark–gluon vertex

The matter interaction follows from

$$
\overline\psi i\gamma^\mu D_\mu\psi
=
\overline\psi i\gamma^\mu\partial_\mu\psi
-g\overline\psi\gamma^\mu A_\mu^aT^a\psi.
$$

Thus the quark–gluon vertex is

$$
\text{quark–gluon vertex:}\qquad -ig\gamma^\mu T^a.
$$

For matter in a representation $R$, replace $T^a$ by the generator $T_R^a$ in that representation.

### Ghost–gluon vertex

The ghost interaction is

$$
\mathcal L_{\rm gh,int}
=-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

With incoming antighost momentum $p$ flowing into the derivative, the vertex is

$$
\text{ghost–gluon vertex:}\qquad -g f^{abc}p^\mu.
$$

This convention matches the earlier ghost page: the derivative acts on $\bar c^a$. If instead a source assigns the momentum to the ghost, reverses the ghost-arrow convention, or integrates by parts before reading off the rule, the displayed sign can move. The combination of arrow convention, momentum convention, and loop sign is the invariant rule.

## Gauge-boson self-interactions

The self-interactions are the signature of non-Abelian gauge theory. They come from the nonlinear term in

$$
F_{\mu\nu}^a
=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

### Three-gluon vertex

For incoming labels

$$
(a,\mu,p),
\qquad
(b,\nu,q),
\qquad
(c,\rho,r),
$$

with

$$
p+q+r=0,
$$

the three-gluon vertex in the convention used in this chapter is

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

This formula is antisymmetric in color and arranged so that exchanging two complete gluon labels, including color, Lorentz index, and momentum, gives the appropriate Bose symmetry of the full vertex.

### Four-gluon vertex

For incoming gluons

$$
(a,\mu),\quad (b,\nu),\quad (c,\rho),\quad (d,\sigma),
$$

the four-gluon vertex is

$$
\begin{aligned}
V^{abcd}_{\mu\nu\rho\sigma}
&=
-ig^2\Big[
 f^{abe}f^{cde}
 (\eta_{\mu\rho}\eta_{\nu\sigma}-\eta_{\mu\sigma}\eta_{\nu\rho})\\
&\qquad
+f^{ace}f^{bde}
 (\eta_{\mu\nu}\eta_{\rho\sigma}-\eta_{\mu\sigma}\eta_{\nu\rho})\\
&\qquad
+f^{ade}f^{bce}
 (\eta_{\mu\nu}\eta_{\rho\sigma}-\eta_{\mu\rho}\eta_{\nu\sigma})
\Big].
\end{aligned}
$$

This is one of the easiest rules to mistype. When comparing references, check the sign convention for $F_{\mu\nu}^a$, the all-momenta-incoming convention, and the placement of color labels. In practical calculations, color-ordered rules or color-flow notation often give cleaner bookkeeping.

## Complete covariant-gauge rule table

For quick reference, the basic rules are:

| Object | Rule |
|---|---|
| Gluon propagator | $\displaystyle \frac{-i\delta^{ab}}{k^2+i\epsilon}\left[\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right]$ |
| Feynman-gauge gluon propagator | $\displaystyle \frac{-i\eta_{\mu\nu}\delta^{ab}}{k^2+i\epsilon}$ |
| Ghost propagator | $\displaystyle \frac{i\delta^{ab}}{k^2+i\epsilon}$ |
| Fermion propagator | $\displaystyle \frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}\delta_{ij}$ |
| Quark–gluon vertex | $\displaystyle -ig\gamma^\mu T^a$ |
| Ghost–gluon vertex | $\displaystyle -g f^{abc}p^\mu$, where $p$ is incoming antighost momentum |
| Three-gluon vertex | $\displaystyle gf^{abc}[\eta_{\mu\nu}(p-q)_\rho+\eta_{\nu\rho}(q-r)_\mu+\eta_{\rho\mu}(r-p)_\nu]$ |
| Four-gluon vertex | $\displaystyle -ig^2$ times the color–metric tensor combination displayed above |
| Closed ghost loop | extra factor $-1$ |
| Closed fermion loop | extra factor $-1$ |
| Loop momentum | $\displaystyle \int\frac{d^d\ell}{(2\pi)^d}$ in dimensional regularization |

The table is a rule dictionary, not a proof of gauge invariance. To check a calculation, combine it with the relevant Ward, Slavnov–Taylor, BRST, color, and renormalization identities.

## Example: quark scattering by gluon exchange

For distinct quark flavors,

$$
q_i(p_1)+q'_k(p_2)\to q_j(p_3)+q'_l(p_4),
$$

the $t$-channel gluon-exchange amplitude in Feynman gauge is

$$
\mathcal M_t
=
\frac{g^2}{t+i\epsilon}
\left[\overline u(p_3)\gamma^\mu u(p_1)\right]
\left[\overline u(p_4)\gamma_\mu u(p_2)\right]
(T^a)_{ji}(T^a)_{lk}.
$$

This is the non-Abelian cousin of QED current-current exchange. The new ingredient is the color matrix product

$$
(T^a)_{ji}(T^a)_{lk},
$$

which must be squared, summed, and averaged carefully when computing cross sections.

## Example: gluon self-energy at one loop

In pure Yang–Mills theory, the one-loop gluon two-point function receives contributions from the gluon loop, the four-gluon tadpole, and the ghost loop. With matter present, add quark loops. The ghost loop is not optional: it cancels unphysical gauge-polarization contributions and is required for the correct transverse structure of the polarization tensor.

The result has the color structure

$$
\Pi_{\mu\nu}^{ab}(q)=\delta^{ab}\Pi_{\mu\nu}(q),
$$

and gauge invariance implies the transverse form

$$
q^\mu\Pi_{\mu\nu}^{ab}(q)=0
$$

for the properly renormalized gauge-boson self-energy in a gauge-invariant scheme and within the appropriate identity structure. Diagram by diagram, especially away from special gauges or before all pieces are included, this transversality is not guaranteed.

## How to use the rules without getting lost

A reliable Yang–Mills calculation has a rhythm:

1. Choose a gauge and write the complete gauge-fixed Lagrangian.
2. State the momentum, color, and arrow conventions.
3. Generate all diagrams at the required order, including ghosts and counterterms.
4. Keep color factors symbolic until simplification is safe.
5. Check Ward or Slavnov–Taylor identities on gauge-invariant sets.
6. Only then square, sum, average, integrate phase space, or extract renormalization constants.

Most errors in first Yang–Mills calculations are not deep physics errors. They are missing ghost diagrams, missing four-gluon diagrams, inconsistent all-incoming momentum conventions, or color indices silently treated as commuting numbers. Gauge theory is not forgiving about bookkeeping: a small sign, color-ordering, or missing-diagram error can invalidate an otherwise sensible calculation.

## Common pitfalls

**Using only photon intuition.** Gluons carry gauge charge. They have three- and four-gluon interactions, and the gauge-fixed theory has ghost interactions.

**Forgetting ghost loops.** Ghosts are not external particles, but they do appear in internal loops. Omitting them breaks the gauge-theory identity structure.

**Reading off a vertex sign without checking conventions.** The signs of the quark–gluon, three-gluon, and ghost–gluon vertices depend on the convention for $D_\mu$, $F_{\mu\nu}^a$, and all-momenta-incoming assignments.

**Treating color factors as numbers too early.** Color matrices do not generally commute. Keep representation indices or trace structures explicit until a valid color identity is applied.

**Checking gauge invariance diagram by diagram.** Individual non-Abelian diagrams are rarely gauge invariant. The identities apply to complete gauge-invariant sums, including ghost and counterterm diagrams when relevant.

**Confusing gauge-fixed rules with gauge-invariant observables.** Propagators and ghost fields depend on gauge fixing. Wilson loops, S-matrix elements between physical states, inclusive cross sections, and gauge-invariant operator correlators are the physical objects.

## Relations to other pages

- [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) derives the covariant-gauge gluon propagator.
- [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) derives the ghost propagator, ghost–gluon vertex, and closed ghost-loop sign.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) applies the quark–gluon and gluon self-interaction rules to tree amplitudes.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) gives the Abelian identity whose non-Abelian descendants become Slavnov–Taylor identities.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how counterterm vertices enter loop-level rule dictionaries.
- A later color-factors page will systematize the color algebra used in squared amplitudes and loop calculations.

## Research status

The covariant-gauge Yang–Mills Feynman rules are textbook-standard. They are the starting point for perturbative QCD, electroweak gauge-theory calculations, beta-function computations, and modern amplitude methods.

The subtle issues arise beyond the local perturbative expansion: nonperturbative gauge fixing, Gribov copies, confinement, lattice definitions, gauge-invariant operator bases, real-time gauge theory, and all-order organization by BRST and Slavnov–Taylor identities. Those topics refine the meaning and scope of the rules; they do not change the ordinary weak-coupling rule dictionary used here.

## Exercises

### Exercise 1: Abelian limit

Set $f^{abc}=0$ in the Yang–Mills Feynman rules. Which vertices disappear?

<details>
<summary><strong>Solution</strong></summary>

The three-gluon vertex is proportional to $f^{abc}$, so it vanishes. The four-gluon vertex is proportional to products of structure constants, so it also vanishes. The ghost–gluon vertex is proportional to $f^{abc}$, so it vanishes as well.

The ghost propagator may still be formally present if one writes a ghost action, but the ghosts are free and decouple because the Abelian Faddeev–Popov determinant is field independent in ordinary covariant gauges. What remains is a photon-like gauge-field propagator and matter vertices determined by the charges.

</details>

### Exercise 2: Quark–gluon vertex sign

Starting from

$$
\overline\psi i\gamma^\mu D_\mu\psi,
\qquad
D_\mu=\partial_\mu+igA_\mu^aT^a,
$$

show that the interaction term is

$$
-g\overline\psi\gamma^\mu A_\mu^aT^a\psi.
$$

<details>
<summary><strong>Solution</strong></summary>

Insert the covariant derivative:

$$
\overline\psi i\gamma^\mu D_\mu\psi
=
\overline\psi i\gamma^\mu\partial_\mu\psi
+\overline\psi i\gamma^\mu(igA_\mu^aT^a)\psi.
$$

Since $i\times i=-1$, the second term is

$$
-g\overline\psi\gamma^\mu A_\mu^aT^a\psi.
$$

In the perturbative expansion, this interaction gives the vertex factor

$$
-ig\gamma^\mu T^a.
$$

</details>

### Exercise 3: Ghost–gluon vertex momentum

Given

$$
\mathcal L_{\rm gh,int}
=-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c,
$$

explain why the ghost–gluon vertex is proportional to the antighost momentum.

<details>
<summary><strong>Solution</strong></summary>

The derivative acts on the antighost field $\bar c^a$. In momentum space, a derivative acting on a field produces a factor proportional to that field's momentum. With the all-momenta-incoming and ghost-arrow convention used on this page, this gives the vertex factor

$$
-g f^{abc}p^\mu,
$$

where $p$ is the incoming antighost momentum. A different arrow convention or an integration by parts can move the sign or momentum label, so the convention must be stated along with the rule.

</details>

### Exercise 4: Color diagonal self-energy

Use

$$
f^{acd}f^{bcd}=C_A\delta^{ab}
$$

to show that the adjoint color structure of a one-loop gluon or ghost contribution to the gluon two-point function is proportional to $\delta^{ab}$.

<details>
<summary><strong>Solution</strong></summary>

A two-point function has two external adjoint color indices, say $a$ and $b$. In a loop built from two three-gluon or two ghost–gluon vertices, the internal adjoint indices are summed. The color factor has the form

$$
f^{acd}f^{bcd}.
$$

By definition of the adjoint Casimir,

$$
f^{acd}f^{bcd}=C_A\delta^{ab}.
$$

Therefore the two-point function is color diagonal:

$$
\Pi_{\mu\nu}^{ab}(q)=\delta^{ab}\Pi_{\mu\nu}(q).
$$

</details>

### Exercise 5: Longitudinal propagator check

In Feynman gauge the gluon propagator numerator is $\eta_{\mu\nu}$. In a general covariant gauge it also contains a term proportional to $k_\mu k_\nu$. Why should a physical answer not depend on this term?

<details>
<summary><strong>Solution</strong></summary>

The $k_\mu k_\nu$ term represents the gauge-dependent longitudinal part of the internal gauge-field propagator. Physical states and gauge-invariant observables cannot depend on the arbitrary gauge parameter $\xi$. In simple Abelian current-current exchange, the term vanishes by current conservation. In non-Abelian calculations, the cancellation is distributed among gauge-boson, ghost, matter, and counterterm diagrams and is organized by Slavnov–Taylor or BRST identities.

Thus the term can affect individual diagrams, but not the final gauge-invariant answer.

</details>

## References

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 15, for non-Abelian gauge quantization, ghosts, BRST symmetry, and gauge-theory Feynman rules.
- M. Srednicki, *Quantum Field Theory*, §§69–72, for non-Abelian gauge theory and its perturbative Feynman rules.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 25–26, for Yang–Mills theory, QCD rules, color factors, and one-loop applications.
- S. Coleman, *Lectures on Quantum Field Theory*, ch. 47, for quantizing non-Abelian gauge fields and deriving the corresponding perturbative rules.

## Version history

- **2026-06-13:** Initial polished draft for the Gauge-Theory Perturbation Theory chapter of QFT.org.
