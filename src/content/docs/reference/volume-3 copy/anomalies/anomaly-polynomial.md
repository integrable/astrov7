---
title: "Anomaly Polynomial"
description: "Explains how local perturbative anomalies are packaged by a closed anomaly polynomial, how descent produces anomalous Ward identities, and how index-theorem formulas fix coefficients."
sidebar:
  label: "Anomaly Polynomial"
  order: 13
level: Advanced
status: "Polished draft"
source: "Atiyah–Singer index theorem; Stora–Zumino descent; Alvarez-Gaumé–Witten gravitational anomalies; Bardeen–Zumino; Harvey TASI anomaly lectures; Srednicki, Schwartz, Weinberg, and Bertlmann."
topics:
  - anomaly polynomial
  - descent equations
  - Chern character
  - A-roof genus
  - gauge anomaly
  - gravitational anomaly
  - mixed anomaly
  - anomaly inflow
canonicalTopics:
  - anomaly-polynomial
  - descent-equations
  - chern-character
  - a-roof-genus
  - anomaly-inflow
researchStatus:
  established:
    - "Local perturbative anomalies of chiral fields in even spacetime dimensions are encoded by closed degree-(d+2) characteristic forms called anomaly polynomials."
    - "Descent from the anomaly polynomial produces consistent anomaly representatives and one-higher-dimensional inflow actions."
  active:
    - "Beyond local perturbative anomalies, modern anomaly classification uses eta invariants, differential cohomology, invertible field theories, cobordism, and symmetry TFT."
---

## Summary

The **anomaly polynomial** is a compact way to package local perturbative anomalies.

For a $d$-dimensional QFT, the anomaly polynomial is a closed $(d+2)$-form

$$
I_{d+2}(F,R),
$$

built from background gauge-field strengths $F$ and spacetime curvature two-forms $R$. It is not itself the anomalous Ward identity. Instead, it generates the anomaly by descent:

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

With the normalization of this volume,

$$
\delta\log Z=2\pi i\int_{M_d}I_d^{(1)}.
$$

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing the anomaly polynomial as a closed invariant form, its Chern-Simons descendant, descent variation, boundary anomaly, and bulk inflow interpretation.](/figures/symmetry-anomalies-topology/anomaly-polynomial-descent-tower.svg)

<figcaption>

The anomaly polynomial $I_{d+2}$ is one degree too high to be a Ward-identity density on $M_d$. Descent turns it into the local consistent anomaly $I_d^{(1)}$, while the intermediate Chern–Simons form $I_{d+1}^{(0)}$ gives the corresponding inflow term.

</figcaption>
</figure>

For a chiral spin-$1/2$ fermion in representation $R$ in $d=2n$ dimensions, the basic index-theorem formula is

$$
I_{2n+2}=\left[\widehat A(T)\operatorname{ch}_R(F)\right]_{2n+2},
$$

with an overall sign depending on chirality. This single formula produces gauge anomalies, mixed gauge-gravitational anomalies, and purely gravitational anomalies by expanding the characteristic classes to degree $2n+2$.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Fujikawa Method](/symmetry-anomalies-topology/anomalies/fujikawa-method/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/), [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/), and [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) first.

You should be comfortable with differential forms, characteristic classes, and the convention

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

## Core idea

A local perturbative anomaly in $d$ dimensions has three related descriptions:

1. a local anomalous Ward identity on $M_d$;
2. a descent representative $I_d^{(1)}$;
3. a closed invariant polynomial $I_{d+2}$ in two higher form degrees.

The first description is closest to current conservation. The second is closest to the effective-action variation. The third is closest to topology and index theory.

The surprise is that the third description is often the cleanest.

A chiral fermion determinant knows about the index of a Dirac operator in two more dimensions. The corresponding index density is built from characteristic classes. That density is $I_{d+2}$. Its descent gives the consistent anomaly in $d$ dimensions.

A good slogan is:

$$
\text{anomaly polynomial} = \text{index density whose descent is the anomaly}.
$$

This is why anomaly coefficients are quantized or protected in ways that ordinary loop coefficients are not. They are tied to topological data.

## Setup and conventions

The anomaly-polynomial discussion is most naturally Euclidean. Lorentzian Ward identities are recovered by analytic continuation and by translating the phase convention for $Z$.

