---
title: "Mixed-Correlator Bootstrap"
description: "How several external primaries turn crossing into matrix-valued semidefinite constraints and isolate CFT data more sharply than one correlator can."
sidebar:
  label: "Mixed-Correlator Bootstrap"
  order: 6
level: Graduate
status: "Polished draft"
source: "Kos–Poland–Simmons-Duffin 2014; Kos–Poland–Simmons-Duffin–Vichi 2016; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - mixed correlators
  - semidefinite programming
  - positive semidefinite matrices
  - Ising bootstrap
  - global symmetry
  - bootstrap islands
canonicalTopics:
  - mixed-correlator-bootstrap
  - semidefinite-bootstrap
  - matrix-positivity
  - bootstrap-islands
researchStatus:
  established:
    - "Mixed-correlator bootstrap systems combine several four-point functions and upgrade scalar OPE positivity to positive semidefinite matrix positivity."
    - "Mixed-correlator methods are essential for isolating small allowed regions for theories such as the three-dimensional Ising and O(N) CFTs."
  active:
    - "Current work continues to improve mixed-correlator searches using better block technology, rigorous error control, navigator methods, skydive-type algorithms, and larger external operator systems."
---

## Summary

The mixed-correlator bootstrap studies several four-point functions at once. Instead of bootstrapping only

$$
\langle \phi\phi\phi\phi\rangle,
$$

one might bootstrap, for example,

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle,
\qquad
\langle \sigma\epsilon\sigma\epsilon\rangle.
$$

The reward is that the same exchanged operator can appear in several OPEs. Its OPE coefficients become a vector, and its contribution becomes a positive semidefinite matrix.

For a schematic even operator $\mathcal O^+$ appearing in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$,

$$
\vec\lambda_{\mathcal O^+}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix},
\qquad
\vec\lambda_{\mathcal O^+}\vec\lambda_{\mathcal O^+}^{\,T}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}^2 & \lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}\\
\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O} & \lambda_{\epsilon\epsilon\mathcal O}^2
\end{pmatrix}
\succeq0.
$$

This matrix positivity is the reason mixed-correlator bootstrap can produce small allowed islands in parameter space. It correlates the data of different OPEs instead of letting each four-point function choose its own spectrum independently.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Mixed-correlator bootstrap matrix positivity](/figures/cft-bootstrap/mixed-correlator-matrix-positivity.svg)

<figcaption>

Mixed correlators couple several OPEs to the same exchanged multiplets. A single exchanged operator contributes an outer product of OPE-coefficient vectors, so positivity becomes positive semidefiniteness of matrices. This extra structure can shrink broad bounds into islands.

</figcaption>
</figure>

## Prerequisites

You should know [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), [Four-Point Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/four-point-bootstrap/), [Spinning Conformal Blocks](/cft-bootstrap/conformal-blocks/spinning-conformal-blocks/), and [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) if global symmetries are involved.

This page explains the conceptual structure of mixed-correlator bootstrap equations. Detailed SDPB input generation, block tables, precision choices, and large-scale search algorithms belong in [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) and [Computational CFT and Bootstrap](/cft-bootstrap/computational-cft-bootstrap/).

## Core idea

A single identical correlator constrains one OPE. A mixed-correlator system constrains several OPEs and their mutual compatibility.

The important new facts are:

| Single identical scalar | Mixed correlators |
|---|---|
| One external operator. | Several external operators. |
| Coefficients appear as $\lambda^2\ge0$. | Coefficients appear as matrices $P\succeq0$. |
| Crossing vectors are scalar-valued. | Crossing vectors are often matrix-valued or vector-valued matrices. |
| Gives useful bounds and kinks. | Can give small islands and correlated spectra. |

The slogan is

$$
\text{mixed bootstrap}
=
\text{crossing for many correlators}
+
\text{shared CFT data}
+
\text{matrix positivity}.
$$

The “shared CFT data” part is what matters. The operator $\mathcal O$ appearing in $\phi_i\times\phi_j$ is the same operator when it appears in $\phi_k\times\phi_l$. Its dimension and spin cannot secretly change from one correlator to another.

