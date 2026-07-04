---
title: "Identical Scalar Bootstrap"
description: "How the four-point function of one real scalar primary becomes the basic conformal bootstrap problem."
sidebar:
  label: "Identical Scalar Bootstrap"
  order: 5
level: Graduate
status: "Polished draft"
source: "Rattazzi–Rychkov–Tonni–Vichi 2008; El-Showk et al. 2012; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - identical scalar bootstrap
  - crossing symmetry
  - scalar conformal blocks
  - gap bounds
  - OPE coefficient bounds
  - linear functionals
canonicalTopics:
  - identical-scalar-bootstrap
  - scalar-gap-bounds
  - positive-cone-bootstrap
  - bootstrap-kinks
researchStatus:
  established:
    - "The identical real scalar four-point bootstrap is the canonical first example of a unitary conformal bootstrap problem."
    - "For a real scalar primary, reflection positivity makes the non-identity OPE weights in the identical-scalar crossing equation nonnegative."
  active:
    - "Interpreting kinks, improving rigorous certificates, extracting spectra, and combining identical-scalar input with mixed-correlator and analytic information remain active parts of the bootstrap program."
---

## Summary

The identical scalar bootstrap studies the four-point function of one real scalar primary $\phi$ and asks which spectra and OPE coefficients can satisfy crossing symmetry and unitarity.

With the two-point normalization

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}},
$$

the four-point function is written as

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V),
$$

where

$$
U=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
V=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The $12\to34$ OPE gives

$$
\mathcal G(U,V)
=
1+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(U,V),
$$

and crossing gives the bootstrap equation

$$
F_{\mathbf 1}(U,V)+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0,
\qquad
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This page explains the assumptions behind this equation, how scalar gap bounds are obtained, what kinks mean and do not mean, and why this simple-looking problem is still the template for much of the modern bootstrap.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Scalar gap bound in the identical scalar bootstrap](/figures/cft-bootstrap/identical-scalar-gap-bound.svg)

<figcaption>

A typical identical-scalar bootstrap scan fixes $\Delta_\phi$ and asks how large the first scalar dimension in $\phi\times\phi$ can be. Excluding larger assumed gaps produces an upper-bound curve. Kinks often signal interesting CFTs, but a kink is evidence, not a theorem of existence.

</figcaption>
</figure>

## Prerequisites

You should know [Four-Point Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/four-point-bootstrap/), [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), and [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/).

This page is the first concrete bootstrap setup. It is not yet the full Ising bootstrap, the full $O(N)$ bootstrap, or a tutorial on numerical semidefinite programming. Those require mixed correlators, global-symmetry sectors, and computational pages later in the volume.

## Core idea

The identical scalar bootstrap asks a yes-or-no question:

> Can a unitary CFT contain a real scalar primary $\phi$ of dimension $\Delta_\phi$ whose $\phi\times\phi$ OPE obeys a proposed set of assumptions?

The assumptions usually include unitarity and Bose symmetry, and may also include gaps such as

$$
\Delta_{\text{first scalar in }\phi\times\phi}\ge \Delta_*.
$$

The bootstrap then searches for a contradiction. If the assumptions imply

$$
-F_{\mathbf 1}
\notin
\operatorname{Cone}\{F_{\Delta,\ell}\text{ allowed}\},
$$

then no such CFT can exist. Equivalently, one tries to find a linear functional $\alpha$ satisfying

$$
\alpha(F_{\mathbf 1})>0,
\qquad
\alpha(F_{\Delta,\ell})\ge0
\quad
\text{for all allowed non-identity operators}.
$$

Applying $\alpha$ to crossing gives a contradiction because every term is nonnegative and at least one is strictly positive.

That is the whole trick. The power comes from making the word “all” computationally meaningful.

## Setup and conventions

We work in Euclidean signature and use the scalar four-point conventions of the preceding pages. The cross-ratios are

$$
U=z\bar z,
\qquad
V=(1-z)(1-\bar z).
$$

For a real scalar primary $\phi$, the OPE has the schematic form

$$
\phi\times\phi
=
\mathbf 1+
\sum_{\mathcal O\in\phi\times\phi} \lambda_{\phi\phi\mathcal O}\,\mathcal O.
$$

The exchanged operators are primaries, and their descendants are included inside the conformal blocks. With the standard scalar block normalization, the leading OPE behavior is

$$
G_{\Delta,\ell}(U,V)
\sim
U^{\Delta/2}
C_\ell(\cos\theta)
$$

