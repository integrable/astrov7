---
title: "Anomaly Cancellation in One Generation"
description: "Computes the perturbative Standard Model gauge-anomaly cancellations in one generation using the all-left-handed Weyl fermion ledger and the convention Q = T³ + Y."
sidebar:
  label: "Anomaly Cancellation in One Generation"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77 and §§87–91; Schwartz Chs. 29–30; Burgess Ch. 9; Weinberg Vol. II Standard Model and anomaly material."
topics:
  - Standard Model anomaly cancellation
  - hypercharge
  - chiral fermions
  - one generation
  - mixed anomalies
  - global SU(2) anomaly
canonicalTopics:
  - standard-model-anomaly-cancellation
  - standard-model-hypercharge
  - anomaly-cancellation-one-generation
  - mixed-gauge-anomalies
  - cubic-hypercharge-anomaly
researchStatus:
  established:
    - "One Standard Model generation cancels all perturbative gauge anomalies and has an even number of left-handed SU(2) doublets."
  active:
    - "The deeper meaning of the Standard Model charge pattern is still model-dependent; anomaly cancellation is a consistency condition, not by itself a complete explanation of flavor, generations, or ultraviolet origin."
---

## Summary

One Standard Model generation is a small chiral miracle. In the convention $Q=T^3+Y$, the all-left-handed one-generation ledger is:

| left-handed Weyl field | $SU(3)_c$ | $SU(2)_L$ | $Y$ |
|---|---:|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $\mathbf3$ | $\mathbf2$ | $+1/6$ |
| $u_L^c$ | $\overline{\mathbf3}$ | $\mathbf1$ | $-2/3$ |
| $d_L^c$ | $\overline{\mathbf3}$ | $\mathbf1$ | $+1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $\mathbf1$ | $\mathbf2$ | $-1/2$ |
| $e_L^c$ | $\mathbf1$ | $\mathbf1$ | $+1$ |

Here $u_L^c,d_L^c,e_L^c$ are the left-handed charge-conjugate fields corresponding to the usual physical right-handed charged fermions. The minimal Standard Model has no right-handed neutrino. If a sterile field $N_L^c\sim(\mathbf1,\mathbf1)_0$ is added, it contributes zero to all gauge anomalies.

The consistency checks are

$$
[SU(3)_c]^3,
\qquad
[SU(3)_c]^2U(1)_Y,
\qquad
[SU(2)_L]^2U(1)_Y,
\qquad
[U(1)_Y]^3,
\qquad
[\text{gravity}]^2U(1)_Y,
$$

together with the global $SU(2)$ even-doublet test. One generation passes all of them.

<figure class="doc-figure" style="--figure-width: 58rem;">

![One-generation Standard Model anomaly cancellations](/figures/gauge-theories-standard-model/sm-one-generation-anomaly-cancellation.svg)

<figcaption>

The anomaly ledger for one Standard Model generation. The cancellations are not independent accidents: the same hypercharge assignments that make Yukawa couplings and electric charges work also pass the perturbative gauge-anomaly tests. The global $SU(2)$ test is separate and counts weak doublets mod $2$.

</figcaption>
</figure>

The most important habit is to keep multiplicities visible. A quark doublet is three colors times two weak components. In an $SU(3)^2U(1)_Y$ anomaly it counts as two color triplets; in an $SU(2)^2U(1)_Y$ anomaly it counts as three weak doublets; in a $Y^3$ anomaly it counts as six Weyl fermions.

## Prerequisites

You should first read [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/). You should also know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), and [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/).

We use

$$
T(\mathbf3)=T(\overline{\mathbf3})=\frac12,
\qquad
T(\mathbf2)=\frac12,
$$

for the fundamental Dynkin indices of $SU(3)$ and $SU(2)$. For the cubic $SU(3)$ anomaly we use

$$
A(\mathbf3)=+1,
\qquad
A(\overline{\mathbf3})=-1,
$$

with an arbitrary common normalization. Only the zero matters.

## The all-left-handed rule

The physical right-handed charged fermions are represented in the anomaly ledger by left-handed conjugate fields. The relevant replacements are

$$
 u_R\longleftrightarrow u_L^c\sim(\overline{\mathbf3},\mathbf1)_{-2/3},
\qquad
 d_R\longleftrightarrow d_L^c\sim(\overline{\mathbf3},\mathbf1)_{1/3},
\qquad
 e_R\longleftrightarrow e_L^c\sim(\mathbf1,\mathbf1)_{1}.
$$

The conjugation flips complex representations and flips the Abelian charge. After this rewrite, every entry in the ledger is left-handed, so no extra chirality sign is inserted.

