---
title: "Wess–Zumino Consistency Condition"
description: "Model calculation deriving the Wess–Zumino consistency condition for anomalies from the Lie algebra of gauge transformations."
sidebar:
  label: "Wess–Zumino Consistency Condition"
  order: 10
level: Advanced
status: "Polished draft"
source: "Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II anomaly chapters; Wess–Zumino, Consequences of anomalous Ward identities."
topics:
  - anomalies
  - Wess–Zumino consistency
  - Ward identities
  - descent equations
  - BRST cohomology
canonicalTopics:
  - wess-zumino-consistency-condition
  - consistent-anomaly
  - anomaly-descent
  - brst-cohomology
researchStatus:
  established:
    - "The Wess–Zumino consistency condition is the standard integrability condition that any consistent anomaly must satisfy."
  active:
    - "Modern applications include supersymmetric anomalies, generalized symmetries, anomaly inflow, higher-group backgrounds, and boundary SymTFT formulations."
---

## Summary

An anomaly is not an arbitrary violation of a Ward identity. If it comes from the variation of a quantum effective action, it must respect the algebra of the transformations that are being anomalously realized. This integrability requirement is the **Wess–Zumino consistency condition**.

Let $W[A]$ be the effective action in background gauge fields. Suppose an infinitesimal gauge transformation with parameter $\lambda$ gives

$$
\delta_\lambda W[A]=\mathcal A_\lambda[A].
$$

Here $\mathcal A_\lambda[A]$ is the integrated anomaly. Gauge transformations obey

$$
[\delta_\lambda,\delta_\eta]=\delta_{[\lambda,\eta]},
$$

so applying this commutator to $W[A]$ gives

$$
\boxed{
\delta_\lambda\mathcal A_\eta
-\delta_\eta\mathcal A_\lambda
=\mathcal A_{[\lambda,\eta]}.
}
$$

This is the Wess–Zumino consistency condition. It says that a **consistent anomaly** is a one-cocycle for the gauge-transformation algebra. In BRST language, it becomes

$$
s\mathcal A=0,
$$

modulo anomalies shifted by local counterterms.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A commutative diagram showing two gauge variations of the effective action and the Wess–Zumino consistency condition as the equality of their commutator with the anomaly for the commutator parameter.](/figures/symmetry-anomalies-topology/wess-zumino-consistency-condition.svg)

<figcaption>

A consistent anomaly is not any local functional. Since it is the gauge variation of an effective action, two anomalous variations must reproduce the Lie algebra of gauge transformations. This is the Wess–Zumino consistency condition.

</figcaption>
</figure>

## Prerequisites

You should know the model-library pages on the ABJ anomaly, the Fujikawa Jacobian, anomaly cancellation in the Standard Model, and Chern–Simons level quantization. You should also know the distinction between a gauge anomaly and a ’t Hooft anomaly.

We write the generating functional as

$$
Z[A]=e^{iW[A]},
$$

and define the integrated anomaly by

$$
\delta_\lambda W[A]=\mathcal A_\lambda[A].
$$

For non-Abelian gauge fields, the infinitesimal transformation is written schematically as

$$
\delta_\lambda A=D\lambda.
$$

The sign of $D\lambda$ depends on whether one uses active or passive transformations and whether generators are Hermitian or anti-Hermitian. The consistency condition itself is independent of that convention once the same convention is used everywhere.

## The calculation

Gauge transformations form a Lie algebra. If $\lambda$ and $\eta$ are Lie-algebra-valued functions, then

$$
[\delta_\lambda,\delta_\eta]=\delta_{[\lambda,\eta]},
$$

where

$$
[\lambda,\eta]=i[\lambda^aT_a,\eta^bT_b]
$$

up to the convention used for Hermitian generators. Now act on the effective action:

$$
[\delta_\lambda,\delta_\eta]W[A]
=\delta_\lambda(\delta_\eta W[A])-\delta_\eta(\delta_\lambda W[A]).
$$

Using

$$
\delta_\lambda W[A]=\mathcal A_\lambda[A],
$$

we get

$$
[\delta_\lambda,\delta_\eta]W[A]
=\delta_\lambda\mathcal A_\eta[A]
-\delta_\eta\mathcal A_\lambda[A].
$$

But the gauge algebra also says

$$
[\delta_\lambda,\delta_\eta]W[A]
=\delta_{[\lambda,\eta]}W[A]
=\mathcal A_{[\lambda,\eta]}[A].
$$

Equating the two expressions gives

$$
\delta_\lambda\mathcal A_\eta
-\delta_\eta\mathcal A_\lambda
=\mathcal A_{[\lambda,\eta]}.
$$

