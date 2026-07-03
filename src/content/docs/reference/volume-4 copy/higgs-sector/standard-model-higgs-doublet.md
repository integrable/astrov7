---
title: "Standard Model Higgs Doublet"
description: "Defines the Standard Model Higgs doublet, its electroweak quantum numbers, neutral vacuum direction, and field decomposition into Goldstone and physical Higgs modes."
sidebar:
  label: "Standard Model Higgs Doublet"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - Standard Model Higgs doublet
  - electroweak symmetry breaking
  - weak isospin
  - hypercharge
  - Goldstone modes
canonicalTopics:
  - standard-model-higgs-doublet
  - electroweak-higgs-representation
  - higgs-vacuum-direction
  - goldstone-mode-counting
researchStatus:
  established:
    - "The minimal Standard Model contains one complex scalar electroweak doublet with hypercharge Y = 1/2; a neutral vacuum preserves U(1)em."
  active:
    - "Whether the observed scalar sector is truly minimal is tested through Higgs coupling measurements, self-coupling constraints, flavor structure, and SMEFT analyses."
---

## Summary

The Standard Model Higgs field is a complex scalar doublet under $SU(2)_L$ and has hypercharge $Y=1/2$ in the convention

$$
Q=T^3+Y.
$$

Ignoring color, it is

$$
H(x)=
\begin{pmatrix}
H^+(x)\\
H^0(x)
\end{pmatrix},
\qquad
H\sim(\mathbf 1,\mathbf 2)_{1/2}.
$$

The two components have weak isospin and electric charge

| component | $T^3$ | $Y$ | $Q=T^3+Y$ |
|---|---:|---:|---:|
| $H^+$ | $+1/2$ | $+1/2$ | $+1$ |
| $H^0$ | $-1/2$ | $+1/2$ | $0$ |

The electroweak vacuum is chosen in the neutral component,

$$
\langle H\rangle
=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v
\end{pmatrix},
$$

so the generator $Q=T^3+Y$ annihilates the vacuum. That is the compact reason the photon remains massless: electromagnetism is the gauge redundancy associated with the unbroken direction.

A useful linear parametrization around the vacuum is

$$
H(x)=
\begin{pmatrix}
G^+(x)\\
\dfrac{v+h(x)+iG^0(x)}{\sqrt2}
\end{pmatrix}.
$$

The fields $G^+$, $G^-$, and $G^0$ are would-be Goldstone modes. In a Higgs phase they become the longitudinal polarizations of $W^+$, $W^-$, and $Z$. The remaining real scalar $h$ is the physical Higgs boson.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Standard Model Higgs doublet quantum numbers, neutral vacuum, and Goldstone reorganization](/figures/gauge-theories-standard-model/standard-model-higgs-doublet-map.svg)

<figcaption>

The Standard Model Higgs doublet has one charged component and one neutral component. A vacuum in the neutral component preserves $Q=T^3+Y$, while the three broken electroweak directions are represented perturbatively by $G^\pm$ and $G^0$.

</figcaption>
</figure>

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/), and [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/). The counting of eaten Goldstone modes is explained in [Non-Abelian Higgs Mechanism](/gauge-theories-standard-model/higgs-sector/non-abelian-higgs-mechanism/).

This page fixes the representation-theoretic data of the Higgs field. The next page, [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/), explains why the vacuum has nonzero magnitude and how the physical Higgs mass arises at tree level.

## Core idea

The Standard Model needs a scalar field whose vacuum does exactly three things.

First, it must break

$$
SU(2)_L\times U(1)_Y
\longrightarrow
U(1)_{\rm em}
$$

without breaking electromagnetism. Therefore the vacuum must be electrically neutral.

Second, it must contain exactly three would-be Goldstone directions, because $W^+$, $W^-$, and $Z$ need longitudinal polarizations while the photon must remain massless.

Third, it must allow renormalizable Yukawa couplings to quarks and charged leptons. The same scalar representation that breaks the gauge group also lets the theory write gauge-invariant fermion mass terms after expanding around the vacuum.

A single complex doublet with $Y=1/2$ is the minimal representation that does all three jobs. It has four real scalar components: three become longitudinal gauge-boson modes, and one remains as the physical scalar $h$.

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'YB_\mu,
$$

so for the Higgs doublet

$$
D_\mu H
=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'\frac12B_\mu\right)H.
$$

Matter fields transform with the inverse representation, so locally

$$
H(x)\mapsto
\exp\!\left[-ig\alpha^a(x)\frac{\sigma^a}{2}-ig'\beta(x)\frac12\right]H(x).
$$

The weak-isospin generators are

$$
T^a=\frac{\sigma^a}{2},
\qquad
T^3=\frac12
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix}.
$$

With $Y=1/2$, the electric-charge operator on $H$ is

$$
Q=T^3+Y\mathbf 1_2
=
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix}.
$$

This is why the notation $H^+$ and $H^0$ is not decoration: the upper component has electric charge $+1$, and the lower component is neutral.

## Why the doublet has hypercharge one half

