---
title: "Large-Spin Perturbation Theory"
description: "How analytic bootstrap organizes anomalous dimensions and OPE coefficients of double-twist operators as asymptotic expansions in conformal spin."
sidebar:
  label: "Large-Spin Perturbation Theory"
  order: 2
level: Advanced
status: "Polished draft"
source: "Fitzpatrick, Kaplan, Poland, and Simmons-Duffin; Alday; Caron-Huot; Simmons-Duffin TASI lectures; analytic bootstrap literature."
topics:
  - large spin
  - analytic conformal bootstrap
  - double-twist operators
  - anomalous dimensions
  - conformal spin
canonicalTopics:
  - large-spin-perturbation-theory
  - conformal-spin-expansion
  - double-twist-anomalous-dimensions
researchStatus:
  established:
    - "Large-spin perturbation theory systematically computes asymptotic corrections to double-twist dimensions and OPE coefficients from low-twist crossed-channel data."
  active:
    - "Current research refines finite-spin extrapolation, mixing, spinning correlators, holographic applications, defect systems, and resummations of large-spin expansions."
---

## Summary

**Large-spin perturbation theory** studies CFT data for operators with large spin. In a unitary CFT, crossing symmetry forces double-twist families whose dimensions approach

$$
\Delta_{n,\ell}=\Delta_1+\Delta_2+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad (\ell\to\infty).
$$

Large-spin perturbation theory computes the small corrections

$$
\gamma_{n,\ell}
$$

and the associated OPE coefficient corrections as asymptotic series in inverse conformal spin:

$$
\frac{1}{J}.
$$

The basic mechanism is simple: low-twist operators exchanged in one channel determine the large-spin behavior of double-twist operators in the crossed channel. If an operator of twist $\tau_m$ is exchanged, it typically generates corrections of order

$$
\gamma_{n,\ell}\sim \frac{1}{J^{\tau_m}}
$$

up to coefficients, signs, group theory, and normalization conventions.

This page explains the expansion parameter, the role of conformal spin, how anomalous dimensions appear, why logarithms matter, and how the method connects lightcone bootstrap, Lorentzian inversion, and holographic CFT.

## Prerequisites

Read [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/), [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), and [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) first.

You should know the definition of twist,

$$
\tau=\Delta-\ell,
$$

and the large-spin double-twist spectrum

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

You should also be comfortable with the idea that anomalous dimensions produce logarithms when powers such as $u^{\Delta/2}$ are expanded perturbatively.

## Core idea

The lightcone bootstrap gives the existence of large-spin double-twist families. Large-spin perturbation theory asks for their detailed asymptotic CFT data.

For identical scalars $\phi$, write

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

and

$$
a_{n,\ell}=a_{n,\ell}^{(0)}\left(1+\delta a_{n,\ell}+\cdots\right),
$$

where $a_{n,\ell}$ is the squared OPE coefficient in a chosen block normalization. At large spin, both corrections admit asymptotic expansions:

$$
\gamma_{n,\ell}=\sum_m \frac{\gamma_{n}^{(m)}}{J^{\tau_m}}+\cdots,
$$

and

$$
\delta a_{n,\ell}=\sum_m \frac{\delta a_{n}^{(m)}}{J^{\tau_m}}+\cdots .
$$

Here $m$ labels crossed-channel operators, and $\tau_m$ is their twist.

The slogan is

$$
\text{low-twist crossed-channel data}
\quad\Longrightarrow\quad
\text{large-spin direct-channel data}.
$$

This is a controlled asymptotic statement. It is not automatically a convergent expansion at small spin.

## Conformal spin

The natural expansion variable is not always $\ell$ itself. It is the **conformal spin** $J$, which is related to the quadratic Casimir of the collinear conformal group.

For a double-twist family of identical scalars, a common large-spin variable is

$$
J^2=\left(\ell+\Delta_\phi+n+\frac{\gamma_{n,\ell}}{2}\right)
\left(\ell+\Delta_\phi+n-1+\frac{\gamma_{n,\ell}}{2}\right).
$$

At leading order,

$$
J^2\approx(\ell+\Delta_\phi+n)(\ell+\Delta_\phi+n-1).
$$

For large $\ell$,

$$
J\sim \ell.
$$

So one often writes expansions in $1/J$ but informally calls them large-spin expansions.

The conformal spin variable has two advantages. First, it respects the natural Casimir structure of conformal blocks. Second, expansions in $1/J^2$ often have cleaner parity and reciprocity properties than expansions in $1/\ell$.

## Why low twist dominates

In a lightcone limit, a conformal block behaves schematically as

