---
title: "Four-Point Bootstrap"
description: "How a four-point CFT correlator becomes a concrete bootstrap problem with external data, exchanged spectra, crossing vectors, gaps, and bounds."
sidebar:
  label: "Four-Point Bootstrap"
  order: 3
level: Graduate
status: "Polished draft"
source: "Rattazzi–Rychkov–Tonni–Vichi 2008; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - four-point functions
  - conformal bootstrap
  - crossing symmetry
  - conformal blocks
  - gap assumptions
  - OPE coefficient bounds
canonicalTopics:
  - four-point-bootstrap
  - identical-scalar-bootstrap
  - crossing-vectors
  - bootstrap-bounds
researchStatus:
  established:
    - "Four-point functions are the standard testing ground for the conformal bootstrap because conformal symmetry leaves two cross-ratios and crossing gives nontrivial functional equations."
    - "For unitary identical-scalar correlators, four-point bootstrap equations become positive-sum constraints on conformal-block crossing vectors."
  active:
    - "Modern applications use larger systems of mixed correlators, spinning external operators, rigorous numerics, spectrum extraction, navigator methods, and analytic input to sharpen four-point bootstrap constraints."
---

## Summary

The four-point bootstrap is the practical core of the conformal bootstrap. It starts with one or more four-point correlation functions, expands them in conformal blocks in different OPE channels, and demands that the channel expansions agree.

For one identical scalar primary $\phi$,

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V),
$$

with

$$
\mathcal G(U,V)
=
1+
\sum_{\mathcal O\ne \mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(U,V).
$$

Crossing gives

$$
F_{\mathbf 1}(U,V)+
\sum_{\mathcal O\ne \mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0,
\qquad
\lambda_{\phi\phi\mathcal O}^2\ge0
$$

in a unitary theory. A four-point bootstrap problem is the art of deciding what external correlators to include, what assumptions to impose on the exchanged spectrum, and what conclusion follows if the resulting equation is impossible.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Workflow of a four-point bootstrap problem](/figures/cft-bootstrap/four-point-bootstrap-workflow.svg)

<figcaption>

A four-point bootstrap problem turns a correlator into OPE-channel decompositions, then into crossing vectors. Assumptions about gaps and symmetries define an allowed set. Positivity and linear functionals turn that set into bounds or exclusions.

</figcaption>
</figure>

## Prerequisites

You should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), and [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/).

This page is about setting up and interpreting four-point bootstrap problems. It does not teach the numerical optimization algorithms themselves; those belong in [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/).

## Core idea

A four-point bootstrap problem has three inputs and one output.

| Ingredient | Example | Role |
|---|---|---|
| External data | $\phi$ with dimension $\Delta_\phi$ | Determines the correlator being bootstrapped. |
| Kinematics | Conformal blocks $G_{\Delta,\ell}(U,V)$ | Fixed by conformal symmetry. |
| Assumptions | Unitarity, global symmetry, gaps, known operators | Defines the allowed spectra and OPE data. |
| Output | Exclusion, bound, allowed region, island, extremal spectrum | A conditional statement about possible CFT data. |

The key point is that the four-point function is simple enough to be controlled and complicated enough to contain dynamics. Two- and three-point functions are too constrained by symmetry alone. Four-point functions are the first place where different OPE channels must agree nontrivially.

In slogan form,

$$
\text{four-point bootstrap}
=
\text{two OPE decompositions of one correlator}+
\text{unitarity}.
$$

The same slogan survives in mixed-correlator and spinning bootstrap, although the notation becomes matrix-valued.

## Setup and conventions

We use Euclidean scalar four-point conventions

$$
U=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
V=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2},
$$

and often write

$$
U=z\bar z,
\qquad
V=(1-z)(1-\bar z).
$$

For an identical scalar primary $\phi$ with two-point normalization

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}},
$$

the reduced correlator is

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V).
$$

The $12\to34$ OPE channel gives