That is the whole derivation. Its power is that it constrains possible anomalies without computing a triangle diagram.

:::note[Source note: “consistent”]
The word “consistent” here has a technical meaning: the anomaly is the variation of an effective action and therefore satisfies the Wess–Zumino condition. It does not mean the quantum theory is physically consistent. A gauge anomaly can be a consistent anomaly and still make a gauge theory inconsistent unless it cancels.
:::

## Local anomaly notation

Often the anomaly is written as

$$
\mathcal A_\lambda[A]
=\int d^dx\,\lambda^a(x)\mathcal G_a[A](x),
$$

where $\mathcal G_a[A]$ is the local anomaly density. For example, in four dimensions an Abelian axial anomaly has the schematic form

$$
\mathcal A_\alpha[A]
=\frac{q^2}{16\pi^2}\int \alpha\,F\wedge F
$$

in differential-form notation up to the Lorentzian normalization convention.

For an Abelian gauge algebra, $[\lambda,\eta]=0$. The Wess–Zumino condition reduces to

$$
\delta_\lambda\mathcal A_\eta
=\delta_\eta\mathcal A_\lambda.
$$

If the Abelian anomaly depends only on $F$ and $\delta_\lambda F=0$, this condition is automatic.

For a non-Abelian gauge anomaly, the condition is nontrivial. It constrains the relative coefficients of the terms involving $A$, $dA$, and $A^3$ in the consistent anomaly.

## Counterterms and trivial anomalies

The effective action is not unique. One may add a local counterterm

$$
W[A]\mapsto W[A]+C[A].
$$

The anomaly then shifts by

$$
\mathcal A_\lambda[A]\mapsto
\mathcal A_\lambda[A]+\delta_\lambda C[A].
$$

An anomaly of the form

$$
\mathcal A_\lambda=\delta_\lambda C
$$

is called trivial in anomaly cohomology: it can be removed by adding a local counterterm. A nontrivial anomaly is a solution of the Wess–Zumino condition that is not of this form.

Thus the classification problem is not simply

$$
\delta_\lambda\mathcal A_\eta-\delta_\eta\mathcal A_\lambda=\mathcal A_{[\lambda,\eta]}.
$$

It is the classification of solutions modulo counterterm shifts.

This is why anomaly formulas sometimes change between schemes. The anomaly itself can be moved between different currents or symmetry transformations by counterterms, but a nontrivial obstruction cannot be removed altogether.

## BRST form

The BRST formulation packages the Wess–Zumino condition efficiently. Replace the gauge parameter by a ghost field $c$ with ghost number $1$. The BRST transformation satisfies

$$
s^2=0.
$$

An anomaly is now a local functional of ghost number $1$:

$$
\mathcal A=\int I_d^{(1)}(c,A).
$$

The Wess–Zumino consistency condition becomes

$$
s\mathcal A=0.
$$

A counterterm shift is

$$
\mathcal A\mapsto\mathcal A+sC.
$$

Therefore anomalies live in BRST cohomology:

$$
\mathcal A\in H^1(s\mid d)
$$

in the local form-language version, where total derivatives are quotiented appropriately.

:::note[Why BRST is useful]
The BRST form turns the consistency condition from a two-parameter Lie-algebra identity into a nilpotency equation. This is the cleanest route to descent equations and anomaly classification.
:::

## Descent equations

Consistent gauge anomalies in even dimension $d=2n$ are generated by invariant polynomials in $d+2=2n+2$ dimensions. Start with

$$
I_{2n+2}=\operatorname{tr}(F^{n+1}).
$$

Locally,

$$
I_{2n+2}=dI_{2n+1}^{(0)}(A),
$$

where $I_{2n+1}^{(0)}$ is a Chern–Simons form. Under a gauge or BRST transformation,

$$
sI_{2n+1}^{(0)}+dI_{2n}^{(1)}=0.
$$

The consistent anomaly is

$$
\mathcal A=2\pi i\int_{M_{2n}} I_{2n}^{(1)}
$$

up to the normalization set by the fermion representation and chirality. Applying $s$ again gives

$$
sI_{2n}^{(1)}+dI_{2n-1}^{(2)}=0,
$$

so after integration on a closed spacetime,

$$
s\mathcal A=0.
$$

This is the descent-equation proof of Wess–Zumino consistency.

## Consistent versus covariant anomalies

A consistent anomaly satisfies the Wess–Zumino condition because it is the variation of an effective action. It is the anomaly obtained by functionally differentiating a single $W[A]$.

A covariant anomaly transforms covariantly under gauge transformations and is often simpler to write. For example, it may take the schematic form

$$
D_\mu J^\mu_{\mathrm{cov}}\propto F\wedge F.
$$

