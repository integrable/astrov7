---
title: "Locality and Symmetry in EFT"
description: "How locality and symmetry determine the allowed operator expansion in an effective field theory, and why all allowed local terms must be included."
sidebar:
  label: "Locality and Symmetry"
  order: 2
level: Graduate
status: "Polished draft"
source: "Weinberg 1979; Polchinski 1984; Burgess 2020, chs. 2–4; Georgi EFT lectures; Manohar EFT reviews; Schwartz 2014, chs. 21–23."
topics:
  - effective field theory
  - locality
  - symmetry
  - operator basis
  - spurions
  - Wilson coefficients
canonicalTopics:
  - locality-in-eft
  - symmetry-in-eft
  - operator-basis
researchStatus:
  established:
    - "A local EFT contains all local operators compatible with the chosen light degrees of freedom and symmetries, organized by a power counting and modulo redundancies."
  active:
    - "Operator-basis construction remains active in high-order EFTs, gauge theories, gravitational EFTs, hydrodynamic EFTs, nonlinearly realized symmetries, automated Hilbert-series methods, and theories with generalized symmetries or boundaries."
---

## Summary

The practical rule for building an effective field theory is:

> Write the most general local Lagrangian built from the light degrees of freedom, consistent with the symmetries, then organize it by power counting.

This rule can feel extravagant. It tells you to include not just the operators you expect, but every operator not forbidden. The reason is renormalization. If an operator is allowed by the degrees of freedom and symmetries, quantum corrections will generically generate it. Excluding it without a symmetry or power-counting reason is not a prediction; it is an unstated fine tuning.

The general form is

$$
\mathcal L_{\text{EFT}}
=
\sum_i g_i\mathcal O_i
=
\mathcal L_{\text{leading}}
+
\sum_i \frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

Locality tells us that short-distance physics appears as a derivative expansion in local operators. Symmetry tells us which operators are allowed. Power counting tells us which allowed operators matter at a chosen accuracy.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![The EFT operator filter begins with light fields, applies locality and symmetries, quotients redundancies, orders terms by power counting, and outputs Wilson coefficients for predictions.](/figures/renormalization-rg-eft/eft-operator-filter.svg)

<figcaption>

The EFT construction rule is a filter, not a guess. Choose the light fields, impose locality and symmetries, remove redundant operators, order the survivors by power counting, and assign Wilson coefficients. Observables use the coefficients, matrix elements, and RG running together.

</figcaption>
</figure>

:::note[The all-allowed-terms rule]
An EFT Lagrangian should include all local operators compatible with its light fields and symmetries, through the order being computed. If a term is absent, the page must explain why: symmetry, redundancy, power counting, matching, or tuning.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/). The Wilsonian origin is in [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/) and [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/).

It is useful, but not required, to know [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), because the same operator-space logic will later control running.

## Core idea

Low-energy probes cannot resolve short-distance details. If the unresolved physics is separated from the long-distance physics by a scale $M$, then its effects can be expanded in powers of derivatives divided by $M$.

This is locality. A heavy propagator gives the prototype:

$$
\frac{1}{M^2-\Box}
=
\frac{1}{M^2}
+\frac{\Box}{M^4}
+\frac{\Box^2}{M^6}
+\cdots.
$$

Every power of $\Box$ gives a local operator with more derivatives. The low-energy theory therefore contains a tower of local terms.

But not every local term is allowed. The EFT must respect the symmetries that act on the light degrees of freedom. If a symmetry is exact, forbidden operators have zero coefficient. If a symmetry is approximate, the breaking must be tracked by small spurions or symmetry-breaking parameters. If a symmetry is spontaneously broken, the EFT may realize it nonlinearly. If the symmetry is a gauge redundancy, the operator basis must be gauge invariant or written in a gauge-fixed language with the corresponding Ward, Slavnov–Taylor, or BRST constraints.

The central principle is

$$
\text{low-energy action}
=
\text{all local symmetry-allowed terms}
\quad\text{ordered by size}.
$$

This is one of the most important rules in modern QFT. It is also one of the easiest to underuse.

## Setup and conventions

