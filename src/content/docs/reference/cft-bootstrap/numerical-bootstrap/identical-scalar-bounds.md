---
title: "Identical Scalar Bounds"
description: "How the simplest numerical bootstrap setup bounds operator dimensions, OPE coefficients, and stress-tensor data from one identical-scalar four-point function."
sidebar:
  label: "Identical Scalar Bounds"
  order: 7
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; Simmons-Duffin TASI lectures; early numerical bootstrap literature."
topics:
  - identical scalar bootstrap
  - numerical conformal bootstrap
  - scalar gap bounds
  - OPE coefficient bounds
  - stress tensor bounds
canonicalTopics:
  - identical-scalar-bounds
  - scalar-gap-bootstrap
  - single-correlator-bootstrap
researchStatus:
  established:
    - "The identical-scalar four-point bootstrap gives rigorous-looking conditional bounds on operator dimensions and OPE coefficients in unitary CFTs."
  active:
    - "Modern work refines scalar bounds using higher precision, mixed correlators, navigator methods, large-spin information, and applications to gauge, defect, and supersymmetric systems."
---

## Summary

The **identical scalar bootstrap** is the cleanest numerical bootstrap problem. Choose one scalar primary $\phi$ and study the four-point function

$$
\langle \phi\phi\phi\phi\rangle.
$$

Crossing symmetry and unitarity imply a schematic equation

$$
\vec F_{\mathbf 1}
+\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2\vec F_{\Delta,\ell}=0,
$$

with

$$
\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

A numerical bootstrap bound asks whether this equation can be satisfied if one assumes a gap in some sector. For example, suppose the first non-identity scalar in $\phi\times\phi$ has dimension at least $\Delta_{\rm gap}$. If a linear functional excludes that assumption, then every unitary CFT with scalar $\phi$ must contain a scalar below $\Delta_{\rm gap}$.

The output is usually a curve such as

$$
\Delta_{\rm first\ scalar}\le B(\Delta_\phi),
$$

or an OPE-coefficient or central-charge bound. These are the original workhorses of the modern numerical conformal bootstrap. They teach the whole method in its least cluttered form: crossing, positivity, a spectral assumption, and an excluding functional.

## Prerequisites

Read [What the Numerical Bootstrap Computes](/cft-bootstrap/numerical-bootstrap/what-the-numerical-bootstrap-computes/), [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/), [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), and [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) first.

You should know the scalar conformal block expansion, the unitarity bounds, and why identical-scalar OPE coefficients enter as nonnegative squares.

## Core idea

The identical scalar bootstrap is a one-correlator consistency test. The input is an external scalar dimension $\Delta_\phi$ and a proposed spectrum in the $\phi\times\phi$ OPE. The computation asks whether the identity vector can be canceled by a positive sum of allowed conformal block vectors.

The geometric condition is

$$
-\vec F_{\mathbf 1}
\in
\operatorname{Cone}\{\vec F_{\Delta,\ell}\text{ allowed}\}.
$$

A bound is obtained by changing the allowed cone. If one raises the assumed scalar gap, fewer scalar block vectors are available. Eventually the cone becomes too small to contain $-\vec F_{\mathbf1}$. At that point a separating functional appears, and the assumed gap is excluded.

The slogan is

$$
\text{raise a gap until crossing breaks}.
$$

The largest gap not excluded at a chosen cutoff is the numerical bound.

## Setup and conventions

Let $\phi$ be a scalar primary of dimension $\Delta_\phi$ in a unitary CFT in $d$ dimensions. Normalize

$$
\langle\phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

The four-point function is

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v),
$$

with

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The conformal block decomposition is

$$
\mathcal G(u,v)=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v).
$$

For identical bosonic scalars, only even spins appear:

$$
\ell=0,2,4,\ldots .
$$

The identity has

$$
\Delta=0,
\qquad
\ell=0,
\qquad
\lambda_{\phi\phi\mathbf1}=1.
$$

All non-identity operators must obey the unitarity bounds. For scalar primaries,

$$
\Delta\ge\frac{d-2}{2},
$$

except for the identity. For symmetric traceless spin $\ell\ge1$,

$$
\Delta\ge \ell+d-2.
$$

## The scalar gap bound

The simplest classic bound concerns the first scalar in $\phi\times\phi$. Define

