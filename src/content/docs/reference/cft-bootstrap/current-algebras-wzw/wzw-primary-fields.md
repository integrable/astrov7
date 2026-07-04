---
title: "WZW Primary Fields"
description: "How Wess–Zumino–Witten primary fields are labeled by affine highest weights, transform under left and right current algebras, and acquire conformal weights from the Sugawara construction."
sidebar:
  label: "WZW Primary Fields"
  order: 6
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Senechal chs. 14–15; Knizhnik and Zamolodchikov 1984; Witten 1984; standard WZW representation theory."
topics:
  - WZW primary fields
  - affine primaries
  - current algebra
  - Sugawara construction
  - integrable representations
canonicalTopics:
  - wzw-primary-fields
  - affine-primary-fields
  - current-primary-ope
researchStatus:
  established:
    - "Primary fields of compact WZW models are labeled by integrable highest weights of the affine algebra at level k, and their conformal weights are fixed by the quadratic Casimir."
  active:
    - "Non-diagonal modular invariants, boundary conditions, defects, supergroup WZW models, and logarithmic current algebras require refinements of the compact diagonal story."
---

## Summary

A **WZW primary field** is a local field transforming as a primary under the affine current algebra. For a compact simple WZW model $G_k$, chiral affine primaries are labeled by integrable highest weights $\lambda$ of $\widehat{\mathfrak g}_k$. In the diagonal local theory, the corresponding bulk primary has left and right labels paired as

$$
\Phi_\lambda(z,\bar z)\in
\mathcal V_\lambda\otimes\overline{\mathcal V}_\lambda.
$$

The current OPEs have the schematic form

$$
J^a(z)\Phi_\lambda(w,\bar w)
\sim
\frac{t^a_\lambda\Phi_\lambda(w,\bar w)}{z-w},
$$

and similarly for the right-moving current. The Sugawara construction fixes the chiral conformal weight:

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}
=\frac{(\lambda,\lambda+2\rho)}{2(k+h^\vee)}.
$$

For $SU(2)_k$, the primary labels are spins

$$
j=0,\frac12,1,\ldots,\frac{k}{2},
$$

with

$$
h_j=\frac{j(j+1)}{k+2}.
$$

This page explains how WZW primaries transform, why only finitely many appear at positive integer level, how their dimensions are computed, and how they organize correlators and fusion.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/), and [WZW Action](/cft-bootstrap/current-algebras-wzw/wzw-action/) first.

You should also know that an ordinary Virasoro primary is defined by its OPE with $T(z)$. A WZW primary is more restrictive: it is primary with respect to the current algebra, not merely with respect to Virasoro.

## Core idea

The WZW model has more symmetry than a generic two-dimensional CFT. Instead of organizing states only into Virasoro families, we organize them into affine current-algebra families.

A chiral affine primary state $|\lambda\rangle$ obeys

$$
J^a_n|\lambda\rangle=0
\qquad n>0,
$$

and the zero modes act as a finite-dimensional representation of $\mathfrak g$ with highest weight $\lambda$:

$$
J^a_0|\lambda\rangle=t^a_\lambda|\lambda\rangle.
$$

Negative current modes create affine descendants:

$$
J^{a_1}_{-n_1}\cdots J^{a_r}_{-n_r}|\lambda\rangle,
\qquad n_i>0.
$$

The key point is that an affine family contains many Virasoro families. Organizing by affine symmetry is therefore much more efficient than organizing by Virasoro alone.

The slogan is

$$
\text{finite highest weight }\lambda
\quad\Longrightarrow\quad
\text{affine primary}
\quad\Longrightarrow\quad
\text{current-algebra conformal family}.
$$

## Setup and conventions

We use the current OPE convention

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The current modes are

$$
J^a_n=\oint_0\frac{dz}{2\pi i}\,z^nJ^a(z).
$$

For compact simple $\mathfrak g$, we use long-root normalization

$$
(\theta,\theta)=2,
$$

where $\theta$ is the highest root. The dual Coxeter number is $h^\vee$, the Weyl vector is $\rho$, and the quadratic Casimir of highest weight $\lambda$ is

$$
C_2(\lambda)=(\lambda,\lambda+2\rho).
$$

In these conventions, the Sugawara conformal weight is

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}.
$$

The precise placement of signs in right-moving current OPEs depends on whether the right index is written as a representation or dual-representation index. The invariant statement is that the bulk field transforms under $G_L\times G_R$ with specified left and right representations.

## Chiral affine primaries

A chiral affine primary field $\phi_\lambda(z)$ is defined by the OPE

$$
J^a(z)\phi_\lambda(w)
\sim
\frac{t^a_\lambda\phi_\lambda(w)}{z-w}.
$$

There is no double pole in this OPE. A double pole would mean the field is not an affine primary but an affine descendant or composite with a more singular current action.

At the state level, radial quantization gives

$$
J^a_n|\lambda\rangle=0
\qquad n>0.
$$

The zero modes form the finite Lie algebra:

$$
[J^a_0,J^b_0]=i f^{ab}{}_cJ^c_0.
$$

Thus the zero-mode part of an affine primary is an ordinary finite-dimensional $\mathfrak g$ representation. The positive modes vanish on the primary, while negative modes generate descendants.

For a highest-weight primary, one also chooses a highest-weight vector under the finite algebra. Acting with finite lowering operators inside $\mathfrak g$ produces the other components of the finite multiplet.

## Bulk WZW fields

A full local WZW field has both holomorphic and antiholomorphic labels. In the diagonal compact WZW model, the Hilbert space is

$$
\mathcal H_{\rm diag}
=\bigoplus_{\lambda\in P_k^+}
\mathcal V_\lambda\otimes\overline{\mathcal V}_\lambda,
$$

where $P_k^+$ is the finite set of integrable highest weights at level $k$.

The corresponding bulk primary field may be written schematically as

$$
\Phi_\lambda(z,\bar z).
$$

More explicitly, it has finite representation indices:

$$
(\Phi_\lambda)^A{}_{\bar B}(z,\bar z),
$$

where $A$ transforms under the left representation and $\bar B$ under the right representation or its dual, depending on convention.

For the basic group-valued field in the WZW action, one often writes

$$
g(z,\bar z)^A{}_{\bar B},
$$

which transforms under

$$
g\mapsto h_L g h_R^{-1}.
$$

This field is the primary associated with the defining representation when that representation is integrable at the chosen level.

## Current-primary Ward identities

The current-primary OPE immediately gives the Ward identity

$$
\left\langle J^a(z)\prod_i\Phi_i(z_i,\bar z_i)\right\rangle
=\sum_i\frac{t_i^a}{z-z_i}
\left\langle \prod_i\Phi_i(z_i,\bar z_i)\right\rangle,
$$

for sphere correlators with no extra singularity at infinity.

Integrating around all insertions gives the global singlet condition

$$
\sum_i t_i^a
\left\langle \prod_i\Phi_i(z_i,\bar z_i)\right\rangle=0.
$$

This is the finite-group selection rule. But current algebra gives more: insertions of negative current modes and descendants can also be reduced using contour deformation. These Ward identities are the starting point for the Knizhnik–Zamolodchikov equations.

The current algebra therefore controls not just which correlators vanish, but also how nonzero correlators depend on positions.

## Conformal weights from Sugawara

The Sugawara zero mode is

$$
L_0=\frac{1}{2(k+h^\vee)}\left(\kappa_{ab}J^a_0J^b_0+2\sum_{n>0}\kappa_{ab}J^a_{-n}J^b_n\right).
$$

On an affine primary $|\lambda\rangle$, the positive modes vanish. Therefore

$$
L_0|\lambda\rangle
=\frac{C_2(\lambda)}{2(k+h^\vee)}|\lambda\rangle.
$$

Thus

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}.
$$

For a diagonal bulk primary,

$$
\Delta_\lambda=h_\lambda+\bar h_\lambda=2h_\lambda,
\qquad
J_\lambda=h_\lambda-ar h_\lambda=0.
$$

For non-diagonal modular invariants or chiral theories, left and right labels can differ, and the spin need not vanish. Bosonic locality requires integer spin for genuine local operators.

## Integrability and finite spectra

Not every finite-dimensional highest weight is allowed in a compact WZW model at level $k$. The allowed weights are integrable:

$$
(\lambda,\theta)\le k.
$$

This constraint is what makes the positive-integer-level compact WZW model rational. There are only finitely many allowed affine primary families.

For $SU(2)_k$, the condition becomes

$$
2j\le k.
$$

For $SU(N)_k$, if

$$
\lambda=\sum_{i=1}^{N-1}\lambda_i\omega_i
$$

is written in Dynkin labels, the condition is

$$
\sum_{i=1}^{N-1}\lambda_i\le k.
$$

The next page develops this condition systematically. Here the important point is that primary fields are not labeled by all finite representations of $G$, but only by the integrable ones at the chosen level.

## Example: SU(2) at level k

The $SU(2)_k$ WZW model has affine primaries labeled by spin

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

The central charge is

$$
c=\frac{3k}{k+2},
$$

and the conformal weights are

$$
h_j=\frac{j(j+1)}{k+2}.
$$

At level $k=1$, the allowed primaries are

$$
j=0,\quad \frac12.
$$

Their weights are

$$
h_0=0,
\qquad
h_{1/2}=\frac14.
$$

At level $k=2$, the allowed primaries are

$$
j=0,\quad \frac12,\quad 1,
$$

with

$$
h_0=0,
\qquad
h_{1/2}=\frac{3}{16},
\qquad
h_1=\frac12.
$$

These small examples are useful calibration points for fusion rules and modular data.

## Example: SU(N) fundamentals

For $SU(N)_k$, the fundamental representation has quadratic Casimir

$$
C_2({\rm fund})=\frac{N^2-1}{N}
$$

in the long-root convention used by the formula

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+N)}.
$$

Therefore

$$
h_{\rm fund}=\frac{N^2-1}{2N(k+N)}.
$$

