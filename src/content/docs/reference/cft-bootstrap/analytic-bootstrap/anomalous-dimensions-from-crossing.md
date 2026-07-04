---
title: "Anomalous Dimensions from Crossing"
description: "How crossed-channel low-twist exchange produces logarithms that determine large-spin anomalous dimensions of double-twist operators."
sidebar:
  label: "Anomalous Dimensions from Crossing"
  order: 4
level: Advanced
status: "Polished draft"
source: "Fitzpatrick, Kaplan, Poland, and Simmons-Duffin; Komargodski and Zhiboedov; Alday; Caron-Huot; Simmons-Duffin TASI lectures."
topics:
  - anomalous dimensions
  - analytic conformal bootstrap
  - crossing symmetry
  - large spin
  - double-twist operators
canonicalTopics:
  - anomalous-dimensions-from-crossing
  - low-twist-exchange
  - large-spin-anomalous-dimensions
researchStatus:
  established:
    - "Crossing symmetry relates low-twist exchange in one channel to anomalous dimensions and OPE coefficient corrections of large-spin double-twist operators in the crossed channel."
  active:
    - "Current work refines finite-spin continuation, mixing, spinning correlators, Lorentzian inversion, Regge constraints, and holographic loop-level anomalous dimensions."
---

## Summary

**Anomalous dimensions from crossing** are one of the central outputs of analytic bootstrap. Start with a double-twist family

$$
[\phi\phi]_{n,\ell},
\qquad
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell}.
$$

The lightcone bootstrap says

$$
\gamma_{n,\ell}\to0
\qquad
\ell\to\infty.
$$

Crossing symmetry then determines the leading large-spin behavior of $\gamma_{n,\ell}$ from the lowest-twist operators exchanged in the crossed channel. If a crossed-channel primary $\mathcal O_m$ has twist

$$
\tau_m=\Delta_m-\ell_m,
$$

then its leading contribution typically behaves schematically as

$$
\gamma_{n,\ell}^{(m)}\sim\frac{1}{J^{\tau_m}},
$$

where $J$ is the conformal spin. In many identical-scalar unitary channels, stress-tensor exchange gives a negative correction, interpreted as an attractive interaction between large-spin two-particle states.

The practical diagnostic is logarithms. Expanding a shifted dimension produces

$$
u^{\Delta_{n,\ell}/2}
=
u^{\Delta_{n,\ell}^{(0)}/2}
\left(1+\frac{\gamma_{n,\ell}}2\log u+\cdots\right).
$$

Thus the coefficient of $\log u$ in one channel encodes anomalous dimensions forced by crossed-channel exchange.

## Prerequisites

Read [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/), [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/), and [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/) first.

You should know the reduced four-point function, conformal block expansion, twist,

$$
\tau=\Delta-\ell,
$$

and the double-twist mean-field dimensions

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell
$$

for identical scalar external operators.

## Core idea

Crossing relates singularities in different channels. A low-twist operator in the crossed channel produces a distinctive singular term. The direct channel reproduces that term by summing over many large-spin double-twist operators.

The anomalous dimension appears because the double-twist dimensions are not exactly mean-field values:

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\gamma_{n,\ell}.
$$

When the conformal block expansion is expanded in small $\gamma_{n,\ell}$, the shift produces logarithms:

$$
G_{\Delta_{n,\ell},\ell}
=G_{\Delta_{n,\ell}^{(0)},\ell}
+\gamma_{n,\ell}\,\partial_\Delta G_{\Delta,
\ell}\big|_{\Delta=\Delta_{n,\ell}^{(0)}}+\cdots .
$$

Since conformal blocks contain powers of $u$, the derivative term contains $\log u$. Therefore matching logarithms determines $\gamma_{n,\ell}$.

The slogan is

$$
\text{crossed-channel singularity}
\quad\Longleftrightarrow\quad
\text{direct-channel anomalous dimensions}.
$$

This is the analytic-bootstrap analogue of reading anomalous dimensions from perturbative logarithms in ordinary QFT.

## Setup and conventions

Consider identical scalar primaries $\phi$ of dimension $\Delta_\phi$ in a unitary CFT. Write

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v),
$$

with

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The $12\to34$ channel expansion is

$$
\mathcal G(u,v)
=1+\sum_{n,\ell}a_{n,\ell}G_{\Delta_{n,\ell},\ell}(u,v)+\cdots,
$$

where $a_{n,\ell}=\lambda_{\phi\phi[\phi\phi]_{n,\ell}}^2$ in a unitary identical-scalar normalization.

