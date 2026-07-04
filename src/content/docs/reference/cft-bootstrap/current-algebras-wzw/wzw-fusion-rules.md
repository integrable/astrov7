---
title: "WZW Fusion Rules"
description: "How primary fields in compact WZW models multiply through level-truncated tensor products, affine representation theory, and the Verlinde formula."
sidebar:
  label: "WZW Fusion Rules"
  order: 8
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal chs. 14–16; Verlinde 1988; Kac; standard WZW and rational CFT literature."
topics:
  - WZW fusion rules
  - affine Lie algebras
  - Verlinde formula
  - integrable representations
  - rational CFT
canonicalTopics:
  - wzw-fusion-rules
  - affine-fusion
  - su2k-fusion
researchStatus:
  established:
    - "Fusion rules of compact WZW models at positive integer level are finite and are computed by the affine modular S matrix through the Verlinde formula."
  active:
    - "Nonsemisimple, logarithmic, supergroup, boundary, and defect versions require refinements beyond the compact semisimple WZW fusion ring."
---

## Summary

**WZW fusion rules** describe the allowed primary families in the operator product of two Wess–Zumino–Witten primary fields. For a compact simple WZW model $G_k$, primary labels are integrable highest weights

$$
\lambda\in P_k^+,
$$

and fusion is written

$$
\mathcal V_\lambda\times\mathcal V_\mu
=\sum_{\nu\in P_k^+}N_{\lambda\mu}{}^\nu\,\mathcal V_\nu.
$$

The coefficient

$$
N_{\lambda\mu}{}^\nu\in\mathbb Z_{\ge0}
$$

is a fusion coefficient. It says which affine conformal families may appear. It is not an OPE coefficient.

For $SU(2)_k$, the rule is a level-truncated version of angular-momentum addition:

$$
j_1\times j_2
=\sum_{j=|j_1-j_2|}^{\min(j_1+j_2,k-j_1-j_2)} j,
$$

where $j$ increases in integer steps. The upper cutoff is the new WZW feature. It removes ordinary finite-dimensional tensor-product channels that lie outside the level-$k$ affine alcove.

In general compact WZW models, the most universal computational formula is the Verlinde formula:

$$
N_{\lambda\mu}{}^\nu
=\sum_{\rho\in P_k^+}
\frac{S_{\lambda\rho}S_{\mu\rho}S^*_{\nu\rho}}{S_{0\rho}}.
$$

This page explains the fusion ring, the $SU(2)_k$ example, the relation to ordinary tensor products, quantum dimensions, simple currents, and common normalization traps.

## Prerequisites

Read [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/), [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Verlinde Formula Preview](/cft-bootstrap/minimal-models-rational-cft/verlinde-formula-preview/) first.

You should know that compact WZW primaries are not labeled by all finite-dimensional representations of $G$. At positive integer level $k$, they are labeled only by integrable highest weights satisfying

$$
(\lambda,\theta)\le k.
$$

## Core idea

The ordinary tensor product of finite-dimensional representations is usually too large for a WZW model at fixed level. It can produce highest weights outside the integrable set $P_k^+$. WZW fusion is the conformal-field-theory multiplication rule after the affine level constraint has been imposed.

A useful first approximation is

$$
\text{WZW fusion}
\approx
\text{finite tensor product, truncated by the level}.
$$

This slogan is exact enough to guide intuition, but it is not the full general algorithm for all groups. The fully reliable statement is that fusion is computed by the affine modular $S$ matrix through the Verlinde formula.

The conceptual pipeline is

$$
\widehat{\mathfrak g}_k\text{ characters}
\longrightarrow
S_{\lambda\mu}
\longrightarrow
N_{\lambda\mu}{}^\nu
\longrightarrow
\text{allowed OPE families}.
$$

This is one of the cleanest examples of rational CFT: modular transformations on the torus determine operator-algebra selection rules on the sphere.

## Setup and conventions

Let $G$ be compact and simple, with Lie algebra $\mathfrak g$. The affine current algebra has level $k$:

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}+k m\kappa^{ab}\delta_{m+n,0}.
$$

The integrable highest weights at level $k$ form the finite set

$$
P_k^+=\{\lambda\in P^+:(\lambda,\theta)\le k\}.
$$

For each $\lambda\in P_k^+$ there is an affine module $\mathcal V_\lambda$ and a character

