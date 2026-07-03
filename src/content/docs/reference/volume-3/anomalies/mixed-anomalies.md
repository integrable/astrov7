---
title: "Mixed Anomalies"
description: "Explains anomalies involving more than one symmetry or background structure, including gauge-gravity, gauge-global, global-global, and higher-form examples."
sidebar:
  label: "Mixed Anomalies"
  order: 9
level: Advanced
status: "Polished draft"
source: "Bardeen counterterms; ’t Hooft anomaly matching; anomaly-polynomial and descent formalism; Srednicki §§75–77; Schwartz Ch. 30; Gaiotto–Kapustin–Seiberg–Willett; modern inflow viewpoint."
topics:
  - mixed anomaly
  - mixed gauge anomaly
  - mixed gauge-gravitational anomaly
  - mixed thooft anomaly
  - anomaly matching
  - background fields
  - Bardeen counterterm
  - anomaly polynomial
canonicalTopics:
  - mixed-anomaly
  - mixed-gauge-gravitational-anomaly
  - mixed-thooft-anomaly
  - anomaly-matching
  - bardeen-counterterm
researchStatus:
  established:
    - "Mixed anomalies are invariant obstructions involving two or more symmetry or background structures, even when the anomaly can be moved among Ward identities by counterterms."
    - "If a mixed anomaly involves a gauge redundancy, the gauge-redundancy part must cancel for the theory to be consistent."
  active:
    - "Mixed anomalies involving higher-form, non-invertible, subsystem, reflection, or time-reversal symmetries are central in modern phase and duality constraints."
---

## Summary

A **mixed anomaly** is an anomaly involving more than one symmetry or background structure. Instead of saying “symmetry $G$ is anomalous in isolation,” it says that the combined background dependence of several symmetries cannot be made simultaneously invariant.

Typical examples include:

| Name | Background data | Meaning |
|---|---|---|
| $G^2U(1)$ anomaly | nonabelian $G$ background and $U(1)$ background | the $U(1)$ current has an anomaly in a $G$ background, or gauging both may be obstructed |
| $U(1)^3$ anomaly | three $U(1)$ backgrounds | cubic abelian anomaly |
| mixed gauge-gravitational anomaly | $U(1)$ background and metric/spin connection | $U(1)$ current has a gravitational contribution, or gauging the $U(1)$ conflicts with background geometry |
| mixed ’t Hooft anomaly | two or more global-symmetry backgrounds | the global symmetries cannot all be gauged together |
| mixed higher-form anomaly | ordinary and higher-form backgrounds | extended operators and ordinary symmetry backgrounds are linked |

<figure class="doc-figure" style="--figure-width: 62rem;">

![Flowchart for a mixed anomaly. Candidate symmetries are coupled to background fields A, B, and the metric. A mixed anomaly polynomial contains terms involving more than one type of background. The result is an obstruction to making all background symmetries simultaneously exact, while counterterms can move but not erase the anomaly class.](/figures/symmetry-anomalies-topology/mixed-anomaly-backgrounds.svg)

<figcaption>

A mixed anomaly is detected only after turning on more than one kind of background. Local counterterms may move the anomaly between Ward identities, but the mixed cohomology class remains.

</figcaption>
</figure>

The most important practical rule is:

$$
\text{mixed anomaly involving a gauge redundancy} \quad\Longrightarrow\quad \text{must cancel}.
$$

If all participating symmetries are physical global symmetries, the mixed anomaly is not an inconsistency. It is ’t Hooft anomaly data. It constrains RG flow, phases, boundaries, defects, and dual descriptions.

## Prerequisites

Read [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), and [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/) first.

You should be comfortable with the background-field idea:

$$
Z[A,B,g]
$$

is a generating functional depending on background gauge fields $A$, $B$, and possibly a background metric $g_{\mu\nu}$. A mixed anomaly is a failure of this functional to be invariant under all background transformations at once.

## Core idea

Suppose a theory has two candidate symmetries, $G_A$ and $G_B$. Couple them to background fields $A$ and $B$. Classically, one might expect

$$
Z[A^\alpha,B]=Z[A,B],
\qquad
Z[A,B^\beta]=Z[A,B]
$$

for background transformations $\alpha$ and $\beta$.

A mixed anomaly means that no choice of regulator and local counterterms makes both statements true simultaneously. One may be able to choose a scheme in which $G_A$ looks exact:

