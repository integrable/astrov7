---
title: "Wess–Zumino Consistency Condition"
description: "Derives the Wess–Zumino consistency condition for anomalies, explains its BRST cohomology form, and shows how it constrains possible anomalous Ward identities."
sidebar:
  label: "Wess–Zumino Consistency"
  order: 12
level: Advanced
status: "Polished draft"
source: "Wess–Zumino; Bardeen; Zumino descent; Bardeen–Zumino currents; Weinberg Vol. II; Bertlmann; Harvey TASI anomaly lectures; standard BRST-cohomology treatments."
topics:
  - Wess-Zumino consistency condition
  - anomaly consistency
  - consistent anomaly
  - BRST cohomology
  - local counterterms
  - descent equations
  - Ward identities
canonicalTopics:
  - wess-zumino-consistency-condition
  - anomaly-cohomology
  - consistent-anomaly
  - brst-anomaly-class
researchStatus:
  established:
    - "An anomaly obtained as the variation of a quantum effective action must obey the Wess–Zumino consistency condition."
    - "In BRST language, consistent local anomalies are ghost-number-one BRST cohomology classes modulo local counterterms and total derivatives."
  active:
    - "The same consistency logic remains central in modern work on supersymmetric anomalies, Weyl anomalies, generalized symmetries, anomaly inflow, and symmetry TFT."
---

## Summary

The **Wess–Zumino consistency condition** is the integrability condition that any anomaly must satisfy if it is the variation of a quantum effective action.

Suppose a theory is coupled to background fields $A$ and the effective action has anomalous variation

$$
\delta_\alpha W[A]=\mathcal A(\alpha;A).
$$

If the transformations close as

$$
[\delta_\alpha,\delta_\beta]=\delta_{[\alpha,\beta]_{\mathfrak g}},
$$

then consistency of the two possible orders of variation requires

$$
\delta_\alpha\mathcal A(\beta;A)
-\delta_\beta\mathcal A(\alpha;A)
=\mathcal A([\alpha,\beta]_{\mathfrak g};A).
$$

This is the Wess–Zumino consistency condition.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing the Wess-Zumino consistency condition as compatibility between the gauge algebra, effective-action variation, BRST cocycle condition, counterterm ambiguity, and anomaly class.](/figures/symmetry-anomalies-topology/wess-zumino-consistency-cohomology.svg)

<figcaption>

An anomalous variation $\mathcal A(\alpha;A)$ cannot be arbitrary. It must be compatible with the algebra of background transformations. In BRST language the same statement is $s a_d^1+d a_{d-1}^2=0$, modulo local counterterms.

</figcaption>
</figure>

The condition does not say that the anomaly vanishes. It says that a genuine anomaly must be **compatible with the symmetry algebra**. This is why the previous page emphasized the word **consistent**: a consistent anomaly is one that can arise as the variation of $W[A]$.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/), and [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) first.

You should know the background-field convention

$$
D=d-iA,
\qquad
F=dA-iA\wedge A,
\qquad
\delta_\alpha A=D\alpha.
$$

The bracket $[\alpha,\beta]_{\mathfrak g}$ below means the parameter determined by the transformation algebra through

$$
[\delta_\alpha,\delta_\beta]=\delta_{[\alpha,\beta]_{\mathfrak g}}.
$$

This notation avoids hiding a convention-dependent sign in the Lie bracket of Hermitian matrices.

## Core idea

An anomaly is not just any term that spoils a Ward identity. It is a term that can arise from a quantum effective action.

Let $W[A]$ be the connected generating functional in a fixed background $A$. An infinitesimal background gauge transformation gives

$$
\delta_\alpha W[A]=\mathcal A(\alpha;A),
$$

where $\mathcal A$ is linear in the gauge parameter $\alpha$ and local in $\alpha$ and $A$ for a perturbative local anomaly.

Now act with two transformations. Since $W[A]$ is a functional, the commutator of its variations must equal the variation associated with the commutator of transformations:

$$
[\delta_\alpha,\delta_\beta]W[A]
=\delta_{[\alpha,\beta]_{\mathfrak g}}W[A].
$$

The left side is