At large spin,

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

and

$$
a_{n,\ell}=a_{n,\ell}^{(0)}\left(1+\delta a_{n,\ell}+\cdots\right).
$$

The crossed channel contains the identity plus non-identity primaries:

$$
\mathcal O_m,
\qquad
\tau_m=\Delta_m-\ell_m.
$$

The identity fixes the mean-field skeleton. The non-identity low-twist operators produce anomalous dimensions and OPE coefficient corrections.

## The logarithm mechanism

The simplest way to see anomalous dimensions is to focus on the leading small-$u$ power. A direct-channel block for a spin-$\ell$ operator of dimension $\Delta$ begins schematically as

$$
G_{\Delta,\ell}(u,v)\sim u^{(\Delta-\ell)/2}\times(\text{function of }v)+\cdots .
$$

For the double-twist family,

$$
\Delta_{n,\ell}-\ell=2\Delta_\phi+2n+\gamma_{n,\ell}.
$$

Therefore

$$
u^{(\Delta_{n,\ell}-\ell)/2}
=u^{\Delta_\phi+n}\left(1+\frac{\gamma_{n,\ell}}2\log u+\cdots\right).
$$

The coefficient of $\log u$ in the direct-channel expansion is proportional to

$$
a_{n,\ell}^{(0)}\gamma_{n,\ell}.
$$

Crossing tells us what this logarithmic term must be. Once the crossed-channel low-twist contribution is expanded in the direct-channel lightcone limit, the matching condition determines $\gamma_{n,\ell}$.

This is why analytic-bootstrap calculations often separate a correlator into logarithmic and non-logarithmic pieces. The log part is the anomalous-dimension detector.

## Crossed-channel low-twist exchange

Suppose a crossed-channel operator $\mathcal O_m$ has twist $\tau_m$ and spin $\ell_m$. Its contribution near the crossed-channel lightcone limit behaves like a power controlled by $\tau_m$. In the direct-channel large-spin sum, this becomes a correction of the form

$$
\gamma_{n,\ell}^{(m)}
=\frac{1}{J^{\tau_m}}
\left(c_{0,n}^{(m)}+\frac{c_{1,n}^{(m)}}{J^2}+\frac{c_{2,n}^{(m)}}{J^4}+\cdots\right),
$$

in common parity-even situations.

The coefficients

$$
c_{k,n}^{(m)}
$$

depend on the external dimensions, the exchanged operator's dimension and spin, the OPE coefficient $\lambda_{\phi\phi m}$, spacetime dimension, and block normalization.

The qualitative hierarchy is universal:

$$
\text{smaller crossed-channel twist}
\quad\Rightarrow\quad
\text{larger large-spin effect}.
$$

Thus the identity gives the leading mean-field data, and the lowest non-identity twist controls the leading anomalous dimensions.

## Conformal spin expansion

For identical external scalars, a useful large-spin variable is

$$
J^2=\left(\ell+\Delta_\phi+n+\frac{\gamma_{n,\ell}}2\right)
\left(\ell+\Delta_\phi+n-1+\frac{\gamma_{n,\ell}}2\right).
$$

At leading order,

$$
J^2=(\ell+\Delta_\phi+n)(\ell+\Delta_\phi+n-1)+O(\gamma).
$$

Using $J$ rather than $\ell$ makes the expansion align with the conformal Casimir. Many results naturally organize as powers of

$$
\frac{1}{J^{\tau_m+2k}}.
$$

The $2k$ step is not a law of nature in every possible setup. It is a common structure in parity-even scalar systems. Spinning operators, global symmetry, degeneracies, or special dimensions can modify the pattern.

## Stress-tensor exchange

Every local CFT has a stress tensor with

$$
\Delta_T=d,
\qquad
\ell_T=2,
\qquad
\tau_T=d-2.
$$

Therefore stress-tensor exchange gives a universal contribution to large-spin double-twist anomalous dimensions of order

$$
\gamma_{n,\ell}^{(T)}\sim -\frac{\text{const}}{J^{d-2}}
$$

in many identical-scalar channels.

The coefficient depends on the scalar dimension and the stress-tensor two-point normalization $C_T$, because the Ward identity fixes

$$
\lambda_{\phi\phi T}^2\propto \frac{\Delta_\phi^2}{C_T}
$$

up to conventions.

The negative sign is often interpreted as gravitational attraction in holographic theories. In general CFT language, it is tied to positivity, causality, and the universal role of the stress tensor. For exact formulas, one must specify block normalization and the convention for $C_T$.

## Scalar exchange

