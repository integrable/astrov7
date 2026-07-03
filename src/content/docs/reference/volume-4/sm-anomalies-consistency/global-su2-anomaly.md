---
title: "Global SU(2) Anomaly"
description: "Explains the Witten global SU(2) anomaly, the even-doublet condition, and why the Standard Model passes this nonperturbative consistency test."
sidebar:
  label: "Global SU(2) Anomaly"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§75 and 77; Schwartz Ch. 30; Witten's SU(2) anomaly paper; Weinberg Vol. II anomaly and electroweak material."
topics:
  - global SU(2) anomaly
  - Witten anomaly
  - Standard Model consistency
  - chiral gauge theory
  - weak doublets
  - mod-two index
canonicalTopics:
  - global-su2-anomaly
  - witten-anomaly
  - standard-model-anomaly-cancellation
  - chiral-gauge-theory
  - weak-isospin-doublets
researchStatus:
  established:
    - "A four-dimensional SU(2) gauge theory with an odd number of left-handed fundamental Weyl doublets has a nonperturbative sign obstruction and is not a consistent gauge theory."
  active:
    - "Modern treatments place this anomaly inside the broader framework of global anomalies, anomaly inflow, eta invariants, cobordism, and generalized anomaly constraints."
---

## Summary

The local $SU(2)^3$ gauge anomaly vanishes automatically in four dimensions. This is why the perturbative triangle-anomaly tests do not object to an arbitrary number of left-handed weak doublets. But $SU(2)$ has a more subtle quantum consistency condition: a theory with an odd number of left-handed Weyl fermions in the fundamental doublet representation has a **global $SU(2)$ anomaly**, also called the **Witten anomaly**.

The Standard Model passes because one generation contains

$$
3\text{ quark doublets }Q_L+1\text{ lepton doublet }L_L=4
$$

left-handed $SU(2)_L$ doublets. With $N_g$ generations,

$$
N_{\mathbf2}=4N_g,
$$

which is even.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Global SU(2) anomaly filter](/figures/gauge-theories-standard-model/global-su2-anomaly-filter.svg)

<figcaption>

The $SU(2)^3$ triangle anomaly vanishes locally, but the theory must also pass a global test. The nontrivial class in $\pi_4(SU(2))=\mathbb Z_2$ can flip the sign of the fermion path-integral measure for a single left-handed fundamental doublet. The Standard Model has four such doublets per generation, so the sign is $+1$.

</figcaption>
</figure>

The key lesson is that anomaly cancellation is not exhausted by Feynman triangle diagrams. Some obstructions are invisible in perturbation theory and only appear when one asks whether the fermion path integral can be defined consistently over the full gauge-field configuration space.

## Prerequisites

Read [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/), [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/), and [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) first. You should also know the [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) and the role of [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/).

This page uses $SU(2)$ to mean the local weak-isospin gauge algebra and its simply connected covering group. Global-form refinements of the full Standard Model gauge group are discussed separately in [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/).

## Core idea

Perturbative anomalies test infinitesimal gauge transformations connected continuously to the identity. A global anomaly tests something bigger: whether the quantum theory is invariant under gauge transformations in nontrivial topology classes.

For four-dimensional $SU(2)$ gauge theory, the relevant fact is

$$
\pi_4(SU(2))=\mathbb Z_2.
$$

This means there is a gauge transformation on compactified Euclidean spacetime $S^4$ that cannot be smoothly deformed to the identity. For a single left-handed Weyl doublet, the fermion functional integral changes sign under this transformation. Schematically,

$$
Z_{\rm fermion}[A^g]=-Z_{\rm fermion}[A]
$$

for the nontrivial large gauge transformation $g$. With $N_{\mathbf2}$ independent fundamental doublets,

$$
Z_{\rm fermion}[A^g]=(-1)^{N_{\mathbf2}}Z_{\rm fermion}[A].
$$

Gauge-related configurations must represent the same physical point in configuration space. Therefore a sign flip is not allowed. The consistency condition is

$$
N_{\mathbf2}\in2\mathbb Z.
$$

This is a mod-two condition. It is not a small correction to the triangle anomaly; it is a different kind of anomaly.

## Setup and conventions

We count left-handed Weyl fermions. In the Standard Model, the weak-doublet fields in one generation are

$$
Q_L=(u_L,d_L),
\qquad
L_L=(\nu_L,e_L).
$$

The quark doublet has an additional color index,

$$
Q_L^r,
\quad Q_L^g,
\quad Q_L^b,
$$

so it counts as three independent $SU(2)_L$ doublets for the global anomaly. The lepton doublet counts as one. Thus

$$
N_{\mathbf2}^{\rm one\ generation}=3+1=4.
$$

The right-handed charged fermions are $SU(2)_L$ singlets, and so are the left-handed conjugate fields $u_L^c,d_L^c,e_L^c$. A sterile neutrino $N_L^c$, if added, is also an $SU(2)_L$ singlet. None of these fields affects the global $SU(2)$ anomaly.