Let $\Phi$ denote all light fields kept in the EFT. They may include scalars, fermions, gauge fields, Goldstone fields, nonrelativistic fields, hydrodynamic variables, metric fluctuations, or background sources. A local operator has the schematic form

$$
\mathcal O_i(x)
=
\mathcal O_i\bigl(\Phi(x),\partial\Phi(x),\partial^2\Phi(x),\ldots\bigr),
$$

with all indices contracted according to Lorentz, rotation, internal, gauge, flavor, spacetime, and discrete symmetries appropriate to the problem.

The action is

$$
S_{\text{EFT}}
=
\int d^d x\,\mathcal L_{\text{EFT}},
\qquad
\mathcal L_{\text{EFT}}=\sum_i g_i\mathcal O_i.
$$

When an operator $\mathcal O_i$ has engineering dimension $\Delta_i$, it is often useful to write

$$
g_i=\frac{C_i}{M^{\Delta_i-d}},
$$

so that $C_i$ is dimensionless. This normalization is not mandatory. In chiral perturbation theory, nonrelativistic EFTs, SCET, hydrodynamics, and gravitational EFTs, a different normalization may make the power counting more transparent.

We use "symmetry" broadly. It includes:

| Type | EFT role |
|---|---|
| Lorentz or spacetime symmetry | constrains index contractions and derivative structures |
| internal global symmetry | organizes fields and forbids charged operators |
| gauge redundancy | requires gauge-invariant or BRST-consistent descriptions |
| discrete symmetry | forbids operators odd under the symmetry |
| approximate symmetry | organizes small breaking effects |
| spontaneously broken symmetry | constrains Goldstone interactions, often nonlinearly |
| accidental symmetry | may appear at low orders and be broken by higher operators |
| spurionic symmetry | tracks how symmetry-breaking parameters transform |

## Locality: why short-distance physics becomes operators

The EFT expansion is possible because long-distance observers cannot distinguish a compact source from its multipole moments. In QFT language, a short-distance subgraph with only light external legs can be replaced by a local vertex plus derivative corrections.

Schematic momentum dependence near $p=0$ takes the form

$$
F(p)=F(0)+p_\mu\left.\frac{\partial F}{\partial p_\mu}\right|_{p=0}
+\frac12p_\mu p_\nu
\left.\frac{\partial^2F}{\partial p_\mu\partial p_\nu}\right|_{p=0}
+\cdots.
$$

In position space this becomes a derivative expansion. Analytic dependence on small external momenta gives local operators.

The word analytic is doing real work. Nonanalytic low-energy behavior, such as

$$
\log(-p^2),
\qquad
\sqrt{4m^2-p^2},
\qquad
\frac{1}{p^2},
$$

usually signals light propagation, thresholds, or long-distance physics. Such effects should not be hidden inside local Wilson coefficients. They must be produced by explicit light fields and loops inside the EFT.

That is the locality test:

| Effect | EFT treatment |
|---|---|
| heavy off-shell propagation | local operators |
| light propagation | explicit fields and propagators |
| low-energy branch cuts | light loops or thresholds |
| topological or anomaly data | special local terms, constraints, or inflow structures |
| long-range forces | keep the mediator explicit |

A common mistake is to integrate out something that is not actually short-distance for the process under study. If a field is massless or nearly on shell, it belongs in the EFT.

## Symmetry: what is allowed

Symmetry does not merely decorate the EFT. It is the main organizing principle.

Suppose the light fields transform under a group $G$. An operator is allowed only if it is invariant under the exact symmetries, or if its non-invariance is compensated by spurions representing controlled symmetry breaking. For an internal symmetry,

$$
\Phi(x)\to R(g)\Phi(x),
\qquad g\in G,
$$

allowed operators must transform as singlets:

$$
\mathcal O_i(x)\to \mathcal O_i(x).
$$

For spacetime symmetry, Lorentz or rotational indices must be contracted properly. For gauge symmetry, one builds operators from covariant derivatives, field strengths, gauge-invariant combinations, or gauge-fixed variables with the correct BRST structure. For discrete symmetries, one tracks signs and complex conjugations carefully.

The most useful slogan is:

$$
\text{everything not forbidden is generated}.
$$