$$
[\delta_\alpha,\delta_\beta]W
=\delta_\alpha\mathcal A(\beta;A)
-\delta_\beta\mathcal A(\alpha;A),
$$

while the right side is

$$
\delta_{[\alpha,\beta]_{\mathfrak g}}W
=\mathcal A([\alpha,\beta]_{\mathfrak g};A).
$$

Equating them gives the consistency condition.

This is the same mathematical move as checking equality of mixed partial derivatives. The anomaly is a one-form on the space of background fields along gauge-orbit directions; Wess–Zumino consistency says that this one-form has the curvature dictated by the transformation algebra.

:::note[Source note]
The original Wess–Zumino analysis was phrased in terms of anomalous Ward identities and effective actions. Modern treatments often rewrite the same condition as a BRST-cohomology problem. The latter is usually the cleanest language for classification, while the former is usually the cleanest language for physics.
:::

## Setup and conventions

We work on a closed $d$-dimensional spacetime $M_d$ unless stated otherwise. Boundary terms are discussed separately because they change the interpretation of anomalies by allowing inflow or edge degrees of freedom.

For a background internal symmetry connection $A$, the anomalous variation is written

$$
\delta_\alpha W[A]=\int_{M_d}\mathcal I_d^{(1)}(\alpha,A),
$$

or, in the descent normalization used in this volume,

$$
\delta_\alpha\log Z[A]=2\pi i\int_{M_d}I_d^{(1)}(\alpha,A),
\qquad
\delta_\alpha W[A]=2\pi\int_{M_d}I_d^{(1)}(\alpha,A).
$$

The superscript $(1)$ denotes ghost number one or, equivalently, linearity in the infinitesimal transformation parameter. It is not a form degree. The form degree of $I_d^{(1)}$ is $d$.

A local counterterm is a local functional

$$
B[A]=\int_{M_d} b_d^{(0)}(A).
$$

Replacing

$$
W[A]\longrightarrow W[A]+B[A]
$$

changes the anomaly by

$$
\mathcal A(\alpha;A)
\longrightarrow
\mathcal A(\alpha;A)+\delta_\alpha B[A].
$$

Therefore two anomaly representatives that differ by the variation of a local counterterm describe the same anomaly class.

## Effective-action derivation

Let $\mathcal A_\alpha$ abbreviate $\mathcal A(\alpha;A)$. Start with

$$
\delta_\alpha W=\mathcal A_\alpha.
$$

Apply $\delta_\beta$:

$$
\delta_\beta\delta_\alpha W=\delta_\beta\mathcal A_\alpha.
$$

Interchange $\alpha$ and $\beta$, subtract, and use closure:

$$
\delta_\alpha\delta_\beta W-
\delta_\beta\delta_\alpha W
=[\delta_\alpha,\delta_\beta]W
=\delta_{[\alpha,\beta]_{\mathfrak g}}W.
$$

Thus

$$
\delta_\alpha\mathcal A_\beta-
\delta_\beta\mathcal A_\alpha
=\mathcal A_{[\alpha,\beta]_{\mathfrak g}}.
$$

This derivation is deliberately short because the idea is simple. The hard part is not proving the condition. The hard part is finding all local functionals $\mathcal A_\alpha$ that obey it, modulo counterterms.

That classification problem is what anomaly descent and BRST cohomology solve.

## Abelian case

For an Abelian background symmetry, the algebra bracket vanishes:

$$
[\delta_\alpha,\delta_\beta]=0.
$$

Wess–Zumino consistency becomes

$$
\delta_\alpha\mathcal A_\beta
=\delta_\beta\mathcal A_\alpha.
$$

So the anomalous variation must be locally integrable on background-field space.

For example, in four dimensions a common Abelian anomaly representative has the schematic form

$$
\mathcal A_\alpha
=c\int_{M_4}\alpha\,F\wedge F.
$$

Since $F$ is invariant under an Abelian background gauge transformation,

$$
\delta_\beta F=0,
$$

we get

$$
\delta_\beta\mathcal A_\alpha=0
=\delta_\alpha\mathcal A_\beta.
$$

The Abelian anomaly passes the Wess–Zumino test.