For an internal background gauge field, we use the Hermitian-generator convention of this volume:

$$
A=A^aT_a,
\qquad
F=dA-iA\wedge A.
$$

For a representation $R$, define the Chern character by

$$
\operatorname{ch}_R(F)
=\operatorname{tr}_R\exp\!\left(\frac{F}{2\pi}\right)
$$

in the present Hermitian-connection convention. A mathematics convention using an anti-Hermitian connection $\mathcal A=-iA$ often writes the same object as

$$
\operatorname{tr}_R\exp\!\left(\frac{i\mathcal F}{2\pi}\right).
$$

These are the same after $\mathcal F=-iF$.

For the tangent bundle, write the curvature two-form as

$$
R^a{}_b=d\omega^a{}_b+\omega^a{}_c\wedge\omega^c{}_b.
$$

We use

$$
p_1(T)=-\frac{1}{8\pi^2}\operatorname{tr}R\wedge R,
$$

and

$$
\widehat A(T)=1-\frac{p_1(T)}{24}
+\frac{7p_1(T)^2-4p_2(T)}{5760}+\cdots.
$$

For a positive-chirality Weyl fermion in representation $R$ in $d=2n$ dimensions, the local anomaly polynomial is

$$
I_{2n+2}=\left[\widehat A(T)\operatorname{ch}_R(F)\right]_{2n+2}.
$$

A fermion of the opposite chirality contributes the negative of this polynomial. For real, pseudoreal, Majorana-Weyl, self-dual, or gravitino fields, extra factors or different genera can appear; those are not universal spin-$1/2$ formulas and should be stated case by case.

:::caution[Convention-sensitive formula]
Some references write $\operatorname{ch}_R(F)=\operatorname{tr}_R\exp(iF/2\pi)$ because their $F$ is not the same as the Hermitian $F$ used here. Do not mix these conventions. Check whether the connection is Hermitian or anti-Hermitian before comparing coefficients.
:::

## What the polynomial encodes

The anomaly polynomial simultaneously records several anomaly types.

A **pure gauge anomaly** involves only gauge-field strengths:

$$
I_{d+2}\supset \operatorname{tr}_R(F^{n+1})
\qquad
(d=2n).
$$

A **mixed gauge-gravitational anomaly** involves both gauge and tangent-bundle characteristic classes:

$$
I_{d+2}\supset \operatorname{tr}_R(F^r)\,p_i(T)\cdots.
$$

A **pure gravitational anomaly** involves only Pontryagin classes:

$$
I_{d+2}\supset p_i(T)p_j(T)\cdots.
$$

Not every spacetime dimension allows every type. For example, in four spacetime dimensions the local anomaly polynomial has degree six. There is no purely gravitational six-form built only from Pontryagin classes, so there is no pure local gravitational anomaly in four dimensions. But there can be mixed $U(1)$-gravity-gravity anomalies because a two-form gauge factor can multiply the four-form $p_1(T)$.

The polynomial is additive over independent chiral species:

$$
I_{d+2}^{\rm total}=\sum_{\text{chiral fields}}I_{d+2}^{\rm field}.
$$

For a dynamical gauge symmetry, consistency requires the total gauge anomaly polynomial to vanish in the relevant gauge directions. For a global symmetry, a nonzero polynomial is valid ’t Hooft anomaly data.

## Descent to the consistent anomaly

Let $I_{d+2}$ be a closed invariant polynomial. Locally, it can be written as

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

The form $I_{d+1}^{(0)}$ is a Chern–Simons-like form. It is not gauge invariant, but its exterior derivative is.

Under an infinitesimal background transformation,

$$
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

The $d$-form $I_d^{(1)}$ is the descent representative of the consistent anomaly:

$$
\delta\log Z=2\pi i\int_{M_d}I_d^{(1)}.
$$

The superscripts mean:

| Symbol | Meaning |
|---|---|
| $I_{d+2}$ | degree $d+2$, ghost number zero |
| $I_{d+1}^{(0)}$ | degree $d+1$, ghost number zero |
| $I_d^{(1)}$ | degree $d$, ghost number one |

The descent representative is not unique. If

$$
I_{d+1}^{(0)}\longrightarrow I_{d+1}^{(0)}+dL_d,
$$

then