At level $k=1$, the integrable representations of $SU(N)_1$ are the antisymmetric tensor representations with highest weights

$$
0,\ \omega_1,\ \omega_2,\ \ldots,\ \omega_{N-1}.
$$

This finite set is closely related to abelian current algebra and compact bosons. For example, $SU(2)_1$ is equivalent to a compact boson at a special radius after matching chiral algebras.

## Fusion preview

WZW fusion is a level-truncated version of finite-dimensional tensor product decomposition. In $SU(2)_k$, the fusion rule resembles angular momentum addition but with an upper cutoff:

$$
j_1\times j_2
=\sum_{j=|j_1-j_2|}^{\min(j_1+j_2,k-j_1-j_2)}j,
$$

where $j$ increases in integer steps.

At large $k$, the cutoff is often invisible for small spins, and one recovers the ordinary finite $SU(2)$ tensor product. At finite $k$, the truncation is essential. It is the WZW analogue of the finite fusion rules in minimal models.

The exact fusion coefficients are computed by the Verlinde formula using the affine modular $S$ matrix. The primary labels on this page are the labels that enter that formula.

## Common pitfalls

**Do not confuse affine primaries with Virasoro primaries.** Every affine primary is Virasoro primary under the Sugawara stress tensor, but a Virasoro primary need not be affine primary.

**Do not label WZW primaries by all finite-dimensional representations.** At compact positive integer level, only integrable highest weights are allowed.

**Do not forget the level in the conformal weight.** The same finite representation has different conformal weights at different $k$.

**Do not confuse the group-valued field $g$ with every primary field.** The field $g$ is the primary in the defining representation when that representation is allowed. Other primaries correspond to other integrable representations.

**Do not ignore right-moving data.** A full local WZW operator needs both left and right chiral labels and a modular-invariant pairing.

**Do not mix Casimir normalizations.** The formula for $h_\lambda$ must be used with the same generator normalization as the current OPE and Sugawara tensor.

## Relations to other pages

This page uses [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) for conformal weights and [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/) for current Ward identities.

The next page, [Integrable Highest Weights](/cft-bootstrap/current-algebras-wzw/integrable-highest-weights/), explains the finite set $P_k^+$ in detail. [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) explains how these labels multiply. [Knizhnik–Zamolodchikov Equations](/cft-bootstrap/current-algebras-wzw/knizhnik-zamolodchikov-equations/) derives differential equations for correlators of these primaries.

This page also connects back to [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) and [Verlinde Formula Preview](/cft-bootstrap/minimal-models-rational-cft/verlinde-formula-preview/).

## Research status

The classification of WZW primaries by integrable highest weights and their Sugawara conformal weights is established for compact simple WZW models at positive integer level.

Active research uses these structures in broader settings: boundary WZW models, conformal defects, non-diagonal modular invariants, coset dualities, supergroup WZW models, logarithmic current algebras, and chiral algebras extracted from higher-dimensional quantum field theories.

## Exercises

### Exercise 1

For $SU(2)_3$, list the allowed WZW primary labels and compute their conformal weights.

<details><summary><strong>Solution</strong></summary>

For $SU(2)_k$, the allowed spins are

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

At $k=3$, this gives

$$
j=0,\frac12,1,\frac32.
$$

The weights are

$$
h_j=\frac{j(j+1)}{k+2}=\frac{j(j+1)}{5}.
$$

Thus

$$
h_0=0,
\qquad
h_{1/2}=\frac{3}{20},
\qquad
h_1=\frac25,
\qquad
h_{3/2}=\frac34.
$$

</details>

### Exercise 2

Explain why an affine primary is automatically a Virasoro primary for the Sugawara stress tensor.

<details><summary><strong>Solution</strong></summary>

The Sugawara stress tensor is built from current modes. Its positive Virasoro modes $L_n$ with $n>0$ contain terms with at least one positive current mode when acting on an affine highest-weight state. Since an affine primary satisfies

$$
J^a_m|\lambda\rangle=0
\qquad m>0,
$$

these positive Virasoro modes annihilate it:

$$
L_n|\lambda\rangle=0
\qquad n>0.
$$

Therefore the state is Virasoro primary. The converse need not hold.

</details>

### Exercise 3

Compute the conformal weight of the fundamental primary of $SU(3)_1$.

<details><summary><strong>Solution</strong></summary>

For $SU(N)_k$,

$$
h_{\rm fund}=\frac{N^2-1}{2N(k+N)}.
$$

For $N=3$ and $k=1$,

$$
h_{\rm fund}=\frac{9-1}{2\cdot3\cdot4}=\frac{8}{24}=\frac13.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- E. Witten, “Non-Abelian bosonization in two dimensions,” *Communications in Mathematical Physics* **92** (1984).
- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.

## Version history

- 2026-06-30: First polished draft. Added affine-primary definition, current-primary Ward identities, Sugawara conformal weights, $SU(2)_k$ and $SU(N)_k$ examples, fusion preview, exercises, and references.
