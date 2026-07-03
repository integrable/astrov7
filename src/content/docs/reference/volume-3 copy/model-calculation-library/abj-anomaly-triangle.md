---
title: "ABJ Anomaly Triangle"
description: "Model calculation of the Adler–Bell–Jackiw axial anomaly from the vector-vector-axial triangle diagram."
sidebar:
  label: "ABJ Anomaly Triangle"
  order: 5
level: Advanced
status: "Polished draft"
source: "Srednicki §§75–76; Schwartz §30.2; Coleman, Aspects of Symmetry, Soft Pions; Bertlmann, Anomalies in Quantum Field Theory."
topics:
  - ABJ anomaly
  - chiral anomaly
  - triangle diagram
  - axial current
  - Ward identity
  - regularization
canonicalTopics:
  - abj-anomaly
  - axial-anomaly
  - triangle-anomaly
  - anomalous-ward-identity
researchStatus:
  established:
    - "The Adler–Bell–Jackiw anomaly is a standard one-loop exact result: the axial current of a massless charged Dirac fermion is not conserved in a background electromagnetic field."
    - "The triangle diagram teaches the central anomaly lesson: not all classical Ward identities can be preserved by one regulator."
  active:
    - "Modern treatments repackage the same anomaly as an obstruction to gauging, an inflow term, a relative/invertible field theory, or a constraint on generalized symmetry."
---

## Summary

This page computes the Adler–Bell–Jackiw anomaly from the triangle diagram with one axial current and two vector currents. For one Dirac fermion of $U(1)$ charge $q$, the classical vector and axial currents are

$$
j^\mu=q\,\overline\psi\gamma^\mu\psi,
\qquad
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

When $m=0$, the classical equations of motion give

$$
\partial_\mu j^\mu=0,
\qquad
\partial_\mu j_5^\mu=0.
$$

Quantum mechanically, preserving the vector Ward identity forces the axial current to have an anomaly:

$$
\partial_\mu j_5^\mu
=
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

in the conventions of this volume, with

$$
\widetilde F^{\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma},
\qquad
\epsilon^{0123}=+1.
$$

For a massive Dirac fermion, the mass term adds the classical breaking,

$$
\partial_\mu j_5^\mu
=
2im\,\overline\psi\gamma^5\psi
+
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

<figure class="doc-figure" style="--figure-width: 45rem;">

![Triangle diagram with one axial-current insertion and two vector-current insertions. The vector Ward identities are preserved, while the axial Ward identity acquires the anomaly.](/figures/symmetry-anomalies-topology/abj-triangle-ward-identities.svg)

<figcaption>

The triangle diagram cannot satisfy all three naive Ward identities at once. Gauge consistency requires the two vector currents to remain conserved; the price is the anomalous divergence of the axial current.

</figcaption>
</figure>

The computation is not about a mysterious failure of algebra. It is about regularization. The loop integral is linearly divergent before regulation, so shifting the loop momentum is not innocent. Different momentum routings distribute the anomalous surface term among the three currents. A gauge-invariant regulator chooses to preserve the vector Ward identities, leaving the axial anomaly.

## Prerequisites

You should know the [Noether Current for a Dirac Field](/symmetry-anomalies-topology/model-calculation-library/noether-current-for-dirac-field/) and the [Ward Identity in QED](/symmetry-anomalies-topology/model-calculation-library/ward-identity-in-qed/). You should also know the gamma-matrix convention

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
$$

and the shorthand

$$
p\!\!\!/\equiv \gamma^\mu p_\mu.
$$

The calculation uses the one-loop fermion triangle. The important physics can be understood without doing every Feynman-parameter integral, but the sign and normalization require fixing conventions.

## Setup and conventions

Consider a Dirac fermion coupled to a nondynamical Abelian background field,

$$
\mathcal L
=
\overline\psi(i\gamma^\mu D_\mu-m)\psi,
\qquad
D_\mu=\partial_\mu+iqA_\mu.
$$

The background field couples as

$$
\mathcal L
=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi
-
A_\mu j^\mu,
\qquad
j^\mu=q\,\overline\psi\gamma^\mu\psi.
$$

The axial current is

$$
j_5^\lambda=\overline\psi\gamma^\lambda\gamma^5\psi.
$$

The object of interest is the three-current correlator

$$
T^{\lambda\mu\nu}(p;k_1,k_2)
=
\int d^4x\,d^4y\,d^4z\,
e^{-ip\cdot x+ik_1\cdot y+ik_2\cdot z}
\left\langle T\,j_5^\lambda(x)j^\mu(y)j^\nu(z)\right\rangle,
$$