$$
\delta_\alpha W[A,B]=0,
$$

but then $G_B$ has an anomaly depending on $A$:

$$
\delta_\beta W[A,B]
=2\pi i\int_{M_d} I_d^{(1)}(\beta;A,B).
$$

A different local counterterm can move the anomaly to the $G_A$ Ward identity. The invariant statement is not which current appears anomalous in a particular convention. The invariant statement is that the combined background-field problem has a nontrivial anomaly class.

This is exactly what happens in the familiar vector/axial anomaly story. One chooses counterterms so that the vector gauge symmetry is exact. Then the axial current carries the anomaly. Another scheme could distribute the anomaly differently, but not remove the obstruction.

## Setup and conventions

Let the theory live in $d=2n$ dimensions. Local anomalies are encoded by a $(d+2)$-form anomaly polynomial,

$$
I_{d+2}(F_A,F_B,R).
$$

It is **mixed** if it contains terms involving more than one background structure. Schematically,

$$
I_{d+2}^{\rm mixed}
\supset
c_{AB}\,\operatorname{tr}F_A^{r}\operatorname{tr}F_B^{s}
+
 c_{A\text{-grav}}\,\operatorname{tr}F_A^r\,p_i(T)+\cdots.
$$

The descent equations are

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta I_{d+1}^{(0)}=dI_d^{(1)},
$$

and the anomalous variation is

$$
\delta W=2\pi i\int_{M_d}I_d^{(1)}.
$$

For chiral spin-$1/2$ fermions,

$$
I_{2n+2}=\left[\widehat A(T)\operatorname{ch}_{\mathcal R}(F)\right]_{2n+2},
$$

with chirality-dependent sign. Mixed gauge-gravitational terms come from multiplying the gauge part of the Chern character by the gravitational part of $\widehat A(T)$.

:::note[Convention-sensitive source note]
A mixed anomaly may be represented in several equivalent ways: as a nonconservation equation for one current, as a non-invariance of the generating functional under one background transformation, as a descent class, or as inflow from a one-higher-dimensional term. Counterterms change the representative. The anomaly class and the set of transformations that cannot all be gauged are invariant.
:::

## Mixed anomaly versus anomaly of a product group

If the symmetry group is a product,

$$
G=G_A\times G_B,
$$

then one may be tempted to ask whether the anomaly is “really” an anomaly of $G$, not a mixed anomaly. Both descriptions are useful.

The full anomaly is indeed an anomaly of the combined background $G$-bundle. It is called mixed when the corresponding polynomial, cocycle, or inflow action does not split into a sum of a term involving only $A$ and a term involving only $B$.

For example,

$$
I_{d+2}=I_{d+2}^{A}(F_A)+I_{d+2}^{B}(F_B)
$$

is not mixed. But

$$
I_{d+2}=c\,F_A\wedge F_B\wedge F_B
$$

is mixed.

The distinction matters physically because a mixed anomaly can imply that each symmetry looks harmless alone, but the pair cannot be simultaneously gauged or simultaneously realized trivially.

## Four-dimensional triangle bookkeeping

In four spacetime dimensions, perturbative fermion anomalies are encoded by a six-form polynomial. For left-handed Weyl fermions, the important schematic terms are

$$
I_6\sim \operatorname{Tr}F^3-\frac{1}{24}\operatorname{Tr}F\,p_1(T),
$$

up to conventional normalizations. Decompose $F$ into factors for the relevant gauge or background groups.

For a simple nonabelian group $G$ and a $U(1)_X$ symmetry, a mixed $G^2U(1)_X$ anomaly is proportional to

$$
\sum_i q_i\,T(R_i),
$$

where $q_i$ is the $U(1)_X$ charge of the left-handed Weyl fermion $i$, and $T(R_i)$ is the quadratic index of its representation under $G$.

A cubic abelian anomaly is proportional to

$$
\sum_i q_i^3.
$$

A mixed $U(1)_X$-gravity-gravity anomaly is proportional to

$$
\sum_i q_i.
$$

These sums are over left-handed Weyl fermions. A right-handed fermion of charge $q$ is equivalently a left-handed conjugate fermion of charge $-q$.

:::note[Left-handed bookkeeping]
Most anomaly mistakes in four dimensions come from mixing left- and right-handed conventions. The clean rule is: convert every fermion to a left-handed Weyl fermion first. Then sum charges and representation indices.
:::

## Mixed gauge-gravitational anomaly in four dimensions

