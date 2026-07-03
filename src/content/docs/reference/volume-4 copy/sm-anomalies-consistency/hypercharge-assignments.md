---
title: "Hypercharge Assignments"
description: "Derives the Standard Model hypercharge assignments from anomaly cancellation, Yukawa invariance, and the electric-charge convention Q = T³ + Y."
sidebar:
  label: "Hypercharge Assignments"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77 and §§87–91; Schwartz Chs. 29–30; Burgess Ch. 9; Weinberg Vol. II Standard Model and anomaly material."
topics:
  - hypercharge
  - Standard Model anomaly cancellation
  - Yukawa couplings
  - electric charge
  - chiral fermions
canonicalTopics:
  - standard-model-hypercharge
  - hypercharge-assignments
  - anomaly-cancellation-one-generation
  - yukawa-invariance
  - electric-charge-quantization
researchStatus:
  established:
    - "In the minimal one-generation Standard Model, anomaly cancellation fixes the relative hypercharges up to an overall normalization and the naming of the up- and down-type singlets."
  active:
    - "The deeper origin of the hypercharge pattern depends on possible ultraviolet structure, such as grand unification, global form, discrete quotients, or additional anomaly-free symmetries."
---

## Summary

Hypercharge is the part of the Standard Model that looks least natural if one only lists particles. Why should the numbers

$$
\frac{1}{6},\quad -\frac{2}{3},\quad \frac{1}{3},\quad -\frac{1}{2},\quad 1
$$

appear in exactly the right places? The answer is not that anomaly cancellation alone explains everything, but it gets surprisingly close. In the minimal one-generation Standard Model, the perturbative anomaly equations force the relative hypercharges to be

$$
Y_Q:q,\qquad
Y_L:-3q,\qquad
Y_{u^c}:-4q,\qquad
Y_{d^c}:2q,\qquad
Y_{e^c}:6q,
$$

up to an overall normalization and the interchange of the two color-antitriplet singlets. Choosing the electromagnetic convention $Q=T^3+Y$ and the neutral Higgs vacuum fixes

$$
q=\frac{1}{6}.
$$

Equivalently, if one begins with gauge-invariant Yukawa couplings and a Higgs doublet of hypercharge $Y_H$, anomaly cancellation gives $Y_Q=Y_H/3$. With $Y_H=1/2$, the usual table follows.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Hypercharge assignment logic](/figures/gauge-theories-standard-model/hypercharge-assignment-logic.svg)

<figcaption>

Hypercharge is constrained by several independent-looking requirements. The anomaly equations are quantum consistency conditions, Yukawa invariance tells the Higgs how to connect left- and right-handed fermions, and the neutral Higgs vacuum fixes the normalization for the electromagnetic charge $Q=T^3+Y$.

</figcaption>
</figure>

The moral is delicate. Anomaly cancellation is not a numerology game; it is a consistency test for gauging $U(1)_Y$. But the fact that the same numbers also make the Yukawa couplings and electric charges work is one of the most compact clues that the Standard Model representation content is not random confetti.

## Prerequisites

Read [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) and [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) first. You should also know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), and the [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/).

We use the volume convention

$$
Q_{\rm em}=T^3+Y.
$$

All anomaly equations below are written using left-handed Weyl fermions. The conjugate fields $u_L^c,d_L^c,e_L^c$ have hypercharges opposite to those of the usual physical right-handed fields $u_R,d_R,e_R$.

## The unknown-hypercharge ledger

Begin with the non-Abelian representation content of one generation but do not assume the numerical hypercharges. Write

$$
\begin{array}{c|c|c|c}
\text{left-handed Weyl field} & SU(3)_c & SU(2)_L & Y \\
\hline
Q_L & \mathbf3 & \mathbf2 & Y_Q \\
u_L^c & \overline{\mathbf3} & \mathbf1 & Y_u \\
d_L^c & \overline{\mathbf3} & \mathbf1 & Y_d \\
L_L & \mathbf1 & \mathbf2 & Y_L \\
e_L^c & \mathbf1 & \mathbf1 & Y_e
\end{array}
$$