with

$$
p=k_1+k_2.
$$

The one-loop amplitude is represented by the triangle diagram. Up to an overall convention for factors of $i$, one routing gives

$$
T^{\lambda\mu\nu}
=
-q^2\int\frac{d^4\ell}{(2\pi)^4}
\operatorname{tr}
\left[
\gamma^\lambda\gamma^5
S_F(\ell)
\gamma^\mu
S_F(\ell-k_1)
\gamma^\nu
S_F(\ell+k_2)
\right]
+
(\mu,k_1\leftrightarrow \nu,k_2),
$$

where

$$
S_F(r)=\frac{i(r\!\!\!/+m)}{r^2-m^2+i\epsilon}.
$$

The exact routing is not sacred. In fact, the routing ambiguity is the point.

:::note[Source note: routing ambiguity]
The unregulated triangle integral is superficially linearly divergent. Shifting $\ell$ in a linearly divergent integral can produce a finite surface term. A regulator is not just a convergence trick; it decides which Ward identities are imposed.
:::

## What the three Ward identities would say

Classically, for $m=0$, one might expect

$$
k_{1\mu}T^{\lambda\mu\nu}=0,
\qquad
k_{2\nu}T^{\lambda\mu\nu}=0,
\qquad
p_\lambda T^{\lambda\mu\nu}=0.
$$

The first two equations are vector-current Ward identities. If the vector current is coupled to a gauge field, these are required for gauge invariance. The third is the axial Ward identity.

The quantum theorem of the triangle diagram is:

$$
\text{vector Ward identities}
+
\text{locality}
+
\text{a regulator}
\quad
\Longrightarrow
\quad
\text{axial anomaly}.
$$

One can choose a regulator that hides the anomaly elsewhere, but not a regulator that preserves all three Ward identities while keeping locality and gauge invariance.

For QED, the vector current is the gauge current. A vector-current anomaly would make the gauge redundancy inconsistent. Therefore the consistent regularization condition is

$$
k_{1\mu}T^{\lambda\mu\nu}=0,
\qquad
k_{2\nu}T^{\lambda\mu\nu}=0.
$$

Then the axial divergence is nonzero.

## The regulated answer

With the vector Ward identities imposed, the massless triangle divergence has the form

$$
p_\lambda T^{\lambda\mu\nu}
\propto
q^2\,\epsilon^{\mu\nu\rho\sigma}k_{1\rho}k_{2\sigma}.
$$

Rather than treat this momentum-space proportionality constant as convention-independent, we fix the normalization by the local background-field equation. In the conventions of this volume, the result is

$$
\partial_\lambda j_5^\lambda
=
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

Standalone momentum-space formulas for the triangle amplitude differ across books because authors make different choices about current normalization, whether the vector vertices include $q$, whether both photon permutations have already been included, how $\widetilde F^{\mu\nu}$ is defined, and whether the displayed equation is a matrix element or a local operator equation.

:::caution[Coefficient hygiene]
Before comparing anomaly coefficients, check four things: the definition of $\gamma^5$, the sign of $\epsilon^{0123}$, whether $D_\mu=\partial_\mu+iqA_\mu$ or $\partial_\mu-iqA_\mu$, and whether the author writes the anomaly as $F_{\mu\nu}\widetilde F^{\mu\nu}$ or as $\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}$.
:::

## A quick derivation of the surface term

The triangle calculation can be summarized without drowning in Feynman parameters.

Contracting the axial vertex with $p_\lambda$ gives

$$
p_\lambda\gamma^\lambda\gamma^5
=
(k_1+k_2)_\lambda\gamma^\lambda\gamma^5.
$$

Inside the loop, this can be rewritten in terms of inverse fermion propagators. Naively, inverse propagators cancel adjacent propagators and the result looks like the difference of two linearly divergent integrals. If those integrals could be shifted freely, they would cancel.

But the regulated difference is a surface term at large loop momentum. Schematically,

$$
\int d^4\ell\, f(\ell+a)-\int d^4\ell\, f(\ell)
\sim
a_\mu\int_{S^3_\infty}dS^\mu\, f(\ell).
$$

The trace with $\gamma^5$ extracts the antisymmetric part,

$$
\operatorname{tr}
(\gamma^5\gamma^\mu\gamma^\nu\gamma^\rho\gamma^\sigma)
=
-4i\epsilon^{\mu\nu\rho\sigma}
$$