This does not mean every coefficient is large. A coefficient may vanish because of matching, be loop-suppressed, be spurion-suppressed, be $1/N$-suppressed, or be forbidden by a more subtle selection rule. But absence requires a reason.

## Building an operator basis

A practical EFT construction proceeds in steps.

### Step 1: Choose the light fields

List the fields that can propagate at the scale of interest. This is a physical decision, not a formal afterthought. Below $m_W$, the $W$ boson is not a light field. In chiral perturbation theory, pions are light Goldstone fields. In hydrodynamics, the fields are densities, velocity, temperature, and phases associated with conserved quantities.

### Step 2: State the symmetries

Include spacetime, internal, gauge, discrete, accidental, approximate, and spontaneously broken symmetries. Also state how sources and spurions transform. A sloppy symmetry statement leads to a sloppy EFT.

### Step 3: Write local building blocks

Use fields, covariant derivatives, field strengths, curvatures, spurions, invariant tensors, and background sources. For a gauge theory, ordinary derivatives usually become covariant derivatives:

$$
D_\mu=\partial_\mu-iA_\mu^aT^a.
$$

Field strengths enter through commutators:

$$
[D_\mu,D_\nu]=-iF_{\mu\nu}^aT^a.
$$

### Step 4: Form invariant operators

Contract indices and multiply building blocks to form scalars under the exact symmetries. Include all such terms through the desired order in the power counting.

### Step 5: Remove redundancies

Operators related by integration by parts, algebraic identities, Bianchi identities, equations of motion, and field redefinitions should not all be kept as independent basis elements.

For example, an integrated total derivative does not affect bulk equations or scattering in the absence of boundary effects:

$$
\int d^d x\,\partial_\mu K^\mu=0
$$

under suitable boundary conditions. EOM operators are redundant for many on-shell observables, though they can matter for contact terms and off-shell correlators.

### Step 6: Assign power counting

Order the independent operators by the expansion parameter. Engineering dimension is often a first guide, but the actual power counting may involve loop factors, small symmetry-breaking parameters, velocities, chiral dimensions, background gradients, large-$N$ factors, or multiple scales.

### Step 7: Match or measure coefficients

Each basis operator receives a Wilson coefficient. These coefficients are the short-distance data needed by the EFT.

The final product is not just a Lagrangian; it is a controlled approximation scheme.

## Example: a real scalar with a Z₂ symmetry

Let a light real scalar have a $\mathbb Z_2$ symmetry

$$
\phi\to -\phi.
$$

In four spacetime dimensions, and ignoring total derivatives, the lowest local operators include

$$
1,
\qquad
\phi^2,
\qquad
(\partial_\mu\phi)(\partial^\mu\phi),
\qquad
\phi^4,
$$

followed by higher-dimension terms such as

$$
\phi^6,
\qquad
\phi^2(\partial_\mu\phi)(\partial^\mu\phi),
\qquad
(\partial_\mu\phi\partial^\mu\phi)^2,
\qquad
\phi^8,
\qquad\ldots
$$

Terms odd in $\phi$, such as $\phi$ or $\phi^3$, are forbidden by the $\mathbb Z_2$ symmetry. If the symmetry is broken by a small spurion $\varepsilon$ that transforms as $\varepsilon\to-\varepsilon$, then odd operators can appear multiplied by odd powers of $\varepsilon$:

$$
\mathcal L\supset \varepsilon a_1\phi+\varepsilon a_3\phi^3+\cdots.
$$

This spurion language preserves the bookkeeping power of the symmetry even when the symmetry is not exact.

## Example: four-fermion operators

At energies far below a heavy vector boson of mass $M$, an exchange interaction between fermion currents can become a local four-fermion operator:

$$
\mathcal L_{\text{EFT}}
\supset
\frac{C}{M^2}
(\bar\psi\gamma^\mu\psi)(\bar\chi\gamma_\mu\chi).
$$

But symmetry determines which currents can appear. Lorentz invariance allows scalar, pseudoscalar, vector, axial-vector, and tensor bilinears. Gauge and flavor symmetries restrict which contractions are legal. Discrete symmetries may eliminate some combinations. Fierz identities may relate others. If the fermions are identical, additional antisymmetry constraints appear.