The same logic applies to a Weyl anomaly. Local Weyl transformations commute, so the Weyl anomaly must satisfy

$$
\delta_{\sigma_1}\mathcal A_{\sigma_2}
=\delta_{\sigma_2}\mathcal A_{\sigma_1}.
$$

This condition strongly constrains possible curvature terms in the trace anomaly.

## Non-Abelian case

For a non-Abelian background symmetry, the bracket term matters. A candidate anomaly of the form

$$
\mathcal A_\alpha=\int_{M_d}\operatorname{tr}(\alpha\,X[A])
$$

is not automatically allowed. It must satisfy

$$
\delta_\alpha\mathcal A_\beta-
\delta_\beta\mathcal A_\alpha
=\mathcal A_{[\alpha,\beta]_{\mathfrak g}}.
$$

A gauge-covariant-looking expression is tempting, but not every covariant expression is a consistent anomaly. This is the reason the covariant anomaly on the previous page required special treatment: it is useful for covariant Ward identities, but the ordinary variation of $W[A]$ gives the consistent anomaly.

In four dimensions, the consistent non-Abelian gauge anomaly associated with a chiral fermion is obtained from the six-form polynomial

$$
I_6\sim \operatorname{tr}_R(F^3)
$$

by descent. Its explicit $d$-form representative contains both $A$ and $dA$ in a non-manifestly covariant way. That is not a bug. The non-covariant-looking terms are exactly what make the Wess–Zumino condition work.

:::caution[Covariant is not the same as consistent]
A covariant anomaly transforms nicely under background gauge transformations, but it is not generally the variation of the same local effective action. Wess–Zumino consistency is a test for **consistent** anomalies, not for arbitrary covariant current divergences.
:::

## BRST form

The compact modern form of Wess–Zumino consistency uses the BRST differential $s$.

Replace the infinitesimal gauge parameter by a ghost field $c$. For a background connection in the same Hermitian-generator convention, one may write schematically

$$
sA=Dc,
\qquad
sc=\text{the ghost expression that makes }s^2=0.
$$

The detailed sign in $sc$ depends on the convention for Hermitian versus anti-Hermitian generators and for the graded bracket. The invariant point is nilpotency:

$$
s^2=0.
$$

Let the local anomaly density be $a_d^{1}$, a $d$-form with ghost number one, so that

$$
\mathcal A=\int_{M_d}a_d^{1}.
$$

Wess–Zumino consistency becomes

$$
s\mathcal A=0.
$$

Locally, since densities are defined modulo total derivatives,

$$
s a_d^{1}+d a_{d-1}^{2}=0.
$$

A counterterm $B=\int b_d^{0}$ changes the anomaly by

$$
a_d^{1}\longrightarrow a_d^{1}+s b_d^{0}+d b_{d-1}^{1}.
$$

Thus local perturbative anomalies are classified by local BRST cohomology:

$$
\frac{\{a_d^{1}\mid s a_d^{1}+d a_{d-1}^{2}=0\}}
{\{s b_d^{0}+d b_{d-1}^{1}\}}.
$$

The numerator says “consistent.” The denominator says “not removable by a local counterterm.”

## Relation to descent

Descent equations produce solutions of Wess–Zumino consistency almost automatically.

Start with a closed invariant polynomial in degree $d+2$:

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

Under a gauge or local Lorentz transformation,

$$
\delta I_{d+1}^{(0)}=dI_d^{(1)}.
$$

Then the anomaly

$$
\delta\log Z=2\pi i\int_{M_d}I_d^{(1)}
$$

obeys Wess–Zumino consistency. The reason is structural: the descent was built from an invariant polynomial, and the BRST descent satisfies

$$
(s+d)(I_{d+2}+I_{d+1}^{(0)}+I_d^{(1)}+\cdots)=0
$$

in the total complex.

This is why anomaly polynomials are so powerful. They do not merely produce an anomaly density; they produce a density with the correct integrability properties.

## Counterterms and trivial anomalies

A candidate anomalous Ward identity may look nonzero but still be physically removable. If

$$
\mathcal A_\alpha=\delta_\alpha B[A]
$$