$$
\mathcal G(U,V)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(U,V),
$$

where the identity contribution is

$$
G_{0,0}(U,V)=1,
\qquad
\lambda_{\phi\phi\mathbf 1}=1.
$$

The crossing equation comparing the $12\to34$ and $14\to23$ channels is

$$
V^{\Delta_\phi}\mathcal G(U,V)
=
U^{\Delta_\phi}\mathcal G(V,U).
$$

Define

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,\ell}(V,U).
$$

Then the identical scalar bootstrap equation is

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(U,V)=0.
$$

This is the prototype. Most four-point bootstrap systems are elaborations of this equation.

## What is being solved?

The unknowns are not the values of the four-point function at a few points. The unknowns are the CFT data appearing in the OPE:

$$
\{\Delta_\mathcal O,\ell_\mathcal O,\lambda_{\phi\phi\mathcal O}\}_{\mathcal O\in\phi\times\phi}.
$$

For a single identical scalar correlator, crossing asks whether there exists a nonnegative set of OPE weights

$$
p_\mathcal O=\lambda_{\phi\phi\mathcal O}^2\ge0
$$

and an allowed spectrum such that

$$
-F_{\mathbf 1}
=
\sum_{\mathcal O\ne\mathbf 1}p_\mathcal O F_{\Delta,\ell}.
$$

This is not a finite-dimensional linear algebra problem, because the allowed dimensions are continuous and the function space is infinite-dimensional. The bootstrap becomes computational only after choosing a finite family of functionals, such as derivatives at the crossing-symmetric point.

Still, the geometric picture is exact in spirit: can the fixed vector $-F_{\mathbf 1}$ be built from a positive sum of allowed non-identity vectors?

## External data versus assumptions

It is useful to separate the data that define the correlator from the assumptions imposed on the exchanged spectrum.

The external data might be:

- one scalar $\phi$ with dimension $\Delta_\phi$;
- two scalars $\sigma$ and $\epsilon$ with dimensions $(\Delta_\sigma,\Delta_\epsilon)$;
- an $O(N)$ vector $\phi_i$;
- a conserved current $J_\mu$ or stress tensor $T_{\mu\nu}$;
- a defect operator or boundary operator in a defect CFT.

The assumptions might be:

- unitarity bounds in every spin and symmetry sector;
- a gap above the identity in a scalar sector;
- exactly one relevant scalar in a given representation;
- a conserved stress tensor at $\Delta=d$ and spin $2$;
- a conserved current at $\Delta=d-1$ and spin $1$;
- global-symmetry selection rules;
- equality of OPE coefficients across different correlators;
- absence or presence of a low-lying operator motivated by perturbation theory, lattice data, or a known model.

The output is conditional on these assumptions. Bootstrap claims are strongest when the assumptions are minimal, explicit, and stable under enlarging the correlator system.

## The identical scalar problem

The simplest famous problem fixes $\Delta_\phi$ and asks how large the gap to the first scalar in $\phi\times\phi$ can be. Let $\epsilon$ denote the first non-identity scalar in this OPE. Assume

$$
\Delta_{\epsilon}\ge \Delta_*.
$$

The allowed set contains:

$$
\ell=0,\quad \Delta\ge\Delta_*,
$$

and, for even spins $\ell=2,4,6,\ldots$,

$$
\Delta\ge \ell+d-2
$$

in a unitary CFT with $d>2$. Odd spins are absent from the OPE of identical bosonic scalars in a symmetry-trivial channel.

If a positive linear functional excludes the assumption for a given $\Delta_*$, then no such unitary CFT exists. Varying $\Delta_*$ gives an upper bound

$$
\Delta_{\epsilon}
\le
\Delta_{\max}(\Delta_\phi).
$$

A point on this curve is not automatically a CFT. The curve says which gaps have been ruled out by the chosen bootstrap search.

## Four-point bootstrap as a bound machine