Suppose $H$ is an $SU(2)_L$ doublet with hypercharge $Y_H$. Its lower component has $T^3=-1/2$, so its electric charge is

$$
Q(H^0)=-\frac12+Y_H.
$$

For the vacuum to preserve electromagnetism, the component acquiring a vacuum expectation value must have $Q=0$. Therefore

$$
Y_H=\frac12.
$$

The upper component then has

$$
Q(H^+)=+\frac12+\frac12=+1.
$$

This also explains why the neutral representative is written in the lower component. Once the electromagnetic generator is named $Q=T^3+Y$, the lower component is the component annihilated by $Q$. Other nonzero doublet directions can be related by gauge choices, but the physical vacuum must preserve the electromagnetic generator that acts on all fields with the observed charges.

:::note[Convention translation]
Some books define hypercharge by $Q=T^3+Y/2$. In that convention the same Higgs doublet has $Y=1$ rather than $Y=1/2$. This volume uses $Q=T^3+Y$.
:::

## Vacuum direction and unbroken electromagnetism

Take

$$
H_0
=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v
\end{pmatrix}.
$$

The unbroken generator is the generator that annihilates $H_0$. Since

$$
T^3H_0=-\frac12H_0,
\qquad
YH_0=+\frac12H_0,
$$

we get

$$
QH_0=(T^3+Y)H_0=0.
$$

The other three electroweak directions move the vacuum. The charged generators

$$
T^\pm=T^1\pm iT^2
$$

connect the upper and lower components, while the neutral broken direction is the combination orthogonal to $Q$ in the gauge-boson mass matrix. After diagonalization, the gauge fields are organized as $W^\pm$, $Z$, and $A$.

The statement

$$
SU(2)_L\times U(1)_Y\to U(1)_{\rm em}
$$

therefore means: around this vacuum, the perturbative spectrum contains three massive weak bosons and one massless photon. It does not mean that gauge redundancy was literally destroyed.

## Field parametrizations

There are two common parametrizations. The linear parametrization is

$$
H(x)=
\begin{pmatrix}
G^+(x)\\
\dfrac{v+h(x)+iG^0(x)}{\sqrt2}
\end{pmatrix}.
$$

This is useful in renormalizable covariant gauges because the would-be Goldstone fields remain explicit. The fields $G^+$ and $G^-$ are complex conjugates, so together they represent two real degrees of freedom, while $G^0$ is one real degree of freedom.

For conceptual counting, an exponential parametrization is often cleaner:

$$
H(x)
=
\exp\!\left[-\frac{i}{v}\pi^a(x)\sigma^a\right]
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v+h(x)
\end{pmatrix}.
$$

The three fields $\pi^a$ lie along the gauge orbit through the vacuum. In unitary gauge, they are removed from $H$ by a gauge transformation, leaving

$$
H(x)=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\ v+h(x)
\end{pmatrix}.
$$

Unitary gauge is excellent for reading off the physical particle content. Covariant gauges are usually better for loop calculations because they keep ultraviolet behavior and renormalization power counting more transparent.

## Doublet data as a compact table

The minimal Higgs-sector data can be summarized as follows.

| Object | Value | Meaning |
|---|---:|---|
| color representation | $\mathbf 1$ | The Higgs field is color neutral. |
| weak representation | $\mathbf 2$ | The Higgs field is an $SU(2)_L$ doublet. |
| hypercharge | $Y=1/2$ | The lower component can be electrically neutral. |
| vacuum | $\langle H\rangle=(0,v/\sqrt2)^T$ | Preserves $U(1)_{\rm em}$. |
| real fields in $H$ | $4$ | One complex doublet contains four real components. |
| eaten fields | $3$ | Supply longitudinal modes of $W^\pm$ and $Z$. |
| physical scalar | $1$ | The Higgs boson $h$. |

The table is short, but it is doing a lot of work. The entire tree-level gauge and Higgs sector follows by inserting this field into

$$
\mathcal L_H=(D_\mu H)^\dagger(D^\mu H)-V(H).
$$

## Yukawa preview

The same doublet also makes charged-fermion masses possible. In four-component notation, the Standard Model Yukawa terms can be written schematically as

$$
\mathcal L_Y
=
-\bar Q_LY_dHd_R
-\bar Q_LY_u\widetilde H u_R
-\bar L_LY_eHe_R
+\text{h.c.},
$$

where

$$
\widetilde H=i\sigma^2H^*.
$$

Since $H$ has $Y=1/2$, the conjugate doublet $\widetilde H$ has $Y=-1/2$. This is why the up-type and down-type Yukawa couplings use different doublets built from the same field. After $H$ gets a vacuum expectation value, the Yukawa matrices become fermion mass matrices.

This is only a preview. Flavor physics begins when those Yukawa matrices are diagonalized, producing CKM mixing in the quark sector and, after adding neutrino masses, PMNS mixing in the lepton sector.

## Common pitfalls

**Calling the Higgs boson an electroweak doublet.** The field $H$ is an electroweak doublet. The physical Higgs boson $h$ is the neutral scalar excitation left after expanding around the vacuum and fixing the gauge.