$$
G_{\Delta,\ell}(z,\bar z)\sim z^{\tau/2}\,k_{\Delta+\ell}(\bar z)+\cdots,
$$

where

$$
\tau=\Delta-\ell.
$$

Thus smaller twist gives stronger leading behavior as $z\to0$. In a crossed channel, the identity has twist zero. The next important operators are the lowest-twist non-identity operators: conserved currents, stress tensors, low-dimension scalars, or other protected or light operators.

If the lowest non-identity twist is $\tau_m$, then the leading correction to double-twist data is typically suppressed by

$$
J^{-\tau_m}.
$$

This is why the stress tensor, with

$$
\tau_T=d-2,
$$

often controls the universal leading correction in theories where no lower-twist scalar is present.

The hierarchy of twists becomes a hierarchy of large-spin corrections.

## Logarithms and anomalous dimensions

An anomalous dimension appears in the power of $u$ in a conformal block. Suppose a double-twist operator has

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\gamma_{n,\ell}.
$$

Then a factor such as

$$
u^{\Delta_{n,\ell}/2}
$$

expands as

$$
u^{\Delta_{n,\ell}^{(0)}/2}
\left[1+\frac{1}{2}\gamma_{n,\ell}\log u+\cdots\right].
$$

Therefore the coefficient of

$$
\log u
$$

in the direct-channel expansion contains anomalous-dimension data.

This is one of the workhorses of analytic bootstrap. A crossed-channel low-twist exchange produces a singular function of the cross-ratios. When re-expanded in the direct channel, the logarithmic part determines

$$
\gamma_{n,\ell}.
$$

The non-logarithmic part helps determine OPE coefficient corrections.

## A schematic formula

For identical external scalars, the contribution of a crossed-channel operator $\mathcal O_m$ of twist $\tau_m$ and spin $\ell_m$ gives a leading large-spin correction of the schematic form

$$
\gamma_{n,\ell}^{(m)}
\sim
-\frac{\lambda_{\phi\phi m}^2\,\mathcal K_{n,m}}{J^{\tau_m}},
$$

where $\mathcal K_{n,m}$ is a known coefficient depending on dimensions, spin, spacetime dimension, and normalization conventions.

The minus sign is common for stress-tensor-like attractive exchanges in identical scalar setups, but signs can depend on the exchanged operator, external representations, and global-symmetry channel. The formula above is therefore a template, not a universal sign theorem.

A more complete expansion has the form

$$
\gamma_{n,\ell}^{(m)}
=\frac{1}{J^{\tau_m}}
\left(c_0+\frac{c_1}{J^2}+\frac{c_2}{J^4}+\cdots\right)
$$

in many parity-even situations. Additional powers, logarithms, or mixing effects can appear in more complicated cases.

The exact coefficients belong on specialized calculation pages. This page is about the structure.

## Leading trajectory n equals zero

The simplest family is the leading-twist family

$$
[\phi\phi]_{0,\ell}.
$$

Its mean-field dimensions are

$$
\Delta_{0,\ell}^{(0)}=2\Delta_\phi+\ell.
$$

At large spin,

$$
\Delta_{0,\ell}=2\Delta_\phi+\ell+\gamma_{0,\ell}.
$$

The leading trajectory often gives the clearest signal of low-twist exchange. For example, if the stress tensor is the leading non-identity operator in the crossed channel, then

$$
\gamma_{0,\ell}\sim -\frac{\text{const}}{J^{d-2}}.
$$

This large-spin tail is universal in the sense that the stress tensor and its Ward identity exist in every local CFT. The coefficient is theory-dependent through $C_T$ and through the external scalar dimension.

Higher $n$ families are also present, but their mixing and coefficient structure can be more involved.

## Higher radial excitations

For each nonnegative integer $n$, there is a family

$$
[\phi\phi]_{n,\ell}
$$

with mean-field twist

$$
\tau_n^{(0)}=2\Delta_\phi+2n.
$$

Large-spin perturbation theory can be performed at fixed $n$ and large $\ell$. The resulting data are functions of $n$:

$$
\gamma_{n,\ell}=\frac{c_n}{J^{\tau_m}}+\cdots .
$$

For fixed low $n$, this is straightforward in principle. For large $n$ and large $\ell$ simultaneously, new regimes can appear. In holographic CFTs, large $n$ probes high-energy two-particle states in AdS, and the expansion can become sensitive to bulk locality, black-hole thresholds, or stringy physics.

Thus the phrase “large spin” usually means:

$$
\ell\to\infty\quad\text{with }n\text{ fixed},
$$

unless another limit is explicitly stated.

## OPE coefficient corrections