$$
I_d^{(1)}\longrightarrow I_d^{(1)}+\delta L_d+dL_{d-1}^{(1)}.
$$

On a closed spacetime, the total derivative drops out and $\delta L_d$ is a local counterterm shift. Thus descent naturally explains why the anomaly class is invariant while the local representative is scheme-dependent.

## Inflow interpretation

Let $M_d=\partial X_{d+1}$. The same descent data defines a one-higher-dimensional inflow term

$$
S_{\rm inflow}=2\pi i\int_{X_{d+1}}I_{d+1}^{(0)}.
$$

Under a background transformation,

$$
\delta S_{\rm inflow}
=2\pi i\int_{X_{d+1}}dI_d^{(1)}
=2\pi i\int_{M_d}I_d^{(1)}.
$$

Depending on orientation convention, this cancels or reproduces the anomalous boundary variation. The invariant statement is that the anomalous $d$-dimensional theory can be viewed as a boundary or defect of a $(d+1)$-dimensional invertible theory whose local action is Chern–Simons-like.

This is the local perturbative version of anomaly inflow. Global anomalies often require more refined bulk actions involving eta invariants or differential cohomology rather than just Chern–Simons forms.

## Four-dimensional examples

For a four-dimensional theory, $d=4$, so the anomaly polynomial is a six-form $I_6$.

For left-handed Weyl fermions of charges $q_i$ under a background $U(1)$ symmetry, the gauge and mixed gauge-gravitational part is

$$
I_6
=\frac{1}{6}\left(\sum_i q_i^3\right)\left(\frac{F}{2\pi}\right)^3
-\frac{1}{24}\left(\sum_i q_i\right)\left(\frac{F}{2\pi}\right)p_1(T).
$$

Thus a dynamical $U(1)$ gauge theory requires

$$
\sum_i q_i^3=0,
\qquad
\sum_i q_i=0,
$$

for the local $U(1)^3$ and mixed $U(1)$-gravity-gravity gauge anomalies to cancel.

For a non-Abelian simple group, the pure gauge part contains

$$
I_6\supset \frac{1}{6(2\pi)^3}\operatorname{tr}_R(F^3).
$$

Equivalently, with generators $T_a$,

$$
\operatorname{tr}_R\left(T_{(a}T_bT_{c)}\right)
$$

controls the cubic gauge anomaly. Real and pseudoreal representations have vanishing cubic anomaly, while complex representations may contribute.

For the Standard Model, the famous anomaly-cancellation conditions are just the statement that the total six-form polynomial vanishes when restricted to dynamical gauge transformations.

:::note[Source note]
The polynomial formula is often the fastest way to reproduce the anomaly-cancellation conditions that are otherwise derived from triangle diagrams. The triangle diagram gives the same data in four dimensions; the anomaly polynomial organizes it in a dimension-independent and topology-aware way.
:::

## Two-dimensional example

For a two-dimensional chiral fermion, the anomaly polynomial is a four-form. Expanding

$$
\widehat A(T)\operatorname{ch}_R(F)
$$

to degree four gives

$$
I_4=\frac12\operatorname{tr}_R\left(\frac{F}{2\pi}\right)^2
-\frac{\dim R}{24}p_1(T),
$$

again with an overall sign depending on chirality.

The first term gives a two-dimensional gauge anomaly. The second term gives the gravitational anomaly, which in conformal language is related to the difference of left- and right-moving central charges,

$$
c_L-c_R.
$$

A nonchiral Dirac fermion has equal left- and right-moving contributions, so its local anomaly polynomial cancels.

## Six-dimensional orientation

For a six-dimensional theory, the local anomaly polynomial is an eight-form. A chiral spin-$1/2$ fermion produces terms schematically of the form

$$
I_8\supset
\operatorname{tr}_R(F^4),
\qquad
\operatorname{tr}_R(F^2)p_1(T),
\qquad
\dim R\,p_1(T)^2,
\qquad
\dim R\,p_2(T).
$$

In six dimensions, anomaly cancellation is much richer than in four dimensions. Chiral spinors, self-dual tensors, and gravitinos can all contribute. Some theories cancel anomalies directly by summing fields. Others cancel them through a Green–Schwarz mechanism, where the polynomial factorizes in a way that can be canceled by tensor-field inflow.

