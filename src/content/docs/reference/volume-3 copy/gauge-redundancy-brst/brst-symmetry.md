---
title: "BRST Symmetry"
description: "Introduces BRST symmetry as the nilpotent remnant of gauge redundancy in gauge-fixed path integrals and derives its transformations for Yang–Mills theory."
sidebar:
  label: "BRST Symmetry"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.5–15.8; Coleman, Lectures Ch. 31; Zinn-Justin, BRST and the Zinn-Justin equation; standard BV-BRST treatments."
topics:
  - BRST symmetry
  - gauge fixing
  - Faddeev-Popov ghosts
  - nilpotent differential
  - Slavnov-Taylor identities
  - gauge-fixed Yang-Mills theory
canonicalTopics:
  - brst-symmetry
  - brst-differential
  - nilpotent-charge
  - gauge-fixed-action
  - slavnov-taylor-identity
researchStatus:
  established:
    - "BRST symmetry is the standard organizing symmetry of perturbatively gauge-fixed Yang–Mills theory and packages gauge invariance, ghost interactions, and Slavnov–Taylor identities."
    - "When the gauge symmetry is anomaly-free, BRST symmetry makes gauge-parameter independence and the removal of unphysical polarizations precise."
  active:
    - "The global status of BRST beyond perturbation theory can be subtle in the presence of Gribov copies, boundaries, large gauge transformations, and non-Lagrangian gauge-like structures."
---

## Summary

Gauge fixing makes gauge theory calculable, but it also hides the original gauge redundancy. The gauge-fixed Lagrangian contains a gauge-fixing term and Faddeev–Popov ghosts, and it is no longer invariant under the original local gauge transformations as ordinary transformations of $A_\mu$ alone. BRST symmetry is the replacement structure that survives.

The slogan is:

$$
\text{BRST} = \text{gauge redundancy with the gauge parameter replaced by a ghost}.
$$

For Yang–Mills theory, the BRST differential $s$ acts schematically as

$$
sA_\mu=\mathcal D_\mu c,
\qquad
sc=-igc^2,
\qquad
s\bar c=B,
\qquad
sB=0.
$$

Here $c$ is the ghost, $\bar c$ is the antighost, and $B$ is an auxiliary Nakanishi–Lautrup field. The crucial property is nilpotence:

$$
s^2=0.
$$

This one equation is the small hinge on which a big door swings. It lets us define BRST cohomology, identify physical states and operators, prove gauge-fixing independence, organize counterterms, and state gauge anomalies as obstructions to quantum BRST symmetry.

<figure class="doc-figure" style="--figure-width: 52rem;">

![BRST symmetry as a nilpotent differential built from gauge transformations, ghost fields, the gauge-fixing fermion, and the gauge-fixed action.](/figures/symmetry-anomalies-topology/brst-differential-map.svg)

<figcaption>

BRST symmetry turns infinitesimal gauge redundancy into a nilpotent fermionic differential $s$. The gauge-fixing and ghost terms are compactly written as $s\Psi$, where $\Psi$ is the gauge-fixing fermion. The resulting symmetry gives the Slavnov–Taylor identities.

</figcaption>
</figure>

BRST symmetry is not an extra spacetime supersymmetry. It is an anticommuting global symmetry of the gauge-fixed description. Its job is less glamorous and more important: it remembers exactly enough of gauge redundancy to make the calculation honest.

## Prerequisites

Read [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/) and [Faddeev–Popov Ghosts](/symmetry-anomalies-topology/gauge-redundancy-brst/faddeev-popov-ghosts/) first. You should know why the Faddeev–Popov determinant appears and why non-Abelian ghosts interact with gauge fields.

It also helps to know [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), because BRST symmetry has a conserved current and charge in the gauge-fixed theory, and [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), because the most useful BRST identities come from change of variables in the path integral.

## Core idea

Start with a gauge-invariant classical action,