in the $12\to34$ OPE limit, up to a convention-dependent normalization of the angular polynomial. The exact choice is not important as long as it is used consistently with the OPE coefficient normalization.

The crossing equation follows from the equality of the $12\to34$ and $14\to23$ OPE decompositions:

$$
V^{\Delta_\phi}\mathcal G(U,V)=U^{\Delta_\phi}\mathcal G(V,U).
$$

Define

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,\ell}(V,U).
$$

The identity contribution is

$$
F_{\mathbf 1}(U,V)=V^{\Delta_\phi}-U^{\Delta_\phi}.
$$

Thus

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0.
$$

For a unitary theory and a real operator basis, the coefficients $\lambda_{\phi\phi\mathcal O}^2$ are nonnegative.

## Spin selection for identical scalars

Because the two external operators are identical bosonic scalars, the OPE $\phi(x_1)\phi(x_2)$ is symmetric under exchanging $x_1$ and $x_2$. A spin-$\ell$ primary contributes with angular dependence that changes by $(-1)^\ell$ under the exchange direction $x_{12}\to -x_{12}$. Therefore

$$
\lambda_{\phi\phi\mathcal O}=0
\qquad
\text{for odd }\ell
$$

in the OPE of a single real scalar with itself.

So the minimal identical scalar bootstrap equation sums over even spins:

$$
F_{\mathbf 1}
+
\sum_{\substack{\mathcal O\ne\mathbf 1\\ \ell=0,2,4,\ldots}}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}=0.
$$

This even-spin rule is a frequent source of mistakes. It is not a universal rule for all scalar correlators. If the scalars carry global-symmetry indices, odd spins can appear in antisymmetric internal-symmetry channels. If the external operators are distinct, both even and odd spins can appear.

## Unitarity input

The exchanged primary dimensions must obey the unitary bounds. For scalar primaries in $d>2$,

$$
\Delta\ge\frac{d-2}{2},
$$

and for spin $\ell>0$ symmetric traceless primaries,

$$
\Delta\ge \ell+d-2.
$$

Saturation for $\ell>0$ means conservation. A spin-one primary at the bound is a conserved current, and a spin-two primary at the bound is a conserved stress tensor. In any local CFT with a stress tensor, $T_{\mu\nu}$ should appear in $\phi\times\phi$ unless $\phi$ is in a completely decoupled sector with no coupling to that stress tensor.

In a first scalar bootstrap scan, one often does not isolate the stress tensor explicitly. One merely allows spin-two operators with $\Delta\ge d$, and the stress tensor is among the allowed operators. More refined analyses can impose a stress tensor at $\Delta=d$ and use the Ward identity relation between $\lambda_{\phi\phi T}$ and $C_T$.

## Scalar gap bounds

The simplest useful output is an upper bound on the first scalar appearing in $\phi\times\phi$.

Fix the external dimension $\Delta_\phi$. Suppose the assumptions say that the first non-identity scalar $S$ in the $\phi\times\phi$ OPE has

$$
\Delta_S\ge \Delta_*.
$$

For each trial value $\Delta_*$, ask whether a separating functional exists. If one exists, the gap assumption is impossible. If no functional exists at the chosen search strength, the gap is not excluded.

By scanning $\Delta_*$, one obtains a numerical upper bound

$$
\Delta_S\le f(\Delta_\phi).
$$

This should be read carefully. The statement is conditional:

> Under the assumptions used in the search, every unitary CFT with scalar $\phi$ of dimension $\Delta_\phi$ must contain some scalar in $\phi\times\phi$ with dimension at most $f(\Delta_\phi)$.

It is not a statement that every point below the curve is realized by an actual CFT.

## OPE coefficient bounds

The same setup can bound an OPE coefficient. Suppose the spectrum contains a scalar $S$ with dimension $\Delta_S$ and OPE coefficient $\lambda_{\phi\phi S}$. Separate its contribution:

$$
F_{\mathbf 1}
+
\lambda_{\phi\phi S}^2F_{\Delta_S,0}
+
\sum_{\mathcal O\ne \mathbf 1,S}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}=0.
$$

A functional can be optimized to bound $\lambda_{\phi\phi S}^2$ from above or below, depending on the assumed spectrum and normalization. The essential move is to normalize the functional on $F_{\Delta_S,0}$ and demand positivity on the remaining allowed operators.

Similarly, if the stress tensor is isolated, the Ward identity fixes

