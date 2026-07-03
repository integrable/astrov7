---
title: "Running in EFT"
description: "How Wilson coefficients and operator matrix elements evolve with renormalization scale inside an effective field theory."
sidebar:
  label: "Running in EFT"
  order: 7
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II, ch. 18; Burgess 2020, chs. 2–3; Schwartz 2014, chs. 22–23; Srednicki 2007, §§28–29; Manohar EFT lectures; Buras weak Hamiltonian reviews."
topics:
  - effective field theory
  - Wilson coefficients
  - anomalous dimensions
  - operator mixing
  - renormalization group evolution
canonicalTopics:
  - running-in-effective-field-theory
  - wilson-coefficient-running
  - anomalous-dimension-matrix
  - operator-mixing
researchStatus:
  established:
    - "Wilson-coefficient running and operator anomalous dimensions are standard EFT tools for summing logarithms between matching and measurement scales."
  active:
    - "Running in multi-scale EFTs remains technically active in SMEFT, weak effective Hamiltonians, SCET, heavy-particle EFTs, nuclear EFT, finite-temperature EFT, and automated matching-and-running pipelines."
---

## Summary

After matching, an effective field theory usually contains Wilson coefficients defined at a scale near a heavy threshold,

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}
+
\sum_i C_i(\mu_M)\mathcal O_i(\mu_M),
\qquad
\mu_M\sim M.
$$

Low-energy matrix elements are often evaluated at a much lower scale,

$$
\mu_Q\sim Q,
\qquad Q\ll M.
$$

**Running in EFT** is the renormalization-group evolution that carries the coefficients from $\mu_M$ to $\mu_Q$ while keeping physical predictions independent of the arbitrary renormalization scale. It is the middle step in the EFT pipeline:

$$
\text{match at }\mu_M
\quad\longrightarrow\quad
\text{run to }\mu_Q
\quad\longrightarrow\quad
\text{compute low-energy matrix elements}.
$$

The essential equation is

$$
\mu\frac{d}{d\mu}
\left[
\sum_i C_i(\mu)\mathcal O_i(\mu)
\right]
=0,
$$

up to truncation errors and explicit thresholds. The coefficient and the operator separately depend on $\mu$; their product does not.

:::note[Why running matters]
Matching at $\mu\sim M$ avoids large logarithms of $M/\mu$. Matrix elements at $\mu\sim Q$ avoid large logarithms of $Q/\mu$. Running connects the two choices and resums logarithms of $M/Q$.
:::

## Prerequisites

You should know [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Cutoff versus Renormalization Scale](/renormalization-rg-eft/effective-field-theory/cutoff-versus-renormalization-scale/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

Useful background includes [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), and [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/).

## Core idea

An EFT separates two tasks that are easy to confuse.

The matching calculation determines Wilson coefficients at a scale where the heavy physics is still visible:

$$
C_i(\mu_M)
\quad\text{from short-distance physics near }M.
$$

The low-energy calculation evaluates operator matrix elements at a scale where the long-distance physics is natural:

$$
\langle f|\mathcal O_i(\mu_Q)|i\rangle
\quad\text{from light degrees of freedom near }Q.
$$

If $M\gg Q$, a fixed-order calculation performed at one scale contains logarithms like

$$
\alpha\log\frac{M}{Q},
\qquad
\alpha^2\log^2\frac{M}{Q},
\qquad
\alpha^3\log^3\frac{M}{Q},
\qquad \ldots
$$

When these logarithms are numerically large, the loop expansion is no longer organized only by powers of $\alpha$. Running reorganizes the perturbative series by solving RG equations.

The EFT logic is therefore:

$$
\text{short-distance constants}
+
\text{RG evolution}
+
\text{long-distance matrix elements}.
$$

That is not just bookkeeping. It is the reason EFTs can make reliable predictions when the microscopic and observed scales are widely separated.

## Setup and conventions

We use the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). For renormalized composite operators,

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b}(\mu),
$$

with anomalous-dimension matrix

$$
\gamma_a{}^b
\equiv
(Z^{-1})_a{}^c
\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

Then the renormalized operators satisfy

$$
\left.\mu\frac{d}{d\mu}\mathcal O_a(\mu)\right|_{\text{bare}}
=
-\gamma_a{}^b\mathcal O_b(\mu).
$$

