---
title: "Double-Twist Operators"
description: "What double-twist operators are, why crossing forces them at large spin, and how they relate to generalized free fields, large-N double traces, and two-particle states in AdS."
sidebar:
  label: "Double-Twist Operators"
  order: 3
level: Advanced
status: "Polished draft"
source: "Komargodski and Zhiboedov; Fitzpatrick, Kaplan, Poland, and Simmons-Duffin; Alday; Caron-Huot; analytic bootstrap and large-N CFT literature."
topics:
  - double-twist operators
  - analytic conformal bootstrap
  - large spin
  - generalized free fields
  - large-N CFT
canonicalTopics:
  - double-twist-operators
  - large-spin-families
  - double-trace-vs-double-twist
researchStatus:
  established:
    - "Crossing symmetry and unitarity imply large-spin double-twist families whose twists approach sums of external operator twists plus even integers under standard assumptions."
  active:
    - "Current work studies mixing, finite-spin behavior, spinning and defect generalizations, large-N multi-trace data, and nonperturbative reconstruction from Lorentzian inversion."
---

## Summary

A **double-twist operator** is a large-spin primary whose twist approaches the sum of two external operator dimensions plus an even integer. For scalar primaries $\mathcal O_1$ and $\mathcal O_2$, the family is written

$$
[\mathcal O_1\mathcal O_2]_{n,\ell},
$$

with asymptotic dimension

$$
\Delta_{n,\ell}
=\Delta_1+\Delta_2+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad (\ell\to\infty).
$$

Equivalently, the twist satisfies

$$
\tau_{n,\ell}=\Delta_{n,\ell}-\ell
\to
\Delta_1+\Delta_2+2n.
$$

The label $n=0,1,2,\ldots$ counts radial excitations, and $\ell$ is spin. In generalized free field and large-$N$ CFTs, these operators are closely related to double-trace composites. In a generic CFT, the name “double-twist” is more abstract: it means an asymptotic family forced by crossing, not necessarily a literal product of two weakly interacting fields.

The slogan is

$$
\text{double-twist}=\text{large-spin two-operator family forced by crossing}.
$$

## Prerequisites

Read [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) and [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/) first.

You should also know [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), and [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/).

The key definitions are twist,

$$
\tau=\Delta-\ell,
$$

and the mean-field double-trace spectrum

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

## Core idea

Crossing symmetry relates OPE expansions in different channels. In a lightcone limit, the identity operator or another low-twist operator in one channel creates a singularity. The crossed channel reproduces that singularity by summing over infinitely many large-spin operators.

Those operators have twists accumulating at

$$
\Delta_1+\Delta_2+2n.
$$

This accumulation is the double-twist spectrum.

For identical scalars $\phi$, the families are

$$
[\phi\phi]_{n,\ell},
\qquad
\tau_{n,\ell}\to2\Delta_\phi+2n.
$$

The leading family is

$$
[\phi\phi]_{0,\ell},
\qquad
\tau_{0,\ell}\to2\Delta_\phi.
$$

The phrase “double” means two external operators. The phrase “twist” is used because the accumulation is in twist, not in full dimension.

## Schematic construction

For scalar operators, a double-twist primary is often written schematically as

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
\sim
\mathcal O_1\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\mathcal O_2
-\text{traces}
-\text{descendants}.
$$

This expression is useful but should not be taken too literally. A true conformal primary must be annihilated by special conformal generators at the origin, so descendant subtractions are essential.

The dimension count is simple:

| Contribution | Dimension added |
|---|---:|
| $\mathcal O_1$ | $\Delta_1$ |
| $\mathcal O_2$ | $\Delta_2$ |
| spin derivatives | $\ell$ |
| radial derivatives | $2n$ |

Thus the leading additive dimension is

$$
\Delta_1+\Delta_2+2n+\ell.
$$

Interactions and finite-spin effects shift this by

$$
\gamma_{n,\ell}.
$$

## Double-twist versus double-trace

The terms **double-twist** and **double-trace** are related but not identical.

| Term | Meaning | Best context |
|---|---|---|
| double-twist | large-spin family with twist approaching $\Delta_1+\Delta_2+2n$ | generic CFT, analytic bootstrap |
| double-trace | composite of two single-trace operators | large-$N$ gauge or holographic CFT |
| two-particle state | state made of two weakly interacting bulk particles | AdS/CFT |
| mean-field operator | operator in generalized free field block decomposition | MFT or GFF CFT data |

