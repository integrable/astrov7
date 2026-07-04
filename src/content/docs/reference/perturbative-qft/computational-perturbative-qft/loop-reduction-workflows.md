---
title: "Loop Reduction Workflows"
description: "A reproducible workflow for mapping loop amplitudes to integral families, reducing them to master integrals, and validating the result."
sidebar:
  label: "Loop Reduction Workflows"
  order: 3
level: Advanced
status: "Polished draft"
source: "Passarino–Veltman; Chetyrkin–Tkachov IBP; Laporta; FIRE; Kira; LiteRed; Reduze; pySecDec; Henn; Smirnov."
topics:
  - computational perturbative QFT
  - loop integrals
  - integral reduction
  - IBP identities
  - master integrals
  - validation
canonicalTopics:
  - loop-reduction-workflows
  - integral-family-mapping
  - ibp-reduction-workflows
  - master-integral-pipelines
researchStatus:
  established:
    - "Tensor reduction, integration-by-parts identities, sector organization, and reduction to master integrals are standard components of loop calculations in dimensional regularization."
  active:
    - "Multi-scale multi-loop reductions, finite-field reconstruction, canonical bases, elliptic sectors, numerical stability, and large distributed workflows remain active research and software-development areas."
---

## Summary

Loop reduction is the workflow that turns loop amplitudes into a finite set of reusable master integrals. A typical scalar integral family is written as

$$
I(\vec a)
=
\mu^{2L\epsilon}
\int\prod_{r=1}^L\frac{d^d\ell_r}{i\pi^{d/2}}
\frac{1}{D_1^{a_1}\cdots D_N^{a_N}},
\qquad
 d=4-2\epsilon,
$$

where the denominators $D_i$ are quadratic or linear functions of loop and external momenta. Negative or zero entries among the $a_i$ are often used to encode numerator factors.

The reduction problem is to express many such integrals as

$$
I(\vec a)=\sum_k c_k(d,s_{ij},m_i^2)\,M_k,
$$

where the $M_k$ are master integrals and the coefficients $c_k$ are rational functions of the dimension and kinematic invariants. Reduction is not evaluation. It tells you which integrals remain; a separate analytic or numerical method computes them.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Loop reduction workflow from diagrams to integral families, IBP identities, master integrals, evaluation, and validation](/figures/perturbative-qft/loop-reduction-workflows.svg)

<figcaption>

A loop-reduction workflow maps generated amplitudes to integral families, reduces tensor and numerator structures, applies integration-by-parts identities, chooses master integrals, evaluates them, and assembles a checked amplitude. Each stage has its own failure modes and validation tests.

</figcaption>
</figure>

This page explains the workflow logic. It is deliberately tool-agnostic: FIRE, Kira, LiteRed, Reduze, pySecDec, FORM-based pipelines, Mathematica notebooks, and custom finite-field systems are examples of implementations, not replacements for the method.

## Prerequisites

You should know [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), [Feynman Parameters](/perturbative-qft/loop-integral-technology/feynman-parameters/), [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/), [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/), [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/), [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/), and [Diagram Generation Workflows](/perturbative-qft/computational-perturbative-qft/diagram-generation-workflows/).

## Core idea

Loop amplitudes contain too many integrals to evaluate one by one. The same integrals recur with shifted propagator powers, numerator scalar products, different tensor ranks, and different diagrams. Reduction exploits algebraic identities to express this large set in a smaller basis.

A reliable loop-reduction workflow has six layers:

| Layer | Main task | Typical output |
|---|---|---|
| amplitude preparation | generate diagrams and simplify algebra | loop-momentum expressions |
| family assignment | choose denominators and map integrals | integral labels $I(\vec a)$ |
| numerator reduction | express tensor numerators in scalar products | scalar integrals with shifted indices |
| identity generation | produce IBP and symmetry relations | linear equations among integrals |
| master reduction | solve equations and choose masters | coefficients multiplying $M_k$ |
| evaluation and assembly | compute masters and rebuild amplitude | renormalized or bare loop result |

The reduction is only as good as the mapping. If two equivalent integrals are assigned to different families without a bridge relation, the result bloats. If an irreducible numerator is dropped, the result is wrong. If a scaleless subtopology is not identified, the output may contain ghosts of integrals that are zero in dimensional regularization. Not fun ghosts. Bookkeeping ghosts.

## Setup and conventions

We use dimensional regularization with $d=4-2\epsilon$ for the formulas on this page. The normalization of the loop measure is written explicitly because different tools use different factors of $i$, $\pi^{d/2}$, $e^{\gamma_E\epsilon}$, and $4\pi$. Translating these factors is boring but essential.