Write the EFT interaction as a row-vector times a column-vector,

$$
\mathcal L_{\text{EFT}}
\supset
C^T(\mu)\mathcal O(\mu)
=
\sum_a C_a(\mu)\mathcal O_a(\mu).
$$

Scale independence gives

$$
\mu\frac{d}{d\mu}
\left[C^T(\mu)\mathcal O(\mu)\right]=0,
$$

so the Wilson coefficients obey

$$
\boxed{
\mu\frac{dC}{d\mu}=\gamma^T C
}
$$

in this convention. In components,

$$
\mu\frac{dC_a}{d\mu}=\gamma_b{}^a C_b.
$$

Some EFT literature defines the anomalous-dimension matrix with the opposite sign or transposes the operator vector. Before comparing formulas, identify which convention is being used. This page uses the convention above throughout.

## The Wilson-coefficient evolution matrix

The formal solution of

$$
\frac{dC}{d\log\mu}=\gamma^T(g(\mu))C
$$

is

$$
C(\mu_2)=U(\mu_2,\mu_1)C(\mu_1),
$$

where the evolution matrix satisfies

$$
\frac{d}{d\log\mu_2}U(\mu_2,\mu_1)
=
\gamma^T(g(\mu_2))U(\mu_2,\mu_1),
\qquad
U(\mu_1,\mu_1)=\mathbf 1.
$$

If $\gamma(\mu)$ commuted with itself at different scales, the solution would simply be

$$
U(\mu_2,\mu_1)=
\exp\left[
\int_{\log\mu_1}^{\log\mu_2}dt\,\gamma^T(g(t))
\right].
$$

In general, matrices at different scales need not commute, and the formal solution is path ordered:

$$
U(\mu_2,\mu_1)=
P\exp\left[
\int_{\log\mu_1}^{\log\mu_2}dt\,\gamma^T(g(t))
\right].
$$

For many leading-order applications, one diagonalizes a constant leading anomalous-dimension matrix and evolves eigen-combinations of operators separately. At higher orders, scheme choices and non-commuting matrices require more care.

## Single-operator running

If there is only one operator, the matrix notation disappears. Suppose

$$
\mu\frac{dC}{d\mu}=\gamma(g)C,
\qquad
\mu\frac{dg}{d\mu}=\beta(g).
$$

Then

$$
\frac{d\log C}{dg}=\frac{\gamma(g)}{\beta(g)},
$$

so

$$
C(\mu)=C(\mu_0)
\exp\left[
\int_{g(\mu_0)}^{g(\mu)}dg\,\frac{\gamma(g)}{\beta(g)}
\right].
$$

At leading order, let

$$
\gamma(g)=\gamma_0\frac{g^2}{16\pi^2}+O(g^4),
\qquad
\beta(g)=b_0\frac{g^3}{16\pi^2}+O(g^5).
$$

Then

$$
C(\mu)=C(\mu_0)
\left[\frac{g^2(\mu)}{g^2(\mu_0)}\right]^{\gamma_0/(2b_0)}
$$

when $b_0\ne0$. If the beta function is written with a minus sign, as in asymptotically free gauge theory,

$$
\beta_g=-\beta_0\frac{g^3}{16\pi^2}+\cdots,
$$

then substitute $b_0=-\beta_0$ in the formula. The sign is not decoration; it decides whether the coefficient grows or shrinks toward the infrared.

## What running resums

Consider a coefficient matched at $\mu_M\sim M$ and used at $\mu_Q\sim Q$. A fixed-order result might look like

$$
C(\mu_Q)
=
C(\mu_M)
\left[
1
+\frac{\gamma_0\alpha}{4\pi}\log\frac{\mu_Q}{\mu_M}
+O(\alpha^2)
\right].
$$

Repeated insertions generate higher powers,

$$
\left(\alpha\log\frac{\mu_Q}{\mu_M}\right)^n.
$$

Solving the RG equation resums an infinite tower of these logarithms. The standard accuracy hierarchy is:

| Accuracy | What is controlled schematically |
|---|---|
| leading logarithmic (LL) | $\alpha^n L^n$ |
| next-to-leading logarithmic (NLL) | $\alpha^n L^{n-1}$ |
| next-to-next-to-leading logarithmic (NNLL) | $\alpha^n L^{n-2}$ |

where

$$
L=\log\frac{M}{Q}.
$$