Here $Y_u$ means $Y_{u^c}$ and $Y_d$ means $Y_{d^c}$. This notation is compact, but remember the physics: $u_L^c$ is the left-handed antiparticle field associated with $u_R$, not another ordinary up quark.

A sterile neutrino $N_L^c\sim(\mathbf1,\mathbf1)_0$ is not included in the minimal table. Since it has $Y=0$, it would not change any hypercharge anomaly equation.

## The anomaly equations

The perturbative gauge-anomaly constraints involving hypercharge are

$$
[SU(3)_c]^2U(1)_Y,
\qquad
[SU(2)_L]^2U(1)_Y,
\qquad
[U(1)_Y]^3,
\qquad
[\text{gravity}]^2U(1)_Y.
$$

Suppressing common Dynkin-index factors, the color–hypercharge condition is

$$
2Y_Q+Y_u+Y_d=0.
$$

The factor of $2$ is the weak-doublet multiplicity of $Q_L$. The weak-isospin–hypercharge condition is

$$
3Y_Q+Y_L=0,
$$

where the factor of $3$ is color multiplicity. The cubic hypercharge condition is

$$
6Y_Q^3+3Y_u^3+3Y_d^3+2Y_L^3+Y_e^3=0.
$$

The mixed gauge–gravitational condition is

$$
6Y_Q+3Y_u+3Y_d+2Y_L+Y_e=0.
$$

The multiplicities are ordinary state counts under the spectator gauge factors. For example, $Q_L$ has $3\times2=6$ Weyl components, so it contributes $6Y_Q^3$ to the cubic $U(1)_Y$ anomaly and $6Y_Q$ to the mixed gravitational–hypercharge anomaly.

There is also a global $SU(2)$ anomaly condition, but it is not a hypercharge equation. One generation has $3+1=4$ weak doublets, which is even.

## Solving the anomaly equations directly

Let

$$
Y_Q=q.
$$

The weak mixed anomaly gives

$$
Y_L=-3q.
$$

The color mixed anomaly gives

$$
Y_u+Y_d=-2q.
$$

The mixed gravitational anomaly gives

$$
6q+3(Y_u+Y_d)+2(-3q)+Y_e=0.
$$

Using $Y_u+Y_d=-2q$, this becomes

$$
6q-6q-6q+Y_e=0,
$$

so

$$
Y_e=6q.
$$

Only the cubic hypercharge condition remains. Substitute $Y_L=-3q$ and $Y_e=6q$:

$$
6q^3+3Y_u^3+3Y_d^3+2(-3q)^3+(6q)^3=0.
$$

This simplifies to

$$
Y_u^3+Y_d^3+56q^3=0.
$$

Since $Y_u+Y_d=-2q$,

$$
Y_u^3+Y_d^3=(Y_u+Y_d)^3-3Y_uY_d(Y_u+Y_d)
=-8q^3+6qY_uY_d.
$$

Thus, for $q\ne0$,

$$
-8q^3+6qY_uY_d+56q^3=0,
$$

or

$$
Y_uY_d=-8q^2.
$$

The two singlet hypercharges are therefore the roots of

$$
x^2+2qx-8q^2=0,
$$

namely

$$
x=2q,
\qquad
x=-4q.
$$

So anomaly cancellation gives

$$
Y_L=-3q,
\qquad
Y_e=6q,
\qquad
\{Y_u,Y_d\}=\{-4q,2q\}.
$$

To match the observed naming convention, the field that couples to the up-type quark is called $u^c$, so

$$
Y_{u^c}=-4q,
\qquad
Y_{d^c}=2q.
$$

Setting $q=1/6$ gives

$$
Y_Q=\frac{1}{6},
\qquad
Y_{u^c}=-\frac{2}{3},
\qquad
Y_{d^c}=\frac{1}{3},
\qquad
Y_L=-\frac{1}{2},
\qquad
Y_{e^c}=1.
$$

This is the Standard Model table.

