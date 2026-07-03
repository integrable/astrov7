---
title: "Anomaly Cancellation in the Standard Model"
description: "A complete one-generation calculation showing cancellation of perturbative gauge and mixed gravitational anomalies in the Standard Model."
sidebar:
  label: "Anomaly Cancellation in the Standard Model"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77, 87–89; Schwartz §30.4; Weinberg Vol. II Chs. 21–22; Burgess §9.1."
topics:
  - Standard Model
  - gauge anomalies
  - anomaly cancellation
  - hypercharge
  - chiral fermions
canonicalTopics:
  - standard-model-anomaly-cancellation
  - gauge-anomaly
  - hypercharge
  - chiral-gauge-theory
researchStatus:
  established:
    - "Perturbative gauge-anomaly cancellation in each Standard Model generation is a standard consistency check of the chiral gauge theory."
  active:
    - "Extensions of the Standard Model must repeat the same test, including possible global anomalies and global-form refinements of the gauge group."
---

## Summary

The Standard Model is a chiral gauge theory. Its left- and right-handed fermions transform differently under

$$
SU(3)_c\times SU(2)_L\times U(1)_Y.
$$

That makes anomaly cancellation a consistency condition, not a decorative check. A gauge anomaly is an anomaly in a redundancy. If it does not cancel, the gauge theory does not have a consistent physical Hilbert space.

For one generation of Standard Model fermions, written entirely as left-handed Weyl fields,

| Field | Representation under $SU(3)_c\times SU(2)_L$ | Hypercharge |
|---|---:|---:|
| $Q$ | $(\mathbf 3,\mathbf 2)$ | $1/6$ |
| $u^c$ | $(\overline{\mathbf 3},\mathbf 1)$ | $-2/3$ |
| $d^c$ | $(\overline{\mathbf 3},\mathbf 1)$ | $1/3$ |
| $L$ | $(\mathbf 1,\mathbf 2)$ | $-1/2$ |
| $e^c$ | $(\mathbf 1,\mathbf 1)$ | $1$ |

all perturbative gauge and mixed gravitational anomalies cancel:

$$
SU(3)^3,\quad SU(2)^3,\quad SU(3)^2U(1)_Y,\quad SU(2)^2U(1)_Y,\quad
\operatorname{grav}^2U(1)_Y,\quad U(1)_Y^3.
$$

There is also no Witten $SU(2)$ global anomaly, because each generation has four left-handed $SU(2)$ doublets:

$$
3\text{ colored }Q\text{ doublets}+1\text{ lepton }L\text{ doublet}=4.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![A compact flow diagram showing the one-generation Standard Model fermion multiplets feeding into the anomaly sums, all of which vanish.](/figures/symmetry-anomalies-topology/standard-model-anomaly-cancellation.svg)

<figcaption>

One generation of Standard Model left-handed Weyl fermions. The apparently strange hypercharges are precisely what make the mixed and cubic anomaly sums vanish.

</figcaption>
</figure>

## Prerequisites

You should know the previous anomaly pages on the ABJ triangle and Fujikawa Jacobian. You should also know the convention that, when checking anomalies in a chiral gauge theory, it is safest to rewrite every fermion as a **left-handed Weyl fermion**.

The Standard Model electric charge convention used here is

$$
Q_{\rm em}=T_3+Y.
$$

We use

$$
T(\mathbf N)=\frac12
$$

for the Dynkin index of the fundamental representation of $SU(N)$, and we normalize the cubic $SU(N)$ anomaly so that

$$
A(\mathbf N)=+1,\qquad A(\overline{\mathbf N})=-1.
$$

:::note[Convention-sensitive point]
A right-handed fermion in representation $R$ and hypercharge $Y$ is equivalently a left-handed charge-conjugate fermion in representation $\overline R$ and hypercharge $-Y$. Forgetting this conjugation is the most common way to get the wrong anomaly sums.
:::

## Core idea

A perturbative gauge anomaly is proportional to a triangle diagram with three gauge-current insertions. For a collection of left-handed Weyl fermions, the coefficient is a trace over the gauge generators carried by those fermions.

For a simple non-Abelian group $G$, the cubic anomaly coefficient is proportional to

$$
\sum_{\psi_L}\operatorname{tr}_{R_\psi}
\left(T^a\{T^b,T^c\}\right).
$$

For mixed anomalies involving two non-Abelian currents and one hypercharge current, the relevant coefficient is