This table is schematic. The exact counting depends on whether the leading process starts at tree level or loop level, and on how the coupling itself runs.

## Operator mixing during running

If the EFT contains several operators with the same symmetries, renormalization usually mixes them:

$$
\mu\frac{d}{d\mu}
\begin{pmatrix}
C_1\\
C_2\\
\vdots
\end{pmatrix}
=
\begin{pmatrix}
\gamma_1{}^1 & \gamma_2{}^1 & \cdots\\
\gamma_1{}^2 & \gamma_2{}^2 & \cdots\\
\vdots & \vdots & \ddots
\end{pmatrix}
\begin{pmatrix}
C_1\\
C_2\\
\vdots
\end{pmatrix}.
$$

This means a coefficient that vanishes at the matching scale can be generated at lower scales. For example,

$$
C_2(\mu_M)=0
$$

need not imply

$$
C_2(\mu_Q)=0.
$$

Running follows the symmetries and basis relations of the EFT, not the reader's wish list.

In mass-independent schemes such as MS and $\overline{\mathrm{MS}}$, operators of the same engineering dimension and quantum numbers often mix among themselves. Lower-dimensional operators can also enter when relevant masses, symmetry breaking, power divergences, or non-minimal subtraction schemes are present. Pages using a particular operator basis should state which redundancies have been quotiented out.

## Matching, running, and matrix elements

The physical amplitude has the form

$$
\mathcal A(Q)
=
\sum_i C_i(\mu)\langle f|\mathcal O_i(\mu)|i\rangle_Q.
$$

The coefficient running is only half the story. Matrix elements also run:

$$
\mu\frac{d}{d\mu}\langle\mathcal O_i(\mu)\rangle_Q
=-\gamma_i{}^j\langle\mathcal O_j(\mu)\rangle_Q.
$$

Thus the scale dependence cancels:

$$
\mu\frac{d\mathcal A}{d\mu}=0.
$$

At finite order, the cancellation is imperfect because the matching, anomalous dimensions, matrix elements, and power expansion have all been truncated. Residual $\mu$ dependence is therefore a diagnostic of missing higher-order terms, not a physical effect by itself.

:::tip[Choose scales to avoid large logs]
A practical EFT calculation usually chooses $\mu_M\sim M$ for matching and $\mu_Q\sim Q$ for matrix elements. Then running handles the logarithm between them. Choosing one scale for everything is legal, but often silly.
:::

## Thresholds and chains of EFTs

Running is done inside a fixed EFT. If the scale crosses a particle mass or another physical threshold, the EFT itself may need to change.

For a hierarchy

$$
M_1\gg M_2\gg Q,
$$

a typical chain is

$$
\text{full theory}
\xrightarrow{\text{match at }M_1}
\text{EFT}_1
\xrightarrow{\text{run}}
\xrightarrow{\text{match at }M_2}
\text{EFT}_2
\xrightarrow{\text{run}}
\text{matrix element at }Q.
$$

Do not run through thresholds blindly. The anomalous dimensions below a threshold are computed with the degrees of freedom that remain dynamical below that threshold. Heavy fields appear in boundary conditions for Wilson coefficients, not in loops of the lower-energy EFT.

This point is especially important in QCD, weak effective Hamiltonians, SMEFT-to-LEFT matching, HQET, SCET, chiral perturbation theory, and finite-temperature dimensional reduction.

## Running is not matching

Running and matching answer different questions.

| Task | Question answered | Physics included |
|---|---|---|
| matching | What local coefficients reproduce the heavy theory at a threshold? | short-distance threshold effects |
| running | How do coefficients change when the renormalization scale changes inside one EFT? | logarithmic light-field renormalization |
| matrix elements | What does the operator do between low-energy states? | long-distance dynamics |

A common error is to compute a large logarithm in the full theory and call it matching. A cleaner EFT calculation separates the hard part at $M$ from the logarithmic evolution between $M$ and $Q$.

In dimensional regularization, this separation can be made very sharp. The full-theory hard region fixes Wilson coefficients. The EFT loops reproduce soft long-distance behavior. Matching subtracts the common infrared physics, and running evolves the coefficient after the heavy modes have been removed.

## A model for intuition: four-fermion operators

Suppose a heavy vector boson of mass $M$ mediates an interaction among light fermions. At low energy, tree-level matching gives a four-fermion operator,