Thus "write the four-fermion operator" is not enough. An EFT basis requires the independent symmetry-allowed four-fermion operators, modulo identities.

## Example: Goldstone fields and nonlinear symmetry

When a continuous global symmetry is spontaneously broken,

$$
G\to H,
$$

the low-energy degrees of freedom include Goldstone fields valued in the coset $G/H$. The symmetry $G$ is still present, but it acts nonlinearly on the Goldstone coordinates.

This is the origin of derivative interactions in many Goldstone EFTs. A constant Goldstone configuration often corresponds to moving along the vacuum manifold, so non-derivative potentials are forbidden unless the symmetry is explicitly broken. The leading terms are built from derivatives:

$$
\mathcal L_{\text{Goldstone}}
\sim
\frac{f^2}{2}\partial_\mu\pi^a\partial^\mu\pi^a
+
O(\partial^4).
$$

The precise invariant building blocks depend on the coset construction, but the EFT philosophy is unchanged: light fields plus symmetry plus locality gives the allowed local expansion.

## Gauge symmetry and locality

Gauge symmetry is not an ordinary physical symmetry acting on distinct states. It is a redundancy in the description. That makes it even more constraining.

In a gauge-invariant EFT, local operators must be gauge invariant, or the gauge-fixed formulation must include the corresponding ghost, gauge-fixing, and BRST structure. For an Abelian gauge field, typical gauge-invariant building blocks include

$$
F_{\mu\nu},
\qquad
D_\mu\phi,
\qquad
\bar\psi i\gamma^\mu D_\mu\psi.
$$

For non-Abelian gauge theory, field strengths and covariant derivatives carry group indices that must be traced or contracted into singlets:

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}),
\qquad
\operatorname{tr}(F_{\mu}{}^{\nu}F_{\nu}{}^{\rho}F_{\rho}{}^{\mu}),
\qquad
\bar\psi F_{\mu\nu}\sigma^{\mu\nu}\psi,
$$

with the representation and normalization stated in context.

Gauge invariance can also force correlations among coefficients. For example, covariant derivatives contain gauge interactions tied to kinetic terms. One cannot arbitrarily change one vertex in a gauge EFT while leaving the symmetry-related vertices unchanged.

## Approximate symmetries and spurions

Many EFTs rely on approximate symmetries. A symmetry may be exact in a limit and broken by small parameters. Spurions encode this cleanly.

Suppose a parameter $m$ breaks a symmetry. Instead of declaring the symmetry gone, one assigns $m$ a transformation rule that makes the Lagrangian formally invariant. Operators are then classified by powers of $m$.

This is more than elegance. It tells us which symmetry-breaking terms are correlated. Examples include:

| EFT context | Spurion role |
|---|---|
| chiral perturbation theory | quark masses break chiral symmetry |
| flavor EFT | Yukawa matrices break flavor symmetry |
| weak interactions | CKM factors and weak couplings track symmetry breaking |
| soft symmetry breaking | small parameters preserve a controlled limit |
| lattice artifacts | powers of lattice spacing can be treated as spurions |

Spurions prevent a common mistake: treating every symmetry-breaking term as unrelated. If the microscopic breaking has a specific transformation structure, the EFT remembers it.

## Accidental and emergent symmetries

An EFT can have symmetries at low orders that are not exact symmetries of the microscopic theory. These are **accidental symmetries**.

For example, if the leading terms forbid a process but a higher-dimension operator allows it, the low-energy theory may appear to have a conservation law that is only approximate. The symmetry is accidental because it follows from the limited set of low-dimension operators, not from a fundamental principle.

This is a powerful idea. It explains why some processes can be very rare without being exactly forbidden. It also warns us that checking only the leading Lagrangian can overstate the symmetry of a theory.

An **emergent symmetry** is slightly different: it may appear near an RG fixed point or in the infrared because symmetry-breaking perturbations are irrelevant or dynamically suppressed. The EFT can then enjoy more symmetry at long distances than the microscopic description makes manifest.

## Locality can fail or change form

The local EFT expansion has conditions. It can fail or require modification when:

- there is no gap between the low-energy states and the states being removed;
- the process lies near a threshold or resonance;
- a massless mediator is integrated out incorrectly;
- the background varies on scales comparable to $M^{-1}$;
- the system has memory, dissipation, or open-system dynamics requiring nonlocal-in-time kernels;
- topological sectors or defects require extra global data;
- the EFT is being used outside its radius of convergence.

Near a resonance, for instance, the propagator

$$
\frac{1}{M^2-p^2-iM\Gamma}
$$

cannot be replaced by a simple derivative expansion if $p^2\approx M^2$. The resonance should be kept explicitly, or a specialized EFT should be used.

Near a massless threshold, logarithms and branch cuts are long-distance physics. They belong to the EFT loops, not to local Wilson coefficients.

## The main rule in practice

When writing an EFT calculation, a trustworthy page or paper should state:

1. the light degrees of freedom;
2. the symmetries, including approximate and spurionic ones;
3. the expansion parameter and power counting;
4. the operator basis through the required order;
5. the redundancies removed;
6. the scheme and scale used for Wilson coefficients;
7. the matching or measurement inputs;
8. the estimated size of omitted terms.

This is the EFT equivalent of specifying a gauge, regulator, and renormalization scheme in perturbation theory. Without it, the calculation may still be intuitively right, but it is hard to check.

## Common pitfalls

**Forgetting allowed operators.** If an operator is allowed by the symmetries, it generally appears under renormalization. Omitting it without explanation makes the EFT unstable.

**Overusing symmetry.** Symmetry forbids what transforms incorrectly. It does not choose a unique coefficient, and it rarely chooses a unique operator.

**Confusing exact and approximate symmetries.** Exact symmetries forbid terms. Approximate symmetries suppress terms. Spurions keep the difference visible.

**Treating gauge symmetry as optional.** Gauge redundancy constrains the entire operator basis and the relations among vertices. It cannot be imposed diagram by diagram after the fact.

**Integrating out light fields.** Nonanalytic low-energy behavior is a sign that a light mode has been removed improperly or that the EFT is being used near a threshold.

**Counting only engineering dimension.** Real EFT power counting can involve loops, symmetry-breaking parameters, velocities, chiral dimensions, inverse heavy masses, background gradients, and multiple scales.

**Dropping EOM operators without tracking the observable.** EOM operators can be redundant for on-shell amplitudes but relevant to contact terms, sources, and off-shell correlators.

**Ignoring boundaries and defects.** Total derivatives and field redefinitions can become physical when boundaries, interfaces, defects, or nontrivial topology are present.

## Relations to other pages

This page turns [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/) into the construction rule for Lagrangians. The next pages, [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/) and [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), explain how locality becomes an ordered derivative expansion and how the operator tower becomes a calculational hierarchy.

For redundancy and bases, see [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/) and [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/). For operator mixing under RG, see [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/). For explicit coefficient determination, continue later to [Matching](/renormalization-rg-eft/effective-field-theory/matching/) and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

## Research status

The principle of writing all local symmetry-allowed operators is established. It is the backbone of chiral perturbation theory, heavy-particle EFTs, nonrelativistic EFTs, SMEFT, gravitational EFT, hydrodynamic EFT, and many condensed-matter effective descriptions.

Active work concerns difficult operator bases and subtle symmetry structures: high-dimension SMEFT bases, Hilbert-series counting, nonlinearly realized symmetries, redundant operators in gauge theories, curved-space and gravitational operators, dissipative and open-system EFTs, boundaries and defects, generalized symmetries, and automated matching and running.

The conceptual frontier is not whether locality and symmetry organize EFTs. It is how far this organization can be pushed when locality is approximate, symmetries are categorical or higher-form, the system is out of equilibrium, or the separation of scales is only partial.

## Exercises

### Exercise 1: Z₂ scalar operators

In four spacetime dimensions, a real scalar field has $\mathbb Z_2$ symmetry $\phi\to-\phi$. List the independent bulk operators of dimension up to six that can appear in a Lorentz-invariant EFT, ignoring total derivatives and using leading equations of motion only for basis reduction.

<details><summary><strong>Solution</strong></summary>