A four-point bootstrap setup can produce several kinds of bounds.

| Target | Typical question | Bootstrap output |
|---|---|---|
| Operator dimension | How large can the first scalar gap be? | Upper bound on the first operator in a sector. |
| OPE coefficient | How large or small can $\lambda_{\phi\phi\mathcal O}$ be? | Interval or one-sided bound at fixed dimensions. |
| Central charge | How small can $C_T$ be? | Lower bound on stress-tensor two-point normalization. |
| Current coefficient | How small can $C_J$ be? | Lower bound on current two-point normalization. |
| Allowed region | Which $(\Delta_\sigma,\Delta_\epsilon)$ can occur? | Region in parameter space. |
| Island | Which small region survives mixed correlators and assumptions? | Candidate isolated CFT data. |
| Spectrum | What operators appear at an extremal boundary point? | Approximate extremal spectrum. |

The cleanest result is an exclusion. Allowed regions and islands are more interpretive: they combine exclusions with the failure to exclude the remaining points at a given numerical strength.

## Reading a one-correlator bootstrap plot

A common plot has $\Delta_\phi$ on the horizontal axis and an upper bound on the first scalar dimension on the vertical axis. To read it correctly:

1. Pick a value of $\Delta_\phi$.
2. Move upward in the proposed scalar gap $\Delta_*$.
3. Above the plotted curve, the assumption of no scalar below $\Delta_*$ has been excluded.
4. Below the curve, the assumption has not been excluded by that calculation.

A kink is a sharp change in the boundary. Kinks often signal interesting CFTs because a real solution may sit close to a transition between different optimal functionals. But a kink is a clue, not a theorem. The case becomes stronger if the kink persists under higher derivative order, appears in related correlators, matches independent estimates, and yields a consistent extremal spectrum.

## OPE coefficient bounds

Suppose a particular scalar $\epsilon$ of dimension $\Delta_\epsilon$ appears in $\phi\times\phi$. Separating it gives

$$
F_{\mathbf 1}
+
p_\epsilon F_{\Delta_\epsilon,0}
+
\sum_{\mathcal O\ne\mathbf 1,\epsilon}
p_\mathcal O F_{\Delta,\ell}=0,
\qquad
p_\epsilon=\lambda_{\phi\phi\epsilon}^2.
$$

A linear functional can bound $p_\epsilon$. For example, if

$$
\alpha(F_{\Delta_\epsilon,0})=1,
\qquad
\alpha(F_{\Delta,\ell})\ge0
$$

for all other allowed operators, then applying $\alpha$ gives

$$
p_\epsilon
\le
-\alpha(F_{\mathbf 1})
$$

provided the right side is positive in the chosen normalization. Reversing the sign conditions can produce lower bounds. In practice, OPE coefficient bounds are sensitive to the assumed spectrum, especially gaps above the isolated operator.

## Mixed correlators

The four-point bootstrap becomes much sharper when several correlators are solved together. For example, in a $\mathbb Z_2$-symmetric theory with an odd scalar $\sigma$ and an even scalar $\epsilon$, one studies

$$
\langle\sigma\sigma\sigma\sigma\rangle,
\qquad
\langle\sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle\epsilon\epsilon\epsilon\epsilon\rangle.
$$

An even operator $\mathcal O$ appearing in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$ carries an OPE coefficient vector

$$
\vec\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

Its contribution is controlled by the positive semidefinite matrix

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}.
$$

This is why mixed-correlator bootstrap problems naturally lead to semidefinite programming. The same operator must satisfy several crossing equations at once, with shared dimensions and shared OPE data. That is much harder to fake than satisfying one equation in isolation.

## Global symmetry channels

If the external operator transforms under a global symmetry, the four-point function decomposes into symmetry representations. For an $O(N)$ vector $\phi_i$,

$$
\mathbf N\otimes\mathbf N=S\oplus T\oplus A,
$$

