---
title: "Perturbative Gauge Anomalies"
description: "Explains local gauge anomalies in chiral gauge theories, their triangle-diagram origin, cancellation conditions, and Standard Model anomaly checks."
sidebar:
  label: "Perturbative Gauge Anomalies"
  order: 6
level: Graduate
status: "Polished draft"
source: "Adler–Bell–Jackiw; Bardeen; Wess–Zumino; Srednicki §75 and §77; Schwartz §30.4; Weinberg Vol. II gauge-anomaly and BRST chapters."
topics:
  - gauge anomaly
  - chiral gauge theory
  - triangle anomaly
  - anomaly cancellation
  - Standard Model
  - BRST consistency
canonicalTopics:
  - perturbative-gauge-anomaly
  - gauge-anomaly-cancellation
  - chiral-gauge-theory
  - standard-model-anomaly-cancellation
researchStatus:
  established:
    - "Perturbative gauge anomalies are local obstructions to preserving gauge invariance in chiral quantum field theories; they are detected by one-loop triangle diagrams and equivalently by descent from anomaly polynomials."
    - "A dynamical gauge symmetry must be free of both perturbative and global gauge anomalies for the quantum theory to be consistent."
  active:
    - "Modern treatments package perturbative gauge anomalies with mixed, global, fermionic, and higher-form anomalies using BRST cohomology, anomaly inflow, cobordism, and symmetry TFT language."
---

## Summary

A **perturbative gauge anomaly** is a local, infinitesimal failure of gauge invariance in a quantum theory. It is called perturbative because it is visible near the identity component of the gauge group and, in four-dimensional chiral gauge theories, already appears in one-loop triangle diagrams.

For a global current, an anomalous divergence may be a physical feature. For a **dynamical gauge current**, it is usually fatal: gauge invariance is the mechanism that removes unphysical polarizations and enforces the constraints of the theory. If the gauge Ward identity fails, the longitudinal modes do not decouple and the gauge-fixed theory loses its basic consistency.

The first practical rule is therefore blunt:

$$
\text{dynamical gauge symmetry} \quad \Longrightarrow \quad \text{all gauge anomalies cancel}.
$$

For left-handed Weyl fermions in representations $R_i$ of a simple nonabelian gauge group, the perturbative cubic gauge-anomaly cancellation condition is

$$
\sum_i \operatorname{tr}_{R_i}\!\left(T^a\{T^b,T^c\}\right)=0
\qquad\text{for all }a,b,c.
$$

For a $U(1)$ gauge symmetry with left-handed Weyl fermion charges $q_i$, the cubic condition is

$$
\sum_i q_i^3=0.
$$

If the $U(1)$ is also coupled to gravity as a gauge symmetry, there is a mixed gauge-gravitational condition

$$
\sum_i q_i=0.
$$

<figure class="doc-figure" style="--figure-width: 55rem;">

![A perturbative gauge anomaly map. Chiral Weyl fermions in a triangle diagram produce a possible anomalous gauge variation. The local Ward identity is repaired only if the symmetric cubic group factor sums to zero across all left-handed Weyl fermions. Otherwise gauge invariance, BRST symmetry, and unitarity fail.](/figures/symmetry-anomalies-topology/perturbative-gauge-anomaly-cancellation.svg)

<figcaption>

Perturbative gauge anomalies are local obstructions. The triangle diagram produces a symmetric cubic group factor $\operatorname{tr}_R(T^a\{T^b,T^c\})$; a consistent gauge theory requires the sum of this factor over all left-handed Weyl fermions to vanish.

</figcaption>
</figure>

These equations are simple to state but profound. They are why chiral gauge theories are rare gems rather than generic toys.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/), [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/), and [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/) first.

You should also know the distinction between background and dynamical gauge fields from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), and the BRST viewpoint from [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/) and [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/).

## Core idea

The chiral anomaly page studied a safe situation: a vector gauge symmetry was preserved, while a global axial symmetry became anomalous. A perturbative gauge anomaly is the dangerous cousin. It occurs when the anomalous current is the current coupled to a dynamical gauge field.

A chiral gauge theory couples left- and right-handed fermions differently. The simplest language is to write every fermion as a **left-handed Weyl fermion**. A right-handed Weyl fermion in representation $R$ is equivalently a left-handed Weyl fermion in the conjugate representation $R^*$.