In a large-$N$ gauge theory, if $\mathcal O_1$ and $\mathcal O_2$ are single-trace operators, then

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
$$

is naturally called double-trace.

In a generic CFT with no large-$N$ expansion, there may be no literal trace. The family still exists at large spin under the assumptions of the lightcone bootstrap. Calling it double-twist avoids implying a matrix or large-$N$ structure.

## Generalized free field example

Generalized free field gives the cleanest exact example. For a scalar $\phi$ of dimension $\Delta_\phi$, the four-point function is

$$
\mathcal G_{\rm GFF}(u,v)=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

Its OPE contains primaries

$$
[\phi\phi]_{n,\ell}
$$

with exact dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

For identical bosonic $\phi$, only even spin appears:

$$
\ell=0,2,4,\ldots .
$$

In this special case,

$$
\gamma_{n,\ell}=0
$$

for all $n$ and $\ell$.

Interacting CFTs can be viewed, at large spin, as deformations of this mean-field pattern. The dimensions become

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

with

$$
\gamma_{n,\ell}\to0
$$

as $\ell\to\infty$.

## Why large spin makes them universal

Large spin separates the two constituents. In radial quantization, the CFT lives on

$$
\mathbb R\times S^{d-1}.
$$

A double-twist operator behaves like a two-particle state with large angular momentum. Large angular momentum keeps the particles far apart on the sphere. Their interaction becomes weak, so the energy approaches a sum of one-particle energies plus excitation energy.

This explains the asymptotic dimension:

$$
\Delta_{n,\ell}\approx\Delta_1+\Delta_2+2n+\ell.
$$

The anomalous dimension

$$
\gamma_{n,\ell}
$$

is the residual interaction energy.

This physical explanation is not a proof, but it matches the analytic bootstrap theorem and becomes literal in holographic CFTs.

## Identical versus non-identical operators

For identical bosonic scalars,

$$
\phi\times\phi
$$

contains only even spins. Therefore the double-twist families have

$$
\ell=0,2,4,\ldots .
$$

For non-identical scalars

$$
\mathcal O_1\times\mathcal O_2,
$$

both even and odd spins can appear, unless additional symmetries forbid them.

For operators with global symmetry, double-twist families are organized by representation. For example, in an $O(N)$ model,

$$
\phi_i\times\phi_j=S+T+A,
$$

so the double-twist spectrum splits into singlet, traceless symmetric, and antisymmetric families. Their anomalous dimensions need not be the same.

The universal statement is sector-by-sector:

$$
\text{crossing forces large-spin families in the allowed representation sectors.}
$$

## Leading and subleading families

The integer $n$ labels a tower of families. The leading family is

$$
n=0.
$$

Subleading families have

$$
n=1,2,3,\ldots .
$$

Their twists approach

$$
\tau_n=\Delta_1+\Delta_2+2n.
$$

The leading family is usually easiest to see and often controls the most visible large-spin behavior. Subleading families are equally part of the CFT data but can be harder to isolate, especially when operator mixing is present.

At fixed $n$ and large spin, the asymptotic expansion is controlled. At large $n$, new physics can enter. For example, in holographic theories large $n$ corresponds to high radial excitation in AdS and can probe short-distance bulk interactions.

Thus one should specify the limit:

$$
\ell\to\infty\quad\text{with }n\text{ fixed}
$$

is the standard double-twist large-spin limit.

## Anomalous dimensions

The anomalous dimension is defined by

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\left(\Delta_1+\Delta_2+2n+\ell\right).
$$

In a generic unitary CFT,

$$
\gamma_{n,\ell}\to0
\qquad
\ell\to\infty.
$$

Low-twist exchanged operators determine the leading falloff. If the leading crossed-channel non-identity operator has twist $\tau_m$, then schematically

$$
\gamma_{n,\ell}\sim \frac{1}{J^{\tau_m}}.
$$

For stress-tensor exchange,

$$
\tau_T=d-2,
$$

so its contribution scales like

$$
\gamma_{n,\ell}^{(T)}\sim \frac{1}{J^{d-2}}.
$$

The sign depends on channel and operator type. In many identical-scalar stress-tensor cases, the correction is negative, corresponding to attraction in the AdS interpretation.

## OPE coefficients

Double-twist operators also have OPE coefficients. For identical scalars, write

$$
\lambda_{\phi\phi[\phi\phi]_{n,\ell}}^2=a_{n,\ell}.
$$

At large spin,