A loop family is specified by denominators

$$
D_i=q_i(\ell_r,p_a)^2-m_i^2+i\epsilon,
$$

or by linear denominators in eikonal and effective-theory integrals. The scalar integral is labeled by integer powers $a_i$. Positive $a_i$ are propagators. Zero or negative $a_i$ often indicate absent propagators or irreducible numerator factors.

A workflow should record:

| Choice | Why it matters |
|---|---|
| loop-momentum routing | determines the denominator list and family mapping |
| integral normalization | affects master-integral definitions and comparison with literature |
| regulator convention | controls powers of $\mu$, $4\pi$, and $\gamma_E$ |
| kinematic region | fixes analytic continuation and branch prescriptions |
| masses and thresholds | determine singularities and boundary conditions |
| family symmetries | reduce duplicate integrals and equations |
| master basis | affects compactness and differential-equation structure |
| treatment of scaleless sectors | prevents zero integrals from polluting the result |

## From diagrams to integral families

Start with an amplitude written as a sum of loop integrals. For a one-loop bubble with external momentum $p$, a natural family is

$$
D_1=\ell^2-m_1^2+i\epsilon,
\qquad
D_2=(\ell+p)^2-m_2^2+i\epsilon,
$$

with

$$
I(a_1,a_2)
=\mu^{2\epsilon}\int\frac{d^d\ell}{i\pi^{d/2}}\frac{1}{D_1^{a_1}D_2^{a_2}}.
$$

A numerator such as $\ell\cdot p$ can be expressed in terms of denominators and irreducible scalar products. In this bubble family,

$$
2\ell\cdot p
=(\ell+p)^2-\ell^2-p^2
=D_2-D_1+m_2^2-m_1^2-p^2.
$$

Thus the numerator does not require a new master structure; it shifts propagator powers and adds simpler integrals.

At higher loops, one chooses enough denominators to span all scalar products involving loop momenta. If some scalar products cannot be expressed through denominators, they become irreducible scalar products. They are usually represented by negative powers of auxiliary denominators.

## Tensor reduction and numerator control

Tensor loop integrals contain loop momenta in the numerator:

$$
\int\frac{d^d\ell}{i\pi^{d/2}}\frac{\ell^\mu\ell^\nu}{D_1D_2\cdots}.
$$

Lorentz covariance allows them to be decomposed into tensors built from external momenta and the metric. For a two-point one-loop vector integral,

$$
B^\mu(p)=\int\frac{d^d\ell}{i\pi^{d/2}}\frac{\ell^\mu}{D_1D_2},
$$

the only available vector is $p^\mu$, so

$$
B^\mu(p)=p^\mu B_1(p^2;m_1^2,m_2^2).
$$

This is the simplest Passarino–Veltman idea. At higher points and higher loops, direct tensor reduction can generate large denominators involving Gram determinants. Modern workflows often prefer to express numerators in integral-family form and let IBP reduction handle the scalar integrals.

The practical rule is: reduce tensors enough to get a controlled scalar-integral representation, but do not simplify away the structure needed for stable family mapping.

## Integration-by-parts identities

The key identity is that total derivatives vanish in dimensional regularization when no boundary contribution survives:

$$
0=
\int\prod_{r=1}^L d^d\ell_r\,
\frac{\partial}{\partial \ell_i^\mu}
\left(
\frac{v^\mu}{D_1^{a_1}\cdots D_N^{a_N}}
\right),
$$

where $v^\mu$ is built from loop and external momenta. Expanding the derivative gives linear relations among integrals with shifted indices. These are the integration-by-parts, or IBP, identities.

A large IBP system has the form

$$
\sum_j A_{ij}(d,s,m^2) I_j=0,
$$

where the $I_j$ are integrals in the chosen family and nearby sectors. Solving this system expresses harder integrals in terms of simpler ones and ultimately in terms of master integrals.

The Laporta strategy orders integrals by a complexity measure and solves the linear system recursively. Modern implementations use symmetries, finite fields, modular arithmetic, sparse linear algebra, distributed computation, and careful sector ordering to keep the system from eating the building.

## Sectors, subtopologies, and symmetries

A sector records which denominators are present. For a family with denominators $D_1,\ldots,D_N$, the sector can be represented by the subset of indices with positive powers.

Why sectors matter:

| Feature | Use |
|---|---|
| top sector | contains all chosen propagators |
| subsectors | correspond to contracted lines or simpler topologies |
| sector symmetries | identify integrals related by momentum shifts or graph automorphisms |
| zero sectors | contain scaleless or kinematically forbidden integrals |
| boundary sectors | often provide simpler master integrals |