A four-dimensional $U(1)$ gauge symmetry can have a mixed gauge-gravitational anomaly. In Ward-identity form, the $U(1)$ current may have a gravitational contribution,

$$
\nabla_\mu J^\mu_X
\supset
\frac{\sum_i q_i}{384\pi^2}\,
\epsilon^{\mu\nu\rho\sigma}R^\alpha{}_{\beta\mu\nu}R^\beta{}_{\alpha\rho\sigma},
$$

in a common convention. The coefficient is proportional to the sum of $U(1)_X$ charges of all left-handed Weyl fermions.

If $U(1)_X$ is dynamical, consistency requires

$$
\sum_i q_i=0.
$$

This condition is separate from the cubic condition

$$
\sum_i q_i^3=0
$$

and from nonabelian mixed conditions such as

$$
\sum_i q_iT(R_i)=0.
$$

If $U(1)_X$ is a global symmetry, a nonzero mixed gauge-gravitational anomaly is an ’t Hooft anomaly involving the global symmetry and spacetime geometry. It is not an inconsistency, but it forbids gauging $U(1)_X$ without adding new degrees of freedom or inflow.

## Standard Model hypercharge checks

Per generation, use left-handed Weyl fields:

| Field | Multiplicity | Hypercharge |
|---|---:|---:|
| $Q_L$ | $3\times2$ | $1/6$ |
| $u^c_L$ | $3$ | $-2/3$ |
| $d^c_L$ | $3$ | $1/3$ |
| $L_L$ | $2$ | $-1/2$ |
| $e^c_L$ | $1$ | $1$ |

The mixed hypercharge-gravity condition is

$$
\sum_i Y_i=0.
$$

Indeed,

$$
6\left(\frac{1}{6}\right)
+3\left(-\frac{2}{3}\right)
+3\left(\frac{1}{3}\right)
+2\left(-\frac{1}{2}\right)
+1
=0.
$$

The $SU(2)_L^2U(1)_Y$ condition is

$$
3\left(\frac{1}{6}\right)+1\left(-\frac{1}{2}\right)=0,
$$

where the factor $3$ is color multiplicity. The $SU(3)_c^2U(1)_Y$ condition is also zero after converting right-handed quarks to left-handed conjugates:

$$
2\left(\frac{1}{6}\right)+\left(-\frac{2}{3}\right)+\left(\frac{1}{3}\right)=0.
$$

These mixed conditions are part of why hypercharge assignments look so rigid.

The cubic condition $\sum_iY_i^3=0$ also holds per generation. It is not a mixed anomaly, but it belongs to the same anomaly-cancellation package.

## Baryon and lepton number examples

Baryon number $B$ and lepton number $L$ are excellent examples because they distinguish three ideas that students often collapse.

First, the Standard Model gauge redundancies must be anomaly-free. They are.

Second, some classical global currents have anomalous divergences in Standard Model gauge backgrounds. For example, $B+L$ has an electroweak anomaly,

$$
\partial_\mu J^\mu_{B+L}\propto N_g\,\operatorname{tr}W\wedge W,
$$

where $N_g$ is the number of generations. This means the continuous $B+L$ current is not conserved quantum mechanically in nontrivial electroweak backgrounds.

Third, $B-L$ is special. In the minimal Standard Model without right-handed neutrinos, gauging $B-L$ runs into anomaly constraints. With one right-handed neutrino per generation, the usual $B-L$ gauge and mixed gravitational anomalies cancel.

The lesson is that “global symmetry,” “accidental classical symmetry,” “gaugeable symmetry,” and “anomalous current” are different properties.

## Counterterms and moving the anomaly

A mixed anomaly often lets us choose which Ward identity looks anomalous. This is controlled by local counterterms.

Suppose $A$ is a vector background and $A_5$ is an axial background. A triangle diagram may produce anomaly terms involving both. If $A$ is to be a gauge field, we must preserve vector gauge invariance. One adds a Bardeen counterterm so that

$$
\delta_{\rm vector}W=0,
$$

and the anomaly appears in the axial Ward identity.

This does not mean the axial anomaly is an arbitrary convention. It means the representative of the mixed anomaly was chosen so that the gauge redundancy is exact.

More generally:

$$
\text{counterterms move anomaly representatives, not anomaly classes.}
$$

This is the practical reason background fields are so clarifying. They make it visible which symmetries are being preserved by convention and which obstruction remains invariant.