with the mostly-minus convention used here. That antisymmetric surface term is the anomaly.

This is the triangle-diagram version of a broader lesson: anomalous Ward identities are ultraviolet effects. They are finite and infrared-visible, but they are fixed by how the theory is regulated at short distances.

## Pauli–Villars viewpoint

A clean way to see the anomaly is Pauli–Villars regularization. Introduce a heavy regulator fermion with mass $M$ and coefficients chosen to cancel the ultraviolet divergence. The vector current can be preserved by coupling the regulator gauge-invariantly. The regulator mass, however, breaks axial symmetry.

For an ordinary fermion, the classical axial divergence is

$$
\partial_\mu j_5^\mu=2im\,\overline\psi\gamma^5\psi.
$$

For the regulator field, the corresponding term is proportional to $M$. Even as $M\to\infty$, the expectation value

$$
2iM\,\langle\overline\chi\gamma^5\chi\rangle
$$

does not vanish. The loop suppression and the large mass combine to leave a finite remainder,

$$
\lim_{M\to\infty}2iM\,\langle\overline\chi\gamma^5\chi\rangle
=
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

This is a particularly physical way to understand the result: the regulator required to define the vector gauge theory cannot also respect the axial symmetry.

## Massive fermions

For $m\neq0$, the axial symmetry is already explicitly broken. The exact operator equation becomes

$$
\partial_\mu j_5^\mu
=
2im\,\overline\psi\gamma^5\psi
+
\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}.
$$

The anomaly term does not disappear in the massless limit. It is not caused by the explicit mass. It is caused by the incompatibility between axial symmetry and gauge-invariant regularization.

This distinction matters in pion physics. The axial current is approximately conserved when quark masses are small, but the anomalous singlet axial current is not protected in the same way. It also matters in the strong CP problem, axion physics, and the meaning of anomalous chiral rotations.

## Gauge anomaly versus global anomaly of the axial current

In the Dirac-QED example, the vector current is the gauge current and is conserved; the axial current is global and anomalous. This is consistent.

A gauge anomaly would be different. If the anomalous current were the current coupled to a dynamical gauge field, the gauge redundancy would fail quantum mechanically. Then the theory would not have a consistent physical Hilbert space unless the anomaly cancels or is repaired by inflow from a higher-dimensional system.

Thus the triangle diagram has two morals:

1. A global current can be anomalous without making the theory inconsistent.
2. A gauge current must have no uncancelled anomaly.

The Standard Model anomaly-cancellation page later turns this into a concrete representation-theory calculation.

## One-loop exactness

The ABJ anomaly coefficient is one-loop exact in ordinary perturbative QFT. This statement is often called the Adler–Bardeen theorem. Its practical meaning is that higher-loop corrections do not renormalize the coefficient of

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
$$

in the axial anomaly equation, once the current normalization and gauge coupling conventions are fixed.

There are many ways to understand this: regulator arguments, Wess–Zumino consistency, topological quantization, and supersymmetric arguments in special theories. For this model calculation, the important point is modest: the triangle diagram is not just the first term in a vague expansion. It gives the anomaly coefficient.

## Common mistakes

**Shifting a divergent integral as if it were convergent.** The anomaly is exactly the finite remainder of such a forbidden shift.

**Trying to preserve all three triangle Ward identities.** The regulator cannot preserve both vector gauge invariance and axial current conservation in the massless charged theory.

**Calling the axial anomaly explicit breaking.** The mass term is explicit breaking. The anomaly is quantum breaking by regularization.

**Forgetting which current is gauged.** A global-current anomaly is allowed. A gauge-current anomaly is an inconsistency unless cancelled or inflowed.

**Comparing coefficients without translating conventions.** Factors of $2$, $q$, $i$, and signs depend on $\widetilde F$, $\epsilon^{0123}$, vertex normalization, and Lorentzian versus Euclidean conventions.

## Relations to other pages

The [Fujikawa Chiral Jacobian](/symmetry-anomalies-topology/model-calculation-library/fujikawa-chiral-jacobian/) page derives the same anomaly from the path-integral measure. The two derivations are complementary: the triangle diagram shows the conflict among Ward identities in perturbation theory, while Fujikawa’s method shows the non-invariance of the fermion measure.

The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter explains how this model calculation generalizes to perturbative gauge anomalies, consistent versus covariant anomalies, and descent equations. The [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) chapter explains why global anomalies constrain RG flow. The [Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) page explains how the same local variation can be cancelled by a bulk term.