For a single left-handed Weyl fermion coupled to a gauge field, the triangle diagram with three gauge-current insertions asks for too much: it asks the regulator to preserve all three gauge Ward identities simultaneously. In general it cannot. Shifting the loop momentum can move the anomaly from one external leg to another, but cannot remove it.

The miracle is that different Weyl fermions can cancel one another. The anomaly is additive over fermions. A chiral gauge theory is perturbatively consistent only when the sum of the relevant anomaly coefficients vanishes.

## Setup and conventions

The volume convention for a background or dynamical gauge field is

$$
D_\mu=\partial_\mu-iA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
$$

where the coupling may be absorbed into $A_\mu$ when this makes anomaly formulae cleaner. The generators $T^a$ are Hermitian.

A left-handed Weyl fermion in representation $R$ has kinetic term

$$
\mathcal L_\psi=i\psi^\dagger\bar\sigma^\mu D_\mu\psi.
$$

Equivalently, one may use a four-component Dirac spinor with the left projector

$$
P_L=\frac{1-\gamma^5}{2}.
$$

The perturbative anomaly is usually written in terms of the effective action $W[A]$ obtained after integrating out fermions:

$$
e^{iW[A]}=\int D\psi^\dagger D\psi\,e^{iS[\psi^\dagger,\psi;A]}.
$$

An infinitesimal gauge transformation with parameter $\alpha=\alpha^aT^a$ acts as

$$
\delta_\alpha A_\mu=D_\mu\alpha.
$$

A gauge anomaly is the statement that

$$
\delta_\alpha W[A]\neq 0.
$$

Equivalently, the gauge-current Ward identity has a local anomalous right-hand side.

:::note[Convention-sensitive source note]
There are many normalizations of the nonabelian consistent anomaly. A common differential-form convention absorbs the gauge coupling into $A$ and writes the local anomaly schematically as

$$
\delta_\alpha W[A]\sim \frac{1}{24\pi^2}\int \operatorname{tr}_R\!\left[\alpha\,d\left(A\,dA-\frac{i}{2}A^3\right)\right].
$$

Do not compare this coefficient blindly across books. Authors differ in whether $A$ contains the coupling, whether generators are Hermitian or anti-Hermitian, whether all fermions are left-handed, and whether they use the consistent or covariant current. The robust cancellation condition is the vanishing of the group-theory anomaly coefficient.
:::

## Why gauge anomalies are fatal

Gauge symmetry is not an ordinary physical degeneracy. It is the redundancy that removes unphysical variables.

In covariant quantization, gauge invariance becomes a tower of Ward or Slavnov–Taylor identities. These identities ensure, among other things, that unphysical longitudinal polarizations and negative-norm states do not appear in physical amplitudes. If a gauge anomaly breaks the identities, the theory is no longer a consistent quantum gauge theory.

In BRST language, the gauge-fixed action should have a nilpotent BRST symmetry. A perturbative gauge anomaly is a ghost-number-one obstruction to this symmetry:

$$
s\Gamma\neq 0,
$$

where $s$ is the BRST differential and $\Gamma$ is the quantum effective action. Consistency requires

$$
s(s\Gamma)=0,
$$

which is the BRST form of the Wess–Zumino consistency condition. A trivial anomaly can be removed by adding a local counterterm. A nontrivial gauge-anomaly class cannot.

The slogan is

$$
\text{global anomaly of a global symmetry: data},
\qquad
\text{gauge anomaly of a gauge symmetry: inconsistency}.
$$

The second statement has one qualification: a theory can sometimes be made consistent by adding new boundary degrees of freedom, a higher-dimensional inflow bulk, or additional fermions. But the isolated lower-dimensional gauge theory must still have its total gauge variation canceled.

## The triangle-diagram origin

Consider the three-current correlator

$$
\langle J^{\mu a}(x)J^{\nu b}(y)J^{\rho c}(z)\rangle.
$$

At one loop, a chiral fermion can run around the triangle. The loop integral is superficially linearly divergent. Shifting the loop momentum changes a surface term. That surface term is exactly where the anomaly lives.

For a vectorlike Dirac fermion, the left- and right-handed contributions cancel. For a single Weyl fermion, they do not. The group theory multiplying the anomalous part is the symmetric trace

$$
D_R^{abc}\equiv \operatorname{tr}_R\!\left(T^a\{T^b,T^c\}\right).
$$