$$
\Delta_{S,0}^{\rm first}
$$

as the dimension of the lowest non-identity scalar appearing in the OPE. To bound it, assume the opposite of what you want to prove:

$$
\Delta_{S,0}^{\rm first}\ge\Delta_{\rm gap}.
$$

Then the allowed spectrum is:

| Spin | Assumed allowed range |
|---:|---|
| $\ell=0$ | $\Delta\ge\Delta_{\rm gap}$ |
| $\ell=2,4,6,\ldots$ | $\Delta\ge\ell+d-2$ |

If a functional satisfies

$$
\alpha(\vec F_{\mathbf1})>0,
$$

$$
\alpha(\vec F_{\Delta,0})\ge0
\qquad
\Delta\ge\Delta_{\rm gap},
$$

and

$$
\alpha(\vec F_{\Delta,\ell})\ge0
\qquad
\Delta\ge\ell+d-2,\quad \ell=2,4,6,\ldots,
$$

then the assumed gap is excluded. Therefore a scalar must exist below $\Delta_{\rm gap}$.

Scanning $\Delta_{\rm gap}$ for each value of $\Delta_\phi$ produces a curve

$$
\Delta_{S,0}^{\rm first}\le B(\Delta_\phi).
$$

This curve is one of the simplest numerical bootstrap plots.

## What the curve means

A scalar gap bound curve separates two regions.

| Region | Meaning |
|---|---|
| above the curve | excluded by a functional at the chosen cutoff |
| below the curve | not excluded by this computation |
| on the curve | optimal boundary at the chosen cutoff |

The lower region is not a catalogue of existing CFTs. It is only the region not ruled out by the chosen one-correlator bootstrap problem.

At special values of $\Delta_\phi$, the bound may develop a kink. A kink often suggests that a real CFT lives there, but this is not automatic. The 3D Ising model famously appears near a kink in the $d=3$ scalar bound, but the high-precision Ising determination requires mixed correlators and gap assumptions, not the kink alone.

A careful caption for a bound should state:

- spacetime dimension $d$;
- external dimension $\Delta_\phi$ range;
- derivative cutoff $\Lambda$;
- spin treatment;
- assumptions on sectors;
- normalization convention;
- numerical precision.

No caption, no glory.

## Generalized free field as a benchmark

The generalized free scalar of dimension $\Delta_\phi$ has the mean-field four-point function

$$
\mathcal G_{\rm GFF}(u,v)=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

Its $\phi\times\phi$ OPE contains double-trace operators

$$
[\phi\phi]_{n,\ell},
\qquad
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

Therefore the first scalar has

$$
\Delta_{S,0}^{\rm first}=2\Delta_\phi.
$$

Many scalar bootstrap bounds approach or interact with the generalized-free line. This makes GFF a useful sanity check: it is an exactly crossing-symmetric solution with positive OPE data, though it is usually not a complete local CFT with a finite-$C_T$ stress tensor.

If a proposed bound excludes known GFF data in a regime where GFF should be allowed as a crossing solution, something is wrong with the setup.

## Stress tensor and C_T bounds

In a local CFT, the stress tensor appears in the $\phi\times\phi$ OPE as a spin-two operator with

$$
\Delta_T=d,
\qquad
\ell=2.
$$

The OPE coefficient $\lambda_{\phi\phi T}$ is fixed by Ward identities in terms of $\Delta_\phi$ and the stress-tensor two-point normalization $C_T$. Schematically,

$$
\lambda_{\phi\phi T}^2\propto\frac{\Delta_\phi^2}{C_T},
$$

with convention-dependent proportionality.

Thus bounding $\lambda_{\phi\phi T}^2$ is equivalent to bounding $C_T$. A lower bound on $C_T$ can be obtained by asking how large stress-tensor exchange must be for crossing to work.

This is physically important. $C_T$ measures stress-tensor fluctuations and roughly counts degrees of freedom. In large-$N$ theories, $C_T$ is large and stress-tensor exchange in normalized single-particle correlators is suppressed.

In a one-correlator scalar bootstrap, $C_T$ bounds are useful but rarely isolate a theory by themselves. Mixed correlators and additional assumptions usually give sharper information.

## OPE coefficient bounds