A good family choice minimizes the number of unrelated sectors. A poor choice turns equivalent integrals into strangers, and strangers make terrible linear systems.

Symmetry detection is not cosmetic. If a graph has a loop-momentum shift mapping $D_1\leftrightarrow D_2$, the reduction should use it. Otherwise the solver may rediscover the same relation the hard way.

## Master integrals

Master integrals are a basis for the quotient of all integrals in a family by IBP and symmetry relations. They are not unique. A different basis gives different coefficients and different analytic convenience.

A master basis is judged by several criteria:

| Criterion | Why it helps |
|---|---|
| small number of masters | compact amplitudes and fewer functions to evaluate |
| good analytic behavior | simpler branch cuts and thresholds |
| uniform transcendental weight | simpler differential equations when available |
| finite integrals | improved numerical stability |
| physical normalization | easier comparison to cuts and limits |
| simple boundary values | easier analytic evaluation |

In the differential-equation method, one differentiates masters with respect to kinematic invariants and reduces the result back to the master basis:

$$
\frac{\partial}{\partial x}\vec M(x,\epsilon)
= A(x,\epsilon)\vec M(x,\epsilon).
$$

A particularly good basis can make the $\epsilon$ dependence factorized or otherwise simple. Such bases are powerful, but they are not guaranteed for every integral family, especially when elliptic or more general functions appear.

## A minimal bubble reduction

Consider the equal-mass bubble family

$$
D_1=\ell^2-m^2+i\epsilon,
\qquad
D_2=(\ell+p)^2-m^2+i\epsilon.
$$

The scalar bubble is $I(1,1)$. A numerator integral with $\ell\cdot p$ reduces because

$$
2\ell\cdot p=D_2-D_1-p^2.
$$

Therefore

$$
\int\frac{d^d\ell}{i\pi^{d/2}}\frac{\ell\cdot p}{D_1D_2}
=\frac12\left[
\int\frac{d^d\ell}{i\pi^{d/2}}\frac{1}{D_1}
-
\int\frac{d^d\ell}{i\pi^{d/2}}\frac{1}{D_2}
-p^2 I(1,1)
\right].
$$

By shifting $\ell\to\ell-p$, the two tadpole integrals are equal. Thus the numerator integral is expressed in terms of the tadpole and the scalar bubble. This tiny example already shows the general pattern: rewrite numerator scalar products, use symmetry or momentum shifts, and reduce to a smaller set.

## Practical workflow

### Step 1: prepare the amplitude

Generate diagrams, apply Feynman rules, simplify spinor and color algebra, and separate tensor structures from loop integrals. Keep enough metadata to reconstruct each integral's diagrammatic origin.

### Step 2: choose integral families

Pick denominators that cover every loop-momentum scalar product appearing in the amplitude. Keep families aligned with graph topologies and expected symmetries.

### Step 3: map every integral

Convert each loop expression into a label $I(\vec a)$ in a family. Reject unmapped terms. An unmapped numerator is not a warning to ignore; it is the calculation tapping you on the shoulder.

### Step 4: find symmetries and zero sectors

Use graph automorphisms, loop-momentum shifts, mass degeneracies, and scaleless-integral tests. This should happen before generating a huge IBP system.

### Step 5: generate and solve identities

Create IBP identities, possibly Lorentz-invariance identities, and solve them with a clear integral ordering. Store reduction rules in a versioned, reusable form.

### Step 6: choose and evaluate masters

Use known analytic formulas, differential equations, Mellin–Barnes methods, sector decomposition, expansion by regions, or numerical integration. Record the kinematic region and branch prescription.

### Step 7: assemble and validate

Insert master integrals back into the amplitude. Check UV poles, IR poles, known limits, symmetries, thresholds, and numerical stability.

## Validation checklist

| Check | What it detects |
|---|---|
| family coverage | missing denominators or irreducible numerators |
| dimension counting | wrong loop measure or numerator power |
| symmetry relations | duplicate sectors or bad momentum routing |
| scaleless-sector removal | spurious zero integrals |
| pole structure | missing counterterms or wrong regulator normalization |
| cut structure | wrong analytic continuation or missing thresholds |
| known one-loop limits | normalization errors |
| differential-equation consistency | bad master basis or reduction table |
| numerical sample comparison | algebraic reduction mistakes |
| independent tool comparison | implementation-specific errors |

A useful habit is to test reduction on random rational kinematic points before inserting complicated analytic master integrals. If the reduction fails numerically, the closed-form answer will not heal it.