for some local counterterm $B[A]$, then redefining

$$
W'[A]=W[A]-B[A]
$$

removes it:

$$
\delta_\alpha W'[A]=0.
$$

Such an anomaly is called **trivial** in cohomology. It may still matter in a chosen renormalization scheme because it changes contact terms and currents, but it is not an obstruction to gauging.

This is the local-counterterm version of a familiar principle:

$$
\text{an anomaly class is physical; a representative is scheme-dependent.}
$$

The Bardeen counterterm in vector/axial anomaly calculations is the classic example. It moves the anomaly into the axial current so that the vector gauge symmetry is exact. The anomaly has not disappeared; its representative has changed.

## What the condition does and does not prove

Wess–Zumino consistency is a necessary condition for a local anomaly to come from an effective action. It is not by itself a complete dynamical calculation.

It does **not** determine the coefficient. Triangle diagrams, Fujikawa Jacobians, index theorems, or other calculations determine coefficients.

It does **not** decide whether a symmetry is global or gauged. That is a physical input. If the anomalous symmetry is a dynamical gauge redundancy, the theory is inconsistent unless the total anomaly cancels. If it is a global symmetry, the anomaly is valid ’t Hooft data.

It does **not** detect every possible global anomaly. A local anomaly polynomial may vanish even though a large gauge transformation or large diffeomorphism changes the sign or phase of the partition function.

It does **not** choose a unique current. Improvement terms, Bardeen–Zumino currents, and local counterterms change the representative.

What it does is more precise and more useful: it tells us which local anomalous Ward identities are compatible with the symmetry algebra.

## Common pitfalls

**Checking covariance instead of consistency.** A covariant expression may fail to be the variation of $W[A]$. Wess–Zumino consistency checks integrability, not merely transformation covariance.

**Dropping the bracket term in non-Abelian symmetry.** For non-Abelian transformations, the right side is not zero. The anomaly must reproduce the algebra.

**Mistaking a removable local term for an anomaly.** If a candidate anomaly is the variation of a local counterterm, it is a scheme artifact, not an obstruction.

**Ignoring boundary terms.** On a manifold with boundary, the same calculation produces boundary variations. These may be canceled by inflow or boundary degrees of freedom rather than by setting the anomaly to zero.

**Comparing formulas before comparing conventions.** The sign of $[\alpha,\beta]_{\mathfrak g}$, the sign of $F$, and the normalization of $\delta\log Z$ vary across references.

## Relations to other pages

- [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/) explains why Wess–Zumino consistency belongs to the consistent representative.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) explains the invariant-polynomial package that generates consistent anomaly representatives by descent.
- [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) develops the full descent tower after this page.
- [BRST Cohomology](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-cohomology/) gives the cohomological language used to classify gauge-invariant observables and anomalies.
- [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) uses the anomaly class as RG-invariant global-symmetry data.

## Research status

The Wess–Zumino condition is established textbook material for local anomalies. Its BRST form is one of the standard classification tools for gauge, gravitational, Weyl, and mixed perturbative anomalies.

The active frontier is not whether the condition is true. The frontier is how broadly the same integrability logic should be formulated for generalized symmetries, non-invertible defects, higher-categorical background fields, supersymmetric current multiplets, and global anomalies that are not captured by local differential forms.

## Exercises

### Exercise 1: Derive the condition

Assume $\delta_\alpha W=\mathcal A_\alpha$ and $[\delta_\alpha,\delta_\beta]=\delta_{[\alpha,\beta]_{\mathfrak g}}$. Derive the Wess–Zumino consistency condition.

<details><summary><strong>Solution</strong></summary>

Compute the commutator in two ways. First,

$$
[\delta_\alpha,\delta_\beta]W
=\delta_\alpha\mathcal A_\beta-
\delta_\beta\mathcal A_\alpha.
$$

Second, closure of the transformation algebra gives

$$
[\delta_\alpha,\delta_\beta]W
=\delta_{[\alpha,\beta]_{\mathfrak g}}W
=\mathcal A_{[\alpha,\beta]_{\mathfrak g}}.
$$

Equating these expressions gives