$$
\lambda_{\phi\phi T}^2\propto \frac{\Delta_\phi^2}{C_T}
$$

with a convention-dependent proportionality factor. Bounding $\lambda_{\phi\phi T}^2$ gives a bound on $C_T$. This is one way the scalar bootstrap constrains a theory's effective number of degrees of freedom.

## Generalized free fields as a calibration point

A useful calibration example is a generalized free scalar. Its four-point function is determined by Wick-like pairings:

$$
\mathcal G(U,V)=1+U^{\Delta_\phi}+\left(\frac{U}{V}\right)^{\Delta_\phi}.
$$

This correlator is crossing symmetric for any $\Delta_\phi$ compatible with scalar unitarity. Its OPE contains double-twist operators with schematic dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell,
\qquad
n=0,1,2,\ldots,
$$

and even spin $\ell$ for the identical scalar OPE.

Generalized free fields are excellent tests of normalization and large-spin intuition. But they also teach a cautionary lesson. A crossing-symmetric four-point function is not automatically a complete local CFT with a normal stress tensor in the same OPE. The bootstrap equation is a consistency condition on CFT data, not a complete constructive definition unless all correlators, OPE associativity conditions, and locality requirements are satisfied.

## Kinks and candidate CFTs

When a scalar-gap bound is plotted as a function of $\Delta_\phi$, the curve sometimes develops a sharp bend or kink. Famous examples occur near data of known or expected CFTs, such as the critical Ising model in three dimensions.

The intuitive explanation is this. A bound curve is the boundary of what the bootstrap search cannot exclude. At special CFTs, many constraints can become simultaneously tight: a low-lying scalar, a stress tensor, higher-spin gaps, and positivity may all conspire to make the allowed region turn sharply.

But a kink is not a proof of existence. Kinks can be caused by changes in the optimal functional, by generalized-free-like behavior, by decoupled sectors, by insufficient assumptions, or by numerical artifacts. A convincing identification of a CFT usually requires additional evidence: stable convergence with increasing derivative order, spectrum extraction, mixed-correlator islands, known symmetry assignments, analytic checks, or independent lattice and perturbative comparisons.

Kinks are wonderful signposts. They are not passports.

## Linear-functional certificates

The cleanest output of an exclusion search is a functional certificate. For an assumed gap, a functional $\alpha$ certifies exclusion if

$$
\alpha(F_{\mathbf 1})>0,
$$

and

$$
\alpha(F_{\Delta,\ell})\ge0
$$

for every allowed exchanged operator. The allowed set includes the unitarity bound, the spin parity rule, any assumed scalar gap, and any other spectral assumptions.

In a derivative-basis search, one writes

$$
\alpha[f]
=
\sum_{m+n\le\Lambda}a_{mn}
\left.
\partial_z^m\partial_{\bar z}^n f(z,\bar z)
\right|_{z=\bar z=1/2},
$$

with parity restrictions chosen so that the derivatives test the independent crossing-odd components. Larger $\Lambda$ means a larger functional space. Bounds usually become stronger and more reliable as $\Lambda$ increases, but numerical cost grows quickly.

A good numerical result should specify the functional basis, derivative order, spin truncation or asymptotic treatment, block approximation, precision, and assumptions. Without those details, a bootstrap plot is a picture of an argument whose proof has gone missing.

## Common pitfalls

**Confusing exclusion with construction.** If a point is not excluded, that does not prove a CFT exists there. It only means no contradiction was found in the chosen search space.

**Forgetting even-spin selection.** A single real scalar OPE contains only even-spin symmetric traceless primaries. This statement changes in global-symmetry channels and in nonidentical correlators.

**Treating kink equals CFT as a theorem.** Kinks are often physically meaningful, but they require supporting evidence.

**Ignoring two-point normalization.** Rescaling an exchanged operator rescales OPE coefficients. Only normalization-invariant combinations or convention-fixed coefficients are physically comparable.

**Assuming generalized free fields are ordinary local CFTs.** Generalized free correlators solve many crossing equations, but they do not by themselves supply the full local operator content of an interacting CFT with a stress tensor.

**Overreading finite-derivative numerics.** A finite derivative cutoff gives a rigorous statement only when the positivity over the continuous spectrum and numerical precision are controlled.

## Relations to other pages