The exact six-dimensional coefficients depend on field type and chirality. The important structural lesson here is that the anomaly polynomial is the common ledger.

## Cancellation conditions

For a dynamical gauge field, local gauge anomaly cancellation means that the total consistent gauge variation vanishes. Polynomially, this requires the relevant gauge-dependent part of $I_{d+2}$ to vanish or be canceled by an allowed inflow mechanism.

For a collection of left-handed Weyl fermions in four dimensions, this means setting the cubic trace coefficients to zero:

$$
\sum_{\text{fermions}}\operatorname{tr}_{R_i}(T_{(a}T_bT_{c)})=0.
$$

For Abelian factors, it also includes mixed conditions such as

$$
\sum_i q_i=0,
\qquad
\sum_i q_i^3=0,
\qquad
\sum_i q_i\,T(R_i)=0
$$

for the appropriate $U(1)$-gravity-gravity, $U(1)^3$, and $G^2U(1)$ anomalies.

For a global symmetry, one does not set the polynomial to zero. Instead, the nonzero polynomial is the ’t Hooft anomaly. It constrains RG flow, symmetry-preserving gapped phases, boundary theories, and possible gaugings.

## What the polynomial does not see

The anomaly polynomial detects **local perturbative anomalies**. It does not detect all anomalies.

A theory can have a vanishing local anomaly polynomial and still have a global anomaly under a large gauge transformation or large diffeomorphism. Witten’s four-dimensional $SU(2)$ anomaly is the standard warning sign: it is not visible as a nonzero six-form polynomial built from $\operatorname{tr}F^3$ because $SU(2)$ has no cubic invariant, but it is still a real obstruction.

The anomaly polynomial also does not fully encode discrete-symmetry anomalies, time-reversal anomalies, or anomalies of generalized symmetries with discrete higher-form background fields. Those may require cohomology operations, eta invariants, bordism groups, differential cohomology, or symmetry TFT.

So the correct statement is not

$$
I_{d+2}=0\quad\Longleftrightarrow\quad\text{no anomaly at all}.
$$

The correct statement is

$$
I_{d+2}=0\quad\Longleftrightarrow\quad\text{no local perturbative anomaly of this polynomial type}.
$$

## Common pitfalls

**Using the polynomial as the Ward identity.** The anomaly polynomial has degree $d+2$. The Ward-identity anomaly in $d$ dimensions is obtained only after descent.

**Forgetting chirality.** Vectorlike pairs cancel because opposite chiralities contribute opposite polynomials.

**Mixing Hermitian and anti-Hermitian conventions.** This changes where factors of $i$ appear in $\operatorname{ch}(F)$ and Chern–Simons forms.

**Forgetting the trace normalization.** The coefficient of $\operatorname{tr}F^3$ depends on which trace is used. Always state whether the trace is in the fundamental, adjoint, or fermion representation.

**Assuming zero polynomial means no global anomaly.** The polynomial does not detect all topology-sensitive phases of the determinant line.

**Treating counterterm shifts as different anomalies.** Different descent representatives can describe the same anomaly class.

## Relations to other pages

- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) explains why descent representatives are consistent anomalies.
- [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) develops the local tower $I_{d+2}$, $I_{d+1}^{(0)}$, $I_d^{(1)}$ in detail.
- [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/) uses $I_6$ to state four-dimensional cancellation conditions.
- [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/) explains the Pontryagin-class and $\widehat A$ pieces.
- [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/) explains how products of gauge and gravitational characteristic classes encode mixed anomalies.
- [Anomaly Inflow](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) interprets the descent data as a bulk-boundary cancellation mechanism.

## Research status

For local perturbative anomalies, anomaly polynomials are established and canonical. They are the standard language for chiral fermion anomalies in even dimensions, gravitational anomalies, mixed anomalies, anomaly cancellation, and Green–Schwarz-type mechanisms.

The active frontier is the global and generalized extension. Modern anomaly theory often treats anomalies as invertible field theories one dimension higher. Local anomaly polynomials give the differential-form part of that story, but global anomalies, fermionic tangential structures, discrete symmetries, higher-form symmetries, and non-invertible symmetries require more refined data.

## Exercises

### Exercise 1: Four-dimensional Abelian cancellation