If the crossed channel contains a scalar $s$ of dimension

$$
\Delta_s
$$

and spin zero, then its twist is

$$
\tau_s=\Delta_s.
$$

Its leading large-spin contribution scales like

$$
\gamma_{n,\ell}^{(s)}\sim -\frac{\lambda_{\phi\phi s}^2\,K_{n,s}}{J^{\Delta_s}}
$$

in many identical-scalar setups, with $K_{n,s}$ positive in common unitary conventions.

If

$$
\Delta_s<d-2,
$$

then scalar exchange dominates stress-tensor exchange at large spin. This happens in many critical theories, where a low-dimension scalar appears in the OPE.

Thus the leading anomalous dimension is not always controlled by the stress tensor. It is controlled by the lowest non-identity twist that actually appears in the relevant crossed channel.

## Conserved-current exchange

If $\phi$ transforms under a global symmetry, a conserved current may appear. A conserved spin-one current has

$$
\Delta_J=d-1,
\qquad
\ell_J=1,
\qquad
\tau_J=d-2.
$$

Its large-spin correction also scales as

$$
\frac{1}{J^{d-2}}.
$$

Unlike the stress-tensor contribution, the sign and coefficient depend strongly on representation channel. For example, two charged operators can form singlet or non-singlet double-twist families, and current exchange can be attractive in one channel and repulsive in another.

This is an important lesson: anomalous dimensions are sector-dependent. Once global symmetry is present, one must track representation labels, not only $n$ and $\ell$.

## OPE coefficient corrections

Anomalous dimensions are only half the story. The same crossed-channel exchange also corrects OPE coefficients:

$$
a_{n,\ell}=a_{n,\ell}^{(0)}\left(1+\delta a_{n,\ell}\right).
$$

Expanding the direct-channel contribution gives

$$
a_{n,\ell}G_{\Delta_{n,\ell},\ell}
=
a_{n,\ell}^{(0)}G_{\Delta_{n,\ell}^{(0)},\ell}
+a_{n,\ell}^{(0)}\delta a_{n,\ell}G_{\Delta_{n,\ell}^{(0)},\ell}
+a_{n,\ell}^{(0)}\gamma_{n,\ell}\partial_\Delta G_{\Delta,\ell}\big|_{\Delta=\Delta_{n,\ell}^{(0)}}+\cdots .
$$

The derivative term contains the logarithm. The regular term contains a combination of $\delta a_{n,\ell}$ and non-logarithmic pieces induced by $\gamma_{n,\ell}$.

Therefore extracting OPE coefficient corrections requires more bookkeeping than extracting anomalous dimensions. It is also more normalization-dependent.

## Mixing

The formula

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell}
$$

assumes a single identifiable family. If several operators have the same spin, representation, and mean-field twist, crossing determines a matrix of anomalous dimensions rather than a single number.

Suppose the naive double-twist basis is

$$
\{[\mathcal O_a\mathcal O_b]_{n,\ell}\}.
$$

Then interactions can produce

$$
\Gamma_{AB}(n,\ell),
$$

whose eigenvalues are the actual anomalous dimensions. The exact primaries are eigenvectors.

Mixing is common in large-$N$ theories with several single-trace operators, in theories with global symmetry, and in supersymmetric systems. Ignoring mixing can give a formula that is algebraically clean but physically mislabeled.

## Holographic interpretation

In a holographic CFT, a double-twist operator is a two-particle state in global AdS. The anomalous dimension is the binding energy:

$$
\gamma_{n,\ell}=E_{\rm interacting}-E_{\rm free}.
$$

Large spin corresponds to large impact parameter, so the interaction is weak. The exchanged low-twist operator is a bulk field mediating a long-range force.

| CFT exchange | Bulk interpretation | Large-spin effect |
|---|---|---|
| stress tensor | graviton exchange | gravitational binding |
| conserved current | gauge-boson exchange | charge-dependent force |
| scalar primary | scalar force | channel-dependent binding |
| higher-spin current | higher-spin field | strong constraints or near-free behavior |

The scaling

$$
\gamma_{n,\ell}\sim J^{-\tau_m}
$$

is the CFT version of a long-distance potential falloff controlled by the exchanged field.

## Relation to Lorentzian inversion

The Lorentzian inversion formula turns this matching logic into a systematic reconstruction method. Instead of manually matching lightcone singularities, one computes a function of dimension and spin from the double discontinuity:

$$
c(\Delta,\ell)\sim \int dz\,d\bar z\; \operatorname{dDisc}[\mathcal G(z,\bar z)]\times \text{kernel}.
$$