The perturbative nonabelian gauge anomaly of a collection of left-handed Weyl fermions is proportional to

$$
\mathcal D^{abc}=\sum_i D_{R_i}^{abc}.
$$

A necessary and, for local perturbative gauge anomalies in ordinary four-dimensional chiral gauge theories, sufficient cancellation condition is

$$
\mathcal D^{abc}=0.
$$

When the group is simple and has a unique symmetric invariant $d^{abc}$, one often writes

$$
D_R^{abc}=A(R)d^{abc},
$$

where $A(R)$ is the anomaly coefficient of $R$. Then the condition is

$$
\sum_i A(R_i)=0.
$$

For conjugate representations,

$$
A(R^*)=-A(R).
$$

This is why vectorlike theories are safe: a Dirac fermion is a left-handed fermion in $R$ plus a left-handed fermion in $R^*$.

## Abelian anomaly conditions

For a $U(1)$ gauge symmetry, each left-handed Weyl fermion has charge $q_i$. The cubic perturbative gauge anomaly is proportional to

$$
\sum_i q_i^3.
$$

Thus the pure $U(1)^3$ anomaly cancels if

$$
\sum_i q_i^3=0.
$$

If the theory is placed on curved spacetime and the $U(1)$ is dynamical, there is also a mixed gauge-gravitational anomaly proportional to

$$
\sum_i q_i.
$$

The cancellation condition is therefore

$$
\sum_i q_i=0.
$$

For a product of nonabelian factors and $U(1)$ factors, there are mixed conditions. For example, if left-handed Weyl fermions transform in representations $R_i$ of a simple group $G$ and have $U(1)$ charges $q_i$, then the $G^2U(1)$ anomaly is proportional to

$$
\sum_i q_i T_2(R_i),
$$

where

$$
\operatorname{tr}_{R_i}(T^aT^b)=T_2(R_i)\delta^{ab}.
$$

When the fermion also carries spectator quantum numbers under other groups, their multiplicities must be included. This is the most common source of arithmetic mistakes in Standard Model anomaly checks.

## Nonabelian examples

For $SU(N)$ with $N\geq 3$, complex representations can have nonzero cubic anomaly coefficient. In the convention $A(\mathbf N)=1$,

$$
A(\overline{\mathbf N})=-1.
$$

For $SU(2)$, the perturbative cubic anomaly vanishes because there is no nonzero symmetric invariant $d^{abc}$ in the adjoint-index triple. Equivalently, the fundamental representation is pseudoreal. This does **not** mean that every $SU(2)$ chiral gauge theory is consistent: $SU(2)$ has a global anomaly for an odd number of Weyl doublets, discussed on the next page.

For $SO(N)$ in the familiar vectorlike settings, perturbative cubic anomalies are absent or strongly constrained by the reality properties of the relevant representations. But representation theory must still be checked carefully, especially for spinor representations in special dimensions.

The safe habit is:

$$
\text{do not infer anomaly cancellation from the group name alone;}\quad
\text{compute the anomaly coefficients of the actual fermion representations.}
$$

## Standard Model anomaly cancellation

Work with one generation of Standard Model fermions, all written as left-handed Weyl fermions:

| Field | Representation under $SU(3)_c\times SU(2)_L$ | Hypercharge $Y$ |
|---|---:|---:|
| $Q$ | $(\mathbf 3,\mathbf 2)$ | $1/6$ |
| $u^c$ | $(\overline{\mathbf 3},\mathbf 1)$ | $-2/3$ |
| $d^c$ | $(\overline{\mathbf 3},\mathbf 1)$ | $1/3$ |
| $L$ | $(\mathbf 1,\mathbf 2)$ | $-1/2$ |
| $e^c$ | $(\mathbf 1,\mathbf 1)$ | $1$ |

The convention is

$$
Q_{\rm electric}=T_3+Y.
$$

The pure $SU(3)_c^3$ anomaly cancels because the color theory is vectorlike after accounting for the two weak components of $Q$:

$$
2A(\mathbf 3)+A(\overline{\mathbf 3})+A(\overline{\mathbf 3})=2-1-1=0.
$$

The pure $SU(2)_L^3$ perturbative anomaly vanishes because $SU(2)$ has no cubic perturbative anomaly. The global $SU(2)$ anomaly requires an even number of doublets; one generation has three colored quark doublets plus one lepton doublet, hence four.