But the covariant anomaly is generally not the direct variation of one local effective action in the same way. The consistent and covariant currents differ by a Bardeen–Zumino current:

$$
J_{\mathrm{cov}}=J_{\mathrm{cons}}+J_{\mathrm{BZ}}.
$$

Correspondingly, the anomalies differ by the divergence or variation of a local polynomial built from the background field.

This distinction matters in anomaly matching, hydrodynamics, supersymmetric anomalies, and inflow. When checking Wess–Zumino consistency, use the consistent anomaly.

## Example: Abelian anomaly

Let

$$
\mathcal A_\alpha[A]=C\int_M \alpha\,F\wedge F
$$

in four dimensions, where $\alpha$ is an Abelian gauge parameter. Since

$$
\delta_\beta F=0,
$$

we have

$$
\delta_\beta\mathcal A_\alpha=0
$$

if the parameters are treated as independent test functions. Also

$$
[\alpha,\beta]=0.
$$

Thus

$$
\delta_\alpha\mathcal A_\beta-\delta_\beta\mathcal A_\alpha=0=\mathcal A_{[\alpha,\beta]}.
$$

So the Abelian $F\wedge F$ anomaly satisfies Wess–Zumino consistency.

The statement does not say the anomaly is harmless. If this is a gauge anomaly of a dynamical gauge field, it must cancel. If it is an anomaly of a global symmetry probed by a background field, it is an allowed ’t Hooft anomaly.

## Example: why a random term fails

Suppose someone proposes a non-Abelian anomaly

$$
\mathcal A_\lambda=\int\operatorname{tr}(\lambda\,dA\wedge dA)
$$

with no accompanying $A^3$ or $A\,dA$ terms. This expression may resemble part of a real anomaly, but by itself it generally fails the Wess–Zumino condition. Under a non-Abelian transformation,

$$
\delta_\eta A=D\eta,
$$

and the variation of $dA$ produces terms involving commutators with $A$ and derivatives of $\eta$. The missing terms are precisely what are needed to combine into

$$
\mathcal A_{[\lambda,\eta]}.
$$

This is why the non-Abelian consistent anomaly has a very specific polynomial structure. It is not obtained by guessing the Abelian answer and inserting traces.

## Gauge anomalies versus ’t Hooft anomalies

The same consistency condition applies to anomalies of background gauge transformations. The interpretation changes.

If $A$ is a background for a global symmetry, then

$$
\delta_\lambda W[A]=\mathcal A_\lambda[A]
$$

is a ’t Hooft anomaly. The theory can be perfectly healthy; the anomaly means the global symmetry cannot be gauged by itself.

If $A$ is a dynamical gauge field for a redundancy, then the same anomalous variation means the path integral is not consistently defined on gauge-equivalence classes. Unless canceled by other fields or inflow, this is an inconsistency.

Wess–Zumino consistency is required in both cases. It is not sufficient for physical consistency in the dynamical gauge case.

## Relation to Chern–Simons inflow

The companion page on Chern–Simons level quantization explains that a Chern–Simons action in odd dimension shifts by boundary terms under gauge transformations. In descent notation,

$$
I_{2n+2}=dI_{2n+1}^{(0)},
\qquad
sI_{2n+1}^{(0)}+dI_{2n}^{(1)}=0.
$$

On a manifold with boundary,

$$
s\int_{M_{2n+1}}I_{2n+1}^{(0)}
=-\int_{\partial M_{2n+1}}I_{2n}^{(1)}.
$$

The boundary term is a consistent anomaly. The nilpotency of $s$ and the descent equations guarantee Wess–Zumino consistency. This is why anomaly inflow automatically produces consistent anomalies.

## Common pitfalls

**Confusing consistent and covariant anomalies.** The Wess–Zumino condition applies to consistent anomalies. Covariant anomalies transform nicely but are not always variations of a single effective action.

**Thinking Wess–Zumino consistency means the gauge theory is consistent.** A gauge anomaly can satisfy the Wess–Zumino condition and still be fatal unless it cancels.

**Ignoring counterterms.** Local counterterms shift the representative of the anomaly. The meaningful classification is modulo such shifts.

**Guessing non-Abelian anomalies from Abelian ones.** Non-Abelian consistency fixes extra $A$-dependent terms.

**Forgetting background versus dynamical interpretation.** The same formula may be an allowed ’t Hooft anomaly for a global symmetry or an inconsistency for a gauge redundancy.

## Relations to other pages

This page sits between the ABJ anomaly, Fujikawa Jacobian, Standard Model anomaly cancellation, Chern–Simons level quantization, anomaly polynomial, and descent-equation pages. It explains the algebraic test every anomaly formula must pass.