$$
\sum_{\psi_L} Y_\psi\, T_G(R_\psi)\,\prod_{\text{spectator groups}} d(R_{\rm spectator}).
$$

For the mixed gravitational anomaly with one $U(1)_Y$ current,

$$
\sum_{\psi_L}Y_\psi\, d(R_3)d(R_2)
$$

must vanish. For the cubic hypercharge anomaly,

$$
\sum_{\psi_L}Y_\psi^3\, d(R_3)d(R_2)
$$

must vanish.

The Standard Model passes all these tests generation by generation.

## One generation as left-handed Weyl fermions

The Standard Model is often introduced with right-handed electron, up-quark, and down-quark fields. For anomaly calculations, rewrite them as left-handed charge-conjugate fields:

$$
u_R\quad\leadsto\quad u^c_L,
\qquad
d_R\quad\leadsto\quad d^c_L,
\qquad
e_R\quad\leadsto\quad e^c_L.
$$

Their hypercharges flip sign. Their non-Abelian representations are conjugated. This gives the table:

$$
Q=(\mathbf 3,\mathbf 2)_{1/6},
\qquad
u^c=(\overline{\mathbf 3},\mathbf 1)_{-2/3},
\qquad
d^c=(\overline{\mathbf 3},\mathbf 1)_{1/3},
$$

$$
L=(\mathbf 1,\mathbf 2)_{-1/2},
\qquad
e^c=(\mathbf 1,\mathbf 1)_{1}.
$$

A sterile right-handed neutrino, if added, appears as

$$
\nu^c=(\mathbf 1,\mathbf 1)_0,
$$

and contributes nothing to the gauge or mixed gravitational anomaly sums.

## The non-Abelian cubic anomalies

### The SU(3) cubic anomaly

For $SU(3)_c^3$, count the number of color fundamentals and antifundamentals, weighted by spectator $SU(2)$ multiplicity.

The quark doublet $Q$ contains two left-handed color triplets:

$$
Q:\quad 2\,A(\mathbf 3)=2.
$$

The fields $u^c$ and $d^c$ are color antifundamentals:

$$
u^c:\quad A(\overline{\mathbf 3})=-1,
\qquad
d^c:\quad A(\overline{\mathbf 3})=-1.
$$

Therefore

$$
2-1-1=0.
$$

So the $SU(3)_c^3$ anomaly cancels.

### The SU(2) cubic anomaly

There is no perturbative $SU(2)_L^3$ anomaly because $SU(2)$ has no independent symmetric invariant $d^{abc}$ in the fundamental; equivalently, its doublet is pseudoreal.

But $SU(2)$ has a **global** anomaly discovered by Witten. A four-dimensional $SU(2)$ gauge theory is inconsistent if it has an odd number of left-handed doublets.

Per Standard Model generation, the number of $SU(2)_L$ doublets is

$$
3\times Q + 1\times L = 4.
$$

This is even, so the Witten anomaly is absent.

:::note[Source note]
The perturbative triangle test and the Witten global-anomaly test are logically different. The first is visible in infinitesimal gauge variation of the effective action. The second is a large-gauge-transformation obstruction.
:::

## The SU(3)²U(1) anomaly

The coefficient of $SU(3)_c^2U(1)_Y$ is

$$
\sum_{\psi_L} d(R_2)\,T_3(R_3)\,Y_\psi.
$$

Only colored fermions contribute. Using $T(\mathbf 3)=T(\overline{\mathbf 3})=1/2$,

$$
Q:\quad 2\cdot \frac12\cdot \frac16=\frac16,
$$

$$
u^c:\quad 1\cdot \frac12\cdot\left(-\frac23\right)=-\frac13,
$$

$$
d^c:\quad 1\cdot \frac12\cdot \frac13=\frac16.
$$

The sum is

$$
\frac16-\frac13+\frac16=0.
$$

Thus

$$
SU(3)_c^2U(1)_Y
$$

is anomaly-free.

## The SU(2)²U(1) anomaly

The coefficient of $SU(2)_L^2U(1)_Y$ is

$$
\sum_{\psi_L} d(R_3)\,T_2(R_2)\,Y_\psi.
$$

Only $SU(2)$ doublets contribute. Using $T(\mathbf 2)=1/2$,

$$
Q:\quad 3\cdot \frac12\cdot \frac16=\frac14,
$$