## Research status

The ABJ anomaly and its triangle-diagram derivation are settled textbook material. What remains active is not the coefficient in QED, but the organization of anomalies in modern language: invertible field theories, anomaly inflow, generalized symmetries, symmetry TFT, non-invertible symmetry, and anomalies of non-Lagrangian systems.

## Exercises

### Exercise 1: Classical axial divergence

Starting from

$$
\mathcal L=\overline\psi(i\gamma^\mu D_\mu-m)\psi,
$$

show that the classical axial current obeys

$$
\partial_\mu j_5^\mu=2im\,\overline\psi\gamma^5\psi
$$

before the anomaly is included.

<details><summary><strong>Solution</strong></summary>

Use

$$
j_5^\mu=\overline\psi\gamma^\mu\gamma^5\psi.
$$

Then

$$
\partial_\mu j_5^\mu
=
(D_\mu\overline\psi)\gamma^\mu\gamma^5\psi
+
\overline\psi\gamma^\mu\gamma^5D_\mu\psi,
$$

where the gauge connection cancels because the current is neutral. The equations of motion are

$$
i\gamma^\mu D_\mu\psi=m\psi,
\qquad
i(D_\mu\overline\psi)\gamma^\mu=-m\overline\psi.
$$

Using $\{\gamma^5,\gamma^\mu\}=0$, one obtains

$$
\partial_\mu j_5^\mu=2im\,\overline\psi\gamma^5\psi.
$$

For $m=0$, the classical divergence vanishes.

</details>

### Exercise 2: Why the vector Ward identities are protected

In QED, why do we choose the regulator so that the vector Ward identities are preserved rather than the axial Ward identity?

<details><summary><strong>Solution</strong></summary>

The vector current is coupled to the gauge field. If the vector Ward identity failed, the gauge redundancy of QED would fail quantum mechanically, and the theory would not consistently remove unphysical photon polarizations. The axial current is a global current in this example. Its anomaly is physically meaningful but does not make QED inconsistent. Therefore a consistent QED regulator preserves vector gauge invariance and places the anomaly in the axial divergence.

</details>

### Exercise 3: Total derivative form

Show that in Abelian gauge theory

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
=
2\partial_\mu\left(\epsilon^{\mu\nu\rho\sigma}A_\nu\partial_\rho A_\sigma\right)
$$

up to the conventions for $\widetilde F$ and $\epsilon$.

<details><summary><strong>Solution</strong></summary>

Using

$$
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma},
$$

we have

$$
F_{\mu\nu}\widetilde F^{\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}.
$$

For Abelian $F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu$, antisymmetry gives

$$
\epsilon^{\mu\nu\rho\sigma}F_{\mu\nu}F_{\rho\sigma}
=
4\epsilon^{\mu\nu\rho\sigma}
(\partial_\mu A_\nu)(\partial_\rho A_\sigma).
$$

Meanwhile,

$$
\partial_\mu(\epsilon^{\mu\nu\rho\sigma}A_\nu\partial_\rho A_\sigma)
=
\epsilon^{\mu\nu\rho\sigma}
(\partial_\mu A_\nu)(\partial_\rho A_\sigma),
$$

because the second-derivative term is symmetric in derivatives and killed by $\epsilon^{\mu\nu\rho\sigma}$. Combining these equations gives the displayed identity.

</details>

### Exercise 4: Global versus gauge anomaly

A theory has one anomalous global axial symmetry and one conserved vector gauge symmetry. Is the theory inconsistent?

<details><summary><strong>Solution</strong></summary>

No. An anomaly in a global symmetry is allowed and can be physically important. The theory would be inconsistent if the anomalous symmetry were a gauge redundancy. In QED with a Dirac fermion, the vector gauge current is conserved and the axial global current is anomalous, so the theory is consistent.

</details>

## References

- S. L. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* **177** (1969).
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the $\sigma$-Model,” *Il Nuovo Cimento A* **60** (1969).
- M. Srednicki, *Quantum Field Theory*, §§75–76.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §30.2.
- S. Coleman, *Aspects of Symmetry*, especially “Soft Pions.”
- R. A. Bertlmann, *Anomalies in Quantum Field Theory*.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” for anomaly-polynomial and descent perspectives beyond the Abelian triangle.

## Version history

- 2026-06-23: Polished model-calculation draft. Fixed the convention-sensitive axial-anomaly normalization and emphasized the routing/regulator origin of the triangle result.