$$
\chi_\lambda(\tau)=\operatorname{Tr}_{\mathcal V_\lambda}q^{L_0-c/24}.
$$

The modular $S$ matrix is defined by

$$
\chi_\lambda(-1/\tau)=\sum_{\mu\in P_k^+}S_{\lambda\mu}\chi_\mu(\tau).
$$

The fusion rules are

$$
\mathcal V_\lambda\times\mathcal V_\mu
=\sum_{\nu\in P_k^+}N_{\lambda\mu}{}^\nu\mathcal V_\nu.
$$

In diagonal local WZW models, this chiral fusion data is paired with the corresponding antiholomorphic data. Non-diagonal modular invariants can use the same chiral fusion ring while assembling local fields differently.

## Fusion is not an OPE coefficient

Fusion rules say which affine families can appear. They do not give the normalized OPE coefficients.

A chiral OPE has the schematic form

$$
\phi_\lambda(z)\phi_\mu(0)
\sim
\sum_{\nu,\alpha}
C_{\lambda\mu}^{\nu,\alpha}
z^{h_\nu-h_\lambda-h_\mu}
\left(\phi_{\nu,\alpha}(0)+\text{descendants}\right),
$$

where $\alpha$ labels possible multiplicity. The fusion coefficient counts the number of independent chiral channels:

$$
\alpha=1,\ldots,N_{\lambda\mu}{}^\nu.
$$

In many simple WZW examples, fusion is multiplicity-free, so $N_{\lambda\mu}{}^\nu$ is $0$ or $1$. More general affine and rational CFTs can have higher multiplicities.

The OPE coefficient is dynamical and convention-dependent. The fusion coefficient is an integer selection rule. Confusing them is the current-algebra version of a classic bootstrap mistake.

## SU(2) at level k

The $SU(2)_k$ primaries are labeled by spins

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

The fusion rule is

$$
j_1\times j_2
=\sum_j j,
$$

where $j$ runs in integer steps from

$$
|j_1-j_2|
$$

to

$$
\min(j_1+j_2,k-j_1-j_2).
$$

The ordinary tensor product would stop at $j_1+j_2$. The WZW fusion rule replaces that upper endpoint by the smaller value

$$
\min(j_1+j_2,k-j_1-j_2).
$$

The second endpoint is the affine level cutoff.

Examples:

| Theory | Fusion rule | Comment |
|---|---|---|
| $SU(2)_1$ | $\frac12\times\frac12=0$ | The spin-$1$ channel is absent. |
| $SU(2)_2$ | $\frac12\times\frac12=0+1$ | Matches ordinary tensor product for this product. |
| $SU(2)_2$ | $1\times1=0$ | The spin-$2$ channel is absent. |
| $SU(2)_3$ | $1\times1=0+1$ | The spin-$2$ channel is absent. |
| $SU(2)_3$ | $\frac32\times\frac32=0$ | The top representation is a simple current. |

These examples show that the truncation is not a small correction. At low level, it is the dominant feature.

## SU(2) modular S matrix

The $SU(2)_k$ modular $S$ matrix is