The poles of $c(\Delta,\ell)$ encode dimensions and OPE coefficients. Expanding those poles at large spin reproduces the anomalous dimensions described here.

In this sense, lightcone matching is the intuitive method, and Lorentzian inversion is the industrial machine. Both express the same idea: crossed-channel data determine direct-channel large-spin data.

## Common pitfalls

**Do not confuse the power with the coefficient.** The twist $\tau_m$ fixes the leading power $J^{-\tau_m}$, but the coefficient depends on OPE coefficients, spin, dimensions, and normalization.

**Do not assume the stress tensor always dominates.** A lower-twist scalar or current in the relevant channel can dominate.

**Do not quote signs without specifying the channel.** Global symmetry and operator representations can flip the sign of anomalous dimensions.

**Do not treat logarithms as optional.** The $\log u$ term is the cleanest signal of anomalous dimensions in the direct-channel expansion.

**Do not ignore mixing.** Degenerate double-twist families require anomalous-dimension matrices.

**Do not extrapolate blindly to low spin.** Large-spin anomalous dimensions are asymptotic data unless further arguments control finite spin.

**Do not forget normalization conventions.** Exact coefficients depend on conformal block and two-point-function normalizations.

## Relations to other pages

This page follows [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/) and prepares [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/).

It also connects to [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/), and [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/), because low-twist conserved operators control universal large-spin tails.

For large-$N$ and AdS interpretations, see [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), and [Holographic CFT](/cft-bootstrap/holographic-cft/).

## Research status

The extraction of large-spin anomalous dimensions from crossed-channel low-twist exchange is established. It is a core result of the lightcone and analytic bootstrap.

Active work studies exact finite-spin reconstruction, mixing, spinning external operators, nonunitary cases, thermal and defect analogues, loop-level holographic correlators, Regge constraints, and how analytic large-spin data improve numerical bootstrap computations.

## Exercises

### Exercise 1

Show how a small anomalous dimension produces a logarithm in the direct-channel OPE.

<details><summary><strong>Solution</strong></summary>

Let

$$
\Delta=\Delta^{(0)}+\gamma.
$$

Then

$$
u^{\Delta/2}=u^{\Delta^{(0)}/2}\exp\left(\frac{\gamma}{2}\log u\right).
$$

For small $\gamma$,

$$
u^{\Delta/2}=u^{\Delta^{(0)}/2}
\left(1+\frac{\gamma}{2}\log u+\cdots\right).
$$

Thus the coefficient of $\log u$ is proportional to the anomalous dimension.

</details>

### Exercise 2

If the leading crossed-channel non-identity operator has twist $\tau_m$, what is the leading large-spin scaling of its contribution to $\gamma_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

At large conformal spin $J$, the leading contribution scales as

$$
\gamma_{n,\ell}^{(m)}\sim J^{-\tau_m},
$$

up to a coefficient depending on OPE data, spacetime dimension, spin, external dimensions, and normalization.

</details>

### Exercise 3

What is the stress-tensor twist in $d$ dimensions, and what large-spin power does it generate?

<details><summary><strong>Solution</strong></summary>

The stress tensor has

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

Therefore its twist is

$$
\tau_T=d-2.
$$

It generates large-spin corrections scaling as

$$
\gamma_{n,\ell}^{(T)}\sim J^{-(d-2)}.
$$

</details>

### Exercise 4

Why are OPE coefficient corrections harder to extract than anomalous dimensions?

<details><summary><strong>Solution</strong></summary>

Anomalous dimensions multiply derivatives of conformal blocks with respect to $\Delta$, producing logarithms such as $\log u$. These logarithms are easy to isolate. OPE coefficient corrections contribute to non-logarithmic terms, which mix with regular terms generated by the anomalous-dimension expansion. They also depend more directly on block and operator normalization conventions.

</details>

### Exercise 5

Why can global symmetry change the sign of anomalous dimensions?

<details><summary><strong>Solution</strong></summary>

With global symmetry, double-twist operators live in representation sectors. Current exchange and other charged exchanges carry group-theory factors that differ by sector. These factors can be positive in one channel and negative in another, so the same exchanged operator can produce attractive corrections in one representation and repulsive corrections in another.

</details>

## References

- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- Z. Komargodski and A. Zhiboedov, “Convexity and liberation at large spin,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added logarithm mechanism, low-twist exchange scaling, conformal-spin expansion, stress-tensor, scalar, and current examples, OPE coefficient corrections, mixing, holographic interpretation, exercises, and references.