$$
S_{\rm YM}[A]=-\frac{1}{2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F^{\mu\nu}.
$$

Gauge fixing introduces a condition $\mathcal F^a[A]=0$ and a Faddeev–Popov determinant. Exponentiating that determinant introduces ghost fields. The gauge-fixed action has the form

$$
S_{\rm fixed}=S_{\rm YM}+S_{\rm gf}+S_{\rm gh}.
$$

Although $S_{\rm gf}+S_{\rm gh}$ is not invariant under the original gauge transformation of $A_\mu$ alone, it is invariant under a new fermionic transformation that also moves $c$, $\bar c$, and $B$. That transformation is BRST.

The ghost $c$ plays the role of an infinitesimal gauge parameter, except that it is Grassmann odd and carries ghost number $+1$. The BRST differential therefore raises ghost number by one:

$$
\operatorname{gh}(sX)=\operatorname{gh}(X)+1.
$$

The nilpotence $s^2=0$ is the algebraic memory of the closure of gauge transformations. Once this nilpotence exists, one can form a cohomology. The next page explains why this cohomology, not the full gauge-fixed field space, is the physical content.

## Setup and conventions

Use the same convention as the previous pages in this chapter. The gauge field is Lie-algebra valued,

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators. Matter fields transform as $\psi\mapsto U^{-1}\psi$, and the covariant derivative is

$$
D_\mu=\partial_\mu+igA_\mu.
$$

The gauge field transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

For $U=1+ig\alpha+O(\alpha^2)$,

$$
\delta_\alpha A_\mu=\mathcal D_\mu\alpha
=\partial_\mu\alpha+ig[A_\mu,\alpha].
$$

The BRST differential is obtained by replacing $\alpha$ by the ghost $c$ and extending the action to all fields:

$$
sA_\mu=\mathcal D_\mu c,
\qquad
sc=-igc^2,
\qquad
s\bar c=B,
\qquad
sB=0.
$$

In components, the ghost transformation is equivalently

$$
sc^a=\frac{g}{2}f^{abc}c^bc^c,
$$

with this page’s convention for $D_\mu$ and the gauge transformation of $A_\mu$.

:::note[Convention-sensitive source note]
Many books use $D_\mu=\partial_\mu-igA_\mu$ and matter transformation $\psi\mapsto U\psi$. Then signs in $sA_\mu$, $sc$, and the ghost interaction change. The invariant content is the nilpotent BRST differential associated with the gauge algebra and the Faddeev–Popov determinant, not a particular sign convention for $D_\mu$.
:::

The ghost-number assignments are

| Field | Grassmann parity | Ghost number |
|---|---:|---:|
| $A_\mu$ | even | $0$ |
| $c$ | odd | $+1$ |
| $\bar c$ | odd | $-1$ |
| $B$ | even | $0$ |

The BRST differential is Grassmann odd and has ghost number $+1$.

## Why the ghost transforms nonlinearly

The transformation of $c$ is not optional decoration. It is forced by nilpotence.

Since $c$ replaces the gauge parameter, the first guess is

$$
sA_\mu=\mathcal D_\mu c.
$$

But applying $s$ again to $A_\mu$ gives two kinds of terms: one from $sc$ and one from the fact that $\mathcal D_\mu$ contains $A_\mu$. In matrix notation, $s$ is a graded derivation, so

$$
s^2A_\mu
=\mathcal D_\mu(sc)+ig\{\mathcal D_\mu c,c\}.
$$

Choosing

$$
sc=-igc^2
$$

makes these terms cancel, because $\mathcal D_\mu(c^2)=(\mathcal D_\mu c)c+c(\mathcal D_\mu c)$. Thus

$$
s^2A_\mu=0.
$$

Similarly,

$$
s^2c=0,
$$

which follows from associativity of matrix multiplication and the Grassmann nature of the ghost. In components, this is the Jacobi identity for the Lie algebra in disguise.

This is the first nice moral of BRST: the ghost self-transformation is the gauge algebra written as a differential.

## The auxiliary field and off-shell nilpotence

The field $B^a$ is an auxiliary field. It has no propagating degree of freedom. Its main job is to make BRST nilpotence completely off shell:

$$
s\bar c^a=B^a,
\qquad
sB^a=0
\quad\Rightarrow\quad
s^2\bar c^a=0.
$$

If one eliminates $B^a$ immediately, the transformation of $\bar c^a$ becomes proportional to the gauge-fixing function, for example

$$
s\bar c^a=-\frac{1}{\xi}\partial^\mu A_\mu^a
$$

in a covariant gauge. Then $s^2\bar c^a=0$ holds only using equations of motion. That is acceptable for some calculations, but the auxiliary-field form is cleaner for explaining cohomology, gauge-fixing independence, and BV generalizations.

Tiny auxiliary fields, huge bookkeeping payoff. A very QFT bargain.

## Gauge fixing as a BRST-exact term

For covariant $R_\xi$ gauges, define the gauge-fixing fermion

$$
\Psi=\int d^4x\,\bar c^a\left(\mathcal F^a[A]+\frac{\xi}{2}B^a\right),
$$

where $\mathcal F^a[A]=\partial^\mu A_\mu^a$ for Lorenz gauge. The word “fermion” means that $\Psi$ is Grassmann odd and has ghost number $-1$.

Acting with $s$ gives

$$
s\Psi
=\int d^4x\left[
B^a\mathcal F^a[A]
+\frac{\xi}{2}B^aB^a
-\bar c^a\frac{\delta\mathcal F^a}{\delta A_\mu^b}\mathcal D_\mu^{bc}c^c
\right].
$$

For Lorenz gauge this is

$$
s\Psi
=\int d^4x\left[
B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu\mathcal D_\mu^{ab}c^b
\right].
$$

The gauge-fixed action is

$$
S_{\rm BRST}=S_{\rm YM}+s\Psi.
$$

Eliminating $B^a$ through its algebraic equation of motion,

$$
B^a=-\frac{1}{\xi}\partial^\mu A_\mu^a,
$$

gives

$$
\mathcal L_{\rm gf}
=-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2,
$$

and the usual ghost term

$$
\mathcal L_{\rm gh}
=-\bar c^a\partial^\mu\mathcal D_\mu^{ab}c^b.
$$

The BRST invariance of $S_{\rm BRST}$ is now almost too easy:

$$
sS_{\rm BRST}=sS_{\rm YM}+s^2\Psi=0.
$$

The first term vanishes because $S_{\rm YM}$ is gauge invariant, and the second because $s^2=0$.

## Gauge-parameter independence

A change of gauge condition changes $\Psi$. Suppose

$$
\Psi\mapsto\Psi+\delta\Psi.
$$

Then

$$
S_{\rm BRST}\mapsto S_{\rm BRST}+s\delta\Psi.
$$

For a BRST-closed observable $\mathcal O$, meaning

$$
s\mathcal O=0,
$$

the variation of its expectation value is formally proportional to the expectation value of a BRST-exact insertion:

$$
\delta\langle\mathcal O\rangle
\propto i\langle\mathcal O\,s\delta\Psi\rangle
= i\langle s(\mathcal O\,\delta\Psi)\rangle.
$$

If the path-integral measure is BRST invariant and there are no boundary contributions in field space, then

$$
\langle sX\rangle=0,
$$

so

$$
\delta\langle\mathcal O\rangle=0.
$$

This is the conceptual origin of gauge-fixing independence. It is also why anomalies are so serious: a quantum anomaly is precisely the failure of the measure or effective action to respect the symmetry that made this argument work.

## BRST Ward identities and Slavnov–Taylor identities

Because BRST is a change of variables of the gauge-fixed path integral, it gives Ward identities. In non-Abelian gauge theory these are usually called Slavnov–Taylor identities.

The simplest abstract form is

$$
\langle sX\rangle=0.
$$

Choosing different composite insertions $X$ produces relations among ghost, gauge-field, and matter correlation functions. These identities generalize the Ward–Takahashi identities of QED.

For example, in QED the Ward–Takahashi identity relates the electron-photon vertex to the electron propagator. In Yang–Mills theory, the corresponding identities are more elaborate because the gauge bosons self-interact and the ghosts do not decouple. BRST symmetry keeps all of this organized in one algebraic package.

At the level of the effective action, the Slavnov–Taylor identity is a functional equation. In a more advanced treatment, one introduces sources for BRST variations, or antifields in the BV formalism, and writes the identity as a master equation. The simple lesson for this page is enough:

$$
\text{BRST invariance controls the allowed quantum corrections.}
$$

## Abelian example

For QED, the gauge transformations are

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
\psi\mapsto e^{-ie\alpha}\psi.
$$

The BRST transformations are

$$
sA_\mu=\partial_\mu c,
\qquad
sc=0,
\qquad
s\psi=-iec\psi,
\qquad
s\bar\psi=ie\bar\psi c,
$$

along with

$$
s\bar c=B,
\qquad
sB=0.
$$

The Abelian ghost is free and decouples in ordinary linear covariant gauges because the Faddeev–Popov determinant is field-independent. But BRST is still useful: it packages gauge-fixing independence and identifies the physical photon polarizations.

The nilpotence on matter is worth checking. Since $c$ is Grassmann odd, $c^2=0$ in the Abelian case, and

$$
s^2\psi=-ie\,s(c\psi)
=-ie\left((sc)\psi-c\,s\psi\right)=0.
$$

## Non-Abelian example

In Yang–Mills theory with matter, the BRST transformation of a matter field in representation $R$ is

$$
s\psi=-igc_R\psi,
$$

where $c_R=c^aT_R^a$. The gauge field and ghost transform as

$$
sA_\mu=\partial_\mu c+ig[A_\mu,c],
\qquad
sc=-igc^2.
$$

The nonzero $sc$ reflects the non-Abelian gauge algebra. The ghost field itself carries adjoint gauge information, and its interactions are not optional. They are forced by the curvature of gauge orbit space, so to speak.

In perturbation theory, ghost loops cancel contributions from unphysical gauge polarizations. At the same time, the BRST Ward identities ensure that counterterms preserve the gauge structure. This is why non-Abelian gauge theory can be quantized covariantly without sacrificing unitarity or renormalizability.

## Relation to unitarity

Gauge-fixed Lagrangians contain unphysical fields. Covariant gauges include timelike and longitudinal gauge-field modes. Ghost fields are Grassmann-odd Lorentz scalars. None of these should appear as physical external particles.

BRST symmetry handles this by defining physical states through a cohomology:

$$
Q_{\rm B}|\psi\rangle=0,
\qquad
|\psi\rangle\sim |\psi\rangle+Q_{\rm B}|\chi\rangle.
$$

Here $Q_{\rm B}$ is the conserved BRST charge. States that differ by a BRST-exact state represent the same physical state. In this framework, unphysical polarizations and ghosts arrange themselves into BRST doublets or quartets that drop out of the cohomology.

This is the bridge from Lagrangian symmetry to physical Hilbert space. The next page develops it carefully.

## BRST symmetry versus gauge symmetry

It is easy to say something slightly wrong here, so let’s be precise.

Gauge symmetry is a redundancy of description. It acts locally and relates field configurations that represent the same physical configuration.

BRST symmetry is a global fermionic symmetry of the gauge-fixed action. It acts on $A_\mu$, ghosts, antighosts, auxiliary fields, and matter fields. It is global in the sense that the anticommuting transformation parameter is constant, while the ghost field $c(x)$ carries the local gauge-parameter dependence.

So BRST is not “the gauge symmetry after gauge fixing” in the naive sense. It is the algebraic remnant of gauge redundancy inside an enlarged field space. That enlarged field space includes fields whose only purpose is to represent the gauge-fixing Jacobian and the gauge-fixing condition.

This distinction matters because physical statements are not “BRST is spontaneously broken” or “BRST is a new force.” The physical statement is:

$$
\text{physical data live in BRST cohomology.}
$$

## Boundaries, zero modes, and anomalies

The compact formula $S_{\rm BRST}=S_{\rm YM}+s\Psi$ assumes a well-behaved perturbative gauge-fixing problem. Several effects complicate the story.

First, zero modes of the Faddeev–Popov operator require separate treatment. They can come from residual gauge transformations, global symmetries, or boundary conditions.

Second, boundaries can make some would-be gauge transformations physical. Then one must distinguish gauge redundancy from boundary symmetry. A BRST transformation that is pure gauge in the bulk may carry edge information at the boundary.

Third, the path-integral measure may fail to be BRST invariant. That failure is a gauge anomaly. In a gauge theory, this is not a harmless breaking of a global symmetry. It is an obstruction to consistently defining the quantum theory with the claimed gauge redundancy.

In equations, a quantum effective action $\Gamma$ should satisfy a BRST identity of the schematic form

$$
s\Gamma=0.
$$

An anomaly has the form

$$
s\Gamma=\mathcal A,
\qquad
s\mathcal A=0,
$$

where $\mathcal A$ cannot be removed by adding a local counterterm. This is the BRST version of the Wess–Zumino consistency condition.

## Common pitfalls

**Pitfall: thinking ghosts are physical particles.** Faddeev–Popov ghosts are fields in a gauge-fixed redundant description. They do not appear as external physical asymptotic states.

**Pitfall: treating BRST as ordinary supersymmetry.** BRST is Grassmann odd, but it is not a spacetime supersymmetry. It does not pair physical bosons and fermions into particle supermultiplets.

**Pitfall: dropping the nonlinear ghost transformation.** In a non-Abelian theory, $sc=-igc^2$ is forced by nilpotence. Setting $sc=0$ would describe an Abelian algebra, not Yang–Mills theory.

**Pitfall: eliminating the auxiliary field too early.** Without $B$, BRST nilpotence on $\bar c$ can become on-shell. That is fine for some calculations but obscures the clean cohomological structure.

**Pitfall: saying the gauge-fixed action is not gauge invariant, therefore gauge invariance is lost.** The original redundancy is hidden by gauge fixing, but BRST symmetry preserves its consequences in the enlarged field space.

**Pitfall: ignoring boundaries.** BRST-exact arguments assume that no boundary terms in spacetime or field space contribute. Edge modes, asymptotic symmetries, and Gribov horizons can invalidate naive manipulations.

## Relations to other pages

This page builds directly on [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/) and [Faddeev–Popov Ghosts](/symmetry-anomalies-topology/gauge-redundancy-brst/faddeev-popov-ghosts/). It prepares [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/), where physical states and operators are identified as cohomology classes.

Later pages use this material in [Physical State Space](/symmetry-anomalies-topology/gauge-redundancy-brst/physical-state-space/), [BV Formalism Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/bv-formalism-preview/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), and the gauge-theory volume’s treatment of Slavnov–Taylor identities and renormalization.

## Research status

Perturbative BRST symmetry is established technology. It is one of the standard ways to formulate covariant quantization of Yang–Mills theory, prove gauge-parameter independence of physical quantities, and constrain renormalization.

The nonperturbative and global status of BRST is subtler. Gribov copies, gauge-fixing horizons, boundaries, large gauge transformations, and non-Lagrangian theories all require care. In modern language, BRST is also the entry point to BV quantization, derived geometry, and the local cohomology of gauge theories.

## Exercises

### Exercise 1. Nilpotence on the gauge field

Using matrix notation, $sA_\mu=\mathcal D_\mu c$ and $sc=-igc^2$, show that $s^2A_\mu=0$.

<details><summary><strong>Solution</strong></summary>

Because $s$ is a graded derivation,

$$
s^2A_\mu=s(\mathcal D_\mu c)
=\mathcal D_\mu(sc)+ig\{\mathcal D_\mu c,c\}.
$$

Substitute $sc=-igc^2$:

$$
\mathcal D_\mu(sc)
=-ig\mathcal D_\mu(c^2)
=-ig\left((\mathcal D_\mu c)c+c(\mathcal D_\mu c)\right).
$$

Also,

$$
ig\{\mathcal D_\mu c,c\}
=ig\left((\mathcal D_\mu c)c+c(\mathcal D_\mu c)\right).
$$

The two terms cancel, so

$$
s^2A_\mu=0.
$$

</details>

### Exercise 2. Eliminating the auxiliary field

Starting from

$$
\mathcal L_B=B^a\mathcal F^a+\frac{\xi}{2}B^aB^a,
$$

show that eliminating $B^a$ gives $\mathcal L_{\rm gf}=-(\mathcal F^a\mathcal F^a)/(2\xi)$.

<details><summary><strong>Solution</strong></summary>

The algebraic equation of motion is

$$
0=\frac{\partial\mathcal L_B}{\partial B^a}
=\mathcal F^a+\xi B^a.
$$

Thus

$$
B^a=-\frac{1}{\xi}\mathcal F^a.
$$

Substitute this back:

$$
\mathcal L_B
=-\frac{1}{\xi}\mathcal F^a\mathcal F^a
+\frac{\xi}{2}\frac{1}{\xi^2}\mathcal F^a\mathcal F^a
=-\frac{1}{2\xi}\mathcal F^a\mathcal F^a.
$$

For $\mathcal F^a=\partial^\mu A_\mu^a$, this is the usual covariant gauge-fixing term.

</details>

### Exercise 3. Gauge-fixing independence as a BRST-exact variation

Assume the path-integral measure is BRST invariant. Show that a deformation $S\mapsto S+s\delta\Psi$ does not change the expectation value of a BRST-closed observable $\mathcal O$, to first order in $\delta\Psi$.

<details><summary><strong>Solution</strong></summary>

To first order,

$$
\delta\langle\mathcal O\rangle
=i\langle\mathcal O\,s\delta\Psi\rangle
-i\langle\mathcal O\rangle\langle s\delta\Psi\rangle.
$$

The second term vanishes because $\langle s\delta\Psi\rangle=0$. Since $s\mathcal O=0$,

$$
\mathcal O\,s\delta\Psi=s(\mathcal O\delta\Psi)
$$

up to the standard graded sign, because $\mathcal O$ is assumed even. Therefore

$$
\langle\mathcal O\,s\delta\Psi\rangle
=\langle s(\mathcal O\delta\Psi)\rangle=0.
$$

So

$$
\delta\langle\mathcal O\rangle=0.
$$

The assumptions matter: boundary terms, anomalies, or a bad gauge-fixing region can spoil this formal argument.

</details>

## References

- Becchi, Rouet, and Stora, original papers on BRST symmetry.
- Tyutin, original BRST preprint.
- Faddeev and Popov, “Feynman Diagrams for the Yang–Mills Field,” 1967.
- Srednicki, *Quantum Field Theory*, especially the non-Abelian gauge theory and BRST sections.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chapter 15.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Chapter 31, and “Secret Symmetry” in *Aspects of Symmetry*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, BRST and Zinn-Justin equation chapters.
- Henneaux and Teitelboim, *Quantization of Gauge Systems*, for constrained systems and BRST.
- Barnich, Brandt, and Henneaux, “Local BRST cohomology in gauge theories,” for the advanced cohomological viewpoint.

## Version history

- 2026-06-17: First polished draft. Added nilpotent differential conventions, auxiliary-field form, gauge-fixing fermion, Slavnov–Taylor bridge, anomaly warning, and exercises.