where $S$ is singlet, $T$ is symmetric traceless, and $A$ is antisymmetric. The bootstrap equation becomes a vector equation with sums over sectors:

$$
\sum_{\mathcal O\in S}p_\mathcal O\vec F^{\,S}_{\Delta,\ell}
+
\sum_{\mathcal O\in T}p_\mathcal O\vec F^{\,T}_{\Delta,\ell}
+
\sum_{\mathcal O\in A}p_\mathcal O\vec F^{\,A}_{\Delta,\ell}
=0.
$$

Each vector combines spacetime block kinematics with group-theory crossing matrices. Spin selection rules also depend on the symmetry channel. In identical bosonic four-point functions, symmetric internal channels pair with even spacetime spin, while antisymmetric channels pair with odd spin.

## Checks on a four-point setup

Before trusting a bound, check the following.

| Check | Why it matters |
|---|---|
| Identity normalization | A wrong identity coefficient shifts the whole equation. |
| Two-point normalization | OPE coefficients and central charges depend on it. |
| Spin selection rules | Including forbidden spins weakens or corrupts the problem. |
| Unitarity bounds | These define the baseline allowed region. |
| Conserved operators | Currents and stress tensors sit at shortening thresholds. |
| Global-symmetry crossing matrices | Wrong representation algebra gives the wrong vector equation. |
| Derivative parity | Symmetries around $z=\bar z=1/2$ remove redundant derivatives. |
| Numerical stability | Bounds should improve or stabilize as the search space grows. |

A surprisingly large number of bootstrap mistakes are not conceptual. They are normalization, channel, or bookkeeping errors wearing a tiny fake mustache.

## Common pitfalls

| Pitfall | Repair |
|---|---|
| Saying the four-point bootstrap “solves” a theory from one correlator. | One correlator constrains one slice of the CFT data. A full solution needs all correlators or a complete reconstruction argument. |
| Confusing excluded and allowed regions. | Excluded means certified contradiction. Allowed usually means not excluded at the chosen numerical strength. |
| Treating a kink as proof of a CFT. | Use it as evidence and test it with stronger systems and independent data. |
| Forgetting assumptions behind an island. | Islands often require gaps, symmetry assignments, or uniqueness assumptions. State them. |
| Comparing OPE coefficients across conventions. | Match two-point normalizations, block normalizations, and stress-tensor/current conventions first. |
| Ignoring degeneracies. | Degenerate operators contribute sums of squares or positive matrices, not a single signed coefficient. |
| Using single-correlator intuition in a mixed system. | Mixed systems require matrix positivity and shared OPE data. |
| Assuming all useful correlators are scalar. | Spinning correlators and conserved-current correlators can be essential for central charges, collider bounds, and symmetry data. |

## Relations to other pages

- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) explains why different OPE channels must agree.
- [Bootstrap Equations](/cft-bootstrap/crossing-bootstrap-logic/bootstrap-equations/) develops the crossing-vector and cone language used here.
- [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) explains why OPE weights and coefficient matrices are positive in unitary systems.
- [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/) specializes the setup to the classic single-correlator problem.
- [Mixed Correlator Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/mixed-correlator-bootstrap/) develops the matrix-valued version in detail.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) and [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) explain the block functions used in practical calculations.
- [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) and [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) turn the logic into algorithms.

## Research status

The four-point bootstrap is a mature framework. The basic identical-scalar crossing equation, gap bounds, OPE coefficient bounds, global-symmetry decomposition, and mixed-correlator semidefinite formulation are standard tools.

Active work is less about whether four-point bootstrap works and more about how much it can extract. Current directions include larger mixed systems, spinning correlators, stress-tensor and current bootstrap, defect four-point functions, rigorous numerical certificates, extremal spectra, navigator methods, skydive-type searches, analytic lightcone input, and hybrid approaches that combine perturbation theory with nonperturbative constraints.

## Exercises

### Exercise 1: The gap bound as an exclusion statement

