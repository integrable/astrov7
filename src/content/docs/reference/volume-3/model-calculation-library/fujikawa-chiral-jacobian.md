---
title: "Fujikawa Chiral Jacobian"
description: "Model calculation deriving the axial anomaly from the transformation of the regulated fermion path-integral measure."
sidebar:
  label: "Fujikawa Chiral Jacobian"
  order: 6
level: Advanced
status: "Polished draft"
source: "Srednicki §77; Schwartz §30.3; Fujikawa and Suzuki; Alvarez-Gaumé and Witten."
topics:
  - Fujikawa method
  - chiral anomaly
  - fermion measure
  - heat kernel
  - path integral
  - index density
canonicalTopics:
  - fujikawa-method
  - chiral-jacobian
  - fermion-measure-anomaly
  - heat-kernel-anomaly
researchStatus:
  established:
    - "Fujikawa’s method is a standard path-integral derivation of the chiral anomaly: the classical chiral rotation is a symmetry of the action in the massless theory but not of the regulated fermion measure."
    - "The heat-kernel regulator connects the anomaly density to the local index density."
  active:
    - "Modern anomaly theory reformulates the same calculation using determinant lines, eta invariants, invertible field theories, and anomaly inflow."
---

## Summary

This page derives the axial anomaly from the path-integral measure. For a Dirac fermion of $U(1)$ charge $q$,

$$
\mathcal L=\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu,
$$

the classical massless action is invariant under the chiral rotation

$$
\psi\mapsto e^{i\alpha\gamma^5}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{i\alpha\gamma^5}.
$$

Fujikawa’s observation is that the fermion measure is not invariant once it is defined with a gauge-invariant ultraviolet regulator. The formal Jacobian is infinite and ambiguous until regulated; the gauge-invariant heat-kernel regulator gives

$$
\mathcal D\psi\,\mathcal D\overline\psi
\mapsto
\mathcal D\psi\,\mathcal D\overline\psi\,
\exp\left[
i\int d^4x\,\alpha(x)
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
\right]
$$

in the Lorentzian conventions of this volume. Therefore the anomalous Ward identity is

$$
\partial_\mu j_5^\mu
=
2im\,\overline\psi\gamma^5\psi
+
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

<figure class="doc-figure" style="--figure-width: 48rem;">

![Flowchart of Fujikawa's method: expand fermions in Dirac eigenmodes, rotate coefficients, regulate the trace with a heat kernel, and obtain the anomaly density.](/figures/symmetry-anomalies-topology/fujikawa-jacobian-flow.svg)

<figcaption>

Fujikawa’s method turns the anomaly into a regulated trace over fermion modes. The chiral rotation is harmless for the classical massless action, but the measure Jacobian is the heat-kernel trace of $\gamma^5$.

</figcaption>
</figure>

The triangle-diagram derivation and the Fujikawa derivation give the same anomaly. The triangle diagram emphasizes the impossibility of preserving all naive Ward identities in perturbation theory. Fujikawa’s method emphasizes that the path-integral measure itself must be regulated, and the regulator cannot preserve both gauge invariance and axial symmetry.

## Prerequisites

You should know the [ABJ Anomaly Triangle](/symmetry-anomalies-topology/model-calculation-library/abj-anomaly-triangle/) page, the [Noether Current for a Dirac Field](/symmetry-anomalies-topology/model-calculation-library/noether-current-for-dirac-field/), and the basic fermionic path integral.

You should also know the convention

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\epsilon^{0123}=+1,
\qquad
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma}.
$$

The cleanest derivation uses Euclidean signature, because the Dirac operator has a discrete orthonormal basis on a compact Euclidean spacetime. The final formula is then translated back to Lorentzian signature.

:::note[Euclidean warning]
Fujikawa’s method is often written in Euclidean signature. This page displays the final anomaly in the Lorentzian conventions of the volume. Intermediate Euclidean signs depend on the Euclidean gamma-matrix and Wick-rotation conventions.
:::

## Setup in Euclidean signature

Let $\not D_E$ be the Euclidean Dirac operator coupled to a background gauge field. Expand the fermion fields in a complete orthonormal basis of eigenfunctions,

$$
\not D_E\varphi_n=\lambda_n\varphi_n,
\qquad
\int d^4x\,\varphi_m^\dagger(x)\varphi_n(x)=\delta_{mn}.
$$

Write