where the factor $3$ is color multiplicity, and

$$
L:\quad 1\cdot \frac12\cdot\left(-\frac12\right)=-\frac14.
$$

Therefore

$$
\frac14-\frac14=0.
$$

Thus

$$
SU(2)_L^2U(1)_Y
$$

is anomaly-free.

## The gravitational²U(1) anomaly

The mixed gravitational anomaly with one $U(1)_Y$ current is proportional to the sum of hypercharges over all left-handed Weyl fermion components:

$$
\sum_{\psi_L} d(R_3)d(R_2)Y_\psi.
$$

For one generation,

$$
Q:\quad 3\cdot2\cdot\frac16=1,
$$

$$
u^c:\quad 3\cdot1\cdot\left(-\frac23\right)=-2,
$$

$$
d^c:\quad 3\cdot1\cdot\frac13=1,
$$

$$
L:\quad 1\cdot2\cdot\left(-\frac12\right)=-1,
$$

$$
e^c:\quad 1\cdot1\cdot1=1.
$$

The sum is

$$
1-2+1-1+1=0.
$$

Thus the mixed gravitational-$U(1)_Y$ anomaly cancels.

## The U(1)³ anomaly

The cubic hypercharge anomaly is proportional to

$$
\sum_{\psi_L} d(R_3)d(R_2)Y_\psi^3.
$$

For one generation,

$$
Q:\quad 6\left(\frac16\right)^3=\frac{1}{36},
$$

$$
u^c:\quad 3\left(-\frac23\right)^3=-\frac{8}{9},
$$

$$
d^c:\quad 3\left(\frac13\right)^3=\frac{1}{9},
$$

$$
L:\quad 2\left(-\frac12\right)^3=-\frac14,
$$

$$
e^c:\quad 1^3=1.
$$

Putting them over a common denominator,

$$
\frac{1}{36}-\frac{32}{36}+\frac{4}{36}-\frac{9}{36}+\frac{36}{36}=0.
$$

Thus

$$
U(1)_Y^3
$$

is anomaly-free.

## What about U(1)²SU(N)?

A triangle with two hypercharge currents and one simple non-Abelian current contains a factor

$$
\operatorname{tr}_{R}(T^a)Y^2.
$$

For a simple non-Abelian group, the generators are traceless in every finite-dimensional representation:

$$
\operatorname{tr}_{R}(T^a)=0.
$$

So $U(1)_Y^2SU(3)_c$ and $U(1)_Y^2SU(2)_L$ vanish automatically. They are not additional independent Standard Model anomaly-cancellation conditions.

## Why this is not numerology

The cancellation is a consistency requirement. It is also a clue.

The cancellation connects quark and lepton hypercharges in a way that is not obvious if one looks only at low-energy electromagnetism. It is one reason grand-unified representations are attractive: in $SU(5)$ language, one generation fits into

$$
\overline{\mathbf 5}\oplus \mathbf {10},
$$

and the anomaly cancellation becomes group-theoretically packaged. One does not need grand unification for the Standard Model to be consistent, but anomaly cancellation is one of the facts that grand unification makes feel less accidental.

There is also an important modesty lesson. Anomaly cancellation constrains the fermion content, but it does not uniquely derive the Standard Model. Many anomaly-free chiral gauge theories exist.

## Common pitfalls

**Using right-handed fields without conjugating.** A right-handed field should be converted to a left-handed conjugate field before summing anomalies. This flips both the representation and the hypercharge.

**Forgetting multiplicities.** The $Q$ field has three colors and two weak components. Both factors matter in $U(1)$ sums.

**Using $Q_{\rm em}$ instead of $Y$.** Gauge anomalies must be checked for the unbroken gauge group in the UV. Before electroweak symmetry breaking, the relevant abelian gauge symmetry is $U(1)_Y$, not electromagnetism.

**Stopping at triangle anomalies.** Perturbative triangle anomalies are not the whole story. The $SU(2)$ global anomaly is a separate large-gauge-transformation test.

**Thinking global anomalies are harmless for gauge symmetries.** A global anomaly of a gauge redundancy is also an inconsistency.

**Forgetting that cancellation is generation-by-generation.** The Standard Model cancels anomalies within each generation, not only after summing over all three known generations.

## Relations to other pages