:::note[What was assumed?]
This derivation assumed the non-Abelian representation content of one generation and the absence of an additional nonzero-hypercharge singlet. It fixed the relative $U(1)_Y$ charges. The overall normalization of a $U(1)$ generator remains conventional until we specify how $Y$ is embedded in $Q_{\rm em}=T^3+Y$ and how the gauge coupling is normalized.
:::

## The Yukawa-coupling derivation

There is another useful route. Instead of solving the singlet charges directly from the anomaly equations, ask that the renormalizable Yukawa interactions exist. Let the Higgs doublet have hypercharge

$$
Y_H=h.
$$

The gauge-invariant Yukawa terms, written in all-left-handed language, have the schematic form

$$
Q_L H u_L^c,
\qquad
Q_L H^\dagger d_L^c,
\qquad
L_L H^\dagger e_L^c.
$$

Their hypercharge neutrality requires

$$
Y_Q+h+Y_u=0,
$$

$$
Y_Q-h+Y_d=0,
$$

and

$$
Y_L-h+Y_e=0.
$$

Therefore

$$
Y_u=-Y_Q-h,
\qquad
Y_d=-Y_Q+h,
\qquad
Y_e=h-Y_L.
$$

The color mixed anomaly

$$
2Y_Q+Y_u+Y_d=0
$$

is then automatic. The weak mixed anomaly gives

$$
3Y_Q+Y_L=0.
$$

The mixed gravitational anomaly becomes

$$
6Y_Q+3(-Y_Q-h)+3(-Y_Q+h)+2Y_L+(h-Y_L)=0,
$$

which reduces to

$$
Y_L+h=0.
$$

Combining this with $Y_L=-3Y_Q$ gives

$$
Y_Q=\frac{h}{3}.
$$

The cubic anomaly gives the same condition. Indeed, after imposing Yukawa invariance and $Y_L=-3Y_Q$, the cubic anomaly is

$$
(h-3Y_Q)^3=0.
$$

Thus

$$
Y_Q=\frac{Y_H}{3},
\qquad
Y_L=-Y_H,
\qquad
Y_u=-\frac{4Y_H}{3},
\qquad
Y_d=\frac{2Y_H}{3},
\qquad
Y_e=2Y_H.
$$

With the Standard Model Higgs normalization $Y_H=1/2$,

$$
Y_Q=\frac{1}{6},
\qquad
Y_L=-\frac{1}{2},
\qquad
Y_{u^c}=-\frac{2}{3},
\qquad
Y_{d^c}=\frac{1}{3},
\qquad
Y_{e^c}=1.
$$

This is often the most physically transparent derivation because it shows how anomaly cancellation cooperates with mass generation.

## Fixing the overall normalization by electric charge

A pure $U(1)$ generator can be rescaled together with its gauge coupling. The convention used in this volume is

$$
Q_{\rm em}=T^3+Y.
$$

The Higgs vacuum sits in the neutral lower component of the Higgs doublet. Since the lower component has

$$
T^3=-\frac{1}{2},
$$

neutrality of the vacuum requires

$$
0=Q_{\rm em}\langle H\rangle
=\left(-\frac{1}{2}+Y_H\right)\langle H\rangle.
$$

Therefore

$$
Y_H=\frac{1}{2}.
$$

Once this is fixed, the electric charges follow immediately:

$$
Q(u_L)=\frac{1}{2}+\frac{1}{6}=\frac{2}{3},
\qquad
Q(d_L)=-\frac{1}{2}+\frac{1}{6}=-\frac{1}{3},
$$

$$
Q(\nu_L)=\frac{1}{2}-\frac{1}{2}=0,
\qquad
Q(e_L)=-\frac{1}{2}-\frac{1}{2}=-1.
$$

For the physical right-handed fields, remember to undo the all-left conjugation:

$$
Y(u_R)=+\frac{2}{3},
\qquad
Y(d_R)=-\frac{1}{3},
\qquad
Y(e_R)=-1.
$$