$$
\psi(x)=\sum_n a_n\varphi_n(x),
\qquad
\overline\psi(x)=\sum_n \overline b_n\varphi_n^\dagger(x),
$$

where $a_n$ and $\overline b_n$ are Grassmann coefficients. The formal measure is

$$
\mathcal D\psi\,\mathcal D\overline\psi
=
\prod_n da_n\,d\overline b_n.
$$

This expression is not yet meaningful by itself. The infinite product depends on how the basis and ultraviolet cutoff are defined. Fujikawa’s method keeps this dependence visible.

## Chiral rotation of the coefficients

For an infinitesimal local chiral rotation,

$$
\psi'(x)=\psi(x)+i\alpha(x)\gamma^5\psi(x),
$$

the coefficients transform as

$$
a'_m
=
\sum_n
\left[
\delta_{mn}
+
i\int d^4x\,\alpha(x)\varphi_m^\dagger(x)\gamma^5\varphi_n(x)
\right]a_n.
$$

Define the matrix

$$
C_{mn}
=
\int d^4x\,\alpha(x)\varphi_m^\dagger(x)\gamma^5\varphi_n(x).
$$

For Grassmann variables, the measure transforms with the inverse determinant:

$$
\prod_n da'_n
=
\det(1+iC)^{-1}\prod_n da_n.
$$

The barred variables give another identical factor, so formally

$$
\mathcal D\psi'\,\mathcal D\overline\psi'
=
\exp\left[-2i\,\operatorname{Tr}C\right]
\mathcal D\psi\,\mathcal D\overline\psi.
$$

The formal trace is

$$
\operatorname{Tr}C
=
\int d^4x\,\alpha(x)
\sum_n\varphi_n^\dagger(x)\gamma^5\varphi_n(x).
$$

If we naively pair nonzero Dirac eigenmodes, we may be tempted to declare this trace zero. That is the trap. The sum is ultraviolet divergent and must be regulated before it can be manipulated.

## Gauge-invariant heat-kernel regulator

To preserve vector gauge invariance, regulate the trace using the gauge-covariant Dirac operator:

$$
\sum_n\varphi_n^\dagger(x)\gamma^5\varphi_n(x)
\quad\longrightarrow\quad
\lim_{M\to\infty}
\sum_n
\varphi_n^\dagger(x)\gamma^5
e^{-\lambda_n^2/M^2}
\varphi_n(x).
$$

In operator notation,

$$
\mathcal A_E(x)
=
2\lim_{M\to\infty}
\operatorname{tr}
\left[
\gamma^5
e^{-\not D_E^{\,2}/M^2}
\right]_{x,x}.
$$

The factor of $2$ comes from the $\psi$ and $\overline\psi$ measures. The trace `tr` is now over spinor and internal indices, while the heat kernel controls the infinite mode sum.

The regulator is gauge invariant because $\not D_E^{\,2}$ is gauge covariant. It is not chiral invariant, because it uses the spectrum of the Dirac operator in the background gauge field to define the measure.

:::note[Source note: what the regulator chooses]
Fujikawa’s regulator is not arbitrary decoration. Choosing $e^{-\not D_E^{\,2}/M^2}$ means the fermion measure is defined in a way compatible with vector gauge invariance. The anomaly is the resulting failure of the axial rotation to have unit Jacobian.
:::

## Heat-kernel evaluation

The key identity is the square of the Dirac operator. In flat space,

$$
\not D_E^{\,2}
=
D_E^2+\frac{iq}{4}[\gamma_E^\mu,\gamma_E^\nu]F_{\mu\nu}
$$

up to Euclidean sign conventions. When expanding

$$
e^{-\not D_E^{\,2}/M^2}
$$

at large $M$, only the term quadratic in the field strength survives inside the trace with $\gamma^5$ in four dimensions. Lower terms vanish because

$$
\operatorname{tr}\gamma^5=0,
\qquad
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu)=0.
$$

The nonzero spinor trace is proportional to

$$
\operatorname{tr}
(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
\propto
\epsilon^{\mu\nu\rho\sigma}.
$$

The Gaussian momentum integral supplies

$$
\int\frac{d^4k}{(2\pi)^4}e^{-k^2/M^2}
=
\frac{M^4}{16\pi^2}.
$$

The powers of $M$ cancel the $1/M^4$ from the second-order field-strength expansion. The regulated trace has a finite limit,

$$
\mathcal A(x)
=
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu},
$$