## Setup and conventions

Let $\phi_i$ be a finite set of scalar primaries, chosen with diagonal two-point normalization

$$
\langle \phi_i(x)\phi_j(0)\rangle
=
\frac{\delta_{ij}}{(x^2)^{\Delta_i}}
$$

for real neutral fields. More generally, $i,j$ may also label global-symmetry representations, in which case the two-point metric should first be put in a positive orthonormal basis when possible.

The OPE has coefficients

$$
\phi_i\times\phi_j
\sim
\sum_{\mathcal O}
\lambda_{ij\mathcal O}\,\mathcal O.
$$

A four-point function

$$
\langle \phi_i\phi_j\phi_k\phi_l\rangle
$$

can be expanded in the $ij\to kl$ channel as

$$
\sum_{\mathcal O}
\lambda_{ij\mathcal O}\lambda_{kl\mathcal O}
G^{ij,kl}_{\Delta,\ell}(U,V),
$$

with external-dimension-dependent blocks and possible tensor or group-theory structures. Crossing compares this expansion with another channel, such as $il\to kj$.

For fixed quantum numbers of $\mathcal O$, collect all relevant OPE coefficients into a vector

$$
\vec\lambda_{\mathcal O}
=
(\lambda_{i_1j_1\mathcal O},\lambda_{i_2j_2\mathcal O},\ldots)^T.
$$

Then the contribution of $\mathcal O$ to crossing can be written schematically as

$$
\vec\lambda_{\mathcal O}^{\,T}
\mathbf V_{\Delta,\ell}
\vec\lambda_{\mathcal O}
=
\operatorname{Tr}
\left(
P_{\mathcal O}\,\mathbf V_{\Delta,\ell}
\right),
\qquad
P_{\mathcal O}=\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}\succeq0.
$$

Here $\mathbf V_{\Delta,\ell}$ is a matrix of crossing-vector functions. The exact size of the matrix depends on the chosen external operators and symmetry sectors.

## The Ising-style two-scalar system

The cleanest example is a theory with a $Z_2$ symmetry and two low-lying scalar primaries:

$$
\sigma\quad Z_2\text{-odd},
\qquad
\epsilon\quad Z_2\text{-even}.
$$

The selection rules are

$$
\sigma\times\sigma \sim Z_2\text{-even},
\qquad
\epsilon\times\epsilon \sim Z_2\text{-even},
\qquad
\sigma\times\epsilon \sim Z_2\text{-odd}.
$$

Thus an even operator $\mathcal O^+$ can appear in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$, with coefficient vector

$$
\vec\lambda_{\mathcal O^+}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O^+}\\
\lambda_{\epsilon\epsilon\mathcal O^+}
\end{pmatrix}.
$$

An odd operator $\mathcal O^-$ appears in $\sigma\times\epsilon$, with coefficient $\lambda_{\sigma\epsilon\mathcal O^-}$.

The crossing equations can be written schematically as

$$
\vec V_{\mathbf 1}
+
\sum_{\mathcal O^+}
\operatorname{Tr}
\left(
P_{\mathcal O^+}\,\vec V^{+}_{\Delta,\ell}
\right)
+
\sum_{\mathcal O^-}
\lambda_{\sigma\epsilon\mathcal O^-}^2
\vec V^{-}_{\Delta,\ell}
=0,
$$

where

$$
P_{\mathcal O^+}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O^+}^2
&
\lambda_{\sigma\sigma\mathcal O^+}\lambda_{\epsilon\epsilon\mathcal O^+}\\
\lambda_{\sigma\sigma\mathcal O^+}\lambda_{\epsilon\epsilon\mathcal O^+}
&
\lambda_{\epsilon\epsilon\mathcal O^+}^2
\end{pmatrix}
\succeq0.
$$

This one matrix is the beating heart of the mixed Ising bootstrap. The even sector cannot independently tune the $\sigma\sigma$ and $\epsilon\epsilon$ OPE data in different correlators. It must use the same operator with the same coefficient vector.

## Why mixed correlators sharpen bounds