$$
\mathcal L_{\text{EFT}}
\supset
C(\mu_M)(\bar\psi\gamma^\mu\psi)(\bar\chi\gamma_\mu\chi),
\qquad
C(\mu_M)\sim \frac{g^2}{M^2}.
$$

If the light fermions also interact through a gauge force, loops below $M$ renormalize the four-fermion operator. The coefficient at the low scale is not simply $g^2/M^2$; it is

$$
C(\mu_Q)=U(\mu_Q,\mu_M)C(\mu_M).
$$

The factor $U$ contains the effect of light gauge bosons and light fermions between the two scales. It does not contain the heavy vector as a dynamical field. That heavy field has already done its job by setting the boundary condition $C(\mu_M)$.

This is the conceptual skeleton behind weak effective Hamiltonians, heavy-quark decays, flavor EFTs, and many nonrelativistic EFTs.

## Scheme dependence

Wilson coefficients are not observables. They depend on:

- the renormalization scheme;
- the operator basis;
- the normalization of operators;
- the treatment of evanescent operators in dimensional regularization;
- the matching scale and threshold conventions;
- the truncation order.

This is not a bug. Matrix elements depend on the same choices in the opposite way. A quoted Wilson coefficient without a scheme and basis is not a physical number.

For example, in dimensional regularization, operators that vanish in exactly four dimensions but not in $d=4-2\epsilon$ can affect finite parts through products like

$$
\epsilon\times\frac{1}{\epsilon}.
$$

Such **evanescent operators** are not optional in precision multi-loop EFT calculations. They belong to the bookkeeping that makes the final answer scheme consistent.

## Common pitfalls

**Running the full theory below a heavy threshold.** Below $M$, the heavy field is not a dynamical degree of freedom in the EFT. Its effect is in Wilson coefficients and threshold corrections.

**Calling Wilson coefficients physical.** A Wilson coefficient is a coordinate in a chosen scheme and basis. The physical object is the full amplitude or observable.

**Ignoring operator mixing.** Symmetry-allowed operators generally mix. Setting a coefficient to zero at one scale does not prove it is zero at another scale.

**Choosing $\mu=Q$ during matching by habit.** Matching is normally cleanest at $\mu\sim M$. Low-energy matrix elements are normally cleanest at $\mu\sim Q$.

**Using anomalous dimensions with inconsistent conventions.** Some references use $\mu dC/d\mu=\gamma C$, some use $\mu dC/d\mu=-\gamma^T C$, and some define $\gamma$ for operators with the opposite sign. Compare definitions, not just formulas.

**Forgetting that power corrections also matter.** RG running resums logarithms. It does not include omitted higher-dimension operators unless those operators are present in the EFT basis.

## Relations to other pages

[Matching](/renormalization-rg-eft/effective-field-theory/matching/) fixes the initial conditions for Wilson coefficients. This page evolves them. The next major conceptual step is decoupling: understanding why heavy degrees of freedom can be replaced by local operators in the first place.

[Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) provide the operator-language infrastructure behind the coefficient RG equations.

[RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/) explains the same large-log resummation logic in general perturbative QFT. This page specializes that logic to EFT Wilson coefficients and operator matrix elements.

## Research status

The conceptual structure of running in EFT is settled. Wilson coefficients evolve by anomalous-dimension matrices, and physical amplitudes are independent of the arbitrary renormalization scale when matching, running, and matrix elements are treated consistently.

The technically active part is not the idea, but the execution: high-loop anomalous dimensions, large operator bases, evanescent operators, thresholds, flavor structures, helicity bases, nonrelativistic power counting, rapidity renormalization in SCET, finite-temperature scale hierarchies, and automated matching-and-running workflows.

## Exercises

### Exercise 1: Derive the coefficient RG equation

Let

$$
\mathcal O_0=Z\mathcal O(\mu),
\qquad
\gamma=Z^{-1}\mu\frac{dZ}{d\mu},
$$

so that

$$
\mu\frac{d\mathcal O}{d\mu}=-\gamma\mathcal O.
$$

For an interaction $C^T\mathcal O$, derive the RG equation obeyed by $C$.

<details><summary><strong>Solution</strong></summary>

Scale independence requires