The Higgs doublet is a boson. The Witten anomaly discussed here is a sign obstruction in the chiral fermion measure, so the Higgs doublet does not contribute to the mod-two fermion count.

## Why the local SU(2) anomaly vanishes

The perturbative non-Abelian gauge anomaly in four dimensions is controlled by the symmetric trace

$$
d_R^{abc}=2\operatorname{tr}_R\left(T^a\{T^b,T^c\}\right).
$$

For $SU(2)$, the generators in the fundamental representation are $T^a=\sigma^a/2$, and

$$
\{T^b,T^c\}=\frac{1}{2}\delta^{bc}\mathbf1.
$$

Therefore

$$
d_{\mathbf2}^{abc}
=2\operatorname{tr}\left(T^a\frac{1}{2}\delta^{bc}\mathbf1\right)
=\delta^{bc}\operatorname{tr}T^a
=0.
$$

This vanishing is not an accident of the fundamental representation. $SU(2)$ has no independent totally symmetric invariant tensor $d^{abc}$ of the type that produces a local cubic gauge anomaly. That is why local triangle diagrams do not see a problem.

But this is not the end of the story. Local anomaly cancellation says the fermion determinant behaves correctly under infinitesimal gauge transformations. The global anomaly asks whether its sign can be chosen consistently around a noncontractible loop in gauge-field configuration space. For an odd number of doublets, the answer is no.

## The sign obstruction

The Euclidean fermion path integral for a left-handed Weyl fermion is more delicate than the path integral for a vectorlike Dirac fermion. Roughly speaking, one must choose a phase for a chiral determinant or Pfaffian over the space of gauge fields. The local anomaly is the curvature of this phase choice. The global anomaly is a holonomy: even when the local curvature obstruction vanishes, the sign may fail to return to itself around a nontrivial loop.

For $SU(2)$ in four dimensions, the nontrivial loop is tied to

$$
\pi_4(SU(2))=\mathbb Z_2.
$$

Along this loop, a single fundamental Weyl doublet has an odd spectral flow. Equivalently, the relevant mod-two index is nonzero. The result is a sign flip of the fermion measure.

A useful mental picture is this:

$$
\text{local anomaly}=\text{infinitesimal failure},
\qquad
\text{global anomaly}=\text{failure after going around a topological loop}.
$$

For one doublet, the loop returns the gauge field to a gauge-equivalent configuration but returns the fermion measure with the opposite sign. For two doublets, the two signs multiply to $+1$. Thus the anomaly is a parity test.

## The Standard Model doublet count

One generation contains the left-handed Weyl doublets

$$
Q_L\sim(\mathbf3,\mathbf2)_{1/6},
\qquad
L_L\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

The $SU(2)_L$ singlet conjugates $u_L^c,d_L^c,e_L^c$, and an optional sterile $N_L^c$, do not contribute. The doublet count is therefore

$$
Q_L:\text{ three colors }\Rightarrow3\text{ doublets},
\qquad
L_L:1\text{ doublet}.
$$

Hence

$$
N_{\mathbf2}=4
$$

per generation. For three generations,

$$
N_{\mathbf2}=12.
$$

Since both are even, the Standard Model has no global $SU(2)_L$ anomaly.

Notice the pleasing parallel with perturbative anomaly cancellation. The mixed $[SU(2)_L]^2U(1)_Y$ anomaly cancels because

$$
3\left(\frac{1}{6}\right)+\left(-\frac{1}{2}\right)=0.
$$

The global $SU(2)$ anomaly cancels because

$$
3+1=4\in2\mathbb Z.
$$

The first equation uses hypercharge. The second does not. It only knows the parity of the number of weak doublets.

## What would fail?

A toy electroweak-like theory with only one lepton doublet and no quark doublets would have

$$
N_{\mathbf2}=1,
$$

so it would suffer from the global $SU(2)$ anomaly. It would not be a consistent $SU(2)$ gauge theory even though its local $SU(2)^3$ triangle anomaly vanishes.

A theory with one additional chiral lepton doublet added to the Standard Model would change the count to

$$
N_{\mathbf2}=4N_g+1,
$$

which is odd for integer $N_g$. Such an extension would be inconsistent unless another new $SU(2)_L$ doublet, or some other anomaly-cancelling structure, is also added.

By contrast, a vectorlike pair of weak doublets is safe. Written in left-handed language, a vectorlike pair contributes two fundamental Weyl doublets. Two is even, so the mod-two obstruction cancels.

## Common pitfalls

**Do not confuse the global SU(2) anomaly with the ordinary SU(2) triangle anomaly.** The ordinary $SU(2)^3$ anomaly vanishes locally. The Witten anomaly is a nonperturbative mod-two obstruction.

**Color multiplicity counts.** The quark doublet $Q_L$ is one electroweak doublet for each color. It contributes three $SU(2)_L$ doublets to the global anomaly count.