Later pages on Wess–Zumino terms, Wess–Zumino–Witten terms, anomaly inflow, SymTFT, finite-symmetry anomalies, and non-invertible Ward identities reuse the same idea: anomalous transformation laws are constrained by the consistency of composing transformations.

## Research status

The Wess–Zumino consistency condition is established. Active uses include supersymmetric anomaly multiplets, hydrodynamic anomaly constraints, higher-group symmetries, generalized symmetries, non-invertible symmetry defects, and SymTFT boundary formulations.

## Exercises

### Exercise 1: Derive the condition

Assume

$$
\delta_\lambda W=\mathcal A_\lambda,
\qquad
[\delta_\lambda,\delta_\eta]=\delta_{[\lambda,\eta]}.
$$

Derive the Wess–Zumino consistency condition.

<details><summary><strong>Solution</strong></summary>

Act with the commutator on $W$:

$$
[\delta_\lambda,\delta_\eta]W
=\delta_\lambda\mathcal A_\eta-\delta_\eta\mathcal A_\lambda.
$$

But the transformation algebra gives

$$
[\delta_\lambda,\delta_\eta]W=\delta_{[\lambda,\eta]}W=\mathcal A_{[\lambda,\eta]}.
$$

Equating the two expressions gives

$$
\delta_\lambda\mathcal A_\eta-\delta_\eta\mathcal A_\lambda=\mathcal A_{[\lambda,\eta]}.
$$

</details>

### Exercise 2: Abelian check

Check that

$$
\mathcal A_\alpha=C\int \alpha F\wedge F
$$

satisfies Wess–Zumino consistency for an Abelian symmetry.

<details><summary><strong>Solution</strong></summary>

For an Abelian symmetry, $[\alpha,\beta]=0$ and $\delta_\beta F=0$. Thus

$$
\delta_\beta\mathcal A_\alpha=0,
\qquad
\delta_\alpha\mathcal A_\beta=0.
$$

Therefore

$$
\delta_\alpha\mathcal A_\beta-\delta_\beta\mathcal A_\alpha=0=\mathcal A_{[\alpha,\beta]}.
$$

</details>

### Exercise 3: Counterterm shift

Show that if $\mathcal A_\lambda$ satisfies Wess–Zumino consistency, then

$$
\mathcal A'_\lambda=\mathcal A_\lambda+\delta_\lambda C
$$

also satisfies it.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\delta_\lambda\mathcal A'_\eta-\delta_\eta\mathcal A'_\lambda
=
\delta_\lambda\mathcal A_\eta-\delta_\eta\mathcal A_\lambda
+
\delta_\lambda\delta_\eta C-
\delta_\eta\delta_\lambda C.
$$

The first two terms give $\mathcal A_{[\lambda,\eta]}$. The last two give

$$
[\delta_\lambda,\delta_\eta]C=\delta_{[\lambda,\eta]}C.
$$

Thus

$$
\delta_\lambda\mathcal A'_\eta-\delta_\eta\mathcal A'_\lambda
=
\mathcal A_{[\lambda,\eta]}+\delta_{[\lambda,\eta]}C
=
\mathcal A'_{[\lambda,\eta]}.
$$

</details>

### Exercise 4: BRST version

Explain why $s^2=0$ turns the Wess–Zumino consistency condition into $s\mathcal A=0$.

<details><summary><strong>Solution</strong></summary>

In BRST notation, the gauge parameter is replaced by a ghost field $c$, and the anomaly is a ghost-number-one functional $\mathcal A$. The anomalous variation of the effective action is

$$
sW=\mathcal A.
$$

Applying $s$ again gives

$$
0=s^2W=s\mathcal A,
$$

because $s^2=0$. Therefore $s\mathcal A=0$. Counterterm shifts are $\mathcal A\mapsto\mathcal A+sC$, so the anomaly is a BRST cohomology class.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§75–77 for chiral gauge theories, global anomalies, and the path-integral treatment of fermion anomalies.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 30 for triangle anomalies, measure anomalies, Standard Model anomaly cancellation, and anomaly matching.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, anomaly and current-algebra chapters.
- J. Wess and B. Zumino, “Consequences of anomalous Ward identities,” *Physics Letters B* **37** (1971).
- W. A. Bardeen and B. Zumino, “Consistent and Covariant Anomalies in Gauge and Gravitational Theories,” *Nuclear Physics B* **244** (1984).
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* **234** (1984).

## Version history

- 2026-06-23: Initial polished model-library page. Added derivation from the gauge algebra, BRST form, descent relation, counterterm shifts, consistent/covariant distinction, examples, and exercises.