$$
S_{jj'}=\sqrt{\frac{2}{k+2}}
\sin\left(\frac{(2j+1)(2j'+1)\pi}{k+2}\right),
$$

where

$$
j,j'=0,\frac12,1,\ldots,\frac{k}{2}.
$$

The Verlinde formula

$$
N_{j_1j_2}{}^{j_3}
=\sum_{j=0}^{k/2}
\frac{S_{j_1j}S_{j_2j}S^*_{j_3j}}{S_{0j}}
$$

reproduces the truncated spin-addition rule above.

The quantum dimension is

$$
d_j=\frac{S_{j0}}{S_{00}}
=\frac{\sin\left(\frac{(2j+1)\pi}{k+2}\right)}
{\sin\left(\frac{\pi}{k+2}\right)}.
$$

For the fundamental spin-$1/2$ primary,

$$
d_{1/2}=2\cos\left(\frac{\pi}{k+2}\right).
$$

At large $k$, this approaches $2$, the ordinary dimension of the fundamental $SU(2)$ representation. At finite $k$, the quantum dimension is not generally an integer.

## Fusion matrices

For each primary label $\lambda$, define the fusion matrix

$$
(N_\lambda)_\mu{}^\nu=N_{\lambda\mu}{}^\nu.
$$

The fusion matrices satisfy

$$
N_\lambda N_\mu=\sum_\nu N_{\lambda\mu}{}^\nu N_\nu.
$$

They commute and are simultaneously diagonalized by the modular $S$ matrix:

$$
N_\lambda S_{\cdot\rho}
=\frac{S_{\lambda\rho}}{S_{0\rho}}S_{\cdot\rho}.
$$

This is the matrix form of the Verlinde formula. It is often the cleanest way to compute or check fusion.

For $SU(2)_2$ in the basis

$$
0,\quad \frac12,\quad 1,
$$

fusion by $1/2$ has matrix

$$
N_{1/2}=
\begin{pmatrix}
0&1&0\\
1&0&1\\
0&1&0
\end{pmatrix},
$$

which is the same adjacency matrix as the Ising spin fusion matrix. This is not an accident: $SU(2)_2$ has Ising-type fusion after identifying the spin-$1/2$ object with the nonabelian object.

## Simple currents

A primary $J$ is a **simple current** if fusion by $J$ permutes the primary labels:

$$
J\times\lambda=J(\lambda).
$$

Equivalently, in a unitary rational CFT, it has quantum dimension

$$
d_J=1.
$$

In $SU(2)_k$, the top spin

$$
j=\frac{k}{2}
$$

is a simple current. Its fusion action is

$$
\frac{k}{2}\times j=\frac{k}{2}-j.
$$

Simple currents are important because they can generate non-diagonal modular invariants and extended chiral algebras. They also provide a bridge between fusion rules and generalized symmetry language.

However, not every primary of quantum dimension one is automatically a physical symmetry operator in a chosen local theory. One must still check spin, locality, and the modular invariant.

## Relation to finite tensor products

At large level, for representations much smaller than the level, WZW fusion agrees with ordinary tensor products. For example, in $SU(2)_k$, if

$$
j_1+j_2\le\frac{k}{2},
$$

then

$$
j_1\times j_2
$$

contains the same spins as the ordinary $SU(2)$ tensor product. If

$$
j_1+j_2>\frac{k}{2},
$$

high-spin channels are removed.

For general $G_k$, a similar statement holds qualitatively: finite tensor products are modified by the affine Weyl alcove. Ordinary highest weights outside the level-$k$ alcove do not appear as independent WZW primary channels.

A more precise algorithm can be expressed using affine Weyl reflections and signs, or computed directly through the Verlinde formula. The Verlinde formula is usually the safest route because it automatically implements all affine identifications and truncations.

## Fusion and conformal blocks

Fusion coefficients count chiral conformal blocks on the sphere with three insertions:

$$
N_{\lambda\mu}{}^\nu
=\dim \operatorname{Hom}(\mathcal V_\lambda\times\mathcal V_\mu,\mathcal V_\nu).
$$

For four-point functions, fusion rules constrain the allowed intermediate affine families. If

$$
\lambda\times\mu=\sum_\nu N_{\lambda\mu}{}^\nu\nu,
$$

then the $\lambda\mu$ OPE channel contains only those $\nu$.

The Knizhnik–Zamolodchikov equations then determine the corresponding chiral conformal blocks as solutions of a differential equation. Fusion rules tell us how many local solutions are expected in an OPE channel; the KZ equations describe their position dependence.

Thus the division of labor is

$$
\text{fusion rules} \Rightarrow \text{which channels},
\qquad
\text{KZ equations} \Rightarrow \text{how blocks vary with }z_i.
$$

## Relation to anyons and topological phases

The fusion ring of a rational CFT is also the fusion ring of the corresponding topological lines in the associated three-dimensional topological field theory, when such a theory exists. For compact WZW models, this relation is realized through Chern–Simons theory.

In this language, integrable highest weights label anyon types, fusion coefficients count fusion channels, and quantum dimensions measure asymptotic fusion growth. For example, $SU(2)_k$ gives the familiar family of anyon theories often used as examples in topological quantum computation.

This page stays on the CFT side. The topological-field-theory interpretation becomes important later in boundary, defect, and topological phases pages.

## Common pitfalls

**Do not use ordinary tensor products without the level cutoff.** WZW fusion is not simply finite-dimensional tensor product decomposition.

**Do not treat fusion coefficients as OPE coefficients.** Fusion coefficients are integers. OPE coefficients depend on normalization and crossing data.

**Do not include nonintegrable weights.** Only $\lambda\in P_k^+$ label compact WZW primary families at level $k$.

**Do not assume diagonal local pairing.** Chiral fusion rules are part of the data. A full local CFT also requires a modular invariant.

**Do not forget multiplicities in general.** Many simple examples are multiplicity-free, but rational CFT fusion coefficients can be larger than one.

**Do not compare quantum dimension with ordinary representation dimension.** They agree only in special limits or special cases. At finite level, quantum dimensions are generally noninteger.

## Relations to other pages

This page follows [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/) and explains how the allowed affine primary labels multiply. It uses [Verlinde Formula Preview](/cft-bootstrap/minimal-models-rational-cft/verlinde-formula-preview/) and [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/) for the modular-data logic.

The next page, [Knizhnik–Zamolodchikov Equations](/cft-bootstrap/current-algebras-wzw/knizhnik-zamolodchikov-equations/), explains how current algebra determines WZW conformal blocks. [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) later uses WZW fusion in numerator and denominator theories. Boundary and defect chapters use the same fusion coefficients to build Cardy boundary states and topological defect algebras.

## Research status

WZW fusion rules for compact simple groups at positive integer level are established. They are a central part of rational CFT, affine Lie algebra representation theory, and modular tensor category theory.

Active work uses and generalizes this structure in nonsemisimple current algebras, logarithmic CFT, supergroup WZW models, non-invertible symmetry, conformal defects, topological phases, and categorified approaches to rational CFT.

## Exercises

### Exercise 1

Compute the fusion rule $\frac12\times\frac12$ in $SU(2)_1$.

<details><summary><strong>Solution</strong></summary>

The allowed spins are

$$
j=0,\frac12.
$$

The lower endpoint is

$$
|\frac12-\frac12|=0.
$$

The upper endpoint is

$$
\min\left(\frac12+\frac12,1-\frac12-\frac12\right)=\min(1,0)=0.
$$

Therefore

$$
\frac12\times\frac12=0.
$$

The ordinary spin-$1$ channel is absent because it is not integrable at level one.

</details>

### Exercise 2

Compute the fusion rule $1\times1$ in $SU(2)_2$.

<details><summary><strong>Solution</strong></summary>

The lower endpoint is

$$
|1-1|=0.
$$

The upper endpoint is

$$
\min(1+1,2-1-1)=\min(2,0)=0.
$$

Thus only $j=0$ appears:

$$
1\times1=0.
$$

The ordinary finite tensor product $1\otimes1=0+1+2$ is heavily truncated at level two.

</details>

### Exercise 3

Use the $SU(2)_k$ quantum dimension formula to compute $d_{1/2}$ at $k=2$.

<details><summary><strong>Solution</strong></summary>

The formula is

$$
d_{1/2}=2\cos\left(\frac{\pi}{k+2}\right).
$$

At $k=2$,

$$
d_{1/2}=2\cos\left(\frac{\pi}{4}\right)=2\cdot\frac{1}{\sqrt2}=\sqrt2.
$$

This matches the Ising-like nonabelian fusion of the spin-$1/2$ object in $SU(2)_2$.

</details>

### Exercise 4

Explain why the Verlinde formula determines fusion but not OPE coefficients.

<details><summary><strong>Solution</strong></summary>

The Verlinde formula computes the integers

$$
N_{\lambda\mu}{}^\nu.
$$

These integers count allowed chiral channels or multiplicities. OPE coefficients are the numerical constants multiplying the allowed primary families in a chosen normalization. Those constants depend on field normalization and crossing data. Therefore fusion is necessary information for the OPE, but it is not the full OPE.

</details>

## References

- E. Verlinde, “Fusion rules and modular transformations in 2D conformal field theory,” *Nuclear Physics B* **300** (1988).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).
- V. G. Turaev, *Quantum Invariants of Knots and 3-Manifolds*, de Gruyter, 1994.

## Version history

- 2026-06-30: First polished draft. Added WZW fusion definitions, $SU(2)_k$ rule, modular $S$ matrix, Verlinde computation, fusion matrices, simple currents, quantum dimensions, pitfalls, exercises, and references.