- [Mixed-Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) explains how one improves this setup by bootstrapping several four-point functions at once.
- [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/) discusses the assumptions that turn crossing into useful bounds.
- [Islands in Parameter Space](/cft-bootstrap/crossing-bootstrap-logic/islands-in-parameter-space/) explains how small allowed regions arise.
- [Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/) explains how boundary points can reveal approximate spectra.
- [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) develops the optimization machinery behind the search.

## Research status

The identical scalar bootstrap is a mature and established part of the conformal bootstrap. It is the simplest setting where conformal blocks, crossing, unitarity, and positive linear functionals all appear in their cleanest form.

Its limitations are equally established. A single four-point function often gives bounds and kinks, but not enough information to isolate a physical theory uniquely. Modern high-precision determinations of nontrivial CFT data usually combine single-correlator intuition with mixed correlators, global symmetries, spectrum assumptions, stress-tensor information, analytic large-spin input, or numerical island-finding algorithms.

## Exercises

### Exercise 1: Derive the crossing vector

Starting from

$$
V^{\Delta_\phi}\mathcal G(U,V)=U^{\Delta_\phi}\mathcal G(V,U),
$$

and

$$
\mathcal G(U,V)=1+
\sum_{\mathcal O\ne\mathbf 1}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(U,V),
$$

derive the identical scalar crossing equation in terms of $F_{\Delta,\ell}$.

<details><summary><strong>Solution</strong></summary>

Substitute the block expansion into crossing:

$$
V^{\Delta_\phi}
\left(
1+
\sum_{\mathcal O\ne\mathbf 1}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(U,V)
\right)
=
U^{\Delta_\phi}
\left(
1+
\sum_{\mathcal O\ne\mathbf 1}\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(V,U)
\right).
$$

Move the right-hand side to the left:

$$
V^{\Delta_\phi}-U^{\Delta_\phi}
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
\left(
V^{\Delta_\phi}G_{\Delta,\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,\ell}(V,U)
\right)
=0.
$$

Thus

$$
F_{\mathbf 1}=V^{\Delta_\phi}-U^{\Delta_\phi},
$$

and

$$
F_{\Delta,\ell}=V^{\Delta_\phi}G_{\Delta,\ell}(U,V)-U^{\Delta_\phi}G_{\Delta,\ell}(V,U).
$$

</details>

### Exercise 2: Why do odd spins vanish?

Explain why a single real scalar OPE $\phi\times\phi$ contains only even-spin symmetric traceless primaries.

<details><summary><strong>Solution</strong></summary>

The product $\phi(x_1)\phi(x_2)$ is symmetric under exchanging the two identical bosonic operators. In the OPE, a spin-$\ell$ symmetric traceless primary appears with an angular dependence built from the separation direction $x_{12}$. Under $x_1\leftrightarrow x_2$, this direction changes sign:

$$
x_{12}\to -x_{12}.
$$

A spin-$\ell$ structure changes by $(-1)^\ell$. Symmetry of the full OPE therefore requires

$$
(-1)^\ell=1,
$$

so $\ell$ is even. Odd-spin coefficients vanish for this particular OPE.

</details>

### Exercise 3: Functional exclusion

Suppose $\alpha(F_{\mathbf 1})=1$ and $\alpha(F_{\Delta,\ell})\ge0$ for every non-identity operator allowed by some assumptions. Show that the assumptions are inconsistent.

<details><summary><strong>Solution</strong></summary>

Apply $\alpha$ to crossing:

$$
0=
\alpha(F_{\mathbf 1})+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2\alpha(F_{\Delta,\ell}).
$$

By assumption, the identity term is $1$. In a unitary identical scalar problem,

$$
\lambda_{\phi\phi\mathcal O}^2\ge0,
$$

and all $\alpha(F_{\Delta,\ell})$ are nonnegative. Therefore the right-hand side is at least $1$, contradicting the equality to zero. The assumed spectrum cannot occur in a unitary CFT satisfying the bootstrap equation.

</details>

## References

- A. M. Polyakov, “Non-Hamiltonian approach to conformal quantum field theory,” *Soviet Physics JETP* **39** (1974).
- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding scalar operator dimensions in 4D CFT,” *JHEP* **0812** (2008), arXiv:0807.0004.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising model with the conformal bootstrap,” *Physical Review D* **86** (2012), arXiv:1203.6064.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs in Physics, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, arXiv:1602.07982.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405.

## Version history

- 2026-06-28: First polished draft. Introduces the identical scalar bootstrap equation, spin selection, scalar gap bounds, OPE coefficient bounds, generalized free calibration, kink interpretation, and functional certificates.
