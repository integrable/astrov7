---
title: "3D Ising CFT"
description: "The conformal field theory describing the three-dimensional Ising universality class, including its leading operators, CFT data, critical exponents, and bootstrap interpretation."
sidebar:
  label: "3D Ising CFT"
  order: 10
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; recent 3D Ising bootstrap literature; standard critical-phenomena references."
topics:
  - 3D Ising CFT
  - Ising universality class
  - conformal bootstrap
  - critical exponents
  - higher-dimensional CFT
canonicalTopics:
  - three-dimensional-ising-cft
  - ising-universality-class
  - bootstrap-island
researchStatus:
  established:
    - "The 3D Ising universality class is a unitary conformal field theory with Z2 global symmetry and a highly constrained low-lying spectrum."
  active:
    - "Precision determinations of subleading CFT data, stress-tensor data, higher-spin trajectories, line and surface defects, and off-critical deformations remain active research areas."
---

## Summary

The **3D Ising CFT** is the conformal field theory that describes the critical point of the three-dimensional Ising universality class. It is the infrared fixed point of a real scalar theory with $\mathbb Z_2$ symmetry,

$$
\phi\mapsto -\phi,
$$

and it describes many microscopic systems with one real order parameter and a second-order phase transition.

The two most important scalar primary operators are the $\mathbb Z_2$-odd spin operator $\sigma$ and the $\mathbb Z_2$-even energy operator $\epsilon$. Current high-precision bootstrap determinations give approximately

$$
\Delta_\sigma\approx0.518148806,
\qquad
\Delta_\epsilon\approx1.41262528.
$$

These two numbers determine the standard thermal and magnetic critical exponents by scaling relations. For example, in $d=3$,

$$
\nu=\frac{1}{3-\Delta_\epsilon}\approx0.629971,
\qquad
\eta=2\Delta_\sigma-1\approx0.036298.
$$

This page explains the CFT data viewpoint on the 3D Ising model: the symmetry, leading operators, OPE channels, relation to critical exponents, bootstrap island logic, and common traps when translating between lattice, Landau–Ginzburg, and CFT language.

## Prerequisites

Read [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/), [Conformal Symmetry in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/conformal-symmetry-in-higher-dimensions/), [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/), [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), and [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) first.

For the bootstrap side, you should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), and the idea that a CFT is specified by operator dimensions and OPE coefficients.

## Core idea

The microscopic Ising model has spins

$$
s_i=\pm1
$$

on a lattice, with a nearest-neighbor Hamiltonian such as

$$
H=-J\sum_{\langle ij\rangle}s_i s_j.
$$

At its critical temperature, the correlation length diverges. Long-distance physics forgets most lattice details and is described by a continuum CFT. The order parameter becomes a scalar primary $\sigma(x)$, and the temperature-like perturbation becomes a scalar primary $\epsilon(x)$.

The continuum slogan is

$$
\text{critical Ising lattice model in 3D}
\quad\longrightarrow\quad
\text{unitary }\mathbb Z_2\text{-symmetric CFT}.
$$

The CFT is not free. It is the interacting Wilson–Fisher fixed point of a one-component scalar theory. It has no known closed-form solution, but its low-lying CFT data are known with extraordinary precision from the conformal bootstrap, Monte Carlo, high-temperature expansions, and the renormalization group.

The modern viewpoint is that the 3D Ising CFT is not defined by a preferred Lagrangian. It is defined by its conformal data:

$$
\{\Delta_i,\ell_i,\mathbb Z_2\text{ parity},\lambda_{ijk}\}.
$$

## Setup and conventions

We work in three Euclidean dimensions:

$$
d=3.
$$

The conformal group is locally

$$
SO(4,1).
$$

The global internal symmetry is

$$
\mathbb Z_2.
$$

Operators are labeled by scaling dimension, spin, and $\mathbb Z_2$ parity. The leading scalar primaries are conventionally named:

| Operator | Spin | $\mathbb Z_2$ parity | Physical role |
|---|---:|---:|---|
| $\mathbf 1$ | $0$ | even | identity operator |
| $\sigma$ | $0$ | odd | spin/order-parameter operator |
| $\epsilon$ | $0$ | even | energy/thermal operator |
| $T_{\mu\nu}$ | $2$ | even | stress tensor |
| $\epsilon'$ | $0$ | even | leading irrelevant scalar in the even sector |
| $\sigma'$ | $0$ | odd | next odd scalar |

The normalization of two-point functions is usually chosen as

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

With this convention, OPE coefficients such as $\lambda_{\sigma\sigma\epsilon}$ are physical CFT data up to signs fixed by operator conventions.

## Landau–Ginzburg description

A useful continuum route to the 3D Ising universality class is the Euclidean scalar theory