The Higgs convention therefore turns the abstract anomaly solution into the observed electric-charge spectrum.

## What hypercharge cancellation does not prove

The derivation above is powerful, but it has boundaries.

First, it does not explain why there are three generations. The anomaly cancellation works generation by generation, so repeating the whole generation any number of times preserves the perturbative gauge-anomaly cancellations.

Second, it does not uniquely explain the global form of the gauge group. The same local Lie algebra

$$
\mathfrak{su}(3)\oplus\mathfrak{su}(2)\oplus\mathfrak{u}(1)
$$

can correspond to different global groups, such as quotients by subgroups of the common center. Hypercharge assignments are closely related to those quotients, but perturbative anomaly cancellation alone does not determine the full global form.

Third, if new fermions are added, new anomaly-free combinations can appear. A familiar example is $B-L$: in the minimal Standard Model without a right-handed neutrino, $B-L$ is an accidental global symmetry but is not gaugeable without a mixed gravitational obstruction. Adding a sterile neutrino per generation makes gauged $B-L$ possible from the anomaly viewpoint.

Fourth, anomaly cancellation is a low-energy consistency condition. It is compatible with grand-unified explanations such as embedding one generation into $\overline{\mathbf5}\oplus\mathbf{10}$ of $SU(5)$, but it does not force that interpretation by itself.

That is the right attitude: anomaly cancellation is not the whole origin story, but it is a severe consistency filter. A theory that fails it cannot be the quantum Standard Model.

## Common mistakes

**Using right-handed hypercharges in the all-left table.** The physical $u_R$ has $Y=+2/3$, but the left-handed conjugate $u_L^c$ has $Y=-2/3$. For anomaly sums, decide which bookkeeping you use and stick to it.

**Forgetting multiplicities.** The quark doublet contributes six Weyl fermions to $Y^3$ but only two color triplets to $SU(3)^2U(1)$ and three weak doublets to $SU(2)^2U(1)$. One line in a table is not always one fermion for anomaly arithmetic.

**Thinking the cubic anomaly alone fixes everything.** The cubic equation is essential, but it works together with the mixed non-Abelian and mixed gravitational equations. The simple final numbers come from the full system.

**Confusing normalization with physics.** Replacing $Y$ by $cY$ and $g'$ by $g'/c$ leaves the local coupling $g'Y$ unchanged. The normalization used here is fixed by $Q=T^3+Y$ and the Higgs vacuum.

**Treating anomaly cancellation as an aesthetic criterion.** Gauge-anomaly cancellation is a consistency requirement. A theory with an uncancelled gauge anomaly has no gauge-invariant quantum definition with the advertised gauge symmetry.

## Exercises

### Exercise 1: Solve the anomaly equations

Starting from unknowns $Y_Q,Y_u,Y_d,Y_L,Y_e$, solve the four perturbative anomaly equations and show that, for nonzero $Y_Q=q$,

$$
Y_L=-3q,
\qquad
Y_e=6q,
\qquad
\{Y_u,Y_d\}=\{-4q,2q\}.
$$

<details><summary><strong>Solution</strong></summary>

The weak mixed anomaly gives $Y_L=-3q$. The color mixed anomaly gives $Y_u+Y_d=-2q$. The mixed gravitational anomaly gives

$$
6q+3(Y_u+Y_d)+2Y_L+Y_e=0.
$$

Substituting $Y_u+Y_d=-2q$ and $Y_L=-3q$ gives $Y_e=6q$.

The cubic anomaly becomes

$$
6q^3+3Y_u^3+3Y_d^3+2(-3q)^3+(6q)^3=0,
$$

or

$$
Y_u^3+Y_d^3+56q^3=0.
$$

Use

$$
Y_u^3+Y_d^3=(Y_u+Y_d)^3-3Y_uY_d(Y_u+Y_d)
$$

and $Y_u+Y_d=-2q$ to get

$$
-8q^3+6qY_uY_d+56q^3=0.
$$

For $q\ne0$,

$$
Y_uY_d=-8q^2.
$$