Large-spin perturbation theory also computes OPE coefficients. Write

$$
a_{n,\ell}=a_{n,\ell}^{(0)}\left(1+\delta a_{n,\ell}\right).
$$

The anomalous dimension controls logarithms. The OPE coefficient correction controls non-logarithmic terms, but it is often entangled with derivatives of conformal blocks with respect to $\Delta$.

A useful schematic expansion is

$$
a_{n,\ell}G_{\Delta_{n,\ell},\ell}
=
a_{n,\ell}^{(0)}G_{\Delta_{n,\ell}^{(0)},\ell}
+a_{n,\ell}^{(0)}\delta a_{n,\ell}G_{\Delta_{n,\ell}^{(0)},\ell}
+a_{n,\ell}^{(0)}\gamma_{n,\ell}\partial_\Delta G_{\Delta,\ell}\big|_{\Delta=\Delta_{n,\ell}^{(0)}}+\cdots .
$$

The derivative term generates logarithms. The coefficient correction contributes to the regular part.

In practice, extracting $\delta a_{n,\ell}$ is more convention-dependent and sometimes more delicate than extracting $\gamma_{n,\ell}$.

## Mixing and degeneracy

Large-spin labels such as

$$
[\phi\phi]_{n,\ell}
$$

can hide mixing. If several operator families have the same quantum numbers and nearby dimensions, interactions diagonalize an anomalous-dimension matrix.

This is common in large-$N$ theories with several single-trace operators, in theories with global symmetry, and in systems with multiple external scalars.

For example, if two scalar primaries $\mathcal O_1$ and $\mathcal O_2$ have dimensions such that

$$
\Delta_1+\Delta_2+2n
$$

coincides with another double-twist twist, then the naive basis of composites is not the basis of exact primaries. One must diagonalize mixing order by order.

The safe statement is:

$$
\text{large-spin perturbation theory organizes families, but exact operators are eigenvectors.}
$$

Ignoring mixing is one of the fastest ways to get a clean formula with the wrong interpretation.

## Relation to Lorentzian inversion

The Lorentzian inversion formula systematizes large-spin perturbation theory. It reconstructs CFT data as a function of spin from the double discontinuity of a correlator:

$$
c(\Delta,\ell)\sim\int dz\,d\bar z\;\operatorname{dDisc}[\mathcal G(z,
\bar z)]\times\text{known kernel}.
$$

The poles of $c(\Delta,\ell)$ encode operator dimensions and OPE coefficients.

Large-spin perturbation theory can be viewed as an asymptotic evaluation of this inversion formula. Crossed-channel low-twist operators dominate the relevant integrals, producing powers of $1/J$.

This perspective has major advantages:

1. It clarifies analyticity in spin.
2. It handles systematic subleading corrections.
3. It makes positivity of double discontinuities important.
4. It connects lightcone bootstrap to dispersion-like formulas.
5. It gives a cleaner route to finite-spin questions, subject to spin thresholds and Regge assumptions.

## Holographic interpretation

In holographic CFTs, double-twist operators are two-particle states in AdS. Large spin means large angular momentum, which corresponds to large impact parameter. The two particles are far apart, so interactions are weak.

A low-twist exchanged operator corresponds to a light bulk field mediating a long-range force. The large-spin anomalous dimension is the binding energy of the two-particle state:

$$
\gamma_{n,\ell}\sim \text{interaction energy in AdS}.
$$

Stress-tensor exchange corresponds to graviton exchange. Conserved-current exchange corresponds to gauge-boson exchange. Scalar exchange corresponds to a bulk scalar force.

This interpretation makes the power law natural:

$$
\frac{1}{J^{\tau_m}}
$$

is the CFT version of a long-distance potential falloff controlled by the exchanged field.

Large-spin perturbation theory is therefore one of the clearest bridges between conformal bootstrap and AdS effective field theory.

## Practical workflow

A typical large-spin calculation follows this pattern:

1. Choose the four-point function and external operators.
2. Identify the leading mean-field or double-twist families.
3. Identify the lowest-twist crossed-channel operators.
4. Expand the crossed-channel contribution in the lightcone limit.
5. Match logarithmic terms to extract $\gamma_{n,\ell}$.
6. Match regular terms to extract OPE coefficient corrections.
7. Re-express the answer in powers of conformal spin $J$.
8. Check mixing, global symmetry, and normalization conventions.
9. Compare with Lorentzian inversion when available.
10. Treat finite-spin extrapolation cautiously.

For simple examples, this can be done by hand. For modern applications, inversion formulas and symbolic computation are often used.

## Common pitfalls