:::caution[The fastest way to get the wrong answer]
Do not sum over $Q_L,u_R,d_R,L_L,e_R$ using the hypercharges of the physical right-handed fields unless you also insert the right-handed chirality sign. This page uses the all-left-handed ledger, so the signs are already built into $u_L^c,d_L^c,e_L^c$.
:::

## Cubic color anomaly

The $[SU(3)_c]^3$ anomaly receives contributions only from colored Weyl fermions. The quark doublet $Q_L$ contains two $SU(3)$ fundamentals, while $u_L^c$ and $d_L^c$ are antifundamentals. With

$$
A(\mathbf3)=+1,
\qquad
A(\overline{\mathbf3})=-1,
$$

we get

$$
[SU(3)_c]^3:
\qquad
2A(\mathbf3)+A(\overline{\mathbf3})+A(\overline{\mathbf3})
=2-1-1=0.
$$

This is the color version of vectorlike cancellation. QCD is chiral only in the sense that quarks participate differently in electroweak interactions. As far as color alone is concerned, one generation contains enough triplets and antitriplets to cancel the cubic color anomaly.

## Perturbative weak-isospin anomaly

There is no perturbative $[SU(2)_L]^3$ triangle anomaly in four dimensions because $SU(2)$ has no symmetric cubic invariant. Equivalently, the fundamental representation is pseudoreal, and the local cubic anomaly coefficient vanishes.

So the perturbative statement is simply

$$
[SU(2)_L]^3:
\qquad
0.
$$

This does not finish the $SU(2)$ story. There is also the global $SU(2)$ anomaly, which requires an even number of left-handed weak doublets. One Standard Model generation has

$$
3\text{ quark doublets from color}+1\text{ lepton doublet}=4
$$

left-handed $SU(2)_L$ doublets, which is even. The detailed topology behind this condition belongs to [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/), but the one-generation count is already visible here.

## Color–hypercharge anomaly

The mixed anomaly $[SU(3)_c]^2U(1)_Y$ contains two color generators and one hypercharge insertion. The contribution of a left-handed Weyl field is proportional to

$$
Y\,T_{SU(3)}(R_c)\,\dim(R_2).
$$

Only colored fields contribute. Since $T(\mathbf3)=T(\overline{\mathbf3})=1/2$, the common factor $1/2$ can be suppressed. Then

$$
[SU(3)_c]^2U(1)_Y:
\qquad
2\left(\frac16\right)
+
\left(-\frac23\right)
+
\left(\frac13\right)
=0.
$$

The factor of $2$ on $Q_L$ is the weak-doublet multiplicity. Written with the Dynkin-index factor displayed,

$$
2\left(\frac16\right)\frac12
+
\left(-\frac23\right)\frac12
+
\left(\frac13\right)\frac12
=
\frac16-\frac13+\frac16=0.
$$

## Weak-isospin–hypercharge anomaly

The mixed anomaly $[SU(2)_L]^2U(1)_Y$ contains two weak generators and one hypercharge insertion. The contribution of a left-handed Weyl field is proportional to

$$
Y\,T_{SU(2)}(R_2)\,\dim(R_c).
$$

Only weak doublets contribute. Since $T(\mathbf2)=1/2$, the condition is

$$
[SU(2)_L]^2U(1)_Y:
\qquad
3\left(\frac16\right)
+
\left(-\frac12\right)
=0.
$$

The factor of $3$ on $Q_L$ is the color multiplicity. With the common $1/2$ factor included,

$$
3\left(\frac16\right)\frac12
+
\left(-\frac12\right)\frac12
=
\frac14-\frac14=0.
$$

This cancellation is one of the cleanest links between quark and lepton hypercharges. The lepton doublet is not an afterthought; it cancels the hypercharge-weighted contribution of the three colored quark doublets.

## Cubic hypercharge anomaly

The $[U(1)_Y]^3$ anomaly sums $Y^3$ over all left-handed Weyl components. Now every color and weak component counts. Therefore

$$
[U(1)_Y]^3:
\qquad
6\left(\frac16\right)^3
+3\left(-\frac23\right)^3
+3\left(\frac13\right)^3
+2\left(-\frac12\right)^3
+1^3.
$$

Putting everything over a common denominator gives

$$
\frac{1}{36}
-
\frac{8}{9}
+
\frac{1}{9}
-
\frac14
+1
=
\frac{1-32+4-9+36}{36}=0.
$$

This is the most sensitive arithmetic check. It uses the quark and lepton charges, the color multiplicities, the weak multiplicities, and the conjugate-field signs.

## Mixed gravitational–hypercharge anomaly

The mixed $[\text{gravity}]^2U(1)_Y$ anomaly is proportional to the sum of hypercharges over all left-handed Weyl components:

$$
[\text{gravity}]^2U(1)_Y:
\qquad
6\left(\frac16\right)
+3\left(-\frac23\right)
+3\left(\frac13\right)
+2\left(-\frac12\right)
+1.
$$

The sum is

$$
1-2+1-1+1=0.
$$

This means the hypercharge gauge current remains consistent even when the theory is coupled to background spacetime geometry. The pure gravitational anomaly is absent in four-dimensional Lorentz-invariant theories of this type; the relevant Standard Model check is the mixed gravitational–hypercharge anomaly.

## The whole calculation in one table

The one-generation anomaly checks can be summarized as follows.

| Anomaly | Condition | One-generation value |
|---|---|---:|
| $[SU(3)_c]^3$ | $2A(\mathbf3)+A(\overline{\mathbf3})+A(\overline{\mathbf3})$ | $2-1-1=0$ |
| $[SU(2)_L]^3$ | no local cubic invariant | $0$ |
| $[SU(3)_c]^2U(1)_Y$ | $2Y_Q+Y_{u^c}+Y_{d^c}$ | $1/3-2/3+1/3=0$ |
| $[SU(2)_L]^2U(1)_Y$ | $3Y_Q+Y_L$ | $1/2-1/2=0$ |
| $[U(1)_Y]^3$ | $6Y_Q^3+3Y_{u^c}^3+3Y_{d^c}^3+2Y_L^3+Y_{e^c}^3$ | $0$ |
| $[\text{gravity}]^2U(1)_Y$ | $6Y_Q+3Y_{u^c}+3Y_{d^c}+2Y_L+Y_{e^c}$ | $0$ |
| global $SU(2)_L$ | number of left-handed doublets even | $3+1=4$ |

This table is often the quickest diagnostic for proposed extensions of the Standard Model. Add a chiral fermion? Run this table again. If the new fermion content is vectorlike, it cancels automatically. If it is genuinely chiral, the anomaly constraints are a hard gate.

## Why generation-by-generation cancellation matters

The Standard Model has three generations. Since each generation has the same gauge quantum numbers, the anomaly coefficient of the full theory is just three times the one-generation coefficient:

$$
\mathcal A_{\rm total}=3\mathcal A_{\rm one\ generation}=0.
$$

This is stronger than merely saying the three generations cancel together. The cancellation does not require a delicate relation among different generations. Each copy is independently consistent.

That fact is useful phenomenologically. Flavor physics may mix generations through Yukawa matrices, but anomaly cancellation is a statement about gauge representations. Changing the Yukawa basis or diagonalizing mass matrices does not change the anomaly coefficient.

## Hypercharge normalization

The zero conditions are invariant under an overall rescaling of hypercharge,

$$
Y\mapsto cY,
$$

provided the coupling $g'$ is rescaled oppositely so that $g'Y$ is unchanged. Under such a rescaling, the $G^2U(1)$ and gravitational–$U(1)$ anomalies scale by $c$, while the $U(1)^3$ anomaly scales by $c^3$. Zero remains zero.

This page uses $Q=T^3+Y$. If a source uses $Q=T^3+Y/2$, every hypercharge in the table is twice as large. The cancellation checks look different by factors of $2$ and $8$, but the same representation content passes.

## What anomaly cancellation does and does not explain

Anomaly cancellation is a consistency condition. It says which chiral charge assignments are allowed in a quantum gauge theory. It does not, by itself, prove that the Standard Model charge pattern is unique in every possible setting.

For example, anomaly cancellation plus the existence of the usual Yukawa couplings strongly ties the hypercharges together. Additional assumptions can lead to charge quantization and motivate grand-unified embeddings. But anomaly cancellation alone is not a full theory of why there are three generations, why the Yukawa matrices have their values, or why the gauge group has its particular global form.

The right attitude is: anomaly cancellation is not decorative numerology. It is a necessary quantum consistency filter. The Standard Model passing it is a structural fact that any proposed ultraviolet completion must respect.

## Common mistakes

**Forgetting the conjugates.** The fields $u_L^c,d_L^c,e_L^c$ have hypercharges $-2/3,+1/3,+1$, not the physical right-handed hypercharges $+2/3,-1/3,-1$.

**Dropping weak or color multiplicities.** The factors $6,3,3,2,1$ in the $Y^3$ sum are not optional. They are the dimensions of the non-Abelian representations.

**Using electric charges instead of hypercharges.** The anomaly being tested is hypercharge before electroweak symmetry breaking. Use $Y$, not $Q$, in the $U(1)_Y$ anomaly sums.

**Thinking $SU(2)^3=0$ is the whole $SU(2)$ test.** The perturbative triangle anomaly vanishes, but the global $SU(2)$ anomaly requires an even number of left-handed doublets.