A four-dimensional theory has left-handed Weyl fermions of $U(1)$ charges $q_i$. Use the anomaly polynomial to state the local $U(1)^3$ and mixed $U(1)$-gravity-gravity cancellation conditions.

<details><summary><strong>Solution</strong></summary>

The six-form polynomial contains

$$
I_6
=\frac{1}{6}\left(\sum_i q_i^3\right)\left(\frac{F}{2\pi}\right)^3
-\frac{1}{24}\left(\sum_i q_i\right)\left(\frac{F}{2\pi}\right)p_1(T).
$$

For a dynamical $U(1)$ gauge symmetry, both coefficients must vanish:

$$
\sum_i q_i^3=0,
\qquad
\sum_i q_i=0.
$$

The first is the $U(1)^3$ anomaly cancellation condition. The second is the mixed gauge-gravitational anomaly cancellation condition.

</details>

### Exercise 2: Why no pure local gravitational anomaly in four dimensions?

Explain using form degree why a four-dimensional theory has no pure local gravitational anomaly polynomial.

<details><summary><strong>Solution</strong></summary>

For $d=4$, the local anomaly polynomial has degree $d+2=6$. Pure gravitational anomaly polynomials are built from Pontryagin classes,

$$
p_1(T),p_2(T),\ldots,
$$

whose degrees are multiples of four. There is no degree-six polynomial built only from Pontryagin classes. Therefore there is no pure local gravitational anomaly in four dimensions.

This does not rule out mixed gauge-gravitational anomalies, because a two-form gauge factor such as $F$ can multiply the four-form $p_1(T)$ to make a six-form.

</details>

### Exercise 3: Two-dimensional chiral pair

A two-dimensional left-moving fermion and a right-moving fermion transform in the same representation $R$. What is their total local anomaly polynomial?

<details><summary><strong>Solution</strong></summary>

Opposite chiralities contribute opposite anomaly polynomials. If the two fermions transform in the same representation, then

$$
I_4^{\rm left}+I_4^{\rm right}=I_4-I_4=0.
$$

Thus the vectorlike pair has no local perturbative gauge or gravitational anomaly.

</details>

### Exercise 4: Degree bookkeeping in descent

For a six-dimensional theory, what are the degrees of $I_{d+2}$, $I_{d+1}^{(0)}$, and $I_d^{(1)}$?

<details><summary><strong>Solution</strong></summary>

Here $d=6$. Therefore

$$
I_{d+2}=I_8,
\qquad
I_{d+1}^{(0)}=I_7^{(0)},
\qquad
I_d^{(1)}=I_6^{(1)}.
$$

The form $I_8$ is the closed anomaly polynomial. The seven-form $I_7^{(0)}$ is a local Chern–Simons descendant. The six-form $I_6^{(1)}$ is the local consistent anomaly density integrated over the six-dimensional spacetime.

</details>

## References

- M. F. Atiyah and I. M. Singer, index theorem papers. Mathematical origin of the characteristic-class formulas.
- L. Alvarez-Gaumé and E. Witten, “Gravitational anomalies.” Classic anomaly-polynomial treatment for gravitational anomalies.
- L. Alvarez-Gaumé and P. Ginsparg, “The structure of gauge and gravitational anomalies.” Useful structural treatment of descent and index theory.
- B. Zumino, Y.-S. Wu, and A. Zee, “Chiral anomalies, higher dimensions, and differential geometry.” Classic differential-geometric descent reference.
- W. A. Bardeen and B. Zumino, “Consistent and covariant anomalies in gauge and gravitational theories.” Standard consistent/covariant reference.
- M. B. Green and J. H. Schwarz, “Anomaly cancellations in supersymmetric D=10 gauge theory and superstring theory.” Classic Green–Schwarz mechanism.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*. Detailed textbook treatment.
- J. A. Harvey, “TASI 2003 Lectures on Anomalies.” Broad review of anomaly polynomials, descent, and applications.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. Gauge-theory and anomaly background.
- M. Srednicki, *Quantum Field Theory*. See chiral gauge theories and anomalies.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the anomaly chapter and Standard Model cancellation checks.

## Version history

- 2026-06-18: First polished draft. Added definition, index-density formula, descent and inflow interpretation, four-dimensional and two-dimensional examples, limitations, and exercises.