**Forgetting the hypercharge convention.** In this volume $Q=T^3+Y$, so the Higgs doublet has $Y=1/2$. In the alternative convention $Q=T^3+Y/2$, the same physics is described by assigning the doublet $Y=1$.

**Thinking the photon is massless by accident.** The photon remains massless because the vacuum is annihilated by $Q=T^3+Y$. This is a representation-theoretic statement, not a numerical tuning.

**Confusing Goldstone fields with physical particles.** The fields $G^\pm$ and $G^0$ are useful perturbative fields in many gauges, but they are not massless physical particles in the Higgs phase of the gauge theory.

**Using unitary gauge too early.** Unitary gauge hides the Goldstone fields and displays the physical spectrum, but it can obscure Ward identities, high-energy behavior, and renormalization structure.

## Relations to other pages

- [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) introduced the same vacuum from the gauge-boson point of view.
- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) diagonalizes the gauge-boson basis after the neutral Higgs vacuum is chosen.
- [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/) explains the gauge-invariant potential whose minima have $H^\dagger H=v^2/2$.
- The planned Gauge Boson Masses page uses $|D_\mu H|^2$ to derive $m_W$ and $m_Z$.
- The planned Yukawa Couplings page uses $H$ and $\widetilde H$ to build fermion mass matrices.

## Research status

The one-doublet representation $H\sim(\mathbf 1,\mathbf 2)_{1/2}$ is textbook-standard and experimentally successful as the minimal scalar sector of the Standard Model. The conceptual subtleties are mostly about gauge redundancy, convention choices, and the distinction between the charged doublet field $H$ and the physical neutral scalar $h$.

The active physics lies in whether this minimal description is complete. Precision Higgs couplings, rare decays, the Higgs self-coupling, electroweak vacuum stability, extended scalar sectors, composite Higgs models, and SMEFT analyses are all ways of testing whether the observed scalar is exactly the minimal Higgs field or the low-energy remnant of a larger structure.

## Exercises

### Exercise 1: Check the component charges

Using $T^3=\operatorname{diag}(1/2,-1/2)$ and $Y=1/2$, compute the electric charges of the two components of $H$.

<details>
<summary><strong>Solution</strong></summary>

The charge operator is

$$
Q=T^3+Y\mathbf 1_2
=
\begin{pmatrix}
1/2&0\\
0&-1/2
\end{pmatrix}
+
\begin{pmatrix}
1/2&0\\
0&1/2
\end{pmatrix}
=
\begin{pmatrix}
1&0\\
0&0
\end{pmatrix}.
$$

Thus the upper component has charge $+1$ and the lower component has charge $0$.

</details>

### Exercise 2: Find the unbroken generator

Show that the vacuum $H_0=(0,v/\sqrt2)^T$ is annihilated by $Q=T^3+Y$ but not by $T^1$ or $T^2$.

<details>
<summary><strong>Solution</strong></summary>

For the neutral vacuum,

$$
T^3H_0=-\frac12H_0,
\qquad
YH_0=+\frac12H_0,
$$

so $(T^3+Y)H_0=0$. But

$$
T^1H_0=
\frac{v}{2\sqrt2}
\begin{pmatrix}
1\\0
\end{pmatrix},
\qquad
T^2H_0=
\frac{-iv}{2\sqrt2}
\begin{pmatrix}
1\\0
\end{pmatrix},
$$

which are nonzero. Therefore $T^1$ and $T^2$ move the vacuum and correspond to broken charged directions.

</details>

### Exercise 3: Count the real fields

Verify that the parametrization

$$
H=
\begin{pmatrix}
G^+\\
(v+h+iG^0)/\sqrt2
\end{pmatrix}
$$

contains four real scalar fields.

<details>
<summary><strong>Solution</strong></summary>

The complex field $G^+$ contains two real fields, with $G^-=(G^+)^*$ not independent. The neutral component contains the real field $h$ and the real field $G^0$. The constant $v$ is not a fluctuating field. Therefore the total is $2+1+1=4$ real scalar fields.

</details>

### Exercise 4: Hypercharge of the conjugate doublet

Show that $\widetilde H=i\sigma^2H^*$ has hypercharge $-1/2$ if $H$ has hypercharge $+1/2$.

<details>
<summary><strong>Solution</strong></summary>

Under a $U(1)_Y$ transformation in this convention,

$$
H\mapsto e^{-ig'\beta Y_H}H.
$$

Taking the complex conjugate gives

$$
H^*\mapsto e^{+ig'\beta Y_H}H^*.
$$

The matrix $i\sigma^2$ only converts the conjugate $SU(2)$ doublet back into a doublet; it does not change hypercharge. Thus $\widetilde H$ transforms as a doublet with hypercharge $-Y_H=-1/2$.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §87, for the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for the Higgs mechanism and electroweak symmetry breaking.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for a classic explanation of spontaneous symmetry breaking and the Higgs phenomenon.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and spontaneously broken gauge theories.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9, for the Standard Model as an effective theory and the role of the Higgs sector in the low-energy expansion.

## Version history

- **2026-06-18:** Initial standardized page.