**Adding a sterile neutrino and expecting anomaly trouble.** A gauge singlet with $Y=0$ contributes nothing to the gauge anomalies. It can matter enormously for neutrino masses, but not for these cancellation sums.

## Exercises

### Exercise 1: Check the cubic hypercharge sum

Verify explicitly that

$$
6\left(\frac16\right)^3
+3\left(-\frac23\right)^3
+3\left(\frac13\right)^3
+2\left(-\frac12\right)^3
+1^3=0.
$$

<details><summary><strong>Solution</strong></summary>

Compute each term:

$$
6\left(\frac16\right)^3=\frac1{36},
\qquad
3\left(-\frac23\right)^3=-\frac89,
\qquad
3\left(\frac13\right)^3=\frac19,
$$

and

$$
2\left(-\frac12\right)^3=-\frac14,
\qquad
1^3=1.
$$

With denominator $36$,

$$
\frac1{36}-\frac{32}{36}+\frac4{36}-\frac9{36}+\frac{36}{36}=0.
$$

</details>

### Exercise 2: Add a sterile neutrino

Add a left-handed sterile field $N_L^c\sim(\mathbf1,\mathbf1)_0$. Show that it changes none of the gauge-anomaly cancellation conditions.

<details><summary><strong>Solution</strong></summary>

The field is a singlet under $SU(3)_c$ and $SU(2)_L$, so it does not contribute to the non-Abelian cubic or mixed non-Abelian anomalies. Its hypercharge is $Y=0$, so it contributes

$$
Y=0,
\qquad
Y^3=0
$$

to the mixed gravitational–hypercharge and cubic hypercharge anomalies. It also is not an $SU(2)$ doublet, so it does not affect the global $SU(2)$ parity count.

</details>

### Exercise 3: Derive the weak mixed condition from Yukawa invariance

Assume the Standard Model Yukawa couplings are gauge invariant and use $Y_H=1/2$. Show that the mixed anomaly condition $3Y_Q+Y_L=0$ is not automatically guaranteed by the charged-fermion Yukawa terms alone.

<details><summary><strong>Solution</strong></summary>

Yukawa invariance gives relations among left- and right-handed hypercharges. In all-left notation these may be written as constraints on $Y_Q,Y_L,Y_{u^c},Y_{d^c},Y_{e^c}$ involving $Y_H$. They tie, for example, $Y_{u^c}$ and $Y_{d^c}$ to $Y_Q$ and $Y_H$, and $Y_{e^c}$ to $Y_L$ and $Y_H$.

However, the mixed $SU(2)^2U(1)$ anomaly involves only the weak doublets:

$$
3Y_Q+Y_L.
$$

The charged Yukawa terms alone do not force this combination to vanish. Anomaly cancellation supplies an additional condition linking the quark doublet and lepton doublet hypercharges. With the observed values,

$$
3\left(\frac16\right)-\frac12=0.
$$

</details>

## Relations to other pages

- [Gauge Anomalies in Chiral Theories](/gauge-theories-standard-model/sm-anomalies-consistency/gauge-anomalies-in-chiral-theories/) explains why these arithmetic identities are quantum consistency conditions.
- [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/) continues the story by combining anomaly cancellation with Yukawa invariance and electric charge.
- [Mixed Gauge–Gravitational Anomalies](/gauge-theories-standard-model/sm-anomalies-consistency/mixed-gauge-gravitational-anomalies/) gives the geometric interpretation of the $\sum Y=0$ check.
- [Global SU(2) Anomaly](/gauge-theories-standard-model/sm-anomalies-consistency/global-su2-anomaly/) explains the even-doublet condition beyond perturbation theory.
- [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) gives the representation table before rewriting right-handed fields as conjugates.

## Research status

The one-generation cancellation calculation is established textbook physics. The active questions begin one layer higher: why this representation content occurs, how it embeds into possible ultraviolet theories, what the global form of the gauge group is, and how anomaly constraints extend to generalized symmetries, defects, and possible beyond-Standard-Model sectors.

## Where to go next

Continue to [Hypercharge Assignments](/gauge-theories-standard-model/sm-anomalies-consistency/hypercharge-assignments/). It explains how the anomaly equations fit together with Yukawa couplings and the electric-charge operator $Q=T^3+Y$.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the chiral gauge theory, anomaly, and Standard Model sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction and anomaly chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory and anomaly-cancellation discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory, chiral fermions, and anomaly constraints.
- Coleman, *Aspects of Symmetry*, especially the lectures on currents, Ward identities, and symmetry in quantum field theory.
- Reviews on anomaly inflow and global anomalies for the modern topological interpretation of these cancellation conditions.

## Version history

- **2026-06-19:** Initial page computing one-generation Standard Model anomaly cancellation in the all-left-handed Weyl convention.