## Reduction versus evaluation

Reduction and evaluation solve different problems.

| Question | Reduction answers | Evaluation answers |
|---|---|---|
| Which integrals are independent? | yes | no |
| What coefficients multiply the masters? | yes | no |
| What functions appear? | only indirectly | yes |
| What is the value in a physical region? | no | yes |
| Where are the branch cuts? | partly through denominators | yes |
| How do UV and IR poles enter? | through coefficient and master expansions | yes after expansion |

Confusing reduction with evaluation leads to misleading confidence. A reduction table can be perfectly correct while the wrong branch of a master integral is used. Conversely, a numerical sector-decomposition result may evaluate an integral without explaining how it fits into the amplitude basis.

## Common pitfalls

**Choosing families too late.** If simplification destroys topology information, mapping integrals becomes harder.

**Ignoring loop-momentum shifts.** Equivalent integrals can be duplicated unless family symmetries are detected.

**Dropping irreducible numerators.** Negative indices or auxiliary denominators are often necessary, not optional.

**Treating masters as unique.** Master integrals are basis-dependent. A bad basis can make a simple amplitude look monstrous.

**Forgetting normalization factors.** Factors of $i$, $\pi^{d/2}$, $e^{\gamma_E\epsilon}$, $4\pi$, and $\mu^{2\epsilon}$ differ across tools and papers.

**Trusting reductions near singular kinematics without checks.** Gram determinants, thresholds, and exceptional points can make coefficients look singular even when the amplitude is finite.

**Forgetting scaleless integrals.** In dimensional regularization, scaleless integrals vanish. Keeping them can obscure cancellations; dropping non-scaleless integrals by mistake is worse.

**Not saving the reduction tables.** Large reductions are expensive. A reproducible workflow stores both the generated equations and the solved rules.

## Relations to other pages

- [Diagram Generation Workflows](/perturbative-qft/computational-perturbative-qft/diagram-generation-workflows/) explains the upstream graph and amplitude inventory.
- [Tensor Integral Reduction](/perturbative-qft/loop-integral-technology/tensor-integral-reduction/) introduces numerator and Lorentz-tensor decomposition.
- [Passarino–Veltman Reduction](/perturbative-qft/loop-integral-technology/passarino-veltman-reduction/) gives the classic one-loop tensor-reduction method.
- [Integration-by-Parts Identities](/perturbative-qft/loop-integral-technology/integration-by-parts-identities/) derives the identities used by modern reduction engines.
- [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/) explains the basis remaining after reduction.
- [Differential Equations for Integrals](/perturbative-qft/loop-integral-technology/differential-equations-for-integrals/) explains one major method for evaluating master integrals.
- [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) and [Landau Singularities](/perturbative-qft/loop-integral-technology/landau-singularities/) give analytic checks on master integrals and amplitudes.

## Research status

- **Established:** Passarino–Veltman reduction at one loop, IBP identities, Laporta-style reductions, sector organization, and master-integral bases are standard tools in perturbative QFT.
- **Active:** Multi-scale multi-loop reductions remain computationally hard. Active directions include finite-field reconstruction, syzygy-based identities, canonical-basis searches, elliptic and beyond-elliptic functions, numerical unitarity, GPU and distributed workflows, and machine-learning-assisted reduction strategies.
- **Convention-dependent:** Integral normalizations, regulator factors, master bases, kinematic regions, analytic continuations, and definitions of scalar integral libraries differ across tools and references.

## Exercises

### Exercise 1: Rewriting a bubble numerator

For the bubble family

$$
D_1=\ell^2-m_1^2+i\epsilon,
\qquad
D_2=(\ell+p)^2-m_2^2+i\epsilon,
$$

express $\ell\cdot p$ in terms of $D_1$, $D_2$, masses, and $p^2$.

<details>
<summary><strong>Solution</strong></summary>

Start from

$$
D_2-D_1
=(\ell+p)^2-m_2^2-\ell^2+m_1^2.
$$

Expanding $(\ell+p)^2=\ell^2+2\ell\cdot p+p^2$ gives

$$
D_2-D_1=2\ell\cdot p+p^2+m_1^2-m_2^2.
$$

Therefore

$$
\ell\cdot p
=\frac12\left(D_2-D_1-p^2-m_1^2+m_2^2\right).
$$

This turns the numerator into shifted propagator powers and simpler integrals.

</details>

### Exercise 2: A one-loop tadpole IBP identity

Let

$$
T_a=\int d^d\ell\,\frac{1}{(\ell^2-m^2+i\epsilon)^a}.
$$