Suppose one only bootstraps $\langle \sigma\sigma\sigma\sigma\rangle$. Then the even-sector coefficients appear as

$$
\lambda_{\sigma\sigma\mathcal O^+}^2.
$$

If one only bootstraps $\langle \epsilon\epsilon\epsilon\epsilon\rangle$, the same even operators appear with

$$
\lambda_{\epsilon\epsilon\mathcal O^+}^2.
$$

A single-correlator analysis does not fully enforce that these are coefficients of the same exchanged operator spectrum. A mixed analysis does. It also includes mixed correlators, which contain products such as

$$
\lambda_{\sigma\sigma\mathcal O^+}\lambda_{\epsilon\epsilon\mathcal O^+}.
$$

These signs and products matter. They encode relative OPE information that is invisible in a single squared coefficient.

This is why mixed correlators often turn a broad allowed band into a small region. They ask not merely whether each correlator can be made crossing symmetric, but whether one common CFT can make all of them crossing symmetric at once.

## Matrix-valued linear functionals

In a single-correlator problem, a functional $\alpha$ maps a crossing vector to a number. In a mixed-correlator problem, it often maps a matrix-valued crossing vector to a matrix:

$$
\alpha[\mathbf V_{\Delta,\ell}]
=
\text{a real symmetric matrix}.
$$

To certify exclusion, one demands

$$
\alpha(\vec V_{\mathbf 1})>0,
$$

and, for every allowed exchanged operator,

$$
\alpha[\mathbf V_{\Delta,\ell}]\succeq0.
$$

Then each matrix contribution is nonnegative because

$$
\operatorname{Tr}
\left(
P_{\mathcal O}\,\alpha[\mathbf V_{\Delta,\ell}]
\right)
\ge0
$$

whenever

$$
P_{\mathcal O}\succeq0,
\qquad
\alpha[\mathbf V_{\Delta,\ell}]\succeq0.
$$

This is the route from mixed crossing equations to semidefinite programming. The semidefinite condition is not a numerical trick. It is Hilbert-space positivity written in the language of OPE coefficient vectors.

## External dimensions and islands

Mixed-correlator searches often scan over several external dimensions. In the $Z_2$ two-scalar example, the natural plane is

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

For each point in this plane, impose assumptions such as:

- $\sigma$ is the lowest $Z_2$-odd scalar;
- $\epsilon$ is the lowest $Z_2$-even scalar after the identity;
- the next $Z_2$-odd scalar has dimension above a gap;
- the next $Z_2$-even scalar has dimension above a gap;
- the theory has a unique stress tensor;
- global-symmetry currents or relevant deformations are present or absent as appropriate.

Then one asks which points survive the mixed crossing equations. With enough correlators and well-chosen gaps, the allowed region can become a compact island.

An island is stronger than a kink because it constrains more than one parameter and usually uses more data. But it still remains conditional on assumptions and numerical control. The correct reading is:

> Under the stated assumptions and numerical precision, any CFT satisfying the system must lie in this allowed region.

It is not automatically a constructive proof that every point in the island is realized.

## Global symmetry channels

Mixed-correlator logic is not limited to $Z_2$. If a scalar $\phi_i$ transforms in a representation of a global symmetry group $G$, then $\phi_i\times\phi_j$ decomposes into irreducible representations. For an $O(N)$ vector,

$$
\phi_i\times\phi_j
\sim
S^+\oplus T^+\oplus A^-.
$$

Here $S$ is the singlet, $T$ is the symmetric traceless representation, and $A$ is the antisymmetric representation. The superscript reminds us of the spin parity for identical bosonic external fields: singlet and symmetric-traceless channels contain even spins, while the antisymmetric channel contains odd spins.

A mixed $O(N)$ bootstrap may add a singlet scalar $s$, a traceless scalar $t_{ij}$, a current $J_\mu^{[ij]}$, or the stress tensor. Each additional external operator increases the number of correlators and the number of coefficient vectors. The equations get larger, but the CFT data become more tightly coupled.