$$
0=\mu\frac{d}{d\mu}(C^T\mathcal O)
=\left(\mu\frac{dC^T}{d\mu}\right)\mathcal O
+C^T\left(\mu\frac{d\mathcal O}{d\mu}\right).
$$

Using

$$
\mu\frac{d\mathcal O}{d\mu}=-\gamma\mathcal O,
$$

we get

$$
0=\left(\mu\frac{dC^T}{d\mu}-C^T\gamma\right)\mathcal O.
$$

Since the renormalized operators are independent basis elements,

$$
\mu\frac{dC^T}{d\mu}=C^T\gamma.
$$

Equivalently,

$$
\mu\frac{dC}{d\mu}=\gamma^T C.
$$

</details>

### Exercise 2: Solve single-operator running

Suppose

$$
\mu\frac{dC}{d\mu}=\gamma_0\frac{g^2}{16\pi^2}C,
\qquad
\mu\frac{dg}{d\mu}=b_0\frac{g^3}{16\pi^2}.
$$

Show that

$$
C(\mu)=C(\mu_0)
\left[\frac{g^2(\mu)}{g^2(\mu_0)}\right]^{\gamma_0/(2b_0)}.
$$

<details><summary><strong>Solution</strong></summary>

Divide the two RG equations:

$$
\frac{d\log C}{dg}
=
\frac{\gamma_0 g^2/(16\pi^2)}{b_0 g^3/(16\pi^2)}
=
\frac{\gamma_0}{b_0}\frac{1}{g}.
$$

Integrating from $g(\mu_0)$ to $g(\mu)$ gives

$$
\log\frac{C(\mu)}{C(\mu_0)}
=
\frac{\gamma_0}{b_0}
\log\frac{g(\mu)}{g(\mu_0)}.
$$

Therefore

$$
C(\mu)=C(\mu_0)
\left[\frac{g(\mu)}{g(\mu_0)}\right]^{\gamma_0/b_0}
=
C(\mu_0)
\left[\frac{g^2(\mu)}{g^2(\mu_0)}\right]^{\gamma_0/(2b_0)}.
$$

</details>

### Exercise 3: Why coefficient running cancels operator running

Assume $C$ and $\mathcal O$ obey

$$
\mu\frac{dC}{d\mu}=\gamma^T C,
\qquad
\mu\frac{d\mathcal O}{d\mu}=-\gamma\mathcal O.
$$

Show that $C^T\mathcal O$ is scale independent.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\mu\frac{d}{d\mu}(C^T\mathcal O)
=
(\gamma^T C)^T\mathcal O
+C^T(-\gamma\mathcal O).
$$

Since

$$
(\gamma^T C)^T=C^T\gamma,
$$

the two terms cancel:

$$
C^T\gamma\mathcal O-C^T\gamma\mathcal O=0.
$$

Thus the interaction written as $C^T\mathcal O$ is independent of the arbitrary renormalization scale.

</details>

### Exercise 4: Threshold discipline

A theory has heavy particles of masses $M_1\gg M_2\gg Q$. Explain why a single running calculation from $M_1$ to $Q$ in one EFT is usually not the right organization.

<details><summary><strong>Solution</strong></summary>

Between $M_1$ and $M_2$, the particle of mass $M_2$ is still a dynamical low-energy field relative to $M_1$. Below $M_2$, it should be removed from the EFT and replaced by local operators and threshold corrections. Therefore the clean sequence is

$$
\text{match at }M_1,
\quad
\text{run to }M_2,
\quad
\text{match at }M_2,
\quad
\text{run to }Q.
$$

This avoids using anomalous dimensions with the wrong field content below a threshold and avoids putting threshold physics into ordinary running.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, matching, and mass effects in field theory.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3, for Wilson actions, matching, exact RG logic, and power counting.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 22–23, for nonrenormalizable theories, RG equations, and Wilsonian intuition.
- Mark Srednicki, *Quantum Field Theory*, sections on the renormalization group and effective field theory.
- Aneesh Manohar, EFT lectures and reviews, for practical Wilson-coefficient running and operator-basis technology.
- Andrzej Buras, weak effective Hamiltonian reviews, for a classic precision setting where matching, anomalous dimensions, and coefficient evolution are essential.

## Version history

- 2026-06-18: First polished draft. Added conventions for Wilson-coefficient running, operator anomalous dimensions, evolution matrices, threshold matching, and scheme dependence.