Fix $\Delta_\phi$ and assume that the first scalar in $\phi\times\phi$ has dimension at least $\Delta_*$. Explain why excluding this assumption implies an upper bound on the first scalar dimension.

<details><summary><strong>Solution</strong></summary>

If the assumption $\Delta_{\epsilon}\ge\Delta_*$ is excluded, then no unitary CFT satisfying the rest of the setup can have all scalar operators above $\Delta_*$. Therefore any such CFT must contain a scalar with

$$
\Delta_\epsilon<\Delta_*.
$$

By varying $\Delta_*$, the boundary between excluded and not-excluded assumptions gives an upper bound on $\Delta_\epsilon$ as a function of $\Delta_\phi$.

</details>

### Exercise 2: Why only even spins for identical scalars?

For identical bosonic scalar operators in a symmetry-trivial OPE channel, explain why odd-spin primary exchange is absent.

<details><summary><strong>Solution</strong></summary>

Interchanging the two identical scalars sends $x_{12}\to -x_{12}$. A spin-$\ell$ contribution changes by $(-1)^\ell$ under this exchange in the leading OPE tensor structure. The product $\phi(x_1)\phi(x_2)$ is symmetric because the operators are identical bosonic scalars at separated Euclidean points. Therefore only even $\ell$ can appear in the symmetry-trivial channel. If there is an antisymmetric internal-symmetry channel, the internal wavefunction contributes an extra minus sign, so odd spacetime spins can appear there.

</details>

### Exercise 3: OPE coefficient upper bound

Assume crossing has the form

$$
F_{\mathbf 1}+p_*F_*+
\sum_i p_iF_i=0,
\qquad
p_i\ge0.
$$

Suppose a functional $\alpha$ obeys

$$
\alpha(F_*)=1,
\qquad
\alpha(F_i)\ge0.
$$

Show that $p_*\le -\alpha(F_{\mathbf 1})$.

<details><summary><strong>Solution</strong></summary>

Apply $\alpha$ to crossing:

$$
0=\alpha(F_{\mathbf 1})+p_*+
\sum_i p_i\alpha(F_i).
$$

Since $p_i\ge0$ and $\alpha(F_i)\ge0$,

$$
\sum_i p_i\alpha(F_i)\ge0.
$$

Thus

$$
p_*=-\alpha(F_{\mathbf 1})-
\sum_i p_i\alpha(F_i)
\le
-\alpha(F_{\mathbf 1}).
$$

This is the basic logic behind OPE coefficient upper bounds.

</details>

### Exercise 4: Why mixed correlators are stronger

Give one reason why adding $\langle\sigma\sigma\epsilon\epsilon\rangle$ and $\langle\epsilon\epsilon\epsilon\epsilon\rangle$ can shrink an allowed region obtained from $\langle\sigma\sigma\sigma\sigma\rangle$ alone.

<details><summary><strong>Solution</strong></summary>

A single correlator only sees OPE coefficients in $\sigma\times\sigma$. Mixed correlators force the same exchanged operators to appear consistently in several OPEs, such as $\sigma\times\sigma$, $\sigma\times\epsilon$, and $\epsilon\times\epsilon$. The dimensions and OPE coefficients cannot be chosen independently in each channel. This shared-data constraint produces matrix positivity conditions and can exclude spectra that survive the single-correlator test.

</details>

## References

- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding scalar operator dimensions in 4D CFT,” 2008.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, lectures on four-point functions and the numerical bootstrap.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, sections on four-point functions, crossing, reflection positivity, and semidefinite programming.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” sections on CFT techniques and numerical methods.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” review of recent algorithmic and software developments.

## Version history

- 2026-06-28: First polished draft. Added the four-point bootstrap workflow, identical-scalar setup, gap and OPE coefficient bounds, mixed-correlator and global-symmetry extensions, interpretation guidance, exercises, and a workflow figure.