$$
S=\int d^d x\left[\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{g}{4!}\phi^4\right],
$$

with $\phi\mapsto-\phi$. In $d=4-\varepsilon$, this theory has the Wilson–Fisher fixed point. Continuing to $d=3$ gives a powerful qualitative and quantitative approximation.

At the fixed point, the microscopic field $\phi$ flows to the CFT operator $\sigma$, and the tuning parameter $r$ couples to $\epsilon$:

$$
\phi\rightsquigarrow \sigma,
\qquad
\phi^2\rightsquigarrow \epsilon+	ext{descendants and mixing}.
$$

The arrows are not literal operator equalities. They mean that the corresponding microscopic operators have leading overlap with the indicated scaling operators in the infrared.

The fixed-point action is not obtained by merely setting $r=0$ in a classical potential. Quantum fluctuations move the theory to a nontrivial interacting CFT.

## Operator sectors

Because of $\mathbb Z_2$ symmetry, the OPE decomposes into parity sectors.

The odd-even fusion rules are schematic selection rules:

$$
\text{even}\times\text{even}=\text{even},
$$

$$
\text{even}\times\text{odd}=\text{odd},
$$

$$
\text{odd}\times\text{odd}=\text{even}.
$$

The most important OPEs are

$$
\sigma\times\sigma=\mathbf1+\epsilon+T+\epsilon'+\cdots,
$$

$$
\sigma\times\epsilon=\sigma+\sigma'+\cdots,
$$

and

$$
\epsilon\times\epsilon=\mathbf1+\epsilon+T+\epsilon'+\cdots .
$$

Spin selection also matters. In the OPE of two identical scalars, exchanged symmetric traceless tensors have even spin. Thus $\sigma\times\sigma$ and $\epsilon\times\epsilon$ contain even-spin operators, while mixed OPEs such as $\sigma\times\epsilon$ can contain both even and odd spin.

## Benchmark CFT data

The leading dimensions are often quoted as

$$
\Delta_\sigma=0.518148806(24),
\qquad
\Delta_\epsilon=1.41262528(29),
$$

where the parentheses indicate uncertainty in the final quoted digits in a recent high-precision bootstrap determination. These values are representative benchmark numbers; for precision work, always specify the source, assumptions, normalization, and date of the data.

Some other useful qualitative facts are:

| Data | Meaning |
|---|---|
| $\Delta_\sigma<1$ | The order parameter is relevant and has a small anomalous dimension. |
| $\Delta_\epsilon<3$ | The temperature perturbation is relevant. |
| $\Delta_T=3$ | The stress tensor is conserved. |
| $\Delta_{\epsilon'}>3$ | The leading even scalar after $\epsilon$ is irrelevant. |
| no conserved spin $>2$ | The theory is interacting, not a free higher-spin theory. |

The low-lying spectrum is sparse enough that mixed-correlator bootstrap equations isolate a small island in the $(\Delta_\sigma,\Delta_\epsilon)$ plane. This island is one of the flagship achievements of the numerical conformal bootstrap.

## Critical exponents from CFT data

Statistical mechanics often uses critical exponents rather than operator dimensions. In the Ising universality class, the thermal exponent is

$$
y_t=d-\Delta_\epsilon,
$$

and the magnetic exponent is

$$
y_h=d-\Delta_\sigma.
$$

The correlation-length exponent is

$$
\nu=\frac1{y_t}=\frac1{d-\Delta_\epsilon}.
$$

In $d=3$, using the benchmark values above,

$$
\nu\approx0.629971.
$$

The anomalous dimension $\eta$ is related to $\Delta_\sigma$ by

$$
\Delta_\sigma=\frac{d-2+\eta}{2},
$$

so in $d=3$,

$$
\eta=2\Delta_\sigma-1\approx0.036298.
$$

The magnetization exponent is

$$
\beta=\nu\Delta_\sigma\approx0.326419,
$$

and the critical-isotherm exponent is

$$
\delta=\frac{d-\Delta_\sigma}{\Delta_\sigma}\approx4.7898.
$$

These relations are often the cleanest way to translate between the CFT literature and the critical-phenomena literature.

## Bootstrap island

The numerical bootstrap studies crossing equations for correlators involving $\sigma$ and $\epsilon$, such as

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

The input assumptions include:

1. unitarity;
2. conformal symmetry in $d=3$;
3. $\mathbb Z_2$ symmetry;
4. the identification of $\sigma$ and $\epsilon$ as the leading odd and even scalars;
5. gaps to the next operators in selected sectors.

Crossing plus positivity excludes most possible values of $\Delta_\sigma$ and $\Delta_\epsilon$. With mixed correlators and gap assumptions, the allowed region becomes a small island.

This is not a perturbative calculation. It is a nonperturbative consistency result. The bootstrap does not start from the Ising lattice Hamiltonian or from the $\phi^4$ Lagrangian. It starts from the hypothesis that the desired CFT is a unitary $\mathbb Z_2$-symmetric solution of crossing with the right low-lying spectrum.

## Relation to the epsilon expansion

The Wilson–Fisher fixed point can be studied near four dimensions by setting

$$
d=4-\varepsilon.
$$

At small $\varepsilon$, perturbation theory finds a fixed point at coupling

$$
g_*\sim O(\varepsilon).
$$

The 3D Ising CFT corresponds to setting

$$
\varepsilon=1.
$$

This is not parametrically small, but resummed perturbation theory gives useful estimates. The epsilon expansion explains why the theory exists and why its operator spectrum is close to—but not equal to—that of a free scalar.

The bootstrap complements the epsilon expansion. Perturbation theory gives analytic control near $d=4$; bootstrap gives rigorous or semi-rigorous constraints directly in $d=3$.

A mature understanding of the 3D Ising CFT uses all available tools:

$$
\text{RG}+arepsilon\text{ expansion}+\text{Monte Carlo}+\text{high-temperature series}+\text{bootstrap}.
$$

## Relation to experiments and simulations

The 3D Ising universality class describes systems with a scalar order parameter and a $\mathbb Z_2$ symmetry or emergent $\mathbb Z_2$ critical behavior. Examples include uniaxial magnets, liquid-gas critical points, binary fluids, and lattice spin systems.

CFT data are universal. Microscopic details change nonuniversal quantities such as the critical temperature, lattice spacing, and normalization of microscopic operators. They do not change $\Delta_\sigma$, $\Delta_\epsilon$, or universal critical exponents.

A lattice spin variable $s_i$ does not equal $\sigma(x)$ exactly. At long distances it expands as

$$
s_i\sim A_\sigma\sigma(x)+A_{\sigma'}\sigma'(x)+\cdots,
$$

where $A_\sigma$ is nonuniversal. Similarly, the lattice energy density has overlap with $\epsilon$ plus other even operators.

This explains why universal exponents are shared by many systems, while raw correlation-function amplitudes are not.

## Comparison with the 2D Ising CFT

The two-dimensional Ising CFT is exactly solvable and is the minimal model $\mathcal M(3,4)$ with central charge

$$
c=\frac12.
$$

Its primary dimensions are rational:

$$
\Delta_\sigma=\frac18,
\qquad
\Delta_\epsilon=1.
$$

The 3D Ising CFT is very different. It has no Virasoro algebra, no holomorphic factorization, no finite minimal-model spectrum, and no known exact solution. Its conformal group is finite-dimensional, and its operator spectrum is infinite in the ordinary higher-dimensional sense.

The relation is conceptual rather than exact:

$$
\text{2D Ising: solvable Virasoro minimal model},
$$

$$
\text{3D Ising: interacting higher-dimensional CFT constrained numerically}.
$$

Both are Ising universality classes, but the mechanisms of solution are radically different.

## Deformations

The two leading relevant deformations are the thermal and magnetic perturbations:

$$
S_{\rm CFT}\to S_{\rm CFT}+t\int d^3x\,\epsilon(x)+h\int d^3x\,\sigma(x).
$$

The coupling $t$ moves the system away from critical temperature while preserving $\mathbb Z_2$. The coupling $h$ is the magnetic field and breaks $\mathbb Z_2$ explicitly.

Their RG eigenvalues are

$$
y_t=3-\Delta_\epsilon,
\qquad
 y_h=3-\Delta_\sigma.
$$

The signs and normalizations of $t$ and $h$ are nonuniversal. Their scaling dimensions are universal.

Irrelevant deformations such as the leading even scalar $\epsilon'$ control corrections to scaling. The dimension of the leading irrelevant scalar determines the correction-to-scaling exponent

$$
\omega=\Delta_{\epsilon'}-3.
$$

This exponent is important when comparing finite-size or finite-lattice simulations to continuum CFT predictions.

## Common pitfalls

**Do not confuse the lattice spin with the CFT primary exactly.** The lattice spin has leading overlap with $\sigma$, but also contains subleading odd operators.

**Do not identify $\phi^2$ naively with $\epsilon$ without qualification.** In the infrared, the microscopic thermal perturbation flows to $\epsilon$, but operator mixing and normalization matter.

**Do not use 2D Ising exact formulas in 3D.** The 3D Ising CFT has no Virasoro minimal-model solution.

**Do not treat the bootstrap island as assumption-free.** It depends on unitarity, $\mathbb Z_2$ symmetry, crossing, numerical truncation choices, and spectral gap assumptions.

**Do not confuse critical exponents with scaling dimensions.** They are related by scaling relations, but different communities quote different quantities.

**Do not overstate Lagrangian dependence.** The 3D Ising CFT can be reached from $\phi^4$ theory, but the fixed point is defined by universal conformal data, not by a unique microscopic action.

**Do not call every $\mathbb Z_2$ CFT the Ising CFT.** The Ising universality class is a specific solution with a specific spectrum and relevant-operator structure.

## Relations to other pages

This page follows [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) as the main small-$N$ benchmark of higher-dimensional bootstrap, even though $N=1$ is not a large-$N$ theory.

It prepares [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/) because the 3D Ising CFT is the $N=1$ member of the $O(N)$ Wilson–Fisher family. It also connects to [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/), [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), and [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/).

For the two-dimensional counterpart, see [Ising Model CFT](/cft-bootstrap/minimal-models-rational-cft/ising-model-cft/) and [Minimal Models](/cft-bootstrap/minimal-models-rational-cft/minimal-models/).

## Research status

The 3D Ising CFT is established as the continuum theory of the three-dimensional Ising universality class. Its leading scaling dimensions and several OPE coefficients are known to very high precision from the numerical conformal bootstrap and are consistent with Monte Carlo and RG approaches.

Active research includes increasingly precise stress-tensor and current-like data, subleading operator spectra, defect and boundary versions, thermal and Lorentzian observables, finite-size spectra, fuzzy-sphere regularizations, conformal perturbation theory away from criticality, and relations to experimental critical phenomena.

## Exercises

### Exercise 1

Using

$$
\Delta_\sigma=0.518148806,
\qquad
\Delta_\epsilon=1.41262528,
$$

compute $\nu$ and $\eta$ in $d=3$.

<details><summary><strong>Solution</strong></summary>

The correlation-length exponent is

$$
\nu=\frac1{3-\Delta_\epsilon}.
$$

Therefore

$$
\nu=\frac1{3-1.41262528}\approx0.629971.
$$

The anomalous dimension satisfies

$$
\Delta_\sigma=\frac{1+\eta}{2},
$$

so

$$
\eta=2\Delta_\sigma-1=2(0.518148806)-1\approx0.036298.
$$

</details>

### Exercise 2

Use $\mathbb Z_2$ symmetry to determine which parity sector appears in $\sigma\times\epsilon$.

<details><summary><strong>Solution</strong></summary>

The operator $\sigma$ is $\mathbb Z_2$ odd and $\epsilon$ is $\mathbb Z_2$ even. The product of parities is odd:

$$
(-1)(+1)=-1.
$$

Therefore only $\mathbb Z_2$-odd operators can appear in the $\sigma\times\epsilon$ OPE. The leading such operator is $\sigma$ itself, followed by subleading odd primaries such as $\sigma'$.

</details>

### Exercise 3

Why does $\sigma\times\sigma$ contain only $\mathbb Z_2$-even operators?

<details><summary><strong>Solution</strong></summary>

Both factors are odd under $\mathbb Z_2$, so their product is even:

$$
(-1)(-1)=+1.
$$

Thus the OPE can contain only even operators. The leading terms are

$$
\sigma\times\sigma=\mathbf1+\epsilon+T+\cdots .
$$

</details>

### Exercise 4

Explain why the stress tensor has $\Delta=3$ in the 3D Ising CFT.

<details><summary><strong>Solution</strong></summary>

In any local CFT in $d$ dimensions, the stress tensor is a conserved spin-two primary. The spin-two unitarity bound is

$$
\Delta\ge d.
$$

Conservation saturates the bound, so

$$
\Delta_T=d.
$$

For the 3D Ising CFT, $d=3$, hence

$$
\Delta_T=3.
$$

</details>

### Exercise 5

Why is the 3D Ising CFT not solved by the same methods as the 2D Ising CFT?

<details><summary><strong>Solution</strong></summary>

The 2D Ising CFT has the infinite-dimensional Virasoro symmetry and is a rational minimal model. This makes its spectrum and correlators exactly solvable.

In $d=3$, the conformal group is finite-dimensional. There is no generic Virasoro algebra, no holomorphic factorization, and no finite minimal-model spectrum. The 3D Ising CFT is therefore studied using higher-dimensional tools: numerical bootstrap, RG expansions, Monte Carlo simulations, and conformal perturbation theory.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- C.-H. Chang, V. Dommes, R. S. Erramilli, A. Homrich, P. Kravchuk, A. Liu, M. S. Mitchell, D. Poland, and D. Simmons-Duffin, “Bootstrapping the 3d Ising Stress Tensor,” 2024.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the ε Expansion,” *Physics Reports* **12** (1974).

## Version history

- 2026-07-01: First polished draft. Added leading operator data, critical exponent dictionary, bootstrap island explanation, RG and lattice interpretation, 2D comparison, deformations, exercises, and references.