## Mixed ’t Hooft anomalies

If all symmetries involved are global, a mixed anomaly is an ’t Hooft anomaly. It is not a sickness. It is robust data of the QFT.

Suppose a theory has global symmetry

$$
G_A\times G_B.
$$

A mixed ’t Hooft anomaly means:

- the theory can be coupled to $A$ alone;
- it can be coupled to $B$ alone;
- but it cannot be coupled to both $A$ and $B$ while preserving both background gauge invariances.

Equivalently, the partition function is a boundary object for an invertible theory in one higher dimension,

$$
Z_{M_d}[A,B]\quad\text{lives on}\quad \partial X_{d+1}.
$$

Under RG flow, this anomaly cannot disappear. Therefore the infrared must match it by one or more of the following:

- massless degrees of freedom;
- spontaneous symmetry breaking;
- topological order or a TQFT;
- boundary degrees of freedom;
- a dual description with the same anomaly.

This is anomaly matching in its most useful modern form.

## Higher-form and generalized mixed anomalies

Mixed anomalies are not limited to ordinary $0$-form symmetries.

A modern example is a mixed anomaly between an ordinary symmetry and a one-form symmetry. In four-dimensional Yang–Mills theory, the center one-form symmetry acts on Wilson lines. At special theta angles, time reversal can have a mixed anomaly with this center symmetry. The anomaly constrains the possible infrared behavior: a trivially gapped, symmetry-preserving vacuum may be forbidden.

The details depend on global form, line operators, theta periodicity, and background two-form gauge fields. The important conceptual point is simple:

$$
\text{mixed anomaly} = \text{obstruction involving several background structures}.
$$

The background structures may be ordinary gauge fields, higher-form gauge fields, spin or Pin structures, crystalline backgrounds, or non-invertible defect data.

## Diagnosing a mixed anomaly

A useful diagnostic workflow is:

1. **List the candidate symmetries.** Decide which are gauge redundancies and which are physical global symmetries.
2. **Introduce background fields.** Use $A$, $B$, $g_{\mu\nu}$, higher-form backgrounds, or discrete cocycles as needed.
3. **Compute or identify the anomaly class.** Use triangle diagrams, Fujikawa Jacobians, anomaly polynomials, discrete cohomology, eta invariants, or inflow.
4. **Separate removable representatives from invariant classes.** Add local counterterms and see what remains.
5. **Apply the consistency rule.** Gauge-redundancy anomalies must cancel.
6. **Apply matching.** Purely global mixed anomalies must be reproduced in the IR.

This workflow prevents two common errors: declaring a theory inconsistent because a global symmetry is anomalous, and declaring a gauge theory consistent after checking only one anomaly coefficient.

## Common pitfalls

**Thinking mixed means small or secondary.**  Mixed anomalies can be the most important anomaly in the problem. They often control whether a symmetry can be gauged and whether a trivial symmetric gapped phase is possible.

**Forgetting which symmetry is gauged.**  If the anomalous transformation is a gauge redundancy, the theory is inconsistent. If it is a physical global symmetry, the anomaly is matching data.

**Treating a counterterm choice as physics.**  Bardeen counterterms can move an anomaly among currents. The invariant object is the anomaly class.

**Using right-handed charges without conjugation.**  In four-dimensional anomaly sums, convert all fermions to left-handed Weyl fields first.

**Ignoring gravity in anomaly cancellation.**  For a gauged $U(1)$, the mixed gauge-gravitational condition $\sum_i q_i=0$ is independent of the cubic condition $\sum_i q_i^3=0$.

**Assuming each symmetry is gaugeable because each looks fine alone.**  A mixed anomaly can vanish when either background is set to zero and appear only when both are turned on.

## Relations to other pages

- [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/) explains the gravitational part of mixed gauge-gravity anomalies.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) gives the unified characteristic-class calculation.
- [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/) explains representative dependence.
- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) explains the algebraic consistency of anomaly variations.
- [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) treats global anomalies as RG-invariant obstruction data.
- [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) explains how mixed anomalies extend to charged line and surface operators.

## Research status

Perturbative mixed gauge and mixed gauge-gravitational anomalies in ordinary four-dimensional fermion theories are textbook material. The anomaly-polynomial formalism is the standard unifying language for local continuous anomalies.