$$
\delta_\alpha\mathcal A_\beta-
\delta_\beta\mathcal A_\alpha
=\mathcal A_{[\alpha,\beta]_{\mathfrak g}}.
$$

</details>

### Exercise 2: Abelian anomaly check

In four dimensions let

$$
\mathcal A_\alpha=c\int_{M_4}\alpha F\wedge F
$$

for an Abelian background field $A$. Show that Wess–Zumino consistency holds.

<details><summary><strong>Solution</strong></summary>

For an Abelian background field,

$$
\delta_\beta A=d\beta,
\qquad
\delta_\beta F=d\delta_\beta A=d^2\beta=0.
$$

The parameters $\alpha$ and $\beta$ are independent infinitesimal transformation parameters, so $\delta_\beta\alpha=0$. Therefore

$$
\delta_\beta\mathcal A_\alpha=0,
\qquad
\delta_\alpha\mathcal A_\beta=0.
$$

The Abelian bracket vanishes, so the consistency condition reads $0=0$.

</details>

### Exercise 3: Trivial anomalies satisfy consistency

Let $\mathcal A_\alpha=\delta_\alpha B[A]$ for a local counterterm $B[A]$. Show that $\mathcal A_\alpha$ obeys Wess–Zumino consistency.

<details><summary><strong>Solution</strong></summary>

Using $\mathcal A_\alpha=\delta_\alpha B$,

$$
\delta_\alpha\mathcal A_\beta-
\delta_\beta\mathcal A_\alpha
=\delta_\alpha\delta_\beta B-
\delta_\beta\delta_\alpha B
=[\delta_\alpha,\delta_\beta]B.
$$

By closure,

$$
[\delta_\alpha,\delta_\beta]B
=\delta_{[\alpha,\beta]_{\mathfrak g}}B
=\mathcal A_{[\alpha,\beta]_{\mathfrak g}}.
$$

So any counterterm variation automatically satisfies the condition. This is why consistency alone is not enough to identify a nontrivial anomaly.

</details>

### Exercise 4: BRST interpretation

Suppose $\mathcal A=\int a_d^1$ and $s\mathcal A=0$. If $a_d^1=s b_d^0+d b_{d-1}^1$, explain why the anomaly is removable on a closed spacetime.

<details><summary><strong>Solution</strong></summary>

On a closed spacetime,

$$
\int_{M_d} d b_{d-1}^1=0.
$$

Thus

$$
\mathcal A=\int_{M_d}s b_d^0=s\int_{M_d}b_d^0.
$$

This is the BRST variation of a local counterterm. Adding the counterterm

$$
B=-\int_{M_d}b_d^0
$$

to the effective action shifts the anomalous variation by $-\mathcal A$ and removes it.

</details>

## References

- J. Wess and B. Zumino, “Consequences of anomalous Ward identities.” The original consistency-condition analysis.
- W. A. Bardeen, “Anomalous Ward identities in spinor field theories.” Classic non-Abelian anomaly analysis.
- W. A. Bardeen and B. Zumino, “Consistent and covariant anomalies in gauge and gravitational theories.” Standard reference for the consistent/covariant distinction and Bardeen–Zumino currents.
- B. Zumino, Y.-S. Wu, and A. Zee, “Chiral anomalies, higher dimensions, and differential geometry.” Classic descent viewpoint.
- L. Alvarez-Gaumé and P. Ginsparg, “The structure of gauge and gravitational anomalies.” Useful bridge between index theory and descent.
- L. Alvarez-Gaumé and E. Witten, “Gravitational anomalies.” Classic gravitational-anomaly polynomial treatment.
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*. Detailed textbook treatment.
- J. A. Harvey, “TASI 2003 Lectures on Anomalies.” Review of descent, anomaly polynomials, and applications.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. See the anomaly and BRST/gauge-theory chapters.
- M. Srednicki, *Quantum Field Theory*. See the sections on chiral gauge theories, anomalies, and fermion path integrals.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the anomaly chapter.

## Version history

- 2026-06-18: First polished draft. Added effective-action derivation, Abelian and non-Abelian forms, BRST cohomology interpretation, counterterm discussion, and exercises.