after translating to the Lorentzian convention used in this volume.

## From Jacobian to Ward identity

Perform the chiral change of variables in the path integral with local parameter $\alpha(x)$. The path integral cannot change under a change of variables. The variation has two contributions:

1. the classical variation of the action;
2. the Jacobian of the measure.

The action variation is

$$
\delta S
=
-\int d^4x\,\alpha(x)
\left[
\partial_\mu j_5^\mu
-
2im\,\overline\psi\gamma^5\psi
\right],
$$

up to the sign convention used for Lorentzian $e^{iS}$. The measure contributes

$$
\delta\log J
=
i\int d^4x\,\alpha(x)
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Since $\alpha(x)$ is arbitrary, the Ward identity is

$$
\partial_\mu j_5^\mu
=
2im\,\overline\psi\gamma^5\psi
+
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

That is exactly the ABJ anomaly.

## Relation to the index theorem

On a compact Euclidean four-manifold, the integrated regulated trace is the index of the Dirac operator. In the Abelian normalization compatible with the local formula above,

$$
\operatorname{ind}\not D
=
n_+-n_-
=
\frac{q^2}{8\pi^2}\int F\wedge F
=
\frac{q^2}{16\pi^2}\int d^4x\,
F_{\mu\nu}\widetilde F^{\mu\nu},
$$

up to the usual flux-quantization, representation, and trace-normalization conventions.

The anomaly density is therefore the local index density. This is one reason anomalies are robust. The coefficient is not an accident of a special diagram calculation; it is tied to topology, zero modes, and the index theorem.

For non-Abelian gauge fields and curved backgrounds, the same heat-kernel logic produces the appropriate characteristic classes: gauge terms involving $\operatorname{tr}(F\wedge F)$ and gravitational terms involving curvature two-forms. Later anomaly-polynomial pages develop this systematically.

## Why the naive cancellation fails

A common quick argument says that because

$$
\{\gamma^5,\not D_E\}=0
$$

in the massless theory, nonzero eigenvalues come in pairs $\lambda$ and $-\lambda$, and their contributions to

$$
\sum_n\varphi_n^\dagger\gamma^5\varphi_n
$$

cancel. This is incomplete.

First, zero modes do not pair. They contribute to the integrated index.

Second, even for the local anomaly density, the sum is not absolutely convergent. Pairing modes before regulating the trace is not legitimate. The regulator defines what the trace means, and the gauge-invariant definition leaves a finite local density.

The moral is the same as in the triangle diagram: formal manipulations of divergent expressions can hide finite quantum effects.

## Non-Abelian generalization

For fermions in a representation $R$ of a non-Abelian gauge group,

$$
D_\mu=\partial_\mu+iA_\mu^aT_a^{(R)}.
$$

The Abelian factor $q^2F\widetilde F$ is replaced by a representation trace,

$$
\partial_\mu j_5^\mu
\supset
\frac{1}{16\pi^2}
\operatorname{tr}_R(F_{\mu\nu}\widetilde F^{\mu\nu}),
$$

with the normalization of generators stated on the relevant page. If

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab},
$$

then the coefficient is proportional to $T(R)$.

Gauge anomalies of chiral fermions require a related but more delicate calculation with gauge transformations rather than axial transformations. The relevant group factor becomes the symmetric cubic trace

$$
\operatorname{tr}_R(T^a\{T^b,T^c\}),
$$

which is why anomaly cancellation becomes a representation-theory constraint.

## Comparing to the triangle calculation

The triangle calculation computes a three-point function and finds that the axial Ward identity cannot be maintained together with vector gauge invariance. Fujikawa’s method computes the measure Jacobian and finds that the chiral rotation changes the regulated fermion measure.

They agree because both are regulated versions of the same determinant. Perturbatively, the logarithm of the fermion determinant produces the triangle diagram. Nonperturbatively, the determinant line and its phase carry global information. Fujikawa’s method therefore sits naturally between diagrammatic anomaly calculations and modern geometric anomaly theory.

## Common mistakes

**Treating the fermion measure as automatically invariant.** Infinite-dimensional measures need a definition. The regulator is part of that definition.

**Regulating with a non-gauge-covariant operator.** That can move the anomaly into the vector current and destroy gauge invariance.

**Dropping zero modes.** The integrated anomaly is tied to the index and therefore to zero-mode counting.

**Pairing eigenvalues before regulating.** The trace is divergent. Pairing arguments must be made after a legitimate regulator is chosen.