**Do not expand in dimension when twist is the organizing variable.** The lightcone limit is controlled by $\tau=\Delta-\ell$.

**Do not confuse large $J$ with exact finite-spin data.** Large-spin perturbation theory is asymptotic unless additional convergence or inversion arguments are supplied.

**Do not ignore mixing.** Degenerate double-twist families require diagonalization.

**Do not quote signs without specifying channels.** Global symmetry and representation channels can change signs and coefficients.

**Do not treat OPE coefficient corrections as convention-free.** They depend on block normalization and operator normalization.

**Do not assume the stress tensor is always the leading correction.** A lower-twist scalar, current, or protected operator may dominate.

**Do not forget the identity contribution.** It gives the mean-field skeleton around which the expansion is built.

## Relations to other pages

This page follows [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) and prepares [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/) and [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/).

It connects to [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), and [Holographic CFT](/cft-bootstrap/holographic-cft/) because large-spin perturbation theory is the analytic language for perturbing double-trace data.

It also connects to [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), where the large-spin expansion is embedded in a more powerful reconstruction formula.

## Research status

Large-spin perturbation theory is established as a central tool of analytic conformal bootstrap. Its leading results are standard, and the Lorentzian inversion formula has made the framework systematic.

Active research studies finite-spin control, mixing, spinning external operators, nonunitary systems, defects and boundaries, thermal correlators, high-energy limits, holographic loop corrections, and the relation between large-spin expansions and numerical bootstrap data.

## Exercises

### Exercise 1

Explain why an exchanged operator of twist $\tau_m$ produces corrections scaling like $J^{-\tau_m}$ at large spin.

<details><summary><strong>Solution</strong></summary>

In the lightcone limit, crossed-channel contributions are organized by twist. Lower twist gives stronger singular behavior. Matching this crossed-channel behavior to the direct-channel sum over large-spin double-twist blocks requires corrections whose large-spin tail reproduces the same singularity. The asymptotic conformal block analysis gives a power set by the exchanged twist:

$$
\gamma_{n,\ell}^{(m)}\sim J^{-\tau_m}.
$$

The coefficient depends on the exchanged operator's dimension, spin, OPE coefficient, and normalization conventions.

</details>

### Exercise 2

Why is conformal spin often preferred to $\ell$ as the expansion variable?

<details><summary><strong>Solution</strong></summary>

Conformal spin is related to the quadratic Casimir of the collinear conformal group. For identical scalars, a leading definition is

$$
J^2\approx(\ell+\Delta_\phi+n)(\ell+\Delta_\phi+n-1).
$$

Expansions in $1/J$ respect the natural conformal-block structure and often have cleaner parity and reciprocity properties than raw expansions in $1/\ell$.

</details>

### Exercise 3

Show how an anomalous dimension produces a logarithm.

<details><summary><strong>Solution</strong></summary>

Let

$$
\Delta=\Delta^{(0)}+\gamma.
$$

Then

$$
u^{\Delta/2}
=u^{\Delta^{(0)}/2+\gamma/2}
=u^{\Delta^{(0)}/2}\exp\left(\frac{\gamma}{2}\log u\right).
$$

For small $\gamma$,

$$
u^{\Delta/2}
=u^{\Delta^{(0)}/2}\left(1+\frac{\gamma}{2}\log u+\cdots\right).
$$

Thus logarithmic terms in the block expansion encode anomalous dimensions.

</details>

### Exercise 4

When is mixing important in large-spin perturbation theory?

<details><summary><strong>Solution</strong></summary>

Mixing is important when two or more operators have the same spin, global-symmetry representation, and equal or nearby mean-field twists. In that case, interactions do not assign anomalous dimensions to the schematic composites independently. Instead, one must diagonalize an anomalous-dimension matrix. This is common in large-$N$ theories with several single-trace operators or in theories with global-symmetry multiplets.

</details>

### Exercise 5

What is the holographic interpretation of $\gamma_{n,\ell}$?

<details><summary><strong>Solution</strong></summary>

In AdS/CFT, a double-twist operator is a two-particle state in global AdS. Its mean-field dimension is the noninteracting two-particle energy. The anomalous dimension

$$
\gamma_{n,\ell}
$$

is the interaction energy. At large spin the particles are separated by a large impact parameter, so the interaction becomes weak and can be expanded in inverse conformal spin.

</details>

## References

- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- Z. Komargodski and A. Zhiboedov, “Convexity and liberation at large spin,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added conformal spin, anomalous-dimension logarithms, low-twist exchange structure, leading and higher double-twist families, OPE coefficient corrections, mixing, inversion-formula and holographic interpretations, exercises, and references.