The frontier is broader. Modern QFT uses mixed anomalies involving higher-form symmetries, discrete symmetries, time reversal, reflection, subsystem symmetries, and non-invertible defects to constrain phases and dualities. The computational language may involve cohomology, bordism, symmetry TFT, or categorical data rather than triangle diagrams.

## Exercises

### Exercise 1: Hypercharge-gravity anomaly cancellation

Using the table in this page, verify that the mixed $U(1)_Y$-gravity-gravity anomaly cancels for one Standard Model generation.

<details><summary><strong>Solution</strong></summary>

Sum hypercharges over left-handed Weyl fermions, including multiplicities:

$$
6\left(\frac{1}{6}\right)
+3\left(-\frac{2}{3}\right)
+3\left(\frac{1}{3}\right)
+2\left(-\frac{1}{2}\right)
+1
=1-2+1-1+1=0.
$$

Therefore the mixed hypercharge-gravity anomaly cancels per generation.

</details>

### Exercise 2: SU(2) squared U(1) condition

Check the $SU(2)_L^2U(1)_Y$ anomaly cancellation condition for one Standard Model generation.

<details><summary><strong>Solution</strong></summary>

Only $SU(2)_L$ doublets contribute: $Q_L$ and $L_L$. The quadratic index of the doublet is common, so it is enough to sum hypercharges weighted by multiplicity from color:

$$
3\left(\frac{1}{6}\right)+1\left(-\frac{1}{2}\right)=\frac{1}{2}-\frac{1}{2}=0.
$$

Thus the $SU(2)_L^2U(1)_Y$ mixed anomaly cancels.

</details>

### Exercise 3: Why a mixed anomaly may be invisible in restricted backgrounds

Suppose an anomaly polynomial contains $I_6=cF_A\wedge F_B\wedge F_B$. What happens if $B=0$? Does this mean the anomaly is absent?

<details><summary><strong>Solution</strong></summary>

If $B=0$, then

$$
F_B=0,
$$

and the displayed term vanishes. The anomaly is invisible on that restricted background.

But the anomaly class is not absent. It appears when both $A$ and $B$ backgrounds are allowed. Therefore it obstructs simultaneous gauging or simultaneous background invariance of the two symmetries.

</details>

### Exercise 4: Bardeen-counterterm logic

Why is it physically sensible to choose a counterterm that preserves vector gauge invariance while leaving the axial current anomalous?

<details><summary><strong>Solution</strong></summary>

If the vector field is a gauge field, vector gauge invariance is a redundancy required for consistency. It must be exact. The axial symmetry, by contrast, may be a physical global symmetry. An anomaly in a global symmetry is not an inconsistency; it is a quantum statement about the theory.

Therefore one chooses a Bardeen counterterm so that

$$
\delta_{\rm vector}W=0,
$$

and the anomaly appears in the axial Ward identity. The counterterm changes the representative of the mixed anomaly, not the underlying anomaly class.

</details>

### Exercise 5: Gauging one factor

A theory has global symmetry $G_A\times G_B$ with a mixed ’t Hooft anomaly. What must be checked before gauging $G_A$?

<details><summary><strong>Solution</strong></summary>

After gauging $G_A$, transformations of $G_A$ become gauge redundancies. Any anomaly involving $G_A$ as a gauge transformation must vanish or be canceled by additional degrees of freedom or inflow. If the mixed anomaly implies that $G_A$ gauge transformations fail in $G_B$ backgrounds, then gauging $G_A$ may force a modification of the $G_B$ symmetry, attach topological degrees of freedom, or make $G_B$ non-onsite/nontrivial.

The practical rule is: a global mixed anomaly is allowed, but once one factor is promoted to a gauge redundancy, the gauge variation must be made exactly zero.

</details>

## References

- W. A. Bardeen, “Anomalous Ward Identities in Spinor Field Theories,” *Physical Review* **184** (1969).
- G. ’t Hooft, “Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking,” in *Recent Developments in Gauge Theories* (1980).
- M. Srednicki, *Quantum Field Theory*, sections on chiral gauge theories, global anomalies, and fermion path integrals.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30.
- S. Weinberg, *The Quantum Theory of Fields*, Volume II, chapters on gauge theories and anomalies.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”
- D. S. Freed, “Anomalies and Invertible Field Theories.”

## Version history

- 2026-06-18: First polished draft. Added mixed-anomaly taxonomy, four-dimensional anomaly sums, Standard Model checks, Bardeen-counterterm discussion, higher-form preview, and exercises.