The ABJ triangle and Fujikawa pages explain why anomalies appear at all. The Background Fields and Gauging chapter explains why gauge anomalies are obstructions to gauging. The ’t Hooft Anomalies chapter explains why anomalies of global symmetries can be allowed and useful. The Standard Model pages in the Gauge Theories volume develop the physical fermion content and gauge interactions in more detail.

This page is deliberately a calculation page: it does not derive the Standard Model, grand unification, or fermion masses. It gives the anomaly-cancellation check that every chiral gauge theory must pass.

## Research status

This calculation is settled. What remains active is the broader use of anomaly constraints in model building, generalized symmetries, global forms of the Standard Model gauge group, discrete gauge symmetries, higher-form symmetries, and beyond-Standard-Model chiral gauge theories.

The most common research-level refinement is that anomaly cancellation is not only a perturbative Lie-algebra condition. One must also specify the global form of the gauge group and check possible global anomalies on allowed spacetime manifolds and gauge bundles.

## Exercises

### Exercise 1: Add a right-handed neutrino

Add a sterile right-handed neutrino $\nu_R$ to the Standard Model. In left-handed notation this is $\nu^c=(\mathbf 1,\mathbf 1)_0$. Show that it does not affect any anomaly sum.

<details><summary><strong>Solution</strong></summary>

The field $\nu^c$ is a singlet under $SU(3)_c$ and $SU(2)_L$, and has $Y=0$. Therefore it contributes zero to

$$
SU(3)^3,\quad SU(2)^3,\quad SU(3)^2U(1),\quad SU(2)^2U(1),\quad \operatorname{grav}^2U(1),\quad U(1)^3.
$$

It also does not change the number of $SU(2)$ doublets, so it does not affect the Witten anomaly check.

</details>

### Exercise 2: Check the SU(2)²U(1) sum

Redo the $SU(2)^2U(1)_Y$ anomaly sum, carefully explaining every multiplicity.

<details><summary><strong>Solution</strong></summary>

The contributing fields are $Q$ and $L$, because they are the only $SU(2)_L$ doublets.

For $Q$, there are three colors. Each color gives one $SU(2)$ doublet with $Y=1/6$ and $T(\mathbf 2)=1/2$:

$$
3\cdot \frac12\cdot\frac16=\frac14.
$$

For $L$, there is one color-singlet doublet with $Y=-1/2$:

$$
1\cdot\frac12\cdot\left(-\frac12\right)=-\frac14.
$$

The total is zero.

</details>

### Exercise 3: Why the electron singlet has $Y=1$ in this table

The right-handed electron has electric charge $Q_{\rm em}=-1$ and $T_3=0$. Why does the anomaly table use $e^c$ with $Y=+1$?

<details><summary><strong>Solution</strong></summary>

The physical right-handed electron field has

$$
Y(e_R)=-1.
$$

For anomaly sums we rewrite it as a left-handed charge-conjugate field

$$
e^c_L=(e_R)^c.
$$

Charge conjugation flips the abelian charge, so

$$
Y(e^c_L)=+1.
$$

The table lists only left-handed Weyl fields, so it uses $e^c$ rather than $e_R$.

</details>

### Exercise 4: Show the cubic hypercharge sum vanishes

Compute

$$
6\left(\frac16\right)^3+3\left(-\frac23\right)^3+3\left(\frac13\right)^3+2\left(-\frac12\right)^3+1^3.
$$

<details><summary><strong>Solution</strong></summary>

The terms are

$$
\frac{1}{36},\qquad -\frac89,\qquad \frac19,\qquad -\frac14,\qquad 1.
$$

With denominator $36$,

$$
\frac{1}{36}-\frac{32}{36}+\frac{4}{36}-\frac{9}{36}+\frac{36}{36}=0.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§75–77 for chiral gauge theories and anomalies, and §§87–89 for the Standard Model field content.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.4 for gauge anomalies in the Standard Model.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chs. 21–22 for gauge theories, anomalies, and Standard Model structure.
- C. P. Burgess, *Introduction to Effective Field Theory*, §9.1 for the Standard Model as an effective theory and its anomaly-cancellation condition.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” for mixed gauge-gravitational anomaly technology.
- E. Witten, “An SU(2) Anomaly,” for the global $SU(2)$ anomaly.

## Version history

- 2026-06-17: Initial polished calculation page. Added one-generation Standard Model anomaly table, all perturbative anomaly sums, Witten anomaly check, convention notes, and exercises.