**Forgetting Euclidean/Lorentzian translation.** Fujikawa’s heat-kernel derivation is cleanest in Euclidean signature, but many QFT anomaly equations are quoted in Lorentzian signature.

## Relations to other pages

The [ABJ Anomaly Triangle](/symmetry-anomalies-topology/model-calculation-library/abj-anomaly-triangle/) page derives the same anomaly from a one-loop diagram. The present page derives it from the measure. The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter explains the general regulator logic. The [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) pages explain how the heat-kernel/index-density result becomes the modern descent formalism. The [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) page explains how this boundary variation can be cancelled by a bulk term.

## Research status

Fujikawa’s derivation is established textbook material. Its modern descendants remain central: determinant line bundles, eta invariants, global anomalies, invertible field theories, and SymTFT all refine the same idea that quantum measures and partition functions can transform projectively rather than invariantly.

## Exercises

### Exercise 1: Grassmann Jacobian

Let $a'_m=M_m{}^n a_n$ for finitely many Grassmann variables. Show that

$$
\prod_m da'_m=(\det M)^{-1}\prod_m da_m.
$$

<details><summary><strong>Solution</strong></summary>

For one Grassmann variable $a'=Ma$, Berezin integration is defined by

$$
\int da\,a=1.
$$

Since $a=M^{-1}a'$, we need

$$
1=\int da\,a=\int da'\,J\,M^{-1}a',
$$

where $da=J\,da'$. This gives $J=M$, or equivalently $da'=M^{-1}da$. For many variables the result multiplies over eigenvalues, giving

$$
\prod_m da'_m=(\det M)^{-1}\prod_m da_m.
$$

</details>

### Exercise 2: Why two factors?

Why does the chiral Jacobian contain a factor of $2$ relative to the trace from the $\psi$ coefficients alone?

<details><summary><strong>Solution</strong></summary>

The Dirac path integral has independent Grassmann variables for $\psi$ and $\overline\psi$. Under the chiral rotation,

$$
\psi\mapsto e^{i\alpha\gamma^5}\psi,
\qquad
\overline\psi\mapsto \overline\psi e^{i\alpha\gamma^5},
$$

both sets of coefficients transform. Each contributes the same regulated trace to the logarithm of the Jacobian. Therefore the full measure has twice the single-field contribution.

</details>

### Exercise 3: Vanishing of lower heat-kernel terms

Explain why the terms with zero or two gamma matrices do not contribute to the regulated trace with $\gamma^5$ in four dimensions.

<details><summary><strong>Solution</strong></summary>

The relevant spinor traces are

$$
\operatorname{tr}\gamma^5=0,
\qquad
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu)=0.
$$

In four dimensions, a nonzero trace with $\gamma^5$ requires four gamma matrices:

$$
\operatorname{tr}(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
\propto
\epsilon^{\mu\nu\rho\sigma}.
$$

Thus the first nonzero heat-kernel contribution is the term quadratic in the field strength, which supplies four gamma matrices through two factors of $[\gamma^\mu,\gamma^\nu]F_{\mu\nu}$.

</details>

### Exercise 4: Why gauge-covariant regulation?

Why is the regulator $e^{-\not D_E^{\,2}/M^2}$ appropriate for the axial anomaly in QED?

<details><summary><strong>Solution</strong></summary>

The vector current is the gauge current in QED, so gauge invariance must be preserved for the theory to be consistent. The operator $\not D_E^{\,2}$ is built from the gauge-covariant derivative, so its heat kernel transforms covariantly under gauge transformations. The regulated trace therefore preserves vector gauge invariance. It does not preserve axial symmetry, and that failure is precisely the axial anomaly.

</details>

## References

- K. Fujikawa, “Path-Integral Measure for Gauge-Invariant Fermion Theories,” *Physical Review Letters* **42** (1979).
- K. Fujikawa and H. Suzuki, *Path Integrals and Quantum Anomalies*.
- M. Srednicki, *Quantum Field Theory*, §77.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.3.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies.”
- M. Nakahara, *Geometry, Topology and Physics*, for index-theorem and characteristic-class background.
- T. Frankel, *The Geometry of Physics*, for differential-form and characteristic-class conventions.

## Version history

- 2026-06-23: Polished model-calculation draft. Added mode expansion, Grassmann Jacobian, heat-kernel regulator, index-density interpretation, and Lorentzian convention translation.