$$
a_{n,\ell}=a_{n,\ell}^{\rm GFF}\left(1+\delta a_{n,\ell}+\cdots\right).
$$

The leading coefficients reproduce generalized-free-field data. The corrections are determined by the same crossed-channel operators that determine anomalous dimensions.

OPE coefficient corrections are often more convention-dependent than dimensions. They depend on how conformal blocks and two-point functions are normalized.

A robust statement is:

$$
\text{large-spin double-twist OPE data approach mean-field data.}
$$

The exact numerical coefficients require a convention-specific formula.

## Mixing

The label

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
$$

can be ambiguous when several operators have the same quantum numbers. Suppose there are two possible schematic composites:

$$
[\mathcal O_1\mathcal O_2]_{n,\ell},
\qquad
[\mathcal O_3\mathcal O_4]_{m,\ell},
$$

with equal or nearby mean-field twists. Interactions mix them.

Then the true primary operators are eigenvectors of an anomalous-dimension matrix:

$$
\Gamma_{ab}(n,\ell).
$$

The double-twist theorem guarantees families, but it does not always assign a unique naive composite label to each exact operator.

Mixing is especially important in:

- large-$N$ theories with several single-trace operators;
- theories with global symmetry;
- supersymmetric theories with multiplet recombination;
- finite spin extrapolations;
- degenerate generalized-free spectra.

The cute notation is not a substitute for diagonalization. Alas, notation continues to be adorable and dangerous.

## Relation to large-N double traces

In a large-$N$ CFT, normalized single-trace operators behave as generalized free fields at leading order. Therefore the double-twist operators are literal double-trace operators:

$$
[\mathcal O_i\mathcal O_j]_{n,\ell}.
$$

Their leading dimensions are

$$
\Delta_i+\Delta_j+2n+\ell.
$$

Connected correlators at order $1/N^p$ generate anomalous dimensions:

$$
\Delta_{n,\ell}=\Delta_i+\Delta_j+2n+\ell+\frac{1}{N^p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

This is the main setting where double-twist and double-trace language overlap perfectly.

At higher orders in $1/N$, multi-trace operators also appear and can mix. For example, double-trace operators may mix with triple-trace operators if dimensions and quantum numbers allow. Large $N$ suppresses but does not eliminate the need for careful bookkeeping.

## Holographic interpretation

In AdS/CFT, a scalar primary $\mathcal O$ corresponds to a one-particle bulk field. A double-twist operator corresponds to a two-particle state in global AdS.

The dictionary is:

| CFT object | AdS interpretation |
|---|---|
| $\mathcal O_1$ | one-particle state |
| $\mathcal O_2$ | another one-particle state |
| $[\mathcal O_1\mathcal O_2]_{n,\ell}$ | two-particle state |
| $n$ | radial excitation |
| $\ell$ | angular momentum on $S^{d-1}$ |
| $\gamma_{n,\ell}$ | interaction energy |
| large $\ell$ | large impact parameter |

Bulk field exchange produces anomalous dimensions. Contact interactions produce additional corrections, often with characteristic support in spin. Bulk locality constrains how these anomalous dimensions behave at large $n$ and $\ell$.

This is why double-twist data are central in holographic bootstrap.

## Relation to Lorentzian inversion

The Lorentzian inversion formula reconstructs CFT data from the double discontinuity of a four-point function. It makes double-twist families visible as poles in a function of dimension and spin.

In this language, double-twist operators arise from singularities generated by crossed-channel operators. The identity produces the leading mean-field poles. Non-identity low-twist operators shift the pole locations and residues.

The inversion formula improves the original lightcone argument in several ways:

1. It gives systematic coefficients.
2. It explains analyticity in spin.
3. It clarifies which spins are controlled.
4. It handles subleading corrections more cleanly.
5. It connects double-twist data to positive double discontinuities.

Thus double-twist operators are not just an intuitive large-spin picture. They are encoded in a precise analytic structure of CFT data.

## Finite spin caution

The large-spin theorem is asymptotic. It does not say that spin zero operators must behave like simple double-twist composites.

For example, the family

$$
[\phi\phi]_{0,\ell}
$$

may be clearly identifiable for large $\ell$ but hard to track down to

$$
\ell=0.
$$

At low spin, operators can mix, disappear into other families, hit unitarity bounds, recombine in supersymmetric theories, or simply be far from the asymptotic formula.

Extrapolating large-spin formulas to small spin can be useful and sometimes remarkably accurate. But it should be labeled as extrapolation.

The honest statement is:

$$
\text{large-spin data constrain finite spin; they do not automatically solve it.}
$$

## Common pitfalls

**Do not confuse double-twist with double-trace.** Double-trace is a large-$N$ notion; double-twist is a generic large-spin CFT notion.

**Do not forget the limit.** The statement is usually $\ell\to\infty$ at fixed $n$.

**Do not treat schematic composites as exact primaries.** Descendant subtraction and mixing matter.

**Do not ignore spin selection rules.** Identical bosonic scalars allow only even spin, while non-identical OPEs may allow odd spin.

**Do not assume one family in all symmetry sectors.** Global symmetry decomposes double-twist operators into representations.

**Do not overtrust finite-spin extrapolation.** Large-spin formulas are asymptotic.

**Do not quote OPE coefficient corrections without conventions.** Block and operator normalization matter.

## Relations to other pages

This page follows [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/) and prepares [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/) and [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/).

It connects to [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) and [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/) because those pages give the exact mean-field double-trace spectrum.

It also connects to [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) and [Holographic CFT](/cft-bootstrap/holographic-cft/) because double-twist operators become two-particle states in large-$N$ and AdS settings.

## Research status

Double-twist operators are established central objects of analytic bootstrap. Their existence at large spin and their mean-field asymptotics follow from lightcone crossing under standard assumptions.

Active research studies their finite-spin continuation, mixing, degeneracies, spinning generalizations, defect and boundary analogues, large-$N$ multi-trace corrections, holographic loop effects, nonunitary cases, and numerical extraction from bootstrap data.

## Exercises

### Exercise 1

For scalar primaries $\mathcal O_1$ and $\mathcal O_2$, write the asymptotic dimension of the double-twist family $[\mathcal O_1\mathcal O_2]_{n,\ell}$.

<details><summary><strong>Solution</strong></summary>

The asymptotic dimension is

$$
\Delta_{n,\ell}=\Delta_1+\Delta_2+2n+\ell+\gamma_{n,\ell},
$$

with

$$
\gamma_{n,\ell}\to0
\qquad
\ell\to\infty.
$$

The corresponding twist approaches

$$
\tau_{n,\ell}\to\Delta_1+\Delta_2+2n.
$$

</details>

### Exercise 2

Why is the phrase “double-trace” not always appropriate?

<details><summary><strong>Solution</strong></summary>

Double-trace refers to composites of two single-trace operators in large-$N$ matrix-like theories. A generic CFT may not have a large-$N$ expansion or literal trace operators. Nevertheless, crossing can still force large-spin families whose twists approach sums of external dimensions. These are double-twist operators. Thus double-twist is the more general term.

</details>

### Exercise 3

For identical scalar $\phi$, why are only even spins present in $[\phi\phi]_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

The OPE $\phi\times\phi$ must be symmetric under exchange of the two identical bosonic scalar operators. The three-point function of two identical scalars with a spin-$\ell$ symmetric traceless operator changes by $(-1)^\ell$ under this exchange. Symmetry requires $(-1)^\ell=1$, so $\ell$ is even.

</details>

### Exercise 4

What is the meaning of $n$ in $[\mathcal O_1\mathcal O_2]_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

The integer $n$ labels radial excitation. In a schematic composite it corresponds to inserting $n$ powers of a two-derivative scalar structure such as $(\partial^2)^n$. It raises the leading twist by $2n$:

$$
\tau_n^{(0)}=\Delta_1+\Delta_2+2n.
$$

In AdS language, it is the radial excitation number of a two-particle state.

</details>

### Exercise 5

Why can one zero or one schematic label hide multiple double-twist operators?

<details><summary><strong>Solution</strong></summary>

If several operators share the same spin, global-symmetry representation, and nearby or equal mean-field twist, interactions mix them. The exact conformal primaries are eigenvectors of an anomalous-dimension matrix, not necessarily the naive schematic composites. Thus a label such as $[\mathcal O_1\mathcal O_2]_{n,\ell}$ may refer to a family or subspace rather than a unique exact operator.

</details>

## References

- Z. Komargodski and A. Zhiboedov, “Convexity and liberation at large spin,” *Journal of High Energy Physics* **2013**.
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added definition of double-twist families, distinction from double-trace operators, generalized-free and large-$N$ examples, spin and symmetry-sector rules, anomalous dimensions, mixing, holographic interpretation, finite-spin caveats, exercises, and references.