One can also bound the OPE coefficient of a specific operator. Suppose an operator $\mathcal O_*$ of known dimension and spin is assumed to appear. Separate it from the crossing equation:

$$
\vec F_{\mathbf1}+\lambda_*^2\vec F_*+\sum_i p_i\vec F_i=0,
\qquad
p_i\ge0.
$$

Choose a functional normalized by

$$
\alpha(\vec F_{\mathbf1})=1,
$$

and positive on all non-target allowed operators:

$$
\alpha(\vec F_i)\ge0.
$$

If

$$
\alpha(\vec F_*)<0,
$$

then applying $\alpha$ to crossing gives

$$
\lambda_*^2\le -\frac{1}{\alpha(\vec F_*)}.
$$

Optimizing over $\alpha$ gives the best upper bound available at that cutoff. Lower bounds can also be formulated, but the details depend on how the target contribution is isolated and what assumptions are imposed.

OPE coefficient bounds are often more convention-sensitive than dimension bounds. Always specify two-point and conformal block normalizations.

## Relevant versus irrelevant scalar bounds

In statistical physics, a scalar is relevant if

$$
\Delta<d.
$$

A scalar gap bound can therefore constrain how many relevant scalars a CFT must or may have. For example, if crossing forces a scalar below $d$, then any CFT with that external operator has a relevant scalar in the OPE.

This logic is useful for distinguishing ordinary critical points from multicritical points. A theory with many relevant singlets requires more tunings to reach criticality. A bound on the first or second scalar can help test whether a proposed CFT could describe a stable critical point.

However, a one-correlator bound sees only the $\phi\times\phi$ OPE. It may miss relevant operators that do not appear in that OPE or appear in other symmetry sectors. For stability questions, global symmetry and mixed correlators are usually essential.

## The role of gaps

A gap assumption removes operators from the allowed cone. Examples include:

$$
\Delta_{S,0}^{\rm next}\ge 3.8,
$$

or

$$
\Delta_{\ell=4}^{\rm first}\ge 5.
$$

Gap assumptions make the bootstrap stronger but more conditional. They are justified when based on physics: known relevant-operator counts, global symmetry, perturbative estimates, large-$N$ expansions, previous bootstrap results, or independent numerical evidence.

Unjustified gaps can manufacture pretty islands with no physical meaning. The bootstrap will happily optimize whatever assumptions you feed it. It is not a conscience; it is a machine with excellent posture.

A responsible gap-based claim says exactly which operators are assumed absent below which dimensions.

## Cutoff dependence

At derivative cutoff $\Lambda$, the bound is a finite-dimensional result. Increasing $\Lambda$ enlarges the functional search space. In nested setups, bounds should become stronger or stabilize.

A robust bound is shown as a sequence:

$$
B_{\Lambda=11},
\qquad
B_{\Lambda=19},
\qquad
B_{\Lambda=27},
\qquad
\ldots .
$$

A kink that sharpens and stabilizes as $\Lambda$ increases is more interesting than one that drifts or disappears. An island that shrinks in a controlled way is more convincing than one that exists only at one cutoff.

Numerical precision also matters. Higher $\Lambda$ often requires higher arithmetic precision and tighter control of conformal block approximations.

## Common plots

The identical scalar bootstrap produces several classic plot types.

| Plot | Horizontal axis | Vertical axis | Interpretation |
|---|---|---|---|
| scalar gap bound | $\Delta_\phi$ | first scalar dimension | crossing forces a scalar below the curve |
| $C_T$ bound | $\Delta_\phi$ | $C_T/C_T^{\rm free}$ or similar | stress-tensor exchange cannot be too weak |
| OPE bound | $\Delta_\phi$ or target $\Delta$ | $\lambda^2$ | target coupling is constrained |
| allowed region | two trial dimensions | allowed/excluded shading | not necessarily existence |
| kink plot | any bound curve | sharp feature | possible CFT clue |

These plots are visually seductive. The safe habit is to translate every plot back into a sentence beginning with “Assuming…”

## Common pitfalls

**Do not confuse below the bound with existing.** The bound excludes a region; it does not populate the allowed region with actual CFTs.

**Do not interpret a kink as proof of a CFT.** Kinks are clues. They need support from mixed correlators, spectrum extraction, convergence, and independent evidence.