The $SU(3)_c^2U(1)_Y$ anomaly is

$$
2\left(\frac16\right)T_2(\mathbf 3)
+\left(-\frac23\right)T_2(\overline{\mathbf 3})
+\left(\frac13\right)T_2(\overline{\mathbf 3})=0,
$$

using $T_2(\mathbf 3)=T_2(\overline{\mathbf 3})=1/2$.

The $SU(2)_L^2U(1)_Y$ anomaly is

$$
3\left(\frac16\right)T_2(\mathbf 2)
+\left(-\frac12\right)T_2(\mathbf 2)=0,
$$

where the factor $3$ counts colors.

The cubic hypercharge anomaly is

$$
6\left(\frac16\right)^3
+3\left(-\frac23\right)^3
+3\left(\frac13\right)^3
+2\left(-\frac12\right)^3
+1^3=0.
$$

The mixed gravitational-hypercharge anomaly is

$$
6\left(\frac16\right)
+3\left(-\frac23\right)
+3\left(\frac13\right)
+2\left(-\frac12\right)
+1=0.
$$

This cancellation is not an aesthetic accident. It ties quark and lepton quantum numbers together.

:::note[Right-handed fields and signs]
The fields $u^c$, $d^c$, and $e^c$ above are left-handed charge-conjugate fields. If instead you list right-handed fields $u_R$, $d_R$, and $e_R$, the anomaly formula has opposite signs for right-handed fermions. Both conventions give the same answer, but mixing them mid-calculation is sign-chaos in a lab coat.
:::

## Counterterms and moving the anomaly

Triangle anomalies are not always tied to a unique current. In a theory with several currents, a local counterterm can move the anomalous divergence from one current to another.

This is already visible in the axial-vector-vector triangle. One can choose a regulator that preserves the two vector Ward identities and leaves the axial current anomalous. That is the choice required if the vector symmetry is gauged.

For gauge symmetries, moving the anomaly is not enough. Every dynamical gauge Ward identity must be preserved simultaneously. If no local counterterm can make all gauge variations vanish, the gauge anomaly is real.

Later pages distinguish two related objects:

- the **consistent anomaly**, obtained as the variation of one effective action and satisfying Wess–Zumino consistency;
- the **covariant anomaly**, which transforms covariantly under gauge transformations but is not itself the variation of the same effective action without an added Bardeen–Zumino current.

The cancellation condition is independent of this bookkeeping.

## Anomaly cancellation as a design principle

When building a chiral gauge theory, anomaly cancellation is not a final decorative check. It is part of the definition of the model.

A practical workflow is:

1. Write every fermion as a left-handed Weyl fermion.
2. List all gauge representations and all abelian charges.
3. Include multiplicities from spectator gauge factors.
4. Check pure nonabelian cubic anomalies.
5. Check $G^2U(1)$ anomalies.
6. Check $U(1)^3$ anomalies.
7. Check mixed gravitational-$U(1)$ anomalies.
8. Check global gauge anomalies, especially $SU(2)$-type mod-two anomalies.

The last step is not perturbative. That is why it lives on the next page.

## Common pitfalls

**Forgetting multiplicities.** A quark doublet $Q$ has two weak components and three color components. Which multiplicity matters depends on which anomaly is being checked.

**Using right-handed charges in a left-handed formula.** Convert all fermions to left-handed Weyl fields or use a left-minus-right formula consistently.

**Thinking vectorlike means uninteresting.** Vectorlike means perturbative gauge anomalies cancel automatically. It does not mean the theory has no global symmetries, no theta angle, no confinement, or no anomalies in global currents.

**Confusing perturbative and global anomalies.** $SU(2)$ has no perturbative cubic gauge anomaly in four dimensions, but it can have a global mod-two anomaly.

**Trusting classical gauge invariance.** The classical Lagrangian may be gauge invariant. The quantum fermion measure may not be.

## Relations to other pages

- [Triangle Anomaly](/symmetry-anomalies-topology/anomalies/triangle-anomaly/) explains the momentum-routing origin of the anomaly.
- [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/) derives anomalies from the regulated fermion measure.
- [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/) explains anomaly obstructions invisible to infinitesimal perturbation theory.
- [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/) separates two standard current conventions.
- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) develops the cohomological consistency condition.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) give the systematic classification method.

## Research status