Thus $Y_u$ and $Y_d$ are roots of

$$
x^2+2qx-8q^2=0,
$$

so the two roots are $2q$ and $-4q$.

</details>

### Exercise 2: Derive hypercharge from Yukawa invariance

Assume the Yukawa terms $QHu^c$, $QH^\dagger d^c$, and $LH^\dagger e^c$ are gauge invariant. Let $Y_H=h$. Use anomaly cancellation to show that $Y_Q=h/3$.

<details><summary><strong>Solution</strong></summary>

Yukawa invariance gives

$$
Y_u=-Y_Q-h,
\qquad
Y_d=-Y_Q+h,
\qquad
Y_e=h-Y_L.
$$

The weak mixed anomaly gives

$$
3Y_Q+Y_L=0,
$$

so $Y_L=-3Y_Q$. The mixed gravitational anomaly becomes

$$
6Y_Q+3(-Y_Q-h)+3(-Y_Q+h)+2Y_L+(h-Y_L)=0.
$$

The first three terms cancel, leaving

$$
Y_L+h=0.
$$

Using $Y_L=-3Y_Q$ gives

$$
Y_Q=\frac{h}{3}.
$$

With $h=1/2$, $Y_Q=1/6$.

</details>

### Exercise 3: Check electric charges

Using $Q_{\rm em}=T^3+Y$, compute the electric charges of $u_L,d_L,\nu_L,e_L$ from $Y_Q=1/6$ and $Y_L=-1/2$.

<details><summary><strong>Solution</strong></summary>

For weak doublets, the upper component has $T^3=+1/2$ and the lower component has $T^3=-1/2$. Therefore

$$
Q(u_L)=\frac{1}{2}+\frac{1}{6}=\frac{2}{3},
\qquad
Q(d_L)=-\frac{1}{2}+\frac{1}{6}=-\frac{1}{3},
$$

and

$$
Q(\nu_L)=\frac{1}{2}-\frac{1}{2}=0,
\qquad
Q(e_L)=-\frac{1}{2}-\frac{1}{2}=-1.
$$

</details>

### Exercise 4: Add a sterile neutrino

Add $N_L^c\sim(\mathbf1,\mathbf1)_0$. Show that none of the hypercharge anomaly equations change.

<details><summary><strong>Solution</strong></summary>

The new field is a singlet under $SU(3)_c$ and $SU(2)_L$, so it does not affect the mixed non-Abelian anomalies. Its hypercharge is zero, so its contribution to the cubic and mixed gravitational hypercharge anomalies is

$$
0^3=0,
\qquad
0=0.
$$

Thus all four hypercharge anomaly equations are unchanged.

</details>

## Relations to other pages

- [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) performs the explicit cancellation check after the usual hypercharges are known.
- [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) explains the $\sum Y=0$ condition geometrically.
- [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) gives the representation table used here.
- [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/) explains why the Higgs doublet relates the left-handed doublets to the singlet conjugates.
- [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/) explains how hypercharge also knows about global quotient data.

## Research status

The anomaly-based derivation of the Standard Model hypercharges is established textbook physics. The open questions are interpretive and ultraviolet: why the representation content is what it is, whether it embeds into a unified gauge group, whether the global gauge group is a quotient, and whether additional anomaly-free symmetries such as $B-L$ are gauged in nature.

## Where to go next

Continue to [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/). That page explains why the linear equation

$$
6Y_Q+3Y_u+3Y_d+2Y_L+Y_e=0
$$

is not just another arithmetic check, but the condition that hypercharge remains gauge-consistent when the theory is placed in a curved background.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomaly, and Standard Model sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction and anomaly chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory and anomaly-cancellation discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and chiral anomaly constraints.
- Reviews on global forms of the Standard Model gauge group for the relation between hypercharge quantization, quotient groups, and line operators.

## Version history

- **2026-06-19:** Initial page deriving Standard Model hypercharge assignments from anomaly cancellation, Yukawa invariance, and the convention $Q=T^3+Y$.