The field dimension is $[\phi]=1$ and $[\partial_\mu]=1$. The $\mathbb Z_2$ symmetry allows only even powers of $\phi$.

Up to dimension four, the standard operators are

$$
1,
\qquad
\phi^2,
\qquad
(\partial_\mu\phi)(\partial^\mu\phi),
\qquad
\phi^4.
$$

At dimension six, representative operators include

$$
\phi^6,
\qquad
\phi^2(\partial_\mu\phi)(\partial^\mu\phi),
\qquad
(\Box\phi)^2,
\qquad
\phi^3\Box\phi,
$$

before reducing the basis. Up to total derivatives,

$$
\phi^3\Box\phi
= -3\phi^2(\partial_\mu\phi)(\partial^\mu\phi).
$$

Using the leading EOM can also remove operators involving $\Box\phi$ in favor of non-derivative terms, depending on the chosen leading Lagrangian. A common reduced basis through dimension six contains

$$
\phi^6,
\qquad
\phi^2(\partial_\mu\phi)(\partial^\mu\phi),
$$

besides lower-dimension terms, but the exact displayed basis depends on the chosen EOM convention and normalization.

</details>

### Exercise 2: Locality from a heavy propagator

Show that a tree-level amplitude proportional to

$$
\frac{1}{M^2-s}
$$

can be reproduced at $s\ll M^2$ by a tower of local operators with increasing numbers of derivatives. What is the expansion parameter?

<details><summary><strong>Solution</strong></summary>

For $s\ll M^2$,

$$
\frac{1}{M^2-s}
=
\frac{1}{M^2}
\frac{1}{1-s/M^2}
=
\frac{1}{M^2}\left(1+\frac{s}{M^2}+\frac{s^2}{M^4}+\cdots\right).
$$

Since $s$ is quadratic in external momenta, each power of $s$ corresponds in position space to two additional derivatives. The expansion parameter is

$$
\frac{s}{M^2}\sim \frac{Q^2}{M^2}.
$$

The tower of local operators reproduces the amplitude only away from the heavy pole at $s=M^2$.

</details>

### Exercise 3: Spurion bookkeeping

A theory has a real scalar $\phi$ and an approximate $\mathbb Z_2$ symmetry $\phi\to-\phi$. A small parameter $\varepsilon$ breaks the symmetry. Assign a spurion transformation to $\varepsilon$ and determine whether $\varepsilon\phi^3$ and $\varepsilon^2\phi^3$ are formally invariant.

<details><summary><strong>Solution</strong></summary>

Assign

$$
\varepsilon\to-\varepsilon
$$

under the spurionic $\mathbb Z_2$. Since

$$
\phi^3\to-\phi^3,
$$

the product $\varepsilon\phi^3$ transforms as

$$
\varepsilon\phi^3\to (-\varepsilon)(-\phi^3)=\varepsilon\phi^3,
$$

so it is formally invariant. But

$$
\varepsilon^2\phi^3\to \varepsilon^2(-\phi^3)=-\varepsilon^2\phi^3,
$$

so it is not invariant. The spurion rule says that odd-$\phi$ operators require odd powers of the symmetry-breaking spurion.

</details>

## References

- Steven Weinberg, "Phenomenological Lagrangians," *Physica A* **96** (1979) 327–340, for the all-terms-consistent-with-symmetry effective-Lagrangian principle.
- Joseph Polchinski, "Renormalization and Effective Lagrangians," *Nuclear Physics B* **231** (1984) 269–295, for the Wilsonian logic behind local effective actions.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on effective actions, power counting, matching, redundant interactions, and symmetries.
- Howard Georgi, lectures on effective field theory, for practical operator construction and symmetry reasoning.
- Aneesh V. Manohar, reviews and lectures on EFT, for modern power counting and operator-basis methodology.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on renormalizability, nonrenormalizable theories, and RG.
- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II, for effective Lagrangians, symmetries, and field redefinitions in QFT.

## Version history

- 2026-06-18: First polished draft. Explained locality as a derivative expansion, symmetry as an operator filter, the all-allowed-terms rule, basis construction, spurions, gauge constraints, accidental symmetries, locality caveats, and common EFT construction pitfalls.