**The Higgs doublet does not count.** This anomaly is a sign problem in the chiral fermion measure. Bosonic weak doublets do not contribute.

**Right-handed singlets do not count.** Fields such as $u_R,d_R,e_R$, or equivalently $u_L^c,d_L^c,e_L^c$, are weak singlets in the minimal Standard Model.

**Even local anomaly cancellation is not enough.** A chiral gauge theory must pass both local and global anomaly tests. The slogan is: triangle diagrams check the neighborhood; global anomalies check the topology.

## Relations to other pages

- [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) explains the perturbative obstruction from triangle diagrams.
- [Anomaly Cancellation in One Generation](/gauge-theories-standard-model/sm-anomalies-consistency/anomaly-cancellation-in-one-generation/) performs the ordinary Standard Model anomaly-cancellation checks.
- [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) explains another consistency test that is local but not purely gauge-theoretic.
- [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/) contrasts fatal gauge anomalies with physical anomalous global currents.
- [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) gives the representation table used for the doublet count.
- [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/) explains how global choices of gauge group affect line operators and charge quantization.

## Research status

The even-doublet condition for four-dimensional $SU(2)$ gauge theories is established. Its conceptual home has broadened over time. Modern anomaly theory treats it as one example of a global anomaly detected by topology and index theory. In more advanced language, such anomalies can be encoded by invertible field theories in one higher dimension and studied using cobordism and eta invariants.

For this chapter, the important point is simpler: the Standard Model is not merely free of perturbative gauge anomalies. It also passes the global $SU(2)_L$ test generation by generation.

## Exercises

### Exercise 1: Count Standard Model doublets

Count the number of left-handed $SU(2)_L$ fundamental doublets in one Standard Model generation.

<details><summary><strong>Solution</strong></summary>

The quark doublet $Q_L$ has three color copies, so it contributes three weak doublets. The lepton doublet $L_L$ contributes one. Therefore

$$
N_{\mathbf2}=3+1=4.
$$

This is even, so one generation passes the Witten anomaly test.

</details>

### Exercise 2: Why no local cubic SU(2) anomaly?

Using $T^a=\sigma^a/2$, show that

$$
2\operatorname{tr}\left(T^a\{T^b,T^c\}\right)=0
$$

in the fundamental representation of $SU(2)$.

<details><summary><strong>Solution</strong></summary>

The Pauli matrices obey

$$
\{T^b,T^c\}=\frac{1}{2}\delta^{bc}\mathbf1.
$$

Therefore

$$
2\operatorname{tr}\left(T^a\{T^b,T^c\}\right)
=2\operatorname{tr}\left(T^a\frac{1}{2}\delta^{bc}\mathbf1\right)
=\delta^{bc}\operatorname{tr}T^a.
$$

Since $T^a$ is traceless,

$$
\operatorname{tr}T^a=0,
$$

and the cubic local anomaly coefficient vanishes.

</details>

### Exercise 3: Add one new lepton doublet

Suppose the Standard Model is extended by one extra left-handed lepton-like Weyl doublet and no other new weak doublets. Does the theory pass the global $SU(2)$ anomaly test?

<details><summary><strong>Solution</strong></summary>

With three ordinary generations, the Standard Model has

$$
N_{\mathbf2}=12.
$$

Adding one new left-handed weak doublet gives

$$
N_{\mathbf2}=13.
$$

This is odd, so the extension has the global $SU(2)$ anomaly unless additional fields or structure cancel it.

</details>

### Exercise 4: Add a vectorlike pair

A vectorlike weak doublet pair consists of a left-handed doublet and a right-handed doublet with conjugate quantum numbers. Rewritten using only left-handed fields, how many $SU(2)$ fundamental doublets does it add modulo two?

<details><summary><strong>Solution</strong></summary>

A right-handed doublet can be rewritten as a left-handed conjugate field. For $SU(2)$, the fundamental representation is pseudoreal, so the conjugate is again a doublet for purposes of the mod-two anomaly count. Thus a vectorlike pair contributes

$$
2
$$

left-handed doublets, which is even. It does not change the Witten anomaly condition.

</details>

## Where to go next

Continue to [Baryon and Lepton Number Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/baryon-and-lepton-number-anomalies/). The global $SU(2)$ anomaly is a fatal obstruction for a gauge redundancy; baryon and lepton number anomalies are physical violations of accidental global currents.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the sections on chiral gauge theories, anomalies, and the path integral for fermions.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the anomaly chapter and the Standard Model representation discussion.
- Witten, “An $SU(2)$ Anomaly,” for the original global-anomaly argument.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and anomaly constraints.
- Reviews on global anomalies, eta invariants, anomaly inflow, and cobordism for the modern topological formulation.

## Version history

- **2026-06-19:** Initial page explaining the Witten global $SU(2)$ anomaly and the Standard Model even-doublet check.