Perturbative gauge anomalies in ordinary four-dimensional chiral gauge theories are a settled subject. The one-loop coefficient, anomaly-cancellation conditions, descent formalism, and BRST cohomology interpretation are standard.

The active frontier is not whether these anomalies exist, but how they sit inside broader anomaly classification: global anomalies, torsion anomalies, fermionic anomalies, higher-form anomalies, boundaries, relative theories, and symmetry TFTs. The perturbative anomaly is the local free part of a larger story.

## Exercises

### Exercise 1: Vectorlike cancellation

A Dirac fermion in representation $R$ of a nonabelian gauge group can be written as two left-handed Weyl fermions in $R$ and $R^*$. Show that its perturbative cubic gauge anomaly cancels.

<details><summary><strong>Solution</strong></summary>

The anomaly coefficient is additive over left-handed Weyl fermions. The Dirac fermion contributes

$$
D_R^{abc}+D_{R^*}^{abc}.
$$

For conjugate representations,

$$
D_{R^*}^{abc}=-D_R^{abc}.
$$

Thus

$$
D_R^{abc}+D_{R^*}^{abc}=0.
$$

This is the group-theory expression of the familiar statement that vectorlike fermions have canceling left- and right-handed gauge anomalies.

</details>

### Exercise 2: A chiral abelian model

Consider a $U(1)$ gauge theory with one left-handed Weyl fermion of charge $+2$ and eight left-handed Weyl fermions of charge $-1$.

1. Does the pure $U(1)^3$ gauge anomaly cancel?
2. Does the mixed gravitational-$U(1)$ anomaly cancel?

<details><summary><strong>Solution</strong></summary>

The pure cubic anomaly is proportional to

$$
2^3+8(-1)^3=8-8=0.
$$

So the pure $U(1)^3$ anomaly cancels.

The mixed gravitational-$U(1)$ anomaly is proportional to the sum of charges:

$$
2+8(-1)=-6.
$$

It does not cancel. If the theory is coupled to dynamical gravity, or if one wants the corresponding background-gravity Ward identity to be gauge invariant, additional charged fermions or another cancellation mechanism is needed.

</details>

### Exercise 3: The SU(2)-squared U(1) Standard Model check

Using one generation of left-handed fields,

$$
Q:(\mathbf 3,\mathbf 2)_{1/6},
\qquad
L:(\mathbf 1,\mathbf 2)_{-1/2},
$$

show that the $SU(2)_L^2U(1)_Y$ anomaly cancels.

<details><summary><strong>Solution</strong></summary>

Only $SU(2)$ doublets contribute. The $Q$ doublet comes in three colors, so it contributes

$$
3\left(\frac16\right)T_2(\mathbf 2).
$$

The lepton doublet contributes

$$
\left(-\frac12\right)T_2(\mathbf 2).
$$

The total is

$$
\left(\frac{3}{6}-\frac12\right)T_2(\mathbf 2)=0.
$$

Thus the anomaly cancels.

</details>

### Exercise 4: Why SU(2) cubed is not the end of the story

Explain why the absence of a perturbative $SU(2)^3$ anomaly does not prove that every four-dimensional $SU(2)$ chiral gauge theory is consistent.

<details><summary><strong>Solution</strong></summary>

The perturbative $SU(2)^3$ anomaly vanishes because there is no nonzero symmetric cubic invariant $d^{abc}$ for $SU(2)$. This only rules out local anomalies visible under infinitesimal gauge transformations.

Four-dimensional $SU(2)$ gauge theory can still have a global anomaly because

$$
\pi_4(SU(2))=\mathbb Z_2.
$$

A theory with an odd number of left-handed Weyl doublets changes sign under the nontrivial large gauge transformation. This anomaly is invisible in the triangle-diagram cubic coefficient, so it must be checked separately.

</details>

## References

- S. L. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* **177** (1969).
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the $\sigma$-Model,” *Il Nuovo Cimento A* **60** (1969).
- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969).
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* **37** (1971).
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* **234** (1984).
- M. Srednicki, *Quantum Field Theory*, §§75 and 77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.4.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, gauge-anomaly and BRST chapters.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*, Oxford University Press.

## Version history

- 2026-06-18: First polished draft. Added local gauge-anomaly definition, triangle origin, nonabelian and abelian cancellation conditions, Standard Model checks, BRST consistency perspective, and exercises.