**Do not forget the identity contribution.** The fixed identity vector is what makes the cone problem nontrivial.

**Do not apply identical-scalar spin selection to non-identical correlators.** Odd spins are absent only in the OPE of identical bosonic scalars.

**Do not hide gap assumptions.** Gaps are physical assumptions and must be stated explicitly.

**Do not compare $C_T$ or OPE bounds across papers without matching conventions.** Normalizations differ.

**Do not treat $\Lambda$ as a physical cutoff.** It is a derivative-search cutoff in the numerical method.

## Relations to other pages

This page follows [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/) and gives the first concrete bootstrap application: one identical scalar four-point function.

The next page, [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), explains how features in bounds become evidence for particular CFTs and how additional spectral assumptions produce islands.

For physics examples, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/).

For method pages, see [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), and [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/).

## Research status

Identical-scalar bounds are established and remain a standard benchmark for numerical conformal bootstrap. They are the simplest setting where exclusion, kinks, OPE bounds, and stress-tensor bounds can be explained clearly.

Active work uses scalar bounds as components of larger systems and as tests for new algorithms. Precision frontiers usually involve mixed correlators, spinning operators, defects, supersymmetry, global symmetry, or navigator-style searches rather than a single identical scalar correlator alone.

## Exercises

### Exercise 1

Explain how a scalar gap bound is obtained by contradiction.

<details><summary><strong>Solution</strong></summary>

Assume the first non-identity scalar has dimension at least $\Delta_{\rm gap}$. This removes all scalar block vectors with

$$
0<\Delta<\Delta_{\rm gap}
$$

from the allowed cone. If a functional is positive on the identity and nonnegative on all remaining allowed operators, applying it to crossing gives a contradiction. Therefore the assumed gap is impossible, and at least one scalar must have

$$
\Delta<\Delta_{\rm gap}.
$$

</details>

### Exercise 2

Why do only even spins appear in the OPE $\phi\times\phi$ for identical bosonic scalars?

<details><summary><strong>Solution</strong></summary>

The three-point function of two identical scalars and a spin-$\ell$ symmetric traceless operator changes by $(-1)^\ell$ when the two scalar positions are exchanged. Because the scalars are identical bosonic operators, the correlator must be symmetric. Thus $(-1)^\ell=1$, so $\ell$ is even.

</details>

### Exercise 3

For a generalized free scalar of dimension $\Delta_\phi$, what is the first scalar dimension in $\phi\times\phi$?

<details><summary><strong>Solution</strong></summary>

The generalized free spectrum contains double-trace operators

$$
[\phi\phi]_{n,\ell}
$$

with dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

The first scalar has $n=0$ and $\ell=0$, so

$$
\Delta_{S,0}^{\rm first}=2\Delta_\phi.
$$

</details>

### Exercise 4

Why is a one-correlator scalar bound usually not enough to prove that a kink is the 3D Ising CFT?

<details><summary><strong>Solution</strong></summary>

A kink is a feature of an exclusion curve. It suggests a special crossing solution but does not by itself identify the full operator spectrum, $\mathbb Z_2$ parity structure, relevant-operator count, or mixed OPE data. The 3D Ising identification becomes precise through mixed-correlator bootstrap with $\sigma$ and $\epsilon$, gap assumptions, convergence, and agreement with other methods.

</details>

### Exercise 5

Why is a bound on $\lambda_{\phi\phi T}^2$ related to a bound on $C_T$?

<details><summary><strong>Solution</strong></summary>

The stress tensor is the conserved current for spacetime symmetry. Ward identities fix the three-point coefficient $\lambda_{\phi\phi T}$ in terms of the scalar dimension $\Delta_\phi$ and the normalization of the stress-tensor two-point function $C_T$. In common conventions,

$$
\lambda_{\phi\phi T}^2\propto\frac{\Delta_\phi^2}{C_T}.
$$

Thus constraining the stress-tensor OPE coefficient constrains $C_T$, after conventions are fixed.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding scalar operator dimensions in 4D CFT,” *Journal of High Energy Physics* **2008**.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.

## Version history

- 2026-07-01: First polished draft. Added scalar gap bound logic, bound-curve interpretation, generalized-free benchmark, stress-tensor and OPE coefficient bounds, gap assumptions, cutoff dependence, exercises, and references.