The same idea applies to supersymmetric multiplets, conserved currents, stress tensors, defects, and spinning external operators. The labels and tensor structures become more elaborate, but the core principle remains: one theory, one spectrum, one set of OPE coefficients, many crossing equations.

## Choosing assumptions

A mixed-correlator bootstrap is only as transparent as its assumptions. Important assumptions include:

| Assumption | Example | Why it matters |
|---|---|---|
| External spectrum | $\sigma$ and $\epsilon$ are the lowest odd/even scalars | Prevents the search from drifting to another theory. |
| Gap assumptions | $\Delta_{\epsilon'}\ge \Delta_*$ | Shrinks allowed regions and encodes physical input. |
| Stress tensor uniqueness | one spin-two operator at $\Delta=d$ | Excludes decoupled products of CFTs. |
| Current assumptions | one current or no current in a channel | Encodes global symmetry. |
| OPE sign conventions | choose one coefficient positive | Makes relative signs meaningful. |
| Degeneracy assumptions | no accidental degeneracy below a gap | Simplifies matrix interpretation. |

These assumptions are not embarrassing. They are the way a bootstrap problem becomes a precise theorem-like statement. The danger is not using assumptions; the danger is hiding them.

## Degeneracies and basis choices

If several primaries share the same dimension, spin, and symmetry representation, OPE coefficients become basis-dependent inside the degenerate subspace. The positive matrix

$$
P=\sum_a \vec\lambda_a\vec\lambda_a^{\,T}
$$

is basis-independent, while the individual vectors $\vec\lambda_a$ are not.

This is why semidefinite programming naturally allows general positive semidefinite matrices, not only rank-one outer products. A physical CFT contributes a sum of rank-one matrices from possibly degenerate operators, and the sum is positive semidefinite.

In practice, allowing arbitrary positive semidefinite matrices can also be viewed as a relaxation. Under mild conditions it is the correct closure of the physical possibility, but extracting individual OPE vectors from a numerical solution requires care.

## What mixed bootstrap can prove

A well-controlled mixed-correlator exclusion can prove that no unitary CFT satisfying the stated assumptions exists at a chosen point in external-dimension and gap space. It can also bound dimensions, OPE coefficients, central charges, current central charges, and ratios of OPE coefficients.

A mixed-correlator island can give a precise allowed region for a target CFT's data. With convergence tests and independent checks, this can become a very high-precision determination of CFT data.

What it cannot do by itself is explain the microscopic origin of the CFT, prove that a particular lattice model flows to it, or construct all higher-point correlators. Those statements require additional physics or mathematical input.

## Common pitfalls

**Forgetting shared spectra.** The point of mixed correlators is that the same operator appears in several OPEs. Treating each correlator as if it has an independent spectrum throws away the main advantage.

**Replacing matrix positivity by entrywise positivity.** A positive semidefinite matrix is not the same as a matrix with all entries positive. The correct condition is

$$
v^T P v\ge0
$$

for every real vector $v$.

**Ignoring relative signs.** In mixed systems, signs of products like $\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}$ are meaningful after conventions are fixed. They can affect crossing strongly.

**Calling every small region an island.** A robust island should be stable under increasing derivative order, improving precision, and varying reasonable implementation choices.

**Hiding gap assumptions.** Many striking mixed-correlator results rely on physically motivated gaps. The assumptions should be stated on the same page as the conclusion.

**Confusing a numerical island with a Lagrangian derivation.** The bootstrap constrains or solves CFT data nonperturbatively. It does not necessarily identify a microscopic model unless that model is separately argued to flow to the CFT.

## Relations to other pages

- [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/) gives the single-correlator prototype.
- [Gaps and Assumptions](/cft-bootstrap/crossing-bootstrap-logic/gaps-and-assumptions/) explains how assumptions shape allowed regions.
- [Islands in Parameter Space](/cft-bootstrap/crossing-bootstrap-logic/islands-in-parameter-space/) develops the geometry and interpretation of islands.
- [Extremal Functional Method](/cft-bootstrap/crossing-bootstrap-logic/extremal-functional-method/) discusses spectrum extraction at boundaries.
- [Mixed-Correlator Numerics](/cft-bootstrap/numerical-bootstrap/mixed-correlator-numerics/) explains the computational implementation.
- [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) records the canonical application.