Use

$$
0=\int d^d\ell\,\frac{\partial}{\partial\ell^\mu}\left(\frac{\ell^\mu}{(\ell^2-m^2+i\epsilon)^a}\right)
$$

to derive a relation between $T_a$ and $T_{a+1}$.

<details>
<summary><strong>Solution</strong></summary>

Expanding the derivative gives

$$
0=\int d^d\ell\left[
\frac{d}{D^a}
-a\frac{2\ell^2}{D^{a+1}}
\right],
\qquad
D=\ell^2-m^2+i\epsilon.
$$

Use $\ell^2=D+m^2-i\epsilon$. The infinitesimal term only fixes the pole prescription and does not affect the algebraic mass relation. Thus

$$
0=dT_a-2a\int d^d\ell\left(\frac{D}{D^{a+1}}+\frac{m^2}{D^{a+1}}\right).
$$

Therefore

$$
0=(d-2a)T_a-2am^2T_{a+1}.
$$

Equivalently,

$$
T_{a+1}=\frac{d-2a}{2am^2}T_a.
$$

This is a tiny IBP reduction: all higher tadpole powers reduce to one master tadpole, assuming $m\ne0$.

</details>

### Exercise 3: Why scaleless tadpoles vanish

Explain why

$$
\int d^d\ell\,\frac{1}{(\ell^2+i\epsilon)^a}
$$

vanishes in dimensional regularization when no other scale is present.

<details>
<summary><strong>Solution</strong></summary>

The integral has no mass scale and no external momentum scale. By dimensional analysis it would have dimension $d-2a$, but there is no scale from which to build a quantity of that dimension. Dimensional regularization sets such scaleless integrals to zero. Equivalently, their ultraviolet and infrared divergences cancel after analytic continuation. This is a conventionally compact way of saying that the integral contains no physical scale-dependent information by itself.

</details>

### Exercise 4: Vector two-point decomposition

For a one-loop two-point integral depending only on an external momentum $p$, explain why

$$
B^\mu(p)=\int\frac{d^d\ell}{i\pi^{d/2}}\frac{\ell^\mu}{D_1D_2}
$$

must have the form $B^\mu=p^\mu B_1$.

<details>
<summary><strong>Solution</strong></summary>

After integration, the only available Lorentz vector is the external momentum $p^\mu$. The integration measure and denominators are Lorentz invariant, so the result must transform as a vector built from available external data. There is no other vector in a two-point function. Therefore

$$
B^\mu(p)=p^\mu B_1(p^2;m_1^2,m_2^2),
$$

where $B_1$ is a scalar function. Contracting with $p_\mu$ determines $B_1$ in terms of scalar numerator integrals.

</details>

## References

- G. Passarino and M. Veltman, “One-loop corrections for $e^+e^-$ annihilation into $\mu^+\mu^-$ in the Weinberg model,” *Nuclear Physics B* **160** (1979), for classic one-loop tensor reduction.
- K. G. Chetyrkin and F. V. Tkachov, “Integration by parts: The algorithm to calculate beta functions in 4 loops,” *Nuclear Physics B* **192** (1981), and F. V. Tkachov, “A theorem on analytical calculability of four-loop renormalization group functions,” for IBP identities.
- S. Laporta, “High-precision calculation of multiloop Feynman integrals by difference equations,” for systematic reduction by solving large IBP systems.
- A. V. Smirnov and collaborators, FIRE documentation and papers, for modern IBP reduction implementations.
- P. Maierhöfer, J. Usovitsch, and P. Uwer, “Kira — A Feynman integral reduction program,” for a modern Laporta-style reduction tool.
- R. N. Lee, “LiteRed 1.4: a powerful tool for reduction of multiloop integrals,” for Mathematica-based IBP and symmetry workflows.
- A. von Manteuffel and C. Studerus, “Reduze 2 — Distributed Feynman integral reduction,” for distributed reduction and topology identification.
- J. M. Henn, “Multiloop integrals in dimensional regularization made simple,” for canonical differential equations.
- S. Borowka et al., “pySecDec: a toolbox for the numerical evaluation of multi-scale integrals,” for numerical sector-decomposition workflows.
- V. A. Smirnov, *Feynman Integral Calculus* and *Analytic Tools for Feynman Integrals*, for broader integral technology.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, appendices on regularization and loop integrals, for an accessible QFT-oriented entry point.

## Version history

- **2026-06-13:** Initial polished draft. Added workflow map, family and IBP definitions, bubble example, validation checklist, and solved exercises.