## Research status

Mixed-correlator bootstrap is established as the standard route from qualitative bounds to precision CFT data in many higher-dimensional bootstrap problems. It is essential for isolating small regions because it ties multiple OPEs to the same exchanged operators.

The frontier is not the concept of matrix positivity itself, but scale and control: larger operator systems, spinning correlators, stress-tensor and current correlators, non-Abelian global symmetries, supersymmetric constraints, rigorous numerics, navigator functions, skydive-type searches, and reliable spectrum extraction from high-dimensional allowed regions.

## Exercises

### Exercise 1: Outer products are positive

Let

$$
\vec\lambda=\begin{pmatrix}a\\ b\end{pmatrix}.
$$

Show that

$$
P=\vec\lambda\vec\lambda^{\,T}
$$

is positive semidefinite.

<details><summary><strong>Solution</strong></summary>

For any real vector

$$
\vec v=\begin{pmatrix}x\\ y\end{pmatrix},
$$

we have

$$
\vec v^{\,T}P\vec v
=
\vec v^{\,T}\vec\lambda\vec\lambda^{\,T}\vec v
=
(\vec\lambda^{\,T}\vec v)^2
=
(ax+by)^2
\ge0.
$$

Therefore $P\succeq0$.

</details>

### Exercise 2: Even and odd sectors in the Z₂ system

Let $\sigma$ be $Z_2$-odd and $\epsilon$ be $Z_2$-even. Determine the $Z_2$ parity of operators in $\sigma\times\sigma$, $\epsilon\times\epsilon$, and $\sigma\times\epsilon$.

<details><summary><strong>Solution</strong></summary>

The parity of an OPE channel is the product of the parities of the external operators. Thus

$$
(-)\times(-)=+,
\qquad
(+)\times(+)=+,
\qquad
(-)\times(+)=-.
$$

So $\sigma\times\sigma$ and $\epsilon\times\epsilon$ contain $Z_2$-even operators, while $\sigma\times\epsilon$ contains $Z_2$-odd operators.

</details>

### Exercise 3: Why one even operator gives a matrix

Suppose an even operator $\mathcal O^+$ appears in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$. Explain why its contribution depends on the products $\lambda_{\sigma\sigma\mathcal O}^2$, $\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}$, and $\lambda_{\epsilon\epsilon\mathcal O}^2$.

<details><summary><strong>Solution</strong></summary>

In a four-point function, an exchanged operator contributes with one OPE coefficient from the left pair and one from the right pair. For example, in the $12\to34$ channel,

$$
\langle \sigma\sigma\epsilon\epsilon\rangle
$$

contains the product

$$
\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}.
$$

The correlator $\langle \sigma\sigma\sigma\sigma\rangle$ contains $\lambda_{\sigma\sigma\mathcal O}^2$, while $\langle \epsilon\epsilon\epsilon\epsilon\rangle$ contains $\lambda_{\epsilon\epsilon\mathcal O}^2$. These three products are entries of the outer-product matrix

$$
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}^2
&
\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}\\
\lambda_{\sigma\sigma\mathcal O}\lambda_{\epsilon\epsilon\mathcal O}
&
\lambda_{\epsilon\epsilon\mathcal O}^2
\end{pmatrix}.
$$

</details>

## References

- F. Kos, D. Poland, and D. Simmons-Duffin, “Bootstrapping Mixed Correlators in the 3D Ising Model,” *JHEP* **1411** (2014), arXiv:1406.4858.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision Islands in the Ising and O(N) Models,” *JHEP* **1608** (2016), arXiv:1603.04436.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs in Physics, 2016.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI 2015 lectures, arXiv:1602.07982.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” arXiv:2311.15844.

## Version history

- 2026-06-28: First polished draft. Introduces mixed-correlator crossing, OPE-coefficient vectors, positive semidefinite matrices, the $Z_2$ two-scalar example, islands, global-symmetry sectors, assumptions, and matrix-valued functional certificates.
